---
tags: [title,  version,  publisher]
title: Untitled
---

# Untitled
! $$$$ (/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/title\_page. Jpg) $$$${ #title \_page. Xhtml} ::: { #title \_page. Xhtml\_cover-image} ! $$QuantLib Python Cookbook$$ (/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/title\_page. Jpg) ::: $$$${ #version \_page. Xhtml} ## QuantLib Python Cookbook   #### Luigi Ballabio and Goutham Balaraman   This book is for sale at This version was published on 2021-04-20 ! $$publisher\\'s logo$$ (/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub-logo. Png){ #publisher -logo} \\\*   \\\*   \\\*   \\\*   \\\* This is a $$Leanpub$$ ( http://leanpub.com ) book. Leanpub empowers authors and publishers with the Lean Publishing process. $$Lean Publishing$$ ( http://leanpub.com/manifesto ) is the act of publishing an in-progress ebook using lightweight tools and many iterations to get reader feedback,  pivot until you have the right book and build traction once you do. \\\*   \\\*   \\\*   \\\*   \\\*
© 2014 - 2021 Luigi Ballabio and Goutham Balaraman
$$$${ #toc . xhtml} ::: {. Section .frontmatter .TableOfContents .frontmatter .toc} ## Table of Contents { #toc . xhtml\_toc}
\## Guide 1. $$Begin Reading$$ ( #chap00 . xhtml){. Bodymatter}
::: $$$${ #chap00 . xhtml}
The authors have used good faith effort in preparation of this book,    but make no expressed or implied warranty of any kind and disclaim without limitation all responsibility for errors or omissions. No liability is assumed for incidental or consequential damages in connection with or arising out of the use of the information or programs contained herein. Use of the information and instructions in this book is at your own risk. The cover image is in the public domain and available from the $$New York Public Library$$ ( http://digitalcollections.nypl.org/items/510d47df-335e-a3d9-e040-e00a18064a99 ). The cover font is Open Sans Condensed,    released by $$Steve Matteson$$ ( https://twitter.com/SteveMatteson1 ) under the $$Apache License version 2.0$$ ( http://www.apache.org/licenses/LICENSE-2.0 ).
$$$${ #chap01 . xhtml}
\## A note on Python and C++ { #chap01 . xhtml\_leanpub-auto-a-note-on-python-and-c} The choice of using the QuantLib Python bindings and Jupyter was due to their interactivity,    which make it easier to demonstrate features,    and to the fact that the platform provides out of the box excellent modules like \`matplotlib\` for graphing and \`pandas\` for data analysis. This choice might seem to leave C++ users out in the cold. However,    it's easy enough to translate the Python code shown here into the corresponding C++ code. An example of such translation is shown in the appendix.
$$$${ #chap02 . xhtml}
\## Code conventions used in this book { #chap02 . xhtml\_leanpub-auto-code-conventions-used-in-this-book} The recipes in this cookbook are written as $$Jupyter notebooks$$ ( http://jupyter.org/ ),    and follow their structure: blocks of explanatory text,    like the one you're reading now,    are mixed with cells containing Python code (\*inputs\*) and the results of executing it (\*outputs\*). The code and its output---if any---are marked by \`In $$N$$ \` and \`Out $$N$$ \`,    respectively,    with \`N\` being the index of the cell. You can see an example in the computations below:
    In [1]: def f (x,    y):
	    Return x + 2*y
    In [2]: a = 4
            B = 2
            F (a,    b)
    Out[2]: 8
By default,    Jupyter displays the result of the last instruction as the output of a cell,    like it did above; however,    \`print\` statements can display further results.
    In [3]: print (a)
            Print (b)
            Print (f (b,    a))
    Out[3]: 4
            2
            10
Jupyter also knows a few specific data types,    such as Pandas data frames,    and displays them in a more readable way:
    In [4]: import pandas as pd
            Pd.DataFrame ({ 'foo': [1,   2,   3],    'bar': ['a',   'b',   'c'] })
    Out[4]: 
  Foo bar --- ----- ----- 0 1 a 1 2 b 2 3 c The index of the cells shows the order of their execution. Jupyter doesn't constrain it; however,    in all of the recipes of this book the cells were executed in sequential order as displayed. All cells are executed in the global Python scope; this means that,    as we execute the code in the recipes,    all variables,    functions and classes defined in a cell are available to the ones that follow. Notebooks can also include plots,    as in the following cell:
    In [5]: %matplotlib inline
            Import numpy as np
            Import utils
            F,    ax = utils.Plot (figsize=(10,   2))
            Ax.Plot ([0,    0.25,    0.5,    0.75,    1.0],    np.Random.Random (5))
    Out[5]: [<matplotlib.lines.Line2D at 0x7fef5c24fda0>]
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/cookbook_code_conventions-5.png)
::: As you might have noted,    the cell above also printed a textual representation of the object returned from the plot,    since it's the result of the last instruction in the cell. To prevent this,    cells in the recipes might have a semicolon at the end,    as in the next cell. This is just a quirk of the Jupyter display system,    and it doesn't have any particular significance; I'm mentioning it here just so that you dont't get confused by it.
    In [6]: f,    ax = utils.Plot (figsize=(10,   2))
            Ax.Plot ([0,    0.25,    0.5,    0.75,    1.0],    np.Random.Random (5));
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/cookbook_code_conventions-6.png)
::: Finally,    the \`utils\` module that I imported above is a short module containing convenience functions,    mostly related to plots,    for the notebooks in this collection. It's not necessary to understand its implementation to follow the recipes,    and therefore we won't cover it here; but if you're interested and want to look at it,    it's included in the zip archive that you can download from Leanpub if you purchased the book. \`\`{=html}
$$$${ #chap03 . xhtml}
\# Basics { #chap03 . xhtml\_leanpub-auto-basics}
$$$${ #chap04 . xhtml}
\## $$1.$${. Section-number}QuantLib basics { #chap04 . xhtml\_quantlib-basics} In this chapter we will introduce some of the basic concepts such as \`Date\`,    \`Period\`,    \`Calendar\` and \`Schedule\`. These are QuantLib constructs that are used throughout the library in creation of instruments,    models,    term structures etc.
    In [1]: import QuantLib as ql
            Import pandas as pd
\##### Date Class { #chap04 . xhtml\_leanpub-auto-date-class} The \`Date\` object can be created using the constructor as \`Date (day,    month,    year)\`. It would be worthwhile to pay attention to the fact that \`day\` is the first argument,    followed by \`month\` and then the \`year\`. This is different from the Python \`datetime\` object instantiation.
    In [2]: date = ql.Date (31,    3,    2015)
            Print (date)
    Out[2]: March 31 st,    2015
The fields of the \`Date\` object can be accessed using the \`month ()\`,    \`dayOfMonth ()\` and \`year ()\` methods. The \`weekday ()\` method can be used to fetch the day of the week.
    In [3]: print ("%d-%d-%d" %(date.Month (),    
                               Date.DayOfMonth (),   
                               Date.Year ()))
    Out[3]: 3-31-2015
    In [4]: date.Weekday () == ql. Tuesday
    Out[4]: True
The \`Date\` objects can also be used to perform arithmetic operations such as advancing by days,    weeks,    months etc. Periods such as weeks or months can be denoted using the \`Period\` class. \`Period\` object constructor signature is \`Period (num\_periods,    period\_type)\`. The \`num\_periods\` is an integer and represents the number of periods. The \`period\_type\` can be \`Weeks\`,    \`Months\` and \`Years\`.
    In [5]: type (date+1)
    Out[5]: QuantLib. QuantLib. Date
    In [6]: print ("Add a day      : {0}".Format (date + 1))
            Print ("Subtract a day : {0}".Format (date - 1))
            Print ("Add a week     : {0}".Format (date + ql.Period (1,    ql. Weeks)))
            Print ("Add a month    : {0}".Format (date + ql.Period (1,    ql. Months)))
            Print ("Add a year     : {0}".Format (date + ql.Period (1,    ql. Years)))
    Out[6]: Add a day      : April 1 st,    2015
            Subtract a day : March 30 th,    2015
            Add a week     : April 7 th,    2015
            Add a month    : April 30 th,    2015
            Add a year     : March 31 st,    2016
One can also do logical operations using the \`Date\` object.
    In [7]: print (date == ql.Date (31,    3,    2015))
            Print (date > ql.Date (30,    3,    2015))
            Print (date < ql.Date (1,    4,    2015))
            Print (date != ql.Date (1,    4,    2015))
    Out[7]: True
            True
            True
            True
The \`Date\` object is used in setting valuation dates,    issuance and expiry dates of instruments. The \`Period\` object is used in setting tenors,    such as that of coupon payments,    or in constructing payment schedules. ##### Calendar Class { #chap04 . xhtml\_leanpub-auto-calendar-class} The \`Date\` arithmetic above did not take holidays into account. But valuation of different securities would require taking into account the holidays observed in a specific exchange or country. The \`Calendar\` class implements this functionality for all the major exchanges. Let us take a look at a few examples here.
    In [8]: date = ql.Date (31,    3,    2015)
            Us_calendar = ql.UnitedStates ()
            Italy_calendar = ql.Italy ()
            Period = ql.Period (60,    ql. Days)
            Raw_date = date + period
            Us_date = us_calendar.Advance (date,    period)
            Italy_date = italy_calendar.Advance (date,    period)
            Print ("Add 60 days: {0}".Format (raw_date))
            Print ("Add 60 business days in US: {0}".Format (us_date))
            Print ("Add 60 business days in Italy: {0}".Format (italy_date))
    Out[8]: Add 60 days: May 30 th,    2015
            Add 60 business days in US: June 24 th,    2015
            Add 60 business days in Italy: June 26 th,    2015
The \`addHoliday\` and \`removeHoliday\` methods in the calendar can be used to add and remove holidays to the calendar respectively. If a calendar has any missing holidays or has a wrong holiday,    then these methods come handy in fixing the errors. The \`businessDaysBetween\` method helps find out the number of business days between two dates per a given calendar. Let us use this method on the \`us\_calendar\` and \`italy\_calendar\` as a sanity check.
    In [9]: us_busdays = us_calendar.BusinessDaysBetween (date,    us_date)
            Italy_busdays = italy_calendar.BusinessDaysBetween (date,    italy_date)
            Print ("Business days US: {0}".Format (us_busdays))
            Print ("Business days Italy: {0}".Format (italy_busdays))
    Out[9]: Business days US: 60
            Business days Italy: 60
In valuation of certain deals,    more than one calendar's holidays are observed. QuantLib has \`JointCalendar\` class that allows you to combine the holidays of two or more calendars. Let us take a look at a working example.
    In [10]: joint_calendar = ql.JointCalendar (us_calendar,    italy_calendar)
             Joint_date = joint_calendar.Advance (date,    period)
             Joint_busdays = joint_calendar.BusinessDaysBetween (date,    joint_date)
             Print ("Add 60 business days in US-Italy: {0}".Format (joint_date))
             Print ("Business days US-Italy: {0}".Format (joint_busdays))
    Out[10]: Add 60 business days in US-Italy: June 29 th,    2015
             Business days US-Italy: 60
\##### Schedule Class { #chap04 . xhtml\_leanpub-auto-schedule-class} The \`Schedule\` object is necessary in creating coupon schedules or call schedules. \`Schedule\` object constructors have the following signature:
    Schedule (const Date& effectiveDate,   
             Const Date& terminationDate,   
             Const Period& tenor,   
             Const Calendar& calendar,   
             BusinessDayConvention convention,   
             BusinessDayConvention terminationDateConvention,   
             DateGeneration:: Rule rule,   
             Bool endOfMonth,   
             Const Date& firstDate = Date (),   
             Const Date& nextToLastDate = Date ())
And
    Schedule (const std::vector<Date>&,   
             Const Calendar& calendar,   
             BusinessDayConvention rollingConvention)
    In [11]: effective_date = ql.Date (1,    1,    2015)
             Termination_date = ql.Date (1,    1,    2016)
             Tenor = ql.Period (ql. Monthly)
             Calendar = ql.UnitedStates ()
             Business_convention = ql. Following
             Termination_business_convention = ql. Following
             Date_generation = ql. DateGeneration. Forward
             End_of_month = False
             Schedule = ql.Schedule (effective_date,   
                                    Termination_date,   
                                    Tenor,   
                                    Calendar,   
                                    Business_convention,   
                                    Termination_business_convention,   
                                    Date_generation,   
                                    End_of_month)
             Pd.DataFrame ({'date': list (schedule)})
    Out[11]: 
  Date ---- --------------------- 0 January 2 nd,    2015 1 February 2 nd,    2015 2 March 2 nd,    2015 3 April 1 st,    2015 4 May 1 st,    2015 5 June 1 st,    2015 6 July 1 st,    2015 7 August 3 rd,    2015 8 September 1 st,    2015 9 October 1 st,    2015 10 November 2 nd,    2015 11 December 1 st,    2015 12 January 4 th,    2016 Here we have generated a \`Schedule\` object that will contain dates between \`effective\_date\` and \`termination\_date\` with the \`tenor\` specifying the \`Period\` to be \`Monthly\`. The \`calendar\` object is used for determining holidays. Here we have chosen the convention to be the day following holidays. That is why we see that holidays are excluded in the list of dates. The \`Schedule\` class can handle generation of dates with irregularity in schedule. The two extra parameters \`firstDate\` and \`nextToLastDate\` parameters along with a combination of forward or backward date generation rule can be used to generate short or long stub payments at the front or back end of the schedule. For example,    the following combination of \`firstDate\` and backward generation rule creates a short stub in the front on the January 15,    2015.
    In [12]: # short stub in the front
             Effective_date = ql.Date (1,    1,    2015)
             Termination_date = ql.Date (1,    1,    2016)
             First_date = ql.Date (15,    1,    2015)
             Schedule = ql.Schedule (effective_date,   
                                    Termination_date,   
                                    Tenor,   
                                    Calendar,   
                                    Business_convention,   
                                    Termination_business_convention,   
                                    Ql. DateGeneration. Backward,   
                                    End_of_month,   
                                    First_date)
             Pd.DataFrame ({'date': list (schedule)})
    Out[12]: 
  Date ---- --------------------- 0 January 2 nd,    2015 1 January 15 th,    2015 2 February 2 nd,    2015 3 March 2 nd,    2015 4 April 1 st,    2015 5 May 1 st,    2015 6 June 1 st,    2015 7 July 1 st,    2015 8 August 3 rd,    2015 9 September 1 st,    2015 10 October 1 st,    2015 11 November 2 nd,    2015 12 December 1 st,    2015 13 January 4 th,    2016 Using the \`nextToLastDate\` parameter along with the forward date generation rule creates a short stub at the back end of the schedule.
    In [13]: # short stub at the back
             Effective_date = ql.Date (1,    1,    2015)
             Termination_date = ql.Date (1,    1,    2016)
             Penultimate_date = ql.Date (15,    12,    2015)
             Schedule = ql.Schedule (effective_date,   
                                    Termination_date,   
                                    Tenor,   
                                    Calendar,   
                                    Business_convention,   
                                    Termination_business_convention,   
                                    Ql. DateGeneration. Forward,   
                                    End_of_month,   
                                    Ql.Date (),   
                                    Penultimate_date)
             Pd.DataFrame ({'date': list (schedule)})
    Out[13]: 
  Date ---- --------------------- 0 January 2 nd,    2015 1 February 2 nd,    2015 2 March 2 nd,    2015 3 April 1 st,    2015 4 May 1 st,    2015 5 June 1 st,    2015 6 July 1 st,    2015 7 August 3 rd,    2015 8 September 1 st,    2015 9 October 1 st,    2015 10 November 2 nd,    2015 11 December 1 st,    2015 12 December 15 th,    2015 13 January 4 th,    2016 Using the backward generation rule along with the \`firstDate\` allows us to create a long stub in the front. Below the first two dates are longer in duration than the rest of the dates.
    In [14]: # long stub in the front
             First_date = ql.Date (1,    2,    2015)
             Effective_date = ql.Date (15,    12,    2014)
             Termination_date = ql.Date (1,    1,    2016)
             Schedule = ql.Schedule (effective_date,   
                                    Termination_date,   
                                    Tenor,   
                                    Calendar,   
                                    Business_convention,   
                                    Termination_business_convention,   
                                    Ql. DateGeneration. Backward,   
                                    End_of_month,    
                                    First_date)
             Pd.DataFrame ({'date': list (schedule)})
    Out[14]: 
  Date ---- --------------------- 0 December 15 th,    2014 1 February 2 nd,    2015 2 March 2 nd,    2015 3 April 1 st,    2015 4 May 1 st,    2015 5 June 1 st,    2015 6 July 1 st,    2015 7 August 3 rd,    2015 8 September 1 st,    2015 9 October 1 st,    2015 10 November 2 nd,    2015 11 December 1 st,    2015 12 January 4 th,    2016 Similarly the usage of \`nextToLastDate\` parameter along with forward date generation rule can be used to generate long stub at the back of the schedule.
    In [15]: # long stub at the back
             Effective_date = ql.Date (1,    1,    2015)
             Penultimate_date = ql.Date (1,    12,    2015)
             Termination_date = ql.Date (15,    1,    2016)
             Schedule = ql.Schedule (effective_date,   
                                    Termination_date,   
                                    Tenor,   
                                    Calendar,   
                                    Business_convention,   
                                    Termination_business_convention,   
                                    Ql. DateGeneration. Forward,   
                                    End_of_month,   
                                    Ql.Date (),   
                                    Penultimate_date)
             Pd.DataFrame ({'date': list (schedule)})
    Out[15]: 
  Date ---- --------------------- 0 January 2 nd,    2015 1 February 2 nd,    2015 2 March 2 nd,    2015 3 April 1 st,    2015 4 May 1 st,    2015 5 June 1 st,    2015 6 July 1 st,    2015 7 August 3 rd,    2015 8 September 1 st,    2015 9 October 1 st,    2015 10 November 2 nd,    2015 11 December 1 st,    2015 12 January 15 th,    2016 Below the \`Schedule\` is generated from a list of dates.
    In [16]: dates = [ql.Date (2,   1,   2015),    ql.Date (2,    2,   2015),   
                      Ql.Date (2,   3,   2015),    ql.Date (1,   4,   2015),   
                      Ql.Date (1,   5,   2015),    ql.Date (1,   6,   2015),   
                      Ql.Date (1,   7,   2015),    ql.Date (3,   8,   2015),   
                      Ql.Date (1,   9,   2015),    ql.Date (1,   10,   2015),   
                      Ql.Date (2,   11,   2015),    ql.Date (1,   12,   2015),   
                      Ql.Date (4,   1,   2016)]
             Rolling_convention = ql. Following
             Schedule = ql.Schedule (dates,    calendar,   
                                    Rolling_convention)
             Pd.DataFrame ({'date': list (schedule)})
    Out[16]: 
  date ---- --------------------- 0 January 2 nd,    2015 1 February 2 nd,    2015 2 March 2 nd,    2015 3 April 1 st,    2015 4 May 1 st,    2015 5 June 1 st,    2015 6 July 1 st,    2015 7 August 3 rd,    2015 8 September 1 st,    2015 9 October 1 st,    2015 10 November 2 nd,    2015 11 December 1 st,    2015 12 January 4 th,    2016 ##### Interest Rate { #chap04 . xhtml\_leanpub-auto-interest-rate} The \`InterestRate\` class can be used to store the interest rate with the compounding type,    day count and the frequency of compounding. Below we show how to create an interest rate of 5.0% compounded annually,    using Actual/Actual day count convention.
    In [17]: annual_rate = 0.05
             Day_count = ql.ActualActual ()
             Compound_type = ql. Compounded
             Frequency = ql. Annual
             Interest_rate = ql.InterestRate (annual_rate,    
                                             Day_count,    
                                             Compound_type,    
                                             Frequency)
             Print (interest_rate)
    Out[17]: 5.000000 % Actual/Actual (ISDA) Annual compounding
Lets say if you invest a dollar at the interest rate described by \`interest\_rate\`,    the \`compoundFactor\` method in the \`InterestRate\` object gives you how much your investment will be worth after any period. Below we show that the value returned by \`compound\_factor\` for 2 years agrees with the expected compounding formula.
    In [18]: t = 2.0
             Print (interest_rate.CompoundFactor (t))
             Print ((1+annual_rate)*(1.0+annual_rate))
    Out[18]: 1.1025
             1.1025
The \`discountFactor\` method returns the reciprocal of the \`compoundFactor\` method. The discount factor is useful while calculating the present value of future cashflows.
    In [19]: print (interest_rate.DiscountFactor (t))
             Print (1.0/interest_rate.CompoundFactor (t))
    Out[19]: 0.9070294784580498
             0.9070294784580498
A given interest rate can be converted into other compounding types and compounding frequency using the \`equivalentRate\` method.
    In [20]: new_frequency = ql. Semiannual
             New_interest_rate = interest_rate.EquivalentRate (compound_type,   
                                                              New_frequency,    t)
             Print (new_interest_rate)
    Out[20]: 4.939015 % Actual/Actual (ISDA) Semiannual compounding
The discount factor for the two \`InterestRate\` objects,    \`interest\_rate\` and \`new\_interest\_rate\` are the same,    as shown below.
    In [21]: print (interest_rate.DiscountFactor (t))
             Print (new_interest_rate.DiscountFactor (t))
    Out[21]: 0.9070294784580498
             0.9070294784580495
The \`impliedRate\` method in the \`InterestRate\` class takes compound factor to return the implied rate. The \`impliedRate\` method is a static method in the \`InterestRate\` class and can be used without an instance of \`InterestRate\`. Internally the \`equivalentRate\` method invokes the \`impliedRate\` method in its calculations. ##### Conclusion { #chap04 . xhtml\_leanpub-auto-conclusion} This chapter gave an introduction to the basics of QuantLib. Here we explained the \`Date\`,    \`Schedule\`,    \`Calendar\` and \`InterestRate\` classes.
$$$${ #chap05 . xhtml}
\## $$2.$${. Section-number}Instruments and pricing engines { #chap05 . xhtml\_leanpub-auto-instruments-and-pricing-engines} In this notebook,    I'll show how instruments and their available engines can monitor changes in their input data. ##### Setup { #chap05 . xhtml\_leanpub-auto-setup} To begin,    we import the QuantLib module and set up the global evaluation date.
    In [1]: import QuantLib as ql
    In [2]: today = ql.Date (7,    ql. March,    2014)
            Ql.Settings.Instance (). EvaluationDate = today
\##### The instrument { #chap05 . xhtml\_leanpub-auto-the-instrument} As a sample instrument,    we'll take a textbook example: a European option. Building the option requires only the specification of its contract,    so its payoff (it's a call option with strike at 100) and its exercise,    three months from today's date. Market data will be selected and passed later,    depending on the calculation methods.
    In [3]: option = ql.EuropeanOption (ql.PlainVanillaPayoff (ql. Option. Call,    100.0),   
                                       Ql.EuropeanExercise (ql.Date (7,    ql. June,    2014)))
\##### First pricing method: analytic Black-Scholes formula { #chap05 . xhtml\_leanpub-auto-first-pricing-method-analytic-black-scholes-formula} The different pricing methods are implemented as pricing engines holding the required market data. The first we'll use is the one encapsulating the analytic Black-Scholes formula. First,    we collect the quoted market data. We'll assume flat risk-free rate and volatility,    so they can be expressed by \`SimpleQuote\` instances: those model numbers whose value can change and that can notify observers when this happens. The underlying value is at 100,    the risk-free value at 1%,    and the volatility at 20%.
    In [4]: u = ql.SimpleQuote (100.0)
            R = ql.SimpleQuote (0.01)
            Sigma = ql.SimpleQuote (0.20)
In order to build the engine,    the market data are encapsulated in a Black-Scholes process object. First we build flat curves for the risk-free rate and the volatility...
    In [5]: riskFreeCurve = ql.FlatForward (0,    ql.TARGET (),   
                                           Ql.QuoteHandle (r),    ql. Actual 360 ())
            Volatility = ql.BlackConstantVol (0,    ql.TARGET (),   
                                             Ql.QuoteHandle (sigma),    ql. Actual 360 ())
... Then we instantiate the process with the underlying value and the curves we just built. The inputs are all stored into handles,    so that we could change the quotes and curves used if we wanted. I'll skip over this for the time being.
    In [6]: process = ql.BlackScholesProcess (ql.QuoteHandle (u),   
                                             Ql.YieldTermStructureHandle (riskFreeCurve),   
                                             Ql.BlackVolTermStructureHandle (volatility))
Once we have the process,    we can finally use it to build the engine...
    In [7]: engine = ql.AnalyticEuropeanEngine (process)
... And once we have the engine,    we can set it to the option and evaluate the latter.
    In [8]: option.SetPricingEngine (engine)
    In [9]: print (option.NPV ())
    Out[9]: 4.155543462156206
Depending on the instrument and the engine,    we can also ask for other results; in this case,    we can ask for Greeks.
    In [10]: print (option.Delta ())
             Print (option.Gamma ())
             Print (option.Vega ())
    Out[10]: 0.5302223303784392
             0.03934493301271913
             20.109632428723106
\##### Market changes { #chap05 . xhtml\_leanpub-auto-market-changes} As I mentioned,    market data are stored in \`Quote\` instances and thus can notify the option when any of them changes. We don't have to do anything explicitly to tell the option to recalculate: once we set a new value to the underlying,    we can simply ask the option for its NPV again and we'll get the updated value.
    In [11]: u.setValue (105.0)
             Print (option.NPV ())
    Out[11]: 7.27556357927846
Just for showing off,    we can use this to graph the option value depending on the underlying asset value. After a bit of graphic setup (don't pay attention to the man behind the curtains)...
    In [12]: %matplotlib inline
             Import numpy as np
             From IPython. Display import display
             Import utils
... We can take an array of values from 80 to 120,    set the underlying value to each of them,    collect the corresponding option values,    and plot the results.
    In [13]: f,    ax = utils.Plot ()
             Xs = np.Linspace (80.0,    120.0,    400)
             Ys = []
             For x in xs:
                 u.setValue (x)
                 Ys.Append (option.NPV ())
             Ax. Set_title ('Option value')
             Utils. Highlight_x_axis (ax)
             Ax.Plot (xs,    ys);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/instruments_and_pricing_engines-13.png)
::: Other market data also affect the value,    of course.
    In [14]: u.setValue (105.0)
             r.setValue (0.01)
             Sigma.SetValue (0.20)
    In [15]: print (option.NPV ())
    Out[15]: 7.27556357927846
We can see it when we change the risk-free rate...
    In [16]: r.setValue (0.03)
    In [17]: print (option.NPV ())
    Out[17]: 7.624029148527754
... Or the volatility.
    In [18]: sigma.SetValue (0.25)
    In [19]: print (option.NPV ())
    Out[19]: 8.531296969971573
\##### Date changes { #chap05 . xhtml\_leanpub-auto-date-changes} Just as it does when inputs are modified,    the value also changes if we advance the evaluation date. Let's look first at the value of the option when its underlying is worth 105 and there's still three months to exercise...
    In [20]: u.setValue (105.0)
             r.setValue (0.01)
             Sigma.SetValue (0.20)
             Print (option.NPV ())
    Out[20]: 7.27556357927846
... And then move to a date two months before exercise.
    In [21]: ql.Settings.Instance (). EvaluationDate = ql.Date (7,    ql. April,    2014)
Again,    we don't have to do anything explicitly: we just ask the option its value,    and as expected it has decreased,    as can also be seen by updating the plot.
    In [22]: print (option.NPV ())
    Out[22]: 6.560073820974377
    In [23]: ys = []
             For x in xs:
                 u.setValue (x)
                 Ys.Append (option.NPV ())
             Ax.Plot (xs,    ys,    '--')
             Display (f)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/instruments_and_pricing_engines-23.png)
::: In the default library configuration,    the returned value goes down to 0 when we reach the exercise date.
    In [24]: ql.Settings.Instance (). EvaluationDate = ql.Date (7,    ql. June,    2014)
    In [25]: print (option.NPV ())
    Out[25]: 0.0
\##### Other pricing methods { #chap05 . xhtml\_leanpub-auto-other-pricing-methods} The pricing-engine mechanism allows us to use different pricing methods. For comparison,    I'll first set the input data back to what they were previously and output the Black-Scholes price.
    In [26]: ql.Settings.Instance (). EvaluationDate = today
             u.setValue (105.0)
             r.setValue (0.01)
             Sigma.SetValue (0.20)
    In [27]: print (option.NPV ())
    Out[27]: 7.27556357927846
Let's say that we want to use a Heston model to price the option. What we have to do is to instantiate the corresponding class with the desired inputs...
    In [28]: model = ql.HestonModel (
                 Ql.HestonProcess (
                     Ql.YieldTermStructureHandle (riskFreeCurve),   
                     Ql.YieldTermStructureHandle (ql.FlatForward (0,    ql.TARGET (),   
                                                                0.0,    ql. Actual 360 ())),   
                     Ql.QuoteHandle (u),   
                     0.04,    0.1,    0.01,    0.05,    -0.75))
... Pass it to the corresponding engine,    and set the new engine to the option.
    In [29]: engine = ql.AnalyticHestonEngine (model)
             Option.SetPricingEngine (engine)
Asking the option for its NPV will now return the value according to the new model.
    In [30]: print (option.NPV ())
    Out[30]: 7.295356086978629
\##### Lazy recalculation { #chap05 . xhtml\_leanpub-auto-lazy-recalculation} One last thing. Up to now,    we haven't really seen evidence of notifications going around. After all,    the instrument might just have recalculated its value every time,    regardless of notifications. What I'm going to show,    instead,    is that the option doesn't just recalculate every time anything changes; it also avoids recalculations when nothing has changed. We'll switch to a Monte Carlo engine,    which takes a few seconds to run the required simulation.
    In [31]: engine = ql.MCEuropeanEngine (process,    "PseudoRandom",   
                                          TimeSteps=20,   
                                          RequiredSamples=250000)
             Option.SetPricingEngine (engine)
When we ask for the option value,    we have to wait for the calculation to finish...
    In [32]: %time print (option.NPV ())
    Out[32]: 7.2805592569497755
             CPU times: user 1.85 s,    sys: 0 ns,    total: 1.85 s
             Wall time: 1.83 s
... But a second call to the \`NPV\` method will be instantaneous when made before anything changes. In this case,    the option didn't calculate its value; it just returned the result that it cached from the previous call.
    In [33]: %time print (option.NPV ())
    Out[33]: 7.2805592569497755
             CPU times: user 0 ns,    sys: 0 ns,    total: 0 ns
             Wall time: 1.38 ms
If we change anything (e.g.,    the underlying value)...
    In [34]: u.setValue (104.0)
... The option is notified of the change,    and the next call to \`NPV\` will again take a while.
    In [35]: %time print (option.NPV ())
    Out[35]: 6.582898868982841
             CPU times: user 1.78 s,    sys: 0 ns,    total: 1.78 s
             Wall time: 1.77 s
$$$${ #chap06 . xhtml}
\## $$3.$${. Section-number}Numerical Greeks calculation { #chap06 . xhtml\_leanpub-auto-numerical-greeks-calculation} In this notebook,    I'll build on the facilities provided by the \`Instrument\` class (that is,    its ability to detect changes in its inputs and recalculate accordingly) to show how to calculate numerical Greeks when the engine doesn't provide them. ##### Setup { #chap06 . xhtml\_leanpub-auto-setup-1} As usual,    we import the QuantLib module and set the evaluation date:
    In [1]: import QuantLib as ql
    In [2]: today = ql.Date (8,    ql. October,    2014)
            Ql.Settings.Instance (). EvaluationDate = today
\##### A somewhat exotic option { #chap06 . xhtml\_leanpub-auto-a-somewhat-exotic-option} As an example,    we'll use a knock-in barrier option:
    In [3]: option = ql.BarrierOption (ql. Barrier. UpIn,   
                                      120.0,      # barrier
                                      0.0,        # rebate
                                      Ql.PlainVanillaPayoff (ql. Option. Call,    100.0),   
                                      Ql.EuropeanExercise (ql.Date (8,    ql. January,    2015)))
For the purpose of this example,    the market data are the underlying value,    the risk-free rate and the volatility. We wrap them in quotes,    so that the instrument will be notified of any changes...
    In [4]: u = ql.SimpleQuote (100.0)
            R = ql.SimpleQuote (0.01)
            Sigma = ql.SimpleQuote (0.20)
... And from the quotes we build the flat curves and the process that the engine requires. As explained in a later notebook,    we build the term structures so that they move with the evaluation date; this will be useful further on.
    In [5]: riskFreeCurve = ql.FlatForward (0,    ql.TARGET (),   
                                           Ql.QuoteHandle (r),    ql. Actual 360 ())
            Volatility = ql.BlackConstantVol (0,    ql.TARGET (),   
                                             Ql.QuoteHandle (sigma),    ql. Actual 360 ())
    In [6]: process = ql.BlackScholesProcess (ql.QuoteHandle (u),   
                                             Ql.YieldTermStructureHandle (riskFreeCurve),   
                                             Ql.BlackVolTermStructureHandle (volatility))
Finally,    we build the engine (the library provides one based on an analytic formula) and set it to the option.
    In [7]: option.SetPricingEngine (ql.AnalyticBarrierEngine (process))
Now we can ask the option for its value...
    In [8]: print (option.NPV ())
    Out[8]: 1.3657980739109867
... But we're not so lucky when it comes to Greeks:
    In [9]: print (option.Delta ())
    Out[9]: ---------------------------------------------------------------------------
            RuntimeError                              Traceback (most recent call last)
            <ipython-input-9-dcaa26b2b456> in <module>
            ----> 1 print (option.Delta ())
            /usr/local/lib/python 3.6/dist-packages/QuantLib/QuantLib. Py in delta (self)
              12437 
              12438     def delta (self):
            > 12439         return _QuantLib. BarrierOption_delta (self)
              12440 
              12441     def gamma (self):
            RuntimeError: delta not provided
The engine doesn't provide the delta,    so asking for it raises an error. ##### Numerical calculation { #chap06 . xhtml\_leanpub-auto-numerical-calculation} What does a quant have to do? We can use numerical differentiation to approximate the Greeks,    as shown in the next figure: that is,    we can approximate the derivative by calculating the option value for two slightly different values of the underlying and by taking the slope between the resulting points. ::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/numerical_greeks_calculation.png)
::: The relevant formulas are: !$$\\\\Delta = \\\\frac{P (u\_0+h)-P (u\_0-h)}{2 h} \\\\; \\\\; \\\\; \\\\; \\\\; \\\\; \\\\Gamma = \\\\frac{P (u\_0+h)-2 P (u\_0)+P (u\_0-h)}{h\\^2}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_0. Png){. Block-equation width="553"} where !$$P (u)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_1. Png){. Inline-equation width="36"} is the price of the option for a given value of the underlying !$$u$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_2. Png){. Inline-equation width="9"}. Thanks to the framework we set in place,    getting the perturbed prices is easy enough. We just have to set the relevant quote to the new value and ask the option for its price again. Thus,    we choose a small increment and start. First,    we save the current value of the option...
    In [10]: u 0 = u.value () ; h = 0.01
    In [11]: P 0 = option.NPV () ; print (P 0)
    Out[11]: 1.3657980739109867
... Then we increase the underlying value and get the new option value...
    In [12]: u.setValue (u 0+h)
             P_plus = option.NPV () ; print (P_plus)
    Out[12]: 1.3688112201958083
... Then we do the same after decreasing the underlying value.
    In [13]: u.setValue (u 0-h)
             P_minus = option.NPV () ; print (P_minus)
    Out[13]: 1.3627900998610207
Finally,    we set the underlying value back to its current value.
    In [14]: u.setValue (u 0)
Applying the formulas above give us the desired Greeks:
    In [15]: Delta = (P_plus - P_minus)/(2*h)
             Gamma = (P_plus - 2*P 0 + P_minus)/(h*h)
             Print (Delta)
             Print (Gamma)
    Out[15]: 0.3010560167393761
             0.05172234855521651
The approach is usable for any Greek. We can use the two-sided formula above,    or the one-sided formula below if we want to minimize the number of evaluations: !$$\\\\frac{\\\\partial P}{\\\\partial x} = \\\\frac{P (x\_0+h)-P (x\_0)}{h}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_3. Png){. Block-equation width="202"} For instance,    here we calculate Rho and Vega:
    In [16]: r 0 = r.value () ; h = 0.0001
             r.setValue (r 0+h) ; P_plus = option.NPV ()
             r.setValue (r 0)
             Rho = (P_plus - P 0)/h ; print (Rho)
    Out[16]: 6.531038494277386
    In [17]: sigma 0 = sigma.Value () ; h = 0.0001
             Sigma.SetValue (sigma 0+h) ; P_plus = option.NPV ()
             Sigma.SetValue (sigma 0)
             Vega = (P_plus - P 0)/h ; print (Vega)
    Out[17]: 26.52519924198904
The approach for the Theta is a bit different,    although it still relies on the fact that the option reacts to the change in the market data. The problem is that we don't have the time to maturity available as a quote,    as was the case for the other quantities. Instead,    since we set up the term structures so that they move with the evaluation date,    we just have to set it to tomorrow's date to get the corresponding option value:
    In [18]: ql.Settings.Instance (). EvaluationDate = today+1
             P 1 = option.NPV ()
             H = 1.0/365
             Theta = (P 1-P 0)/h ; print (Theta)
    Out[18]: -10.770888399441302
$$$${ #chap07 . xhtml}
\## $$4.$${. Section-number}Market quotes { #chap07 . xhtml\_leanpub-auto-market-quotes} In this notebook,    I'll show a pitfall to avoid when multiple quotes need to be updated.
    In [1]: %matplotlib inline
            Import numpy as np
            Import utils
    In [2]: import QuantLib as ql
    In [3]: today = ql.Date (17,    ql. October,    2016)
            Ql.Settings.Instance (). EvaluationDate = today
\##### Setting the stage { #chap07 . xhtml\_leanpub-auto-setting-the-stage} For illustration purposes,    I'll create a bond curve using the same data and algorithm shown in one of the QuantLib C++ examples; namely,    I'll give to the curve the functional form defined by the Nelson-Siegel model and I'll fit it to a number of bond. Here are the maturities in years and the coupons of the bonds I'll use:
    In [4]: data = [ (2,    0.02),     (4,    0.0225),     (6,    0.025),     (8,    0.0275),   
                    (10,    0.03),    (12,    0.0325),    (14,    0.035),    (16,    0.0375),   
                    (18,    0.04),    (20,    0.0425),    (22,    0.045),    (24,    0.0475),   
                    (26,    0.05),    (28,    0.0525),    (30,    0.055)]
For simplicity,    I'll use the same start date,    frequency and conventions for all the bonds; this doesn't affect the point I'm going to make in the rest of the notebook. I'll also assume that all bonds currently price at 100. I'll skip over the details of building the curve now; the one thing you'll need to remember is that it depends on the quotes modeling the bond prices.
    In [5]: calendar = ql.TARGET ()
            Settlement = calendar.Advance (today,    3,    ql. Days)
            Quotes = []
            Helpers = []
            For length,    coupon in data:
                Maturity = calendar.Advance (settlement,    length,    ql. Years)
                Schedule = ql.Schedule (
                    Settlement,    maturity,    ql.Period (ql. Annual),   
                    Calendar,    ql. ModifiedFollowing,    ql. ModifiedFollowing,   
                    Ql. DateGeneration. Backward,    False)
                Quote = ql.SimpleQuote (100.0)
                Quotes.Append (quote)
                Helpers.Append (
                    Ql.FixedRateBondHelper (ql.QuoteHandle (quote),    3,    100.0,   
                                           Schedule,    [coupon],    ql.SimpleDayCounter (),   
                                           Ql. ModifiedFollowing))
            Curve = ql.FittedBondDiscountCurve (0,    calendar,    helpers,   
                                               Ql.SimpleDayCounter (),   
                                               Ql.NelsonSiegelFitting ())
Here is a visualization of the curve as discount factors versus time in years:
    In [6]: sample_times = np.Linspace (0.0,    30.0,    301)
            Sample_discounts = [ curve.Discount (t) for t in sample_times ]
            F,    ax = utils.Plot ()
            Ax. Set_ylim (0.0,    1.0)
            Ax.Plot (sample_times,    sample_discounts);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/market_quotes-6.png)
::: Also,    here's a bond priced by discounting its coupons on the curve:
    In [7]: schedule = ql.Schedule (today,    calendar.Advance (today,    15,    ql. Years),   
                                   Ql.Period (ql. Semiannual),    calendar,   
                                   Ql. ModifiedFollowing,    ql. ModifiedFollowing,   
                                   Ql. DateGeneration. Backward,    False)
            Bond = ql.FixedRateBond (3,    100.0,    schedule,    [0.04],    ql. Actual 360 ())
            Bond.SetPricingEngine (
                Ql.DiscountingBondEngine (ql.YieldTermStructureHandle (curve)))
            Print (bond.CleanPrice ())
    Out[7]: 105.77449628297312
\##### "It looked like a good idea at the time" { #chap07 . xhtml\_leanpub-auto-it-looked-like-a-good-idea-at-the-time} Now,    let's add an observer that checks whether the bond is out of date,    and if so recalculates the bond and outputs its new price. In Python,    I can do this by defining a function to be triggered by the notifications,    by passing it to the observer I'm creating,    and (this last step is as in C++) by registering the observer with the bond. As a reminder of how the whole thing works: the changes will come from the market quotes,    but the observer doesn't need to be concerned with that and only registers with the object it's ultimately interested in; in this case,    the bond whose price it wants to monitor. A change in any of the market quotes will cause the quote to notify the helper,    which in turn will notify the curve,    and so on to the pricing engine,    the bond and finally our observer.
    In [8]: prices = []
            Def print_price ():
                P = bond.CleanPrice ()
                Prices.Append (p)
                Print (p)
            O = ql.Observer (print_price)
            o.registerWith (bond)
The function also appends the new price to a list that can be used later as a history of the prices. Let's see if it works:
    In [9]: quotes[2]. SetValue (101.0)
    Out[9]: 105.77449628297312
            105.8656042875337
Whoa,    what was that? The function was called twice,    which surprised me too when I wrote this notebook. It turns out that,    due to a glitch of multiple inheritance,    the curve sends two notifications to the instrument. After the first,    the instrument recalculates but the curve doesn't (which explains why the price doesn't change); after the second,    the curve updates and the price changes. This should be fixed in a future release,    but again it doesn't change the point of the notebook. Let's set the quote back to its original value.
    In [10]: quotes[2]. SetValue (100.0)
    Out[10]: 105.8656042875337
             105.77449634664224
Now,    let's say the market moves up and,    accordingly,    all the bonds prices increase to 101. Therefore,    we need to update all the quotes.
    In [11]: prices = []
             For q in quotes:
                 q.setValue (101.0)
    Out[11]: 105.77449634664224
             105.28388426272507
             105.28388426272507
             105.2186288679219
             105.2186288679219
             105.3195906444377
             105.3195906444377
             105.4878663448759
             105.4878663448759
             105.68032070200927
             105.68032070200927
             105.87580370787278
             105.87580370787278
             106.06201680440225
             106.06201680440225
             106.23044624497663
             106.23044624497663
             106.37409230798896
             106.37409230798896
             106.48708840758337
             106.48708840758337
             106.56505206364592
             106.56505206364592
             106.60570726105742
             106.60570726105742
             106.60980187075381
             106.60980187075381
             106.58011186582736
             106.58011186582736
             106.52070699740128
As you see,    each of the updates sent a notification and thus triggered a recalculation. We can use the list of prices we collected (slicing it to skip duplicate values) to visualize how the price changed.
    In [12]: unique_prices = prices[:: 2]+prices[-1::]
             _,    ax = utils.Plot ()
             Ax.Plot (unique_prices,    '-');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/market_quotes-12.png)
::: The first price is the original one,    and the last price is the final one; but all those in between are calculated based on an incomplete set of changes in which some quotes were updated and some others weren't. Those are all incorrect,    and (since they went both above and below the range of the real prices) outright dangerous in case there were any triggers on price levels that could have fired. Clearly,    this is not the kind of behavior we want our code to have. ##### Alternatives? { #chap07 . xhtml\_leanpub-auto-alternatives} There are workarounds we can apply. For instance,    it's possible to freeze the bond temporarily,    preventing it from forwarding notifications.
    In [13]: bond.Freeze ()
Now,    notifications won't be forwarded by the bond and thus won't reach our observer. In fact,    the following loop won't print anything.
    In [14]: for q in quotes:
                 q.setValue (101.5)
When we restore the bond,    it sends a single notification,    which triggers only one recalculation and gives the correct final price.
    In [15]: bond.Unfreeze ()
    Out[15]: 106.85839373944943
When using C++,    it's also possible to disable and re-enable notifications globally,    which makes it more convenient. But it all feels a bit convoluted anyway. The whole thing will be simpler if we discard the initial idea and don't force a recalculation for each notification. ##### Pull,    don't push { #chap07 . xhtml\_leanpub-auto-pull-dont-push} It's preferable for updates to \*not\* trigger recalculation and just set some kind of dirty flag,    just like the instruments in the library do. This way,    you can control when the calculation occur. To do so,    let's remove the observer we have in place...
    In [16]: del o
... And instead create one that raises a flag when it's notified.
    In [17]: flag = {}
             Flag['status'] = 'down'
             Def set_flag ():
                 Flag['status'] = 'up'
             O = ql.Observer (set_flag)
             o.registerWith (bond)
The flag is initially down...
    In [18]: print (flag)
    Out[18]: {'status': 'down'}
... And quote changes cause it to be raised.
    In [19]: for q in quotes:
                 q.setValue (100.0)
    In [20]: print (flag)
    Out[20]: {'status': 'up'}
At this point,    we can ask the bond for its final price.
    In [21]: bond.CleanPrice ()
    Out[21]: 105.77449635334463
Better yet,    we can let the instrument do that: let's remove the second observer,    too,    and just ask the instrument for its price after the changes. The instrument keeps track of whether it needs recalculation,    so it doesn't need us to keep track of it.
    In [22]: del o
    In [23]: for q in quotes:
                 q.setValue (101.0)
    In [24]: bond.CleanPrice ()
    Out[24]: 106.52070687248381
So,    less is more? In this case,    it seems so.
$$$${ #chap08 . xhtml}
\## $$5.$${. Section-number}Term structures and their reference dates { #chap08 . xhtml\_leanpub-auto-term-structures-and-their-reference-dates} In this notebook,    I show briefly how to set up term structures so that they track (or don't track) the global evaluation date. ##### Setup { #chap08 . xhtml\_leanpub-auto-setup-2} Import the QuantLib module and set up the global evaluation date. You might want to take note of the date,    since we'll be moving it around later on.
    In [1]: import QuantLib as ql
    In [2]: ql.Settings.Instance (). EvaluationDate = ql.Date (3,    ql. October,    2014)
\##### Specifying the reference date of a term structure { #chap08 . xhtml\_leanpub-auto-specifying-the-reference-date-of-a-term-structure} In not-too-accurate terms,    the reference date of a term structure is where it begins. It can be the evaluation date,    but you might also want it to start on the spot date,    for instance. We have two possibilities to define a reference date for a curve---even though some particular classes only allow one of them. The first is to define it by means of a (possibly null) offset from the current evaluation date; e.g.,    "two business days after the evaluation date" to define it as the spot date,    or "no business days" to define it as the evaluation date itself. I'll do it here by building a sample curve over a few swaps. Never mind the helper object that I'm building here...
    In [3]: helpers = [ ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100.0)),   
                                          Ql.Period (*tenor),    ql.TARGET (),   
                                          Ql. Annual,    ql. Unadjusted,    
                                          Ql. Thirty 360 (),    
                                          Ql. Euribor 6 M ())
                        For tenor,    rate in [((2,    ql. Years),    0.201),   
                                            ((3,    ql. Years),    0.258),   
                                            ((5,    ql. Years),    0.464),   
                                            ((10,    ql. Years),    1.151),   
                                            ((15,    ql. Years),    1.588)] ]
... Because the construction of the curve is the main point: note the \`0\` and \`TARGET ()\` arguments,    specifying the number of days and the calendar used to determine business days.
    In [4]: curve 1 = ql.PiecewiseFlatForward (0,    ql.TARGET (),    helpers,    ql. Actual 360 ())
The second possibility is to specify the reference date explicitly. For instance,    the \`ForwardCurve\` class takes a vector of specific dates and the corresponding rates and interpolates between them; the first passed date is taken as the reference date of the curve. For comparison purposes,    I'll ask the curve above for its nodes and use them to build a \`ForwardCurve\` instance:
    In [5]: dates,    rates = zip (*curve 1.Nodes ())
    In [6]: curve 1.Nodes ()
    Out[6]: ((Date (3,   10,   2014),    0.0019777694879293093),   
             (Date (7,   10,   2016),    0.0019777694879293093),   
             (Date (9,   10,   2017),    0.0036475517704509294),   
             (Date (7,   10,   2019),    0.007660760701876805),   
             (Date (7,   10,   2024),    0.018414773669420893),   
             (Date (8,   10,   2029),    0.025311634328221498))
The curve built based on these data will be the same as the first,    except that we're specifying its reference date explicitly as October 3 rd (the first passed date).
    In [7]: curve 2 = ql.ForwardCurve (dates,    rates,    ql. Actual 360 ())
Both curves are defined over the same range of dates...
    In [8]: print ("{0} to {1}".Format (curve 1.ReferenceDate (),    curve 1.MaxDate ()))
            Print ("{0} to {1}".Format (curve 2.ReferenceDate (),    curve 2.MaxDate ()))
    Out[8]: October 3 rd,    2014 to October 8 th,    2029
            October 3 rd,    2014 to October 8 th,    2029
... And return the same rates,    whether we ask for a given time (for instance,    5 years)...
    In [9]: print (curve 1.ZeroRate (5.0,    ql. Continuous))
            Print (curve 2.ZeroRate (5.0,    ql. Continuous))
    Out[9]: 0.452196 % Actual/360 continuous compounding
            0.452196 % Actual/360 continuous compounding
... Or for a given date.
    In [10]: print (curve 1.ZeroRate (ql.Date (7,    ql. September,    2019),   
                                   Ql. Actual 360 (),    ql. Continuous))
             Print (curve 2.ZeroRate (ql.Date (7,    ql. September,    2019),   
                                   Ql. Actual 360 (),    ql. Continuous))
    Out[10]: 0.452196 % Actual/360 continuous compounding
             0.452196 % Actual/360 continuous compounding
With the help of a couple more Python modules,    we can also plot the whole curve by asking for rates over a set of times:
    In [11]: %matplotlib inline
             Import utils
             From matplotlib. Ticker import FuncFormatter
             Import numpy as np
    In [12]: times = np.Linspace (0.0,    15.0,    400)
             Rates = [ curve 1.ZeroRate (t,    ql. Continuous). Rate () for t in times ]
             _,    ax = utils.Plot ()
             Ax. Yaxis. Set_major_formatter (
                 FuncFormatter (lambda r,    pos: utils. Format_rate (r,    2)))
             Ax.Plot (times,    rates);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/term_structures-12.png)
::: ##### Moving the evaluation date { #chap08 . xhtml\_leanpub-auto-moving-the-evaluation-date} To recap: we built the first curve specifying its reference date relative to the evaluation date,    and the second curve specifying its reference date explicitly. Now,    what happens if we change the evaluation date?
    In [13]: ql.Settings.Instance (). EvaluationDate = ql.Date (19,    ql. September,    2014)
As you might expect,    the reference date of the first curve changes accordingly while that of the second curve doesn't. We can see how the range of definition has now changed for the first curve,    but not for the second:
    In [14]: print ("{0} to {1}".Format (curve 1.ReferenceDate (),    curve 1.MaxDate ()))
             Print ("{0} to {1}".Format (curve 2.ReferenceDate (),    curve 2.MaxDate ()))
    Out[14]: September 19 th,    2014 to September 24 th,    2029
             October 3 rd,    2014 to October 8 th,    2029
And of course the rates have changed,    too...
    In [15]: print (curve 1.ZeroRate (5.0,    ql. Continuous))
             Print (curve 2.ZeroRate (5.0,    ql. Continuous))
    Out[15]: 0.452196 % Actual/360 continuous compounding
             0.452196 % Actual/360 continuous compounding
... If we look at them in the right way. The whole curve has moved back a couple of weeks,    so if we ask for a given time we'll get the same rates; in other words,    we're asking for the zero rate over five years after the reference date,    and that remains the same for a rigid translation of the curve. If we ask for the zero rate at a given date,    though,    we'll see the effect:
    In [16]: print (curve 1.ZeroRate (ql.Date (7,    ql. September,    2019),   
                                   Ql. Actual 360 (),    ql. Continuous))
             Print (curve 2.ZeroRate (ql.Date (7,    ql. September,    2019),   
                                   Ql. Actual 360 (),    ql. Continuous))
    Out[16]: 0.454618 % Actual/360 continuous compounding
             0.452196 % Actual/360 continuous compounding
\##### Notifications { #chap08 . xhtml\_leanpub-auto-notifications} Finally,    we can see how the two curves behave differently also with respect to notifications. Let's make two observers...
    In [17]: def make_observer (i):
                 Def say ():
                     S = "Observer %d notified" % i
                     Print ('-'*len (s))
                     Print (s)
                     Print ('-'*len (s))
                 Return ql.Observer (say)
             Obs 1 = make_observer (1)
             Obs 2 = make_observer (2)
... And check that they work correctly by connecting them to a few quotes. The first observer will receive notifications from the first and third quote,    and the second observer will receive notifications from the second and third quote.
    In [18]: q 1 = ql.SimpleQuote (1.0)
             Obs 1.RegisterWith (q 1)
             Q 2 = ql.SimpleQuote (2.0)
             Obs 2.RegisterWith (q 2)
             Q 3 = ql.SimpleQuote (3.0)
             Obs 1.RegisterWith (q 3)
             Obs 2.RegisterWith (q 3)
If I trigger a change in the first quote,    the first observer is notified and outputs a message:
    In [19]: q 1.SetValue (1.5)
    Out[19]: -------------------
             Observer 1 notified
             -------------------
A change in the second quote causes a message from the second observer...
    In [20]: q 2.SetValue (1.9)
    Out[20]: -------------------
             Observer 2 notified
             -------------------
... And a change in the third quote causes both observers to react.
    In [21]: q 3.SetValue (3.1)
    Out[21]: -------------------
             Observer 2 notified
             -------------------
             -------------------
             Observer 1 notified
             -------------------
Now let's connect the observers to the curves. The first observer will receive notifications from the curve that moves with the evaluation date,    and the second observer will receive notifications from the curve that doesn't move.
    In [22]: obs 1.RegisterWith (curve 1)
             Obs 2.RegisterWith (curve 2)
Now we can see what happens when the evaluation date changes again:
    In [23]: ql.Settings.Instance (). EvaluationDate = ql.Date (23,    ql. September,    2014)
    Out[23]: -------------------
             Observer 1 notified
             -------------------
As you can see,    only the moving curve sent a notification. The other did not,    since it was not modified by the change of evaluation date.
$$$${ #chap09 . xhtml}
\## $$6.$${. Section-number}Pricing over a range of days { #chap09 . xhtml\_leanpub-auto-pricing-over-a-range-of-days} Based on questions on \*Stack Exchange\* from $$Charles$$( https://stackoverflow.com/questions/32869325/ ),    $$bob. Jonst$$( https://quant.stackexchange.com/questions/35961/ ),    $$MCM$$( https://quant.stackexchange.com/questions/38509 ) and $$lcheng$$( https://quant.stackexchange.com/questions/36830/ ).
    In [1]: import QuantLib as ql
            Import numpy as np
            Np.Random.Seed (42)
Let's say we have an instrument (a fixed-rate bond,    for instance) that we want to price on a number of dates. I assume we also have the market quotes,    or the curves,    corresponding to each of the dates; in this case we only need interest rates,    but the library works the same way for any quotes. We'll store the resulting prices in a dictionary,    with the date as the key.
    In [2]: prices = {}
\##### Producing a single price { #chap09 . xhtml\_leanpub-auto-producing-a-single-price} To price the bond on a single date,    we create the instrument itself...
    In [3]: start_date = ql.Date (8,    ql. February,    2016)
            Maturity_date = start_date + ql.Period (5,    ql. Years)
            Schedule = ql.Schedule (start_date,    maturity_date,   
                                   Ql.Period (ql. Semiannual),    ql.TARGET (),   
                                   Ql. Following,    ql. Following,   
                                   Ql. DateGeneration. Backward,    False)
            Coupons = [0.01]*10
            Bond = ql.FixedRateBond (3,    100,    schedule,    coupons,    ql. Thirty 360 ())
... And the required discount curve. For brevity,    here I'm interpolating precomputed rates; I might as well bootstrap the curve on a set of market rates.
    In [4]: today = ql.Date (9,    ql. May,    2018)
            Nodes = [ today + ql.Period (i,    ql. Years) for i in range (11) ]
            Rates = [ 0.007,    0.010,    0.012,    0.013,    0.014,   
                      0.016,    0.017,    0.018,    0.020,    0.021,    0.022 ]
            Discount_curve = ql.ZeroCurve (nodes,    rates,    ql. Actual 360 ())
Given the bond and the curve,    we link them together through an engine,    set the evaluation date and get the result.
    In [5]: discount_handle = ql.RelinkableYieldTermStructureHandle (discount_curve)
            Bond.SetPricingEngine (ql.DiscountingBondEngine (discount_handle))
    In [6]: ql.Settings.Instance (). EvaluationDate = today
    In [7]: prices[today] = bond.CleanPrice ()
            Print (prices[today])
    Out[7]: 99.18942082987543
\##### Pricing on multiple days { #chap09 . xhtml\_leanpub-auto-pricing-on-multiple-days} We could repeat the above for all dates,    but it goes against the grain of the library. The architecture (see chapter 2 of $$Implementing QuantLib$$( https://leanpub.com/implementingquantlib ) for details) was designed so that the instrument can react to changing market conditions; therefore,    we can avoid recreating the instrument. We'll only change the discount curve and the evaluation date. For instance,    here I'll calculate the price for the business day before today:
    In [8]: calendar = ql.TARGET ()
            Yesterday = calendar.Advance (today,    -1,    ql. Days)
I'll generate random rates to avoid coming up with a new set; but the idea is to build the correct discount curve for the evaluation date.
    In [9]: nodes = [ yesterday + ql.Period (i,    ql. Years) for i in range (11) ]
            Base_rates = np.Array (rates)
            Rates = base_rates * np.Random.Normal (loc=1.0,    scale=0.005,   
                                                  Size=base_rates. Shape)
            Discount_curve = ql.ZeroCurve (nodes,    list (rates),    ql. Actual 360 ())
As I mentioned,    I need to set the new evaluation date and to link the handle in the engine to the new discount curve...
    In [10]: ql.Settings.Instance (). EvaluationDate = yesterday
             Discount_handle.LinkTo (discount_curve)
... After which the bond returns the updated price.
    In [11]: prices[yesterday] = bond.CleanPrice ()
             Print (prices[yesterday])
    Out[11]: 99.16663635835845
By repeating the process,    I can generate prices for,    say,    the whole of last year. Again,    I'm generating random rates to avoid tedious listings or external data files; you'll use the correct ones instead.
    In [12]: first_date = calendar.Advance (today,    -1,    ql. Years)
             Date = calendar.Advance (yesterday,    -1,    ql. Days)
             While date >= first_date:
                 Nodes = [ date + ql.Period (i,    ql. Years) for i in range (11) ]
                 Rates = base_rates * np.Random.Normal (loc=1.0,    scale=0.005,   
                                                       Size=base_rates. Shape)
                 Discount_curve = ql.ZeroCurve (nodes,    list (rates),    ql. Actual 360 ())
                 Ql.Settings.Instance (). EvaluationDate = date
                 Discount_handle.LinkTo (discount_curve)
                 Prices[date] = bond.CleanPrice ()
                 Date = calendar.Advance (date,    -1,    ql. Days)
Here are the results. Through the random noise,    you can see how the price increases as the bond gets nearer to maturity.
    In [13]: %matplotlib inline
             Import utils
    In [14]: dates,    values = zip (*sorted (prices.Items ()))
    In [15]: fig,    ax = utils.Plot ()
             Ax. Xaxis. Set_major_formatter (utils. Date_formatter ())
             Ax. Plot_date ([ utils. To_datetime (d) for d in dates ],    values,   '-');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/pricing_over_a_range_of_days-15.png)
::: ##### Using quotes { #chap09 . xhtml\_leanpub-auto-using-quotes} If we work with quotes,    we can also avoid rebuilding the curve. Let's say our discount curve is defined as a risk-free curve with an additional credit spread. The risk-free curve is bootstrapped from a number of market rates; for simplicity,    here I'll use a set of overnight interest-rate swaps,    but you'll use whatever makes sense in your case.
    In [16]: index = ql.Eonia ()
             Tenors = [ ql.Period (i,    ql. Years) for i in range (1,   11) ]
             Rates = [ 0.010,    0.012,    0.013,    0.014,    0.016,   
                       0.017,    0.018,    0.020,    0.021,    0.022 ]
             Quotes = []
             Helpers = []
             For tenor,    rate in zip (tenors,    rates):
                 Q = ql.SimpleQuote (rate)
                 H = ql.OISRateHelper (2,    tenor,    ql.QuoteHandle (q),    index)
                 Quotes.Append (q)
                 Helpers.Append (h)
One thing to note: I'll setup the curve so that it moves with the evaluation date. This means that I won't pass an explicit reference date,    but a number of business days and a calendar. Passing 0,    as in this case,    will cause the reference date of the curve to equal the evaluation date; passing 2,    for instance,    would cause it to equal the corresponding spot date.
    In [17]: risk_free_curve = ql.PiecewiseFlatForward (0,    ql.TARGET (),   
                                                       Helpers,    ql. Actual 360 ())
Finally,    I'll manage credit as an additional spread over the curve:
    In [18]: spread = ql.SimpleQuote (0.01)
             Discount_curve = ql.ZeroSpreadedTermStructure (
                 Ql.YieldTermStructureHandle (risk_free_curve),   
                 Ql.QuoteHandle (spread))
Now we can recalculate today's price...
    In [19]: prices = {}
             Ql.Settings.Instance (). EvaluationDate = today
             Discount_handle.LinkTo (discount_curve)
             Prices[today] = bond.CleanPrice ()
             Print (prices[today])
    Out[19]: 96.50362161659807
... And as before,    we go back; except this time we don't need to build a new curve. Instead,    we can set new values to the quotes and they will trigger the necessary recalculations.
    In [20]: date = calendar.Advance (today,    -1,    ql. Days)
             Base_rates = np.Array (rates)
             While date >= first_date:
                 Rates = base_rates * np.Random.Normal (loc=1.0,    scale=0.005,   
                                                       Size=base_rates. Shape)
                 For q,    r in zip (quotes,    rates):
                     q.setValue (r)
                 Spread.SetValue (spread.Value ()*np.Random.Normal (loc=1.0,    scale=0.005))
                 Ql.Settings.Instance (). EvaluationDate = date
                 Prices[date] = bond.CleanPrice ()
                 Date = calendar.Advance (date,    -1,    ql. Days)
Note that we didn't create any new object in the loop; we're only settings new values to the quotes. Again,    here are the results:
    In [21]: dates,    values = zip (*sorted (prices.Items ()))
             Fig,    ax = utils.Plot ()
             Ax. Xaxis. Set_major_formatter (utils. Date_formatter ())
             Ax. Plot_date ([ utils. To_datetime (d) for d in dates ],    values,   '-');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/pricing_over_a_range_of_days-21.png)
::: ##### A complication: past fixings { #chap09 . xhtml\_leanpub-auto-a-complication-past-fixings} For instruments that depend on the floating rate,    we might need some past fixings. This is not necessarily related to pricing on a range of dates: even on today's date,    we need the fixing for the current coupon. Let's set the instrument up...
    In [22]: forecast_handle = ql.YieldTermStructureHandle (risk_free_curve)
             Index = ql. Euribor 6 M (forecast_handle)
             Bond = ql.FloatingRateBond (3,    100,    schedule,    index,    ql. Thirty 360 ())
             Bond.SetPricingEngine (ql.DiscountingBondEngine (discount_handle))
    In [23]: ql.Settings.Instance (). EvaluationDate = today
             For q,    r in zip (quotes,    base_rates):
                 q.setValue (r)
             Spread.SetValue (0.01)
... And try to price it. No joy.
    In [24]: print (bond.CleanPrice ())
    Out[24]: ---------------------------------------------------------------------------
             RuntimeError                              Traceback (most recent call last)
             <ipython-input-24-74ed33c38331> in <module>
             ----> 1 print (bond.CleanPrice ())
             /usr/local/lib/python 3.6/dist-packages/QuantLib/QuantLib. Py in cleanPrice (self,    *args)
               15417 
               15418     def cleanPrice (self,    *args):
             > 15419         return _QuantLib. Bond_cleanPrice (self,    *args)
               15420 
               15421     def dirtyPrice (self,    *args):
             RuntimeError: Missing Euribor 6 M Actual/360 fixing for February 6 th,    2018
Being in the past,    the fixing can't be retrieved from the curve. We have to store it into the index,    after which the calculation works:
    In [25]: index.AddFixing (ql.Date (6,    ql. February,    2018),    0.005)
             Print (bond.CleanPrice ())
    Out[25]: 97.11939323923686
When pricing on a range of dates,    though,    we need to take into account the fact that the current coupon changes as we go back in time. These two dates will work...
    In [26]: ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. March,    2018)
             Print (bond.CleanPrice ())
             Ql.Settings.Instance (). EvaluationDate = ql.Date (15,    ql. February,    2018)
             Print (bond.CleanPrice ())
    Out[26]: 96.84331874622794
             96.79054303973298
... But this one causes the previous coupon to be evaluated,    and that requires a new fixing:
    In [27]: ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. February,    2018)
             Print (bond.CleanPrice ())
    Out[27]: ---------------------------------------------------------------------------
             RuntimeError                              Traceback (most recent call last)
             <ipython-input-27-59706c1763aa> in <module>
                   1 ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. February,    2018)
             ----> 2 print (bond.CleanPrice ())
             /usr/local/lib/python 3.6/dist-packages/QuantLib/QuantLib. Py in cleanPrice (self,    *args)
               15417 
               15418     def cleanPrice (self,    *args):
             > 15419         return _QuantLib. Bond_cleanPrice (self,    *args)
               15420 
               15421     def dirtyPrice (self,    *args):
             RuntimeError: Missing Euribor 6 M Actual/360 fixing for August 4 th,    2017
Once we add it,    the calculation works again.
    In [28]: index.AddFixing (ql.Date (4,    ql. August,    2017),    0.004)
             Print (bond.CleanPrice ())
    Out[28]: 96.98060241422583
(If you're wondering how the calculation worked before,    since this coupon belonged to the bond: on the other evaluation dates,    this coupon was expired and the engine could skip it without needing to calculate its amount. Thus,    its fixing didn't need to be retrieved.) ##### More complications: future prices { #chap09 . xhtml\_leanpub-auto-more-complications-future-prices} What if we go forward in time,    instead of pricing on past dates? For one thing,    we'll need to forecast curves in some way. One way is to imply them from today's curves: I talk about implied curves in another notebook,    so I won't repeat myself here. Let's assume we have implied rates and we can set them. Once we do,    we can price in the future just as easily as we do in the past. As I write this,    it's May 19 th 2018,    and June 1 st is in the future:
    In [29]: ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. June,    2018)
             Print (bond.CleanPrice ())
    Out[29]: 97.2126812565699
However,    there's another problem,    as pointed out by $$Mariano Zeron$$( https://sourceforge.net/p/quantlib/mailman/message/35270917/ ) in a post to the QuantLib mailing list. If we go further in the future,    the bond will require---so to speak---future past fixings.
    In [30]: ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. June,    2019)
             Print (bond.CleanPrice ())
    Out[30]: ---------------------------------------------------------------------------
             RuntimeError                              Traceback (most recent call last)
             <ipython-input-30-bdfbd457ca41> in <module>
                   1 ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. June,    2019)
                   2 
             ----> 3 print (bond.CleanPrice ())
             /usr/local/lib/python 3.6/dist-packages/QuantLib/QuantLib. Py in cleanPrice (self,    *args)
               15417 
               15418     def cleanPrice (self,    *args):
             > 15419         return _QuantLib. Bond_cleanPrice (self,    *args)
               15420 
               15421     def dirtyPrice (self,    *args):
             RuntimeError: Missing Euribor 6 M Actual/360 fixing for February 6 th,    2019
Here the curve starts on June 1 st 2019,    and cannot retrieve the fixing at the start of the corresponding coupon. One way out of this might be to forecast fixings off the current curve and store them:
    In [31]: ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. June,    2018)
             Future_fixing = index.Fixing (ql.Date (6,    ql. February,    2019))
             Print (future_fixing)
             Index.AddFixing (ql.Date (6,    ql. February,    2019),    future_fixing)
    Out[31]: 0.011387399107860378
This way,    they will be retrieved in the same way as real past fixings.
    In [32]: ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. June,    2019)
             Print (bond.CleanPrice ())
    Out[32]: 98.30830224923507
Of course,    you might forecast them in a better way: that's up to you. And if you're worried that this might interfere with pricing on today's date,    don't: stored fixings are only used if they're in the past with respect to the evaluation date. The fixing I'm storing below for February 3 rd 2021 will be retrieved if the evaluation date is later...
    In [33]: index.AddFixing (ql.Date (3,    ql. February,    2021),    0.02)
             Ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. June,    2021)
             Print (index.Fixing (ql.Date (3,    ql. February,    2021)))
    Out[33]: 0.02
... But it will be forecast from the curve when it's after the evaluation date:
    In [34]: ql.Settings.Instance (). EvaluationDate = ql.Date (1,    ql. June,    2020)
             Print (index.Fixing (ql.Date (3,    ql. February,    2021)))
    Out[34]: 0.011367299732914539
$$$${ #chap10 . xhtml}
\## $$7.$${. Section-number}A note on random numbers and dimensionality { #chap10 . xhtml\_leanpub-auto-a-note-on-random-numbers-and-dimensionality} ##### Setup { #chap10 . xhtml\_leanpub-auto-setup-3} Import QuantLib and the graphing module.
    In [1]: %matplotlib inline
            Import matplotlib. Pyplot as plt
            Import QuantLib as ql
Also,    define a helper function to make the notebook less verbose.
    In [2]: def set_unit_square (ax):
                Ax.Axis ('scaled')
                Ax. Set_xlim ([0,   1])
                Ax. Set_ylim ([0,   1])
\##### Covering a unit square { #chap10 . xhtml\_leanpub-auto-covering-a-unit-square} Let's say we want to extract points inside a unit square; that is,    pairs of points in the domain !$$(0,   1) \\\\times (0,   1)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_4. Png){. Inline-equation width="100"}. The dimensionality of the problem is 2,    since we need 2 numbers,    !$$x$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_5. Png){. Inline-equation width="9"} and !$$y$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_6. Png){. Inline-equation width="8"},    per each sample. With pseudo-random numbers,    it doesn't matter much: we can just extract single numbers and form pairs from them.
    In [3]: rng = ql.MersenneTwisterUniformRng (42)
    In [4]: xs = []
            Ys = []
            For i in range (2047):
                Xs.Append (rng.Next (). Value ())
                Ys.Append (rng.Next (). Value ())
    In [5]: fig = plt.Figure (figsize=(8,   8))
            Ax = fig. Add_subplot (1,   1,   1)
            Set_unit_square (ax)
            Ax.Plot (xs,    ys,   'o');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/random_numbers-5.png)
::: The same doesn't hold for quasi-random numbers,    for which each sample is correlated to the one that follows it in order to cover the domain evenly. We can see this by plotting the sequence of Sobol numbers generated to cover the 1-dimensional unit interval:
    In [6]: fig = plt.Figure (figsize=(12,   4))
            For i,    n in enumerate ([0,   1,   2,   3,    4,   5,   6,   7,    9,   11,   13,   15,    19,   23,   27,   31]):
                Rng = ql.SobolRsg (1)
                Xs = [ rng.NextSequence (). Value ()[0] for j in range (n) ]
                Ax = fig. Add_subplot (4,    4,    i+1)
                Ax.Axis ('scaled')
                Ax. Set_xlim ([0,   1])
                Ax. Set_ylim ([-0.1,   0.1])
                Ax. Set_xticks ([])
                Ax. Set_yticks ([])
                Ax.Plot (xs,   [0]*len (xs),   'o')
                Ax.Text (0.0,    0.15,    'n = %d' % n)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/random_numbers-6.png)
::: The points are not added randomly at all,    but in a predetermined sequence. This ruins the random properties of the sequence when used with the wrong dimensionality. (You can also see how an even coverage is only obtained for a number of samples of the form !$$n = 2\\^i -1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_7. Png){. Inline-equation width="80"} for some !$$i$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_8. Png){. Inline-equation width="5"}.)
    In [7]: rng = ql.SobolRsg (1)
    In [8]: xs = []
            Ys = []
            For i in range (2047):
                Xs.Append (rng.NextSequence (). Value ()[0])
                Ys.Append (rng.NextSequence (). Value ()[0])
    In [9]: fig = plt.Figure (figsize=(8,   8))
            Ax = fig. Add_subplot (1,   1,   1)
            Set_unit_square (ax)
            Ax.Plot (xs,    ys,   'o');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/random_numbers-9.png)
::: To cover the domain correctly,    we have to use the right dimensionality.
    In [10]: rng = ql.SobolRsg (2)
    In [11]: xs = []
             Ys = []
             For i in range (2047):
                 X,    y = rng.NextSequence (). Value ()
                 Xs.Append (x)
                 Ys.Append (y)
    In [12]: fig = plt.Figure (figsize=(8,   8))
             Ax = fig. Add_subplot (1,   1,   1)
             Set_unit_square (ax)
             Ax.Plot (xs,    ys,   'o');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/random_numbers-12.png)
::: The pattern above covers the square evenly,    and also causes projections on the two axes to have good coverage (which wouldn't happen,    for instance,    with a regular placement in rows and columns; the projections of most points would coincide). It is also interesting to see how the coverage is built as the number of samples increase:
    In [13]: fig = plt.Figure (figsize=(12,   9))
             For i,    n in enumerate ([0,   1,   2,   3,    4,   5,   6,   7,    15,   31,   63,   127]):
                 Rng = ql.SobolRsg (2)
                 Ax = fig. Add_subplot (3,    4,    i+1)
                 Ax. Set_xticks ([])
                 Ax. Set_yticks ([])
                 If n == 0:
                     Continue
                 Points = [ rng.NextSequence (). Value () for j in range (n) ]
                 Xs,    ys = zip (*points)
                 Ax.Axis ('scaled')
                 Ax. Set_xlim ([0,   1])
                 Ax. Set_ylim ([0,   1])
                 Ax.Plot (xs,    ys,   'o')
                 Ax.Text (0.0,    1.05,    'n = %d' % n)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/random_numbers-13.png)
::: ##### Dimensionality of Monte Carlo simulations { #chap10 . xhtml\_leanpub-auto-dimensionality-of-monte-carlo-simulations} The classes in the QuantLib Monte Carlo framework will check the dimensionality of the generators they're given and will warn you if it's not correct. It's still up to you to find the correct one,    while writing your engines (for details on that,    you can check chapter 6 of $$\*Implementing QuantLib\*$$( https://leanpub.com/implementingquantlib )). For instance,    let's say that you want to simulate three correlated stocks; and for sake of simplicity,    let's say they follow the Black-Scholes process. You'll build a process for each of them...
    In [14]: today = ql.Date (27,    ql. January,    2018)
             Ql.Settings.Instance (). EvaluationDate = today
             Risk_free = ql.YieldTermStructureHandle (
                 Ql.FlatForward (today,    0.01,    ql. Actual 360 ()))
             Processes = [
                 Ql.BlackScholesProcess (
                     Ql.QuoteHandle (ql.SimpleQuote (S)),   
                     Risk_free,   
                     Ql.BlackVolTermStructureHandle (
                         Ql.BlackConstantVol (today,    ql.TARGET (),    sigma,    ql. Actual 360 ())))
                 For S,    sigma in [(100,    0.20),   
                                  ( 80,    0.25),   
                                  (110,    0.18)] ]
... And a single multi-dimensional process that correlates them. In this case,    the resulting process has three random drivers.
    In [15]: rho = [[1.0,    0.6,    0.8],   
                    [0.6,    1.0,    0.4],   
                    [0.8,    0.4,    1.0]]
             Process = ql.StochasticProcessArray (processes,    rho)
             Print (process.Factors ())
    Out[15]: 3
Now,    let's say that we want to simulate paths over four steps,    starting from today and ending one year from now. Each sample of the Monte Carlo simulation will need three random number for each step,    for a total of 12 random numbers. This is the dimensionality of the problem; and,    as I mentioned,    the framework will check it and complain if it doesn't match. (Please bear with me as I build the several classes needed for random-numbers generation. If find yourself doing this,    you might want to write a helper function,    like I do here.)
    In [16]: def rng (dimensionality):
                 Return ql.GaussianRandomSequenceGenerator (
                     Ql.UniformRandomSequenceGenerator (
                         Dimensionality,   
                         Ql.UniformRandomGenerator (42)))
             Times = [0.25,    0.50,    0.75,    1.0]
             Generator = ql.GaussianMultiPathGenerator (process,    times,    rng (10))
    Out[16]: ---------------------------------------------------------------------------
             RuntimeError                              Traceback (most recent call last)
             <ipython-input-16-b09a2e817c24> in <module>
                   6 
                   7 times = [0.25,    0.50,    0.75,    1.0]
             ----> 8 generator = ql.GaussianMultiPathGenerator (process,    times,    rng (10))
             /usr/local/lib/python 3.6/dist-packages/QuantLib/QuantLib. Py in __init__(self,    process\
    ,    times,    generator,    brownianBridge)
               19782 
               19783     def __init__(self,    process,    times,    generator,    brownianBridge=False):
             > 19784         this = _QuantLib. New_GaussianMultiPathGenerator (process,    times,    gener\
    Ator,    brownianBridge)
               19785         try:
               19786             self.This.Append (this)
             RuntimeError: dimension (10) is not equal to (3 * 4) the number of factors times the \
    Number of time steps
As you might expect,    the thing works with the correct dimensionality:
    In [17]: generator = ql.GaussianMultiPathGenerator (process,    times,    rng (12))
    In [18]: sample = generator.Next (). Value ()
    In [19]: fig = plt.Figure (figsize=(12,   6))
             Ax = fig. Add_subplot (1,   1,   1)
             Ts = [0.0] + times
             Y_min = 80
             Y_max = 110
             For i in range (3):
                 P,    = ax.Plot (ts,    sample[i],    label='Stock %d' % (i+1))
                 ax.Plot (ts,    sample[i],    'o',    color=p.get_color ())
                 Y_min = min (y_min,    min (sample[i]))
                 Y_max = max (y_max,    max (sample[i]))
             Ax. Set_xlim (0.0-0.02,    1.0+0.02)
             Ax. Set_xticks (ts)
             Ax. Set_ylim (y_min-2,    y_max+2)
             Ax.Legend (loc='best');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/random_numbers-19.png)
:::
$$$${ #chap11 . xhtml}
\# Interest-rate curves { #chap11 . xhtml\_leanpub-auto-interest-rate-curves}
$$$${ #chap12 . xhtml}
\## $$8.$${. Section-number}EONIA curve bootstrapping { #chap12 . xhtml\_leanpub-auto-eonia-curve-bootstrapping} In the next notebooks,    I'll reproduce the results of the paper by F. M. Ametrano and M. Bianchetti,    \*Everything You Always Wanted to Know About Multiple Interest Rate Curve Bootstrapping but Were Afraid to Ask\* (April 2,    2013). The paper is available at SSRN: http://ssrn.com/abstract=2219548.
    In [1]: %matplotlib inline
            Import math
            Import utils
    In [2]: import QuantLib as ql
    In [3]: today = ql.Date (11,    ql. December,    2012)
            Ql.Settings.Instance (). EvaluationDate = today
\##### First try { #chap12 . xhtml\_leanpub-auto-first-try} We start by instantiating helpers for all the rates used in the bootstrapping process,    as reported in figure 25 of the paper. The first three instruments are three 1-day deposit that give us discounting between today and the day after spot. They are modeled by three instances of the \`DepositRateHelper\` class with a tenor of 1 day and a number of fixing days going from 0 (for the deposit starting today) to 2 (for the deposit starting on the spot date).
    In [4]: helpers = [
                Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                     Ql.Period (1,    ql. Days),    fixingDays,   
                                     Ql.TARGET (),    ql. Following,   
                                     False,    ql. Actual 360 ())
                For rate,    fixingDays in [(0.04,    0),    (0.04,    1),    (0.04,    2)]
            ]
Then,    we have a series of OIS quotes for the first month. They are modeled by instances of the \`OISRateHelper\` class with varying tenors. They also require an instance of the \`Eonia\` class,    which doesn't need a forecast curve and can be shared between the helpers.
    In [5]: eonia = ql.Eonia ()
    In [6]: helpers += [
                Ql.OISRateHelper (2,    ql.Period (*tenor),   
                                 Ql.QuoteHandle (ql.SimpleQuote (rate/100)),    eonia)
                For rate,    tenor in [(0.070,    (1,    ql. Weeks)),    (0.069,    (2,    ql. Weeks)),   
                                    (0.078,    (3,    ql. Weeks)),    (0.074,    (1,    ql. Months))]
            ]
Next,    five OIS forwards on ECB dates. For these,    we need to instantiate the \`DatedOISRateHelper\` class and specify start and end dates explicitly.
    In [7]: helpers += [
                Ql.DatedOISRateHelper (start_date,    end_date,   
                                      Ql.QuoteHandle (ql.SimpleQuote (rate/100)),    eonia)
                For rate,    start_date,    end_date in [
                    ( 0.046,    ql.Date (16,    ql. January,    2013),    ql.Date (13,    ql. February,    2013)),   
                    ( 0.016,    ql.Date (13,    ql. February,    2013),    ql.Date (13,    ql. March,    2013)),   
                    (-0.007,    ql.Date (13,    ql. March,    2013),    ql.Date (10,    ql. April,    2013)),   
                    (-0.013,    ql.Date (10,    ql. April,    2013),    ql.Date (8,    ql. May,    2013)),   
                    (-0.014,    ql.Date (8,    ql. May,    2013),    ql.Date (12,    ql. June,    2013))]
            ]
Finally,    we add OIS quotes up to 30 years.
    In [8]: helpers += [
                Ql.OISRateHelper (2,    ql.Period (*tenor),   
                                 Ql.QuoteHandle (ql.SimpleQuote (rate/100)),    eonia)
                For rate,    tenor in [(0.002,    (15,    ql. Months)),    (0.008,    (18,    ql. Months)),   
                                    (0.021,    (21,    ql. Months)),    (0.036,    (2,    ql. Years)),   
                                    (0.127,    (3,    ql. Years)),    (0.274,    (4,    ql. Years)),   
                                    (0.456,    (5,    ql. Years)),    (0.647,    (6,    ql. Years)),   
                                    (0.827,    (7,    ql. Years)),    (0.996,    (8,    ql. Years)),   
                                    (1.147,    (9,    ql. Years)),    (1.280,    (10,    ql. Years)),   
                                    (1.404,    (11,    ql. Years)),    (1.516,    (12,    ql. Years)),   
                                    (1.764,    (15,    ql. Years)),    (1.939,    (20,    ql. Years)),   
                                    (2.003,    (25,    ql. Years)),    (2.038,    (30,    ql. Years))]
            ]
The curve is an instance of \`PiecewiseLogCubicDiscount\` (corresponding to the \`PiecewiseYieldCurve\` class in C++; I won't repeat the argument for this choice made in section 4.5 of the paper). We let the reference date of the curve move with the global evaluation date,    by specifying it as 0 days after the latter on the TARGET calendar. The day counter chosen is not of much consequence,    as it is only used internally to convert dates into times. Also,    we enable extrapolation beyond the maturity of the last helper; that is mostly for convenience as we retrieve rates to plot the curve near its far end.
    In [9]: eonia_curve_c = ql.PiecewiseLogCubicDiscount (0,    ql.TARGET (),   
                                                         Helpers,    ql. Actual 365 Fixed ())
            eonia_curve_c.enableExtrapolation ()
To compare the curve with the one shown in figure 26 of the paper,    we can retrieve daily overnight rates over its first two years and plot them:
    In [10]: today = eonia_curve_c.referenceDate ()
             End = today + ql.Period (2,    ql. Years)
             Dates = [ ql.Date (serial) for serial in range (today.SerialNumber (),   
                                                           End.SerialNumber ()+1) ]
             rates_c = [ eonia_curve_c.forwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
    In [11]: _,    ax = utils.Plot ()
             Utils. Highlight_x_axis (ax)
             Utils. Plot_curve (ax,    dates,    [(rates_c,   '-')],    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/eonia_curve_bootstrapping-11.png)
::: However,    we still have work to do. Out plot above shows a rather large bump at the end of 2012 which is not present in the paper. To remove it,    we need to model properly the turn-of-year effect. ##### Turn-of-year jumps { #chap12 . xhtml\_leanpub-auto-turn-of-year-jumps} As explained in section 4.8 of the paper,    the turn-of-year effect is a jump in interest rates due to an increased demand for liquidity at the end of the year. The jump is embedded in any quoted rates that straddles the end of the year and must be treated separately; the \`YieldTermStructure\` class allows this by taking any number of jumps,    modeled as additional discount factors,    and applying them at the specified dates. Our problem is to estimate the size of the jump. To simplify analysis,    we turn to flat forward rates instead of log-cubic discounts; thus,    we instantiate a \`PiecewiseFlatForward\` curve (corresponding to \`PiecewiseYieldCurve\` in C++).
    In [12]: eonia_curve_ff = ql.PiecewiseFlatForward (0,    ql.TARGET (),   
                                                      Helpers,    ql. Actual 365 Fixed ())
             Eonia_curve_ff.EnableExtrapolation ()
To show the jump more clearly,    I'll restrict the plot to the first 6 months:
    In [13]: end = today + ql.Period (6,    ql. Months)
             Dates = [ ql.Date (serial) for serial in range (today.SerialNumber (),   
                                                           End.SerialNumber ()+1) ]
             Rates_ff = [ eonia_curve_ff.ForwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                                     Ql. Actual 360 (),    ql. Simple). Rate ()
                          For d in dates ]
    In [14]: _,    ax = utils.Plot ()
             Utils. Highlight_x_axis (ax)
             Utils. Plot_curve (ax,    dates,    [(rates_ff,   '-')],    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/eonia_curve_bootstrapping-14.png)
::: As we see,    the forward ending at the beginning of January 2013 is out of line. In order to estimate the jump,    we need to estimate a "clean" forward that doesn't include it. A possible estimate (although not the only one) can be obtained by interpolating the forwards around the one we want to replace. To do so,    we extract the values of the forwards rates and their corresponding dates.
    In [15]: nodes = list (eonia_curve_ff.Nodes ())
If we look at the first few nodes,    we can clearly see that the seventh is out of line.
    In [16]: nodes[: 9]
    Out[16]: [(Date (11,   12,   2012),    0.00040555533025081675),   
              (Date (12,   12,   2012),    0.00040555533025081675),   
              (Date (13,   12,   2012),    0.00040555533047721286),   
              (Date (14,   12,   2012),    0.00040555533047721286),   
              (Date (20,   12,   2012),    0.0007604110692568178),   
              (Date (27,   12,   2012),    0.0006894305026004767),   
              (Date (3,   1,   2013),    0.0009732981324671213),   
              (Date (14,   1,   2013),    0.0006728161005748453),   
              (Date (13,   2,   2013),    0.000466380545910482)]
To create a curve that doesn't include the jump,    we replace the relevant forward rate with a simple average of the ones that precede and follow...
    In [17]: nodes[6] = (nodes[6][0],    (nodes[5][1]+nodes[7][1])/2.0)
             Nodes[: 9]
    Out[17]: [(Date (11,   12,   2012),    0.00040555533025081675),   
              (Date (12,   12,   2012),    0.00040555533025081675),   
              (Date (13,   12,   2012),    0.00040555533047721286),   
              (Date (14,   12,   2012),    0.00040555533047721286),   
              (Date (20,   12,   2012),    0.0007604110692568178),   
              (Date (27,   12,   2012),    0.0006894305026004767),   
              (Date (3,   1,   2013),    0.000681123301587661),   
              (Date (14,   1,   2013),    0.0006728161005748453),   
              (Date (13,   2,   2013),    0.000466380545910482)]
... And instantiate a \`ForwardCurve\` with the modified nodes.
    In [18]: temp_dates,    temp_rates = zip (*nodes)
             Temp_curve = ql.ForwardCurve (temp_dates,    temp_rates,   
                                          Eonia_curve_ff.DayCounter ())
For illustration,    we can extract daily overnight nodes from the doctored curve and plot them alongside the old ones:
    In [19]: temp_rates = [ temp_curve.ForwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                            For d in dates ]
    In [20]: _,    ax = utils.Plot ()
             Utils. Highlight_x_axis (ax)
             Utils. Plot_curve (ax,    dates,    [(temp_rates,   '-'),    (rates_ff,   '--')],   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/eonia_curve_bootstrapping-20.png)
::: Now we can estimate the size of the jump. As the paper hints,    it's more an art than a science. I've been able to reproduce closely the results of the paper by extracting from the two curves the forward rate over the two weeks around the end of the year:
    In [21]: d 1 = ql.Date (31,    ql. December,    2012) - ql.Period (1,    ql. Weeks)
             D 2 = ql.Date (31,    ql. December,    2012) + ql.Period (1,    ql. Weeks)
    In [22]: F = eonia_curve_ff.ForwardRate (d 1,    d 2,    ql. Actual 360 (),    ql. Simple). Rate ()
             F_1 = temp_curve.ForwardRate (d 1,    d 2,    ql. Actual 360 (),    ql. Simple). Rate ()
             Print (utils. Format_rate (F,    digits=3))
             Print (utils. Format_rate (F_1,    digits=3))
    Out[22]: 0.082 %
             0.067 %
We want to attribute the whole jump to the last day of the year,    so we rescale it according to !$$(F-F\_1) \\\\cdot t\\\_{12} = J \\\\cdot t\_J$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_9. Png){. Block-equation width="167"} where !$$t\\\_{12}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_10. Png){. Inline-equation width="19"} is the time between the two dates and !$$t\_J$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_11. Png){. Inline-equation width="14"} is the time between the start and end date of the end-of-year overnight deposit. This gives us a jump quite close to the value of 10.2 basis points reported in the paper.
    In [23]: t 12 = eonia_curve_ff.DayCounter (). YearFraction (d 1,    d 2)
             T_j = eonia_curve_ff.DayCounter (). YearFraction (ql.Date (31,    ql. December,    2012),   
                                                            Ql.Date (2,    ql. January,    2013))
             J = (F-F_1)*t 12/t_j
             Print (utils. Format_rate (J,    digits=3))
    Out[23]: 0.101 %
As I mentioned previously,    the jump can be added to the curve as a corresponding discount factor !$$1/(1+J \\\\cdot t\_J)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_12. Png){. Inline-equation width="102"} on the last day of the year. The information can be passed to the curve constructor,    giving us a new instance:
    In [24]: B = 1.0/(1.0+J*t_j)
             Jumps = [ql.QuoteHandle (ql.SimpleQuote (B))]
             Jump_dates = [ql.Date (31,    ql. December,    2012)]
             Eonia_curve_j = ql.PiecewiseFlatForward (0,    ql.TARGET (),   
                                                     Helpers,    ql. Actual 365 Fixed (),   
                                                     Jumps,    jump_dates)
Retrieving daily overnight rates from the new curve and plotting them,    we can see the jump quite clearly:
    In [25]: rates_j = [ eonia_curve_j.forwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
    In [26]: _,    ax = utils.Plot ()
             Utils. Highlight_x_axis (ax)
             Utils. Plot_curve (ax,    dates,    [(rates_ff,   '-'),    (rates_j,   'o')],   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/eonia_curve_bootstrapping-26.png)
::: We can now go back to log-cubic discounts and add the jump.
    In [27]: eonia_curve = ql.PiecewiseLogCubicDiscount (0,    ql.TARGET (),   
                                                        Helpers,    ql. Actual 365 Fixed (),   
                                                        Jumps,    jump_dates)
             Eonia_curve.EnableExtrapolation ()
    In [28]: rates_c = [ eonia_curve_c.forwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
             Rates = [ eonia_curve.ForwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                               Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
    In [29]: _,    ax = utils.Plot ()
             Utils. Highlight_x_axis (ax)
             Utils. Plot_curve (ax,    dates,    [(rates_c,   '-'),    (rates,   'o')],   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/eonia_curve_bootstrapping-29.png)
::: As you can see,    the large bump is gone now. The two plots in figure 26 can be reproduced as follows (omitting the jump at the end of 2013 for brevity,    and the flat forwards for clarity):
    In [30]: dates = [ today+ql.Period (i,    ql. Days) for i in range (0,    365*2+1) ]
             Rates = [ eonia_curve.ForwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                               Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Highlight_x_axis (ax)
             Utils. Plot_curve (ax,    dates,    [(rates,   '.')],    ymin=-0.001,    ymax=0.002,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/eonia_curve_bootstrapping-30.png)
:::
    In [31]: dates = [ today+ql.Period (i,    ql. Months) for i in range (0,    12*60+1) ]
             Rates = [ eonia_curve.ForwardRate (d,    ql.TARGET (). Advance (d,    1,    ql. Days),   
                                               Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,   '-')],    ymin=0.0,    ymax=0.035,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/eonia_curve_bootstrapping-31.png)
::: A final word of warning: as you saw,    the estimate of the jumps is not an exact science,    so it's best to check it manually and not to leave it to an automated procedure. Moreover,    jumps nowadays might be present at the end of each month,    as reported for instance in $$Paolo Mazzocchi's presentation at the QuantLib User Meeting 2014$$( https://speakerdeck.com/nando1970/eonia-jumps-and-proper-euribor-forwarding ). This,    too,    suggests particular care in building the Eonia curve.
$$$${ #chap13 . xhtml}
\## $$9.$${. Section-number}Euribor curve bootstrapping { #chap13 . xhtml\_leanpub-auto-euribor-curve-bootstrapping} In this notebook,    I'll go over the second part of F. M. Ametrano and M. Bianchetti,    \*Everything You Always Wanted to Know About Multiple Interest Rate Curve Bootstrapping but Were Afraid to Ask\* (April 2,    2013). The paper is available at SSRN: http://ssrn.com/abstract=2219548.
    In [1]: %matplotlib inline
            Import math
            Import numpy as np
            Import utils
    In [2]: import QuantLib as ql
    In [3]: today = ql.Date (11,    ql. December,    2012)
            Ql.Settings.Instance (). EvaluationDate = today
\##### Discounting curve { #chap13 . xhtml\_leanpub-auto-discounting-curve} The bootstrap of the Eonia curve was analyzed in another notebook,    so I'll just instantiate the curve here without further explanation.
    In [4]: eonia = ql.Eonia ()
    In [5]: helpers = [
                Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                     Ql.Period (1,    ql. Days),    fixingDays,   
                                     Ql.TARGET (),    ql. Following,    False,    ql. Actual 360 ())
                For rate,    fixingDays in [(0.04,    0),    (0.04,    1),    (0.04,    2)]
            ]
    In [6]: helpers += [
                Ql.OISRateHelper (2,    ql.Period (*tenor),   
                                 Ql.QuoteHandle (ql.SimpleQuote (rate/100)),    eonia)
                For rate,    tenor in [(0.070,    (1,    ql. Weeks)),    (0.069,    (2,    ql. Weeks)),   
                                    (0.078,    (3,    ql. Weeks)),    (0.074,    (1,    ql. Months))]
            ]
    In [7]: helpers += [
                Ql.DatedOISRateHelper (start_date,    end_date,   
                                      Ql.QuoteHandle (ql.SimpleQuote (rate/100)),    eonia)
                For rate,    start_date,    end_date in [
                    ( 0.046,    ql.Date (16,    ql. January,    2013),    ql.Date (13,    ql. February,    2013)),   
                    ( 0.016,    ql.Date (13,    ql. February,    2013),    ql.Date (13,    ql. March,    2013)),   
                    (-0.007,    ql.Date (13,    ql. March,    2013),    ql.Date (10,    ql. April,    2013)),   
                    (-0.013,    ql.Date (10,    ql. April,    2013),    ql.Date (8,    ql. May,    2013)),   
                    (-0.014,    ql.Date (8,    ql. May,    2013),    ql.Date (12,    ql. June,    2013))]
            ]
    In [8]: helpers += [
                Ql.OISRateHelper (2,    ql.Period (*tenor),   
                                 Ql.QuoteHandle (ql.SimpleQuote (rate/100)),    eonia)
                For rate,    tenor in [(0.002,    (15,    ql. Months)),    (0.008,    (18,    ql. Months)),   
                                    (0.021,    (21,    ql. Months)),    (0.036,    (2,    ql. Years)),   
                                    (0.127,    (3,    ql. Years)),    (0.274,    (4,    ql. Years)),   
                                    (0.456,    (5,    ql. Years)),    (0.647,    (6,    ql. Years)),   
                                    (0.827,    (7,    ql. Years)),    (0.996,    (8,    ql. Years)),   
                                    (1.147,    (9,    ql. Years)),    (1.280,    (10,    ql. Years)),   
                                    (1.404,    (11,    ql. Years)),    (1.516,    (12,    ql. Years)),   
                                    (1.764,    (15,    ql. Years)),    (1.939,    (20,    ql. Years)),   
                                    (2.003,    (25,    ql. Years)),    (2.038,    (30,    ql. Years))]
            ]
    In [9]: jumps = [ql.QuoteHandle (ql.SimpleQuote (math.Exp (-J*2.0/360)))
                     For J in [0.00102,    0.00086]]
            Jump_dates = [ql.Date (31,    ql. December,    2012),    ql.Date (31,    ql. December,    2013)]
    In [10]: eonia_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),    helpers,    
                                                        Ql. Actual 365 Fixed (),   
                                                        Jumps,    jump_dates)
             Eonia_curve.EnableExtrapolation ()
\##### 6-months Euribor { #chap13 . xhtml\_leanpub-auto-months-euribor} As we'll see,    most of the Euribor curves for different tenors have their own quirks. I'll start from the 6-months Euribor curve,    which is somewhat simpler due to having a number of quoted rates directly available for bootstrapping. The first instrument used in the paper if the TOM 6-months FRA,    which can be instantiated as a 6-months deposit with 3 fixing days; its rate (and those of all other FRAs) is retrieved from figure 6 in the paper.
    In [11]: helpers = [
                 Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (0.312/100)),   
                                      Ql.Period (6,    ql. Months),    3,   
                                      Ql.TARGET (),    ql. Following,    False,    ql. Actual 360 ())
             ]
Then comes a strip of 6-months FRA up to 2 years maturity:
    In [12]: euribor 6 m = ql. Euribor 6 M ()
    In [13]: helpers += [
                 Ql.FraRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                  Start,    euribor 6 m)
                 For rate,    start in [(0.293,    1),    (0.272,    2),    (0.260,    3),   
                                     (0.256,    4),    (0.252,    5),    (0.248,    6),   
                                     (0.254,    7),    (0.261,    8),    (0.267,    9),   
                                     (0.279,    10),    (0.291,    11),    (0.303,    12),   
                                     (0.318,    13),    (0.335,    14),    (0.352,    15),   
                                     (0.371,    16),    (0.389,    17),    (0.409,    18)]
             ]
Finally,    we have a series of swap rates with maturities from 3 to 60 years,    listed in figure 9. As the paper explains,    the curve being bootstrapped will be used only for forecasting the 6-months Euribor fixings paid by the floating leg; all the payments will be discounted by means of the OIS curve,    which is wrapped in a \`Handle\` and passed as an extra argument to the \`SwapRateHelper\` constructor.
    In [14]: discount_curve = ql.RelinkableYieldTermStructureHandle ()
             Discount_curve.LinkTo (eonia_curve)
    In [15]: helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                   Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                   Ql. Annual,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 6 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    tenor in [(0.424,    3),    (0.576,    4),    (0.762,    5),   
                                     (0.954,    6),    (1.135,    7),    (1.303,    8),   
                                     (1.452,    9),    (1.584,    10),    (1.809,    12),   
                                     (2.037,    15),    (2.187,    20),    (2.234,    25),   
                                     (2.256,    30),    (2.295,    35),    (2.348,    40),   
                                     (2.421,    50),    (2.463,    60)]
             ]
This will give us a decent Euribor curve,    that we can display it by sampling 6-months forward rates at a number of dates.
    In [16]: euribor 6 m_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),    helpers,   
                                                            Ql. Actual 365 Fixed ())
             Euribor 6 m_curve.EnableExtrapolation ()
    In [17]: spot = euribor 6 m_curve.ReferenceDate ()
             Dates = [ spot+ql.Period (i,    ql. Months) for i in range (0,    60*12+1) ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-')],    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-17.png)
::: This seems to work,    and at the scale of the plot it seems to match figure 32 in the paper; but looking closely at the first part of the curve,    you can see a glitch (some kind of dip) in the last part of 2014,    when the FRA strip ends.
    In [18]: dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (0,    52*4+1) ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,   '-')],    ymin=0.0,    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-18.png)
::: ##### Synthetic deposits { #chap13 . xhtml\_leanpub-auto-synthetic-deposits} In short,    the reason is that the short end of the curve (which is required for pricing FRAs; for instance,    the 1 x 7 FRA required the discount factor at 1 month from now) is extrapolated backwards from the first quoted pillar at 6 months and is not quite correct. This leads to oscillations as soon as the curve is out of the tight strip of FRA quotes. One way to correct this is to add synthetic deposits with short tenors,    as explained in section 4.4.2 of the paper. To begin with,    let's save the original curve to another variable for later comparison.
    In [19]: euribor 6 m_curve_0 = euribor 6 m_curve
As detailed in the paper,    one can model the basis between the Euribor market quotes and the corresponding OIS-based rates as a polynomial; that is,    following equation 88,    !$$R\\\_{x}(T\_1,    T\_2) \\\\tau (T\_1,    T\_2) = R\\\_{on}(T\_1,    T\_2) \\\\tau (T\_1,    T\_2) + \\\\Delta (T\_1,    T\_2)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_13. Png){. Block-equation width="424"} In the paper,    the expression for !$$\\\\Delta (T\_1,    T\_2)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_14. Png){. Inline-equation width="71"} is given by equation 90,    that is,    !$$\\\\Delta (T\_1,    T\_2) = \\\\alpha \\\\cdot (T\_2-T\_1) + \\\\frac{1}{2} \\\\beta \\\\cdot (T\_2-T\_1)\\^2 + \\\\frac{1}{3} \\\\gamma \\\\cdot (T\_2-T\_1)\\^3 + \\\\ldots$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_15. Png){. Block-equation width="519"} However,    the above leads to problems when trying to solve for more than one coefficient. Following $$a later formulation$$( https://speakerdeck.com/nando1970/eonia-jumps-and-proper-euribor-forwarding ),    I'll express the instantaneous basis instead as !$$\\\\delta (t) = \\\\alpha + \\\\beta \\\\cdot t + \\\\gamma \\\\cdot t\\^2 + \\\\ldots$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_16. Png){. Block-equation width="222"} which leads to !$$\\\\Delta (T\_1,    T\_2) = \\\\int\\\_{T\_1}\\^{T\_2} \\\\delta (t) = \\\\alpha \\\\cdot (T\_2-T\_1) + \\\\frac{1}{2} \\\\beta \\\\cdot (T\_2\\^2-T\_1\\^2) + \\\\frac{1}{3} \\\\gamma \\\\cdot (T\_2\\^3-T\_1\\^3) + \\\\ldots$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_17. Png){. Block-equation width="606"} Once the basis is known,    we can calculate synthetic deposit rates !$$R (0,    T)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_18. Png){. Inline-equation width="56"} for any maturity !$$T$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_19. Png){. Inline-equation width="12"}. Depending on how many polynomial coefficients we want to determine,    we'll need a corresponding number of market quotes; by replacing their values and those of the OIS rates in equation 88 we can solve for !$$\\\\alpha$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_20. Png){. Inline-equation width="10"},    !$$\\\\beta$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_21. Png){. Inline-equation width="10"} and any other coefficient. For a constant polynomial,    we'll need one quote to determine !$$\\\\alpha$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_22. Png){. Inline-equation width="10"}; we can use the TOM 6-months deposit that the Euribor curve reprices exactly.
    In [20]: d = ql.TARGET (). Advance (spot,    1,    ql. Days)
             F_x = euribor 6 m_curve_0.ForwardRate (d,    ql.TARGET (). Advance (d,    6,    ql. Months),   
                                                 Ql. Actual 360 (),    ql. Simple). Rate ()
             F_on = eonia_curve.ForwardRate (d,    ql.TARGET (). Advance (d,    6,    ql. Months),   
                                            Ql. Actual 360 (),    ql. Simple). Rate ()
             Day_counter = euribor 6 m.DayCounter ()
             T_x = day_counter.YearFraction (d,    ql.TARGET (). Advance (d,    6,    ql. Months))
             Alpha = (F_x - F_on)
             Print (alpha)
    Out[20]: 0.002949286970370156
From the basis,    we can instantiate synthetic deposits for a number of maturities below 6 months...
    In [21]: synth_helpers = []
             For n,    units in [(1,    ql. Days),    (1,    ql. Weeks),    (2,    ql. Weeks),    (3,    ql. Weeks),   
                              (1,    ql. Months),    (2,    ql. Months),    (3,    ql. Months),   
                              (4,    ql. Months),    (5,    ql. Months)]:
                 T = day_counter.YearFraction (spot,    ql.TARGET (). Advance (spot,    n,    units))
                 F_on = eonia_curve.ForwardRate (
                     Spot,    ql.TARGET (). Advance (spot,    n,    units),   
                     Ql. Actual 360 (),    ql. Simple). Rate ()
                 F = F_on + alpha
                 Print ("{0}: {1}".Format (ql.Period (n,    units),    utils. Format_rate (F,    4)))
                 Synth_helpers.Append (
                     Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (F)),   
                                          Ql.Period (n,    units),    2,   
                                          Ql.TARGET (),    ql. Following,   
                                          False,    ql. Actual 360 ()))
    Out[21]: 1 D: 0.3349 %
             1 W: 0.3649 %
             2 W: 0.3639 %
             3 W: 0.3729 %
             1 M: 0.3689 %
             2 M: 0.3559 %
             3 M: 0.3419 %
             4 M: 0.3272 %
             5 M: 0.3188 %
... After which we can create a new curve,    which seems to have a smaller dip:
    In [22]: euribor 6 m_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),   
                                                            Helpers+synth_helpers,   
                                                            Ql. Actual 365 Fixed ())
             Euribor 6 m_curve.EnableExtrapolation ()
    In [23]: dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (0,    52*4+1) ]
             Rates_0 = [ euribor 6 m_curve_0.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                       Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates_0,   '-'),    (rates,   '-')],    ymin=0.0,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-23.png)
::: By choosing to sample at different dates,    we can zoom into the affected area. The original curve is the dotted line; the new curve is the solid one.
    In [24]: dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (65,    130) ]
             Rates_0 = [ euribor 6 m_curve_0.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                       Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates_0,   '.'),    (rates,   '-')],    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-24.png)
::: If we wanted to determine more coefficients for the basis,    we'd have to select more quotes and solve a linear system. For instance,    to determine both !$$\\\\alpha$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_23. Png){. Inline-equation width="10"} and !$$\\\\beta$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_24. Png){. Inline-equation width="10"},    we can use the TOM 6-months and the 1 x 7 FRAs:
    In [25]: start = ql.TARGET (). Advance (spot,    1,    ql. Days)
             End = ql.TARGET (). Advance (start,    6,    ql. Months)
             F_x = euribor 6 m_curve_0.ForwardRate (start,    end,   
                                                 Ql. Actual 360 (),    ql. Simple). Rate ()
             F_on = eonia_curve.ForwardRate (start,    end,   
                                            Ql. Actual 360 (),    ql. Simple). Rate ()
             T_x 0 = day_counter.YearFraction (start,    end)
             Delta 0 = F_x - F_on
             Start = ql.TARGET (). Advance (spot,    1,    ql. Months)
             End = ql.TARGET (). Advance (start,    6,    ql. Months)
             F_x = euribor 6 m_curve_0.ForwardRate (start,    end,   
                                                 Ql. Actual 360 (),    ql. Simple). Rate ()
             F_on = eonia_curve.ForwardRate (start,    end,   
                                            Ql. Actual 360 (),    ql. Simple). Rate ()
             T_x 1 = day_counter.YearFraction (start,    end)
             Delta 1 = F_x - F_on
             T 1 = day_counter.YearFraction (spot,    start)
             T 2 = day_counter.YearFraction (spot,    end)
             L = np.Array ([[T_x 0,    0.5*T_x 0**2],    [T_x 1,    0.5*(t 2**2-t 1**2)]])
             B = np.Array ([Delta 0*T_x 0,    Delta 1*T_x 1])
             Alpha,    beta = np.Linalg.Solve (L,    b)
             Print (alpha)
             Print (beta)
    Out[25]: 0.0030464085692271255
             -0.0003842173141594401
Again,    we can create synthetic deposits...
    In [26]: synth_helpers = []
             For n,    units in [(1,    ql. Days),   
                              (1,    ql. Weeks),    (2,    ql. Weeks),    (3,    ql. Weeks),   
                              (1,    ql. Months),    (2,    ql. Months),    (3,    ql. Months),   
                              (4,    ql. Months),    (5,    ql. Months)]:
                 T = day_counter.YearFraction (spot,    ql.TARGET (). Advance (spot,    n,    units))
                 F_on = eonia_curve.ForwardRate (spot,    ql.TARGET (). Advance (spot,    n,    units),   
                                                Ql. Actual 360 (),    ql. Simple). Rate ()
                 F = F_on + alpha + 0.5*beta*t
                 Print ("{0}: {1}".Format (ql.Period (n,    units),    utils. Format_rate (F,    4)))
                 Synth_helpers.Append (
                     Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (F)),   
                                          Ql.Period (n,    units),    2,   
                                          Ql.TARGET (),    ql. Following,   
                                          False,    ql. Actual 360 ()))
    Out[26]: 1 D: 0.3446 %
             1 W: 0.3743 %
             2 W: 0.3729 %
             3 W: 0.3815 %
             1 M: 0.3769 %
             2 M: 0.3623 %
             3 M: 0.3468 %
             4 M: 0.3304 %
             5 M: 0.3204 %
... And build a new curve. I'll leave it to you to decide whether this is an improvement over the degree-1 polynomial basis.
    In [27]: euribor 6 m_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),   
                                                            Helpers+synth_helpers,   
                                                            Ql. Actual 365 Fixed ())
             Euribor 6 m_curve.EnableExtrapolation ()
    In [28]: dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (0,    52*4+1) ]
             Rates_0 = [ euribor 6 m_curve_0.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                       Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates_0,   '-'),    (rates,   '-')],    ymin=0.0,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-28.png)
:::
    In [29]: dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (65,    130) ]
             Rates_0 = [ euribor 6 m_curve_0.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                       Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates_0,   '.'),    (rates,   '-')],    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-29.png)
::: One thing to note: the values I'm getting for the synthetic deposits are not the same as those reported by the paper in figure 17. I still haven't found the reason for the discrepancy. As for figure 32 in the paper,    here's how we can reproduce it:
    In [30]: spot = euribor 6 m_curve.ReferenceDate ()
             Dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (0,    2*52+1) ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-')],    ymin=0.0,    ymax=0.0075,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-30.png)
:::
    In [31]: spot = euribor 6 m_curve.ReferenceDate ()
             Dates = [ spot+ql.Period (i,    ql. Months) for i in range (0,    60*12+1) ]
             Rates = [ euribor 6 m_curve.ForwardRate (d,    euribor 6 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-')],    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-31.png)
::: ##### 12-months Euribor { #chap13 . xhtml\_leanpub-auto-months-euribor-1} For the 12-months curve,    we'll start with the quoted 12-months deposit and 12 x 24 FRA (see figures 4 and 5).
    In [32]: euribor 12 m = ql. Euribor 1 Y ()
             Helpers = [
                 Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (0.54/100)),   
                                      Ql.Period (12,    ql. Months),    2,   
                                      Ql.TARGET (),    ql. Following,    False,    ql. Actual 360 ())
             ]
             Helpers += [
                 Ql.FraRateHelper (ql.QuoteHandle (ql.SimpleQuote (0.5070/100)),   
                                  12,    euribor 12 m)
             ]
Unfortunately,    there are no quoted swap rates against 12-months Euribor. However,    the market quotes 6- vs 12-months basis swaps; and more importantly,    it quotes them as a portfolio of two IRS,    payer and receiver,    both accruing annual fixed coupons against Euribor 6 M and 12 M,    respectively. The spread between the two fixed legs is quoted so that it sets the NPV of the portfolio at zero. Given that the market also quotes the fair fixed rate for one of the two swaps,    i.e.,    the one paying a fixed rate against Euribor 6 M,    it's straightforward to see that the fair fixed rate for the swap against Euribor 12 M can be obtained by just adding the 6 M rate to the basis spread: that is,    if the NPV of a swap !$$S\_1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_25. Png){. Inline-equation width="16"} paying !$$K$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_26. Png){. Inline-equation width="15"} against Euribor 6 M is 0,    and if the NPV of the portfolio of !$$S\_1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_27. Png){. Inline-equation width="16"} minus another swap !$$S\_2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_28. Png){. Inline-equation width="16"} paying !$$K+S$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_29. Png){. Inline-equation width="50"} against Euribor 12 M is also 0,    then the NPV of !$$S\_2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_30. Png){. Inline-equation width="16"} must be 0 as well. This gives us quoted swap rates against Euribor 12 M up to 30 years,    which is the longest quoted maturity for basis swaps. The data are from figures 9 and 15.
    In [33]: helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote ((rate+basis)/100)),   
                                   Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                   Ql. Annual,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 12 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    basis,    tenor in [(0.424,    0.179,    3),    (0.576,    0.164,    4),   
                                            (0.762,    0.151,    5),    (0.954,    0.139,    6),   
                                            (1.135,    0.130,    7),    (1.303,    0.123,    8),   
                                            (1.452,    0.118,    9),    (1.584,    0.113,    10),   
                                            (1.809,    0.106,    12),    (2.037,    0.093,    15),   
                                            (2.187,    0.080,    20),    (2.234,    0.072,    25),   
                                            (2.256,    0.066,    30)] ]
Again,    we'll be using synthetic helpers to improve the shape of the short end of the curve. The same procedure we used for the Euribor 6 M curve lets us create deposits with a number of maturities below 1 year; I'll skip the calculation and just create helpers with the the resulting rates as reported by the paper.
    In [34]: synth_helpers = [
                 Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                      Ql.Period (*tenor),    2,   
                                      Ql.TARGET (),    ql. Following,    False,    ql. Actual 360 ())
                 For rate,    tenor in [(0.6537,    (1,    ql. Months)),    (0.6187,    (3,    ql. Months)),   
                                     (0.5772,    (6,    ql. Months)),    (0.5563,    (9,    ql. Months))] ]
It is also possible to build synthetic FRAs: their construction is explained in the paper. I'll leave it to a later version of this chapter; for the time being,    I'll just add the finished helpers.
    In [35]: synth_helpers += [
                 Ql.FraRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                  Months_to_start,    euribor 12 m)
                 For rate,    months_to_start in [(0.4974,    3),    (0.4783,    6),    (0.4822,    9),   
                                               (0.5481,    15),    (0.6025,    18)] ]
Finally,    we can extend the long end of the curve by creating synthetic swaps with maturities above 30 years. To calculate their rates,    we add the swap rates against Euribor 6 M (quoted up to 60 years) to the last quoted basis spread.
    In [36]: last_basis = 0.066
             Synth_helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote ((rate+last_basis)/100)),   
                                   Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                   Ql. Annual,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 12 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    tenor in [(2.295,    35),    (2.348,    40),   
                                     (2.421,    50),    (2.463,    60)] ]
Bootstrapping over the whole set of real and synthetic quotes gives us our final Euribor 12 M curve:
    In [37]: euribor 12 m_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),   
                                                             Helpers+synth_helpers,   
                                                             Ql. Actual 365 Fixed ())
             Euribor 12 m_curve.EnableExtrapolation ()
For comparison,    we can build another one excluding the synthetic helpers.
    In [38]: euribor 12 m_curve_0 = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),    helpers,   
                                                               Ql. Actual 365 Fixed ())
             Euribor 12 m_curve_0.EnableExtrapolation ()
The two curves are plotted together in the two following graphs,    which also reproduce figure 34 in the paper. The solid line corresponds to the complete curve,    and the dashed line to the curve without the synthetic helpers. The differences are obvious,    both in the short and in the long end.
    In [39]: spot = euribor 12 m_curve.ReferenceDate ()
             Dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (0,    2*52+1) ]
             Rates_0 = [ euribor 12 m_curve_0.ForwardRate (d,    euribor 12 m.MaturityDate (d),   
                                                        Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
             Rates = [ euribor 12 m_curve.ForwardRate (d,    euribor 12 m.MaturityDate (d),   
                                                    Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-'),    (rates_0,    '--')],    ymin=0.0,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-39.png)
:::
    In [40]: dates = [ spot+ql.Period (i,    ql. Months) for i in range (0,    60*12+1) ]
             Rates_0 = [ euribor 12 m_curve_0.ForwardRate (d,    euribor 12 m.MaturityDate (d),   
                                                        Ql. Actual 360 (),    ql. Simple). Rate ()
                         For d in dates ]
             Rates = [ euribor 12 m_curve.ForwardRate (d,    euribor 12 m.MaturityDate (d),   
                                                    Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-'),    (rates_0,    '--')],   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-40.png)
::: ##### 3-months Euribor { #chap13 . xhtml\_leanpub-auto-months-euribor-2} For the 3-months Euribor,    we can use a strip of very liquid futures after the 3-months deposit; their rates are listed in figures 7 and 4,    respectively.
    In [41]: euribor 3 m = ql. Euribor 3 M ()
             Helpers = [ ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (0.179/100)),   
                                              Ql.Period (3,    ql. Months),    3,   
                                              Ql.TARGET (),    ql. Following,   
                                              False,    ql. Actual 360 ()) ]
             Helpers += [
                 Ql.FuturesRateHelper (ql.QuoteHandle (ql.SimpleQuote (100-rate)),   
                                      Start_date,    euribor 3 m,    ql.QuoteHandle ())
                 For rate,    start_date in [(0.1775,    ql.Date (19,    ql. December,    2012)),   
                                          (0.1274,    ql.Date (20,    ql. March,    2013)),   
                                          (0.1222,    ql.Date (19,    ql. June,    2013)),   
                                          (0.1269,    ql.Date (18,    ql. September,    2013)),   
                                          (0.1565,    ql.Date (18,    ql. December,    2013)),   
                                          (0.1961,    ql.Date (19,    ql. March,    2014)),   
                                          (0.2556,    ql.Date (18,    ql. June,    2014)),   
                                          (0.3101,    ql.Date (17,    ql. September,    2014))] ]
For the swaps,    we combine quotes for the swaps against 6-months Euribor with quotes for the 3-months against 6-months basis swap,    like we did for the 12-months curve; basis swap quotes for this tenor are available up to 50 years,    as shown in figure 15. In this case,    though,    the fixed rate against Euribor 3 M is lower than the one against Euribor 6 M; therefore,    the basis must be subtracted from the quoted rate:
    In [42]: helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote ((rate-basis)/100)),   
                                   Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                   Ql. Annual,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 3 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    basis,    tenor in [(0.424,    0.1395,    3),    (0.576,    0.1390,    4),   
                                            (0.762,    0.1395,    5),    (0.954,    0.1375,    6),   
                                            (1.135,    0.1350,    7),    (1.303,    0.1320,    8),   
                                            (1.452,    0.1285,    9),    (1.584,    0.1250,    10),   
                                            (1.809,    0.1170,    12),    (2.037,    0.1045,    15),   
                                            (2.187,    0.0885,    20),    (2.234,    0.0780,    25),   
                                            (2.256,    0.0700,    30),    (2.348,    0.0600,    40),   
                                            (2.421,    0.0540,    50)] ]
Again,    synthetic deposit rates can be calculated and added for short maturities...
    In [43]: synth_helpers = [
                 Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                      Ql.Period (*tenor),    2,   
                                      Ql.TARGET (),    ql. Following,    False,    ql. Actual 360 ())
                 For rate,    tenor in [(0.1865,    (2,    ql. Weeks)),    (0.1969,    (3,    ql. Weeks)),   
                                     (0.1951,    (1,    ql. Months)),    (0.1874,    (2,    ql. Months))] ]
... And again,    we can add a few synthetic swaps where quotes for the 3-months versus 6-months Euribor are not available. We can calculate a quote for the 35-years basis swap by interpolating between the 30- and 40-years quotes,    and one for the 60-years swap by extrapolating the 50-years quote flatly,    like we did for the 12-months Euribor. Note that in this case,    the authors of the paper choose instead to extrapolate the previous quotes linearly; anyway,    this gives a difference of less than half a basis point.
    In [44]: synth_helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote ((rate-basis)/100)),   
                                   Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                   Ql. Annual,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 3 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    basis,    tenor in [(2.295,    0.0650,    35),    (2.463,    0.0540,    60)] ]
\##### Turn of year { #chap13 . xhtml\_leanpub-auto-turn-of-year} This is not the end of the story,    though,    since one of the futures we used turns out to be out of line with respect to the others in the strip.
    In [45]: futures = [(0.1775,    ql.Date (19,    ql. December,    2012)),   
                        (0.1274,    ql.Date (20,    ql. March,    2013)),   
                        (0.1222,    ql.Date (19,    ql. June,    2013)),   
                        (0.1269,    ql.Date (18,    ql. September,    2013)),   
                        (0.1565,    ql.Date (18,    ql. December,    2013)),   
                        (0.1961,    ql.Date (19,    ql. March,    2014)),   
                        (0.2556,    ql.Date (18,    ql. June,    2014)),   
                        (0.3101,    ql.Date (17,    ql. September,    2014))]
Not surprisingly,    it's the one that spans the end of the year and thus includes the corresponding jump; that is,    the one at index 4 in the list,    starting on December 18 th. This can be seen clearly enough by fitting a spline between the other futures and plotting the quoted value against the curve:
    In [46]: spot = euribor 6 m_curve.ReferenceDate ()
             Day_counter = euribor 3 m.DayCounter ()
             Quotes,    times = zip (*[(q,    day_counter.YearFraction (spot,    d))
                                   For q,    d in futures])
             F = ql.MonotonicCubicNaturalSpline (times[: 4]+times[5:],   
                                                Quotes[: 4]+quotes[5:])
    In [47]: _,    ax = utils.Plot ()
             Ts,    fs = zip (*[(t,   f (t,    True)) for t in np.Arange (0.0,    2.0,    0.01)])
             Ax.Plot (ts,    fs)
             _ = ax.Plot (times,    quotes,   'o')
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-47.png)
::: We can also ask the interpolation for the estimated value and compare it with the real one:
    In [48]: print (utils. Format_rate (quotes[4]))
             Print (utils. Format_rate (f (times[4])))
    Out[48]: 15.65 %
             15.06 %
To account for the jump,    we can estimate the corresponding discount factor !$$e\\^{-J\\\*\\\\tau}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_31. Png){. Inline-equation width="40"} (where both !$$J$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_32. Png){. Inline-equation width="10"} and !$$\\\\tau$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_33. Png){. Inline-equation width="9"} are calculated with respect to the tenor of the futures) and add it to the curve.
    In [49]: J = (quotes[4] - f (times[4]))/100
             Tau = day_counter.YearFraction (ql.Date (18,    ql. December,    2013),   
                                            Ql.Date (18,    ql. March,    2014))
             Print (utils. Format_rate (J))
             Print (tau)
    Out[49]: 0.01 %
             0.25
    In [50]: jumps = [ql.QuoteHandle (ql.SimpleQuote (math.Exp (-J*tau)))]
             Jump_dates = [ql.Date (31,    ql. December,    2013)]
             Euribor 3 m_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),   
                                                            Helpers+synth_helpers,   
                                                            Ql. Actual 365 Fixed (),   
                                                            Jumps,    jump_dates)
             Euribor 3 m_curve.EnableExtrapolation ()
We can now reproduce figure 30 in the paper. The end-of-year jump can be seen clearly in the first plot.
    In [51]: spot = euribor 3 m_curve.ReferenceDate ()
             Dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (0,    2*52+1) ]
             Rates = [ euribor 3 m_curve.ForwardRate (d,    euribor 3 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-')],    ymin=0.0,    ymax=0.0075,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-51.png)
:::
    In [52]: dates = [ spot+ql.Period (i,    ql. Months) for i in range (0,    60*12+1) ]
             Rates = [ euribor 3 m_curve.ForwardRate (d,    euribor 3 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-')],    ymin=0.0,    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-52.png)
::: ##### 1-month Euribor { #chap13 . xhtml\_leanpub-auto-month-euribor} Last,    let's bootstrap the 1-month Euribor curve. Quoted instruments based on this tenor include the 1-month deposit and interest-rate swaps paying a monthly fixed rate against 1-month Euribor with maturities up to 1 year; their rates are listed in figures 4 and 11.
    In [53]: euribor 1 m = ql. Euribor 1 M ()
             Helpers = [
                 Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (0.110/100)),   
                                      Ql.Period (1,    ql. Months),    2,   
                                      Ql.TARGET (),    ql. Following,    False,    ql. Actual 360 ())
             ]
             Helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                   Ql.Period (tenor,    ql. Months),    ql.TARGET (),   
                                   Ql. Monthly,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 1 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    tenor in [(0.106,    2),    (0.096,    3),    (0.085,    4),    (0.079,    5),   
                                     (0.075,    6),    (0.071,    7),    (0.069,    8),    (0.066,    9),   
                                     (0.065,    10),    (0.064,    11),    (0.063,    12)] ]
For longer maturities,    we can combine the swaps against 6-months Euribor with the 1-month vs 6-months basis swaps shown in figure 15.
    In [54]: helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote ((rate-basis)/100)),   
                                   Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                   Ql. Annual,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 1 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    basis,    tenor in [(0.324,    0.226,    2),    (0.424,    0.238,    3),   
                                            (0.576,    0.246,    4),    (0.762,    0.250,    5),   
                                            (0.954,    0.250,    6),    (1.135,    0.248,    7),   
                                            (1.303,    0.245,    8),    (1.452,    0.241,    9),   
                                            (1.584,    0.237,    10),    (1.703,    0.233,    11),   
                                            (1.809,    0.228,    12),    (2.037,    0.211,    15),   
                                            (2.187,    0.189,    20),    (2.234,    0.175,    25),   
                                            (2.256,    0.163,    30)] ]
As before,    we can use synthetic deposits for maturities below the 1-month tenor...
    In [55]: synth_helpers = [
                 Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100)),   
                                      Ql.Period (*tenor),    2,   
                                      Ql.TARGET (),    ql. Following,    False,    ql. Actual 360 ())
                 For rate,    tenor in [(0.0661,    (1,    ql. Days)),    (0.098,    (1,    ql. Weeks)),   
                                     (0.0993,    (2,    ql. Weeks)),    (0.1105,    (3,    ql. Weeks))] ]
... And we'll extend the 30-years basis spread flatly to combine it with longer-maturity swaps against 6-months Euribor.
    In [56]: last_basis = 0.163
             Synth_helpers += [
                 Ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote ((rate-last_basis)/100)),   
                                   Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                   Ql. Annual,    ql. Unadjusted,   
                                   Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                   Euribor 1 m,    ql.QuoteHandle (),    ql.Period (0,    ql. Days),   
                                   Discount_curve)
                 For rate,    tenor in [(2.295,    35),    (2.348,    40),   
                                     (2.421,    50),    (2.463,    60)] ]
This curve,    too,    shows a jump at the end of the year. The paper claims that it can be determined and corrected by interpolating the quoted swaps with maturities from 1 to 12 months,    but I haven't reproduced the calculation yet. For the time being,    I'll just use the value reported in the paper and calculate the corresponding discount factor.
    In [57]: J = 0.0016
             T_j = euribor 1 m.DayCounter (). YearFraction (ql.Date (31,    ql. December,    2012),   
                                                       Ql.Date (2,    ql. January,    2013))
             B = 1.0/(1.0+J*t_j)
             Jumps = [ql.QuoteHandle (ql.SimpleQuote (B))]
             Jump_dates = [ql.Date (31,    ql. December,    2013)]
    In [58]: euribor 1 m_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),   
                                                            Helpers+synth_helpers,   
                                                            Ql. Actual 365 Fixed (),   
                                                            Jumps,    jump_dates)
             Euribor 1 m_curve.EnableExtrapolation ()
This last curve gives us figure 28 in the paper,    down to the oscillations during the first year.
    In [59]: spot = euribor 1 m_curve.ReferenceDate ()
             Dates = [ spot+ql.Period (i,    ql. Weeks) for i in range (0,    2*52+1) ]
             Rates = [ euribor 1 m_curve.ForwardRate (d,    euribor 1 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-')],    ymin=0.0,    ymax=0.0075,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-59.png)
:::
    In [60]: dates = [ spot+ql.Period (i,    ql. Months) for i in range (0,    60*12+1) ]
             Rates = [ euribor 1 m_curve.ForwardRate (d,    euribor 1 m.MaturityDate (d),   
                                                   Ql. Actual 360 (),    ql. Simple). Rate ()
                       For d in dates ]
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(rates,    '-')],    ymin=0.0,    ymax=0.035,   
                              Format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-60.png)
::: ##### Basis curves { #chap13 . xhtml\_leanpub-auto-basis-curves} Finally,    like the authors of the paper,    we summarize the results by calculating the difference between the FRA rates calculated on the corresponding Euribor curve and those calculated on the ON curve. This lets us reproduce the top panel of figure 35.
    In [61]: dates = [ spot+ql.Period (i,    ql. Months) for i in range (0,    12*30+1) ]
             Def basis (curve,    tenor):
                 Results = []
                 For d in dates:
                     D 2 = ql.TARGET (). Advance (d,    ql.Period (*tenor),    ql. ModifiedFollowing)
                     FRA 1 = curve.ForwardRate (d,    d 2,    ql. Actual 360 (),    ql. Simple). Rate ()
                     FRA 2 = eonia_curve.ForwardRate (d,    d 2,    ql. Actual 360 (),    ql. Simple). Rate ()
                     Results.Append (FRA 1-FRA 2)
                 Return results
             Basis_1 m = basis (euribor 1 m_curve,    (1,    ql. Months))
             Basis_3 m = basis (euribor 3 m_curve,    (3,    ql. Months))
             Basis_6 m = basis (euribor 6 m_curve,    (6,    ql. Months))
             Basis_12 m = basis (euribor 12 m_curve,    (12,    ql. Months))
             _,    ax = utils.Plot ()
             Utils. Plot_curve (ax,    dates,    [(basis_1 m,    '-'),    (basis_3 m,    '-'),   
                                          (basis_6 m,    '-'),    (basis_12 m,    '-')],   
                              Ymin=0,    ymax=0.006,    format_rates=True)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/euribor_curve_bootstrapping-61.png)
:::
$$$${ #chap14 . xhtml}
\## $$10.$${. Section-number}Constructing a yield curve { #chap14 . xhtml\_yc-construction} In this chapter we will go over the construction of treasury yield curve. Let's start by importing QuantLib and other necessary libraries.
    In [1]: import QuantLib as ql
            From pandas import DataFrame
            Import numpy as np
            Import utils
            %matplotlib inline
This is an example based on Exhibit 5-5 given in Frank Fabozzi's Bond Markets,    Analysis and Strategies,    Sixth Edition.
    In [2]: depo_maturities = [ql.Period (6,    ql. Months),    ql.Period (12,    ql. Months)]
            Depo_rates = [5.25,    5.5]
            # Bond rates
            Bond_maturities = [ql.Period (6*i,    ql. Months) for i in range (3,   21)]
            Bond_rates = [5.75,    6.0,    6.25,    6.5,    6.75,    6.80,    7.00,    7.1,    7.15,    
                          7.2,    7.3,    7.35,    7.4,    7.5,    7.6,    7.6,    7.7,    7.8]
            Maturities = depo_maturities+bond_maturities
            Rates = depo_rates+bond_rates
            DataFrame (list (zip (maturities,    rates)),    
                      Columns=["Maturities",   "Curve"],   
                      Index=['']*len (rates))
    Out[2]: 
  Maturities Curve --- ------------ -------   6 M 5.25   1 Y 5.50   1 Y 6 M 5.75   2 Y 6.00   2 Y 6 M 6.25   3 Y 6.50   3 Y 6 M 6.75   4 Y 6.80   4 Y 6 M 7.00   5 Y 7.10   5 Y 6 M 7.15   6 Y 7.20   6 Y 6 M 7.30   7 Y 7.35   7 Y 6 M 7.40   8 Y 7.50   8 Y 6 M 7.60   9 Y 7.60   9 Y 6 M 7.70   10 Y 7.80 Below we declare some constants and conventions used here. For the sake of simplicity,    we assume that some of the constants are the same for deposit rates and bond rates.
    In [3]: calc_date = ql.Date (15,    1,    2015)
            Ql.Settings.Instance (). EvaluationDate = calc_date
            Calendar = ql.UnitedStates ()
            Business_convention = ql. Unadjusted 
            Day_count = ql. Thirty 360 ()
            End_of_month = True
            Settlement_days = 0
            Face_amount = 100
            Coupon_frequency = ql.Period (ql. Semiannual)
            Settlement_days = 0
The basic idea of bootstrapping is to use the deposit rates and bond rates to create individual rate helpers. Then use the combination of the two helpers to construct the yield curve. As a first step,    we create the deposit rate helpers as shown below.
    In [4]: depo_helpers = [
                Ql.DepositRateHelper (ql.QuoteHandle (ql.SimpleQuote (r/100.0)),   
                                     M,   
                                     Settlement_days,   
                                     Calendar,   
                                     Business_convention,   
                                     End_of_month,   
                                     Day_count)
                For r,    m in zip (depo_rates,    depo_maturities)
            ]
The rest of the points are coupon bonds. We assume that the YTM given for the bonds are all par rates. So we have bonds with coupon rate same as the YTM. Using this information,    we construct the fixed rate bond helpers below.
    In [5]: bond_helpers = []
            For r,    m in zip (bond_rates,    bond_maturities):
                Termination_date = calc_date + m
                Schedule = ql.Schedule (calc_date,   
                                       Termination_date,    
                                       Coupon_frequency,    
                                       Calendar,   
                                       Business_convention,    
                                       Business_convention,    
                                       Ql. DateGeneration. Backward,    
                                       End_of_month)
                Bond_helper = ql.FixedRateBondHelper (
                    Ql.QuoteHandle (ql.SimpleQuote (face_amount)),   
                    Settlement_days,   
                    Face_amount,   
                    Schedule,   
                    [r/100.0],   
                    Day_count,   
                    Business_convention)
                Bond_helpers.Append (bond_helper)
The union of the two helpers is what we use in bootstrapping shown below.
    In [6]: rate_helpers = depo_helpers + bond_helpers
The \`get\_spot\_rates\` is a convenient wrapper function that we will use to get the spot rates on a monthly interval.
    In [7]: def get_spot_rates (
                    Yieldcurve,    day_count,    
                    Calendar=ql.UnitedStates (),    months=121):
                Spots = []
                Tenors = []
                Ref_date = yieldcurve.ReferenceDate ()
                Calc_date = ref_date
                For month in range (0,    months):
                    Yrs = month/12.0
                    D = calendar.Advance (ref_date,    ql.Period (month,    ql. Months))
                    Compounding = ql. Compounded
                    Freq = ql. Semiannual
                    Zero_rate = yieldcurve.ZeroRate (yrs,    compounding,    freq)
                    Tenors.Append (yrs)
                    Eq_rate = zero_rate.EquivalentRate (
                        Day_count,    compounding,    freq,    calc_date,    d). Rate ()
                    Spots.Append (100*eq_rate)
                Return DataFrame (list (zip (tenors,    spots)),   
                                 Columns=["Maturities",   "Curve"],   
                                 Index=['']*len (tenors))
The bootstrapping process is fairly generic in QuantLib. You can chose what variable you are bootstrapping,    and what is the interpolation method used in the bootstrapping. There are multiple piecewise interpolation methods that can be used for this process. The \`PiecewiseLogCubicDiscount\` will construct a piece wise yield curve using \`LogCubic\` interpolation of the \`Discount\` factor. Similarly \`PiecewiseLinearZero\` will use \`Linear\` interpolation of \`Zero\` rates. \`PiecewiseCubicZero\` will interpolate the \`Zero\` rates using a \`Cubic\` interpolation method.
    In [8]: yc_logcubicdiscount = ql.PiecewiseLogCubicDiscount (calc_date,   
                                                               Rate_helpers,   
                                                               Day_count)
The zero rates from the tail end of the \`PiecewiseLogCubicDiscount\` bootstrapping is shown below.
    In [9]: splcd = get_spot_rates (yc_logcubicdiscount,    day_count)
            Splcd.Tail ()
    Out[9]: 
  Maturities Curve --- ------------ ----------   9.666667 7.981384   9.750000 8.005292   9.833333 8.028145   9.916667 8.050187   10.000000 8.071649 The yield curves using the \`PiecewiseLinearZero\` and \`PiecewiseCubicZero\` is shown below. The tail end of the zero rates obtained from \`PiecewiseLinearZero\` bootstrapping is also shown below. The numbers can be compared with that of the \`PiecewiseLogCubicDiscount\` shown above.
    In [10]: yc_linearzero = ql.PiecewiseLinearZero (
                 Calc_date,    rate_helpers,    day_count
             )
             Yc_cubiczero = ql.PiecewiseCubicZero (
                 Calc_date,    rate_helpers,    day_count
             )
             Splz = get_spot_rates (yc_linearzero,    day_count)
             Spcz = get_spot_rates (yc_cubiczero,    day_count)
             Splz.Tail ()
    Out[10]: 
  Maturities Curve --- ------------ ----------   9.666667 7.976804   9.750000 8.000511   9.833333 8.024221   9.916667 8.047934   10.000000 8.071649 All three are plotted below to give you an overall perspective of the three methods.
    In [11]: fig,    ax = utils.Plot ()
             Ax.Plot (splcd["Maturities"],    splcd["Curve"],    '.',   
                     Label="LogCubicDiscount")
             Ax.Plot (splz["Maturities"],    splz["Curve"],   '--',    
                     Label="LinearZero")
             Ax.Plot (spcz["Maturities"],    spcz["Curve"],   
                     Label="CubicZero")
             Ax. Set_xlabel ("Months",    size=12)
             Ax. Set_ylabel ("Zero Rate",    size=12)
             Ax. Set_xlim (0.5,   10)
             Ax. Set_ylim ([5.25,   8])
             Ax.Legend (loc=0);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/term_structure_construction-11.png)
::: ##### Conclusion { #chap14 . xhtml\_leanpub-auto-conclusion-1} In this chapter we saw how to construct yield curves by bootstrapping bond quotes.
$$$${ #chap15 . xhtml}
\## $$11.$${. Section-number}Dangerous day-count conventions { #chap15 . xhtml\_leanpub-auto-dangerous-day-count-conventions} (Based on a question by Min Gao on the QuantLib mailing list. Thanks!)
    In [1]: import QuantLib as ql
    In [2]: today = ql.Date (22,   1,   2018)
            Ql.Settings.Instance (). EvaluationDate = today
    In [3]: %matplotlib inline
            Import utils
\##### The problem { #chap15 . xhtml\_leanpub-auto-the-problem} Talking about term structures in $$\*Implementing QuantLib\*$$( https://leanpub.com/implementingquantlib ),    I suggest to use simple day-count conventions such as Actual/360 or Actual/365 to initialize curves. That's because the convention is used internally to convert dates into times,    and we want the conversion to be as regular as possible. For instance,    we'd like distances between dates to be additive: given three dates !$$d\_1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_34. Png){. Inline-equation width="14"},    !$$d\_2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_35. Png){. Inline-equation width="15"} and !$$d\_3$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_36. Png){. Inline-equation width="15"},    we would expect that !$$T (d\_1,    d\_2) + T (d\_2,    d\_3) = T (d\_1,    d\_3)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_37. Png){. Inline-equation width="253"},    where !$$T$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_38. Png){. Inline-equation width="12"} denotes the time between dates. Unfortunately,    that's not always the case for some day counters. The property holds for most dates...
    In [4]: dc = ql. Thirty 360 (ql. Thirty 360. USA)
    In [5]: d 1 = ql.Date (1,    ql. January,    2018)
            D 2 = ql.Date (15,    ql. January,    2018)
            D 3 = ql.Date (31,    ql. January,    2018)
    In [6]: print (dc.YearFraction (d 1,    d 2) + dc.YearFraction (d 2,    d 3))
            Print (dc.YearFraction (d 1,    d 3))
    Out[6]: 0.08333333333333334
            0.08333333333333333
... But doesn't for some.
    In [7]: d 1 = ql.Date (1,    ql. January,    2018)
            D 2 = ql.Date (30,    ql. January,    2018)
            D 3 = ql.Date (31,    ql. January,    2018)
    In [8]: print (dc.YearFraction (d 1,    d 2) + dc.YearFraction (d 2,    d 3))
            Print (dc.YearFraction (d 1,    d 3))
    Out[8]: 0.08055555555555556
            0.08333333333333333
That's because some day-count conventions were designed to calculate the duration of a coupon,    not the distance between any two given dates. They have particular formulas and exceptions that make coupons more regular; but those exceptions also cause some pairs of dates to have strange properties. For instance,    there might be no distance at all between some particular distinct dates:
    In [9]: d 1 = ql.Date (30,    ql. January,    2018)
            D 2 = ql.Date (31,    ql. January,    2018)
            Print (dc.YearFraction (d 1,    d 2))
    Out[9]: 0.0
The 30/360 convention is not the worst offender,    either. Min Gao's question came from using for the term structure the same convention used for the bond being priced,    that is,    ISMA actual/actual. This day counter is supposed to be given a reference period,    as well as the two dates whose distance one needs to measure; failing to do so will result in the wrong results...
    In [10]: d 1 = ql.Date (1,    ql. January,    2018)
             D 2 = ql.Date (15,    ql. January,    2018)
             Reference_period = (ql.Date (1,    ql. January,    2018),    ql.Date (1,    ql. July,    2018))
    In [11]: dc = ql.ActualActual (ql. ActualActual. ISMA)
             Print (dc.YearFraction (d 1,    d 2,    *reference_period))
             Print (dc.YearFraction (d 1,    d 2))
    Out[11]: 0.03867403314917127
             0.038356164383561646
... And sometimes,    in spectacularly wrong results. Here is what happens if we plot the year fraction since January 1 st,    2018 as a function of the date over that same year.
    In [12]: d 1 = ql.Date (1,    ql. January,    2018)
             Dates = [ (d 1 + i) for i in range (366) ]
             Times = [ dc.YearFraction (d 1,    d) for d in dates ]
    In [13]: fig,    ax = utils.Plot ()
             Ax. Xaxis. Set_major_formatter (utils. Date_formatter ())
             Ax. Plot_date ([ utils. To_datetime (d) for d in dates ],    times,   '-');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/dangerous_day_counters-13.png)
::: Of course,    that's no way to convert dates into times. Using this day-count convention inside a coupon is ok,    of course. Using it inside a term structure,    which doesn't have any concept of a reference period,    leads to very strange behaviors.
    In [14]: curve = ql.FlatForward (today,    0.01,    ql.ActualActual (ql. ActualActual. ISMA))
    In [15]: dates = [ (today + i) for i in range (366) ]
             Discounts = [ curve.Discount (d) for d in dates ]
             Fig,    ax = utils.Plot ()
             Ax. Xaxis. Set_major_formatter (utils. Date_formatter ())
             Ax. Plot_date ([ utils. To_datetime (d) for d in dates ],    discounts,   '-');
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/dangerous_day_counters-15.png)
::: ##### Any solutions? { #chap15 . xhtml\_leanpub-auto-any-solutions} Not really,    at this time. Work is underway to store a schedule inside an ISMA actual/actual day counter and use it to retrieve the correct reference period,    but that's not fully working yet. In the meantime,    what I can suggest is to use the specified day-count conventions for coupons; but,    unless something prevents it,    use a simple day-count convention such as actual/360 or actual/365 for term structures.
$$$${ #chap16 . xhtml}
\## $$12.$${. Section-number}Implied term structures { #chap16 . xhtml\_leanpub-auto-implied-term-structures} (Based on $$a question$$( http://quant.stackexchange.com/questions/9589/ ) by \*Stack Exchange\* user Lisa Ann. Thanks!)
    In [1]: import QuantLib as ql
    In [2]: %matplotlib inline
            Import pandas as pd
            Import utils
            From utils import to_datetime,    format_rate
            From matplotlib. Dates import MonthLocator,    DateFormatter
            From matplotlib. Ticker import FuncFormatter
            Def plot_curve (*curves):
                Fig,    ax = utils.Plot ()
                Dates = [ today+ql.Period (i,    ql. Weeks) for i in range (0,    52*5) ]
                For (c,    style) in curves:
                    valid_dates = [ d for d in dates if d >= c.referenceDate () ]
                    rates = [ c.forwardRate (d,    d+1,    ql. Actual 360 (),    ql. Simple). Rate ()
                              For d in valid_dates ]
                    Ax. Plot_date ([ to_datetime (d) for d in valid_dates ],    rates,    style)
                Ax. Set_xlim (to_datetime (min (dates)),    to_datetime (max (dates)))
                Ax. Xaxis. Set_major_locator (MonthLocator (bymonth=[6,   12]))
                Ax. Xaxis. Set_major_formatter (DateFormatter ("%b '%y"))
                Ax.Xaxis.Grid (True,    'major')
                Ax.Xaxis.Grid (False,    'minor')
                Ax. Yaxis. Set_major_formatter (FuncFormatter (lambda r,    pos: format_rate (r)))
\##### The statement of the case { #chap16 . xhtml\_leanpub-auto-the-statement-of-the-case} Let's say we have an interest-rate curve. For the sake of example,    I'll take a simple one bootstrapped on a few swap rates.
    In [3]: today = ql.Date (9,    ql. March,    2016)
            Ql.Settings.Instance (). EvaluationDate = today
    In [4]: helpers = [ ql.SwapRateHelper (ql.QuoteHandle (ql.SimpleQuote (rate/100.0)),   
                                          Ql.Period (*tenor),    ql.TARGET (),   
                                          Ql. Annual,    ql. Unadjusted,    
                                          Ql. Thirty 360 (),    
                                          Ql. Euribor 6 M ())
                        For tenor,    rate in [((6,    ql. Months),    0.201),   
                                            ((2,    ql. Years),    0.258),   
                                            ((5,    ql. Years),    0.464),   
                                            ((10,    ql. Years),    1.151),   
                                            ((15,    ql. Years),    1.588)] ]
            Curve = ql.PiecewiseLinearZero (0,    ql.TARGET (),    helpers,    ql. Actual 360 ())
    In [5]: plot_curve ((curve,    '-'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/implied_term_structures-5.png)
::: I'm using linear interpolation on the zero rates,    which isn't great for actual use. However,    the resulting jumps in the forward rates will be useful as visual points of reference; note,    for instance,    the jump around March 2018. The curve also implies an interest-rate curve in 1 year; meaning that,    for instance,    it can give us the forward rate between 1 and to 2 years,    that we expect to be the 1-year spot rate one year from now,    or the forward rate between 1 year and 18 months,    which will be the 6-months spot rate in one year. The implied curve can be built as an instance of the \`ImpliedTermStructure\` class:
    In [6]: future_reference = today + ql.Period (1,    ql. Years)
            Implied_curve = ql.ImpliedTermStructure (ql.YieldTermStructureHandle (curve),   
                                                    Future_reference)
    In [7]: plot_curve ((implied_curve,    '-'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/implied_term_structures-7.png)
::: In the common range,    the two curves are the same...
    In [8]: plot_curve ((curve,    '-'),    (implied_curve,    'o'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/implied_term_structures-8.png)
::: ... Although,    of course,    a spot rate for the implied curve corresponds to a forward rate for the original curve.
    In [9]: dates = [ future_reference + ql.Period (i,    ql. Years) for i in range (6) ]
            Rates_1 = [ curve.ForwardRate (future_reference,    d,   
                                          Ql. Actual 360 (),    ql. Continuous). Rate ()
                        For d in dates ]
            Rates_2 = [ implied_curve.ZeroRate (d,    ql. Actual 360 (),    ql. Continuous). Rate ()
                        For d in dates ]
            Pd.DataFrame (list (zip (dates,   
                                  [ format_rate (r) for r in rates_1 ],   
                                  [ format_rate (r) for r in rates_2 ])),   
                         Columns=('Maturity',    'Original forward rate',   
                                  'Implied zero rate'),    index=['']*6)
    Out[9]: 
  Maturity Original forward rate Implied zero rate --- ----------------- ----------------------- -------------------   March 9 th,    2017 0.25 % 0.25 %   March 9 th,    2018 0.29 % 0.29 %   March 9 th,    2019 0.37 % 0.37 %   March 9 th,    2020 0.45 % 0.45 %   March 9 th,    2021 0.52 % 0.52 %   March 9 th,    2022 0.67 % 0.67 % Now,    Lisa Ann's idea was to forecast a bond price as of one year from now based on the implied curve. In the library framework,    that means setting the evaluation date to 1 year from today and using the implied curve to discount the bond cash flows. However,    after changing the evaluation date...
    In [10]: ql.Settings.Instance (). EvaluationDate = future_reference
... The implied curve had changed.
    In [11]: rates_3 = [ implied_curve.ZeroRate (d,    ql. Actual 360 (),    ql. Continuous). Rate ()
                         For d in dates ]
             Pd.DataFrame (list (zip (dates,   
                                   [ format_rate (r) for r in rates_2 ],   
                                   [ format_rate (r) for r in rates_3 ])),   
                          Columns=('Maturity',    'Before date change',   
                                   'After date change'),    index=['']*6)
    Out[11]: 
  Maturity Before date change After date change --- ----------------- -------------------- -------------------   March 9 th,    2017 0.25 % 0.20 %   March 9 th,    2018 0.29 % 0.22 %   March 9 th,    2019 0.37 % 0.25 %   March 9 th,    2020 0.45 % 0.32 %   March 9 th,    2021 0.52 % 0.39 %   March 9 th,    2022 0.67 % 0.46 % ##### What happened? { #chap16 . xhtml\_leanpub-auto-what-happened} Simply put: the reference date of the original curve was specified relative to the evaluation date,    and when we moved it the curve moved,    too. Let's try it:
    In [12]: ql.Settings.Instance (). EvaluationDate = future_reference
             Plot_curve ((curve,    '-'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/implied_term_structures-12.png)
::: Remember that jump in March 2018? It's in March 2019 now. Thus,    after moving the evaluation date,    the original and implied curve are exactly the same; and the spot rates returned by the implied curve are no longer forward rates,    but the spot rates returned by the original curve.
    In [13]: rates_1 = [ curve.ZeroRate (d,    ql. Actual 360 (),    ql. Continuous). Rate ()
                         For d in dates ]
             Rates_2 = [ implied_curve.ZeroRate (d,    ql. Actual 360 (),    ql. Continuous). Rate ()
                         For d in dates ]
             Pd.DataFrame (list (zip (dates,   
                                   [ format_rate (r) for r in rates_1 ],   
                                   [ format_rate (r) for r in rates_2 ])),   
                          Columns=('Maturity',    'Original zero rate',   
                                   'Implied zero rate'),    index=['']*6)
    Out[13]: 
  Maturity Original zero rate Implied zero rate --- ----------------- -------------------- -------------------   March 9 th,    2017 0.20 % 0.20 %   March 9 th,    2018 0.22 % 0.22 %   March 9 th,    2019 0.25 % 0.25 %   March 9 th,    2020 0.32 % 0.32 %   March 9 th,    2021 0.39 % 0.39 %   March 9 th,    2022 0.46 % 0.46 % The solution would be to build the original curve so that it doesn't move when the evaluation date changes; and as you might remember,    the way to do that is to specify a reference date explicitly. Unfortunately,    though,    doing this to a bootstrapped curve is an open issue; even if we specified the reference date,    the underlying swaps would still move (it's a long story). Thus,    the actual solution will be a bit of a kludge: we'll make a frozen copy of the original curve that doesn't move when the evaluation date does. The way we do it is to return to the original evaluation date...
    In [14]: ql.Settings.Instance (). EvaluationDate = today
... Extract the bootstrapped rates...
    In [15]: curve.Nodes ()
    Out[15]: ((Date (9,   3,   2016),    0.001954693606572509),   
              (Date (12,   9,   2016),    0.001954693606572509),   
              (Date (12,   3,   2018),    0.002536800732553941),   
              (Date (11,   3,   2021),    0.004572804156623578),   
              (Date (11,   3,   2026),    0.011524783611804843),   
              (Date (11,   3,   2031),    0.01615156507336212))
... And create a curve with the same rates and a fixed reference date.
    In [16]: node_dates,    node_rates = zip (*curve.Nodes ())
             Frozen_curve = ql.ZeroCurve (node_dates,    node_rates,    curve.DayCounter ())
    In [17]: plot_curve ((frozen_curve,    '-'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/implied_term_structures-17.png)
::: As I said,    a bit of a kludge: this curve is a frozen copy,    and won't react to changes in the underlying quoted swap rates,    so you'd have to recreate it manually if you want to track the market as it moves. However,    now we can build the implied curve based on the frozen one:
    In [18]: implied_curve = ql.ImpliedTermStructure (
                 Ql.YieldTermStructureHandle (frozen_curve),   
                 Future_reference)
If we move the evaluation date,    the frozen curve remains fixed at today's date...
    In [19]: ql.Settings.Instance (). EvaluationDate = future_reference
             Plot_curve ((frozen_curve,   '-'),    (implied_curve,   'o'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/implied_term_structures-19.png)
::: ... And the implied curve returns the correct rates.
    In [20]: rates_1 = [ frozen_curve.ZeroRate (d,    ql. Actual 360 (),    ql. Continuous). Rate ()
                         For d in dates ]
             Rates_2 = [ frozen_curve.ForwardRate (future_reference,    d,   
                                                  Ql. Actual 360 (),    ql. Continuous). Rate ()
                         For d in dates ]
             Rates_3 = [ implied_curve.ZeroRate (d,    ql. Actual 360 (),    ql. Continuous). Rate ()
                         For d in dates ]
             Pd.DataFrame (list (zip (dates,   
                                   [ format_rate (r) for r in rates_1 ],   
                                   [ format_rate (r) for r in rates_2 ],   
                                   [ format_rate (r) for r in rates_3 ])),   
                          Columns=('Maturity',    'Original zero rate',   
                                   'Original forward rate',    'Implied zero rate'),   
                          Index=['']*6)
    Out[20]: 
  Maturity Original zero rate Original forward rate Implied zero rate --- ----------------- -------------------- ----------------------- -------------------   March 9 th,    2017 0.21 % 0.25 % 0.25 %   March 9 th,    2018 0.25 % 0.29 % 0.29 %   March 9 th,    2019 0.32 % 0.37 % 0.37 %   March 9 th,    2020 0.39 % 0.45 % 0.45 %   March 9 th,    2021 0.46 % 0.52 % 0.52 %   March 9 th,    2022 0.60 % 0.67 % 0.67 %
$$$${ #chap17 . xhtml}
\## $$13.$${. Section-number}Interest-rate sensitivities via zero spread { #chap17 . xhtml\_leanpub-auto-interest-rate-sensitivities-via-zero-spread} In this notebook,    I'll show a couple of different ways to calculate the sensitivity of an instrument price to changes in the interest-rate curve.
    In [1]: import QuantLib as ql
            Today = ql.Date (8,    ql. March,    2016)
            Ql.Settings.Instance (). EvaluationDate = today
    In [2]: %matplotlib inline
            From matplotlib. Ticker import FuncFormatter
            Import numpy as np
            Import utils
            From utils import format_rate
            Def plot_curves (*curves):
                Fig,    ax = utils.Plot ()
                Ax. Yaxis. Set_major_formatter (FuncFormatter (lambda r,    pos: format_rate (r)))
                Ax. Set_xlim (0,   15)
                Ax. Set_xticks ([0,   5,   10,   15])
                Times = np.Linspace (0.0,    15.0,    400)
                For curve,    style in curves:
                    Rates = [ curve.ZeroRate (t,    ql. Continuous). Rate () for t in times ]
                    Ax.Plot (times,    rates,    style)
            Def plot_curve (curve):
                Plot_curves ((curve,   '-'))
\##### Setup { #chap17 . xhtml\_leanpub-auto-setup-4} Let's say we have an interest-rate curve,    no matter how it was calculated. As an example,    I'll use a curve bootstrapped over the 6-months deposit,    a strip of 6-months FRAs and a number of swaps against the 6-months Euribor. All the market inputs are stored in quotes so that their values can be changed.
    In [3]: quotes = [ ql.SimpleQuote (0.312/100) ]
            Helpers = [
                Ql.DepositRateHelper (ql.QuoteHandle (quotes[0]),   
                                     Ql.Period (6,    ql. Months),    3,   
                                     Ql.TARGET (),    ql. Following,   
                                     False,    ql. Actual 360 ()) ]
            For rate,    months_to_start in [(0.293,    1),    (0.272,    2),    (0.260,    3),   
                                          (0.256,    4),    (0.252,    5),    (0.248,    6),   
                                          (0.254,    7),    (0.261,    8),    (0.267,    9),   
                                          (0.279,    10),    (0.291,    11),    (0.303,    12),   
                                          (0.318,    13),    (0.335,    14),    (0.352,    15),   
                                          (0.371,    16),    (0.389,    17),    (0.409,    18)]:
                Quotes.Append (ql.SimpleQuote (rate/100))
                Helpers.Append (ql.FraRateHelper (ql.QuoteHandle (quotes[-1]),   
                                                Months_to_start,    ql. Euribor 6 M ()))
            For rate,    tenor in [(0.424,    3),    (0.576,    4),    (0.762,    5),    (0.954,    6),   
                                (1.135,    7),    (1.303,    8),    (1.452,    9),    (1.584,    10),   
                                (1.809,    12),    (2.037,    15),    (2.187,    20),    (2.234,    25),   
                                (2.256,    30),    (2.295,    35),    (2.348,    40),    (2.421,    50),   
                                (2.463,    60)]:
                Quotes.Append (ql.SimpleQuote (rate/100))
                Helpers.Append (ql.SwapRateHelper (ql.QuoteHandle (quotes[-1]),   
                                                 Ql.Period (tenor,    ql. Years),    ql.TARGET (),   
                                                 Ql. Annual,    ql. Unadjusted,   
                                                 Ql. Thirty 360 (ql. Thirty 360. BondBasis),   
                                                 Ql. Euribor 6 M ()))
            Rate_curve = ql.PiecewiseLogCubicDiscount (2,    ql.TARGET (),   
                                                      Helpers,    ql. Actual 365 Fixed ())
            Curve_handle = ql.RelinkableYieldTermStructureHandle (rate_curve)
Here's the curve,    plotted over 15 years.
    In [4]: plot_curve (rate_curve)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/interest_rate_sensitivities_via_zero_spread-4.png)
::: For illustration purposes,    I'll be using the curve to price an interest-rate swap. Let's create a 12-years swap starting in one month,    with an annual schedule for the fixed leg and a semiannual schedule for the floating leg. We'll use the curve above to forecast the floating-rate fixings,    so we pass it to the \`Euribor 6 M\` instance that,    in turn,    we pass to the swap constructor.
    In [5]: fixed_schedule = ql.Schedule (
                Ql.Date (8,    ql. April,    2016),    ql.Date (8,    ql. April,    2028),   
                Ql.Period (1,    ql. Years),    ql.TARGET (),    ql. Following,    ql. Following,   
                Ql. DateGeneration. Forward,    False)
            Floating_schedule = ql.Schedule (
                Ql.Date (8,    ql. April,    2016),    ql.Date (8,    ql. April,    2028),   
                Ql.Period (6,    ql. Months),    ql.TARGET (),    ql. Following,    ql. Following,   
                Ql. DateGeneration. Forward,    False)
            Index = ql. Euribor 6 M (curve_handle)
            Swap = ql.VanillaSwap (ql. VanillaSwap. Payer,    10000.0,   
                                  Fixed_schedule,    0.02,    ql. Thirty 360 (),   
                                  Floating_schedule,    index,    0.0,    ql. Actual 360 ())
Of course,    we should use a different curve for discounting. But let me just skip that part for brevity,    and simply pass the same curve to the engine used by the swap. The points I'm going to make won't suffer for this. Once we've done this,    we can finally get the value of the swap.
    In [6]: swap.SetPricingEngine (ql.DiscountingSwapEngine (curve_handle))
            P 0 = swap.NPV ()
            Print (P 0)
    Out[6]: -189.83267948709272
Now,    let's say that this was you pricing a deal. And let's also say that you're interested (as you should) in how the swap price reacts to changes in the underlying rates. ##### Interest-rate sensitivities { #chap17 . xhtml\_leanpub-auto-interest-rate-sensitivities} If you're interested in the sensitivities of the price to the input rates,    you can have them: shift any input rate by setting a perturbed value to the corresponding quote and recalculate the NPV. For instance,    you can bump the 6-months deposit rate by one basis point and get the new price as follows:
    In [7]: bp = 1.0 e-4
            Ref = quotes[0]. Value ()
            Quotes[0]. SetValue (ref+1*bp)
            Print (swap.NPV ())
            Quotes[0]. SetValue (ref)
    Out[7]: -190.1069970119836
(Also,    don't forget to set the value back to the actual quoted rate when you're done). This can be done for a single rate,    as above,    or for any number of rates; all of them,    for instance...
    In [8]: for q in quotes:
                q.setValue (q.value ()+1*bp)
            Print (swap.NPV ())
            For q in quotes:
                q.setValue (q.value ()-1*bp)
    Out[8]: -178.68820577843826
... So the above gives you the swap price when all the input rates move 1 basis point upwards; the difference between the new price and the old one will give you the DV 01 of the swap. (Note that,    depending on how you define it,    you might want to shift either the forecast curve,    the discount curve,    or both.) Different combinations of changes can also give you different stress scenarios; for instance,    ones in which the curve tilts in some direction,    or ones in which you only move the short end or the long end of the curve. In doing so,    though,    you're constrained to use the nodes of the original curve. For instance,    in the curve above there are no nodes between 20 and 25 years,    thus there are no levers to pull in that interval. As an alternative,    you can take an approach in which you modify the curve as a whole independently of the underlying rates. For instance,    to shift all the zero rates upwards,    you can keep the original curve as it is and add one basis point to all its zero rates by means of the \`ZeroSpreadedTermStructure\` class. To use it for pricing our swap,    we'll store the original curve in a separate handle,    add the spread,    and link the new curve to the handle we're using for forecasting. As usual,    the swap price will react accordingly.
    In [9]: base_curve = ql.YieldTermStructureHandle (rate_curve)
            Spread = ql.SimpleQuote (1*bp)
            Curve_handle.LinkTo (
                Ql.ZeroSpreadedTermStructure (base_curve,    ql.QuoteHandle (spread)))
            Print (swap.NPV ())
    Out[9]: -178.8676404436867
As we could expect,    the result is close to what we got by shifting all the input rates (the difference is just one or two digits in the first decimal place) but not quite the same: modifying,    say,    an input swap rate doesn't have the same effect as applying the same change to the zero rates directly. As usual,    I'll trust you to know what you're doing in either case. To get a more visual idea of what we're doing,    we can also increase the spread and plot the resulting curve on top of the original one:
    In [10]: spread.SetValue (5*bp)
             Plot_curves ((rate_curve,   '-'),    (curve_handle,   '--'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/interest_rate_sensitivities_via_zero_spread-10.png)
::: Another class,    \`SpreadedLinearZeroInterpolatedTermStructure\` (for whose name I apologize on behalf of the library developers: I don't know what came over us) allows one to apply a spread which is interpolated linearly between a set of nodes,    which of course are independent of the nodes of the underlying curve. For instance,    we can create a scenario in which we tilt the curve by taking equally spaced dates each year between now and 20 years,    and define the corresponding spreads as negative in the short end,    increasing until they reach zero at the 7-years mark,    and more and more positive in the long end. Again,    we can plot the resulting curve for comparison with the original one...
    In [11]: spot = rate_curve.ReferenceDate ()
             Dates = [ spot + ql.Period (n,    ql. Years) for n in range (21)]
             Spreads = [ ql.QuoteHandle (ql.SimpleQuote ((n-7)*bp))  for n in range (21) ]
             Curve_handle.LinkTo (
                 Ql.SpreadedLinearZeroInterpolatedTermStructure (base_curve,   
                                                                Spreads,    dates))
             Plot_curves ((rate_curve,   '-'),    (curve_handle,   '--'))
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/interest_rate_sensitivities_via_zero_spread-11.png)
::: ... And again,    we can ask the swap for its price under this scenario.
    In [12]: print (swap.NPV ())
    Out[12]: -138.69485276964178
When using this technique,    going back to the actual market quotes simply means linking the curve handle to the original curve:
    In [13]: curve_handle.LinkTo (rate_curve)
             Print (swap.NPV ())
    Out[13]: -189.83267949204492
If you want more control of the shift (as asked,    for instance,    by user 6142489 $$on \*Stack Overflow\*$$( https://stackoverflow.com/questions/46279785/quantlib-building-key-rate-risks ) who wanted to calculate key-rate risks) you might have to increase the number of nodes. If your nodes are one year apart as above,    and if you modify,    e.g.,    the node at 7 years,    the interpolation scheme will cause the whole range between 6 and 8 years to change,    and all coupons paid in that period to be affected. The more nodes you have and the closer they are together,    the more localized any change will be.
$$$${ #chap18 . xhtml}
\## $$14.$${. Section-number}A glitch in forward-rate curves { #chap18 . xhtml\_leanpub-auto-a-glitch-in-forward-rate-curves} (Based on $$a question asked by Boris Chow$$( https://sourceforge.net/p/quantlib/mailman/message/34286980/ ) on the QuantLib mailing list. Thanks!)
    In [1]: %matplotlib inline
            From pandas import DataFrame
            Import numpy as np
            Import utils
    In [2]: import QuantLib as ql
    In [3]: today = ql.Date (24,    ql. August,    2015)
            Ql.Settings.Instance (). EvaluationDate = today
\##### The statement of the case { #chap18 . xhtml\_leanpub-auto-the-statement-of-the-case-1} Let's say we have built an interpolated forward-rate curve,    by which I mean that it interpolates instantaneous forward rates (for more details,    read my other book). We're using a backward-flat interpolation,    which corresponds to log-linear discount factors. The dates and forwards are entirely made up; they are just for show.
    In [4]: dates = [ today ] + [ today + ql.Period (i,    ql. Years)
                                  For i in [1,    2,    3,    5,    10,    20] ]
            Forwards = [ 0.01,    0.03,    0.02,    0.025,    0.035,    0.05,    0.04 ]
            Curve = ql.ForwardCurve (dates,    forwards,    ql. Actual 360 ())
We can ask the curve for its nodes,    and it will return those we expect---that is,    those we passed ourselves...
    In [5]: DataFrame (list (curve.Nodes ()),   
                      Columns = ('date',   'rate'),   
                      Index = ['']*len (dates))
    Out[5]: 
  Date rate --- ------------------- -------   August 24 th,    2015 0.010   August 24 th,    2016 0.030   August 24 th,    2017 0.020   August 24 th,    2018 0.025   August 24 th,    2020 0.035   August 24 th,    2025 0.050   August 24 th,    2035 0.040 ... And if we retrieve the instantaneous forward from a date between the nodes,    it's the same as that of the following node,    as expected for a backward-flat interpolation.
    In [6]: d = today + ql.Period (4,    ql. Years)
            Print (d)
            Print (curve.ForwardRate (d,    d,    curve.DayCounter (),    ql. Continuous))
    Out[6]: August 24 th,    2019
            3.500000 % Actual/360 continuous compounding
We can even plot the whole thing and get the expected shape.
    In [7]: sample_times = np.Linspace (0.0,    20.0,    401)
            Sample_rates = [ curve.ForwardRate (t,    t,    ql. Continuous). Rate ()
                             For t in sample_times ]
            F,    ax = utils.Plot ()
            Ax. Set_ylim (0.0,   0.06)
            Ax. Yaxis. Set_major_formatter (utils. Rate_formatter ())
            Ax.Plot (sample_times,    sample_rates);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/a_glitch_in_forward_curves-7.png)
::: So it seems all is well with the world. What if we retrieve the instantaneous forward rates at the curve nodes,    though?
    In [8]: dates,    expected = zip (*curve.Nodes ())
            Rates = [ curve.ForwardRate (d,    d,    curve.DayCounter (),    ql. Continuous). Rate ()
                      For d in dates]
            DataFrame (list (zip (dates,    expected,    rates)),   
                      Columns = ('date',   'expected',   'retrieved'),   
                      Index = ['']*len (dates))
    Out[8]: 
  Date expected retrieved --- ------------------- ---------- -----------   August 24 th,    2015 0.010 0.0300   August 24 th,    2016 0.030 0.0250   August 24 th,    2017 0.020 0.0225   August 24 th,    2018 0.025 0.0300   August 24 th,    2020 0.035 0.0425   August 24 th,    2025 0.050 0.0450   August 24 th,    2035 0.040 0.0400 Here are the above points,    together with the rest of the curve.
    In [9]: node_times = [ curve.DayCounter (). YearFraction (today,    d) for d in dates ]
            Ax.Plot (node_times,    rates,    'o',    markersize=8)
            Display (f)
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/a_glitch_in_forward_curves-9.png)
::: ##### What's wrong? { #chap18 . xhtml\_leanpub-auto-whats-wrong} It's a combination of two things. First,    the particular interpolation we've chosen causes the instantaneous forwards to be discontinuous at the nodes. Second,    there's a limitation in the implementation of the base \`TermStructure\` class: the instantaneous forwards are not taken directly from the interpolation,    but retrieved generically from the discount factors as the forward over a small interval around the given time; that is,    !$$\\\\tilde{f}(t) = \\\\frac{1}{2 \\\\delta t} \\\\log\\\\left (\\\\frac{B (t-\\\\delta t)}{B (t+\\\\delta t)}\\\\right)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_39. Png){. Block-equation width="215"} Again,    the details are in my other book. By writing the discount factors !$$B (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_40. Png){. Inline-equation width="33"} in terms of the zero rates as !$$\\\\exp\\\\left (Z (t) \\\\cdot t \\\\right)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_41. Png){. Inline-equation width="97"},    and in turn the zero rates in terms of the instantaneous forwards as !$$Z (t) = \\\\displaystyle{\\\\int\_0\\^t f (\\\\tau) d\\\\tau}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_42. Png){. Inline-equation width="139"},    the above simplifies (well,    for some value of "simplifies") to !$$\\\\tilde{f}(t) = \\\\frac{1}{2 \\\\delta t} \\\\left\\$$\\\\int\_0\\^{t+\\\\delta t} f (\\\\tau) d\\\\tau - \\\\int\_0\\^{t-\\\\delta t} f (\\\\tau) d\\\\tau \\\\right\\$$$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_43. Png){. Block-equation width="332"} We can interpret the above expression in two ways; both explain why the values at the nodes are off and why we get the correct values elsewhere. As the difference of two integrals,    it equals !$$\\\\frac{1}{2 \\\\delta t} \\\\left\\$$\\\\int\\\_{t-\\\\delta t}\\^{t+\\\\delta t} f (\\\\tau) d\\\\tau \\\\right\\$$$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_44. Png){. Block-equation width="148"} that is,    the average of !$$f (\\\\tau)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_45. Png){. Inline-equation width="32"} between !$$t-\\\\delta t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_46. Png){. Inline-equation width="44"} and !$$t+\\\\delta t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_47. Png){. Inline-equation width="43"}. What this means is clear from the following figure: off the nodes,    the result equals the flat value of the forwards; at the nodes,    though,    it equals the average between the two adjacent levels. ::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/a_glitch_in_forward_curves-integral.png)
::: If we consider the integral !$$\\\\displaystyle{\\\\int\_0\\^t f (\\\\tau) d\\\\tau}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_48. Png){. Inline-equation width="80"} as a function !$$F (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_49. Png){. Inline-equation width="32"} instead,    !$$\\\\tilde{f}(t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_50. Png){. Inline-equation width="29"} equals !$$\\\\displaystyle{\\\\frac{F (t+\\\\delta t)-F (t-\\\\delta t)}{2 \\\\delta t}}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_51. Png){. Inline-equation width="169"}; that is,    the numerical derivative of !$$F$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_52. Png){. Inline-equation width="13"} at !$$t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_53. Png){. Inline-equation width="5"}. Again,    a figure shows clearly what happens at and off the nodes: the forwards are piecewise flat,    their integral is piecewise linear with slopes equal to the forwards,    and the derivative at a given node is in between the two joining slopes. ::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/a_glitch_in_forward_curves-derivative.png)
::: ##### Is the curve wrong,    then? { #chap18 . xhtml\_leanpub-auto-is-the-curve-wrong-then} Yes and no. The glitch above is real,    but discount factors and discrete rates are retrieved correctly so there's no problem using the curve (unless the value of an instrument depends on instantaneous forwards,    but that's unlikely). If the above troubles you,    though,    what you can do is simply to choose another interpolation that doesn't cause discontinuities.
$$$${ #chap19 . xhtml}
\# Interest-rate models { #chap19 . xhtml\_leanpub-auto-interest-rate-models}
$$$${ #chap20 . xhtml}
\## $$15.$${. Section-number}Simulating interest rates using Hull White model { #chap20 . xhtml\_leanpub-auto-simulating-interest-rates-using-hull-white-model} The Hull-White Short Rate Model is defined as: !$$dr\_t = (\\\\theta (t) - a r\_t) dt + \\\\sigma dW\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_54. Png){. Block-equation width="218"} where !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_55. Png){. Inline-equation width="8"} and !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_56. Png){. Inline-equation width="9"} are constants,    and !$$\\\\theta (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_57. Png){. Inline-equation width="27"} is chosen in order to fit the input term structure of interest rates. Here we use QuantLib to show how to simulate the Hull-White model and investigate some of the properties. We import the libraries and set things up as shown below:
    In [1]: import QuantLib as ql
            Import utils
            Import numpy as np
            %matplotlib inline
The constants that we use for this example is all defined as shown below. Variables \`sigma\` and \`a\` are the constants that define the Hull-White model. In the simulation,    we discretize the time span of \`length\` 30 years into 360 intervals (one per month) as defined by the \`timestep\` variable. For simplicity we will use a constant forward rate term structure as an input. It is straight forward to swap with another term structure here.
    In [2]: sigma = 0.1
            A = 0.1
            Timestep = 360
            Length = 30 # in years
            Forward_rate = 0.05
            Day_count = ql. Thirty 360 ()
            Todays_date = ql.Date (15,    1,    2015)
    In [3]: ql.Settings.Instance (). EvaluationDate = todays_date
            Spot_curve = ql.FlatForward (todays_date,   
                                        Ql.QuoteHandle (ql.SimpleQuote (forward_rate)),   
                                        Day_count)
            Spot_curve_handle = ql.YieldTermStructureHandle (spot_curve)
    In [4]: hw_process = ql.HullWhiteProcess (spot_curve_handle,    a,    sigma)
            Rng = ql.GaussianRandomSequenceGenerator (
                Ql.UniformRandomSequenceGenerator (timestep,    ql.UniformRandomGenerator ()))
            Seq = ql.GaussianPathGenerator (hw_process,    length,    timestep,    rng,    False)
The Hull-White process is constructed by passing the term-structure,    \`a\` and \`sigma\`. To create the path generator,    one has to provide a random sequence generator along with other simulation inputs such as \`timestep\` and \\\`length. A function to generate paths can be written as shown below:
    In [5]: def generate_paths (num_paths,    timestep):
                Arr = np.Zeros ((num_paths,    timestep+1))
                For i in range (num_paths):
                    Sample_path = seq.Next ()
                    Path = sample_path.Value ()
                    Time = [path.Time (j) for j in range (len (path))]
                    Value = [path[j] for j in range (len (path))]
                    Arr[i,    :] = np.Array (value)
                Return np.Array (time),    arr
The simulation of the short rates look as shown below:
    In [6]: num_paths = 10
            Time,    paths = generate_paths (num_paths,    timestep)
            Fig,    ax = utils.Plot ()
            For i in range (num_paths):
                Ax.Plot (time,    paths[i,    :],    lw=0.8,    alpha=0.6)
            Ax. Set_title ("Hull-White Short Rate Simulation");
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/hull_white_simulations-6.png)
::: The short rate !$$r (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_58. Png){. Inline-equation width="27"} is given a distribution with the properties: !$$\\\\begin{eqnarray} E\\\\{r (t) \\| F\_s\\\\} &=& r (s) e\\^{-a (t-s)} + \\\\alpha (t) - \\\\alpha (s) e\\^{-a (t-s)} \\\\\\\\ Var\\\\{ r (t) \\| F\_s \\\\} &=& \\\\frac{\\\\sigma\\^2}{2 a} \\$$1 - e\\^{-2 a (t-s)}\\$$ \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_59. Png){. Block-equation width="506"} where !$$\\\\alpha (t) = f\\^M (0,    t) + \\\\frac{\\\\sigma\\^2} {2 a\\^2}(1-e\\^{-at})\\^2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_60. Png){. Block-equation width="256"} as shown in Brigo & Mercurio's book on Interest Rate Models.
    In [7]: num_paths = 1000
            Time,    paths = generate_paths (num_paths,    timestep)
The mean and variance compared between the simulation (red dotted line) and theory (blue line).
    In [8]: vol = [np.Var (paths[:,    i]) for i in range (timestep+1)]
            Fig,    ax = utils.Plot ()
            Ax.Plot (time,    vol,    "-.",    lw=3,    alpha=0.6)
            Ax.Plot (time,    sigma*sigma/(2*a)*(1.0-np.Exp (-2.0*a*np.Array (time))),    "-",   
                    Lw=2,    alpha=0.5)
            Ax. Set_title ("Variance of Short Rates",    size=14);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/hull_white_simulations-8.png)
:::
    In [9]: def alpha (forward,    sigma,    a,    t):
                Return forward + 0.5* np.Power (sigma/a*(1.0 - np.Exp (-a*t)),    2)
            Avg = [np.Mean (paths[:,    i]) for i in range (timestep+1)]
            Fig,    ax = utils.Plot ()
            Ax.Plot (time,    avg,    "-.",    lw=3,    alpha=0.6)
            Ax.Plot (time,   alpha (forward_rate,    sigma,    a,    time),    "-",    lw=2,    alpha=0.6)
            Ax. Set_title ("Mean of Short Rates",    size=14);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/hull_white_simulations-9.png)
:::
$$$${ #chap21 . xhtml}
\## $$16.$${. Section-number}Thoughts on the convergence of Hull-White model Monte Carlo simulations { #chap21 . xhtml\_leanpub-auto-thoughts-on-the-convergence-of-hull-white-model-monte-carlo-simulations} I had recently written an introductory post on $$simulating short rates in the Hull-White Model$$( http://gouthamanbalaraman.com/blog/hull-white-simulation-quantlib-python.html ). This $$question on the QuantLib forum$$( http://quantlib0.\1.n7.nabble.com/Matching-results-between-HW-tree-and-simulation-models-td16399.html ) raised some interesting questions on the convergence of the Hull-White model simulations. In this post,    I discuss the convergence of Monte Carlo simulations using the Hull-White model. The Hull-White Short Rate Model is defined as: !$$dr\_t = (\\\\theta (t) - a r\_t) dt + \\\\sigma dW\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_61. Png){. Block-equation width="218"} where !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_62. Png){. Inline-equation width="8"} and !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_63. Png){. Inline-equation width="9"} are constants,    and !$$\\\\theta (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_64. Png){. Inline-equation width="27"} is chosen in order to fit the input term structure of interest rates. Here we use QuantLib to show how to simulate the Hull-White model and investigate some of the properties. The variables used in this post are described below: - \`timestep\` is the number of steps used to discretize the time grid - \`hw\_process\` the object that defines the Hull-White process,    - \`length\` is the time span of the simulation in years - \`low\_discrepancy\` is a boolean variable that is used to chose Sobol low discrepancy random or not - \`brownian\_bridge\` is a boolean that chooses brownian bridge for path generation - \`num\_paths\` is the number of paths in the simulation - \`a\` is the constant parameter in the Hull-White model - \`sigma\` is the constant parameter !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_65. Png){. Inline-equation width="9"} in the Hull-White model that describes volatility
    In [1]: import QuantLib as ql
            Import matplotlib. Pyplot as plt
            Import numpy as np
            From scipy. Integrate import simps,    cumtrapz,    romb
            %matplotlib inline
            Import math
            Import utils
            Todays_date = ql.Date (15,    1,    2015)
            Ql.Settings.Instance (). EvaluationDate = todays_date
The \`get\_path\_generator\` function creates the a path generator. This function takes various inputs such as
    In [2]: def get_path_generator (timestep,    hw_process,    length,    
                                   Low_discrepancy=False,    brownian_bridge=True):
                """
                Returns a path generator
                """
                If low_discrepancy:
                    Usg = ql.UniformLowDiscrepancySequenceGenerator (timestep)
                    Rng = ql.GaussianLowDiscrepancySequenceGenerator (usg)
                    Seq = ql.GaussianSobolPathGenerator (
                            Hw_process,    length,    timestep,    rng,    brownian_bridge)
                Else:
                    Usg = ql.UniformRandomSequenceGenerator (timestep,   
                                                            Ql.UniformRandomGenerator ())
                    Rng = ql.GaussianRandomSequenceGenerator (usg)
                    Seq = ql.GaussianPathGenerator (
                            Hw_process,    length,    timestep,    rng,    brownian_bridge)
                Return seq
The \`generate\_paths\` function uses the generic path generator produced by the \`get\_path\_generator\` function to return a tuple of the array of the points in the time grid and a matrix of the short rates generated.
    In [3]: def generate_paths (num_paths,    timestep,    seq):
                Arr = np.Zeros ((num_paths,    timestep+1))
                For i in range (num_paths):
                    Sample_path = seq.Next ()
                    Path = sample_path.Value ()
                    Time = [path.Time (j) for j in range (len (path))]
                    Value = [path[j] for j in range (len (path))]
                    Arr[i,    :] = np.Array (value)
                Return np.Array (time),    arr
The \`generate\_paths\_zero\_price\` essentially is a wrapper around \`generate\_path\_generator\` and \`generate\_paths\` taking all the required raw inputs. This function returns the average of zero prices from all the paths for different points in time. I wrote this out so that I can conveniently change all the required inputs and easily plot the results.
    In [4]: def generate_paths_zero_price (spot_curve_handle,    a,    sigma,   
                                          Timestep,    length,    
                                          Num_paths,    avg_grid_array,   
                                          Low_discrepancy=False,    
                                          Brownian_bridge=True):
                """
                This function returns a tuple (T_array,    F_array),    where T_array
                Is the array of points in the time grid,    and F_array is the array
                Of the average of zero prices observed from the simulation.
                """
                Hw_process = ql.HullWhiteProcess (spot_curve_handle,    a,    sigma)
                Seq = get_path_generator (
                        Timestep,    hw_process,    length,    low_discrepancy,    brownian_bridge
                )
                Time,    paths = generate_paths (num_paths,    timestep,    seq)
                Avgs = [(time[j],    (np.Mean ([math.Exp (-simps (paths[i][0: j],    time[0: j])) 
                                           For i in range (num_paths)]))) 
                        For j in avg_grid_array
                        ]
                Return zip (*avgs)
            Def generate_paths_discount_factors (spot_curve_handle,    a,    sigma,   
                                                Timestep,    length,   
                                                Num_paths,    avg_grid_array,   
                                                Low_discrepancy=False,   
                                                Brownian_bridge=True):
                """
                This function returns a tuple (T_array,    S_matrix),    where T_array
                Is the array of points in the time grid,    and S_matrix is the matrix
                Of the spot rates for each path in the different points in the time grid.
                """
                Hw_process = ql.HullWhiteProcess (spot_curve_handle,    a,    sigma)
                Seq = get_path_generator (
                        Timestep,    hw_process,    length,    low_discrepancy,    brownian_bridge
                )
                Time,    paths = generate_paths (num_paths,    timestep,    seq)
                Arr = np.Zeros ((num_paths,    len (avg_grid_array)))
                For i in range (num_paths):
                    Arr[i,    :] =  [np.Exp (-simps (paths[i][0: j],    time[0: j]))
                                  For j in avg_grid_array ]
                T_array = [time[j] for j in avg_grid_array]
                Return t_array,    arr
            Def V (t,    T,    a,    sigma):
                """ Variance of the integral of short rates,    used below"""
                Return sigma*sigma/a/a*(T-t + 2.0/a*math.Exp (-a*(T-t)) - 
                                        1.0/(2.0*a)*math.Exp (-2.0*a*(T-t)) - 3.0/(2.0*a))
$$$${ #chap22 . xhtml}
\### Factors affecting the convergence { #chap22 . xhtml\_leanpub-auto-factors-affecting-the-convergence} In order to understand the convergence of Monte Carlo for the Hull-White model,    let us compare the market discount factor,    !$$P\\^M (t,    T) = \\\\exp\\\\left (-\\\\int\_t\\^Tf\\^{M} (t,    u) du\\\\right)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_66. Png){. Block-equation width="284"} with the expectation of the discount factors from the sample of Monte Carlo paths,    !$$P\\^{MC}(t,    T) = E\_t\\\\left\\\\{ e\\^{-\\\\int\_t\\^T r\\^{MC}(u) du} \\\\right\\\\}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_67. Png){. Inline-equation width="252"}. Here !$$f\\^{M}(t,    T)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_68. Png){. Inline-equation width="65"} is the instantaneous forward rate implied by the market,    and !$$r\\^{MC}(s)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_69. Png){. Inline-equation width="54"} is the instantaneous short rate from the Monte Carlo simulations. The error in the Monte Carlo simulation can be defined as: !$$\\\\epsilon (T) = P\\^M (0,    T) - P\\^{MC}(0,    T)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_70. Png){. Block-equation width="238"} As a first step,    let us look at the plots of !$$\\\\epsilon (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_71. Png){. Inline-equation width="25"} for different values of !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_72. Png){. Inline-equation width="8"} and !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_73. Png){. Inline-equation width="9"}.
    In [5]: # Here we vary sigma with fixed a and observe the error epsilon
            # define constants 
            Num_paths = 500
            Sigma_array = np.Arange (0.01,   0.1,   0.03)
            A = 0.1
            Timestep = 180
            Length = 15 # in years
            Forward_rate = 0.05
            Day_count = ql. Thirty 360 ()
            Avg_grid_array = np.Arange (12,    timestep+1,    12)
            # generate spot curve
            Spot_curve = ql.FlatForward (
                Todays_date,    
                Ql.QuoteHandle (ql.SimpleQuote (forward_rate)),    day_count
            )
            Spot_curve_handle = ql.YieldTermStructureHandle (spot_curve)
            #initialize plots
            Figure,    axis = utils.Plot ()
            Plots = []
            Zero_price_theory = np.Array (
                [spot_curve.Discount (j*float (length)/float (timestep))
                 For j in avg_grid_array])
            For sigma in sigma_array:
                Term,    zero_price_empirical = generate_paths_zero_price (
                    Spot_curve_handle,    a,    sigma,    timestep,    length,    num_paths,   
                    Avg_grid_array
                )
                Plots += axis.Plot (
                    Term,    np.Abs (zero_price_theory - np.Array (zero_price_empirical)),   
                    Lw=2,    alpha=0.6,    
                    Label="$\sigma=%. 2 f$"%sigma
                )
            # plot legend
            labels = [p.get_label () for p in plots]
            Legend = axis.Legend (plots,    labels,    loc=0)
            Axis. Set_xlabel ("T (years)",    size=12)
            Axis. Set_ylabel ("|$\epsilon (T)$|",    size=12)
            Axis. Set_title ("Discount Factor Error for $a=$%0.2 f and Varying $\sigma$"%a,   
                           Size=14);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/hull_white_monte_carlo_convergence-5.png)
::: The above plot illustrates that for !$$\\\\sigma=0.01$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_74. Png){. Inline-equation width="66"},    the Monte Carlo model shows good convergence,    and the convergence gradually deteriorates as !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_75. Png){. Inline-equation width="9"} increases and approaches !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_76. Png){. Inline-equation width="8"}.
    In [6]: # Here we vary a with fixed sigma and observe the error epsilon
            #define constants
            Num_paths = 500
            Sigma = 0.1
            A_array = np.Arange (0.1,    0.51,    0.1)
            Timestep = 180
            Length = 15 # in years
            Forward_rate = 0.05
            Day_count = ql. Thirty 360 ()
            Avg_grid_array = np.Arange (12,    timestep+1,    12)
            # generate spot curve
            Spot_curve = ql.FlatForward (
                Todays_date,   
                Ql.QuoteHandle (ql.SimpleQuote (forward_rate)),    day_count
            )
            Spot_curve_handle = ql.YieldTermStructureHandle (spot_curve)
            #initialize plots
            Figure,    axis = utils.Plot ()
            Plots = []
            Zero_price_theory = np.Array (
                [spot_curve.Discount (j*float (length)/float (timestep)) 
                 For j in avg_grid_array])
            For a in a_array:
                Term,    zero_price_empirical = generate_paths_zero_price (
                    Spot_curve_handle,    a,    sigma,    timestep,    length,    num_paths,   
                    Avg_grid_array
                )
                Plots += axis.Plot (
                    Term,   np.Abs (zero_price_theory - np.Array (zero_price_empirical)),     
                    Lw=2,    alpha=0.6,    
                    Label="$a=%. 2 f$"%a
                )
            # plot legend
            labels = [p.get_label () for p in plots]
            Legend =axis.Legend (plots,    labels,    loc=0)
            Axis. Set_xlabel ("T (years)",    size=12)
            Axis. Set_ylabel ("|$\epsilon (T)$|",    size=12)
            Axis. Set_title (
                "Discount Factor Error for $\sigma$=%0.2 f and Varying $a$"%sigma,   
                Size=14);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/hull_white_monte_carlo_convergence-6.png)
::: The above plot illustrates that for !$$a=0.1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_77. Png){. Inline-equation width="55"} the convergence of Monte Carlo is poor,    and it gradually improves as !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_78. Png){. Inline-equation width="8"} increases more than !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_79. Png){. Inline-equation width="9"}. From the plots above,    we observe that the convergence is good if the ratio !$$\\\\sigma/a \\< 1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_80. Png){. Inline-equation width="61"},    and the convergence deteriorates as the ratio !$$\\\\sigma/a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_81. Png){. Inline-equation width="28"} increases above unity. Now,    let us try to formalize this observation from the theoretical footing of the Hull-White model.
$$$${ #chap23 . xhtml}
\### Distribution of Discount Factors { #chap23 . xhtml\_leanpub-auto-distribution-of-discount-factors} The Monte Carlo approach estimates the market discount factor as the expectation of discount factors from each Monte Carlo path. If distribution of discount factors has a standard deviation !$$\\\\sigma\_D$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_82. Png){. Inline-equation width="20"},    then the error in our estimate of !$$P\\^{MC}(t,    T)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_83. Png){. Inline-equation width="79"} on using !$$N$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_84. Png){. Inline-equation width="15"} paths will be of the order of: !$$\\\\epsilon (t,    T) \\\\approx \\\\frac{\\\\sigma\_D}{\\\\sqrt (N)}.$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_85. Png){. Block-equation width="130"} In other words,    there are two factors at play in our Monte Carlo estimate,    the number of Monte Carlo paths !$$N$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_86. Png){. Inline-equation width="15"} and the standard deviation of the distribution of discount factors !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_87. Png){. Inline-equation width="9"}. Using more Monte Carlo paths will lead to improved convergence. But at the same time,    the !$$\\\\sigma\_D$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_88. Png){. Inline-equation width="20"} has to be relatively small for us to get a good estimate. The integral of short rates can be shown to be normally distributed (refer Brigo-Mercurio,    second edition page 75),    and is given as !$$\\\\int\_t\\^T r (u) du \\| \\\\mathcal{F}\\\_t \\\\sim \\\\mathcal{N}\\\\left (B (t,    T)\\$$r (t)-\\\\alpha (t)\\$$ + \\\\ln\\\\frac{P\\^M (0,    t)}{P\\^M (0,    T)} + \\\\frac{1}{2}\\$$V (0,    T) - V (0,    t)\\$$,    V (t,    T)\\\\right)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_89. Png){. Block-equation width="695"} where,    !$$\\\\begin{eqnarray} B (t,    T) &=& \\\\frac{1}{a} \\\\left\\$$1 - e\\^{-a (T-t)}\\\\right\\$$ \\\\\\\\ V (t,    T) &=& \\\\frac{\\\\sigma\\^2}{a\\^2}\\\\left\\$$T - t + \\\\frac{2}{a}e\\^{-a (T-t)} - \\\\frac{1}{2 a}e\\^{-2 a (T-t)} - \\\\frac{3}{2 a}\\\\right\\$$ \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_90. Png){. Block-equation width="524"} Based on this result,    the discount factor from the Monte Carlo simulation of short rates !$$P\\^{MC}(t,    T) = \\\\exp\\\\left (- \\\\int\_t\\^T r (u) du \\| \\\\mathcal{F}\\\_t \\\\right)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_91. Png){. Block-equation width="287"} will have a log-normal distribution with a standard deviation !$$\\\\sigma\_D (t,    T) = P\\^M (t,    T)\\\\sqrt{e\\^{V (t,    T)} -1 }$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_92. Png){. Block-equation width="259"} This result follows from the fact that if !$$X$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_93. Png){. Inline-equation width="15"} is a random process with a normal distribution having mean !$$\\\\mu$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_94. Png){. Inline-equation width="10"} and standard deviation !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_95. Png){. Inline-equation width="9"},    then $$log-normal distribution$$( http://en.wikipedia.org/wiki/Log-normal\_distribution ) !$$Y=e\\^X$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_96. Png){. Inline-equation width="58"} will satisfy: !$$\\\\begin{eqnarray} E (Y) &=& e\\^{\\\\mu+\\\\sigma\\^2/2}\\\\\\\\ Var (Y) &=& (e\\^{\\\\sigma\\^2} -1 ) E (Y)\\^2 \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_97. Png){. Block-equation width="415"}
    In [7]: #define constants
            Num_paths = 500
            Sigma = 0.02
            A = 0.1
            Timestep = 180
            Length = 15 # in years
            Forward_rate = 0.05
            Day_count = ql. Thirty 360 ()
            Avg_grid_array = np.Arange (1,    timestep+1,    12)
            # generate spot curve
            Spot_curve = ql.FlatForward (
                Todays_date,   
                Ql.QuoteHandle (ql.SimpleQuote (forward_rate)),    day_count
            )
            Spot_curve_handle = ql.YieldTermStructureHandle (spot_curve)
            Term,    discount_factor_matrix = generate_paths_discount_factors (
                    Spot_curve_handle,    a,    sigma,    timestep,    length,    num_paths,   
                    Avg_grid_array
                )
            Fig,    axis = utils.Plot ()
            Vol = [np.Var (discount_factor_matrix[:,    i]) for i in range (len (term))]
            L 1 = axis.Plot (term,    100*np.Sqrt (vol),   "-",    lw=2,    alpha=0.6,    label="Empirical")
            Vol_theory = [100*np.Sqrt (math.Exp (V (0,    T,    a,    sigma))-1.0) * 
                          Spot_curve_handle.Discount (T) for T in term]
            L 2 = axis.Plot (term,    vol_theory,   "--",    lw=2,    alpha=0.6,    label="Theory")
            Plots = l 1+l 2
            labels = [p.get_label () for p in plots]
            Legend =plt.Legend (plots,    labels,    loc=0)
            Axis. Set_xlabel ("Time (Years)",    size=12)
            Axis. Set_ylabel ("$\sigma_D (0,    T)$ (%)",    size=12)
            Axis. Set_title ("Standard Deviation of Discount Factors "
                           " (a=%0.2 f,    $\sigma$=%0.2 f)"%(a,    sigma),    size=14);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/hull_white_monte_carlo_convergence-7.png)
::: The plot above compares the standard deviation of the discount factors !$$\\\\sigma\_D$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_98. Png){. Inline-equation width="20"} from the closed form expression with a Monte Carlo estimate. The empirical estimate is in agreement with the theoretical expectation. We can estimate the value of !$$\\\\sigma\_D$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_99. Png){. Inline-equation width="20"} for the asymptotic limit of !$$T\\\\rightarrow\\\\infty$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_100. Png){. Inline-equation width="59"}: !$$\\\\sigma\_D (0,    T) \\\\approx P\\^M (0,    T) e\\^{f\\^M (0,    T)/a-\\\\sigma\\^2/(4 a\\^3)}\\\\sqrt{e\\^{\\\\sigma\\^2 T/a\\^2} - 1}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_101. Png){. Block-equation width="404"} The exponential term,    !$$e\\^{\\\\sigma\\^2 T/a\\^2}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_102. Png){. Inline-equation width="50"},    can become very large when !$$\\\\sigma\\^2 T/a\\^2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_103. Png){. Inline-equation width="55"} grows above 1. Thus we can expect good convergence when !$$\\\\sigma\\^2 T/a\\^2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_104. Png){. Inline-equation width="55"} remains small or close to zero for the time !$$T$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_105. Png){. Inline-equation width="12"} of interest to us. The above result suggests that if the parameters !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_106. Png){. Inline-equation width="9"} and !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_107. Png){. Inline-equation width="8"} are not chosen carefully,    (i.e. !$$\\\\sigma/a \\>1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_108. Png){. Inline-equation width="61"}) then the convergence of the simulation would be poor and the results untrustworthy.
$$$${ #chap24 . xhtml}
\## $$17.$${. Section-number}Short interest rate model calibration { #chap24 . xhtml\_leanpub-auto-short-interest-rate-model-calibration} In the earlier chapters,    we have discussed simulating Hull-White model. That exercise gave a primer on how to use the model classes. There the model parameters were assumed to be given. However in practice,    the model parameters need to calibrated from market data. Typically instruments such as swaptions,    caps or floors and their market prices / volatilities are taken as inputs. Then the model parameters are fit in such a way that the model prices for these options are close enough. The goodness of fit depends,    apart from the choice of the numerical methods,    on the type of model itself. This is because models such as Hull-White 1 factor cannot fit some of the humped volatility term structures observed in the market. Never the less,    Hull-White is usually a good starting point to understand calibration process. Here we will discuss Hull-White model in detail. Then we will also show how the same procedure can be applied to calibrate other short rate models. We will assume the quotes to be at-the-money (ATM) log-normal volatilities. In the later section,    we will extend to normal volatilities.
    In [1]: import QuantLib as ql
            From collections import namedtuple
            Import math
            From pandas import DataFrame
            # This is for compatibility with QuantLib < 1.15
            Try:
                Ql. BlackCalibrationHelper
            Except:
                Ql. BlackCalibrationHelper = ql. CalibrationHelper
\##### Hull-White 1-Factor Model { #chap24 . xhtml\_leanpub-auto-hull-white-1-factor-model} Hull-White model was one of the first practical exogenous models that attempted to fit to the market interest rate term structures. The model is described as: !$$dr\_t = (\\\\theta (t) - a r\_t) dt + \\\\sigma dW\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_109. Png){. Block-equation width="218"} where !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_110. Png){. Inline-equation width="8"} is the mean reversion constant,    !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_111. Png){. Inline-equation width="9"} is the volatility parameter. The parameter !$$\\\\theta (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_112. Png){. Inline-equation width="27"} is chosen in order to fit the input term structure of interest rates. What is the "right" value for parameters !$$a$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_113. Png){. Inline-equation width="8"} and !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_114. Png){. Inline-equation width="9"}? This is the question that we address by calibrating to market instruments.
    In [2]: today = ql.Date (15,    ql. February,    2002);
            Settlement = ql.Date (19,    ql. February,    2002);
            Ql.Settings.Instance (). EvaluationDate = today;
            Term_structure = ql.YieldTermStructureHandle (
                Ql.FlatForward (settlement,    0.04875825,    ql. Actual 365 Fixed ())
            )
            Index = ql. Euribor 1 Y (term_structure)
In this example we are going to calibrate given the starting tenor,    months to maturity,    and the swaption volatilities as shown below.
    In [3]: CalibrationData = namedtuple ("CalibrationData",    
                                         "start,    length,    volatility")
            Data = [CalibrationData (1,    5,    0.1148),   
                    CalibrationData (2,    4,    0.1108),   
                    CalibrationData (3,    3,    0.1070),   
                    CalibrationData (4,    2,    0.1021),   
                    CalibrationData (5,    1,    0.1000 )]
In order to make the code succinct in the various examples,    we will create two functions. Function \`create\_swaption\_helpers\` takes all the swaption data,    the index such as \`Euribor 1 Y\`,    the term structure and the pricing engine,    and returns a list of \`SwaptionHelper\` objects. The \`calibration\_report\` evaluates the calibration by comparing the model price and implied volatilities with the Black price and market volatilities.
    In [4]: def create_swaption_helpers (data,    index,    term_structure,    engine):
                Swaptions = []
                Fixed_leg_tenor = ql.Period (1,    ql. Years)
                Fixed_leg_daycounter = ql. Actual 360 ()
                Floating_leg_daycounter = ql. Actual 360 ()
                For d in data:
                    vol_handle = ql.QuoteHandle (ql.SimpleQuote (d.volatility))
                    helper = ql.SwaptionHelper (ql.Period (d.start,    ql. Years),   
                                               ql.Period (d.length,    ql. Years),   
                                               Vol_handle,   
                                               Index,   
                                               Fixed_leg_tenor,   
                                               Fixed_leg_daycounter,   
                                               Floating_leg_daycounter,   
                                               Term_structure
                                               )
                    Helper.SetPricingEngine (engine)
                    Swaptions.Append (helper)
                Return swaptions    
            Def calibration_report (swaptions,    data):
                Columns = ["Model Price",    "Market Price",    "Implied Vol",    "Market Vol",   
                           "Rel Error Price",    "Rel Error Vols"]
                Report_data = []
                Cum_err = 0.0
                Cum_err 2 = 0.0
                For i,    s in enumerate (swaptions):
                    model_price = s.modelValue ()
                    Market_vol = data[i]. Volatility
                    black_price = s.blackPrice (market_vol)
                    Rel_error = model_price/black_price - 1.0
                    implied_vol = s.impliedVolatility (model_price,   
                                                      1 e-5,    50,    0.0,    0.50)
                    Rel_error 2 = implied_vol/market_vol-1.0
                    Cum_err += rel_error*rel_error
                    Cum_err 2 += rel_error 2*rel_error 2
                    Report_data.Append ((model_price,    black_price,    implied_vol,   
                                        Market_vol,    rel_error,    rel_error 2))
                Print ("Cumulative Error Price: %7.5 f" % math.Sqrt (cum_err))
                Print ("Cumulative Error Vols : %7.5 f" % math.Sqrt (cum_err 2))
                Return DataFrame (report_data,    columns=columns,   
                                 Index=['']*len (report_data))
\###### Calibrating Reversion and Volaitility { #chap24 . xhtml\_leanpub-auto-calibrating-reversion-and-volaitility} Here we use the \`JamshidianSwaptionEngine\` to value the swaptions as part of calibration. The \`JamshidianSwaptionEngine\` requires one-factor affine models as input. For other interest rate models,    we need a pricing engine that is more suited to those models.
    In [5]: model = ql.HullWhite (term_structure);
            Engine = ql.JamshidianSwaptionEngine (model)
            Swaptions = create_swaption_helpers (data,    index,    term_structure,    engine)
            Optimization_method = ql.LevenbergMarquardt (1.0 e-8,   1.0 e-8,   1.0 e-8)
            End_criteria = ql.EndCriteria (10000,    100,    1 e-6,    1 e-8,    1 e-8)
            Model.Calibrate (swaptions,    optimization_method,    end_criteria)
            A,    sigma = model.Params ()
            Print ("a = %6.5 f,    sigma = %6.5 f" % (a,    sigma))
    Out[5]: a = 0.04642,    sigma = 0.00580
    In [6]: calibration_report (swaptions,    data)
    Out[6]: Cumulative Error Price: 0.11583
            Cumulative Error Vols : 0.11614
    Out[6]: 
  Model Price Market Price Implied Vol Market Vol Rel Error Price Rel Error Vols --- ------------- -------------- ------------- ------------ ----------------- ----------------   0.008775 0.009485 0.106198 0.1148 -0.074854 -0.074928   0.009669 0.010078 0.106292 0.1108 -0.040610 -0.040688   0.008663 0.008716 0.106343 0.1070 -0.006138 -0.006138   0.006490 0.006226 0.106442 0.1021 0.042367 0.042525   0.003542 0.003323 0.106612 0.1000 0.065817 0.066122 ##### Calibrating Volatility With Fixed Reversion { #chap24 . xhtml\_leanpub-auto-calibrating-volatility-with-fixed-reversion} There are times when we need to calibrate with one parameter held fixed. QuantLib allows you to perform calibration with constraints. However,    this ability is not exposed in the SWIG wrappers as of version 1.6. I have created a $$github issue$$( https://github.com/lballabio/quantlib-old/issues/336 ) and provided a patch to address this issue. This patch has been merged into QuantLib-SWIG version 1.7. If you are using version lower than 1.7,    you will need this patch to execute the following cells. Below,    the model is calibrated with a fixed reversion value of 5%. The following code is similar to the Hull-White calibration,    except we initialize the constrained model with given values. In the calibrate method,    we provide a list of boolean with constraints \`$$True,    False$$\`,    meaning that the first parameter \`a\` is constrained where as the second \`sigma\` is not constrained.
    In [7]: constrained_model = ql.HullWhite (term_structure,    0.05,    0.001);
            Engine = ql.JamshidianSwaptionEngine (constrained_model)
            Swaptions = create_swaption_helpers (data,    index,    term_structure,    engine)
            Optimization_method = ql.LevenbergMarquardt (1.0 e-8,   1.0 e-8,   1.0 e-8)
            End_criteria = ql.EndCriteria (10000,    100,    1 e-6,    1 e-8,    1 e-8)
            Constrained_model.Calibrate (swaptions,    optimization_method,    
                                        End_criteria,    ql.NoConstraint (),    
                                        [],    [True,    False])
            A,    sigma = constrained_model.Params ()
            Print ("a = %6.5 f,    sigma = %6.5 f" % (a,    sigma))
    Out[7]: a = 0.05000,    sigma = 0.00586
    In [8]: calibration_report (swaptions,    data)
    Out[8]: Cumulative Error Price: 0.11584
            Cumulative Error Vols : 0.11615
    Out[8]: 
  Model Price Market Price Implied Vol Market Vol Rel Error Price Rel Error Vols --- ------------- -------------- ------------- ------------ ----------------- ----------------   0.008776 0.009485 0.106212 0.1148 -0.074738 -0.074812   0.009668 0.010078 0.106284 0.1108 -0.040682 -0.040761   0.008662 0.008716 0.106330 0.1070 -0.006261 -0.006261   0.006490 0.006226 0.106436 0.1021 0.042311 0.042469   0.003542 0.003323 0.106625 0.1000 0.065946 0.066252 ##### Black Karasinski Model { #chap24 . xhtml\_leanpub-auto-black-karasinski-model} The Black Karasinski model is described as: !$$d\\\\ln (r\_t) = (\\\\theta\_t - a \\\\ln (r\_t)) dt + \\\\sigma dW\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_115. Png){. Block-equation width="267"} Black-Karasinski is not an affine model,    and hence we cannot use the \`JamshidianSwaptionEngine\`. In order to calibrate,    we use the \`TreeSwaptionEngine\` which will work with all short rate models. The calibration procedure is shown below.
    In [9]: model = ql.BlackKarasinski (term_structure);
            Engine = ql.TreeSwaptionEngine (model,    100)
            Swaptions = create_swaption_helpers (data,    index,    term_structure,    engine)
            Optimization_method = ql.LevenbergMarquardt (1.0 e-8,   1.0 e-8,   1.0 e-8)
            End_criteria = ql.EndCriteria (10000,    100,    1 e-6,    1 e-8,    1 e-8)
            Model.Calibrate (swaptions,    optimization_method,    end_criteria)
            A,    sigma =  model.Params ()
            Print ("a = %6.5 f,    sigma = %6.5 f" % (a,    sigma))
    Out[9]: a = 0.03902,    sigma = 0.11695
    In [10]: calibration_report (swaptions,    data)
    Out[10]: Cumulative Error Price: 0.12132
             Cumulative Error Vols : 0.12163
    Out[10]: 
  Model Price Market Price Implied Vol Market Vol Rel Error Price Rel Error Vols --- ------------- -------------- ------------- ------------ ----------------- ----------------   0.008717 0.009485 0.105497 0.1148 -0.080954 -0.081033   0.009670 0.010078 0.106309 0.1108 -0.040453 -0.040531   0.008679 0.008716 0.106540 0.1070 -0.004297 -0.004297   0.006503 0.006226 0.106656 0.1021 0.044457 0.044623   0.003547 0.003323 0.106765 0.1000 0.067333 0.067646 ##### G 2++ Model { #chap24 . xhtml\_leanpub-auto-g 2-model} As a final example,    let us look at a calibration example of the 2-factor G 2++ model. !$$dr\_t = \\\\varphi (t) + x\_t + y\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_116. Png){. Inline-equation width="154"} where !$$x\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_117. Png){. Inline-equation width="14"} and !$$y\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_118. Png){. Inline-equation width="12"} are defined by !$$\\\\begin{eqnarray} dx\_t &=& -a x\_t dt + \\\\sigma dW\\^1\_t \\\\\\\\ dy\_t &=& -b y\_t dt + \\\\eta dW\\^2\_t \\\\\\\\ \\\\left\\ &=& \\\\rho dt \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_119. Png){. Block-equation width="432"} Once again,    we use the \`TreeSwaptionEngine\` to value the swaptions in the calibration step. One can also use \`G 2 SwaptionEngine\` and \`FdG 2 SwaptionEngine\`. But the calibration times,    and accuracy can vary depending on the choice of parameters.
    In [11]: model = ql. G 2 (term_structure);
             Engine = ql.TreeSwaptionEngine (model,    25)
             # engine = ql. G 2 SwaptionEngine (model,    10,    400)
             # engine = ql. FdG 2 SwaptionEngine (model)
             Swaptions = create_swaption_helpers (data,    index,    term_structure,    engine)
             Optimization_method = ql.LevenbergMarquardt (1.0 e-8,   1.0 e-8,   1.0 e-8)
             End_criteria = ql.EndCriteria (1000,    100,    1 e-6,    1 e-8,    1 e-8)
             Model.Calibrate (swaptions,    optimization_method,    end_criteria)
             A,    sigma,    b,    eta,    rho = model.Params ()
             Print ("a = %6.5 f,    sigma = %6.5 f,    b = %6.5 f,    eta = %6.5 f,    rho = %6.5 f " % \
                   (a,    sigma,    b,    eta,    rho))
    Out[11]: a = 0.03942,    sigma = 0.00473,    b = 0.04720,    eta = 0.00301,    rho = 0.03865 
    In [12]: calibration_report (swaptions,    data)
    Out[12]: Cumulative Error Price: 0.12241
             Cumulative Error Vols : 0.12272
    Out[12]: 
  Model Price Market Price Implied Vol Market Vol Rel Error Price Rel Error Vols --- ------------- -------------- ------------- ------------ ----------------- ----------------   0.008704 0.009485 0.105333 0.1148 -0.082383 -0.082464   0.009672 0.010078 0.106322 0.1108 -0.040334 -0.040412   0.008676 0.008716 0.106510 0.1070 -0.004583 -0.004583   0.006503 0.006226 0.106647 0.1021 0.044365 0.044531   0.003548 0.003323 0.106800 0.1000 0.067681 0.067996 ##### Calibrating to Normal Volatilities { #chap24 . xhtml\_leanpub-auto-calibrating-to-normal-volatilities} In certain markets in Europe and Japan for instance have had negative interest rates in the recent past for some of the tenors of the yield curve. The lognormal volatility quotes used above are inconsistent with negative rates and it is generally a practice to quote normal volaitilities in this case. The \`SwaptionHelperPtr\` used above with lognormal volatilities can be modified for normal volatilities by setting the \`VolatilityType\` parameter. The full \`C++\` syntax for the \`SwaptionHelper\` object is as shown below:
    SwaptionHelperPtr (const Date& exerciseDate,    const Period& length,   
                  const Handle<Quote>& volatility,   
                  Const IborIndexPtr& index,   
                  Const Period& fixedLegTenor,   
                  Const DayCounter& fixedLegDayCounter,   
                  Const DayCounter& floatingLegDayCounter,   
                  const Handle<YieldTermStructure>& termStructure,   
                  BlackCalibrationHelper:: CalibrationErrorType errorType
                            = BlackCalibrationHelper:: RelativePriceError,   
                  const Real strike = Null<Real>(),   
                  Const Real nominal = 1.0,   
                  Const VolatilityType type = ShiftedLognormal,   
                  Const Real shift = 0.0) 
In the above examples,    we did not pass any of the optional arguments for \`errorType\`,    \`strike\`,    \`nominal\` and \`type\` specifying the \`VolatilityType\`. One can set the optional \`type\` parameter to change from log-normal volatilities to normal volatilities. A function to create swaption helpers with \`normal\` volatilities is shown below:
    In [13]: def create_swaption_helpers_normal (data,    index,    term_structure,    engine):
                 Swaptions = []
                 Fixed_leg_tenor = ql.Period (1,    ql. Years)
                 Fixed_leg_daycounter = ql. Actual 360 ()
                 Floating_leg_daycounter = ql. Actual 360 ()
                 For d in data:
                     vol_handle = ql.QuoteHandle (ql.SimpleQuote (d.volatility))
                     Helper = ql.SwaptionHelper (
                         ql.Period (d.start,    ql. Years),   
                         ql.Period (d.length,    ql. Years),   
                         Vol_handle,   
                         Index,   
                         Fixed_leg_tenor,   
                         Fixed_leg_daycounter,   
                         Floating_leg_daycounter,   
                         Term_structure,   
                         Ql. BlackCalibrationHelper. RelativePriceError,   
                         Ql.NullDouble (),   
                         1.0,   
                         Ql. Normal)
                     Helper.SetPricingEngine (engine)
                     Swaptions.Append (helper)
                 Return swaptions    
Now,    we can call the \`create\_swaption\_helpers\_normal\` instead to constructions swaptions with normal volatilities and pass it to the calibration routine to determine the model parameters.
    In [14]: model = ql.HullWhite (term_structure);
             Engine = ql.JamshidianSwaptionEngine (model)
             Swaptions = create_swaption_helpers_normal (data,    index,   
                                                        Term_structure,    engine)
             Optimization_method = ql.LevenbergMarquardt (1.0 e-8,   1.0 e-8,   1.0 e-8)
             End_criteria = ql.EndCriteria (10000,    100,    1 e-6,    1 e-8,    1 e-8)
             Model.Calibrate (swaptions,    optimization_method,    end_criteria)
             A,    sigma = model.Params ()
             Print ("a = %6.5 f,    sigma = %6.5 f" % (a,    sigma))
    Out[14]: a = 0.04595,    sigma = 0.11868
\##### Conclusion { #chap24 . xhtml\_leanpub-auto-conclusion-2} In this chapter,    we saw some simple examples of calibrating the interest rate models to the swaption volatilities. We looked at setting up different interest rate models and discussed both lognormal and normal volatilities.
$$$${ #chap25 . xhtml}
\## $$18.$${. Section-number}Par versus indexed coupons { #chap25 . xhtml\_leanpub-auto-par-versus-indexed-coupons} (Based on $$a question asked by KK$$( https://sourceforge.net/p/quantlib/mailman/message/32902476/ ) on the QuantLib mailing list. Thanks!)
    In [1]: import QuantLib as ql
            Import pandas as pd
            Today = ql.Date (7,    ql. January,    2013)
            Ql.Settings.Instance (). EvaluationDate = today
\##### The statement of the case { #chap25 . xhtml\_leanpub-auto-the-statement-of-the-case-2} User KK was pricing an interest-rate swap. In the interest of brevity,    I'll skip the part where he bootstrapped a LIBOR curve (there are other notebooks showing that in detail) and instantiate the resulting curve directly from the resulting forward rates.
    In [2]: dates,    forwards = zip (*[(ql.Date (7,   1,   2013),    0.03613672438543303),   
                                    (ql.Date (8,   4,   2013),    0.03613672438543303),   
                                    (ql.Date (8,   7,   2013),    0.033849133719219514),   
                                    (ql.Date (7,   1,   2014),    0.03573931373272106),   
                                    (ql.Date (7,   7,   2014),    0.03445303757052511)])
            Libor_curve = ql.ForwardCurve (dates,    forwards,    ql. Actual 365 Fixed ())
Here is the floating leg of the swap; we don't need to care about the fixed leg.
    In [3]: index = ql.GBPLibor (ql.Period (6,    ql. Months),   
                                Ql.YieldTermStructureHandle (libor_curve))
            Calendar = index.FixingCalendar ()
            Nominal = 1000000
            Length = 1
            Maturity = calendar.Advance (today,    length,    ql. Years)
            Adjustment = index.BusinessDayConvention ()
            Schedule = ql.Schedule (today,    maturity,   
                                   Index.Tenor (),    calendar,   
                                   Adjustment,    adjustment,   
                                   Ql. DateGeneration. Backward,    False)
            Floating_leg = ql.IborLeg ([nominal],    schedule,   
                                      Index,    index.DayCounter ()) 
Next,    KK set out to do some cash-flow analysis. He reproduced the coupon amounts by multiplying the LIBOR fixing,    the notional,    and the accrual period; the actual code was different,    but the calculations are the same I'm doing here:
    In [4]: df = pd.DataFrame ()
            Dates = list (schedule)
            Df['fixing date'] = dates[:-1]
            Df['index fixing'] = [ index.Fixing (d) for d in df['fixing date'] ]
            Df['start date'] = dates[:-1]
            Df['end date'] = dates[1:]
            Df['days'] = df['end date'] - df['start date']
            Df['accrual period'] = df['days']/365
            Df['amount'] = df['index fixing'] * nominal * df['accrual period']
            Df
    Out[4]: 
  Fixing date index fixing start date end date days accrual period amount --- ------------------- -------------- ------------------- ------------------- ------ ---------------- --------- 0 January 7 th,    2013 0.035300 January 7 th,    2013 July 8 th,    2013 182 0.49863 17601.6 1 July 8 th,    2013 0.036056 July 8 th,    2013 January 7 th,    2014 183 0.50137 18077.4 Unfortunately,    the results for the second coupon don't agree with what the library says:
    In [5]: df 2 = pd.DataFrame ({'amount': [ c.amount () for c in floating_leg ],   
                                'rate': [ ql. As_coupon (c). Rate () for c in floating_leg ]})
            Df 2
    Out[5]: 
  amount rate --- -------------- ---------- 0 17601.643836 0.035300 1 18080.116395 0.036061 The difference (in the rate,    and thus the amount) is small but well above the expected precision for the calculations. ##### Where's the problem? { #chap25 . xhtml\_leanpub-auto-wheres-the-problem} Let's go through the calculations again. The second coupon fixes on the expected date,    and the forecast for the fixing is the same KK obtained.
    In [6]: coupon = ql. As_floating_rate_coupon (floating_leg[1])
            Print (coupon.FixingDate ())
            Print (index.Fixing (coupon.FixingDate ()))
    Out[6]: July 8 th,    2013
            0.036056087457623655
The fixing is also consistent with what we can forecast from the LIBOR curve,    given the start and end date of the underlying tenor:
    In [7]: startDate = index.ValueDate (coupon.FixingDate ())
            EndDate = index.MaturityDate (startDate)
            Print (startDate)
            Print (endDate)
    Out[7]: July 8 th,    2013
            January 8 th,    2014
    In [8]: print (libor_curve.ForwardRate (startDate,    endDate,   
                                          Coupon.DayCounter (),    ql. Simple))
    Out[8]: 3.605609 % Actual/365 (Fixed) simple compounding
The above is,    in fact,    the calculation performed in the \`index. Fixing\` method. Why does the coupon return a different rate,    then? The problem is that,    for historical reasons,    the coupon is calculated at par; that is,    the floating rate is calculated over the duration of the coupon. Due to the constraints of the schedule,    the end of the coupon doesn't correspond to the end of the LIBOR tenor...
    In [9]: couponStart = coupon.AccrualStartDate ()
            CouponEnd = coupon.AccrualEndDate ()
            Print (couponStart)
            Print (couponEnd)
    Out[9]: July 8 th,    2013
            January 7 th,    2014
... And therefore,    the calculated rate is different:
    In [10]: print (libor_curve.ForwardRate (couponStart,    couponEnd,   
                                           Coupon.DayCounter (),    ql. Simple))
    Out[10]: 3.606143 % Actual/365 (Fixed) simple compounding
The coupon amount is consistent with the rate above...
    In [11]: coupon.Rate ()
    Out[11]: 0.0360614343399347
... And so is the amount:
    In [12]: coupon.Rate () * nominal * coupon.AccrualPeriod ()
    Out[12]: 18080.116395090554
    In [13]: coupon.Amount ()
    Out[13]: 18080.11639509055
Was it a good idea to use par coupons? Hard to say. They are used in textbook examples,    which one might want to reproduce. In any case,    I've heard arguments against both calculations. The one against using the forecast index fixing goes that the rate would be accrued over a period which is different from the one over which it was calculated,    and thus it will require a small convexity adjustment. Personally,    the argument failed to persuade me,    since with par coupons we're using the wrong rate over the right period and therefore we're introducing an error anyway; I doubt that it's smaller than the missing convexity adjustment. Moreover,    the value of the swap is going to jump as soon as the coupon rate is actually fixed,    forcing an adjustment of the P&L. The good news is that you can choose which one to use: there's a configuration flag for the library that allows you to use the forecast of the fixing. The bad news is that this requires the recompilation of both the C++ library and the Python module. It would be better if the choice could be made at run-time; I describe the details in $$\*Implementing QuantLib\*$$( https://leanpub.com/implementingquantlib/ ),    including a few glitches that this might cause. For the time being,    you'll have to make do.
$$$${ #chap26 . xhtml}
\## $$19.$${. Section-number}Modeling interest rate swaps using QuantLib { #chap26 . xhtml\_leanpub-auto-modeling-interest-rate-swaps-using-quantlib} An interest rate swap is a financial derivative instrument in which two parties agree to exchange interest rate cash flows based on a notional amount from a fixed rate to a floating rate or from one floating rate to another floating rate. Here we will consider an example of a plain vanilla USD swap with 10 million notional and 10 year maturity. Let the fixed leg pay 2.5% coupon semiannually,    and the floating leg pay Libor 3 m quarterly.
    In [1]: import QuantLib as ql
            Calculation_date = ql.Date (20,    10,    2015)
            Ql.Settings.Instance (). EvaluationDate = calculation_date
Here we construct the yield curve objects. For simplicity,    we will use flat curves for discounting and Libor 3 M. This will help us focus on the swap construction. Please refer to $$curve construction example$$( http://gouthamanbalaraman.com/blog/quantlib-term-structure-bootstrap-yield-curve.html ) for some details.
    In [2]: risk_free_rate = 0.01
            Libor_rate = 0.02
            Day_count = ql. Actual 365 Fixed ()
            Discount_curve = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    risk_free_rate,    day_count)
            )
            Libor_curve = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    libor_rate,    day_count)
            )
            #libor3M_index = ql. Euribor 3 M (libor_curve)  
            Libor 3 M_index = ql.USDLibor (ql.Period (3,    ql. Months),    libor_curve)
To construct the swap,    we have to specify the fixed rate leg and floating rate leg. We construct the fixed rate and floating rate leg schedules below.
    In [3]: calendar = ql.UnitedStates ()
            Settle_date = calendar.Advance (calculation_date,    5,    ql. Days)
            Maturity_date = calendar.Advance (settle_date,    10,    ql. Years)
            Fixed_leg_tenor = ql.Period (6,    ql. Months)
            Fixed_schedule = ql.Schedule (settle_date,    maturity_date,    
                                         Fixed_leg_tenor,    calendar,   
                                         Ql. ModifiedFollowing,    ql. ModifiedFollowing,   
                                         Ql. DateGeneration. Forward,    False)
            Float_leg_tenor = ql.Period (3,    ql. Months)
            Float_schedule = ql.Schedule (settle_date,    maturity_date,    
                                         Float_leg_tenor,    calendar,   
                                         Ql. ModifiedFollowing,    ql. ModifiedFollowing,   
                                         Ql. DateGeneration. Forward,    False)
Below,    we construct a \`VanillaSwap\` object by including the fixed and float leg schedules created above.
    In [4]: notional = 10000000
            Fixed_rate = 0.025
            Fixed_leg_daycount = ql. Actual 360 ()
            Float_spread = 0.004
            Float_leg_daycount = ql. Actual 360 ()
            Ir_swap = ql.VanillaSwap (ql. VanillaSwap. Payer,    notional,    fixed_schedule,    
                                     Fixed_rate,    fixed_leg_daycount,    float_schedule,   
                                     Libor 3 M_index,    float_spread,    float_leg_daycount)
We evaluate the swap using a discounting engine.
    In [5]: swap_engine = ql.DiscountingSwapEngine (discount_curve)
            Ir_swap.SetPricingEngine (swap_engine)
\##### Result Analysis { #chap26 . xhtml\_leanpub-auto-result-analysis} The cash flows for the fixed and floating leg can be extracted from the \`ir\_swap\` object. The fixed leg cash flows are shown below:
    In [6]: from pandas import DataFrame
            DataFrame (
                [(cf.Date (),    cf.Amount ()) for cf in ir_swap.Leg (0)],   
                Columns=["Date",    "Amount"],   
                Index=range (1,    len (ir_swap.Leg (0))+1))
    Out[6]: 
  Date Amount ---- -------------------- --------------- 1 April 27 th,    2016 127083.333333 2 October 27 th,    2016 127083.333333 3 April 27 th,    2017 126388.888889 4 October 27 th,    2017 127083.333333 5 April 27 th,    2018 126388.888889 6 October 29 th,    2018 128472.222222 7 April 29 th,    2019 126388.888889 8 October 28 th,    2019 126388.888889 9 April 27 th,    2020 126388.888889 10 October 27 th,    2020 127083.333333 11 April 27 th,    2021 126388.888889 12 October 27 th,    2021 127083.333333 13 April 27 th,    2022 126388.888889 14 October 27 th,    2022 127083.333333 15 April 27 th,    2023 126388.888889 16 October 27 th,    2023 127083.333333 17 April 29 th,    2024 128472.222222 18 October 28 th,    2024 126388.888889 19 April 28 th,    2025 126388.888889 20 October 27 th,    2025 126388.888889 The floating leg cash flows are shown below:
    In [7]: from pandas import DataFrame
            DataFrame (
                [(cf.Date (),    cf.Amount ()) for cf in ir_swap.Leg (1)],   
                Columns=["Date",    "Amount"],   
                Index=range (1,    len (ir_swap.Leg (1))+1))
    Out[7]: 
  Date Amount ---- -------------------- -------------- 1 January 27 th,    2016 60760.458147 2 April 27 th,    2016 60098.647700 3 July 27 th,    2016 60098.647700 4 October 27 th,    2016 60760.458147 5 January 27 th,    2017 60760.458147 6 April 27 th,    2017 59436.867427 7 July 27 th,    2017 60098.647700 8 October 27 th,    2017 60760.458147 9 January 29 th,    2018 62084.169572 10 April 27 th,    2018 58113.397399 11 July 27 th,    2018 60098.647700 12 October 29 th,    2018 62084.169572 13 January 28 th,    2019 60098.647700 14 April 29 th,    2019 60098.647700 15 July 29 th,    2019 60098.647700 16 October 28 th,    2019 60098.647700 17 January 27 th,    2020 60098.647700 18 April 27 th,    2020 60098.647700 19 July 27 th,    2020 60098.647700 20 October 27 th,    2020 60760.458147 21 January 27 th,    2021 60760.458147 22 April 27 th,    2021 59436.867427 23 July 27 th,    2021 60098.647700 24 October 27 th,    2021 60760.458147 25 January 27 th,    2022 60760.458147 26 April 27 th,    2022 59436.867427 27 July 27 th,    2022 60098.647700 28 October 27 th,    2022 60760.458147 29 January 27 th,    2023 60760.458147 30 April 27 th,    2023 59436.867427 31 July 27 th,    2023 60098.647700 32 October 27 th,    2023 60760.458147 33 January 29 th,    2024 62084.169572 34 April 29 th,    2024 60098.647700 35 July 29 th,    2024 60098.647700 36 October 28 th,    2024 60098.647700 37 January 27 th,    2025 60098.647700 38 April 28 th,    2025 60098.647700 39 July 28 th,    2025 60098.647700 40 October 27 th,    2025 60098.647700 Some other analytics such as the fair value,    fair spread etc can be extracted as shown below.
    In [8]: print ("%-20 s: %20.3 f" % ("Net Present Value",    ir_swap.NPV ()))
            Print ("%-20 s: %20.3 f" % ("Fair Spread",    ir_swap.FairSpread ()))
            Print ("%-20 s: %20.3 f" % ("Fair Rate",    ir_swap.FairRate ()))
            Print ("%-20 s: %20.3 f" % ("Fixed Leg BPS",    ir_swap.FixedLegBPS ()))
            Print ("%-20 s: %20.3 f" % ("Floating Leg BPS",    ir_swap.FloatingLegBPS ()))
    Out[8]: Net Present Value   :          -115054.034
            Fair Spread         :                0.005
            Fair Rate           :                0.024
            Fixed Leg BPS       :            -9629.981
            Floating Leg BPS    :             9642.042
\##### Conclusion { #chap26 . xhtml\_leanpub-auto-conclusion-3} Here we saw a simple example on how to construct a swap and value them. We evaluated the fixed and floating legs and then valued the \`VanillaSwap\` using the \`DiscountingSwapEngine\`.
$$$${ #chap27 . xhtml}
\## $$20.$${. Section-number}Caps and floors { #chap27 . xhtml\_leanpub-auto-caps-and-floors} In this post,    I will walk you through a simple example of valuing caps. I want to talk about two specific cases: 1. Value caps given a constant volatility 2. Value caps given a cap volatility surface Caps,    as you might know,    can be valued as a sum of caplets. The value of each caplet is determined by the Black formula. In practice,    each caplet would have a different volatility. Meaning,    a caplet that is in the near term can have a different volatility profile compared to the caplet that is far away in tenor. Similarly caplet volatilities differ with the strike as well.
    In [1]: import QuantLib as ql
    In [2]: calc_date = ql.Date (14,    6,    2016)
            Ql.Settings.Instance (). EvaluationDate = calc_date
\##### Constant Volatility { #chap27 . xhtml\_leanpub-auto-constant-volatility} Let us start by constructing different components required in valuing the caps. The components that we would need are: 1. Interest rate term structure for discounting 2. Interest rate term structure for the floating leg 3. Construction of the cap 4. The pricing engine to value caps using the Black formula For simplicity,    we will construct only one interest rate term structure here,    and assume that the discounting and the floating leg is referenced by the same. Below the term structure of interest rates is constructed from a set of zero rates.
    In [3]: dates = [ql.Date (14,   6,   2016),     ql.Date (14,   9,   2016),    
                     Ql.Date (14,   12,   2016),    ql.Date (14,   6,   2017),   
                     Ql.Date (14,   6,   2019),     ql.Date (14,   6,   2021),   
                     Ql.Date (15,   6,   2026),     ql.Date (16,   6,   2031),   
                     Ql.Date (16,   6,   2036),     ql.Date (14,   6,   2046)
                     ]
            Yields = [0.000000,    0.006616,    0.007049,    0.007795,   
                      0.009599,    0.011203,    0.015068,    0.017583,   
                      0.018998,    0.020080]
            Day_count = ql.ActualActual ()
            Calendar = ql.UnitedStates ()
            Interpolation = ql.Linear ()
            Compounding = ql. Compounded
            Compounding_frequency = ql. Annual
            Term_structure = ql.ZeroCurve (dates,    yields,    day_count,    
                                          Calendar,    interpolation,    
                                          Compounding,    compounding_frequency)
            Ts_handle = ql.YieldTermStructureHandle (term_structure)
As a next step,    lets construct the cap itself. In order to do that,    we start by constructing the \`Schedule\` object to project the cash-flow dates.
    In [4]: start_date = ql.Date (14,    6,    2016)
            End_date = ql.Date (14,    6 ,    2026)
            Period = ql.Period (3,    ql. Months)
            Calendar = ql.UnitedStates ()
            Bus_convention = ql. ModifiedFollowing
            Rule = ql. DateGeneration. Forward
            End_of_month = False
            Schedule = ql.Schedule (start_date,    end_date,    period,   
                                   Calendar,    bus_convention,    
                                   Bus_convention,    rule,    end_of_month)
Now that we have the schedule,    we construct the \`USDLibor\` index. Below,    you can see that I use \`addFixing\` method to provide a fixing date for June 10,    2016. According the schedule constructed,    the start date of the cap is June 14,    2016,    and there is a 2 business day settlement lag (meaning June 10 reference date) embedded in the \`USDLibor\` definition. So in order to set the rate for the accrual period,    the rate is obtained from the fixing data provided. For all future dates,    the libor rates are automatically inferred using the forward rates provided by the given interest rate term structure.
    In [5]: ibor_index = ql.USDLibor (ql.Period (3,    ql. Months),    ts_handle)
            Ibor_index.AddFixing (ql.Date (10,   6,   2016),    0.0065560)
            Ibor_leg = ql.IborLeg ([1000000],    schedule,    ibor_index)
Now that we have all the required pieces,    the \`Cap\` can be constructed by passing the \`ibor\_leg\` and the \`strike\` information. Constructing a floor is done through the \`Floor\` class. The \`BlackCapFloorEngine\` can be used to price the cap with constant volatility as shown below.
    In [6]: strike = 0.02
            Cap = ql.Cap (ibor_leg,    [strike])
            Vols = ql.QuoteHandle (ql.SimpleQuote (0.547295))
            Engine = ql.BlackCapFloorEngine (ts_handle,    vols)
            Cap.SetPricingEngine (engine)
            Print (cap.NPV ())
    Out[6]: 54369.85806286924
\##### Using Volatility Surfaces { #chap27 . xhtml\_leanpub-auto-using-volatility-surfaces} In the above exercise,    we used a constant volatility value. In practice,    one needs to strip the market quoted cap/floor volatilities to infer the volatility of each caplet. QuantLib provides excellent tools in order to do that. Let us assume the following dummy data represents the volatility surface quoted by the market. I have the various \`strikes\`,    \`expiries\`,    and the volatility quotes in percentage format. I take the raw data and create a \`Matrix\` in order to construct the volatility surface.
    In [7]: strikes = [0.01,   0.015,    0.02]
            Temp = list (range (1,    11)) + [12]
            Expiries = [ql.Period (i,    ql. Years) for i in temp] 
            Vols = ql.Matrix (len (expiries),    len (strikes))
            Data = [
                [47.27,    55.47,    64.07,    70.14,    72.13,    69.41,   
                 72.15,    67.28,    66.08,    68.64,    65.83],   
                [46.65,    54.15,    61.47,    65.53,    66.28,    62.83,   
                 64.42,    60.05,    58.71,    60.35,    55.91],   
                [46.60,    52.65,    59.32,    62.05,    62.00,    58.09,   
                 59.03,    55.00,    53.59,    54.74,    49.54]
            ]
            For i in range (vols.Rows ()):
                For j in range (vols.Columns ()):
                    Vols[i][j] = data[j][i]/100.0
The \`CapFloorTermVolSurface\` offers a way to store the cap/floor volatilities. These are however \`CapFloor\` volatilities,    and not the volatilities of the individual options.
    In [8]: calendar = ql.UnitedStates ()
            Bdc = ql. ModifiedFollowing
            Daycount = ql. Actual 365 Fixed ()
            Settlement_days = 2
            Capfloor_vol = ql.CapFloorTermVolSurface (
                Settlement_days,    calendar,    bdc,    
                Expiries,    strikes,    vols,    daycount
            )
The \`OptionletStripper 1\` class lets you to strip the individual caplet/floorlet volatilities from the cap/floor volatilities. We have to 'jump' some hoops here to make it useful for pricing. The \`OptionletStripper 1\` class cannot be consumed directly by a pricing engine. The \`StrippedOptionletAdapter\` takes the stripped optionlet volatilities,    and creates a term structure of optionlet volatilities. We then wrap that into a handle using \`OptionletVolatilityStructureHandle\`.
    In [9]: optionlet_surf = ql. OptionletStripper 1 (
                Capfloor_vol,    ibor_index,    ql.NullDouble (),   
                1 e-6,    100,    ts_handle
            )
            Ovs_handle = ql.OptionletVolatilityStructureHandle (
                Ql.StrippedOptionletAdapter (optionlet_surf)
            )
Below,    we visualize the cap/floor volatility surface,    and the optionlet volatility surface for a fixed strike.
    In [10]: import utils
             Import numpy as np
             %matplotlib inline
    In [11]: tenors = np.Arange (0,   10,   0.25)
             Strike = 0.01
             Capfloor_vols = [capfloor_vol.Volatility (t,    strike) for t in tenors]
             Opionlet_vols = [ovs_handle.Volatility (t,    strike) for t in tenors]
             Fig,    ax = utils.Plot ()
             Ax.Plot (tenors,    capfloor_vols,    "--",    label="CapFloor Vols")
             Ax.Plot (tenors,    opionlet_vols,   "-",    label="Optionlet Vols")
             Ax.Legend (loc='best')
             Ax. Set_xlabel ("Tenors",    size=14)
             Ax. Set_ylabel ("Volatility",    size=14);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/capfloor_valuations-11.png)
::: The \`BlackCapFloorEngine\` can accept the optionlet volatility surface in order to price the caps or floors.
    In [12]: engine 2 = ql.BlackCapFloorEngine (ts_handle,    ovs_handle)
             Cap.SetPricingEngine (engine 2)
             Print (cap.NPV ())
    Out[12]: 54384.928314950135
One can infer the implied volatility for the cap at its NPV,    and it should be in agreement with what is quote by the surface.
    In [13]: cap.ImpliedVolatility (cap.NPV (),    ts_handle,    0.4)
    Out[13]: 0.5474438930928851
The QuantLib C++ class allow for one to view the projected cash flows in terms of individual caplets.
$$$${ #chap28 . xhtml}
\# Equity models { #chap28 . xhtml\_leanpub-auto-equity-models}
$$$${ #chap29 . xhtml}
\## $$21.$${. Section-number}Valuing European option using the Heston model { #chap29 . xhtml\_leanpub-auto-valuing-european-option-using-the-heston-model} Heston model can be used to value options by modeling the underlying asset such as the stock of a company. The one major feature of the Heston model is that it inocrporates a stochastic volatility term. !$$\\\\begin{eqnarray} dS\_t &=& \\\\mu S\_tdt + \\\\sqrt{V\_t} S\_t dW\_t\\^1 \\\\\\\\ dV\_t &=& \\\\kappa (\\\\theta-V\_t) + \\\\sigma \\\\sqrt{V\_t} dW\_t\\^2 \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_120. Png){. Block-equation width="426"} Here : - !$$S\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_121. Png){. Inline-equation width="14"} is the asset's value at time !$$t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_122. Png){. Inline-equation width="5"} - !$$\\\\mu$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_123. Png){. Inline-equation width="10"} is the expected growth rate of the log normal stock value - !$$V\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_124. Png){. Inline-equation width="14"} is the variance of the asset !$$S\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_125. Png){. Inline-equation width="14"} - !$$W\_t\\^1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_126. Png){. Inline-equation width="24"} is the stochastic process governing the !$$S\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_127. Png){. Inline-equation width="14"} process - !$$\\\\theta$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_128. Png){. Inline-equation width="7"} is the value of mean reversion for the variance !$$V\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_129. Png){. Inline-equation width="14"} - !$$\\\\kappa$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_130. Png){. Inline-equation width="9"} is the strength of mean reversion - !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_131. Png){. Inline-equation width="9"} is the volatility of volatility - !$$W\_t\\^2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_132. Png){. Inline-equation width="25"} is the stochastic process governing the !$$V\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_133. Png){. Inline-equation width="14"} process - The correlation between !$$W\_t\\^1$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_134. Png){. Inline-equation width="24"} and !$$W\_t\\^2$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_135. Png){. Inline-equation width="25"} is !$$\\\\rho$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_136. Png){. Inline-equation width="8"} In contrast,    the Black-Scholes-Merton process assumes that the volatility is constant.
    In [1]: import QuantLib as ql
            Import numpy as np
            Import math
Let us consider a European call option for AAPL with a strike price of 130 maturing on 15 th Jan,    2016. Let the spot price be 127.62. The volatility of the underlying stock is know to be 20%,    and has a dividend yield of 1.63%. We assume a short term risk free rate of 0.1%. Lets value this option as of 8 th May,    2015.
    In [2]: # option parameters
            Strike_price = 110.0
            Payoff = ql.PlainVanillaPayoff (ql. Option. Call,    strike_price)
            # option data
            Maturity_date = ql.Date (15,    1,    2016)
            Spot_price = 127.62
            Strike_price = 130
            Volatility = 0.20 # the historical vols for a year
            Dividend_rate =  0.0163
            Option_type = ql. Option. Call
            Risk_free_rate = 0.001
            Day_count = ql. Actual 365 Fixed ()
            Calendar = ql.UnitedStates ()
            Calculation_date = ql.Date (8,    5,    2015)
            Ql.Settings.Instance (). EvaluationDate = calculation_date
Using the above inputs,    we construct the European option as shown below.
    In [3]: # construct the European Option
            Payoff = ql.PlainVanillaPayoff (option_type,    strike_price)
            Exercise = ql.EuropeanExercise (maturity_date)
            European_option = ql.VanillaOption (payoff,    exercise)
In order to price the option using the Heston model,    we first create the Heston process. In order to create the Heston process,    we use the parameter values: mean reversion strength \`kappa = 0.1\`,    the spot variance \`v 0 = volatility\*volatility = 0.04\`,    the mean reversion variance \`theta=v 0\`,    volatility of volatility \`sigma = 0.1\` and the correlation between the asset price and its variance is \`rho = -0.75\`.
    In [4]: # construct the Heston process
            V 0 = volatility*volatility  # spot variance
            Kappa = 0.1
            Theta = v 0
            Sigma = 0.1
            Rho = -0.75
            Spot_handle = ql.QuoteHandle (
                Ql.SimpleQuote (spot_price)
            )
            Flat_ts = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    risk_free_rate,    day_count)
            )
            Dividend_yield = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    dividend_rate,    day_count)
            )
            Heston_process = ql.HestonProcess (flat_ts,    dividend_yield,   
                                              Spot_handle,    v 0,    kappa,   
                                              Theta,    sigma,    rho)
On valuing the option using the Heston model,    we get the net present value as:
    In [5]: engine = ql.AnalyticHestonEngine (ql.HestonModel (heston_process),    0.01,    1000)
            European_option.SetPricingEngine (engine)
            H_price = european_option.NPV ()
            Print ("The Heston model price is {0}".Format (h_price))
    Out[5]: The Heston model price is 6.533855481449102
Performing the same calculation using the Black-Scholes-Merton process,    we get:
    In [6]: flat_vol_ts = ql.BlackVolTermStructureHandle (
                Ql.BlackConstantVol (calculation_date,    calendar,    
                                    Volatility,    day_count)
            )
            Bsm_process = ql.BlackScholesMertonProcess (spot_handle,    dividend_yield,    
                                                       Flat_ts,    flat_vol_ts)
            European_option.SetPricingEngine (ql.AnalyticEuropeanEngine (bsm_process))
            Bs_price = european_option.NPV ()
            Print ("The Black-Scholes-Merton model price is {0}".Format (bs_price))
    Out[6]: The Black-Scholes-Merton model price is 6.749271812460607
The difference in the price between the two models is \`bs\_price - h\_price\`,    or about 0.215. This difference is due to the stochastic modeling of the volatility as a CIR-process.
$$$${ #chap30 . xhtml}
\## $$22.$${. Section-number}Volatility smile and Heston model calibration { #chap30 . xhtml\_leanpub-auto-volatility-smile-and-heston-model-calibration} European options on an equity underlying such as an index (S&P 500) or a stock (AMZN) trade for different combinations of strikes and maturities. It turns out that the Black-Scholes implied volatility for these options with different maturities and strikes is not the same. The fact that the implied volatility varies with strike is often referred in the market as having a \*smile\*.
    In [1]: import QuantLib as ql
            Import math
First let us define some of the basic data conventions such as the day\_count,    calendar etc.
    In [2]: day_count = ql. Actual 365 Fixed ()
            Calendar = ql.UnitedStates ()
            Calculation_date = ql.Date (6,    11,    2015)
            Spot = 659.37
            Ql.Settings.Instance (). EvaluationDate = calculation_date
            Dividend_yield = ql.QuoteHandle (ql.SimpleQuote (0.0))
            Risk_free_rate = 0.01
            Dividend_rate = 0.0
            Flat_ts = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    risk_free_rate,    day_count))
            Dividend_ts = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    dividend_rate,    day_count))
Following is a sample matrix of volatility quote by expiry and strike. The volatilities are log-normal volatilities and can be interpolated to construct the implied volatility surface.
    In [3]: expiration_dates = [
                Ql.Date (6,   12,   2015),    ql.Date (6,   1,   2016),    ql.Date (6,   2,   2016),   
                Ql.Date (6,   3,   2016),    ql.Date (6,   4,   2016),    ql.Date (6,   5,   2016),   
                Ql.Date (6,   6,   2016),    ql.Date (6,   7,   2016),    ql.Date (6,   8,   2016),   
                Ql.Date (6,   9,   2016),    ql.Date (6,   10,   2016),    ql.Date (6,   11,   2016),   
                Ql.Date (6,   12,   2016),    ql.Date (6,   1,   2017),    ql.Date (6,   2,   2017),   
                Ql.Date (6,   3,   2017),    ql.Date (6,   4,   2017),    ql.Date (6,   5,   2017),   
                Ql.Date (6,   6,   2017),    ql.Date (6,   7,   2017),    ql.Date (6,   8,   2017),   
                Ql.Date (6,   9,   2017),    ql.Date (6,   10,   2017),    ql.Date (6,   11,   2017)]
            Strikes = [527.50,    560.46,    593.43,    626.40,    659.37,    692.34,    725.31,    758.28]
            Data = [
            [0.37819,    0.34177,    0.30394,    0.27832,    0.26453,    0.25916,    0.25941,    0.26127],   
            [0.3445,    0.31769,    0.2933,    0.27614,    0.26575,    0.25729,    0.25228,    0.25202],   
            [0.37419,    0.35372,    0.33729,    0.32492,    0.31601,    0.30883,    0.30036,    0.29568],   
            [0.37498,    0.35847,    0.34475,    0.33399,    0.32715,    0.31943,    0.31098,    0.30506],   
            [0.35941,    0.34516,    0.33296,    0.32275,    0.31867,    0.30969,    0.30239,    0.29631],   
            [0.35521,    0.34242,    0.33154,    0.3219,    0.31948,    0.31096,    0.30424,    0.2984],   
            [0.35442,    0.34267,    0.33288,    0.32374,    0.32245,    0.31474,    0.30838,    0.30283],   
            [0.35384,    0.34286,    0.33386,    0.32507,    0.3246,    0.31745,    0.31135,    0.306],   
            [0.35338,    0.343,    0.33464,    0.32614,    0.3263,    0.31961,    0.31371,    0.30852],   
            [0.35301,    0.34312,    0.33526,    0.32698,    0.32766,    0.32132,    0.31558,    0.31052],   
            [0.35272,    0.34322,    0.33574,    0.32765,    0.32873,    0.32267,    0.31705,    0.31209],   
            [0.35246,    0.3433,    0.33617,    0.32822,    0.32965,    0.32383,    0.31831,    0.31344],   
            [0.35226,    0.34336,    0.33651,    0.32869,    0.3304,    0.32477,    0.31934,    0.31453],   
            [0.35207,    0.34342,    0.33681,    0.32911,    0.33106,    0.32561,    0.32025,    0.3155],   
            [0.35171,    0.34327,    0.33679,    0.32931,    0.3319,    0.32665,    0.32139,    0.31675],   
            [0.35128,    0.343,    0.33658,    0.32937,    0.33276,    0.32769,    0.32255,    0.31802],   
            [0.35086,    0.34274,    0.33637,    0.32943,    0.3336,    0.32872,    0.32368,    0.31927],   
            [0.35049,    0.34252,    0.33618,    0.32948,    0.33432,    0.32959,    0.32465,    0.32034],   
            [0.35016,    0.34231,    0.33602,    0.32953,    0.33498,    0.3304,    0.32554,    0.32132],   
            [0.34986,    0.34213,    0.33587,    0.32957,    0.33556,    0.3311,    0.32631,    0.32217],   
            [0.34959,    0.34196,    0.33573,    0.32961,    0.3361,    0.33176,    0.32704,    0.32296],   
            [0.34934,    0.34181,    0.33561,    0.32964,    0.33658,    0.33235,    0.32769,    0.32368],   
            [0.34912,    0.34167,    0.3355,    0.32967,    0.33701,    0.33288,    0.32827,    0.32432],   
            [0.34891,    0.34154,    0.33539,    0.3297,    0.33742,    0.33337,    0.32881,    0.32492]]
\##### Implied Volatility Surface { #chap30 . xhtml\_leanpub-auto-implied-volatility-surface} Each row in \`data\` is a different expiration time,    and each column corresponds to various strikes as given in \`strikes\`. We load all this data into the QuantLib \`Matrix\` object. This can then be used seamlessly in the various surface construction routines. The variable \`implied\_vols\` holds the above data in a \`Matrix\` format. One unusual bit of info that one needs to pay attention to is the ordering of the rows and columns in the \`Matrix\` object. The implied volatilities in the QuantLib context needs to have strikes along the row dimension and expiries in the column dimension. This is transpose of the way the data was constructed above. All of this detail is taken care by swapping the \`i\` and \`j\` variables below. Pay attention to the line:
    Implied_vols[i][j] = data[j][i]
In the cell below.
    In [4]: implied_vols = ql.Matrix (len (strikes),    len (expiration_dates))
            For i in range (implied_vols.Rows ()):
                For j in range (implied_vols.Columns ()):
                    Implied_vols[i][j] = data[j][i]
Now the Black volatility surface can be constructed using the \`BlackVarianceSurface\` method.
    In [5]: black_var_surface = ql.BlackVarianceSurface (
                Calculation_date,    calendar,    
                Expiration_dates,    strikes,    
                Implied_vols,    day_count)
The volatilities for any given strike and expiry pair can be easily obtained using \`black\_var\_surface\` shown below.
    In [6]: strike = 600.0
            Expiry = 1.2 # years
            Black_var_surface.BlackVol (expiry,    strike)
    Out[6]: 0.3352982638587421
$$$${ #chap31 . xhtml}
\### Visualization { #chap31 . xhtml\_leanpub-auto-visualization}
    In [7]: import numpy as np
            Import utils
            %matplotlib inline
            From mpl_toolkits. Mplot 3 d import Axes 3 D
            Import matplotlib. Pyplot as plt
            From matplotlib import cm
Given an expiry,    we can visualize the volatility as a function of the strike.
    In [8]: strikes_grid = np.Arange (strikes[0],    strikes[-1],    10)
            Expiry = 1.0 # years
            Implied_vols = [black_var_surface.BlackVol (expiry,    s) 
                            For s in strikes_grid] # can interpolate here
            Actual_data = data[11] # cherry picked the data for given expiry
            Fig,    ax = utils.Plot ()
            Ax.Plot (strikes_grid,    implied_vols,    label="Black Surface")
            Ax.Plot (strikes,    actual_data,    "o",    label="Actual")
            Ax. Set_xlabel ("Strikes",    size=12)
            Ax. Set_ylabel ("Vols",    size=12)
            Ax.Legend (loc="upper right");
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/heston_model_calibration_smile-8.png)
::: The whole volatility surface can also be visualised as shown below.
    In [9]: plot_years = np.Arange (0,    2,    0.1)
            Plot_strikes = np.Arange (535,    750,    1)
            Fig = plt.Figure (figsize=utils. Default_plot_size)
            Ax = fig.Gca (projection='3 d')
            X,    Y = np.Meshgrid (plot_strikes,    plot_years)
            Z = np.Array ([black_var_surface.BlackVol (float (y),    float (x)) 
                          For xr,    yr in zip (X,    Y) 
                              For x,    y in zip (xr,    yr) ]
                         ). Reshape (len (X),    len (X[0]))
            Surf = ax. Plot_surface (X,    Y,    Z,    rstride=1,    cstride=1,    cmap=cm. Coolwarm,   
                                   Linewidth=0.1)
            Fig.Colorbar (surf,    shrink=0.5,    aspect=5);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/heston_model_calibration_smile-9.png)
::: One can also construct a local volatility surface (\*a la\* Dupire) using the \`LocalVolSurface\`. There are some issues with this as shown below.
    In [10]: local_vol_surface = ql.LocalVolSurface (
                 Ql.BlackVolTermStructureHandle (black_var_surface),    
                 Flat_ts,    
                 Dividend_ts,    
                 Spot)
    In [11]: plot_years = np.Arange (0,    2,    0.1)
             Plot_strikes = np.Arange (535,    750,    1)
             Fig = plt.Figure (figsize=utils. Default_plot_size)
             Ax = fig.Gca (projection='3 d')
             X,    Y = np.Meshgrid (plot_strikes,    plot_years)
             Z = np.Array ([local_vol_surface.LocalVol (float (y),    float (x)) 
                           For xr,    yr in zip (X,    Y) 
                               For x,    y in zip (xr,    yr) ]
                          ). Reshape (len (X),    len (X[0]))
             Surf = ax. Plot_surface (X,    Y,    Z,    rstride=1,    cstride=1,    cmap=cm. Coolwarm,   
                                    Linewidth=0.1)
             Fig.Colorbar (surf,    shrink=0.5,    aspect=5);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/heston_model_calibration_smile-11.png)
::: The correct pricing of local volatility surface requires an arbitrage free implied volatility surface. If the input implied volatility surface is not arbitrage free,    this can lead to negative transition probabilities and/or negative local volatilities and can give rise to mispricing. Refer to Fengler's arbitrage-free smoothing \\$$1\\$$ which QuantLib currently lacks. When you use an arbitrary smoothing,    you will notice that the local volatility surface leads to undesired negative volatilities. This can lead to errors as shown below.
    In [12]: black_var_surface.SetInterpolation ("bicubic")
             Local_vol_surface = ql.LocalVolSurface (
                 Ql.BlackVolTermStructureHandle (black_var_surface),    
                 Flat_ts,    
                 Dividend_ts,    
                 Spot)
             Plot_years = np.Arange (0,    2,    0.15)
             Plot_strikes = np.Arange (535,    750,    10)
             X,    Y = np.Meshgrid (plot_strikes,    plot_years)
             Z = np.Array ([local_vol_surface.LocalVol (float (y),    float (x)) 
                           For xr,    yr in zip (X,    Y) 
                               For x,    y in zip (xr,    yr) ]
                          ). Reshape (len (X),    len (X[0]))
    Out[12]: ---------------------------------------------------------------------------
             RuntimeError                              Traceback (most recent call last)
             <ipython-input-12-3332ef075340> in <module>
                   9 X,    Y = np.Meshgrid (plot_strikes,    plot_years)
                  10 Z = np.Array ([local_vol_surface.LocalVol (float (y),    float (x)) 
             ---> 11               for xr,    yr in zip (X,    Y)
                  12                   for x,    y in zip (xr,    yr) ]
                  13              ). Reshape (len (X),    len (X[0]))
             <ipython-input-12-3332ef075340> in <listcomp>(. 0)
                  10 Z = np.Array ([local_vol_surface.LocalVol (float (y),    float (x)) 
                  11               for xr,    yr in zip (X,    Y)
             ---> 12                   for x,    y in zip (xr,    yr) ]
                  13              ). Reshape (len (X),    len (X[0]))
             /usr/local/lib/python 3.6/dist-packages/QuantLib/QuantLib. Py in localVol (self,    *args)
                8642 
                8643     def localVol (self,    *args):
             -> 8644         return _QuantLib. LocalVolTermStructure_localVol (self,    *args)
                8645 
                8646     def enableExtrapolation (self):
             RuntimeError: negative local vol^2 at strike 655 and time 0.75; the black vol surface\
     Is not smooth enough
\##### Heston Model Calibration { #chap31 . xhtml\_leanpub-auto-heston-model-calibration} Heston model is defined by the following stochastic differential equations. !$$\\\\begin{eqnarray} dS (t,    S) &=& \\\\mu S dt + \\\\sqrt{v} S dW\_1 \\\\\\\\ dv (t,    S) &=& \\\\kappa (\\\\theta - v) dt + \\\\sigma \\\\sqrt{v} dW\_2 \\\\\\\\ dW\_1 dW\_2 &=& \\\\rho dt \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_137. Png){. Block-equation width="446"} Here the asset is modeled as a stochastic process that depends on volatility !$$v$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_138. Png){. Inline-equation width="8"} which is a mean reverting stochastic process with a constant volatility of volatility !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_139. Png){. Inline-equation width="9"}. The two stochastic processes have a correlation !$$\\\\rho$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_140. Png){. Inline-equation width="8"}. Let us look at how we can calibrate the Heston model to some market quotes. As an example,    let's say we are interested in trading options with 1 year maturity. So we will calibrate the Heston model to fit to market volatility quotes with one year maturity. Before we do that,    we need to construct the pricing engine that the calibration routines would need. In order to do that,    we start by constructing the Heston model with some dummy starting parameters as shown below.
    In [13]: # dummy parameters
             V 0 = 0.01; kappa = 0.2; theta = 0.02; rho = -0.75; sigma = 0.5;
             Process = ql.HestonProcess (flat_ts,    dividend_ts,    
                                        Ql.QuoteHandle (ql.SimpleQuote (spot)),    
                                        V 0,    kappa,    theta,    sigma,    rho)
             Model = ql.HestonModel (process)
             Engine = ql.AnalyticHestonEngine (model)
Now that we have the Heston model and a pricing engine,    let us pick the quotes with all strikes and 1 year maturity in order to calibrate the Heston model. We build the Heston model helper which will be fed into the calibration routines.
    In [14]: heston_helpers = []
             Black_var_surface.SetInterpolation ("bicubic")
             One_year_idx = 11 # 12 th row in data is for 1 year expiry
             Date = expiration_dates[one_year_idx]
             For j,    s in enumerate (strikes):
                 T = (date - calculation_date )
                 P = ql.Period (t,    ql. Days)
                 Sigma = data[one_year_idx][j]
                 #sigma = black_var_surface.BlackVol (t/365.25,    s)
                 Helper = ql.HestonModelHelper (p,    calendar,    spot,    s,    
                                               Ql.QuoteHandle (ql.SimpleQuote (sigma)),   
                                               Flat_ts,    dividend_ts)
                 Helper.SetPricingEngine (engine)
                 Heston_helpers.Append (helper)
    In [15]: lm = ql.LevenbergMarquardt (1 e-8,    1 e-8,    1 e-8)
             Model.Calibrate (heston_helpers,    lm,    
                             Ql.EndCriteria (500,    50,    1.0 e-8,   1.0 e-8,    1.0 e-8))
             Theta,    kappa,    sigma,    rho,    v 0 = model.Params ()
    In [16]: print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
    Out[16]: theta = 0.1323,    kappa = 10.9809,    sigma = 4.0181,    rho = -0.3516,    v 0 = 0.0657
Let us look at the quality of calibration by pricing the options used in the calibration using the model and lets get an estimate of the relative error.
    In [17]: avg = 0.0
             Summary = []
             For i,    opt in enumerate (heston_helpers):
                 Err = (opt.ModelValue ()/opt.MarketValue () - 1.0)
                 Summary.Append ((
                     Strikes[i],    opt.MarketValue (),    
                     Opt.ModelValue (),    
                     100.0*(opt.ModelValue ()/opt.MarketValue () - 1.0)))
                 Avg += abs (err)
             Avg = avg*100.0/len (heston_helpers)
    In [18]: import pandas as pd
             Print ("Average Abs Error (%%) : %5.3 f" % (avg))
             Pd.DataFrame (
                 Summary,   
                 Columns=["Strikes",    "Market value",    "Model value",    "Relative error (%)"],   
                 Index=['']*len (summary))
    Out[18]: Average Abs Error (%) : 0.633
    Out[18]: 
  Strikes Market value Model value Relative error (%) --- --------- -------------- ------------- --------------------   527.50 44.678931 44.465565 -0.477555   560.46 55.052769 55.232883 0.327167   593.43 67.371524 67.665921 0.436975   626.40 80.934108 81.828303 1.104843   659.37 98.889639 97.751713 -1.150703   692.34 93.297706 92.551981 -0.799296   725.31 79.649513 79.448640 -0.252195   758.28 67.621458 67.972305 0.518840 ##### References { #chap31 . xhtml\_leanpub-auto-references} \\$$1\\$$ Mathias R. Fengler,    $$\*Arbitrage Free Smoothing of Implied Volatility Surface\*$$( https://core.ac.uk/download/files/153/6978470.pdf )
$$$${ #chap32 . xhtml}
\## $$23.$${. Section-number}Heston model parameter calibration in QuantLib Python & SciPy { #chap32 . xhtml\_leanpub-auto-heston-model-parameter-calibration-in-quantlib-python--scipy} I have discussed parameter calibration using the QuantLib solvers in the earlier chapter. In this chapter I want to show how you can use QuantLib Python and the Python SciPy library to do parameter calibration. This exercise opens us to use more robust solvers available in the Python open source libraries. QuantLib's strength is all financial models. SciPy's strength is all the solvers and numerical methods. So here,    I will show you how you can make the best of both worlds. We will start as usual by importing the modules.
    In [1]: import QuantLib as ql
            From math import pow,    sqrt
            Import numpy as np
            From scipy. Optimize import root
Let's construct some of the basic dependencies such as the yield and dividend term structures.
    In [2]: day_count = ql. Actual 365 Fixed ()
            Calendar = ql.UnitedStates ()
            Calculation_date = ql.Date (6,    11,    2015)
            Spot = 659.37
            Ql.Settings.Instance (). EvaluationDate = calculation_date
            Risk_free_rate = 0.01
            Dividend_rate = 0.0
            Yield_ts = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    risk_free_rate,    day_count))
            Dividend_ts = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    dividend_rate,    day_count))
Following is a sample grid of volatilities for different expiration and strikes.
    In [3]: expiration_dates = [
                Ql.Date (6,   12,   2015),    ql.Date (6,   1,   2016),    ql.Date (6,   2,   2016),   
                Ql.Date (6,   3,   2016),    ql.Date (6,   4,   2016),    ql.Date (6,   5,   2016),   
                Ql.Date (6,   6,   2016),    ql.Date (6,   7,   2016),    ql.Date (6,   8,   2016),   
                Ql.Date (6,   9,   2016),    ql.Date (6,   10,   2016),    ql.Date (6,   11,   2016),   
                Ql.Date (6,   12,   2016),    ql.Date (6,   1,   2017),    ql.Date (6,   2,   2017),   
                Ql.Date (6,   3,   2017),    ql.Date (6,   4,   2017),    ql.Date (6,   5,   2017),   
                Ql.Date (6,   6,   2017),    ql.Date (6,   7,   2017),    ql.Date (6,   8,   2017),   
                Ql.Date (6,   9,   2017),    ql.Date (6,   10,   2017),    ql.Date (6,   11,   2017)]
            Strikes = [527.50,    560.46,    593.43,    626.40,    659.37,    692.34,    725.31,    758.28]
            Data = [
            [0.37819,    0.34177,    0.30394,    0.27832,    0.26453,    0.25916,    0.25941,    0.26127],   
            [0.3445,    0.31769,    0.2933,    0.27614,    0.26575,    0.25729,    0.25228,    0.25202],   
            [0.37419,    0.35372,    0.33729,    0.32492,    0.31601,    0.30883,    0.30036,    0.29568],   
            [0.37498,    0.35847,    0.34475,    0.33399,    0.32715,    0.31943,    0.31098,    0.30506],   
            [0.35941,    0.34516,    0.33296,    0.32275,    0.31867,    0.30969,    0.30239,    0.29631],   
            [0.35521,    0.34242,    0.33154,    0.3219,    0.31948,    0.31096,    0.30424,    0.2984],   
            [0.35442,    0.34267,    0.33288,    0.32374,    0.32245,    0.31474,    0.30838,    0.30283],   
            [0.35384,    0.34286,    0.33386,    0.32507,    0.3246,    0.31745,    0.31135,    0.306],   
            [0.35338,    0.343,    0.33464,    0.32614,    0.3263,    0.31961,    0.31371,    0.30852],   
            [0.35301,    0.34312,    0.33526,    0.32698,    0.32766,    0.32132,    0.31558,    0.31052],   
            [0.35272,    0.34322,    0.33574,    0.32765,    0.32873,    0.32267,    0.31705,    0.31209],   
            [0.35246,    0.3433,    0.33617,    0.32822,    0.32965,    0.32383,    0.31831,    0.31344],   
            [0.35226,    0.34336,    0.33651,    0.32869,    0.3304,    0.32477,    0.31934,    0.31453],   
            [0.35207,    0.34342,    0.33681,    0.32911,    0.33106,    0.32561,    0.32025,    0.3155],   
            [0.35171,    0.34327,    0.33679,    0.32931,    0.3319,    0.32665,    0.32139,    0.31675],   
            [0.35128,    0.343,    0.33658,    0.32937,    0.33276,    0.32769,    0.32255,    0.31802],   
            [0.35086,    0.34274,    0.33637,    0.32943,    0.3336,    0.32872,    0.32368,    0.31927],   
            [0.35049,    0.34252,    0.33618,    0.32948,    0.33432,    0.32959,    0.32465,    0.32034],   
            [0.35016,    0.34231,    0.33602,    0.32953,    0.33498,    0.3304,    0.32554,    0.32132],   
            [0.34986,    0.34213,    0.33587,    0.32957,    0.33556,    0.3311,    0.32631,    0.32217],   
            [0.34959,    0.34196,    0.33573,    0.32961,    0.3361,    0.33176,    0.32704,    0.32296],   
            [0.34934,    0.34181,    0.33561,    0.32964,    0.33658,    0.33235,    0.32769,    0.32368],   
            [0.34912,    0.34167,    0.3355,    0.32967,    0.33701,    0.33288,    0.32827,    0.32432],   
            [0.34891,    0.34154,    0.33539,    0.3297,    0.33742,    0.33337,    0.32881,    0.32492]]
I have abstracted some of the repetitive methods into python functions. The function \`setup\_helpers\` will construct the Heston model helpers and returns an array of these objects. The \`cost\_function\_generator\` is a method to set the cost function and will be used by the SciPy modules. The \`calibration\_report\` lets us evaluate the quality of the fit. The \`setup\_model\` method initializes the \`HestonModel\` and the \`AnalyticHestonEngine\` prior to calibration.
    In [4]: def setup_helpers (engine,    expiration_dates,    strikes,    
                              Data,    ref_date,    spot,    yield_ts,    
                              Dividend_ts):
                Heston_helpers = []
                Grid_data = []
                For i,    date in enumerate (expiration_dates):
                    For j,    s in enumerate (strikes):
                        T = (date - ref_date )
                        P = ql.Period (t,    ql. Days)
                        Vols = data[i][j]
                        Helper = ql.HestonModelHelper (
                            P,    calendar,    spot,    s,    
                            Ql.QuoteHandle (ql.SimpleQuote (vols)),   
                            Yield_ts,    dividend_ts)
                        Helper.SetPricingEngine (engine)
                        Heston_helpers.Append (helper)
                        Grid_data.Append ((date,    s))
                Return heston_helpers,    grid_data
            Def cost_function_generator (model,    helpers,    norm=False):
                Def cost_function (params):
                    Params_ = ql.Array (list (params))
                    Model.SetParams (params_)
                    error = [h.calibrationError () for h in helpers]
                    If norm:
                        Return np.Sqrt (np.Sum (np.Abs (error)))
                    Else:
                        Return error
                Return cost_function
            Def calibration_report (helpers,    grid_data,    detailed=False):
                Avg = 0.0
                If detailed:
                    Print ("%15 s %25 s %15 s %15 s %20 s" % (
                        "Strikes",    "Expiry",    "Market Value",    
                        "Model Value",    "Relative Error (%)"))
                    Print ("="*100)
                For i,    opt in enumerate (helpers):
                    Err = (opt.ModelValue ()/opt.MarketValue () - 1.0)
                    Date,    strike = grid_data[i]
                    If detailed:
                        Print ("%15.2 f %25 s %14.5 f %15.5 f %20.7 f " % (
                            Strike,    str (date),    opt.MarketValue (),    
                            Opt.ModelValue (),    
                            100.0*(opt.ModelValue ()/opt.MarketValue () - 1.0)))
                    Avg += abs (err)
                Avg = avg*100.0/len (helpers)
                If detailed: print ("-"*100)
                Summary = "Average Abs Error (%%) : %5.9 f" % (avg)
                Print (summary)
                Return avg
            Def setup_model (_yield_ts,    _dividend_ts,    _spot,    
                            Init_condition=(0.02,   0.2,   0.5,   0.1,   0.01)):
                Theta,    kappa,    sigma,    rho,    v 0 = init_condition
                Process = ql.HestonProcess (_yield_ts,    _dividend_ts,    
                                          Ql.QuoteHandle (ql.SimpleQuote (_spot)),    
                                          V 0,    kappa,    theta,    sigma,    rho)
                Model = ql.HestonModel (process)
                Engine = ql.AnalyticHestonEngine (model) 
                Return model,    engine
            Summary= []
\##### Comparing Different Calibration Methods { #chap32 . xhtml\_leanpub-auto-comparing-different-calibration-methods} Solvers such as Levenberg-Marquardt find local minima and are very sensitive to the initial conditions. Depending on the starting conditions for your solver,    you could end up with a good set of parameters with good convergence or not so good set of parameters. We will look at two initial conditions for different solvers and see how the local minima solvers perform. We will compare this with differential evolution that looks for global minima. We will setup the Heston model with two different initial conditions: - theta,    kappa,    sigma,    rho,    v 0 = (0.02,    0.2,    0.5,    0.1,    0.01) - theta,    kappa,    sigma,    rho,    v 0 = (0.07,    0.5,    0.1,    0.1,    0.1) ##### Local Solvers { #chap32 . xhtml\_leanpub-auto-local-solvers} ###### Using QuantLib Levenberg-Marquardt Solver { #chap32 . xhtml\_leanpub-auto-using-quantlib-levenberg-marquardt-solver} As a first step,    let's look at QuantLib's Levenberg-Marquardt solver. The initial condition considered is \`theta,    kappa,    sigma,    rho,    v 0 = (0.02,   0.2,   0.5,   0.1,   0.01)\`
    In [5]: model 1,    engine 1 = setup_model (
                Yield_ts,    dividend_ts,    spot,    
                Init_condition=(0.02,   0.2,   0.5,   0.1,   0.01))
            Heston_helpers 1,    grid_data 1 = setup_helpers (
                Engine 1,    expiration_dates,    strikes,    data,    
                Calculation_date,    spot,    yield_ts,    dividend_ts
            )
            Initial_condition = list (model 1.Params ())
    In [6]: %%time
            Lm = ql.LevenbergMarquardt (1 e-8,    1 e-8,    1 e-8)
            Model 1.Calibrate (heston_helpers 1,    lm,    
                             Ql.EndCriteria (500,    300,    1.0 e-8,   1.0 e-8,    1.0 e-8))
            Theta,    kappa,    sigma,    rho,    v 0 = model 1.Params ()
            Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                  (theta,    kappa,    sigma,    rho,    v 0))
            Error = calibration_report (heston_helpers 1,    grid_data 1)
            Summary.Append (["QL LM 1",    error] + list (model 1.Params ()))
    Out[6]: theta = 0.1257,    kappa = 7.9150,    sigma = 1.8879,    rho = -0.3649,    v 0 = 0.0554
            Average Abs Error (%) : 3.015268051
            CPU times: user 2.98 s,    sys: 10 ms,    total: 2.99 s
            Wall time: 2.97 s
Methods like Levenberg-Marquardt solve for local minima and do not search for global minima. The solver is very sensitive to the initial conditions. Let's set a different set of initial conditions,    and see what happens below. The initial condition considered is \`theta,    kappa,    sigma,    rho,    v 0 = (0.07,   0.5,   0.1,   0.1,   0.1)\`
    In [7]: model 1,    engine 1 = setup_model (
                Yield_ts,    dividend_ts,    spot,    
                Init_condition=(0.07,   0.5,   0.1,   0.1,   0.1))
            Heston_helpers 1,    grid_data 1 = setup_helpers (
                Engine 1,    expiration_dates,    strikes,    data,    
                Calculation_date,    spot,    yield_ts,    dividend_ts
            )
            Initial_condition = list (model 1.Params ())
    In [8]: %%time
            Lm = ql.LevenbergMarquardt (1 e-8,    1 e-8,    1 e-8)
            Model 1.Calibrate (heston_helpers 1,    lm,    
                             Ql.EndCriteria (500,    300,    1.0 e-8,   1.0 e-8,    1.0 e-8))
            Theta,    kappa,    sigma,    rho,    v 0 = model 1.Params ()
            Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                  (theta,    kappa,    sigma,    rho,    v 0))
            Error = calibration_report (heston_helpers 1,    grid_data 1)
            Summary.Append (["QL LM 2",    error] + list (model 1.Params ()))
    Out[8]: theta = 0.0845,    kappa = 0.0000,    sigma = 0.1323,    rho = -0.5143,    v 0 = 0.0999
            Average Abs Error (%) : 11.007433024
            CPU times: user 3.08 s,    sys: 40 ms,    total: 3.12 s
            Wall time: 3.09 s
We see that the solver produces a 11% average of absolute error. This is not particularly great. ###### Using SciPy Levenberg-Marquardt Solver { #chap32 . xhtml\_leanpub-auto-using-scipy-levenberg-marquardt-solver} Here we are going to try the same exercise but using SciPy. SciPy has far more optimization,    minimization and root finding algorithms that are very robust. So by leveraging it,    we can take advantage of this rich set of options at hand.
    In [9]: model 2,    engine 2 = setup_model (
                Yield_ts,    dividend_ts,    spot,    
                Init_condition=(0.02,   0.2,   0.5,   0.1,   0.01))
            Heston_helpers 2,    grid_data 2 = setup_helpers (
                Engine 2,    expiration_dates,    strikes,    data,   
                Calculation_date,    spot,    yield_ts,    dividend_ts
            )
            Initial_condition = list (model 2.Params ())
    In [10]: %%time
             Cost_function = cost_function_generator (model 2,    heston_helpers 2)
             Sol = root (cost_function,    initial_condition,    method='lm')
             Theta,    kappa,    sigma,    rho,    v 0 = model 2.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 2,    grid_data 2)
             Summary.Append (["SciPy LM 1",    error] + list (model 2.Params ()))
    Out[10]: theta = 0.1257,    kappa = 7.9157,    sigma = 1.8879,    rho = -0.3649,    v 0 = 0.0554
             Average Abs Error (%) : 3.015252651
             CPU times: user 3.23 s,    sys: 10 ms,    total: 3.24 s
             Wall time: 3.24 s
The solution for this particular case seems to be fairly robust. Both solvers (QuantLib and SciPy) seem to have landed on more or less the same solution for this particular initial condition. Let's see how SciPy does for the second initial condition considered above - \`theta,    kappa,    sigma,    rho,    v 0 = (0.07,   0.5,   0.1,   0.1,   0.1)\`
    In [11]: model 2,    engine 2 = setup_model (
                 Yield_ts,    dividend_ts,    spot,   
                 Init_condition=(0.07,   0.5,   0.1,   0.1,   0.1))
             Heston_helpers 2,    grid_data 2 = setup_helpers (
                 Engine 2,    expiration_dates,    strikes,    data,   
                 Calculation_date,    spot,    yield_ts,    dividend_ts
             )
             Initial_condition = list (model 2.Params ())
    In [12]: %%time
             Cost_function = cost_function_generator (model 2,    heston_helpers 2)
             Sol = root (cost_function,    initial_condition,    method='lm')
             Theta,    kappa,    sigma,    rho,    v 0 = model 2.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 2,    grid_data 2)
             Summary.Append (["SciPy LM 2",    error] + list (model 2.Params ()))
    Out[12]: theta = 0.0482,    kappa = -0.5489,    sigma = 0.1980,    rho = -0.9995,    v 0 = 0.0906
             Average Abs Error (%) : 7.019499509
             CPU times: user 20.1 s,    sys: 0 ns,    total: 20.1 s
             Wall time: 20.1 s
For this particular case,    SciPy solver has performed significantly better. It would be inappropriate to make loud claims about SciPy's superiority based on one observation. Perhaps this calls for a more detailed study for later. ###### Using Least Squares Method { #chap32 . xhtml\_leanpub-auto-using-least-squares-method} If you want to use a simpler approach like least squares,    you can do that with SciPy. Here is how you would use it.
    In [13]: from scipy. Optimize import least_squares
    In [14]: model 3,    engine 3 = setup_model (
                 Yield_ts,    dividend_ts,    spot,    
                 Init_condition=(0.02,   0.2,   0.5,   0.1,   0.01))
             Heston_helpers 3,    grid_data 3 = setup_helpers (
                 Engine 3,    expiration_dates,    strikes,    data,   
                 Calculation_date,    spot,    yield_ts,    dividend_ts
             )
             Initial_condition = list (model 3.Params ())
    In [15]: %%time
             Cost_function = cost_function_generator (model 3,    heston_helpers 3)
             Sol = least_squares (cost_function,    initial_condition)
             Theta,    kappa,    sigma,    rho,    v 0 = model 3.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 3,    grid_data 3)
             Summary.Append (["SciPy LS 1",    error] + list (model 3.Params ()))
    Out[15]: theta = 0.1257,    kappa = 7.9158,    sigma = 1.8879,    rho = -0.3649,    v 0 = 0.0554
             Average Abs Error (%) : 3.015251175
             CPU times: user 4.15 s,    sys: 0 ns,    total: 4.15 s
             Wall time: 4.16 s
With the second initial condition:
    In [16]: model 3,    engine 3 = setup_model (
                 Yield_ts,    dividend_ts,    spot,    
                 Init_condition=(0.07,   0.5,   0.1,   0.1,   0.1))
             Heston_helpers 3,    grid_data 3 = setup_helpers (
                 Engine 3,    expiration_dates,    strikes,    data,   
                 Calculation_date,    spot,    yield_ts,    dividend_ts
             )
             Initial_condition = list (model 3.Params ())
    In [17]: %%time
             Cost_function = cost_function_generator (model 3,    heston_helpers 3)
             Sol = least_squares (cost_function,    initial_condition)
             Theta,    kappa,    sigma,    rho,    v 0 = model 3.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 3,    grid_data 3)
             Summary.Append (["SciPy LS 2",    error] + list (model 3.Params ()))
    Out[17]: theta = 3.1368,    kappa = 0.0000,    sigma = -0.0002,    rho = -0.0000,    v 0 = 1.5979
             Average Abs Error (%) : 5.096414042
             CPU times: user 26.6 s,    sys: 10 ms,    total: 26.6 s
             Wall time: 26.6 s
\##### Global Solvers { #chap32 . xhtml\_leanpub-auto-global-solvers} ###### Using Differential Evolution { #chap32 . xhtml\_leanpub-auto-using-differential-evolution} The above methods are more suited to finding local minima. One method that makes an attempt at searching for global minima is the differential evolution. Both QuantLib and SciPy have implementations of this method. SciPy however has a lot more bells and whistles to tune and calibrate the methodology. Let's take a look at SciPy's \`differential\_evolution\` methodology.
    In [18]: from scipy. Optimize import differential_evolution
    In [19]: model 4,    engine 4 = setup_model (yield_ts,    dividend_ts,    spot)
             Heston_helpers 4,    grid_data 4 = setup_helpers (
                 Engine 4,    expiration_dates,    strikes,    data,   
                 Calculation_date,    spot,    yield_ts,    dividend_ts
             )
             Initial_condition = list (model 4.Params ())
             Bounds = [(0,   1),    (0.01,   15),    (0.01,   1.),    (-1,   1),    (0,   1.0) ]
    In [20]: %%time
             Cost_function = cost_function_generator (
                 Model 4,    heston_helpers 4,    norm=True)
             Sol = differential_evolution (cost_function,    bounds,    maxiter=100)
             Theta,    kappa,    sigma,    rho,    v 0 = model 4.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 4,    grid_data 4)
             Summary.Append (["SciPy DE 1",    error] + list (model 4.Params ()))
    Out[20]: theta = 0.1235,    kappa = 4.8877,    sigma = 0.9421,    rho = -0.5867,    v 0 = 0.0797
             Average Abs Error (%) : 2.859256225
             CPU times: user 1 min 50 s,    sys: 40 ms,    total: 1 min 50 s
             Wall time: 1 min 50 s
In the above example,    I am setting the variable \`maxiter\` in order to limit the time taken. In production scenarios,    you may want to try a larger number or not provide any value and default to 1000. This can help search a larger area of the parameter space.
    In [21]: model 4,    engine 4 = setup_model (yield_ts,    dividend_ts,    spot)
             Heston_helpers 4,    grid_data 4 = setup_helpers (
                 Engine 4,    expiration_dates,    strikes,    data,   
                 Calculation_date,    spot,    yield_ts,    dividend_ts
             )
             Initial_condition = list (model 4.Params ())
             Bounds = [(0,   1),    (0.01,   15),    (0.01,   1.),    (-1,   1),    (0,   1.0) ]
    In [22]: %%time
             Cost_function = cost_function_generator (
                 Model 4,    heston_helpers 4,    norm=True)
             Sol = differential_evolution (cost_function,    bounds,    maxiter=100)
             Theta,    kappa,    sigma,    rho,    v 0 = model 4.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 4,    grid_data 4)
             Summary.Append (["SciPy DE 2",    error] + list (model 4.Params ()))
    Out[22]: theta = 0.1220,    kappa = 5.5238,    sigma = 0.9823,    rho = -0.5962,    v 0 = 0.0798
             Average Abs Error (%) : 2.868580939
             CPU times: user 1 min 41 s,    sys: 80 ms,    total: 1 min 41 s
             Wall time: 1 min 41 s
\###### Basin Hopping Algorithm { #chap32 . xhtml\_leanpub-auto-basin-hopping-algorithm} Here we will use the Basin Hopping (annealing-like) method to solve for the parameters. A couple things to make note here. The Basin Hopping method works best when used with a minimizer. Here I played with various minimizers and finally decided to use something that supports bounds checking. Without bounds checking,    I often ended with \`nan\` and did not have a meaningful solution in the end. I have chosen bounds based on a very basic reasoning. One needs careful reasoning to use appropriate bounds for the problem at hand.
    In [23]: from scipy. Optimize import basinhopping
    In [24]: class MyBounds (object):
                  Def __init__(self,    xmin=[0.,    0.01,   0.01,   -1,   0],    xmax=[1,   15,   1,   1,   1.0] ):
                      Self. Xmax = np.Array (xmax)
                      Self. Xmin = np.Array (xmin)
                  Def __call__(self,    **kwargs):
                      X = kwargs["x_new"]
                      Tmax = bool (np.All (x <= self. Xmax))
                      Tmin = bool (np.All (x >= self. Xmin))
                      Return tmax and tmin
             Bounds = [(0,   1),    (0.01,   15),    (0.01,   1.),    (-1,   1),    (0,   1.0) ]
    In [25]: model 5,    engine 5 = setup_model (
                 Yield_ts,    dividend_ts,    spot,   
                 Init_condition=(0.02,   0.2,   0.5,   0.1,   0.01))
             Heston_helpers 5,    grid_data 5 = setup_helpers (
                 Engine 5,    expiration_dates,    strikes,    data,   
                 Calculation_date,    spot,    yield_ts,    dividend_ts
             )
             Initial_condition = list (model 5.Params ())
    In [26]: %%time
             Mybound = MyBounds ()
             Minimizer_kwargs = {"method": "L-BFGS-B",    "bounds": bounds }
             Cost_function = cost_function_generator (
                 Model 5,    heston_helpers 5,    norm=True)
             Sol = basinhopping (cost_function,    initial_condition,    niter=5,   
                                Minimizer_kwargs=minimizer_kwargs,   
                                Stepsize=0.005,   
                                Accept_test=mybound,   
                                Interval=10)
             Theta,    kappa,    sigma,    rho,    v 0 = model 5.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 5,    grid_data 5)
             Summary.Append (["SciPy BH 1",    error] + list (model 5.Params ()))
    Out[26]: theta = 0.1234,    kappa = 5.0639,    sigma = 0.9895,    rho = -0.5723,    v 0 = 0.0796
             Average Abs Error (%) : 2.852458351
             CPU times: user 1 min 48 s,    sys: 100 ms,    total: 1 min 48 s
             Wall time: 1 min 48 s
    In [27]: model 5,    engine 5 = setup_model (
                 Yield_ts,    dividend_ts,    spot,   
                 Init_condition=(0.07,   0.5,   0.1,   0.1,   0.1))
             Heston_helpers 5,    grid_data 5 = setup_helpers (
                 Engine 5,    expiration_dates,    strikes,    data,   
                 Calculation_date,    spot,    yield_ts,    dividend_ts
             )
             Initial_condition = list (model 5.Params ())
    In [28]: %%time
             Mybound = MyBounds ()
             Minimizer_kwargs = {"method": "L-BFGS-B",    "bounds": bounds}
             Cost_function = cost_function_generator (
                 Model 5,    heston_helpers 5,    norm=True)
             Sol = basinhopping (cost_function,    initial_condition,    niter=5,   
                                Minimizer_kwargs=minimizer_kwargs,   
                                Stepsize=0.005,   
                                Accept_test=mybound,   
                                Interval=10)
             Theta,    kappa,    sigma,    rho,    v 0 = model 5.Params ()
             Print ("theta = %. 4 f,    kappa = %. 4 f,    sigma = %. 4 f,    rho = %. 4 f,    v 0 = %. 4 f" %
                   (theta,    kappa,    sigma,    rho,    v 0))
             Error = calibration_report (heston_helpers 5,    grid_data 5)
             Summary.Append (["SciPy BH 2",    error] + list (model 5.Params ()))
    Out[28]: theta = 0.1236,    kappa = 5.0315,    sigma = 0.9955,    rho = -0.5641,    v 0 = 0.0793
             Average Abs Error (%) : 2.851169399
             CPU times: user 1 min 32 s,    sys: 70 ms,    total: 1 min 32 s
             Wall time: 1 min 32 s
\##### Summary { #chap32 . xhtml\_leanpub-auto-summary} Here is a summary of all the results with the calibration error overall,    and the respective parameters. All the local minima methods give parameters that are very different based on the initial condition that we start with. This is different in contrary with the global minimization methods that all end up in more or less the same proximity of each other. The global solvers such as Differential Evolution and Basin Hopping are capable of finding the global minima and it is sometimes a question of computation resources. Here,    I have lower "iterations" set for these routines for faster solving. Even with such a short threshold,    we get fairly good solution set. I think it is premature to compare the effectiveness of different global solvers just based on the results here. The $$scipy optimize$$( http://docs.scipy.org/doc/scipy/reference/optimize.html ) package has detailed documentation with various tuning parameters. I haven't exploited the nuances much,    and is left as an exercise for the reader.
    In [29]: from pandas import DataFrame
             DataFrame (
                 Summary,   
                 Columns=["Name",    "Avg Abs Error",   "Theta",    "Kappa",    "Sigma",    "Rho",    "V 0"],   
                 Index=['']*len (summary))
    Out[29]: 
  Name Avg Abs Error Theta Kappa Sigma Rho V 0 --- ----------- --------------- ---------- --------------- ----------- ----------- ----------   QL LM 1 3.015268 0.125748 7.915000 e+00 1.887854 -0.364942 0.055397   QL LM 2 11.007433 0.084523 1.625740 e-08 0.132289 -0.514278 0.099928   SciPy LM 1 3.015253 0.125747 7.915687 e+00 1.887934 -0.364944 0.055394   SciPy LM 2 7.019500 0.048184 -5.489029 e-01 0.197958 -0.999547 0.090571   SciPy LS 1 3.015251 0.125747 7.915814 e+00 1.887949 -0.364944 0.055394   SciPy LS 2 5.096414 3.136774 4.896844 e-06 -0.000245 -0.000010 1.597904   SciPy DE 1 2.859256 0.123468 4.887678 e+00 0.942144 -0.586662 0.079667   SciPy DE 2 2.868581 0.121951 5.523823 e+00 0.982323 -0.596156 0.079790   SciPy BH 1 2.852458 0.123403 5.063875 e+00 0.989452 -0.572259 0.079601   SciPy BH 2 2.851169 0.123572 5.031477 e+00 0.995536 -0.564053 0.079288
$$$${ #chap33 . xhtml}
\## $$24.$${. Section-number}Valuing European and American options { #chap33 . xhtml\_leanpub-auto-valuing-european-and-american-options} I have written about option pricing earlier. The $$introduction to option pricing$$( http://gouthamanbalaraman.com/blog/option-model-handbook-part-I-introduction-to-option-models.html ) gave an overview of the theory behind option pricing. The post on $$introduction to binomial trees$$( http://gouthamanbalaraman.com/blog/option-model-handbook-part-II-introduction-to-binomial-trees.html ) outlined the binomial tree method to price options. In this post,    we will use QuantLib and the Python extension to illustrate a simple example. Here we are going to price a European option using the Black-Scholes-Merton formula. We will price them again using the Binomial tree and understand the agreement between the two.
    In [1]: import QuantLib as ql
            Import utils
            %matplotlib inline
\##### European Option { #chap33 . xhtml\_leanpub-auto-european-option} Let us consider a European call option for AAPL with a strike price of 130 maturing on 15 th Jan,    2016. Let the spot price be 127.62. The volatility of the underlying stock is know to be 20%,    and has a dividend yield of 1.63%. Let's value this option as of 8 th May,    2015.
    In [2]: maturity_date = ql.Date (15,    1,    2016)
            Spot_price = 127.62
            Strike_price = 130
            Volatility = 0.20 # the historical vols for a year
            Dividend_rate =  0.0163
            Option_type = ql. Option. Call
            Risk_free_rate = 0.001
            Day_count = ql. Actual 365 Fixed ()
            Calendar = ql.UnitedStates ()
            Calculation_date = ql.Date (8,    5,    2015)
            Ql.Settings.Instance (). EvaluationDate = calculation_date
We construct the European option here.
    In [3]: payoff = ql.PlainVanillaPayoff (option_type,    strike_price)
            Exercise = ql.EuropeanExercise (maturity_date)
            European_option = ql.VanillaOption (payoff,    exercise)
The Black-Scholes-Merton process is constructed here.
    In [4]: spot_handle = ql.QuoteHandle (
                Ql.SimpleQuote (spot_price)
            )
            Flat_ts = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    
                               Risk_free_rate,    
                               Day_count)
            )
            Dividend_yield = ql.YieldTermStructureHandle (
                Ql.FlatForward (calculation_date,    
                               Dividend_rate,    
                               Day_count)
            )
            Flat_vol_ts = ql.BlackVolTermStructureHandle (
                Ql.BlackConstantVol (calculation_date,    
                                    Calendar,    
                                    Volatility,    
                                    Day_count)
            )
            Bsm_process = ql.BlackScholesMertonProcess (spot_handle,    
                                                       Dividend_yield,    
                                                       Flat_ts,    
                                                       Flat_vol_ts)
Lets compute the theoretical price using the \`AnalyticEuropeanEngine\`.
    In [5]: european_option.SetPricingEngine (ql.AnalyticEuropeanEngine (bsm_process))
            Bs_price = european_option.NPV ()
            Print ("The theoretical price is %lf" % bs_price)
    Out[5]: The theoretical price is 6.749272
Lets compute the price using the binomial-tree approach.
    In [6]: def binomial_price (option,    bsm_process,    steps):
                Binomial_engine = ql.BinomialVanillaEngine (bsm_process,    "crr",    steps)
                Option.SetPricingEngine (binomial_engine)
                Return option.NPV ()
            Steps = range (2,    200,    1)
            Prices = [binomial_price (european_option,    bsm_process,    step) for step in steps]
In the plot below,    we show the convergence of binomial-tree approach by comparing its price with the BSM price.
    In [7]: fig,    ax = utils.Plot ()
            Ax.Plot (steps,    prices,    label="Binomial Tree Price",    lw=2,    alpha=0.6)
            Ax.Plot ([0,   200],   [bs_price,    bs_price],    "--",    label="BSM Price",    lw=2,    alpha=0.6)
            Ax. Set_xlabel ("Steps",    size=14)
            Ax. Set_ylabel ("Price",    size=14)
            Ax. Set_title ("Binomial Tree Price For Varying Steps",    size=14)
            Ax.Legend ();
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/option_pricing-7.png)
::: ##### American Option { #chap33 . xhtml\_leanpub-auto-american-option} The above exercise was pedagogical,    and introduces one to pricing using the binomial tree approach and compared with Black-Scholes. As a next step,    we will use the Binomial pricing to value American options. The construction of an American option is similar to the construction of \`European\` option discussed above. The one main difference is the use of \`AmericanExercise\` instead of \`EuropeanExercise\` use above.
    In [8]: payoff = ql.PlainVanillaPayoff (option_type,    strike_price)
            Settlement = calculation_date
            Am_exercise = ql.AmericanExercise (settlement,    maturity_date)
            American_option = ql.VanillaOption (payoff,    am_exercise)
Once we have constructed the \`american\_option\` object,    we can price them using the Binomial trees as done above. We use the same function we constructed above.
    In [9]: steps = range (2,    200,    1)
            Prices = [binomial_price (american_option,    bsm_process,    step) for step in steps]
    In [10]: fig,    ax = utils.Plot ()
             Ax.Plot (steps,    prices,    label="Binomial Tree Price",    lw=2,    alpha=0.6)
             Ax.Plot ([0,   200],   [bs_price,    bs_price],    "--",    label="BSM Price",    lw=2,    alpha=0.6)
             Ax. Set_xlabel ("Steps",    size=14)
             Ax. Set_ylabel ("Price",    size=14)
             Ax. Set_title ("Binomial Tree Price For Varying Steps",    size=14)
             Ax.Legend ();
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/option_pricing-10.png)
::: Above,    we plot the price of the American option as a function of steps used in the binomial tree,    and compare with that of the Black-Scholes price for the European option with all other variables remaining the same. The binomial tree converges as the number of steps used in pricing increases. American option is valued more than the European BSM price because of the fact that it can be exercised anytime during the course of the option. ##### Conclusion { #chap33 . xhtml\_leanpub-auto-conclusion-4} In this chapter we learnt about valuing European and American options using the binomial tree method.
$$$${ #chap34 . xhtml}
\## $$25.$${. Section-number}Valuing options on commodity futures using the Black formula { #chap34 . xhtml\_leanpub-auto-valuing-options-on-commodity-futures-using-the-black-formula} The Black-Scholes equation is the well known model to price equity European options. In the case of equities,    the spot price fluctuates and hence the intuition to model as a stochastic process makes sense. In the case of commodities,    however,    the spot price does not fluctuate as much,    and hence cannot be modeled as a stochastic process to value options on commodities. In the 1976 paper \\$$1\\$$,    Fischer Black addressed this problem by modeling the futures price,    which demonstrates fluctuations,    as the lognormal stochastic process. The futures price at time !$$t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_141. Png){. Inline-equation width="5"},    !$$F\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_142. Png){. Inline-equation width="15"} with a is modeled as: !$$dF\_t = \\\\sigma\_t F\_t dW$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_143. Png){. Block-equation width="113"} where !$$\\\\sigma\_t$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_144. Png){. Inline-equation width="14"} is the volatility of the underlying,    and !$$dW$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_145. Png){. Inline-equation width="28"} is the Weiner process. The value of an option at strike !$$K$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_146. Png){. Inline-equation width="15"},    maturing at !$$T$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_147. Png){. Inline-equation width="12"},    risk free rate !$$r$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_148. Png){. Inline-equation width="7"} with volatility !$$\\\\sigma$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_149. Png){. Inline-equation width="9"} of the underlying is given by the closed form expression: !$$\\\\begin{eqnarray} c &=& e\\^{-r T} \\$$FN (d\_1) - KN (d\_2)\\$$ \\\\\\\\ p &=& e\\^{-r T} \\$$KN (-d\_2) - FN (-d\_1)\\$$ \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_150. Png){. Block-equation width="444"} where !$$\\\\begin{eqnarray} d\_1 &=& \\\\frac{\\\\ln (F/K) + (\\\\sigma\\^2/2) T}{\\\\sigma\\\\sqrt{T}} \\\\nonumber \\\\\\\\ d\_2 &=& \\\\frac{\\\\ln (F/K) - (\\\\sigma\\^2/2) T}{\\\\sigma\\\\sqrt{T}} = d\_1 - \\\\sigma\\\\sqrt{T} \\\\end{eqnarray}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_151. Png){. Block-equation width="464"} This formula can be easily used to price caps,    swaptions,    futures options contract. Here we will use QuantLib to price the options on commodity futures.
    In [1]: import QuantLib as ql
            Import math
    In [2]: calendar = ql.UnitedStates ()
            Business_convention = ql. ModifiedFollowing
            Settlement_days = 0
            Day_count = ql.ActualActual ()
\##### Option on Treasury Futures Contract { #chap34 . xhtml\_leanpub-auto-option-on-treasury-futures-contract} Options on treasury futures (10 Yr Note TYF 6 C 119) can be valued using the Black formula. Let us value a Call option maturing on December 24,    2015,    with a strike of 119. The current futures price is 126.95,    and the volatility is 11.567%. The risk free rate as of December 1,    2015 is 0.105%. Let us value this Call option as of December 1,    2015.
    In [3]: interest_rate = 0.00105
            Calc_date = ql.Date (1,   12,   2015)
            Yield_curve = ql.FlatForward (calc_date,    
                                         Interest_rate,   
                                         Day_count,   
                                         Ql. Compounded,   
                                         Ql. Continuous)
    In [4]: ql.Settings.Instance (). EvaluationDate = calc_date
            Option_maturity_date = ql.Date (24,   12,   2015)
            Strike = 119
            Spot = 126.953# futures price
            Volatility = 11.567/100.
            Flavor = ql. Option. Call
            Discount = yield_curve.Discount (option_maturity_date)
            Strikepayoff = ql.PlainVanillaPayoff (flavor,    strike)
            T = yield_curve.DayCounter (). YearFraction (calc_date,    
                                                      Option_maturity_date)
            Stddev = volatility*math.Sqrt (T)
            Black = ql.BlackCalculator (strikepayoff,    
                                       Spot,    
                                       Stddev,    
                                       Discount)
    In [5]: print ("%-20 s: %4.4 f" %("Option Price",    black.Value ()))
            Print ("%-20 s: %4.4 f" %("Delta",    black.Delta (spot)))
            Print ("%-20 s: %4.4 f" %("Gamma",    black.Gamma (spot)))
            Print ("%-20 s: %4.4 f" %("Theta",    black.Theta (spot,    T)))
            Print ("%-20 s: %4.4 f" %("Vega",    black.Vega (T)))
            Print ("%-20 s: %4.4 f" %("Rho",    black.Rho (T)))
    Out[5]: Option Price        : 7.9686
            Delta               : 0.9875
            Gamma               : 0.0088
            Theta               : -0.9356
            Vega                : 1.0285
            Rho                 : 7.3974
\##### Natural Gas Futures Option { #chap34 . xhtml\_leanpub-auto-natural-gas-futures-option} I saw $$this$$( http://quantlib0.\1.n7.nabble.com/Quantlib-methods-for-option-pricing-td17018.html ) question on the QuantLib users group. Thought I will add this example as well. Call option with a 3.5 strike,    spot 2.919,    volatility 0.4251. The interest rate is 0.15%.
    In [6]: interest_rate = 0.0015
            Calc_date = ql.Date (23,   9,   2015)
            Yield_curve = ql.FlatForward (calc_date,    
                                         Interest_rate,   
                                         Day_count,   
                                         Ql. Compounded,   
                                         Ql. Continuous)
    In [7]: ql.Settings.Instance (). EvaluationDate = calc_date
            T = 96.12/365.
            Strike = 3.5
            Spot = 2.919
            Volatility = 0.4251
            Flavor = ql. Option. Call
            Discount = yield_curve.Discount (T)
            Strikepayoff = ql.PlainVanillaPayoff (flavor,    strike)
            Stddev = volatility*math.Sqrt (T)
            Black = ql.BlackCalculator (strikepayoff,    spot,    stddev,    discount)
    In [8]: print ("%-20 s: %4.4 f" %("Option Price",    black.Value ()))
            Print ("%-20 s: %4.4 f" %("Delta",    black.Delta (spot)))
            Print ("%-20 s: %4.4 f" %("Gamma",    black.Gamma (spot)))
            Print ("%-20 s: %4.4 f" %("Theta",    black.Theta (spot,    T)))
            Print ("%-20 s: %4.4 f" %("Vega",    black.Vega (T)))
            Print ("%-20 s: %4.4 f" %("Rho",    black.Rho (T)))
    Out[8]: Option Price        : 0.0789
            Delta               : 0.2347
            Gamma               : 0.4822
            Theta               : -0.3711
            Vega                : 0.4600
            Rho                 : 0.1597
\##### Conclusion { #chap34 . xhtml\_leanpub-auto-conclusion-5} In this notebook,    I demonstrated how Black formula can be used to value options on commodity futures. It is worth pointing out that different vendors usually have different scaling conventions when it comes to reporting Greeks. One would needs to take that into account when comparing the values shown by QuantLib with that of other vendors. ##### References { #chap34 . xhtml\_leanpub-auto-references-1} \\$$1\\$$ Fischer Black,    \*The pricing of commodity contracts\*,    Journal of Financial Economics,    (3) 167-179 (1976)
$$$${ #chap35 . xhtml}
\## $$26.$${. Section-number}Defining rho for the Black process { #chap35 . xhtml\_leanpub-auto-defining-rho-for-the-black-process} (Based on a question by DPaulino on the QuantLib mailing list. Thanks!)
    In [1]: import QuantLib as ql
    In [2]: today = ql.Date (24,   12,   2016)
            Ql.Settings.Instance (). EvaluationDate = today
\##### The dangers of generalization { #chap35 . xhtml\_leanpub-auto-the-dangers-of-generalization} QuantLib provides a few classes to represent specific cases of the Black-Scholes-Merton process; for instance,    the \`BlackScholesProcess\` class assumes that there are no dividends,    and the \`BlackProcess\` class that the cost of carry is equal to 0. It is the latter,    or rather a glitch in it,    that is the subject of this notebook. All such classes inherit from a base \`GeneralizedBlackScholesProcess\` class (I know,    we're not that good at naming things) that models the more general case in which the underlying stock has a continuous dividend yield. The specific cases are implemented by inheriting from this class and setting a constraint on the dividends !$$q (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_152. Png){. Inline-equation width="27"}: for the Black-Scholes process,    !$$q (t) = 0$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_153. Png){. Inline-equation width="62"}; and for the Black process,    !$$q (t) = r (t)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_154. Png){. Inline-equation width="81"},    which makes the cost of carry !$$b$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_155. Png){. Inline-equation width="7"} equal 0. We can check the constraint by creating two instances of such processes. Here are the quotes and term structures we'll use to model the dynamics of the underlying:
    In [3]: u = ql.SimpleQuote (100.0)
            R = ql.SimpleQuote (0.01)
            Sigma = ql.SimpleQuote (0.20)
            Risk_free_curve = ql.FlatForward (today,    ql.QuoteHandle (r),    ql. Actual 360 ())
            Volatility = ql.BlackConstantVol (today,    ql.TARGET (),   
                                             Ql.QuoteHandle (sigma),    ql. Actual 360 ())
The constructor of the \`BlackScholesProcess\` class doesn't take a dividend yield,    and sets it to 0 internally:
    In [4]: process_1 = ql.BlackScholesProcess (
                Ql.QuoteHandle (u),   
                Ql.YieldTermStructureHandle (risk_free_curve),   
                Ql.BlackVolTermStructureHandle (volatility))
            Print (process_1.DividendYield (). ZeroRate (1.0,    ql. Continuous))
    Out[4]: 0.000000 % Actual/365 (Fixed) continuous compounding
The constructor of the \`BlackProcess\` class doesn't take a dividend yield either,    and sets its handle as a copy of the risk free handle:
    In [5]: process_2 = ql.BlackProcess (ql.QuoteHandle (u),   
                                        Ql.YieldTermStructureHandle (risk_free_curve),   
                                        Ql.BlackVolTermStructureHandle (volatility))
            Print (process_2.RiskFreeRate (). ZeroRate (1.0,    ql. Continuous))
            Print (process_2.DividendYield (). ZeroRate (1.0,    ql. Continuous))
    Out[5]: 1.000000 % Actual/360 continuous compounding
            1.000000 % Actual/360 continuous compounding
Now,    the above processes can be used to price options on underlyings behaving accordingly; the first process describes,    e.g.,    a stock that doesn't pay any dividends,    and the second describes,    e.g.,    a futures. The classes to use are the same: \`EuropeanOption\` for the instrument and \`AnalyticEuropeanEngine\` for the pricing engine. The constructor of the engine takes an instance of \`GeneralizedBlackScholesProcess\`,    to which both our processes can be converted implicitly.
    In [6]: option_1 = ql.EuropeanOption (ql.PlainVanillaPayoff (ql. Option. Call,    100.0),   
                                         Ql.EuropeanExercise (today+100))
            Option_1.SetPricingEngine (ql.AnalyticEuropeanEngine (process_1))
            Print (option_1.NPV ())
    Out[6]: 4.337597216336533
    In [7]: option_2 = ql.EuropeanOption (ql.PlainVanillaPayoff (ql. Option. Call,    100.0),   
                                         Ql.EuropeanExercise (today+100))
            Option_2.SetPricingEngine (ql.AnalyticEuropeanEngine (process_2))
            Print (option_2.NPV ())
    Out[7]: 4.191615257389808
So far,    so good. However,    we can see the glitch when we ask the options for their Greeks. With this particular engine,    they're able to calculate them by using closed formulas (none other,    of course,    that those expressing the derivatives of the Black-Scholes-Merton formula). As I described in a previous notebook,    we can also calculate the Greeks numerically,    by bumping the inputs and repricing the option. If we compare the two approaches,    they should yield approximately the same results. For convenience,    I'll define a utility function to calculate numerical Greeks. It takes the option,    the quote to change and the amplitude of the bump.
    In [8]: def greek (option,    quote,    dx):
                X 0 = quote.Value ()
                Quote.SetValue (x 0+dx)
                P_u = option.NPV ()
                Quote.SetValue (x 0-dx)
                P_d = option.NPV ()
                Quote.SetValue (x 0)
                Return (P_u-P_d)/(2*dx)
By passing different quotes,    we can calculate different Greeks. Bumping the underlying value will give us the delta,    which we can compare to the analytic result:
    In [9]: print (option_1.Delta ())
            Print (greek (option_1,    u,    0.01))
    Out[9]: 0.5315063340142601
            0.531506323010289
    In [10]: print (option_2.Delta ())
             Print (greek (option_2,    u,    0.01))
    Out[10]: 0.5195711146255227
             0.5195711052036867
Bumping the volatility gives us the vega...
    In [11]: print (option_1.Vega ())
             Print (greek (option_1,    sigma,    0.001))
    Out[11]: 20.96050033373808
             20.960499909565833
    In [12]: print (option_2.Vega ())
             Print (greek (option_2,    sigma,    0.001))
    Out[12]: 20.938677847075486
             20.938677605407463
... And bumping the risk-free rate will give us the rho.
    In [13]: print (option_1.Rho ())
             Print (greek (option_1,    r,    0.001))
    Out[13]: 13.559176718080407
             13.55917453385036
    In [14]: print (option_2.Rho ())
             Print (greek (option_2,    r,    0.001))
    Out[14]: 13.268193390322908
             -1.1643375864700545
Whoops. Not what you might have expected. ##### What's happening here? { #chap35 . xhtml\_leanpub-auto-whats-happening-here} The problem is that the engine works with a generic process,    and !$$\\\\rho$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_156. Png){. Inline-equation width="8"} is calculated as !$$\\\\rho = \\\\frac{\\\\partial}{\\\\partial r} C (u,    r,    q,    \\\\sigma)$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_157. Png){. Block-equation width="146"} where !$$C$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_158. Png){. Inline-equation width="13"} is the Black-Scholes-Merton formula for the value of the call option. However,    not knowing about the specific process type we passed,    the engine doesn't know about the constraint we set on the underlying variables: in this case,    that !$$q = q (r) = r$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_159. Png){. Inline-equation width="97"}. Therefore,    the correct value for !$$\\\\rho$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_160. Png){. Inline-equation width="8"} should be !$$\\\\rho = \\\\frac{d}{dr} C (u,    r,    q (r),    \\\\sigma) = \\\\frac{\\\\partial C}{\\\\partial r} + \\\\frac{\\\\partial C}{\\\\partial q} \\\\cdot \\\\frac{\\\\partial q}{\\\\partial r} = \\\\frac{\\\\partial C}{\\\\partial r} + \\\\frac{\\\\partial C}{\\\\partial q}.$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_161. Png){. Block-equation width="419"} which is the sum of the rho as defined in the engine and the dividend rho. We can verify this by comparing the above with the numerical Greek:
    In [15]: print (option_2.Rho () + option_2.DividendRho ())
             Print (greek (option_2,    r,    0.001))
    Out[15]: -1.1643375714971693
             -1.1643375864700545
Now: is this a bug in the engine? Well,    it might be argued. The engine might detect the case of a Black process and change the calculation of rho accordingly; it's kind of a hack,    and there goes the genericity,    but it's possible to implement. However,    the above might also happen with a usually well-behaved process if we use the same term structure for !$$r$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_162. Png){. Inline-equation width="7"} and !$$q$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_163. Png){. Inline-equation width="7"}:
    In [16]: process_3 = ql.BlackScholesMertonProcess (
                 Ql.QuoteHandle (u),   
                 Ql.YieldTermStructureHandle (risk_free_curve),   
                 Ql.YieldTermStructureHandle (risk_free_curve),   
                 Ql.BlackVolTermStructureHandle (volatility))
             Option_3 = ql.EuropeanOption (ql.PlainVanillaPayoff (ql. Option. Call,    100.0),   
                                          Ql.EuropeanExercise (today+100))
             Option_3.SetPricingEngine (ql.AnalyticEuropeanEngine (process_3))
    In [17]: print (option_3.Delta ())
             Print (greek (option_3,    u,    0.01))
    Out[17]: 0.5195711146255227
             0.5195711052036867
    In [18]: print (option_3.Rho ())
             Print (greek (option_3,    r,    0.001))
             Print (option_3.Rho () + option_3.DividendRho ())
    Out[18]: 13.268193390322908
             -1.1643375864700545
             -1.1643375714971693
The issue is not even limited to processes. You're defining a discount curve as the risk-free rate plus a credit spread? Bumping the risk-free rate will modify both,    and your sensitivities will be affected accordingly (even though in this case the effect is probably what you wanted). In any case,    this is something you should be aware of.
$$$${ #chap36 . xhtml}
\## $$27.$${. Section-number}Using curves with different day-count conventions { #chap36 . xhtml\_leanpub-auto-using-curves-with-different-day-count-conventions} (Based on $$a question by Vinod Rajakumar$$( https://sourceforge.net/p/quantlib/mailman/message/36015671/ ) on the QuantLib mailing list. Thanks!) Like a number of other notebooks,    this one describes a glitch in the library that you might want to be aware of. ##### The problem { #chap36 . xhtml\_leanpub-auto-the-problem-1} Let's say we're pricing an option. We've already seen it in other notebooks,    so I'll go through the setup without much details:
    In [1]: import QuantLib as ql
            Import math
    In [2]: today = ql.Date (27,    ql. July,    2018)
            Ql.Settings.Instance (). EvaluationDate = today
            Calendar = ql.UnitedStates (ql. UnitedStates. NYSE)
    In [3]: exercise_date = today+ql.Period (3,    ql. Months)
            Strike = 100.0
            Option = ql.EuropeanOption (ql.PlainVanillaPayoff (ql. Option. Call,    strike),   
                                       Ql.EuropeanExercise (exercise_date))
I'll set up handles for the needed curves,    so we can change them later...
    In [4]: u = ql.RelinkableQuoteHandle ()
            R = ql.RelinkableYieldTermStructureHandle ()
            Sigma = ql.RelinkableBlackVolTermStructureHandle ()
    In [5]: process = ql.BlackScholesProcess (u,    r,    sigma)
... And I'll use the process above to instantiate two different engines: the first uses the analytic Black-Scholes formula,    and the second a finite-difference model.
    In [6]: analytic_engine = ql.AnalyticEuropeanEngine (process)
            Fd_engine = ql.FdBlackScholesVanillaEngine (process,    1000,    1000)
Now we get to pricing the option. First,    I'll link the risk-free rate and the volatility to two constant curves with the same day-count convention (in this case,    Actual/365 fixed). Let's say the risk-free rate is 0% and the volatility is 20%.
    In [7]: u.linkTo (ql.SimpleQuote (100.0))
            r.linkTo (ql.FlatForward (today,    0.0,    ql. Actual 365 Fixed ()))
            Sigma.LinkTo (ql.BlackConstantVol (today,    calendar,    0.20,    ql. Actual 365 Fixed ()))
With this setup,    the two engines give the same result (within numerical error) and everybody is happy:
    In [8]: option.SetPricingEngine (analytic_engine)
            Option.NPV ()
    Out[8]: 4.004101982740124
    In [9]: option.SetPricingEngine (fd_engine)
            Option.NPV ()
    Out[9]: 4.004120663979733
However,    things are not always so simple. For instance,    the volatility might have been quoted with a different day-count convention,    as is practice on some markets. Let's say,    for instance,    that the 20% volatility was quoted based on the commonly used business/252 convention.
    In [10]: sigma.LinkTo (
                 Ql.BlackConstantVol (today,    calendar,    0.20,    ql. Business 252 (calendar)))
In this case,    we're not so lucky; the results from the two engines differ significantly.
    In [11]: option.SetPricingEngine (analytic_engine)
             Option.NPV ()
    Out[11]: 4.050510859367279
    In [12]: option.SetPricingEngine (fd_engine)
             Option.NPV ()
    Out[12]: 4.004120663979733
By looking at the numbers,    we can see that analytic engine reacts to the change,    while the finite-differences engine doesn't. ##### What is happening? { #chap36 . xhtml\_leanpub-auto-what-is-happening} This is not something that could be expected; unfortunately,    it's an artifact of the implementation and could only be deduced by looking at the code. Specifically,    the analytic engine is able to include in the calculation the day-count convention of the volatility curve,    while the FD model is forced to use one single time grid and can't account for different conventions. More in detail,    what the FD engine does is to ask the curve for the volatility at the exercise date...
    In [13]: vol = sigma.BlackVol (exercise_date,    strike)
             Vol
    Out[13]: 0.2
... And use it on the grid. However,    the time grid on which the FD model works uses the day-count convention of the risk-free rates,    resulting in a time to maturity that is inconsistent with the volatility quote...
    In [14]: T_vol = sigma.DayCounter (). YearFraction (today,    exercise_date)
             T_vol
    Out[14]: 0.25793650793650796
    In [15]: T_grid = r.dayCounter (). YearFraction (today,    exercise_date)
             T_grid
    Out[15]: 0.25205479452054796
... And therefore the wrong value for the variance of the stock price:
    In [16]: vol*vol*T_grid
    Out[16]: 0.01008219178082192
    In [17]: var = sigma.BlackVariance (exercise_date,    strike)
             Var
    Out[17]: 0.01031746031746032
\##### An attempt at a solution { #chap36 . xhtml\_leanpub-auto-an-attempt-at-a-solution} In this case,    and having assessed the problem,    we can work around the problem; that is,    we can find the volatility that,    together with the day-count convention used on the grid,    gives the correct variance.
    In [18]: vol = math.Sqrt (var/T_grid)
             Vol
    Out[18]: 0.20232004929429467
This synthetic value can be used to build a volatility curve with the same day-count convention as the rate. This allows the FD engine to return a more correct value.
    In [19]: sigma.LinkTo (ql.BlackConstantVol (today,    calendar,    vol,    ql. Actual 365 Fixed ()))
    In [20]: option.SetPricingEngine (analytic_engine)
             Option.NPV ()
    Out[20]: 4.050510859367279
    In [21]: option.SetPricingEngine (fd_engine)
             Option.NPV ()
    Out[21]: 4.0505297872982675
Of course,    this is more cumbersome if the volatility is not flat; you might have to convert multiple values if you're interpolating them,    or sample multiple values and then convert them if the curve is of some other kind. On the whole,    it is unfortunate that the implementation is leaking into the use of the engine. We still don't have a solution,    though. What I can suggest is,    when possible,    to perform sanity checks like the previous comparison between engine results. This will give you information on the underlying implementation and the precautions you'll have to take when a comparison is not possible (such as,    for instance,    when the option is American and there's no corresponding analytic engine).
$$$${ #chap37 . xhtml}
\# Bonds { #chap37 . xhtml\_leanpub-auto-bonds}
$$$${ #chap38 . xhtml}
\## $$28.$${. Section-number}Modeling fixed rate bonds { #chap38 . xhtml\_fixedratebonds} In this chapter we will consider a simple example to model fixed rate bonds. Let's consider a hypothetical bond with a par value of 100,    that pays 6% coupon semi-annually issued on January 15 th,    2015 and set to mature on January 15 th,    2016. The bond will pay a coupon on July 15 th,    2015 and January 15 th,    2016. The par amount of 100 will also be paid on the January 15 th,    2016. To make things simpler,    lets assume that we know the spot rates of the treasury as of January 15 th,    2015. The annualized spot rates are 0.5% for 6 months and 0.7% for 1 year point. Lets calculate the net present value of the cash flows directly as shown below.
    In [1]: 3/pow (1+0.005,    0.5) + (100 + 3)/(1+0.007)
    Out[1]: 105.27653992490681
Here,    we discounted the coupon and par payments with the appropriate spot rates. Now we will replicate this calculation using the QuantLib framework. Let's start by importing the \`QuantLib\` module.
    In [2]: import QuantLib as ql
As a first step,    we need to construct a yield curve with the given spot rates. This is done using the \`ZeroCurve\` class as discussed in an $$earlier chapter$$( #chap14 . xhtml\_yc-construction).
    In [3]: calc_date = ql.Date (15,    1,    2015)
            Ql.Settings.Instance (). EvaluationDate = calc_date
            Spot_dates = [ql.Date (15,    1,    2015),    ql.Date (15,    7,    2015),    ql.Date (15,    1,    2016)]
            Spot_rates = [0.0,    0.005,    0.007]
            Day_count = ql. Thirty 360 ()
            Calendar = ql.UnitedStates ()
            Interpolation = ql.Linear ()
            Compounding = ql. Compounded
            Compounding_frequency = ql. Annual
            Spot_curve = ql.ZeroCurve (spot_dates,    spot_rates,    day_count,    calendar,    
                                      Interpolation,    compounding,    compounding_frequency)
            Spot_curve_handle = ql.YieldTermStructureHandle (spot_curve)
As a next step,    we are going to build a fixed rate bond object. In order to construct the \`FixedRateBond\` object,    we will create a schedule for the coupon payments. Creation of \`Schedule\` object was discussed in an $$earlier chapter$$( #chap04 . xhtml\_quantlib-basics).
    In [4]: issue_date = ql.Date (15,    1,    2015)
            Maturity_date = ql.Date (15,    1,    2016)
            Tenor = ql.Period (ql. Semiannual)
            Calendar = ql.UnitedStates ()
            Business_convention = ql. Unadjusted
            Date_generation = ql. DateGeneration. Backward
            Month_end = False
            Schedule = ql.Schedule (issue_date,    maturity_date,    tenor,    
                                   Calendar,    business_convention,    
                                   Business_convention,    date_generation,    
                                   Month_end)
Let us print the schedule to check if it is in agreement with what we expect it to be.
    In [5]: list (schedule)
    Out[5]: [Date (15,   1,   2015),    Date (15,   7,   2015),    Date (15,   1,   2016)]
Now that we have the schedule,    we can create the \`FixedRateBond\` object. The \`FixedRateBond\` constructor has the following signature.
    FixedRateBond (Natural settlementDays,   
                  Real faceAmount,   
                  Const Schedule& schedule,   
                  const std::vector<Rate>& coupons,   
                  Const DayCounter& accrualDayCounter,   
                  BusinessDayConvention paymentConvention = Following,   
                  Real redemption = 100.0,   
                  Const Date& issueDate = Date (),   
                  Const Calendar& paymentCalendar = Calendar (),   
                  Const Period& exCouponPeriod = Period (),   
                  Const Calendar& exCouponCalendar = Calendar (),   
                  Const BusinessDayConvention exCouponConvention = Unadjusted,   
                  Bool exCouponEndOfMonth = false)
Let us create the \`FixedRateBond\` object below.
    In [6]: coupon_rate = 0.\1
            Coupons = [coupon_rate]
            Settlement_days = 0
            Face_value = 100
            Fixed_rate_bond = ql.FixedRateBond (settlement_days,    
                                               Face_value,    
                                               Schedule,   
                                               Coupons,    
                                               Day_count)
Now the we have the fixed rate bond instrument,    we need a valuation engine in order to price this bond. The fixed rate bond can be priced using a \`DiscountingBondEngine\`. The \`DiscountingBondEngine\` takes the yield curve object as an argument in its constructor. The \`setPricingEngine\` method in the fixed rate bond instrument is used to set the pricing engine.
    In [7]: bond_engine = ql.DiscountingBondEngine (spot_curve_handle)
            Fixed_rate_bond.SetPricingEngine (bond_engine)
Now,    the net present value of the bond can be extracted using the \`NPV\` method.
    In [8]: fixed_rate_bond.NPV ()
    Out[8]: 105.27653992490683
    In [9]: fixed_rate_bond.CleanPrice ()
    Out[9]: 105.27653992490683
We can also obtain various other analytics for the bond.
    In [10]: fixed_rate_bond.AccruedAmount ()
    Out[10]: 0.0
    In [11]: fixed_rate_bond.DirtyPrice ()
    Out[11]: 105.27653992490683
    In [12]: fixed_rate_bond.BondYield (day_count,   
                                       Compounding,   
                                       Compounding_frequency)
    Out[12]: 0.006971154634952549
$$$${ #chap39 . xhtml}
\## $$29.$${. Section-number}Building irregular bonds { #chap39 . xhtml\_leanpub-auto-building-irregular-bonds} (Based on $$a question$$( http://quant.stackexchange.com/questions/11090/ ) by \*Stack Exchange\* user user 7922,    $$another$$( http://quant.stackexchange.com/questions/9080/ ) by user Lisa Ann,    and $$yet another$$( https://sourceforge.net/p/quantlib/mailman/message/36170786/ ) asked by Anthony Calleja on the QuantLib mailing list. Thanks!)
    In [1]: import QuantLib as ql
            From datetime import date
            From pandas import DataFrame
            Import utils
Let me just define a small helper function before starting. It's just for visualization,    nothing to write about.
    In [2]: def rate_if_available (c):
                C = ql. As_coupon (c)
                return utils. Format_rate (c.rate ()) if c else ''
\##### The first question { #chap39 . xhtml\_leanpub-auto-the-first-question} user 7922 had to price a bond that,    curiously,    had a last coupon date before the maturity date; e.g.,    the last coupon date is April 20 th,    2020 and maturity date is April 20 th,    2021. Yes,    it's strange,    but who are we to judge? There's no way to express this directly in QuantLib,    but we can get it with some work. In case of a fixed-rate bond,    and if we want to do the simplest thing that can possibly work,    we can cancel the last coupon by giving it a rate of 0%.
    In [3]: today = ql.Date (8,    ql. October,    2014)
            Ql.Settings.Instance (). EvaluationDate = today
    In [4]: issueDate = today+7
            MaturityDate = issueDate + ql.Period (10,    ql. Years)
            Schedule = ql.Schedule (issueDate,    maturityDate,   
                                   Ql.Period (ql. Annual),    ql.TARGET (),   
                                   Ql. Following,    ql. Following,   
                                   Ql. DateGeneration. Backward,    False)
The schedule we just built gives us the correct maturity date,    as well as the date where we want the last real coupon. Now for the bond:
    In [5]: settlementDays = 3
            FaceAmount = 100
            PaymentDayCounter = ql. Thirty 360 ()
            Coupon_rate = 0.02
            N = len (schedule)-1   # number of coupons
            Coupons = [coupon_rate]*(N-1) + [0.0]
            Bond = ql.FixedRateBond (settlementDays,   
                                    FaceAmount,   
                                    Schedule,   
                                    Coupons,   
                                    PaymentDayCounter)
    In [6]: DataFrame ([ (c.date (),    rate_if_available (c),    c.amount ())
                        For c in bond.Cashflows () ],   
                      Columns = ('date',    'rate',    'amount'),   
                      Index=['']*len (bond.Cashflows ()))
    Out[6]: 
  Date rate amount --- -------------------- -------- ------------   October 15 th,    2015 2.00 % 2.000000   October 17 th,    2016 2.00 % 2.011111   October 16 th,    2017 2.00 % 1.994444   October 15 th,    2018 2.00 % 1.994444   October 15 th,    2019 2.00 % 2.000000   October 15 th,    2020 2.00 % 2.000000   October 15 th,    2021 2.00 % 2.000000   October 17 th,    2022 2.00 % 2.011111   October 16 th,    2023 2.00 % 1.994444   October 15 th,    2024 0.00 % 0.000000   October 15 th,    2024   100.000000 The same trick also works for floating-rate coupons,    if we use a null gearing for the last coupon:
    In [7]: euribor_curve = ql.FlatForward (0,    ql.TARGET (),    0.002,    ql. Actual 360 ())
            Index = ql. Euribor 1 Y (ql.YieldTermStructureHandle (euribor_curve))
            N = len (schedule)-1   # number of coupons
            Gearings = [1.0]*(N-1) + [0.0]
            Bond = ql.FloatingRateBond (settlementDays = 3,   
                                       FaceAmount = 100,   
                                        Schedule = schedule,   
                                       Index = index,   
                                       PaymentDayCounter = ql. Thirty 360 (),   
                                       PaymentConvention = ql. Following,   
                                       FixingDays = index.FixingDays (),   
                                       Gearings = gearings,   
                                       Spreads = [],   
                                       Caps= [],   
                                       Floors = [],   
                                       InArrears = False,   
                                       Redemption = 100.0,   
                                       IssueDate = issueDate)
    In [8]: DataFrame ([ (c.date (),    rate_if_available (c),    c.amount ())
                       For c in bond.Cashflows () ],   
                      Columns = ('date',    'rate',    'amount'),   
                      Index=['']*len (bond.Cashflows ()))
    Out[8]: 
  Date rate amount --- -------------------- -------- ------------   October 15 th,    2015 0.20 % 0.200203   October 17 th,    2016 0.20 % 0.201317   October 16 th,    2017 0.20 % 0.199646   October 15 th,    2018 0.20 % 0.199646   October 15 th,    2019 0.20 % 0.200203   October 15 th,    2020 0.20 % 0.200203   October 15 th,    2021 0.20 % 0.200203   October 17 th,    2022 0.20 % 0.201316   October 16 th,    2023 0.20 % 0.199646   October 15 th,    2024 0.00 % 0.000000   October 15 th,    2024   100.000000 However,    that's a bit sloppy. The coupon paying a null rate looks strange,    and might confuse cash-flow analysis. It's better,    even if it takes a bit more work,    to remove the coupon altogether. We can get the cash flows from the bond we created...
    In [9]: cashflows = list (bond.Cashflows ())
... Delete the ones we don't want to keep,    that is,    the one before the last (the last being the redemption)...
    In [10]: del cashflows[-2]
... And use the cleaned-up cash flows to create a new bond:
    In [11]: bond = ql.Bond (3,    ql.TARGET (),    100.0,   
                            MaturityDate,    issueDate,   
                            Cashflows)
This gives us the coupons we wanted:
    In [12]: DataFrame ([ (c.date (),    rate_if_available (c),    c.amount ())
                         For c in bond.Cashflows () ],   
                       Columns = ('date',    'rate',    'amount'),   
                       Index=['']*len (bond.Cashflows ()))
    Out[12]: 
  date rate amount --- -------------------- -------- ------------   October 15 th,    2015 0.20 % 0.200203   October 17 th,    2016 0.20 % 0.201317   October 16 th,    2017 0.20 % 0.199646   October 15 th,    2018 0.20 % 0.199646   October 15 th,    2019 0.20 % 0.200203   October 15 th,    2020 0.20 % 0.200203   October 15 th,    2021 0.20 % 0.200203   October 17 th,    2022 0.20 % 0.201316   October 16 th,    2023 0.20 % 0.199646   October 15 th,    2024   100.000000 ##### The second question { #chap39 . xhtml\_leanpub-auto-the-second-question} Lisa Ann had to price a more common instrument (namely,    a fixed-to-floater) for which,    however,    there's no specific class in the library. In this case,    too,    we can create the required bond by manipulating coupons; and in this case,    too,    we can choose how much work to do. Let's say the bond pays three fixed-rate coupon first and then seven floating-rate coupons. We might create the fixed-rate coupons...
    In [13]: schedule = ql.Schedule (issueDate,    issueDate+ql.Period (3,    ql. Years),   
                                    Ql.Period (ql. Annual),    ql.TARGET (),   
                                    Ql. Following,    ql. Following,   
                                    Ql. DateGeneration. Backward,    False)
             Fixed = ql.FixedRateLeg (schedule = schedule,   
                                     DayCount = ql. Actual 360 (),   
                                     Nominals = [100.0],   
                                     CouponRates = [0.02])
... Then the floating-rate coupons...
    In [14]: schedule = ql.Schedule (issueDate+ql.Period (3,    ql. Years),    maturityDate,   
                                    Ql.Period (ql. Annual),    ql.TARGET (),   
                                    Ql. Following,    ql. Following,   
                                    Ql. DateGeneration. Backward,    False)
             Floating = ql.IborLeg (nominals = [100.0],   
                                   Schedule = schedule,   
                                   Index = index,   
                                   Spreads = [0.001])
... And finally put them together,    add the redemption,    and build a custom bond:
    In [15]: bond = ql.Bond (3,    ql.TARGET (),    100.0,   
                            MaturityDate,    issueDate,   
                            Fixed + floating + (ql.Redemption (100.0,    maturityDate),   ))
    In [16]: DataFrame ([ (c.date (),    rate_if_available (c),    c.amount ())
                         For c in bond.Cashflows () ],   
                       Columns = ('date',    'rate',    'amount'),   
                       Index=['']*len (bond.Cashflows ()))
    Out[16]: 
  Date rate amount --- -------------------- -------- ------------   October 15 th,    2015 2.00 % 2.027778   October 17 th,    2016 2.00 % 2.044444   October 16 th,    2017 2.00 % 2.022222   October 15 th,    2018 0.30 % 0.303538   October 15 th,    2019 0.30 % 0.304372   October 15 th,    2020 0.30 % 0.305207   October 15 th,    2021 0.30 % 0.304372   October 17 th,    2022 0.30 % 0.306041   October 16 th,    2023 0.30 % 0.303538   October 15 th,    2024 0.30 % 0.304372   October 15 th,    2024   100.000000 However,    I'm not very comfortable with building the coupons with two half-schedules; I haven't looked very hard for a counter-example,    but I suspect that some combination of holidays and business-day conventions might cause the coupon dates to be off. A safer alternative would be to build both fixed and floating coupons over the full bond schedule,    and just keep those we need:
    In [17]: schedule = ql.Schedule (issueDate,    maturityDate,   
                                    Ql.Period (ql. Annual),    ql.TARGET (),   
                                    Ql. Following,    ql. Following,   
                                    Ql. DateGeneration. Backward,    False)
             Fixed = ql.FixedRateLeg (schedule = schedule,   
                                     DayCount = ql. Actual 360 (),   
                                     Nominals = [100.0],   
                                     CouponRates = [0.02])
             Floating = ql.IborLeg (nominals = [100.0],   
                                   Schedule = schedule,   
                                   Index = index,   
                                   Spreads = [0.001])
             Cashflows = fixed[: 3] + floating[3:] + (ql.Redemption (100.0,    maturityDate),   )
    In [18]: bond = ql.Bond (3,    ql.TARGET (),    100.0,   
                            MaturityDate,    issueDate,    cashflows)
    In [19]: DataFrame ([ (c.date (),    rate_if_available (c),    c.amount ())
                         For c in bond.Cashflows () ],   
                       Columns = ('date',    'rate',    'amount'),   
                       Index=['']*len (bond.Cashflows ()))
    Out[19]: 
  Date rate amount --- -------------------- -------- ------------   October 15 th,    2015 2.00 % 2.027778   October 17 th,    2016 2.00 % 2.044444   October 16 th,    2017 2.00 % 2.022222   October 15 th,    2018 0.30 % 0.303538   October 15 th,    2019 0.30 % 0.304372   October 15 th,    2020 0.30 % 0.305207   October 15 th,    2021 0.30 % 0.304372   October 17 th,    2022 0.30 % 0.306041   October 16 th,    2023 0.30 % 0.303538   October 15 th,    2024 0.30 % 0.304372   October 15 th,    2024   100.000000 Also,    in a pinch (for instance,    if you're using the QuantLib Excel module and can't create custom bonds easily) a fixed-rate coupon can be approximated by a floating-rate coupon with a null gearing and a spread equal to the desired rate,    so you might get the same result this way:
    In [20]: schedule = ql.Schedule (issueDate,    maturityDate,   
                                    Ql.Period (ql. Annual),    ql.TARGET (),   
                                    Ql. Following,    ql. Following,   
                                    Ql. DateGeneration. Backward,    False)
             Gearings = [0.0]*3 + [1.0]*7
             Spreads = [0.02]*3 + [0.001]*7
             Bond = ql.FloatingRateBond (settlementDays = 3,   
                                        FaceAmount = 100,   
                                        Schedule = schedule,   
                                        Index = index,   
                                        PaymentDayCounter = ql. Actual 360 (),   
                                        PaymentConvention = ql. Following,   
                                        FixingDays = index.FixingDays (),   
                                        Gearings = gearings,   
                                        Spreads = spreads,   
                                        Caps= [],   
                                        Floors = [],   
                                        InArrears = False,   
                                        Redemption = 100.0,   
                                        IssueDate = issueDate)
    In [21]: DataFrame ([ (c.date (),    rate_if_available (c),    c.amount ())
                        For c in bond.Cashflows () ],   
                       Columns = ('date',    'rate',    'amount'),   
                       Index=['']*len (bond.Cashflows ()))
    Out[21]: 
  date rate amount --- -------------------- -------- ------------   October 15 th,    2015 2.00 % 2.027778   October 17 th,    2016 2.00 % 2.044444   October 16 th,    2017 2.00 % 2.022222   October 15 th,    2018 0.30 % 0.303538   October 15 th,    2019 0.30 % 0.304372   October 15 th,    2020 0.30 % 0.305207   October 15 th,    2021 0.30 % 0.304372   October 17 th,    2022 0.30 % 0.306041   October 16 th,    2023 0.30 % 0.303538   October 15 th,    2024 0.30 % 0.304372   October 15 th,    2024   100.000000 However,    I don't suggest doing this if you can get actual fixed- and floating-rate coupons. ##### The third question { #chap39 . xhtml\_leanpub-auto-the-third-question} This one requires a bit more work (and involved a swap,    instead of a bond,    but it doesn't matter; you can build custom swaps with the \`Swap\` class). Anthony needed a floating leg paying 6-months Euribor,    but with a short initial stub paying the fixing of 3-months Euribor instead. In a vanilla leg,    even with the correct schedule,    the first coupon would pay the 6-months fixing instead:
    In [22]: euribor_curve_3 m = ql.FlatForward (0,    ql.TARGET (),    0.0015,    ql. Actual 360 ())
             Index_3 m = ql. Euribor 3 M (ql.YieldTermStructureHandle (euribor_curve_3 m))
             Euribor_curve_6 m = ql.FlatForward (0,    ql.TARGET (),    0.0020,    ql. Actual 360 ())
             Index_6 m = ql. Euribor 6 M (ql.YieldTermStructureHandle (euribor_curve_6 m))
    In [23]: startDate = today + 7
             EndDate = startDate + ql.Period (3,    ql. Months) + ql.Period (5,    ql. Years)
             Schedule = ql.Schedule (startDate,    endDate,   
                                    Ql.Period (ql. Semiannual),    ql.TARGET (),   
                                    Ql. Following,    ql. Following,   
                                    Ql. DateGeneration. Backward,    False)
             Cashflows = ql.IborLeg (nominals = [100.0],   
                                    Schedule = schedule,   
                                    Index = index_6 m)
    In [24]: DataFrame ([ (c.date (),   
                          Ql. As_coupon (c). AccrualStartDate (),   
                          Ql. As_coupon (c). AccrualEndDate (),   
                          utils. Format_rate (ql. As_coupon (c). Rate ()),    c.amount ())
                         For c in cashflows ],   
                       Columns = ('payment date',    'start date',    'end date',   
                                  'rate',    'amount'),   
                       Index=['']*len (cashflows))
    Out[24]: 
  Payment date start date end date rate amount --- -------------------- -------------------- -------------------- -------- ----------   January 15 th,    2015 October 15 th,    2014 January 15 th,    2015 0.20 % 0.051124   July 15 th,    2015 January 15 th,    2015 July 15 th,    2015 0.20 % 0.100606   January 15 th,    2016 July 15 th,    2015 January 15 th,    2016 0.20 % 0.102274   July 15 th,    2016 January 15 th,    2016 July 15 th,    2016 0.20 % 0.101162   January 16 th,    2017 July 15 th,    2016 January 16 th,    2017 0.20 % 0.102831   July 17 th,    2017 January 16 th,    2017 July 17 th,    2017 0.20 % 0.101162   January 15 th,    2018 July 17 th,    2017 January 15 th,    2018 0.20 % 0.101162   July 16 th,    2018 January 15 th,    2018 July 16 th,    2018 0.20 % 0.101162   January 15 th,    2019 July 16 th,    2018 January 15 th,    2019 0.20 % 0.101718   July 15 th,    2019 January 15 th,    2019 July 15 th,    2019 0.20 % 0.100606   January 15 th,    2020 July 15 th,    2019 January 15 th,    2020 0.20 % 0.102274 The first coupon has the correct dates,    but the rate is wrong. To use the right one,    we have to build a custom first coupon with the correct index and use it instead of the current one. We also need to set it a pricer (which is usually done for us by \`IborLeg\`).
    In [25]: first = ql. As_floating_rate_coupon (cashflows[0])
             Coupon 3 m = ql.IborCoupon (first.Date (),    first.Nominal (),   
                                      First.AccrualStartDate (),    first.AccrualEndDate (),   
                                      First.FixingDays (),    index_3 m)
             Coupon 3 m.SetPricer (ql.BlackIborCouponPricer ())
             Cashflows = (coupon 3 m,   ) + cashflows[1:]
    In [26]: DataFrame ([ (c.date (),   
                          Ql. As_coupon (c). AccrualStartDate (),   
                          Ql. As_coupon (c). AccrualEndDate (),   
                          utils. Format_rate (ql. As_coupon (c). Rate ()),    c.amount ())
                         For c in cashflows ],   
                       Columns = ('payment date',    'start date',    'end date',   
                                  'rate',    'amount'),   
                       Index=['']*len (cashflows))
    Out[26]: 
  Payment date start date end date rate amount --- -------------------- -------------------- -------------------- -------- ----------   January 15 th,    2015 October 15 th,    2014 January 15 th,    2015 0.15 % 0.038341   July 15 th,    2015 January 15 th,    2015 July 15 th,    2015 0.20 % 0.100606   January 15 th,    2016 July 15 th,    2015 January 15 th,    2016 0.20 % 0.102274   July 15 th,    2016 January 15 th,    2016 July 15 th,    2016 0.20 % 0.101162   January 16 th,    2017 July 15 th,    2016 January 16 th,    2017 0.20 % 0.102831   July 17 th,    2017 January 16 th,    2017 July 17 th,    2017 0.20 % 0.101162   January 15 th,    2018 July 17 th,    2017 January 15 th,    2018 0.20 % 0.101162   July 16 th,    2018 January 15 th,    2018 July 16 th,    2018 0.20 % 0.101162   January 15 th,    2019 July 16 th,    2018 January 15 th,    2019 0.20 % 0.101718   July 15 th,    2019 January 15 th,    2019 July 15 th,    2019 0.20 % 0.100606   January 15 th,    2020 July 15 th,    2019 January 15 th,    2020 0.20 % 0.102274 As before,    the resulting cash flows can be used to instantiate a bond or a swap.
$$$${ #chap40 . xhtml}
\## $$30.$${. Section-number}Valuation of bonds with credit spreads { #chap40 . xhtml\_leanpub-auto-valuation-of-bonds-with-credit-spreads} In an earlier example on pricing fixed rate bonds,    I demonstrated how to construct and value bonds using the given yield curve. In this example,    let us take a look at valuing bonds with credit spreads. We will show how to add credit spreads to the give yield curve using different approaches. As usual,    let us start by importing the QuantLib library and pick a valuation date and set the calculation instance evaluation date.
    In [1]: import QuantLib as ql
            Calc_date = ql.Date (26,    7,    2016)
            Ql.Settings.Instance (). EvaluationDate = calc_date
For simplicity,    let us imagine that the treasury yield curve is flat. This makes it easier to construct the yield curve easily. This also allows us to directly shock the yield curve,    and provides a validation for the more general treatment of shocks on yield curve.
    In [2]: flat_rate = ql.SimpleQuote (0.0015)
            Rate_handle = ql.QuoteHandle (flat_rate)
            Day_count = ql. Actual 360 ()
            Calendar = ql.UnitedStates ()
            Ts_yield = ql.FlatForward (calc_date,    rate_handle,    day_count)
            Ts_handle = ql.YieldTermStructureHandle (ts_yield)
Now let us construct the bond itself. We do that by first constructing the schedule,    and then passing the schedule into the bond.
    In [3]: issue_date = ql.Date (15,    7,    2016)
            Maturity_date = ql.Date (15,    7,    2021)
            Tenor = ql.Period (ql. Semiannual)
            Calendar = ql.UnitedStates ()
            Business_convention = ql. Unadjusted
            Date_generation = ql. DateGeneration. Backward
            Month_end = False
            Schedule = ql.Schedule (issue_date,    maturity_date,    
                                   Tenor,    calendar,    
                                   Business_convention,   
                                   Business_convention,    
                                   Date_generation,    
                                   Month_end)
    In [4]: settlement_days = 2
            Day_count = ql. Thirty 360 ()
            Coupon_rate = 0.03
            Coupons = [coupon_rate]
            # Now lets construct the FixedRateBond
            Settlement_days = 0
            Face_value = 100
            Fixed_rate_bond = ql.FixedRateBond (
                Settlement_days,    
                Face_value,    
                Schedule,    
                Coupons,    
                Day_count)
Now that we have the \`fixed\_rate\_bond\` object,    we can create a \`DiscountingBondEngine\` and value the bond.
    In [5]: bond_engine = ql.DiscountingBondEngine (ts_handle)
            Fixed_rate_bond.SetPricingEngine (bond_engine)
            Fixed_rate_bond.NPV ()
    Out[5]: 114.18461651948999
So far,    we have valued the bond under the treasury yield curve and have not incorporated the credit spreads. Let us assume that the market prices this bond with a \`50 BP\` spread on top of the treasury yield curve. Now we can,    in this case,    directly shock the \`flat\_rate\` used in the yield term structure. Let us see what the value is:
    In [6]: flat_rate.SetValue (0.0065)
            Fixed_rate_bond.NPV ()
    Out[6]: 111.5097766266561
Above we shocked the \`flat\_rate\` and since the yield term structure is an \`Observer\` observing the \`Observable\` \`flat\_rate\`,    we could just shock the rate,    and QuantLib behind the scenes recalculates all the \`Observer\`s. Though,    this approach is not always viable,    in cases such as a bootstrapped bond curve. So let us look at two different approaches that can be used. Before we do that,    we need to reset the \`flat\_rate\` back to what it was.
    In [7]: flat_rate.SetValue (0.0015)
            Fixed_rate_bond.NPV ()
    Out[7]: 114.18461651948999
\##### Parallel Shift of the Yield Curve { #chap40 . xhtml\_leanpub-auto-parallel-shift-of-the-yield-curve} The whole yield curve can be shifted up and down,    and the bond revalued with the help of the \`ZeroSpreadedTermStructure\`. The constructor takes the yield curve and the spread as argument.
    In [8]: spread 1 = ql.SimpleQuote (0.0050)
            Spread_handle 1 = ql.QuoteHandle (spread 1)
            Ts_spreaded 1 = ql.ZeroSpreadedTermStructure (ts_handle,    spread_handle 1)
            Ts_spreaded_handle 1 = ql.YieldTermStructureHandle (ts_spreaded 1)
            Bond_engine = ql.DiscountingBondEngine (ts_spreaded_handle 1)
            Fixed_rate_bond.SetPricingEngine (bond_engine)
            # Finally the price
            Fixed_rate_bond.NPV ()
    Out[8]: 111.50977662665609
Once we have constructed the spreaded term structure,    it is rather easy to value for other spreads. All we need to do is change the \`SimpleQuote\` object \`spread 1\` here.
    In [9]: spread 1.SetValue (0.01)
            Fixed_rate_bond.NPV ()
    Out[9]: 108.89999943320038
\##### Non-Parallel Shift of the Yield Curve { #chap40 . xhtml\_leanpub-auto-non-parallel-shift-of-the-yield-curve} The above method allows only for parallel shift of the yield curve. The \`SpreadedLinearZeroInterpolatedTermStructure\` class allows for non parallel shock. First,    let us mimic a parallel shift using this class. For the constructor,    we need to pass the yield term structure that we wish to shift,    and the a list of spreads and a list of the corresponding dates.
    In [10]: spread 21 = ql.SimpleQuote (0.0050)
             Spread 22 = ql.SimpleQuote (0.0050)
             Start_date = calc_date
             End_date = calendar.Advance (start_date,    ql.Period (50,    ql. Years))
             Ts_spreaded 2 = ql.SpreadedLinearZeroInterpolatedTermStructure (
                 Ts_handle,   
                 [ql.QuoteHandle (spread 21),    ql.QuoteHandle (spread 22)],   
                 [start_date,    end_date]
             )
             Ts_spreaded_handle 2 = ql.YieldTermStructureHandle (ts_spreaded 2)
             Bond_engine = ql.DiscountingBondEngine (ts_spreaded_handle 2)
             Fixed_rate_bond.SetPricingEngine (bond_engine)
             # Finally the price
             Fixed_rate_bond.NPV ()
    Out[10]: 111.50977662665609
Here,    once again we can change the value of \`spread 2\` to value for other shocks.
    In [11]: spread 21.SetValue (0.01)
             Spread 22.SetValue (0.01)
             Fixed_rate_bond.NPV ()
    Out[11]: 108.89999943320038
We can easily do non-parallel shifts just by shocking one end.
    In [12]: spread 21.SetValue (0.005)
             Spread 22.SetValue (0.01)
             Fixed_rate_bond.NPV ()
    Out[12]: 111.25358792334083
The \`SpreadedLinearZeroInterpolatedTermStructure\` is a powerful class and can be used to implement key-rate duration calculations.
$$$${ #chap41 . xhtml}
\## $$31.$${. Section-number}Modeling callable bonds { #chap41 . xhtml\_leanpub-auto-modeling-callable-bonds} In this chapter,    lets take a look at valuing callable bonds in QuantLib Python. The approach to construct a callable bond is lot similar to $$modeling a fixed rate bond in QuantLib$$( #chap38 . xhtml\_fixedratebonds). The one additional input that we need to provide here is the details on the call or put schedule. If you follow the fixed rate bond example already,    this should be fairly straight forward. As always,    we will start with some initializations and imports.
    In [1]: import QuantLib as ql
            Import numpy as np
            Import utils
            %matplotlib inline
            Calc_date = ql.Date (16,   8,   2016)
            Ql.Settings.Instance (). EvaluationDate = calc_date
            # This is for compatibility with QuantLib < 1.22
            Try:
                Ql. BondPrice
            Except:
                Ql. BondPrice = ql. CallabilityPrice
For simplicity,    let us assume that the interest rate term structure is a flat yield curve at 3.5%. You can refer to $$constructing yield curves$$( #chap14 . xhtml\_yc-construction) for more details on constructing yield curves.
    In [2]: day_count = ql.ActualActual (ql. ActualActual. Bond)
            Rate = 0.035
            Ts = ql.FlatForward (calc_date,    rate,    
                                Day_count,    ql. Compounded,    
                                Ql. Semiannual)
            Ts_handle = ql.YieldTermStructureHandle (ts)
The call and put schedules for the callable bond is created as shown below. We create a container for holding all the call and put dates using the \`CallabilitySchedule\` class. You can add each call using \`Callability\` class and noting as \`Callability. Call\` or \`Callability. Put\` for either a call or put.
    In [3]: callability_schedule = ql.CallabilitySchedule ()
            Call_price = 100.0
            Call_date = ql.Date (15,    ql. September,    2016);
            Null_calendar = ql.NullCalendar ();
            For i in range (0,   24):
                Callability_price  = ql.BondPrice (
                    Call_price,    ql. BondPrice. Clean)
                Callability_schedule.Append (
                        Ql.Callability (callability_price,    
                                       Ql. Callability. Call,   
                                       Call_date))
                Call_date = null_calendar.Advance (call_date,    3,    
                                                  Ql. Months)
What follows next is similar to the \`Schedule\` that we created in the vanilla fixed rate bond valuation.
    In [4]: issue_date = ql.Date (16,    ql. September,    2014)        
            Maturity_date = ql.Date (15,    ql. September,    2022)
            Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
            Tenor = ql.Period (ql. Quarterly)
            Accrual_convention = ql. Unadjusted
            Schedule = ql.Schedule (issue_date,    maturity_date,    tenor,   
                                   Calendar,    accrual_convention,    
                                   Accrual_convention,   
                                   Ql. DateGeneration. Backward,    False)
The callable bond is instantiated using the \`CallableFixedRateBond\` class,    which accepts the bond inputs and the call or put schedule.
    In [5]: settlement_days = 3
            Face_amount = 100
            Accrual_daycount = ql.ActualActual (ql. ActualActual. Bond)
            Coupon = 0.025
            Bond = ql.CallableFixedRateBond (
                Settlement_days,    face_amount,   
                Schedule,    [coupon],    accrual_daycount,   
                Ql. Following,    face_amount,    issue_date,   
                Callability_schedule)
In order to value the bond,    we need an interest rate model to model the fact that the bond will get called or not in the future depending on where the future interest rates are at. The \`TreeCallableFixedRateBondEngine\` can be used to value the callable bond. Below,    the \`value\_bond\` function prices the callable bond based on the Hull-White model parameter for mean reversion and volatility.
    In [6]: def value_bond (a,    s,    grid_points,    bond):
                Model = ql.HullWhite (ts_handle,    a,    s)
                Engine = ql.TreeCallableFixedRateBondEngine (model,    grid_points)
                Bond.SetPricingEngine (engine)
                Return bond
The callable bond value for a 3% mean reversion and 12% volatility is shown below.
    In [7]: value_bond (0.03,    0.12,    40,    bond)
            Print ("Bond price: %lf" % bond.CleanPrice ())
    Out[7]: Bond price: 68.396593
The price sensitivity of callable bonds to that of volatility parameter is shown below. As volatility increases,    there is a higher chance of it being callable. Hence the value of the bond decreases.
    In [8]: sigmas = np.Arange (0.001,    0.15,    0.001)
            Prices = [value_bond (0.03,    s,    40,    bond). CleanPrice () 
                      For s in sigmas]
    In [9]: _,    ax = utils.Plot ()
            Ax.Plot (sigmas,    prices)
            Ax. Set_xlabel ("Sigma",    size=12)
            Ax. Set_ylabel ("Price",    size=12);
::: {. Figure-wrapper .center}
![](/Users/rogerlin/Downloads/QuantLib_Cookbook_Media/images/callable_bonds-9.png)
::: The static cash flows can be accessed using the \`cashflows\` accessor.
    In [10]: from pandas import DataFrame
             DataFrame (
                 [(cf.Date (),    cf.Amount ()) for cf in bond.Cashflows ()],   
                 Columns=["Date",    "Amount"],   
                 Index=range (1,    len (bond.Cashflows ())+1))
    Out[10]: 
  Date Amount ---- ---------------------- ------------ 1 December 15 th,    2014 0.618132 2 March 16 th,    2015 0.625000 3 June 15 th,    2015 0.625000 4 September 15 th,    2015 0.625000 5 December 15 th,    2015 0.625000 6 March 15 th,    2016 0.625000 7 June 15 th,    2016 0.625000 8 September 15 th,    2016 0.625000 9 December 15 th,    2016 0.625000 10 March 15 th,    2017 0.625000 11 June 15 th,    2017 0.625000 12 September 15 th,    2017 0.625000 13 December 15 th,    2017 0.625000 14 March 15 th,    2018 0.625000 15 June 15 th,    2018 0.625000 16 September 17 th,    2018 0.625000 17 December 17 th,    2018 0.625000 18 March 15 th,    2019 0.625000 19 June 17 th,    2019 0.625000 20 September 16 th,    2019 0.625000 21 December 16 th,    2019 0.625000 22 March 16 th,    2020 0.625000 23 June 15 th,    2020 0.625000 24 September 15 th,    2020 0.625000 25 December 15 th,    2020 0.625000 26 March 15 th,    2021 0.625000 27 June 15 th,    2021 0.625000 28 September 15 th,    2021 0.625000 29 December 15 th,    2021 0.625000 30 March 15 th,    2022 0.625000 31 June 15 th,    2022 0.625000 32 September 15 th,    2022 0.625000 33 September 15 th,    2022 100.000000 ##### Conclusion { #chap41 . xhtml\_leanpub-auto-conclusion-6} Here we explored a minimal example on pricing a callable bond.
$$$${ #chap42 . xhtml}
\## $$32.$${. Section-number}Discount margin calculation { #chap42 . xhtml\_leanpub-auto-discount-margin-calculation} (Based on $$two$$( http://quant.stackexchange.com/questions/8965/ ) $$questions$$( https://quant.stackexchange.com/questions/37705/ ) by \*Stack Exchange\* users HookahBoy and Kyle. Thanks!)
    In [1]: import QuantLib as ql
    In [2]: today = ql.Date (8,    ql. October,    2014)
            Ql.Settings.Instance (). EvaluationDate = today
\##### The question { #chap42 . xhtml\_leanpub-auto-the-question} Given a floating-rate bond price,    we want to find the corresponding discount margin. This is one in a class of similar problems: we have a calculation which is not immediate to do directly,    but is straightforward to do in the opposite direction; in this case,    find the price of a bond when discounting its coupons at a spread over LIBOR. The general idea is to implement the inverse calculation (DM to price) and then to use a solver to determine the correct input given the result. First,    we build the bond.
    In [3]: forecast_curve = ql.RelinkableYieldTermStructureHandle ()
            Discount_curve = ql.RelinkableYieldTermStructureHandle ()
    In [4]: index = ql. Euribor 6 M (forecast_curve)
    In [5]: issueDate = ql.Date (13,    ql. October,    2014)
            MaturityDate = ql.Date (13,    ql. October,    2024)
            Schedule = ql.Schedule (issueDate,    maturityDate,   
                                   Ql.Period (ql. Semiannual),    ql.TARGET (),   
                                   Ql. Following,    ql. Following,   
                                   Ql. DateGeneration. Backward,    False)
    In [6]: bond = ql.FloatingRateBond (settlementDays = 3,   
                                       FaceAmount = 100,   
                                       Schedule = schedule,   
                                       Index = index,   
                                       PaymentDayCounter = ql. Actual 360 (),   
                                       PaymentConvention = ql. Following,   
                                       FixingDays = index.FixingDays (),   
                                       Gearings = [],   
                                       Spreads = [],   
                                       Caps= [],   
                                       Floors = [],   
                                       InArrears = False,   
                                       Redemption = 100.0,   
                                       IssueDate = issueDate)
            Bond.SetPricingEngine (ql.DiscountingBondEngine (discount_curve))
Now we link the forecast curve to the current Euribor curve (whatever that is; I'm using a flat one as an example,    but it could as well be a real one)...
    In [7]: forecast_curve.LinkTo (ql.FlatForward (0,    ql.TARGET (),    0.002,    ql. Actual 360 ()))
... And the discount curve to the Euribor curve plus the discount margin.
    In [8]: DM = ql.SimpleQuote (0.0)
            Discount_curve.LinkTo (ql.ZeroSpreadedTermStructure (forecast_curve,   
                                                               Ql.QuoteHandle (DM)))
Setting a value to the DM quote will affect the bond price: this gives us the knob to manipulate in order to find the solution of our problem.
    In [9]: print (bond.CleanPrice ())
    Out[9]: 100.00000000000001
    In [10]: DM.SetValue (0.001)
             Print (bond.CleanPrice ())
    Out[10]: 98.99979030764418
To invert the calculation,    we encapsulate the above into a function. The Python language makes it easier to write it in a general way; the function below takes the target price,    and returns another function that takes a value for the discount margin and returns the difference between the corresponding price and the target. In C++,    we would create a function object taking the target price in its constructor and returning the difference from its \`operator ()\`.
    In [11]: def F (price):
                 Def _f (s):
                     DM.SetValue (s)
                     Return bond.CleanPrice () - price
                 Return _f
    In [12]: f = F (98.9997903076)
             Print (f (0.0))
             Print (f (0.002))
    Out[12]: 1.00020969240002
             -0.9901429992548856
We want to find the value of the discount margin that causes the calculated price to equal the target price,    that is,    that causes the error to be 0; and for that,    we can use a solver.
    In [13]: margin = ql.Brent (). Solve (F (99.6),    1 e-8,    0.0,    1 e-4)
             Print (margin)
    Out[13]: 0.00039870328652332745
We can verify that this works by setting the margin to the returned value and checking that the bond price equals the input:
    In [14]: DM.SetValue (margin)
             Print (bond.CleanPrice ())
    Out[14]: 99.59999988275108
However,    note that the spread above is continuously compounded. You might want to see the discount margin in the same units as the index fixings:
    In [15]: value_date = index.ValueDate (today)
             Maturity_date = index.MaturityDate (value_date)
             Print (ql.InterestRate (margin,    discount_curve.DayCounter (),   
                                   Ql. Continuous,    ql. NoFrequency)
                   .equivalentRate (index.DayCounter (),   
                                   Ql. Simple,    index.Tenor (). Frequency (),   
                                   Value_date,    maturity_date))
    Out[15]: 0.039874 % Actual/360 simple compounding
\##### Not just for bonds { #chap42 . xhtml\_leanpub-auto-not-just-for-bonds} The approach I described can be generalized to any problem in this class. Here I'll use it to get the implied volatility of an Asian option: first I'll create the instrument...
    In [16]: exerciseDate = today + ql.Period (1,    ql. Years)
             FixingDates = [ today + ql.Period (n,    ql. Months) for n in range (1,   12) ]
             Option = ql.DiscreteAveragingAsianOption (
                 Ql. Average. Arithmetic,   
                 0.0,    0,   
                 FixingDates,   
                 Ql.PlainVanillaPayoff (ql. Option. Call,    100.0),   
                 Ql.EuropeanExercise (exerciseDate))
... And an engine,    taking care of writing the input volatility as a quote.
    In [17]: sigma = ql.SimpleQuote (0.20)
             RiskFreeCurve = ql.FlatForward (0,    ql.TARGET (),    0.01,    ql. Actual 360 ())
             Volatility = ql.BlackConstantVol (0,    ql.TARGET (),   
                                              Ql.QuoteHandle (sigma),    ql. Actual 360 ())
             Process = ql.BlackScholesProcess (ql.QuoteHandle (ql.SimpleQuote (100.0)),   
                                              Ql.YieldTermStructureHandle (riskFreeCurve),   
                                              Ql.BlackVolTermStructureHandle (volatility))
    In [18]: option.SetPricingEngine (
                 Ql.MCDiscreteArithmeticAPEngine (process,    "pseudorandom",   
                                                 RequiredSamples=1000,   
                                                 Seed=42))
Now we can use the same technique as above: the function below takes a target price and returns a function from the volatility to the pricing error:
    In [19]: def F (price):
                 Def _f (v):
                     Sigma.SetValue (v)
                     Return option.NPV () - price
                 Return _f
Using a solver,    we can invert it to solve for any price:
    In [20]: print (ql.Brent (). Solve (F (5.0),    1 e-8,    0.20,    1 e-4))
    Out[20]: 0.20081193864526342
    In [21]: print (ql.Brent (). Solve (F (6.0),    1 e-8,    0.20,    1 e-4))
    Out[21]: 0.24362397543255393
$$$${ #chap43 . xhtml}
\## $$33.$${. Section-number}Duration of floating-rate bonds { #chap43 . xhtml\_leanpub-auto-duration-of-floating-rate-bonds} (Based on a question by Antonio Savoldi on the QuantLib mailing list. Thanks!)
    In [1]: import QuantLib as ql
            From pandas import DataFrame
    In [2]: today = ql.Date (8,    ql. October,    2014)
            Ql.Settings.Instance (). EvaluationDate = today
\##### The problem { #chap43 . xhtml\_leanpub-auto-the-problem-2} We want to calculate the modified duration of a floating-rate bond. First,    we need an interest-rate curve to forecast its coupon rates: for illustration's sake,    let's take a flat curve with a 0.2% rate.
    In [3]: forecast_curve = ql.RelinkableYieldTermStructureHandle ()
            Forecast_curve.LinkTo (ql.FlatForward (today,    0.002,    ql. Actual 360 (),   
                                                 Ql. Compounded,    ql. Semiannual))
Then,    we instantiate the index to be used. The bond has semiannual coupons,    so we create a \`Euribor 6 M\` instance and we pass it the forecast curve. Also,    we set a past fixing for the current coupon (which,    having fixed in the past,    can't be forecast).
    In [4]: index = ql. Euribor 6 M (forecast_curve)
            Index.AddFixing (ql.Date (6,    ql. August,    2014),    0.002)
The bond was issued a couple of months before the evaluation date and will run for 5 years with semiannual coupons.
    In [5]: issueDate = ql.Date (8,    ql. August,    2014)
            MaturityDate = ql.Date (8,    ql. August,    2019)
            Schedule = ql.Schedule (issueDate,    maturityDate,   
                                   Ql.Period (ql. Semiannual),    ql.TARGET (),   
                                   Ql. Following,    ql. Following,   
                                   Ql. DateGeneration. Backward,    False)
            Bond = ql.FloatingRateBond (settlementDays = 3,   
                                       FaceAmount = 100,   
                                       Schedule = schedule,   
                                       Index = index,   
                                       PaymentDayCounter = ql. Actual 360 ())
The cash flows are calculated based on the forecast curve. Here they are,    together with their dates. As expected,    they each pay around 0.1% of the notional.
    In [6]: dates = [ c.date () for c in bond.Cashflows () ]
            cfs = [ c.amount () for c in bond.Cashflows () ]
            DataFrame (list (zip (dates,    cfs)),   
                      Columns = ('date',   'amount'),   
                      Index = range (1,   len (dates)+1))
    Out[6]: 
  Date amount ---- -------------------- ------------ 1 February 9 th,    2015 0.102778 2 August 10 th,    2015 0.101112 3 February 8 th,    2016 0.101112 4 August 8 th,    2016 0.101112 5 February 8 th,    2017 0.102223 6 August 8 th,    2017 0.100556 7 February 8 th,    2018 0.102223 8 August 8 th,    2018 0.100556 9 February 8 th,    2019 0.102223 10 August 8 th,    2019 0.100556 11 August 8 th,    2019 100.000000 If we try to use the function provided for calculating bond durations,    though,    we run into a problem. When we pass it the bond and a 0.2% semiannual yield,    the result we get is:
    In [7]: y = ql.InterestRate (0.002,    ql. Actual 360 (),    ql. Compounded,    ql. Semiannual)
            Print (ql.BondFunctions.Duration (bond,    y,    ql. Duration. Modified))
    Out[7]: 4.8609591731332165
which is about the time to maturity. Shouldn't we get the time to next coupon instead? ##### What happened? { #chap43 . xhtml\_leanpub-auto-what-happened-1} The function above is too generic. It calculates the modified duration as !$$\\\\displaystyle{-\\\\frac{1}{P}\\\\frac{dP}{dy}}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_164. Png){. Inline-equation width="57"}; however,    it doesn't know what kind of bond it has been passed and what kind of cash flows are paid,    so it can only consider the yield for discounting and not for forecasting. If you looked into the C++ code,    you'd see that the bond price !$$P$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_165. Png){. Inline-equation width="13"} above is calculated as the sum of the discounted cash flows,    as in the following:
    In [8]: y = ql.SimpleQuote (0.002)
            Yield_curve = ql.FlatForward (bond.SettlementDate (),    ql.QuoteHandle (y),   
                                         Ql. Actual 360 (),    ql. Compounded,    ql. Semiannual)
            dates = [ c.date () for c in bond.Cashflows () ]
            cfs = [ c.amount () for c in bond.Cashflows () ]
            Discounts = [ yield_curve.Discount (d) for d in dates ]
            P = sum (cf*b for cf,    b in zip (cfs,    discounts))
            Print (P)
    Out[8]: 100.03665363580889
(Incidentally,    we can see that this matches the calculation in the \`dirtyPrice\` method of the \`Bond\` class.)
    In [9]: bond.SetPricingEngine (
                Ql.DiscountingBondEngine (ql.YieldTermStructureHandle (yield_curve)))
            Print (bond.DirtyPrice ())
    Out[9]: 100.03665363580889
Finally,    the derivative !$$\\\\displaystyle{\\\\frac{dP}{dy}}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_166. Png){. Inline-equation width="24"} in the duration formula in approximated as !$$\\\\displaystyle{\\\\frac{P (y+dy)-P (y-dy)}{2 dy}}$$(/Users/rogerlin/Downloads/QuantLib\_Cookbook\_Media/images/leanpub\_equation\_167. Png){. Inline-equation width="182"},    so that we get:
    In [10]: dy = 1 e-5
             y.setValue (0.002 + dy)
             cfs_p = [ c.amount () for c in bond.Cashflows () ]
             Discounts_p = [ yield_curve.Discount (d) for d in dates ]
             P_p = sum (cf*b for cf,    b in zip (cfs_p,    discounts_p))
             Print (P_p)
             y.setValue (0.002 - dy)
             cfs_m = [ c.amount () for c in bond.Cashflows () ]
             Discounts_m = [ yield_curve.Discount (d) for d in dates ]
             P_m = sum (cf*b for cf,    b in zip (cfs_m,    discounts_m))
             Print (P_m)
             y.setValue (0.002)
    Out[10]: 100.03179102561501
             100.0415165074028
    In [11]: print (-(1/P)*(P_p - P_m)/(2*dy))
    Out[11]: 4.8609591756253225
Which is the same figure returned by \`BondFunctions. Duration\`. The problem is that the above doesn't use the yield curve for forecasting,    so it's not really considering the bond as a floating-rate bond. It's using it as a fixed-rate bond,    whose coupon rates happen to equal the current forecasts for the Euribor 6 M fixings. This is clear if we look at the coupon amounts and discounts we stored during the calculation:
    In [12]: DataFrame (list (zip (dates,    cfs,    discounts,   
                                Cfs_p,    discounts_p,    cfs_m,    discounts_m)),   
                       Columns = ('date',   'amount',   'discounts',   
                                  'amount (+)',   'discounts (+)',   
                                  'amount (-)',   'discounts (-)',   ),   
                       Index = range (1,   len (dates)+1))
    Out[12]: 
  date amount discounts amount (+) discounts (+) amount (-) discounts (-) ---- -------------------- ------------ ----------- ------------ --------------- ------------ --------------- 1 February 9 th,    2015 0.102778 0.999339 0.102778 0.999336 0.102778 0.999343 2 August 10 th,    2015 0.101112 0.998330 0.101112 0.998322 0.101112 0.998338 3 February 8 th,    2016 0.101112 0.997322 0.101112 0.997308 0.101112 0.997335 4 August 8 th,    2016 0.101112 0.996314 0.101112 0.996296 0.101112 0.996333 5 February 8 th,    2017 0.102223 0.995297 0.102223 0.995273 0.102223 0.995320 6 August 8 th,    2017 0.100556 0.994297 0.100556 0.994269 0.100556 0.994325 7 February 8 th,    2018 0.102223 0.993282 0.102223 0.993248 0.102223 0.993315 8 August 8 th,    2018 0.100556 0.992284 0.100556 0.992245 0.100556 0.992322 9 February 8 th,    2019 0.102223 0.991270 0.102223 0.991227 0.102223 0.991314 10 August 8 th,    2019 0.100556 0.990275 0.100556 0.990226 0.100556 0.990323 11 August 8 th,    2019 100.000000 0.990275 100.000000 0.990226 100.000000 0.990323 where you can see how the discount factors changed when the yield was modified,    but the coupon amounts stayed the same. ##### The solution { #chap43 . xhtml\_leanpub-auto-the-solution} Unfortunately,    there's no easy way to fix the \`BondFunctions. Duration\` method so that it does the right thing. What we can do,    instead,    is to repeat the calculation above while setting up the bond and the curves so that the yield is used correctly. In particular,    we have to link the forecast curve to the flat yield curve being modified...
    In [13]: forecast_curve.LinkTo (yield_curve)
... So that changing the yield will also affect the forecast rate of the coupons.
    In [14]: y.setValue (0.002 + dy)
             P_p = bond.DirtyPrice ()
             cfs_p = [ c.amount () for c in bond.Cashflows () ]
             Discounts_p = [ yield_curve.Discount (d) for d in dates ]
             Print (P_p)
             y.setValue (0.002 - dy)
             P_m = bond.DirtyPrice ()
             cfs_m = [ c.amount () for c in bond.Cashflows () ]
             Discounts_m = [ yield_curve.Discount (d) for d in dates ]
             Print (P_m)
             y.setValue (0.002)
    Out[14]: 100.03632329080955
             100.03698398354918
Now the coupon amounts change with the yield (except,    of course,    the first coupon,    whose amount was already fixed)...
    In [15]: DataFrame (list (zip (dates,    cfs,    discounts,    cfs_p,   
                                Discounts_p,    cfs_m,    discounts_m)),   
                       Columns = ('date',   'amount',   'discounts',   
                                  'amount (+)',   'discounts (+)',   
                                  'amount (-)',   'discounts (-)',   ),   
                       Index = range (1,   len (dates)+1))
    Out[15]: 
  Date amount discounts amount (+) discounts (+) amount (-) discounts (-) ---- -------------------- ------------ ----------- ------------ --------------- ------------ --------------- 1 February 9 th,    2015 0.102778 0.999339 0.102778 0.999336 0.102778 0.999343 2 August 10 th,    2015 0.101112 0.998330 0.101617 0.998322 0.100606 0.998338 3 February 8 th,    2016 0.101112 0.997322 0.101617 0.997308 0.100606 0.997335 4 August 8 th,    2016 0.101112 0.996314 0.101617 0.996296 0.100606 0.996333 5 February 8 th,    2017 0.102223 0.995297 0.102734 0.995273 0.101712 0.995320 6 August 8 th,    2017 0.100556 0.994297 0.101059 0.994269 0.100053 0.994325 7 February 8 th,    2018 0.102223 0.993282 0.102734 0.993248 0.101712 0.993315 8 August 8 th,    2018 0.100556 0.992284 0.101059 0.992245 0.100053 0.992322 9 February 8 th,    2019 0.102223 0.991270 0.102734 0.991227 0.101712 0.991314 10 August 8 th,    2019 0.100556 0.990275 0.101059 0.990226 0.100053 0.990323 11 August 8 th,    2019 100.000000 0.990275 100.000000 0.990226 100.000000 0.990323 ... And the duration is calculated correctly,    thus approximating the four months to the next coupon.
    In [16]: print (-(1/P)*(P_p - P_m)/(2*dy))
    Out[16]: 0.33022533022465994
This also holds if the discounting curve is dependent,    but not the same as the forecast curve; e.g.,    as in the case of an added credit spread:
    In [17]: discount_curve = ql.ZeroSpreadedTermStructure (
                 Forecast_curve,   
                 Ql.QuoteHandle (ql.SimpleQuote (0.001)))
             Bond.SetPricingEngine (
                 Ql.DiscountingBondEngine (ql.YieldTermStructureHandle (discount_curve)))
This causes the price to decrease due to the increased discount factors...
    In [18]: P = bond.DirtyPrice ()
             cfs = [ c.amount () for c in bond.Cashflows () ]
             Discounts = [ discount_curve.Discount (d) for d in dates ]
             Print (P)
    Out[18]: 99.55107926688962
... But the coupon amounts are still the same.
    In [19]: DataFrame (list (zip (dates,    cfs,    discounts)),   
                       Columns = ('date',   'amount',   'discount'),   
                       Index = range (1,   len (dates)+1))
    Out[19]: 
  Date amount discount ---- -------------------- ------------ ---------- 1 February 9 th,    2015 0.102778 0.999009 2 August 10 th,    2015 0.101112 0.997496 3 February 8 th,    2016 0.101112 0.995984 4 August 8 th,    2016 0.101112 0.994475 5 February 8 th,    2017 0.102223 0.992952 6 August 8 th,    2017 0.100556 0.991456 7 February 8 th,    2018 0.102223 0.989938 8 August 8 th,    2018 0.100556 0.988446 9 February 8 th,    2019 0.102223 0.986932 10 August 8 th,    2019 0.100556 0.985445 11 August 8 th,    2019 100.000000 0.985445 The price derivative is calculated in the same way as above...
    In [20]: y.setValue (0.002 + dy)
             P_p = bond.DirtyPrice ()
             Print (P_p)
             y.setValue (0.002 - dy)
             P_m = bond.DirtyPrice ()
             Print (P_m)
             y.setValue (0.002)
    Out[20]: 99.55075966035385
             99.55139887578544
    In [21]: print (-(1/P)*(P_p - P_m)/(2*dy))
    Out[21]: 0.3210489711903113
... And yields a similar result.
$$$${ #chap44 . xhtml}
\## $$34.$${. Section-number}Treasury futures contracts { #chap44 . xhtml\_leanpub-auto-treasury-futures-contracts} In this chapter,    we will learn how to value treasury futures contracts using QuantLib. The treasury futures contract gives the buyer the right to buy the underlying by the time the contract expires. The underlying is usually delivered from a basket of securities. So in order to properly value the futures contract,    we would need to find the deliverable. Here we start by doing a naive calculation by constructing a fictional security. We will see what is wrong about this approach. As a next step we will perform the cheapest to deliver calculation and subsequently use that deliverable to value the same contract.
    In [1]: import QuantLib as ql
            Import math
            From pandas import DataFrame
    In [2]: calc_date = ql.Date (30,   11,   2015)
            Ql.Settings.Instance (). EvaluationDate = calc_date
            Day_count = ql.ActualActual ()
            Calendar = ql.UnitedStates ()
            Business_convention = ql. Following
            End_of_month = False
            Settlement_days = 0
            Face_amount = 100
            Coupon_frequency = ql.Period (ql. Semiannual)
\##### Build Yield Curve { #chap44 . xhtml\_leanpub-auto-build-yield-curve} As a first step,    we build the treasury curve out of the treasury securities such as T-Bills,    T-Notes and Treasury bonds.
    In [3]: prices = [99.9935,   99.9576,   99.8119,   99.5472,   99.8867,   
                      100.0664,   99.8711,   100.0547,   100.3047,   100.2266]
            Coupon_rates = [0.0000,    0.0000,    0.0000,    0.0000,    0.00875,    
                            0.0125,    0.01625,    0.02,    0.0225,    0.03]
            Maturity_dates = [ql.Date (24,   12,   2015),    ql.Date (25,   2,   2016),    
                              Ql.Date (26,   5,   2016),     ql.Date (10,   11,   2016),   
                              Ql.Date (30,   11,   2017),    ql.Date (15,   11,   2018),    
                              Ql.Date (30,   11,   2020),    ql.Date (30,   11,   2022),   
                              Ql.Date (15,   11,   2025),    ql.Date (15,   11,   2045)]
            Issue_dates = [ql.Date (25,   6,   2015),     ql.Date (27,   8,   2015),   
                           Ql.Date (28,   5,   2015),     ql.Date (12,   11,   2015),   
                           Ql.Date (30,   11,   2015),    ql.Date (16,   11,   2015),   
                           Ql.Date (30,   11,   2015),    ql.Date (30,   11,   2015),   
                           Ql.Date (16,   11,   2015),    ql.Date (16,   11,   2015)]
            Coupon_frequency = ql.Period (6,    ql. Months)
            Bond_helpers = []
            For coupon,    issue_date,    maturity_date,    price \
                In zip (coupon_rates,    issue_dates,    maturity_dates,    prices):
                Schedule = ql.Schedule (calc_date,   
                                       Maturity_date,   
                                       Coupon_frequency,   
                                       Calendar,   
                                       Business_convention,   
                                       Business_convention,   
                                       Ql. DateGeneration. Backward,   
                                       False)
                Helper = ql.FixedRateBondHelper (ql.QuoteHandle (ql.SimpleQuote (price)),   
                                                Settlement_days,   
                                                Face_amount,   
                                                Schedule,   
                                                [coupon],   
                                                Day_count,   
                                                Business_convention)
                Bond_helpers.Append (helper)
    In [4]: yield_curve = ql.PiecewiseCubicZero (calc_date,    bond_helpers,    day_count)
            Yield_curve_handle = ql.YieldTermStructureHandle (yield_curve)
            Discount_factors = [yield_curve.Discount (d) for d in maturity_dates]
            DataFrame (list (zip (maturity_dates,    discount_factors)),   
                      Columns= ["Dates",    "Discount Factors"],   
                      Index=['']*len (maturity_dates))
    Out[4]: 
  Dates Discount Factors --- --------------------- ------------------   December 24 th,    2015 0.999935   February 25 th,    2016 0.999576   May 26 th,    2016 0.998119   November 10 th,    2016 0.995472   November 30 th,    2017 0.981524   November 15 th,    2018 0.964278   November 30 th,    2020 0.920306   November 30 th,    2022 0.868533   November 15 th,    2025 0.799447   November 15 th,    2045 0.384829 ##### Treasury Futures { #chap44 . xhtml\_leanpub-auto-treasury-futures} Here we want to understand how to model treasury futures contract. Let us look at the TYZ 5,    the treasury futures on the 10 year note for delivery in December 2015. The notional deliverable is a 10-year 6% coupon note. In reality,    the seller of the futures contract can deliver from a basket of securities. For now,    lets assume that the deliverable is actually a 6% coupon 10-year note issued as of the calculation date. Let us construct a 10 year treasury note and value this security. The futures price for the TYZ 5 is 127.0625.
    In [5]: def create_tsy_security (bond_issue_date,    
                                    Bond_maturity_date,   
                                    Coupon_rate,   
                                    Coupon_frequency=ql.Period (6,    ql. Months),   
                                    Day_count=ql.ActualActual (),   
                                    Calendar=ql.UnitedStates ()):
                Face_value = 100.
                Settlement_days = 0
                Schedule = ql.Schedule (bond_issue_date,   
                                       Bond_maturity_date,   
                                       Coupon_frequency,   
                                       Calendar,   
                                       Ql. ModifiedFollowing,   
                                       Ql. ModifiedFollowing,   
                                       Ql. DateGeneration. Forward,   
                                       False)
                Security = ql.FixedRateBond (settlement_days,   
                                            Face_value,   
                                            Schedule,   
                                            [coupon_rate],   
                                            Day_count)
                Return security
    In [6]: bond_issue_date = calc_date 
            Delivery_date = ql.Date (1,   12,   2015)
            Bond_maturity_date = bond_issue_date + ql.Period (10,    ql. Years)
            Day_count = ql.ActualActual ()
            Coupon_frequency = ql.Period (6,    ql. Months)
            Coupon_rate = 6/100.
            Deliverable = create_tsy_security (bond_issue_date,   
                                              Bond_maturity_date,   
                                              Coupon_rate,   
                                              Coupon_frequency,   
                                              Day_count,   
                                              Calendar)
            Bond_engine = ql.DiscountingBondEngine (yield_curve_handle)
            Deliverable.SetPricingEngine (bond_engine)
Lets calculate the Z-Spread for this deliverable. The Z-Spread is the static spread added to the yield curve to match the price of the security. This spread is a measure of the risk associated with the security. For a treasury security,    you would expect this to be zero.
    In [7]: futures_price = 127.0625
            Clean_price = futures_price*yield_curve.Discount (delivery_date)
            Zspread = ql.BondFunctions.ZSpread (deliverable,    clean_price,   
                                               Yield_curve,    day_count,    
                                               Ql. Compounded,    ql. Semiannual,    
                                               Calc_date)*10000
            Print ("Z-Spread =%3.0 fbp" % (zspread))
    Out[7]: Z-Spread = 71 bp
Here we get a spread of 71 basis points. This is unusually high for a treasury futures contract. ##### Cheapest To Deliver { #chap44 . xhtml\_leanpub-auto-cheapest-to-deliver} Above we used a fictional 6% coupon bond as the deliverable. In reality,    the deliverable is picked from a basket of securities based on what is the cheapest to deliver. Cheapest to deliver is not the cheapest in price. The seller of the futures contract,    has to buy the delivery security from the market and sell it at an adjusted futures price. The adjusted futures price is given as: \*Adjusted Futures Price = Futures Price x Conversion Factor\* The gain or loss to the seller is given by the basis,    \*Basis = Cash Price - Adjusted Futures Price\* So the cheapest to deliver is expected to be the security with the lowest basis. The conversion factor for a security is the price of the security with a 6% yield. Let us look at a basket of securities that is underlying this futures contract to understand this aspect.
    In [8]: day_count = ql.ActualActual ()
            Basket = [(1.625,    ql.Date (15,   8,   2022),    97.921875),    
                      (1.625,    ql.Date (15,   11,   2022),    97.671875),   
                      (1.75,    ql.Date (30,   9,   2022),    98.546875),   
                      (1.75,    ql.Date (15,   5,   2023),    97.984375),   
                      (1.875,    ql.Date (31,   8,   2022),    99.375),   
                      (1.875,    ql.Date (31,   10,   2022),    99.296875),   
                      (2.0,    ql.Date (31,   7,   2022),    100.265625),    
                      (2.0,    ql.Date (15,   2,   2023),    100.0625),   
                      (2.0,    ql.Date (15,   2,   2025),    98.296875),   
                      (2.0,    ql.Date (15,   8,   2025),    98.09375),   
                      (2.125,    ql.Date (30,   6,   2022),    101.06250),   
                      (2.125,    ql.Date (15,   5,   2025),    99.25),   
                      (2.25,    ql.Date (15,   11,   2024),    100.546875),   
                      (2.25,    ql.Date (15,   11,   2025),    100.375),   
                      (2.375,    ql.Date (15,   8,   2024),    101.671875),   
                      (2.5,    ql.Date (15,   8,   2023),    103.25),   
                      (2.5,    ql.Date (15,   5,   2024),    102.796875),   
                      (2.75,    ql.Date (15,   11,   2023),    105.0625),   
                      (2.75,    ql.Date (15,   2,   2024),    104.875)
                      ]
            Securities = []
            Min_basis = 100; min_basis_index = -1
            For i,    b in enumerate (basket):
                Coupon,    maturity,    price = b
                Issue = maturity - ql.Period (10,    ql. Years)
                S = create_tsy_security (issue,    maturity,    coupon/100.)
                Bond_engine = ql.DiscountingBondEngine (yield_curve_handle)
                s.setPricingEngine (bond_engine)
                Cf = ql.BondFunctions.CleanPrice (s,    0.06,   
                                                 Day_count,    ql. Compounded,   
                                                 Ql. Semiannual,    calc_date)/100.
                Adjusted_futures_price = futures_price * cf
                Basis = price-adjusted_futures_price
                If basis< min_basis:
                    Min_basis = basis 
                    Min_basis_index = i
                Securities.Append ((s,    cf))
            Ctd_info = basket[min_basis_index]
            Ctd_bond,    ctd_cf = securities[min_basis_index]
            Ctd_price = ctd_info[2]
            Print ("%-30 s = %lf" % ("Minimum Basis",    min_basis))
            Print ("%-30 s = %lf" % ("Conversion Factor",    ctd_cf))
            Print ("%-30 s = %lf" % ("Coupon",    ctd_info[0]))
            Print ("%-30 s = %s" % ("Maturity",    ctd_info[1]))
            Print ("%-30 s = %lf" % ("Price",    ctd_info[2]))
    Out[8]: Minimum Basis                  = 0.450601
            Conversion Factor              = 0.791830
            Coupon                         = 2.125000
            Maturity                       = June 30 th,    2022
            Price                          = 101.062500
The basis is the loss for a notional of 100 that the seller accrues to close this contract. For a single futures contract (which has a 100000 notional),    there is a loss of 450.60. NOTE: You will need my $$pull request$$( https://github.com/lballabio/quantlib-old/pull/370 ) to execute the \`FixedRateBondForward\` class since it is not exposed in SWIG at the moment.
    In [9]: futures_maturity_date = ql.Date (21,   12,   2015)
            Futures = ql.FixedRateBondForward (
                Calc_date,    futures_maturity_date,   
                Ql. Position. Long,    0.0,    settlement_days,   
                Day_count,    calendar,    business_convention,   
                Ctd_bond,    yield_curve_handle,    yield_curve_handle)
The valuation of the futures contract and the underlying is shown below:
    In [10]: model_futures_price = futures.CleanForwardPrice ()/ctd_cf
             Implied_yield = futures.ImpliedYield (ctd_price/ctd_cf,    futures_price,    
                                                  Calc_date,    ql. Compounded,   
                                                  Day_count). Rate ()
             Z_spread = ql.BondFunctions.ZSpread (ctd_bond,    ctd_price,    yield_curve,    
                                                 Day_count,    ql. Compounded,    ql. Semiannual,    
                                                 Calc_date)
             Ytm = ql.BondFunctions.BondYield (ctd_bond,    ctd_price,    day_count,   
                                              Ql. Compounded,    ql. Semiannual,    calc_date)
             Print ("%-30 s = %lf" % ("Model Futures Price",    model_futures_price))
             Print ("%-30 s = %lf" % ("Market Futures Price",    futures_price))
             Print ("%-30 s = %lf" % ("Model Adjustment",    model_futures_price-futures_price))
             Print ("%-30 s = %2.3 f%%" % ("Implied Yield",    implied_yield*100))
             Print ("%-30 s = %2.1 fbps" % ("Forward Z-Spread",    z_spread*10000))
             Print ("%-30 s = %2.3 f%%" % ("Forward YTM ",    ytm*100))
    Out[10]: Model Futures Price            = 127.610365
             Market Futures Price           = 127.062500
             Model Adjustment               = 0.547865
             Implied Yield                  = -7.473%
             Forward Z-Spread               = 1.6 bps
             Forward YTM                    = 1.952%
\##### References { #chap44 . xhtml\_leanpub-auto-references-2} \\$$1\\$$ $$Understanding Treasury Futures$$( https://www.cmegroup.com/education/files/understanding-treasury-futures.pdf ),    CME Group PDF ##### Conclusion { #chap44 . xhtml\_leanpub-auto-conclusion-7} In this chapter,    we looked into understanding and valuing treasury futures contracts. We used the QuantLib \`FixedRateBondForward\` class in order to model the futures contract. But,    we also made a cheapest to deliver calculation to figure out the deliverable.
$$$${ #chap45 . xhtml}
\## $$35.$${. Section-number}Mischievous pricing conventions { #chap45 . xhtml\_leanpub-auto-mischievous-pricing-conventions} (Based on $$a question$$( http://stackoverflow.com/questions/15273797/ ) by \*Stack Exchange\* user ducky. Thanks!)
    In [1]: import QuantLib as ql
            Import pandas as pd
\##### The case of the bond off par { #chap45 . xhtml\_leanpub-auto-the-case-of-the-bond-off-par} Like our user,    I'll instantiate a four-years floating-rate bond with three-months coupons. It's being issued on the evaluation date,    January 5 th 2010,    and for simplicity I won't use any settlement days or holidays:
    In [2]: today = ql.Date (5,    ql. January,    2010)
            Ql.Settings.Instance (). EvaluationDate = today
            Discounting_curve = ql.RelinkableYieldTermStructureHandle ()
            Forecasting_curve = ql.RelinkableYieldTermStructureHandle ()
            Index = ql.USDLibor (ql.Period (3,    ql. Months),    forecasting_curve)
            Settlement_days = 0
            Calendar = ql.NullCalendar ()
            Face_amount = 100.0
            Schedule = ql.Schedule (today,    today + ql.Period (4,    ql. Years),   
                                   Ql.Period (3,    ql. Months),    calendar,   
                                   Ql. Unadjusted,    ql. Unadjusted,   
                                   Ql. DateGeneration. Forward,    False)
            Bond = ql.FloatingRateBond (settlement_days,   
                                       Face_amount,   
                                       Schedule,   
                                       Index,   
                                       Ql. Thirty 360 (),   
                                       Ql. Unadjusted,   
                                       FixingDays = 0)
            Bond.SetPricingEngine (ql.DiscountingBondEngine (discounting_curve))
To price it,    we use a flat 10% quarterly rate for both forecasting and discounting...
    In [3]: flat_rate = ql.FlatForward (today,    0.10,    ql. Thirty 360 (),   
                                       Ql. Compounded,    ql. Quarterly)
            Forecasting_curve.LinkTo (flat_rate)
            Discounting_curve.LinkTo (flat_rate)
... So we expect the bond to be at par. Is it?
    In [4]: print (bond.CleanPrice ())
    Out[4]: 99.5433545426823
Hmm. ##### What is happening here? { #chap45 . xhtml\_leanpub-auto-what-is-happening-here} We have mismatched a few conventions. The ones with the largest effect are the day-count conventions used for the curve and the index. Here they are:
    In [5]: print (flat_rate.DayCounter ())
            Print (ql. As_coupon (bond.Cashflows ()[0]). DayCounter ())
            Print (index.DayCounter ())
    Out[5]: 30/360 (Bond Basis) day counter
            30/360 (Bond Basis) day counter
            Actual/360 day counter
Thus,    the coupons accrue for the expected time (given by their day-count convention); however,    the rates are not the expected 10%. They are calculated from discount factors given by the curve according to its 30/360 convention and recombined by the index according to its Actual/360 convention,    which doesn't end well.
    In [6]: coupons = [ ql. As_coupon (c) for c in bond.Cashflows ()[:-1] ]
            pd.DataFrame ([(c.date (),    c.rate (),    c.accrualPeriod ())
                          For c in coupons ],   
                         Columns=('Date',    'Rate',    'Accrual period'),   
                         Index=range (1,   len (coupons)+1))
    Out[6]: 
  Date Rate Accrual period ---- ------------------- ---------- ---------------- 1 April 5 th,    2010 0.100014 0.25 2 July 5 th,    2010 0.098901 0.25 3 October 5 th,    2010 0.097826 0.25 4 January 5 th,    2011 0.097826 0.25 5 April 5 th,    2011 0.100000 0.25 6 July 5 th,    2011 0.098901 0.25 7 October 5 th,    2011 0.097826 0.25 8 January 5 th,    2012 0.097899 0.25 9 April 5 th,    2012 0.098952 0.25 10 July 5 th,    2012 0.098849 0.25 11 October 5 th,    2012 0.097826 0.25 12 January 5 th,    2013 0.097826 0.25 13 April 5 th,    2013 0.100014 0.25 14 July 5 th,    2013 0.098901 0.25 15 October 5 th,    2013 0.097826 0.25 16 January 5 th,    2014 0.097826 0.25 ##### The importance of being consistent { #chap45 . xhtml\_leanpub-auto-the-importance-of-being-consistent} In order to reproduce the textbook value,    we have to reconcile the different conventions (which are,    well,    conveniently glossed over in textbooks). The correct one to choose depends on the terms and conditions of the bond; it is likely to be the Actual/360 convention used by the USD libor,    so we'll pass it to both the bond and the curve:
    In [7]: bond = ql.FloatingRateBond (settlement_days,   
                                       Face_amount,   
                                       Schedule,   
                                       Index,   
                                       Ql. Actual 360 (),   
                                       Ql. Unadjusted,   
                                       FixingDays = 0)
            Bond.SetPricingEngine (ql.DiscountingBondEngine (discounting_curve))
    In [8]: flat_rate_2 = ql.FlatForward (today,    0.10,    ql. Actual 360 (),   
                                         Ql. Compounded,    ql. Quarterly)
            Forecasting_curve.LinkTo (flat_rate_2)
            Discounting_curve.LinkTo (flat_rate_2)
    In [9]: print (bond.CleanPrice ())
    Out[9]: 100.00117521248728
There's still a small discrepancy,    which is likely due to date adjustments in the underlying USD libor fixings. The coupon rates are much better overall,    so we seem to be on the right track.
    In [10]: coupons = [ ql. As_coupon (c) for c in bond.Cashflows ()[:-1] ]
             pd.DataFrame ([(c.date (),    c.rate (),    c.accrualPeriod ())
                           For c in coupons ],   
                          Columns=('Date',    'Rate',    'Accrual period'),   
                          Index=range (1,   len (coupons)+1))
    Out[10]: 
  Date Rate Accrual period ---- ------------------- ---------- ---------------- 1 April 5 th,    2010 0.100014 0.250000 2 July 5 th,    2010 0.100014 0.252778 3 October 5 th,    2010 0.100028 0.255556 4 January 5 th,    2011 0.100028 0.255556 5 April 5 th,    2011 0.100000 0.250000 6 July 5 th,    2011 0.100014 0.252778 7 October 5 th,    2011 0.100028 0.255556 8 January 5 th,    2012 0.100055 0.255556 9 April 5 th,    2012 0.100041 0.252778 10 July 5 th,    2012 0.099986 0.252778 11 October 5 th,    2012 0.100028 0.255556 12 January 5 th,    2013 0.100028 0.255556 13 April 5 th,    2013 0.100014 0.250000 14 July 5 th,    2013 0.100014 0.252778 15 October 5 th,    2013 0.100028 0.255556 16 January 5 th,    2014 0.100028 0.255556 To get a (theoretical) par bond,    we can use a custom index whose conventions match exactly those of the bond we wanted to use: no fixing days,    30/360 day-count convention,    and no holidays. We'll use a curve with the same day-count convention,    too.
    In [11]: index = ql.IborIndex (
                 'Mock Libor',    ql.Period (3,    ql. Months),    0,    ql.USDCurrency (),   
                 Ql.NullCalendar (),    ql. Unadjusted,    False,    ql. Thirty 360 (),   
                 Forecasting_curve)
             Bond = ql.FloatingRateBond (settlement_days,   
                                        Face_amount,   
                                        Schedule,   
                                        Index,   
                                        Ql. Thirty 360 (),   
                                        Ql. Unadjusted,   
                                        FixingDays = 0)
             Bond.SetPricingEngine (ql.DiscountingBondEngine (discounting_curve))
    In [12]: forecasting_curve.LinkTo (flat_rate)
             Discounting_curve.LinkTo (flat_rate)
And now,    we finally hit the jackpot:
    In [13]: print (bond.CleanPrice ())
    Out[13]: 100.00000000000001
    In [14]: coupons = [ ql. As_coupon (c) for c in bond.Cashflows ()[:-1] ]
             pd.DataFrame ([(c.date (),    c.rate (),    c.accrualPeriod ())
                           For c in coupons ],   
                          Columns=('Date',    'Rate',    'Accrual period'),   
                          Index=range (1,   len (coupons)+1))
    Out[14]: 
  Date Rate Accrual period ---- ------------------- ------ ---------------- 1 April 5 th,    2010 0.1 0.25 2 July 5 th,    2010 0.1 0.25 3 October 5 th,    2010 0.1 0.25 4 January 5 th,    2011 0.1 0.25 5 April 5 th,    2011 0.1 0.25 6 July 5 th,    2011 0.1 0.25 7 October 5 th,    2011 0.1 0.25 8 January 5 th,    2012 0.1 0.25 9 April 5 th,    2012 0.1 0.25 10 July 5 th,    2012 0.1 0.25 11 October 5 th,    2012 0.1 0.25 12 January 5 th,    2013 0.1 0.25 13 April 5 th,    2013 0.1 0.25 14 July 5 th,    2013 0.1 0.25 15 October 5 th,    2013 0.1 0.25 16 January 5 th,    2014 0.1 0.25
$$$${ #chap46 . xhtml}
\## $$36.$${. Section-number}More mischievous conventions { #chap46 . xhtml\_leanpub-auto-more-mischievous-conventions} (Based on $$a question$$( http://quant.stackexchange.com/questions/12707/ ) by \*Stack Exchange\* user nickos 556. Thanks!)
    In [1]: import QuantLib as ql
            From pandas import DataFrame
\##### The case of the two slightly different prices { #chap46 . xhtml\_leanpub-auto-the-case-of-the-two-slightly-different-prices} nickos 556 instantiated a fixed-rate bond with semiannual payments and tried to deduce its price from a given yield:
    In [2]: today = ql.Date (27,    ql. January,    2011)
            Ql.Settings.Instance (). EvaluationDate = today
    In [3]: issueDate = ql.Date (28,    ql. January,    2011)
            Maturity = ql.Date (31,    ql. August,    2020)
            Schedule = ql.Schedule (issueDate,    maturity,    ql.Period (ql. Semiannual),   
                                   Ql.UnitedStates (ql. UnitedStates. GovernmentBond),   
                                   Ql. Unadjusted,    ql. Unadjusted,   
                                   Ql. DateGeneration. Backward,    False)
            Bond = ql.FixedRateBond (1,    100.0,    schedule,   
                                    [0.03625],   
                                    Ql.ActualActual (ql. ActualActual. Bond),   
                                    Ql. Unadjusted,   
                                    100.0)
This can be done either by passing the yield directly...
    In [4]: bond_yield = 0.034921
            P 1 = bond.DirtyPrice (bond_yield,    bond.DayCounter (),   
                                 Ql. Compounded,    ql. Semiannual)
... Or by first setting an engine that uses a corresponding flat term structure.
    In [5]: flat_curve = ql.FlatForward (bond.SettlementDate (),    bond_yield,   
                                        Ql.ActualActual (ql. ActualActual. Bond),   
                                        Ql. Compounded,    ql. Semiannual)
            Engine = ql.DiscountingBondEngine (ql.YieldTermStructureHandle (flat_curve))
            Bond.SetPricingEngine (engine)
            P 2 = bond.DirtyPrice ()
Surprisingly,    the results were different:
    In [6]: DataFrame ([(P 1,    P 2)],    columns=['with yield',    'with curve'],    index=[''])
    Out[6]: 
  with yield with curve --- ------------ ------------   101.076816 101.079986 ##### What happened? { #chap46 . xhtml\_leanpub-auto-what-happened-2} Mischievous conventions again. The bond uses the Actual/Actual (Bond) convention,    which has a requirement: in the case of short or long coupons,    we also need to pass a reference start and end date that determine the regular underlying period. Case in point: this bond has a short first coupon.
    In [7]: DataFrame ([(ql. As_coupon (c). AccrualStartDate (),   
                        Ql. As_coupon (c). AccrualEndDate ())
                       For c in bond.Cashflows ()[:-1]],   
                      Columns = ('start date',   'end date'),   
                      Index = range (1,    len (bond.Cashflows ())))
    Out[7]: 
  Start date end date ---- --------------------- --------------------- 1 January 28 th,    2011 February 28 th,    2011 2 February 28 th,    2011 August 31 st,    2011 3 August 31 st,    2011 February 29 th,    2012 4 February 29 th,    2012 August 31 st,    2012 5 August 31 st,    2012 February 28 th,    2013 6 February 28 th,    2013 August 31 st,    2013 7 August 31 st,    2013 February 28 th,    2014 8 February 28 th,    2014 August 31 st,    2014 9 August 31 st,    2014 February 28 th,    2015 10 February 28 th,    2015 August 31 st,    2015 11 August 31 st,    2015 February 29 th,    2016 12 February 29 th,    2016 August 31 st,    2016 13 August 31 st,    2016 February 28 th,    2017 14 February 28 th,    2017 August 31 st,    2017 15 August 31 st,    2017 February 28 th,    2018 16 February 28 th,    2018 August 31 st,    2018 17 August 31 st,    2018 February 28 th,    2019 18 February 28 th,    2019 August 31 st,    2019 19 August 31 st,    2019 February 29 th,    2020 20 February 29 th,    2020 August 31 st,    2020 The accrual time for the coupon,    starting January 27 th 2011 and ending February 28 th 2011,    must be calculated as:
    In [8]: dayCounter = ql.ActualActual (ql. ActualActual. Bond)
            T = dayCounter.YearFraction (ql.Date (28,    ql. January,    2011),   
                                        Ql.Date (28,    ql. February,    2011),   
                                        Ql.Date (28,    ql. August,    2010),   
                                        Ql.Date (28,    ql. February,    2011))
            Print (T)
    Out[8]: 0.08423913043478261
If the coupon were annual,    it would be:
    In [9]: print (dayCounter.YearFraction (ql.Date (28,    ql. January,    2011),   
                                          Ql.Date (28,    ql. February,    2011),   
                                          Ql.Date (28,    ql. February,    2010),   
                                          Ql.Date (28,    ql. February,    2011)))
    Out[9]: 0.08493150684931507
The corresponding discount factor given the yield is as follows:
    In [10]: y = ql.InterestRate (bond_yield,    dayCounter,    ql. Compounded,    ql. Semiannual)
             print (y.discountFactor (T))
    Out[10]: 0.997087920498809
\##### Yield-based calculation { #chap46 . xhtml\_leanpub-auto-yield-based-calculation} The yield-based calculation uses the above to discount the first coupon,    and combines it with discount factors corresponding to the regular coupon times to discount the others. We can write down the full computation:
    In [11]: data = []
             For i,    c in enumerate (bond.Cashflows ()[:-1]):
                 C = ql. As_coupon (c)
                 A = c.amount ()
                 T = c.accrualPeriod ()
                 D = y.discountFactor (T)
                 D_cumulative = D if i == 0 else D * data[-1][3]
                 A_discounted = A*D_cumulative
                 Data.Append ((A,    T,    D,    D_cumulative,    A_discounted))
             Data.Append ((100,   '',   '',    D_cumulative,    100*D_cumulative))
             Data = DataFrame (data,   
                              Columns = ('amount',    'T',    'discount',   
                                         'discount (cum.)',    'amount (disc.)'),   
                              Index = ['']*len (data))
             Data
    Out[11]: 
  Amount T discount discount (cum.) amount (disc.) --- ------------ ----------- ---------- ----------------- ----------------   0.305367 0.0842391 0.997088 0.997088 0.304478   1.812500 0.5 0.982839 0.979977 1.776208   1.812500 0.5 0.982839 0.963160 1.745727   1.812500 0.5 0.982839 0.946631 1.715769   1.812500 0.5 0.982839 0.930386 1.686325   1.812500 0.5 0.982839 0.914420 1.657386   1.812500 0.5 0.982839 0.898728 1.628944   1.812500 0.5 0.982839 0.883305 1.600990   1.812500 0.5 0.982839 0.868146 1.573515   1.812500 0.5 0.982839 0.853248 1.546513   1.812500 0.5 0.982839 0.838606 1.519973   1.812500 0.5 0.982839 0.824215 1.493889   1.812500 0.5 0.982839 0.810070 1.468253   1.812500 0.5 0.982839 0.796169 1.443056   1.812500 0.5 0.982839 0.782506 1.418292   1.812500 0.5 0.982839 0.769077 1.393953   1.812500 0.5 0.982839 0.755879 1.370031   1.812500 0.5 0.982839 0.742908 1.346521   1.812500 0.5 0.982839 0.730159 1.323413   1.812500 0.5 0.982839 0.717629 1.300702   100.000000     0.717629 71.762879 The bond price is the sum of the discounted amounts...
    In [12]: print (sum (data['amount (disc.)']))
    Out[12]: 101.07681646503603
... And,    not surprisingly,    equals the yield-based bond price.
    In [13]: print (bond.DirtyPrice (bond_yield,    bond.DayCounter (),   
                                   Ql. Compounded,    ql. Semiannual))
    Out[13]: 101.07681646503603
\##### Curve-based calculation { #chap46 . xhtml\_leanpub-auto-curve-based-calculation} Long story short: the bond engine gets the first discount wrong. Given the curve interface,    all it can do is ask for the discounts at the coupon dates,    as follows:
    In [14]: data = []
             For c in bond.Cashflows ()[:-1]:
                 A = c.amount ()
                 D = flat_curve.Discount (c.date ())
                 A_discounted = A*D
                 Data.Append ((A,    D,    A_discounted))
             Data.Append ((100.0,    D,    100.0*D))
             Data = DataFrame (data,   
                              Columns = ('amount',    'discount',    'amount (disc.)'),   
                              Index = ['']*len (data))
             Data
    Out[14]: 
  Amount discount amount (disc.) --- ------------ ---------- ----------------   0.305367 0.997119 0.304487   1.812500 0.980008 1.776264   1.812500 0.963190 1.745782   1.812500 0.946661 1.715823   1.812500 0.930415 1.686378   1.812500 0.914449 1.657438   1.812500 0.898756 1.628995   1.812500 0.883332 1.601040   1.812500 0.868174 1.573565   1.812500 0.853275 1.546561   1.812500 0.838632 1.520021   1.812500 0.824240 1.493936   1.812500 0.810096 1.468299   1.812500 0.796194 1.443101   1.812500 0.782530 1.418336   1.812500 0.769102 1.393997   1.812500 0.755903 1.370074   1.812500 0.742931 1.346563   1.812500 0.730182 1.323455   1.812500 0.717651 1.300743   100.000000 0.717651 71.765129 The result equals the curve-based price.
    In [15]: print (sum (data['amount (disc.)']))
    Out[15]: 101.0799861183387
    In [16]: print (bond.DirtyPrice ())
    Out[16]: 101.0799861183387
The problem is that the first call to the \`discount\` method,    that is,   
    In [17]: flat_curve.Discount (ql.Date (28,    ql. February,    2011))
    Out[17]: 0.9971191880350325
Results in a call to:
    In [18]: print (dayCounter.YearFraction (ql.Date (28,    ql. January,    2011),   
                                           Ql.Date (28,    ql. February,    2011)))
    Out[18]: 0.08333333333333333
Compare this to the correct one:
    In [19]: T = dayCounter.YearFraction (ql.Date (28,    ql. January,    2011),   
                                         Ql.Date (28,    ql. February,    2011),   
                                         Ql.Date (28,    ql. August,    2010),   
                                         Ql.Date (28,    ql. February,    2011))
             Print (T)
    Out[19]: 0.08423913043478261
Does this account for the difference in price? Yes,    it does. The two prices can be reconciled as follows:
    In [20]: P_y = bond.DirtyPrice (bond_yield,    bond.DayCounter (),   
                                   Ql. Compounded,    ql. Semiannual)
             D_y = y.discountFactor (T)
             P_c = bond.DirtyPrice ()
             D_c = flat_curve.Discount (ql.Date (28,    ql. February,    2011))
             Print (P_y)
             Print (P_c*(D_y/D_c))
    Out[20]: 101.07681646503603
             101.0768164650361
\`\`{=html}
$$$${ #chap47 . xhtml}
\# Appendix { #chap47 . xhtml\_leanpub-auto-appendix}
$$$${ #chap48 . xhtml}
\## Translating QuantLib Python examples to C++ { #chap48 . xhtml\_leanpub-auto-translating-quantlib-python-examples-to-c} It's easy enough to translate the Python code shown in this book into the corresponding C++ code. As an example,    I'll go through a bit of code from the notebook on instruments and pricing engines.
    In [1]: import QuantLib as ql
This line imports the \`QuantLib\` module and provides a shorter alias that can be used to qualify the classes and functions it contains. The C++ equivalent would be:
    #include <ql/quantlib.hpp>
    Namespace ql = QuantLib;
In C++,    however,    I wouldn't include the global \`quantlib. Hpp\` header,    which would inflate your compilation times; instead,    you can include the specific headers for the classes you'll use. Moreover,    in C++ is not as discouraged as in Python to import the whole contents of a namespace in a source file,    that is,    to use
    Using namespace QuantLib;
However,    the above should not be used in header files; ask the nearest C++ guru if you're not sure why.
    In [2]: today = ql.Date (7,    ql. March,    2014)
            Ql.Settings.Instance (). EvaluationDate = today
The code above has a couple of caveats. The first line is easy enough to translate; you'll have to declare the type to the variable (or use \`auto\` if you're compiling in C++11 mode). The second line is trickier. To begin with,    the syntax to call static methods differs in Python and C++,    so you'll have to replace the dot before \`instance\` by a double colon (the same goes for the namespace qualifications). Then,    \`evaluationDate\` is a property in Python but a method in C++; it was changed in the Python module to be more idiomatic,    since it's not that usual in Python to assign to the result of a method. Luckily,    you won't find many such cases. The translated code is:
    Ql:: Date today (7,    ql:: March,    2014);
    Ql::Settings:: instance (). EvaluationDate () = today;
Next:
    In [3]: option = ql.EuropeanOption (ql.PlainVanillaPayoff (ql. Option. Call,    100.0),   
                                       Ql.EuropeanExercise (ql.Date (7,    ql. June,    2014)))
Again,    you'll have to declare the type of the variable. Furthermore,    the constructor of \`EuropeanOption\` takes its arguments by pointer,    or more precisely,    by \`boost:: shared\_ptr\`. This is hidden in Python,    since there's no concept of pointer in the language; the SWIG wrappers take care of exporting \`boost:: shared\_ptr\` simply as \`T\`. The corresponding C++ code (note also the double colon in \`Option:: Call\`):
    Ql:: EuropeanOption option (
        boost::make_shared<ql::PlainVanillaPayoff>(ql::Option:: Call,    100.0),   
        Boost::make_shared<ql:: EuropeanExercise (ql:: Date (7,    ql:: June,    2014)));
(A note: in the remainder of the example,    I'll omit the \`boost::\` and \`ql::\` namespaces for brevity.)
    In [4]: u = ql.SimpleQuote (100.0)
            R = ql.SimpleQuote (0.01)
            Sigma = ql.SimpleQuote (0.20)
Quotes,    too,    are stored and passed around as \`shared\_ptr\` instances; this is the case for most polymorphic classes (when in doubt,    you can look at the C++ headers and check the signatures of the functions you want to call). The above becomes:
    shared_ptr<SimpleQuote> u = make_shared<SimpleQuote>(100.0);
    shared_ptr<SimpleQuote> r = make_shared<SimpleQuote>(0.01);
    shared_ptr<SimpleQuote> sigma = make_shared<SimpleQuote>(0.20);
Depending on what you need to do with them,    the variables might also be declared as \`shared\_ptr\`. I used the above,    since I'll need to call a method of \`SimpleQuote\` in a later part of the code.
    In [5]: riskFreeCurve = ql.FlatForward (0,    ql.TARGET (),   
                                           Ql.QuoteHandle (r),    ql. Actual 360 ())
            Volatility = ql.BlackConstantVol (0,    ql.TARGET (),   
                                             Ql.QuoteHandle (sigma),    ql. Actual 360 ())
The \`Handle\` template class couldn't be exported as such,    because Python doesn't have templates. Thus,    the SWIG wrappers have to declare separate classes \`QuoteHandle\`,    \`YieldTermStructureHandle\` and so on. In C++,    you can go back to the original syntax.
    shared_ptr<YieldTermStructure> riskFreeCurve =
        make_shared<FlatForward>(0,    TARGET (),   
                                 Handle<Quote>(r),    Actual 360 ());
    shared_ptr<BlackVolTermStructure> volatility =
        make_shared<BlackConstantVol>(0,    TARGET (),   
                                      Handle<Quote>(sigma),    Actual 360 ());
Next,   
    In [6]: process = ql.BlackScholesProcess (ql.QuoteHandle (u),   
                                             Ql.YieldTermStructureHandle (riskFreeCurve),   
                                             Ql.BlackVolTermStructureHandle (volatility))
Turns into
    shared_ptr<BlackScholesProcess> process =
        make_shared<BlackConstantVol>(
            Handle<Quote>(u),   
            Handle<YieldTermStructure>(riskFreeCurve),   
            Handle<BlackVolTermStructure>(volatility));
And
    In [7]: engine = ql.AnalyticEuropeanEngine (process)
Into
    shared_ptr<PricingEngine> engine =
        make_shared<AnalyticEuropeanEngine>(process);
So far,    we've been calling constructors. Method invocation works the same in Python and C++,    except that in C++ we might be calling methods through a pointer. Therefore,   
    In [8]: option.SetPricingEngine (engine)
    In [9]: print (option.NPV ())
    In [10]: print (option.Delta ())
             Print (option.Gamma ())
             Print (option.Vega ())
Where \`option\` is an object in C++,    becomes
    Option.SetPricingEngine (engine);
    Cout << option.NPV () << endl;
    Cout << option.Delta () << endl;
    Cout << option.Gamma () << endl;
    Cout << option.Vega () << endl;
Whereas
    In [11]: u.setValue (105.0)
Since \`u\` is a (smart) pointer,    turns into
    U->setValue (105.0);
Of course,    the direct translation I've been doing only applies to the QuantLib code; I'm not able to point you to libraries that replace the graphing functionality in \`matplotlib\`,    or the data-analysis facilities in \`pandas\`,    or the parallel math functions in \`numpy\`. However,    I hope that the above can still enable you to extract value from this cookbook,    even if you're programming in C++.