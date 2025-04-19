---
tags:
  - cash_flows
  - currency_forwards
  - exchange_rate
  - financial_engineering
  - hedging
aliases:
  - FX Forwards
  - Forward Contracts
key_concepts:
  - Currency forward instruments
  - EUR/USD exchange rate
  - Forward exchange rate
  - Hedging, pricing, risk management
  - Synthetic instrument creation
---

# 6.2 CURRENCY FORWARDS  

Currency forwards are very liquid instruments. Although they are elementary, they are used in a broad spectrum of financial engineering problems.  

Consider the EUR/UsD exchange rate.' The cash flows implied by a forward purchase of USD100 against euros are represented in Figure 6.2a. At time $t_{0}$ a contract is written for the forward purchase (sale) of USD100 against $100/F_{t_{0}}$ euros. The settlement--that is to say, the actual exchange of currencies-will take place at time $t_{1}$ . The forward exchange rate is $\boldsymbol{F}_{t_{0}}$ . At time $t_{0}$ nothing changes hands.  

Obviously, the forward exchange rate $F_{t_{0}}$ should be chosen at $t_{0}$ so that the two parties are satisfied with the future settlement and thus do not ask for any immediate compensating payment. This means that the time. $t_{0}$ value of a forward contract concluded at time $t_{0}$ is zero. It may, however,. become positive or negative as time passes and markets move.  

In this section, we discuss the structure of this instrument. How do we create a synthetic for an instrument such as this one? How do we decompose a forward contract? Once this is understood, we consider applications of our methodology to hedging, pricing, and risk management.  

![](acca12e93c876190b56516c4f75f984fafadb448e74d3070eedcc04098fda482.jpg)  

# FIGURE 6.2  

$(\mathrm{a}-\mathrm{c})$ A currency forward. $(\mathrm{d-f})$ A money market synthetic.  

A general method of engineering a (currency) forward or, for that matter, any linear instrument-is as follows:  

1. Begin with the cash flow diagram as shown in Figure 6.2a.   
2. Detach and carry the (two) rectangles representing the cash flows into Figure 6.2b and c.   
3. Then, add and subtract new cash flows at carefully chosen dates so as to convert the detached cash flows into meaningful financial contracts that players will be willing to buy and sell.   
4. As you do this, make sure that when the diagrams are added vertically, the newly added cas flows cancel out and the original cash flows are recovered.  

This procedure will become clearer as it is applied to progressively more complicated instruments. Now we consider the details..  

![](a14c7f280d9acc0241dc7e2519fc377d1eaa374d3e968df63d5f512d15c4b668.jpg)  

# FIGURE 6.2  

# 6.2.1 ENGINEERING THE CURRENCY FORWARD  

We apply this methodology to engineering a currency forward. Our objective is to obtain a contractual equation at the end and, in this way, express the original contract as a sum of two or more elementary contracts. The steps are discussed in detail.  

Begin with cash flows as shown in Figure 6.2a. If we detach the two cash flows, we get Figure 6.2b and c. At this point, nobody would like to buy cash flows in Figure 6.2b, whereas nobody would sell the cash flows in Figure 6.2c. Indeed, why pay something without receiving anything in return? So at this point, Figure 6.2b and c cannot represent tradeable financial instruments.  

However, we can convert them into tradeable contracts by inserting new cash flows, as in step 3 of the methodology. In Figure 6.2b, we add a corresponding cash inflow. In Figure 6.2c, we add a cash outflow. By adjusting the size and the timing of these new cash flows, we can turn the transactions in Figure 6.2b and c into meaningful financial contracts..  

We keep this as simple as possible. For Figure 6.2b, add a positive cash flow, preferably at time $t_{0}$ 2 This is shown in Figure 6.2d. Note that we denote the size of the newly added cash flow. by CEUR.  

In Figure 6.2c, add a negative cash flow at time $t_{0}$ , to obtain Figure 6.2e. Let this cash flow be denoted by $C_{t_{0}}^{\mathrm{USD}}$ . The size of $C_{t_{0}}^{\mathrm{USD}}$ is not known at this point, except that it has to be in USD..  

The vertical addition of Figure 6.2d and e should replicate what we started with in Figure 6.2a.. At this point, this will not be the case, since. $C_{t_{0}}^{\mathrm{USD}}$ and $\bar{C}_{t_{0}}^{\mathrm{EUR}}$ do not cancel out at time $t_{0}$ as they are denominated in different currencies. But, there is an easy solution to this. The "extra' time. $t_{0}$ cash flows can be eliminated by considering a third component for the synthetic. Consider Figure 6.2f Where one exchanges $C_{t_{0}}^{\mathrm{USD}}$ against $C_{t_{0}}^{\mathrm{EUR}}$ at time $t_{0}$ Afer he adition of this component, a vertical sum of the cash flows in Figure $6.2\mathrm{d-f}$ gives a cash flow pattern identical to the ones shown in. Figure 6.2a. If the credit risks are the same, we have succeeded in replicating the forward contract with a synthetic..  

# 6.2.2 WHICH SYNTHETIC?  

Yet, it is still not clear what the synthetic in Figure. $6.2\mathrm{d-f}$ consists of. True, by adding the cash. flows in these figures, we recover the original instrument shown in Figure 6.2a, but what kind of contracts do these figures represent? The answer depends on how the synthetic instruments shown in Figure 6.2d-f are interpreted.  

This can be done in many different ways. We consider two major cases. The first is a depositloan interpretation. The second involves Treasury bills..  

# 6.2.2.1 A money market synthetic  

The first synthetic is obtained using money market instruments. To do this, we need a brief review. of money market instruments. The following lists some important money market instruments, along. with the corresponding quote, registration, settlement, and other conventions that will have cash flow patterns similar to Figure 6.2d and e. The list is not comprehensive..  

# EXAMPLE  

Deposits/loans. These mature in less than 1 year. They are denominated in domestic and Eurocurrency units. Settlement is on the same day for domestic deposits and in 2 business days for Eurocurrency deposits. There is no registration process involved and they are not negotiable.  

Certificates of deposit $(C D)$ . Generally these mature in up to 1 year. They pay a coupon. and are sometimes sold in discount form. They are quoted on a yield basis, and exist both in domestic and Eurocurrency forms. Settlement is on the same day for domestic deposits and. in 2 working days for Eurocurrency deposits. They are usually bearer securities and are negotiable.  

Treasury bills. These are issued at 13-, 26-, and 52-week maturities. In France, they can also mature in 4-7 weeks; in the United Kingdom, also in 13 weeks. They are sold on a discount basis (United States, United Kingdom). In other countries, they are quoted on a yield basis. Issued in domestic currency, they are bearer securities and are negotiable.  

Commercial paper $(C P)$ . Their maturities are 1-270 days. They are very short-term securities, issued on a discount basis. The settlement is on the same day; they are bearer securities and are negotiable.  

Euro-CP. The maturities range from 2 to 365 days but most have 30- or 180-day maturities. Issued on a discount basis, they are quoted on a yield basis. They can be issued in any. Eurocurrency, but in general they are in Eurodollars. Settlement is in 2 business days, and they are negotiable.  

How can we use these money market instruments to interpret the synthetic for the FX forward as shown in Figure 6.2?  

One money market interpretation is as follows. The cash flow shown in Figure 6.2e involves making a payment of $C_{t_{0}}^{\mathrm{USD}}$ at timee $t_{0}$ to receive USD100 at a later date, $t_{1}$ . Clearly, an $C_{t_{0}}^{\mathrm{USD}}$ Eurodeposit rate.  

$$
C_{t_{0}}^{\mathrm{USD}}=\frac{100}{1+L_{t_{0}}^{\mathrm{USD}}((t_{1}-t_{0})/360)}
$$  

Note that we are using an ACT/360-day basis for the deposit rate $L_{t_{0}}^{\mathrm{USD}}$ , since the cash flow is in Eurodollars. Also, we are using money market conventions for the interest rate.3 Given the observed value of $L_{t_{0}}^{\mathrm{USD}}$ we can numerically determine the $C_{t_{0}}^{\mathrm{USD}}$ by using this equation.  

How about the cash flows shown in Figure 6.2d? This can be interpreted as a loan obtained in interbank markets. One receives $C_{t_{0}}^{\mathrm{EUR}}$ at time $t_{0}$ and makes a euro-denominated payment of. $100/F_{t_{0}}$ at the later date $t_{1}$ . The value of this cash flow will be given by  

$$
C_{t_{0}}^{\mathrm{EUR}}=\frac{100/F_{t_{0}}}{1+L_{t_{0}}^{\mathrm{EUR}}((t_{1}-t_{0})/360)}
$$  

where $C_{t_{0}}^{\mathrm{EUR}}$ is the relevant interest rate in euros.  

Finally, we need to interpret the last diagram shown in Figure 6.2f. These cash flows represent an exchange of $C_{t_{0}}^{\mathrm{USD}}$ against $C_{t_{0}}^{\mathrm{EUR}}$ al time $t_{0}$ at the rate $e_{t_{0}}$  

The synthetic is now fully described:  

Take an interbank loan in euros (Figure 6.2d).   
Using these euro funds, buy spot dollars (Figure 6.2f).   
Deposit these dollars in the interbank market (Figure 6.2f).  

This portfolio would exactly replicate the currency forward, since by adding the cash flows in Figure 6.2d-f, we recover exactly the cash flows generated by a currency forward as shown in Figure 6.2a.  

# 6.2.2.2 A synthetic with T-bills  

We can also create a synthetic currency forward using Treasury-bill markets. In fact, let $B$ $(t_{0},t_{1})^{\mathrm{USD}}$ be the time. $t_{0}$ price of a default-free discount bond that pays USD100 at time $t_{1}$ Similarly, let $B(t_{0},t_{1})^{\mathrm{EUR}}$ be the time $t_{0}$ price of a default-free discount bond that pays EUR100 at time $t_{1}.$ Then the cash flows shown in Figure 6.2d-f can be reinterpreted so as to represent the following transactions:\*  

Figure 6.2d is a short position in $B(t_{0},t_{1})^{\mathrm{EUR}}$ where $1/F_{t_{0}}$ units of this security is borrowed and. sold at the going market price to generate $B(t_{0},t_{1})^{\mathrm{EUR}}/F_{t_{0}}$ euros. In Figure 6.2f, these euros are exchanged into dollars at the going exchange rate. : In Figure 6.2e, the dollars are used to buy one dollar-denominated bond $\bar{B(t_{0},t_{1})}^{\mathrm{USD}}$  

At time $t_{1}$ these operations would amount to exchanging EUR $100/F_{t_{0}}$ against USD100, given that the corresponding bonds mature at par..  

# 6.2.2.3 which synthetic should one use?  

If synthetics for an instrument can be created in many ways, which one should a financial engineer use in hedging, risk management, and pricing? We briefly comment on this important question.  

As a rule, a market practitioner would select the synthetic instrument that is most desirable according to the following attributes: (1) The one that costs the least. (2) The one that is most liquid, which, ceteris paribus, will, in general, be the one that costs the least. (3) The one that is most convenient for regulatory purposes. (4) The one that is most appropriate given balance sheet considerations. Of course, the final decision will have to be a compromise and will depend on the particular needs of the market practitioner.  

# 6.2.2.4 Credit risk  

Section 6.2.2.1 displays a list of instruments that have similar cash flow patterns to loans and T-bills. The assumption of no-credit risk is a major reason why we could alternate between loans and T-bills in Sections 6.2.2.1 and 6.2.2.2. If credit risk were taken into account, the cash flows would be significantly different. In particular, for loans we would have to consider a diagram as shown in Figure 6.1, whereas T-bills would have no default risks.5  
