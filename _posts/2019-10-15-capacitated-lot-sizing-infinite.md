---
title: Digging into the paper " the infinite horizon periodic review problem with setup costs".
categories:
- Paper reading
excerpt: |
  I am trying to fully understand the paper "The infinite horizon periodic review problem with setup costs and capacity constraints: a partial characterization of the optimal policy"

feature_image: "https://picsum.photos/2560/600?/?random"
image: "https://picsum.photos/2560/600?/?random"
---

The paper "The infinite horizon periodic review problem with setup costs and capacity constraints: a partial characterization of the optimal policy" published in OR, 2004 is not easy for me to follow.

I am puzzed by the definition of "piecewise concavity". This definition is used for proving the optimal order quantity continues to be an integer if the starting inventory level $x$ is an integer. In the paper, it says $g_1(y)=L(y)+cy$ is piecewise concave. <font color="#FF4500">However, $L(y)$ is a convex function by assumption. Why is this convex function piecewise concave? </font>

Then, this paper proposes a definition of $(C, K)$-convex. By the way, $(C, K)$-convex here is different from the CK-convexity in 0Gallego (2000).


In order to depict the ordering policy for infinite horizon, the author proves the existence of limiting function of the functional equation. This part is very difficult for me. Maybe additional knowledge of convergence is needed to understand it.

In the next step, the $(C, K)$-convexity of the limiting function is proved and the X-Y band policy is given. A liner progromming model is also formulated. I am a little puzzled about the meaning of $\pi_i^k(t)$.
