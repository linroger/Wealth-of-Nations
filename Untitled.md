```latex
\usepackage{tikz}
\usetikzlibrary{positioning}

\begin{document}
\begin{tikzpicture}[
    box/.style = {draw,     rounded corners,     minimum width=5cm,     minimum height=2cm,     align=left},    
    node distance=4cm
]

% Level i = 0
\node[box] (i0) {
    $S_0 = 1502.39$\\
    $q^*_0 = 0.5446$\\
    $p_0^1 = 50.2 = p^{mkt}(1550,     0.21)$\\
    $p_0^2 = 14.65 = p^{mkt}(1450,     0.21)$
};

% Level i = 1,     upper branch
\node[box,     right=of i0,     yshift=3cm] (i1u) {
    $S_{1,    u} = 1551.26$\\
    $q^*_{1,    u} = 0.7144$\\
    $p^1_{1,    u} = 13.5413$\\
    $p^2_{1,    u} = 0$
};

% Level i = 1,     lower branch
\node[box,     right=of i0,     yshift=-3cm] (i1d) {
    $S_{1,    d} = 1455.059$\\
    $q^*_{1,    d} = 0.7373$\\
    $p^1_{1,    d} = 94.67$\\
    $p^2_{1,    d} = 32.36$
};

% Level i = 2,     upper-upper branch
\node[box,     right=of i1u,     yshift=3cm] (i2uu) {
    $S_{2,    uu} = 1567.0713$\\
    $p^1_{2,    uu} = 0$\\
    $p^2_{2,    uu} = 0$
};

% Level i = 2,     middle branch
\node[box,     right=of i1u,     yshift=-3cm] (i2ud) {
    $S_{2,    ud} = S_{2,    du} = 1502.39$\\
    $p^1_{2,    ud} = 47.61$\\
    $p^2_{2,    ud} = 0$
};

% Level i = 2,     lower-lower branch
\node[box,     right=of i1d,     yshift=-3cm] (i2dd) {
    $S_{2,    dd} = 1336.2316$\\
    $p^1_{2,    dd} = 213.7684$\\
    $p^2_{2,    dd} = 113.7684$
};

% Connect nodes
\draw[->] (i0.east) -- ++(0.5,    0) |- (i1u.west);
\draw[->] (i0.east) -- ++(0.5,    0) |- (i1d.west);
\draw[->] (i1u.east) -- ++(0.5,    0) |- (i2uu.west);
\draw[->] (i1u.east) -- ++(0.5,    0) |- (i2ud.west);
\draw[->] (i1d.east) -- ++(0.5,    0) |- (i2ud.west);
\draw[->] (i1d.east) -- ++(0.5,    0) |- (i2dd.west);

% Labels for time levels
\node[above left=0.5cm of i0] {$i = 0$};
\node[above left=0.5cm of i1u] {$i = 1$};
\node[above left=0.5cm of i2uu] {$i = 2$};

\end{tikzpicture}
\end{document}

```
