---
tags:
  - cds_pricing
  - default_correlation
  - joint_probability
  - protection_seller
  - reference_issuer
aliases:
  - CDS Default
  - Joint Default Probability
  - Protection Seller Default
key_concepts:
  - CDS premium and credit quality
  - Conditional default probability
  - Default correlation reference issuer
  - Joint default probability modeling
  - Protection seller default risk
---

# 7.5 THE DEFAULT CORRELATION OF THE REFERENCE ISSUER AND THE PROTECTION SELLER  

The arbitrage argument of Section 7.1.2 breaks down in the presence of the possibility of default by the protection seller. Financing the purchase of a corporate bond at LIBOR and buying CDS protection on the bond do not produce a risk-free bond if the protection seller can default. The arbitrage argument turns into an inequality. The premium charged can be at most equal to the LIBOR margin, equal if the protection seller were a default-free sovereign, and strictly lower otherwise.' Intuitively, the higher the credit quality of the protection seller, the closer the CDS premium can get to the corporate spread of the issuer. In general, what matters is the joint distribution of defaults of the reference issuer and the protection seller. Modeling this joint distribution parametrically is generally quite difficult. Only marginal normal distributions can be naturally combined into multivariate normals. Fitting a univariate Poisson to obtain a term structure of intensity parameters $\lambda$ for a given corporate does not easily combine with a separate marginal Poisson fitting for the protection seller. However, one way to do it is to specify the correlation of defaults implicitly through joint and conditional probabilities.  

Following the logic of Chen and Sopranzetti (2002), let us assume a joint Bernoulli set-up for defaults of the reference issuer ABC and the protection seller PS. We denote the random variables  

$$
X_{A B C}=\left\{\begin{array}{c c c}{{0,}}&{{\mathrm{if~no~default}}}&{{\mathrm{and}}}&{{X_{P S}=\left\{\begin{array}{l l}{{0,}}&{{\mathrm{if~no~default}}}\ {{1,}}&{{\mathrm{if~default}}}\end{array}\right.}}\end{array}\right.
$$  

and the joint probability of defaults as in Table 7.7.  

The marginal probability of default of the reference issuer ABC is $P(X_{A B C}=1)=p_{A B C}=$ 0.15 and the marginal probability of default of the protection seller PS is. $P\left(X_{P S}=1\right)=$ $p_{P S}=0.1$ . Using the basic mathematical probability definitions in Hogg and Craig (1978),. the means and variances of the two Bernoulli random variables are:  

$$
\mu_{A B C}=p_{A B C}=0.15,\quad\sigma_{A B C}^{2}=p_{A B C}(1-p_{A B C})=0.1275,
$$  

and  

$$
\mu_{P S}=p_{P S}=0.10,\quad\sigma_{P S}^{2}=p_{P S}(1-p_{P S})=0.09
$$  

Dropping the zero terms, we can compute the covariance of defaults  

$$
\begin{array}{c}{{E\left[\left(X_{A B C}-\mu_{A B C}\right)\left(X_{P S}-\mu_{P S}\right)\right]=E\left[X_{A B C}X_{P S}\right]-\mu_{A B C}\mu_{P S}}}\ {{{}}}\ {{=1\times1\times0.05-0.15\times0.1=0.035}}\end{array}
$$  

and, finally, the unconditional correlation coefficient  

$$
\rho={\frac{0.035}{{\sqrt{0.1275}}\times{\sqrt{0.09}}}}=0.3267
$$  

The unconditional correlation coefficient is rather unintuitive. The more relevant quantity from the perspective of the protection buyer may be the conditional probability of the protection seller's default, given that the reference issue has defaulted, that is  

$$
P\left(X_{P S}=1|X_{A B C}=1\right)=\frac{P\left(X_{P S}=1\cap X_{A B C}=1\right)}{P\left(X_{A B C}=1\right)}=\frac{0.05}{0.15}=\frac{1}{3}
$$  

The probability that the protection buyer will not receive the payment when it is due -- that is the insurer will default when the insurance is needed - is 1/3.  

The pricing of the CDS in this set-up follows the logic of Figure 7.9, i.e. of matching. the probability-weighted discounted payoff to the probability-weighted discounted premium,. but in a multinomial set-up. We don't show it here, as this set-up is rarely used for the following two reasons. First, suppose that the protection seller and the protection buyer are both large institutional CDS dealers - both defaultable entities. Therefore, the seller in setting the premium would have to take into account that the buyer may also default on the premium payments. In theory, we then have to take into account the joint distribution of three parties: the reference issuer, the protection seller, and the protection buyer. However, the positions of the seller and buyer in the CDS contract are not the same. The protection buyer will only default if he is not due any payoff. The seller then should ignore the probability of the default by the buyer and should charge a full premium assuming there will be no buyer default. However, this argument also breaks down since the ISDA master documents provide for the netting of the derivative contracts. This argues in favor of ignoring both buyer and seller defaults in the calculation of the CDS spreads as long as there is no large imbalance of the supply and demand. of the contracts, i.e. they are not all sold by the same dealer. In that case, the buyers face the average credit quality of the entire dealer community, similar to swap pricing at LIBOR flat, irrespective of the relative credit quality among the participating dealers. The only argument that survives is whether the CDS premiums should be equal to or lower than the corporate spread on the reference issue.  

The second reason why the correlation model proposed in this section is not strictly followed is that, given the reality of the CDS market, it is much more important for the dealers to try. to model the joint multivariate distribution of corporate credits in their bond, loan and CDS portfolios. The marginal $\lambda$ fitting and Poisson pricing of single-issuer CDSs is a boundary. condition, but the joint distribution modeling allows the pricing of basket credit derivatives and the risk management of the entire portfolios of the credit derivative contracts. We defer the multivariate copula-based modeling till Chapter 10..  

Structured finance is a very broad term encompassing any complicated cash flow arrangement between two or more parties. The arrangement often involves contingent payouts that may be. event-driven or at the discretion of one the parties involved. In corporate securities, a callable or a convertible bond, and convertible preferred or hybrid debt, might peripherally fall under this description. Many lease and swap arrangements would also fit this description. However, we will apply the term structured finance in a narrower sense..  

A structured security typically takes the form of debt. It is issued as a note or a bond and has a non-standard coupon or principal redemption definition. Often the coupon is fixed and the principal formula is tied to the performance of another asset, the principal is fixed and the coupon is tied to the performance of another asset, or both. The formula of the bond's coupon or principal can depend on the performance of a stock index, commodity, currency,. or the movement of interest rates. The performance of the reference asset can be directly part of the formula, e.g. coupon of $3\%$ plus $70\%$ of the appreciation in the S&P 500 index,. or the payment may be contingent on the asset reaching a level or being in the range, e.g.. daily coupon of. $5\%$ p.a. but accrued only for days when LIBOR is between. $1\%$ and $3.5\%$ The payout formula may also be tied to the performance of non-asset economic or event variables, e.g. inflation, GDP, or catastrophic events like hurricane damage. In general, one sees three types of structured securities in terms of design intent: capital (principal) protected (where the holder will get at least the full principal back), yield enhanced (where the coupon formula offer "additions' tied to other assets), and income structures. While common, this is not a very good classification, since the designer of the security can easily shift cash flows between coupon and principal. Legally, principal and coupon may be distinct, but practically they are just arbitrarily defined cash flows. We will attempt a different classification in the next section.  

Structured notes have traditionally been put together by large broker-dealers and banks and sold to institutional investors. The issuers have been either sovereigns and corporates, or special purpose vehicle (SPV) trusts. In either case, the structuring dealers would enter into a set of derivative (swap plus option) transactions with the issuer. The purpose of these. derivatives would be to pay to the sovereign, corporate, or the SPV the coupon or principal formula which would then be passed on to the investor. More recently, structured notes entered the retail market through two channels: electronically traded notes (ETNs) and structured bank. deposits. An ETN is a structured note that trades on a stock exchange like a regular stock. The main advantage of an ETN form is its liquidity. While the ETN has all the features of a structured bond (periodic cash flow tied to the performance of an equity index or a commodity, and may have a stated maturity or be a rollover structure), the retail investor can trade in and. out of it with much more ease. Many banks have also started offering deposit accounts whose interest accrual calculation is tied to the performance of equities, currencies, or commodities. Usually these are renewable term deposits (like CDs with stated maturities) or the interest formula is applied at regular calendar intervals (pay the percentage interest equal to the S&P 500 appreciation for the calendar quarter).  

Structured finance is the subject of this and the next two chapters. The latter cover specialized areas of mortgage-backed securities (MBSs) and collateralized debt obligations (CDOs). The special features there are the pooling of credit risk and the tranching of cash flows. Other markets that share the credit risk pooling feature are generally all asset-backed securities (ABSs), like bonds backed by consumer credit card receipts, car and student loans, etc. All ABSs, including MBSs and CDOs, are structured with the use of an SPV trust that holds the underlying risky loans or bonds, and issues pass-through certificates entitling the holder to the proportional share of the coupon cash flow (similar to a mutual fund design) which is fixed and equal to the weighted average of all the coupon flows received by the trust. Those pass-through certificates can then be pooled and, with the use of another SPV, be spliced (tranched) into several classes of certificates with unequal rights to the cash flows..  

In this chapter, we focus on the rest of structured notes trading in the financial markets, most of which are not tranched, and whose coupon and principal are often not simple weighted average pass-through quantities, but are specifically designed to depend on other economic. variables to meet the investors' demand for risk. We start with a general consideration of the purpose of structured finance, followed by the examples of the main three types and a discussion of the design and valuation issues..  
