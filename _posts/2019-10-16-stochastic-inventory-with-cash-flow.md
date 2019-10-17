---
title: Digging into the paper "Dynamic Inventory Management with Cash Flow Constraints".
categories:
- Paper reading
excerpt: |
  I am trying to fully understand the paper "Dynamic Inventory Management with Cash Flow Constraints"

feature_image: "https://picsum.photos/2560/600?/?random"
image: "https://picsum.photos/2560/600?/?random"
---

The paper "Dynamic Inventory Management with Cash Flow Constraints" published in Naval Research Logistics, 2008 gave a pioneering work on multi-period stochastic inventory problem with cash flow constraints.

The functional equation for the problem:

$$
\begin{cases}
V_n(x, w)=\max_{x\leq y\leq x+w/c}V_{n+1}((y-d)^+, p\min\{y, d\}-c(y-x)+w)\\
V_N(x,w)=w+rx
\end{cases}
$$

Now we need to prove the joint concavity of $V_n(x,w)$. This is by induction.

$V_n(x, w)$ is apparently jointly concave for $n=N$.

Assume $V_{n+1}(x, w)$ is jointly concave. We now prove the property for $n$. This is by proving the joint concavity of $V_{n+1}(x, y, w)$ in $x$, $y$ and $w$.

For any $(x_1, y_1, w_1)$, $(x_2, y_2, w_2)$, and $0\leq \lambda\leq 1$, $0\leq \overline{\lambda}\leq 1$, $\lambda+\overline{\lambda}=1$, we need to prove:

$$
\begin{align}
&V_{n+1}((\lambda y_1+\overline{\lambda}y_2-d)^+,p\min\{\lambda y_1+\overline{\lambda}y_2,d\}-c(\lambda y_1+\overline{\lambda}y_2-\lambda x_1)+w)\\
\leq & \lambda V_{n+1}((y_1-d)^+, p\min\{y_1, d\}-c(y_1-\lambda x_1-\overline{\lambda} x_2)+w)\\
& + \overline{\lambda}V_{n+1}((y_2-d)^+, p\min\{y_2, d\}-c(y_2-\lambda x_1-\overline{\lambda} x_2)+w)
\end{align}
$$

Because of the convexity of $(y-d)^+$,

$$
(\lambda y_1+\overline{\lambda}y_2-d)^+\leq \lambda(y_1-d)^++\overline{\lambda}(y_2-d)^+
$$

Because of the concavity of $\min\{y, d\}$,

$$
p\min\{\lambda y_1+\overline{\lambda}y_2,d\}\geq \lambda p\min\{y_1, d\}+\overline{\lambda}p\min\{y_2, d\}
$$

And

$$
\begin{align}
&V_{n+1}((\lambda y_1+\overline{\lambda}y_2-d)^+,p\min\{\lambda y_1+\overline{\lambda}y_2,d\}-c(\lambda y_1+\overline{\lambda}y_2-\lambda x_1-\overline{\lambda} x_2)+w)\}\\
&=V_{n+1}((\lambda y_1+\overline{\lambda}y_2-d)^+,p(\lambda y_1+\overline{\lambda}y_2)-p(\lambda y_1+\overline{\lambda}y_2-d)^+\\
&\quad -c(\lambda y_1+\overline{\lambda}y_2-\lambda x_1-\overline{\lambda} x_2)+w)
\end{align}
$$

Since $V_n(z, A-pz)$ is decreasing in $z$ (this is proved by that the domain of $y$ narrows as the increasing of $z$), we can obtain:



$$
\begin{align}
&V_{n+1}((\lambda y_1+\overline{\lambda}y_2-d)^+,p\min\{\lambda y_1+\overline{\lambda}y_2,d\}-c(\lambda y_1+\overline{\lambda}y_2-\lambda x_1-\overline{\lambda} x_2)+w)\}\\
&\geq V_{n+1}(\lambda(y_1-d)^++\overline{\lambda}(y_2-d)^+,p(\lambda y_1+\overline{\lambda}y_2)-p(\lambda(y_1-d)^++\overline{\lambda}(y_2-d)^+\\
&\quad -c(\lambda y_1+\overline{\lambda}y_2-\lambda x_1-\overline{\lambda} x_2)+w)\\
&=V_{n+1}(\lambda(y_1-d)^++\overline{\lambda}(y_2-d)^+,p\lambda y_1-p\lambda(y_1-d)^--c\lambda (y_1-x_1)\\
&\quad +p\overline{\lambda} y_2-p\overline{\lambda}(y_2-d)^--c\overline{\lambda} (y_2-x_2)+w)\\
&\geq \lambda V_{n+1}((y_1-d)^+, p\min\{y_1, d\}-c(y_1-x_1)+w)\\
&\quad+\overline{\lambda}V_{n+1}((y_2-d)^+, p\min\{y_2, d\}-c(y_2-x_2)+w)
\end{align}
$$

The second inequality is justified by the concavity of $V_{n+1}(x, w)$ from assumption. (<font color = "#FF4500"> I am a little puzzled by this point.  </font>)
