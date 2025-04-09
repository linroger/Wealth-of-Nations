# 24.3 CREDIT VALUATION ADJUSTMENT  

Throughout this book, we have assumed that there is no default risk in derivatives transactions. For exam-. ple, in the Black-Scholes model we assumed that each counterparty will honor its obligations and that neither will default. The assumption that large financial institutions are default free is not realistic. For example, in 2008, eight credit events on financial institutions occurred in 1 month (Lehman Brothers, Fannie Mae, Freddie Mac, Washington Mutual, Landsbanki, Glitnir, Kaupthing, and Merrill Lynch)..  

# 24.3.1 COUNTERPARTY RISK EXAMPLE AND CVA  

It was not just in the valuation of forwards, options, and credit default swaps that we assumed coun-. terparty risk away. In our discussion of interest rate swaps (IRSs) in Chapter 3, we also did not consider the risk that a counterparty may default. How does counterparty risk affect the valuation of a. simple IRS? Let's assume an IRS with a notional amount of. $N$ and maturity $T=t_{4}$ , between bank B and a corporate counterparty C where B pays fixed and C pays floating. Figure 24.1a illustrates the. cash flows if we assume that B and C cannot default. Let's continue to assume that B is risk free for now, but let's allow for the possibility of default by. $\mathrm{^C}$ at an unknown time $\tau$ .This is shown in Figure 24.1b. For illustration we assume that the default occurs at some point between dates. $t_{3}$ and $t_{4}$ Apart from the trivial scenario of no default (that is. $\tau>T$ , we can distinguish two basic scenarios:  

Scenario 1 (default and B has positive exposure): C defaults at some point $\tau$ where $t_{\underline{{3}}}<\tau<t_{4}$ , and the net present value (NPV) of the remaining payments from C to B is positive, that is, B has positive exposure. In this case, B receives only a recovery fraction REC of the net present value NPV. Scenario 2 (default and B has negative exposure): If C defaults at some point. $\tau$ where $t_{3}<\tau<t_{4}$ , and the NPV of the remaining payments from C to. $\mathbf{B}$ is negative, then B has. negative exposure. In this case, B pays the liquidator of C a positive amount..  

The example in Figure 24.1 illustrates the important insight that it is not just the stochastic default time that is important but also the sign and magnitude of the NPV of any remaining payments at. default. These are features that any adjustment for counterparty risk must take into account.  

There are several ways of incorporating counterparty risk into derivatives pricing. CVA is one. such adjustment and it is simple and intuitive. The idea behind CVA is that if we enter into a portfo-. lio derivative transaction with a counterparty, that counterparty might default and it might default at a time when we have an exposure, that is the value of the transaction to us is positive and negative to the counterparty. This has to be incorporated into the valuation of the transaction. First, we value the  

![](images/0b4fb6632958b3660f26b66cf97b84af1a3e414c473c3bf9ebe7a13849fc600a.jpg)  

![](images/ee6624a89b0b9aa0324b6671415d312789ab4cacb87522dd4fe2a0f810f4fa7f.jpg)  

# FIGURE 24.1  

IRS cash flows with and without counterparty risk.  

transaction assuming that neither we nor the counterparty would default. Then we will subtract the.   
CVA, or credit valuation adjustment, to reflect the possibility that the counterparty might default..   
Even before going into the details of CVA, it is clear that the above logic implies that another adjust-.   
ment may be required for the fact that we could also default on the payment obligations to the counterparty. This is called DVA and we will discuss it in a subsequent section..  

For illustration, we could assume that in the example above the counterparty C can be either the European Central Bank (ECB) or a Greek commercial bank in 2010. Clearly the ECB and the Greek bank had very different counterparty risks in 2010, as our discussion of sovereign default swaps in Chapter 18 showed. Incorporating counterparty risk into the evaluation of the payoffs from the transaction will necessarily imply that we will condition on whether a default by the bank's counterparty will occur or not. Intuitively, the inclusion of the risk of the bank's counterparty defaulting will add optionality into the payoff from the bank's perspective.  

The CVA adjustment can be positive or negative. Consider an example involving bank B and. its counterparty, a corporate client C. If C defaults and the present value of the portfolio at default. is positive from the perspective of the surviving party (bank B), then B only gets a fraction of the. portfolio equal to the recovery rate from C. It is also possible that the present value of the portfolio is negative from the perspective of the surviving party B. In this case, B has to pay the liquidators of the defaulted corporate C. This logic leads to a price of the derivatives transaction with counterparty risk $(P_{\mathrm{with~CR}})$ that is equal to the value of the deal without counterparty risk. $(P_{\mathrm{without~CR}})$ minus a positive adjustment, labeled CVA, which captures the above option:.  

$$
P_{\mathrm{with~CR}}=P_{\mathrm{no~CR}}-\mathrm{CVA}
$$  

This adjustment looks relatively straightforward, but several complications arise in practice. First, even for some simple derivatives incorporating counterparty risk makes the valuation model dependent, even if under default-free pricing it was model independent. One of the simplest derivatives that we have seen is an IRS as discussed in Chapter 4. With counterparty risk, the IRS valuation needs to include an option on the residual value of the portfolio and to price such an option we require an interest rate option pricing model.  

Second, as we introduce a new source of risk in the form of counterparty risk, we need to also take into account correlations between interest rate risk and counterparty risk. This leads us to the concept of wrong-way risk (WwR). wWR refers to the additional risk that arises when the underlying portfolio and the default of the counterparty are correlated in the worst possible way, i.e. when the portfolio value from bank B's perspective is positively correlated with the default probability of the counterparty. This could lead to a scenario when the counterparty C defaults in a state of the world when it owes bank B the most.  

Third, to obtain volatility and correlation parameters we need to obtain such values under the risk-neutral probability. There are many counterparties that do not issue bonds or have CDS written on them. This makes it difficult to obtain default information about them. In practice, one can sometimes approximate the default probability under the risk-neutral measure with volatilities and correlations of default and other risks based on the real world measure.  

# 24.3.2 CVA AS AN OPTION  

The above discussion has been heuristic. Now we want to show rigorously that CVA can be inter-. preted as an option. For this purpose, we first make some assumptions. First, we assume that the. counterparty risk valuation problem is symmetric for counterparties B and C. This means that the total value of the position for B as valued at a given time, including counterparty risk, is the opposite of the total value of the position valued by C at the time. Second, as in Figure 24.1 we continue to. make the unrealistic unilateral default assumption (UDA) and assume that bank B is default free. We will allow for bilateral default and relax the UDA later in the chapter. The example with only one defaultable counterparty is already sufficient to explain the fundamental financial engineering issues that arise when dealing with counterparty risk. Third, we assume that there are no collateral agreements or other guarantees in place. Fourth, our framework assumes that the default risk is charged. upfront to counterparty C and is therefore included in the risk-neutral valuation framework..  

In this section, we will derive a general formula for unilateral counterparty risk valuation. We will see that the price in the presence of counterparty risk can be expressed as the default-free price minus a discounted option term in scenarios of early default multiplied by the loss given default. We will present a Monte Carlo simulation to calculate the CVA for a bank that has multiple IRSs with several. different counterparties. The example will assume independence between interest rates and credit spreads (default intensities). This implies that, for simplicity, we are abstracting away from WwR.4.  

In what follows we present the calculations from the point of view of the investor, that is bank B. We continue to use the risk-neutral valuation framework which implies that expectations $E_{t}$ are taken under the risk-neutral probability measure $(Q)$ . We follow Brigo et al. (2013) and use $\pmb{\Pi}(\pmb{u},\pmb{s})$ to denote the net cash flows of a generic claim as seen from the perspective of bank B and traded. with the counterparty $\mathrm{^C}$ between time $u$ and time $s$ , and discounted back to time $u$ 5 We define the. default-free NPV at time $t$ as $\mathrm{NPV}(t)=E_{t}[\pi(t,T)]$ . In the context of the discussion of Figure 24.1 we used the term exposure. More formally, we can define exposure at time $t$ for a position with a final maturity $T$ and cash flows $\pmb{\Pi}(\pmb{t},\pmb{T})$ as  

$$
\mathbf{Ex}(t)=(E_{t}[\varPi(t,T)])^{+}=(\mathbf{NPV}(t))^{+}.
$$  

To incorporate counterparty risk, we denote the payoff with a defaultable counterparty as ${\overline{{\cal U}}}(t,T)$ and define it as follows:  

$$
\overline{{\pi}}(t,T)=1_{\{\tau>T\}}\pmb{\Pi}(t,T)+1_{\{t<\tau\leq T\}}[\pmb{\Pi}(t,\tau)+\pmb{D}(t,\tau)(\mathbf{REC}(\mathbf{NPV}(\tau))^{+}-(-\mathbf{NPV}(\tau))^{+})].
$$  

Equation (24.3) shows that if there is no default, that is $\tau>T$ , then we obtain the risk-neutral valua-. tion formula $\pi(t,T)$ that we used throughout the book up until now. The remaining components of the right-hand side of Eq. (24.3) can be interpreted as consisting of the payments due before default occurs $(\boldsymbol{\Pi}(t,\tau))$ , the default-free stochastic discount factor at time $t$ for maturity $\tau(D(t,\tau))$ , and two terms with embedded options in the form of a positive recovery value $({\bf R E C}({\bf N P V}(\tau))^{+})$ to be received by bank $\mathbf{B}$ if the net present value. $\mathbf{NPV}(\tau)$ is positive and a payment from $\mathbf{B}$ to $\mathrm{^C}$ if the NPV is negative..  

# 24.3.2.1 Close-out proceedings  

When counterparty C defaults, close-out proceedings begin. These are governed by the regulations and ISDA rules. As part of the close-out process the residual value of the contract to bank B is  

![](images/74b73e42f849afe562a0a4cd52865ffded3c60ba66d9f2982b810de8a8822f8c.jpg)  

# FIGURE 24.2  

Counterparty risk adds optionality.  

determined. If it is positive, the bank will receive a payment depending on the recovery rate and if it is negative, the bank will make a payment. When calculating the loss arising from the counterparty's default one assumes that the bank enters into a similar contract with another counterparty so that it maintains its market position. The banks' market position is unchanged after replacing the contract. The loss is a function of the contract's replacement cost at the time of default. There are therefore two scenarios:  

Scenario 1 (the contract value is positive for bank B at the time of default): In this case B closes out the position with C by paying it the market value of the contract. At the same time B enters into a similar contract with another counterparty and receives the market value of the contract, which implies that the net loss to B is zero. Scenario 2 (the contract value is positive for bank B at the time of default): In this case B. closes out the position with C but does not receive any payment from the defaulting counterparty C. Since B enters into a corresponding contract with another counterparty, B suffers a net loss equal to the market value of the contract.  

Figure 24.2 illustrates how the market value of the contract fluctuates over time for one assumed path. Scenarios 1 and 2 imply that the exposure of a bank that enters a derivative transaction with a counterparty is the maximum of contract $\ddot{\iota}^{\flat}$ s market value or zero, which reflects the embedded optionality.  

The above equation highlights the embedded optionality. Brigo et al. (2013) show that one can. take expectations under the risk-neutral measure of Eq. (24.3) and obtain after some manipulations the following price of the payoff with maturity. $T$ under counterparty risk:  

$$
E_{t}(\overline{{\pi}}(t,T))=E_{t}[\pi(t,T)]-E_{t}[\mathbf{LGD}\times\boldsymbol{1}_{\{t<\tau\leq T\}}D(t,\tau)((\mathbf{NPV}(\tau))^{+})].
$$  

The second term on the right-hand side of Eq. (24.4) can be interpreted as the counterparty risk adjustment. We can write Eq. (24.4) as the default-free net present value minus the unilateral CVA:  

$$
E_{t}(\overline{{\Pi}}(t,T))=E_{t}[\Pi(t,T)]-U_{\mathrm{CVA}}(t,T)
$$  

Since the loss given default (LGD) is equal to 1 minus the recovery rate, we can also write the unilateral CVA in terms of the exposure $\mathbf{Ex}(\tau)$ at time $t$  

$$
U_{\mathrm{CVA}}(t,T)=E_{t}[(1-{\bf R E C})\times D(t,\tau)\times1_{\{t<\tau\leq T\}}\times{\bf E x}(\tau)]
$$  

# 24.3.3 COUNTERPARTY RISK AND UNILATERAL CVA IN A SINGLE IRS  

To provide an illustration of the application of the CVA concept, we will consider a simple IRS. As in Figure 24.1, we continue to assume that bank $\mathbf{B}$ pays a fixed rate. $\pmb{S t}_{0}$ and receives a floating. interest rate $L$ from counterparty C. We further assume that the notional amount $N$ is equal to 1. As. discussed in Chapter 14, the fair (forward swap) rate $\pmb{S}_{t_{0}}$ at time $t_{0}$ without counterparty risk is defined as the rate at which the present value of the fixed leg and floating legs payments is the same. For the 3-year paper swap in Figure 24.1, the discounted payoff IRS is  

$$
\sum_{i=2}^{4}D(t_{0},t_{i})\delta N\big(L(t_{i-1},t_{i})-s_{t_{0}}\big)
$$  

We can denote the NPV at time $t_{0}$ of an IRS without default risk that starts at time $t_{1}$ and has a. maturity of date of $t_{4}$ as $\pi_{\mathrm{IR}}(t_{0},t_{4})$ . Since bank $\mathbf{B}$ is paying fixed and receiving floating payments. from counterparty $\mathrm{^C}$ ,introducing the possibility that. $\mathrm{^C}$ may default implies that the correct swap. rate to be paid as part of the fixed leg with counterparty risk should be lower than the rate without counterparty risk since the fixed rate payer is compensated for the additional risk in this way. If we. apply Eq. (24.4) to the IRS example the net present value from the perspective of. $\mathbf{B}$ with counterparty risk becomes:  

$$
\overline{{I}}_{\mathrm{IR}}(t_{0},t_{4})=I I_{\mathrm{IR}}(t_{0},t_{4})-U_{\mathrm{CVA}}(t_{0},t_{4})
$$  

where $U_{\mathbf{CVA}}(t_{0},t_{4})$ is again the unilateral credit valuation adjustment (UCVA) due to default. It can be shown that $U_{\mathbf{CVA}}(t_{0},t_{4})$ can be rewritten as  

$$
U_{\mathrm{CVA}}(t_{0},t_{4})=\mathbf{LGD}\times E_{t_{0}}\left[1_{\{t_{0}<\tau\leq t_{4}\}}D(t_{0},\tau)((\mathbf{NPV}(\tau))^{+})\right]
$$  

or  

$$
U_{\mathrm{CVA}}(t_{0},t_{4})=\mathrm{LGD}\times\int_{t_{1}}^{t_{4}}P S\left(t_{0},u,t_{4},s_{t_{0}},\sigma_{u,t_{4}}\right)d_{u}P^{Q}\{\tau\leq u\}
$$  

In Eq. (24.10), $\begin{array}{r}{\int_{t_{1}}^{t_{4}}P S\left(t_{0},u,t_{4},K,s_{t_{0}},\sigma_{u,t_{4}}\right)}\end{array}$ represents the price at time $t_{0}$ of a swaption with maturity $u$ , strike price $K.$ underlying forward swap rate $\pmb{S t}_{0}$ , volatility $\sigma_{u,t_{4}}$ , and underlying swap with final maturity $t_{4}$  

The intuition for the result in Eq. (24.10) is straightforward. The key assumption is that the default time $\boldsymbol{\tau}$ and interests rates are independent. Moreover, the residual net present value is a forward starting IRS starting at time $\boldsymbol{\tau}$ . Therefore the option on the residual NPV can be interpreted as a sum of. swaptions with maturities spanning the possible range of default times with weights equal to riskneutral probabilities $P^{Q}$ of defaulting around each time value. To value default-risky assets, it is. essential to introduce the default times and default probabilities in the pricing framework. CDS are one liquid source of market risk-neutral default probabilities. An alternative would use credit spreads implied by corporate bond prices to calibrate the default probability. The resulting estimates may differ due to the CDS-bond basis discussed in Chapter 18. In Chapters 18 and 19, we have seen that different models can be used to calibrate CDS data to back out default probabilities. In this chapter, we will use reduced-form survival probability/hazard function models, but the end of chapter references show how structural models can be used to address counterparty risk.  

# 24.3.4 NUMERICAL CVA EXAMPLE FOR IRS PORTFOLIO  

We illustrate the calculation of unilateral CVA for IRSs in the context of a case study.  

# EXAMPLE  

Consider a bank B that holds a portfolio of vanilla interest rates swaps with five counterparties. The time $t_{0}$ is assumed to be December 14, 2007. We apply the unilateral CVA formula in Eq. (24.5) to calculate the CVA for bank B. Bank B enters into a total of 30 interest rates swaps with the five counterparties. The number of swaps and swap maturities per counterparty is as follows:  

Counterparty 1: Six swaps with maturities ranging from June 15, 2009 to June 23, 2012. Counterparty 2: Two swaps with maturities ranging from May 12, 2012 to December 4, 2014. Counterparty 3: Three swaps with maturities ranging from July 12, 2010 to February 13, 2012.   
Counterparty 4: Seven swaps with maturities ranging from June 2, 2009 until July 20, 2014. Counterparty 5: Twelve swaps with maturities ranging from January 8, 2009 until June 5, 2014.   
One can calculate the unilateral CVA by following the four steps:.   
Step 1 (Scenario Generation): We simulate many future interest rate paths or scenarios which are the underlying risk factors for the swaps.   
Step 2 (Instrument Valuation): For each path in step 1 we value the underlying swap portfolio and derive future NPV(t) distributions for each trade within the portfolio..   
Step 3 (Portfolio Aggregation): For each counterparty and according to the netting agreement in place we aggregate the NPV(t) distributions of its trades to derive the NPV(t) distribution of the portfolio.   
Step 4 (Exposure Calculation): Then, for each counterparty we calculate the exposure using Equation (24.2) and we discount (scenario consistently) to. $t_{0}$ . We calculate the expected discounted exposure by simply taking the average of the discounted exposures at every $t.$ Step 5 (Probability Weighting): We weight the expected exposures by the default probabilities. The default probabilities are extracted from CDS market quotes..  

<html><body><table><tr><td colspan="6">Table 24.1 Assumed Term Structured of CDS Quotes for Each Counterparty</td></tr><tr><td>Date</td><td>CP1</td><td>CP2</td><td>CP3</td><td>CP4</td><td>CP5</td></tr><tr><td>March 20,2008</td><td>140</td><td>85</td><td>115</td><td>170</td><td>140</td></tr><tr><td>March 20,2009</td><td>185</td><td>120</td><td>150</td><td>205</td><td>175</td></tr><tr><td>March 20,2010</td><td>215</td><td>170</td><td>195</td><td>245</td><td>210</td></tr><tr><td>March 20,2011</td><td>275</td><td>215</td><td>240</td><td>285</td><td>265</td></tr><tr><td>March 20,2012</td><td>340</td><td>255</td><td>290</td><td>320</td><td>310</td></tr></table></body></html>  

![](images/e518330d4cc316b2f6a17ec9e687033692465c427bc2e4f0f1a42a960cec96e6.jpg)  

# FIGURE 24.3  

Default probability curves for each counterparty.  

Table 24.1 shows the assumed term structure of CDS quotes for each counterparty (CP1, CP2, ..., CP5) as of December 2007. Based on the CDS quotes in Table 24.1, we can extract default probabilities which are shown in Figure 24.3. At date. $t_{0}$ , each swap in the portfolio. has a value close to zero. Figure 24.4 shows the assumed yield curve at settle date. $t_{0}$ (December 14, 2007) for maturities of 3 months, 6 months, 1 year, 5 years, 7 years, 10 years,.  

![](images/21ffe5a39fbebdb56ddbe14ab0d13497808a6ac2b16fc43f1afed09b6d424b8c.jpg)  

# FIGURE 24.4  

Yield curve at settle date.  

20 years, and 30 years. As we see the yield curve is upward sloping for all maturities until   
2027 and then becomes hump-shaped for the last 10 years.  

To implement Step 2 described above, the example uses the Hull-White single factor model to simulate the value of the swap contracts. Figure 24.5 shows one scenario for the yield curve evolution from 2007 until 2015.  

As part of Step 3, we calculate the mark-to-market value of each swap contract at each future simulation date. Figure 24.6 shows the mark-to-market values of the 30 swap contracts for one simulated scenario. As expected at time $t_{0}$ , the swap contracts are valued close to zero.  

If we aggregate across all 30 swap contracts at each point in time for a given simulated path, we obtain the simulated path of the entire portfolio. The exposure of a particular contract $i$ at time $t$ is the maximum of the contract value and O. To better visualize the exposure profile, we can evaluate certain statistics of the exposure distribution at each simulation date. One can calculate the expected exposure profile, for example, by computing the expectation of each exposure at each simulation date. If we also discount the expected exposure, we can calculate the discounted expected exposure as reported in Figure 24.7.  

It is clear from Figure 24.7 that the (discounted) expected exposure changes over time.. There are two offsetting effects that determine the exposure profile over time: the diffusion effect and the amortization effect. The longer a simulation path is the greater the resulting  

![](images/f725ef7f76ff481881f5dde2769decbaa361106755ae6a16c9683ca84e4e71ba.jpg)  

# FIGURE 24.5  

Yield curve evolution for one scenario.  

![](images/6232341948fbff8245b3eec6b091e85205ddfc600035bf0b5ae966ae5cf719c1.jpg)  

# FIGURE 24.6  

Swap prices for one scenario.  

![](images/526f4a3fc8d4b5922abf44c777dbdbf2171e4b8ab05dabbb80a8d43adcba7e74.jpg)  

# FIGURE 24.7  

Discounted expected exposure for each counterparty.  

variability in the risk factor (such as interest rates) and hence the further away the future. value is from the current value. At the same time as the simulation path moves towards maturity of the contract, the value tends to decrease the exposure over time, since it reduces the remaining cash flows that are exposed to default. The two effects are offsetting since the diffusion effect increases the credit exposure and the amortization effect decreases it over. time. On the one hand, for FX forwards and other single cash flow products, the potential exposures peak at the maturity of the transaction since the exposure is purely driven by the diffusion effect. For products with multiple cash flows, on the other hand, such as the IRS, the potential exposure usually peaks at one-third to one half of the way into the life of the. transaction according to Pykthin and Zhu (2007). Figure 24.7 shows that this is also the case in our example with a portfolio of 30 IRSs.  

The exposure profile does not just depend on the asset class and instrument but also on the. underlying risk factors and the point in the market cycle. For example, when the yield curve is upward sloping, the exposure is greater for a payer swap than for a corresponding receiver swap, since the fixed payments in the early periods are greater than the floating payments. This leads to positive forward values on the payer swap. The opposite is true if the yield curve is downward sloping. We can see from Figure 24.4 that the yield curve was upward sloping in our example and the exposure profile is indeed as predicted. One of the uses of exposure profiles is for the purpose of calculating economic and regulatory capital, pricing and hedging counterparty risk as well as verifying compliance with credit limits.  

<html><body><table><tr><td colspan="6">Table24.2 CVA for Each Counterparty</td></tr><tr><td>Counterparty</td><td>CP1</td><td>CP2</td><td>CP3</td><td>CP4</td><td>CP5</td></tr><tr><td>CVA</td><td>$2228.36</td><td>$2487.60</td><td>$920.39</td><td>$5478.50</td><td>$5859.30</td></tr></table></body></html>  

Finally by using the default probabilities from Figure 24.3, we can calculate the unilateral CVA with respect to each counterparty. These are reported in Table 24.2.  

The above example illustrates the calculation of unilateral CVA for a portfolio of simple interest rates swaps. For reasons of space we cannot cover the CVA examples for other asset classes such as credit, commodities, equities, or FX, but the references at the end of the chapter include such examples.  
