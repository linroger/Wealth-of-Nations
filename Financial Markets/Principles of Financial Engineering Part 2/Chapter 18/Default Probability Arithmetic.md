# 18.6 DEFAULT PROBABILITY ARITHMETIC  

Modeling the occurrence and the timing of default events can be quite complex. The market, however, gravitates to some simple and tradable notions as we have seen before with options and implied volatility. In this section, we discuss the arithmetic behind the trading of default probability.  

Imagine default as an event that happens at a random time $\tau$ , starting from some time $t_{0}$ How should we model the probabilities associated with such events?  

We consider the exponential distribution, which can be described as a probability distribution.   
describing the waiting time between events. In this case the event is the default and the waiting time.   
is time until default. Thus we are dealing with modeling the random times until some events occur.  

Let $\tau$ be the occurrence time of a default. The density function of an exponentially distributea random variable, $f(\tau)$ , is given by  

$$
d(\tau)=\lambda e^{-\lambda\tau}
$$  

This is one way to model default occurrence and timing.  

We see that as the parameter $\lambda$ gets bigger, the probability that the event will occur earlier goes. up. Hence this parameter governs when the default event is likely to occur. It is called the intensity associated with the random event..  

The market does not like to use the exponential distribution. Taking the second-order Taylor series approximation of the $f(\tau)$ around the point $\tau_{t_{0}}=0$ we get  

$$
f(\tau)\cong\lambda-\lambda^{2}\tau+\frac{\lambda^{2}\tau^{2}}{2}+o(\tau)^{3}
$$  

Thus the probability that default will occur in a small interval $\Delta$ immediately following $\tau_{t_{0}}$ is approximately given by  

$$
f\left(\tau_{t_{0}}\right)\Delta\cong\lambda\Delta
$$  

Integrating the density. $f(\tau)$ from 0 to some $T$ we get the corresponding probability distribution function (PDF)  

$$
\begin{array}{c}{{P(\tau<T)=\displaystyle\int_{0}^{T}\lambda e^{-\lambda\tau}\mathbf{d}\tau}}\ {{=1-e^{-\lambda T}}}\end{array}
$$  

The first-order Taylor series approximation of the PDF is then given by  

$$
1-e^{\lambda\tau}\cong\lambda\tau
$$  

According to this, the probability that default occurs during a period $\Delta$ is approximately proportional to $\lambda.$ The probability that the event will occur within 1 year is obtained by replacing $T$ in the PDF by 1. We obtain  

$$
P(\tau\leq1)\cong\lambda
$$  

Hence the parameter $\lambda$ can be looked at as the approximate constant rate of default probability. The market likes to trade annual default probabilities, assuming that the corresponding probability is constant over various trading maturities. Obviously as time passes and quotes change, the  

corresponding default probability will also change. Hence it is best to use the subscript $t_{0}$ to denote a probability that is written in an instrument at time $t_{0}$ and use $p_{t_{0}}\cong\lambda_{t_{0}}$ as the default probability written in a contract at inception time $t_{0}$  

Looking at this from a different way: suppose $0<\Delta$ is a small time interval. The default event is represented by a random variable $d_{t}$ that assumes the values of O or 1, depending on whether during $[t,t+\Delta]$ the credit defaults or not.  

$$
d_{t}=\left\{\begin{array}{l l}{{0}}&{{\mathrm{Nodefault}}}\ {{1}}&{{\mathrm{Default}}}\end{array}\right.
$$  

Now we make the assumption that the probability of default follows the equation  

$$
\mathrm{Prob}(d_{t}=1){\cong}p_{t}\Delta
$$  

which says that the probability that the credit defaults during a small interval $\Delta$ depends on the length of the interval and on a parameter $p_{t}$ called the "intensity."' According to this, the probability that default occurs by time $t$ will be given by  

$$
\mathrm{Prob}(\tau<t)=1-e^{-\int_{0}^{t}p_{s}~\mathrm{d}s}
$$  

Assuming $p_{s}$ is constant gives  

$$
\mathrm{Prob}(\tau<\Delta)=1-e^{-p\Delta}
$$  

We have the Taylor series approximation around $t=0$  

$$
e^{-p\Delta}=1-p\Delta+{\frac{1}{2}}p^{2}\Delta^{2}\cdots
$$  

or  

$$
1-e^{-p\Delta}\cong p\Delta
$$  

According to this, the probability that the credit defaults during 1 year will equal $p$  

# 18.6.1 THE DVO1'S  

Working with a CDS of maturity $T=3$ years, let $p_{t_{0}}$ be the risk-adjusted default probability associated with a CDS contract of maturity 3 years. We will ignore the. $t_{0}$ subscript and write this parameter simply as. $p$ .The CDS rate is $\mathrm{cds}_{t_{0}}$ and is observed in the markets. The. $\delta_{i}$ is the time as a. proportion of the year between two consecutive settlement dates.  

Using this we can write the initial value of the CDS at inception time $t_{0}$ as follows. First, if during the 3 years the name does not default, the present value of the cash flows denoted by $P V_{N D}$ will be  

$$
\mathrm{PV}_{\mathrm{ND}}=\big[B(t_{0},t_{1})(1-p)\delta_{1}\mathrm{cds}_{t_{0}}+B(t_{0},t_{2})(1-p)^{2}\delta_{2}\mathrm{cds}_{t_{0}}+B(t_{0},t_{2})(1-p)^{3}\delta_{3}\mathrm{cds}_{t_{0}}\big]N
$$  

On the other hand, the name can default during years 1, 2, or 3. The expected present value of the accrued premium denoted by $P V_{A P}$ if a case default event occurs will be.  

$$
\begin{array}{r l}&{\mathrm{PV}_{\mathrm{AP}}=[B(t_{0},t_{0}+\Delta_{1})\Delta_{1}p\times\mathrm{cds}_{t_{0}}+B(t_{0},t_{1}+\Delta_{2})\Delta_{2}(1-p)p\times\mathrm{cds}_{t_{0}}}\ &{\qquad+B(t_{0},t_{2}+\Delta_{3})\Delta_{3}(1-p)^{2}p\times\mathrm{cds}_{t_{0}}]N}\end{array}
$$  

Three comments might help here. First,. $\Delta_{i}$ are the parameters that determine the prorated spreads that will be received. If the name defaults right after the settlement date then that particular $\Delta_{i}$ will be close to O. If the default is right before the next settlement date, $\Delta_{i}$ will be close to. $\delta_{i\cdot}{}^{22}$ Assuming that the expected default time is the middle of the settlement period gives  

$$
\begin{array}{c}{{\displaystyle{\bf P V}_{\mathrm{AP}}=\frac{1}{2}[B(t_{0},t_{0}+\Delta_{1})\delta_{1}p\times\mathrm{cds}_{t_{0}}+B(t_{0},t_{1}+\Delta_{2})\delta_{2}(1-p)p\times\mathrm{cds}_{t_{0}}}}\ {{{}}}\ {{{}+B(t_{0},t_{2}+\Delta_{3})\delta_{3}(1-p)^{2}p\times\mathrm{cds}_{t_{0}}]N}}\end{array}
$$  

Ihe $\frac12$ comes from the expected default time during an interval $[t_{i},t_{i+1}]$ as given by a uniform distrisution on the interval [0,1], the height of the uniform density being $\mathrm{d}t$  

The expected value of the compensation for the cash payouts during default will be given by  

$$
\begin{array}{c}{{\mathrm{PV_{D}}=B(t_{0},t_{0}\Delta_{1})p(1-R)N+B(t_{0},t_{1}+\Delta_{2})(1-p)p(1-R)N}}\ {{{}}}\ {{+B(t_{0},t_{2}+\Delta_{3})(1-p)^{2}(1-R)N}}\end{array}
$$  

The expected payments and receipts should be equal under the risk-adjusted probability and the CDS rate $\mathrm{cds}_{t_{0}}$ must satisfy the equation  

$$
\mathrm{PV_{ND}=P V_{D}-P V_{A P}}
$$  

Generalizing from the 3-year maturity to $n$ settlement dates, we can write  

$$
\begin{array}{l}{\displaystyle\left[\sum_{i=1}^{n}B(t_{0},t_{i})(1-p)^{i}\delta_{i}\mathrm{cds}_{t_{0}}\right]N+\left[\frac{1}{2}\sum_{i=1}^{n}B\left(t_{0},t_{i-1}+\frac{1}{2}\delta_{i}\right)(1-p)^{i-1}p\delta_{i}\mathrm{cds}_{t_{0}}\right]N}\ {\displaystyle=\sum_{i=1}^{n}B\left(t_{0},t_{i-1}+\frac{1}{2}\delta_{i}\right)(1-p)^{i-1}p(1-R)N}\end{array}
$$  

Using Eq. (18.36), we now define two important concepts. The first is the risky annuity factor. Suppose the investor receives $\$1$ at all $t_{i}.$ The payments will stop with a default. For that period the investor receives only a prorated premium. The risky annuity factor, denoted by $\tilde{A}$ , is the value of this defaultable annuity. It is obtained by letting $\mathrm{cds}_{t_{0}}N=1$ on the right-hand side of the expression in Eq. (18.36)  

$$
\tilde{A}=\left[\sum_{i=1}^{n}B(t_{0},t_{i})(1-p)^{i}\delta_{i}\right]+\left[\frac{1}{2}\sum_{i=1}^{n}B\left(t_{0},t_{i-1}+\frac{1}{2}\delta_{i}\right)(1-p)^{i-1}P\delta_{i}\right]
$$  

The second concept is the risky Dv01. This is given by letting the $\mathrm{cds}_{t_{0}}$ change by one basis point.23 The CDS Dv01 is also known as a credit delta or spread delta. Often the traders use the $\tilde{A}$ as the risky Dv01. Yet, there is a difference between the two concepts. The risky $D V O I$ is how much the value of the CDS changes if one increases $\mathrm{cds}_{t_{0}}$ by 0.0001. In general, this is not going to. equal $\tilde{A}$ , although it will be close to it depending on the shape of the curve and the change in spreads. The reason is following the relationship between the probability of default and the CDS spread ds 24  

$$
(1-R)p_{t_{0}}=\mathrm{cds}_{t_{0}}.
$$  

If Dv01 is the value of a stream of payments to a $\mathrm{dcds}_{t_{0}}=1$ , then note that we have  

$$
\mathrm{d}p={\frac{1}{(1-R)}}
$$  

In other words, the risky annuity factor $\tilde{A}$ will change due to two factors. Both $\mathrm{cds}_{t_{0}}$ and $p_{t_{0}}$ would change. This means that the risky Dvo1 is a nonlinear function of. $\mathrm{cds}_{t_{0}}$ and that there will be a. convexity effect. Most market participants ignore this effect and consider the annuity factor $\tilde{A}$ as a good approximation of Dv01. Yet, if the CDS spreads are moving in a volatile environment then. the two sensitivity measures would differ..  

# 18.6.2 UNWINDING A CDS  

There are three essential ways to unwind a CDS transaction. The first two are similar to the transactions we routinely see in futures markets. The third is a bit different..  

The most common way of unwinding a CDS position is to offset the position with another CDS or by getting in an offsetting position in the underlying assets.  

A second way to unwind a CDS position is by terminating the contract and pay (or receive from) the counterparty the present value of the remaining CDS cash flows. The trick here is to remember that in a credit event, the cash flows would terminate early, hence, the calculation of the PV should take this into account. This is a good example for the use of risky annuities and risky DV01s.  

Finally, assigning the contract to another dealer is the third way of terminating the contract. Below we discuss an example for the use of Dvo1 by terminating the contract before maturity. We will calculate the upfront cash payment or receipt.  

# EXAMPLE  

Theoretically, one can unwind a CDS position by getting into an offsetting position or by receiving or paying the PV of the contract. However, in practice, if the CDS in question is substantially in-the-money, then it may be difficult to find a counterparty who will be willing to pay a substantial upfront for a position that can be attained with no upfront cash. This means that the original owner of the contract may have to accept a PV significantly lower to entice the counterparty to take over the position. In other words, there will be a haircut issue. For example:  

An investor bought 3-year ABC protection on October 29, 2007 at 122 bps on $\$100$ notional. Three days later on November 1, the spread is at 140 bps. This means that the original CDS will be in-the-money by an amount.  

If there is no credit event this means an annuity of  

$$
\frac{(140-122)}{10,000}100m=\$180,000
$$  

to be paid annually at times. $t_{1},t_{2},t_{3}$ . On the other hand, there may be a credit event and the. coupon payments may stop. Assuming that this credit event can occur only at the end of the year there are three possible cash flow paths..  

$$
\{180,180,180\},\{180,180\},\{180\}
$$  

The payments during a default event will approximately cancel each other out assuming that the same cheapest-to-deliver bond is involved during the delivery.  

Suppose the recovery rate is. $40\%$ . In order to determine the present value (PV) of these. cash flows we use risk-adjusted probabilities of default $p$ obtained from the CDS spread at time $t_{0}$  

$$
p=\frac{142}{10,000(1-0.4)}=0.023
$$  

Clearly, we also need the corresponding risky zero bond prices, $\tilde{B}(t_{0},t_{i})$ . Suppose they are given by  

$$
\begin{array}{r}{\tilde{B}(t_{0},t_{1})=0.92}\ {\tilde{B}(t_{0},t_{2})=0.86}\ {\tilde{B}(t_{0},t_{3})=0.79}\end{array}
$$  

Hence we can write the present value of the coupon payments if no default occurs,  

$$
\begin{array}{r l}&{\mathrm{DV}01=[((\tilde{B}(t_{0},t_{1})+\tilde{B}(t_{0},t_{2})+\tilde{B}(t_{0},t_{3}))(1-p)^{3}}\ &{\qquad+(\tilde{B}(t_{0},t_{1})+\tilde{B}(t_{0},t_{2}))(1-p)^{2}+(\tilde{B}(t_{0},t_{1}))(1-p))]\times0.18\times(100)}\end{array}
$$  

where $p^{i}$ $\upsilon^{i},i=1,2,3$ are the probabilities associated with each annuity path. Plugging in the numbers we obtain  

$$
\mathrm{DV}01=87.4775
$$  

Note that we needed to use the default risky discounts and the corresponding Dv01 because the default will change the timing of the cash flows..  

# 18.6.3 UPFRONT PAYMENTS AND CDS UNWINDING  

As we discussed earlier, in 2009 the single-name CDS also moved to upfront payments.  
