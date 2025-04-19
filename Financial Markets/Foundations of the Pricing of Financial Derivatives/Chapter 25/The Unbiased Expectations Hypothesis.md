---
tags:
  - arbitrage
  - forward_price
  - risk_premium
  - spot_price
aliases:
  - Expectations Hypothesis
  - UEH
key_concepts:
  - Arbitrage opportunities
  - Cost of carry
  - Expected spot price
  - Forward price
  - Risk premium impact
---

# 25.1 THE UNBIASED EXPECTATIONS HYPOTHESIS

Let us start by defining $S_{0}$ and $F_{0}$ as the spot and forward prices for an asset.5 The forward price is for a forward contract that expires one period later and requires delivery of the underlying asset. In other words, one enters into a contract to purchase the asset one period later, paying the price $F_{0}$ , which is determined when the contract is created. Unless otherwise stated, we assume annual time increments, so time 1 occurs in 1 year. Thus, we can set aside compounding issues $(\tau=1$

Now let us move ahead to time 1, at which time the spot price is $S_{1}$ . To avoid the existence of any arbitrage opportunities, the forward price at expiration must converge to the spot price. Therefore,

$$
F_{1}=S_{1}.
$$

In a technical sense, the forward price. $F_{1}$ is the price of a contract expiring instantaneously.. Therefore, it has to be the spot price. That is, a forward contract calling for instantaneous. payment and delivery of the asset is a spot transaction, because a spot transaction calls for instantaneous payment and delivery of the asset..

At time 0, the expected spot price at time 1 is denoted as $E_{0}(S_{1})$ . As such, with $F_{1}=S_{1}$

$$
E_{0}(S_{1})=E_{0}(F_{1}).
$$

The unbiased expectations hypothesis states that the forward price is the expected spot price. Formally,

$$
F_{0}=E_{0}(S_{1}).
$$

Let us now see why this statement cannot be true. By definition, today's spot price of any asset is the expected future spot price minus the risk premium, with this

value discounted back to the present at the risk-free rate. Let us write this statement as follows:

$$
S_{0}=e^{-r_{c}}[E_{0}(S_{1})-\lambda],
$$

where $r_{c}$ is the one-period continuously compounded interest rate and $\lambda$ is the dollar risk premium. At this point, we do not specify what the risk premium is. For example, we do not. require that it derives from the capital asset pricing model. We simply define it in general terms. It is the amount in money by which the future asset price is reduced to induce some-. one to buy the asset. Equation (25.4) must hold because rational investors require ex ante. compensation for the opportunity cost of funds tied up in the risky asset as well as compensation for the assumption of risk. Also, note that the bracketed term is the risk-adjusted expected value at time 1, and it is, therefore, appropriate to discount this value for one. period at the risk-free rate. Equation (25.4) is what we call a certainty equivalent, because. it is the amount of money we would take for certain in lieu of facing a risk.

It is a well-known fact that to prevent arbitrage, a forward price must equal the spot price compounded at the risk-free interest rate. This is the basic cost of carry pricing model for a forward contract,6

$$
\begin{array}{r}{F_{0}=S_{0}e^{r_{c}}.}\end{array}
$$

As such, we can restate Equation (25.5) as

$$
S_{0}=F_{0}e^{-r_{c}}.
$$

Substituting Equation (25.6) into Equation (25.4) gives

$$
F_{0}=E_{0}(S_{1})-\lambda.
$$

In other words, the forward price is the expected spot price minus a risk premium. The existence of a positive risk premium makes the forward price a biased estimate of the expected spot price, thereby invalidating the unbiased expectations hypothesis. Note that the bias is on the low side, assuming a positive risk premium. That is, the forward price will understate the expected spot price by the amount of the risk premium.

For further proof, let us suppose that the forward price is unbiased. That is, assume Equation (25.3) holds. By definition, the spot price is the expected future spot price discounted at a risky rate, which we shall denote as $k$ . That is,

$$
S_{0}=E_{0}(S_{1})e^{-k}.
$$

If the unbiased expectations hypothesis were correct, then substitute Equation (25.3) into Equation (25.8), and we obtain the result that.

$$
S_{0}=F_{0}e^{-k}.
$$

But we know that to prevent arbitrage, Equation (25.5) must hold. This implies that $k=r_{c}$ That is, the rate at which a risky future value must be discounted would be the risk-free rate. Moreover, this statement would be true for any asset. So, if the unbiased expectations hypothesis were true, the risky discount rate would be the same for every asset and equal to the risk-free rate. Except in the uninteresting cases of no risk or investors being risk neutral, this statement obviously cannot be true.

As we now turn to forward interest rates, we will need slightly more precise notation because forward interest rates have a current date, the time until the interest rate period starts, and the time until the interest rate period ends. To refresh your memory, a forward contract is established at one point in time and fixes the rate on a spot transaction that begins at another point in time, accrues interest, and ends at a later point in time. Further, we distinguish between the forward price (uppercase. $F$ ) and the forward rates (lowercase $f$ ). We shall standardize things by using forward rates covering only one period but up to $j$ periods ahead. Thus, $f(t,t+j)$ denotes the continuously compounded one-period forward rate observed at time $t$ for a spot transaction that starts at time $t+j_{:}$ $r(t+j,t+j+1)$ denotes the continuously compounded single-period spot rate over the period $t+j$ to $t+j+1$ , and $H P R(t,t+1,j)$ denotes the continuously compounded holding period return over the period $t$ to $t+1$ for a $j$ -maturity bond.

Within the context of interest rates, the unbiased expectations hypothesis states that forward rates are unbiased predictors of future spot rates. If UEH holds, then the forward rate is the best estimate of expected future spot rates. Based on our notation, we have

$$
\mathrm{UEH:}~f(t,t+j)=E_{t}[r(t+j,t+j+1)];j=1,\ldots,n,
$$

where $f(t,t+j)$ denotes the continuously compounded one-period forward rate observed at time $t$ for a transaction that starts at time $t+j$ and $r(t+j,t+j+1)$ denotes the continuously compounded single period spot rate over the period $t+j$ to $t+j+1$ . See, for example, Lutz (1940), Culbertson (1957), Campbell and Shiller (1987), Engsted and Tanggaard (1994, 1995), and Lund (1993).
