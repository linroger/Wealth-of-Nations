---
tags:
  - '#constant_maturity_swaps_cms'
  - '#fixed_income_security_pricing'
  - '#forward_libor_model'
  - '#girsanov_transformations'
  - '#measure_change_technology'
  - '#ois_curve'
  - '#swap_derivatives'
  - '#swap_instruments'
  - '#term_structure_modeling'
---
# 14.1 INTRODUCTION  

This chapter extends the discussion of swap-type instruments and outlines a simple framework for fixed-income security pricing. Term structure modeling is treated within this framework. The chapter also introduces the recent models that are becoming a benchmark in this sector.  

Until the late 1990s, short-rate modeling was the most common approach in pricing and riskmanaging fixed-income securities. The publication in 1992 of the Heath-Jarrow-Merton (HJM) approach enabled arbitrage-free modeling of multifactor-driven term structure models, but markets continued to use short-rate modeling. A few years ago the situation changed. The Forward LIBOR or Brace-Gatarek-Musiela (BGM) Model published in 1997 became the market standard for pricing and risk management.  

During the GFC, the LIBOR rate rose significantly and diverged from the overnight indexed. swap (OIS) rate raising questions about whether LIBOR is an appropriate riskless discount. In. Chapter 24, we will discuss recent models and market developments such as the use of OIS curve. as a risk-free curve for discounting. The use of the OIS curve implies that more than one zero curve must be modeled for the purpose of pricing derivatives. The LIBOR curve is used to determine. payoffs and the OiS zero curve is used for discounting. This chapter will discuss the Forward LIBOR Model and we will deal with more complex and recent issues such as approaches that. simultaneously or separately model the LIBOR and the OIS curve in Chapter 24..  

This chapter will approach the issues from a practical point of view using swap markets and swap derivatives as a background. We are interested in providing a framework for analyzing the mechanics of swaps and swap derivatives, for decomposing them into simpler instruments, and for constructing synthetics. Recent models of fixed-income modeling can then be built on this foundation very naturally.  

It is worth reviewing the basic principles of swap engineering laid out in Chapter 4. First of all, swaps are almost always designed such that their value at initiation is zero. This is a characteristic of modern swap-type "spread instruments," and there is no surprise here. Second, what makes the value of the swap equal to zero is a spread or an interest rate that is chosen with the purpose that the initial value of the swap vanishes. Third, swaps encompass more than one settlement date. This. means that whatever the value of the swap rate or swap spread, these will in the end be some sort. of "average of shorter term floating rates or spreads.' This not only imposes simple arbitrage conditions on relevant market rates but also provides an opportunity to trade the volatility associated with such averages through the use of options on swaps. Since swaps are very liquid, they form an. excellent underlying for swaptions. Swaptions, in turn, are related to interest rate volatilities for the underlying subperiods, which will relate to cap/floor volatilities. This structure is conducive to.  

![](images/7d81e4d7f074049638074f247b4cf292440bc92dbfc7667726fb1adb5549616c.jpg)  

# FIGURE 14.1  

Three-period forward swap.  

designing and understanding more complex swap products such as constant maturity swaps (CMS).   
The CMS is used as an example for showing the advantages of the Forward LIBOR Model.  

Finally, the chapter will further use the developed framework to illustrate the advantages of measure change technology. Switching between various. $T.$ forward measures, we show how convex-. ity effects can be calculated.  

Most of the discussion will center on a three-period swap first, and then generalize the results.. We begin with this simple example, because with a small number of cash flows the analysis becomes. more manageable and easier to understand. Next, we lay out a somewhat more technical framework for engineering fixed-income instruments. Eventually, this is developed into the Forward LIBOR Model. Within our framework, measure changes using Girsanov-type transformations emerge as fun-. damental tools of financial engineering. The chapter discusses how measures can be changed sequentially during a numerical pricing exercise as was done in the simulation of the Forward LIBOR. Model. These tools are then applied to CMS, which are difficult to price with traditional models..  
