---
title: Appendix 5.C Forward And Futures Prices When Interest Rates Are Random
---

# Appendix 5.C Forward And Futures Prices When Interest Rates Are Random

This appendix formalizes the difference between forward and futures prices and shows the relationship between them when interest rates are stochastic. We will use the following notation:

$$F_{t,        T}=$$

Ft ,  T = Forward price ft ,  F = Futures price St = Time t price of the underlying asset Pt ,  T = Time t price of a zero-coupon bond maturing at time T .

$${\mathbf{}}_{t_{\mathrm{a}},        T}$$
$\mathbf{M}$
Rt = Time t interest rate from time t to time t + h.

h = Length of a period; h = T/n We will refer to an instrument that pays the short-term interest rate as a money-market account.

The strategy in these derivations,  which follow Cox et al. (1981),  is to find a strategy that replicates fully funded contracts.

## Forward Prices

The forward price is

$$F_{t,        \,        T}=\mathrm{PV}\left({\frac{S_{T}}{P_{t,        \,        T}}}\right)={\frac{S_{t}}{P_{t,        \,        T}}}$$
$$(5.23)$$

$$(5.24)$$

In the chapter,  we wrote this formula asFt ,  T = *Ster(T* −t). This is the same as equation (5.23),
where r is the continuously compounded yield on the bond: r = ln(1/Pt ,  T *)/(T* − t).

To prove equation (5.23),  buy Ft ,  T bonds paying $1 at maturity (this prefunds the forward price) and go long 1/Pt ,  T forward contracts. The payoff is

$${\frac{F_{t,        \,        T}}{P_{t,        \,        T}}}+{\frac{1}{P_{t,        \,        T}}}\left[F_{T,        \,        T}-F_{t,        \,        T}\right]={\frac{F_{t,        \,        T}}{P_{t,        \,        T}}}={\frac{S_{T}}{P_{t,        \,        T}}}$$

This demonstrates that a portfolio costing the forward price at time t pays ST /Pt ,  T . Thus,  the forward price is the present value of ST /Pt ,  T ,  or *St/Pt* ,  T .

## Futures Price

We will show that the futures price is

$$f_{I,        \,        T}=\mathrm{PV}\left[S_{T}\prod_{i=t}^{T}(1+R_{i})\right]$$
(5.24)
Note that if the interest rate is known,         	Ti=t
(1+ Ri) = 1/Pt ,  T (the bond can be replicated with the money-market fund),  and the forward price equals the futures price.

To prove equation (5.24),  invest the amount ft ,  T at the short-term interest rate,  reinvesting the proceeds each period. Also,  at each time ti ≡ t + ih,  i = 1,  … ,  n,  invest in tij=t
(1+ Rj ) futures contracts. At time ti+1,  liquidate position and invest the proceeds in the money-market account. The net cash flow at time T will be

$$f_{t,        \,        T}\prod_{i=t}^{T}(1+R_{i})+\sum_{i=t}^{T-h}\left(\prod_{j=t}^{i}(1+R_{j})(f_{j,        \,        T}-f_{j-h,        \,        T})\prod_{j=i+h}^{T-h}(1+R_{j})\right)$$ $$=f_{T,        \,        T}\prod_{i=t}^{T-h}(1+R_{i})=S(T)\prod_{i=t}^{T-h}(1+R_{i})$$ For future reference,  note that in continuous time,  equation (5.24) becomes
$$f_{t,        \,        T}=\text{PV}\left[S_{T}e^{\int_{t}^{T}r(s)ds}\right]\tag{5.25}$$

where *r(s)* is the instantaneous continuously compounded short-term interest rate.
