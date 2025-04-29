---
tags:
  - american_options
  - futures_contract
  - futures_options
  - market_conventions
  - option_pricing
aliases:
  - Eurodollar futures
  - Futures Option
  - Options on Futures
  - T-bond futures
key_concepts:
  - European call/put bounds
  - Futures option underlying futures
  - Options on spot assets
  - Payoffs and trading strategies
  - Price quotes and delivery
---
# Options on Futures  

# Aims  

• To analyse futures options, that is, options contracts where the underlying asset is a futures contract.   
• To explain price quotes, delivery and settlement procedures.   
• To establish upper and lower bounds for the price of European calls and puts on futures.   
• To examine payofs and trading strategies using futures options.   
• To examine the relative merits of options on spot assets and options on futures contracts.  

A futures option is an option where the underlying asset to be delivered is a futures contract. The futures contract itself could, for example, be written on T-bonds, Eurodollar interest rates, spot-FX rates or commodities such as corn or oil. Most futures options are American style options. The main advantage they have over options on the spot asset is that they deliver a futures contract, which is highly liquid and easy to close out at low cost. The latter can sometimes make them more attractive than using options on the underlying spot asset itself.  

# 20.1 MARKET CONVENTIONS  

A long American call (put) option on a futures contract gives the holder the right, but not the obligation, to buy (or sell) a futures contract at the strike price, up to and including the maturity date of the option.  

Some of the most popular futures options are on T-bond and T-note futures (CBOT), on Eurodollar futures (CME), on EURIBOR futures (Euronext-LIFFE) and on the S&P 500 futures contract. Other futures options which are also actively traded, include those written on futures contracts on the Japanese yen (CME), the euro (CME), the Canadian dollar (CME), crude oil and other oil products (NYMEX), gold (CMX), corn, soybeans, cotton, and sugar (CBOT).  

When you buy a call or put futures option you must immediately pay the full option premium (invoice price). At maturity, a futures option delivers a futures contract which itself has a maturity date. Futures options are referred to by the month in which the underlying futures contract matures (and not by the expiration date of the option itself). However, the expiration date of a futures option is usually on, or a few days before, the maturity date of the underlying futures contract.  

For example, a futures option on the S&P 500 futures index expires on the same day as the futures contract. However, the T-bond futures option expires in the month prior to the month that ‘names’ the option contract. For example, the October T-bond futures option expires in September and delivers a T-bond futures contract which expires in October. CME currency futures options expire two business days prior to the expiration of the underlying futures contract. Where the contracts on the option and the deliverable futures contract expire simultaneously $F_{T}=S_{T}$ , so the futures option is analytically equivalent to an option on the spot asset, but with cash settlement.  

The closing prices of futures options are available for diferent strike prices $K$ and expiration months. For example, suppose on 1 January, the US T-bond October-call futures option (CBOT) for expiration in September, has a strike price of $K=96$ per $\$100$ nominal of T-bonds) and a quoted call premium of 2-39. The $\cdot_{39},$ represents 39/64th, so the call premium is $C=2(39/64)\%=2.609375\%$ , with invoice price:  

Invoice price of T-bond futures option $\b=$ 0.02609375 $\$100,000$ 609.38  

At expiration (in September), the October-call futures option delivers one T-bond futures contract with a contract size of $\$100,000$ .  

# 20.1.1 Expiration and Delivery  

Let us now consider what happens on the expiration date $t\equiv T$ of a European futures option or when an (American) futures option is exercised $(t\leq T)$ . If a long call option is exercised, the holder acquires a long position in the underlying futures contract (with a delivery price of $K$ ) plus a cash amount equal to $F_{s e t t l e}-K$ , where $F_{s e t t l e}$ is the futures settlement price at the end of the previous day. However, it turns out (see Example 20.1) that exercising the call option at $t$ , (where $t\equiv T$ for a European option) results in a payof equivalent to:  

$$
\mathrm{Effective\payofffrom\call}=\operatorname*{max}(0,F_{t}-K)
$$  

where $F_{t}$ is the futures price at the time of exercise of the option. Since the options are American, exercise can take place at any time $t>0$ and not just at $T$ .  

# EXAMPLE 20.1  

# Call Payoff  

Suppose at 11 a.m. on 15 August the T-bond futures price is $F_{t}=103$ (per $\$100$ nominal of deliverable bonds). The price of the call futures option is 1-08 $(1~8/64=1.125\%$ of the principal). The payof to a call option on T-bond futures with $K=100$ is:  

$$
P a y o f f f r o m~c a l l=(103-100)(\S100,000/100)=\S3,000
$$  

This payof arises as follows. On 15 August it is actually the settlement price for the futures the night before (14 August) $F_{s e t t l e}=102.9$ which is used. So the cash payof from the option is actually based on $F_{s e t t l e}-K$ . But on 15 August you also take delivery of one futures contract which can immediately be closed out (in the futures market) at $F_{t}-F_{s e t t l e}$ , hence:  

$$
f f=O p t i o n p a y o f f+P r o f i t o n f u t u r e s=(F_{s e t l e}-K)+(F_{t}-F_{s e t t l e})=F_{t}-K
$$  

You do not have to close out your long futures contract if you do not wish to do so, but the value of your cash payof of $F_{s e t t l e}-K$ plus the mark-to-market value of your long futures position $F_{t}-F_{s e t t l e}$ , is equal to $F_{t}-K=\S3,000$ . The invoice price of the call futures option is 11.25 $(=0.01125\times\S100,000/100)$ .  

If the investor decides not to close out the futures contract she has to pay the initial margin on the long futures position. When the call is exercised, the writer of the call has $F_{s e t t l e}-K>0$ deducted from her margin account and also has to provide any additional margin requirements on the futures – she ‘inherits’ a short position in T-bond futures, when the option is exercised. If on the expiration date $F_{T}<K$ , then the call is not exercised, and the writer retains the call premium.  

If a long put futures option is exercised, the holder acquires a short position in the underlying futures contract (with a delivery price of $K$ ) plus a cash amount equal to $K-F_{s e t t l e}$ . For example, exercise of the September-100, T-bond put-futures option results in a short position in T-bond futures at a ‘delivery price’ of ${\mathrm{K}}=100{\mathrm{\Omega}}$ together with a cash amount of $K-F_{s e t t l e}$ . Again, the position is immediately marked-to-market1 which for a short futures position is $-(F_{t}-F_{s e t t l e})$ . The payof to the put if it is exercised is $K-F_{s e t t l e}-(F_{t}-F_{s e t t l e})$ , hence:  

$$
{\mathrm{Payofffom~Put}}=\operatorname*{max}(0,K-F_{t})
$$  

At expiration, the writer of a put ‘inherits’ a long position in the futures at a delivery price of $K$ and the position is immediately marked-to-market. Writers of calls or puts, must post margin payments on the options contracts (as with options on other cash-market assets) and the option writer’s margin account is marked-to-market.  

Nearly all futures options are American and hence early exercise is possible. For American style futures options it is often not possible to derive an analytical (closed form) solution, (e.g. Black–Scholes equation as for certain European style options) – hence, to price futures options may require numerical techniques such as the binomial option pricing model (BOPM – see Chapters 21–23) and Monte Carlo simulation (MCS – see Chapter 26).  

# 20.2 PRICE BOUNDS ON EUROPEAN FUTURES OPTIONS  

If a quoted futures option price is below the lower bound or above the upper bound (as set out below) then there are arbitrage profts to be made. Establishing these bounds only requires the assumption of a positive risk-free (nominal) rate of interest. The easiest way to establish the no-arbitrage bounds for European futures options is to use the put–call parity relationship (see Chapter 25)2:  

$$
P=C+(K-F)e^{-r T}
$$  

where we assume the option and the futures mature at the same time (and the call and put, both have the same strike and time to maturity). Because the price of the put cannot be negative, then Equation (20.2) gives a lower bound for the call futures price:  

$$
\begin{array}{l}{C+K e^{-r T}\geq F e^{-r T}}\\ {\qquad}\\ {C\geq(F-K)e^{-r T}}\end{array}
$$  

Similarly, the price of the call cannot be negative, then Equation (20.2) gives a lower bound for the put futures price:  

$$
K e^{-r T}\leq F e^{-r T}+P
$$  

$$
P\geq(K-F)e^{-r T}
$$  

Since the call and put cannot be worth less than zero the lower bounds for European futures-options are:  

$$
\begin{array}{r}{C\ge\operatorname*{max}[(F-K)e^{-r T},\quad0]\ }\\ {\ }\\ {P\ge\operatorname*{max}[(K-F)e^{-r T},\quad0]}\end{array}
$$  

A European call futures option gives the holder the right to take delivery of a futures contract and the call can never be worth more than the current futures price. Hence the upper bound for European call futures options is $C\leq F$ . For a European put futures option the minimum value is $K$ at maturity $T_{\mathbf{\delta}}$ , so today the put cannot be worth more than $P\leq\bar{K}e^{-r T}$ .  

# 20.3 TRADING STRATEGIES  

The popularity of futures options is due to:  

• Greater liquidity in the futures market than in the spot (cash) market. • Transactions costs using options on stock index futures are lower than for options on the underlying stock indices. This is also true for futures on agricultural products and metals, since these options deliver a futures contract which can be closed out at low cost. In contrast, for options on the spot asset, delivery of the underlying asset may be costly or inconvenient.  

Since futures and spot prices move closely together, a long call on a futures contract would constitute a speculative (open) position, where the investor expects a rise in futures prices. If the speculator expects a fall in futures prices, she would proft by purchasing put futures contract. We consider each of these in turn.  

# 20.3.1 Long Call  

The proft at expiration is:  

$$
\begin{array}{r l}&{\Pi=\operatorname*{max}(F_{T}-K,0)-C}\\ &{\quad=-C\quad\mathrm{if}F_{T}\leq K}\\ &{\quad=F_{T}-K-C\quad\mathrm{if}F_{T}>K}\end{array}
$$  

with a breakeven futures price of $F_{B E}=K+C.$ . For a call option on the futures stock index with $K=475$ , and the value of an index point $z=\$250$ , Figure 20.1 gives the possible outcomes:  

The call premium is $C=7$ and the invoice price of one contract is $\$1,750$ $(=\$250C)$ . The breakeven point is $F_{B E}=K+C=475+7=482.$ If, at expiry, $\mathrm{F_{T}}=485$ $\ 、>K=475$ , then the net proft per contract is :  

$$
\Pi=\left(F_{T}-K-C\right)\S250=\left(485-475-7\right)\S250=\S750
$$  

If $F_{T}\leq K$ , then the call expires worthless and with $C=7$ , the invoice cost per contract is $\$1,750$ .  

![](edc8e6f1d5a9345cca04ef530918b5c206790885969645229530c8845717c772.jpg)  
FIGURE 20.1 Call on stock index futures contract  

# 20.3.2 Long Put  

The payof at maturity is:  

$$
\begin{array}{r l}&{\Pi=\operatorname*{max}(K-F_{T},0)-P}\\ &{\quad=K-F_{T}-P\quad\mathrm{if}F_{T}<K}\\ &{\quad=-P\quad\mathrm{if}F_{T}\geq K}\end{array}
$$  

and the breakeven futures price is $F_{B E}=K-P$ . If $P=5$ then the invoice price is $\left(\$250\right)P=$ $\$1,250$ . Figure 20.2 gives the proft profle at expiry. If $F_{T}=462$ and $K=475$ then the proft is $\left(K-F_{T}-P\right)\S250=8\left(\S250\right)=\S2{,}000$ .  

Note that if the underlying futures contract matures at the same time as the (European) option then $F_{T}=S_{T}$ and the European futures option and the European option on the spot asset (with the same strike) are equivalent – and they both have the same (call and put) premia.  

![](9f58a0f39621892c2b3544872caca691eef81c8599f057d714954e7985eebc59.jpg)  
FIGURE 20.2 Put on stock index futures contract  

# 20.3.3 Covered Call  

Holding a long futures position is highly risky – if the futures price falls you lose money. You can mitigate some of this potential loss if you write a call futures option, since you then receive the call premium. However, this does not eliminate much of the potential downside loss if the futures price falls. Consider a covered call using futures options, where the underlying futures contract is on a stock index (e.g. the S&P 100 or S&P 500).  

# Covered Call Long Futures $+$ Written Call on Futures Option  

The payof profle for long-futures $\{+1,+1\}$ plus written call $\{0,-1\}$ gives the $\{+1,0\}$ payof for a covered call (see Figure 20.3). If the futures price falls (below $K=475$ ), the long call expires worthless, so the writer of the call does not have to pay anything at $T_{\mathbf{\delta}}$ . The losses on the long futures position $F_{T}-F_{0}$ are (partially) ofset by receipt of the call premium, $C=8$ . Hence, downside losses from a covered call are slightly less than when holding only the long futures.  

At $T_{:}$ , if the futures price rises (above $K$ ), the long futures is closed out at a prof $\mathbf{\Psi}:=F_{T}-F_{0}$ but the long call is in-the-money, so the written call makes a loss $-(F_{T}-K)$ . Overall, payof from the long futures plus the short call cancel each other out, so the holder of the covered call merely retains the call premium.  

The proft from the covered call is:  

$$
\begin{array}{r l}{\Pi=F_{T}-F_{0}-\operatorname*{max}\left(F_{T}-K,0\right)+C}&{}\\ {=K-F_{0}+C}&{\mathrm{if}F_{T}>K(\mathrm{independent}\mathrm{of}F_{T})}\\ {=F_{T}-F_{0}+C}&{\mathrm{if}F_{T}\leq K(\mathrm{depends}\mathrm{on}F_{T})}\end{array}
$$  

![](610828636de1259c04d902739c2731fb081323a13d424e47ee4891af1fa128e6.jpg)  
FIGURE 20.3 Covered call  

Note that the outcome for the futures price $F_{T}$ only afects the covered call payof when $F_{T}\leq K$ . The breakeven futures price (for $F_{T}\leq K)$ is $F_{B E}=F_{0}-C.$ . Figure 20.3 gives the proft profle on the covered call for Example 20.2.  

# EXAMPLE 20.2  

# Covered Call Futures Option  

Suppose $F_{0}=477,K=475$ and the call futures option has $C=8$ . What is the payof to a covered call, if the futures price at expiry of the option is either $F_{T}=490$ or $F_{T}=460$ and the value of an index point is $\$250?$ (see Figure 20.3).  

Fo $\mathrm{r}F_{T}=490>K=475$ , the long call is exercised and the call writer pays $F_{T}-K=15$ . But the long futures can be closed out at a proft of $F_{T}-F_{0}=13$ . The net proft is $^{-2}$ plus the call premium of 8, that is:  

$$
\Pi=K-F_{0}+C=(475-477)+8=6{\mathrm{~(per~co}}
$$  

giving an overall proft of $\$1,500$ . If $F_{T}=460<K=475$ , the breakeven futures price is $F_{B E}=F_{0}-C=477-8=469.$ The long call is not exercised and the call writer receives the call premium of $C=8$ . However, there is a loss on the long futures position of $F_{T}-F_{0}=460-477=-17$ and hence a net proft of $8-17=-9$ , that is:  

$$
\Pi=F_{T}-F_{0}+C=460-477+8=-9
$$  

All the options strategies we discussed in Chapter 17 with respect to options on the underlying spot asset (e.g. spreads, straddles, condors etc.) can be undertaken with futures options.  

# 20.4 SUMMARY  

• For a futures option the underlying deliverable asset is a futures contract. The futures contract that is delivered usually has a maturity date slightly later than the expiration date of the futures option.   
• A call futures option, is an option to take delivery of a futures contract (i.e. go long the futures) at a delivery price $K$ , at expiration of the option. The payof to a long call option on a futures contract is max $(F_{T}-K,0)$ .   
• A put futures option, is an option to deliver a futures contract (i.e. go short the futures) at a delivery price $K$ , at expiration of the option. The payof to a long put option on a futures contract is max $(K-F_{T},0)$ .   
• We can establish upper and lower limits for call and put premia on European futures options. If quoted options prices lie outside these bounds then risk-free arbitrage profts can be made.   
• The most popular futures options are on US T-bond and T-note futures (CBOT), on Eurodollar futures (CME), and the Euro-LIBOR contract (Euronext-LIFFE), as well as on futures contracts on the major currencies (Euro, Japanese yen, Canadian dollar, on CME). Options on futures contracts on commodities, for example, crude oil and other oil products (NYMEX), gold (CMX) and corn (CBOT) are also actively traded.   
• Futures options are often used rather than options on the underlying asset itself. This is because at maturity of the option the underlying futures contract can be easily closed out at relatively low transactions costs.  

# EXERCISES  

# Question 1  

What is a futures option?  

Question 2 In January, a June-futures option is purchased. Does the option expire in June?  

Question 3 When does the October-futures option on the S&P 500 index expire?  

# Question 4  

A long call futures option on T-bonds is exercised but the futures contract is not closed out. What happens to the trader holding the long call?  

Question 5 If you exercise a call futures option by cash-settling the option contract, what is the cash payof?  

# Question 6  

A T-bond call futures option with expiration date in September has a strike price of $K=96$ and a quoted call premium of 2-60. The contract size is $\$100,000$ . What is the invoice price of the call futures option?  

# Question 7  

Why might you hedge your future heating oil purchases using a call futures option on heating oil rather than a call option on (spot) heating oil (itself)?  