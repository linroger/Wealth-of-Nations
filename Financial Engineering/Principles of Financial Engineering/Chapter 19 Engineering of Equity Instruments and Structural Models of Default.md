# ENGINEERING OF EQUITY INSTRUMENTS AND STRUCTURAL MODELS OF DEFAULT  

# 19  

# CHAPTER OUTLINE  

# 19.1 Introduction . 660  

19.2 What Is Equity?. . 662   
9.3 Equity as the Discounted Value of Future Cash Flows . 663   
9.4 Equity as an Option on the Assets of the Firm.. . 663   
19.4.1 Merton’s Structural Model of Default.. 663   
19.4.2 Payoffs to Bond and Equity Holders 664   
19.4.2.1 Payments to debt and equity holders under different scenarios... 666   
19.4.2.2 Bond and equity value in the Merton model .. 667   
19.4.3 Probability of Default.. 670   
19.4.4 Application of the Merton Model and Equity-to-Credit Approach . . 671   
19.4.5 Assumptions of the Merton Model and Extensions . . 672   
19.4.5.1 Extensions in published academic research .. 672   
19.4.5.2 Evolution of structural models of default in industry . 672  

# 9.5 Capital Structure Arbitrage . 673  

19.5.1 Examples of Capital Structure Arbitrage Trades .. . 673   
19.5.2 Using the Merton Model to Provide Signals for Capital Structure Arbitrage Trades ...... 674   
19.5.3 Source of Profits from Capital... . 676   
19.5.3.1 Capital structure arbitrage as a mispricing of bonds (or CDS) and equity.. . 678   
19.5.3.2 Capital structure arbitrage from the perspective of mispriced volatility . . 678  

# 19.6 Engineering Equity Products .. 680  

19.6.1 Purpose. 680   
19.6.2 Convertibles. 681   
19.6.3 Synthetic Convertible Bonds and Cash Flow Engineering. 683   
19.6.4 Real-World Example 685   
19.6.5 Convertible Bond Pricing.. 686   
19.6.5.1 Bond plus equity option approach.. 686   
19.6.5.2 Multifactor model 686   
19.6.6 Convertible Bond Arbitrage. 686   
19.6.7 Comparing the Role of Volatility in Convertible Bond Arbitrage and Capital Structure   
Arbitrage . 688   
19.6.8 Incorporating More Complex Structures . 688   
19.6.8.1 Exchange rate exposure.. 688   
19.6.8.2 Making the convertibles callable . 690   
19.6.8.3 Exchangeable bond . 690   
19.6.9 Using convertibles.. 690   
19.6.10 Warrants. 691   
19.7 Conclusions.. 692   
Suggested Reading . 692   
Exercises . . 693  

# 19.1 INTRODUCTION  

Fixed-income instruments involve payoffs that are, in general, known and “fixed.” They also have set maturity dates. Putting aside the credit quality of the instrument, fixed-income assets have relatively simple cash flows that depend on a known, small set of variables and, hence, risk factors. There are also well-established and quite accurate ways to calculate the relevant term structure. Finally, there are several liquid and efficient fixed-income derivatives markets such as swaps, forward rate agreements (FRAs), and futures, which simplify the replication and pricing problems existing in this sector.  

There is no such luxury in equity analysis. The underlying asset, which is often a stock or a stock index, does not have a set maturity date. It depends on a nontransparent, idiosyncratic set of risks, and the resulting cash flows are complex. The timing and the size of future cash flows may not be known. There are also complex issues of growth, investment, and management decisions that further complicate the replication and pricing of equity instruments. Finally, relatively few related derivatives markets are liquid and usable for a replication exercise.  

Yet, the general principles of option pricing and replication can be applied to value equity. In this chapter, we extend the methods introduced earlier to equity and equity-linked products. We also discuss the engineering applications of some products that are representative of this sector.  

First, we show how the equity of a company can be viewed and priced as an option on the assets of the firm with a strike price equal to the present value of the debt. This approach is based on the so-called Merton (1974) structural model of default. It is an elegant and useful application of financial engineering principles and importantly it allows us to link the pricing of credit and equity instruments. Similar to the Black Scholes model that we have used in earlier chapters to either price an option based on a given set of input parameters or to back out an implied volatility based on observed market price of the option, the Merton (1974) model can be applied in three main different ways. First, given information about a firm’s assets, its capital structure and debt value we can determine the model implied price of the equity. Second, in the equity-to-credit approach we can plug observed market prices of equity into the model to back out the implied credit spread and probability of default for the debt. The third application uses observed market prices for the equity and observed credit spreads (from bond or CDS markets) to back out an implied volatility for the equity.  

These wide-ranging uses have important practical uses. The following example highlights the practical relevance of structural models of default in today’s markets.  

# EXAMPLE  

$I...J$ leading investors say Merton models are now so frequently used that they are actually driving the credit market. Take Barclays Global Investors (BGI) in San Francisco, with $\$780$ billion under management. BGI has been using Merton models an in-house model as well as those available on the market for a number of years, but its head of US fixed income, Peter Wilson, says the model is now becoming so prevalent with other investors that it is starting to dictate which way credit markets will move.  

(Source: Risk Magazine, November 1, 2003, ‘Barra joins crowded market for Merton models’, www.risk.net/1497515/)  

As markets for credit derivatives developed and market prices for credit spreads became more widely available the Merton model became more widely used in the financial sector and many banks integrated their equity and fixed-income divisions to a greater extent and located them on the same trading floor. Previously equity and fixed-income divisions were often found on different trading floors. The underlying intellectual foundation for this reorganization lies in structural models of default. Furthermore, these models can be used for so-called capital structure arbitrage strategies. Such strategies use the Merton model to identify mispricing between credit and equity markets and take positions in equity, bond, or CDS markets to exploit it.  

Given the complexity of equity markets and their risks, as we will see, there are however also limitations associated with the basic Merton model and its applications.  

In the previous chapter, we had discussed credit risk, the probability of default of a risky bond, and credit default swaps. We had seen that credit spreads and therefore an implied probability of default can be backed out from both corporate bond spreads as well as CDS spreads. The Merton model provides us with a third source of information for the probability of default, since the model can be used to calculate it if the market value of equity and other parameters about the capital structure are observed.  

The simple Merton model has been extended significantly over the last 40 years and industry versions such as the KMV or the CreditGrades model are widely used. We discuss how hedge funds pursue so-called capital structure arbitrage strategies that are based on structural models of default.  

The second purpose of this chapter is to discuss the engineering of some popular equity instruments such as convertible bonds and hybrid equity products.  

The plan of this section is as follows. First, we discuss how financial engineering and option pricing principles can be applied to value a company’s equity. We discuss applications and limitations of the model. Second, we consider convertible bonds and their relative, warrant-linked bonds. Convertible bonds are another example of bonds with embedded options. In Chapter 17, we saw the first example of a bond with an embedded option in the form of callable bonds. In the next chapter, we will discuss structured products including equity structured products and so-called reverse convertibles.  

We begin by applying option replication and financial engineering principles to a company’s equity.  

# 19.2 WHAT IS EQUITY?  

Equity holders have a claim to the residual value of a company after creditors have been paid. The traditional approach to equity valuation is to view the price of equity as the present discounted value of future cash flows. This approach is covered in most standard corporate finance textbooks and, therefore, we will briefly summarize it without discussing it further.1 However, this approach, which discounts cash flows under the real-world probability measure and uses a risky discount rate, does not require any financial engineering. It turns out that there is also a second alternative perspective which views equity as an option on the assets of the firm and which can be used to calculate its value under the risk-neutral measure. The second interpretation is the one that represents an elegant application of financial engineering principles such as option replication and pricing that we discussed in previous chapters and therefore we focus on it in this chapter. From a practitioner perspective, there is another important reason why the option replication approach to equity valuation is a useful framework. The reason is that it creates a link between the value of equity and bonds and thus between equity and bond markets. In fact, with the existence of liquid credit derivative markets, it can even be used to connect equity, bond, and CDS markets. The reason for these linkages is that equity can be viewed as an option on the assets of the firm with a strike price equal to the present value of the debt. This leads to a closed-form expression that links equity and bond prices as well as equity prices and credit spreads. In this equity-to-credit approach, equity market values can be used to back out default probabilities of the debt.  

Bonds are contracts that promise the delivery of known cash flows, at known dates. Sometimes these cash flows are floating, but the dates are almost always known, and with floating rate instruments, pricing and risk management is less of an issue. Finally, the owner of a bond is a lender to the institution that issues the bond. This means a certain set of covenants would exist.  

Stocks, on the other hand, entitle the holder to some ownership of the company that issues the instrument.2 Thus, the position of the equity holder is similar to that of a partner of the company, benefiting directly from increasing profits and getting hurt by losses. One of the differences compared to a partnership is however that shareholders of public companies have limited liability.  

# 19.3 EQUITY AS THE DISCOUNTED VALUE OF FUTURE CASH FLOWS  

The traditional approach before option pricing models were developed was to view equity as the present discounted value of cash flows to equity holder. The stock or share prices corresponded to the equity value per share. These approaches postulate that expected future cash flows properly discounted should equal the current price $S_{t}.$ . Here it is important to note that the discount rate that is used to discount cash flows is risky and is used under the real-world probability measure. One variant of this approach is the Dividend Discount Model, for example, which takes dividends to be the cash flows that equity holds receive.  

The corporation has future dividends per share denoted by $D P S_{t},$ . We can buy one unit of $S_{t}$ to get the title for future dividends. We then use the real-world probability $P$ and the real-world discount rate $k_{t}$ that apply to the dollar dividends paid out by this company to write an equation that is similar to the representation for the coupon bond price:3  

$$
S_{t}=E_{t}^{P}\left[\sum_{i=1}^{\infty}\frac{D P S_{t+i}}{\prod_{j=1}^{i}(1+k_{t+j})}\right]
$$  

It is worth re-emphasizing that, in this expression, we are using the real-world probability. Thus, the relevant discount rate will differ from the risk-free rate:  

$$
k_{t}\neq r
$$  

How is $k_{t}$ obtained in practice? Various models such as the Capital Asset Pricing Model (CAPM), the Arbitrage Pricing Theory (APT), and others have been proposed. These models form the theoretical foundation for valuation and practitioners use different single or multifactor models to calculate the expected return and discount rate in practice.  

# 19.4 EQUITY AS AN OPTION ON THE ASSETS OF THE FIRM 19.4.1 MERTON’S STRUCTURAL MODEL OF DEFAULT  

In Chapter 9, we introduced the Black Scholes option pricing model to price an option on a stock. Can the option pricing approach also be used to price equity? It turns out that the answer is affirmative. Merton (1974) proposed a seminal structural model of default in which the equity of a firm is viewed as an option on the assets of the firm with a strike price equal to the (face) value of the debt. As the name indicates, the typical application of the model does not lie in the pricing of the equity, but rather in backing out information about the debt (including the default probability) from observed market prices for equity. As a result structural models of default have a large range of important practical applications including the modeling, pricing, and forecasting of default risk.4 The following example illustrates the practical relevance of the structural approach.  

# EXAMPLE  

The Tequila crisis, the Asian financial crisis, Brazil, Russia, Enron. . . it seems most large credit events are followed by critical post mortems on the effectiveness of credit rating agencies. Investors seeking better default indicators than produced by rating analysts have turned to a variety of sources, not least of which is the family of so-called Merton model tools, perhaps the most well known of which is KMV’s.  

(Risk Magazine, February 1, 2002, ‘Battle of the supermodels’, www.risk.net/1506552)  

The GFC provided further recent examples of corporate defaults that preceded downgrades by rating agencies. Merton-type models, of course, are not infallible and like all models they have their strengths and weaknesses. One application of structural models of default is in the form of so-called capital structure arbitrage. As we will see capital structure arbitrage consists of exploiting potential misvaluation between the debt and the equity issued by a given company.  

The Merton (1974) model is an excellent example of the financial engineering and option valuation concepts that we discussed in previous chapters. In the previous chapter, we discussed credit risk, the probability of default of a risky bond and credit default swaps. We saw that credit spreads and therefore an implied probability of default can be backed out from both corporate bond spreads as well as CDS spreads. The Merton model provides us with a third source of probability of default information. All three sources of default probabilities use market prices and therefore provide us with risk-neutral default probabilities. These probabilities can be used to calculate expected cash flows in a risk-neutral world with credit risk. We saw in Chapter 12 that according to the fundamental theorem of asset pricing, a derivative’s price is the discounted expected value of the future payoff under the risk-neutral measure. Since structural models of default tie together the values of bond and equity markets they allow financial engineers and market participants to exploit potential arbitrage and relative value opportunities between equity, bond, and CDS markets. We will discuss examples of such arbitrage strategies below.  

The Merton model has spawned a large literature that has extended the basic model in many different directions.5 We will first describe the basic model and then discuss applications before pointing to recent extensions. Since it is the simplest case, we review the Merton model in the context of the valuation of a risky zero-coupon bond, but Merton (1974) also considered the cases of coupon-bearing and callable debt.  

# 19.4.2 PAYOFFS TO BOND AND EQUITY HOLDERS  

A standard company balance sheet is a summary of the financial position of a company at a given point in time and consists of three main parts: assets, liabilities, and equity. Equity holders therefore have a residual claim on the firm after creditors have been paid. Figure 19.1a illustrates a stylized balance sheet. The stock market allows us to observe the market value of equity. Therefore the balance sheet in the figure can be interpreted as reflecting market as opposed to book values of assets, debt, and equity. For (medium and large) companies that publicly issue bonds we can observe market values for the debt in the form of bond prices.6  

a Firm's balance sheet (market values (b) Payments to debt and equity holders under different scenarios cPayoff profile of debt and equity positions  

<html><body><table><tr><td>Assets</td><td>Liabilities</td><td></td></tr><tr><td rowspan="2"></td><td>Debt</td><td rowspan="2">Use tradedbond and equityvalues ifavailable</td></tr><tr><td>Equity</td></tr></table></body></html>  

<html><body><table><tr><td></td><td>Scenario1: A>F T</td><td>Scenario2: A<F T</td></tr><tr><td>Debtholders</td><td>F</td><td>A T</td></tr><tr><td>Equityholders</td><td>A_-F T</td><td>0</td></tr></table></body></html>  

![](e03b3222fbd24e7ba8c5a2645bc7e1c2836ac12c1019b17a1f0f471290bbcd2a.jpg)  
d) Decomposition of payoff to debt holders into short put option position  

<html><body><table><tr><td rowspan="5">Portfolio</td><td></td><td>Scenario 1: A>F T</td><td>Scenario2: A<F</td></tr><tr><td>Debt holders</td><td>F</td><td></td></tr><tr><td>Risklessdebt</td><td>F</td><td>F</td></tr><tr><td>-putoption</td><td>0</td><td>-(A-F）</td></tr></table></body></html>  

# FIGURE 19.1  

Equity as option on firm’s assets.  

# 19.4.2.1 Payments to debt and equity holders under different scenarios  

Consider a firm that has only issued two types of securities: equity and zero-coupon bonds, that is the debt. How can we apply option valuation techniques to the equity of such a firm that issues only one type of debt in the form of a zero-coupon bond with face value $F?$ The value of the firm at date $t$ is equal to the (market) value of the firm’s assets and therefore we denote it by $A_{t}$ . Let’s first consider the relationship between the value of the firm, denoted by $A_{t}$ , the value of the equity $E_{t},$ and the value of the debt $D_{t}$ . Debt holders are promised a payment of $F$ at maturity date $T.$ . Now, consider two possible scenarios:  

1. $A_{T}>F$ : If $A_{T}$ , the assets of the firm at maturity $T$ exceed the promised value of the payment to bond holders $F_{\mathrm{\bullet}}$ , then equity holders will be paid the residual amount $A_{T}{-}F$ and the equity is worth $E_{T}=A_{T}-F$ . In this scenario, there is no default.   
2. $\ensuremath{\boldsymbol{A}}_{T}<\ensuremath{\boldsymbol{F}}$ : If $A_{T}$ , the assets of the firm at maturity $T$ are below the amount promised to debt holders, the firm defaults. In this case, there is no residual amount remaining for equity holders and the equity is worth zero $E_{T}.$ The equity holders have limited liability and as a result their claim cannot be worth less than zero. These two scenarios are illustrated in Figure 19.1b.  

We can plot the payoffs to equity, $E_{T}$ , and the payoff to bond holders, $D_{T}$ against the value of the firm’s asset at maturity $T,A_{T}.$ . This is represented by the dashed lines in Figure 19.1c. As we can observe the payoff profile of equity resembles that of a call option on the assets of the firm, $\quad A_{T}.$ The figure also indicates the limited liability feature. It implies that equity holders can walk away from the firm’s debt in exchange for a payoff of zero. The strike price is the face value of the zero-coupon debt. The payoff profile for the bond or debt holders, in contrast is reminiscent of a short put position. Since before maturity at date $t<T$ the options also have time value, the curved black lines plot the value of the equity and the debt at dates before maturity. The value of the equity and debt has some time value before maturity. The black lines represent the value of equity $E_{t}$ and debt $D_{t}$ before maturity.  

Figure 19.1c illustrates the basic intuition for why in the Merton model, the equity is priced as a European call option on the firm’s assets while the bond holders’ claim is equivalent to risk-free debt in addition to a short put position. The payoff of the creditors at date $T$ can be written as:  

$$
D(A_{T},T)=\operatorname*{min}(A_{T},F)=F-\left(F-A_{T}\right)^{+}.
$$  

This is illustrated in Figure 19.1d. The decomposition of the payoff to the bond holders shows that the bond holders are short a put option written on the assets of the borrowing firm with a strike price equal to the face value of the debt $F$ . The put option implicit in the creditor payoff is sometimes referred to as a default or credit put.  

We can also apply the put call parity relationship, introduced in Chapter 11, to derive the value of the firm and the value of risky debt. Remember that the put call parity relationship states that a portfolio of a call minus a put is equal to the value of a portfolio containing the underlying minus a riskless bond.  

$$
C_{t}-P_{t}=S_{t}-e^{-r(T-t)}K
$$  

In the context of the Merton model the underlying assets $(S_{t})$ are the firm’s assets, that is $S_{t}=A_{t}$ . The face value of the bond is $F$ , that is $K=F$ , so that the put call parity relationship becomes  

$$
C_{t}-P_{t}=S_{t}-e^{-r(T-t)}K=A_{t}-{\mathrm{Riskless~Bond}}(t)
$$  

![](72c31cd623c1d2b19424447da2f09cac3060d7eebcf2c25fee92f1519074e565.jpg)  

# FIGURE 19.2  

Distribution of firm value in Merton model.  

Equation (19.5) can be rewritten in terms of the assets $A_{t}$ of the firm as follows:  

$$
A_{t}=\operatorname{Riskless}\operatorname{Bond}(t)+C_{t}-P_{t}
$$  

We also know that the value of the assets equals the (risky) debt plus the equity:  

$$
A_{t}=E_{t}+D_{t}
$$  

Since the underlying assets in Eq. (19.6) are the assets of the firm, we can set Eqs. (19.6) and (19.7) equal to each other to get  

$$
{\mathrm{Riskless~Bond}}(t)+C_{t}-P_{t}=E_{t}+D_{t}
$$  

Now we note that equity in the Merton model is a call option on the assets of the firm ( $\begin{array}{r}{C_{t}=E_{t},}\end{array}$ so that we can write Eq. (19.8) as follows:  

$$
{\mathrm{Riskless~Bond}}(t)+E_{t}-P_{t}=E_{t}+D_{t}
$$  

and therefore we subtract $C_{t}$ from both sides to get  

$$
{\mathrm{Riskless~Bond}}(t)-P_{t}=D_{t}
$$  

This leads to the following contractual equation:  

![](a351a05bab2781eb2cf4cf5e99bce6f1c66bb78fd1c91ee1056dad9a1430737f.jpg)  

# 19.4.2.2 Bond and equity value in the Merton model  

One of the convenient results of the Merton model and subsequent papers using this methodology is that closed-form solutions for the value of debt and equity can be obtained. To do so, we need to make an assumption about the evolution of the firm’s assets over time and its relationship to the firm’s liabilities. Figure 19.2 illustrates one such possible path followed by the firm’s assets $A_{t}$ over time.  

The dashed blue line represents the path of the firm’s expected asset value over time. The curve at time $T$ represents the probability distribution of $A_{t}$ at time $T.$ The distribution illustrates the fact that there is uncertainty about the evolution of $A_{t}$ . The Merton model makes specific distributional assumptions about the evolution of assets over time.7 The face value of the debt is represented by $F$ . Default occurs if the assets $A_{T}$ at time $T$ fall below the face amount of the debt $F_{\mathrm{\bullet}}$ . The difference between $E(A_{T})$ and $F$ is called distance to default $(D D)$ . We assume that the value of the assets of the firm $A_{t}$ follows a geometric Brownian motion.  

$$
\mathrm{d}A_{t}=A_{t}(\mu\mathrm{d}t+\sigma\mathrm{d}W_{t})
$$  

where $\sigma$ is the asset volatility, $\mu$ is the expected continuously compounded return on $A_{t}$ , and $W_{t}$ represents a geometric Brownian motion. The basic model makes several restrictive assumptions which we discuss later and which have been relaxed by subsequent research. Here we highlight one of the assumptions that is implicit in our discussion above, namely that default can only occur at date $T$ and there are no distress costs associated with default, which implies that bond holders receive $A_{T}$ in case of default. This assumption allows us to model the option feature as a European option with maturity date $T.$  

As we saw in Figure 19.1c, the firm’s equity value at time $T$ is given by  

$$
E_{T}=\operatorname*{max}(A_{T}-F,0)
$$  

We can apply the Black Scholes European call option pricing formula8 to derive the value of the firm’s equity at date $t.$ If we make the assumption that one can trade the firm’s assets $A_{t}$ then, from Chapter 12, we know that $e^{-r t}A_{t}$ is a martingale under the risk-neutral measure $\tilde{P}$ which leads to the following:  

$$
E_{t}=E^{\tilde{P}}[e^{-r(T-t)}(A_{T}-F)^{+}]=B S\mathrm{Call}(A_{t},F,r,\sigma,T-t)
$$  

The Black Scholes formula for a European call is  

$$
E_{t}=A_{t}N(d_{1})-F e^{-r(T-t)}N(d_{2})
$$  

where  

$$
d_{1}=\frac{l n(A_{t}/F)+(r+(1/2)\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}
$$  

and  

$$
d_{2}=d_{1}-\sigma\sqrt{T-t}
$$  

The value of the debt at date $t$ is  

$$
D_{t}=A_{t}N(-d_{1})+e^{-r(T-t)}F N(d_{2})
$$  

An important insight from the Merton model is that the spread between the risky debt and the risk-free debt is the value of the put option. Credit spreads are therefore a function of the input  

parameters of the model such as the maturity of the debt, the leverage, the strike price of the put, and the business risk of the firm.  

Let the yield on a riskless bond be represented by $r.$ . Furthermore, if we denote the yield on a risky zero-coupon bond by $R$ , then the price of a risky bond at date $t$ as a function of the yield and the face value is  

$$
D_{t}=e^{-R(T-t)}F
$$  

After taking logs and solving for $R$ , the yield $R$ can be written as  

$$
R=-\left({\frac{1}{T-t}}\right)l n\left({\frac{D_{t}}{F}}\right)
$$  

We can plug the expression for $D_{t}$ from Eq. (19.16) into Eq. (19.18) to obtain the yield $R$ of a risky bond:  

$$
\begin{array}{l}{{R=-\displaystyle\frac{1}{T-t}l n\Big[\displaystyle\frac{A_{t}N(-d_{1})+e^{-r(T-t)}F N(d_{2})}{F}\Big]}}\\ {{=-\displaystyle\frac{1}{T-t}l n\Big[e^{-r(T-t)}\left(\displaystyle\frac{A_{t}}{e^{-r(T-t)}F}N(-d_{1})+N(d_{2})\right)\Big]}}\\ {{=-\displaystyle\frac{1}{T-t}\Big\{-r(T-t)+l n\Big[\left(\displaystyle\frac{1}{L}N(-d_{1})+N(d_{2})\right)\Big]\Big\}}}\\ {{=r-\displaystyle\frac{1}{T-t}\left(l n\Big[\left(\displaystyle\frac{1}{L}N(-d_{1})+N(d_{2})\right)\Big]\right)}}\end{array}
$$  

where $L=e^{-r(T-t)}F/A_{t}$ is a measure of leverage. We can rewrite Eq. (19.22) in terms of the credit spread $R-r$ :  

$$
R-r=-{\frac{1}{T-t}}\left(l n\left[\left({\frac{1}{L}}N(-d_{1})+N(d_{2})\right)\right]\right)
$$  

The expression in Eq. (19.23) is important and useful since it shows us how based on the input parameters one can calculate the implied credit spread from the Merton model. This equity implied credit spread can be compared to credit spreads from bond or CDS prices. The Merton model implies that as share prices increase, the credit spread decreases. Do we observe such a negative relationship in practice? Figure 19.3 provides an illustrative example. It plots the credit default spread for Goldman Sachs against the Goldman Sachs share price over the period $2007{-}2014$ on a weekly basis. It is clear that the relationship is negative as predicted by the Merton model. This example does, of course, not represent proof of the practical usefulness of the Merton model in explaining credit spreads. Recent comprehensive academic studies find some support for the Merton model and for its input parameters being able to explain credit spreads, but these studies also suggest that factors outside the Merton model are important for the determination of credit spreads.  

It is a priori not clear which financial market should price credit risk correctly, but a market participant can take the view that either the equity, the bond, or the CDS market prices credit risk correctly and then take long and short positions in two of these markets to try to exploit potential relative mispricing. We will describe the underlying rationale and examples of such trades in detail in one of the subsequent sections.  

![](8de64489bd05ec170604dd7d5f2a694bbf60e47c35a57e84a362bb1444d489b4.jpg)  
Goldman Sachs CDS versus share price (2007–2014, weekly frequency)  

# FIGURE 19.3  

Goldman Sachs CDS versus share price (2007 2014).  

# 19.4.3 PROBABILITY OF DEFAULT  

One of the uses of Merton models in practice is as an indicator of default risk. The Merton model can be used to calculate the option implied risk-neutral probability of default, that is the risk-neutral probability that $A_{T}<F$ . The risk-neutral probability of default is the probability that the put finishes in-the-money. The probability of default can be calculated as follows:  

$$
{\mathrm{Probability~of~Default}}=P(A_{T}<F)=N(-d_{2})
$$  

In the risk-neutral world, the drift of the firm value process is the risk-free rate $r.$ . Note that under the stochastic process in Eq. (19.12) for $A_{t}$ the real-world probability of default is the probability that $A_{T}<F$ given that $A_{t}$ has a drift $\mu$ and a volatility $\sigma$ . The drifts $\mu$ and $r$ may be different. Therefore, the risk-neutral probability of default in Eq. (19.24) may differ from the actual probability of default. On the one hand, if $\mu>r$ , the firm value in the real world drifts upwards faster than in the risk-neutral world, which implies that the real-world probability of default would be lower than the risk-neutral probability. On the other hand, if $\mu<r$ , the real-world probability of default would be higher than the risk-neutral probability of default. It is possible to derive closed-form solutions for the actual probability of default from the risk-neutral probability. Typically $\mu>r$ and therefore the real-world probability is below the risk-neutral probability. We can interpret the higher risk-neutral probability as consisting of the real-world probability plus a risk premium for uncertainty regarding the timing and magnitude of default. Note that in the basic Merton model, there is no uncertainty considering the timing which is not realistic.  

The following example illustrates the application of the Merton model.  

# EXAMPLE  

We assume that the value and volatility of assets is given and our objective is to calculate the current market value of equity and debt as well as the implied credit spread and default probability. Table 19.1 shows the input parameters.  

<html><body><table><tr><td colspan="2">Table 19.1 Input Parameters for Merton Model Example</td></tr><tr><td>Parameter</td><td>Value</td></tr><tr><td>Asset/firm value (At)</td><td>100</td></tr><tr><td>Face value of the debt (F)</td><td>75</td></tr><tr><td>Maturity (T)</td><td>1</td></tr><tr><td>(Riskless) interest rate (r)</td><td>2%</td></tr><tr><td>Asset volatility (o)</td><td>20%</td></tr></table></body></html>  

If we apply Eq. (19.15) to calculate the price of the equity $E_{O}$ at date $t=0$ we obtain a value of $E_{O}=26.84\$ . Similarly, according to Eq. (19.16) the market value of debt is 73.16. The implied yield to maturity of the risky debt based on Eq. (19.18) is $2.49\%$ and the resulting credit spread is 49. The value of the riskless debt is 73.51 and the difference between the value of the riskless debt and the risk debt is the value of put, which is 0.36. The default probability is given by Eq. (19.24) and is equal to $3.46\%$ in this example.9  

# 19.4.4 APPLICATION OF THE MERTON MODEL AND EQUITY-TO-CREDIT APPROACH  

As Eq. (19.15) shows, structural models such as the Merton model are based on the unobserved variable $A_{t}$ . For publicly traded companies, the share price and therefore the equity value is observable in the market. The usual approach to estimating the value of the firm’s assets $A_{t}$ and their volatility $\sigma_{A}$ is to use Eq. (19.13) together with another equation that links the value and volatility of equity to the value and volatility of assets. If we apply Itoˆ’s formula to Eq. (19.15), we obtain:  

$$
E_{t}\sigma_{E}=A_{t}\sigma_{A}{\frac{\partial E}{\partial A}}=N(d_{1})\sigma_{V}V_{t}
$$  

Equations (19.15) and (19.25) represent a pair of simultaneous equations that can be solved for $A_{t}$ and $\sigma_{A}$ . Once we calculate $A_{t}$ and $\sigma_{A}$ it is also possible to calculate the probability of default $N(-d_{2})$ based on Eq. (19.24). We can also obtain the market value of the debt which is equal to $A_{t}-E_{t}$ . By comparing the current model implied market value to the present value of the promised debt payment, we can calculate the expected loss (EL). The end of chapter exercises provide a numerical example of an application of this approach.  

One of the first firms to use Merton-type models in practice to estimate probabilities of default of a debt issuer from share price data and the firm’s capital structure data was KMV (now Moody’s  

KMV) in the 1980s. This approach is sometimes also referred to as equity-to-credit and its advantage over credit ratings is that it is based on real-time data from liquid markets. This makes it particularly useful for predicting defaults. Default probabilities derived from credit ratings issued by credit rating agencies on the other hand are updated relatively infrequently and there are many examples when large publicly listed companies were only downgraded by credit rating agencies after the companies had filed for bankruptcy and defaulted on their debt. Default probabilities can also be obtained from other sources. Four other potential sources of such information are (i) credit ratings, (ii) historical default rates, (iii) credit spreads implied by publicly traded bonds, and (iv) credit spreads implied by CDS. Merton-type models should therefore be viewed as complementing rather than replacing other models and approaches when investment decisions are taken. Although Merton-type models are popular in credit markets, market participants still continue to use other fundamental and quantitative tools instead of purely relying on the outputs of structural models. Sometimes structural models are viewed as useful for understanding the sources of risk, while other classes of models can be useful for predicting market values of bonds and equities. Merton-type models are used by many institutional asset managers to understand how, for example corporate bonds will perform, in different asset volatility scenarios. However, ultimately decisions are made by taking into account information from all models.  

# 19.4.5 ASSUMPTIONS OF THE MERTON MODEL AND EXTENSIONS  

The basic Merton model that we reviewed above has been extended significantly by both practitioners and academics over the last 40 years. Many of the more recent and advanced structural models implemented in practice are proprietary and there is no public information about their underlying assumptions. Published academic research has, however, also developed more complex structural models of default that fit the stylized empirical facts better than the basic model.  

# 19.4.5.1 Extensions in published academic research  

As part of the introduction of the basic Merton model, we mentioned a range of simplifying assumptions that the basic model is based on. For reasons of space, the list of assumptions provided above is incomplete. Sundaresan (2013) provides a comprehensive review of the basic Merton model, its assumptions and how subsequent structural models of default have relaxed these assumptions to fit stylized empirical facts better. One of the assumptions that is used in almost all papers in this literature is that trading in assets takes place continuously. Clearly this is an unrealistic assumption for all firms and all assets. While some very liquid exchange traded assets can be viewed to a first-order approximation as exhibiting continuous trading, the physical assets of many firms are very illiquid and no market may exist for some of them. In fact, the value of the firm’s assets and its parameters are not even directly observable. The extensions that have been incorporated in richer, more complex structural models of default include (a) agency costs, (b) moral hazard, (c) bankruptcy codes, (d) renegotiations, (e) investments, (f) taxes, (g) jumps in the stochastic process followed by firm value, and (h) the dependence of default probabilities on the business cycle.  

# 19.4.5.2 Evolution of structural models of default in industry  

Although the details of models used by practitioners are not known, some published accounts indicate that several of the extensions such as (a) (h) mentioned in the previous section have been incorporated into such models. Even the original KMV model developed in the 1980s contained some significant differences compared to the basic Merton model since it scaled the distance to default obtained from the basic Merton model to actual default probabilities using a proprietary default database.10 Many software vendors, banks, and other private sector institutions developed their own Merton-type models. While the focus of early versions of the KMV model was on default probabilities, the development of credit derivatives markets in the 1990s led the industry to develop structural models of default to estimate bond and CDS spreads. One such example was CreditGrades launched by the Riskmetrics group (now part of MSCI) in 2002. The original CreditGrades model was based on the Black Cox model, which relaxes some of the assumptions of the basic Merton model to allow default to occur prior to time $T$ if the value of the firm’s assets hit a predetermined default barrier. Models such as CreditGrades can generate theoretical (model-implied) CDS spreads and various Greeks. In practice, to produce realistic credit spreads and default probabilities, contemporary models have been extended to include such variables as convertible debt, preferred equity, and so on. One of the challenges of applying standard Merton-type models is that the capital structure of a company can suddenly change. It may be possible to use the model to state whether the equity is correctly priced relative to the credit for the current capital structure but it is almost impossible to reliably forecast how the capital structure will change in the future. For example, it is very difficult to predict when the capital structure will change due to a management decision. Consider the situation of a capital structure arbitrage fund that has a long credit position and a short equity position on the company. What would happen if the company unexpectedly carries out a leveraged buyout? The likely result is that the position will lose money as a result. Some arbitrageurs trade equity and credit to express a view about expected future changes in a company’s capital structure.  

The paragraph above discusses the usefulness of Merton-type models for capital structure arbitrage strategies. We will introduce these strategies in the following section.  

# 19.5 CAPITAL STRUCTURE ARBITRAGE  

# 19.5.1 EXAMPLES OF CAPITAL STRUCTURE ARBITRAGE TRADES  

Capital structure arbitrage is a class of strategies used by market participants such as credit hedge funds and certain banks. The basic idea behind the strategy is to go long one security in a company’s capital structure while at the same time going short another security in the same company’s capital structure. Examples of capital structure arbitrage trades include  

1. “Long the stock of company ABC and short the bonds of company ABC”.   
2. “Long equity of a company ABC and short the CDS on the debt issued by ABC”.   
3. “Go long subordinated debt and short senior bonds”.  

How could a structural model of default be used to provide a decision rule for the implementation of the trade in (1)? One could use a Merton-type model to calculate the implied credit spread and probability of default based on company ABC’s stock price. Call this spread sMerton, implied.  

If company ABC has publicly traded bonds one can use bond prices to calculate the bond implied credit spread sBond, implied.  

If sMerton, implied $<s_{B o n d,}$ , implied, then $\varepsilon=s_{B o n d,\ i m p l i e d}-s_{M e r t o n,\ i m p l i e d}>0.$ . Assume one takes the view that the equity market correctly prices the default risk while the bond market overestimates the risk. Furthermore, if one believes that the two markets should converge in their assessment of the default risk, then one could take a long bond and a short stock position. Implicit in this approach is the view that the pricing error $\varepsilon$ declines (to 0) over time.  

The signal for such trades can be the discrepancy between the Merton model implied bond spread derived from equity prices and the CDS spread.  

The example in (2) above is based on a comparison of equity and CDS implied information and not equity and bond implied information as in the example in (1). As described in the previous chapter, CDS markets can be used to calculate a CDS implied credit spread sCDS, implied for company ABC. Consider the scenario where sMerton, implied $>s_{C D S}$ , implied. Now consider the case where a market participant believes that the CDS market is pricing the credit risk correctly while the equity market is not. One way to express this view is through a long position in the stocks of ABC while buying a CDS of company ABC. If, over time, the equity and the CDS market converge in their assessment of the credit risk, this position would make a profit.  

The following reading illustrates that such strategies can be applied not just to individual companies but also to indices. In the example, the CDS market is seen to have interpreted the macroeconomic environment differently from the equity market.  

# EXAMPLE  

JP Morgan Chase and Morgan Stanley’s CDS index for Europe, Trac-x Europe, narrowed from 140 basis points in October 2002 to 105 bp during the war, while the Dow Jones Eurostoxx 50, which was at 2,275 in early October 2002, reached a low of 1,928 in March. The apparent discrepancy was largely due to the fact that a lot of European companies were reducing their debt levels at this time [. . .]. The credit market took the view that corporate debt reduction was a stronger indicator of company performance than the negative macroeconomic indicators that were pummelling stock levels.  

(Risk Magazine, November 1, 2003, ‘Barra joins crowded market for Merton models’, www.risk.net/1497515)  

The above reading illustrates that the narrowing of CDS spreads from 140 to 105 bp reflected a view in the CDS market that credit risk diminished as European companies reduced debt levels. Since equity holders are residual claimants to the assets of the company, such an interpretation should coincide with a rise in equity prices if the equity market agreed with the CDS market. But as the example illustrates the two markets disagreed in this case and the equity market actually fell from 2275 to 1928.  

# 19.5.2 USING THE MERTON MODEL TO PROVIDE SIGNALS FOR CAPITAL STRUCTURE ARBITRAGE TRADES  

The above examples illustrated the basic idea behind capital structure arbitrage trades. We now want to look in more detail at how the Merton model can be used to provide signals for such trades. Equation (19.23) above shows how we can back out implied credit spreads from observed share prices. For a given company, which we call XYZ, we could plot the Merton model implied credit spreads for a range of different share prices. Figure 19.4a shows such a relationship.11 The axes in the figure correspond to those from the output of the basic Merton model. We see that a share price of around $\$30$ implies a credit spread of $5\%$ for XYZ. The relationship is downward sloping since a share price increase implies a lower probability of default and thus a lower credit spread. Conversely, if share prices decrease the probability of default increases.  

Now imagine that for company XYZ we gather credit spreads from bond prices of CDS markets. For simplicity we assume that the data are from bond markets, but an analogous argument could be made if the data were from CDS markets. If we used CDS market data, any potential position to exploit the mispricing would involve buying or selling CDS, while below we explain how one can go long or short bonds to exploit the mispricing.  

We superimpose these observed spreads on the relationship in Figure 19.4a. The result is shown in Figure 19.4b. The circles represent different hypothetical market observations. As the figure shows, the fit is quite good. Assume that on a given trading day a market participant plots the figure and observes share prices of around $\$25$ and a credit spread of around $10\%$ $(1000\mathrm{bp})$ as indicated by point $P$ and the horizontal line passing through $P$ . What would be the theoretical credit spread implied by the Merton model for a share price of $\$25?$ Figure $19.4\mathrm{b}$ suggests that the Merton model would imply a credit spread closer to $5\%$ $(500\mathrm{bp})$ if the share price is $\$25$ . This is illustrated by point $P^{\prime}$ and the dashed red line. Does this mean that the debt is overvalued or undervalued relative to the equity? How could one exploit any potential mispricing?  

First we note that according to Figure 19.4b, point $P$ corresponds to an observation that lies above the line indicating the theoretical relationship. This implies that the actual spread of 1000 bp (point $P$ ) is higher than the theoretical spread of $500\mathrm{bp}$ (point $P$ ’). The actual spread can be interpreted as being too high. If the actual spread is derived from bond data, this means that bonds are too cheap. If the spread is from CDS prices it means the CDS spread is too high relative to the model. From the perspective of the equity value, we observe that the actual share price is $\$25$ , whereas the Merton model would predict that the share price should be closer to $\$14$ if the credit spread was $1000\mathrm{bp}$ , which is illustrated by the dashed black line. From this perspective, the equity is overvalued. This example shows that the Merton model can be used to identify relative mispricing. To exploit the relative mispricing it is not enough to only take one position in bonds, CDS, or equities, respectively. A long position in bonds and a short position in stocks would allow exploiting a potential correction in the relative mispricing between the bonds and equities of company XYZ. Therefore to exploit the observed mispricing we would go short XYZ equity and go long XYZ bonds in the hope that stock prices will fall and bond yields fall as predicted by the Merton model. The following example illustrates however that capital structure arbitrage trades can also lose money even if it is based on long/short positions:  

# EXAMPLE  

A number of capital structure arbitrageurs were caught out when stock levels plummeted in the run-up to the war in Iraq—the Dow Jones Eurostoxx 50, which was at 2,275 in early October 2002, reached a low of 1,928 in March. But credit default swap (CDS) spreads remained relatively tight, rather than widening as a Merton model-based credit system would predict. The Trac-x Europe CDS index narrowed from 140 basis points in October to 105 bp during the war.  

(Risk Magazine, November 1, 2003, ‘Barra joins crowded market for Merton models’, www.risk.net/1497515/)  

The above example is an illustration of the use of CDS instead of bond positions together with stock positions. Arbitrageurs were long equities and sustained losses as the index fell from 2275 to 1928. They are referred to as having been short credit, which typically means long the CDS or buying protection. Thus, as credit spread’s tightened they would have suffered mark-to-market losses on the CDS position. The reason for these market moves was that the credit market believed that the ongoing corporate deleveraging was a more important determinant of company performance than the macroeconomic factors related to the war. The result was that arbitrageurs that were short credit and long equities suffered losses.  

We can generalize the above conclusions and state that the capital structure arbitrage strategy and the decision which security to go long or short depends on which side of the line representing the theoretical relationship between the actual credit spread and share price observation falls. This is shown in Figure 19.4c.  

How can we calculate the appropriate hedge ratio for the arbitrage strategy? We can derive the delta theoretically from the delta of equity with respect to the firm’s asset value $A_{t}$ . From Eq. (19.15) we know that  

$$
\frac{\mathrm{d}E_{t}}{\mathrm{d}A_{t}}=N(d_{1})
$$  

and  

$$
\frac{\mathrm{d}D_{t}}{\mathrm{d}E_{t}}=\frac{\mathrm{d}(A_{t}-E_{t})}{\mathrm{d}E_{t}}=\frac{\mathrm{d}A_{t}}{\mathrm{d}E_{t}}-1=\frac{1}{N(d_{1})}-1.
$$  

The hedge ratio $\mathrm{d}D_{t}/\mathrm{d}E_{t}$ allows us to calculate how many shares to go short (or long) for each bond bought (or sold). Our discussion so far has been framed in terms of the relative pricing of equity and bonds. If instead of bond prices the actual credit spreads were derived from CDS prices, then to exploit the mispricing one would instead of going long bonds (in the hope that bond prices would rise and spreads would tighten) one would sell a CDS.  

# 19.5.3 SOURCE OF PROFITS FROM CAPITAL  

Figure 19.4 illustrated a decision rule based on the Merton model that can be used to exploit any potential mispricing between bonds (or CDS) and equity. Now we want to examine the main  

![](67ef885d4fc55bb8e047c9e202b7101a8ac26f44498a3d6b72f1cd21297af65c.jpg)  
(a) lustrative example of relationship between credit spread and share price  

![](1f483ff75cf00d234dc07d4a76bfca51789050a4ad0e8e0a906e77e885d66d66.jpg)  
c) Indictator for capital structure arbitrage strategy and decision to go long or short  

# FIGURE 19.4  

Credit spread versus share price.  

sources of profit for the capital arbitrage strategy discussed above. It turns out that the profits can be viewed either from (a) the perspective of bond/CDS and equity prices correcting or (b) a more advanced perspective of volatility arbitrage.  

# 19.5.3.1 Capital structure arbitrage as a mispricing of bonds (or CDS) and equity  

Let’s examine (a) first. To exploit the apparent arbitrage represented by point $P$ we noted that a short stock and long bond position is optimal. Such a position will benefit if either the share price increases or the bond price rises (that is credit spreads tighten) or both occur simultaneously. There are however also other scenarios when the strategy will be profitable, for example, when the share price rises, but losses on the short stock position are outweighed by gains from the long bond position if credit spreads tighten to a sufficient extent.  

We can distinguish three potential areas in the credit spread share price space to discuss whether the strategy (i) will make money, (ii) will lose money, or (iii) will break even. Figure 19.5 illustrates the three areas. The starting point is a delta-hedged position at point $P$ . The position consists of a long bond and short stock position. As the arrow which points towards the south-west indicates any move from point $P$ towards the theoretical credit spread share price relationship represents a correction of the apparent mispricing at point $P$ and would make money for the strategy. A share price/ spread move toward the north-east would on the other hand lead to losses. There is a third area however represented by the line that passes through point $P$ . This line can be interpreted as a break-even area. Point $P$ represents a delta-hedged position and any move in the credit spreads along the line corresponds to a movement as the Merton model would indicate $i f$ the current share price/spreads observation at point $P$ was correct, that is if there was no mispricing.  

# 19.5.3.2 Capital structure arbitrage from the perspective of mispriced volatility  

As discussed, there is a second perspective (b) which interprets mispricing as mispricing of volatility rather than spreads and share prices. In our discussion of the application of the Merton model in Section 19.4.4, we showed how one can back out a credit spread from observed equity prices and volatility. This approach could be presented by the following relationship which suggests that using variables such as the equity value and volatility we can obtain the Merton model implied credit spread:  

$$
\begin{array}{r}{E_{t},\sigma_{E},F,r,\sigma_{A},T-t\xrightarrow[\mathrm{Merton-Model}]{}R-r_{\mathrm{Merton}}}\end{array}
$$  

The alternative route is to start with actual credit spreads and then back out the implied equity volatility  

$$
(R-r)_{\mathrm{actual}},E_{t},F,r,\sigma_{A},T-t\xrightarrow[\mathrm{Merton-Model}]{}\sigma_{E}^{\mathrm{actual}}
$$  

The procedure in Eq. (19.28) illustrates the use of theoretical/Merton model spreads. Figure $19.5\mathrm{b}$ shows the lines that represent that theoretical spread share price relationship for different volatilities. For example, at point $P^{\prime}$ if we plug in a share price of around $\$25$ we obtain a credit spread of $5\%$ if we use an implied equity volatility of $\sigma_{E}^{\mathrm{Merton}}$ .  

What would happen if we used the procedure in Eq. (19.29) and, together with the other parameters, plugged the share price of $\$25$ and the observed credit spread of $10\%$ corresponding to point $\mathrm{~\bf~P~}$ into the Merton formula to obtain an implied equity volatility? In this case, we would obtain an equity volatility of $\sigma_{E}^{\mathrm{actual}}$ .  

![](3b1b4bbd897e91349d24a3264d8d2c2c9cd19bf918ed23b1f1c4ca1a85035d31.jpg)  
a) llustrative example of relationship between credit spread and share price  

![](fa3e0458a26c0321cec9c5b3c1c0b85a769f35e59ed5a6b02b480ee613525d6e.jpg)  
(b) Model implied relationship versus credit spreads observed in the market  

# FIGURE 19.5  

Capital structure arbitrage profits.  

Since the Merton model is based on the Black Scholes formula, it is clear that to obtain a higher credit spread at the same stock price level of $\$25$ one would need to use a higher implied volatility. Therefore, the volatility backed out using the combination of a $\$25$ share price and $5\%$ credit spread must be lower than the volatility obtained using a $\$25$ share price and $10\%$ credit spread. $\sigma_{E}^{\mathrm{Merton}}<\sigma_{E}^{\mathrm{actual}}$ . In other words, the actual bond (or CDS) spreads being too high (compared to the Merton model implied ones for the same stock price) can be also interpreted as the bond (or CDS) spread implied equity volatility being high relative to what could be referred to as the true volatility. The profits from the strategy that is long XYZ bonds and short XYZ stocks can be reinterpreted as a result. The strategy will make money if the implied equity volatility corrects (that is decreases), that is by moves towards the theoretical credit spreadshare relationship based on volatility $\sigma_{E}^{\mathrm{Merton}}$ .  

What could be a source of the “true” equity market volatility be in the comparison above? How can we get an estimate of the input parameter $\sigma_{E}$ . One potential source is equity option implied volatility. The following reading illustrates the use of the implied equity volatility perspective on capital structure arbitrage in practice. The reading refers to an asset manager that takes CDS prices and extracts from them an implied equity volatility which is then compared to the implied volatility in the equity options market. The equity volatilities also provide the sensitivities for the delta hedging.  

# EXAMPLE  

On September 10, the CDS spread on Sun was around 70 bp above LIBOR. “This gives us a kind of implied   
equity volatility—when we use our capital structure model—of something like 45 50 volatility [basis]   
points,” $I...J$ The Axa team then compared this value with the implied volatility value on Sun in the equity options   
market. On that day, the implied volatility of 3-month at-the-money options on Sun was around 65 bp. The   
1520 bp difference was the arbitrage opportunity. To monetise this, Axa bought CDS protection on Sun   
while buying Sun stock to delta hedge the position. To work out the implied equity volatilities, $I...J$ Axa relies on a proprietary equity-based firm-value   
model based on Merton theory [. . .] (Risk Magazine, October 1, 2003, ‘Capital structure builds a following’, www.risk.net/152627  

The Merton model was used in the example to back out $\sigma_{E}^{\mathrm{actual}}$ as in Eq. (19.29). The observed CDS spread in the market implied an equity volatility of $45{\mathrm{-}}50~{\mathrm{bp}}$ , which was lower than the equity option market implied volatility of 65 bp. It seems that the traders took the view that the equity option volatility was more correct. This view was expressed by buying CDS protection and hedging by buying stock. If the credit spread in the CDS market widens the protection buyer would make mark-to-market gains. If the spread tightens the long stock position would hopefully provide a hedge given the negative empirical relationship between the two.  

# 19.6 ENGINEERING EQUITY PRODUCTS  

# 19.6.1 PURPOSE  

Companies raise capital by issuing debt or equity.12 Suppose a corporation or a bank decides to raise funds by issuing equity. Are there more advantageous ways of doing this? Financial engineering offers several alternatives that may address the company’s specific needs.  

1. Some strategies may decrease the cost of equity financing.   
2. Other strategies may result in modifying the composition of the balance sheet.   
3. There are steps directed toward better timing for issuing securities depending on the direction of interest rates, stock markets, and currencies.  

4. Finally, there are strategies directed toward broadening the investor base.  

In discussing these strategies, we consider two basic instruments that the reader is already familiar with. First, we need a straight coupon bond issued by the corporation. The second instrument is an option written on the stock. The (call) option on the stock is of European style, has expiration date $T$ and strike price $K$ . The call is sold at a premium $C\left(t_{0}\right)$ . Its payoff at time $T$ is  

$$
C\left(T\right)={\mathrm{max}}\left[S_{T}-K,\ 0\right]
$$  

These sets of instruments can be complemented by two additional products. In some equitylinked products, we may want to use a call option on the bond as well. The option will be European. In other special cases, we may want to add a credit default swap to the analysis. Many useful synthetics can be created from these building blocks. We start with the engineering of a convertible bond in a simplified setting.  

# 19.6.2 CONVERTIBLES  

In Chapter 17, we discussed callable bonds that convey an option to the issuer to redeem the bond issue early. Convertible bonds and convertible preferred stock are another example of securities with embedded options. In contrast to callable bonds they give an option to the holder of the security rather than the issuing firm. A convertible bond is a bond that incorporates an option to convert the principal into stocks. The principal can be converted to a predetermined number of stocks of the issuing company. Otherwise, the par value is received. It is clear that the convertible bond is a hybrid product that gives the bond holder exposure to the company stock in case the underlying equity appreciates significantly.  

Consider the example of a convertible bond with a conversion ratio of 20 and a par value of $\$1000$ . This allows the convertible bond holder to convert one bond of par value $\$1000$ into 20 shares of common stock. The conversion price is defined as the par value divided by the conversion ratio or $\$1000$ , that is $\$50$ in this example. The bond holder evaluates whether it is worth foregoing bonds with a face value of $\$1000$ or $\$50$ per share. When is it optimal for the holder to convert the bond? This is the case when the present value of the bond’s promised payments is $<20$ times the value of one share of stock. A convertible bond that is trading at $\$900$ and has a conversion ratio of 20 might be worth converting if the stocks were selling above $\$45$ since the value of 20 shares that the holder would receive for each bond is higher than $\$900$ . The bond’s conversion value is defined as the value that it would have if the holder converted it into stock.  

Can we say anything about the price of the convertible bond and how high it should be relative to the conversion value and the value of a straight bond? On the one hand, the convertible bond should trade at least as high as its conversion value. Otherwise one could buy the convertible bond, convert it and make an immediate profit. Such an arbitrage strategy could in reality be expected to push up the price to the conversion value or above.  

On the other hand, the convertible bond is worth at least as much as a straight bond since the convertible consists of a straight bond plus a call option. The straight bond value provides a bond floor. Figures 19.6a illustrates the straight bond value. For bond issuers with a strong balance sheet, the straight debt value should be largely independent of the value of the stock since the default risk  

![](1418c115d73a56923ec9a9e723b0a1563208b6de8005c13dc8a25d115a55901b.jpg)  

# FIGURE 19.6  

Convertible bond, conversion, and straight bond value.  

is negligible. This is represented by the horizontal bond floor. If the bond is risky then as the stock price declines the bond value can be expected to decline and even become worth close to zero as it becomes distressed. Figure 19.6b illustrates the conversion value. Figure 19.6c shows that the convertible bond value is bounded from below by the straight (risky) bond value when the stock price makes conversion unlikely. In this case, the convertible is also referred to as being busted. It is bounded from below by the conversion value when the stock price is high enough to make conversion likely. When the stock price is significantly above the conversion price, the convertible behaves like equity. The difference between the convertible bond value and the conversion value is called the conversion premium. Some convertible bonds have a required conversion or redemption feature, in which case they are called mandatory convertibles.  

We discuss the engineering of such a convertible bond under simplified assumptions. In the first case, we discuss a bond that has no default risk. This is illustrative, but unrealistic. All corporate bonds have some default risk. Sometimes this risk is significant. Hence, we redo the engineering, after adding a default risk in the second example.  

# 19.6.3 SYNTHETIC CONVERTIBLE BONDS AND CASH FLOW ENGINEERING  

From the above discussion, we can see that a convertible bond can be viewed as a portfolio of a straight bond plus a call option. This leads us to the following contractual equation.  

![](44d958b78dc1a97d17d4db3dd4c78aec77d3b571f52a368b775512626ba25611.jpg)  

Figure 19.7 shows the composition of a convertible bond’s cash flows into a defaultable bond and a call option.13 There are four potential scenarios depending on whether the bond defaults or not and whether the option is exercised or not.  

As the issuer sells an embedded option to convert its shares, the issuer expects to pay a lower fee or coupon. The buyer of the convertible is rewarded by the potential to participate in the upside of the company.  

For a risky bond, we can also build on the discussion from the previous chapter on CDS which showed that a defaultable can be replicated by a portfolio consisting of a receiver interest rate swap, a default-free deposit and selling a CDS. Thus if we replace the straight bond in Eq. (19.31) by a portfolio we obtain the following contractual equation:  

![](5f01d35252ddddecec0260bd06b245704461dd2dc1976ceba9d5483c119fbcce.jpg)  

This contractual equation provides an interesting insight since it shows that the convertible bond contains default risk that can be hedged by buying a CDS.  

![](1a30a2d540f88aae1f255a890c9fd14e730face03bb65e325cf3f825d60b5b33.jpg)  

# FIGURE 19.7  

Convertible bond decomposition.  

<html><body><table><tr><td colspan="2">Table 19.2 Intel Corporation 2.95 % Convertible Bonds Due in 2035</td></tr><tr><td>Issuer</td><td>INTEL CORP</td></tr><tr><td>Par amount Conversion ratio</td><td>$1000 34.9501</td></tr><tr><td>Conversion price Conversion value Coupon (fixed) (Conversion) Parity Conversion premium (over conversion value)</td><td>28.6122 1000 2.95% 110.547 15.703</td></tr><tr><td>Price of one Intel Share Yield to maturity</td><td>31.63 1.51</td></tr><tr><td>Coupon Frequency Price of the convertible bond Call provision</td><td>Semiannual 126.25 None</td></tr><tr><td>Implied volatility Delta</td><td>62.194 0.560</td></tr><tr><td>Vega Theta</td><td>0.268 0.004</td></tr><tr><td>Psi Credit sensitivity</td><td>-2.092</td></tr><tr><td></td><td>-3.539</td></tr><tr><td></td><td></td></tr><tr><td>Aggregate amount issued</td><td>1,600,000 (M)</td></tr><tr><td>Announcement date</td><td>03/30/2006</td></tr><tr><td>1st coupon date</td><td>06/14/2035</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td>Convertible until</td><td>12/14/2035</td></tr><tr><td></td><td>12/15/2035</td></tr><tr><td>Maturity date</td><td></td></tr><tr><td>Book Runner</td><td>JPM</td></tr><tr><td></td><td></td></tr><tr><td>Source:Bloomberg,July15,20l4.</td><td></td></tr></table></body></html>  

# 19.6.4 REAL-WORLD EXAMPLE  

It is instructive to examine a real-world example. Table 19.2 provides information on a convertible bond issued by Intel. The bond matures in 2035. The bond pays a $2.95\%$ semiannual coupon. The reported conversion ratio is 34.9501 and the conversion price is 26.6122. If we multiply the conversion ratio times the conversion price we obtain a conversion value of 1000. The share price of Intel on that day was 31.63. The convertible bond is currently selling for 126.25 per $\$100$ or 1262.5 per $\$1000$ par value. The conversion parity is defined as the share price multiplied by the conversion ratio: $34.9501\times31.63=1105.47$ . The conversion premium is defined as the price of the convertible minus the conversion parity, that is $1262.5-1105.47=157.03$ per $\$1000$ or $\$15.703$ per $\$100$ as indicated in the table. The implied volatility is 62.194 and can be compared to the implied volatility of equity options on Intel shares on that day. The delta is the sensitivity of the convertible bond to changes in the share prices and it is 0.56 according to the table.  

# 19.6.5 CONVERTIBLE BOND PRICING  

# 19.6.5.1 Bond plus equity option approach  

There are several issues that complicate the decomposition in Eq. (19.31) and any valuation based on it. These complications include dividend payments by the stock, a conversion price that may increase over time and any potential call options that allow the issuer to repurchase the bond early. Moreover, convertible bonds contain an option component with a stochastic strike price equal to the bond price.  

# 19.6.5.2 Multifactor model  

A further complicating factor relates to default risk. As we saw in Figure 19.6, the share price level is a key determinant of the convertible bond value. In principle, this means that we can use the Black Scholes approach to value the convertible with the state variable being the share price and use a dynamic hedging strategy to value to embedded option. However, as Figure 19.6c shows, the credit risk of the bond also depends on the stock price. The most recent and sophisticated convertible bond pricing models incorporate the stochastic nature of interest rates and credit spreads. References to recent papers on convertible bond pricing are provided at the end of the chapter. Bloomberg’s convertible bond pricing function, for example, incorporates not only time-varying interest rates, dividends, and volatility but also allows for jumps in the stock price which can be calibrated to CDS data.  

# 19.6.6 CONVERTIBLE BOND ARBITRAGE  

Historically some of the most active buyers of convertible bonds were hedge funds.14 However, recent estimates suggest that the proportion of hedge funds as buyers of convertible bonds has fallen from $75\%$ in 2008 to less than $40\%$ in 2013.  

Convertible arbitrage strategies are used by hedge funds in an attempt to generate risk-adjusted performance. Consider the following reading.  

# EXAMPLE  

Convertible arb hedge funds in the U.S. are piling into the credit default swaps market. The step-up in demand is in response to the rise in investment-grade convertible bond issuance over the last month, coupled with illiquidity in the U.S. asset swaps market and the increasing credit sensitivity of convertible players’ portfolios, said market officials in New York and Connecticut.   
Arb hedge funds are using credit default swaps to strip out the credit risk from convertible bonds, leaving them with only the implicit equity derivative and interest rate risk. The latter is often hedged through futures or treasuries. Depending on the price of the investment-grade convertible bond, this strategy is often cheaper than buying equity derivatives options outright, said [a trader].   
Asset swapping, which involves stripping out the equity derivative from the convertible, is the optimal hedge for these funds, said the [trader] as it allows them to finance the position cheaply, and removes interest rate risk and credit risk in one fell swoop. But with issuer-credit quality in the U.S. over the last 12 to 18 months declining, finding counterparties willing to take the other side of an asset swap has become more difficult. . .  

(Based on an article in Derivatives Week (now part of GlobalCapital))  

Convertible bonds are generally issued at a discount to their theoretical value. This implies that hedge fund managers can extract the undervalued component from the convertible using appropriate techniques. One of the most basic convertible bond arbitrage strategies is to buy cheap volatility. A convertible bond consists of a bond and an option as we saw earlier. A hedge fund manager can calculate the price of the embedded option or the equity volatility implied by the current price of the convertible. By comparing the implied volatility of the embedded option to historical volatility or the implied volatility of listed options on the same stock, it is possible to calculate whether the embedded option in the convertible bond is undervalued. The implied equity volatility is the volatility that needs to be entered into a convertible bond pricing model together with other input parameters in order to generate the observed convertible bond price. The implied volatility for the convertible bond issued by Intel, for example, was 62.194 according to the Bloomberg data in Table 19.2.  

If the option embedded in the convertible is cheaper than a vanilla call option on the same stock, then a fund can go long the convertible bond in the hope that the undervalued embedded option will appreciate in value. A range of techniques can be employed to hedge against unwanted risks and isolate the desired equity, credit, event, or even currency exposure embedded in the securities.  

The basic convertible bond arbitrage strategy is long volatility. This means that the strategy benefits from volatility in the underlying stock. The volatility exposure arises from two different sources. First, the embedded stock option implies that the buyer of the convertible bond is long gamma, that is the rate of change in the delta with respect to stock prices. Second, the strategy is long vega since the call option price rises if implied volatility rises. In the case of the Intel convertible discussed above, the vega was 0.268. If the implied volatility corrects and rises, this will lead to gains for the holder of the convertible bond. Convertible bonds are also exposed to more complex risk including credit risk. On the one hand, a deterioration in the creditworthiness of the issuer is likely to coincide with an increase in the volatility of the underlying stock which in turn affects the value of the embedded call option. The opposite is likely to happen if creditworthiness improves. On the other hand, a deterioration of the credit quality of the issuer directly affects the underlying risky bonds. As credit spreads tighten, the value of a convertible bond is likely to increase. As credit spreads widen its value decreases.  

Equation 19.32 showed that a convertible bond can be decomposed into several constituents including a CDS position. Therefore, CDS can be used to hedge credit risk embedded in a long convertible bond position. The reason is that the mark-to-market value of an existing CDS position will change as the credit risk of the issuer changes. To establish the correct hedge ratio, we examine how sensitive the CDS is to changes in credit spreads relative to the sensitivity of the convertible bond. Omnicron measures the price impact of an increase in credit spreads. Typically this measure is rebased for 1 basis point increase in the level of credit spreads. Practitioners also call this sensitivity the Credit DV01.  

The equity market risk can be hedged using short stock positions or put options. The credit market risk exposure is in principle best hedged using CDS. However, sometimes, equity market puts may be a cheaper hedging alternative than CDS. As the Merton model illustrated, equity market and credit markets are linked. One can calculate the sensitivity of put options and CDS to the underlying credit risk and use this sensitivity as a hedge ration and choose between a CDS or equity put option hedge depending on which one is cheaper.  

# 19.6.7 COMPARING THE ROLE OF VOLATILITY IN CONVERTIBLE BOND ARBITRAGE AND CAPITAL STRUCTURE ARBITRAGE  

As we saw in Section 19.5, in capital structure arbitrage we can interpret the straight bond as an equity derivative since there is a theoretical relationship between the bond and the equity. We can use a Merton-type model to calculate the equity volatility implied by the share price and the credit spread. If this implied equity volatility differs from what is viewed as the correct volatility, the market participant can buy or sell the bonds (or the CDS) and delta hedge the position. There is an important difference between the capital structure arbitrage strategy and the convertible bond arbitrage strategy since a convertible bond can be converted into equity while a straight bond cannot. This implies that there are theoretical arbitrage bounds for the convertible but no such bounds exist for straight debt based on the Merton-type models. This in addition to the restrictive assumptions of the Merton model imply that arbitrage strategies based on simple structural models of default may not predict actual movements in equity and credit markets well.  

# 19.6.8 INCORPORATING MORE COMPLEX STRUCTURES  

This section considers two variations of the basic convertible structure. First of all, the basic convertible can be modified in a way that will make the buyer operate in two different currencies. In fact, a dollar-denominated bond may be sold, but the underlying shares may be, say, French shares, denominated in Euros. This amounts, as we will see, to adding a call or put option on a foreign currency.  

The second alternative is also important. The basic convertible can be made callable. This amounts to making the underlying debt issue a callable bond. It leads to adding a call option on the bond. Before we see how these are used, we consider some of the financial engineering issues in each case.  

# 19.6.8.1 Exchange rate exposure  

Suppose the convertible bond is structured in two currencies. A Thai company secures funding by selling a euro convertible in the Eurodollar market, and the debt component of the structure is denominated in dollars. So, the bonds have a par value of, say, $\$100$ . The conversion is into the shares of the firm, which trade, say, in Bangkok. The shares are baht denominated. We assume, unrealistically, that there is no default risk.  

Because Thai shares trade in Thai exchanges and are quoted in Thai baht, the conversion price to be included in the convertible bond needs to specify something about the value of the exchange rate to be used during a potential conversion. Otherwise, the conversion rule will not be complete. That is to say, instead of specifying only the number of shares, $n$ , and the conversion price, $K.$ , using the equality  

$$
100\S=K n
$$  

the conversion condition now needs to be  

$$
e_{t}100\mathbb{S}=K n
$$  

where $\boldsymbol{e}_{t}$ is an exchange rate denoting the price of USD1 in terms of Thai baht at date $t.$ This is needed since the original conversion price, $K$ , will be in Thai baht, yet, the face value of the bond will be in USD. The bond structure can set a value for $\boldsymbol{e}_{t}$ and include it as a parameter in the contract. Often, this $\boldsymbol{e}_{t}$ will be the current exchange rate.  

![](af3c6b31a10dfc5be9916624dbc4faec85ce1b05f4b2a38f5305196210ab8346.jpg)  

# FIGURE 19.8  

Convertible with currency conversion.  

Now, suppose a Thai issuer has sold such a Euro convertible at $\boldsymbol{e}_{t}$ , the current exchange rate. Then, if Thai stocks rise and the exchange rate remains stable, the conversion will occur. Here is the important point. With this structure, at maturity, the Thai firm will meet its obligations by using its own shares instead of returning the original $\$100$ to bond holders. Yet, if, in the meantime, $\boldsymbol{e}_{t}$ rises,15 then, in spite of higher stock prices, the value of the original principal $\$100$ , when measured in Thai baht, may still be higher than the $n S_{T}$ and the conversion may not occur. As a result, the Thai firm may face a significant dollar cash outflow.16  

This shows that a convertible bond, issued in major currencies but written on domestic stocks, will carry an FX exposure. This point can be seen more clearly if we reconstruct this type of convertible and create its synthetic. This is done in Figure 19.8.  

The top part of Figure 19.8 is similar to Figure 19.7. A straight coupon bond with coupon $c$ matures at time $t_{3}$ and pays the principal $\$100$ . The difference is in the second part of the figure. Here, we have, as usual, the call option on the stock $S_{t}$ . But $S_{t}$ is denominated in baht and the call will be in-the-money—that is to say, the conversion will occur only if  

$$
n S_{t_{3}}>100e_{t_{3}}
$$  

The idea in Figure 19.8 is the following. We would like to begin with a dollar bond and then convert the new call option into an option as in the case before. But, if the Thai baht collapses,17 then the $\$100$ received from the principal at maturity will be much more valuable than $S_{t_{3}}n/e_{t_{0}}$ .  

# 19.6.8.2 Making the convertibles callable  

One can extend the basic convertible structure in a second way and add a call option on the underlying convertible bond. For example, if the bond maturity is $T_{\mathbf{\delta}}$ , then we can add an implicit option that gives the issuer the right to buy the bond back at time, U $\ ,\ U{<}T$ at the price  

$$
\operatorname*{max}{[\mathbb{S}100,~n S_{U}]}
$$  

This way the company has the right to force the conversion and issue new securities at time $U$ .   
Some corporations may find this a useful strategy.  

With this type of convertible, forcing the conversion is the main purpose. Suppose the following two conditions are satisfied:  

1. The share is trading at a higher price than the conversion price (i.e., the strike $K_{\cdot}$ ). 2. The expected future dividends to be paid on the stock are lower than the current coupon of the convertible.  

Then, if the convertible is callable, the issuer may force the conversion by calling the bond. This will convert a debt issue in the issuer’s balance sheet into equity and affect some important ratios, in case these are relevant. Second, the immediate cash flow of the firm will improve.  

# 19.6.8.3 Exchangeable bond  

The basic convertible-warrant structures can be modified to meet further financial engineering needs. We can consider another example. Suppose the convertible bond, when it converts, converts into another company’s security. This may be the case, for example, if company $A$ has acquired an interest in company B. This way, the company can sell convertible bonds where the conversion is into company B’s securities.  

From a financial engineering point of view, the structure of this “exchangeable” is the same. Yet, the pricing and risk management are different because now there are two credits that affect the price of the bond: the credit of the company that issues the bond and the credit of the company this bond may convert.  

Another difference involves the dilution of the shares of the target company. When a convertible is issued and converts at a later date, there may be dilution of the shares, yet, in an exchangeable the shares that are exchanged will come, in general, from the free float.  

# 19.6.9 USING CONVERTIBLES  

A convertible bond has some attractiveness from the point of view of end investors. For example, the investor who buys the convertible will have some exposure to the share price. If $S_{t}$ increases significantly, the bond becomes a portfolio of shares. On the other hand, if the bond fails to convert, the investor has at least some minimum cash flow to count on as income, and the principal is recovered (when there is no default).  

But, our interest in this book is not with the investors, but rather, in the advantages of the product from an issuer’s point of view. For what types of purposes can we use a convertible bond?  

The first consequence of issuing convertibles rather than a straight bond is that the convertible carries a lower coupon. Hence, it “seems” like the funds are secured at lower cost.   
More notably for a financial engineer, convertibles have interesting implications for balance sheet management. If an equity-linked capital is regarded as equity, it may have less effect on ratios such as debt to equity. But, in general, rating agencies would consider straight convertibles as debt rather than equity.   
Note that with a convertible, in case conversion occurs, the shares will be sold at a higher price than the original stock price at issue time. Finally, convertibles are bonds, and they can be sold in the Euro markets as Euro-convertibles. This way a new investor base can be reached.  

We should also point out that convertibles, when combined with other instruments, may have significant and subtle tax advantages. The best way to show this is by looking at an example from the markets.  

# EXAMPLE  

(ABC Capital) has entered into a total return swap on 154,000 shares of Cox Communications preferred stock exchangeable into shares of Sprint PCS, and a total return swap on 225,000 shares of Sprint PCS. In the Cox swap, the hedge fund pays three-month LIBOR plus 50 basis points and receives the return on the exchangeable preferred shares. In the Sprint swap, ABC pays the return on the stock and receives threemonth LIBOR less 25 bps. Both total return swaps mature in about 13 months.   
The total return swaps were entered into for tax reasons. ABC’s positions are held by a Cayman Islands limited duration company. Because the Cayman Islands do not have a tax treaty with the U.S., income from these securities is withheld at the non-treaty rate of $30\%$ . Entering the total return swaps ensures that ABC does not physically hold the securities, and, hence, is not subject to U.S. withholding.   
The underlying position was put on as part of a convertible arb play. ABC bought the exchangeable preferred stock and is using the cash equity to delta hedge the implicit equity option. The market is   
undervaluing the exchangeable preferred shares, according to a trader, who noted that although these shares recently traded at USD76.50, the fund’s models indicate they should be priced around USD87. The company’s model is based in part on the volatility of the underlying stock, the credit quality of the issuer, and the features of the convertible. In this case, the market may be undervaluing the security because it is not pricing in all the features of the complicated preferreds and because of general malaise in the telecom sector.  

(Derivatives Week (now part of GlobalCapital), November 2000)  

This reading is also an example of how implicit options can be used to form arbitrage portfolios.   
However, there are many delicate points of doing this as were shown earlier.  

# 19.6.10 WARRANTS  

Warrants are detachable options linked to bonds. In this sense, they are similar to convertibles.   
But, from a financial engineering point of view, there are important differences.  

1. The warrant is detachable and can be sold separately from the bond. Of course, a financial engineer can always detach the implicit option in a convertible bond as well, but still there are differences. The fact that the warrant is detachable means that the principal will always have to be paid at maturity.  

The number of warrants will not necessarily be chosen so as to give an exercise cash inflow that equals the cash outflow due to the payment of the principal. Thus, the investor can, in principle, end up with both the debt and the equity arising from the same issue.   
2. The exchange rate used in a convertible is fixed. But, because there is no such requirement for a warrant and because the latter is detachable, this is, in general, not the case for a warrant. Hence, there is no implicit option on the exchange rate in the case of warrants. In this sense warrants are said to be relatively more attractive for strong currency borrowers, whereas convertibles are more attractive for weak currency borrowers.   
3. Finally, because warrants are detachable, the warrant cannot be forced to convert. The bond can be called, but the conversion is not required.  

We now move to another topic and look at securitizing cash flows. This can be regarded as an example of new product structuring.  

# 19.7 CONCLUSIONS  

In this chapter, we saw how we can apply the financial engineering and option pricing principles to value equity. Equity can be viewed as an option on the assets of the firm with a strike price equal to the debt value. Structural models of default thus establish a link between equity markets and bond or CDS markets. The development of credit derivative markets has accelerated the use of structural models of default in practice. Their applications range from the forecasting of default to capital structure arbitrage. Convertible bonds are hybrid products that can be converted from debt to equity. Convertible bond arbitrage strategies are based on exploiting cheap volatility while delta hedging the position. In the next chapter, we will review various structure products including reverse convertibles. Unlike convertible bonds, in reverse convertibles, the conversion option is conveyed to the issuer of the product and not the buyer. Both types of instruments have thus embedded options whose value depends on the implied volatility.  

# SUGGESTED READING  

This chapter has provided a simple introduction to structural models of default and hybrid equity products. The reader may want to follow up on the discussion in two ways. Das and Sundaram (2010) provide an accessible summary and application of the Merton (1974) model. Sundaresan (2013) reviews recent developments in research on structural models of default. Tepla (2004) provides a nice example and case study of convertible and capital structure arbitrage strategies based on KBC Investment Management. The discussion of capital arbitrage profits in this chapter is based on the case study.  

Ayache et al. (2003) provide a review of valuation of convertible bonds with credit risk. Several books deal with the current state of hybrid equity instruments. Das (2000) is one example. Duffie and Singleton (2003) is also a good reference. The reader may also want to learn more about the technical issues related to pricing, hedging, and risk-managing hybrid equity products.  

Kat (2001) deals with some of the related issues. Damadoran (2012) is a good reference for discounted cash flow and other equity valuation approaches under the real-world probability measure which we do not discuss in this chapter.  

# EXERCISES  

1. Explain why debt in the Merton (1974) model is viewed as an option.   
2. Assume that company A has an asset volatility of $20\%$ . The current value of its assets is $\$100$ million and the face value of its 1-year maturity zero-coupon debt is $\$50$ million. The risk-free rate of interest is $2\%$ . Use the Merton (1974) model to calculate the value of the firm’s equity. What is the value of the debt?   
3. Consider company B which issued equity and zero-coupon bonds with a maturity of 1 year. Assume that the value of the firm is $\$100$ and the value of the equity is $\$50$ million. The risk-free rate is $2\%$ . The equity volatility is $30\%$ . a. What is the market value of debt and the implied credit spread? b. Assume that the company has 1 million shares outstanding. Plot the credit spread against the share price for a range of different share price values. c. Plot the hedge ratios for different values of the share price.   
4. What variables and real-world complications are important in practice but ignored by the basic Merton model.   
5. Consider two convertible bonds X and Y, which for simplicity are assumed to be riskless. The following table provides information about the two bonds. Calculate the conversion value. What is the yield to maturity of the convertible bonds based on the actual bond price?  

<html><body><table><tr><td></td><td>Convertible Bond X</td><td>Convertible Bond Y</td></tr><tr><td>Annual coupon</td><td>50</td><td>50</td></tr><tr><td>Time to maturity</td><td>5 years</td><td>5 years</td></tr><tr><td>Conversion ratio</td><td>30</td><td>40</td></tr><tr><td>Stock price</td><td>$25</td><td>$30</td></tr><tr><td>Conversion value</td><td>？</td><td>？</td></tr><tr><td>Yield on 5-year Treasuries</td><td>5%</td><td>5%</td></tr><tr><td>Value of straight debt</td><td>913.41</td><td>913.41</td></tr><tr><td>Actual convertible bond price</td><td>920</td><td>1207</td></tr><tr><td>Yield to maturity of convertible</td><td>？</td><td>？</td></tr></table></body></html>  

Examine the information given in Table 19.2 in the text. Consider a trader that buys the convertible bond because it views the implied volatility as cheap and expects the implied volatility of the bond to correct. If the trader decides to hedge the long convertible bond position, how many shares does he have to short to be delta neutral?  

This page intentionally left blank  