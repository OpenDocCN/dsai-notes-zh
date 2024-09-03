<!--yml

category: 未分类

date: 2024-09-03 17:30:48

-->

# LLM 推断揭秘：调查与屋顶线模型见解

> 来源：[`arxiv.org/html/2402.16363`](https://arxiv.org/html/2402.16363)

1.  [1 引言](https://arxiv.org/html/2402.16363v6#S1 "在 LLM 推断揭秘：调查与屋顶线模型见解")

1.  [2 深入 LLM 推断和部署](https://arxiv.org/html/2402.16363v6#S2 "在 LLM 推断揭秘：调查与屋顶线模型见解")

    1.  [2.1 LLM 推断](https://arxiv.org/html/2402.16363v6#S2.SS1 "在 2 深入 LLM 推断和部署‣LLM 推断揭秘：调查与屋顶线模型见解")

    1.  [2.2 屋顶线模型](https://arxiv.org/html/2402.16363v6#S2.SS2 "在 2 深入 LLM 推断和部署‣LLM 推断揭秘：调查与屋顶线模型见解")

    1.  [2.3 LLM-Viewer](https://arxiv.org/html/2402.16363v6#S2.SS3 "在 2 深入 LLM 推断和部署‣LLM 推断揭秘：调查与屋顶线模型见解")

1.  [3 模型压缩](https://arxiv.org/html/2402.16363v6#S3 "在 LLM 推断揭秘：调查与屋顶线模型见解")

    1.  [3.1 量化](https://arxiv.org/html/2402.16363v6#S3.SS1 "在 3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.1.1 LLM-Viewer 的应用案例：量化的屋顶线分析](https://arxiv.org/html/2402.16363v6#S3.SS1.SSS1 "在 3.1 量化‣3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.1.2 用于压缩预训练 LLM 的量化](https://arxiv.org/html/2402.16363v6#S3.SS1.SSS2 "在 3.1 量化‣3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.1.3 参数高效微调的量化（Q-PEFT）](https://arxiv.org/html/2402.16363v6#S3.SS1.SSS3 "在 3.1 量化‣3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.1.4 LLM 量化讨论](https://arxiv.org/html/2402.16363v6#S3.SS1.SSS4 "在 3.1 量化‣3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

    1.  [3.2 剪枝](https://arxiv.org/html/2402.16363v6#S3.SS2 "在 3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.2.1 非结构化剪枝](https://arxiv.org/html/2402.16363v6#S3.SS2.SSS1 "在 3.2 剪枝‣3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.2.2 结构化剪枝](https://arxiv.org/html/2402.16363v6#S3.SS2.SSS2 "在 3.2 剪枝‣3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

    1.  [3.3 知识蒸馏](https://arxiv.org/html/2402.16363v6#S3.SS3 "在 3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.3.1 白盒知识蒸馏](https://arxiv.org/html/2402.16363v6#S3.SS3.SSS1 "在 3.3 知识蒸馏‣3 模型压缩‣LLM 推断揭秘：调查与屋顶线模型见解")

        1.  [3.3.2 黑箱知识蒸馏](https://arxiv.org/html/2402.16363v6#S3.SS3.SSS2 "在 3.3 知识蒸馏 ‣ 3 模型压缩 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

    1.  [3.4 分解](https://arxiv.org/html/2402.16363v6#S3.SS4 "在 3 模型压缩 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

1.  [4 种快速解码的算法方法](https://arxiv.org/html/2402.16363v6#S4 "在 LLM 推理揭示：调查与 Roofline 模型见解")

    1.  [4.1 每个令牌解码所用的最少参数](https://arxiv.org/html/2402.16363v6#S4.SS1 "在 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

        1.  [4.1.1 早期退出](https://arxiv.org/html/2402.16363v6#S4.SS1.SSS1 "在 4.1 每个令牌解码所用的最少参数 ‣ 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

        1.  [4.1.2 上下文稀疏性](https://arxiv.org/html/2402.16363v6#S4.SS1.SSS2 "在 4.1 每个令牌解码所用的最少参数 ‣ 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

        1.  [4.1.3 专家混合模型](https://arxiv.org/html/2402.16363v6#S4.SS1.SSS3 "在 4.1 每个令牌解码所用的最少参数 ‣ 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

        1.  [4.1.4 动态参数减少的 Roofline 模型分析](https://arxiv.org/html/2402.16363v6#S4.SS1.SSS4 "在 4.1 每个令牌解码所用的最少参数 ‣ 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

    1.  [4.2 每次 LLM 前向传播解码的最大令牌数](https://arxiv.org/html/2402.16363v6#S4.SS2 "在 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

        1.  [4.2.1 推测解码](https://arxiv.org/html/2402.16363v6#S4.SS2.SSS1 "在 4.2 每次 LLM 前向传播解码的最大令牌数 ‣ 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

        1.  [4.2.2 并行解码](https://arxiv.org/html/2402.16363v6#S4.SS2.SSS2 "在 4.2 每次 LLM 前向传播解码的最大令牌数 ‣ 4 种快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

1.  [5 编译器/系统优化](https://arxiv.org/html/2402.16363v6#S5 "在 LLM 推理揭示：调查与 Roofline 模型见解")

    1.  [5.1 操作符融合](https://arxiv.org/html/2402.16363v6#S5.SS1 "在 5 编译器/系统优化 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

    1.  [5.2 内存管理和工作负载卸载](https://arxiv.org/html/2402.16363v6#S5.SS2 "在 5 编译器/系统优化 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

    1.  [5.3 并行服务](https://arxiv.org/html/2402.16363v6#S5.SS3 "在 5 编译器/系统优化 ‣ LLM 推理揭示：调查与 Roofline 模型见解")

1.  [6 硬件优化](https://arxiv.org/html/2402.16363v6#S6 "在 LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [6.1 空间架构](https://arxiv.org/html/2402.16363v6#S6.SS1 "在 6 硬件优化 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [6.2 内存处理](https://arxiv.org/html/2402.16363v6#S6.SS2 "在 6 硬件优化 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [6.3 新数据格式](https://arxiv.org/html/2402.16363v6#S6.SS3 "在 6 硬件优化 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [6.4 新处理元素](https://arxiv.org/html/2402.16363v6#S6.SS4 "在 6 硬件优化 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

1.  [7 讨论](https://arxiv.org/html/2402.16363v6#S7 "在 LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [7.1 可靠性](https://arxiv.org/html/2402.16363v6#S7.SS1 "在 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

        1.  [7.1.1 幻觉](https://arxiv.org/html/2402.16363v6#S7.SS1.SSS1 "在 7.1 可靠性 ‣ 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [7.2 安全对齐](https://arxiv.org/html/2402.16363v6#S7.SS2 "在 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [7.3 OOD 泛化](https://arxiv.org/html/2402.16363v6#S7.SS3 "在 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [7.4 高效的大型多模态模型](https://arxiv.org/html/2402.16363v6#S7.SS4 "在 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

        1.  [7.4.1 大型多模态模型 (LMMs)](https://arxiv.org/html/2402.16363v6#S7.SS4.SSS1 "在 7.4 高效的大型多模态模型 ‣ 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

        1.  [7.4.2 高效的 LMMs](https://arxiv.org/html/2402.16363v6#S7.SS4.SSS2 "在 7.4 高效的大型多模态模型 ‣ 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

    1.  [7.5 长上下文建模](https://arxiv.org/html/2402.16363v6#S7.SS5 "在 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

        1.  [7.5.1 替代注意力设计](https://arxiv.org/html/2402.16363v6#S7.SS5.SSS1 "在 7.5 长上下文建模 ‣ 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

        1.  [7.5.2 递归与检索](https://arxiv.org/html/2402.16363v6#S7.SS5.SSS2 "在 7.5 长上下文建模 ‣ 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

        1.  [7.5.3 操控位置编码](https://arxiv.org/html/2402.16363v6#S7.SS5.SSS3 "在 7.5 长上下文建模 ‣ 7 讨论 ‣ LLM 推理揭示：调查和 Roofline 模型见解")

1.  [8 结论](https://arxiv.org/html/2402.16363v6#S8 "在 LLM 推理揭示：调查和 Roofline 模型见解")

\useunder

\ul

# LLM 推理揭示：调查和 Roofline 模型见解

Zhihang Yuan^(1,)         Yuzhang Shang^(2,∗)         Yang Zhou^(3,∗)         Zhen Dong⁸

Zhe Zhou⁴         Chenhao Xue⁴         Bingzhe Wu⁵          Zhikai Li⁶         Qingyi Gu⁶

Yong Jae Lee⁷         Yan Yan²         Beidi Chen³          Guangyu Sun⁴         Kurt Keutzer⁸

¹Infinigence-AI , ²伊利诺伊理工学院, ³卡内基梅隆大学, ⁴北京大学, ⁵腾讯 AI 实验室,

⁶自动化研究所, 中国科学院, ⁷威斯康星大学麦迪逊分校, ⁸加州大学伯克利分校。贡献相等。Zhihang Yuan (hahnyuan@gmail.com) 是项目负责人。

###### 摘要

高效大型语言模型（LLM）推理领域正在迅速发展，呈现出独特的机遇和挑战的结合。尽管该领域已扩展且充满活力，但尚未有一个简洁的框架来分析各种 LLM 推理方法，以提供对这一领域的清晰理解。我们的调查与传统文献综述不同，不仅总结了当前的研究状态，还引入了一个基于 Roofline 模型的框架，用于系统分析 LLM 推理技术。该框架识别了在硬件设备上部署 LLM 时的瓶颈，并提供了对实际问题的清晰理解，例如为何 LLM 受限于内存，它们需要多少内存和计算，以及如何选择合适的硬件。我们系统地整理了高效 LLM 推理的最新进展，涵盖了关键领域，如模型压缩（例如量化）、算法改进（例如推测解码）以及系统和硬件层面的增强（例如操作符融合）。我们的调查通过 Roofline 模型分析这些方法，帮助我们理解它们对内存访问和计算的影响。这种独特的方法不仅展示了当前的研究格局，还为实际实施提供了宝贵的见解，使我们的工作成为新入门研究人员以及那些寻求深入了解高效 LLM 部署的研究人员的必备资源。分析工具，[LLM-Viewer](https://github.com/hahnyuan/LLM-Viewer)，已开源。

## 1 引言

![参考说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：我们设计的 LLM-Viewer 的工作流程。输入：预期 LLM 部署的配置细节和特定硬件设备的信息。在接收到这些输入后，LLM-Viewer 旨在精确分析和识别与在指定硬件设备上部署给定 LLM 相关的瓶颈，从而促进针对性的优化，以实现高效 LLM 推理。

![参考说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2：关于高效 LLM 推断的思维导图。我们的调查与传统调查不同，专注于 LLM 推断的实际方面。具体而言，我们识别并分析了与 LLM 推断相关的挑战。随后，我们介绍了一种专门开发的 Roofline 模型，以找出 LLM 推断过程中的瓶颈（见[第二部分](https://arxiv.org/html/2402.16363v6#S2 "2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")）。调查将提高 LLM 推断效率的策略分为四个主要领域：参数减少（见[第三部分](https://arxiv.org/html/2402.16363v6#S3 "3 Model Compression ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")），快速解码算法设计（见[第四部分](https://arxiv.org/html/2402.16363v6#S4 "4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")），系统级优化（见[第五部分](https://arxiv.org/html/2402.16363v6#S5 "5 Compiler/System Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")），以及硬件级优化（见[第六部分](https://arxiv.org/html/2402.16363v6#S6 "6 Hardware Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")），为解决高效 LLM 部署的复杂性提供了全面的框架。

大型语言模型（LLMs）近年来已成为人工智能进步的基石，重塑了机器学习和自然语言处理（NLP）的格局[赵等人，2023](https://arxiv.org/html/2402.16363v6#bib.bib244)。这一趋势可以追溯到像**ChatGPT**这样的革命性模型的成功[布朗等人，2020](https://arxiv.org/html/2402.16363v6#bib.bib14)，[欧阳等人，2022](https://arxiv.org/html/2402.16363v6#bib.bib158)，这些模型通过卓越的理解和生成能力产生非常类似于人类的文本。在**ChatGPT**之后，其他显著的 LLMs 如 OPT[张等人，2022](https://arxiv.org/html/2402.16363v6#bib.bib241)，BLOOM[斯考等人，2022](https://arxiv.org/html/2402.16363v6#bib.bib172)和 Llama[[图弗龙等人，2023a](https://arxiv.org/html/2402.16363v6#bib.bib196)，[图弗龙等人，2023b](https://arxiv.org/html/2402.16363v6#bib.bib197)]也相继出现，进一步巩固了较大模型往往带来增强能力的共识。因此，拥有数十亿参数的模型变得越来越普遍。由于这些模型的庞大规模，它们在推理时面临着相当大的挑战，这不仅对计算能力有限的设备如此，对最先进的硬件也是如此。由于其复杂性和规模以及能源和计算需求，这些模型在实际应用中难以部署。此外，这些模型资源密集的特性引发了对能源消耗、可扩展性和可达性的担忧。对于计算资源少于大型公司的较小组织和社区来说，这种情况尤为困难。因此，这些挑战突显了需要创新解决方案来使 LLM 推理变得更具普遍可达性和可持续性。

为了应对部署 LLM 的挑战，已经开发了众多方法。在过去两年中，高效 LLM 推断领域迅速发展，既带来了机遇，也带来了挑战。尽管日益增多的研究量展示了该领域的活跃性，但它也可能无意中掩盖了关键趋势并减缓了进展。现有文献中的一个重要空白是缺乏一个系统化且实用的统一分析框架和全面的解决方案开发。为了弥补这一空白，我们的工作提供了对高效 LLM 推断研究现状的全面概述，特别关注其以实践为驱动的特性。与传统的文献综述不同，我们的工作不仅讨论了现有研究，还引入了专门开发的 Roofline 模型。该模型旨在分析 LLM 部署中的瓶颈，这是我们认为对于实际应用和优化至关重要的一步，如图 [1](https://arxiv.org/html/2402.16363v6#S1.F1 "Figure 1 ‣ 1 Introduction ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")所示。我们所做的工作是，迄今为止，我们了解到的第一个提供此类工具来分析硬件设备上推断 LLM 复杂性的工作，系统地汇总了高效 LLM 推断的最新进展。我们深入探讨了部署挑战，特别强调了推断效率。我们的讨论涵盖了多个领域，包括模型压缩、解码算法优化、系统级和硬件级的增强，如图 [2](https://arxiv.org/html/2402.16363v6#S1.F2 "Figure 2 ‣ 1 Introduction ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")所示。尽管在这一领域存在相关的调查，例如[Zhu et al., 2023](https://arxiv.org/html/2402.16363v6#bib.bib253)关于 LLM 压缩的研究，以及[[Miao et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib146)]、[Ding et al., 2023](https://arxiv.org/html/2402.16363v6#bib.bib47)和[[Wang et al., 2024a](https://arxiv.org/html/2402.16363v6#bib.bib201)]关于整体 LLM 服务的研究，我们的工作通过结合 Roofline 模型分析而显得与众不同。

在本文中，我们首先讨论 LLMs 的基础，并开发了一个名为 LLM-Viewer 的工具，利用 Roofline 模型分析部署 LLMs 的瓶颈（第[2](https://arxiv.org/html/2402.16363v6#S2 "2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")节）。LLM-Viewer 可用于分析各种硬件平台上的 LLM 架构部署，如图 [1](https://arxiv.org/html/2402.16363v6#S1.F1 "Figure 1 ‣ 1 Introduction ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")所示。对于文献综述，本调查将提高 LLM 推理效率的策略分为四个主要领域：模型压缩（第[3](https://arxiv.org/html/2402.16363v6#S3 "3 Model Compression ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")节）、快速解码的算法方法（第[4](https://arxiv.org/html/2402.16363v6#S4 "4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")节）、编译器/系统级优化（第[5](https://arxiv.org/html/2402.16363v6#S5 "5 Compiler/System Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")节）以及硬件级优化（第[6](https://arxiv.org/html/2402.16363v6#S6 "6 Hardware Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")节）。

## 2 深入探讨 LLM 推理与部署

### 2.1 LLM 推理

![参考图注](img/9df2a699c179d7d103da938773675ba1.png)

图 3: LLM 架构示意图。

目前，大多数大型语言模型（LLMs）采用的主流架构是 Transformer 解码器架构。这里我们将提供其基本结构的简要概述，想要深入了解可以参考这篇调查 Zhao et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib244)]。该结构包括一个嵌入层、一系列顺序的 Transformer 层和一个预测头。图 [3](https://arxiv.org/html/2402.16363v6#S2.F3 "Figure 3 ‣ 2.1 LLM Inference ‣ 2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 展示了这一架构。

嵌入层将输入标记转换为隐状态。隐状态被送往 Transformer 层。每个 Transformer 层由两个组件组成。首先是一个掩码多头注意力模块，记作 MHA。接着是一个多层感知机子模块，标记为 MLP。最后一个 Transformer 层的输出被送往预测头，负责在输入标记之后预测下一个标记。

推理代表了与训练过程相反的过程。在训练过程中，模型从大量数据集中学习，以捕捉语言和上下文的复杂性。模型中的权重会被更新。相反，在推理过程中，用户输入一个提示，LLM 进行生成响应的过程。这个过程涉及模型利用其固定的预训练权重来理解输入文本并生成输出文本。大型语言模型（LLMs）的推理过程分为两个阶段：预填充阶段和解码阶段。

预填充阶段作为 LLM 推理的初始步骤。在此阶段，模型将提示序列作为输入，并为 LLM 中的每个 Transformer 层生成一个键值缓存（KV 缓存）。KV 缓存在存储和组织模型认为对后续令牌生成相关的信息中发挥了至关重要的作用。每个 Transformer 层都配备了自己独特的 KV 缓存，这个预填充过程为后续的解码阶段奠定了基础。

在预填充阶段，多头注意力（MHA）创建将存储在 KV 缓存中的键值（KV）对。我们将输入到 Transformer 层的矩阵表示为$\mathbf{X}_{\text{pre}}\in\mathbb{R}^{n\times d}$，其中$d$是隐藏层大小，$n$是提示令牌序列的长度。MHA 中的层有权重，由$\mathbf{W}_{q}$、$\mathbf{W}_{k}$、$\mathbf{W}_{v}$和$\mathbf{W}_{o}$表示。查询、键和值通过以下过程计算：

|  | $\displaystyle\text{查询:}\quad\mathbf{Q}_{\text{pre}}$ | $\displaystyle=\mathbf{X}_{\text{pre}}\cdot\mathbf{W}_{q}$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle\text{键:}\quad\mathbf{K}_{\text{pre}}$ | $\displaystyle=\mathbf{X}_{\text{pre}}\cdot\mathbf{W}_{k}$ |  |
|  | $\displaystyle\text{值:}\quad\mathbf{V}_{\text{pre}}$ | $\displaystyle=\mathbf{X}_{\text{pre}}\cdot\mathbf{W}_{v}$ |  |

生成的$\mathbf{K}_{\text{pre}}$和$\mathbf{V}_{\text{pre}}$被存储在 KV 缓存中。MHA 中的其他计算可以被公式化为¹¹1 为了简化，我们省略了层归一化、位置掩码和位置嵌入。：

|  | $\displaystyle\mathbf{O}_{\text{pre}}$ | $\displaystyle=\text{softmax}\left(\frac{\mathbf{Q}_{\text{pre}}\cdot\mathbf{K}_{\text{pre}}^{T}}{\sqrt{d}}\right)\cdot\mathbf{V}_{\text{pre}}\cdot\mathbf{W}_{o}+\mathbf{X}_{\text{pre}},$ |  |
| --- | --- | --- | --- |

其中 MHA 的输出$\mathbf{O}_{\text{pre}}\in\mathbb{R}^{n\times d}$被发送到 MLP。MLP 的输出作为下一个 Transformer 层的输入。

解码阶段是 LLM 推理过程的核心。在解码阶段，模型使用之前准备好的 KV 缓存，并可能向其中添加新信息。这里的目标是生成令牌，实际上就是单词或词的一部分。这是逐步进行的。每个新令牌的生成都受到之前生成的令牌的影响，就像逐字构建句子一样。

在解码阶段，MHA 加载之前存储的 KV 缓存$\mathbf{K}_{\text{cache}}$和$\mathbf{V}_{\text{cache}}$。输入是$\mathbf{X}_{\text{dec}}\in\mathbb{R}^{1\times d}$。新的键值对被计算并连接到现有缓存中：

|  | $\displaystyle\text{查询:}\quad\mathbf{Q}_{\text{dec}}$ | $\displaystyle=\mathbf{X}_{\text{dec}}\cdot\mathbf{W}_{q}$ |  |
| --- | --- | --- | --- |
|  | $\displaystyle\text{键:}\quad\mathbf{K}_{\text{cat}}$ | $\displaystyle=[\mathbf{K}_{\text{cache}},\mathbf{X}_{\text{dec}}\cdot\mathbf{W% }_{k}]$ |  |
|  | $\displaystyle\text{值:}\quad\mathbf{V}_{\text{cat}}$ | $\displaystyle=[\mathbf{V}_{\text{cache}},\mathbf{X}_{\text{dec}}\cdot\mathbf{W% }_{v}]$ |  |

新计算的$\mathbf{X}_{\text{dec}}\cdot\mathbf{W}_{k}$和$\mathbf{X}_{\text{dec}}\cdot\mathbf{W}_{v}$随后被附加到 KV 缓存中。MHA 中的其他计算如下进行：

|  | $\displaystyle\mathbf{O}_{\text{dec}}$ | $\displaystyle=\text{softmax}\left(\frac{\mathbf{Q}_{\text{dec}}\cdot\mathbf{K}% _{\text{cat}}^{T}}{\sqrt{d}}\right)\cdot\mathbf{V}_{\text{cat}}\cdot\mathbf{W}% _{o}+\mathbf{X}_{\text{dec}}$ |  |
| --- | --- | --- | --- |

MHA 的输出$\mathbf{O}_{\text{dec}}\in\mathbb{R}^{1\times d}$被送到 MLP。最后的 Transformer 层的输出被送到最终预测层以预测下一个令牌。

### 2.2 Roofline 模型

评估 LLMs 在特定硬件上的部署效率涉及对硬件和模型特性的全面考虑。为了进行这种评估，我们使用 Roofline 模型。Roofline 模型作为一种有效的理论框架，用于评估在特定硬件上部署模型的潜在性能。

![参见标题](img/ebb17c4cc7cc9df00a33d741a1bf8410.png)

图 4：在硬件上执行操作。

如图[4](https://arxiv.org/html/2402.16363v6#S2.F4 "Figure 4 ‣ 2.2 Roofline Model ‣ 2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")所示，神经网络层在硬件设备上的执行涉及将数据从内存（DDR 或 HBM）转移到片上缓冲区，然后由片上处理单元执行计算，最终将结果输出回内存。因此，评估性能需要同时考虑内存访问和处理单元的能力。如果一个层涉及大量计算但内存访问很少，它被称为计算瓶颈。这种情况会导致内存访问处于空闲状态。相反，当一个层需要大量内存访问但计算需求较少时，它被称为内存瓶颈。在这种情况下，计算单元的利用率较低。我们可以通过 Roofline 模型清晰区分这两种情况，并为不同情况提供性能上限。

![参见说明](img/1a659a5b01c2ef160b61ce311c78d792.png)

图 5：Nvidia A6000 GPU 的 Roofline 模型演示。计算以 FP16 进行。

使用 Roofline 模型有两个步骤：

1\. 绘制 Roofline：确定目标硬件设备的峰值计算性能（每秒操作次数，OPS）和峰值内存带宽（每秒字节数）。OPS 指的是每秒的操作次数。每个乘法-累加（MAC）操作计算两个操作。然后创建一个图表，纵轴为性能（OPS），横轴为算术强度（OPs/byte）：绘制一条与峰值计算性能相等的水平线。这条线代表硬件设备能够实现的最大性能。并绘制一条从原点开始、斜率等于峰值内存带宽的对角线。这条线代表系统上可用的最大内存带宽，称为内存 Roofline。图[5](https://arxiv.org/html/2402.16363v6#S2.F5 "Figure 5 ‣ 2.2 Roofline Model ‣ 2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")演示了 Nvidia A6000 GPU 的 Roofline 模型。

2\. 分析层的性能：通过量化每层的操作次数（OPs）和从内存中访问的数据量（字节），评估模型中每层的性能。通过将所需的操作次数除以传输的数据量，计算每层的算术强度（OPs/byte）。根据第一步中创建的图表，每层的理论最大性能由图表上对应于算术强度的 x 轴值的位置决定。这使我们能够确定系统在这一点上是内存瓶颈还是计算瓶颈，从而指导后续的优化策略。

表 1：使用 Nvidia A6000 GPU 的 Roofline 模型对 Llama-2-7b 层的分析。在此示例中，序列长度为 2048，批量大小为 1。

| 层名称 | OPs |
| --- | --- |

&#124; 内存 &#124;

&#124; 访问 &#124;

|

&#124; 算术 &#124;

&#124; 强度 &#124;

|

&#124; 最大值 &#124;

&#124; 性能 &#124;

| 绑定 |
| --- | --- | --- | --- | --- | --- |
| 预填充 |
| --- |
| q_proj | 69G | 67M | 1024 | 155T | 计算 |
| k_proj | 69G | 67M | 1024 | 155T | 计算 |
| v_proj | 69G | 67M | 1024 | 155T | 计算 |
| o_proj | 69G | 67M | 1024 | 155T | 计算 |
| gate_proj | 185G | 152M | 1215 | 155T | 计算 |
| up_proj | 185G | 152M | 1215 | 155T | 计算 |
| down_proj | 185G | 152M | 1215 | 155T | 计算 |
| qk_matmul | 34G | 302M | 114 | 87T | 内存 |
| sv_matmul | 34G | 302M | 114 | 87T | 内存 |
| softmax | 671M | 537M | 1.25 | 960G | 内存 |
| norm | 59M | 34M | 1.75 | 1T | 内存 |
| add | 8M | 34M | 0.25 | 192G | 内存 |
| 解码 |
| q_proj | 34M | 34M | 1 | 768G | 内存 |
| k_proj | 34M | 34M | 1 | 768G | 内存 |
| v_proj | 34M | 34M | 1 | 768G | 内存 |
| o_proj | 34M | 34M | 1 | 768G | 内存 |
| gate_proj | 90M | 90M | 1 | 768G | 内存 |
| up_proj | 90M | 90M | 1 | 768G | 内存 |
| down_proj | 90M | 90M | 1 | 768G | 内存 |
| qk_matmul | 17M | 17M | 0.99 | 762G | 内存 |
| sv_matmul | 17M | 17M | 0.99 | 762G | 内存 |
| softmax | 328K | 262K | 1.25 | 960G | 内存 |
| norm | 29K | 16K | 1.75 | 1T | 内存 |
| add | 4K | 16K | 0.25 | 192G | 内存 |

有两种情况资源未被充分利用：当模型的计算强度低于拐点，位于红色区域时，这意味着每次内存访问所需的计算工作负载较低。即使达到峰值带宽，也未能充分利用所有计算资源。在这种情况下，该层受内存访问的限制（内存绑定），一些计算单元可能处于空闲状态。如果层受内存限制，可以考虑量化、内核融合和增加批量大小等优化技术来减轻内存占用。相反，如果模型的计算强度高于拐点，位于绿色区域，则说明模型仅需少量内存访问即可消耗大量计算能力。这意味着该层受计算限制（计算绑定），一些内存单元可能处于空闲状态。在这种情况下，我们应研究启用低位计算等策略以提高计算效率。后续部分将提供这些方法的详细说明。

例如，表格 [1](https://arxiv.org/html/2402.16363v6#S2.T1 "Table 1 ‣ 2.2 Roofline Model ‣ 2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 展示了使用 Roofline 模型在 Nvidia A6000 GPU 上对 Llama-2-7b 层的分析。从表中可以看出，在预填充阶段，大部分计算是计算绑定的，导致性能高。相反，在解码阶段，所有计算都是内存绑定的，导致性能显著低于 GPU 计算单元的计算能力。在用户与大型模型互动时，预填充阶段仅执行一次，而解码阶段则重复执行以生成连续输出。因此，为了解码阶段的内存绑定特性进行优化对于提升大型模型的推理性能至关重要。

### 2.3 LLM-Viewer

在大型语言模型（LLMs）中存在多个 Transformer 层，每层包含各种操作。此外，不同的 LLMs 拥有不同的操作集。此外，我们还需要跟踪信息，如内存占用，以计算峰值内存使用和总推理时间。因此，分析 LLMs 涉及网络范围的关注点。在本节中，我们提出了一个强大的工具，LLM-Viewer ³³3 该工具的开源地址是 https://github.com/hahnyuan/LLM-Viewer，用于执行网络范围的分析。它支持在各种硬件平台上分析 LLM 的性能和效率，为 LLM 的推理和性能优化提供了宝贵的见解。

LLM-Viewer 的工作流程如图 [1](https://arxiv.org/html/2402.16363v6#S1.F1 "Figure 1 ‣ 1 Introduction ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 所示。其步骤包括：（1）输入 LLM 并收集每一层的关键信息，例如计算量、输入和输出张量的形状以及数据依赖关系。（2）为硬件提供输入，生成一个考虑到硬件计算能力和内存带宽的 Roofline 模型。（3）配置推理设置，包括批处理大小、提示令牌长度和生成令牌长度。（4）配置优化设置，如量化位宽、FlashAttention 的使用、解码方法以及其他系统优化技术。（5）LLM-Viewer 分析器利用 Roofline 模型和层信息来分析每层的性能。它还跟踪每层的内存使用情况，并根据数据依赖关系计算峰值内存消耗。通过汇总所有层的结果，可以获得 LLM 的整体网络性能。（6）生成报告，提供每层和网络的最大性能和性能瓶颈信息，以及内存占用。可以从报告中绘制批处理大小-性能曲线和序列长度-性能曲线，以了解不同设置对性能的影响。（7）LLM-Viewer 提供一个网页查看器，方便可视化网络架构和分析结果。该工具便于调整配置，并提供对每层各种数据的访问。

## 3 模型压缩

大型语言模型（LLMs）的庞大规模和计算需求对实际部署提出了重大挑战，尤其是在资源有限的环境中。为缓解这些限制，最直接的解决方案是压缩 LLM。在本节中，我们回顾了 LLM 神经网络压缩的概念。这一探索包括对已建立技术的全面审查，包括但不限于量化、剪枝、知识蒸馏和低秩分解。在每个小节中，我们将利用 LLM-Viewer 分析网络压缩对 LLM 推理的影响。基于我们的分析，我们将提供优化建议。

### 3.1 量化

在 LLM 压缩领域，量化已成为缓解这些模型显著存储和计算开销的关键技术。本质上，量化涉及将原始 LLM 中的浮点值转换为整数或其他离散形式，这一过程显著减少了存储需求和计算复杂性 [Gholami et al., [2022](https://arxiv.org/html/2402.16363v6#bib.bib62)]。虽然该过程固有一些精度损失，但精心设计的量化技术可以在对准确性影响最小的情况下实现显著的模型压缩。LLM 中的量化主要可以分为两个方向：压缩预训练 LLM 的量化和参数高效微调（Q-PEFT）的量化。第一类包括将量化应用于 LLM，以将量化 LLM 作为预训练模型使用。这一类又可以进一步分为两个子类：量化感知训练（QAT）和训练后量化（PTQ）。QAT 将量化集成到模型的训练过程中或在预训练 LLM 的微调/再训练期间，使模型从一开始就适应量化。相比之下，PTQ 在模型完成训练阶段后应用量化，提供了一种更简单的模型压缩方法，无需重新训练。这些不同的方法突显了量化技术在满足 LLM 部署特定需求和约束方面的多样性。

#### 3.1.1 LLM-Viewer 的一个使用案例：

量化的 Roofline 分析

在这里，我们提供了一个如何使用我们的 LLM-Viewer（第[2.3 节](https://arxiv.org/html/2402.16363v6#S2.SS3 "2.3 LLM-Viewer ‣ 2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")）来分析 LLM 部署瓶颈的示例。在 LLM 中，张量包括权重和激活，其中激活包括临时激活和 KV 缓存。 (1) LLM 权重必须存储在内存中。例如，Llama-13b [[Touvron et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib196)]，拥有 130 亿个权重，FP16 格式下大约占用 26GB 的内存。(2) 在推理过程中会生成临时激活。例如，每个变换器层的输入会保留在内存中，直到残差加法执行。(3) 对于自回归 LLM，将键和值激活（KV 缓存）缓存到内存中对于后续的令牌生成是必要的。我们利用 LLM-Viewer 从计算、内存消耗和内存访问三个方面分析量化对这些张量的影响。

![参见说明](img/b70cd20838f82652e09cae77fa4eec83.png)

图 6：不同计算数据类型下，Nvidia A6000 GPU 的 Roofline 模型演示。

![参考说明](img/3aa5d7ae0235d0a558fb54e0bffad5c5.png)

图 7：不同量化设置下 Llama-2-13b 的相对内存消耗。Tmp Act 指代临时激活。

计算：最新的计算设备，如 NVIDIA GPU，通常支持 FP32、FP16 和 INT8 数据类型进行计算。硬件设备在处理较小位宽的数据时通常表现更好。例如，NVIDIA 的 A6000 GPU 能够以 155 TOP/s 和 310 TOP/s 的速度分别执行 FP16 的两倍。根据 Roofline 模型，当启用量化以加快计算速度时，roofline 高度会增加，这表示计算密集型层的性能得到提升。如图 [6](https://arxiv.org/html/2402.16363v6#S3.F6 "图 6 ‣ 3.1.1 LLM-Viewer 的一个用例：量化的 Roofline 分析 ‣ 3.1 量化 ‣ 3 模型压缩 ‣ LLM 推理揭秘：调查和 Roofline 模型见解") 所示，使用 INT8 计算时，最大性能得到了提高。然而，为了利用 INT8 的计算能力，所有输入操作数必须为 INT8 格式。因此，如果只有权重被量化为 INT8，而激活保持在 FP16 格式，则无法利用 INT8 的计算能力。相反，INT8 权重需要转换为 FP16，以便与 FP16 激活进行乘法。此外，当张量被量化到硬件不支持的位宽时，它们需要转换为更高位宽进行计算。例如，NVIDIA H100 GPU 不支持 INT4 计算。因此，如果权重或激活被量化为 INT4，则需要转换为更高的位宽，如 INT8 或 FP16，以进行计算。

内存消耗：不同张量的量化导致内存消耗的减少程度各异，如图[7](https://arxiv.org/html/2402.16363v6#S3.F7 "Figure 7 ‣ 3.1.1 A Use Case of LLM-Viewer: Roofline Analysis for Quantization ‣ 3.1 Quantization ‣ 3 Model Compression ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")所示。在我们的记号中，W4 表示将权重量化为 4 位，同时保持激活在 FP16 格式。W4A4 表示权重和激活均量化为 4 位。在 W4KV4 的情况下，权重和 KV 缓存被量化，而临时激活保持在 FP16 格式。值得注意的是，临时激活的内存使用相对较低，特别是在解码阶段。这可以归因于它们的短暂寿命，使其在完成任务后可以释放内存。另一方面，分配给 KV 缓存的内存行为不同。在生成完整答案的整个过程中，KV 缓存的内存不能被释放，这需要多次推理通过网络。此外，随着批量大小的增加和输入序列的延长，KV 缓存的内存消耗也会增加。这是因为模型需要存储更多的键值对（KV）以促进其操作。

内存访问：在 LLM 中量化张量可以显著减少内存访问，从而减少为相同计算量移动的数据字节数。这种算术强度的提高有助于 Roofline 模型，导致三种情况：(1) 量化后，算术强度仍在内存绑定范围内。随着算术强度的提升，平均每次计算的数据访问量减少，缓解了对数据内存访问的压力。因此，理论性能得到提升。这可以大大提升在内存绑定解码阶段的性能。(2) 算术强度从内存绑定转变为计算绑定。这种转变也减少了对数据内存访问的压力，从而提高了理论性能。(3) 量化前后，算术强度始终保持在计算绑定范围内。在这种情况下，性能没有改善。例如，这种情况可能发生在计算绑定的预填充阶段或解码阶段当批量大小较大时。

如图[8](https://arxiv.org/html/2402.16363v6#S3.F8 "图 8 ‣ 3.1.1 LLM-Viewer 的应用案例：量化的 Roofline 分析 ‣ 3.1 量化 ‣ 3 模型压缩 ‣ LLM 推理揭示：调查与 Roofline 模型见解")所示，当批量大小较小时时，网络中的层在量化前后都受内存限制。因此，量化可以提高性能并减少网络的推理时间。然而，当批量大小较大时，将网络的权重从 4 位压缩到 2 位或 1 位不会导致推理时间的减少。这是因为此时网络已经受到计算限制，量化权重变得无效。与前一种情况类似，系统的行为在预填充阶段可能会出现饱和效应。如图[9](https://arxiv.org/html/2402.16363v6#S3.F9 "图 9 ‣ 3.1.1 LLM-Viewer 的应用案例：量化的 Roofline 分析 ‣ 3.1 量化 ‣ 3 模型压缩 ‣ LLM 推理揭示：调查与 Roofline 模型见解")所示，当序列长度较小时，预填充阶段受到内存限制。在这种情况下，应用量化可以通过减少网络的内存访问需求来提高性能。然而，随着序列长度的增加，预填充阶段变得更加受计算限制。因此，当网络在预填充阶段已经受计算限制并且序列长度较大时，量化权重可能不会带来显著的性能提升。

![参考说明](img/b5dd8a4974f126b9fcaa8e5bd2dcaf58.png)

图 8：Llama-2-13b 在不同量化设置下的解码阶段推理时间。（序列长度=1024）

![参考说明](img/3056f7567a8d8df15b27f17313e6bd21.png)

图 9：Llama-2-13b 在不同量化设置下的预填充阶段推理时间。（批量大小=1）

#### 3.1.2 压缩预训练 LLM 的量化

在量化感知训练（QAT）[Courbariaux et al., [2015](https://arxiv.org/html/2402.16363v6#bib.bib29), Choi et al., [2018](https://arxiv.org/html/2402.16363v6#bib.bib24), Dong et al., [2019](https://arxiv.org/html/2402.16363v6#bib.bib48)]中，量化过程被无缝集成到大型语言模型（LLMs）的训练中，使它们能够适应低精度表示，从而减轻精度损失。LLM-QAT [[Liu et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib140)] 创新性地解决了 LLMs 训练数据获取的挑战，通过无数据蒸馏，利用预训练模型的输出来免除大量数据收集的需要。此外，LLM-QAT 将量化扩展到权重和激活之外，包括关键值（KV）缓存，提高了吞吐量并支持更长的序列依赖性。其成功将大型 Llama 模型蒸馏为 4 位量化权重和 KV 缓存，强调了准确量化 4 位 LLMs 的潜力。

为实现更低位的量化，例如低于 2 位，[Kim et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib104) 提出了针对 LLMs 的三元 QAT 的 Token-Scaled Logit Distillation (TSLD)方法。该方法使用了一种自适应知识蒸馏技术，基于 token 置信度修改 Logit 知识蒸馏，在 LLM QAT 过程中提供量身定制的指导。此外，Shang et al., [[2024](https://arxiv.org/html/2402.16363v6#bib.bib178)] 关注于 PB-LLM 中部分二值化矩阵的显著权重。通过在更高位保存这些关键权重，PB-LLM 有效地保持了高度量化 LLMs 的推理能力。此外，PB-LLM 还通过确定二值化 LLMs 的最佳缩放因子来探索最小化量化误差，这在保持模型在激进量化下的有效性方面至关重要。

![参见说明](img/c83e69920eb76c9c681272549a16b4d8.png)

图 10：2022 年至 2024 年 LLM 方法的量化时间线。红色突出显示的方法代表它们属于参数高效微调（Q-PEFT）的量化，绿色突出显示的方法代表它们属于 QAT 相关方法，其他为 PTQ 基础的方法。

后训练量化（PTQ）

后训练量化（PTQ）是一种优化大规模语言模型（LLMs）的关键技术，它涉及在 LLM 训练阶段后对模型参数进行量化。PTQ 的主要目标是减少 LLM 的存储需求和计算复杂性，而无需对模型架构进行更改或重新训练。这种方法以其简单性和高效性而脱颖而出，特别是在实现显著的模型压缩方面。在通常包含数十亿参数的 LLM 的背景下，量化感知训练（QAT）由于训练成本过高，往往变得不切实际。因此，PTQ 成为这些大规模模型的更可行的解决方案。然而，必须承认的是，PTQ 可能会因为量化过程而导致一定程度的精度损失。尽管如此，PTQ 仍然是一种有效的方法，可以提高 LLM 的效率，提供了一种避免重大修改或大量额外训练的简单解决方案。

在 PTQ 中，各种方法专注于仅对权重进行量化，以提高效率。例如，LUT-GEMM [Park et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib162)] 使用仅对权重进行量化和 BCQ 格式来优化 LLMs 中的矩阵乘法，从而减少延迟并提高计算效率。LLM.int8() [Dettmers et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib38)] 采用 8 位量化，这在推理过程中将 GPU 内存使用量减少了一半，并通过按向量量化和混合精度分解保持精度。这种方法使得在高达 1750 亿参数的模型中实现高效推理成为可能。ZeroQuant [Yao et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib225)] 结合了对硬件友好的量化方案和逐层知识蒸馏，将权重和激活值优化为 INT8，且精度损失最小。针对更高的压缩目标，GPTQ [Frantar et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib55)] 引入了一种基于近似二阶信息的逐层量化技术，将每个权重减少到 3-4 位，且精度损失最小。此外，Dettmers 和 Zettlemoyer 的研究，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib41)] 探讨了模型大小与位精度之间的平衡，特别是在零样本性能方面，发现 4 位精度通常提供了最佳平衡。像 AWQ [Lin et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib135), [Kim et al., 2023c,](https://arxiv.org/html/2402.16363v6#bib.bib105)] 这样的创新表明，保护少量显著权重可以显著减少量化误差。AWQ 采用了基于激活的量化方法，关注激活幅度较大的权重通道，并结合每通道缩放以实现最佳量化。OWQ [Lee et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib117)] 分析了激活异常值如何放大量化误差，引入了混合精度方案，将更高的精度分配给受这些异常值影响的权重。SpQR [[Dettmers et al., 2023b,](https://arxiv.org/html/2402.16363v6#bib.bib40)] 采用了一种独特的方法，将异常权重隔离存储于更高精度中，同时将其余部分压缩至 3-4 位。这种技术允许更高效的压缩，同时保持接近无损的性能。QuantEase [Behdin et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib10)] 建议使用坐标下降方法来优化网络中的所有权重，从而提高量化效率。

为实现更低位量化（例如，低于 2 位），QuIP [Chee et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib17)] 引入了一种创新的方法，考虑了权重幅度的均匀分布以及准确舍入方向与坐标轴不对齐的意义。QuIP 包括一个自适应舍入过程，最小化一个二次代理目标，对于优化量化过程至关重要。此外，它采用高效的预处理和后处理技术，通过与随机正交矩阵的乘法确保权重和 Hessian 的不相关性，这对于保持量化效果至关重要。进一步推进 PTQ 方法，[Li et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib123) 受到这样一个观察的启发：将量化的激活分布与其浮点对应物对齐可以恢复 LLM 的准确性。他们提出的“Norm Tweaking”策略涉及一个精细的校准数据生成过程和通道级距离约束。这种方法更新归一化层的权重，从而提高了泛化能力。[Shang et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib178)] 提出了部分二值化 LLM (PB-LLM)，通过将二值化 [Hubara et al., , [2016](https://arxiv.org/html/2402.16363v6#bib.bib93)] 引入 LLM 量化中，以推动权重量化低于 2 位。继 PB-LLM 之后，BiLLM [Huang et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib90)] 将权重量化推向几乎 1 位。

除了专注于 LLM 中权重量化的努力外，许多 PTQ 方法也关注权重和激活的量化。SmoothQuant [[肖等, 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib215)] 解决了量化激活的挑战，因为激活的量化可能由于存在异常值而变得复杂。它引入了一种每通道缩放变换，有效地平滑了激活幅度，使模型对量化的接受能力更强。认识到 LLM 中激活量化的复杂性，RPTQ [[袁等, 2023c,](https://arxiv.org/html/2402.16363v6#bib.bib232)] 强调了通道之间范围的不均匀性以及异常值的普遍存在。RPTQ 的创新方法涉及对通道进行量化聚类，从而减少通道范围的不一致性。这种方法巧妙地将通道重新排序集成到层归一化和线性层权重中，以最小化开销。OliVe [[郭等, 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib69)] 采用了异常值受害者对（OVP）量化策略，重点在于局部处理异常值，具有低硬件开销和显著的性能优势。这种方法源于这样一个理解：异常值至关重要，而相邻的正常值则不那么重要。基于此，Outlier Suppression+ 扩展了这一概念，通过解决特定通道中不对称分布的有害异常值来改进。它引入了通道级别的平移和缩放操作，以平衡异常值的分布，并减少有问题的通道的影响，同时考虑了异常值的性质和随后的量化误差。ZeroQuant-FP [[吴等, 2023d,](https://arxiv.org/html/2402.16363v6#bib.bib210)] 探讨了浮点（FP）量化，特别是 FP8 和 FP4 格式。这项研究发现 LLM 中的 FP8 激活量化优于传统的 INT8 格式，而 FP4 权重量化显示出与 INT4 相当的效果。ZeroQuant-FP 通过将所有缩放因子标准化为 2 的幂，并将它们限制在一个计算组内，解决了权重和激活之间的差异，确保了量化过程的一致性和效率。 [李等, 2023c](https://arxiv.org/html/2402.16363v6#bib.bib126) 提出了 FPTQ，其中他们采用了逐层策略来应对不同级别的量化难度。特别是，他们设计了一种离线对数激活均衡，以使以前难以处理的层具有适合量化的分布。

![参见说明](img/e8558e92e4e2dd65a15c6abd02f7105c.png)

图 11：Llama-2-13b 在不同量化设置下的解码阶段内存消耗。（批量大小=1）。

自 2023 年底以来，token 的长度显著增加，导致 KV 缓存消耗更多内存。例如，Google Gemini 1.5 [Sundar Pichai, , [2024](https://arxiv.org/html/2402.16363v6#bib.bib192)] 在生产中可以处理最多 100 万个 tokens，而处理书籍、大型图像或视频的 LLMs 将需要数万个 tokens。因此，KV 缓存量化的优化变得越来越重要。2024 年几篇最新的论文集中于改进 KV 缓存量化。例如，Hooper et al., [[2024](https://arxiv.org/html/2402.16363v6#bib.bib83)] 提出了一个通过 KV 缓存量化实现 1000 万上下文长度 LLM 推断的解决方案。KIVI [[Liu et al., 2024b,](https://arxiv.org/html/2402.16363v6#bib.bib142)] 将 KV 缓存的量化推进到 2 位。Yue et al., [[2024](https://arxiv.org/html/2402.16363v6#bib.bib234)] 提出了 WKVQuant，旨在联合优化 LLMs 中权重和 KV 缓存的量化，使 W4KV4 具有与 W4 相同的性能。如图 [11](https://arxiv.org/html/2402.16363v6#S3.F11 "图 11 ‣ 3.1.2 压缩预训练 LLMs 的量化 ‣ 3.1 量化 ‣ 3 模型压缩 ‣ LLM 推断揭示：调查与 Roofline 模型见解") 所示，我们使用 LLM-Viewer 分析 KV 缓存量化的内存减少情况。当序列长度超过 50k 时，可以观察到 KV 缓存占用了大部分内存，其量化可以显著降低内存消耗。

#### 3.1.3 参数高效微调的量化（Q-PEFT）

参数高效微调（PEFT）是大型语言模型（LLMs）中的一个重要话题。最受欢迎的方法之一是低秩适配（LoRA）[Hu et al., , [2021](https://arxiv.org/html/2402.16363v6#bib.bib86), Valipour et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib199)]，其关键见解是将适配器权重分解为两个低秩（因此参数高效）矩阵的乘积。LoRA 声称其性能与全面微调相当，同时使用的可学习参数要少得多。有关该适配器的更多细节，请参阅综述论文 [Hu et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib87)]。

除了明确的量化范式之外，一种新型的 LLM 效率范式正在出现：参数高效微调的量化（Q-PEFT）。这种方法将量化整合到 LLM 的微调过程中，提供了一种独特且高效的方法，特别是在大型模型时代非常相关。该范式中的开创性工作，如 PEQA [[Kim et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib103) ]、DFT [[Li et al., 2023e,](https://arxiv.org/html/2402.16363v6#bib.bib130) ]和 QLORA [[Dettmers et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib39) ]展示了这一方法的可行性和有效性。PEQA 采用双阶段过程，其中第一阶段涉及将每个全连接层的参数矩阵量化为低位整数矩阵，并配以一个标量向量。第二阶段则专注于针对特定下游任务微调标量向量，从而实现更加高效的任务特定调整。DFT 采用高效的 Lion 优化器，该优化器只跟踪动量，并为每个参数保持一致的更新幅度，这对于稳健的量化具有固有优势；（ii）我们对所有模型状态进行量化，并将其存储为整数值，同时提出了一种量化权重的梯度流和参数更新方案。另一方面，QLORA 引入了新的概念，如新的数据类型、双重量化和分页优化器。这些创新旨在高效节省内存，同时保持 LLM 微调性能。值得注意的是，QLORA 使得在单个 GPU 上进行大型模型的微调成为可能，并在 Vicuna 基准测试中取得了领先的结果，这证明了其在平衡内存效率和模型性能方面的有效性。

然而，QLoRA 的一个限制是其在微调过程中最多仅支持 4 位量化；如 2 位等低位量化会显著降低性能。为应对这一挑战，多个研究已经涉足 Q-PEFT 领域，以实现低位量化。LQ-LoRA [[Guo et al., 2023b,](https://arxiv.org/html/2402.16363v6#bib.bib71)]引入了一种迭代算法，将每个预训练矩阵分解为高精度低秩组件和内存高效的量化组件。在微调过程中，仅更新低秩组件，而保持量化组件固定。该方法提出了一种整数线性规划方法，用于量化组件，允许在给定内存预算内动态配置量化参数，如位宽和块大小。另一个值得注意的方法，Loft-Q [[Li et al., 2023d,](https://arxiv.org/html/2402.16363v6#bib.bib128)]，同时量化 LLM 并建立适用于 LoRA 微调的低秩初始化。这一策略有效地弥合了量化模型和全精度模型之间的差距，显著提升了下游任务的泛化能力。QA-LoRA [[Xu et al., 2023c,](https://arxiv.org/html/2402.16363v6#bib.bib223)]利用将 LLM 权重量化为低位整数的优势，促进了高效的微调阶段。此外，它生成了一个轻量级的微调模型，避免了通常与 PTQ 相关的精度损失。

#### 3.1.4 LLM 量化讨论

图[10](https://arxiv.org/html/2402.16363v6#S3.F10 "Figure 10 ‣ 3.1.2 Quantization for Compressing Pre-trained LLMs ‣ 3.1 Quantization ‣ 3 Model Compression ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")展示了 LLM 量化技术的时间线，突显了从作为初期主流方法的后训练量化（PTQ）到量化感知训练（QAT）和参数高效微调量化（Q-PEFT）逐渐突出的演变。这一转变强调了社区在应对 PTQ 性能瓶颈时的适应，标志着 QAT 和 Q-PEFT 作为追求高效 LLM 推断的新兴关注领域。

### 3.2 剪枝

剪枝 [LeCun et al., , [1989](https://arxiv.org/html/2402.16363v6#bib.bib116), Liang et al., , [2021](https://arxiv.org/html/2402.16363v6#bib.bib133)]，集中于识别和消除被认为不必要或冗余的模型参数，是另一种流行的压缩 LLM 技术。在 LLM 的背景下，参数通常占据了模型大小和计算需求的相当一部分。通过仔细剪枝这些参数，可以简化模型，使其更高效，而不会显著影响其性能。剪枝方法大致可以分为两类：无结构剪枝和结构化剪枝，下面我们将逐一描述每种类别的研究进展。

#### 3.2.1 无结构剪枝

无结构剪枝选择性地消除模型中的个别权重或神经元，导致一个更加稀疏但结构不规则的网络。这种剪枝方式在确保模型准确性方面表现优异，然而，权重分布的不规则性需要专门的处理或软件优化。SparseGPT [Frantar and Alistarh, , [2023](https://arxiv.org/html/2402.16363v6#bib.bib54)] 是一种针对 LLM 的开创性一次性剪枝方法。它通过将剪枝挑战重新构思为一系列广泛的稀疏回归问题，并由新开发的求解器高效解决。值得注意的是，SparseGPT 能够在单个 GPU 上在短短几小时内高效处理一个具有 1750 亿参数的模型，并且可以在不显著牺牲准确性或需要微调的情况下诱导 LLM 显著的稀疏性（50-60%）。为了解决 SparseGPT 中重建成本的问题，[Sun et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib187) 提出了 Wanda，它通过评估每个权重的大小和相应输入的范数来评估其重要性，从而显著提高计算效率。此外，[Yin et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib227) 设计了一组非均匀分层稀疏性比率，以更多关注出现异常值较多的层，从而提高剪枝性能。此外，考虑到对无结构剪枝的硬件支持，Flash-LLM [[Xia et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib212)] 提出了一个无结构稀疏矩阵乘法方法，其特点是稀疏加载和密集计算，以实现 GPU Tensor Core 对无结构稀疏性的高级支持。

#### 3.2.2 结构化剪枝

结构化剪枝去除整个神经元或层， resulting in a cleaner, more regular structure. 剪枝后的模型通常与传统硬件更兼容，但这种简单性和规则性是有代价的：这种形式的剪枝可能对模型性能产生更明显的影响，因为它涉及移除更大、潜在更关键的组件。 LLM-Pruner [Ma et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib144)] 代表了一种在 LLM 结构化剪枝方面的开创性方法。它采用了一次性剪枝技术，该技术依赖于一阶和估计的 Hessian 数据，并需要随后使用 LoRA 进行微调以恢复权重。这项工作具有显著的优势，因为它显著降低了计算需求和内存要求，同时保持了 LLM 的基本结构。 Sheared Llama [[Xia et al., 2023b,](https://arxiv.org/html/2402.16363v6#bib.bib214) ] 提出了另一种值得注意的解决方案，通过结合有针对性的结构化剪枝与动态批处理加载算法。首先，它通过分析预训练模型的配置，仔细地将源模型修剪为所需的目标架构。然后，它通过动态批处理加载算法提高训练效率，该算法调整来自不同领域的训练数据的比例。 Compresso [[Guo et al., 2023c,](https://arxiv.org/html/2402.16363v6#bib.bib74) ] 建立了一个协作学习框架，其中 LLM 和一种资源高效的剪枝算法协同工作，能够将 Llama-7B 剪枝至 5.4B，同时保留原始性能。

### 3.3 知识蒸馏

知识蒸馏 [Hinton et al., , [2015](https://arxiv.org/html/2402.16363v6#bib.bib78), Gou et al., , [2021](https://arxiv.org/html/2402.16363v6#bib.bib63)] 是一种技术，它有助于将更大模型（称为“教师”）的能力转移到更小的模型（称为“学生”），使得更小的模型可以以与更大模型相似的能力执行任务，但所需计算资源减少 [Gou et al., , [2021](https://arxiv.org/html/2402.16363v6#bib.bib63), Shang et al., , [2021](https://arxiv.org/html/2402.16363v6#bib.bib177)]。对于 LLM 压缩，有两种主要的知识蒸馏类别：白盒和黑盒蒸馏。在这些类别中，研究人员开发了一系列针对 LLM 的蒸馏方法，下面详细描述了这些方法。此外，还进行了有关 LLM 知识蒸馏的更详细和具体的调查 [Xu et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib222)]。

#### 3.3.1 白盒知识蒸馏

在白箱蒸馏中，教师模型的架构和权重是完全可访问的。这种透明性使得学生模型不仅可以学习教师模型的输出，还可以学习其内部表示和决策过程。MiniLLM [Gu et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib68)] 批评了标准知识蒸馏目标的局限性，并建议反向 Kullback-Leibler 散度在捕捉生成任务的复杂性方面更有效，这可以提高学生模型的响应质量和可靠性。MiniLLM 还引入了单步正则化、教师混合采样和长度归一化，以应对训练中的挑战，从而在标准基准上展示了出色的性能潜力。与 MiniLLM 相比，GKD [Agarwal et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib2)] 提出了一个更简单和稳定的方法。它通过避免通过学生模型的采样进行反向传播，更贴近监督训练。GKD 不使用预定的输出序列，而是让学生模型在自己创建的序列上进行训练，利用教师的概率作为指导，从而显著改善学生模型的表现。Homotopic distillation [[Liang et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib131)] 旨在促进学生模型预测与教师模型在广泛开放域数据上的对齐。它涉及从教师模型的配置开始学生模型，并逐步减少学生模型的神经元，以达到指定的模型复杂度。此外，[Liang et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib132) 提出了一个逐层蒸馏方法，该方法为每层教师和学生模型创建独特的任务感知过滤器。这些过滤器，实际上是配备了任务特定头部的神经网络，旨在蒸馏和捕捉来自各自模型隐藏层的预测知识。AD-KD [[Wu et al., 2023b,](https://arxiv.org/html/2402.16363v6#bib.bib208)] 分析了教师模型的 token 级推理，利用集成梯度将归因知识转移到学生模型，从而使学生模型能够模仿教师的潜在推理，而不仅仅是其行为。

#### 3.3.2 黑箱知识蒸馏

与白盒蒸馏不同，黑盒蒸馏不需要访问教师模型的内部信息。相反，它专注于复制教师模型的输出行为。学生模型仅从教师生成的输入-输出配对中学习，而对其内部操作没有任何洞察。Multitask-ICT [黄等人, 2022](https://arxiv.org/html/2402.16363v6#bib.bib91) 引入了上下文学习蒸馏，将上下文学习的目标与语言建模的目标相结合，旨在将理解上下文示例的能力以及特定任务所需的知识蒸馏到较小的模型中。LaMini-LM [[吴等人, 2023a](https://arxiv.org/html/2402.16363v6#bib.bib206)] 创建了一组 258 万条指令，并利用 GPT-3.5 Turbo 生成对这些指令的响应。随后，它使用这些指令作为基础，对一系列学生模型进行微调。类似地，Sahu 等人[[2023](https://arxiv.org/html/2402.16363v6#bib.bib169)] 提出了 PromptMix，这是一种基于提示的两步法，用于为文本分类创建标记示例。在 PromptMix 中，边界示例可以增强从教师模型（如 GPT-3.5）到学生模型的知识转移。与传统的单向知识蒸馏不同，Lion [姜等人, 2023](https://arxiv.org/html/2402.16363v6#bib.bib99)] 引入了一种对抗性蒸馏框架，该框架鼓励教师模型识别“困难”指令，并随后为学生模型生成新的“困难”指令，从而形成一个动态的三步对抗循环。

黑盒蒸馏也被认为是将链式思维（CoT）从大型模型转移到小型模型的有前途的工具。[Fu et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib57)观察到语言模型之间的多样能力之间的权衡，并侧重于将教师模型的能力从一般能力转向增强学生模型对目标数学 CoT 的熟练度。SCOTT [Wang et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib200)]使用对比解码以获得更好的理由监督和对立推理目标以获得真实的蒸馏，从而获得更真实的 CoT 理由。分步蒸馏[Hsieh et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib85)]推出了更小模型的新训练方法，超越了使用更少数据的 LLMs。它使用 LLM 理由作为额外的训练材料在多任务框架中，降低了数据需求，与标准的微调和蒸馏相比。类似地，[Li et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib125)提出了符号 CoT 蒸馏，他们从教师模型中获得未标记数据集实例的 CoT 理由，然后根据这些实例训练学生模型预测理由和标签。为了在对话背景中促进复杂的多步推理，即对话 CoT 推理，[Chae 等。2023](https://arxiv.org/html/2402.16363v6#bib.bib16)利用 LLMs 作为不一致的教师，并通过对准筛选器战略性地提炼有价值和逻辑合理的理由。

### 3.4 因式分解

使用低秩矩阵分解[Kishore Kumar and Schneider, , [2017](https://arxiv.org/html/2402.16363v6#bib.bib108)]作为压缩深度神经网络（DNNs）的技术代表了一种简单而有效的方法，在科学计算和机器学习领域受到了广泛关注。近年来，通过低秩方法高效压缩和加速大规模神经网络的挑战成为研究的焦点。这导致了在为 DNNs 量身定制的低秩因式分解策略的重大进展[Schotthöfer et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib173)]。

激活感知奇异值分解（ASVD）[[Yuan et al., 2023d,](https://arxiv.org/html/2402.16363v6#bib.bib233)] 是首个使用因式分解技术来压缩 LLM 的工作。ASVD 通过根据激活分布调整权重矩阵，有效管理激活离群值，提高了分解的准确性和效率。ASVD 还解决了不同 LLM 层对分解的敏感性差异，通过迭代校准过程实现了最优的层级分解。同时，LAyer-SElective Rank reduction（LASER）[Sharma et al., [2023](https://arxiv.org/html/2402.16363v6#bib.bib180)] 展示了一个令人惊讶的结果：通过选择性地去除权重矩阵的高阶分量，通常可以显著提高 LLM 的性能。除了针对 LLM 的权重，TensorGPT [[Xu et al., 2023b,](https://arxiv.org/html/2402.16363v6#bib.bib221)] 通过 Tensor-Train Decomposition (TTD) [Oseledets, [2011](https://arxiv.org/html/2402.16363v6#bib.bib157)] 压缩 LLM 的嵌入层，以便将大量嵌入存储在低秩张量格式中，从而减少了许多参数。

## 4 种快速解码算法

![参见说明文字](img/ad7a264d510c6691d57fa3b785a103a1.png)

图 12：输入依赖动态网络技术示意图

LLM 在各种文本生成任务中取得了惊人的性能。它们通常包含解码阶段，该阶段根据所有前面的标记按自回归关系生成标记。在解码每个标记时，解码器权重必须反复加载到内存中。由于 LLM 的参数规模庞大，解码过程变得严重依赖内存 [de Jong et al., [2023](https://arxiv.org/html/2402.16363v6#bib.bib36)] 并且硬件利用率低，导致延迟非常长 [[Kim et al., 2023d,](https://arxiv.org/html/2402.16363v6#bib.bib106)]。这在像 ChatBot 这样的实际应用中尤为严重，因为快速甚至实时响应至关重要。因此，迫切需要优化解码过程，以提高这些应用中的性能。

本节重点讨论了从算法角度减少 LLM 推理成本的先前努力。具体来说，本节旨在从两个方向展开讨论：

+   •

    在[4.1 节](https://arxiv.org/html/2402.16363v6#S4.SS1 "4.1 每个解码的标记使用的最小参数 ‣ 4 种快速解码算法 ‣ LLM 推理揭示：调查与 Roofline 模型见解")中，讨论了如何在解码每个标记时（固定#tokens decoded）利用 LLM 的最少参数数量。

+   •

    在[4.2](https://arxiv.org/html/2402.16363v6#S4.SS2 "4.2 每次 LLM 前向传播解码的最大令牌数 ‣ 4 快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型洞见")节中，对于 LLM 的每一次前向传播（固定的参数数量），如何解码最大数量的令牌。

### 4.1 每个解码令牌使用的最小参数

有趣的是，Simoulin 和 Crabbé，[[2021](https://arxiv.org/html/2402.16363v6#bib.bib182)] 显示了尽管语言模型通常具有大量参数，但并非所有参数都需要生成准确的令牌。通过仅选择每个输入令牌所需的参数子集（加载）来减少 LLM 推理延迟，同时保持解码令牌的准确性。在本节中，我们从三个不同的角度查看 LLM 的输入依赖动态权重丢弃方案：[4.1.1](https://arxiv.org/html/2402.16363v6#S4.SS1.SSS1 "4.1.1 提前退出 ‣ 4.1 每个解码令牌使用的最小参数 ‣ 4 快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型洞见") 关注提前退出，即动态选择层、深度和维度中的权重；[4.1.2](https://arxiv.org/html/2402.16363v6#S4.SS1.SSS2 "4.1.2 上下文稀疏性 ‣ 4.1 每个解码令牌使用的最小参数 ‣ 4 快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型洞见") 介绍了在 LLM 的宽度维度中动态检测稀疏性的方法，修剪掉头部和 MLP 列；[4.1.3](https://arxiv.org/html/2402.16363v6#S4.SS1.SSS3 "4.1.3 专家混合模型 ‣ 4.1 每个解码令牌使用的最小参数 ‣ 4 快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型洞见") 展示了专家混合模型（MoE），该模型预训练一个稀疏模型，并在运行时选择正确的专家来处理不同的输入。

#### 4.1.1 提前退出

早期退出（或层跳过）在各种网络架构中已被充分探索，特别是在仅编码器模型中 [Baier-Reinio 和 Sterck, , [2020](https://arxiv.org/html/2402.16363v6#bib.bib9), Hou 等人, , [2020](https://arxiv.org/html/2402.16363v6#bib.bib84), Li 等人, , [2021](https://arxiv.org/html/2402.16363v6#bib.bib124), Liu 等人, , [2020](https://arxiv.org/html/2402.16363v6#bib.bib137), [2022](https://arxiv.org/html/2402.16363v6#bib.bib139), Schwartz 等人, , [2020](https://arxiv.org/html/2402.16363v6#bib.bib176), Stickland 和 Murray, , [2019](https://arxiv.org/html/2402.16363v6#bib.bib186), Xin 等人, , [2020](https://arxiv.org/html/2402.16363v6#bib.bib218), Zhou 等人, , [2020](https://arxiv.org/html/2402.16363v6#bib.bib249), Zhu, , [2021](https://arxiv.org/html/2402.16363v6#bib.bib252), Schuster 等人, , [2021](https://arxiv.org/html/2402.16363v6#bib.bib175)]。解码器架构的早期退出需要在序列级别保持一致性和质量，因为每个标记都依赖于之前的标记，而这一点在之前大量的仅编码器早期退出文献中并未涉及。解码器包含具有相同结构的层。得益于这一特性，每层的输出隐藏状态可以用来传递给 LM Head，以获取下一个标记解码的概率分布预测。Geva 等人，[[2022](https://arxiv.org/html/2402.16363v6#bib.bib60)] 和 Simoulin 和 Crabbé，[[2021](https://arxiv.org/html/2402.16363v6#bib.bib182)] 观察到，对于某些标记，隐藏状态在中间层期间饱和。换句话说，对于某些标记，早期退出在中间层会输出与完全运行模型相同的正确 top-1 预测。这一观察为解码器早期退出方法的成功奠定了基础。

Elbayad 等人，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib50)] 对于高效的机器翻译任务进行了一项早期尝试，利用解码器架构中的早期退出。该方法提出了一种通用的方法来遵循。图 [12](https://arxiv.org/html/2402.16363v6#S4.F12 "Figure 12 ‣ 4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") (b) 中展示了，在前向传播过程中，每一层之后都有一个内部置信度函数，通常是一个固定的度量标准或一个具有少量层的 MLP，该函数根据隐藏状态计算置信度分数，以评估在当前层是否可能达到饱和。这个分数用于决定是否根据一些精心设计的标准退出。然后，使用 LM Head 输出下一个标记的预测概率分布。由于新的后续工作高度相似，我们通过考察为语言模型设计早期退出方案的关键挑战来扩展讨论，这些工作引入了不同的新技术。

饱和度信心建模。CALM [Schuster et al., [2022](https://arxiv.org/html/2402.16363v6#bib.bib174)] 研究了三种不同的方法来输出信心评分以进行退出：softmax 响应，或 softmax 后的前两值之间的差异；隐藏状态的饱和度，或当前层隐藏状态与最后一层隐藏状态之间的余弦相似度；每一层插入的线性分类器的输出。线性分类器通过简单地使用交叉熵损失来训练，以对齐 MLP 输出，当输入隐藏状态时，检查当前层解码的 top-1 token 是否与完整模型解码的 top-1 token 匹配。实验表明，尽管该分类器方法不是最准确的预测器，但它在额外 FLOPs 开销与评分生成的预测准确性之间达到了最佳权衡。从 CALM 出发，[Bae et al., [2023](https://arxiv.org/html/2402.16363v6#bib.bib7)] 观察到，当从浅层一致退出会导致异常长的长度。此外，每层的信心评分计算会注入较高的开销，减少了早期退出的好处。因此，建议仅有两个选择进行早期退出：要么退出所谓的“浅层模块”或一组浅层，或者进入完整模型，即“深层模块”，从而大大减少模型内部所需的分类器数量。这种设计使其在某些任务上实现了比 CALM 更高的加速，达到了 2 倍。另一方面，ConsistentEE [Zeng et al., [2023](https://arxiv.org/html/2402.16363v6#bib.bib238)] 提出了不同的方法来预测何时退出。它使用一个 RL 策略网络，该网络通过每层输出分类头进行迭代训练。策略网络的训练目标是平衡效率（早期层获得奖励）和准确性（奖励函数中包含一个早期退出输出的 CE 损失项）的优化。

早期退出标准。CALM [Schuster et al., [2022](https://arxiv.org/html/2402.16363v6#bib.bib174)] 提出了一个无分布校准技术，该技术使用固定序列测试程序（家庭错误率程序）来输出合适的阈值。该阈值呈指数下降，以允许在序列后期更积极地退出。另一方面，Bae et al., [2023](https://arxiv.org/html/2402.16363v6#bib.bib7) 观察到信心标准的模式类似于 beta 分布，并使用在线数据通过 MLE 更新 beta 分布模型，并利用这种概率模型来指导其决策。Zeng et al., [2023](https://arxiv.org/html/2402.16363v6#bib.bib238) 通过让策略网络直接输出退出决策来绕过这个问题。

隐藏状态传播。跳过层的隐藏状态可能会带来技术挑战。如[12](https://arxiv.org/html/2402.16363v6#S4.F12 "图 12 ‣ 4 快速解码算法 ‣ LLM 推理揭示：调查和屋脊模型见解")（b）所示，“school”位置的令牌比之前的令牌晚出现。然而，最后的自注意力层没有之前早期退出令牌的键值对。Elbayad 等人，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib50)] 和 Schuster 等人，[[2022](https://arxiv.org/html/2402.16363v6#bib.bib174)] 提出了“隐藏状态传播”技术。例如，存储了退出层 $l_{1}$ 的令牌“Max”的隐藏状态。当后来的令牌“school”达到更深的层 $l_{2}$ 时，将“Max”的隐藏状态复制到 $l_{1}$ 和 $l_{2}$ 之间的所有层中，然后在复制的隐藏状态上计算键值对。基本上，是为了用早期层的隐藏状态来近似深层的隐藏状态。后来的工作 Bae 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib7)] 和 Ding 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib47)] 发现状态传播会导致性能下降。由于 LLM 推理主要由内存加载主导，计算相对“免费”。这两种方法建议直接实时重新计算后续隐藏状态。[Chen et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib21) 提出了并行运行完整的大型模型以高效地平行计算缺失的 kv 缓存。Din 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib46)] 对在变压器架构中使用线性网络跨层跳跃进行了系统研究，并展示了可以添加线性层来有效弥合直接复制和计算隐藏状态之间的性能差距，同时降低内存和计算成本。SkipDecode Corro 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib28)] 选择了一种激进的方法，优先考虑加速并放宽性能保持目标。通过利用观察到的情况，即在同一序列中，后来的令牌平均需要更少的层来解码正确的令牌，它完全绕过了状态传播的需要，强制最大使用的层对更深的位置单调递减。此外，SkipDecode 还引入了固定退出点以优化批量早期退出。

输出分类器训练。当从中间层退出时，中间隐藏状态需要通过输出分类器头来输出下一个标记概率分布的预测。输出分类器可以是共享的，如图 [12](https://arxiv.org/html/2402.16363v6#S4.F12 "Figure 12 ‣ 4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")所示，或者是每层独立的。这些分类器通常会被训练以更好地适应早期退出模式。Elbayad 等人，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib50)] 提出了将所有层的平均 CE 损失作为分类器的训练损失。另一方面，Schuster 等人，[[2022](https://arxiv.org/html/2402.16363v6#bib.bib174)] 使用加权平均，其中权重随着层数的增加而增加，将更多的贡献分配给较深的层。Bae 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib7)] 引入了动态知识蒸馏损失，它动态地为“浅层模块”分配一个合适的隐藏状态来自“深层模块”。Rotem 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib168)] 和 Ji 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib97)] 在对所有模型进行联合训练时发现了“冲突梯度”问题：Rotem 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib168)] 发现了语言模型的早期和晚期层之间的梯度冲突，而 Ji 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib97)] 则发现了改善语义感知和改善早期退出决策目标之间的“正交梯度”。这两种方法都提出了添加额外的参数块和迭代训练以缓解问题。除了上述观点，[Chen 等人，2023b](https://arxiv.org/html/2402.16363v6#bib.bib21) 研究了系统级优化技术，以在 3D 并行设置下高效运行 LLM 早期退出。

![参考标题](img/af21439121a8b5ca2d01bbfe4a931ed3.png)

图 13：并行解码方法示意图

#### 4.1.2 上下文稀疏性

尽管早期退出的目标是在深度维度上选择参数，但也有一些技术被提出来利用宽度维度上的动态稀疏性。Deja Vu [Liu et al., 2023c](https://arxiv.org/html/2402.16363v6#bib.bib141) 对 LLM 宽度维度上的动态稀疏性进行了全面研究。该论文揭示了上下文稀疏性可能高达 80%，意味着大多数权重可以被舍弃，同时仍保持原始模型的性能。然而，所选择的权重是动态的，对于不同的输入标记是不同的。该论文将这个问题形式化为一个近邻搜索问题，即对于来自前几层嵌入层的隐藏状态，如何找到最相似的注意力头和 MLP 列。为了节省计算资源，该论文建议在 LLM 的 Multi-Head Attention (MHA)和 Feed-Forward Networks (FFN)前训练一个小的 MLP 网络作为稀疏预测器，如图 [12](https://arxiv.org/html/2402.16363v6#S4.F12 "Figure 12 ‣ 4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") (c) 所示。通过仅使用一部分权重和减少内存 IO 开销，Deja Vu 设法实现 LLM 推断的超过 2 倍加速。基于 Deja Vu，PowerInfer (Song et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib184)])将上下文稀疏性发现带到了跨异构设备（CPU 和 GPU）的 LLM 推断中。PowerInfer 发现大部分权重在输入无关的设置中被大量使用并激活，因此存储在 GPU 内存中，而其他权重则存储在 CPU 内存中。然后，为了特定地找到给定输入标记使用的权重，它训练了一个比 Deja Vu 更小的稀疏预测器。为了更好地在混合的 CPU 和 GPU 环境中部署模型进行推断，它引入了一种新颖的内存放置方案，并实现了一种基于向量的稀疏计算库。同时，MatFormer (Devvrit et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib45)]) 研究了 LLM 在不同硬件能力的各种异构设备上的部署问题。他们仅在 FFN 上添加了动态结构，而 FFN 占总权重的 60%。该模型经过特殊训练，以便在推断期间，根据目标硬件属性，对 MLP 层进行行维度采样，以提供具有合理性能的各种尺寸的模型。为了多样化模型尺寸的选择，它施加了 Mix’n’Match 方法来选择不同层的不同设置，从而结合起来会提供更多变化的模型尺寸。

#### 4.1.3 专家模型混合

语言模型，特别是变压器架构，展示了强大的幂律缩放（Kaplan et al., [[2020](https://arxiv.org/html/2402.16363v6#bib.bib102)], Hoffmann et al., [[2022](https://arxiv.org/html/2402.16363v6#bib.bib79)])，即当训练数据集扩大时，模型性能会显著提升。另一方面，尽管大参数量带来了强劲的性能提升，但使得模型的训练和推理效率低下。混合专家（MoE）技术是一个研究充分的课题（Yuksel et al., [[2012](https://arxiv.org/html/2402.16363v6#bib.bib235)]），它有效地解耦了模型的参数量和模型训练及推理所需的计算 FLOPs，从而在某些条件下带来了巨大的效率提升。此外，MoE 被证明可以有效地扩展语言模型的规模并提高其性能，而无需担心推理期间计算量的增加（Lepikhin et al., [[2020](https://arxiv.org/html/2402.16363v6#bib.bib121)], Fedus et al., [[2021](https://arxiv.org/html/2402.16363v6#bib.bib53)]）。如图 [12](https://arxiv.org/html/2402.16363v6#S4.F12 "图 12 ‣ 4 种算法方法用于快速解码 ‣ LLM 推理揭秘：调查和 Roofline 模型洞察") (d) 所示，专家网络被插入到变压器架构中，以替代 FFN 层。此外，在多头注意力和专家网络之间引入了一个门控函数，旨在为给定的输入 token 选择最合适的专家或专家组合。关于 MoE 扩展泛化、路由算法、训练技术等的深入分析和讨论，我们推荐读者参考关于稀疏专家模型的调查（Fedus et al., [[2022](https://arxiv.org/html/2402.16363v6#bib.bib52)]）。尽管这两者都依赖输入 token 来确定稀疏结构，我们故意将 MoE 和上下文稀疏技术分开，因为后者作用于预训练的密集语言模型，并利用密集神经网络的稀疏性，而前者则从一开始就训练一个稀疏模型。近年来，MoE 技术取得了显著成功。Sparse Mixer（Lee-Thorp 和 Ainslie, [[2022](https://arxiv.org/html/2402.16363v6#bib.bib119)]）为 BERT（Devlin et al., [[2019](https://arxiv.org/html/2402.16363v6#bib.bib44)]）模型带来了 89% 和 98% 的加速，无论是在训练还是推理中。Du et al., [[2022](https://arxiv.org/html/2402.16363v6#bib.bib49)] 仅使用 49% 的 FLOPs，却在性能上超过了 GPT-3（Brown et al., [[2020](https://arxiv.org/html/2402.16363v6#bib.bib14)]）。ST-MoE（Zoph et al., [[2022](https://arxiv.org/html/2402.16363v6#bib.bib255)]）将 MoE 引入编码器-解码器模型中，甚至成为许多推理和生成任务的最先进模型。ST-MoE 在训练和推理中使用的 FLOPs 分别减少了 20 倍和 40 倍，其性能超过了 540B PaLM（Chowdhery et al., [[2022](https://arxiv.org/html/2402.16363v6#bib.bib25)]）。Mixtral 8x7B（Jiang et al., [[2024](https://arxiv.org/html/2402.16363v6#bib.bib98)]），尽管在推理过程中仅主动使用 13B 参数，但在各种评估基准上表现与 Llama2-70B 模型（[Touvron et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib197)）相当。

此外，已经进行了各种尝试来优化 MoE 模型推理。Kossmann 等人，[[2022](https://arxiv.org/html/2402.16363v6#bib.bib109)] 构建了一个高效的编译器库 RECOMPILE，针对 MoE 模型引入了动态重编译和根据变化的推理批量大小进行优化。Rajbhandari 等人，[[2022](https://arxiv.org/html/2402.16363v6#bib.bib167)] 将 ZeRO 分布式推理方法扩展到 MoE 模型。Jawahar 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib96)] 对专家网络架构进行神经架构搜索（NAS）。Yi 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib226)] 在边缘设备上部署大型 MoE 语言模型。它优化了部署，以发现某些神经元在 MoE 模型中的使用远高于其他神经元。

#### 4.1.4 动态参数减少的 Roofline 模型分析

每个解码令牌使用的最小参数方法同时减少了计算和内存访问开销。从 roofline 模型的角度来看，这些方法对每个操作的算术强度和绑定类型造成的变化较小。

对于早期退出或层跳过的方法，整个 Transformer 层被跳过，从而导致整体计算、内存访问和推理时间按比例减少。换句话说，推理时间随着跳过的层数按比例减少。然而，对于如上下文稀疏性和专家混合的方法，算术强度在不同操作中有所不同。因此，动态选择激活这些层会导致计算和内存访问的变化，进而对整体推理时间产生不同的影响。

### 4.2 每次 LLM 前向传播解码的最大令牌数

减少 LLM 推理延迟的另一种方法是放宽 LLM 自回归解码的限制，使得每次 LLM 前向传播可以解码多个标记。我们考虑了两种实现方式：[4.2.1](https://arxiv.org/html/2402.16363v6#S4.SS2.SSS1 "4.2.1 推测解码 ‣ 4.2 每次 LLM 前向传播解码的最大标记数 ‣ 4 快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型洞察") 介绍了推测解码方法，该方法引入了计算高效的草稿模型来为下几个标记位置提出候选，而 LLM 被用来评估草稿模型提出的草稿标记，而不是生成下一个标记。另一方面，[4.2.2](https://arxiv.org/html/2402.16363v6#S4.SS2.SSS2 "4.2.2 并行解码 ‣ 4.2 每次 LLM 前向传播解码的最大标记数 ‣ 4 快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型洞察") 介绍了使 LLM 能够直接从单次前向传播中解码多个标记的工作。由于一些方法结合了两种方向的优点并处于中间位置，我们手动添加了一个区分，只是为了命名的意义，这里的推测解码方法都包含了转化器架构中的草稿模型。

#### 4.2.1 推测解码

由于记忆加载挑战和自回归特性，LLM 在推理时效率较低。然而，较小尺寸的模型显示出（[Kim et al., 2023e](https://arxiv.org/html/2402.16363v6#bib.bib107)）具有与 LLM 相同的解码正确序列的能力，只要小模型生成序列中的一些关键标记得到纠正。然后，如图 [13](https://arxiv.org/html/2402.16363v6#S4.F13 "图 13 ‣ 4.1.1 早期退出 ‣ 4.1 每个标记解码所用的最小参数 ‣ 4 快速解码的算法方法 ‣ LLM 推理揭示：调查与 Roofline 模型洞察")（a）所示，当小模型被要求推断（猜测）并输出一系列草稿标记时，模型权重的记忆加载问题较少，从而显著提高了硬件计算单元的利用率。为了确保小模型生成文本的质量，LLM 可以“定期”评估和纠正小模型草稿中的标记。然后，尽管大模型有时需要评估错误的草稿标记，可能导致比 LLM 自回归解码花费更多的 FLOPs，但权重的记忆加载在标记维度上是并行的，显著减少了内存 IO 开销。由于 LLM 推理是内存瓶颈，推测解码将大大降低 LLM 推理的延迟。

LLM 分布保持 在这一思想的早期探索中，出现了两条不同的路径。[Kim 等人，2023e](https://arxiv.org/html/2402.16363v6#bib.bib107) 提出了让小模型进行预测并生成草稿标记，直到标记解码信心降到阈值以下。然后，小模型“回退”到大模型以评估生成的草稿标记，并将其交给小模型。一些标记被拒绝，因此大模型要求小模型“回滚”这些错误的标记并重新开始预测。在论文的设定中，所有解码都是“贪婪的”。论文表明，大模型和小模型的组合可以生成与原始大模型自回归生成的文本质量相当的文本。然而，Leviathan 等人，[2023](https://arxiv.org/html/2402.16363v6#bib.bib122) 和 [Chen 等人，2023a](https://arxiv.org/html/2402.16363v6#bib.bib18) 基于小模型预测范式，指出了一种重采样技术，这种技术在 LLM 拒绝小模型的预测的情况下，能使大模型和小模型的预测处于与大模型自回归生成相同的概率分布中。以下技术通常遵循预测、评估和重采样的范式，以保持 LLM 自回归解码质量，同时实现加速。

构建草稿令牌树 由于 LLM 是以自回归的顺序生成的，每个令牌都依赖于所有之前生成的令牌，而小模型草稿中的接受令牌长度通常是适中的且有限的。预测更远的未来令牌难度呈指数级增长。例如，如果小模型被要求输出长度为 m 的草稿序列，而 LLM 接受了 n 个令牌，其中 n $<$ m，则(m - n)个令牌会被自动丢弃。因此，投机解码的加速比有限，因为每次 LLM 的前向推理仅解码了有限数量的令牌。有两种方法可以提高投机解码的加速。首先，[Sun et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib191)、[Miao et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib147)和[Xu et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib220)都提出了在批量大小方向上提升草稿的方法，或者让小模型并行采样多个可行的草稿序列供 LLM 评估。具体来说，[Sun et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib191)提出了一种方法及理论保证，使 LLM 能够批量验证并从多个小模型草稿中重新采样，从而保持 LLM 的分布，且不会造成生成质量的损失。论文首先将投机解码与离散最优传输的更广泛问题联系起来。要求小模型使用 topk 采样来采样多个草稿序列。根据离散最优传输的特性，找到评估和重新采样的最优方法就变成了寻找最优的传输路径。另一方面，[Miao et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib147)除了保持草稿树的投机解码一致性外，还构建了一个基于多个多样化训练的小草稿模型而非小草稿模型的 top 预测的令牌树，这些小模型并行运行并输出多样而强大的草稿序列。论文提出了一种新颖的草稿令牌树构建算法，该算法通过预定义的扩展和合并方案基于多样化的草稿序列构建候选令牌树。然后，要求大模型使用精心设计的树注意力并行验证构建的树，以最大化关键-值缓存的重用并保持基于树的因果掩码。[Xu et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib220)创新性地将投机解码的好处应用于边缘设备。论文构建了一个用于边缘的 LLM 服务引擎，其中一个较小的草稿 LLM 持续驻留在内存中，而一个较大且稳健的 LLM 则偶尔被加载到内存中进行验证。为了提高大 LLM 的接受率，它还使用 topk 令牌构建了一个树。为了适应边缘硬件的特性，它实现了一个基于树的并行验证解码器，配备了掩码和定制的大-小 LLM 计算管道，以避免内存争用。

知识蒸馏和自我推测解码 另一种提高接受率的方法是通过知识蒸馏在大型模型生成的语料库上微调小型草稿模型，从而提高小型草稿模型与 LLM 生成分布的对齐能力。[Zhou et al., 2023c](https://arxiv.org/html/2402.16363v6#bib.bib250) 建立了接受率与小型模型和 LLM 之间的自然差异之间的数学联系：最小化差异即最大化接受率。该论文还研究了一系列不同的知识蒸馏损失，并显示添加知识蒸馏带来了 10-45%的延迟加速一致性提高。然而，论文普遍发现，最佳的知识蒸馏损失选择因模型而异，应作为超参数进行调整。[Liu et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib138) 还展示了知识蒸馏促进了小型模型训练。此外，论文将推测解码引入了云在线学习设置。LLM 推理受限于内存瓶颈，这意味着计算资源总是有多余的。这些计算资源可以用于在服务器上持续训练草稿模型，这带来了两个好处：1）通过知识蒸馏的持续训练提升了其接受率，从而减少了 LLM 推理延迟；2）服务输入在不同领域不断变化，持续训练帮助草稿模型在不同领域保持强劲的性能。张等人，[2023](https://arxiv.org/html/2402.16363v6#bib.bib240) 通过从大型模型中选择性地采样较小的草稿模型来避免存储单独的草稿模型。在部署之前，论文利用贝叶斯优化方法，通过跳过预训练大型模型中的中间层来搜索草稿模型。此外，论文提出了一种针对从大型模型中采样的草稿模型解码的自适应阈值选择技术。

#### 4.2.2 并行解码

另外，已经提出了大量的方法，使得大型模型可以直接进行并行解码，而无需小型变换器模型的帮助。

同时预测多个未来令牌的研究正广泛探索如何从大型语言模型的一次前向传播中直接进行多个令牌预测。Stern 等人，[[2018](https://arxiv.org/html/2402.16363v6#bib.bib185)] 率先设计了在最后的隐藏状态输出和语言建模头的输入之间插入线性投影层，以便仅基于当前令牌的最后隐藏状态作为输入来投影多个未来令牌。随后，LLM 会对这些投影的令牌进行评估，以决定是否接受或拒绝。所提出的技术主要集中在具有解码器结构的序列到序列模型上。最近，Cai 等人，[[2024](https://arxiv.org/html/2402.16363v6#bib.bib15)] 将之前的工作扩展到仅解码器语言模型，如图 [13](https://arxiv.org/html/2402.16363v6#S4.F13 "Figure 13 ‣ 4.1.1 Early Exiting ‣ 4.1 Minimum Parameter Used Per Token Decoded ‣ 4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") (b) 所示。除了最后层投影外，为了进一步提高解码接受率，论文建议添加基于树的解码结构和相关的注意力掩码设计，以同时提出多个草稿供大型模型评估。此外，Monea 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib152)] 提出了在输入序列的末尾添加几个虚拟令牌，这些令牌被称为“前瞻嵌入”。在每层的前向传播过程中，可以利用之前的提示令牌和已解码令牌的信息来并行解码几个连续的未来令牌。为了实现这一设计，该工作训练了一个专门用于这些前瞻嵌入的嵌入层。Li 等人，[[2024](https://arxiv.org/html/2402.16363v6#bib.bib127)] 也致力于通过 LLM 评估进行并行解码。与之前的工作类似，它也添加了一个轻量结构 FeatExtrapolator。不同的是，该结构同时接受前一个令牌的最后层隐藏状态和实际解码令牌嵌入作为输入，并输出下一层的隐藏状态预测。使用 LLM 的语言模型头，采样几个令牌，然后用这些令牌构建解码树供 LLM 并行评估。

频繁 N-gram 的检索 除了直接使用 LLM 输出几个后续的标记外，一些研究利用自然语言中频繁出现的 n-gram，使得多个未来标记可以在大模型的一次前向传递中生成。LLMA（Yang et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib224)]）首次观察到生成任务倾向于要求 LLM 重复出现在先前上下文中的标记。基于这一信息，论文着手利用解码标记和提示进行前缀匹配，并与一组参考文献进行比对，以便在出现重复时，重复的标记可以直接复制到当前位置。然后，LLM 将评估这些从先前上下文中找到的候选标记，以决定是否使用它们。He et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib77)] 进一步扩展了 LLMA，提出首先基于 LLM 预训练或微调的数据集和语料库构建一个常见短语的数据库。然后，在解码过程中，使用先前的上下文提示或标记作为查询，从构建的数据库中进行检索。检索到的候选项被组织成前缀树结构或 trie，LLM 可以高效地进行评估。Lan et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib114)] 类似地使用检索方法来加速推理。与此不同的是，它在 LLM 的末尾添加了一个额外的注意力层，使用当前标记的隐藏状态表示的当前上下文作为查询，关注从参考文档中检索到的相关短语，并根据注意力分数选择前几的短语。

语言中的**层次结构**是存在的。撰写长篇文章的通常方法是首先写出论文的一般大纲，格式如同要点。然后，对于每一个要点，可以扩展论点以涵盖该要点的完整意图。基于不同要点的论点在语义上相对独立的观察，提出了一些方法来并行生成不同的要点。**思维骨架**（Ning et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib154)]）建议首先让 LLM 生成简洁的要点，然后在批处理轴上收集这些要点，并再次将其作为提示输入 LLM，要求 LLM 并行扩展每个要点的论点。实现的加速约为 2 倍，但有一个警告，即该方法不能轻易推广到所有文本生成任务。最近，**APAR**（[Liu et al., 2024a](https://arxiv.org/html/2402.16363v6#bib.bib136)）在此方向上进行了扩展。该论文添加了特定的软标记，明确在生成过程中告知 LLM 层次信息。LLM 进一步被指导调整以结合这些特殊标记，生成过程通过**美杜莎**（Cai et al., [[2024](https://arxiv.org/html/2402.16363v6#bib.bib15)]）技术得到了提升，实现了在具有层次结构的文本生成上的 4 倍加速。

Jacobi 和 Gaussian-Seidel 迭代算法 Song 等人，[[2021](https://arxiv.org/html/2402.16363v6#bib.bib183)] 开创了使用可并行化方法来近似全连接网络或卷积神经网络迭代和顺序推理结果的研究。虽然看似不可行，但论文发现神经网络能够容忍数值近似误差，并且神经网络学习的数据模式在某种程度上暴露了并行结构，这使得在某些场景下可以并行化神经网络的顺序推理。Jacobi 和 Gaussian-Seidel 算法以前被提出用于求解非线性方程组（Ortega 和 Rheinboldt，[[2000](https://arxiv.org/html/2402.16363v6#bib.bib156)]），并被证明能有效地并行化顺序神经网络推理。Santilli 等人，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib170)] 扩展了 Jacobi 和 Gaussian-Seidel 算法以并行化机器翻译任务中的自回归解码。具体而言，这项工作基于以前的非自回归 Transformer 架构（我们将在本章后面讨论）来增强并行解码，使用 GS-Jacobi 算法。并行解码过程在解码文本中找到 [EOS] 标记时停止。同时，图 [13](https://arxiv.org/html/2402.16363v6#S4.F13 "Figure 13 ‣ 4.1.1 Early Exiting ‣ 4.1 Minimum Parameter Used Per Token Decoded ‣ 4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") (c) 中展示的 Lookahead 解码 ([Fu 等人，2023a](https://arxiv.org/html/2402.16363v6#bib.bib56)) 将这一方法扩展到并行化 LLM 生成后续标记。除了使用原始的 Jacobi 迭代算法外，它还通过基于检索的算法来提高速度，以重用之前见过的 n-gram。此外，通过向原始 LLM 模型引入精心设计的注意力掩码，它并行化了前瞻步骤和 LLM 验证步骤，以进一步提高解码效率。

对于需要自回归解码的序列到序列模型的机器翻译任务，提出了非自回归变换器（NAT）以迭代方式一起解码所有输出标记，如图[13](https://arxiv.org/html/2402.16363v6#S4.F13 "Figure 13 ‣ 4.1.1 Early Exiting ‣ 4.1 Minimum Parameter Used Per Token Decoded ‣ 4 Algorithmic Methods for Fast Decoding ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")（d）所示。NAT 已被相对充分地探索（Gu et al., [[2017](https://arxiv.org/html/2402.16363v6#bib.bib66)], Wang et al., [[2019](https://arxiv.org/html/2402.16363v6#bib.bib203)], Li et al., [[2019](https://arxiv.org/html/2402.16363v6#bib.bib129)], [Sun et al., 2019b](https://arxiv.org/html/2402.16363v6#bib.bib190), Wei et al., [[2019](https://arxiv.org/html/2402.16363v6#bib.bib204)], Shao et al., [[2020](https://arxiv.org/html/2402.16363v6#bib.bib179)], Lee et al., [[2018](https://arxiv.org/html/2402.16363v6#bib.bib118)], Ghazvininejad et al., [[2019](https://arxiv.org/html/2402.16363v6#bib.bib61)], Guo et al., [[2020](https://arxiv.org/html/2402.16363v6#bib.bib72)], Gu and Kong, [[2020](https://arxiv.org/html/2402.16363v6#bib.bib67)], Savinov et al., [[2021](https://arxiv.org/html/2402.16363v6#bib.bib171)])，我们向读者推荐以下专门讨论 NAT 模型的综述论文[Xiao et al., 2023c](https://arxiv.org/html/2402.16363v6#bib.bib217)以获取关于该主题的深入评审和分析。粗略来说，文本解码的加速来自于使解码器输出的一次前向传递产生多个标记。首先将输入序列输入到编码器中，编码器输出隐藏状态以提取输入语义。编码器的输出隐藏状态随后作为解码器传递的条件。为了加快文本生成，解码器端放宽了自回归约束，并将一个充满虚拟标记[pad]的序列作为输入开始迭代并行解码过程。在每次迭代中，根据编码器输出隐藏状态设定的条件，可以自信地预测一些标记，这些标记是未掩盖的。序列混合了未掩盖的解码标记，剩余的掩盖标记再次输入到解码器中，直到每个标记都被解码。输入到解码器中的序列长度或生育度通常在编码器内部作为特殊的[CLS]标记学习，或由编码器和解码器之间的专门生育度预测器学习。最近，Savinov et al., [[2021](https://arxiv.org/html/2402.16363v6#bib.bib171)] 将解码器视为扩散模型，并训练其根据给定条件去噪声化嘈杂的初始序列。然而，由于需要使用编码器隐藏状态作为并行解码的条件，NAT 方法在直接扩展到仅解码器架构时面临自然困难。

## 5 编译器/系统优化

在对大型语言模型（LLMs）进行模型压缩和算法优化之后，下一步是将其编译并部署到硬件设备上。为了确保 LLMs 的高效推理，可以采用各种编译器优化技术。此外，由于 LLMs 的规模不断增加，可能需要多个硬件设备进行部署和执行，形成复杂的推理基础设施系统。因此，系统级优化以实现高效推理已成为一个热门话题。在本节中，我们将探讨一些广泛使用的编译器优化和系统优化技术。这些包括操作符融合、内存管理、负载卸载和并行服务。

### 5.1 操作符融合

![参见说明](img/7646e3cdcd6f5cae929ec71e9975c7cf.png)

图 14：线性操作符后跟 SiLU 操作符的操作符融合演示。

![参见说明](img/4ea9c30db839988ec7a6e4183b381114.png)

图 15：操作符融合的内存受限情况和计算受限情况演示。

![参见说明](img/bb5dcb97249df65dde94c237e3e50ec8.png)

图 16：FlashAttention 在 Nvidia A6000 上的内存访问减少和推理时间减少。

操作符融合是在深度学习框架中提高计算效率的重要编译时优化技术。它将计算图中直接连接的多个操作符或层结合在一起。这可以消除冗余的数据移动和中间表示。例如，线性操作符后跟 SiLU 操作符可以融合成一个单一操作符。如图[14](https://arxiv.org/html/2402.16363v6#S5.F14 "图 14 ‣ 5.1 操作符融合 ‣ 5 编译器/系统优化 ‣ LLM 推理揭秘：调查与 Roofline 模型见解")所示，这样可以避免在每个操作符之间存储和加载中间激活，从而减少内存消耗和内存访问。如图[15](https://arxiv.org/html/2402.16363v6#S5.F15 "图 15 ‣ 5.1 操作符融合 ‣ 5 编译器/系统优化 ‣ LLM 推理揭秘：调查与 Roofline 模型见解")所示，Roofline 模型表明，内核融合可以提高算术强度，并在内存受限区域增强推理性能。然而，当操作符已经位于计算受限区域时，内存融合的好处不大。

尽管操作符融合在许多情况下可以提供显著的性能提升，但它并不适用于所有操作符。对于某些操作符，操作符融合可能不可行或无益：（1）操作符融合要求融合操作的中间结果在计算图中的其他地方不需要。如果后续操作依赖于中间操作的输出，则没有引入额外复杂性或重新计算的情况下，无法进行融合。（2）操作符融合可能会增加融合操作的片上缓冲区需求。如果可用的片上缓冲区有限，则可能无法融合某些操作。（3）某些框架或硬件架构可能对哪些操作可以融合有限制或约束，这取决于它们的实现细节。

一些编译工具，如 TVM [Chen et al., , [2018](https://arxiv.org/html/2402.16363v6#bib.bib20)]，能够识别可以融合在一起的操作符，并用融合后的操作符替代它们。然而，对于 LLMs，自动检测和融合操作符既不必要也复杂，因为 LLMs 具有固定的架构。相反，可以使用特定的融合模式来提高效率。例如，注意力机制是 LLMs 的一个重要部分。自动融合注意力机制对于编译工具来说可能是一个复杂的任务。FlashAttention [Dao et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib33), Dao, , [2023](https://arxiv.org/html/2402.16363v6#bib.bib32)] 和 Flash-Decoding [Dao et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib34)] 提出了将自注意力中的矩阵乘法和 softmax 操作符融合成一个操作符。这种融合技术消除了存储和加载中间注意力矩阵的需求，当序列长度或批量大小很大时，这些矩阵可能非常庞大。如图 [16](https://arxiv.org/html/2402.16363v6#S5.F16 "Figure 16 ‣ 5.1 Operator Fusion ‣ 5 Compiler/System Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 所示，融合它们可以显著减少内存访问和推理时间。我们可以观察到预填充阶段和解码阶段之间的差异。在解码阶段，内存访问减少与推理时间减少是相同的。然而，在预填充阶段，推理时间减少低于内存访问减少。这是因为预填充阶段的一些操作是计算密集型的，因此通过操作符融合减少内存访问带来的好处有限。

DeepSpeed-inference [Aminabadi et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib6)] 引入了一种叫做 Deep-Fusion 的技术。它特别融合了变压器层中的四个主要区域：QKV GeMM 和输入层归一化；转置和注意力操作；注意力后的层归一化和中间 GeMM；偏置添加和残差添加。xFormers [Lefaudeux et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib120)] 提供了各种融合内核，可以提升变压器的性能。这些包括融合的 softmax、融合的线性层、融合的层归一化和融合的 SwiGLU。TensorRT-LLM [Vaidya et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib198)] 是另一个提供广泛高性能融合内核的框架。它包含一个强大的模式匹配算法，可以检测各种 LLM 中的潜在融合。

除了内核融合，我们还可以通过进一步优化操作符的实现来提升 LLM 的性能。例如，FlashDecoding++ [Hong et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib81)] 提出了使用异步 softmax 和双缓冲的平面 GEMM 优化来提高效率。

### 5.2 内存管理和工作负载卸载

在使用 LLM 生成响应时，输入和输出 token 的数量可能每次都会变化。用户的输入提示的长度可能不同，影响预填充阶段的序列长度。此外，在解码阶段，随着 token 的生成，序列长度逐渐增加。这意味着激活的形状不像在普通神经网络中那样固定。如何在张量大小变化时有效管理内存是一个问题。PagedAttention [Kwon et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib110)] 通过将 KV 缓存划分为块来高效处理 KV 缓存。每个序列的 KV 缓存被划分为块，每个块包含固定数量的 token 的键和值。为了管理这些块，使用一个表来将序列的逻辑块映射到 GPU 内存中的物理块。这种映射类似于 CPU 内存管理系统中的虚拟内存工作方式。

![参见说明](img/829fcc0bcc4d0420e4b67fcc2b921d3d.png)

图 17：在典型的计算机架构中，内存系统由不同类型的内存空间组成。

![参见说明](img/cd66305291f67cd958b0b0e6d1251755.png)

图 18：不同卸载设置下的 Roofline 模型。

当 GPU 的内存容量有限且网络过大无法容纳时，可能需要采用负载卸载将网络存储在其他内存空间中。如图 [17](https://arxiv.org/html/2402.16363v6#S5.F17 "Figure 17 ‣ 5.2 Memory Management and Workload Offloading ‣ 5 Compiler/System Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 所示，计算机系统由各种内存空间组成，包括 CPU 的 DDR、GPU 的 GDDR/HBM 和硬盘。然而，这些不同的内存空间具有不同的访问带宽。图 [18](https://arxiv.org/html/2402.16363v6#S5.F18 "Figure 18 ‣ 5.2 Memory Management and Workload Offloading ‣ 5 Compiler/System Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 说明，当数据被卸载到 CPU 的 DDR 并在需要时传输到 GPU 进行计算时，比在 CPU 上执行计算更为有效。当批量大小足够大时，算术强度显著增加，使 GPU 能够充分利用其计算能力并取得良好结果。DeepSpeed-inference [Aminabadi et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib6)] 引入了 ZeRO-Inference，将大模型的权重卸载到 CPU 内存中。这种机制在批量大小较大时表现良好，因为增加的批量大小增加了计算需求，并使计算延迟与获取模型权重的延迟重叠，从而提高了整体效率。Huggingface Accelerate [HuggingFace, , [2022](https://arxiv.org/html/2402.16363v6#bib.bib94)] 也可以在 GPU 空间不足以存储整个模型时，将某些模块移动到 CPU 或硬盘。FlexGen [Sheng et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib181)] 提供了一种探索不同计算卸载方式的方法，考虑了来自 GPU、CPU 和硬盘的硬件资源限制。为了找到最佳的吞吐量策略，FlexGen 使用了基于线性规划的搜索算法。Alizadeh et al., [[2023](https://arxiv.org/html/2402.16363v6#bib.bib5)] 利用闪存相比 DRAM 的更大容量，通过将模型参数存储在闪存中并在需要时转移到 DRAM 中来高效执行推理。

### 5.3 并行服务

并行服务同时处理多个用户请求。一个目标是快速响应每个请求。为了实现这一目标，我们需要减少响应每个用户的时间，即响应延迟。另一个重要因素是吞吐量，它是服务器在给定时间内可以处理的请求数量。通过提高服务器的吞吐量，我们可以同时服务更多的用户，从而提升整体系统性能。为了最大化吞吐量，同时确保响应延迟在可接受范围内，服务系统应进行优化。批处理是一种通过同时处理多个用户请求来提高吞吐量的基本方法。图 [19](https://arxiv.org/html/2402.16363v6#S5.F19 "Figure 19 ‣ 5.3 Parallel Serving ‣ 5 Compiler/System Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 显示，在解码阶段增加批量大小会显著提高吞吐量。然而，增加批量大小可能会增加响应延迟和内存消耗。

![参见说明](img/ef4ac35550267d7e5961b1f2412286af.png)

图 19：并行服务设置对 Nvidia A6000 GPU (Llama-2-13b) 的吞吐量、延迟和内存使用有影响。

已提出几种技术来优化批处理方法。例如，ORCA [Yu et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib229)] 引入了连续批处理（也称为迭代或滚动批处理）来结合来自不同用户的推理。SARATHI [Agrawal et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib3)] 采用了分块预填充和解码最大批处理。它结合了预填充块和解码请求以创建批次，从而增加了运算强度并提高了吞吐量。同样，DeepSpeed-FastGen [Holmes et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib80)] 和 LightLLM [ModelTC, , [2024](https://arxiv.org/html/2402.16363v6#bib.bib150)] 也采用了拆分和融合技术。

## 6 硬件优化

设计硬件以高效支持 LLM 推理是一项具有挑战性的任务，因为在不同推理阶段和工作负载条件下算术强度有所变化⁵⁵5 算术强度指的是算术操作与内存访问的比率，这在 Roofline 模型中已有描述（第[2.2 节](https://arxiv.org/html/2402.16363v6#S2.SS2 "2.2 Roofline Model ‣ 2 Delve into LLM Inference and Deployment ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")）。具体而言，预填充阶段通常利用 GEMM 运算符处理批量的令牌，这显示出较高的算术强度。相反，解码阶段逐个计算输出令牌，这需要使用 GEMV 运算符或精简的 GEMM 运算符来处理注意力和 FFN 层。这些运算符的算术强度较低。

此外，算术强度可能会因批量大小和序列长度的不同而表现出显著的变化。例如，大批量大小可能会显著改变算术强度，而长序列长度可能会增加每次解码步骤中 KV 缓存读取的内存访问开销。这种变化给硬件设计过程带来了额外的复杂性，因为不同阶段或配置可能需要不同的优化策略。因此，在设计硬件时，考虑这些因素以确保在各种场景下的高效性能是至关重要的。

考虑到这些挑战，需要对硬件设计进行仔细考虑和优化。在本节中，我们将调查和分析各种针对高效 LLM 推理的硬件优化，重点解决与变化的算术强度相关的问题。

### 6.1 空间架构

LLM 的解码过程涉及基于之前生成的词逐个预测词。然而，这一过程可能会很昂贵，尤其是在长序列生成任务中。这是因为模型需要访问大量的权重和键值（KV）缓存来生成每个令牌，从而导致算术强度较低。

已开发出几种解决方案来应对这一问题。其中一种解决方案是实现“空间架构”。与传统计算机架构不同，空间架构采用不同的计算方法。空间架构不是将计算过程折叠成多个处理元素（PE）与主存之间的交互，而是将计算分布到多个 PE 上。这种设计利用了并行性，因为每个 PE 同时执行部分计算。此外，PE 之间的数据流动，避免了每次都写回到 DRAM。

![参见说明](img/90e09883b7c57ffe44eb4bb413f4f5a7.png)

图 20：带宽对 Roofline 模型和 Llama-2-13b 的影响。（批量大小=1，序列长度=1024）

在空间架构中，每个处理元素（PE）负责特定部分的计算。为了实现高效的通信，数据通常在相邻的 PE 之间移动。这使得性能得到提升，并有效利用资源。在空间设置中，每个 PE 都有直接访问内存的权限。这使得多个处理单元能够同时访问内存，从而提高了信息进出内存的总体速度。这导致了内存带宽的提升和 LLM 推理性能的整体改善。如图 [20](https://arxiv.org/html/2402.16363v6#S6.F20 "Figure 20 ‣ 6.1 Spatial Architecture ‣ 6 Hardware Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 所示，随着总内存带宽的增加，解码阶段线性层的性能可以显著提升。

在一个案例中，Groq 使用其 LPU [Abts et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib1)] 创建了一个用于 LLM 推理的空间系统。该系统在 Llama-2-70b 模型上实现了每秒超过 300 个 token 的惊人速度 [Groq, , [2023](https://arxiv.org/html/2402.16363v6#bib.bib65)]。另一个例子是 Graphcore 的智能处理单元（IPU），这是一种高效执行 LLM 的空间架构 [Graphcore, , [2024](https://arxiv.org/html/2402.16363v6#bib.bib64)]。

### 6.2 内存处理

LLM 推理的解码阶段会遇到所谓的“内存墙”问题，这主要是由于其低算力密度。这个问题并不新鲜，计算机架构界已经为解决“内存墙”问题苦苦挣扎了几十年。在各种潜在解决方案中，近年来内存处理技术（PIM）受到了极大关注。通过将计算单元直接放置在内存芯片中，我们可以利用更高的内部内存带宽，并减少内存与 CPU/GPU 核心之间的数据传输开销。

近年来，基于 DRAM 的 PIM 已进入商业化阶段，这可能缓解 LLM 推理中的内存带宽瓶颈。如表 [2](https://arxiv.org/html/2402.16363v6#S6.T2 "Table 2 ‣ 6.2 Processing in Memory ‣ 6 Hardware Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 所示，UPMEM 的 PIM-DIMM [Devaux, 2019a](https://arxiv.org/html/2402.16363v6#bib.bib42) 是首款商业化的 DRAM-PIM 产品，它在 DDR4-DIMM 中放置了通用 RISC 核心。然而，该产品并未针对深度学习应用，因此其峰值带宽和吞吐量难以满足 LLM 推理的要求。与 UPMEM 的 PIM-DIMM 相比，三星提出将 MAC 单元放入 HBM 内存中，实现了 2TB/s 的内部内存带宽，这远高于传统 HBM2（每立方体 307GB/s）内存。由于处理单元是专为深度学习工作负载定制的，HBM-PIM 的峰值计算吞吐量可达 1.2TFLOPS。换句话说，HBM-PIM 适合加速具有 1-2 Ops/Byte 算术强度的运算。

Choi 等人提议通过使用 HBM-PIM 加速 KV-Cache 处理，这在批量 LLM 推理中具有低算术强度。根据他们的评估 Choi 等人，[2023](https://arxiv.org/html/2402.16363v6#bib.bib23)，用于 LLM 推理的 GPU+HBM-PIM 系统相比传统的单体 GPU 系统能实现 3.24$\times$ 的加速。

与三星的 HBM-PIM 类似，SK-hynix 也提出了一种基于 GDDR6 的 PIM 加速器 Kwon 等人，[2022](https://arxiv.org/html/2402.16363v6#bib.bib112) 称为 AiM。如表 [2](https://arxiv.org/html/2402.16363v6#S6.T2 "Table 2 ‣ 6.2 Processing in Memory ‣ 6 Hardware Optimization ‣ LLM Inference Unveiled: Survey and Roofline Model Insights") 所示，AiM 的计算单元采用了 BF16 数据格式，这对深度学习加速更为高效。通过优化的 MAC 单元，AiM 每芯片提供 1TFLOPS 的计算能力，而峰值带宽为每芯片 1TB/s。尽管 AiM 尚未报告其在 LLM 上的性能，但在 LSTM 任务上与 GPU+HBM2 系统相比，性能提升可达 10$\times$。

请注意，虽然基于 DRAM 的 PIM 技术已显示出在 LLM 推理中加速内存密集型运算的良好潜力，但仍存在一些未来需要解决的局限性。

+   •

    计算能力有限。DRAM-PIM 在加速 LLM 时的一个关键限制是其受限的计算能力。DRAM-PIM 利用使用 DRAM 工艺制造的计算单元，这使得其晶体管速度比同技术节点的 CMOS 慢 3 倍，逻辑密度也低好几倍 [Devaux, 2019b](https://arxiv.org/html/2402.16363v6#bib.bib43)。更糟糕的是，DRAM 芯片通常金属层较少，导致同样的路由密度较低。由于这些技术限制，DRAM-PIM 几乎无法集成强大的计算单元。因此，DRAM-PIM 仅适用于小批量推断或 KV 缓存处理。对于计算密集型的大批量推断，仍然需要强大的主机。

+   •

    容量限制。DRAM-PIM 的另一个显著限制是其受限的容量。由于 DRAM-PIM 会分配部分内存容量用于构建计算单元，因此其总内存容量通常比标准内存低 50% [Kwon et al., [[2021](https://arxiv.org/html/2402.16363v6#bib.bib111)]。对于需要大量内存容量来存储权重和 KV 缓存的 LLM 应用，DRAM-PIM 可能会面临容量相关的问题。

+   •

    不足的 PIM 间通信。除了计算能力和容量的限制外，DRAM-PIM 的另一个限制是其不佳的 PIM 间通信能力。由于各 DRAM 银行附近存在分布式计算单元，这些单元间的数据汇聚和计算同步是不可避免的。然而，DRAM-PIM 缺乏强大的互连 [Zhou et al., 2023d](https://arxiv.org/html/2402.16363v6#bib.bib251)，Jonatan et al., [[2024](https://arxiv.org/html/2402.16363v6#bib.bib100)]，它们通常依赖主机 CPU/GPU 进行 PIM 单元之间的数据交换。这种依赖可能导致系统效率低下。因此，为了提升 LLM 推断能力，未来的 DRAM-PIM 版本应致力于改善其 PIM 间通信能力。

表 2：商品 DRAM NMC 产品对比

| 产品 | PIM-DIMM | HBM-PIM | AiM |
| --- | --- | --- | --- |
| 技术 | DDR4 | HBM2 | GDDR6 |
| PIM 单元 | RISC 核心 | FP16 MAC | BF16 MAC |
| 峰值带宽 | 每 DIMM 80.4 GB/s | 每立方体 2 TB/s | 每芯片 1 TB/s |
| 峰值吞吐量 | 每 DIMM 43.8 GOP/s | 1.2 TFLOPS | 1 TFLOPS |

### 6.3 新数据格式

神经网络通常采用高精度浮点数（16 或 32 位）进行训练。虽然高精度浮点数可以兼顾表示精度和范围，但浮点运算所需的复杂硬件实现不利于高效推理。为了降低硬件开销，均匀量化将高精度浮点数转换为低精度整数表示，用高效的整数逻辑替代昂贵的浮点逻辑。然而，均匀量化难以同时平衡表示精度和范围，导致模型准确性显著下降。此外，为了在不降级的情况下保持模型准确性，需要设计良好的量化算法，这引入了额外的转换工作。非均匀量化试图通过非均匀地分配位数和离散化参数范围来提高低位条件下的数据表示精度。然而，非均匀量化的一个关键缺点是其在通用计算硬件上的部署挑战，例如 CPU 和 GPU [Gholami et al., [2022](https://arxiv.org/html/2402.16363v6#bib.bib62)]。总之，现有数据格式未能同时实现精细精度、广泛范围、高效率和低调优成本。鉴于降低 LLM 部署成本的关键性，需要大量工作深入探索针对 LLM 的最平衡数据格式。

| 方面 |
| --- |

&#124; 浮点数 &#124;

&#124; 点 &#124;

|

&#124; 均匀 &#124;

&#124; 量化 &#124;

|

&#124; 非均匀 &#124;

&#124; 量化 &#124;

|

| --- | --- | --- | --- |
| --- | --- | --- | --- |
| 精度 | 良好 | 差 | 中等 |
| 范围 | 良好 | 差 | 中等 |
| 硬件效率 | 差 | 良好 | 差 |
| 转换工作 | 良好 | 差 | 中等 |

表 3: 浮点数、均匀量化和非均匀量化的比较

为了提高硬件效率，从原始的 FP 模型中，自然的进展是减少高分辨率浮点格式中的指数和尾数位。正如最近的研究所展示的，[Micikevicius et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib148), [Sun et al., 2019a,](https://arxiv.org/html/2402.16363v6#bib.bib188)]，各种类别的模型在 FP16 中预训练（包括 LLMs）可以直接量化为 FP8，而不会显著降低精度。此外，在广泛的任务范围内，使用 FP8 训练可以有效匹配 16 位训练会话所实现的结果质量。低分辨率浮点格式所带来的显著硬件效率提升和对用户努力的低需求，已引起 AI 硬件制造商的关注。例如，NVIDIA 在其最新的 H100 GPU 中实现了 FP8 Tensor Core [NVIDIA, , [2022](https://arxiv.org/html/2402.16363v6#bib.bib155)]。特斯拉还在其 Tesla Dojo 芯片中引入了可配置浮点格式，即 CFloat8 [Tesla, , [2023](https://arxiv.org/html/2402.16363v6#bib.bib195)]。

除了行业引入的新颖架构外，学术界也开始努力挖掘低精度浮点格式在 LLMs 中的潜力。ZeroQuant-FP [[Wu et al., 2023d,](https://arxiv.org/html/2402.16363v6#bib.bib210)] 提出了用于 LLMs 的 FP4 和 FP8 权重/激活量化。作者采用了权重量化的缩放约束，实现了从 FP4 到 FP8 的高效权重转换，并更好地利用了 FP8 Tensor Core。ZeroQuant-(4+2) [[Wu et al., 2023c,](https://arxiv.org/html/2402.16363v6#bib.bib209)] 和 FP6-LLM [Xia et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib213)] 提出了使用 FP6 对 LLMs 进行权重量化，并分别在 CUDA Core 和 Tensor Core 上提供了高效的实现。LLM-FP4 [[Liu et al., 2023b,](https://arxiv.org/html/2402.16363v6#bib.bib140)] 提出了将 LLMs 的权重和激活量化到 FP4。总之，这些努力展示了在量化中应用更低位宽浮点格式的可行性，以及在现有或新硬件平台上实现更大效率提升的潜力。

另一方面，研究人员正在深入探讨低精度量化格式的改进，以增强数据表示的适应性，同时保持硬件效率。一些研究提出探索单值表示中的新编码方案。与利用固定长度子字段编码不同信息，如指数和尾数的 INT 和 FP 数字相对，新的基于规则的量化格式能够动态调整子字段位宽。ALPS [Langroudi et al., , [2021](https://arxiv.org/html/2402.16363v6#bib.bib115)] 提出了一个通用的 posit 格式以及一种新的自适应量化算法，以最佳方式表示 DNN 参数的动态范围和分布。ANT [[Guo et al., 2022a,](https://arxiv.org/html/2402.16363v6#bib.bib70) ] 提出了一个名为 flint 的新数据格式，使用领先的 1 编码用于指数字段。Dybit [[Zhou et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib247) ] 提出了使用第一个遇到的 0 作为分隔符来分离指数和尾数字段。这些可变长度数据格式的灵活性提供了在范围和精度之间更有效地权衡的机会，并允许定制以更好地符合 LLMs 权重和激活的分布。

另一类研究利用值之间的相似性和差异性。异常值感知量化利用了大幅度值对模型性能的显著影响。在这种方法中，重要值被识别为异常值，并与正常值不同对待，以确保更准确的表示。OLAccel [Park et al., , [2018](https://arxiv.org/html/2402.16363v6#bib.bib161)] 和 GOBO [Zadeh et al., , [2020](https://arxiv.org/html/2402.16363v6#bib.bib236)] 分别存储并分配更高位宽给异常值。OliVe [[Guo et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib69) ] 通过异常值-受害者对编码方案来优化这一概念，以确保内存访问对齐并提高效率。位共享编码集中于值之间的固有相似性，并以粗粒度注释附加信息，从而在表示精度和硬件效率之间取得平衡。AdaptivFloat [Tambe et al., , [2020](https://arxiv.org/html/2402.16363v6#bib.bib193)] 提出了通过共同的张量级别指数偏置来最佳地移动 FP 值的可用范围。MX [Darvish Rouhani et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib35)] 将 AdaptivFloat 的观察扩展到更细粒度，并提出了块数据表示（BDR）框架，以探索表示精度和硬件效率之间的最佳权衡。

| 方法 | 描述 | 好处 |
| --- | --- | --- |
| 低位浮点数 | 减少指数和尾数位数 | 效率 $\uparrow$ |
| 可变长度编码 | 动态调整子字段位宽 | 精度 $\uparrow$ |
| 异常值感知量化 | 为异常值定制量化 | 精度 $\uparrow$ |
| 位共享编码 | 在一个块内共享常见信息 | 精度 $\uparrow$ |

表 4：数据格式改进总结。这些好处对其他因素的负面影响微乎其微。

### 6.4 新处理单元

除了对内存访问的高需求外，人们对开发专用处理单元（PEs）以提升计算性能的兴趣也在增加。这些专用架构旨在提供比通用处理单元（如 CUDA 核心）更显著的计算增强，专门针对与 LLMs 相关的特定操作。

NVIDIA 在其 H100 GPU 中开发了一种名为 Transformer Engine 的特殊硬件加速引擎。该引擎通过统计分析来确定模型每一层的最佳精度（FP16 或 FP8），在保持准确性的同时实现最佳性能。一些研究人员已经设计了专门的加速器，以高效执行语言模型（LLMs）中的注意力机制[Kao et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib101), Qin et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib165)]。一些公司和研究小组也在探索使用 FPGAs 来加速 LLM 计算。例子包括 DFX[Hong et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib82)]和 LightLLM[Zeng et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib237)]。

## 7 讨论

### 7.1 可靠性

上述讨论显著提升了 LLMs 在实际场景中的推理和训练效率。然而，这些压缩方法也会导致模型可靠性的微妙变化。总体而言，第[3](https://arxiv.org/html/2402.16363v6#S3 "3 Model Compression ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")节讨论的各种压缩技术将对模型可靠性产生重大影响。因此，本节主要关注这些不同压缩技术中的关键设计选择如何影响以下三个可靠性方面：幻觉、安全对齐和超出分布的泛化。

幻觉主要指的是大语言模型（LLMs）的输出与现实世界知识不一致的情况，通常生成的是事实错误或毫无意义的内容 [Huang et al., 2023a](https://arxiv.org/html/2402.16363v6#bib.bib89)。安全对齐关注于模型自主识别和拒绝有害查询的能力，从而防止生成不当或危险的内容 Ouyang et al., [[2022](https://arxiv.org/html/2402.16363v6#bib.bib158)]。可靠性涉及模型在面对长尾场景中的非常规数据时的稳定性，例如来自对抗样本的干扰或决策捷径 Geirhos et al., [[2020](https://arxiv.org/html/2402.16363v6#bib.bib59)]。接下来的部分将深入探讨不同压缩方法如何影响这些模型性能的三个关键方面。

#### 7.1.1 幻觉

大语言模型（LLM）抑制幻觉的能力受到参数修改的关键影响。根据先前的研究发现，事实知识通常储存在变换器模块的前馈网络（FFNs）中。因此，在使用量化或结构化压缩方法时，应特别关注 FFN 层的输出校准。应对这一问题的可行方法包括识别关键的 FFN 层，即利用先前研究中的神经元级解释技术 Meng et al., [[2022](https://arxiv.org/html/2402.16363v6#bib.bib145)] 来识别对于储存知识至关重要的 FFN 层。这些层被认为重要，因为它们包含对模型准确回忆和利用事实信息至关重要的权重和表示。

对于被识别为储存知识至关重要的部分，应选择性地提高量化精度。这意味着在整体模型进行量化以减小其规模和计算需求的同时，针对这些关键的 FFN 层的量化过程会调整以保持更高的精度。这种选择性的方法有助于保持储存的事实知识的完整性和准确性，从而减少输出幻觉的风险。

在剪枝的背景下，即删除被认为不那么重要的权重或神经元以简化模型，必须保留已识别的重要 FFN 层。通过保留这些层，模型保持其核心能力，以回忆和处理事实知识，这对于确保输出的准确性和减少生成幻觉内容的可能性至关重要。

### 7.2 安全对齐

根据之前的研究发现 [Yuan et al., 2023c](https://arxiv.org/html/2402.16363v6#bib.bib232)，适度的模型压缩，如 8 位量化，并不会显著削弱模型的安全能力。然而，这可能使模型更易受到某些越狱攻击——这一方向在以前的研究中很少涉及 Deng et al., [2023](https://arxiv.org/html/2402.16363v6#bib.bib37)。因此，我们建议在部署这些压缩模型之前进行全面的红队测试。此外，基于知识迁移的方法可能会显著削弱模型的安全性。因此，我们建议在完成知识迁移后重新微调较小的模型。

### 7.3 OOD 泛化

大型语言模型在实际应用中，往往受到决策捷径的影响，导致在长尾子群体分布中出现错误决策，见 Geirhos 等人，[2020](https://arxiv.org/html/2402.16363v6#bib.bib59)。正如之前的研究所示 [Yuan et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib231)，经过量化压缩的神经网络在同一任务中的不同子群体之间表现出显著的性能差异，判断错误常发生在依赖于上下文中决策捷径的长尾子群体中。此外，kv-cache 压缩是一种常用于提高大型语言模型推理效率的技术，在推理过程中依赖于随机丢弃注意力矩阵中的令牌。这种方法进一步加剧了模型对决策捷径的依赖。因此，建议在下游特定场景中考虑集成相应的鲁棒性增强方法，如先前研究中提到的不变测试时间优化技术 Ma et al., [2024](https://arxiv.org/html/2402.16363v6#bib.bib143)。

### 7.4 高效的大型多模态模型

#### 7.4.1 大型多模态模型（LMMs）

大型多模态模型（LMMs），特别是视觉语言模型（VLMs），已成为创建通用助手的有前途的途径，展示了感知和推理能力的显著提升。这些模型利用 LLMs 作为其认知核心，丰富了多模态（MM）任务，具有强大的语言生成、零样本迁移能力和上下文学习能力。不同模态的基础模型提供了高质量的表示。LMMs 的一个关键挑战是有效整合来自其他模态的模型以促进协同推理。主要关注点在于通过 MM 预训练 + MM 指令微调流程提高模态对齐并与人类意图对齐。两项综述文章，[Yin et al., 2023b](https://arxiv.org/html/2402.16363v6#bib.bib228) 和 [Zhang et al., 2024a](https://arxiv.org/html/2402.16363v6#bib.bib239) 对 LMMs 进行了详细探讨。

#### 7.4.2 高效 LMMs

在资源有限的场景中，对跨模态能力的需求变得越来越明显。尽管 LMM 取得了进展，但它们的大规模训练和部署仍然产生了显著的计算成本， necessitating efficient parallel device implementations。Google 的 Gemini [Team et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib194)]在高效 LMM 方面处于领先地位，在多模态基准测试中实现了最先进的性能，并推出了适用于低内存设备的移动规模 LMM。然而，Gemini 仍然是闭源的。开源项目，如 LLaVA-v1.5，利用了先进的压缩技术，如通过 bitsandbytes [Dettmers et al., , [2022](https://arxiv.org/html/2402.16363v6#bib.bib38)]的 4/8 位量化，有关压缩技术的更多信息，请参见第[3](https://arxiv.org/html/2402.16363v6#S3 "3 Model Compression ‣ LLM Inference Unveiled: Survey and Roofline Model Insights)节。

进一步提高高效 LMM 的努力包括 MobileVLM [Chu et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib26)]，该系统开发了紧凑的 LLM 和高效的多模态特征投影器，以及其继任者 MobileVLM-v2 [Chu et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib27)]，探索了针对移动场景的改进训练策略。TinyGPT-V [[Yuan et al., 2023a,](https://arxiv.org/html/2402.16363v6#bib.bib230) ]利用先进的 Phi-2 [Javaheripi et al., , [2023](https://arxiv.org/html/2402.16363v6#bib.bib95)] LLM 超越了显著更大模型的性能。同样，LLaVA-Phi [Zhu et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib254)]和 Vary-toy [Wei et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib205)]引入了更小的骨干网络和增强的词汇表，以实现更广泛的泛化。TinyLLaVA [Zhou et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib246)]研究了架构选择、数据质量和训练策略的影响，表明较小的 LMM 可以通过优化数据和训练匹配其更大同行的性能。MoE-LLaVA [Lin et al., , [2024](https://arxiv.org/html/2402.16363v6#bib.bib134)]采用专家混合（MoE） [Yuksel et al., , [2012](https://arxiv.org/html/2402.16363v6#bib.bib235)]来减轻由于稀疏性造成的模型退化。

### 7.5 长上下文建模

当用于像聊天机器人或文档总结工具这样的任务时，大型语言模型的长上下文语言建模和推理能力会面临挑战。然而，这些模型通常是在一般的预训练语料库上进行训练的，这些语料库通常由文本片段组成，长度不足以作为高质量的训练示例供 LLM 学习。为了缓解预训练模型的长上下文能力不足的问题，许多研究尝试从不同角度解决这一问题。在本节讨论中，我们主要关注[7.5.1](https://arxiv.org/html/2402.16363v6#S7.SS5.SSS1 "7.5.1 Alternative Attention Design ‣ 7.5 Long Context Modeling ‣ 7 Discussion ‣ LLM Inference Unveiled: Survey and Roofline Model Insights")中的替代注意力机制、缓存压缩和上下文检索以及位置编码修改。有关 LLM 长上下文建模问题的更多详细研究和更全面的综述，请参阅最近关于这一主题的调查[黄等, 2023b](https://arxiv.org/html/2402.16363v6#bib.bib92)。

#### 7.5.1 替代注意力设计

在变换器架构的核心是自注意力机制。对于仅解码器模型的推理，如果过去的上下文很长，计算所有过去的键并与过去的值计算会带来计算和内存瓶颈。先前的工作发现，并非所有的过去标记都需要被关注，以保持模型推理性能。Landmark Attention（Mohtashami 和 Jaggi，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib151) ]）引入了特殊的地标注意力到序列中，以总结以下标记块的信息。新的查询会首先关注地标标记，以确定块中的以下标记是否需要用于预测下一个词，从而减少注意力计算，同时保持注意力的随机访问特性。早期，Funnel-Transformer（Dai 等，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib30) ]）也采取了在块级别进行注意力的相同目标。不同的是，他们在编码器部分引入了下采样，并在解码器部分引入了上采样方法。减少的 FLOPs 使他们能够构建一个更深且更宽的模型，在相同计算预算下超越原始模型。另一方面，Longformer（Beltagy 等，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib11) ]）早期尝试将滑动窗口注意力与全局注意力结合，其中他们只允许少量预定义的标记关注序列中的所有标记，而其他标记则执行滑动窗口注意力，并且还关注这些选定的全局注意标记。同时，ETC（Ainslie 等，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib4) ]）在输入中引入了一个 2 级层次结构，使普通的长输入标记可以执行滑动窗口注意力，而从原始输入中提取并下采样的辅助全局标记可以执行正常的注意力。普通输入被允许关注全局输入，从而获取全局上下文信息。同样，LongT5（[Guo 等，2022b](https://arxiv.org/html/2402.16363v6#bib.bib73) ）提出了一种更简单的方法，通过使用大小为 16 的均值池化直接下采样长的和先前的上下文，下采样的键和值直接附加在其余输入序列的前面。然后，模型的其余部分可以在前面附加的下采样上下文摘要标记的额外注意下执行滑动窗口注意力。在预训练变得非常昂贵的 LLM 时代，StreamingLLM（[Xiao 等，2023b](https://arxiv.org/html/2402.16363v6#bib.bib216) ）和 LM Infinite（Han 等，[[2023](https://arxiv.org/html/2402.16363v6#bib.bib76) ]）同时提出了一个插入式的滑动窗口注意力模式作为 LLM 的插件工具，以增强 LLM 的长上下文能力。特别是，StreamingLLM 指出，由于变换器中 softmax 操作的机制，输入的开始标记对于保持自注意力性能至关重要。修改后的注意力掩码在长上下文语言建模中取得了强大的效果，而无需额外的模型微调。此外，$H_{2}O$（[Zhang 等，2024b](https://arxiv.org/html/2402.16363v6#bib.bib242) ）通过仅关注从先前预填充的输入上下文中感兴趣的标记来降低自注意力的计算复杂度。为此，他们建立了一个用于选择标记的经验性神谕。该方法已显示出对长上下文 LLM 的益处。

#### 7.5.2 递归与检索

Transformer-XL Dai 等人，[[2019](https://arxiv.org/html/2402.16363v6#bib.bib31)] 提出了在语言模型中引入段级递归结构，以提升当前语言模型在长上下文能力上的表现。该方法将前一个段落的最后一层输出存储起来，并附加到当前层，从而大幅度增加了模型的依赖距离。Segatron（Bai 等人，[[2021](https://arxiv.org/html/2402.16363v6#bib.bib8)]）和 Compressive Transformer（Rae 等人，[[2019](https://arxiv.org/html/2402.16363v6#bib.bib166)]）在之前的思想基础上进行扩展。Segatron 通过段感知机制提升了位置嵌入的段级递归，从词级、句子级等多个层次进行扩展。Compressive Transformer 提出了二级压缩内存 FIFO 队列，因此过去的段上下文不应被丢弃，而是通过其自定义函数进行压缩并存储在队列中，以延长上下文依赖的长度。在大语言模型时代，Dynamic Memory Compression Nawrot 等人，[[2024](https://arxiv.org/html/2402.16363v6#bib.bib153)] 也遵循了递归思想，通过压缩上下文动态决定如何压缩先前的上下文信息，从而在保持远程信息的同时减少注意力的序列长度。此外，除了段级别的研究，Fan 等人，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib51)] 还研究了回溯递归。Memorizing Transformer（Wu 等人，[[2022](https://arxiv.org/html/2402.16363v6#bib.bib211)]）和 Memformer（Wu 等人，[[2020](https://arxiv.org/html/2402.16363v6#bib.bib207)]）结合了检索和本地缓存以及遗忘机制。

另一方面，跟随不需要每个过去的标记来生成当前标记的趋势，过去的 KV 缓存可以物理上放置在更远的位置，即次级存储，以便在需要时检索特定的键值对。因此，另一种提升 LLM 的方法是通过检索增强生成（RAG）。RAG 本身是一个热门话题，包含了丰富的技术和过去的工作。由于我们论文的范围有限，我们友好地推荐以下关于 RAG 的全面综述，供感兴趣的读者参考：Gao 等，[2023](https://arxiv.org/html/2402.16363v6#bib.bib58)和 Zhao 等，[2024](https://arxiv.org/html/2402.16363v6#bib.bib243)。为了应对本节开头提出的长上下文能力的特定动机，LangChain Pandya 和 Holia，[2023](https://arxiv.org/html/2402.16363v6#bib.bib160) 是通过检索缓解聊天机器人的过去长对话的流行方法。LangChain 是一个开源工具，专门用于使用 LLM 计算用户输入的长文档和文件的嵌入，因此后续根据用户的提示，通过余弦相似度指标检索最相关的内容。此外，还有许多其他快速发展的相关工作（Borgeaud 等，[2021](https://arxiv.org/html/2402.16363v6#bib.bib13)，Bertsch 等，[2024](https://arxiv.org/html/2402.16363v6#bib.bib12)，Zhong 等，[2023](https://arxiv.org/html/2402.16363v6#bib.bib245)，[Zhou 等，2023b](https://arxiv.org/html/2402.16363v6#bib.bib248)，Kynoch 等，[2023](https://arxiv.org/html/2402.16363v6#bib.bib113)，Modarressi 等，[2023](https://arxiv.org/html/2402.16363v6#bib.bib149)，Guu 等，[2020](https://arxiv.org/html/2402.16363v6#bib.bib75)，[Wang 等，2024b](https://arxiv.org/html/2402.16363v6#bib.bib202)）在长上下文设置中的检索方面。

#### 7.5.3 操作位置编码

在预训练期间，变换器的位置信息编码未见过长度超过固定限制的输入序列。此外，由于位置信息编码通常基于三角函数，原始的变换器无法外推到不熟悉的更长序列长度。早期技术在软最大操作之前向注意力图中添加了注意力偏置。ALiBi（Press 等，[2021](https://arxiv.org/html/2402.16363v6#bib.bib164)）引入了设计这种注意力偏置的启发式方法，在变换器架构的长上下文外推任务中取得了早期成功。此外，Kerple（Chi 等，[2022](https://arxiv.org/html/2402.16363v6#bib.bib22)）和 Sandwich 在前期工作的基础上，引入了可训练参数来构建注意力偏置矩阵或通过位置信息编码的正弦特性构建注意力偏置。

另一方面，另一条活跃的研究方向探讨了调整 RoPE。受到神经切线核（NTK）理论的启发，NTK-aware Scaled RoPE（Xiong 等，[2023](https://arxiv.org/html/2402.16363v6#bib.bib219)）修改了 RoPE 的基础参数；LEX（Sun 等，[2022](https://arxiv.org/html/2402.16363v6#bib.bib189)）和 PermuteFormer（Chen，[2021](https://arxiv.org/html/2402.16363v6#bib.bib19)）添加了指数衰减项；位置插值对每个标记施加线性缩放；Dynamic-NTK（Huang 和 Yau，[2019](https://arxiv.org/html/2402.16363v6#bib.bib88)）逐渐增加缩放比例。在 LLM 时代，YaRN（Peng 等，[2023](https://arxiv.org/html/2402.16363v6#bib.bib163)）使用温度因子线性缩放查询和键。Giraffe（Pal 等，[2023](https://arxiv.org/html/2402.16363v6#bib.bib159)）发现高频项受到通常训练不足的低频项的影响，并提出了一种基于幂律的缩放机制，以保护训练良好的高频信息。

## 8 结论

在这项工作中，我们回顾了高效的大型语言模型（LLM）推断。对于这一以实践为驱动的主题，我们的全面研究超越了传统的文献综述，提供了现有研究的概述以及屋顶线模型的发展。我们的第一步是开发一个屋顶线模型，这使我们能够找出 LLM 部署中的瓶颈，从而使研究人员可以采用更具体的部署策略。通过仔细整合该领域的最新发展，我们的调查涵盖了诸多关键领域，包括权重优化技术的创新、解码算法的改进以及硬件和系统级优化的进展。需要注意的是，该项目将会定期更新和维护。

## 参考文献

+   Abts 等人，[2022] Abts, D., Kimmell, G., Ling, A., Kim, J., Boyd, M., Bitar, A., Parmar, S., Ahmed, I., DiCecco, R., Han, D., 等（2022）。用于大规模机器学习的软件定义张量流处理器。发表于第 49 届年度国际计算机架构研讨会论文集，第 567-580 页。

+   Agarwal 等人，[2023] Agarwal, R., Vieillard, N., Stanczyk, P., Ramos, S., Geist, M., 和 Bachem, O.（2023）。GKD: 自回归序列模型的广义知识蒸馏。arXiv 预印本 arXiv:2306.13649。

+   Agrawal 等人，[2023] Agrawal, A., Panwar, A., Mohan, J., Kwatra, N., Gulavani, B. S., 和 Ramjee, R.（2023）。Sarathi: 通过利用分块预填充的解码实现高效的 LLM 推断。arXiv 预印本 arXiv:2308.16369。

+   Ainslie 等人，[2020] Ainslie, J., Ontanon, S., Alberti, C., Cvicek, V., Fisher, Z., Pham, P., Ravula, A., Sanghai, S., Wang, Q., 和 Yang, L.（2020）。ETC: 在变换器中编码长结构输入。arXiv 预印本 arXiv:2004.08483。

+   Alizadeh 等，[2023] Alizadeh, K., Mirzadeh, I., Belenko, D., Khatamifard, K., Cho, M., Del Mundo, C. C., Rastegari, M., 和 Farajtabar, M.（2023）。Llm in a flash：在有限内存下高效的大型语言模型推理。arXiv 预印本 arXiv:2312.11514。

+   Aminabadi 等，[2022] Aminabadi, R. Y., Rajbhandari, S., Awan, A. A., Li, C., Li, D., Zheng, E., Ruwase, O., Smith, S., Zhang, M., Rasley, J., 等（2022）。Deepspeed-inference：在前所未有的规模下实现变换器模型的高效推理。SC22：高性能计算、网络、存储和分析国际会议，页面 1–15。IEEE。

+   Bae 等，[2023] Bae, S., Ko, J., Song, H., 和 Yun, S.-Y.（2023）。快速且稳健的自回归语言模型早期退出框架，具有同步并行解码。

+   Bai 等，[2021] Bai, H., Shi, P., Lin, J., Xie, Y., Tan, L., Xiong, K., Gao, W., 和 Li, M.（2021）。Segatron：面向分段的变换器用于语言建模和理解。发表于 AAAI 人工智能会议论文集，第 35 卷，页面 12526–12534。

+   Baier-Reinio 和 Sterck，[2020] Baier-Reinio, A. 和 Sterck, H. D.（2020）。N-ode 变换器：一种使用神经常微分方程的深度自适应变换器。

+   Behdin 等，[2023] Behdin, K., Acharya, A., Gupta, A., Keerthi, S., 和 Mazumder, R.（2023）。Quantease：基于优化的语言模型量化——一种高效且直观的算法。arXiv 预印本 arXiv:2309.01885。

+   Beltagy 等，[2020] Beltagy, I., Peters, M. E., 和 Cohan, A.（2020）。Longformer：长文档变换器。arXiv 预印本 arXiv:2004.05150。

+   Bertsch 等，[2024] Bertsch, A., Alon, U., Neubig, G., 和 Gormley, M.（2024）。Unlimiformer：具有无限长度输入的长程变换器。《神经信息处理系统进展》，36。

+   Borgeaud 等，[2021] Borgeaud, S. 等（2021）。通过从万亿个标记中检索来改进语言模型。arxiv 电子印刷本，art. arXiv 预印本 arXiv:2112.04426。

+   Brown 等，[2020] Brown, T., Mann, B., Ryder, N., Subbiah, M., Kaplan, J. D., Dhariwal, P., Neelakantan, A., Shyam, P., Sastry, G., Askell, A., 等（2020）。语言模型是少样本学习者。《神经信息处理系统进展》，33:1877–1901。

+   Cai 等，[2024] Cai, T., Li, Y., Geng, Z., Peng, H., Lee, J. D., Chen, D., 和 Dao, T.（2024）。Medusa：具有多个解码头的简单 LLM 推理加速框架。arXiv 预印本 arXiv:2401.10774。

+   Chae 等，[2023] Chae, H., Song, Y., Ong, K. T.-i., Kwon, T., Kim, M., Yu, Y., Lee, D., Kang, D., 和 Yeo, J.（2023）。对话链思维蒸馏用于常识感知对话代理。arXiv 预印本 arXiv:2310.09343。

+   Chee 等，[2023] Chee, J., Cai, Y., Kuleshov, V., 和 De Sa, C.（2023）。Quip：具有保障的大型语言模型 2 位量化。《神经信息处理系统进展》。

+   [18] Chen, C., Borgeaud, S., Irving, G., Lespiau, J.-B., Sifre, L., 和 Jumper, J. (2023a). 通过推测采样加速大语言模型解码。arXiv 预印本 arXiv:2302.01318。

+   Chen, [2021] Chen, P. (2021). Permuteformer：用于长序列的高效相对位置编码。

+   Chen et al., [2018] Chen, T., Moreau, T., Jiang, Z., Zheng, L., Yan, E., Shen, H., Cowan, M., Wang, L., Hu, Y., Ceze, L., 等. (2018). Tvm：一个用于深度学习的自动化端到端优化编译器。在第 13 届 USENIX 操作系统设计与实现研讨会（OSDI 18），第 578–594 页。

+   [21] Chen, Y., Pan, X., Li, Y., Ding, B., 和 Zhou, J. (2023b). Ee-llm：利用 3D 并行大规模训练和推理早期退出的大语言模型。

+   Chi et al., [2022] Chi, T.-C., Fan, T.-H., Ramadge, P. J., 和 Rudnicky, A. (2022). Kerple：用于长度外推的核化相对位置嵌入。神经信息处理系统进展，35:8386–8399。

+   Choi et al., [2023] Choi, J., Park, J., Kyung, K., Kim, N. S., 和 Ahn, J. H. (2023). 释放 pim 的潜力：加速基于变换器的生成模型的大批量推理。IEEE 计算机架构信函。

+   Choi et al., [2018] Choi, J., Wang, Z., Venkataramani, S., Chuang, P. I.-J., Srinivasan, V., 和 Gopalakrishnan, K. (2018). Pact：用于量化神经网络的参数化裁剪激活。arXiv 预印本 arXiv:1805.06085。

+   Chowdhery et al., [2022] Chowdhery, A., Narang, S., Devlin, J., Bosma, M., Mishra, G., Roberts, A., Barham, P., Chung, H. W., Sutton, C., Gehrmann, S., Schuh, P., Shi, K., Tsvyashchenko, S., Maynez, J., Rao, A., Barnes, P., Tay, Y., Shazeer, N., Prabhakaran, V., Reif, E., Du, N., Hutchinson, B., Pope, R., Bradbury, J., Austin, J., Isard, M., Gur-Ari, G., Yin, P., Duke, T., Levskaya, A., Ghemawat, S., Dev, S., Michalewski, H., Garcia, X., Misra, V., Robinson, K., Fedus, L., Zhou, D., Ippolito, D., Luan, D., Lim, H., Zoph, B., Spiridonov, A., Sepassi, R., Dohan, D., Agrawal, S., Omernick, M., Dai, A. M., Pillai, T. S., Pellat, M., Lewkowycz, A., Moreira, E., Child, R., Polozov, O., Lee, K., Zhou, Z., Wang, X., Saeta, B., Diaz, M., Firat, O., Catasta, M., Wei, J., Meier-Hellstern, K., Eck, D., Dean, J., Petrov, S., 和 Fiedel, N. (2022). Palm：通过路径扩展语言建模。

+   Chu et al., [2023] Chu, X., Qiao, L., Lin, X., Xu, S., Yang, Y., Hu, Y., Wei, F., Zhang, X., Zhang, B., Wei, X., 等. (2023). Mobilevlm：一个快速、可复现且强大的移动设备视觉语言助手。arXiv 预印本 arXiv:2312.16886。

+   Chu et al., [2024] Chu, X., Qiao, L., Zhang, X., Xu, S., Wei, F., Yang, Y., Sun, X., Hu, Y., Lin, X., Zhang, B., 等. (2024). Mobilevlm v2：更快、更强大的视觉语言模型基线。arXiv 预印本 arXiv:2402.03766。

+   Corro 等人，[2023] Corro, L. D., Giorno, A. D., Agarwal, S., Yu, B., Awadallah, A., 和 Mukherjee, S. (2023). Skipdecode：具有批处理和缓存的自回归跳过解码以实现高效的 LLM 推理。

+   Courbariaux 等人，[2015] Courbariaux, M., Bengio, Y., 和 David, J.-P. (2015). Binaryconnect：在传播过程中使用二进制权重训练深度神经网络。神经信息处理系统进展，28。

+   Dai 等人，[2020] Dai, Z., Lai, G., Yang, Y., 和 Le, Q. (2020). Funnel-transformer：过滤序列冗余以实现高效的语言处理。神经信息处理系统进展，33:4271–4282。

+   Dai 等人，[2019] Dai, Z., Yang, Z., Yang, Y., Carbonell, J., Le, Q. V., 和 Salakhutdinov, R. (2019). Transformer-xl：超越固定长度上下文的注意力语言模型。arXiv 预印本 arXiv:1901.02860。

+   Dao，[2023] Dao, T. (2023). Flashattention-2：更快的注意力机制，具有更好的并行性和工作分配。

+   Dao 等人，[2022] Dao, T., Fu, D., Ermon, S., Rudra, A., 和 Ré, C. (2022). Flashattention：快速且内存高效的确切注意力机制，具有 IO 意识。神经信息处理系统进展，35:16344–16359。

+   Dao 等人，[2023] Dao, T., Haziza, D., Massa, F., 和 Sizov, G. (2023). 长上下文推理的 Flash-decoding。

+   Darvish Rouhani 等人，[2023] Darvish Rouhani, B., Zhao, R., Elango, V., Shafipour, R., Hall, M., Mesmakhosroshahi, M., More, A., Melnick, L., Golub, M., Varatkar, G., 等人 (2023). 共享微指数的作用微小，却能产生重大效果。在第 50 届国际计算机架构年会论文集中，页码 1–13。

+   de Jong 等人，[2023] de Jong, M., Zemlyanskiy, Y., Ainslie, J., FitzGerald, N., Sanghai, S., Sha, F., 和 Cohen, W. (2023). Fido：为更强的性能和更快的推理优化的解码器融合。

+   Deng 等人，[2023] Deng, G., Liu, Y., Li, Y., Wang, K., Zhang, Y., Li, Z., Wang, H., Zhang, T., 和 Liu, Y. (2023). Jailbreaker：跨多个大型语言模型聊天机器人进行自动化越狱。arXiv 预印本 arXiv:2307.08715。

+   Dettmers 等人，[2022] Dettmers, T., Lewis, M., Belkada, Y., 和 Zettlemoyer, L. (2022). Llm. int8 ()：大规模变换器的 8 位矩阵乘法。arXiv 预印本 arXiv:2208.07339。

+   [39] Dettmers, T., Pagnoni, A., Holtzman, A., 和 Zettlemoyer, L. (2023a). Qlora：量化 LLM 的高效微调。arXiv 预印本 arXiv:2305.14314。

+   [40] Dettmers, T., Svirschevski, R., Egiazarian, V., Kuznedelev, D., Frantar, E., Ashkboos, S., Borzunov, A., Hoefler, T., 和 Alistarh, D. (2023b). Spqr：接近无损 LLM 权重压缩的稀疏量化表示。arXiv 预印本 arXiv:2306.03078。

+   Dettmers 和 Zettlemoyer，[2023] Dettmers, T. 和 Zettlemoyer, L. (2023). 4 位精度的案例：k 位推理缩放定律。在国际机器学习会议上，页码 7750–7774。PMLR。

+   [42] Devaux, F. (2019a). 真实的内存处理加速器. 在 2019 IEEE Hot Chips 31 研讨会 (HCS)，页面 1–24\. IEEE 计算机学会。

+   [43] Devaux, F. (2019b). 真实的内存处理加速器. 在 2019 IEEE Hot Chips 31 研讨会 (HCS)，页面 1–24\. IEEE 计算机学会。

+   Devlin 等，[2019] Devlin, J., Chang, M.-W., Lee, K., 和 Toutanova, K. (2019). Bert: 深度双向变换器的预训练用于语言理解。

+   Devvrit 等，[2023] Devvrit, Kudugunta, S., Kusupati, A., Dettmers, T., Chen, K., Dhillon, I., Tsvetkov, Y., Hajishirzi, H., Kakade, S., Farhadi, A., 和 Jain, P. (2023). Matformer: 弹性推理的嵌套变换器。

+   Din 等，[2023] Din, A. Y., Karidi, T., Choshen, L., 和 Geva, M. (2023). 跳到结论：用线性变换加速变换器。

+   Ding 等，[2023] Ding, T., Chen, T., Zhu, H., Jiang, J., Zhong, Y., Zhou, J., Wang, G., Zhu, Z., Zharkov, I., 和 Liang, L. (2023). 大型语言模型的效率谱：算法综述. arXiv 预印本 arXiv:2312.00678。

+   Dong 等，[2019] Dong, Z., Yao, Z., Gholami, A., Mahoney, M. W., 和 Keutzer, K. (2019). Hawq: 具有混合精度的神经网络赫西矩阵感知量化. 在 IEEE/CVF 国际计算机视觉会议，页面 293–302。

+   Du 等，[2022] Du, N., Huang, Y., Dai, A. M., Tong, S., Lepikhin, D., Xu, Y., Krikun, M., Zhou, Y., Yu, A. W., Firat, O., 等. (2022). Glam: 高效扩展混合专家的语言模型. 在国际机器学习会议，页面 5547–5569\. PMLR。

+   Elbayad 等，[2020] Elbayad, M., Gu, J., Grave, E., 和 Auli, M. (2020). 深度自适应变换器。

+   Fan 等，[2020] Fan, A., Lavril, T., Grave, E., Joulin, A., 和 Sukhbaatar, S. (2020). 通过反馈记忆解决变换器的一些局限性. arXiv 预印本 arXiv:2002.09402。

+   Fedus 等，[2022] Fedus, W., Dean, J., 和 Zoph, B. (2022). 深度学习中稀疏专家模型的综述. arXiv 预印本 arXiv:2209.01667。

+   Fedus 等，[2021] Fedus, W., Zoph, B., 和 Shazeer, N. (2021). Switch transformers: 简单高效的稀疏性实现千亿参数模型. (2021). arXiv 预印本 cs.LG/2101.03961。

+   Frantar 和 Alistarh，[2023] Frantar, E. 和 Alistarh, D. (2023). Sparsegpt: 大型语言模型可以一次性准确修剪. ICML。

+   Frantar 等，[2022] Frantar, E., Ashkboos, S., Hoefler, T., 和 Alistarh, D. (2022). Gptq: 生成预训练变换器的精确后训练量化. arXiv 预印本 arXiv:2210.17323。

+   [56] Fu, Y., Bailis, P., Stoica, I., 和 Zhang, H. (2023a). 通过前瞻解码打破 LLM 推断的顺序依赖。

+   [57] Fu, Y., Peng, H., Ou, L., Sabharwal, A., 和 Khot, T. (2023b). 针对多步骤推理的小型语言模型专业化. arXiv 预印本 arXiv:2301.12726。

+   Gao 等，[2023] Gao, Y., Xiong, Y., Gao, X., Jia, K., Pan, J., Bi, Y., Dai, Y., Sun, J., 和 Wang, H.（2023）。用于大语言模型的检索增强生成：综述。arXiv 预印本 arXiv:2312.10997。

+   Geirhos 等，[2020] Geirhos, R., Jacobsen, J.-H., Michaelis, C., Zemel, R., Brendel, W., Bethge, M., 和 Wichmann, F. A.（2020）。深度神经网络中的捷径学习。《自然机器智能》，2(11):665–673。

+   Geva 等，[2022] Geva, M., Caciularu, A., Wang, K. R., 和 Goldberg, Y.（2022）。Transformer 前馈层通过促进词汇空间中的概念来构建预测。

+   Ghazvininejad 等，[2019] Ghazvininejad, M., Levy, O., Liu, Y., 和 Zettlemoyer, L.（2019）。Mask-predict：条件掩码语言模型的并行解码。

+   Gholami 等，[2022] Gholami, A., Kim, S., Dong, Z., Yao, Z., Mahoney, M. W., 和 Keutzer, K.（2022）。高效神经网络推理的量化方法综述。在《低功耗计算机视觉》中，第 291–326 页。Chapman and Hall/CRC。

+   Gou 等，[2021] Gou, J., Yu, B., Maybank, S. J., 和 Tao, D.（2021）。知识蒸馏：综述。《计算机视觉国际期刊》，129:1789–1819。

+   Graphcore，[2024] Graphcore（2024）。使用 Graphcore 的 IPU 和 Hugging Face 的任务与教程。 [`github.com/graphcore/Gradient-HuggingFace`](https://github.com/graphcore/Gradient-HuggingFace)。访问日期：2024 年 3 月 10 日。

+   Groq，[2023] Groq（2023）。Groq 在 Meta AI 基础 LLM Llama 2.70b 上创造了每用户每秒 300 个令牌的新大语言模型性能记录。 [`wow.groq.com/groq-sets-new-large-language-model-performance-record-of-300-tokens-per-second-per-user-on-meta-ai-foundational-llm-llama-2-70b/`](https://wow.groq.com/groq-sets-new-large-language-model-performance-record-of-300-tokens-per-second-per-user-on-meta-ai-foundational-llm-llama-2-70b/)。

+   Gu 等，[2017] Gu, J., Bradbury, J., Xiong, C., Li, V. O., 和 Socher, R.（2017）。非自回归神经机器翻译。arXiv 预印本 arXiv:1711.02281。

+   Gu 和 Kong，[2020] Gu, J. 和 Kong, X.（2020）。完全非自回归神经机器翻译：实践技巧。

+   Gu 等，[2023] Gu, Y., Dong, L., Wei, F., 和 Huang, M.（2023）。大语言模型的知识蒸馏。arXiv 预印本 arXiv:2306.08543。

+   [69] Guo, C., Tang, J., Hu, W., Leng, J., Zhang, C., Yang, F., Liu, Y., Guo, M., 和 Zhu, Y.（2023a）。Olive：通过硬件友好的异常值-受害者对量化加速大语言模型。在第 50 届国际计算机架构年会论文集中，第 1–15 页。

+   [70] Guo, C., Zhang, C., Leng, J., Liu, Z., Yang, F., Liu, Y., Guo, M., 和 Zhu, Y.（2022a）。Ant：利用自适应数值数据类型进行低位深度神经网络量化。在 2022 年第 55 届 IEEE/ACM 国际微架构会议（MICRO）论文集中，第 1414–1433 页。IEEE。

+   [71] Guo, H., Greengard, P., Xing, E. P., 和 Kim, Y.（2023b）。Lq-lora: 低秩加量化矩阵分解用于高效语言模型微调。arXiv 预印本 arXiv:2311.12023。

+   Guo 等，[2020] Guo, J., Xu, L., 和 Chen, E.（2020）。联合掩码的序列到序列模型用于非自回归神经机器翻译。在 Jurafsky, D., Chai, J., Schluter, N., 和 Tetreault, J. 编者，《第 58 届计算语言学协会年会论文集》，第 376–385 页，在线。计算语言学协会。

+   [73] Guo, M., Ainslie, J., Uthus, D., Ontanon, S., Ni, J., Sung, Y.-H., 和 Yang, Y.（2022b）。Longt5: 高效的文本到文本变换器用于长序列。

+   [74] Guo, S., Xu, J., Zhang, L. L., 和 Yang, M.（2023c）。Compresso: 结构化剪枝与协作提示学习紧凑的大规模语言模型。arXiv 预印本 arXiv:2310.05015。

+   Guu 等，[2020] Guu, K., Lee, K., Tung, Z., Pasupat, P., 和 Chang, M.（2020）。检索增强语言模型预训练。在国际机器学习会议上，第 3929–3938 页。PMLR。

+   Han 等，[2023] Han, C., Wang, Q., Xiong, W., Chen, Y., Ji, H., 和 Wang, S.（2023）。Lm-infinite: 简单的即时长度泛化用于大规模语言模型。arXiv 预印本 arXiv:2308.16137。

+   He 等，[2023] He, Z., Zhong, Z., Cai, T., Lee, J. D., 和 He, D.（2023）。Rest: 基于检索的推测解码。arXiv 预印本 arXiv:2311.08252。

+   Hinton 等，[2015] Hinton, G., Vinyals, O., 和 Dean, J.（2015）。提取神经网络中的知识。arXiv 预印本 arXiv:1503.02531。

+   Hoffmann 等，[2022] Hoffmann, J., Borgeaud, S., Mensch, A., Buchatskaya, E., Cai, T., Rutherford, E., de Las Casas, D., Hendricks, L. A., Welbl, J., Clark, A., Hennigan, T., Noland, E., Millican, K., van den Driessche, G., Damoc, B., Guy, A., Osindero, S., Simonyan, K., Elsen, E., Rae, J. W., Vinyals, O., 和 Sifre, L.（2022）。训练计算优化的大规模语言模型。

+   Holmes 等，[2024] Holmes, C., Tanaka, M., Wyatt, M., Awan, A. A., Rasley, J., Rajbhandari, S., Aminabadi, R. Y., Qin, H., Bakhtiari, A., Kurilenko, L., 等（2024）。Deepspeed-fastgen: 通过 MII 和 Deepspeed-inference 实现高吞吐量的文本生成。arXiv 预印本 arXiv:2401.08671。

+   Hong 等，[2023] Hong, K., Dai, G., Xu, J., Mao, Q., Li, X., Liu, J., Chen, K., Dong, H., 和 Wang, Y.（2023）。Flashdecoding++: 在 GPU 上加速大规模语言模型推理。arXiv 预印本 arXiv:2311.01282。

+   Hong 等，[2022] Hong, S., Moon, S., Kim, J., Lee, S., Kim, M., Lee, D., 和 Kim, J.-Y.（2022）。Dfx: 一种低延迟的多 FPGA 设备，用于加速基于变换器的文本生成。在 2022 第 55 届 IEEE/ACM 微架构国际研讨会（MICRO），第 616–630 页。IEEE。

+   Hooper 等，[2024] Hooper, C., Kim, S., Mohammadzadeh, H., Mahoney, M. W., Shao, Y. S., Keutzer, K., 和 Gholami, A. (2024). Kvquant: 通过 kv 缓存量化实现 1000 万上下文长度的 LLM 推理。arXiv 预印本 arXiv:2401.18079。

+   Hou 等，[2020] Hou, L., Huang, Z., Shang, L., Jiang, X., Chen, X., 和 Liu, Q. (2020). Dynabert: 具有自适应宽度和深度的动态 BERT。

+   Hsieh 等，[2023] Hsieh, C.-Y., Li, C.-L., Yeh, C.-K., Nakhost, H., Fujii, Y., Ratner, A., Krishna, R., Lee, C.-Y., 和 Pfister, T. (2023). 分步蒸馏！用更少的训练数据和更小的模型尺寸超越更大的语言模型。arXiv 预印本 arXiv:2305.02301。

+   Hu 等，[2021] Hu, E. J., Shen, Y., Wallis, P., Allen-Zhu, Z., Li, Y., Wang, S., Wang, L., 和 Chen, W. (2021). Lora: 大型语言模型的低秩适配。arXiv 预印本 arXiv:2106.09685。

+   Hu 等，[2023] Hu, Z., Lan, Y., Wang, L., Xu, W., Lim, E.-P., Lee, R. K.-W., Bing, L., 和 Poria, S. (2023). Llm-adapters: 一种用于大型语言模型参数高效微调的适配器家族。arXiv 预印本 arXiv:2304.01933。

+   Huang 和 Yau，[2019] Huang, J. 和 Yau, H.-T. (2019). 深度神经网络和神经切线层级的动态。

+   [89] Huang, L., Yu, W., Ma, W., Zhong, W., Feng, Z., Wang, H., Chen, Q., Peng, W., Feng, X., Qin, B., 等。 (2023a). 大型语言模型中的幻觉调查：原则、分类法、挑战和未解问题。arXiv 预印本 arXiv:2311.05232。

+   Huang 等，[2024] Huang, W., Liu, Y., Qin, H., Li, Y., Zhang, S., Liu, X., Magno, M., 和 Qi, X. (2024). Billm: 推进 LLM 后训练量化的极限。arXiv 预印本 arXiv:2402.04291。

+   Huang 等，[2022] Huang, Y., Chen, Y., Yu, Z., 和 McKeown, K. (2022). 上下文学习蒸馏：转移预训练语言模型的少样本学习能力。arXiv 预印本 arXiv:2212.10670。

+   [92] Huang, Y., Xu, J., Jiang, Z., Lai, J., Li, Z., Yao, Y., Chen, T., Yang, L., Xin, Z., 和 Ma, X. (2023b). 推进长上下文大型语言模型的变换器架构：综合调查。arXiv 预印本 arXiv:2311.12351。

+   Hubara 等，[2016] Hubara, I., Courbariaux, M., Soudry, D., El-Yaniv, R., 和 Bengio, Y. (2016). 二值化神经网络。神经信息处理系统进展，29。

+   HuggingFace，[2022] HuggingFace (2022). Hugging Face 加速。

+   Javaheripi 等，[2023] Javaheripi, M., Bubeck, S., Abdin, M., Aneja, J., Bubeck, S., Mendes, C. C. T., Chen, W., Del Giorno, A., Eldan, R., Gopi, S., 等。 (2023). Phi-2: 小型语言模型的惊人力量。微软研究博客。

+   Jawahar 等，[2023] Jawahar, G., Mukherjee, S., Liu, X., Kim, Y. J., Mageed, M. A., Laks Lakshmanan, V., Hassan, A., Bubeck, S., 和 Gao, J. (2023). Automoe: 具有自适应计算的异构专家混合模型，用于高效的神经机器翻译。计算语言学协会发现：ACL 2023，页码 9116–9132。

+   Ji 等人，[2023] Ji, Y., Wang, J., Li, J., Chen, Q., Chen, W., 和 Zhang, M. (2023). 通过解耦表示和等角紧框架实现早期退出。发表于 Rogers, A., Boyd-Graber, J., 和 Okazaki, N. 主编的《计算语言学协会发现：ACL 2023》，第 14128–14142 页，多伦多，加拿大。计算语言学协会。

+   Jiang 等人，[2024] Jiang, A. Q., Sablayrolles, A., Roux, A., Mensch, A., Savary, B., Bamford, C., Chaplot, D. S., Casas, D. d. l., Hanna, E. B., Bressand, F., 等人 (2024). Mixtral 专家。arXiv 预印本 arXiv:2401.04088。

+   Jiang 等人，[2023] Jiang, Y., Chan, C., Chen, M., 和 Wang, W. (2023). Lion: 闭源大型语言模型的对抗性蒸馏。arXiv 预印本 arXiv:2305.12870。

+   Jonatan 等人，[2024] Jonatan, G., Cho, H., Son, H., Wu, X., Livesay, N., Mora, E., Shivdikar, K., Abellán, J. L., Joshi, A., Kaeli, D., 等人 (2024). 使用实际系统评估处理内存中的可扩展性限制。ACM 计算系统测量与分析会议录，8(1):1–28。

+   Kao 等人，[2023] Kao, S.-C., Subramanian, S., Agrawal, G., Yazdanbakhsh, A., 和 Krishna, T. (2023). Flat: 一种优化的数据流，用于缓解注意力瓶颈。发表于第 28 届 ACM 国际编程语言和操作系统架构支持会议，卷 2，第 295–310 页。

+   Kaplan 等人，[2020] Kaplan, J., McCandlish, S., Henighan, T., Brown, T. B., Chess, B., Child, R., Gray, S., Radford, A., Wu, J., 和 Amodei, D. (2020). 神经语言模型的缩放法则。

+   [103] Kim, J., Lee, J. H., Kim, S., Park, J., Yoo, K. M., Kwon, S. J., 和 Lee, D. (2023a). 通过子 4 位整数量化的内存高效微调压缩大型语言模型。arXiv 预印本 arXiv:2305.14152。

+   [104] Kim, M., Lee, S., Lee, J., Hong, S., Chang, D.-S., Sung, W., 和 Choi, J. (2023b). 适用于三值权重生成语言模型的令牌尺度对数提取。arXiv 预印本 arXiv:2308.06744。

+   [105] Kim, S., Hooper, C., Gholami, A., Dong, Z., Li, X., Shen, S., Mahoney, M. W., 和 Keutzer, K. (2023c). Squeezellm: 密集与稀疏量化。arXiv 预印本 arXiv:2306.07629。

+   [106] Kim, S., Hooper, C., Wattanawong, T., Kang, M., Yan, R., Genc, H., Dinh, G., Huang, Q., Keutzer, K., Mahoney, M. W., Shao, Y. S., 和 Gholami, A. (2023d). 变压器推理的全栈优化：一项调查。

+   [107] Kim, S., Mangalam, K., Moon, S., Malik, J., Mahoney, M. W., Gholami, A., 和 Keutzer, K. (2023e). 使用大小解码器的推测解码。

+   Kishore Kumar 和 Schneider，[2017] Kishore Kumar, N. 和 Schneider, J. (2017). 矩阵低秩近似的文献综述。线性与多线性代数，65(11):2212–2244。

+   Kossmann 等人，[2022] Kossmann, F., Jia, Z., 和 Aiken, A. (2022). 使用动态重新编译优化专家混合。arXiv 预印本 arXiv:2205.01848。

+   Kwon 等，[2023] Kwon, W., Li, Z., Zhuang, S., Sheng, Y., Zheng, L., Yu, C. H., Gonzalez, J., Zhang, H., 和 Stoica, I. (2023). 大语言模型服务的高效内存管理与分页注意力。在第 29 届操作系统原理研讨会论文集中，第 611-626 页。

+   Kwon 等，[2021] Kwon, Y., Lee, S. H., Lee, J., Kwon, S., Ryu, J., Son, J., O, S., Yu, H., Lee, H., Kim, S. Y., Cho, Y., Kim, J. G., Choi, J., Shin, H., Kim, J., Phuah, B., Kim, H., Song, M. J., Choi, A., Kim, D., Kim, S., Kim, E., Wang, D., Kang, S., Ro, Y., Seo, S., Song, J., Youn, J., Sohn, K., 和 Kim, N. S. (2021). 25.4 一种基于 HBM2 的 20nm 6GB 功能内存 DRAM，具有 1.2Tflops 可编程计算单元，使用银行级并行性，适用于机器学习应用。IEEE 国际固态电路会议，ISSCC 2021，美国加利福尼亚州旧金山，2021 年 2 月 13-22 日，第 350-352 页。IEEE。

+   Kwon 等，[2022] Kwon, Y., Vladimir, K., Kim, N., Shin, W., Won, J., Lee, M., Joo, H., Choi, H., Kim, G., An, B., 等 (2022). GDDR6-AIM 的系统架构和软件栈。在 2022 IEEE 热芯片 34 研讨会 (HCS) 中，第 1-25 页。IEEE。

+   Kynoch 等，[2023] Kynoch, B., Latapie, H., 和 van der Sluis, D. (2023). Recallm: 一种适用于大语言模型的具有时间理解的可适应记忆机制。

+   Lan 等，[2023] Lan, T., Cai, D., Wang, Y., Huang, H., 和 Mao, X.-L. (2023). 复制就是你所需的一切。

+   Langroudi 等，[2021] Langroudi, H. F., Karia, V., Carmichael, Z., Zyarah, A., Pandit, T., Gustafson, J. L., 和 Kudithipudi, D. (2021). Alps: 具有广义 posits 的深度神经网络自适应量化。IEEE/CVF 计算机视觉与模式识别会议论文集，第 3100-3109 页。

+   LeCun 等，[1989] LeCun, Y., Denker, J., 和 Solla, S. (1989). 最优脑损伤。神经信息处理系统进展，2。

+   Lee 等，[2023] Lee, C., Jin, J., Kim, T., Kim, H., 和 Park, E. (2023). Owq: 从激活异常值中学习的重量量化经验教训，适用于大语言模型。arXiv 预印本 arXiv:2306.02272。

+   Lee 等，[2018] Lee, J., Mansimov, E., 和 Cho, K. (2018). 通过迭代精化进行确定性非自回归神经序列建模。

+   Lee-Thorp 和 Ainslie，[2022] Lee-Thorp, J. 和 Ainslie, J. (2022). 稀疏混合器：结合 moe 和 mixing 以构建更高效的 bert。arXiv 预印本 arXiv:2205.12399。

+   Lefaudeux 等，[2022] Lefaudeux, B., Massa, F., Liskovich, D., Xiong, W., Caggiano, V., Naren, S., Xu, M., Hu, J., Tintore, M., Zhang, S., Labatut, P., Haziza, D., Wehrstedt, L., Reizenstein, J., 和 Sizov, G. (2022). xformers: 一个模块化和可破解的变换器建模库。[`github.com/facebookresearch/xformers`](https://github.com/facebookresearch/xformers)。

+   Lepikhin 等，[2020] Lepikhin, D., Lee, H., Xu, Y., Chen, D., Firat, O., Huang, Y., Krikun, M., Shazeer, N., 和 Chen, Z.（2020）。Gshard：通过条件计算和自动分片扩展巨型模型。arXiv 预印本 arXiv:2006.16668。

+   Leviathan 等，[2023] Leviathan, Y., Kalman, M., 和 Matias, Y.（2023）。通过猜测解码实现变压器的快速推理。

+   [123] 李玲，李庆，张博，和楚翔（2023a）。规范调整：大规模语言模型的高性能低位量化。arXiv 预印本 arXiv:2309.02784。

+   李玲 等，[2021] 李玲，林颖，陈东，任帅，李平，周杰，和孙晓（2021）。Cascadebert：通过校准完整模型级联加速预训练语言模型的推理。

+   [125] 李玲，Hessel, J., 余阳，任轩，Chang, K.-W., 和崔云（2023b）。符号链式思考蒸馏：小模型也可以“逐步思考”。arXiv 预印本 arXiv:2306.14050。

+   [126] 李庆，张磊，李玲，姚鹏，张博，楚翔，孙勇，杜磊，和谢宇（2023c）。Fptq：大规模语言模型的细粒度后训练量化。arXiv 预印本 arXiv:2308.15987。

+   李燕 等，[2024] 李燕，魏飞，张超，和张华（2024）。Eagle：猜测采样需要重新考虑特征不确定性。arXiv 预印本 arXiv:2401.15077。

+   [128] 李燕，余阳，梁晨，何鹏，Karampatziakis, N., 陈伟，和赵婷（2023d）。Loftq：针对大规模语言模型的 Lora 微调感知量化。arXiv 预印本 arXiv:2310.08659。

+   李泽 等，[2019] 李泽，林志，何栋，田丰，秦天，王磊，和刘天阳（2019）。基于提示的非自回归机器翻译训练。arXiv 预印本 arXiv:1909.06708。

+   [130] 李泽，刘晓，朱博，董志，顾强，和 Keutzer, K.（2023e）。Qft：使用可负担资源的量化全参数调优。arXiv 预印本 arXiv:2310.07147。

+   [131] 梁晨，姜辉，李泽，唐翔，尹博，和赵婷（2023a）。Homodistil：预训练变压器的同质任务无关蒸馏。arXiv 预印本 arXiv:2302.09632。

+   [132] 梁晨，左松，张强，何鹏，陈伟，和赵婷（2023b）。少即是多：任务感知层级蒸馏用于语言模型压缩。国际机器学习大会论文集，20852–20867 页。PMLR。

+   梁涛 等，[2021] 梁涛，Glossner, J., 王磊，石磊，和张旭（2021）。深度神经网络加速的剪枝和量化：综述。Neurocomputing, 461:370–403。

+   林斌 等，[2024] 林斌，唐志，叶颖，崔杰，朱博，金鹏，张杰，宁美，和袁磊（2024）。Moe-llava：面向大型视觉-语言模型的专家混合。arXiv 预印本 arXiv:2401.15947。

+   林江 等，[2023] 林江，唐杰，唐辉，杨莎，邓晓，和韩松（2023）。Awq：用于大语言模型压缩和加速的激活感知权重量化。arXiv 预印本 arXiv:2306.00978。

+   [136] 刘铭、曾浩、王斌、张鹏、唐杰 和 董宇 (2024a)。Apar: LLMs 能够进行自动并行自回归解码。

+   刘等 (2020) 刘伟、周鹏、赵震、王志、邓浩 和 具强 (2020)。Fastbert: 一种具有自适应推理时间的自蒸馏 BERT。

+   [138] 刘晓、胡莉、Bailis、Stoica、邓卓、Cheung 和 张华 (2023a)。在线猜测解码。arXiv 预印本 arXiv:2310.07177。

+   刘等 (2022) 刘晓、孙婷、何杰、吴建、吴亮、张晓、姜华、曹志、黄翔 和 邱晓 (2022)。迈向高效 NLP: 一个标准评估和一个强基准。在 Carpuat, M., de Marneffe, M.-C., 和 Meza Ruiz, I. V. 编辑的《2022 年北美计算语言学协会年会论文集: 人类语言技术》，第 3288-3303 页，西雅图，美国。计算语言学协会。

+   [140] 刘志远、Oguz、赵辰、张怡、Stock、Mehdad、石宇、Krishnamoorthi 和 Chandra (2023b)。Llm-qat: 数据无关的量化感知训练用于大型语言模型。arXiv 预印本 arXiv:2305.17888。

+   [141] 刘志远、王俊、Dao、周涛、袁博、宋志、Shrivastava、张超、田野、Re 和 陈波 (2023c)。Déjà vu: 上下文稀疏性用于高效的 LLM 推理时。

+   [142] 刘志远、袁俊、金辉、钟帅、徐磊、Braverman、陈波 和 胡晓 (2024b)。Kivi: 一种无调优的非对称 2bit 量化用于 kv 缓存。arXiv 预印本 arXiv:2402.02750。

+   Ma 等 (2024) Ma, H., Zhu, Y., Zhang, C., Zhao, P., Wu, B., Huang, L.-K., Hu, Q., 和 Wu, B. (2024)。面向视觉-语言模型泛化的不可变测试时适应。arXiv 预印本 arXiv:2403.00376。

+   Ma 等 (2023) Ma, X., Fang, G., 和 Wang, X. (2023)。LLM-pruner: 大型语言模型的结构化剪枝研究。arXiv 预印本 arXiv:2305.11627。

+   孟凯等 (2022) 孟凯、Bau、Andonian 和 Belinkov (2022)。定位和编辑 GPT 中的事实关联。在 Koyejo, S., Mohamed, S., Agarwal, A., Belgrave, D., Cho, K., 和 Oh, A. 编辑的《神经信息处理系统进展 35: 2022 年神经信息处理系统年会》，NeurIPS 2022，美国路易斯安那州新奥尔良，2022 年 11 月 28 日 - 12 月 9 日。

+   [146] 苗鑫、Oliaro、张震、程晓、金辉、陈涛 和 贾志 (2023a)。迈向高效的生成性大型语言模型服务: 从算法到系统的调查。arXiv 预印本 arXiv:2312.15234。

+   [147] 苗鑫、Oliaro、张震、程晓、王志、黄荣、陈泽、Arfeen、Abhyankar 和 贾志 (2023b)。Specinfer: 通过推测推理和令牌树验证加速生成 LLM 服务。arXiv 预印本 arXiv:2305.09781。

+   Micikevicius 等，[2022] Micikevicius, P., Stosic, D., Burgess, N., Cornea, M., Dubey, P., Grisenthwaite, R., Ha, S., Heinecke, A., Judd, P., Kamalu, J. 等. (2022). Fp8 格式用于深度学习。arXiv 预印本 arXiv:2209.05433。

+   Modarressi 等，[2023] Modarressi, A., Imani, A., Fayyaz, M., 和 Schütze, H. (2023). Ret-llm: 面向大型语言模型的通用读写记忆。

+   ModelTC，[2024] ModelTC (2024). Lightllm: 基于 Python 的 llm 推理和服务框架。 [`github.com/ModelTC/lightllm`](https://github.com/ModelTC/lightllm)。

+   Mohtashami 和 Jaggi，[2023] Mohtashami, A. 和 Jaggi, M. (2023). 地标注意力：用于变换器的随机访问无限上下文长度。arXiv 预印本 arXiv:2305.16300。

+   Monea 等，[2023] Monea, G., Joulin, A., 和 Grave, E. (2023). Pass: 并行推测采样。arXiv 预印本 arXiv:2311.13581。

+   Nawrot 等，[2024] Nawrot, P., Łańcucki, A., Chochowski, M., Tarjan, D., 和 Ponti, E. M. (2024). 动态内存压缩：对 llms 的重新适配以加速推理。arXiv 预印本 arXiv:2403.09636。

+   Ning 等，[2023] Ning, X., Lin, Z., Zhou, Z., Wang, Z., Yang, H., 和 Wang, Y. (2023). 思维框架：大型语言模型可以进行并行解码。

+   NVIDIA，[2022] NVIDIA (2022). NVIDIA Hopper 架构内部介绍。 [`www.nvidia.com/en-us/data-center/technologies/hopper-architecture/`](https://www.nvidia.com/en-us/data-center/technologies/hopper-architecture/)。访问于 2024 年 3 月 11 日。

+   Ortega 和 Rheinboldt，[2000] Ortega, J. M. 和 Rheinboldt, W. C. (2000). 多变量非线性方程的迭代解法。SIAM。

+   Oseledets，[2011] Oseledets, I. V. (2011). 张量-训练分解。SIAM 科学计算杂志, 33(5):2295–2317。

+   Ouyang 等，[2022] Ouyang, L., Wu, J., Jiang, X., Almeida, D., Wainwright, C., Mishkin, P., Zhang, C., Agarwal, S., Slama, K., Ray, A. 等. (2022). 通过人类反馈训练语言模型以遵循指令。神经信息处理系统进展, 35:27730–27744。

+   Pal 等，[2023] Pal, A., Karkhanis, D., Roberts, M., Dooley, S., Sundararajan, A., 和 Naidu, S. (2023). Giraffe: 扩展 llms 上下文长度的冒险。

+   Pandya 和 Holia，[2023] Pandya, K. 和 Holia, M. (2023). 使用 langchain 自动化客户服务：为组织构建自定义开源 GPT 聊天机器人。arXiv 预印本 arXiv:2310.05421。

+   Park 等，[2018] Park, E. 等. (2018). 基于异常值感知低精度计算的节能神经网络加速器。在 ISCA 会议上，第 688–698 页。IEEE。

+   Park 等，[2023] Park, G., Park, B., Kim, M., Lee, S., Kim, J., Kwon, B., Kwon, S. J., Kim, B., Lee, Y., 和 Lee, D. (2023). Lut-gemm: 基于 luts 的量化矩阵乘法，用于大规模生成语言模型中的高效推理。arXiv 预印本 arXiv:2206.09557。

+   Peng 等人，[2023] Peng, B., Quesnelle, J., Fan, H., 和 Shippole, E. (2023). Yarn: 大型语言模型的高效上下文窗口扩展。

+   Press 等人，[2021] Press, O., Smith, N. A., 和 Lewis, M. (2021). 短期训练，长期测试：带有线性偏差的注意力机制实现输入长度外推。arXiv 预印本 arXiv:2108.12409。

+   Qin 等人，[2023] Qin, Y., Wang, Y., Deng, D., Zhao, Z., Yang, X., Liu, L., Wei, S., Hu, Y., 和 Yin, S. (2023). Fact: FFN-注意力共同优化的变压器架构与急切相关预测。发表于第 50 届年度国际计算机架构研讨会，页码 1–14。

+   Rae 等人，[2019] Rae, J. W., Potapenko, A., Jayakumar, S. M., 和 Lillicrap, T. P. (2019). 压缩变压器用于长程序列建模。

+   Rajbhandari 等人，[2022] Rajbhandari, S., Li, C., Yao, Z., Zhang, M., Aminabadi, R. Y., Awan, A. A., Rasley, J., 和 He, Y. (2022). Deepspeed-moe: 促进专家混合推理和训练以支持下一代 AI 规模。发表于国际机器学习会议，页码 18332–18346。PMLR。

+   Rotem 等人，[2023] Rotem, D., Hassid, M., Mamou, J., 和 Schwartz, R. (2023). 寻找甜蜜点：在低资源环境中分析和改进自适应推理。

+   Sahu 等人，[2023] Sahu, G., Vechtomova, O., Bahdanau, D., 和 Laradji, I. H. (2023). Promptmix: 一种用于大型语言模型蒸馏的类别边界增强方法。arXiv 预印本 arXiv:2310.14192。

+   Santilli 等人，[2023] Santilli, A., Severino, S., Postolache, E., Maiorca, V., Mancusi, M., Marin, R., 和 Rodolà, E. (2023). 通过并行解码加速翻译中的变压器推理。arXiv 预印本 arXiv:2305.10427。

+   Savinov 等人，[2021] Savinov, N., Chung, J., Binkowski, M., Elsen, E., 和 Oord, A. v. d. (2021). 用于文本生成的步骤展开去噪自编码器。arXiv 预印本 arXiv:2112.06749。

+   Scao 等人，[2022] Scao, T. L., Fan, A., Akiki, C., Pavlick, E., Ilić, S., Hesslow, D., Castagné, R., Luccioni, A. S., Yvon, F., Gallé, M., 等人. (2022). Bloom: 一个 176b-参数的开放访问多语言模型。arXiv 预印本 arXiv:2211.05100。

+   Schotthöfer 等人，[2022] Schotthöfer, S., Zangrando, E., Kusch, J., Ceruti, G., 和 Tudisco, F. (2022). 低秩彩票：通过矩阵微分方程寻找高效低秩神经网络。神经信息处理系统进展，35:20051–20063。

+   Schuster 等人，[2022] Schuster, T., Fisch, A., Gupta, J., Dehghani, M., Bahri, D., Tran, V. Q., Tay, Y., 和 Metzler, D. (2022). 自信自适应语言建模。

+   Schuster 等人，[2021] Schuster, T., Fisch, A., Jaakkola, T., 和 Barzilay, R. (2021). 通过自信自适应变压器实现一致的加速推理。

+   Schwartz 等，[2020] Schwartz, R., Stanovsky, G., Swayamdipta, S., Dodge, J., 和 Smith, N. A. (2020). 适合工作的工具：模型与实例复杂度匹配。见 Jurafsky, D., Chai, J., Schluter, N., 和 Tetreault, J. 主编，《第 58 届计算语言学协会年会论文集》，页 6640–6651，在线。计算语言学协会。

+   Shang 等，[2021] Shang, Y., Duan, B., Zong, Z., Nie, L., 和 Yan, Y. (2021). 利普希茨连续性引导的知识蒸馏。见《IEEE/CVF 国际计算机视觉会议论文集》，页 10675–10684。

+   Shang 等，[2024] Shang, Y., Yuan, Z., 和 Dong, Z. (2024). Pb-llm：部分二值化的大型语言模型。见 ICLR。

+   Shao 等，[2020] Shao, C., Zhang, J., Feng, Y., Meng, F., 和 Zhou, J. (2020). 最小化非自回归神经机器翻译的 bag-of-ngrams 差异。见《AAAI 人工智能会议论文集》，第 34 卷，页 198–205。

+   Sharma 等，[2023] Sharma, P., Ash, J. T., 和 Misra, D. (2023). 真相在其中：通过层选择性秩降低改善语言模型的推理能力。arXiv 预印本 arXiv:2312.13558。

+   Sheng 等，[2023] Sheng, Y., Zheng, L., Yuan, B., Li, Z., Ryabinin, M., Chen, B., Liang, P., Ré, C., Stoica, I., 和 Zhang, C. (2023). Flexgen：使用单个 GPU 高通量生成推理大型语言模型。见 Krause, A., Brunskill, E., Cho, K., Engelhardt, B., Sabato, S., 和 Scarlett, J. 主编，《国际机器学习大会论文集》，ICML 2023，2023 年 7 月 23-29 日，美国夏威夷檀香山，第 202 卷，机器学习研究论文集，页 31094–31116。PMLR。

+   Simoulin 和 Crabbé，[2021] Simoulin, A. 和 Crabbé, B. (2021). 多少层及其原因？对变换器模型深度的分析。见 Kabbara, J., Lin, H., Paullada, A., 和 Vamvas, J. 主编，《第 59 届计算语言学协会年会暨第 11 届国际自然语言处理联合会议：学生研究研讨会论文集》，页 221–228，在线。计算语言学协会。

+   Song 等，[2021] Song, Y., Meng, C., Liao, R., 和 Ermon, S. (2021). 通过并行非线性方程求解加速前向计算。见 Meila, M. 和 Zhang, T. 主编，《第 38 届国际机器学习大会论文集》，第 139 卷，机器学习研究论文集，页 9791–9800。PMLR。

+   Song 等，[2023] Song, Y., Mi, Z., Xie, H., 和 Chen, H. (2023). Powerinfer：使用消费者级 GPU 快速提供大型语言模型服务。

+   Stern 等，[2018] Stern, M., Shazeer, N., 和 Uszkoreit, J. (2018). 深度自回归模型的块级并行解码。神经信息处理系统进展，31。

+   Stickland 和 Murray，[2019] Stickland, A. C. 和 Murray, I. (2019). Bert 和伙伴：用于多任务学习的高效适应的投影注意力层。

+   [187] Sun, M., Liu, Z., Bair, A., 和 Kolter, J. Z. (2023a). 一种简单有效的大型语言模型剪枝方法。arXiv 预印本 arXiv:2306.11695。

+   [188] Sun, X., Choi, J., Chen, C.-Y., Wang, N., Venkataramani, S., Srinivasan, V. V., Cui, X., Zhang, W., 和 Gopalakrishnan, K. (2019a). 混合 8 位浮点 (hfp8) 深度神经网络的训练和推理。神经信息处理系统进展，32。

+   Sun 等人，[2022] Sun, Y., Dong, L., Patra, B., Ma, S., Huang, S., Benhaim, A., Chaudhary, V., Song, X., 和 Wei, F. (2022). 一种长度可外推的变换器。

+   [190] Sun, Z., Li, Z., Wang, H., He, D., Lin, Z., 和 Deng, Z. (2019b). 序列模型的快速结构化解码。神经信息处理系统进展，32。

+   [191] Sun, Z., Suresh, A. T., Ro, J. H., Beirami, A., Jain, H., 和 Yu, F. (2023b). Spectr: 通过最优传输实现快速推测解码。arXiv 预印本 arXiv:2310.15141。

+   Sundar Pichai，[2024] Sundar Pichai, D. H. (2024). 我们的下一代模型：Gemini 1.5。

+   Tambe 等人，[2020] Tambe, T., Yang, E.-Y., Wan, Z., Deng, Y., Reddi, V. J., Rush, A., Brooks, D., 和 Wei, G.-Y. (2020). 适应性浮点编码的算法-硬件协同设计，用于鲁棒深度学习推理。在 2020 年第 57 届 ACM/IEEE 设计自动化会议 (DAC)，第 1–6 页。IEEE。

+   Team 等人，[2023] Team, G., Anil, R., Borgeaud, S., Wu, Y., Alayrac, J.-B., Yu, J., Soricut, R., Schalkwyk, J., Dai, A. M., Hauth, A., 等 (2023). Gemini: 一类高能力的多模态模型。arXiv 预印本 arXiv:2312.11805。

+   Tesla，[2023] Tesla (2023). Tesla dojo 技术：特斯拉可配置浮点格式与运算指南。 [`cdn.motor1.com/pdf-files/535242876-tesla-dojo-technology.pdf/`](https://cdn.motor1.com/pdf-files/535242876-tesla-dojo-technology.pdf/)。

+   [196] Touvron, H., Lavril, T., Izacard, G., Martinet, X., Lachaux, M.-A., Lacroix, T., Rozière, B., Goyal, N., Hambro, E., Azhar, F., 等 (2023a). Llama: 开放和高效的基础语言模型。arXiv 预印本 arXiv:2302.13971。

+   [197] Touvron, H., Martin, L., Stone, K., Albert, P., Almahairi, A., Babaei, Y., Bashlykov, N., Batra, S., Bhargava, P., Bhosale, S., 等 (2023b). Llama 2: 开放的基础模型和微调的聊天模型。arXiv 预印本 arXiv:2307.09288。

+   Vaidya 等人，[2023] Vaidya, N., Oh, F., 和 Comly, N. (2023). 使用 NVIDIA TensorRT-LLM 对大型语言模型进行优化，现在已公开提供。

+   Valipour 等人，[2022] Valipour, M., Rezagholizadeh, M., Kobyzev, I., 和 Ghodsi, A. (2022). Dylora: 使用动态无搜索低秩适应进行预训练模型的参数高效调优。arXiv 预印本 arXiv:2210.07558。

+   Wang 等人，[2023] Wang, P., Wang, Z., Li, Z., Gao, Y., Yin, B., 和 Ren, X. (2023). Scott: 自一致链式思维蒸馏。arXiv 预印本 arXiv:2305.01879。

+   [201] 王伟, 陈伟, 罗阳, 龙艳, 林中, 张磊, 林斌, 蔡栋, 何晓. (2024a). 大型语言模型的模型压缩与高效推理: 综述. arXiv 预印本 arXiv:2402.09748.

+   [202] 王伟, 董磊, 程浩, 刘晓, 阎鑫, 高佳, 韦飞. (2024b). 增强语言模型的长期记忆. 神经信息处理系统进展, 36.

+   王勇, 田峰, 何东, 秦涛, 翟晨, 刘腾跃. (2019). 辅助正则化的非自回归机器翻译. 在人工智能 AAAI 会议论文集中, 第 33 卷, 页 5377–5384.

+   韦博, 王明, 周浩, 林骞, 谢佳, 孙晓. (2019). 用于非自回归神经机器翻译的模仿学习. arXiv 预印本 arXiv:1906.02041.

+   韦洪, 孔磊, 陈俊, 赵磊, 葛震, 余恩, 孙杰, 韩成, 张轩. (2024). 小型语言模型与强化视觉词汇相遇. arXiv 预印本 arXiv:2401.12503.

+   [206] 吴敏, 瓦希德, 张楚, 阿卜杜勒-马吉德, 阿吉. (2023a). Lamini-lm: 来自大规模指令的多样化蒸馏模型. arXiv 预印本 arXiv:2304.14402.

+   吴青, 蓝志, 钱凯, 顾骏, 盖拉米法尔德, 余中. (2020). Memformer: 一种用于序列建模的记忆增强型变换器. arXiv 预印本 arXiv:2010.06891.

+   [208] 吴世光, 陈赫, 全晓, 王强, 王睿. (2023b). Ad-kd: 基于归因驱动的知识蒸馏用于语言模型压缩. arXiv 预印本 arXiv:2305.10010.

+   [209] 吴晓, 夏华, 尹思, 郑志, 陈思, 巴赫提亚里, 怀亚特, 何杨, 鲁瓦斯, 宋亮, 等. (2023c). Zeroquant (4+ 2): 用于多样生成任务的新型 fp6 中心策略重新定义 llms 量化. arXiv 预印本 arXiv:2312.08583.

+   [210] 吴晓, 姚志, 何杨. (2023d). Zeroquant-fp: 使用浮点格式在 llms 后训练 w4a8 量化中的跃进. arXiv 预印本 arXiv:2307.09782.

+   吴玉, 拉贝, 邓迪, 斯泽格迪. (2022). 记忆变换器. arXiv 预印本 arXiv:2203.08913.

+   [212] 夏华, 郑志, 李洋, 庄迪, 周志, 邱星, 李洋, 林伟, 宋世龙. (2023a). Flash-llm: 通过非结构化稀疏性实现成本效益高且高效的大规模生成模型推理. arXiv 预印本 arXiv:2309.10285.

+   夏华, 郑志, 吴晓, 陈思, 姚志, 尹思, 巴赫提亚里, 怀亚特, 庄迪, 周志, 等. (2024). Fp6-llm: 通过 fp6 中心算法-系统共设计高效服务大规模语言模型. arXiv 预印本 arXiv:2401.14112.

+   [214] 夏敏, 高天, 曾志, 陈东. (2023b). Sheared llama: 通过结构化剪枝加速语言模型预训练. arXiv 预印本 arXiv:2310.06694.

+   [215] Xiao, G., Lin, J., Seznec, M., Wu, H., Demouth, J., 和 Han, S. (2023a). Smoothquant: 对大语言模型的准确且高效的后训练量化。在国际机器学习会议，页面 38087–38099\. PMLR。

+   [216] Xiao, G., Tian, Y., Chen, B., Han, S., 和 Lewis, M. (2023b). 高效的流式语言模型与注意力沉降。arXiv 预印本 arXiv:2309.17453。

+   [217] Xiao, Y., Wu, L., Guo, J., Li, J., Zhang, M., Qin, T., 和 Liu, T.-y. (2023c). 关于神经机器翻译及其扩展的非自回归生成综述。IEEE 模式分析与机器智能汇刊。

+   Xin 等人，[2020] Xin, J., Tang, R., Lee, J., Yu, Y., 和 Lin, J. (2020). Deebert: 动态早期退出以加速 BERT 推理。

+   Xiong 等人，[2023] Xiong, W., Liu, J., Molybog, I., Zhang, H., Bhargava, P., Hou, R., Martin, L., Rungta, R., Sankararaman, K. A., Oguz, B., Khabsa, M., Fang, H., Mehdad, Y., Narang, S., Malik, K., Fan, A., Bhosale, S., Edunov, S., Lewis, M., Wang, S., 和 Ma, H. (2023). 基础模型的有效长上下文扩展。

+   [220] Xu, D., Yin, W., Jin, X., Zhang, Y., Wei, S., Xu, M., 和 Liu, X. (2023a). Llmcad: 快速且可扩展的设备端大语言模型推理。arXiv 预印本 arXiv:2309.04255。

+   [221] Xu, M., Xu, Y. L., 和 Mandic, D. P. (2023b). Tensorgpt: 基于张量分解的大语言模型嵌入层的高效压缩。arXiv 预印本 arXiv:2307.00526。

+   Xu 等人，[2024] Xu, X., Li, M., Tao, C., Shen, T., Cheng, R., Li, J., Xu, C., Tao, D., 和 Zhou, T. (2024). 大语言模型知识蒸馏综述。

+   [223] Xu, Y., Xie, L., Gu, X., Chen, X., Chang, H., Zhang, H., Chen, Z., Zhang, X., 和 Tian, Q. (2023c). Qa-lora: 对大语言模型的量化感知低秩适应。arXiv 预印本 arXiv:2309.14717。

+   Yang 等人，[2023] Yang, N., Ge, T., Wang, L., Jiao, B., Jiang, D., Yang, L., Majumder, R., 和 Wei, F. (2023). 参考推理：大语言模型的无损加速。arXiv 预印本 arXiv:2304.04487。

+   Yao 等人，[2022] Yao, Z., Yazdani Aminabadi, R., Zhang, M., Wu, X., Li, C., 和 He, Y. (2022). Zeroquant: 大规模变换器的高效且经济的后训练量化。神经信息处理系统进展，35:27168–27183。

+   Yi 等人，[2023] Yi, R., Guo, L., Wei, S., Zhou, A., Wang, S., 和 Xu, M. (2023). Edgemoe: 快速的基于 Moe 的大语言模型设备端推理。arXiv 预印本 arXiv:2308.14352。

+   [227] Yin, L., Wu, Y., Zhang, Z., Hsieh, C.-Y., Wang, Y., Jia, Y., Pechenizkiy, M., Liang, Y., Wang, Z., 和 Liu, S. (2023a). 异常加权逐层稀疏 (OWL)：对大语言模型进行高稀疏修剪的缺失秘密成分。arXiv 预印本 arXiv:2310.05175。

+   [228] Yin, S., Fu, C., Zhao, S., Li, K., Sun, X., Xu, T., 和 Chen, E. (2023b). 多模态大语言模型综述。arXiv 预印本 arXiv:2306.13549。

+   余光义，郑敬，金国伟，金帅，和春博（2022）。Orca：用于$\{$基于 Transformer$\}$生成模型的分布式服务系统。在第 16 届 USENIX 操作系统设计与实现研讨会（OSDI 22），页码 521–538。

+   [230] 袁泽，李志，孙雷（2023a）。Tinygpt-v：通过小骨干的高效多模态大语言模型。arXiv 预印本 arXiv:2312.16862。

+   [231] 袁泽，刘晶，吴俊，杨达，吴强，孙刚，刘伟，王晓，吴博（2023b）。后训练量化的可靠性基准测试：特别关注最坏情况性能。arXiv 预印本 arXiv:2303.13003。

+   [232] 袁泽，牛磊，刘晶，刘伟，王晓，商颖，孙刚，吴强，吴俊，吴博（2023c）。Rptq：基于重新排序的后训练量化，用于大语言模型。arXiv 预印本 arXiv:2304.01089。

+   [233] 袁泽，商颖，宋宇，吴强，阎宇，孙刚（2023d）。Asvd：激活感知的奇异值分解，用于压缩大语言模型。arXiv 预印本 arXiv:2312.05821。

+   岳洋，袁泽，段穆，周晟，吴俊，聂琳（2024）。Wkvquant：量化大语言模型的权重和键/值缓存以获得更多。arXiv 预印本 arXiv:2402.12065。

+   尤克塞尔等，[2012] 尤克塞尔，S. E.，威尔逊，J. N.，和盖德，P. D.（2012）。专家混合的二十年。IEEE 神经网络与学习系统学报，23(8)：1177–1193。

+   Zadeh 等，[2020] Zadeh，A. H. 等（2020）。Gobo：量化基于注意力的 NLP 模型以实现低延迟和节能推理。在 MICRO，页码 811–824。IEEE。

+   曾书华等，[2024] 曾书华，刘俊，戴光，杨鑫，傅婷，王辉，马文，孙赫，李盛，黄志等（2024）。Flightllm：在 FPGA 上进行完整映射流的高效大语言模型推理。arXiv 预印本 arXiv:2401.03868。

+   曾智勇等，[2023] 曾智勇，洪阳，戴辉，庄宏，陈超（2023）。Consistentee：一种一致性和硬度引导的早期退出方法，用于加速语言模型推理。

+   [239] 张大，余洋，李聪，董俊，苏东，褚超，余东。（2024a）。Mm-llms：多模态大语言模型的最新进展。arXiv 预印本 arXiv:2401.13601。

+   张杰，王佳，李辉，寿亮，陈凯，陈刚，和梅赫罗特拉（2023）。Draft & verify：通过自我推测解码实现无损大语言模型加速。arXiv 预印本 arXiv:2309.08168。

+   张韶，罗勒，戈亚尔，阿尔特克斯，陈敏，陈实，德万，迪亚布，李轩，林欣·V. 等（2022）。Opt：开放预训练的变换器语言模型。arXiv 预印本 arXiv:2205.01068。

+   [242] 张卓，盛勇，周涛，陈婷，郑磊，蔡睿，宋振，田野，Ré，C.，Barrett，C. 等（2024b）。H2o：用于大语言模型高效生成推理的重击者神谕。神经信息处理系统进展，36。

+   Zhao 等，[2024] Zhao, P., Zhang, H., Yu, Q., Wang, Z., Geng, Y., Fu, F., Yang, L., Zhang, W., 和 Cui, B. (2024)。检索增强生成用于 AI 生成内容：综述。arXiv 预印本 arXiv:2402.19473。

+   Zhao 等，[2023] Zhao, W. X., Zhou, K., Li, J., Tang, T., Wang, X., Hou, Y., Min, Y., Zhang, B., Zhang, J., Dong, Z., 等 (2023)。大型语言模型综述。arXiv 预印本 arXiv:2303.18223。

+   Zhong 等，[2023] Zhong, W., Guo, L., Gao, Q., 和 Wang, Y. (2023)。Memorybank: 通过长期记忆增强大型语言模型。arXiv 预印本 arXiv:2305.10250。

+   Zhou 等，[2024] Zhou, B., Hu, Y., Weng, X., Jia, J., Luo, J., Liu, X., Wu, J., 和 Huang, L. (2024)。Tinyllava: 小规模大型多模态模型的框架。arXiv 预印本 arXiv:2402.14289。

+   [247] Zhou, J., Wu, J., Gao, Y., Ding, Y., Tao, C., Li, B., Tu, F., Cheng, K.-T., So, H. K.-H., 和 Wong, N. (2023a)。Dybit: 动态位精度数字用于高效的量化神经网络推理。arXiv 预印本 arXiv:2302.12510。

+   [248] Zhou, W., Jiang, Y. E., Cui, P., Wang, T., Xiao, Z., Hou, Y., Cotterell, R., 和 Sachan, M. (2023b)。Recurrentgpt: 互动生成（任意长度）文本。arXiv 预印本 arXiv:2305.13304。

+   Zhou 等，[2020] Zhou, W., Xu, C., Ge, T., McAuley, J., Xu, K., 和 Wei, F. (2020)。Bert 失去耐心：利用早期退出实现快速和鲁棒的推理。

+   [250] Zhou, Y., Lyu, K., Rawat, A. S., Menon, A. K., Rostamizadeh, A., Kumar, S., Kagy, J.-F., 和 Agarwal, R. (2023c)。Distillspec: 通过知识蒸馏改进推测解码。arXiv 预印本 arXiv:2310.08461。

+   [251] Zhou, Z., Li, C., Yang, F., 和 Suny, G. (2023d)。Dimm-link: 实现高效的内存间通信用于近存处理。在 2023 IEEE 高性能计算架构国际研讨会 (HPCA)，页 302–316。IEEE。

+   Zhu，[2021] Zhu, W. (2021)。LeeBERT: 通过跨层优化学习的 BERT 早期退出。在 Zong, C., Xia, F., Li, W., 和 Navigli, R. 编辑的《第 59 届计算语言学协会年会及第 11 届国际自然语言处理联合会议论文集 (第 1 卷：长论文)》，页 2968–2980，在线。计算语言学协会。

+   Zhu 等，[2023] Zhu, X., Li, J., Liu, Y., Ma, C., 和 Wang, W. (2023)。大型语言模型的模型压缩综述。arXiv 预印本 arXiv:2308.07633。

+   Zhu 等，[2024] Zhu, Y., Zhu, M., Liu, N., Ou, Z., Mou, X., 和 Tang, J. (2024)。Llava-phi: 使用小型语言模型的高效多模态助手。arXiv 预印本 arXiv:2401.02330。

+   Zoph 等，[2022] Zoph, B., Bello, I., Kumar, S., Du, N., Huang, Y., Dean, J., Shazeer, N., 和 Fedus, W. (2022)。St-moe: 设计稳定和可转移的稀疏专家模型。arXiv 预印本 arXiv:2202.08906。

生成于 2024 年 5 月 1 日星期三 20:44:38，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
