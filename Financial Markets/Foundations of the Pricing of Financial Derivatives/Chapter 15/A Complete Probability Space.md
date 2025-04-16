---
tags:
  - '#adapted_process'
  - '#binomial_example'
  - '#complete_probability_space'
  - '#girsanov_theorem'
  - '#risk'
  - '#sigma_field'
  - '#stochastic_economy'
  - '#uncertainty'
---
# 15.3 A COMPLETE PROBABILITY SPACE

The complete probability space is a very formal mathematical representation of our per-. ceptions of the possible uncertain outcomes and their probabilities, such as the random movements in asset prices. In financial practice, one always faces uncertainty where both likelihood and outcome are unknown. In finance, uncertainty means we do not know. the potential outcomes and/or their corresponding likelihoods. Risk means we can assert both the potential outcomes and their corresponding likelihoods. Most quantitative tasks. seek to model uncertainty with some risk-based framework. With the complete probability space, uncertainty is reduced to risk, again where both likelihood and outcome are known. For a thorough treatment of this topic, see Harrison and Kreps (1979) and Harrison and. Pliska (1981).

Girsanov's theorem relies on a formal mathematical structure. Hence, we introduce. some of the formalities here. We assume a finite time horizon; that is, time is modeled as a real number over $(0,{\widehat{T}})$ , for fixed $0\leq t\leq\widehat{T}$ where $\widehat{T}<\infty$

The uncertainty is characterized by a complete probability space expressed as $(\itOmega,I,P)$ where the state space. $\varOmega$ is the set of all possible realizations of the stochastic economy between time O and time $\hat{T}$ and has a typical element $\omega$ representing a single sample path, $I$ is called the sigma field of distinguishable events denoted $I$ for information at time $\widehat{T}_{:}$ and $P$ is a probability measure defined on the elements of $I,P$ is short for $\mathrm{Pr}(x)$ A sigma field is a means of keeping track of what is known and unknown as illustrated next.

To illustrate a complete probability space, consider a three-period binomial example where each period is one year and the likelihood of an up move is $60\%$ . Thus, the state space can be represented as:

$$
\Omega=\left\{\begin{array}{l}{\emptyset,\{d\},\{u\},\{d,d\},\{d,u\},\{u,d\},\{u,u\},\{d,d,d\},\{d,d,u\},\{d,d,u\},}\ {\{d,u,d\},\{d,u,u\},\{u,d,d\},\{u,d,d\},\{u,d,u\},\{d,u,u\}}\end{array}\right\},
$$

where $\varnothing$ represents the null set. The initial time period, 0, in this illustration is ${\hat{T}}-3$ For example, one element of the state space is $\boldsymbol{\omega}=\{u,d,u\}$ . The sigma field of distinguishable.

events, $I.$ keeps track of the information along the complete past sample path, where the percentages in parentheses here are probabilities:

<html><body><table><tr><td>t=0 Io=</td><td colspan="2">O,{d}, {u}, {d,d}, {d,u}, {u,d}, {u,u}, {d,d,d}, {d,d,u}, {d,u,d}, {d,u,u}, (100%) {u,d,d},{u,d,u}, {u,u,d}, {u,u,u}</td></tr><tr><td>t=1:</td><td>{d}, {d,d}, {d,u}, {d,d,d}, {d,d,u}, {d,u,d}, {d,u,u}</td><td>(40%) {u},{u,d}, {u,u},{u,d,d},</td></tr><tr><td>t=2:</td><td>1o I2 ={{dd},{ddd},{ddu}} (16%)</td><td>(60%) {u,d,u}, {u,u,d},{u,u,u} I2={{du},{dud},{duu}}(24%)</td></tr><tr><td>t=3:</td><td>I2={{ud},{udd}, {udu}} (24%) I2={{uu},{uud},{uuu}} (36%)</td><td></td></tr><tr><td rowspan="6"></td><td>={{d,d,d}} (6.4%)</td><td></td></tr><tr><td>13 ={{d,d,u}} (9.6%)</td><td></td></tr><tr><td>I3 = {{d,u,d}} (9.6%)</td><td></td></tr><tr><td></td><td>I3 ={{d,u,u}} (14.4%)</td></tr><tr><td>I3 = {{u,d,d}} (9.6%)</td><td></td></tr><tr><td></td><td>I3 ={{u,d,u}} (14.4%)</td></tr><tr><td></td><td></td></tr><tr><td></td><td>I3 ={{u,u,d}} (14.4%)</td></tr><tr><td></td><td>I3 ={{u,u,u}} (21.6%)</td></tr><tr><td></td><td></td></tr></table></body></html>

An adapted process on a complete probability space is non-anticipating. Generally, process $x$ is said to be adapted if and only if for every outcome. $x_{t},x_{t}$ is known at time $t.$ Ito processes are adapted processes.

There are several other highly technical assumptions, but we leave them for further. study in the mentioned references. With this foundation, we are now ready for a formal statement of Girsanov's theorem.
