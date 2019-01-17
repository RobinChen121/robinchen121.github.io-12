---
title: Proof for the continuity of a min function.
categories:
- Paper reading
excerpt: |
  I am trying to prove the continuity of a min function following the mathematical definition.

feature_image: "https://picsum.photos/2560/600?/?random"
image: "https://picsum.photos/2560/600?/?random"
---

Assume a min real function is defined below:

$$
f(x)=\min\limits_{x\leq y\leq h(x)}g(y)
$$

$g(x)$ is continuous. $x\geq 0$, $h(x)=ax+b$, $a\geq 1, b\geq 0$. Prove $f(x)$ is continuous.


$\textit{Proof}.$

<!-- For any $x_0$, there are two cases according to whether $f(x_0)=g(x_0)$.

1. $f(x_0)=g(x_0)$

Because $g(x)$ is continuous. For $x\in[x_0-\delta, x_0+\delta]$, $|g(x)-g(x_0)|<\epsilon$. And by the definition of $f(x)$, $f(x)\leq g(x)$.

   $$|f(x)-f(x_0)|=|f(x)-g(x_0)|\leq |g(x)-g(x_0)|<\epsilon$$


2. $f(x_0)\neq g(x_0)$

There must exist $s$, $x_0\leq s\leq h(x_0)$, such that $f(s)=g(x_0)$. Let $\delta=s-x_0$ -->


We must prove that for any $\epsilon>0$, there exists $\delta>0$, such that when $|x-x_0|<\delta$,

$$|f(x)-f(x_0)|<\epsilon$$

Because $g(x)$ is continous, for any $\epsilon_1>0$, there exits $\delta_1$, when $|x-x_0|<\delta_1$,

$$|g(x)-g(x_0)|<\epsilon_1\tag{1}$$

<!-- Because $h(x)$ is linear, it is also continuous. For any $\epsilon_2>0$, there exists $\delta_2$, when $|x-x_0|<\delta_2$,

$$|h(x)-h(x_0)|<\epsilon_2\tag{2}$$ -->

$g(x)$ is also continous on $x=h(x_0)$. For any $|f(x)-f(x_0)|>0$, there exists $\delta_2$, when $|h(x)-h(x_0)|<\delta_2$,

$$|g(h(x))-g(h(x_0))|<\epsilon_2\tag{2}$$

For any two number $x_1$, $x_2$ in the domain $[x_0-\delta, x_0+\delta]$, let $\delta\leq \delta_1$, we can get

$$
\begin{aligned}
|g(x_1)-g(x_2)|&=|g(x_1)-g(x_0)+g(x_0)-g(x_2)|\\
&\leq |g(x_1)-g(x_0)|+|g(x_0)-g(x_2)|<2\epsilon_1
\end{aligned}\tag{3}
$$

<!-- In a similar way, for any two number $x_1$, $x_2$ in the domain $[x_0-\delta, x_0+\delta]$, we can get

$$
\begin{aligned}
|h(x_1)-h(x_2)|&=|h(x_1)-h(x_0)+h(x_0)-h(x_2)|\\
&\leq |h(x_1)-h(x_0)|+|h(x_0)-h(x_2)|<2\epsilon_2
\end{aligned}\tag{5}
$$ -->

In a similar way, for any two number $x_1$, $x_2$ that satisfying $h(x_1), h(x_2)\in [h(x_0)-\delta_2, h(x_0)+\delta_2]$, we can get

$$
\begin{aligned}
|g(h(x_1))-g(h(x_2))|&=|g(h(x_1))-g(h(x_0))+g(h(x_0))-g(h(x_2))|\\
&\leq |g(h(x_1))-g(h(x_0))|+|g(h(x_0))-g(h(x_2))|<2\epsilon_2
\end{aligned}\tag{4}
$$

<!-- Specially, for any two number $x_1$, $x_2$ in the domain $[x_0-\delta, x_0+\delta]$,

$$|g(x_1)-g(x_2)|<2\epsilon\tag{1}$$

We can also get

$$|h(x+\delta)-h(x)|<2\epsilon\tag{2}$$

Because $h(x)$ is linear, without losss of generallity, we asssume $h(x)=ax+b$,

$$|g(h(x+\delta))-g(h(x))|=|g(ax+b+a\delta)-g(ax+b)|<2a\epsilon\tag{3}$$ -->

Assume
$$g(y^\ast_{0})=\min\limits_{x_0\leq y\leq h(x_0)}g(y)$$

$$g(y^\ast_{\Delta})=\min\limits_{x_0-\delta\leq y\leq h(x_0+\delta)}g(y)$$

For any $x\in [x_0-\delta, x_0+\delta]$,

$$g(y^\ast_{x})=\min\limits_{x\leq y\leq h(x)}g(y)$$

Apparently, $g(y^\ast_{\Delta})\leq g(y^\ast_{x})$, $g(y^\ast_{\Delta})\leq g(y^\ast_0)$.

And $f(x)=g(y^\ast_x)$, $f(x_0)=g(y^\ast_0)$.

So,

$$
\begin{aligned}
|f(x)-f(x_0)|&=|g(y^\ast_x)-g(y^\ast_0)| \\
&= |g(y^\ast_x)-g(y^\ast_\Delta)+g(y^\ast_\Delta)-g(y^\ast_0)|\\
&\leq |g(y^\ast_x)-g(y^\ast_\Delta)|+|g(y^\ast_0)-g(y^\ast_\Delta)|
\end{aligned}\tag{5}
$$


According the location of $y^\ast_\Delta$, there are three cases possible for $\| g(y^\ast_x)-g(y^\ast_\Delta) \|$ :

(a).  $y^\ast_\Delta= y^\ast_x$, if $y^\ast_\Delta\in [x, h(x)]$.

In this case, $\| g(y^\ast_x)-g(y^\ast_\Delta) \|=0$.

(b). $y^\ast_\Delta\in [x-\delta, x]\subset [x_0-\delta, x_0+\delta]$.

In this case, let $\delta\leq \delta_1$, $\| g(y^\ast_x)-g(y^\ast_\Delta) \|\leq \| g(x)-g(y^\ast_\Delta) \|<2\epsilon_1$. (because of Eq. (3))

(c). $y^\ast_\Delta\in [h(x), h(x_0+\delta)]\subset [h(x_0-\delta), h(x_0+\delta)]$.

In this case, select a $\delta$ satisfying $[h(x_0-\delta), h(x_0+\delta)]\subset [h(x_0)-\delta_2, h(x_0)+\delta_2]$. That is, according $h(x)=ax+b$,

$$
\begin{aligned}
ax_0+b-\delta_2\leq &a(x_0-\delta)+b \\
ax_0+b+\delta_2\geq &a(x_0+\delta)+b
\end{aligned}
$$

Just let $\delta\leq \delta_2$,

<!-- becase $|h(x+\delta)-h(x)|<2\epsilon$,
$$y^\ast_\Delta\in [h(x), h(x+\delta)]\subset [h(x), h(x)+2\epsilon]$$. -->

$\| g(y^\ast_x)-g(y^\ast_\Delta) \|\leq \| g(h(x))-g(y^\ast_\Delta) \|<2\epsilon_2$ (according to Eq. (4)).

Therefore, from the three cases, when $\delta\leq\min\{\delta_1, \delta_2\}$, we can get

$$| g(y^\ast_x)-g(y^\ast_\Delta) |<\max\{2\epsilon_1, 2\epsilon_2\}$$

Because $g(y^\ast_0)$ is a special situation of $g(y^\ast_x)$ when $x=x_0$, there is also

$$|g(y^\ast_0)-g(y^\ast_\Delta)|<\max\{2\epsilon_1, 2\epsilon_2\}$$

Eq. (6) can be written to be:

$$|f(x)-f(x_0)|<2\max\{2\epsilon_1, 2\epsilon_2\}$$

Let $\max\{\epsilon_1, \epsilon_2\}=\epsilon$, we can get $|f(x)-f(x_0)|<\epsilon$. The continuity of $f(x)$ is proved.
$$\hspace{300pt}\Box$$
