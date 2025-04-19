---
tags:
  - capital_structure_arbitrage
  - credit_risk
  - default_risk
  - equity_valuation
  - merton_model
aliases:
  - Merton's Model
  - Structural Model
key_concepts:
  - capital structure arbitrage
  - credit rating agencies
  - default probability
  - equity as option
  - risk neutral probabilities
---

# 19.4 EQUITY AS AN OPTION ON THE ASSETS OF THE FIRM 19.4.1 MERTON'S STRUCTURAL MODEL OF DEFAULT  

In Chapter 9, we introduced the Black-Scholes option pricing model to price an option on a stock. Can the option pricing approach also be used to price equity? It turns out that the answer is affirmative. Merton (1974) proposed a seminal structural model of default in which the equity of a firm is viewed as an option on the assets of the firm with a strike price equal to the (face) value of the debt. As the name indicates, the typical application of the model does not lie in the pricing of the equity, but rather in backing out information about the debt (including the default probability) from observed market prices for equity. As a result structural models of default have a large range of important practical applications including the modeling, pricing, and forecasting of default risk.4 The following example illustrates the practical relevance of the structural approach.  

# EXAMPLE  

The Tequila crisis, the Asian financial crisis, Brazil, Russia, Enron... it seems most large credit events are followed by critical post mortems on the effectiveness of credit rating agencies. Investors seeking better default indicators than produced by rating analysts have turned to a variety of sources, not least of which is the family of so-called Merton model tools, perhaps the most well known of which is KMV's..  

(Risk Magazine, February 1, 2002, Battle of the supermodels', www.risk.net/1506552)  

The GFC provided further recent examples of corporate defaults that preceded downgrades by rating agencies. Merton-type models, of course, are not infallible and like all models they have their strengths and weaknesses. One application of structural models of default is in the form of so-called capital structure arbitrage. As we will see capital structure arbitrage consists of exploiting potential misvaluation between the debt and the equity issued by a given company.  

The Merton (1974) model is an excellent example of the financial engineering and option valuation concepts that we discussed in previous chapters. In the previous chapter, we discussed credit risk, the probability of default of a risky bond and credit default swaps. We saw that credit spreads and therefore an implied probability of default can be backed out from both corporate bond spreads as well as CDS spreads. The Merton model provides us with a third source of probability of default information. All three sources of default probabilities use market prices and therefore provide us with risk-neutral default probabilities. These probabilities can be used to calculate expected cash flows in a risk-neutral world with credit risk. We saw in Chapter 12 that according to the fundamental theorem of asset pricing, a derivative's price is the discounted expected value of the future payoff under the risk-neutral measure. Since structural models of default tie together the values of bond and equity markets they allow financial engineers and market participants to exploit potential arbitrage and relative value opportunities between equity, bond, and CDS markets. We will discuss examples of such arbitrage strategies below.  

The Merton model has spawned a large literature that has extended the basic model in many different directions. We will first describe the basic model and then discuss applications before pointing to recent extensions. Since it is the simplest case, we review the Merton model in the context of the valuation of a risky zero-coupon bond, but Merton (1974) also considered the cases of coupon-bearing and callable debt.  

# 19.4.2 PAYOFFS TO BOND AND EQUITY HOLDERS  

A standard company balance sheet is a summary of the financial position of a company at a given point in time and consists of three main parts: assets, liabilities, and equity. Equity holders therefore have a residual claim on the firm after creditors have been paid. Figure 19.1a illustrates a stylized balance sheet. The stock market allows us to observe the market value of equity. Therefore the balance sheet in the figure can be interpreted as reflecting market as opposed to book values of assets, debt, and equity. For (medium and large) companies that publicly issue bonds we can observe market values for the debt in the form of bond prices.6  

(a Firm's balance sheet (market values)  

<html><body><table><tr><td>Assets</td><td>Liabilities</td><td></td></tr><tr><td rowspan="2"></td><td>Debt</td><td rowspan="2">Usetradedbond andequityvalues ifavailable</td></tr><tr><td>Equity</td></tr></table></body></html>  

(b)Payments to debt and equity holders under different scenarios c Payoff profile of debt and equity positions  

<html><body><table><tr><td></td><td>Scenario1: A>F T</td><td>Scenario2: A<F T</td></tr><tr><td>Debtholders</td><td>F</td><td>A T</td></tr><tr><td>Equityholders</td><td>A-F T</td><td>0</td></tr></table></body></html>  

![](a96c81b6b0ffdafd60f2b37d64569b346a56363b1760c72984e157a9c3beb997.jpg)  
(dDecomposition of payoff to debt holders into short put option position  

<html><body><table><tr><td rowspan="5">Portfolio</td><td></td><td>Scenario1: A>F T</td><td>Scenario2: A<F T</td></tr><tr><td>Debtholders</td><td>F</td><td>A T</td></tr><tr><td>Risklessdebt</td><td>F</td><td>F</td></tr><tr><td></td><td>0</td><td>-（A_-F) T</td></tr></table></body></html>  

# FIGURE 19.1  

Equity as option on firm's assets.  

# 19.4.2.1 Payments to debt and equity holders under different scenarios  

Consider a firm that has only issued two types of securities: equity and zero-coupon bonds, that is the debt. How can we apply option valuation techniques to the equity of such a firm that issues. only one type of debt in the form of a zero-coupon bond with face value $F\mathrm{?}$ The value of the firm at date $t$ is equal to the (market) value of the firm's assets and therefore we denote it by $A_{t}$ . Let's first consider the relationship between the value of the firm, denoted by. $A_{t}$ the value of the equity $E_{t},$ and the value of the debt. $D_{t}$ . Debt holders are promised a payment of. $F$ at maturity date $T.$ Now, consider two possible scenarios:.  

1. $A_{T}>F$ : If $A_{T}$ the assets of the firm at maturity $T$ exceed the promised value of the payment to bond holders $F,$ then equity holders will be paid the residual amount $A_{T}{-}F$ and the equity is worth $E_{T}=A_{T}-F $ In this scenario, there is no default.   
2. $A_{T}{<}F$ : If $A_{T}$ the assets of the firm at maturity $T$ are below the amount promised to debt holders, the firm defaults. In this case, there is no residual amount remaining for equity holders and the equity is worth zero $E_{T}.$ The equity holders have limited liability and as a result their claim cannot be worth less than zero. These two scenarios are illustrated in Figure 19.1b.  

We can plot the payoffs to equity, $E_{T}$ , and the payoff to bond holders, $D_{T}$ against the value of the firm's asset at maturity $T,A_{T}.$ This is represented by the dashed lines in Figure 19.1c. As we can observe the payoff profile of equity resembles that of a call option on the assets of the firm, $A_{T}.$ The figure also indicates the limited liability feature. It implies that equity holders can walk away from the firm's debt in exchange for a payoff of zero. The strike price is the face value of the zero-coupon debt. The payoff profile for the bond or debt holders, in contrast is reminiscent of a short put position. Since before maturity at date $t<T$ the options also have time value, the curved black lines plot the value of the equity and the debt at dates before maturity. The value of the equity and debt has some time value before maturity. The black lines represent the value of equity $E_{t}$ and debt $D_{t}$ before maturity.  

Figure 19.1c illustrates the basic intuition for why in the Merton model, the equity is priced as a European call option on the firm's assets while the bond holders' claim is equivalent to risk-free debt in addition to a short put position. The payoff of the creditors at date $T$ can be written as:  

$$
D(A_{T},T)=\operatorname*{min}(A_{T},F)=F-{(F{-}A_{T})}^{+}.
$$  

This is illustrated in Figure 19.1d. The decomposition of the payoff to the bond holders shows that the bond holders are short a put option written on the assets of the borrowing firm with a strike price equal to the face value of the debt $F$ The put option implicit in the creditor payoff is sometimes referred to as a default or credit put.  

We can also apply the put--call parity relationship, introduced in Chapter 11, to derive the value of the firm and the value of risky debt. Remember that the put--call parity relationship states that a portfolio of a call minus a put is equal to the value of a portfolio containing the underlying minus a riskless bond.  

$$
C_{t}-P_{t}=S_{t}-e^{-r(T-t)}K
$$  

In the context of the Merton model the underlying assets $(S_{t})$ are the firm's assets, that is $S_{t}=A_{t}$ The face value of the bond is $F$ , that is $K=F$ , so that the put-call parity relationship becomes  

$$
C_{t}-P_{t}=S_{t}-e^{-r(T-t)}K=A_{t}-\operatorname{Riskless}\operatorname{Bond}(t)
$$  

![](ee7e08b12a33d3aa24f3cadb6f07b7ff877b675aed2c3a5a998718cc3404baab.jpg)  

# FIGURE 19.2  

Distribution of firm value in Merton model.  

Equation (19.5) can be rewritten in terms of the assets $A_{t}$ of the firm as follows:.  

$$
A_{t}=\operatorname{Riskless}\operatorname{Bond}(t)+C_{t}-P_{t}
$$  

We also know that the value of the assets equals the (risky) debt plus the equity:  

$$
A_{t}=E_{t}+D_{t}
$$  

Since the underlying assets in Eq. (19.6) are the assets of the firm, we can set Eqs. (19.6) and (19.7) equal to each other to get  

$$
\mathrm{Riskless~Bond}(t)+C_{t}-P_{t}=E_{t}+D_{t}
$$  

Now we note that equity in the Merton model is a call option on the assets of the firm ( $C_{t}=E_{t},$ that we can write Eq. (19.8) as follows:.  

$$
\mathrm{Riskless~Bond}(t)+E_{t}-P_{t}=E_{t}+D_{t}
$$  

and therefore we subtract $C_{t}$ from both sides to get  

$$
\mathrm{Riskless\:Bond}(t)-P_{t}=D_{t}
$$  

This leads to the following contractual equation:  

![](a2828f213259b8bf8ddbb5cddc6df69610214f24ad8574a4ce00424f48a879c9.jpg)  

# 19.4.2.2 Bond and equity value in the Merton mode!  

One of the convenient results of the Merton model and subsequent papers using this methodology is. that closed-form solutions for the value of debt and equity can be obtained. To do so, we need to. make an assumption about the evolution of the firm's assets over time and its relationship to the firm's liabilities. Figure 19.2 illustrates one such possible path followed by the firm's assets. $A_{t}$ Over time.  

The dashed blue line represents the path of the firm's expected asset value over time. The curve at time $T$ represents the probability distribution of $A_{t}$ at time $T.$ The distribution illustrates the fact that there is uncertainty about the evolution of. $A_{t}$ . The Merton model makes specific distributional assumptions about the evolution of assets over time.' The face value of the debt is represented by $F$ . Default occurs if the assets. $A_{T}$ at time $T$ fall below the face amount of the debt $F.$ The difference between $E(A_{T})$ and $F$ is called distance to default. $(D D)$ . We assume that the value of the assets of the firm $A_{t}$ follows a geometric Brownian motion.  

$$
\mathrm{d}A_{t}=A_{t}(\mu\mathrm{d}t+\sigma\mathrm{d}W_{t})
$$  

where $\sigma$ is the asset volatility, $\mu$ is the expected continuously compounded return on $A_{t}$ and $W_{t}$ represents a geometric Brownian motion. The basic model makes several restrictive assumptions which we discuss later and which have been relaxed by subsequent research. Here we highlight one of the assumptions that is implicit in our discussion above, namely that default can only occur at date $T$ and there are no distress costs associated with default, which implies that bond holders receive $A_{T}$ in case of default. This assumption allows us to model the option feature as a European option with maturity date $T.$  

As we saw in Figure 19.1c, the firm's equity value at time $T$ is given by  

$$
E_{T}=\operatorname*{max}(A_{T}-F,0)
$$  

We can apply the Black-Scholes European call option pricing formula to derive the value of the firm's equity at date $t.$ If we make the assumption that one can trade the firm's assets $A_{t}$ then, from Chapter 12, we know that $e^{-r t}A_{t}$ is a martingale under the risk-neutral measure $\tilde{P}$ which leads to the following:  

$$
E_{t}=E^{\Tilde{P}}[e^{-r(T-t)}(A_{T}-F)^{+}]=B S\mathrm{Call}(A_{t},F,r,\sigma,T-t)
$$  

The Black--Scholes formula for a European call is  

$$
E_{t}=A_{t}N(d_{1})-F e^{-r(T-t)}N(d_{2})
$$  

where  

$$
d_{1}={\frac{l n(A_{t}/F)+(r+(1/2)\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

and  

$$
d_{2}=d_{1}-\sigma{\sqrt{T-t}}
$$  

The value of the debt at date $t$ is  

$$
D_{t}=A_{t}N(-d_{1})+e^{-r(T-t)}F N(d_{2})
$$  

An important insight from the Merton model is that the spread between the risky debt and the risk-free debt is the value of the put option. Credit spreads are therefore a function of the input  

parameters of the model such as the maturity of the debt, the leverage, the strike price of the put, and the business risk of the firm..  

Let the yield on a riskless bond be represented by $r.$ Furthermore, if we denote the yield on a. risky zero-coupon bond by. $R$ , then the price of a risky bond at date. $t$ as a function of the yield and. the face value is  

$$
D_{t}=e^{-R(T-t)}F
$$  

After taking logs and solving for $R$ , the yield. $R$ can be written as.  

$$
R=-\left({\frac{1}{T-t}}\right)l n\left({\frac{D_{t}}{F}}\right)
$$  

We can plug the expression for $D_{t}$ from Eq. (19.16) into Eq. (19.18) to obtain the yield $R$ of a risky bond:  

$$
\begin{array}{l}{{\displaystyle R=-\frac{1}{T-t}l n\left[\frac{A_{t}N(-d_{1})+e^{-r(T-t)}F N(d_{2})}{F}\right]}}\ {{\displaystyle~=-\frac{1}{T-t}l n\left[e^{-r(T-t)}\left(\frac{A_{t}}{e^{-r(T-t)}F}N(-d_{1})+N(d_{2})\right)\right]}}\ {{\displaystyle~=-\frac{1}{T-t}\bigg\{-r(T-t)+l n\left[\left(\frac{1}{L}N(-d_{1})+N(d_{2})\right)\right]\bigg\}}}\ {{\displaystyle~=r-\frac{1}{T-t}\left(l n\left[\left(\frac{1}{L}N(-d_{1})+N(d_{2})\right)\right]\right)}}\end{array}
$$  

where $L=e^{-r(T-t)}F/A_{t}$ is a measure of leverage. We can rewrite Eq. (19.22) in terms of the credit spread $R-r$  

$$
R-r=-\frac{1}{T-t}\left(l n\left[\left(\frac{1}{L}N(-d_{1})+N(d_{2})\right)\right]\right)
$$  

The expression in Eq. (19.23) is important and useful since it shows us how based on the input parameters one can calculate the implied credit spread from the Merton model. This equity implied credit spread can be compared to credit spreads from bond or CDS prices. The Merton model implies that as share prices increase, the credit spread decreases. Do we observe such a negative relationship in practice? Figure 19.3 provides an illustrative example. It plots the credit default spread for Goldman Sachs against the Goldman Sachs share price over the period. $2007-2014$ on a weekly basis. It is clear that the relationship is negative as predicted by the Merton model. This example does, of course, not represent proof of the practical usefulness of the Merton model in explaining credit spreads. Recent comprehensive academic studies find some support for the Merton model and for its input parameters being able to explain credit spreads, but these studies also suggest that factors outside the Merton model are important for the determination of credit spreads..  

It is a priori not clear which financial market should price credit risk correctly, but a market. participant can take the view that either the equity, the bond, or the CDS market prices credit risk. correctly and then take long and short positions in two of these markets to try to exploit potential. relative mispricing. We will describe the underlying rationale and examples of such trades in detail in one of the subsequent sections.  

![](25f1a8702ab47715b981324cb2abfaf5b2e97026d0961ce8b9e25df8a25cdf0b.jpg)  
Goldman Sachs CDS versus share price (2007-2014, weekly frequency)  

# FIGURE 19.3  

Goldman Sachs CDS versus share price (2007-2014).  

# 19.4.3 PROBABILITY OF DEFAULT  

One of the uses of Merton models in practice is as an indicator of default risk. The Merton model can be used to calculate the option implied risk-neutral probability of default, that is the risk-neutral probability that $A_{T}{<}F$ . The risk-neutral probability of default is the probability that the put finishes in-the-money. The probability of default can be calculated as follows:  

$$
\mathrm{Probability~of~Default}=P(A_{T}<F)=N(-d_{2})
$$  

In the risk-neutral world, the drift of the firm value process is the risk-free rate $r.$ Note that under. the stochastic process in Eq. (19.12) for $A_{t}$ the real-world probability of default is the probability that $A_{T}{<}F$ given that $A_{t}$ has a drift $\mu$ and a volatility $\sigma$ . The drifts $\mu$ and $r$ may be different.. Therefore, the risk-neutral probability of default in Eq. (19.24) may differ from the actual probabil-. ity of default. On the one hand, if $\mu>r$ , the firm value in the real world drifts upwards faster than in the risk-neutral world, which implies that the real-world probability of default would be lower. than the risk-neutral probability. On the other hand, if $\mu<r$ the real-world probability of default would be higher than the risk-neutral probability of default. It is possible to derive closed-form solu-. tions for the actual probability of default from the risk-neutral probability. Typically $\mu>r$ and therefore the real-world probability is below the risk-neutral probability. We can interpret the higher. risk-neutral probability as consisting of the real-world probability plus a risk premium for uncertainty regarding the timing and magnitude of default. Note that in the basic Merton model, there is. no uncertainty considering the timing which is not realistic.  

The following example illustrates the application of the Merton model.  

# EXAMPLE  

We assume that the value and volatility of assets is given and our objective is to calculate the current market value of equity and debt as well as the implied credit spread and default probability. Table 19.1 shows the input parameters.  

<html><body><table><tr><td colspan="2">Table 19.1 Input Parameters for Merton Model Example</td></tr><tr><td>Parameter</td><td>Value</td></tr><tr><td>Asset/firm value (At)</td><td>100</td></tr><tr><td>Face value of the debt (F)</td><td>75</td></tr><tr><td>Maturity (T)</td><td>1</td></tr><tr><td>(Riskless)interestrate</td><td>2%</td></tr><tr><td>Assetvolatility(o)</td><td>20%</td></tr></table></body></html>  

If we apply Eq. (19.15) to calculate the price of the equity $E_{O}$ at date $t=0$ we obtain a value of. $E_{O}=26.84$ . Similarly, according to Eq. (19.16) the market value of debt is 73.16. The implied yield to maturity of the risky debt based on Eq. (19.18) is $2.49\%$ and the resulting credit spread is 49.. The value of the riskless debt is 73.51 and the difference between the value of the riskless debt and the risk debt is the value of put, which is 0.36. The default probability is given by Eq. (19.24) and is equal to $3.46\%$ in this example.9  

# 19.4.4 APPLICATION OF THE MERTON MODEL AND EQUITY-TO-CREDIT APPROACH  

As Eq. (19.15) shows, structural models such as the Merton model are based on the unobserved variable $A_{t}$ For publicly traded companies, the share price and therefore the equity value is observ-. able in the market. The usual approach to estimating the value of the firm's assets $A_{t}$ and their volatility $\sigma_{A}$ is to use Eq. (19.13) together with another equation that links the value and volatility of equity to the value and volatility of assets. If we apply Ito's formula to Eq. (19.15), we obtain:  

$$
E_{t}\sigma_{E}=A_{t}\sigma_{A}{\frac{\partial E}{\partial A}}=N(d_{1})\sigma_{V}V_{t}
$$  

Equations (19.15) and (19.25) represent a pair of simultaneous equations that can be solved for. $A_{t}$ and $\sigma_{A}$ .Once we calculate $A_{t}$ and $\sigma_{A}$ it is also possible to calculate the probability of default. $N(-d_{2})$ based on Eq. (19.24). We can also obtain the market value of the debt which is equal to. $A_{t}-E_{t}$ . By comparing the current model implied market value to the present value of the promised debt payment, we can calculate the expected loss (EL). The end of chapter exercises provide a numerical example of an application of this approach.  

One of the first firms to use Merton-type models in practice to estimate probabilities of default. of a debt issuer from share price data and the firm's capital structure data was KMV (now Moody's  

KMV) in the 1980s. This approach is sometimes also referred to as equity-to-credit and its advantage over credit ratings is that it is based on real-time data from liquid markets. This makes it particularly useful for predicting defaults. Default probabilities derived from credit ratings issued by credit rating agencies on the other hand are updated relatively infrequently and there are many examples when large publicly listed companies were only downgraded by credit rating agencies. after the companies had filed for bankruptcy and defaulted on their debt. Default probabilities can also be obtained from other sources. Four other potential sources of such information are (i) credit ratings, (ii) historical default rates, (ii) credit spreads implied by publicly traded bonds, and (iv) credit spreads implied by CDS. Merton-type models should therefore be viewed as complementing rather than replacing other models and approaches when investment decisions are taken.. Although Merton-type models are popular in credit markets, market participants still continue to use other fundamental and quantitative tools instead of purely relying on the outputs of structural models. Sometimes structural models are viewed as useful for understanding the sources of risk, while other classes of models can be useful for predicting market values of bonds and equities. Merton-type models are used by many institutional asset managers to understand how, for example corporate bonds will perform, in different asset volatility scenarios. However, ultimately decisions are made by taking into account information from all models..  

# 19.4.5 ASSUMPTIONS OF THE MERTON MODEL AND EXTENSIONS  

The basic Merton model that we reviewed above has been extended significantly by both practitioners and academics over the last 40 years. Many of the more recent and advanced structural models implemented in practice are proprietary and there is no public information about their underlying assumptions. Published academic research has, however, also developed more complex structural models of default that fit the stylized empirical facts better than the basic model.  

# 19.4.5.1 Extensions in published academic research  

As part of the introduction of the basic Merton model, we mentioned a range of simplifying assumptions that the basic model is based on. For reasons of space, the list of assumptions provided above is incomplete. Sundaresan (2013) provides a comprehensive review of the basic Merton model, its. assumptions and how subsequent structural models of default have relaxed these assumptions to fit. stylized empirical facts better. One of the assumptions that is used in almost all papers in this literature is that trading in assets takes place continuously. Clearly this is an unrealistic assumption for all firms and all assets. While some very liquid exchange traded assets can be viewed to a first-order approximation as exhibiting continuous trading, the physical assets of many firms are very illiquid. and no market may exist for some of them. In fact, the value of the firm's assets and its parameters are not even directly observable. The extensions that have been incorporated in richer, more complex structural models of default include (a) agency costs, (b) moral hazard, (c) bankruptcy codes, (d) renegotiations, (e) investments, (f) taxes, (g) jumps in the stochastic process followed by firm. value, and (h) the dependence of default probabilities on the business cycle.  

# 19.4.5.2 Evolution of structural models of default in industry  

Although the details of models used by practitioners are not known, some published accounts indi-. cate that several of the extensions such as (a)-(h) mentioned in the previous section have been incorporated into such models. Even the original KMV model developed in the 1980s contained some significant differences compared to the basic Merton model since it scaled the distance to default obtained from the basic Merton model to actual default probabilities using a proprietary default database.1o Many software vendors, banks, and other private sector institutions developed their own Merton-type models. While the focus of early versions of the KMV model was on default probabilities, the development of credit derivatives markets in the 1990s led the industry to develop structural models of default to estimate bond and CDS spreads. One such example was CreditGrades launched by the Riskmetrics group (now part of MSCI) in 2002. The original CreditGrades model was based on the Black-Cox model, which relaxes some of the assumptions of the basic Merton model to allow default to occur prior to time $T$ if the value of the firm's assets hit a predetermined default barrier. Models such as CreditGrades can generate theoretical (model-implied) CDS spreads and various Greeks. In practice, to produce realistic credit spreads and default probabilities, contemporary models have been extended to include such variables as convertible debt, preferred equity, and so on. One of the challenges of applying standard Merton-type models is that the capital structure of a company can suddenly change. It may be possible to use the model to state whether the equity is correctly priced relative to the credit for the current capital structure but it is almost impossible to reliably forecast how the capital structure will change in the future. For example, it is very difficult to predict when the capital structure will change due to a management decision. Consider the situation of a capital structure arbitrage fund that has a long credit position and a short equity position on the company. What would happen if the company unexpectedly carries out a leveraged buyout? The likely result is that the position will lose money as a result. Some arbitrageurs trade equity and credit to express a view about expected future changes in a company's capital structure.  

The paragraph above discusses the usefulness of Merton-type models for capital structure arbitrage strategies. We will introduce these strategies in the following section..  
