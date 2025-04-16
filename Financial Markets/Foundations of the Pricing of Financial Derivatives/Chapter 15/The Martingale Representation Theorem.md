---
tags:
  - '#derivative_pricing'
  - '#dynamic_replication'
  - '#girsanov_theorem'
  - '#martingale_representation_theorem'
  - '#option_delta'
  - '#option_pricing'
  - '#risk_neutral_pricing'
  - '#stochastic_processes'
---
# 15.1 THE MARTINGALE REPRESENTATION THEOREM

In applying Girsanov's theorem, what we do is alter the probability distribution of the asset return such that it follows a stochastic process known as a martingale. A martingale is a process without a drift, that is, it has a zero price change.1 In that case, we can obtain the value today of the derivative by determining the expected future value of the derivative, where the expectation is arrived at by using the altered probability distribution. In doing it this way, we avoid the problem of having to solve a differential equation.

First, however, let us identify why we are doing this. One of the important results of mathematical finance is that any two stochastic processes that are both martingales can be related to each other via a simple transformation. For example, given one martingale, $x_{t}$ and another, $y_{t}$ , the relationship,

$$
y_{t}=y_{0}+\int_{0}^{t}\lambda_{j}d x_{j},
$$

represents one martingale in terms of the other. Accordingly, this specification is referred to as the martingale representation theorem. It is important to note, however, and often overlooked in the mathematical finance literature that these two processes cannot simply be any two martingales. They must be rationally connected as we explain next.

Suppose we consider $x$ and $y$ , which we specify to be two independent stochastic variables with expected returns of zero. The variable $x$ may be the stock price of a gas company in Warsaw, Poland, whereas $y$ might be the price of corn in Madison County, Iowa. There. is no amount of mathematical wizardry that can convert the price of a gas company in. Warsaw to the price of corn in Iowa, even though both may be martingales given the. probability distribution of states of the global economy. The martingale representation. theorem seems to say that these variables can be expressed in terms of each other, but what is missing can be easily seen by recalling the binomial model..

Suppose $x$ can go up to $x^{+}$ or down to $x^{-}$ . Now we want to model $y.$ Intuitively we might specify that $y$ can go up to $y^{+}$ or down to $y^{-}$ If we allow only two states of nature and jointly consider $x$ and $y$ in the same model, then whenever $x$ is $x^{+}$ $y$ is $y^{+}$ , and whenever $x$ is $x^{-}$ $y$ is $y^{-}$ . In that case, the variables $x$ and $y$ are perfectly related to each other. If you know the value of one, you know the value of the other. In a very loose sense. $x$ and $y$ can be thought of as perfectly correlated, though correlation is a specific and rather strong type. of relationship that does not have to hold to make this point. In our example, it is obvious that when the price of corn is up, the price of the Polish gas company can be up or down. There is probably little relation between our $x$ and $y$ . Furthermore, we do not require such an extreme example to make this point. The variable $x$ could be the price of Microsoft and $y$ is the price of Exxon. Though both share a common relationship as driven by general stock market movements, there is no way that we can completely determine the value of one from the other. So, if Microsoft and Exxon were martingales, we could not relate one to the other as the martingale representation theorem seems to suggest. Even two stocks in the same industry, such as Ford and General Motors, cannot be related by the martingale representation theorem.

But if $x$ is the price of Microsoft stock and $y$ is the price of a call option on Microsoft, we can connect the two, because the price of the latter is completely determined by the price of the former. In the binomial sense, we can easily see this point. The option payoff at expiration for a given outcome is completely identified by the underlying asset price in that outcome.2 Thus, the martingale representation theorem requires that one variable be completely determined by the other. Well, that was the binomial case, which applies in a discrete time world. In a continuous time world, Girsanov's theorem will provide the connection.

How we use the martingale representation theorem is in the following manner. If the price of an asset, as indicated by the $x$ variable, is a martingale, then by the described. transformation, we can turn it into the. $y$ variable, if $y$ is completely determined by. $x$ . If $y$ is the option on $x$ , then we have replicated. $y$ with $x$ . It should be apparent that. $\lambda$ is likely to represent a certain number of shares of. $x$ held to replicate $y$

Those who have studied option pricing theory from a financial economics perspective, however, may find this result a bit disconcerting because they know that one must hold bonds as well as shares to replicate an option. The martingale representation theorem gives us only the condition under which the uncertainty in $y$ can be captured by the uncertainty in $x$ More formally, if we differentiate $y_{t}$ with respect to $x_{t}$ from Equation (15.1) we obtain

$$
d y_{t}=\lambda_{t}d x_{t}.
$$

This is the result we need and the one that clearly indicates that the uncertainty in $y$ is driven by the uncertainty in $x$ . The bonds we must hold for replication introduce no element of. uncertainty.

So the martingale representation theorem tells us that we must find a stochastic process $\lambda_{t}$ such that we are holding just the right number of units of. $x$ . In addition, we must invest a certain amount in risk-free bonds such that we replicate $y$ . Formally,

$$
y_{t}=\lambda_{t}x_{t}+\theta_{t}B_{t},
$$

where $B_{t}$ is the value of the bonds, and which accrues value by the factor $e^{r_{c}d t}$ . Note that $\lambda$ and $\theta$ are variables. They are indexed by $t$ and are determined as the asset evolves along its stochastic paths. We need to know their values at $t$ 3 They change as we move through time, but they are completely determined once we know the new price of the asset. Financial economists know this as the dynamic nature of the option delta. Indeed delta is what we are currently designating as $\lambda_{t}$

Mathematical finance formally tells us that if the asset can be transformed into a mar-. tingale, we can find a stochastic process such that the asset can be transformed into another martingale that replicates the option. Once we have replicated the option, we can price it using the asset price, the number of units of the asset we hold, the investment in risk-free bonds, and the interest rate, and so on, or in other words, all known values. We can obtain the option value by finding the expectation of the future value of this process.

Now let us proceed to examine the mathematics of how derivative prices are found.. Our first step is to learn how to change the drift, that is, the expected return of a random variable.
