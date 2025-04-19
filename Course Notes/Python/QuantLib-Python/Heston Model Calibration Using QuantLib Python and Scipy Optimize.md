---
title: Heston Model Calibration Using QuantLib Python and Scipy Optimize
tags:
  - heston_model
  - option_pricing
  - parameter_calibration
  - quantlib_python
  - scipy_optimize
aliases:
  - Heston Calibration
  - Model Calibration
  - QuantLib Calibration
  - Scipy Optimization
key_concepts:
  - Differential evolution
  - Heston model
  - Least squares method
  - Levenberg-Marquardt solver
  - Local minima solvers
  - Parameter calibration methods
  - QuantLib Python
  - Scipy Optimize package
---

# Heston Model Calibration Using QuantLib Python and Scipy Optimize
In this post we do a deep dive on calibration of Heston model using QuantLib Python and Scipy's Optimize package.

I have discussed parameter calibration in a couple of my earlier posts. In this post I want to show how you can use QuantLib Python and Scipy to do parameter calibration. In order to run this,  you will need to build the QuantLib github master and the latest SWIG code with [my pull request](https://github.com/lballabio/QuantLib-SWIG/pull/26). Alternately,  this should get merged into version 1.9 and you should be able to use it when it is released. This pull request adds some of the moethods of the `CalibratedModel` such as `calibrationError` that we will use in calibrating models using Scipy. QuantLib's strength is all financial models. Scipy's strength is all the solvers and numerical methods. So here,  I will show you how you can make the best of both worlds. We will start as usual by importing the modules.

```python
import QuantLib as ql
from math import pow,   sqrt
import numpy as np
from scipy.optimize import root
```

Let's construct some of the basic dependencies such as the yield and dividend term structures.

```python
day_count = ql.Actual365Fixed()
calendar = ql.UnitedStates()
calculation_date = ql.Date(6,   11,   2015)

spot = 659.37
ql.Settings.instance().evaluationDate = calculation_date

risk_free_rate = 0.01
dividend_rate = 0.0
yield_ts = ql.YieldTermStructureHandle(
    ql.FlatForward(calculation_date,   risk_free_rate,   day_count))
dividend_ts = ql.YieldTermStructureHandle(
    ql.FlatForward(calculation_date,   dividend_rate,   day_count))
```

Following is a sample grid of volatilities for different expiration and strikes.

```python
expiration_dates = [ql.Date(6,  12,  2015),   ql.Date(6,  1,  2016),   ql.Date(6,  2,  2016),  
                    ql.Date(6,  3,  2016),   ql.Date(6,  4,  2016),   ql.Date(6,  5,  2016),   
                    ql.Date(6,  6,  2016),   ql.Date(6,  7,  2016),   ql.Date(6,  8,  2016),  
                    ql.Date(6,  9,  2016),   ql.Date(6,  10,  2016),   ql.Date(6,  11,  2016),   
                    ql.Date(6,  12,  2016),   ql.Date(6,  1,  2017),   ql.Date(6,  2,  2017),  
                    ql.Date(6,  3,  2017),   ql.Date(6,  4,  2017),   ql.Date(6,  5,  2017),   
                    ql.Date(6,  6,  2017),   ql.Date(6,  7,  2017),   ql.Date(6,  8,  2017),  
                    ql.Date(6,  9,  2017),   ql.Date(6,  10,  2017),   ql.Date(6,  11,  2017)]
strikes = [527.50,   560.46,   593.43,   626.40,   659.37,   692.34,   725.31,   758.28]
data = [
[0.37819,   0.34177,   0.30394,   0.27832,   0.26453,   0.25916,   0.25941,   0.26127],  
[0.3445,   0.31769,   0.2933,   0.27614,   0.26575,   0.25729,   0.25228,   0.25202],  
[0.37419,   0.35372,   0.33729,   0.32492,   0.31601,   0.30883,   0.30036,   0.29568],  
[0.37498,   0.35847,   0.34475,   0.33399,   0.32715,   0.31943,   0.31098,   0.30506],  
[0.35941,   0.34516,   0.33296,   0.32275,   0.31867,   0.30969,   0.30239,   0.29631],  
[0.35521,   0.34242,   0.33154,   0.3219,   0.31948,   0.31096,   0.30424,   0.2984],  
[0.35442,   0.34267,   0.33288,   0.32374,   0.32245,   0.31474,   0.30838,   0.30283],  
[0.35384,   0.34286,   0.33386,   0.32507,   0.3246,   0.31745,   0.31135,   0.306],  
[0.35338,   0.343,   0.33464,   0.32614,   0.3263,   0.31961,   0.31371,   0.30852],  
[0.35301,   0.34312,   0.33526,   0.32698,   0.32766,   0.32132,   0.31558,   0.31052],  
[0.35272,   0.34322,   0.33574,   0.32765,   0.32873,   0.32267,   0.31705,   0.31209],  
[0.35246,   0.3433,   0.33617,   0.32822,   0.32965,   0.32383,   0.31831,   0.31344],  
[0.35226,   0.34336,   0.33651,   0.32869,   0.3304,   0.32477,   0.31934,   0.31453],  
[0.35207,   0.34342,   0.33681,   0.32911,   0.33106,   0.32561,   0.32025,   0.3155],  
[0.35171,   0.34327,   0.33679,   0.32931,   0.3319,   0.32665,   0.32139,   0.31675],  
[0.35128,   0.343,   0.33658,   0.32937,   0.33276,   0.32769,   0.32255,   0.31802],  
[0.35086,   0.34274,   0.33637,   0.32943,   0.3336,   0.32872,   0.32368,   0.31927],  
[0.35049,   0.34252,   0.33618,   0.32948,   0.33432,   0.32959,   0.32465,   0.32034],  
[0.35016,   0.34231,   0.33602,   0.32953,   0.33498,   0.3304,   0.32554,   0.32132],  
[0.34986,   0.34213,   0.33587,   0.32957,   0.33556,   0.3311,   0.32631,   0.32217],  
[0.34959,   0.34196,   0.33573,   0.32961,   0.3361,   0.33176,   0.32704,   0.32296],  
[0.34934,   0.34181,   0.33561,   0.32964,   0.33658,   0.33235,   0.32769,   0.32368],  
[0.34912,   0.34167,   0.3355,   0.32967,   0.33701,   0.33288,   0.32827,   0.32432],  
[0.34891,   0.34154,   0.33539,   0.3297,   0.33742,   0.33337,   0.32881,   0.32492]]
```

I have abstracted some of the repetitive methods into python functions. The function `setup_helpers` will construct the Heston model helpers and returns an array of these objects. The `cost_function_generator` is a method to set the cost function and will be used by the Scipy modules. The `calibration_report` lets us evaluate the quality of the fit. The `setup_model` method initializes the `HestonModel` and the `AnalyticHestonEngine` prior to calibration.

```python
def setup_helpers(engine,   expiration_dates,   strikes,   
                  data,   ref_date,   spot,   yield_ts,   
                  dividend_ts):
    heston_helpers = []
    grid_data = []
    for i,   date in enumerate(expiration_dates):
        for j,   s in enumerate(strikes):
            t = (date - ref_date )
            p = ql.Period(t,   ql.Days)
            vols = data[i][j]
            helper = ql.HestonModelHelper(
                p,   calendar,   spot,   s,   
                ql.QuoteHandle(ql.SimpleQuote(vols)),  
                yield_ts,   dividend_ts)
            helper.setPricingEngine(engine)
            heston_helpers.append(helper)
            grid_data.append((date,   s))
    return heston_helpers,   grid_data

def cost_function_generator(model,   helpers,  norm=False):
    def cost_function(params):
        params_ = ql.Array(list(params))
        model.setParams(params_)
        error = [h.calibrationError() for h in helpers]
        if norm:
            return np.sqrt(np.sum(np.abs(error)))
        else:
            return error
    return cost_function

def calibration_report(helpers,   grid_data,   detailed=False):
    avg = 0.0
    if detailed:
        print "%15s %25s %15s %15s %20s" % (
            "Strikes",   "Expiry",   "Market Value",   
             "Model Value",   "Relative Error (%)")
        print "="*100
    for i,   opt in enumerate(helpers):
        err = (opt.modelValue()/opt.marketValue() - 1.0)
        date,  strike = grid_data[i]
        if detailed:
            print "%15.2f %25s %14.5f %15.5f %20.7f " % (
                strike,   str(date),   opt.marketValue(),   
                opt.modelValue(),   
                100.0*(opt.modelValue()/opt.marketValue() - 1.0))
        avg += abs(err)
    avg = avg*100.0/len(helpers)
    if detailed: print "-"*100
    summary = "Average Abs Error (%%) : %5.9f" % (avg)
    print summary
    return avg
    
def setup_model(_yield_ts,   _dividend_ts,   _spot,   
                init_condition=(0.02,  0.2,  0.5,  0.1,  0.01)):
    theta,   kappa,   sigma,   rho,   v0 = init_condition
    process = ql.HestonProcess(_yield_ts,   _dividend_ts,   
                           ql.QuoteHandle(ql.SimpleQuote(_spot)),   
                           v0,   kappa,   theta,   sigma,   rho)
    model = ql.HestonModel(process)
    engine = ql.AnalyticHestonEngine(model) 
    return model,   engine
summary= []
```

### Comparing Different Calibration Methods

Solvers such as Levenberg-Marquardt find local minimas and are very sensitive to the initial conditions. Depending on the starting conditions for your solver,  you could end up with a good set of parameters with good convergence or not so good set of parameters. We will look at two initial conditions for different solvers and see how the local minima solvers perform. We will compare this with differential evolution that looks for global minima.

We will setup the Heston model with two different initial conditions:

```python
- theta,   kappa,   sigma,   rho,   v0 = (0.02,   0.2,   0.5,   0.1,   0.01)
- theta,   kappa,   sigma,   rho,   v0 = (0.07,   0.5,   0.1,   0.1,   0.1)
```

#### Local Solvers

##### Using QuantLib Levenberg-Marquardt Solver

As a first step,  let's look at QuantLib's Levenberg-Marquardt solver. The initial condition considered is `theta,   kappa,   sigma,   rho,   v0 = (0.02,  0.2,  0.5,  0.1,  0.01)`

```python
model1,   engine1 = setup_model(
    yield_ts,   dividend_ts,   spot,   
    init_condition=(0.02,  0.2,  0.5,  0.1,  0.01))
heston_helpers1,   grid_data1 = setup_helpers(
    engine1,   expiration_dates,   strikes,   data,   
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model1.params())
```

```python
%%time
lm = ql.LevenbergMarquardt(1e-8,   1e-8,   1e-8)
model1.calibrate(heston_helpers1,   lm,   
                 ql.EndCriteria(500,   300,   1.0e-8,  1.0e-8,   1.0e-8))
theta,   kappa,   sigma,   rho,   v0 = model1.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers1,   grid_data1)
summary.append(["QL LM1",   error] + list(model1.params()))
```

```python
theta = 0.125748,   kappa = 7.915000,   sigma = 1.887854,   rho = -0.364942,   v0 = 0.055397
Average Abs Error (%) : 3.015268051
CPU times: user 4.86 s,   sys: 0 ns,   total: 4.86 s
Wall time: 4.86 s
```

```python
theta = 0.125748,   kappa = 7.915000,   sigma = 1.887854,   rho = -0.364942,   v0 = 0.055397
Average Abs Error (%) : 3.015268051
CPU times: user 4.86 s,   sys: 0 ns,   total: 4.86 s
Wall time: 4.86 s
```

Methods like Levenberg-Marquardt solve for local minimas and do not search for global minimas. The solver is very sensitive to the initial conditions. Let's set a different set of initial conditions,  and see what happens below. The initial condition considered is `theta,   kappa,   sigma,   rho,   v0 = (0.07,  0.5,  0.1,  0.1,  0.1)`

```python
model1,   engine1 = setup_model(
    yield_ts,   dividend_ts,   spot,   
    init_condition=(0.07,  0.5,  0.1,  0.1,  0.1))
heston_helpers1,   grid_data1 = setup_helpers(
    engine1,   expiration_dates,   strikes,   data,   
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model1.params())
```

```python
%%time
lm = ql.LevenbergMarquardt(1e-8,   1e-8,   1e-8)
model1.calibrate(heston_helpers1,   lm,   
                 ql.EndCriteria(500,   300,   1.0e-8,  1.0e-8,   1.0e-8))
theta,   kappa,   sigma,   rho,   v0 = model1.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers1,   grid_data1)
summary.append(["QL LM2",   error] + list(model1.params()))
```

```python
theta = 0.084523,   kappa = 0.000000,   sigma = 0.132289,   rho = -0.514278,   v0 = 0.099928
Average Abs Error (%) : 11.007433024
CPU times: user 4.97 s,   sys: 0 ns,   total: 4.97 s
Wall time: 4.98 s
```

We see that the solver produces a 11% average of absolute error. This is not particularly great.

##### Using Scipy Levenberg-Marquardt Solver

Here we are going to try the same exercise but using Scipy. Scipy has far more optimization,  minimization and root finding algorithms that are very robust. So by leveraging Scipy,  we can take advantage of this rich set of options at hand.

```python
model2,   engine2 = setup_model(
    yield_ts,   dividend_ts,   spot,   
    init_condition=(0.02,  0.2,  0.5,  0.1,  0.01))
heston_helpers2,   grid_data2 = setup_helpers(
    engine2,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model2.params())
```

```python
%%time
cost_function = cost_function_generator(model2,   heston_helpers2)
sol = root(cost_function,   initial_condition,   method='lm')
theta,   kappa,   sigma,   rho,   v0 = model2.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers2,   grid_data2)
summary.append(["Scipy LM1",   error] + list(model2.params()))
```

```python
theta = 0.125747,   kappa = 7.915687,   sigma = 1.887934,   rho = -0.364944,   v0 = 0.055394
Average Abs Error (%) : 3.015252651
CPU times: user 4.68 s,   sys: 12 ms,   total: 4.69 s
Wall time: 4.65 s
```

The solution for this particular case seems to be fairly robust. Both solvers (QuantLib and Scipy) seem to have landed on more or less the same solution for this particular initial condition. Let's see how Scipy does for the second initial condition considered above - `theta,   kappa,   sigma,   rho,   v0 = (0.07,  0.5,  0.1,  0.1,  0.1)`

```python
model2,   engine2 = setup_model(
    yield_ts,   dividend_ts,   spot,  
    init_condition=(0.07,  0.5,  0.1,  0.1,  0.1))
heston_helpers2,   grid_data2 = setup_helpers(
    engine2,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model2.params())
```

```python
%%time
cost_function = cost_function_generator(model2,   heston_helpers2)
sol = root(cost_function,   initial_condition,   method='lm')
theta,   kappa,   sigma,   rho,   v0 = model2.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers2,   grid_data2)
summary.append(["Scipy LM2",   error] + list(model2.params()))
```

```python
theta = 0.048184,   kappa = -0.548903,   sigma = 0.197958,   rho = -0.999547,   v0 = 0.090571
Average Abs Error (%) : 7.019499509
CPU times: user 20.7 s,   sys: 56 ms,   total: 20.7 s
Wall time: 20.5 s
```

For this particular case,  Scipy solver has performed significantly better. It would be inappropriate to make loud claims about Scipy's superiority based on one observation. Perhaps this calls for a more detailed study for later.

##### Using Least Squares Method

If you want to use a simpler approach like least squares,  you can do that with Scipy. Here is how you would use it.

```python
from scipy.optimize import least_squares
```

```python
model3,   engine3 = setup_model(
    yield_ts,   dividend_ts,   spot,   
    init_condition=(0.02,  0.2,  0.5,  0.1,  0.01))
heston_helpers3,   grid_data3 = setup_helpers(
    engine3,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model3.params())
```

```python
%%time
cost_function = cost_function_generator(model3,   heston_helpers3)
sol = least_squares(cost_function,   initial_condition)
theta,   kappa,   sigma,   rho,   v0 = model3.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers3,   grid_data3)
summary.append(["Scipy LS1",   error] + list(model3.params()))
```

```python
theta = 0.125747,   kappa = 7.915814,   sigma = 1.887949,   rho = -0.364944,   v0 = 0.055394
Average Abs Error (%) : 3.015251175
CPU times: user 4.54 s,   sys: 8 ms,   total: 4.55 s
Wall time: 4.55 s
```

With the second initial condition:

```python
model3,   engine3 = setup_model(
    yield_ts,   dividend_ts,   spot,   
    init_condition=(0.07,  0.5,  0.1,  0.1,  0.1))
heston_helpers3,   grid_data3 = setup_helpers(
    engine3,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model3.params())
```

```python
%%time
cost_function = cost_function_generator(model3,   heston_helpers3)
sol = least_squares(cost_function,   initial_condition)
theta,   kappa,   sigma,   rho,   v0 = model3.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers3,   grid_data3)
summary.append(["Scipy LS2",   error] + list(model3.params()))
```

```python
theta = 3.136774,   kappa = 0.000005,   sigma = -0.000245,   rho = -0.000010,   v0 = 1.597904
Average Abs Error (%) : 5.096414042
CPU times: user 28.1 s,   sys: 16 ms,   total: 28.2 s
Wall time: 28.1 s
```

#### Global Solvers

##### Using Differential Evolution

The above methods are more suited to finding local minimas. One method that makes an attempt at searching for global minima is the differential evolution. Both QuantLib and Scipy have implementations of this method. Scipy however has a lot more bells and whistles to tune and calibrate the methodology. Let's take a look at the Scipy's `differential_evolution` methodology.

```python
from scipy.optimize import differential_evolution
```

```python
model4,   engine4 = setup_model(yield_ts,   dividend_ts,   spot)
heston_helpers4,   grid_data4 = setup_helpers(
    engine4,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model4.params())
bounds = [(0,  1),  (0.01,  15),   (0.01,  1.),   (-1,  1),   (0,  1.0) ]
```

```python
%%time
cost_function = cost_function_generator(
    model4,   heston_helpers4,   norm=True)
sol = differential_evolution(cost_function,   bounds,   maxiter=100)
theta,   kappa,   sigma,   rho,   v0 = model4.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers4,   grid_data4)
summary.append(["Scipy DE1",   error] + list(model4.params()))
```

```python
theta = 0.123221,   kappa = 5.012199,   sigma = 0.950309,   rho = -0.570340,   v0 = 0.078440
Average Abs Error (%) : 2.859113482
CPU times: user 1min 39s,   sys: 144 ms,   total: 1min 39s
Wall time: 1min 39s
```

In the above example,  I am setting the variable `maxiter` in order to limit the time taken. In production scenarios,  you may want to try a larger number or not provide any value and default to 1000. This can help search a larger area of the parameter space.

```python
model4,   engine4 = setup_model(yield_ts,   dividend_ts,   spot)
heston_helpers4,   grid_data4 = setup_helpers(
    engine4,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model4.params())
bounds = [(0,  1),  (0.01,  15),   (0.01,  1.),   (-1,  1),   (0,  1.0) ]
```

```python
%%time
cost_function = cost_function_generator(
    model4,   heston_helpers4,   norm=True)
sol = differential_evolution(cost_function,   bounds,   maxiter=100)
theta,   kappa,   sigma,   rho,   v0 = model4.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers4,   grid_data4)
summary.append(["Scipy DE2",   error] + list(model4.params()))
```

```python
theta = 0.122251,   kappa = 4.996804,   sigma = 0.849266,   rho = -0.637706,   v0 = 0.079484
Average Abs Error (%) : 2.876087363
CPU times: user 1min 57s,   sys: 200 ms,   total: 1min 57s
Wall time: 1min 57s
```

##### Basin Hopping Algorithm

Here we will use the Basin Hopping (annealing like) method to solve for the parameters. A couple things to make note here. The Basin Hopping method works best when used with a minimizer. Here I played with various minimizers and finally decided to use something that supports bounds checking. Without bounds checking,  I often ended with `nan` and did not have a meaningful solution in the end.

I have chosen bounds based on a very basic reasoning. One needs careful reasoning to use appropriate bounds for the problem at hand.

```python
from scipy.optimize import basinhopping
```

```python
class MyBounds(object):
     def __init__(self,   xmin=[0.0.\1,  0.01,  -1,  0],   xmax=[1,  15,  1,  1,  1.0] ):
         self.xmax = np.array(xmax)
         self.xmin = np.array(xmin)
     def __call__(self,   **kwargs):
         x = kwargs["x_new"]
         tmax = bool(np.all(x <= self.xmax))
         tmin = bool(np.all(x >= self.xmin))
         return tmax and tmin
bounds = [(0,  1),  (0.01,  15),   (0.01,  1.),   (-1,  1),   (0,  1.0) ]
```

```python
model5,   engine5 = setup_model(
    yield_ts,   dividend_ts,   spot,  
    init_condition=(0.02,  0.2,  0.5,  0.1,  0.01))
heston_helpers5,   grid_data5 = setup_helpers(
    engine5,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model5.params())
```

```python
%%time
mybound = MyBounds()
minimizer_kwargs = {"method": "L-BFGS-B",   "bounds": bounds }
cost_function = cost_function_generator(
    model5,   heston_helpers5,   norm=True)
sol = basinhopping(cost_function,   initial_condition,   niter=5,  
                   minimizer_kwargs=minimizer_kwargs,  
                   stepsize=0.005,  
                   accept_test=mybound,  
                   interval=10)
theta,   kappa,   sigma,   rho,   v0 = model5.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers5,   grid_data5)
summary.append(["Scipy BH1",   error] + list(model5.params()))
```

```python
theta = 0.123455,   kappa = 5.074067,   sigma = 0.995095,   rho = -0.562106,   v0 = 0.079009
Average Abs Error (%) : 2.850972273
CPU times: user 2min 15s,   sys: 456 ms,   total: 2min 16s
Wall time: 2min 14s
```

```python
model5,   engine5 = setup_model(
    yield_ts,   dividend_ts,   spot,  
    init_condition=(0.07,  0.5,  0.1,  0.1,  0.1))
heston_helpers5,   grid_data5 = setup_helpers(
    engine5,   expiration_dates,   strikes,   data,  
    calculation_date,   spot,   yield_ts,   dividend_ts
)
initial_condition = list(model5.params())
```

```python
%%time
mybound = MyBounds()
minimizer_kwargs = {"method": "L-BFGS-B",   "bounds": bounds}
cost_function = cost_function_generator(
    model5,   heston_helpers5,   norm=True)
sol = basinhopping(cost_function,   initial_condition,   niter=5,  
                   minimizer_kwargs=minimizer_kwargs,  
                   stepsize=0.005,  
                   accept_test=mybound,  
                   interval=10)
theta,   kappa,   sigma,   rho,   v0 = model5.params()
print "theta = %f,   kappa = %f,   sigma = %f,   rho = %f,   v0 = %f" % \
    (theta,   kappa,   sigma,   rho,   v0)
error = calibration_report(heston_helpers5,   grid_data5)
summary.append(["Scipy BH2",   error] + list(model5.params()))
```

```python
theta = 0.123403,   kappa = 4.791319,   sigma = 0.904397,   rho = -0.593711,   v0 = 0.079215
Average Abs Error (%) : 2.863355647
CPU times: user 1min 50s,   sys: 332 ms,   total: 1min 50s
Wall time: 1min 49s
```

#### Summary

Here is a summary of all the results with the calibration error overall,  and the respective parameters. All the local minima methods give parameters that are very different based on the initial condition that we start with. This is different in contrary with the global minimization methods that all end up in more or less the same proximity of each other.

The global solvers such as Differential Evolution and Basin Hopping are capable of finding the global minima and it is sometimes a question of computation resources. Here,  I have lower "iterations" set for these routines for faster solving. Even with such a short threshold,  we get fairly good solution set. I think it is premature to compare the effectiveness of different global solvers just based on the results here. The [scipy optimize](http://docs.scipy.org/doc/scipy/reference/optimize.html) package has detailed documentation with various tuning parameters. I haven't exploited the nuances much,  and is left as an exercise for the reader.

Hope you find this useful!

```python
from pandas import DataFrame
DataFrame(
    summary,  
    columns=["Name",   "Avg Abs Error",  "Theta",   "Kappa",   "Sigma",   "Rho",   "V0"],  
    index=['']*len(summary))
```

```python
|Name|Avg Abs Error|Theta|Kappa|Sigma|Rho|V0|
|---|---|---|---|---|---|---|
||QL LM1|3.015268|0.125748|7.915000e+00|1.887854|-0.364942|0.055397|
||QL LM2|11.007433|0.084523|1.625740e-08|0.132289|-0.514278|0.099928|
||Scipy LM1|3.015253|0.125747|7.915687e+00|1.887934|-0.364944|0.055394|
||Scipy LM2|7.019500|0.048184|-5.489029e-01|0.197958|-0.999547|0.090571|
||Scipy LS1|3.015251|0.125747|7.915814e+00|1.887949|-0.364944|0.055394|
||Scipy LS2|5.096414|3.136774|4.896844e-06|-0.000245|-0.000010|1.597904|
||Scipy DE1|2.859113|0.123221|5.012199e+00|0.950309|-0.570340|0.078440|
||Scipy DE2|2.876087|0.122251|4.996804e+00|0.849266|-0.637706|0.079484|
||Scipy BH1|2.850972|0.123455|5.074067e+00|0.995095|-0.562106|0.079009|
||Scipy BH2|2.863356|0.123403|4.791319e+00|0.904397|-0.593711|0.079215|
```

| Name      | Avg Abs Error | Theta    | Kappa         | Sigma     | Rho       | V0       |
| --------- | ------------- | -------- | ------------- | --------- | --------- | -------- |
| QL LM1    | 3.015268      | 0.125748 | 7.915000e+00  | 1.887854  | -0.364942 | 0.055397 |
| QL LM2    | 11.007433     | 0.084523 | 1.625740e-08  | 0.132289  | -0.514278 | 0.099928 |
| Scipy LM1 | 3.015253      | 0.125747 | 7.915687e+00  | 1.887934  | -0.364944 | 0.055394 |
| Scipy LM2 | 7.019500      | 0.048184 | -5.489029e-01 | 0.197958  | -0.999547 | 0.090571 |
| Scipy LS1 | 3.015251      | 0.125747 | 7.915814e+00  | 1.887949  | -0.364944 | 0.055394 |
| Scipy LS2 | 5.096414      | 3.136774 | 4.896844e-06  | -0.000245 | -0.000010 | 1.597904 |
| Scipy DE1 | 2.859113      | 0.123221 | 5.012199e+00  | 0.950309  | -0.570340 | 0.078440 |
| Scipy DE2 | 2.876087      | 0.122251 | 4.996804e+00  | 0.849266  | -0.637706 | 0.079484 |
| Scipy BH1 | 2.850972      | 0.123455 | 5.074067e+00  | 0.995095  | -0.562106 | 0.079009 |
| Scipy BH2 | 2.863356      | 0.123403 | 4.791319e+00  | 0.904397  | -0.593711 | 0.079215 |