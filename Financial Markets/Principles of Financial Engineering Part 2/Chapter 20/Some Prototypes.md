# 20.4 SOME PROTOTYPES  

In this section, we discuss some typical fixed-income structured products and their engineering in detail using the tools previously introduced. We consider three typical structured products that are representative.  

# 20.4.1 THE COMPONENTS  

In order to engineer fixed-income structured products, the market practitioner will need a small number of components. These are  

1. The relevance discount curve $B(t_{0},t_{i})$ in a certain currency. This will be used to discount future "expected" cash flows.12 2. A relevant forward curve in the same currency. This could be a forward LIBOR curve or a forward swap curve. Obviously, this can be obtained from the discount curve using relations such as13  

$$
(1+F(t_{0},t_{i},t_{k})\delta)=\frac{B(t_{0},t_{i})}{B(t_{0},t_{k})}\quad i\le k
$$  

This is equivalent to needing a market for vanilla swaps, i.e., a tradeable swap curve.  

3. A market for CMS, since the structurer may want to receive or pay a floating rate that can be any point of the yield curve. A fixed CMS rate will be paid against this.14  

4. A market for (Bermudan) swaptions if the structure is callable.  

5. A market for caps/floors if the structure is of range accrual type.  

We now show how some prototypes for fixed-income structured products can be manufactured using these components. The prototypes we discuss are exotics in the sense that the structurer cannot buy the note from some wholesale market and then sell it. The structurer has to manufacture the note. In other words, they are exotics because one side of the market does not exist and the structurer has to know how to price and hedge the product in-house..  

# 20.4.2 CMS-LINKED STRUCTURES  

There are (at least) two kinds of CMS-based products. Some link the coupon to a CMS rate. This would be similar to a floating rate note, but the floating rate would be a long-term rate this time.. The second kind will be linked to a CMS spread. An investor buying CMS spread-linked structures will not be affected by parallel shifts in the yield curve. Rather, the buyer will be affected by. the slope of the yield curve. Depending on whether the curve flattens or steepens, the buyer of the spread notes would benefit.  

A note linked to a CMS rate enables investors to benefit from shifts in the long or short end of the yield curve over prolonged periods of time. The note pays a fixed coupon which goes up as the short end of the yield curve shifts upward over the lifetime of the product.15 If made callable, the investor also receives enhanced returns. This is one of the most common types of structured fixedincome products. A straightforward example is shown below..  

# EXAMPLE: A CMS-LINKED NOTE  

Issuer: Bank ABC Tenor: 5 years Principal: Guaranteed at maturity at $100\%$ Coupon: Year 1: $4.00\%$ Year 2: CMS $10+2.5\%$ Year 3: CMS $10+2.5\%$ Year 4: CMS $10+2.5\%$ Year 5: CMS $10+2.5\%$ where CMS 10 refers to the 10-year constant maturity swap rate. Call: Callable on each counon date  

Suppose an institutional investor expects 10-year rates to rise successively during the next 5 years. This would be equivalent to five consecutive shifts in the long end of the yield curve. Then the note provides a way to take exposure to this risk. We now discuss how CMs-linked products can be engineered using standard tools in fixed-income markets.  

# 20.4.3 ENGINEERING A CMS-LINKED NOTE  

In this section, we engineer a straightforward CMS-linked note. Suppose an investor has "a view" concerning the yield curve. For example, he or she expects the long end of the yield curve to shift up gradually during the next 5 years. For such an investor, the structurer would like to put together. a portfolio of elementary assets that generates the promised risk-return characteristics of the relevant CMS-linked note with maturity $T=5$ years. The example discussed above provides a good framework. For simplicity we assume annual interest payment dates. How do we engineer the. CMS-linked note shown above?  

1. First we select a CMS rate. For example, let the CMS rate be the floating rate of an $m$ -period swap observed at every $t_{i}$ (in-advance) and paid at time $t_{i+1}$ (in arrears). There is no harm in thinking that $m=10$ years.   
2. Next we manufacture the high, known, first-year coupon $c_{t_{0}}$ . There is no harm in thinking that $c_{t_{0}}=5\%$ as in the above case. The question is, of course, how to manufacture such a high. coupon. This value will be determined during pricing.  

3. Next, offer a "floating"' coupon for the following 4 years of the form  

$$
c_{t_{t}}=\mathrm{cms}_{t_{i}}^{m}+\alpha_{t_{0}}^{t_{i}}
$$  

where $\mathrm{cms}_{t_{i}}^{m}$ is the CMS rate of period $t_{i}$  

4. $\alpha_{t_{i}}^{t_{i}}$ will be known constants at time. $t_{0}$ and will have to be determined during the pricing. Below we consider two different formulations for this term.   
5. Make the note callable at call dates $t_{1},t_{2},t_{3}$ and $t_{4}$  

First, some general observations. The first-year coupon needs to be constant, since even with. floating rate instruments the first coupon is always known. The investor is taking a position on. "floating" rates, but the first floating rate will be observed at the purchase date. Second, the note is. made callable. The structurer is making the investor sell an option, so that the returns can be enhanced by this option's premium. Third, the option is of Bermudan style, so it can be exercised four times at any of the four future dates. This option would naturally be more expensive than a vanilla swaption and hence the investor can be better compensated..  

# 20.4.3.1 A contractual equation  

Now we can put together a replicating portfolio, i.e., obtain a contractual equation for this note.  

First, start with the floating CMS coupons. $\mathrm{cms}_{t_{i}}^{m}$ . How can the structurer pay such coupons to. the investor?16 Here the answer is straightforward. The structurer gets into a 5-year receiver CMS at time $t_{0}$ .We assume that in this CMS the floating CMS rate is exchanged against a floating LIBOR rate. In this swap the first-year coupon is fixed, but at every. $t_{i:}$ $i=1$ , 2, 3, 4 the going CMS rate $\mathrm{cms}_{t_{i}}^{m}$ will be received by the structurer and that period's LIBOR. $L_{t_{i}}$ will be paid. The structurer will pass the. $\mathrm{cms}_{t_{i}}^{m}$ to the investor. So part of the coupon has now been constructed. This situation is shown in Figure 20.9. The source of the LIBOR payments will be discussed later.  

What would $\alpha_{t_{i}}$ represent then? Calculate the premium of a 5-year Bermudan swaption-call it. $C_{t_{0}}$ . This swaption is on the CMS rate and can be exercised four times during the period $[t_{0},T]$  

Premium $C_{t_{0}}$ from 5-year Bermudan option used to enhance coupon  

![](c792d40d4ca4a3396cf52e8b1ab6236d53a2476f6f7afe347c5bc9d045bab02c.jpg)  

# FIGURE 20.9  

CMS-linked note.  

annually at each $t_{i},$ $i=1$ , 2, 3, 4, 5. Allocate this premium to the four future years by choosing the $\alpha_{t_{0}}^{t_{i}}$ such that,  

$$
C_{t_{0}}=B(t_{0},t_{1})~\alpha_{t_{0}}^{t_{1}}+B(t_{0},t_{2})~\alpha_{t_{0}}^{t_{2}}+B(t_{0},t_{3})~\alpha_{t_{0}}^{t_{3}}+B(t_{0},t_{4})~\alpha_{t_{0}}^{t_{4}}+B(t_{0},t_{5})~\alpha_{t_{0}}^{t_{5}}
$$  

This gives $\alpha_{t_{0}}^{t_{i}}$  

Finally, note that the structurer will be making LIBOR referenced payments to the CMS market maker. These payments will come from the original principal. $N=100$ . The structurer will place the. principal into a deposit account and receive floating LIBOR..  

The replication is complete. The structurer buys a receiver a 5-year CMS on the 10-year CMS rate and sells a 5-year Bermudan swaption on the CMS rate that can be exercised annually. The original $N$ received as principal is held in a deposit account..  

The cash flows of this portfolio are shown in Figure 20.9. These cash flows are identical to the ones promised by the note. The structurer is essentially buying the portfolio, repackaging it, and then selling it to the client as a structured CMS-linked note. We can summarize such CMS-linked structures using contractual equations. For this particular CMS-linked note we have  

![](f21a0538f5ac5402774686bb7124af14f6c4efdd4c2add90abee1c72685c889d.jpg)  

Note that the replicating portfolio presents further opportunities to the structurer. The structurer may be in need to sell swaption volatility to other clients. Through this CMs-linked note the structurer is buying swaption volatility from retail clients. Hence, the note may be a good way of generating a needed supply of swaption volatility at an attractive price. The structurer will naturally sell the swaption at a higher (offer) price than the price of the swaption implicitly bought from the retail client.  

A similar comment is valid for the CMS. The structurer may in fact be a CMS market maker and may be receiving fixed CMS rates and paying floating rates in a different deal. By marketing. the CMS-linked note to the investor the structurer is paying a fixed CMS rate. This is like receiving. the asked CMS rate and then paying the bid CMS rate.  

In other words, the instruments that need to be purchased from the market may in fact already be in the books of the structurer. The structured product is then a good way of taking these risks, repackaging them, and then selling them, to retail clients.  

# 20.4.4 ENGINEERING A CMS SPREAD NOTE  

Suppose an investor expects that the yield curve will steepen. In that case, a CMS-spread structure is appropriate. First we consider the product itself.  

This LIBOR exotic has three additional properties. First, the instrument is more complicated. because the floating annual coupon will depend on more than one CMS rate, hence the "spread." Second, this spread will be offered to the retail investor after multiplying it with a participation rate. The participation rate has the potential of significantly enhancing the yields if the expectation. turns out to be correct and if the product is not called. The spread in question can become negative. To prevent investors from paying negative coupons, such spread-related coupons are often floored at zero. Third, because the product is written on more than one CMS rate, the value of the structure will explicitly depend on the correlation between these rates..  

The example below is typical of CMS spread notes.  

# EXAMPLE: A CMS SPREAD NOTE  

Issuer: Bank ABC; Tenor: 5 years   
Principal: Guaranteed at maturity at $100\%$   
Coupons:   
Year 1 $:4.00\%$   
Year $\mathrm{\Omega}{-5\colon17\times(C M S^{10}{-C M S^{20}})}$ , max $22\%$ $\mathrm{mm}0\%$   
Call: Callable on each coupon date, $t_{i}$ ---  

Why would an investor be interested in such a note? Suppose an institutional investor expects that the yield curve will steepen further. This can happen in two ways at least..  

First, if at constant inflation and hence at constant long rates, the short end interest rates decline.   
A loosening of monetary policy by the Central Bank due to moderately weakening real economy.   
may be one example. Second, short rates and Central Bank monetary policy may stay the same, but.  

due either to inflationary pressures or strengthening economic activity the long rates may go up.. These two cases represent two possible views and the spread note will provide one way to take an exposure toward such an event.  

This product will offer higher rates if the yield curve keeps steepening gradually, as the coupon. is dependent on the differential between the rates. Below we synthetically create a CMS spread note starting with more elementary instruments.  

# 20.4.5 THE ENGINEERING  

The CMS spread product has (at least) two novel financial engineering features: the product will illustrate the utilization of the participation rate and the way one has to floor the spreads. In addi-. tion, on the pricing side, we will see that correlation becomes an explicit additional risk."' Now we engineer the CMS spread note mentioned above. The first year coupon is already discussed; it comes from the first year LIBOR rate which is known, plus part of the option premium sold by the investor. The real novelty of the structure is in the coupons for years. $i=2,3,4,5.$ In fact, the coupons are of the form,  

$$
c_{t_{i}}=\mathrm{max}\left[\lambda\big(\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h}\big)+\alpha_{t_{i}},0\right]
$$  

where $\mathrm{cms}_{t_{i}}^{m}$ and $\mathrm{cms}_{t_{i}}^{h}$ are two floating CMS rates observed at time $t_{i}$ with CMS maturities of $m$ and $h$ years, respectively. As shown in the example, there is no harm in thinking that $m=10$ and $h=2$ years, respectively. According to this, the coupon gets bigger or smaller depending on the difference between the 10-year and 2-year swap rates at times $t_{i}$ in the future. At times $t_{i}.$ we are taking snapshots of the swap curve and paying the client a coupon proportional to the slope of the curve. In this particular case, the client would get progressively higher coupons if the swap curve becomes steeper and steeper during the following 5 years. The note will benefit from progressive steepening $i f$ it is not called.  

In order to engineer the coupons, first ignore the floor, and let the. $\alpha$ represent a swaption pre. mium allocated to the five settlement dates, as before. Now consider engineering the component,  

$$
\lambda(\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h})
$$  

These coupons can be replicated using the following position: pay 2-year CMS rate and receive 10-year CMS rate for 5 years during the. $t_{1},~t_{2},~t_{3},~t_{4}$ .This can be accomplished by getting in two. CMS. The structurer buys $\lambda$ units of the 10-year CMS and sells. $\lambda$ units of the 2-year CMS. For simplicity the cash flows for the first 2 years only are shown in Figure 20.10.  

The figure incorporates the way CMS market quotes the CMS. It turns out that the market doe: this as a spread to the plain vanilla swap rate. Thus,.  

$$
\mathrm{cms}_{t_{i}}^{10}=s_{t_{0},t_{i}}^{5}+s p_{t_{i}}^{10,5}
$$  

and  

$$
\mathrm{cms}_{t_{i}}^{2}=s_{t_{0},t_{i}}^{5}+s p_{t_{0}}^{2,5}
$$  

![](a8b6da817bbdb5549e8a0802f45667d745cc5ed7816dca68ccc99bd26e5ac775.jpg)  

# FIGURE 20.10  

CMS spread product and two CMS.  

where $s_{t_{0},t_{t}}^{5}$ is the 5-ear vanilla foward) swap rate known at ime $t_{0}$ for the case swap beginninge at time t;. spio. $s p_{t_{0}}^{10,5}$ is the 10-year CMS spread for an instrument of 5-year maturity. The structurer will receive this.e $s p_{t_{0}}^{2,5}$ on the other hand is the 2-year CMs spread for an instrument of 5-year maturity. The structurer will pay this. Note that at time $t_{0}$ , both spreads are known for all. $t_{i}$  

Adding together the components we have:  

$$
\begin{array}{r l}&{c_{t_{i}}=\operatorname*{max}\Big[\lambda\Big(\mathrm{cms}_{t_{i}}^{10}-\mathrm{cms}_{t_{i}}^{2}\Big)+\alpha_{t_{i}},0\Big]}\ &{\quad=\operatorname*{max}\Big[\lambda\Big(\Big(s_{t_{0},t_{i}}^{5}+s p_{t_{0}}^{10,5}\Big)-\Big(s_{t_{0},t_{i}}^{5}+s p_{t_{0}}^{2,5}\Big)\Big)+\alpha_{t_{i}},0\Big]}\ &{\quad=\operatorname*{max}\Big[\lambda\Big(s p_{t_{0}}^{10,5}-s p_{t_{i}}^{2,5}\Big)+\alpha_{t_{0}},0\Big]}\end{array}
$$  

This is the coupon. Note that at this point of the engineering the floating rates have dropped, and the only unknown on the right-hand side is the participation rate. $\lambda$ . Next we show how $\lambda$ can be determined.  

First remember that the principal. $N$ is received from the investor. This is placed in a deposit. account that pays the LIBOR rates $L_{t_{i}}$ in the future. At time. $t_{0}$ one can get in a 5-year swap and convert these floating cash flows into a strip of known swap rate cash flows at the rate. $s_{t_{0}}^{5}$ . This means at every $t_{i}$ the structurer will receive the known quantity. $s_{t_{0}}^{5}$ . This is shown in Figure 20.11 for a simplified 2-year maturity version of the 5-year maturity product. Consider the following:  

$$
\lambda\Big(s p_{t_{0}}^{10,5}-s p_{t_{0}}^{2,5}\Big)=s_{t_{0}}^{5}
$$  

This is an equation where all quantities are known at $t_{0}$ except $\lambda$ . Solve for $\lambda$ and insert this number in the original coupon rate,  

$$
c_{t_{i}}=\operatorname*{max}\Big[\lambda\Big(\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h}\Big)+\alpha_{t_{i}},0\Big]
$$  

In this expression, the unknowns are the CMS rates and this is the risk the client is assuming. To the structurer, however, the spread. $\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h}$ does not represent a risk since it can be hedged. at a cost of $s p_{t_{0}}^{10,5}-s p_{t_{0}}^{2,5}$ The example below shows this simplecalculation.  

# EXAMPLE  

Suppose the 2-year and 10-year CMS trade at spreads of  

$$
\begin{array}{r}{s p^{10,5}=50\mathrm{{bps}}}\ {\mathrm{{}}}\ {s p^{2,5}=20\mathrm{{bps}}}\end{array}
$$  

The difference is 30 bps. Suppose also that the 5-year swap rate is $4.5\%$ . Then $\rangle$ will be given by  

$$
\frac{450}{30}=15
$$  

This explains the high participation rates. Even if the curve steepens by a small $30\mathrm{bp}$ the investor can receive a coupon over $10\%$ $\alpha_{t_{i}}$ plus the 450 bp.  

![](30fa0b5f1b2a75c7f2ea4845bb2aa77bfc21b63e66301640110e47dcce25bf90.jpg)  

# FIGURE 20.11  

The structurer has determined all the unknown parameters. Essentially the structurer will buy. and sell two CMS with different reference rates, buy floors and sell swaptions on CMS rates to. manufacture a synthetic of the 5-year CMS note. Then the structurer will repackage these as a structured note and sell it to clients..  

# 20.4.5.1 A contractual equation  

This characterization is shown in the contractual equation below.  

![](6c2fc3c84f3cf6a3e5b72e392e6f0e9c6eec7e9de300b683c7352afba231d029.jpg)  

As in the previous case, the synthetic structure can open several possibilities for the structurer. The structurer can buy swaption volatility, sell cap/floor volatility at advantageous rates from the retail client, and market them at better rates in the interbank market or to other clients. Again, as before, the structurer may in fact have some of the components of the synthetic on his books and the CMS spread note would be a good way of passing them along to other customers and removing them from the balance sheet.  

Or, the structurer can take the exposure itself. The structurer can buy/sell all the components in the right-hand side of the contractual equation except the swaption. Note that, then, if the expectation turns out to be correct, the synthetic structure will have a positive value. But, the note is callable. The structurer will call the note and close the position on the hedge side with a good profit. It is partly for this reason that when the callable notes are likely to pay very high coupons they are in fact called. The investors basically receive the high initial coupon.  

# 20.4.6 SOME OTHER STRUCTURES  

A special case of structured fixed-income products is called Target Redemption Note (TARN). This security provides a sum of coupons until a target level is reached. The note then terminates early.. TARNs may be quite popular with investors when interest rates are low, or more correctly when. they are heading lower. The additional risk in TARNs is the uncertainty of termination date. Although this is like a callable note, there is a difference. The termination condition is explicitly. stated in a TARN and can easily be priced using the LIBOR market model. On the other hand, callable products contain embedded Bermudan swaptions. It is much more difficult to determine when the option will be exercised (i.e., called). Some investors may prefer the more transparent way the TARNs are redeemed early. Like the others, the instrument is path dependent..  

Another example is an inverse floater. As typical in such structured products, the first coupon is fixed. The subsequent coupons are set so as to depend on LIBOR inversely. When LIBOR rates decline, the coupon automatically increases. Often such coupons accumulate. If the accumulated coupons reach the target level, the note will be redeemed early. The client is paid the par value..  

We can also give examples of structured products that are useful for asset-liability manage-. ment. Consider a trigger swap that fixes borrowing costs for. $T$ years at a level lower than the current comparable market rates. In this sense, it is an asset-liability management tool. We discuss a simple variant. It is easy to complicate this simple prototype. Products such as trigger swaps belong in the category of fixed-income structured products although they are not marketed to investors. The clients are corporations and the product is useful in managing assets and liabilities. Still, the main idea is the same. The corporation has a view on the yield curve movements, or simply desires to lower hedging costs, which is the equivalent of yield enhancement..  
