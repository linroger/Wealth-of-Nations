# Heston Model Calibration Using QuantLib Python and Scipy Optimize
In this post we do a deep dive on calibration of Heston model using QuantLib Python and Scipy's Optimize package.

I have discussed parameter calibration in a couple of my earlier posts. In this post I want to show how you can use QuantLib Python and Scipy to do parameter calibration. In order to run this, you will need to build the QuantLib github master and the latest SWIG code with [my pull request](https://github.com/lballabio/QuantLib-SWIG/pull/26). Alternately, this should get merged into version 1.9 and you should be able to use it when it is released. This pull request adds some of the moethods of the `CalibratedModel` such as `calibrationError` that we will use in calibrating models using Scipy. QuantLib's strength is all financial models. Scipy's strength is all the solvers and numerical methods. So here, I will show you how you can make the best of both worlds. We will start as usual by importing the modules.

```
import QuantLib as ql
from math import pow, sqrt
import numpy as np
from scipy.optimize import root
```

Let's construct some of the basic dependencies such as the yield and dividend term structures.

```
day_count = ql.Actual365Fixed()
calendar = ql.UnitedStates()
calculation_date = ql.Date(6, 11, 2015)

spot = 659.37
ql.Settings.instance().evaluationDate = calculation_date

risk_free_rate = 0.01
dividend_rate = 0.0
yield_ts = ql.YieldTermStructureHandle(
    ql.FlatForward(calculation_date, risk_free_rate, day_count))
dividend_ts = ql.YieldTermStructureHandle(
    ql.FlatForward(calculation_date, dividend_rate, day_count))
```

Following is a sample grid of volatilities for different expiration and strikes.

```
expiration_dates = [ql.Date(6,12,2015), ql.Date(6,1,2016), ql.Date(6,2,2016),
                    ql.Date(6,3,2016), ql.Date(6,4,2016), ql.Date(6,5,2016), 
                    ql.Date(6,6,2016), ql.Date(6,7,2016), ql.Date(6,8,2016),
                    ql.Date(6,9,2016), ql.Date(6,10,2016), ql.Date(6,11,2016), 
                    ql.Date(6,12,2016), ql.Date(6,1,2017), ql.Date(6,2,2017),
                    ql.Date(6,3,2017), ql.Date(6,4,2017), ql.Date(6,5,2017), 
                    ql.Date(6,6,2017), ql.Date(6,7,2017), ql.Date(6,8,2017),
                    ql.Date(6,9,2017), ql.Date(6,10,2017), ql.Date(6,11,2017)]
strikes = [527.50, 560.46, 593.43, 626.40, 659.37, 692.34, 725.31, 758.28]
data = [
[0.37819, 0.34177, 0.30394, 0.27832, 0.26453, 0.25916, 0.25941, 0.26127],
[0.3445, 0.31769, 0.2933, 0.27614, 0.26575, 0.25729, 0.25228, 0.25202],
[0.37419, 0.35372, 0.33729, 0.32492, 0.31601, 0.30883, 0.30036, 0.29568],
[0.37498, 0.35847, 0.34475, 0.33399, 0.32715, 0.31943, 0.31098, 0.30506],
[0.35941, 0.34516, 0.33296, 0.32275, 0.31867, 0.30969, 0.30239, 0.29631],
[0.35521, 0.34242, 0.33154, 0.3219, 0.31948, 0.31096, 0.30424, 0.2984],
[0.35442, 0.34267, 0.33288, 0.32374, 0.32245, 0.31474, 0.30838, 0.30283],
[0.35384, 0.34286, 0.33386, 0.32507, 0.3246, 0.31745, 0.31135, 0.306],
[0.35338, 0.343, 0.33464, 0.32614, 0.3263, 0.31961, 0.31371, 0.30852],
[0.35301, 0.34312, 0.33526, 0.32698, 0.32766, 0.32132, 0.31558, 0.31052],
[0.35272, 0.34322, 0.33574, 0.32765, 0.32873, 0.32267, 0.31705, 0.31209],
[0.35246, 0.3433, 0.33617, 0.32822, 0.32965, 0.32383, 0.31831, 0.31344],
[0.35226, 0.34336, 0.33651, 0.32869, 0.3304, 0.32477, 0.31934, 0.31453],
[0.35207, 0.34342, 0.33681, 0.32911, 0.33106, 0.32561, 0.32025, 0.3155],
[0.35171, 0.34327, 0.33679, 0.32931, 0.3319, 0.32665, 0.32139, 0.31675],
[0.35128, 0.343, 0.33658, 0.32937, 0.33276, 0.32769, 0.32255, 0.31802],
[0.35086, 0.34274, 0.33637, 0.32943, 0.3336, 0.32872, 0.32368, 0.31927],
[0.35049, 0.34252, 0.33618, 0.32948, 0.33432, 0.32959, 0.32465, 0.32034],
[0.35016, 0.34231, 0.33602, 0.32953, 0.33498, 0.3304, 0.32554, 0.32132],
[0.34986, 0.34213, 0.33587, 0.32957, 0.33556, 0.3311, 0.32631, 0.32217],
[0.34959, 0.34196, 0.33573, 0.32961, 0.3361, 0.33176, 0.32704, 0.32296],
[0.34934, 0.34181, 0.33561, 0.32964, 0.33658, 0.33235, 0.32769, 0.32368],
[0.34912, 0.34167, 0.3355, 0.32967, 0.33701, 0.33288, 0.32827, 0.32432],
[0.34891, 0.34154, 0.33539, 0.3297, 0.33742, 0.33337, 0.32881, 0.32492]]
```

I have abstracted some of the repetitive methods into python functions. The function `setup_helpers` will construct the Heston model helpers and returns an array of these objects. The `cost_function_generator` is a method to set the cost function and will be used by the Scipy modules. The `calibration_report` lets us evaluate the quality of the fit. The `setup_model` method initializes the `HestonModel` and the `AnalyticHestonEngine` prior to calibration.

```
def setup_helpers(engine, expiration_dates, strikes, 
                  data, ref_date, spot, yield_ts, 
                  dividend_ts):
    heston_helpers = []
    grid_data = []
    for i, date in enumerate(expiration_dates):
        for j, s in enumerate(strikes):
            t = (date - ref_date )
            p = ql.Period(t, ql.Days)
            vols = data[i][j]
            helper = ql.HestonModelHelper(
                p, calendar, spot, s, 
                ql.QuoteHandle(ql.SimpleQuote(vols)),
                yield_ts, dividend_ts)
            helper.setPricingEngine(engine)
            heston_helpers.append(helper)
            grid_data.append((date, s))
    return heston_helpers, grid_data

def cost_function_generator(model, helpers,norm=False):
    def cost_function(params):
        params_ = ql.Array(list(params))
        model.setParams(params_)
        error = [h.calibrationError() for h in helpers]
        if norm:
            return np.sqrt(np.sum(np.abs(error)))
        else:
            return error
    return cost_function

def calibration_report(helpers, grid_data, detailed=False):
    avg = 0.0
    if detailed:
        print "%15s %25s %15s %15s %20s" % (
            "Strikes", "Expiry", "Market Value", 
             "Model Value", "Relative Error (%)")
        print "="*100
    for i, opt in enumerate(helpers):
        err = (opt.modelValue()/opt.marketValue() - 1.0)
        date,strike = grid_data[i]
        if detailed:
            print "%15.2f %25s %14.5f %15.5f %20.7f " % (
                strike, str(date), opt.marketValue(), 
                opt.modelValue(), 
                100.0*(opt.modelValue()/opt.marketValue() - 1.0))
        avg += abs(err)
    avg = avg*100.0/len(helpers)
    if detailed: print "-"*100
    summary = "Average Abs Error (%%) : %5.9f" % (avg)
    print summary
    return avg
    
def setup_model(_yield_ts, _dividend_ts, _spot, 
                init_condition=(0.02,0.2,0.5,0.1,0.01)):
    theta, kappa, sigma, rho, v0 = init_condition
    process = ql.HestonProcess(_yield_ts, _dividend_ts, 
                           ql.QuoteHandle(ql.SimpleQuote(_spot)), 
                           v0, kappa, theta, sigma, rho)
    model = ql.HestonModel(process)
    engine = ql.AnalyticHestonEngine(model) 
    return model, engine
summary= []
```

### Comparing Different Calibration Methods

Solvers such as Levenberg-Marquardt find local minimas and are very sensitive to the initial conditions. Depending on the starting conditions for your solver, you could end up with a good set of parameters with good convergence or not so good set of parameters. We will look at two initial conditions for different solvers and see how the local minima solvers perform. We will compare this with differential evolution that looks for global minima.

We will setup the Heston model with two different initial conditions:

```
- theta, kappa, sigma, rho, v0 = (0.02, 0.2, 0.5, 0.1, 0.01)
- theta, kappa, sigma, rho, v0 = (0.07, 0.5, 0.1, 0.1, 0.1)
```

#### Local Solvers

##### Using QuantLib Levenberg-Marquardt Solver

As a first step, let's look at QuantLib's Levenberg-Marquardt solver. The initial condition considered is `theta, kappa, sigma, rho, v0 = (0.02,0.2,0.5,0.1,0.01)`

```
```
- theta, kappa, sigma, rho, v0 = (0.02, 0.2, 0.5, 0.1, 0.01)
- theta, kappa, sigma, rho, v0 = (0.07, 0.5, 0.1, 0.1, 0.1)
```
```

```
<span></span><span>%%</span><span>time</span>
<span>lm</span> <span>=</span> <span>ql</span><span>.</span><span>LevenbergMarquardt</span><span>(</span><span>1e-8</span><span>,</span> <span>1e-8</span><span>,</span> <span>1e-8</span><span>)</span>
<span>model1</span><span>.</span><span>calibrate</span><span>(</span><span>heston_helpers1</span><span>,</span> <span>lm</span><span>,</span> 
                 <span>ql</span><span>.</span><span>EndCriteria</span><span>(</span><span>500</span><span>,</span> <span>300</span><span>,</span> <span>1.0e-8</span><span>,</span><span>1.0e-8</span><span>,</span> <span>1.0e-8</span><span>))</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model1</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers1</span><span>,</span> <span>grid_data1</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"QL LM1"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model1</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.125748, kappa = 7.915000, sigma = 1.887854, rho = -0.364942, v0 = 0.055397
Average Abs Error (%) : 3.015268051
CPU times: user 4.86 s, sys: 0 ns, total: 4.86 s
Wall time: 4.86 s
```

Methods like Levenberg-Marquardt solve for local minimas and do not search for global minimas. The solver is very sensitive to the initial conditions. Let's set a different set of initial conditions, and see what happens below. The initial condition considered is `theta, kappa, sigma, rho, v0 = (0.07,0.5,0.1,0.1,0.1)`

```
<span></span><span>model1</span><span>,</span> <span>engine1</span> <span>=</span> <span>setup_model</span><span>(</span>
    <span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>,</span> 
    <span>init_condition</span><span>=</span><span>(</span><span>0.07</span><span>,</span><span>0.5</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>))</span>
<span>heston_helpers1</span><span>,</span> <span>grid_data1</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine1</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span> 
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model1</span><span>.</span><span>params</span><span>())</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>lm</span> <span>=</span> <span>ql</span><span>.</span><span>LevenbergMarquardt</span><span>(</span><span>1e-8</span><span>,</span> <span>1e-8</span><span>,</span> <span>1e-8</span><span>)</span>
<span>model1</span><span>.</span><span>calibrate</span><span>(</span><span>heston_helpers1</span><span>,</span> <span>lm</span><span>,</span> 
                 <span>ql</span><span>.</span><span>EndCriteria</span><span>(</span><span>500</span><span>,</span> <span>300</span><span>,</span> <span>1.0e-8</span><span>,</span><span>1.0e-8</span><span>,</span> <span>1.0e-8</span><span>))</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model1</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers1</span><span>,</span> <span>grid_data1</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"QL LM2"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model1</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.084523, kappa = 0.000000, sigma = 0.132289, rho = -0.514278, v0 = 0.099928
Average Abs Error (%) : 11.007433024
CPU times: user 4.97 s, sys: 0 ns, total: 4.97 s
Wall time: 4.98 s
```

We see that the solver produces a 11% average of absolute error. This is not particularly great.

##### Using Scipy Levenberg-Marquardt Solver

Here we are going to try the same exercise but using Scipy. Scipy has far more optimization, minimization and root finding algorithms that are very robust. So by leveraging Scipy, we can take advantage of this rich set of options at hand.

```
<span></span><span>model2</span><span>,</span> <span>engine2</span> <span>=</span> <span>setup_model</span><span>(</span>
    <span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>,</span> 
    <span>init_condition</span><span>=</span><span>(</span><span>0.02</span><span>,</span><span>0.2</span><span>,</span><span>0.5</span><span>,</span><span>0.1</span><span>,</span><span>0.01</span><span>))</span>
<span>heston_helpers2</span><span>,</span> <span>grid_data2</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine2</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model2</span><span>.</span><span>params</span><span>())</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span><span>model2</span><span>,</span> <span>heston_helpers2</span><span>)</span>
<span>sol</span> <span>=</span> <span>root</span><span>(</span><span>cost_function</span><span>,</span> <span>initial_condition</span><span>,</span> <span>method</span><span>=</span><span>'lm'</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model2</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers2</span><span>,</span> <span>grid_data2</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy LM1"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model2</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.125747, kappa = 7.915687, sigma = 1.887934, rho = -0.364944, v0 = 0.055394
Average Abs Error (%) : 3.015252651
CPU times: user 4.68 s, sys: 12 ms, total: 4.69 s
Wall time: 4.65 s
```

The solution for this particular case seems to be fairly robust. Both solvers (QuantLib and Scipy) seem to have landed on more or less the same solution for this particular initial condition. Let's see how Scipy does for the second initial condition considered above - `theta, kappa, sigma, rho, v0 = (0.07,0.5,0.1,0.1,0.1)`

```
<span></span><span>model2</span><span>,</span> <span>engine2</span> <span>=</span> <span>setup_model</span><span>(</span>
    <span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>,</span>
    <span>init_condition</span><span>=</span><span>(</span><span>0.07</span><span>,</span><span>0.5</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>))</span>
<span>heston_helpers2</span><span>,</span> <span>grid_data2</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine2</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model2</span><span>.</span><span>params</span><span>())</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span><span>model2</span><span>,</span> <span>heston_helpers2</span><span>)</span>
<span>sol</span> <span>=</span> <span>root</span><span>(</span><span>cost_function</span><span>,</span> <span>initial_condition</span><span>,</span> <span>method</span><span>=</span><span>'lm'</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model2</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers2</span><span>,</span> <span>grid_data2</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy LM2"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model2</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.048184, kappa = -0.548903, sigma = 0.197958, rho = -0.999547, v0 = 0.090571
Average Abs Error (%) : 7.019499509
CPU times: user 20.7 s, sys: 56 ms, total: 20.7 s
Wall time: 20.5 s
```

For this particular case, Scipy solver has performed significantly better. It would be inappropriate to make loud claims about Scipy's superiority based on one observation. Perhaps this calls for a more detailed study for later.

##### Using Least Squares Method

If you want to use a simpler approach like least squares, you can do that with Scipy. Here is how you would use it.

```
<span></span><span>from</span> <span>scipy.optimize</span> <span>import</span> <span>least_squares</span>
```

```
<span></span><span>model3</span><span>,</span> <span>engine3</span> <span>=</span> <span>setup_model</span><span>(</span>
    <span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>,</span> 
    <span>init_condition</span><span>=</span><span>(</span><span>0.02</span><span>,</span><span>0.2</span><span>,</span><span>0.5</span><span>,</span><span>0.1</span><span>,</span><span>0.01</span><span>))</span>
<span>heston_helpers3</span><span>,</span> <span>grid_data3</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine3</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model3</span><span>.</span><span>params</span><span>())</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span><span>model3</span><span>,</span> <span>heston_helpers3</span><span>)</span>
<span>sol</span> <span>=</span> <span>least_squares</span><span>(</span><span>cost_function</span><span>,</span> <span>initial_condition</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model3</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers3</span><span>,</span> <span>grid_data3</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy LS1"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model3</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.125747, kappa = 7.915814, sigma = 1.887949, rho = -0.364944, v0 = 0.055394
Average Abs Error (%) : 3.015251175
CPU times: user 4.54 s, sys: 8 ms, total: 4.55 s
Wall time: 4.55 s
```

With the second initial condition:

```
<span></span><span>model3</span><span>,</span> <span>engine3</span> <span>=</span> <span>setup_model</span><span>(</span>
    <span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>,</span> 
    <span>init_condition</span><span>=</span><span>(</span><span>0.07</span><span>,</span><span>0.5</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>))</span>
<span>heston_helpers3</span><span>,</span> <span>grid_data3</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine3</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model3</span><span>.</span><span>params</span><span>())</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span><span>model3</span><span>,</span> <span>heston_helpers3</span><span>)</span>
<span>sol</span> <span>=</span> <span>least_squares</span><span>(</span><span>cost_function</span><span>,</span> <span>initial_condition</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model3</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers3</span><span>,</span> <span>grid_data3</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy LS2"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model3</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 3.136774, kappa = 0.000005, sigma = -0.000245, rho = -0.000010, v0 = 1.597904
Average Abs Error (%) : 5.096414042
CPU times: user 28.1 s, sys: 16 ms, total: 28.2 s
Wall time: 28.1 s
```

#### Global Solvers

##### Using Differential Evolution

The above methods are more suited to finding local minimas. One method that makes an attempt at searching for global minima is the differential evolution. Both QuantLib and Scipy have implementations of this method. Scipy however has a lot more bells and whistles to tune and calibrate the methodology. Let's take a look at the Scipy's `differential_evolution` methodology.

```
<span></span><span>from</span> <span>scipy.optimize</span> <span>import</span> <span>differential_evolution</span>
```

```
<span></span><span>model4</span><span>,</span> <span>engine4</span> <span>=</span> <span>setup_model</span><span>(</span><span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>)</span>
<span>heston_helpers4</span><span>,</span> <span>grid_data4</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine4</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model4</span><span>.</span><span>params</span><span>())</span>
<span>bounds</span> <span>=</span> <span>[(</span><span>0</span><span>,</span><span>1</span><span>),(</span><span>0.01</span><span>,</span><span>15</span><span>),</span> <span>(</span><span>0.01</span><span>,</span><span>1.</span><span>),</span> <span>(</span><span>-</span><span>1</span><span>,</span><span>1</span><span>),</span> <span>(</span><span>0</span><span>,</span><span>1.0</span><span>)</span> <span>]</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span>
    <span>model4</span><span>,</span> <span>heston_helpers4</span><span>,</span> <span>norm</span><span>=</span><span>True</span><span>)</span>
<span>sol</span> <span>=</span> <span>differential_evolution</span><span>(</span><span>cost_function</span><span>,</span> <span>bounds</span><span>,</span> <span>maxiter</span><span>=</span><span>100</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model4</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers4</span><span>,</span> <span>grid_data4</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy DE1"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model4</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.123221, kappa = 5.012199, sigma = 0.950309, rho = -0.570340, v0 = 0.078440
Average Abs Error (%) : 2.859113482
CPU times: user 1min 39s, sys: 144 ms, total: 1min 39s
Wall time: 1min 39s
```

In the above example, I am setting the variable `maxiter` in order to limit the time taken. In production scenarios, you may want to try a larger number or not provide any value and default to 1000. This can help search a larger area of the parameter space.

```
<span></span><span>model4</span><span>,</span> <span>engine4</span> <span>=</span> <span>setup_model</span><span>(</span><span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>)</span>
<span>heston_helpers4</span><span>,</span> <span>grid_data4</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine4</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model4</span><span>.</span><span>params</span><span>())</span>
<span>bounds</span> <span>=</span> <span>[(</span><span>0</span><span>,</span><span>1</span><span>),(</span><span>0.01</span><span>,</span><span>15</span><span>),</span> <span>(</span><span>0.01</span><span>,</span><span>1.</span><span>),</span> <span>(</span><span>-</span><span>1</span><span>,</span><span>1</span><span>),</span> <span>(</span><span>0</span><span>,</span><span>1.0</span><span>)</span> <span>]</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span>
    <span>model4</span><span>,</span> <span>heston_helpers4</span><span>,</span> <span>norm</span><span>=</span><span>True</span><span>)</span>
<span>sol</span> <span>=</span> <span>differential_evolution</span><span>(</span><span>cost_function</span><span>,</span> <span>bounds</span><span>,</span> <span>maxiter</span><span>=</span><span>100</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model4</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers4</span><span>,</span> <span>grid_data4</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy DE2"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model4</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.122251, kappa = 4.996804, sigma = 0.849266, rho = -0.637706, v0 = 0.079484
Average Abs Error (%) : 2.876087363
CPU times: user 1min 57s, sys: 200 ms, total: 1min 57s
Wall time: 1min 57s
```

##### Basin Hopping Algorithm

Here we will use the Basin Hopping (annealing like) method to solve for the parameters. A couple things to make note here. The Basin Hopping method works best when used wiht a minimizer. Here I played with various minimizers and finally decided to use something that supports bounds checking. Without bounds checking, I often ended with `nan` and did not have a meaningful solution in the end.

I have chosen bounds based on a very basic reasoning. One needs careful reasoning to use appropriate bounds for the problem at hand.

```
<span></span><span>from</span> <span>scipy.optimize</span> <span>import</span> <span>basinhopping</span>
```

```
<span></span><span>class</span> <span>MyBounds</span><span>(</span><span>object</span><span>):</span>
     <span>def</span> <span>__init__</span><span>(</span><span>self</span><span>,</span> <span>xmin</span><span>=</span><span>[</span><span>0.</span><span>,</span><span>0.01</span><span>,</span><span>0.01</span><span>,</span><span>-</span><span>1</span><span>,</span><span>0</span><span>],</span> <span>xmax</span><span>=</span><span>[</span><span>1</span><span>,</span><span>15</span><span>,</span><span>1</span><span>,</span><span>1</span><span>,</span><span>1.0</span><span>]</span> <span>):</span>
         <span>self</span><span>.</span><span>xmax</span> <span>=</span> <span>np</span><span>.</span><span>array</span><span>(</span><span>xmax</span><span>)</span>
         <span>self</span><span>.</span><span>xmin</span> <span>=</span> <span>np</span><span>.</span><span>array</span><span>(</span><span>xmin</span><span>)</span>
     <span>def</span> <span>__call__</span><span>(</span><span>self</span><span>,</span> <span>**</span><span>kwargs</span><span>):</span>
         <span>x</span> <span>=</span> <span>kwargs</span><span>[</span><span>"x_new"</span><span>]</span>
         <span>tmax</span> <span>=</span> <span>bool</span><span>(</span><span>np</span><span>.</span><span>all</span><span>(</span><span>x</span> <span>&lt;=</span> <span>self</span><span>.</span><span>xmax</span><span>))</span>
         <span>tmin</span> <span>=</span> <span>bool</span><span>(</span><span>np</span><span>.</span><span>all</span><span>(</span><span>x</span> <span>&gt;=</span> <span>self</span><span>.</span><span>xmin</span><span>))</span>
         <span>return</span> <span>tmax</span> <span>and</span> <span>tmin</span>
<span>bounds</span> <span>=</span> <span>[(</span><span>0</span><span>,</span><span>1</span><span>),(</span><span>0.01</span><span>,</span><span>15</span><span>),</span> <span>(</span><span>0.01</span><span>,</span><span>1.</span><span>),</span> <span>(</span><span>-</span><span>1</span><span>,</span><span>1</span><span>),</span> <span>(</span><span>0</span><span>,</span><span>1.0</span><span>)</span> <span>]</span>
```

```
<span></span><span>model5</span><span>,</span> <span>engine5</span> <span>=</span> <span>setup_model</span><span>(</span>
    <span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>,</span>
    <span>init_condition</span><span>=</span><span>(</span><span>0.02</span><span>,</span><span>0.2</span><span>,</span><span>0.5</span><span>,</span><span>0.1</span><span>,</span><span>0.01</span><span>))</span>
<span>heston_helpers5</span><span>,</span> <span>grid_data5</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine5</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model5</span><span>.</span><span>params</span><span>())</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>mybound</span> <span>=</span> <span>MyBounds</span><span>()</span>
<span>minimizer_kwargs</span> <span>=</span> <span>{</span><span>"method"</span><span>:</span> <span>"L-BFGS-B"</span><span>,</span> <span>"bounds"</span><span>:</span> <span>bounds</span> <span>}</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span>
    <span>model5</span><span>,</span> <span>heston_helpers5</span><span>,</span> <span>norm</span><span>=</span><span>True</span><span>)</span>
<span>sol</span> <span>=</span> <span>basinhopping</span><span>(</span><span>cost_function</span><span>,</span> <span>initial_condition</span><span>,</span> <span>niter</span><span>=</span><span>5</span><span>,</span>
                   <span>minimizer_kwargs</span><span>=</span><span>minimizer_kwargs</span><span>,</span>
                   <span>stepsize</span><span>=</span><span>0.005</span><span>,</span>
                   <span>accept_test</span><span>=</span><span>mybound</span><span>,</span>
                   <span>interval</span><span>=</span><span>10</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model5</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers5</span><span>,</span> <span>grid_data5</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy BH1"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model5</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.123455, kappa = 5.074067, sigma = 0.995095, rho = -0.562106, v0 = 0.079009
Average Abs Error (%) : 2.850972273
CPU times: user 2min 15s, sys: 456 ms, total: 2min 16s
Wall time: 2min 14s
```

```
<span></span><span>model5</span><span>,</span> <span>engine5</span> <span>=</span> <span>setup_model</span><span>(</span>
    <span>yield_ts</span><span>,</span> <span>dividend_ts</span><span>,</span> <span>spot</span><span>,</span>
    <span>init_condition</span><span>=</span><span>(</span><span>0.07</span><span>,</span><span>0.5</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>,</span><span>0.1</span><span>))</span>
<span>heston_helpers5</span><span>,</span> <span>grid_data5</span> <span>=</span> <span>setup_helpers</span><span>(</span>
    <span>engine5</span><span>,</span> <span>expiration_dates</span><span>,</span> <span>strikes</span><span>,</span> <span>data</span><span>,</span>
    <span>calculation_date</span><span>,</span> <span>spot</span><span>,</span> <span>yield_ts</span><span>,</span> <span>dividend_ts</span>
<span>)</span>
<span>initial_condition</span> <span>=</span> <span>list</span><span>(</span><span>model5</span><span>.</span><span>params</span><span>())</span>
```

```
<span></span><span>%%</span><span>time</span>
<span>mybound</span> <span>=</span> <span>MyBounds</span><span>()</span>
<span>minimizer_kwargs</span> <span>=</span> <span>{</span><span>"method"</span><span>:</span> <span>"L-BFGS-B"</span><span>,</span> <span>"bounds"</span><span>:</span> <span>bounds</span><span>}</span>
<span>cost_function</span> <span>=</span> <span>cost_function_generator</span><span>(</span>
    <span>model5</span><span>,</span> <span>heston_helpers5</span><span>,</span> <span>norm</span><span>=</span><span>True</span><span>)</span>
<span>sol</span> <span>=</span> <span>basinhopping</span><span>(</span><span>cost_function</span><span>,</span> <span>initial_condition</span><span>,</span> <span>niter</span><span>=</span><span>5</span><span>,</span>
                   <span>minimizer_kwargs</span><span>=</span><span>minimizer_kwargs</span><span>,</span>
                   <span>stepsize</span><span>=</span><span>0.005</span><span>,</span>
                   <span>accept_test</span><span>=</span><span>mybound</span><span>,</span>
                   <span>interval</span><span>=</span><span>10</span><span>)</span>
<span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span> <span>=</span> <span>model5</span><span>.</span><span>params</span><span>()</span>
<span>print</span> <span>"theta = </span><span>%f</span><span>, kappa = </span><span>%f</span><span>, sigma = </span><span>%f</span><span>, rho = </span><span>%f</span><span>, v0 = </span><span>%f</span><span>"</span> <span>%</span> \
    <span>(</span><span>theta</span><span>,</span> <span>kappa</span><span>,</span> <span>sigma</span><span>,</span> <span>rho</span><span>,</span> <span>v0</span><span>)</span>
<span>error</span> <span>=</span> <span>calibration_report</span><span>(</span><span>heston_helpers5</span><span>,</span> <span>grid_data5</span><span>)</span>
<span>summary</span><span>.</span><span>append</span><span>([</span><span>"Scipy BH2"</span><span>,</span> <span>error</span><span>]</span> <span>+</span> <span>list</span><span>(</span><span>model5</span><span>.</span><span>params</span><span>()))</span>
```

```
theta = 0.123403, kappa = 4.791319, sigma = 0.904397, rho = -0.593711, v0 = 0.079215
Average Abs Error (%) : 2.863355647
CPU times: user 1min 50s, sys: 332 ms, total: 1min 50s
Wall time: 1min 49s
```

#### Summary

Here is a summary of all the results with the calibration error overall, and the respective parameters. All the local minima methods give parameters that are very different based on the initial condition that we start with. This is different in contrary with the global minimization methods that all end up in more or less the same proximity of each other.

The global solvers such as Differential Evolution and Basin Hopping are capable of finding the global minima and it is sometimes a question of computation resources. Here, I have lower "iterations" set for these routines for faster solving. Even with such a short threshold, we get fairly good solution set. I think it is premature to compare the effectiveness of different global solvers just based on the results here. The [scipy optimize](http://docs.scipy.org/doc/scipy/reference/optimize.html) package has detailed documentation with various tuning parameters. I haven't exploited the nuances much, and is left as an exercise for the reader.

Hope you find this useful!

```
<span></span><span>from</span> <span>pandas</span> <span>import</span> <span>DataFrame</span>
<span>DataFrame</span><span>(</span>
    <span>summary</span><span>,</span>
    <span>columns</span><span>=</span><span>[</span><span>"Name"</span><span>,</span> <span>"Avg Abs Error"</span><span>,</span><span>"Theta"</span><span>,</span> <span>"Kappa"</span><span>,</span> <span>"Sigma"</span><span>,</span> <span>"Rho"</span><span>,</span> <span>"V0"</span><span>],</span>
    <span>index</span><span>=</span><span>[</span><span>''</span><span>]</span><span>*</span><span>len</span><span>(</span><span>summary</span><span>))</span>
```

|  | Name | Avg Abs Error | Theta | Kappa | Sigma | Rho | V0 |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  | QL LM1 | 3.015268 | 0.125748 | 7.915000e+00 | 1.887854 | -0.364942 | 0.055397 |
|  | QL LM2 | 11.007433 | 0.084523 | 1.625740e-08 | 0.132289 | -0.514278 | 0.099928 |
|  | Scipy LM1 | 3.015253 | 0.125747 | 7.915687e+00 | 1.887934 | -0.364944 | 0.055394 |
|  | Scipy LM2 | 7.019500 | 0.048184 | -5.489029e-01 | 0.197958 | -0.999547 | 0.090571 |
|  | Scipy LS1 | 3.015251 | 0.125747 | 7.915814e+00 | 1.887949 | -0.364944 | 0.055394 |
|  | Scipy LS2 | 5.096414 | 3.136774 | 4.896844e-06 | -0.000245 | -0.000010 | 1.597904 |
|  | Scipy DE1 | 2.859113 | 0.123221 | 5.012199e+00 | 0.950309 | -0.570340 | 0.078440 |
|  | Scipy DE2 | 2.876087 | 0.122251 | 4.996804e+00 | 0.849266 | -0.637706 | 0.079484 |
|  | Scipy BH1 | 2.850972 | 0.123455 | 5.074067e+00 | 0.995095 | -0.562106 | 0.079009 |
|  | Scipy BH2 | 2.863356 | 0.123403 | 4.791319e+00 | 0.904397 | -0.593711 | 0.079215 |