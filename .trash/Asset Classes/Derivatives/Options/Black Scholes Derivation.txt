---
Owner: RRoger Lin
aliases:
- Alias_258_Black Scholes Derivation.md
- Alias_261_Black Scholes Derivation.md
tags:
- Options
- tag_example
---


# BLACK SCHOLES DERIVATION

The Black-Scholes equation is a partial differential equation, which describes the price of the option over time. The equation is:

$$
\frac{\partial V}{\partial t} + \frac{1}{2}\sigma^2S^2\frac{\partial^2 V}{\partial S^2} + rS\frac{\partial V}{\partial S} - rV = 0
$$

Where:

+ (V) is the price of the option.
+ (t) is the time to expiration.
+ (S) is the price of the underlying asset.
+ (\sigma) is the volatility of the underlying asset.
+ (r) is the risk-free interest rate.

The Black-Scholes formula for a European call option is given by:

$[C(S, t) = SN(d_1) - Ke^{-rt}N(d_2)]$

For a put option, it is given by:

$[P(S, t) = Ke^{-rt}N(-d_2) - SN(-d_1)]$

Where:

+ (N(\cdot)) is the cumulative distribution function of the standard normal distribution.
+ (K) is the strike price of the option.

$(d_1 = \frac{\ln(\frac{S}{K}) + (r + \frac{\sigma^2}{2})(T-t)}{\sigma\sqrt{T-t}})$

$(d_2 = d_1 - \sigma\sqrt{T-t})$

Now, let's derive the Black-Scholes formula step by step:

1. **Non-dimensionalizing the Black-Scholes PDE**

	 To simplify the Black-Scholes PDE, we introduce dimensionless variables:

$[x = \ln\left(\frac{S}{K}\right)]$

$[\tau = \frac{1}{2}\sigma^2(T-t)]$

$[\bar{V}(x,\tau) = \frac{V(S,t)}{K}]$

	 Substituting these into the Black-Scholes PDE, we get a transformed PDE for$(\bar{V})$﻿.

2. **Applying the transformation**

	 By applying the chain rule, we can transform the derivatives of (V) with respect to (S) and (t) into derivatives of (\bar{V}) with respect to (x) and (\tau). The transformed PDE becomes:

$[\frac{\partial \bar{V}}{\partial \tau} = \frac{\partial^2 \bar{V}}{\partial x^2} + \left(k - 1\right)\frac{\partial \bar{V}}{\partial x} - k\bar{V}]$

	 where$(k = \frac{2r}{\sigma^2})$﻿.

3. **Solving the transformed PDE**

	 We look for a solution of the form$(\bar{V}(x,\tau) = e^{ax + b\tau} \Phi(x,\tau))$﻿ where$(\Phi)$﻿ satisfies the heat equation:

$[\frac{\partial \Phi}{\partial \tau} = \frac{\partial^2 \Phi}{\partial x^2}]$

	 We choose (a) and (b) to eliminate the first derivative term and the zeroth derivative term in (\tau). This gives us:

$[a = \frac{1}{2}(k - 1)]$

$[b = \frac{1}{2}a^2]$

	 With these choices, (\Phi) indeed satisfies the heat equation.

4. **Boundary conditions**

	 We apply the boundary conditions to (\Phi) that correspond to the payoff of the option at expiration. For a call option, this is:

$[\bar{V}(x,0) = \max(e^x - 1, 0)]$

	 For a put option, it would be:

$[\bar{V}(x,0) = \max(1 - e^x, 0)]$

5. **Solving the heat equation**

	 The solution to the heat equation with the above boundary conditions can be found using the method of images or Fourier transform methods. The solution is given by:

$[\Phi(x,\tau) = e^{-a^2\tau - ax}\int_{-\infty}^{x} \frac{e^{-\frac{(y-x)^2}{2\tau}}}{\sqrt{2\pi\tau}}\max(e^y - 1, 0) dy]$

6. **Back to the original variables**

	 We then transform back to the original variables ((S, t)) and (V) using the relationships between (x, \tau) and (S, t), as well as (\bar{V}) and (V). The final Black-Scholes formula for a call option is:

$[C(S, t) = SN(d_1) - Ke^{-rt}N(d_2)]$

	 And similarly for a put option.

7. **Deriving (d_1) and (d_2)**

	 The terms (d_1) and (d_2) come from the solution of the integral in the previous step. When we work through the integration and apply the boundary conditions, we end up with these terms, which represent the probabilities that the option will finish in the money, adjusted for the present value.

	 To derive the terms (d_1) and (d_2) in the Black-Scholes formula, we first need to solve the integral that arises from the solution to the heat equation, which has been transformed back to the option pricing context. Let's start from the point where we have the solution to the heat equation and transform back to the original variables.

	 We have the solution to the transformed PDE as:

$[\Phi(x,\tau) = e^{-a^2\tau - ax}\int_{-\infty}^{x} \frac{e^{-\frac{(y-x)^2}{2\tau}}}{\sqrt{2\pi\tau}}\max(e^y - 1, 0) dy]$

	 This represents the option price at the transformed variables. We need to convert this back to the original variables ((S, t)) and (V). Recall that

$(x = \ln\left(\frac{S}{K}\right))$

	 and

$(\tau = \frac{1}{2}\sigma^2(T-t))$

	 Also,

$(a = \frac{1}{2}(k - 1))$

	 and

$(k = \frac{2r}{\sigma^2})$

	 which gives us

$(a = \frac{r}{\sigma^2} - \frac{1}{2}).$

	 Now, we need to evaluate the integral. For a call option, the payoff at expiry is ((S - K)^+), which is the max of (S - K) or 0. In terms of our transformed variables, this is (\max(e^x - 1, 0)). The integral becomes:

$[\int_{-\infty}^{x} \frac{e^{-\frac{(y-x)^2}{2\tau}}}{\sqrt{2\pi\tau}}(e^y - 1) dy]$

	 This integral can be split into two parts:

$[\int_{-\infty}^{x} \frac{e^{-\frac{(y-x)^2}{2\tau}}}{\sqrt{2\pi\tau}}e^y dy - \int_{-\infty}^{x} \frac{e^{-\frac{(y-x)^2}{2\tau}}}{\sqrt{2\pi\tau}} dy]$

	 The first integral evaluates to the cumulative normal distribution function of (d_1), and the second integral evaluates to the cumulative normal distribution function of (d_2).

	 Let's derive (d_1) and (d_2):

	 The integral that gives us (N(d_1)) is:

$[e^{x + \frac{\tau}{2}}N\left(\frac{x}{\sqrt{\tau}} + \sqrt{\tau}\right)]$

	 Substituting back (x) and (\tau) with the original variables, we get:

$[S N\left(\frac{\ln(S/K) + (r + \frac{\sigma^2}{2})(T-t)}{\sigma\sqrt{T-t}}\right)]$

	 This is (SN(d_1)). Thus, we have:

$[d_1 = \frac{\ln(S/K) + (r + \frac{\sigma^2}{2})(T-t)}{\sigma\sqrt{T-t}}]$

	 For (d_2), we have:

$[N\left(\frac{x}{\sqrt{\tau}}\right)]$

	 Substituting back (x) and (\tau) with the original variables, we get:

$[N\left(\frac{\ln(S/K) + (r - \frac{\sigma^2}{2})(T-t)}{\sigma\sqrt{T-t}}\right)]$

	 This is$(Ke^{-rt}N(d_2)).$﻿ Thus, we have:

$[d_2 = \frac{\ln(S/K) + (r - \frac{\sigma^2}{2})(T-t)}{\sigma\sqrt{T-t}}]$

	 But we can also express (d_2) in terms of (d_1):

$[d_2 = d_1 - \sigma\sqrt{T-t}]$

	 These are the (d_1) and (d_2) terms in the Black-Scholes formula, representing the standardized moves of the log of the stock price (under the risk-neutral measure) from (t) to (T), adjusted for the present value. The terms (N(d_1)) and (N(d_2)) represent the probabilities that the option will expire in-the-money under the risk-neutral measure, adjusted to the present value.

### **APPLYING THE FEYNMAN-KAC FORMULA TO SOLVE THE BLACK-SCHOLES PDE**

    1. **Black-Scholes PDE**:  
        The Black-Scholes PDE for a European call option is given by:
    
	$\frac{\partial C}{\partial t} + rS \frac{\partial C}{\partial S} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 C}{\partial S^2} - rC = 0$
	 
    1. **Transformation of Variables**:  
        Transform the PDE using new variables:
    
	$\tau = T - t, \quad C(S, t) = u(S, T - t)$
	 
    The PDE becomes:
    

  $$$
  -\frac{\partial u}{\partial \tau} + rS \frac{\partial u}{\partial S} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 u}{\partial S^2} - ru = 0
  $$$

    1. **Expectation Representation**:  
        The Feynman-Kac formula represents the solution as:
    
	$$
	u(S, \tau) = e^{-r\tau} \mathbb{E}^{\mathbb{Q}}[ \max(S_T - K, 0) | S_\tau = S ]
	$$
	 
    1. **Risk-Neutral Valuation**:  
        Under the risk-neutral measure QQ, the stock price dynamics are:
    
	$dS = rS dt + \sigma S dW^{\mathbb{Q}}(t)$
	 
    1. **Solution of the SDE under** **Q****Q**:  
        The SDE solution is:
        
       $S_T = S e^{(r - \frac{1}{2} \sigma^2) \tau + \sigma \sqrt{\tau} Z}$
        
    2. where _Z_ is a standard normal random variable.
        
    3. **Expected Payoff**:  
        The expected payoff calculation involves:
    4. where ϕ(z)is the standard normal density.
        
    
	$\mathbb{E}^{\mathbb{Q}}[\max(S_T - K, 0)] = \int_{-\infty}^{\infty} \max(S e^{(r - \frac{1}{2} \sigma^2) \tau + \sigma \sqrt{\tau} z} - K, 0) \phi(z) dz$
	 
    1. **Integration**:  
        This integral is solved by considering the region where ST>K
    2. **Change of Variables**:  
        Introduce d1_d_1 and d2_d_2:
    
	$d_1 = \frac{\ln(\frac{S}{K}) + (r + \frac{1}{2} \sigma^2) \tau}{\sigma \sqrt{\tau}}, \quad d_2 = d_1 - \sigma \sqrt{\tau}$
	 
    1. **Final Integration**:  
        The final Black-Scholes formula is obtained by evaluating the integrals:
        
       $C(S, t) = S N(d_1) - K e^{-r\tau} N(d_2)$
        

where N(⋅)_N_(⋅) denotes the cumulative distribution function of the standard normal distribution

-----

## INTRODUCTION

The Black-Scholes model is a mathematical model for the dynamics of a financial market containing derivative investment instruments. Here, we focus on the Black-Scholes equation for pricing European call options, which allows us to derive a closed-form solution known as the Black-Scholes formula.

Let's start by listing and defining the variables involved in the Black-Scholes equation:

+ The current price of the underlying asset (e.g., stock).$S$
+ The strike price of the option. ﻿:$K$
+ The time to maturity of the option (in years).$T$
+ The risk-free interest rate, continuously compounded.$r$﻿:
+ The volatility of the underlying asset's returns, which is considered constant.$\sigma$﻿:
+ The price of a European call option as a function of the underlying asset's price and time.$C(S, t)$﻿:
﻿- The current time, with$t=0﻿$being the valuation date and$T$﻿ being the maturity date of the option.$t$

## ASSUMPTIONS

The Black-Scholes model makes several key assumptions:

1. The stock price follows geometric Brownian motion with constant drift and volatility.
2. There are no dividends paid during the life of the European option.
3. European options can only be exercised at expiration.
4. No transaction costs or taxes, and the risk-free rate is constant.
5. The markets are efficient, meaning that prices reflect all known information.
6. Investors can borrow and lend unlimited amounts at the risk-free rate.
7. The risk preferences of investors do not affect the option price.

## THE BLACK-SCHOLES PARTIAL DIFFERENTIAL EQUATION (PDE)

The Black-Scholes PDE describes the change in the option price,$C$, over time and stock price. It is given by:

$$
\frac{\partial C}{\partial t} + \frac{1}{2}\sigma^2S^2\frac{\partial^2 C}{\partial S^2} + rS\frac{\partial C}{\partial S} - rC = 0
$$

## DERIVATION OF BLACK-SCHOLES FORMULA

To derive the Black-Scholes option pricing formula from the PDE, we will use the following steps along with the necessary boundary conditions.

### STEP 1: TRANSFORM VARIABLES

We will perform a change of variables to transform the PDE into the heat equation, which we know how to solve. Define:

$$
x = \ln(S)
$$

$$
\tau = T - t
$$

$$
v(x, \tau) = e^{\alpha x + \beta \tau}C(S, t)
$$

where$\alpha$and$\beta$are to be determined.

Applying the chain rule, we can derive the following relationships:

$$
\frac{\partial C}{\partial S} = e^{-\alpha x - \beta \tau} \frac{\partial v}{\partial x}
$$

$$
\frac{\partial^2 C}{\partial S^2} = e^{-\alpha x - \beta \tau} \left( \frac{\partial^2 v}{\partial x^2} - \alpha \frac{\partial v}{\partial x} \right)
$$

$$
\frac{\partial C}{\partial t} = -e^{-\alpha x - \beta \tau} \frac{\partial v}{\partial \tau}
$$

By substituting these into the original PDE, we can derive a PDE for$$
By substituting these into the original PDE, we can derive a PDE forv(x, \tau)
By substituting these into the original PDE, we can derive a PDE for$$

### STEP 2: SIMPLIFY PDE FOR$$
### STEP 2: SIMPLIFY PDE FORV(X, \TAU)
### STEP 2: SIMPLIFY PDE FOR$$﻿

After substitution and simplification, we obtain:$$
After substitution and simplification, we obtain: -e^{-\alpha x - \beta \tau} \frac{\partial v}{\partial \tau} + \frac{1}{2}\sigma^2 e^{-\alpha x - \beta \tau} \left(\frac{\partial^2 v}{\partial x^2} - \alpha \frac{\partial v}{\partial x} \right) + re^{-\alpha x - \beta \tau} \frac{\partial v}{\partial x} - re^{-\alpha x - \beta \tau} v = 0

After substitution and simplification, we obtain:$

$To remove the$v$terms not involving derivatives, choose$\alpha$﻿ and$\beta$﻿ such that:$$

After substitution and simplification, we obtain:$

$-e^{-\alpha x - \beta \tau} \frac{\partial v}{\partial \tau} + \frac{1}{2}\sigma^2 e^{-\alpha x - \beta \tau} \left(\frac{\partial^2 v}{\partial x^2} - \alpha \frac{\partial v}{\partial x} \right) + re^{-\alpha x - \beta \tau} \frac{\partial v}{\partial x} - re^{-\alpha x - \beta \tau} v = 0$$To remove the$v$terms not involving derivatives, choose$\alpha$﻿ and$\beta$﻿ such that: \alpha = -\frac{1}{2} \left(\frac{2r}{\sigma^2} + 1 \right)

After substitution and simplification, we obtain:$

$-e^{-\alpha x - \beta \tau} \frac{\partial v}{\partial \tau} + \frac{1}{2}\sigma^2 e^{-\alpha x - \beta \tau} \left(\frac{\partial^2 v}{\partial x^2} - \alpha \frac{\partial v}{\partial x} \right) + re^{-\alpha x - \beta \tau} \frac{\partial v}{\partial x} - re^{-\alpha x - \beta \tau} v = 0$$To remove the$v$terms not involving derivatives, choose$\alpha$﻿ and$\beta$﻿ such that:$$

$$
\beta = -\frac{1}{2} \left( \frac{2r}{\sigma^2} - 1 \right)^2
$$

After substituting$\alpha$and$\beta$and simplifying, we get the heat equation:

$$
\frac{\partial v}{\partial \tau} = \frac{1}{2}\sigma^2 \frac{\partial^2 v}{\partial x^2}
$$

### STEP 3: SOLVE THE HEAT EQUATION

The heat equation can be solved using Fourier transforms, but we will skip to the resulting general solution for the purpose of these notes:

$$
v(x, \tau) = \int_{-\infty}^{\infty} G(x-y,\tau) \phi(y)dy
$$

where G﻿ is the Green’s function of the heat equation and$\phi$is the payoff function at terminal time$\tau = 0$

For a call option, the terminal payoff is$$
For a call option, the terminal payoff is \phi(y) = \max(e^y - K, 0)
For a call option, the terminal payoff is$$

### STEP 4: APPLY THE BOUNDARY CONDITION

The final step is to evaluate the integral at time

$$
v(x,0) = e^x - K
$$

where$v(x, 0)$﻿ is the initial condition representing the payoff of the call option at expiry.

Substitute$v(x, 0)$into$v(x, \tau)$and use the boundary conditions to evaluate the integral. We can simplify this using standard results for normally distributed variables.

### FINAL RESULT: THE BLACK-SCHOLES FORMULA

Through the above steps, we ultimately arrive at the Black-Scholes formula for a European call option:

$$
C(S, t) = SN(d_1) - Ke^{-r(T-t)}N(d_2)
$$

where

$$
d_1 = \frac{\ln(\frac{S}{K}) + \left(r + \frac{\sigma^2}{2}\right)(T-t)}{\sigma\sqrt{T-t}}
$$

$$
d_2 = d_1 - \sigma\sqrt{T-t}
$$

and$$
andN(d)
and$$

﻿ is the cumulative distribution function of the standard normal distribution.

This concludes the derivation of the Black-Scholes option pricing formula. It is important to understand each step in the process contributes to the final result and is based upon the key assumptions and mathematical properties underlying the model. Through this derivation, we developed an essential tool to aid investors and traders in pricing European-style call options.

Please note that this document provides an overview and omits certain detailed mathematical steps for brevity. For a full, rigorous derivation, each operation must be justified and executed with mathematical precision, usually in a more advanced mathematical finance class or textbook.

---

Starting with the Black-Scholes PDE (which, for clarity, I'll restate):

$$
[\frac{\partial C}{\partial t} + rS\frac{\partial C}{\partial S} + \frac{1}{2}\sigma^2 S^2 \frac{\partial^2 C}{\partial S^2} - rC = 0 \tag{1}]
$$

Using the following transformations:$$
Using the following transformations: v(x, \tau) = e^{-r\tau}C(S,t) \tag{5}$$$$x = \ln\left(\frac{S}{K}\right) \tag{3}$$$$\tau = T - t \tag{4}
Using the following transformations:$$

We'll convert the derivatives in the Black-Scholes PDE to the new variables (x) and (\tau).

The transformed first and second partial derivatives with respect to (S) are:$$
The transformed first and second partial derivatives with respect to (S) are: \frac{\partial C}{\partial S} = \frac{\partial C}{\partial x} \frac{\partial x}{\partial S} = \frac{1}{S} \frac{\partial v}{\partial x} e^{r\tau} \tag{6}
The transformed first and second partial derivatives with respect to (S) are:$$

$$$\frac{\partial^2 C}{\partial S^2} = \frac{\partial}{\partial S}\left(\frac{1}{S} \frac{\partial v}{\partial x} e^{r\tau}\right) = \frac{1}{S^2} \left(\frac{\partial^2 v}{\partial x^2} - \frac{\partial v}{\partial x}\right) e^{r\tau} \tag{7}$$

For the time derivative we get:$$
For the time derivative we get:[\frac{\partial C}{\partial t} = -\frac{\partial v}{\partial \tau} e^{-r\tau} \tag{8}]
For the time derivative we get:$$

Now we substitute the transformed derivatives (6), (7), and (8) into the original Black-Scholes PDE (1), and because this substitution and simplification involve a number of steps, I'll break it down further:

The PDE (1) transforms into:$$
The PDE (1) transforms into:-r e^{-r\tau} v(x, \tau) - e^{-r\tau}\frac{\partial v}{\partial \tau} + r e^{-r\tau} e^{r\tau} \frac{\partial v}{\partial x} + \frac{1}{2}\sigma^2 e^{-r\tau} e^{2r\tau} \left(\frac{\partial^2 v}{\partial x^2} - \frac{\partial v}{\partial x}\right) - r e^{-r\tau} v(x, \tau) = 0
The PDE (1) transforms into:$$

Notice that after cancellation of the exponential terms and rearrangement, the PDE becomes:$$
Notice that after cancellation of the exponential terms and rearrangement, the PDE becomes:[\frac{\partial v}{\partial \tau} = \frac{1}{2} \sigma^2 \frac{\partial^2 v}{\partial x^2} - \left(r + \frac{1}{2}\sigma^2\right) \frac{\partial v}{\partial x} + rv \tag{9}]
Notice that after cancellation of the exponential terms and rearrangement, the PDE becomes:$$

This PDE (9) is simpler than the original Black-Scholes PDE and is now in a form that can be solved more easily. You'll notice how the discount rate (r) has been factored into the PDE, reflecting the present value adjustment.

To solve PDE (9), boundary and final conditions need to be applied, which are:

+ Final condition for the call option (as ($\tau \rightarrow 0$)), reflecting the option payout at expiry:$$
+ Final condition for the call option (as ($\tau \rightarrow 0$)), reflecting the option payout at expiry: v(x,0) = e^{-r(T-t)} \max(e^xK - K, 0) = e^{-rT} \max(Ke^x - K, 0)
+ Final condition for the call option (as ($\tau \rightarrow 0$)), reflecting the option payout at expiry:$$
+ Boundary conditions when ($x \rightarrow \pm \infty$).

With the right techniques, one can solve the transformed PDE (9) subject to these conditions, possibly involving a series of methods such as Fourier transforms, method of characteristics, or similarity solutions depending on how the problem is approached. The goal is to solve for (v(x, \tau)), after which you can apply the inverse transformations to retrieve the original call option pricing formula (C(S,t)).

The final, derived Black-Scholes formula for a European call option is a solution to the PDE (1) when the appropriate boundary conditions are applied. The solution has the form:$$
The final, derived Black-Scholes formula for a European call option is a solution to the PDE (1) when the appropriate boundary conditions are applied. The solution has the form: [C(S, t) = S_0 N(d_1) - K e^{-r(T-t)}N(d_2)]
The final, derived Black-Scholes formula for a European call option is a solution to the PDE (1) when the appropriate boundary conditions are applied. The solution has the form:$$

where (N) is the cumulative distribution function of a standard normal random variable and ($d_1$) and ($d_2$) are given by:

$$
d_1 = \frac{\ln(S_0/K) + (r + \sigma^2/2)(T-t)}{\sigma \sqrt{T-t}}
$$

This formula assumes constant volatility and risk-free rates, and it requires market prices of the underlying asset to follow a log-normal distribution as per the geometric Brownian motion assumption.

---

**Black-Scholes Formula Derivation**

We start with just two assumptions:

+ 1) The underlying asset follows a lognormal random walk
+ 2) Arbitrage arguments allow us to use a risk-neural valuation approach (Cox-Rubinstein's proof is easiest here), discounting the expected payoff of the option at expiration by the riskless rate and assuming the underlying's return is the risk free rate

Derivation of Black-Scholes for a European call option **c** with strike **K**, discount rate **r**, on stock **S**, with time to maturity **t**, and expectations operator **E**.

Equation 1: The definition of a call option $$
Equation 1: The definition of a call option c = r^{-t} E\left[\max(0, S(t) - K) \right]
Equation 1: The definition of a call option$$

Equation 2: End of period stock price as a function of its return by definition, where R is the gross rate of return$$
Equation 2: End of period stock price as a function of its return by definition, where R is the gross rate of return s(t) = R \cdot S(0)
Equation 2: End of period stock price as a function of its return by definition, where R is the gross rate of return$$

Equation 3: rewriting eq(1) in integral form, where h() is the lognormal density function, and labeling S(0) as simply S, (note K and k are the same below)$$
Equation 3: rewriting eq(1) in integral form, where h() is the lognormal density function, and labeling S(0) as simply S, (note K and k are the same below) c = r^{-t} \int_{K/S}^{\infty} (SR - K)h(R) \, dR

Equation 3: rewriting eq(1) in integral form, where h() is the lognormal density function, and labeling S(0) as simply S, (note K and k are the same below)$

$Equation 4: substitute into R an exponential and its normal distribution, where f(u) is the normal density function with a mean of$\mu t = ln(r) - \frac{1}{2} \sigma^2$and volatility$\sigma \sqrt{t}$ $$

Equation 3: rewriting eq(1) in integral form, where h() is the lognormal density function, and labeling S(0) as simply S, (note K and k are the same below)$

$c = r^{-t} \int_{K/S}^{\infty} (SR - K)h(R) \, dR$$Equation 4: substitute into R an exponential and its normal distribution, where f(u) is the normal density function with a mean of$\mu t = ln(r) - \frac{1}{2} \sigma^2$and volatility$\sigma \sqrt{t}$  c = r^{-t} \int_{\ln(K/S)}^{\infty} (Se^u - K)f(u) \,du

Equation 3: rewriting eq(1) in integral form, where h() is the lognormal density function, and labeling S(0) as simply S, (note K and k are the same below)$

$c = r^{-t} \int_{K/S}^{\infty} (SR - K)h(R) \, dR$$Equation 4: substitute into R an exponential and its normal distribution, where f(u) is the normal density function with a mean of$\mu t = ln(r) - \frac{1}{2} \sigma^2$and volatility$\sigma \sqrt{t}$ $$

Equation 5: substituting for _u_ now using a change in variables to _z_ we have
Equation 5: substituting for _u_ now using a change in variables to z_ we have c = r^{-t} \int_{\frac{\ln(K/S) - \mu t}{\sigma \sqrt{t}}}^{\infty} (Se^{\mu t + z \sigma \sqrt{t}} - k)\phi(z) \, dz

Equation 5: substituting for _u_ now using a change in variables to _z_ we have$$Equation 6: rearranging$$

Equation 5: substituting for _u_ now using a change in variables to _z_ we have$$c = r^{-t} \int_{\frac{\ln(K/S) - \mu t}{\sigma \sqrt{t}}}^{\infty} (Se^{\mu t + z \sigma \sqrt{t}} - k)\phi(z) \, dz$$

Equation 6: rearranging c = Sr^{-t} \int_{\frac{\ln(K/S) - \mu t}{\sigma \sqrt{t}}}^{\infty} e^{\mu t + z \sigma \sqrt{t}} \phi(z) \, dz - kr^{-t} \int_{\frac{\ln(K/S) - \mu t}{\sigma \sqrt{t}}}^{\infty} \phi(z) \, dz

Equation 5: substituting for _u_ now using a change in variables to _z_ we have$$c = r^{-t} \int_{\frac{\ln(K/S) - \mu t}{\sigma \sqrt{t}}}^{\infty} (Se^{\mu t + z \sigma \sqrt{t}} - k)\phi(z) \, dz$$

Equation 6: rearranging$$
Equation 7: substitute _(ln(r)-  \frac{1}{2} σ^2) for μ_ and factor out _eln(r)t$$

Equation 7: substitute _(ln(r)- \frac{1}{2} σ^2) for μ_ and factor out _eln(r)tc = S \int_{\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} e^{-\frac{1}{2} \sigma^2 t + z \sigma \sqrt{t}} \phi(z) \, dz - Kr^{-t} \int_{\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} \phi(z) \, dz

Equation 7: substitute _(ln(r)- \frac{1}{2} σ^2) for μ_ and factor out _eln(r)t$$
Equation 8: multiply the normal density by the exponent$$

Equation 8: multiply the normal density by the exponent \begin{aligned}c&=S\int_{\frac{\ln\left(Kr^{-t}/S\right)+\sigma^2/_2\cdot t}{\sigma\sqrt{t}}}^{\infty}\frac{1}{\sqrt{2\pi}}e^{-1/2{z^2-1/2{\sigma^2t+z\sigma\sqrt{t}}}}dz-Kr^{-t}\int_{\frac{\ln\left(Kr^{-t}/S\right)+\sigma^2/2\cdot t}{\sigma\sqrt{t}}}^{\infty}\phi(z)dz\end{aligned}
Equation 8: multiply the normal density by the exponent$$Equation 9: factor exponent

$$
c = S \int_{\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} \, dz - Kr^{-t} \int_{\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} \phi(z) \, dz
$$

  Equation 10: make substitution$zhat=z-σ√t$

$$
c = S \int_{\frac{\ln(Kr^{-t} / S) - \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} \, dz - Kr^{-t} \int_{\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} \phi(z) \, dz
$$

Equation 11: rearrange integral bound

$$
c = S \int_{\frac{\ln(Kr^{-t} / S) - \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} \, dz - Kr^{-t} \int_{\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}}^{\infty} \phi(z) \, dz
$$

Equation 12: using the fact that$$
Equation 12: using the fact that \int_{a}^{\infty} e^{-x^2} \, dx = \int_{-\infty}^{-a} e^{-x^2} \, dx
Equation 12: using the fact that$$

we can switch and negate the integral bounds$$
we can switch and negate the integral bounds c = S \int_{-\infty}^{-\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}} \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} \, dz - Kr^{-t} \int_{-\infty}^{-\frac{\ln(Kr^{-t} / S) - \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}} \phi(z) \, dz
we can switch and negate the integral bounds$$

Equation 13: using algebra we then get$$
Equation 13: using algebra we then get c = S \int_{-\infty}^{-\frac{\ln(Kr^{-t} / S) + \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}} \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} \, dz - Kr^{-t} \int_{-\infty}^{-\frac{\ln(Kr^{-t} / S) - \sigma^2 / 2 \cdot t}{\sigma\sqrt{t}}} \phi(z) \, dz
Equation 13: using algebra we then get$$

 Equation 14: rewrite in Normal Cumulative Density notation to get the familiar Black-Scholes$$
 Equation 14: rewrite in Normal Cumulative Density notation to get the familiar Black-Scholes c = SN(d_1) - r^{-t} KN(d_1 - \sigma\sqrt{t})
 Equation 14: rewrite in Normal Cumulative Density notation to get the familiar Black-Scholes$$

 $$
d_1 = \frac{\ln(S_0/K) + (r + \sigma^2/2)(T-t)}{\sigma \sqrt{T-t}}

$$