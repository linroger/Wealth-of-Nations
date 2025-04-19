---
title: Risk Neutral Valuation Framework for Credit Default Swaps
tags:
  - cds_valuation
  - credit_default_swaps
  - credit_risk
  - hazard_rates
  - risk_neutral_valuation
aliases:
  - CDS
  - Credit Derivatives
  - Risk Neutrality
key_concepts:
  - CDS cash flows
  - CDS duration
  - Deterministic interest rates
  - Hazard rates
  - Risk neutral valuation
---

# [[Financial Instruments/Financial Derivatives and Quantitative Methods/Credit Default Swaps|Risk Neutral Valuation Framework for Credit Default Swaps]]

## OVERVIEW

This set of lecture notes provides a thorough explanation of the risk neutral valuation framework for pricing and analyzing Credit Default Swaps (CDS). The key components covered include:

1. Risk neutral valuation principles
1. Simple case of deterministic interest rates
1. CDS premium/fixed leg cash flows
1. CDS default/loss leg cash flows
1. Valuation of CDS using hazard rates
1. Properties of hazard rates
1. Numerical quadrature for CDS valuation
1. CDS duration,  ParSpread,  and valuation formulas

## RISK NEUTRAL VALUATION PRINCIPLES

The risk neutral valuation framework is based on the following principles:

1. Each instrument is uniquely defined by its cumulative future cash flows: $CF(t),         \quad t \geq 0 \quad (1)$
1. Risk neutral valuation uses a "market implied" probability measure $\mathbb{P}$ for determining prices of securities.
1. A bank savings account security $B$ is used as a numeraire for discounting future cash flows: $$B(t) = e^{\int_0^t r_s ds},         \quad t \geq 0$$
1. The present value is obtained as: $$PV(t) = B(t) \cdot \mathbb{E}\left[\int_t^{\infty} B(s)^{-1} \cdot dCF(s) | \mathcal{F}_t\right] \quad (2)$$

## SIMPLE CASE: DETERMINISTIC INTEREST RATES

For the simple case of deterministic interest rates:

1. The "time value of money" at time $t$ for time $s$ is captured in the calibrated discount factor curve: $$DF(t,         s) = B(t) \cdot \mathbb{E}\left[B(s)^{-1}|\mathcal{F}_t\right] = e^{-\int_t^s r_u du},         \quad 0 \leq t \leq s \quad (3)$$
1. The risk free valuation formula simplifies to: $PV(t) = \mathbb{E}\left[\int_t^{\infty} DF(t,         s) \cdot dCF(s) | \mathcal{F}_t\right] \quad (4)$
1. The same formula holds when security cash flows and interest rates are independent.

## CDS PREMIUM/FIXED LEG CASH FLOWS

For CDS premium/fixed leg cash flows:

1. Quarterly coupon payments until maturity $$T = T_n$: ${c_i,         T_i}_{i=1…n},         \quad 0 \leq t < T_1 < … < T_n \tag{5}$$
1. We denote the random/stochastic issuer default time by: $\tau \in [0,         \infty)$
1. Cumulative Premium Leg cash flows have stochastic dependence on $\tau$: $$PL(s):= \sum_{i=1}^n c_i \cdot \mathbf{1}_{{s \geq T_i}} \cdot \mathbf{1}_{{\tau > T_i}} \tag{6}$$

## VALUATION FRAMEWORK FOR CREDIT-RISKY CASH FLOWS

The valuation framework for credit-risky cash flows assumes:

1. $DF(t,         s)$ is the deterministic risk-free discount factor (as of time $t$,  for time $s$).
1. The $DF(t,         \cdot)$ curve can be calibrated from market quotes via bootstrapping.
1. $\tau \in [0,         \infty)$ is the random/stochastic issuer default time.
1. Market implied issuer survival & default probabilities: $$SP(t,         s):= \mathbb{P}(\tau > s | \tau > t),         \quad 0 \leq t \leq s,         \quad (7)$$ $$DP(t,         s):= \mathbb{P}(\tau \leq s | \tau > t) = 1 - SP(t,         s). \quad (8)$$

## CDS DEFAULT/LOSS LEG CASH FLOWS

For CDS default/loss leg cash flows:

1. Recovery Rate given default is denoted by $R$.
1. For simplicity ("basic model"),  we assume $R$ is constant.
1. $R$ can be thought of as the expected (average) recovery rate for a given issuer and seniority rank.
1. Default Leg cash flows until time $s$ are given by:
   $$DL(s):= (1 - R) \cdot \mathbf{1}_{\{\tau \leq s\}} \tag{15}$$

## VALUATION OF CDS DEFAULT/LOSS LEG (USING FUBINI)

The present value of the CDS default/loss leg is:
$$PV_{CDS_DL}(t) = \mathbb{E}\left[\int_t^T DF(t,        s) \cdot dDL(s) | \tau > t\right] \tag{16}$$

$$= \mathbb{E}\left[\int_t^T (1 - R) \cdot DF(t,        s) \cdot d\mathbf{1}_{\{\tau \leq s\}} | \tau > t\right] \tag{17}$$

$$= \int_t^T (1 - R) \cdot DF(t,        s) \cdot d\mathbb{E}\left[\mathbf{1}_{\{\tau \leq s\}} | \tau > t\right] \tag{18}$$

$$= (1 - R) \cdot \int_t^T DF(t,        s) \cdot d\mathbb{P}(\tau \leq s | \tau > t) \tag{19}$$

$$= (1 - R) \cdot \int_t^T DF(t,        s) \cdot dDP(t,        s). \tag{20}$$

The intuitive interpretation is that the default leg present value at the (random) issuer default time is:
$$ PV_{CDS_DL}(t) = \int_t^T (1 - R) \cdot DF(t,        s) \cdot dDP(t,        s) \tag{21} $$

This is obtained by:

1. Splitting the time until maturity $[t,        T]$ into infinitesimal (one day) intervals and summing up the loss amount on each interval: $1 - R$.
1. Multiplying with the discount factor for that interval: $DF(t,        s)$.
1. Multiplying with the incremental probability of default on that interval: $dDP(t,        s)$.

## HAZARD RATES (A.K.A. DEFAULT INTENSITIES)

Hazard rates $h(t,        s)$ represent infinitesimal probabilities of default at future time $s$,  using market information as of time $t$.

1. Similar concept to forward interest rates.
1. Hazard rate curves $h(t,        \cdot)$ defined implicitly from Survival Probability curves:
   $$SP(t,        s) = \exp\left[-\int_t^s h(t,        u) du\right],        \quad 0 \leq t \leq s. \tag{24}$$
1. Or defined explicitly as:
   $$h(t,        s) = -\frac{\partial}{\partial s} \ln[SP(t,        s)] = -\frac{1}{SP(t,        s)} \cdot \frac{\partial SP}{\partial s}(t,        s). \tag{25}$$

## PROPERTIES OF HAZARD RATES

Hazard rates $h(t,        s)$ quantify conditional probabilities of default "around" specific times $s$ in the future:
$$\mathbb{P}(s < \tau \leq s + \varepsilon | \tau > s,        \tau > t) \tag{26}$$

$$= \frac{\mathbb{P}(s < \tau \leq s + \varepsilon | \tau > t)}{\mathbb{P}(\tau > s | \tau > t)}$$

$$= \frac{SP(t,        s) - SP(t,        s + \varepsilon)}{SP(t,        s)}$$

$$= 1 - \exp\left[-\int_s^{s+\varepsilon} h(t,        u) du\right]$$

$$\simeq h(t,        s) \cdot \varepsilon,        \quad 0 \leq t \leq s.$$

## VALUATION OF CDS DEFAULT/LOSS LEG USING HAZARD RATES

$$PV_{CDS_DL}(t) = (1 - R) \cdot \int_t^T DF(t,        s) \cdot dDP(t,        s) \tag{27}$$

$$= (1 - R) \cdot \int_t^T DF(t,        s) \cdot d[1 - SP(t,        s)] \tag{28}$$

$$= - (1 - R) \cdot \int_t^T DF(t,        s) \cdot dSP(t,        s) \tag{29}$$

$$= (1 - R) \cdot \int_t^T h(t,        s) \cdot DF(t,        s) \cdot SP(t,        s) \cdot ds. \tag{30}$$

## NUMERICAL QUADRATURE OF CDS DEFAULT/LOSS LEG

$$PV_{CDS_DL}(t) = (1 - R) \cdot \int_t^T h(t,        s) \cdot DF(t,        s) \cdot SP(t,        s) \cdot ds$$

$$= \sum_{i=1}^n (1 - R) \cdot \int_{T_{i-1}}^{T_i} h(t,        s) \cdot DF(t,        s) \cdot SP(t,        s) \cdot ds \tag{31}$$

$$\simeq \sum_{i=1}^n (1 - R) \cdot h(t,        T_i) \cdot \Delta T_i \cdot DF(t,        T_i) \cdot SP(t,        T_i). \tag{32}$$

## CDS VALUATION (RECEIVING PREMIUM $C$,  PAYING DEFAULT/LOSS LEG)

$$PV_{CDS}(t) = PV_{CDS_PL}(t) - PV_{CDS_DL}(t) \tag{33}$$

$$= \sum_{i=1}^n c \cdot DF(t,        T_i) \cdot SP(t,        T_i)$$

$$- (1 - R) \cdot \int_t^T h(t,        s) \cdot DF(t,        s) \cdot SP(t,        s) \cdot ds$$

$$= \sum_{i=1}^n [c - (1 - R) \cdot h(t,        T_i)] \cdot \Delta T_i \cdot DF(t,        T_i) \cdot SP(t,        T_i). \tag{34}$$

## CDS DURATION AND PARSPREAD

1. CDS Duration defined as the "Unit" 1bp Premium Leg PV: $$Duration(t):= \sum_{i=1}^n \Delta T_i \cdot DF(t,        T_i) \cdot SP(t,        T_i) \tag{35}$$
1. CDS Premium Leg valuation via Duration: $$PV_{CDS_PL}(t) = c \cdot Duration(t) \tag{36}$$
1. ParSpread defined from CDS Default Leg and Duration:$$PV_{CDS_DL}(t) = ParSpread(t) \cdot Duration(t) \tag{37}$$
1. CDS valuation:$$PV_{CDS}(t) = [c - ParSpread(t)] \cdot Duration(t) \tag{38}$$

## CDS DURATION AND PARSPREAD FORMULAS

1. CDS trades "At Par" when ParSpread matches the coupon:
   $$PV_{CDS}(t) = 0 \Leftrightarrow ParSpread(t) = c \tag{39}$$

1. CDS ParSpread measures the credit risk of the CDS contract:
   $$ParSpread(t) \cong (1 - R) \cdot h \tag{40}$$

1. CDS CS01 defined as $\Delta PV$ for -1bp change in ParSpread:
   $$CS01_{CDS}(t,        s):= PV_{CDS}(t,        s - 1bp) - PV_{CDS}(t,        s) \tag{41}$$
   $$\cong [c - s + 1bp] \cdot Duration(t) - [c - s] \cdot Duration(t) = Duration(t)$$

1. Cumulative Future Cash Flows:
   $$CF(t),        \quad t \geq 0 \tag{1}$$
   This formula represents the cumulative future cash flows of an instrument over time. It captures all the cash inflows and outflows associated with the instrument from the current time $t$ onwards.

1. Present Value:
   $$PV(t) = B(t) \cdot \mathbb{E}\left[\int_t^{\infty} B(s)^{-1} \cdot dCF(s) | \mathcal{F}_t\right] \tag{2}$$
   The present value formula calculates the value of an instrument at time $t$ by discounting the expected future cash flows. It multiplies the bank savings account value $B(t)$ at time $t$ with the expected value of the integral of discounted future cash flows. The discount factor $B(s)^{-1}$ adjusts the future cash flows to their present value at time $t$. The expectation is taken under the risk-neutral probability measure $\mathbb{P}$ and is conditional on the information available at time $t$,  denoted by $\mathcal{F}_t$.

1. Deterministic Discount Factor:
   $$DF(t,        s) = B(t) \cdot \mathbb{E}\left[B(s)^{-1}|\mathcal{F}_t\right] = e^{-\int_t^s r_u du},        \quad 0 \leq t \leq s \tag{3}$$
   In the case of deterministic interest rates,  the discount factor $DF(t,        s)$ represents the present value at time $t$ of a unit cash flow received at a future time $s$. It is calculated by multiplying the bank account value $B(t)$ at time $t$ with the expected value of the inverse of the bank account value at time $s$,  conditional on the information available at time $t$. The formula simplifies to an exponential term involving the integral of the deterministic interest rate $r_u$ from time $t$ to $s$.

1. Simplified Present Value (Deterministic Interest Rates):
   $$PV(t) = \mathbb{E}\left[\int_t^{\infty} DF(t,        s) \cdot dCF(s) | \mathcal{F}_t\right] \tag{4}$$
   When interest rates are deterministic,  the present value formula simplifies. It becomes the expected value of the integral of the product of the deterministic discount factor $DF(t,        s)$ and the incremental cash flows $dCF(s)$ from time $t$ to infinity. The expectation is taken under the risk-neutral probability measure and is conditional on the information available at time $t$.

1. CDS Premium Leg Cash Flows:
   $$PL(s):= \sum_{i=1}^n c_i \cdot \mathbf{1}_{\{s \geq T_i\}} \cdot \mathbf{1}_{\{\tau > T_i\}} \tag{6}$$
   This formula represents the cumulative cash flows of the premium leg of a CDS contract up to time $s$. It is a sum of the product of the coupon payments $c_i$ and two indicator functions. The first indicator function $\mathbf{1}_{\{s \geq T_i\}}$ ensures that the coupon payment is included only if time $s$ is greater than or equal to the payment date $T_i$. The second indicator function $\mathbf{1}_{\{\tau > T_i\}}$ ensures that the coupon payment is made only if the issuer has not defaulted by time $T_i$. The variable $\tau$ represents the random default time of the issuer.

1. Issuer Survival Probability:
   $$SP(t,        s):= \mathbb{P}(\tau > s | \tau > t),        \quad 0 \leq t \leq s,        \tag{7}$$
   The issuer survival probability $SP(t,        s)$ represents the probability that the issuer survives beyond time $s$,  given that the issuer has survived up to time $t$. It is calculated as the conditional probability of the issuer's default time $\tau$ being greater than $s$,  given that it is already greater than $t$.

1. Issuer Default Probability:
	$$DP(t,        s):= \mathbb{P}(\tau \leq s | \tau > t) = 1 - SP(t,        s). \tag{8}$$
	The issuer default probability $DP(t,        s)$ represents the probability that the issuer defaults by time $s$,  given that the issuer has survived up to time $t$. It is calculated as the complement of the issuer survival probability $SP(t,        s)$.

1. Default Leg Cash Flows:
	$$DL(s):= (1 - R) \cdot \mathbf{1}_{\{\tau \leq s\}} \tag{15}$$
	The default leg cash flows $DL(s)$ represent the payment made by the protection seller to the protection buyer in the event of the issuer's default. It is calculated as the product of the loss given default $(1 - R)$,  where $R$ is the recovery rate,  and an indicator function $\mathbf{1}_{\{\tau \leq s\}}$ that equals 1 if the issuer defaults by time $s$ and 0 otherwise.

1. Present Value of Default Leg (using Fubini's theorem):
	$$PV_{CDS_DL}(t) = (1 - R) \cdot \int_t^T DF(t,        s) \cdot dDP(t,        s). \tag{20}$$
	The present value of the default leg $PV_{CDS_DL}(t)$ is calculated by integrating the product of the loss given default $(1 - R)$,  the deterministic discount factor $DF(t,        s)$,  and the incremental default probability $dDP(t,        s)$ from time $t$ to the maturity time $T$. This formula is derived using Fubini's theorem,  which allows for the interchange of the order of integration and expectation.

1. Hazard Rates:
	$$SP(t,        s) = \exp\left[-\int_t^s h(t,        u) du\right],        \quad 0 \leq t \leq s. \tag{24}$$
	Hazard rates $h(t,        s)$ represent the instantaneous probability of default at a future time $s$,  given the information available at time $t$. The survival probability $SP(t,        s)$ is expressed in terms of the hazard rates using the exponential function. The negative integral of the hazard rates from time $t$ to $s$ gives the cumulative hazard,  and the exponential of the negative cumulative hazard yields the survival probability.

1. Present Value of Default Leg (using Hazard Rates):
	$$PV_{CDS_DL}(t) = (1 - R) \cdot \int_t^T h(t,        s) \cdot DF(t,        s) \cdot SP(t,        s) \cdot ds. \tag{30}$$
	This formula calculates the present value of the default leg using hazard rates. It integrates the product of the loss given default $(1 - R)$,  the hazard rate $h(t,        s)$,  the deterministic discount factor $DF(t,        s)$,  and the survival probability $SP(t,        s)$ from time $t$ to the maturity time $T$. The hazard rate represents the instantaneous probability of default,  the discount factor adjusts for the time value of money,  and the survival probability accounts for the probability of the issuer surviving up to each point in time.

1. CDS Valuation:
	$$PV_{CDS}(t) = PV_{CDS_PL}(t) - PV_{CDS_DL}(t) \tag{33}$$
	The value of a CDS contract $PV_{CDS}(t)$ is determined by the difference between the present value of the premium leg $PV_{CDS_PL}(t)$ and the present value of the default leg $PV_{CDS_DL}(t)$. The premium leg represents the payments made by the protection buyer to the protection seller,  while the default leg represents the potential payment made by the protection seller to the protection buyer in the event of the issuer's default.

1. CDS Duration:
	$$Duration(t):= \sum_{i=1}^n \Delta T_i \cdot DF(t,        T_i) \cdot SP(t,        T_i) \tag{35}$$
	CDS duration is defined as the present value of a stream of unit premium payments. It is calculated by summing the product of the time interval $\Delta T_i$,  the deterministic discount factor $DF(t,        T_i)$,  and the survival probability $SP(t,        T_i)$ for each premium payment date $T_i$ from time $t$ to the maturity of the CDS contract.

1. CDS ParSpread:
	$$PV_{CDS_DL}(t) = ParSpread(t) \cdot Duration(t) \tag{37}$$
	The CDS ParSpread is the premium rate that equates the present value of the default leg to the present value of the premium leg. It represents the fair premium rate that the protection buyer should pay to the protection seller for the credit protection. The ParSpread is calculated by dividing the present value of the default leg $PV_{CDS_DL}(t)$ by the CDS duration $Duration(t)$.

1. CDS CS01:
	$$CS01_{CDS}(t,        s):= PV_{CDS}(t,        s - 1bp) - PV_{CDS}(t,        s) \tag{41}$$
	CDS CS01 (Credit Spread 01) measures the sensitivity of the CDS contract's value to a one basis point (1bp) change in the CDS ParSpread. It is calculated as the difference between the CDS value $PV_{CDS}(t,        s - 1bp)$ when the ParSpread is reduced by 1bp and the CDS value $PV_{CDS}(t,        s)$ at the current ParSpread $s$. CS01 provides an indication of the CDS contract's sensitivity to changes in the credit spread.