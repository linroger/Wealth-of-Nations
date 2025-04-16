---
tags:
  - '#backward_equation'
  - '#binomial_tree'
  - '#discrete_time'
  - '#fokker_planck_equation'
  - '#forward_equation'
  - '#kolmogorov_equations'
  - '#path_dependent_options'
  - '#probability_density'
  - '#stochastic_process'
---
# 16.4 THE KOLMOGOROV EQUATIONS

We now take a look at a set of equations that appears in the analysis of movements of a. stochastic process. These equations are called the Kolmogorov equations. They are slight variations of the partial differential equation that is well known in derivative pricing theory in which the option price change is related to its derivatives and changes in time and the. underlying. But instead of relating prices to their derivatives, the Kolmogorov equations relate probabilities to their derivatives. There are two such equations: the forward equation. and backward equation.

Consider the following setup in a two-state discrete time world. In other words, the. random process can move up or down in a given time and then up or down again and again. Suppose the random variable of interest starts off in state. $j$ at time 0. We are interested. in the probability that the process is in state. $k$ at time $_n$ In the two-state discrete world, the only way the process could get to state $k$ at time $_n$ is to be at state $k+1$ at time $n-1$ and move down with probability. $1-\phi$ or to be in state $k-1$ at time $n-1$ and move up with probability $\phi$ If the probability of moving from state $j$ at time 0 to state $k+1$ at time $n-1$ .5 $\phi_{j,k+1,n-1}$ and the probability of moving from state $j$ at time 0 to state $k-1$ at time $n-1$ .5 $\phi_{j,k+1,n-1}$ , then the probability of being in state $k$ at time $_n$ is

$$
\phi_{j,k,n}=(1-\phi)\phi_{j;k+1;n-1}+\phi\phi_{j;k-1;n-1}.
$$

Note that the parameter $\phi$ with no subscript is the probability of a move upward, and. its complement, $1-\phi$ , is the probability of a move downward. We are interested in moving from one state to another, not moving up or down. The variable $\phi$ with a subscript represents a compound probability, reflecting movements over time and states.

Consider a process $x_{t}$ that changes by the value $\varphi x$ over the interval $\Delta t.$ Let us express the probability in Equation (16.39) more generally as $\phi_{x;t;x_{0}}$ , which is the probability of being in state. $x$ at time $t$ given that we were in state $x_{0}$ at time 0. We would write this probability as

$$
\phi_{x;t;x_{0}}=\phi\phi_{x-\Delta x;t-\Delta t;x_{0}}+(1-\phi)\phi_{x+\Delta x;t-\Delta t;x_{0}}.
$$

If we expand $\phi_{x-\Delta x;t-\Delta t;x_{0}}$ and $\phi_{x+\Delta x;t-\Delta t;x_{0}}$ in a second-order Taylor series, we obtain

$$
\begin{array}{l}{\displaystyle{\phi_{x+\Delta x;t-\Delta t;x_{0}}=\phi_{x;t;x_{0}}-\frac{\partial\phi}{\partial t}\Delta t+\frac{\partial\phi}{\partial x}\Delta x+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}}}\ {\displaystyle{\phi_{x-\Delta x;t-\Delta t;x_{0}}=\phi_{x;t;x_{0}}-\frac{\partial\phi}{\partial t}\Delta t-\frac{\partial\phi}{\partial x}\Delta x+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}},}\end{array}
$$

where we have suppressed some of the arguments on the joint probabilities for notational. simplicity. We shall bring them back later. We now use (16.41) and (16.40) to obtain

$$
\begin{array}{l}{\displaystyle\phi_{x;t;x_{0}}=\phi\left[\phi_{x;t;x_{0}}-\frac{\partial\phi}{\partial t}\Delta t-\frac{\partial\phi}{\partial x}\Delta x+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}\right]}\ {\displaystyle~+\left(1-\phi\right)\left[\phi_{x;t;x_{0}}-\frac{\partial\phi}{\partial t}\Delta t+\frac{\partial\phi}{\partial x}\Delta x+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}\right].}\end{array}
$$

Rearranging, we have

$$
\begin{array}{r l}&{\phi_{x;t x_{0}}=\phi\left[\phi_{x;t x_{0}}-\frac{\partial\phi}{\partial t}\Delta t+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}\right]-\phi\frac{\partial\phi}{\partial x}\Delta x}\ &{\qquad+\phi_{x;t x_{0}}-\frac{\partial\phi}{\partial t}\Delta t+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}+\frac{\partial\phi}{\partial x}\Delta x}\ &{\qquad-\phi\left[\phi_{x;t x_{0}}-\frac{\partial\phi}{\partial t}\Delta t+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}\right]-\phi\frac{\partial\phi}{\partial x}\Delta x}\ &{\qquad0=-\frac{\partial\phi}{\partial t}\Delta t+\frac{\partial\phi}{\partial x}\Delta x+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}-2\phi\frac{\partial\phi}{\partial x}\Delta x}\ &{\frac{\partial\phi}{\partial t}\Delta t=\frac{\partial\phi}{\partial x}\Delta x(1-2\phi)+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}.}\end{array}
$$

It turns out that an appropriate set of values for $\phi$ and $\Delta x$ is12

$$
{\begin{array}{c}{\Delta x=\sigma{\sqrt{\Delta t}}}\ {\phi={\cfrac{1}{2}}\left(1+{\cfrac{\mu{\sqrt{\Delta t}}}{\sigma}}\right)}\ {1-\phi={\cfrac{1}{2}}\left(1-{\cfrac{\mu{\sqrt{\Delta t}}}{\sigma}}\right).}\end{array}}
$$

Substituting from (16.44) into (16.43), we obtain

$$
\begin{array}{l}{\displaystyle\frac{\partial\phi}{\partial t}\Delta t=\frac{\partial\phi}{\partial x}\sigma\sqrt{\Delta t}\left(1-{1-\frac{\mu\sqrt{\Delta t}}{\sigma}}\right)+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\Delta x^{2}}\ {~=-\frac{\partial\phi}{\partial x}\mu\Delta t+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\sigma^{2}\Delta t}\ {~\displaystyle\frac{\partial\phi}{\partial t}=-\frac{\partial\phi}{\partial x}\mu+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi}{\partial x^{2}}\sigma^{2}.}\end{array}
$$

Reinserting the omitted notation, the result is the forward equation,

$$
\frac{\partial\phi_{x;t;x_{0}}}{\partial t}=-\frac{\partial\phi_{x;t;x_{0}}}{\partial x}\mu+\left(\frac{1}{2}\right)\frac{\partial^{2}\phi\left(x;t;x_{0}\right)}{\partial x^{2}}\sigma^{2}.
$$

Equation (16.46) is a continuous time representation of a partial differential equation. for the probability density of being in a future state at a particular time and is called the. forward equation, also known as the Fokker-Planck equation. It relates the probability at a forward time to the prior paths that take it to that point. The forward equation is a partial differential equation with a solution of the probability density,.

$$
\phi_{x;t;x_{0}}={\frac{1}{\sigma\sqrt{2\pi t}}}e^{-{\frac{1}{2}}{\frac{\left(x-x_{0}-\mu t\right)^{2}}{\sigma^{2}t}}}.
$$

Equation (16.47) is also recognized as the density for a variable $x$ with mean $x_{0}+\Delta t$ and variance $\Delta^{2}t.^{13}$ The special case of $\phi=0$ is the one-dimensional equation for heat transfer in which $\phi_{x;t;x_{0}}$ is the temperature.

Now let us look briefly at the backward equation. In this case, we want to know the probability that we started at a particular point, given that we ended up at a particular. point. As an example, and to distinguish the backward problem from the forward problem, note Figure 16.7.

Notice how we have labeled the states. For example, the lowest state at time 4 is. referred to as state 4,1. The next highest state is labeled 4,2, and so on, with the highest state in time 4 being state 4,5. A similar pattern follows for times 3, 2, and 1. Of course, there is only one state at time 0.

Now suppose we are in state 1,2. Find this state in the Figure 16.7. Suppose we are interested in knowing the probability of being in state 4,4. Note that to get from 1,2 to 4,4, we can go up two periods and down one or down one period and up two. We can also go up one period, then down one period, and then up one period. Thus, there is more. than one path that can take us to 4,4 from 1,2. We do not need to consider the path from state 1,1 to 2,2 to 3,3 to 4,4, because it did not start off in state 1,2. The probability of getting to state 4,4 from state 1,2 is the forward probability. Alternatively, we might be. in state 4,4 and want to know what is the probability that we came from state 1,2. The paths are the same as in the forward probability, but the perspective is different. We can think of the forward probability as $\operatorname*{Pr}(k=4,4|j=1,2)$ and the backward probability as $\operatorname*{Pr}(j=1,2|k=4,4)$

![](images/d81e030d36cd5298c130f62f217c29dab8b7799673ff9f8ad7e376f70996ee04.jpg)
FIGURE 16.7 Four-Period Binomial Wiener Process

For illustration of the forward probability, let state $j$ be state 1,2; state $k$ be state 4,4; then $n=3$ . Recall the forward probability stated in Equation (16.39):

$$
\phi_{j;k;n}=(1-\phi)\phi_{j;k+1;n-1}+\phi\phi_{j;k-1;n-1}.
$$

In this example, to go from state 1,2 to state 4,4, the up state one state before state 4,4 is state 3,4 and the down state one state before state 4,4 is state 3,3; thus, state $k+1$ is equivalent to state 3,4 and state $k-1$ is equivalent to state 3,3. We can write the forward looking probability as

$$
\operatorname*{Pr}(k=4,4|j=1,2)=\phi_{(1,2);(4,4);3}=(1-\phi)\phi_{(1,2);(3,4);2}+\phi\phi_{(1,2);(3,3);2}.
$$

Now, we can take this further by finding expressions for $\phi_{(1,2);(3,4);2}$ and $\phi_{(1,2);(3,3);2}$ . The probability $\phi_{(1,2);(3,4);2}$ represents the path of moving from state 1,2 to state 3,4 in two. steps. This is accomplished in the same way as in the binomial world in exactly one way,. two up movements or $\phi^{2}$ . The probability $\phi_{(1,2);(3,3);2}$ represents the paths of moving from state 1,2 to state 3,3, which is accomplished in two different ways, both having exactly one up and one down movement or $2\phi(1-\phi)$ . Thus, we can write the probability further as

$$
\begin{array}{r l}&{\operatorname*{Pr}(k=4,4|j=1,2)=\phi_{(1,2);(4,4);3}}\ &{\qquad=(1-\phi)\phi_{(1,2);(3,4);2}+\phi\phi_{(1,2);(3,3);2}}\ &{\qquad=(1-\phi)\phi^{2}+\phi2\phi(1-\phi)}\ &{\qquad=3\phi^{2}(1-\phi).}\end{array}
$$

Now, more generally for the backward probability, let $\phi_{j;k;n}$ be the probability of going from state $j$ at time 0 to state $k$ in $_n$ steps. Let $\phi_{j-1;k;m}$ be the probability of going from state $j-1$ to $k$ in $^m$ steps and $\phi_{j+1;k;m}$ be the probability of going from state $j+1$ to state $k$ in $^m$ steps. Given that the probability is $\phi$ that we went up to state $j+1$ at time $n-m$ and $1-\phi$ that we went down to state $j-1$ at time $n-m$ , then the probability of going from state $j$ to state $k$ in $m+1$ steps is

$$
\phi_{j;k;m+1}=\phi\phi_{j+1;k;m}+(1-\phi)\phi_{j-1;k;m}.
$$

For illustration of the backward probability, let state $k$ be state 4,4; state $j$ be state 1,2; then $n=3$ $m=2$ , and $n-m=1$ . In this example, to go from state 4,4 to state 1,2, the. upstate one state before reaching state 1,2 from state 4,4 is state 2,3 and the down state one state before state 1,2 is state 2,2; thus, state $j+1$ is equivalent to state 2,3 and state $j-1$ is equivalent to state 2,2. We can write the backward looking probability as.

$$
\begin{array}{c}{{\phi_{j;k;m+1}=\phi\phi_{j+1;k;m}+(1-\phi)\phi_{j-1;k;m}}}\ {{{}}}\ {{\operatorname*{Pr}(j=1,2|k=4,4)=\phi_{(1,2);(4,4);3}=\phi\phi_{(2,3);(4,4);2}+(1-\phi)\phi_{(2,2);(4,4);2}.}}\end{array}
$$

Because we are asking what the probability is that we came from state 1,2, then we should note that it is impossible to have ever moved through some states. In Figure 16.8, the nodes where it would be impossible to have traveled from to get to the current state 4,4 are denoted in bold.

Now, suppose for a minute that state 4,4 has a lattice of its own where the lattice arrives to state 4,4 as the final point. Figure 16.9 illustrates this particular backward lattice.

This backward lattice consists of states that do not actually exist. The impossible. states are expressed as bold. The possible states correspond to the nonbold states shown in Figure 16.8. If we treat this backward lattice as a usual lattice found in the binomial world, then we can use the usual binomial probability of each state, with a probability (down movement) $=1-\phi$ and probability (up movement) $=\phi$

For the columns 0, 1, and 2, we can see that there exists states in each column that are not real. If we are coming from a state in one of these columns, then we must consider that we came from only a possible state in the column (not a fake state created during the creation of the backward lattice). Conditional probabilities are used to update the probabilities for a given column. Column 1, for example, has only two possible states-1,1 and 1,2; thus, if we are looking for the probability that we came from a state in column 1 given that we are currently in state 4,4, we must update the probability to be conditional that we have to be in either state 1,1 or 1,2 only. Thus,.

![](images/f20b16426e91d90daefc5b4d2cbb397a8b9c9979fc195b8a86b870a155bb320d.jpg)
FIGURE 16.8Forward Lattice with Impossible Nodes Demarcated in Bold

![](images/30ed96ddc5ddce8c9d096d1cb3cef9a11920f97682ab2cec1d38519a0d374456.jpg)
FIGURE 16.9  Backward Lattice Illustrated with Impossible Nodes Demarcated in Bold

$$
\operatorname*{Pr}(j=1,2\cup j=1,1|k=4,4\cap j=1,x)=\phi_{(1,1);(4,4);3}+\phi_{(1,2);(4,4);4}=1.
$$

Following a similar procedure as we did for the forward equation, we obtain the continuous time backward equation

$$
\frac{\partial\phi\left(\boldsymbol{x},t;\boldsymbol{x}_{0}\right)}{\partial t}=\mu\frac{\partial\phi(\boldsymbol{x},t;\boldsymbol{x}_{0})}{\partial\boldsymbol{x}_{0}}+\frac{1}{2}\frac{\partial^{2}\phi(\boldsymbol{x},t;\boldsymbol{x}_{0})}{\partial{x_{0}}^{2}}\sigma^{2},
$$

where we note that the difference from the forward equation is that here we are viewing.
the problem from the current position $x_{0}$ . In the forward equation, we are viewing the.
problem from the future position, $x$ The solution to the backward equation, (16.49), is.
the same as the solution to the forward equation, (16.46), namely, the density (16.47).

The Kolmogorov equations for continuous time express the probability densities of looking from one state to another, either looking forward in time or looking back. The general idea behind such equations is to specify the likelihoods of various paths that a random variable can take in the future or has taken in the past. As is often the case, the lesson can oftentimes be more easily seen in discrete time. As such, we introduce a discrete time example.

Figure 16.10 shows a three-period binomial tree for an asset priced at 100 that can go up by $26\%$ or down by $20\%$ each period. The probability of an up move is 0.54, so the probability of a down move is 0.46. There are three values in each cell: the asset price, a cell identifier, and the probability of moving to that cell from the initial cell, 0,0.

For the discrete time analog of the forward equations, we present Table 16.1, which indicates the probability of being in a future state, given that one is in a current state. The rows, as described in the first column, are the current states in which one could be. The columns are the future states. A given cell value is the probability of being in the future state, given that one is in the current state. There are a number of values indicated as NA, which are cases in which the current cell is either after or in the same time step as the future state. That is, from state 2,2, you cannot get to any prior states, nor can you get. to state 2,1 or 2,3. For all future states, there is a probability given when feasible. From. state 2,2, you cannot get to state 3,1, so it is infeasible but that probability is shown as 0.0000. From state 2,2, you can get to state 3,3 by going up, probability 0.54, or to state. 3,2 by going down, probability 0.46. Of course, you cannot get to state 3,4 from 2,2, so that probability is 0.0000.

![](images/1f62f11d1b6c9194587d473d9e321aa082b528bf8c55075078a12b4aa57c6fbb.jpg)
FIGURE 16.10 Binomial Tree for Illustrating Forward and Backward Probabilities

IABLE 16.1 Forward Probabilities in a Binomial World


<html><body><table><tr><td colspan="11">Panel A. Points in Time 0-3</td></tr><tr><td colspan="11">Future States</td></tr><tr><td>Current State</td><td>0,0</td><td>1,1</td><td>1,2</td><td>2,1</td><td>2,2</td><td>2,3</td><td>3,1</td><td>3,2</td><td>3,3</td><td>3,4</td></tr><tr><td>0,0</td><td>NA</td><td>0.4600</td><td>0.5400</td><td>0.2116</td><td>0.4968</td><td>0.2916</td><td>0.0973</td><td>0.3428</td><td>0.4024</td><td>0.1575</td></tr><tr><td>1,1</td><td>NA</td><td>NA</td><td>NA</td><td>0.4600</td><td>0.5400</td><td>NA</td><td>0.2116</td><td>0.4968</td><td>0.2916</td><td>NA</td></tr><tr><td>1,2</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>0.4600</td><td>0.5400</td><td>0.0000</td><td>0.2116</td><td>0.4968</td><td>0.2916</td></tr><tr><td>2,1</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>0.4600</td><td>0.5400</td><td>0.0000</td><td>0.0000</td></tr><tr><td>2,2</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>0.0000</td><td>0.4600</td><td>0.5400</td><td>0.0000</td></tr><tr><td>2,3</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>0.0000</td><td>0.0000</td><td>0.4600</td><td>0.5400</td></tr><tr><td>3,1</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>3,2</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>3,3</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>3,4</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td colspan="11">Panel B. Point in Time 4</td></tr><tr><td colspan="11">Future States Current</td></tr><tr><td>State</td><td></td><td>4,1</td><td></td><td>4,2</td><td></td><td>4,3</td><td>4,4</td><td></td><td></td><td>4,5</td></tr><tr><td>0,0</td><td></td><td>0.0448</td><td></td><td>0.2102</td><td></td><td>0.3702</td><td></td><td>0.2897</td><td></td><td>0.0850</td></tr><tr><td>1,1</td><td></td><td>0.0973</td><td></td><td>0.3428</td><td></td><td>0.4024</td><td></td><td>0.1575</td><td></td><td>0.0000</td></tr><tr><td>1,2</td><td></td><td>0.0000</td><td></td><td>0.0973</td><td></td><td>0.3428</td><td></td><td>0.4024</td><td></td><td>0.1575</td></tr><tr><td>2,1</td><td></td><td>0.2116</td><td></td><td>0.4968</td><td></td><td>0.2916</td><td></td><td>0.0000</td><td></td><td>0.0000</td></tr><tr><td>2,2</td><td></td><td>0.0000</td><td></td><td>0.2116</td><td></td><td>0.4968</td><td></td><td>0.2916</td><td></td><td>0.0000</td></tr><tr><td>2,3</td><td></td><td>0.0000</td><td></td><td>0.00000</td><td></td><td>0.2116</td><td></td><td>0.4968</td><td></td><td>0.2916</td></tr><tr><td>3,1</td><td></td><td>0.4600</td><td></td><td>0.5400</td><td></td><td>0.0000</td><td></td><td>0.0000</td><td></td><td>0.0000</td></tr><tr><td>3,2</td><td></td><td>0.0000</td><td></td><td>0.4600</td><td></td><td>0.5400</td><td></td><td>0.0000</td><td></td><td>0.0000</td></tr><tr><td>3,3</td><td></td><td>0.0000</td><td></td><td>0.0000</td><td></td><td>0.4600</td><td></td><td>0.5400</td><td></td><td>0.0000</td></tr><tr><td>3,4</td><td></td><td>0.0000</td><td></td><td>0.0000</td><td></td><td>0.0000</td><td></td><td>0.4600</td><td></td><td>0.5400</td></tr><tr><td>4,1</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td></tr><tr><td>4,2</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td></tr><tr><td>4,3</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td></tr><tr><td>4,4</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td></tr><tr><td>4,5</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td><td></td><td>NA</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

IABLE 16.2 Backward Probabilities in a Binomial World


<html><body><table><tr><td rowspan="2">Current State</td><td colspan="10">State You Came From</td></tr><tr><td>0,0</td><td>1,1</td><td>1,2</td><td>2,1</td><td>2,2</td><td>2,3</td><td>3,1</td><td>3,2</td><td>3,3</td><td>3,4</td></tr><tr><td>0,0</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>1,1</td><td>1.0000</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>1,2</td><td>1.0000</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>2,1</td><td>1.0000</td><td>1.0000</td><td>0.00</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>2,2</td><td>1.0000</td><td>0.5400</td><td>0.4600</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>2,3</td><td>1.0000</td><td>0.0000</td><td>1.000</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>3,1</td><td>1.0000</td><td>1.0000</td><td>0.0000</td><td>1.0000</td><td>0.0</td><td>0.0</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>3,2</td><td>1.0000</td><td>0.7013</td><td>0.2987</td><td>0.5400</td><td>0.4600</td><td>0.0</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>3,3</td><td>1.0000</td><td>0.3699</td><td>0.6301</td><td>0.0000</td><td>0.5400</td><td>0.4600</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>3,4</td><td>1.0000</td><td>0.0000</td><td>1.0000</td><td>0.0000</td><td>0.0000</td><td>1.0000</td><td>NA</td><td>NA</td><td>NA</td><td>NA</td></tr><tr><td>4,1</td><td>1.0000</td><td>1.0000</td><td>0.0000</td><td>1.0000</td><td>0.0000</td><td>0.0000</td><td>1.0</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>4,2</td><td>1.0000</td><td>0.7788</td><td>0.2212</td><td>0.7013</td><td>0.2987</td><td>0.0000</td><td>0.54</td><td>0.46</td><td>0.00</td><td>0.00</td></tr><tr><td>4,3</td><td>1.0000</td><td>0.5400</td><td>0.4600</td><td>0.2916</td><td>0.4968</td><td>0.2116</td><td>0.0</td><td>0.54</td><td>0.46</td><td>0.00</td></tr><tr><td>4,4</td><td>1.0000</td><td>0.28125</td><td>0.71875</td><td>0.0000</td><td>0.3699</td><td>0.6301</td><td>0.0</td><td>0.00</td><td>0.54</td><td>0.46</td></tr><tr><td>4,5</td><td>1.0000</td><td>0.0000</td><td>1.0000</td><td>0.0000</td><td>0.0000</td><td>1.0000</td><td>0.0</td><td>0.00</td><td>0.00</td><td>1.00</td></tr></table></body></html>

Referring back to our first forward probability example, we can see that this table matches what we had previously said with

$$
\operatorname*{Pr}(k=4,4|j=1,2)=\phi_{(1,2);(4,4);3}=3\phi^{2}(1-\phi)=3(0.54^{2})(1-0.54)=0.4024.
$$

The backward probabilities are slightly more difficult to understand. A backward. probability asks the question of, given you are in a particular state, what is the probability you got here from a specific past state. Table 16.2 shows the backward probabilities for all possible current states. The values of NA indicate states from which you could not have come, such as the same state or a contemporaneous state. Inasmuch as there is no time travel, you also could not have come from a future state. You can, however, have come from a prior state. For example, in state 2,2, there is a 0.46 chance you came from state 1,2, having gone down, and a 0.54 chance you came from state 1,1, having gone up.. Notice that the probability is 1.0000 that you were in state 0,0..

Understanding these types of measures is important for path-dependent options. The. forward measures are clearly more important in finance, because we nearly always look ahead rather than back, but understanding how something came about is helpful in modeling. Estimates of the future nearly always start with what has happened in the past. The. historic paths taken by asset prices can be helpful in developing and validating models.. Thus, they are an important element in the study of stochastic processes..
