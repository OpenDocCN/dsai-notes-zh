<!--yml

category: 未分类

date: 2024-09-06 19:35:20

-->

# [2401.02349] 关于深度强化学习泛化的调查分析

> 来源：[`ar5iv.labs.arxiv.org/html/2401.02349`](https://ar5iv.labs.arxiv.org/html/2401.02349)

# 关于泛化的调查分析

深度强化学习

Ezgi Korkmaz

伦敦大学学院

###### 摘要

强化学习研究通过利用深度神经网络在高维状态或动作空间中解决问题，取得了显著的成功和关注。虽然深度强化学习策略目前已经在从医疗应用到自动驾驶车辆等多个领域得到应用，但仍有许多未解的问题在等待解决，特别是关于深度强化学习策略的泛化能力。在本文中，我们将概述深度强化学习策略遇到过拟合问题的基本原因，这些问题限制了其鲁棒性和泛化能力。此外，我们将对各种提高泛化能力并克服状态-动作值函数中过拟合的解决方法进行形式化和统一。我们相信我们的研究可以为当前深度强化学习的进展提供紧凑的系统统一分析，并帮助构建具有更好泛化能力的鲁棒深度神经策略。

## 1 介绍

强化学习算法的性能通过将深度神经网络作为函数近似器（Mnih et al., 2015）得到了提升。目前，能够学习到可以在大状态和/或动作空间 MDP 中运行的深度强化学习策略（Silver et al., 2017；Vinyals et al., 2019）。这一进展使得构建出能够在高维状态表示（如 Atari, StarCraft）下进行计算机游戏、解决复杂机器人控制任务、设计算法（Mankowitz et al., 2023；Fawzi et al., 2022）以及玩一些最复杂的棋盘游戏（如国际象棋、围棋）（Schrittwieser et al., 2020）的合理深度强化学习策略成为可能。然而，深度强化学习算法也遇到了一些由于其总体泛化能力有限而引发的问题。一些研究通过引入对策略状态观测的对抗性扰动（Huang et al., 2017；Kos & Song, 2017；Korkmaz, 2022）来展示这些问题，另一些则集中在探索函数近似、状态-动作值函数中的估计偏差（Hasselt et al., 2016）或新架构设计思想（Wang et al., 2016）的基本问题。

即使使用深度神经网络作为函数逼近器，我们也无法完全探索高维状态表示的 MDP，这一点是限制泛化能力的根本问题之一。除此之外，一些问题直接由深度神经网络的使用引发，从而继承了其固有的问题（Goodfellow et al., 2015; Szegedy et al., 2014; Korkmaz, 2022）。

在本文中，我们将关注深度强化学习中的泛化及其当前面临的限制的根本原因。特别地，我们将尝试回答以下问题：

+   •

    探索在深度强化学习中的过拟合中扮演什么角色？

+   •

    在状态-动作值函数中观察到的高估偏差的原因是什么？

+   •

    到目前为止，为克服深度强化学习算法遇到的过拟合问题，已经做了哪些工作？

+   •

    强化学习研究未来的方向有哪些，以获得更高水平的深度神经策略泛化能力？

为回答这些问题，我们将探讨连接强化学习多个子领域的研究，关注泛化相关的问题及其相应提出的解决方案。本文介绍了用于实现和测试泛化的不同方法的分类，并用其系统地总结和整合当前的研究成果。我们进一步描述了价值函数高估的问题以及探索在强化学习中过拟合的作用。此外，我们解释了可能在长期内解决这些问题的新兴研究领域，包括元强化学习和终身学习。我们希望我们的论文能够提供对当前领域进展和局限性的简明概述和统一。

## 2 深度强化学习的基础

深度强化学习的目标是通过与环境在马尔可夫决策过程（MDP）中交互来学习一种策略，以最大化期望的累积折扣奖励。MDP 由一个五元组 $\mathcal{M}=(S,A,P,r,\rho_{0},\gamma)$ 表示，其中 $S$ 代表状态空间，$A$ 代表动作空间，$r:S\times A\to\mathbb{R}$ 是奖励函数，$\mathcal{P}:S\times A\to\Delta(S)$ 是转移概率核，$\rho_{0}$ 代表初始状态分布，$\gamma$ 代表折扣因子。强化学习的目标是学习一个策略 $\pi:S\to\Delta(A)$，该策略将状态映射到动作的概率分布上，以最大化期望的累积奖励 $R=\mathbb{E}\sum_{t=0}^{T-1}\gamma^{t}r(s_{t},a_{t})$，其中 $a_{t}\sim\pi(s_{t}),s_{t+1}\sim\mathcal{P}(s_{t},a_{t})$。在 $Q$-学习中，目标是学习最优的状态-动作价值函数（Watkins, 1989）

|  | $Q^{*}(s,a)=R(s,a)+\sum_{s^{\prime}\in S}P(s^{\prime}\mid s,a)\max_{a^{\prime}\in A}Q^{*}(s^{\prime},a^{\prime}).$ |  | (1) |
| --- | --- | --- | --- |

这是通过迭代的贝尔曼更新实现的，该更新通过

|  | $Q(s_{t},a_{t})+\alpha[\mathcal{R}_{t+1}+\gamma\max_{a}Q(s_{t+1},a)-Q(s_{t},a_{t})].$ |  |
| --- | --- | --- |

因此，最优策略是通过在状态 $s$ 中选择动作 $a^{*}(s)=\operatorname*{arg\,max}_{a}Q(s,a)$ 来确定的。在高维状态空间或动作空间的 MDP 中，最优策略通过由深度神经网络表示的函数逼近的状态-动作价值函数来决定。在一个平行的算法家族中，策略本身由 $\pi_{\theta}$ 直接参数化，学习中使用的梯度估计器是

|  | $g=\mathbb{E}_{t}\big{[}\nabla_{\theta}\log\pi_{\theta}(s_{t},a_{t})(Q(s_{t},a_{t})-\max_{a}Q(s_{t},a))\big{]}$ |  |
| --- | --- | --- |

其中 $Q(s_{t},a_{t})$ 指的是时间步 $t$ 的状态-动作价值函数。

## 3 如何实现泛化？

为了能够对不同的路径进行分类以实现泛化，我们首先提供一个定义，旨在捕捉通用强化学习算法的行为。

###### 定义 3.1.

一个强化学习训练算法$\mathcal{A}$通过与 MDP $\mathcal{M}$交互来学习一个策略$\pi$。我们将$\mathcal{A}$的执行分为离散时间步骤，如下所示。在每个时间$t$，算法选择一个状态$s_{t}$，采取一个动作$a_{t}$，观察到状态$s^{\prime}_{t}$的转移及其对应的奖励$r_{t}=r(s_{t},a_{t},s^{\prime}_{t})$。我们将算法$\mathcal{A}$在 MDP $\mathcal{M}$中的历史定义为序列$H_{t}=(s_{0},a_{0},s^{\prime}_{0},r_{0}),\dots(s_{t},a_{t},s^{\prime}_{t},r_{t})$，即算法迄今为止观察到的所有转移。我们要求在时间$t$选择的状态和动作$(s_{t},a_{t})$仅是$H_{t-1}$的函数，即算法迄今为止观察到的转移。在时间$t=T$时，算法停止并输出一个策略$\pi$。

直观上，强化学习算法对 MDP 执行一系列查询$(s_{t},a_{t})$，并观察结果状态转换和奖励。为了尽可能地通用，定义没有对算法如何选择查询序列做出假设。特别地，如果在状态$s_{t}$下采取动作$a_{t}$导致转移到状态$s^{\prime}_{t}$，并不要求$s_{t+1}=s^{\prime}_{t}$。实际上，唯一的假设是$(s_{t+1},a_{t+1})$仅依赖于$H_{t}$，即迄今为止观察到的转移历史。这使得定义能够涵盖深度强化学习算法，这些算法可能基于先前观察到的状态转换以复杂的方式选择查询状态和动作。基于这种通用强化学习算法的定义，我们将进一步定义为实现泛化而提出的不同技术。

###### 定义 3.2  (*奖励转化泛化*)。

设$\mathcal{A}$是一个训练算法，输入为 MDP 并输出一个策略。给定一个 MDP $\mathcal{M}=(S,A,P,r,\rho_{0},\gamma)$，*奖励转化* 泛化方法$\mathcal{G}_{R}$由一系列函数$F_{t}:(S\times A\times S\times\mathbb{R})^{t}\to\mathbb{R}$给出。该方法试图通过在 MDP $\mathcal{M}$上运行$\mathcal{A}$来实现泛化，但在每个时间$t$修改奖励为$\tilde{r}_{t}(s_{t},a_{t},s^{\prime}_{t})=F_{t-1}(H_{t-1})$，其中$H_{t-1}$是算法$\mathcal{A}$在使用扰动奖励运行时的历史。

总之，奖励转化泛化方法只是运行原始算法，但修改观察到的奖励。类似地，我们定义了另外两种泛化方法，它们在运行原始算法的同时，分别修改状态和转移概率。

###### 定义 3.3  (*状态转化泛化*)。

设$\mathcal{A}$是一个训练算法，输入一个 MDP 并输出一个策略。给定一个 MDP $\mathcal{M}=(S,A,P,r,\rho_{0},\gamma)$，一个*状态变换*泛化方法$\mathcal{G}_{S}$由一系列函数$F_{t}:(S\times A\times S\times\mathbb{R})^{t}\times S\to S$给出。该方法试图通过在 MDP $\mathcal{M}$上运行$\mathcal{A}$来实现泛化，但通过将时间$t$选择的状态修改为$\tilde{s}_{t}=F_{t-1}(H_{t-1},s_{t})$，其中$H_{t-1}$是算法$\mathcal{A}$在使用扰动状态时的历史记录。

###### 定义 3.4  (*转移概率变换泛化*)。

设$\mathcal{A}$是一个训练算法，输入一个 MDP 并输出一个策略。给定一个 MDP $\mathcal{M}=(S,A,P,r,\rho_{0},\gamma)$，一个*转移概率变换*泛化方法$\mathcal{G}_{\mathcal{P}}$由一系列函数$F_{t}:(S\times A\times S\times\mathbb{R})^{t}\times(S\times A\times S)\to\mathbb{R}$给出。该方法试图通过在 MDP $\mathcal{M}$上运行$\mathcal{A}$来实现泛化，但通过将时间$t$的转移概率修改为$\tilde{P}(s_{t},a_{t},s^{\prime}_{t})=F_{t-1}(H_{t-1},s_{t},a_{t},s^{\prime}_{t})$，其中$H_{t-1}$是算法$\mathcal{A}$在使用扰动转移概率时的历史记录。

我们定义的最后一种泛化方法基于直接修改训练算法选择下一时间步状态和动作对的方式。虽然这个定义足够宽泛，可以捕捉到训练算法的非常复杂的变化，但在实践中，修改的选择通常有一个简单的描述。

###### 定义 3.5  (*策略变换泛化*)。

设$\mathcal{A}$是一个训练算法，输入一个 MDP 并输出一个策略。给定一个 MDP $\mathcal{M}=(S,A,P,r,\rho_{0},\gamma)$，一个*策略变换*泛化方法$\mathcal{G}_{\pi}$由一系列函数$F_{t}:(S\times A\times S\times\mathbb{R})^{t}\to S\times A$给出。该方法试图通过在 MDP $\mathcal{M}$上运行$\mathcal{A}$来实现泛化，但通过将$\mathcal{A}$选择下一个状态和动作的策略修改为$(\tilde{s_{t}},\tilde{a_{t}})=F_{t-1}(H_{t-1})$，其中$H_{t-1}$是算法$\mathcal{A}$在使用扰动策略时的历史记录。

到目前为止，所有定义都将方法分类为修改训练算法以实现泛化。然而，许多修改训练算法的方法都有一个对应的方法，可以用来测试训练策略的泛化能力。我们的最终定义捕捉了这种对应关系。

###### 定义 3.6  (*泛化测试*)。

设$\hat{\pi}$为 MDP $\mathcal{M}$的训练策略。设$F_{t}$为对应于之前定义之一的泛化方法的函数序列。$F_{t}$的*泛化测试*方法通过在$\mathcal{M}$中执行策略$\hat{\pi}$来给出，但在每一步中应用修改$F_{t}$，其中历史$H_{t}$由迄今为止由$\hat{\pi}$执行的过渡给出。当同时使用泛化方法和泛化测试方法时，我们将使用下标表示泛化方法，并使用上标表示测试方法。例如，$\mathcal{G}_{S}^{\pi}$对应于使用状态转换方法进行训练，使用策略转换方法进行测试。

## 深度强化学习中的 4 种高估根源

许多强化学习算法计算 MDP 中状态-行动值的估计。因为这些估计通常基于与 MDP 的随机交互，所以计算出准确的估计，并且这些估计能正确地推广到进一步的交互，是强化学习中最基本的任务之一。在这一领域的主要挑战是许多类别的强化学习算法倾向于一致性地高估状态-行动值。最初，$Q$-学习的高估偏差被 Thrun 和 Schwartz (1993) 讨论并理论上证明，作为使用函数逼近器进行状态-行动值估计的副产品。随后已证明，深度强化学习过程中的几个部分可能会导致高估偏差。学习高估的状态-行动值可能是由于使用单个最大操作符的统计偏差（van Hasselt, 2010）、值函数与最优策略之间的耦合（Raileanu & Fergus, 2021；Cobbe 等人, 2021）或由累积的函数逼近误差引起（Boyan & Moore, 1994）。

已提出几种方法来针对价值迭代算法的高估偏差。特别是，为了解决由最大操作符引入的这种高估偏差（van Hasselt, 2010）建议使用双重估计器来进行状态-行动值估计。后来，作者还创建了一个可以解决高维状态空间问题的算法版本（Hasselt 等人, 2016）。一些针对价值迭代算法的研究工作基于在训练期间简单地平均状态-行动值与之前学习的状态-行动值估计（Anschel 等人, 2017）。

尽管高估偏差被证明是一个问题，并且经过长时间讨论（Thrun & Schwartz, 1993; van Hasselt, 2010），最近的研究还进一步表明，演员-评论家算法也面临这个问题（Fujimoto et al., 2018）。

表 1：不同探索策略在泛化中的环境和算法细节。

| 引用 | 提议的方法 | 环境 | 强化学习算法 |
| --- | --- | --- | --- |
| Mnih et al. (2015) | $\epsilon$-贪婪 | ALE | DQN |
| Bellemare et al. (2016) | 基于计数 | ALE | A3C 和 DQN |
| Osband et al. (2016b) | RLSVI | Tetris | 表格 $Q$-学习 |
| Osband et al. (2016a) | 启动 DQN | ALE | DQN |
| Houthooft et al. (2017) | VIME | DeepMind Control Suite | TRPO |
| Fortunato et al. (2018) | NoisyNet | ALE | A3C 和 DQN |
| Lee et al. (2021) | SUNRISE | DCS¹¹1DeepMind Control Suite 和 Atari | Soft Actor-Critic 和 Rainbow DQN |

## 5 探索在过拟合中的作用

探索与利用的根本权衡是代理可以通过牺牲当前的即时奖励来尝试采取行动以接近更多未探索的状态。虽然有大量关于可证明有效的探索策略的研究，但这些研究的结果并不一定直接转移到高维状态或动作 MDPs。最显著的迹象是，即使可以使用深度神经网络作为大状态空间的函数逼近器，代理仍然无法完全探索整个状态空间。代理只能探索状态空间的一部分，这就会在学习的价值函数中产生偏差（Baird, 1995）。

在本节中，我们将探讨深度强化学习中的几种探索策略及其对策略过拟合的影响。其中一个相对简单的版本是通过在训练期间的动作选择中添加噪声，例如 $\epsilon$-贪婪探索。请注意，这是定义 3.5. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning")中 $\mathcal{G}_{\pi}$ 策略变换泛化方法的一个例子，见第三部分。虽然 $\epsilon$-贪婪探索在深度强化学习中被广泛使用（Wang et al., 2016; Hamrick et al., 2020; Kapturowski et al., 2023），但也已证明，这些算法在探索状态空间时可能需要指数级的时间（Kakade, 2003）。还有一些研究关注于随机化强化学习训练算法的不同组件。特别地，（Osband et al., 2016b）提出了随机最小二乘值迭代算法，以便更有效地探索，从而提高线性参数化值函数的泛化。这是通过简单地将高斯噪声作为状态访问频率的函数添加到训练数据集中来实现的。后来，作者们还提出了自助式 DQN 算法（即添加时间相关噪声）以提高非线性函数逼近的泛化（Osband et al., 2016a）。

Houthooft 等人 (2017) 提出了一个探索技术，集中于最大化代理对环境动态的信念的信息增益。实际上，作者使用贝叶斯神经网络有效地探索高维动作空间的 MDP。继这一提高探索效率的工作之后，Fortunato 等人 (2018) 提出了在高维状态 MDP 中将参数噪声添加到深度强化学习策略权重中。虽然有几种方法专注于集成状态-动作价值函数学习（Osband 等人，2016a），Lee 等人 (2021) 提出了从一组策略的目标 Q 值中进行重新加权（即加权贝尔曼备份），并结合最高上置信界行动选择。探索策略的另一条研究方向集中于基于计数的方法，这些方法使用状态访问的直接计数。在这一研究方向中，Bellemare 等人 (2016) 尝试阐明基于计数的方法与内在动机之间的关系，并将基于计数的方法用于高维状态 MDP（即 Arcade 学习环境）。然而，值得注意的是，目前大多数深度强化学习算法使用非常简单的探索技术，例如 $\epsilon$-贪婪策略，该策略基于以概率 $1-\epsilon$ 采取最大化状态-动作价值函数的行动，并以概率 $\epsilon$ 采取随机行动（Mnih 等人，2015；Hasselt 等人，2016；Wang 等人，2016；Hamrick 等人，2020；Kapturowski 等人，2023）。

可以争辩说，通过特定类型的训练方法 $\mathcal{A}$ 相比于方法 $\mathcal{B}$，深度强化学习策略在相同样本数量下获得了更高分数，这本身就是技术 $\mathcal{A}$ 导致更泛化策略的证据。尽管代理在相同环境中进行训练和测试，但训练期间探索的状态并不完全是测试期间访问的状态。通过技术 $\mathcal{A}$ 训练出的策略在一个回合结束时获得更高分数，唯一的证据是代理使用 $\mathcal{A}$ 训练能够在 MDP 中访问更远的状态并取得成功。然而，整篇论文将讨论在强化学习研究的不同子领域中探讨的不同泛化概念。虽然探索与利用是强化学习策略性能中的主要问题之一，但本节的大部分工作集中于在难以探索的游戏（即蒙特祖玛的复仇）中获得更高分，而不是在给定基准下对每个游戏总体目标设定更高分。因此，到目前为止，专注于探索的大多数工作可能无法在给定基准下获得与第六部分中描述的研究一样表现良好的策略。

## 6 正则化

在本节中，我们将重点讨论用于提高深度强化学习策略泛化的不同正则化技术。我们将通过将每个技术分类为数据增强、对抗训练和直接函数正则化来进行讨论。在每个类别下，我们将这些不同的泛化方法与我们在第三部分中定义的设置相联系。

表 2：用于状态观察泛化的数据增强技术的环境和算法细节。本节中的所有研究都集中在第三部分中定义的状态变换方法 $\mathcal{G}_{S}$ 上。

| 引用 | 提议方法 | 环境 | 强化学习算法 |
| --- | --- | --- | --- |
| Yarats 等 (2021) | DrQ | DeepMind Control Suite, ALE | DQN |
| Laskin 等 (2020b) | CuRL | DeepMind Control Suite, ALE | Soft Actor Critic 和 DQN |
| Laskin 等 (2020a) | RAD | DeepMind Control Suite, ProcGen | Soft Actor Critic 和 PPO |
| Wang 等 (2020) | Mixreg | ProcGen | DQN 和 PPO |

### 6.1 数据增强

几项研究专注于通过多样化深度强化学习策略的观察来提高泛化能力。在这方面的研究线集中在简单使用数据增强技术的不同版本（Laskin et al., 2020a; b; Yarats et al., 2021）用于高维状态表示环境。特别是，这些研究涉及在训练期间简单技术，如裁剪、旋转或移动状态观察。尽管这一工作得到了相当大的关注，但一项较新的研究（Agarwal et al., 2021b）表明，当随机种子的数量增加到一百时，相对性能在（Laskin et al., 2020b; Yarats et al., 2021）的数据增强训练中减少到一个可能需要提及的重要水平。

虽然这一研究线中的一些工作简单地专注于使用一组数据增强方法（Laskin et al., 2020a; b; Yarats et al., 2021），其他工作则专注于提出新的训练环境（Cobbe et al., 2020）。关于设计新环境以训练深度强化学习策略的研究基本上旨在提供高变化的观察环境，例如在游戏中以有意义的方式更改背景颜色和物体形状，以提高测试时间泛化能力。在鲁棒性和测试时间表现方面，最近的一项工作也在第 6.3 节中提到，表明不可察觉的数据增强可能对策略性能造成重大损害，而经过认证的鲁棒深度强化学习策略对这些不可察觉的增强更为脆弱（Korkmaz, 2023）。

在这一类别中，有些工作专注于通过简单地混合多个观察（例如，从多个不同观察中创建混合状态）来产生更多观察以增加泛化能力（Wang et al., 2020）。虽然大多数试图通过数据增强技术提高泛化能力的研究主要在 DeepMind Control Suite 或 Arcade Learning Environment (ALE)（Bellemare et al., 2013）中进行，但这些研究中的一小部分（Wang et al., 2020）是在相对较新设计的训练环境如 ProcGen（Cobbe et al., 2020）中进行的。Cobbe et al. (2019)专注于通过提出新的游戏环境 CoinRun 来解耦强化学习的训练和测试集。

表 3：不同直接函数正则化策略的环境和算法详细信息，旨在克服强化学习中的过拟合问题。请注意，大多数基于直接函数正则化的方法都是一种策略扰动方法 $\mathcal{G}_{\pi}$，以克服过拟合，如第三部分中所述。

| 引用 | 提议的方法 | 环境 | 强化学习算法 |
| --- | --- | --- | --- |
| Igl 等 (2019) | SNI 和 IBAC | GridWorld 和 CoinRun | Proximal Policy Optimization |
| Vieillard 等 (2020b) | Munchausen RL | Atari | DQN 和 IQN |
| Lee 等 (2020) | 网络随机化 | 2D CoinRun 和 3D DeepMind Lab | Proximal Policy Optimization |
| Amit 等 (2020) | 折扣正则化 | GridWorld 和 Mujoco²²2Mujoco 的低维设置用于这项研究。 | Twin Delayed DDPG (TD3) |
| Agarwal 等 (2021a) | PSM | DDMC 和 Rectangle Game³³3Rectangle 游戏是一个简单的视频游戏，只有两个动作，“右”和“跳”。游戏有黑色背景和两个矩形，游戏目标是避免白色障碍物并到达屏幕右侧。Agarwal 等 (2021a) 是我们遇到的唯一一个实验这个特定游戏的论文。 | DrQ |
| Liu 等 (2021) | BN 和 dropout 以及 $L_{2}/L_{1}$ | Mujoco | PPO, TRPO, SAC, A2C |

### 6.2 直接函数正则化

尽管我们迄今讨论的一些工作侧重于对数据（即状态观察）进行正则化，如第 6.1 节所述，但有些则侧重于直接对所学函数进行正则化，旨在模拟来自深度神经网络正则化的技术，如批量归一化和 dropout（Igl 等，2019）。尽管一些研究尝试在强化学习中模拟这些已知技术，但有些则专注于直接应用这些技术以克服过拟合。在这方面的研究中，Liu 等 (2021) 提出使用深度神经网络正则化中的已知技术应用于连续控制深度强化学习训练。特别是，这些技术包括批量归一化（BN）（Ioffe & Szegedy，2015）、权重裁剪、dropout、熵和 $L_{2}/L_{1}$ 权重正则化。

Lee 等人 (2020) 提出了利用随机网络来随机化输入观察，以提高深度强化学习策略的泛化能力，并在 Cobbe 等人 (2019) 提出的 2D CoinRun 游戏和 3D DeepMind Lab 中测试了该提议。特别地，作者实际上引入了一个随机卷积层来扰动状态观察。因此，这项研究也是定义 3.3. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning") 中描述的状态变换泛化方法 $\mathcal{G}_{S}$ 的一个明确示例。虽然这又是一个随机状态扰动方法的例子，我们将在第 6.3 节进一步解释最坏情况下的扰动方法，以针对强化学习策略中的泛化。

一些研究利用对比表示学习从相互接近的状态观察中学习深度强化学习策略（Agarwal 等人，2021a）。该研究的作者利用了强化学习的时间特性，并提出了一个策略相似性度量。本文的主要目标是阐明序列结构，并利用表示学习从状态表示中学习可泛化的抽象。该研究的一个缺点是，大部分实验研究是在非基准环境（矩形游戏）中进行的。尽管作者在这个特定游戏中展示了令人惊讶的结果，但并未直接说明所提出的方法是否适用于高维状态表示的 MDP，例如 Arcade Learning Environment。Malik 等人 (2021) 研究了能够泛化到多个环境的强化学习策略的查询复杂性。该研究的作者关注于定义 3.4. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning") 中的过渡概率变换设置 $\mathcal{G}_{\mathcal{P}}$，以及定义 3.2. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning") 中的奖励函数变换设置 $\mathcal{G}_{R}$。

直接函数泛化的另一个研究方向探讨了减少折扣因子与在损失函数中加入$\ell_{2}$-正则化项（即权重衰减）之间的关系（Amit 等人，2020）。这项工作的作者展示了减少折扣因子与在时间差分学习的价值函数中加入$\ell_{2}$-正则化器之间的明确联系。特别是，这项研究表明，在损失函数中加入$\ell_{2}$-正则化项等同于使用较低折扣因子进行训练，作者称之为折扣正则化。然而，这项研究的结果基于表格型强化学习的实验以及 Mujoco 环境的低维设置。

对于定义中设定的奖励变换$\mathcal{G}_{R}$（见定义 3.2），Vieillard 等人（2020b）将缩放后的对数策略添加到当前奖励中。为了克服过拟合，一些工作尝试学习状态之间的显式或隐式相似性，以获得合理的策略（Lan 等人，2021）。特别是，这项工作中的作者试图通过提供强化学习中的度量分类法来统一状态空间表示。几项研究提出了将当前策略和更新前策略之间的 Kullback-Leibler（KL）散度作为正则化项添加到强化学习目标中的不同方法（Schulman 等人，2015）。最近，一些研究认为，利用 Kullback-Leibler 正则化隐式地平均了状态-动作值估计（Vieillard 等人，2020a）。

### 6.3 深度神经策略泛化的对抗视角

规范化状态观察的一种方法是基于将最坏情况下的扰动添加到状态观察中（即对抗扰动）。这项工作始于将 Goodfellow 等人提出的快速梯度符号法（2015）产生的扰动引入深度强化学习观察中（Huang 等人，2017；Kos & Song，2017），并比较在最坏情况下的扰动和高斯噪声存在下，训练的深度强化学习策略的泛化能力。这些基于梯度的对抗方法基于对训练策略的成本函数关于状态观察的梯度。还有几种其他技术被提出用于对状态观察的对抗性改变的优化方向。在这方面的工作中，Korkmaz（2020）提出了一种基于 Nesterov 动量的方法，用于生成深度强化学习策略的对抗扰动。Korkmaz（2022）进一步表明，深度强化学习策略在不同 MDP 中学习到共享的对抗特征。在这项工作中，作者探讨了这一问题的根本原因，并展示了策略高灵敏度方向与状态观察的感知相似性之间的不相关性。此外，研究表明，目前最先进的对抗训练技术也学习到与原始训练的深度强化学习策略类似的高灵敏度方向。从安全角度来看，这种对抗框架属于黑箱对抗攻击范畴，这是首个研究表明深度强化学习策略容易受到黑箱对抗攻击的研究（Korkmaz，2022）。此外，需要注意的是，黑箱对抗扰动是更具通用性的全局扰动，能够影响许多不同的策略。虽然一些研究专注于状态观察的改变，以评估策略对这些变化的鲁棒性，一些研究则专注于这些状态观察变化的可解释性和解释性，以及这些变化如何对标准深度强化学习训练算法和认证鲁棒（即对抗性）训练算法产生不同的影响（Korkmaz，2021e）。有关此论文的初步版本，请参见 Korkmaz（2021a；d）。

表 4：用于深度强化学习中对抗策略正则化和攻击技术的环境及算法细节。请注意，大多数基于对抗策略正则化的方法都是一种状态观察扰动方法 $\mathcal{G}_{S}^{S}$，如定义 3.6. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning") 所述。

| 引用 | 提出的方法 | 环境 | 强化学习算法 |
| --- | --- | --- | --- |
| Huang 等人 (2017) | FGSM | ALE | DQN, TRPO, A3C |
| Kos & Song (2017) | FGSM | ALE | DQN 和 IQN |
| Lin 等人 (2017) | 战略性时机攻击 | ALE | A3C 和 DQN |
| Gleave 等人 (2020) | 对抗策略 | Mujoco | 近端策略优化 |
| Huan 等人 (2020) | SA-DQN | ALE 和 $L_{\textrm{Mujoco}}$⁶⁶6 低维状态 Mujoco 指的是 Mujoco 的设置，其中状态维度不是由像素表示，状态观察的维度范围从 11 到 117。 | DDQN 和 PPO |
| Korkmaz (2022) | 对抗框架 | ALE | DDQN 和 A3C |
| Korkmaz (2023) | 自然攻击 | ALE | DDQN 和 A3C |
| Korkmaz & Brown-Cohen (2023) | 对抗检测 | ALE | DDQN |

请注意，这一工作属于状态观察泛化测试类别 $\mathcal{G}_{S}^{S}$，如定义 3.6. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning") 所述。

尽管一些研究专注于改进优化技术以计算最优扰动，但有一系列研究致力于使深度神经策略对这些扰动具有鲁棒性。Pinto 等人 (2017) 提出了将对手与深度神经策略之间的动态建模为零和游戏，其中对手的目标是最小化深度强化学习策略的预期累计奖励。这项研究清楚地展示了通过转移概率扰动实现通用性$\mathcal{G}_{\mathcal{P}}$，如第 3.4. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning")节中的定义所述。Gleave 等人 (2020) 通过限制对手在 MDP 中采取自然动作而不是用$\ell_{p}$-范数有界的扰动修改观测来处理这个问题。作者将这一动态建模为零和马尔可夫游戏，并通过自我博弈的近端策略优化（PPO）来解决它。一些近期研究提出将对手与深度强化学习策略之间的互动建模为状态对抗 MDP，并声称他们提出的算法状态对抗双深度 Q 网络（SA-DDQN）能够学习理论上认证的鲁棒策略，对抗自然噪声和扰动。特别是，这些认证对抗训练技术旨在在深度$Q$-学习中的时间差损失中添加一个正则化项。

|  | $\mathcal{H}(r_{i}+\gamma\max_{a}\hat{Q}_{\hat{\theta}}(s_{i},a;\theta)-Q_{\theta}(s_{i},a_{i};\theta))+\kappa\mathcal{R}(\theta)$ |  |
| --- | --- | --- |

其中$\mathcal{H}$是 Huber 损失，$\hat{Q}$指的是目标网络，$\kappa$用于调整收敛的正则化水平。不同的认证对抗训练技术可能使用不同的正则化项，而基线技术使用的是

|  | $\displaystyle\mathcal{R}(\theta)=\max\{\max_{\hat{s}\in B(s)}\max_{a\neq\operatorname*{arg\,max}_{a^{\prime}}Q(s,a^{\prime})}Q_{\theta}(\hat{s},a)-Q_{\theta}(\hat{s},\operatorname*{arg\,max}_{a^{\prime}}Q(s,a^{\prime}),-c\}.$ |  |
| --- | --- | --- |

其中 $B(s)$ 是半径为 $\epsilon$ 的 $\ell_{p}$-范数球体。尽管这些经过认证的对抗训练技术引起了社区的一些关注，但最近对理论上经过认证的对抗性训练的深度强化学习策略的鲁棒性提出了更多关注（Korkmaz, 2021e; 2022）。在这些研究中，作者认为对抗训练（即经过认证的鲁棒性）深度强化学习策略从环境中学习到了不准确的状态-动作值函数和非鲁棒特征。特别是在 Korkmaz (2021c) 中，作者使用动作操控来研究最坏情况扰动训练。这项研究也是定义 3.6. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning") 中政策扰动泛化测试方法 $\mathcal{G}_{S}^{\pi}$ 的一个清晰示例。更重要的是，最近已显示对抗性训练的深度强化学习策略在高维状态空间 MDPs 中的泛化能力比普通训练的强化学习策略更差（Korkmaz, 2023）⁷⁷7A short and preliminary version of the paper (Korkmaz, 2023) can also be found here (Korkmaz, 2021b)。虽然这项研究提供了对抗方向与 MDP 固有的自然方向之间的对比，但它进一步展示了经过认证的对抗训练技术阻碍了标准深度强化学习策略的泛化能力。此外，请注意这项研究也是定义 3.6. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning") 中状态观察扰动泛化测试方法 $\mathcal{G}_{S}^{S}$ 的一个清晰示例。

## 7 元强化学习与元梯度

一项相当新的研究方向将其研究精力集中在自动发现强化学习算法上，而无需明确设计这些算法，通过元梯度（Oh et al., 2020; Xu et al., 2020）。这项研究的目标是通过仅与一组环境进行交互，将“学习算法”作为元学习问题进行学习。特别是，

|  | $\eta^{*}=\operatorname*{arg\,max}_{\eta}\mathbb{E}_{\varepsilon\sim\rho(\varepsilon)}\mathbb{E}_{\theta_{0}\sim\rho(\theta_{0})}[\mathbb{E}_{\theta_{N}}[\sum_{t=0}^{\infty}\gamma^{t}r_{t}]]$ |  |
| --- | --- | --- |

这里的最优更新规则由 $\eta$ 参数化，对于环境的分布 $\rho(\varepsilon)$ 和初始策略参数 $\rho(\theta_{0})$，其中 $\mathbb{E}_{\theta_{N}}[\sum_{t=0}^{\infty}\gamma^{t}r_{t}]$ 是智能体生命周期结束时的期望回报。

元强化学习的目标是能够构建能够随着时间学习如何学习的智能体，从而使这些策略能够适应变化的环境或 MDP 的任何其他变化条件。最近，为实现这一目标进行了大量研究，特别是 Oh et al. (2020) 提出了发现强化学习更新规则的方案。这一工作也属于定义在第 3.5. ‣ 3 How to Achieve Generalization? ‣ A Survey Analyzing Generalization in Deep Reinforcement Learning")节中的政策转化泛化 $\mathcal{G}_{\pi}$。随后，Xu et al. (2020) 提出了一个联合元学习框架，以学习策略应该预测什么以及如何利用这些预测来更新策略。最近，Kirsch et al. (2022) 提出了在发现强化学习算法时使用对称信息，并讨论了元泛化。

还有一些工作致力于使强化学习算法发现时间抽象（Veeriah et al., 2021）。特别地，时间抽象指的是策略能够将一系列动作抽象为完成某些子任务的能力。正如该子领域所承诺的，元强化学习被认为是一个研究方向，它可以使我们构建出能够适应不同环境、随时间变化的环境甚至不同任务的深度强化学习策略。

## 8 强化学习中的迁移

强化学习中的迁移是一个在某些强化学习算法应用中（如机器人技术）被广泛讨论的子领域。在当前的机器人研究中，没有安全的方法通过让机器人在现实生活中探索来训练强化学习智能体。因此，克服这一问题的方法是先在模拟环境中训练策略，然后将训练好的策略应用到实际应用环境中。模拟环境和安装环境的不完全相同是强化学习应用研究的主要问题之一。这被称为模拟到现实的差距。

强化学习研究中的另一个子领域专注于获取具有普遍适应性的策略，通过强化学习中的迁移来探讨这一概念。该研究领域的考虑是建立针对特定任务在有限数据下训练的策略，并尝试使这些策略在略微不同的任务上表现良好。关于这方面的初步讨论开始于 (Taylor & Stone, 2007)，旨在以更高效的样本方式将初步在源任务中训练的策略迁移到目标任务。随后，Tirinzoni 等人 (2018) 提出了迁移基于从源任务中学习的最优价值函数的先验分布的价值函数。然而，该研究是在具有低维状态空间的简单环境中进行的。 (Barreto 等人, 2017) 考虑了在第 3.2。 ‣ 3 如何实现泛化？ ‣ 一项分析深度强化学习中泛化的调查") 节中定义的奖励变换设置 $\mathcal{G}_{R}$。特别是，作者考虑了在奖励函数 $r(s,a)$ 的特定任务与奖励函数 $r^{\prime}(s,a)$ 的不同任务之间的策略迁移。该研究的目标是将状态表示与任务解耦。在第 3.3。 ‣ 3 如何实现泛化？ ‣ 一项分析深度强化学习中泛化的调查") 节中定义的状态变换泛化 $\mathcal{G}_{S}$ 设置中，Gamrian & Goldberg (2019) 专注于源任务和目标任务之间的状态差异。特别是，作者使用未对齐的生成对抗网络从源任务状态生成目标任务状态。在第 3.5。 ‣ 3 如何实现泛化？ ‣ 一项分析深度强化学习中泛化的调查") 节中定义的策略变换泛化 $\mathcal{G}_{\pi}$ 设置中，Jain 等人 (2020) 专注于对新引入的动作集进行零样本泛化以提高适应性。

尽管迁移学习是强化学习的一个有前景的研究方向，但该子领域的研究仍然仅仅面向强化学习应用，与第六部分中讨论的研究线相比，可能存在研究成熟度的差异，无法在复杂的已建立基准中测试这些主张或提议。

## 9 终身强化学习

终身学习是一个与迁移学习紧密相关的子领域，最近引起了强化学习社区的关注。终身学习旨在构建能够通过任务间知识转移来顺序解决不同任务的策略。在这方面的研究中，Lecarpentier 等人 (2021) 提出了一个在 Lipschitz 连续任务空间中基于价值的转移算法，并为终身学习目标提供了理论贡献。在定义为第 3.5. ‣ 3 如何实现泛化？ ‣ 深度强化学习中泛化分析的综述")节的动作转换泛化设置$\mathcal{G}_{\pi}$中，Chandak 等人 (2020) 关注于终身学习中动作集的时间变化（例如，源任务和目标任务之间的变化）。在终身强化学习中，一些研究关注不同的探索策略。特别是，Garcia & Thomas (2019) 将终身学习的探索策略问题建模为另一个 MDP，并使用一个独立的强化学习代理来为初始终身学习代理寻找最佳探索方法。基准测试的缺乏限制了终身强化学习研究的进展，因为它限制了提出的算法或方法之间的直接比较。然而，最近有工作提出了一个基于机器人应用的新的训练环境基准，以克服这一问题（Wolczyk 等人，2021)⁸⁸8 该基准的状态维度为 12\. 因此，状态空间是低维的。

## 10 逆向强化学习

逆向强化学习关注于在缺乏奖励函数的情况下学习一个有效的策略。由于在这种设置下真实的奖励函数无法访问，而奖励函数需要通过观察专家完成给定任务来学习，因此逆向强化学习的设置属于定义在第 3.2. ‣ 3 如何实现泛化？ ‣ 深度强化学习中泛化分析的综述")节 3 中的奖励转换泛化设置$\mathcal{G}_{R}$。首次引入逆向强化学习的工作由 Ng & Russell (2000)提出，展示了对于一个观察到的最优策略，可以构造出多个不同的奖励函数。该初步研究的作者通过线性规划实现了这一目标。

|  | $\displaystyle\textrm{maximize}\sum_{s\in S_{\rho}}$ | $\displaystyle\min_{a\in A}\{p(\mathbb{E}_{s^{\prime}\sim\mathcal{P}(s,a_{1}&#124;\cdot)}\mathcal{V}^{\pi}(s^{\prime})-\mathbb{E}_{s^{\prime}\sim\mathcal{P}(s,a&#124;\cdot)}\mathcal{V}^{\pi}(s^{\prime}))\}$ |  | (2) |
| --- | --- | --- | --- | --- |
|  |  | $\displaystyle\textrm{s.t.}\>\>&#124;\alpha_{i}&#124;\leq 1\>,\>i=1,2,\dots,d$ |  |

其中 $p(x)=x$ 如果 $x\geq 0$，否则 $p(x)=2x$，且 $\mathcal{V}^{\pi}=\alpha_{1}\mathcal{V}^{\pi}_{1}+\alpha_{2}\mathcal{V}^{\pi}_{2}+\dots+\alpha_{d}\mathcal{V}^{\pi}_{d}$。在这方面的研究中，最近取得了一些进展，实现了在高维状态观测 MDP 中学习有效的策略（Garg 等，2021）。该研究通过观察专家演示来学习软 $Q$-函数，并进一步论证了从学习到的软状态-动作值函数中恢复奖励是可能的。

## 11 结论

在本文中，我们尝试回答以下问题：（i）哪些显性问题限制了强化学习算法获得能够泛化的高性能策略？（ii）我们如何对迄今为止提出的不同技术进行分类，以实现强化学习中的泛化？（iii）这些由不同强化学习研究子领域提出的不同技术在构建能够泛化的强化学习策略方面有哪些相似性和差异？为了回答这些问题，我们首先解释了探索策略在过拟合中的重要性，并解释了强化学习中过估计偏差的多种原因。在论文的第二部分，我们提出了一个框架，用于统一和分类各种实现强化学习泛化的技术。从解释状态表示或学习的价值函数中的不同正则化技术，从最坏情况到平均情况，我们提供了一个关于强化学习子领域的广泛布局，这些子领域本质上都在朝着相同的目标努力，即可泛化的深度强化学习策略。最后，我们对每个类别的算法的缺点和优点进行了讨论。我们相信我们的研究可以为近期强化学习泛化研究提供一个紧凑的统一形式化。

## 参考文献

+   Agarwal 等（2021a）Rishabh Agarwal, Marlos C. Machado, Pablo Samuel Castro, 和 Marc G. Bellemare。强化学习中的对比行为相似性嵌入。在 *国际学习表征会议（ICLR）*，2021a。

+   Agarwal 等（2021b）Rishabh Agarwal, Max Schwarzer, Pablo Samuel Castro, Aaron C. Courville, 和 Marc G. Bellemare。统计悬崖边缘的深度强化学习。*神经信息处理系统会议（NeurIPS）*，2021b。

+   Amit et al. (2020) Ron Amit, Ron Meir 和 Kamil Ciosek. 强化学习中的折扣因子作为正则化项。发表于*国际机器学习会议（ICML）*，2020 年。

+   Anschel et al. (2017) Oron Anschel, Nir Baram 和 Nahum Shimkin. 平均 DQN：深度强化学习中的方差减少和稳定性。发表于*国际机器学习会议（ICML）*，2017 年。

+   Baird (1995) Leemon Baird. 残差算法：具有函数逼近的强化学习。发表于*国际机器学习会议（ICML）*，1995 年。

+   Barreto et al. (2017) André Barreto, Will Dabney, Rémi Munos, Jonathan J. Hunt, Tom Schaul, David Silver 和 Hado van Hasselt. 强化学习中的后继特征用于迁移。发表于*神经信息处理系统会议（NeurIPS）*，2017 年。

+   Bellemare et al. (2013) Marc G Bellemare, Yavar Naddaf, Joel Veness 和 Michael Bowling. 游戏机学习环境：通用智能体的评估平台。发表于*JAIR*，2013 年。

+   Bellemare et al. (2016) Marc G. Bellemare, Sriram Srinivasan, Georg Ostrovski, Tom Schaul, David Saxton 和 Rémi Munos. 统一基于计数的探索和内在动机。发表于*神经信息处理系统会议（NeurIPS）*，2016 年。

+   Boyan & Moore (1994) Justin A. Boyan 和 Andrew W. Moore. 强化学习中的泛化：安全地逼近价值函数。发表于*神经信息处理系统会议（NeurIPS）*，1994 年。

+   Chandak et al. (2020) Yash Chandak, Georgios Theocharous, Chris Nota 和 Philip S. Thomas. 具有变化动作集的终身学习。发表于*AAAI 人工智能会议（AAAI）*，2020 年。

+   Cobbe et al. (2019) Karl Cobbe, Oleg Klimov, Christopher Hesse, Taehoon Kim 和 John Schulman. 量化强化学习中的泛化。发表于*国际机器学习会议（ICML）*，2019 年。

+   Cobbe et al. (2020) Karl Cobbe, Christopher Hesse, Jacob Hilton 和 John Schulman. 利用过程生成来基准测试强化学习。发表于*国际机器学习会议（ICML）*，2020 年。

+   Cobbe et al. (2021) Karl Cobbe, Jacob Hilton, Oleg Klimov 和 John Schulman. 相位策略梯度。发表于*国际机器学习会议（ICML）*，2021 年。

+   Fawzi et al. (2022) Alhussein Fawzi, Matej Balog, Aja Huang, Thomas Hubert, Bernardino Romera-Paredes, Mohammadamin Barekatain, Alexander Novikov, Francisco J. R. Ruiz, Julian Schrittwieser, Grzegorz Swirszcz, David Silver, Demis Hassabis 和 Pushmeet Kohli. 通过强化学习发现更快的矩阵乘法算法。发表于*自然*，610(7930):47–53，2022 年。

+   Fortunato et al. (2018) Meire Fortunato, Mohammad Gheshlaghi Azar, Bilal Piot, Jacob Menick, Ian Osband, Alex Graves, Vlad Mnih, Rémi Munos, Demis Hassabis, Olivier Pietquin, Charles Blundell 和 Shane Legg. 用于探索的噪声网络。发表于*国际学习表征会议（ICLR）*，2018 年。

+   Fujimoto 等 (2018) Scott Fujimoto, Herke van Hoof 和 David Meger。解决演员-评论家方法中的函数逼近误差。在 *国际机器学习大会 (ICML)*，2018 年。

+   Gamrian & Goldberg (2019) Shani Gamrian 和 Yoav Goldberg。通过图像到图像转换的相关 RL 任务的迁移学习。在 *国际机器学习大会 (ICML)*，2019 年。

+   Garcia & Thomas (2019) Francisco M. Garcia 和 Philip S. Thomas。用于终身强化学习的探索的元 MDP 方法。在 *神经信息处理系统会议 (NeurIPS)*，2019 年。

+   Garg 等 (2021) Divyansh Garg, Shuvam Chakraborty, Chris Cundy, Jiaming Song 和 Stefano Ermon。Iq-learn：用于模仿的逆软 Q 学习。*神经信息处理系统 (NeurIPS) [专题报告]*，2021 年。

+   Gleave 等 (2020) Adam Gleave, Michael Dennis, Cody Wild, Kant Neel, Sergey Levine 和 Stuart Russell。对抗性策略：攻击深度 RL。*国际学习表征大会 (ICLR)*，2020 年。

+   Goodfellow 等 (2015) Ian Goodfellow, Jonathan Shelens 和 Christian Szegedy。解释和利用对抗样本。*国际学习表征大会 (ICLR)*，2015 年。

+   Hamrick 等 (2020) Jessica Hamrick, Victor Bapst, Alvaro SanchezGonzalez, Tobias Pfaff, Theophane Weber, Lars Buesing 和 Peter Battaglia。结合 Q 学习和搜索的摊销价值估计。在 *第八届国际学习表征大会, ICLR*，2020 年。

+   Hasselt 等 (2016) Hado van Hasselt, Arthur Guez 和 David Silver。使用双重 Q 学习的深度强化学习。*AAAI 人工智能会议, AAAI*，2016 年。

+   Houthooft 等 (2017) Rein Houthooft, Xi Chen, Yan Duan, John Schulman, Filip De Turck 和 Pieter Abbeel。VIME：变分信息最大化探索。在 *神经信息处理系统会议 (NeurIPS)*，2017 年。

+   Huan 等 (2020) Zhang Huan, Chen Hongge, Xiao Chaowei, Bo Li, Mingyan Boning, Duane Liu 和 ChoJui Hsiesh。针对状态观测的对抗性扰动的鲁棒深度强化学习。*神经信息处理系统会议 (NeurIPS)*，2020 年。

+   Huang 等 (2017) Sandy Huang, Nicholas Papernot, Yan Goodfellow, Ian an Duan 和 Pieter Abbeel。对神经网络策略的对抗性攻击。*国际学习表征大会 (ICLR)*，2017 年。

+   Igl 等 (2019) Maximilian Igl, Kamil Ciosek, Yingzhen Li, Sebastian Tschiatschek, Cheng Zhang, Sam Devlin 和 Katja Hofmann。具有选择性噪声注入和信息瓶颈的强化学习泛化。*神经信息处理系统会议 (NeurIPS)*，2019 年。

+   Ioffe & Szegedy (2015) Sergey Ioffe 和 Christian Szegedy。批量归一化：通过减少内部协变量偏移加速深度网络训练。在 *国际机器学习大会 (ICML)*，2015 年。

+   Jain et al. (2020) Ayush Jain, Andrew Szot 和 Joseph J. Lim. 强化学习中对新动作的泛化。见于 *国际机器学习会议（ICML）*，2020。

+   Kakade (2003) Sham Kakade. 强化学习的样本复杂度。见于 *博士论文*，2003。

+   Kapturowski et al. (2023) Steven Kapturowski, Victor Campos, Ray Jiang, Nemanja Rakicevic, Hado van Hasselt, Charles Blundell 和 Adrià Puigdomènech Badia. 人类水平的 Atari 游戏速度提升 200 倍。见于 *第十一届国际学习表征会议，ICLR 2023*，2023。

+   Kirsch et al. (2022) Louis Kirsch, Sebastian Flennerhag, Hado van Hasselt, Abram L. Friesen, Junhyuk Oh 和 Yutian Chen. 在黑箱元强化学习中引入对称性。见于 *AAAI 人工智能会议，AAAI*，2022。

+   Korkmaz (2020) Ezgi Korkmaz. 深度强化学习领域中的 Nesterov 动量对抗扰动。见于 *国际机器学习会议（ICML）研讨会*，2020。

+   Korkmaz (2021a) Ezgi Korkmaz. 四维域中的对抗训练神经策略。见于 *国际学习表征会议（ICLR）现实世界中的稳健与可靠机器学习研讨会*，2021a。

+   Korkmaz (2021b) Ezgi Korkmaz. 对抗训练阻碍神经策略的泛化。见于 *国际学习表征会议（ICLR）现实世界中的稳健与可靠机器学习研讨会*，2021b。

+   Korkmaz (2021c) Ezgi Korkmaz. 对抗训练深度神经策略中非最优动作的状态-动作值函数的不准确性。见于 *IEEE/CVF 计算机视觉与模式识别会议（CVPR）研讨会*，2021c。

+   Korkmaz (2021d) Ezgi Korkmaz. 深度强化学习中的非鲁棒特征映射。见于 *国际机器学习会议（ICML）对抗机器学习研讨会*，2021d。

+   Korkmaz (2021e) Ezgi Korkmaz. 探讨深度神经策略的脆弱性。见于 *人工智能不确定性会议（UAI）*，2021e。

+   Korkmaz (2022) Ezgi Korkmaz. 深度强化学习策略在多智能体决策问题中学习共享对抗特征。见于 *AAAI 人工智能会议，AAAI*，2022。

+   Korkmaz (2023) Ezgi Korkmaz. 对抗鲁棒深度强化学习需要重新定义鲁棒性。见于 *AAAI 人工智能会议，AAAI*，2023。

+   Korkmaz & Brown-Cohen (2023) Ezgi Korkmaz 和 Jonah Brown-Cohen. 检测深度强化学习中的对抗方向以做出稳健决策。见于 *国际机器学习会议，ICML 2023*，第 202 卷 *机器学习研究论文集*，第 17534–17543 页。PMLR，2023。

+   Kos & Song (2017) Jernej Kos 和 Dawn Song. 深入探讨对深度策略的对抗攻击。见于 *国际学习表征会议（ICLR）*，2017。

+   Lan 等（2021）Charline Le Lan、Marc G. Bellemare 和 Pablo Samuel Castro。强化学习中的度量与连续性。发表于*AAAI 人工智能会议，AAAI*，2021 年。

+   Laskin 等（2020a）Michael Laskin、Kimin Lee、Adam Stooke、Lerrel Pinto、Pieter Abbeel 和 Aravind Srinivas。增强数据下的强化学习。发表于*神经信息处理系统会议（NeurIPS）*，2020 年。

+   Laskin 等（2020b）Michael Laskin、Aravind Srinivas 和 Pieter Abbeel。CURL：用于强化学习的对比无监督表征。发表于*国际机器学习会议（ICML）*，2020 年。

+   Lecarpentier 等（2021）Erwan Lecarpentier、David Abel、Kavosh Asadi、Yuu Jinnai、Emmanuel Rachelson 和 Michael L. Littman。Lipschitz 终身强化学习。*AAAI 人工智能会议，AAAI*，2021 年。

+   Lee 等（2020）Kimin Lee、Kibok Lee、Jinwoo Shin 和 Honglak Lee。网络随机化：深度强化学习中的一种通用化简单技术。发表于*国际学习表征会议（ICLR）*，2020 年。

+   Lee 等（2021）Kimin Lee、Michael Laskin、Aravind Srinivas 和 Pieter Abbeel。SUNRISE：深度强化学习中的简单统一集成学习框架。发表于*国际机器学习会议（ICML）*，2021 年。

+   Lin 等（2017）Yen-Chen Lin、Hong Zhang-Wei、Yuan-Hong Liao、Meng-Li Shih、Ing-Yu Liu 和 Min Sun。对抗攻击 DRL 代理的战术。*IJCAI*，2017 年。

+   Liu 等（2021）Zhuang Liu、Xuanlin Li 和 Trevor Darrell。政策优化中的正则化问题 - 对连续控制的实证研究。发表于*国际学习表征会议（ICLR）*，2021 年。

+   Malik 等（2021）Dhruv Malik、Yuanzhi Li 和 Pradeep Ravikumar。何时强化学习是可泛化的？发表于*神经信息处理系统会议（NeurIPS）*，2021 年。

+   Mankowitz 等（2023）Daniel J. Mankowitz、Andrea Michi、Anton Zhernov、Marco Gelmi、Marco Selvi、Cosmin Paduraru、Edouard Leurent、Shariq Iqbal、Jean-Baptiste Lespiau、Alex Ahern、Thomas Köppe、Kevin Millikin、Stephen Gaffney、Sophie Elster、Jackson Broshear、Chris Gamble、Kieran Milan、Robert Tung、Minjae Hwang、Taylan Cemgil、Mohammadamin Barekatain、Yujia Li、Amol Mandhane、Thomas Hubert、Julian Schrittwieser、Demis Hassabis、Pushmeet Kohli、Martin A. Riedmiller、Oriol Vinyals 和 David Silver。利用深度强化学习发现的更快排序算法。*自然*，618(7964)：257–263，2023 年。

+   Mnih 等（2015）Volodymyr Mnih、Koray Kavukcuoglu、David Silver、Andrei A Rusu、Joel Veness、Marc G Bellemare、Alex Graves、Martin Riedmiller、Andreas Fidjeland、Georg Ostrovski、Stig Petersen、Charles Beattie、Amir Sadik、Antonoglou、Helen King、Dharshan Kumaran、Daan Wierstra、Shane Legg 和 Demis Hassabis。通过深度强化学习实现人类水平控制。*自然*，518：529–533，2015 年。

+   Ng & Russell (2000) Andrew Y. Ng 和 Stuart J. Russell。逆向强化学习的算法。见 Pat Langley (编), *第十七届国际机器学习会议（ICML 2000）论文集，斯坦福大学，斯坦福，加州，美国，2000 年 6 月 29 日 - 7 月 2 日*，第 663–670 页，2000 年。

+   Oh et al. (2020) Junhyuk Oh, Matteo Hessel, Wojciech M. Czarnecki, Zhongwen Xu, Hado van Hasselt, Satinder Singh 和 David Silver。发现强化学习算法。见 *神经信息处理系统会议（NeurIPS）*，2020 年。

+   Osband et al. (2016a) Ian Osband, Charles Blundell, Alexander Pritzel 和 Benjamin Van Roy。通过自助 DQN 进行深度探索。*神经信息处理系统会议（NeurIPS）*，2016a 年。

+   Osband et al. (2016b) Ian Osband, Benjamin Van Roy 和 Zheng Wen。通过随机化价值函数实现泛化与探索。见 *国际机器学习会议（ICML）*，2016b 年。

+   Pinto et al. (2017) Lerrel Pinto, James Davidson, Rahul Sukthankar 和 Abhinav Gupta。鲁棒的对抗性强化学习。*国际机器学习会议（ICML）*，2017 年。

+   Raileanu & Fergus (2021) Roberta Raileanu 和 Rob Fergus。强化学习中的价值与策略解耦以实现泛化。见 *国际机器学习会议（ICML）*，2021 年。

+   Schrittwieser et al. (2020) Julian Schrittwieser, Ioannis Antonoglou, Thomas Hubert, Karen Simonyan, Laurent Sifre, Simon Schmitt, Arthur Guez, Edward Lockhart, Demis Hassabis, Thore Graepel, Timothy P. Lillicrap 和 David Silver。通过规划和学习的模型掌握 Atari、围棋、国际象棋和将棋。*自然*，588(7839):604–609，2020 年。

+   Schulman et al. (2015) John Schulman, Sergey Levine, Philipp Moritz, Michael I. Jordan 和 Pieter Abbeel。信任区域策略优化。*计算机研究报告*，2015 年。

+   Silver et al. (2017) David Silver, Julian Schrittwieser, Karen Simonyan, Ioannis Antonoglou, Aja Huang, Arthur Guez, Thomas Hubert, Lucas Baker, Matthew Lai, Adrian Bolton, Yutian Chen, Timothy Lillicrap, Fan Hui, Laurent Sifre, George Driessche, Thore Graepel 和 Demis Hassabis。无须人类知识的围棋游戏掌握。*自然*，500:354–359，2017 年。

+   Szegedy et al. (2014) Christian Szegedy, Wojciech Zaremba, Ilya Sutskever, Joan Bruna, Dimutru Erhan, Ian Goodfellow 和 Rob Fergus。神经网络的有趣特性。*学习表征国际会议（ICLR）*，2014 年。

+   Taylor & Stone (2007) Matthew E. Taylor 和 Peter Stone。强化学习的跨领域迁移。见 *国际机器学习会议（ICML）*，2007 年。

+   Thrun & Schwartz (1993) Sebastian Thrun 和 Anton Schwartz。使用函数逼近进行强化学习的问题。*第四届连接主义模型暑期学校*，1993 年。

+   Tirinzoni et al. (2018) Andrea Tirinzoni, Rafael Rodriguez Sanchez 和 Marcello Restelli。通过变分方法进行价值函数的迁移。*神经信息处理系统会议（NeurIPS）*，2018 年。

+   van Hasselt（2010）Hado van Hasselt。双重 Q 学习。在 *神经信息处理系统大会（NeurIPS）*，2010。

+   Veeriah 等（2021）Vivek Veeriah、Tom Zahavy、Matteo Hessel、Zhongwen Xu、Junhyuk Oh、Iurii Kemaev、Hado van Hasselt、David Silver 和 Satinder Singh。通过元学习子目标发现选项。在 *神经信息处理系统大会（NeurIPS）*，2021。

+   Vieillard 等（2020a）Nino Vieillard、Tadashi Kozuno、Olivier Pietquin、Rémi Munos 和 Matthieu Geist。利用平均值：对强化学习中 KL 正则化的分析。在 *神经信息处理系统大会（NeurIPS）*，2020a。

+   Vieillard 等（2020b）Nino Vieillard、Olivier Pietquin 和 Matthieu Geist。Munchausen 强化学习。在 *神经信息处理系统大会（NeurIPS）*，2020b。

+   Vinyals 等（2019）Oriol Vinyals、Igor Babuschkin、Wojciech M. Czarnecki、Michaël Mathieu、Andrew Dudzik、Junyoung Chung、David H. Choi、Richard Powell、Timo Ewalds、Petko Georgiev、Junhyuk Oh、Dan Horgan、Manuel Kroiss、Ivo Danihelka、Aja Huang、L. Sifre、Trevor Cai、John P. Agapiou、Max Jaderberg、Alexander Sasha Vezhnevets、Rémi Leblond、Tobias Pohlen、Valentin Dalibard、David Budden、Yury Sulsky、James Molloy、Tom Le Paine、Caglar Gulcehre、Ziyun Wang、Tobias Pfaff、Yuhuai Wu、Roman Ring、Dani Yogatama、Dario Wünsch、Katrina McKinney、Oliver Smith、Tom Schaul、Timothy P. Lillicrap、Koray Kavukcuoglu、Demis Hassabis、Chris Apps 和 David Silver。利用多智能体强化学习在《星际争霸 II》中达到大宗师级别。*自然*，第 1–5 页，2019。

+   Wang 等（2020）Kaixin Wang、Bingyi Kang、Jie Shao 和 Jiashi Feng。在 RL 中通过混合正则化改善泛化。在 *神经信息处理系统大会（NeurIPS）*，2020。

+   Wang 等（2016）Ziyu Wang、Tom Schaul、Matteo Hessel、Hado Van Hasselt、Marc Lanctot 和 Nando De Freitas。用于深度强化学习的对抗网络架构。*国际机器学习大会（ICML）*，第 1995–2003 页，2016。

+   Watkins（1989）Chris Watkins。学习延迟奖励。在 *剑桥大学博士论文*，1989。

+   Wolczyk 等（2021）Maciej Wolczyk、Michal Zajac、Razvan Pascanu、Lukasz Kucinski 和 Piotr Milos。持续世界：一个用于持续强化学习的机器人基准。*神经信息处理系统大会（NeurIPS）*，2021。

+   Xu 等（2020）中英文 Xu、Hado Philip van Hasselt、Matteo Hessel、Junhyuk Oh、Satinder Singh 和 David Silver。通过在线发现目标的元梯度强化学习。在 *神经信息处理系统大会（NeurIPS）*，2020。

+   Yarats 等（2021）Denis Yarats、Ilya Kostrikov 和 Rob Fergus。图像增强即是你所需：从像素中正则化深度强化学习。在 *学习表示国际会议（ICLR）*，2021。
