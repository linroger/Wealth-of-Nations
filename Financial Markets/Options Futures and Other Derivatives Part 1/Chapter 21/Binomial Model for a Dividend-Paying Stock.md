---
tags:
  - binomial_model
  - dividend_paying_stock
  - ex_dividend_date
  - option_pricing
  - stock_options
aliases:
  - BOPM
  - Binomial Option Pricing
  - Dividend Valuation
key_concepts:
  - American option valuation
  - Binomial model
  - Dividend-paying stock
  - Known dividend yield
  - Known dollar dividend
---

# 21.3  BINOMIAL MODEL FOR A DIVIDEND-PAYING STOCK  

We now move on to the more tricky issue of how the binomial model can be used for a dividend-paying stock. As in Chapter 15, the word "dividend" will, for the purposes of our discussion, be used to refer to the reduction in the stock price on the ex-dividend date as a result of the dividend.  

# Known Dividend Yield  

For long-life stock options, it is sometimes assumed for convenience that there is a known continuous dividend yield of. $q$ on the stock. The options can then be valued in. the same way as options on a stock index..  

For more accuracy, known dividend yields can be assumed to be paid discretely.. Suppose that there is a single dividend, and the dividend yield (i.e., the dividend as a percentage of the stock price) is known. The parameters $u,d$ , and $p$ can be calculated as though no dividends are expected. If the time $i\Delta t$ is prior to the stock going exdividend, the nodes on the tree correspond to stock prices  

$$
S_{0}u^{j}d^{i-j},\quad j=0,1,\dots,i
$$  

If the time i $\Delta t$ is after the stock goes ex-dividend, the nodes correspond to stock prices  

$$
S_{0}(1-\delta)u^{j}d^{i-j},j=0,1,...,i
$$  

where $\delta$ is the dividend yield. The tree has the form shown in Figure 21.7. Several known dividend yields during the life of an option can be dealt with similarly. If $\delta_{i}$ is the total dividend yield associated with all ex-dividend dates between time zero and time i $\Delta t$ , the nodes at time $i~\Delta t$ correspond to stock prices  

$$
S_{0}(1-\delta_{i})u^{j}d^{i-j}
$$  

![](da4ed0ecb3234ceeddb182f6c1b16e32ccfb243087ca55f8cb0cc1bb4c1d5dc2.jpg)  
Figure 21.7 Tree when stock pays a known dividend yield at one particular time.  

# Known Dollar Dividend  

In some situations, particularly when the life of the option is short, the most realistic assumption is that the dollar amount of the dividend rather than the dividend yield is known in advance. If the volatility of the stock, $\sigma$ , is assumed constant, the tree then takes the form shown in Figure 21.8. It does not recombine, which means that the number of nodes that have to be evaluated is liable to become very large. Suppose that there is only one dividend, that the ex-dividend date, $\tau$ , is between $k\Delta t$ and $(k+1)\Delta t$ and that the dollar amount of the dividend is $D$ . When $i\leq k$ , the nodes on the tree at time $i\Delta t$ correspond to stock prices  

$$
S_{0}u^{j}d^{i-j},\quad j=0,1,2,\ldots,i
$$  

as before. When $i=k+1$ , the nodes on the tree correspond to stock prices  

$$
S_{0}u^{j}d^{i-j}-D,~j=0,1,2,~\ldots,i
$$  

When $i=k+2$ , so that the nodes on the tree correspond to stock prices  

$$
(S_{0}u^{j}d^{i-1-j}-D)u\quad\mathrm{and}\quad(S_{0}u^{j}d^{i-1-j}-D)d
$$  

for $j=0,1,2,\dots,i-1$ , there are $2i$ rather than $i+1$ nodes. When $i=k+m$ there are $m(k+2)$ rather than $k+m+1$ nodes. The number of nodes expands even. faster when there are several ex-dividend dates during the option's life.  

![](09b607fc933bf8fab957aa88f3d348e8dffcc4e48e0f71e1c205c27cf5d46582.jpg)  
Figure 21.8 Tree when dollar amount of dividend is assumed known and volatility is assumed constant.  

Section 15.12 explained that European options on dividend-paying stocks are valued by assuming that the stock price has two components: a part that is uncertain and a part that is the present value of dividends paid during the life of the option. It outlined a number of reasons why practitioners find this a sensible assumption. American options clearly have to be valued using the same model as European options. (Otherwise the prices of American options that should never be exercised early will not be the same as the prices of European options.) American options on stocks paying known dividends are therefore in practice valued using the approach in Section 15.12. As it happens, this solves the node-proliferation problem in Figure 21.8.  

Suppose that there is only one ex-dividend date, $\tau$ , during the life of the option and that $k\Delta t\leq\tau\leq(k+1)\Delta t.$ The value $S^{*}$ of the uncertain component (i.e., the component not used to pay dividends) at time $i~\Delta t$ is given by  

$$
S^{*}=S\quad{\mathrm{when~}}i\Delta t>\tau
$$  

and  

$$
S^{*}=S-D e^{-r(\tau-i\Delta t)}\mathrm{when}i\Delta t\leq\tau
$$  

where $D$ is the dividend. Define $\sigma^{*}$ as the volatility of $S^{*}$ The parameters $p,u$ , and $d$ can be calculated from equations (21.4) to (21.7) with $\sigma$ replaced by $\sigma^{*}$ and a tree can be constructed in the usual way to model $S^{*}$ .6 By adding to the stock price at each node,. the present value of future dividends (if any), the tree can be converted into another tree that models $S$ . Suppose that $S_{0}^{*}$ is the value of $S^{*}$ at time zero. At time $i~\Delta t$ , the nodes on this tree correspond to the stock prices  

$$
S_{0}^{*}u^{j}d^{i-j}+D e^{-r(\tau-i\Delta t)},~j=0,1,~.~..~,i
$$  

when $i\Delta t<\tau$ and  

$$
S_{0}^{*}u^{j}d^{i-j},~j=0,1,~.~.~.~,i
$$  

when i $\Delta t>\tau$ This approach, which leads to a situation where the tree recombines so that there are $i+1$ nodes at time $i~\Delta t$ can be generalized in a straightforward way to. deal with the situation where there are several dividends..  

# Example 21.5  

Consider a 5-month American put option on a stock that is expected to pay a single dividend of $\$2.06$ during the life of the option. The initial stock price is $\$52$ the strike price is $\$50$ , the risk-free interest rate is $10\%$ per annum, the volatility is $40\%$ per annum, and the ex-dividend date is in $3{\frac{1}{2}}$ months.  

We first construct a tree to model $S^{*}$ , the stock price less the present value of future dividends during the life of the option. At time zero, the present value of the dividend is  

$$
2.06\times e^{-0.2917\times0.1}=2.00
$$  

The initial value of $S^{*}$ is therefore 50.00. If we assume that the. $40\%$ per annum volatility refers to $S^{*}$ , then Figure 21.3 provides a binomial tree for. $S^{*}$ . (This is because $S^{*}$ has the same initial value and volatility as the stock price that. Figure 21.3 was based upon.) Adding the present value of the dividend at each node leads to Figure 21.9, which is a binomial model for S. The probabilities at each node are, as in Figure 21.3, 0.5073 for an up movement and 0.4927 for a down movement. Working back through the tree in the usual way gives the option price as $\$4.44$ . (Using 50 time steps, DerivaGem gives a value for the. option of 4.208; using 100 steps it gives 4.214.)  

# Control Variate Technique  

A technique known as the control variate technique can improve the accuracy of the pricing of an American option.' This involves using the same tree to calculate the value of both the American option,. $f_{A}$ , and the corresponding European option, $f_{E}$ .Thed Black-Scholes-Merton price of the European option, $f_{\mathrm{BSM}}$ , is also calculated. The. error when the tree is used to price the European option, $f_{\mathrm{BSM}}-f_{E}$ is assumed equal to the error when the tree is used to price the American option. This gives the estimate of the price of the American option as.  

$$
f_{A}+(f_{\mathrm{BSM}}-f_{E})
$$  

To illustrate this approach, Figure 21.10 values the option in Figure 21.3 on the assumption that it is European. The price obtained, $f_{E}$ , is $\$4.32$ . From the BlackScholes-Merton formula, the true European price of the option, $f_{\mathrm{BSM}}$ , is $\$4.08$ . The  

At each node:. Upper value $=$ Underlying Asset Price Lower value $=$ Option Price Shading indicates where option is exercised  

![](396f2c363553d50cad21154a2b9d208b74baa80cf6f7c968e39f6856a91ae3d1.jpg)  
Figure 21.9 Tree produced by DerivaGem for Example 21.5.  

estimate of the American price in Figure 21.3, $f_{A}$ , is $\$4.49$ . The control variate estimate.   
of the American price, therefore, is.  

$$
4.49+(4.08-4.32)=4.25
$$  

A good estimate of the American price, calculated using 100 steps, is 4.278. The control variate approach does, therefore, produce a considerable improvement over the basic tree estimate of 4.49 in this case.  

The control variate technique in effect involves using the tree to calculate the. difference between the European and the American price rather than the American. price itself. We give a further application of the control variate technique when we discuss Monte Carlo simulation later in the chapter.  

Figure 21.10 Tree, as produced by DerivaGem, for European version of option in Figure 21.3. At each node, the upper number is the stock price, and the lower number is the option price.  

At each node: Upper value $=$ Underlying Asset Price Lower value $=$ Option Price Shading indicates where option is exercised  

![](674e0115bd39999b07f2c2daa642fc819280d610ba6b5d59b4e7cb254b30f141.jpg)  
