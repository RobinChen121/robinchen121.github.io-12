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



This paper characterize some features of the optimal ordering policy for the problem --- "capacitated stochastic inventory problem with fixed costs".  It proposes a definition  of CK convexity.


<font color="#FF4500">This paper is not very long, but is very concise in its wonderful proofs. </font>

# 1. Problem description

$L(y)$ is the expected one-period holding/backorder cost.

$$
L(y)=E[h(y-D)^++p(y-D)^-]
$$

$p$ is the unit backorder cost.

$$
J(y) = cy+L(y)
$$

It can be easily shown that $J(y)$ is convex. Also assume $J(y)\rightarrow \infty$ as $\|y\|\rightarrow\infty$ (for proving the convexity or CK convexity of a induction expression).

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

$\alpha$ is the dicount factor and $I\\{A\\}$ is a unit step function.


# 2. CK-convexity


**CK convex**: Given a non-negative $C$ and $K$, we call the function $G:\mathbb{R}\rightarrow \mathbb{R}$ CK-convex if for all $y$, $b>0$, $z\in[0, C]$，

$$K+G(y+z)\geq G(y)+\frac{z}{b}\{G(y)-G(y-b)\}$$

**strong CK convex** Given a non-negative $C$ and $K$, we call the function $G:\mathbb{R}\rightarrow \mathbb{R}$ strong CK-convex if for all $y$, $b>0$, $a\geq 0$, $z\in[0, C]$，

$$K+G(y+z)\geq G(y)+\frac{z}{b}\{G(y-a)-G(y-a-b)\}$$

When $a=0$, strong CK-convex is CK-convex.

Properties of CK-convex:

1.If $G$ is strong CK-convex, it is also DL-convex for any $0\leq D\leq C$ and $L\geq K$.
2.If $G$ is convex, it is also strong CK-convex.
3.If $G_1$ is strong CK-convex, and $G_2$ is strong CL-convex, then for $\alpha, \beta\geq 0$, $\alpha G_1+\beta G_2$ is strong $C(\alpha K+\beta L)$ convex.
4.If $G$ is strong CK-convex and $X$ is a random variable such that $E[\|G(y-x)\|]<\infty$, then $E[\|G(y-x)\|]$ is strong CK convex.

# 3.Optimal policy structure

Define the following:

$$
G^{\ast}=\inf_{y\in\mathbb{R}} G(y)
$$

$$
S = \inf\{y\in\mathbb{R}|G(y)=G^\ast\}
$$

$$
\tilde{G}(x)=K+\inf_{x\leq y\leq x+C}G(y)
$$

$$
\begin{aligned}
A(x)&=\tilde{G}(x)-G(x)\\
s&=  \inf\{x|A(x)\geq 0\}\\
s'&=\max\{x\leq S|A(x)\leq 0\}
\end{aligned}
$$

Clearly $-\infty\leq s\leq s'\leq S$ (<font color="#FF4500"> so $s$ might not exist when it's $-\infty$, when $x<s$, it is always better to order $C$, when $x>s'$, it is always better to not order </font>) It is easy to understand $s$, $s'$ and the following lemma by drawing a picture.

Also define:

$$
\begin{aligned}
G_C(x)&=K+G(x+C)\\
\overline{G}(x)&=K+ \inf_{s'\leq y\leq x+C}G(y), \qquad s'-C\leq x\leq s'\\
I_+&=I\{s'-C>s\}\\
I_-&=I\{s>s'-C\}
\end{aligned}
$$

An important lemma below.

**Lemma** Under the assumption $\|S\|$ is finite (guarantee the optimal point exist).

1.$G$ is non-increasing on $(-\infty, s')$ and stricty decreasing on $(\infty, s)$.
2.$A(x)\geq 0, \forall x>s'$. (means it's always not to order when $x>s'$).
3.Let

$$H(x)=\inf_{x\leq y\leq x+C}\{K I\{y>x\}+G(y)\}=\min\{G(x), \tilde{G}(x)\}$$

Then,

$$
H(x)=\begin{cases}
G_C(x), \qquad & x<\min\{s'-C, s\},\\
\min\{G(x), G_C(x)\}I_++\overline{G}(x)I_-\qquad & \min\{s'-C, s\}\leq x<\max\{s'-C, s\}.\\
\min\{G(x), \overline{G}(x)\}, & \max\{s'-C, s\}\leq x\leq s',\\
G(x), & s'<x
\end{cases}
$$

4.$H(x)$ is strong CK-convex.

*Proof.*
1. for any two values $x_1$, $x_2$ and $s'>x_1>x_2$, by strong CK convexity,


Since $A(x)\leq 0$ when $x\leq s'$, let $z^\ast$ be the point where $G(s'+z^\ast)=\inf_{0\leq z\leq C} G(s'+z )$, so

$$K+ G(s'+z^\ast )\leq G(s')$$

By strong CK convexity,

$$
K+G(s'+z^\ast)\geq G(s')+\frac{z^\ast}{x_1-x_2}(G(x_1)-G(x_2))
$$

From the above expressions, we can obtain
$$
G(x_1)\leq G(x_2)
$$

That is, $G$ is non-increasing on $(-\infty, s')$.

For $s>x_1>x_2$，since $A(x)\leq 0$ when $x< s$, let $z^\ast$ be the point where $G(x_1+z^\ast)=\inf_{0\leq z\leq C} G(s'+z )$, so

$$K+ G(x_1+z^\ast )< G(x_1)$$

By strong CK convexity,

$$
K+G(x_1+z^\ast)\geq G(x_1)+\frac{z^\ast}{x_1-x_2}(G(x_1)-G(x_2))
$$

We can obtain
$$
G(x_1)< G(x_2)
$$

That is, $G$ is strictly decreasing on $(-\infty, s)$.

2. By definition, this property is true when $x\in(s', S]$, when $x>S$, for any $z\in[0, C]$, from CK convexity,
$$
K+G(x+z)\geq G(x)+\frac{z}{x_1-x_2}(G(x)-G(S))
$$

Since $G(x)\geq G(S)$,
$$
K+G(x+z)\geq G(x)
$$

This leads to $A(x)\geq 0$.

3.
(1) Since $x<\min\{s'-C, s\}$, $x+C\leq s'$, because G is non-increasing in $(-\infty, s')$, $H(x)=G_C(x)$.

(2) When $x>s'$, since $A(x)\geq 0$, $H(x)=G(x)$.

(3) When $\max\{s'-C, s\}\leq x\leq s'$, $s'\leq x+C$. $H(x)$ is the minimum value of $G(x)$ in the range $[x, x+C]$, so
$$H(x)=\min\{G(x), \overline{G}(x)\}$$

(4) When  $\min\{s'-C, s\}\leq x<\max\{s'-C, s\}$, $x+C<s'$,

if $s'-C\geq s$, $s\leq x\leq s'-C$, $s+C\leq x+C\leq s'$, may order  $C$ or not order, $H(x)=\min\{G(x), G_C(x)\}I^+$;

if $s'-C< s$, $x<s$, always order to the point in $[s', x+C]$, $H(x)=\overline{G}(x)I^-$.

4. For three values $x+z$, $x$, $x-a$, $x-a-b$ in the domin.

There are several scenarios according to the values of $H(x+z)$ and $H(x-a-b)$. Let $\Delta$:

$$
\Delta=K+H(x+z)-H(x)-\frac{z}{b}(H(x-a)-H(x-a-b))
$$

We need to prove that $\Delta\geq0$.

(1) $H(x+z)=G(x+z)$, $H(x-a-b)=G(x-a-b)$.

Since $H(x)=\min\{G(x), \tilde{G}(x)\}$, $H(x)\leq G(x)$; Similarly, $H(x-a)\leq G(x-a)$,
$$\Delta\geq K+G(x+z)-G(x)-\frac{z}{b}(G(x-a)-G(x-a-b))\geq 0$$

The above equation holds from the CK-convexity of $G$.

(2) There exists $u_1\in[0,C]$ and $u_2\in[0,C]$, where $H(x+z)=\tilde{G}(x+z)=K+G(x+z+u_1)$, $H(x-a-b)=\tilde{G}(x-a-b)=K+G(x-a-b+u_2)$.

$$
\begin{align}
\Delta=&K+\tilde{G}(x+z)-H(x)-\frac{z}{b}(H(x-a)-\tilde{G}(x-a-b))
\end{align}$$

(a). $z+u_1\leq C$.

In this situation, $H(x)\leq \tilde{G}(x+z)$.



&nbsp;&nbsp;&nbsp;&nbsp; (I) $-b+u_2> 0$.

&nbsp;&nbsp;&nbsp;&nbsp; In this situation, $\tilde{G}(x-a-b)=K+G(x-a-b+u_2)\geq H(x-a)$, so

$$
\begin{align}
\Delta=&K+\tilde{G}(x+z)-H(x)-\frac{z}{b}(H(x-a)-\tilde{G}(x-a-b))\\
\geq &K\geq 0
\end{align}
$$

&nbsp;&nbsp;&nbsp;&nbsp; (II) $-b+u_2\leq 0$.

&nbsp;&nbsp;&nbsp;&nbsp; In this situation,  since $H(x)\leq K+G(x+u_1)$, $H(x-a)\leq K+G(x-a)$,

$$
\begin{align}
\Delta=&K+\tilde{G}(x+z)-H(x)-\frac{z}{b}(H(x-a)-\tilde{G}(x-a-b))\\
\geq &K+K+G(x+z+u_1)-K-G(x+u_1)-\frac{z}{b}(K+G(x-a)-K-G(x-a-b+u_2))\\
=& K+G(x+z+u_1)-G(x+u_1)-\frac{z}{b}(G(x-a)-G(x-a-b+u_2))\\
\geq& K+G(x'+z)-G(x')-\frac{z}{b'}(G(x'-a')-G(x-a'-b'))\geq 0
\end{align}
$$

where $x' = x+u_1\geq z$ and $a'=a+u_1$, $b'=b-u_2$.


(b). $z+u_1> C$.

In this situation,
$$
\begin{align}
\Delta=&K+K+G(x+z+u_1)-H(x)-\frac{z}{b}(H(x-a)-H(x-a-b))\\
\geq & K+G(x+z+u_1)-G(x)-\frac{z}{b}(G(x-a)-G(x-a-b+u_2))\\
\end{align}
$$
&nbsp;&nbsp;&nbsp;&nbsp; (I) $-b+u_2\leq 0$.

$\Delta\geq 0$ is justified by the similar proof with the above.

&nbsp;&nbsp;&nbsp;&nbsp; (II) $-b+u_2> 0$.

In this situation, $H(x-a)\leq K+G(x-a+u_2)$, $H(x)\leq H(x+C)$.

$$
\begin{align}
\Delta=&K+K+G(x+z+u_1)-H(x)-\frac{z}{b}(H(x-a)-H(x-a-b))\\
\geq & K+G(x+z+u_1)-G(x+C)-\frac{z}{b}(G(x-a+u_2)-G(x-a-b+u_2))\\
\geq & K+G(x+z')-G(x+C)-\frac{z'}{b}(G(x-a')-G(x-a'-b))\geq 0
\end{align}
$$

where $z'=z+u_1-C<z$, $a'=a+C-u_2$.

(3) $H(x+z)=K+G(x+z+u_1)$, $H(x-a-b)=G(x-a-b)$.

$$
\begin{align}
\Delta=&K+K+G(x+z+u_1)-H(x)-\frac{z}{b}(H(x-a)-G(x-a-b))\\
\end{align}
$$

Since $H(x)\leq G(x+u_1)$, $H(x-a)\leq G(x-a)$.

$$
\begin{align}
\Delta\geq &K+G(x+z+u_1)-G(x)-\frac{z}{b}(G(x-a)-G(x-a-b))\\
\geq&K+G(x+z)-G(x+u_1)-\frac{z}{b}(G(x+u_1-a-u_1)-G(x+u_1-a-u_1-b))\\
=& K+G(x'+z)-G(x'+u_1)-\frac{z}{b}(G(x'-a')-G(x'-a'))\geq 0
\end{align}
$$

where $x'=x+u_1$, $a'=a+u_1$.  

(4)  $H(x+z)=G(x+z)$, $H(x-a-b)=K+G(x-a-b+u_2)$.
$$
\begin{align}
\Delta= &K+G(x+z)-H(x)-\frac{z}{b}(H(x-a)-K-G(x-a-b+u_2))\\
\end{align}
$$

(a). If $H(x-a)-K-G(x-a-b+u_2)\leq 0$, since $K+G(x+z)-H(x)\geq 0(\because  z\in [0,C])$, $\Delta\geq 0$.

(b). If $H(x-a)-K-G(x-a-b+u_2)>0$,

$$
\begin{align}
\Delta= &K+G(x+z)-H(x)-\frac{z}{b}(H(x-a)-K-G(x-a-b+u_2))
\end{align}
$$

There are two scenarios:

&nbsp;&nbsp;&nbsp;&nbsp; (I) $b-u_2\geq 0$.

$$
\begin{align}
\Delta
\geq& K+G(x+z)-G(x)-\frac{z}{b}(G(x-a)-G(x-a-b+u_2))\\
=&K+G(x+z)-G(x)-\frac{z}{b'}(G(x-a)-G(x-a-b'))
\end{align}
$$

where $b'=b-u_2\leq b$, $\Delta\geq 0$ according to the CK-convexity of $G$.

&nbsp;&nbsp;&nbsp;&nbsp; (I) $b-u_2< 0$.

$$
\begin{align}
\Delta=K+G(x+z)-H(x)-\frac{z}{b}(H(x-a)-K-G(x-a-b+u_2))
\end{align}
$$

Since $H(x-a)\leq K+G(x-a-b+u_2)$, from the assumption $H(x-a)-K-G(x-a-b+u_2)>0$, we know that $H(x-a)= K+G(x-a-b+u_2)$. (<font color="#FF4500"> this condition is very clear, I think it is not very necessary to give a corrigendum in 2016</font>)

$$
\begin{align}
\Delta=K+G(x+z)-H(x)\geq 0
\end{align}
$$

Based on the above scenarios of $H(x+z)$, $H(x-a-b)$ and different bounds of $H(x)$, $H(x-a)$, the CK-convexity of $H$ is justified.

$\Box$
