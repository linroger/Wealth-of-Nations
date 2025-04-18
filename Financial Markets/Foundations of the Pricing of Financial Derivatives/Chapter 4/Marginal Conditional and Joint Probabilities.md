---
tags:
  - conditional_probability
  - joint_probability
  - marginal_probability
  - probability
  - statistics
aliases:
  - Probability Concepts
  - Unconditional Probability
key_concepts:
  - Conditional probability definition
  - Joint probability definition
  - Marginal probability definition
  - Probability of brown hair
  - Probability with two coins
---

# 4.1 MARGINAL, CONDITIONAL, AND JOINT PROBABILITIES

Probability is a measure, meaning a numerical description or quantification, of the relative. frequency of an event. The probability of observing heads in one toss of a fair coin is obviously 1/2. There are two possibilities and one fits the definition of the desired event.. Technically this concept is called the marginal probability, which distinguishes it from the conditional probability, which is the probability that something will happen, given that. something else has already happened. Finally, we have the concept of joint probability,. which is the probability that two or more events will happen..

To illustrate these concepts, consider the following information. A sample of 100 peo-. ple, 55 female and 45 male, is collected and examined for the frequency of brown hair. Of the 55 females, 31 have brown hair and 24 have some other color. Of the 45 males,. 28 have brown hair and 17 have some other color. If this is a reliable sample, what is the probability that a person selected at random will have brown hair? This is the unconditional probability, sometimes called the marginal probability, and it is 0.59, given that 59 out of 100 have brown hair. Note that we did not condition on whether the person is male or female.

Now suppose you know that you selected a male. Then what would be the probability. that the subject has brown hair? This concept is the conditional probability, specifically. the probability that the subject would have brown hair, given that it is a male. Then the answer would be $28/45=0.62$ because $62\%$ of the males have brown hair..

Now suppose you selected someone at random and you wanted to know the probability that it would be a female with a hair color other than brown. Out of 100 subjects, 24 are females with a hair color other than brown. So, on that basis alone, we know that the joint probability would be 0.24. The joint probability is equal to the conditional probability times the marginal probability of the condition. In our example this means that we want the probability that the subject will be a female with a hair color other than brown and this will be the probability that the subject will be female, given that you know the subject does not have brown hair, times the probability that the subject does not have brown hair. The probability that the subject will be female, given that we know that the subject does not have brown hair is 24/41 because there are 41 people with a hair color other than brown and 24 are female. This is the conditional probability. The probability that. the subject does not have brown hair is 41/100 because you know that out of 100 people, 41 do not have brown hair. This is the marginal probability. Multiplying the conditional. probability times the marginal probability gives us $(24/41)(41/100)=24/100$

Alternatively, we could have found the conditional probability that the subject will not have brown hair given that we know it is a female, which will be 24/55, times the. probability that the subject is female, 55/100, giving us the correct answer of 24/100.

Now, let us consider another simple event, such as the probability of a head on one. toss of a coin being 1/2. Now suppose we toss two coins. What is the probability of a. head? Now we have to define more precisely what we mean. Do we mean one head, two heads, or at least one head? We also have to be assured that the coins are independent,. for if not, it does affect our answer. Let us focus on the probability of exactly one head. Assuming the two coins are independent, consider the probability of one head as restricted to the probability that we toss a head on coin one and a tail on coin two, which is (1/2) $(1/2)=1/4$ . This is what we mean by the joint probability with independent events. There. are two ways to toss one head, however: a head on the first and a tail on the second or a tail on the first and a head on the second. So, the probability of exactly one head is really $1/4+1/4=1/2$ . If we want the probability of two heads, then we must toss a head on. both coins. Because the events are independent, the joint probability is the product of the marginal probabilities. Thus, the probability of two heads is. $(1/2)(1/2)=1/4.$ If we want the probability of at least one head, we require the probability of exactly one head plus the probability of two heads, which is $1/2+1/4=3/4.$ Interestingly, there is another way of solving the "at least one" case. Its probability is one minus the probability of no heads. The probability of no heads is. $(1/2)(1/2)=1/4.$ . So, the probability of at least one head is. $1-1/4=3/4.$

We can easily verify these results by summarizing all possible outcomes:

Head on first coin, head on second coin Head on first coin, tail on second coin Tail on first coin, head on second coin Tail on first coin, tail on second coin

These are equally likely events so each has a probability of $1/4$ The outcome of one head is represented by the second and third events so the probability is. $1/4+1/4=1/2.$ For two heads, there is just one way to do it, the first event. So that probability is 1/4. If we want. the probability of at least one head, we include the first three events, so that probability is $1/4+1/4+1/4=3/4$ . Alternatively, the probability of at least one head can be restated as 1 minus the probability of no heads. There is only one event here with no heads, the fourth event, so the answer is $1-1/4=3/4$ or alternatively, 1 - the probability of a tail on both tosses, which is $1-1/4=3/4$

The probability of two events occurring, as noted, is called the joint probability. Defining the events as $A$ and $B$ and denoting probability as $\mathrm{Pr},$ we state the joint probability for. independent events in the following manner:.

$\operatorname*{Pr}(A{\mathrm{~and~}}B)=\operatorname*{Pr}(A)\operatorname*{Pr}(B).$ given independence of $A$ and $B$

For events that are dependent, we must make some modifications. First, let us ask what we mean by independence and dependence. The coin tosses are clearly independent. The outcome of one coin is unrelated to the outcome of the other. We can, however, map the coin tosses into values that are not independent. Consider the following experiment. Toss a coin one time. If heads occur, record the value $+1$ ; if tails occurs, record the value. $-1$ Then toss the coin again. Once again record $+1$ or $-1$ and add it to the amount recorded. after the first coin toss. We are interested in the probabilities of the numerical outcomes. Here are the equally likely possibilities:

Head on first coin, head on second coin: $\mathrm{sum}=+2$ Head on first coin, tail on second coin: $\operatorname{sum}=0$ Tail on first coin, head on second coin: $\operatorname{sum}=0$ Tail on first coin, tail on second coin: sum $=-2$

Thus, the probability distribution is as follows:

<html><body><table><tr><td>Outcome</td><td>Probability</td></tr><tr><td>+2</td><td>1/4</td></tr><tr><td>0</td><td>1/2</td></tr><tr><td></td><td></td></tr><tr><td>-2</td><td>1/4</td></tr></table></body></html>

These are the marginal probabilities.2 We might also want to know the conditional probabilities. For example, we might wish to know the probabilities of. $+2,0$ and $^{-2}$ given that a head occurred on the first toss. These probabilities are as follows:.

<html><body><table><tr><td>Outcome</td><td>Probability3</td></tr><tr><td>+2</td><td>1/2</td></tr><tr><td>0</td><td>1/2</td></tr><tr><td></td><td></td></tr><tr><td>-2</td><td>0</td></tr></table></body></html>

If a tail occurs on the first toss, the probabilities are as follows:4

<html><body><table><tr><td>Outcome</td><td>Probability</td></tr><tr><td></td><td>0</td></tr><tr><td>+2</td><td></td></tr><tr><td>0</td><td>1/2</td></tr><tr><td>-2</td><td>1/2</td></tr></table></body></html>

The probabilities of. $+2$ and $^{-2}$ outcomes are quite different if a head or tail has occurred. on the first toss. This is what we mean by the conditional probability. The events, defined specifically as the sum of the. $+1$ or $-1$ assigned to the head or tail tossed, are not independent. The occurrence of a head or a tail, however, is independent from one toss to the other. It is interesting to note how the same sample experiment can give rise to a quite. different set of probabilities for different events..

In general, we have the following result, where $\acute{\mathcal{O}}$ denotes and:

$$
\operatorname*{Pr}(A\&B)=\operatorname*{Pr}(B|A)\operatorname*{Pr}(A)=\operatorname*{Pr}(A|B)\operatorname*{Pr}(B).
$$

Note that $\mathrm{Pr}(.)$ stands for the probability of the event(s) in the parentheses. When a vertical. line appears in parentheses it means conditional on the event following the vertical line.. To cast our event in this context, think of the two tosses as two coins, coin1 and coin2. The outcome of a. $+2$ can occur only in the joint condition that both coins come up heads.. The probability of this occurring is obtained from the conditional probabilities as follows: the probability of a head on the second coin conditional on a head on the first coin $(1/2)$ times the probability of a head on the first coin. $(1/2)$ . Alternatively, it is the probability of a head on the first coin conditional on a head on the second coin. $(1/_{2})$ times the probability of a head on the second coin. $(1/2)$ 5.

A probability distribution is a mathematical specification of the probabilities associated with events. For the examples shown, we easily laid out the probability distribution. Many types of random outcomes can be characterized with an exact mathematical formulation that gives either the probability of an event occurring or the probability of a range of events occurring. Coin tosses are outcomes from what is called a binomial probability distribution. This distribution is one of a family of distributions that are called discrete,. which means that only a finite number of outcomes can occur. Another family of distributions is referred to as continuous, meaning that the number of possible outcomes is infinite. Anything that can be measured with fractional precision is continuous. For example, the return on an asset is continuous. An asset bought at 99.75 and sold at 102.5 has a return of $2.757\dots\%$ . There are an infinite number of possible returns, provided the return is mea-. sured with decimal precision and not rounded off to a certain number of decimal places. One major example of a continuous distribution is the familiar normal or bell-shaped distribution.

Consider a random variable, $x.$ An expression such as. $\operatorname*{Pr}(x=a)$ , representing the prob-. ability that an outcome of $x$ is a value of. $^{a}$ , is one example of information revealed by a. discrete probability distribution. In some cases, we wish to know the cumulative probability, $\operatorname*{Pr}(x\leq a)$ . For example, consider the previous problem in which we wish to know.

the probability of achieving a specific total after two coin tosses where a head counts as $+1$ and a tail counts as $-1$ . Suppose we wish to know the probability that the total is nonnegative. Then we have $\operatorname*{Pr}(x\geq0)$ , which equals $\operatorname*{Pr}(x=0)+\operatorname*{Pr}(x=2)=1/2+1/4=3/4$ Alternatively, we could calculate using the complement,. $\operatorname*{Pr}(x\geq0)=1-\operatorname*{Pr}(x<0)=1-$ $\operatorname*{Pr}(x=-2)=1-1/4=3/4$ Note that it is not possible to obtain a total of $+1$ or $-1$ . The outcomes are either $+2$ , 0, or $^{-2}$

If a random variable is continuous, we cannot specify a probability in terms of a spe-. cific value. For example, in the standard normal distribution we cannot specify $\mathrm{Pr}(x=0)$ 6. Because there are an infinite number of outcomes, the probability of any one outcome occurring is zero. We can, however, specify the probability of a range of outcomes occurring. Statements like. $\operatorname*{Pr}(x>0)$ are quite acceptable.7 The answer is 0.5, owing to the symmetry of the distribution and the fact that its expected value is zero. Likewise, we can use statements like $\Pr(b<x<a)$ , which is easily found as. $\operatorname*{Pr}(x<a)-\operatorname*{Pr}(x<b)$

Because the probability of a specific value of the random variable occurring is zero in the continuous case, there is no mathematical specification that gives such results as $\operatorname*{Pr}(x=a)$ . There is, however, a mathematical specification that can lead to such statements as $\operatorname*{Pr}(x<a)$ . We start with a mathematical function referred to as the probability density function. If we plot such a function, specified as. $f(x)$ , we observe a graph of values of a. variable $f(x)$ in terms of the random variable $X$ . The specific value of $f(x)$ has no particular interpretation in a continuous distribution, but the area under the curve generated by $f(x)$ is the probability we seek. Thus, the area under the curve and to the left of a particular value $f(a)$ is $\operatorname*{Pr}(x<a)$ . Integrating the function, meaning to accumulate its values over a range of values of $x$ , gives us the desired probability. These concepts are discussed in more detail later in this chapter. Such a function is called the probability distribution function, or just the distribution function, and sometimes the cumulative density function.8

Probability distributions are often characterized not only with a density or distribution function but also with a moment-generating function. This is a mathematical specification that incorporates the density or distribution function and yields what are called the moments of the distribution. The $k^{t b}$ raw moment of a distribution is defined as $E\big(x^{k}\big)$ As we shall see in the next section, the first moment . $(k=1)$ is the expected value and the second moment $(k=2)$ is closely related to the variance. The third moment,. $E\big(x^{3}\big)$ , is closely related to the concept of skewness, which measures the symmetry of a probability distribution. The fourth moment, $E(x^{4})$ , is closely related to the concept of kurtosis,. which measures the extent to which a distribution is peaked or flat..

Not all probability distributions have a moment-generating function, but all have a characteristic function, which, although requiring use of complex numbers, can be used to yield many useful results. Characteristic functions and to some extent moment-generating functions are occasionally used in finance.

These paragraphs provide only a brief treatment but should be sufficient to refresh our memory of previous encounters with this material. In some cases, certain concepts are being encountered for the first time. The reader will in all likelihood be required to refer to more specific material to fill in gaps and extend knowledge. We now turn to the primary operations used with random variables in finance concepts, which are the determination of expectations, variances, and covariances.
