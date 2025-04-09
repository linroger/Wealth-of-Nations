# 19.5 CAPITAL STRUCTURE ARBITRAGE  

# 19.5.1 EXAMPLES OF CAPITAL STRUCTURE ARBITRAGE TRADES  

Capital structure arbitrage is a class of strategies used by market participants such as credit hedge funds and certain banks. The basic idea behind the strategy is to go long one security in a company's capital structure while at the same time going short another security in the same company's capital structure. Examples of capital structure arbitrage trades include  

1. Long the stock of company ABC and short the bonds of company ABC".   
2. Long equity of a company ABC and short the CDS on the debt issued by ABC".   
3. "Go long subordinated debt and short senior bonds"..  

How could a structural model of default be used to provide a decision rule for the implementa-. tion of the trade in (1)? One could use a Merton-type model to calculate the implied credit spreac and probability of default based on company ABC's stock price. Call this spread sMerion, implied  

If company ABC has publicly traded bonds one can use bond prices to calculate the bond implied credit spread SBond, implied.  

If SMerton, implied $<s_{B o n d} $ implied, then $\varepsilon=s_{B o n d,i m p l i e d}-s_{M e r t o n,i m p l i e d}>0.$ Assume one takes the view that the equity market correctly prices the default risk while the bond market overestimates the risk. Furthermore, if one believes that the two markets should converge in their assessment of the default risk, then one could take a long bond and a short stock position. Implicit in this approach is the view that the pricing error $\varepsilon$ declines (to 0) over time.  

The signal for such trades can be the discrepancy between the Merton model implied bond spread derived from equity prices and the CDS spread..  

The example in (2) above is based on a comparison of equity and CDS implied information and not equity and bond implied information as in the example in (1). As described in the previous chapter, CDS markets can be used to calculate a CDS implied credit spread scos, implied for company ABC. Consider the scenario where sMerton, implied $>s_{C D S}$ implied. Now consider the case where a market participant believes that the CDS market is pricing the credit risk correctly while the equity market is not. One way to express this view is through a long position in the stocks of ABC while buying a CDS of company ABC. If, over time, the equity and the CDS market converge in their assessment of the credit risk, this position would make a profit..  

The following reading illustrates that such strategies can be applied not just to individual com-. panies but also to indices. In the example, the CDS market is seen to have interpreted the macroeconomic environment differently from the equity market.  

# EXAMPLE  

JP Morgan Chase and Morgan Stanley's CDS index for Europe, Trac-x Europe, narrowed from 140 basis.   
points in October 2002 to 105 bp during the war, while the Dow Jones Eurostoxx 50, which was at 2,275 in early October 2002, reached a low of 1,928 in March. The apparent discrepancy was largely due to the fact.   
that a lot of European companies were reducing their debt levels at this time [...]. The credit market took.   
the view that corporate debt reduction was a stronger indicator of company performance than the negative.   
macroeconomic indicators that were pummelling stock levels.  

(Risk Magazine, November 1, 2003, Barra joins crowded market for Merton models', www.risk.net/1497515)  

The above reading illustrates that the narrowing of CDS spreads from 140 to 105 bp reflected a view in the CDS market that credit risk diminished as European companies reduced debt levels. Since equity holders are residual claimants to the assets of the company, such an interpretation should coincide with a rise in equity prices if the equity market agreed with the CDS market. But as the example illustrates the two markets disagreed in this case and the equity market actually fell from 2275 to 1928.  

# 19.5.2 USING THE MERTON MODEL TO PROVIDE SIGNALS FOR CAPITAL STRUCTURE ARBITRAGE TRADES  

The above examples illustrated the basic idea behind capital structure arbitrage trades. We now want to look in more detail at how the Merton model can be used to provide signals for such.  

trades. Equation (19.23) above shows how we can back out implied credit spreads from observed share prices. For a given company, which we call XYZ, we could plot the Merton model implied credit spreads for a range of different share prices. Figure 19.4a shows such a relationship.11 The axes in the figure correspond to those from the output of the basic Merton model. We see that a share price of around. $\$30$ implies a credit spread of. $5\%$ for XYZ. The relationship is downward sloping since a share price increase implies a lower probability of default and thus a lower credit spread. Conversely, if share prices decrease the probability of default increases.  

Now imagine that for company XYZ we gather credit spreads from bond prices of CDS markets. For simplicity we assume that the data are from bond markets, but an analogous argument could be made if the data were from CDS markets. If we used CDS market data, any potential position to exploit the mispricing would involve buying or selling CDS, while below we explain how one can go long or short bonds to exploit the mispricing.  

We superimpose these observed spreads on the relationship in Figure 19.4a. The result is shown in Figure 19.4b. The circles represent different hypothetical market observations. As the figure shows, the fit is quite good. Assume that on a given trading day a market participant plots the figure and observes share prices of around. $\$25$ and a credit spread of around $10\%$ $(1000\mathrm{bp})$ as indicated by point $P$ and the horizontal line passing through $P$ . What would be the theoretical credit spread implied by the Merton model for a share price of. $\$23?$ Figure $19.4\mathrm{b}$ suggests that the Merton model would imply a credit spread closer to. $5\%$ $(500~\mathrm{bp})$ if the share price is $\$25$ This is illustrated by point $P^{\star}$ and the dashed red line. Does this mean that the debt is overvalued. or undervalued relative to the equity? How could one exploit any potential mispricing?.  

First we note that according to Figure 19.4b, point $P$ corresponds to an observation that lies above the line indicating the theoretical relationship. This implies that the actual spread of. 1000 bp (point $P$ ) is higher than the theoretical spread of $500\mathrm{bp}$ (point $P$ ). The actual spread can be interpreted as being too high. If the actual spread is derived from bond data, this means. that bonds are too cheap. If the spread is from CDS prices it means the CDS spread is too high relative to the model. From the perspective of the equity value, we observe that the actual share price is $\$25$ , whereas the Merton model would predict that the share price should be closer to $\$14$ if the credit spread was $1000\mathrm{bp}$ , which is illustrated by the dashed black line. From this perspective, the equity is overvalued. This example shows that the Merton model can be used. to identify relative mispricing. To exploit the relative mispricing it is not enough to only take one position in bonds, CDS, or equities, respectively. A long position in bonds and a short position in stocks would allow exploiting a potential correction in the relative mispricing between the bonds and equities of company XYZ. Therefore to exploit the observed mispricing we would go short XYZ equity and go long XYZ bonds in the hope that stock prices will fall and bond yields fall as predicted by the Merton model. The following example illustrates however that capital structure arbitrage trades can also lose money even if it is based on long/short. positions:  

# EXAMPLE  

A number of capital structure arbitrageurs were caught out when stock levels plummeted in the run-up to the war in Iraq-the Dow Jones Eurostoxx 50, which was at 2,275 in early October 2002, reached a low of 1,928 in March. But credit default swap (CDS) spreads remained relatively tight, rather than widening as a Merton model-based credit system would predict. The Trac-x Europe CDS index narrowed from 140 basis points in October to 105 bp during the war.  

(Risk Magazine, November 1, 2003, 'Barra joins crowded market for Merton models', www.risk.net/1497515/)  

The above example is an illustration of the use of CDS instead of bond positions together with stock positions. Arbitrageurs were long equities and sustained losses as the index fell from 2275 to 1928. They are referred to as having been short credit, which typically means long the CDS or buying protection. Thus, as credit spread's tightened they would have suffered mark-to-market losses on the CDS position. The reason for these market moves was that the credit market believed that the ongoing corporate deleveraging was a more important determinant of company performance than the macroeconomic factors related to the war. The result was that arbitrageurs that were short credit and long equities suffered losses.  

We can generalize the above conclusions and state that the capital structure arbitrage strategy and the decision which security to go long or short depends on which side of the line representing the theoretical relationship between the actual credit spread and share price observation falls. This is shown in Figure 19.4c.  

How can we calculate the appropriate hedge ratio for the arbitrage strategy? We can derive the. delta theoretically from the delta of equity with respect to the firm's asset value $A_{t}$ From Eq. (19.15) we know that  

$$
{\frac{\mathrm{d}E_{t}}{\mathrm{d}A_{t}}}=N(d_{1})
$$  

and  

$$
{\frac{\mathrm{d}D_{t}}{\mathrm{d}E_{t}}}={\frac{\mathrm{d}(A_{t}-E_{t})}{\mathrm{d}E_{t}}}={\frac{\mathrm{d}A_{t}}{\mathrm{d}E_{t}}}-1={\frac{1}{N(d_{1})}}-1.
$$  

The hedge ratio $\mathrm{d}D_{t}/\mathrm{d}E_{t}$ allows us to calculate how many shares to go short (or long) for each. bond bought (or sold). Our discussion so far has been framed in terms of the relative pricing of equity and bonds. If instead of bond prices the actual credit spreads were derived from CDS prices, then to exploit the mispricing one would instead of going long bonds (in the hope that bond prices would rise and spreads would tighten) one would sell a CDS..  

# 19.5.3 SOURCE OF PROFITS FROM CAPITAL  

Figure 19.4 illustrated a decision rule based on the Merton model that can be used to exploit any potential mispricing between bonds (or CDS) and equity. Now we want to examine the main  

![](images/6b40a68632a364589e59a62b687851e05c581fa77973c0c0b23ae2586ea3cb53.jpg)  
(a) lustrative example of relationship between credit spread and share price  

![](images/a94928a097d087ed023d5d76b291f1f4e745f262056f07fb9e39c365c212eef5.jpg)  
(c) Indictator for capital structure arbitrage strategy and decision to go long or short  

# FIGURE 19.4  

Credit spread versus share price.  

sources of profit for the capital arbitrage strategy discussed above. It turns out that the profits can be viewed either from (a) the perspective of bond/CDS and equity prices correcting or (b) a more. advanced perspective of volatility arbitrage.  

# 19.5.3.1 Capital structure arbitrage as a mispricing of bonds (or CDS) and equity  

Let's examine (a) first. To exploit the apparent arbitrage represented by point $P$ we noted that a short stock and long bond position is optimal. Such a position will benefit if either the share price increases or the bond price rises (that is credit spreads tighten) or both occur simultaneously. There are however also other scenarios when the strategy will be profitable, for example, when the share price rises, but losses on the short stock position are outweighed by gains from the long bond position if credit spreads tighten to a sufficient extent.  

We can distinguish three potential areas in the credit spread--share price space to discuss whether. the strategy (ii) will make money, (ii) will lose money, or (ili) will break even. Figure 19.5 illustrates the three areas. The starting point is a delta-hedged position at point $P$ . The position consists of a. long bond and short stock position. As the arrow which points towards the south-west indicates any. move from point $P$ towards the theoretical credit spread--share price relationship represents a correction of the apparent mispricing at point $P$ and would make money for the strategy. A share price/ spread move toward the north-east would on the other hand lead to losses. There is a third area however represented by the line that passes through point $P$ . This line can be interpreted as a break-even area. Point $P$ represents a delta-hedged position and any move in the credit spreads along the line. corresponds to a movement as the Merton model would indicate $i f$ the current share price/spreads. observation at point $P$ was correct, that is if there was no mispricing.  

# 19.5.3.2 Capital structure arbitrage from the perspective of mispriced volatility  

As discussed, there is a second perspective (b) which interprets mispricing as mispricing of volatility rather than spreads and share prices. In our discussion of the application of the Merton model in Section 19.4.4, we showed how one can back out a credit spread from observed equity prices and volatility. This approach could be presented by the following relationship which suggests that using variables such as the equity value and volatility we can obtain the Merton model implied credit spread:  

$$
E_{t},\sigma_{E},F,r,\sigma_{A},T-t\xrightarrow[\mathrm{Merton-Model}]{}R-r_{\mathrm{Merton}}
$$  

The alternative route is to start with actual credit spreads and then back out the implied equity volatility  

$$
(R-r)_{\mathrm{actual}},E_{t},F,r,\sigma_{A},T-t\xrightarrow[\mathrm{Merton-Model}]{}\sigma_{E}^{\mathrm{actual}}
$$  

The procedure in Eq. (19.28) illustrates the use of theoretical/Merton model spreads. Figure $19.5\mathrm{b}$ shows the lines that represent that theoretical spread-share price relationship for different volatilities. For example, at point $P^{\prime}$ if we plug in a share price of around $\$25$ we obtain a credit spread of $5\%$ if we use an implied equity volatility of. $\sigma_{E}^{\mathrm{{Merton}}}$  

What would happen if we used the procedure in Eq. (19.29) and, together with the other parameters, plugged the share price of $\$25$ and the observed credit spread of $10\%$ corresponding to point $\mathrm{\bfP}$ into the Merton formula to obtain an implied equity volatility? In this case, we would. obtain an equity volatility of $\sigma_{E}^{\mathrm{actual}}$  

(a) llustrative example of relationship between credit spread and share price  

![](images/0a719da94c102a1be55ea6235693d0813a8ab6de1b8792f8e4c519fc3eef9200.jpg)  

# FIGURE 19.5  

Capital structure arbitrage profits.  

Since the Merton model is based on the Black--Scholes formula, it is clear that to obtain a higher credit spread at the same stock price level of $\$25$ one would need to use a higher implied volatility. Therefore, the volatility backed out using the combination of a. $\$25$ share price and $5\%$ credit spread must be lower than the volatility obtained using a. $\$25$ share price and $10\%$ credit spread. $\sigma_{E}^{\mathrm{Merton}}<\sigma_{E}^{\mathrm{actual}}$ In other words. the actual bond (or Ds) spreads beig to high (compared to the Merton model implied ones for the same stock price) can be also interpreted as the bond (or CDS). spread implied equity volatility being high relative to what could be referred to as the true volatility. The profits from the strategy that is long XYZ bonds and short XYZ stocks can be reinterpreted as a.  

result. The strategy will make money if the implied equity volatility corrects (that is decreases), that is by moves towards the theoreicl credit spread- share relationship based on volatility $\sigma_{E}^{\mathrm{{Merton}}}$  

What could be a source of the "true' equity market volatility be in the comparison above? How can we get an estimate of the input parameter $\sigma_{E}$ One potential source is equity option implied volatility. The following reading illustrates the use of the implied equity volatility perspective on. capital structure arbitrage in practice. The reading refers to an asset manager that takes CDS prices and extracts from them an implied equity volatility which is then compared to the implied volatility. in the equity options market. The equity volatilities also provide the sensitivities for the delta hedging.  

# EXAMPLE  

On September 10, the CDS spread on Sun was around 70 bp above LIBOR. "This gives us a kind of implied   
equity volatility-when we use our capital structure model-of something like 45-50 volatility [basis]   
points, " $I...J$ The Axa team then compared this value with the implied volatility value on Sun in the equity options.   
market. On that day, the implied volatility of 3-month at-the-money options on Sun was around 65 bp. The   
15-20 bp difference was the arbitrage opportunity. To monetise this, Axa bought CDS protection on Sun   
while buying Sun stock to delta hedge the position. To work out the implied equity volatilities, $I...J$ Axa relies on a proprietary equity-based firm-value   
model based on Merton theory [...] (Risk Magazine, October 1, 2003, Capital structure builds a following', www.risk.net/1526277)  

The Merton model was used in the example to back out $\sigma_{E}^{\mathrm{actual}}$ as in Eq. (19.29). The observed CDS spread in the market implied an equity volatility of. $45\mathrm{-}50~\mathrm{bp}$ , which was lower than the. equity option market implied volatility of 65 bp. It seems that the traders took the view that the equity option volatility was more correct. This view was expressed by buying CDS protection and hedging by buying stock. If the credit spread in the CDS market widens the protection buyer would make mark-to-market gains. If the spread tightens the long stock position would hopefully provide a hedge given the negative empirical relationship between the two..  
