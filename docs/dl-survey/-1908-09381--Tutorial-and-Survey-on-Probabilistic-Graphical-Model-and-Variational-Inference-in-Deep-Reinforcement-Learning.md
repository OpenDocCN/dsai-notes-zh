<!--yml

类别：未分类

日期：2024-09-06 20:05:19

-->

# [1908.09381] 深度强化学习中的**概率图模型**和**变分推断**教程与综述

> 来源：[`ar5iv.labs.arxiv.org/html/1908.09381`](https://ar5iv.labs.arxiv.org/html/1908.09381)

# 深度强化学习中的**概率图模型**和**变分推断**教程与综述

**徐东** 统计学系

路德维希·马克西米利安大学

慕尼黑，德国

邮箱：xudong.sun@stat.uni-muenchen.de    **伯恩德·比施尔** 统计学系

路德维希·马克西米利安大学

慕尼黑，德国

###### 摘要

本文旨在提供一个全面且简洁的教程综述，详细推导了变分推断和使用**概率图模型**的强化学习。对深度强化学习的最新进展进行了各个方面的综述和比较。我们提供了深度强化学习中概率图模型和变分推断方法的详细推导，这些内容作为原始贡献的补充材料。

###### 关键词：

**概率图模型**；**变分推断**；深度强化学习

## 引言

尽管最近通过深度神经网络在复杂任务如游戏[1]和机器人运动[2]以及自动机器学习[3]等优化任务中取得了成功，该领域仍面临许多挑战，包括高维状态和策略的表达、稀疏奖励中的探索等。**概率图模型**和**变分推断**提供了表达广泛轨迹分布的强大工具，并可以进行推断，作为控制方法。由于其新兴的流行性，我们呈现了一篇全面且简洁的教程综述论文，包含以下贡献：

+   •

    我们为强化学习中的许多基本概念提供了**概率图模型**，这些内容在文献中很少涉及。我们还为一些最近的深度强化学习工作提供了**概率图模型**[4, 5]，这些内容在原始贡献中并不存在。

+   •

    我们涵盖了深度强化学习中使用的**概率图模型**和**变分推断**[6]方法的分类，并对许多关键方程进行了详细推导，这些内容在原始贡献中没有提供。结合变分推断和深度强化学习的回顾，本文作为一个自包含的教程，适用于初学者和高级读者。

### I-A 论文组织

在章节 I-B 中，我们首先介绍概率图模型和变分推断的基础知识，然后通过在章节 II-A、II-B、II-C 中回顾强化学习的基础知识，并概述深度强化学习的不同方法，在章节 II-D 中进行比较。在章节 III-A 中，我们讨论了如何使用无向图来建模值函数和策略，这在高维离散状态和动作空间中效果良好。在章节 III-B 中，我们介绍了如何将策略视为动作的后验的有向无环图框架，同时添加了许多原始贡献中不存在的证明。在章节 III-C 中，我们介绍了如何使用变分推断来近似环境模型，并添加了原始贡献中不存在的图模型和证明。

### I-B 概率图模型和变分推断的先决条件、术语和约定

我们使用大写字母来表示随机变量（RV），而使用小写字母来表示其实现。为了避免在许多强化学习文献中使用 $A$ 来表示优势时符号冲突，我们明确使用 $A^{act}$ 来表示动作。我们用 $(B\mathrel{\text{\scalebox{1.07}{$\perp\mkern-10.0mu\perp$}}}C)\mid A$ 表示 $B$ 在给定 $A$ 的条件下与 $C$ 条件独立，或等价地 $p(B|A,C)=p(B|A)$ 或 $p(BC|A)=P(B|A)P(C|A)$。有向无环图（DAG）[7] 作为概率图模型提供了一种直观的方法，通过 d-分离 [7] 假设条件独立来定义随机变量的分解联合分布 [7]。无向图，包括马尔可夫随机场，也通过局部马尔可夫性质和全局马尔可夫性质来指定条件独立 [8]。

变分推断（VI）通过变分提议后验分布 $q_{\phi}(z\mid x)$（由变分参数 $\phi$ 表征）来逼近在概率图模型中指定的不可处理的后验分布 $p(z\mid x)=\frac{1}{\int_{z^{{}^{\prime}}}p(z^{{}^{\prime}})p(x|z^{{}^{\prime}})dz^{{}^{\prime}}}p(z)p(x\mid z)$。通过优化证据下界（ELBO）[6]，变分推断同时为观察到的变量和潜在变量赋值。变分推断在深度学习社区中被广泛使用，如变分重采样 [9]。变分推断还用于逼近神经网络权重分布的后验，以解决在多臂老虎机问题中的探索-利用权衡 [10]，以及逼近激活分布，如变分自编码器 [11]。

作为本文的贡献，我们总结了证据 $\log p(x)$、KL 散度 $D_{KL}$、交叉熵 $H_{q}(p)$、熵 $H(q)$、自由能 $F(\phi,\theta)$ 和 $ELBO(\phi,\theta)$ 在方程 (1) 中的关系。

|  |  | $\displaystyle\log p(x)$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle E_{q}\left[\log p(x\mid z)\right]-E_{q}\left[\log\frac{q_{\phi}{(z\mid x)}}{p(z)}\right]+E_{q}\left[\log\frac{q_{\phi}{(z\mid x)}}{p(z\mid x)}\right]$ |  |
|  | $\displaystyle=$ | $\displaystyle-D_{KL}(q_{\phi}(z&#124;x)&#124;&#124;p(x,z))-E_{q}\left[\log p(z&#124;x)\right]+$ |  |
|  |  | $\displaystyle E_{q}\log q_{\phi}(z&#124;x)$ |  |
|  | $\displaystyle=$ | $\displaystyle-F(\phi,\theta)+H_{q}(p)-H(q)$ |  |
|  | $\displaystyle=$ | $\displaystyle ELBO(\phi,\theta)+D_{KL}(q_{\phi}(z\mid x)&#124;&#124;p(z\mid x))$ |  | (1) |

## II 强化学习与深度强化学习

### II-A 关于图模型的强化学习基础

\includegraphics

[scale=0.6]tikz_rl_def.pdf

图 1：强化学习的概念

#### II-A1 RL 概念、术语和约定

如图 1 所示，强化学习（RL）涉及通过与环境的交互来优化智能体的行为。在时间 $t$，智能体处于状态 $S_{t}$，通过按照策略 [12] $\pi(a|S_{t})$ 执行动作 $a_{t}$，智能体跳到另一个状态 $S_{t+1}$，同时获得奖励 $R_{t}$。折扣因子 $\gamma$ 决定了即时奖励相对于长期回报的优先级，同时也可以在无限视野强化学习中允许可处理性 [12]，以及在蒙特卡罗设置中减少方差 [13]。目标是最大化累计奖励 $G=\sum_{t=0}^{T}\gamma^{t}R_{t}$，这通常在 RL 文献中称为回报。

为了简化，我们在方便时交替使用两种约定：假设一个回合持续从 $t=0:T$，其中 $T\rightarrow\infty$ 对应于连续非回合制强化学习。我们使用另一种约定 $t\in\{0,\cdots,\infty\}$，假设当回合结束时，智能体保持在一个自我吸收状态中，采取无效动作，同时获得零奖励。

通过展开图 1，我们得到一个由状态、动作和奖励元组 $\{(S_{t},A^{act}_{t},R_{t})\}$ 组成的序列，这个序列被称为轨迹 $\tau$ [14]。图 2 说明了一个回合中轨迹的部分。状态空间 $\mathcal{S}$ 和动作空间 $\mathcal{A}$ 可以是离散的、连续的或多维的，在图 2 中各自用一个连续维度表示，并用不同的颜色正交绘制，同时我们使用板的厚度来表示奖励空间 $\mathcal{R}$。

\includegraphics

[scale=0.6]tikz_drl_illustrator.pdf

图 2: 状态、动作和奖励轨迹的插图

#### II-A2 (部分观察的) 马尔可夫决策过程的 DAG

强化学习是一个随机决策过程，通常伴随着三重不确定性。也就是说，在一个特定的随机策略 $\pi(a|s)=p(a|s)$ 下，在一个特定环境中，其状态转移概率 $p(s_{t+1}|s_{t},a)$ 和奖励分布函数 $p(r_{t}|s_{t},a_{t})$，学习代理可以观察到具有不同展开实现的不同轨迹。这通常被建模为马尔可夫决策过程 [12]，其图形模型如图 3 马尔可夫决策过程的 DAG ‣ II-A 图形模型中的强化学习基础 ‣ II 强化学习与深度强化学习 ‣ 深度强化学习中的概率图模型与变分推断教程与调查") 所示，我们可以定义一个状态、动作和奖励随机变量的轨迹上的联合概率分布。在图 3 马尔可夫决策过程的 DAG ‣ II-A 图形模型中的强化学习基础 ‣ II 强化学习与深度强化学习 ‣ 深度强化学习中的概率图模型与变分推断教程与调查") 中，我们使用虚线箭头连接状态和动作来表示策略，在固定策略 $\pi$ 下，我们在方程 (2 马尔可夫决策过程的 DAG ‣ II-A 图形模型中的强化学习基础 ‣ II 强化学习与深度强化学习 ‣ 深度强化学习中的概率图模型与变分推断教程与调查")) 中有轨迹的似然。

|  | $\displaystyle p(\tau)=p(s_{0})\prod_{t=0}^{T}p(s_{t+1} | s_{t},a_{t})p(r_{t} | s_{t},a_{t})\pi(a_{t} | s_{t})$ |  | (2) |
| --- | --- | --- | --- | --- | --- | --- |

在图 3 马尔可夫决策过程的 DAG ‣ II-A 图形模型中的强化学习基础 ‣ II 强化学习与深度强化学习 ‣ 深度强化学习中的概率图模型与变分推断教程与调查") 中观察到状态 $s_{t}$ 时，在该时间步的动作与状态和动作历史 $\mathcal{E}_{t}=\{S_{0},A^{act}_{0},\cdots,S_{t-1}\}$ 条件独立，这可以表示为 $(A^{act}_{t}\mathrel{\text{\scalebox{1.07}{$\perp\mkern-10.0mu\perp$}}}\mathcal{E}_{t})\mid S_{t}$。

\includegraphics

[scale=0.7]tikz_pgm_mdp.pdf

图 3: 马尔可夫决策过程的有向无环图

更现实的模型是部分可观察的马尔可夫决策过程 [15]，其有向无环图（DAG）表示如图 4 Markov Decision Process ‣ II-A Basics about Reinforcement Learning with graphical model ‣ II Reinforcement Learning and Deep Reinforcement Learning ‣ Tutorial and Survey on Probabilistic Graphical Model and Variational Inference in Deep Reinforcement Learning")所示，其中代理只能通过不可逆函数观察到状态的部分信息，即通过观测到的 $O_{t}$ 和下一个状态 $S_{t+1}$ 以及动作 $a_{t}$，如图中 $p(o_{t}|s_{t+1},a_{t})$ 所示，而其他边的分布被省略，因为它们与图 3 Markov Decision Process ‣ II-A Basics about Reinforcement Learning with graphical model ‣ II Reinforcement Learning and Deep Reinforcement Learning ‣ Tutorial and Survey on Probabilistic Graphical Model and Variational Inference in Deep Reinforcement Learning")中的相同。在图 4 Markov Decision Process ‣ II-A Basics about Reinforcement Learning with graphical model ‣ II Reinforcement Learning and Deep Reinforcement Learning ‣ Tutorial and Survey on Probabilistic Graphical Model and Variational Inference in Deep Reinforcement Learning")的图形规格下，可观察到的 $O_{t}$ 不再是马尔可夫的，而是依赖于整个历史，但潜在状态 $S_{t}$ 仍然是马尔可夫的。对于 POMDP，信念状态 $b_{t}$ 在时间 $t$ 被定义，它与潜在状态 $S_{t}$ 上的概率分布 $b_{t}(s_{t})$ 相关，其中 $\sum_{\mathcal{S}}b(S_{t})=1$，其中状态 $S$ 取值于潜在状态空间 $\mathcal{S}$ [15]。

\includegraphics

[scale=0.8]tikz_pgm_pomdp.pdf

图 4: POMDP 的概率图模型

与信念状态相关的潜在状态分布可以在方程 (6 Markov Decision Process ‣ II-A Basics about Reinforcement Learning with graphical model ‣ II Reinforcement Learning and Deep Reinforcement Learning ‣ Tutorial and Survey on Probabilistic Graphical Model and Variational Inference in Deep Reinforcement Learning")) 中以贝叶斯方式更新。

|  |  | $\displaystyle b_{t+1}(s_{t+1})$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle p(s_{t+1}\mid o_{t},a_{t},b_{t})$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(s_{t+1},o_{t},a_{t},b_{t})}{p(o_{t},a_{t},b_{t})}\frac{p(s_{t+1},a_{t},b_{t})}{p(s_{t+1},a_{t},b_{t})}$ |  |
|  | $\displaystyle=$ | $\displaystyle p(o_{t}\mid a_{t},s_{t+1},b_{t})\frac{p(s_{t+1}\mid a_{t},b_{t})}{p(o_{t}\mid a_{t},b_{t})}$ |  | (3) |
|  | $\displaystyle=$ | $\displaystyle p(o_{t}\mid s_{t+1},a_{t})\frac{\sum_{{s_{t}}}p(s_{t},s_{t+1}\mid a_{t},b_{t})}{p(o_{t}\mid a_{t},b_{t})}$ |  | (4) |
|  | $\displaystyle=$ | $\displaystyle p(o_{t}\mid s_{t+1},a_{t})\frac{\sum_{{s_{t}}}p(s_{t+1}\mid s_{t},a_{t},b_{t})p(s_{t}\mid a_{t},b_{t})}{p(o_{t}\mid a_{t},b_{t})}$ |  | (5) |
|  | $\displaystyle=$ | $\displaystyle p(o_{t}\mid s_{t+1},a_{t})\frac{\sum_{{s_{t}}}p(s_{t+1}\mid s_{t},a_{t})p(s_{t}\mid a_{t},b_{t})}{p(o_{t}\mid a_{t},b_{t})}$ |  | (6) |

### II-B 值函数、贝尔曼方程、策略迭代

在方程 (7) 中定义状态 $s\in\mathcal{S}$ 的状态值函数，其中对应的贝尔曼方程在方程 (8) 中推导。

|  |  | $\displaystyle V^{\pi}(s)=E_{\pi,\varepsilon}[\sum_{i=0}^{\infty}\gamma^{i}R_{t+i}(S_{t+i},A^{act}_{t+i})\mid\forall S_{t}=s]$ |  | (7) |
| --- | --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle E_{\pi,\varepsilon}[R_{t}(S_{t},A^{act}_{t})+\gamma\sum_{i=1}^{\infty}\gamma^{(i-1)}R_{t+i}(S_{t+i},A^{act}_{t+i})]$ |  |
|  | $\displaystyle=$ | $\displaystyle E_{\pi,\varepsilon}[R_{t}(S_{t},A^{act}_{t})+\gamma\sum_{i^{{}^{\prime}}=0}^{\infty}\gamma^{i^{{}^{\prime}}}R_{t+1+i^{{}^{\prime}}}(S_{t+1+i^{{}^{\prime}}},A^{act}_{t+1+i^{{}^{\prime}}})]$ |  |
|  | $\displaystyle=$ | $\displaystyle E_{\pi,\varepsilon}[R_{t}(S_{t},A^{act}_{t})+\gamma V^{\pi}(S_{t+1})]$ |  | (8) |

在 $S_{t+i}\sim p(s_{t+i+1}|s_{t+i},a_{t+i})$ 取自 $\mathcal{S}$，$A^{act}_{t+i}\sim\pi(a|S_{t+i+1})$ 取自 $\mathcal{A}$ 的情况下，我们在期望值 $E$ 操作的下标中使用了 $\pi$ 和 $\varepsilon$ 来表示策略和环境（包括转移概率和奖励概率）的概率分布。状态动作值函数 [12] 在方程 (9) 中定义，方程 (10) 中陈述了它与状态值函数的关系。

|  |  | $\displaystyle Q^{\pi}(s,a)\,(\forall S_{t}=s,A^{act}_{t}=a)$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle E_{\pi,\varepsilon}[R_{t}(S_{t}=s,A^{act}_{t}=a)+\sum_{i=1}^{\infty}\gamma^{i}R_{t+i}(S_{t+i},A^{act}_{t+i})]$ |  | (9) |
|  | $\displaystyle=$ | $\displaystyle E_{\pi,\varepsilon}[R_{t}(S_{t}=s,A^{act}_{t}=a)+\gamma V^{\pi}(S_{t+1})]$ |  | (10) |

结合方程 (8) 和方程 (9)，我们得到

|  | $V(s)=\sum_{a}\pi(a\mid s)Q(s,a)$ |  | (11) |
| --- | --- | --- | --- |

定义最优策略 [12] 为

|  | $\displaystyle\pi^{*}$ | $\displaystyle=\underset{\pi}{arg\,max}\,V^{\pi}(s),\forall s\in S$ |  |
| --- | --- | --- | --- |
|  |  | $\displaystyle=\underset{\pi}{arg\,max}\,E_{\pi}[R_{t}+\gamma V^{\pi}(S_{t+1})]$ |  | (12) |

将最优策略 $\pi^{*}$ 代入方程 (8) 中，我们得到

|  | $\displaystyle V^{\pi^{*}}(s)=E_{\pi^{*},\varepsilon}\left[R_{t}(s,A^{act}_{t})+\gamma V^{\pi^{*}}(S_{t+1})\right]$ |  | (13) |
| --- | --- | --- | --- |

将最优策略 $\pi^{*}$ 代入方程 (9) 中，我们得到

|  | $\displaystyle Q^{\pi^{*}}(s,a)=E_{\pi^{*},\varepsilon}[R_{t}(s,a)+\sum_{i=1}^{\infty}\gamma^{i}R_{t+i}(S_{t+i},A^{act}_{t+i})]$ |  | (14) |
| --- | --- | --- | --- |

基于方程 (14) 和方程 (13)，我们得到

|  | $\displaystyle V^{\pi^{*}}(s)=\underset{a}{max}\,Q^{\pi^{*}}(s,a)$ |  | (15) |
| --- | --- | --- | --- |

和

|  | $\displaystyle Q^{\pi^{*}}(s,a)=E_{\varepsilon,\pi^{*}}\left[R_{t}(s,a)+\gamma\underset{\bar{a}}{max}\,Q^{\pi^{*}}(S_{t+1},\bar{a})\right]$ |  | (16) |
| --- | --- | --- | --- |

为了学习最优策略和值函数，可以进行一般策略迭代 [12]，如图 5 所示，其中绘制了一个收敛过程 [12]。从初始策略 $\pi_{0}$ 开始，可以估计相应的值函数 $V^{\pi_{0}}$，这可以通过对动作的贪婪最大化得到改进后的策略 $\pi_{1}$。收敛过程应当收敛到最优策略 $\pi^{*}$。

作为学习算法的理论基础，动态规划和蒙特卡罗学习作为环境完全知识和完全无模型的两个极端 [12]，而时间差分学习 [12] 则更为普遍使用，像一个连接这两个极端的桥梁。时间差分学习基于贝尔曼更新误差 $\delta_{t}=Q(s_{t},a_{t})-\left(R_{t}(s,a)+\gamma\underset{a}{max}\,Q(s_{t+1},a)\right)$。

\includegraphics

[scale=0.6]tikz_gpi.pdf

图 5：一般策略迭代

### II-C 策略梯度与 Actor Critic

强化学习可以被视为一个函数优化过程。我们可以定义一个以策略 $\pi_{\theta}(a|s)$ 为基础的目标函数，这个函数由参数 $\theta$ 表征，$\theta$ 可以对应于神经网络权重，例如。

假设所有的 episodes 从一个辅助初始状态 $s_{0}$ 开始，状态 $s_{0}$ 以概率 $h(s)$ 跳转到不同的状态 $s\in\mathcal{S}$，且没有奖励。$h(s)$ 表征了初始状态分布，这仅依赖于环境。令 $\eta(s)$ 表示在状态 $s$ 上花费的预期步数，这可以通过将从辅助状态 $s_{0}$ 出发的进入状态 $s$ 的 $\gamma$ 折现概率 $P^{\pi}(s_{0}\rightarrow s,k+1)$ 相加来计算，如方程 (17) 中所述，这可以被视为条件在状态 $s$ 下的 $\gamma^{k}$ 的期望。

|  | $\displaystyle\eta(s)$ | $\displaystyle=\sum_{k=0}\gamma^{k}P^{\pi}(s_{0}\rightarrow s,k+1)$ |  | (17) |
| --- | --- | --- | --- | --- |
|  |  | $\displaystyle=h(s)+\sum_{\bar{s},a}\gamma\eta(\bar{s})\pi_{\theta}(a&#124;\bar{s})P(s&#124;\bar{s},a)$ |  | (18) |

在方程 (18) 中，该量可以通过直接从状态 $s$ 开始计算，这对应于方程 (17) 中的 $k=0$，或者通过一步从状态 $\bar{s}$ 进入状态 $s$，对应于方程 (17) 中的 $k+1\geq 2$。

对于任意状态 $s\in\mathcal{S}$，使用 $s^{{}^{\prime}}$ 和 $s^{{}^{\prime\prime}}$ 表示后续状态作为虚拟索引，

|  |  | $\displaystyle\nabla_{\theta}V^{\pi(\theta)}(s)=\nabla_{\theta}\left[\sum_{a}Q^{\pi(\theta)}(s,a)\pi_{\theta}(a&#124;s)\right]$ |  | (19) |
| --- | --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle\sum_{a}\left[\nabla_{\theta}Q^{\pi(\theta)}(s,a)\pi_{\theta}(a&#124;s)+\nabla_{\theta}\pi_{\theta}(a&#124;s)Q^{\pi(\theta)}(s,a)\right]$ |  |
|  | $\displaystyle=$ | $\displaystyle\sum_{a}\nabla_{\theta}\left[\sum_{s^{{}^{\prime}},R}P(s^{{}^{\prime}},R&#124;s,a)\left(R+\gamma V^{\pi(\theta)}(s^{{}^{\prime}})\right)\right]\pi_{\theta}(a&#124;s)$ |  |
|  |  | $\displaystyle+\sum_{a}\nabla_{\theta}\pi_{\theta}(a&#124;s)Q^{\pi(\theta)}(s,a)$ |  | (20) |
|  | $\displaystyle=$ | $\displaystyle\sum_{a}\sum_{s^{{}^{\prime}}}\gamma P(s^{{}^{\prime}}&#124;s,a)\nabla_{\theta}V^{\pi(\theta)}(s^{{}^{\prime}})\pi_{\theta}(a&#124;s)+$ |  |
|  |  | $\displaystyle\sum_{a}\nabla_{\theta}\pi_{\theta}(a&#124;s)Q^{\pi(\theta)}(s,a)$ |  | (21) |
|  | $\displaystyle=$ | $\displaystyle\sum_{a}\nabla_{\theta}\pi_{\theta}(a&#124;s)Q^{\pi(\theta)}(s,a)+\sum_{a}\sum_{s^{{}^{\prime}}}\gamma P(s^{{}^{\prime}}&#124;s,a)\pi_{\theta}(a&#124;s)$ |  |
|  |  | $\displaystyle\left[\sum_{a^{{}^{\prime}}}\sum_{s^{{}^{\prime\prime}}}\gamma P(s^{{}^{\prime\prime}}&#124;s^{{}^{\prime}},a^{{}^{\prime}})\nabla_{\theta}V^{\pi(\theta)}(s^{{}^{\prime\prime}})\pi_{\theta}(a^{{}^{\prime}}&#124;s^{{}^{\prime}})+\right.$ |  |
|  |  | $\displaystyle\left.\sum_{a^{{}^{\prime}}}\nabla_{\theta}\pi_{\theta}(a^{{}^{\prime}}&#124;s^{{}^{\prime}})Q^{\pi(\theta)}(s^{{}^{\prime}},a^{{}^{\prime}})\right]$ |  | (22) |

方程 (22) 中的方括号中的项实际上是方程 (21) 将$a$和$s^{{}^{\prime}}$替换为$a^{{}^{\prime}}$和$s^{{}^{\prime\prime}}$。由于 $\nabla_{\theta}V^{\pi(\theta)}(s^{\infty})=0$，方程 (22) 可以写作方程 (23)，其中$s_{k}$ 表示在$s$之后 $k$ 步的状态，而$P^{\pi}(s\rightarrow s_{k},k)$ 已经包括了在到达状态$s_{k}$之前中间状态 $s_{k-1},\ldots s_{1}$ 的积分。

|  | $\displaystyle\nabla_{\theta}V^{\pi(\theta)}(s)=\sum_{a}\nabla_{\theta}\pi_{\theta}(a&#124;s)Q^{\pi(\theta)}(s,a)+$ |  |
| --- | --- | --- |
|  | $\displaystyle\sum_{k=1}\sum_{s_{k}}\sum_{a_{k}}\gamma^{k}P^{\pi}(s\rightarrow s_{k},k)\nabla_{\theta}\pi_{\theta}(a_{k}&#124;s_{k})Q^{\pi(\theta)}(s_{k},a_{k})$ |  | (23) |

目标函数关于策略的定义为从辅助状态$s_{0}$开始的值函数，如方程 (24) 所示。

|  | $\displaystyle J(\pi_{\theta})=V^{\pi}(s_{0})=E_{\pi,\varepsilon}\sum_{t=0}^{\infty}\gamma^{t}R_{t}(S_{0}=s)$ |  | (24) |
| --- | --- | --- | --- |

最优策略可以通过梯度上升优化获得，从而得到策略梯度算法 [12]，如方程 (29) 所示。

|  |  | $\displaystyle\nabla_{\theta}J(\pi_{\theta})=\nabla_{\theta}V^{\pi}(s_{0})$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle\sum_{k=0}\sum_{s_{k}}\sum_{a_{k}}\gamma^{k}P^{\pi}(s_{0}\rightarrow s_{k},k)\nabla_{\theta}\pi_{\theta}(a_{k}&#124;s_{k})Q^{\pi(\theta)}(s_{k},a_{k})$ |  |
|  | $\displaystyle=$ | $\displaystyle\sum_{s}\sum_{a}\eta(s)\nabla_{\theta}\pi_{\theta}(a&#124;s)Q^{\pi(\theta)}(s,a)$ |  | (25) |
|  | $\displaystyle=$ | $\displaystyle\frac{\sum_{s}\eta(s)}{\sum_{s}\eta(s)}\sum_{s}\sum_{a}\eta(s)\nabla_{\theta}\pi_{\theta}(a | s)Q^{\pi(\theta)}(s,a)$ |  | (26) |
|  | $\displaystyle=$ | $\displaystyle\sum_{\bar{s}}\eta(\bar{s})\sum_{s}\sum_{a}\mu(s)\nabla_{\theta}\pi_{\theta}(a | s)Q^{\pi(\theta)}(s,a)$ |  | (27) |
|  | $\displaystyle=$ | $\displaystyle\sum_{\bar{s}}\eta(\bar{s})\sum_{s}\sum_{a}\mu(s)\frac{\pi_{\theta}(a | s)}{\pi_{\theta}(a | s)}\nabla_{\theta}\pi_{\theta}(a | s)Q^{\pi(\theta)}(s,a)$ |  | (28) |
|  | $\displaystyle\propto$ | $\displaystyle\,E_{\pi}\left[\frac{\nabla_{\theta}\pi_{\theta}(A | S)}{\pi_{\theta}(A | S)}\hat{Q}^{\pi(\theta)}(S,A)\right]$ |  | (29) |

策略梯度可以增强为包含零梯度基准 $b(s)$，关于目标函数 $J(\pi_{\theta})$ 的方程 (28)，作为状态 $s$ 的函数，不包含策略 $\theta$ 的参数，因为 $\sum_{a}\nabla_{\theta}\pi_{\theta}(a|s)=0$。为了减少梯度的方差，基准通常选择为状态值函数估计器 $\hat{V}_{w}(s)$，以平滑每个状态下 $Q(s,a)$ 的变化，同时 $\hat{V}_{w}(s)$ 通过与 $\hat{Q}^{\pi_{\theta}}(S,A)=G_{t}$ 比较的蒙特卡洛方式进行更新。

演员-评论员算法 [12] 将 $G_{t}-V_{w}(s_{t})$ 分解为 $R_{t}+\gamma V_{w}(s_{t+1})-V_{w}(s_{t})$，因此使用引导方法代替了蒙特卡洛方法。

### II-D 深度强化学习基础

深度 Q 学习 [1] 在将神经网络用作复杂任务中值函数的功能逼近器方面取得了突破。它通过从重放记忆中随机抽样来解决转移相关问题。具体而言，强化学习被转化为一个监督学习任务，通过在目标 $R_{t}+\gamma\underset{a}{max}\,Q(s_{t+1},a)$ 上进行拟合，输入为状态 $s_{t}$ 的重放记忆。然而，目标可能会很容易发生漂移，导致学习不稳定。在 [1] 中，使用目标网络为更新网络提供稳定的目标，以便在偶尔更新之前进行学习。然而，双深度 Q 学习 [16] 通过拥有两个 Q 网络并以交替方式更新参数来解决这个问题。我们从不同方面回顾一些最先进的深度强化学习算法：

#### II-D1 离策略方法

除了上述提到的深度 Q 学习 [1]，DDPG [17] 使用深度神经网络功能逼近器扩展了确定性策略梯度（DPG） [18]，它是一种演员-评论员算法，在连续动作空间中表现良好。

#### II-D2 在策略方法

A3C [19] 在深度学习中的异步方法[19]中脱颖而出，可以在单个多核 CPU 上并行运行。信任区域策略优化[2]和近端策略优化[20] 采纳了自然策略梯度，它们使用对预期回报的局部近似。局部近似可以作为预期回报的下界，可以在 KL 散度约束下安全地优化两个后续策略之间的差异，而在实际操作中，约束被放宽为正则化。

#### II-D3 基于目标的强化学习

在机器人操控任务中，目标在某些情况下可以通过状态来表示[14]。通用价值函数逼近器（UVFA）[21] 将目标纳入深度神经网络，使神经网络功能逼近器也能对任务中的目标变化进行泛化，类似于推荐系统[22]。这一方向的工作包括[23, 14]，例如。

#### II-D4 回放记忆操控方法

回放记忆是深度强化学习中的关键组件，它解决了单次实验中的相关转移问题。除了深度 Q 网络中的均匀采样[1]，优先经验回放[24]通过对那些具有更大 TD 错误的转移给予优先级来提升性能，而事后经验回放（HER）[23]则通过改变目标来操控回放记忆，从而改变奖励以促进探索。最大熵正则化多目标强化学习[14]在采样时优先考虑那些很少发生的轨迹，已被证明优于 HER [14]。

#### II-D5 替代策略优化

类似于贝叶斯优化中使用的替代模型[25]，在强化学习中也使用了下界替代模型。信任区域策略优化（TRPO）[2] 基于[26]中的恒等式，见于公式 (30)，其中 $\eta_{\pi^{new}}(s)$ 表示在策略 $\pi^{new}$ 下的状态访问频率，优势 $A^{\pi^{old}}(a_{t},s_{t})=Q^{\pi^{old}}(a_{t},s_{t})-V^{\pi^{old}}(s_{t})$。

|  | $\displaystyle J(\pi^{new})$ | $\displaystyle=J(\pi^{old})+\sum_{s}\eta_{\pi^{new}}(s)\sum_{a}\pi^{new}(a&#124;s)A^{\pi^{old}}(a,s)$ |  | (30) |
| --- | --- | --- | --- | --- |

基于策略优势 [26] $A_{\pi^{old},\eta_{old}}(\pi^{new})=\sum_{s}\eta_{\pi^{old}}(s)\sum_{a}\pi^{new}(a|s)A^{\pi^{old}}(a,s)$，可以在方程 (30) 中定义一个局部近似 $L_{\pi^{old}}(\pi^{new})$，基于此，一个替代函数 $M(\pi^{new},\pi^{old})$ 在方程 (32) 中被定义，它在 $\pi^{old}$ 处次优化 $J(\pi^{new})$，其中 $D_{KL}^{max}(\pi^{old},\pi^{new})=\underset{s}{\max}D_{KL}(\pi^{old}(a|s),\pi^{new}(a|s))$ 是最大 KL 散度，因此 MM [2] 算法可以用于改进策略，从而导致信任区域方法 [2]。

|  |  | $\displaystyle L_{\pi^{old}}(\pi^{new})$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle J(\pi^{old})+\sum_{s}\eta_{\pi^{old}}(s)\sum_{a}\pi^{new}(a&#124;s)A^{\pi^{old}}(a_{t},s_{t})$ |  | (31) |
|  |  | $\displaystyle M(\pi^{new},\pi^{old})$ |  |
|  | $\displaystyle=$ | $\displaystyle L_{\pi^{old}}(\pi^{new})-\frac{4\underset{a,s}{max}&#124;A^{\pi^{old}}(s,a)&#124;\gamma}{1-\gamma^{2}}D_{KL}^{max}(\pi^{old},\pi^{new})$ |  | (32) |

表 I：深度强化学习方法比较：“S”表示状态，“A”表示动作，其中“c”表示连续，“d”表示离散。“standalone”表示算法是否独立工作或需要与其他学习算法结合。“var”表示变分推断所近似的概率，“p”表示方法是否在策略上或脱策略。“na”表示不适用

| Algorithm | S | A | standalone | var | p |
| --- | --- | --- | --- | --- | --- |
| Deep Q | c | d | y | na | off |
| A3C | c | c/d | y | na | on |
| TRPO/PPO | c | c/d | y | na | on |
| DDPG | c | c | y | na | off |
| Boltzmann | d | d | y | na | on |
| VIME | c | c | n | $p_{\theta}(s_{t+1}&#124;s_{t},a_{t})$ | na |
| VAST | c | d | n | $p(s_{t}&#124;o_{t-k})$ | na |
| SoftQ | c | c/d | y | $p(a_{t}&#124;s_{t})$ | on |

## III 深度强化学习中的概率图模型和变分推断分类

尽管深度强化学习在许多讨论中取得了成功，但该领域仍面临一些关键挑战。其中一个问题是稀疏奖励的探索。在复杂的真实环境中，智能体需要长时间探索才能获得任何奖励反馈。由于奖励不足，传统的强化学习方法表现不佳，这导致了许多近期对探索方法的贡献。另一个挑战是如何在极大状态和动作空间中表示策略。此外，当某些轨迹可能等同于其他轨迹时，具有多模态行为对智能体有时是有益的，我们希望学习所有这些轨迹。

在本节中，我们详细解释了图形模型和变分推断如何用于建模和优化在这些挑战下的强化学习过程，并形成这些方法的分类。

结合在 II-D 节中提到的深度强化学习方法，我们在表格 I 中对它们进行了比较。

### III-A 无向图中的策略和价值函数

我们首先讨论无向图在深度强化学习中的应用，它通过团体建模变量的联合分布[7]。在[27]中，作者使用限制玻尔兹曼机（RBM）[8]，它具有在观察变量条件下，对潜在变量的可处理的分解后验分布的优良特性。为了处理大状态和动作空间的马尔可夫决策过程（MDP），他们用限制玻尔兹曼机的负自由能来建模状态-动作值函数。具体来说，限制玻尔兹曼机的可见状态[27]包括状态 $s$ 和动作 $a$ 的二进制变量，如图 6 所示，其中隐藏节点由 $L$ 个二进制变量组成，而状态变量 $s_{i}$ 为深色以表示它可以被观察到，动作 $a_{j}$ 为浅色以表示它需要被采样。与辅助隐藏变量一起，无向图定义了状态和动作对的联合概率分布，这定义了一个随机策略网络，该网络可以在策略学习中采样动作。由于计算网络中自由能 $F(s,a)$ 对系数 $w_{k,j}$ 的导数非常简单，可以使用时间差分学习来更新网络中的系数。得益于玻尔兹曼机的特性，给定状态下的动作条件分布 $p(a|s)$，它可以作为策略使用，仍然是玻尔兹曼分布的，如方程 (33) 中所示，由自由能 $F(a,s)$ 控制，其中 $Z(s)$ 是分区函数[7]，负自由能用于逼近状态动作值函数 $Q(s,a)$。通过调整温度 $T$，还可以在不同的探索强度之间进行变化。

\includegraphics

[scale=0.6]tikz_pgm_boltzmanmachine.pdf

图 6：限制玻尔兹曼机的值与策略

|  | $\displaystyle p(a | s)={1/Z(s)}e^{-F(s,a)/T}={1/Z(s)}e^{Q(s,a)/T}$ |  | (33) |
| --- | --- | --- | --- | --- |

几步 MCMC 采样 [7] 可以用来采样动作，作为策略的近似，这可以输入到如 SARSA [12] 这样的时间差分学习方法中，以更新状态值函数 $Q(s,a)$ 的估计。这种策略学习过程在大状态动作空间中已被实证证明是有效的[27]。

### III-B 对“最优”策略的变分推断

#### III-B1 政策作为“最优”后验

Boltzmann 机器定义的专家模型产品在 [27] 对于大状态和动作空间效果良好，但仅限于离散的特别是二进制状态和动作变量。对于连续状态和动作空间，在 [28] 中，作者提出了基于深度能量的模型与有向无环图（DAG） [7]，我们在图 7 中以不同形式重新组织，并添加了注释。与图 3 Markov Decision Process ‣ II-A Basics about Reinforcement Learning with graphical model ‣ II Reinforcement Learning and Deep Reinforcement Learning ‣ Tutorial and Survey on Probabilistic Graphical Model and Variational Inference in Deep Reinforcement Learning") 的区别在于，在图 7 中，奖励在有向图模型中没有明确表示。相反，使用辅助的二进制可观察量 $O$ 来定义当前步骤的相应动作是否是最优的。动作最优的条件概率为 $p(O_{t}=1|s_{t},a_{t})=\exp(r(s_{t},a_{t}))$，这将条件最优性与奖励的数量联系起来，通过鼓励代理采取高度奖励的动作来以指数方式进行。这些奖励必须是负的，以确保概率的有效性，但这不会影响一般性，因为奖励范围可以转换 [13]。

图中的图形模型 7 总体上定义了轨迹似然或方程中的证据 (34)：

|  | $\displaystyle p(\tau)$ | $\displaystyle=\left[p(s_{1})\prod_{t}p(s_{t+1}&#124;s_{t},a_{t})\right]\exp\left(\sum_{t}r(s_{t},a_{t})\right)$ |  | (34) |
| --- | --- | --- | --- | --- |

.

通过这种方式，作者强迫将一种功能表达形式应用于图的条件独立结构，通过分配一个似然函数。这样，计算动作分布的最优策略就变成了一个计算后验 $p(a_{t}|s_{t},O_{t:T}=1)$ 的推断问题，该后验表明，在从当前时间步到剧集结束的最优条件下，当前状态为 $s_{t}$，动作 $a_{t}$ 的分布，这个后验对应于最优策略。从图 7 中观察到的 d-分离，$O_{1:{t-1}}$ 在给定 $s_{t}$ 的情况下与 $a_{t}$ 条件独立，即 $(O_{1:{t-1}}\mathrel{\text{\scalebox{1.07}{$\perp\mkern-10.0mu\perp$}}}A^{act}_{t})\mid{S_{t}}$，因此 $p(a_{t}|s_{t},O_{1:t-1},O_{t:T})=p(a_{t}|s_{t},O_{t:T})$

\includegraphics

[scale=0.7]tikz_pgm_soft_q.pdf

图 7：动作的最优策略作为后验概率：$p(a_{t}|s_{t},O_{t:T}=1)$

#### III-B2 对后验的精确推断中的消息传递

在本节中，我们详细推导了关于策略后验的精确推断，这在 [13] 中没有给出。类似于隐马尔可夫模型中的前向-后向消息传递算法 [7]，后验 $p(a_{t}|s_{t},O_{t:T}=1)$ 也可以通过传递消息来计算。我们提供了关于方程 (35) 中后验 $p(a_{t}|s_{t},O_{t:T}=1)$ 的分解的详细推导，这在 [13] 中不可用。

|  |  | $\displaystyle p(a_{t}\mid s_{t},O_{t:T}=1)$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle\frac{p(a_{t},s_{t},O_{t:T}=1)}{p(s_{t},O_{t:T}=1)}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(O_{t:T}=1\mid a_{t},s_{t})p(a_{t},s_{t})}{p(s_{t},O_{t:T}=1)}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(O_{t:T}=1\mid a_{t},s_{t})p(a_{t}\mid s_{t})p(s_{t})}{\int_{a_{t}{{}^{\prime}}}p(s_{t},a_{t}^{{}^{\prime}},O_{t:T}=1)d\{a_{t}^{{}^{\prime}}\}}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(O_{t:T}=1\mid a_{t},s_{t})p(a_{t}\mid s_{t})p(s_{t})}{\int_{a_{t}^{{}^{\prime}}}p(O_{t:T}=1\mid a_{t}{{}^{\prime}},s_{t})p(a_{t}{{}^{\prime}}\mid s_{t})p(s_{t})d\{a_{t}^{{}^{\prime}}\}}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(O_{t:T}=1&#124;a_{t},s_{t})p(a_{t}&#124;s_{t})}{\int_{a_{t}^{{}^{\prime}}}p(O_{t:T}=1&#124;a_{t}{{}^{\prime}},s_{t})p(a_{t}{{}^{\prime}}&#124;s_{t})d\{a_{t}^{{}^{\prime}}\}}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{\beta(a_{t},s_{t})}{\int_{a_{t}^{{}^{\prime}}}\beta(a_{t}^{{}^{\prime}},s_{t})d\{a_{t}^{{}^{\prime}}\}}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{\beta(a_{t},s_{t})}{\beta(s_{t})}$ |  | (35) |

在方程 (35) 中，我们定义了消息 $\beta(a_{t},s_{t})=p(O_{t:T}=1|a_{t},s_{t})p(a_{t}|s_{t})$ 和消息 $\beta(s_{t})=\int_{a_{t}^{{}^{\prime}}}\beta(a_{t}^{{}^{\prime}},s_{t})d\{a_{t}^{{}^{\prime}}\}$。如果我们将 $p(a_{t}|s_{t})$ 视为一个具有均匀分布的先验 [13]，那么唯一与策略相关的项就是 $p(O_{t:T}=1|a_{t},s_{t})$。

与 HMM 相比，这里只有向后信息是相关的。此外，这里的向后信息 $\beta(a_{t},s_{t})$ 不是 HMM 中的概率分布，而仅仅是一个概率。在图 7 中，向后信息 $\beta(a_{t},s_{t})$ 可以递归地分解。由于在 [13] 中作者仅给出了结论而没有推导，我们在方程 (36) 中提供了这一递归的详细推导。

|  |  | $\displaystyle\beta(s_{t},a_{t})$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle p(O_{t}=1,O_{t+1:T}=1&#124;s_{t},a_{t})$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{\int p(O_{t}=1,O_{t+1:T}=1,s_{t},a_{t},s_{t+1},a_{t+1})d\{s_{t+1},a_{t+1}\}}{p(s_{t},a_{t})}$ |  |
|  | $\displaystyle=$ | $\displaystyle\int p(O_{t+1:T}=1,s_{t+1},a_{t+1},O_{t}=1&#124;s_{t},a_{t})d\{s_{t+1},a_{t+1}\}$ |  |
|  | $\displaystyle=$ | $\displaystyle\int p(O_{t+1:T}=1,s_{t+1},a_{t+1}&#124;s_{t},a_{t})p(O_{t}=1&#124;s_{t},a_{t})$ |  |
|  |  | $\displaystyle d\{s_{t+1},a_{t+1}\}$ |  | ($(O_{t+1:T},S_{t+1},A_{t+1}\mathrel{\text{\scalebox{1.07}{$\perp\mkern-10.0mu\perp$}}}O_{t})\mid S_{t},A_{t}$) |
|  | $\displaystyle=$ | $\displaystyle\int\frac{p(O_{t+1:T}=1,s_{t+1},a_{t+1})}{p(s_{t+1},a_{t+1})}\frac{p(s_{t+1},s_{t},a_{t})}{p(s_{t},a_{t})}$ |  |
|  |  | $\displaystyle p(O_{t}=1&#124;s_{t},a_{t})d\{s_{t+1},a_{t+1}\}$ |  |
|  | $\displaystyle=$ | $\displaystyle\int p(O_{t+1:T}=1&#124;s_{t+1},a_{t+1})p(s_{t+1}&#124;s_{t},a_{t})p(O_{t}=1&#124;s_{t},a_{t})$ |  |
|  |  | $\displaystyle d\{s_{t+1},a_{t+1}\}$ |  |
|  | $\displaystyle=$ | $\displaystyle\int\beta(s_{t+1})p(s_{t+1}&#124;s_{t},a_{t})p(O_{t}=1&#124;s_{t},a_{t})ds_{t+1}$ |  | (36) |

方程式 (36) 中的递归从一个情节的最后时间点 $T$ 开始。

#### III-B3 消息传递与贝尔曼方程之间的联系

如果我们在方程式 (37) 中定义 Q 函数，并在方程式 (38) 中定义 V 函数

|  | $Q(s_{t},a_{t})=\log(\beta(a_{t},s_{t}))$ |  | (37) |
| --- | --- | --- | --- |
|  | $\displaystyle V(s_{t})$ | $\displaystyle=\log\beta(s_{t})=\log\int\beta(s_{t},a_{t})da_{t}$ |  |
|  |  | $\displaystyle=\log\int \exp(Q(s_{t},a_{t}))da_{t}\approx\underset{a_{t}}{max}Q(s_{t},a_{t})$ |  | (38) |

那么相应的政策可以写成方程式 (39)。

|  | $\pi(a_{t}&#124;s_{t})=p(a_{t}&#124;s_{t},O_{t:T}=1)=\exp(Q(s_{t},a_{t})-V(s_{t}))$ |  | (39) |
| --- | --- | --- | --- |

对方程(36)取对数，我们得到方程(40)

|  | $\displaystyle\log(\beta(s_{t},a_{t}))$ |  |
| --- | --- | --- |
|  | $\displaystyle=\log\int\beta(s_{t+1})p(s_{t+1}&#124;s_{t},a_{t})p(O_{t}=1&#124;s_{t},a_{t})ds_{t+1}$ |  |
|  | $\displaystyle=\log\int\exp[r(s_{t},a_{t})+V(s_{t+1})]p(s_{t+1}&#124;s_{t},a_{t})ds_{t+1}$ |  |
|  | $\displaystyle=r(s_{t},a_{t})+\log\int\exp(V(s_{t+1}))p(s_{t+1}&#124;s_{t},a_{t})ds_{t+1}$ |  | (40) |

这简化为方程(41)中提到的风险寻求备份 [13]：

|  | $Q(s_{t},a_{t})=r(s_{t},a_{t})+\log E_{s_{t+1}\sim p(s_{t+1}&#124;s_{t},a_{t})}[\exp(V(s_{t+1}))]$ |  | (41) |
| --- | --- | --- | --- |

这里的数学见解是，如果我们定义在图 7 中传递的消息，那么消息传递对应于一种特殊的贝尔曼方程备份，这会导致一种不希望出现的风险寻求行为 [13]：与方程 (10) 相比，这里的 Q 函数采用了软最大化而不是对下一个状态的期望值。

#### III-B4 变分近似至 ”最佳” 策略

由于精确推断会导致意外行为，因此可以使用近似推断。策略的优化可以被视为一个变分推断问题，我们使用动作后验分布$q(a_{t}|s_{t})$的变分策略，该分布可以通过神经网络表示，以构建如方程（42）所示的提议变分似然函数：

|  | $\displaystyle q(\tau)$ | $\displaystyle=p(s_{1})\prod_{t}[p(s_{t+1}&#124;s_{t},a_{t})q(a_{t}&#124;s_{t})]$ |  | (42) |
| --- | --- | --- | --- | --- |

在这里，初始状态分布$p(s_{1})$和状态转移的环境动态保持不变。以建议轨迹作为枢轴，我们可以推导出最优轨迹的证据下界（ELBO），如方程（43）所示，这对应于奖励加熵回报的有趣目标函数，如方程（45）所示。

|  |  | $\displaystyle\log(p(O_{1:T}))$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle\log\int p(O_{1:T}=1,s_{1:T},a_{1:T})\frac{q(s_{1:T},a_{1:T})}{q(s_{1:T},a_{1:T})}ds_{1:T}da_{1:T}$ |  |
|  | $\displaystyle=$ | $\displaystyle\log E_{q(s_{1:T},a_{1:T})}\frac{p(O_{1:T}=1,s_{1:T},a_{1:T})}{q(s_{1:T},a_{1:T})}$ |  |
|  | $\displaystyle\geq$ | $\displaystyle E_{q(s_{1:T},a_{1:T})}[\log p(O_{1:T}=1,s_{1:T},a_{1:T})-\log q(s_{1:T},a_{1:T})]$ |  | (43) |
|  | $\displaystyle=$ | $\displaystyle-D_{KL}(q(\tau)&#124;p(\tau))$ |  | (44) |
|  | $\displaystyle=$ | $\displaystyle E_{q(s_{1:T},a_{1:T})}[\sum_{t=1:T}[r(s_{t},a_{t})-\log q(a_{t}&#124;s_{t})]]$ |  |
|  | $\displaystyle=$ | $\displaystyle\sum_{t=1:T}E_{s_{t},a_{t}}[r(s_{t},a_{t})+H(\pi(a_{t}&#124;s_{t}))]$ |  | (45) |

#### III-B5 示例

在[28]中，状态动作值函数在方程（46）中定义。

|  | $Q^{\pi}_{soft}(s,a)=r_{0}+E_{r\sim\pi,s_{0}=s,a_{0}=a}[\sum_{t=1}^{\infty}\gamma^{t}(r_{t}+\alpha H(\pi(. \mid s_{t})))]$ |  | (46) |
| --- | --- | --- | --- |

和一个类似于 Q 学习的贝尔曼更新的软版本 [12] 被执行，这导致相对于方程 (47) 中相应的目标函数的策略改进。

|  |  | $\displaystyle J(\pi)$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle\sum_{t}E_{(s_{t},a_{t})\sim\rho_{\pi}}\sum_{l=t}^{\infty}\gamma^{l-t}E_{(s_{l},a_{l})}[r(s_{l},a_{l})+$ |  |
|  |  | $\displaystyle\alpha H(\pi(. \mid s_{l})) \mid s_{t},a_{t}]]$ |  |
|  | $\displaystyle=$ | $\displaystyle\sum_{t}E_{(s_{t},a_{t})\sim\rho_{\pi}}[Q_{soft}^{\pi}(s_{t},a_{t})+\alpha H(\pi(. \mid s_{t}))]$ |  | (47) |

设定策略为方程 (39) 可导致策略改进。我们提供了方程 (48) 中关键公式的详细证明，该公式在 [28] 的方程 (19) 中没有证明。在方程 (48) 中，我们使用 $\pi(\cdot|s)$ 来隐式表示 $\pi(a|s)$，以避免符号别名。

|  |  | $\displaystyle H(\pi(\cdot \mid s))+E_{a\sim\pi}[Q_{soft}^{\pi}(s,a)]$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle-\int_{a}\pi(a\mid s)[\log\pi(a\mid s)-Q_{soft}^{\pi}(s,a)]da$ |  |
|  | $\displaystyle=$ | $\displaystyle-\int_{a}\pi(a\mid s)[\log\pi(a\mid s)-\log[\exp(Q_{soft}^{\pi}(s,a))]]da$ |  |
|  | $\displaystyle=$ | $\displaystyle-\int_{a}\pi(a\mid s)[\log\pi(a\mid s)-\log[\frac{\exp(Q_{soft}^{\pi}(s,a))}{\int\exp(Q_{soft}^{\pi}(s,a^{{}^{\prime}}))da^{{}^{\prime}}}$ |  |
|  |  | $\displaystyle\int\exp(Q_{soft}^{\pi}(s,a^{{}^{\prime}}))da^{{}^{\prime}}]]da$ |  |
|  | $\displaystyle=$ | $\displaystyle-\int_{a}\pi(a\mid s)[\log\pi(a\mid s)-\log[\tilde{\pi}(a\mid s)]-$ |  |
|  |  | $\displaystyle \log\int \exp(Q_{soft}^{\pi}(s,a^{{}^{\prime}}))]da^{{}^{\prime}}$ |  |
|  | $\displaystyle=$ | $\displaystyle-D_{KL}(\pi(\cdot | s) | | \tilde{\pi}(\cdot | s))+\log\int\exp(Q_{soft}^{\pi}(s,a^{{}^{\prime}}))da^{{}^{\prime}}$ |  | (48) |

对于其余的证明，我们邀请读者查阅 [28] 的附录。这类最大熵家族的算法还包括软演员评论家 [29]。

### III-C 环境中的变分推断

在强化学习中使用变分推断的另一个方向是学习环境模型，既可以是动态模型，也可以是潜在状态空间后验。

#### III-C1 转移模型的变分推断

在变分信息最大化探索（VIME）[4]中，代理与环境的动态模型 $p_{\theta}(s_{t+1}|s_{t},a_{t})$ 是通过贝叶斯神经网络 [10] 来建模的。$\theta$ 的随机变量用 $\Theta$ 表示，并通过建模神经网络权重 $\theta$ 的不确定性以贝叶斯方式对待。我们用图 8 中的图示表示此模型，该图在 [4] 中未给出。关于环境的信念不确定性被建模为基于轨迹观察 $\xi_{t}=\{s_{1:t},a_{1:t-1}\}$ 的神经网络权重后验分布的熵 $H(\Theta|\xi_{t})$。该方法通过缓解观察到新状态 $s_{t+1}$ 后代理对环境的信念的平均信息增益来鼓励采取探索性行动，其为 $E_{p(s_{t+1}|\xi_{t},a_{t})}D_{KL}(p(\theta|\xi_{t+1})||p(\theta|\xi_{t}))$，这等同于熵减去条件熵 $H(\Theta|\xi_{t},a_{t})-H(\Theta|\xi_{t},a_{t},s_{t+1})=H(\Theta|\xi_{t},a_{t})-H(\Theta|\xi_{t+1})$。

\includegraphics

[scale=0.6]tikz_pgm_mdp_vime.pdf

图 8：VIME 的概率图模型

在公式（49$。这样的推导在[4]中没有给出。

|  | $\displaystyle I(X;Y\mid Z)$ | $\displaystyle=\int_{x,y,z}p(z)p(x,y\mid z)\log\frac{p(x,y\mid z)}{p(x\mid z)p(y\mid z)}dxdydz$ |  |
| --- | --- | --- | --- |
|  |  | $\displaystyle=-\int_{x,y,z}p(z)p(x,y\mid z)\log p(x\mid z)dxdzdy+$ |  |
|  |  | $\displaystyle+\int_{x,y,z}p(x,y,z)\log p(x\mid y,z)dxdzdy$ |  |
|  |  | $\displaystyle=H(X\mid Z)-H(X\mid Y,Z)$ |  | (49) |
|  |  | $\displaystyle H(\Theta\mid\xi_{t},a_{t})-H(\Theta\mid\xi_{t},a_{t},s_{t+1})=I(\Theta,S_{t+1}\mid\xi_{t},a_{t})$ |  |
|  | $\displaystyle=$ | $\displaystyle E_{\xi_{t},a_{t}}\int_{\Theta,\mathcal{S}}p(s_{t+1},\theta\mid\xi_{t},a_{t})\log[\frac{p(s_{t+1},\theta\mid\xi_{t},a_{t})}{p(\theta\mid\xi_{t})p(s_{t+1}\mid\xi_{t},a_{t})}]d\theta$ |  |
|  |  | $\displaystyle ds_{t+1}$ |  |
|  | $\displaystyle=$ | $\displaystyle E_{\xi_{t},a_{t}}\int_{\Theta,\mathcal{S}}p(s_{t+1}\mid\xi_{t},a_{t})p(\theta\mid\xi_{t+1})\log[\frac{p(\theta\mid\xi_{t+1})}{p(\theta\mid\xi_{t})}]d\theta ds_{t+1}$ |  |
|  | $\displaystyle=$ | $\displaystyle E_{\xi_{t},a_{t}}E_{p(s_{t+1}\mid\xi_{t},a_{t})}D_{KL}(p(\theta\mid\xi_{t+1})\|\ p(\theta\mid\xi_{t}))$ |  | (50) |

基于方程（50），可以从环境奖励函数中增强内在奖励，因此该方法可以与任何现有的强化学习算法（例如 TRPO [2]）结合使用。在对动作 $a_{t}$ 和状态 $s_{t+1}$ 对于轨迹历史 $\xi_{t}$ 的附加观察后，环境参数 $\theta$ 的后验分布 $p(\theta|\xi_{t})$ 可以以贝叶斯方式更新为 $p(\theta|\xi_{t+1})$，如方程（51）中推导的，这一方法最早在 [30] 中提出。

|  | $\displaystyle p(\theta&#124;\xi_{t+1})=$ | $\displaystyle\frac{p(\theta,\xi_{t},a_{t},s_{t+1})}{p(\xi_{t},a_{t},s_{t+1})}$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle=$ | $\displaystyle\frac{p(s_{t+1}&#124;\theta,\xi_{t},a_{t})p(\theta,\xi_{t},a_{t})}{p(\xi_{t},a_{t},s_{t+1})}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(s_{t+1}&#124;\theta,\xi_{t},a_{t})p(\theta,\xi_{t},a_{t})}{p(a_{t},\xi_{t})p(s_{t+1}&#124;a_{t},\xi_{t})}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(s_{t+1}&#124;\theta,\xi_{t},a_{t})p(\theta&#124;\xi_{t},a_{t})}{p(s_{t+1}&#124;a_{t},\xi_{t})}$ |  |
|  | $\displaystyle=$ | $\displaystyle\frac{p(s_{t+1}&#124;\theta,\xi_{t},a_{t})p(\theta&#124;\xi_{t})}{p(s_{t+1}&#124;a_{t},\xi_{t})}$ |  | (51) |

在方程（51）中，分母可以写成方程（52），从而可以利用神经网络权重 $\theta$ 模拟的环境动态 $p(s_{t+1}|\theta,a_{t},\xi_{t})$。

|  | $\displaystyle p(s_{t+1}&#124;a_{t},\xi_{t})$ |  |
| --- | --- | --- |
|  | $\displaystyle=\int_{\Theta}p(s_{t+1},\theta&#124;a_{t},\xi_{t})d\theta$ |  |
|  | $\displaystyle=\int_{\Theta}\frac{p(s_{t+1},\theta,a_{t},\xi_{t})}{p(a_{t},\xi_{t})}d\theta$ |  |
|  | $\displaystyle=\int_{\Theta}\frac{p(s_{t+1}&#124;\theta,a_{t},\xi_{t})p(\theta,a_{t},\xi_{t})}{p(a_{t},\xi_{t})}d\theta$ |  |
|  | $\displaystyle=\int_{\Theta}p(s_{t+1}&#124;\theta,a_{t},\xi_{t})p(\theta&#124;\xi_{t})d\theta$ |  | (52) |

方程式 (52) 的最后一步利用了 $p(\theta|\xi_{t},a_{t})=p(\theta|\xi_{t})$ 。

由于方程式 (52) 中的积分是不可计算的，因此对神经网络权重后验分布 $p(\theta|\xi_{t})$ 进行变分处理，由变分参数 $\phi$ 表征，如图 8 中虚线所示。在每一步更新的模型参数 $\theta$ 的变分后验，可用于计算方程式 (50) 中的内在奖励。

#### III-C2 隐藏状态后验的变分推断

在变分状态表格（VaST）[5] 中，作者假设高维观察状态由 Observable $O$ 表示，而在潜在状态空间 $S$ 发生转换，该空间是有限离散的。 作者假设观察和潜在空间联合概率具有分解形式，我们在方程式 (53) 中明确陈述。

|  | $\displaystyle p(O,S)=\pi_{\theta_{0}}(s_{0})\prod_{t=0}^{T}p_{\theta^{R}}(o_{t}&#124;s_{t})\prod_{t=1}^{T}p_{\theta^{T}}(s_{t}&#124;s_{t-1},a_{t-1})$ |  | (53) |
| --- | --- | --- | --- |

此外，我们用图中的概率图模型来刻画方程 (53)，9 中显示的该模型在 [5] 中并不存在。与图 7 相比，这里的潜在状态 $S$ 是离散空间中的，而观察值是高维图像，而不是表示最优动作的二进制变量。通过假设方程 (54) 中变分后验的因式分解形式，

|  | $\displaystyle q(S_{0:T}&#124;O_{0:T})=\prod_{t=0}^{T}q_{\phi}(S_{t}&#124;O_{t-k:t})$ |  | (54) |
| --- | --- | --- | --- |

作者假设回合长度为$T$，并将默认帧先验观测设为空帧。观察到的轨迹的证据下界（ELBO）（方程 (53) 可以通过类似于变分自编码器的架构[31]轻松表示，其中编码器$q_{\phi}$，结合重参数化技巧[31]，将观察状态$O$映射到 Con-crete 分布[32]的参数，因此可以在确定性变量上使用反向传播来更新网络的权重，基于 ELBO，它被分解为变分自编码器架构的不同重建损失部分。像 VIME [4]一样，VaSt 可以与其他强化学习算法结合。这里在编码器输出的 Heviside 激活上直接进行优先级清扫[12]，通过计数过渡频率，而不是等待方程 (53) 中缓慢学习的环境过渡模型 $p_{\theta^{T}}(s_{t}|s_{t-1},a_{t-1})$。这样做的一个潜在问题是潜在状态$s$和观察状态$o$之间的混叠。为缓解这个问题，在[5]中，作者一旦发现可观察变量被分配了不同的潜在离散状态，便主动重新标记回放记忆中的过渡历史。

\includegraphics

[scale=0.7]tikz_pgm_vast.pdf

图 9：变化状态制表的图形模型

## IV 结论

作为一项教程调查，我们回顾了结合概率图模型的强化学习，总结了深度强化学习的最新进展，并提供了深度强化学习中概率图模型和变分推断的分类，包含了原始贡献中未包括的详细推导。

## 参考文献

+   [1] V. Mnih, K. Kavukcuoglu, D. Silver, A. A. Rusu, J. Veness, M. G. Bellemare, A. Graves, M. Riedmiller, A. K. Fidjeland, G. Ostrovski *等*，“通过深度强化学习实现人类水平控制，” *自然*，第 518 卷，第 7540 期，第 529 页，2015。

+   [2] J. Schulman, S. Levine, P. Abbeel, M. Jordan 和 P. Moritz，“信任区域策略优化”，发表于 *国际机器学习会议*，2015，第 1889–1897 页。

+   [3] X. Sun, J. Lin 和 B. Bischl，“Reinbo: 机器学习管道搜索与配置，内嵌贝叶斯优化强化学习”，2019。

+   [4] R. Houthooft, X. Chen, Y. Duan, J. Schulman, F. De Turck, 和 P. Abbeel, “VIME：变分信息最大化探索，” 在 *神经信息处理系统进展*，2016 年，第 1109–1117 页。

+   [5] D. Corneil, W. Gerstner, 和 J. Brea, “基于模型的深度强化学习的高效变分状态表征，” *arXiv 预印本 arXiv:1802.04325*，2018 年。

+   [6] D. M. Blei, A. Kucukelbir, 和 J. D. McAuliffe, “变分推断：统计学家的回顾，” *美国统计协会期刊*，第 112 卷，第 518 期，第 859–877 页，2017 年。

+   [7] C. M. Bishop, *模式识别与机器学习*。Springer，2006 年。

+   [8] A. Fischer 和 C. Igel, “受限玻尔兹曼机的训练：简介，” *模式识别*，第 47 卷，第 25–39 页，2014 年 1 月。

+   [9] X. Sun, A. Gossmann, Y. Wang, 和 B. Bischl, “在分布变化下基于变分重采样的深度神经网络评估，” 2019 年。

+   [10] C. Blundell, J. Cornebise, K. Kavukcuoglu, 和 D. Wierstra, “神经网络中的权重不确定性，” *arXiv 预印本 arXiv:1505.05424*，2015 年。

+   [11] D. P. Kingma 和 M. Welling, “自编码变分贝叶斯，” *arXiv 预印本 arXiv:1312.6114*，2013 年。

+   [12] R. S. Sutton, A. G. Barto *等*，*强化学习导论*。MIT Press Cambridge，1998 年，第 2 卷，第 4 期。

+   [13] S. Levine, “将强化学习和控制视为概率推断：教程与回顾，” *arXiv 预印本 arXiv:1805.00909*，2018 年。

+   [14] R. Zhao, X. Sun, 和 V. Tresp, “最大熵正则化的多目标强化学习，” *arXiv 预印本 arXiv:1905.08786*，2019 年。

+   [15] L. P. Kaelbling, M. L. Littman, 和 A. R. Cassandra, “在部分可观察的随机领域中进行规划与行动，” *人工智能*，第 101 卷，第 1-2 期，第 99–134 页，1998 年。

+   [16] H. Van Hasselt, A. Guez, 和 D. Silver, “使用双重 Q 学习的深度强化学习，” 在 *第三十届 AAAI 人工智能会议*，2016 年。

+   [17] T. P. Lillicrap, J. J. Hunt, A. Pritzel, N. Heess, T. Erez, Y. Tassa, D. Silver, 和 D. Wierstra, “使用深度强化学习的连续控制，” *arXiv 预印本 arXiv:1509.02971*，2015 年。

+   [18] D. Silver, G. Lever, N. Heess, T. Degris, D. Wierstra, 和 M. Riedmiller, “确定性策略梯度算法，” 2014 年。

+   [19] V. Mnih, A. P. Badia, M. Mirza, A. Graves, T. Lillicrap, T. Harley, D. Silver, 和 K. Kavukcuoglu, “深度强化学习的异步方法，” 在 *国际机器学习大会*，2016 年，第 1928–1937 页。

+   [20] J. Schulman, F. Wolski, P. Dhariwal, A. Radford, 和 O. Klimov, “近端策略优化算法，” *arXiv 预印本 arXiv:1707.06347*，2017 年。

+   [21] T. Schaul, D. Horgan, K. Gregor, 和 D. Silver, “通用价值函数逼近器，” 在 *国际机器学习大会*，2015 年，第 1312–1320 页。

+   [22] N. Kushwaha, X. Sun, B. Singh, 和 O. Vyas, “从基于 PMF 的方法中获得的教训，用于语义推荐系统，” *智能信息系统杂志*，第 50 卷，第 3 期，第 441–453 页，2018 年。

+   [23] M. Andrychowicz, F. Wolski, A. Ray, J. Schneider, R. Fong, P. Welinder, B. McGrew, J. Tobin, O. P. Abbeel, 和 W. Zaremba, “事后经验重放，” 发表在*神经信息处理系统进展*，2017 年，第 5048–5058 页。

+   [24] T. Schaul, J. Quan, I. Antonoglou, 和 D. Silver, “优先经验重放，” *arXiv 预印本 arXiv:1511.05952*，2015 年。

+   [25] X. Sun, A. Bommert, F. Pfisterer, J. Rahnenführer, M. Lang, 和 B. Bischl, “高维限制性联邦模型选择与基于移位分布的多目标贝叶斯优化，” *arXiv 预印本 arXiv:1902.08999*，2019 年。

+   [26] S. Kakade 和 J. Langford, “近似最优近似强化学习，” 发表在*ICML*，第 2 卷，2002 年，第 267–274 页。

+   [27] B. Sallans 和 G. E. Hinton, “具有分解状态和动作的强化学习，” *机器学习研究杂志*，第 5 卷，第 8 月，第 1063–1088 页，2004 年。

+   [28] T. Haarnoja, H. Tang, P. Abbeel, 和 S. Levine, “使用深度能量基策略的强化学习，” 发表在*第 34 届国际机器学习会议-第 70 卷*。JMLR. org，2017 年，第 1352–1361 页。

+   [29] T. Haarnoja, A. Zhou, P. Abbeel, 和 S. Levine, “软演员-评论家：具有随机演员的离策略最大熵深度强化学习，” *arXiv 预印本 arXiv:1801.01290*，2018 年。

+   [30] Y. Sun, F. Gomez, 和 J. Schmidhuber, “计划受到惊讶：动态环境中的最佳贝叶斯探索，” 发表在*人工智能通用智能国际会议*。Springer，2011 年，第 41–51 页。

+   [31] C. Doersch, “变分自编码器教程，” *arXiv 预印本 arXiv:1606.05908*，2016 年。

+   [32] C. J. Maddison, A. Mnih, 和 Y. W. Teh, “具体分布：离散随机变量的连续松弛，” *arXiv 预印本 arXiv:1611.00712*，2016 年。
