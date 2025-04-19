---
tags:
  - equity_derivatives
  - libor_model
  - reverse_convertibles
  - structured_products
  - volatility_trading
aliases:
  - Conclusions
  - Reverse Convertibles
  - Volatility Trading
key_concepts:
  - equity structured products
  - high stock index volatility
  - reverse convertible bond
  - stochastic volatility model
  - structured product trading
---

# 20.5 CONCLUSIONS  

We close this chapter with a comment on modeling structured products. Which model to use and how to calibrate the chosen models is clearly a crucial component of structured product trading. The structurer cannot buy these products in the wholesale market. The products need to be manufactured in-house. This requires extensive pricing and hedging efforts that will often depend on the model one is working with.  

In equity structured products, versions of the stochastic volatility model are found to be quite effective and are widely used. For fixed-income versions of the forward LIBOR model that incorporate some volatility, smile needs to be used.  

# SUGGESTED READING  

For LIBOR exotics consider Piterbarg (2005) and Andersen and Piterbarg (2010). Wystup (2006) is recommended for FX structured products. For the new equity structured products, Gatheral (2010) is required reading.  

# EXERCISES  

1. Case Study: Reverse-Convertibles and Volatility Trading  

This case study shows another example of volatility trading and reverse convertibles. Read the case study below and answer the following questions.  

a. What is a reverse-convertible bond? How would you decompose this instrument? How would a corporate treasurer use reverse-convertible bonds?.   
b. How are the market professionals using reverse-convertibles? Why is there a "flood'?.   
c.What is a synthetic convertible?.   
d. What is the other solution mentioned in the text? What are the possible risks behind this. solution?  

e. Finally, the regulators. Consider the case of French regulators and reverse-convertible bonds. Why would the regulators have an issue with these products? Do you think this is justified? Discuss briefly.  

Reverse convertibles activity soared to new heights last week, driven by sustained high stock index volatility.   
levels across Europe and stock market jitters. Warrant professionals highlighted the increasing number of   
structuring banks involved in the sector and the broadening range of issuance currencies.. These factors were evidence, they said, of the product's growing acceptance throughout the industry.   
Stock index volatilities across Europe have consistently been in the high twenties of percentage points since   
the beginning of the year. Explaining the sudden surge in demand, equity derivatives professionals said reverse convertibles were an   
ideal means of taking advantage of current high volatility rates throughout Europe. Others said interest in the product was spreading across Europe, whereas it had previously been confined   
to Switzerland and Germany. "There's been a flood. It's all over the place," enthused one German bank   
derivatives official. Reverse convertibles are credit products with an embedded put option referenced to a particular quoted   
company stock. The face value of the bond is discounted to the equivalent value of the option premium. If the   
stock price breaches a certain minimum value threshold, the bond investor receives equity instead of a cash   
payout. Credit Lyonnais Equity Derivatives was in the thick of the action, structuring three deals. Volkswagen was   
chosen as the underlying for an issue paying a $I O\%$ coupon; Telecom Italia was selected as the reference   
stock for an issue paying an $1I\%$ coupon; and ABN AMRO was the reference for a third. If the stock price on the final date is greater than or equal to $95\%$ of the initial price, then the   
investor receives $100\%$ cash redemption. But if the price is below, then the investor receives one.  

physical.  

Thomson Reuters IFR, June 1998  

2. Consider the swap and LIBOR curves available in Reuters or Bloomberg.  

a. Obtain the 3-month discount and forward curves   
b. Obtain the 2-year forward curve   
c. Find the components for the following note: maturity: 3 years Callable: each coupon payment date Payments: annual Coupons: Year $1\colon R_{1}$ Year 2: $\alpha_{1}\times(2$ -year CMS) $^+$ previous coupon Year 3: $\alpha_{2}\times$ (2-year CMS) $^+$ previous coupon   
Determine the unknowns $R_{1}$ $\phantom{}_{1},\phantom{}\alpha_{1},\phantom{}\alpha_{2}$   
d. Find the components for the following note: Maturity: 3 years Callable: each coupon payment date Payments: annual Coupons: Year $1\colon{\mathsf{R}}_{1}$ Year 2: $x\times[(3\mathrm{-year~CMS})-(2\mathrm{-year~CMS})]+\beta_{1}$ Year 3: $x\times[(3\mathrm{-year~CMS})-(2\mathrm{-year~CMS})]+\beta_{2}$   
Determine the unknowns $R_{1},\alpha,\beta_{i}$   
e. In the latter case, when would $\beta_{1}=\beta_{2}\gamma$  

3. What follows is the description of a rather complex swap structured by a bank. The structure. is sold for the purpose of liability management and involves an exotic option (digital cap) and a CMS component.  

At time O the bank and the client agree to exchange cash flows semiannually for 5 years according to the following rules:.  

The bank pays semiannually, 6m-LIBOR on the notional amount. This is a vanilla swap. The client pays a coupon $c_{t}$ according to the following formula:  

$$
c_{t}=c_{1t}-c_{2t}
$$  

where  

$$
c_{1t}=\left\{\begin{array}{l l}{\mathrm{LIBOR}+47\mathrm{bp}\%}&{\mathrm{if}\quad\mathrm{LIBOR}<4.85\%}\ {5.23\%}&{\mathrm{if}\quad4.85\%<\mathrm{LIBOR}<6.13\%}\ {2.98\%}&{\mathrm{if}\quad\mathrm{LIBOR}>6.13\%}\ {c_{2t}=\{\mathrm{cms}(30Y)-(\mathrm{cms}(10Y)+198\mathrm{bp})\}}\end{array}\right.
$$  

for the first 2 years. And  

$$
c_{2t}=8\{\cos(30Y)-(\cos(10Y)+198~\mathrm{bp})\}
$$  

for the last 3 years.  

a. Unbundle this LIBOR exotic into vanilla products the best you can. b. Why would an investor demand this product? What would be his or her expectations?  

Show how you would engineer the following Snowball Note.   
Issuer: ABC bank   
Notional: $\$10$ mio   
Tenor: 10 years; Principal: Guaranteed at maturity.   
Coupon: Yr 1; Q1: $9.00\%$   
Q2: Previous Coupon $+\mathrm{CMS}104.65\%$   
Q3: Previous Coupon $+\mathrm{CMS}104.85\%$   
Q4: Previous $\mathrm{Coupon+CMS10}5.25\%$   
Yr 2 Q1: Previous $\mathrm{Coupon+CMS10}5.45\%$   
Yr 2 Q2-Q4: Previous $\mathrm{Coupon+CMS10}5.65\%$   
Yr 3: Previous $\mathrm{Coupon+CMS10}5.75\%$   
Yr 410: Previous Coupon   
Coupon subject to a minimum of. $0\%$   
Call: Callable on each coupon   
a.What is the view of the investor?.   
b. What are the risks?   
c. Now forget about the call provision and calculate the coupons paid under the two following realizations of LIBOR rates:   
Realization $1=5.0$ , 6.0, 6.5, 7.0, 8.0, 9.0, 10.0   
Realization $2={\mathrm{LIBOR}}$ stays at 3.5   
d. How can you characterize these coupons using a swap? What type of swap is this?.   
e. Suppose you have 8 annual FRAs quoted to you. How can you price these coupon payments?   
f. How do you generate the first-year coupon?   
g.Are the coupons floored at 0?   
h. Write a contractual equation representing this instrument.  

5. Show how you would engineer the following CMS spread note Issuer: ABC Notional: $\$100$ Tenor: 10 years Principal: Guaranteed at maturity Coupon: Yr 1: $11.50\%$ Yr 2- $10\colon16\times(\mathbf{CMS}30-\mathbf{CMS}10)$ , max of $30\%$ , min $0\%$ Call: Callable on each coupon date by the issuer. a. What is the view of the investor? b.What are the risks?  

This page intentionally left blank  

# SECURITIZATION, ABSs, CDOs, AND CREDIT STRUCTURED PRODUCTS  

# 21  

# :HAPTER OUTLINE  

21.1 Introduction. 740   
21.2 Financial Engineering of Securitization .... .740   
21.2.1 Choosing Cash Flows 741   
21.2.2 The Critical Step: Securing the Cash Flow . 742   
21.2.3 Some Comparisons... 743   
21.2.3.1 Loan sales. 743   
21.2.3.2 Secured lending 744   
21.3 ABSs Versus CDOs... .745   
21.3.1 Tranches and Some Securitization History . 746   
21.3.2 A Comparison of ABSs and CDOs.. 747   
21.3.2.1 Credit indices 748   
21.3.2.2 Synthetic CDOs. . 748   
21.4 A Setup for Credit Indices.... .750   
21.5 Index Arbitrage 754   
21.5.1 Real-World Complications 754   
21.5.2 Credit Skew Trade.. 755   
21.6 Tranches: Standard and Bespoke. .756   
21.7 Tranche Modeling and Pricing. .757   
21.7.1 A Mechanical View of the Tranches. 758   
21.7.2 Tranche Values and the Default Distribution. 759   
21.8 The Roll and the Implications . .762   
21.8.1 Roll and Default Risk.. 763   
21.9 Regulation, Credit Risk Management, and Tranche Pricing. .764   
21.9.1 Credit Risk Management, Default Losses, and Mark-to-Market Losses. 764   
21.9.2 Capital Requirements and CD0 Activity. 765   
21.9.3 Lessons from the GFC, Post-GFC Capital Regulation and the Securitization Market .. 766   
21.9.4 Can Securitization Cure Cancer? 767   
21.10 New Index Markets .767   
21.10.1 The ABX Index 768   
21.1O.2 The LCDS, LCDX. 768   
21.10.2.1 Cancelability. 769   
21.10.2.2 Quoting conventions. 769   
1 Structured Credit Products.... 769   
21.11.1 Credit Options. 769   
21.11.2 Forward Start CDOs. 770   
21.11.3 The CMDS. 770   
21.11.4 Leveraged Super Senior Notes.. 772   
21.11.5 CoCos. 773   
21.11.5.1 Cocos versus convertible bonds. 773   
21.11.5.2 Valuation of CoCos. 774   
21.11.5.3 The outlook for CoCos. 775   
21.12 Conclusions.. 776   
Suggested Reading . .776   
Exercises ... 777  

MATLAB Exercise. 780  
