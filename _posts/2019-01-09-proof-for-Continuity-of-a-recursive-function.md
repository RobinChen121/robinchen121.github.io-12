---
title: Proof for the continuity of an recursive function
categories:
- Paper reading
excerpt: |
  Recently I am reading one paper "Shaoxiang Chen, M. Lambrecht. XY Band and (s, S) Policies[R]. Research Paper, 1990, No. 9011, ETEW, KU Leuven." Its proofs for the continuity of a recurisive function is very impressive for me. The proof for this is by induction.

feature_image: "https://picsum.photos/2560/600?/?random"
image: "https://picsum.photos/2560/600?/?random"
---

Recently I am reading one paper "Shaoxiang Chen, M. Lambrecht. XY Band and (s, S) Policies[R]. Research Paper, 1990, No. 9011, ETEW, KU Leuven." Its proofs for the continuity of a recurisive function is very impressive for me.

The recursive function is:

$$
\begin{aligned}
&f_n(x)=\min
\begin{cases}
L(x)+\displaystyle\int f_{n+1}(x-t)\phi(t)dt\\
\min\limits_{x\leq y\leq  x+B}K-cx+L(y)+\displaystyle\int f_{n+1}(y-t)\phi(t)dt
\end{cases}\\
&f_{N+1}(x)=0
\end{aligned}
$$

An assumption: $L(y)$ is a continuous function.

$\textit{Proof}.$
