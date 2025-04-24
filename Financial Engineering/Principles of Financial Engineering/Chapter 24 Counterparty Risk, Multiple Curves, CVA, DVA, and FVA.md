# COUNTERPARTY RISK, MULTIPLE CURVES, CVA, DVA, AND FVA  

# 24  

# CHAPTER OUTLINE  

24.1 Introduction .. . 827   
24.2 Counterparty Risk.. . 829   
24.3 Credit Valuation Adjustment. . 831   
24.3.1 Counterparty Risk Example and CVA .. . 831   
24.3.2 CVA as an Option.... 833   
24.3.2.1 Close-out proceedings . 834   
24.3.3 Counterparty Risk and Unilateral CVA in a Single IRS... . 836   
24.3.4 Numerical CVA Example for IRS Portfolio . 837   
24.4 Debit Valuation Adjustment... .. 842   
24.5 Bilateral Counterparty Risk ... . 843   
24.6 Hedging Counterparty Risk.. 843   
24.6.1 CVA and DVA Hedging in Practice ... 844   
24.6.2 Contingent CDS.. 845   
24.7 Funding Valuation Adjustment ... .. 845   
24.8 CVA Desk... . 846   
24.9 Choice of the Discount Rate and Multiple Curves ... . 847   
24.10 Conclusions.. .. 849   
Suggested Reading .. .. 849   
Exercises .. .. 850   
MATLAB Exercise . 850  

# 24.1 INTRODUCTION  

In this chapter, we review recent innovations in financial engineering that attempt to better incorporate counterparty risk into derivatives pricing. The topics covered in this chapter are very much at the forefront of financial engineering practice and derivatives research. In previous chapters, we showed how basic principles such as swap cash flow engineering, option valuation, and dynamic replication can be used to construct and value more complex products. Our hope is that the reader now appreciates the commonality in the approaches to different asset classes and financial engineering problems. In this chapter, we will see how some of the tools that we studied earlier can be used to better account for counterparty risk. We will see that it is possible to model and incorporate counterparty risk in a derivatives transaction by applying several financial engineering tools that we encountered before including option valuation and CDS. In particular, credit valuation adjustment (CVA) is shown to resemble an option on the residual value of the portfolio with a random maturity given the default time of the counterparty. The default probability and default intensity for the counterparty can be backed out from CDS spreads. Thus some approaches to counterparty risk build on credit risk financial engineering tools such as CDS and structural models of default that we saw in Chapters 18 and 19. Some collateral agreements allow the choice of collateral and this choice leads to an embedded option. This optionality has recently been addressed by ISDA’s so-called SCSA (standard credit support annex). Finally, some solutions that attempt to hedge counterparty risk build on CDO structuring ideas that we encountered in Chapter 21. Thus, as in previous chapters we can use basic financial engineering principles to address counterparty risk.  

Incorporating counterparty risk-related adjustments significantly changes pricing formulae for derivatives and in practice it significantly changes valuations and behavior by market makers whose perspective is central to this book. The reason why we chose not to deal with counterparty risk by asset class in each chapter is that we first needed to develop the option valuation, CDS and CDO toolkit that we apply to address counterparty risk. Therefore, despite their importance, it is best to deal with more advanced counterparty risk issues at the end of the book so that the reader has had time to absorb the tools studied in the previous chapters.  

Throughout this book, we have used financial engineering tools that price derivatives as if we lived in a world without counterparty risk. Counterparty risk affects many aspects of financial markets and banking including but not limited to derivatives pricing. First, incorporating counterparty risk has implications for financial derivatives pricing and the organization of banks. Many banks now make adjustments to the default-free derivatives that reflect the risk of their counterparty defaulting, so-called CVAs.1 The principle of CVA is similar to that of a price discount for default risk assets in the sense that the value of a generic claim traded with a counterparty subject to default risk is always smaller than the value of the same claim traded with a counterparty having a null default probability. We discuss a case study that shows how CVA can be calculated for a portfolio of interest rates swaps. It is beyond the scope of this book to show how counterparty risk changes the pricing of derivatives for every asset class but we provide references at the end of the chapter that guide the interested reader to such applications.  

The increasing attention that is being paid to counterparty risk led to an expansion in the role and workload of so-called CVA desks in banks, a functional unit that did not exist in many banks a few years ago. Banks also make adjustments arising from the bank’s own default risk in the form of debit valuation adjustments (DVAs). Finally funding costs affect the valuation of derivatives and this is reflected in so-called funding valuation adjustments (FVAs). Therefore, the price of a derivative that incorporates counterparty risk can be decomposed in the default-free price plus an adjustment related to CVA, DVA, and FVA. The modeling choices related to CVA, DVA, and FVA are extensive and they imply that there is a wide dispersion in their application between banks. In previous chapters, we applied the overarching finance principle that the price of an asset should depend on the risk of the asset and be discounted by a discount rate that reflects this risk. However, in practice different borrowers have different funding costs and market practice is moving towards using different discount rates that reflect differences in funding costs which represents a breach of the fundamental principle. As a result of counterparty risk adjustments there is no such thing as a fair value for a derivatives transaction since the value will depend on the counterparty. Moreover, counterparty risk introduces a new source of model risk. We had seen the prevalence of Black Scholes Merton option pricing model approaches, the Merton structural model of default, and the standard Gaussian copula market model. Our discussion will show that it is even conceptually not clear whether such a standard model can be found to reflect counterparty risk valuation in practice.  

Second, counterparty risk affects capital requirements. In Basel II, there was a credit VaR charge related to counterparty risk. The most recent Basel III proposals require that capital requirements reflect risk that arises from mark-to-market losses related to CVA. However, these proposals do not allow for DVA which leads to a divergence between the treatment of counterparty risk from a capital charge regulation perspective and a derivatives pricing perspective.  

Third, accounting standards (including IFRS and US GAAP) require credit risk to be reflected in the fair value measurement of derivatives. This has had multibillion dollar profit and loss implications for banks as they report the effects of DVA and CVA in their financial accounts.  

Finally in this chapter, we will find that this discussion is everything but theoretical. These issues have transformed market practice, led to gains and losses for banks of the order of magnitude of several billion dollars over the last years and also created new professional opportunities and functions in the financial sector such as CVA desks.  

The issue of counterparty risk also affects the choice of the discount rate that is used to discount cash flows under the risk-neutral measure. Typically LIBOR was used as a proxy for the riskless rate but after the GFC market practice has moved to the usage of OIS rates as a discount rate in collateralized transactions. This is partly due to the fact that LIBOR rates were significantly higher than OIS rates as a result of the counterparty risk that was priced into LIBOR rates. The move to OIS rates has three fundamental implications for derivatives pricing which we discuss in this chapter.  

The topic of counterparty risk in financial engineering is a vast area and this chapter can only provide a brief summary. However, our focus is, as throughout the book, on showing how our existing financial engineering toolkit can be used to address these challenges and what the most important valuation and risk management issues are.  

# 24.2 COUNTERPARTY RISK  

Counterparty risk refers to the risk that a counterparty entering a transaction may default and not honor its payment obligations. In Chapter 2, we discussed how central clearing and CCPs can mitigate the effects of counterparty risk. Therefore, the counterparty risk associated with exchangetraded derivatives, which are always centrally cleared with CCPs, and with centrally cleared OTC transactions is remote since a clearing house guarantees the cash flows promised by the derivative to the counterparties.2 However, the majority of derivatives transactions are not centrally cleared which makes counterparty risk adjustments widespread and economically important. How large is the noncentrally cleared derivatives market that requires counterparty risk adjustments? According to recent BIS 2013 Triannual Survey, the OTC segment accounts for around $90\%$ of the $\$750$ trillion derivatives market in terms of notional amount outstanding.3 Moreover, only approximately onethird of the OTC’s market’s notional is cleared via CCPs. Based on the above numbers, we estimate that roughly $\$440$ trillion of the derivatives is not centrally cleared based on 2013 numbers.  

Practitioners were aware of counterparty risk before the GFC, but, compared to other risks, such as market and credit risk, it was considered of second-order importance. There is however evidence that counterparty risk is of first-order importance. The following two motivating examples illustrate counterparty risk-related concepts that we will explain in detail in this chapter. First, mark-tomarket losses due to counterparty risk can exceed mark-to-market losses due to market or credit risk at times as the following reading illustrates.  

# EXAMPLE  

Under Basel II, the risk of counterparty default and credit migration risk were addressed but mark-to-market losses due to credit valuation adjustments (CVA) were not. During the financial crisis, however, roughly two-thirds of losses attributed to counterparty credit risk were due to CVA losses and only about one-third were due to actual defaults.  

(Bank for International Settlements, 2011)  

Second, recent profits reported by major banks reflected CVA and DVA adjustments that amount to several billion dollars. The following is just one recent example.  

# EXAMPLE  

Goldman Sachs was the first large U.S. bank to report a third-quarter loss so far this earnings season, and   
its loss was due, in part, to its decision to hedge a potentially large accounting gain. [. . .] The company hedged potential gains from its debit valuation adjustment, or DVA, by taking offsetting   
positions through insurance-like contracts called credit default swaps on a basket of other financials. [. . .] Goldman’s DVA gains in the third quarter totaled $\$450$ million, about $\$300$ million of which was   
recorded under its fixed income, currency and commodities trading segment and another $\$150$ million   
recorded under equities trading. That amount is comparatively smaller than the $\$1.9$ billion in DVA gains that J.P. Morgan Chase and   
Citigroup each recorded for the third quarter. Bank of America reported $\$1.7$ billion of DVA gains in its   
investment bank. All three banks were profitable and got a boost from the DVA gains, an accounting   
phenomenon that can reverse in subsequent quarters, given the direction of bond spreads. (Wall Street Journal, Deal Journal blog, October 18, 2011, “Goldman Sachs Hedge  

Way to Less Volatile Earnings” by Liz Moyer and Katy Burne)  

Both of these examples illustrate how important CVA and DVA are in practice. We will discuss these concepts and how the derivatives industry has become progressively sophisticated in adjusting for counterparty risk in further detail below. Note that the formulae presented in this chapter are for uncollateralized derivatives transactions, but they can be generalized to collateralized deals too, where the CVA will be smaller and broadly speaking the option term will not be on the residual NPV at default but on the part of the residual NPV at default (if any) that will not be covered by collateral. This can be due to sudden profit and loss swings, possibly caused by the counterparty default itself or gap risk.  

# 24.3 CREDIT VALUATION ADJUSTMENT  

Throughout this book, we have assumed that there is no default risk in derivatives transactions. For example, in the Black Scholes model we assumed that each counterparty will honor its obligations and that neither will default. The assumption that large financial institutions are default free is not realistic. For example, in 2008, eight credit events on financial institutions occurred in 1 month (Lehman Brothers, Fannie Mae, Freddie Mac, Washington Mutual, Landsbanki, Glitnir, Kaupthing, and Merrill Lynch).  

# 24.3.1 COUNTERPARTY RISK EXAMPLE AND CVA  

It was not just in the valuation of forwards, options, and credit default swaps that we assumed counterparty risk away. In our discussion of interest rate swaps (IRSs) in Chapter 3, we also did not consider the risk that a counterparty may default. How does counterparty risk affect the valuation of a simple IRS? Let’s assume an IRS with a notional amount of $N$ and maturity $T=t_{4}$ , between bank B and a corporate counterparty C where B pays fixed and C pays floating. Figure 24.1a illustrates the cash flows if we assume that B and C cannot default. Let’s continue to assume that B is risk free for now, but let’s allow for the possibility of default by $\mathbf{C}$ at an unknown time $\tau$ . This is shown in Figure 24.1b. For illustration we assume that the default occurs at some point between dates $t_{3}$ and $t_{4}$ . Apart from the trivial scenario of no default (that is $\tau>T$ ), we can distinguish two basic scenarios:  

Scenario 1 (default and B has positive exposure): C defaults at some point $\tau$ where $t_{3}<\tau<t_{4}$ , and the net present value (NPV) of the remaining payments from C to B is positive, that is, B has positive exposure. In this case, B receives only a recovery fraction REC of the net present value NPV. Scenario 2 (default and B has negative exposure): If C defaults at some point $\tau$ where $t_{3}<\tau<t_{4}$ , and the NPV of the remaining payments from C to $\mathbf{B}$ is negative, then B has negative exposure. In this case, B pays the liquidator of C a positive amount.  

The example in Figure 24.1 illustrates the important insight that it is not just the stochastic default time that is important but also the sign and magnitude of the NPV of any remaining payments at default. These are features that any adjustment for counterparty risk must take into account.  

There are several ways of incorporating counterparty risk into derivatives pricing. CVA is one such adjustment and it is simple and intuitive. The idea behind CVA is that if we enter into a portfolio derivative transaction with a counterparty, that counterparty might default and it might default at a time when we have an exposure, that is the value of the transaction to us is positive and negative to the counterparty. This has to be incorporated into the valuation of the transaction. First, we value the  

![](3b96d97faee767f62c3d47694da2dfd9da91c4e2a8ca7abdc1f770d3ef9e64eb.jpg)  

![](20a013ab82210633756932e12f27ab7b111ade725db6a0a1eed8a21762c68ece.jpg)  

# FIGURE 24.1  

IRS cash flows with and without counterparty risk.  

transaction assuming that neither we nor the counterparty would default. Then we will subtract the CVA, or credit valuation adjustment, to reflect the possibility that the counterparty might default. Even before going into the details of CVA, it is clear that the above logic implies that another adjustment may be required for the fact that we could also default on the payment obligations to the counterparty. This is called DVA and we will discuss it in a subsequent section.  

For illustration, we could assume that in the example above the counterparty C can be either the European Central Bank (ECB) or a Greek commercial bank in 2010. Clearly the ECB and the Greek bank had very different counterparty risks in 2010, as our discussion of sovereign default swaps in Chapter 18 showed. Incorporating counterparty risk into the evaluation of the payoffs from the transaction will necessarily imply that we will condition on whether a default by the bank’s counterparty will occur or not. Intuitively, the inclusion of the risk of the bank’s counterparty defaulting will add optionality into the payoff from the bank’s perspective.  

The CVA adjustment can be positive or negative. Consider an example involving bank B and its counterparty, a corporate client C. If C defaults and the present value of the portfolio at default is positive from the perspective of the surviving party (bank B), then B only gets a fraction of the portfolio equal to the recovery rate from C. It is also possible that the present value of the portfolio is negative from the perspective of the surviving party B. In this case, B has to pay the liquidators of the defaulted corporate C. This logic leads to a price of the derivatives transaction with counterparty risk $(P_{\mathrm{with~CR}})$ that is equal to the value of the deal without counterparty risk $(P_{\mathrm{without~CR}})$ minus a positive adjustment, labeled CVA, which captures the above option:  

$$
P_{\mathrm{with}\mathrm{CR}}=P_{\mathrm{no}\mathrm{CR}}-\mathrm{CVA}
$$  

This adjustment looks relatively straightforward, but several complications arise in practice. First, even for some simple derivatives incorporating counterparty risk makes the valuation model dependent, even if under default-free pricing it was model independent. One of the simplest derivatives that we have seen is an IRS as discussed in Chapter 4. With counterparty risk, the IRS valuation needs to include an option on the residual value of the portfolio and to price such an option we require an interest rate option pricing model.  

Second, as we introduce a new source of risk in the form of counterparty risk, we need to also take into account correlations between interest rate risk and counterparty risk. This leads us to the concept of wrong-way risk (WWR). WWR refers to the additional risk that arises when the underlying portfolio and the default of the counterparty are correlated in the worst possible way, i.e. when the portfolio value from bank B’s perspective is positively correlated with the default probability of the counterparty. This could lead to a scenario when the counterparty C defaults in a state of the world when it owes bank B the most.  

Third, to obtain volatility and correlation parameters we need to obtain such values under the risk-neutral probability. There are many counterparties that do not issue bonds or have CDS written on them. This makes it difficult to obtain default information about them. In practice, one can sometimes approximate the default probability under the risk-neutral measure with volatilities and correlations of default and other risks based on the real world measure.  

# 24.3.2 CVA AS AN OPTION  

The above discussion has been heuristic. Now we want to show rigorously that CVA can be interpreted as an option. For this purpose, we first make some assumptions. First, we assume that the counterparty risk valuation problem is symmetric for counterparties B and C. This means that the total value of the position for B as valued at a given time, including counterparty risk, is the opposite of the total value of the position valued by C at the time. Second, as in Figure 24.1 we continue to make the unrealistic unilateral default assumption (UDA) and assume that bank B is default free. We will allow for bilateral default and relax the UDA later in the chapter. The example with only one defaultable counterparty is already sufficient to explain the fundamental financial engineering issues that arise when dealing with counterparty risk. Third, we assume that there are no collateral agreements or other guarantees in place. Fourth, our framework assumes that the default risk is charged upfront to counterparty C and is therefore included in the risk-neutral valuation framework.  

In this section, we will derive a general formula for unilateral counterparty risk valuation. We will see that the price in the presence of counterparty risk can be expressed as the default-free price minus a discounted option term in scenarios of early default multiplied by the loss given default. We will present a Monte Carlo simulation to calculate the CVA for a bank that has multiple IRSs with several different counterparties. The example will assume independence between interest rates and credit spreads (default intensities). This implies that, for simplicity, we are abstracting away from WWR.4  

In what follows we present the calculations from the point of view of the investor, that is bank B. We continue to use the risk-neutral valuation framework which implies that expectations $E_{t}$ are taken under the risk-neutral probability measure $(Q)$ . We follow Brigo et al. (2013) and use $\pmb{\pi}(\pmb{u},\pmb{s})$ to denote the net cash flows of a generic claim as seen from the perspective of bank B and traded with the counterparty $\mathrm{~C~}$ between time $u$ and time $s$ , and discounted back to time $u$ .5 We define the default-free NPV at time $t$ as $\mathrm{NPV}(t)=E_{t}[\pmb{I}(t,\pmb{T})]$ . In the context of the discussion of Figure 24.1 we used the term exposure. More formally, we can define exposure at time $t$ for a position with a final maturity $T$ and cash flows $\pmb{\pi}(t,T)$ as  

$$
\begin{array}{r}{\mathbf{Ex}(t)=(E_{t}[\boldsymbol{\Pi}(t,T)])^{+}=(\mathbf{NPV}(t))^{+}.}\end{array}
$$  

To incorporate counterparty risk, we denote the payoff with a defaultable counterparty as $\overline{{\boldsymbol{\pi}}}(t,\boldsymbol{T})$ and define it as follows:  

$$
\overline{{{\cal{I}}}}(t,T)=1_{\{\tau>T\}}\underline{{{\cal{I}}}}(t,T)+1_{\{t<\tau\leq T\}}[\underline{{{\cal{I}}}}(t,\tau)+D(t,\tau)({\bf{R E C}}(\mathrm{NPV}(\tau))^{+}-(-\mathrm{NPV}(\tau))^{+})].
$$  

Equation (24.3) shows that if there is no default, that is $\tau>T$ , then we obtain the risk-neutral valuation formula $\pmb{\pi}(t,\pmb{T})$ that we used throughout the book up until now. The remaining components of the right-hand side of Eq. (24.3) can be interpreted as consisting of the payments due before default occurs $(\boldsymbol{\pi}(t,\tau))$ , the default-free stochastic discount factor at time $t$ for maturity $\tau(D(t,\tau))$ , and two terms with embedded options in the form of a positive recovery value $(\mathbf{REC}(\mathbf{NPV}(\tau))^{+})$ to be received by bank $\mathbf{B}$ if the net present value $\mathbf{NPV}(\tau)$ is positive and a payment from $\mathbf{B}$ to $\mathbf{C}$ if the NPV is negative.  

# 24.3.2.1 Close-out proceedings  

When counterparty C defaults, close-out proceedings begin. These are governed by the regulations and ISDA rules.6 As part of the close-out process the residual value of the contract to bank B is  

![](61a4d4c724018832bf25de7da8ea26b6407e4a1751211780987741ccb789752f.jpg)  

# FIGURE 24.2  

Counterparty risk adds optionality.  

determined. If it is positive, the bank will receive a payment depending on the recovery rate and if it is negative, the bank will make a payment. When calculating the loss arising from the counterparty’s default one assumes that the bank enters into a similar contract with another counterparty so that it maintains its market position. The banks’ market position is unchanged after replacing the contract. The loss is a function of the contract’s replacement cost at the time of default. There are therefore two scenarios:  

Scenario 1 (the contract value is positive for bank B at the time of default): In this case B closes out the position with C by paying it the market value of the contract. At the same time B enters into a similar contract with another counterparty and receives the market value of the contract, which implies that the net loss to B is zero. Scenario 2 (the contract value is positive for bank B at the time of default): In this case B closes out the position with C but does not receive any payment from the defaulting counterparty C. Since B enters into a corresponding contract with another counterparty, B suffers a net loss equal to the market value of the contract.  

Figure 24.2 illustrates how the market value of the contract fluctuates over time for one assumed path. Scenarios 1 and 2 imply that the exposure of a bank that enters a derivative transaction with a counterparty is the maximum of contract $i^{\mathfrak{g}}$ s market value or zero, which reflects the embedded optionality.  

The above equation highlights the embedded optionality. Brigo et al. (2013) show that one can take expectations under the risk-neutral measure of Eq. (24.3) and obtain after some manipulations the following price of the payoff with maturity $T$ under counterparty risk:  

$$
E_{t}(\overline{{{I I}}}(t,T))=E_{t}[I I(t,T)]-E_{t}[\mathbf{LGD}\times\mathbf{1}_{\{t<\tau\leq T\}}D(t,\tau)(\left(\mathbf{NPV}(\tau)\right)^{+})].
$$  

The second term on the right-hand side of Eq. (24.4) can be interpreted as the counterparty risk adjustment. We can write Eq. (24.4) as the default-free net present value minus the unilateral CVA:  

$$
E_{t}(\overline{{I I}}(t,T))=E_{t}[I I(t,T)]-U_{\mathrm{CVA}}(t,T)
$$  

Since the loss given default LGD is equal to 1 minus the recovery rate, we can also write the unilateral CVA in terms of the exposure $\mathbf{Ex}(\tau)$ at time $t$ :  

$$
U_{\mathrm{CVA}}(t,T)=E_{t}[(1-\mathrm{REC})\times D(t,\tau)\times1_{\{t<\tau\leq T\}}\times\mathrm{{\bfEx}}(\tau)]\
$$  

# 24.3.3 COUNTERPARTY RISK AND UNILATERAL CVA IN A SINGLE IRS  

To provide an illustration of the application of the CVA concept, we will consider a simple IRS. As in Figure 24.1, we continue to assume that bank $\mathbf{B}$ pays a fixed rate $s_{t_{0}}$ and receives a floating interest rate $L$ from counterparty C. We further assume that the notional amount $N$ is equal to 1. As discussed in Chapter 14, the fair (forward swap) rate $s_{t_{0}}$ at time $\pmb{t}_{0}$ without counterparty risk is defined as the rate at which the present value of the fixed leg and floating legs payments is the same. For the 3-year paper swap in Figure 24.1, the discounted payoff IRS is  

$$
\sum_{i=2}^{4}D(t_{0},t_{i})\delta N\big(L(t_{i-1},t_{i})-s_{t_{0}}\big)
$$  

We can denote the NPV at time $t_{0}$ of an IRS without default risk that starts at time $t_{1}$ and has a maturity of date of $t_{4}$ as $\pmb{\Pi}_{\mathbf{IR}}(\pmb{t}_{0},\pmb{t}_{4})$ . Since bank $\mathbf{B}$ is paying fixed and receiving floating payments from counterparty $\mathbf{C}$ , introducing the possibility that $\mathbf{C}$ may default implies that the correct swap rate to be paid as part of the fixed leg with counterparty risk should be lower than the rate without counterparty risk since the fixed rate payer is compensated for the additional risk in this way. If we apply Eq. (24.4) to the IRS example the net present value from the perspective of $\mathbf{B}$ with counterparty risk becomes:  

$$
\overline{{T}}_{\mathrm{IR}}(t_{0},t_{4})=\cal{{H}}_{\mathrm{IR}}(t_{0},t_{4})-{\cal{U}}_{\mathrm{CVA}}(t_{0},t_{4})
$$  

where $U_{\mathrm{CVA}}(t_{0},t_{4})$ is again the unilateral credit valuation adjustment (UCVA) due to default. It can be shown that $U_{\mathrm{CVA}}(t_{0},t_{4})$ can be rewritten as  

$$
U_{\mathrm{CVA}}(t_{0},t_{4})=\mathbf{LGD}\times E_{t_{0}}\left[1_{\{t_{0}<\tau\leq t_{4}\}}D(t_{0},\tau)((\mathbf{NPV}(\tau))^{+})\right]
$$  

or  

$$
U_{\mathrm{CVA}}(t_{0},t_{4})=\mathbf{LGD}\times\int_{t_{1}}^{t_{4}}P S\left(t_{0},u,t_{4},s_{t_{0}},\sigma_{u,t_{4}}\right)d_{u}P^{\mathcal{Q}}\{\tau\leq u\}
$$  

In Eq. (24.10), $\begin{array}{r}{\int_{t_{1}}^{t_{4}}P S\left(t_{0},{u},t_{4},K,s_{t_{0}},\pmb{\sigma}_{{u},t_{4}}\right)}\end{array}$ represents the price at time $t_{0}$ of a swaption with maturity $u$ , strike price $K.$ , underlying forward swap rate $s_{t_{0}}$ , volatility $\sigma_{u,t_{4}}$ , and underlying swap with final maturity $t_{4}$ .  

The intuition for the result in Eq. (24.10) is straightforward. The key assumption is that the default time $\tau$ and interests rates are independent. Moreover, the residual net present value is a forward starting IRS starting at time $\tau$ . Therefore the option on the residual NPV can be interpreted as a sum of swaptions with maturities spanning the possible range of default times with weights equal to riskneutral probabilities $P^{Q}$ of defaulting around each time value. To value default-risky assets, it is essential to introduce the default times and default probabilities in the pricing framework. CDS are one liquid source of market risk-neutral default probabilities. An alternative would use credit spreads implied by corporate bond prices to calibrate the default probability. The resulting estimates may differ due to the CDS-bond basis discussed in Chapter 18. In Chapters 18 and 19, we have seen that different models can be used to calibrate CDS data to back out default probabilities. In this chapter, we will use reduced-form survival probability/hazard function models, but the end of chapter references show how structural models can be used to address counterparty risk.  

# 24.3.4 NUMERICAL CVA EXAMPLE FOR IRS PORTFOLIO  

We illustrate the calculation of unilateral CVA for IRSs in the context of a case study.  

# EXAMPLE  

Consider a bank B that holds a portfolio of vanilla interest rates swaps with five counterparties. The time $t_{0}$ is assumed to be December 14, 2007. We apply the unilateral CVA formula in Eq. (24.5) to calculate the CVA for bank B. Bank B enters into a total of 30 interest rates swaps with the five counterparties. The number of swaps and swap maturities per counterparty is as follows :  

Counterparty 1: Six swaps with maturities ranging from June 15, 2009 to June 23, 2012. Counterparty 2: Two swaps with maturities ranging from May 12, 2012 to December 4, 2014. Counterparty 3: Three swaps with maturities ranging from July 12, 2010 to February 13, 2012.   
Counterparty 4: Seven swaps with maturities ranging from June 2, 2009 until July 20, 2014. Counterparty 5: Twelve swaps with maturities ranging from January 8, 2009 until June 5, 2014.   
One can calculate the unilateral CVA by following the four steps:   
Step 1 (Scenario Generation): We simulate many future interest rate paths or scenarios which are the underlying risk factors for the swaps.   
Step 2 (Instrument Valuation): For each path in step 1 we value the underlying swap portfolio and derive future NPV(t) distributions for each trade within the portfolio.   
Step 3 (Portfolio Aggregation): For each counterparty and according to the netting agreement in place we aggregate the NPV(t) distributions of its trades to derive the NPV(t) distribution of the portfolio.   
Step 4 (Exposure Calculation): Then, for each counterparty we calculate the exposure using Equation (24.2) and we discount (scenario consistently) to $t_{0}$ . We calculate the expected discounted exposure by simply taking the average of the discounted exposures at every $t$ . Step 5 (Probability Weighting): We weight the expected exposures by the default probabilities. The default probabilities are extracted from CDS market quotes.  

<html><body><table><tr><td colspan="6"> Table 24.1 Assumed Term Structured of CDS Quotes for Each Counterparty</td></tr><tr><td>Date</td><td>CP1</td><td>CP2</td><td>CP3</td><td>CP4</td><td>CP5</td></tr><tr><td>March 20, 2008</td><td>140</td><td>85</td><td>115</td><td>170</td><td>140</td></tr><tr><td>March 20, 2009</td><td>185</td><td>120</td><td>150</td><td>205</td><td>175</td></tr><tr><td>March 20, 2010</td><td>215</td><td>170</td><td>195</td><td>245</td><td>210</td></tr><tr><td>March 20, 2011</td><td>275</td><td>215</td><td>240</td><td>285</td><td>265</td></tr><tr><td>March 20, 2012</td><td>340</td><td>255</td><td>290</td><td>320</td><td>310</td></tr></table></body></html>  

![](aab8f2b1883abf6696d7aaa8c88719bda3b030a71f954e4524d0d10127f115ce.jpg)  

# FIGURE 24.3  

Default probability curves for each counterparty.  

Table 24.1 shows the assumed term structure of CDS quotes for each counterparty (CP1, CP2, . . ., CP5) as of December 2007. Based on the CDS quotes in Table 24.1, we can extract default probabilities which are shown in Figure 24.3. At date $t_{0}$ , each swap in the portfolio has a value close to zero. Figure 24.4 shows the assumed yield curve at settle date $t_{0}$ (December 14, 2007) for maturities of 3 months, 6 months, 1 year, 5 years, 7 years, 10 years,  

![](67b54008c457d44d2335c339f49cc462690bbd51cd39719d931bb3817c35a5b1.jpg)  

# FIGURE 24.4  

Yield curve at settle date.  

20 years, and 30 years. As we see the yield curve is upward sloping for all maturities until   
2027 and then becomes hump-shaped for the last 10 years.  

To implement Step 2 described above, the example uses the Hull White single factor model to simulate the value of the swap contracts. Figure 24.5 shows one scenario for the yield curve evolution from 2007 until 2015.  

As part of Step 3, we calculate the mark-to-market value of each swap contract at each future simulation date. Figure 24.6 shows the mark-to-market values of the 30 swap contracts for one simulated scenario. As expected at time $t_{0}$ , the swap contracts are valued close to zero.  

If we aggregate across all 30 swap contracts at each point in time for a given simulated path, we obtain the simulated path of the entire portfolio. The exposure of a particular contract $i$ at time $t$ is the maximum of the contract value and 0. To better visualize the exposure profile, we can evaluate certain statistics of the exposure distribution at each simulation date. One can calculate the expected exposure profile, for example, by computing the expectation of each exposure at each simulation date. If we also discount the expected exposure, we can calculate the discounted expected exposure as reported in Figure 24.7.  

It is clear from Figure 24.7 that the (discounted) expected exposure changes over time. There are two offsetting effects that determine the exposure profile over time: the diffusion effect and the amortization effect. The longer a simulation path is the greater the resulting  

![](b7595ec9af16db95a5cd7b30ab51c16fe7ce441a0c906d21d5461fe235c2a5e9.jpg)  

# FIGURE 24.5  

Yield curve evolution for one scenario.  

![](a98aa95a8de6a35d9b2464f5a89d123eff3c7eb6ef2d9ae7975841a619c53cef.jpg)  

# FIGURE 24.6  

Swap prices for one scenario.  

![](bb4d23625ff0cae1e081e5f47c3def897098837498d8eda4173a0c80b4dedd86.jpg)  

# FIGURE 24.7  

Discounted expected exposure for each counterparty.  

variability in the risk factor (such as interest rates) and hence the further away the future value is from the current value. At the same time as the simulation path moves towards maturity of the contract, the value tends to decrease the exposure over time, since it reduces the remaining cash flows that are exposed to default. The two effects are offsetting since the diffusion effect increases the credit exposure and the amortization effect decreases it over time. On the one hand, for FX forwards and other single cash flow products, the potential exposures peak at the maturity of the transaction since the exposure is purely driven by the diffusion effect. For products with multiple cash flows, on the other hand, such as the IRS, the potential exposure usually peaks at one-third to one half of the way into the life of the transaction according to Pykthin and Zhu (2007). Figure 24.7 shows that this is also the case in our example with a portfolio of 30 IRSs.  

The exposure profile does not just depend on the asset class and instrument but also on the underlying risk factors and the point in the market cycle. For example, when the yield curve is upward sloping, the exposure is greater for a payer swap than for a corresponding receiver swap, since the fixed payments in the early periods are greater than the floating payments. This leads to positive forward values on the payer swap. The opposite is true if the yield curve is downward sloping. We can see from Figure 24.4 that the yield curve was upward sloping in our example and the exposure profile is indeed as predicted. One of the uses of exposure profiles is for the purpose of calculating economic and regulatory capital, pricing and hedging counterparty risk as well as verifying compliance with credit limits.  

<html><body><table><tr><td colspan="6">Table 24.2 CVA for Each Counterparty</td></tr><tr><td>Counterparty</td><td>CP1</td><td>CP2</td><td>CP3</td><td>CP4</td><td>CP5</td></tr><tr><td>CVA</td><td>$2228.36</td><td>$2487.60</td><td>$920.39</td><td>$5478.50</td><td>$5859.30</td></tr></table></body></html>  

Finally by using the default probabilities from Figure 24.3, we can calculate the unilateral CVA with respect to each counterparty. These are reported in Table 24.2.  

The above example illustrates the calculation of unilateral CVA for a portfolio of simple interest rates swaps. For reasons of space we cannot cover the CVA examples for other asset classes such as credit, commodities, equities, or FX, but the references at the end of the chapter include such examples.  

# 24.4 DEBIT VALUATION ADJUSTMENT  

Consider the example above that we discussed. From bank B’s perspective the price of the derivative was reduced by a positive CVA amount. The same adjustment seen from the perspective of the counterparty is called debit valuation adjustment (DVA). It is positive because the default of the counterparty C would lead to a discount on C’s payment obligation and this can be interpreted as a gain. In this case, we continue to assume that the bank B itself is still default free. The DVA is unilateral since only the default risk of the client is included. For the two counterparties to agree, we require that the adjustment to the risk-free price be the same, but that it is added by counterparty C and subtracted by bank B. In other words we require:  

$$
\mathrm{Unilateral}\mathrm{CVA}(\mathrm{Bank}B)=\mathrm{UnilateralDVA}(\mathrm{Corporate}C)
$$  

Although the concept of DVA looks simple, there are several complications in practice. First, it is difficult to monetize DVA in practice. Consider what would be required to do this. One would need to unwind trades to the counterparty to monetize DVA since it is the reduced NPV of one’s derivatives payment obligations to the counterparty. Prior to default this is practically impossible to achieve given that it would involve unwinding a complex derivatives portfolio. Second, it is important to note that the treatment of DVA for purposes of derivatives pricing is distinct from that for accounting purposes. As the second example in Section 24.2 has shown, DVA is a major element in financial reporting and there were recent instances when large banks such as Citibank saw their quarterly profit and loss reports change from a loss to a profit as the credit spreads of the banks widened. Although DVA is widely used to price new OTC derivatives, its accounting treatment is more ambiguous and many firms report DVA on a separate line and identify it as an accounting charge rather than a real profit and loss. Third, the treatment of DVA from a bank capital regulation perspective is also distinct from those for pricing and accounting purposes. Despite its use for accounting and derivatives pricing purposes, until recently the BIS explicitly excluded DVA from regulatory capital calculations. However, a recent Basel Committee on Banking Supervision consultative document discusses several options of recognizing DVA for capital purposes which implies the potential for a convergence between the accounting, regulatory, and derivatives pricing treatment of DVA.9  

# 24.5 BILATERAL COUNTERPARTY RISK  

So we have adopted the unilateral perspective. What would happen if both counterparties view each other as risky? For example, the corporate C could view bank B as risky. After the demise of Lehman Brothers in 2008 and multiple credit events involving financial institutions during the GFC this is a realistic scenario. The only way to deal with this situation is to allow both counterparties to include their own default besides the default of the counterparty into their valuation. This implies that each counterparty will subtract a positive CVA value from and add a positive DVA to the default risk-free price of the transaction. In other words, the CVA of one party will be the DVA of another party and vice versa. In the example above, we will obtain the following equation from bank B’s perspective,  

$$
P_{\mathrm{with\CR}}^{\mathrm{to\bank\B}}=P_{\mathrm{no\CR}}^{\mathrm{to\bank\B}}+\mathrm{DVA}_{\mathrm{Bank\B}}-\mathrm{CVA}_{\mathrm{Bank\B}}
$$  

From the perspective of corporate $\mathrm{^c}$ , the value of the deal has the opposite sign:  

$$
\begin{array}{r}{P_{\mathrm{{no}\ C R}}^{\mathrm{{to}\ b a n k\mathrm{{\bf~B}}}}=-P_{\mathrm{{no}\ C R}}^{\mathrm{{to}\ c o r p o r a t e\ C}}}\\ {\mathrm{DV}\mathrm{A}_{\mathrm{Bank\mathrm{{\bf~B}}}}=\mathrm{CV}\mathrm{A}_{\mathrm{Corporate\C}}}\\ {\mathrm{DV}\mathrm{A}_{\mathrm{Corporate\C}}=-\mathrm{CV}\mathrm{A}_{\mathrm{Bank\mathrm{{\bf~B}}}}}\end{array}
$$  

Equations (24.12) (24.15) imply that  

$$
P_{\mathrm{with~CR}}^{\mathrm{to~bank~B}}=P_{\mathrm{with~CR}}^{\mathrm{to~corporate~C~}}
$$  

This means that both counterparties agree on the price. It is common to refer to the difference (DVA-CVA) as the bilateral valuation adjustment (BVA). One of the complications that arises with BVA is that it requires agreeing on which counterparty defaults first, since when one counterparty defaults its CVA is triggered and the other parties are not.  

# 24.6 HEDGING COUNTERPARTY RISK  

The main objectives of hedging CVA and DVA are threefold. First, hedging CVA and DVA allows one to reduce the sensitivity of a bank’s profit and loss to changes in the credit spread of the counterparty or the banks’ own creditworthiness changes. Second, hedging allows to lock in the CVA position for the duration of the trade with the counterparty. Third, hedging allows a reduction of a CVA exposure. In practice, CVA hedging is not that simple since hedging jump to default risk is difficult and WWR can make separating counterparty risk from other risks impossible.  

# 24.6.1 CVA AND DVA HEDGING IN PRACTICE  

As we saw earlier, DVA and CVA adjustments can amount to billions of dollars in practice. The following reading illustrates this practice.  

# EXAMPLE  

“Asked by an analyst to explain why the company’s DVA gains were relatively muted, for a period in which its debt spreads also widened and which, in theory, should have led to a large DVA gain, Goldman Sachs Chief Financial Officer David Viniar said Tuesday that the company attempts to hedge using a basket of different financials. A Goldman spokesman confirmed that the company did this by selling credit default swaps on a range of financial firms. In selling CDS coverage, a firm is hoping to gain from an improvement in the credit quality of the underlying debt as evidenced by a narrowing in its risk spreads. Goldman wouldn’t say what specific financials were in the basket, but Viniar confirmed to the analyst asking the question that the basket contained “a peer group.”  

Most would consider peers to Goldman to be other large banks with big investment-banking divisions, including Morgan Stanley, J.P. Morgan Chase, Bank of America, Citigroup, and others.  

In Europe, a company could hedge against a range of banks at once through an index of credit default swaps called the iTraxx Europe Senior Financials, administered by Markit. But in the United States, there is no popularly traded index of CDS contracts on financials, so Goldman likely created a custom basket with another dealer.”  

(Wall Street Journal, Deal Journal blog, October 18, 2011, “Goldman Sachs Hedges Its Way to Less Volatile Earnings” by Liz Moyer and Katy Burne)  

The example above also showcases the role of credit derivatives as hedges for DVA gains. What is at first sight counterintuitive is that a deterioration in a bank’s credit quality can lead to accounting gains. Although Goldman Sachs denied using CDS on its own name this raised the issue of whether a bank could potentially increase its account profits by taking actions that would reduce its credit-worthiness.  

According to a recent Ernst and Young survey10 based on responses from 19 financial institutions, the most popular instruments to manage and hedge market and credit risk related to CVA are single-name CDS (used by 14 of the 19 respondents) and interest rate and FX products (14 users) to manage market and credit risk relating to CVA. The next most popular hedges are based on index-linked CDS (13 users) and volatility hedges (10 users), while bond-based hedging (8 users) and correlation products (7 users) as well as contingent CDS (CCDS) (6 users) are less popular. Some more recent and advanced approaches to deal with counterparty risk involve CVA-CDOs and margin lending.  

Although CDS can be used for CVA hedging, there are some problems associated with static CDS hedging. The payout from a CDS is fixed and only depends on whether the reference name defaults and not on the amount of the exposure to the counterparty. This can be partly addressed by dynamic hedging, that is adjusting the CVA position over time and depending on the amount of exposure that one has today. There is also a tradeoff between single-name and index CDS hedges. Single-name hedging is more precise in case of bad news affecting a single firm rather than broad market moves, but single-name CDS are not available for most counterparties as reference names. Index CDS hedges or other macro hedges are one practical alternative but they represent a rather imperfect hedge against bad news affecting a single firm.  

# 24.6.2 CONTINGENT CDS  

The above hedging limitations associated with vanilla CDS hedging have driven innovation in credit products such as CCDS. Whereas in a simple CDS, a credit event triggers the payment, in a CCDS, the trigger requires both a credit event and another specified event such as the level of a particular market or sector variable. A CCDS can be viewed as a derivative which contains an embedded knock-in option upon the default of the reference transaction. The economic rationale that leads to the development of the CCDS is that it eliminates the economic risk which arises from variations in the credit exposure of a counterparty as a result of deterioration in broader economic market forces. One of the caveats associated with CCDS is, however, that they are currently not standardized and this implies elevated contractual risks or deliverability risk compared to vanilla CDS. Moreover, in contrast to a vanilla CDS, a CCDS can currently only be used to create a static hedge and not a dynamic hedge, against the counterparty credit risk.  

# 24.7 FUNDING VALUATION ADJUSTMENT  

A final aspect of counterparty risk that needs to be taken into account relates to funding. When a trader manages a trading position, he or she must obtain cash in order to carry out different operations including (i) hedging the position and (ii) posting collateral. These operations have a cost and need to be funded. Accounting for this funding cost is called funding valuation adjustment. If we incorporate CVA, DVA, and FVA into the valuation of derivatives under counterparty risk, we obtain the following equation:  

$$
P_{\mathrm{with~CR}}^{\mathrm{to~bank~B}}=P_{\mathrm{no~CR}}^{\mathrm{to~bank~B}}+\mathrm{DVA}_{\mathrm{Bank~B}}-\mathrm{CVA}_{\mathrm{Bank~B}}-\mathrm{FVA}_{\mathrm{Bank~B}}
$$  

The practical implementation of FVA is not straightforward. The reason is that including funding costs leads to a recursive pricing problem that can be expressed as a backwards stochastic differential equation.  

The pre-GFC market practice related to funding was that collateral and funding were secondorder concerns when assessing the profit and loss of a trading desk. Banks were used to borrowing money by posting collateral via a variety of low-cost funding options. The borrowing cost was to a large extent offset by the interest paid on collateral by the receiving party. After the GFC, a fundamental shift occurred in the role of funding in the derivatives business since funding costs increased. What changed market practice is that the risk of credit lines being pulled if a firm is perceived as being at risk of default became very real. One practical example of the relevance of funding considerations is that a trade may appear to have a positive profit and loss, but it may also have high potential future exposure. If a credit support annex (CSA) is in place, then an adverse market could lead to significant additional funding needs in the form of a requirement to immediately post additional collateral.11 Even if there is no CSA in place, expected future losses related to the trade may cause a loss of confidence in the bank and a withdrawal of credit lines to the firm. In practice, the primary role of FVA is to provide monetary incentives for trading desks to use less funding. FVA is currently not supported by accounting rules.  

# 24.8 CVA DESK  

The incorporation of counterparty risk adjustments into market practice has also affected the internal organization of banks as banks created CVA desks.12 The rationale for their creation was to move counterparty risk management away from traditional asset classes trading desks by creating a specific counterparty risk trading desk. In principle, the creation of CVA desks could be interpreted as allowing traditional traders to work in a counterparty risk-free world in the same way as they did before the GFC. Some top-tier banks used to have CVA desks for many years before the GFC, but their importance has now grown and CVA desks can now be found in most large banks. One of the incentives to create CVA desks is that it reduces the workload and skill needs of traders. They are freed from the need to be familiar with advanced credit models that are linked to traditional derivatives trading models for different asset classes, as illustrated by the CVA study above. Moreover, the traders do not need to concern themselves with netting details. Finally the CVA desk aggregates counterparty risks across trades, thus enabling the bank to take a view of counterparty risk-related options on the whole portfolio of derivatives transactions.  

The main job of a bank’s CVA desks is to manage all counterparty risk for the bank. This implies several functions. First, CVA desks provide CVA/DVA and FVA pricing for trades with counterparties. Second, CVA desks can be involved in trade origination as they advise on structuring trades to minimize credit risk. Typically there is an upfront charge for the trade which contains CVA/DVA and it is allocated to the CVA desk. Thus the CVA desk provides protection to the origination/trading desk. Third, the CVA desk helps to monitor and dynamically hedge market, credit and cross partial risks as well as default risk. Fourth, in case a counterparty defaults, it is typically also the responsibility of the CVA desk to (i) pay the originating desk the exposure coverage, (ii) manage the workout with CDS protection providers, (iii) support trade termination activities, and (iv) maximize the recovery of the remaining trade value.  

Although a CVA desk can in principle address some of these issues related to counterparty risk, one of the implications of incorporating counterparty risk is that there is no such thing as a fair value for derivative transaction since the deal value depends on the counterparty. It also implies that there is no such thing as mark-to-market at the deal level since the mark-to-market depends on the rest of the portfolio. Counterparty risk adjustments to some extent invalidate essential assumptions behind risk-neutral valuation, that is market completeness and hedge availability to create a riskless portfolio. Moreover, model risk associated with CVA models is a new issue.  

In practice, there are also some institutional and psychological aspects that affect the efficient functioning of CVA desks. Some traders may question the CVA fees that they have to pay to the CVA desk and be reluctant to cede authority to another unit such as the CVA desk. CVA desks may also give a false sense of security if traders incorrectly assume that counterparty risk can be perfectly hedged away by CVA desks. As we have seen in the previous section, CVA hedges are rather imperfect in practice.  

# 24.9 CHOICE OF THE DISCOUNT RATE AND MULTIPLE CURVES  

Throughout the book, we took the standard approach of pricing derivatives under the risk-neutral measure and using a risk-free discount rate. This was based on the fundamental financial engineering principle that a derivative can be valued by means of a replicating portfolio that leads to a riskfree portfolio. However, as will see below, one of the most common proxies for the risk-free rate before the GFC embeds a significant amount of counterparty risk which makes it an unsatisfactory proxy for the risk-free rate. We introduced LIBOR and the OIS rate in Chapter 3. Figure 24.8 shows the LIBOR OIS spread over the December 2003 July 2014 period based on Bloomberg data. The solid line and the dashed line show the 1-month and 3-month LIBOR OIS spreads, respectively. As the figure shows there were several episodes where the LIBOR and OIS rates diverged by several percentage points including the years during the GFC. The divergence between the two rates reflects counterparty risk and changes in the perception of creditworthiness of banks and their willingness to lend to each other.  

Before the GFC, LIBOR was the most commonly used proxy for the riskless rate but after the GFC, market practice has moved to the usage of OIS rates as a discount rate in collateralized transactions. This is partly due to the fact that LIBOR rates were significantly higher than OIS rates as a result of the counterparty risk that was priced into LIBOR rates.  

The following example illustrates that the move to OIS discounting affects hundreds of billions of dollars of derivatives transactions:  

# EXAMPLE  

With an increasing proportion of interest rate swap trades now being valued using the overnight swap index (OIS) rather than Libor, LCH.Clearnet plans to begin using the measure to discount its US\$218trn interest rate swap portfolio to ensure a more accurate valuation for risk management purposes. The move signals an ongoing trend that began during the financial crisis, and the shift could help to boost liquidity across the OIS curve. Even prior to the crisis, many market participants argued that OIS was the most appropriate measure given that it represents an accurate measure of expectations of the federal funds rate over the term of the swap. With the Libor OIS spread historically stuck around 10 bp, there was little impetus for change. But after peaking at more than 300 bp in late 2008, market participants were forced into reconsidering their valuation methods. Traders believe that the ongoing shift towards OIS discounting has already improved liquidity in longer maturities and more exotic currencies, and the shift by LCH.Clearnet should further boost liquidity.  

(Thomson Reuters IFR 1838, June 19 to June 25, 2010, “LCH adopts OIS discounting”)  

![](4c70209a7eb6b56cd233033cc302769c0a69b6b84aa0970622f7d4a19a0b3091.jpg)  

# FIGURE 24.8  

LIBOR OIS spread.  

The move to OIS rates has three fundamental implications for derivatives pricing. First, it is not possible anymore to use the same LIBOR/swap zero curves to price certain derivatives such as IRSs that we discussed in Chapter 4. Payoffs continue to depend on LIBOR rates, but discount rates will be based on OIS rates. Second, multiple curves need to be modeled to price fixed-income derivatives such as IRSs as well as caps and swaptions discussed in Chapter 17. The reason is not just due to the fact that OIS and LIBOR rates differ, but also because practitioners now use multiple LIBOR curves which reflect different levels of counterparty risk. Third, if one assumes that banks can risklessly borrow and lend at LIBOR and OIS rates then an implicit arbitrage arises.  

The move to the OIS rate as the riskless rate also has implications for fixed-income financial engineering discussed in Chapter 14. We saw that one of the widely used models was the so-called Forward LIBOR or BGM (Brace Gatarek Musiela) Model. In principle, this model can be modified easily by replacing the LIBOR rate with the OIS rate, which would lead to a Forward OIS model. For some fixed-income derivatives, it is necessary to model the LIBOR and OIS curves simultaneously. In practice, many banks continue to use several models such as the 3-factor HJM and the Forward LIBOR model. One of the first-order effects in fixed-income modeling is stochastic volatility. It is important to incorporate stochastic volatility but the Forward LIBOR model is not very suitable for this purpose when large trading books are concerned since most Monte Carlo methods that would allow this tend to be too time consuming.  

OIS discounting also brings with it some practical computational challenges as the following reading illustrates.  

# EXAMPLE  

Some buy-side firms have also taken steps to mitigate the problem of collateral-adjusted valuation by limiting the assets that can be posted under their CSAs, and therefore removing the collateral switch option. “The appropriate discount curve for valuing trades is more clearly defined under a clean CSA, leaving less room for ambiguity and additional margins both at inception and in the future,” says LGIM’s Walsh. “If clients move to clean CSAs, then it is no longer sensible to discount with Libor—so you need to be able to discount using the OIS rate. . .  

$I...J$ says buy-side firms may be able to approximate OIS discounting using simpler methods, but matching the accuracy of dealers is considerably more challenging—as is performing the calculations in a manageable time frame. “Speed of calculation becomes important when you want to do accurate risk management,” says Douglas. OIS discounting can be orders of magnitude more computationally demanding than Libor discounting because of the number of curve calculations and calibrations it entails, he says. And if a firm also wants to calculate the CVA, debit valuation adjustment and funding valuation adjustment on a deal, then this is far beyond the reach of conventional position-keeping systems.  

(Risk Magazine, February 22, 2013, “OIS discounting dilemma for the buy-side”, by Clive Davidson, www.risk.net/2244927)  

Finally there is an ongoing debate among practioners and among academics about the correct discount rate to use and this discussion is also related to a debate about the rationale for FVA.  

# 24.10 CONCLUSIONS  

In this chapter, we have reviewed recent innovations in financial engineering and derivatives pricing related to counterparty risk. The discussion has shown that many of the tools from the toolkit developed in previous chapters can be applied in corporate counterparty risk. CVA can be viewed as an option on the residual value of a portfolio upon default. Default probabilities for the calculation of CVA can be backed out from CDS market quotes. Finally, the option to choose the type of eligible collateral also. At the same time, we have seen that this is a very new and complex area and it is likely that practitioners, accountants, regulators, and academics will debate the best way of incorporating counterparty risk into accounting statements, pricing approaches, and bank capital charges for years to come.  

# SUGGESTED READING  

This chapter could only provide a brief summary of the treatment of counterparty risk in financial engineering and derivatives pricing. Brigo et al. (2013) provide one of the best reviews of counterparty risk including detailed examples for each major asset class and a discussion of CVA-CDOs. The discussion in this chapter is partly based on this text. The best source for recent developments in counterparty risk market practice and thinking is in the form of articles in Risk magazine, which we strongly recommend. For details about the recent debate about the choice of the riskless rate proxy as well as the merits of FVA, for example, we refer the reader to Risk magazine as well as Hull and White (2014). For recent developments related to model risk in counterparty risk adjustments see Kenyon and Stamm (2012) and Anfuso, Karyampas and Nawroth (2014).  

# EXERCISES  

1. What do the terms CVA, DVA, and FVA refer to?   
2. What is the difference between unilateral and bilateral CVA?   
3. Consider the reading below and explain how it is possible that a widening of credit spreads can lead to accounting gains? What is the difference between the treatment of DVA from an accounting and a bank’s regulatory capital perspective? On May 10, Jamie Dimon, chairman and chief executive of JP Morgan, announced that the bank would book a multi-billion dollar loss from “poorly executed” and “poorly monitored” derivatives trades made at its London-based Chief Investment Office. JP Morgan’s credit spreads have steadily worsened since news of the trading loss broke. The cost of insuring against a JP Morgan default on five-year debt, using a CDS contract, increased from 110 basis points on May 9 to 165 bps on June 5, according to data from Markit. This means that the cost of protection on an annual basis over five years has jumped from \$110,000 per \$10m of debt at the start of the year, to $\$165,000$ . Pugachevsky worked out his approximate \$1bn gain prediction from JP Morgan’s previous quarterly results. At the end of the first quarter, JP Morgan reported a \$900m DVA loss on the back of tightening spreads on its debt. Credit spreads had fallen from 144 bps on December 30 to 93 bps on March 30. Kinner Lakhani, a banks analyst at Citigroup, said, however, that while widening spreads generally convert to DVA gains, these gains are accounting “noise” that does nothing to “help boost a bank’s regulatory capital”.  

Efinancialnews, June 6, 2012, “JP Morgan DVA gains could hit \$1bn in second quarter”  

4. How can counterparty risk be hedged?  

# MATLAB EXERCISE  

5. (CVA for interest rate portfolio) Consider the CVA case study for a portfolio of interest swaps in the text. The case study is based on a Matlab example. Update the example by collecting data on (i) a portfolio of IRSs between a bank B and five counterparties (making sure that the floating and fixed leg rates are chosen so that current swap values are close to zero), (ii) a recent yield curve data, and (iii) CDS data for the counterparties. Back out the implied probabilities of default from the CDS spreads by applying a reduced-form hazard function model. Now redo Steps 1 4 in the case study and plot a. the evolution of the yield curve for a given scenario b. the mark-to-market value of the swap portfolio for one simulation c. the mark-to-market value of the portfolio for all simulations d. the exposure of the portfolio for all simulations e. the expected exposure f. the discounted expected exposure for each counterparty. Finally calculate the CVA for each counterparty from bank B’s perspective.  