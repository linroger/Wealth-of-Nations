---
tags:
  - credit_derivatives
  - credit_risk_modeling
  - default_risk
  - reduced_form_models
  - structural_models
aliases:
  - Credit Models
  - Credit Risk Introduction
key_concepts:
  - CAPM and portfolio theory
  - Credit default swap contracts
  - Default probability modeling
  - Default rates and credit ratings
  - Models of credit risks
  - Option pricing for bonds
  - Structural and reduced form models
  - Valuing default risk claims
---

# An Introduction to Credit Risk Modelling

Models of credit risks have long existed in the insurance and corporate finance literature. Those models concentrate on default rates, credit ratings and credit risk premiums. These traditional models focus on diversification and assume that since the credit risk for the individual assets in the portfolio are unique; these can be diversified away in a large portfolio. Models of this kind are along the line of portfolio theory that employs the capital asset pricing model (CAPM). In the CAPM, only the systematic risk or market risk matters. For single, isolated credits, the models calculate risk premiums as mark-ups onto the risk-free rate. Since the default risk is not diversified away, a similar model to the CAPM called the  capital market line  is used to compute the correct markup for bearing the default risk. The Sharpe ratio is commonly used to measure how credit risks are priced

Modern credit derivative models can be partitioned into two groups known as  structural models  and  reduced form models . Structural models were pioneered by Black and Scholes and Merton. The basic idea, common to all structural-type models, is that a company defaults on its debt if the value of the assets of the company falls below a certain default point. For this reason, these models are also known as firm-value models. In these models it has been demonstrated that default can be modelled as an option and, as a result, researchers were able to apply the same principles used for option pricing to the valuation of risky corporate securities. The application of option pricing avoids the use of risk premium and tries to use other marketable securities to price the option. The use of option pricing theory set forth by Black-Scholes-Merton (BSM) provides significant improvement over traditional methods for valuing default risky bonds. It also offers much more accurate prices, but provides information about how to hedge out the default risk, which was not obtainable from traditional methods. Subsequent to the work of BSM, there have been many extensions.

The second group of credit models, known as  reduced form  models, are more recent. These models, most notably the Jarrow-Tunbull and Duffie and Singleton models, do not look inside the firm. Instead, they model directly the likelihood of default or downgrade. Not only is the current probability of default modelled, some researchers attempt to model a ‘forward curve’ of default probabilities. This can be used to price instruments of varying maturities. Modelling a probability has the effect of making default a surprise – the default event is a random event that can suddenly occur at any time. All we know is its probability.

There is no standard model for credit. Part of the reason why this is so is that each of the models has its own set of advantages and disadvantages, making the choice of which to use depend heavily on what the model is to be used for. It is ultimately down to what suits the user’s requirements best. Pricing credit derivatives and credit risk in general, is quite similar in technique to pricing traditional derivatives, such as interest rate swaps or stock options. This paper introduces the concept behind two general frameworks for valuing default risk claims and extending these models to valuation of credit derivatives, in particular default swap or credit default swap contracts (CDS). The models or approaches investigated are the structural and reduced form models. We will examine the suitability of these models to the pricing of credit protection in rapidly growing credit default swap market by identifying some of the key advantages and drawback.  The following are some of the key questions that market practitioners must address. How is credit default swap priced? Which model is most appropriate model to use for pricing implementations? In a subsequent paper the authors use reduced or intensity based model to implement pricing default swaps using corporate bond yields and solve for the default swap premium they imply. In practice, we see that when comparing the implied credit default swap premium to actual market CDS prices, implied premiums tend to be much higher than the CDS prices quoted in the market. What accounts for these differences? The differences are related to measures of Treasury special ness, corporate bond il liquidity, and coupon rates of the underlying bonds, suggesting the presence of important tax-related and liquidity components in corporate spreads. Also, both credit derivatives and equity markets tend to lead the corporate bond market.  In this paper, we introduce the concept behind credit risk models.

# Structural models

Structural credit pricing models are based on modelling the stochastic evolution of the balance sheet of the issuer, with default when the issuer is unable or unwilling to meet its obligations. In this model, the asset value of the firm is assumed to follow a diffusion process and default is modelled as the first time the firm’s value hits a pre-specified boundary. Because of the continuity of the process used, the time of default is a predictable stopping time. The models of Merton (1974), Black and Cox (1976), Geske (1977), Longstaff and Schwartz (1993) and Das (1995) are representatives of this approach.
# Reduced-form models/intensity models

In the intensity models the time of default is modelled directly as the time of the first jump of a Poisson process with random intensity. The first models of this type were developed by Jarrow and Thurnbull (1995), Madal and Unal (1998), and Duffie and Singleton (1997). Jarrow and Turnbull assume default is driven by a Poisson process with constant intensity and known payoff at default. The Duffie and Singleton (1997) model assumes the payoff when default occurs as cash, but denoted as a fraction (1-q) of the value of default able security just before default. This model was applied to a variety of problems, including swap credit risk, two-sided credit risk and pricing credit default swap, binary credit default swap and credit default swap option.

# Structural credit models

The basic of structural approach, which goes back to Black and Scholes (1973) and Merton (1974), is that corporate liabilities are contingent claims on the asset of a firm. The market value of the firm is the fundamental source of uncertainty deriving credit risk.

# Basic assumptions

Consider a fix finite forward or horizon date   $T^{*}>0$  , and we suppose that the underlying probability space   $(\Omega,\,{\cal{F}},\,P)$  , endowed with some (reference) filtration  $\mathrm{F}{=}\left(\mathrm{f}_{\mathrm{t}}\right)_{0{\leq}t{\geq}T^{\star}}$  , is sufficiently rich to support the following objects.

● The short-term interest rate process  $r_{:}$  , and thus also a default-free term structure model.   $\bullet$  The firms value process  V , which is interpreted as a model for the total value of the firm’s assets.   $\bullet$  There is a barrier process  $p$  , which can be used in the specification of the default time  $\uptau$  .  $\bullet$  The promised contingent claim  $X$   represents the firm’s liabilities to be redeemed at maturity date  $T{\le}T^{\star}$  .  $\bullet$  The process   $C_{t},$  the liabilities stream that is redeemed continuously or discretely over time to the holder of a default able claim.   $\bullet$  The recovery claim   $\bar{X}$    represents the recovery pay-off received at the time   $T.$  , if default occurs prior to or at the maturity date of the claim  $X$  .  $\bullet$  The recovery process  $Z,$   specifies the recovery pay-off at the time of default, if it occurs prior to or at the maturity date   $T.$

# Default able claims

Technical assumptions The processes   $V,Z,$  ,   $C$   and  $\mathcal{P}$   are progressively measurable with respect to the filtration  $F_{;}$  , and that the random variables  $X$   and  $\bar{X}$  are  $F_{T}-$    measurable . In addition,  $C$   is assumed to be a process of finite variation, with  $C=0$  . It is assumed that all random objects introduced above satisfy suitable integrability conditions.

Probabilities

The probability   $P$   is assumed to represent the real-world (or statistical) probability, as opposed to the martingale measure (also known as the risk-neutral probability). The latter probability is denoted by  $P^{\star}$  .

Default time/stopping times

In order to be able to model the arrival risk of a credit event, one needs to model a known, random point in time   $t{\in}R_{+}$  . This can also be extended to the possible set of realisation s of τ  to include  ∞ for events that may never occur. Thus,  $\mathbf{\Psi}^{\mathrm{T}}$   is a random variable with values in  $R_{+}{\cup}\{\infty\}$   But one may need to link  $\uptau$   to the way information is revealed in the filtration  $(F_{t})_{t\geq0}$  . In particular, if  $\uptau$   is the time of some event, we want that at the time of default event it is known that this event has occurred. Formally, this shows that at every time  $\tau$   we know if  $\uptau$   has already occurred or not:

$$
\{\tau\leq t\}\in F_{t}\ \ \ \ \forall t\geq0
$$

This property defines the random time  $\uptau$   as a stopping time. Equation 2.1 says that we can observe the event at the time it occurs. But it does not require that the event comes as a surprise. The value of the stopping time may be known a long time before time  $t=\tau$  . The maximum and minimum of a set of stopping times is again a stopping time, and the sum of the two stopping times. In order to represent stopping time with a stochastic process, we define its indicator process that jumps from zero to one at the stopping time:

$$
N_{\uptau}(t)\!:=\!I I_{\{\uptau\leq t\}}
$$

In particular, depending on the model and the purpose we may have that  $\scriptstyle{\uptau=\{T\}}$   – meaning that the default event may only take place at the maturity of the company’s outstanding debt as in the classical Merton model, or that  $\scriptstyle{\mathfrak{T}}=\{T_{1},\,T_{2},\dotsc T_{\mathrm{N}}\}$   if default can only happen (or rather, can be declared) at some discrete time instants, such as the coupon payment dates.

For default risk modelling, default indicator functions can be used (the indicator function of the default event) and the survival indicator functions (one minus the default indicator function). Another concept in conjunction with the default indicator is also the idea of predictable stopping time  $\uptau$  . The indicator process of a predictable stopping time is a predictable process. A predictable stopping time has an announcing sequence of stopping times.  $\uptau_{1}{\leq}\uptau_{2}{\leq}\ldots$  . with

$$
\uptau_{n}<\uptau\;\mathrm{and}\;\underset{n\rightarrow\infty}{\operatorname*{lim}}\uptau_{n}=\uptau\;\mathrm{for}\;\mathrm{all}\;\upomega\in\Omega\;\{\uptau(\upomega)>0\}
$$

This means that there is a sequence of early warning signals  $\uptau_{n}$   that occurs before  $\uptau$   and that announce the predictable stopping time. An example of predictable stopping time is the first hitting time of a continuous stochastic process   $X(t)$  , ie the first time when  $X(t)$   hits a barrier,  $\bar{K}$    . If the process starts above the barrier  $X(t){>}\bar{K}$  , then one possible announcing is given by the following times:
$$
\mathfrak{T}_{n}=\operatorname*{inf}\{t\mid X(t)\le\bar{K}\!+\!1/n\}
$$

The announcing sequence gives the times when  $X(t)$   hits barriers that are closer to the final barrier  $\bar{K}$    .

Recovery rules

If default does not occur before or at time   $T_{i}$  , the promised claim   $X$   is paid in full at time   $T$  . Otherwise, depending on the market convention, either; (1) the amount  $\bar{X}$  is paid at maturity date   $T$  ; or (2) the amount  $Z_{\tau}$   is paid at time  $\uptau$  . In this paper we assume that the recovery payment of   $\bar{X}$    is paid in the event of default at maturity, i.e. on the event  $\uptau\!\!=\!T.$  .

Risk neutral valuation formula

We consider a financial market model that is arbitrage free, in the sense that there exists a martingale measure (risk neutral probability)   $P^{\star}$  , meaning that the price process of any tradable security, which pays no coupon or dividends, becomes an   $F$  -martingale under measure  $P^{\star}$  , when discounted by the saving account   $B$   given as:

$$
B_{t}=\exp\bigotimes_{0}^{t}r_{u}d u_{\big>}
$$

We introduce the jump process  $H_{t}{=}1_{\tau>T}$   $D$    as the process that models all cash flows received by the owner of a default able claim . Let us denote

$$
X^{d}(T)=X I I_{\tau>T}+\bar{X}\,I I_{\tau\leq T}
$$

The above equation shows the payoff of a default able claim if default does not happen at the maturity of the contract and the event that default takes place before or at the maturity of the contract.

The dividend process  $D$   of a default able contingent claim  $(X,C,{\bar{X}},Z,\uptau)$  , which settles at time  $T.$  , equals

$$
D_{t}=X^{d}(T)I I_{t\geq T}+\int_{0.t}(1-H_{u})d C_{u}+\int_{0,t}Z_{u}d H_{u}
$$

$D$   is a process of finite variation, and

$$
\int_{0.t}(1-H_{u})d C_{u}=\int H_{\tau>u}d C_{u}=C_{\tau-}I I_{\tau\leq t}+C_{t}I I_{\tau>t}.
$$

In principal, the promised payoff   $X$   could be incorporated into the promised dividends process  $C$  . However, this would be inconvenient, since in practice the recovery rules concerning the promised dividends  $C$   and the promised claim  $X$   are different, in general. For instance, in the case of a default able coupon bond, it is frequently postulated that, in case of default, the future coupons are lost, but a strictly positive fraction of the face value is usually received by the bondholder.

Let us denote  $S_{t}$   as the ex-dividend price of a default able claim. At any time  $t,$  , the random variable  $S_{t}$   represents the current value of all future cash flows associated with a given default able claim. For any date  $\scriptstyle t\in[0,\,t]$   the ex-dividend price of the default able claim   $(X,C,{\bar{X}},Z,\uptau)$   is given as:

$$
S_{t}=B_{t}E_{P^{*}}(\int_{t,T}B_{u}^{-1}d D_{u}\mid F_{t})
$$

It is common to use the above equation, but with the probability measure  $P^{\star}$   substituted with  $\mathcal{Q}^{\star}$  .

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4f549af2ab5d69124b7b3d1f6574a6abcac6e6c3c6090e53ae24fafcb43b0868.jpg)

Default able zero-coupon bond

Assume that   $\scriptstyle C=0$  ,  $Z{=}0$   and  $X{=}L$   for some positive constant  $L{>}0$  . Then the value process  $S$   represents the arbitrage price of default able zero-coupon bond with face value of  $L$   and recovery at maturity only. In general, the price  $D(t,T)$   of such a bond equals:

$$
D(t,T)=B_{t}E_{P^{*}}(B_{T}^{-1}(L I I_{\tau>T}+\bar{X}\,I I_{\tau\leq T})\,|\,F_{t})
$$

The above formula can also be rewritten as follows:

$$
D(t,T)=L B_{t}E_{P^{*}}(B_{T}^{-1}(I I_{\tau>T}+\delta(T)I I_{\tau\leq T})\,|\,F_{t})
$$

where the random variable  $\scriptstyle\delta(\,T)={\bar{X}}/L$    represents the  recovery rate upon default. It is also natural to assume between  $0\%$   and  $100\%$   of the bond’s face value. This can be written as:

$$
0\leq\bar{X}\geq L\;\mathrm{so~that}\;\delta(T)\;\mathrm{satisfies}\;0\leq\delta(T)\geq1
$$

Alternatively, one can re-express the bond price as follows:

$$
D(t,T)=L(B(t,T)-B_{t}E_{P^{*}}(B_{T}^{-1}w(T)I I_{\tau\leq T})\,|\,F_{t}))
$$

where

$$
B(t,T)=B_{t}E_{P^{*}}(B_{T}^{-1}\,|\,F_{t})
$$

is the price of a unit default free zero coupon bond and  $w(\mathit{T}){=}1{-}\delta(\mathit{T})$   is the write-down rate upon default. Generally, the time $\cdot\,t$   value of a corporate bond depends on the joint probability distribution of under measure  $P^{\star}$   of the threedimensional random variable  $(B_{T},\updelta(T),\uptau)$  .

# Classical approach

If we consider a firm with a market value  $V_{\parallel}$  , and let  V  represent the present value of future the firm’s cash flows. Let  $K$  represent the value of face value of the firm’s debt and  T  the maturity date of these debts. As stated above, let’s define the default time  $\uptau$   as a discrete random variable given by:

$$
{\uptau}=T\ \mathrm{if}\ \ V_{T}<K
$$

$$
{\uptau}=\infty\;\mathrm{if}\;\mathrm{else}
$$

To calculate the probability of default, we make assumptions about the distribution of assets at debt maturity under the probability measure  $P^{\star}$  . The change of the asset prices over time follows geometric Brownian motion:

$$
\begin{array}{c c}{d V_{t}=u V_{t}d r+\upsigma V_{t}d W_{t}}\\ {}\\ {\displaystyle\frac{d V_{t}}{V_{t}}=u d t+\upsigma d W_{t},}&{V_{0}=0,}\end{array}
$$

where  $u$   is the drift,  $\upsigma$   is the volatility parameter and   $W$   is a standard Brownian motion. Via Ito’s lemma, the solution of the above equation can be written as 1 :
$$
V_{t}=V_{0}\exp(m t+\odot W_{t})
$$

Since   $W_{t}$   is   $N{\sim}(0,\,T)$  , the default probabilities  $P(T)$   are given by

$$
\begin{array}{l}{p(T)=P(V_{T}<K)}\\ {=P(\upsigma W_{T}<\log L-m T)}\\ {=\Phi\Bigg(\displaystyle\frac{\log L-m T}{\upsigma\sqrt{T}}\Bigg)}\end{array}
$$

where   $L{=}K/V_{0}$   is the initial leverage ratio and  $\Phi$   is the standard normal distribution function. If we assume that the firm cannot repurchase its shares or issue new debt, the payoffs to the firms liabilities at debt maturity  Τ  can be summarized in Table 1.

If the asset value   $V_{T}$   is equal or greater than the face value of the firm’s debt   $K,$   the bondholder will receive the face value back, while the equity holders will get the difference between the value of the firm and debt value. In the event the firm value is below the firm’s debt value, the equity will be worthless and the debt holders will assume ownership of the firm.

# Summary and conclusions

Credit risk is the distribution of financial losses due to unexpected changes in the credit quality of counter party in a financial agreement. Examples range from agency downgrades to failure to service debts to liquidation. Credit risks exist in virtually all financial transactions. The distribution of credit losses is complex. At its centre is the probability of default or the likelihood of failure to honour a financial agreement. To estimate these probabilities of default, one needs to specify a model of investor uncertainty, a model of the available information and its evolution over time, and a model definition of the default event.

However, default probabilities alone are not sufficient to price credit sensitive securities. One needs, in addition, a model for the risk free interest rate, a model of recovery upon default and a model of the premium investors require as a compensation for bearing systematic credit risk.

The credit premium maps actual default probabilities to the market-implied probabilities that are embedded in market prices. To price securities that are sensitive to the credit risk of multiple issuers and to measure aggregated portfolio credit risk, we also need to specify a model that links defaults of several entities 2 .

There are three main quantitative approaches to analysing credit. In the  structural  approach, we take explicit assumptions about the dynamics of a firm’s assets, its capital structure, and its debt and shareholders. A firm defaults if its assets are insufficient according to some measure. In this situation, a corporate liability can be characterized as an option on the firm’s assets. The  reduced form  approach is silent about why a firm defaults. Instead, the dynamics of default are exogenous ly given through a default rate, or intensity. In this approach, prices of credit sensitive securities can be calculated as if they were default free using an interest rate that is the risk-free rate adjusted by the intensity. The  incomplete information  approach combines the structural and reduced form models. While avoiding the difficulties, it picks the best features of both approaches: the economic and intuitive appeal of the structural approach and the tract ability and empirical fit of the reduced form approach.

Abukar Ali is a research partner with YieldCurve.com.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/dcd80beba484b7e7ee5be05eb556b1146c15a9af6db2bc2f6f7daf6b29456100.jpg)

# References

1) Black, F. and M. Scholes, “The Pricing of Options and Corporate Liabilities” Journal of Political Economy 81, 1973, 637-654. 2) Black, Fischer and John C. Cox, “Valuing Corporate Securities: Some Effects of Bond Indenture Provisions”, Journal of Finance, Vol. XXXI, No. 2, (May 1976), pp. 351-367. 3) Das (1995) 4) Duffie, D., K. Singleton, “An econometric model of the term structure of interest rate swap yields”, (1997), Journal of Finance 52, pp.1287-13215) Geske, Robert, “The Valuation of Corporate Liabilities as Compound Options”, Journal of Financial and Quantitative Analysis, Vol. 12, No. 4, UCLA, (November 1977), pp. 541-552. 6) Hull, J., Introduction to Futures and Options Markets, Englewood Cliffs, New Jersey: Prentice-Hall, Second edition, 1995 7) Jarrow, Robert A. and Stuart M. Turnbull. “Pricing Derivatives on Financial Securities Subject to Credit Risk”, Journal of Finance, Vol. L, No. 1, Cornell University, and Queen’s University (Canada) (Mar1995), pp. 53-85 8) Longstaff and Schwartz (1993) 9) Madal, D., and Unal, H., “Pricing the Risk of Ddefault”, Working paper, The Wharton School 1998 10) Merton, Robert C. “On the Pricing of Corporate Debt: The Risk Structure of Interest Rates”, Journal of Finance, Vol. 29, MIT (1974), pp. 449-470 11) F.A Longstaff and E.S. Schwartz (1995) A simple approach to valuing risky fixed and floating. Rate debt. Journal of Finance 51, 987-1019
