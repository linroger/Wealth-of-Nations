# 11.1 A RESULT FROM BASIC CALCULUS

Although there is a great deal of formal mathematical rigor to Ito's lemma, the essential elements are relatively simple. Let us begin, however, with a reminder of a few basic results from ordinary calculus. Recall that any differential in ordinary calculus,. $d t<1$ , has a limit. of zero if raised to a power greater than 1.0. In other words,. $d t^{k}\to0$ if $k>1$ . Consider a generic mathematical function such as $\boldsymbol{F}(\boldsymbol{x},t)$ in which the first and second derivatives. exist with respect to. $x$ and $t$ . Using a Taylor series expansion, the change in value of the. function can be expressed as

$$
d F={\frac{\partial F}{\partial x}}d x+{\frac{\partial F}{\partial t}}d t+{\frac{1}{2}}{\frac{\partial^{2}F}{\partial x^{2}}}d x^{2}+{\frac{1}{2}}{\frac{\partial^{2}F}{\partial t^{2}}}d t^{2}+{\frac{\partial^{2}F}{\partial x\partial t}}d x d t+\cdot\cdot\cdot.
$$

Because $d x^{2}\rightarrow0,d t^{2}\rightarrow0$ and $d x d t\to0$ we write Equation (11.1) as

$$
d F=\frac{\partial F}{\partial x}d x+\frac{\partial F}{\partial t}d t.
$$

This statement means that the change in $F$ is a function of the first-order changes in $x$ and t. The change in $x$ is multiplied by the partial derivative of. $F$ with respect to $x$ and the change in $t$ is multiplied by the partial derivative of $F$ with respect to $t$ . All of this is a formal way. of stating that as $x$ and $t$ change, they induce a change in. $F.$ The changes in $x$ and $t$ are so small, however, that squared changes in $x$ and $t$ are zero in the limit, and their product is also zero in the limit..
