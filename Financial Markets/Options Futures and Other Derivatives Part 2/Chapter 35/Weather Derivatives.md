---
tags:
  - cdd
  - cme_weather_contracts
  - hhd
  - otc_derivatives
  - weather_derivatives
aliases:
  - CDD
  - HDD
  - Weather Derivatives
key_concepts:
  - companies hedge weather risk
  - cooling degree days
  - cumulative HDD or CDD
  - forward or option contract
  - heating degree days
---

# 35.5 WEATHER DERIVATIVES  

Many companies are in the position where their performance is liable to be adversely affected by the weather.' It makes sense for these companies to consider hedging their weather risk in much the same way as they hedge foreign exchange or interest rate risks.  

The first over-the-counter weather derivatives were introduced in 1997. To understand how they work, we explain two variables:.  

HDD: Heating degree days  

CDD: Cooling degree days  

A day's HDD is defined as  

$$
\mathrm{HDD}=\operatorname*{max}(0,65-A)
$$  

and a day's CDD is defined as  

$$
\mathrm{CDD}=\operatorname*{max}(0,A-65)
$$  

where $A$ is the average of the highest and lowest temperature during the day at a specified weather station, measured in degrees Fahrenheit. For example, if the maximum temperature during a day (midnight to midnight) is $68^{\circ}$ Fahrenheit and the minimum temperature is $44^{\circ}$ Fahrenheit, $A=56$ . The daily HDD is then 9 and the daily CDD is 0.  

A typical over-the-counter product is a forward or option contract providing a payoff dependent on the cumulative HDD or CDD during a month. For example, a deriva-. tives dealer could in January 2022 sell a client a call option on the cumulative HDD. during February 2023 at the Chicago O'Hare Airport weather station with a strike price of 700 and a payment rate of $\$10,000$ per degree day. If the actual cumulative HDD is 820, the payoff is $\$1.2$ million. Often contracts include a payment cap. If the payment. cap in our example is $\$1.5$ million, the contract is the equivalent of a bull spread (see Chapter 12). The client has a long call option on cumulative HDD with a strike price of. 700 and a short call option with a strike price of 850.  

A day's HDD is a measure of the volume of energy required for heating during the day. A day's CDD is a measure of the volume of energy required for cooling during the day. Most weather derivative contracts are entered into by energy producers and energy consumers. But retailers, supermarket chains, food and drink manufacturers, health service companies, agriculture companies, and companies in the leisure industry are also potential users of weather derivatives. The Weather Risk Management Association (www.wrma.org) has been formed to serve the interests of the weather risk management industry.  

In September 1999 the Chicago Mercantile Exchange (CME) began trading weather futures and European options on weather futures. The contracts are on the cumulative. HDD and CDD for a month observed at a weather station. The contracts are settled in cash just after the end of the month once the HDD and CDD are known. One futures contract is on $\$20$ times the cumulative HDD or CDD for the month. The CME now. offers weather futures and options for several cities throughout the world..  
