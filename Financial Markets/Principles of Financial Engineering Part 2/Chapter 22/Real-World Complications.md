---
tags:
  - base_correlation
  - dispersion_effect
  - real_world_complications
  - time_effect
  - tranche_spreads
aliases:
  - CDS spreads
  - Dispersion
  - Real-world trading
  - Tranche valuation
key_concepts:
  - Base correlation approach
  - Dispersion effect on valuation
  - Implied compound correlation
  - Model tranche spreads
  - Time to maturity impact
---

# 22.6 REAL-WORLD COMPLICATIONS  

The discussion of how to model and value tranche spreads has been a very simplified one. Realworld trading has several complications and also requires further modeling effort. Several additional questions also need to be addressed. We briefly discuss them below..  

![](2101131f85e5f9436ae33bb67eafa0b2939f40970511e5af82b1f745c0023409.jpg)  

# FIGURE 22.4  

Base correlation.  

# 22.6.1 BASE CORRELATIONS  

The calculation of the implied compound correlation leads to the correlation smile in Figure 22.3. One of the issues is that the implied (compound) correlations can sometimes not be unique or may not even exist in mezzanine tranches. To address the issue of the nonmonotonicity of the mezzanine tranche, it became market practice to quote in another correlation, the base correlation, in addition to the compound correlation.  

The intuition behind the base correlation approach is relatively simple. The approach consists of transforming tranche quotes into quotes for equity tranches with increasing attachment points.11 The procedure to calculate base correlations in this way is referred to as a bootstrapping process and is outlined by McGinty et al. (2004). Base correlation will also give a skew, but this skew will. always exist and be unique (see Figure 22.4). One of the additional advantages of base correlations is that one can interpolate correlations to detachment points for which no market tranches exist. For these reasons, Bloomberg quotes iTraxx tranches in terms of base correlations and tranche spreads and not compound correlations.  

# 22.6.2 THE DISPERSION EFFECT  

The dispersion effect refers to how different individual spreads are from the index spread. For. example, if individual CDS spreads are more or less the same as the overall index spread, then we say that there is low dispersion..  

The dispersion of individual CDS spreads in the portfolio versus the spread of the portfolio itself is an important factor influencing the tranche valuation. The effect varies with individual tranches. For the equity tranche, the higher the dispersion of spreads the higher the number of basis points. This is due to the increased riskiness of the tranche. In the mezzanine tranche, the lower the dispersion, the higher the number of bps indicating increased risk. The results of senior and super senior tranches are similar to the mezzanine.  

# 22.6.3 THE TIME EFFECT  

Time is also a variable affecting the tranche spreads. As the time to maturity gets shorter, tranche values tend to decline. In other words, the tranche spread curves are, in general, upward sloping.  

# 22.6.4 DO DELTAS ADD UP TO ONE?  

Suppose there are two tranches and only two names in the reference portfolio. We can define two. tranches: the equity tranche and, say, the senior tranche. Can we say that the deltas of the entire reference portfolio weighted by tranche size should sum to one?.  

Suppose one default occurs. If we sold protection on the index itself, the index spread we would receive in the future would stay the same. However, a weighted average of tranche spreads would be significantly affected, since with the first default equity protection the seller would receive no further premiums. And, it turns out that the equity tranche spreads would be the highest.  

This effect is due to the fact that tranche spreads are unevenly distributed whereas the index has. a single spread. With the first default, the high spread tranche is triggered and the average spread of the remaining tranche portfolio decreases significantly. Clearly, if all tranches and the index. traded on an upfront basis this effect would disappear..  
