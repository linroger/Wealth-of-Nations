---
tags:
  - '#bond_options'
  - '#coupon_bearing_bonds'
  - '#cox_ingersoll_ross_model'
  - '#european_option'
  - '#ho_lee_model'
  - '#hull_white_model'
  - '#interest_rate_cap_floor'
  - '#option_pricing'
  - '#vasicek_model'
  - '#zero_coupon_bonds'
---
# 32.2 OPTIONS ON BONDS  

Some of the models just presented allow options on zero-coupon bonds to be valued analytically. For the Vasicek, Ho-Lee, and Hull-White one-factor models, the price at time zero of a call option that matures at time $T$ on a zero-coupon bond maturing at time $s$ is  

$$
L P(0,s)N(h)-K P(0,T)N(h-\sigma_{P})
$$  

where $L$ is the principal of the bond, $K$ is its strike price, and  

$$
h=\frac{1}{\sigma_{P}}\mathrm{ln}\frac{L P(0,s)}{P(0,T)K}+\frac{\sigma_{P}}{2}
$$  

The price of a put option on the bond is  

$$
K P(0,T)N(-h+\sigma_{P})-L P(0,s)N(-h)
$$  

Technical Note 31 shows that, in the case of the Vasicek and Hull-White models,  

$$
\sigma_{P}=\frac{\sigma}{a}[1-e^{-a(s-T)}]\sqrt{\frac{1-e^{-2a T}}{2a}}
$$  

and, in the case of the Ho-Lee model,  

$$
\begin{array}{r}{\sigma_{P}=\sigma(s-T)\sqrt{T}}\end{array}
$$  

Equation (32.10) is essentially the same as Black's model for pricing bond options in Section 29.1 with the forward bond price volatility equaling $\bar{\sigma_{P}}/\sqrt{T}$ . As explained in Section 29.2, an interest rate cap or floor can be expressed as a portfolio of options on zero-coupon bonds. It can, therefore, be valued analytically using the equations just presented.  

There are also formulas for valuing options on zero-coupon bonds in the Cox, Ingersoll, and Ross model, which we presented in Section 31.2. These involve integrals of the noncentral chi-square distribution.  

# Options on Coupon-Bearing Bonds  

In a one-factor model of. $r$ , all zero-coupon bonds move up in price when. $r$ decreases and all zero-coupon bonds move down in price when. $r$ increases. As a result, a one-. factor model allows a European option on a coupon-bearing bond to be expressed as the sum of European options on zero-coupon bonds. The procedure is as follows:  

1. Calculate $r^{*}$ , the critical value of $r$ for which the price of the coupon-bearing bond equals the strike price of the option on the bond at the option maturity $T$   
2. Calculate prices of European options with maturity $T$ on the zero-coupon bonds that comprise the coupon-bearing bond. The strike prices of the options equal the values the zero-coupon bonds will have at time $T$ when $r=r^{*}$   
3. Set the price of the European option on the coupon-bearing bond equal to the sum of the prices on the options on zero-coupon bonds calculated in Step 2.  

This allows options on coupon-bearing bonds to be valued for the Vasicek, Cox, Ingersoll, and Ross, Ho-Lee, and Hull-White models. As explained in Business Snapshot 29.2, a European swap option can be viewed as an option on a coupon-bearing bond. It can, therefore, be valued using this procedure. For more details on the procedure and a numerical example, see Technical Note 15 at www-2.rotman.utoronto.ca/\~hull/ TechnicalNotes.  
