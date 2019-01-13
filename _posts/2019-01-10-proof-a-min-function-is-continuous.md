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

$g(x)$ is continuous and $h(x)$ is a non-decreasing linear function. Prove $f(x)$ is continuous.


$\textit{Proof}.$

<!-- For any $x_0$, there are two cases according to whether $f(x_0)=g(x_0)$.

1. $f(x_0)=g(x_0)$

Because $g(x)$ is continuous. For $x\in[x_0-\delta, x_0+\delta]$, $|g(x)-g(x_0)|<\epsilon$. And by the definition of $f(x)$, $f(x)\leq g(x)$.

   $$|f(x)-f(x_0)|=|f(x)-g(x_0)|\leq |g(x)-g(x_0)|<\epsilon$$


2. $f(x_0)\neq g(x_0)$

There must exist $s$, $x_0\leq s\leq h(x_0)$, such that $f(s)=g(x_0)$. Let $\delta=s-x_0$ -->



Because $g(x)$ is continous, for any $\epsilon>0$ and any given $x_0$,there exits $x\in [x_0-\delta, x_0+\delta]$, such that

$$|g(x)-g(x_0)|<\epsilon$$

Because $h(x)$ is non-decreasing, it is also continuous. There is also

$$|h(x)-h(x_0)|<\epsilon$$

For any two number $x_1$, $x_2$ in the domain $[x_0-\delta, x_0+\delta]$, we can get

$$
\begin{aligned}
|g(x_1)-g(x_2)|&=|g(x_1)-g(x_0)+g(x_0)-g(x_2)|\\
&\leq |g(x_1)-g(x_0)|+|g(x_0)-g(x_2)|<2\epsilon
\end{aligned}
$$

Specially, for any two number $x_1$, $x_2$ in the domain $[x-\delta, x]$,

$$|g(x_1)-g(x_2)|<2\epsilon\tag{1}$$

We can also get

$$|h(x+\delta)-h(x)|<2\epsilon\tag{2}$$

Because $h(x)$ is linear, without losss of generallity, we asssume $h(x)=ax+b$,

$$|g(h(x+\delta))-g(h(x))|=|g(ax+b+a\delta)-g(ax+b)|<2a\epsilon\tag{3}$$

Assume
$$g(y^\ast_{0})=\min\limits_{x_0\leq y\leq h(x_0)}g(y)$$

$$g(y^\ast_{\Delta})=\min\limits_{x_0-\delta\leq y\leq h(x_0+\delta)}g(y)$$

For any $x\in [x_0-\delta, x_0+\delta]$,

$$g(y^\ast_{x})=\min\limits_{x\leq y\leq h(x)}g(y)$$

Apparently, $g(y^\ast_{\Delta})\leq g(y^\ast_{x})$, $g(y^\ast_{\Delta})\leq g(y^\ast_0)$, and $f(x)=g(y^\ast_x)$, $f(x_0)=g(y^\ast_0)$.

So,

$$
\begin{aligned}
|f(x)-f(x_0)|&=|g(y^\ast_x)-g(y^\ast_0)| \\
&= |g(y^\ast_x)-g(y^\ast_\Delta)+g(y^\ast_\Delta)-g(y^\ast_0)|\\
&\leq |g(y^\ast_x)-g(y^\ast_\Delta)|+|g(y^\ast_0)-g(y^\ast_\Delta)|
\end{aligned}\tag{4}
$$


According the location of $y^\ast_\Delta$, there are three cases possible for $\| g(y^\ast_x)-g(y^\ast_\Delta) \|$ :

(a).  $y^\ast_\Delta= y^\ast_x$, if $y^\ast_\Delta\in [x, h(x)]$.

In this case, $|g(y^\ast_x)-g(y^\ast_\Delta)|=0$.

(b). $y^\ast_\Delta\in [x-\delta, x]\subset [x_0-\delta, h(x_0+\delta)]$.

In this case, $|g(y^\ast_x)-g(y^\ast_\Delta)|\leq |g(x)-g(y^\ast_\Delta)|<2\epsilon$.

(c). $y^\ast_\Delta\in [h(x), h(x+\delta)]\subset [x_0-\delta, h(x_0+\delta)]$.

In this case, becase $|h(x+\delta)-h(x)|<2\epsilon$,
$$y^\ast_\Delta\in [h(x), h(x+\delta)]\subset [h(x), h(x)+2\epsilon]$$.

So, $|g(y^\ast_x)-g(y^\ast_\Delta)|\leq |g(h(x))-g(y^\ast_\Delta)|<2a\epsilon$ (according to Eq. (3)).

Therefore, frome the three cases, we can get

$$|g(y^\ast_x)-g(y^\ast_\Delta)|<\max\{2\epsilon, 2a\epsilon\}$$.

Because $g(y^\ast_0)$ is a special situation of $g(y^\ast_x)$ when $x=x_0$, there is also

$$|g(y^\ast_0)-g(y^\ast_\Delta)|<\max\{2\epsilon, 2a\epsilon\}$$.

Eq. (4) can be written to be:

$$|f(x)-f(x_0)|<2\max\{2\epsilon, 2a\epsilon\}$$.

The right term of above formula is only related with $\epsilon$ and a fixed number $a$. The continuity of $f(x)$ is proved.
$$\hspace{300pt}\Box$$
