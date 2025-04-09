# 22.8 CONCLUSIONS  

In this chapter, we have discussed the dependence of tranche spreads on default correlation in detail and explained how default correlation can be traded. We have applied the standard market model in the form of the Gaussian copula model and highlighted real-world complications. Similar to other model-based trading strategies that we discussed in previous chapters, we explained how correlation trading positions can be delta hedged and how gamma gains arise for such strategies..  

# SUGGESTED READING  

The best references to continue with the discussion given in this chapter are handbooks and reports prepared by broker-dealers themselves. We recommend the JP Morgan's Credit Derivatives Handbook (2007), the two-volume Merrill Lynch set published in 2006 and the Credit Suisse (2007) Handbook on Credit Risk Modeling. Francis et al. (2003) is a good reference for correlation trading. The 2004 JP Morgan credit correlation guide is a good introduction to correlation, the difference between compound and base correlations and their relative merits. Brigo et al. (2010) provide a good account of credit models and CDOs during and after the GFC while Schonbucher (2004) and Duffie and Singleton (2002) are earlier academic approaches.  

# APPENDIX 22.1: SOME BASIC STATISTICAL CONCEPTS  

Consider again the table discussed in the text, shown below, which gives the joint distribution of two random variables.  

This simple table is an example of marginal and joint distribution functions associated with the two random variables $d^{A}$ $d^{B}$ representing the default possibilities for the two references named $A$ $B$ , respectively.  

It is best to start the discussion with a small credit portfolio, then generalize to the, say, iTraxx index. Suppose we have an equally weighted CDS portfolio of. $n=2$ names denoted by $j=A$ $B$ We are interested in a horizon (i.e., maturity) of 1 year. According to this, there are two random variables $d^{A}$ and $\mathrm{d}^{\mathrm{B}}$ , each representing the credits $j=A$ and $j=B$ The $\mathscr{d}^{j}$ assumes the value of 1 if the jth name defaults, otherwise it is equal to 0.  

Suppose the probabilities of default by $A$ and $B$ are given as in the table below.  

<html><body><table><tr><td></td><td>A Defaults (dA = 1) A Survives (dA = 0)</td><td>Sum of Rows</td></tr><tr><td>B Defaults (d = 1) 0.02</td><td>0.03</td><td>0.05</td></tr><tr><td>B Survives (d = 0) 0.01</td><td>0.94</td><td>0.95</td></tr><tr><td>Sumofcolumns 0.03</td><td>0.97</td><td>1</td></tr></table></body></html>  

Now we can discuss the most relevant point concerning this table. If the default-related random variables $d^{A}$ and $d^{B}$ were independent, then we would have  

$$
\begin{array}{c}{{p^{11}=(1-p^{A})(1-p^{B})}}\ {{{}}}\ {{p^{22}=(p^{A})(p^{B})}}\ {{{}}}\ {{p^{12}=(1-p^{A})(p^{B})}}\ {{{}}}\ {{p^{21}=(p^{A})(1-p^{B})}}\end{array}
$$  

Otherwise, if any of these conditions were not satisfied, then the default random variables would. be correlated. In this particular case, a quick calculation would reveal that none of these conditions are satisfied. For example for $p^{11}$ we have  

$$
p^{11}=0.02\neq p^{A}p^{B}=0.0015
$$  

As a matter of fact, the joint probability of default is more than 10 times greater than the. simple-minded (and in this case, wrong) calculation by simple multiplication of individual default probabilities.  

Let us calculate the expected values, variances, and covariances of the two random variables $d^{A}$ and $d^{B}$ . For the expected values  

$$
\begin{array}{l}{{E[d^{A}]=1p^{A}+0(1-p^{A})=p^{A}}}\ {{\mathrm{}=0.03}}\end{array}
$$  

$$
\begin{array}{l}{{E[d^{B}]=1p^{B}+0(1-p^{A})=p^{B}\nonumber}}\ {{\nonumber}}\ {{\qquad=0.05}}\end{array}
$$  

For the variances, we have  

$$
\begin{array}{r}{E[(d^{A}-E[d^{A}])^{2}]=(1-p^{A})^{2}p^{A}+(0-p^{A})^{2}(1-p^{A})=(1-p^{A})p^{A}}\ {=(0.03)(0.97}\end{array}
$$  

$$
\begin{array}{r}{E[(d^{B}-E[d^{B}])^{2}]=(1-p^{B})^{2}p^{B}+(0-p^{B})^{2}(1-p^{B})=(1-p^{B})p^{B}}\ {=(0.05)(0.95}\end{array}
$$  

Finally, the more important moment, the covariance between $d^{A}$ and $d^{B}$ is given by  

$$
\begin{array}{r}{E[(d^{B}-E[d^{B}])(d^{A}-E[d^{A}])]=(1-p^{B})(1-p^{A})p^{11}+(0-p^{B})(0-p^{A})p^{22}\qquad}\ {+(1-p^{B})(0-p^{A})p^{12}+(1-p^{A})(0-p^{B})p^{21}\qquad}\end{array}
$$  

where $p^{i k}$ is the joint probability that the corresponding events happen jointly. Remember that we must have  

$$
p^{11}+p^{12}+p^{21}+p^{22}=1
$$  

To convert this into a correlation, we need to divide this by the square root of the variances of $d^{A}$ and $d^{B}$  

# EXERCISES  

1. Explain the difference between a cash CDO and a synthetic CDO?   
2. What is the difference between compound correlation and base correlation?   
3. We consider a reference portfolio of three investment grade names with the following 1-year CDS rates: $c(1)=116$ $c(2)=193$ $c(3)=140$ The recovery rate is the same for all names at $R=40$ The notional amount invested in every CDO tranche is $\$1.50$ Consider the questions: a. What are the corresponding default probabilities? b. How would you use this information in predicting actual defaults? c. Suppose the defaults are uncorrelated. What is the distribution of the number of defaults during 1 year? d. How much would a $0{-}66\%$ tranche lose under these conditions? e. Suppose there are two tranches: $0{-}50\%$ and $50{-}100\%$ . How much would each tranche pay over a year if you sell protection? f. Suppose all CDS rates are now equal and that we have. $c(1)=c(2)=c(3)=100$ Also, all defaults are correlated with a correlation of one. What is the loss distribution? What is the. spread of the $0{-}50\%$ tranche?  

4. We consider a reference portfolio of four investment grade names with the following 1-year CDS rates:  

$\begin{array}{l}{c(1)=14}\ {c(2)=7}\ {\mathfrak{c}(3)=895}\ {c(4)=33}\end{array}$   
The recovery rate is the same for all names at. $R=30\%$   
The notional amount invested in every CDO tranche is $\$1.00$ . Consider the questions:  

a. What are the corresponding annual default probabilities?  

b. Suppose the defaults are uncorrelated, what is the distribution of the number of defaults during 1 year?   
c. Suppose there are three tranches:. $0-50\%$ $50-75\%$ $75-100\%$ How much would each tranche pay over a year?  

d. Suppose the default correlation becomes 1, and all CDS rates are equal at $60~\mathrm{bp}$ answer questions (a)-(c) again. e. How do you hedge the risk that the probability of default will go up in the equity tranche'  

5. We consider a reference portfolio of three investment grade names with the following 1-year CDS rates: $c(1)=15$ $c(2)=11$ $c(3)=330$ The recovery rate is the same for all names at $R=40$ The notional amount invested in every CDO tranche is $\$1.50$ . Consider the questions: a. What are the corresponding default probabilities? b. How would you use this information in predicting actual defaults? c. Suppose the defaults are uncorrelated. What is the distribution of the number of defaults during 1 year? d. How much would a $0{-}66\%$ tranche lose under these conditions? e. Suppose there are two tranches: $0{-}50\%$ and $50{-}100\%$ . How much would each tranche pay over a year if you sell protection?. f. Suppose all CDS rates are now equal and that we have. $c(1)=c(2)=c(3)=100$ . Also, all defaults are correlated with a correlation of one. What is the loss distribution? What is th spread of the $0-50\%$ tranche?  

6. Explain the following position using appropriate graphs. In particular, make sure that you define a barbell in credit sector. Finally, in what sense is this a convexity position?  

1008 GMT [Dow Jones] LONDON-SG recommends selling 7-year $0{-}3\%$ tranche protection versus 5-year and 10-year $0{-}3\%$ protection. 7-year equity correlation tightened versus 5-year and 10-year last year..  

SG's barbell plays a steepening of the 7-year bucket, as well as offering positive roll down, time decay, and jump to default.  

7. (May 2005 Crisis) What was the effect of the 2005 downgrade of General Motors and Ford on the credit market. What was the effect on default correlations and correlation trading. positions?  

# MATLAB EXERCISES  

8. (Default Loss Distribution) Building on the tranche valuation model outlined in the text, write a MATLAB program to model the sensitivity of the default loss distribution of a portfolio consisting of 100 names/underlyings to changes in default correlation (p). Assume that the default probability (p) of each of the portfolio constituents is the same and equal to $5\%$ . Take 100 numbers of latent variables to carry out the simulations and interpret the results.   
9. (Correlation swaps and equity option implied correlation) In this chapter, we drew an analogy between tranche implied default correlations and implied volatilities and implied correlations in equity option markets. Equity correlation trading was discussed in Chapter 16. One approach to trading correlations is by means of a correlation swap. a. Explain how a synthetic equity correlation swap on the S&P500 or S&P100, for example, can be created. What are the similarities and differences between trading default correlation and equity option implied correlation? b. Download stock return and option data and calculate the implied and realized correlation. for the index over the 2004-2013 period. c. Comment on the evolution of the so-called correlation risk premium, that is the difference between the implied and realized correlation. d. Are correlation swaps an attractive investment? What are the caveats?  

# PRINCIPAL PROTECTION TECHNIQUES  

# 23  

# CHAPTER OUTLINE  

23.1 Introduction. .80?   
3.2 The Classical Case.... 810   
23.3 The CPPI 811   
23.4 Modeling the CPPI Dynamics 813   
23.4.1 Interpretation.. 814   
23.4.2 How to Pick 815   
23.5 An Application: CPPI and Equity Tranches . 815   
23.5.1 A Numerical Example . 816   
23.5.1.1 The initial position. 817   
23.5.1.2 Dynamic adjustments. 818   
23.5.1.3 Default and switching out of CPPI into zero-coupon bond. 820   
3.6 Differences Between CPDO and CPPI .... .820   
23.7 A Variant: The DPPI. 821   
23.8 Application of CPPI in the Insurance Sector: ICPPI. . 822   
3.9 Real-World Complications .. .824   
23.9.1 The Gap Risk 824   
23.9.2 The Issue of Liquidity. 824   
23.9.3 Which Principal Protection Technique is Best in Practice?. 825   
23.10 Conclusions. 825   
Suggested Reading .. .826   
Exercises . 826  

# 23.1INTRODUCTION  

Investment products, where the principal is protected, have always been popular in financial markets. However, until recently the so-called guaranteed products sector has relied mainly on static principal protection which consists of a static portfolio of a default-free bond plus a basket of. options. This is also sometimes referred to as option-based portfolio insurance (OBPI). However,. recent advances in financial engineering techniques have made it possible to create guaranteed pro-. ducts and offer protection in other ways. As structurers understood dynamic replication better, they realized that dynamic replication could synthetically create options on risks where no traded.  

options exist. This led to the creation of dynamic rebalancing techniques, the best known being the constant proportion portfolio insurance (CPPI). CPPI products on a variety of assets have been sold. by banks, including equity indices and credit default swap indices. With the development of credit. markets, CPPI was applied to credit indices and the implied tranches as well. As expertise on the. dynamic replication techniques grew, market activity led to new innovations such as the dynamic proportion portfolio insurance (DPPI). The heyday of CPPI product development and innovation. was during the years before the GFC, but CPPI applications continue to exist in various markets.  

A major reason for the popularity of the guaranteed product sector is regulatory behavior. Several countries do not let investment banks issue structured products involving "exotic" risks unless the product provides some principal protection guarantee. CPPI is a protected note and is not subject to these restrictions. In addition, many funds are not allowed, by law, to invest in securities that are speculative grade. Other dynamic proportion techniques are not principal protected, but both the principal and the coupon can be rated AAA by the main rating agencies, although they offer unusually high coupons. These make them attractive to conservative funds as well.'  

In this chapter, we discuss the classical static principal protection methodology followed by an. introduction to the CPPI as an extension of this classical methodology. We show the dynamics of. the portfolio value that applies this technique under some simple conditions and provide the results of some simulations as well. We then deal with the application of the methodology to standard credit index tranches and discuss the complications that may arise when this is implemented. Finally, we introduce some modeling aspects and discuss the so-called gap risk, and deal briefly with the DPPI.  
