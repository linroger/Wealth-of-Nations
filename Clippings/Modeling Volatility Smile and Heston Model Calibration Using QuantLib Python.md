---
tags: [sigma]
title: Modeling Volatility Smile and Heston Model Calibration Using QuantLib Python
---
# Modeling Volatility Smile and Heston Model Calibration Using QuantLib Python
Modeling Volatility Smile and Heston Model Calibration Using QuantLib Python
============================================================================

 May 19,  2016   by  [Goutham Balaraman](http://gouthamanbalaraman.com/author/goutham-balaraman.html)

 Share on: [Diaspora\*](https://sharetodiaspora.github.io/?title=Modeling%20Volatility%20Smile%20and%20Heston%20Model%20Calibration%20Using%20QuantLib%20Python&url=http%3A//gouthamanbalaraman.com/blog/volatility-smile-heston-model-calibration-quantlib-python.html "Share on Diaspora") / [Twitter](http://twitter.com/home?status=Modeling%20Volatility%20Smile%20and%20Heston%20Model%20Calibration%20Using%20QuantLib%20Python%20http%3A//gouthamanbalaraman.com/blog/volatility-smile-heston-model-calibration-quantlib-python.html "Share on Twitter") / [Facebook](http://www.facebook.com/sharer/sharer.php?u=http%3A//gouthamanbalaraman.com/blog/volatility-smile-heston-model-calibration-quantlib-python.html "Share on Facebook") / [Google+](https://plus.google.com/share?url=http%3A//gouthamanbalaraman.com/blog/volatility-smile-heston-model-calibration-quantlib-python.html "Share on Google Plus") / [Email](mailto:?subject=Modeling%20Volatility%20Smile%20and%20Heston%20Model%20Calibration%20Using%20QuantLib%20Python&body=http%3A//gouthamanbalaraman.com/blog/volatility-smile-heston-model-calibration-quantlib-python.html "Share via Email") / [Bloglovin](http://www.bloglovin.com/blog/14559547/?claim=cqravg9v4n2)

Provides an introduction to constructing implied volatility surface consistent with the smile observed in the market and calibrating Heston model using QuantLib Python.

_Visit here for other [QuantLib Python examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html). If you found these posts useful,  please take a minute by providing some [feedback.](https://docs.google.com/forms/d/e/1FAIpQLSdFdJ768HKmIyJmaVRHBUJNY5NyQl6vr0GZvSkx-bUfIloNZA/viewform)_

European options on an equity underlying such as an index (S&P 500) or a stock (AMZN) trade for different combinations of strikes and maturities. It turns out that the Black-Scholes implied volatility for these options with different maturities and strikes is not the same. The fact that the implied volatility varies with strike is often referred in the market as having a _smile_.

In \[1\]:

```latex
import QuantLib as ql
import math

```

First let us define some of the basic data conventions such as the day\_count,  calendar etc.

In \[2\]:

```latex
day\_count \= ql.Actual365Fixed()
calendar \= ql.UnitedStates()

calculation\_date \= ql.Date(6,  11,  2015)

spot \= 659.37
ql.Settings.instance().evaluationDate \= calculation\_date

dividend\_yield \= ql.QuoteHandle(ql.SimpleQuote(0.0))
risk\_free\_rate \= 0.01
dividend\_rate \= 0.0
flat\_ts \= ql.YieldTermStructureHandle(
    ql.FlatForward(calculation\_date,  risk\_free\_rate,  day\_count))
dividend\_ts \= ql.YieldTermStructureHandle(
    ql.FlatForward(calculation\_date,  dividend\_rate,  day\_count))

```

Following is a sample matrix of volatility quote by exipiry and strike. The volatilities are log-normal volatilities and can be interpolated to construct the implied volatility surface.

In \[3\]:

```latex
expiration\_dates \= \[ql.Date(6, 12, 2015),  ql.Date(6, 1, 2016),  ql.Date(6, 2, 2016), 
                    ql.Date(6, 3, 2016),  ql.Date(6, 4, 2016),  ql.Date(6, 5, 2016),  
                    ql.Date(6, 6, 2016),  ql.Date(6, 7, 2016),  ql.Date(6, 8, 2016), 
                    ql.Date(6, 9, 2016),  ql.Date(6, 10, 2016),  ql.Date(6, 11, 2016),  
                    ql.Date(6, 12, 2016),  ql.Date(6, 1, 2017),  ql.Date(6, 2, 2017), 
                    ql.Date(6, 3, 2017),  ql.Date(6, 4, 2017),  ql.Date(6, 5, 2017),  
                    ql.Date(6, 6, 2017),  ql.Date(6, 7, 2017),  ql.Date(6, 8, 2017), 
                    ql.Date(6, 9, 2017),  ql.Date(6, 10, 2017),  ql.Date(6, 11, 2017)\]
strikes \= \[527.50,  560.46,  593.43,  626.40,  659.37,  692.34,  725.31,  758.28\]
data \= \[
\[0.37819,  0.34177,  0.30394,  0.27832,  0.26453,  0.25916,  0.25941,  0.26127\], 
\[0.3445,  0.31769,  0.2933,  0.27614,  0.26575,  0.25729,  0.25228,  0.25202\], 
\[0.37419,  0.35372,  0.33729,  0.32492,  0.31601,  0.30883,  0.30036,  0.29568\], 
\[0.37498,  0.35847,  0.34475,  0.33399,  0.32715,  0.31943,  0.31098,  0.30506\], 
\[0.35941,  0.34516,  0.33296,  0.32275,  0.31867,  0.30969,  0.30239,  0.29631\], 
\[0.35521,  0.34242,  0.33154,  0.3219,  0.31948,  0.31096,  0.30424,  0.2984\], 
\[0.35442,  0.34267,  0.33288,  0.32374,  0.32245,  0.31474,  0.30838,  0.30283\], 
\[0.35384,  0.34286,  0.33386,  0.32507,  0.3246,  0.31745,  0.31135,  0.306\], 
\[0.35338,  0.343,  0.33464,  0.32614,  0.3263,  0.31961,  0.31371,  0.30852\], 
\[0.35301,  0.34312,  0.33526,  0.32698,  0.32766,  0.32132,  0.31558,  0.31052\], 
\[0.35272,  0.34322,  0.33574,  0.32765,  0.32873,  0.32267,  0.31705,  0.31209\], 
\[0.35246,  0.3433,  0.33617,  0.32822,  0.32965,  0.32383,  0.31831,  0.31344\], 
\[0.35226,  0.34336,  0.33651,  0.32869,  0.3304,  0.32477,  0.31934,  0.31453\], 
\[0.35207,  0.34342,  0.33681,  0.32911,  0.33106,  0.32561,  0.32025,  0.3155\], 
\[0.35171,  0.34327,  0.33679,  0.32931,  0.3319,  0.32665,  0.32139,  0.31675\], 
\[0.35128,  0.343,  0.33658,  0.32937,  0.33276,  0.32769,  0.32255,  0.31802\], 
\[0.35086,  0.34274,  0.33637,  0.32943,  0.3336,  0.32872,  0.32368,  0.31927\], 
\[0.35049,  0.34252,  0.33618,  0.32948,  0.33432,  0.32959,  0.32465,  0.32034\], 
\[0.35016,  0.34231,  0.33602,  0.32953,  0.33498,  0.3304,  0.32554,  0.32132\], 
\[0.34986,  0.34213,  0.33587,  0.32957,  0.33556,  0.3311,  0.32631,  0.32217\], 
\[0.34959,  0.34196,  0.33573,  0.32961,  0.3361,  0.33176,  0.32704,  0.32296\], 
\[0.34934,  0.34181,  0.33561,  0.32964,  0.33658,  0.33235,  0.32769,  0.32368\], 
\[0.34912,  0.34167,  0.3355,  0.32967,  0.33701,  0.33288,  0.32827,  0.32432\], 
\[0.34891,  0.34154,  0.33539,  0.3297,  0.33742,  0.33337,  0.32881,  0.32492\]\]

```

Implied Volatility Surface
--------------------------

Each row in ```
data
``` is a different exipiration time,  and each column corresponds to various strikes as given in ```
strikes
```. We load all this data into the ```
QuantLib
``` ```
Matrix
``` object. This can then be used seamlessly in the various surface construction routines. The variable ```
implied_vols
``` holds the above data in a ```
Matrix
``` format. One unusual bit of info that one needs to pay attention to is the ordering of the rows and columns in the ```
Matrix
``` object. The implied volatilities in the ```
QuantLib
``` context needs to have strikes along the row dimension and expiries in the column dimension. This is transpose of the way the data was constructed above. All of this detail is taken care by swapping the ```
i
``` and ```
j

``` variables below. Pay attention to the line:

```

```latex
implied_vols[i][j] = data[j][i]
```

```latex

in the cell below.

In \[4\]:

```

implied\_vols \= ql.Matrix(len(strikes),  len(expiration\_dates))
for i in range(implied\_vols.rows()):
	for j in range(implied\_vols.columns()):
		implied\_vols\[i\]\[j\] \= data\[j\]\[i\]

```latex

Now the Black volatility surface can be constructed using the ```
BlackVarianceSurface
``` method.

In \[5\]:

```

black\_var\_surface \= ql.BlackVarianceSurface(
	calculation\_date,  calendar,
	expiration\_dates,  strikes,
	implied\_vols,  day\_count)

```latex

The volatilities for any given strike and expiry pair can be easily obtained using ```
black_var_surface
``` shown below.

In \[6\]:

```

strike \= 600.0
expiry \= 1.2 \# years
black\_var\_surface.blackVol(expiry,  strike)

```latex

Out\[6\]:

```

0.3352982638587421

```latex

Visualization
-------------

In \[7\]:

```

import numpy as np
% matplotlib inline
from mpl\_toolkits.mplot3d import Axes3D
import matplotlib.pyplot as plt
from matplotlib import cm

```latex

Given an expiry,  we can visualize the volatility as a function of the strike.

In \[8\]:

```

strikes\_grid \= np.arange(strikes\[0\],  strikes\[\-1\], 10)
expiry \= 1.0 \# years
implied\_vols \= \[black\_var\_surface.blackVol(expiry,  s)
				for s in strikes\_grid\] \# can interpolate here
actual\_data \= data\[11\] \# cherry picked the data for given expiry

fig,  ax \= plt.subplots()
ax.plot(strikes\_grid,  implied\_vols,  label\="Black Surface")
ax.plot(strikes,  actual\_data,  "o",  label\="Actual")
ax.set\_xlabel("Strikes",  size\=12)
ax.set\_ylabel("Vols",  size\=12)
legend \= ax.legend(loc\="upper right")

```latex

![](data:image/png;base64, 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
)

The whole volatility surface can also be visualised as shown below.

In \[10\]:

```

plot\_years \= np.arange(0,  2,  0.1)
plot\_strikes \= np.arange(535,  750,  1)
fig \= plt.figure()
ax \= fig.gca(projection\='3d')
X,  Y \= np.meshgrid(plot\_strikes,  plot\_years)
Z \= np.array(\[black\_var\_surface.blackVol(y,  x)
			  for xr,  yr in zip(X,  Y)
				  for x,  y in zip(xr, yr) \]
			 ).reshape(len(X),  len(X\[0\]))

surf \= ax.plot\_surface(X, Y, Z,  rstride\=1,  cstride\=1,  cmap\=cm.coolwarm,
				linewidth\=0.1)
fig.colorbar(surf,  shrink\=0.5,  aspect\=5)

```latex

Out\[10\]:

```

```latex

![](data:image/png;base64, iVBORw0KGgoAAAANSUhEUgAAAWAAAADtCAYAAACBOK/+AAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAIABJREFUeJzsvXm4JXdd7vv5/WquNe+5p8wgSUhIAgEJBhRRJHoxIorK
PXA9ItyL+jidIyoe5dxz9ApcVB7geHhEkDGESzRETgAZTAwEAhIIIXRChu6ku9PD7j2stWqtmut3
/6hVi9U7e3fvsXt3Uu/z9NN7qFWrqvZa7/rW+3u/71copShRokSJEqcf8kwfQIkSJUo8VVEScIkS
JUqcIZQEXKJEiRJnCCUBlyhRosQZQknAJUqUKHGGUBJwiRIlSpwh6Kf4felRK1GixGohzvQBnG0o
K+ASJUqUOEMoCbhEiRIlzhBKAi5RokSJM4SSgEuUKFHiDKEk4BIlSpQ4QygJuESJEiXOEEoCLlGi
RIkzhJKAS5QoUeIMoSTgEiVKlDhDKAm4RIkSJc4QSgIuUaJEiTOEkoBLlChR4gyhJOAnIZRSxHFM
Oe+vRIntjVOloZU4i6CUIk1ToigiDEOEECilME0T0zSRUiKlRIgytKpEie2AkoCfJMiyjDiOWVxc
pFKpIIRASkmv1wMgiqIh8WqahmEYaJqGpmkIIUpSLlHiDKAk4LMcSimSJCFJEiAn4l6vR5ZlQ1JN
0xRd15FSDrcJgmC4DyEEuq6jadpwu2LbEiVKbB3EKXTCUkTcpijkhiRJUEqhlCIIAsIwxHGcofzg
+z6apqGUIssypJRomjb8vyDp4vfF91LKISmPVsolSpwE5QtkjSgr4LMQhdyQZRmQywu+72Oa5rCa
LchWCIFlWUgphySbpulQK1ZKPYGQC6KNouiE5y1IuSDmUk8uUWJjKAn4LMJSuSFNU/r9PkIIarUa
uq4Tx/GKjxdCDKvZAlmWDUk5jmPSNB3qx6PEXDz/6AJfsU/DMIaacqknlyixepQEfBZgqdwA4Ps+
URThuu6w8l0PCr1X1/XhcxXPl2UZURQNq+lRUi404iAISJJkWE0X2xSVcqknlyixMkoC3uZYKjfE
cUy/38c0TRqNxhPIbaMVaPH40f0W0sVopVyQckG6o48pthnVkwtSLvXkEiV+gJKAtymWczf0+32U
UlSrVQzDOOljCxSLcRvBqHRRPG9BykEQnFCdr6Qnx3F8gjxS6sklSpQEvO1QENtoJ9uou8GyrG1B
VAUpSykxDGO48LdWPXl0oa/0J5d4qqEk4G2EooW4IK4kSej3++i6vqzcsN2wUT15OX/ycpVyiRJP
FpQEvA2wVG5QStHr9UjTlEqlclK54WT7PNPV41r15OX8yWma4nkejuMM9zlKyKWeXOJsRknAZxiF
thuGIa7rEoYhQRBg2zbVanXN5DJqD9uOWElPLqrkUUfFaMVb6sklnowoCfgMYVRuAEiShE6ng6Zp
1Ov1E7y669n32YSiqh3FaJUMDP3Oo1VyQc4r6clLrXAlKZfYbigJ+DSjqPaKCq5oIc6ybOhuKImC
E3TiOI6pVConVMphGJ5STw7DkDAMgR9U3kuli/JalziTKAn4NGKlFmLDMJBSYprmljzv2VYRL4fN
0pMLnb3YZ6knlziTKAn4NGB0kU0I8YQWYmAYG7lRFL7f0SyIsxknW0xcj568tBW72CaKIkzTPEG6
KPXkEluNkoC3EMslli3XQpym6aZVqcVzFFX2KJ4KFd6p9OQ4jgmC4Al68mhnX0HIBfmXenKJrUJJ
wFuEtbYQbxQF8SZJgmmaQxIqfLUrEc9TgUxO5U8udOIgCJZtGlmqJwPLShdP9utYYvNREvAm42Qt
xEVi2VJstF04iqJhw4au68Pb8YIUik61UeIpKvOVNNMnM5ks1ZML37VlWcNKeWm40Gr15NGFvifz
NSyxOSgJeJOwXGLZVrcQF+SeJMlQ0vA8b8XtR4lnaaZDceyjmulyxPNkxlr05KVVMvxATy4+UEs9
ucSpUBLwJmCp3LDVLcRKKcIwxPd9LMui0Wis+419qozgon14dLunig66Xj159O896k8u7jZM0xw6
X54K17HEyigJeANYTm7wfX/NLcRrkSCSJKHX650Qwr7ccW3kTb2cZrqUlIvb86JKPJtzf9dyvVaj
J6/kT06SZNhYMhpqX4YQPXVREvA6UBBvFEVD0tloC/FqntP3/TVLGlsZR5mmKWEYnqCHjlq9NqO6
2w6ZFifDyfzJS0c/FdtmWXaCrFMOSX3qoiTgNaKQG4pVccdx6PV6m9ZCvBzZjC6ybZdUtIIk4jge
Vm+rrQS3M6FuBpaTdYqOR/iBVgyccG0KUh79gC+HpD65URLwKrFcYlmapvR6veEC2Hqx0htpdJFt
tZLGmXpTrqUSXKqXnukPlNNRZY9en+K1sh49eRQFEZeLfGcvSgI+BZYLSC9aiIENLYCd7Dk3ssi2
XW7bV6oEC0IezT5+qniTR89rI3oyMCTvUk8+e1ES8EmwNCB9tIXYdd1hxbIZKG49i6r6ZItsq93f
dsRo/gKcSDrLeZNHt9mu57RZWMtdxEpae5ZldLtdAAzD4B3veAe/8Ru/wczMzBk5pxInR0nAy2C5
xLJ+v08cx0O5IcuyTQ25GW1T3k6jh7Yaq/EmF40SZ7s3eT0fIie7i1hqfyyuyyhBf+tb39rQukSJ
rcWZX83ZZihG5xTkG0URnU4HIQTNZnNLiHHUJ9poNLBte0O+3rMdBemYpollWUgpcV0XwzCGdyW9
Xo9er0cQBMO7lPV+IJ5t1XVxF2GaJo7j4LoujuMMr08hX7zgBS/g0KFDfPCDH+SrX/0qt9xyC894
xjN42tOexlvf+tYn7PdTn/oUz3rWs7jyyiu5+uqr+cpXvjL83V//9V/zzGc+k8suu4xf+ZVfOaEt
u8T6IU7xoj37cwxXieXkhkIKcF13WUN+u92m1Wqt+zlHF9mUUht2UcCJweXwg3yDrYq6LOI01yuV
nAqFG8B13RN+vtSbXHy9nrbqJEmI43g49mir0O/3sSxryyvSQhp76KGH+J3f+R2uuOIKvv71r3Pk
yBHuvPNOdu3axdVXX80NN9zAxRdfPHxcr9ejUqkAcO+99/KLv/iL7N27l0OHDnHttdeyd+9eLMvi
Va96Fddddx2vfe1rlz712fMptk3wlK+AC3dDMV4d8jdKt9vFtu0N6bAne84gCGi320gpN30hr6ji
R7MKzmYsd22KDxnDMLBtG9d1qVQqw4S5JEnwfZ9+vz+UdkbbxJ/MKJwml156Kbqu87d/+7e85z3v
4fLLL+e8887DMAx+6Zd+iU996lMnPK4gXwDP807QoovuzuL/Xbt2nbbzeTLjKa0BbySxbL0NDit1
sm1GwwQw1K41TRsuaI2a/5/MK+NLW4dXO5X5yUbKxfkU5w9w6NAh9uzZM9xm9+7d3HXXXU947M03
38wf/dEfcezYMW699VYAdu3axe///u9zzjnn4DgOL33pS3nJS15yGs7kyY+nZAVcyA1hGA5vZT3P
IwgCqtUqlUpl1d7U1b55i4W8breLZVmbXlkX55AkyQlV4ahHNE1TfN+n1+utWBUulyN8tmJ0cc+y
rGGVXOjKaZoOA5MK3bT40NoKnE6tefR51vKBe/3117N3715uvvlm/uRP/gSAhYUFbrnlFvbv38/j
jz+O53l89KMf3ZLjfqrhKVUBL5dYtp72XljbYtdWdrIVAeKFvmhZ1gm/K958oxrwcmE7APtu+xz7
v3o79q5zec4vvIbW5OSmHed2wXKuglG55sngTR4l+uL/Xbt2ceDAgeE2Bw4cYPfu3Svu49prr+WR
Rx5hbm6OL33pS5x//vmMj48D8IpXvII777yTV7/61Vt4Fk8NPGUIuKh2ijfSZiSWFbLBZnSyrUeC
KBYKR7OGfd8fHtNK+1vaAHDk/vvY+08fxV9cQKqMcP/3uf0df0bzkiu5+hW/jGXbZ6Xta7UoKuXi
w+tkDREbyU0+3W6LKIqGr7nnPOc5PPjgg+zfv5+dO3dy4403csMNN5yw/cMPP8wFF1yAEIK7776b
KIoYHx/nnHPO4Wtf+xq+72PbNl/4whd47nOfe9rO48mMJz0BF4tscRzT6XSo1+vrSixb63NuVlzk
SvsPgmAY/rNe21pn7jh7b/oID333OyiVMlZxQWhoUmIIRfjAPdz+ju8z+dxrufjaF5+gnT6ZCHkp
Ma63rXq7XJPifDzPo1qtAvkEj3e/+9289KUvJU1Tfu3Xfo2LL76Y9773vQC84Q1v4KabbuJDH/oQ
hmHgOA433ngjAM973vN45StfyVVXXYWu61x11VW8/vWvP2Pn92TCk9aGttw8tna7jRBiQ6Q1isXF
RWq12hNCuU9mX1sJhTZ8KrvY6P4rlcoTLE3FPLjCE1oEuozuN01THrj1nzhw17+RxhEIiOKUbhhj
GQZ110Spwe2rEIBAGxvn/Be/nHMuuXRIRMVrZ7T9dbMJ6HRYxAoyHZVvVoOlNriTSRdFM0mlUtlS
kh59nscee4w///M/f0Klu4U4858+ZxmelBXwqLth1NMLbImtDNYfF7me/Y8O9FyKpT9bKkU8fu/d
3P3JjzE7e4TpWhUhQAmJbWtYpkE/ijmy2GW8XsGUBoj8UzhdmOPBf/wHDn3jQi6//pdoTU6dEKO4
NExms9LPtnOTxKlyk0fbqkfHH8HWN8wsrYBLbE88qQh4ucSy0ZE9S72NG0VBblsdF1l0fm1k/wuH
D3HfJz5E59BjCBQTFZcFP0AhGK84CCUQUuDaFlXHphMEzPX77Gg287JGCIQC/+AjfO29b6X5jCt4
9stfhRAnzpxbLrh9O96mbwVGP3yW5iYXHvMixGmlWXObiZKAtz+eFAR8ssSyUQ12sz2fBcFnWbZh
PXm5RbPlZr6tFX6/x/23fIK9X/8qk25uv5IChNIYq7iEccKs16Nq27imgSYlGYq641CxLRb7OWGM
VasgFZkCoTI63/sWX3rwe0w8+xqe9WM/NTyHkxHQVlXJG8VWVtmFN7mYiOG67gl68kre5PVek9Fz
6fV61Gq1zT6lEpuIs56Al8oNWZadNE1sMwi4WGTLsgxd16nVapsuNxRVddEUstb9K6XY/+Uv8f1/
uYUkCJhybdpBQJymTDVqyLysxTZNbMukH0Uc6XhMN2poQiIkoHSarkaUpMx2PSqWQcWyQIESApVE
HPvql/jCd/6dc695MZdc86InHMdy6WdP9Sq5KAZWM/Jp6QfVqTBKwGdjBSyE2LJ1J6XUtntRnbUE
vJzcUDQXrKSRbsabenQRTNO0TdV6izdir9cjyzKq1eqaq2ohBEceuI+7Pv5hpLeAZQyqZgENxyFJ
U+a9AF2X1B0LAQgpqDhWXvH6IUmWMlmvAwolJJYpsSyDfhByuN1hqllH0yUqyRACpO/x2Bdv4cDX
b+e8a36cH3ruC056fGupkovfb2cteDU42fGf7JoUBUaxwLeWkU9nIwED/C/nhzZ9nz/tP7Dp+9wM
nJUEXLSVFtXsaluIN9Luu9wim+d5myppxHE89Fqux6WxcOQw93zs71l89BFsMnqpou17TDXyHn8h
BLqp0zJ0gjjhSKfHRNXFkDogEBLGqi5xkrLg9dE1Sb3qIIBUQdWtUKm4LHT79MKQneNNJAIhZb7+
3e+y7ws3s/+r/8oF1/4kT7tqdV7Rk1XJxd1Nr9dbV0V4tuJUbdXLhbVrmja8E4RcgpiamjpTp7Bu
aM4WhBX5T/yREOKngL8BNOB9Sqm3Lvn9zwL/N5ABCfA7SqmvDH7XBN4HXEq+Tv0flVJfE0KMATcC
5wL7gV9USi2udFhnFQEvTSwrNNLRRoSTYb0EvNWLbEXlJ4RYVyJa3+vy9Rv+gUP3fB1X6gip0ISk
5lpUHJPFfghSMFFzKLrPXcfCtU06fsh8P2BHq47KFBm5Z7RV1QmSmKMLXcZqLpZhkIqcGOuuQ6Pi
0PZ8/Dhhx3gDTQgyQChF1u/wyOc+yf6v3cb517yYi654zprOZ2m3WpqmWJa1bEW4Gd1qxe3+dsZa
vMmQR0s++uijjI2NnalDXjc0Z+v/FkIIDXg38BLgEPANIcQtSqm9I5t9QSn1qcH2lwGfAIr4uHcC
tyqlXimE0IEiyegPgc8rpd4mhHjT4Ps/XPE4zgYf8NKAdGDYw78Wy9dqvbYFTtXJ5nneMGdgPRht
qChmey2NXTwZ0jTlwc/dwiP/9gViv08/SlgMfCaqFUxdRwCZUiAhSjI6YUTdtXCMgTwjACGI05RO
ECKFZLzmkimBJgXZ4M+/2A/wgpAdY010KUlzkzCgyFSG54eEScZ0qwECMgUw6MZDoDfGueCaF3P+
5Vet+Rqt5NEdrQiXi6NcS5VcXP+taMopcLoiL4u26o985CN87GMf44EHHmB6eprrrruOz3/+86Rp
yute9zre9KY3nfC4T33qU/zpn/7pUJv+m7/5G17wglxKWlxc5HWvex333XcfQgje//7388M//MPL
Pf2GNSIhhLrtGc/a6G6egB+9/54TNGAhxPOBP1NK/dTg+z8EUEr95QrH9XzyKvlSIUQD+JZS6oJl
trsfeJFS6qgQYga4TSn1jJWOa9tXwEsTyzbSQrzaCni1nWwbkTQK2aSIo1zreKMHv3I7X/vER6hm
yTBSybEMHEtnoecTZQFTdRchNRQKyzSYNE16UciRoMuOZmNwDmBqOpM1g2DgAW64Lo71AzmgbtvU
XZt238dPIna2xpAS0gyk1KlXdFAZC70+YZKwo9UYUPdgTE5njocGFfG517yYC555xbqu2ShGK8JT
6aZna6bDelBck9e//vXs27ePd7/73dRqNX76p3+a22+/fZgF/PKXv/yELOCXvOQl/OzP/ixwYhYw
wG//9m9z3XXX8clPfnK4BrKV0MzTcjeyCzgw8v1B4HlLNxJCXA/8P8AUcN3gx+cDs0KIDwDPAr4J
/LZSqg9MK6WODrY7Ckyf7CC2LQGPLrIVRNfv9zfUQrwawlwpLnKzUJxHFEXD81gLIRx98H7uvfGD
9I4dwUlTjgdR7k6wTYTK99+qOKQZLPQDDKnTqNgoQKCoOjZVx2be65EpmKhXhs0WpmkybRt0/JC5
BZ8dzSpIObwPalZdmlRo9/r4ccrOsTpxmqKEQGoajYqLUhnzXo8kVUy2aqhMDZ4b0s4cD3/uJg58
49/Yc/WPccEzL9vUa3sy3XS5eXOjcZRbTcqnaxFxqQuiXq/T6XS4+OKLOe+88wCGWcCjBLxSFnC7
3eaOO+7ggx/8IMCw8NlKSGPjGvDd3Q7fGszGWwGrqpyUUjcDNwshrgX+O/AT5Lx5FfCbSqlvCCH+
hlxm+NMlj1WncnVsOwIu3jDFi8AwjBNyD6rV6oY7q1b6+Vo72dZaARdasmEYT6jeT7Wv9uwxbnvf
exDHDoLKKzvT0JgxK/TDiCOdLtO1nDClEOi6YMqu4fkhR9oeO1q1fLGMXHoYq1QIBtazmmVRcy1Q
ApSg6tgDD3BAmGbsqNdQMreeIaBRc6mkGce7PcI4Yfd4k0QNFA1dY6xWJUlT2j2fOM4Ybw5W4qVA
ANHCLI984ZMc/Oa/cc7zfpTznnHpqq/hWrDaKrn4eZGZfDZXyaOvIc/zqNVq7N27d91ZwPv27WNy
cpJf/dVf5Z577uHZz34273znO9ckla0Vhr1xAn6e3eJ5kz+YVvP+w4eXbnII2DPy/R7yKnhZKKXu
EEJcMFhkOwgcVEp9Y/Drm4BC0zkqhJhRSh0RQuwAjp3sOLflykNRqRQBOkmSUK/XcRxnQ2+MlR4b
RRHtdntTZrIthyKrt9/vU6lU1pQ3nKYp933q/+POt/8pycF9HO/2afsRQkgQAgVYhs6EY9MOQtp+
3hqsBsdfcSymmxXafsRst08e7yCQUuA6FruaDRCKA3OLRElCTEau9khaFZfpRpUF3+fooocuBQKB
UAJdSFq1CpONGse9PnNeD6lrA/1XoGsaddehVXPo9n3mOz2E0gCBRIBSRPNHefAzn+BfP/Q/2L/3
u5t2vU+Gokou5qkVf4timGUYhvR6Pfr9PmEYDuWvjbpdTqeNbmkjxmqfd7ks4CRJuPvuu3njG9/I
3XffTaVS4S//clmZdNMgDW3T/y2DfweeJoQ4TwhhAq8CbhndQAhxoRhcPCHEVYCplJpXSh0BDggh
nj7Y9MeB+wZf3wIUs5peC9x8snPddhVwUQkWJFyMmdnMfRdYS1zkava3FKMNFadKRStcHaPYd/c3
+P4/foyws0imwNA1xjWNIE051O2yo1ZFoRBSYho6LVORJClHOz1a1QqmIQfrbJKGa5NkKbNeH8vQ
abhOvmAmoGo7OLZNtx/S60bsGGugUCiVV7x110GpjLlenyhKmWrVB4t4ub7aqjokmWK+2ydJE6aa
DVIFUgo0qVHXDdI0ZcHvkSSK8UaFTIEmJAiFWpzl+5/7JA9/7V+58Pk/xnnPeOaa/g4bQVElF4ug
8MSpzMXQ1LV4cM8URh0dvV6ParW67izg+fl5du/eze7du7n66qsBeOUrX7nlBKwZW18XKqUSIcRv
Ap8jt6H9vVJqrxDiDYPfvxf4eeA1QoiY3Mj2qpFd/Bbw0QF5Pwz86uDnfwl8QgjxawxsaCc7jm1H
wMBQgzUMY1OHSRYkt9pFto1guaze1cJbmOc7H/17Dt//Xeb7Pi3XxtL1XD0QAleXWLrGvO8jpWCi
VkUoQAqkJpkxdXpRTLsbMd1sIAbJZpbUmKwZ+HHCkU6XyWo1r6IFgKJesalXbLwwohdFzDTqQ+0Y
qVG3bVJTsej1idKUqUaDTKVIoWHogmZVJ80UC/0eWQZj1QqZUAhA0zWahkuSZnR6PnGSMN6sI0Xu
1NA1iegtsvfWT/LQV/6VC5//o5x/yeZqxCthaXW61AZ3Mg/uRvKBtxppmqJp2rqzgAsL2549e/j+
97/P05/+dL7whS9w6aVbIxkV0MzTQ0tKqc8An1nys/eOfP024G0rPPYe4Oplfj5Pbm1bFbYlAReZ
vVsxVDLLsuGY+Y0usi1XtY5ay9baUKGU4sHPf5qHP/dp4jDEkJLpaoVOGNEOYmZqLmmmUCg0KZms
VvCTlCPtPi3XxCzORUHVtrAMgzmvjyYlY9Vcs9OkxNVMHMtgsefjxTG7Wg1Ah0E/Rd2xqFgGnb5P
mGRMNqsIJVAamBqYukaSZSz2PJIsY6JRJ8lyIpaaoFmpkKQJ7SAkTVNaterQ1qZrkkbVJU0zOn2f
JMsYr9dIVU7UtmWA32Hv525i3123s/uKH+bc00TEK+FUHtzVVMlnYhGuOPaNZAEDvOtd7+LVr341
URRx4YUX8oEPfGBLz+F0VMDbBdvSB1x0hMVxvGmtlEopPM8jjmNc192UFuJiknKxgnyqrN6T4dD3
vss3P/x3HD36ONPVIiYyV0yVyKuZeT/ANXRqjp37x0YIoevnC2YTtQoKhRQDNlUCP4poRxEzzRoI
kWu8AqQQJFlK1w/pJwk7mw1AoIQiXy5TpAq8MCJJUyYbNZTKj0vKPCc4iiO6YYIio1Wtkqn8ucXA
WZFlGb04QWWKVrUyJLMMhZRarvMHAWmmmGjUc1kDgdBk3vGYpmjVJhc+74VccOnG7WvLYTPGxS+t
kov/C0Iuvl4pRnSz4Pv+MJv5ZS97GV/+8pdPZ1W+KT7gva/8ic04lhNw8Sc/X2ZBrBbFm3Sz2nwL
HbYwmdu2varHFW+akx1n8cZbTVbvcuh3u9x34wc59t27IUuZrlRZ8EMMXVG3KzmRKVBSMF2t4Kcp
R70eO5r1watdoISgWXVJspS5fg9daIzVq4hcIcbVLBzXZsHz6ccxM4PHFiTYqlaoZRmLPZ8oTZlp
1klRgEQT0Kw6pGn++xTFeK2ak6tSaJrOWNUkTlK6vo9QgmatQpoBSqHpOjWpkWYpi14fIaFRraAQ
pJlCajoT9TpxkjDveSRJxtRYE5FlaJrEkhpxr8ODX/o0+/79y5x31Qu48LIrV3VtTydOVSUX/xcT
q7cqinK5Cvhsg9SfOhXwtiRg2FiTQ4Gli2yFPLBa3P+lL/GVG27k1//+71Y8xjRNabfba24MUUqx
91/+F3d/6pPUNXKqVCB0wVjFph+nPN7tMl11UYCu6UgJFV1iWwZzPR9NCFoVGzlwQxiawXTdoNv3
ObzYYaZeBRSpAIGgWbWoZibtfp8gTpkZqw9kFIWmSVr1CkmSMt/rk2aKyWZt6OHVNY1G1ckX03p9
hCKXEvILgWkamJZJFMcseH2kJmhU8sU2qQl0Pa/+ojhhrtNDCkG96qJrklRl6IbBlGXhhxHH210U
GdNjLZRKMXQdJQRZ3+PhL3+Wfd+8k/OuuoaLLl8bEadpyqFH99OeO0Zv7jjdxTn8ziK2Ltnx9Mu4
5Pkv3FAVvBSjWnJhcSu+XimKcrO05M3MKDnd0K1tS0ubjm17phsh4JUW2UZbmVeD5OGHiR58gLf9
zMv5g0+f4FAZToNI05RqtbqmxcKjDz7APR/5O/z54zgi5VgvYqIyyOqV+ZuvIsExXBaCCCkFkzUD
RN4UIQVMViv045jD3R4ztRpSkwPJQlCxbaoVyZyXd6ZNDpothNAwdWhVDaIkYcHzibOUqXotlxwG
TotWtUKS5YE8CGhUCukADEPS1HXiOGXR8xESxmu1vGIWYJkGlmkSJSlzHQ/TNGhWXOIsPzbDNJmw
LaI4odv3QUgaVSfXkFWGZepMWXWCMObYQoeMjKlmC03k7dFkCvwu++/8Fx6752vsuuxqfuiK57Aw
P8+RA/vpzB/Hm5+l3+kQeh5h3yMMArI4JEtiJGpQ24MmBDNjDRIFhxdmOfLtr+DsuIBnvugnaE5s
zUTolaZoLDdrbj1VclEBB0Gw5W3PWwWpb0EYzzbFtiTgjUgQJ+tkW+s+D37r20xOTRA9+hhvu/7n
+IOb/+kEa5mu62iatmry9RYX+No/vJd4/0MoMnRNYmgSU9dpBxFxFjFdrZBmecyjpmlM1Vz6ccrB
xR47G7lnVSBRMsO1TFzLYsEPAMV4rZJXrBkgRE5sccqc1wchmKzXyACpgS0NLFMnSJKcaKVksl4l
UxlKgK6C4PI1AAAgAElEQVRrtCouUZqy2O0jdEmrYqOURCCwbIlpmYRxxNFOF9fQqTgumVBIIbAs
Hdtu4Achx9odHNPCta1csiGfUefYNn4YsegFmLpGxbFJUoWQefbDlGXSDyPmFttkQjDdaqAPKtRE
ZSi/y79/5ia++MkPQ5Ki6RpCZWSZQIoUgYbMxRKEAl2SLyYCliZp1CoYmo6UgiTLII7IDj/Elz/w
PapTO9h1+fO46Ipnb8pt/EqLcEsdF3DirLm1VsnF85ytUZRQEvC2wFrJcjWdbGvZZ5ZldI7PUtUN
xnfNMH9wP2/7hV/g/3r/+8myjFqtNnzO1ezroc/9M4988TPMdzr0k5TpgStBDN5UTVcSxjEHOx4z
jVpuy5IAgoqtUbEN5nohQuYjhBASpEApaLoOcZpyeLFL07XRpEQXYAgNzRRM6FWiNGW220OTYrBQ
l4GQOJZFxbbphRFHFztIXTJeq4LKF+N0TdKqu8RJxpzXx9QMGhWHTOULdYZhMGFZBGHMbLdL3c0n
aaQDbdy2TEzLJAgjZtseNdeh4hhkSpFmCtM0GLcMwkEEpqlrVFw337/Mu/KqFZdur8+RhTYKwY6x
JnGScfT4HH4UI5RCahJURhjELPZ7SCS6JjCKuwoFCIEhwTIMNMuk64eYukGSpNiWRZymBFFC3TGJ
FmbZf/s/8+jX/5Xqngu5/IU/iXuaCG0zquSzmoCNbUtLm45te6ZrIcutiIs8cO+9NA2Dw16H3RNj
tNtt3AP7eM8bfp03ffQGhBDDicsnw8Fvf5PvfeLDBJ15pNRpOjZVpZjtBzRdE0fT86aHLMMyDc5x
LOb9EKVgrOrAcKlNMFF36IUJj3c8ZhpVdARI8sQxTce06ix4fTw/YGasiVC5XiGloGqZVGwbLwg5
2u7hmDr1io3KFKnMg3wqjk3fD5jreEipM1ZzERKEFFhSYhpVgjjmWKdL1TJxHBuhJJK8q852LIIg
4vH5Nq1aBcc0UEqQqQzHtnAdh54fcnh+gfF6DcsySdIUEJi6zljDIIwT5rpdKpZFxbFzaSPLqFWr
1Gs1ul6ffYePMd/uIIVCKoEgr7oFAkOX7Bhv5Xp6oasLCSJDArZhMd6ooGn5B14/jPHDCN0PmGg0
kFIRxEme0aEgCfoE+77H7Q9+l8rkLi543o+w+8K1B4ZvxIa22iq52P+jjz7K3r17T8h3OJtwuipg
sYE84MHvNfKOuoNKqf9t8LO3AK8DZgeb/ZFS6rMrHsN2tKEVgesLCwu0Wq0VX7hr7WTLsox2u02r
1TrpdgD3ffzj3HvDDdiOiReETI7VuW/v/VQ0SeeHLuU///0HhnLHcuEkxx/bz96P/wMHH3qQNEuZ
qFby22Zy/VEJ6AQxocqYcGykLlEDDTZFkCQxc/2Q6XpuZxMyv3UWIvc2LHgBiVJM1nJ9N6ex3FoW
JwntIKIfhOwab5Iq0LQ8B0JqeStxNwjpBAE126FiG8M/tBR5wLofRnTCCNcyqVgmSghEYU8TGn4Y
0g1CxmoVrIEEk2UKqWlkKvf4emHEjlYTU9dzK12mUCp3X3hBSC/Iu+40TSPJivjK/Bj8KKIXhDiW
hW2agxFJcGShQ9fz8rl2QoDKhpY5OTgGhMJAoooclLw/mkbFYaxWIYwS5ED6CeIYKSFOFO2eT5Zl
7J5qEUQJhq4jhSRMYgxdQyAJkgizOsbYRZdwyQ+/EHOVUaSbYXU7GQoLXBAEfO5zn+Mtb3kLR48e
5dprr+Xcc8/ljjvuWFcUJeSLl895znPYvXs3//zP/3yyw9gUG9rh//Tqje7mCdjx/350aRylBjzA
SB4w8MujecBCiIpSqjf4+jLgE0qpi0d+/3vAs4GaUurlg5/9GdBVSv3Vao5rW1fAsHzlsN5OtrVU
1Yv3fhcvjnEcA83U6Ech551/Lo/t30/z4e/xzt98I7/5znc9YX/d+TkevOljzN1/b554ZmgEKRzo
eOyoVdE1YKDfNVxJnGbM+gFTVSev3IVAAzTDYEfTYKEfIgS0KnkORlHRjddc+lHMsW4+UNM2JSCJ
s9y30Kw41B2bhb5PnKZMDIYzKqGQCKquRc218cKQxxc7TNQq+fgikedI2JaJ69r0w4jZTo9G1cXU
tQFJClzXxnFsuj2f2U6PXRNNdF0bEKhGzXVpVPLkNC8I2T01Pjw/oRS1iku94tDp+XhByK7JcaQm
cwJVCseycG2bTs/neKdDlqY8fnyevu+jCYk+uOXWB9YvKUU+525gco5zm3J+qy4EY7UKcZpyYHae
c6bGieKUME2wLQs/DNF1jV0TY/TCkNnFLnGqqNomjmliGzphkiIluJaD7y0yf9/XueP+uzEndnLx
C36ciZmdJ309bXUjRmGBE0Lw8z//89RqNe666y6uueYa3vCGN3DXXXetK4oS4J3vfCeXXHIJ3ZOn
i20aTpMN7bnAQ0qp/QBCiI8DPwsMT7wg3wGq5JUwg+13k8dT/jnwe0v2veo/9LYlYFjew7gZcZGn
ejPEccz+B+5nZ6PGkV6PcyfHeLzbYapepdqsE3Y9rL138z/+4Pf5D//lLUA+lWL/rTfzndu+SBr5
1Cwrr7JMA1taVO2UYz2fiqnjGPqgm03DNDR2WLn3N00Sphr1PDUsj0nIRwSlCY93e+xu1pBSoFQe
im4aBhOWSc8POdoNmKlV0AWkRYusULQqg/bfIEQTUB98L1UGmsA2DXZbFp4fMt/rsKNVy21tIs8R
tk0Ty7Dw45CjnT7T9QaGLsgGjRyNqkO96tLu+fTDiB3jY7lbQtdRQtFsVKm4LnNejzBOmWk1EDIP
8xFSUK9VqFZcFj2PfpSwa3J82GGYqQzXMfHjkE7Pp+rYtFwXJQWDXLfhKz3/WMihDSppMQijn6zV
QChMXSdJMg7PtUlVxkS9hq9CjMHtvR9H2KaBbVokaYwfJRzv+aRpwu7JceI0IYxjHNMiVikqSVDH
D/H1T7wPpzXF7suv5qLLr9oW3tter8f09DTT09NceeWVnLeOKEqAgwcPcuutt/LmN7+Zv/qrVRV1
G4bcwmD8EWwkDxjgr4H/DNSX2fdvCSFeQy5P/L4620YSFS/g0Yp1PXGRSzF79Cizjx9eUYIosnoP
P/YYNSFo+z7T9RpHOx12jzc53OnwtAsv5L59+9D9PuHdd/LB//5f+alrn89DX/oXkiikqmkEmk4n
ihlzHdJMkWQJQkgmqg79MOJ432dns55bw2RujBpzbbphxKGOx65GBVS+fq9pAk0z2KkbzPcDNASN
ijNohMu3qTgWjmEw5/nESjHdqCCFAD3vepNAq+ISxDHHvT6uaVBzbDLyhbAsy7Atg0rFptMPCOKE
mWaDTA1kB1EM7bTp+gG+l7BzrJlb+7Kc8Jq1Ko6TMtf1SFTGdKs1yKeQmKZkwqoTxjGLXi4ZTYw1
IVPoUkNp0KrXqSQp8+0uQRSzc3KcNEs5dHyBNI4xDR2hMhR5pauRvzZy8SEvTHIVOK+AhcoJt+ZY
aLqGqWkEcYKQkp2TY4RxjNcPiBWkScxks45t6gRhhq7nLox8Dp5NnGYcXegQJSm7J1r4SYRtmCgB
YZxQsS1Uv83+Oz7Lo9/4N8YvuJiLn/8i7NNsA1uaBVyr1Th06NC6oygBfvd3f5e3v/3tdDqdrT+B
AcQmaMBf3vc4X9n/hAjKUaw7D1gI8TPAMaXUt4QQP7rkIX9LrhsD/DfgHcCvrbT/bUnABQoC3qxF
tqmZGT7xV+/mwksufkI33GhWb7JvHwhBAmQqHz3f7vs0XYej7UUue/qFPHTgIC2vw+Fv3sHf3fVl
fuLKyzBtkzBJsQwdLcs43PfZVa+gSY0sTYiVomaZmKbOwY7HjnoVmak80FwKqrZJo+Iw64UYuhjm
NyhA0wWtapV+GHFwsUur4mIbOkXes27oTNp1ojjmeKeH0iSTlQpSl7kbQtOQusSyTIIo5vHFDmMV
B9eyhvpspjJqjo1jZcx5HkmaMdVq5JmlQgMJ9aqLm2XMtj0ypWjVKwgpkELgmAa2aRCEMcfbXXSp
0ag5uawiBJZl4Vg2fhQx2+kiEYw3a4hMgCZxbAvbMgnCkAOzx1lse5DltjgJg4aTfMFNqnxxsLCY
IfIPAsh1YMs0EFLRCSKcVJFZxmCNQBHGCbph0KwbxElKkiW0/ZDeXMCe6XHiNCUKAlzTIh5YwGYm
xvImkY5HKhR+GFN3HWzLJIxipBDYtkkQ+Sx8/1vc8fC9OFO7ueSaH2dscuq0hb4X8DyPPXv2rPo5
r7/+eq6//nruuOMO/uRP/oTPf/7zfPrTn2Zqaoorr7yS2267bYuO+omQm6CTv/CiPbzwoh988Lz9
truXbrLePOBx4Brg5UKI6wAbqAshPqSUeo1Sapj/K4R4H3BS0XxbEzDkixdFLOVmzOx6wc/9DO/4
9d/kzR9+H7D8Qp7/wAPMeh7nTo1zcLHNOVNjPN5tM+3akCS0e3327JxhdtFh18Jx0m6Pz37rO/z4
sy7FMHR0XSNJM3RN43DbwzF06q6NOZh+YWl5ZTXr+RiaoOHkHwYSgRSS6bpDN4o5vOgx06gghBwQ
D1QdE9c26PZDDnkeO1qNvNodvNEsw2SqpRMlKce9HqZmUHctMpWhSYmhaxi6RrXisOD5HPcW2DnW
RNMkOhKkREszLMMkzlLmuz2EgLFqNZdGBBiazkSjlnt0Ox6GbtCsugOiBdvOHRJBFDPX7mFbFlXX
giwjVWAaBjNjTcIoZr7TQ9d0GrVcGhHAYi8kSRPqFWuYW6HlpS4oBouBed6EHDSfFNUw5GFBdcfG
NI1c641jvCiit9hh50QLy8zdFpoUOLZJ34dWzaJVq3C84xGnKZP1Kn4cYeg6utTo9fuYhsl4vUaY
JHkYUd8nCCJ2TY+jAD+Isaz8NZolKdnsYe7+xw+i1VpM/9DlXHzVE8KzNh0F4fZ6PSqVClNTU+uK
opybm+POO+/klltu4dZbbyUIAjqdDq95zWv40Ic+tKXnIE9PGtowDxh4nDxq8pdHNxBCXAg8Mphs
UeQBzwF/PPiHEOJFwH9SSr1m8P0OpVRRev8ccO/JDmLbNl0XXWZCCBqNxqYNTDz/4megVMbH3vbX
hGFIu90ezmUrnuPRb9/DeMVlttthplnjyGKb3a0Gs12Pna0GnTBCk5JKtYo7s5NzWw0mTcm/fOd+
kjQliCJSwDB1djVznXrRD1EqJVMpUZKRKcV4zcXQDY72fNA0pK4j9Vy/rTs2k3WXY16fRT8kJb/d
T7M8g8G1TXaNNfGihMWej9AG1R+KLAPDMJhu1bFtg2Pd7qDChSTNSMlbnyfqVc6ZGqfrhzx2fIEE
lZOgFOiGpGJZTLeaVGybo50OvSgccKAizVIcy2S61cAyNI61uyRZipKSTDHUqCfH6mgSjrbbg7bk
fKEuVQrDNJho1LEsg9l2l+OLixycnafv94fj7oUAHYFEQ9ckmiaR2sDbyyCsSKmcjAHb0BmvVzFM
nThJsEydSsWhZjvMjLfo+AH7jh7PPwyllpOmbQCSNFVMjbeYHmvSi2L6UcJc1yPOMiquM5BsUlzb
xjIN6hWHqfEmxxY6HDwyh+PkFXWWKRzbJk4TpAA98Hj0ri/ypQ++h3vvvG2YnLbZGK2ye70e9Xr9
hCjKKIq48cYbefnLX37C4x5++OFh9VxEUY6Pj/MXf/EXHDhwgH379vHxj3+cF7/4xVtOvgBC0zb9
3zLXKgGKPODvATcWecBikAlMngd8rxDiW+QTlF/1hB0Ndjfy9VuFEN8RQtwDvAj43ZOd67atgJMk
GU4u2MxbNyEEr3/7X/Cmn/xpLnrOlVz1wh85YSHP931ir4uta2SZIEkTdF2j0w9oug6zix12jzWZ
7XbZPTXBvtk5Zi68kPiRh6HT4+Zv3MMvPP/ZRGmaW8d0jbqb38oe7YfsatYhUyiRNypUTR1dkxxp
e7QcA9uwyGRe1emaZLJeoRcmHF3ssrNVz+MvhUDTJQpBw9WJ05i5Th/L0GhUK/kHl5QolWEZBhP1
On4S0+sH7G41QEKSZIPpxop6zaFWsen0I+I0GcRLgiQFLe9Qq1ZcOn2fwwsddo2PoQwxaBBQQ49v
p+cz1+mxe7KFQpANZtQ5joVbcWl384W2nRMtpJCkAlSa4VgmYZxyfHGBLEkH1bxCKsjSDE0TQ/dE
pgZuB1S+yCbyZhQpBK5tgpQcPLbAzskWZlHpCg3bzqWCZrXCWL3GscUOcZTSqrmEYYxp6dimRc8P
sUydiUadfhSTpSmeH/H47DznzEyhaZIgitB1HSkEQZww2WqgFByZ7xAnKWPVGlEaYFsmUgj6UYBt
Gmgq4fC93+DI/d9mbPcFnHfF8xifOunMxnWjaMTYaBTl0vfO6cByhLkV2Ege8Mg2twO3j3z/mrUc
w7b0AUOuyXqeh6Zpq04vOxWUUrTbbZRS3PCXb+Wuz36R//nV23FG5ls9/NWv8uC73sXjnXYuQbQX
OWdijIOdNjvHmsz1+zRcG6QkzFImGnWOdrvsGG/y7e/cy3w/4PuLPq98/lXUXJs4SUlVbpJPlWLB
j6g5Fq6pIzQtn3k5WHA73umiRE66mVJk5Lf8GbkrYN7zyBCDNDORa6ACGCw9eUHIYs9nrJZru5AT
UzZoyEizPEw9TDJ2jtXRdB2VZaTZIAxISJIso933cQYVniJPYwOGZLfQ90nTlKmxRk7CCpQaHKtS
+cDPJGVyIG0wIGNEvm17MLRzaryJymB2sY0f+HnDxKBrTQ6yJVSWJ7YJFHJwTQrP7+DLPMPYtbEt
iyiOEULQj2LmO10umJ4ETSOOIgzLQGWCIAqxbQsFLLbzRUOh8swL09LJMkWUpDi2mXefZQpd01no
enhBMFyAzARYukGSpiRZNnx+r5cvhqosoVGpYFkmUZzPnrNtkyTNSJIUTTfQGxOce/nVnHPR09ko
ig45y7J44xvfyJvf/Gae8YwVJ6JvBTbFB9x9z5tOveEaUfuNt27LOMptTcCF3WwzQkUK+1qWZTiO
g6Zp/NYLriWMUn7vN/4jkz/2EmYuehrfef/7+c4/3kSzVsVLQlq1Kou+z/RYnSOdLnsmxziw2GbP
ZIsj3R5V08C0bbzQZ2a8xTe+cy9eP+ShxR4/cunT2TM5lrfJZhBnGUplLAZ5KNB41QYlyGS+uIQi
9wX3fKYbtUEwT05CQgqk1PDjhLYf5J1rtjnQQvP1f5l3YjDX7eFHCdPN2vAtIYQcVJKSKIpZ6AdI
oFmr5J5amS+UZeQyRT+MaPsBM80mhiFzchwsGKZkxEk+dFMIwXi9htTzjIrCkxDGCe1eb7AQl+cb
C5FLBwqBH0Qcb3doe32USgbxlfm/VCWoNEOXGo5rUrWcYfRxnoWRV8ZF08ZYzc11YCGwjFx/zwBd
asx3uvTCmKlmFU3m8odpGMSDsH/TMPCjeJA9nNDueOyaHEc3dKIoQdPyLsMginM9WNeYXeyQpCmu
aeZTWwwNTdcIwwhdN9B1jX4QkmQZUZyy6HnsmRzHMHT6QYhpmOiGRj+MsXQNJQSxZrPjaRdz8XOu
WfeQgFECfu1rX8u73/1udu48uT95k7EpBOz9zz/ejGM5AdX/8y9KAl4LCgIGNjSBdWlWbxiG2LaN
aZp8+v3v46Nv/Suu2D3Js84/j8BxEWFM+/ARxmsV2lFIs+rgJQk12yAZuDLq9QrzvT67p8bZNzvH
rvG8MnYsi7FGg7u/ey9+GPK9owtc+bQLedrMZH4LXWiXUuIFIW0/ZKZRg0HoY5JmSF1HCFjo+YRZ
ypibf1gMgiHy20Ch6IcxXhiys5V34WVK5JW2lCQD7bzjB0iRW9AyIfNKeODflZqkH8R0g4iKaeLY
xqDLLZ+aIbVc4mj3+rR7PrvGW3n2xMC/nE9YzrvHFrw+U406pqmjhESTORlKIfD6IZ2+T8V1cK28
Y05KyXy3S9+P0OSgwh5kPxTnqAlI4pQojklVlrccD4y/hU8Ycl+z1w/YMzWOIQVBnKLrciAVJPmi
qJQcb3cIE4Vr6pimjqkbGJqkF0VYuo6u6/TDCE3T6PkhC12PmfFGvhiZJFiGSYYijBIqjkWmVF7J
Z4o4SWhVq1iWTqYgilJsyyBDEQ0W+7p9n8Wux7kzMyAgShIsI8/ECJMEx7QIk4QUyfiuc9l18RXs
Ove8Nb3WwzBEiDzo6BWveAU33XQT9fpyNtUtw6YQcO99/2UzjuUEVF7330oCXgviOB5WrOvtaS/2
oes6rusipcTzPAzDwBrcov/RdS/j0KFD/NTF5zNRb/DQ8XmMTMPIEs6ZmuBge3Hghlhkz+Q4j7c7
zDTrdKMIXRM4ts2i73POjikenV/IE8Wk5JFH9hGEAXfvP8qlF53PZbunUYOpwkiBGhDq4U6PqUYV
TUqSJEEOOrySNCNOEjpRRLPiYus6olh4EoJMCRKVstDLO92mm42c+BCIgogz8KOIRa9Ho1qhaluD
xToxCMvJ5dZeEOIFCTvH6kg52HeWDQgxz3Lo9AI0qdGqu3lymMqdaSrLcwoW+z6+H7Fjokk6GOhZ
SIZCanR7fbwwpFWt4gUhURgNBkiqobc3SwceXoBBEFChCWtC5gHy4gd3BWP1GkkSI6WkF0QsdDzO
2zEBSKI4wTTzD5UwjjFNAyXAG3QGhlHCeK2KZeYDQ1OVYZs2SZKQCLB0nYWORy+KqNk2jm3md0+2
lctKWTaI3UyI4iS/I/B67JhoYpkWcZzk4T+GThglKBSWaTK32MEPYxoVB8sykIOuPi8I89ZnSU7a
moFeqdHccyGXPXd1VfEoAb/sZS/j9ttv37LW5xWwOQT8gbdswqGciMqvvqUk4LUgjmP6/f4JI39W
i1FrWTGhokCv1ztBV/76Zz/D+/74zZw72eTCiSauZeIlCi1KESrNK6woYKLZYNbz2D0xxsH2IrvG
xziwsMBMo0EvTdA0yXiryZF2l4lGFT9LOfDYQbIw4MsPHeCiPXt43tPPpSjjcm7Lb/mP9wJQ0HBN
tEFzhRAyDyVRsOhH9KJwIEvkFWPuhc4rVj+O6QYhFdPEtszhAqYYcRJ0/ZAFr89Mq547CaQ2zB5G
CRIy5hY9ElJmms1B2zBIkbsaYpURJTELXZ+xuotr2gPNd5DxIPKc3U7fByWYaObjhRR5loASAj+M
OHp8nixTCE2g0owsU2RZmudkpJClCfWKQ8V1GDSykakUIXIdWBsQcN2tkAG2qZNmEGcJpm6w0O7i
BSFTzTq6LsnI08/iJCVTCtswCNOEOE6I0pSFdo8dY3Ucx8EP46HkEMZRPtpHCha7fYI4QZNQtW10
Q8fQdfwwwtB0dEMjjGI0qeGFPgttj6lWg6pj40fJwL2h4Ucxpq6jGzrz7S5xmkKWUXVdHMciTTKS
NMv9xGGEJgVS0+iFCa1de9hzyVXs2LV7xXzgIAjQNA3DMHjZy17GHXfccbq78jaFgPsf/vPNOJYT
4P6HN5cEvBasZy7caNOGaZq4rvuEF+BSAgZ42//xau6/5z7+92ufTRpFzPYD5voBTQRTzTrtIKBV
reAlMbahgyaIVMZ0q8mhxUXOm5nksbkFploNokzhJwnTrQZzfZ/52VmyKOC27+3jaefs4bIL9lC1
rNyypQarSFLSj2OOLXbZNdZA041hw4FCgFSkScpiEGPrkobrgsgrxyRTeRC7FPT8iE4QsKORW9+U
UqRKkaYq768XknYv91VPN+ukmSLNa+ZcW5WCIMzJ3NJ1XCcn2YLEhch9you9Potej52TY2SZwtA1
pPhBYFDX92l7Aa5lUqu4SE2y0O0RxvHAs5uBUugyl0UyleUfOEKAUvSDIF98EwqV5UFDZLkFTIo8
9H261Rz6eYUUWIZJEOXh9bquM9/x8MOYmmthGwaarqHrkjBMBiPoNfwgwtA1uv2Aha7HZLNOreLQ
D+LcwQD0omjoZuj28iGlgd+n1ajj2AYIQRglOLYFCvphvr3XD2h7HhXbplGv4gcBFddFqbzCtUyD
KE0Iw5gkVcx3O8y0GjiuQxCEWKaFQhHF8dDSFscpdmMMd2oXF19x9XD2W0HIQRCcyXlwsEkE7H9s
88feO7/yhyUBrwVJkgy129ogSOZkSNP0hKaNlW7Z+v8/e+8eJel1lvf+9v7u9dX90tW3GUmWjCxb
ki9CWJZ9bHAgdmIHixgwrHDICV5gIJhjTHIIWQ74hMPhgLkcYnsRApgVL8DAwbFIYBkSczH4Ajax
wVwsycK6TPdMd1d33b/67nufP/bX7ZE0I81oxl7jhHetWhpNV9VU9/r6rbfe/Ty/Z7V6wsHeA3/x
5/zc//7P0VLydXfeZk7fS8V9BxPsJOX6YZ8z4wlbvY5RRQz67C2WDJp1VkWOkIJ+p83efMF6r8Ph
IgIp2Ox32BnPyLOUYj7ld//6QU71B1y/uc52r21Ms8LIxQyoXJsDOoGhnGGYvFIYPqzWMI1jJsuY
7V7HrIXF8cGUOIHP7I5nSC0YdOogDBNCWjZoQUlJlhVMooTQc2iFIcdgBa0x8jMpWCUp81XCZr9t
XocWFFojpQJhoZVmvkooSxMvXypd7YXFyQ55sYrZP5qyjFd0G3XTBKVt9rdSg6rs1FpXLAeJRqE1
WFJXdmyj8RVQfUQ3bwZxmrNYRieQnzTLcF0HS1ikudn9SimZRBFlobABz/fwXBfLEkRJSs0zb8JR
klCr+SyjlMl8QSMMaIYBWV5SC1yK0uxyfc/sgbPMYCxXcUKrHtBqhBSFIlclnuOZDDihcW2XRRQx
X60QWjDomn29bTvEWYZtWdiWRZykeK7LMo5ZLFd4nkurYSK0PMchyXIsS2LZNkmS4fsuTrPHnX//
NSeM4OPfY6UUH//4x/mpn/opPvjBD/IFrqvTgH/tbVfjtTymgtf9yyc04KeLoxRC+BjpmYeR8v6G
1vqt1WO6wK8B1wEPA1//ZCyIa7oBJ0lCHMdPepBwPhntUmLg4zhGa/2Eg73/8L1v5M8/8qe85Obr
uatbAcoAACAASURBVK7fBmAeJ+xMFvQdh5rvEuU5a902B/MF28M+u5Mpm902O9M5g3aDUgrSvGCj
3+XMeGomtW6HR0ZjfNchPtzn7b/7YV787JsZ9No859QGSqmK+WCjUFiWTZTmjJcrNjvNk6amhT5x
u2mtma5SpDSwHoSoMIxmXaAwO855nNMKPFzPQpVGzmVZRk2BgPkqYbpcsdFtIaSZoqxq9SCEpFSa
0XxOUZSs9z4nKTM7aMwutSiZRwnN0KdR86smqslLRZLnrOIUgCRJyVVhlGPVwVWpNXlREtg23VYd
KayqASsksvq+FAgIXA9pGbuzEIIky9BI4jRlMl9yw+YaAoizAtexkQJWeUHomqineRSTFjlZltFp
1AkCz0zbaW4ocBLKosTzXGbLFYtVgi0FvVaDvNJTF6UxWbhuxTHWEGc508WSwHNZ67ZJ0hwpq91v
XiCFwHEdZouINMtJ0oxOs07guUhpkWQZnusYtq820/18EZFkOWmW0W6GJ8PC8TQctnvc+uWvwjvv
U5xSijiO2d/f5w1veAOf+MQneM5znsP29jb3338/WuvLQlGeOXOGb/7mb+bg4MBo57/t2/ju7/7u
p/q1vToN+L3/75U+zRMqeO2briqOUghR01qvhBA28CHgu7XWHxNC/BhwqLX+MSHE9wEdrfW/uuj3
ey034DRNL8rbPb7ParUCuOQY+DiOL3iwd/bRh/n57/xWjpYr7rnlNEdxYlYBrst0vOSGfpeDVcSw
1WCR5XiujeO6RGnCer/D7nTO6WGfnckM33EY9js8dDCmGfh0O00ePZzQCHzGB2f5gV/6bf7Bl95O
v9Xk9htPE/oeChPwadkWShga2mgeYWlBrxXCsQHBEghhoZRmmaaMFxHrnRaubZqqqlYSlrAptGK+
WjFfpZwedKpDNYnSikKZhi6FYBYlKK0ZdlugNWlZghJIWyIts5ZYxhm+bRGEPscncHYFEpLSYrpc
MV5EnFrrgJDESWYcgaqsXrs5zDPrjmrcrhQZqzSjyAqkhEJrylKBUmRFQZEVnF5fw/cdfM9Fa02e
l3iui0aRFAWOVa0RpgtOrw9OYOuu6wDm9fueg9KQZBlZUbCIEgadJr7roMqSUogTxYNSGs9ziOKE
xcmUb5gYjuuQ5jmWtE2TTTIs2yLOUqazCMexWO91SbIUy7axpc0qSfBcByktVmlKmudEcYaDYH2t
UzGJjUV8lWT4noNGkFZNeLFKcC3N+mCNsNvnti9/Fc4FYrCOmcMAr3rVq3jb297Ga17zGv7kT/6E
06dPc+edd/Ke97znMSS0Y8syPBZFube3x97eHs973vNYLpfccccd3HvvvY957AXq6jTge99+pU/z
hArueePjG/CLgB/UWr+y+v9/BaC1vuD+o7r/z2utn/O4v68Bfwx8u9b640KI+4CXaa33hRDrwB9q
rS8qxr5mnXBCXDwX7krIaBe73+bp67n57pfwyd//AH+6c8BX3Xwa/BradnE9n0f3j3jmxpCzsymn
1wc8fDjmukbILImJ4oRmELA/mXGq1+XRownj6YJT/Q5nJ3PkMmK732VvOqO3cZp/+bp/yA//8m/x
0ttuxvVcmvUGN270Kq2vPMEsbrSaLNKcc9MFm+2mSQZWAqVLpKjiemo+k2XCdJUYA4cQFIUC1+x2
u806jVrAOErQStFuhCBMSrH5GUt6rTpRnPHIwSE116PbaiCdyn0mjoM2HZZJyt5kxla3i2WZw8Ks
KEFpwtCnUQuYLJfsH01J8px+q4EjbROmKQRaYf4MJwYSjaGWBdUUqktjp5VSUypjyFBKMY9TkjSn
XjM24BIzRfuOh0ZR8zzap+qVG2/BVr+DJS3iNDeGCq0pyoIw8PErq3CcZeyPp8Yd126SZkaf7fsu
cZbhOi7DXkCcZMyimCzLaYU1ajUfW1rEcWpkbpaFZTlsDfsGdHQ4RpWKrfU+cZqaQ2AhSPKMWi3A
LVzCICDNc0N7KwpObw6JkhS/UlvkZUEt8BCWpBHWSIqC3Al57t/76osOGo/PgxNCcMcdd3DjjTcC
l4eiXF9fZ319HYB6vc4tt9zC2bNnn6oBX536wig3rghHKYSQwCeAG4F3aK0/Xn1pqLXer/68Dzyp
1fGaZUEAF2zAeZ4zm80oy5JWq/WUK4dLec7jesW3v5H+oMdolaItC8vzQIKnU2S7znS1pB3WOJjN
ONXrsD+bs93rMI5immFArjSH8zmnBj0Wec4qSVnrNImqabDTqLNMEm688QZ++Nu+gT/4q/v5g0/8
NUma8Dc7Z08+b0gpQJpDs7rvs9ZusrdcMV4mCIkJ83RktVKwaIc+YeCxO11USQ5mOjVJGhYKQbte
oxYGjBZRJfGyEcIi12bq9AOX7UEPx7XZHU1Ii5ykKMiK8iS3rlWvc2rQ43AR8cjBYeUQkzi2jSMt
srJEI+l3WmwPBsaqW+Qs04T5MmIyX7A/njCezU+ahT5P32suRl252wSuZdEIa/Q6Ldr1ENtxmMYJ
B9OZUQu4LkpAWZq1gAZ81+EZWxskecEj+4dkFZejLEp8zzeqDcDzXBq1gM21PsKyeeTciOnS0PDi
NMOWRumQZDmOa7PW7dDvtimAw+mCg9kC13WMhCw1VmNRcS421vqsDbqcO5pwOFuSlzlpkeF7Pllu
Yqxc18GybIb9LsNBn7NHY2aLFbNlRFkqfMclTjJcy8Z2XIbb1/PlX/MNl/QpL4oi6vX6BVGUu7u7
T7j/8WT76le/mne9611P+PrDDz/MJz/5SV74wif0p89PSevq355Yl4yjrNYO92BwlMd/r7TWzwO2
gRcKIZ5zgcfqp/p3rtkJGB7bLI9ZvVmWnVDLns4J75NN1a7vc8NdLyH5w//GHz2yz1c+t4NKEuqe
w829Nvft7HGT5zGdp9VBkcU8WtGt1ziYzDg16PPI4RF+HLPWrHO0jOl7LqHvMVmu6LeaNMMaUZpz
/XWneNdb3sS3/vC/Y/T7H+GfvPxF3Ldzjus2hjRqARpBiVECOLZlIEBxwrnpku1uyzjSSkWWldi2
RaMW0AhrTFcxBwtDScsKo+W1pIXjmPTmsBYwni2J4iWbgw6OZSZuKU2sfa0W4Hs+0yhCIBm06ydq
C0WBEIJ+q0Fa+BwtV/i2Ra3mE8UpaVGitbHcSkvgSxe34jToauVhVQdmqyQHkZsDq1KTF+bPvVYT
35PYll2xeM0+23UdfM/By8wKYBmnTOY5vU4D27EoS4VWGt/zKLQm8HyajQbz1Yq9oxk1z8F2HAMJ
sm2jZUbgVh/3w1qNJMvYORjj2JJht82qUhVIaXbNvucR+D5RklBWSM4yz9lc66EFxHFK4AdoNEWp
GQ76lEXJeD5Ha8liuaLfaSMtmzhNqzWKptAlG4MBSZaTJDHzOGV5OOP05hpSCpprm9z+slc85fV+
oQn4UupCKMrjWi6XfO3Xfi0//dM//YUL+bSvHLz1R39xH3/0qfue7C5PF0fZ1VqPz/v7mRDiD4BX
An8N7Ash1rXWe0KIDeDgYs8J1/AEfP7Fc0wtA2i1Wlcd0HM8VSuleNUbvotuv89kFXO0NGqGmmvj
eR4b7ToPjA453e8yWizY6LaYxik13/zST6OI9W6T2SoBIQgDl/FiST3wsCuzQiusYVsWk+WKZiPk
537wzcRFzr/7L79HvVbj4b0R95/dRwpwLHmigBBC0gprbPU7nJ0vOZjMKZXC94wOVQjDhmiHJgro
7DQizlJcW2Lb5kAr14o8K2k3Qtb7HcbLFVGcGilVUZJVCE3fdxh22zRCn92jOfM4rg7orJN8Otd1
aTVqlGh2R0c8uLPHPFqa1yskQgujsBPVSkUauLsEbMeiHvq06yGtekinXWej32XY71AqRV6WLNOU
o/mSslR4lassznIc26FZD2kEHo16jdkq5exogsbsZwulKErTsEulCFyP7fU+ruuyNzXW51IZ1YDj
2OR5ibRsXNfCdR02hn2ajQZnx1MmiwjLtswUXLGEl6uYwHVp1Go06zWarQajWcSje4f4gZGOpXmO
H7hmt6w1g27XcJTDBpNlwkM7Z/GqfXZZamp+QJykWELSajUJgxrDQZt5FOO21i65+R7XcQPe2tp6
WijK8Xh88nvx2te+lm/6pm/innvuuYLfsMssy7ri20tf8Bze8r+99uR2gTrBUQohXAzp7D+ffwch
xI2i+sGfh6McCyH6Qoh29fcB8FV8LsroPwP/tPrzPwXufbJv9ZptwPC5iyqOY8IwJAzDK048fvxU
HUURy+WSWq1GvV7H931u+cp/QL/Z4E8fPIOwbRzbQkvo+Babpzc5mC2o+S6H8wXDVp2D2YLTa30W
SYJW0AgDJlVWm1IwWa7YHHQptOJwOmej16HQiqPFkl67wdve/O1ct77GD7z7P9Gs1yiynM+eOzDW
5Kr5HrvnSqUYNM3rHC1XJzB0LQRFqclLTeA5bPWbSMfh0cMZaW5gMUILHNfCsiWu5zLoNMmBR/fH
WJbEtawT7XGhFI7jsjXoopHsTRbV3leQKUMlsy0LadkEfsDGoIvj2CzjhHm0YhavOJwv2D04JK9k
UpY0bjatTG6cUoYIJ4VAoRDSYthvM+i06LTqOK7LPE44nM6MicJ1EZYJ7HRch7AW0KgFtFsNlmnK
7uERReVQK5SqPuobe7DrumwN16jVahzMlkwWS/LSmEcc2zJBncI6iSca9nsM+l3OjeeM5xGOtEiO
9b5SEiUptmvj+x5h6LHW73I0X/LI2T1c2zT2UmkDmE9SHMchrPkEgcv25gbjWcTO6JBSKZIkM7tk
xyKOM1zXpubXeMYtt3LXK/7RZa/YFosFjUbjaaMou90uWmte//rX8+xnP5s3velNV/Q7d7mlpXXV
b0/4N64MR7kB/H6FnPwY8F+11scxIv8PJjXjAeDl1f9ftK5ZFUSapkwmE7TWtFqtq2apPIbyBEFw
krJxbFM+LqUU7/qeb+Po3D43bK3xnLZH0eigVjNkvc1ndg44HYacGR+x2etwGEU0wxDbdZivEta6
TfYmC2zXYaPfYedoSuB7rPU7PLJ/RBj4DLod/nb/kDDwWB/0eXjviHt/74O8/yN/xo996zfgOi6T
ecSw36HdqKOERpcKYUnsaj9clIqjZYRjWdQCD1taJ/QzaZmP5ZkqmcwW2JZNv90wjAelSUuFFBLL
thBCM1nEFFlOp91Ao7AsxyRMVM09y3ITV28J1rptpBaG3qY0pVZYwsISkKvSSM20ruR1FkmcUKgC
iSTNjaFAYd5ILMfGQlKogk4jNNQ0bXjEEkmUphSqJE0LQNGu17EdGyEEq8Q0K8dxSJKcoixJi4xF
lLDRa+M4pvnmhVFNlFpRlCWu45CmOZPlElUW9NttLGlhO1ZFU5O4lf7WcWy00hxMZ+R5zka/S5ab
Rqy00QR7nmcYELlxxo0XS1ZJTL9piHPH+uUkS/G9gFIZV57nOhyNZ+RliRSaes2Q06SUdLev59YX
fcUlX9fHMrQwDHn/+9/PAw88wFve8hbe//7386Y3vekERfn93//9j0FR/tiP/dhjUJQ//uM/zt13
382HPvQhXvrSl3L77befvAH8yI/8CK985Suf7GVcHSvyBy+Mw7ySCl/2ur8zYlxOHV9Qx9lWV6sB
53nOYrFASvmkKRv//QPv52O/+h85WkS85rbrIWygkxhdq6PTFX+5O+aWXoez0ymnhn12JnPW2g1m
cUqhNdtrPc4cTal5Lv1um52jCY3QTNnnxlOzs2222Bkd0qiHdNttPntun4PRiP/7F97DP/l7L+bm
U9vMVzGu5/IlW2vm471tndiZkQbSPl/FRKuU7X7baGdLRa4NN9ipfm6rrGC6jGjWfDzPxRLGLHGs
Lc5LTZ5lTKOYdqNGzfcqpq8yuXJSIC2bKEmZziMOp1PW+11saaZyx5IVHxgsuwICSYnUmrwssaRA
aEGpFLZjoRVEqwgpJHlRYlmSdr1G4Hs4tkWhoCjKExJbmubkShFnOVIrwrBmpF2VxdlxjI07KwvK
UhGnGctVYrLePBcF5FmB5zvGAVgW+J5PkmZMFgvyXDFoN5BS4rouaZFXCSKV5dgxh5ZH4ylZWdIO
A4SU1UGgIM9NI86LAqU1ru1wNJ1WXAdB3Q/wA9/8PLXhQiSJOeCzpGS+jMjKkjROue1L7+Q5d335
ZV3X5zfg3/iN32A2m33BJ1euVgP+0G9cjdfymApf8rV/14Avp45txbPZ7EmdbZdTx4Q1rTWdTucp
P9r9yr95M0dndnB9m79/y/XMcoXr+6g0Yi5czu6co2Zb1DwXqzqhPz0ccOZoQuh79Lotdg6ntOo1
PN/jcBHRaTTAkkyihE6rjhA2kyiiXg+pBQHnxlOEkHzn//k2vvTmm/jWf/RyolXKMsvYHnTxXNMI
tDDJyKqy9GZKMVmusIVRArgVx0BUdl/TTDWTZUxR5mx0jBOvUPrkEO44Nn62jJkuF2z1TUKxsGTF
qDAYybjITUPMc4qKd6y1ZhWtGPY7eK5LXpY4loWujCa2kBRlgRYGe5mVJY40POSa71MqRZylxElG
IwzwHQfHtimVIivUyWSYpsZMERdF1YhDPMdBCCrHmJk4i7IgVyWrJCdaxfQadYKab3TEhdkrF0pT
FjmOY6Rfk0VEURTUaz6B62LbDnlpzCOO65pGbJuGeTSdk6sC37KNAchzKbQydmHXIS0K7MoROFtE
5EXBapUw6LTwfM849xzXMCKSFC/wkELS3byOW1/0ssu+tsuyPCH+/eIv/iJhGPL61180C/LzVVel
AS8/8r6r8VoeU/W7v+aabMDX9A4Ynlw2dqmllGK5XLJarQjD8ERj/FR1+6v+Mc1WjclixWy5oHBc
fKlQlovnevSHA3zfZxIluI6RJI1mC06t9VllOcsood9uMI8NparmB0xXMa5jE3gO8yjBdSxqns8y
jsnynG6rBULy9rd+H3/x0KN87zvfTVwYhsKDO3vsjRdQTZ0KVeXBSZN80W4gLYfRbFm51iRaCxOB
hKGWDTpNes0m58YLJosIKUQVYS8RlmV2rb7HRr/PeLliHsdIadYds9WKpCzI8xzXMRKxMPDptxr0
Wg1Oba6jtWC2jFglKeP5gt3RIXGSUOgShMS1DfDct00SSOAZV5njWDRrNdqNOmlWsj9dsEpSQzXz
DNUsSTOkLQkbIZ1GA88PmMcJR9OFaY6ui2tbZEWBRhB4Pp1mnWG/Q6Y1OwdjFlGM67oorSkKc7im
tKLQMOh2WOt3ycqSo0XEdDFHCHA8l7RKwbAtizjLaLcabAz6aMtmHsfsjyeVQcQhL5WBHVkWcZpS
D0O6nTaDfp9Uac6cGxnYjmURxTGO6yC1oLG2ybPufPEVX++r1eqS7PvXainLueq3a7Wu2QZ83CCv
pAEf25Qfn/t2qc93610vobGxxbDT5MOPHOE7NmWek1sOdd9mreEzQzJoNxgvIja6beK8YLpYMOy2
mccJjrTwPZfJYkWnESIQHE4XDNotk3IxX9LtNBFCGh2qZeE6Zq/5E2/5XoZr67z5nb/E1lqfm05t
EXguZw7GCCGxhIW0DERHKU2hDGB9c63H4SLmaLEkK5UB1AhjQRZCYDk2g24L6TjsTeYIIRG2JM0K
SmU0qp7rsNbr4Lg+D509ZJGkhnqmVKXMsMgL0ziPqWeWbVUcgwbdVpNWo86pjXUc1yNKcqIs42Ay
Y28yZRnHeJ5jPsZ7HlJYZLnC9316nTb9dptlljOaR6RpRpJnuI6DY9lGSysgDAMGrSau77BIco4m
M3OYZkkc16FUBhvpei6NRp1Bt4USgr3DMUezOb7rGcZFUeIfN+KipNtp0+t20dJivFxxcDipzCsW
SW7A7I5jm2Tkesig18EPfKI05dFz+5TauPPSLMfzfISUpGlWRTf5bGysIW2XM/sjFlGM7dg01ze5
5c6XnHxKW61WpGlKnucn7OOnutaPf2eOVRBftPWF0QFfE3VN64Dh6TdgpdQJT7jRaJysMM5XQFzS
FPzqr+fj734ny2zB6PCIQa+NLS0sVZBqOL21xmce3qUhNIfzBafWuuwcTgiCGr5nlBIbgx47R1NG
kynbwx4P7x1xMJ5yejjgof0RB+MJp4YDHjxzlqPZjE6nTakFi1XCd3/LN/LZR3b42h/4CV7xZbfz
mpfehS0EZw6P6NYb1Ou+oWZpZT7yC8yBW6fJfJWwP5ux2WlXxg5hkiCkwHYsOk6dZljjYBZRljnD
TscA4THRQmWpcB2bjbUe+0djrOr0vywMP6HTDJHC7Htt2zZQdWGA7lleYFs2lpDYtkkhybOMRuDj
uR5pljJexDi2oF2vG1eb7yKFJMkLbMdm0GmTl4rpfE6SlQxadZQGx3GxLYtSlRSFoh7WaTQEiyhi
Gsewgk7TfNJxHCNNy/MSz/NwPY8gKEjzgv3JjFIp1ntdNJBmBrijFZRlQbNhEkWWUcI8SsinC7pt
cx6RJDmWbVUa4Yx6GKK1oBYExmF3dECrFuD5PvFqhRf4lCi0FgbE7mm26uukeUbh1HnuS77y5Ho0
u3RFWZYnlnxx/EmlMsUYdcyFr9/jc5Mv1rqQauF/1LqmG/CT2ZEvVucjKT3Pe4Ig/XL1wzfd+lzu
O3UDWj/Ep/fGhN0uQ0cS5wXK9bGkxU3Xb7O3f8gqSYjjhG4zZLKM2Oh32B3PGE3nnBr2eGjviKPp
0hzaHU4YLxZsrfU5ezg2TXhzyKP7h4wmcwaDLvUwQCG48Ybr+G+/9O957RvezCfvf4h//c++HksK
DudTprHLsNfBrZI0QFJqhdJQr/nUawGHs/lJ/JC0KnKaFmgJSki6rTqrNOPseMrWoFvtho0ETpew
WEX0Wg2SvKQWBFiWJIpWJHlJtFoa62ye0+u0qFcWW9c2qRlZkePZDnmeY0nTfKQlqNdqtJomuufs
eEbg2PieR5Ln2I5tQjurN4F+p4uUgtF0SpLkrHVs8kJRYpQECM0qyajXajRCwSJOOFxECA39dtPA
0z2XUpm1g1sB+V3HvK7RdEZZFqwPBmhhoDeu44IwTblZqTMWUcQyzomnCwadtply8wLPdk8AQb7n
Y9sOQRCS5Rk7ByMcYTHwfdI8J/B8skIhLfPppd/b4gVf/oonXKPHmMnja9pohg35LM9zI+ur7iOl
RCl18hzHTrgv1lLif54GfM2uIM6vS23AZVmyWCxIkoRGo3FBHjBc/lT9vFd/HZbvEzgWj+4fkJQ5
K9vDdV0CW+JYknqvheU6jKOY0PVACEbTOafX+kRpxnQRsTXoECUpqySh12oYQleW0WyErOKUOE7Z
6PeRluTgcIrt2NRrAa7nsLt/wP/3sz/JTTc9g+97538ky3Ly0rzZPHJ2RBTHCC2rdYBRQhwbIdba
bbwgYOdwRlnqE11xUQJaY1k2rXrI9vqAw/mSs4cTnGpXu4hW+K5DlpfYwiQ1F0VJs1HH81z63RYb
a33WBwNAMp4vmUcx++MpO3uHeJbJX7MsYQ4GbctMxdXqwrJsTg0HBLWAM6Mxy8r0YZQKZgKX0qRa
9NptTm0OWWYZ547m5g0CQZbmRrWhjTTNdz3We13qjZDRdMHhdFE138K4zypYkOu61MMajWadRqPF
4XzB2f0RjmXmkiwrcFwbEKR5RrPeoNNp0240mScZj549QCmFtAVJmuK5DkJoCmVet+d4bKytUauH
7B3OOJrMKJRCKYVj24TtDs976Vc95VBg2BgSx3Hwff9EE3+8TsuyjCzLKIqCt7/97cxmM5bL5SVf
39da/d0O+BqqS5lYtdYkScJ8PsdxHJrN5lOqJi61AWutGWyeor59A0GtxuFsxVJ4NHwPFzONKDSt
IEDXQjIFB/M5W70OcVaYKbffZREnJt2jFjCLYjzXwXWMZjT0zMfy2SoGoN2o4/sOB4djHNemHgQ4
jsvO3oi3/os38lM/9G/4gZ97D//p9z7MsN/HdiQ7B2Me3h+Zj+WqrHi4FsKSlBgTw6n1AdMkZX82
J81NTI6ZoIzeV2noNE2TOXs044FHdimKnFIphDBStCzP8TyHJDU8W0taZofqe7iuQ7tVZ9Bp0et2
2FzrM4lW5g0oiplHq0pKZ5vDwazA8xyQAtdx2Vjr4QYBe5M54/nCqBukOXyzKwxllpe0Gg2u214n
TkvO7B0i5DEYqMAPPBzHJskKLGmz1u/S6bQYjaeMJnMTlJkZpq6sTB2u5VIPjZW73e4wiVbsjEbY
jo0tLdNcHQ/QJEmKXwvotpr0+l2Wcc6j5w6IU3NQGiUmSUMrA5q3pNmXr6312NjY5HC2YDqfY3k1
bnvxVz5teaUQBjzveR61Wu0xcPb77ruPe+65h+FwyOnTp3nmM5/Jj/7ojz7hOX7zN3+T5z73uTz/
+c/nzjvv5MMf/vDJ137nd36HZz3rWRd97OezvhBGDDA8YCHEfUKIz1ToyMd//TVCiL8QQnxSCPFx
IcSLz/vau4QQ+0KIv3zcY94qhNipHvPJijl80bpmZWjwuUy3C/F7j6ssy5PwzktFUk6n00vSFp+/
R87imA/+/E+SxxEKyQtv2iLVgkwICgTSctBCcPbcAUQLWjWfTqvF7tgkZUR5SVoUDHs99sYTpGUx
HPQ5MxrjeS6bawP+9uwerufRqAT8s0VElOac2hgSZznLVUJSlGxtrhOtEt78lh8ijVf8+Pd+O45t
cXA0ZhbFnN5cp1lxgo8RiI7jIgUIaZGkGeeOJqx3mnhuxcJV5vu1bZtCaxaLFa7nslytyPIClGax
nLPW6WBZZhoTVeik57qkaVbZfw1/xLUNicx1bEBTCwIW0Yo4y/EsSeD7ONXH8EKVaCWwXRPBlOTm
jW2VpKAK+r1ulZlX5cPZNlorsspgsYhWHB5N2Rh0jK33PIB5WcnkzM5YcTCeUOYl2xsDkrzAt22w
LLIsx3EdLGmsx0ppoyVeLthcG+A4NllRnChG4jTF9TyEhqwsyLKC+WKJLSXrgx5xmpm1h1YUB3ht
0wAAIABJREFUeYHn+6RpimM7NNptbr375Vcl7fu4zs+Du+eee3jf+97Hbbfdxr333sutt956WSjK
siy5+eab+cAHPsDW1tYFH3uRuioytIO/+pMrfZon1Nqtd11tHvD/AiyBd2utbzvvMT8ILLTWP3kp
r+uLYgJ+MiTlfD7Hdd3LMms81QrifPWEZVk0m00G6+ts3XYHluuyiGNGcU4qbSzXx3ddAt/D9zxu
uPF6rHaH6SohyTLqtYCjpUmEKErFaDxhY9AlKxTj2ZzrN9ZI85yDydQ02jRnMlugSk2zERK4LrsH
hwS+X4FyXHbO7hOGIT/+f/0Ad7/oRbzpR9/O737kz6jXQ25+xmkm8zl/e+YsUsrPSaKO9+mAsCSn
N4ZEhWI0XwISpcC27erQa4nnuQYA7vl0mw0ajTrPOH0duYa01BzOFuzsGdpYkqb4nmsMFVJgS7Mb
DXyPsiwIg4C8VDTrdYa9DpbncjhbEmcZShkeguXIasI1cT3NRp1Ou4nrBYwmc5bLyCQtWxZofZJU
LIXEc1xObW+QKc1n9/ZJi6JqvgWlVriOAxVgfnM45NT2JqPxnNFkRqYUWWoYE5awiNMMKS1qgU+z
XqPfGzBfJTyyN0JrYwpJqh2xRJCW5nXUwhqDfpewWWf3cMzhxLBLiqwwB4FVTl+j1eLZL3zZVW2+
j680TfnUpz7FLbfcwvOf/3wcxzlBUZ5fF0NRfuxjH+Omm27i+uuvv+hjP5+lpH3VbxeoLwMe1Fo/
rLXOgV8FXnP+HY6bb1V1TDLG8df+GJhc5Fu45DeiL8oGXBQF8/mcPM9pNptXFUl5rBm+0B75+a94
DV7YpNdq8teP7tEOHFxdQJlT5ilFnpGnKeubm4h6k/E8oh3W0ArTYCt98HSx4tS6+fN8GbHeNxPT
fBGxudbDd10OpzO0FjQaIb7nsrt/QBj4hH6A57nsnNsjrId83T/+av71v/5+fvejf8Y7f+V97Owf
EgQBw36XBx7ZYZUkJ0GWSKtKIjYHZN1Wg1arwaMHY/Iyp1Ca+XJFGNY+lySsDRzHsSVxltJpNfE8
l7Vul62tdUppkZZwdjzlaDZnulhQKBO5nqQp9XpYpR4LjiPlHcdjc2OAEhaPHBwZ67SwSLMS2zE5
a6Uy8rlWs8Fav0emBaPZnDTLyYsC2zHGjKwokJaNZVnUgoDt4ToKwc7+iHkU4TlulcNWScKEIM5S
ev0upzY3mC1iRrMZRVlWRg6BZZlVS6k0Qc2j2WzS63SYr2LOnN0nqwwfaWGCQHXlhLNtc7g36HUZ
DgccVAeweVFSlop6o8mX3HE34efhgOx8VY/WmnPnzj1tFOWlYiw/X6WEddVvF6gL8YC3Hn8nIcQ9
QohPA78FfMslfgtvrFYXv3AM7blYXdMN+PEqiOOpd7FY4HneVbUoX2jqffwe2fd9tp7/QvxaDUsK
HjhzQIYkxSIX5p22AApVsLa1yUJY7E9mbK91WcYps2XE1qDHKs1IM6MhnccJAgg8jyhJiZOUdrNO
LfAYjSdIKamHNVzH5sy5A2q1gFrgY1kWO7vnaDUbbA3X+KEf+rcIz+cdv/xe0ILxbEGzHpKmGbtH
Y3T1cywVSMtCVLFDju2yubFGlCse3h8xmS9ZRTG1wKsMFy6ObQwaruOa0EnXBGAKKQlrNcKax/b6
kEG/h+vXmMcZe9M5izjFkhZZWVT8Bkmal7iWhUAQBD7bG+tkWvPI3ggwh4YSQV4WWJYNAoqyoN1q
sjFYI85y9icLyrw0qcKAXb2+UiukJWmEIf1uD+l4nD2acDSb43k+CEw6heOZ5OOsoNNpsb2xySLN
OJhMyTOTSaeFoaupoiTNDTqy2WwwWBtQItk5GJ1MjVmW4djGjVcWJbbtoIFOt83W5gbTKCJVmme+
4C5ane5VuV6f7DqGS1f73HPPPXz605/m3nvv5S1vecvn86VdcilpXfHtQx//BG9758+e3C5QV8QD
fpL6GeAG4HnAOeAnnuzO17QMDT43rR5DdKSUNJvNK2q8j5+AL6YZvlC94CteyW/f/5d00Tx8cMT2
9iaBBNt2KQFtWWhpPsoPrr+O3QcewHXnbK31OJwvTQP1PcaLiO31AVGaMp4v2RgOeGj3gHkUo6VF
MwwplOZgPGG936MehiASHt09x8bmOkWpiLOC3b0DtjY3KRdL3vAd38lHP/pRfuQ/vJsX3XE7X/3y
l3E4mSC0YHf/iEG3jWUZVYHW1c9BaZSGmhcQeB5KaaI0Ye9wjhYlFhGDbpcyL0DoE5ttWKsRJwmu
a1MUJWklH1Na02iEoDRCCg6mC4qiYKPfMwGjUiKqNI1SaRzHoh6GeJ7PPFqRThf0Wg1cz0UgDEfC
MoaNUivq9TqdTofFYsnh0YTttb5p0nmJ63ggNEmWE3iuCeH0XLJMMZpOUaVirdsxWWz5Md/B/BvN
ep1uu808WjEejWnUQxp1h6w0IHettdnlui6iin7PipyzFdHs1PqQJM1wPROVpJTCdT1KpRgO1nj2
l76Ibn/taV+zT1XnT8BCCLa3t582ivJyH3u162rI0O666y7uuuuuk///qXf8+8ff5arwgC9wvxP+
rxDi54H/8mSv85qegI/rWF7m+z71ev2Kp97jBnwpU+/jS0rJdXe8GM/3Gfa7fOL+v0VlOUlqIpKS
OCaNV5RlSbvZ5tQtt7IzXSKlwHNdjuZLBp0WZVmyfzTl1HCNJMsYjadct7mGbVss45gkS40awnU5
OJrg2A5B4GPbFnsHI5rNJrXAx7Vtdvf2aDWb+L7Hi+6+m+940/fw559+kJ/4+XcTBAG9bhshYHd0
aAhgSp2oHvKyrCJwzCEUEpphSL/fptfuUqu3GM2WzFcxu3sj0MqwJ/KcwPfIKli6AIQ28HhVKmzb
wbYd2u0W9UaD0XzJaLqoLNImu86yZLWXNi6zXrvNcNhnEsXsH00q4wIGGoRAFRrHdkzopetwenOT
KM15aPccWhkTSJzmeK4HwrjPHMel2azTarbwazVG8yV7R2Ns6WBXCg60xnYctAbPcdjYHCIdmzP7
h6wSc7iVVzttDZSFqlxtNVqtFp1Wh3OHY87uj9BIsjTHsl2oWBynnvkc1jae8On2qtbjVxBXgqK8
lMd+PqsU9lW/XaCeNg/4yV57BWE/rq8B/vJi94VrvAEfT73HSMrLyX57shJCPOmu96nq9he+BKfd
xwsCLGmxO4+RfohTC3GCEC1NlM1ytcILPE7dejuf3Ttk2GmRlQX74ynXVcqGyWzB1pppwrPlkvVe
F99xmS2M+qBZr+G6Lrt7+7i2S6Nex3Ucdvf2T/bftm1z9twe7XYb3/NoNpq88V98H43eGv/H297B
n/3Vp3Fdn83hkFWS8NmdfZTS5GVRGQ8KY4JIU1zHpSxLbMuEfIY1Yw1ut9psbm8yjhKWSca5wzHL
aGXUAVlmADyqxPc80yQtk4ohtCAMAjqdFpbrsns4ZVXZmo/dXKVSCAy4RmkYDHoM+gNGkyWj6bzS
LCssx7ymNDX7VikF9bDG1sYmidY8fO6AsiwquZw59LKEebOQUtIM63TbLYJajaP5nL3xmBKFtG2j
dCnyavI20rHt9Q1s1+PM/ojpYokC0krCpsAA3/0A1/doN1tsbZ3icDLl7OiQoigoC8X1X3ILw+1T
V8x3uNQqKqWGbdu84x3v4BWveAXPfvazed3rXsctt9zCz/7sz57gKN/73vdy22238fznP5/v+q7v
4td+zWAgL/bYL1R9IXbAV8gDRgjxHuAjwJcIIc4IIf5Z9aUfFUJ8qmIFvwz4nif7Xq9pGVocx4Z8
Fcd0Op2r8pxaaxYL87HY932CIHhaTf3BT/8VD/3x+ymylMPpgjue9QxyDQqBcBxsv4YSJoYmU4o0
Tch2H+EZ25ucGR3RbTaQrstkGdFvt4myooJ8O/R7PcazOas0p9NuAoL5KiEvFRvrQ1ZxyiJOyArF
qe0txjMDoyk1bG1ucDAeG65DqUmzlH/7gz9IPfT54e/956RpjpBwcDQlz3NuuuE0RakqV1iBVaEi
NWBblpmMbcNfcG2HPC9BChxLnDSlVbTEEQZm43sepdKGM1xFGR2D3IvCpD5PF0um0xnXbfQRwqIo
NY5rn+h8bduCqnEWeckqTcnThK3h4CTZ2HNdtJRk2efSj8uiZJkkrKKIwPfptJqG75CX2G5lrsiL
KlFFMpstDPPXglrNvNFJSxLHqZnqpWSVpHiuR1HmTMYzlC7ZGK4ZPbDvozFySbNuMMGfruMwjyI2
tk7zvC97EUVRAJzYiI9vV2OYOK5jxvVsNuM7vuM7+O3f/u2r9tyXUVdFhvaZBz97NV7LY+qZNz3j
mqShXdMNuCzLEyTl1WjAx7veojC/hI+Ppr/c+r1f+0X0/JDZfIEfhKyv9aAihykEWlr4YR1pOYxn
c0Z75xiQUKvVmK1iNgZ9DmdLlICNwYBH90coIanVarQaDUbTKWlesjboUSpYxglJVrC1tcFsGRHF
ZpLc2NxkOlsQZxkAvcEa4+mMLC/Ji4Jur8ev/vKv8LGP/hHdRoNv+cbXYlsGvpOmpulbQnL61CZ5
XuC7LllemMieosS2BWWpKbWJScpLs2ooqkMwIS3SNKYoFFmSsDnoIKqpwxyMGX2vEgKBQGFYE4tF
xDIydmzLMnAfKUyTKpSZoDXV4WuasopTdJHT73VO9LpuZThJ889NxUmaE6cpSbzCtR3arSbSMisJ
13ONNjoxBDshLaJlxCpNsCQ0wsaJvTfNcmzHMs+fpDieD0pxcHREUZas97tVAocPaMOS8I0tuTvc
5Ll33nXC6a3VaidW4mPOw/lch+P/Pt06bsC7u7u89a1v5dd//dev6Np+mnVVGvB9Dz56NV7LY+pZ
N53+uwZ8uaUq19JkMrkkfu+TVZqmJ3yI47qYueNSa/eRh3ngD3+L1WrJaDLljlueCbaD5fooYVGU
inkUUwLNdptCwd/8+Se5bdhkvIywbZuNtQF/u7t3giwcTRdkZYnrGILXbBUTpxnDwYCsUCzjmLQo
2N7cYrpYsowTQLKxucF4MiNJTQrwYDhkNluQ5jlJktLqdPD9gF/4mXey89kHCIKAb/yaf4hrG4eZ
AuIkBUzU0Ob6AKU0tmUare045FXDM83ZoVCl2fc6RtbmWA5Ka0ZHYxwLeu2m4U4IWSVkGFVLUXEL
hDDQntliiSshDAKDhxSgihJRTYmlUli2jZCS6WxBlmVIoWmGIY7rAppCaxxpUVQ5tJZlJugoTsyK
xLJotponoaDSsrGPo4ikSQZZrWIWy4oX3Tb3tRybJDamCymEYff6ZhU2OhpTqpJmrYa0LFzXw7Ik
rd4aL7jrxea1n8fpPb/OB+4c385nQBxPyJd6zS+XS8Iw5P777+dnfuZnLphu/AWoq9KA/+bBi56F
Pe169k3b12QD/qJQQVxJKaVYrVYURXGicIjj+Ip3clpr2v0Bud/E05oN1+WBnQNObw5R2ZJSC4S0
aLVbaCkZT+cIy+G2u+7mk3/0B7z4S07z0P6Io8mcU+tDzh1N2Duc0Ot1mMyNScHNC1qNOoqIc6ND
ttaHZnqME86cPcf29haFgiTPObu3z8bGBofjCXmcMjo4oDcYQhQZkMx8TlEoXv+db2Q2m/P+976H
33z/f8WxXb7qK15KGASEYc1Mqlqxuz8yqpCgRqMZgja6XKUVlm2RK7MnNmHHEls6xtps26z1+8Rp
ytnxnIbv0AjDSsGuqcTACGkO1hzHod/rkpclo/GEwJF0O23zvNWBnVZGtVEWJUHg02g0WMUxR8sV
gZvhuz6eb9KNy6LAtk3gpUIYxYyUHM3mjMZTo46o4O6F0qiyrJjAGtu2GQz6ZEXBdGZ05oNuC9tx
kEKSFjmeax6bpBm9bhcpJePZnCKJcdKU665/xknzfbJ6KuBOlmWPAe48GQHt8YGcX8wkNAClr+mj
qata13wDhs+pFi63GR+zVT3Po9VqPUamcymM1YtVURQsl0ts2+YFL38lf/G776uUAUvyUtHudCgw
9t7ZfG4m4FYHJSzOnTvg2Xe/jP/+Zx/mOaeGHEwXBKXR9s5XCXuHY05trDOaTpkulvQdA8rRCHb3
R2xublBq0EnKztl9tjY3GM/mxGnGuf19hmtDCj0xduO9cwzXNwBBkmTE8Yq8KOn2erz66/9XRocH
fOqPP8BH/+TjSEvygufdztqgj8ZofgWQ5hn7hxOyNKPTblJvhDiWjVKlMVdobdKSbXmSfiEsiR8E
1Op1DscT5qMJw17H3P9kSKry5tBmepaSwaDPcrViZ39Mo+bSrDfIlVlhCEtSVgdrQoDtOAx6PZI0
ZTSbE8YujWZYuf40WalOpsg0L2g3moiWYDqbEc0jaoFxsNmuMVJkSYbtGukbwFp/QKFLjo4mlOWS
ZmhSTaRt1h2WbZpikmW0Gg2ktLFclzvufuljrtNLvW6Pp91j6A5wMiErpUjTFKXUY1YWj98jCyG+
+FnAQKn/56GhXdMN+PyGeTkT6/lTb71ef0Lu2+U+33EdG0HSNCUMQ0PTqtdRtTaBStjcsPnszh43
WRYaAdKh2WqhhcV8GZGWio1Ns79t3nQbZ/cfpmZZjGdzs2IoFWlRcDCZ0Ot0UJMZR9M5vW6XRlgD
kXBu/4CtjQ2UEKg4Y/fcOTa3NinHU5I05/DokE67y3g6I81zzp07x2CwBkJCIsiLnIODA3r9Ndak
xUte/Toefegz7H/mL3nggQd54LMPcXp7kxtOnUYBvuXjIxENQZZmjI5mlGVOt9nEqYfYlo20TBR9
JrRpyEKiMaGc7XYTQZvJdEaaxEa3q48bkzyOtjOHlwjajSatZpuj8YSdgzH9bgPHlpXMzDRwjaj+
XQvHcRmumUOxcwdjPM9h0O2iSmVkdYDQBodcaE0trNNu28wWC45mS3zPoR7WsGzbrC2y3EjShCbL
Cvr9PlrDZDZlNVvguDa1oIZju+RFYYwjlqTRavKCF774ilO7z6+TmKjzrr/zJ2RVIUOP75Pn+f8Y
DfjaFmdd1bqmd8BPJxfu/Kn3YgqHLMtI0/SyPqqdbwQJw/Axvxhnd3f56z/+HYQqKPKCZZxx803P
oFCaZZKQ5QVhs4Xt+owmE2yvRq3e4L777+cURgrXrNfpdNoczebGLea5tJotJoslUZqyOVwnyXOW
q5isKNne2mIyXxDFGQjB2vqQo/GEVZrhuh6tdofZYkleFKRpRq9nFAfRakWSZJSlYrixYZIXsow8
Lzj70H0s9x9GlgWFgnqrybNuvMkMraJqmlKiS80yiUEpPMekPVuWgdUISyCFTVGWyCriSAiBsGyW
y4g0SxBFQa/T+v/Ze/MgXe6z3u/Te/fby7vOPnMW6WiXjpBsS14AY64B24mVxDgBl40pX2xTkBDH
kAoEqgghFTBQlz1lgq9xQfDFTqjcRLiMDb7Atbm2LLiyLdmWZG1H58zMu6/9br3nj9/br0ZH5xyd
ZXR8RHiqumbeme6e7nn7ffrp5/k+n4cMiUzKQJKRkBftxwrZ4glFkiRanS5RGLC1uiKmLysCkynJ
CrIiEYURiqqJZow4ZTqfM5mMUSWZWrVEFAv0o6yIiccCoq4QhiGqYTDxxwyGI+yCQdHzSJJUNFlE
0cLJq8yCuagdZDAYDImTGEUC2xFITsctcte9r31efSE3MTcvfknYD3keOY7FmKhf/dVf5S/+4i/Y
2Njgve99L7Is86EPfYgkSXjve9/Lz/7s84FfH//4x/n1X/91sizDdV0+/OEPc/LkSQB+67d+i49+
9KNIksQdd9zBxz72sXOe31l2KDngf3y8e6W7eYG98qbqNZkDflk44NFohLUo0JzPDka9F5p2DJfm
gHPU5Xw+X0qVznbqw+GQR778Rax0Qn8wYDAYsb5aQ1IUzIKDoptMg5De0KdaWyWRJOqtDqvrmzz5
2GMcVacC+5jB1sYa/ZHPNIxx7AJWoUB/NCaIEjbXVxnPAsazOXGSsb2zRac3YDYPUTSVcrlCfzRi
Mg1QNJ2VlRWGI58gFIMsHa9IoWAz8n3CQAzUrK2uEoYx09mceTAnjRJ6Z75JNuljGTphlIAqc/zI
sWULM0johiamQczmjCdTVmsVVEVFkoWzjeIIWRYs3XQx5j6flDyZTBmPfGplB0UVci8ZMVYpk/IR
SylIQlEiKzLDkc94NOTI1sZCpyz2HSex0PFm4mJVZIU4iUXxLQjI4pDVlRXBF07FdtmCN6yqCwqa
pjGdzxkM+miyQq1WWQzu1InjRKA4FZUgitEXTnk0HhHM55QrFV7/L77/vA42iiKSJME0zRe91i7X
8kKfYRj89m//Nk8//TRhGPJXf/VXPPTQQ+clmn3pS1/i1ltvpVgs8pnPfIZf+qVf4oEHHmBvb4/v
+q7v4tFHH8UwDH7oh36It7zlLfzoj/7oix3KoTjgBx87H+Pm8u2em8svcMALVORvAwrwr7Ms+7Wz
fv+fAb+MgPDEwH+XZdl/uNC2kiRVgE8CR4FTwH+VZdngfMd1Tcf6F5uCyKNkSZKWc99ebL8Xk4LI
O/By6M+FGkHuet130x5OMK0CGxvrnGl2cRyPOM3odLsEYcjGxiZBGNLu9IR0bDBk4+h1tJUySQqK
orDXbFMplTANnfFURM+e7aDrOmf2m8vpyYois7ffoFwuLSO24XBEqSjmk6VpQqPREFGaaaIbBpPx
GH/k47oeumGgaBqtVhNFVXFdB9O0UAyd6nUnqd36OvxIQlIVNEXl1OlnOL27SxDFmJaJoghVgmUW
WFmpMRyL7rVMZCGQFmkIWZZZaMmQZKExdoslqmtrTBKZvWYvf1NIF29JxgI7JUlkC7WE53msbW7S
GU3Za7RJyYizFEmWl5OfJVkCSagtHMemUq1iukXawxG94RBN0ZAV0f0mS8Lhp1kmWqJVjbW1DYrV
Ku3ekG5ffGZEtC0cvIwEikycRBSsAjtHj/Gd33O4WMkrMWXRIn3ffffxgQ98gHvuueeCRLPXvOY1
FItFAO699152d59TH8RxvAxoptMpW1svbSffQYtT+dCXs22Bo/x94E3ArcA7JEk6u9vkc1mW3Zll
2V0IEM+/vohtfw746yzLbgT+3eL1ee2adsDwQiDPQTs47dhxnOXE44vZ54vhKHPA+8WgLnMOa2Xr
GIblMJ4HFD2P/XqTKBJ5RMdxaXfazIKA9fV1+r0+hmkKqpdTYVpYRVFFPq/R7VEtFTF0jcFwRCaB
W7AwDIO9epOi52FYJiCxt9+gVC5hmpYgqo3HFItFEanLMu12C8e2KRRsdENnNpvQ73ZxPQ9DNzB0
g26nQxhGOI6LoRvIsgKSysnv/UHMtRsJY6hVqpQ9h8loQL3eyM9cSMaQKBY9HM+l0e0z8seCuAYL
WLpEQgbSMpcBCBng6uYGjd6YTm8k3usFHP4Fb48kocgKpVKJlY3cEbdEbnsReMmZmALNgoOcZim2
ZVOrrWJYDq3BiF5/KH6vCqetLEhqqcjao0gKXqlCbWWVVm9Is90RudcoFHI7CeIkwXZsbjt5J45z
4aeoyykeX6qdPZDT87xLJpp99KMf5S1veQsAW1tb/MzP/AxHjhxhc3OTUqnEG9/4xpf0HA5amsmH
vpzDrgRHeaFt7wP+ePH9HyMgPue1a94Bn88uNeq9WEvTFN/3CYLgklGXr3jNd9L2J9TWNpA1jUmc
YBUKDEc+nV4ft1jEK5ZotdsUbAfDMOl2O6xvbjHVPQb6OqKjK6XbH1Etl9ANg06vj6br2AULVVU5
s7dP0XHRF91j/f6AcqmIYehMJmN8f0KxVBZtyopGo9FcjN9xMawCaZrSabdxPQ9NN9B0jeFowGw2
xfOKQs+qqjTre2yduIOdV72JvXFKbzhG0zV0TWF/f59ub4QICoWOWNd1KpXKAgfZIkkXWElF8IZl
WSGVskV+WKQCNE2nXKtiFsvsdfuMJ7NF/nchuZJECkOSnouKFUWhWCpTW9+kPRxTb7WQMkBmgbYU
M++kRcSaZhmmZVJZWUG1bHqjMf3+ULRDSwtpnaKgqGKAp6oqKIqK47isbW7S9yfsd3rM5xFBGOM4
LjffdpLyS0w2uxzLi3CX4vT/9m//lj/6oz9aTr7o9/vcf//9nDp1iv39fcbjMR//+MdfqkN+gSWZ
dOjLOexKcJQX2nYty7Lm4vsmsHahc31ZOOCDEevlRr3n219uB8E8+VijSwW8K4rC6s51RHGG7XiY
hsmp3V00TadWrYkmhVab6soKqqbSbLbY3DpCs9FkZXWdieQwdI6QALMoYORPKXmi0FNvtbBtm4Il
xpzvNxpUylVMwxDNDMMRnuuiazqz2RR/NMIrCqes6zqtlrgmHNtBN00koNVq4HkuhYKNaVpMxmMG
wz6OW0TTDRRVo9NuoGoqJ+56A8rGSU61fHabbaazGWN/QH2vQZxmS6pamoFuWlQqNTqDIe1udzEW
fNEhkUerMs/FE4sxRRtbO0wzmXqnTxSFBwoQInIW6YbFeyeJ6c/lcoVSbZ3GwKfR7ZGSiSJeloiY
dvFns0wIzAzTpFpbQS+4dEc+rV5PpCRkmTQTByRLMimgqSqKrFCwbTY3twiSlF5/yLHrT1AslUiS
5EVTWVc7As4Hcm5tbV0U0ezhhx/mfe97H/fff/+y2/Rzn/scx48fp1qtoqoqb3vb2/jiF7/4kp7D
QUtS+dCXc9hh4iilc+0vExfHBf/ONS1Dg+enIHKFg67rz9P1Xs4+LxdH+WL7u/uVr+Iv/99/y9pK
hfFMFLVUTaM/GJLKEhvbW0xnAd3+iM3tHXqDPoZhMp8HeEWP4dBHrtyC2v4m4+kEVVcpOi7ZeMKZ
/Tob6+tESSZGn7dbrK6tEnUHjKcTZFWjWCwyHE+YBwFxt0u1WmM0ngASvV4f23VxXY8xY8IoolFv
sLa+uWgdlgjDgNGgR6lSW0LvO8025WqVja2juMUKvfYufudp9GhGnI4Zz2ZUV1aoVivSL0f2AAAg
AElEQVTkl5wkS5TKJeZByO5+k3LRxZSF1CtOUhRZA2lOmCSoskq8ILQ5rotartBqNkkHE6plV3AZ
JBmydOF85aUvzzKR+6zVVojiWIDs45i1lZpYVxa5XhapjSSJURZTkWv6CkEY0hkMyLKUtVoNRVVB
lkgWrc0pIp0hywqu53HXXXexvXNkWfjKpWAvFePhUi1vxLj11luXRLPNzU0++clP8md/9mfPW/f0
6dO87W1v40//9E85ceLE8udHjx7lgQceYDabYZomn/vc57jnnnuu2jkkh9CI8bV/+Pd87R8/f6FV
LhtHuVjv4Lbbi/0BNCVJWs+yrLEgo7XO3tdBu+YdcG5BEACcU9d7qXbQYR6UrV3qo9u5TJZl1o8c
w++2qKysMQt3eWZ3j2PHjiMpKqORzyQI2djapNsfIiFj2QWajRZOsYxuWkzDkMLaXcSNr5AMhqzW
VrBMkzhNqbdabG9tkQ6GzIOYVrtLqVxmMIKRP6aqGwt2sJi43Gq1WVldBabIcshk7BNHMW6xiO9P
yDKJZmOfysoaBdkGJIIgpNtuU1tdZzwRI4tGwwG241FwXNJ0i6i4Rn//W6TjNramsHvmDJ1Ol6PH
j6LpBkKvC4ZuUKsZDMdjeoMmO9ubIGWkaYKi6kIZochkSSIcJaL4WVsoFwb9PlF/xNbGKhKL3PCy
RVciey7IFcVG02Q6ndIejomDGRtrawJpKS3GMUkysiToarIso+k6tZVVkjSjOxwQzgM2NlbJI/Uk
TZYdaNVajRM33ACwvEmfT5ubO+NvRwScBxE50SxJEn7sx35sSUMD+PEf/3F++Zd/mX6/z0/8xE8A
oGkaDz74IPfccw9vf/vbufvuu0Wz0d138/73v/8lPYeDlh6CWuyOV34Pd7zye5av/48/+F/PXmWJ
owT2EaSzdxxcQZKk64GnsyzLDuIoJUm60Lb3Az8K/Nri6/9zoeO8pmVoIC4o3/eXud7DuJizLKPf
76Pr+kXJ1i7mGBVFwTAMgiBgNpvx+X//d6zWKqRxwjPPnGJne4PheErBcSk4Hp3+kCyV8Yplnt3d
ZWPrKLtnzlAs1wiCOVGUYhUcpqe+RNHS2N7cYDIXErQ0TdnY3KLd6zGdR9iug12wl0Ae1ytimhYj
f0wYiblotdoqYRAJSV0QoOo65UqN0cgnDEKCMKRcqQmZ2HhCGMakWcbK+iZjf0wYBoRBgFWwsQou
o9GQIIyYzyb49cdRkzGObTOe+FRra2xv7ywvnmzhjOM4pj8YULBMXMdFUVWht9U04iQlTzOkaSry
sVGMogrw+XQyYTIcsLO1LvK8i1bmJHvuhiovHF6SiuLaaOQTxyFJHLJWqxKn4mgURSWO40XaIVsW
+OI4RZJhMBwyn05YX10lSdNlSurVr3nNi6alLobxcJjNGvD8gZxvfetb+exnP3sxmt2Xwg5Fhvbp
h8LDOJbn2Vvu1s8lQ3szz0nJPppl2a/mKMosy/53SZL+B+DdQATMgP8+y7Ivnm/bxc8rwP8JHOEi
ZGjXvAMejUbLdszD6vCJomg51uhSOMDns8lkIiAzcUyWZTiOw6OPPkqz1cIpFBgOhzzz9JPceeed
pJlEuztA0w1sr8TeXp3qyjqthS741KlnWNvYYdAfkKRgOQ7jJ7/IStFgZ2uTwXjKeDIDWQB4Wp0+
QRRTLBVRFE3ofqOYgm1TcFx8f0wcx8yCgLW1DaI4ZTIZE0cxmSSxsrqB7/vMg4U22ithGBbjsU8Q
hCRpysrqBvPFjSWYz9F0g2KptpDoBYRhCEnC3re+iKWCbRnMw5jj15/AtsV7luUKCEliOpsz9kcc
2d4hiIJlwS1aNEHEcYKm6wRhhK4ZhHGIpujMgjnz6ZgwmLK+toosKySLScmZJC0Kas/J4OI0QZFk
ZvM5s+mYJIpZWa0hyzJJHCMpCmmSLGfkxVGCoqqkSQqKjD/yGfsDdrY2+a7v/u7LoufNZrPnuMeH
AN05lx10wG9605v4whe+cOhO/iLtUBzw/f8YHcaxPM/ue6V2TTZiXPNFuEKhgKqqhwK0zrKMyWSy
HGN/uSzgsy1NU+bz+fOKd7fffjvBPCJMMrxSmerKBvv7dZptMc3Cdj0ajSaV2iqT6RTbcWi3W6xv
7NBqNimWqkRxxGwe4t30Bnb7Ic/u1vEW3VeSJNPrD6iUy0KuNhgiyRIFx8YwDSbTKcPBkGJJFNQM
w6TRbECW4jhC/SAh0arXsV0XwzAxdAPfHzKd+LhuCd0wURWVdmMfXTMxDAtNM4iikH6/heeV0DRD
pBwUle94/Q9jrtxEezAmy+DUM8/w1NNPiyKcJPS6mSRjFQrUVtfYazQYDIYiNSArSxZClon/aZaJ
m6UsCe2taZg4bolibYNme0i70xV1PFmGBcxm6QOEJJhMkgULpFzFq9To9EfU681lGkM0cAjcJrIY
lZQtSiqO43D0+Aluv+PkFaFLFUVB13Usy8K2bSzLQlEUkiRhNpsxnU6X7OuLKeydbWenOb6dOejD
MKGeOdzlWrVr3gHD5bMbDloURQyHQ7Isw/O8Q3O847GIMM/V+nzd9ccFHjKT2D5yjIE/YX19A0XT
qTcalMtVJCQmvo+siGnAo9GQcrVKu9NgbX2LYDJmNptSPPFdPNtLeXZvj1qtiq5rzOZzRmMfr1hE
N3Ra7bb4oBcKGIZBuMgBF4uecLCaQa/fI4qjhQRNR1ZVWvV9bLuAZRUwdJFDHQz6eF4RzTCQVY1G
/QyqLON4HrpukiQpnXYd1yui6yaartNu19m47nZuft0PESou09kcfzTg4a99hV6/R7KgjyULjnCl
WkMzbVrtHtPZTDRgpOlC6SDyrCliinOSColZnCYYuoFXqlDwVmh0+vQHg4V2WEKWnxvLk0kyWZYs
9ceablAsV6isbNBsD9jfX9RHDjqvxbZIGaqqcd3xo2xvH14TwkHgjmmaS4esLqZyzOdzJpPJZTnk
qzV146W2NJMOfblW7Z+8A86yjOl0yng8plAo4DjO8pHwSi7YKIoYjUTzwPk65G6+6UbiKCEMM6IU
to5ez9NPn6Je32dtdQ1VVcT3G9t0uy1ct8Q8mJEmGY5TpNNusb51FH84EDSy6+/lVE/i2dN7VCpl
DN1gMp6KoprtoGsG9UYTMrBtG8PUIctoNOp4rotpWZiGwXg0WhRrPHRNQ1E1GvV9NN0Qzts0iaKA
fq+D63jouo5pWvT7XeI4wXWLaJqYj9Zu1XHdhRPWdPqdNrIE13/H9+Hs3MM0UpgHAaeefppvPf4Y
mq6jaTrygumgqBrFcpnxNKTV7jKdzZEVMegTRCkvf5xWFAUZadnSDFCtrSOpNvVmn16/L9qZF3lh
shSQF00dQjIhI/K9ldoqldU1Oj2f+n5jSXfLlqobgcU8cd2xy75G4OJkaGc75EKhgKZpS2lk7pCD
IFimuS70N17uEXCcHP5yrdo174Cv5GKK43iZQ867ww7u93KJaAcd+ovpkG84cZx5GJEkGablEmUS
m1s7iC62fbZ2jtJo1FlZ3aTVbrC6uslg0BMMWkWm3Wqwtr6DPx6QIePt3MmTXYW9epNyqYRhGfQG
A1RNpVAwMXSdXr9PGEW4ruh2kySFZrNOwS5gmgVUTWM+nTIc9nFLJTRNOMV2q46iyBQKjkg1xBHN
5j5eqYJpFtB0A3/UZx7M8IoldN1AlmVazV1sx0M3LHTTZNDvkiURmzvXc+zO70fxrmc8C5lMxnzp
77/A6dNniGOh180bIIqlIrUVwbo4feaMcLILPW6SikaMKI6RNY0kTlAUdSlB0w2DtfVtwlSn0ewz
GA6W0HeRdl7gTGWJNMvIJDHAU5ZVytUqtfUtBuOA3XqLOE7IMgnHtbnz5K2XcdVducmyjKqqyxrF
wSJxrtqZTqfndcgvd/vnFMQ1ZpfqLHNs5MFJyucqSlzqhXs+h36h4ztx/XFkOSNOxSPy9pHreerp
p6k3mmxu7TAaDjENk8nYF80LnRZr65t0mk1cr0KaxoxGQ1bXthkNuuh6AXf9Zh5tKjRaXTzXw9BV
9htNbNvBsiwMXccfjZhMpjieh2HoKIpKs9FA13UKBRvN0InCmF6nTbEkCm+6btBpd0jTFMsSDldR
VFqNPewFK0JTdSZjAcZx3CKqJrgQ7cYuhYKNYRYwDIvhsE8Uzik4RdaP3ML2bW8kkQUbo7F/hke+
9pCYTLFgMiSJiFxt26Va22DkT9jd20OWFOIoRlLURQFLXj7Gp1m60ARLJFmGVypSWl0nzkyajT7D
kU+SZKSLfWeZSG0IClvewiwmdpRKFdY2thlNAkb+mDtuueklBehcikmS9AKHnEOhoigiTVOeeOIJ
fvqnf1q0sjcafOYzn+Hmm2/mhhtuWHa4HbSPf/zj3HnnnZw8eZLXve51PPzww8vfDQYD3v72t3PL
Lbdw66238sADD1zN0yVJD3+5Vu1loQO+FAecJAnj8RhJki7YzXYpkfXFENEuZDddd5RvPLlPZigo
io6i2tRqZWbTGZPxmOrKGu1uF82wMHSDwXBAdWWNTrtBdWWT+u4ZJFnFdUv0e23K1XWC6AjfaNS5
TfMpuS5JNmZ3b5/1zU1kRQVJYjabkcQJpUqV0dgnk2RarSaV6gp2wSHLJkRRTLvVpLa6TjYUF2u3
06FYKuF5JSa+TxCGNOt7VFc2RPFqPicI5sRpj1Kpxmg0JMug1dqnWt1AXqAlx+MRVpbieCWyscz6
9a9iPO4zqn+dLI745sNfxXY8brz1NmRJMH9lOUNRJLximTCO6PYGQMba2hrJgr8bJimSIvS2SSKG
eMZxjKYKKFGxUiYKXYJwTrPVw7Z0Co4DcbzIMS9m1CEceLZoHMmShGKxzI3XH6FWq170+/ti185h
pwRyh5xbzn9YXV3lc5/7HLfccguz2YxHH32U7e1tXvWqV3Hfffc9j4R23XXX8fnPf35JQnv/+9+/
dLQf+MAHeMtb3sKf//mfLzGsV9Pi5NqNWA/brvkI+GAn3MUCdAzDuCiAzmER0V5sX8eO7YjBlplE
nMDqxg5nztTpdNpsbG3TaDZYW9uk12lju0WC+ZwkSSnYDv1+h/WdY4xHA5BldKNAt9PEK9VQ7RqP
7KoMxvNF3lClXm8sBo46ohAXxbQ6bTxX5HINw6Df7xElMY7roRk6WQb1vV2sgr0sJo7HPtOJj+0I
hYSiaLSb+2iajmW7aJpBEkX0ui28YhlNN9FUjU5rH9XQRRpDN5lOxkynPp5XQtEMCnaJ9Rtfj127
hSjNiMKArz30D5x65qlFNJchSJQSpmFSrtawbI/9/QbD4Yg0TVE1TcyiU1UhQ0PwHGRZJkkX1DLA
dUsUyyugObSaXcbTqeANZwApWc6wzLJl7thxbG46cfRFr4trySRJYmNjg3e84x289rWv5VOf+hT3
3nsvx48fv2QS2nA45Atf+AL/8l8K7IGqqsv1rpal6eEv16pd8w4YXjxazZ3kpQB0LoaIFgQBo9EI
TdMu6NAvxpnffuMRoigmTjKiBEynjO16NBsN1tc3aNT3Wd3YotNusrG5w2DQwbQcyGA06FFb32Y0
7GK7Hqqq0e+2WFndRjVdvnbGYDSOMAwDXdNoNJtkgOO66IZGlqTU63s4jouum6iaxng4ZD6bUvTK
i8GWEq3mQpK2SD/MZjORJy6WMUyhdOh0hJTNdl003STNUjqtfSFJ0000w6DTqiPJEtbCCc9nE8b+
EK9YRtVNkjjGqe5w4u63M0/FOPfxcMATjz/KoN9H01QkRV2MlI9RFJVSZQXNKNBotQnmARmgqmJs
kqyKsfRxmiIjLXLGQpetaiqmaVFZ3yKTCzRaPUbDISAjUsQSWZaSZhmaYXDDsQ3CMDy03OrV7ITL
ORD1ep0bb7xx+ftLIaE988wzrKys8J73vIe7776b973vfUyn05f0+M+2q5WCkCTpTZIkPSZJ0hOS
JP3sOX7/TkmSviZJ0sOSJP0HSZJOHvjdByVJ+rokSY9IkvRvJEkyFj//JUmSdiVJ+spiedOFzvVl
4YDhwgCd3EleCkDnQpazIWazGa7rHopeeKVWIYt86vUGzUaTWRBz6tk9lMWkCMOwmI4neF6JTqvJ
+uYO3XaD2so6s+mEYD7DccoMum1K1TXSNGE46LC2cQxVM/hG06UziFA0DVVV6Xa7zGczUYgzdCRJ
pV7fx3aE7EnTDSaTKYN+H8f1FvldjVZ9H9MwBb5SN4ijiE6rgeMW0U0LQzcZ9DtEYSAkaZqJJIlC
nOMU0Q0xrqffbQtHbRfRNYv5bIo/7OO4JTTDIIpDptMh133HmzEqtzKLRDDabtZ57JvfYD6bAYJK
pqiC42taNsVSlWmQ0Gq2RXu6LPS0miYaKDRDI0lTVEUliWOQFOIoQkG0Ha+sbxFh0Gz16PYGojCH
hKzIHNtZZ3NjbZlbfbkVu3zfv2ISWhzHPPTQQ/zkT/4kDz30ELZt86EPfeilOuRzWpIc/nK2SRfH
A34a+O4sy04C/wvwh4ttt4CfAl6RZdkdiG64H15skwG/mWXZXYvlMxc612veAecX07kAOuOxGOdz
OU7yfFHrQXlZsVi8KDDPhSLgLMuW9LYfeMOr2dxYY2P7GBtbx7jptlcwGE0Yj33cYpHpdIKm6WRI
TPwJTrFEq9VgY/s4w0EPVTPQdJ1uu8HqxhGCYMpw0KO6tk2WpTw1KPFsI0aSFUzTZDQaCYaD7aDp
qkBT7u9jGBZmoYCmKszDGaNhn2K5jGaKpopWcx9FVbBsG80wgYxWcx/HXigdNIPxaMh07IuIXDOQ
FZVWc1dgNi2x3XDQJQ7nFBwPXTcIghn+oIvrVtBUgyiMGPa7bF9/J6vXv55YLpJm4onmqW89SrO+
C7KyGLmTCH6EouK4LqsbWwz8CY1mQzRryOoCK6mSISErAtWpKQrIEoqmL6ZsKBimRWV1i1TSafWG
dDsdCgWLG6/bWQ5rzRsn8pTTQYc8n8+Xxa8L2dVw2Af/xmGQ0La3t5d5Y4C3v/3tPPTQQy/xWTzf
4iQ79OUcdjE84C9lWTZcvPwyArqTmwoUJElSgQLPwXjgEjoCr3kHnNvZAJ3hcIiiKHied8n0srP3
B8/vkrNt+7Iwl2dbHMcMh+L9y6PzV9y2TbdTZ29vjzNnThOmMrNZQLOxx/rmDq1Wg9rqGiN/gKGZ
yJJEv9dhZXWTQb+FV6qSJhH9TpPV9SNMpyOmkzGV2iaKLNOeOTzeKNAfzTEMiyAM8X2fUqmMYRqo
C82vJINlu5iGRRRGdNotSsWK0OnqOt12m2QhZdN0A0VWaDb2Ma0CZsFGN0xm8xn+aIC7kKQpikq7
uYdhmJiWg66b+OMhUTjDLZbRDZMoDhn029heGd0skKUxw14Lr1SjsnUSyb2RKFMwDJNhv8cjX32Q
drMpZrmpolmFDMIwwrIcoZgYTdjb30NGcCQkBI5SjJ5PUWVVUNBU8VXVhKKiWKrhuFUKxTWObjzH
9pUXPIp8gec7ZFmWl5MiJpPJizrkq6HLzVMQruvyyle+cklCC8OQT37yk9x3333PW/98JLT19XV2
dnb41re+BQg05W233faSH/9BuxoRMBfJAz5gPwZ8GiDLsj3gXwGnETCeQZZlnzuw7k8tUhcflSSp
dKFzfVmoIEBcYAc7zw6DipY74LzSmzv0S+2jP5czP6iaUNVcQiXhuTbHNmzqQxPTNMmylOGgz7Bz
hm63zcrqBu1mg42to+zvnWZt4yh7u8+i6SZWwaXbbrKyfoT9M8+gqCOqK5t0m3VkT8Urr+CPBsyD
Oa3wOgaNU2xUhLPo9jqsVNfoZ0NSoNvuUK2sYBYKJGlKEIbU63usrm3i+2MkOcAfjbAKCY7j4Y9H
gEgRVFfWAJmMGVEUMug2qdQ2GA4HSGFAp7lHdXUTCZtMkplMfNI0xXZLxHGPMJwzGfXwSisMBz3i
OGTYb1Esr4GkEJge4/6z6NKAlVqZyXTEY19vs3P0BKZlCwi8oiwQmlBwXbTQpNcbEMcRa5sbRFGM
qmrESYyu6syjEFXRmAdz0WgSRqiqSpwmnDi+w403nCCOY+I4fh6v4WDTzsH3+KCmPEkS4jheMhle
KujOuexgjjlPQVwJCQ3g937v93jnO99JGIZcf/31fOxjH3vJz+OgHYZs7MlH/o6nvv53F1rloh9P
JEl6AwLG/rrF6zJi8sUxYAj8X5IkvTPLso8DH0bMkQORtvhXCOd97n1f6zAeELCRwWBAlmULHeuV
A3Rms9kSHXi58rLccgdeLBZJkmQp27Ft+3kf3Pl8TpIkWJbFF778OJ2pQr/XIZjPyJIImYj1zR2m
symSoiPLIj9cqa2zv3uG6toW3XYLSVYpFldoNE5jezXiMGY8Hgl4uFfDH/YJwxmGYUPkU7PbFJ0C
SRKztrbFdDZhNguE0sLz0DQDfzhivuDbrqxuMp1NCYKQOI7QdJNiqcpoNCSKIubzgEptVYB1plOi
MCBLobK6wdj3CeZTojCiVF0hzSSmkwlREKDqBo5bxh8PiIIQSVYpLW4aURQAEqXKBoNBhyiYEycx
8fApTD3Dtm0m0wkSMkeO37QkmQVhgCKrSIvx8GEYMBr2SZKIIzvHCOYBumEwnU/RNIsoDDFMk2Ae
YFoWmSTx/a+7laL33GihnGh20CEDz4Pn5O9p7gAPOtuchhbHMSCUBIcF3jnb0jRlNpth2zZ/+Id/
yNraGu9617sObf+XaIcC4/m1Pz/81rWffbvyPBiPJEmvBn4py7I3LV7/j0CavXAw50ng/wbelGXZ
k4uf/ZfAD2RZ9t7F6x8BXp1l2X991rbHgL9Y5InPadd8CiJPDaRpimEYh5IayPcbhuFFDdx8Mcs/
kAcLgoVCYQGUyZZFPWAZobz+NbfQqT9DqbLGzvEb2T52s6jS1/coVVbxR4KYlmUpo+GQcqVGr9Nk
ZX2L+WzMZDKiWFphPOxhmAXxeJ2mDHtNHK+CodsEwYw4M+gmt/LUmSFRlNJqN4XSwbRQdI3RcMh8
OsUtirlyqqLRatXFlAzLQlE1gmBOu7W/nJRhGAaDbps4inAc0ZaMBJ3mPq5TxDBtNN0QhbhUYDUV
TScKA8ajPq4jUhZpEtHvt3CLFRRVJ0kT+r06xVINTRfjlJy1k0T6No1mB9f2cDyP+t7TtOq7YrS8
qqOoIkoNggApkylX1qjWttjfb9DptAnjGElSyNIURRPTmRVVJQxDbji68Tznm7+fOV7Utm1c18W2
7SWvIQiCJachd6hnpyy0BfQdeAF452DK4krzxOeahvFytyTJDn05hy2ZvpIk6Qim7/0HV5Ak6QjC
+b4rd74LexZ4tSRJliT++W8EvrnYZuPAev8F8MiFzvWad8Dw3LTXw1A45I5yPp8jy/KL6oUvdp95
JOI4YoJx/sGKoojpdPoC9KUsy/zQfd9JlkZMJjPO7O5iuRVSSafdqLOxeZRuu8Xq+g5jf4AkKSiK
RrfdZH3jGGN/AJLQBQ96bdxiFdNyBCWtvYvjlTAMmzCOmIy6aJVX8cS+Qn8wobG3T6FgY5kFDMNk
PPaZ+COBojRNVFWn1aiLOXKOh2FapBm0mnuL4Z5CyjYaDJj6I2y3iKaJUUnNxmkKto1h2ui64EdE
UbCkq0VRyGjUwylWUDWDLE3ptfeErlkzSZKE7uK1pov1DavCxs1v4okzfZ5+8il8f8Kg3+XZpx6j
3WoQhQlRJJyxrKlIi9H0rlfGcsp02j16nfaiSCeTximqKtgLN1+3+qLv70GHXCgUlg5Z07QXOOR8
/TwKzt9vVVUxTfMlJaHl0zBe7nY1dMBZlsXAfwN8FuE8P5ll2aOSJP24tGACA78IlIEPLyRlDy62
fRD4c+AhIG8h/MPF119byNa+Brwe+OCFzvVlkYIIw5DxeIyiKFfUHnpw9JCu6yRJcsURQ14dT9OU
Uqm0jGrydmgQSM3z5QP/4WuP8/n/uMfW9nFkWUQxe888wtHrboBMYjqfUa6s0qjvidzv7rMU7DKS
LOOPhhQrG7TruyRZiutVSVOZyWRIFMxxy+sE8xnhfEqSRBSrWwz7HQrJ02yu2WxuHyGMIgFgD0I0
w3heqiEKI7xyFU0VmMoojkjilOrqBtPpjPl8ShSEKJpGsbKKPxwSxyFxFFGpbTCbzwnmc+IoXKgj
XIajPlEYoCoaXnkVf9QnDOaARKW2xXDQJQzF9JP8dRBM0RQN26sxGnXp7D4CYZ+CZZJmCWmSUays
cOTYCaIoEo0W8mIwpywTRSJFMptPULIUr1RBNwxuu2GLW2/YOef7cil2EMKepy3yz1UeOJz9OTuY
tjgIb8+y7AXw9gs9mQmFSIRlWfzcz/0c7373u7n33nuv+Jwu0w4lBfE//+nh84D/p3f9Mw/4su1g
N9zl2tnKiXN9KC7Fcgc7Ho+XNwXx4c+WeWBVVbFt+4LFmFfdeRO337QFUsZ4MqPX67Nx9Hbq+2cw
CgWiUETQBdul3aqzunEEf9RHUXVkVaPfbVLbOIKi6IyGXZIkwHbKyIrGoCuiWLPgoSgGg/Yujlcm
NG/lG6dCHnvscVRZEdGcIWRh/V4HzxMpAk03GA0HzGYTHK+IblgoqkKrsY9u6Ni2J6YsJymDbhuv
WEZWdQH/aeyi6bpoxjBMptMJE3+I55YXOMuYXqeO51VRNfGo3m3t4RYraLoJkkS3vSteawZREtPv
1fGKNVaP3EXl6OsIKRJGKamUMRp0+ObD/0in0xTDO5GXjRyqqqPrJsViDVm36fV7TPwBN19/OJjJ
PELOlRK548yvi4MRch6x5tdJ/jNVVbEsa1m0vVg05dkpiH8KEXAcp4e+XKv2snDAcGX0sly/6TjO
Mg1wJQ797PbkPEUynU7xfZ/pdIqmaRdd1HvDq64jmPTpD0asbR5FM20krcwzTzzO2uYRRv0elu0R
RxHj0ZBipcaw16FSXiOOQga9DqXqGppuM/FHzGYjvNIKulnAH7SRSLGcIopq0iJAiWEAACAASURB
VO/so+kadvkmnu1W+I9feYwoioSqRNeJo5hWu4HtFjFMC13XmU4nDAd9XLeEppnouk631UQiw7Yd
dEOoOXqdhkBTmhamVaDbbgAphllAVQ1mwQR/1MNxRNccWUa3s0dpkX6QZIVOU9wkNM0EJLrtM7il
FTRd6Lx7rTPYThHDKFBcvQFn9S507zjzQOiEB702zzz1TXq9NiCYCZIsk2YJURRhmCYbW8f4T7/v
NYeuUshVOpIk4TjOMmXhed5StZPXHg461IORcB495w7ZsqxzoinP5ZB93/8n4YCvUg74mrB/0g44
1+HmEPaDsrXLdcDnKrTBc7KkPNeXN2D4vr/8wJxPJ6rrGq89uUK5XCFNE/qDEW55HcNeoVk/Q3ll
jU6rztrmEfzRAEXRkFWVbrfBysZRgplPp3UG2/XQTZs4mDPxe7heFcWwmEwGhPMJBa+MrlsMey0k
CbzKJqPsGH//4Ck6nd6iddlAyqBV38MqCHylrovOtU67geuV0HQD3TDoD3tEUYTtFlFVAWnvtvcp
emUMU2zrD/uQZRRcD123COZzoQN2BBsCJNrNPdxiGc0wkRWFbuM0jlfGMAqATL+zi+OW0PUCimrQ
a+2i6yZGwUXVLRS9zPYtP0CsrNDvDUiiiE5znycf+xqDXocoCEgzUFQNz3X5F/eeoFY5XL5BHMeM
x+NlFHz2jVeW5aWCx3Xd58kowzBkPp8vVRP5tvkorjwtkeeQDzrk3BF/5CMfIYqiQ6mTfLvtnx3w
NWaXGrEexFFalnVeHOWlWB7dXKjQlgO1DxZr8vxvPocud8h5uiK3G647wm1HNGazgCjKsMwCqlmi
1epBBoqqMhr0qa5uMOi1qdREfnfsD/Aqa8iSSr+1L6JDyyVOEoa9Bp5XQ9UKzOdTZpMBBbuMblhM
/T5RMKPglFEKx/jHb8x44sk9AdExDBRVo93YR9U0LNvB0MVNpdncE+3NpomhmYz9IZPxaDEKSTx+
t5q7Av5uFtB0E3/UI5xPcb0yhmWRZin9XgvXqyArOpkE7fppbLuEbhTEzaX5fCfca53Bsl10w0LV
DXrdOrIEllNEVQ0G/Ra1zZu5/u63MZpqDIc+WZaye/pJnnjsYaaTEZ5r88bX3Ei5dHhRYu4Ip9Mp
hcUkkot56skdsmVZuK6L67rLm7iQ+s1f0P58LoesqqLj78yZM3z1q1/lhhtu4Pbbb+e66667LBRl
/nfuuusu3vrWt17hf+fy7P9PKYiXVSPGxdLL8sfAYrF4Xsd7KQ49L7TlvIlcbpQ3XGRZdk4nf1CU
bxjGMu8XxzFhGDKdTlEUBVVVUVWVe+48xiOPfwGveIQwipnOAnauu5Onn/o6N916B7unn0EzBFC9
32myuiGKcrZdxC3VmIz69Dp7FMurZJLMfOrTa+9SrO2QZRAGU5Koi+2tME57hLMpSZxguxWyLON0
a067/yw3n6ig6zqRJNPrtHDcEo5TZDIdEwQBreY+ldUNZFlE9bOJLzrLyjVGgz4Q0W3VKVc3BK9X
kphOxyRJiuuW8f0hYRgw7DYp1zbw/SHBbEKr+SzVlS2SJCEioNV4luraDtkIQmS6rV3K1XXREZdJ
+KMuhuFQcEpIU5nZ1CdJE47f/t2MRwNeeZPHDcer+P6UM7t7fM/rbsIuWBf1nl+M5Tf6vJh7JTf5
3CHndrCol0vWztYhxzleU5L4xV/8RR544AG+8pWvcMcdd/DZz36Wm2+++ZJRlAC/8zu/w6233orv
+5d9PldiybUM8D1ke1lEwLldKo7yQh+Ii3HA2YHpF5ZlYZrmUmqUF9oURXnRQtvBv5mnKGzbXpLb
gOWxv/UNt6AyZz4PUVWTNAXZWOGxbzzM6voOg16bcmVNEMbGY1yvzGw2Ipj62MUqmm4y6DbF3ykU
RTGufZqCXUQ3XdI0we/Xcbwqqm4RR3Mmfhd78XoauXz54Qln9n3SDDTDYDjsM5uOxdQLXaQJWvt7
SJKEVXCxLIc4Cul3mhRLFSFTU3W67TqyDJZlYxgmwXzKaNTD9SrougmSTLe5SC9YNpqq02vtLtqW
bSRJpr1/ikJB4C9V1aDfbUAaU3BLKIrBbOYTzHyRN9YtwmDGeJF+ue5IjeNHNjl52wn+kx94/aE6
31xRc76b75VaPqboYISc64qjKCIIAqIoot1u8+Uvf5nPfvaz7O3t8c1vfpOTJ09yxx13XDKKEmB3
d5dPf/rTvPe97/22wYfSBUT/MJdr1V4WDvjFuofy9MCl4ChfzJIkWU6/yAtteQ53Pp8zm80oFApX
9LcOOmTHcfA8j0q5xN3XawwHXQzTZDYL0C2PQnGLRmMXXbfotpvU1neYjYeYlotm2IRhwHjYXTpW
v98SxTe7hKLo9Du7WFYB3XLIJJl+5zS2W0LRRIfceNDCdmsomoWq6ey2VL7+ZEK7NUTTdGbzCf6w
h7cokCmaRq/bQpIzLEekBtIkodOq43hC86sbYjxRmiZYdnGhA44Y9JrCYRomKDLt5mlBUjMtFM2g
XT+N47iYBRdVN+m2dtENE8OyUVSD4aDLfDyi4JTQDZs4CvEHHeyicMJpnBAGE45u167oGjif5U9Z
qqoeSlfmxdhBh5w3IymKwv7+Pj//8z/Pu9/9bo4cOcJHPvIRdnaek9ZdCooS4IMf/CC/8Ru/8e0a
aw9AHCWHvlyr9rJwwHD+iPVc8rIr2d/BjrY8R3d2R1uWZbiue1kQoBc7Jk3T+I7br+f2Y+JDNg9i
TNNGkgv0umN002I+mxAEc8yCI5yZXcSwbHHTGDTxSiuous3E75HEMyyngqqZ9Nr7aJqBYXrIis6g
u4ttu+imTQYMumewCkU03UaSVebziIa/wdcf7zMezwijkHa7ju16WKaFYZj0+13CYLbATIoIs93Y
FQS0xZij8UgUAW2vjK4bJGlKr7UvttEtVFWj1TgjjsUooOomncaZReRso+omo34LWea5SDeaMfF7
FOwismqILrrWPrYrnLJCdMWskHNZno7Kn4iuhvM9aHmxzzAMdF3n/vvv57WvfS31ep1f+IVfuCQV
xNkoyk996lOsrq5y1113fVvRm1erCCddJg9YkqSbpOd4v1+RJGkoSdJ/u/hdRZKkv5Yk6VuSJP3V
i8F4XrYO+HzyskvZX76f3HIHmyMuz9fRdhh84Bez+77vJJY0JkFGUWSCMGF16xZOPXVqIU3rYtke
YTCn0xaqAKvgQQaDzj6OV0HVbeazCeHcx3Er6IbFqN8U0yYKHrKsM+jWMS0HVS8gywqj/h6abqKb
DopqMvW7pMoqzzSqPP1Um9l0SqfdoOC4Yv6bbjLxR0z8waJV2USRFdotQUUzLBtVM5hNx0z8Ic6i
DRlZotvaFaoKo4CmGbSaZ7CsAqZVQDVMuu09jEIB0xJO2B/2mE9HuKUqhulAljHqNfCKZXS9gKyo
dBqnRbSsqxeFjLxYy1NcOXfhpXDuL2b5NWhZFmEY8q53vYvjx4/z4Q9/mGq1ypvf/GZ+5Ed+5LJR
lF/84he5//77OX78OO94xzv4m7/5G9797ndftfPLLUnSQ1/ONukKeMBZlj2e836BVwBT4N8utvk5
4K+zLLsR+HeL1+e1l4UDPlsFEUXRUl5WLBYv+8Nw9j5zDnAeReSRb65aODgM8aU2WZZ58+u2iAOf
NE6IU/E/0N1tnnnicQqOx7DXZmXjKJpu0WvXATF5OZNYtCNX0fQCYTBlOhlQcCpohsVkKAZvmnYR
RdMZdPYwjAKa6aKoBuNhizSLMO0SqmYRzsaE0YxQvYlvPhHQbHSp753GNM0l+zeYzxgNews5mYWq
6nRa+yiKQsERqYRwPmU06OJ6FTRtITlr7VFwHAzTQtNMOm3BKzZMG00z6bV2kSQJw3LRdIsonDMe
LGRsuomsqPTaexRsB8v2MMwCg26d40fEZIuzlSeX45DzWkBO4bvaUq+znX+z2eRtb3sb73nPe5aD
OHO7EhTlr/zKr3DmzBmeeeYZPvGJT/C93/u9/Mmf/MlVO8/c0iQ99OUcdqU84NzeCDyVZVl+17sP
+OPF938M/OcXOteXnQoin1CQO8MrtbP3mffpS5K07NfPZ6ld7cfN1ZUS3/MdFR781pxMUsTQSsVC
czYZjwdkqcSgW6dU2WRIh8l4gGV5FOwSY79Pp3mKcm2HNIUonDIZdbC9GlnaZz4ZopsOll0iS3uM
+vsU3Bqm6REwJpyOiZUQs1AmTlLkNGTqt/Aqx2mPfFqd0/ijMcdP3EjBdpnLE4L5nF6nTqW2ydgf
QQb9XhvXq2A7JSbZgCgM6LX3KdU2mYxHZNmMTn2X2to2eSdrr7VHqbZJVoCMjGGvjVnwcLwys8mI
KAzod3cpljeYywphMKPX2ccrrWAWPDKgWlKWNLq84ywfNZSPfc+XF6sv5MXWq5XvPWhnKy2++tWv
8sEPfpA/+IM/4BWveMUL1r9SFOVBu9rnmttVytmeiwd8oR7uJQ/4LPth4N8ceL2WZVlz8X0TWLvQ
QbwsWBA56GY0GqGq6qFVnfv9PrIsI8syhULheejIvMqct4ZebYuiiNlshmEYfPLTj/JUy8SxYDIF
w0jptfZYWxcOiUyitLLNqN9lPhtj2UUUWWfsD4iiOaXKJpPxmHkwhhRKlU1Gox5RMEUzCuiGw8Tv
E4UzdMNB021m0xFxOBP57tIa89mUOJwQhwFOaZ0oCpn6HUq2zw03HcMrVZiMhgRhQJZBbXWL8dgn
CgOCMMCyXEzbwR8KJ5xlEpWVdSbjMWEwI4wCytVtwnBOMBPO3CvXiJOMYD4lCQNkRcUrrzLxh8RR
SBTPKZbXRdvuzCcM5lgFB8PyePO9ZW68buMF/9eDUsD86/kccg5dz/OtV9shpWnKdDoVahPL4lOf
+hS///u/zyc+8YlzphWuATsUFsQ7f/78RcOLteazX6T57JeWrx/5+988G0f5gwjE5PsWr98F3Jtl
2U+d45jeAPxvwOuyLOsf+LmOmIRxa5Zl7cXP+lmWlQ+s08uyrHL2PnN7WUTAcRwvNYkXK/m6kOWF
trzl0zCM5aNp7uwVRcF13W9LxJPjCnPn/4PffxO//SdfJU3LZEAcJrilIzQbz7K2USOYTIRGtrZF
mmbMxiPMgo3tVZn4ffrdfUrVTZBlZpMR/e4+TnmdJE4IpgJwbztlxj6EwZggmGHbVeYoJNGMYW8f
p7iGJCukmY8/aGLZJRxvnfHM4oEHTnHi+j5Hjx8jlSTiMKRVP0N5ZQNpoQOeTX2SOML1KoyGA5Ik
pt3Yo7a+vfgfS/Tbe3iVVcyCQ5KkDHot3GIVxykxnQwFq6KzR6myQRDMYC4xGrQpWA62W4asTzCf
omkG2+vnrn3kypP8pnrQIecNFTkAJ0mSxbTpq5/vTZKE6XSKqqrous7v/u7v8uCDD/KXf/mX/yTa
jS9k50kZXJKtbL+ale1XL18/8ve/efYqe/D/tXfmYVaUV/7/1HK3ulvvzaqIYAAXJJhgMpNxAxEz
ODoS1whh0aijhp/G7XF8BpIowbhrJmHGiBqjMnHFCA1qEoIaYBQUIonCCAYaaOiml7vUXvX7o7qu
t5tmaWjobqzP8/Sj3fd23fcWfU+9dc73fA/FTkwD8XbBbWgtvP03XrBubPfwBOADP/i2UicIQh/X
dXe0WlPu3Nc6e0UOWJblg5pU0RHFkjV/59Ndhbb2+PImx3HaqCzi8RiTzh2MY5m4ruhZ7AGiXMKW
TZuRQjFE0e8eKyMUjaPmcxh6lniyDDkcZfeuWqJRhZiSRpQkMru3kUyVI4cVTF0j07SLSDSFIEZw
bYdMSx3RaIxwNIEcipFt3gmuTUzx8sKa2oJh5IjFS4nE+7J5q8jKP69H10zkUBQ53DqiXpJa5WQR
dNNoHavk5aIlWWbXji2EI4pXrItEadm9E9uyURJpIlGFXKaZfLYJJVHS2qocZnd9LZIoEkt4Rb+8
miXXstuT4IViYOsoB6j5bS8F9C+6fuODrwP3L4pHQh3gG/xHIhEkSWLmzJnU19fz0ksvHfXBF8Ay
rS7/6oBD8QP2uRx4vt3PFgJTWv9/CvDqvt5rrwjAvubxUB3R/OKdv7v1P2CqqpLL5TAM44gW2oox
DINcLrfXiR9fOb6a4/vYWI6LaRq4to5jq4RjVeyo3QGugCRHaNj5d+KJNOFoHF3Lo+WbSSTLCUcU
Ghu81uJINIkohmhq3EYyXUY4msDFIdO8g5iS8tqBxRDNTdtxXYtoNIUsR9HVFgythViiBFn2mjjU
bANKPI0kx1DNOKtX76K2tgHLcgiHozQ21mNbBolkaeFOo2HnNpKtBbNQyLs4yHKISDSOKIfJZZuw
LYN4wmubNi2TpoYdxBMpIpEYoVDMS6GoeeIJz4vYti2aGnaQTJcSCR9ckaz4lt/3ayhulvHliX5A
PhyTkv0OSUVRyOVyXHrppYwePZoHHnjgqPB5OBAcy+nyr/Ycih8wgCAIcbwC3MvtDv1TYJwgCJ8C
Z7d+v1d6RQ7Yd5Bqbm4uTCbo7O+rqtqm0OanHPy+e38QY2cKNF1BcZFFUZR9fshs2+aRp1awbZeF
KIWQQzIgenlWtYl4XPJM2I085dXHkmlpwtBVJEEiliwn29yAoeVRUhWeP26uBcvSSJb1J9vciGXk
cR2beKIC26U1PaEiSVHCSgo9l8G2VHAhnq5Gy2ewzDy2bZFM90VVs1h6HsexCIdDVFfalJYncXGJ
RuIo8TTZTDOm6RnIlFX29f5dVBXdUInHS5DDUfLZFnRdJ6bEiUST5PMZTEPDNk3Spd6YI03LYhkG
giiQLK1GzTZjGBqOZfL1r57Ied/cM/+7L/zOxv0VXItTFn4eubid3N8odBY/9WRZFoqi8PnnnzNj
xgxmzZrFeeedt9/f37JlC5MnT2bnzp0IgsA111zDTTfdtMfzbrrpJhYvXoyiKDz11FOMGjWq02vd
B12SA77w3z7tirW04dWfn9Aj/YB7RQ7Y/4M+mB2wf1sviiKpVKrQUAFfFNr8oN5RPrArPlz7Wpv/
GolEYr/HliSJGyeP4b+eX8Gm7Ta67iC0DqiMJypRtQxqtp5UeTn1O/5OWdVAQETLteA016MkynEc
gXxLA7FEGZFYEjtn07RzC6myfmiSjKWrZDMNBYWEporYloaaqSeerELNCZhmnuaGrcTTVXg3UXla
mmpRElWIooyhZdA0lV27K9hRt5vqaoGSEu/WOl1aRSbTDIZOfd1W0uV9cR2wXZd8rgUFiCdLQGhu
TaPoJEsqySMgiBLNTfVEY0mUeJo8GWxDp3HXFkrK+iEIEgZ5Sjrpse+7kflOY/uioxyyH4j9mX+d
/ZvxlTiu682+W7lyJXfccQfz58/npJNOOqD3EAqFeOihhzj11FPJZrOMHj2acePGtfGAWLRoERs3
bmTDhg2sXLmS6667ro0HRE+hK3LAvYVeEYDh4BzRdF1HVVVisVjB5Bq+KLSJothGUbG3D5dlWYUh
nsW74/1NK9jX2gzDQNd1otFop+R0oZDM9Vf9AwsWfsAHn2jYDji2BYJNSI5iSxEad9WTSCXYvWsr
JWV9cR0XXcuSaa4jma6mpdkl29JANJ4moqRw3QzNu7ehJMqQlRS6msXUVSxTIxYvQ1MlMPNkmrcR
T1Yih8IYepZc8y4iSgo5ksJ2XHLNO4nEUkSiaXAFNLUZUVKob0qyY9tnVPeNYVo25ZX9yGdbcByX
hp21lFb0IS6XoOZayOUyRGybeLIU1230Wpfra0mVVGNJIXQEdC2HrudJl1Wj5rKgQ2P9NpLpCmLx
EkriB/7v4Fs6+ndGncXvXvQDd/HfzIEE5GKZWywW47e//S1PP/00v/vd76iu3qeCqQ19+vShT58+
gDd3cPjw4Wzbtq1NAF64cCFTpnjpyTFjxtDU1ERdXV2nXudIYJldPxGjp9JrAjAc+A64ePRQcVEF
vjAyiUajhEKhfQbQ9h+u4km5uu6NzWkfkPdHccrhUD70l/3LaZQv+5jfv9+EboBj2diICLhIkTJa
WpqIRiR276qlpLwfDgJGroVs8y7iyUoypo2a2U0sWY4SLyGfbULNNiKFokTjaS+9YOhkm+qIpysx
RQmXLLnmesJKkqhSArRgaFmkUBRFKSWfa0JXW3BFiVisFEPP4VgaWlZHSQxm2/Zm6ndtoqWpkWOO
H4bjgiCItDTWE0+Weq5muRZ0TcU2LRKlleRamjENgabGOmLxFLHWtZmGTuOuWtJlfbzzLqpkWxpI
l1bRr2r/hariXWdXmunsKyAXX8T9qRm+1DAUCjF37lw2bNjA4sWLicUO3jho8+bNrFmzZo/RRLW1
tXv4RGzdurXHBeCOcrZHK0ddAPaLWf5E2/bWkY7jHHTg8y0D/RZlPyD7eeTiHXRH+WP/Q+hrmQ81
nTHujBNJpz5l4dt1qELIC8KO17wgymny+SzhsEZj/TbS5f3BAV3N0NywjVRpP7KZevLZRiKxlBd0
1RZsQyfbvJNEshJdkDD1HC2NO4jFS4kqaXQymFoOS9SIKWWoaguWoaGau0mkKgp5ZTVXTyxRgaHL
WHqWlubtxJQKbHsgn366nYadKzjhxBFEYwkQRLItTURjSRKpUtzmRnRDo7lhB8mSKm/EkOHZa/op
CTXn5YWbdm8nnighnvB20LaRJ5Xcdw7Cv0D76ofDmeffW0D274D+9re/8aMf/QjXdTnuuON45pln
DqnBKJvNMmnSJB555JEO5x22//x0V7PFvvAdB78M9JoAvL8UhL+j8XO6HXW0+VMsuuKPbl9ev+3z
x/5aDMM4oDxjZ/j6qBMoTceZ/9J6TCEBlo1t2bgIiHIcVcthGi24QCJZhR1WsJ0c2ZYdJNLVZJsb
ULPNyKEwSqwEjSyWZdDStINYopxwLIVLFl1tQZRCxOJlqLlmLFMj01JHIlWNhoBlqGSadxBPVIAm
YaOiZncRjqQIJ8rR9Ra0XD2hcIJEqi8tuRbe/dNHDDmhL9X9+gGg6zlsyySersBtacSyTBp31ZJM
lyPH0+j5LKah01S/lVRpXyRZQlcF8vkMsqiRTFfiWs37PF/d3VwBX3j9xuNxqqqqSKfT6LrO+++/
z9ChQ9m8efNBrcs0TS6++GK++93vcuGFe3bA9u/fv41PxNatW+nfv2vm4nUl9pcoBdErZGg+ewvA
lmXR0tJSSDn4igZoax15OLW9HVlL+oHZb3X213Uw48f3xdDB/bntmtOJyy0ggCRLiII3GDgcjmM5
KRp27KSxoZZoTCESTeA60Lx7O/FUBXLrkMxMy04isQShsIIsR9FyDZiGSkwpRZSjOKZJpnkH0XgK
ORRHFCUyTduR5QjhSApRCJFtrgMsIrE0ohTFNHLoWjPRmGd9aVoqpp5FSVYQiVWzeVOe9//8F5p2
NyPJIUzToLFhe8Evwp+ooasZ4slSQtEYohShafd2XNtCSaRbx9lbNDZs47hjOw4oBzu5oivx78IM
wyCRSLBx40amTp3KzJkzWbx4MevWrePjjz8+6LrC9OnTGTFiBDNnzuzwORdccEHB22HFihWUlJT0
uPQDgN26iejKr55Kr5ChwRdNEv7OAToutPnvp7jQFovFusXf1N9t+QM6i3PIfhdeZ/LH+8M0TR75
1Tt8Xud1lomihGPZnm4YMLUGlESYij6DMXQdTW3BsR2S6T7kso3YloFl6oSVNLLk6X5tS8N1BeLJ
ytZuNt0bM58ow3HB0LJYpkY4kkCSFfR8E7atI4oS0VgZup7DMlVsy0BJVOHYNqaRwbYt4slyDMPA
1DKIgkgs7lBRGSEWT4LrUlLeB13XMAwNy9BBEEiXVGIYOrruHVOSZBLpKs8jQlc5+x+G8Y1T2gaV
9nn37vhb8N37BEFAURT+9Kc/MXv2bJ555hlOOOGEQz7+O++8wz/90z9xyimnFAL4vffey9///nfA
84AAuOGGG6ipqSEejzN//ny++tWvHvJrF9ElMrRvXbi8K9bShuWvfqtHytB6TQD2g5k/wbe40OYb
VLcvtHXXbWZxdX1vKYfiYGxZ1n7zx5157Sef/zP/+3EWkHDxtM1i62dDzTchSSp9B52Irqno+QyO
bRFPVmIaBpahYlo6khQiFislr3pB1zZ1lFQFju2iq1lsyyAcVVqDrpf3lUSZSKwETc1i2zq2bRCN
luC6AraZx7Z1wpEkUmtTh2VqRKJJBCnsBXvbIBYrIRTeTXlFgnAkhhJPIcsRNC2HbVlYtkEyVY4o
R1r9Kry8frqsGlPXmfAPfTlxaL8259lvrugOMx1o21YciUT49a9/zcsvv8wLL7xAeXn5EV/PYaRL
AnBXLKQjggB8CBQH4HA4XCi0RaPRQpGtuNC2v6aGw4X/gQcKAzn3R3FBz/86FP2x4zi8+Pr7LH13
J7LkV9O98yMIno5XkvL0GTAMTctjaFlM0yCqpJCkGJrajG2ZuI5FPFmFaeoYWg7bNAjH4khSDF3L
Yls6IKAkyj1lgqnh2iZRpRzHtdH1HK6lE5JjhGMpNDWDZamIgoySKPOKZraKKISIxEpQ881Ydp5o
tATLyBOL5Ugko6TLK1rHMOUxdA3L0pFDURKpMlQ1g20YmKZOaUU/rhzfn/IyzwfiQJsrDifFOWdZ
lpk1axYNDQ3MmzevMGLoKKLHBbieTq8LwKqqAhQCrD+U0N9lhEKhbplUAF84mB3qB76jbqsD1R8X
u6h9sG4rv37pb5hOBFwQcMFxcQSw9DxSKEPfY070bvH1PKahIcphYvFSdDXv7YZNjVi8FFEKoee9
oCsIIkqinHw+g2WoOI5FPFWFqamYhorjGAhCiEg0haHncRwDx7JQEpVYloZpqq273TJsx8HUs94x
4hUYpoqp5RBlmVA4iWVqaPntVFYrVFb3IVVa5XXcmQauY5EoqcQ0LSxdJRoJcfP3xiAIQqeaKw4X
xWswDINrr72W0aNHc8cdd3TryJ/DSBCAO0mvCcCaphVM2P2OtvbWkd31hm4kDAAAHfJJREFUYStO
ORwO+8piLene8sd7W8On/7eDx576gLwWBhdcHFwHcB0sywDqqew3hFCr8bplm9imQTxdiW1ZGFoO
09SRpRDReClaax7YUytUYeq6p/d1dMLhFC4yppHFtU1c1/F2w46NqedxbB0ppHgz7FpTEKGwghRS
0LVmbFMjqpSCK2DoWSxbJxZNIshRDC2DZapEoxZ9B1QTjnjSLssyiSkJpLCCYGWYdtFJhWKt3+TS
nSmoeDzOrl27mDJlCjfeeCPf+c53eqT0q4s4at/Y4aLXBGBfSeD7Ofg5X19/212FtvaerUdiDe3T
FT7+GtpfAHbUNXL/L//M7oxn6u664LoOrgsiJrq6k0gsTJ9jhmPoOqapYhk64WgMOZT0UhKGjuva
xJN9WotiXmCOxtKIYhhN9aRpIBBPVGCYOral4VgGkhwlHEmga1ksW0VwBWLxMgxdxTLz4DjEkpVo
ag7b9Aqn4WgKw1BxbM82NBpLe+/byOM6nkwpmRKIp8IoSoxwVGH4Ccdy7tcrChco34j9cLaTt8cv
+PlpsI8//pgbbriBRx99lG984xuH7XV7CEEA7iS9JgD7+tpsNovruoiiiG3bRCKRbsvvFd/ud5em
1FeH+IFlbwbjmUye+36+jNpdAq7j4rguOAaWrSM4AoIoYBrNlFZVEU9WouueukFARElUoKs5LEvD
sgxiSgmCIKNpWWxDQ5RkwtE0Wq4FFwvHNgiFE0ihGKaWw7F1bzJyrAzLsTwDH1MjEk0jiGEM3csN
R2KliIjoaguOa35xDD2LbWmIUohwNIVlalimioBANJYml9lGSVmI8WeP5Nx/HNImBdX+7qGr2sk7
wr8Yi6JINBrlzTff5Gc/+xm/+c1vOO644/b5u9OmTeONN96gqqqKdevW7fH4H//4R/7lX/6FwYMH
A3DxxRfz7//+712y7i4kCMCdpNcE4DvvvJO1a9dy+umns2HDBqZMmcLJJ5+Mbdvd4mDW3jT9SLM3
pcW+3LoAHp63jE82G5iGiuCCKMmAgOPaOLaFbdnIIZtUWQVSKIpteS5ksUSZlxrQPAWEKMtEYqXk
s01YpgqOSyzuFd8s3csDO65LVCnDsSzMVhVESI4hRxLo+WYcx0QQJCKxtFfkszQEQSSilGCoOWxb
AxzC0TQCIoaexXYMIpEkghhuDcw6ciiGHFa47rtDGH3q4P2OGCo+P67rttkhH2xALi74hcNh/uu/
/ou3336b3/zmN5SU7HMwLgDLly8nkUgwefLkvQbgBx98kIULF3bw2z2GIAB3kl4TgF3X5eWXX+aa
a65h2LBhOI7DsGHDOPvssznzzDOJx+OdLlgdDH6xzx9j1F2dVKrqjQvan9Kiox3ga4s/4p2VW1CN
KI5r4zo2oijjDYr1WrdNQyUUdkmWVSGJIpZhIEdjhMMJdDWDZWnYloUSr8CyDEwjj2ubiHKEUCSB
aWg4lo5jG56dZSSJpmdwbR3btokp5diOjaXnWuVqKVxBQlebwbUJReKIYhTTyLYW9URC0RSObWEa
OXBsItESHNdF17MkEgq/+On5nVa+dJTO6aw+278TikajiKLI7bffjiAIPPLII52qSWzevJmJEyfu
NQA/8MADvP766wf+5o48QQDuJL2qFbm+vp5nn32WCRMm4DgOa9euZenSpcyYMYN8Ps83vvENxo0b
x1e/+tXC7WBXNjz4Ve3uTDkUN3cciNqjI0Ohy/71dC48/1ReeGUFq1bvQDOj4IpYlgaigIhAKKwA
sHv7TuSwi5JMI5g6eUNFSVTi5AUcRyWf20ksVo4YTWFoOZzW4Z2xWBoiSU8VYWnks7uIxEpwQ1Fc
LUs+10AkHCUSS6NrGTStBVkOE42XeoU/Q8V1c0QiKRBimGYOXW1CEmWisRJMQ0VVmxEAJV5KSUrs
Mn8Pf4fs1xfa75CL8esSiqKQz+eZPn06Y8eOZebMmV369yEIAu+99x4jR46kf//+3H///YwYMaLL
jh/QPfSaHfD+yOfzLF++nCVLlrBy5UpKSko4++yzGTduHAMGDCgUZA6m4aEzpumHi2ILy65Se7iu
i2maPPfbd1n23iY0M4YgSLi4uLaFIHgFO1GUcWwdUbZQ0mU4ticpA7E1JaEiiWFC0RS2ZWCaKjje
+KRILNXaDqp5zRpymHAk6cnTbAPbMokpZdiug6lncGyTcDiJKIUxjFyh4BaOpsB1Mc0clmkQCilI
chTLzGE7Fv987iguv/Arh3xO2p+f9jtkP90lSVLhjisej1NbW8vUqVO54447mDhx4kEF333tgDOZ
TGEy8+LFi/nBD37Ap592vXH5IRLsgDvJUROAi3Fdl+3bt/Pmm2+ydOlSNmzYwIknnshZZ53FWWed
1SZdIUkSoVBor+mKYtP07pgT57+fw30BsG2b5178M39c/hk5TcRTDbfu9lwLEMB1MAyVcFQgUVJB
KBwlEkmjqs04loFtm4QjCWQ5iqFruI7RGnRjXtA18jimjmUZRGIpxNYCnG1phEIKcjiOrmZwHAPX
dQlHEwjImGYOxzGRRE8bbBoalq0hODahaBJJCnHdVcMYfeqgLj8vxRTn1w3DW+NPfvITNE1j+fLl
PPXUU3zzm9886OPvKwC357jjjuODDz6grGyvA3e7gyAAd5KjMgC3pzhd8fbbb++RrgD20Nf6Dmaa
pnXaNL0rOdIXANu2ee6l9/jDso3kNBkEF5A9+Zrj4OK1e9tWnnDEGwcUT1Z6Hr6Wjt0qG4tEUohi
CN3I4lgGjm0RjqW9qRW6t7MVEIjESlpHCWnYjkkkkgZB9HLKjqclDkeTgIRpeIU5SQx7aghLwzZ1
4okkj98z7ohowIutLMPhMPPmzePVV1/FNE0+/vhjHn30UaZNm3ZQx95XAK6rq6OqqgpBEFi1ahWX
XHIJmzdvPsR30+UEAbiTfCkCcHv2lq4YO3YsAwcORNO0gtTNz58eCXVFe/ycc3dcACzLYsHLK3lr
2UYyWRAEr40ZQcR1XHDBtE1w80hhgfKq4wmFFUwjj22bOJaOIEiEIykcx8Uy8607W4jESnBs25Oj
WQZyKEYoEkfPt2A7JuASjiQRBAnLyOI6Ng4QkuOIktja+GERkqPIYYV0wuaB2ecfkXNS3Fb8yCOP
sHr1ap555hkSiQTZbBbTNCktLe30sS+//HKWLVtGfX091dXVzJ49G7PVlvH73/8+P//5z/nFL36B
LMsoisKDDz7I6aefvp+jHnGCANxJvpQBuJj26YoPP/yQ3bt3M2nSJG677bY90hWyLBMKhbpcXdF+
TcUDGrtrGq5lWTQ3N/N6zV9Y9u4mcqrY2n3Y+mfhuLiCgGWqGHoGOSRRUjWAeKLSK6I5JpZltNpV
JjAtvdUZzSQUjhEKxTF0FcfWcFyHSCTVmnNVwbFwgHA4gYuAZeZxXdtTQ4QTXj7YyOE4NuPPHsXk
7ww7rOeiuK3YdV1mzpxJRUUFc+fO/dJMKz4AggDcSb70AbiY3/3ud0ybNo1bb70V13UPOF3RVXaS
sOeMsO7KOfsFP1/nbJomC15cwdt/2kBObR1gahm4guW1ONu2lzowdVzXIhwNkyzrjyyHwbWwW5sz
5HAUU1dxLQPLNglH4ohS1MsFm15ThxxWQJCwjByWqSMIApFoCkGUPe2vbSGJElI4geDafP+qkxgz
etBhOxfFbcXNzc1MnTqVSZMmcc011xzNbcUHQ3AyOkkQgItobGyksbGx0G0E+05XHHPMMYWiTFfY
SfaEzrriWWkdaYwty+LXzy9n+XsbaNidR5QiWJaJJHrpCVwbx3ERRQnTNBAlECSReLKcUCSC6zpe
AU4IYxhZXNMAAULRNK5rt5r5mLiALMWQ5BC2qeG0qiFCoXhroM/j2CaJZAkPzToTRTn4GWr7OhfF
bcWbNm1ixowZ/PjHP+bcc8/t8tc7CggCcCcJAnAn6Ky64kD9B3pCZx10vuC3c2cDb/5+LevWb2PL
1gYy2VZ/idZbcsfxUgZei7QJgoMkCYSVFLFoikgshQvYpopl60hiCDmkeBc1UwPBARzC4QSCGMIy
NGxLAwHCkQQgkUrYPPzjf+7yc9HeR/i9997jrrvuYv78+Zx44old/npHCUEA7iQ9IgAPGjSIVCpV
kIStWrWK3bt3c+mll/L5558zaNAg/ud//qfQ0jlnzhyefPJJJEni0Ucf7bbdiK+uWLJkCb///e8P
Kl3RHWY+HVHczXWwBb/PNm/lnT9v4KO1f2fLlnpUHRAkaLXBRBBwBRfXsnFFF0lyURKVJEv6YZoG
jq1h20Zr8S6JKMmtdpcGLjZhOY4ghbFMHdvxzIHO/IdTuPrKk7r0XBRbm4bDYRYsWMCzzz7LggUL
qKqq6tLXOsoIAnAn6REBuCNN42233UZFRQW33XYbc+fOpbGxkZ/+9KesX7+eK664gv/93/+ltraW
sWPH8umnn/YIf9XOpisEQShM7uguQ6HDaaX52We1LP39R/z1b1vZuq0J1XABAcEVEVwXVwDLNhEE
CIVkEum+hJU0VmseWcBFDivIUhjLNnBMHdd1CIUVBDGMbWtcfeWp/OOYfRvddAZf6RCNRpFlmXvv
vZfNmzfz5JNPEo1Gu+x1jlKCANxJekwAfv/999uMZxk2bBjLli2jurqaHTt2cOaZZ/K3v/2NOXPm
FPrtAc477zxmzZrV4yQ5+0pXnHnmmXz00UeMHDmSUCh0RO0Si+mMp0RX8JePN/KH5X/l4/VbqN3W
gGWJ2I6D41jeBA5cEERC4RAhKYQYCpFIViNIEqFQDCkUaZ3UYeI4FolkOXPv+iYl6WSXrM9XOiiK
gmma/Nu//RsnnHACs2bN2u+52Z+bGcBNN93E4sWLURSFp556ilGjRnXJunsQQQDuJD3CC0IQBMaO
HYskSXz/+9/n6quvpq6urjCxtbq6mrq6OgC2bdvWJtgOGDCA2trabln3vhAEgX79+jFlyhSmTJlS
SFe8/PLL3HrrrZSVlfHtb3+bc889l9GjRxcKPodLXdGe4jllR2qCyEknDuGkE4cA3gVqzYd/5b2V
n/Dphlp27mqmqSmLrls4JmiGhauqtOxuQJQEJFlGkkSisVLKqociOA5hSSOZUAqjlg6WYtlfPB6n
oaGBqVOnMm3aNL773e8e0LGnTp3KjTfeyOTJkzt8fNGiRWzcuJENGzawcuVKrrvuOlasWHHQaw44
OugRAfjdd9+lb9++7Nq1i3HjxjFsWFtNpyAI+/wQ9AYpkCiKnHrqqcyePZspU6Zw1113sWLFCmpq
apg9e/Ye6YpiM5iuttrszgaPYkYMH8yQ4wcQj8cLWtodO3ay7J11/OUvn/P32p3UNzSTyeq4lo1l
iWjqdpp3byddEmfMKWPI5XJA5x3MfIpVH/F4nE8++YRrr72W+++/nzPOOOOAj/Otb31rn51pCxcu
ZMqUKQCMGTOGpqamNpuMgC8nPSIA9+3bF4DKykouuugiVq1aVUg99OnTh+3btxeKH/3792fLli2F
3926dSv9+/fvlnUfDM8//3whlzh+/HjGjx/fJl1x33337aGuCIVC6LpeUCgcbLqi/U6vuxoIioNe
IpFoEzD79Kni0knncOmkL56vqirv/Xkda9ZtYkD/Ppz1TydRXVVeOJZvmOMXEg/UH7pYc60oCn/4
wx+45557eO655xg6dGiXvufa2loGDhxY+H7AgAFs3bo1CMBfcro9AOfzeWzbJplMksvlWLp0Kf/x
H//BBRdcwNNPP83tt9/O008/zYUXXgjABRdcwBVXXMHNN99MbW0tGzZs4Otf/3o3v4sDp6NCzt7S
FUuWLGljtTl27Ng90hXtzYT2RrHaIpFIdNtdw8GkPmKxGOec/XXOOXvPf2ffLlKSJCKRSBvDnH1d
tNobqM+fP5/XX3+dN95447AZ3LSvt/SGO7eAw0u3B+C6ujouuugiwKtAX3nllZx77rmcdtppXHLJ
JfzqV78qyNAARowYwSWXXMKIESOQZZn//M//3O8fckcyt1mzZvHEE09QWVkJwL333suECROA7pe5
+emKU089ldtvv72grqipqWHWrFmUlpZ2Kl3hV/a7czx78Tp81cfhoPgcQFtDer+pQhRFHMehvr6e
Y445hrvvvttruX799cOWkuntd24Bh4ceoYI43HQkc5s9ezbJZJKbb765zXN7sswNDqwZxN8BFs+J
i8Vi3Zbv7ai1ubvW4RuoS5LEOeecQ21tLcceeyw33ngjEydOLFyQD4Z9uZktWrSIxx9/nEWLFrFi
xQpmzpx5NBbhgi19J+n2HfCRoqMLTUc/e+2117j88ssJhUIMGjSIIUOGsGrVqh4jczvQdMUZZ5zB
hx9+yIUXXkhFRQWqqmKaZhszoSNBsZdx+3zvkaR4Hclkkrq6OkpKSrjuuuuQZZklS5YwePBgzjzz
zIM6frGb2cCBA/dwMzv//PNZtGgRQ4YMIR6PM3/+/C58dwG9lS/FDnjw4MGk0+k2MrfZs2czf/58
0uk0p512Gg888AAlJSXceOONnH766Vx55ZUAzJgxgwkTJnDxxRd387s4MPL5PC+//DI//OEPqa6u
5thjj+WMM844LN4V+6N9O293pT5c1yWXyxXWsXbtWm666SYef/xxxowZ0y1rOkoJdsCdpGfcVx9m
3n33XdasWcPixYv5+c9/zvLly7nuuuvYtGkTH374IX379uWWW27Z6+/3pmKJoiisXr2aW265hTVr
1vDLX/6SiooK7rvvPsaPH8+tt97K0qVLMQwDQRAwDIOWlhay2WxBIbGfi/IBYds22Wy24F/bnUW/
bDZb8LdYtGgRt9xyCy+++GIQfAO6nS9FCqIjmdu3vvWtwuMzZsxg4sSJwNFRLHnggQcKAe9g1BWO
4xzSZOli79wjMaVibxQX/cLhML/4xS9YtmwZixcvJp1Od9u6AgJ8jvodcD6fJ5PJABRkbieffDI7
duwoPOeVV17h5JNPBjyZ2wsvvIBhGGzatOmAZW5NTU1MmjSJ4cOHM2LECFauXMnu3bsZN24cJ5xw
Aueeey5NTU2F58+ZM4ehQ4cybNgwli5d2qXveW/B0ldX3H777SxZsoQlS5ZwzjnnUFNTw8SJE5k8
eTLPPvssO3fuRJblglQrk8kUcsj72h37OmNN04jH490afA3DIJ/PFwyObr75Zj7//HNeeeWVIPgG
9BiO+hzwpk2b9pC53XnnnUyePJkPP/wQQRA47rjjmDdvXkEUf++99/Lkk08Wxs6MHz9+v68zZcoU
zjjjDKZNm4ZlWeRyOe65555eYyjUWXVFe13t/nyEj+T7KDZQz2azTJ8+nfPOO48bb7yxV6WTeiHB
ye0kR30APhI0NzczatQoPvvsszY/782GQnuz2vTTFYIgYJomjuMgSVIhbRGNRrs1+BZfBLZs2cK0
adO46667+Od/7nrP4IA9CAJwJ/lS5IAPN5s2baKyspKpU6fy0UcfMXr0aB5++OFebSh0oM0gVVVV
7Ny5k6uuugrLsgqFN9/l7UgFY19xIYoiiqLw/vvv88Mf/pAnnniCkSNHHpE1BAR0lqM+B3wksCyL
1atXc/3117N69Wri8Tg//elP2zyntxsKKYrC+PHjefDBB3n33XeZN28eq1ev5rrrruOtt97itttu
Y+nSpZimiSiKGIZBJpPpcnVFRxQrLqLRKK+88gp33303r7322gEH35qaGoYNG8bQoUOZO3fuHo//
8Y9/JJ1OM2rUKEaNGsVPfvKTrn4bAV9Cgh1wFzBgwAAGDBjA1772NQAmTZrEnDlz6NOnz1FpKCQI
AqFQiK1bt7Ju3TqOPfbYQrpi+vTpqKraJl0BoGkatm0fkrqiI4oneciyzIMPPsjatWupqalBUZQD
OoZt29xwww289dZb9O/fn6997WtccMEFDB8+vM3zzjjjDBYuXHhI6w0IKCbYAXcBffr0YeDAgXz6
6acAvPXWW5x44olMnDiRp59+GmAPQ6GDUVr0JKqrq1m2bBnHHXdcG3XF0qVL91BXXHXVVfz617+m
rq5uD3VFPp/HMAwcx+nU6/vFNlVVURTPE/j6668nl8uxYMGCAw6+AKtWrWLIkCEMGjSIUCjEZZdd
xmuvvdbhawYEdCXBDriLeOyxx7jyyisxDIPjjz+e+fPnY9t2lxkKgSd1mzFjBh9//DGCIPDkk09S
U1PT40yF/HSFb7W5bds23nzzTX72s5+xYcMGRowYwdlnn81ZZ51FOBwu7GIP1Gqz2FYzkUjQ1NTE
9773PS677DKmT5/e6V11R1aRK1eubPMcQRB47733GDlyJP379+f+++9nxIgRnT85AQFFBCqIXkRH
UreHH364V5kKFasr3n777T3SFb550N7SFb7SAbxAv3HjRq655hruuecexo4de1Breumll6ipqeG/
//u/AXj22WdZuXIljz32WOE5mUym4Bu8ePFifvCDHxTueAIK9OxCRg8kSEH0Epqbm1m+fDnTpk0D
vAkQfkNBZ0yFuptDSVf4/7UsC0VReOedd7j66qt56qmnDjr4wp45+S1btjBgwIA2z0kmk4W0xoQJ
EzBNk927dx/0awYEQJCC6DV0JHV75JFHAC/98cwzz7QxFeoNUjfYe7rivvvuY+PGjYV0hS/jGz9+
PJMnT2br1q3k83keeughBg8efEhrOO2009iwYQObN2+mX79+LFiwgOeff77Nc+rq6qiqqkIQBFat
WoXruofNuD3gy0OwA+4l7E3qdv311x81pkKCINC/f3++973v8dxzzxV8c2tqarjooov47W9/y/33
3091dTUnnXQSV1xxBXPnzuXuu+8+pNeVZZnHH3+c8ePHM2LECC699FKGDx/OvHnzmDdvHgAvvvgi
J598MqeeeiozZ87khRde6Iq3HPBlx3XdfX0F9BC2b9/uDho0qPD98uXL3W9/+9ttnrNp0yb3pJNO
cl3XdefMmePOmTOn8Nj48ePdFStWHJnFdiE7duxwhw8f7n700UduLpdzFy5c6E6fPt21bbvwHMdx
unGFAUXsL54EX+2+gh1wL2FvUreuNhXqaVRXV7Nu3TpOOeUUFEVh4sSJPPHEE22KiT19Zx8QsDeC
ANyL8KVuI0eOZO3atdx5553cdtttnHLKKYwcOZJly5bx0EMPAW2lbhMmTDhgqdsnn3xS6PYaNWoU
6XSaRx99tNuc3YBum94cEHC4CWRoAXvFcRz69+/PqlWreOyxx3qNs1tAtxHcinSS4FMSsFfeeust
hgwZwsCBA1m4cCFTpkwBPD3yq6++CvRcuVtAQG8gCMABe+WFF17g8ssvB9ins1uxZranyt0CAnoi
QQAO6BDDMHj99df5zne+s8djvd3ZLSCgpxAE4IAOWbx4MaNHjy54TPim8sBR5ewWENCdBAE4oEOe
f/75QvoBPFlbT3R225+PL8BNN93E0KFDGTlyJGvWrDliawsI2C/7EQoHfAnJZrNueXm529LSUvhZ
Q0ODe84557hDhw51x40b5zY2NhYeu+eee9zjjz/e/cpXvuLW1NQcsXValuUef/zx7qZNm1zDMNyR
I0e669evb/OcN954w50wYYLruq67YsUKd8yYMUdsfV9Cur2xobd9BTK0gG7hk08+4bLLLit8/9ln
n/GjH/2IxsbGA7bXTCaTzJ49m5qaGoDCFJI77rijcNxrr72Ws846i0svvRRoO6cvoMsJkv+dJEhB
BHQLX/nKV1izZg1r1qzhgw8+QFEU/vVf/xVBELj55psLj/nBd/369SxYsID169dTU1PD9ddfz5Yt
W/bw8W2vwOjI63fr1q1H5k0GBOyHIAAHdDvFemP/1qw9HemN/+///u+Ajt/+eIFKI6CnEATggG6n
WG8sCAKPPfYYI0eOZPr06YWW5470xsB+fXwDlUZAT2Z/OeCAgMOKIAhhoBYY4bruLkEQqoBdrQ//
GOjruu50QRAeA1a4rvub1t97AqgB5gLnANuAVcDlruv+tej45wM3uK57viAIpwMPu677hVFyQEA3
EhiyB3Q3E4APXNfdBeC67k7/gdYg+3rrt7XAwKLfGwBsAW4AlgAS8CvXdf8qCML3W481z3XdRYIg
nC8IwkYgB0w93G8oIOBACXbAAd2KIAgvAItd13269fu+rutub/3//wd8zXXdKwRBGAE8B3wd6A+8
BQxxgz/ggF5MsAMO6DYEQYgDY4Gri348VxCEU/EkkJsAfze7XhCE/wHWAxZwfRB8A3o7wQ44ICAg
oJsIVBABAQEB3UQQgAMCAgK6if8P098E7FtyaO4AAAAASUVORK5CYII=
)

One can also construct a local volatility surface (_a la_ Dupire) using the ```
LocalVolSurface
```. There are some issues with this as shown below.

In \[11\]:

```

local\_vol\_surface \= ql.LocalVolSurface(
	ql.BlackVolTermStructureHandle(black\_var\_surface),
	flat\_ts,
	dividend\_ts,
	spot)

```latex

In \[12\]:

```

plot\_years \= np.arange(0,  2,  0.1)
plot\_strikes \= np.arange(535,  750,  1)
fig \= plt.figure()
ax \= fig.gca(projection\='3d')
X,  Y \= np.meshgrid(plot\_strikes,  plot\_years)
Z \= np.array(\[local\_vol\_surface.localVol(y,  x)
			  for xr,  yr in zip(X,  Y)
				  for x,  y in zip(xr, yr) \]
			 ).reshape(len(X),  len(X\[0\]))

surf \= ax.plot\_surface(X,  Y,  Z,  rstride\=1,  cstride\=1,  cmap\=cm.coolwarm,
				linewidth\=0.1)
fig.colorbar(surf,  shrink\=0.5,  aspect\=5)

```latex

Out\[12\]:

```

```latex

![](data:image/png;base64, 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
edtQAAAAAElFTkSuQmCC
)

The correct pricing of local volatility surface requires an arbitrage free implied volatility surface. If the input implied volatility surface is not arbitrage free,  this can lead to negative transition probabilities and/or negative local volatilities and can give rise to mispricing. Refer to Fengler's arbtirage free smoothing \[1\] which QuantLib currently lacks.

When you use an arbitrary smoothing,  you will notice that the local volatility surface leads to undesired negative volatilities.

In \[13\]:

```

black\_var\_surface.setInterpolation("bicubic")
local\_vol\_surface \= ql.LocalVolSurface(
	ql.BlackVolTermStructureHandle(black\_var\_surface),
	flat\_ts,
	dividend\_ts,
	spot)
plot\_years \= np.arange(0,  2,  0.15)
plot\_strikes \= np.arange(535,  750,  10)
fig \= plt.figure()
ax \= fig.gca(projection\='3d')
X,  Y \= np.meshgrid(plot\_strikes,  plot\_years)
Z \= np.array(\[local\_vol\_surface.localVol(y,  x)
			  for xr,  yr in zip(X,  Y)
				  for x,  y in zip(xr, yr) \]
			 ).reshape(len(X),  len(X\[0\]))

surf \= ax.plot\_surface(Y, X,  Z,  rstride\=1,  cstride\=1,  cmap\=cm.coolwarm,
				linewidth\=0.1)
fig.colorbar(surf,  shrink\=0.5,  aspect\=5)

```latex

```

```latex
\---------------------------------------------------------------------------
RuntimeError                              Traceback (most recent call last)
 in ()
     12 Z = np.array(\[local\_vol\_surface.localVol(y,  x) 
     13               for xr,  yr in zip(X,  Y)
\---> 14                   for x,  y in zip(xr, yr) \]     15              ).reshape(len(X),  len(X\[0\]))
     16 

C:\\Users\\gbalaram\\Documents\\Code\\env\\Lib\\site-packages\\QuantLib\\QuantLib.pyc in localVol(self,  \*args)
   7467 
   7468     def localVol(self,  \*args):
\-> 7469         return \_QuantLib.LocalVolTermStructure\_localVol(self,  \*args)
   7470 
   7471     def enableExtrapolation(self):

RuntimeError: negative local vol^2 at strike 655 and time 0.75; the black vol surface is not smooth enough
```

```latex

![](data:image/png;base64, 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
TkSuQmCC
)

Heston Model Calibration
------------------------

Heston model is defined by the following stochastic differential equations.

dS(t, S)dv(t, S)dW1dW2\=\=\=μSdt+v√SdW1κ(θ−v)dt+σv√dW2ρdtdS(t, S)\=μSdt+vSdW1dv(t, S)\=κ(θ−v)dt+σvdW2dW1dW2\=ρdt

\\begin{eqnarray} dS(t,  S) &=& \\mu S dt + \\sqrt{v} S dW\_1 \\\\ dv(t,  S) &=& \\kappa (\\theta - v) dt + \\sigma \\sqrt{v} dW\_2 \\\\ dW\_1 dW\_2 &=& \\rho dt \\end{eqnarray}

Here the asset is modeled as a stochastic process that depends on volatility $v$ which is a mean reverting stochastic process with a constant volatility of volatility $\\sigma$. The two stochastic processes have a correlation $\\rho$.

Let us look at how we can calibrate the Heston model to some market quotes. As an example,  let's say we are interested in trading options with 1 year maturity. So we will calibrate the Heston model to fit to market volatility quotes with one year maturity. Before we do that,  we need to construct the pricing engine that the calibration routines would need. In order to do that,  we start by constructing the Heston model with some dummy starting parameters as shown below.

In \[14\]:

```

\# dummy parameters
v0 \= 0.01; kappa \= 0.2; theta \= 0.02; rho \= \-0.75; sigma \= 0.5;

process \= ql.HestonProcess(flat\_ts,  dividend\_ts,
						   ql.QuoteHandle(ql.SimpleQuote(spot)),
						   v0,  kappa,  theta,  sigma,  rho)
model \= ql.HestonModel(process)
engine \= ql.AnalyticHestonEngine(model)
\# engine = ql.FdHestonVanillaEngine(model)

```latex

Now that we have the Heston model and a pricing engine,  let us pick the quotes with all strikes and 1 year maturity in order to calibrate the Heston model. We build the Heston model helper which will be fed into the calibration routines.

In \[15\]:

```

heston\_helpers \= \[\]
black\_var\_surface.setInterpolation("bicubic")
one\_year\_idx \= 11 \# 12th row in data is for 1 year expiry
date \= expiration\_dates\[one\_year\_idx\]
for j,  s in enumerate(strikes):
	t \= (date \- calculation\_date )
	p \= ql.Period(t,  ql.Days)
	sigma \= data\[one\_year\_idx\]\[j\]
	#sigma = black\_var\_surface.blackVol(t/365.25,  s)
	helper \= ql.HestonModelHelper(p,  calendar,  spot,  s,
								  ql.QuoteHandle(ql.SimpleQuote(sigma)),
								  flat\_ts,
								  dividend\_ts)
	helper.setPricingEngine(engine)
	heston\_helpers.append(helper)

```latex

In \[16\]:

```

lm \= ql.LevenbergMarquardt(1e-8,  1e-8,  1e-8)
model.calibrate(heston\_helpers,  lm,
				 ql.EndCriteria(500,  50,  1.0e-8, 1.0e-8,  1.0e-8))
theta,  kappa,  sigma,  rho,  v0 \= model.params()

```latex

In \[17\]:

```

print "theta = %f,  kappa = %f,  sigma = %f,  rho = %f,  v0 = %f" % (theta,  kappa,  sigma,  rho,  v0)

```latex

```

theta = 0.135147,  kappa = 1.878471,  sigma = 0.002035,  rho = -1.000000,  v0 = 0.043485

```latex

Let us look at the quality of calibration by pricing the options used in the calibration using the model and lets get an estimate of the relative error.

In \[18\]:

```

avg \= 0.0

print "%15s %15s %15s %20s" % (
	"Strikes",  "Market Value",
	 "Model Value",  "Relative Error (%)")
print "="\*70
for i,  opt in enumerate(heston\_helpers):
	err \= (opt.modelValue()/opt.marketValue() \- 1.0)
	print "%15.2f %14.5f %15.5f %20.7f " % (
		strikes\[i\],  opt.marketValue(),
		opt.modelValue(),
		100.0\*(opt.modelValue()/opt.marketValue() \- 1.0))
	avg += abs(err)
avg \= avg\*100.0/len(heston\_helpers)
print "-"\*70
print "Average Abs Error (%%) : %5.3f" % (avg)

```latex

```

        Strikes    Market Value     Model Value   Relative Error (%)
======================================================================
		 527.50 184.23863 177.26114 -3.7872037
		 560.46 162.13295 156.75990 -3.3139776
		 593.43 141.96233 138.13403 -2.6967003
		 626.40 123.03554 121.33552 -1.3817289
		 659.37 108.50169 106.27965 -2.0479306
		 692.34 93.29771 92.86049 -0.4686261
		 725.31 79.64951 80.95876 1.6437604
		 758.28 67.62146 70.44848 4.1806550
----------------------------------------------------------------------
Average Abs Error (%) : 2.440

```latex

References
----------

\[1\] Mathias R. Fengler,  _Arbitrage Free Smoothing of Implied Volatility Surface_,  [https://core.ac.uk/download/files/153/6978470.pdf](https://core.ac.uk/download/files/153/6978470.pdf)

Click here to download the [ipython notebook](/extra/notebooks/heston_model_calibration_smile.ipynb).

  
  
   [quantlib](http://gouthamanbalaraman.com/tag/quantlib.html)   [python](http://gouthamanbalaraman.com/tag/python.html)   [finance](http://gouthamanbalaraman.com/tag/finance.html)    

* * *

**Related Post**

*   [QuantLib Python Tutorials With Examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html)
*   [On the Convergence of Hull White Monte Carlo Simulations](http://gouthamanbalaraman.com/blog/hull-white-simulation-monte-carlo-convergence.html)
*   [Valuing Options on Commodity Futures Using QuantLib Python](http://gouthamanbalaraman.com/blog/value-options-commodity-futures-black-formula-quantlib-python.html)
*   [Short Interest Rate Model Calibration in QuantLib Python](http://gouthamanbalaraman.com/blog/short-interest-rate-model-calibration-quantlib.html)
*   [QuantLib Python Cookbook Announcement](http://gouthamanbalaraman.com/blog/quantlib-python-cookbook-announcement.html)

* * *

![](/images/me.png)  
I am Goutham Balaraman,  and I explore topics in quantitative finance,  programming,  and data science. You can follow me [@gsbalaraman](https://twitter.com/gsbalaraman).  

* * *

**Checkout my book**

[![](/images/cookbook.png)](https://leanpub.com/quantlibpythoncookbook)  
Updated posts from this blog and transcripts of Luigi's screencasts on YouTube is compiled into [QuantLib Python Cookbook](https://leanpub.com/quantlibpythoncookbook) .

© [Goutham Balaraman](http://gouthamanbalaraman.com) Proudly powered by [Pelican](http://getpelican.com/)

[Atom](http://gouthamanbalaraman.com/feeds/all.atom.xml)   [RSS](http://gouthamanbalaraman.com/feeds/all.rss.xml)

 jQuery(document).ready(function($) { $("div.collapseheader").click(function () { $header = $(this).children("span").first(); $codearea = $(this).children(".input\_area"); console.log($(this).children()); $codearea.slideToggle(500,  function () { $header.text(function () { return $codearea.is(":visible") ? "Collapse Code" : "Expand Code"; }); }); }); }); jQuery(document).ready(function($) { $("body table").addClass("table table-sm table-hover"); $("body table").attr("border", 0); }); MathJax.Hub.Config({ "HTML-CSS": { styles: { ".MathJax .mo,  .MathJax .mi": {color: "black ! important"}} },  tex2jax: {inlineMath: \[\['$', '$'\],  \['\\\\\\\\(', '\\\\\\\\)'\]\], processEscapes: true} });
