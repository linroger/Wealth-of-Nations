# Math Notes

# Derivatives and Their Rules

## Derivatives of Elementary Functions

### Power Function
- The **power function** is $f(x) = x^n$, where $n$ is any real number.
- Its derivative is given by the formula:
  $$f'(x) = nx^{n-1}$$

### Exponential Function
- The **exponential function** is $f(x) = e^x$.
- Its derivative is:
  $$f'(x) = e^x$$

### Logarithmic Function
- The **logarithmic function** is $f(x) = \ln(x)$, where $x > 0$.
- Its derivative is:
  $$f'(x) = \frac{1}{x}$$

### Trigonometric Functions
1. **Sine Function**:
   - $f(x) = \sin(x)$
   - Derivative:
     $$f'(x) = \cos(x)$$
2. **Cosine Function**:
   - $f(x) = \cos(x)$
   - Derivative:
     $$f'(x) = -\sin(x)$$
3. **Tangent Function**:
   - $f(x) = \tan(x)$
   - Derivative:
     $$f'(x) = \sec^2(x)$$

## Rules for Differentiation

### Sum/Difference Rule
- If $f(x)$ and $g(x)$ are differentiable functions, then the derivative of their sum/difference is given by:
  $$(f \pm g)'(x) = f'(x) \pm g'(x)$$

### Product Rule
- For two differentiable functions $f(x)$ and $g(x)$, the **product rule** is:
  $$(fg)'(x) = f'(x)g(x) + f(x)g'(x)$$

### Quotient Rule
- For differentiable functions $f(x)$ and $g(x)$, where $g(x) \neq 0$, the **quotient rule** is:
  $$\left( \frac{f}{g} \right)'(x) = \frac{f'(x)g(x) - f(x)g'(x)}{(g(x))^2}$$

### Chain Rule
- If a function $f$ can be written as $f(x) = h(g(x))$, where both $h$ and $g$ are differentiable, the **chain rule** states that:
  $$f'(x) = h'(g(x)) \cdot g'(x)$$

## Higher-Order Derivatives

- The **second derivative** of a function $f$ is the derivative of $f'(x)$, denoted as $f''(x)$.
- In general, the $n$-th derivative is denoted as $f^{(n)}(x)$.

## Examples

### Example 1: Derivative of a Power Function
- Find the derivative of $f(x) = x^5$.
  - Using the power rule:
    $$f'(x) = 5x^{4}$$

### Example 2: Product Rule Application
- Given $f(x) = x^2$ and $g(x) = \sin(x)$, find $(fg)'(x)$.
  - By the product rule:
    $$(fg)'(x) = f'(x)g(x) + f(x)g'(x)$$
  - Calculating:
    $$f'(x) = 2x, \quad g'(x) = \cos(x)$$
  - Therefore:
    $$(fg)'(x) = (2x)(\sin(x)) + (x^2)(\cos(x)) = 2x\sin(x) + x^2\cos(x)$$

### Example 3: Chain Rule Application
- Find the derivative of $f(x) = (\ln(x))^2$.
  - Let $h(u) = u^2$ and $g(x) = \ln(x)$, so $f(x) = h(g(x))$.
  - By the chain rule:
    $$f'(x) = h'(g(x)) \cdot g'(x)$$
  - Calculating:
    $$h'(u) = 2u, \quad g'(x) = \frac{1}{x}$$
  - Therefore:
    $$f'(x) = 2\ln(x) \cdot \frac{1}{x} = \frac{2\ln(x)}{x}$$

### Example 4: Quotient Rule Application
- Given $f(x) = \frac{\cos(x)}{x^2}$, find $f'(x)$.
  - Let $u(x) = \cos(x)$ and $v(x) = x^2$.
  - By the quotient rule:
    $$f'(x) = \frac{u'(x)v(x) - u(x)v'(x)}{(v(x))^2}$$
  - Calculating:
    $$u'(x) = -\sin(x), \quad v'(x) = 2x$$
  - Therefore:
    $$f'(x) = \frac{(-\sin(x)) \cdot (x^2) - (\cos(x)) \cdot (2x)}{(x^2)^2} = \frac{-x^2\sin(x) - 2x\cos(x)}{x^4}$$

If you need any further adjustments, or additional examples or elaboration, just let me know!