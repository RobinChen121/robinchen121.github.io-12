---
title: Pursuing the paper " cash-flow based dynamic inventory management"
categories:
- Paper reading
excerpt: |
  I am trying to fully understand the paper "cash-flow based dynamic inventory management"

feature_image: "https://picsum.photos/2560/600?/?random"
image: "https://picsum.photos/2560/600?/?random"
---

This paper is written by Katehakis et al. (2016). Its main difference with Chao et al. (2008) and Gong et al. (2014) is its considering of non-stationary demand.

Inventory-cash state $(x_n, y_n)$, where $x_n$ the initial inventory in period $n$, and $y_n$ denotes the amount of product that can be purchased using all the available cash $\gamma_n$ ($\gamma_n=cy_n$).

The cash flow fron inventory operations ($D_n$ is the random demand):

$$
\begin{aligned}
R_n(D_n, q_n, x_n)=& p\min\{q_n+x_n, D_n\}-h(q_n+x_n-D_n)^+\\
=&p(q_n+x_n)-(p+h)(q_n+x_n-D_n)^+
\end{aligned}
$$

The cash flow from financial transactions is ($i$ is deposite rate and $l$ is bank loan interest rate):

$$
\begin{aligned}
K_n(q_n, y_n)=& c(y_n-q_n)[(1+i)\bf{1}_{\{q_n\leq y_n\}}+(1+l)\bf{1}_{\{q_n> y_n\}}]
\end{aligned}
$$

State transition functions:

$$
\begin{aligned}
x_{n+1}=&(x_n+q_n-D_n)^+\\
y_{n+1}=&\left[R_n(D_n, q_n, x_n)+K_n(q_n, y_n)\right]/c
\end{aligned}
$$

Optimality equation:

$$
\begin{aligned}
V_n(x_n, y_n)=&\sup_{q_n\geq 0} \mathbb{E}\left[V_{n+1}(x_{n+1},y_{n+1})\right]\\
=&\sup_{q_n\geq 0} \mathbb{E}\left[R_n(D_n, q_n, x_n)+K_n(q_n, y_n)\right]
\end{aligned}
$$
