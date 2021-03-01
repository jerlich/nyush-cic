# Glossary

There are a lot of technical terms that covered in the class. The idea here is to list and define the terms, with links back to the textbook/course material.

## Definitions 
| **Term**   | Definition | Defined at | Notes |
|-------:|:----------|:-----------:|--------|
| Identifiability | A causal quantity (e.g. 𝔼[𝑌(𝑡)]) is identifiable if we can compute it from a purely statistical quantity (e.g. $`E[Y \vert t]`$ ). | Chapter 2.1 | |
| Bayesian Network Factorization | Given a probability distribution 𝑃 and a DAG 𝐺, 𝑃 factorizes according to 𝐺 if $`P(x_1 ... x_n) = \prod_i P(x_i \vert pa_i)`$ | Chapter 3.1 | |
| Cause |  A variable 𝑋 is said to be a cause of a variable 𝑌 if 𝑌 can change in response to changes in 𝑋. | Chapter 3.2 | |
| Blocked Path | A path between nodes 𝑋 and 𝑌 is blocked by a (potentially empty) conditioning set 𝑍 if either of the following is true: 1. Along the path,there is a chain···→𝑊 →··· or a fork · · · ← 𝑊 → · · ·, where 𝑊 is conditioned on (𝑊 ∈ 𝑍). 2. There is a collider 𝑊 on the path that is not conditioned on (𝑊 ∉ 𝑍) and none of its descendants are conditioned on. | Chapter 3.3 | | 
| d-separation | Two (sets of) nodes 𝑋 and 𝑌 are d-separated by a set of nodes 𝑍 if all of the paths between (any node in) 𝑋 and (any node in) 𝑌 are blocked by 𝑍 | Chapter 3.4 | |


## Assumptions
| Term   | Definition | Defined at | Notes |
|-------:|:----------|:-----------:|--------|
| Ignorability / Exchangeability | Ignoring how people ended up in the treatment groups as if they were randomly assigned. $`(𝑌(1), 𝑌(0)) \perp\!\!\! \perp 𝑇  `$| Chapter 2.1   |  |
| Conditional Exchangeability / Unconfoundedness | Conditioning on X has made the treatment groups comparable. $`(𝑌(1), 𝑌(0)) \perp \!\!\! \perp 𝑇 \vert 𝑋  `$| Chapter 2.2 | |
| Positivity | For all values of covariates 𝑥 present in the population of interest (i.e. 𝑥 such that 𝑃(𝑋 = 𝑥) > 0), $ 0 < P(T = 1 \vert  X = x) < 1 $ | Chapter 2.3 | |
| No interference | My outcome is not affected by anyone else's treatment. | Chapter 2.4 | |
| Consistency | If treatment is T, the observed outcome Y is the potential outcome under treatment T. $ Y = Y(T) $| Chapter 2.5 | |
| Local Markov | Given its parents in the DAG, a node X is independent of all its non-descendants. This allows for Bayesian Network factorization. | Chapter 3.1 | |
| Minimality | In addition to 3.1, all adjacent nodes in the DAG are dependent for causal graphs. (minimising independencies) | Chapter 3.2 | |
| Causal Edge | In a directed graph, every parent is a direct cause of all its children | Chapter 3.3| |

## Theorems
* **2.1 Adjustment Formula**: Given unconfoundedness, positivity, no interference and consistency, average treatment effect becomes
$$ \begin{aligned}
E(Y(1) - Y(0)] &= E_xE(Y(1) - Y(0)|X] \\
&= E_x[E[Y|T=1,X] - E[Y|T=0,X]] \\
\end{aligned}
$$
*  **3.1 Global Markov**: Given that 𝑃 is Markov with respect to 𝐺 (satisfies the local Markov assumption, Assumption 3.1), if 𝑋 and 𝑌 are d-separated in 𝐺 conditioned on 𝑍, then 𝑋 and 𝑌 are independent in 𝑃 conditioned on 𝑍. We can write this succinctly as follows:
$$ 𝑋 \perp \!\!\! \perp_G 𝑌|𝑍 \Longrightarrow 𝑋\perp \!\!\! \perp_P 𝑌|𝑍 $$ 

