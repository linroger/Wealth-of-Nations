---
tags:
  - '#cdx_itraxx_tranche_markets'
  - '#correlation_trades'
  - '#credit_volatility'
  - '#default_correlation'
  - '#equity_tranche'
  - '#gm_ford_downgrade'
  - '#hedge_fund_unwinding'
  - '#may_2005_credit_market_events'
  - '#mezzanine_tranche'
  - '#synthetic_cdos'
---
# 22.7 DEFAULT CORRELATION CASE STUDY: MAY 2O05  

During May 2005, credit markets witnessed an intriguing event which looked like a puzzle and created a significant amount of discussion as to the correctness of the credit markets' standard models. The events are worth reviewing briefly since they are a good example of the way cash derivatives markets influence each other in the newly developing credit markets.  

Essentially, the May 2005 events were triggered by General Motors and Ford being downgraded by rating agencies. These credits that had massive amounts of debt were investment grade and were downgraded to speculative grade, which meant that many institutional players would be prevented from holding them in their portfolios. The ensuing sales led to significant credit volatility in credit markets.  

The biggest volatility happened in CDX and iTraxx tranche markets, since several players anticipating these events had put long correlation trades in place. The following IFR report shows the series of events as they happened in May 2005.  

# EXAMPLE: MAY 2005 EVENTS  

Speculation about losses in the hedge fund industry sent a shudder through credit markets earlier this month. Fund managers were wrong-footed by going long on the equity piece of. synthetic CDOs, while funding that position by shorting the mezzanine tranche on the view. that spreads would move in the way predicted by their correlation assumptions..  

This positive carry trade was popular with banks and hedge funds because the trade made. money if spreads of the related pieces moved in a parallel fashion, as well as creating a hedge against large losses.  

The risk was exposure to unexpected default in the portfolio, but with default rates at historic lows, investors were happy to assume this risk.  

The ratings downgrade on GM and Ford, which are often included in these CDO struc-. tures because they are such large issuers of debt, made the banks change their outlook on default rates and prompted them to begin unwinding massive correlation books..  

While equity spreads jumped higher, those on the mezzanine tranches headed in the other direction, ensuring these trades significantly underperformed. As a result, investors suffered on both legs of the trade.  

Initially, the underperformance was most acutely felt in the United States, however, during the last couple of weeks the European market has been hit by hedge fund unwinding of iTraxx CDO tranche trades. It is estimated that between 20 and 30 hedge funds executed. correlation trades in Europe.  

"Selling is a result of the negative returns that these types of trades have generated in the US recently," said a European credit strategist..  

The iTraxx spreads should not be affected by the sell-off in correlation positions.. 'Fundamentally, a risk re-distribution between different tranches, as reflected by a change in. correlation, should have a very limited effect on the underlying market," said a credit strate-. gist. However, from a sentimental point of view the impact was much more significant and the rush to unwind the same trade caused massive volatility in the DJ iTraxx crossover index. last week.  

The index ballooned to. $475\mathrm{bp}$ in 5 years from 330 bp the previous week.  

However, hedge funds putting on large shorts in a widening market coupled with a rally in JS treasuries caused a violent snap back in the index to 380 bp towards the end of the week.  

Attention also turned last week to the banking sector and the size of potential losses. Most of the fall-out will be felt in London and the United States where the majority of inter national banks keep their correlation books, whereas Asia is less exposed.  

That is partly because synthetic tranching of purely Asian credit has not really taken off. Facilitating the interest in structured credit products in Europe and the United States has been the development and liquidity of the credit default swap indices; they have given transparency to implied correlation in those markets. Not so in Asia, where the regional indices have not proved hugely popular, there has been even less take-up of index tranching.  

The end of June is critical for the high-yield market because most funds have quarterly liquidity, and there is the threat of huge redemptions. Many are unwinding positions in expectation that clients will redeem their cash.  

We can now study this case in more detail. According to the series of events, the status quo before the volatility was as follows..  

Several hedge funds and bank proprietary trading desks were long correlation, meaning that they had sold protection on the equity tranche by a notional amount. $N^{E}$ and bought protection on the mezzanine tranche by a notional amount $N^{M}$ These two notional amounts were related to each other according to  

$$
N_{t}^{M}=\setminus_{t}N^{E}
$$  

where $\lambda_{t}$ is the hedge ratio selected so that the sensitivity of the portfolio to movements in the underlying index, or, in average default probability $P_{t}$ is approximately zero. Letting $V^{E}$ and $V^{M}$ represent the value of the. $\$1$ invested in the equity and mezzanine tranches, respectively, we can. write the value  

$$
\frac{\partial}{{\partial}p_{t}}\left[N^{E}V_{t}^{E}-{\lambda}N^{E}V_{t}^{M}\right]=0
$$  

These positions were taken with the view that the compound default correlation coefficient denoted by $\rho_{t}$ would go up. Since we had  

$$
\frac{\partial}{\partial\rho_{t}}V_{t}^{E}>0
$$  

and  

$$
\frac{\partial}{\partial\rho_{t}}V_{t}^{M}\cong0
$$  

The position would benefit as correlation increased,  

$$
\frac{\partial}{{\partial\rho_{t}}}V_{t}^{E}-\frac{\partial}{{\partial\rho_{t}}}V_{t}^{M}>0
$$  

in fact, as the reading above indicates, with the GM and Ford downgrades the reverse happened. One possible explanation of the May 2005 events is as follows.12 As GM and Ford were downgraded, the equity spreads increased and $V_{t}^{E}$ decreased, which led to a sudden collapse of the default correlation. Meanwhile, the mezzanine spreads decreased and $V_{t}^{M}$ increased. This meant severe mark-to-market losses of the long correlation trades  

$$
\frac{\partial}{\partial\rho_{t}}V_{t}^{E}-\frac{\partial}{\partial\rho_{t}}V_{t}^{M}<0
$$  

since both legs of the trades started to have severe mark-to-market losses.  

The dynamics of the tranche spreads observed during May 2005 contradicted what the theoreti-. cal models implied. The observed real-world relationships had the opposite sign of what the market standard models would imply. What was the reason behind this puzzle?.  

One explanation is, of course, the models themselves. If the market convention used the "wrong" model then it is natural that sometimes the real-world development would contradict the model predictions. This is possible, but we know of no satisfactory new theoretical model that would explain the observed discrepancy at that time.  

There is, on the other hand, a plausible structural explanation of the puzzle and it relates to the. cash CDO market. Over the years, starting from the mid-1990s, banks had sold mezzanine tranches of cash CDOs (the banks were paying mezzanine spreads). Some of these positions could have been unhedged. As GM and Ford were downgraded, and as these names were heavily used in cash CDOs, the banks who were short the mezzanine tranche tried to cover these positions in the index. market. This means that they had to sell protection on the mezzanine index tranche.'3 It is plausible that this dynamic created a downward spiral where the attempt to hedge the cash mezzanine posi-. tion via selling mezzanine protection in the index market resulted in even further mezzanine spread. tightening.  

At the same time, since the correlation trade had gone in the opposite direction, hedge funds tried to close their position in the equity tranche. They were selling equity protection before, but closing the position meant buying equity protection and such a rush by institutions would create exactly the type of dynamic observed at that time. The equity spreads increased and the mezzanine spreads declined and, at the end, correlation declined. The downgrade by GM and Ford had created the opposite effect.  
