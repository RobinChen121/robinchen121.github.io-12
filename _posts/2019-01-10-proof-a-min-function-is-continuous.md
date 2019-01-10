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

$g(x)$ is continuous and $h(x)$ is a monotone function. Prove $f(x)$ is continuous.


</br>


$\textit{Proof}.$ Because $g(x)$ is continous, for any $\epsilon>0$ and any given $x_0$,there exits $x\in [x_0-\delta, x_0+\delta]$, such that
$$|g(x)-g(x_0)|<\epsilon$$

Since $h(x)$ is a monotone function, just let it be increasing. Then, assume

$$g(y^\ast_{\Delta})=\min\limits_{x_0-\delta\leq y\leq h(x_0+\delta)}g(y)$$

For any $x\in [x_0-\delta, h(x_0+\delta)]$,

$$f(x)=g(y^\ast_{x})=\min\limits_{x-\delta\leq y\leq h(x+\delta)}g(y)$$

Apparently, $g(y^\ast_{\Delta})\leq g(y^\ast_{x})$.
According the location of $y^\ast_\Delta$, there are three cases possible:

(a).  $y^\ast_\Delta= y^\ast_x$, if $y^\ast_\Delta\in [x, h(x)]$.


(b). $y^\ast_\Delta\in [x-\Delta, x]\subset [x_0-\delta, h(x_0+\delta)]$.


(c). $y^\ast_\Delta\in [h(x), h(x+\delta)]\subset [x_0-\delta, h(x_0+\delta)]$.
