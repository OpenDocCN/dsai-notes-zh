<!--yml

category: 未分类

date: 2024-09-03 17:29:14

-->

# CAP 原则：长期上下文大语言模型服务的调查

> 来源：[`arxiv.org/html/2405.11299`](https://arxiv.org/html/2405.11299)

1.  [1 引言](https://arxiv.org/html/2405.11299v2#S1 "在 CAP 原则：长期上下文大语言模型服务的调查")

1.  [2 CAP 用于 LLM 服务](https://arxiv.org/html/2405.11299v2#S2 "在 CAP 原则：长期上下文大语言模型服务的调查")

    1.  [2.1 概述](https://arxiv.org/html/2405.11299v2#S2.SS1 "在 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

    1.  [2.2 改善上下文 (C)](https://arxiv.org/html/2405.11299v2#S2.SS2 "在 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

        1.  [2.2.1 模型记忆](https://arxiv.org/html/2405.11299v2#S2.SS2.SSS1 "在 2.2 改善上下文 (C) ‣ 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

            1.  [系统视角的分类](https://arxiv.org/html/2405.11299v2#S2.SS2.SSS1.Px1 "在 2.2.1 模型记忆 ‣ 2.2 改善上下文 (C) ‣ 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

        1.  [2.2.2 位置嵌入](https://arxiv.org/html/2405.11299v2#S2.SS2.SSS2 "在 2.2 改善上下文 (C) ‣ 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

    1.  [2.3 改善准确性 (A)](https://arxiv.org/html/2405.11299v2#S2.SS3 "在 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

    1.  [2.4 提升性能 (P)](https://arxiv.org/html/2405.11299v2#S2.SS4 "在 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

        1.  [2.4.1 稀疏注意力](https://arxiv.org/html/2405.11299v2#S2.SS4.SSS1 "在 2.4 提升性能 (P) ‣ 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

        1.  [2.4.2 线性注意力](https://arxiv.org/html/2405.11299v2#S2.SS4.SSS2 "在 2.4 提升性能 (P) ‣ 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

        1.  [2.4.3 分布式加速](https://arxiv.org/html/2405.11299v2#S2.SS4.SSS3 "在 2.4 提升性能 (P) ‣ 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

    1.  [2.5 改善上下文和性能 (CP)](https://arxiv.org/html/2405.11299v2#S2.SS5 "在 2 CAP 用于 LLM 服务 ‣ CAP 原则：长期上下文大语言模型服务的调查")

        1.  [2.5.1 提示压缩](https://arxiv.org/html/2405.11299v2#S2.SS5.SSS1 "在 2.5 改善上下文和性能（CP） ‣ 2 LLM 服务的 CAP ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查中")

    1.  [2.6 改善上下文和准确性（CA）](https://arxiv.org/html/2405.11299v2#S2.SS6 "在 2 LLM 服务的 CAP ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查中")

        1.  [2.6.1 代理记忆](https://arxiv.org/html/2405.11299v2#S2.SS6.SSS1 "在 2.6 改善上下文和准确性（CA） ‣ 2 LLM 服务的 CAP ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查中")

1.  [3 结论](https://arxiv.org/html/2405.11299v2#S3 "在 LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查中")

# LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查

牌 曾

华为云 & 上海交通大学

甄宇 宁

上海交通大学

解如 赵

上海交通大学

魏浩 崔

上海交通大学

孟伟 许

北京邮电大学

李伟 郭

电子科技大学

许生 陈

华为云

易舟 单

华为云

###### 摘要

我们调查了大型语言模型（LLM）服务领域，以了解成本效益与准确性之间的复杂动态，这一问题随着在大规模部署模型时对长上下文理解需求的增长而被放大。我们的研究发现，该领域的工作在三个不同但相互冲突的目标之间进行优化：改善服务上下文长度（C）、改善服务准确性（A）和改善服务性能（P）。受数据库中 CAP 定理的启发，我们提出了 LLM 服务的 CAP 原则，该原则建议任何优化最多只能同时改善这三个目标中的两个。我们的调查在这一框架内对现有工作进行了分类。我们发现，用户感知测量指标的定义和连续性对于确定目标是否已实现至关重要，类似于先前的 CAP 数据库应用。我们将 LLM 服务的 CAP 原则视为指导原则，而非正式定理，以告知设计者服务模型中的固有和动态权衡。由于服务准确性和性能已被广泛研究，本调查集中于扩展服务上下文长度及应对由此产生的挑战的工作。

## 1 引言

大型语言模型（LLMs）及其基础的变换器架构已经彻底改变了人工智能，并成为许多新兴应用的基石。LLM 周围的生态系统正朝着人工通用智能（AGI）上升：新 LLM 和其应用的数量猛增，截至 2024 年，基于 LLM 的应用已经在图像分类和视觉推理等许多任务中超过了人类[[1](https://arxiv.org/html/2405.11299v2#bib.bib1), [2](https://arxiv.org/html/2405.11299v2#bib.bib2)]。高质量模型对于实现 AGI 至关重要，但同样重要的是以合理低成本大规模部署和服务模型，而不影响其准确性。服务准确性和服务性能（例如，每秒处理的 tokens 数量）之间的冲突是一个棘手的问题，促使了该领域的大量研究[[3](https://arxiv.org/html/2405.11299v2#bib.bib3), [4](https://arxiv.org/html/2405.11299v2#bib.bib4)]。通常，在生产环境中没有一刀切的解决方案。提升性能的优化可能会导致准确性的降低，反之亦然。例如，稀疏性和量化是两种常见的技术，它们在提高性能的同时会牺牲准确性。

不幸的是，随着实际部署模型时对更长上下文理解的需求增长，这种准确性与性能之间的冲突最近被加剧了[[5](https://arxiv.org/html/2405.11299v2#bib.bib5)]。这引入了新的复杂性，因为变换器的注意力机制在处理更长上下文时资源消耗呈二次增长[[6](https://arxiv.org/html/2405.11299v2#bib.bib6)]。此外，LLM 在有效利用更长上下文中的信息方面也存在困难[[7](https://arxiv.org/html/2405.11299v2#bib.bib7)]。本质上，对长上下文的服务需求打破了服务准确性和性能之间脆弱的平衡，并呼唤新的系统设计。

为了探讨在大规模模型部署中准确性与性能之间复杂的关系，特别是处理长上下文的情况，我们对 LLM 服务领域进行了广泛的调查。在回顾相关文献后，我们强调了三个关键观察点。

1.  1.

    首先，我们发现服务系统的范围已经扩展。它包括两个系统层次：模型服务层和代理服务层。模型层系统运行给定的 LLM 模型，通常将模型推理作为其北向 API[[8](https://arxiv.org/html/2405.11299v2#bib.bib8), [9](https://arxiv.org/html/2405.11299v2#bib.bib9)]。在这一层次上的工作通常优化模型结构[[10](https://arxiv.org/html/2405.11299v2#bib.bib10), [11](https://arxiv.org/html/2405.11299v2#bib.bib11)]、缓存[[8](https://arxiv.org/html/2405.11299v2#bib.bib8), [12](https://arxiv.org/html/2405.11299v2#bib.bib12)]、调度[[13](https://arxiv.org/html/2405.11299v2#bib.bib13), [14](https://arxiv.org/html/2405.11299v2#bib.bib14)]等。代理层系统位于模型层系统之上，是利用 LLM 驱动的工作流来提高原始 LLM 模型的准确性和效率，同时处理复杂实际任务的 LLM 驱动系统应用的结果[[15](https://arxiv.org/html/2405.11299v2#bib.bib15)]。

1.  2.

    其次，我们发现这一领域的工作在三个不同的目标上进行优化：提高服务上下文长度（Context）、提高服务准确性（Accuracy）和提高服务性能（Performance）。具体来说，上下文是指上下文窗口中的令牌数量；准确性是指在某些任务上的评估指标（例如，MMLU），而性能是指首次令牌的时间、每秒令牌数、每百万令牌的价格等。

1.  3.

    最后，我们发现上述三个目标之间存在三难困境，无论它们应用于哪个层次。我们发现，任何服务优化最多只能改善两个不同的目标。此外，我们还观察到在一个方向上的进展不会导致其他方向的进展。例如，使用位置嵌入扩展模型的范围并不会提高模型在上下文长度之外的准确性[[16](https://arxiv.org/html/2405.11299v2#bib.bib16)]，而使用量化[[11](https://arxiv.org/html/2405.11299v2#bib.bib11)]、剪枝[[17](https://arxiv.org/html/2405.11299v2#bib.bib17)]和稀疏性[[12](https://arxiv.org/html/2405.11299v2#bib.bib12)]可以使模型的服务速度更快，但可能以牺牲准确性为代价。

基于上述观察，并受到经典的数据库 CAP 定理的启发[[18](https://arxiv.org/html/2405.11299v2#bib.bib18)]，我们提出了 LLM 服务的 CAP 原则，该原则指出，任何给定的 LLM 服务优化，无论应用于哪个系统层次，最多只能改善以下两个目标中的两个：

+   •

    上下文：终端用户有效处理和感知的上下文长度。

+   •

    准确性：终端用户根据特定任务指标评估的输出精度。

+   •

    性能：终端用户感知的令牌处理和生成的效率。

![参见说明文字](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：LLM 服务的 CAP 原则。C 是改善上下文长度，A 是提高准确性，P 是改善服务性能或成本效益。它表示任何服务优化至多可以改进上述三个目标中的两个。

提出的 CAP 原则的视角强调的是最终用户从对远程 LLM 服务系统应用特定优化中感知到的效果，而不是关注 LLM 服务系统中的特定组件。这一点至关重要，因为我们关心的是一个 LLM 服务系统整体是否能服务 AGI，而不是单一方向上的改进。一般来说，这一原则导致六种类型的优化：C、A、P、CA、CP 和 AP，取决于哪个目标被优先考虑。

LLM 的 CAP 原则在许多方面类似于数据库的 CAP 定理。

+   •

    两者都表示，为了实现其他目标，你必须放弃至少一个目标。由于我们关注的是长上下文服务，维持长上下文（C）是必要的。这使我们有两个选择：提高准确性（A）或提高性能（P）。提高准确性依赖于设计新算法，以更好地利用长上下文的特性。然而，这些算法可能由于增加的 FLOPs、硬件不友好的操作等因素，影响模型执行的成本效益。另一方面，通过量化和稀疏性等技术在特定硬件上提高性能通常会以降低准确性为代价。虽然有方法可以在不失准确性的情况下提高性能，但通常需要额外的硬件资源。

+   •

    他们的目标是持续测量的，而不是二元的。用户感知的测量指标的定义和连续性对于确定目标是否达成至关重要。一些近期研究已对这一方面进行了准确性检查[[19](https://arxiv.org/html/2405.11299v2#bib.bib19), [20](https://arxiv.org/html/2405.11299v2#bib.bib20)]。数据库的 CAP 可用性和 LLM 的 CAP 准确性都在 0 到 100 之间。LLM 的 CAP 原则的准确性，像数据库 CAP 定理的可用性一样，不必达到 100%。只需要足够高，以便最终用户认为它有用。因此，从系统的角度来看，分类为 CP 的优化即使满足用户的准确性要求，仍然可能被视为实现了所有三个 CAP 目标，这类似于在实际数据库中观察 CAP 的方式[[21](https://arxiv.org/html/2405.11299v2#bib.bib21)]。

+   •

    两者最初提出是为了让系统设计师在部署大规模系统时意识到严格的设计权衡。

我们预见到未来可能实现真正的 CAP，其中这些目标之间没有固有的冲突。提出的 CAP 原则主要源于在现有 AI 芯片上使用基于变换器的 LLM，这反映了当今硬件和软件的限制与能力。随着我们向 AGI 的进步，模型和硬件都预计会显著演变。新兴技术可能会同步开发，新模型将特别设计以优化在下一代硬件上的性能。模型和硬件之间的这种协同作用对于克服当前障碍和在 LLM 服务中实现真正的 CAP 至关重要。

我们的调查是基于提出的 CAP 原则组织的。与之前的调查[[4](https://arxiv.org/html/2405.11299v2#bib.bib4)、[3](https://arxiv.org/html/2405.11299v2#bib.bib3)、[22](https://arxiv.org/html/2405.11299v2#bib.bib22)、[23](https://arxiv.org/html/2405.11299v2#bib.bib23)、[24](https://arxiv.org/html/2405.11299v2#bib.bib24)、[25](https://arxiv.org/html/2405.11299v2#bib.bib25)、[26](https://arxiv.org/html/2405.11299v2#bib.bib26)]相比，我们做出了两个独特的贡献。首先，我们提出了 LLM 服务的 CAP 原则，并将现有工作映射到 CAP 格局中，以突出它们之间的紧张关系。其次，我们将大规模 LLM 服务系统作为一个整体来研究，而不是专注于某个具体技术（例如 RAG [[26](https://arxiv.org/html/2405.11299v2#bib.bib26)]、长上下文 [[23](https://arxiv.org/html/2405.11299v2#bib.bib23)]）或某一层（例如模型 [[3](https://arxiv.org/html/2405.11299v2#bib.bib3)]、代理 [[25](https://arxiv.org/html/2405.11299v2#bib.bib25)]）。在接下来的部分中，我们将讨论表[1](https://arxiv.org/html/2405.11299v2#S2.T1 "表 1 ‣ 2 CAP 适用于 LLM 服务 ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查")和图[2](https://arxiv.org/html/2405.11299v2#S2.F2 "图 2 ‣ 2 CAP 适用于 LLM 服务 ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查")中列出的工作。我们关注那些扩展服务上下文长度并解决由此产生的准确性和性能问题的工作。具体来说，我们将涵盖模型记忆（表[2](https://arxiv.org/html/2405.11299v2#S2.T2 "表 2 ‣ 2.2.1 模型记忆 ‣ 2.2 改善上下文 (C) ‣ 2 CAP 适用于 LLM 服务 ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查")）、位置嵌入（表[3](https://arxiv.org/html/2405.11299v2#S2.T3 "表 3 ‣ 2.2.2 位置嵌入 ‣ 2.2 改善上下文 (C) ‣ 2 CAP 适用于 LLM 服务 ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查")）、中间找到、长上下文的分布式加速、提示压缩、稀疏性（表[5](https://arxiv.org/html/2405.11299v2#S2.T5 "表 5 ‣ 2.4.1 稀疏注意力 ‣ 2.4 改善性能 (P) ‣ 2 CAP 适用于 LLM 服务 ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查")）以及代理记忆（表[7](https://arxiv.org/html/2405.11299v2#S2.T7 "表 7 ‣ 2.6.1 代理记忆 ‣ 2.6 改善上下文和准确性 (CA) ‣ 2 CAP 适用于 LLM 服务 ‣ LLM 服务的 CAP 原则：长上下文大型语言模型服务的调查")）。

## 2 CAP 适用于 LLM 服务

表 1：CAP 定理在 LLM 服务中的结果呈现六种类型。

| 类型 | 优化 |
| --- | --- |
| C | 模型记忆，位置嵌入 |
| A | 中间找到 |
| P | 稀疏注意力，线性注意力，分布式加速，量化，模型剪枝 |
| CP | 提示剪枝 |
| CA | 代理记忆 |
| AP | 不适用 |

![参见说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2：现代 LLM 服务系统通常具有两个层次：模型层，运行给定的 LLM 模型，以及代理层，运行基于 LLM 的系统应用。PE 代表位置嵌入。Quant 是量化的缩写。

### 2.1 概述

我们对该领域进行了调查，并将其映射到表格[1](https://arxiv.org/html/2405.11299v2#S2.T1 "Table 1 ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving")中，如图[2](https://arxiv.org/html/2405.11299v2#S2.F2 "Figure 2 ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving")所示的代理和模型层。值得注意的是，我们可以将所有现有的 LLM 服务优化工作映射到 CAP 产生的六种类型中，突显了我们提出的 CAP 原则反映了该领域固有的长期设计权衡。

表格[1](https://arxiv.org/html/2405.11299v2#S2.T1 "Table 1 ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving")的概述：

+   •

    共有六种类型：C、A、P、CA、CP 和 AP，具体取决于优先考虑哪些目标。

+   •

    C：这一领域的工作仅改善 LLM 服务系统的上下文长度。我们的研究识别了改进 C 的两种方法。我们将第一种方法称为模型记忆，这是一种增强变换器的递归和动态外部记忆的工作。另一种是位置嵌入，它将模型的上下文窗口扩展到更长的上下文和更多的标记。

+   •

    A：这一领域的工作解决了长上下文服务中出现的准确性问题。存在一些初步工作，例如发现中间，但有些工作为了更好的 A 而放弃了 P。

+   •

    P：在这一领域的研究通常提高了服务性能或成本效益。我们特别关注两类工作，这些工作旨在改善长上下文服务。第一类是分布式加速，它探讨了序列并行以实现更快的处理。第二类是稀疏性，它减少了计算和内存使用，从而提高性能。

+   •

    CP：这种类型的工作同时改进了这两个方面。我们已确定提示压缩是这一类别的唯一工作方向。

+   •

    CA：这种类型的工作同时改进了这两个方面。我们已确定代理记忆是这一类别的唯一工作方向。

### 2.2 改善上下文（C）

本节调查了扩展服务系统上下文长度的工作，以应对对长上下文推理的日益增长的需求。我们将讨论两种方法。我们将第一种方法称为模型记忆，这是一种通过递归和动态外部记忆增强变换器架构的工作。另一种是位置嵌入，它将 LLM 的上下文窗口扩展到处理更多的标记。

#### 2.2.1 模型记忆

表格 2：比较模型记忆工作。

| 工作 | 内存聚合 | 内存组织 | 内存检索 | 内存更新 | 内存驱逐 |
| --- | --- | --- | --- | --- | --- |
| Transformer-XL [[10](https://arxiv.org/html/2405.11299v2#bib.bib10)] | 点注意力 | FIFO | 全部 | 无 | 丢弃 |
| 压缩 Transformer [[27](https://arxiv.org/html/2405.11299v2#bib.bib27)] | 点注意力 | FIFO | 全部 | 无 | 丢弃 |
| 记忆 Transformer [[28](https://arxiv.org/html/2405.11299v2#bib.bib28)] | 学习门 | FIFO | kNN | 无 | 丢弃 |
| Memformer [[29](https://arxiv.org/html/2405.11299v2#bib.bib29)] | 点注意力 | 随机 | 全部 | 是 | 是 |
| 记忆 Transformer [[30](https://arxiv.org/html/2405.11299v2#bib.bib30)] | 软提示 | 随机 | 全部 | 是 | 是 |
| RMT [[31](https://arxiv.org/html/2405.11299v2#bib.bib31)] | 软提示 | FIFO | 全部 | 无 | 丢弃 |
| AutoCompressor [[32](https://arxiv.org/html/2405.11299v2#bib.bib32)] | 软提示 | FIFO | 全部 | 无 | 丢弃 |
| Infini-Attention [[33](https://arxiv.org/html/2405.11299v2#bib.bib33)] | 学习门 | 随机 | 线性 | 是 | 是 |

扩展 Transformer 上下文长度的一种方式是添加内存以保存远程信息。我们为这种工作流命名为模型内存，它通过递归和动态外部内存扩展 Transformer 架构。核心在于，模型内存为 Transformer 建立了一个内存系统，使其能够检查过去的远程信息。

##### 从系统角度的分类

我们意识到，管理 Transformer 模型的扩展内存类似于操作系统中的经典虚拟内存管理 [[34](https://arxiv.org/html/2405.11299v2#bib.bib34)]，这主要围绕组织内存、读取、更新以及驱逐的内容和时间。为此，我们建议通过将模型内存工作映射到以下五个维度来进行比较。

+   •

    内存聚合：决定如何将局部内存与全局内存（从扩展内存中检索）聚合。可以是注意力机制、学习门或软提示。

+   •

    内存组织：决定如何组织外部扩展内存。可以是 FIFO 缓冲区或随机访问缓冲区，内存大小固定。由于容量限制，似乎没有动态大小的内存。

+   •

    内存检索：决定如何以及从扩展内存中检索什么。大多数工作会检索整个内存，而其他工作则使用某些算法检索部分内存。

+   •

    内存更新：决定在有新内存时如何更新扩展内存。如果是 FIFO 内存，更新意味着入队。如果是随机内存，更新将使用某些算法更新全部或部分内存。

+   •

    内存驱逐：决定在扩展内存满时驱逐什么。如果是 FIFO 内存，驱逐会丢弃尾部内存。如果是随机内存，则不会发生驱逐，因为内存会就地更新。

我们现在深入探讨表格 [2](https://arxiv.org/html/2405.11299v2#S2.T2 "Table 2 ‣ 2.2.1 Model Memory ‣ 2.2 Improve Context (C) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving") 中列出的工作。

+   •

    Transformer-XL [[10](https://arxiv.org/html/2405.11299v2#bib.bib10)] 为 Transformer 架构添加了递归。它使用每层的内存缓冲区来捕捉长期依赖，并将长序列分割成固定大小的段，以捕捉相邻层之间的段级递归。其内存组织是 FIFO，没有更新规则。旧记忆会随着新段的加入而被丢弃。在推理过程中，它通过点积注意力将从内存中读取的隐藏状态和当前段的局部状态进行聚合。Compressive Transformer [[27](https://arxiv.org/html/2405.11299v2#bib.bib27)] 在 Transformer-XL 的基础上添加了第二级压缩内存。它进一步扩展了上下文而不改变核心机制。Memorizing Transformer [[28](https://arxiv.org/html/2405.11299v2#bib.bib28)] 采取了稍有不同的方法。它不是读取整个内存，而是使用 kNN 算法从外部内存中检索，并通过学习到的门进行聚合。上述三种方法会丢弃来自遥远过去的信息。

+   •

    Memformer [[29](https://arxiv.org/html/2405.11299v2#bib.bib29)] 为 Transformer 架构添加了固定大小的动态外部内存。它使用随机访问内存，而不是前两种方法使用的 FIFO 内存。它将内存分隔成许多插槽，并设计了一种基于注意力的算法来独立更新内存插槽。此外，它使用遗忘机制来逐出未在多个时间戳中更新的内存插槽。通过这种方式，它关注更重要的信息，并声称理论上具有无限的记忆时间范围。

+   •

    Memory Transformer [[30](https://arxiv.org/html/2405.11299v2#bib.bib30)] 与 Memformer [[29](https://arxiv.org/html/2405.11299v2#bib.bib29)] 的不同之处在于前者使用软提示 [[35](https://arxiv.org/html/2405.11299v2#bib.bib35)] 将外部内存中的信息与当前提示汇聚。它将内存标记添加到用户提示的开头，并使用未修改的注意力模块使内存标记能够关注长序列。

+   •

    RMT [[31](https://arxiv.org/html/2405.11299v2#bib.bib31)] 和 AutoCompressor [[32](https://arxiv.org/html/2405.11299v2#bib.bib32)] 使用软提示将内存标记添加到提示的开头，这与 Memory Transformer [[30](https://arxiv.org/html/2405.11299v2#bib.bib30)] 和 Transformer-XL [[10](https://arxiv.org/html/2405.11299v2#bib.bib10)] 中的段级递归类似。两者都基于 Transformer-XL 的代码库构建。

+   •

    Infin-Attention [[33](https://arxiv.org/html/2405.11299v2#bib.bib33)]是这一类别中最新的工作。它将压缩和动态记忆与普通的点积注意力层紧密结合，使模型能够处理无限长度的上下文。它采用关联矩阵作为记忆，允许随机访问。它使用线性注意力检索记忆，并使用增量更新规则更新记忆。它通过学习的门将检索到的记忆与局部注意力状态进行聚合。与普通的 Transformer-XL 相比，这种方法使用更少的计算和内存。

总结来说，模型记忆工作通过动态和压缩记忆增强了原始的 Transformer 架构，使模型能够处理长甚至无限的上下文。它们在记忆的访问方式、记忆的更新等方面有所不同。由于大多数方法要么丢弃要么压缩记忆，它们不可避免地会损害 A。在 P 方面，它们保持中立，因为它们没有解决注意力机制中的平方复杂度。

#### 2.2.2 位置嵌入

表 3：比较位置嵌入工作。

| 工作 | 位置 | 需要训练 | 自适应 | 集成 |
| --- | --- | --- | --- | --- |
| ALiBi [[36](https://arxiv.org/html/2405.11299v2#bib.bib36)] | QK 相乘后 | ✓ | ✗ | 添加 |
| XPOS [[37](https://arxiv.org/html/2405.11299v2#bib.bib37)] | QK 相乘前 | ✓ | ✗ | 乘法 |
| CLEX [[38](https://arxiv.org/html/2405.11299v2#bib.bib38)] | QK 相乘前 | ✓ | ✓ | 乘法 |
| 线性插值 [[39](https://arxiv.org/html/2405.11299v2#bib.bib39)] | QK 相乘前 | ✗ | ✗ | 乘法 |
| NTK 插值  [[40](https://arxiv.org/html/2405.11299v2#bib.bib40)] | QK 相乘前 | ✗ | ✗ | 乘法 |
| YaRN [[41](https://arxiv.org/html/2405.11299v2#bib.bib41)] | QK 相乘前 | ✓ | ✓ | 乘法 |
| FIRE [[42](https://arxiv.org/html/2405.11299v2#bib.bib42)] | QK 相乘后 | ✓ | ✓ | 添加 |
| LongRoPE [[43](https://arxiv.org/html/2405.11299v2#bib.bib43)] | QK 相乘前 | ✓ | ✓ | 乘法 |

这项工作专注于位置嵌入（PE），使 LLM 能够处理长上下文序列（从而改善 C）。在表格 [3](https://arxiv.org/html/2405.11299v2#S2.T3 "Table 3 ‣ 2.2.2 Positional Embedding ‣ 2.2 Improve Context (C) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving")中，我们在四个维度上进行比较。

+   •

    位置：位置数据是如何被编码到令牌表示中的。

+   •

    需要训练：是否可以即插即用而无需重新训练。

+   •

    自适应：是否可以根据输入进行适应和调整。

+   •

    集成：位置表示如何与令牌表示集成。

我们下面的讨论被分类为外推和插值。

+   •

    位置外推。这一策略将位置嵌入扩展到超出训练时最大上下文长度的范围。例如，ALiBi [[36](https://arxiv.org/html/2405.11299v2#bib.bib36)] 引入了相对位置嵌入和可学习的线性偏置，使得模型能够根据序列的实际长度动态调整注意力分布。XPOS [[37](https://arxiv.org/html/2405.11299v2#bib.bib37)] 在 ROPE 的基础上引入了额外的指数衰减项，使得注意力在相对距离增加时逐渐衰减。CLEX [[38](https://arxiv.org/html/2405.11299v2#bib.bib38)] 将连续动态建模为带有长度缩放因子的常微分方程，通过推广位置嵌入缩放来实现。

+   •

    位置插值：这一策略将输入位置编码索引范围缩放到模型的上下文窗口。例如，线性插值 [[39](https://arxiv.org/html/2405.11299v2#bib.bib39)] 引入了一种位置插值技术，直接减少位置索引。这样，最大位置索引匹配了预训练阶段的上下文窗口约束，从而扩展了上下文窗口。受到神经切线核（NTK）理论的启发，仅使用位置插值的模型将难以识别相邻标记的顺序和位置。NTK 插值 [[40](https://arxiv.org/html/2405.11299v2#bib.bib40)] 设计了一种非线性方法，通过动态调整 RoPE 中的基数来调整缩放因子。YaRN [[41](https://arxiv.org/html/2405.11299v2#bib.bib41)] 结合了 NTK 插值和线性插值，并引入了一种注意力分布修正策略，以抵消长输入所导致的注意力矩阵中的分布偏差。FIRE [[42](https://arxiv.org/html/2405.11299v2#bib.bib42)] 使用可学习的连续函数将位置信息映射到偏置，并提出了渐进式插值来解决输入长度超出训练范围时的泛化问题。LongRoPE [[43](https://arxiv.org/html/2405.11299v2#bib.bib43)] 通过识别和利用 RoPE 维度和标记位置的非均匀性，改进了位置插值方法。PoSE [[44](https://arxiv.org/html/2405.11299v2#bib.bib44)] 引入了一种称为位置跳跃法（Positional Skip-wise Method）的训练方法，通过应用量身定制的跳跃偏置项来调整每个片段的位置索引，从而模拟在固定上下文窗口内的扩展输入。

总结来说，对位置嵌入的研究增强了模型在训练阶段未出现的位置信息的泛化能力，通过外推和插值两种方式。这些方法根据输入位置索引范围是否缩放以适应模型的上下文窗口而有所不同。它们在 C 和 P 上是中性的，我们认为它们对于实现长上下文服务至关重要。

### 2.3 提高准确性 (A)

较长的 C 挑战 A。本节集中讨论解决长上下文 LLM 服务中出现的准确性问题的工作。中间丢失 [[7](https://arxiv.org/html/2405.11299v2#bib.bib7)] 是分析 LLM 如何利用长上下文的开创性工作。他们发现现有的 LLM 不能稳健地利用长上下文中的信息，文档的位置会影响最终的服务准确性。这一缺陷将限制长上下文 LLM 在实际应用中的使用，导致输出偏差。

我们找到三项工作来解决这个问题。

+   •

    注意力排序 [[45](https://arxiv.org/html/2405.11299v2#bib.bib45)] 通过将关键信息放在输入提示的末尾来解决这个问题。他们通过执行一步解码，按所收到的注意力（最高注意力在最后）对文档进行排序，重复这一过程，然后用新排序的上下文生成答案。尽管这种方法可以提高 A，但其局限性很明显：并非所有任务都可以映射到一组文档中，而且额外的排序增加了非平凡的开销，影响了 P。

+   •

    注意力桶 [[46](https://arxiv.org/html/2405.11299v2#bib.bib46)] 使用多个模型副本，每个副本在旋转位置嵌入上有不同的基本角度。这创建了独特的注意力波形，增强了 LLM 对各种上下文位置的意识。该解决方案适用于模型层和代理层。他们提高了 A，但因为需要多个副本处理输入提示，所以放弃了 P。

+   •

    中间发现 [[47](https://arxiv.org/html/2405.11299v2#bib.bib47)] 采取了更轻量的方法。他们发现中间丢失现象很可能由两个因素引起：一种是 LLM 在注意力中不成比例地偏向初始 token [[12](https://arxiv.org/html/2405.11299v2#bib.bib12)]，另一种是 RoPE 的长期衰减效应 [[16](https://arxiv.org/html/2405.11299v2#bib.bib16)]，该效应会降低远离但语义上有意义的 token 的注意力分数。他们的答案是多尺度位置编码（Ms-PoE），它为不同的注意力头分配不同的缩放比，以保留从预训练步骤中学到的信息，同时利用位置索引重新缩放来缓解长期衰减效应。这项工作属于模型层，并提高了 A，而没有增加额外的开销。

总之，在长**上下文**下改进**A**仍是一个需要密切审查的领域。一些初步的工作旨在提高长上下文推理和理解，但其中一些为了更好的**A**而牺牲了**P**。我们相信，需要更多的研究来同时提高**A**和**P**。

### 2.4 提高性能（P）

本节涵盖了那些显著提高**长上下文**服务的工作，这些工作在计算浮点运算和内存使用方面需求更多资源。从系统的角度来看，使用并行化或近似等原理来解决这些问题并不罕见。我们专注于三条专门提出的改进长上下文服务的工作：稀疏注意力、线性注意力和分布式加速。

稀疏注意力通过在每个注意力步骤中选择性地关注输入的子集来减少资源使用。线性注意力通过用一个将输入特征映射到低维空间的核函数来近似注意力计算，从而减少资源使用。两种技术都旨在减少传统注意力机制的二次复杂度。线性注意力通过降维实现，而稀疏注意力则使用选择性聚焦。当数据的不同部分重要性不均匀或序列具有自然局部性（如图像或结构化文本）时，稀疏注意力尤其有用。线性注意力更适用于需要压缩和高效处理整个数据的任务。分布式加速探索序列并行性以加快处理速度。我们建议读者参考[[4](https://arxiv.org/html/2405.11299v2#bib.bib4), [3](https://arxiv.org/html/2405.11299v2#bib.bib3)]获取改进**P**的一般优化方法，例如分页注意力[[8](https://arxiv.org/html/2405.11299v2#bib.bib8)]、闪存注意力[[48](https://arxiv.org/html/2405.11299v2#bib.bib48)]、KV 缓存[[49](https://arxiv.org/html/2405.11299v2#bib.bib49)]等。

#### 2.4.1 稀疏注意力

本节探讨了稀疏性，这是一种通过最小化冗余的$QK$乘法操作和减少内存使用来提高计算效率的方法。我们将稀疏性技术分为四种主要类型，基于两个基本方面。第一个方面与转换器架构有关。对于编码器-解码器架构，稀疏性被应用于选择性地忽略查询和键之间的较不重要的交互，从而帮助将计算资源集中在更重要的元素上。对于仅解码器架构，稀疏性被用于从键和值缓存中清除不重要的数据。第二个方面关注于识别查询和键之间哪些连接不重要的策略。这些策略分为动态和静态稀疏性两类[[50](https://arxiv.org/html/2405.11299v2#bib.bib50)]。动态稀疏性通过不断识别查询和键之间较不重要的连接并在运行时过滤相应的标记来适应输入序列。静态稀疏性则使用预先确定的稀疏模式来决定忽略哪些连接，简化了实现但可能牺牲适应性。

我们在表格[5](https://arxiv.org/html/2405.11299v2#S2.T5 "Table 5 ‣ 2.4.1 Sparse Attention ‣ 2.4 Improve Performance (P) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving")中比较了四个维度的代表性稀疏性工作。

+   •

    稀疏性策略：注意力矩阵的稀疏模式是否预定义（静态）或在推理过程中动态确定（动态，有时也称为学习）。

+   •

    模式策略：保留连接的组成部分（对应静态方法）和获取模式的技术（对应动态方法）。

+   •

    补偿：系统是否对丢弃的元素进行补偿。

+   •

    是否需要训练：稀疏性工作是否可以即插即用而无需训练。

以下讨论基于表格[4](https://arxiv.org/html/2405.11299v2#S2.T4 "Table 4 ‣ 2.4.1 Sparse Attention ‣ 2.4 Improve Performance (P) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving")进行组织。

表格 4：讨论矩阵。

|  | 编码器-解码器 | 仅解码器 |
| --- | --- | --- |
| 动态稀疏性 | (1) | (4) |
| 静态稀疏性 | (2) | (3) |

(1) 动态稀疏性 + 编码器-解码器。在 LLM（大语言模型）出现之前，编码器-解码器模型会根据输入查询和键动态调整注意力模式，包括算法工作如自适应稀疏变换器[[51](https://arxiv.org/html/2405.11299v2#bib.bib51)]、Sinkhorn 注意力[[52](https://arxiv.org/html/2405.11299v2#bib.bib52)]、路由变换器[[53](https://arxiv.org/html/2405.11299v2#bib.bib53)]、变换器[[54](https://arxiv.org/html/2405.11299v2#bib.bib54)]、地标注意力[[55](https://arxiv.org/html/2405.11299v2#bib.bib55)]，以及硬件加速器工作如$A^{3}$[[56](https://arxiv.org/html/2405.11299v2#bib.bib56)]、Spatten[[57](https://arxiv.org/html/2405.11299v2#bib.bib57)]、Sanger[[58](https://arxiv.org/html/2405.11299v2#bib.bib58)]、Dota[[59](https://arxiv.org/html/2405.11299v2#bib.bib59)]、Salo2[[50](https://arxiv.org/html/2405.11299v2#bib.bib50)]、Acceltran[[60](https://arxiv.org/html/2405.11299v2#bib.bib60)]、Fact[[61](https://arxiv.org/html/2405.11299v2#bib.bib61)]、Energon[[62](https://arxiv.org/html/2405.11299v2#bib.bib62)]和 Dtqatten[[63](https://arxiv.org/html/2405.11299v2#bib.bib63)]等。这些方法过滤掉无关的令牌，并根据输入或内部状态生成稀疏模式以进行关键的注意力计算。它们采用各种技术来确定运行时的稀疏模式，例如基于阈值修剪注意力矩阵、通过聚类识别查询的关键要素或采用 Top-k 修剪等。例如，路由变换器利用聚类来衡量键和查询之间的相似性，并为每个查询识别 Top-k 最相关的键。Sanger、Acceltran 和 Dtqatten 通过在近似分数矩阵中掩盖低于预定义阈值的元素来推导稀疏模式。

(2) 静态稀疏性 + 编码器-解码器。注意力机制的二次复杂性带来了沉重的计算和内存负担，特别是当内容长度非常长时。在长输入序列的场景中，动态稀疏性由于过滤或聚类查询和键的额外开销而导致效率问题。这促使了静态稀疏性的出现。像 Block-Bert [[64](https://arxiv.org/html/2405.11299v2#bib.bib64)]、Sparse transformer [[65](https://arxiv.org/html/2405.11299v2#bib.bib65)]、Longformer [[66](https://arxiv.org/html/2405.11299v2#bib.bib66)]、BigBird [[67](https://arxiv.org/html/2405.11299v2#bib.bib67)]、Star-transformer [[68](https://arxiv.org/html/2405.11299v2#bib.bib68)]、LongT5 [[69](https://arxiv.org/html/2405.11299v2#bib.bib69)]、LongNet [[70](https://arxiv.org/html/2405.11299v2#bib.bib70)]、Zebra [[71](https://arxiv.org/html/2405.11299v2#bib.bib71)] 以及某些硬件加速器如 Vitcod [[72](https://arxiv.org/html/2405.11299v2#bib.bib72)] 和 Salo [[73](https://arxiv.org/html/2405.11299v2#bib.bib73)] 采用了静态稀疏性策略。这些工作通过将注意力连接限制为预定义的稀疏模式（如块注意力、滑动窗口注意力、全局注意力、随机注意力和扩张注意力）来实现稀疏性。例如，Longformer 结合了滑动窗口注意力和全局注意力，以分别捕捉局部和长距离依赖。

(3) 静态稀疏性 + 仅解码器。现在在 LLM 时期，仅解码器架构的模型正变得主流。在仅解码器变换器的解码过程中，历史键值会被缓存以提高计算效率，因此稀疏性现在有利于逐出 KV 缓存中不重要的键和值。静态稀疏性仍然适用于仅解码器架构的模型。例如，LM-Infinite [[74](https://arxiv.org/html/2405.11299v2#bib.bib74)] 和 StreamingLLM [[12](https://arxiv.org/html/2405.11299v2#bib.bib12)] 缓存了起始令牌和最后 $L$ 个令牌的键值，只有缓存中的键值会被用来与当前查询进行注意力计算。

(4) 动态稀疏性 + 仅解码器。由于解码器-仅架构的单步解码的线性复杂度，动态稀疏性再次活跃。例如，FastGen [[75](https://arxiv.org/html/2405.11299v2#bib.bib75)] 在预填充阶段为每个注意力头选择适当的压缩策略，并根据解码阶段的压缩策略选择是否缓存新生成的标记的 KV 向量。 H2O [[76](https://arxiv.org/html/2405.11299v2#bib.bib76)] 和 Keyformer [[77](https://arxiv.org/html/2405.11299v2#bib.bib77)] 在运行时缓存了最后$L$个标记和注意力分数动态选择的重要标记的键和值向量。 SparQ Attention[[78](https://arxiv.org/html/2405.11299v2#bib.bib78)] 根据近似注意力分数消除不重要的键和值向量。为弥补消除的值向量，SparQ Attention 另外维护了所有消除的值向量的均值向量来计算注意力输出。 EasyKV [[79](https://arxiv.org/html/2405.11299v2#bib.bib79)] 通过基于本地注意力分数和鲁棒性度量的鲁棒缓存省略策略驱逐不重要的键和值向量。 LESS[[80](https://arxiv.org/html/2405.11299v2#bib.bib80)] 使用了基于 KV 缓存驱逐的低秩方法，学习了原始注意力输出和注意力输出的稀疏策略近似之间的残差差异，这是通过将根据驱逐策略丢弃的信息累积到一个恒定大小的低秩缓存或状态中来实现的，从而允许查询恢复丢失的信息。 InfLLM [[81](https://arxiv.org/html/2405.11299v2#bib.bib81)] 缓存了起始标记和最后$L$个标记的键和值，并通过查找表重新加载存储在外部存储器中的一些相关被驱逐的键和值向量。

表 5：稀疏性工作比较。

| 工作 | 稀疏性策略 | 模式策略 | 补偿 | 需要训练 |
| --- | --- | --- | --- | --- |
| Sparse Transformers [[65](https://arxiv.org/html/2405.11299v2#bib.bib65)] | 静态 | 本地 + 扩张 | ✗ | ✓ |
| Adaptively Transformers [[51](https://arxiv.org/html/2405.11299v2#bib.bib51)] | 动态 | Topk | ✗ | ✓ |
| Block Attention [[64](https://arxiv.org/html/2405.11299v2#bib.bib64)] | 静态 | 块 | ✗ | ✓ |
| ETC [[82](https://arxiv.org/html/2405.11299v2#bib.bib82)] | 静态 | 本地 + 全局 | ✗ | ✓ |
| BigBird  [[67](https://arxiv.org/html/2405.11299v2#bib.bib67)] | 静态 | 本地 + 全局 + 随机 | ✗ | ✓ |
| Longformer [[66](https://arxiv.org/html/2405.11299v2#bib.bib66)] | 静态 | 本地 + 全局 | ✗ | ✓ |
| Reformer [[54](https://arxiv.org/html/2405.11299v2#bib.bib54)] | 动态 | LSH | ✗ | ✓ |
| Sinkhorn Attention [[52](https://arxiv.org/html/2405.11299v2#bib.bib52)] | 动态 | 块 + 排序 | ✗ | ✓ |
| Routing Transformer [[53](https://arxiv.org/html/2405.11299v2#bib.bib53)] | 动态 | 聚类 | ✗ | ✓ |
| Star Transformer [[68](https://arxiv.org/html/2405.11299v2#bib.bib68)] | 静态 | 本地 + 全局 | ✗ | ✓ |
| LongT5 [[69](https://arxiv.org/html/2405.11299v2#bib.bib69)] | 静态 | 本地 + 全局 | ✓ | ✓ |
| LongNet [[70](https://arxiv.org/html/2405.11299v2#bib.bib70)] | 静态 | 膨胀 | ✗ | ✓ |
| Zebra [[71](https://arxiv.org/html/2405.11299v2#bib.bib71)] | 静态 | 本地或全局 | ✗ | ✓ |
| Landmark Attention [[55](https://arxiv.org/html/2405.11299v2#bib.bib55)] | 动态 | 块 + Topk | ✗ | ✓ |
| LM-Infinite [[74](https://arxiv.org/html/2405.11299v2#bib.bib74)] | 静态 | 本地 + 全局 | ✗ | ✓ |
| StreamingLLM [[12](https://arxiv.org/html/2405.11299v2#bib.bib12)] | 静态 | 本地 + 全局 | ✗ | ✗ |
| H2O [[76](https://arxiv.org/html/2405.11299v2#bib.bib76)] | 动态 | 本地 + Topk | ✗ | ✗ |
| Keyformer [[77](https://arxiv.org/html/2405.11299v2#bib.bib77)] | 动态 | 本地 + Topk | ✗ | ✗ |
| SparQ Attention [[78](https://arxiv.org/html/2405.11299v2#bib.bib78)] | 动态 | Topk | ✓ | ✗ |
| EasyKV [[79](https://arxiv.org/html/2405.11299v2#bib.bib79)] | 动态 | Topk | ✗ | ✗ |
| LESS [[80](https://arxiv.org/html/2405.11299v2#bib.bib80)] | 动态 | Topk | ✓ | ✓ |
| InfLLM [[81](https://arxiv.org/html/2405.11299v2#bib.bib81)] | 动态 | 本地 + Topk | ✗ | ✗ |

总结来说，稀疏性通过最小化冗余计算和内存使用来提高 P。该领域的大多数研究仅提高了 P，但可能会降低精度。StreamingLLM [[12](https://arxiv.org/html/2405.11299v2#bib.bib12)] 是一个例外，因为它通过启用无限上下文窗口和利用高效的注意力机制来同时实现 CP。我们认为，探索模型记忆、位置嵌入和稀疏性优化的组合将会很有趣。

#### 2.4.2 线性注意力

线性注意力将注意力机制的复杂度从关于序列长度的二次复杂度减少到线性复杂度。它通过一个核函数来近似注意力计算，该核函数将输入特征映射到一个低维空间，然后计算注意力分数。具体而言，它用其他函数代替 softmax 操作，例如，$sim(Q,K)=\phi(Q)\phi(K)^{T}$，并计算$\phi(Q)(\phi(K)^{T}V)$代替$sim(Q,K)V$，线性注意力将二次复杂度$O(n^{2}d)$降低到线性$O(nrd)$，其中$r$表示$\phi()$将$\mathbb{R}^{d}$映射到$\mathbb{R}^{r}$。在这个领域工作的如线性变换器 [[83](https://arxiv.org/html/2405.11299v2#bib.bib83)]、Performer [[84](https://arxiv.org/html/2405.11299v2#bib.bib84)] 和高效注意力 [[85](https://arxiv.org/html/2405.11299v2#bib.bib85)] 定义了不同的$\phi()$来近似 softmax 操作，而 Scatterbrain [[86](https://arxiv.org/html/2405.11299v2#bib.bib86)] 和 ViTALiTy [[87](https://arxiv.org/html/2405.11299v2#bib.bib87)]则进一步用来自 Reformer [[54](https://arxiv.org/html/2405.11299v2#bib.bib54)] 和 Sanger [[58](https://arxiv.org/html/2405.11299v2#bib.bib58)]的稀疏注意力来补偿低秩函数。例如，Performer 使用正交随机特征（PORF）作为低秩函数$\phi()$，而 Scatterbrain 则表明，将低秩线性注意力（通过 Performer 中的函数$\phi()$）与稀疏注意力（通过 Reformer 中的局部敏感哈希）结合起来，可以实现高效的近似，并且性能优于单独使用。

线性注意力和稀疏注意力都降低了传统注意力机制的二次复杂度。线性注意力通过降维实现这一点，而稀疏注意力则通过选择性关注来实现。两者都以 A 换取更好的 P。

#### 2.4.3 分布式加速

<svg class="ltx_picture" height="268.41" id="S2.F3.1.pic1" overflow="visible" version="1.1" width="701.17"><g transform="translate(0,268.41) matrix(1 0 0 -1 0 0) translate(180.92,0) translate(0,252.31)"><g fill="#000000" stroke="#000000" stroke-dasharray="0.5pt,2.0pt" stroke-dashoffset="0.0pt" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 -131 -3.11)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="262">在线标准化 [[88](https://arxiv.org/html/2405.11299v2#bib.bib88)]</foreignobject></g><g fill="#000000" stroke="#000000" stroke-dasharray="0.5pt,2.0pt" stroke-dashoffset="0.0pt" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 -175.96 -81.85)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="352.74">内存高效注意力 [[89](https://arxiv.org/html/2405.11299v2#bib.bib89)]</foreignobject></g><g fill="#000000" stroke="#000000" stroke-dasharray="0.5pt,2.0pt" stroke-dashoffset="0.0pt" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 79.28 -81.85)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="235.92">闪电注意力 [[48](https://arxiv.org/html/2405.11299v2#bib.bib48)]</foreignobject></g><g fill="#000000" stroke="#000000" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 -131.36 -160.59)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="264.25">块级并行变换器 [[90](https://arxiv.org/html/2405.11299v2#bib.bib90)]</foreignobject></g><g fill="#000000" stroke="#000000" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 81.06 -160.59)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="232.35">环形注意力 [[91](https://arxiv.org/html/2405.11299v2#bib.bib91)]</foreignobject></g><g fill="#000000" stroke="#000000" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 272.11 -160.59)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="243.94">爆发注意力 [[92](https://arxiv.org/html/2405.11299v2#bib.bib92)]</foreignobject></g><g fill="#000000" stroke="#000000" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 65.85 -239.33)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="262.38">条纹注意力 [[93](https://arxiv.org/html/2405.11299v2#bib.bib93)]</foreignobject></g><g fill="#000000" stroke="#000000" stroke-width="0.5pt" transform="matrix(1.0 0.0 0.0 1.0 284.29 -239.33)"><foreignobject height="12.45" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="219.59">距离注意力 [[94](https://arxiv.org/html/2405.11299v2#bib.bib94)]</foreignobject></g></g></svg>

图 3：使用序列并行的方法。灰色框未针对长上下文进行优化。

![参见说明](img/9df2a699c179d7d103da938773675ba1.png)

(a) Ring Attention 中计算单个解码器层的工作流程 [[91](https://arxiv.org/html/2405.11299v2#bib.bib91)]。它通过块状计算和计算与数据传输重叠来高效实现 SP。

![参考标题](img/ebb17c4cc7cc9df00a33d741a1bf8410.png)

(b) Striped Attention 中计算单个解码器层的工作流程 [[93](https://arxiv.org/html/2405.11299v2#bib.bib93)]。它通过标记置换优化 Ring Attention，从而降低因因果蒙版引起的 SP 节点负载不平衡。

图 4: 用于 LLM 服务预填充阶段的高效 SP-attention 机制。

![参考标题](img/1a659a5b01c2ef160b61ce311c78d792.png)

图 5: Dist Attention [[94](https://arxiv.org/html/2405.11299v2#bib.bib94), [95](https://arxiv.org/html/2405.11299v2#bib.bib95)], 为 LLM 服务的自回归解码阶段优化的 SP-attention 机制。在解码阶段，Q 长度为 1，KV 已经分布。

我们讨论了以分布式方式探索序列并行（SP）维度的工作。在这里，长上下文推理请求被分段为子序列并分布到节点上进行并行处理。虽然传统的分布策略如张量并行（TP）或流水线并行（PP）也可以增强推理性能，但我们在本调查中省略了它们，因为它们并非专门为长上下文处理而设计，通常作为 SP 优化的正交或互补。

我们的分析分为两步。首先，我们研究了使用 SP 加速单一长上下文请求的方法。其次，我们研究了加速集群用于服务长上下文请求的方法。

加速单一请求。

+   •

    图 [3](https://arxiv.org/html/2405.11299v2#S2.F3 "图 3 ‣ 2.4.3 分布式加速 ‣ 2.4 提高性能（P） ‣ 2 LLM 服务的 CAP 原则 ‣ LLM 服务的 CAP 原则：长上下文大语言模型服务的调查")展示了这一研究工作线的关系。这一研究工作可以追溯到在线标准化工作 [[88](https://arxiv.org/html/2405.11299v2#bib.bib88)]，这是一种数学上等价的用于块状 softmax 计算的方法，避免了实现完整的注意力矩阵 softmax$(QK^{T})$。这种方法是存储效率注意力的基础 [[89](https://arxiv.org/html/2405.11299v2#bib.bib89)]，以及它们的 CUDA 实现 [[48](https://arxiv.org/html/2405.11299v2#bib.bib48), [96](https://arxiv.org/html/2405.11299v2#bib.bib96)]。

+   •

    SP 首次由 Li 等人提出[[97](https://arxiv.org/html/2405.11299v2#bib.bib97)]，并广泛应用于 Megatron[[98](https://arxiv.org/html/2405.11299v2#bib.bib98)] 和 Deepspeed [[99](https://arxiv.org/html/2405.11299v2#bib.bib99)] 等分布式 LLM 训练框架中。在 LLM 服务系统的背景下，出现了新的挑战：（1）LLM 服务通常对延迟敏感，因此需要比 LLM 训练更小的批量大小；（2）LLM 服务具有自回归解码阶段，其中序列长度仅为一，但需要大量内存用于 KV 缓存存储；（3）LLM 服务通常依赖于大型融合内核以提高性能。尽管序列中每个 token 的前馈网络（FFN）计算是线性独立的，但注意力的计算则不是。因此，在使用 SP 计算分布式注意力时涉及大量的数据交换，从而为性能优化打开了重要的空间。

+   •

    Blockwise Parallel Transformer (BPT) [[90](https://arxiv.org/html/2405.11299v2#bib.bib90)] 将这一块状并行计算思想从自注意力扩展到自注意力和前馈网络（FFN）的融合。BPT 直接使用每个块的 Q 的注意力结果计算 FFN，而不需要完全实现注意力矩阵，从而减少了处理扩展上下文请求的内存需求。

+   •

    Ring Attention [[91](https://arxiv.org/html/2405.11299v2#bib.bib91)] 是 BPT 的后续工作，并将其适应于分布式环境。如图 [4(a)](https://arxiv.org/html/2405.11299v2#S2.F4.sf1 "In Figure 4 ‣ 2.4.3 Distributed Acceleration ‣ 2.4 Improve Performance (P) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving") 所示，它将块状注意力和 FFN 计算分布到设备上，实现主机之间键值块的圆形模式并发通信。该设置将通信与查询-键-值块和 FFN 的计算重叠，从而提高效率。Striped Attention [[93](https://arxiv.org/html/2405.11299v2#bib.bib93)] 通过解决因因果遮罩引起的分布式节点负载不平衡问题，优化了 Ring Attention，如图 [4(b)](https://arxiv.org/html/2405.11299v2#S2.F4.sf2 "In Figure 4 ‣ 2.4.3 Distributed Acceleration ‣ 2.4 Improve Performance (P) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving") 所示。Burst Attention [[92](https://arxiv.org/html/2405.11299v2#bib.bib92)] 通过将 FlashAttention 的切片优化整合到每个节点的计算中，并引入全局优化器进行分布式协调，进一步增强了 Ring Attention。Dist Attention [[94](https://arxiv.org/html/2405.11299v2#bib.bib94)] 针对自回归解码阶段专门优化了 Ring Attention，如图 [5](https://arxiv.org/html/2405.11299v2#S2.F5 "Figure 5 ‣ 2.4.3 Distributed Acceleration ‣ 2.4 Improve Performance (P) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving") 所示，其中查询长度为 1。在解码阶段，Q 长度为 1，KV 已经在序列并行节点之间分布。

加速集群。

+   •

    在部署长上下文服务时，系统会遇到不同上下文长度的请求。这种多样性给 LLM 服务系统带来了重大挑战，不同请求的计算和内存需求可能差异巨大。两个并行的工作，Infinite-LLM [[94](https://arxiv.org/html/2405.11299v2#bib.bib94)] 和 LoongServe [[95](https://arxiv.org/html/2405.11299v2#bib.bib95)]，通过类似的思路解决了这个挑战：它们利用 SP 将不同上下文长度的请求分割成较小的、可管理的片段，并将这些片段分布到整个集群中进行调度。

+   •

    Infinite-LLM [[94](https://arxiv.org/html/2405.11299v2#bib.bib94)] 引入了 Dist Attention，这是一种为自回归解码阶段优化的 SP 注意力机制。此外，Infinite-LLM 还包含一个全局内存管理器，该管理器在请求片段之间协调集群的内存分配，考虑到一致性约束和碎片化问题。

+   •

    LoongServe [[95](https://arxiv.org/html/2405.11299v2#bib.bib95)] 则提出了弹性序列并行（ESP），以动态调整推断请求的并行度，并具有最小的开销。ESP 促成了两种优化策略：（1）在预填充阶段之后降低序列并行度，并在解码阶段保持较低的并行度，因为该阶段需要的计算量较少（每个自回归步骤）；（2）在自回归阶段随着序列长度的增长增加序列并行度，当 LLM 预计生成较长的输出序列时，这一点尤为有前途。

总之，现有的工作在从单个请求或集群的角度来看，都大大提高了长上下文服务的 P。我们还发现了一些值得探索的潜在未来方向。首先，虽然这些系统工作对长上下文模型而言是通用的，但它们的优化方法与上层模型级别的优化没有协同效应，甚至可能相互矛盾。例如，优化 SP 节点负载平衡的注意力机制可能在上下文稀疏的情况下表现不佳。其次，据我们了解，尚未对代理层技术和分布式加速系统之间的联合设计进行任何努力。例如，在请求的分布式推断之后，其“内存”分散在多个节点之间，这给代理系统收集和过滤这些信息带来了挑战。最后，同样，没有研究是否以及如何加速模型内存线工作（见 §[2.2](https://arxiv.org/html/2405.11299v2#S2.SS2 "2.2 Improve Context (C) ‣ 2 CAP for LLM Serving ‣ The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving")）与 SP。

### 2.5 改进上下文和性能（CP）

本节讨论了可以同时提高 C 和 P 的工作。要一箭双雕确实具有挑战性，我们已经确定了一条工作路线：提示压缩。

#### 2.5.1 提示压缩

表 6：比较提示压缩工作。

| 类型 | 工作 |
| --- | --- |
| Block-Box | 选择性上下文 [[100](https://arxiv.org/html/2405.11299v2#bib.bib100)], LLMLingua [[101](https://arxiv.org/html/2405.11299v2#bib.bib101)], LongLLMLingua [[102](https://arxiv.org/html/2405.11299v2#bib.bib102)], LLMLingua2 [[103](https://arxiv.org/html/2405.11299v2#bib.bib103)] |
| White-Box | Gist-Token [[104](https://arxiv.org/html/2405.11299v2#bib.bib104)], PCCC [[105](https://arxiv.org/html/2405.11299v2#bib.bib105)], ICAE [[106](https://arxiv.org/html/2405.11299v2#bib.bib106)], AutoCompressor [[32](https://arxiv.org/html/2405.11299v2#bib.bib32)] |

提示压缩在保持关键信息的同时减少给定提示的长度，以便服务系统能够处理更长的上下文。请记住，我们根据用户感知的度量标准来确定 C 和 P 是否已经满足。我们将这种方法归类为 CP，因为它可以在提示输入模型之前缩短用户提供的提示，从而改善用户感知的上下文长度和性能。我们根据 LLM 模型是否被用作黑箱或白箱来分类工作。

+   •

    黑箱压缩。LLMLingua [[101](https://arxiv.org/html/2405.11299v2#bib.bib101)]观察到自然语言中的显著冗余，并提出了一套通过去除标记来压缩提示的方法。它使用标记级别的迭代算法来压缩提示。这样做可以通过考虑标记之间的条件依赖关系来保留提示中的关键信息。LongLLMLingua [[102](https://arxiv.org/html/2405.11299v2#bib.bib102)] 基于 LLMLingua 构建，添加了问题感知压缩，通过添加对比困惑度来捕捉标记相对于问题的分布变化。LLMLingua2 [[103](https://arxiv.org/html/2405.11299v2#bib.bib103)] 更进一步，它针对任务无关的提示压缩。它使用 GPT-4 从原始提示生成压缩文本，并使用二分类分类器来删除不需要的标记。

+   •

    白箱压缩。这类工作将以某种方式修改模型架构以实现压缩。然后他们通过软提示 [[35](https://arxiv.org/html/2405.11299v2#bib.bib35)] 输入压缩的提示。Gist tokens [[104](https://arxiv.org/html/2405.11299v2#bib.bib104)] 修改了变换器注意力掩码，使 LLM 能够将提示压缩成较小的“要点”标记集，这些标记可以缓存并重复使用以提高计算效率，从而改善 C 和 P。另一个工作，PCCC [[105](https://arxiv.org/html/2405.11299v2#bib.bib105)]，向 LLM 添加了可训练的软提示权重。他们的见解是，用于条件 LLM 的提示可以由一组精心选择的权重来近似表示。他们的目标是训练软提示权重，使其尽可能接近固定的硬提示。ICAE [[106](https://arxiv.org/html/2405.11299v2#bib.bib106)] 采取了不同的方法。它由 2 个模块组成：一个从 LLM 适配的可学习编码器，使用 LoRA 将长上下文编码到少量内存槽中，以及一个固定解码器，即 LLM 本身，其中代表原始上下文的内存槽被用于与提示互动以实现各种目标。最后，基于 RMT 架构的 AutoCompressor [[32](https://arxiv.org/html/2405.11299v2#bib.bib32)] 构建了一个分段级别的总结标记来压缩提示。

总结来说，有多种压缩提示的方法。可以将 LLM 视为一个黑箱，使用一套方法在发送给黑箱 LLM 之前压缩提示。或者，也可以修改模型架构以实现有效压缩。提示压缩改善用户感知的 C 和 P。

### 2.6 提升上下文和准确性（CA）

本节讨论了可以同时改善 C 和 A 的工作。我们确定了一项工作线：代理记忆，它在代理层管理记忆。

#### 2.6.1 代理记忆

扩展服务系统的上下文长度和性能的一种方法是通过隐式管理代理层内的记忆和提示。我们将这种方法称为代理记忆。它属于 CA，因为它可以在固定上下文模型上创造无限上下文的错觉，并反映过去的记忆以提高未来任务的准确性，从而改善用户感知的 C 和 A。代理记忆与之前讨论的模型记忆不同，代理记忆在代理内部操作记忆和提示，而模型记忆在模型内部操作记忆。它们不是相互矛盾的解决方案，而是互补的。例如，可以在模型记忆工作如 Infini-Attention [[33](https://arxiv.org/html/2405.11299v2#bib.bib33)]上运行一个代理记忆工作如 MemGPT [[107](https://arxiv.org/html/2405.11299v2#bib.bib107)]。

表 7：比较代理记忆工作。

| 工作 | 在线记忆管理 | 离线记忆反思 |
| --- | --- | --- |
| MemWalker [[108](https://arxiv.org/html/2405.11299v2#bib.bib108)] | ✓ | / |
| WebGPT [[109](https://arxiv.org/html/2405.11299v2#bib.bib109)] | ✓ | / |
| MemGPT [[107](https://arxiv.org/html/2405.11299v2#bib.bib107)] | ✓ | / |
| TheSim [[110](https://arxiv.org/html/2405.11299v2#bib.bib110)] | ✓ | ✓ |
| ChatDev [[111](https://arxiv.org/html/2405.11299v2#bib.bib111)] | ✓ | ✓ |
| MetaGPT [[112](https://arxiv.org/html/2405.11299v2#bib.bib112)] | ✓ | ✓ |
| Self-Refine [[113](https://arxiv.org/html/2405.11299v2#bib.bib113)] | ✓ | ✓ |
| Reflexion [[114](https://arxiv.org/html/2405.11299v2#bib.bib114)] | ✓ | ✓ |
| MLCopilot [[115](https://arxiv.org/html/2405.11299v2#bib.bib115)] | ✓ | ✓ |

我们讨论了代理记忆工作在两个维度上的表现。

+   •

    在线记忆管理：它表示解决方案是否可以实时根据智能体的过去记忆、外部知识和当前用户提示动态构建提供给模型的提示。它需要机制从过去的记忆中提取相关信息，并构建提示。MemWalker [[108](https://arxiv.org/html/2405.11299v2#bib.bib108)]、WebGPT [[109](https://arxiv.org/html/2405.11299v2#bib.bib109)] 和 MemGPT [[107](https://arxiv.org/html/2405.11299v2#bib.bib107)] 是这一领域的开创性工作。特别是，MemGPT 在固定上下文模型的基础上提供了无限上下文的假象。它构建了一个多层次的层级和一套在当前构建的提示与外部过去记忆之间交换记忆的机制。因此，它隐性地提高了 C。

+   •

    离线记忆反射：它表示解决方案是否可以反思智能体的过去记忆以学习经验、提炼知识、删除不必要的句子等。它需要读取和写入过去记忆的机制。许多基于智能体的应用程序在离线时采用这一机制，以提高未来任务的服务准确性 [[114](https://arxiv.org/html/2405.11299v2#bib.bib114), [113](https://arxiv.org/html/2405.11299v2#bib.bib113)]。例如，ChatDev [[111](https://arxiv.org/html/2405.11299v2#bib.bib111)]、Generative Agents [[110](https://arxiv.org/html/2405.11299v2#bib.bib110)] 和 MLCopilot [[115](https://arxiv.org/html/2405.11299v2#bib.bib115)] 中的智能体定期反思，将过去的记忆综合成更高层次的知识，以提高未来任务的准确性。结合起来，具有特征的智能体记忆提高了 C 和 A。

总结来说，智能体记忆有三个关键特征：在线记忆管理和离线记忆反射。前者符合 C，后者符合 A。如果在此基础上加入提示压缩，智能体记忆接近 CAP。

## 3 结论

我们认为，除了拥有高质量的模型外，以合理的低成本大规模部署和服务模型，并且不降低准确性同样重要。我们调查了 LLM 服务领域，以了解在对长上下文服务需求日益增长的背景下，成本效益与准确性之间复杂的动态关系。我们的发现揭示了该领域的研究在以下三个 distinct 但相互冲突的目标之间进行优化：提高服务上下文长度（C）、提高服务准确性（A）以及提高服务性能（P）。我们提出了 CAP 原则，即任何给定的 LLM 服务优化最多只能在上述三个目标中的两个上取得改进。我们仔细审视了相关文献，并发现现有的工作可以归入这一类别。展望未来，我们希望这一原则能够帮助设计师理解在构建大规模服务系统时固有的动态权衡。

## 参考文献

+   [1] Meredith Ringel Morris, Jascha Sohl-dickstein, Noah Fiedel, Tris Warkentin, Allan Dafoe, Aleksandra Faust, Clement Farabet 和 Shane Legg. AGI 的各个层次：在通向 AGI 的道路上实施进展。arXiv 预印本 arXiv:2311.02462, 2023。

+   [2] THE AI INDEX REPORT. [`aiindex.stanford.edu/report/`](https://aiindex.stanford.edu/report/)。

+   [3] Mengwei Xu, Wangsong Yin, Dongqi Cai, Rongjie Yi, Daliang Xu, Qipeng Wang, Bingyang Wu, Yihao Zhao, Chen Yang, Shihe Wang 等. 资源效率的 LLM 和多模态基础模型调查。arXiv 预印本 arXiv:2401.08092, 2024。

+   [4] Zixuan Zhou, Xuefei Ning, Ke Hong, Tianyu Fu, Jiaming Xu, Shiyao Li, Yuming Lou, Luning Wang, Zhihang Yuan, Xiuhong Li 等. 大型语言模型高效推理调查。arXiv 预印本 arXiv:2404.14294, 2024。

+   [5] Khaled Saab, Tao Tu, Wei-Hung Weng, Ryutaro Tanno, David Stutz, Ellery Wulczyn, Fan Zhang, Tim Strother, Chunjong Park, Elahe Vedadi 等. Gemini 模型在医学中的能力。arXiv 预印本 arXiv:2404.18416, 2024。

+   [6] Reiner Pope, Sholto Douglas, Aakanksha Chowdhery, Jacob Devlin, James Bradbury, Jonathan Heek, Kefan Xiao, Shivani Agrawal 和 Jeff Dean. 高效扩展 Transformer 推理。机器学习与系统论文集，5, 2023。

+   [7] Nelson F Liu, Kevin Lin, John Hewitt, Ashwin Paranjape, Michele Bevilacqua, Fabio Petroni 和 Percy Liang. 在中间迷失：语言模型如何使用长上下文。计算语言学学会交易，12:157–173, 2024。

+   [8] Woosuk Kwon, Zhuohan Li, Siyuan Zhuang, Ying Sheng, Lianmin Zheng, Cody Hao Yu, Joseph Gonzalez, Hao Zhang 和 Ion Stoica. 使用 pagedattention 的大型语言模型服务的高效内存管理。在第 29 届操作系统原理研讨会论文集中，页码 611–626, 2023。

+   [9] TensorRT LLM. [`github.com/NVIDIA/TensorRT-LLM`](https://github.com/NVIDIA/TensorRT-LLM)。

+   [10] Zihang Dai, Zhilin Yang, Yiming Yang, Jaime Carbonell, Quoc V Le 和 Ruslan Salakhutdinov. Transformer-xl: 超越固定长度上下文的注意力语言模型。arXiv 预印本 arXiv:1901.02860, 2019。

+   [11] Yilong Zhao, Chien-Yu Lin, Kan Zhu, Zihao Ye, Lequn Chen, Size Zheng, Luis Ceze, Arvind Krishnamurthy, Tianqi Chen 和 Baris Kasikci. Atom: 高效且准确的 LLM 服务的低位量化。arXiv 预印本 arXiv:2310.19102, 2023。

+   [12] Guangxuan Xiao, Yuandong Tian, Beidi Chen, Song Han 和 Mike Lewis. 具有注意力消耗的高效流式语言模型, 2023。

+   [13] Gyeong-In Yu, Joo Seong Jeong, Geon-Woo Kim, Soojeong Kim 和 Byung-Gon Chun. Orca: 用于 $\{$Transformer-Based$\}$ 生成模型的分布式服务系统。在第 16 届 USENIX 操作系统设计与实施研讨会（OSDI 22）上，页码 521–538, 2022。

+   [14] Cunchen Hu, Heyang Huang, Liangliang Xu, Xusheng Chen, Jiang Xu, Shuang Chen, Hao Feng, Chenxi Wang, Sa Wang, Yungang Bao, 等等. 无干扰推理：混合下游工作负载的非集成 LLM 推理。arXiv 预印本 arXiv:2401.11181, 2024。

+   [15] Matei Zaharia, Omar Khattab, Lingjiao Chen, Jared Quincy Davis, Heather Miller, Chris Potts, James Zou, Michael Carbin, Jonathan Frankle, Naveen Rao, 和 Ali Ghodsi. 从模型到复合 AI 系统的转变。 [`bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/`](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/), 2024。

+   [16] Jianlin Su, Yu Lu, Shengfeng Pan, Bo Wen, 和 Yunfeng Liu. Roformer：增强的带旋转位置嵌入的变换器。《CoRR》，abs/2104.09864, 2021。

+   [17] Xunyu Zhu, Jian Li, Yong Liu, Can Ma, 和 Weiping Wang. 大型语言模型的模型压缩调查。arXiv 预印本 arXiv:2308.07633, 2023。

+   [18] Wikipedia. CAP 定理。 [`en.wikipedia.org/wiki/CAP_theorem`](https://en.wikipedia.org/wiki/CAP_theorem), 2024。

+   [19] Zhengxiao Du, Aohan Zeng, Yuxiao Dong, 和 Jie Tang. 从损失视角理解语言模型的突现能力。arXiv 预印本 arXiv:2403.15796, 2024。

+   [20] Rylan Schaeffer, Brando Miranda, 和 Sanmi Koyejo. 大型语言模型的突现能力是否只是海市蜃楼？《神经信息处理系统进展》，36, 2024。

+   [21] Google. Spanner, truetime 和 CAP 定理。 [`storage.googleapis.com/gweb-research2023-media/pubtools/pdf/45855.pdf`](https://storage.googleapis.com/gweb-research2023-media/pubtools/pdf/45855.pdf), 2017。

+   [22] Saurav Pawar, SM Tonmoy, SM Zaman, Vinija Jain, Aman Chadha, 和 Amitava Das. 大型语言模型中上下文长度扩展技术的何、为什么及如何——详细调查。arXiv 预印本 arXiv:2401.07872, 2024。

+   [23] Zican Dong, Tianyi Tang, Lunyi Li, 和 Wayne Xin Zhao. 基于变换器的长文本建模调查。arXiv 预印本 arXiv:2302.14502, 2023。

+   [24] Xindi Wang, Mahsa Salmani, Parsa Omidi, Xiangyu Ren, Mehdi Rezagholizadeh, 和 Armaghan Eshaghi. 超越极限：大型语言模型中扩展上下文长度的技术调查。arXiv 预印本 arXiv:2402.02244, 2024。

+   [25] Zhiheng Xi, Wenxiang Chen, Xin Guo, Wei He, Yiwen Ding, Boyang Hong, Ming Zhang, Junzhe Wang, Senjie Jin, Enyu Zhou, 等等. 基于大型语言模型的智能体的崛起与潜力：一项调查。arXiv 预印本 arXiv:2309.07864, 2023。

+   [26] Yunfan Gao, Yun Xiong, Xinyu Gao, Kangxiang Jia, Jinliu Pan, Yuxi Bi, Yi Dai, Jiawei Sun, 和 Haofen Wang. 大型语言模型的检索增强生成：一项调查。arXiv 预印本 arXiv:2312.10997, 2023。

+   [27] Jack W Rae, Anna Potapenko, Siddhant M Jayakumar, 和 Timothy P Lillicrap. 用于长序列建模的压缩变换器。arXiv 预印本 arXiv:1911.05507, 2019。

+   [28] Yuhuai Wu、Markus N Rabe、DeLesley Hutchins 和 Christian Szegedy。《记忆变换器》。arXiv 预印本 arXiv:2203.08913，2022 年。

+   [29] Qingyang Wu、Zhenzhong Lan、Kun Qian、Jing Gu、Alborz Geramifard 和 Zhou Yu。《Memformer：一种用于序列建模的记忆增强变换器》。arXiv 预印本 arXiv:2010.06891，2020 年。

+   [30] Mikhail S Burtsev、Yuri Kuratov、Anton Peganov 和 Grigory V Sapunov。《记忆变换器》。arXiv 预印本 arXiv:2006.11527，2020 年。

+   [31] Aydar Bulatov、Yury Kuratov 和 Mikhail Burtsev。《递归记忆变换器》。神经信息处理系统进展，35:11079–11091，2022 年。

+   [32] Alexis Chevalier、Alexander Wettig、Anirudh Ajith 和 Danqi Chen。《将语言模型调整为压缩上下文》。arXiv 预印本 arXiv:2305.14788，2023 年。

+   [33] Tsendsuren Munkhdalai、Manaal Faruqui 和 Siddharth Gopal。《不留任何上下文：具有无限注意力的高效无限上下文变换器》。arXiv 预印本 arXiv:2404.07143，2024 年。

+   [34] Yizhou Shan、Yutong Huang、Yilun Chen 和 Yiying Zhang。《LegoOS：一种分布式、分散式操作系统，用于硬件资源解耦》。在第 13 届 USENIX 操作系统设计与实现研讨会 (OSDI 18) 上，页码 69–87，加利福尼亚州卡尔斯巴德，2018 年 10 月。USENIX 协会。

+   [35] Brian Lester、Rami Al-Rfou 和 Noah Constant。《参数高效提示调整的规模效应》。arXiv 预印本 arXiv:2104.08691，2021 年。

+   [36] Ofir Press、Noah A. Smith 和 Mike Lewis。《训练短，测试长：具有线性偏置的注意力实现输入长度外推》，2022 年。

+   [37] Yutao Sun、Li Dong、Barun Patra、Shuming Ma、Shaohan Huang、Alon Benhaim、Vishrav Chaudhary、Xia Song 和 Furu Wei。《长度可外推的变换器》，2022 年。

+   [38] Guanzheng Chen、Xin Li、Zaiqiao Meng、Shangsong Liang 和 Lidong Bing。《Clex：大型语言模型的连续长度外推》，2024 年。

+   [39] Shouyuan Chen、Sherman Wong、Liangjian Chen 和 Yuandong Tian。《通过位置插值扩展大型语言模型的上下文窗口》，2023 年。

+   [40] bloc97。《Ntk-aware scaled rope 允许 LLaMA 模型具有扩展的 (8k+) 上下文大小，无需任何微调且最小困惑度降级》，2023 年。 [`www.reddit.com/r/LocalLLaMA/comments/14lz7j5/ntkaware_scaled_rope_allows_llama_models_to_have/,D`](https://www.reddit.com/r/LocalLLaMA/comments/14lz7j5/ntkaware_scaled_rope_allows_llama_models_to_have/,D)，最后访问时间：2023-12-19。

+   [41] Bowen Peng、Jeffrey Quesnelle、Honglu Fan 和 Enrico Shippole。《Yarn：高效的上下文窗口扩展大型语言模型》，2023 年。

+   [42] Shanda Li、Chong You、Guru Guruganesh、Joshua Ainslie、Santiago Ontanon、Manzil Zaheer、Sumit Sanghai、Yiming Yang、Sanjiv Kumar 和 Srinadh Bhojanapalli。《相对位置的功能插值提升了长上下文变换器》，2024 年。

+   [43] Yiran Ding、Li Lyna Zhang、Chengruidong Zhang、Yuanyuan Xu、Ning Shang、Jiahang Xu、Fan Yang 和 Mao Yang。《Longrope：扩展 LLM 上下文窗口超过 200 万个标记》，2024 年。

+   [44] Dawei Zhu, Nan Yang, Liang Wang, Yifan Song, Wenhao Wu, Furu Wei, 和 Sujian Li。Pose：通过位置跳跃训练高效扩展 llms 的上下文窗口，2024。

+   [45] Alexander Peysakhovich 和 Adam Lerer。注意力排序对抗长上下文语言模型中的近期偏差。arXiv 预印本 arXiv:2310.01427，2023。

+   [46] Yuhan Chen, Ang Lv, Ting-En Lin, Changyu Chen, Yuchuan Wu, Fei Huang, Yongbin Li, 和 Rui Yan。强化注意力中的最短音符：增强大型语言模型的上下文意识以有效使用工具。arXiv 预印本 arXiv:2312.04455，2023。

+   [47] Zhenyu Zhang, Runjin Chen, Shiwei Liu, Zhewei Yao, Olatunji Ruwase, Beidi Chen, Xiaoxia Wu, 和 Zhangyang Wang。发现于中间：语言模型如何通过即插即用的位置编码更好地使用长上下文。arXiv 预印本 arXiv:2403.04797，2024。

+   [48] Tri Dao, Dan Fu, Stefano Ermon, Atri Rudra, 和 Christopher Ré。Flashattention：快速且内存高效的精确注意力与 io 感知。神经信息处理系统进展，35:16344–16359，2022。

+   [49] Lianmin Zheng, Liangsheng Yin, Zhiqiang Xie, Jeff Huang, Chuyue Sun, Cody Hao Yu, Shiyi Cao, Christos Kozyrakis, Ion Stoica, Joseph E Gonzalez, 等。使用 sglang 高效编程大型语言模型。arXiv 预印本 arXiv:2312.07104，2023。

+   [50] Jieru Zhao, Pai Zeng, Guan Shen, Quan Chen, 和 Minyi Guo。硬件-软件协同设计实现静态和动态稀疏注意力机制。IEEE 集成电路与系统计算机辅助设计学报，页码 1–1，2024。

+   [51] Gonçalo M. Correia, Vlad Niculae, 和 André F. T. Martins。自适应稀疏变换器，2019。

+   [52] Yi Tay, Dara Bahri, Liu Yang, Donald Metzler, 和 Da-Cheng Juan。稀疏 Sinkhorn 注意力，2020。

+   [53] Aurko Roy, Mohammad Saffar, Ashish Vaswani, 和 David Grangier。高效基于内容的稀疏注意力与路由变换器。计算语言学学会会刊，9:53–68，2021。

+   [54] Nikita Kitaev, Łukasz Kaiser, 和 Anselm Levskaya。Reformer：高效的变换器，2020。

+   [55] Amirkeivan Mohtashami 和 Martin Jaggi。Landmark attention：变换器的随机访问无限上下文长度，2023。

+   [56] Tae Jun Ham, Sung Jun Jung, Seonghak Kim, Young H. Oh, Yeonhong Park, Yoonho Song, Jung-Hun Park, Sanghee Lee, Kyoung Park, Jae W. Lee, 和 Deog-Kyoon Jeong。A³：通过近似加速神经网络中的注意力机制，2020。

+   [57] Hanrui Wang, Zhekai Zhang, 和 Song Han。Spatten：具有级联标记和头部剪枝的高效稀疏注意力架构，2021。

+   [58] Liqiang Lu, Yicheng Jin, Hangrui Bi, Zizhang Luo, Peng Li, Tao Wang, 和 Yun Liang。Sanger：一个用于启用稀疏注意力的可重构架构的协同设计框架。MICRO-54：第 54 届 IEEE/ACM 微架构国际研讨会，2021。

+   [59] 郑屈、刘雷、涂风斌、陈兆东、丁雨飞和谢远。Dota：检测并省略弱注意力以加速可扩展变换器。第 27 届 ACM 国际编程语言与操作系统体系结构支持会议论文集，2022。

+   [60] Shikhar Tuli 和 Niraj K. Jha。Acceltran：一个关注稀疏性的加速器，用于动态推断的变换器，2023。

+   [61] 秦玉彬、王杨、邓大正、赵志仁、杨晓龙、刘磊波、魏少俊、胡杨和尹寿义。Fact：Ffn-attention 共同优化的变换器架构，具备积极的相关性预测。第 50 届国际计算机架构年会论文集，2023。

+   [62] 周哲、刘俊林、顾振宇和孙广宇。Energon：利用动态稀疏注意力实现变换器的高效加速。IEEE 集成电路与系统计算机辅助设计汇刊，42(1):136–149，2023。

+   [63] 杨涛、李冬跃、宋卓然、赵毅龙、刘芳欣、王宗武、贺哲之和江丽。Dtqatten：利用动态基于令牌的量化提高注意力架构的效率。2022 年欧洲设计、自动化与测试会议暨展览（DATE），第 700–705 页，2022。

+   [64] 邱杰中、马昊、奥默尔·莱维、斯科特·伊赫、王四农和唐洁。区块自注意力用于长文档理解。ArXiv，abs/1911.02972，2019。

+   [65] 雷温·柴尔德、斯科特·格雷、阿列克·拉德福德和伊利亚·苏茨克维尔。利用稀疏变换器生成长序列，2019。

+   [66] 伊兹·贝尔塔吉、马修·E·彼得斯和阿尔曼·科汉。Longformer：长文档变换器，2020。

+   [67] 曼齐尔·扎希尔、古鲁·古鲁加内什、库马尔·阿维纳瓦·杜贝、乔舒亚·安斯利、克里斯·阿尔伯提、圣地亚哥·翁塔农、菲利普·范、阿尼鲁德·拉瓦拉、王启凡、杨力和阿姆尔·艾哈迈德。Big bird：适用于更长序列的变换器。在 H. 拉罗谢尔、M. 兰扎托、R. 哈德塞尔、M.F. 巴尔坎和 H. 林编，神经信息处理系统进展，第 33 卷，第 17283–17297 页。Curran Associates, Inc.，2020。

+   [68] 郭启鹏、邱希鹏、刘鹏飞、邵云帆、薛向阳和张郑。Star-transformer，2022。

+   [69] 曼迪·郭、乔舒亚·安斯利、大卫·乌瑟斯、圣地亚哥·翁塔农、纪建模、云轩·孙和尹飞。LongT5：高效的文本到文本变换器用于长序列。在 Marine Carpuat、Marie-Catherine de Marneffe 和 Ivan Vladimir Meza Ruiz 编，计算语言学协会会议成果：NAACL 2022，第 724–736 页，美国西雅图，2022 年 7 月。计算语言学协会。

+   [70] 丁佳玉、马树铭、董力、张兴兴、黄绍瀚、王文辉、郑南宁和魏富如。Longnet：将变换器扩展到 1,000,000,000 个标记，2023。

+   [71] 宋开强、王晓杨、曹尚武、潘晓曼和董钰。Zebra：通过层次分组的本地-全局注意力扩展上下文窗口，2023。

+   [72] 尤浩然，孙展义，石慧洪，俞中智，赵阳，张永安，李超建，李宝璞，林盈燕。《Vitcod：通过专用算法和加速器共同设计加速视觉变换器》，2022 年。

+   [73] 关申，赵洁如，陈全，冷靖雯，李超，郭敏义。《Salo：一种高效的空间加速器，实现长序列的混合稀疏注意力机制》，2022 年。

+   [74] 韩驰，王其凡，彭浩，熊文汉，陈宇，季恒，王思农。《Lm-infinite：大型语言模型的零样本极端长度泛化》，2023 年。

+   [75] 叶苏宇，张云南，刘利远，张敏佳，韩佳伟，高剑锋。《模型告诉你该丢弃什么：针对 LLMs 的自适应 KV 缓存压缩》，2024 年。

+   [76] 张振宇，盛颖，周天怡，陈天龙，郑连敏，蔡瑞思，宋钊，田元东，克里斯托弗·瑞，克拉克·巴雷特，王章扬，陈贝迪。《H[2]o：大型语言模型高效生成推理的重型预言机》，2023 年。

+   [77] 穆罕默德·阿德南，阿基尔·阿伦库马尔，古拉夫·贾因，普拉尚特·J·奈尔，伊利亚·索洛维奇克，普鲁索瑟姆·卡马特。《Keyformer：通过关键令牌选择减少 KV 缓存以实现高效生成推理》，2024 年。

+   [78] 卢卡·里巴尔，伊万·切隆比耶夫，卢克·哈德拉斯-加利，查理·布莱克，卡洛·卢斯基，道格拉斯·奥尔。《Sparq 注意力：带宽高效的 LLM 推理》，2024 年。

+   [79] 任思雨，朱肯尼·Q。《关于键值受限生成语言模型推理的驱逐策略的有效性》，2024 年。

+   [80] 唐哈利，杨欣瑜，张振宇，王章扬，池悦杰，陈贝迪。《用更少获得更多：通过 KV 缓存压缩合成递归以高效 LLM 推理》，2024 年。

+   [81] 萧超军，张鹏乐，韩旭，肖光轩，林彦凯，张正燕，刘智源，韩松，孙茂松。《Infllm：揭示 LLMs 在无需训练的记忆下理解极长序列的内在能力》，2024 年。

+   [82] 乔舒亚·安斯利，圣地亚哥·翁塔农，克里斯·阿尔贝尔蒂，瓦茨拉夫·茨维切克，扎卡里·费舍尔，菲利普·范，阿尼鲁德·拉武拉，苏密特·桑海，王其凡，杨利。《ETC：在变压器中编码长结构化输入》。在邦妮·韦伯，特雷弗·科恩，赫玉兰，刘杨编，《2020 年自然语言处理经验方法会议论文集，EMNLP 2020》，在线，2020 年 11 月 16-20 日，页面 268–284。计算语言学协会，2020 年。

+   [83] 安吉洛斯·卡萨罗普洛斯，阿普尔夫·维亚斯，尼古劳斯·帕帕斯，弗朗索瓦·弗吕雷。《变压器即循环神经网络：具有线性注意力的快速自回归变压器》。发表于国际机器学习会议，页面 5156–5165。PMLR，2020 年。

+   [84] 克日什托夫·乔罗曼斯基，瓦列里·利霍舍尔斯托夫，大卫·多汉，宋星友，安德里亚·加内，塔马什·萨尔洛什，彼得·霍金斯，贾雷德·戴维斯，阿夫罗兹·莫希丁，卢卡什·凯泽等。《重新思考表演者的注意力》。arXiv 预印本 arXiv:2009.14794，2020 年。

+   [85] 朱然·申, 明源·张, 亥宇·赵, 帅毅, 和 洪生·李. 高效注意力: 具有线性复杂度的注意力. 在 IEEE/CVF 计算机视觉应用冬季会议论文集中, 页码 3531–3539, 2021.

+   [86] 陈北蒂, 戴三, 埃里克·温索, 赵松, 阿特里·鲁德拉, 和 克里斯托弗·雷. Scatterbrain: 统一稀疏和低秩注意力. 神经信息处理系统进展, 34:17413–17426, 2021.

+   [87] 乔提克里希纳·达斯, 尚吴, 许洪·石, 朝剑·李, 之凡·叶, 钟峰·王, 和 盈彦·林. Vitality: 统一低秩和稀疏近似以加速视觉变换器，采用线性泰勒注意力. 在 2023 IEEE 国际高性能计算架构研讨会 (HPCA) 上, 页码 415–428. IEEE, 2023.

+   [88] 马克西姆·米拉科夫 和 纳塔利亚·吉梅尔谢因. 软最大函数的在线归一化计算. arXiv 预印本 arXiv:1805.02867, 2018.

+   [89] 马库斯·N·拉贝 和 查尔斯·斯塔茨. 自注意力不需要 $O(n^{2})$ 内存. arXiv 预印本 arXiv:2112.05682, 2021.

+   [90] 刘浩 和 皮特·阿贝尔. 用于大上下文模型的块状并行变换器. 神经信息处理系统进展, 36, 2024.

+   [91] 刘浩, 马特伊·扎哈里亚, 和 皮特·阿贝尔. 使用块状变换器的环状注意力以适应接近无限的上下文. arXiv 预印本 arXiv:2310.01889, 2023.

+   [92] 孙傲, 韦林·赵, 徐汉, 程杨, 祁源·刘, 船石, 毛松·孙, 盛南·王, 和 滕苏. Burstattention: 用于极长序列的高效分布式注意力框架. arXiv 预印本 arXiv:2403.09347, 2024.

+   [93] 威廉·布兰登, 阿尼鲁达·努鲁西玛, 凯文·钱, 扎卡里·安克纳, 田进, 施叶宋, 和 乔纳森·拉根-凯利. 条纹注意力: 为因果变换器提供更快的环状注意力. arXiv 预印本 arXiv:2311.09431, 2023.

+   [94] 林彬, 彭涛, 张晨, 孙敏敏, 兰博·李, 韩宇·赵, 温聪·肖, 徐琦, 邱夏飞, 申力, 等. Infinite-llm: 通过 distattention 和分布式 kvcache 提供长上下文的高效 llm 服务. arXiv 预印本 arXiv:2401.02669, 2024.

+   [95] 吴炳洋, 刘胜宇, 钟银敏, 孙鹏, 刘轩哲, 和 辛金. Loongserve: 通过弹性序列并行高效服务长上下文的大语言模型. arXiv 预印本 arXiv:2404.09526, 2024.

+   [96] 戴三. Flashattention-2: 更快的注意力，具有更好的并行性和工作分区. arXiv 预印本 arXiv:2307.08691, 2023.

+   [97] 李胜贵, 褚召雪, 查伊坦亚·巴拉纳瓦尔, 李永宾, 和 杨有. 序列并行: 从系统角度看长序列训练. arXiv 预印本 arXiv:2105.13120, 2021.

+   [98] 维贾伊·安南德·科尔蒂坎提, 贾里德·卡斯珀, 桑克格·林姆, 劳伦斯·麦卡菲, 迈克尔·安德申, 穆罕默德·肖伊比, 和 布莱恩·卡坦扎罗. 减少大型变换器模型中的激活重计算. 机器学习与系统会议论文集, 5, 2023.

+   [99] Sam Ade Jacobs, Masahiro Tanaka, Chengming Zhang, Minjia Zhang, Leon Song, Samyam Rajbhandari, 和 Yuxiong He. Deepspeed ulysses: 用于**极长序列**变换器模型训练的系统优化。arXiv 预印本 arXiv:2309.14509，2023 年。

+   [100] Yucheng Li. 解锁 LLMs 的上下文限制：通过**自我信息**基于内容过滤提升 LLMs 的上下文效率。CoRR, abs/2304.12102，2023 年。

+   [101] Huiqiang Jiang, Qianhui Wu, Chin-Yew Lin, Yuqing Yang, 和 Lili Qiu. Llmlingua: 压缩提示以加速**大语言模型**的推理。arXiv 预印本 arXiv:2310.05736，2023 年。

+   [102] Huiqiang Jiang, Qianhui Wu, Xufang Luo, Dongsheng Li, Chin-Yew Lin, Yuqing Yang, 和 Lili Qiu. Longllmlingua: 通过提示压缩加速和增强**长上下文**场景中的 LLMs。arXiv 预印本 arXiv:2310.06839，2023 年。

+   [103] Zhuoshi Pan, Qianhui Wu, Huiqiang Jiang, Menglin Xia, Xufang Luo, Jue Zhang, Qingwei Lin, Victor Rühle, Yuqing Yang, Chin-Yew Lin 等. Llmlingua-2: **任务无关**提示压缩的数据蒸馏，用于高效和真实。arXiv 预印本 arXiv:2403.12968，2024 年。

+   [104] Jesse Mu, Xiang Li, 和 Noah Goodman. 学习使用**要旨令牌**压缩提示。神经信息处理系统进展，36，2024 年。

+   [105] David Wingate, Mohammad Shoeybi, 和 Taylor Sorensen. 提示压缩与对比条件以控制性和毒性减少。编辑：Yoav Goldberg, Zornitsa Kozareva, 和 Yue Zhang，**计算语言学协会**EMNLP 2022 发现，页 5621–5634，阿布扎比，阿联酋，2022 年 12 月。计算语言学协会。

+   [106] Tao Ge, Jing Hu, Xun Wang, Si-Qing Chen, 和 Furu Wei. **大语言模型**中的上下文压缩的上下文自编码器。CoRR, abs/2307.06945，2023 年。

+   [107] Charles Packer, Vivian Fang, Shishir G Patil, Kevin Lin, Sarah Wooders, 和 Joseph E Gonzalez. Memgpt: 朝着**操作系统**的 LLMs 迈进。arXiv 预印本 arXiv:2310.08560，2023 年。

+   [108] Howard Chen, Ramakanth Pasunuru, Jason Weston, 和 Asli Celikyilmaz. 漫步记忆迷宫：通过**互动阅读**超越上下文限制。arXiv 预印本 arXiv:2310.05029，2023 年。

+   [109] Reiichiro Nakano, Jacob Hilton, Suchir Balaji, Jeff Wu, Long Ouyang, Christina Kim, Christopher Hesse, Shantanu Jain, Vineet Kosaraju, William Saunders 等. Webgpt: 带有人类反馈的浏览器辅助问答。arXiv 预印本 arXiv:2112.09332，2021 年。

+   [110] Joon Sung Park, Joseph O’Brien, Carrie Jun Cai, Meredith Ringel Morris, Percy Liang, 和 Michael S Bernstein. 生成代理：**人类行为**的互动模拟体。在第 36 届 ACM 用户界面软件与技术年会论文集中，页 1–22，2023 年。

+   [111] Chen Qian, Xin Cong, Cheng Yang, Weize Chen, Yusheng Su, Juyuan Xu, Zhiyuan Liu, 和 Maosong Sun. **软件开发**的交流代理。arXiv 预印本 arXiv:2307.07924，2023 年。

+   [112] Sirui Hong, Xiawu Zheng, Jonathan Chen, Yuheng Cheng, Jinlin Wang, Ceyao Zhang, Zili Wang, Steven Ka Shing Yau, Zijuan Lin, Liyang Zhou 等人. Metagpt：用于多代理协作框架的元编程。arXiv 预印本 arXiv:2308.00352，2023。

+   [113] Aman Madaan, Niket Tandon, Prakhar Gupta, Skyler Hallinan, Luyu Gao, Sarah Wiegreffe, Uri Alon, Nouha Dziri, Shrimai Prabhumoye, Yiming Yang 等人. 自我精炼：通过自我反馈的迭代改进。神经信息处理系统进展，36，2024。

+   [114] Noah Shinn, Federico Cassano, Ashwin Gopinath, Karthik Narasimhan 和 Shunyu Yao. Reflexion：具有语言强化学习的语言代理。神经信息处理系统进展，36，2024。

+   [115] Lei Zhang, Yuge Zhang, Kan Ren, Dongsheng Li 和 Yuqing Yang. Mlcopilot：在解决机器学习任务中释放大型语言模型的力量。arXiv 预印本 arXiv:2304.14979，2023。

生成于 2024 年 5 月 24 日 13:44:53，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/) 生成。
