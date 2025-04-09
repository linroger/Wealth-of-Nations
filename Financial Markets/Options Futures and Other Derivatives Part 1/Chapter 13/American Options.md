# 13.5 AMERICAN OPTIONS  

Up to now all the options we have considered have been European. We now move on to.   
consider how American options can be valued using a binomial tree such as that in Figure 13.4 or 13.7. The procedure is to work back through the tree from the end to the.   
beginning, testing at each node to see whether early exercise is optimal. The value of the.   
option at the final nodes is the same as for the European option. At earlier nodes the.   
value of the option is the greater of.  

1. The value given by equation (13.5)   
2. The payoff from early exercise.  

Figure 13.8 shows how Figure 13.7 is affected if the option under consideration is American rather than European. The stock prices and their probabilities are unchanged. The values for the option at the final nodes are also unchanged. At node B, equation (13.5) gives the value of the option as 1.4147, whereas the payoff from early exercise is negative $(=-8)$ . Clearly early exercise is not optimal at node B, and the value of the option at this node is 1.4147. At node C, equation (13.5) gives the value of the option as 9.4636, whereas the payoff from early exercise is 12. In this case, early exercise is optimal and the value of the option at the node is 12. At the initial node A, the value given by equation (13.5) is  

$$
e^{-0.05\times1}(0.6282\times1.4147+0.3718\times12.0)=5.0894
$$  

![](images/4d988cc3988ef44ba9ca9688f1ddd83616cb4c6f0e8ab551faff6337f7f7125f.jpg)  
Figure 13.8 Using a two-step tree to value an American put option. At each node, the upper number is the stock price and the lower number is the option price..  

and the payoff from early exercise is 2. In this case early exercise is not optimal. The value of the option is therefore $\$5.0894$  
