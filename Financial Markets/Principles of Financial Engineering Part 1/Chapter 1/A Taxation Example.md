---
tags:
  - capital_gains
  - financial_engineering
  - synthetic_instruments
  - taxation
  - wash_sale
aliases:
  - Tax Example
  - Taxation
  - Wash Sale
key_concepts:
  - capital gain realization
  - financial engineering perspective
  - legal and regulatory issues
  - synthetic instrument creation
  - taxable gains and losses
---

# 1.3 A TAXATION EXAMPLE  

Now consider a totally different problem. We create synthetic instruments to restructure taxable gains. The legal environment surrounding taxation is a complex and ever-changing phenomenon; therefore, this example should be read only from a financial engineering perspective and not as a tax strategy. Yet the example illustrates the close connection between what a financial engineer does and the legal and regulatory issues that surround this activity.  

# 1.3.1 THE PROBLEM  

In taxation of financial gains and losses, there is a concept known as a wash-sale. Suppose that during the year 2014, an investor realizes some financial gains. Normally, these gains are taxable that year. But a variety of financial strategies can possibly be used to postpone taxation to the year after. To prevent such strategies, national tax authorities have a set of rules known as wash-sale and straddle rules. It is important that professionals working for national tax authorities in various countries understand these strategies well and have a good knowledge of financial engineering.. Otherwise some players may rearrange their portfolios, and this may lead to significant losses in. tax revenues. From our perspective, we are concerned with the methodology of constructing synthetic instruments.  

Suppose that in September 2014, an investor bought an asset at a price $S_{0}=\mathbb{S}100$ . In December 2014, this asset is sold at $S_{1}=\mathbb{S}150$ . Thus, the investor has realized a capital gain of. $\$50$ These cash flows are shown in Figure 1.9..  

One may propose the following solution. This investor is probably holding assets other than the. $S_{t}$ mentioned earlier. After all, the right way to invest is to have diversifiable portfolios. It is also reasonable to assume that if there were appreciating assets such as. $S_{t},$ there were also assets that lost value during the same period. Denote the price of such an asset by. $Z_{t}$ Let the purchase price be $Z_{0}$ . If there were no wash-sale rules, the following strategy could be put together to postpone year 2014 taxes.  

Sell the $Z\cdot$ asset on December 2014, at a price $Z_{1}$ $Z_{1}<Z_{0}$ , and, the next day, buy the same $Z_{t}$ at a similar price. The sale will result in a loss equal to  

$$
Z_{1}-Z_{0}<0
$$  

The subsequent purchase puts this asset back into the portfolio so that the diversified portfolio can be maintained. This way, the losses in $Z_{t}$ are recognized and will cancel out some or all of the capital gains earned from $S_{t}$ There may be several problems with this strategy, but one is fatal. Tax authorities would call this a wash-sale (i.e., a sale that is being intentionally used to "wash' the 2014 capital gains) and would disallow the deductions.17  

![](7bb6f274784579e67362ff990df7e4e21866b5478e7a95adbbc5065675a2b65c.jpg)  

# FIGURE 1.9  

An investment liquidated on December 2014.  

# 1.3.1.1 Another strategy  

Investors can find a way to sell the $Z$ -asset without having to sell it in the usual way. This can be done by first creating a synthetic $Z$ asset and then realizing the implicit capital losses using this synthetic, instead of the $Z$ -asset held in the portfolio.  

Suppose the investor originally purchased the $Z\cdot$ asset at a price. $Z_{0}=\$100$ and that asset is currently trading at. $Z_{1}=\$50$ , with a paper loss of $\$50$ . The investor would like to recognize the loss without directly selling this asset. At the same time, the investor would like to retain the original position in the. $Z$ -asset in order to maintain a well-balanced portfolio. How can the loss be realized while maintaining the $Z$ position and without selling the $Z_{t}^{\cdot}$  

The idea is to construct a proper synthetic. Consider the following sequence of operations:  

Buy another $Z$ asset at price. $Z_{1}=\$50$ on November 26, 2014.   
Sell an at-the-money call on $Z$ with expiration date December 30, 2014.   
Buy an at-the-money put on $Z$ with the same expiration.  

The specifics of call and put options will be discussed in later chapters. For those readers with no background in financial instruments we can add a few words. Briefly, options are instruments that give the purchaser a right. In the case of the call option, it is the right to purchase the underlying asset (here the Z-asset) at a prespecified price (here $\$50$ . The put option is the opposite. It is the right to sell the asset at a prespecified price (here $\$50$ ). When one sells options, on the other hand, the seller has the obligation to deliver or accept delivery of the underlying at a prespecified price.  

For our purposes, what is important is that short call and long put are two securities whose expi-. ration payoff, when added, will give the synthetic short position shown in Figure 1.10. By selling the call, the investor has the obligation to deliver the $Z$ -asset at a price of. $\$50$ if the call holder. demands it. The put, on the other hand, gives the investor the right to sell the. $Z$ -asset at $\$50$ if he or she chooses to do so..  

The important point here is this: When the short call and the long put positions shown in Figure 1.10 are added together, the result will be equivalent to a short position on stock $Z_{t}$ In fact, the investor has created a synthetic short position using options.  

Now consider what happens as time passes. If $Z_{t}$ appreciates by December 30, the call will be exercised. This is shown in Figure 1.11a. The call position will lose money, since the investor has to deliver, at a loss, the original $Z$ stock that cost $\$100$ . If, on the other hand, the $Z_{t}$ decreases, then. the put position will enable the investor to sell the original $Z$ stock at $\$50$ . This time the call will expire worthless.18 This situation is shown in Figure 1.11b. Again, there will be a loss of. $\$50$ Thus, no matter what happens to the price $Z_{t}$ either the investor will deliver the original $Z$ asset purchased at a price $\$100$ , or the put will be exercised and the investor will sell the original $Z$ -asset at $\$50$ . Thus, one way or another, the investor is using the original asset purchased at $\$100$ to close an option position at a loss. This means he or she will lose $\$50$ while keeping the same $Z$ position, since the second Z, purchased at $\$50$ , will still be in the portfolio.  

The timing issue is important here. For example, according to US tax legislation, wash-sale rules will apply if the investor has acquired or sold a substantially identical property within a.  

![](7e1abe0b2e9086bd808b38e659d452d8169daff684d5a7910ba252a44810b549.jpg)  

# FIGURE 1.10  

Two positions that cancel each other.  

31-day period. According to the strategy outlined here, the second. $Z$ is purchased on November 26, while the options expire on December 30. Thus, there are more than 31 days between the two operations.19  

# 1.3.2 IMPLICATIONS  

There are at least three interesting points to our discussion. First, the strategy offered to the investor was risk-free and had zero cost aside from commissions and fees. Whatever happens to the new long position in the $Z$ asset, it will be canceled by the synthetic short position. This situation is shown in the lower half of Figure 1.10. As this graph shows, the proposed solution has no market risk, but may have counterparty, or operational risks. The second point is that, once again, we have created a synthetic, and then used it in providing a solution to our problem. Finally, the example  

![](5da122eb8724b2aa524965b109dc80c52c2765fe023da83430eb2ed97a2b688e.jpg)  

# FIGURE 1.11  

The strategy with the. $Z$ initially at 50. Two ways to realize loss.  

displays the crucial role legal and regulatory frameworks can play in devising financial strategies. Although this book does not deal with these issues, it is important to understand the crucial role they play at almost every level of financial engineering..  
