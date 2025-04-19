---
tags:
  - expectations_hypothesis
  - interest_rate
  - segmented_markets
  - term_premium
  - term_structure
aliases:
  - LPH
  - MSH
  - RMEH
  - SMH
  - TPH
  - YMEH
key_concepts:
  - liquidity premium
  - money substitute
  - return to maturity
  - term premium
  - term structure hypotheses
---

# 25.4 OTHER TERM STRUCTURE OF INTEREST RATE HYPOTHESES

In this section, we review several term structure of interest rate hypotheses, excluding UEH and LEH because they have been covered already. We also provide several foundational research papers on which these hypotheses were created and evaluated..

# 25.4.1 Return to Maturity Expectations Hypothesis (RMEH)

The RMEH states that the holding period return from buying a long-term bond and hold-. ing it until maturity is equal to the expected return from buying one-period bonds and

rolling them into the next one-period bond for the same time period as the long-term bond. Based on our notation, we have.

$$
\mathrm{RMEH:}~r(t,t+j)=\sum_{i=1}^{j}E_{t}[r(t+i-1,t+i)];j=1,\ldots,n.
$$

See Cox, Ingersoll, and Ross (1981, 1985a, b). One variation of RMEH is the yield to maturity expectations hypothesis (YMEH). The YMEH states that the yield to maturity. from buying a long-term bond and holding it until maturity is equal to the expected return. from buying one-period bonds and rolling them into the next one-period bond for the. same time period as the long-term bond. Note this hypothesis is just a restatement of the RMEH. See Cox, Ingersoll, and Ross (1981, 1985a, b).

# 25.4.2Term Premium Hypothesis (TPH)

The TPH states that forward rates are biased predictors of future spot rates. Specifically,. forward rates are biased by a known amount defined as a term premium (tp). The term premium might be positive or negative, might vary widely with maturity, and might vary across time. The word term is generic and might indicate a wide variety of ssues depending. on context. The word term, however, is always indicative of time to maturity. Thus, this generic TPH encapsulates all the premium hypotheses stated here. Based on our notation, we have

$$
\mathrm{TPH:}~f(t,t+j)=E_{t}[r(t+j,t+j+1)]+t p(t,t+j);j=1,\ldots,n.
$$

See Kane (1980). The liquidity premium hypothesis (LPH) is a variation of the TPH. The LPH states that forward rates are biased predictors of future spot rates and are biased high by a known amount defined as a liquidity premium $(l p)$ . The idea is that investors deem shorter maturity bonds as being more liquid; hence, they demand a higher yield for longer maturity bonds. From this perspective, the liquidity premium must be positive and must be nondecreasing with long maturities. It might vary across time. Based on our notation, we have

$$
\mathrm{LPH}\colon f(t,t+j)=E_{t}[r(t+j,t+j+1)]+l p(t,t+j);j=1,\ldots,n.
$$

See Hicks (1946) and Kane (1980).

# 25.4.3 Money Substitute Hypothesis (MSH)

The MsH states that forward rates are biased predictors of future spot rates by a known amount defined as a money premium $(m p)$ . The money premium is based solely on the very short-term bonds acting as a pure substitute for money; hence, demand is high and yields and holding period returns are low. The money premium must be positive and must be nondecreasing with long maturities. It might vary across time. Based on our notation, we have

$$
\mathrm{MSH}\colon\boldsymbol{f}(t,t+j)=E_{t}[r(t+j,t+j+1)]+m p(t,t+j);j=1,\ldots,n.
$$

See Thornton (1802), Mill (1923), Keynes (1935), Timberlake (1964), and Kessel (1965).

# 25.4.4Segmented Markets Hypothesis (SMH)

The SMH states that forward rates are biased predictors of future spot rates based on maturity sectors representing distinct markets with their own supply and demand forces. These forces result in known allowance amounts and are defined here as a segment premium $(s p)$ The SMH requires knowledge of where these maturity segments are located before being able to assign the appropriate segment premiums. The segment premium might be positive or negative, might vary widely across maturities, and might vary across time. Based on our notation, we have

$$
\mathrm{SMH}\colon\boldsymbol{f}(t,t+j)=E_{t}[r(t+j,t+j+1)]+s\boldsymbol{p}(t,t+j);j=1,\ldots,n.
$$

See Culbertson (1957) and Sundaresan (2002). Sundaresan suggests SMH driven by regulatory constraints.

The preferred habitat hypothesis (PHH) is a variation of the MSH. The core idea is that investors have preferred maturities of bonds they trade. For example, insurance companies might prefer very long-dated bonds whereas banks prefer bonds with less than a few years to maturity. These maturity ranges are their preferred habitats. For a sufficient yield differential these preferences might be overcome. The PHH states that forward rates are biased predictors of future spot rates. Specifically, forward rates are biased based on habitat displacement allowances. This known allowance amount is defined as a habitat premium $(b p)$ . The PHH requires knowledge of borrower and lender habitats before being. able to assign the appropriate habitat premiums. The habitat premium might be positive or negative, might vary widely across maturities, and might vary across time. Based on our notation, we have

$$
\mathrm{PHH}\colon\:f(t,t+j)=E_{t}[r(t+j,t+j+1)]+b\phi(t,t+j);j=1,\ldots,n.
$$

See Modigliani and Sutch (1966). Cox, Ingersoll, and Ross (1981) suggest LPH is a special case of PHH where the preferred habitat is short-term bonds..

# 25.4.5 Risk Premium Hypothesis (RPH)

The RPH states that forward rates are biased predictors of future spot rates based on the market price of risk bearing and the systematic risk of each bond. Every bond, except the single-period bond, contains some systematic risk and its market price of risk might vary. This known compensation for risk is defined as a risk premium. $(r p)$ . The RPH requires the ability to measure systematic risk as well as knowledge of the market price of risk-bearing. services for various amounts of systematic risk before being able to assign the appropriate risk premiums. The risk premium must be positive, might vary widely across maturities, and might vary across time. Based on our notation, we have.

$$
\mathrm{PH:}~f(t,t+j)=E_{t}[r(t+j,t+j)+1]+r p(t,t+j);j=1,\ldots,n.
$$

See Modigliani and Sutch (1966).
