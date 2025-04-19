---
tags:
  - coupon_bond
  - frobenius_series
  - gauss_laguerre
  - interest_rate_derivatives
  - stochastic_volatility
aliases:
  - Interest Rate Derivatives Pricing
  - Nabil Tahani
  - Xiaofei Li
key_concepts:
  - Coupon bond options
  - Frobenius series solution
  - Gauss-Laguerre quadrature rule
  - Interest rate derivatives pricing
  - Stochastic interest rate volatility
---

# Pricing Interest Rate Derivatives under Stochastic Volatility  

Nabil Tahani Xiaofei Li\* York University York University This Draft: May 21, 2007  

# Abstract  

This paper derives semi-closed-form solutions to a variety of interest rate derivatives prices.. Our approach consists of first deriving the Frobenius series solution to the cross-moments gener-. ating function, and then inverting the characteristic function using the Gauss-Laguerre quadrature rule for the corresponding cumulative probabilities. We apply our approach to value options on discount bonds, coupon bond options, swaptions, interest rate caps, floors, and collars. Our approach is found to be both accurate and fast, and it compares favorably with some alternative. approaches in the literature.  

JEL Classification: G12; G13.  

Keywords: characteristic functions; Frobenius series solution; Gauss-Laguerre quadrature rule; interest rate derivatives; stochastic volatility.  

# 1 Introduction  

It is well-known to both academics and practitioners that the volatility of interest rates is itself volatile (see among others Ball and Torous (1999)). Figures 1 and 2 plot the time series of the weekly 3-month U.S. T-bill rates as well as their first order differences over the time period January 1954 to December 2006 (source of data: the H.15 release from the Federal Reserve Board). Table 1 shows the statistics summary for both series. It is evident from the figures and the descriptive statistics that the interest rates are not Gaussian and that their volatility is changing through time.  

[Figures 1 and 2 are about here.] [Table 1 is about here.]  

Modeling interest rate volatility is critical from an asset pricing perspective. Almost all fixedincome securities contain embedded options, for example, callable bonds and putable bonds etc. Since the prices of the embedded options (e.g. call and put options) depend on interest rate volatility, measuring the sensitivity of a security's value to interest rate volatility is therefore central to pricing fixed-income securities.  Modeling interest rate volatility also has a wide variety of applications in managing fixed-income portfolios, including portfolio hedging, portfolio indexing, and portfolio immunization, to name just a few. Indeed, the ability to effectively model interest rate volatility is fundamental to virtually all areas of fixed-income security and portfolio analysis. Not surprisingly, the academic literature on modeling interest rate volatility and pricing interest rate derivatives has been growing fast.  

In this paper, we provide semi-closed-form solutions to various interest rate derivatives under stochastic interest rate volatility. Different from the existing literature (some of them are reviewed below), our approach is specifically for a stochastic volatility interest rate model where the volatility is modeled by a separate process. But our approach is not model-specific. In fact, it can be. generalized to other affine term structure models with stochastic volatility as well. Specifically, in our approach we first derive the Frobenius series solution to the moments generating function of the zero-coupon bond price.1 Then, we invert the characteristic function using the Gauss-Laguerre. 1Although Selby and Strickland (1995) use a similar approach to compute zero-coupon bond prices, we extend quadrature rule to recover the corresponding cumulative probabilities, which are used to compute the prices of different interest rate derivatives. Our approach is easier to implement, fast, and. accurate, and it compares favorably with some other approaches in the literature..  

A number of recent studies have also examined the pricing of options on coupon bonds. Jamshidian (1989), for instance, argues that an option on a coupon bond can be decomposed into a portfolio of options on discount bonds. Provided that there exists a closed-form solution to discount bond option price, we can solve for the value of a coupon bond option analytically. Jamshidian illustrates his approach in the context of the constant volatility Vasicek (1977) model, and his approach is valid for any single-factor interest rate model.  

Wei (1997) develops an approximation for coupon bond options prices based on closed-form solutions for the corresponding discount bond options and a duration measure defined in his paper.. He applies his approach to the constant volatility model in Vasicek (1977) and the model in Cox,. Ingersoll, and Ross (1985, CIR hereafter) where volatility, though not a constant, is not modeled as a separate factor. Munk (1999) extends the approach in Wei (1997) and develops a method known as the stochastic duration approach. Munk applies his method to a number of multi-factor models. including the deterministic volatility models in Ho and Lee (1986), Hull and White (1990), and Heath, Jarrow, and Morton (1992), and the model in Longstaff and Schwartz (1992). Singleton and. Umantsev (2002) propose an approximation to the prices of European options on coupon bonds. where the underlying short rate is an affine combination of the CIR-type square root processes. Stochastic volatility of interest rates is present in their framework only because in a CIR-type. process volatility depends on the level of state variable (e.g. short rate) and is thus time-varying. However, in this framework volatility can not move independently of the state variable. In contrast, in the Fong and Vasicek (1991, hereafter FV) model used in this paper, interest rate volatility is modeled as a separate process (see equations (1) and (2) in Section 2 below). Finally, Chacko and Das (2002) present a theoretical approach to pricing a wide variety of interest rate derivatives. The general model considered in their paper involves both jumps in the level of short rate and stochastic volatility. But for multi-factor models, such as the stochastic volatility model in Fong and Vasicek (1991), the method proposed in Chacko and Das (2002) may be time-consuming.  

The rest of the paper is organized as follows. Section 2 introduces the FV model. Section 3 provides the solutions to options on zero-coupon bonds. Section 4 extends the approach to value coupon bond options and discusses the valuation of swaptions, interest rate caps, floors, and collars. Section 5 presents some numerical examples to assess the accuracy and efficiency of the proposed approach. Finally, Section 6 concludes the article. The computational details are contained in the Appendix.  

# 2 The Fong and Vasicek (1991) interest rate model  

Fong and Vasicek (1991) explicitly incorporate the stochastic volatility of interest rates as a separate factor (in addition to the short rate itself) and propose a two-factor model of interest. rates. Their model is described as the follows..  

Under the physical (or actual) probability measure $P$ , the instantaneous nominal riskless interest rate is denoted by $r_{t}$ , and is assumed to follow the diffusion processes  

$$
\begin{array}{r}{d r_{t}=\alpha(\overline{{r}}-r_{t})d t+\sqrt{v_{t}}d W_{t},}\ {d v_{t}=\gamma(\overline{{v}}-v_{t})d t+\xi\sqrt{v_{t}}d Z_{t},}\end{array}
$$  

where the two Brownian motions $W_{t}$ and $Z_{t}$ are correlated with a coefficient of. $\rho$ . In equation (2), $v_{t}$ denotes the instantaneous variance of the risk free rate $r_{t}$ and is modeled using a distinct. stochastic process. It follows that the volatility of interest rate $r_{t}$ is also stochastic. In equations. (1) and (2), $\alpha$ and $\gamma$ are the speed of mean reversion of factors $r_{t}$ , and $v_{t}$ , respectively; and $r$ and $v$ can be interpreted as the long-run mean of $r_{t}$ , and $v_{t}$ , respectively. The specification in equations (1) and (2) belongs to the class of exponential affine (or simply affine) term structure of interest rate models.2  

We write the processes in (1) and (2) under the risk-neutral probability measure $Q$ as  

$$
\begin{array}{r}{d r_{t}=(\alpha(\overline{{r}}-r_{t})+\lambda v_{t})d t+\sqrt{v_{t}}d\widehat{W}_{t},}\ {d v_{t}=(\gamma\overline{{v}}-(\gamma+\xi\eta)v_{t})d t+\xi\sqrt{v_{t}}d\widehat{Z}_{t},}\end{array}
$$  

where the two Brownian motions $\widehat{W_{t}}$ and $\hat{Z}_{t}$ have a correlation coefficient of $\rho$ , and $\lambda$ and $\eta$ are the risk premiums associated with interest rate risk and volatility risk, respectively.  

The FV model can generate various shapes for the yield term structure, as shown in Figures. 3-5. The FV model also allows for a closed-form solution to zero-coupon (or discount) bond. price. But the original solution given in Fong and Vasicek (1991) involves complex algebra and is difficult to implement in practice. Selby and Strickland (1995, hereafter SS) introduce an alternative. method to compute the discount bond prices in the FV model. The SS method is based on the Frobenius solutions and is both accurate and fast. Finally, using Monte Carlo valuation Clewlow and Strickland (1997) show how to price various interest rate derivatives within the FV framework. In this paper, we extend the Frobenius series method proposed in SS to price a variety of interest rate derivatives accuartely and much faster than the Monte Carlo simulation..  

[Figures 3-5 are about here.]  

# 3 Pricing of discount bond options  

This section illustrates the pricing of call options on zero-coupon bonds.3 Consider a call option with a maturity of $T$ years written on a zero-coupon bond of a maturity of $\theta$ years and a strike price of $K$ . We use $P(T,\theta)$ and $C a l l(t,T,\theta,K)$ to denote the price of the underlying zero-coupon bond and the time $t$ price of this call option, respectively. Under the risk-neutral probability measure $Q$ the call option price is given as  

$$
\begin{array}{r l r}&{}&{C a l l(t,T,\theta,K)={\cal E}_{t}^{Q}[e^{-\int_{t}^{T}r_{s}d s}(P(T,\theta)-K)^{+}]}\ &{}&\ &{}&{\quad={\cal E}_{t}^{Q}[e^{-\int_{t}^{T}r_{s}d s}P(T,\theta)\times1_{P(T,\theta)\ge K}]-K{\cal E}_{t}^{Q}[e^{-\int_{t}^{T}r_{s}d s}\times1_{P(T,\theta)\ge K}],}\end{array}
$$  

we can rewrite equation (5) equivalently as4  

$$
C a l l(t,T,\theta,K)=P(t,\theta)E_{t}^{Q^{\theta}}[1_{\ln P(T,\theta)\geq\ln K}]-K P(t,T)E_{t}^{Q^{T}}[1_{\ln P(T,\theta)\geq\ln K}],
$$  

where the Radon-Nikodym derivatives are  

$$
\frac{d Q^{M}}{d Q}\equiv\frac{e^{-\int_{t}^{T}r_{s}d s}P(T,M)}{P(t,M)},
$$  

$M=T$ $\theta$ To comput he probaility $E_{t}^{Q^{M}}[1_{\ln{P(T,\theta)}}\geq\ln{K}]$ in (), we have t ist calelate its corresponding moment generating function  

$$
E_{t}^{Q^{M}}[e^{\varphi\ln(P(T,\theta))}],
$$  

where $\varphi$ is a constant. In the Appendix, it is shown that the moment generating function in equation (8) is equal to  

$$
\frac{1}{P(t,M)}E_{t}^{Q}[e^{-\int_{t}^{T}r_{s}d s}\times e^{-(\varphi D(T,\theta)+D(T,M))r_{T}}\times e^{(\varphi F(T,\theta)+F(T,M))v_{T}}\times e^{(\varphi G(T,\theta)+G(T,M))b_{T}}]
$$  

for $M=T$ or $\theta$ . The functions $D(t,s)$ $F(t,s)$ , and $G(t,s)$ in (9) above are the functions consisting of the discount bond price $P(t,s)$ in the FV model. We refer the interested reader to Selby and Strickland (1995) for the details about these three functions.  

For notational simplicity, we rewrite equation (9) as  

$$
E_{t}^{Q^{M}}[e^{\varphi\ln(P(T,\theta))}]=\frac{1}{P(t,M)}E_{t}^{Q}[e^{-\int_{t}^{T}r_{s}d s}\times e^{-A_{0}r_{T}}\times e^{B_{0}v_{T}}\times e^{C_{0}}],
$$  

with ${\cal A}_{0}\equiv\varphi D(T,\theta)+D(T,{\cal M})$ $B_{0}\equiv\varphi F(T,\theta)+F(T,M)$ , and $C_{0}\equiv\varphi G(T,\theta)+G(T,M)$ . Once we solve the moment generating function $E_{t}^{Q^{M}}[e^{\varphi\ln(P(T,\theta))}]$ , we can recover the cumulative probability $Q^{M}(\ln P(T,\theta)\geq\ln K)$ by applying the Fourier inversion transform to get  

$$
Q^{M}(\ln P(T,\theta)\geq\ln K)=\frac{1}{2}+\frac{1}{\pi}\int_{0}^{+\infty}\mathop{\mathrm{Re}}\{\frac{E_{t}^{Q^{M}}[e^{i\varphi\ln(P(T,\theta))}]}{i\varphi}K^{-i\varphi}\}d\varphi,
$$  

where $\operatorname{Re}(\cdot)$ denotes the real part of a complex number. In equation (11) the integrand is welldefined and the integral is convergent. Finally, although the integral in (11) can not be solved in  

closed-form, numerical techniques can be used to approximate its value (see e.g. Heston (1993)). In this paper, we follow Sullivan (2000, 2001) and Tahani (2004) and use the Gauss-Laguerre quadrature rule to compute the value of the integral in (11).  

Before computing the moment generating function in $E_{t}^{Q^{M}}[e^{\varphi\ln(P(T,\theta))}]$ , it is worthwhile to consider the valuation of the following "generalized" zero-coupon bond price5  

$$
P(t,T,\psi,\varphi,\omega)=E_{t}^{Q}(e^{-\psi\int_{t}^{T}r_{s}d s}\times e^{-\varphi r_{T}}\times e^{-\omega v_{T}}).
$$  

Denote $\tau\equiv T-t$ , we can rewrite the above "generalized" bond price as $P(\tau,\psi,\varphi,\omega)$ . We assume the following functional form for $P(\tau,\psi,\varphi,\omega)$  

$$
P(\tau,\psi,\varphi,\omega)=e^{-A(\tau)r+B(\tau)v+C(\tau)}.
$$  

We show in the Appendix that the system of the ordinary differential equations (ODEs) satisfied by the functions $A(\tau),B(\tau)$ , and $C(\tau)$ is the following  

$$
\begin{array}{c}{{A^{\prime}=-\alpha A+\psi,~A(0)=\varphi;}}\ {{{}}}\ {{B^{\prime}=\displaystyle\frac{1}{2}\xi^{2}B^{2}-\left((\gamma+\xi\eta)+\rho\xi A\right)B-\lambda A+\displaystyle\frac{1}{2}A^{2},~B(0)=-\omega;}}\ {{{}}}\ {{C^{\prime}=-\alpha\overline{{{r}}}A+\gamma\overline{{{v}}}B,~C(0)=0.}}\end{array}
$$  

In the above system of ODEs, $A^{\prime}$ denotes $\frac{\partial A}{\partial\tau}$ $B^{\prime}$ and $C^{\prime}$ are defined analogously; and $A(0)=\varphi$ $B(0)=-\omega$ , and $C(0)=0$ are the initial conditions.  

The ODE in (14), which is for function $A$ , can be solved in simple closed-form as $A(\tau)=$ $\begin{array}{r}{\frac{\psi}{\alpha}+(\varphi-\frac{\psi}{\alpha})e^{-\alpha\tau}}\end{array}$ , and function $C$ can be found by direct integration once we know both $A$ and $B$ . The difficult part lies in solving the ODE for. $B$ in (15), which is a Riccati equation. A Riccati. equation is one type of nonlinear first-order ODE. In the current case, although function $B$ can be found in closed-form, the solution is fairly complicated and contains complex algebra.  

To overcome this difficulty, we follow Selby and Strickland (1995) and make a simple substitution  

$$
U(\tau)=\exp[-\frac{1}{2}\xi^{2}\int_{0}^{\tau}B(s)d s],~U(0)=1,U^{\prime}(0)=\frac{\xi^{2}}{2}\omega.
$$  

This substitution transforms the nonlinear ODE in (15) into an equivalent linear second-order ODE for $U$ . Under this substitution, functions $B$ and $C$ can be rewritten as  

$$
\begin{array}{c}{{\displaystyle B(\tau)=-\frac{2}{\xi^{2}}\frac{U^{\prime}(\tau)}{U(\tau)},}}\ {{\displaystyle C(\tau)=-\alpha\overline{{{r}}}\int_{0}^{\tau}A(s)d s-\frac{2\gamma\overline{{{v}}}}{\xi^{2}}\ln U(\tau).}}\end{array}
$$  

Therefore the solution to the "generalized' zero-coupon bond pricing formula in (13) amounts to evaluating $U(\tau)$ and $U^{\prime}(\tau)$ . A further substitution  

$$
\tau=-\frac{1}{\alpha}\ln(z),0\leq z\leq1;
$$  

$$
U(\tau)=z^{\beta}S(z),
$$  

where $\beta$ is a constant to be determined, reduces the ODE for $U$ to a homogeneous linear ODE of. second order for $S$ , which can be solved by using a Frobenius series solution method. Once we obtain the solution to $S$ , we can retrace, substituting $S$ back into (20) for $U$ , and then substituting $U$ back into (18) and (19) for $B$ and $C$ , respectively. For computational details, please refer to the Appendix.  

# 4 Valuation of options on coupon bonds and other derivatives  

We now extend the valuation approach in the previous section to the pricing of coupon bond options and other interest rate derivatives..  

# 4.1 Coupon bond options  

Following Munk (1999), we approximate the price of a coupon bond option using an option on a zero-coupon bond that has the same stochastic duration as the coupon bond. In particular, consider a coupon bond paying. $a_{i}$ at time $t_{i}$ $i=1$ , 2, ..,. $n$ . The price of this bond at any time $t<t_{1}$ is given by. $H(t)=\sum_{i=1}^{n}a_{i}P(t,t_{i})$ . A straightforward application of the Ito's lemma yields  

$$
\frac{H(t)}{H(t)}=\sum_{i=1}^{n}a_{i}^{\prime}(t,t_{i})\mu(t,t_{i},r_{t},v_{t})d t+\xi\sqrt{v_{t}}\sum_{i=1}^{n}a_{i}^{\prime}(t,t_{i})F(t,t_{i})d Z_{t}-\sqrt{v_{t}}\sum_{i=1}^{n}a_{i}^{\prime}(t,t_{i})D(t,t_{i})d Z_{t}.
$$  

where the weight $\begin{array}{r}{a_{i}^{\prime}(t,t_{i})=\frac{a_{i}P(t,t_{i})}{H(t)}}\end{array}$ , and $\mu(t,t_{i},r_{t},v_{t})$ is a function of the model's parameters. In addition, for the zero-coupon bond price $P(t,s)$ we have  

$$
\frac{d P(t,s)}{P(t,s)}=\mu(t,s,r_{t},v_{t})d t+\xi\sqrt{v_{t}}F(t,s)d Z_{t}-\sqrt{v_{t}}D(t,s)d W_{t}.
$$  

The stochastic duration. $\delta(t)$ is defined as the time to maturity of the discount bond that has the same relative volatility as the coupon bond.6 More specifically,. $\delta(t)$ is the solution of the following. equation  

$$
\begin{array}{c}{{\displaystyle\left[\xi F(t,\delta(t))-\rho D(t,\delta(t))\right]^{2}+(1-\rho^{2})D(t,\delta(t))^{2}}}\ {{=\displaystyle\left[\sum_{i=1}^{n}a_{i}^{\prime}(t,t_{i})\left[\xi F(t,t_{i})-\rho D(t,t_{i})\right]\right]^{2}+(1-\rho^{2})\left[\sum_{i=1}^{n}a_{i}^{\prime}(t,t_{i})D(t,t_{i})\right]^{2}.}}\end{array}
$$  

Clearly, equation (23) has to be solved numerically. Once $\delta(t)$ is computed, the price of the coupon bond option can be approximated by a multiple of the price of the option on a zero-coupon bond with a time to maturity equal to $\delta(t)$ . More formally, the price of a call option on the coupon bond defined above is approximated by  

$$
C a l l_{B o n d}(t,T,K)\simeq\zeta C a l l(t,T,t+\delta(t),\frac{K}{\zeta}),
$$  

where $\begin{array}{r}{\zeta=\frac{H(t)}{P(t,t+\delta(t))}}\end{array}$ . The put option price can be approximated similarly.  

# 4.2 Swaptions  

A swaption (or option on an interest rate swap) is an option to exchange periodical fixed-rate. payments for floating-rate payments. When the swap is created, the floating-rate payments have a. present value equal to the notional principal amount of the swap. The swaption can therefore be valued as a coupon bond call option with a strike price equal to the principal amount..  

# 4.3 Interest rate caps, floors, and collars  

An interest rate cap or floor provides the right to get payoffs at periodic dates called the reset dates. At each reset date, the interest rate cap/floor has a payoff that is the same as the payoff for a zero-coupon bond put/call option. Therefore, the interest rate cap/floor can be seen as a sequence of many puts/calls called caplets or floorlets, respectively. The cap/floor premium is then equal to the sum of the corresponding caplets/floorlets premiums. The price of an interest rate cap. with reset dates $(\theta_{i})_{1\leq i\leq n}$ and a cap rate ${'}c a p$ is given by  

$$
C a p(t,(\theta_{i})_{1\leq i\leq n},r_{c a p})=(1+r_{c a p}\Delta\theta)\sum_{i=1}^{n-1}P u t(t,\theta_{i},\theta_{i+1},K_{c a p}),
$$  

where $\begin{array}{r}{K_{c a p}=\frac{1}{1+r_{c a p}\Delta\theta}}\end{array}$ $\Delta\theta$ is the reset interval, and. $P u t(t,\theta_{i},\theta_{i+1},K_{c a p})$ is the price of a zero-.   
coupon bond put.  

Equivalently, the price of an interest rate floor with reset dates $(\theta_{i})_{1\leq i\leq n}$ and a floor rate $r_{f l o o r}$ is given by  

$$
F l o o r(t,(\theta_{i})_{1\le i\le n},r_{f l o o r})=(1+r_{f l o o r}\Delta\theta)\sum_{i=1}^{n-1}C a l l(t,\theta_{i},\theta_{i+1},K_{f l o o r}),
$$  

where K floor = 1+r floor0.  

A collar is another popular interest rate derivative. It is simply a combination of a long position on an interest rate cap and a short position on an interest rate foor with the same characteristics (i.e. settlement dates and reset intervals). In this, the collar can simply be priced as the difference between the price of the long cap with a strike price $K_{c a p}$ and the price of the short floor with a strike price $K_{f l o o r}$  

# 5 Numerical examples  

This section presents some numerical examples to assess the accuracy and the efficiency of the. proposed approximation with different sets of parameters. The benchmark prices are either given. by closed-form solutions such as the Jamshidian (1989) formula in the case of constant volatility Vasicek (1977) model, or by a plain Monte Carlo simulation based on 100,000 paths in the case of the FV (1991) stochastic volatility model.  

First, we assess the approximation within the Vasicek (1977) constant volatility model. We consider the following set of parameters: $\alpha=1.2$ $\overline{{r}}=0.095$ $r=0.08$ , and $v=0.015$ .We price a one-year at-the-money forward call on a five-year zero-coupon bond. Table 2 shows how the approximate price converges to the exact price given by the Jamshidian (1989) formula for different quadrature orders as well as the absolute errors. Note that an order of 15 is sufficient to obtain a very accurate price.  

[Table 2 is about here.]  

The second example is a one-year at-the-money forward call on a two-year zero-coupon bond in the FV stochastic volatility model with the following set of parameters:. $\alpha=2$ $\overline{{r}}=0.07$ $r=0.08$ $\overline{{v}}=v=0.02$ $\gamma=2$ $\lambda=0.2$ $\xi=0.0001$ $\eta=0.1$ , and $\rho=0.2$ . The third example is a one-year at-the-money forward call on a five-year zero-coupon bond in the FV model with the following set of parameters: $\alpha=2$ $\overline{{r}}=0.095$ $r=0.08$ $\overline{{v}}=v=0.015$ $\gamma=2$ $\lambda=0.2$ $\xi=0.0001$ $\eta=0.1$ , and $\rho=0.6$ . Tables 3 and 4 provide the approximate prices, the Monte Carlo prices, and their standard. deviations for these two examples, respectively. It is shown in the tables that a good accuracy can be achieved for quadrature orders of 25 and higher..  

[Tables 3-4 are about here.]  

We now provide some results for options on coupon bonds. Consider a one-year call on a fiveyear coupon bond with a semi-annual coupon of $\$0.04$ and a face value of $\$1$ . Tables 5 and 6 use the Vasicek (1977) model since we have a closed-form solution provided by Jamshidian (1989) to which. we can compare our approximation. The model's parameters are:. $\alpha=1.2$ $\overline{{r}}=0.095$ $r=0.08$ , and $\overline{{v}}=v=0.015$ . Table 5 shows the results for an at-the-money call with a strike price. $K=\mathbb{5}0.8767$ The stochastic duration of this coupon bond is 3.5324 and the call price is \$0.0733076, while in. comparison the call price by the Jamshidian solution is $\$0.0733027$ . Table 6 shows the results for an in-the-money call with a strike price $K=\mathbb{5}0.7970$ . The call price is \$0.14477, while the Jamshidian price is \$0.144770.  

[Tables 5-6 are about here.]  

Within the FV (1991) stochastic volatility model, Tables 7-8 compare our approximation to a plain Monte Carlo simulation using the following set of parameters:. $\alpha=2$ $\overline{{r}}=0.095$ $r=0.08$ $\overline{{v}}=v=0.015$ $\gamma=2$ $\lambda=0.2$ $\xi=0.0001$ $\eta=0.1$ , and $\rho=0.6$ . The stochastic duration of. the coupon bond is 2.8825. For Table 7, the at-the-money strike price is. $\$0.8557$ , the approximate call price is. $\$0.0726108$ , while the Monte Carlo price is. $\$0.0726402$ with a standard deviation of $8.6275e\mathrm{~-~}5$ . For Table 8, the in-the-money strike price is \$0.8150, the approximate price is $\$0.109902$ , while the Monte Carlo price is \$0.109801 with a standard deviation of $8.8149e\mathrm{~-~}5$  

[Tables 7-8 are about here.]  

For all the above numerical examples, the approximation based on the Frobenius series and the. stochastic duration is found to be very accurate relative to the Monte Carlo simulation. In addition, Table 9 contains an analysis of the computation time. The approximation method is found to be very fast, compared to the Monte Carlo simulation..  

[Table 9 is about here.]  

# 6 Conclusion  

This paper derives semi-closed form pricing formulas for different interest rate derivatives. under stochastic volatility. It extends the Fong and Vasicek (1991) valuation formula as well as the Selby and Strickland (1995) methodology. The main contribution consists of deriving the moments generating function of the zero-coupon bond as a Frobenius series. This allows us to easily price options on zero-coupon bonds by inverting the characteristic function using the Gauss-Laguerre quadrature rule. The approach is then applied to the pricing of coupon bond options, swaptions,. interest rate caps, floors, and collars. The numerical analysis conducted shows that the combination of Frobenius series with the quadrature rules provides a very accurate and fast valuation of interest. rate derivatives. Although the approximation is developed only for the FV (1991) model, it can be easily adapted to any other affine term structure models with stochastic volatility..  

# Appendix: Technical details  

Appendix 1: Derivation of the moment generating function  

The moments generating function of $\ln P(T,\theta)$ under the forward measure $Q^{M}$ for $M=T$ or $\theta$ is given by  

$$
\begin{array}{r c l}{{^{H}[e^{\varphi\ln(P(T,\theta))}]}}&{{=}}&{{E_{t}^{Q M}[e^{-\varphi D(T,\theta)r_{T}+\varphi F(T,\theta)v_{T}+\varphi G(T,\theta)}]}}\ {{}}&{{=}}&{{\displaystyle\frac{1}{P(t,M)}E_{t}^{Q}[e^{-\int_{t}^{T}r_{s}d s}\times P(T,M)\times e^{-\varphi D(T,\theta)r_{T}+\varphi F(T,\theta)v_{T}+\varphi G(T,\theta)}]}}\ {{}}&{{}}&{{=}}&{{\displaystyle\frac{1}{P(t,M)}E_{t}^{Q}\left[\begin{array}{c}{{e^{-\int_{t}^{T}r_{s}d s}\times e^{-(\varphi D(T,\theta)+D(T,M))r_{T}}\times e^{(\varphi F(T,\theta)+F(T,M)}}}\ {{\times e^{(\varphi G(T,\theta)+G(T,M))}}}\end{array}\right.}}\ {{}}&{{=}}&{{\displaystyle\frac{1}{P(t,M)}E_{t}^{Q}[e^{-\int_{t}^{T}r_{s}d s}\times e^{-A_{0}r_{T}}\times e^{B_{0}v_{T}}\times e^{C_{0}}],}}\end{array}
$$  

where functions $A_{0}$ $B_{0}$ and $C_{0}$ are defined in equation (10).  

# Appendix 2: Derivation of the ODEs in equations (14)-(16)  

Using the Feynman-Kac theorem, the cross-moment generating function defined in equation (12) must solve the following PDE  

$$
\frac{^2P}{r^{2}}+\frac{1}{2}\xi^{2}v\frac{\partial^{2}P}{\partial v^{2}}+\rho\xi v\frac{\partial^{2}P}{\partial v\partial r}+(\alpha\bar{r}-\alpha r+\lambda v)\frac{\partial P}{\partial r}+(\gamma\bar{v}-(\gamma+\xi\eta)v)\frac{\partial P}{\partial v}-\psi r P=\frac{\partial P}{\partial\pi}
$$  

with the boundary condition. $P(\tau=0,\psi,\varphi,\omega)=e^{-\varphi r-\omega v}$ . Assume the following functional form: $P(\tau,\psi,\varphi,\omega)=e^{-A(\tau)r+B(\tau)v+C(\tau)}$ , as in (13). By taking derivatives and substituting the derivatives into the above PDE, we can easily show that functions $A$ $B$ and $C$ must solve the ODEs in equations (14)-(16).  

# Appendix 3: Derivation of the Frobenius series solution  

Define $U(\tau)=\exp[-{\textstyle{\frac{1}{2}}}\xi^{2}\int_{0}^{\tau}B(s)d s]$ . Substituting the definition of. $U(\tau)$ into the ODE in (15), it is easy to see that. $U$ must solve the following second-order linear ODE  

$$
{\cal U}^{\prime\prime}+(\rho\xi A+\xi\eta+\gamma){\cal U}^{\prime}-\frac{\xi^{2}}{2}(\lambda A-\frac{1}{2}A^{2}){\cal U}=0,
$$  

with $U(0)=1$ and $\begin{array}{r}{U^{\prime}(0)=\frac{\xi^{2}}{2}\omega}\end{array}$ . Now consider the function $S(z)=z^{-\beta}U(\tau)$ where $z=e^{-\alpha\tau}$ , it  

can be shown that $S$ solves the following homogeneous second-order ODE  

$$
z S^{\prime\prime}+(\overline{{{\alpha}}}+\overline{{{\beta}}}z)S^{\prime}+(\overline{{{\gamma}}}+\overline{{{\delta}}}z)S=0,
$$  

with $S(1)=1$ and $\begin{array}{r}{S^{\prime}(1)=-\beta-\frac{\xi^{2}}{2\alpha}\omega}\end{array}$ , and where  

$$
\begin{array}{r l}{\bar{\alpha}}&{={}2\beta-\kappa+1,}\ {\bar{\beta}}&{={}\frac{\rho\xi}{\alpha^{2}}(\psi-\alpha\varphi),}\ {\bar{\beta}}&{{}={}\frac{\xi^{2}}{4\alpha^{4}}(\psi-\alpha\varphi)^{2},}\ {\bar{\gamma}}&{{}={}\left(\frac{\rho\xi\beta}{\alpha^{2}}-\frac{\xi^{2}}{\alpha^{4}}(\psi-\alpha\lambda)\right)(\psi-\alpha\varphi),}\ {\kappa}&{{}={}\frac{\xi\eta+\gamma}{\alpha}+\frac{\rho\xi}{\alpha^{2}}\psi,}\ {\kappa_{1}}&{{}={}\frac{\xi^{2}\psi}{2\alpha^{3}}(\frac{\psi}{2\alpha}-\lambda),}\ {\mathrm{and}\beta}&{{}={}\frac{\hat{\kappa}}{2}-\frac{1}{2}\sqrt{\kappa^{2}-4\kappa_{1}}.}\end{array}
$$  

Assume the following Frobenius series $S(z;\varepsilon)=z^{\varepsilon}\sum_{n=0}^{+\infty}q_{n}z^{n}$ as a solution to the homogeneous ODE in (A.4) above. It can be shown that $\varepsilon=0$ or $\varepsilon=1-\overline{{\alpha}}$ . Moreover, the coefficients $\left(q_{n}\right)$ are given recursively by  

$$
\begin{array}{r c l}{{q_{1}}}&{{=}}&{{\displaystyle\frac{-(\overline{{{\gamma}}}+\overline{{{\beta}}}\varepsilon)q_{0}}{(1+\varepsilon)(\varepsilon+\overline{{{\alpha}}})},}}\ {{q_{n}}}&{{=}}&{{\displaystyle\frac{-\overline{{{\delta}}}q_{n-2}-(\overline{{{\gamma}}}+\overline{{{\beta}}}(n-1+\varepsilon))q_{n-1}}{(n+\varepsilon)(n-1+\varepsilon+\overline{{{\alpha}}})}\quad\mathrm{~}f o r~n\geq2,}}\end{array}
$$  

where $q_{0}$ is any arbitrary constant. The general solution to function $S$ can then be written as. $S(z)=a S(z;0)+b S(z;1-\overline{{\alpha}})$ where  

$$
\begin{array}{r c l}{{b}}&{{=}}&{{\displaystyle\frac{S^{\prime}(1;0)-S^{\prime}(1)S(1;0)}{S(1;1-\overline{{{\alpha}}})S^{\prime}(1;0)-S^{\prime}(1;1-\overline{{{\alpha}}})S(1;0)},}}\ {{a}}&{{=}}&{{\displaystyle\frac{1-b S(1;1-\overline{{{\alpha}}})}{S(1;0)}.}}\end{array}
$$  

# References  

[1] Ball, C.A. and W.N. Torous, 1999. The stochastic volatility of short-term interest rates: some international evidence. Journal of Finance, 54 (6), 2339-2359.   
[2] Chacko, G. and S. Das, 2002. Pricing interest rate derivatives: a general approach. Review of Financial Studies, 15 (1), 195-241.   
[3] Clewlow, L. and C. Strickland, 1997. Monte Carlo valuation of interest rate derivatives under stochastic volatility. Journal of Fixed Income, December, 35-45.   
[4] Cox, J.C., Ingersoll, J.E. Jr., and S.A. Ross, 1985. A theory of the term structure of interest rates. Econometrica, 53 (2), 385-407.   
[5] Dai, Q. and K.J. Singleton, 2000. Specification analysis of affine term structure models. Journal of Finance, 55 (5), 1943-1978..   
[6] Fong, H.G. and O.A. Vasicek, 1991. Fixed-income volatility management. Journal of Portfolio Management, Summer, 41-46.   
[7] Geman, H., Karoui, N.E., and J.-C. Rochet, 1995. Changes of Numeraire, Changes of Probability Measure and Option Pricing. Journal of Applied Probability, 32, 443-458.   
[8] Heath, D., Jarrow, R., and A. Morton, 1992. Bond pricing and the term structure of interest rates: a new methodology, Econometrica, 60 (1), 77-105.   
[9] Heston, S.L., 1993. A closed-form solution for options with stochastic volatility with applica tions to bond and currency options. Review of Financial Studies, 6 (2), 327-343.   
10] Ho, T.S.Y. and S. Lee, 1986. Term structure movements and pricing interest rate contingent claims. Journal of Finance, 41, 1011-1029.   
11] Hull, J. and A. White, 1990. Pricing interest rate derivative securities. Review of Financial Studies, 3 (4), 573-592.   
[12] Jamshidian, F., 1989. An exact bond option formula. Journal of Finance, 44, 205-209.   
[13] Longstaff, F.A. and E. Schwartz, 1992. Interest rate volatility and the term structure: a two-. factor general equilibrium model. Journal of Finance, 48, 1259-1282.   
[14] Munk, C., 1999. Stochastic duration and fast coupon bond option pricing in multi-factor models. Review of Derivatives Research, 3 (2), 157-181.   
[15] Selby, M.J.P. and C. Strickland, 1995. Computing the Fong and Vasicek pure discount bond price formula. Journal of Fixed Income, September, 78-84.   
[16] Singleton, K.J. and L. Umantsev, 2002. Pricing coupon-bond options and swaptions in affine term structure models. Mathematical Finance, 12 (4), 427-446.   
[17] Sullivan, M.A., 2o00. Valuing American put options using Gaussian quadrature. Review of Financial Studies, 13, 75-94.   
[18] Sullivan, M.A., 2001. Discrete-time continuous-state interest rate models. Journal of Economic Dynamics and Control, 25, 1001-1017.   
[19] Tahani, N., 2004. Valuing credit derivatives using Gaussian quadrature: a stochastic volatility framework. Journal of Futures Markets, 24 (1), 3-35.   
[20] Vasicek, O.A., 1977. An equilibrium characterization of the term structure. Journal of Financial Economics, 5, 177-188.   
[21] Wei, J.Z., 1997. A simple approach to bond option pricing. Journal of Futures Markets, 17 (2), 131-160.  

![](7a80d8e567553b62aa6dfa408c9446fca26e8ca77ba3582e53679edff2254ef4.jpg)  
Figure 1: Weekly 3-Month U.S. T-Bill Rates  

![](2284fafa6e95f7f252e87de80bdf0b1161376a69d3ba5979ccacda9aa7ea7511.jpg)  
Figure 2: First Order Changes of Weekly 3-Month U.S. T-Bill Rates  

![](c21df9bb730295481b4e091bdaff4bef0822aab7200f798b72056fd93a754893.jpg)  
Figure 3: Term Structure of Interest Rates - Normal Curve  

![](1dddf2b5e77ba7aa0350165f9a898554dcf6edc2a1bf9ad8580b0a306a35d5ab.jpg)  
Figure 4: Term Structure of Interest Rates - Inverted Curve  

![](38cbd21058558d5615bac33f35b2f1ae4b80710ef8624a03ba832ff2748cd647.jpg)  
Figure 5: Term Structure of Interest Rates - Hump-Shaped Curve  

Table 1: Summary Statistics of the Interest Rate Series   


<html><body><table><tr><td></td><td>Min</td><td>1Q</td><td>Median</td><td>3Q</td><td>Max</td></tr><tr><td>3-MonthUST-Bill</td><td>0.58</td><td>3.15</td><td>4.94</td><td>6.45</td><td>16.76</td></tr><tr><td>First order change</td><td>-1.82</td><td>-0.05</td><td>0.00</td><td>0.06</td><td>1.92</td></tr><tr><td></td><td>Mean</td><td>Std.Dev.</td><td>Skewness</td><td>Kurtosis</td><td></td></tr><tr><td>3-MonthUST-Bill</td><td>5.175</td><td>2.808</td><td>1.104</td><td>4.828</td><td></td></tr><tr><td>First order change</td><td>0.001</td><td>0.200</td><td>-0.681</td><td>25.761</td><td></td></tr></table></body></html>  

Table 2: Zero-coupon Call option in the Vasicek (1977) Model   


<html><body><table><tr><td>Order</td><td>Price</td><td>Abs. Error</td></tr><tr><td>10</td><td>1.434E-02</td><td>3.36E-04</td></tr><tr><td>11</td><td>1.450E-02</td><td>1.68E-04</td></tr><tr><td>12</td><td>1.459E-02</td><td>7.91E-05</td></tr><tr><td>13</td><td>1.464E-02</td><td>3.47E-05</td></tr><tr><td>14</td><td>1.466E-02</td><td>1.41E-05</td></tr><tr><td>15</td><td>1.467E-02</td><td>5.35E-06</td></tr><tr><td>16</td><td>1.467E-02</td><td>1.85E-06</td></tr><tr><td>17</td><td>1.467E-02</td><td>5.65E-07</td></tr><tr><td>18</td><td>1.467E-02</td><td>1.90E-07</td></tr><tr><td>19</td><td>1.467E-02</td><td>3.98E-08</td></tr><tr><td>20</td><td>1.467E-02</td><td>1.67E-10</td></tr><tr><td>21</td><td>1.467E-02</td><td>1.55E-09</td></tr><tr><td>22</td><td>1.467E-02</td><td>8.44E-09</td></tr><tr><td>23</td><td>1.467E-02</td><td>5.58E-09</td></tr><tr><td>24</td><td>1.467E-02</td><td>8.19E-09</td></tr><tr><td>25</td><td>1.467E-02</td><td>1.65E-08</td></tr><tr><td>26</td><td>1.467E-02</td><td>1.12E-10</td></tr><tr><td>27</td><td>1.467E-02</td><td>1.05E-07</td></tr><tr><td>28</td><td>1.467E-02</td><td>6.63E-08</td></tr><tr><td>29</td><td>1.467E-02</td><td>5.40E-07</td></tr><tr><td>30</td><td>1.467E-02</td><td>5.06E-07</td></tr><tr><td>True Price</td><td>1.467E-02</td><td></td></tr></table></body></html>  

Table 3: Zero-coupon Call option in the FV (1991) Model   


<html><body><table><tr><td>Order</td><td>Price</td><td>Abs. Error</td></tr><tr><td>10</td><td>7.497E-03</td><td>3.00E-03</td></tr><tr><td>11</td><td>8.006E-03</td><td>2.49E-03 2.04E-03</td></tr><tr><td>12</td><td>8.452E-03</td><td>1.66E-03</td></tr><tr><td>13</td><td>8.836E-03</td><td></td></tr><tr><td>14</td><td>9.163E-03</td><td>1.33E-03</td></tr><tr><td>15</td><td>9.436E-03</td><td>1.06E-03</td></tr><tr><td>16</td><td>9.662E-03</td><td>8.31E-04</td></tr><tr><td>17</td><td>9.845E-03</td><td>6.47E-04 5.00E-04</td></tr><tr><td>18</td><td>9.992E-03</td><td>3.84E-04</td></tr><tr><td>19</td><td>1.011E-02</td><td>2.93E-04</td></tr><tr><td>20</td><td>1.020E-02</td><td>2.24E-04</td></tr><tr><td>21</td><td>1.027E-02</td><td>1.72E-04</td></tr><tr><td>22</td><td>1.032E-02</td><td></td></tr><tr><td>23</td><td>1.036E-02</td><td>1.33E-04</td></tr><tr><td>24</td><td>1.039E-02</td><td>1.04E-04 8.35E-05</td></tr><tr><td>25</td><td>1.041E-02</td><td></td></tr><tr><td>26</td><td>1.042E-02</td><td>6.88E-05 5.84E-05</td></tr><tr><td>27</td><td>1.043E-02</td><td>5.15E-05</td></tr><tr><td>28</td><td>1.044E-02</td><td>4.59E-05</td></tr><tr><td>29</td><td>1.045E-02</td><td>4.35E-05</td></tr><tr><td>30 MC Price</td><td>1.045E-02 1.049E-02</td><td></td></tr><tr><td>Std. Dev.</td><td>5.111E-05</td><td></td></tr></table></body></html>  

Table 4: Zero-coupon Call option in the FV (1991) Model   


<html><body><table><tr><td>Order</td><td>Price</td><td>Abs. Error</td></tr><tr><td>10</td><td>4.958E-03</td><td>1.97E-03</td></tr><tr><td>11</td><td>5.294E-03</td><td>1.64E-03</td></tr><tr><td>12</td><td>5.588E-03</td><td>1.34E-03</td></tr><tr><td>13</td><td>5.841E-03</td><td>1.09E-03</td></tr><tr><td>14</td><td>6.057E-03</td><td>8.73E-04</td></tr><tr><td>15</td><td>6.237E-03</td><td>6.93E-04</td></tr><tr><td>16</td><td>6.386E-03</td><td>5.44E-04</td></tr><tr><td>17</td><td>6.506E-03</td><td>4.23E-04</td></tr><tr><td>18</td><td>6.603E-03</td><td>3.27E-04</td></tr><tr><td>19</td><td>6.679E-03</td><td>2.50E-04</td></tr><tr><td>20</td><td>6.739E-03</td><td>1.91E-04</td></tr><tr><td>21</td><td>6.784E-03</td><td>1.45E-04</td></tr><tr><td>22</td><td>6.819E-03</td><td>1.11E-04</td></tr><tr><td>23</td><td>6.844E-03</td><td>8.55E-05</td></tr><tr><td>24</td><td>6.863E-03</td><td>6.68E-05</td></tr><tr><td>25</td><td>6.876E-03</td><td>5.33E-05</td></tr><tr><td>26</td><td>6.886E-03</td><td>4.37E-05</td></tr><tr><td>27</td><td>6.893E-03</td><td>3.69E-05</td></tr><tr><td>28</td><td>6.897E-03</td><td>3.24E-05</td></tr><tr><td>29</td><td>6.901E-03</td><td>2.88E-05</td></tr><tr><td>30</td><td>6.902E-03</td><td>2.72E-05</td></tr><tr><td>MC Price Std. Dev.</td><td>6.930E-03 3.351E-05</td><td></td></tr></table></body></html>  

Table 5: Coupon Bond Call option in the Vasicek (1977) Model   


<html><body><table><tr><td>Order</td><td>Price</td><td>Abs. Error</td></tr><tr><td>20</td><td>7.330784E-02</td><td>5.15E-06</td></tr><tr><td>21</td><td>7.330785E-02</td><td>5.17E-06</td></tr><tr><td>22</td><td>7.330789E-02</td><td>5.20E-06</td></tr><tr><td>23</td><td>7.330790E-02</td><td>5.21E-06</td></tr><tr><td>24</td><td>7.330791E-02</td><td>5.22E-06</td></tr><tr><td>25</td><td>7.330786E-02</td><td>5.18E-06</td></tr><tr><td>26</td><td>7.330787E-02</td><td>5.19E-06</td></tr><tr><td>27</td><td>7.330794E-02</td><td>5.25E-06</td></tr><tr><td>28</td><td>7.330784E-02</td><td>5.16E-06</td></tr><tr><td>29</td><td>7.330778E-02</td><td>5.09E-06</td></tr><tr><td>30</td><td>7.330759E-02</td><td>4.90E-06</td></tr><tr><td>True Price</td><td>7.330269E-02</td><td></td></tr></table></body></html>  

Table 6: Coupon Bond Call option in the Vasicek (1977) Model   


<html><body><table><tr><td>Order</td><td>Price</td><td>Abs.Error</td></tr><tr><td>20</td><td>1.447702E-01</td><td>5.06E-07</td></tr><tr><td>21</td><td>1.447701E-01</td><td>3.76E-07</td></tr><tr><td>22</td><td>1.447700E-01</td><td>3.40E-07</td></tr><tr><td>23</td><td>1.447700E-01</td><td>3.55E-07</td></tr><tr><td>24</td><td>1.447701E-01</td><td>3.70E-07</td></tr><tr><td>25</td><td>1.447700E-01</td><td>3.35E-07</td></tr><tr><td>26</td><td>1.447700E-01</td><td>3.31E-07</td></tr><tr><td>27</td><td>1.447699E-01</td><td>1.63E-07</td></tr><tr><td>28</td><td>1.447702E-01</td><td>4.60E-07</td></tr><tr><td>29</td><td>1.447694E-01</td><td>3.29E-07</td></tr><tr><td>30</td><td>1.447713E-01</td><td>1.59E-06</td></tr><tr><td>True Price</td><td>1.447697E-01</td><td></td></tr></table></body></html>  

Table 7: Coupon Bond Call option in the FV (1991) Model   


<html><body><table><tr><td>Order</td><td>Price</td><td>Abs. Error</td></tr><tr><td>20</td><td>7.229855E-02</td><td>3.42E-04</td></tr><tr><td>21</td><td>7.242059E-02</td><td>2.20E-04</td></tr><tr><td>22</td><td>7.251866E-02</td><td>1.22E-04</td></tr><tr><td>23</td><td>7.258585E-02</td><td>5.43E-05</td></tr><tr><td>24</td><td>7.262409E-02</td><td>1.61E-05</td></tr><tr><td>25</td><td>7.263997E-02</td><td>2.04E-07</td></tr><tr><td>26</td><td>7.264134E-02</td><td>1.17E-06</td></tr><tr><td>27</td><td>7.263545E-02</td><td>4.73E-06</td></tr><tr><td>28</td><td>7.262645E-02</td><td>1.37E-05</td></tr><tr><td>29</td><td>7.261896E-02</td><td>2.12E-05</td></tr><tr><td>30</td><td>7.261076E-02</td><td>2.94E-05</td></tr><tr><td>MC Price</td><td>7.264017E-02</td><td></td></tr><tr><td>Std. Dev.</td><td>8.627500E-05</td><td></td></tr></table></body></html>  

Table 8: Coupon Bond Call option in the FV (1991) Model   


<html><body><table><tr><td>Order</td><td>Price</td><td>Abs. Error</td></tr><tr><td>20</td><td>1.101486E-01</td><td>3.47E-04</td></tr><tr><td>21</td><td>1.099426E-01</td><td>1.41E-04</td></tr><tr><td>22</td><td>1.098145E-01</td><td>1.31E-05</td></tr><tr><td>23</td><td>1.097687E-01</td><td>3.27E-05</td></tr><tr><td>24</td><td>1.097814E-01</td><td>2.00E-05</td></tr><tr><td>25</td><td>1.098209E-01</td><td>1.95E-05</td></tr><tr><td>26</td><td>1.098617E-01</td><td>6.04E-05</td></tr><tr><td>27</td><td>1.098897E-01</td><td>8.83E-05</td></tr><tr><td>28</td><td>1.099033E-01</td><td>1.02E-04</td></tr><tr><td>29</td><td>1.099024E-01</td><td>1.01E-04</td></tr><tr><td>30</td><td>1.099024E-01</td><td>1.01E-04</td></tr><tr><td>MC Price</td><td>1.098014E-01</td><td></td></tr><tr><td>Std. Dev.</td><td>8.814900E-05</td><td></td></tr></table></body></html>  

Table 9: Computation Time   


<html><body><table><tr><td>Method</td><td>Computation Time</td></tr><tr><td>Monte Carlo</td><td>692 sec</td></tr><tr><td>Approximation</td><td>0.753 s sec</td></tr></table></body></html>  