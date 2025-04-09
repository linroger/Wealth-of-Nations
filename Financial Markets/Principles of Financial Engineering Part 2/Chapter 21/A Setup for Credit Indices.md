# 21.4 A SETUP FOR CREDIT INDICES  

We saw in Chapter 18 that a single-name CDS is a contract that provides protection against a default event on the part of a single issuer or reference name. The protection seller pays zero and receives a constant premium if no default event occurs. The CDS premium is. $\mathrm{cds}_{t_{0}}$ . If a default event does occur the protection seller pays the difference between the promised (face) value of the underlying issue (100) and the market value of the defaulted bond. The recovery rate is denoted by. $R$ . Consider the single-name CDS in Figure 21.7. The maturity. $T$ is assumed to be 1 year for simplicity and the notional amount $N$ is 100. The net payment by the protection seller in case of default is $(I-R)I_{}00$  

A credit index is obtained by selecting $n$ such reference entities indexed by $j=1,...,n.$ This pool is called the reference portfolio. The associated CDS rates at time $t.$ denoted by $\{\mathrm{cds}_{t}^{j}\}$ are assumed to be arbitrage-free. A tradeable CDS index is formed by putting these names in a single contract, where if. $N$ dollars insurance is sold on the index, then this would correspond to a sale of insurance on each name by an amount $\scriptstyle{\frac{1}{n}}N$  

Let $I_{t}$ represent the spread on the credit index for the preselected $n$ names. The "index" would then trade as a separate security from the underlying single-name CDSs. It should be. regarded as a standalone security with a known maturity, coupon, and standardized documentation. Trading the index is equivalent to buying or selling protection on the reference portfolio. names with equal weights.' The spread of this portfolio, i.e., $I_{t}$ , is quoted separately from the underlying CDSs.  

![](images/33549bc7d260114f63a2adc4ba9b798e5f924e0a1e7f7818c8663f7d22abf213.jpg)  

# FIGURE 21.7  

A single-name CDS.  

At the outset, one may think that. $I_{t}$ would (approximately) equal the simple average of the. underlying CDSs. This turns out not to be the case, except in exceptional circumstances when all the CDS rates and their volatilities are the same. In general, we will have.  

$$
I_{t}\leq\frac{1}{n}\sum_{j=1}\mathrm{cds}_{t}^{j}
$$  

In fact, why should a traded credit index trade as if all credits are weighted equally? It is more. reasonable that the pricing of a reference portfolio would weigh the underlying names using their survival probabilities as well as the level of the corresponding CDS rates. In other words, the index spread would be Dvo1-weighted even though the composition of the index is weighted equally..  

# EXAMPLE  

The index has two names:  

$$
\mathrm{cds}^{1}=20\mathrm{bp}
$$  

$$
\mathrm{cds}^{2}=4500\mathrm{bp}
$$  

reminiscent of the spreads during the credit crisis. The average spread will be:  

$$
{\frac{4500+20}{2}}=2260
$$  

According to these spreads it is much less likely that the first name defaults in the near future compared to the second name. This means that if an investor sold protection with notional $N=50$ on each of the individual CDSs, the average receipt during the next. five years is unlikely to be 2260. This is the case since the default of the second name. appears to be imminent. Assuming that default occurs immediately after the transaction, the average return of the remaining 50 invested in the first credit would be. $20\mathrm{bp}$ for the next five years.  

On the other hand, if the index traded at $2260\mathrm{bp}$ , the index protection seller will continue to receive this spread on the remaining $\$50$  

According to this, the index spread will deviate more from the simple average of the underlying CDS spreads, the more dispersed the latter are. This is due to the Dv01 weighing mentioned above.  

Thus, the credit indices are fundamentally different from the better-known equity indices such as S&P500 or Dow. The latter are supposed to equal some average of the price of the underlying. stocks, otherwise there would be an (index) arbitrage opportunity. In the credit sector this differ-. ence is far from zero and the traders trade this difference if it deviates from a calculated fair value..  

For the sake of presentation, the discussion will continue using the iTraxx IG index as representing the $I_{t}$ The next example will help to understand the cash flow structure of such an index.  

# EXAMPLE  

Suppose $n=3$ . The underlying names are A, B, and C. We consider a 1-year maturity with settlement in arrears at the end of the year.  

Suppose $N=3$ is invested in this index. All names are equally weighted and all probabili-. ties of default $p^{i}$ are assumed to be the same. This makes the position similar to putting. $\$1$ on each name in a reference portfolio of three single-name CDSs. However, as mentioned above, the spread on the portfolio as a whole may deviate significantly from the average of the three independent single-name CDSs.  

Essentially, there will be four possibilities or scenarios at the end of the year. There may be no defaults, one default, two defaults or three defaults at time. $t_{1}$ . The structure will be as. shown in Figure 21.8..  

On the other hand, if the position was for more than 1 year the default possibilities would be more complicated for the second year. This is discussed later in this chapter..  

![](images/e474ad4f71203c31f35955e53d220520c0904d023425e1fda09108f6de6b6519.jpg)  

# FIGURE 21.8  

Index with three names.  

What happens when an entity that belongs to the underlying reference names defaults? Consider the case of the iTraxx index with $n=125$ names. The resulting process for this default is similar to. that for a single-name CDS. The protection seller pays to the protection buyer a compensation equal to ${\frac{1}{125}}N.$ In return, the protection buyer delivers deliverable bonds with the same face value.  

After the default, trading will continue in the case of a credit index, albeit with the notional amount reduced by ${\begin{array}{l}{{\frac{1}{n}}}\end{array}}N.$ The index will then have $n-1$ names and any contracts written on it will continue as if the notional amount has become:  

$$
N-{\frac{1}{n}}N={\frac{n-1}{n}}N
$$  

Further defaults would lower this notional in a similar way.  
