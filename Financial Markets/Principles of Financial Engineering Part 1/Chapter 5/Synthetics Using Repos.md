# 5.6 SYNTHETICS USING REPOS  

We will now analyze repo strategies by using contractual equations that we introduced in previous chapters. We show several examples. The first example deals with using repos in cash-and-carry arbitrage, we then manipulate the resulting contractual equations to get further synthetics.  

# 5.6.1 A CONTRACTUAL EQUATION  

Let $F_{t}$ be the forward price observed at time. $t$ , for a Treasury bond to be delivered at a future date $T_{:}$ with $t<T.$ Suppose the bond to be delivered at time. $T$ needs to have a maturity of. $U$ years. Then, at time $t_{:}$ we can (i) buy a $(T-t)+U$ year Treasury bond, (ii) repo it out to get the necessary. cash to pay for it, and (ii) hold this repo position until $T.$ At time $T_{:}$ cash plus the repo interest has to be returned to the repo dealer and the bond is received. The bond will have a maturity of $U$ years. As seen above, these steps will result in exactly the same outcome as a bond forward. We express these steps using a contractual equation. This equation provides a synthetic forward.  

![](cee69828170fb0e5b24dfc37d9be1b440057baefa72e8828408bf061e4863268.jpg)  

According to this, futures positions can be fully hedged by transactions shown on the right-hand side of the equation. This contractual equation can be used in several interesting applications of. repo transactions. We discuss two examples.  

# 5.6.2 A SYNTHETIC REPO  

Now rearrange the preceding contractual equation so that repo is on the left-hand side:  

![](455262ab91a1ee9fdf6578f33af4c63d73db77638d74cb2023d0bb96ee300d02.jpg)  

Thus, we can easily create a synthetic repo transaction by using a spot sale along with a forward purchase of the underlying asset.  

# 5.6.3 A SYNTHETIC OUTRIGHT PURCHASE  

Suppose for some reason we don't want to buy the underlying asset directly. We can use the contractual equation to create a spot purchase synthetically. Moving the spot operation to the left-hand side,  

![](f4f916282cf97f62d744b52010d767c8e185c03bf7bb1805ee317284b57dfe82.jpg)  

The right-hand side operations are equivalent to the outright purchase of the security.  

# 5.6.4 SWAPS VERSUS REPO  

There may be some interesting connections between strips, swaps, and repo market strategies. For example, if strips are purchased by investors who hold them until maturity, there will be fewer whole-coupon bonds. This by itself raises the probability that these bonds will trade as "special." As a result, the repo rate will on the average be lower, since the trader who is short the instrument will have to accept a "low" repo rate to get the security that is "special' to him or her.12  

According to some traders, this may lead to an increase in the average swap spread because the availability of cheap funding makes paying fixed relatively more attractive than receiving fixed.  
