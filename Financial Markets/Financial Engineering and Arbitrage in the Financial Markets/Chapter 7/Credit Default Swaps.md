---
tags:
  - corporate_bonds
  - credit_default_swaps
  - credit_derivatives
  - credit_risk
  - floating_rate_bonds
  - no_arbitrage
aliases:
  - CDS
  - Credit Default Swap
  - Default Insurance
  - Protection Contract
key_concepts:
  - Default insurance arrangement
  - No-arbitrage principle
  - Periodic premium payments
  - Protection buyer seller
  - Reference issue default risk
---

# 7.1 CREDIT DEFAULT SWAPS  

More than two-thirds of all credit derivatives trading in the world are credit default swaps which insure the risk of default of a single bond issue or issuer. In this section, we describe the basic transaction, and relate it structurally to the floating rate bond in order to derive the fundamental no-arbitrage relationship for credit derivatives. We then show some common variants of the structure of the credit default swap.  

# 7.1.1 Credit Default Swap  

A credit default swap (CDS) is a default insurance arrangement between two counterparties dressed in a language of swaps. The protection contract is most commonly written on a single bond issue, called the reference issue. The buyer of the default protection, called the buyer, makes periodic payments, called the spreads, on the premium leg of the swap until default or. maturity of the reference issue, whichever comes earlier. The seller of the protection pays a. lump-sum payment only once if and when the default occurs, but nothing otherwise. The swap is typically physically settled to avoid disputes over the post-default value of the reference. bond and has no embedded delivery options. Upon the default, the seller of the protection pays. the principal and the accrued interest in exchange for the receipt of the defaulted bond. On. rare occasions, the two parties may settle the swap in cash with the protection seller paying the difference between the principal plus the accrued interest and the recovery value of the. bond - the recovery value being defined as the after-market price of the defaulted bond.  

Figure 7.1 shows the cash flows of a 3-year credit default swap under two alternative scenarios, one that the reference issuer defaults on the reference bond in year 2 and the other that the bond does not default during the life of the swap..  

![](4d8a0d6b07d748b8cc41db7f8a401781d60743c1875a3a7acb206506af771e27.jpg)  

Figure 7.1 The credit default swap  

If the reference issuer defaults on the bond 2 years into the credit default swap, then the. protection seller pays to the protection buyer the value lost on the bond. At that time, the protection buyer stops making the periodic premium payments. Typically, the premium payments are quarterly, and quoted on a per annum Act/360 basis for dollar bonds (to correspond to a. LIBOR-plus-margin convention).  

# 7.1.2  No Arbitrage: CDS vs Corporate Bond Spread  

Under the assumption of no counterparty risk, i.e. no possibility that the protection seller. himself may default on the credit default swap, the swap is a perfect hedge for a corresponding. par floating rate bond and the premium amounts must be equal to the corporate spread the reference issuer would pay on a floating rate bond with a maturity equal to the maturity of the credit default swap. This is the fundamental no-arbitrage principle of credit derivatives..  

To see this, consider the following strategy. An investor purchases a par floater that pays. LIBOR plus a spread, and finances the purchase by borrowing at LIBOR. At the same time, the. investor buys a default swap. The premium on the default swap must be equal to the corporate spread paid by the issuer to prevent arbitrage, because the strategy is equivalent to buying a par floater paying LIBOR and financing it at LIBOR. If we substitute the term "risk-free rate"' for "LIBOR" in this argument and add a condition that the protection seller is a default-free. sovereign, then the strategy is equivalent to purchasing a default-free par floater and financing. it at a risk-free rate.  

Figure 7.2 shows the cash flows of the strategy under the default and no-default scenarios, excluding the LIBOR financing cost (and repayment of the borrowing) of buying the floater.  

The investor pays the spread on the default swap. He receives LIBOR plus the spread from the bond. Net, his periodic cash flow is equal to LIBOR. If the default occurs, he stops paying. the spread, and stops receiving LIBOR plus spread. His principal is also returned. In cash settlement, he receives the principal minus the recovery value from the protection seller plus the recovery value in the after-market. In the physical settlement, he exchanges the defaulted bond for the principal from the protection seller. The total principal is used to pay off his borrowing. The investor gained or lost nothing.  

![](68c0c2380fe4d2a75d6665776619580cb9d4c6050b6c7eb302f70e4c466e0df1.jpg)  
Figure 7.2  A par floater replication  

If the bond does not default, then the investor receives all the scheduled LIBOR plus the spread payments, spends the spread on protection and LIBOR on financing, and uses the final principal of the bond to pay off his borrowing.  

The argument holds if there are no day-count and payment date discrepancies between floating coupons and swap premium payments, and if defaults occur only on (i.e. right after) the payment dates. If they occur in between, then the interest accruals may make the swap settlement amount slightly different from the amount needed to pay off the borrowing.  

In reality, the credit default premium will be different from the par floater spread to the extent that there is a difference in the credit quality of the reference issuer and the protection seller. If the reference issuer is an AA-rated corporate entity, but the protection seller is a single A-rated broker-dealer, then the credit default premium will be lower than the corporate spread on the floater to compensate for the fact that the guaranteeing counterparty is of a lower credit quality. Actually, the exact pricing of this disparity requires modeling the correlation of the default probabilities of the corporate issuer and the protection seller, covered intuitively at the end of this chapter. The exact valuation relies on the default correlation models of first-to-default baskets tackled in Chapter 10.  

# 7.1.3 Bundled Single-Name Credit Derivatives  

In addition to the credit default swap, holders of corporate bonds or loans have one other way to manage the default risk of their assets. They can enter into a total rate of return swap with a dealer whereby they give up the fixed rate of return on the asset in exchange for a floating rate coupon quoted as LIBOR plus (or minus) a spread. The total rate of return swap is a vehicle for synthetically creating floating rate bonds with default risk. This asset swap spread should in theory be equal to the CDS premium. Often it is not, because the asset swap spread bundles the cost of the protection contract with a repo-financed purchase of the asset. The CDS basis is defined as the difference between the cost of pure insurance and the asset swap margin, or  

$$
C D S b a s i s=C D S p r e m i u m-A s s e t s w a p s p r e a d
$$  

The basis can be positive or negative. The main factor determining the basis is how far from par the bond trades, as that drives the financing cost of buying the asset..  

# 7.1.3.1 The Total Rate of Return Swap  

A total rate of return swap is an off-market interest rate swap in which one counterparty, who typically holds a corporate bond or loan, pays a fixed rate related to, or equal to, the fixed coupon rate of the corporate bond or loan to another counterparty in exchange for a floating rate coupon expressed as LIBOR plus, or minus, an asset swap spread. The maturity of the swap is equal to the maturity of the underlying bond or loan. In the par-in par-out version of the swap, the notional principal on both legs of the swap is equal to the principal of the bond/loan. In the market-in market-out version, the floating leg's notional principal is equal to. the current price of the bond/loan. The objective of the fixed rate payer is to retain the credit exposure of the underlying bond, but swap the interest rate risk of the fixed leg into a near-zero interest rate risk of the floating leg.  

In Figure 7.3, the Kool Kredit Bank has a loan out to ABC on which it receives a fixed rate of return. It enters into a total return swap with a dealer in which it transfers the fixed coupon on the ABC loan to the dealer in exchange for a floating coupon. Kool Kredit does not have to involve ABC in the transaction. The dealer agrees to pay Kool Kredit LIBOR plus a spread. The spread level depends on the current value of the loan.  

In the par structure of this asset swap, the floating leg's notional principal is set to be equal to the fixed leg's principal. Yet if the bond does not currently trade at par, then the present values of the two legs, including the principal exchanges at the end, are not equal. The floating leg's PV is equal to par, while the fixed leg's PV is equal to the value of the bond. The spread over LIBOR is determined to make the two PVs balance. In the market structure of this asset swap, the floating leg's notional principal is set to equal the current value of the underlying bond or loan which, in turn, is equal to the present value of the fixed leg. The mismatch of the principals results in a net payment at maturity to settle the principal exchange (similar to currency swaps).  

![](9fa6703575ed66b1800d8459da648db0bc220aa3fabeca187f383ff8ee17e17b.jpg)  
Figure 7.3 The total rate of return  

# 7.1.3.2 CDS Basis and No Arbitrage between CDSs and Asset Swaps  

Credit default swap spreads and asset swap spreads are tied together through a no-arbitrage. condition. The CDS exposure can be replicated synthetically with the use of a total rate of return asset swap and a repo purchase of the underlying bond. To see this, let the coupon on the underlying bond or loan be denoted as the equivalent maturity Treasury plus a corporate bond spread, or. $T+c$ . Let the interest rate swap spread be denoted by. $s$ . Thus a zero-PV (on-market) interest rate swap is quoted as fixed. $T+s$ against a floating LIBOR $L$ flat (no) spread). The repo rate on purchasing the corporate bond is quoted as LIBOR minus the repo premium, or $L-\rho$ . Let us assume that there is no haircut on the repo (i.e. no difference. between the value of the securities purchased in the repo and the money received). We will consider the following numerical values for our example. The underlying bond has 5 years left to maturity and 5-year Treasuries trade at $T=4\%$ yields. Five-year swap spreads are at. $s=0.5\%$ , and swaps are quoted at. $T+s=4.5\%$ . The underlying bond is a. ${\mathrm{BBB+}}$ rated bond with a coupon and the yield to maturity equal to. $T+c=5\%$ . Consider the following simultaneous transactions:  

Term repo: Borrow 100 at a floating rate $L-\rho$ and buy the ${\tt B B+}$ bond for 100. When the bond matures, it will be redeemed for par and the borrowing will be repaid. Pay fixed $T+s=4.5\%$ on an interest rate swap to receive floating $L$  

The cash inflows are: $T+c=5\%$ from the bond and $L$ from the swap. The cash outflows are: $L-\rho$ on the repo financing and $T+s=4.5\%$ on the swap. Net the cash inflow is:  

$$
T+c+L-(L-\rho)-(T+s)=c-s+\rho
$$  

which is equal to a fixed periodic spread of $0.5\%$ if the repo is non-special and $\rho=0$  

If the bond defaults and trades at the recovery rate $R$ , the funds borrowed on the repo (100) are immediately repaid. The net cash outflow at the time is $100-R$ . The synthetic exposure of the two transactions is the same as that of a protection seller in a CDS: a receipt of a fixed periodic premium for a one-time payment of $100-R$ if and when the bond defaults.. Therefore the CDS swap should trade close to $c-s+\rho$ . The forces that cause deviations from the no-arbitrage condition include to a lesser extent special repo conditions and primarily funding cost differentials between protection buyers and sellers. Highly creditworthy entities that can fund themselves at sub-LIBOR levels can use their funding cost advantage to hold assets to swap out of them, or in conjunction with protection purchases.  

# 7.1.3.3Credit-Linked Notes  

A credit-linked note is a debt security whose principal repayment depends on the value of a. third-party reference security. In case of third party default, the defaulted security recovery. value is passed on to the investor in lieu of principal. The enhanced interest rate of the credit-. linked note reflects the implicit sale of credit protection by the investor. The issuer of the note is typically a trust set up by a bank arranging the sale of the note. The trust receives premiums for the sale of the protection to the bank. The premiums subsidize the coupon of the. note issued to the investors. The trust uses the proceeds from the sale of the note to invest in risk-free securities to guarantee the principal of the note. If the third party does not default, that principal is returned to the credit-linked note holder. If the third party defaults, the principal is exchanged for the recovery value of the reference security with the protection buyer, and only the recovery value is returned (early) to the credit-linked note holder.  

![](200f9637ed5c2100ed0ebffbc3e7b8647358d2b5befe21b42bf9cb1a03464f7a.jpg)  
Figure 7.4A credit-linked note  

The investor gains a much enhanced interest rate, but bears all the risk of default. The arranging bank acquires protection for its loan or bond portfolio. In the case of default of the underlying issuer, the bank receives the excess of the value of the securities held by the trust over the recovery value of the reference security.  

The credit-linked note bundles a credit default swap with a standard bond obligation. The. credit protection premium paid by the arranging bank in Figure 7.4 is passed on to the investor. in the form of an enhanced coupon. The protection payout is passed from investors to the bank. at redemption. If there are no credit events associated with the reference security, the investor gets a periodic coupon and par at maturity. A synthetic collateralized debt obligation (CDO) tranche certificate is an example of a credit-linked note..  

# 7.1.3.4 Credit Spread Options  

Credit spread options pay out the yield differential between defaultable securities and reference. benchmarks. The payout is not contingent on a credit event. Most credit spread options are structured as put options on the price. The holder of a credit spread option has the right to sell a particular corporate bond at a contingent strike price. The strike price is computed to be the value the corporate bond would need on the expiry date so that its yield to maturity would equal the yield to maturity on the reference default-free security plus a spread strike. For example, the buyer of a spread option on ABC's 5-year note struck at a spread strike of. 50 bp over the 5-year US Treasury note will face either of two possibilities on the expiration date. If the spread between the yield to maturity on the ABC bond and the Treasury note is less than 50 bp, the option expires worthless. If the spread exceeds. $50~\mathrm{bp}$ , the ABC bond is sold to the option writer. The price he receives is equal to the present value of the cash flows from the ABC bond discounted at the yield equal to the 5-year Treasury yield plus 50 bp..  

To illustrate this numerically, suppose 1 year ago we purchased a 1-year European option on the spread between ABC's 6-year bond paying a $5\%$ coupon semi-annually and the 5-year US Treasury struck at 55 bp. The face amount of the option was $\$100$ million. At that time, the  

ABC bond yielded $5.75\%$ (semi) to price at 96.2392. The reference Treasury from which we were going to calculate the yield spread between the two bonds had not been issued. The then current 5-year Treasury paying a $5.25\%$ semi-annual coupon, yielded $5.23\%$ and was priced at 100.1019. The option was described as 3 bp out-of-the-money since the spread at the time of the option purchase was 52 bp. Recently, the US Treasury auctioned off a new 5-year note with a coupon of $5.125\%$ . This note will be used to determine the payoff on the spread option.  

Suppose the now 5-year ABC bond is yielding $5.68\%$ . The current market price is 97.0759. The new 5-year Treasury is yielding $5.04\%$ and is priced at 100.3716. The yield spread between the two bonds at. $64~\mathrm{bp}$ is higher than the strike spread of 55 bp. We will exercise our option to sell the bond at 55 bp over Treasuries, that is, at a yield of $5.59\%$ . Computing the price of the ABC bond at that yield we obtain 97.4571. Since we can buy the bond for 97.0759 on the open market, the payoff on the option to us is:  

$$
(97.4571-97.0759)/100\times\mathbb{5}100,000,000=\mathbb{5}381,153
$$  

Suppose instead that the now 5-year ABC bond is yielding $6.23\%$ . The current market price. is 94.7846. The new 5-year Treasury is yielding $5.59\%$ and prices to 97.9958. The yield spread. between the two bonds again at 64 bp is higher than the strike spread of 55 bp. We will exercise our option to sell the bond at. $55~\mathrm{bp}$ over Treasuries, that is, at a yield of. $6.14\%$ . Computing the price of the ABC bond at that yield, we obtain 95.1551. Since we can buy the bond for 94.7846 on the open market, the payoff on the option to us is:  

$$
(95.1551-94.7846)/100\times\S100,000,000=\$370,528
$$  

The option payout in the two scenarios is not identical, but is almost the same. This is because. it can be viewed as purely a bet on the spread between the two bonds grossed up by the duration. of the bond under consideration. For the last scenario, the duration of the bond computed by blipping the yield from 6.14 to 6.15 is 4.1254. The payout on the option is based on 9 bp. (64 - 55). So using the duration approximation, the total payout is:.  

$$
0.041254\times9\times\S100,000,000=\S371,289
$$  

Nowhere in the calculations did we use the actual price of the Treasury. Comparing the two examples, we can see that the payout is independent of whether interest rates in general go up or down. The relevant factor is the yield spread between the bond and the reference risk-free security. Spread options are sometimes written by fixing the duration multiplier and defining the payout explicitly as the difference in yields.  

The fundamental difference between credit spread options and other credit derivatives is that credit events do not explicitly drive the payout, but are implicitly incorporated in the payout through a spread differential which, in turn, depends on the probability of default of the underlying bond.  
