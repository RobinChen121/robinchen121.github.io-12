---
title: Proof for the continuity of a min function.
categories:
- Paper reading
excerpt: |
  I am trying to prove the continuity of a min function following the mathematical defintion.

feature_image: "https://picsum.photos/2560/600?/?random"
image: "https://picsum.photos/2560/600?/?random"
---

Assume a min real function is defined below:

$$
f(x)=\min\limits_{x\leq y\leq h(x)}g(y)
$$

$g(x)$ is continuous and $h(x)$ is a non-decreasing function. Prove $f(x)$ is continuous.


$\textit{Proof}.$

For any $x_0$, there are two cases according to whether $f(x_0)=g(x_0)$.

1. $f(x_0)=g(x_0)$

Because $g(x)$ is continuous. For $x\in[x_0-\delta, x_0+\delta]$, $|g(x)-g(x_0)|<\epsilon$. And by the definition of $f(x)$, $f(x)\leq g(x)$.

   $$|f(x)-f(x_0)|=|f(x)-g(x_0)|\leq |g(x)-g(x_0)|<\epsilon$$


2. $f(x_0)\neq g(x_0)$

There must exist $s$, $x_0\leq s\leq h(x_0)$, such that $f(s)=g(x_0)$. Let $\delta=s-x_0$




Because $g(x)$ is continous, for any $\epsilon>0$ and any given $x_0$,there exits $x\in [x_0-\delta, x_0+\delta]$, such that
$$|g(x)-g(x_0)|<\epsilon$$

Assume
$$f(x_0)=g(y^\ast_{0})=\min\limits_{x_0\leq y\leq h(x_0)}g(y)$$

$$g(y^\ast_{\Delta})=\min\limits_{x_0-\delta\leq y\leq h(x_0+\delta)}g(y)$$

For any $x\in [x_0-\delta, x_0+\delta]$,

$$f(x)=g(y^\ast_{x})=\min\limits_{x\leq y\leq h(x)}g(y)$$

Apparently, $g(y^\ast_{\Delta})\leq g(y^\ast_{x})$, $g(y^\ast_{\Delta})\leq g(y^\ast_0)$.

So,

$$
\begin{aligned}
|f(x)-f(x_0)|&=|g(y^\ast_x)-g(y^\ast_0)| \\
&= |\min\limits_{x\leq y\leq h(x)}g(y)-\min\limits_{x_0\leq y\leq h(x_0)}g(y)|\\
&=
\end{aligned}
$$






According the location of $y^\ast_\Delta$, there are three cases possible:

(a).  $y^\ast_\Delta= y^\ast_x$, if $y^\ast_\Delta\in [x, h(x)]$.


(b). $y^\ast_\Delta\in [x-\Delta, x]\subset [x_0-\delta, h(x_0+\delta)]$.


(c). $y^\ast_\Delta\in [h(x), h(x+\delta)]\subset [x_0-\delta, h(x_0+\delta)]$.
