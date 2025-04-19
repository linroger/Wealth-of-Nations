---
tags:
  - '#independent_factors'
  - '#ito_lemma'
  - '#market_prices_of_risk'
  - '#numeraire'
  - '#risk_neutral_world'
  - '#uncorrelated_variables'
  - '#world_defined_by_numeraire'
---
# 28.5 EXTENSION TO SEVERAL FACTORS  

The results presented in Sections 28.3 and 28.4 can be extended to cover the situation when there are many independent factors.' Assume that there are. $n$ independent factors  

and that the processes for. $f$ and $g$ in the traditional risk-neutral world are  

$$
d f=r f d t+\sum_{i=1}^{n}\sigma_{f,i}f d z_{i}
$$  

and  

$$
d g=r g d t+\sum_{i=1}^{n}\sigma_{g,i}g d z_{i}
$$  

It follows from Section 28.2 that other internally consistent worlds can be defined by setting  

and  

$$
d f=\left[r+\sum_{i=1}^{n}\lambda_{i}\sigma_{f,i}\right]f d t+\sum_{i=1}^{n}\sigma_{f,i}f d z_{i}
$$  

$$
d g=\bigg[r+\sum_{i=1}^{n}\lambda_{i}\sigma_{g,i}\bigg]g d t+\sum_{i=1}^{n}\sigma_{g,i}g d z_{i}
$$  

where the $\lambda_{i}$ $_i\left(1\leq i\leq n\right)$ are the $n$ market prices of risk. One of these other worlds is the real world.  

We now extend our earlier terminology. A "world defined by numeraire. $g^{,}$ is a world where $\lambda_{i}=\sigma_{g,i}$ for all $i$ It can be shown from Ito's lemma, using the fact that the. $d z_{i}$ are uncorrelated, that the process followed by. $f/g$ in this world has zero drift (see Problem 28.12). The rest of the results in the last two sections (from equation (28.15) onward) are therefore still true.  
