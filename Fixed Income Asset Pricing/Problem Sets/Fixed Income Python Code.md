---
title: Fixed Income Python Code
---

# Fixed Income Python Code

Please rewrite the code to produce the charts using plotly and to improve the formatting of the solutions using tables. Use display() instead of print(). For instance, show the price, duration, and convexity as a table with the metrics and their values as two columns.

```python
#%% Bus 35130 HW1

# Suggested solution.

# %% Packages
import os
import math
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from numpy import exp, sqrt, log, mean, std, nonzero, isnan, array, zeros, ones, amax, amin
from numpy import concatenate, arange, interp, diff, cov, var, diag, eye, cumsum, tile, transpose

#plt.close('all')       # Close all charts
#print("\n" * 100)      # Clear Console

#%% =================== Question 1 ===========================
# Determining time series of BEY and provide its plot

# Read time series of 3-month Treasury Bills from 'DTB3.xls' Excel file, sheet 'Dtb3'
Data_TBill = pd.read_excel('DTB3_2024.xls',sheet_name='DTB3',names=['DATE', 'DTB3'] )
rates = array(Data_TBill.DTB3)

II = ~np.isnan(rates)                 # find business dates and ignore days when markets are closed
rates = rates[II]/100                 # get rid of percentages by dividing by 100

# input in BEY formula
N1 = 365
N2 = 360
N3 = 91
BEY = N1*rates/(N2-rates*N3)          # BEY calc according to the formula

# Plot the results
fig = plt.figure(1,figsize=(8,8))
plt.plot(rates)                           # plot of the T-bill rates
plt.plot(BEY)                             # actual plot
plt.ylabel('3-month T-bill rates')        # label on y axis
plt.legend(['Quoted discounts', 'BEY'])   # plot legend

#%% =================== Question 2 ===========================
# Estimating of the AR(1) process for interest rates

m = BEY.shape[0]-1     # the number of regression observations
Y = BEY[1:]            # the dependent variable
X = BEY[0:-1]          # the independent variable

# OLS regression
ybar = mean(Y) # Unconditional mean of Y variable defined above
xbar = mean(X) # Unconditional mean ofXY variable defined above

# beta_hat = cov(X,Y)/var(X), but the Python function 'cov' gives the
# 2 by 2 covariance matrix, not just the covariance, so we use just one number s(1,2)
# Complete the following

s         = cov(X,Y,ddof=1)                   # Covariance calculation
beta_hat  = s[0,1]/var(X,ddof=1)              # Regression slope, beta
alpha_hat = ybar-beta_hat*xbar                # Regression intercept, alpha

# Calculating error terms
eps = Y-alpha_hat-beta_hat*X    # Regression residuals
sig = np.sqrt(var(eps)*m/(m-1)) # Sample standard error of residuals

# Displaying the results in matlab's Command Window
print(' Standard approach ')
print('===========================================================================')
print('Regression coefficients for rates:')
print('beta_hat = ',str(beta_hat))
print('alpha_hat = ',str(alpha_hat))
print('Standard error of residuals:')
print('sig = ',str(sig))
print('===========================================================================')
print(' ')

#%% =================== Question 3 ===========================
# Interest rate forecasts over the period of 5 years

n = 5                                 # number of years to forecast

rate_forecast = zeros(n*252+1)        # vector to store the forecasts
rate_forecast[0] = BEY[-1]            # r_today - the most recent interest rate

# Loop to carry out AR(1) forecast
# r_forecast(i+1) = alpha + beta_hat * r_forecast(i). Fill in the blanks
for i in range(n*252):
    rate_forecast[i+1] = alpha_hat+beta_hat*rate_forecast[i]

# Plot the results
plt.figure(2,figsize=(8,8))
x = arange(0,n+1/252,1/252)
LR_mean = alpha_hat/(1-beta_hat)      # Long-run mean of the interest rate

plt.plot(x,rate_forecast)
plt.plot(x,LR_mean*ones((len(x))),'--',linewidth=2)
plt.ylim((0,0.07))
plt.xlabel('forecasting horizon (years)')
plt.ylabel('3-month T-bill rates')
plt.legend(('Time Series Forecast','Long-term interest rate'))

#%% =================== Question 4 ===========================
# Computing both the current yield curve and forward rates for all
# maturities and comparing the forecasts of future interest rates
# that are implicit in the forward rates to those obtained in question 3

strips_data = pd.read_excel('DTB3_2024.xls', sheet_name='Strip Prices', names= ['Mat','Price'])

Mat  = array(strips_data.Mat)                    # Store maturities into a vector
Imat = nonzero(Mat<5+0.25)                       # Find index with maturity n
Mat  = Mat[Imat]                                 # Take all the maturities up to n
Zfun = array(strips_data.Price)
Zfun = Zfun[Imat]

yield1 = -log(Zfun)/Mat                          # Compute yields from strips (quoted term structure)
fwds = -log(Zfun[1:]/Zfun[0:-1])/0.5             # Compute forward rates
fwds = np.hstack([yield1[0],fwds])               # the first fwd = yield

print(Mat)
print(Zfun)
print(yield1)
print(fwds)

# Plot the results: Z-function only
plt.figure(3)
plt.plot(Mat,Zfun,linewidth=2)
plt.xlabel('forecasting horizon (years)')
plt.ylabel('Z function')
plt.title('Discount function')
#plt.show()

# Plot the results: yields vs forward rates
plt.figure(4)
plt.plot(Mat,yield1,Mat,fwds,'-.',linewidth=2)
plt.xlabel('Maturity')
plt.ylabel('spot rate')
plt.title('Yields and Forwards')
plt.legend(('Yield','Forward'),loc='best')
#plt.show()

# Plot the results: forward rates vs AR(1) forecast of interest rates
plt.figure(5)
plt.plot(Mat,fwds,'-.',x,rate_forecast,linewidth=2)
plt.xlabel('forecasting horizon (years)')
plt.ylabel('spot rate')
plt.title('Two forecasts of future interest rates')
plt.legend(('Forward','Time Series Forecast'),loc='best')
plt.show()

#%% Bus 35130 HW2

# Guide to the solution
# This file is not going to work as is. Your task is to complete the file
# by filling in the ?? scattered through the fil

# %% Packages
import math
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from numpy import exp, sqrt, log, mean, std, nonzero, isnan, array, zeros, ones, amax, amin
from numpy import concatenate, arange, interp, diff, cov, var, diag, eye, cumsum, tile, transpose
from numpy.linalg import inv
from scipy.stats import norm

plt.close('all')       # Close all charts
print("\n" * 100)      # Clear Console

#%% Question 1. Bootstraping the term structure

linethick = 2 # Thinkness of the line for use with plots

# displaying the results in the command window
print('==================================================================')
print('LEVERAGED INVERSE FLOATER')
print('==================================================================')

for i in range(2):
    if i==0:
        bond_data = pd.read_excel('HW2_Data_Solution.xls', sheet_name='Quotes_Semi',usecols=range(12,16))
    elif i==1:
        bond_data = pd.read_excel('HW2_Data_Solution.xls', sheet_name='Quotes_Semi',usecols=range(2,6))
    
    bond_data = array(bond_data)
    coupon    = bond_data[:] # create coupon data
    bid       = bond_data[:] # create bid price data
    ask       = bond_data[:] # create ask price data
    maturity  = bond_data[:] # create maturity data
    
    Nmat     = len(maturity)             # time to maturity
    freq     = 2                         # frequency of coupons, compounding
    price    = (bid+ask)/2               # take price as avg of bid,ask
    maturity = np.round(maturity)      # round maturity (from  to )
    
    # Actual Bootstrap of the Zero Curve - See appendix of Chapter 2 for matrix formulation
    CF=zeros((Nmat,Nmat))
    for ii in range(Nmat):
        CF[ii:ii+1] = coupon[ii]/freq
    CF = CF+100*eye(Nmat)      # add principal
    Z = inv(CF)@price
    
    # convert to yield (both continuously and semi-annually compounded for comparison)
    yield1     = -log(Z)/maturity
    yield_semi = 2*(1/(Z**(1/(2*maturity)))-1)
    
    if i==0:
        ZZ     = Z                              # save the zero coupon
        yyield = yield1                         # save the bootstrapped yield data
    elif i==1:
        ZZ = np.vstack((ZZ,Z)).T                # save the zero coupon
        yyield = np.vstack((yyield,yield1)).T    # save the bootstrapped yield data

# plot discount and yield curves
plt.figure(1)
plt.plot(maturity,ZZ[:],'-.',maturity,ZZ[:],linewidth=linethick)
plt.plot(array((10,10)),array((0.62,1)),'k:',linewidth=linethick)
plt.title('Bootstapped Discount')
plt.xlabel('maturity')
plt.legend(('Use Old Bonds','Use New Bonds'),loc='best')

# plot discount and yield curves
plt.figure(2)
plt.plot(maturity,yyield[:],'-.',maturity,yyield[:],linewidth=linethick)
plt.plot(array((10,10)),array((0,0.04)),'k:',linewidth=linethick)
plt.title('Boostrapped Term Structure')
plt.xlabel('maturity')
plt.legend(('Use Old Bonds','Use New Bonds'),loc='best')

#Note that the directions said to bootstrap as far as we could---12.5 years.
#However, the rest of Part 1 is usually concerned with 5-year maturities.
#Rather than truncate the yield and discount vectors at 5, I continually
#make use of the number freq*T.  Remember that this is simply the number 10
#here because freq=2 (semi-annual), and T is 5.

#%% Question 2. Pricing Leveraged Inverse Floater

coup_fix = 10 # number of coupon payments
T        = 5  # years to maturit

CF_fixed      = (coup_fix/freq)*ones((T*freq))      # fixed coupon
CF_fixed[-1]  = CF_fixed[-1]+100                    # principal amount
P_Fixed       = Z[0:T*freq]@CF_fixed                # price of fixed part
P_Float       = 100                                 # price of floating part
P_zero        = 100*Z[T*freq-1]                     # part of zero part
P_LIF         = P_Fixed-2*P_Float+2*P_zero          # LIF price

# displaying the results in the command window
print('       ')
print('Price of Inverse Floater:')
print(str(np.round(P_LIF)))

# Comparing price and coupon of LevInvFlt (holding short rate fixed) to fixed 5-year bond
coup_IFLconst    = coup_fix-2*100*yield1[0]
CF_IFLconst      = (coup_IFLconst/freq)*ones(T*freq)
CF_IFLconst[-1]  = CF_IFLconst[-1]+100;
P_IFLconst       = Z[0:T*freq]@CF_IFLconst

# displaying the results in the command window
print('IF SHORT-TERM RATE HELD CONSTANT (at ' + str(round(100*yield1[0])) + '%)…')
print('Leveraged Inverse Floater enhances coupon from ' + str(round(coupon[freq*T-1])) + '% to ' + str(round(coup_IFLconst)) + '%')
print('Price of fixed coupon bond with this rate would be ',str(round(P_IFLconst)))

#%% Question 3: Duration and Convexity analysis

# Duration calculations
stripweights     = (Z[0:freq*T]/P_Fixed)*(coup_fix/2)        # coupon weights
stripweights[-1] = stripweights[-1]+(Z[freq*T-1]*100)/P_Fixed # principal weight
D_Fixed          = stripweights@maturity[0:freq*T]          # fixed duration
D_Float          = 1/freq                                    # floating duration
D_Zero           = maturity[freq*T-1]                          # zero duration

# LIF duration
D_LIF = (P_Fixed*D_Fixed-2*P_Float*D_Float+2*100*Z[freq*T-1]*D_Zero)/P_LIF

# compare to duration of fixed 5-year coupon bond
D_fixed5 = maturity[0:freq*T]@(Z[0:freq*T]*0.5*coupon[freq*T-1]/price[freq*T-1]) + maturity[freq*T-1]*100*Z[freq*T-1]/price[freq*T-1]

# displaying the results in the command window
print(' ')
print('Duration of LEV.INV.FLT.: ' + str(round(D_LIF)))
print('Duration of FIXED COUPON NOTE')
print('(with same maturity as LIF): ' + str(round(D_fixed5,2)))

# Graphically display duration effects
# Plot sensitivity of portfolio to parallel shift in term structure

yshift = arange(-0.005,0.05+0.0005,0.0005)   #sizes of term structure shifts
Nyshift = len(yshift)

#initialize vectors computed by loop
Plif_shift    = zeros(Nyshift)
Pfixed5_shift = zeros(Nyshift)

# compute price of both LevInvFlt and fixed 5-yr coupon for each shift
# Pfloat is still the same, par at reset dates
for ii in range(Nyshift):
    Zshift            = exp(-(yield1+yshift[ii])*maturity)
    Pfixed_shift      = np.sum(Zshift[0:freq*T])*coup_fix/2+Zshift[freq*T-1]*100
    Plif_shift[ii]    = Pfixed_shift-2*P_Float + 2*Zshift[freq*T-1]*100
    Pfixed5_shift[ii] = np.sum(Zshift[0:freq*T])*coupon[freq*T-1]/2+Zshift[freq*T-1]*100

# plot of the results
plt.figure(3)
plt.plot(yshift,Plif_shift,linewidth=linethick)
plt.plot(yshift,Pfixed5_shift,'-.',linewidth=linethick)
plt.xlabel('size of parallel shift')
plt.ylabel('price')
plt.legend(('Leveraged Inverse Floater','Fixed Rate 5-yr Bond'))

# Convexity calculations
# Convexity of portfolio = weighted average of portfolio of convexities.
C_Fixed = stripweights@(maturity[0:freq*T]**2)    # fixed convexity
C_Float =(1/freq)**2                              # floating convexity
C_Zero  = maturity[freq*T-1]**2                   # zero convexity

# LIF convexity
C_LIF = (P_Fixed*C_Fixed-2*P_Float*C_Float+2*Z[freq*T-1]*100*C_Zero)/P_LIF;

# note convexity
C_fixed5 = (maturity[0:freq*T]**2)@(Z[0:freq*T]*0.5*coupon[freq*T-1]/price[freq*T-1]) + (maturity[freq*T-1]**2)*100*Z[freq*T-1]/price[freq*T-1]

# displaying the results in the command window
print('   ')
print('Convexity of LIF: ' + str(round(C_LIF)))
print('Convexity of 5-yr fixed coupon bond: ' + str(round(C_fixed5,2)))

#%% Question 4. Value at Risk calculation

# read data from Excel and remove NaN
d6  = pd.read_excel('HW2_Data_Solution.xls', sheet_name='DTB6',skiprows=6,usecols=range(1,2), names=['d6'])
id1 = (d6.d6!='ND')
a   = d6.d6[id1]
d6  = array(a.astype('float'))

P6 = (1-180/360*d6/100) # compute P6 using formula. n=182

# continuous compounding
r6  = -log(P6)*2
dr6 = diff(r6)
# compute distribution of d r6
mu6  = mean(dr6)
sig6 = std(dr6,ddof=1)

# For the LIF
mu_LIF  = -D_LIF*P_LIF*mu6
sig_LIF = sqrt((-D_LIF*P_LIF*sig6)**2)

VaR95 = -(mu_LIF-1.645*sig_LIF)
VaR99 = -(mu_LIF-2.326*sig_LIF)

# For the Fixed
mu_Fixed  = -D_Fixed*P_Fixed*mu6
sig_Fixed = sqrt((-D_Fixed*P_Fixed*sig6)**2)

VaR95_Fixed = -(mu_Fixed-1.645*sig_Fixed)
VaR99_Fixed = -(mu_Fixed-2.326*sig_Fixed)

# historical distribution for the LIF
dP_LIF = -D_LIF*P_LIF*dr6

VaR95_H = -np.percentile(dP_LIF,interpolation='midpoint')
VaR99_H = -np.percentile(dP_LIF,interpolation='midpoint')

# plot the results
plt.figure(41)
histogram_data = plt.hist(dP_LIF)
plt.close(41)
NN = histogram_data[0]
XX = histogram_data[1]
plt.figure(4)
plt.bar(XX[0:-1],NN/sum(NN)/mean(diff(XX)),width=0.25,color='cyan', edgecolor='blue')
plt.xlim((-7,7))
plt.plot(XX,mu_LIF+sig_LIF*norm.pdf(XX),'-g')
plt.plot(array((-VaR99_H,-VaR99_H)),array((0,0.8)),':k',array((-VaR99,-VaR99)),array((0,0.8)),'-.k',linewidth=2)
plt.title('VaR and Historical Distribution for LIF')
plt.legend(('Historical Distribution','Normal Distribution','99 % VaR: Historical','99 % VaR: Normal'),loc='best')

print('95 percent Normal VaR of LIF: ' + str(round(VaR95,2)))
print('95 percent Historical VaR of LIF: ' + str(round(VaR95_H)))
print('99 percent Normal VaR of LIF: ' + str(round(VaR99,2)))
print('99 percent Historical VaR of LIF: ' + str(round(VaR99_H)))

# historical distribution for the Fixed
dP_Fixed = -D_Fixed*P_Fixed*dr6

VaR95_H_Fixed = -np.percentile(dP_Fixed,interpolation='midpoint')
VaR99_H_Fixed = -np.percentile(dP_Fixed,interpolation='midpoint')

# plot the results
plt.figure(51)
histogram_data = plt.hist(dP_Fixed)
plt.close(51)
NN = histogram_data[0]
XX = histogram_data[1]
plt.figure(5)
plt.bar(XX[0:-1],NN/sum(NN)/mean(diff(XX)),width=0.25,color='cyan', edgecolor='blue')
plt.xlim((-7,7))
plt.plot(XX,mu_Fixed+sig_Fixed*norm.pdf(XX),'-g')
plt.plot(array((-VaR99_H_Fixed,-VaR99_H_Fixed)),array((0,2)),':k',array((-VaR99_Fixed,-VaR99_Fixed)), array((0,2)), '-.k',linewidth=2)
plt.title('VaR and Historical Distribution for Fixed Rate Bond')
plt.legend(('Historical Distribution','Normal Distribution','99 % VaR: Historical','99 % VaR: Normal'))

# displaying the results in the command window
print('95 percent Normal VaR of Fixed Rate Bond: ' + str(round(VaR95_Fixed)))
print('95 percent Historical VaR of Fixed Rate Bond: ' + str(round(VaR95_H_Fixed)))
print('99 percent Normal VaR of Fixed Rate Bond: ' + str(round(VaR99_Fixed)))
print('99 percent Historical VaR of Fixed Rate Bond: ' + str(round(VaR99_H_Fixed)))
plt.show()

# Packages
import math
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from numpy import exp, sqrt, log, mean, std, nonzero, isnan, array, zeros, ones, amax, amin
from numpy import concatenate, arange, interp, diff, cov, var, diag, eye, cumsum, tile, transpose
from numpy.linalg import eigh,inv
from scipy.stats import norm
from scipy.interpolate import interp1d, PchipInterpolator

print('==================================================================')
print('PART 1 - PRINCIPAL COMPONENT ANALYSIS')
print('==================================================================')

## data preparation, yields, zeros

# read data
data = pd.read_excel('FBYields_2024_V2.xlsx',sheet_name='FBYields',skiprows=5,usecols='A,C:I')
data = array(data)

# find dates
date1 = 20090331
I_1 = data[:]==date1
date2 = 20090430
I_2 = data[:]==date2

# term structure on the two dates
Mat     = array([np.hstack([1/12,3/12,arange(1,6)])]).T
MatInt  = array([arange(,5+,)]).T
yields1 = (data[I_1,1:]).T/100 # put in decimals
yields2 = (data[I_2,1:]).T/100 # put in decimals

# compute relevant yields at semi-annual frequencies
f = PchipInterpolator(Mat.squeeze(),yields1.squeeze())
Y_Int_1 = f(MatInt)
f = PchipInterpolator(Mat.squeeze(),yields2.squeeze())
Y_Int_2 = f(MatInt)

# compute zeros
Z1=exp(-Y_Int_1*MatInt)
Z2=exp(-Y_Int_2*MatInt)

# plot results
plt.figure(0)
plt.plot(MatInt,Y_Int_1,MatInt,Y_Int_2,linewidth=2)
plt.title('Change in the term structure between March 31st and April 30th')
plt.xlabel('Maturity')
plt.ylabel('Yield')
plt.legend(['March 31, 2009','April 30,2009'])

## Compute value of LIF on both cases

freq=2
coup_fix=10
TT=5

# compute C(T), the cash flows at various maturities, of the "fixed" rate
# bond underlying the LIF
CF_fixed=(coup_fix/freq)*ones((TT*freq))
CF_fixed[-1]=CF_fixed[-1]+100

P_Fixed1=(Z1[0:TT*freq]).T@CF_fixed.T
P_Fixed2=(Z2[0:TT*freq]).T@CF_fixed.T

P_Float=100
P_zero1=100*Z1[TT*freq-1]
P_zero2=100*Z2[TT*freq-1]
# as from HW2, the value of the LIF is given by?
P_LIF1=P_Fixed1-2*P_Float+2*P_zero1
P_LIF2=P_Fixed2-2*P_Float+2*P_zero2

print(' ')
print('P_LIF March, P_LIF April')
print([P_LIF1, P_LIF2,])

# compute average change in the yield curve between date 1 and date 2
dr=mean(Y_Int_2-Y_Int_1)
D_LIF_HW2=11.29 # the duration of LIF from HW2
C_LIF_HW2=58.45 # the convexity of LIF from HW2

dPP_D = -D_LIF_HW2*dr # the change in price due to duration (add formula)
dPP_D_C = -D_LIF_HW2*dr+1/2*C_LIF_HW2*dr**2 # the change in price due to convexity (add formula)

print(' ')
print('Dur-based  Dur/Conv-based   Actual ')
print('Return (%)   Return (%)   Return (%)')
print([dPP_D*100,dPP_D_C*100,  (P_LIF2-P_LIF1)/P_LIF1*100])

## Calculating Principal Components

loc=data[:]<=date1
YY=data[loc:]
T=YY.shape[0]

# We need to build a dataset. Moreover, we need the "betas" from PCA at
# given horizons. Thus, for each month, we build the dataset and interpolate the yields
# on the relevant  horizons, to compute proper betas for the duration
yields=zeros((T,MatInt.shape[0]))
for ii in range(T):
    f=PchipInterpolator(Mat.squeeze(),YY[ii,:])
    yields[ii,:]=f(MatInt).T
    
# compute changes in yields
dy=diff(yields,axis=0)
# compute the covariance matrix of the changes in yields
SIGMA=cov(dy,rowvar=False,ddof=1)
# compute the eigenvalues and eigenvectors of SIGMA
E,V=eigh(SIGMA)
# compute the vectors of eigenvalues from the diagonal matrix E
E=diag(E)
# compute number of eigenvalues. "Eig" command orders eigenvalues and
# eigenvectors from the smallest to the largest. The methodology requires
# we start from the largest eigenvalue.
mm=E.shape[0]

# compute the betas "explicitly"
# component 1

z1=dy@V[:,-1]                 # transform data using eigenvector corresponding to largest eigenvalue (mm)
Level=array([cumsum(z1)]).T   # Level factor
z11=np.vstack((ones(T-1),z1)).T # make a vector for the regressions (include vector of ones)
b1=inv(z11.T@z11)@z11.T@dy    # Regression beta = first component (note: first component is just the second row. The first is just the intercept)
e1=dy-z11@b1                  # Residuals to be used in the next step

RSS1=diag(e1.T@e1)                                      # Residual sum of squares
sisq1=(RSS1/(T-3)).reshape((dy.shape[1]))             # variance of residuals
t1=b1/(sqrt(diag(inv(z11.T@z11)).reshape(2,1)@sisq1.T)) # t-statitstics

# component 2

z2=e1@V[:,-2]                      # transform the residuals using the eigenvector correposponding to the second largest eigenvalue (mm-1)
Slope=array([cumsum(z2)]).T        # Slope factor
z22=np.vstack((ones(T-1),z1,z2)).T # prepare vector for regression
b2=inv(z22.T@z22)@z22.T@dy         # second component = third row of regression beta
e2=dy-z22@b2                       # residuals from regression to compute next component

RSS1=diag(e1.T@e1)                                      # to compute t-stats
sisq2=(RSS1/(T-3)).reshape((dy.shape[1]))
t2=b2/(sqrt(diag(inv(z22.T@z22)).reshape(3,1)@sisq2.T))

# assign the two principal components a new name for simplicity
betas=array([b2[1,:],b2[2,:]])
print('betas: 6 months - 5 years')
print(betas.T)

plt.figure(1)
plt.plot(MatInt,betas[0,:],MatInt,betas[1,:],linewidth=2)
plt.title('Factors')
plt.xlabel('Maturity')
plt.ylabel('Factor Beta')
plt.legend(['Level','Slope'])

# make a vector of dates for the plot
BegDate=1952.5        # beginning of data
EndDate=2009+2/12     # end of data
NDates=Level.shape[0] # number of data points
DatePlot=BegDate+(EndDate-BegDate)*array([arange(0,NDates)]).T/NDates # Vector of dates for the plot

plt.figure(2)
plt.plot(DatePlot,Level,linewidth=2)
plt.title('Level Factor')

plt.figure(3)
plt.plot(DatePlot,Slope,linewidth=2)
plt.title('Slope Factor')

# change in levels and slope
Diff_Level=dy@betas[0,:]
Diff_Slope=dy@betas[1,:]

## Computing factor durations of LIF
   
maturity=MatInt # redefine some variables, to use same codes as HW2
stripweights=(Z1[0:freq*TT]/P_Fixed1)*(coup_fix/2) # we use the "1" price above, as it refers to March
stripweights[-1]=stripweights[-1]+(Z1[freq*TT-1]*100)/P_Fixed1 # principal weight

# Duration against the level factor
D_Fixed_L=(stripweights*maturity*array([betas[0,:]]).T).sum()
D_Float_L=maturity[0]*betas[0,0]
D_Zero_L=maturity[-1]*betas[0,-1]
#take weighted average of level-factor durations
D_LIF_L=(P_Fixed1*D_Fixed_L-2*P_Float*D_Float_L+2*P_zero1*D_Zero_L)/P_LIF1

print(' ')
print('Level Duration: Fixed, Floating, Zero-Coupon, LIF')
print([D_Fixed_L, D_Float_L, D_Zero_L, D_LIF_L])

# Duration against the slope factor
D_Fixed_S=(stripweights*maturity*array([betas[1,:]]).T).sum()
D_Float_S=maturity[0]*betas[1,0]
D_Zero_S=maturity[-1]*betas[1,-1]
#take weighted average of slope-factor durations
D_LIF_S=(P_Fixed1*D_Fixed_S-2*P_Float*D_Float_S+2*P_zero1*D_Zero_S)/P_LIF1

print(' ')
print('Slope Duration: Fixed, Floating, Zero-Coupon, LIF')
print([D_Fixed_S, D_Float_S, D_Zero_S, D_LIF_S])

Diff_Level_March_April=-D_LIF_L*(array([betas[0,:]])@(Y_Int_2-Y_Int_1)) # What is the change in value of LIF due to Level factor?
Diff_Slope_March_April=(-D_LIF_S*array([betas[1,:]]).T*(Y_Int_2-Y_Int_1)).sum() # What is the change in value of LIF due to Slope factor?

dPP_Factors=Diff_Level_March_April+Diff_Slope_March_April # What is the change in value of LIF due to Level and Slope factors?

print(' ')
print('Dur-based Dur/Conv-based Factor-based  Actual ')
print('Return (#)  Return (#)    Return (#)  Return (#)')
print([dPP_D*100,dPP_D_C*100, dPP_Factors*100, (P_LIF2-P_LIF1)/P_LIF1*100])

def regression_35130(Y,X):
    T=Y.shape[0]
    B=inv(X.T@X)@X.T@Y
    eps=Y-X@B # residuals
 
    RSS=eps.T@eps # residual sum of squares
    RSSToT=(Y-mean(Y)).T@(Y-mean(Y))
    sigsq=RSS/(T-3)
    tstat=B/(sqrt(diag(inv(X.T@X))*sigsq))
    R2=1-RSS/RSSToT
    
    return B,tstat,R2

print('==================================================================')
print('PART 2 - PREDICTABILITY OF EXCESS RETURNS                         ')
print('==================================================================')

# Load all the data at annual frequency
DataB = pd.read_excel('FBYields_2024_v2.xlsx',sheet_name='Annual',header=None,skiprows=5)
DataB = array(DataB)
DataB = DataB[::31]

DateB=np.round(DataB[:]/100)       # Date vector
yields=DataB[:,arange(1,6)]          # Yields: Available in Spreadsheet
fwd=DataB[:,arange(17,21)]           # Forwards: Available in Spreadsheet
RetB=DataB[:,arange(25,29)]          # Holding Period Return
AveRetB=DataB[:]
CP=DataB[:]                       # Cochrane-Piazzesi Factor

#BegDateB=round(DateB(1,1));   % Initial date in sample
#EndDateB=round(DateB(end)); % End date in sample
#NDatesB=size(DateB);        % number of data points
#DatePlotB=BegDateB+(EndDateB-BegDateB)*[0:NDatesB]/NDatesB; % make a vector of dates for the plot
DatePlotB = DateB

# Predictive Regressions Regressions
TABLE_FB = zeros((4,6)) # initiate table to save Fama - Bliss Results
TABLE_CP = zeros((4,6)) # initiate table to save Cochrane - Piazzesi Results
for jpred in range(4):
    YY=RetB[1:,jpred]

    # Fama Bliss
    XX0=ones(YY.shape[0])
    XX1=fwd[0:-1,jpred]-yields[0:-1,0] # DEFINE PREDICTIVE VARIABLE (the "X")
    XX=np.vstack([XX0,XX1]).T
    
    BB,tBB,R2=regression_35130(YY,XX)
    TABLE_FB[jpred,:]=array([jpred+2,BB[0],BB[1],tBB[0],tBB[1],R2])
    
    # Cochrane Piazzesi
    XX1=CP[0:-1] # DEFINE PREDICTIVE VARIABLE (the "X")
    XX=np.vstack([XX0,XX1]).T
    BB,tBB,R2=regression_35130(YY,XX)
    TABLE_CP[jpred,:]=array([jpred+2,BB[0],BB[1],tBB[0],tBB[1],R2])

print('Fams-Bliss')
print(TABLE_FB)
print(' ')
print('Cochrane-Piazzesi')
print(TABLE_CP)

# FIGURES FAMA BLISS
ibond=3 # use bond 4 ==> 5 year to maturity

plt.figure(4)
YY=RetB[1:,ibond]
XX0=ones(YY.shape[0])
XX1=fwd[0:-1,jpred]-yields[0:-1,0] # see above: Need to select regressor!
XX=np.vstack([XX0,XX1]).T
BB,tBB,R2 = regression_35130(YY,XX)
plt.plot(XX[:],YY,'bo',XX[:],XX@BB,'k-')
plt.title('Realized 5-year Bond Return vs 5-year Forward Spread')
plt.xlabel('5-year forward spread')
plt.ylabel('realized bond return')
plt.legend(['data','regression fit'])

plt.figure(5)
plt.plot(DatePlotB[0:-1],YY,DatePlotB[0:-1],XX@BB,linewidth=2)
plt.title('5-year Bond Return and Predicted Return from 5-year Forward Spread')
plt.legend(['lagged realized bond return','predicted return'])

# FIGURES COCHRANE PIAZZESI

plt.figure(6)
YY=RetB[1:,ibond]
XX0=ones(YY.shape[0])
XX1=CP[0:-1] # see above: Need to select regressor!
XX=np.vstack([XX0,XX1]).T
BB,tBB,R2 = regression_35130(YY,XX)
plt.plot(XX[:],YY,'bo',XX[:],XX@BB,'k-')
plt.title('Realized 5-year Bond Return vs CP factor')
plt.xlabel('5-year forward spread')
plt.ylabel('realized bond return')
plt.legend(['data','regression fit'])

plt.figure(7)
plt.plot(DatePlotB[0:-1],YY,DatePlotB[0:-1],XX@BB,linewidth=2)
plt.title('5-year Bond Return and Predicted Return from CP factor')
plt.legend(['lagged realized bond return','predicted return'])
plt.show()

# %% Packages
import math
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from numpy import arange, exp, sqrt, log, mean, std, nonzero, isnan, array, zeros, ones, amax, amin, hstack, vstack
from numpy import concatenate, arange, interp, diff, cov, var, diag, eye, cumsum, tile, transpose
from scipy.optimize import fmin
from NLLS_Func import NLLS, NLLS_Min
from YTM_Func import YTMsolver
from scipy.interpolate import interp1d, PchipInterpolator

plt.close('all')   # Close all charts
print("\n" * 100)  # Clear Console

#%% Controls
part1 = 0  # put = 1 to do part 1
part2 = 1  # put = 1 to do part 2. It only works if part1=0.

#%% PART I: TIPS
if part1==1:
    DataR     = array(pd.read_excel('DataTIPS.xlsx',sheet_name='TIPS_01152013',skiprows=4,usecols=arange(2,11)))
    CashFlowR = array(pd.read_excel('DataTIPS.xlsx',sheet_name='TIPS_01152013',skiprows=4,usecols=arange(12,44)))  # This is the cash flow matrix (N x T). Cash flow of each bond corresponding to each maturity.
    MatR      = array(pd.read_excel('DataTIPS.xlsx',sheet_name='TIPS_01152013',skiprows=4,usecols=arange(45,77)))  # Maturity Matrix (N x T) where N=number of bonds, T=max number of maturities.

    BidR   = DataR[:]
    AskR   = DataR[:]
    PriceR = (BidR+AskR)/2

    # Use Nelson Siegel Model.
    vecR0    = array((1.3774,-2.1906,-6.7484,244.0966))/100       # use solution as starting value.
    vecR     = fmin(func=NLLS_Min,x0=vecR0,args=(PriceR,MatR,CashFlowR))
    J,PPhatR = NLLS(vecR,PriceR,MatR,CashFlowR)

    # translate solution back in "formulas"
    th0R = vecR[0]; th1R = vecR[1]; th2R = vecR[2]; laR = vecR[3]

    plt.figure(1)
    plt.plot(DataR[:],PPhatR,'o',DataR[:],PriceR,'*')
    plt.legend(('Fitted','Data'),loc='best')
    plt.xlabel('Maturity')
    plt.ylabel('Price')
    plt.title('TIPS')

    hs   = 1/2         # time step
    T    = arange(hs+hs,hs)  # times
    YccR = th0R+(th1R+th2R)*(1-exp(-T/laR))/(T/laR)-th2R*exp(-T/laR) # real yield

    # Real Discount
    ZZccR = exp(-YccR*T)

    plt.figure(2)
    plt.plot(T,ZZccR,linewidth=2);
    plt.xlabel('Maturity')
    plt.ylabel('Z')
    plt.title('Real Discount')

    plt.figure(3)
    plt.plot(T,YccR,linewidth=2)
    plt.xlabel('Maturity')
    plt.ylabel('Yield')
    plt.title('Real Yield')
    #plt.show()

#%% PART I: Nominal Rates
if part1==1:
    DataN     = array(pd.read_excel('DataTIPS.xlsx',sheet_name='Treasuries_01152013',skiprows=5,usecols=arange(1,9)))
    CashFlowN = array(pd.read_excel('DataTIPS.xlsx',sheet_name='Treasuries_01152013',skiprows=5,usecols=arange(10,70)))  # This is the cash flow matrix (N x T). Cash flow of each bond corresponding to each maturity.
    MatN      = array(pd.read_excel('DataTIPS.xlsx',sheet_name='Treasuries_01152013',skiprows=5,usecols=arange(71,131)))  # Maturity Matrix (N x T) where N=number of bonds, T=max number of maturities.

    Bid        = DataN[:]
    Ask        = DataN[:]
    CleanPrice = (Bid+Ask)/2
    AccrInt    = DataN[:]/2

    # Compute Dirty Prices
    PriceN = AccrInt+CleanPrice

    # Use Nelson Siegel Model.
    vec0    = array((3.9533,-2.6185,-7.3917,200.9313))/100       # use solution as starting value.
    vec     = fmin(func=NLLS_Min,x0=vec0,args=(PriceN,MatN,CashFlowN))
    J,PPhat = NLLS(vec,PriceN,MatN,CashFlowN)

    # translate solution back in "formulas"
    th0 = vec[0]; th1 = vec[1]; th2 = vec[2]; la = vec[3]

    plt.figure(4)
    plt.plot(DataN[:],PPhat,'o',DataN[:],PriceN,'*')
    plt.legend(('Fitted','Data'),loc='best')
    plt.xlabel('Maturity')
    plt.ylabel('Price')
    plt.title('Treasuries')

    hs   = 1/2         # time step
    T    = arange(hs+hs,hs)  # times
    Ycc = th0+(th1+th2)*(1-exp(-T/la))/(T/la)-th2*exp(-T/la) # nominal rate

    # Nominal Discount
    ZZcc = exp(-Ycc*T)

    # Fwd rates
    FWD = -log(ZZcc[1:]/ZZcc[0:-1])/hs
    FWD = hstack((Ycc[0],FWD))

    plt.figure(5)
    plt.plot(T,ZZcc,linewidth=2)
    plt.xlabel('Maturity')
    plt.ylabel('Z')
    plt.title('Nominal Discount')

    plt.figure(6)
    plt.plot(T,Ycc,T,FWD,'--',linewidth=2)
    plt.xlabel('Maturity')
    plt.ylabel('Yield')
    plt.legend(('yield', 'forward'))
    plt.title('Nominal Yield and Forward')

    # Break Even Rates(CC)
    pi = Ycc - YccR

    plt.figure(7)
    plt.plot(T,pi,linewidth=2)
    plt.xlabel('Maturity')
    plt.ylabel('Rate')
    plt.title('Break Even Rate')
    plt.show()

# %% PART II
if part2==1:
    print('==================================================================')
    print('PART 1 - SWAP SPREAD TRADES')
    print('==================================================================')

    #%% Examine Historical Data

    #Load and Prep Data
    H15_SWAPS = array(pd.read_csv('H15_SWAPS.txt', sep='\s+', header=None, skiprows=15))

    II        = (np.isnan(H15_SWAPS[:])==0)  # elimiinate NaN's
    H15_SWAPS = H15_SWAPS[II,:]                # redefine data without NaN's

    Dates = H15_SWAPS[:]                # dates
    LIBOR = H15_SWAPS[:]                # LIBOR rates
    Repo  = H15_SWAPS[:]                # Repo rates
    Swaps = H15_SWAPS[::11]             # Swap rates across maturity
    CMT   = H15_SWAPS[::]              # US Treasury constant maturity rates

    # Creat a plot
    plt.figure(10)
    plt.plot(Swaps[:]-CMT[:],linewidth=1)       # plot Swap Spread
    plt.plot(LIBOR-Repo) # plot LIBOR - Repo spread
    plt.title('5 year Swap Spread and Funding Spread over time')
    plt.legend(('Swap Spread','Funding Spread'))
    #plt.show()

    #%% Load and Prep Swap and Treasury Data for trading exercise

    linethick = 2 # for use with plots
    freq = 2

    # load prices for 5 year T-note

    data = array(pd.read_excel('HW4_Data.xls', sheet_name='Daily_Bond_Swaps', skiprows=12, usecols=arange(1,29)))
    QuoteDates = data[:]
    MatDates   = data[:]
    Coupon     = data[:]
    bid        = data[:]
    ask        = data[:]
    maturity   = data[:]
    AccInt     = data[:]
    LIBOR      = data[:]
    Repo       = data[:]
    SWAPS      = data[:,arange(9,17)]
    CMT        = data[::]
    PriceTnote = (bid + ask)/2

    #%% Setup Trade
    # Examine the usual side of the trade. At the end take negative to get
    # profit on other side of the trade.

    # (A) reverse Repo the 5 year note, and short in to the market.
    #      Pay coupon and receive Repo rate
    # (B) enter swap, receive fixed swap rate, pay floating, 3 M LIBOR

    Swap30     = SWAPS[:,-1]              # time seirs of 30-year swap rates
    SwapRate   = Swap30[0]                # 30-year swap rate at trade date
    CouponRate = Coupon[0]                # Bond coupon rate
    SS         = SwapRate-CouponRate;     # Swap Spread
    LRS        = LIBOR[0]-Repo[0]         # LIBOR-Repo Spread

    print('Swap Spread minus Carry')
    print(100*(SS - LRS))

    # Yield to maturity of Note is
    YTM = YTMsolver(PriceTnote[0],CouponRate,freq)

    # LIBOR Swap curve at time 0 (this only required for later plot)
    DataMat   = hstack((0.25,arange(1,6),10,30))   # maturity points given by data
    IntMat    = arange(0.25,30+0.25,0.25)            # desired points on curve to do interpolation
    DataRates = hstack((LIBOR[0],SWAPS[0,:]))

    f       = PchipInterpolator(DataMat,DataRates)
    IntSwap = f(IntMat)

    # Compute Discounts of Swap
    ZL = zeros(IntSwap.shape[0])
    ZL[0]=1/(1+LIBOR[0]/100*0.25)
    for jj in range(1,IntSwap.shape[0]):
        ZL[jj] = (1-IntSwap[jj]/100*0.25*np.sum(ZL[0:jj]))/(1+IntSwap[jj]/100*0.25)
    LIBOR_Curve_0 = -log(ZL)/IntMat

    # POSITION OF TRADE
    position = 1e8 # size of trade = 100 million
    Tnotes   = position/(PriceTnote[0]+AccInt[0])  # numbers of T-notes bought

    #%% Trade Value after one Quarter

    ValueTNotes = Tnotes*(PriceTnote[0]+AccInt[0])        # Value of notes on the first date
    ValueRepo   = position-Tnotes*(PriceTnote[0]+AccInt[0]) # Value of notes on the second date
    SwapSpread  = SS

    # One quarter later
    Today = 20090518

    # find this date in dataset
    idxToday = nonzero(Today==QuoteDates)

    # compute cash flows
    CF_SS_Today  = Tnotes*1/2*CouponRate*1/2-position*1/4*SwapRate/100   # assume you get accrued interest this quarter
    CF_LRS_Today = position*1/4*LIBOR[0]/100position*1/4*Repo[0]/100   # Cash flow at t depends on rates at t-delta (delta = 0.5)

    # compute value of position
    ValueTNotes_Today = Tnotes*(PriceTnote[idxToday]+AccInt[idxToday])
    ValueRepo_Today   = ValueTNotes_Today-position

    # to value the old swap, we must first extract the LIBOR curve
    # Compute LIBOR Curve Z^{LIBOR}(t;T) by INTERPOLATION
    DataMat   = hstack((0.25,arange(1,6),10,30))   # maturity points given by data
    IntMat    = arange(0.25,30+0.25,0.25)            # desired points on curve to do interpolation
    DataRates = hstack((LIBOR[idxToday][0],SWAPS[idxToday,:][0,0,:]))

    f       = PchipInterpolator(DataMat,DataRates)
    IntSwap = f(IntMat)

    # Compute Discounts of Swap
    ZL = zeros(IntSwap.shape[0])
    ZL[0]=1/(1+LIBOR[idxToday]/100*0.25)
    for jj in range(1,IntSwap.shape[0]):
        ZL[jj] = (1-IntSwap[jj]/100*0.25*np.sum(ZL[0:jj]))/(1+IntSwap[jj]/100*0.25)
    LIBOR_Curve_Today = -log(ZL)/IntMat

    # Given swap curve, value swap as long fixed coupon rate and
    # short floating. (Recall to adjust for the maturity)
    npay            = 30*4-1  # number of payments left AFTER today
    ValueSwap_Today = position*(1-(SwapRate/100*0.25*sum(ZL[0:npay])+ZL[npay-1]))  # value of the swap

    print('Total Values on May 8, 2009')
    print('Repo,  Swap , Swap + Repo')
    print([ValueRepo_Today[0],ValueSwap_Today,ValueSwap_Today+ValueRepo_Today[0]])

    plt.figure(20)
    plt.plot(IntMat,LIBOR_Curve_0,IntMat,LIBOR_Curve_Today,'--',linewidth=2)
    plt.title('LIBOR curve on Feb 2 and May 18, 2009')
    plt.xlabel('Maturity')
    plt.ylabel('yield')
    plt.legend(('Feb 2, 2009', 'May 8,2009'))
    plt.show()

a=1

# Packages
import math
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from numpy import arange, exp, sqrt, log, mean, std, nonzero, isnan, array, zeros, ones, amax, amin, hstack, vstack
from numpy import concatenate, arange, interp, diff, cov, var, diag, eye, cumsum, tile, transpose, nan
from scipy.interpolate import interp1d, PchipInterpolator
from BlackScholes import BSfwd

# Input data
dataMat   = hstack((1/12,arange(1,8)))                                       # maturity points given by data
intMat    = arange(0.25,6+0.25,0.25)                                         # desired points on curve to do interpolation
dataRates = array((0.30338,0.362,0.322,0.321,0.357,0.408,0.461,0.516))/100   # rates points given by data

# Interpolated swap curve at quarterly frequency
f        = PchipInterpolator(dataMat,dataRates)
intRates = f(intMat)

# Bootstrap

# Discount Factor calculations via Bootstrap
dt    = 0.25
ZZ = zeros(intRates.shape[0])
ZZ[0] = 1/(1+dt*intRates[0])
for i in range(1,intRates.shape[0]):
    ZZ[i] = (1-intRates[i]*dt*np.sum(ZZ[0:i]))/(1+intRates[i]*dt)

fwd_Z          = hstack((nan,ZZ[1:]/ZZ[0:-1]))           # Forward Discount
fwd_Rate       = (1/fwd_Z-1)/dt                          # Forward Rate
fwd_Z_Swaption = hstack((nan,nan,nan,nan,ZZ[4:]/ZZ[3]))  # Forward Discount for Swaption calculations

# 1-year Cap
T     = 1                     # Time-to-maturity (years)
X     = 0.00362               # Strike Rate (from data)
sigma = 106.79/100            # Volatility  (from data)
F     = fwd_Rate[1:int(T/dt)] # Forward Rates
Z     = ZZ[1:int(T/dt)]       # Discount Factors
CallF = 1                     # 1 for calls and 2 for puts
T_Cap = arange(dt,T,dt)       # caplet maturities

Caplets_1Year = 100*dt*BSfwd(F,X,Z,sigma,T_Cap,CallF)  # Caplet prices (use BlackScholes.py)
Cap_1Year     = np.sum(Caplets_1Year)                  # Cap price

TABLE_1Year = vstack((arange(dt,T+dt,dt),hstack((nan,F)),hstack((nan,Z)),hstack((nan,Caplets_1Year)))).T
print(TABLE_1Year)
print(('1-year Cap Price = ' + round(Cap_1Year).astype('str')))

# 2-year Cap
T     = 2                     # Time-to-maturity (years)
X     = 0.322/100             # Strike Rate (from data)
sigma = 128.170/100           # Volatility (from data)
F     = fwd_Rate[1:int(T/dt)] # Forward Rates
Z     = ZZ[1:int(T/dt)]       # Discount Factors
CallF = 1                     # 1 for calls and 2 for puts
T_Cap = arange(dt,T,dt)       # caplet maturities

Caplets_2Year = 100*dt*BSfwd(F,X,Z,sigma,T_Cap,CallF)  # Caplet prices (use BlackScholes.py)
Cap_2Year     = np.sum(Caplets_2Year)                  # Cap price

TABLE_2Year = vstack((arange(dt,T+dt,dt),hstack((nan,F)),hstack((nan,Z)),hstack((nan,Caplets_2Year)))).T
print(TABLE_2Year)
print(('2-year Cap Price = ' + round(Cap_2Year).astype('str')))

# Swaption
T     = 1          # Swaption Maturity
X     = 0.408/100  # Strike Rate (5-year swap rate) (from data)
sigma = 99.120/100 # Swaption Volatility (from data)
Z     = 1          # Discount Factors
CallF = 1          # 1 for calls and 2 for puts

# Fwd 5-year Swap Rate
SwapRate = 1/dt*(1-fwd_Z_Swaption[-1])/np.sum(fwd_Z_Swaption[4:])

# A-factor
A = dt*np.sum(ZZ[4:])

# Swaption price
Swaption = A*BSfwd(SwapRate,X,Z,sigma,T,CallF) # use BlackScholes.py.  Compare formula with TNs to understand what inputs to use.

print(('Forward 5-year Swap Rate = ' + round(SwapRate).astype('str')))
print(('A = ' + round(A).astype('str')))
print(('Swaption Price = ' + round(Swaption).astype('str')))


import math
import pandas as pd
import plotly.graph_objects as go
import numpy as np
from numpy.linalg import inv
from numpy import arange, exp, sqrt, log, mean, std, nonzero, isnan, array, zeros, ones, amax, amin, maximum, minimum
from numpy import concatenate, arange, interp, diff, cov, var, diag, eye, cumsum, tile, transpose, nan, hstack, vstack
from numpy import setdiff1d
from scipy.interpolate import interp1d, PchipInterpolator
from scipy.optimize import fmin
from scipy.stats import norm
from numpy.random import normal
from NLLS_Func import NLLS, NLLS_Min
from HoLee_SimpleBDT_Tree import fmin_HoLee_SimpleBDT_Tree, HoLee_SimpleBDT_Tree

print('==================================================================')
print('INTEREST RATE TREES  & VALUATION')
print('==================================================================')

# Load data
Data = array(pd.read_excel('HW6_Data_Bonds.xls', sheet_name='Sheet1', skiprows=4, usecols=arange(9)))
Mat = array(pd.read_excel('HW6_Data_Bonds.xls', sheet_name='Sheet1', skiprows=4, usecols=arange(10, 70)))  # Maturity Matrix (N x T) where N=number of bonds, T=max number of maturities.
CashFlow = array(pd.read_excel('HW6_Data_Bonds.xls', sheet_name='Sheet1', skiprows=4, usecols=arange(72, 132)))  # This is the cash flow matrix (N x T). Cash flow of each bond corresponding to each maturity.

# Assign names to some of the data
Bid = Data[:, 5]
Ask = Data[:, 6]
CleanPrice = (Bid + Ask) / 2
Price = CleanPrice + Data[:, 8]  # add accrued interest to the clean prices.

# Use Nelson Siegel Model
vec0 = array([5.3664, -0.1329, -1.2687, 132.0669]) / 100  # use solution as starting value.
vec = fmin(func=NLLS_Min, x0=vec0, args=(Price, Mat, CashFlow))  # minimization algorithm

# Translate solution back in "formulas"
th0, th1, th2, la = vec
J, PPhat = NLLS(vec, Price, Mat, CashFlow)

# Plot Fitted vs Data
fig1 = go.Figure()
fig1.add_trace(go.Scatter(x=Data[:, 7], y=PPhat, mode='markers', name='Fitted'))
fig1.add_trace(go.Scatter(x=Data[:, 7], y=Price, mode='markers', name='Data'))
fig1.update_layout(title='Fitted vs Data', xaxis_title='Maturity', yaxis_title='Price')
fig1.show()

# Calculate Yield Curve
hs = 1 / 2
T = arange(hs, 30 + hs, hs)
Ycc = th0 + (th1 + th2) * (1 - exp(-T / la)) / (T / la) - th2 * exp(-T / la)

# Discount
ZZcc = exp(-Ycc * T)

# Fwd rates
FWD = -log(ZZcc[1:] / ZZcc[0:-1]) / hs
FWD = hstack((Ycc[0], FWD))

# Plot Discount Curve
fig2 = go.Figure(go.Scatter(x=T, y=ZZcc, mode='lines'))
fig2.update_layout(title='Discount Curve', xaxis_title='Maturity', yaxis_title='Z')
fig2.show()

# Plot Yield and Forward Rates
fig3 = go.Figure()
fig3.add_trace(go.Scatter(x=T, y=Ycc, mode='lines', name='yield'))
fig3.add_trace(go.Scatter(x=T, y=FWD, mode='lines', name='forward'))
fig3.update_layout(title='Yield and Forward Rates', xaxis_title='Maturity', yaxis_title='Yield')
fig3.show()

# BUILDING A RECOMBINING BINOMIAL TREE
# Load time series of six month rates
data = array(pd.read_csv('HW6_FRB_H15.csv', skiprows=5, usecols=[1]))[:, 0]
n = data.shape[0]
DataY6 = data / 100  # back in decimals
P6 = (1 - 180 / 360 * DataY6)
rr6 = -1 / 0.5 * log(P6)

r0 = Ycc[0]

# Build tree, semi-annual increments
BDT_Flag = 0  # = 0: HoLee; =1: SimpleBDT
if BDT_Flag == 1:
    sigma = std(diff(log(rr6) * sqrt(12)), ddof=1)  # note: units (month) must be annualized
else:
    sigma = std(diff(rr6 * sqrt(12)), ddof=1)  # note: units (month) must be annualized

ImTree = zeros((int(30 / hs), int(30 / hs)))
ZZTree = zeros((int(30 / hs + 1), int(30 / hs + 1), int(30 / hs)))

ImTree[0, 0] = r0  # root of the tree
ZZTree[0, 0, 0] = exp(-r0 * hs)  # first zero coupon bond (maturity i=2)
ZZTree[0:1, 1, 0] = 1

ImTree_1 = ImTree

FFF = zeros(int(30 / hs) - 1)
theta = zeros(int(30 / hs) - 1)
for i in arange(1, int(30 / hs)):
    theta_i = fmin(func=fmin_HoLee_SimpleBDT_Tree, x0=0, args=(ZZcc[i], ImTree_1, i, sigma, hs, BDT_Flag))
    theta[i - 1] = theta_i
    FF, ImTree, ZZTreei = HoLee_SimpleBDT_Tree(theta_i, ZZcc[i], ImTree_1, i, sigma, hs, BDT_Flag)
    FFF[i - 1] = FF
    ImTree_1 = ImTree
    ZZTree[0:i + 2, 0:i + 2, i] = ZZTreei

yyTree = -log(ZZTree[0, 0, :]) / T

# Plot Yields: Data vs Tree
fig4 = go.Figure()
fig4.add_trace(go.Scatter(x=T, y=yyTree, mode='lines', name='Tree'))
fig4.add_trace(go.Scatter(x=T, y=Ycc, mode='lines', name='Data', line=dict(dash='dash')))
fig4.update_layout(title='Yields: Data versus Tree', xaxis_title='Maturity', yaxis_title='yield')
fig4.show()

# Plot Theta vs Fwd Rate
if BDT_Flag == 0:  # this only works if we are in the original HoLee model
    fig5 = go.Figure()
    fig5.add_trace(go.Scatter(x=T[:-1], y=theta, mode='lines', name='theta'))
    fig5.add_trace(go.Scatter(x=T[:-1], y=(FWD[1:] - FWD[:-1]) / hs + sigma ** 2 * T[:-1], mode='lines', name='d fwd_dt + sigma^2 T', line=dict(dash='dash')))
    fig5.update_layout(title='Theta vs Fwd Rate', xaxis_title='Maturity', yaxis_title='yield')
    fig5.show()

# Price of the Freddie Mac callable bond on the tree
coupon = 0.06
TBond = 20
FCT = 4  # first call time
iT = int(TBond / hs + 1)  # step at maturity: always 1 more step than T/hs for maturity
iFCT = int(FCT / hs + 1)  # step at first call time

pi = 0.5  # Risk Neutral Probability of up movement

PPTree_NC = zeros((iT, iT))  # initialize the matrix for the non-callable coupon bond with maturity i.
Call = zeros((iT, iT))  # initialize the matrix for American call coupon bond with maturity i.

# Final payoff of non-callable bond
PPTree_NC[0:iT, iT - 1] = 100  # final price is equal to 100

# Backward algorithm
for j in range(iT - 1, 0, -1):
    PPTree_NC[0:j, j - 1] = exp(-ImTree[0:j, j - 1] * hs) * (pi * PPTree_NC[0:j, j] + (1 - pi) * PPTree_NC[1:j + 1, j] + coupon * 100 * hs)
    if j >= iFCT:
        Call[0:j, j - 1] = maximum(exp(-ImTree[0:j, j - 1] * hs) * (pi * Call[0:j, j] + (1 - pi) * Call[1:j + 1, j]), PPTree_NC[0:j, j - 1] - 100)
    else:
        Call[0:j, j - 1] = exp(-ImTree[0:j, j - 1] * hs) * (pi * Call[0:j, j] + (1 - pi) * Call[1:j + 1, j])

PPTree_C = PPTree_NC - Call

print('Price Freddie Mac Callable Bond')
print('P_NC, Call, P_Call')
print(np.round(array([PPTree_NC[0, 0], Call[0, 0], PPTree_NC[0, 0] - Call[0, 0]]), 4))

# Plot Non-Callable vs Callable Bond Prices
fig6 = make_subplots(rows=2, cols=2, subplot_titles=("FCD", "1 period before FCD", "2 periods before FCD", "3 periods before FCD"))
for j in range(1, 5):
    fig6.add_trace(go.Scatter(x=ImTree[0:iFCT - (j - 1), iFCT - (j - 1)], y=PPTree_NC[0:iFCT - (j - 1), iFCT - (j - 1)], mode='lines', name='Non-Callable'), row=(j+1)//2, col=(j-1)%2 + 1)
    fig6.add_trace(go.Scatter(x=ImTree[0:iFCT - (j - 1), iFCT - (j - 1)], y=PPTree_C[0:iFCT - (j - 1), iFCT - (j - 1)], mode='lines', name='Callable'), row=(j+1)//2, col=(j-1)%2 + 1)
fig6.update_layout(title='Non-Callable vs Callable Bond Prices')
fig6.show()

# Duration and Convexity
# Duration - Non-Callable
DNC = -1 / PPTree_NC[0, 0] * (PPTree_NC[0, 1] - PPTree_NC[1, 1]) / (ImTree[0, 1] - ImTree[1, 1])

# Duration - Callable
DCallable = -1 / PPTree_C[0, 0] * (PPTree_C[0, 1] - PPTree_C[1, 1]) / (ImTree[0, 1] - ImTree[1, 1])

# Convexity - Non-Callable
Delta_NC_1u = (PPTree_NC[0, 2] - PPTree_NC[1, 2]) / (ImTree[0, 2] - ImTree[1, 2])
Delta_NC_1d = (PPTree_NC[1, 2] - PPTree_NC[2, 2]) / (ImTree[1, 2] - ImTree[2, 2])
C_NC = 1 / PPTree_NC[0, 0] * (Delta_NC_1u - Delta_NC_1d) / (ImTree[0, 1] - ImTree[1, 1])

# Convexity - Callable
Delta_Call_1u = (PPTree_C[0, 2] - PPTree_C[1, 2]) / (ImTree[0, 2] - ImTree[1, 2])
Delta_Call_1d = (PPTree_C[1, 2] - PPTree_C[2, 2]) / (ImTree[1, 2] - ImTree[2, 2])
C_Callable = 1 / PPTree_C[0, 0] * (Delta_Call_1u - Delta_Call_1d) / (ImTree[0, 1] - ImTree[1, 1])

print('Duration and Convexity:')
print(f'Duration - Non-Callable: {DNC:f}')
print(f'Duration - Callable: {DCallable:f}')
print(f'Convexity - Non-Callable: {C_NC:f}')
print(f'Convexity - Callable: {C_Callable:f}')

# Display results in a table
results_df = pd.DataFrame({
    'Parameter': ['Duration - Non-Callable', 'Duration - Callable', 'Convexity - Non-Callable', 'Convexity - Callable'],
    'Value': [DNC, DCallable, C_NC, C_Callable]
})

display(results_df)
```

```


