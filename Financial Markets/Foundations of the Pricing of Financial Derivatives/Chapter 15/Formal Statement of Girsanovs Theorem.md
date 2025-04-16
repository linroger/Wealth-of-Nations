---
tags:
  - '#adapted_process'
  - '#girsanov_theorem'
  - '#martingale'
  - '#probability_measure'
  - '#probability_space'
  - '#radon_nikodym_derivative'
  - '#wiener_process'
---
# 15.4 FORMAL STATEMENT OF GIRSANOV'S THEOREM

Define the complete probability space as $(\itOmega,I,P)$ . Let $\mathcal{Q}$ be a probability measure defined on I. $\mathcal{Q}$ is equivalent to $P$ if for every $A$ that is an element of $I,P(A)=0$ if and only if $Q(A)=0$

Assuming equivalent probability measures for $P$ and $\mathcal{Q}$ , the Radon-Nikodym deriva-. tive of $\mathcal{Q}$ with respect to $P$ is defined as

$$
Z\equiv\frac{d Q}{d P}=\frac{\mathrm{Pr}^{Q}(x)}{\mathrm{Pr}(x)}.
$$

For our purposes here, recall the properties of the standard Wiener processes based on the notation used here:.

Let $\boldsymbol{W}$ and $Z$ be standard Wiener processes on probability measures $P$ and $\mathcal{Q}$ , respectively. Then $W_{0}=0$ and $Z_{0}=0$
: $\mathbb{W}_{u}-\mathbb{W}_{t}$ and $\mathbb{W}_{s}-\mathbb{W}_{t}$ $Z_{u}-Z_{t}~Z_{s}-Z_{t}$ are $P$ -independent and $\mathcal{Q}$ -independent if $0\leq s<t<u$
: $\mathbb{W}_{u}-\mathbb{W}_{t}$ $Z_{u}-Z_{t}$ are $N(0,u-t)$ -distributed under $P$ and $\mathcal{Q}$ , respectively.

We are now ready for a formal statement of Girsanov's theorem. We will then proceed to explain various aspects of it. Girsanov's theorem: Let $\mathbf{}\mathbf{}{W}_{t}$ be a standard Wiener process with respect to probability measure $P$ on $I_{t}$ . Let $(\gamma_{\mathrm{t}})$ be an adapted process such that $\begin{array}{c}{t}\ {\displaystyle{\int_{0}\gamma_{j}d W_{j}}}\end{array}$ is defined. Define a. martingale, $M_{t}$ as $M_{t}\equiv e^{\frac{t}{\rho}\gamma_{j}d W_{j}-\frac{1}{2}\int_{0}^{t}\gamma_{j}^{2}d j}$ Define a new probability measure $\mathcal{Q}$ on $I_{t}$ as $Q(A)\equiv E(1_{A}M_{t});A\in I_{t}$ Then $\begin{array}{c}{{t}}\ {{\int d\widehat{W}_{j}\equiv\int d W_{j}-\int_{0}^{t}\gamma_{j}d j}}\ {{0}}\end{array}$ is a standard Wiener process with respect to $\mathcal{Q}$
