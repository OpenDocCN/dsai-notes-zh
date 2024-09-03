<!--yml

分类：未分类

日期：2024-09-03 17:28:49

-->

# 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件

> 来源：[`arxiv.org/html/2406.05804`](https://arxiv.org/html/2406.05804)

1.  [1 引言](https://arxiv.org/html/2406.05804v2#S1 "在 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

    1.  [调研目的](https://arxiv.org/html/2406.05804v2#S1.SS0.SSS0.Px1 "在 1 引言 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

    1.  [贡献](https://arxiv.org/html/2406.05804v2#S1.SS0.SSS0.Px2 "在 1 引言 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

1.  [2 任务环境和工具环境](https://arxiv.org/html/2406.05804v2#S2 "在 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

    1.  [2.1 典型的任务环境](https://arxiv.org/html/2406.05804v2#S2.SS1 "在 2 任务环境和工具环境 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

    1.  [2.2 自然语言交互环境](https://arxiv.org/html/2406.05804v2#S2.SS2 "在 2 任务环境和工具环境 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

        1.  [单步骤 NLIEs 用于问答](https://arxiv.org/html/2406.05804v2#S2.SS2.SSS0.Px1 "在 2.2 自然语言交互环境 ‣ 2 任务环境和工具环境 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

        1.  [深思熟虑的多步骤 NLIEs](https://arxiv.org/html/2406.05804v2#S2.SS2.SSS0.Px2 "在 2.2 自然语言交互环境 ‣ 2 任务环境和工具环境 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

    1.  [2.3 工具环境](https://arxiv.org/html/2406.05804v2#S2.SS3 "在 2 任务环境和工具环境 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

        1.  [嵌套 NLIE-QA + 工具环境](https://arxiv.org/html/2406.05804v2#S2.SS3.SSS0.Px1 "在 2.3 工具环境 ‣ 2 任务环境和工具环境 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

1.  [3 LLM-剖析组件](https://arxiv.org/html/2406.05804v2#S3 "在 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

    1.  [通用 LLM-剖析组件](https://arxiv.org/html/2406.05804v2#S3.SS0.SSS0.Px1 "在 3 LLM-剖析组件 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

    1.  [任务依赖的 LLM-剖析组件](https://arxiv.org/html/2406.05804v2#S3.SS0.SSS0.Px2 "在 3 LLM-剖析组件 ‣ 基于 LLM 的智能体调研：常见工作流程和可重用的 LLM-剖析组件")

1.  [4 基于 LLM 的智能体工作流](https://arxiv.org/html/2406.05804v2#S4 "在《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

    1.  [4.1 仅策略工作流](https://arxiv.org/html/2406.05804v2#S4.SS1 "在 4 基于 LLM 的智能体工作流 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

    1.  [4.2 搜索工作流](https://arxiv.org/html/2406.05804v2#S4.SS2 "在 4 基于 LLM 的智能体工作流 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

        1.  [通过遍历和启发式搜索](https://arxiv.org/html/2406.05804v2#S4.SS2.SSS0.Px1 "在 4.2 搜索工作流 ‣ 4 基于 LLM 的智能体工作流 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

        1.  [基于 MCTS 的模拟搜索](https://arxiv.org/html/2406.05804v2#S4.SS2.SSS0.Px2 "在 4.2 搜索工作流 ‣ 4 基于 LLM 的智能体工作流 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

    1.  [4.3 反馈学习工作流](https://arxiv.org/html/2406.05804v2#S4.SS3 "在 4 基于 LLM 的智能体工作流 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

1.  [LMPCs 的 5 种实现](https://arxiv.org/html/2406.05804v2#S5 "在《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

    1.  [5.1 通用实现](https://arxiv.org/html/2406.05804v2#S5.SS1 "在 5 种 LMPCs 实现 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

    1.  [5.2 工作流特定实现](https://arxiv.org/html/2406.05804v2#S5.SS2 "在 5 种 LMPCs 实现 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

        1.  [$\text{glm}_{\text{policy}}$ 实现](https://arxiv.org/html/2406.05804v2#S5.SS2.SSS0.Px1 "在 5.2 工作流特定实现 ‣ 5 种 LMPCs 实现 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

        1.  [$\text{glm}_{\text{eval}}$ 实现](https://arxiv.org/html/2406.05804v2#S5.SS2.SSS0.Px2 "在 5.2 工作流特定实现 ‣ 5 种 LMPCs 实现 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

    1.  [5.3 任务特定实现](https://arxiv.org/html/2406.05804v2#S5.SS3 "在 5 种 LMPCs 实现 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

        1.  [$\text{glm}_{\text{policy}}$ 实现](https://arxiv.org/html/2406.05804v2#S5.SS3.SSS0.Px1 "在 5.3 任务特定实现 ‣ 5 种 LMPCs 实现 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

        1.  [ReAct 对 $\text{glm}_{\text{actor}}$ 的实现](https://arxiv.org/html/2406.05804v2#S5.SS3.SSS0.Px2 "在 5.3 任务特定实现 ‣ 5 种 LMPCs 实现 ‣ 《基于 LLM 的智能体调查：常见工作流与可重用 LLM 配置组件》中")

        1.  [$\text{glm}_{\text{eval}}$ 实现](https://arxiv.org/html/2406.05804v2#S5.SS3.SSS0.Px3 "在 5.3 特定任务实现 ‣ LMPC 的 5 种实现 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

1.  [6 未来工作](https://arxiv.org/html/2406.05804v2#S6 "在 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

    1.  [通用工具使用](https://arxiv.org/html/2406.05804v2#S6.SS0.SSS0.Px1 "在 6 未来工作 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

    1.  [跨任务统一框架](https://arxiv.org/html/2406.05804v2#S6.SS0.SSS0.Px2 "在 6 未来工作 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

    1.  [减少带宽](https://arxiv.org/html/2406.05804v2#S6.SS0.SSS0.Px3 "在 6 未来工作 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

1.  [7 结论](https://arxiv.org/html/2406.05804v2#S7 "在 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

1.  [A 基于 LLM 的代理框架](https://arxiv.org/html/2406.05804v2#A1 "在 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

1.  [B 示例提示](https://arxiv.org/html/2406.05804v2#A2 "在 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

    1.  [B.1 LLM-特征策略模型](https://arxiv.org/html/2406.05804v2#A2.SS1 "在 附录 B 示例提示 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

    1.  [B.2 针对 LLM 评估者的提示](https://arxiv.org/html/2406.05804v2#A2.SS2 "在 附录 B 示例提示 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

    1.  [B.3 作为动态模型的提示](https://arxiv.org/html/2406.05804v2#A2.SS3 "在 附录 B 示例提示 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

1.  [C 创建一个与任务无关的工具环境](https://arxiv.org/html/2406.05804v2#A3 "在 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

1.  [D 随机 $\text{glm}_{\text{actor}}$](https://arxiv.org/html/2406.05804v2#A4 "在 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

1.  [E 记忆](https://arxiv.org/html/2406.05804v2#A5 "在 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件")

# 基于 LLM 的代理调查：常见工作流程和可重用的 LLM-特征组件

Xinzhe Li

澳大利亚迪肯大学信息技术学院

lixinzhe@deakin.edu.au

###### 摘要

最近，大型语言模型（LLMs）的进展推动了开发基于 LLM 的代理的复杂框架的发展。然而，这些框架的复杂性在细微层面上提出了差异化的难题，这对于实现不同框架之间的高效实施和促进未来研究至关重要。因此，本次调查的主要目的是通过识别共同的工作流程和可重用的 LLM 配置组件（LMPCs），促进对近期提出的各种框架的整体理解。

关于基于 LLM 的代理的调查：常见工作流程和可重用的 LLM 配置组件

Xinzhe Li 信息技术学院，迪肯大学，澳大利亚 lixinzhe@deakin.edu.au

![参见说明](img/f9a75975e214ecdf9fabbe4ea870cee2.png)

(a) 仅政策工作流程。

![参见说明](img/781725a24fea6b105d150cbd77631b40.png)

(b) 搜索工作流程。

![参见说明](img/4fabd739ada261be693490ee136cfa46.png)

(c) 反馈学习工作流程。

图 1：基于三个 LLM 配置组件（政策、评估者和动态模型）的八种常见工作流程，适用于任务或/和工具使用环境。

## 1 引言

生成式大型语言模型（GLMs 或 LLMs）已经获得了广泛的常识和类人推理能力（Santurkar 等，[2023](https://arxiv.org/html/2406.05804v2#bib.bib15)；Wang 等，[2022](https://arxiv.org/html/2406.05804v2#bib.bib23)；Zhong 等，[2022](https://arxiv.org/html/2406.05804v2#bib.bib33)，[2023](https://arxiv.org/html/2406.05804v2#bib.bib32)），使其在构建被称为基于 LLM 的代理的 AI 代理中发挥关键作用。在本次调查的背景下，基于 LLM 的代理被定义为能够与外部工具（如 Wikipedia）或环境（如家庭环境）积极互动，并被设计为代理的核心组成部分，包括行动、规划和评估。

#### 调查目的

本次调查的动机来源于这样的观察：尽管存在各种技术和概念挑战，如搜索算法（Yao 等，[2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）、树结构（Hao 等，[2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）和强化学习（RL）组件（Shinn 等，[2023](https://arxiv.org/html/2406.05804v2#bib.bib16)），许多基于 LLM 的代理仍然包含类似的工作流程和组件。Wu 等（[2023](https://arxiv.org/html/2406.05804v2#bib.bib27)）提供了一种模块化的方法，但与流行的代理工作流程缺乏整合。Wang 等（[2024](https://arxiv.org/html/2406.05804v2#bib.bib21)）对 LLM 代理进行了全面的综述，探讨了它们在个人资料、记忆、规划和行动方面的能力。相比之下，我们的调查并不试图全面涵盖基于 LLM 的代理的所有组件。相反，我们集中于 LLM 在代理工作流程中的参与，并旨在澄清 LLM 在代理实现中的角色。我们创建了包含可重用的 LLM-Profiled 组件（LMPCs）的常见工作流程，如图 [1](https://arxiv.org/html/2406.05804v2#S0.F1 "Figure 1 ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 所示。

#### 贡献

本次调查提供了以下贡献：1) 缓解复杂框架的理解：现有框架的复杂性可以简化为可实施的工作流程，特别是当它们被提取用于特定任务时。本调查强调了可重用的工作流程和流行框架中的 LMPC（大语言模型配置），如 ReAct（Yao 等，[2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）、Reflexion（Shinn 等，[2023](https://arxiv.org/html/2406.05804v2#bib.bib16)）和 Tree-of-Thoughts（Yao 等，[2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）。具体来说，基于互动环境（§[2](https://arxiv.org/html/2406.05804v2#S2 "2 Task Environments And Tool Environments ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")）和常用 LMPC 的使用（§[3](https://arxiv.org/html/2406.05804v2#S3 "3 LLM-Profiled Components ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")），我们对各种工作流程进行了分类和详细描述，例如工具使用工作流程、搜索工作流程和反馈学习工作流程。许多现有框架由这些工作流程和 LMPC 组成，并结合了一些特定的非 LLM 组件。2) 帮助研究人员/从业者以更细致和一致的层次评估当前框架：第[4](https://arxiv.org/html/2406.05804v2#S4 "4 Workflows of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")节分类了主要框架，并展示了它们如何由共同的工作流程和 LMPC 组装，如表[2](https://arxiv.org/html/2406.05804v2#S3.T2 "Table 2 ‣ Task-Dependent LLM-Profiled Components ‣ 3 LLM-Profiled Components ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")所总结¹¹1 更详细的总结见附录[A](https://arxiv.org/html/2406.05804v2#A1 "Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")。3) 促进现有框架的进一步扩展：现有框架可以通过改变 LMPC 的实现来进行修改。为此，我们不仅总结了 LMPC 的实现，还总结了它们在不同工作流程和任务中的适用性，第[5](https://arxiv.org/html/2406.05804v2#S5 "5 Implementations of LMPCs ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")节提供了相关内容。

| 环境类型 | 与代理互动的实体 | 动作属性 | 动作实例示例 | 环境实例示例 |
| --- | --- | --- | --- | --- |
| 任务环境 |  |  |  |  |

| 游戏环境 | 虚拟游戏元素（对象、化身、其他角色），以及可能的其他玩家或游戏叙事 | 离散的、可执行的，

确定性 | Move(Right) | BlocksWorld, CrossWords |

| 具身环境 | 物理世界（通过传感器和执行器） | 离散的、可执行的，

确定性 | Pick_Up[Object] | AlfWorld（Shridhar et al., [2021](https://arxiv.org/html/2406.05804v2#bib.bib17)），VirtualHome，

Minecraft（Fan et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib3)） |

| NLIEs | 人类（通过对话或文本） | 自由形式、离散，

确定性

（单步 QA）

随机

（多步） | 答案是 Answer Finish[Answer] | GSM8K，HotpotQA |

| 工具环境（嵌套于任务环境中） |  |  |  |  |
| --- | --- | --- | --- | --- |

| 检索 | 检索 | 离散、可执行，

确定性，

非状态改变 | Wiki_Search[Entity] | 一个维基百科 API（Goldsmith，[2023](https://arxiv.org/html/2406.05804v2#bib.bib4)）（被 ReAct（Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）使用） |

| 计算器 | 计算器 | 可执行、确定性，

非状态改变 | 2 x 62 = << 计算器 >> | Python 的 eval 函数（被 MultiTool-CoT（Inaba et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib9)）使用） |

表 1：常见任务环境和工具使用环境。我们将 12 个主动工作流中存在的所有基准分为四种环境类型。一个行动实例通常由行动谓词和行动参数形式化。工具使用可以被认为是代理的内部环境，并且通常在 NLIEs 下为 QA 任务定义。

## 2 任务环境和工具环境

本节探讨任务环境和工具环境，这些环境与传统的 AI 和强化学习（RL）代理框架（Russell 和 Norvig，[2010](https://arxiv.org/html/2406.05804v2#bib.bib14)；Sutton 和 Barto，[2018](https://arxiv.org/html/2406.05804v2#bib.bib18)）相比，提供了不同的设置。在简要概述标准的基于逻辑的游戏和模拟体现环境后，我们重点关注两个特定领域：自然语言交互环境（NLIEs）和工具环境。

### 2.1 典型任务环境

通常，有两种常见的任务环境类型：1）基于规则的游戏环境：这些环境是确定性和完全可观察的，包括各种抽象战略游戏如国际象棋和围棋，以及逻辑谜题，如 24 点游戏（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）和 Blocksworld（Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）。它们要求深入的逻辑推理和战略规划来导航和解决。2）模拟体现环境：这些环境模拟现实世界的物理互动和空间关系。它们要求代理进行导航、对象操作和其他复杂的物理任务，反映物理环境的变化。

### 2.2 自然语言交互环境

随着大语言模型（LLM）代理的兴起，NLP 研究人员越来越倾向于将典型的 NLP 任务重新定义为代理环境（Yao 等人，[2023b](https://arxiv.org/html/2406.05804v2#bib.bib30); Hao 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib7); Yao 等人，[2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）。这些设置在我们的调查中被称为自然语言交互环境。

在 NLIEs 中，环境保持静态直到代理采取行动。与典型的任务环境中自然语言作为中介不同，在 NLIEs 中，状态和动作都是以语言方式定义的，使得状态概念化，动作通常模糊且广泛定义。

#### 单步 NLIEs 用于问答

许多研究（Yao 等人，[2023b](https://arxiv.org/html/2406.05804v2#bib.bib30); Shinn 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib16)）将传统问答设置表述为单步决策过程，其中代理生成一个回答以回应问题。这个过程以问题作为初始状态开始，并在提供答案作为动作后结束。

#### 深思熟虑的多步骤自然语言交互环境（NLIEs）

对于那些“中间步骤未明确定义”的任务，一些研究将自然语言处理（NLP）任务转化为马尔可夫决策过程，以便于代理工作流程。例如，Hao 等人 ([2023](https://arxiv.org/html/2406.05804v2#bib.bib7)) 将问答任务中的子问题重新表述为动作，通过多步骤过程来回应用户查询。这种方法允许初始问题作为一系列状态转移的开始。动作可以从在单步问答中提供直接的自由格式答案到战略性地形成子问题，引导代理通过顺序更新达到全面解决方案。此方法与顺序决策过程更为契合，适合在基于规划的代理系统中部署。此外，Wan 等人 ([2024](https://arxiv.org/html/2406.05804v2#bib.bib20)) 建议“将输出序列拆分成标记可能是定义多步骤 NLIEs 的好选择”。此外，Yao 等人 ([2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)) 将创造性写作中的两步 NLIEs 分为明确的规划和执行阶段。

### 2.3 工具环境

现代 LLM 代理通常通过外部工具来增强其问题解决能力（Inaba 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib9); Yao 等人，[2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）。这些工具的设计和集成增加了复杂性，需要仔细考虑 LLM 如何与任务环境以及这些辅助工具进行互动。通常，工具环境中的动作涉及与资源的互动，而这些互动不会影响资源。例如，从 Wikipedia 检索数据构成了“只读”操作，不会修改 Wikipedia 数据库。这个特点将这种工具使用行为与传统任务环境或典型的强化学习（RL）设置中的行为区分开来，后者的动作通常会改变环境状态。然而，重要的是要认识到工具环境可以是动态的，可能会发生外部变化。这一点反映了工具应该被视为外部环境，而非代理的内部过程。

#### 嵌套的 NLIE-QA + 工具环境

工具环境经常与 NLIEs 一起建立，以帮助解决 QA 任务。Shinn 等人 ([2023](https://arxiv.org/html/2406.05804v2#bib.bib16)); Yao 等人 ([2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)) 通过引入工具来增强回答的真实性。他们定义了类似命令的动作，如“Search”和“LookUp”以与 Wikipedia 互动，其中“Search”会从相关的 wiki 页面中建议前 5 个相似实体，而“LookUp”则模拟浏览器中的 Ctrl+F 功能。除了简单的检索外，Thoppilan 等人 ([2022](https://arxiv.org/html/2406.05804v2#bib.bib19)) 在对话任务中还包括了语言翻译器和计算器。类似地，Inaba 等人 ([2023](https://arxiv.org/html/2406.05804v2#bib.bib9)) 使用 Python eval 函数实现的计算器来解决 NumGLUE 基准中的数值查询。

## 3 LLM-配置组件

本节探讨了 LLM 通常被配置的常见代理角色。这些组件利用 LLM 的内部常识知识和推理能力来生成动作、计划、估算值²²2Values 指的是与在某个状态下采取某个动作相关的估计奖励（对结果的成功或期望的量化衡量），广泛用于典型的 RL 和 MDP 设置中，以学习执行期望行为的策略模型。以及推断后续状态。

#### 通用的 LLM-配置组件

具体而言，以下任务无关的组件经过配置，并在各种工作流程中广泛使用。*1) LLM-配置策略 $\text{glm}_{\text{policy}}$*：策略模型旨在生成决策，这些决策可能是执行外部环境中的某个动作或一系列动作（计划），也可以用于搜索和规划算法。³³3 请注意，规划算法可能会被用于结构化一系列计划；例如，Tree-of-Thought 使用树搜索，其中每个节点可能代表一个单独的动作或整个计划。与典型的 RL 策略模型通过试错来学习最大化累积奖励不同，LLM-配置策略模型（表示为 $\text{glm}_{\text{policy}}$）利用从广泛文本数据中获得的预训练知识和常识。我们区分两种类型的 $\text{glm}_{\text{policy}}$：一个 actor $\text{glm}_{\text{actor}}$ 直接将状态映射到动作，而一个 planner $\text{glm}_{\text{planner}}$ 从给定状态生成一系列动作。*2) LLM-配置评估器 $\text{glm}_{\text{eval}}$*：$\text{glm}_{\text{eval}}$ 提供对不同工作流程至关重要的反馈。它们在基于搜索的工作流程中评估动作和状态（Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7); Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)），并在反馈学习工作流程中修正决策（Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16); Wang et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib24)）（有关更多细节，请参见 §[4](https://arxiv.org/html/2406.05804v2#S4 "4 Workflows of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")）。这些评估器对于直接动作评估和更广泛的战略调整都至关重要。*3) LLM-配置动态模型 $\text{glm}_{\text{dynamic}}$*：它们预测或描述环境的变化。通常，动态模型通过预测从当前状态 $s$ 和动作 $a$ 得到的下一个状态 $s^{\prime}$ 来形成一个全面的世界模型。虽然典型的 RL 使用概率分布 $p(s^{\prime}\mid s,a)$ 来建模潜在的下一个状态，LLM 基于的动态模型直接预测下一个状态 $s^{\prime}=\text{glm}_{\text{dynamic}}(s,a)$。

#### 任务依赖的 LLM-配置组件

除了通用组件外，某些与 LLM（大语言模型）配置的组件是专门针对特定任务定制的。例如，**语言生成器**在具身环境中至关重要，但在 NLIE（自然语言推理任务）中则不必要。语言生成器将行动和观察转化为规划器的输入；例如，在**规划者-行动者-报告者**工作流中（Wang et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib22)），一个经过微调的**视觉语言模型**（VLM）与$\text{glm}_{\text{planner}}$一起将像素状态转换为文本输入。同样地，如果环境反馈可以感知到状态，那么可能需要一个语言生成器将这种反馈转化为$\text{glm}_{\text{policy}}$的文字描述，类似于在强化学习中生成数值刺激以进行策略学习。配置为语言生成器的 LLMs，$\text{glm}_{\text{verbalizer}}$（Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)），通常根据指定的标准指导描述。

| 工作流 | 相关框架 | LMPCs | 适用环境 |
| --- | --- | --- | --- |

| 仅策略 | 基础 | LLM 规划器（Huang et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib8)）、DEPS（Wang et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib24)）、规划者-行动者-报告者（Dasgupta et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib2)）、计划与解决（Wang et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib22)）、ReAct（Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)） | $\text{glm}_{\text{planner}}$、$\text{glm}_{\text{action\_selector}}$（具身环境可选） |

$\text{glm}_{\text{verbalizer}}$（具身环境可选） | 具身环境、NLIEs-写作、NLIE-QA |

|  | 工具使用 | MultiTool-CoT（Inaba et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib9)）、ReAct（Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）、Reflexion（Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)） | $\text{glm}_{\text{actor}}$ | NLIEs |
| --- | --- | --- | --- | --- |
| 搜索 | 遍历与启发式 | 思维树（ToT）（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）、树状束搜索（Xie et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib28)）、思维增强（Chen et al., [2024](https://arxiv.org/html/2406.05804v2#bib.bib1)） | $\text{glm}_{\text{actor}}$或$\text{glm}_{\text{planner}}$、$\text{glm}_{\text{eval}}$ | 游戏、NLIEs-写作、NLIE-QA |
|  | MCTS | RAP（Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）、Wan et al.（[2024](https://arxiv.org/html/2406.05804v2#bib.bib20)） | $\text{glm}_{\text{actor}}$、$\text{glm}_{\text{dynamic}}$、$\text{glm}_{\text{eval}}$ | 游戏、NLIEs-QA |
| 反馈学习 | 来自$\text{glm}_{\text{eval}}$ | Reflexion（Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)）、自我精炼（Madaan et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib12)） | $\text{glm}_{\text{actor}}$、$\text{glm}_{\text{eval}}$ | NLIEs-QA |
|  | 来自$\text{glm}_{\text{eval}}$ & 任务环境 | Reflexion（Shinn 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib16)） | $\text{glm}_{\text{actor}}$, $\text{glm}_{\text{eval}}$, $\text{glm}_{\text{fb\_verbalizer}}$ | 具身环境 |
|  | 来自工具与人类 | Guan 等人 ([2023](https://arxiv.org/html/2406.05804v2#bib.bib6)) | $\text{glm}_{\text{planner}}$, $\text{glm}_{\text{pddl\_translator}}$ | 具身环境 |
|  | 来自工具与$\text{glm}_{\text{eval}}$ | CRITIC（Gou 等人，[2024](https://arxiv.org/html/2406.05804v2#bib.bib5)） | $\text{glm}_{\text{actor}}$, $\text{glm}_{\text{eval}}$ | NLIEs |

表 2：LLM 基础代理的工作流程及相关框架。我们根据所列框架的原始论文总结了 LLM-Profiled Components（LMPCs）和适用环境，尽管也存在其他可能性，例如，在工具使用工作流程中使用$\text{glm}_{\text{planner}}$，以及将基本工作流程应用于游戏环境。

## 4 LLM 基础代理的工作流程

本节探讨了不同的工作流程及各种 LLM-Profiled Components（LMPCs）的利用，如图[1](https://arxiv.org/html/2406.05804v2#S0.F1 "Figure 1 ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")所示。具体而言，我们将根据工作流程类型汇总提出的框架，如表[2](https://arxiv.org/html/2406.05804v2#S3.T2 "Table 2 ‣ Task-Dependent LLM-Profiled Components ‣ 3 LLM-Profiled Components ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")所示。本节深入探讨了多样的工作流程及不同 LLM-Profiled Components（LMPCs）的应用，如图[1](https://arxiv.org/html/2406.05804v2#S0.F1 "Figure 1 ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")所示。我们将相关框架按照工作流程进行分类和整合，如表[2](https://arxiv.org/html/2406.05804v2#S3.T2 "Table 2 ‣ Task-Dependent LLM-Profiled Components ‣ 3 LLM-Profiled Components ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")所示。值得注意的是，一个框架可能根据任务或环境采用不同的工作流程。框架的更多细节总结在附录[A](https://arxiv.org/html/2406.05804v2#A1 "Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")中。

### 4.1 仅政策工作流程

基本和工具使用工作流只需要将 LLMs 配置为策略模型。在具身任务的领域中，许多项目使用$\text{glm}_{\text{planner}}$来生成使用 LLM 代理的计划，例如 LLM Planner（Huang et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib8)）、Planner-Actor-Reporter（Dasgupta et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib2)）和 DEPS（Wang et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib24)）。Plan-and-solve 方法（Wang et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib22)）将基本工作流应用于 NLIEs-QA。这种基本工作流也可以应用于其他 NLIE 任务，例如创意写作（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）。相比之下，使用$\text{glm}_{\text{actor}}$的工具使用工作流总是应用于 NLIEs，如 ReAct（Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）、Reflexion（Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)）和 MultiTool-CoT（Inaba et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib9)）。

### 4.2 搜索工作流

与基于$\text{glm}_{\text{planner}}$的基本代理不同，后者在一个生成过程中生成一系列动作，搜索工作流中的动作被组织成树（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29); Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）和图（Liu et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib11)）以进行探索。规划或搜索算法可以以非线性的方式探索顺序决策。在此过程中，树（或解决方案）通过添加节点来构建，每个节点表示一个部分解决方案，包括输入和到目前为止的思考/动作序列。树等数据结构使得可以在来自多个推理路径的动作上进行战略搜索。这通过使用如束搜索（Xie et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib28)）、深度优先和广度优先搜索（DFS 和 BFS）（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）以及蒙特卡洛树搜索（MCTS）（Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）等算法来完成。

通常，LMPCs 用于探索通往目标的路径。与在仅限策略的工作流中直接在外部环境上应用动作不同，$\text{glm}_{\text{policy}}$生成多个动作样本以促进搜索过程中的动作选择，而$\text{glm}_{\text{eval}}$用于计算在探索过程中进行动作/状态评估的值（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)；Chen et al., [2024](https://arxiv.org/html/2406.05804v2#bib.bib1)）或作为奖励模型（Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）。

#### 通过遍历和启发式搜索

Tree-of-Thoughts (ToT) 工作流 (Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)) 使用 $\text{glm}_{\text{policy}}$ 在树上扩展节点，而 $\text{glm}_{\text{eval}}$ 提供固定值估计来选择节点进行进一步扩展。为了扩展树，Tree-BeamSearch 工作流 (Xie et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib28)) 采用了束搜索，而 ToT 则应用了深度优先搜索/广度优先搜索 (DFS 和 BFS)。然而，BFS 实际上是带有 $N$ 束的束搜索，因为由效用模型 $\text{glm}_{\text{eval}}$ 生成的值用于维持 $N$ 个最有前途的节点。⁴⁴ 通常，BFS 不使用效用模型来决定扩展哪些节点，因为它系统地探索每个深度的所有可能节点。

#### 基于 MCTS 的模拟搜索

RAP 工作流 (Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)) 也通过搜索构建树，并包含 $\text{glm}_{\text{policy}}$ 和 $\text{glm}_{\text{eval}}$ 来扩展节点。然而，通过使用 MCTS，这种以模拟为驱动的搜索策略，选择扩展的节点不仅由 $\text{glm}_{\text{eval}}$ 或其他启发式方法的静态输出决定（无论它们是否指示目标达成），还由多个模拟中累积的统计数据决定。具体来说，导致所有模拟（或轨迹）中后续节点获得更好平均奖励的节点确实更有可能被进一步扩展。在选择阶段之后，$\text{glm}_{\text{policy}}$ 参与了扩展阶段的动作采样。然后，它与 $\text{glm}_{\text{dynamic}}$ 和 $\text{glm}_{\text{eval}}$ 在模拟阶段密切协作，充当滚动策略。具体来说，$\text{glm}_{\text{policy}}$ 根据当前状态 $s_{t}$ 采样一个动作 $a_{t}$，然后由 $\text{glm}_{\text{eval}}$ 评估。选择得分最高的动作，$\text{glm}_{\text{dynamic}}$ 使用该动作推导 $s_{t+1}$，并迭代模拟轨迹。

### 4.3 反馈学习工作流

主要有四个主要的反馈来源：$\text{glm}_{\text{eval}}$（内部反馈）、人类、任务环境和工具。

Reflexion (Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)) 和 Self-Refine (Madaan et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib12)) 利用 $\text{glm}_{\text{eval}}$ 对 $\text{glm}_{\text{policy}}$ 之前的生成结果进行反思，使 $\text{glm}_{\text{policy}}$ 从这些反思中学习。与在树扩展过程中使用 $\text{glm}_{\text{eval}}$ 的输出进行动作选择的搜索工作流不同，这里反馈用于修正整个决策，允许 $\text{glm}_{\text{policy}}$ 重新生成。在涉及物理交互的任务中，Reflexion 中的 $\text{glm}_{\text{eval}}$ 还整合了来自任务环境的外部信息 (Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16))。类似地，$\text{glm}_{\text{eval}}$ 可以从工具中接收信息以生成反馈，如 CRITIC 工作流中所示 (Gou et al., [2024](https://arxiv.org/html/2406.05804v2#bib.bib5))。在这种设置中，是否调用工具进行反馈由 $\text{glm}_{\text{eval}}$ 自主决定（参见表 [15](https://arxiv.org/html/2406.05804v2#A2.T15 "Table 15 ‣ B.2 Prompts for LLM Evaluators ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 以获取示例），而在 Reflexion 中，反馈传递由工作流设计硬编码。正如 Guan et al. ([2023](https://arxiv.org/html/2406.05804v2#bib.bib6)) 的工作流所指出，人类可以直接向 $\text{glm}_{\text{policy}}$ 提供反馈，而无需 $\text{glm}_{\text{eval}}$。

|  | 提示 | 示例工作 | 示例提示（见附录） |
| --- | --- | --- | --- |
| $\text{glm}_{\text{actor}}$ | 少样本 | ReAct (Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)), Reflexion (Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)), RAP (Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)), MultiTool-CoT (Inaba et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib9)) | 表 [8](https://arxiv.org/html/2406.05804v2#A1.T8 "Table 8 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components"), [10](https://arxiv.org/html/2406.05804v2#A1.T10 "Table 10 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") |
| $\text{glm}_{\text{planner}}$ | 零样本 | Plan-and-Solve (Wang et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib22)), LLM Planner (Huang et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib8)) | 表 [6](https://arxiv.org/html/2406.05804v2#A1.T6 "Table 6 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") |
|  | 少量样本 | DEPS (Wang et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib24)), Planner-Actor-Reporter (Dasgupta et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib2)) |  |
| $\text{glm}_{\text{evaluator}}$ | 少量样本 | RAP (Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)), Tree-BeamSearch (Xie et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib28)), Reflexion (Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)), CRITIC (Gou et al., [2024](https://arxiv.org/html/2406.05804v2#bib.bib5)) | 表 [12](https://arxiv.org/html/2406.05804v2#A2.T12 "表 12 ‣ B.2 LLM 评估器的提示 ‣ 附录 B 示例提示 ‣ 一项基于 LLM 的代理调查：常见工作流和可重用的 LLM 配置组件")、[13](https://arxiv.org/html/2406.05804v2#A2.T13 "表 13 ‣ B.2 LLM 评估器的提示 ‣ 附录 B 示例提示 ‣ 一项基于 LLM 的代理调查：常见工作流和可重用的 LLM 配置组件") |
| $\text{glm}_{\text{dynamic}}$ | 少量样本 | RAP (Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)) | 表 [16](https://arxiv.org/html/2406.05804v2#A2.T16 "表 16 ‣ B.3 作为动态模型的提示 ‣ 附录 B 示例提示 ‣ 一项基于 LLM 的代理调查：常见工作流和可重用的 LLM 配置组件") |

表 3: LLM 配置组件的提示方法

| 任务表述 | 反馈类型 | 适用工作流 | 示例工作 |
| --- | --- | --- | --- |
| 文本生成 | 自由形式反思 | 反馈学习工作流 | Self-Refine (Madaan et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib12)), Reflexion (Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)), CRITIC (Gou et al., [2024](https://arxiv.org/html/2406.05804v2#bib.bib5)) |
| 二分类/多分类 | 离散值 | 搜索工作流 | RAP (Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)), Tree-BeamSearch (Xie et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib28)) ToT (Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)) |
| 二分类 | 连续值（logits） | 通过 MCTS 的搜索工作流 | RAP (Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)) |
| 多选 QA | 前 N 个动作的选择 | 通过遍历和启发式的搜索工作流 | ToT (Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)) |

表 4: 根据任务表述和反馈类型的工作流特定 LLM 配置评估器

## 5 种 LMPC 实现

在本节中，我们探讨了 LMPC 的不同实现方法，涵盖了与特定工作流和任务无关的策略、专门为特定任务设计的实现以及针对特定工作流量身定制的实现。

### 5.1 通用实现

LLM 通常通过利用链式思维（CoT）提示来超越基本的输入输出推理，从而促进中间推理步骤的创建。这是通过两种技术实现的：零样本 CoT 将 CoT 触发器（如“Kojima et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib10)）的“让我们一步步思考”）集成到任务指令中，而少样本 CoT 则将手工制作的推理步骤包含在提供的示例中以进行上下文学习（Wei et al., [2022](https://arxiv.org/html/2406.05804v2#bib.bib25)）。

如表 [3](https://arxiv.org/html/2406.05804v2#S4.T3 "表 3 ‣ 4.3 反馈学习工作流 ‣ 4 基于 LLM 的代理工作流 ‣ 基于 LLM 的代理：常见工作流和可重用 LLM 配置组件的调查") 所示，一些研究（Wang et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib22)）采用零样本 CoT 提示，但大多数（Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)；Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16)；Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）通过少样本 CoT 实现 LLM 策略模型。与少样本 CoT 提示不同，零样本 CoT 实现的$\text{glm}_{\text{planner}}$通常无法生成长期规划（Wang et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib24)）。虽然有效，但少样本提示需要手动编制包含推理步骤的示例，从而增加了手动工作量和计算资源使用。像 Auto CoTs（Zhang et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib31)）这样的自动生成少样本示例的方法可以缓解这一挑战。

### 5.2 工作流特定实现

#### $\text{glm}_{\text{policy}}$ 实现

可以使用两种不同的实现方式来使$\text{glm}_{\text{policy}}$在工具使用和反馈学习工作流（接收来自工具的反馈）中触发工具使用。

1.  1.

    使用生成触发器：工具可以在推理生成过程中被调用，例如，MultiTool-CoT（Inaba 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib9)）。代理程序监控生成的每一个标记，当检测到工具触发时暂停文本生成。这种暂停允许调用工具，其输出被插入到提示中以完成推理。这些工具的触发器通过工具描述、少量示例演示 ⁵⁵5 生成触发器通过少量示例演示：参见表 [15](https://arxiv.org/html/2406.05804v2#A2.T15 "表 15 ‣ B.2 LLM 评估者的提示 ‣ 附录 B 示例提示 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM 定制组件")，或两者的组合 ⁶⁶6 生成触发器通过描述和少量示例演示：参见表 [8](https://arxiv.org/html/2406.05804v2#A1.T8 "表 8 ‣ 附录 A 基于 LLM 的代理框架 ‣ 基于 LLM 的代理调查：常见工作流程和可重用的 LLM 定制组件")。

1.  2.

    推理-行动（ReAct）策略用于工具使用：由 Yao 等人（[2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）提出，每个推理或行动步骤通过完整生成进行表达。虽然 ReAct 框架（Yao 等人，[2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）在工具使用工作流程中统一了工具操作，在基本工作流程中统一了任务特定操作，但我们认为工具操作和任务特定操作的策略应予以区分。由于工具操作和任务特定操作的触发方式不同，这一点将在关于任务特定实现的后续部分中进一步强调。

#### $\text{glm}_{\text{eval}}$ 实现

通常，不同的工作流程需要不同类型的反馈和任务制定。根据这两个视角，总结出四种情况，如表[4](https://arxiv.org/html/2406.05804v2#S4.T4 "Table 4 ‣ 4.3 Feedback-Learning Workflows ‣ 4 Workflows of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")所示：1) 生成自由形式的反思：这种反思输出通常会融入到反馈学习工作流程中的$\text{glm}_{\text{policy}}$提示中（Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16); Gou et al., [2024](https://arxiv.org/html/2406.05804v2#bib.bib5)）。$\text{glm}_{\text{eval}}$旨在反映反馈学习工作流程中的先前状态和行动。根据具体的反馈学习工作流程，它可能会结合任务或工具环境中的外部输入来丰富反思过程。2) 二分类/多分类：反馈来自离散的输出标记，通常为“no”或“yes”。这些标记可以转换为 0/1 值用于搜索工作流程。这些标量值可以在蒙特卡罗树搜索（MCTS）模拟中作为奖励信号（Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)），或者直接用于指导树遍历的每一步决策（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）。3) 带有标量值的二分类：这种方法与前一种方法不同，它通过使用标记的 logit 值来计算标量反馈值。例如，“yes”响应的概率可以通过以下公式计算：

|  | $v=\text{probs}_{\text{&quot;yes&quot;}}=\frac{e^{l_{\text{&quot;yes&quot;}}}}{e^{l_{\text{&quot;yes&quot;}}}% +e^{l_{\text{&quot;no&quot;}}}},$ |  |
| --- | --- | --- |

其中$l_{\text{&quot;yes&quot;}}$和$l_{\text{&quot;no&quot;}}$分别是“yes”和“no”标记的 logit 值。⁷⁷7 请注意，这些$\text{glm}_{\text{eval}}$的实现无法通过黑箱 LLMs 访问。这些标量值随后可以用于 MCTS 的搜索工作流程中的奖励。4) 多选 QA：在需要从多个选项中进行选择的环境中使用，支持涉及从前 N 个可能动作中选择的任务，如用于行动选择的搜索工作流程（Yao et al., [2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）。

### 5.3 任务特定的实现

#### $\text{glm}_{\text{policy}}$ 实现

值得注意的细节包括：1) 多步骤生成：对于那些本质上涉及顺序决策的任务（例如“把一个凉的番茄放进微波炉”），通常需要后处理步骤，使得$\text{glm}_{\text{policy}}$能够作为一个策略模型工作。在通过 CoT 实现$\text{glm}_{\text{policy}}$生成推理路径后，会进行后续调用以提取可执行动作。此外，$\text{glm}_{\text{planner}}$的首次生成通常包含必须进一步转化为原始动作的高级动作（HLA），然后才能提取可执行动作。对于 NLIE 任务，这通常是不必要的，因为计划生成和执行可能发生在单一的 LLM 生成中⁸⁸8 同时计划生成和执行：见表[6](https://arxiv.org/html/2406.05804v2#A1.T6 "Table 6 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")中的示例提示。2) 隐式规划：另一个需要考虑的点是，尽管$\text{glm}_{\text{actor}}$并未明确实现生成计划，它可能在推理阶段自动制定计划，然后再决定当前的行动（Shinn et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib16); Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)) ⁹⁹9 隐式规划：见表[7](https://arxiv.org/html/2406.05804v2#A1.T7 "Table 7 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")中的示例提示。这些生成的计划作为内部状态进行维护，不作为与其他组件的通信信号。

#### ReAct 对$\text{glm}_{\text{actor}}$的实现

ReAct 框架（Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)）在工具使用工作流和任务特定动作之间进行了统一。然而，推理和动作输出交替的顺序依赖于任务。对于问答（QA）任务，推理步骤和工具动作的生成是固定的，交替的提示用于思考和行动。¹⁰¹⁰10 推理-行动策略（QA 任务）：见表[10](https://arxiv.org/html/2406.05804v2#A1.T10 "Table 10 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")中的示例提示。相比之下，对于具身任务，是否在下一步继续思考或行动由$\text{glm}_{\text{policy}}$自主决定。¹¹¹¹11 推理-行动策略（具身任务）：见表[7](https://arxiv.org/html/2406.05804v2#A1.T7 "Table 7 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")中的示例提示。

#### $\text{glm}_{\text{eval}}$实现

$\text{glm}_{\text{eval}}$ 可以配置以评估不同的任务特定视角，具体的代理提示决定评估标准。一般来说，有用性可以用于评估任何动作（Hao et al., [2023](https://arxiv.org/html/2406.05804v2#bib.bib7)） ¹²¹²12 评估标准（有用性）：见表 [12](https://arxiv.org/html/2406.05804v2#A2.T12 "Table 12 ‣ B.2 Prompts for LLM Evaluators ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 中的示例提示。在 NLIE-QA 情境中，一个常见的指标是回应的事实性（真实性）（Gou et al., [2024](https://arxiv.org/html/2406.05804v2#bib.bib5)） ¹³¹³13 评估标准（事实性/真实性）：见表 [14](https://arxiv.org/html/2406.05804v2#A2.T14 "Table 14 ‣ B.2 Prompts for LLM Evaluators ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 和 [15](https://arxiv.org/html/2406.05804v2#A2.T15 "Table 15 ‣ B.2 Prompts for LLM Evaluators ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 中的示例提示。

## 6 未来工作

随着我们进一步探讨 LMPCs 和代理工作流，确定了几个未来研究的关键方向，以推动全自动代理在各种任务中的发展。

#### 通用工具使用

一个方向是超越为特定任务预定义的工具使用，发展能够使 LLMs 根据当前任务的具体需求自主确定工具使用的策略。另一个方向是将工具使用整合到政策模型和评估器中。换句话说，LLMs 可以在各种任务之间推理工具的使用，并灵活地在不同角色之间切换。其潜力的洞察在附录 [C](https://arxiv.org/html/2406.05804v2#A3 "Appendix C Creation of a Task-Agnostic Tool Environment ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 中有详细描述。

#### 任务之间的统一框架

如 §[5](https://arxiv.org/html/2406.05804v2#S5 "5 Implementations of LMPCs ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 中详细说明，尽管许多框架展示了集成的概念工作流，但许多组件是任务特定的。例如，ReAct 旨在协调工具动作和任务特定动作。然而，这些工作流和 LMPCs 的具体实现因任务而异，如 NLIE-QA 中的硬编码推理和行动步骤与具身环境中的自主确定推理和行动步骤。类似地，尽管 Reflexion 中的反馈学习循环在理论上是统一的，但在实践中，外部反馈仅在具身环境中生成，而在 NLIE-QA 中则没有。

#### 减少带宽

减少 LLM 推理所需带宽的几种潜在策略¹⁴¹⁴14 这里的带宽指的是在单次 LLM 生成过程中处理的信息量，包括使用随机$\text{glm}_{\text{actor}}$（详细信息见附录 [D](https://arxiv.org/html/2406.05804v2#A4 "附录 D 随机 "glm"_"actor" ‣ 基于 LLM 的代理调查：常见工作流程和可重用 LLM 概况组件")）。

## 结论

本调查提供了对常见工作流程和 LLM 概况组件的总结，以鼓励这些组件的重用，并通过集成任务特定的 LMPC 和非 LLM 组件来扩展现有工作流程。这种方法旨在促进代理工作流程的发展和可重复性。

## 限制

本调查省略了对记忆设计的讨论¹⁵¹⁵15 附录 [E](https://arxiv.org/html/2406.05804v2#A5 "附录 E 记忆 ‣ 基于 LLM 的代理调查：常见工作流程和可重用 LLM 概况组件")提供了关于基于 LLM 的代理的记忆以及外围组件在代理工作流程中的集成的简要讨论¹⁶¹⁶16 这些在附录 [A](https://arxiv.org/html/2406.05804v2#A1 "附录 A 基于 LLM 的代理框架 ‣ 基于 LLM 的代理调查：常见工作流程和可重用 LLM 概况组件")中简要总结，因为我们的重点是代理工作流程中常见的 LLM 概况组件的细节，以促进可重用组件和可扩展工作流程的实现。这使得我们的工作与其他调查显著不同。

## 参考文献

+   Chen et al. (2024) 司佳·陈、宝春·李和迪·牛。2024 年。[思想提升：使用大语言模型的试错问题解决](https://openreview.net/forum?id=qBL04XXex6)。在*第十二届国际学习表征会议*上。

+   Dasgupta et al. (2022) 伊希塔·达斯古普塔、克里斯汀·凯瑟-陈、肯尼斯·马里诺、阿伦·阿胡贾、谢拉·巴巴扬、费利克斯·希尔和罗布·弗格斯。2022 年。[与语言模型协作进行具身推理](https://openreview.net/forum?id=YoS-abmWjJc)。在*第二届语言与强化学习研讨会*上。

+   Fan et al. (2022) 林溪·范、关志·王、云凡·姜、阿杰·曼德卡、云聪·杨、浩毅·朱、安德鲁·唐、德安·黄、玉可·朱和安妮玛·安南德库马。2022 年。[Minedojo: 构建具有互联网规模知识的开放式具身代理](https://openreview.net/forum?id=rc8o_j8I8PX)。在*第 36 届神经信息处理系统大会数据集和基准测试分会*上。

+   Goldsmith (2023) 乔纳森·戈德史密斯。2023 年。[Wikipedia: 一个使访问和解析维基百科数据变得容易的 python 库](https://pypi.org/project/wikipedia/)。Python 包索引。

+   Gou et al. (2024) 苟志彬、邵志鸿、龚业云、沈夜龙、杨宇九、段楠、陈伟柱。2024 年。[CRITIC：大型语言模型可以通过工具互动批评进行自我修正](https://openreview.net/forum?id=Sx038qxjek)。发表于 *第十二届国际表征学习会议*。

+   Guan et al. (2023) 管林、卡尔蒂克·瓦尔梅卡姆、萨拉斯·斯里达兰、苏巴拉奥·坎班帕提。2023 年。[利用预训练的大型语言模型构建和利用世界模型以进行基于模型的任务规划](https://openreview.net/forum?id=zDbsSscmuj)。发表于 *第 37 届神经信息处理系统会议*。

+   Hao et al. (2023) 郝世博、顾毅、马浩迪、洪乔舒亚、王震、王黛西、胡志婷。2023 年。[与语言模型推理即是与世界模型规划](https://aclanthology.org/2023.emnlp-main.507)。发表于 *2023 年自然语言处理实证方法会议论文集*，第 8154–8173 页，新加坡。计算语言学协会。

+   Huang et al. (2022) 黄文龙、皮特·阿贝尔、迪帕克·帕塔克、伊戈尔·莫达奇。2022 年。语言模型作为零样本规划者：为具身代理提取可操作知识。发表于 *国际机器学习会议*，第 9118–9147 页。PMLR。

+   Inaba et al. (2023) 稻叶达郎、清丸浩和、程飞、黑桥定雄。2023 年。[MultiTool-CoT：GPT-3 可以使用多个外部工具与思维链提示](https://doi.org/10.18653/v1/2023.acl-short.130)。发表于 *第 61 届计算语言学协会年会（第 2 卷：短篇论文）*，第 1522–1532 页，加拿大多伦多。计算语言学协会。

+   Kojima et al. (2022) 小岛健志、郭时翔、马切尔·里德、松尾丰、岩泽友祐。2022 年。[大型语言模型是零样本推理器](https://openreview.net/forum?id=e2TBb5y0yFf)。发表于 *神经信息处理系统进展*。

+   Liu et al. (2023) 刘汉萌、滕志阳、崔乐扬、张超力、周奇姝、张跃。2023 年。[Logicot：逻辑思维链指令微调](http://arxiv.org/abs/2305.12147)。

+   Madaan et al. (2023) 阿曼·马达安、尼凯特·坦登、普拉卡什·古普塔、斯凯勒·哈利南、刘宇、高璐、莎拉·维格雷夫、乌里·阿隆、努哈·兹里、施里梅·普拉布莫耶、杨一鸣等。2023 年。Self-refine：自我反馈的迭代精炼。*arXiv 预印本 arXiv:2303.17651*。

+   Manakul et al. (2023) 潘萨维·马纳库尔、艾迪安·刘斯、马克·JF·盖尔斯。2023 年。Selfcheckgpt：用于生成大型语言模型的零资源黑箱幻觉检测。*arXiv 预印本 arXiv:2303.08896*。

+   Russell and Norvig (2010) 斯图尔特·J·拉塞尔、彼得·诺维格。2010 年。*人工智能：一种现代方法*。伦敦。

+   Santurkar et al. (2023) 席巴尼·桑图卡尔、艾辛·杜尔穆斯、费萨尔·拉达克、奇诺·李、佩西·梁、辰野桥本。2023 年。语言模型反映了谁的观点？ *arXiv 预印本 arXiv:2303.17548*。

+   Shinn 等（2023）Noah Shinn、Federico Cassano、Edward Berman、Ashwin Gopinath、Karthik Narasimhan 和 Shunyu Yao。2023 年。[Reflexion: 带有语言强化学习的语言代理](http://arxiv.org/abs/2303.11366)。

+   Shridhar 等（2021）Mohit Shridhar、Xingdi Yuan、Marc-Alexandre Cote、Yonatan Bisk、Adam Trischler 和 Matthew Hausknecht。2021 年。[{ALFW}orld: 对齐文本和具身环境以实现交互式学习](https://openreview.net/forum?id=0IOX0YcCdTn)。在 *国际学习表征会议* 上。

+   Sutton 和 Barto（2018）Richard S Sutton 和 Andrew G Barto。2018 年。*强化学习：导论*。MIT 出版社。

+   Thoppilan 等（2022）Romal Thoppilan、Daniel De Freitas、Jamie Hall、Noam Shazeer、Apoorv Kulshreshtha、Heng-Tze Cheng、Alicia Jin、Taylor Bos、Leslie Baker、Yu Du 等。2022 年。Lamda: 对话应用的语言模型。*arXiv 预印本 arXiv:2201.08239*。

+   Wan 等（2024）Ziyu Wan、Xidong Feng、Muning Wen、Ying Wen、Weinan Zhang 和 Jun Wang。2024 年。[类似 AlphaZero 的树搜索可以指导大型语言模型的解码和训练](https://openreview.net/forum?id=fLO9VaAb3B)。

+   Wang 等（2024）Lei Wang、Chen Ma、Xueyang Feng、Zeyu Zhang、Hao Yang、Jingsen Zhang、Zhiyuan Chen、Jiakai Tang、Xu Chen、Yankai Lin 等。2024 年。一项关于基于大型语言模型的自主代理的调查。*计算机科学前沿*, 18(6):1–26。

+   Wang 等（2023a）Lei Wang、Wanyu Xu、Yihuai Lan、Zhiqiang Hu、Yunshi Lan、Roy Ka-Wei Lee 和 Ee-Peng Lim。2023a 年。[计划与解决提示: 通过大型语言模型改进零样本链式思维推理](https://doi.org/10.18653/v1/2023.acl-long.147)。在 *第 61 届计算语言学协会年会（第 1 卷: 长篇论文）* 上，第 2609–2634 页，加拿大多伦多。计算语言学协会。

+   Wang 等（2022）Siyuan Wang、Zhongkun Liu、Wanjun Zhong、Ming Zhou、Zhongyu Wei、Zhumin Chen 和 Nan Duan。2022 年。[来自 lsat: 复杂推理的进展与挑战](https://doi.org/10.1109/TASLP.2022.3164218)。*IEEE/ACM Trans. Audio, Speech and Lang. Proc.*, 30:2201–2216。

+   Wang 等（2023b）Zihao Wang、Shaofei Cai、Guanzhou Chen、Anji Liu、Xiaojian Ma 和 Yitao Liang。2023b 年。[描述、解释、规划和选择: 通过 LLMs 实现开放世界多任务代理的交互式规划](https://openreview.net/forum?id=KtvPdGb31Z)。在 *第三十七届神经信息处理系统会议* 上。

+   Wei 等（2022）Jason Wei、Xuezhi Wang、Dale Schuurmans、Maarten Bosma、brian ichter、Fei Xia、Ed H. Chi、Quoc V Le 和 Denny Zhou。2022 年。[思维链提示引发大型语言模型的推理](https://openreview.net/forum?id=_VjQlMeSB_J)。在 *神经信息处理系统进展* 上。

+   Willard 和 Louf（2023）Brandon T Willard 和 Rémi Louf。2023 年。高效引导生成用于 LLMs。*arXiv 预印本 arXiv:2307.09702*。

+   Wu 等人（2023）Qingyun Wu, Gagan Bansal, Jieyu Zhang, Yiran Wu, Shaokun Zhang, Erkang Zhu, Beibin Li, Li Jiang, Xiaoyun Zhang, 和 Chi Wang. 2023. Autogen: 通过多代理对话框架实现下一代 LLM 应用。*arXiv 预印本 arXiv:2308.08155*。

+   Xie 等人（2023）Yuxi Xie, Kenji Kawaguchi, Yiran Zhao, Xu Zhao, Min-Yen Kan, Junxian He, 和 Qizhe Xie. 2023. [自我评估引导的束搜索用于推理](https://openreview.net/forum?id=Bw82hwg5Q3)。在 *第三十七届神经信息处理系统会议*。

+   Yao 等人（2023a）Shunyu Yao, Dian Yu, Jeffrey Zhao, Izhak Shafran, Thomas L. Griffiths, Yuan Cao, 和 Karthik Narasimhan. 2023a. [思维树：使用大型语言模型的深思熟虑问题解决](http://arxiv.org/abs/2305.10601)。

+   Yao 等人（2023b）Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik R Narasimhan, 和 Yuan Cao. 2023b. [React: 语言模型中的推理与行动协同](https://openreview.net/forum?id=WE_vluYUL-X)。在 *第十一届国际学习表征会议*。

+   Zhang 等人（2023）Zhuosheng Zhang, Aston Zhang, Mu Li, 和 Alex Smola. 2023. 大型语言模型中的自动思维链提示。在 *第十一届国际学习表征会议（ICLR 2023）*。

+   Zhong 等人（2023）Wanjun Zhong, Ruixiang Cui, Yiduo Guo, Yaobo Liang, Shuai Lu, Yanlin Wang, Amin Saied, Weizhu Chen, 和 Nan Duan. 2023. Agieval: 一种以人为本的基础模型评估基准。*arXiv 预印本 arXiv:2304.06364*。

+   Zhong 等人（2022）Wanjun Zhong, Siyuan Wang, Duyu Tang, Zenan Xu, Daya Guo, Yining Chen, Jiahai Wang, Jian Yin, Ming Zhou, 和 Nan Duan. 2022. [文本的分析推理](https://doi.org/10.18653/v1/2022.findings-naacl.177)。在 *Findings of the Association for Computational Linguistics: NAACL 2022*，第 2306–2319 页，美国西雅图。计算语言学协会。

## 附录 A 大型语言模型基础代理框架

表格 [5](https://arxiv.org/html/2406.05804v2#A1.T5 "表格 5 ‣ 附录 A 大型语言模型基础代理框架 ‣ LLM 基础代理的调查：常见工作流程与可重用的 LLM 配置组件") 展示了每个框架的工作流程、LMPCs 和非 LMPC 组件。

|  | 相关工作流程 | LMPCs | 非 LMPC 组件 | 应用环境 |
| --- | --- | --- | --- | --- |
| 思维树（ToT） (Yao 等人，[2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)) | 通过遍历与启发式搜索 | $\text{glm}_{\text{actor}}$, $\text{glm}_{\text{eval}}$, $\text{glm}_{\text{planner}}$（仅用于 NLIEs-Writing） | 搜索树 | 游戏；NLIEs-Writing |
| Tree-BeamSearch (Xie 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib28)) | 基于搜索的遍历与启发式 | $\text{glm}_{\text{actor}}$, $\text{glm}_{\text{eval}}$ | 搜索树 | NLIE-QA |
| RAP（Hao 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib7)） | 通过 MCTS 搜索 | $\text{glm}_{\text{actor}}$，$\text{glm}_{\text{dynamic}}$，$\text{glm}_{\text{eval}}$ | 搜索树 | 游戏；NLIEs-QA |
| LLM Planner（Huang 等人，[2022](https://arxiv.org/html/2406.05804v2#bib.bib8)） | 基础 | $\text{glm}_{\text{planner}}$ | 用于行动翻译的 MLM | 实体环境 |
| DEPS（Wang 等人，[2023b](https://arxiv.org/html/2406.05804v2#bib.bib24)） | 基础 | $\text{glm}_{\text{planner}}$，$\text{glm}_{\text{action\_selector}}$，$\text{glm}_{\text{verbalizer}}$ | 立即 actor，VLM+GLM 作为表述者 | 实体环境 |
| Planner-Actor-Reporter（Dasgupta 等人，[2022](https://arxiv.org/html/2406.05804v2#bib.bib2)） | 基础 | $\text{glm}_{\text{planner}}$ | 强化学习 actor，训练分类器+硬编码作为表述者 | 实体环境 |
| Plan-and-solve（Wang 等人，[2023a](https://arxiv.org/html/2406.05804v2#bib.bib22)） | 基础 | $\text{glm}_{\text{planner}}$ | / | NLIEs-QA |
| MultiTool-CoT（Inaba 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib9)） | 工具使用 | $\text{glm}_{\text{actor}}$ | / | NLIEs |
| ReAct（Yao 等人，[2023b](https://arxiv.org/html/2406.05804v2#bib.bib30)） | 工具使用 | $\text{glm}_{\text{actor}}$ | / | NLIEs |
|  | 基础 | $\text{glm}_{\text{actor}}$ | / | 实体环境 |
| Guan 等人（[2023](https://arxiv.org/html/2406.05804v2#bib.bib6)） | 反馈学习（来自工具和人） | $\text{glm}_{\text{planner}}$，$\text{glm}_{\text{pddl\_translator}}$ | 领域专家，领域无关规划器 | 实体环境 |
| CRITIC（Gou 等人，[2024](https://arxiv.org/html/2406.05804v2#bib.bib5)） | 反馈学习（来自工具和$\text{glm}_{\text{eval}}$） | $\text{glm}_{\text{actor}}$ | / | NLIEs |
| Self-refine（Madaan 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib12)） | 反馈学习（来自$\text{glm}_{\text{eval}}$） | $\text{glm}_{\text{actor}}$，$\text{glm}_{\text{eval}}$， | / | NLIEs |

| Reflexion（Shinn 等人，[2023](https://arxiv.org/html/2406.05804v2#bib.bib16)） | 反馈学习（来自$\text{glm}_{\text{eval}}$），

工具使用 | $\text{glm}_{\text{actor}}$，$\text{glm}_{\text{eval}}$， | / | NLIEs-QA |

|  | 反馈学习（来自任务环境和$\text{glm}_{\text{eval}}$）， | $\text{glm}_{\text{actor}}$，$\text{glm}_{\text{eval}}$，$\text{glm}_{\text{fb\_verbalizer}}$ | $\text{heuristic\_func}_{\text{eval}}$ | 实体环境 |
| --- | --- | --- | --- | --- |

表 5：基于 LLM 的代理的框架。MLM：屏蔽语言模型。

| 问题：在一个有 20 名学生的舞蹈班中，有 20%的人报名现代舞蹈，剩下的 25%报名爵士舞蹈，其他人报名街舞。整个学生中有多少百分比的人报名了街舞？ 答：让我们首先理解问题，并制定解决问题的计划。

然后，让我们逐步执行计划，解决问题。

计划: <svg class="ltx_picture" height="192.22" id="A1.T6.3.3.3.3.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,192.22) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="163.28" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">步骤 1: 计算报名参加现代舞和爵士舞的学生总数。

步骤 2: 计算报名参加嘻哈舞的学生总数。

步骤 3: 计算报名参加嘻哈舞的学生百分比。

解决方案:

步骤 1: $20\%$的 20 名学生是 4 名学生。$25\%$的剩余 16 名学生是 4 名学生。所以，总共有 8 名学生报名参加现代舞和爵士舞。

步骤 2: 剩下的 12 名学生报名参加了嘻哈舞。

步骤 3: 报名参加嘻哈舞的学生比例是$12/20=60\%$。</foreignobject></g></g></svg> 因此，答案（阿拉伯数字）是 <svg class="ltx_picture" height="40.09" id="A1.T6.4.4.4.4.p2.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,40.09) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="11.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">60%</foreignobject></g></g></svg> |

表 6: 一个在 NLIE-QA 下的 LLM 规划器，由零-shot CoT 方法实现。CoT 触发器以红色字体突出显示。阴影框中的内容由 LLM 生成。来源于 Wang 等人（[2023a](https://arxiv.org/html/2406.05804v2#bib.bib22)）

| 与家庭成员互动以解决任务。这里有两个示例。你在房间中间。快速环顾四周，你看到一个柜子 9、一个柜子 8、一个柜子 7、一个柜子 6、一个柜子 5、一个柜子 4、一个柜子 3、一个柜子 2、一个柜子 1、一个咖啡机 1、一个台面 3、一个台面 2、一个台面 1、一个抽屉 9、一个抽屉 8、一个抽屉 7、一个抽屉 6、一个抽屉 5、一个抽屉 4、一个抽屉 3、一个抽屉 2、一个抽屉 1、一个冰箱 1、一个垃圾桶 1、一个微波炉 1、一个架子 3、一个架子 2、一个架子 1、一个水槽 1、一个炉灶 1、一个炉灶 2、一个炉灶 3、一个炉灶 4，以及一个烤面包机 1。你的任务是: 将一个凉的杯子放到架子上。

> think: 为了完成任务，我需要找到一个杯子，然后用冰箱将它冷却，然后把它放到架子上。

好的。

> think: 首先，我需要找到一个杯子。杯子更可能出现在台面（1-3）、咖啡机（1）、柜子（1-9）、架子（1-3）、抽屉（1-9）中。我可以一个一个检查，从台面 1 开始。

好的。

> 去台面 1

在台面 1 上，你看到一个刀子 1、一个锅 2、一个锅 1 和一个盘子 1。

…

> think: 现在我把杯子凉下来。接下来，我需要把它放在架子 1 上。好的。
> 
> 去架子 1

在架子 1 上，你看到一个杯子 2、一个杯子 1、一个胡椒瓶 1 和一个盐瓶 1。

> 把杯子 3 放在/放到架子 1 上

你把杯子 3 放在/放到架子 1 上。任务是：你在房间的中间。环顾四周，你看到一个橱柜 6、橱柜 5、橱柜 4、橱柜 3、橱柜 2、橱柜 1、咖啡机 1、台面 3、台面 2、台面 1、抽屉 3、抽屉 2、抽屉 1、冰箱 1、垃圾桶 1、微波炉 1、架子 3、架子 2、架子 1、水槽盆 1、炉子燃烧器 4、炉子燃烧器 3、炉子燃烧器 2、炉子燃烧器 1 和一个烤面包机 1。

你的任务是：把一个冷番茄放进微波炉。

> <svg class="ltx_picture" height="55.16" id="A1.T7.1.1.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,55.16) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="26.21" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">思考：为了解决任务，我需要找到一个番茄，然后用冰箱冷却它，最后放进微波炉。</foreignobject></g></g></svg> 好的。
> 
> <svg class="ltx_picture" height="73.76" id="A1.T7.2.2.2.2.p2.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,73.76) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="44.82" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">思考：首先，我需要找到一个番茄。番茄更可能在台面（1-3）、橱柜（1-6）、抽屉（1-3）、架子（1-3）或水槽盆中。我可以从检查台面 1 开始。</foreignobject></g></g></svg> 好的。 > <svg class="ltx_picture" height="40.55" id="A1.T7.3.3.3.3.p3.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,40.55) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="11.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">前往台面 1</foreignobject></g></g></svg> 在台面 1 上，你看到一个海绵 1 和一个杯子 2。…

表 7：一个 LLM Actor 在 Alfred 世界基准测试下的基础工作流中，采用了少量示例 CoT 方法。阴影框中的内容由 LLM 生成。来源 (Yao et al., [2023b](https://arxiv.org/html/2406.05804v2#bib.bib30))。

| 使用以下工具回答一些问题： |
| --- |
| - <<计算器>> |
| - <<化学反应预测器>> |
| - <<摩尔质量列表>> |
| 问：找出将 2 摩尔的 $\mathrm{CO}2$ 和 2 摩尔的 $\mathrm{H}2\mathrm{O}$ 结合形成的 $\mathrm{H}2\mathrm{CO}3$ 的量。 |
| 答：首先，使用化学反应预测器确定反应的化学方程式。 |
| 反应物：$2\mathrm{CO}2,2\mathrm{H}2\mathrm{O}$ |
| 产物：?$ \mathrm{H}2\mathrm{CO}3$ |
| <<化学反应预测器>> |
| $2\mathrm{CO}2+2\mathrm{H}2\mathrm{O}\rightarrow 2\mathrm{H}2\mathrm{CO}3$ |
| 第二，使用摩尔质量列表确定$\mathrm{H}2\mathrm{CO}3$的摩尔质量。$\mathrm{H}2\mathrm{CO}3$ <<摩尔质量列表>> $62\mathrm{~{}g}/\mathrm{mol}$ |
| 第三，使用计算器计算 2 摩尔$\mathrm{H}2\mathrm{CO}3$的量。$2\times 62=$ <<计算器>> $124$ |
| 因此，形成了$124\mathrm{~{}g}$的$\mathrm{H}2\mathrm{CO}3$。 |
| 问：找出反应 2 摩尔二氧化碳形成 2 摩尔碳酸钙和 2 摩尔水所需的氢氧化钙的量。 |
| 答： |

表 8：通过 MultiTool-CoT（Inaba 等， [2023](https://arxiv.org/html/2406.05804v2#bib.bib9)）实现工具使用的 LLM 演员。

| 问：朱莉在读一本 120 页的书。昨天，她读了 12 页，今天她读了昨天的两倍页数。如果她想明天读剩下页数的一半，她应该读多少页？答：朱莉今天读了昨天的两倍，所以她今天读了 12 * 2 = 24 页。因为昨天朱莉读了 12 页，加上今天的 24 页，总共读了 12 + 24 = 36 页。所以，还剩 120 - 36 = 84 页。由于她想读剩下页数的一半，所以她应该读 84 / 2 = 42 页。答案是 42。

问：肯制作了一个护理包准备寄给在寄宿学校的弟弟。肯将一个箱子放在称上，然后倒入足够的糖果豆，使得重量达到 2 磅。接着，他添加了足够的布朗尼，使得重量增加到三倍。然后，他又添加了 2 磅的糖果豆。最后，他添加了足够的软糖虫，使得重量再次翻倍。这个装满美食的箱子的最终重量是多少磅？

答：肯往箱子里倒了足够的糖果豆，使得箱子的重量为 2 磅，所以箱子的初始重量是 2 磅。然后，肯添加了足够的布朗尼，使得重量增加到三倍，所以箱子的重量是 2 * 3 = 6 磅。之后，肯再添加了 2 磅的糖果豆，使得箱子的重量变成 6 + 2 = 8 磅。最后，他添加了足够的软糖虫，使重量再次翻倍，所以箱子的重量是 8 * 2 = 16 磅。答案是 16。

问：詹姆斯每周给两个不同的朋友写三页的信。他一年写多少页？

答：詹姆斯每周给两个不同的朋友写三页的信，每周写 3 * 2 * 2 = 12 页。一年有 52 周，所以他每年写 12 * 52 = 624 页。答案是 624。

问：娜塔莉亚在四月卖出了 48 个夹子，然后在五月卖出了一半的夹子。娜塔莉亚在四月和五月总共卖出了多少个夹子？

A: 纳塔利亚在 4 月销售了 48 个夹子，5 月销售了一半的夹子，因此她在 5 月销售了 48 / 2 = 24 个夹子。总共，她销售了 48 + 24 = 72 个夹子。答案是 72。

问：珍妮特的鸭子每天产 16 个蛋。她每天早上吃三个作为早餐，并且每天用四个做蛋糕给朋友们吃。她在农贸市场上以每个新鲜鸭蛋 2 美元的价格出售剩余的蛋。她每天在农贸市场上赚多少钱？

A:" <svg class="ltx_picture" height="91.82" id="A1.T9.1.1.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,91.82) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="62.88" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">珍妮特的鸭子每天产 16 个蛋。她每天早上吃三个作为早餐，并且每天用四个做蛋糕给朋友们吃，所以她每天使用 3 + 4 = <<3+4=7>>7 个蛋。因此，她每天在农贸市场上出售 16 - 7 = <<16-7=9>>9 个蛋。因此，她每天在农贸市场上赚取 9 * $2 = $<<9*2=18>>18。答案：18。</foreignobject></g></g></svg> |

表格 9：在 NLIE-QA 下的工具使用工作流中使用少量示例 CoT 方法实现的 LLM 演员。阴影框中的内容由 LLM 生成。

| 通过先进行思考来解决问题回答任务，然后用你的答案完成。思考可以推理当前情况。完成[答案]返回答案并结束任务。 |
| --- |
| 以下是一些示例： |
| 问题 1：科罗拉多造山带东部区域的海拔范围是多少？ |
| 思考：我们一步一步来考虑。科罗拉多造山带的东部区域延伸到高原地区。高原的海拔从约 1,800 英尺上升到 7,000 英尺，因此答案是 1,800 到 7,000 英尺。 |
| 行动：完成[1,800 到 7,000 英尺] |
| … |
| 问题 6：帕维尔·乌里索夫和列昂尼德·列文是否以相同类型的工作著称？ |
| 思考：我们一步一步来考虑。帕维尔·乌里索夫是数学家。列昂尼德·列文是数学家和计算机科学家。因此，帕维尔·乌里索夫和列昂尼德·列文的工作类型相同。 |
| 行动：完成[是] |
| 示例结束) |
| 问题：VIVA Media AG 在 2004 年更改了名称。它们的新缩写代表什么？ |
| 思考: <svg class="ltx_picture" height="92.59" id="A1.T10.1.1.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,92.59) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="63.65" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">让我们一步步思考。VIVA Media AG 在 2004 年更改了名称。新的首字母缩写必须代表他们采用的新名称。为了找到答案，我们需要研究 VIVA Media AG 在 2004 年之后的新名称。操作: 完成[需要进一步研究以确定新的首字母缩写。]</foreignobject></g></g></svg> |
| 操作: <svg class="ltx_picture" height="42.78" id="A1.T10.3.3.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,42.78) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="13.84" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">完成[需要进一步研究以确定新的首字母缩写。]</foreignobject></g></g></svg> |

表 10: HotPot-QA 基准测试中用于工具使用工作流的 LLM Actor，由少量示例 CoT 实现。阴影框中的内容由 LLM 生成。来源于 Yao 等人 ([2023b](https://arxiv.org/html/2406.05804v2#bib.bib30))。

| 给定一个问题，请将其拆解为子问题。对于每个子问题，请用完整的句子回答，并以“答案是”结尾。当原始问题可以回答时，请以“现在我们可以回答这个问题:”开始子问题。 |
| --- |
| 问题 1: James 每周写两次 3 页的信给两个不同的朋友。他一年写多少页？ |
| 问题 1.1: 他每周写多少页？ |
| 答案 1.1: James 每周写 3 * 2 * 2 = 12 页信。答案是 12。 |
| 问题 1.2: 一年有多少周？ |
| 答案 1.2: 一年有 52 周。答案是 52。 |
| 问题 1.3: 现在我们可以回答这个问题：他一年写多少页？ |
| 答案 1.3: James 每周写 12 页，因此他一年写 12 * 52 = 624 页。答案是 624。 |
| … |
| 问题 5: Janet 的鸭子每天产 16 个蛋。她每天早晨吃三个做早餐，然后用四个给朋友们烤松饼。她每天在农贸市场上以每个新鲜鸭蛋 2 美元的价格出售剩余的蛋。她每天在农贸市场上赚多少钱？ |
| 问题 5.1: <svg class="ltx_picture" height="55.16" id="A1.T11.1.1.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,55.16) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="26.21" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">Janet 吃掉三个早餐蛋和用四个蛋做了松饼后还剩下多少个蛋？</foreignobject></g></g></svg> |

表格 11：GSM8K 基准下的 LLM 执行者。阴影框中的内容由 LLM 生成。来源于 Hao 等人（[2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）。

## 附录 B 示例提示

### B.1 LLM 定制策略模型

1) 基本工作流：NLIE-QA 的规划器和家庭环境（ALFRED）的执行者分别在表格[6](https://arxiv.org/html/2406.05804v2#A1.T6 "Table 6 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")和[7](https://arxiv.org/html/2406.05804v2#A1.T7 "Table 7 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")中演示。2) 工具使用工作流：NLIE-QA 下的执行者在表格[8](https://arxiv.org/html/2406.05804v2#A1.T8 "Table 8 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")、[9](https://arxiv.org/html/2406.05804v2#A1.T9 "Table 9 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 和[10](https://arxiv.org/html/2406.05804v2#A1.T10 "Table 10 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")中演示。前两个表格展示了生成触发器的实现，而最后一个表格展示了 ReAct 实现。3) 搜索工作流：在 RAP 工作流的 MCTS 扩展阶段需要一个执行者。提示和预期生成见表格[11](https://arxiv.org/html/2406.05804v2#A1.T11 "Table 11 ‣ Appendix A Frameworks of LLM-Based Agents ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")。

### B.2 LLM 评估者的提示

表[12](https://arxiv.org/html/2406.05804v2#A2.T12 "Table 12 ‣ B.2 Prompts for LLM Evaluators ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")和[13](https://arxiv.org/html/2406.05804v2#A2.T13 "Table 13 ‣ B.2 Prompts for LLM Evaluators ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")显示了被描述为分类任务的 LLM 评估器，而表[15](https://arxiv.org/html/2406.05804v2#A2.T15 "Table 15 ‣ B.2 Prompts for LLM Evaluators ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components")展示了另一种通用自由形式文本。

| 给定一个问题和一些子问题，确定最后一个子问题是否对回答问题有用。输出‘是’或‘否’，并说明原因。 |
| --- |
| 问题 1: 四年前，Kody 的年龄只有穆罕默德的一半。如果穆罕默德现在 30 岁，那么 Kody 几岁？ |
| 问题 1.1: 穆罕默德现在几岁？ |
| 问题 1.2: 四年前穆罕默德几岁？ |
| 新问题 1.3: Kody 四年前几岁？ |
| 新的问题有用吗？是的。我们需要答案来计算 Kody 现在几岁。 |
| … |
| 问题 5: Janet 的鸭子每天下 16 个蛋。她每天早上吃三个，并用四个烘焙蛋糕给朋友。她每天在农贸市场以每个新鲜鸭蛋 2 美元的价格出售剩余的。她每天在农贸市场赚多少钱？ |
| 新问题 5.1: 现在我们可以回答这个问题：她每天在农贸市场赚多少钱？ |
| 新的问题有用吗？ |

表 12: 在 NLIE-QA 下的 RAP 工作流中的 LLM 评估器，通过少-shot CoT 提示实现。它评估新子问题在解决原始问题中的有用性。来源于 Hao 等人（[2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）

| 评估给定的数字是否能达到 24（确定/可能/不可能）10 14

10 + 14 = 24

确定

…

1 3 3

1 * 3 * 3 = 9

(1 + 3) * 3 = 12

1 3 3 都太小了

不可能

11, 12 |

表 13: 在游戏 24 下的 Tree-of-Thought 工作流中的 LLM 评估器，通过少-shot CoT 提示实现。LLM 被描述为多类分类。来源于 Yao 等人（[2023a](https://arxiv.org/html/2406.05804v2#bib.bib29)）。

| 上下文: … 句子: …

句子是否得到上文的支持？

回答是或否: |

表 14: 一个 LLM 评估器，通过零-shot CoT 提示实现。LLM 被描述为多类分类。来源于 Manakul 等人（[2023](https://arxiv.org/html/2406.05804v2#bib.bib13)）。

| … |
| --- |
| 问题: Serianna 是什么类型的乐队，结合了重金属和硬核朋克的元素？ |
| 建议答案：让我们一步步思考。Serianna 是一支金属核风格的乐队。金属核是重金属和硬核朋克的一个子类别。因此，Serianna 是一支重金属和硬核朋克的乐队。所以答案是：重金属和硬核朋克。 |
| 1\. 可能性：<svg class="ltx_picture" height="138.72" id="A2.T15.1.1.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,138.72) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="109.78" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">问题要求找出结合了重金属和硬核朋克元素的风格，而答案是“重金属和硬核朋克”，只是重复了问题。因此，这不太可能。 2\. 真实性：让我们在 Google 上搜索这个问题： > 搜索查询：Serianna 是什么风格的乐队，结合了重金属和硬核朋克元素？ site: wikipedia.org > 证据：</foreignobject></g></g></svg> [金属核 - 维基百科] 金属核是一种融合音乐风格，结合了极端金属和硬核朋克的元素。 |
| <svg class="ltx_picture" height="91.06" id="A2.T15.4.4.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,91.06) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="62.11" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">证据表明，金属核是结合了极端金属和硬核朋克元素的风格，正如建议答案所述。让我们在 Google 上搜索建议答案： > 搜索查询：Serianna 是金属核风格的乐队。 site: wikipedia.org > 证据：</foreignobject></g></g></svg> [Serianna - 维基百科] Serianna 是一支来自威斯康星州麦迪逊的金属核乐队。乐队成立于 2006 年… |
| <svg class="ltx_picture" height="107.66" id="A2.T15.7.7.1.1.p1.pic1" overflow="visible" version="1.1" width="603.94"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,107.66) matrix(1 0 0 -1 0 0) translate(0,3.94)"><g fill-opacity="1.0" transform="matrix(1.0 0.0 0.0 1.0 20.38 12.5)"><foreignobject color="#000000" height="78.72" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="559.25">证据表明 Serianna 是一支金属核乐队，建议答案在这一点上是正确的。总的来说，建议答案准确地识别了 Serianna 是一支金属核风格的乐队，该风格结合了重金属和硬核朋克元素。然而，最终答案不太可能，因为它只是列出了金属核结合的风格。 </foreignobject></g></g></svg> |

表 15: 一个 LLM 评估器在反馈学习工作流（工具）中，实施了少量示例演示。阴影框中的内容由 LLM 生成。为了简洁，我们省略了一些演示。来源于 Gou et al. ([2024](https://arxiv.org/html/2406.05804v2#bib.bib5)).

### B.3 作为动态模型的提示

表 [16](https://arxiv.org/html/2406.05804v2#A2.T16 "Table 16 ‣ B.3 Prompts as Dynamic Models ‣ Appendix B Examples Prompts ‣ A Survey on LLM-Based Agents: Common Workflows and Reusable LLM-Profiled Components") 被配置为动态模型。

| 给定一个问题，请将其分解为子问题。对于每个子问题，请用完整的句子回答，并以“答案是”结束。当原始问题可以回答时，请用“现在我们可以回答这个问题：”开头。 |
| --- |
| 问题 1: Weng 每小时赚 12 美元照看孩子。昨天，她只做了 50 分钟的照看。她赚了多少钱？ |
| 问题 1.1: Weng 每分钟赚多少钱？ |
| 答案 1.1: 由于 Weng 每小时赚 12 美元，她每分钟赚 $12 / 60 = $0.2。答案是 0.2。 |
| 问题 1.2: 现在我们可以回答这个问题：她赚了多少钱？ |
| 答案 1.2: 工作 50 分钟，她赚了 $0.2 x 50 = $10。答案是 10。 |
| … |
| 问题 5: Janet 的鸭子每天产下 16 个蛋。她每天早晨吃三个作为早餐，并且每天用四个蛋给她的朋友们烤松饼。她每天在农贸市场上以每个新鲜鸭蛋 2 美元的价格出售剩余的蛋。她每天在农贸市场上赚多少钱？ |
| 问题 5.1: Janet 在吃掉三个早餐蛋和使用四个做松饼后剩下多少个蛋？ |
| 答案 5.1: |

表 16: 一个 LLM-配置的动态模型。

## 附录 C 创建任务无关的工具环境

以前的工作总是将工具限制在特定应用，如 NLIE-QA，未来的工作应旨在建立一个综合的工具环境，涵盖适用于各种任务的广泛工具。这里的一个主要挑战是如何让一个单一的演员有效利用这样的环境。尽管生成策略的触发器通常仅适用于具有简单参数的基本工具，推理-行动策略可能更有前景。尽管如此，定义工具仍然是一个挑战，尤其是在有效的上下文学习或微调工具使用方面。

## 附录 D 随机 $\text{glm}_{\text{actor}}$

通常，从 glmactor 的输出中采样一个单一的动作。探索一个随机的 glmactor，它提供了一个可能动作的分布，可以增强 glmpolicy 的随机特性并提高效率。这种方法可能包括研究受限生成技术（Willard 和 Louf，[2023](https://arxiv.org/html/2406.05804v2#bib.bib26)）。此外，使用这样的分布可以有效地作为所有可能动作的奖励，可能会在某些工作流中消除单独使用 glmeval 来建模奖励的需要。这种方法允许在一个生成步骤中同时扩展多个潜在节点，而不是在基于搜索的工作流中逐个节点扩展（Hao 等，[2023](https://arxiv.org/html/2406.05804v2#bib.bib7)）。

## 附录 E 记忆

在审查的工作中，记忆的实现通常是简单而任意的。通常，静态信息（例如，分析消息）是手动构建和存储的，而动态信息（例如，反馈）则通过每个工作流中的运行时数据结构进行处理。虽然 Wang 等人（[2024](https://arxiv.org/html/2406.05804v2#bib.bib21)）在之前的调查中详细讨论了混合记忆系统的管理——这需要明确处理和管理短期和长期记忆——但这些记忆管理方面超出了本次调查的重点，本次调查集中在基于 LLM 的工作流上。

生成于 2024 年 6 月 16 日星期日 01:00:18，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
