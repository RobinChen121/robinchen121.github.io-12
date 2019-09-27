---
title: Pursuing the paper " Capacitated inventory problems with fixed order costs-some optimal policy structure"
categories:
- Paper reading
excerpt: |
  I am trying to fully understand the paper "Capacitated inventory problems with fixed order costs: some optimal policy structure"

feature_image: "https://picsum.photos/2560/600?/?random"
image: "https://picsum.photos/2560/600?/?random"
---

Recently, one of my paper was rejected. I forgot to cite one important paper "Capacitated inventory problems with fixed order costs: some optimal policy structure" in EJOR (2000) by Gallego & Scheller-Wolf. Now I am digging into this paper.



This paper characterize some features of the optimal ordering policy for the problem --- "capacitated stochastic inventory problem with fixed costs".  It propose a definition  of CK convexity.



# 1. Problem description

$L(y)$ is the expected one-period holding/backorder cost.

$$
L(y)=E[h(y-D)^+p(y-D)^-]
$$

$p$ is the unit backorder cost.

$$
J(y) = cy+L(y)
$$

It can be easily shown that $J(y)$ is convex. Also assume $J(y)\rightarrow \infty$ as $|y|\rightarrow \infty$ (for proving the convexity or CK convexity of a induction expression).

The DP(dynamic programming model) of the problem is:

$$
f_n(x) = -cx+H_n(x), \qquad 0\leq n\leq N
$$

where:

$$
\begin{aligned}
G_n(y) &= J(y)+\alpha E[f_{n-1}(y-D_n)]\\
H_n(y) &=\inf_{y\in[x, x+C]}\{KI\{y>x\}+G_n(y)\}
\end{aligned}
$$

$\alpha$ is the dicount factor and $I\{A\}$ is a unit step function.


# 2. CK-convexity


**CK convex**: Given a non-negative $C$ and $K$, we call the function $G:\mathbb{R}\rightarrow \mathbb{R}$ CK-convex if for all $y$, $b>0$, $z\in[0, C]$，
$$K+G(y+z)\geq G(y)+\frac{z}{b}\{G(y)-G(y-b)\}$$

**strong CK convex** Given a non-negative $C$ and $K$, we call the function $G:\mathbb{R}\rightarrow \mathbb{R}$ strong CK-convex if for all $y$, $b>0$, $a\geq 0$, $z\in[0, C]$，
$$K+G(y+z)\geq G(y)+\frac{z}{b}\{G(y-a)-G(y-a-b)\}$$

When $a=0$, strong CK-convex is CK-convex.

Properties of CK-convex:

1.  If $G$ is strong CK-convex, it is also DL-convex for any $0\leq D\leq C$ and $L\geq K$.
2. If $G$ is convex, it is also strong CK-convex.
3. If $G_1$ is strong CK-convex, and $G_2$ is strong CL-convex, then for $\alpha, \beta\geq 0$, $\alpha G_1+\beta G_2$ is strong $C(\alpha K+\beta L)$ convex.
4. If $G$ is strong CK-convex and $X$ is a random variable such that $E[|G(y-x)|]<\infty$, then $E[|G(y-x)|]$ is strong CK convex.
