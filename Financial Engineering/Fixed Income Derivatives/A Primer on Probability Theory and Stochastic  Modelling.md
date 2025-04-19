---
tags:
  - markov_chain
  - probability_equations
  - stationary_distribution
  - stochastic_modelling
  - transition_probabilities
aliases:
  - Probability Primer
  - Stochastic Process Example
key_concepts:
  - Markov Chain Model
  - Random Process Steps
  - Stationary Distribution
  - System of Equations
  - Transition Probabilities
---

# A Primer on Probability Theory and Stochastic  Modelling  

# Markov Chain  

Suppose there are two urns.  John has one urn and Abdul has the other. The two urns each  contain   $n$   balls. Of the total of  $2n$   balls,  $n$   are red and  $n$   are black. At each step of a random  process, one of the balls in each urn (John’s and Abdul’s) is chosen at random and John and  Abdul then exchange these two balls. So, that each urn continues to contain  $n$   balls. Let the  1 state of the system be indexed by the number ,  $r_{:}$  , of red balls in John’s urn.  

Now, the transition probabilities for a Markov Chain model of this process is given by:  

If there are   $X_{i}$   red balls in John’s urn at step i,  

$P_{r,s}=P\big(X_{i+1}=s\big|X_{i}=r\big)\qquad\mathit{f o r\,r},\,s=O,\,I,\,...,\,n.$    Then  $P_{O,I}=1$    also P  $P_{n,n+I}\,=\,1$  

When  $X_{i}=r$  , John’s urn contains  $r$   red and   $(n{-}1)$   black, and Abdul’s ( n -1) red and  $r$    black.  

$P_{_{r,r+1}}=P\big({c h o o s e\,r e d\,i n\,R o d/s\,u r n}\big|X_{_{i}}=r\big).\,P\big({c h o o s e\,\,b l a c k\,i n\,A b u k a r/s\,u r n}\big|X_{_{i}}=r\big).$  =      $P_{r,r}=2{\bigg(}{\frac{r}{n}}{\bigg)}{\bigg(}1\!-\!{\frac{r}{n}}{\bigg)}\;\;\,b y\,s i m i l a r\,a r g u m e n t;\,a n d\,a l s o$     $P_{_{r,r+1}}=\left(1-{\frac{r}{n}}\right)^{2}\quad{\it o t h e r w i s e}\,P_{_{r,s}}=0$  

Now that we worked out an expression for transition probabilities, we can write a system of  equations that must be satisfied by the stationary distribution of this model.  

$$
\bar{\Pi}=\left[\Pi_{0},\Pi_{1},...,\Pi_{n}\right]
$$  

The probability   $\pi_{i}$     $\it{i s\,P\big(i\,r e d\,b a l l s\,i n\,R o d^{\prime}\!s\,u r n\big)}$  

Therefore,  

$$
\pi_{0}=\!\left({\frac{1}{n}}\right)^{2}\pi_{1};{\mathrm{~}}a n d{\mathrm{~}}\pi_{n}=\!\left({\frac{1}{n}}\right)^{2}\pi_{n-1}.
$$  
for   $\mathbf{r}=\mathbb{1},\mathbb{2},\mathbf{n}\mathbb{-}\mathbb{1}$  ,  

$$
\pi_{r}=P_{r-1,r}\pi_{r-1}+P_{r,r}\pi_{r}+P_{r+1,r}\pi_{r+1},
$$  

$\boldsymbol{\pi}_{r}=\!\left(\!1\!-\!\frac{r-\!1}{n}\!\right)^{2}\boldsymbol{\pi}_{r-1}+2\!\left(\!\frac{r}{n}\!\right)\!\!\left(1\!-\!\frac{r}{n}\!\right)\!\boldsymbol{\pi}_{r}+\!\left(\!\frac{r+\!1}{n}\!\right)^{2}\boldsymbol{\pi}_{r+1}.$  

Equations (A) and (B) define the process, with  $\mathrm{with}\sum_{r=0}^{n}\pi_{r}=1\,.$  .  

Example:  

Suppose  $\mathsf{n}=3$  , we can solve above equations in order to find  $\Pi_{1},\Pi_{2}$   and  $\Pi_{3}$   .  

From equation (A) we have  

$\pi_{0}=\frac{1}{9}\pi_{1}$   

  $\pi_{3}=\frac{1}{9}\pi_{2}$    and   $\pi_{0}+\pi_{1}+\pi_{2}+\pi_{3}=1$  

Also, from equation (B) we have  

$\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\$   

  $\frac{1}{9}\pi_{1}+\pi_{1}+\pi_{2}+\frac{1}{9}\pi_{2}=1=\frac{10}{9}\big(\pi_{1}+\pi_{2}\big),\ \,s o\,\pi_{1}+\pi_{2}=\frac{9}{10}.$  

Now use  

$$
\begin{array}{l}{\displaystyle\pi_{0}=\frac{1}{9}\pi_{1}}\\ {\displaystyle\pi_{2}=\frac{9}{10}-\pi_{1}}\\ {\displaystyle\pi_{3}=\frac{1}{10}\!-\!\frac{1}{9}\pi_{1}}\end{array}
$$  
# Therefore  

$\begin{array}{l}{{\displaystyle{\pi_{1}=\pi_{0}+\frac{4}{9}\pi_{1}+\frac{4}{9}\pi_{2}}}}\\ {{\displaystyle{\ }}}\\ {{\displaystyle{=\frac{1}{9}\pi_{1}+\frac{4}{9}\pi_{1}+\frac{4}{9}\bigg(\frac{9}{10}-\pi_{1}\bigg)\!=\!\frac{1}{9}\pi_{1}+\frac{2}{5}.}}}\end{array}$   
  $\therefore{\frac{8}{9}}\pi_{1}={\frac{2}{5}},$  or    ${\begin{array}{l}{\displaystyle\pi_{1}={\frac{9}{20}}}\\ {\displaystyle\pi_{0}={\frac{1}{20}}}\\ {\displaystyle\pi_{2}={\frac{9}{20}}}\\ {\displaystyle\pi_{3}={\frac{1}{20}}.}\end{array}}$  

So it is complete. Whew!!  

I have omitted couple of tedious calculations! As usual, all the typos and mistakes are  mine!  
