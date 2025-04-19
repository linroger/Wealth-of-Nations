---
tags:
  - adverse_selection
  - asset_pricing
  - bid_ask_spread
  - liquidity
  - market_microstructure
  - trading
aliases:
  - Chapter 6
  - Market Microstructure
  - Trading and Liquidity
key_concepts:
  - Adverse selection and trading
  - Bid-ask spread and asset pricing
  - Liquidity and spreads
  - Market microstructure impacts prices
  - Trader information asymmetry
---

# Adverse Selection, Trading, and Liquidity  

# 6.1 MARKET MICRO STRUCTURE, LIQUIDITY, AND SPREADS  

In Section 1.5, we characterized market micro structure as being concerned with the markets for transaction services. In Section 1.6, we noted that liquidity refers to the ability to easily transact without causing significant price changes. However, it is important to appreciate that while liquidity is easily recognized by every trader, it is a somewhat elusive concept, unobservable and cannot be properly measured with a single metric or proxy. Volumes or spreads might be used as simple measures to capture certain aspects of liquidity, but we know from price impact that both are far from being a complete measure of liquidity.  

More generally, this chapter is concerned with information, uncertainty,  adverse selection (a party to a contract using her superior information to the disadvantage of her counterparty) and dealer inventories on trading and market micro structure. We will examine how market micro structure impacts trader behavior and prices. Later in this section, we will examine a simple model depicting how security spreads affect prices and returns. Material in this chapter is of practical importance to traders because it forms an important basis for many algo and HFT trading models in which traders anticipate order flow based on characteristics of existing and past order flow.  

Traders are dependent on information, but differences in trader access to information can have perverse effects on liquidity and how securities are priced. We will discuss in Sections 6.2 to 6.6  how traders with inferior information alter their trading behavior in the presence of counter parties with superior information.  

Liquidity and liquidity risk play important roles in the pricing of securities (see, for example,  Amihud, Mendelson, & Pederson, 2005 ). Empirical studies verify that reductions in liquidity reduce security prices and increase required returns (e.g.,  Chan, Hong, & Sub rahman yam, 2008; Chaplinsky & Ramchand, 2004 ).  Brennan and Sub rahman yam (1996) question this positive relationship between asset returns and liquidity, but  Brennan, Chordia, Sub rahman yam, and Tong (2012)  find that sell-side il liquidity and its effects far exceed buyside il liquidity and its effects, and that this sell-side il liquidity is reflected in security returns.  
In Chapter 4, we discussed liquidity as a function of direct transactions costs and the price impact of trading. First, consider how transactions costs affect the price of a security. We will extend this discussion in this chapter by examining the roles of uncertainty, information asymmetry, and dealer inventories on liquidity. First, we will discuss the effects of liquidity on prices and returns as reflected in spreads.  

# Asset Pricing and the Bid-Ask Spread  

In the absence of uncertainty and dividend growth, the familiar Gordon stock pricing model is:  

$$
P=\!{\frac{d}{r}}
$$  

where    $P$   is the stock value,    $d$   is the constant annual dividend payment, and  $r$   is the appropriate discount rate. Now, consider a market with transactions costs reflected by a constant relative spread  s    $(s{=}(P_{a}-P_{b})/P),$  , and where the stock is traded    $\eta$   times per year. An investor buys the stock from a market maker at price    $P_{a},$   sells it to the market maker at  $P_{b},$   $P$  and adjusts his valuation    of the stock accordingly. We revise the Gordon model as follows (See  Amihud & Mendelson, 1986 ):  

$$
P=\frac{d}{r+\eta s}
$$  

Essentially, the total annual transactions cost as reflected by the proportional spread is added to the discount rate for purposes of valuation; the value of an asset is reduced by the present value of all of its expected future trading costs. The proportional spread incurred  $\eta$   times per year must be recovered before an investor can break even. For example, a stock traded twice per year with an average spread of  $3\%$   paying annual dividends equal to  $\S1$   discounted at  $5\%$   is valued under each of our two frameworks as:  

$$
P={\frac{\S1}{0.05}}=\S20\quad P={\frac{\S1}{0.05+2\times0.03}}=\S9.09
$$  

Clearly, the spread has a substantial impact on the value of the security. Notice that a reduction in the spread from  $3\%$   to  $1\%$   would significantly increase the stock price:  

$$
P=\frac{\S1}{0.05+2\times0.01}=\S14.29
$$  

Now, suppose that the discount rate in the absence of a spread for the stock,  $\scriptstyle{r=E[R]=0.05,}$  , is determined by the Capital Asset Pricing Model or other valuation model when there is no liquidity premium. In economies where stock expected returns include liquidity risk premiums, stock expected returns would be    $E[R]{=}r{+}\eta s$  . For our two liquidity risk premium scenarios, expected returns are    $E[R]{=}0.05{+}2\times0.03{=}0.11$   and   $[R]{=}0.05$   $+2\times0.01{=}0.07$  . Obviously, the absence of liquidity that causes spreads to increase will increase expected (required) returns and decrease prices. In the next several sections, we will discuss factors that affect this spread, including uncertainty, adverse selection, noise trading, dealer inventories, and volatility.  
# 6.2 INFORMATION AND TRADING  

The  economics of information  is concerned with how information along with the quality and value of this information affect an economy and economic decisions. Information can be inexpensively created, can be reliable, and, when reliable, is valuable. Some economists have suggested that more than half of the U.S. economy is currently engaged in activities that are producing and analyzing information products. In fact, revenues obtained by the New York Stock Exchange from selling trading data exceed its trading-fee based revenues. The simplest microeconomics models assume that information is costless and all agents have equal access to relevant information. But, such assumptions do not hold in reality, and costly and asymmetric access to information very much affects how traders interact with each other. Investors and traders look to the trading behavior of other investors and traders for information, which affects the trading behavior of informed investors who seek to limit the information that they reveal.  

In Chapter 4, we discussed slippage and market impact models, describing how prices move against traders who execute large orders due to the perceived information content of those orders. Here, particularly in our discussion of the  Bagehot (1971) ,  Kyle (1985) , and Glosten and Milgrom (1985)  models, we discuss the market mechanisms causing prices to react to the information content of trades (market impact or slippage), and how traders and dealers can react to this information content to maximize their own profits (or minimize losses). This chapter is concerned primarily with problems that arise when traders and other market participants have inadequate, different ( asymmetric information availability ), and costly access to information. In this chapter, we discuss information and information a symmetries in a trading context.  

# Adverse Selection  

Adverse selection  originally referred to the tendency of higher risk individuals to seek insurance coverage. More generally, adverse selection refers to pre contractual opportunism where one contracting party uses his private information to the counter party’s disadvantage. For example, the adverse selection problem can arise when a woman planning a pregnancy purchases health insurance, when a car rental customer secretly planning a trip through a Golan Heights minefield buys comprehensive insurance on the car, or when a pyromaniac purchases fire insurance. In all three cases, the agent (insured or customer) has private information with respect to the higher anticipated costs of the insurance coverage or lease, but pays a “pooling” premium for the incident or casualty coverage. Obviously, this private information affects the behavior of insurers and other insured clients, in what might otherwise be taken to be a suboptimal manner, referred to as the adverse selection problem. In a financial trading context, adverse selection occurs when one trader with secret or special information uses that information to her advantage at the expense of her counter party in trade. Trade counter parties realize that they might fall victim to adverse selection, so they carefully monitor trading activity in an effort to discern which trades are likely to reflect special information. For example, large or numerous buy (sell) orders originating from the same trader are likely to be perceived as being motivated by special information. Trade counter parties are likely to react by adjusting their offers (bids) upwards (downwards), resulting in slippage as we discussed in Chapter 4. This market impact or slippage is the market’s reaction to the adverse selection problem. In this chapter, we will consider the impact of the adverse selection problem on order sizes, security prices, and the spread.  
# 6.3 NOISE TRADERS  

N oise traders  trade on the basis of what they falsely believe to be special information or misinterpret useful information concerning the future price or payoffs of a risky asset. Noise traders make investment and trading decisions based on incorrect perceptions or analyses of the market, perhaps creating opportunities for more sophisticated investors and traders. In many models of markets, noise traders are assumed to have no useful information or at least react inappropriately to useful information concerning a security’s fundamentals. But, do noise traders distort prices? If noise traders trade in large numbers, if their trading behavior is correlated, or if their effects cannot be mitigated by informed and rational traders, they may well distort prices from fundamental values. In many models, individual investors are presumed to be noise traders and that their psychology (see Chapter 11) and poor access to information inhibit their trading success.  

In  1953 , the economist Milton Friedman suggested that traders who produce positive profits do so by trading against less rational or poorly informed investors who tend to move prices away from their fundamental or correct values.  Fama (1965)  argued that when irrational trading does occur, security prices will not be significantly affected because more sophisticated traders will react quickly to exploit and eliminate any deviations from fundamental economic values.  Figlewski (1979)  suggested that it might take irrational investors a very long time to lose all their money and for prices to reflect security intrinsic values, but nonetheless, those traders who choose their portfolios irrationally are doomed in the long run.  

Noise traders are useful, perhaps even necessary, for markets to function. Without noise traders, markets would be information ally efficient. Prices would always fully reflect information (to the extent that market frictions and liquidity trading are absent). Even with asymmetric information access, informed traders can fully reveal their superior information through their trading activities, and prices would reflect this information and ultimately eliminate the motivation for information-based trading. That is, as  Black (1986) argued, without noise traders, dealers would widen their spreads to avoid losing profits to informed traders such that no trades would ever be executed. However, noise traders do impose on other traders the risk that prices might move un predictably, irrationally, and without reference to relevant information. In some instances, this risk imposed by noise traders might discourage arb it rage urs from acting to exploit price deviations from fundamental values. Prices can deviate significantly from rational valuations, and can remain different for long periods. In fact, arb it rage urs might sometimes need to ask themselves the following important question: “Does my ability to remain solvent exceed the asset price’s ability to remain irrational?” We will discuss this issue more in Chapter 7.  
# 6.4 ADVERSE SELECTION IN DEALER MARKETS  

Bagehot (1971)  described a market where dealers or market makers stand by to provide liquidity to every trader who wishes to trade, losing on trades with informed traders but recovering these losses by trading with uninformed, noise, or liquidity-motivated traders. The market maker sets prices and trades to ensure this outcome, on average. The market maker merely recovers his operating costs along with a “normal return.” In this framework, trading is a zero-sum or neutral game. Informed investors armed with special information or superior analytical skills will earn abnormal returns; uninformed investors will lose more than they make. In fact, the more frequently an uninformed trader trades, the more he can be expected to lose, and these trading losses are reflected as informed trader profits. Market makers observe buying and selling pressure on prices and set prices accordingly, often making surprisingly little use of fundamental analysis when making their pricing decisions.  Kyle’s (1985)  theoretical model describes the trading behavior of informed traders and uninformed market makers who set prices in an environment with noise traders.  

# Kyle: Informed Traders, Market Makers, and Noise Traders  

Suppose that two rational traders have access to the same information and are otherwise identical. They have no motivation to trade. Now, suppose they have different information. Will they trade? Not if one trader believes that the second will trade only if the second has information that will enable him to profit at the first trader’s expense. Traders will not trade if they expect to lose money to their counter party in trade. In fact, rational traders might not trade against other rational traders even if their information differs. This is a variation of the Akerlof “lemon problem,” in which traders lacking superior information decline to trade with traders who have superior information. So, why do we observe so much trading in the marketplace? Most of us believe that others are not as informed or rational as we are or that others do not have the same ability to access and process information that we do. Or, maybe one of the parties makes price concessions sufficient to cover any informational advantage (e.g.,  Rock, 1986 ). In Kyle’s analysis, the market maker sets prices so that his losses to informed traders are offset by profits realized from noise trader transactions. Therefore, we are happy to trade with our less informed and capable counter parties.  

# The Setting: Kyle’s Adverse Selection Model  

Kyle models edict trading and price setting in a market where some traders are informed and others (noise or liquidity traders) are not. Dealers or market makers, who have information only about net demand for or supply of the stock, serve as intermedia ries between informed and uninformed traders, and seek to set security prices that enable them to survive even without the special information enjoyed by informed traders. Kyle models how informed traders will use their information to maximize their trading profits given that their trades yield useful information to market makers. Furthermore, market makers will seek to learn from the informed trader’s trading behavior, and the informed trader will seek to disguise his special information from the dealer by reducing the volume of his trading activity. Successful deception by the informed trader will reduce the price slippage imposed by the market maker who sets the stock price.  
Traders rely on the market and on each other for information. Suppose, for example, that the unconditional value of a stock in a  Kyle (1985)  framework is normally distributed with an expected value equal to    $E[v]$   and a variance equal to    $\Sigma_{0}$  . However, suppose that the informed trader has private information that the value of the stock is actually    $v$   and is able to reduce his own uncertainty to zero. Uninformed investor trading is random, normally distributed with an ex-ante expected net share demand of zero   $(E[u]{=}0;$   negative net demand represents net selling activity or net supply) and a variance equal to    $\Bar{\sigma}_{u}^{2}$  . In the Kyle model, the informed trader and noise traders take the first step and submit market orders to the dealer, who can observe the total level of order volume    $X{=}x{+}u_{,}$  , where    $u$  reflects aggregate noise trader transactions and  $x$   reflects informed demand. However, the dealer cannot distinguish between  $x$   and    $u$  . The dealer’s problem is to set a market clearing price    $p$   for the security so that his losses on transactions with informed traders are offset by his profits from trading with noise traders.  

# Informed Trader Demand  

In the context of the Kyle model, what allows the informed trader to maximize trading profits and gives the informed trader the ability to camouflage his trades by having them appear to blend in with noise traders? First, any time that    $v\ >\ E[v]$   (or,    $v\ <\ E[v])$  ), the informed trader’s private information indicates a buying opportunity (selling opportunity), and the purchase (sale) of additional shares increases his profits. Thus, in the absence of the market maker inferring information from the informed trader’s demand and adjusting market prices accordingly, the informed trader’s profits are maximized when  $x$   equals    $\infty$   given favorable private information or    $-\infty$   given negative information. However, the market maker does observe and use the level of total demand    $X{=}[x{+}u]$   for the stock. While uninformed demand  $u$   is purely random,    $X$   is directly, though imperfectly related to    $x$  . When the market maker observes a large total demand    $X,$   she infers, with error, a high informed demand level  $x,$   and accordingly increases the market price    $p$   of the stock, decreasing the informed trader’s profits. Thus, the larger the informed trader’s demand, the more shares he purchases and the greater will be the informed trader’s trading profits in the absence of price changes. However, high total demand    $X$   for the stock will cause the market maker to increase the stock price  $p.$  , thereby decreasing the informed trader’s profits. In the presence of these offsetting pressures on profits, how does the informed trader set his order size? As we demonstrate in Appendix A to this chapter, the informed trader’s demand is linearly related to the informed trader’s informational advantage    $|v-E[v]|$   but inversely related to the uncertainty    $\Sigma_{0}$   resolved by informed trader demand relative to the noise    $\sigma_{u}^{2}$    associated with uninformed trader demand:  

$$
x=\frac{v-E[v]}{\sqrt{\Sigma_{0}/\sigma_{u}^{2}}}
$$  
Thus, the informed trader’s purchase demand for shares increases at a constant rate as his informational advantage    $v-E[v]$   and uninformed trader camouflage    $\sigma_{u}$   increase, but decreases with his anticipation that the market maker expects his uncertainty advantage improves   $(\Sigma_{0})$  . Similarly, the informed trader’s selling supply for shares increases as the absolute value of his informational advantage  $v-E[v]$   and uninformed trader camouflage  $\sigma_{u}$   increase, but decreases with his anticipation that the market maker expects his uncertainty advantage improves   $(\Sigma_{0})$  .  

# Market Maker Price-Setting  

The informed trader would prefer to purchase or sell an infinite number of shares to exploit his informational advantage, but cannot because the market maker would correctly infer that his transactions convey meaningful information and resolves uncertainty at a rate related to  $\Sigma_{0}/\sigma_{u}^{2}$  . Thus, the market maker institutes price revisions leading to slippage in the market price  $p$  . At what level does the dealer set the market price, given her observation of the total demand    $X{=}[x{+}u]?$   As we demonstrate in Appendix A to this chapter, the market maker sets a price that is linearly related to total demand    $X{=}[x{+}u]$   for the stock, directly related to the uncertainty    $\Sigma_{0}$   resolved by informed trader demand relative to the noise  $\dot{\sigma_{u}^{2}}$    associated with uninformed trader demand:  

$$
p=E[v]+\left(\frac{\mathbf{1}}{2}\,\sqrt{\Sigma_{0}/\sigma_{u}^{2}}\right)(x+u)=E[v]+\frac{\mathbf{1}}{2}\,\lambda(x+u)
$$  

Thus, the market price of the stock set by the market maker equals its expected value plus its total demand multiplied by a sensitivity factor    $\lambda$   related to the proportion of uncer   $\lambda$  tainty presumed to have been resolved by the informed trader. Thus,  (sometimes referred to as  Kyle’s lambda ) is the sensitivity of the dealer price to order flow;   $1/\lambda$   measures the depth of the market (the order flow needed to cause the price to change by  $\S1.$  ) for the stock. If the market maker believes that the informed trader uncertainty resolution is large compared to uninformed trader volatility, she will adjust the market price of the stock by larger amounts given total demand    $x{+}u$  .  

There is an abundance of empirical evidence on the relationship between order flow and market impact (See for example,  Zarinelli, Treccani, Farmer, & Lillo, 2015 ). While Kyle, due to simplifying assumptions, predicts a positive and linear relationship (positive and constant lambda), statistical evidence seems more consistent with a positive and concave relationship. This concavity might be partly explained by a combination of factors, including the tendency of the informed trader to slice trade sizes and trade over time and dealer risk aversion.  

# Illustration: Kyle’s Adverse Selection Model  

Suppose in this example, that the unconditional value of a stock in a  Kyle (1985)  framework is normally distributed with an expected value equal to    $E[v]{=}\Phi50$   and a variance equal to  $\Sigma_{0}{=}30$  . However, the informed trader has private information that the value of the stock is actually  $v{=}\S45$   per share. Uninformed investor trading is random and normally distributed with an ex-ante expected net share demand of zero and a variance    $\sigma_{u}^{2}$    equal to 5000. The dealer can observe the total level of order volume    $\scriptstyle{X=x+u}$   where  $u$   reflects noise trader transactions and    $x$   reflects informed demand, but the dealer cannot distinguish between  $x$   and  $u$  .  
Under the market and trading circumstances set forth above, what would be the level of informed trader demand for the stock? Since    $v\,<\,E[v],$  , the informed trader will wish to sell shares, and we solve for  $x$   as follows, using  Equation (6.1) :  

$$
x=\frac{v-E[v]}{\sqrt{\Sigma_{0}/\sigma_{u}^{2}}}\!=\!\frac{45-50}{\sqrt{\frac{30}{5000}}}\!=\!\frac{-\,5}{0.07746}\!=\,-\,64.5497
$$  

Thus, the informed trader will provide a net supply of 64.5497 shares to be sold in the marketplace. Notice that an increase in either the variance of uninformed trader demand  $\sigma_{u}^{2}$    or the expected value of the asset without special information    $E[v]$   would increase the number of shares that the dealer informed trader would supply. On the other hand, an increase in either the amount of information that the informed trader’s special information resolves    $\Sigma_{0}$   or the true value of the asset would reduce the supply by the informed trader.  

The informed trader would wish to sell an infinite number of shares to earn a  $\S5$   profit on each, but cannot because the market maker would correctly infer that his share sales convey meaningful information, and the market maker’s price revisions would lead to slippage. Thus, at what level does the market maker set her price, given the total demand  $\scriptstyle X=[x+u]=\ -\ 64.5497+0$   that she observes? Since the order volume    $X$   is negative, the market maker will set a price less than its unconditional expected value equal to 50, and we solve for the price level using  Equation (6.2)  as follows:  

$$
p=50+{\frac{1}{2}}{\sqrt{30/5000}}(-64.5497+0)=47.50
$$  

In this scenario, net uninformed order level was zero. For a given increase in the total order flow, we expect that the dealer price would increase by the amount of that increase times  $\lambda=0.5\ \times\ \dot{(30/5000)}^{0.5}=0.03873.$  . For example, how would informed order flow and the market maker price level change if uninformed order level were actually 40 shares rather than zero? First, since the informed trader does not know about uninformed orders, his net demand (supply) is unaffected. However, the market maker sets her price based on the sum of total order flow as follows:  

$$
p=50+{\frac{1}{2}}{\sqrt{30/5000}}(-64.5497+40)=49.049=47.50+0.03873\times40=49.049
$$  

Since the market maker was unable to distinguish between the informed and uninformed orders, the impact of the informed sell orders was muted somewhat by the noise trader buy orders and the market maker set a market price that reduced slippage from its earlier level above. This camouflage enabled the informed trader to obtain a better price for the sale of his shares.  
# Kyle: Empirical Evidence  

Significant evidence from stock markets, recent and not so recent, supports many predictions of the Kyle model of strategic informed trading. For example,  Koudijs (2015) , in a simple setting involving trading of English securities in 18th century Amsterdam and London markets, was able to identify the impact of private information. These primitive markets are ideal for examining the applicability of Kyle’s model because of the muchdelayed arrival of inside information from London to Amsterdam by boats delivering mail packets containing private correspondence and newsletters with public information. This combination of slow information transmission and the absence of insider trading regulation enabled insiders to strategically exploit their superior information, and enabled Koudijs to examine how prices incorporated this private information through the trading process. In particular, insiders would strategically time their more aggressive trading based on the anticipated arrival of the next vessel from London in a manner consistent with Kyle‘s predictions.  

In a similar vein, though based on much later trading scenarios,  Boland n azar, Jackson, Jiang, and Mitts (2020)  conducted a “natural experiment” that examined how accidental early releases of security disclosures by the SEC that informed certain traders ultimately incorporated new information into security prices, producing an empirical work that complimented the theoretical work of  Kyle (1985) . The dates, times, and content of these accidental private releases as well as their later public releases were all known to the researchers. Noise trading and informational advantage impacted aggressive insider trading much as Kyle‘s model predicted, with less insider trading intensity in the presence of less noise trading and increasing in the insider’s relative information advantage. Among the important findings of both Koudijs and Boland n azar et al. is that insiders trade strategically ' for example, when anticipating longer delays to public revelation of private information, they trade more patiently, and otherwise, much as the Kyle model would predict.  

# 6.5 ADVERSE SELECTION, DEALER INVENTORIES, AND THE SPREAD  

Walrasian markets assume perfect and friction less competition where supply of and demand for securities are simultaneously apparent. Market micro structure is, in large part, concerned with how imperfect competition, frictions, and the non synchronous arrival of supply and demand impact markets. Walrasian markets are perfectly efficient; market micro structure is concerned with inefficiencies and their impact on the market. In security markets, imperfect competition, bid ' offer imbalances, and frictions often reveal themselves in bid ' offer spreads. Here, we are concerned with the determinants of the bid ' offer spread. First, the evolution of prices through time should provide insight as to what affects the spread. Consider, for example, frictions such as transaction costs and taxes. If these were the only factors affecting the spread, we should expect that in the absence of new information, execution prices would tend to bounce between bid and ask prices. For example, after a trade at the bid price, the next trade would be either at the same price or at the offer. After a trade at the offer, the next trade would be either at the same price or the bid. That is, price changes would tend to be either zero or at the opposite side of the spread. Thus, execution prices will tend to be either unchanged or to change in the opposite direction from the most recent transaction. Thus, transaction costs tend to induce negative serial correlation in asset prices, particularly in the absence of new information.  
On the other hand, asymmetric information tends to produce positive serial correlation in asset prices. Now, suppose that asymmetric information is the only source of the spread, such that transaction prices reflect information communicated by transactions. Transactions executed at bid prices would cause permanent drops in prices to reflect negative information and transactions executed at offer prices would cause permanent increases in prices to reflect positive information. However, the extent to which information arrives randomly will induce a random element in price changes. Thus, if price changes are solely a function of random news arrival, price changes will be random. If the distribution of information is asymmetric, prices will exhibit positive serial correlation as informed traders communicate their information through their trading activity (recall that this is what informed traders try to avoid in the Kyle model). Thus, the extent to which information distribution is asymmetric will affect the serial correlation of asset prices. Increased informational a symmetries imply positively correlated price changes from one transaction to the next.  

Inventory costs (such as un systematic risk caused by the dealer’s inability to diversify) will tend to cause negative serial correlations in price quotes. Transactions at the bid will tend to cause risk averse dealers to reduce their bid quotes as they become more reluctant not to over diversify their inventories. Similarly, transactions at the ask will tend to cause dealers to raise their quotes as they become more reluctant not to under diversify their inventories. Thus, inventory costs and transaction costs will tend to lead towards negative serial correlation in security prices. As we noted above, asymmetric information availability will lead towards positive serial correlation in security prices as transactions communicate new information.  

# The Demsetz Immediacy Argument  

As we discussed earlier, trader bids and offers do not arrive to markets simultaneously. Order imbalances impose waits on impatient traders requiring immediacy. The costs of providing immediacy to liquidity traders include order processing costs (transaction costs), information and adverse selection costs, inventory holding costs, costs of absorbing inventory risks, and costs of providing trading options. The bid ' offer spread provides the dealer compensation for assuming these costs on behalf of the market. Each of these costs is examined in the following sections. But first, in the  Demsetz (1968)  analysis, buyers and sellers of a security are each of two types, one of which who wants an immediate transaction and a second who wants a transaction, but can wait. Buy and sell orders arrive to the market in a non synchronous fashion, causing order imbalances. An imbalance of traders demanding an immediate trade causes price slippage and the less patient trader to pay for immediacy. The greater the costs of trading, and the greater will be the desire for immediacy, the greater will be the market spread.  
# Glosten and Milgrom Information Asymmetry Model  

The  Glosten and Milgrom (1985)  adverse selection model assumes that dealer spreads are based on the likelihood  $\pi$   (  $\cdot\pi$   is a probability, not a profit level in this scenario) that an informed trader (one who knows the value of the asset) will trade. Trades arrive to the market maker, each with some random chance of originating from either an informed or uninformed trader. Suppose that the asset can take on one of two prices, a high price  $P_{H}$  and a low price  $P_{L},$   each with probability   $1/2$  . The informed trader originates the trade with probability    $\pi$   and knows which price the asset will take on. Liquidity or uninformed traders will not pay more than    $P_{H}$   for the asset and they will not sell for less than    $P_{L}$  . Thus, the informed trader will sell only when the asset is worth    $P_{L}$   and will buy only when the asset is worth    $P_{H}.$  . Risk-neutral liquidity traders value the asset at   $(P_{H}+P_{L})/2$  . When setting his quotes, the dealer needs to account for the probability that an informed trader will transact at his quote, and will set his bid price    $P_{b}$   and ask price  $P_{a}$   as follows:  

$$
\begin{array}{r}{P_{b}=\pi P_{L}+(1-\pi)(P_{H}+P_{L})/2}\\ {P_{a}=\pi P_{H}+(1-\pi)(P_{H}+P_{L})/2}\end{array}
$$  

The spread is simply the difference between the ask and bid prices:  

$$
P_{a}-P_{b}=\pi(P_{H}-P_{L})
$$  

Thus, in the single-period Glosten and Milgrom model, the spread is a function of the likelihood that there exists an informed trader in the market and uncertainty in the value of the traded asset. The greater the uncertainty in the value of the traded asset as reflected by  $(P_{H}-\,P_{L}),$  , and the greater the probability    $\pi$   that a trade has originated with an informed trader, the greater will be the spread. Increased uncertainty and increased information a symmetries lead to increased spreads.  

Clearly, traders, including market makers (dealers), will seek to avoid trading with an informed trader and have an interest in knowing the probability that their counter parties in trade will be informed. How might a trader estimate the probability that his counter party in trade is informed? Suppose that a trader can estimate the risk of a security in a dealer market, and based on his risk estimate, the trader believes that the price of a stock will fall between 20 and 24, with potential prices being uniformly distributed in this range. The trader believes that informed traders will know with certainty the value of the stock. Further suppose that the dealer’s bid-offer quotations are 22 and 23, respectively. The trader relies on his risk estimates as well as the dealer’s quotes (spread) to determine the probability that an informed trader is active in this market. Based on these quotes provided by the dealer, what is the probability that a given trade will have originated with an informed trader? Since    $P_{a}\,-\,P_{b}=\pi(P_{H}\,-\,P_{L}),$  ,    $\pi\overset{_{-}}{=}(P_{a}-P_{b})/(P_{H}-P_{L})=(23\small{-}22)/(24\small{-}20)=.25$  . Thus, the trader estimates a 25% probability that his trading counter party is informed. Essentially, the trader relies on the dealer’s knowledge of market participants as reflected through the dealer spread. As the dealer spread widens, the trader associates a higher probability that he would trade with an informed trader. The trader can use this probability to determine whether he should trade at this time.  Glosten and Milgrom (1985)  extend their modeling over series of sequential trades and more sophisticated scenarios, as do  Easley and O’Hara (1987 and 1992) .  
# 6.6 RISK, RISK AVERSION, AND DEALER SPREADS  

# The Stoll Inventory Model  

A risk averse dealer needs to maintain inventories in assets in which he makes a market to sell to investors as well as cash to purchase assets from investors. First, we will discuss determinants of dealer behavior in the absence of dealer inventory. Suppose that a dealer currently without inventory in a particular asset    $P$   trades so as to maximize the expected utility level that he associates with his uncertain level of wealth    $W.^{2}$    We assume here that the dealer’s wealth level is subject to some normally distributed security return represented by  $r$   whose expected value, for sake of simplicity, is assumed to be zero. This security produces an uncertain profit equal to    $r P$   and a variance of profits equal to    $\sigma^{2}$  . The dealer is willing to quote a bid price    $P_{b}$   to purchase this security whose consensus value or consensus price is    $P$  . This consensus price can be considered to be the true value estimate for the security. Our problem here is to determine the maximum price that a risk averse dealer would be willing to bid; in the absence of inventory, we show that the level of this bid is a function of the dealer’s level of risk aversion. First, we note that the maximum bid that the dealer is willing to quote would be that which equates the expected utility associated with his current uncertain level of wealth after purchasing the risky security with the level of utility he would realize if he opted not to purchase the risky security and its associated risk:  

$$
E[U(W-P_{b}+(1+r)P)]=U(W)
$$  

Rewriting to adjust expected utility for the expected trading profit against the bid and return over time on the asset consensus value:  

$$
E(U(W+(P-P_{b})+r P)]=U(W)
$$  

Thus, the dealer’s expected utility after the security purchase is a function of his current level of wealth    $W,$   his bid price    $P_{b},$   and his uncertain return. If the security is not purchased, the dealer’s utility will be a function of his current wealth level. Our problem is to solve this equality for  $P_{b}$  . We start by performing a Taylor series expansion:  

$$
E[U(W)+(P-P_{b}+r P)U^{\prime}(W))+{1/2}(P-P_{b}+r P)^{2}(U^{\prime\prime}(W))+\ldots]=U(W)
$$  

$E[r]=0,\ E[r P]U^{\prime}(W)$  Since    can be dropped from the equality. In addition, we note that  $\sigma^{2}=E[(P\mathrm{~-~}P_{b}+r P)^{2}]$  :  

$$
E[U(W)+(P-P_{b})U^{\prime}(W))+1/2(\sigma)^{2}(U^{\prime\prime}(W))+\ldots]=U(W)
$$  

We will approximate by dropping all of the left-hand-side higher-order terms not explicitly stated in the above equality, which is quite reasonable if we are willing to assume that the risk is normally distributed, meaning, for example, that  $E[r^{3}]$   will equal 0. Our pricing equation simplifies as follows:  
$$
\begin{array}{r l}&{(P-P_{b})(U^{\prime}(W))\approx-\,1/2(\sigma)^{2}U^{\prime\prime}(W)}\\ &{(P-P_{b})\approx-\,1/2(\sigma)^{2}U^{\prime\prime}(W)/U^{\prime}(W)}\\ &{(P-P_{b})\approx1/2(\sigma)^{2}A R A}\end{array}
$$  

where    $-\,U^{\prime\prime}(W)/U^{\prime}(W)$   is the dealer’s  Arrow-Pratt absolute risk aversion coefficient  (ARA). The ARA indicates the dealer’s aversion   $(U^{\prime\prime}(W)<0)$   to a given risk, based on his utility of wealth function    $U(W)$   and his current level of wealth. As the dealer’s level of risk aversion increases, the absolute value of    $U^{\prime\prime}(W)$   increases relative to    $U^{\prime}(W)$   since risk aversion is presumed to result from diminishing marginal utility to additional units of wealth. Thus, the greater the dealer’s risk aversion, or the greater the uncertainty associated with the asset, the greater will be the discount associated with his bid.  

Now, suppose that the dealer maintains an initial inventory    $W_{p}$   of securities constituting his initial wealth level    $W_{p}$  . The dealer is free to borrow and lend at the riskless rate    $r_{f\!\mathrm{,~}}$   for sake of simplicity, assumed to be zero. This initial inventory of securities    $W_{p}$   is an optimal portfolio that maximizes the dealer’s utility associated with his uncertain level of wealth W  subject to his initial wealth constraint:  

$$
E[U(W_{p}(1+r_{p})+(P-P_{b})+r P)]=U(W_{p})
$$  

where  $r$   is the uncertain return on the tradable asset    $i$   and    $r_{p}$   is the uncertain return on the optimal portfolio    $W_{p}$  . As we did above, we will expand the left side of this equation around    $E[U(W_{p})],$   and assuming that    $E[r]=E[r_{p}]=\bar{0},$  , and after dropping higher-order terms, we have:  

$$
)+(P-P_{b})(U^{\prime}(W_{p}))+1/2(\sigma^{2})U^{\prime\prime}(W_{p})+2\times1/2\times E[r P\times r_{p}W_{p}]\times U^{\prime\prime}(W_{p})]\approx U
$$  

The covariance of cash flows between profits on the optimal portfolio and the tradable asset  $i$   is   $2\times{}^{1}\!/\!_{2}\times E[r_{P}\times r_{p}W_{p}]=\sigma_{i,P}$  . A larger dealer inventory of security    $i$   in the initially optimal portfolio    $W_{p}$   implies a larger covariance    $\sigma_{i,P}$   between    $i$   and    $W_{p}$  . Simplifying and solving for   $(P\mathrm{~-~}P_{b})$  , we find that the dealer’s bidding discount from the consensus price is:  

$$
(P-P_{b})=\sigma_{i,p}A R A+1/2(\sigma)^{2}A R A
$$  

Again, the discount   $(P\mathrm{-}P_{b})$   implied by the dealer’s bid increases as the dealer’s level of risk aversion increases and as the asset risk increases. But, with non-zero inventory levels, the dealer’s situation changes, and the bid discount is affected by the covariance of his inventory level and the performance of security  $i.$   Notice that a higher level of  $\sigma_{i,P}$   implies  $i$   $W_{p}$  a higher level of covariance between security    and the dealer’s optimal portfolio    that includes his inventory of security    $i.$  . The greater the dealer’s inventory level, the greater will be his risk as implied by    $\sigma_{i,P}$   along with its associated loss of diversification, and the less he will be willing to bid for an additional unit of security  i .  
In addition to increasing his bid discount when his level of risk aversion increases and/ or when the risk of security    $i$   increases, the dealer will increase his bid discount as his inventory of securities increases and as the covariance between his inventory returns and the asset returns increases. Similarly, the premium based the dealer’s ask or offer price    $P_{a}$  is obtained as follows:  

$$
(P_{a}-P)=\sigma_{i,p}A R A+1/2(\sigma)^{2}A R A
$$  

Thus, the dealer will increase his offer premium as his inventory of securities decreases and as the covariance between his inventory returns and the asset returns decreases. The bid ' offer spread is simply the sum of the bid discount and the offer premium:  

$$
(P_{a}-P_{b})=(\sigma^{2})A R A
$$  

Thus, the greater the dealer’s risk aversion, or the greater the uncertainty associated with the asset, the greater will be the dealer’s spread. Interestingly, the dealer’s inventory level does not affect the size of the spread, although it will affect each of the two price quotes from which the spread is determined. As the dealer’s inventory increases, his reluctance to purchase additional units of the security is offset by his willingness to sell units, simultaneously decreasing both his bid and ask prices by comparable amounts. Consequently, the dealer with non-zero inventory will not place his quotations so that the consensus value of the security is centered within the bid and offer. Instead, the spread will straddle the consensus price, with one quote being closer to the consensus price than the other. Both quotes will decrease as his inventory increases and will increase as his inventory decreases. Other traders can “approximate” the dealer’s consensus price (if we were to assume that they not part of the consensus) by knowing the dealer’s inventory.  

# The Copeland and Galai Options Model  

Copeland and Galai (1983)  reasoned that a bid provides prospective sellers a put on the asset, with the exercise price of the put equal to the bid. For as long as the bid is quoted, other traders (at least the first to exercise) have the right to sell the asset at the quoted price. Similarly, an offer provides a call to other traders. Thus, when the dealer posts both bid and offer quotes, the spread is, in effect, a short  strangle  provided to the market. Increases in underlying asset risk increase both the values of call options and the values of put options. Both legs of this strangle are more valuable when the risk of the underlying security is higher. The value of this short strangle is directly related to the volatility of the asset and inversely related to how quickly it can be revoked or revised.  
An options pricing model can be used to value this dealer spread. When the dealer posts quotes, she provides other traders free long and short positions on short-term calls and puts. Thus, dealer posting of quotes is a costly activity. Essentially, a dealer can value each leg of the short strangle as individual options, and add the two to value the short strangle position associated with her quotes. The dealer will then widen the spread to capture this lost value. Ultimately, this “implied premium” associated with this dealer spread is paid by liquidity (uninformed, as in Glosten and Milgrom) traders who trade without information. Informed traders make money at the expense of the dealer, who ultimately earns it back at the expense of uninformed traders. Unlike some of the other models we discussed, the Copeland and Galai model, as presented here, does not have a mechanism to allow trading activity to convey information from informed traders to dealers and uninformed traders. Nonetheless, in the Copeland and Galai option-based model, the spread widens as the uncertainty with respect to the security price increases. Thus, in all three of our spread-based models, Copeland and Galai, Stoll, and Glosten and Milgrom, we see that greater uncertainty increases dealer spreads.  

# Additional Reading  

Chapters 10 to 12 in  Harris (2003)  offer good introductions to several models presented in this chapter, and O’Hara (1998)  offers a somewhat more rigorous introduction.  Stoll (2003)  and  Madhavan (2000)  provide excellent reviews of relevant literature as of their publication dates and all four offer broader discussions of market microstructure and related literature.  Vayanos and Wang (2013)  provide good discussions of both theoretical and empirical issues concerning market liquidity.  Amihud et al. (2005)  provide a slightly more technical discussion of liquidity and its effects on security prices.  

# References  

Amihud, Y., & Mendelson, H. (1986). Asset pricing and the bid-ask spread.  Journal of Financial Economics ,  17 , 223 ' 249. Amihud, Y., Mendelson, H., & Pedersen, L. H. (2005). Liquidity and asset prices.  Foundations and Trends in Finance ,  1 (4), 269 ' 364. Bagehot, W. (1971). The only game in town.  Financial Analysts Journal ,  27 (12 ' 14), 22. Barber, B., Lee, Y. T., Liu, Y. J., & Odean, T. (2009). Just how much do investors lose from trade?  Review of Financial Studies ,  22 , 151 ' 186. Barber, B., & Odean, T. (2000). Trading is hazardous to your wealth: The common stock investment performance of individual investors.  Journal of Finance ,  55 , 773 ' 806. Barber, B., & Odean, T. (2001). Boys will be boys: Gender, over confidence, and common stock investment. Quarterly Journal of Economics ,  116 (1), 261 ' 292. Barber, B., & Odean, T. (2002). On-line investors: Do the slow die first?  Review of Financial Studies ,  15 (2), 455 ' 487. Barclay, M. J., & Warner, J. B. (1993). Stealth and volatility: Which trades move prices?  Journal of Financial Economics ,  34 , 281 ' 306. Black, F. (1986). Noise.  Journal of Finance ,  41 (3), 529 ' 543. Boland n azar, M., Jackson, R., Jiang, W., & Mitts, J. (2020). Trading against the random expiration of private information: A natural experiment.  Journal of Finance ,  75 (1), 5 ' 44. Brennan, M. l, Chordia, T., Sub rahman yam, A., & Tong, T. (2012). Sell-order liquidity and the cross-section of expected stock returns.  Journal of Financial Economics ,  105 , 523 ' 541. Brennan, M., & Sub rahman yam, A. (1996). Market micro structure and asset pricing: On the compensation for illiquidity in stock returns.  Journal of Financial Economics ,  41 , 441 ' 464.  
Chan, J., Hong, D., & Sub rahman yam, M. (2008). A tale of two prices: Liquidity and asset prices in multiple markets.  Journal of Banking and Finance ,  32 (6), 947 ' 960. Chaplinsky, S., & Ramchand, L. (2004). The borrowing costs of international issuers: SEC Rule 144A.  The Journal of Business ,  77 , 1073 ' 1097. Copeland, T. C., & Galai, D. (1983). Information effects of the bid-ask spread.  Journal of Finance ,  38 , 1457 ' 1469. Demsetz, H. (1968). The cost of transacting.  Quarterly Journal of Economics ,  82 , 33 ' 53. Easley, D., & O’Hara, M. (1987). Price, trade size, and information in securities markets.  Journal of Financial Economics ,  19 , 69 ' 90. Easley, D., & O’Hara, M. (1992). Time and the process of security price adjustment.  Journal of Finance ,  47 , 576'605.Fama, E. (1965). The behavior of stock market prices.  Journal of Business ,  38 , 34 ' 105. Figlewski, S. (1979). Market “efficiency” in a market with heterogeneous information.  Journal of Political Economy , 86 , 581 ' 597. Friedman, M. (1953). The case for flexible exchange rates. In M. Friedman (Ed.),  Essays in positive economics . Chicago: University of Chicago Press. Glosten, L. R., & Milgrom, P. R. (1985). Bid, ask and transactions prices in a specialist market with heterogeneously informed traders.  Journal of Financial Economics ,  14 (1), 71 ' 100. Harris, L. (2003).  Trading and exchanges: Market micro structure for practitioners . Oxford: Oxford University Press. Koudijs, P. (2015). Those who know most: Insider trading in 18th century Amsterdam.  The Journal of Political Economy ,  123 , 1356 ' 1409. Kyle, A. S. (1985). Continuous auctions of insider trading.  Econometric a ,  53 (6), 1315 ' 1336. Madhavan, A. (2000). Market micro structure: A survey.  Journal of Financial Markets ,  3 , 205 ' 258. O’Hara, M. (1998).  Market micro structure theory . New York: Blackwell Publishers. Rock, K. (1986). Why are new issues under priced?  Journal of Financial Economics ,  15 , 187 ' 212. Stoll, H. R. (1978). The supply of dealer services in securities markets.  Journal of Finance ,  33 , 1133 ' 1151. Stoll, H. R. (2003). Market micro structure. In G. M. Constantini des, M. Harris, & R. Stulz (Eds.),  Handbook of the economics of finance 1A  (pp. 553 ' 604). Amsterdam: Elsevier Science. Vayanos, D., & Wang J. (2013). Market liquidity: Theory and empirical evidence. In G. M. Constantini des, M. Harris, & R. Stulz (Eds.),  Handbook of the economics of finance 2B  (pp. 1289 ' 1361). Amsterdam: Elsevier Science.  

Zarinelli, E., Treccani, M., Farmer, J. D., & Lillo, F. (December 2015). Beyond the square root: evidence for logarithmic dependence of market impact on size and participation rate.  Market Micro structure and Liquidity ,  1 (2), 1137 ' 1156.  

# 6.7 EXERCISES  

1.  Consider a stock that is traded 4 times per year with an average spread of  $1\%$   and paying annual dividends equal to  $\S2$  , discounted at   $3\%$  . a.  Based on the  $1\%$   spread and annual turnover equal to 4, what is the value of the stock? b.  What would be your answer to part a if the spread were  $0.5\%$  ? c.  What would be your answer to part b if the annual turnover were 2? d.  What is the expected return for the stock in part c? e.  What are the current bid/ask prices given the scenario in part c? Assume that the stock’s value is midway between the bid and ask prices and round to the nearest  $\S0.001$  .  

2.  Members of tribal fishing societies often undertake efforts to share information on where the fish are biting. Modern fishermen often purchase information identifying locations of schools of fish obtained from remote sensing satellite data. However, this information is often kept secret. Why do members of tribal societies share this information and modern fishermen opt not to share?  
3.  The model of demand in the  Kyle (1985)  assumes that perfectly informed trader demand    $x$   increases linearly in his expected value of the traded stock. This assumption is important to Kyle’s results. Demonstrate that perfectly informed trader demand    $x$   in the Kyle model increases linearly in the difference between his expected value of the traded stock and the price  $p$   set by the dealer. (This difference,    $v-p_{0},$   is the profit per share to the informed trader.)  

4.  An informed trader has private information that the value of a stock is  $\S100$   per share. Without this information, the variance of payoffs on the stock would be   $\S60_{.}$  ; this is the level of payoff uncertainty faced by uninformed investors. The variance associated with uninformed investor trades is10,000 shares.  

a.  If the value of the stock were to be  $\S100$   without the private information, what would be the level of informed trader demand for the stock? b.  If the value of the stock were to be  $\S90$   without the private information, what would be the level of informed trader demand for the stock? c.  What will be the informed trader’s expected profits from purchasing the number of shares computed in part b? d.  Suppose that actual uninformed demand for the stock were zero. Based on your computations from part  $\mathsf{b}_{,}$  , at what level would the dealer set the stock price?  

5.  We saw in Chapter 4 that in a statistical study of stock market data,  Barclay and Warner (1993)  found that very small trades and the very large trades did not have a significant impact on stock prices. They found that medium-sized trades had the greatest impact on the security process.  

a.  Describe how this empirical finding might be consistent with the theoretical results of  Kyle (1985) . b.  Describe how this empirical finding might be inconsistent with the theoretical results of  Kyle (1985) . c.  Financial blogging has substantially increased the flow of information to investors who would otherwise be uninformed, decreasing investor a symmetries. Would related improvements in the flow of information tend to increase or decrease Kyle’s lambda?  

6.  In the  Glosten and Milgrom (1985)  model, dealer spreads will tend to be smaller when arrivals of buy and sell orders are balanced. Why do such balanced order arrivals tend to produce smaller dealer spreads?  

7. a.  In the Glosten and Milgrom Information Asymmetry Model, are dealer spreads greater if all traders (excluding the dealer) are fully informed and know what prices will be or if all traders are uninformed and trade on noise? Why? b.  How is price uncertainty reflected in the Glosten and Milgrom model?  

8.  Based on his estimates of the risk of a security, a trader believes that the price of a stock traded in a dealer market will fall within a   $\S3$   range, with potential prices being uniformly distributed. The trader knows that there are a substantial number of informed traders trading this stock, and that these informed traders will know with certainty the value of the stock. The dealer’s bid ' offer quotations are 12.9 and 14.1, respectively. Based on these quotes provided by the dealer, what is the probability that the trader will estimate that any given trade will have originated with an informed trader?  
9.  Suppose that a dealer with   $\mathbb{S20,000}$   in capital and zero stock inventory has a logarithmic utility of wealth function:  $\mathbf{U}=\ln(W)$  . a.  Assuming a small risk (the Arrow-Pratt model, as used by  Stoll, 1978 ), what would be his Coefficient of Absolute Risk Aversion (ARA)? b.  Uncertainty, as measured by the price variance on a given stock is 10,000. The consensus price of this stock is 100. What are the bid price and bid discount for this stock? What are the ask price and ask premium for this stock? What is the spread for this stock? c.  Now, suppose that the dealer maintains an inventory of shares of this stock so that the covariance between profits on the stock and this optimal initial inventory is  $E[r_{P}\times r_{p}W_{p}]=\sigma_{i,P}=1000$  . Calculate the bid discount and price for the stock under this revised circumstance. d.  What is the dealer spread for part c?  

10.  Describe how transaction costs will tend to increase inverse correlations between trade-to-trade transaction prices.  

11.  Suppose that dealer inventory costs were the sole source of the dealer spread. Further suppose that a transaction was executed at the bid. Would subsequent bid and offer quotes tend to be higher or lower? Why? Now, suppose that a transaction was executed at the offer. Would subsequent bid and offer quotes tend to be higher or lower? Why? In either scenario, would transaction prices tend to exhibit positive, negative, or zero auto correlation? Why?  

12.  This exercise is related to a trading practice called  quote matching  (see Section 13.4 or Glossary), which occurs when a small trader places an order one uptick (downtick) from that of a large trader so as to profit from the large trader’s transaction upward (downward) price pressure, or to use the large trader as a trade counter party should prices decrease (increase). Suppose that Stock X has just sold for  $\S10.05$  . An institutional investor places a limit order to purchase 1 million shares at  $\S10.00,$  , which is now the best bid. The best offer is currently  $\mathbb{S}10.10$  . A trader, who reasons that the stock is equally likely to have an intrinsic value (true worth) of either  $\S10.00$   or   $\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \$   $(E[V]=\S10.05)$  ), places a limit order to buy 200,000 shares of the stock for   $\S10.01$  . a.  Describe how the trader is attempting to exploit the options provided by the spread. b.  How might the institutional investor be losing wealth as a result of his limit order?  

13.  Based on models described in this chapter, why does the dealer spread widen as the uncertainty associated with the relevant security increases?  

14. a.  Suppose that stock price changes in a given market from transaction to transaction are clearly and statistically inversely correlated, bouncing between prices in a definable range. Is it more likely that transaction prices are influenced by asymmetric information availability, random arrival of information, or frictions such as transactions costs? b.  Suppose that stock price changes in a given market from transaction to transaction are clearly uncorrelated, randomly fluctuating over time. Is it more likely that transaction prices are governed by asymmetric information availability, random arrival of information (that is, perfectly or nearly perfectly efficient markets), or  
frictions such as transactions costs? c.  Suppose that stock price changes in a given market from transaction to transaction are clearly and statistically positively correlated and are more likely to move in a given direction displaying momentum. Is it more likely that transaction prices are governed by asymmetric information availability, random arrival of information, or frictions such as transactions costs?  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0752a4bff9cb81f778544dc66c19e1a8f4b4e22904ea1b36f04e941f838067a6.jpg)  

# 6. A.1 THE KYLE ADVERSE SELECTION MODEL  

This appendix provides for a somewhat more technical introduction to the Kyle (1985) model than is offered in Section 6.4.  

Consider a one-time-period single auction model involving an asset that will pay in one time period    $v\!\sim\!N(p_{0};\,\Sigma_{0})$   that is, the asset’s future liquidation payoff    $v$   is normally distributed with mean value    $p_{0}$   and variance    $\Sigma_{0}$  . Thus,  $p_{0}$   is the unconditional expected value of the asset. Variance,    $\Sigma_{0},$   can be interpreted to be the amount of uncertainty that the informed trader’s perfect information resolves, so that    $\Sigma_{0}$   reflects the informed trader’s value advantage. There are three trader types—a single informed trader with perfect information, on the asset payoff many uninformed noise traders, and a single dealer or market maker who sets the market price of the asset and acts as an intermediary in all trades. All are risk neutral, there is no spread, and money has no time value. Market makers and noise traders seek to learn from the actions of the informed trader, who seeks to disguise himself and his special information in a batch market (markets accumulate orders before the dealer clears them). Thus, the informed trader seeks to determine    $x,$   an appropriate share purchase (sale) volume that maximizes his trading profits based on his superior information:    $\scriptstyle{\pi=E[(v-p)x|v]}$   where  $p$   is the market price of the asset. That is, the informe trader seeks to maximize his expected trading profits given his perfect knowledge of  v and the price  $p$   that he pays (or receives) for    $x$   shares of the stock. The market maker will observe total share purchases    $X{=}x{+}u$  , where    $u$   reflects noise trader transactions, increasing  $X$  the price of shares    $p$   as    increases. The market maker cannot distinguish between informed trader demand    $x$   and noise trader demand  $u,$  , but does correctly observe total demand  X . Nonetheless,  $X$   will be correlated with  $x,$   hence, the informed trader needs to exercise care in deciding on his transactions volume    $x$   to protect himself from price slippage (see Chapter 4). Thus, neither the dealer nor the noise traders will know which trades or traders are informed, but they seek to discern informed demand  $x$   from the noisy signal X  representing total demand.  

Noise traders submit market orders for    $u$   shares randomly, such that their orders contain no useful information content. In fact, noise trader activity will obscure information provided by the informed trader, which enables informed traders to disguise the information content of their trading from the dealer. Noise traders will demand    $u$   shares, where  $u$  is distributed normally with mean    $E[u]{=}0$   (they are as likely to sell as to buy) and variance  $\sigma_{u}^{2}:u\!\sim\!N(0;\sigma_{u}^{2})$  ð Þ . Thus,    $\sigma_{u}^{2}$    is the variance of uninformed investor demand. Informed traders do not know how many shares uninformed traders will buy or sell, but the informed trader does know the parameters of the distribution of the demand. Informed and noise traders submit their order quantities    $x$   and  $u$   to the market maker in a batch market. The  $X$  market maker observes the net market imbalance (the extent to which  is positive or negative), and sets the price  $p$   at which the total order flow    $\scriptstyle{X=x+u}$   is executed and clears. Thus, the market maker observes    $X,$   and then sets the price as a function of the sum of informed and uninformed investor demand:  $p{=}E\ [v|x{+}u]$  .  
# THE INFORMED TRADER’S PROBLEM: PROFIT MAXIMIZATION  

Kyle’s Bayesian learning model shows that informed investor demand    $x$   can be expressed as a simple linear function of  v:  $\cdot\ x{=}\alpha{+}\beta v,$   where    $\alpha$   and    $\beta$   are simple coefficients whose traits will be discerned and examined shortly. Similarly, the security’s price    $p,$  , set by the market maker or dealer, is assumed to be a simple linear function of demand:  $p{=}\mu$   $+\lambda(x{+}u)_{.}$  , where    $\mu$   and    $\lambda$   are also simple coefficients whose traits will also be examined shortly. Thus, informed investor demand    $x$   is a linear function of true security value    $v$   and the security price    $p$   is a linear function of the sum of informed and uninformed investor demand    $\scriptstyle X=(x+u)$  .  

The informed trader’s primary problem is to determine the optimal purchase (or sale) quantity  $x$   so as to maximize the expected value of his trading profits:  

  
$$
m a x_{x}E[\pi]=E[(v-p)x\big|v]=E[(v-\mu-\lambda(x+u))x\big|v]=E[v x-\mu x-\lambda x^{2}-\lambda u x)]
$$  

To maximize the informed trader’s profits, find the derivative of expected trading profits  $E[\pi]$   with respect to informed investor demand    $x$   and set equal to zero:  

$$
\frac{\partial E[\pi]}{\partial x}=v-\mu-2\lambda x-\lambda u=0
$$  

Also recall that that the distribution of    $u$   implies that  $E[u]{=}0$   since uninformed investors randomly buy and sell. Next, note that    $\lambda,$   known as Kyle’s lambda, must be positive for the second-order condition (the second derivative must be negative   $(\r-2\lambda\!<\!0)$  ) to hold for maximization. We will demonstrate this later. Finally, we rearrange terms to obtain:  

$$
2\lambda x=v-\mu
$$  

$$
x={}-\frac{\mu}{2\lambda}{}+\frac{1}{2\lambda}v
$$  

which is linear in  $v$   as Kyle proposed it would be. Now, we see that our coefficients    $\alpha$   and  $\beta$   are simply:  

$$
\alpha={}-\frac{\mu}{2\lambda},~~~~\beta=\frac{1}{2\lambda}
$$  

the dealer pricing function. Thus, the informed trader linear demand function    $\begin{array}{r}{x=\alpha+\beta v=\textrm{--}\frac{\mu}{2\lambda}+\frac{v}{2\lambda}}\end{array}$      is set based on  
# DEALER PRICE SETTING  

But, to gain insight into what the informed trader linear demand function implies, we need to better understand our coefficients    $\alpha$   and  $\beta$  . To explore this, we will examine the trading of the dealer or market maker who observes total order flow    $\scriptstyle{X=x+u},$  , and sets a single market clearing price  $p$   or    $E[v]$   as a function of total demand    $\scriptstyle{p=E[v|x+u]}$   where    ${x}{=}{\alpha}{+}{\beta}v$  . N te he that the dealer increases the price of the security as total demand  $x{+}u$   increases. Since  v  and  X 6 are normally distributed, we will apply the projection theorem to  $p$   as follows :  

$$
p=E[v]+\left[\frac{\mathrm{COV}[v,x+u]}{\mathrm{VAR}[x+u]}\right]\!\left[x+u-E[x+u]\right]
$$  

This dealer pricing function has a straightforward interpretation. First, the sensitivity of the dealer price to total share demand  $x{+}u$   is a function of the covariance between the stock’s value and total demand for the shares   $\operatorname{COV}[v,\ x+u]$  . Thus, if the dealer believes that total demand  $x{+}u$   for the stock increases dramatically with its intrinsic value  $v$   (unknown to him), the price that the dealer sets for shares will be very sensitive to total demand. Thus, if the informed trader is known to dominate trading in the marketplace, the dealer will set the price of the security mostly or entirely as a function of total demand for the security. This sensitivity to total demand will diminish as uninformed demand volatility increases. As total demand deviates more from expected demand, the price of shares will increase.  

# INFORMED TRADER DEMAND AND DEALER PRICE ADJUSTMENT  

Since    $\scriptstyle{x=\alpha+\beta v,}$   and    $\Sigma_{0}$   is the variance of or uncertainty associated with asset payoffs    $v,$  d trader demand   $\operatorname{VAR}[x]$   will equal    $\beta^{2}{\sum}_{0}$  . Since noise trader demand is uncorrelated to informed trader demand, this means that

  $\begin{array}{r}{\mathrm{VAR}[x+u]=\beta^{2}\sum_{0}+\sigma_{u}^{2},}\end{array}$  ½  þ ' ¼ P   þ , which means that we can write the dealer pricing equation as:  

$$
p=E[v]+\left[\frac{\mathrm{COV}[v,x+u]}{\beta^{2}\Sigma_{0}+\sigma_{u}^{2}}\right][x+u-\alpha-\beta E[v]]
$$  

Now, recall that    $\beta$   is the slope of a line plotting a random dependent variable    $X$   or   $(x$   $+u)$   with respect to an independent random variable    $v$  . That is,    $\beta{=}\mathrm{FOV}[v,\ x{+}u]/\mathrm{VAR}[v]$   $\,=\!\!\operatorname{COV}[v,\,x\!+\!u]/\Sigma_{0},$   which means that   $\scriptstyle{\mathrm{COV}}[v,\,x+u]=\beta\Sigma_{0},$   and we can write this equation as:  

$$
p=E[v]+\left[\frac{\beta\sum_{0}}{\beta^{2}\sum_{0}+\sigma_{u}^{2}}\right][x+u-\alpha-\beta E[v]]
$$  

6 The projection theorem has many applications in finance, such as to the Capital Asset Pricing Model (CAPM) and Arbitrage Pricing Theory (APT). Many students are first exposed to it in econometrics when seeking an unbiased estimator in an econometrics setting. Generally, the projection theorem states that the relationship between some random dependent variable  $y$   and an independent random variable  $x$   is  
$$
y=E[y]+\left[\frac{\mathrm{COV}[y,x]}{\mathrm{VAR}[x]}\right]\left[x-E[x]\right]
$$  

Recall that Kyle suggested a linear relationship between the security price and its demand:  $p{=}\mu{+}\lambda(x{+}u)$  . This implies a slope    $\lambda$   equal to:  

$$
\lambda=\left[\frac{\beta\sum_{0}}{\beta^{2}\sum_{0}+\sigma_{u}^{2}}\right]
$$  

which implies    $\scriptstyle\mu=p+\lambda(\,-\,x\,-\,u)$   and  

$$
\mu=E[v]+\lambda[-\alpha-\beta E[v]]
$$  

Next, we will use    $\alpha$   and    $\beta$   coefficients from above to demonstrate that    $\scriptstyle{\mu=E[v]}$  :  

$$
\mu=E[v]+\lambda\bigg[\frac{\mu}{2\lambda}-\frac{1}{2\lambda}E[v]\bigg]=E[v]+\bigg[\frac{\mu}{2}-\frac{1}{2}E[v]\bigg]=\frac{1}{2}E[v]+\frac{\mu}{2}=E[v]
$$  

Now, we will rewrite    $\lambda,$   substituting in for    $\beta$  :  

$$
\lambda=\left[\frac{\beta\!\sum_{0}}{\beta^{2}\!\sum_{0}+\sigma_{u}^{2}}\right]=\left[\frac{\displaystyle\frac{1}{2\lambda}\!\sum_{0}}{\left(\displaystyle\frac{1}{2\lambda}\right)^{2}\!\sum_{0}+\sigma_{u}^{2}}\right]
$$  

We will use a bit of algebra to simplify this expression for    $\lambda,$   starting by multiplying    $\lambda$  and the right-hand side of  Equation (6.A.11)  by the denominator of the right-hand side of the equation:  

$$
\lambda{\left[{\left(\frac{1}{2\lambda}\right)}^{2}{\sum}_{0}+\sigma_{u}^{2}\right]}=\frac{1}{2\lambda}{\sum}_{0}
$$  

$\lambda$  Next, we will simplify the left-hand side and then multiply both sides by  and simplify further by subtracting  $\frac{1}{4}\sum_{i}$  P   from both sides:  

$$
\begin{array}{r l}&{\left[\left(\cfrac{1}{4\lambda}\right)\sum_{0}+\lambda\sigma_{u}^{2}\right]=\cfrac{1}{2\lambda}\sum_{0}}\\ &{~~~~\left(\cfrac{1}{4}\right)\sum_{0}+\lambda^{2}\sigma_{u}^{2}=\cfrac{1}{2}\sum_{0}}\\ &{~~~~~~\lambda^{2}\sigma_{u}^{2}=\cfrac{1}{4}\sum_{0}}\\ &{~~~~\lambda=\sqrt{\cfrac{1}{4}\sum_{0}}=\cfrac{1}{2}\sqrt{\cfrac{\sum_{0}}{\sigma_{u}^{2}}}}\end{array}
$$  

First, we see that it is obvious that    $\lambda$   is positive and that our second-order condition for profit maximization has been fulfilled. More importantly,    $\lambda$   can be taken to be the dealer price adjustment for total stock demand; that is,    $\lambda$   can be considered to be the il liquidity adjustment . The ratio  $\textstyle\sum_{0}/{\sigma_{u}^{2}}$    is the ratio of informed trader private information resolution to the level of noise trading. Thus, dealer price adjustment is proportional to the square root of this ratio, increasing as private information    $\Sigma_{0}$   is increasing and decreasing as noise trading    $\sigma_{u}^{2}$    increases. This means that if the dealer determines that the informed trader resolves a substantial level of risk relative to the amount of noise trading, the level of    $\lambda$  dealer price adjustment  will be large. Now, we can write our informed investor demand coefficients    $\alpha$   and  $\beta$   as follows:  
$$
\alpha=\mathrm{}-\frac{E[v]}{\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}},\,\,\,\,\,\,\,\beta=\frac{1}{\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}}
$$  

Now, we can more easily interpret our informed trader demand function:  

$$
x=\alpha+\beta v=\mathrm{}-\frac{E[v]}{\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}}+\frac{v}{\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}}=\frac{(v-E[v])\sigma_{u}}{\sqrt{\sum_{0}}}
$$  

This result indicates that informed trader transaction sizes will increase as the variance of uninformed noise demand for shares    $\sigma_{u}^{2}$    increases. That is, the informed trader will trade more aggressively as noise trader volume increases. This volatility reflects noise trader demand for (or supply of) shares. Thus, informed traders will want to take larger positions in the stock or sell off more shares as uninformed trader uncertainty increases and their transaction volume increases. This increased noise volume will better enable informed traders to camouflage their information advantage over the dealer. Also note that, even with perfect information and risk neutrality, informed traders will limit their trading activity to camouflage their intentions. In fact, as the informed trader advantage  $\Sigma_{0}$   over the market maker increases, informed trader demand for share volume will decline. That is, as the informed trader’s information improves relative to the dealer, the informed trader will seek to camouflage his advantage by reducing his trade volume. This is intended to prevent the dealer from observing the increased trade volume or imbalance on buy (sell) transactions and raising the share price to balance the orders. Here, the informed trader will earn his profits by maintaining more profit on a per share basis rather than on transaction volume.  

Recall from  Equation (6.A.7)  that the market maker sets the price at  $p,$   which we will rewrite using the result of  Equation (6.A.16) :  

$$
p=E[v]+\left[\frac{\beta\sum_{0}}{\beta^{2}\sum_{0}+\sigma_{u}^{2}}\right][x+u-\alpha-\beta E[v]]=E\big[v\big|x+u\big].
$$  

$$
p=\mu+\lambda(x+u)=E[v]+\frac{1}{2}\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}(x+u)
$$  
First, note that the dealer price    $p$   is the security’s expected value    $E[v]$   conditioned on total demand   $[x{+}u]$   for the security. We see here that the dealer price is linear in total demand for the security and linear in the ratio of informed trader value uncertainty to uninformed or noise trader uncertainty. Higher noise or uninformed trader uncertainty reduces the security price unless total demand   $(x{+}u)$   is negative. The opposite is true for value or cash flow uncertainty, which increases the informed trader’s informational advantage. The market maker sets the price at    $p,$   such that the informed trader buys (sells) whenever    $v>E[v]$     $(v<E[v])$  , and buys (sells) more aggressively as this difference increases. Note that some of these implications might be clarified with the following 7 informed trader profit function :  

$$
]=E[[v-E[v]]x]=E\left[[v-E[v]]\left[\frac{v}{\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}}-\frac{E[v]}{\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}}\right]\right]=\frac{\sum_{0}}{\sqrt{\frac{\sum_{0}}{\sigma_{u}^{2}}}}=\sqrt{\sum_{0}\sigma_{u}^{2}}=\sqrt{\sum_{0}\sigma_{u}^{2}}\mathrm{~,~}
$$  

(6.A.20)  

We see here that expected informed trader profits are linear and increasing in the quality of their information advantage  $\sqrt{\sum_{0}}$  p P and the demand uncertainty    $\sigma_{u}$   of noise traders. A larger value    $\Sigma_{0}$   implies a greater deviation in the security value    $v$   (known by the informed trader) from its expected value    $E[v]$   (estimated by the dealer). A larger value for  $\Sigma_{0}$   implies a larger information advantage to the informed trader. Greater dealer price uncertainty (which arises from the combination of uninformed demand variability and value uncertainty) increases informed trader trading profits. Increased uninformed trader uncertainty and its associated increase in transactions    $\sigma_{u}$   mean that the informed trader is better able to disguise from the market maker his information advantage  $\Sigma_{0}$   and trading activity through the increased noise trader volume    $\sigma_{u}$  . This ability to camouflage means that the informed trader can trade more aggressively, taking larger positions   $(x\ \mathrm{or}\ -x)$  and profits in the stock without accurately revealing his transactions to the market maker. While the market maker does observe order imbalances    $X,$   he cannot distinguish between informed trader demand  $x$   and noise trader demand    $u$  . The market maker responds by setting a competitive price    $p$   such that informed traders earn their profits indirectly from noise traders. The market maker loses on trades with informed traders and earns profits on trades with noise traders. The market maker merely earns a competitive profit as long as informed traders successfully camouflage their intentions at the ultimate expense of noise traders.  Kyle (1985)  continues his model in a multi period framework to demonstrate that analogous implications arise in sequential and continuous auctions.  
