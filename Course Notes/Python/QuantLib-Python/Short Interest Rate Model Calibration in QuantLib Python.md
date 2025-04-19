---
title: Short Interest Rate Model Calibration in QuantLib Python
source: 
  http://gouthamanbalaraman.com/blog/short-interest-rate-model-calibration-quantlib.html
description: Provides examples of short interest rate model calibration to swaption
  volatilities in QuantLib Python
tags:
  - hull_white_model
  - interest_rate_models
  - model_calibration
  - quantlib_python
  - swaption_volatilities
aliases:
  - QuantLib Calibration
  - Short Rate Calibration
key_concepts:
  - Black Karasinski model
  - Calibrating model parameters
  - Hull-White model details
  - QuantLib Python examples
  - Swaption volatility calibration
---

# Short Interest Rate Model Calibration in QuantLib Python

Provides examples of short interest rate model calibration to swaption volatilities in QuantLib Python

*Visit here for other [QuantLib Python examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html). If you found these posts useful,  please take a minute by providing some [feedback.](https://docs.google.com/forms/d/e/1FAIpQLSdFdJ768HKmIyJmaVRHBUJNY5NyQl6vr0GZvSkx-bUfIloNZA/viewform)*

I have talked about Hull-White model in my earlier blog posts. The focus of those posts was to see how to use the model classes. The model parameters were assumed to be given. However in practice,  the model parameters need to calibrated from market data. Typically instruments such as swaptions,  caps or floors and their market prices / volatilities are taken as inputs. Then the model parameters are fit in such a way that the model prices these options close enough. The goodness of fit depends,  apart from the choice of the numerical methods,  on the type of model itself. This is because models such as Hull-White 1 factor cannot fit some of the humped volatility term structures observed in the market. Never the less,  Hull-White is usually a good starting point to understand calibration process.

Here we will discuss Hull-White model in detail. Then we will also show how the same procedure can be applied to calibrate other short rate models.

In \[1\]:

```latex
import QuantLib as ql
from collections import namedtuple
import math
```

## Hull-White 1 Factor Model

Hull-White model was one of the first practical exogenous models that attempted to fit to the market interest rate term structures. The model is described as:

$$
d r_{t} = \left(\right. \theta \left(\right. t \left.\right) - a r_{t} \left.\right) d t + \sigma d W_{t}
$$

where $a$ is the mean reversion constant,  $\sigma$ is the volatility parameter. The parameter $\theta \left(\right. t \left.\right)$ is chosen in order to fit the input term structure of interest rates.

What is the "right" value for parameters $a$ and $\sigma$? This is the question that we address by calibrating to market instruments.

In \[2\]:

```latex
today = ql.Date(15,  ql.February,  2002);
settlement= ql.Date(19,  ql.February,  2002);
ql.Settings.instance().evaluationDate = today;
term_structure = ql.YieldTermStructureHandle(
    ql.FlatForward(settlement, 0.04875825, ql.Actual365Fixed())
    )
index = ql.Euribor1Y(term_structure)
```

In this example we are going to calibrate to the swaption volatilities as shown below.

In \[3\]:

```latex
CalibrationData = namedtuple("CalibrationData",  
                             "start,  length,  volatility")
data = [CalibrationData(1,  5,  0.1148), 
        CalibrationData(2,  4,  0.1108), 
        CalibrationData(3,  3,  0.1070), 
        CalibrationData(4,  2,  0.1021), 
        CalibrationData(5,  1,  0.1000 )]
```

### Calibrating Reversion and Volaitility

Here we use the `JamshidianSwaptionEngine` to value the swaptions as part of calibration. The `JamshidianSwaptionEngine` requires one-factor affine models as input. For other interest rate models,  we need a pricing engine that is more suited to those models.

In \[5\]:

```latex
model = ql.HullWhite(term_structure);
engine = ql.JamshidianSwaptionEngine(model)
swaptions = create_swaption_helpers(data,  index,  term_structure,  engine)

optimization_method = ql.LevenbergMarquardt(1.0e-8, 1.0e-8, 1.0e-8)
end_criteria = ql.EndCriteria(10000,  100,  1e-6,  1e-8,  1e-8)
model.calibrate(swaptions,  optimization_method,  end_criteria)

a,  sigma = model.params()
print "a = %6.5f,  sigma = %6.5f" % (a,  sigma)
```

```latex
a = 0.04642,  sigma = 0.00580
```

In \[6\]:

```latex
calibration_report(swaptions,  data)
```

```latex
----------------------------------------------------------------------------------
    Model Price    Market Price     Implied Vol      Market Vol       Rel Error
----------------------------------------------------------------------------------
        0.00878         0.00949         0.10620         0.11480        -0.07485
        0.00967         0.01008         0.10629         0.11080        -0.04061
        0.00866         0.00872         0.10634         0.10700        -0.00614
        0.00649         0.00623         0.10644         0.10210         0.04237
        0.00354         0.00332         0.10661         0.10000         0.06582
----------------------------------------------------------------------------------
Cumulative Error :         0.11614
```

In \[7\]:

```latex
model = ql.HullWhite(term_structure);
engine = ql.JamshidianSwaptionEngine(model)
swaptions = create_swaption_helpers(data,  index,  term_structure,  engine)

optimization_method = ql.LevenbergMarquardt(1.0e-8, 1.0e-8, 1.0e-8)
end_criteria = ql.EndCriteria(10000,  100,  1e-6,  1e-8,  1e-8)
model.calibrate(swaptions,  optimization_method,  end_criteria)

a,  sigma = model.params()
print "a = %6.5f,  sigma = %6.5f" % (a,  sigma)
calibration_report(swaptions,  data)
```

```latex
a = 0.04642,  sigma = 0.00580
----------------------------------------------------------------------------------
    Model Price    Market Price     Implied Vol      Market Vol       Rel Error
----------------------------------------------------------------------------------
        0.00878         0.00949         0.10620         0.11480        -0.07485
        0.00967         0.01008         0.10629         0.11080        -0.04061
        0.00866         0.00872         0.10634         0.10700        -0.00614
        0.00649         0.00623         0.10644         0.10210         0.04237
        0.00354         0.00332         0.10661         0.10000         0.06582
----------------------------------------------------------------------------------
Cumulative Error :         0.11614
```

### Calibrating Volatility With Fixed Reversion

Some times we need to calibrate with one parameter held fixed. This can be done in the QuantLib libraries. However,  this ability is not exposed in the SWIG wrappers as of version 1.6. I have created a [github issue](https://github.com/lballabio/quantlib/issues/336) and provided a patch to address this issue. You will need this patch to execute the following cells. Below,  the model is calibrated with a fixed reversion value of 5%.

In \[8\]:

```latex
constrained_model = ql.HullWhite(term_structure,  0.05,  0.001);
engine = ql.JamshidianSwaptionEngine(constrained_model)
swaptions = create_swaption_helpers(data,  index,  term_structure,  engine)

optimization_method = ql.LevenbergMarquardt(1.0e-8, 1.0e-8, 1.0e-8)
end_criteria = ql.EndCriteria(10000,  100,  1e-6,  1e-8,  1e-8)
constrained_model.calibrate(swaptions,  optimization_method,  end_criteria,  ql.NoConstraint(),  [],  [True,  False])

a,  sigma = constrained_model.params()
print "a = %6.5f,  sigma = %6.5f" % (a,  sigma)
```

```latex
a = 0.05000,  sigma = 0.00586
```

In \[9\]:

```latex
calibration_report(swaptions,  data)
```

```latex
----------------------------------------------------------------------------------
    Model Price    Market Price     Implied Vol      Market Vol       Rel Error
----------------------------------------------------------------------------------
        0.00878         0.00949         0.10621         0.11480        -0.07474
        0.00967         0.01008         0.10628         0.11080        -0.04068
        0.00866         0.00872         0.10633         0.10700        -0.00626
        0.00649         0.00623         0.10644         0.10210         0.04231
        0.00354         0.00332         0.10663         0.10000         0.06595
----------------------------------------------------------------------------------
Cumulative Error :         0.11615
```

## Black Karasinski Model

The Black Karasinski model is described as:

$$
d ln ⁡ \left(\right. r_{t} \left.\right) = \left(\right. \left(\theta\right)_{t} - a ln ⁡ \left(\right. r_{t} \left.\right) \left.\right) d t + \sigma d W_{t}
$$

In order to calibrate,  we use the `TreeSwaptionEngine` which will work with all short rate models. The calibration is shown below.

In \[10\]:

```latex
model = ql.BlackKarasinski(term_structure);
engine = ql.TreeSwaptionEngine(model,  100)
swaptions = create_swaption_helpers(data,  index,  term_structure,  engine)

optimization_method = ql.LevenbergMarquardt(1.0e-8, 1.0e-8, 1.0e-8)
end_criteria = ql.EndCriteria(10000,  100,  1e-6,  1e-8,  1e-8)
model.calibrate(swaptions,  optimization_method,  end_criteria)

a,  sigma =  model.params()
print "a = %6.5f,  sigma = %6.5f" % (a,  sigma)
```

```latex
a = 0.03902,  sigma = 0.11695
```

In \[11\]:

```latex
calibration_report(swaptions,  data)
```

```latex
----------------------------------------------------------------------------------
    Model Price    Market Price     Implied Vol      Market Vol       Rel Error
----------------------------------------------------------------------------------
        0.00872         0.00949         0.10550         0.11480        -0.08095
        0.00967         0.01008         0.10631         0.11080        -0.04045
        0.00868         0.00872         0.10654         0.10700        -0.00430
        0.00650         0.00623         0.10666         0.10210         0.04446
        0.00355         0.00332         0.10676         0.10000         0.06733
----------------------------------------------------------------------------------
Cumulative Error :         0.12163
```

## G2++ Model

As a final example,  let us look at a calibration example of the 2-factor G2++ model.

$$$
d r_{t} = \varphi \left(\right. t \left.\right) + x_{t} + y_{t}
$$

where $x_{t}$ and $y_{t}$ are defined by
$$
d x_{t}  =  - a x_{t} d t + \sigma d W_{t}^{1} $$

$$ d y_{t}  =  - b y_{t} d t + \eta d W_{t}^{2} $$

$$ d W_{t}^{1} d W_{t}^{2}   =  \rho d t
$$

Once again,  we use the `TreeSwaptionEngine` to value the swaptions in the calibration step.

In \[12\]:

```
model = ql.G2(term_structure);
engine = ql.TreeSwaptionEngine(model,  25)
# Short Interest Rate Model Calibration in QuantLib Python
# engine = ql.FdG2SwaptionEngine(model)
swaptions = create_swaption_helpers(data,  index,  term_structure,  engine)

optimization_method = ql.LevenbergMarquardt(1.0e-8, 1.0e-8, 1.0e-8)
end_criteria = ql.EndCriteria(1000,  100,  1e-6,  1e-8,  1e-8)
model.calibrate(swaptions,  optimization_method,  end_criteria)

a,  sigma,  b,  eta,  rho = model.params()
print "a = %6.5f,  sigma = %6.5f,  b = %6.5f,  eta = %6.5f,  rho = %6.5f " % (a,  sigma,  b,  eta,  rho)
```

```
a = 0.04050,  sigma = 0.00474,  b = 0.04438,  eta = 0.00301,  rho = 0.03541 
```

In \[13\]:

```
calibration_report(swaptions,  data)
```

```
----------------------------------------------------------------------------------
    Model Price    Market Price     Implied Vol      Market Vol       Rel Error
----------------------------------------------------------------------------------
        0.00870         0.00949         0.10535         0.11480        -0.08228
        0.00967         0.01008         0.10633         0.11080        -0.04029
        0.00868         0.00872         0.10651         0.10700        -0.00456
        0.00650         0.00623         0.10665         0.10210         0.04438
        0.00355         0.00332         0.10680         0.10000         0.06770
----------------------------------------------------------------------------------
Cumulative Error :         0.12265
```

## Conclusion

In this post,  we saw some simple examples of calibrating the model to the swaption volatilities.

Click here to download the [ipython notebook](http://gouthamanbalaraman.com/extra/notebooks/interest_rate_model_calibration.ipynb)

   [quantlib](http://gouthamanbalaraman.com/tag/quantlib.html)   [python](http://gouthamanbalaraman.com/tag/python.html)   [finance](http://gouthamanbalaraman.com/tag/finance.html)

---

**Related Post**

- [QuantLib Python Tutorials With Examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html)
- [On the Convergence of Hull White Monte Carlo Simulations](http://gouthamanbalaraman.com/blog/hull-white-simulation-monte-carlo-convergence.html)
- [Valuing Options on Commodity Futures Using QuantLib Python](http://gouthamanbalaraman.com/blog/value-options-commodity-futures-black-formula-quantlib-python.html)
- [QuantLib Python Cookbook Announcement](http://gouthamanbalaraman.com/blog/quantlib-python-cookbook-announcement.html)
- [Valuing Bonds with Credit Spreads in QuantLib Python](http://gouthamanbalaraman.com/blog/bonds-with-spreads-quantlib-python.html)
