# CASH FLOW ENGINEERING IN FOREIGN EXCHANGE MARKETS  

# 6  

# HAPTER OUTLINE  

6.1 Introduction .. 176   
6.2 Currency Forwards . 178   
6.2.1 Engineering the Currency Forward. 180   
6.2.2 Which Synthetic? . . 180   
6.2.2.1 A money market synthetic . .180   
6.2.2.2 A synthetic with T-bills . .182   
6.2.2.3 Which synthetic should one use? . .182   
6.2.2.4 Credit risk .. .183   
6.3 Synthetics and Pricing . .. 183   
6.4 A Contractual Equation ... . 184   
6.5 Applications ... . 185   
6.5.1 Application 1: A Withholding Tax Problem . 185   
6.5.2 Application 2: Creating Synthetic Loans . 187   
6.5.3 Application 3: Capital Controls . . 189   
6.5.4 Application 4: “Cross” Currencies.. 189   
6.6 Conventions for FX Forward and Futures . 191   
6.6.1 Quoting Conventions for FX Forward .. 191   
6.6.2 FX Forward Versus FX Futures. 194   
6.7 Swap Engineering in FX Markets.. . 194   
6.7.1 FX Swaps.. 194   
6.7.1.1 Advantages .. .195   
6.7.1.2 Uses of FX swaps .. .196   
6.7.1.3 Quotation conventions . .197   
6.8 Currency Swaps Versus FX Swaps... 198   
6.8.1 Currency Swaps.. 198   
6.8.2 Differences Between Currency Swaps and FX Swaps.. . 200   
6.8.3 Another Difference .. 202   
6.8.4 Uses of Currency Swaps .. . 202   
6.8.5 Relative Size and Liquidity of FX Swap and Currency Swap Markets.. 202   
6.8.6 The Effect of the GFC on the FX Market, Margins, and Clearing ... . 203   
6.9 Mechanics of Swapping New Issues. 204   
6.9.1 Interest Rate and Currency Swap Example. 204   
6.10 Conclusions... .. 206   
Suggested Reading .. .. 207   
Exercises .. . 207  

# 6.1 INTRODUCTION  

Forwards and futures contracts are ideal for creating synthetic instruments for many reasons. Forwards and futures are, in general, linear permitting static replication. They are often very liquid and, in the case of currency forwards, have homogeneous underlying. Many technical complications are automatically eliminated by the homogeneity of a currency. Consider the following interpretation.  

Financial instruments are denominated in different currencies. A market practitioner who needs to perform a required transaction in US dollars (USD) normally uses instruments denoted in USD. In the case of the dollar, this works out fine since there exists a broad range of liquid markets. Market professionals can offer all types of services to their customers using these. On the other hand, there is a relatively small number of, say, liquid Swiss Franc (CHF) denoted instruments. Would the Swiss market professionals be deprived of providing the same services to their clients? It turns out that liquid foreign exchange (FX) forward contracts in USD/CHF can, in principle, make USD-denominated instruments available to CHF-based clients as well.  

Instead of performing an operation in CHF, one can first buy and sell USD at $t_{0}$ and then use a USD-denominated instrument to perform any required operation. Liquid FX forwards permit future USD cash flows to be reconverted into CHF as of time $t_{0}$ . Thus, entry into and exit from a different currency is fixed at the initiation of a contract. As long as liquid forward contracts exist, market professionals can use USD-denominated instruments in order to perform operations in any other currency without taking FX risk.  

As an illustration, we provide the following example where a synthetic zero coupon bond is cre ated using an FX forward and the bond markets of another country.  

# EXAMPLE  

Suppose we want to buy, at time $t_{0}.$ , a USD-denominated default-free discount bond, with maturity at $t_{1}$ and current price $B(t_{0},\ t_{1})$ . We can do this synthetically using bonds denominated in any other currency, as long as an FX forward exists and the relevant credit risks are the same.  

First, we buy an appropriate number of, say, euro-denominated bonds with the same maturity, default risk, and the price $B(t_{0},\ t_{1})^{\mathrm{EUR}}$ . This requires buying euros against dollars in the spot market at an exchange rate $e_{t_{0}}$ . Then, using a forward contract on euro, we sell forward the euros that will be received on December 31, 2015, when the bond matures. The forward exchange rate is $\boldsymbol{F}_{t_{0}}$ .  

The final outcome is that we pay USD now and receive a known amount of USD at maturity. This should generate the same cash flows as a USD-denominated bond under no-arbitrage conditions. This operation is shown in Figure 6.1.  

![](1166b1b36236222d395b6d1bfa3e968d73dfdfd74055192a0d1ea2bfa2303555.jpg)  

# FIGURE 6.1  

A synthetic USD bond created using an FX forward and a EUR bond.  

In principle, such steps can be duplicated for any (linear) underlying asset, and the ability to execute forward purchases or sales plays a crucial role here.  

Next we discuss the engineering of one of the simplest and most liquid contracts; namely, the currency forward.  

# 6.2 CURRENCY FORWARDS  

Currency forwards are very liquid instruments. Although they are elementary, they are used in a broad spectrum of financial engineering problems.  

Consider the EUR/USD exchange rate.1 The cash flows implied by a forward purchase of USD100 against euros are represented in Figure 6.2a. At time $t_{0}$ , a contract is written for the forward purchase (sale) of USD100 against $100/F_{t_{0}}$ euros. The settlement—that is to say, the actual exchange of currencies—will take place at time $t_{1}$ . The forward exchange rate is $\boldsymbol{F}_{t_{0}}$ . At time $t_{0}$ , nothing changes hands.  

Obviously, the forward exchange rate $\boldsymbol{F}_{t_{0}}$ should be chosen at $t_{0}$ so that the two parties are satisfied with the future settlement and thus do not ask for any immediate compensating payment. This means that the time $t_{0}$ value of a forward contract concluded at time $t_{0}$ is zero. It may, however, become positive or negative as time passes and markets move.  

In this section, we discuss the structure of this instrument. How do we create a synthetic for an instrument such as this one? How do we decompose a forward contract? Once this is understood, we consider applications of our methodology to hedging, pricing, and risk management.  

![](382ab49eb10e6426abe1c2bb6f3ca95f4f661375aa7a78eef65ca362588ceaa8.jpg)  

# FIGURE 6.2  

$\operatorname{\rho}({\mathrm{a-c}})$ A currency forward. $(\mathrm{d-f})$ A money market synthetic.  

A general method of engineering a (currency) forward—or, for that matter, any linear instrument—is as follows:  

1. Begin with the cash flow diagram as shown in Figure 6.2a.   
2. Detach and carry the (two) rectangles representing the cash flows into Figure 6.2b and c.   
3. Then, add and subtract new cash flows at carefully chosen dates so as to convert the detached cash flows into meaningful financial contracts that players will be willing to buy and sell.   
4. As you do this, make sure that when the diagrams are added vertically, the newly added cash flows cancel out and the original cash flows are recovered.  

This procedure will become clearer as it is applied to progressively more complicated instruments. Now we consider the details.  

![](8e814e12e80c560a342f005b4ef0dcd1955002ca49e5ba2ed17842358f736a1a.jpg)  

# FIGURE 6.2  

# 6.2.1 ENGINEERING THE CURRENCY FORWARD  

We apply this methodology to engineering a currency forward. Our objective is to obtain a contractual equation at the end and, in this way, express the original contract as a sum of two or more elementary contracts. The steps are discussed in detail.  

Begin with cash flows as shown in Figure 6.2a. If we detach the two cash flows, we get Figure 6.2b and c. At this point, nobody would like to buy cash flows in Figure 6.2b, whereas nobody would sell the cash flows in Figure 6.2c. Indeed, why pay something without receiving anything in return? So at this point, Figure 6.2b and c cannot represent tradeable financial instruments.  

However, we can convert them into tradeable contracts by inserting new cash flows, as in step 3 of the methodology. In Figure 6.2b, we add a corresponding cash inflow. In Figure 6.2c, we add a cash outflow. By adjusting the size and the timing of these new cash flows, we can turn the transactions in Figure 6.2b and c into meaningful financial contracts.  

We keep this as simple as possible. For Figure 6.2b, add a positive cash flow, preferably at time $t_{0}$ .2 This is shown in Figure 6.2d. Note that we denote the size of the newly added cash flow by $C_{t_{0}}^{\mathrm{EUR}}$ .  

In Figure 6.2c, add a negative cash flow at time $t_{0}$ , to obtain Figure 6.2e. Let this cash flow be denoted by $C_{t_{0}}^{\mathrm{USD}}$ . The size of $C_{t_{0}}^{\mathrm{USD}}$ is not known at this point, except that it has to be in USD.  

The vertical addition of Figure 6.2d and e should replicate what we started with in Figure 6.2a. At this point, this will not be the case, since $C_{t_{0}}^{\mathrm{USD}}$ and $\bar{C}_{t_{0}}^{\mathrm{EUR}}$ do not cancel out at time $t_{0}$ as they are denominated in different currencies. But, there is an easy solution to this. The “extra” time $t_{0}$ cash flows can be eliminated by considering a third component for the synthetic. Consider Figure 6.2f where one exchanges $C_{t_{0}}^{\mathrm{USD}}$ against $C_{t_{0}}^{\mathrm{EUR}}$ at time $t_{0}$ . After the addition of this component, a vertical sum of the cash flows in Figure $6.2\mathrm{d-f}$ gives a cash flow pattern identical to the ones shown in Figure 6.2a. If the credit risks are the same, we have succeeded in replicating the forward contract with a synthetic.  

# 6.2.2 WHICH SYNTHETIC?  

Yet, it is still not clear what the synthetic in Figure $6.2\mathrm{d-f}$ consists of. True, by adding the cash flows in these figures, we recover the original instrument shown in Figure 6.2a, but what kind of contracts do these figures represent? The answer depends on how the synthetic instruments shown in Figure 6.2d f are interpreted.  

This can be done in many different ways. We consider two major cases. The first is a deposit loan interpretation. The second involves Treasury bills.  

# 6.2.2.1 A money market synthetic  

The first synthetic is obtained using money market instruments. To do this, we need a brief review of money market instruments. The following lists some important money market instruments, along with the corresponding quote, registration, settlement, and other conventions that will have cash flow patterns similar to Figure 6.2d and e. The list is not comprehensive.  

# EXAMPLE  

Deposits/loans. These mature in less than 1 year. They are denominated in domestic and Eurocurrency units. Settlement is on the same day for domestic deposits and in 2 business days for Eurocurrency deposits. There is no registration process involved and they are not negotiable.  

Certificates of deposit $(C D)$ . Generally these mature in up to 1 year. They pay a coupon and are sometimes sold in discount form. They are quoted on a yield basis, and exist both in domestic and Eurocurrency forms. Settlement is on the same day for domestic deposits and in 2 working days for Eurocurrency deposits. They are usually bearer securities and are negotiable.  

Treasury bills. These are issued at 13-, 26-, and 52-week maturities. In France, they can also mature in 4 7 weeks; in the United Kingdom, also in 13 weeks. They are sold on a discount basis (United States, United Kingdom). In other countries, they are quoted on a yield basis. Issued in domestic currency, they are bearer securities and are negotiable.  

Commercial paper $(C P)$ . Their maturities are 1 270 days. They are very short-term securities, issued on a discount basis. The settlement is on the same day; they are bearer securities and are negotiable.  

Euro-CP. The maturities range from 2 to 365 days but most have 30- or 180-day maturities. Issued on a discount basis, they are quoted on a yield basis. They can be issued in any Eurocurrency, but in general they are in Eurodollars. Settlement is in 2 business days, and they are negotiable.  

How can we use these money market instruments to interpret the synthetic for the FX forward as shown in Figure 6.2?  

One money market interpretation is as follows. The cash flow shown in Figure 6.2e involves making a payment of $C_{t_{0}}^{\mathrm{USD}}$ at time , to receive USD100 at a later date, $t_{1}$ . Clearly, an ipnrtesrebnat  lduee osif UwSillD1g0e0n, rwathe e athcte  itshcios cnta fh ftlorw apna ebre  bTthaiene,  teh $C_{t_{0}}^{\mathrm{USD}}$ thwei  ble tahnet Eurodeposit rate.  

$$
C_{t_{0}}^{\mathrm{USD}}=\frac{100}{1+L_{t_{0}}^{\mathrm{USD}}((t_{1}-t_{0})/360)}
$$  

Note that we are using an ACT/360-day basis for the deposit rate $L_{t_{0}}^{\mathrm{USD}}$ , since the cash flow is in Eurodollars. Also, we are using money market conventions for the interest rate.3 Given the observed value of $L_{t_{0}}^{\mathrm{USD}}$ , we can numerically determine the $C_{t_{0}}^{\mathrm{USD}}$ by using this equation.  

How about the cash flows shown in Figure 6.2d? This can be interpreted as a loan obtained in interbank markets. One receives $C_{t_{0}}^{\mathrm{EUR}}$ at time $t_{0}$ and makes a euro-denominated payment of $100/F_{t_{0}}$ at the later date $t_{1}$ . The value of this cash flow will be given by  

$$
C_{t_{0}}^{\mathrm{EUR}}=\frac{100/F_{t_{0}}}{1+L_{t_{0}}^{\mathrm{EUR}}((t_{1}-t_{0})/360)}
$$  

where $C_{t_{0}}^{\mathrm{EUR}}$ is the relevant interest rate in euros.  

Finally, we need to interpret the last diagram shown in Figure 6.2f. These cash flows represent an exchange of $C_{t_{0}}^{\mathrm{USD}}$ against $C_{t_{0}}^{\mathrm{EUR}}$ at time $t_{0}$ . Thus, what we have here is a spot purchase of dollars at the rate $\boldsymbol{e}_{t_{0}}$ .  

The synthetic is now fully described:  

Take an interbank loan in euros (Figure 6.2d).   
Using these euro funds, buy spot dollars (Figure 6.2f).   
Deposit these dollars in the interbank market (Figure 6.2f).  

This portfolio would exactly replicate the currency forward, since by adding the cash flows in Figure 6.2d f, we recover exactly the cash flows generated by a currency forward as shown in Figure 6.2a.  

# 6.2.2.2 A synthetic with T-bills  

We can also create a synthetic currency forward using Treasury-bill markets. In fact, let $B$ $\left(t_{0},\ t_{1}\right)^{\mathrm{USD}}$ be the time $t_{0}$ price of a default-free discount bond that pays USD100 at time $t_{1}$ . Similarly, let $B(t_{0},\ t_{1})^{\mathrm{EUR}}$ be the time $t_{0}$ price of a default-free discount bond that pays EUR100 at time $t_{1.}$ Then the cash flows shown in Figure 6.2d f can be reinterpreted so as to represent the following transactions:4  

Figure 6.2d is a short position in $B(t_{0},t_{1})^{\mathrm{EUR}}$ where $1/F_{t_{0}}$ units of this security is borrowed and sold at the going market price to generate $B(t_{0},t_{1})^{\mathrm{EUR}}/F_{t_{0}}$ euros. In Figure 6.2f, these euros are exchanged into dollars at the going exchange rate. • In Figure 6.2e, the dollars are used to buy one dollar-denominated bond $\bar{B(t_{0},t_{1})}^{\mathrm{USD}}$ .  

At time $t_{1}$ these operations would amount to exchanging EUR $100/F_{t_{0}}$ against USD100, given that the corresponding bonds mature at par.  

# 6.2.2.3 Which synthetic should one use?  

If synthetics for an instrument can be created in many ways, which one should a financial engineer use in hedging, risk management, and pricing? We briefly comment on this important question.  

As a rule, a market practitioner would select the synthetic instrument that is most desirable according to the following attributes: (1) The one that costs the least. (2) The one that is most liquid, which, ceteris paribus, will, in general, be the one that costs the least. (3) The one that is most convenient for regulatory purposes. (4) The one that is most appropriate given balance sheet considerations. Of course, the final decision will have to be a compromise and will depend on the particular needs of the market practitioner.  

# 6.2.2.4 Credit risk  

Section 6.2.2.1 displays a list of instruments that have similar cash flow patterns to loans and T-bills. The assumption of no-credit risk is a major reason why we could alternate between loans and T-bills in Sections 6.2.2.1 and 6.2.2.2. If credit risk were taken into account, the cash flows would be significantly different. In particular, for loans we would have to consider a diagram as shown in Figure 6.1, whereas T-bills would have no default risks.5  

# 6.3 SYNTHETICS AND PRICING  

A major use of synthetic assets is in pricing. Everything else being the same, a replicating portfolio must have the same price as the original instrument. Thus, adding up the values of the constituent assets, we can get the cost of forming a replicating portfolio. This will give the price of the original instrument once the market practitioner adds a proper margin.  

In the present context, pricing means obtaining the unknowns in the currency forward, which is the forward exchange rate, $\boldsymbol{F}_{t_{0}}$ , introduced earlier. We would like to determine a set of pricing equations which result in closed-form pricing formulas. Let us see how this can be done.  

Begin with Figure 6.2f. This figure implies that the time $t_{0}$ market values of $C_{t_{0}}^{\mathrm{USD}}$ and $C_{t_{0}}^{\mathrm{EUR}}$ should be the same. Otherwise, one party will not be willing to go through with the deal. This implies  

$$
C_{t_{0}}^{\mathrm{USD}}=C_{t_{0}}^{\mathrm{EUR}}e_{t_{0}}
$$  

where $\boldsymbol{e}_{t_{0}}$ is the spot EUR/USD exchange rate. Replacing from Eqs. (6.1) and (6.2):  

$$
F_{t_{0}}\left[\frac{100}{1+L_{t_{0}}^{\mathrm{USD}}((t_{1}-t_{0})/360)}\right]=\left[\frac{100}{1+L_{t_{0}}^{\mathrm{EUR}}((t_{1}-t_{0})/360)}\right]e_{t_{0}}
$$  

Solving for the forward exchange rate $F_{t0}$ ,  

$$
F_{t_{0}}=e_{t_{0}}\left[\frac{1+L_{t_{0}}^{\mathrm{USD}}((t_{1}-t_{0})/360)}{1+L_{t_{0}}^{\mathrm{EUR}}((t_{1}-t_{0})/360)}\right]
$$  

This is the well-known covered interest rate parity (CIRP) equation. Note that it expresses the “unknown” $\boldsymbol{F}_{t_{0}}$ as a function of variables that can be observed at time $t_{0}$ . Hence, using the market quotes, $\boldsymbol{F}_{t_{0}}$ can be numerically calculated at time $t_{0}$ and does not require any forecasting effort.6  

The second synthetic using T-bills gives an alternative pricing equation. Since the values evaluated at the current exchange rate, $\boldsymbol{e}_{t},$ of the two bond positions needs to be the same, we have  

$$
\boldsymbol{F}_{t_{0}}\boldsymbol{B}(t_{0},t_{1})^{\mathrm{USD}}=\boldsymbol{e}_{t_{0}}\boldsymbol{B}(t_{0},t_{1})^{\mathrm{EUR}}
$$  

Hence, the $\boldsymbol{F}_{t_{0}}$ priced off the T-bill markets will be given by  

$$
F_{t_{0}}=e_{t_{0}}\frac{B(t_{0},t_{1})^{\mathrm{EUR}}}{B(t_{0},t_{1})^{\mathrm{USD}}}
$$  

If the bond markets in the two currencies are as liquid as the corresponding deposits and loans, and if there is no credit risk, the $\boldsymbol{F}_{t_{0}}$ obtained from this synthetic will be very close to the $\boldsymbol{F}_{t_{0}}$ obtained from deposits.7  

# 6.4 A CONTRACTUAL EQUATION  

In this section, we will obtain a contractual equation for a currency forward. In the next section, we will show several applications. We have just created a synthetic for a currency forward. The basic idea was that a portfolio consisting of the following instruments:  

Loan in EUR; Deposit of USD; spot purchase of USD against EUR would generate the same cash flows, at the same time periods, with the same credit risk as the currency forward. This means that under the (unrealistic) assumptions of  

1. No transaction costs   
2. No bid ask spreads   
3. No credit risk   
4. No counterparty risk   
5. Liquid markets  

we can write the equivalence between the related synthetic and the original instrument as a contractual equation that can conveniently be exploited in practice. In fact, the synthetic using the money market involved three contractual deals that can be summarized by the following contractual equation:  

![](7f11f1cfb298a13b9cbb89474d227ba300d28b8d5c291cfa60d26b654e6e71cc.jpg)  

This operation can be applied to any two currencies to yield the corresponding FX forward.  

Under the simplifying assumptions listed above, we expect that arbitrage will make the values of the two sides of the contractual equation equal. Due to arbitrage activity by market participants, CIRP is one of the financial engineering concepts that holds very closely in normal market conditions. In an interesting recent paper, Mancini-Griffoli and Ranaldo (2013) document deviations from CIRP for several months after the Lehman bankruptcy due to limits of arbitrage. Limits of arbitrage refers to a theory that, due to restrictions that are placed on funds that would normally be used by rational traders to exploit arbitrage opportunities, prices may remain in a nonequilibrium state for long periods of time.8  

# 6.5 APPLICATIONS  

The contractual equation derived earlier and the manipulation of cash flows that led to it may initially be thought of as theoretical constructs with limited practical application. This could not be further from the truth. We now discuss four examples that illustrate how the equation can be skillfully exploited to find solutions to practical, common problems faced by market participants.  

# 6.5.1 APPLICATION 1: A WITHHOLDING TAX PROBLEM  

We begin with a practical problem of withholding taxes on interest income. Our purpose is not to comment on the taxation aspects but to use this example to motivate uses of synthetic instruments.  

The basic idea here is easy to state. If a government imposes withholding taxes on gains from a particular instrument, say a bond, and if it is possible to synthetically replicate this instrument, then the synthetic may not be subject to withholding taxes. If one learns how to do this, then the net returns offered to clients will be significantly higher—with, essentially, the same risk.  

# EXAMPLE  

Suppose an economy has imposed a withholding tax on interest income from government bonds. Let this withholding tax rate be $20\%$ . The bonds under question have zero default probability and make no coupon payments. They mature at time $T$ and their time $t$ price is denoted by $B(t,T)$ . This means that if  

$$
B(t,T)=92\
$$  

one pays 92 dollars at time $t$ to receive a bond with face value 100. The bond matures at time $T$ , with the maturity value  

$$
B(T,T)=100
$$  

Clearly, the interest the bondholder has earned will be given by  

$$
100-B(t,T)=8
$$  

But because of the withholding tax, the interest received will only be 6.4:  

$$
\mathrm{Interestreceived}=8-0.2\cdot(8)=6.4
$$  

Thus the bondholder receives significantly less than what he or she earns.  

We can immediately use the ideas put forward to form a synthetic for any discount bond using the contractual equation in formula (6.8). We discuss this case using two arbitrary currencies called $Z$ and $X$ . Suppose T-bills in both currencies trade actively in their respective markets. The contractual equation written in terms of T-bills gives  

![](9a62799537428f313518c641de67b11d7d8e7827e3b4dc85b1fa4f8d5e6c674c.jpg)  

Manipulating this as an algebraic equation, we can transfer the $Z$ -denominated T-bill to the lefthand side and group all other instruments on the right-hand side.  

![](027369ca50fe2efdd4f093d6cbeb42c051e932d8a29f1b91a1914d0956d9b119.jpg)  

Now, we change the negative signs to positive, which reverses the cash flows, and obtain a synthetic $Z$ -denominated T-bill:  

![](2af3bb61dbd55b6380bbd887c1582e0bccb245461417aeca0f144b7ed4be3118.jpg)  

Thus, in order to construct a synthetic for $Z\cdot$ -denominated discount bonds, we first need to use money or T-bill markets of another economy where there is no withholding tax. Let the currency of this country be denoted by the symbol $X$ . According to Eq. (6.15), we exchange $Z^{\gamma}\mathrm{s}$ into currency $X$ with a spot operation at an exchange rate $e_{t_{0}}$ . Using the $X^{\prime}$ s obtained this way, we buy the relevant $X\mathrm{\Omega}$ -denominated T-bill. At the same time, we forward purchase $Z^{\bullet}{} $ for time $t_{1}$ . The geometry of these operations is shown in Figure 6.3. We see that by adding the cash flows generated by the right-hand-side operations, we can get exactly the cash flows of a T-bill in $Z$ .  

There is a simple logic behind these operations. Investors are taxed on $Z\cdot$ -denominated bonds. So they use another country’s markets where there is no withholding tax. They do this in a way that ensures the recovery of the needed $Z^{\bullet}{}_{}$ at time $t_{1}$ by buying $Z$ forward. In a nutshell, this is a strategy of carrying funds over time using another currency as a vehicle while making sure that the entry and exits of the position are pinned down at time $t_{0}$ .  

![](02a6fc48bcd9dadcb89dbcc18c138f5dd48aa365c2b0d24939839120abcc2da8.jpg)  

# FIGURE 6.3  

A synthetic Z-denominated bond.  

# 6.5.2 APPLICATION 2: CREATING SYNTHETIC LOANS  

The second application of the contractual equation has already been briefly discussed in Chapter 1. Consider the following market event from the year 1997. 10  

# EXAMPLE  

Following the collapse of Hokkaido Takushoku Bank, the “Japanese premium,” the extra cost to Japanese banks of raising money in the Eurodollar market increased last week in dramatic style. Japanese banks in the dollar deposit market were said to be paying around 40 bp over their comparable US credits, against less than 30 bp only a week ago.  

Faced with higher dollar funding costs, Japanese banks looked for an alternative source of dollar finance. Borrowing in yen and selling yen against the dollar in the spot market, they bought yen against dollars in the forward market, which in turn caused the USD/yen forward rate to richen dramatically.  

Thomson Reuters IFR (November 22, 1997).  

Readers with no market experience may consider this episode difficult to understand. Yet, the contractual equation in formula (6.8) can be used skillfully, to explain the strategy of Japanese banks mentioned in the example. In fact, what Japanese banks were trying to do was to create synthetic USD loans. The USD loans were either too expensive or altogether unavailable due to lack of credit lines. As such, the excerpt provides an excellent example of a use for synthetics.  

We now consider this case in more detail. We begin with the contractual equation in formula (6.8) again, but this time we write it for the USD/JPY exchange rate:  

![](d0e7d0d4094240f5cb990539f937a94c79adfbab3da0cd8a8745a0da90467609.jpg)  

Again, we manipulate this like an algebraic equation. Note that on the right-hand side, there is a loan contract. This is a genuine USD loan, and it can be isolated on the left-hand side by rearranging the right-hand-side contracts. The loan would then be expressed in terms of a replicating portfolio.  

![](09d3dd4b622a357fedba8385aef7be3728943ff5da7e4cda0a14698fc123eca0.jpg)  

Note that because we moved the deposit and the spot operation to the other side of the equality, signs changed. In this context, a deposit with a minus sign would mean reversing the cash flow diagrams and hence it becomes a loan. A spot operation with a minus sign would simply switch the currencies exchanged. Hence, the contractual equation can finally be written as  

![](7410fb8d7f9357757e34152eab8ec8a007570ebb85091a3ff81afd30f12571a5.jpg)  

This contractual equation can be used to understand the previous excerpt. According to the quote, Japanese banks that were hindered in their effort to borrow Eurodollars in the interbank (Euro) market instead borrowed Japanese yen in the domestic market, which they used to buy (cash) dollars. But, at the same time, they sold dollars forward against yen in order to hedge their future currency exposure. Briefly, they created exactly the synthetic that the contractual equation implies on the right-hand side.  

# 6.5.3 APPLICATION 3: CAPITAL CONTROLS  

Several countries have, at different times, imposed restrictions on capital movements. These are known as capital controls. Suppose we assume that a spot purchase of USD against the local currency $X$ is prohibited in some country.  

A financial engineer can construct a synthetic spot operation using the contractual relationship, since such spot operations were one of the constituents of the contractual equation as shown in formula (6.8). Rearranging formula (6.8), we can write  

![](5c6f07eb29e3da847cf2379a3e96ebf450087dc13913f90ace5e32cf5cec9930.jpg)  

The right-hand side will be equivalent to a spot purchase of USD even when there are capital controls. Precursors of such operations were called parallel loans and were extensively used by businesses, especially in Brazil and some other emerging markets.11 The geometry of this situation is shown in Figure 6.4.12  

# 6.5.4 APPLICATION 4: “CROSS” CURRENCIES  

Our final example does not make use of the contractual equation in formula (6.8) directly. However, it is an interesting application of the notion of contractual equations, and it is appropriate to consider it at this point.  

One of the simplest synthetics is the “cross rates” traded in FX markets. A cross currency exchange rate is a price that does not involve USD. The major “crosses” are EUR/JPY, EUR/ CHF, and GBP/EUR. Other “crosses” are relatively minor. In fact, if a trader wants to purchase Swiss francs in, for example, Taiwan, the trader would carry out two transactions instead of a single spot transaction. He or she would buy USD with Taiwan dollars and then sell the USD against the Swiss franc. At the end, Swiss francs are paid by Taiwan dollars. Why would one go through two transactions instead of a direct purchase of Swiss francs in Taiwan? It is cheaper to do so because of lower transaction costs and higher liquidity of the USD/CHF and USD/TWD exchange rates.  

![](2cef7cb23a170ac9b904682d0844a12facb006cfbc1458a38129b0f72ed6fca4.jpg)  

# FIGURE 6.4  

A synthetic spot operation.  

We can formulate this as a contractual equation:  

![](24f15a0b44e35d6d274b7aee839abefa8d13f5e8b49c6a500c9c37ed36a53ec7.jpg)  

It is easy to see why this contractual equation holds. Consider Figure 6.5. The addition of the cash flows in the top two graphs results in the elimination of the USD element, and one creates a synthetic “contract” of spot purchase of CHF against Taiwan dollars.  

This is an interesting example because it shows that the price differences between the synthetic and the actual contract cannot always be exploited due to transaction costs, liquidity, and other rigidities such as the legal and organizational framework. It is also interesting in this particular case, that it is the synthetic instrument which turns out to be cheaper. Thus, before buying and selling an instrument, a trader should always try to see if there is a cheaper synthetic that can do the same job.  

![](3017a06ef9c9ffadf57f83c5a114d4eadee84282ee24c054dc286f5d1cef9cdb.jpg)  

# FIGURE 6.5  

A synthetic cross rate.  

# 6.6 CONVENTIONS FOR FX FORWARD AND FUTURES 6.6.1 QUOTING CONVENTIONS FOR FX FORWARD  

Forwards in foreign currencies have special quotation conventions. Markets do not quote outright forward rates, but the so-called forward points. The related terminology and conventions are illustrated in the following example.  

# EXAMPLE  

Suppose outright forward EUR/USD quotes are given by and that the spot exchange rate quotes are as given by  

<html><body><table><tr><td>Bid Ask</td><td></td></tr><tr><td>1.0210 1.0220</td><td></td></tr></table></body></html>  

<html><body><table><tr><td>Bid</td><td> Ask</td></tr><tr><td>1.0202 1.0205</td><td></td></tr></table></body></html>  

Then, instead of the outright forward quotes, traders prefer to quote the forward points obtained by subtracting the corresponding spot rate from the outright forward:  

<html><body><table><tr><td>Bid Ask</td><td></td></tr><tr><td>8</td><td></td></tr></table></body></html>  

In reality, forward points are determined directly from Eq. (6.5) or (6.7).  

Market conventions sometimes yield interesting information concerning trading activity and the forward FX quotes is a case in point. Let $\boldsymbol{F}_{t_{0}}$ and $\boldsymbol{e}_{t_{0}}$ be time $t_{1}$ forward and time $t_{0}$ spot exchange rates respectively as given by Eq. (6.5). Using the expression in Eq. (6.5) and ignoring the bid ask spreads, we can write approximately  

$$
F_{t_{0}}-e_{t_{0}}\cong\left(r_{t_{0}}^{\mathrm{d}}-r_{t_{0}}^{\mathrm{f}}\right)\left({\frac{t_{1}-t_{0}}{360}}\right)e_{t_{0}}
$$  

where $r_{t_{0}}^{\mathrm{d}},r_{t_{0}}^{\mathrm{f}}$ are the relevant interest rates in domestic and foreign currencies, respectively.13 Forward points are the difference between the forward rate found using the pricing equation in formula (6.21) and the spot exchange rate:  

$$
F_{t_{0}}-e_{t_{0}}
$$  

They are also called “pips” and written as bid/ask. We give an example for the way forward points are quoted and used.  

# EXAMPLE  

Suppose the spot and forward rate quotes are as follows:  

<html><body><table><tr><td>EUR/USD Bid</td><td>Ask</td></tr><tr><td>Spot 0.8567</td><td>0.8572</td></tr><tr><td>1 Year -28.3</td><td>-27.3</td></tr><tr><td>2 Year 44.00</td><td>54.00</td></tr></table></body></html>  

From this table, we can calculate the outright forward exchange rate $\boldsymbol{F}_{t_{0}}$ .  

For year 1, subtract the negative pips in order to get the outright forward rates:  

$$
{\bigg(}0.8567-{\frac{28.3}{10,000}}{\bigg)}{\bigg/}{\bigg(}0.8572-{\frac{27.3}{10,000}}{\bigg)}
$$  

For year 2, the quoted pips are positive. Thus, we add the positive points to get the outright forward rates:  

$$
{\bigg(}0.8567+{\frac{44}{10,000}}{\bigg)}{\bigg/}{\bigg(}0.8572+{\frac{54}{10,000}}{\bigg)}
$$  

Forward points give the amount needed to adjust the spot rate in order to obtain the outright forward exchange rate. Depending on the market, they are either added to or subtracted from the spot exchange rate. We should discuss briefly some related conventions.  

There are two cases of interest. First, suppose we are given the following forward point quotes (second row) and spot rate quotes (first row) for EUR/USD:  

<html><body><table><tr><td>Bid</td><td>Ask</td></tr><tr><td>1.0110</td><td>1.0120</td></tr><tr><td>12</td><td>16</td></tr></table></body></html>  

Next note that the forward point listed in the “bid” column is lower than the forward point listed in the “ask” column. If forward point quotes are presented this way, then the points will be added to the last two digits of the corresponding spot rate.  

Thus, we will obtain  

Note that the bid ask spread on the forward outright will be greater than the bid ask spread on the spot.  

Second, suppose, we have the following quotes:  

<html><body><table><tr><td>Bid</td><td>Ask</td></tr><tr><td>1.0110</td><td>1.0120</td></tr><tr><td>23</td><td>18</td></tr></table></body></html>  

Here the situation is reversed. The forward point listed in the “bid” column is greater than the forward point listed in the “ask” column. Under these conditions, the forward points will be subtracted from the last two digits of the corresponding spot rate. Thus, we will obtain  

Note that the bid ask spread on the forward outright will again be greater than the bid ask spread on the spot. This second case is due to the fact that sometimes the minus sign is ignored in quotations of forward points.  

# 6.6.2 FX FORWARD VERSUS FX FUTURES  

The OTC FX market turnover has historically dwarfed trading volume of standardized FX products on exchanges. According to the BIS, in 2013, the OTC FX market was about 17 times larger than the exchange-traded FX derivatives market. Although market participants typically use forward instead of futures for FX trading, it is instructive to review contract specifications of FX futures.  

FX futures contracts exist on many currency pairs. The CME, for example, offers the following currency contract: EUR/USD, JPY/USD, GBP, USD, CHF/USD, CDN/USD, AUD/USD, MXN/ USD, NZD/USD, RUB/USD, ZAR/USD, BRL/USD, and most recently RMB/USD and KRW/ USD. Major cross-rate contracts include EUR/GBP, EUR/JPY, EUR/CHF, GBP/CHF, and others.  

Exchange-traded currency futures have historically differed from OTC FX transactions in terms of their standardization and flexibility or customization inherent in working with a dealer. However, derivatives exchanges are introducing greater degrees of flexibility in their trading practices. FX futures are predominantly traded electronically. The typical contract calls for delivery of a specified currency, or a cash settlement, during the months of March, June, September, and December.  

# 6.7 SWAP ENGINEERING IN FX MARKETS  

So far we have discussed simple currency derivatives in the form of FX forward. Now we will apply the more advanced financial engineering concepts related to interest rate swaps that we discussed in Chapter 4 and illustrate swap engineering in FX markets. We will encounter two different types of swaps linked to FX markets. First we will discuss FX swaps, then we will turn to currency swaps. As we will see there are important differences in the replication and uses of FX and currency swaps respectively. In practice, in terms of turnover, the FX swap market is an order of magnitude larger than the currency swap market.  

In the previous sections, we created two synthetics for forward FX contracts. We can now ask the next question: Is there an optimal way of creating a synthetic? Or, more practically, can a trader buy a synthetic cheaply, and sell it to clients after adding a margin, and still post the smallest bid ask spreads?  

# 6.7.1 FX SWAPS  

We can use the so-called FX swaps and pay a single bidask spread instead of going through two separate bid ask spreads, as is done in contractual equation (6.8). The construction of an FX swap is shown in Figure 6.6.  

According to this figure, there are at least two ways of looking at a FX swap. The FX swap is made of a money market deposit and a money market loan in different currencies written on the same “ticket.” The second interpretation is that we can look at a FX swap as if the two counterparties spot purchase and forward sell two currencies against each other, again on the same deal ticket.  

When combined with a spot operation, FX swaps duplicate forward currency contracts easily, as shown in Figure 6.7. Because they are swaps of a deposit against a loan, interest rate differentials  

![](c843f9584db12986ae171c1b2bc251d582232b8b890d2918aaa1711cbd3aa22b.jpg)  

# FIGURE 6.6  

A simplified FX swap.  

will play an important role in FX swaps. After all, one of the parties will be giving away a currency that can earn a higher rate of interest and, as a result, will demand compensation for this “loss.” This compensation will be returned to him or her as a proportionately higher payment at time $t_{1}$ . The parties must exchange different amounts at time $t_{1}$ , as compared to the original exchange at $t_{0}$ .  

As the above figure shows, an FX swap is a contract in which one party borrows one currency from, and at the same time lends another to, the second party. Each party uses the repayment obligation to its counterparty as collateral and the amount of repayment is fixed at the FX forward rate at the start of the contract. Hence, FX swaps can be interpreted as collateralized borrowing/lending, although the collateral does not necessarily cover the entire counterparty risk.  

# 6.7.1.1 Advantages  

Why would a bank prefer to deal in FX swaps instead of outright forward? This is an important question from the point of view of financial engineering. It illustrates the advantages of spread products.  

FX swaps have several advantages over the synthetic seen earlier. First of all, FX swaps are interbank instruments and, normally, are not available to clients. Banks deal with each other every day, and thus, compared to other counterparties, one could argue that counterparty risk is relatively lower in writing such contracts. In liquid markets, the implied bid ask spread for synthetics  

![](edba8fbbfef593ea4e2e696f92f9e2dc793554d5808d2dc94a9f481a53c06241.jpg)  

# FIGURE 6.7  

FX swap combined with spot operation leads to forward.  

constructed using FX swaps will be smaller than the synthetic constructed from deposits and loans, or T-bills for that matter.  

The second issue is liquidity. How can a market participant borrow and lend in both currencies without moving prices? An FX swap is again a preferable way of doing this. With an FX swap, traders are not buying or selling deposits, rather they are exchanging them.  

The final advantage of FX swaps resides in their balance sheet effects, or the lack thereof. The synthetic developed in Figure 6.2 leads to increased assets and liabilities. One borrows new funds and lends them. Such transactions may lead to new credit risks and new capital requirements. FX swaps are off-balance sheet items, and the synthetic shown in Figure 6.7 will have minor balance sheet effects. FX swaps can affect a bank’s capital adequacy ratio (CAR) since they change the capital requirement for market risk and credit market risk.14  

# 6.7.1.2 Uses of FX swaps  

Financial institutions and their clients, such as exporters and importers as well as investors, use FX swaps to hedge their positions. FX swaps can also be used for speculation, typically by combining two offsetting FX swap positions with different maturity dates. Financial institutions with a need for foreign currency can either (a) borrow directly in the uncollateralized money market for the foreign currency or (b) borrow in another (normally the domestic) currency’s uncollateralized money market, and then convert the proceeds into a foreign currency obligation through an FX swap. When a bank, for example, raises dollars by means of an FX swap using the euro as a funding currency, it exchanges euros for dollars at the FX spot rate. The borrowing cost in dollars implied by the EUR/USD FX swap is called the FX swap-implied dollar rate $r_{t_{0}}^{\mathrm{d}}$ . It is defined as  

$$
r_{t_{0}}^{\mathrm{d}}={\frac{F_{t_{0}}}{e_{t_{0}}}}\times\left(1+r_{t_{0}}^{\mathrm{f}}\right)
$$  

where $r_{t_{0}}^{\mathrm{d}}$ and $r_{t_{0}}^{\mathrm{f}}$ are the relevant interest rates in domestic and foreign currencies, respectively, and $F_{t_{0}}$ and $e_{t_{0}}$ are the forward and spot rates between the euro and the dollar. The choice of whether the bank should raise dollars using (a) or (b) above should be a function of the relative cost. If the costs associated with (a) and (b) are the same, i.e., the FX swap-implied dollar rate is equal to the dollar LIBOR rate in our example, then CIRP holds. Deviations from CIRP occurred during the GFC and other turbulent financial market episodes in the past, but arbitrageurs must be careful when interpreting any test of CIRP deviations since these must carefully take into account real-life complications such as bid ask spreads, differences between the costs of secured and unsecured borrowing as well as whether rates such as LIBOR reflect actual interbank borrowing costs in periods of stress.  

# 6.7.1.3 Quotation conventions  

There is an important advantage to quoting swap points over the outright forward quotes. This indicates a subtle aspect of market activity. A quote in terms of forward points will essentially be independent of spot exchange rate movements and will depend only on interest rate differentials. An outright forward quote, on the other hand, will depend on the spot exchange rate movements as well. Thus, by quoting forward points, market professionals are essentially separating the risks associated with interest rate differentials and spot exchange rate movements respectively. The exchange rate risk will be left to the spot trader. The forward FX trader will be trading the risk associated with interest rate differentials only.  

To see this better, we now look at the details of the argument.  

Taking partial derivatives of Eq. (6.21) gives  

$$
\begin{array}{c}{{\displaystyle\partial\big(F_{t_{0}}-e_{t_{0}}\big)\cong\left(r_{t_{0}}^{\mathrm{d}}-r_{t_{0}}^{\mathrm{f}}\right)\left(\frac{t_{1}-t_{0}}{360}\right)\partial e_{t_{0}}}}\\ {{\cong0}}\end{array}
$$  

If the daily movement of the spot rate $\boldsymbol{e}_{t_{0}}$ is small, the right-hand side will be negligible. In other words, the forward swap quotes would not change for normal daily exchange rate movements, if interest rates remain the same and as long as exchange rates are quoted to four decimal places. The following example illustrates what this means.  

# EXAMPLE  

Suppose the relevant domestic and foreign interest rates are given by  

$$
\begin{array}{r}{r_{t_{0}}^{\mathrm{d}}=0.03440}\\ {r_{t_{0}}^{\mathrm{f}}=0.02110}\end{array}
$$  

where the domestic currency is euro and the foreign currency is USD. If the EUR/USD exchange rate has a daily volatility of, say, $0.0I\%$ a day, which is a rather significant move, then, for FX swaps with 3-month maturity, we have the following change in forward points:  

$$
\begin{array}{c l l}{{\partial{\big(}F_{t_{0}}-e_{t_{0}}{\big)}=0.01330{\bigg(}{\frac{90}{360}}{\bigg)}0.0100}}\\ {{}}\\ {{=0.00003325}}\end{array}
$$  

which, in a market that quotes only four decimal points, will be negligible.  

Hence, forward points depend essentially on the interest rate differentials. This “separates” exchange rate and interest rate risk and simplifies the work of the trader. It also shows that forward FX contracts can be interpreted as if they are “hidden” interest rate contracts.  

# 6.8 CURRENCY SWAPS VERSUS FX SWAPS  

Although they have similar names, currency swaps and FX swaps are different instruments. First we introduce currency swaps and apply the swap engineering methodology from Chapter 4 to their replication. Then we will highlight differences between currency swaps and FX swaps.  

# 6.8.1 CURRENCY SWAPS  

Currency swaps15 are similar to interest rate swaps, but there are some differences. First, the exchanged cash flows are in different currencies. This means that two different yield curves are involved in swap pricing instead of just one. Second, in the large majority of cases, a floating rate is exchanged against another floating rate. A third difference lies in the exchange of principals at initiation and a re-exchange at maturity. In the case of interest rate swaps, this question does not arise since the notional amounts are in the same currency. Yet, currency swaps can be engineered almost the same way as interest rate swaps.  

Formally, a currency swap will have the following components. There will be two currencies, say USD $(\$)$ and euro (h). The swap is initiated at time $t_{0}$ and involves (1) an exchange of a principal amount $N^{\mathbb{S}}$ against the principal $\bar{\boldsymbol{M}}^{\epsilon}$ and (2) a series of floating interest payments associated with the principals $N^{\mathbb{S}}$ and $\boldsymbol{M}^{\epsilon}$ , respectively. They are settled at settlement dates, $\{t_{1},t_{2},...,t_{n}\}$ . One party will pay the floating payments $L_{t_{i}}^{\mathbb{S}}N^{\mathbb{S}}\delta$ and receive floating payments of size $L_{t_{i}}M\delta$ . The two LIBOR rates $L_{t_{i}}^{\mathbb{S}}$ and $L_{t_{i}}$ will be determined at set dates $\{t_{0},t_{1},...,t_{n-1}\}$ . The maturity of swap will be $m$ years.  

A small spread $s_{t_{0}}$ can be added to one of the interest rates to make both parties willing to exchange the cash flows. The market maker will quote bid/ask rates for this spread.  

# EXAMPLE  

Figure 6.8 shows a currency swap. The USD notional amount is 1 million. The current USD/ EUR exchange rate is at 0.95. The agreed spread is 6 bp. The initial 3-month LIBOR rates are  

$$
L_{t_{i}}^{\S}=3\%
$$  

$$
L_{t_{i}}^{\S}=3.5\%
$$  

![](dbd1ede0eb90d5c97d66c12421f39b0b698b174a2f9e60df766fd1f7bf6b178f.jpg)  
Pay EUR-LIBOR based floating cash flows plus some small spread. Note that the principals are swapped at the same exchange rate USD/EUR...  

# FIGURE 6.8  

Three-period currency swap.  

This means that at the first settlement date  

$$
(1,000,000)(0.03+0.0006)\frac{1}{4}=\S7650
$$  

will be exchanged against  

$$
0.95(1,000,000)(0.035){\frac{1}{4}}=8312.5
$$  

All other interest payments would be unknown. Note that the euro principal amount is related to the USD principal amount according to  

$$
e_{t_{0}}N^{\S}=M
$$  

where $\boldsymbol{e}_{t_{0}}$ is the spot exchange rate at $t_{0}$ . Also, note that we added the swap spread to the USD LIBOR.  

Pricing currency swaps will follow the same principles as interest rate swaps. A currency swap involves well-defined cash flows and consequently we can calculate an arbitrage-free value for each sequence of cash flows. Then these cash flows are traded. An appropriate spread is added to either floating rate.  

By adjusting this spread, a swap dealer can again make the two parties willing to exchange the two cash flows.  

# 6.8.2 DIFFERENCES BETWEEN CURRENCY SWAPS AND FX SWAPS  

We will now compare currency swaps with FX swaps introduced earlier. To recap, a currency swap has the following characteristics:  

1. Two principals in different currencies and of equal value are exchanged at the start date $t_{0}$ . 2. At settlement dates, interest will be paid and received in different currencies and according to the agreed interest rates. 3. At the end date, the principals are re-exchanged at the same exchange rate.  

A simple example is the following. 100,000,000 euros are received and against these $100,000,000e_{t_{0}}$ dollars are paid, where the $\boldsymbol{e}_{t_{0}}$ is the “current” EUR/USD exchange rate. Then, 6-month LIBOR-based interest payments are exchanged twice. Finally, the principal amounts are exchanged at the end date at the same exchange rate $\boldsymbol{e}_{t_{0}}$ , even though the actual exchange rate $e_{t_{2}}$ at time $t_{2}$ may indeed be different than $\boldsymbol{e}_{t_{0}}$ . See Figure 6.9.  

![](41a83b301d34db51b555cb6eebd4b6293e9036947e6c727858bfef225979553d.jpg)  

# FIGURE 6.9  

Simple currency swap.  

![](30acffe269430356538365b07bc5a4a3857f68c25fbe88a5bcd100d38b2cbf96.jpg)  

# FIGURE 6.10  

FX swap.  

The FX swap for the same period is shown in Figure 6.10. Here, we have no interim interest payments, but instead the principals are re-exchanged at a different exchange rate equal to  

$$
f_{t_{0}}=e_{t_{0}}\frac{1+L_{t_{0}}^{\mathrm{USA}}\delta}{1+L_{t_{0}}^{\mathrm{EUR}}\delta}
$$  

Why this difference? Why would the same exchange rate be used to exchange the principals at start and end dates of a currency swap while different exchange rates are used for an FX swap?  

We can look at this question from the following angle. The two parties are exchanging currencies for a period of 1 year. At the end of the year, they are getting back their original currency.  

But during the year, the interest rates in the two currencies would normally be different. This difference is explicitly paid out in the case of currency swaps during the life of the swap as interim interest payments. As a result, the counterparties are ready to receive the exact original amounts back. The interim interest payments would compensate them for any interest rate differentials.  

In the case of FX swaps, there are no interim interest payments. Hence, the compensation must take place at the end date. Thus, the interest payments are bundled together with the exchange of principals at the end date.  

# 6.8.3 ANOTHER DIFFERENCE  

Looked at from a financial engineering perspective, the currency swap is like an exchange of two FRNs with different currencies and no credit risk. The FX swap, on the other hand, is like an exchange of two zero-coupon bonds in different currencies.  

Because the LIBOR rates at time $t_{1}$ are unknown as of time $t_{0}$ , the currency swap is subject to slightly different risks than FX swaps of the same maturity. Note that FX and currency swaps are in principle subject to significantly more exposure to counterparty risk than are interest rate swaps, due to the exchange of notional amounts in FX and currency swaps.  

# 6.8.4 USES OF CURRENCY SWAPS  

Although there are structural differences between FX and currency swaps, the former basically serve the same economic purpose as the latter, except for the exchange of (floating) interest rates during the contract term. Financial institutions and their clients, including multinational corporations involved in foreign direct investment, use currency swaps to fund foreign currency investments. Other uses involve converting currencies of liabilities, particularly by issuers of bonds denominated in foreign currencies, as we will see in an example at the end of the chapter.  

# 6.8.5 RELATIVE SIZE AND LIQUIDITY OF FX SWAP AND CURRENCY SWAPMARKETS  

We discussed similarities and differences between FX and currency swaps above. Which instrument is more widely used and more important in practice? FX swaps account for a much larger proportion of FX market turnover than currency swaps. In 2013, the FX swap market was about 40 times larger than the currency swap market. According to the BIS Triennial Central Bank Survey 2013, FX swaps remained the most actively traded FX instrument in 2013 and their daily volume of d2.2 trillion accounted for $42\%$ of all FX-related transactions. Spot FX transactions and outright forward transactions made up $37\%$ and $12\%$ , respectively, of FX market turnover. In comparison, currency swaps contribute only a small share of FX turnover. Currency swap turnover stood at $\$54$ billion per day, or around $1\%$ of the total. FX swaps remain most liquid at maturities below 1 year, but FX swap turnover has recently been growing for transactions with longer maturities. In contrast to FX swaps, most currency swaps are long term with maturities ranging from 1 to 30 years. The reason for this is that the currency swap maturity reflects the maturity of the transactions that they are funding.  

# 6.8.6 THE EFFECT OF THE GFC ON THE FX MARKET, MARGINS, AND CLEARING  

As we saw above, the advantages of FX forward and swaps are linked to their relatively high liquidity and low cost. During the GFC, there were significant deviations from CIRP, i.e., the FX swap-implied USD rates and the LIBOR rates for major currencies such as the euro and pound sterling diverged. This has been partly attributed to European financial institutions that required USD but faced increasing concerns about their creditworthiness and counterparty risk in dollar interbank markets. As a result, these institutions used the FX swap market to raise dollars using both euro and pound sterling as funding currencies, causing a shift toward one-sided order flow in the FX swap market.  

The GFC took a toll on volumes in FX derivatives, but the regulatory overhaul of the financial system that followed the crisis has left the FX derivatives market largely unchanged due to exemptions that were granted. On November 16, 2012, the US Department of the Treasury issued its final determination that exempts FX swaps and forwards from mandatory derivative requirements, including central clearing and exchange trading. Following the footsteps of the BIS and the US Treasury, on April 14, 2014, European supervisory authorities proposed to exempt uncleared FX swaps and forwards from initial margin requirements. The EU proposals envisage that users of the FX swaps and forward market will only have to post variation margin on these trades, rather than putting up hefty initial margins as well, leaving these instruments less capital-intensive than other asset classes and boding well for liquidity and financial engineering applications in this market.  

# EXAMPLE  

While participants to an interest rate swap might be paying variation margin on a trade for one or two decades, trade duration in FX is typically much shorter. Of the current gross notional amount of FX swaps and forward in the EU, h5.7 trillion has a maturity of less than 6 months, and only h1.2 trillion stretches out over 6 months. The consultation paper estimates that only $18\%$ of all OTC FX trades will be processed through central counterparties. The figure for rates trades is expected to be $55\%$ , and for credit $62\%$ . Forex market-makers have already begun offering replication products to clients, which mimic the effect of rates or credit hedges but at a fraction of the cost.  

FX week (April 16, 2014).  

As the above reading illustrates the cost advantages implied by lower margin requirements for FX forwards and swaps have already had an impact on financial engineering practice. They have led market makers at major dealers to explore cross-hedges in the form of FX products. Clients, such as investors or banks, that have an incentive to hedge interest rate or credit risk may face higher capital charges and costs on such hedges. If FX products can be devised by dealers that mimic interest rate or credit hedges due to higher correlations with these markets, this can be a more cost-efficient hedge solution for clients and a new revenue stream for dealers. The example also illustrates the continuing trends toward financial engineering solutions involving multiple asset classes and asset class correlations.  

# 6.9 MECHANICS OF SWAPPING NEW ISSUES  

# 6.9.1 INTEREST RATE AND CURRENCY SWAP EXAMPLE  

In the context of interest rate swap engineering, we noted that the basic cash flow engineering for swaps ignores several minor technical points that need to be considered in practice. We provided a real-life example of interest rate swap usage and highlighted quoting conventions and costs. Similarly, in this chapter, our discussion of swap engineering in currency markets has abstracted away from important real-world considerations. Therefore, here we provide another real-world application to new bond issues.  

Suppose there is an A-rated British entity that would like to borrow 100 million sterling (GBP) for a period of 3 years. The entity has no preference toward either floating or fixed-rate funding, and intends to issue in Euromarkets. Market research indicates that if the entity went ahead with its plans, it could obtain fixed-rate funds at $6.5\%$ annually.16 But the bank recommends the following approach.  

It appears that there are nice opportunities in USD GBP currency swaps, and it makes more sense to issue a floating rate Eurobond in the USD sector with fixed coupons. The swap market quotes funding at $\mathrm{LIBOR}+95$ bp in GBP against USD rates for this entity. Then the proceeds can be swapped into sterling for a lower all-in-cost. How would this operation work? And what are the risks?  

We begin with the data concerning the new issue. The parameters of the newly issued bond are provided in Table 6.1.17 Now, the issuer would like to swap these proceeds to floating rate GBP funds. In doing this, the issuer faces the market conditions as provided in Table 6.2. We first work out the original and the swapped cash flows and then calculate the all-in-cost, which is the real cost of funds to the issuer after the proceeds are swapped into GBP.  

<html><body><table><tr><td colspan="2">Table 6.1 The New Issue</td></tr><tr><td>Amount</td><td>USD100 million</td></tr><tr><td>Maturity</td><td>2 years</td></tr><tr><td>Coupon</td><td>6% p.a.</td></tr><tr><td>Issue price</td><td>100</td></tr><tr><td>Options</td><td>None</td></tr><tr><td>Listing</td><td>Luxembourg</td></tr><tr><td>Commissions</td><td>14</td></tr><tr><td>Expenses</td><td>USD75000</td></tr><tr><td>Governing law</td><td>English</td></tr><tr><td>Negative pledge</td><td>Yes</td></tr><tr><td>Pari passu</td><td>Yes</td></tr><tr><td>Cross default</td><td>Yes</td></tr></table></body></html>  

<html><body><table><tr><td>Table 6.2 Swap Market Quotes</td><td></td></tr><tr><td>Spot exchange rate GBP-USD</td><td>1.6701/1.6708</td></tr><tr><td>GBP 2-year interest rate swap</td><td>5.46/51</td></tr><tr><td>USD-GBP currency swap</td><td>+4/-1</td></tr></table></body></html>  

The first step is to obtain the amount of cash the issuer will receive at time $t_{0}$ and then determine how much will be paid out at $t_{1},t_{2}$ . To do this, we again need to calculate the proceeds from the issue.  

The issue price is 100.75 and the commissions are $1.25\%$ . This means that the amount received by the issuer before expenses is  

$$
{\frac{(100.75-1.25)}{100}}100,000,000=99,500,000
$$  

We see that the issue is sold at a premium which increases the proceeds, but once commissions are deducted, the amount received falls below 100 million. Thus, expenses must be deducted  

$$
\mathrm{Proceeds}=99,500,000-75,000=99,425,000
$$  

Given the proceeds, we can calculate the effective cost of fixed-rate USD funds for this issuer. The issuer makes two coupon payments of $6\%$ (out of the 100 million) and then pays back $100~\mathrm{{mil}}.$ - lion at maturity. At $t_{0}$ , the issuer receives only 99,425,000. This cash flow is shown in Figure 6.11. Note that unlike the theoretical examples, the principal paid is not the same as the principal received. This is mainly due to commissions and expenses.  

From this cash flow, we can calculate the internal rate of return $y_{t_{0}}$ by solving the equation  

$$
99,425,000=\frac{60,000}{\left(1+y_{t_{0}}\right)}+\frac{60,000}{\left(1+y_{t_{0}}\right)^{2}}+\frac{100,000,000}{\left(1+y_{t_{0}}\right)^{2}}
$$  

The solution is  

$$
y_{t_{0}}=6.3150\%
$$  

Hence, the true fixed cost of USD funds is greater than $6\%$ .  

The issuer will first convert this into floating rate USD funds. For this purpose, the issuer will sell a swap. That is to say, the issuer will receive fixed $5.46\%$ and pay floating LIBOR flat. This is equivalent to paying approximately USD $\mathrm{LIBOR}+54$ bp. Finally, the issuer will convert these USD floating rate funds into GBP floating rate funds by paying floating GBP and receiving floating USD.  

![](9effb309a47d3cf31af554dd688766b1313da718e7be912f42d62106f61a6023.jpg)  

# FIGURE 6.11  

New bond issue and currency swap.  

# 6.10 CONCLUSIONS  

This chapter has developed two main ideas. First we considered the engineering aspects of FX forward contracts and developed a contractual equation for them. We discussed two methodologies to FX forward replication based on money market and T-bill synthetics. Second, we applied the swap engineering methodology to FX swaps and currency swaps and highlighted differences between them. Real-life complications such as quoting conventions, clearing, and margin requirements are important for financial engineering in practice. We discussed the relative size of FX and currency swap markets and highlighted the effect of recent regulatory exemptions of FX forward and swaps on financial engineering practice in FX markets.  

# SUGGESTED READING  

Weithers (2006) provides a good practical introduction to FX markets. Baba et al. (2008) examine the spillover of money market turbulence in 2007 to FX swap and currency swap markets. Cloyle (2000) provides an introduction to the basics of currency swaps.  

# EXERCISES  

1. Today is March 1, 2004. The day-count basis is actual/365. You have the following contracts on your FX book.  

CONTRACT A: On March 15, 2004, you will sell 1,000,000 EUR at a price $F_{t}^{1}$ dollars   
per EUR. CONTRACT B: On April 30, 2004, you will buy 1,000,000 EUR at a price $F_{t}^{2}$ dollars   
per EUR.   
a. Construct one synthetic equivalent of each contract.   
b. Suppose the spot EUR/USD is 1.1500/1.1505. The USD interest rates for loans under 1 year equal 2.25/2.27, and the German equivalents equal 2.35/2.36. Calculate the $F_{t}^{i}$ numerically.   
c. Suppose the forward points for $F_{t}^{1}$ that we observe in the markets is equal to 10/20. How can an arbitrage portfolio be formed?  

2. You are hired by a financial company in New Zealand and you have instant access to markets. You would like to lock in a 3-month borrowing cost in $\mathrm{NZS}$ for your client. You consider a $\mathrm{NZS}$ $1\times4$ FRA. But you find that it is overpriced as the market is thin.  

So you turn to Aussie. $\mathbf{A}\$1$ FRAs are very liquid. It turns out that the $\mathbf{A}\mathbb{S}$ and $\mathrm{NZS}$ forward are also easily available.  

In particular, you obtain the following data from Reuters:  

<html><body><table><tr><td>A$/NZ$</td><td>Spot the:</td><td>1.17/18</td></tr><tr><td></td><td>1-month forward:</td><td>1.18/22</td></tr><tr><td></td><td>3-month forward:</td><td>1.19/23</td></tr><tr><td></td><td>4-month forward:</td><td>1.28/32</td></tr><tr><td>A$ FRA's</td><td>1X4</td><td>8.97</td></tr></table></body></html>  

a. Show how you can create a $1\times4~\mathrm{NZS}$ from these data.  

b. Show the cash flows.   
c. What are the risks of your position (if any) compared to a direct $1\times4~\mathrm{NZS}$ FRA?   
d. To summarize the lessons learned from this exercise (if any), do you think there must be arbitrage relationships between the FRA markets and currency forward? Explain. Or better, provide the relevant formulas.  

3. Suppose at time $t=0$ , we are given prices for four zero-coupon bonds $(B_{1},B_{2},B_{3},B_{4})$ that mature at times $t=1,2,3$ , and 4. This forms the term structure of interest rates.  

We also have the one-period forward rates $(f_{0},f_{1},f_{2},f_{3})$ , where each $f_{i}$ is the rate contracted at time $t=0$ on a loan that begins at time $t=i$ and ends at time $t=i+1$ . In other words, if a borrower borrows $N$ GBP at time $i$ , he or she will pay back $N(1+f_{i})$ GBP at time $t=i+1$ .  

The spot rates are denoted by $r_{i}$ . By definition, we have  

$$
r=f_{0}
$$  

The $\{B_{i}\}$ and all forward loans are default-free, so that there is no credit risk. You are given the following live quotes:  

$$
B_{1}=0.92/0.94,B_{2}=0.85/0.88,B_{3}=0.82/0.85
$$  

and  

$$
f_{0}=8.10/8.12,f_{1}=9.01/9.03,f_{2}=10.12/10.16,f_{3}=18.04/18.10
$$  

a. Given the data on forward rates, obtain arbitrage-free prices for the zero-coupon bonds, $B_{1}$ and $B_{2}$ .   
b. What is the three-period swap rate under these conditions?  

4. Going back to the previous exercise, suppose you are given, in addition, data on FRAs both for USD and for EUR. Also suppose you are looking for arbitrage opportunities. Would these additional data be relevant for you? Discuss briefly.  

5. Foreigners buying Australian dollar instruments issued in Australia have to pay withholding taxes on interest earnings. This withholding tax can be exploited in tax-arbitrage portfolios using swaps and bonds. First let us consider an episode from the markets related to this issue.  

Under Australia’s withholding tax regime, resident issuers have been relegated to second cousin status compared with nonresident issuers in both the domestic and international markets. Something has to change.  

In the domestic market, bond offerings from resident issuers incur the $10\%$ withholding tax. Domestic offerings from nonresident issuers, commonly known as Kangaroo bonds, do not incur withholding tax because the income is sourced from overseas. This raises the spectre of international issuers crowding out local issuers from their own markets.  

In the international arena, punitive tax rules restricting coupon washing have reduced foreign investor interest in Commonwealth government securities and semigovernment bonds. This has facilitated the growth of global Australian dollar offerings by Triple A-rated issuers such as Fannie Mae, which offer foreign investors an attractive tax-free alternative.  

The impact of the tax regime is aptly demonstrated in the secondary market. Exchangeable issues in the international markets from both Queensland Treasury Corporation and Treasury Corporation of NSW are presently trading through comparable domestic issues. These exchangeable issues are exempt from withholding tax.  

If Australia wishes to develop into an international financial center, domestic borrowers must have unfettered access to the international capital markets—which means compliance costs and uncertainty over tax treatment must be minimized. Moreover, for the Australian domestic debt markets to continue to develop, the inequitable tax treatment between domestic and foreign issues must be corrected (Thomson Reuters IFR, Issue 1206).  

We now consider a series of questions dealing with this problem. First, take a 4-year straight coupon bond issued by a local government that pays interest annually. We let the coupon rate be denoted by $c\%$ .  

Next, consider an Aussie $\$1$ Eurobond issued at the same time by a Spanish company. The Eurobond has a coupon rate $d\%$ . The Spanish company will use the funds domestically in Spain.  

Finally, you know that interest rate swaps or FRAs in Aussie $\$5$ are not subject to any tax   
a. Would a foreign investor have to pay the withholding tax on the Eurobond? Why or why not?   
b. Suppose the Aussie $\$5$ IRSs are trading at a swap rate of $d+10$ bp. Design a 4-year interest rate swap that will benefit from tax arbitrage. Display the relevant cash flows.   
c. If the swap notional is denoted by $N.$ , how much would the tax-arbitrage yield?   
d. Can you benefit from the same tax arbitrage using a strip of FRAs in Aussie $\$1$ ?   
e. Which arbitrage portfolio would you prefer, swaps or FRAs? For what reasons?   
f. Where do you think it is more profitable for the Spanish company to issue bonds under these conditions, in Australian domestic markets or in Euromarkets? Explain.  

6. Consider a 2-year currency swap between USD and EUR involving floating rates only. The EUR benchmark is selected as 6-month Euro LIBOR, the dollar benchmark is 6-month BBA LIBOR. You also have the following information:  

$$
\mathrm{onal\amount}=\mathrm{USD10},\mathrm{000},0
$$  

$$
\mathrm{Exchange~rate~EUR/USD}=0.84
$$  

a. Show the cash flow diagrams of this currency swap. Make sure to quantify every cash flow exactly (i.e., use a graph as well as the corresponding number).   
b. Show that this currency swap is equivalent to two floating rate loans.   
c. Suppose a company is trying to borrow USD10,000,000 from money markets. The company has the following information concerning available rates on 6-month loans:   
EUR LIBOR $=5.7\%$ , USD LIBOR $=6.7\%$   
EUR USD currency swap spread: 1 year—75, 2 years—90.   
Should this company borrow USD directly? Would the company benefit if it borrowed EUR   
first and then swapped them into USD?  

7. A treasurer in Europe would like to borrow USD for 3 months. But instead of an outright loan, the treasurer decides to use the repo market. The company has holdings of EUR40 million bonds. The treasurer uses a cross-currency repo. The details of the transaction are as follows:  

Clean price of the bonds: 97.00   
Term: September 1 to December 1   
Last coupon date on the bond: August 12   
Bond coupon $4\%$ item EUR/USD exchange rate: 1.1150  

3-month USD repo rate: $3\%$ Haircut: $3\%$ a. What is the invoice price (dirty price) of the bond in question? b. Should the repo be done on the dirty price or the clean price? c. How much in dollars is received on September 1? d. How much repo interest is paid on December 1?  

8. Suppose the quoted swap rate is 5.06/5.10. Calculate the amount of fixed payments for a fixed payer swap for the currencies below in a 100 million swap. • USD. EUR.  

Now calculate the amount of fixed payments for a fixed receiver swap for the currencies below in a 100 million swap.  

JPY.   
GBP.  