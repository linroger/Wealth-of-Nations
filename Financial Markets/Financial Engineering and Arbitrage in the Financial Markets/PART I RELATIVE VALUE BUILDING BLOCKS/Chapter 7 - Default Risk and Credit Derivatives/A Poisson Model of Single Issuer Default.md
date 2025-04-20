---
tags:
  - credit_derivatives
  - poisson_model
  - risk_neutral
  - single_issuer_default
  - survival_probability
aliases:
  - Poisson default model
key_concepts:
  - Poisson process
  - credit derivative pricing
  - default intensity
  - risk-neutral setting
  - survival probability
---

# 7.4 A POISSON MODEL OF SINGLE ISSUER DEFAULT  

As in Section 7.2, we adopt a reduced-form pricing approach and model default as an exogenous process. Following Jarrow and Turnbull (1995), Duffie and Singleton (1999), and Hull (2010), we assume that defaults follow a Poisson process, i.e. occur as unexpected jumps of a continuous variable. The defaults are defined in a risk-neutral setting so that we can first probability-weight and then discount cash flows using a risk-free rate as we did in Section 7.2. We start by reviewing the assumptions of Poisson processes and distributions, following Hogg and Craig (1978). In their context, we define the default intensity and survival probability per unit of time. We then propose a Poisson model of single issuer default with risk-free and risky discounting, and a fixed recovery percentage. This model can be easily calibrated and used to price credit derivatives. We also offer some thoughts on extending the modeling to include the correlation between the default of the reference security issuer and the protection seller.  

# 7.4.1 Poisson Distribution  

Poisson distributions are common in modeling life expectancies, earthquake probabilities, or product failures. All these cases have the following common characteristics:.  

The modeled "events' are discrete jumps.   
The probability of an event occurring over a small time interval is small and proportional to the waiting time.   
The probability of more than one event occurring in a small time interval is zero or minuscule.   
The number of events in non-overlapping time intervals is stochastically independent.  

A typical set-up in Poisson modeling calls for defining a failure intensity parameter $\lambda$ , say $\lambda=1/5{,}000$ chance that we will find a flaw in 1 ton of a material or $\lambda=1/5{,}000$ mortality rate per year, and a time or quantity parameter $\omega$ , say $\omega=10$ tons of material or $\omega=10$ years of life. From those two parameters, coupled with the assumption of independence over time (or quantity batches), we can derive failure and survival probabilities over non-cumulative and cumulative periods of time.  

Suppose for a given category of bond issuer we define a "failure" or default intensity parameter $\lambda$ and a time interval $\omega$ over which we observe the failure. For example, suppose we think that $\lambda=0.5\%=0.005$ of triple-CCC credits default per year based on $\omega=10$ years of observation. We can then define the Poisson distribution of the number of failures by defining its mean as $\mu=\lambda\omega=0.05$ and the probability density function as:  

$$
f(x)={\frac{\mu^{x}e^{-\mu}}{x!}}
$$  

where $x$ is the number of failures in the interval $\omega$ and $f(x)$ is the probability of $x$ failures. In particular, we are interested in the probability of no default, i.e.  

$$
f(x=0)=\frac{\mu^{0}e^{-0.05}}{0!}=0.9512
$$  

The probability of no default is called the survival probability and we will denote it as $P(\omega)$ where  

$$
P(\omega=10)=0.9512
$$  

Let us note the similarities to the Bernoulli set-up of Figure 7.5. As in that diagram, we will be able to represent the survival of the bond on a tree, as each time interval is independent. Also, the cumulative probability of survival will be the product of the survival probabilities of the intervening intervals, but here we impose a time proportional structure of those probabilities. Everything in the Poisson set-up depends on a single intensity parameter. In practical terms, this ensures the simplicity of the calibration process.  

# 7.4.2 A Single Issuer Default Model  

Our model is very simple. We assume a risk-neutral default intensity. $\lambda=0.5\%$ and thus a 1-year risk-neutral survival probability $P(\omega=1)=0.9950.$ We give up any pretense of trying. to calibrate our model to historical defaults of the issuer, the rating category, or any default forecast based on the financial statement analysis. The default intensity parameter or the 1-year survival probability must come from another corporate bond by the same issuer or another credit derivative on the reference issuer. It is, by definition, an implied input. It is backed out of the same model with the same underlying risk-free yield curve..  

We use the same default-free yield curve as in Table 7.1. Under time independence, nothing is different, and we can proceed exactly as in Figure 7.5 and Table 7.2; the only change being the new per-year probability of default of 0.995. The price of the bond is.  

$$
B_{0}={\frac{0.995\times{\bar{\mathrm{55}}}}{1.02500000}}+{\frac{0.995^{2}\times{\bar{\mathrm{55}}}}{1.02624924^{2}}}+{\frac{0.995^{3}\times{\bar{\mathrm{5105}}}}{1.02749797^{3}}}=104.9027
$$  

The yield-to-maturity is $3.258\%$ and the corporate spread is $0.513\%$  

Incorporating the recovery rate into the model is pretty straightforward. Suppose we assume that whenever the bond defaults the owner is able to recover. $R=60\%$ of the face value of the bond. First, we alter Figure 7.5 to provide us with Figure 7.8..  

We then sweep back through the tree adding the coupon cash flows at every step. We start at $t=2$ and compute the discounted expected value of the cash flows at. $t=3$ , right after the  

![](241910fed956797de32cae1ffe588f66e62b430635bbba6066716827c8155602.jpg)  
Figure 7.8 Constant probability of default with recovery  

coupon payment at $t=2$  

$$
B_{2}=\frac{1}{1+0.0300}\left[0.995\times(\S100.0000+\S5)+0.005\times\S60\right]=101.7233
$$  

At $t=1$ , immediately after the coupon payment, we have the value of the bond:  

$$
B_{1}=\frac{1}{1+0.0275}\left[0.995\times\left(\mathbb{S}101.7233+\mathbb{S}5\right)+0.005\times\mathbb{S}60\right]=103.6396
$$  

Finally, at $t=0$ , we would compute the price of the bond as the probability-weighted present value of the bond's cash flows equal to.  

$$
B_{0}=\frac{1}{1+0.0250}\left[0.995\times(\S103.6396+\S5)+0.005\times\S60\right]=105.7526
$$  

The recovery values are non-zero and do not drop out of the calculation, but we can separate. their probability weighting and discounting from the probability weighting and discounting of the stated bond cash flows. As before, this will allow us to discount directly to today using spot. zeros, instead of step-by-step using forwards. Table 7.5 summarizes the calculation procedure.  

Note that the cumulative probabilities of recovery values are O.005, $0.995\times0.005$ , and $0.995^{2}\times0.005$ Also note that the inclusion of the recovery value in the valuation changes. the model price (by) $0.85\%$ and the yield-to-maturity quite significantly . $(2.968\%$ VS $3.258\%$ The corporate spread is equal to $0.223\%$ . Recovery values are rarely zero, and a. $60\%$ recovery assumption is not uncommon in credit derivative valuation..  

Table 7.5  Corporate bond valuation in a default probability model with recovery   


<html><body><table><tr><td>Year</td><td>Def prob.per year</td><td>Risk-free zerorate</td><td>Risk-free DF survival prob CF</td><td>Cum</td><td></td><td>PV</td><td>CumProb. of recov.</td><td>CF PV</td></tr><tr><td>1</td><td>0.005</td><td>2.5000%</td><td>0.975610</td><td>0.99890</td><td>5</td><td>4.8727</td><td>0.005000</td><td>600.2927</td></tr><tr><td>2</td><td>0.005</td><td>2.6249%</td><td>0.949499</td><td>0.99780</td><td>5</td><td>4.7371</td><td>0.004975</td><td>600.2834</td></tr><tr><td>3</td><td>0.005</td><td>2.7498%</td><td>0.921843</td><td>0.99670</td><td>105</td><td>96.4745</td><td>0.004950</td><td>600.2738</td></tr><tr><td></td><td>SumPV</td><td></td><td>105.7526</td><td></td><td>104.9027</td><td></td><td></td><td>0.8499</td></tr><tr><td></td><td>Ytm</td><td></td><td>2.9676%</td><td></td><td></td><td></td><td>十</td><td></td></tr></table></body></html>  

![](32b5593f351e8decc62c30544a1db35af9f070e96e3b0f5a43338d100adfee4e.jpg)  
Figure 7.9 Cash flows of a credit default swap  

# 7.4.3 Pricing a Credit Default Swap in a Single Issuer Default Model  

Let us now price a credit default swap on the ABC bond of Section 7.4.2 with the risk-neutral default intensity $\lambda=0.5\%$ and thus a 1-year risk-neutral survival probability $P(\omega=1)=$ 0.9950. We assume a $60\%$ recovery. We denote the premium paid for the default protection as $x.$ Figure 7.9 portrays the cash flows paid and received by the protection buyer.  

In order to determine the premium charged on the swap, we need to set the probabilityweighted discounted value of the receipts on the swap, equal to the face value plus accrued interest minus the recovery (i.e.. $100+5-60=45)$ to the probability-weighted discounted value of the payments on the swap. Table 7.6 shows the computation of the premium. In the table we verify that $x=0.224$ is the solution to this PV matching exercise..  

The premium charged for CDS protection on a fixed rate bond in a non-flat yield curve is approximately equal to the observed corporate spread. We argued earlier in this chapter that for floating rate bonds the premium is identical to the corporate margin over LIBOR.  

Table 7.6 Pricing the credit default swap   


<html><body><table><tr><td>Year</td><td>Def prob per year</td><td>Risk-free zerorate</td><td>Risk-free DF</td><td>Cum prob of receipt</td><td>CF</td><td>PV=CFx DF x Pr</td><td>CF</td><td>PV=CFx DF</td></tr><tr><td>1</td><td>0.005</td><td>2.5000%</td><td>0.975610</td><td>0.005000</td><td>45</td><td>0.2195</td><td>0.2239</td><td>0.2184</td></tr><tr><td>2</td><td>0.005</td><td>2.6249%</td><td>0.949499</td><td>0.004975</td><td>45</td><td>0.2126</td><td>0.2239</td><td>0.2126</td></tr><tr><td>3</td><td>0.005</td><td>2.7498%</td><td>0.921843</td><td>0.004950</td><td>45</td><td>0.2053</td><td>0.2239</td><td>0.2064</td></tr><tr><td></td><td>Ytm</td><td></td><td></td><td></td><td></td><td>0.6374</td><td></td><td>0.6374</td></tr></table></body></html>  

Table 7.7 The joint probability of default of the reference issuer and protection seller   


<html><body><table><tr><td>PS</td><td></td><td>Nodefault XABC = 0</td><td>Default XABC = 1</td><td>Marginal PS</td></tr><tr><td>Nodefault</td><td>Xps =0</td><td>0.80</td><td>0.10</td><td>0.90</td></tr><tr><td>Default</td><td>Xps = 1</td><td>0.05</td><td>0.05</td><td>0.10</td></tr><tr><td>Marginal ABC</td><td></td><td>0.85</td><td>0.15</td><td>1.00</td></tr></table></body></html>  
