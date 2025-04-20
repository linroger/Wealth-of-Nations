---
tags:
  - credit_default_swaps
  - credit_risk
  - derivative_contract
  - market_standard
  - valuation_model
aliases:
  - CDS Valuation
  - Credit Derivatives
  - O'Kane & Turnbull
key_concepts:
  - Credit default swap
  - Credit event
  - Market standard model
  - Protection buyer/seller
  - Trading credit risk
---

# Valuation of Credit Default Swaps

We present the market standard pricing model for marking credit default swap positions to market. Our aim is first to explain why credit default swaps require a valuation model, and then to explain the standard model - the one most widely used in the market. In the process of setting out the model, we take care to explain and justify the various modeling assumptions made. We also provide examples.  

# 1 INTRODUCTION 1  

The credit default swap is a simple derivative contract that has revolutionized the trading of credit risk. Over the past five years it has become the most widely used credit derivative product, representing about $72.5\%$ of a total outstanding market notional currently estimated to be around $\$2.3$ trillion?. The default swap market is truly global, with contracts linked to the credit risk of a wide array of US, European and Asian corporate names as well as to a number of sovereigns.  

The point of this paper is to present a complete and practical exposition of the market standard model and so help those new to credit derivatives to be able to value default swap positions. We intend to publish a more complete study of the valuation and risk management of credit default swaps shortly and we refer the reader to that for many of the technical details omitted from this abridged paper.  

# 2 THE CREDIT DEFAULT SWAP  

Credit default swaps (CDS) have been explained in detail elsewhere'. In brief, a CDS is used to transfer the credit risk of a reference entity (corporate or sovereign) from one party to another. In a standard CDS contract one party purchases credit protection from another party,. to cover the loss of the face value of an asset following a credit event. A credit event is a legally defined event that typically includes bankruptcy, failure-to-pay and restructuring. This protection lasts until some specified maturity date. To pay for this protection, the protection buyer makes a regular stream of payments', known as the premium leg, to the protection. seller as shown in Figure 1. This size of these premium payments is calculated from a quoted default swap spread which is paid on the face value of the protection. These payments are. made until a credit event occurs or until maturity, whichever occurs first..  

Between trade initiation and default or maturity, protection buyer makes regular payments of default swap spread to protection seller  

![](c4413c8b3f68434abae24c90d1534f1a6793c0fc47d53c205d71e054d93c0cb1.jpg)  
Figure 1. Mechanics of a default swap premium leg  

If a credit event does occur before the maturity date of the contract, there is a payment by the protection seller, known as the protection leg. This payment equals the difference between par and the price of the cheapest to deliver' (CTD) asset of the reference entity on the face value of the protection and compensates the protection buyer for the loss. It can be made in cash or physically settled format. This is shown in Figure 2..  

![](2e1278474c0ab0694dddfbf0798f1f39bc1247bea7d78afbe7940a3c3114a65d.jpg)  
Figure 2. The protection leg following a credit event  

# Example  

Suppose a protection buyer purchases 5-year protection on a company at a default swap spread of $300\mathrm{bp}$ . The face value of the protection is $\$10$ million. The protection buyer therefore makes quarterly payments approximately' equal to $\$10$ million $\times~0.03~\times~0.25~=$ $\$75,000$ . Assume that after a short period the reference entity suffers a credit event and that the CTD asset of the reference entity has a recovery price of $\$45$ per $\$100$ of face value. The payments are as follows:  

The protection seller compensates the protection buyer for the loss on the face value of the asset received by the protection buyer. This is equal to \$10 million $\times(100\%-45\%)=$ $\$5.5$ million.   
The protection buyer pays the accrued premium from the previous premium payment date to time of the credit event. For example, if the credit event occurs after a month then the protection buyer pays approximately $\$10$ million $\times0.03\times1/12=\S18{,}750$ of premium accrued. Note that this is the standard for corporate reference entity linked default swaps. For sovereign-linked default swaps there may be no payment of premium accrued.  

# 3. COMPUTING THE MARK-TO-MARKET VALUE  

Unlike bonds, the gain or loss from a CDS position cannot be computed simply by taking the difference between current market quoted price plus the coupons received and the purchase price. To value a CDS we need to use a term structure of default swap spreads, a recovery rate assumption and a model.  

To see this, consider an investor who initially buys 5-year protection on a company at a default swap spread of 60bp and then wishes to value the position after one year. On that date the 4-year credit default swap spread quoted in the market is 170bp. What is the current value. of the position? This is given by.  

$\mathbf{MTM}=$ Current Market Value of Remaining 4-year Protection Expected Present Value of 4-year Premium Leg at 60bp  

The first observation is that the investor has a CDS contract that has increased in value since he is paying only 60bp for something for which the market is now willing to pay 170bp. As. the mark-to-market value of a new default swap is zero, this implies that.  

Current Market Value of Remaining 4-year Protection $=$ Expected Present Value of Premium Leg at 170bp  

Using this knowledge, we can write that the market-to-market value to the protection buyer is $\mathbf{MTM}=$ Expected Present Value of 4-year Premium Leg at 170bp Expected Present Value of 4-year Premium Leg at 60bp  

If we define the Risky PV01 (RPvo1) as the expected present value of 1bp paid on the premium leg until default or maturity, whichever is sooner, then we can rewrite the MTM as  

MTM $=170{\mathrm{bp}}\times{\mathrm{Risky~PV}}01-60{\mathrm{bp}}\times{\mathrm{Risky~PV}}01=110{\mathrm{bp}}\times{\mathrm{Risky~PV}}01.$  

Hence we need to calculate the Risky PV01. The Risky PV01 is called "risky"' because it is the expected present value of an uncertain stream of premia. The uncertainty is due to the fact. that the premia payments terminate if there is a credit event..  

To realize this mark-to-market gain or loss, the investor has two choices :  

i. Unwind it with the initial counterparty (or have it reassigned to another counterparty) for a cash unwind value. The cash unwind value should equal the MTM of the position. ii. Enter into the offsetting position in which the investor sells protection on the same reference entity for the next four years at 170bp as shown in Figure 3. This creates a positive premium income of $170-60=1106\mathrm{p}$ per annum until a credit event or maturity, whichever occurs sooner. If there is a credit event, the investor has no principal risk since the defaulted bond delivered on one side can be delivered into the protection bought and similarly the payments of face value are exchanged. While the investor has no principal risk, there is still a premium risk. The risk is that the reference entity does not survive until the maturity date of the contract and that the four years of 110bp of annual income are not received. These cash flows are risky, and this risk must be accounted for by the Risky. PV01 which effectively discounts the cash flows at a spread over Libor.  

Both choices have the same economic value today. However they are different. In case (i) the P&L is realised immediately and the position is terminated. In case (ii) the P&L is only realised over the remaining life of the swap and the investor is taking the risk that a credit event occurs and the realised P&L is less than that they would have achieved if they had unwound the position for a cash amount. On the other hand, if no credit event occurs, and the net spread income is positive, they will receive more than the cash unwind value.  

![](9858ab1f6167976df36ba03453535588427a7414287aa6be7b5433e3546bfa90.jpg)  
Figure 3. A protection buyer who seeks to value a 5-year protection position after one year  

The present value of a position initially traded at time. $t_{0}$ at a contractual spread of $S(t_{0,}t_{N})$ with maturity. $t_{N}$ and which has been offset at valuation time $t_{V}$ with a position traded at a spread of $S(t_{V,}t_{N})$ is given by.  

$$
M T M(t_{V},t_{N})=\pm[S(t_{V},t_{N})-S(t_{0},t_{N})]\times R P V01(t_{V},t_{N})
$$  

where the positive sign is used for a long protection position and a negative sign for a short protection position. $R P V O I(t_{V},t_{N})$ , known as the risky PV01, is the present value at time $t_{V}$ of a 1bp premium stream which terminates at maturity time $t_{N}$ or default, whichever sooner. This is identical to equation (1a) derived above and shows that the value of both investor choices (i) and (ii) are equal.  

The calculation of the Risky PV01 requires a model because we need to take into account the riskiness of each premium payment by calculating the probability of the reference entity surviving to each premium payment date. These survival probabilities used in the valuation of the Risky PV01 must be the arbitrage-free survival probabilities. These are the survival probabilities that are implied by the market default swap spreads. A valuation model is therefore needed to calculate these survival probabilities from market default swap spreads. Such a model must:  

i. Capture the risk of default of the reference entity;   
ii. Model payment of the recovery rate as a percentage of the face value;.   
ii. Be able to model the timing of the default (especially important as the value of a default swap is the present value - all payments must be discounted to today),.   
iv. Be flexible enough to refit the term structure of quoted default swap spreads - the model should not generate any arbitrages;  

V. Be as simple as possible. A model that makes fewer assumptions but requires greater. implementation effort, and that produces spreads that differ by an amount well within the bid-offer spread should be rejected in favor of the simpler model..  

A model that allows this to be done is described next.  

# 4. MODELING CREDIT USING A REDUCED-FORM APPROACH  

The world of credit modelling is divided into two main approaches, one called the structural and the other called the reduced-form. In the structural approach, the idea is to characterize the default as being the consequence of some company event such as its asset value being insufficient to cover a repayment of debt. Such models are usually extensions of Merton's 1974 firm-value model - see O'Kane and Schloegl (2001) for a more complete discussion - that used a contingent claims analysis for modeling default. Structural models are generally used to say at what spread corporate bonds should trade based on the internal structure of the firm. They therefore require information about the balance sheet of the firm and can be used to establish a link between pricing in the equity and debt markets. However, they are limited in at least three important ways: they are hard to calibrate because internal company data is only published at most four times a year; they generally lack the flexibility to fit exactly a given term structure of spreads; and they cannot be easily extended to price credit derivatives.  

In the reduced-form approach, the credit event process is modeled directly by modeling the probability of the credit event itself. Using a security pricing model based on this approach,. this probability of default can be extracted from market prices. Reduced form models also generally have the flexibility to refit the prices of a variety of credit instruments of different. maturities. They can also be extended to price more exotic credit derivatives. It is for these reasons that they are used for credit derivative pricing..  

The most widely used reduced-form approach is based on the work of Jarrow and Turnbull (1995), who characterize a credit event as the first event of a Poisson counting process which occurs at some time $\uptau$ with a probability defined as  

$$
\operatorname*{Pr}[\tau<t+d t\mid\tau\geq t]=\lambda(t)d t
$$  

ie, the probability of a default occurring within the time interval $\left[\mathrm{t},\mathrm{t}{+}\mathrm{dt}\right)$ conditional on surviving to time t, is proportional to some time dependent function. $\lambda(t)$ , known as the hazard. rate, and the length of the time interval. $d t$ We can therefore think of modelling default in a one-period setting as a simple binomial tree in which we survive with probability $1-\lambda(\mathrm{t})\mathrm{dt}$ or default and receive a recovery value R with probability. $\lambda(\mathrm{t})\mathrm{dt}$  

We make the simplifying assumption that the hazard rate process is deterministic..   
By extension, this assumption also implies that the hazard rate is independent of interest rates and recovery rates. Towards the end of this paper we will discuss the validity of this.   
assumption in the context of pricing. All we say now is that for almost all market participants,.   
these assumptions are acceptable as their pricing impact is well within the typical bid-offer.   
spread for credit default swaps.  

![](64b300be595ce2e0002484a532d51da10e34ca2efb8c5cfd1beec7aa6d60834f.jpg)  
Figure 4. The equivalent of a binomial tree in the modeling of default in which the tree terminates and makes a payment K at default.  

We can extend this model to multiple time periods, as shown pictorially in Figure 4, where K is the payoff at the time of a default. We can compute the continuous time survival probability to time T conditional on surviving to time ty by considering the limit dt. $\rightarrow0$ . It can be shown that the survival probability is given by.  

$$
Q(t_{V},T)=\exp\left(-\int_{t_{V}}^{T}\lambda(s)d s\right).
$$  

In the following sections we will first show how to use this model to value both the premium and protection legs, and hence the breakeven spread of a default swap. We can then use this. model to imply the term structure of arbitrage-free survival probabilities from market spreads. These will then be used to mark our existing position to market.  

# 5.  VALUING THE PREMIUM LEG  

The premium leg is the series of payments of the default swap spread made to maturity or to the time of the credit event, whichever occurs first. It also includes the payment of premium accrued from the previous premium payment date until the time of the credit event. Assume that there are. $\scriptstyle\mathrm{n=1,\ldots,N}$ contractual payment dates $\mathbf{t}_{1},\ldots,\mathbf{t}_{\mathrm{N}}$ where ${} \mathrm{\Delta t_{N}} {}$ is the maturity date of the default swap. Denoting the ${} \mathrm{\Delta t_{N}} {}$ maturity contractual default swap spread by $\mathrm{S(t_{0}t_{N})}$ , and ignoring premium accrued, we can write the present value of the premium leg of an existing contract as  

$$
\operatorname{Premium}\operatorname{Leg}\operatorname{PV}(t_{V},t_{N})=S(t_{0},t_{n})\sum_{n=1}^{N}\Delta(t_{n-1},t_{n},B)Z(t_{V},t_{n})\mathcal{Q}(t_{V},t_{n})
$$  

# where  

$\Delta(\mathrm{t_{n-1}},\mathrm{t_{n}},\mathrm{B})$ is the day count fraction between premium dates. $\bf{t}_{n-1}$ and ${} \mathrm{\bf t}_{\mathrm{n}} {}$ in the appropriate basis convention denoted by B.   
$\mathrm{Q(t_{V},t_{n})}$ is the arbitrage-free survival probability of the reference entity from valuation time ty to premium payment time $\mathrm{\bf t_{n}}$ . This factors into the pricing the risk that a reference. entity will not survive to a premium payment time..   
$Z(\mathrm{t_{V},t_{n}})$ is the Libor discount factor from valuation date to premium payment date n. In. what follows, we have assumed that the user has been able to bootstrap a full term structure of Libor discount factors, $Z(\mathrm{t},\mathrm{T})$ in the currency of the default swap. being priced.  

This equation ignores the effect of premium accrued - the fact that upon a credit event the contract will usually require the protection buyer to pay the fraction of premium that has accrued from the previous premium payment date to the time of credit event.  

To include the effect of premium accrued, we have to work out the expected accrued premium payment by considering the probability of defaulting at each time between two premium dates, and calculating the probability weighted accrued premium payment. To do this, we have to  

1. Consider each premium accrual period starting at $\mathrm{{t_{n-l}}}$ with the payment date at $\mathrm{\bf t}_{\mathrm{n}}$   
2. Determine the probability of surviving from the valuation date $\mathrm{t_{V}}$ to each time s in the. premium period and then defaulting in the next small time interval ds. The probability of this is given by $\mathrm{Q}(\mathrm{t_{V}},\mathrm{s})\lambda(\mathrm{s})\mathrm{d}\mathrm{s}$   
3. Calculate the accrued payment since the previous premium date to each time.   
4. Discount this payment back to the valuation date using the Libor discount factor..   
5. Integrate over all times in the premium period. Strictly speaking this is a discrete daily integration since premium payments are only calculated on a daily basis. However for. mathematical simplicity we tend to approximate this as a continuous integral. The. difference is essentially negligible in this context,.   
6. Sum over all premium periods from $\mathfrak{n}{=}1$ to the final premium $\tt n\mathrm{=}\tt N$  

The resulting expression for the premium accrued is given by  

$$
S(t_{0},t_{N}){\sum_{n=1}^{N}}\int_{t_{n-1}}^{t_{n}}\Delta(t_{n-1},s,B)Z(t_{V},s){\mathcal{Q}}(t_{V},s)\lambda(s)d s
$$  

The integral makes this is a complicated expression to evaluate exactly. However, as we demonstrate in O'Kane and Turnbull (2003), it is possible to approximate this equation with  

$$
\frac{S(t_{0},t_{N})}{2}{\sum_{n=1}^{N}}\Delta(t_{n-1},t_{n},B)Z(t_{V},t_{n})(Q(t_{V},t_{n-1})-Q(t_{V},t_{n}))
$$  

by noting that if a default does occur between two premium dates, the average accrued premium is half the full premium due to be paid at the end of the premium period. The full value of the premium leg is then given by  

$$
S(t_{0},t_{N})\times R P V01
$$  

where RPV01 is the risky PV01 defined as  

$$
R P V01=\sum_{n=1}^{N}\Delta(t_{n-1},t_{n},B)Z(t_{r},t_{n})\biggl[Q(t_{r},t_{n})+\frac{1_{P A}}{2}(Q(t_{r},t_{n-1})-Q(t_{r},t_{n}))\biggr]
$$  

where $1_{\mathrm{PA}}{=}1$ if the contract specifies premium accrued (PA) and O otherwise.  

The effect of premium accrued on the breakeven spread is typically small, although not. negligible, and we plot it in Figure 5 as a function of the default swap spread level for a recovery rate assumption of $40\%$ . The effect of premium accrued on the spread can be very well approximated by  

$$
\frac{S^{2}}{2(1-R)f}
$$  

where $f$ is the frequency of payments on the premium leg.  

![](8ef3a2aa9523a7c828c444427dfe3651001e7c9f72f9c4171f8905af7194e552.jpg)  

The breakeven spread with premium accrued has to be less than that without premium accrued as a protection buyer will want to pay a lower spread in order to offset the possible. extra accrued payment if there is a credit event. For a contract with a credit default swap spread of 200bp and an expected recovery rate of $40\%$ , the change in spread due to premium accrued on a quarterly-paying default swap is approximately equal to 0.83bp. This is well inside typical bid-offers for names that trade at this spread level. However, for wide spread names, this difference, which is quadratic in the spread, cannot be ignored.  

# 6. VALUING THE PROTECTION LEG  

The protection leg is the contingent payment of. $(100\%\mathrm{~-~R~})$ on the face value of the protection made following the credit event. R is the expected recovery rate -- to be precise, it is the expected price of the CTD obligation into the protection at the time of a credit event. There may be a delay of up to 72 calendar days between notification of the credit event and settlement of the protection leg payment, but we typically assume that this payment is made immediately.  

In pricing the protection leg, it is important to take into account the timing of the credit event because this can have a significant effect on the present value of the protection leg - especially for longer maturity default swaps. Within the hazard rate approach we can solve this timing problem by conditioning on each small time interval $\displaystyle\left[\mathbf{s},\mathbf{s}^{+}\mathbf{ds}\right]$ between time ty and time $\mathrm{\Delta t_{N}}$ at which the credit event can occur. The steps are described below.  

1. Calculate the probability of surviving to some future time s which equals $\mathrm{Q(t_{\mathrm{V}},s)}$   
2. Compute the probability of a credit event in the next small time increment ds which is given by (s).ds.   
3.  At this point an amount $(100\%\mathrm{~-~R~})$ is paid, and we discount this back to today at the risk-free rate $Z(\mathrm{t_{V}},\mathrm{s})$   
4. We then consider the probability of this happening at all times from $\mathbf{s}=\mathbf{t}_{\mathrm{V}}$ to the maturity date ty. Strictly speaking the timing of a credit event should not be resolved to less than a day. However, assuming that a credit event can occur intra-day has almost no effect on the valuation while simplifying the exposition.  

![](81bcf1d876d0cf5ede3efe0d8f6ec6a8ee0488e28e4b4e859bcfd2751dac5ef0.jpg)  
Figure 6. Steps in the calculation of the expected present value of a recovery rate which is paid at the time of a credit event  

These steps are also shown in Figure 6. As a result, we calculate the expected present value of the recovery payment as  

$$
(1-R)\int_{t_{V}}^{t_{N}}Z(t_{V},s)Q(t_{V},s)\lambda(s)d s
$$  

where R is the expected recovery price of the CTD asset at the time of the credit event. The integral, makes this expression tedious to evaluate. It is possible to show that we can, without any material loss of accuracy, simply assume that the credit event can only occur on a finite number M of discrete points per year. For a $\mathrm{\Deltat_{N}}$ maturity default swap, we have $\mathrm{M}{\times}\mathrm{t_{N}}$ discrete times which we label as $\mathrm{m}{=}1,\ldots,\mathrm{M}{\times}\mathrm{t_{N}}.$ We then have  

$$
(1-R)\sum_{m=1}^{M\times t_{N}}Z(t_{V},t_{m})(Q(t_{V},t_{m-1})-Q(t_{V},t_{m}))
$$  

The lower the value of M, the fewer calculations we have to do. However it also means that the accuracy is reduced. In terms of spread change, we show in O'Kane and Turnbull (2o03) that for a flat hazard rate structure, the percentage difference in the computed spread between. the continuous and discrete case is given by $\mathbf{r}/2\mathbf{M}$ where r is the continuously compounded default free interest rate. The quality of this approximation is demonstrated in Figure 7 for. different values of M and r. For example, assuming that. $\scriptstyle{\mathrm{r}}=3\%$ and $\mathbf{M}{=}12$ (corresponding to monthly intervals) we have a percentage error in the spread of. $0.125\%$ , i.e., an absolute error. of 1bp on a spread of 800bp compared with the continuous case. This level of accuracy is. well inside the typical bid-offer spread. This is encouraging as it means that the model can be. fast, simple and accurate.  

![](7c3c013c428edf34ff1c2007f008a4a49c9f3fad757a201b4398828240d6f02d.jpg)  
Figure 7. Model-based calculation of the percentage discretization error on protection leg PV shown as a function of 1/M, the interval time spacing  

# 7. CALIBRATING EXPECTED RECOVERY RATES  

One of the required inputs which we have not yet discussed is the recovery rate R. Unlike the spread or interest rate term structure, this is not a market observable input. The expected recovery rate R is not the expected value of the asset following the post-default workout process. Instead it is the price of the CTD asset, expressed as a percentage of face value, within approximately 72 calendar days after notification of the credit event. This is similar to the definition used by rating agencies such as Moody's for their recovery rate statistics. However, there are a number of caveats with rating agency recovery statistics: (i) rating agencies do not view restructuring as a default while standard default swaps do; (ii) they are heavily biased towards US corporates, because that is where the greatest amount of default data originates - see Figure 8  and so may not be appropriate for European names; (iii) they are historical, not forward looking, and so fail to take into account market expectations about the future; (iv) they are not name or sector specific. Despite these, for good quality investment grade credits, most dealers use the rating agency recovery rate data as a starting point.  

These typically show the average recovery rate by seniority and type of credit instrument, and usually focus on a US corporate bond universe. Adjustments may be made for non-US corporate names and for certain industrial sectors.  

Using a valuation model to extract information about the recovery value from bond prices may be one way to overcome this calibration problem. However, this is difficult for good. quality names because the low default probability means that the recovery rate is only a small component of the bond price and of the same order of magnitude as any bid-offer spread.. However, this is not the problem it may seem because as we will show in our longer paper. (O'Kane and Turnbull 2003), the sensitivity of the mark-to-market of a default swap to the recovery rate assumption is very low for low spread levels. For much lower credit quality names the recovery rate sensitivity is much higher, and our hope is that the lower bond prices begin to reveal more information about market expectations for the future recovery rates..  

Figure 8. Average defaulted debt recovery rate estimates Europe vs US, 1985-2001 (percentage of face)   


<html><body><table><tr><td></td><td colspan="2">Europe</td><td colspan="2">sn</td></tr><tr><td>Seniority</td><td>Average</td><td>Count</td><td>Average</td><td>Count</td></tr><tr><td>Bank Loan (Sr. Secured)</td><td>71.8%</td><td>4</td><td>66.8%</td><td>201</td></tr><tr><td>Sr.Secured</td><td>55.0%</td><td>1</td><td>56.9%</td><td>150</td></tr><tr><td>Sr.Unsecured</td><td>20.8%</td><td>28</td><td>50.1%</td><td>565</td></tr><tr><td>Sr. Sub</td><td>24.0%</td><td>4</td><td>32.9%</td><td>359</td></tr><tr><td>Sub</td><td>13.0%</td><td>1</td><td>31.3%</td><td>342</td></tr><tr><td>AllBonds</td><td>22.0%</td><td>34</td><td>42.8%</td><td>1,416</td></tr></table></body></html>

Source: Moody's Investor Services  

# 8. CALCULATING THE BREAKEVEN DEFAULT SWAP SPREAD  

We have now presented a model that values the protection and premium legs of a CDS. The next step is to work out the survival probabilities from the market quoted default swap spread. This is the breakeven spread, and is given by  

For a new contract we have. $\mathrm{t_{V}=t_{0}}$ so that substituting from equation (5) and equation (7) and rearranging, we get  

$$
S(t_{V},t_{N})=\frac{(1-R)\displaystyle\sum_{m=1}^{M\times t_{N}}Z(t_{V},t_{m})[Q(t_{V},t_{m-1})-Q(t_{V},t_{m})]}{R P V01}
$$  

for the breakeven spread where the RPv01 has been defined in equation (5).  

Now we have a direct relationship between the default swap spread quoted in the market and the survival probabilities it implies. However, this is still not sufficient to enable us to extract all of the required survival probabilities. To see this, consider the case of a 1Y CDS which has a quoted spread of 85bp. Assuming quarterly payments on the premium leg, a monthly discretization frequency $(\mathrm{M}{=}12)$ , and premium accrued, we can rewrite equation (9) as  

$$
0.0085=\frac{(1-R)\sum_{m=1}^{12}Z(t_{\nu},t_{m})(\mathscr{Q}(t_{\nu},t_{m-1})-\mathscr{Q}(t_{\nu},t_{m}))}{(1/2)\sum_{n=3,6,9,12}\Delta(t_{n-3},t_{n},B)Z(t_{\nu},t_{n})(\mathscr{Q}(t_{\nu},t_{n-3})+\mathscr{Q}(t_{\nu},t_{n}))}
$$  

In this equation we know all of the accrual factors, we can make an assumption about the recovery rate R, and we can calculate all of the Libor discount factors from the Libor discount curve. All we then need to know are a maximum' of $12{+}4{=}16$ survival probabilities. Clearly this one equation cannot give all of these survival probabilities. We therefore need to make a simplifying assumption about the term structure of survival probabilities.  

# 9. BUILDING A HAZARD RATE TERM STRUCTURE  

The standard modeling assumption used in the credit default swap market is to assume that the hazard rate is a piecewise flat function of maturity time. This is an entirely reasonable assumption because, given only one data point, it is not possible to extract more than one piece of information about the term structure of hazard rates.  

![](63cb83a843859aa0d95a84faef1cb341505cccb7b51afa8ba23f79cbb6c4b1a1.jpg)  
Figure 9. Given market default swap spreads at 1Y, 3Y, 5Y, 7Y and 10Y, the simplest assumption is of a piecewise flat hazard rate term structure. One can also assume a flat then linear term structure  

One could go a stage further and assume that the curve is piecewise linear. However, this only makes a difference if (i) we do not have quoted spreads for many maturities and (ii) the curve is steeply sloped. This is generally not the case because most names only have liquidity at the 5-year default swap and the curve is therefore assumed to be flat. The main exception is when we have an inverted spread curve, usually associated with a distressed credit. In this case we usually have more market spreads, especially at short maturities. As a result we will keep the model simple by assuming a piecewise flat structure, although we note that the generalization to a linear scheme is actually fairly straightforward.  

Given 1Y, 3Y, 5Y, 7Y and 10Y default swap spread values, we would assume that we have a hazard rate term structure with five sections $\lambda_{0,1},\lambda_{1,3},\lambda_{3,5},\lambda_{5,7}$ and $\lambda_{7,10}.$ as shown in Figure 9.  

The process of constructing the term structure of hazard rates is an iterative one commonly known as bootstrapping. It starts with taking the shortest maturity contract and using it to calculate the first survival probability. In this case, the 1Y default swap has to be used to calculate the value of $\lambda_{0,1}$ . Assuming a quarterly premium payment frequency, using a value. of $\mathbf{M}{=}12$ , and assuming that premium accrued is not paid, this is achieved by solving.  

$$
\frac{S(t_{V},t_{V}+1Y)}{1-R}\sum_{n=3,6,9,12}\Delta(t_{n-3},t_{n},B)Z(t_{\nu},t_{n})e^{-\lambda_{01}\tau_{n}}=\sum_{m=1}^{12}Z(t_{\nu},t_{m})(e^{-\lambda_{01}\tau_{m-1}}-e^{-\lambda_{01}\tau_{m}})
$$  

for the value of. $\lambda_{0,1}$ . Our $(\mathrm{M}{=}12\$ ) monthly discretization means that  

$$
\tau_{0}=0.0,\tau_{1}=0.0833,\tau_{2}=0.167,\tau_{3}=0.25,...,\tau_{12}=1.00
$$  

Such an equation can be solved using a one-dimensional root-searching algorithm'. This procedure is then repeated to solve for $\lambda_{1,3}$ and so on until the final maturity default swap is. reached. Beyond this, it is often assumed that the hazard rate is flat. Defining $\scriptstyle\tau=\mathrm{T-t_{V}}$ , we have  

$$
\begin{array}{r}{\mathcal{Q}(t_{V},T)=\left\{\begin{array}{l l}{\exp(-\lambda_{0,1}\tau)}&{\mathrm{~if~}0<\tau\leq1}\ {\exp(-\lambda_{0,1}-\lambda_{1,3}(\tau-1))}&{\mathrm{~if~}1<\tau\leq3}\ {\exp(-\lambda_{0,1}-2\lambda_{1,3}-\lambda_{3,5}(\tau-3))}&{\mathrm{~if~}3<\tau\leq5}\ {\exp(-\lambda_{0,1}-2\lambda_{1,3}-2\lambda_{3,5}-\lambda_{s,7}(\tau-5))}&{\mathrm{~if~}5<\tau\leq7}\ {\exp(-\lambda_{0,1}-2\lambda_{1,3}-2\lambda_{3,5}-2\lambda_{s,7}-\lambda_{7,10}(\tau-7))}&{\tau>7}\end{array}\right.}\end{array}
$$  

We have assumed that the hazard rate remains flat beyond the 10Y maturity.  

Figure 10. An example of hazard rates fitted to a market curve consisting of 6M, 1Y, 2Y,. 3Y, 5Y, 7Y and 10Y spreads. We show the value of the hazard rates for which. the model calculated spread equals the market default swap spreads. A recovery rate of $40\%$ was assumed.   


<html><body><table><tr><td colspan="2"></td><td rowspan="2">MarketSpread (dq)</td><td rowspan="2">ModelSpread (bp)</td><td rowspan="2">Protection Leg</td><td rowspan="2">RiskyPV01</td></tr><tr><td>Term</td><td>HazardRate</td></tr><tr><td>6M</td><td>1.6832%</td><td>100</td><td>100</td><td>0.4941%</td><td>0.4941</td></tr><tr><td>1Y</td><td>2.0203%</td><td>110</td><td>110</td><td>1.0825%</td><td>0.9841</td></tr><tr><td>2Y</td><td>2.1950%</td><td>120</td><td>120</td><td>2.3061%</td><td>1.9218</td></tr><tr><td>3Y</td><td>3.0838%</td><td>140</td><td>140</td><td>3.9264%</td><td>2.8046</td></tr><tr><td>5Y</td><td>2.8126%</td><td>150</td><td>150</td><td>6.6329%</td><td>4.4219</td></tr><tr><td>7Y</td><td>3.2054%</td><td>160</td><td>160</td><td>9.3720%</td><td>5.8575</td></tr><tr><td>10Y</td><td>3.0386%</td><td>165</td><td>165</td><td>12.7162%</td><td>7.7068</td></tr></table></body></html>  

An example fitting is presented in Figure 10. This shows the term of each default swap. spread, the market spread and the value of the hazard rate for which the model spread and market spread are equal. We also show the present value of the protection leg. Finally, we. show that the model spread is the value of the protection leg divided by the Risky PV01..  

The hazard rates calculated here are the arbitrage-free ones. This means that they are the level of hazard rate required by our choice of model in order to fit the market. The arbitragefree hazard rate is typically much larger than the hazard rate implied by historical data. because it includes other non-default factors such as liquidity risk premia, spread risk premia and market supply-demand effects.  

When the spread curve is inverted, it is sometimes found that this implies negative hazard rates. This is clearly incorrect as a probability can never be negative. If we believe the model specification and the recovery rate assumption, then the negative probability implies an arbitrage, which can be either model dependent or model independent.  

Figure 11. An example of hazard rates fitted to a market curve consisting of 6M, 1Y, 2Y, 3Y, 5Y, 7Y and 10Y spreads. For an inverted curve it is possible to find that the hazard rate is negative. This may reflect an arbitrage in the term structure of credit default swap spreads   


<html><body><table><tr><td colspan="3"></td><td rowspan="2">ModelSpread (bp)</td><td rowspan="2">Protection Leg</td><td rowspan="2">RiskyPV01</td></tr><tr><td>Term</td><td>HazardRates</td><td>Spread (bp)</td></tr><tr><td>6M</td><td>13.2731%</td><td>800</td><td>800</td><td>3.7869%</td><td>0.4734</td></tr><tr><td>1Y</td><td>6.5547%</td><td>600</td><td>600</td><td>5.5692%</td><td>0.9282</td></tr><tr><td>2Y</td><td>4.8028%</td><td>450</td><td>450</td><td>8.0081%</td><td>1.7796</td></tr><tr><td>3Y</td><td>-0.4883%</td><td>300</td><td>300</td><td>7.7733%</td><td>2.5911</td></tr><tr><td>5Y</td><td>0.5448%</td><td>200</td><td>200</td><td>8.2728%</td><td>4.1364</td></tr><tr><td>7Y</td><td>3.3592%</td><td>200</td><td>200</td><td>11.0672%</td><td>5.5336</td></tr><tr><td>10Y</td><td>3.3593%</td><td>200</td><td>200</td><td>14.6438%</td><td>7.3219</td></tr></table></body></html>  

An example of a model-independent arbitrage can be seen by considering the calibration in Figure 11, where the market default swap spread term structure is steeply inverted, dropping. from 800bp at a 6-month maturity to. $200\mathrm{bp}$ at five years. We see that the hazard rate for the 2-3 year period is negative at. $-0.4883\%$ . This negative hazard rate has been caused by a 2-. year spread level at 450bp followed by a 3-year spread level at $300\mathrm{bp}$  

This is a clear arbitrage - we can buy 3Y protection at 300bp and sell 2Y protection at 450bp. As long as there is no credit event in the first two years, we receive 150bp in both years. We use these to fund the payment of. $300\mathrm{bp}$ in the final year. A credit event in the first two years. results in a netting of positions - we also keep the net carry to the date of the credit event. A credit event between years two and three results in a windfall gain of. $(100\%-\mathrm{R})$ . As long as interest rates are positive we have a strategy which costs nothing to enter into but which has a payoff greater than or equal to zero in all scenarios (we ignore counter-party risk). Identification of this arbitrage does not require a model..  

In other cases a negative hazard rate may imply a model-dependent arbitrage. In the above example, the hazard rate only becomes positive once the 3Y default swap spread is greater than $310\mathrm{bp}$ , not 300bp. The model is saying is that this extra 10bp per year is the value of the gain from (i) the positive carry if there is a credit event at any time, and (ii) payment of $(100\%\mathrm{~-~}\mathrm{R})$ if there is a credit event between years two and three. This threshold of 310bp therefore depends on the valuation model, the assumed recovery rate of $40\%$ and the term structure of interest rates.  

# 10. COMPUTING THE MARK-TO-MARKET  

In this section we compute the mark-to-market of a default swap position when the valuation date is on a premium payment date. This simplifies things because it avoids a discussion of accrued interest and the treatment of premium accrued. We refer the reader to the longer version for the discussion of these issues. We remind ourselves that the full mark-to-market of a long protection default swap position is given by  

$$
M T M(t_{V},t_{N})=\pm[S(t_{V},t_{N})-S(t_{0},t_{N})]\times R P V01(t_{V},t_{N}).
$$  

where  

$$
R P V01=\sum_{n=1}^{N}\Delta(t_{n-1},t_{n},B)Z(t_{V},t_{n})\biggl[Q(t_{V},t_{n})+\frac{1_{P A}}{2}(Q(t_{V},t_{n-1})-Q(t_{V},t_{n}))\biggr].
$$  

$1_{\mathrm{PA}}{=}1$ if premium accrued is part of the contract and O otherwise. The value of the current market spread to maturity $\mathrm{S(t_{V},t_{N})}$ is given by solving  

$$
(1-R)\sum_{m=1}^{M\times t_{N}}Z(t_{V},t_{m})(\mathcal{Q}(t_{V},t_{m-1})-\mathcal{Q}(t_{V},t_{m}))=S(t_{V},t_{N})\times R P V01(t_{V},t_{N})
$$  

A full example calculation of a default swap mark-to-market is shown in Figure 12 for a $\$100$ long protection position initially transacted at a contractual spread of. $200\mathrm{bp}$ The survival probabilities and discount factors are also shown. The risky PV01 is also easy to compute given that we now have all the discount factors, survival probabilities and accrual. factors.  

The protection was bought at 200bp, spreads have tightened and the current market spread for the remaining term is now worth $142.7\mathrm{bp}$ , according to the model. Note that the current breakeven spread is a model-based interpolation between the 4Y and 5Y CDS spreads of 140bp and $150\mathrm{bp}$ , but closer to the former given that the existing contract has a remaining maturity of four years and three months. The mark-to-market is negative at - $\$223,4$  

<html><body><table><tr><td></td><td colspan="3">Figure 12. Results of model calculation of the CDS mark-to-market.</td></tr><tr><td></td><td>6M 1.35</td><td>1Y</td><td>110bp</td></tr><tr><td></td><td>1Y 1.43</td><td>2Y</td><td>120bp</td></tr><tr><td>Rates</td><td>2Y 1.90</td><td>tSwaps 3Y</td><td>130bp</td></tr><tr><td>BOR LIB</td><td>3Y 2.47</td><td>Default 4Y</td><td>140bp</td></tr><tr><td>人</td><td>2.936</td><td>5Y</td><td>150bp</td></tr><tr><td>5Y</td><td>3.311</td><td>Recovery Rate R</td><td>40%</td></tr><tr><td colspan="2"></td><td colspan="2"></td></tr><tr><td>Notional</td><td>$10,000,000</td><td>Frequency</td><td>Quarterly</td></tr><tr><td>ContractualSpread</td><td>200bp</td><td>Basis</td><td>Actual 360</td></tr><tr><td>Effective Date</td><td>20 June 2002</td><td>Calendar</td><td>USD</td></tr><tr><td>Maturity Date</td><td>20 Sep 2007</td><td>PremiumAccrued</td><td>Yes</td></tr><tr><td colspan="4"></td></tr><tr><td colspan="4">ValuationDate:19June2003</td></tr><tr><td>Payment Dates</td><td>Day Count Actual Flows</td><td>Survival Probability</td><td>Libordiscountfactor</td></tr><tr><td>Mon 22 Sep 2003</td><td>0.261111</td><td>52,222.22 99.567%</td><td>0.99649</td></tr><tr><td>Mon 22 Dec 2003</td><td>0.252778</td><td>50,555.56 99.150%</td><td>0.99311</td></tr><tr><td>Mon22Mar2004</td><td>0.252778</td><td>50,555.56 98.657%</td><td>0.98953</td></tr><tr><td>Mon 21 Jun 2004</td><td>0.252778</td><td>50,555.56 98.164%</td><td>0.98583</td></tr><tr><td>Mon 20 Sep 2004</td><td>0.252778</td><td>50,555.56 97.628%</td><td>0.98084</td></tr><tr><td>Mon 20 Dec 2004</td><td>0.252778</td><td>50,555.56 97.092%</td><td>0.97523</td></tr><tr><td>Mon 21 Mar 2005</td><td>0.252778</td><td>50,555.56 96.559%</td><td>0.96899</td></tr><tr><td>Mon 20 Jun 2005</td><td>0.252778</td><td>50,555.56</td><td>96.030% 0.96218</td></tr><tr><td>Tue 20 Sep 2005</td><td>0.255556</td><td>51,111.11</td><td>95.420% 0.95450</td></tr><tr><td>Tue 20 Dec 2005</td><td>0.252778</td><td>50,555.56</td><td>94.815% 0.94630</td></tr><tr><td>Mon 20 Mar 2006</td><td>0.250000</td><td>50,000.00</td><td>94.220% 0.93754</td></tr><tr><td>Tue 20 Jun 2006</td><td>0.255556</td><td>51,111.11 93.616%</td><td>0.92800</td></tr><tr><td>Wed 20 Sep 2006</td><td>0.255556</td><td>51,111.11</td><td>92.934% 0.91879</td></tr><tr><td>Wed 20 Dec 2006</td><td>0.252778</td><td>50,555.56</td><td>92.259% 0.90931</td></tr><tr><td>Tue 20 Mar 2007</td><td>0.250000</td><td>50,000.00</td><td>91.597% 0.89946</td></tr><tr><td>Wed 20 Jun 2007</td><td>0.255556</td><td>51,111.11</td><td>90.924% 0.88899</td></tr><tr><td>Thu 20 Sep 2007</td><td>0.255556</td><td>51,111.11</td><td>90.173% 0.87902</td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>  

<html><body><table><tr><td>Risky PV01</td><td>3.899</td><td>BreakevenSpread</td><td>142.7</td></tr><tr><td>PVofProtection</td><td>$557,872</td><td>FullMark-to-Market</td><td>-$223,516</td></tr></table></body></html>  

# 11. CONCLUSIONS  

This paper has set out the standard valuation model adopted by the credit derivatives market for the valuation of credit default swaps. Despite being quite simple, the model manages to capture all of the market risks of the credit default swap.  

A number of simplifying assumptions have been made. For example, we have ignored interest rate and credit correlations. However, the extremely low interest rate sensitivity of a credit default swap means that the effect of this correlation is at most second-order and we can reasonably ignore it.  

The model we have set out is therefore capable of doing the specified task. To obtain a simplified Excel-based version of this model, readers are invited to contact one of the authors at dokane@lehman.com.  

A more complete exposition of the valuation model is to be published soon. In addition to what has been covered here, this paper will also discuss the mechanics of CDS contracts, the. risk sensitivities of CDS positions, a comparison of the CDS spread with other credit spread measures, plus a discussion of counter-party and other risks..  

# 12. BIBLIOGRAPHY  

Jarrow and Turnbull (1995), "Pricing Derivatives on Financial Securities Subject to Credit Risk", Journal of Finance, Vol 50 (1995), 53-85.   
O'Kane (2001), Credit Derivatives Explained, Lehman Brothers, March 2001.   
O'Kane and Schloegl (2001), Modelling Credit: Theory and Practice, February 2001. O'Kane and Turnbull (2003), Valuation and Risk-Management of Credit Default Swaps, Lehman Brothers, to be published spring 2003.  