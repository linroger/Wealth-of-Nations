# 12.2 A STOCHASTIC PROCESS FOR THE ASSET PRICE CHANGE

The price change on the asset from a starting point of time 0 to a point of time $d t$ is simply the dollar change or5

$$
d S_{d t}=S_{d t}-S_{0}.
$$

The price change from time $d t$ to time $2d t$ is

$$
d S_{2d t}=S_{2d t}-S_{d t}.
$$

This pattern continues so that at a given future time $T.$ , the price change is

$$
d S_{T}=S_{T}-S_{T-d t}.
$$

Backing up to time 0, the price change on the asset to time $T$ is

$$
\Delta S_{T}=S_{T}-S_{0}.
$$

Thus a price change can be expressed by linking the successive returns,

$$
S_{T}-S_{0}=(S_{d t}-S_{0})+(S_{2d t}-S_{d t})+\cdot\cdot\cdot+(S_{T-d t}-S_{T})+(S_{T}-S_{T-d t}).
$$

Note that due to the potential for nonpositive values, log transformations are not pursued with ABM. With price changes, we assume the change in asset value is normally distributed.

For ABM with arithmetic drift, we have the expected price change and price change variance are6

$$
\begin{array}{c}{{E(d S_{t})=\alpha_{\S}d t{\mathrm{~and}}}}\ {{\mathrm{var}(d S_{t})=\sigma_{\S}^{2}d t.}}\end{array}
$$

With ABM with geometric drift, we have the expected price change and price change variance as follows:7

$$
E(d S_{t})=S_{0}e^{\alpha d t}
$$

and

$$
\operatorname{var}(d S_{t})={\left[{\begin{array}{l l l}{\sigma_{\S}^{2}\left({\frac{e^{2\alpha d t}-1}{2\alpha}}\right)}&{{\mathrm{if~}}\alpha\neq0}\ {\sigma_{\S}^{2}d t}&{{\mathrm{if~}}\alpha=0.}\end{array}}\right.}
$$
