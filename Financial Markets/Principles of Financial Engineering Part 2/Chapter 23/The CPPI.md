---
tags:
  - '#cppi'
  - '#dynamic_ppi'
  - '#investment_strategy'
  - '#leveraged_products'
  - '#market_risk'
  - '#principal_protection'
  - '#risk_management'
  - '#structured_notes'
---
# 23.3 THE CPPI  

The main advantage of the CPPI as a principal protection technique is that it gives a higher participation in the underlying asset than one can get from traditional capital protection. It also can be applied when interest rates are "too' low, or when options do not trade for some underlying risk. Before we discuss the CPPI algorithm and the associated risks we consider some market examples.  

# EXAMPLE  

The CPPI investment is an alternative to standard tranche products, which offer limited upside (fixed premium) in exchange for unlimited downside (potential total loss of principal). CPPI offers limited downside (because of principal protection) and unlimited upside, but exposes investors to the market risk of the underlying default swaps contracts that comprise the coupon.  

With yields hovering near record lows until recently, credit investors are increasingly moving to structures that contain some element of market exposure. That has posed a problem for rating agencies, which are default oriented, and prompted a move to a more valuation-based approach for some products. Leveraged super senior tranches, also subject to market volatility, were the market risk product of choice last year, but in recent months have ceded popularity to CPPI.  

Banks profit from ratings on CPPI coupons because the regulatory capital treatment of rated products under Basel II is much kinder than on unrated holdings.  

The CPPI is a structure which has constant leverage. Dynamic PPI (proportion portfolio insurance) is the name for strategies where the leverage ratio changes during the investment period. CPPI works by dynamically moving the investment between a safe asset and a risky asset, depending on the performance of the risky asset and depending on how much cash one has in hand. The main criterion in doing this is to protect the principal, while at the same time getting the highest participation rate.  

The idea of CPPI can be related to the classical principal protection methods and is summa-. rized as follows. In the classical principal protection, the investor buys a zero-coupon bond and invests the remaining funds to options. CPPI relaxes this with a clever modification. If the idea is to be long a bond with value 100 at. $T.$ then one can invest any carefully selected sum to the. risky asset as long as one makes sure that the total value of the portfolio remains above the value of the zero-coupon bond during the investment period. Then, if the portfolio value is above the value of the zero-coupon bond, at any desired time the risky investment can be liquidated and the bond bought. This will still guarantee the protection of the principal, $N.$ This way, the structurer is not limited to investing just the leftover funds. Instead, the procedure makes possible an investment of funds of any size, as long as risk management and risk preference constraints are met.  

Let the initial investment of $N$ be the principal. The principal is also the initial net asset value of the positions--call it $V_{t_{0}}$ . Next, calculate the present value of $N$ to be received in $T$ years. Call this the floor, $F_{t_{0}}$ 3.  

$$
F_{t_{0}}=\frac{N}{\left(1+r_{t_{0}}\right)^{\mathrm{T}}}
$$  

Let the increment $C u_{t}$ be called the cushion:  

$$
C u_{t_{0}}=V_{t_{0}}-F_{t_{0}}
$$  

Then, select a leverage ratio. $\lambda$ in general satisfying. $1<\lambda.$ This parameter has no time subscript and is constant during the life of the structured note. Using the $\lambda$ calculate the amount to be. invested in the risky asset. $R_{t_{0}}$ as:  

$$
R_{t_{0}}=\lambda\big[V_{t_{0}}-F_{t_{0}}\big]
$$  

This gives the initial exposure to the risky asset $S_{t}.$ Invest $R_{t_{0}}$ in the risky asset and deposit the remaining $V_{t_{0}}-R_{t_{0}}$ into a risk-free deposit account.4  

$$
D_{t_{0}}=V_{t_{0}}-R_{t_{0}}
$$  

Note that the cash deposit $D_{t_{0}}$ is less than the time $t_{0}$ value of a risk-free zero-coupon bond that. matures at time $T_{:}$ denoted by $B(t_{0},T)N_{;}$ where $B(t_{0},T)$ is the time $t_{0}$ price of a default-free discount bond with par value $\$1$ . Hence, in case of a sudden and sizable downward jump in. $S_{t}$ the note will not have enough cash in hand to switch to a zero-coupon bond. This is especially true if the jump in $S_{t}$ leads to flight to quality and increases the. $B(t_{i},T)$ at some future date $t_{i}$ This is called the gap risk by the structurers and is studied later in the chapter..  

Apply this algorithm at every rebalancing date $t_{i}.$  

$$
t_{i}-t_{i-1}=\delta_{i}
$$  

as long as $F_{t_{i}}<V_{t_{i}}$ . This algorithm would increase the investment in the risky asset if things go well (i.e., if $V_{t_{i}}$ increases), and decrease the investment in case markets decline (i.e., if $V_{t_{i}}$ decreases).  

Finally, if at some time $\boldsymbol{\tau}^{*}\:\boldsymbol{V}_{\tau^{*}}$ falls and becomes equal to $F_{\tau^{*}}$ , liquidate the risky investment position and switch all investment to cash. Since the floor $F_{t_{i}}$ is the present value at $t_{i}.$ of 100 to be received at $T.$ this will guarantee that principal. $N$ can be returned to the investors at. $T.$  
