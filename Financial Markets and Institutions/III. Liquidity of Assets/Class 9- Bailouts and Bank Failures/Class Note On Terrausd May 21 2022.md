---
cssclasses:
  - academia
title: Class Note On TerraUSD May 21 2022
tags:
  - bank_run
  - cryptocurrency
  - fixed_exchange_rates
  - luna
  - terrausd
aliases:
  - LUNA
  - TerraUSD Class Note
  - UST
key_concepts:
  - Arbitrage process
  - Bank run analogy
  - LUNA and UST swap
  - Speculative attacks
  - TerraUSD fixed exchange rates
---

# Class Note On TerraUSD May 21 2022

TerraUSD as a bank run or as a failure of fixed exchange rates.

Here is a description of TerraUSD from CoinDesk.com:

So,  how does it actually work?

It all has to do with arbitrage. This usually refers to the process of making small profits by finding discrepancies between asset prices on different exchanges. However,  in the case of LUNA and UST,  it works slightly differently. In the Terra ecosystem,  users can always swap the LUNA token for UST,  and vice versa,  at a guaranteed price of $1 - regardless of the market price of either token at the time. This is important to note because it means if demand for UST rises and its price rises above $1,  LUNA holders can bank a risk-free profit by swapping $1 of LUNA to create one UST token (which due to a rise in demand in this example,     is worth more than $1). During the swapping process,  a percentage of LUNA is burned (permanently removed from circulation) and the remainder is deposited into a community treasury. Funds in the treasury are then used to invest in applications and services that expand the utility of the Terra ecosystem. Burning a percentage of LUNA tokens reduces the number of overall tokens left in circulation,  making them more scarce and,  therefore,  more valuable. By minting more UST tokens,  it has the effect of diluting the existing tokens in circulation and bringing the overall price back down to its $1 level. Similarly,     if demand is low for UST and the price falls below $1,  UST holders can exchange their UST tokens at a ratio of 1:1 for LUNA - which is worth more because of their scarcity and so the user can bank another risk-free profit. (End of quote from CoinDesk.com)

What does this mean? We can see that this is a highly flawed design and is subject to runs or speculative attacks. Start with two analogies. The first is fixed exchange rates,  as the UK Pound in 1992 and the East Asian currencies in 1998. The second is a bank run.

## Terrausd As Fixed Exchange Rates

The fiat currencies the UK Pound in 1992 and the East Asian currencies in 1998 tried to keep fixed exchange rates to the dollar,  but failed. Each had speculative attacks on them (George Soros in the 1992 event),  but the attacks probably just speeded up an inevitable devaluation. The local governments and central banks tried to defend and maintain the exchange rate. They held US Dollar reserves to use to buy their currency to offset selling that would push down their exchange rate. This is like reserves serving as collateral held to back other crypto currencies (such as Tether),  or the one-day liquid assets held by a money market fund. Once they are gone,  an expected devaluation is probably self-fulfilling. As it turns out,  there were no reserves held at Luna or TerraUSD (see below,  about Luna Foundation Guard). The only collateral keeping the TerraUSD fixed at 1 USD was Luna,  which had no value unless it was useful as a cryptocurrency. If there was selling pressure on Terra,  they could be converted into $1 worth of Luna. But if everyone is expected to swap TerraUSD for Luna and the market value of Luna is believed to be less than all the TerraUSD,     the value of TerraUSD will drop below $1USD. The supply of Terra will drop but nothing prevents the value of all Luna from dropping to zero (or almost zero as it is on 5/19/2022). An analogy with UK Pound is useful. There is demand for UK pounds and the UK could say that you are free to swap pounds for dollars at fixed exchange rate. This works if all believe it works forever. But if many believe that it may not work in the future all will sell pounds to buy dollars,  and the exchange rate peg will break. That's what happened in 1992 and what happened to TerraUSD in 2022. We can see the exact same point a bit more precisely,  if we think of this as a bank run (in the next section).

## Terrausd As A Bank Run

The second analogy is tranching claims into short-term "safe" debt (TerraUSD) and equity (Luna). First think of Luna as equity in the value added of Terra and Luna together. The value of the combination is much higher if TerraUSD is a stable coin than if it is predicted to blow up. Call the value if it persists as stable:

VS. The value of TerraUSD coins at $1 each is T.

There is a lower value of value of Terra and Luna together if Terra is not a stable coin. An example of a coin that is not a stable coin is Bitcoin. Call the value if TerraUSD is not a stable coin (is Unstable),  VU<VS,  the value if a stable coin. For example,  VU=10<VS=30. Case A (no run) Suppose everyone expects TerraUSD to survive,  be worth $1 and be stable,     and T<VS the value if it persists as a stable coin. In this case the value of Luna (equity) is VS - T > 0. One could convert Terra to Luna at $1,  but would have no reason to do so once the value of Terra is $1. This is a self-fulfilling prophesy. For the numbers,     suppose that T=25. Then Terra USD is worth 25 and Luna is worth VS-T = 30-25 = 5. Case B (run). Suppose that the value of Terra satisfies T>VU. If this happens then the value of Luna today is zero because it would be VU-T<0,     apart from limited liability. For the numbers,     suppose that T=25,     then Terra is worth VU=10 and Luna is worth zero. In a run,     anyone who holds Terra would want to convert to Luna if the price valued a TerraUSD at $1,  and the stable coin Terra will not persist. Terra will drop in value to VU,  Luna will be worth zero and there will be run on the stable coin because it is unstable. Terra will become an unstable coin.

There are two self-fulling prophecies: Terra is Stable and Terra is Unstable.

There is no real collateral so the most the combined entity is worth in a panic is VU. There was a reserve of some Bitcoin in Luna Foundation Guard,  a separate organization,  which was to serve a similar function reserves foreign currency (US dollar) reserves that a government would use to defend its fixed exchange rate against a speculative attack. But it was not enough.

TerraUSD plus Luna could be worth VS=30 if everyone was sure it would be worth that amount. However,  the right to convert to equity at $1 is worthless if the value of equity is wiped out,  which occurs if everyone wants to convert. Thus,  the ability to convert TerraUSD to Luna does not provide stability or value if it is expected to melt down and have a run. In a run,  Terra plus Luna is worth only VU=10. To a first approximation,  this is what happened in May 2022. TerraUSD was a fake safe asset.

This is just a part of what was going on. The ability convert Terra to other stable coin crypto currencies provided another way to exit TerraUSD in a run (you can read about Anchor,  but that gets quite complicated).