---
aliases:
- Alias_197_Math Notes.md
- Alias_196_Math Notes.md
tags:
- tag_example
title: Math Notes
---



# Math Notes

**Calculus and Statistics Primer for PhD Level Finance**

**1. Calculus**

**1.1. Differentiation**

**1.1.1. Basic Concepts**

- **Derivative Definition**: The derivative of a function  at a point  is defined as:

**1.1.2. Differentiation Rules**

- **Power Rule**:
- **Constant Multiple Rule**:
- **Sum Rule**:
- **Difference Rule**:
- **Product Rule**:
- **Quotient Rule**:
- **Chain Rule**:
- **Implicit Differentiation**: If a function is defined implicitly by an equation involving  and ,  differentiate both sides with respect to  and solve for .
- **Higher-Order Derivatives**: The -th derivative of a function  is denoted by  and is obtained by differentiating   times.

**1.1.3. Derivatives of Special Functions**

- **Exponential Functions**:
- **Logarithmic Functions**:
- **Trigonometric Functions**:
- **Inverse Trigonometric Functions**:
- **Hyperbolic Functions**:

**1.1.4. Special Differentiation Techniques**

- **Logarithmic Differentiation**: Used when differentiating functions of the form :

Differentiate both sides and solve for .

**1.2. Integration**

**1.2.1. Basic Concepts**

- **Indefinite Integral**: The antiderivative of a function  is another function  such that:

where  is the constant of integration.

- **Definite Integral**:

**1.2.2. Integration Rules**

- **Power Rule for Integration**:
- **Constant Multiple Rule**:
- **Sum and Difference Rules**:

**1.2.3. Integration Techniques**

- **Substitution Method**: Let ,  then:
- **Integration by Parts**:
- **Partial Fractions**: Decompose a rational function into simpler fractions before integrating.

**1.2.4. Integrals of Special Functions**

- **Exponential Functions**:
- **Logarithmic Functions**:
- **Trigonometric Functions**:
- **Inverse Trigonometric Functions**:

**1.2.5. Improper Integrals**

- **Definition**: Integrals with infinite limits or integrands with infinite discontinuities.

**1.3. Multivariable Calculus**

**1.3.1. Partial Derivatives**

- **Definition**: The derivative of a multivariable function with respect to one variable,  holding others constant.

\[

\frac{\partial f}{\partial x} = \lim_{h \to 0} \frac{f(x + h,  y,  z,  \dots) - f(x,  y,  z,  \dots)}{h}

\]

**1.3.2. Gradient,  Divergence,  and Curl**

- **Gradient (Vector of Partial Derivatives)**:
- **Divergence**:
- **Curl**:

**1.3.3. Multiple Integrals**

- **Double Integrals**:
- **Triple Integrals**:

**2. Statistics**

**2.1. Probability Theory**

**2.1.1. Basic Concepts**

- **Sample Space ()**: The set of all possible outcomes.
- **Event**: A subset of the sample space.
- **Probability of an Event**:

**2.1.2. Axioms of Probability**

- **Non-negativity**:
- **Normalization**:
- **Additivity**:

\[

\text{If } E_1,  E_2,  \dots \text{ are mutually exclusive,  then } P\left( \bigcup_{i} E_i \right) = \sum_{i} P(E_i)

\]

**2.1.3. Conditional Probability**

- **Definition**:

**2.1.4. Independence**

- **Definition**: Events  and  are independent if:

**2.1.5. Bayes’ Theorem**

- **Formula**:

**2.2. Random Variables**

**2.2.1. Definitions**

- **Random Variable**: A function that assigns a real number to each outcome in the sample space.
- **Discrete Random Variable**: Takes on countable values.
- **Continuous Random Variable**: Takes on values in an interval or collection of intervals.

**2.2.2. Probability Functions**

- **Probability Mass Function (PMF)** for discrete random variables:
- **Probability Density Function (PDF)** for continuous random variables:
- **Cumulative Distribution Function (CDF)**:

**2.3. Expectation and Variance**

**2.3.1. Expectation (Mean)**

- **Discrete Random Variables**:
- **Continuous Random Variables**:

**2.3.2. Variance**

- **Definition**:

**2.3.3. Properties**

- **Linearity of Expectation**:
- **Variance of a Linear Function**:

**2.3.4. Covariance and Correlation**

- **Covariance**:
- **Correlation Coefficient**:

**2.4. Moment Generating Functions**

- **Definition**:
- **Properties**:
- The -th moment of  is obtained by differentiating   times and evaluating at :

**2.5. Common Probability Distributions**

**2.5.1. Discrete Distributions**

- **Bernoulli Distribution**:
- PMF:
- Mean: 
- Variance: 
- **Binomial Distribution**:
- PMF:

\[

p_X(k) = \binom{n}{k} p^k (1 - p)^{n - k},  \quad k = 0,  1,  \dots,  n

\]

- Mean: 
- Variance: 
- **Poisson Distribution**:
- PMF:

\[

p_X(k) = \frac{\lambda^k e^{-\lambda}}{k!},  \quad k = 0,  1,  2,  \dots

\]

- Mean and Variance: 

**2.5.2. Continuous Distributions**

- **Uniform Distribution**:
- PDF:
- Mean: 
- Variance: 
- **Normal Distribution**:
- PDF:
- Mean: 
- Variance: 
- **Exponential Distribution**:
- PDF:
- Mean: 
- Variance: 
- **Gamma Distribution**:
- PDF:
- Mean: 
- Variance: 
- **Beta Distribution**:
- PDF:
- Mean: 
- Variance: 

**2.5.3. Multivariate Distributions**

- **Joint Distribution**: The probability distribution of two or more random variables.
- Joint PDF for continuous variables  and :
- **Marginal Distribution**:
- For variable :
- **Conditional Distribution**:
- For  given :
- **Multivariate Normal Distribution**:
- Joint PDF:
- Mean Vector: 
- Covariance Matrix: 

**2.6. Limit Theorems**

**2.6.1. Law of Large Numbers**

- **Weak Law**: For i.i.d. random variables \( X_1,  X_2,  \dots,  X_n \) with :

\[

\bar{X}n = \frac{1}{n} \sum{i=1}^{n} X_i \xrightarrow{P} \mu \text{ as } n \to \infty

\]

- **Strong Law**:

\[

\bar{X}_n \xrightarrow{a.s.} \mu \text{ as } n \to \infty

\]

**2.6.2. Central Limit Theorem**

- **Statement**: For i.i.d. random variables  with mean  and variance :

\[

\frac{\bar{X}_n - \mu}{\sigma / \sqrt{n}} \xrightarrow{d} N(0,  1) \text{ as } n \to \infty

\]

**2.7. Statistical Inference**

**2.7.1. Estimation**

- **Point Estimation**: Estimating a parameter  by a single value .
- **Properties of Estimators**:
- **Unbiasedness**: 
- **Consistency**: \( \hat{\theta} \xrightarrow{P} \theta \) as 
- **Efficiency**: Estimator with the smallest variance among all unbiased estimators.

**2.7.2. Interval Estimation**

- **Confidence Interval**: An interval  such that:

**2.7.3. Hypothesis Testing**

- **Null Hypothesis ()**: The default assumption.
- **Alternative Hypothesis ()**: Contradicts .
- **Test Statistic**: A function of the sample data used to decide whether to reject .
- **P-value**: The probability of observing a test statistic as extreme as,  or more extreme than,  the observed value under .
- **Decision Rule**: Reject  if the p-value is less than the significance level .

**2.8. Regression Analysis**

**2.8.1. Simple Linear Regression**

- **Model**:

where  is the error term.

- **Least Squares Estimators**:

**2.8.2. Multiple Regression**

- **Model**:

\[

Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \dots + \beta_k X_k + \varepsilon

\]

- **Matrix Form**:

\[

\mathbf{Y} = \mathbf{X} \boldsymbol{\beta} + \boldsymbol{\varepsilon}

\]

- **Least Squares Estimator**:

\[

\hat{\boldsymbol{\beta}} = (\mathbf{X}^\top \mathbf{X})^{-1} \mathbf{X}^\top \mathbf{Y}

\]

This primer provides a comprehensive overview of essential calculus and statistics concepts relevant to PhD-level finance courses. It covers fundamental rules,  definitions,  and equations necessary for advanced financial analysis and modeling.