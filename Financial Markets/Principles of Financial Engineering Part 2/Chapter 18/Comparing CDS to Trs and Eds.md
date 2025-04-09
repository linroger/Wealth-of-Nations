# 18.8 COMPARING CDS TO TRS AND EDS  

To appreciate the nuances of CDS it is helpful to compare them to different but related products.  

# 18.8.1 TOTAL RETURN SWAPS VERSUS CREDIT DEFAULT SWAPS  

We encountered total return swap (TRS) applications in Chapter 4 and discussed equity swaps as. an example of TRS principle. A TRS trades default, credit deterioration, and market risk simultaneously. Therefore, unlike CDS, TRS are not a pure credit derivative..  

It is instructive to compare them with CDSs. In the case of a CDS, a protection buyer owns a bond issued by a credit and would like to buy insurance against default. This is done by making constant periodic payments during the maturity of the contract to the protection seller. It is similar. to, say, fire insurance. A constant amount is paid, and if during the life of the contract the bond issuer defaults, the protection seller compensates the protection buyer for the loss and the contract. ends. The compensation is done by paying the protection buyer the face value of, say, 100, and. then, in return, accepting the delivery of a deliverable bond issued by the credit. In brief, CDSs are. instruments for trading defaults only.27  

A TRS has a different structure. Consider a bond or any arbitrary risky security issued by a credit. This security makes two types of payments. First, it pays a coupon interest. Second, there will be associated capital gains (appreciation in asset price) and capital losses (depreciation in asset price), which include default in the extreme case. In a TRS, the protection seller pays any depreciation in the asset price during periodic intervals to the protection buyer. Default is included in these payments, but it is not the only component. In general, assets gain or lose value for many reasons, and this does not mean the issuer has defaulted or will default. Nevertheless, the protection seller will compensate the protection buyer for these losses as well.  

However, in a TRS, the protection seller's payments will not stop there. The protection seller will also make an additional payment linked to LIBOR plus a spread.  

The protection buyer, on the other hand, will make periodic payments associated with the appreciation and the coupon of the underlying asset. Normally, asset prices appreciate and pay coupons more often than decline, but this is compensated by the LIBOR plus any spread received..  

The TRS structure is equivalent to the following operation. A market participant buys an asset, $S_{t},$ and funds this purchase with a LIBOR-based loan. The loan carries an interest rate, $L_{t_{i}}$ , and has to be rolled over at each $t_{i}$ The market participant is rated A and has to pay the credit spread $d_{t_{0}}$ known at time $t_{0}.S_{t}$ has periodic (coupon) payouts equal to $c$ . The market participant's net receipts at time $t_{i+1}$ would, then, be the following:  

$$
\left(\Delta S_{t_{i+1}}+c\right)-\left(L_{t_{i}}+d_{t_{0}}\right)S_{t_{0}}\Delta
$$  

where $\Delta S_{t_{i+1}}$ is the appreciation or depreciation of the asset price during the period, $\Delta=[t_{i},~t_{i+1}]$ The $c$ is paid during $\Delta$ . The payments are in-arrears.  

A TRS swap is equivalent to this purchase of a risky asset with LIBOR funding. Except, in this particular case, instead of going ahead with this transaction, the market participant can simply sign a TRS with a proper counterparty. This will make him or her a protection seller. Banks may prefer. these types of TRS contracts to lending to market practitioners.  

# 18.8.2 EDS VERSUS CDS  

Equity default swaps (EDS) are strictly speaking equity derivatives, but they have similarities with CDS. EDS have been marketed by dealers with mixed success thus far.28 The EDS emulate CDS. In a CDS, the reference asset is a bond, and the protection is provided against the default of other credit event. In an EDS, the reference asset is a company's stock, and protection is provided against a dramatic decline in the company's stock price..  

An EDS is "exercised" when a company's stock price $S_{t}$ falls below a prespecified barrier $H$ Normally this barrier will be $30-40\%$ below the current stock price level. If $S_{t}<H$ happens, then an "equity event' similar to a credit event takes place.  

If a credit event occurs, the EDS terminates, and the protection seller makes a specified payment to the protection buyer. The payment is calculated as.  

$$
\mathrm{notional~amount}(1-\mathrm{recovery~rate})
$$  

Note, however, that hitting an equity barrier. $H$ , no matter how distant it is, is more likely than a. credit event. After all, a company's stock price can fall dramatically without the company going bankrupt. An EDS shares similarities with CDS and with options. An EDS is similar to a deep outof-the-money, long-dated American digital put. However, there is a difference in that the option premium is paid in installments and these stop when the option is exercised. A better analogy is between the EDS and the CDS. The reason is that typically when a CDS is triggered the stock price of the underlying typically dramatically collapses and might fall to zero at the same time as the reference asset, that is the bond, drops in value. One of the advantages of EDS over CDS is that the trigger events are less ambiguous. It is generally clear whether a stock price has fallen below a certain threshold, while in a CDS there is some ambiguity about what constitutes a credit event or. default, as we will see in our discussion of sovereign CDS below, for example..  

Again, similar to CDSs, dealers can, and have tried to, put together CDOs of the EDSs. Such CDOs can get rated. Normally, however, it is difficult for dealers to get a big enough tranche of such a CDO rated higher than A.29  

It is worth adding that the EDS structure is very similar to a deep out-of-the-money put option written on the stock. In both cases there is a barrier, namely the strike price in the case of the option, such that the option buyer receives a cash payment. The major difference is perhaps the expiration date of the EDS which can be much longer.  
