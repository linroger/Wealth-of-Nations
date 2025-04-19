---
tags:
  - cdo_pricing
  - credit_derivatives
  - credit_spreads
  - default_correlation
  - synthetic_cdo
aliases:
  - CDO Loss Analysis
  - CDO Tranche Pricing
  - Synthetic CDO Analysis
key_concepts:
  - CDS spreads
  - Credit derivative market
  - Rising default correlation
  - Synthetic CDO growth
  - Tranche pricing and loss
---

# 10.4  SYNTHETIC CDO TRANCHE PRICING AND LOSS ANALYSIS  

The first decade of 2000s ushered in an explosive growth of synthetic CDOs. The search for yield and risk diversification drove investors to accept exposure to new assets. For example,. European banks sought exposure to US mortgage assets. The credit derivative market was mature enough to absorb this and make markets in a variety of credits and structures. The demand for exposure drove the CDS spreads often higher than the credit spreads in corporate and sovereign bond markets. Synthetics also allowed the customization of credits and cash flows. The one thing that was not predicted by the yield-hungry investors was the risk of the rising correlation of defaults due to systemic risk. It is very instructive to analyze a typical setup of a synthetic CDO, its initial pricing, and the change in tranche pricing and loss exposure. as CDS spreads widened.  

# 10.4.1 Synthetic CDO Revisited  

Figure 10.7 shows an example of a $\$500$ million synthetic CDO structure with a $\$415$ million super-senior unfunded tranche and six investment tranches totaling $\$85$ million principal and ranging from AAA rating all the way down to the unrated equity tranche. The tranches are issued as credit-linked notes (CLNs).  

The CDO-issuing SPV enters into a $\$500$ million cash-settled CDS agreement with a third party (typically a sponsoring investment bank) selling it credit protection on a portfolio of 100 credits (equivalent to 100 individual CDS). The periodic premium received is to serve as the spread on the coupons paid to the CDO tranche holders. This spread is what the investors are seeking. Presumably, it is higher than what they could obtain in the corporate bond market on equivalent credits.  

The SPV receives $\$85$ million for the CLN tranches. This principal money is not used to buy. the underlying corporate bonds or loans as in the cash CDO, but it is deposited into a credit. support account invested in US Treasuries. It is to be used to absorb any losses coming from defaults. The CLN tranches are hit in the reverse order of seniority, with the first default losses reducing and then wiping out the equity tranche (first. $2\%$ of the collateral defaulting), then the mezzanine (BBB-) tranche (the next $2\%$ defaulting), and then investment grade tranches (the next $13\%$ defaulting). The super-senior tranche holders are the most protected. They have not put any money into the structure, they simply collect some of the CDS premium, and fully $\$85$ million of losses ( $17\%$ of the collateral principal) have to occur before they start making payments on their CDS. Their main risk is the exposure to losses in excess of $\$85$ million in exchange for the CDS premium per $\$1$ of insured collateral that is lower than the original CDS premium received by the SPV. This is due to their "better-than-AAA' status delivered by the protection cushion of the junior tranches.  

![](94dcfac8182184b589a76090556496ac997b31f92ae45efc76cc9c29e65de935.jpg)  
Figure 10.7 A super-senior synthetic CDO  

# 10.4.2 Synthetic CDO Pricing and Expected Loss  

To understand the pricing of the synthetic CDO, let us consider the simple constant probability of default model introduced in Section 7.2 of Chapter 7. Let $p=0.08$ be the one-period (conditional) probability of default and $q=1-p=0.92$ be the one-period (conditional) survival probability. Let us also posit a constant recovery rate $R=0.4$ . Figure 10.8 shows the last step of a pricing tree for a credit sensitive discount bond..  

Consider that last step portrayed by solid lines. If we assume no discounting, then the price of the discount bond is equal to the expected value of the payoff,. $\$100$ with probability 0.92 and $\$40$ with probability 0.08:  

$$
P=\mathbb{5}100\times(q+R\times p)=\mathbb{5}100\times(0.92+0.4\times0.08)=\mathbb{5}95.20
$$  

By arbitrage, the price of a 1-year CDS on the discount bond must be $\$4.80$ . To replicate a riskless discount bond paying off $\$100$ for certain, one can buy the risky discount bond for $\$95.20$ and spend $\$4.80$ to insure it. If the risky bond does not default, then the $\$95.20$ investment turns into $\$100$ , and the insurance expires. If the risky bond defaults, then the $\$95.20$ investment turns into $\$40$ , but the insurance pays $\$100\times(1-R)=\S60$ We can thus interpret the $\$4.80$ cost of the insurance equal to. $4.8\%$ of the face value as the risk-neutral. credit spread on the bond (here in discount yield terms). It is important to note that the credit spread is also equal to the expected risk-neutral loss on the bond. If we define the loss as the loss of principal, then it is equal to zero in the survival state with probability $q=0.92$ , and equal to $\$100\times(1-R)=\S60$ with probability $p=0.08$ . In general,  

![](5a5e1691b4a07f1f70fd3bf6386321091f7d4236fca1e8a2c5a0114e1284efa9.jpg)  
Figure 10.8 A discount bond subject to constant probability of default  

$$
E\left[L o s s\right]=\S100\times p\times(1-R)
$$  

In order to extend the expected loss discussion to a multi-period pricing tree, let us dis-. tinguish between the conditional and the cumulative probabilities of default. The conditional. probability of default over period. $n$ , denoted $p(n-1,n)$ , is defined as the probability of. default in period $n$ conditional on surviving (not defaulting) in previous. $n-1$ periods. The cumulative probability of default over. $n$ periods, denoted $p(0,n)$ , is the probability of default between now, time zero, and the end of period $n$ . Consider the dashed lines in Figure 10.8. representing the second-to-last step of a multi-period tree. In the Figure, both conditional default probabilities are the same and equal to $8\%$ , or  

$$
p\left(0,1\right)=p\left(1,2\right)=0.08
$$  

The cumulative probability of default over two periods between now and the end of period 2 is:  

$$
p\left(0,2\right)=p\left(0,1\right)+[1-p\left(0,1\right)]\times p\left(1,2\right)=0.08+0.92\times0.08=0.1536
$$  

In a general multi-period model, we are typically able to bootstrap the term structure of corporate spreads for any given credit (from corporate bonds or CDSs). As with interest rates, we can recover "zero"' spreads or forward spreads, i.e. those charged on a CDS between now and $n$ periods from now, and those for each forward period. Let us denote the former, which is how CDSs are normally quoted, by $s(0,n)$ . Assuming a constant recovery $R$ , we can generalize our one-step example to the following formula for the cumulative default probability:.  

$$
p\left(0,n\right)=\frac{1-\displaystyle\frac{1}{\left[1+s\left(0,n\right)\right]^{n}}}{1-R}
$$  

For example, using this formula, an annualized spread of $0.5\%$ with a recovery rate of 40 cents on the dollar translates into the cumulative probability of default over 5 years of $4.1\%$  

![](3cd4a0b0becda609a0e5b96954053da8e3fc35634998a3cd59189e2ca06e588e.jpg)  
Figure 10.9 Loss rate distribution for $\rho=0$ , 0.5 and 0.95  

Given the cumulative probabilities, we can recursively back out the conditional probabilities using the equation for our two-step example and solving for $p\left(1,2\right)$ . Once we have the entire conditional probability tree, we can compute the expected loss assuming a deterministic recovery rate.  

# 10.4.3 Synthetic CDO - Loss Rates, Ratings and the Crisis of 2008  

With a little bit of work, one can extend the constant probability of default model for one credit to a Gaussian copula approach with multiple credits. After all, what determines default losses is imply the cumulative joint probability distribution. The default loss behavior of the CDO collateral depends critically on the correlation of defaults.  

Figure 10.9 shows the distribution of loss rates under correlation assumptions of 0.0, 0.50, and 0.95. The loss rate is defined as the total loss over a 5-year period as a percentage of the total CDO principal. We superimpose the loss absorption thresholds for the different CDO tranches.  

When the correlation is zero, the loss distribution centers around its mean and losses higher than $10\%$ are unlikely (tail probability less than 0.005). As the correlation increases, multiple. defaults become more likely and so do higher total losses (fatter right tail). Small losses also become more likely (fatter left tail). When the correlation is very high, the distribution becomes almost binomial, either all assets default together or none defaults. The distribution is dictated by the lowest probability assets. The probability of a zero loss is about 2/3, but there is a non-zero probability of very high losses over $50\%$ . What this implies for the different tranches is that, at zero correlation, even the ${\tt B B+}$ tranche has a high cumulative probability of principal losses, while the S-AAA tranche may remain intact. However, as the correlation.  

increases, the loss on the mezzanine tranches BBB- and ${\tt B B+}$ becomes less likely, but the probability of losses for the super-senior tranche increases from near zero to above $5\%$ and close to $10\%$  

This last observation is the crux of the 2008 crisis of defaults of senior sub-prime mortgagebacked CDOs. They had been structured with a view of low correlation of defaults: some. homeowners were supposed to default while some were not. This would have created the situation where the junior tranches would have absorbed all the losses from the least cred-. itworthy homeowners. However, as correlations increased dramatically and all homeowners started to default at the same time (or at least the perception of that likelihood increased),. the losses spread to the super-senior tranches of the CDOs. Instead of accepting near zero spread on their tranches, the senior holders should have demanded spreads in excess of. 50 bp per annum to compensate them for the loss of market value due to higher correlation of defaults.  

Most rating models of CDOs tranches have been inadequate. From the pronouncements by the S&P one could guess that their approach was based on the riskiest-credit-in-the-basket principle. This implies that the first-to-default baskets and the junior tranches of a CDO. are assigned the credit rating of the weakest names in the pool. This also implies a view that weakest credits always default first. Clearly that has to understate the total cumulative. probability of default. Moody's approach was to not only include the probability of default but also to run all structures through expected loss scenarios. While this may have appeared to be an improvement, since one added to the probability analysis the dimension of the severity of. the loss, in reality it was not. If the recovery rates and default losses were simulated to match observed spreads or historical levels, then they also severely underestimated the cumulative defaults.  
