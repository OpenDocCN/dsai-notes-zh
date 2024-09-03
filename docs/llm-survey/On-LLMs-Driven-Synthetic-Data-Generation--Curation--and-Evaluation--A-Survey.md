<!--yml

类别：未分类

日期：2024-09-03 17:28:44

-->

# 关于基于 LLM 的合成数据生成、整理和评估：调查

> 来源：[`arxiv.org/html/2406.15126`](https://arxiv.org/html/2406.15126)

1.  [1 介绍](https://arxiv.org/html/2406.15126v1#S1 "在 关于基于 LLM 的合成数据生成、整理和评估：调查")

1.  [2 前提](https://arxiv.org/html/2406.15126v1#S2 "在 关于基于 LLM 的合成数据生成、整理和评估：调查")

    1.  [2.1 问题定义](https://arxiv.org/html/2406.15126v1#S2.SS1 "在 2 前提 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

    1.  [2.2 $\mathcal{D}_{\text{gen}}$ 的要求](https://arxiv.org/html/2406.15126v1#S2.SS2 "在 2 前提 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

1.  [3 通用工作流程](https://arxiv.org/html/2406.15126v1#S3 "在 关于基于 LLM 的合成数据生成、整理和评估：调查")

    1.  [3.1 数据生成](https://arxiv.org/html/2406.15126v1#S3.SS1 "在 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

        1.  [3.1.1 提示工程](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS1 "在 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

            1.  [任务规格](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS1.Px1 "在 3.1.1 提示工程 ‣ 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

            1.  [条件提示](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS1.Px2 "在 3.1.1 提示工程 ‣ 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

            1.  [上下文学习](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS1.Px3 "在 3.1.1 提示工程 ‣ 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

        1.  [3.1.2 多步骤生成](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS2 "在 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

            1.  [样本层面的分解](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS2.Px1 "在 3.1.2 多步骤生成 ‣ 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

            1.  [数据集层面的分解](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS2.Px2 "在 3.1.2 多步骤生成 ‣ 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

    1.  [3.2 数据整理](https://arxiv.org/html/2406.15126v1#S3.SS2 "在 3 通用工作流程 ‣ 关于基于 LLM 的合成数据生成、整理和评估：调查")

        1.  [3.2.1 高质量样本过滤](https://arxiv.org/html/2406.15126v1#S3.SS2.SSS1 "在 3.2 数据整理 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [启发式指标](https://arxiv.org/html/2406.15126v1#S3.SS2.SSS1.Px1 "在 3.2.1 高质量样本过滤 ‣ 3.2 数据整理 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [样本重加权](https://arxiv.org/html/2406.15126v1#S3.SS2.SSS1.Px2 "在 3.2.1 高质量样本过滤 ‣ 3.2 数据整理 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

        1.  [3.2.2 标签增强](https://arxiv.org/html/2406.15126v1#S3.SS2.SSS2 "在 3.2 数据整理 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [人工干预](https://arxiv.org/html/2406.15126v1#S3.SS2.SSS2.Px1 "在 3.2.2 标签增强 ‣ 3.2 数据整理 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [辅助模型](https://arxiv.org/html/2406.15126v1#S3.SS2.SSS2.Px2 "在 3.2.2 标签增强 ‣ 3.2 数据整理 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

    1.  [3.3 数据评估](https://arxiv.org/html/2406.15126v1#S3.SS3 "在 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

        1.  [3.3.1 直接评估](https://arxiv.org/html/2406.15126v1#S3.SS3.SSS1 "在 3.3 数据评估 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [数据可信度](https://arxiv.org/html/2406.15126v1#S3.SS3.SSS1.Px1 "在 3.3.1 直接评估 ‣ 3.3 数据评估 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [数据多样性](https://arxiv.org/html/2406.15126v1#S3.SS3.SSS1.Px2 "在 3.3.1 直接评估 ‣ 3.3 数据评估 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

        1.  [3.3.2 间接评估](https://arxiv.org/html/2406.15126v1#S3.SS3.SSS2 "在 3.3 数据评估 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [基准评估](https://arxiv.org/html/2406.15126v1#S3.SS3.SSS2.Px1 "在 3.3.2 间接评估 ‣ 3.3 数据评估 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

            1.  [开放评估](https://arxiv.org/html/2406.15126v1#S3.SS3.SSS2.Px2 "在 3.3.2 间接评估 ‣ 3.3 数据评估 ‣ 3 个通用工作流 ‣ 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

1.  [4 未来方向](https://arxiv.org/html/2406.15126v1#S4 "在 关于基于 LLMs 的合成数据生成、整理和评估：一项调查")

    1.  [4.1 复杂任务分解](https://arxiv.org/html/2406.15126v1#S4.SS1 "在 4 未来方向 ‣ 基于 LLM 的合成数据生成、整理和评估：调查") 

    1.  [4.2 知识增强](https://arxiv.org/html/2406.15126v1#S4.SS2 "在 4 未来方向 ‣ 基于 LLM 的合成数据生成、整理和评估：调查") 

    1.  [4.3 大型与小型语言模型的协同作用](https://arxiv.org/html/2406.15126v1#S4.SS3 "在 4 未来方向 ‣ 基于 LLM 的合成数据生成、整理和评估：调查") 

    1.  [4.4 人类-模型协作](https://arxiv.org/html/2406.15126v1#S4.SS4 "在 4 未来方向 ‣ 基于 LLM 的合成数据生成、整理和评估：调查") 

1.  [5 结论](https://arxiv.org/html/2406.15126v1#S5 "在 基于 LLM 的合成数据生成、整理和评估：调查") 

1.  [A 数据注释](https://arxiv.org/html/2406.15126v1#A1 "在 基于 LLM 的合成数据生成、整理和评估：调查") 

1.  [B 调优技术](https://arxiv.org/html/2406.15126v1#A2 "在 基于 LLM 的合成数据生成、整理和评估：调查") 

1.  [C 应用](https://arxiv.org/html/2406.15126v1#A3 "在 基于 LLM 的合成数据生成、整理和评估：调查") 

    1.  [通用任务](https://arxiv.org/html/2406.15126v1#A3.SS0.SSS0.Px1 "附录 C 应用 ‣ 基于 LLM 的合成数据生成、整理和评估：调查")

    1.  [领域特定任务](https://arxiv.org/html/2406.15126v1#A3.SS0.SSS0.Px2 "附录 C 应用 ‣ 基于 LLM 的合成数据生成、整理和评估：调查") 

    1.  [多模态任务](https://arxiv.org/html/2406.15126v1#A3.SS0.SSS0.Px3 "附录 C 应用 ‣ 基于 LLM 的合成数据生成、整理和评估：调查") 

1.  [D 基准数据集](https://arxiv.org/html/2406.15126v1#A4 "在 基于 LLM 的合成数据生成、整理和评估：调查") 

# 基于 LLM 的合成数据生成、整理， 

和评估：调查 

林龙¹，王瑞¹，肖瑞轩¹ 

赵俊博¹，丁晓²，陈刚¹，王浩博¹ 

¹浙江大学，中国  ²哈尔滨工业大学，中国 

通信作者：wanghaobo@zju.edu.cn 

###### 摘要 

在不断发展的深度学习领域，数据数量和质量的困境一直是一个长期存在的问题。大型语言模型（LLMs）的最新出现提供了一种以数据为中心的解决方案，通过合成数据生成来缓解现实数据的局限性。然而，当前对这一领域的研究缺乏统一的框架，并且大多停留在表面。因此，本文基于合成数据生成的通用工作流程对相关研究进行了组织。通过这样做，我们突出了现有研究中的空白，并概述了未来研究的潜在方向。本文旨在引导学术界和工业界深入、系统地探讨 LLMs 驱动的合成数据生成的能力和应用。

关于 LLMs 驱动的合成数据生成、整理，

和评估：综述

林龙¹，王睿¹，肖瑞轩¹，赵俊博¹，丁晓²，陈刚¹，王浩博¹^†^†感谢：通讯作者。¹浙江大学，中国  ²哈尔滨工业大学，中国 通讯方式：wanghaobo@zju.edu.cn

## 1 引言

大型语言模型（LLMs）的革命性出现引发了深度学习领域的重大范式转变 Zhang et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib108)); Guo et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib25)); Bang et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib3))。尽管取得了这些进展，大量高质量数据仍然是构建稳健 NLP 模型的基础 Gandhi et al. ([2024](https://arxiv.org/html/2406.15126v1#bib.bib19))。更具体地说，这里的高质量数据通常指的是多样化的数据，这些数据包含丰富的监督信号（通常以标签的形式）与人类意图紧密对齐。然而，满足这种对数据的依赖可能会面临挑战，有时甚至是不切实际的，原因包括高成本、数据稀缺、隐私问题等 Kurakin et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib43))。此外，几项研究 Hosking et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib34)); Singh et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib76)); Gilardi et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib23)) 强调了人类生成的数据固有地容易受到偏差和错误的影响，可能并不适合用于模型训练或评估。这些考虑促使我们更深入地探讨一个问题：是否存在其他更有效、更具可扩展性的数据收集方法，以克服当前的局限性？

鉴于最近在 LLMs 方面的进展，它们展示了生成与人类输出相当流畅文本的能力 Hartvigsen et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib28)); Sahu et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib72)); Ye et al. ([2022a](https://arxiv.org/html/2406.15126v1#bib.bib101)); Tang et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib82)); Gao et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib20))，LLMs 生成的合成数据成为了人类生成数据的一个可行替代品或补充。具体而言，合成数据被设计为模仿现实世界数据的特征和模式 Liu et al. ([2024](https://arxiv.org/html/2406.15126v1#bib.bib55))。一方面，LLMs 通过广泛的预训练，获得了丰富的知识库，并展现了卓越的语言理解能力 Kim et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib40)); Ding et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib14))，这为生成真实数据提供了基础。另一方面，LLMs 深厚的指令跟随能力使得生成过程的可控性和适应性更强，能够创建针对特定应用的定制数据集，并具有更灵活的过程设计 Eldan and Li ([2023](https://arxiv.org/html/2406.15126v1#bib.bib16))。这两大优势使得 LLMs 成为极具前景的合成数据生成器。

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：基于 LLMs 的应用生态系统示意图，其中合成数据作为果实的营养源（训练小型 LMs 或针对特定任务的 LLMs 的微调）和根部（训练更强大的 LLMs 或自我改进）。

作为 LLMs 的一个关键应用，合成数据生成对深度学习的发展具有重要意义。如图[1](https://arxiv.org/html/2406.15126v1#S1.F1 "Figure 1 ‣ 1 Introduction ‣ On LLMs-Driven Synthetic Data Generation, Curation, and Evaluation: A Survey")所示，LLMs 驱动的合成数据生成 Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)); Wang et al. ([2021](https://arxiv.org/html/2406.15126v1#bib.bib88)); Seedat et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib73)) 使得整个模型训练和评估过程能够自动化，所需的人工参与极少 Huang et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib36))，这使得深度学习模型的优势能够应用于更广泛的领域。除了提供可扩展的训练和测试数据供应外，LLMs 驱动的合成数据生成还可能为下一代 LLMs 的开发铺平道路。TinyStories Eldan and Li ([2023](https://arxiv.org/html/2406.15126v1#bib.bib16))和 Phi 系列 Gunasekar et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib24)); Li et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib49)) 的研究强调，数据质量对模型学习的有效性至关重要，而 LLMs 使我们能够通过数据操作积极“设计”模型的学习内容，从而显著提升模型训练的效果和可控性。截至 2024 年 6 月，Hugging Face¹¹1https://huggingface.co 上已有超过$300$个数据集被标记为“合成”，许多主流 LLMs 利用高质量合成数据进行训练，包括 Alpaca Taori et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib83))、Vicuna Zheng et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib114))、OpenHermes 2.5 和 Openchat 3.5 Wang et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib86))。

尽管看似简单，生成同时具有高准确性和足够多样性的合成数据集需要精心设计的过程，并涉及许多技巧，Gandhi 等人（[2024](https://arxiv.org/html/2406.15126v1#bib.bib19)）使得基于 LLM 的合成数据生成成为一个非平凡的问题。虽然大多数现有研究通常针对不同任务的数据生成（例如，预训练 Gunasekar 等人（[2023](https://arxiv.org/html/2406.15126v1#bib.bib24)）；Li 等人（[2023b](https://arxiv.org/html/2406.15126v1#bib.bib49)）；Eldan 和 Li（[2023](https://arxiv.org/html/2406.15126v1#bib.bib16)），微调 Mukherjee 等人（[2023](https://arxiv.org/html/2406.15126v1#bib.bib63)）；Mitra 等人（[2023](https://arxiv.org/html/2406.15126v1#bib.bib62)）；Xu 等人（[2023a](https://arxiv.org/html/2406.15126v1#bib.bib99)），评估 Feng 等人（[2023](https://arxiv.org/html/2406.15126v1#bib.bib18)）；Wei 等人（[2024](https://arxiv.org/html/2406.15126v1#bib.bib95)））在不同领域（例如，数学 Yu 等人（[2023a](https://arxiv.org/html/2406.15126v1#bib.bib105)）；Luo 等人（[2023a](https://arxiv.org/html/2406.15126v1#bib.bib57)），代码 Luo 等人（[2023b](https://arxiv.org/html/2406.15126v1#bib.bib58)）；Wei 等人（[2023b](https://arxiv.org/html/2406.15126v1#bib.bib96)），指令 Honovich 等人（[2023a](https://arxiv.org/html/2406.15126v1#bib.bib32)）；Wang 等人（[2023d](https://arxiv.org/html/2406.15126v1#bib.bib90)））存在许多共同的想法。为了解决 LLM 驱动的合成数据生成领域缺乏统一框架的问题，并开发一个通用工作流程，本调查研究了近期的研究，并根据生成、整理和评估这三个密切相关的主题对其进行组织，如图[2](https://arxiv.org/html/2406.15126v1#S2.F2 "图 2 ‣ 2.1 问题定义 ‣ 2 预备知识 ‣ 关于 LLM 驱动的合成数据生成、整理和评估：一项调查")所示。我们的主要目的是提供对该领域现状的全面概述，识别关键关注领域，并突出仍需解决的差距。我们希望为学术界和工业界提供见解，并推动 LLM 驱动的合成数据生成的进一步发展。

## 2 预备知识

### 2.1 问题定义

在本文中，我们研究了使用预训练 LLM（记作$\mathcal{M}$）生成高质量合成数据的挑战。我们并非从头创建新的数据集，而是在更多情况下，利用少量种子样本或未标记输入进行数据增强，我们统称为$\mathcal{D}_{\text{sup}}$。尽管对于 LLM 驱动的合成数据生成来说是可选的，但$\mathcal{D}_{\text{sup}}$通常可以提供有价值的支持信息。因此，整体生成任务可以表述为：

|  | $\mathcal{D}_{\text{gen}}\leftarrow\mathcal{M}_{p}(\mathcal{T},\mathcal{D}_{% \text{sup}})\text{,}$ |  | (1) |
| --- | --- | --- | --- |

其中 $\mathcal{D}_{\text{gen}}$ 表示最终生成的数据集，而 $p$ 指的是用于模型推理的提示。$\mathcal{T}$ 指定了生成任务，如重写、问答、标注等。值得注意的是，数据标注作为合成数据生成的一种专业范式，具有特别广泛的适用性，包括 RLAIF Bai 等人 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib2)) 和基于 LLM 的评估 Chen 等人 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib9)); Zheng 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib114)); Kim 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib39))，这些可能涉及特定的挑战和相应的解决方案。由于篇幅限制，关于数据标注的更多细节可以在附录 [A](https://arxiv.org/html/2406.15126v1#A1 "附录 A 数据标注 ‣ 基于 LLM 的合成数据生成、策划与评估：综述") 中找到。

![参考说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2: 基于 LLM 的合成数据生成、策划和评估的分类。

### 2.2 $\mathcal{D}_{\text{gen}}$ 的要求

简而言之，我们的目标是生成与评估指标紧密对齐的数据。尽管高质量数据的标准可能因下游任务的不同而有所不同，但大多数现有文献中认为有两个通用要求是具有挑战性的：

+   •

    真实性。为了提供有效的监督，生成的数据必须首先在逻辑和语法上连贯。然而，LLM 的幻觉、长尾知识分布等固有问题可能会给生成结果引入显著的噪声，表现为事实错误、标签不正确或内容无关。当生成长篇、复杂或领域特定的数据时，这些问题会更加突出。

+   •

    多样性。多样性捕捉生成数据之间的变化，反映了文本长度、主题或甚至写作风格的差异。它对生成模拟现实世界数据多样性的合成样本至关重要，从而防止模型训练或评估过程中出现过拟合和偏差。然而，由于 LLM 的固有偏差，未受控的生成内容往往趋于单调，限制了其在下游任务中的适用性。

这两个要求是当前大多数研究工作的重点。在随后的工作流程中，我们将介绍不同的方法如何解决这些问题。

![参考说明](img/9df2a699c179d7d103da938773675ba1.png)

图 3: 有效合成数据生成的一个示例。任务规格、条件和上下文演示的相关字段被突出显示，而< >标记了可切换的内容。

## 3 通用工作流程

现有关于 LLM 驱动的合成数据生成的研究通常涵盖三个主要主题：生成、策划和评估。在这些方面中采用各种方法，以协同实现最佳数据生成。

### 3.1 数据生成

在本节中，我们系统地总结了一些使用 LLM 进行合成数据生成的常见实践，这些实践大致可以分为提示工程和多步骤生成。图 [3](https://arxiv.org/html/2406.15126v1#S2.F3 "Figure 3 ‣ 2.2 Requirements of 𝒟_"gen" ‣ 2 Preliminaries ‣ On LLMs-Driven Synthetic Data Generation, Curation, and Evaluation: A Survey") 提供了总体说明。

#### 3.1.1 提示工程

LLM 在合成数据生成中的一个主要优势是其指令跟随能力，这有助于实现很好的可控性 Wang 等人 ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib89))；Radford 等人 ([2019](https://arxiv.org/html/2406.15126v1#bib.bib70))。因此，许多方法尝试通过启发式提示来引导 LLM，从而提高合成数据的真实性和多样性 Liu 等人 ([2024](https://arxiv.org/html/2406.15126v1#bib.bib55))。

实证研究表明，一个有效的提示通常包含三个关键元素：任务规范 $e_{\text{task}}$、生成条件 $e_{\text{condition}}$ 和上下文示例 $e_{\text{demo}}$，然后将这些元素与模板 $E$ 结合成自然语言指令：

|  | $p(\mathcal{T},\mathcal{D})\leftarrow E(e_{\text{task}},e_{\text{condition}},e_{\text{demo}})\text{.}$ |  | (2) |
| --- | --- | --- | --- |

如上所示，生成任务 $\mathcal{T}$ 和支持数据集 $\mathcal{D}$ 都会影响 $p$ 的设计。接下来，我们将详细说明提示的每个部分应如何适当地设计以适应各种场景。

##### 任务规范。

在传统的众包注释场景中，招募的工人通常会提供一本代码手册，说明必要的背景信息，如任务目的、数据解释和其他背景知识，以便他们能更好地理解自己的工作 Gilardi et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib23))。类似地，这种任务规格对于为 LLMs 驱动的数据生成设置正确的背景至关重要，这也可以包括角色扮演 Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50))、格式说明、知识扩充 Xu et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib100))；Sudalairaj et al. ([2024](https://arxiv.org/html/2406.15126v1#bib.bib80)) 等。证据表明，如“假设你是一个 {xxx}”这样的简单前言可以通过为数据生成设置适当的场景，并允许 LLMs 更好地承担角色，显著提高 LLMs 的表现 Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50))。更正式地说，Yoo et al. ([2021](https://arxiv.org/html/2406.15126v1#bib.bib104)) 用文本类型、标签类型和标签-令牌语言化器的三元组定义任务规格。当额外的领域专业知识用于解决术语复杂性等问题时，这种描述头特别重要。结果，Xu et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib100)) 利用外部知识图谱和 LLMs 获取领域主题以进行背景信息提示，从而有效提升生成数据的真实性和复杂性。

##### 条件提示。

如第[2.2](https://arxiv.org/html/2406.15126v1#S2.SS2 "2.2 Requirements of 𝒟_"gen" ‣ 2 Preliminaries ‣ On LLMs-Driven Synthetic Data Generation, Curation, and Evaluation: A Survey")节所述，使用 LLMs 进行合成数据生成的一大关键挑战是确保足够的多样性，因为直接提示 LLMs 生成某些任务的数据通常会导致高度重复的输出，即使在高解码温度下也是如此 Gandhi et al. ([2024](https://arxiv.org/html/2406.15126v1#bib.bib19))；Liu et al. ([2024](https://arxiv.org/html/2406.15126v1#bib.bib55))。解决这个问题的一个广泛采用的策略是条件提示，即明确具体地向 LLMs 传达所需的数据类型。条件提示的核心在于通过一系列条件-值对的制定来划定目标数据：

|  | $e_{\text{condition}}=\{(c_{1},v_{1}),(c_{2},v_{2}),\cdots,(c_{n},v_{n})\}\text% {,}$ |  | (3) |
| --- | --- | --- | --- |

这有效地描述了合成数据所需的属性和特征。通过这些属性的不同组合，我们可以自动实现生成样本中的一种“人工定义”的多样性 Gunasekar et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib24)); Li et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib49)); Eldan and Li ([2023](https://arxiv.org/html/2406.15126v1#bib.bib16))。条件提示不仅可以更好地控制生成数据集的多样性和覆盖范围，还可以将内容精炼到更狭窄、更集中于我们特定期望和需求的范围中 Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50))。当前关于条件提示的研究主要集中在以下两个主题：

+   1)

    条件范围。作为 $e_{\text{condition}}$ 的支柱，条件范围由 $\{c_{1},\cdots,c_{n}\}$ 定义，描绘了我们用来表征目标数据的维度。早期研究 Gao et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib20)); Ye et al. ([2022a](https://arxiv.org/html/2406.15126v1#bib.bib101), [b](https://arxiv.org/html/2406.15126v1#bib.bib102)) 使用了一种基本的输出条件提示策略，将与分类任务相关的具体标签作为条件变量。其背后的主要考虑是保持类别平衡和覆盖。然而，这种策略不适用于缺乏明确类别标签的数据。随后，Yu et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib106)) 的研究认为，使用更细粒度属性的条件提示（例如主题、长度和风格 Xu et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib100))) 由于可能的属性组合数量庞大，能够带来更多的生成多样性，并且也适用于开放式数据。此外，Eldan and Li ([2023](https://arxiv.org/html/2406.15126v1#bib.bib16)) 也将每次生成条件于将三个随机选择的词汇融入生成的故事中。这种方法也被证明显著增强了生成数据的多样性，将焦点从输出的启发式特征转移到通过向提示中添加“创造性随机性”来实现更结构化和有针对性的条件机制 Eldan and Li ([2023](https://arxiv.org/html/2406.15126v1#bib.bib16))。

+   2)

    条件值。在定义了条件范围后，我们需要为每个条件分配具体的值。尽管从已知类别或标签中抽样的策略看似直接，但在某些情况下，可能没有这样的实例池。为解决这个问题，Josifoski 等（[2023](https://arxiv.org/html/2406.15126v1#bib.bib38)）积极从外部知识图谱中检索条件实例，而 Xu 等（[2023b](https://arxiv.org/html/2406.15126v1#bib.bib100)）；Ding 等（[2023b](https://arxiv.org/html/2406.15126v1#bib.bib15)）则利用大型语言模型生成多样化的实例以进行条件提示。具体而言，Ding 等（[2023b](https://arxiv.org/html/2406.15126v1#bib.bib15)）构建了一个概念树，以*深入探讨*不同的子主题，确保样本条件值的覆盖，从而有助于生成更多样化的数据。此外，提示模板 $E$ 也可以被视为一种特殊类型的条件。研究表明，在生成过程中引入具有一定随机性的模板可以增强生成内容的多样性 Meng 等（[2022](https://arxiv.org/html/2406.15126v1#bib.bib60)）。

##### 上下文学习。

由于大型语言模型的固有偏差，仅依靠任务规范和条件提示很难引出理想的响应。在这种情况下，一个简单而有效的策略是提供几个示例，这些示例可以作为一种隐性的人类指导。研究表明，由于大型语言模型卓越的上下文学习（ICL）能力，少量示例可以使其洞察现实数据中展示的模式，从而显著提高生成数据的忠实性 Li 等（[2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)）。在少量样本设置中，当支持集 $\mathcal{D}_{\text{sup}}$ 中有标记样本时，这些样本可以直接用作 ICL 的示例。然而，在没有真实数据的情况下，像 Self-Instruct Wang 等（[2023e](https://arxiv.org/html/2406.15126v1#bib.bib91)）和 Self-Prompting Li 等（[2022](https://arxiv.org/html/2406.15126v1#bib.bib47)）的方法则利用大型语言模型生成的合成示例来进行 ICL。这允许模型在缺乏标记数据的情况下，从自身预测或其他教师模型中学习。

然而，考虑到提示长度和数据不一致的限制，语境样本的质量显著影响语境学习的有效性。Sudalairaj 等人 ([2024](https://arxiv.org/html/2406.15126v1#bib.bib80)) 认为，从种子样本池中随机选择语境示例，如 Self-Instruct Wang 等人 ([2023e](https://arxiv.org/html/2406.15126v1#bib.bib91)) 所做的那样，会导致生成数据缺乏多样性和质量。为解决这个问题，Sudalairaj 等人 ([2024](https://arxiv.org/html/2406.15126v1#bib.bib80)) 选择集中于特定方面的示例，以更好地激发 LLMs 固有的长尾知识。Liu 等人 ([2022b](https://arxiv.org/html/2406.15126v1#bib.bib54)) 和 Su 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib79)) 基于其嵌入空间中的余弦相似性，将一致的样本优先作为示例。另一方面，Ye 等人 ([2022b](https://arxiv.org/html/2406.15126v1#bib.bib102)) 使用量化的影响评分来选择最具信息量的样本，从而引导生成过程。为了增强语境示例的信息量，He 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib29)) 让 LLMs 为每个示例提供解释，然后再将其整合到提示中。这种方法不仅提供了有价值的额外信息，而且与后续的 Chain-of-Thought 生成很好地对齐。

#### 3.1.2 多步骤生成

在前面的段落中，我们介绍了一些常见的提示策略，这些策略通常是为特定的生成任务设计的$\mathcal{T}$。然而，在大多数情况下，由于缺乏足够的推理能力，期望 LLMs 在一次参考中生成整个所需数据集是不切实际的，尤其是当目标是具有复杂结构或语义的数据时 Cui 和 Wang ([2023](https://arxiv.org/html/2406.15126v1#bib.bib12))。为解决这个问题，一种常见策略是多步骤生成，通过这种方式，整体生成过程被手动分解为一系列更简单的子任务$\mathcal{T}_{1:k}$，以迫使 LLMs 按计划逐步生成数据：

|  | $\displaystyle\mathcal{D}_{i}\leftarrow\mathcal{M}^{i}_{p_{i}}(\mathcal{T}_{i},$ | $\displaystyle\mathcal{D}_{0:i-1}),\ i=1,2,\cdots,k\text{,}$ |  | (4) |
| --- | --- | --- | --- | --- |

其中$\mathcal{D}_{0}=\mathcal{D}_{\text{sup}}$。每个中间输出$\mathcal{D}_{i}$是使用模型$\mathcal{M}^{i}$生成的，受到$p_{i}$的提示，用于子任务$\mathcal{T}_{i}$。这些输出随后可以在后续生成中使用。通过手动安排生成过程，我们隐式地将 LLMs 的推理路径与人类的先验知识对齐。具体而言，任务分解有两种常见策略：样本级和数据集级分解，主要旨在提高不同尺度的合成数据质量。

##### 样本级分解。

多步骤生成的典型用例是解决处理长文本和逻辑推理的挑战，特别是在处理对话和实体-关系三元组等多文本数据时。在这种情况下，一种直接的方法是将样本分成较小的块，并一次生成每个样本的一部分 Li et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib47)); Ye et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib103)); Wang et al. ([2023e](https://arxiv.org/html/2406.15126v1#bib.bib91))。这样，$\mathcal{D}_{1:k}$ 可以视为 $\mathcal{D}_{\text{gen}}$ 的不同部分：

|  | $\mathcal{D}_{\text{gen}}=(\mathcal{D}_{1},\mathcal{D}_{2},\cdots,\mathcal{D}_{% k})\text{.}$ |  | (5) |
| --- | --- | --- | --- |

值得注意的是，如公式[4](https://arxiv.org/html/2406.15126v1#S3.E4 "在 3.1.2 多步骤生成 ‣ 3.1 数据生成 ‣ 3 通用工作流程 ‣ 关于基于 LLMs 的合成数据生成、整理和评估的调查")所示，每次生成过程的迭代可以基于之前生成的内容进行条件处理。例如，Ding et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib15)) 促使 LLMs 在充当助手和用户之间交替，根据上下文互相回应，最终生成完整的对话记录。这样，各内部组件 $\mathcal{D}_{i}$ 之间的连贯性可以通过分开的指令得到有效增强，从而使模型更容易遵循要求并生成更真实的数据。需要注意的是，$D_{1:k}$ 不一定是最终 $D_{\text{gen}}$ 的一部分，明确输出一些中间推理步骤也可以改善复杂数据的生成 Bai et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib2)); He et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib29))。链式思维（CoT）提示作为提高 LLM 生成内容真实度的最受欢迎策略之一 Wei et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib94))。然而，当前对这种潜在元数据的探索研究仍然不足，样本级任务分解从推理角度看仍是未来研究中的一个开放问题。

##### 数据集级分解。

在第[3.1.1](https://arxiv.org/html/2406.15126v1#S3.SS1.SSS1.Px2 "条件提示。 ‣ 3.1.1 提示工程 ‣ 3.1 数据生成 ‣ 3 泛用工作流程 ‣ 基于 LLMs 的合成数据生成、整理和评估：综述")节中，我们介绍了如何生成具有特定属性的数据。然而，生成一系列最终可以形成具有良好多样性和领域覆盖的数据集需要长期的安排。为此，数据集级任务分解动态调整多步骤生成中每个阶段使用的条件，以确保整体数据集朝着正确的方向增长：

|  | $\mathcal{D}_{\text{gen}}=\bigcup_{i=1}^{k}\mathcal{D}_{i}\text{.}$ |  | (6) |
| --- | --- | --- | --- |

具体来说，S3 Wang 等人 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib87)) 针对每次迭代中最常被误标记的类别，根据训练在之前生成的数据上的下游模型的表现。类似地，Honovich 等人 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib33))；Shao 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib74)) 使用生成-扩展范式，以相应地增强整体数据集的多样性。其他一些方法还利用特定的数据结构来建模数据生成路径。例如，Explore-Instruct Wan 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib84)) 将领域空间建模为树结构，并在树的遍历过程中不断优化生成的数据，以促进生成数据的专业化和领域覆盖。

### 3.2 数据整理

在前述步骤之后，可能会产生过多且理论上无限的数据 $\mathcal{D}_{\text{gen}}$。然而，这些数据集通常包含大量的噪声、无价值或甚至有害的样本，这主要源于两个原因。首先，LLMs 由于幻觉问题不可避免地会生成带有错误标签的损坏样本。其次，包含模糊描述的无效提示可能会误导模型生成无关或冗余的样本。因此，直接使用这些低质量数据而不经过适当处理，可能会产生显著的负面影响。

为了解决这个问题，已经研究了许多数据整理方法，这些方法主要分为两大类：高质量样本过滤和标签增强，具体如下。

![参见说明](img/ebb17c4cc7cc9df00a33d741a1bf8410.png)

图 4：数据整理的两种主要方法。

#### 3.2.1 高质量样本过滤

样本过滤旨在剔除不需要的低质量样本，并获得一个更有用的子集 $\mathcal{D}_{\text{curated}}\!\subset\!\mathcal{D}_{\text{gen}}$。这些方法通常设计启发式标准或重加权函数来重新排序样本进行过滤，如图[4](https://arxiv.org/html/2406.15126v1#S3.F4 "图 4 ‣ 3.2 数据策划 ‣ 3 通用工作流程 ‣ 基于 LLM 的合成数据生成、策划和评估：综述")所示。

##### 启发式指标。

对于基于启发式指标的方法，关键步骤是根据学习动态设计适当的标准，例如置信度评分（Seedat et al., [2023](https://arxiv.org/html/2406.15126v1#bib.bib73)）、影响函数 Ye et al. ([2022b](https://arxiv.org/html/2406.15126v1#bib.bib102)）和生成能力 Meng et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib60)）。SuperGen Meng et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib60)) 使用估计的生成概率来识别与所需标签最相关的样本。Seedat et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib73)) 丢弃置信度低且不确定性低的样本。一些其他方法假设干净的样本在不同条件下趋向于保持相似的预测，并采用跨条件一致性进行过滤。具体来说，这种一致性可以是 LLM 和下游分类器之间的 Yu et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib107)）、多次执行 Ye et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib103)）或相邻数据点 Seedat et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib73)）之间的。Chen et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib9)) 利用 LLM 强大的文本理解能力来评估不同样本的质量，并过滤出低评分的样本。结果显示，训练于更小但经过精心策划的数据集上的 Alpagasus Chen et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib9)) 在多个基准测试中超越了原始的 Alpaca Taori et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib83))，突显了数据策划的重要性。

##### 样本重加权。

另一方面，重标定方法认为所有数据都是有价值的，但重要性各不相同。因此，它们在下游使用过程中为正确标注或有影响力的样本分配更大的权重 Zhang et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib110))；Gao et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib20))；Meng et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib61))。例如，SunGen Gao et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib20)) 提出了一个无人工标注的自适应双层重标定算法。FewGen Meng et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib61)) 设计了一种判别性元学习目标来调整样本权重并划定不同标签之间的细微差异。

#### 3.2.2 标签增强

标签增强方法旨在纠正生成样本中潜在的错误标注。由于确认偏差，LLMs 不现实地识别自身的错误。为了解决这个问题，最近的工作要么依赖于人工干预，要么结合学生模型进行无人工知识蒸馏。

##### 人工干预。

标签精炼的一种直接策略是包括人为努力重新标注损坏的样本 Chung et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib10))；Wang et al. ([2021](https://arxiv.org/html/2406.15126v1#bib.bib88))；Pangakis et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib66))。Wang et al. ([2021](https://arxiv.org/html/2406.15126v1#bib.bib88)) 提出了主动选择置信度最低的样本进行人工重新标注的方案。Pangakis et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib66)) 和 Liu et al. ([2022a](https://arxiv.org/html/2406.15126v1#bib.bib52)) 进一步强调了人工审查的重要性，并建议对比人类和由相同编码本指导的 LLMs 的标注。尽管方法简单，但这些方法可能会导致相当大的标注成本，并在实际部署中不现实。

##### 辅助模型。

为了降低标注成本，开发了一种更务实的无人工干预范式，该范式涉及用于知识蒸馏和标签精炼的辅助学生模型 Xiao et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib98)); Zhao et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib112)); Saad-Falcon et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib71))。这些方法依赖于学生模型的弱监督能力，并假设从 LLM 教师中蒸馏出的学生可以生成更优的标签。开创性的工作 FreeAL Xiao et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib98)) 提出了一个协作框架，在该框架中，利用学生模型从弱注释中蒸馏出高质量的任务相关知识，并反馈给 LLMs 以进行标签精炼。MCKD Zhao et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib112)) 设计了一个多阶段的蒸馏管道，通过数据拆分训练和交叉分区标注来避免在噪声标签上过拟合。随着 LLMs 能力和可用性的扩展，辅助学生模型的结合将作为一种具有成本效益的替代方案，发挥更重要的作用。

![参考标题](img/1a659a5b01c2ef160b61ce311c78d792.png)

图 5：数据评估的直接和间接方法。

### 3.3 数据评估

在使用生成的数据之前，评估数据的质量和应用效果是非常重要的，以确保其对下游任务的价值。目前主流的评估方法大致可以分为两类：直接和间接，分别通过单独评估 $\mathcal{D}_{\text{gen}}$ 的质量和通过其在下游任务上的效果来进行评估。

#### 3.3.1 直接评估

##### 数据真实性。

理想情况下，如果现有数据集中有实际数据，可以轻松实现对 LLMs 生成结果的自动评估（Zhu et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib115)）。然而，对于开放式数据，需要进行人工评估。一个直接的思路是将一些生成样本提供给人类专家，他们将判断这些样本是否正确，根据这些判断我们可以估计整体生成质量（Wang et al. ([2023e](https://arxiv.org/html/2406.15126v1#bib.bib91)）。理论上，样本量越大，估计结果越准确，但所需的劳动力也会相应增加。为此，可以利用一个可靠的辅助模型来实现更全面且成本效益更高的生成数据评估，替代人工专家（Chung et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib11)）。考虑到大多数模型只能处理有限长度的内容，适当的信息提取可以减轻辅助模型的负担，并有助于更精确地预测样本是否包含事实错误（Lee et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib45)）。

##### 数据多样性。

数据多样性的量化主要采用词汇统计和样本相关性计算（Yu et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib106)），例如词汇大小和 N-gram 频率，提供了一种直接且直观的方法。然而，它们难以捕捉数据集的语义信息。样本相关性的计算有效地弥补了这一限制。最常见的样本相关性度量基于余弦相似度（Wang et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib87)）和样本距离（Chung et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib11)），可以更好地捕捉数据集的上下文和语义多样性。此外，这些度量还可以用于选择与之前生成样本差异较大的上下文演示$e_{\text{demo}}$（Wang et al. ([2023e](https://arxiv.org/html/2406.15126v1#bib.bib91)），从而产生更多样化的生成结果。

#### 3.3.2 间接评估

##### 基准评估。

在生成数据上训练的下游模型的性能在一定程度上也能反映生成质量 Yu et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib106)); Chung et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib11))。具体而言，除了下游模型的专业能力外，合成数据的影响可以从多个维度进行评估。例如，TruthfulQA 使得评估模型识别真实声明的能力成为可能 Sun et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib81)); NIV2 用于评估模型在多个任务上的语言理解和推理能力 Wang et al. ([2023e](https://arxiv.org/html/2406.15126v1#bib.bib91))。

##### 开放评价。

对于开放性基准测试，由于缺乏标准答案，需要由人工或辅助模型进行评估。为了充分利用辅助模型的偏好输出，设计了多种评估策略，如响应排序 Xu et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib99))、四级评分系统 Wang et al. ([2023e](https://arxiv.org/html/2406.15126v1#bib.bib91)) 和 Elo 分数 Bai et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib2))。为了进一步降低评估成本，Sun et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib81)); Xu et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib99)) 利用 Vicuna 提出的基于 GPT-4 的自动评估框架进行评估。然而，通用 LLM 可能缺乏足够的领域知识，这使得它们难以提供有效的评估 Bran et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib6))。因此，收集人工评估数据以微调开源模型用于评估目的在实际场景中是一种重要实践 He et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib29))。像 Peng et al. ([2024](https://arxiv.org/html/2406.15126v1#bib.bib68), [2023](https://arxiv.org/html/2406.15126v1#bib.bib67)) 的其他技术仍需进一步探索。

## 4 未来方向

### 4.1 复杂任务分解

目前的多步骤生成算法依赖于模型对任务需求的理解，需要它在有限的信息下进行复杂的逻辑推理。然而，在现实世界的复杂场景中，这些有限的信息可能不足以支持有效的决策。例如，数学问题解决对的生成涉及多个推理步骤，并可能需要使用计算器工具进行验证。迄今为止，仍然缺乏系统性的研究来激活 LLMs 的推理和规划能力，以实现自主合成数据的生成。受到如 HuggingGPT Shen 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib75)) 和 MetaGPT Hong 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib31)) 等流行 LLMs 基础代理的启发，我们认为开发一个用于工业应用的数据生成代理也是相当有价值的。

### 4.2 知识增强

最近的研究发现，LLMs 的知识呈现长尾分布且存在偏差 Navigli 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib64)); Fei 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib17))。由于缺乏特定领域的知识，LLMs 往往生成带有偏见、单调甚至不真实的数据。尽管我们在前面的章节中介绍了如何通过任务规范和条件提示来轻微引导数据生成，但这些方法仍然存在较大的局限性，不利于大规模实施。相反，我们认为在成熟的领域知识库上直接开发自动条件控制，将显著提高知识增强的效率。例如，我们可以在 LLMs 与外部知识图谱之间建立某些链接 Ji 等人 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib37)) 或从网站中检索增强信息 Gao 等人 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib22))，这对于整个生成过程中的数据特征定义、分解和推理是有帮助的。此外，借助增强的领域知识，我们还可以更好地评估生成数据的质量，甚至开发自动评估系统。总体而言，我们认为知识驱动的数据生成将成为未来研究的一个重点。

### 4.3 大型与小型语言模型的协同作用

在第[3.2](https://arxiv.org/html/2406.15126v1#S3.SS2 "3.2 数据整理 ‣ 3 通用工作流程 ‣ 基于 LLMs 的合成数据生成、整理和评估：一项调查")节中，我们介绍了使用小型领域特定模型进行数据整理。特别是，FreeAL Xiao 等人（[2023](https://arxiv.org/html/2406.15126v1#bib.bib98)）已经展示了通过大型和小型模型之间的集成协作实现低成本数据整理的可行性。利用数据生成过程中由自动性能评估提供的实时反馈来引导后续调整的想法，提示了一个重要的研究方向。然而，当前阶段对小 LM 的利用仅仅基于预测置信度。未来，我们期待看到更多大型和小型模型之间多样化合作模式的出现，以提高生成数据的质量，例如使用各种输出信息、新的协作架构设计等。

### 4.4 人机协作

数据作为模型智能的源泉，在理论上无法完全在没有人为干预的情况下生成。否则，携带有嘈杂、有毒信息的野生合成数据很容易“毒害”模型，甚至导致模式崩溃。由于 LLM 的固有偏见，它们很难自我意识到生成数据中的偏见，最终会偏离我们的意图。因此，设计一个人性化互动系统，需要一些必要的人类知识来进行注释和验证，这是至关重要且不可替代的。迄今为止，仍然缺乏一个通用框架来标准化和系统化涉及数据生产过程中的人机协作。

我们认为，这样一个系统的合适设计必须基于对人类干预的优势和局限性的深入理解，并遵循以人为中心的原则。为了实现可持续和高效的人类参与，我们需要全面考虑各种因素，如可行性、成本，甚至劳动心理。具体例子包括：（i）-确保 LLMs 提供的信息的可读性和可解释性，以减少人类理解障碍；（ii）-进行上游知识丰富化或过滤，以提高人力资源利用效率，减少低成本效益任务消耗；（iii）-融入有趣的互动功能不仅可以缓解机械数据处理任务对人类的负面影响，还能吸引更广泛的受众。

## 5 结论

在本文中，我们系统回顾了由大型语言模型（LLMs）推动的合成数据生成的进展。我们的目标是为企业和组织在使用 LLMs 有效构建其特定领域的数据集提供指导。与此同时，我们努力提供对该领域挑战和机遇的见解，并提出未来研究的潜在方向。我们希望我们的工作能够促进各领域大量数据的快速生成，并推动数据驱动的人工智能的极限。我们还设想一个美好的未来，即构建一个具有人类类似能力（如仿生学和通信）的 LLMs 社区，以生成数据用于自身改进。

## 限制

在本文中，我们调查了现有的基于 LLMs 的合成数据生成、策划和评估的研究，并提出了一个适用于现实世界的通用工作流程。合成数据生成是一个广泛的主题，涉及各种模态的数据和模型，包括视觉和语音。由于篇幅限制，我们主要关注文本数据和 LLMs 驱动的方法，将其他领域的研究留待未来工作。我们还将持续关注最新研究，并增加更多相关方法及更详细的分析。

## 伦理声明

我们相信，我们提出的基于 LLMs 的合成数据生成、策划和评估工作流程可以惠及对数据驱动的人工智能感兴趣的研究人员以及面临数据问题的工业生产者。然而，合成数据的恶意使用也引发了伦理问题，需要引起我们的警惕。

## 致谢

本研究得到了浙江省先锋研发计划（编号：2024C01035）、国家自然科学基金（编号：62206247）和中央高校基础研究基金（编号：226-2024-00049）的支持。

## 参考文献

+   Almeida et al. (2011) Tiago A. Almeida, José María Gómez Hidalgo, and Akebo Yamakami. 2011. Contributions to the study of SMS spam filtering: new collection and results. In *Proceedings of the 2011 ACM Symposium on Document Engineering, Mountain View, CA, USA, September 19-22, 2011*.

+   Bai 等人 (2022) Yuntao Bai, Saurav Kadavath, Sandipan Kundu, Amanda Askell, Jackson Kernion, Andy Jones, Anna Chen, Anna Goldie, Azalia Mirhoseini, Cameron McKinnon, Carol Chen, Catherine Olsson, Christopher Olah, Danny Hernandez, Dawn Drain, Deep Ganguli, Dustin Li, Eli Tran-Johnson, Ethan Perez, Jamie Kerr, Jared Mueller, Jeffrey Ladish, Joshua Landau, Kamal Ndousse, Kamile Lukosiute, Liane Lovitt, Michael Sellitto, Nelson Elhage, Nicholas Schiefer, Noemí Mercado, Nova DasSarma, Robert Lasenby, Robin Larson, Sam Ringer, Scott Johnston, Shauna Kravec, Sheer El Showk, Stanislav Fort, Tamera Lanham, Timothy Telleen-Lawton, Tom Conerly, Tom Henighan, Tristan Hume, Samuel R. Bowman, Zac Hatfield-Dodds, Ben Mann, Dario Amodei, Nicholas Joseph, Sam McCandlish, Tom Brown, 和 Jared Kaplan. 2022. 宪法 AI：来自 AI 反馈的无害性. *CoRR*，abs/2212.08073。

+   Bang 等人 (2023) Yejin Bang, Samuel Cahyawijaya, Nayeon Lee, Wenliang Dai, Dan Su, Bryan Wilie, Holy Lovenia, Ziwei Ji, Tiezheng Yu, Willy Chung, Quyet V. Do, Yan Xu, 和 Pascale Fung. 2023. 对 ChatGPT 在推理、幻觉和互动性方面的多任务、多语言、多模态评估. *CoRR*，abs/2302.04023。

+   Bansal 和 Sharma (2023) Parikshit Bansal 和 Amit Sharma. 2023. 大型语言模型作为注释者：以最低成本增强 NLP 模型的泛化能力. *CoRR*，abs/2306.15766。

+   Bartolo 等人 (2020) Max Bartolo, Alastair Roberts, Johannes Welbl, Sebastian Riedel, 和 Pontus Stenetorp. 2020. [击败 AI：调查用于阅读理解的对抗性人工注释](https://doi.org/10.1162/tacl_a_00338). *计算语言学协会交易*，8:662–678。

+   Bran 等人 (2023) Andres M Bran, Sam Cox, Andrew D White, 和 Philippe Schwaller. 2023. Chemcrow: 用化学工具增强大型语言模型. *arXiv 预印本 arXiv:2304.05376*。

+   Casanueva 等人 (2020) Iñigo Casanueva, Tadas Temčinas, Daniela Gerz, Matthew Henderson, 和 Ivan Vulić. 2020. [使用双句子编码器的高效意图检测](https://doi.org/10.18653/v1/2020.nlp4convai-1.5). 发表在 *第 2 届自然语言处理与对话 AI 研讨会论文集*，第 38–45 页，在线。计算语言学协会。

+   陈等人 (2023a) Derek Chen, Celine Lee, Yunan Lu, Domenic Rosati, 和 Zhou Yu. 2023a. 可控数据生成的软提示混合. 发表在 *EMNLP* 上，第 14815–14833 页。计算语言学协会。

+   陈等人 (2023b) Lichang Chen, Shiyang Li, Jun Yan, Hai Wang, Kalpa Gunaratna, Vikas Yadav, Zheng Tang, Vijay Srinivasan, Tianyi Zhou, Heng Huang, 和 Hongxia Jin. 2023b. Alpagasus: 用更少的数据训练更好的 alpaca. *CoRR*，abs/2307.08701。

+   Chung 等 (2023a) John Chung, Ece Kamar, 和 Saleema Amershi. 2023a. [在保持准确性的同时增加多样性：利用大型语言模型和人工干预生成文本数据](https://doi.org/10.18653/v1/2023.acl-long.34)。在 *第 61 届计算语言学协会年会（第 1 卷：长篇论文）*，页码 575–593，多伦多，加拿大。计算语言学协会。

+   Chung 等 (2023b) John Joon Young Chung, Ece Kamar, 和 Saleema Amershi. 2023b. 在保持准确性的同时增加多样性：利用大型语言模型和人工干预生成文本数据。在 *ACL*，页码 575–593。计算语言学协会。

+   Cui 和 Wang (2023) Wanyun Cui 和 Qianle Wang. 2023. Ada-instruct: 为复杂推理适应指令生成器。*CoRR*，abs/2310.04484。

+   Demszky 等 (2020) Dorottya Demszky, Dana Movshovitz-Attias, Jeongwoo Ko, Alan Cowen, Gaurav Nemade, 和 Sujith Ravi. 2020. [GoEmotions: 一个细粒度情感数据集](https://doi.org/10.18653/v1/2020.acl-main.372)。在 *第 58 届计算语言学协会年会论文集*，页码 4040–4054，在线。计算语言学协会。

+   Ding 等 (2023a) Bosheng Ding, Chengwei Qin, Linlin Liu, Yew Ken Chia, Boyang Li, Shafiq Joty, 和 Lidong Bing. 2023a. [GPT-3 是否是一个好的数据标注员？](https://doi.org/10.18653/v1/2023.acl-long.626) 在 *第 61 届计算语言学协会年会（第 1 卷：长篇论文）*，页码 11173–11195，多伦多，加拿大。计算语言学协会。

+   Ding 等 (2023b) Ning Ding, Yulin Chen, Bokai Xu, Yujia Qin, Shengding Hu, Zhiyuan Liu, Maosong Sun, 和 Bowen Zhou. 2023b. [通过扩展高质量的指令对话来增强聊天语言模型](https://doi.org/10.18653/v1/2023.emnlp-main.183)。在 *2023 年自然语言处理领域实证方法会议论文集*，页码 3029–3051，新加坡。计算语言学协会。

+   Eldan 和 Li (2023) Ronen Eldan 和 Yuanzhi Li. 2023. Tinystories: 语言模型可以小到什么程度还能说出连贯的英语？*CoRR*，abs/2305.07759。

+   Fei 等 (2023) Yu Fei, Yifan Hou, Zeming Chen, 和 Antoine Bosselut. 2023. 减轻上下文学习中的标签偏差。 在 *ACL*，页码 14014–14031。计算语言学协会。

+   Feng 等 (2023) Shangbin Feng, Vidhisha Balachandran, Yuyang Bai, 和 Yulia Tsvetkov. 2023. [FactKB: 使用增强了事实知识的语言模型进行可泛化的事实性评估](https://doi.org/10.18653/v1/2023.emnlp-main.59)。在 *2023 年自然语言处理领域实证方法会议论文集*，页码 933–952，新加坡。计算语言学协会。

+   Gandhi 等人（2024）Saumya Gandhi, Ritu Gala, Vijay Viswanathan, Tongshuang Wu, 和 Graham Neubig。2024。通过检索和转化现有数据集来生成更好的合成数据。*CoRR*，abs/2404.14361。

+   Gao 等人（2023a）Jiahui Gao, Renjie Pi, Yong Lin, Hang Xu, Jiacheng Ye, Zhiyong Wu, Weizhong Zhang, Xiaodan Liang, Zhenguo Li, 和 Lingpeng Kong。2023a。自导噪声自由数据生成以实现高效零-shot 学习。在 *ICLR*。OpenReview.net。

+   Gao 等人（2019）Tianyu Gao, Xu Han, Hao Zhu, Zhiyuan Liu, Peng Li, Maosong Sun, 和 Jie Zhou。2019。 [FewRel 2.0: Towards more challenging few-shot relation classification](https://doi.org/10.18653/v1/D19-1649)。在 *2019 年自然语言处理实证方法会议暨第 9 届国际自然语言处理联合会议（EMNLP-IJCNLP）* 论文集，页面 6250–6255，香港，中国。计算语言学协会。

+   Gao 等人（2023b）Yunfan Gao, Yun Xiong, Xinyu Gao, Kangxiang Jia, Jinliu Pan, Yuxi Bi, Yi Dai, Jiawei Sun, Qianyu Guo, Meng Wang, 和 Haofen Wang。2023b。增强检索生成的语言模型：一项调查。*CoRR*，abs/2312.10997。

+   Gilardi 等人（2023）Fabrizio Gilardi, Meysam Alizadeh, 和 Maël Kubli。2023。ChatGPT 在文本注释任务中优于众包工人。*CoRR*，abs/2303.15056。

+   Gunasekar 等人（2023）Suriya Gunasekar, Yi Zhang, Jyoti Aneja, Caio César Teodoro Mendes, Allie Del Giorno, Sivakanth Gopi, Mojan Javaheripi, Piero Kauffmann, Gustavo de Rosa, Olli Saarikivi, Adil Salim, Shital Shah, Harkirat Singh Behl, Xin Wang, Sébastien Bubeck, Ronen Eldan, Adam Tauman Kalai, Yin Tat Lee, 和 Yuanzhi Li。2023。教科书就是你所需的全部。*CoRR*，abs/2306.11644。

+   Guo 等人（2023）Biyang Guo, Xin Zhang, Ziyuan Wang, Minqi Jiang, Jinran Nie, Yuxuan Ding, Jianwei Yue, 和 Yupeng Wu。2023。ChatGPT 与人类专家的接近程度如何？对比语料库、评估和检测。*CoRR*，abs/2301.07597。

+   Han 和 Gardent（2023）Kelvin Han 和 Claire Gardent。2023。 [Multilingual generation and answering of questions from texts and knowledge graphs](https://doi.org/10.18653/v1/2023.findings-emnlp.918)。在 *计算语言学协会会议论文集：EMNLP 2023*，页面 13740–13756，新加坡。计算语言学协会。

+   Han 等人（2023）Yucheng Han, Chi Zhang, Xin Chen, Xu Yang, Zhibin Wang, Gang Yu, Bin Fu, 和 Hanwang Zhang。2023。Chartllama: 一种用于图表理解和生成的多模态 LLM。*CoRR*，abs/2311.16483。

+   Hartvigsen 等人（2022）Thomas Hartvigsen, Saadia Gabriel, Hamid Palangi, Maarten Sap, Dipankar Ray, 和 Ece Kamar。2022。 [ToxiGen: A large-scale machine-generated dataset for adversarial and implicit hate speech detection](https://doi.org/10.18653/v1/2022.acl-long.234)。在 *计算语言学协会第 60 届年会论文集（第 1 卷：长篇论文）*，页面 3309–3326，都柏林，爱尔兰。计算语言学协会。

+   He 等（2023）Xingwei He、Zhenghao Lin、Yeyun Gong、A-Long Jin、Hang Zhang、Chen Lin、Jian Jiao、Siu Ming Yiu、Nan Duan 和 Weizhu Chen。2023。Annollm: 使大型语言模型成为更好的众包注释员。*CoRR*，abs/2303.16854。

+   Hendrycks 等（2021）Dan Hendrycks、Collin Burns、Saurav Kadavath、Akul Arora、Steven Basart、Eric Tang、Dawn Song 和 Jacob Steinhardt。2021。使用 MATH 数据集测量数学问题解决能力。发表于 *Proc. of NeurIPS*。

+   Hong 等（2023）Sirui Hong、Xiawu Zheng、Jonathan Chen、Yuheng Cheng、Jinlin Wang、Ceyao Zhang、Zili Wang、Steven Ka Shing Yau、Zijuan Lin、Liyang Zhou、Chenyu Ran、Lingfeng Xiao 和 Chenglin Wu。2023。Metagpt: 多智能体协作框架的元编程。*CoRR*，abs/2308.00352。

+   Honovich 等（2023a）Or Honovich、Thomas Scialom、Omer Levy 和 Timo Schick。2023a。[不自然的指令：用（几乎）无需人工劳动的方式调整语言模型](https://doi.org/10.18653/v1/2023.acl-long.806)。发表于 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，页码 14409–14428， 加拿大多伦多。计算语言学协会。

+   Honovich 等（2023b）Or Honovich、Thomas Scialom、Omer Levy 和 Timo Schick。2023b。不自然的指令：用（几乎）无需人工劳动的方式调整语言模型。发表于 *ACL*，页码 14409–14428。计算语言学协会。

+   Hosking 等（2023）Tom Hosking、Phil Blunsom 和 Max Bartolo。2023。人工反馈不是金标准。*CoRR*，abs/2309.16349。

+   Hu 等（2023）Zhiqiang Hu、Lei Wang、Yihuai Lan、Wanyu Xu、Ee-Peng Lim、Lidong Bing、Xing Xu、Soujanya Poria 和 Roy Lee。2023。[LLM-adapters: 用于参数高效微调的大型语言模型适配器家族](https://doi.org/10.18653/v1/2023.emnlp-main.319)。发表于 *2023 年自然语言处理实证方法会议论文集*，页码 5254–5276，新加坡。计算语言学协会。

+   Huang 等（2023）Jiaxin Huang、Shixiang Gu、Le Hou、Yuexin Wu、Xuezhi Wang、Hongkun Yu 和 Jiawei Han。2023。大型语言模型可以自我改进。发表于 *EMNLP*，页码 1051–1068。计算语言学协会。

+   Ji 等（2022）Shaoxiong Ji、Shirui Pan、Erik Cambria、Pekka Marttinen 和 Philip S. Yu。2022。关于知识图谱的调查：表示、获取和应用。*IEEE Trans. Neural Networks Learn. Syst.*，33(2)：494–514。

+   Josifoski 等（2023）Martin Josifoski、Marija Sakota、Maxime Peyrard 和 Robert West。2023。利用不对称性生成合成训练数据：Synthie 和信息提取案例。发表于 *EMNLP*，页码 1555–1574。计算语言学协会。

+   Kim 等人（2023）**Seungone Kim**、**Jamin Shin**、**Yejin Cho**、**Joel Jang**、**Shayne Longpre**、**Hwaran Lee**、**Sangdoo Yun**、**Seongjin Shin**、**Sungdong Kim**、**James Thorne** 和 **Minjoon Seo**。2023。Prometheus: Inducing fine-grained evaluation capability in language models。*CoRR*，abs/2310.08491。

+   Kim 等人（2022）**Su Young Kim**、**Hyeon-Jin Park**、**Kyuyong Shin** 和 **Kyung-Min Kim**。2022。Ask me what you need: Product retrieval using knowledge from GPT-3。*CoRR*，abs/2207.02516。

+   Kocon 等人（2023）**Jan Kocon**、**Igor Cichecki**、**Oliwier Kaszyca**、**Mateusz Kochanek**、**Dominika Szydlo**、**Joanna Baran**、**Julita Bielaniewicz**、**Marcin Gruza**、**Arkadiusz Janz**、**Kamil Kanclerz**、**Anna Kocon**、**Bartlomiej Koptyra**、**Wiktoria Mieleszczenko-Kowszewicz**、**Piotr Milkowski**、**Marcin Oleksy**、**Maciej Piasecki**、**Lukasz Radlinski**、**Konrad Wojtasik**、**Stanislaw Wozniak** 和 **Przemyslaw Kazienko**。2023。Chatgpt: Jack of all trades, master of none。*Inf. Fusion*，99:101861。

+   Kritharoula 等人（2023）**Anastasia Kritharoula**、**Maria Lymperaiou** 和 **Giorgos Stamou**。2023。[Large language models and multimodal retrieval for visual word sense disambiguation](https://doi.org/10.18653/v1/2023.emnlp-main.807)。在 *2023 年自然语言处理实证方法会议论文集*，第 13053–13077 页，新加坡。计算语言学协会。

+   Kurakin 等人（2023）**Alexey Kurakin**、**Natalia Ponomareva**、**Umar Syed**、**Liam MacDermed** 和 **Andreas Terzis**。2023。Harnessing large-language models to generate private synthetic text。*arXiv preprint arXiv:2306.01684*。

+   Larson 等人（2019）**Stefan Larson**、**Anish Mahendran**、**Joseph J. Peper**、**Christopher Clarke**、**Andrew Lee**、**Parker Hill**、**Jonathan K. Kummerfeld**、**Kevin Leach**、**Michael A. Laurenzano**、**Lingjia Tang** 和 **Jason Mars**。2019。An evaluation dataset for intent classification and out-of-scope prediction。在 *EMNLP 会议论文集*。

+   Lee 等人（2022）**Nayeon Lee**、**Wei Ping**、**Peng Xu**、**Mostofa Patwary**、**Pascale N Fung**、**Mohammad Shoeybi** 和 **Bryan Catanzaro**。2022。Factuality enhanced language models for open-ended text generation。*NeurIPS*。

+   Li 和 Callison-Burch（2023）**Bryan Li** 和 **Chris Callison-Burch**。2023。[PAXQA: Generating cross-lingual question answering examples at training scale](https://doi.org/10.18653/v1/2023.findings-emnlp.32)。在 *计算语言学协会：EMNLP 2023 的发现*，第 439–454 页，新加坡。计算语言学协会。

+   Li 等人（2022）**Junlong Li**、**Zhuosheng Zhang** 和 **Hai Zhao**。2022。Self-prompting large language models for open-domain QA。*CoRR*，abs/2212.08635。

+   Li 等人（2023a）**Minzhi Li**、**Taiwei Shi**、**Caleb Ziems**、**Min-Yen Kan**、**Nancy Chen**、**Zhengyuan Liu** 和 **Diyi Yang**。2023a。[CoAnnotating: Uncertainty-guided work allocation between human and large language models for data annotation](https://doi.org/10.18653/v1/2023.emnlp-main.92)。在 *2023 年自然语言处理实证方法会议论文集*，第 1487–1505 页，新加坡。计算语言学协会。

+   Li 等（2023b）Yuanzhi Li、Sébastien Bubeck、Ronen Eldan、Allie Del Giorno、Suriya Gunasekar 和 Yin Tat Lee。2023b。教科书是你所需的一切 II：phi-1.5 技术报告。*CoRR*，abs/2309.05463。

+   Li 等（2023c）Zhuoyan Li、Hangxiao Zhu、Zhuoran Lu 和 Ming Yin。2023c。利用大语言模型生成用于文本分类的合成数据：潜力与局限。于 *EMNLP*，第 10443–10461 页。计算语言学协会。

+   Lin 等（2022）Stephanie Lin、Jacob Hilton 和 Owain Evans。2022。[TruthfulQA: 测量模型如何模仿人类虚假信息](https://doi.org/10.18653/v1/2022.acl-long.229)。在 *第 60 届计算语言学协会年会（第 1 卷：长篇论文）*，第 3214–3252 页，爱尔兰都柏林。计算语言学协会。

+   Liu 等（2022a）Alisa Liu、Swabha Swayamdipta、Noah A. Smith 和 Yejin Choi。2022a。[WANLI: 工人和 AI 协作的自然语言推理数据集创建](https://doi.org/10.18653/v1/2022.findings-emnlp.508)。在 *计算语言学协会发现：EMNLP 2022*，第 6826–6847 页，阿布扎比，阿联酋。计算语言学协会。

+   Liu 等（2023）Haotian Liu、Chunyuan Li、Yuheng Li 和 Yong Jae Lee。2023。改进的基线与视觉指令调优。*CoRR*，abs/2310.03744。

+   Liu 等（2022b）Jiachang Liu、Dinghan Shen、Yizhe Zhang、Bill Dolan、Lawrence Carin 和 Weizhu Chen。2022b。什么样的上下文示例对 GPT-3 有效？于 *DeeLIO@ACL*，第 100–114 页。计算语言学协会。

+   Liu 等（2024）Ruibo Liu、Jerry Wei、Fangyu Liu、Chenglei Si、Yanzhe Zhang、Jinmeng Rao、Steven Zheng、Daiyi Peng、Diyi Yang、Denny Zhou 和 Andrew M. Dai。2024。关于语言模型的合成数据的最佳实践和经验教训。*CoRR*，abs/2404.07503。

+   Lu 等（2023）Yuzhe Lu、Sungmin Hong、Yash Shah 和 Panpan Xu。2023。有效微调以提升大型多模态模型在放射科报告生成中的表现。*CoRR*，abs/2312.01504。

+   Luo 等（2023a）Haipeng Luo、Qingfeng Sun、Can Xu、Pu Zhao、Jianguang Lou、Chongyang Tao、Xiubo Geng、Qingwei Lin、Shifeng Chen 和 Dongmei Zhang。2023a。Wizardmath：通过强化演化指令增强大语言模型的数学推理能力。*CoRR*，abs/2308.09583。

+   Luo 等（2023b）Ziyang Luo、Can Xu、Pu Zhao、Qingfeng Sun、Xiubo Geng、Wenxiang Hu、Chongyang Tao、Jing Ma、Qingwei Lin 和 Daxin Jiang。2023b。Wizardcoder：通过演化指令增强代码大语言模型。*CoRR*，abs/2306.08568。

+   Maas 等（2011）Andrew L. Maas、Raymond E. Daly、Peter T. Pham、Dan Huang、Andrew Y. Ng 和 Christopher Potts。2011。[用于情感分析的词向量学习](https://aclanthology.org/P11-1015)。在 *第 49 届计算语言学协会年会：人类语言技术*，第 142–150 页，美国俄勒冈州波特兰。计算语言学协会。

+   Meng et al. (2022) Yu Meng, Jiaxin Huang, Yu Zhang, 和 Jiawei Han. 2022. 使用语言模型生成训练数据：迈向零样本语言理解。 在 *NeurIPS*。

+   Meng et al. (2023) Yu Meng, Martin Michalski, Jiaxin Huang, Yu Zhang, Tarek Abdelzaher, 和 Jiawei Han. 2023. 将语言模型调优为训练数据生成器以增强少样本学习。 在 *ICML*，页面 24457–24477。PMLR。

+   Mitra et al. (2023) Arindam Mitra, Luciano Del Corro, Shweti Mahajan, Andrés Codas, Clarisse Simões, Sahaj Agrawal, Xuxi Chen, Anastasia Razdaibiedina, Erik Jones, Kriti Aggarwal, Hamid Palangi, Guoqing Zheng, Corby Rosset, Hamed Khanpour, 和 Ahmed Awadallah. 2023. Orca 2: 教授小型语言模型如何推理。*CoRR*，abs/2311.11045。

+   Mukherjee et al. (2023) Subhabrata Mukherjee, Arindam Mitra, Ganesh Jawahar, Sahaj Agarwal, Hamid Palangi, 和 Ahmed Awadallah. 2023. Orca: 从 GPT-4 的复杂解释轨迹中逐步学习。*CoRR*，abs/2306.02707。

+   Navigli et al. (2023) Roberto Navigli, Simone Conia, 和 Björn Ross. 2023. 大型语言模型中的偏见：起源、清单和讨论。*ACM J. Data Inf. Qual.*，15(2):10:1–10:21。

+   Oh et al. (2023) Seokjin Oh, Su Ah Lee, 和 Woohwan Jung. 2023. 使用生成语言模型的数据增强用于神经机器翻译。*CoRR*，abs/2307.16833。

+   Pangakis et al. (2023) Nicholas Pangakis, Samuel Wolken, 和 Neil Fasching. 2023. 生成 AI 的自动注释需要验证。*CoRR*，abs/2306.00176。

+   Peng et al. (2023) Ru Peng, Qiuyang Duan, Haobo Wang, Jiachen Ma, Yanbo Jiang, Yongjun Tu, Xiu Jiang, 和 Junbo Zhao. 2023. Came: 对比自动模型评估。 在 *IEEE/CVF 国际计算机视觉会议论文集* 中，页面 20121–20132。

+   Peng et al. (2024) Ru Peng, Heming Zou, Haobo Wang, Yawen Zeng, Zenan Huang, 和 Junbo Zhao. 2024. 基于能量的自动模型评估。*arXiv 预印本 arXiv:2401.12689*。

+   Qin et al. (2023) Yujia Qin, Shihao Liang, Yining Ye, Kunlun Zhu, Lan Yan, Yaxi Lu, Yankai Lin, Xin Cong, Xiangru Tang, Bill Qian, Sihan Zhao, Runchu Tian, Ruobing Xie, Jie Zhou, Mark Gerstein, Dahai Li, Zhiyuan Liu, 和 Maosong Sun. 2023. Toolllm: 使大型语言模型掌握 16000+ 现实世界 API。*CoRR*。

+   Radford et al. (2019) Alec Radford, Jeff Wu, Rewon Child, David Luan, Dario Amodei, 和 Ilya Sutskever. 2019. 语言模型是无监督的多任务学习者。

+   Saad-Falcon et al. (2023) Jon Saad-Falcon, Omar Khattab, Keshav Santhanam, Radu Florian, Martin Franz, Salim Roukos, Avirup Sil, Md Sultan, 和 Christopher Potts. 2023. [UDAPDR: 通过 LLM 提示和重排序器的蒸馏进行无监督领域适应](https://doi.org/10.18653/v1/2023.emnlp-main.693)。在 *2023 年自然语言处理实证方法会议论文集* 中，页面 11265–11279，新加坡。计算语言学协会。

+   Sahu 等人（2022 年）**高拉夫·萨胡**、**保罗·罗德里格斯**、**伊萨姆·拉拉吉**、**帕尔米达·阿提赫齐安**、**大卫·瓦斯克斯**和**兹米特里·巴赫达瑙**。2022 年。[**使用现成的大型语言模型进行意图分类的数据增强**](https://doi.org/10.18653/v1/2022.nlp4convai-1.5)。在*第 4 届会话 AI NLP 研讨会论文集*，页码 47–57，爱尔兰都柏林。计算语言学协会。

+   Seedat 等人（2023 年）**纳比尔·西达特**、**尼古拉斯·黄**、**鲍里斯·范·布鲁赫**和**米哈伊拉·范德·夏尔**。2023 年。[**策划的 LLM**：LLMs 和数据策划在超低数据环境下的表格增强的协同作用](http://arxiv.org/abs/2312.12112)。

+   Shao 等人（2023 年）**赵中**、**耶云·龚**、**叶龙·申**、**敏丽·黄**、**南·段**和**伟柱·陈**。2023 年。**合成提示**：为大型语言模型生成链式思维示例。在*ICML*，*机器学习研究文集*第 202 卷，页码 30706–30775。PMLR。

+   Shen 等人（2023 年）**永亮·申**、**凯涛·宋**、**徐·谭**、**东升·李**、**维明·卢**和**月亭·庄**。2023 年。**Hugginggpt**：使用 ChatGPT 及其在 Huggingface 中的伙伴解决 AI 任务。*CoRR*，abs/2303.17580。

+   Singh 等人（2023 年）**阿维·辛格**、**约翰·D·科-雷耶斯**、**瑞沙布·阿加瓦尔**、**安凯什·安南**、**皮尤什·帕蒂尔**、**哈维尔·加西亚**、**彼得·J·刘**、**詹姆斯·哈里森**、**在浩·李**、**凯尔文·徐**、**亚伦·帕里西**、**阿比谢克·库马尔**、**亚历克斯·阿莱米**、**亚历克斯·里兹科夫斯基**、**阿扎德·诺瓦**、**本·阿德拉姆**、**伯恩德·博赫内特**、**贾马勒丁·F·艾尔萨耶德**、**哈尼·塞德基**、**伊戈尔·莫达奇**、**伊莎贝尔·辛普森**、**伊泽丁·古尔**、**贾斯帕·斯诺克**、**杰弗里·佩宁顿**、**吉里·赫隆**、**凯瑟琳·肯尼利**、**凯文·斯韦尔斯基**、**克希提杰·马哈詹**、**劳拉·卡尔普**、**乐超·肖**、**麦克斯韦·L·比莱斯基**、**诺亚·康斯坦特**、**罗曼·诺瓦克**、**罗莎娜·刘**、**特里斯·瓦肯廷**、**云迪·钱**、**雅米尼·班萨尔**、**伊桑·戴尔**、**贝赫纳姆·内沙布尔**、**贾斯查·索尔-迪克斯坦**和**诺亚·费德尔**。2023 年。**超越人类数据**：使用语言模型进行问题解决的自我训练扩展。*CoRR*，abs/2312.06585。

+   Smith 等人（2022 年）**瑞安·史密斯**、**杰森·A·弗里斯**、**布雷登·汉考克**和**斯蒂芬·H·巴赫**。2022 年。**语言模型的循环**：将提示纳入弱监督中。*CoRR*，abs/2205.02318。

+   Srivastava et al. (2022) Aarohi Srivastava, Abhinav Rastogi, Abhishek Rao, Abu Awal Md Shoeb, Abubakar Abid, Adam Fisch, Adam R. Brown, Adam Santoro, Aditya Gupta, Adrià Garriga-Alonso, Agnieszka Kluska, Aitor Lewkowycz, Akshat Agarwal, Alethea Power, Alex Ray, Alex Warstadt, Alexander W. Kocurek, Ali Safaya, Ali Tazarv, Alice Xiang, Alicia Parrish, Allen Nie, Aman Hussain, Amanda Askell, Amanda Dsouza, Ameet Rahane, Anantharaman S. Iyer, Anders Andreassen, Andrea Santilli, Andreas Stuhlmüller, Andrew M. Dai, Andrew La, Andrew K. Lampinen, Andy Zou, Angela Jiang, Angelica Chen, Anh Vuong, Animesh Gupta, Anna Gottardi, Antonio Norelli, Anu Venkatesh, Arash Gholamidavoodi, Arfa Tabassum, Arul Menezes, Arun Kirubarajan, Asher Mullokandov, Ashish Sabharwal, Austin Herrick, Avia Efrat, Aykut Erdem, Ayla Karakas, 和 et al. 2022. 超越模仿游戏：量化和外推语言模型的能力. *CoRR*.

+   Su et al. (2023) Hongjin Su, Jungo Kasai, Chen Henry Wu, Weijia Shi, Tianlu Wang, Jiayi Xin, Rui Zhang, Mari Ostendorf, Luke Zettlemoyer, Noah A. Smith, 和 Tao Yu. 2023. 选择性标注使语言模型成为更好的少样本学习者. 在 *ICLR*. OpenReview.net.

+   Sudalairaj et al. (2024) Shivchander Sudalairaj, Abhishek Bhandwaldar, Aldo Pareja, Kai Xu, David D. Cox, 和 Akash Srivastava. 2024. LAB: 大规模对齐聊天机器人. *CoRR*, abs/2403.01081.

+   Sun et al. (2023) Zhiqing Sun, Yikang Shen, Qinhong Zhou, Hongxin Zhang, Zhenfang Chen, David D. Cox, Yiming Yang, 和 Chuang Gan. 2023. 原则驱动的语言模型自我对齐从零开始，且仅需最少人工监督. *CoRR*, abs/2305.03047.

+   Tang et al. (2023) Ruixiang Tang, Xiaotian Han, Xiaoqian Jiang, 和 Xia Hu. 2023. 合成数据生成的 llms 是否有助于临床文本挖掘？ *CoRR*, abs/2303.04360.

+   Taori et al. (2023) Rohan Taori, Ishaan Gulrajani, Tianyi Zhang, Yann Dubois, Xuechen Li, Carlos Guestrin, Percy Liang, 和 Tatsunori B. Hashimoto. 2023. Stanford alpaca: 一个跟随指令的 llama 模型. [`github.com/tatsu-lab/stanford_alpaca`](https://github.com/tatsu-lab/stanford_alpaca).

+   Wan et al. (2023) Fanqi Wan, Xinting Huang, Tao Yang, Xiaojun Quan, Wei Bi, 和 Shuming Shi. 2023. Explore-instruct: 通过主动探索增强领域特定指令覆盖范围. 在 *EMNLP*, 页码 9435–9454\. 计算语言学协会.

+   Wang et al. (2018) Alex Wang, Amanpreet Singh, Julian Michael, Felix Hill, Omer Levy, 和 Samuel Bowman. 2018. [GLUE: 一个多任务基准和自然语言理解分析平台](https://doi.org/10.18653/v1/W18-5446). 在 *2018 年 EMNLP 研讨会 BlackboxNLP: 分析和解释 NLP 中的神经网络*，页码 353–355, 布鲁塞尔，比利时. 计算语言学协会.

+   Wang 等人 (2023a) Guan Wang, Sijie Cheng, Xianyuan Zhan, Xiangang Li, Sen Song 和 Yang Liu. 2023a. Openchat: 通过混合质量数据推进开源语言模型。*arXiv 预印本 arXiv:2309.11235*。

+   Wang 等人 (2023b) Ruida Wang, Wangchunshu Zhou 和 Mrinmaya Sachan. 2023b. 逐步合成: 通过从小模型中推断错误来使用大型语言模型进行迭代数据集合成。在 *EMNLP (发现)* 中，页码 11817–11831。计算语言学协会。

+   Wang 等人 (2021) Shuohang Wang, Yang Liu, Yichong Xu, Chenguang Zhu 和 Michael Zeng. 2021. [想减少标注成本？GPT-3 可以帮忙](https://doi.org/10.18653/v1/2021.findings-emnlp.354)。在 *计算语言学协会会议发现：EMNLP 2021* 中，页码 4195–4205，多米尼加共和国蓬塔卡纳。计算语言学协会。

+   Wang 等人 (2023c) Yidong Wang, Zhuohao Yu, Zhengran Zeng, Linyi Yang, Cunxiang Wang, Hao Chen, Chaoya Jiang, Rui Xie, Jindong Wang, Xingxu Xie, Wei Ye, Shi-Bo Zhang 和 Yue Zhang. 2023c. Pandalm: 用于 llm 指令调优优化的自动评估基准。*ArXiv*。

+   Wang 等人 (2023d) Yizhong Wang, Yeganeh Kordi, Swaroop Mishra, Alisa Liu, Noah A. Smith, Daniel Khashabi 和 Hannaneh Hajishirzi. 2023d. [Self-instruct: 将语言模型与自生成指令对齐](https://doi.org/10.18653/v1/2023.acl-long.754)。在 *第 61 届计算语言学协会年会论文集 (第 1 卷：长篇论文)* 中，页码 13484–13508，加拿大多伦多。计算语言学协会。

+   Wang 等人 (2023e) Yizhong Wang, Yeganeh Kordi, Swaroop Mishra, Alisa Liu, Noah A. Smith, Daniel Khashabi 和 Hannaneh Hajishirzi. 2023e. Self-instruct: 将语言模型与自生成指令对齐。在 *ACL* 中，页码 13484–13508。计算语言学协会。

+   Wang 等人 (2022) Yizhong Wang, Swaroop Mishra, Pegah Alipoormolabashi, Yeganeh Kordi, Amirreza Mirzaei, Atharva Naik, Arjun Ashok, Arut Selvan Dhanasekaran, Anjana Arunkumar, David Stap, Eshaan Pathak, Giannis Karamanolakis, Haizhi Lai, Ishan Purohit, Ishani Mondal, Jacob Anderson, Kirby Kuznia, Krima Doshi, Kuntal Kumar Pal, Maitreya Patel, Mehrad Moradshahi, Mihir Parmar, Mirali Purohit, Neeraj Varshney, Phani Rohitha Kaza, Pulkit Verma, Ravsehaj Singh Puri, Rushang Karia, Savan Doshi, Shailaja Keyur Sampat, Siddhartha Mishra, Sujan Reddy A, Sumanta Patro, Tanay Dixit 和 Xudong Shen. 2022. [Super-NaturalInstructions: 通过声明性指令在 1600+ NLP 任务上的泛化](https://doi.org/10.18653/v1/2022.emnlp-main.340)。在 *2022 年自然语言处理实证方法会议论文集* 中，页码 5085–5109，阿布扎比，阿拉伯联合酋长国。计算语言学协会。

+   Wei 等人（2023a）Fusheng Wei、Robert Keeling、Nathaniel Huber-Fliflet、Jianping Zhang、Adam Dabrowski、Jingchao Yang、Qiang Mao 和 Han Qin. 2023a. 法律文档审查中的 LLM 微调的实证研究。在 *IEEE Big Data* 中，第 2786–2792 页。IEEE。

+   Wei 等人（2022）Jason Wei、Xuezhi Wang、Dale Schuurmans、Maarten Bosma、Brian Ichter、Fei Xia、Ed H. Chi、Quoc V. Le 和 Denny Zhou. 2022. 思维链提示引发大型语言模型的推理能力。在 *NeurIPS*。

+   Wei 等人（2024）Jerry Wei、Chengrun Yang、Xinying Song、Yifeng Lu、Nathan Hu、Dustin Tran、Daiyi Peng、Ruibo Liu、Da Huang、Cosmo Du 和 Quoc V. Le. 2024. 大型语言模型中的长篇事实性。*CoRR*，abs/2403.18802。

+   Wei 等人（2023b）Yuxiang Wei、Zhe Wang、Jiawei Liu、Yifeng Ding 和 Lingming Zhang. 2023b. Magicoder: 源代码就是你所需要的一切。*CoRR*，abs/2312.02120。

+   Xiao 和 Chen（2023）Le Xiao 和 Xiaolin Chen. 2023. 通过进化微调增强 LLM 以生成新闻摘要。*CoRR*，abs/2307.02839。

+   Xiao 等人（2023）Ruixuan Xiao、Yiwen Dong、Junbo Zhao、Runze Wu、Minmin Lin、Gang Chen 和 Haobo Wang. 2023. [FreeAL: 在大语言模型时代走向无人工干预的主动学习](https://doi.org/10.18653/v1/2023.emnlp-main.896)。在 *2023 年自然语言处理实证方法会议论文集* 中，第 14520–14535 页，新加坡。计算语言学协会。

+   Xu 等人（2023a）Can Xu、Qingfeng Sun、Kai Zheng、Xiubo Geng、Pu Zhao、Jiazhan Feng、Chongyang Tao 和 Daxin Jiang. 2023a. Wizardlm: 赋能大型语言模型以遵循复杂指令。*CoRR*，abs/2304.12244。

+   Xu 等人（2023b）Ran Xu、Hejie Cui、Yue Yu、Xuan Kan、Wenqi Shi、Yuchen Zhuang、Wei Jin、Joyce C. Ho 和 Carl J. Yang. 2023b. 知识注入提示：评估和推进临床文本数据生成的大型语言模型。*CoRR*，abs/2311.00287。

+   Ye 等人（2022a）Jiacheng Ye、Jiahui Gao、Qintong Li、Hang Xu、Jiangtao Feng、Zhiyong Wu、Tao Yu 和 Lingpeng Kong. 2022a. [ZeroGen: 通过数据集生成实现高效的零样本学习](https://doi.org/10.18653/v1/2022.emnlp-main.801)。在 *2022 年自然语言处理实证方法会议论文集* 中，第 11653–11669 页，阿布扎比，阿联酋。计算语言学协会。

+   Ye 等人（2022b）Jiacheng Ye、Jiahui Gao、Zhiyong Wu、Jiangtao Feng、Tao Yu 和 Lingpeng Kong. 2022b. [ProGen: 通过上下文反馈的渐进式零样本数据集生成](https://doi.org/10.18653/v1/2022.findings-emnlp.269)。在 *计算语言学协会会议论文集：EMNLP 2022* 中，第 3671–3683 页，阿布扎比，阿联酋。计算语言学协会。

+   Ye 等人（2023） Jiacheng Ye、Chengzu Li、Lingpeng Kong 和 Tao Yu。2023 年。[使用大型语言模型生成符号语言数据](https://doi.org/10.18653/v1/2023.emnlp-main.523)。在*Proceedings of the 2023 Conference on Empirical Methods in Natural Language Processing*，第 8418–8443 页，新加坡。计算语言学协会。

+   Yoo 等人（2021） Kang Min Yoo、Dongju Park、Jaewook Kang、Sang-Woo Lee 和 Woo-Myoung Park。2021 年。Gpt3mix：利用大规模语言模型进行文本增强。在*EMNLP*，第 2225–2239 页。计算语言学协会。

+   Yu 等人（2023a） Longhui Yu、Weisen Jiang、Han Shi、Jincheng Yu、Zhengying Liu、Yu Zhang、James T. Kwok、Zhenguo Li、Adrian Weller 和 Weiyang Liu。2023a。Metamath：为大型语言模型自助生成数学问题。*CoRR*，abs/2309.12284。

+   Yu 等人（2023b） Yue Yu、Yuchen Zhuang、Jieyu Zhang、Yu Meng、Alexander Ratner、Ranjay Krishna、Jiaming Shen 和 Chao Zhang。2023b。大型语言模型作为属性训练数据生成器：多样性与偏见的故事。*CoRR*，abs/2306.15895。

+   Yu 等人（2023c） Yue Yu、Yuchen Zhuang、Rongzhi Zhang、Yu Meng、Jiaming Shen 和 Chao Zhang。2023c。[ReGen：通过渐进稠密检索生成训练数据进行零样本文本分类](https://doi.org/10.18653/v1/2023.findings-acl.748)。在*Association for Computational Linguistics: ACL 2023*，第 11782–11805 页，多伦多，加拿大。计算语言学协会。

+   Zhang 等人（2023a） Chaoning Zhang、Chenshuang Zhang、Sheng Zheng、Yu Qiao、Chenghao Li、Mengchun Zhang、Sumit Kumar Dam、Chu Myaet Thwal、Ye Lin Tun、Le Luang Huy、Dong Uk Kim、Sung-Ho Bae、Lik-Hang Lee、Yang Yang、Heng Tao Shen、In So Kweon 和 Choong Seon Hong。2023a。生成性人工智能（AIGC）完整调查：从 GPT-4 到 GPT-5 的 ChatGPT 是否足够？*CoRR*，abs/2303.11717。

+   Zhang 等人（2022） Jieyu Zhang、Bohan Wang、Xiangchen Song、Yujing Wang、Yaming Yang、Jing Bai 和 Alexander Ratner。2022 年。通过弱间接监督创建训练集。在*ICLR*。OpenReview.net。

+   Zhang 等人（2023b） Ruoyu Zhang、Yanzeng Li、Yongliang Ma、Ming Zhou 和 Lei Zou。2023b。[LLMaAA：将大型语言模型作为主动标注者](https://doi.org/10.18653/v1/2023.findings-emnlp.872)。在*Findings of the Association for Computational Linguistics: EMNLP 2023*，第 13088–13103 页，新加坡。计算语言学协会。

+   Zhang 等人（2015） Xiang Zhang、Junbo Jake Zhao 和 Yann LeCun。2015 年。字符级卷积网络用于文本分类。在*Proc. of NeurIPS*。

+   Zhao 等人（2023a） Jiachen Zhao、Wenlong Zhao、Andrew Drozdov、Benjamin Rozonoyer、Md. Arafat Sultan、Jay-Yoon Lee、Mohit Iyyer 和 Andrew McCallum。2023a。从大型语言模型中多阶段协作知识蒸馏。*CoRR*，abs/2311.08640。

+   Zhao et al. (2023b) Zilong Zhao, Robert Birke, 和 Lydia Chen. 2023b. Tabula: 利用语言模型进行表格数据合成。*arXiv 预印本 arXiv:2310.12746*。

+   Zheng et al. (2023) Lianmin Zheng, Wei-Lin Chiang, Ying Sheng, Siyuan Zhuang, Zhanghao Wu, Yonghao Zhuang, Zi Lin, Zhuohan Li, Dacheng Li, Eric. P Xing, Hao Zhang, Joseph E. Gonzalez, 和 Ion Stoica. 2023. [使用 mt-bench 和聊天机器人竞技场评估 llm-as-a-judge](http://arxiv.org/abs/2306.05685)。

+   Zhu et al. (2023) Yiming Zhu, Peixian Zhang, Ehsan ul Haq, Pan Hui, 和 Gareth Tyson. 2023. ChatGPT 能否再现人类生成的标签？社会计算任务研究。*CoRR*, abs/2304.10145。

## 附录 A 数据标注

在主要文本中，我们介绍了一系列用于通用数据合成的技术。尽管标注可以被视为一种特殊类型的合成，其中的合成条件是特定样本的输入，但也有专门适用于数据标注的方法。其中，选择性标注是最重要的实践之一。选择性标注代表了昂贵且精确的人类标注与经济但相对粗略的基于 LLM 的标注之间的最佳权衡。Wang et al. ([2021](https://arxiv.org/html/2406.15126v1#bib.bib88)); Kocon et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib41))。

选择性标注的关键在于定义一个在人工和 LLM 之间的“性价比”样本分布。Zhang et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib110)); Bansal 和 Sharma ([2023](https://arxiv.org/html/2406.15126v1#bib.bib4)) 介绍了一些常见的基于 LLM 的标注选择策略，包括随机选择、最大熵选择、最小置信度选择和 $k$均值选择，以进行全面比较。结果表明，基于不确定性的方法，即最大熵和最小置信度，比随机基线表现显著更好，具有更快的收敛速度和更好的下游模型性能，后者在标注数据上训练。Li et al. ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib48)) 还利用不确定性来估计 LLM 的标注能力，从而有效地分配人工和 LLM 之间的标注工作。Su et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib79)) 则提出了一种新颖的无监督图形化选择性标注方法，名为 vote-$k$，以选择多样且具有代表性的示例进行标注。

## 附录 B 调优技术

另一大类研究涉及调优技术，例如模型微调 Zhao 等人 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib113)); Sun 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib81)); Meng 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib61)); Kurakin 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib43)) 和软提示 Chen 等人 ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib8))，这些技术已经在其他领域得到广泛研究，可详细参考 Hu 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib35)); Lu 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib56)); Wei 等人 ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib93)); Xiao 和 Chen ([2023](https://arxiv.org/html/2406.15126v1#bib.bib97))。尽管这些方法在提高生成性能方面效果显著，但大多数现有方法是基于 LLM 的可访问性建立的，而其在黑箱模型上的应用仍需进一步探索。

## 附录 C 应用

基于 LLM 的合成数据生成已成为传统依赖人工数据收集的新替代方案，并在各种应用中展示了巨大的潜力，包括一般任务、特定领域任务和多模态任务。

##### 一般任务。

随着 LLM 能力的爆炸性增长，这一生成流程已被广泛应用于基础 NLP 研究中，包括文本分类 Ye 等人 ([2022b](https://arxiv.org/html/2406.15126v1#bib.bib102)); Yu 等人 ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib107)); Sahu 等人 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib72))，命名实体识别 Xiao 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib98))，问答 Li 和 Callison-Burch ([2023](https://arxiv.org/html/2406.15126v1#bib.bib46))，关系提取 He 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib29))，以及自然语言推理 Zhang 等人 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib110))。这些研究进一步支持了多样的应用，如情感识别 Gao 等人 ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib20)); Ye 等人 ([2022b](https://arxiv.org/html/2406.15126v1#bib.bib102))，在线翻译 Oh 等人 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib65))，立场检测 Li 等人 ([2023a](https://arxiv.org/html/2406.15126v1#bib.bib48)) 和垃圾邮件识别 Smith 等人 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib77))。

##### 特定领域任务。

一些特定领域的任务对这一流程提出了显著要求，其中人工标注可能极其昂贵且不切实际，例如医疗诊断 Tang et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib82))、药物发现 Xiao et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib98))、临床试验提取 Xu et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib100))、工业广告 Zhang et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib109)) 和表格数据分析 Seedat et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib73))。

##### 多模态任务。

基于其简单性和低成本，这种生成范式在多模态任务中也展现了显著的前景，包括文本-图像检索 Kritharoula et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib42))、对话理解 Han et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib27))、视觉问答 Han and Gardent ([2023](https://arxiv.org/html/2406.15126v1#bib.bib26)) 和多模态指令调整 Liu et al. ([2023](https://arxiv.org/html/2406.15126v1#bib.bib53))。

| 类型 | 基准数据集 | 子数据集数量 | 部分子数据集 | 任务 | 能力 | 领域/数据来源 |
| --- | --- | --- | --- | --- | --- | --- |
| 分类 | 短信垃圾邮件 Almeida et al. ([2011](https://arxiv.org/html/2406.15126v1#bib.bib1)); Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)) | 1 | 短信垃圾邮件 | 文本分类 | 垃圾邮件检测 | 短信 |
| AG News Zhang et al. ([2015](https://arxiv.org/html/2406.15126v1#bib.bib111)); Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)) | 1 | AG News | 文本分类 | 主题分类 | 新闻 |
| IMDb Maas et al. ([2011](https://arxiv.org/html/2406.15126v1#bib.bib59)); Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)); Wang et al. ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib87)) | 1 | IMDb | 文本分类 | 二分类情感分类 | 影评 |
| GoEmotions Demszky et al. ([2020](https://arxiv.org/html/2406.15126v1#bib.bib13)); Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)) | 1 | GoEmotions | 文本分类 | 情感分类 | Reddit 评论 |
| CLINC150 Larson et al. ([2019](https://arxiv.org/html/2406.15126v1#bib.bib44)); Sahu et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib72)) | 1 | CLINC150 | 文本分类 | 意图检测 | 人工标注 |
| BANKING77 Casanueva et al. ([2020](https://arxiv.org/html/2406.15126v1#bib.bib7)); Sahu et al. ([2022](https://arxiv.org/html/2406.15126v1#bib.bib72)) | 1 | BANKING77 | 文本分类 | 意图检测 | 银行 |
| FewRel Gao et al. ([2019](https://arxiv.org/html/2406.15126v1#bib.bib21)); Li et al. ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)) | 1 | FewRel | 文本分类 | 关系分类 | Wikipedia |
| GLUE Wang 等 ([2018](https://arxiv.org/html/2406.15126v1#bib.bib85), [2023b](https://arxiv.org/html/2406.15126v1#bib.bib87)) | 7 | QNLI | 自然语言推断 | 识别文本蕴含 | Wikipedia |
| RTE | 自然语言推断 | 识别文本蕴含 | 新闻和 Wikipedia |
| QA | AdversarialQA Bartolo 等 ([2020](https://arxiv.org/html/2406.15126v1#bib.bib5)); Wang 等 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib87)) | 1 | AdversarialQA | 问答 | 阅读理解 | Wikipedia |
| TruthfulQA Lin 等 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib51)); Sun 等 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib81)) | 1 | TruthfulQA | 问答 | 诚实性 | 硬数据 |
| 推理 | MATH Hendrycks 等 ([2021](https://arxiv.org/html/2406.15126v1#bib.bib30)); Wan 等 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib84)) | 1 | MATH | 数学推理 | 复杂推理 | 数学 |
| **ToolBench** Qin 等 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib69)) | 1 | ToolBench | 轨迹规划 | 工具操作 | 工具 |
| - | NIV2 Wang 等 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib92), [2023e](https://arxiv.org/html/2406.15126v1#bib.bib91)) | 1616 | - | - | 语言理解与推理 | 基准集合/人工注释 |
| - | BIG-bench Srivastava 等 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib78)); Sun 等 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib81)) | 204 | - | - | 语言理解与推理 | 人工注释 |

表 1：用于评估使用生成数据训练的模型的代表性基准数据集。基于 LLM 生成的数据集用粗体字突出显示。

## 附录 D 基准数据集

在表格[1](https://arxiv.org/html/2406.15126v1#A3.T1 "Table 1 ‣ Multimodal Tasks. ‣ Appendix C Applications ‣ On LLMs-Driven Synthetic Data Generation, Curation, and Evaluation: A Survey")中，我们总结了用于评估通过数据生成训练的模型的代表性基准数据集。其中，**ToolBench** Qin 等 ([2023](https://arxiv.org/html/2406.15126v1#bib.bib69)) 是由 LLMs 生成的，通常用于评估 LLMs 在工具使用能力方面的表现。在大多数分类任务评估中，Li 等 ([2023c](https://arxiv.org/html/2406.15126v1#bib.bib50)); Wang 等 ([2023b](https://arxiv.org/html/2406.15126v1#bib.bib87)); Sahu 等 ([2022](https://arxiv.org/html/2406.15126v1#bib.bib72))，LLMs 通常不被用作测试模型；相反，通常使用在生成数据上训练的小型语言模型，然后在现有基准上进行测试。

由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)生成于 2024 年 6 月 14 日星期五 07:44:27
