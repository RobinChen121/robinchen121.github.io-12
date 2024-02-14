---
title: A query about one paper
categories:
- Paper reading
excerpt: |
  Recently, I am reading the paper "Dynamic Inventory Management with Cash Flow Constraints" from Xiuli Chao, et. al (2008).  The proofs in this paper are very lengthy and complex. During the deductions of the proofs by myself, there is a query that I can not understand.
tags: [dynamic programming, stochastic inventory]
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Recently, I am reading the paper "Dynamic Inventory Management with Cash Flow Constraints" from Xiuli Chao, et. al (2008).  The proofs in this paper are very lengthy and complex. During the deductions of the proofs by myself, there is a query that I can not understand.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Among the proof for Theorem 2 in the appendix, it wrote:

$$
\begin{aligned}
\tilde{V}_n(x, R)=&~V_n(x, S)\\
=&~ V_n(x, R-cx)\\
=&~ \max_{x\leq y\leq R/c}\pi_n(y, R)\\
=&~ \max_{x\leq y\leq R/c}E\left[\tilde{V}_{n+1}((y-D)^+, ~(p-c)\min\{y, D\}+(1+d)R-dcy)\right]
\end{aligned}
$$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In the last term, I can not understand why it is $(p-c)\min\\{y, D\\}$, because on page 761, it wrote:

$$
\pi_n(y, R)=E\left[V_{n+1}((y-D)^+, ~p\min\{y, D\}+(1+d)(R-cy))\right]
$$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;So, I think the last term should be:

$$
\max_{x\leq y\leq R/c}E\left[\tilde{V}_{n+1}((y-D)^+, ~(p-c)\min\{y, D\}+(1+d)R-dcy-cy+c\min\{y, D\})\right]
$$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Why is $y=\min\\{y, D\\}$? This may affect the main conclusions of this paper. In the extension paper of Xiting Gong et. al (2014), I also noted the same problem. In page 188, the author wrote:

$$
\pi_n(y, R)=E\left[\tilde{V}_{n+1}((y-D)^+, ~(p-c)\min\{y, D\}+\phi(R-cy))+cy\right]
$$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I do not know why it is $(p-c)\min\\{y, D\\}$, either. Is it the error of this paper or my incorrect understanding?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I also do some numerical tests for the numerical examples in the paper. I note that the authors do not give the value of initial capital in the numerical example. My results by stochastic dynamic programming seems not to conincide with the results in the paper. Moreover, in the numerical setting, mean demand and variance are both 10, which is too big and can cause negative demand values.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Given the above query, I decide to quit perusing this paper. But the conclusion of the paper about the optimal ordering policy is right: a base-stock policy for the cash caontrained problem. But its computation for the base-stock level may exit some bug. 

<!-- more -->
