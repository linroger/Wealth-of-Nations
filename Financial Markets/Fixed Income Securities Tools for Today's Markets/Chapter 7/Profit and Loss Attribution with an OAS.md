---
tags:
  - carry_roll_down
  - oas
  - profit_loss_attribution
  - relative_value_trading
  - term_structure_models
aliases:
  - OAS
  - P&L attribution
  - Spread change
key_concepts:
  - Carry-roll-down
  - OAS definition
  - One-factor model
  - P&L attribution
  - Rate changes
  - Risk-neutral process
  - Spread change
  - Taylor approximation
---

# 7.7 PROFIT AND LOSS ATTRIBUTION WITH AN OAS  

Chapter 3 introduced profit and loss $(\mathrm{P}\&\mathrm{L})$ attribution. This section gives a mathematical description of attribution in the context of term structure models and of securities that trade with an OAS. While the notation of this chapter is quite formal, the presentation remains intuitive.  

By the definition of a one-factor model, and by the definition of OAS, the market price of a security at time. $t$ and a factor, $r$ , which is often a rate,.  

can be written as. $P_{t}(r,O A S)$ . Using a first-order Taylor approximation, the change in the price of the security is,.  

$$
d P={\frac{\partial P}{\partial r}}d r+{\frac{\partial P}{\partial t}}d t+{\frac{\partial P}{\partial{\mathrm{OAS}}}}d{\mathrm{OAS}}
$$  

where $\partial P/\partial r$ gives the change in the price of the security for a change in $r$ holding $t$ and OAS constant; $\partial P/\partial t$ gives the change in price for a change. in $t$ holding $r$ and OAS constant; and the same for. $\partial P/\partial O A S$ . In words, Equation (7.32) breaks down the total change in price to components of change due to changes in $r,t$ , and OAS.  

Dividing both sides of Equation (7.32) by price and taking expectations,  

$$
E\left[{\frac{d P}{P}}\right]={\frac{1}{P}}{\frac{\partial P}{\partial r}}E[d r]+{\frac{1}{P}}{\frac{\partial P}{\partial t}}d t
$$  

Note that $d P/P$ is the change in price divided by price, or the percentage change in price. Because the OAS calculation assumes that OAS is constant over the life of the security, moving from (7.32) to (7.33) assumes that the expected change in the OAS is zero.  

As mentioned in the previous section, if expectations are taken with. respect to the risk-neutral process, then, for any security priced according to the model,  

$$
E\left[{\frac{d P}{P}}\right]=r_{0}d t
$$  

But Equation (7.34) does not apply to securities that are not priced according. to the model, that is, to securities with an OAS not equal to zero. For these securities, by definition, the cash flows are discounted not at the short-term rate, but at the short-term rate plus the OAs. Equivalently, as argued in the previous section, the expected return under the risk-neutral probabilities is. not the short-term rate, but the short-term rate plus the OAS. Hence, the more general form of Equation (7.34) is,.  

$$
E\left[\frac{d P}{P}\right]=(r_{0}+O A S)d t
$$  

Combining these pieces, substitute for $(1/P)\partial P/\partial t$ from (7.33) and then for $E[d P/P]$ from (7.35) into Equation (7.32) and rearrange terms, which breaks down the return of a security into its component parts,.  

$$
{\frac{d P}{P}}=(r_{0}+O A S)d t+{\frac{1}{P}}{\frac{\partial P}{\partial r}}(d r-E[d r])+{\frac{1}{P}}{\frac{\partial P}{\partial O A S}}d O A S
$$  

Finally, multiplying through by $P$  

$$
d P=(r_{0}+O A S)P d t+{\frac{\partial P}{\partial r}}(d r-E[d r])+{\frac{\partial P}{\partial O A S}}d O A S
$$  

In words, the return of a security or its $\mathrm{P}\&\mathrm{L}$ may be divided into a component due to the passage of time; a component due to changes in the factor; and a component due to the change in the OAS. In the language of Chapter 3, the terms on the right-hand side of (7.37) represent, in order, carry-roll-down, gains or losses from rate changes, and gains or losses from spread change.1 For models with predictive power, the OAS converges or trends to zero; that is, the security price converges or trends toward its fair value according to the model.  

The decompositions of Equations (7.36) and (7.37) highlight the usefulness of OAS as a measure of value. If a model is correct, a long position in. a cheap security earns superior returns in two ways. First, it earns the OAS over time intervals in which the security does not converge to its fair value. Second, it earns its sensitivity to OAS times any convergence of that OAS. to zero.  

The decompositions also provide a framework for relative value trad-. ing. When a cheap or rich security is identified, a relative value trader buys or sells the security and hedges out all interest rate or factor risk. Mathematically, $\partial P/\partial r=0$ . In that case, the expected return or P&L depends only on the short-term rate, the OAS of the securities traded, and any OAS convergence. If the trader finances the trade at the short-term rate, that is, borrows $P$ at rate $r_{0}$ to purchase the security, then the expected return is simply equal to the OAS plus any convergence return. If the hedge itself costs or generates funds, then the P&L also includes a return on those funds at the short-term rate. If the hedging securities are not fairly priced relative to the model, but have an OAS of their own, then the P&L also includes an OAS on the hedge. Finally, Chapter 8 explains that bearing interest rate or. factor risk may earn a risk premium, in which case there would be an additional term in Equations (7.34) through (7.37) that depends on the amount of factor risk borne. But, in the relative value context, where factor risk is hedged away, any risk premium terms cancel out, and the P&L of the trade is as described in this paragraph..  
