---
tags:
  - agency_mbs
  - cmo_structure
  - fixed_income
  - mortgage_backed_securities
  - prepayment_risk
aliases:
  - CMO
  - agency MBS
  - pass-through
key_concepts:
  - agency MBS market
  - collateralized mortgage obligation
  - prepayment function
  - prepayment privileges
  - stripped MBS
---

# 33.3 AGENCY MORTGAGE-BACKED SECURITIES  

One application of the models presented in this chapter is to the agency mortgagebacked security (agency MBS) market in the United States.  

An agency MBS is similar to the ABS considered in Chapter 8 except that payments are guaranteed by a government-related agency such as the Government National Mortgage Association (GNMA) or the Federal National Mortgage Association (FNMA) so that investors are protected against defaults. This makes an agency MBS sound like a regular fixed-income security issued by the government. In fact, there is a critical difference between an agency MBS and a regular fixed-income investment. This difference is that the mortgages in an agency MBS pool have prepayment privileges. These prepayment privileges can be quite valuable to the householder. In the United States, mortgages typically last for 30 years and can be prepaid at any time. This means that the householder has a 30-year American-style option to put the mortgage back to the lender at its face value.  

Prepayments on mortgages occur for a variety of reasons. Sometimes interest rates fall and the owner of the house decides to refinance at a lower rate. On other occasions, a mortgage is prepaid simply because the house is being sold. A critical element in valuing an agency MBS is the determination of what is known as the prepayment function. This is a function describing expected prepayments on the underlying pool of mortgages at a time $t$ in terms of the yield curve at time t and other relevant variables.  

A prepayment function is very unreliable as a predictor of actual prepayment experience for an individual mortgage. When many similar mortgage loans are combined in the same pool, there is a "law of large numbers" effect at work and prepayments can be predicted more accurately from an analysis of historical data. As mentioned, prepayments are not always motivated by pure interest rate considerations. Nevertheless, there is a tendency for prepayments to be more likely when interest rates are low than when they are high. This means that investors require a higher rate of interest on an agency MBS than on other fixed-income securities to compensate for the prepayment options they have written.  

# Collateralized Mortgage Obligations  

The simplest type of agency MBS is referred to as a pass-through. All investors receive the same return and bear the same prepayment risk. Not all mortgage-backed securities work in this way. In a collateralized mortgage obligation (CMO) the investors  

# Business Snapshot 33.1 IOs and POs  

In what is known as a stripped M BS, principal payments are separated from interest payments. All principal payments are channeled to one class of security, known as a principal only (PO). All interest payments are channeled to another class of security known as an interest only (IO). Both IOs and POs are risky investments. As prepayment rates increase, a PO becomes more valuable and an IO becomes less valuable. As prepayment rates decrease, the reverse happens. In a PO, a fixed amount of principal is returned to the investor, but the timing is uncertain. A high rate of prepayments on the underlying pool leads to the principal being received early (which is, of course, good news for the holder of the PO). A low rate of prepayments on the underlying pool delays the return of the principal and reduces the yield provided by the PO. In the case of an IO, the total of the cash flows received by the investor is uncertain. The higher the rate of prepayments, the lower the total cash flows received by the investor, and vice versa.  

are divided into a number of classes and rules are developed for determining how.   
principal repayments are channeled to different classes. A CMO creates classes of.   
securities that bear different amounts of prepayment risk in the same way that the ABS considered in Chapter 8 creates classes of securities bearing different amounts of.   
credit risk.  

As an example of a CMO, consider an agency MBS where investors are divided into three classes: class A, class B, and class C. All the principal repayments (both those that are scheduled and those that are prepayments) are channeled to class A investors until. investors in this class have been completely paid off. Principal repayments are then channeled to class B investors until these investors have been completely paid off. Finally, principal repayments are channeled to class C investors. In this situation, class A investors bear the most prepayment risk. The class A securities can be expected to last for a shorter time than the class B securities, and these, in turn, can be expected to last less long than the class C securities..  

The objective of this type of structure is to create classes of securities that are more attractive to institutional investors than those created by a simpler pass-through MBS. The prepayment risks assumed by the different classes depend on the par value in each class. For example, class C bears very little prepayment risk if the par values in classes A, B, and C are 400, 300, and 100, respectively. Class C bears rather more prepayment. risk in the situation where the par values in the classes are 100, 200, and 500.  

The creators of mortgage-backed securities have created many more exotic structures than the one we have just described. Business Snapshot 33.1 gives an example.  

# Valuing Agency Mortgage-Backed Securities  

Agency MBSs are usually valued by modeling the behavior of Treasury rates using.   
Monte Carlo simulation. The HJM/BGM approach can be used. Consider what.   
happens on one simulation trial. Each month, expected prepayments are calculated.   
from the current yield curve and the history of yield curve movements. These prepay-.   
ments determine the expected cash flows to the holder of the agency MBS and the cash flows are discounted at the Treasury rate plus a spread to time zero to obtain a sample.  

value for the agency MBS. An estimate of the value of the agency MBS is the average of the sample values over many simulation trials.  

# Option-Adjusted Spread  

In addition to calculating theoretical prices for mortgage-backed securities and other bonds with embedded options, traders also like to compute what is known as the option-adjusted spread (OAS). This is a measure of the spread over the yields on government Treasury bonds provided by the instrument when all options have been taken into account.  

To calculate an OAS for an instrument, it is priced as described above using Treasury rates plus a spread for discounting. The price of the instrument given by the model is. compared to the price in the market. A series of iterations is then used to determine the value of the spread that causes the model price to be equal to the market price. This. spread is the OAS.  

# SUMMARY  

The HJM and BGM models provide approaches to valuing interest rate derivatives that give the user complete freedom in choosing the volatility term structure. The BGM model has two key advantages over the HJM model. First, it is developed in terms of the forward rates that determine the pricing of caps, rather than in terms of instantaneous forward rates. Second, it is relatively easy to calibrate to the price of caps or European swap options. The HJM and BGM models both have the disadvantage that they cannot be represented as recombining trees. In practice, this means that they must usually be implemented using Monte Carlo simulation and require much more computation time than the models in Chapter 32.  

The agency mortgage-backed security market in the United States has given birth to many exotic interest rate derivatives: CMOs, IOs, POs, and so on. These instruments provide cash flows to the holder that depend on the prepayments on a pool of mortgages. These prepayments depend on, among other things, the level of interest rates. Because they are heavily path dependent, agency mortgage-backed securities usually have to be valued using Monte Carlo simulation. These are, therefore, ideal candidates for applications of the HJM and BGM models.  

# FURTHER READING  

Andersen, L. B. G., "A Simple Approach to the Pricing of Bermudan Swaption in the MultiFactor LIBOR Market Model," The Journal of Computational Finance, 3, 2 (2000): 5-32.   
Andersen, L. B. G., and J. Andreasen, "Volatility Skews and Extensions of the LIBOR Market Model," Applied Mathematical Finance, 7, 1 (March 2000): 1-32.   
Andersen, L. B. G., and V. Piterbarg, Interest Rate Modeling, Vols. I-III. New York: Atlantic Financial Press, 2010.   
Brace A., D. Gatarek, and M. Musiela "The Market Model of Interest Rate Dynamics,"' Mathematical Finance, 7, 2 (1997): 127-55.   
Duffie, D. and R. Kan, "A Yield-Factor Model of Interest Rates," Mathematical Finance 6, 4 (1996), 379-406.   
Heath, D., R. Jarrow, and A. Morton, "Bond Pricing and the Term Structure of Interest Rates: A Discrete Time Approximation," Journal of Financial and Quantitative Analysis, 25, 4 (December 1990): 419-40.   
Heath, D., R. Jarrow, and A. Morton, "Bond Pricing and the Term Structure of Interest Rates: A New Methodology," Econometrica, 60, 1 (1992): 77-105.   
Hull, J. C., and A. White, "Forward Rate Volatilities, Swap Rate Volatilities, and the Implementation of the LIBOR Market Model," Journal of Fixed Income, 10, 2 (September 2000): 46-62.   
Jamshidian, F., "LIBOR and Swap Market Models and Measures," Finance and Stochastics, 1 (1997): 293-330.   
Jarrow, R. A., and S. M. Turnbull, "Delta, Gamma, and Bucket Hedging of Interest Rate Derivatives," Applied Mathematical Finance, 1 (1994): 21-48.   
Lyashenko, A., and F. Mercurio, "Looking Forward to Backward-Looking Rates: A Modeling. Framework for Term Rates Replacing LIBOR" (2019). SSRN 3330240.   
Mercurio, F., and Z. Xie, "The Basis Goes Stochastic," Risk, 25, 12 (December 2012): 78-83.   
Miltersen, K., K. Sandmann, and D. Sondermann, "Closed Form Solutions for Term Structure Derivatives with Lognormal Interest Rates," Journal of Finance, 52, 1 (March 1997): 409-30.   
Rebonato, R., Modern Pricing of Interest Rate Derivatives: The LIBOR Market Model and Beyond. Princeton Umiversity Press, 2002..  

# Practice Questions  

33.1. Explain the difference between a Markov and a non-Markov model of the short rate.   
33.2. Prove the relationship between the drift and volatility of the forward rate for the multifactor version of HJM in equation (33.6).   
33.3. "When the forward rate volatility $s(t,T)$ in HJM is constant, the Ho-Lee model results. Verify that this is true by showing that HJM gives a process for bond prices that is consistent with the Ho-Lee model in Chapter 32..   
33.4. "When the forward rate volatility, $s(t,T)$ , in HJM is $\sigma e^{-a(T-t)}$ , the Hull-White model results." Verify that this is true by showing that HJM gives a process for bond prices that is consistent with the Hull-White model in Chapter 32..   
33.5. What is the advantage of BGM over HJM?   
33.6. Provide an intuitive explanation of why a ratchet cap increases in value as the number of factors increase.   
33.7. Show that equation (33.10) reduces to (33.4) as the $\delta_{i}$ tend to zero..   
33.8. Explain why a sticky cap is more expensive than a similar ratchet cap..   
33.9. Explain why IOs and POs have opposite sensitivities to the rate of prepayments..   
33.10. "An option adjusted spread is analogous to the yield on a bond. Explain this statement.   
33.11. Prove equation (33.15).   
33.12. Prove the formula for the variance $V(T)$ of the swap rate in equation (33.17).   
33.13. Show that the swap volatility expression (33.19) in Section 33.2 is correct.  

33.14. In the flexi cap considered in Section 33.2 the holder is obligated to exercise the first $N$ in-the-money caplets. After that no further caplets can be exercised. (In the example,. $N=5.$ ) Two other ways that flexi caps are sometimes defined are:.  

(a) The holder can choose whether any caplet is exercised, but there is a limit of $N$ On the total number of caplets that can be exercised.   
(b) Once the holder chooses to exercise a caplet all subsequent in-the-money caplets must be exercised up to a maximum of $N.$  

Discuss the problems in valuing these types of flexi caps. Of the three types of flexi caps, which would you expect to be most expensive? Which would you expect to be least expensive?  

![](7f450e942df9755886da32397276cb532ec9d2451aee4d8b621cb2e1dd44ef15.jpg)  

# Swaps Revisited  

Swaps have been central to the success of over-the-counter derivatives markets. They have proved to be very flexible instruments for managing risk. Based on the range of different contracts that now trade and the total volume of business transacted each year, swaps are arguably one of the most successful innovations in financial markets ever.  

Chapter 7 discussed how plain vanilla interest rate swaps can be valued. The standard approach can be summarized as: "Assume forward rates will be realized." The steps are. as follows:  

1. Calculate the swap's net cash flows on the assumption that rates in the future equal the forward rates calculated from instruments trading in the market today.   
2. Set the value of the swap equal to the present value of the net cash flows using a risk-free (OIS) rate.  

This chapter describes a number of nonstandard swaps. Some can be valued using the "assume forward rates will be realized" approach; some require the application of the convexity, timing, and quanto adjustments we encountered in Chapter 30; some contain embedded options that must be valued using the procedures described in Chapters 29, 32, and 33.  
