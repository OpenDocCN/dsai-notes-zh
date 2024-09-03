<!--yml

类别：未分类

日期：2024-09-03 17:30:59

-->

# 关于 LLM 指令调优的数据选择综述

> 来源：[`arxiv.org/html/2402.05123`](https://arxiv.org/html/2402.05123)

1.  [1 介绍](https://arxiv.org/html/2402.05123v1#S1 "1 介绍 ‣ 关于 LLM 指令调优的数据选择综述")

1.  [2 指令集](https://arxiv.org/html/2402.05123v1#S2 "2 指令集 ‣ 关于 LLM 指令调优的数据选择综述")

1.  [3 数据选择方法](https://arxiv.org/html/2402.05123v1#S3 "3 数据选择方法 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [3.1 基于指标系统的方法](https://arxiv.org/html/2402.05123v1#S3.SS1 "3.1 基于指标系统的方法 ‣ 3 数据选择方法 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [3.2 基于可训练 LLM 的方法](https://arxiv.org/html/2402.05123v1#S3.SS2 "3.2 基于可训练 LLM 的方法 ‣ 3 数据选择方法 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [3.3 基于强大 LLM（如 ChatGPT）的方法](https://arxiv.org/html/2402.05123v1#S3.SS3 "3.3 基于强大 LLM（如 ChatGPT）的方法 ‣ 3 数据选择方法 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [3.4 基于小模型的方法](https://arxiv.org/html/2402.05123v1#S3.SS4 "3.4 基于小模型的方法 ‣ 3 数据选择方法 ‣ 关于 LLM 指令调优的数据选择综述")

1.  [4 评估方法与结果分析](https://arxiv.org/html/2402.05123v1#S4 "4 评估方法与结果分析 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [4.1 胜率](https://arxiv.org/html/2402.05123v1#S4.SS1 "4.1 胜率 ‣ 4 评估方法与结果分析 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [4.2 内部比较](https://arxiv.org/html/2402.05123v1#S4.SS2 "4.2 内部比较 ‣ 4 评估方法与结果分析 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [4.3 外部比较](https://arxiv.org/html/2402.05123v1#S4.SS3 "4.3 外部比较 ‣ 4 评估方法与结果分析 ‣ 关于 LLM 指令调优的数据选择综述")

    1.  [4.4 结果分析](https://arxiv.org/html/2402.05123v1#S4.SS4 "4.4 结果分析 ‣ 4 评估方法与结果分析 ‣ 关于 LLM 指令调优的数据选择综述")

1.  [5 结论与开放挑战](https://arxiv.org/html/2402.05123v1#S5 "5 结论与开放挑战 ‣ 关于 LLM 指令调优的数据选择综述")

HTML 转换有时会出现[显示错误](https://info.dev.arxiv.org/about/accessibility_html_error_messages.html)，这是由于内容从源文件转换时出现了问题。本文使用了以下 HTML 转换工具尚不支持的包。对这些问题的反馈并不必要；它们已知并正在处理之中。

+   失败：forest

作者：通过遵循这些[最佳实践](https://info.arxiv.org/help/submit_latex_best_practices.html)，从您的 LaTeX 提交中获得最佳 HTML 结果。

许可证：CC BY 4.0arXiv:2402.05123v1 [cs.CL] 2024 年 2 月 4 日

# 关于 LLM 指令调优的数据选择调查

Jiahao Wang${}^{1,2}$ 平等贡献和共享共同第一作者。    Bolin Zhang${}^{1}$ ${}^{*}$    Qianlong Du${}^{2}$    Jiajun Zhang${}^{2}$ 通讯作者。    Dianhui Chu${}^{1}$

${}^{1}$哈尔滨工业大学

${}^{2}$中国科学院自动化研究所

jiahaowang0917@gmail.com，{brolin, chudh}@hit.edu.cn，{qianlong.du,jjzhang}@nlpr.ia.ac.cn

###### 摘要

指令调优是训练大型语言模型（LLM）的关键步骤，因此如何提升指令调优的效果受到了越来越多的关注。现有研究表明，在 LLM 的指令调优过程中，数据集的质量比数量更为重要。因此，最近许多研究集中于探索从指令数据集中选择高质量子集的方法，旨在降低训练成本并提升 LLM 的指令跟随能力。本文对 LLM 指令调优的数据选择进行了全面调查。首先，我们介绍了广泛使用的指令数据集。接着，我们提出了一种新的数据选择方法分类，并详细介绍了近期进展，同时详细阐述了数据选择方法的评估策略和结果。最后，我们强调了开放挑战，并展示了该任务的新前沿。

## 1 引言

大型语言模型（例如 PaLMChowdhery 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib5)），GPT-4 OpenAI（[2023](https://arxiv.org/html/2402.05123v1#bib.bib15)）和 LLaMa Touvron 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib24)））在广泛的语言理解和生成任务中展现了卓越的能力，能够有效且安全地遵循人类指令。在训练过程中，LLMs 通常涉及两个基本步骤 Ouyang 等人（[2022a](https://arxiv.org/html/2402.05123v1#bib.bib16)）：在大规模语料库上进行预训练，在指令数据集上进行微调。在这些步骤中，指令数据集上的微调，也称为指令微调，在将 LLMs 与人类指令对齐方面发挥了至关重要的作用。通过在（指令，输出）数据集上训练 LLMs，指令微调有效地弥合了 LLMs 与各种人类意图之间的差距 Zhang 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib31)）。具体而言，指令微调可以使 LLMs 的输出更符合人类偏好，从而增强 LLMs 的可控性和安全性。另一个好处是，指令微调可以使大型模型更快地适应特定领域或学习专门知识，而不需要大量的计算资源和架构更改。

在早期研究中，指令微调的工作主要集中在构建大规模指令数据集，创建指令数据集可以通过两种主要方式完成。一种是通过模板将现有标注自然语言数据集中的文本-标签对转换为指令-输出对，例如 P3Sanh 等人（[2022](https://arxiv.org/html/2402.05123v1#bib.bib20)）。另一种方法是使用如 GPT-3.5-Turbo 这样的 LLMs 为给定的指令生成输出，例如 self-instructWang 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib25)）。尽管已经通过多种方法创建了各种大规模指令数据集，但它们在数量、多样性和创造性方面往往存在限制。此外，如何提升在大规模指令数据集上的指令跟随能力和处理意外回应的能力，仍是一个需要解决的当前问题。

因此，选择合适的数据集对于指令微调阶段至关重要。虽然指令微调主要依赖于大量数据，但如 LIMAZhou 等人（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib33)）的研究表明，数据质量比数量更为关键。他们展示了仅使用 1000 条高质量指令数据在 LLMs 中取得了显著的性能提升。这一发现表明，LLMs 在预训练阶段已经获得了世界知识，而指令微调阶段仅需少量高质量的指令数据即可生成高质量的回应。

手动指令数据选择通常涉及高成本并引入人为偏差。因此，创建自动化方法以高效选择指令数据变得至关重要。然而，由于涉及复杂的因素和多维度的考虑，这项任务具有挑战性。例如，很难评估单个指令的质量并确保所选数据的整体多样性。另一个挑战是降低成本并提高选择过程的效率。鉴于这些因素，已经开发了各种数据选择方法。一些方法使用指标系统来评估单个数据点，而其他方法依赖于可训练的 LLMs 或强大的外部 LLMs。这些方法利用 LLMs 自身的能力来选择指令。此外，使用较小模型并设计全面流程以在各方面实现平衡效果的方法也值得关注。这些方法已显示出令人鼓舞的结果。例如，IFDLi 等人（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib10)）的方法通过仅使用约 5%的 Alpaca 数据集显著优于 Alpaca 模型，并且也比 WizardLM 模型高出约 10%。使用高质量子集进行微调不仅提升了 LLMs 的指令跟随能力，而且显著降低了计算成本和时间。

{forest}

分叉边缘，树= grow=east，reversed=true，anchor=base west，parent anchor=east，child anchor=west，base=left，font=，矩形，draw=hidden-draw，圆角，align=left，minimum width=4em，edge+=darkgray，line width=1pt，s sep=3pt，inner xsep=2pt，inner ysep=3pt，line width=0.8pt，ver/.style=rotate=90，child anchor=north，parent anchor=south，anchor=center， ，where level=1text width=6em,font=，，where level=2text width=6em,font=，，where level=3text width=8em,font=，，where level=4text width=5em,font=，， [ 数据选择用于指令调优，ver [指令

集 (§[2](https://arxiv.org/html/2402.05123v1#S2 "2 指令集 ‣ 数据选择的调查")) [ Alpaca Taori 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib23)），WizardLM Xu 等人（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib28)），

Dolly-v2 Conover 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib6)），P3 Sanh 等人（[2022](https://arxiv.org/html/2402.05123v1#bib.bib20)），

LIMA Zhou 等人（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib33)），自我指令 Wang 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib25)），leaf, text width=37em ] ] [数据选择

方法 (§[3](https://arxiv.org/html/2402.05123v1#S3 "3 数据选择方法 ‣ 数据选择的调查")) [系统

指标

(§[3.1](https://arxiv.org/html/2402.05123v1#S3.SS1 "3.1 基于指标系统的方法 ‣ 3 数据选择方法 ‣ LLM 指令调优的数据选择调查")) [ INSTRUCTMINING Cao 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib1)），InstructionGPT-4 Wei 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib26)），

DQ Zhou 等（[2023b](https://arxiv.org/html/2402.05123v1#bib.bib34)），，leaf，文本宽度=37em ] ] [可训练

LLMs (§[3.2](https://arxiv.org/html/2402.05123v1#S3.SS2 "3.2 基于可训练 LLM 的方法 ‣ 3 数据选择方法 ‣ LLM 指令调优的数据选择调查")) [ IFD Li 等（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib10)），指令回译 Li 等（[2023b](https://arxiv.org/html/2402.05123v1#bib.bib11)），

Nuggets Li 等（[2023c](https://arxiv.org/html/2402.05123v1#bib.bib12)），DIVERSEEVOL Wu 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib27)），

TEGIT Chen 等（[2023c](https://arxiv.org/html/2402.05123v1#bib.bib4)），ActiveIT Kung 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib9)），leaf，文本宽度=37em ] ] [强大

LLMs (§[3.3](https://arxiv.org/html/2402.05123v1#S3.SS3 "3.3 基于强大 LLM（如 ChatGPT）的方法 ‣ 3 数据选择方法 ‣ LLM 指令调优的数据选择调查")) [ AlpaGasus Chen 等（[2023b](https://arxiv.org/html/2402.05123v1#bib.bib3)），INSTAG Lu 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib14)），LIFT Xu 等（[2023b](https://arxiv.org/html/2402.05123v1#bib.bib29)），

DEITA Liu 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib13)），tree-instruct Zhao 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib32)），WaveCoder Yu 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib30)），leaf，文本宽度=37em ] ] [小型

模型 (§[3.4](https://arxiv.org/html/2402.05123v1#S3.SS4 "3.4 基于小型模型的方法 ‣ 3 数据选择方法 ‣ LLM 指令调优的数据选择调查")) [ MoDS Du 等（[2023](https://arxiv.org/html/2402.05123v1#bib.bib8)），基于核心集的选择 Chen 等（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib2)），，leaf，文本宽度=37em ] ] ] [评估

方法 (§[4](https://arxiv.org/html/2402.05123v1#S4 "4 评估方法和结果分析 ‣ LLM 指令调优的数据选择调查")) [ 胜率 (§[4.1](https://arxiv.org/html/2402.05123v1#S4.SS1 "4.1 胜率 ‣ 4 评估方法和结果分析 ‣ LLM 指令调优的数据选择调查"))，内部比较 (§[4.2](https://arxiv.org/html/2402.05123v1#S4.SS2 "4.2 内部比较 ‣ 4 评估方法和结果分析 ‣ LLM 指令调优的数据选择调查"))，外部比较 (§[4.3](https://arxiv.org/html/2402.05123v1#S4.SS3 "4.3 外部比较 ‣ 4 评估方法和结果分析 ‣ LLM 指令调优的数据选择调查"))，leaf，文本宽度=37em ] ] ] ]

图 1：LLM 指令调优的数据选择概述。

本文全面回顾了现有的 LLM 指令调优数据选择方法。为了便利社区，我们维护了一个论文列表¹¹1[`github.com/Bolin97/awesome-instruction-selector`](https://github.com/Bolin97/awesome-instruction-selector)，收集常用的数据选择指令集。第[2](https://arxiv.org/html/2402.05123v1#S2 "2 Instruction Sets ‣ A Survey on Data Selection for LLM Instruction Tuning")节描述了用于指令调优的不同来源和构建方法的主流数据集，第[3](https://arxiv.org/html/2402.05123v1#S3 "3 Data Selection methods ‣ A Survey on Data Selection for LLM Instruction Tuning")节详细描述了四种数据选择方法：指标集、可训练的 LLMs、强大的 LLMs 和小模型。第[4](https://arxiv.org/html/2402.05123v1#S4 "4 Evaluation methods and Result Analysis ‣ A Survey on Data Selection for LLM Instruction Tuning")节介绍了评估方法，并展示了不同指令选择方法的结果。第[5](https://arxiv.org/html/2402.05123v1#S5 "5 Conclusions and Open Challenges ‣ A Survey on Data Selection for LLM Instruction Tuning")节总结了论文内容，并强调了指令选择中的开放挑战和未来方向。

## 2 指令集

各种指令调优数据集（例如 Self-Instruct 和 Alpaca），由 LLMs 生成，提供了大量样本而无需人工劳动，但数据质量依赖于 LLMs 的性能且不确定。相对而言，人工筛选的数据集（例如 LIMA 和 Dolly）通过细致的人为选择获得更高的质量，但可能受到人为偏见的影响。替代的数据集构建方法，如 prompt mapping 和 evol-instruct，旨在提升数据集的质量和多样性，但引入了质量保证的新挑战。数据集构建和来源的这种变异性显著影响了数据质量，突显了仔细数据选择对 LLM 指令调优的重要性。本节描述了几种常见的指令调优数据集的规模和构建程序。

自我指令，由 Wang 等人创建（[2023](https://arxiv.org/html/2402.05123v1#bib.bib25)），包含 52,000 个训练指令和 252 个测试指令。初始指令从种子任务中选取，通过 InstructGPT Ouyang 等人（[2022b](https://arxiv.org/html/2402.05123v1#bib.bib17)）进行分类和多样化，生成输入和输出，采用先输出或先输入的策略。后处理精炼了数据集的独特性和相关性，为自然语言处理应用提供了多功能的资源。

Alpaca，由 Taori 等人创建（[2023](https://arxiv.org/html/2402.05123v1#bib.bib23)），包含 52,002 个样本，用于微调 LLaMA 以提高指令跟随能力。根据 Wang 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib25)）的方法，样本是通过使用 text-davinci-003 生成的。

WizardLM，由 Xu 等人创建（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib28)），包含 250,000 个样本，由进化算法生成。使用了两种算法（深度进化和广度进化）来增强基础指令的复杂性和范围，通过 ChatGPT 生成更复杂和多样化的高质量指令数据。

LIMA，由 Zhou 等人创建（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib33)），包含 1,000 个训练样本、300 个测试样本和 50 个开发样本。除了手动编写的样本外，还严格挑选了从问答网站收集的样本。尽管规模较小，LIMA 因其细致的编纂和设计而脱颖而出。基于 LIMA 微调的 LLM 在跟随指令和适应未知任务方面表现出显著能力。

Dolly-v2，由 Conover 等人创建（[2023](https://arxiv.org/html/2402.05123v1#bib.bib6)），包含 15,000 个指令，涉及各种任务如头脑风暴、分类、问答和总结。员工手动编写（提示，响应）对。他们被限制仅使用维基百科，并被建议不要使用网络来源或生成型 AI 来编写响应。

P3，由 Sanh 等人创建（[2022](https://arxiv.org/html/2402.05123v1#bib.bib20)），整合了 170 个 NLP 数据集和 2,052 个提示。这些提示，也称为任务模板，将传统的 NLP 任务（如问答或文本分类）转换为自然语言的输入输出对。P3 数据集本身由从 PromptSource 中随机选择的提示组成，并将数据组织成输入、答案选项和目标的三元组。

## 3 数据选择方法

正式地，定义一个指令数据集 $X$，其大小为 $n$，其中 $X=\{x_{1},x_{2},\dots,x_{n}\}$，每个 $x_{i}$ 代表一个指令微调数据实例。为了从 $X$ 中采用特定的指令数据选择方法 $\pi$ 并选择一个大小为 $m$ 的子集 $S_{\pi}^{(m)}$，Liu 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib13)）接着使用预定义的评估指标 $Q$ 来评估 $S_{\pi}^{(m)}$ 的质量。通过评估指标测量获得的子集质量，可以评估所选指令数据选择方法的有效性。设计选择方法的过程可以表示为：

|  | $S^{(m)}_{\pi}=\pi\left(X\right)$ |  | (1) |
| --- | --- | --- | --- |
|  | $\pi^{*}=\arg\max_{\pi}Q\left(S^{(m)}_{\pi}\right)$ |  | (2) |

教学数据选择方法的分类基于该方法使用的评分规则和所采用的模型基础。这些方法可以分为以下四类：基于指标系统的方法、可训练的 LLMs、像 ChatGPT 这样的强大 LLMs 和小型模型。

### 3.1 基于指标系统的方法

使用指标集系统的方法直接识别多个指标 $I_{1},I_{2},\dots,I_{n}$，从而建立全面的指标集。该集合中的每个指标由特定的计算公式定义。值得注意的是，某些指标可能利用深度学习技术从数据集中提取特征，这些本质上是指标形式。这些指标有助于计算数据实例的个体分数，记作 $score_{ij}=I_{i}(x_{j})$。这些分数随后在开发更强大的指标集系统中起到关键作用。

|  | $score_{j}=G\left(I_{1}(x_{j}),I_{2}(x_{j}),\dots,I_{n}(x_{j})\right)$ |  | (3) |
| --- | --- | --- | --- |

一旦建立，指标集系统可以直接用于计算数据集中每个数据实例的分数。通过建立合适的阈值，该系统有助于根据各自的分数选择数据：

|  | $S_{\pi}=\{x\|G(x)>\tau\}$ |  | (4) |
| --- | --- | --- | --- |

曹等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib1)）介绍了 INSTRUCTMINING，这是一种基于线性规则的方法，用于评估教学数据的质量。该方法最初识别了关键的自然语言指标，如指令长度、困惑度、奖励分数、KNN-iReimers 和 Gurevych（[2019](https://arxiv.org/html/2402.05123v1#bib.bib19)）；Dong 等人（[2011](https://arxiv.org/html/2402.05123v1#bib.bib7)），等。这些指标随后用于建立线性方程。为了探讨数据质量与这些指标之间的关联，并定义方程的参数，进行了全面的微调实验。不同质量的数据集被划分为子集，组合后用于大规模模型的微调。每个子集的质量标签通过评估模型在测试集上的表现得出。最小二乘法被应用于这些实验结果，以估算 INSTRUCTMINING 中的参数。这涉及将线性方程拟合到评估模型在测试集上的损失。一旦参数确定，这个公式就可以用来计算指令的质量，从而促进数据选择。

Wei 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib26)) 提出了 InstructionGPT-4，一种用于多模态大模型微调的数据选择方法。它在各种评估中优于 MiniGPT-4Zhu 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib35))，且使用的数据更少。第一步，使用 CLIP ScoreRadford 等人 ([2021](https://arxiv.org/html/2402.05123v1#bib.bib18))、指令长度等指标。视觉和文本数据被编码成向量，然后进行降维，这被视为特殊指标。这些指标被组合成一个向量 $e$。然后，将该向量输入到一个可训练的数据选择器中，如多层感知器或自注意力网络。这种方法类似于 Cao 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib1)) 在计算质量标签时，采用聚类算法对数据集进行分割。在每个子集的微调和评估后分配质量标签。

Zhou 等人 ([2023b](https://arxiv.org/html/2402.05123v1#bib.bib34)) 介绍了 DQ 方法，这是一种用于大规模计算机视觉数据集的创新数据压缩技术，但它也已被调整用于 LLM 领域。该方法涉及几个关键步骤：最初，定义增益函数 $P(x)$，

|  | $P(x)=\sum_{p\in S}&#124;&#124;f(p)-f(x)&#124;&#124;^{2}_{2}-\sum_{p\in D\setminus S}&#124;&#124;f(p)-f(x)&#124;&#124;^% {2}_{2}$ |  | (5) |
| --- | --- | --- | --- |

结合特征函数 $f(.)$ —— 类似于度量 —— 并使用当前子集 $S$ 和整个数据集 $D$。该增益函数本质上形成了一个度量集函数 $G(.)$。然后，数据集被迭代地划分为不重叠的子集，按照增益函数的指导以最大化定义的增益。随后，从每个子集中均匀地选择一个代表性样本，以确保覆盖整个数据集，同时优化数据的多样性。这种方法优先考虑保持数据集的整体多样性。

### 3.2 基于可训练 LLM 的方法

本节概述了使用可训练的 LLM（如 LLaMa）来开发数据选择过程中的计算公式。LLM 作为可训练的数据选择器，处理并为每条指令微调数据分配分数。

|  | $score_{i}=LLM_{trainable}(x_{i})$ |  | (6) |
| --- | --- | --- | --- |

这种方法不仅关注分析单个指令，还强调同步数据选择与用于微调的大模型功能的必要性。后续章节将详细说明具体方法。

Li 等人 ([2023a](https://arxiv.org/html/2402.05123v1#bib.bib10)) 提出了 IFD 方法。该方法假设 LLM 可以通过精心挑选的数据初步学习识别指令，从而提升其评估更广泛数据集质量和估计指令跟随难度的能力。最初，该方法涉及对 LLM 进行微调，使用一个小的、聚类的指令数据集，以培养基本的指令跟随技能。然后引入了一个新的度量指标“指令跟随难度（IFD）”，用于评估响应特定指令的挑战。IFD 比较在没有特定指令情况下的响应质量。条件答案得分定义为：

|  | $s_{\theta}(A&#124;Q)=\frac{1}{N}\sum_{i=1}^{n}logP(w_{i}&#124;Q,w_{1},\dots,w_{i-1})$ |  | (7) |
| --- | --- | --- | --- |

该得分评估模型在指令后（Q）与正确答案的对齐情况，考虑了生成答案（A）的影响。最终的 IFD 为：

|  | $r_{\theta}(Q,A)=\frac{s_{\theta}(A&#124;Q)}{s_{\theta}(A)}$ |  | (8) |
| --- | --- | --- | --- |

IFD 得分量化了模型在每个样本上的挑战。通过设置 IFD 得分阈值，可以选择特定的指令进行初始 LLM 预训练，从而得到一个经过优化的模型。

Li 等人 ([2023b](https://arxiv.org/html/2402.05123v1#bib.bib11)) 提出了指令回译（Instruction Backtranslation）方法，用于生成和筛选指令。该方法从一个基线指令跟随模型和一个网络语料库开始，模型为每个网络文档生成指令，形成一个数据集。然后，模型用种子指令进行微调，以获得基本能力。它还会自动对每个指令进行评分，将那些超过设定阈值的指令形成高分子集，以进行进一步微调。这个迭代过程提高了指令生成和筛选的效率。

Li 等人 ([2023c](https://arxiv.org/html/2402.05123v1#bib.bib12)) 提出了 Nuggets 框架，该框架采用了双阶段方法。最初，使用多种预定义任务评估 LLM 在多个场景中的能力，这一过程被称为零-shot 评分。随后，指令数据集中的每个条目作为独特的提示进行一次性使用。这些提示在预定义任务之前呈现，并重新评估 LLM 的表现，这一步称为一次性评分。该方法利用一次性和零-shot 评分之间的差异，为每个指令计算一个明确的“黄金得分”。获得所有指令的黄金得分后，选择那些组成最高得分子集的指令作为“黄金子集”。然后直接使用该子集进行模型的微调。该方法利用了大规模模型固有的上下文学习能力。

Wu 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib27)) 介绍了 DIVERSEEVOL 机制，这是一种创新的迭代数据选择策略。它利用像 LLaMa 这样的大规模模型生成用于指导数据的嵌入向量。该机制使用了 k-center-greedy 算法 Sener 和 Savarese ([2018a](https://arxiv.org/html/2402.05123v1#bib.bib21)) 来促进选择数据子集的多样性，以便对 LLaMa 模型进行微调。该过程被反复应用，逐步扩大所选子集，最终创建一个高质量的指导数据集。

Chen 等人 ([2023c](https://arxiv.org/html/2402.05123v1#bib.bib4)) 提出了 TEGIT 方法，提供了一种生成优质指令微调数据的新方法。特别值得注意的是他们的数据筛选方法。利用 ChatGPT，将小型文档语料库转换为适合指导数据的格式，形成一个元数据集。该数据集随后用于训练两个 Llama2 模型——一个作为任务生成器，另一个作为任务鉴别器。生成器的角色是从提供的文本中设计任务，而鉴别器评估这些任务，以确保其质量。

Kung 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib9)) 提出了 Active Instruction Tuning，这是一种独特的方法，专注于任务敏感性选择，旨在通过使用更少的任务来增强大模型的微调，同时提高任务之外的泛化能力。该技术引入了 Prompt Uncertainty 的概念，该概念通过随机删除原始指令中的单词生成 k 个扰动指令来确定。然后，对这些 k 个扰动指令的 LLM 概率偏差进行平均。表现出较高 Prompt Uncertainty 的任务优先用于指令微调，Prompt Uncertainty 的程度作为任务不确定性的度量。

### 3.3 基于强大 LLM 如 ChatGPT 的方法

本节介绍了使用强大 LLM，如 GPT-4 和 ChatGPT，作为数据选择器的方法。该方法主要包括设计提示模板并利用 LLM 的能力来评估指导数据的质量。

|  | $S_{\pi}=\{x\mid ChatGPT(score\mid prompt,x),score>\tau\}$ |  | (9) |
| --- | --- | --- | --- |

Chen 等人（[2023b](https://arxiv.org/html/2402.05123v1#bib.bib3)）提出了 ALPAGASUS 作为一种创新的数据过滤方法，旨在提高指令跟随任务（IFT）数据整理的效率和准确性。这一方法利用设计良好的提示应用于 ChatGPT，以评估每个数据元组（包括指令、输入和响应）的质量。该方法侧重于排除低于预定义质量阈值的数据元组。当这一过滤过程应用于大量数据集时，观察到数据的相当一部分存在质量问题。值得注意的是，应用基于 LLM 的过滤过程开发出的模型超越了原始模型的性能，该原始模型是使用未过滤的数据集和基于指令的微调进行训练的。

Lu 等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib14)）介绍了一种自动化的指令标记方法（INSTAG），该方法利用 ChatGPT 为指令生成详细的开放式标签，并确保子集的多样性和复杂性。这个过程涉及用反映每个指令语义和意图的标签对数据进行标注，并对其进行标签化选择的规范化处理。该方法遵循复杂性优先的多样化采样策略。首先按标签数量降序排列查询，然后根据标签的唯一性迭代地将查询添加到子集中，直到子集达到所需的大小 N。最终结果是一个经过整理的查询集，拥有更多的标签，表明其复杂性和多样性更高。

为了提升数据集的分布和质量，Xu 等人（[2023b](https://arxiv.org/html/2402.05123v1#bib.bib29)）提出了 LIFT 方法以减少样本的冗余。这一方法包含两个阶段：扩展数据集分布和整理数据集的多样性及质量。最初，ChatGPT 通过生成多样化的指令并将其向量化来增强数据。然后，基于行方差选择一个子集。其次，ChatGPT 对指令的准确性、可解释性、清晰度、难度和长度进行评分。初始子集会根据这些评分重新选择。

刘等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib13)）介绍了 DEITA 方法，该方法整合了多方面的选择指令数据的方法，重点关注复杂性、质量和多样性。复杂性描述了指令的长度、难度和复杂度等因素。质量则捕捉了输出的准确性。利用 WizardLM 技术，ChatGPT 被用来增强指令，然后对这些指令的复杂性和质量进行评估。这些评估包括使用专门训练的复杂性评分器对指令进行复杂性评分，并评估输出质量。数据集中的每个指令都被分配了复杂性分数（$c$）和质量分数（$q$），然后通过将这两个指标相乘来计算综合分数。接着，数据集根据这些综合分数进行组织，并进行向量化以便进一步分析。

为确保多样性，通过添加距离子集中最近邻样本超过设定距离阈值（$\tau$）的样本来创建一个子集。这个过程持续进行，直到子集达到预定的大小。

赵等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib32)）提出了 tree-instruct 方法，该方法通过提高指令的复杂性来改善指令的质量。刘等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib13)）使用该方法来衡量指令的复杂性，并设置指令过滤的阈值。Tree-instruct 利用 GPT-4 生成指令数据的语义解析树，使用树中的节点数量作为复杂性的衡量标准。通过向树中添加节点来增强复杂性，然后使用 GPT-4 将新树转换回自然语言，从而生成新的高质量指令。

于等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib30)）提出了 WaveCoder，这是一种以代码为重点的 LLM，通过指令改进技术得到增强。其训练包含生成的数据，其中数据过滤阶段尤为重要。在数据生成之后，利用 GPT-4 的 LLM 基础判别器对指令数据进行评估，依据分为子主题的既定标准。这种方法能够更精细地控制过滤过程，有效地消除低质量的指令实例。

### 3.4 基于小模型的方法

本节介绍了涉及使用外部小模型作为评分器的方法，或将指令转化为嵌入向量后进行进一步处理。通常，这些方法相当全面。小模型进行的评分过滤或嵌入生成往往只是整个方法过程的一部分。

杜等人（[2023](https://arxiv.org/html/2402.05123v1#bib.bib8)）介绍了 MoDS 方法，重点通过三个标准进行指令选择：质量（指令数据的真实性）、覆盖率（指令类型的多样性）和必要性（指令对 LLM 微调的影响）。该过程分为四个关键步骤：

首先，使用奖励模型评估指令数据集的质量，选择一个子集$D_{h}$，包含超过预定义质量阈值的指令。其次，利用 k-center-greedy 算法（Sener 和 Savarese（[2018a](https://arxiv.org/html/2402.05123v1#bib.bib21)））识别种子指令，从而确保指令数据集的多样性和代表性。第三，对预训练的 LLM 进行种子指令的微调。随后，将该优化模型应用于$D_{h}$生成新数据集$D_{inference}$。然后，使用奖励模型评估该数据集，识别对 LLM 学习至关重要的指令，重点关注那些得分较低的指令。设立阈值以选择增强的指令数据，这些数据特别针对提升模型性能进行调整。最后，将种子指令与增强的指令数据结合，形成一个高质量的指令子集，旨在有效地对 LLM 进行微调。

陈等人（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib2)）提出了一种基于核心集和任务相关的数据选择方法：首先，通过预训练语言模型（如 BERT）获取样本的句子嵌入，然后对这些嵌入应用无监督聚类来选择中心点，最后使用 KCenterGreedy 算法（Sener 和 Savarese（[2018b](https://arxiv.org/html/2402.05123v1#bib.bib22)））从给定数据集中检索核心样本。这种方法有效减少了所需的训练数据量，同时保持或潜在提升模型性能。

表 1：不同选择方法在获胜率上的表现。

选择方法 模型对比 训练集 测试基准（WS） Vicuna/Koala/WizardLM/Self-inst/LIMA total WS IFD Li 等人 ([2023a](https://arxiv.org/html/2402.05123v1#bib.bib10)) llama-7b(5%), llama-7b(full) alpaca 1.125/0.97/1.077/1/1.1 1.04 llama-7b(10%), llama-7b(full) 1.037/1.055/1.114/1.123/1.103 1.097 llama-7b(15%), llama-7b(full) 1/1.038/1.114/1.027/1.09 1.064 llama-7b(10%), llama-7b(full) WizardLM 1.1625/1.1278/1.1147/1.0278/1.1067 1.0971 llama2-7b(5%), llama2-7b(full) alpaca 1.5875/1.4889/1.4266/1.2937/1.4733 1.4311 随机抽样 llama-7b(5%), llama-7b(full) alpaca - 0.9 InstructionGPT4 Wei 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib26)) miniGPT4(6%), miniGPT4(full) cc_sbu_align - 1.167 Alpagsaus Chen 等人 ([2023b](https://arxiv.org/html/2402.05123v1#bib.bib3)) llama-7b(9k), llama-7b(full) alpaca 1.2125/1.0222/1.0596/1.0556/- 1.0658 llama-7b(9k), llama-7b(3k) 1.1/1.183/1.082/1.17/- 1.074 llama-7b(9k), llama-7b(6k) 1.05/1.072/1.05/1.087/- 1.082 llama-13b(9k), llama-13b(full) 1.2125/1.0167/1.133/1.0198/- 1.074 MoDS Du 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib8)) llama2-7b(2k), llama2-7b(full) alpaca 1.7125/1.5111/1.4725/1.369/1.4933 1.4786 InstructionMining Cao 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib1)) llama-7b(2k), llama-7b(full) dolly - 1.088

+   •

    ’-’ 表示原论文中未报告的值，而 model(x)表示使用 x 个样本或 x 百分比样本对模型进行调优。

表 2：对 LLM 在子集上调优的内部比较，与其在完整数据集上调优的情况对比。

| 选择方法 | 训练集（样本数） | 基础模型 | 测试基准 |
| --- | --- | --- | --- |
| total WS |
| activeIT Kung 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib9)) | selfinstruct(2k) | llama-7b | 1.107 |
| selfinstruct(full) | 1.293 |
|  |  |  | BBH/DROP/MMLU/Human-Eval/Avg |
| DQ Zhou 等人 ([2023b](https://arxiv.org/html/2402.05123v1#bib.bib34)) | alpaca(20%) | llama-7b | 32.7/26.7/39.8/9.2/27.1 |
| alpaca(full) | 32.9/26.3/41.6/10/27.7 |
|  |  |  | Vicuna RS/Vicuna WTR/Koala RS/ Koala WTR |
| DIVERSEEVOL Wu 等人 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib27)) | Dolly(1k) | llama-7b | 79.69/20/62.29/6.67 |
| Dolly(full) | 73.84/5/57.9/3.33 |
| SelfIns(1k) | 79.16/7.5/66.95/6.11 |
| SelfIns(full) | 73.03/2.5/69.5/3.89 |
|  |  |  | HellaSwag/ARC/TruthfulQA/MMLU |
| LIFT Xu 等人 ([2023b](https://arxiv.org/html/2402.05123v1#bib.bib29)) | ✗ | Mistral-7B | 0.823/0.602/0.426/0.627 |
| Platypus(15k 随机) | 0.82/0.607/0.438/0.625 |
| Platypus(15k) | 0.844/0.643/0.49/0.645 |
|  |  |  | RTE/CB/ANLI R1/ANLI R2/ANLI R3 |
| coreset Chen 等人 ([2023a](https://arxiv.org/html/2402.05123v1#bib.bib2)) | P3(0.5) | Galactica-1.3b | 74.73/73.21/49.6/41.9/43.75 |
| P3(full) | 76.17/75/44/35.7/39.42 |

+   •

    数据集(x) 表示在给定数据集的 x 个样本上对基础模型进行调优。✗ 表示训练集或基础模型的缺失。

表 3：与其他 LLM 进行外部比较的 LLM 子集调优结果。

| 模型 | 训练集（样本） | 基础模型 | MT-bench | AlpacaEval |
| --- | --- | --- | --- | --- |
| gpt-4 | ✗ | ✗ | 8.99 | 95.28 |
| gpt-3.5-turbo | ✗ | ✗ | 7.94 | 91.36 |
| alpaca-13b | alpaca | llama-13b | 4.53 | - |
| NUGGETSLi 等 ([2023c](https://arxiv.org/html/2402.05123v1#bib.bib12)) | alpaca(7.5k) | llama-7b | 5.34 | - |
| TAGLM-13b-v1.0 Lu 等 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib14)) | mixture(6k) | llama-13b | 6.44±0.04 | 72.8 |
| TAGLM-13b-v2.0 Lu 等 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib14)) | llama2-13b | 6.55±0.02 | - |
| 指令长度 | llama-13b | 5.89 | - |
| 随机抽样 | 5.84 | - |
| IFDLi 等 ([2023a](https://arxiv.org/html/2402.05123v1#bib.bib10)) | 5.91 | - |
| 指令节点赵等 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib32)) | 5.65 | - |
| DEITA Liu 等 ([2023](https://arxiv.org/html/2402.05123v1#bib.bib13)) | mixture(10k) | llama2-13b | 6.79 | 81.09 |

+   •

    ‘mixture’表示 WizardLM(Alpaca)、WizardLM(ShareGPT)、UltraChat 和 ShareGPT 的组合数据集。

## 4 评估方法与结果分析

数据选择方法的有效性依赖于从给定数据集中筛选出的子集的质量。为了衡量子集的质量，对在子集上微调的 LLM 进行不同基准的评估，这些评估可以分为三类：胜率、内部比较和外部比较。

### 4.1 胜率

为了评估数据集选择方法的有效性，计算 LLM-sub 与基础 LLM 的胜率：

|  | $(Num(win)-Num(lose))/Num(all)+1$ |  | (10) |
| --- | --- | --- | --- |

LLM-sub 表示在由选择方法筛选出的训练集子集上微调的 LLM，而基础 LLM 通常涉及两种类型：i) 在完整训练集上微调，ii) 在由常规选择（例如随机抽样和指令长度）筛选的相同规模子集上微调。公式中[10](https://arxiv.org/html/2402.05123v1#S4.E10 "10 ‣ 4.1 胜率 ‣ 4 评估方法与结果分析 ‣ 关于 LLM 指令调优的数据选择调查")，Num(win)代表获胜案例的数量，Num(lose)代表失败案例的数量，Num(all)代表测试基准中的所有案例数量。

LLM-sub 和基础 LLM 的输出由评审按照 1 到 10 的评分标准进行评分，通常使用 GPT4 作为评审。为了应对评审的定位偏差，Li 等（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib10)）将这两种 LLM 的输出以不同的顺序送给评审两次。根据 Li 等（[2023a](https://arxiv.org/html/2402.05123v1#bib.bib10)），获胜的情况指的是 LLM-sub 在两次评审中均优于基础 LLM，或者在一次中获胜而在另一次中打平。失败的情况指的是 LLM-sub 在两次评审中均落后于基础 LLM，或者在一次中打平而在另一次中失败。不同选择方法在测试基准上的获胜率汇总在表[1](https://arxiv.org/html/2402.05123v1#S3.T1 "Table 1 ‣ 3.4 Methods based on Small Models ‣ 3 Data Selection methods ‣ A Survey on Data Selection for LLM Instruction Tuning")中。

### 4.2 内部比较

为了简单直接地评估数据集选择方法的有效性，将 LLM-sub 与相同的 LLM 进行比较，但后者是在完整训练集或通过常规选择筛选的同规模子集上进行微调的。我们将这种评估方法称为内部比较，因为它仅将微调后的子集 LLM 与自身进行比较。不同选择方法在测试基准上的内部比较表现汇总在表[2](https://arxiv.org/html/2402.05123v1#S3.T2 "Table 2 ‣ 3.4 Methods based on Small Models ‣ 3 Data Selection methods ‣ A Survey on Data Selection for LLM Instruction Tuning")中。

### 4.3 外部比较

另一种简单明了的评估方法是外部比较，它将 LLM-sub 与外部 LLMs（即与 LLM-sub 模型不同的模型）在不同的测试基准上进行比较。不同选择方法在测试基准上的外部比较表现汇总在表[3](https://arxiv.org/html/2402.05123v1#S3.T3 "Table 3 ‣ 3.4 Methods based on Small Models ‣ 3 Data Selection methods ‣ A Survey on Data Selection for LLM Instruction Tuning")中。

### 4.4 结果分析

提出的选择方法优于常规选择，这证明了数据选择在指令调优中的重要性。如表[1](https://arxiv.org/html/2402.05123v1#S3.T1 "Table 1 ‣ 3.4 Methods based on Small Models ‣ 3 Data Selection methods ‣ A Survey on Data Selection for LLM Instruction Tuning")和[2](https://arxiv.org/html/2402.05123v1#S3.T2 "Table 2 ‣ 3.4 Methods based on Small Models ‣ 3 Data Selection methods ‣ A Survey on Data Selection for LLM Instruction Tuning")所示，TAGLM-13b-v1.0 和 IFD 在根据指令长度和随机抽样的 MT-benc 上优于常规选择方法，在对 llama-13b 进行混合数据集调优时，Alpagsaus 和 IFD 在对 llama-7b 进行 alpaca 调优时在总 WS 上优于随机抽样。

更先进的 LLM（llama2-7b）在相同子集上的微调相比标准 LLM（llama-7b）表现更好。表[3](https://arxiv.org/html/2402.05123v1#S3.T3 "表 3 ‣ 3.4 基于小型模型的方法 ‣ 3 数据选择方法 ‣ LLM 指令调整的数据选择调查")显示 TAGLM-13b-v2.0 优于 TAGLM-13b-v1.0，表[1](https://arxiv.org/html/2402.05123v1#S3.T1 "表 1 ‣ 3.4 基于小型模型的方法 ‣ 3 数据选择方法 ‣ LLM 指令调整的数据选择调查")显示，在应用 IFD 选择方法时，llama2-7b(5%)优于 llama-7b(5%)。这些改进归因于先进 LLMs 的固有复杂性，从而在子集上具有更高的学习效率。

仅在更大的子集上调整特定 LLM 并不一定能保证性能提升。这可能与选择方法的固有特性有关。正如在表[1](https://arxiv.org/html/2402.05123v1#S3.T1 "表 1 ‣ 3.4 基于小型模型的方法 ‣ 3 数据选择方法 ‣ LLM 指令调整的数据选择调查")中所示，当在训练集 alpaca 中应用 IFD 方法时，llama-7b 的性能并未随着子集大小的增加而改善。然而，当在相同的训练集中应用 Alpagsaus 方法时，llama-7b 的性能随着子集大小的增加而改善。

## 5 结论和开放性挑战

本文全面概述了指令调整数据选择方法和挑战，强调了高质量数据在微调阶段的关键作用。我们展示了一些现有数据集以及它们对应的构建方法。这些数据集存在诸如数据分布不均和数据质量不一致等问题。在此基础上，我们介绍了现有的四种数据选择方法。仅依赖度量集的方法可以有效评估单个数据的质量，但缺乏对复杂数据集特征的考虑。设计评分公式的可训练大型模型方法可以选择适合 LLM 本身的数据，利用像 GPT-4 这样的外部强大 LLMs 进行评分的方法具有异常的数据选择能力。此外，利用设计有多个模块的小型模型的方法通常考虑了各种方面。最后，我们介绍了如何评估数据选择方法，包括获胜率、内部比较和外部比较。尽管现有方法取得了可观的性能，但仍然存在一些挑战。

目前缺乏统一的评估标准。在第[4](https://arxiv.org/html/2402.05123v1#S4 "4 Evaluation methods and Result Analysis ‣ A Survey on Data Selection for LLM Instruction Tuning")节中，我们介绍了多种评估方法和针对 LLMs 的各种基准。各种数据选择方法通常选择不同的评估标准，这造成了确定哪种方法更有优势的相当困难。未来的研究可以致力于建立一种合理、全面且自动化的评估方法，以统一方法的评估过程。

处理大量数据通常效率较低，并且对强大的 LLMs 依赖较大。当待过滤的指令数据集规模过大时，现有方法通常处理时间过长，特别是在使用 LLMs 提取指令特征或执行相关度量计算时。使用 LLMs 处理数十万条指令数据可能非常耗时。此外，使用像 GPT4 API 这样的强大 LLMs 处理数十万条指令时，成本非常高。未来的工作应探索使用较小模型，并努力匹配 LLMs 的选择能力。

现有的数据质量评估模型和方法主要集中在英语和通用领域，缺乏针对其他语言和特定领域选择方法的模型。未来的研究应探索其他语言的指令质量评估模型，并调查任务特定选择方法的设计。这旨在提升方法在不同规模、领域和语言的指令集中的表现。

这些挑战为进一步探索提供了有前景的方向，可能会带来突破。总之，我们希望这些分析努力和提供的概述能进一步促进 LLMs 在遵循人类指令方面能力的提升。

## 参考文献

+   Cao et al. [2023] 曹毅涵、康彦斌和孙立超。《指令挖掘：大语言模型的高质量指令数据选择》。CoRR, abs/2307.06290, 2023。

+   Chen et al. [2023a] 陈浩、张一鸣、张琪、杨汉涛、胡晓萌、马雪涛、杨永刚和赵俊博。《也许只需要 0.5%的数据：低训练数据指令调优的初步探索》。CoRR, abs/2305.09246, 2023。

+   Chen et al. [2023b] 陈丽昌、李世阳、闫俊、王海、卡尔帕·古纳拉特纳、维卡斯·亚达夫、唐正、维杰·斯里尼瓦桑、周天逸、黄恒和金红霞。《Alpagasus：用更少的数据训练更好的 alpaca》。CoRR, abs/2307.08701, 2023。

+   Chen et al. [2023c] 陈永锐、姜海云、黄心婷、石树铭和齐桂林。《Tegit：通过基于文本的任务设计生成高质量的指令调优数据》。CoRR, abs/2309.05447, 2023。

+   Chowdhery et al. [2023] Aakanksha Chowdhery, Sharan Narang, Jacob Devlin, Maarten Bosma, Gaurav Mishra, Adam Roberts, Paul Barham, Hyung Won Chung, Charles Sutton, Sebastian Gehrmann, Parker Schuh, Kensen Shi, Sasha Tsvyashchenko, Joshua Maynez, Abhishek Rao, Parker Barnes, Yi Tay, Noam Shazeer, Vinodkumar Prabhakaran, Emily Reif, Nan Du, Ben Hutchinson, Reiner Pope, James Bradbury, Jacob Austin, Michael Isard, Guy Gur-Ari, Pengcheng Yin, Toju Duke, Anselm Levskaya, Sanjay Ghemawat, Sunipa Dev, Henryk Michalewski, Xavier Garcia, Vedant Misra, Kevin Robinson, Liam Fedus, Denny Zhou, Daphne Ippolito, David Luan, Hyeontaek Lim, Barret Zoph, Alexander Spiridonov, Ryan Sepassi, David Dohan, Shivani Agrawal, Mark Omernick, Andrew M. Dai, Thanumalayan Sankaranarayana Pillai, Marie Pellat, Aitor Lewkowycz, Erica Moreira, Rewon Child, Oleksandr Polozov, Katherine Lee, Zongwei Zhou, Xuezhi Wang, Brennan Saeta, Mark Diaz, Orhan Firat, Michele Catasta, Jason Wei, Kathy Meier-Hellstern, Douglas Eck, Jeff Dean, Slav Petrov, 和 Noah Fiedel. Palm: 通过路径扩展语言建模。J. Mach. Learn. Res., 24:240:1–240:113, 2023。

+   Conover et al. [2023] Mike Conover, Matt Hayes, Ankit Mathur, Jianwei Xie, Jun Wan, Sam Shah, Ali Ghodsi, Patrick Wendell, Matei Zaharia, 和 Reynold Xin. Free dolly: 介绍世界上第一个真正开放的指令调优 LLM，2023。

+   Dong et al. [2011] Wei Dong, Moses Charikar, 和 Kai Li. 高效的 k-最近邻图构建方法，用于通用相似度度量。在 Sadagopan Srinivasan, Krithi Ramamritham, Arun Kumar, M. P. Ravindra, Elisa Bertino, 和 Ravi Kumar 编辑的《第 20 届国际万维网大会会议录，WWW 2011，印度海得拉巴，2011 年 3 月 28 日 - 4 月 1 日》，第 577–586 页。ACM，2011。

+   Du et al. [2023] Qianlong Du, Chengqing Zong, 和 Jiajun Zhang. Mods: 面向模型的数据选择用于指令调优。CoRR，abs/2311.15653，2023。

+   Kung et al. [2023] Po-Nien Kung, Fan Yin, Di Wu, Kai-Wei Chang, 和 Nanyun Peng. 主动指令调优：通过训练在提示敏感任务上提高跨任务泛化能力。在 Houda Bouamor, Juan Pino, 和 Kalika Bali 编辑的《2023 年自然语言处理实证方法会议录，EMNLP 2023，新加坡，2023 年 12 月 6-10 日》，第 1813–1829 页。计算语言学协会，2023。

+   Li et al. [2023a] Ming Li, Yong Zhang, Zhitao Li, Jiuhai Chen, Lichang Chen, Ning Cheng, Jianzong Wang, Tianyi Zhou, 和 Jing Xiao. 从数量到质量：通过自我引导的数据选择提升 LLM 表现。CoRR，abs/2308.12032，2023。

+   Li et al. [2023b] Xian Li, Ping Yu, Chunting Zhou, Timo Schick, Luke Zettlemoyer, Omer Levy, Jason Weston, 和 Mike Lewis. 使用指令回译进行自我对齐。CoRR，abs/2308.06259，2023。

+   Li 等人 [2023c] 云水·李、宾远·辉、晓博·夏、佳熙·杨、敏·杨、磊·张、舒正·司、俊豪·刘、桐亮·刘、飞·黄和永斌·李。单次学习作为大型语言模型的指令数据开采者。CoRR, abs/2312.10302, 2023。

+   Liu 等人 [2023] 韦·刘、韦浩·曾、柯庆·赫、雍·姜和俊贤·赫。什么样的数据对对齐有用？对指令调优中的自动数据选择的综合研究。CoRR, abs/2312.15685, 2023。

+   Lu 等人 [2023] 克明·卢、洪毅·袁、郑源、润基·林、俊扬·林、川奇·谭、昌周和晶仁·周。#instag: 用于分析大语言模型监督微调的指令标记。CoRR, abs/2308.07074, 2023。

+   OpenAI [2023] OpenAI。GPT-4 技术报告。CoRR, abs/2303.08774, 2023。

+   Ouyang 等人 [2022a] 龙·欧阳、杰弗里·吴、徐江、迪奥戈·阿尔梅达、卡罗尔·L·韦恩赖特、帕梅拉·米什金、钟·张、桑迪尼·阿加瓦尔、卡塔里娜·斯拉马、亚历克斯·雷、约翰·舒尔曼、雅各布·希尔顿、弗雷泽·凯尔顿、卢克·米勒、马迪·西门斯、阿曼达·阿斯克尔、彼得·维林德、保罗·F·克里斯蒂亚诺、简·莱克和瑞安·洛。利用人类反馈训练语言模型以遵循指令。见《神经信息处理系统进展 35：2022 年神经信息处理系统年会，NeurIPS 2022，美国路易斯安那州新奥尔良，2022 年 11 月 28 日 - 12 月 9 日》，2022 年。

+   Ouyang 等人 [2022b] 龙·欧阳、杰弗里·吴、徐江、迪奥戈·阿尔梅达、卡罗尔·L·韦恩赖特、帕梅拉·米什金、钟·张、桑迪尼·阿加瓦尔、卡塔里娜·斯拉马、亚历克斯·雷、约翰·舒尔曼、雅各布·希尔顿、弗雷泽·凯尔顿、卢克·米勒、马迪·西门斯、阿曼达·阿斯克尔、彼得·维林德、保罗·F·克里斯蒂亚诺、简·莱克和瑞安·洛。利用人类反馈训练语言模型以遵循指令。见 Sanmi Koyejo, S. Mohamed, A. Agarwal, Danielle Belgrave, K. Cho 和 A. Oh 编者，《神经信息处理系统进展 35：2022 年神经信息处理系统年会，NeurIPS 2022，美国路易斯安那州新奥尔良，2022 年 11 月 28 日 - 12 月 9 日》，2022 年。

+   Radford 等人 [2021] 亚历克·拉德福德、钟旭·金、克里斯·哈拉西、阿迪亚·拉梅什、加布里埃尔·戈、桑迪尼·阿加瓦尔、吉里什·萨斯特里、阿曼达·阿斯克尔、帕梅拉·米什金、杰克·克拉克、格雷琴·克鲁格和伊利亚·苏茨克维尔。学习可转移的视觉模型通过自然语言监督。见 Marina Meila 和 Tong Zhang 编者，《第 38 届国际机器学习会议论文集，ICML 2021，2021 年 7 月 18-24 日，虚拟活动》，《机器学习研究论文集》第 139 卷，第 8748–8763 页。PMLR，2021 年。

+   Reimers 和 Gurevych [2019] 尼尔斯·雷默斯和伊琳娜·古列维奇。Sentence-bert: 使用孪生 BERT 网络的句子嵌入。CoRR, abs/1908.10084, 2019。

+   Sanh et al. [2022] Victor Sanh, Albert Webson, Colin Raffel, Stephen H. Bach, Lintang Sutawika, Zaid Alyafeai, Antoine Chaffin, Arnaud Stiegler, Arun Raja, Manan Dey, M Saiful Bari, Canwen Xu, Urmish Thakker, Shanya Sharma Sharma, Eliza Szczechla, Taewoon Kim, Gunjan Chhablani, Nihal V. Nayak, Debajyoti Datta, Jonathan Chang, Mike Tian-Jian Jiang, Han Wang, Matteo Manica, Sheng Shen, Zheng Xin Yong, Harshit Pandey, Rachel Bawden, Thomas Wang, Trishala Neeraj, Jos Rozen, Abheesht Sharma, Andrea Santilli, Thibault Févry, Jason Alan Fries, Ryan Teehan, Teven Le Scao, Stella Biderman, Leo Gao, Thomas Wolf 和 Alexander M. Rush。多任务提示训练实现零样本任务泛化。第十届国际学习表征会议，ICLR 2022，虚拟会议，2022 年 4 月 25 日至 29 日。OpenReview.net，2022 年。

+   Sener and Savarese [2018a] Ozan Sener 和 Silvio Savarese。卷积神经网络的主动学习：核心集方法。第六届国际学习表征会议，ICLR 2018，加拿大温哥华，2018 年 4 月 30 日至 5 月 3 日，会议论文集。OpenReview.net，2018 年。

+   Sener and Savarese [2018b] Ozan Sener 和 Silvio Savarese。卷积神经网络的主动学习：核心集方法。第六届国际学习表征会议，ICLR 2018，加拿大温哥华，2018 年 4 月 30 日至 5 月 3 日，会议论文集。OpenReview.net，2018 年。

+   Taori et al. [2023] Rohan Taori, Ishaan Gulrajani, Tianyi Zhang, Yann Dubois, Xuechen Li, Carlos Guestrin, Percy Liang 和 Tatsunori B. Hashimoto。斯坦福阿帕卡：一个指令跟随的 llm 模型。[`github.com/tatsu-lab/stanford_alpaca`](https://github.com/tatsu-lab/stanford_alpaca)，2023 年。

+   Touvron et al. [2023] Hugo Touvron, Thibaut Lavril, Gautier Izacard, Xavier Martinet, Marie-Anne Lachaux, Timothée Lacroix, Baptiste Rozière, Naman Goyal, Eric Hambro, Faisal Azhar, Aurélien Rodriguez, Armand Joulin, Edouard Grave 和 Guillaume Lample。Llama：开放且高效的基础语言模型。CoRR，abs/2302.13971，2023 年。

+   Wang et al. [2023] Yizhong Wang, Yeganeh Kordi, Swaroop Mishra, Alisa Liu, Noah A. Smith, Daniel Khashabi 和 Hannaneh Hajishirzi。Self-instruct：使语言模型与自生成指令对齐。在 Anna Rogers, Jordan L. Boyd-Graber 和 Naoaki Okazaki 编辑的第 61 届计算语言学协会年会（第 1 卷：长篇论文）论文集，ACL 2023，加拿大多伦多，2023 年 7 月 9 日至 14 日，第 13484–13508 页。计算语言学协会，2023 年。

+   Wei et al. [2023] Lai Wei, Zihao Jiang, Weiran Huang 和 Lichao Sun。Instructiongpt-4：一种用于微调 minigpt-4 的 200 指令范式。CoRR，abs/2308.12067，2023 年。

+   Wu et al. [2023] Shengguang Wu, Keming Lu, Benfeng Xu, Junyang Lin, Qi Su 和 Chang Zhou。自演变的多样数据采样用于高效指令调优。CoRR，abs/2311.08182，2023 年。

+   Xu et al. [2023a] 徐灿，孙青峰，郑凯，耿秀波，赵浦，冯家展，陶崇阳，蒋大欣。Wizardlm：赋能大型语言模型以执行复杂指令。CoRR, abs/2304.12244, 2023 年。

+   Xu et al. [2023b] 徐杨，姚永强，黄玉凡，齐梦楠，王茂全，顾彬，尼尔·孙达雷桑。重新思考指令质量：LIFT 是你需要的。CoRR, abs/2312.11508, 2023 年。

+   Yu et al. [2023] 余朝建，张鑫，尚宁，黄杨雨，徐灿，赵一书洁，胡文祥，殷秋风。Wavecoder：广泛且多用途的增强指令调优与精细化数据生成。CoRR, abs/2312.14187, 2023 年。

+   Zhang et al. [2023] 张胜宇，董林峰，李晓雅，张森，孙晓飞，王书和，李季伟，胡润怡，张天伟，吴飞，王国银。大语言模型的指令调优：综述。CoRR, abs/2308.10792, 2023 年。

+   Zhao et al. [2023] 赵英修，余博文，惠宾远，余海洋，黄飞，李永彬，张奈文。复杂性与对齐之间的内在关系初步研究，2023 年。

+   Zhou et al. [2023a] 朱冲等人，彭飞刘，徐普新，斯里尼·艾耶尔，焦孙，毛宇宁，马雪哲，阿维亚·艾弗拉特，彭宇，李丽·余，苏珊·张，格尔吉·戈什，迈克·刘易斯，卢克·泽特尔摩耶，奥梅尔·莱维。LIMA：对齐的少即是多。在第 37 届神经信息处理系统会议，2023 年。

+   Zhou et al. [2023b] 周大全，王凯，顾建阳，彭相宇，连东泽，张一凡，游洋，冯佳世。数据集量化。CoRR, abs/2308.10524, 2023 年。

+   Zhu et al. [2023] 朱德耀，陈军，沈晓茜，李翔，穆罕默德·艾尔霍赛尼。Minigpt-4：通过先进的大型语言模型提升视觉-语言理解。CoRR, abs/2304.10592, 2023 年。

Generated on Sun Feb 4 13:31:46 2024 by [LATExml![[LOGO]](img/70e087b9e50c3aa663763c3075b0d6c5.png)](http://dlmf.nist.gov/LaTeXML/)
