# 25.5 RECAP AND PREVIEW

In this chapter, we introduced the local expectations hypothesis and distinguished it from.
the well-known and widely covered unbiased expectations hypothesis. The latter states that the forward rate in the term structure represents the expected future spot rate. The.
local expectations hypothesis says something similar, but not precisely the same. It says that.
when the term structure is arbitrage free, the forward rate is the expected return from any.
strategy over the shortest holding period, and this rate is the shortest period risk-free rate.

We further explored when the unbiased expectations hypothesis and local expectations hypothesis are different and when they are the same. Further, we briefly reviewed numerous other term structure theories that have been offered over the years.

In Chapter 26, we introduce interest rate derivatives, specifically FRAs, swaps, and interest rate options.

# QUESTIONS AND PROBLEMS

1 In some countries, it is illegal to provide financing for arbitrage activities. Explain how the introduction of legal arbitrage activities would be expected to change forward prices. Assume that the hedgers and speculators are roughly balanced between buyers and sellers.
2  Explain the concept of a certainty equivalent and how it is applied in forward pricing models.
3 Compare and contrast the unbiased expectations hypothesis and the local expectations hypothesis within the context of interest rates.
4Under what conditions are the unbiased expectations hypothesis and the local expectations hypothesis identical?
5  Other than the unbiased expectations hypothesis and the local expectations hypothe sis, identify and define three other hypotheses related to the term structure of interest rates.

# NOTES

1. We use rates and yields interchangeably as often occurs within the literature. Where necessary, we. will distinguish between specific measures, such as yield to maturity and holding period return.
2. An excellent illustration of the US government bond term structure and how it has evolved over time is at https://stockcharts.com/freecharts/yieldcurve.php.
3. The unbiased expectations hypothesis is sometimes called the expectations hypothesis, but this is a tremendous misnomer that will become apparent in this chapter, whereby we cover another expectations hypothesis, the local expectations hypothesis. The unbiased expectations hypothesis is also sometimes called the pure expectations hypothesis, although it is unclear what is so pure about it.
4. For references with more details on this subject, see Longstaff (2000), Cox, Ingersoll, and Ross (1981), and Chance and Rich (2001).

5. For ease of exposition, we simplify the forward price from $F_{0}(T)$ to simply $F_{0}$

6. If there were any costs of holding the asset, these costs would be added. If the asset paid out any cash, these amounts would be deducted. It is easy to prove Equation (25.5). Assume that an investor buys the asset and sells a forward contract at the price $F_{0}$ , which obligates the investor to deliver the asset at time 1 and receive $F_{0}$ . This transaction is risk free, because it guarantees a return per dollar invested of $F_{0}/S_{0}$ . Being risk free, this return must equal the risk-free rate. Or, as Equation (25.5) is stated, the spot price must compound to the forward price at the risk-free rate.

7. This section is based on Brooks and Livingston (1992).

# Interest Rate Contracts: Forward Rate Agreements, Swaps, and Options

n Chapter 22, we introduced forward and futures contracts. In those cases, however, the forward and futures were on assets. One of the most popular types of derivative contracts. is based on an interest rate, and an interest rate is not an asset. An asset is something that can be purchased and held in a portfolio.1 One cannot purchase and hold an interest rate. One can, however, purchase and hold an instrument that pays an interest rate, but. the difference must be accounted for when pricing a derivative off of an interest rate. In. this chapter, we shall take a look at interest rate forward contracts, called forward rate agreements, or FRAs, interest rate swaps, and interest rate options. We shall see how we account for this important difference in which there is a payoff based on an underlying. but the underlying cannot be held as an asset. For more details, there are many excellent. references on this subject, among which are Buetow and Fabozzi (2001) and Corb (2012).

Before we begin looking at these instruments, however, let us set up the structure of the problem and identify the key variables. To start, we must understand how loans are done. There are a variety of ways of creating loans. Some are fixed rate, in which the interest rate is set at the start. Others are variable or floating, usually called floating rate, where the interest rate is set and then resets periodically. To see how this is done, let us divide the loan into interest payment periods, sometimes called settlement periods. For example, let us say that each period is one month. So, at the start of the loan, set the rate at the current one-month rate in the market. The interest then accrues for a month, at which time the interest is paid, and the rate resets to the then-current one-month rate. The loan continues in that manner until the final interest payment and principal are made.

These types of loans use what is called add-on interest. Let $B_{0}$ denote the amount borrowed. Letting $L$ be the loan rate expressed in decimal terms, $q$ be the number of days of the loan, and $B_{q}$ denote the amount required to be repaid, the payback at the maturity of the loan is

$$
B_{q}=B_{0}\left[1+L\left(\frac{q}{360}\right)\right].
$$

Note that the convention in this type of market is to divide the interest rate by 360. This is simply a convenience arising from an era in which calculators did not exist and loans commonly used rates such as $6\%$ and the interest payment periods would be 30, 60, 180 days, and so on, in which case the interest could be calculated in one's head.

The rate on this type of loan is typically tied to a commonly used rate benchmark.. Historically, the most popular one was LIBOR, which stood for the London interbank offered rate, the rate at which banks borrow and lend dollars and sometimes other currencies primarily in London. There was significant controversy over the accuracy of LIBOR during some historical periods due to evidence that the official published rate had been manipulated by unscrupulous traders in rate-setting banks. At the time of this writing, there is much debate over the appropriate replacement for LIBOR. Note that. any alternative would still likely be used in the same manner discussed next. The lead candidate is the secured overnight financing rate and related term reference rates. LIBOR data ceased being produced on June 30, 2023.
