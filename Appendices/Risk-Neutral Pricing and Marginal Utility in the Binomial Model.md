# Risk-Neutral Pricing and Marginal Utility in the Binomial Model



BOX 22.3: State Prices

In the example above, $\hat{p}^{H}/(1+r)$ is the state price for the event that the economy does well, and $\hat{p}^{L}/(1+r)$ is the state price for the event that the economy does badly.
Let $Q^H$ be the price at time 0 of a security that pays $1 when the high state occurs, and $\varrho^{\tilde{L}}$ the price of a security paying $1 when the low state occurs.* Call these the high and low securities. To understand the economics of a state price, we can think about marginal utility. If the investor buys an additional unit of the high security, the additional future cash flow is $1 received when the high state occurs. In order to pay for this security, the investor reduces consumption at time 0 by $Q^H$,which has a utility cost of $U_0^{\prime}(C_0)Q^H$ In exchange, the investor receives $1 of extra consumption in the high state, which has a utility value of $U_1^{\prime}(C^H)\times\$1.$ The utility given up must equal the expected utility received, so we have
$$U_0^{\prime}(C_0)Q^H=p\times U_1^{\prime}(C_1^H)\times\$1$$
We can rewrite this as
$$Q^{H}=p^{H}\times\chi^{H}\tag{22.55}$$
Similarly, we can write the price of the low security as

$$Q^L=p^L\times\chi^L\tag{22.56}$$
The variables $\chi^H$ and $\chi^L$ are state-specific discount factors: Cash flows in the high state are discounted by $\chi^H$ and in the low state by $\chi^L.$
We can now value the bond and the stock. The bond pays $1 in each state. Using the state prices, we have
$$B_{0}=[p\times\chi^{H}\times\$1]+[(1-p)\times\chi^{L}\times\$1]\\=Q^{H}\times\$1+Q^{L}\times\$1\text{(22.57)}$$
Similarly, the value of the stock is
$$S_{0}=[p\times\chi^{H}\times S_{1}^{H}]+[(1-p)\times\chi^{L}\times S_{1}^{L}]\\=Q^{H}\times S_{1}^{H}+Q^{L}\times S_{1}^{L}\text{(22.58)}$$
*These are often called“Arrow-Debreu”securities, named after Nobel prize-winning economists Kenneth Arrow and Gerard Debreu.