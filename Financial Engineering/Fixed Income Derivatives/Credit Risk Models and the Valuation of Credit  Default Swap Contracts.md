---
tags:
  - credit_derivatives
  - credit_risk_models
  - default_swap
  - intensity_models
  - merton_model
  - reduced_form_models
  - structural_models
aliases:
  - CDS Valuation
  - Credit Risk
  - Default Swap Pricing
  - KKM Model
key_concepts:
  - Jarrow and Turnbull
  - Kettunen model
  - Merton model
  - credit default swaps
  - credit risk models
  - intensity based models
  - pricing credit derivatives
  - reduced-form models
  - structural models
---

# Credit Risk Models and the Valuation of Credit  Default Swap Contracts

# Abstract

This paper surveys some of the main credit risk models within structural models and  reduced-form models. In particular, it focuses on the Merton model and its extensions  under the structural models. It also concentrates on intensity based models such as  Jarrow and Turnbull (1995), Jarrow, Lando and Turnbull (1997), and Duffie and  Singleton (1998). Empirical results investigating the differences between market-quoted  credit default swaps premium and model implied CDS premiums are presented. Finally,  the Kettunen, K send zo v sky, and Meissner (KKM) model (2003) is reviewed and  implemented to compute credit default swap premium for a given set of data. From the  existing research on credit risk models, reduced form models seems to be the preferred  approach when pricing a firm’s risky debt or related credit derivatives.
# Contents

1     Introduction………………………….. ……… ……………………………………..1
1.1 Structural Models……………………………………………………………..4
1.2 Reduced-form/Intensity models…………………………………………........4
2.1. Structural Credit Risk Models…………………………… . . ... . . . . . . . . . . . . . . . .. 6
2.1.1 Merton’s Model……………………….. . . . . . . . . . . . . . . . . . . . . . . . . . . . .6
2.1.2 Advantages, Disadvantages and Model Extensions . . . . . . . . . . . . . . . . … 11
2.2. First Passage Model……………………………………… . . ... . . . . . . . . . . . .. . . . 12
2.2.1 Other Structural Models………… …….. . . . . . . . . . . . . . . . . . . . . . . . . . ..15
2.2.2 The Kim, Ramaswamy and Sundaresan 1993 Model. . . . . . . . . . . . . . ..….15
2.2.2 The Longstaff-Schwartz 1995 Model. . ….. . . . . ... .. …... .. .. ……. ..…...15
2.3. Empirical tests from structural models……………… . . ... . . . . . . .…... . . . . .. . . . 16
3.1. Reduced-Form Credit Risk Models……………… . . ... . . . . . . .…... ……………..16
3.1.1 Intensity Based Model………… … ………. . . . . . . . . . . . . . . . . . . . . . . . 16
3.1.2 Jarrow and Turnbull (1995) – discrete approach…... . . . . . . . .. . . . . . ..… 18
3.2.  Arbitrary deterministic recovery, deterministic interest rates. .. .. ……….. 22
3.2.1 Stochastic recovery, interest rate and hazard rate……..……………...….. 24
3.2.2 Recovery Protocols……………………………..……..……………...….. 25
4.1. Jarrow, Lando and Turnbull (1997) model – discrete approach.. . . . .. . . ……….. .26
5.1. Pricing Default Swap…………………………………………… . . . .. . . ……….. 30
5.3. Relating risky par rates & default probabilities . . . . . . . . . . . . ……. . . . . . 33
5.4  CDS model using stochastic interest rate and intensity process . ..……….. 34
6.1. Kettunen, Ksendzovsky, and Meissner (KKM) model (2003) . ……….. ………….40
7.1  Structural versus Reduced-form models…………………………………………….42
8.1. Conclusion . ……….. ……………………………………………………………....43
Appendix A & B ……….. ……………………………………………………………....44
Appendix C……….. ………………………………………………………………….....45
References  ……………………………………………………………………………...46
# Credit Risk Models and Valuation of Credit Default  Swap Contract

1.  Introduction.

Pricing credit derivatives and credit risk in general, is quite similar in technique to pricing  traditional derivatives, such as interest rate swaps or stock options.  This paper focuses on  the investigation on two general methods for valuing default risk claims and by extending  these models to valuation of credit derivatives in particular default swap or credit default  swap contracts (CDS). The models or approaches investigated are the structural and  reduced form models. We will examine the suitability of these models to the pricing of  credit protection in rapidly growing credit default swap market by identifying some of the  key advantages and drawback.

The following are some of the key questions that this paper is concerned to investigate.  How is credit default swap priced?. Which model is most appropriate model to use for  pricing implementations?. We will use reduced or intensity based model to implement  pricing default swaps using corporate bond yields and solve for the default swap premium  they imply. We compare these implied credit default swap premium to actual market  CDS prices. Implied premium tend to be much higher than then the CDS prices quoted in  the market. What accounts for these differences?. The differences are related to measures  of Treasury special-ness, corporate bond il liquidity, and coupon rates of the underlying  bonds, suggesting the presence of important tax related and liquidity components in  corporate spreads. Also, both credit derivatives and equity markets tend to lead the  corporate bond market.

There are number of issues that may arise from the implementation when pricing the  credit default swap, for example, what are the assumptions underlying the pricing  model?. What are the implications for relaxing some of these assumptions? For example,  we will assume no counter party default and that interest rate, default probabilities and  recovery rates are independent. The one parameter necessary for valuing default swap  that cannot be observed directly in the market is the expected recovery rate. Hull & White  (2000) assume that the same recovery rate is used for estimating default probability  densities and for calculating the payoff. As it happens there is an offset. As the expected  recovery rate increases, estimates of the probability of default increase and payoff  decrease 1 . The overall impact of the recovery rate assumption on the value of a credit  default swap is generally fairly small when the expected recovery is in the   $0\%\textrm{-}50\%$  range.
# 1.1.  Structural Models.

Structural credit pricing models are based on modelling the stochastic evolution of the  balance sheet of the issuer, with default when the issuer is unable to or unwillingly to  meet its obligations. In this model the asset value of the firm is assumed to follow a  diffusion process and default is modelled as the first time the firm's value hit a prespecified boundary. Because of the continuity of the process used, the time of default is a  predictable stopping time. The models of Merton (1974), Black and Cox (1976), Geske  (1977) Longstaff and Schwartz 1993 and Das 1995 are representatives of this approach.

# 1.2   Reduced-Form Models/ Intensity Models

In the intensity models the time of default is modelled directly as the time of the first  jump of a Poisson process with random intensity. The first models of this type were  developed by Jarrow and Thurnbull (1995), Madal and Unal (1998) and Duffie and  Singleton (1997). Jarrow and Thurnbull assume default is driven by a Poisson process  with constant intensity and known payoff at default. Duffie and Singleton (1997) model  assumes the payoff when default occurs as cash, but denoted as a fraction   $(1{\cdot}q)$   of the  value of default able security just before default. This model was applied to a variety of  problems including swap credit risk, two sided credit risk and pricing credit default swap,  binary credit default swap and credit default swap option. Table 1.1 provides brief  overview on the existing credit risk model’s main advantages as well as their limitations.

Table 1.1  Strengths and Drawbacks of Various Models for Default Risky Bonds and Swaps
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5a7529c31313f2e0abc09d0ca6c1654598e74ad9cbaa1e6cb407e37c8d75a40d.jpg)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/da24443907f805e1d6a9d7cfb0221844d43c825b922dd3287e2fef179ce82e66.jpg)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/df15e1e09f17402aa989b30db1a921f45173c2a2e4e44a68cb0b7654413b2bf9.jpg)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/13917406cdc789e1fcdc2110b6a2ffbe6f2d07465861463af030cb37ac5dd8c6.jpg)

Figure 1.1 illustrates the types of credit risk models available and the focus of this paper  is the implementation of the asset value models and the intensity based models.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/26a7d2e9e72f3f9a7e9a394da499b09e0074af61d6fad66a261efb7202a2b63d.jpg)

# 2.1  Structural Credit Risk Models.

# 2.1.1 Merton’s Model.

The basic foundations of structural models have been laid in the seminal paper Merton  (1974). Here it is assumed that a firm is financed by equity and single zero-coupon bond  with notional amount or face value of   $K$   and maturity   $T.$  . The firm’s contractual obligation  is to repay the face value   $(K)$    of the debt to the bond investors at the maturity of the debt   $(T)$  .   In the event of default, bond holders will assume ownership of the firm.  Hence the  default time   $\tau$  is a discrete random variable given by

$$
\begin{array}{r}{\tau\!=\!\!\left\{\begin{array}{l l}{{\cal T}}&{i f\quad V_{\scriptscriptstyle T}\,<{\cal K}}\\ {\infty}&{i f\quad e l s e.}\end{array}\right.}\end{array}
$$
Figure 2.1 shows the triggering of default as soon as the stochastic path of the firm value  crosses the default barrier which is the face value of the debt at any time between time  zero and   $T.$  . This however is an extension of Merton’s model which relaxes the  assumption of default taking place only at maturity of the debt. Under Merton’s model,  default cannot occur prior to the maturity of the debt. This means that default is only  triggered if the asset value exceeds the total outstanding debt of the firm at time  $T.$  .

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/13c501cb749db8475f73c2fefef5e7364c4e5f6935993fb32538925a6dd9b861.jpg)
Figure 2.1

The dynamics of the firm value under the probability measure   $I\mathrm{P}$    follows a geometric  Brownian motion:

$$
\begin{array}{l}{\displaystyle{\frac{d V_{t}}{V_{t}}=\mu d t\ +\ \sigma d W_{t},}\ V_{0}\ >\ 0,}}\\ {d V_{t}=\mu V_{t}d t\ +\ \sigma V_{t}d W_{t},V_{0}\ >\ 0,}}\end{array}
$$

Where  $\mu\varepsilon R$  is a drift parameter,   $\sigma\!>0$  , is a volatility parameter for the firm, and   $\boldsymbol{W}_{t}$   is a  standard Brownian motion. The solution for equation  $(l)$    is given by 2 :

$$
V_{t}=V_{0}\exp(\mu\!-\!\frac{1}{2}\sigma^{2})t+\sigma W_{t}
$$

We apply Ito’s formula and the above stochastic differential equation (SDE) for the firm  and formulate the Black & Scholes differential equation.

Ito’s Lemma: let   $F(V_{t}\ t)$    be twice-differentiable function of   $t$   and of the random process   $V_{t}$   given in   $(l)$    with well behaved drift and diffusion parameters,   $\mu$  , and   $\sigma^{\mathrm{~3~}}$  .  Then we  have
$$
d F_{t}=\frac{\partial F}{\partial V_{t}}d V_{t}+\frac{\partial F}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}F}{\partial V_{t}^{2}}d V_{t}^{2}
$$

Using Ito’s multiplication rules, the term   $d V_{t}^{2}$    can be reduced to 4 :

$$
d V_{t}^{2}=\sigma^{2}V_{t}^{2}d t
$$

By substituting 1 and 3 into equation 2 and incorporating the portfolio replication, one  can drive for the Black & Scholes partial differential equation whose solution will depend  on the specified boundary condition 5 :

$$
\frac{\partial F}{\partial V_{t}}R V_{t}+\frac{\partial F}{\partial t}+\frac{1}{2}\sigma^{2}V_{t}^{2}\,\frac{\partial^{2}F}{\partial V^{2}{}_{t}}-R F\quad=0
$$

$W_{T}$    is normally distributed with zero mean and variance   $T.$  , default probabilities  $p(T)$    are  given by

$$
p(t)=P[V_{t}<K]\!\!=\!\!P[\sigma W_{t}<\log L\!-\!m T]\!=\!N\!\left({\frac{\log L-m T}{\sigma{\sqrt{T}}}}\right)
$$

Where   $L{=}\frac{K}{V_{0}}$  is the initial leverage ratio and   $N(.)$   is the standard normal distribution  function such that     $N(x)=\!\int_{-\infty}^{x}\exp\!\left(-{\frac{1}{2}}\,z^{2}\right)\!\!d z$

If at time   $T$    the firm’s asset value exceeds the promised payment   $K.$  , the lenders are paid  the promised amount and the shareholder receive the residuals asset value. In the even the  asset value is less than the promised payment the firm defaults and the ownership of the  firm will be transferred to the bond holders. Equity is worthless because of limited  liability 6 . The value of the bond issue   $B_{T}^{T}$  at time  $T$  is given by

$$
B_{T}^{T}=\,\mathrm{min}(K,V_{T})=K-\mathrm{max}(0,K-V_{T})
$$

The above payoff is equivalent to of a portfolio composed of a default-free loan with face  value   $K$    maturing at time   $T$    and a short European put position on the assets of the firm  with strike   $K$    and maturity   $T.$  .  The value of the equity is equivalent to the payoff of a  European call option on the assets of the firm with strike  $K$    and maturity   $T_{\ast}$  .
Table  2.1 Payoffs at maturity
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ffb7779783dfb4fd1604d5cad745cba4ef95aa91af1da6a678c8af8a2dbb0eff.jpg)

$$
E_{\scriptscriptstyle T}\,=\,\operatorname*{max}(0,V_{\scriptscriptstyle T}\,-\,K),
$$

Pricing equity and credit risky debt reduces to pricing European options. Under the  classical Black-Scholes setting with constant risk free rate, volatility and solving equation  (4)  by imposing suitable initial and boundary conditions, the equity value is given by the  Black-Scholes vanilla call option formula:

$$
E_{0}=V_{0}N(d_{1})\!-\!\exp(\!-\!r T)K N(d_{2})
$$

Where

$$
d_{1}=\frac{\ln\!\left({\cfrac{K}{V_{0}}}\right)\!+\!\left(r\!+\!{\cfrac{1}{2}}\sigma^{2}\right)\!T}{\sigma{\sqrt{T}}}\qquad{\mathrm{and}}\quad d_{2}\,=d_{1}-\sigma{\sqrt{T}}
$$

The value of the corresponding the defaulable bond is given by

$$
B_{0}^{T}=K\exp(-r T)-P(\sigma,K,T,V,r)
$$

Where  $P$     is the Black-Scholes put option formula. The value of the put option is equal to  the present value of the default loss suffered by bond investors. This is the discount for  the default risk relative to the risk-free bond, which is valued at   $K\exp(-r T)$  . This yields

$$
B_{0}^{T}=V_{0}-V_{0}N(d_{1})+\exp(-r T)K N(d_{2})
$$

Using equation  (5)  and  (7) , the market value of the firm is given by:

$$
V_{0}~{=}~V_{0}N(d_{1})-\exp(-r T)K N(d_{2})~{+}~~V_{0}~{-}V_{0}N(d_{1})~{+}~\exp(-r T)K N(d_{2})
$$

Both of the equity value and debt value will depend on the firm’s leverage ratio, equation  (8) shows however that their sum does not depend on the firms leverage ratio. This result  asserts that the market value of the firm is independent of its leverage, see Rubinstein  (2003).  The risk neutral default probability can be expressed:

$$
p\!\left(t\right)\!=\!\frac{\ln\!\left(\cfrac{K}{V}_{0}\right)\!+\!\left(r\!+\!\cfrac{1}{2}\sigma^{2}\right)\!T}{\sigma\sqrt{T}}\!-\!\sigma\sqrt{T}
$$
This depends only on the leverage,   $L,$    the asset volatility   $\sigma$  ,  and maturity time of the  debt,  T.

The credit spread is the difference between the yield on the default able bond and the yield  of an equivalent default-free zero coupon bond. This is the access return demanded by  bond investors to bear the potential default losses.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b55762dfa9c791777c63625c9121401462de61a9a4698dd0c1129ea9270424e3.jpg)
Source: Bloomberg  $L P$

Since the yield   $Y(t,\boldsymbol{T})$  on a bond with price   $b(t,T)$  satisfies;

$$
b(t,T)\,=\,\exp(-y(t,T)(T-t)
$$

The credit spread   $S(t,\boldsymbol{T})$   at time   $t$    for a maturity of  $T$    is given as:

$$
S(t,T)\,=\,-\frac{1}{T-t}\mathrm{log}(\sqrt{\frac{B_{t}^{T}}{\beta_{t}^{T}}}\biggr),
$$

$$
T>t,
$$

Where   $\beta_{t}^{T}$   is the price of default-free bond maturing at time   $T.$  .  The term structure of  credit spreads is the schedule of   $S(t,T)$    against different maturities, holding   $t$     fixed. In  the Black-Scholes framework, we have   $\beta_{t}^{T}\,=\,K\exp(-r(T-t))$    and we obtain the credit  spread at time zero

$$
S(0,T)\,=\,-\frac{1}{T}\mathrm{log}\biggl(N\bigl(d_{2}\bigr)+\frac{1}{{\cal L}}e^{r T}N\bigl(-d_{1}\bigr)\biggr),\qquad\qquad T>0,
$$
which is a function of maturity   $T,$  ,  asset volatility   $\sigma$  (the firms business risk), the initial  leverage ratio   $L,$    and the risk free rate   $r.$  .   Figure 2.2 plots the credit spread between  default able and non default able bonds with various maturities and different volatility  levels. This information can be used as a proxy to derive the prices of credit derivatives  contracts such as credit default swaps.

According to Kim, Ramaswamy, and Sundersan (1993) and Jones, Mason, and Rosenfeld  (1984), Merton’s model does not generate the level of yield spreads which can be  observed in the market. They showed that Merton’s model is unable to generate yield  spreads in excess of 120 basis points, whereas over a period between 1926-1986, the  yield spread of AAA-rated corporate ranged from 15 to 215 basis points.

Using a set of structural models, Ericsson, J, Reneby, J and Wang, H., (2005)   investigated bond yield spreads and the price of default protection for a sample of US  corporations. Theory predicts that if credit risk alone explains these two quantities, their  magnitudes should be similar. Their findings are consistent with previous results that  bond yield spreads are underestimated. However, their result showed that credit default  swap prices (premium) were much lower than bond spreads. Furthermore, their results  highlighted the strong relationship between bond residuals and non-default proxies, in  particular il liquidity. CDS residuals exhibit no such relations. This suggests that the bond  spread under estimation by structural models may not stem from their inability to properly  account for default risk, but rather from the importance of the omitted risk factors .

Pricing section of this paper will provide further empirical analysis on credit default swap  premium data from the market and default risk pricing from structural models.

# 2.1.2 Advantages, disadvantages and model extensions

The main advantage of Merton’s model is that it allows to directly apply the theory of  pricing European options developed by Black and Scholes (1973). However, the model  requires to make the necessary assumptions to adapt the dynamics of the firm’s asset  value process, interest rates and capital structure to the requirements of the Black-Scholes  model.

Despite its simplicity and intuitive appeal, Merton's model has many limitations. First, in  the model the firm defaults only at the maturity of the debt, a scenario that may not be  very realistic in real life. Second, another problem of Merton’s model is the restriction of  default time to the maturity of the debt, ruling out the possibility of an early default, no  matter what happens with the firm’s value before the maturity of the debt. If the firm’s  value falls down to minimal levels before the maturity of the debt but it is able to recover  and meet the debt’s payment at maturity, the default would be avoided in Merton’s  approach. Third, Another problem with the Merton model is that the value of the firm, an  input to the valuation formula, is very difficult to determine. Unlike the stock price in the  Black-Scholes-Merton formula for valuing equity options, the current market value of a  firm is not easily observable.
Another limitation of the model is that the usual capital structure of a firm is much more  complicated than a simple zero-coupon bond. Geske (1977, 1979) considers the debt  structure of the firm as a coupon bond, in which each coupon payment is viewed as a  compound option and a possible cause of default. At each coupon payment, the  shareholders have the option either to make the payment to bond holders, obtaining the  right to control the firm until the next coupon, or to not make the payment, in which case  the firm defaults. Geske also extends the model to consider characteristics such as sinking  funds, safety covenants, debt subordination and payout restrictions.

The assumption of a constant and flat term structure of interest rates is other major  criticism the model has received. Jones et al. (1984) suggest that “there exists evidence  that introducing stochastic interest rates, as well as taxes, would improve the model’s  performance.” Stochastic interest rates allow to introduce correlation between the firm’s  asset value and the short rate, and have been considered, among others, by Ronn and  Verma (1986), Kim, Ramaswamy and Sundaresan (1993), Nielsen etal. (1993), Longstaff  and Schwartz (1995), Briys and de Varenne (1997) and Saá-Requejo and Santa Clara  (1997).

Another characteristic of Merton’s model, which will also be present in some of the First  Passage Models (FPM), is the predictability of default. Since the firm’s asset value is  modelled as a geometric Brownian motion and default can only happen at the maturity of  the debt, it can be predicted with increasing precision as the maturity of the debt comes  near. As a result, in this approach default does not come as a surprise, which makes the  models generate very low short-term credit spreads 7 .

# 2.2  First passage model.

First passage model were introduced by Black & Cox (1976) extending the Merton model  to the case when the firm may default at any time, not only at the maturity date of the  debt. They also assume that the firm’s shareholders receive a continuous dividend  payment, proportional to the current value of the firm. Consequently as in section 2.1, the  SDE which governs the dynamics of the firm’s value takes the following form, under the  risk neutral probability measure   $\mathrm{P}^{8}$  ,

$$
d V_{t}=\!V_{t}\left((r-k)d t+\sigma d W_{t}\right)
$$

Where   $k\geq0$    represents the payout ratio (continuous dividend payment),   $\sigma>0$  and  $r$  represent constant volatility and constant short term interest rate respectively.

Safety covenant in the firm’s debt prospectus give the bond holders the right to force the  firm to bankruptcy if the firm is doing poorly according to a set standard. The standard
for a poor performance is set in Black and Cox in terms of a time-dependent deterministic  barrier:

$$
\overline{{\nu}}(t)=K e^{-\gamma(t-T)},\,\,\,\,\,t\in[0,T),
$$

With some constant   $K$  . when the value of the firm crosses this lower threshold the  bond holders takeover the firm. Otherwise default takes place at maturity of debt  depending on whether or not   $V_{T}\geq L$  ,  where  $L$   represents (see footnote 7) the face value  of the firm’s debt.

$$
\nu_{t}=\left\{\!\!\begin{array}{l l}{{\overline{{\nu}}(t)}}&{{f o r\quad t\ \ <T,\nonumber}}\\ {{L}}&{{f o r\quad t=T.\nonumber}}\end{array}\right.
$$

The default time   $\tau$  is the first moment in the interval  $I0,\,T J$    when the firm’s value   $V_{t}$  falls  below the time varying level   $\nu_{t}$  ; otherwise the default event does not occur at all. The  default time   $\tau$  can be defined as

$$
\tau=\operatorname*{inf}{\left\{t\in[0,T]\colon V_{t}<\nu_{t}\right\}},
$$

Formally, we deal with the default able contingent claim   $(X,Z,{\overline{{X}}},\tau)$  which settles at time   $T$  ; where

$$
X=L,\,Z_{_T}=\beta_{2}V_{t},\,\overline{{{X}}}=\beta_{1}V_{_T}.
$$

The random variable  $X$    represents the firms liabilities to be redeemed at time  $T$   (promised  claim). If default does not occur prior to or at time   $T_{s}$  , the promised claim  $X$   is paid in full  at time  $T.$  . otherwise either:

(i)  default occurs at time   $t\ <\ T,$  , and the holder of the default able claim  receives the recovery payoff   $Z_{t}$  at time t, or:

The recovery process   $Z$  is assumed to be proportional to the firm’s value process:   $Z_{t}=\beta_{2}V_{t}$   for some constant   $\beta_{2}$   .  Similarly, the recovery payoff at maturity equals   $\overline{{X}}=\beta_{1}V_{T}$   for some constant   $\beta_{1}$   . The coefficient  β  and   $\beta_{2}$   are constant and represent the  bankruptcy costs. The default time   $\tau=\overline{{\tau}}\wedge\hat{\tau}$  where   $\overline{\tau}$  is the passage time of the firm’s  value process   $V$    to the deterministic barrier   $\overline{{\nu}}$  :

$$
\tau=\operatorname*{inf}{\big\{}t\in[0,T]\colon V_{t}\leq\overline{{\nu}}(t){\big\}}=\operatorname*{inf}{\big\{}t\in[0,T]\colon V_{t}<\overline{{\nu}}(t){\big\}}
$$

$\hat{\tau}$  is the Merton’s default time:
$$
\hat{\tau}=T1_{\{V_{T}<L\}}+\infty1_{\{V_{T}\geq L\}}.
$$

Assuming that for any   $t\in[0,T)$   we have   $\overline{{\nu}}(t)\leq L B(t,T)$  , where   $B(t,\ T)$    is the price of  default able zero coupon bond at time t with a maturity of   $T.$  .

$$
K e^{-\gamma(t-T)}\leq L e^{-r(T-t)}\ =L B(t,T).
$$

Thus the payoff to the bondholder at the default time   $\tau$  never exceeds the value of debt  discounted at the risk-free rate. At time   $t\,<\,T,$  ,  the value of a default able zero-coupon  bond with face value of   $L$    and maturity   $T,$  ,   denoted by   $D(t,\ T)$  ,  admits the following  probabilistic representation,   $\left\{\tau>t\right\}\,a n d=\left\{{\bar{\tau}}>t\right\}$  ,

$$
\begin{array}{r l r}{D(t,T)=E_{P}\big(L e^{-r(T-t)}1_{\{\bar{\tau}\geq T,\,V_{T}\geq L\}}\,|\,F_{t}\big)}&{}&{\mathrm{no\,\,default}}\\ {+\,E_{P}\big(\beta_{1}V_{T}e^{-r(T-t)}1_{\{\bar{\tau}\geq T,\,V_{T}<L\}}\,|\,F_{t}\big)}&{}&{\mathrm{default\,\,at}\,\,T}\end{array}
$$

$$
+\,E_{P}\Big(\beta_{2}K V_{T}e^{-\gamma(T-\bar{\tau})}e^{-r(\bar{\tau}-t)}1_{\{t<\bar{\tau}<T\}}\,\big|\,F_{t}\Big)
$$

After evaluating the above expectations, Bingham and Kiesel show a closed-form  solution for the value of a default able zero-coupon bond as a down-and-out barrier  option 9 . From this model, one can then infer the default probability from time  $t$    to   $T$  :

$$
P\big[\tau\leq T\,\big|\,\tau>T\big]=\,N(h_{1})+\exp\!\left(2\!\left(r-\frac{\sigma_{V}^{2}}{2}\right)\!\ln\!\left(\frac{K}{V_{t}}\right)\!\frac{1}{\sigma_{V}^{2}}\right)\!N(h_{2})\,,
$$

Where

$$
h_{1}=\frac{\ln\!\left(\displaystyle{\frac{K}{e^{-r(T-t)V_{t}}}}\right)\!+\!\displaystyle{\frac{\sigma_{V}^{2}}{2}}(T-t)}{\sigma_{V}\sqrt{T-t}},
$$

The first passage model have been extended to account for stochastic interest rates,  bankruptcy costs, taxed, debt subordination, strategic default, time dependent and  stochastic default barrier, jumps in the asset value process, etc. These extensions may  take into account several important market related factors but these improvements adds  significant complexity to the model. See Bielecki and Rutrkowski (2003) for more indepth analysis. Further discussion on calibration of the first passage model and  application to credit default swap market price quotes, see; Damiano Brigo and Marco  Tarenghi (2005) “credit default swap calibration and counter party risk valuation with a  scenario based first passage model” Working paper.
# 2.2.1 Other Structural Models

# 2.2.2 The Kim, Ramaswamy and Sundaresan 1993 Model

Kim, Ramaswamy and Sundaresan (1993) used simpler default boundary but more  realistic stochastic interest rate process the Black-Cox 1976 model. Default is triggered if  the asset value drops below an exogenous constant   $w.$  .  The interest rate process follows  the risk-neutral Cox-Ingersoll-Ross Model:

$$
d r=a(b-r)d t\!+\!\sigma_{1}\sqrt{r\,}d W_{1}
$$

Where   $r$    is the interest rate,   $a$     is mean reversion factor and   $b$    is long term average of   $r,$  ,  sigma is the volatility of   $r$    and   $W$  is Weiner process. This model has the convenient  property that the interest cannot become negative.

# 2.2.3 The Longstaff-Schwartz 1995 Model

Longstaff and Schwartz suggest a first-passage model with exogenous and constant  default boundary   $K$   and an exogenous and constant recovery rate   $w$  .  For the interest rate  process,  Longstaff and Schwartz use the well-known Vasicek model:

$$
d r=a(b-r)d t\!+\!\sigma_{1}\eta d W_{1}
$$

Where   $\eta$  is an exogenous constant and all the other parameters are the same as in the  Cox-Ingersoll-Ross Model. One of the key findings of Longstaff and Schwartz model is  that the long term average of the interest rate can be negative   $(b<O)$  . This implies that  the credit spreads decrease when the risk-free treasury rate increases. This seems  counter intuitive but can be explained by the fact that a higher interest rate implies higher  growth rate of the asset value  $V$   and as a consequence the probability of default is lower,  and with it the credit spread.
# 2.3.  Empirical tests from structural models

Hull, Nelken and White (2203) tested whether five year credit spreads implied from their  implementation of Merton’s model and the traditional implementation are consistent with  market quoted credit default swaps (CDS) premiums. There are number of reasons for the  difference between the credit spreads implied from Merton’s model and the market  observed credit default swaps spreads. According to Hull, Nelken and White (2203),  Merton’s model is not a perfect representation of market practise because firm’s do not  usually issue only zero-coupon debt.  Credit default swap spreads are also likely to be  slightly different from the bond yield spreads for some of the reasons listed in section 5.4.

Figure 2.3   Historical 5 year CDS spread vs Credit spread for France Tel.  (2003-2005)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7af753ce05927468a1e5023a66ee246bb10c8e33fba1cf7ae49ce3c5a395442c.jpg)
Source: Bloomberg LP. July 2005

The credit spread backed out from Merton’s model is the spread between the yield on  zero-coupon bonds while the credit default swap spreads are based on spread between the  yields on par yield bonds. The authors also suggest that there may be other factors other  than those suggested by Merton’s model may affect the CDS spreads. This is similar to  the conclusion drawn from the implementation of the reduced-form models. These factors  will be discussed briefly (see section 5.4).

# 3.1  Reduced-Form Credit Risk Models.

# 3.1.1  Intensity Based Model .

Reduced form models do not model the evolution of the firm’s value. Instead a specified  jump process models default exogenous ly. There are two classes of reduced form models.  They are intensity-based models that are concerned with modeling the time of the default  event and credit migration models that are concerned with modeling the migration  between credit ratings. Credit derivative models use intensity-based models, as it is the  modelling of the default event that is important in pricing credit derivative contracts. A  common problem with structural models is that default may occur before the boundary  conditions have been met and at other times it may not occur even when the boundary  conditions have been met. Intensity-based models therefore try to model the likelihood of  default rather than trying to specify the actual time of default. According to Bielecki and  Rutkowski (2002) intensity-based models were first formalized by Jarrow and Turnbull  (1995) and Madan and Unal (1998). In intensity based models the time of default is  modeled as the time of the first jump of a Poisson process with (possibly random)  intensity. The time of default is denoted by  $\tau$   and can be regarded as a stopping time. At  the stopping time  $\tau$    the default indicator function   $I(t)$   jumps from zero to one and is  denoted by
$$
I(t)\;\;=\;\;1_{\{\tau\leq t\}}=\;\left\{1\quad i f\quad\tau\leq t\right.
$$

In general, there could exist more than one stropping time   $\tau$  before time   $t$  . Assuming that    $\tau_{i}<\tau_{i+1}$    the collection of stopping times is given by the point process

$$
\{\tau_{i},i\in\mathbf{N}\}=\{\tau_{1},\tau_{2},.......\}.
$$

The counting process   $N(t)$   counts the number of stopping times of the point process that  are before time  $t$  , and is given by

$$
N(t)=\sum_{i=1}^{\infty}1_{\{\tau_{i}\leq t\}}.
$$

In reality there can only be one default event and so the time to default  $\tau$  is the time of the  first jump of  $N_{\cdot}$  ,

$$
\begin{array}{r}{\tau=\operatorname*{inf}{\left\{t\in\mathfrak{R}_{+}\,\vert\,N(t)>0\right\}},}\end{array}
$$

The probability of   $N(t)$   jumping in an infinitesimally small time interval is called the  default intensity function   $\lambda(t)$  or the  hazard rate . In order to determine the probability of  a default occurring in the time interval   $I0,\,T J,$  ,  it is useful to recap a few properties of the  Poisson process. Firstly, by the definition of a Poisson process the probability of   $n$   jumps  occurring in the time interval  $I0,\,T J$   is given by;

$$
P\big[N(t)-N(0)=n\big]\!=\!\frac{1}{n!}\!\bigg(\!\int_{0}^{T}\lambda(s)d s\bigg)^{\!n}\exp\!\bigg(\!-\!\int_{0}^{T}\lambda(s)d s\bigg).
$$

Secondly, this implies that the probability of no jumps occurring in the interval   $I0,\,T J$   is  given by

$$
P\big[N(t)-N(0)=0\big]\!=\!\exp\!\Bigg(\!-\!\int_{0}^{T}\lambda(s)d s\Bigg)\!=\!P(0,t)
$$

and, therefore,   $P(\boldsymbol{O},\,t)$   is the probability that no default events occur in the interval   $I0,\,T J$    and is called the survival probability. The probability that a default event occurs in the  interval is equal to one minus the probability of surviving. Hence the probability of  default   $P^{\mathit{d e f}}$  in the interval  $I O,\,t J$   is given by
$$
P^{d e f}(0,T)=1-P(0,t)=1-\exp\biggl(-\int_{0}^{T}\lambda(s)d s\biggr)
$$

The intensity approach to modeling credit risk was studied by, among others, Jarrow &  Turnbull (1995),  Jarrow et al. (1997), Duffie et al. (1996), Duffie (1998a), Lando  (1998a), Duffie and Singleton (1999), Elliot et al. (2000), Schonbucher (2000a, 2000b).

# 3.1.2 Jarrow and Turnbull (1995) – discrete approach.

Jarrow & Turnbull use the risk-free rate as numeraire, they build a discrete lattice for the  default-free term structure  as well as for default able one and show that, under this  numeraire, they can obtain unique risk-neutral or martingale probabilities such that the  value of default able bond can be expressed as a discount expectation under the riskneutral measure.  In this section we drive a simplified mathematical formulation of the  default probability with  no recovery rate using one period discrete time.

Define:       $y(T)$  :    Yield on a T-year corporate zero-coupon bond   $y^{*}(T)$  :   Yield on a T-year risk-free zero-coupon bond     $Q(T)$  :    Probability that a corporation will default between time zero and  $T$      or   $Q_{T}=Q(\tau<T)$   risk neutral probability of default before time   $T$       $Q(\tau>T)=(1\!-\!Q_{T})$   survival probability

  $\tau:$    Default time   $P_{t,T}$        Default free zero-coupon bond   $P^{d}{}_{t,T}$      Default able zero-coupon bond

The present value of a T-year risk-free zero-coupon with a redemption value of 100 is   $100e^{-y^{\ast}(T)T}$   while the present value of a corporate zero-coupon bond with similar maturity  is   $100e^{-y(T)T}$  . The expected loss from default is therefore

$$
100e^{-y^{^{\ast}(T)T}}\texttt{-}100e^{-y(T)T}=\!100[e^{-y^{^{\ast}(T)T}}-e^{-y(T)T}]
$$

Using the indicator function, the expected payoff of the default able bond can be written  as:

$$
I I_{\tau>T}=\left\{\begin{array}{l l l}{100}&{i f}&{\tau>T,}\\ {0}&{i f}&{\tau<T.}\end{array}\right.
$$

If we assume that there is no recovery in the event of default, the calculation of   $Q(T)$
is relatively easy. At maturity of the corporate bond, it will either be worth zero if default  takes place or 100 (par value of the bond) with probabilities of   $Q(T)$  or   $1\!-\!Q(T)$  respectively. Lets build a two state binomial tree from period 0 and   $\mathrm{T}$  , where the  node at   $t=0$   is the present value of the corporate bond, and nodes at period   $t=T$    are the  expected payoff of the bond if default takes place or not. From the tree below, we can  derive the risk-neutral default probabilities between period zero   and   $T.$  .

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b62cd5c929d1d649b0171ef44a6b64075b68f2f895e0421597191f9900a41108.jpg)

The value of the bond can be calculated as

$$
\begin{array}{l c l}{{100e^{-y(T)T}=100[1-Q(T)]e^{-Y^{*}(T)T}+[100Q(T)]0}}\\ {{\ }}\\ {{100e^{-y(T)T}=100[1-Q(T)]e^{-Y^{*}(T)T}}}\\ {{\ }}\\ {{100e^{-y(T)T}=100[e^{-y^{*}(T)T}-Q(T)e^{-Y^{*}(T)T}]}}\end{array}
$$

$$
\cfrac{100e^{-y(T)T}}{100}\,{=}\,\frac{100[e^{-y^{*}(T)T}-Q(T)e^{-y^{*}(T)T}]}{100}
$$

$$
e^{-y(T)T}=e^{-y^{\ast}(T)T}-Q(T)e^{-Y^{\ast}(T)T}
$$

$$
Q(T)e^{-Y^{*}(T)}=e^{-y^{*}(T)T}-e^{-y(T)T}
$$

$$
\frac{Q(T)e^{-y^{*}(T)T}}{e^{-y^{*}(T)T}}\!=\!\frac{e^{-y^{*}(T)T}-e^{-y(T)T}}{e^{-y^{*}(T)T}}
$$

$$
Q(T)=\frac{e^{-y^{*}(T)T}-e^{-y(T)T}]}{e^{-y^{*}(T)T}}\qquad\qquad\mathrm{or}\qquad Q(T)=1-e^{-[y(T)T-Y^{*}(Y)T]}.
$$

Probability of Default assuming recovery rate  $R$  :

If we use the same notation as before and suppose the expected recovery rate is   $R$  , then if  default takes place, the bondholder receives a proportion of   $R$   of the bond's no-default  value. If there is no default, the bondholder receives the face value of the bond (100).  Lets set up the same tree again but incorporate recovery rate of  $R$    this time.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3a9dec81bdca629168e65a0096f3601bf78a2c3ad88fa9636115e503b0435139.jpg)

We can derive the value of the bond as

$$
100e^{-y(T)T}=100[1-Q(T)]e^{-y^{*}(T)T}+~Q(T)100[R]e^{-y^{*}(T)T}
$$

Now, let   $\begin{array}{l l l}{-y(T)T}&{=}&{A}\\ {\;}&{\;}&{\;}\\ {-y^{*(T)T}=}&{B}\end{array}$  A

Then,

$$
\begin{array}{l}{{100e^{-A}=100[1-Q(T)]e^{-B}\,+\,Q(T)100[R]e^{-B}}}\\ {{\ }}\\ {{100e^{-A}=100e^{-B}-Q(T)100e^{-B}+Q(T)100e^{-B}}}\\ {{\ }}\\ {{100e^{-A}=100e^{-B}-Q(T)100e^{-B}[1-R]}}\\ {{\ }}\\ {{Q(T)100e^{-B}[1-R]=100e^{-B}-100e^{-A}}}\\ {{\ }}\\ {{Q(T)=\displaystyle\frac{100e^{-B}-100e^{-A}}{100[1-R]e^{-B}}=\,\,\,Q(T)=\displaystyle\frac{e^{-B}-e^{-A}}{[1-R]e^{-B}}}}\end{array}
$$

now, substituting A and  $\mathbf{B}$   for the original values, we have the solution

$$
Q(T)\!=\!\!\frac{e^{-y^{*(T)T}}-e^{-y(T)T}}{[1\!-\!R]e^{-y^{*(T)T}}}\!\qquad o r
$$

$$
Q(T)\!=\!\frac{1\!-\!e^{-[y^{*}(T)}\underbrace{-y(T)]T}}{e^{-y^{*}(T)T}}
$$
# Table 1.2

Default Free Bond 1 Default Free Bond 2 Default Free Bond 3

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/722db18e37580fa0016ab3ea0a5ae4eda62b9e556f62cff95d016b6d153a0434.jpg)

From table 1.2, we drive the risk-neutral default probability for default able bond from 1  year to 3 years using par default able and risk-free bonds with coupon payments. We use  the following notations to explain the above result 10 :

Define:       $S P(T)$     Discount factor spread for period   $T$   $Q(T)$  :    Default probability for period   $T$     $R$       Recovery rate      $D F_{\scriptscriptstyle B}(T)$    Benchmark discount factor for period  $T$

The default probabilities for period 1 to 3 are calculated as

$$
\begin{array}{r l}&{Q(1)=(S P(1)/(1-R)*D F_{B}(1))}\\ &{Q(2)=(S P(2)-S P(1))/(1-Q(1))(1-R)*D F_{B}(2))}\\ &{Q(3)=(S P(3)-S P(2)/(1-Q(1))(1-Q(2))(1-Q(3))(1-R)*D F_{B}(3))}\end{array}
$$

# Table 1.3

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/27312e1d25d641668a61c42ccbcf6cd81fe9ee9a1b595c7845838cbfb75cb212.jpg)

Default probability can be quantified in terms of default probability density or in terms of  hazard rate. The (risk neutral) hazard rate   $\gamma=\gamma(t)$   is defined by
$$
\gamma(t)d t=Q(t<\tau\leq t+d t\,|\,\tau>t),
$$

Which is the probability of default between time   $t$    and   $_{t+d t}$    conditional on  no earlier  default.   $\gamma(t)d t$   is the likelihood of default between time   $t$   and time   $_{t+d t}$     conditional on   $q(t)d t$  no default between time zero and time   $t.$  .   The default probability density   is the  unconditional default probability between times  $t$     and time   $_{t+d t}$     conditional as seen at  time zero and the relationship between    $\gamma(t)$   and   $q(t)$   is:

$$
q(t)=h(t)e^{-\int_{0}^{t}h(\tau)d\tau}
$$

Table 1.3 lists the unconditional probabilities of default as seen at time zero. The default  probability for year 5 is computed as   $1.2921\%$  . The hazard rate is the default probability  in year 5 given that no default has taken place up to year 4. The probability of no default  prior to year 4 is   $1\mathrm{~-~}0.0033428\mathrm{~=~}0.966572\%$  . The hazard rate for year 4 is therefore   $0.012962/0.966572=1.3410\%$

# 3.2.  Arbitrary deterministic recovery, deterministic interest rates.

If the recovery rate at the random default time   $\tau$  i s   $Z(\tau)$  , where the function   $Z=Z(t)$  is  some deterministic function of time, and also that the risk-free interest rate   $r(t)$    depends  deterministic ally on time. The price of default able bond via risk-neutral pricing is then  given by,

$$
P_{0,T}^{\,d}=E_{\mathcal{Q}}\Bigg(e^{-\int_{0}^{T}\!\!r(u)d u}\ \ 1_{\tau>T}\ +e^{-\int_{0}^{\tau}\!\!r(u)d u}\ \ Z_{\tau}\ \ 1_{\tau\leq T}\Bigg).
$$

To compute this, one needs the probability distribution of the default time   $\tau$  . Instead of  working directly with   $Q(\tau>T)$  , we use a closely related quantity, the  hazard rate  which  is specified above.

$$
\gamma(t)d t=Q(t<\tau\leq t+d t\,|\,\tau>t),
$$

The relationship between the hazard rate and the cumulative distribution function (cdf) of   $\tau$    is described:

Lemma 3.1. For all   $t\geq0$  , we have that

$$
Q(\tau>t)=e^{-\int_{0}^{t}\gamma(u)d u}\,,
$$

Consequently, the cdf and the pdf of   $\tau$  with respect to the probability   $Q$   are,

$$
F_{\tau}(t)=F_{\tau}^{\,Q}(t)=Q(\tau\leq t)=1-e^{-\int_{0}^{t}\gamma(u)d u}
$$
And

$$
f_{\tau}^{\mathbf{\Omega}}(t)=f_{\tau}^{\mathbf{\Omega}}(t)=\gamma(t)e^{-\int_{0}^{t}\gamma(u)d u}
$$

Which is the derivative of    $\boldsymbol{F}_{\tau}$  11

Now revisiting the zero-coupon bond price of a default able bond with zero recovery but  with deterministic and time dependent interest rate,

$$
p a y o f\!f=\left\{\!\!\begin{array}{c c c}{{1}}&{{i f}}&{{\tau>T,}}\\ {{0}}&{{i f}}&{{\tau<T.}}\end{array}\right.
$$

Then;

and

$$
\begin{array}{l}{{P_{0,T}^{\,d}=e^{-\displaystyle\int_{0}^{T}\!\!r(u)d u}\,Q(\tau>T)+0.Q_{t}=}}\\ {{\mathrm{}}}\\ {{P_{0,T}^{\,d}=e^{-\displaystyle\int_{0}^{T}\!\!r(u)d u+\gamma(u)d u}}}\end{array}
$$

That is, instead of discounting with  $r(t)$  ,  we discount with   $r(t)$    and   $\gamma(t)$  .   where     $\gamma(t)$   is an  instantaneous spread.

If we now assume a deterministic recovery   $Z(\tau)$  at time   $\tau$  , that is, the amount of   $Z(t)$  recovered should default time happen at   $t$   $(t=\tau)$  is known beforehand; the quantity   $Z(\tau)$   is random variable since   $\tau$   is a random variable. As before:

$$
P_{0,T}^{\,d}=E_{\mathcal{Q}}\Bigg(e^{-\int_{0}^{T}\!\!r(u)d u}\ \ 1_{\tau>T}\ +e^{-\int_{0}^{\tau}\!\!r(u)d u}\ \ Z_{\tau}\ \ 1_{\tau\leq T}\Bigg).
$$

The discount factor   $e^{-\int_{0}^{T}\!\!r(u)d u}$   is pulled out of the expectation sign since   $r(t)$   is assumed to  be deterministic. However the second discounting factor is stochastic because of the  random time   $\tau$   and cannot be pulled out of the expectation sign. As specified above the  first discount factor in equation  (26)  is adjusted;   $e^{-\int_{0}^{T}\!\!r(u)d u+\gamma(u)d u}$   and we evaluate the  remaining expression inside the expectation sing with the random component (second  term in equation  (27):

$$
E_{\mathcal{Q}}\Bigg(\;e^{-\int_{0}^{\tau}\!r(u)d u}\;\;Z_{\tau}\;\;1_{\tau\leq T}\;\Bigg).
$$

We had an expression for the probability of default between   $(t,\,t{+}d t)$  :
$$
\begin{array}{r l}&{f_{t}^{\mathcal{Q}}=Q(t<\tau\leq t+d t)=\gamma(t)Q(\tau>t)d t=\gamma(t)e^{-\int_{0}^{\tau}(\tau u)d u}}\\ &{E_{\mathcal{Q}}\Bigg(\begin{array}{l l}{e^{-\int_{0}^{\tau}(u)d u}}&{Z_{\tau}}&{f_{t}^{\mathcal{Q}}}\end{array}\Bigg),}\\ &{E_{\mathcal{Q}}\Bigg(e^{-\int_{0}^{\tau}(r(u)d u}}&{Z_{\tau}}&{\gamma(t)e^{-\int_{0}^{\tau}(\tau(u)d u}\Bigg).}\end{array}
$$

The last equation cane be written as;

$$
E_{\varrho}\Bigg(Z(s)\:\:\gamma(s)\:e^{-\int_{0}^{s}r(u)d u+\gamma(u)d u}\:d s\Bigg).
$$

Then;

$$
P_{0,T}^{d}=\left(e^{-\int_{0}^{r_{r}(u)d u+\gamma(u)d u}}+\int_{0}^{T}Z(s)\;\;\gamma(s)\;e^{-\int_{0}^{s_{r}(u)d u+\gamma(u)d u}}\;d s\right).
$$

And the price at time  $t_{.}$  ;

$$
P_{t,T}^{\,d}=\!1_{\tau>t}\!\left(\,e^{-\int_{0}^{t_{r}}\!\!r(u)d u+\gamma(u)d u}+\int_{0}^{T}\!Z(s)\;\;\gamma(s)\;e^{-\int_{0}^{s}\!\!r(u)d u+\gamma(u)d u}\;d s\right)\!.
$$

# 3.2.1 Stochastic recovery, interest rate and hazard rate

In stochastic interest rate environment, and with stochastic recovery   $Z(\tau)$  and hazard rate   $\gamma(t)$  . , one has:

$$
P_{t,T}^{\,d}=\!1_{\tau>t}\!\left\{\!E_{\varrho}\!\left(e^{-\!\int_{0}^{T}\!\!r(u)\,d u+\gamma(u)\,d u}\;\vert\;f_{t}\right)\!+\!E_{\varrho}\!\left(\!\int_{t}^{T}Z(s)\;\,\gamma(s)\,\,e^{-\!\int_{0}^{s}\!\!r(u)\,d u+\gamma(u)\,d u}\,\,d s\,\vert\;f_{t}\right)\!\right\}
$$

For more rigorous proof, see Bielecki and Rutkowski (2002) “Credit Risk” Springer  Verlag.

In case of zero recovery, the last term of the above equation drops out and we are left  with;

$$
P_{t,T}^{d}=1_{\tau>t}\Bigg\{E_{\mathcal{Q}}\Bigg(e^{-\int_{0}^{T}(u)d u+\gamma(u)d u}\mid f_{t}\Bigg)\Bigg\}
$$
# 3.2.2 Recovery Protocols

In the real world payoffs of defaulted securities are usually greater then zero. The  recovery rates (given default), denoted by   $Z(\tau)$  , is defined as the extent to which the  value of an obligation can be recovered once the obligor has defaulted, i.e. the recovery  rate is a measure for the expected fractional recovery in case of default and such that it  takes any value in the interval   $I0,\,T J$  . The loss rate (given default), is defined as 1 minus  recovery rate.

# Fractional Recovery of Par:

It is assumed that there is a compensation in terms of cash (invested in risk-free money  market account) and the recovery rate is expressed as a fraction of par. The model has  been applied, e.g., by Duffie (1998b).

If   $V$   represents the claims constant par value and   $\delta$   is the claims recovery rate, then;    $Z_{t}=V\delta$   and

$$
P_{t,T}^{d}=\!1_{\tau>t}\Bigg\{E_{Q}\!\left(e^{-\int_{r}^{r}(u)d u+\gamma(u)d u}\,V\,{\mid f_{t}\right)+E_{Q}\!\left(\delta V\!\int_{t}^{T}Z(s)\,\,\gamma(s)\,\,e^{-\int_{t}^{s}(u)d u+\gamma(u)d u}\,d s\,{\mid f_{t}\right)\!\Bigg\}}
$$

# Fractional Recovery of treasury:

It is assumed that there is a compensation in terms of (the value of) non-default able  bonds, i.e. the value of equivalent treasury bond. Several authors have proposed this  model, e.g., Jarrow & Turnbull (1995), Madan & Unal (1998).

In the even of default, recovery is then given by:    $\boldsymbol{Z}_{\tau}=\delta e^{-\int_{\tau}^{T}\boldsymbol{r}(u)d u}$  and the price of a  default able bond using this assumption;

$$
P_{t,T}^{d}=\!1_{\tau>t}\!\left\{E_{Q}\!\left(e^{-\!\int_{t}^{\tau}\!(u)d u+\gamma(u)d u}\,V\,|\,f_{t}\right)\!+E_{Q}\!\left(\delta\!\int_{t}^{T}\,\gamma(s)\;e^{-\!\int_{t}^{\tau}\!(u)d u}\,|\,f_{t}\right)\!\right\}
$$

# Fractional Recovery of market value:

It is assumed that there is a compensation in terms of equivalent default able bonds, which  have not defaulted yet, i.e. the recovery rate is expressed as a fraction of the market value  of the defaulted bond just prior to default. This model was mainly developed by Duffie &  Singleton (1997).

Assume   $Z_{\tau}$   is a positive fraction of the market value of the bond just prior to default   $Z_{\tau}=\delta P_{t,\tau}^{d}$  , then;
$$
P_{t,T}^{\,d}=\left\{E_{\mathcal{Q}}\Bigg(e^{-\int_{t}^{T}(u)d u+s(u)d u}\mid f_{t}\Bigg)\right\}
$$

Where   $s(u)=(1-\delta_{u})\gamma_{u}$  , and   $\delta_{u}$   is the loss rate and  γ  is the intensity of default.

# 4.1    Jarrow, Lando and Turnbull (1997) model – discrete approach.

Jarrow, Lando and Turnbull model is a Markov model for the term structure of credit  spreads based on the earlier Jarrow and Turnbull (1995) paper, but linking the default  process to a discrete state space Markov chain in credit ratings, i.e. the life of the firm is  viewed as a journey through the possible rating states where one of them is an absorbing  state. This model provides great flexibility to calculate the parameters to observable data  and to use it for many purposes: pricing and hedging of bonds with embedded options,  pricing of credit derivatives. The main assumption of this approach is that ratings are an  accepted indicator of a firm’s credit worthiness. Default is exogenous process that does  not require dependence of the underlying asset of the firm. The advantage of such  methods against the structural models introduced above is that we can restrict the  calibration to the available observable s; there is no particular economic requires. Here are  a list of all the ingredients for this model:

Forward rates are defined in discrete time as

$$
f(t,T)=-\ln\!\left(\frac{p(t,T+1)}{p(t,T)}\right)\!.
$$

Under this construction, the instantaneous interest rate   $r(t)$    is equivalent to  $f\!(t,\,T)$  The money market account value is similarly given by

$$
B(t)=\exp\!\left(\sum_{t=0}^{t-1}r(i)\right)
$$

Under the assumption of complete arbitrage-free markets, we have the following  relationship:

$$
B(t)=\overline{{E}}_{t}\Bigg(\frac{B(t)}{B(T)}\Bigg).
$$

And the price of default able bond taking into account the default likelihood is they given  by:

$$
P_{t,T}^{d}=\overline{{E}}_{t}\Bigg(\frac{B(t)}{B(T)}\big(\delta\boldsymbol{1}_{\tau\leq T}+\boldsymbol{1}_{\tau>T}\big)\Bigg).
$$
if default takes place, the payoff is assumed to be fractional recovery of treasury as  specified by Jarrow and Turnbull.  Since the default free term structure and the default  time are assumed to be independent, then;

$$
\begin{array}{l l}{P_{t,T}^{d}=\displaystyle\overline{{E}}_{t}\bigg(\frac{B(t)}{B(T)}\bigg)\overline{{E}}_{t}\big(\delta\boldsymbol{1}_{\tau\leq T}+\boldsymbol{1}_{\tau>T}\big)}\\ {\displaystyle\qquad=p(t,T)(1-\delta)Q_{t}(\tau>T)),}\end{array}
$$

Where   $Q_{t}(\tau>T)$  is the probability that the firm will not default before the maturity  (survival probability).

The contribution of Jarrow et al. (1997) articulates around the specification of the  bankruptcy process as the first hitting time of a time-homogenous Markov chain. This  Markov chain is modelled on a finite state space   $S$    consisting in the credit rating classes   $\{I,\,.\,.\,.\,.\,.\,.\,.\,.\,.\,.\,.\}$  ,  where the   $K–I$    class is the lower credit rating class, while class  $K$    is the  absorbing state representing the bankruptcy state. This Markov chain is specified by  $K x K$  transition matrix:

$$
Q=\left|\begin{array}{l l l l}{q_{11}}&{q_{12}\dots}&{q_{1k}}\\ {q_{21}}&{q_{22}\dots}&{q_{2k}}\\ {\cdot}&{\cdot}&{\cdot}\\ {\cdot}&{\cdot}&{\cdot}\\ {q_{k-1,1}}&{q_{k-1,2}\dots}&{q_{k-1,k}}\\ {0}&{0}&{\dots}&{1}\end{array}\right|,
$$

Where all transition probabilities are positive and   $\boldsymbol{\mathbf{\Sigma}}=\boldsymbol{\mathbf{\mathit{q}}}_{i i}\equiv\sum_{\stackrel{j=1}{i\neq j}}^{K}\boldsymbol{\mathbf{\mathit{q}}}_{i j}$  , ∀ i

Each of the   $q_{i j}$  probabilities represent the probability of getting from class   $i$    to class  $j$   in  one period of time. The last line in equation   $(36)$    represents the probabilities attached to  the absorbing state: the probability of leaving this state is always null and the probability  of staying in this state in 1. Once a firm is in default, it will stay in default. Estimates of  these transition probabilities can be found in the reports of credit rating agencies such as  Moody’s or Standard and Poor.
Table 1.4   Credit rating transition matrix
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/69598335d736411d4250678db0bf70cbbd3c7c892cd30614057e35913e21f9fc.jpg)
Source:  Moody’s 2001

From table 1.4,   $q_{i j}$  is the historical (“real-world”) probability of moving from credit rating  class   $i$    to class  $j$   in one year as stated above. As mentioned by Jarrow et al., nonzero  probabilities tend to concentrate on the diagonal for a 1-year transition matrix since a  movement of more than one rating class is quite improbable.

Following from equation  (36),  the transition matrix under the equivalent martingale 13 measure can be written as:

$$
\begin{array}{r l}&{Q_{t,t+1}=\left|\begin{array}{l l l l}{\boldsymbol{q}_{11}(t,t+1)}&{\boldsymbol{q}_{12}(t,t+1)\ldots}&{\boldsymbol{q}_{1k}(t,t+1)}\\ {\boldsymbol{q}_{21}(t,t+1)}&{\boldsymbol{q}_{22}(t,t+1)\ldots}&{\boldsymbol{q}_{2k}(t,t+1)}\\ {\cdot}&{\cdot}&\\ {\cdot}&{\cdot}&\\ {\boldsymbol{q}_{k-1,1}(t,t+1)}&{\boldsymbol{q}_{k-1,2}(t,t+1)\ldots}&{\boldsymbol{q}_{k-1,k}(t,t+1)}\\ {0}&{0}&{\ldots}&{1}\end{array}\right|,}\end{array}
$$
 ,

Where

$$
\begin{array}{r}{q_{i j}\left(t,t+1\right)\geq0,\;\forall i,j,\;\,i\neq j\;\,a n d\;\,q_{i i}\left(t,t+1\right)\equiv1-\sum_{i\neq j}^{K}q_{i j}\left(t,t+1\right).}\end{array}
$$

Additionally

In the Jarrow and Turnbull (1995) model, default probabilities and credit derivative prices  were derived on the basis of illiquid bond prices. However, the Jarrow, Lando, and  Turnbull (1997) model replaced bond prices as the main input and apply historical  transition probabilities as the basis for their analysis. Today, many investment banks and  insurance companies apply the 1997 model and its extensions to price and hedge credit  derivatives.  Some of the short comings of this model is that asset-liability structure of a  company, is not part of the analysis (this may be argued to be the ultimate economic  reason of default). Also, interest rate process and bankruptcy process are assumed to be  independent. Jarrow, Lando and Turnbull also assume that bonds in the same credit class  have the same yield spread.  Longstaff and Schwartz (1995) pointed out that this was not  necessarily the case. Rating are also done infrequent and may not be recent enough to  reflect current counter party risk.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/326b34af9c63d3c209d74a25ff801cbd72e63d20368c4480e9cd7c61fd6cf7fb.jpg)
Figure 3.1   Credit Spread Term Structure

Figure 3.1 shows the default probabilities for various credit rating classes calculated in  excel spreadsheet. See appendix A for spreadsheet used to generate one period transition  matrix.

In the following section, Duffie and Singleton model will be used to drive a theoretical  and arbitrage free credit default swap (CDS) premium. We will also implement other  numerical models using binomial tree to drive non-arbitrage CDS prices.
# 5.1  Pricing Credit Default Swaps

Credit default swaps (CDS) are a form of insurance against possible default of a reference  issuer, or a bond issued by this issuer. The protection seller promises to compensate the  protection buyer in the event of default of the reference issuer. In return, the protection  buyer pays a constant periodic payment, which terminates at the earlier of the CDS  maturity or a default event.

There are number of variations on the standard credit default swap. In  binary credit default swap , the payoff in the event of default is a specific dollar amount. In a  basket  credit default swap , a group of reference entities are specified and there is a payoff when  the first of these reference entities defaults. In a  contingent credit default swap , the payoff  requires both a credit event and additional trigger. The traditional trigger might be a  credit event with respect to another reference entity or a specified movement in some  market variable.

Several papers have addressed the theoretical pricing of credit derivatives during the last  few years. Longstaff Schwartz (1995) present the pricing of credit spread options based  on exogenous mean-reverting process for credit spreads. Duffie (1999) presents a simple  argumentation for the replication of as well as a simple reduced form model of the  instrument. In the this section, we introduce a reduced-form type pricing model  developed by Hull and White (2000), where they calibrate their model based on the  traded bonds of the underlying on a time series of credit default swap prices on one  underlying.  Like most other approaches, their model assumes that there are no counter  party default risk. Default probabilities, interest rates, and recovery rates are independent.   Finally, they also assume that the claim in the event of default is the face value plus  accrued interest. Consider the valuation of a plain vanilla credit default swap with   $1\S$  notional principal.  Using the notations below, we proceed to show the reduced-form  pricing model.

Figure 3.2   Payment structure of a CDS before and in the event of default

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/01642fde86b6f6fe277c17671005efdc2f3911a2ca701e77b4ecd1459d330bf2.jpg)
# Notations

$P(0,T)=$   Price today of a  $\S1$   risk-free discount bond maturing at time   $T$

$C_{R}(T)=$   Par risky coupon rate for maturity   $T$  , in percent   $q(t)=$        Default probability density at time   $t$  , conditional on no prior default   $Q(t)=$       Cumulative default probability density up to time   $t$

$$
Q(T)=\int_{0}^{T}q(t)d t
$$

R = Recovery rate: fractional amount of bond value recovered on default.   $A I(t)=$  Accrued interest function, based on   $1\%$   per annum coupon.

$$
A I(t)={\begin{array}{r l r l}{t-t_{i-1}}&{,t_{i-1}<t<t_{i}}\\ {0}&{,t=t_{i}}\end{array}}&&{{\mathrm{~where~}}i{\mathrm{~is~such~that~}}t_{i-1}<t\leq t_{i}
$$

Note: for simplicity of notations, we assume in the following equations that bond coupon  payment dates and premium payment dates coincide.

A Credit Default Swap (CDS) provides protection against default of a reference issuer.  The buyer of the protection pays a premium in the form of regular fixed payments   $S\;(\%,$  ,  annualized) for the duration of the protection period, or up to a default event. The  protection seller will pay in the event of default of the reference issuer the difference  between par and the post-default value of the bond.

The expected present value of the “premium” leg of the CDS is

$$
S\biggl[\sum_{j=1}^{m}\bigl\{1-Q(t_{j})\bigr\}P(0,t_{j})\Delta t_{j}+\int_{0}^{T}q(t)A I(t)P(0,t)d t\biggr]
$$

The two terms correspond, respectively, to premium payments (made if default has not  occurred) and payments of accrued premium (if default has occurred). If we assume that  in the event of a future default, the recovered amount is   $R$    times par plus accrued  interest, the expected present value of the “protection” leg of the CDS is

$$
\int_{0}^{T}q(t)\big[100-R\big\{100+A I(t)C_{\scriptscriptstyle R}(T)\big\}\big]P(0,t)d t
$$

The market value of a CDS is the difference between the two legs.

At initiation of a CDS, the premium (the CDS spread) is set to the value   $S=S_{C D S}\left(T\right)$  such that the two legs of the CDS are equal, and the CDS has zero initial value. Solving  for the spread:
$$
S_{C D S}(T)=\frac{\displaystyle\int_{0}^{T}q(t)\big[100-R\big\{100+A I(t)C_{R}(T)\big\}\big]P(0,t)d t}{\displaystyle\sum_{j=1}^{m}\big\{1-Q(t_{j})\big\}P(0,t_{j})\Delta t_{j}+\displaystyle\int_{0}^{T}q(t)A I(t)P(0,t)d t}
$$

This equation gives the value of a par CDS spread, with the default probability curve  used as an input. Conversely, if we have a curve of par CDS spreads, we can use a  bootstrap procedure to infer the default probability curve.

Note: if we do not want to include accrued interest in the default claim, we set   $A I(t)\equiv0$  .

The variable   $S_{C D S}(T)$  is referred to as the credit default swap spread or CDS spread. The  formula at   $(4O)$     is simple and intuitive for developing an analytical approach for pricing  credit default swaps because of the assumptions used. The spread   $S_{C D S}(T)$   is the payment  per year, as a percent of notional principal for newly issued credit default swap contract.  Table 1.5 shows the market value of    $S_{C D S}(T)$   for a list of reference names. For example  the quoted CDS bid/ask spread for a maturity of 5 years for France Telecommunications  is: 38/44 basis points for bid and ask respectively.

Table 1.5   CDS quotes: Telecoms and Electronics – Banco Bilbao
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a3358ffb964ed7e5d44ea2a57483614a4e14cd36633c5c29883c3e1da755d36c.jpg)
Source: Bloomberg LP. July 2005

To implement the above model in order to approximate the quoted market prices, one  need to link the rates observed in the credit protection market and the corporate bond  market via probabilities of default of the issuer. The input used to price the CDS contract  should be selected from a range of market observed yield curves which should include; a  curve of CDS spreads, an issuer (credit-risky) par yield curve, and default probability  curve. The assumptions based on the independence of recovery rates default probabilities  and interest rates may not hold completely in practice since high interest rates may cause  companies to experience financial difficulties and default or administration, and as a  result of this default probabilities would increase. Thus, a positive relation between  interest rates and default probabilities may be associated with high discount rates for the  CDS payoffs, and this would have the effect of reducing the CDS spread. Nevertheless,  the Hull-White approach presents a neat and intuitive approach that allows for a closedform pricing approach for credit default swap, calibrating market data.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7c1f640b2718aebe319d80451734be16097d0bcad71c72ff6aed256aba5f9ff9.jpg)
Figure 4.1   Historical CDS for selected Telecoms reference names (2003-2005)

Source: Bloomberg LP. July 2005  Reference names: British Tel. Deutsche Tel. France Tel. Nokia, Telefonica, Vodafone, Telenor

As an extension of the above model, Hull and white (2001) investigate the impact of  counter party default risk on the value of vanilla CDS.  They find that this impact is small  when the credit quality correlation between the counter party and the reference entity is  zero. It increases as the correlation increases and the credit worthiness of the counter party  declines.

# 5.3  Relating risky par rates & default probabilities

We assume that if a bond defaults, the amount recovered is a fraction   $R$    of the par value  of the bond plus accrued interest. Recovery rates are usually reported as the ratio of the  post-default value of the bond and its par value.

The equation relating the risk-free discount curve   $P(0,t)$  , the risky par rate   $C_{R}(T)$  , the  recovery rate   $R$   , and the default probability curve   $Q(t)$   is

$$
\begin{array}{l l}{{100=C_{R}(T)\Bigg[\displaystyle\sum_{i=1}^{n}\bigl\{1-Q(t_{i})\bigr\}P(0,t_{i})\Delta t_{i}+\displaystyle\int_{0}^{T}q(t)A I(t)P(0,t)d t\Bigg]+100\bigl\{1-Q(T)\bigr\}P(0,T)}}\\ {{\quad\quad\quad+\displaystyle\int_{0}^{T}q(t)R\bigl\{100+A I(t)C_{R}(T)\bigr\}P(0,t)d t}}\end{array}
$$

The first term on the RHS is the sum of all coupons paid assuming that default has not  occurred before their payment times. The second term takes accrued interest into account:  if default occurs in the middle of a coupon payment period, interest accrued on the  coupon is paid. The third term is the bond face value, assuming that the issuer had not  defaulted before maturity. The fourth term sums recovered values (R times par plus  accrued interest) assuming default before maturity of the bond. All future payments are  discounted using the risk-free discount rates. Since this is a par risky bond, the four RHS  terms sum up to 100.
If the default probability curve is known, we can compute the risky par curve directly. If  the risky par curve is known, we can infer the default probability curve using a bootstrap  procedure.

# 5.4  CDS model using stochastic interest rate and intensity process

In this section, we present similar closed-form model for valuing credit default swaps  within the reduced-from framework of Duffie (1998), Lando (1998), Duffie and  Singletob (1998), and others. The default intensity is modeled as square-root process and  explicit solution of credit default swap premia is given. Following standard notion, let   $r_{t}$  denote the risk-free rate and   $\lambda_{t}$   the intensity of the Poisson process governing default.  Both   $r_{t}$   and   $\lambda_{t}$   are stochastic and are assumed to follow independent processes. In the  event of default, the bond holders are assumed to recover a fraction   $1\!-\!w$   of the par value  of the bond. The value of risk-free zero-coupon bond   $P(0,T)$  with maturity of   $T$  is given  by;

$$
P(0,T)=E{\Bigg[}\exp\!{\Bigg(}\!-\!\int_{0}^{T}r_{t}d t{\Bigg)}{\Bigg]}
$$

The risk-neutral dynamics of the intensity process   $\lambda_{t}$   is given by

$$
d\lambda=(\alpha-\beta\lambda)d t+\sigma{\sqrt{\lambda}}\,d Z
$$

Where   $\alpha,\,\beta$  β  and   $\sigma$  are positive constants, and   $Z_{t}$   is a standard Brownian motion. These  dynamics allow for both mean reversion and conditional heteros ke d asti city in corporate  spreads and guarantee that the intensity process is always non negative. Given these  dynamics, the probability that default has not occurred by time   $T$    is given by;

$$
\exp\!{\bigg(\!-\!\int_{0}^{T}\;\lambda_{t}\:d t\bigg)}
$$

And the density function for the time until default is given by

$$
\lambda_{s}\exp\biggl(-\int_{0}^{t}\;\lambda_{s}\:d s\biggr)d t
$$

From Duffie (1998), Lando (1998), Duffie and Singleton (1999), the value of corporate  bonds and the premium and the protection leg of credit default swap can be expressed as  expectations under the risk-neutral measure. Letting   $c$   denote the coupon rate of  default able bond, then the price of the bond which is a function of   $C B(c,w,T)^{I4}$   can be  expressed as:
$$
\begin{array}{r}{P_{0,T}^{d}=E\bigg[c\!\int_{0}^{T}\exp\!\bigg(\!-\!\int_{0}^{t}\,r_{s}+\lambda_{s}d s\bigg)\!d t\bigg]\!+E\bigg[\exp\!\bigg(\!-\!\int_{0}^{T}\,r_{t}+\lambda_{t}d t\bigg)\bigg]}\\ {+\,E\bigg[(1\!-\!w)\!\!\int_{0}^{T}\,\lambda_{t}\,\exp\!\bigg(\!-\!\int_{0}^{s}\,r_{s}+\lambda_{s}d s\bigg)\!d t\bigg].}\end{array}
$$

The first term in equation (46) represents the present value of the coupon portion of the  bond, the second term represents the present value of the promised principal payment,  and the third term is the present value of the recovery payments in the event of default.   As before, let   $s$    denote the premium paid by the buyer of default protection. The present  value of the premium leg of a credit default swap  $P(s,\,T)$    can be expressed as

$$
P(s,T)=E{\Biggr[}s{\int_{0}^{T}}\exp\Bigl(-\int_{0}^{t}\;r_{s}\;+\lambda_{s}d s\Bigr)d t{\Biggr]}
$$

And the value of the protection leg   $P R(w,T)$   can be expressed as

$$
P R(w,T)=E\Bigg[w\!\!\int_{0}^{T}\exp\!\Bigg(\!-\!\!\int_{0}^{t}r_{s}+\lambda_{s}d s\Bigg)\!\!\Bigg]d t\Bigg]
$$

As before, we solve for  $s$    by setting the value of the protection and premium legs equal to  each other. We  then have

$$
s=\frac{E\biggl[w\!\int_{0}^{T}\lambda_{t}\exp\Bigl(-\int_{0}^{t}r_{s}+\lambda_{s}d s\Bigr)d t\biggr]}{E\biggl[\int_{0}^{T}\exp\Bigl(-\int_{0}^{t}r_{s}+\lambda_{s}d s\Bigr)d t\biggr]}
$$

To provide some intuition about the credit default swap market, Duffie (1990) shows that  premium equals the fixed spread over the risk-free rate that a corporate floating rate note  would need to pay to be able to sell at par. Thus if both a firm and the treasury issued  floating rate notes tied to the risk-free rate, the fixed spread between rates paid by the  floating rate notes would equal the credit default premium  s . This result is however not  the case for the yield spread between corporate and treasury fixed rate bonds. Longstaff.  F.A., Mithal S. and Neis E. (2003) apply the closed form solution is equation (48) and fit  the model to the prices of corporate bonds. They solve for the premium implied by the  model. The model implied values of the premia are then compared with the actual market  credit default swap premia.
Longstaff. F.A., Mithal S. and Neis E. (2003) used credit default swap data for 5 year  contract and corresponding bond prices provided by Citigroup for 68 firms for the period  of march 2001 and October 2002. They estimated the dynamics of the intensity process  for each of the firm as well as all the intensity parameters in order to estimate default  swap prices for these firms. Their result showed wide variation in credit default swap  premia, both overtime and across firms. See table 1.6.

Table 1.6  Summary Statistics for the Differences Between Model Implied and Market Credit-Default  Swap Premia.  This table reports summary statistics for the differences between the premia implied by the fitted credit  model and market premia for the indicated firms. Differences are expressed in basis points. Averages reported at the  bottom of the table are cross-sectional averages of the indicated summary statistics taken over all firms.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/81728fbdfd843b5475bda6d9f1e5239d8fe376a11e926df40bd336c051b3d6d0.jpg)

Table   $1.6^{15}$   shows the empirical result from Longstaff. F.A., Mithal S. and Neis E. (2003)  where summary statistics for the difference between the model implied and the market  credit default swap premia are reported.  These summary statistics include the average  differences with their associated t-statistics, the minimum and maximum values of the  difference, and the serial correlation of the difference.  One of the most striking result  from their investigation is that the average difference or pricing error is positive for all  the firms (68) in the sample. Thus, the premia implied by fitting the model to the market  prices of corporate bonds are all greater on average then the actual credit default swap  premia observed in the market. They show that all of the average differences are highly  statistically significant based on their t-statistics.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1dd1aa0974754e8b35f623611ed07b79a787923f3f8957142f119d0708a23bd7.jpg)
Figure 4.2   Histogram-  distribution of average premium differences across firms.

These result strongly suggest that the cost of credit protection in the credit default swap  market is significantly less than the cost implied from the corporate bond prices. Because  of the cross sectional variations in the differences between implied and market premia, it  is possible that other factors may be effecting the cost of protection.

In this section, we list a number of suggested factors that may contribute to the significant  differences between market observed CDS prices and modeled CDS prices.

# Differences in Taxation:

The differences in taxation between corporates and treasuries might explain a significant  portion of the yield spread. Credit swap premium should reflect only the actual risk of  default on the underlying bonds. Thus, if the spread between corporates and treasuries are  partly tax related and partly default related, then this portion of the spread should not be  incorporated into the credit default swap premium.

# Differences in liquidity:

If corporate bonds are less liquid then treasury bonds, then corporate bond spreads could  also include liquidity spread. Thus, the liquidity of corporate bonds should not affect the  cost of credit protection in the CDS market. This implies that if corporate bond yields  include liquidity component, then the credit default swap premia should be less then the  premia implied from corporate bonds. This is consistent with the result presented in table  1.6.
# Modeling error:

Another possible factor due to premia differences may be simply model error. That is,  some key feature of the data is being missed by the model used to estimate the implied  credit default swap premium from corporate bond prices.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/162dd4147f21b059775c76e61a2dda2a6ff81eb22d7353e21498dba01ee0ac30.jpg)
Figure 4.4.1   Market vs implied CDS (Enron).

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6769da2987daf44e5d55cfa301b24dd8ee2f6e694ce579130254ac34a135f4fb.jpg)
Figure 4.4.2 shows Enron’s stock price between December 5, 2000 and December 7, 2001. The arrows on each plot  indicate the dates of important corporate events. Enron filed for bankruptcy on December 2 2001.
# Asset swap spread:

Market practitioners relate the cost of credit protection to the spread between corporate  yields and swap yields. The credit default swap premium is related to the asset swap  spreads, and the difference between the CDS premium and the asset swap spread is  referred to as the basis 16 .

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f2651a6473be5d8effed88f91a689efbae66d4eec4b03ce055c6c5d039ba435d.jpg)
Figure 4.5   Historical mid Asset swap spread vs CDS spread  (2003-2005) Source: Bloomberg LP. July 2005

Using Bloomberg data for a single reference entity 5 year credit default swap premium,  and a mid asset swap spread from the reference obligation of the credit default swap  contract, figure 4.5 show significant difference in basis point. This result is also  consistent with the result reported by Longstaff. F.A., Mithal S. and Neis E. (2003).

Longstaff. F.A., Mithal S. and Neis E. (2003) used the swap curve as a benchmark curve  to determine the discount function. From their result, the use of the swap curve in  estimating the discount function could not account for the large cross-sectional  differences across firms. However, the average differences between implied and market  premia across all firms was only 3.9 basis point according to the authors.

# Default risk from counter party:

Another reason that could explain why the market observed CDS premia are lower than  the implied CDS is that the firm selling credit protection might enter financial distress  itself.  The price of the premium from the buyers point of view should not be worth as  much if there is a default correlation between the protection seller and the reference  entity.
There are several other factors that may contribute to the differences between model  implied CDS premiums and market quoted CDS premiums. Factors such as the cost of  shorting corporate bonds could be considered. It is however beyond the scope of this  paper to examine all of these factors. It is possible that further improvements of the  implemented models or alternative models in the future as a result of further research  may reduce the CDS premium variations observed in most empirical work.

# 6.1  Kettunen, K send zo v sky, and Meissner (KKM) model (2003)

In this section, we use an alternative model to price CDS using KKM model 17 . Kettunen,  K send zo v sky, and Meissner derive the default swap premium with a combination of two  easily implementable discrete binomial trees. One tree represents the default swap  premium, and the other the default swap payoff incase of default.

# 1. KKM model excluding counter party default risk

Notations:

λ :   risk-neutral probability of default of reference entity  $r$   during  $(t,\,t{+}I)$     $\boldsymbol{s}_{t}:$    default swap premium to be paid at time   $t$     $N\colon$     notional

  $\tau_{t}$  :   time between 0 and time  $t$  ,  expressed in years

  $\Delta\boldsymbol{\tau}_{t}$  :  time between  $t$   and  $_{t+I}$  ,  expressed in years   $R R$    recovery rate   $a$     accrued interest from last coupon date until the default date    $r$  :   the risk-free rate for the period   $(O,\,t{+}I)$

We use a simple binomial tree where the premium is paid at the end of default period,  where  $t$    represents the CDS payment dates.

Figure 6.1 Discrete time binomial model

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2eac892c914ca188a9340d5e27709de2a640bc0276a8c8ea4a32a7805541d8f0.jpg)
The present value of the default swap premium payments from figure 6.1 is given by:

$$
\Big[\lambda_{0}^{r}s_{1}N+\big(1-\lambda_{0}^{r}\big)s_{1}N\Big]e^{-r_{0}\tau_{1}}+\Big\{\!\big(1-\lambda_{0}^{r}\big)\!\Big[\lambda_{1}^{r}s_{2}N+\big(1-\lambda_{1}^{r}\big)\!s_{2}N\Big]\!\Big\}e^{-r_{0}\tau_{1}}
$$

Cancelling several terms in (49) and generalizing for   $T$    period, the present value of the  default swap premium is given by:

$$
s_{1}N e^{-r_{0}\tau_{1}}+\sum_{t=2}^{T}\Biggl[s_{1}N e^{-r_{t}-\tau_{1}}\prod_{u=0}^{t-2}(1-\lambda_{u}^{r}\,)\Biggr].
$$

The above tree can be extended to more default period and the pricing formula will  become more complicated. For example using 4 period tree, the present value of the swap  premium can be written as:

$$
\begin{array}{r l}&{\Big[\lambda_{0}^{r}s_{1}N\Delta\tau_{0}+\big(1-\lambda_{0}^{r}\big)s_{1}N\Delta\tau_{0}\Big]e^{-r_{0}\tau_{1}}}\\ &{+\left\{\!\!\big(1-\lambda_{0}^{r}\big)\!\!\left[\lambda_{1}^{r}s_{1}N\Delta\tau_{1}+\big(1-\lambda_{1}^{r}\big)s_{1}N\Delta\tau_{1}\right]\!\right\}\!\!e^{-r_{1}\tau_{2}}}\\ &{+\left\{\!\!\big(1-\lambda_{0}^{r}\big)\!\!\left(1-\lambda_{1}\big)\!\!\left[\lambda_{2}^{r}s_{2}N\Delta\tau_{2}+\big(1-\lambda_{2}^{r}\big)s_{2}N\Delta\tau_{2}\right]\!\right\}\!\!e^{-r_{2}\tau_{3}}}\\ &{+\left\{\!\!\big(1-\lambda_{0}^{r}\big)\!\!\left(1-\lambda_{1}\big)\!\!\left(1-\lambda_{2}\big)\!\!\left[\lambda_{3}^{r}s_{2}N\Delta\tau_{3}+\big(1-\lambda_{3}^{r}\big)s_{2}N\Delta\tau_{3}\right]\!\right\}\!\!e^{-r_{3}\tau_{4}}}\end{array}
$$

Setting the swap premium   $s$    constant in time, i.e.   $s_{1}=s_{2}=s_{3}$  ....,  and canceling several  terms in (51), we get for time  $T$    periods:

$$
s_{1}N\Delta\tau_{0}e^{-r_{0}\tau_{1}}+\sum_{t=2}^{T}\Biggl[s_{1}N\Delta\tau_{t-1}e^{-r_{t}-\tau_{1}}\prod_{u=0}^{t-2}(1-\lambda_{u}^{r})\Biggr].
$$

Incorporating the payoff from the default swap seller to the protection buyer in event of  default as usual, this is defined again as:   $N(1\!-\!R R\!-\!R R a)$  where all the parameters are as  specified above. The present value of the expected payoff is given  by:

$$
\begin{array}{r l}&{\lambda_{0}N(1-R R-R R a)e^{-r_{0}\tau_{1}}+(1-\lambda_{0})\lambda_{1}N(1-R R-R R a)e^{-n\tau_{2}}}\\ &{+\,(1-\lambda_{0})(1-\lambda_{1})\lambda_{2}N(1-R R-R R a)e^{-n\tau_{3}}\cdots}\end{array}
$$

Generalizing (53), we get the present value of the expected payoff:

$$
\lambda_{0}N(1-R R-R R a)e^{-r_{0}\tau_{1}}+\sum_{t=2}^{T}\left[N(1-R R-R R a)\lambda_{t-1}e^{-r_{t-1}\tau_{1}}\prod_{u=0}^{t-2}(1-\lambda_{u}^{r})\right]\!.
$$

Combining equation (52), (53), and (54), the present value of the default swap from the  buyers viewpoint is derived:
$$
\begin{array}{l l}{{}}&{{\lambda_{0}N(1-R R-R R a)e^{-r_{0}\tau_{1}}+\displaystyle\sum_{t=2}^{T}\Biggl[N(1-R R-R R a)\lambda_{t-1}e^{-r_{t-1}\tau_{1}}\prod_{u=0}^{t-2}(1-\lambda_{u}^{r})\Biggr]}}\\ {{}}&{{-\,s N\Delta\tau_{0}e^{-r_{0}\tau_{1}}+\displaystyle\sum_{t=2}^{T}\Biggl[s_{1}N\Delta\tau_{t-1}e^{-r_{t}-\tau_{1}}\prod_{u=0}^{t-2}(1-\lambda_{u}^{r})\Biggr].}}\end{array}
$$

Setting (55) to zero and solving for  $s$    (credit default swap premium), we get:

$$
s=\frac{\lambda_{0}N(1-R R-R R a)e^{-r_{0}\tau_{1}}+\displaystyle\sum_{t=2}^{T}\left[N(1-R R-R R a)\lambda_{t-1}e^{-r_{t-1}\tau_{1}}\displaystyle\prod_{u=0}^{t-2}(1-\lambda_{u}^{r})\right]}{N\Delta\tau_{0}e^{-r_{0}\tau_{1}}+\displaystyle\sum_{t=2}^{T}\left[s_{1}N\Delta\tau_{t-1}e^{-r_{t}-\tau_{1}}\displaystyle\prod_{u=0}^{t-2}(1-\lambda_{u}^{r})\right]}.
$$

As before,   $s$    represents the fair or the mid market default swap premium implied from the  above model since it gives the swap a zero value at the interception of the contract. In  other words, this is neither in-the-money nor out-of-the money from both seller and  buyers viewpoint.

We apply the above equation to compute the default swap premium using the following  data: Given a notional value of  $\S~1{,}000{,}000$  , recovery rate of   $40\%$   and CDS contract with  maturity of 1 year with annual payment. Default probability of   $10\%$   and 30 percent for  period one and two. Accrued interest of   $1\%$   and   $4\%$   for both periods respectively. we  plug these data into formula (56) using excel. The computed CDS premium is   $22.67\%$  .  Appendix B shows a print out of the result from excel spreadsheet.

# 7.1    Structural versus Reduced-form models

Jarrow and Protter (2004) compared structural versus reduced form credit risk models  from an information based perspective. According to the authors, difference between  these two model types can be characterized in terms of the information assumed known  by the modeler. Structural models assume that the modeler has the same information set  as the firm’s manager—complete knowledge of all the firm’s assets and liabilities. In  most situations, this knowledge leads to a predictable default time. In contrast, reduced  form models assume that the modeler has the same information set as the market— incomplete knowledge of the firm’s condition. In most cases, this imperfect knowledge  leads to an inaccessible default time. Jarrow and Potter argue that the key distinction  between structural and reduced form models is not whether the default time is predictable  or inaccessible, but whether the information set is observed by the market or not.

If one is interested in pricing a firm’s risky debt or related credit derivatives, then reduced  form models are the preferred approach. There is consensus in the credit risk literature  that the market does  not  observe the firm’s asset value continuously in time. This implies,  that the simple form of structural models illustrated above does not apply. In contrast,  reduced form models have been constructed, purposefully, to be based on the information  available to the market.
# 8 .1  Conclusion

This paper introduces the existing credit risk models and their applications to price the  premiums in credit default swaps (CDS) contract. Both structural and reduced-form  models such as Merton’s model and extensions as well as intensity based models are  introduced. we examined the difference between model generated CDS prices using both  Merton’s model and intensity based model such as the model proposed by Duffie and  Singleton. according to Longstaff. F.A., Mithal S. and Neis E. (2003) , there is a clear  evidence that the implied cost of credit protection is significantly higher in the corporate   bond market for all the firms they used in their sample.  Possible explanations for the  higher cost of credit protection implied by corporate bonds could be due to number of  factors including tax issues, liquidity issues, asset pricing, the cost of shorting corporate  bonds, or model error due to missing out relevant data.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c9640afa76b23071253719893c467a2e82305ad9467948bdaf0ef9abca234c96.jpg)
The result on the spreads are generated using VBA code which we omit from this text due to the length of  the code.

# Appendix B

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/52f812265849754590cfff5d1d2108a033592b108c20681acfde5d48de8cf128.jpg)
Appendix C 18

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/82f0a3b63f0f9ba6c7495af6bc747176da14ab6afe3b4da924b31081bcaf20a3.jpg)
Banks AAA - Default Probability from recovery of  $0\%-.9\%$

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9c83210fd5b0e498172a66ea3e169a77303559ef4154f251f429c3420c7eb25d.jpg)
# References

Ali, A., (2004)  “Credit Risk Modelling: An introduction to credit risk modeling.” Risk  International. Published by Risk magazine.

Ali, A., and  M. Choudhry (2003)  “Join the game.” GARP Risk Review. May/June 2003,  issue 12.

Black, F., and J. C. Cox, 1976 “Valuing Corporate Securities: Some Effects of Bond  Indenture Provisions,” Journal of Finance 31, 351-367.

Bielecki, T.R., and Rutkowski, M., 2002, “Credit Risk: Modeling, Valuation and  Hedging, “ Springer Finance.

Black, F., and Scholes, M., 1973, “The Pricing of Options and Corporate Liabilities,”  Journal of Political Economy 81, 637-654.

Briys, E., and de Varenne, F., 1997, “Valuing Risky Fixed Rate Debt: An Extension,”  Journal of Financial and Quantitative Analysis 31, 239-248.

Cox, J.C., Ingersoll, J. E., and Ross, S. A.. (1985) “A theory of the term structure of  interest rates.” Econometric a 53.

Duffie, D., (1998a) “Default able term structure models with fractional recovery of par.”  Working paper.

Duffie, D., (1999) “Credit Swap Valuation.” Financial Analyst Journal.

Duffie, D., and K. Singleton (1999) “Modeling term structure of default able bonds.”  Review of financial studies12.

Ericsson, J, Reneby, J and Wang, H.,  (2005) , “Can structural models price default risk?  Evidence from bond and credit derivative markets”.

Geske, R., 1977, “The Valuation of Corporate Liabilities as Compound Options,” Journal  of Financial and Quantitative Analysis 12, 541-552.

Geske, R., 1979, “The Valuation of Compound Options,” Journal of Financial Economics  7, 63-81. 22

Hull, J., and A. White (2000) “Valuing Credit Default Swaps I: No Counter party Default  Risk“,  The Journal of Derivatives .

Hull, J., and A. White (2001) “Valuing Credit Default Swaps II: Modeling default  correlation,“  The Journal of Derivatives .
Hull, J., Nelken, I., and White, A.,  2004,  “Merton’s Model, Credit Risk, and Volatility  Skews,” Journal of Credit Risk,.

Jarrow, R., D. Lando and S. M. Turnbull (1997) “A Markov model for the term structure  of credit risk spreads.” Journal of finance 50.

Jarrow, R., and S. M. Turnbull (1995) “Pricing derivatives on financial securities subject  to credit risk .” Review of financial studies 10.

Jarrow, R., and P. Protter (2004) “Structural versus reduced form models: A new  information based perspective,“  The Journal of Investment Management. Vol,2.  .

Jones, E.P.,  S.P. Mason, and E. Rosenfeld, 1984, “Contingent claim analysis of corporate  capital structures: An empirical investigation”  Journal of Finance 39, 611-625.

Kim, J., K. Ramaswamy, and S. Sundersan, 1993, “The valuation of corporate fixed  income securities”,  Financial Management, 117-131.

Lando, D., (1998a) “On Cox processes and credit-risky securities.” Review of derivative  research 2.

Longstaff, F. A., and Schwartz, E. S., 1995, “A Simple Approach to Valuing Risky  Fixed and Floating Rate Debt,” Journal of Finance 50, 789-819.

Longstaff. F.A., Mithal S. and Neis E. (2003) “Is credit protection priced correctly”   working paper

Madan, D., and H. Unal  (1998) “Pricing of risks of default.” Review of derivatives  research.

Merton, R., 1974, “On the Pricing of Corporate Debt: the Risk Structure of Interest  Rates,” Journal of Finance 29, 449-470.

Ronn, E. I., and Verma, A. K., 1986, “Pricing Risk-Adjusted Deposit Insurance: An  Option Based Model,” Journal of Finance 41, 871-895.

Saá-Requejo, J., and Santa-Clara, P., 1997, “Bond Pricing with Default Risk,”Working  Paper, UCLA.

Sch nb uc her, P. J., 2003, “Credit Derivatives Pricing Models,” Wiley Finance.

Sch on bu cher, P., (2003a) “Credit derivative pricing models.” J. Wiley, Chichester.

Sch on bu cher, P., (2003b) “ A note on survival measures and the pricing of options on  credit default swaps.”  Working paper.
