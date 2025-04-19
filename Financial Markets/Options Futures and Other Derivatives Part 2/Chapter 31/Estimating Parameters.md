---
tags:
  - '#cir_model'
  - '#market_price_of_risk'
  - '#parameter_estimation'
  - '#regression_analysis'
  - '#risk_neutral_world'
  - '#term_structure_modeling'
  - '#treasury_rates'
  - '#vasicek_model'
  - '#zero_coupon_rates'
---
# 31.4 ESTIMATING PARAMETERS  

We will illustrate the estimation of parameters with Vasicek's model. The discrete version of the model in the real world is, from equation (31.13),.  

$$
\Delta r=a(b^{*}-r)\Delta t+\sigma\epsilon\sqrt{\Delta t}
$$  

where $\epsilon$ is a random sample from a standard normal distribution. Define $r_{i}$ as the rate on day $i.$ Daily data on 3-month Treasury rates in the United States between January 4,. 1982, and August 23, 2016, together with a worksheet for the analysis in this section, is on www-2.rotman.utoronto.ca/\~hull/VasicekCIR. When we use this data to regress. $r_{i+1}-r_{i}$ against $r_{i:}$ we obtain  

$$
r_{i+1}-r_{i}=0.00000915-0.000545r_{i}
$$  

with a standard error of 0.000754.  

We have about 250 observations per year, so that $\Delta t=1/250.$ Because $0.00000915=$ $0.00229/250,0.000545=0.136/250$ , and $\dot{0}.000754=0.0119/\sqrt{250}$ the regression result is equivalent to  

$$
\Delta r=(0.00229-0.136r)\Delta t+0.0119\epsilon\sqrt{\Delta t}
$$  

or  

$$
\Delta r=0.136(0.0168-r)\Delta t+0.0119\epsilon\sqrt{\Delta t}
$$  

indicating that the best-fit parameters are $a=0.136$ $b^{*}=0.0168$ (or $1.68\%$ ), and $\sigma=0.0119$ (or $1.19\%$ ). Problem 31.15 shows that the same results are obtained using maximum-likelihood methods.  

So far we have estimated the parameters for Vasicek's model in the real world. If the market price of risk is $\lambda$ , the previous section shows that in the risk-neutral world the parameters are $a=0.136,b=0.168-0.0119\lambda/a$ , and $\sigma=0.0119$ For a trial value of $\lambda$ , we can use equations (31.7), (31.8), and (31.10) to estimate zero-coupon rates as a function of maturity. Solver can then be used to determine the value of $\lambda$ that minimizes the sum of squared errors between the zero-coupon rates given by the model and those in the market. This best-fit value of $\lambda$ turns out to be $-0.175$ 4 Table 31.1 compares the zero-coupon rates given by the model when this best-fit value of $\lambda$ is used with those in. the market. Problem 31.16 uses the same data for the CIR model.  

The two-step estimation procedure we have used is a simple procedure and there has been no attempt to fit the term structure of interest rates at times other than today. In practice, researchers use more sophisticated econometric procedures. The parameters we have estimated for Vasicek's model are reasonable, but this will not always be the case.5  

Table 31.1 Best fit of model rates to those in the market, August 23, 2016.   


<html><body><table><tr><td>Maturity (years)</td><td>Modelrate (%)</td><td>MarketRate (%)</td></tr><tr><td>0.5</td><td>0.40</td><td>0.45</td></tr><tr><td>1.0</td><td>0.49</td><td>0.58</td></tr><tr><td>2.0</td><td>0.65</td><td>0.74</td></tr><tr><td>3.0</td><td>0.80</td><td>0.86</td></tr><tr><td>5.0</td><td>1.06</td><td>1.15</td></tr><tr><td>7.0</td><td>1.27</td><td>1.40</td></tr><tr><td>10.0</td><td>1.52</td><td>1.55</td></tr><tr><td>20.0</td><td>2.02</td><td>1.88</td></tr><tr><td>30.0</td><td>2.26</td><td>2.24</td></tr></table></body></html>  

The period of time over which parameters are estimated and the current shape of the term structure can have a big effect on the results obtained. Some judgment is necessary to determine the most appropriate data to use when a model such as Vasicek or CIR is estimated in practice.  
