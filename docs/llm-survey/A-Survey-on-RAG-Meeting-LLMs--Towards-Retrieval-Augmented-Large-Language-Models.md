<!--yml

category: 未分类

date: 2024-09-03 17:29:38

-->

# 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型

> 来源：[`arxiv.org/html/2405.06211`](https://arxiv.org/html/2405.06211)

1.  [1 介绍](https://arxiv.org/html/2405.06211v3#S1 "在 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

1.  [2 背景](https://arxiv.org/html/2405.06211v3#S2 "在 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

    1.  [2.1 大语言模型（LLMs）](https://arxiv.org/html/2405.06211v3#S2.SS1 "在 2\. 背景 ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

    1.  [2.2 提示学习](https://arxiv.org/html/2405.06211v3#S2.SS2 "在 2\. 背景 ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

        1.  [2.2.1 提示工程](https://arxiv.org/html/2405.06211v3#S2.SS2.SSS1 "在 2.2\. 提示学习 ‣ 2\. 背景 ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

        1.  [2.2.2 上下文学习（ICL）](https://arxiv.org/html/2405.06211v3#S2.SS2.SSS2 "在 2.2\. 提示学习 ‣ 2\. 背景 ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

1.  [3 检索增强型大语言模型（RA-LLMs）](https://arxiv.org/html/2405.06211v3#S3 "在 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

    1.  [3.1 检索](https://arxiv.org/html/2405.06211v3#S3.SS1 "在 3\. 检索增强型大语言模型（RA-LLMs） ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

        1.  [3.1.1 检索器类型](https://arxiv.org/html/2405.06211v3#S3.SS1.SSS1 "在 3.1\. 检索 ‣ 3\. 检索增强型大语言模型（RA-LLMs） ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

        1.  [3.1.2 检索粒度](https://arxiv.org/html/2405.06211v3#S3.SS1.SSS2 "在 3.1\. 检索 ‣ 3\. 检索增强型大语言模型（RA-LLMs） ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

        1.  [3.1.3 检索前和检索后增强](https://arxiv.org/html/2405.06211v3#S3.SS1.SSS3 "在 3.1\. 检索 ‣ 3\. 检索增强型大语言模型（RA-LLMs） ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

        1.  [3.1.4 数据库](https://arxiv.org/html/2405.06211v3#S3.SS1.SSS4 "在 3.1\. 检索 ‣ 3\. 检索增强型大语言模型（RA-LLMs） ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

    1.  [3.2 生成](https://arxiv.org/html/2405.06211v3#S3.SS2 "在 3\. 检索增强型大语言模型（RA-LLMs） ‣ 关于 RAG 会议 LLMs 的调查：走向检索增强型大语言模型")

        1.  [3.2.1 参数可访问的生成器（白箱）](https://arxiv.org/html/2405.06211v3#S3.SS2.SSS1 "在 3.2\. 生成 ‣ 3\. 检索增强的大型语言模型（RA-LLMs） ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

        1.  [3.2.2 参数不可访问的生成器（黑箱）](https://arxiv.org/html/2405.06211v3#S3.SS2.SSS2 "在 3.2\. 生成 ‣ 3\. 检索增强的大型语言模型（RA-LLMs） ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

    1.  [3.3 生成增强的检索整合](https://arxiv.org/html/2405.06211v3#S3.SS3 "在 3\. 检索增强的大型语言模型（RA-LLMs） ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

        1.  [3.3.1 输入层整合](https://arxiv.org/html/2405.06211v3#S3.SS3.SSS1 "在 3.3\. 生成增强的检索整合 ‣ 3\. 检索增强的大型语言模型（RA-LLMs） ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

        1.  [3.3.2 输出层整合](https://arxiv.org/html/2405.06211v3#S3.SS3.SSS2 "在 3.3\. 生成增强的检索整合 ‣ 3\. 检索增强的大型语言模型（RA-LLMs） ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

        1.  [3.3.3 中间层整合](https://arxiv.org/html/2405.06211v3#S3.SS3.SSS3 "在 3.3\. 生成增强的检索整合 ‣ 3\. 检索增强的大型语言模型（RA-LLMs） ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

    1.  [3.4 检索增强的必要性和频率](https://arxiv.org/html/2405.06211v3#S3.SS4 "在 3\. 检索增强的大型语言模型（RA-LLMs） ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

1.  [4 RA-LLMs 训练](https://arxiv.org/html/2405.06211v3#S4 "在 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

    1.  [4.1 无需训练](https://arxiv.org/html/2405.06211v3#S4.SS1 "在 4\. RA-LLMs 训练 ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

        1.  [4.1.1 基于提示工程的方法](https://arxiv.org/html/2405.06211v3#S4.SS1.SSS1 "在 4.1\. 无需训练 ‣ 4\. RA-LLMs 训练 ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

        1.  [4.1.2 检索引导的标记生成方法](https://arxiv.org/html/2405.06211v3#S4.SS1.SSS2 "在 4.1\. 无需训练 ‣ 4\. RA-LLMs 训练 ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

    1.  [4.2 独立训练](https://arxiv.org/html/2405.06211v3#S4.SS2 "在 4\. RA-LLMs 训练 ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

    1.  [4.3 顺序训练](https://arxiv.org/html/2405.06211v3#S4.SS3 "在 4\. RA-LLMs 训练 ‣ 关于 RAG 如何满足 LLMs 的调查：面向检索增强的大型语言模型")

        1.  [4.3.1 先进行检索器训练](https://arxiv.org/html/2405.06211v3#S4.SS3.SSS1 "在 4.3\. 顺序训练 ‣ 4\. RA-LLMs 训练 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [4.3.2 先进行 LLMs 训练](https://arxiv.org/html/2405.06211v3#S4.SS3.SSS2 "在 4.3\. 顺序训练 ‣ 4\. RA-LLMs 训练 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

    1.  [4.4 联合训练](https://arxiv.org/html/2405.06211v3#S4.SS4 "在 4\. RA-LLMs 训练 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

1.  [5 应用](https://arxiv.org/html/2405.06211v3#S5 "在 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

    1.  [5.1 自然语言处理应用](https://arxiv.org/html/2405.06211v3#S5.SS1 "在 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [5.1.1 问答系统](https://arxiv.org/html/2405.06211v3#S5.SS1.SSS1 "在 5.1\. 自然语言处理应用 ‣ 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [5.1.2 聊天机器人](https://arxiv.org/html/2405.06211v3#S5.SS1.SSS2 "在 5.1\. 自然语言处理应用 ‣ 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [5.1.3 事实验证](https://arxiv.org/html/2405.06211v3#S5.SS1.SSS3 "在 5.1\. 自然语言处理应用 ‣ 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

    1.  [5.2 下游任务](https://arxiv.org/html/2405.06211v3#S5.SS2 "在 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [5.2.1 推荐系统](https://arxiv.org/html/2405.06211v3#S5.SS2.SSS1 "在 5.2\. 下游任务 ‣ 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [5.2.2 软件工程](https://arxiv.org/html/2405.06211v3#S5.SS2.SSS2 "在 5.2\. 下游任务 ‣ 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

    1.  [5.3 特定领域应用](https://arxiv.org/html/2405.06211v3#S5.SS3 "在 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [5.3.1 科学中的 AI](https://arxiv.org/html/2405.06211v3#S5.SS3.SSS1 "在 5.3\. 特定领域应用 ‣ 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

        1.  [5.3.2 财务](https://arxiv.org/html/2405.06211v3#S5.SS3.SSS2 "在 5.3\. 特定领域应用 ‣ 5\. 应用 ‣ 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

1.  [6 未来挑战与机遇](https://arxiv.org/html/2405.06211v3#S6 "在 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

1.  [7 结论](https://arxiv.org/html/2405.06211v3#S7 "在 关于 RAG 与 LLMs 的调查：迈向检索增强型大语言模型")

# 关于 RAG 与 LLMs 的调查：迈向检索增强的大型语言模型

Wenqi Fan wenqifan03@gmail.com 香港理工大学，香港特别行政区，Yujuan Ding dingyujuan385@gmail.com 香港理工大学，香港特别行政区，Liangbo Ning BigLemon1123@gmail.com 香港理工大学，香港特别行政区，Shijie Wang shijie.wang@connect.polyu.hk 香港理工大学，香港特别行政区，Hengyun Li neilhengyun.li@polyu.edu.hk 香港理工大学，香港特别行政区，Dawei Yin yindawei@acm.org 百度公司，中国，Tat-Seng Chua dcscts@nus.edu.sg 新加坡国立大学，新加坡，以及 Qing Li csqli@comp.polyu.edu.hk 香港理工大学，香港特别行政区（2024）

###### 摘要。

作为 AI 领域最先进的技术之一，检索增强生成（RAG）可以提供可靠且最新的外部知识，为众多任务提供了极大的便利。尤其在 AI 生成内容（AIGC）时代，检索在提供额外知识方面的强大能力使得 RAG 能够帮助现有的生成型 AI 产生高质量的输出。近期，大型语言模型（LLMs）在语言理解和生成方面展现了革命性的能力，但仍面临固有的局限性，如幻觉和过时的内部知识。鉴于 RAG 在提供最新且有用的辅助信息方面的强大能力，检索增强的大型语言模型（RA-LLMs）应运而生，以利用外部和权威的知识库，而不仅仅依赖于模型的内部知识，以增强 LLMs 的生成质量。在这项调查中，我们全面回顾了 RA-LLMs 的现有研究，涵盖了三种主要技术视角：架构、训练策略和应用。作为初步知识，我们简要介绍了 LLMs 的基础和最新进展。然后，为了说明 RAG 对 LLMs 的实际意义，我们系统地回顾了主流相关工作，包括它们的架构、训练策略和应用领域，具体详细地探讨了每个领域的挑战及 RA-LLMs 的相应能力。最后，为了提供更深刻的见解，我们讨论了当前的局限性以及未来研究的若干有前途的方向。关于这项调查的最新信息可以在[`advanced-recommender-systems.github.io/RAG-Meets-LLMs/`](https://advanced-recommender-systems.github.io/RAG-Meets-LLMs/)找到¹¹1 这是将于 KDD 2024 上出现的长版本（Fan 等，[2024a](https://arxiv.org/html/2405.06211v3#bib.bib34)）。

检索增强生成（RAG）、大型语言模型（LLM）、预训练、微调、上下文学习、提示^†^†版权：acmcopyright^†^†期刊年份：2024

## 1\. 引言

作为最基本的数据挖掘技术之一，检索旨在理解输入查询并从外部数据源中提取相关信息（Kobayashi 和 Takeda，[2000](https://arxiv.org/html/2405.06211v3#bib.bib68)；Singhal 等，[2001](https://arxiv.org/html/2405.06211v3#bib.bib141)；Deng 等，[2024a](https://arxiv.org/html/2405.06211v3#bib.bib25)；Ding 等，[2020b](https://arxiv.org/html/2405.06211v3#bib.bib31)）。它在多个领域得到了广泛应用（Buttcher 等，[2016](https://arxiv.org/html/2405.06211v3#bib.bib9)；Yin 等，[2016](https://arxiv.org/html/2405.06211v3#bib.bib180)；O’Hare 等，[2016](https://arxiv.org/html/2405.06211v3#bib.bib107)；Ding 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib29)），如搜索、问答和推荐系统。例如，搜索引擎（如 Google、Bing 和百度）是检索在工业界最成功的应用；它们可以筛选并检索出与用户查询最相关的网页或文档（Croft 等，[2010](https://arxiv.org/html/2405.06211v3#bib.bib20)；Yin 等，[2016](https://arxiv.org/html/2405.06211v3#bib.bib180)），使用户能够有效地找到所需的信息。同时，检索模型通过在外部数据库中有效维护数据，能够提供真实和及时的外部知识，从而在各种知识密集型任务中发挥重要作用。由于其强大的能力，检索技术已经成功地融入了人工智能生成内容（AIGC）时代的先进生成模型中（Li 等，[2023a](https://arxiv.org/html/2405.06211v3#bib.bib78)；Wu 等，[2024](https://arxiv.org/html/2405.06211v3#bib.bib164)；Sheynin 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib133)）。值得注意的是，检索模型与语言模型的集成产生了检索增强生成（RAG）（Lewis 等，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)），这已经成为生成式人工智能领域最具代表性的技术之一，旨在通过检索到的信息提高生成文本内容的质量（Li 等，[2023a](https://arxiv.org/html/2405.06211v3#bib.bib78)；Lewis 等，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)；Borgeaud 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)）。

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1\. 检索增强生成（RAG）与大型语言模型（LLMs）的结合。当用户的查询超出范围时，例如训练数据中未见过的内容或需要最新信息来回答，LLMs 可能会表现出较差的生成性能。在 RAG 的帮助下，LLMs 可以利用来自外部数据库的额外相关信息来增强其文本生成能力。

为了推动生成模型的发展并提升生成结果，RAG 从外部数据源中整合信息或知识，这些信息或知识作为输入查询或生成输出的补充（Min 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib104)；Khandelwal 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib63)）。具体而言，RAG 首先调用检索器来搜索并提取来自外部数据库的相关文档，然后将这些文档作为上下文来增强生成过程（Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)）。在实践中，RAG 技术的应用可行且高效，只需简单调整检索组件，通常需要的额外训练极少甚至不需要（Ram 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib118)）。近期研究已显示 RAG 在知识密集型任务（如开放域问答（OpenQA））（Borgeaud 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)；Guu 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib47)；Petroni 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib110)；Shi 等，[2024](https://arxiv.org/html/2405.06211v3#bib.bib134)）以及一般语言任务（Khandelwal 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib63)；He 等，[2021a](https://arxiv.org/html/2405.06211v3#bib.bib49)；Xu 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib171)）和各种下游应用（Wu 等，[2024](https://arxiv.org/html/2405.06211v3#bib.bib164)；Liu 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib91)）中展示了巨大的潜力。

近年来，预训练基础模型特别是大型语言模型（LLMs）迅速发展，这些模型在各种任务中表现出色 (Chowdhery et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib19); Achiam et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib2))，包括推荐系统 (Zhao et al., [2024a](https://arxiv.org/html/2405.06211v3#bib.bib196))、分子发现 (Li et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib78)) 和报告生成 (Ding et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib28))。从技术上讲，LLMs 的巨大成功可以归因于具有亿级参数的先进架构，这些模型在来自各种来源的大量训练语料上进行了预训练。这些技术改进促进了 LLMs 显著的涌现能力 (Zhao et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib195), [2024a](https://arxiv.org/html/2405.06211v3#bib.bib196))，尤其是在语言理解和生成、上下文学习等方面。例如，GPT-FAR 通过详细的提示教导 GPT-4 进行图像标记、统计分析和文本分析，以生成多模态时尚报告 (Ding et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib28))。LLMs 在推荐系统中也取得了有前景的成绩，通过理解用户对物品的偏好 (Wang et al., [2024a](https://arxiv.org/html/2405.06211v3#bib.bib155); Zhao et al., [2024a](https://arxiv.org/html/2405.06211v3#bib.bib196))。尽管取得了成功，LLMs 仍然面临固有的局限性 (Zhao et al., [2024a](https://arxiv.org/html/2405.06211v3#bib.bib196), [2023b](https://arxiv.org/html/2405.06211v3#bib.bib195))，例如缺乏领域特定知识、"幻觉"问题以及更新模型所需的大量计算资源。这些问题在医学和法律等领域尤为显著。例如，一项近期研究表明，法律幻觉普遍且令人不安，最先进的 LLMs 在回答特定法律问题时的幻觉率从 69%到 88%不等 (Dahl et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib22))。此外，由于微调 LLMs 以适应领域特定或最新数据所需的巨额计算资源，解决幻觉问题的挑战变得更加困难。这反过来又显著阻碍了 LLMs 在各种现实世界应用中的广泛采用。

为了解决这些局限性，近期的努力已经开始利用 RAG 来增强 LLMs 在各种任务中的能力（Shi et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib136); Khandelwal et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib63); Borgeaud et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib7); Izacard and Grave, [2021a](https://arxiv.org/html/2405.06211v3#bib.bib54)），特别是在对最新和可靠知识要求较高的任务中，如问答（QA）、AI4Science 和软件工程。例如，Lozano et al. ([2023](https://arxiv.org/html/2405.06211v3#bib.bib93)) 介绍了一个基于动态检索科学文献的科学问答系统。MolReGPT 利用 RAG 来增强 ChatGPT 在分子发现中的上下文学习能力（Li et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib78)）。还证明了 RAG 可以有效减少对话任务中的幻觉（Shuster et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib138); Xu et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib172)）。如图[1](https://arxiv.org/html/2405.06211v3#S1.F1 "Figure 1 ‣ 1\. Introduction ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models")所示，基于 LLM 的对话系统对于超出范围的查询无法很好地回答。通过 RAG 从外部数据库检索相关知识并将其整合到生成过程中，这些对话系统成功地给出了正确的答案。鉴于 RAG 在推动 LLMs 方面取得的显著进展，迫切需要对近期在检索增强型大语言模型（RA-LLMs）中的进展进行系统评审。

本调查旨在通过分别总结架构、训练策略和应用领域的代表性方法，提供 RA-LLMs 的全面概述。更具体地说，在第[2](https://arxiv.org/html/2405.06211v3#S2 "2\. Background ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models")节对 LLMs 的背景知识进行简要介绍之后，我们将从检索、生成和增强几个主要角度审视 RA-LLMs 的现有研究，以及 RAG 中检索的必要性和应用频率。在第[3](https://arxiv.org/html/2405.06211v3#S3 "3\. Retrieval-Augmented Large Language Models (RA-LLMs) ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models")节中，我们总结了 RA-LLMs 的主要训练技术，并在第[4](https://arxiv.org/html/2405.06211v3#S4 "4\. RA-LLMs Training ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models")节中介绍了各种 RA-LLMs 的应用，最后在第[5](https://arxiv.org/html/2405.06211v3#S5 "5\. Applications ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models")节中讨论了未来挑战和潜在的探索方向。

与我们的调查同时，几个相关的调查研究针对 RAG 和 LLMs 有着不同的重点。例如，赵等人（[2023a](https://arxiv.org/html/2405.06211v3#bib.bib194)）专门回顾了基于多模态信息的 RAG 技术，赵等人（[2024b](https://arxiv.org/html/2405.06211v3#bib.bib193)）讨论了用于 AIGC 的 RAG。高等人（[2023b](https://arxiv.org/html/2405.06211v3#bib.bib42)）则对 LLMs 的 RAG 进行了相对全面的概述。我们的调查与这些调查的不同之处在于专注于技术视角，并系统性地审视 RA-LLMs 中的模型架构和训练范式，以及应用任务。

## 2\. 背景

在本节中，我们简要介绍了大语言模型和提示学习的背景。

### 2.1\. 大语言模型（LLMs）

最近，LLMs 的重大突破已经彻底改变了人工智能领域 （Zhao et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib195)；Brown et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib8)；Fan et al., [2024b](https://arxiv.org/html/2405.06211v3#bib.bib38)）。先进的 LLMs 通常在大规模数据上进行预训练，拥有十亿级别的参数，并展示了理解和生成类似人类文本的能力，这推动了文本生成和信息检索等各种自然语言处理任务的发展（Zhao et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib195)，[2024a](https://arxiv.org/html/2405.06211v3#bib.bib196)）。LLMs 可以通过在特定数据集上进行微调来适应各种下游任务，从而使它们能够专注于特定领域或应用。一般来说，大多数现有的 LLMs 可以大致分为三类：仅编码器模型、仅解码器模型和编码器-解码器模型。

![参见说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2\. 展示了按主要设计焦点、提出时间和影响（以引用标注）组织的 RAG 和 RA-LLMs 方法。请注意，图中显示的第一作者和年份以及模型名称可以用来查找相应的参考文献。

仅编码器模型，例如 BERT（双向编码器表示模型）（Devlin et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib26)）系列模型，通过将输入文本编码到高维空间来处理文本。仅编码器模型的关键特征是其双向性质，这意味着它们在编码每个标记时可以考虑左右上下文。这种双向性使得仅编码器模型能更好地理解上下文中的词语含义，这对于情感分析、评论阅读和文本分类等任务至关重要（Xu et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib170); Devlin et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib26)）。与这些模型相反，只有解码器的模型以从左到右的方式生成文本。作为代表性的解码器模型，GPT（生成预训练变换器）（Radford et al., [2018](https://arxiv.org/html/2405.06211v3#bib.bib115)）根据前一个标记提供的上下文预测序列中的下一个标记。其架构使它们在语言生成、代码生成和创意写作等任务中表现特别有效。编码-解码模型，例如 T5（文本到文本转换变换器）（Raffel et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib117)），独特地将各种 NLP 任务转化为文本生成问题。具体来说，T5 中的编码器处理输入序列以捕捉其含义，而解码器则根据编码的信息生成输出序列。这种 T5 架构非常适合涉及将一个序列转换为另一个序列的任务，例如机器翻译、摘要生成和对话回应生成。

### 2.2\. 提示学习

#### 2.2.1\. 提示工程

由于 LLM 的巨大参数，提示学习作为一种范式出现，以利用 LLM 的强大功能来实现各种任务（Zhao et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib195), [2024a](https://arxiv.org/html/2405.06211v3#bib.bib196)），而不是对 LLM 进行广泛微调。提示学习精心设计输入，以指导模型在 LLM 中执行下游任务。例如，早期的方法（Petroni et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib111); Brown et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib8)）提供手动制作的模板来处理 NLP 中的各种任务。具体而言，像 BERT 这样的仅编码器模型通常采用填空提示，因为它们与其预训练任务的形式非常匹配（Petroni et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib111); Cui et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib21)）。而对于像 GPT 这样的其他模型，前缀提示往往更为合适，因为它们与生成任务更为契合（Brown et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib8)）。然而，手动设计的提示依赖于人类经验，且没有效果保证。为了解决这一限制，开发了软提示微调技术，以学习可训练的连续提示嵌入（Li and Liang, [2021](https://arxiv.org/html/2405.06211v3#bib.bib84); Vu et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib152); Tu et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib151)）。例如，Prefix-Tuning（Li and Liang, [2021](https://arxiv.org/html/2405.06211v3#bib.bib84)）在输入中添加一系列前缀嵌入，这些嵌入可以被训练和更新。这种方法允许提示不是实际文本，提供了更多生成提示的灵活性。然而，由于缺乏领域特定的知识，模型在面对新任务时可能仍然无法生成准确的响应。

#### 2.2.2\. 上下文学习（ICL）

为克服原始提示学习的局限性，近期的研究（Liu et al., [2022a](https://arxiv.org/html/2405.06211v3#bib.bib90); Kim et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib67); Zhang et al., [2023c](https://arxiv.org/html/2405.06211v3#bib.bib192)）发展了上下文学习（ICL）。ICL 是一种特定的提示学习方法，它在提示中给模型提供几个任务示例。这种范式允许预训练的 LLM 通过示例所提供的模式来理解并解决新任务，而无需微调。例如，通过精心选择几个示例，GPT-3（Brown et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib8)）已显示出执行少量示例任务的能力（Liu et al., [2022a](https://arxiv.org/html/2405.06211v3#bib.bib90)）。这一成功表明，LLMs 具有根据任务特定知识快速适应新任务的显著能力。

尽管效果显著，ICL 通常严重依赖提供的示例的质量（liu2022makes; Su et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib144)），这可能导致生成次优的输出。更糟糕的是，ICL 可能没有足够的必要信息或先验知识来指导 LLMs 生成准确的响应。为了解决 ICL 的上述局限性，近期的研究引入了检索增强生成（RAG）技术（Lewis et al., [2020c](https://arxiv.org/html/2405.06211v3#bib.bib75); Ram et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib118); Shi et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib136)）。通过将检索与生成结合，RAG 模型为提高 LLMs 在各种任务中的性能和适应性提供了一个有前途的方向。

## 3\. 检索增强大语言模型（RA-LLMs）

在 LLMs 时代的 RAG 框架包括几个主要过程：*检索*、*生成* 和 *增强*，以及确定是否需要检索的机制。在本节中，我们将介绍每个过程涉及的重要技术。

![参见说明](img/9df2a699c179d7d103da938773675ba1.png)

图 3\. 针对特定 QA 任务的基础检索增强大语言模型（RA-LLMs）框架示意图，由三个主要组件组成：检索、增强和生成。检索可能具有不同的程序和各种设计，可能包括预检索和后检索过程。检索到的文档在生成过程中进一步利用，与增强模块一起，可能在不同的集成阶段进行。

![参见说明](img/ebb17c4cc7cc9df00a33d741a1bf8410.png)

图 4\. RA-LLMs 中检索器的示意图，它可以以密集或稀疏的方式实现，每种方式都有几个关键操作。

### 3.1\. 检索

给定来自 LLMs 的查询，RAG 中的检索过程旨在从外部知识源中提供相关信息，这些信息可以是开源的或闭源的，如图[3](https://arxiv.org/html/2405.06211v3#S3.F3 "图 3 ‣ 3\. 检索增强的大型语言模型 (RA-LLMs) ‣ 关于 RAG 与 LLMs 会议的调查：朝向检索增强的大型语言模型")所示。关键组件检索器，如图[4](https://arxiv.org/html/2405.06211v3#S3.F4 "图 4 ‣ 3\. 检索增强的大型语言模型 (RA-LLMs) ‣ 关于 RAG 与 LLMs 会议的调查：朝向检索增强的大型语言模型")中详细介绍，由多个程序组成，作为一个整体来衡量查询与数据库中文档的相关性，以实现有效的信息检索。检索的具体流程进一步取决于是否包含检索前和检索后的过程。在本小节中，我们将介绍传统和基于 LLM 的 RAG 检索涉及的主要技术，包括检索器类型、检索粒度、检索前后增强和数据库构建。

#### 3.1.1\. 检索器类型

检索方法通常可以根据信息编码方法分为两种类型：稀疏和密集。稀疏检索是基于词的，主要应用于文本检索，而密集检索将查询和外部知识嵌入向量空间，可以应用于各种数据格式。

作为一种直接的方法，稀疏检索，例如 TF-IDF 和 BM25 (Sparck Jones, [1972](https://arxiv.org/html/2405.06211v3#bib.bib143); Robertson et al., [2009](https://arxiv.org/html/2405.06211v3#bib.bib126))，通常依赖于反向索引匹配以及原始数据输入。例如，许多研究直接应用 BM25 进行段落级检索，以促进它们的 RAG (Chen et al., [2017](https://arxiv.org/html/2405.06211v3#bib.bib11); Ram et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib118); Zhong et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib197); Jiang et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib58); Zhou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib198); Xu et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib169))，其中段落特别表示为词袋，并根据术语和逆文档频率进行排名 (Izacard and Grave, [2021b](https://arxiv.org/html/2405.06211v3#bib.bib55))。除了提供补充以增强生成器的输入，稀疏检索还用于找到在 RA-LLMs (Ye et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib177); Luo et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib97); Rubin et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib127); Agrawal et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib3); Sia and Duh, [2023](https://arxiv.org/html/2405.06211v3#bib.bib139)) 的上下文学习中起作用的示例。应用稀疏检索于 RAG 的主要限制在于其无训练的特性，这使得检索性能严重依赖于数据库和查询的质量。此外，这种基于固定术语的方法仅支持基于相似度的检索，而不能适应 LLM 应用中可能存在的其他检索标准，例如多样性 (Drozdov et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib32))。

相反，密集检索将查询和文档嵌入到具有特定标准的连续向量空间中，例如语义相似性（Karpukhin et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib62)）。密集检索方法通常是可训练的，因此在适应性上具有更多的灵活性和潜力。作为密集检索器的关键组件，嵌入模型在现有的 RAG 模型中设计精巧。一个简单的设计（Khandelwal et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib63); Lewis et al., [2020a](https://arxiv.org/html/2405.06211v3#bib.bib73); Wu et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib166)）是直接使用生成模型的一部分作为检索器的嵌入层，这可能有助于增强检索和生成过程之间的对齐。基于 BERT 的骨干（Devlin et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib26)）广泛应用于检索模型。RAG 中的一个常见检索器设计是构建两个 BERT 结构的双流编码器（一个编码器用于查询，另一个用于文档），这也被称为双编码器（Wu et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib165); Shi et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib136)）。早期阶段的 RAG 方法倾向于冻结（Borgeaud et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib7); Ram et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib118)）或部分冻结（Lewis et al., [2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)）检索器的参数，以执行一般水平的相关知识提取，并更多关注知识利用和生成器微调。大规模专业化预训练进一步增强了 RAG 模型在更多知识密集型任务中的表现。一个典型的成功案例是密集段落检索器（DPR）（Karpukhin et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib62)），它使用基于 BERT 的骨干，并专门为 OpenQA 任务用问答对数据进行预训练。DPR 作为预训练检索器展现了强大的能力，促使许多 RAG 模型在各种下游任务中取得成功（Lewis et al., [2020c](https://arxiv.org/html/2405.06211v3#bib.bib75); Izacard and Grave, [2021b](https://arxiv.org/html/2405.06211v3#bib.bib55); Siriwardhana et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib142); Singh et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib140); Shi et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib136)）。它也被认为是 RAG 范式中改善 LLMs 性能的第一步，这可能通过微调进一步增强查询与相关文本数据之间嵌入的对齐（Cheng et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib17)）。最近的研究（Reichman and Heck, [2024](https://arxiv.org/html/2405.06211v3#bib.bib123)）还发现 DPR 训练使知识在网络中的存储去中心化，创造了多个访问相同信息的途径。通过有效的微调，双编码器检索器也在 ICL 基础的 RAG 中被广泛应用（Rubin et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib127); Poesia et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib112); Lu et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib94); Ye et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib177); Milios et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib102); Li and Qiu, [2023](https://arxiv.org/html/2405.06211v3#bib.bib83)）。具体来说，它们更常用于基于句子嵌入相似性的检索，以及 ICL 中的一些特殊需求，如多样化示例检索（Ye et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib177)）。

另一种广泛应用于 RA-LLMs 的密集检索器使用单一编码器，该编码器可能基于 Transformer、BERT 或其他现成的序列建模骨干。这些单编码器检索器通常通过对比学习（Reichman 和 Heck，[2024](https://arxiv.org/html/2405.06211v3#bib.bib123)）在大规模未对齐文档上进行预训练，因此可能因其通用性而表现优异，这意味着它们可以更好地迁移和泛化到新的领域或任务。这些通用预训练检索器，例如 Contriever（Gautier 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib43)）和 Spider（Ram 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib119)），在面向各种任务的 LLMs 中更具灵活性，并且在许多 RA-LLM 方法中已展示其有效性，如 In-Context RALM（Ram 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib118)）、Atlas（Izacard 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib56)）和 Self-RAG（Asai 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib6)）。根据现有研究的实验结果（Yu 等，[2023a](https://arxiv.org/html/2405.06211v3#bib.bib183)），对于开放领域 QA 任务，当与 InstructGPT（Ouyang 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib108)）配合使用时，应用通用预训练检索器（Contriever）无需微调即可达到与稀疏检索器（BM25）相当的性能。然而，它们都不如在目标数据集上微调的 DPR 模型，显示了在特定任务和数据上微调的有效性。

#### 3.1.2. 检索粒度

检索粒度表示语料库索引中的检索单位，例如文档、段落、标记或其他层次如实体。对于 RAG（检索增强生成），检索粒度的选择会显著影响模型的整体性能，包括效果和效率，因为它们决定了数据库的存储空间以及搜索的计算成本（Asai et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib5)）。早期阶段的检索增强语言模型（Chen et al., [2017](https://arxiv.org/html/2405.06211v3#bib.bib11)）提议检索整篇文档，然后应用训练好的机器理解模型来检测返回文档中的答案范围，这种方法更侧重于语言阅读和文档中的关键信息定位。在生成式语言模型中，Chunk 检索（在一些参考文献中也称为段落（Karpukhin et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib62)；Guu et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib47)；Jiang et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib58)）是常见的，这种方法已在传统和基于 LLM 的 RAG 模型中使用，例如 REALM（Guu et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib47)）、RAG（Lewis et al., [2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)）和 Atlas（Izacard et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib56)）。更细粒度的检索，即标记检索，可以进行更快速的搜索，但会增加数据库的存储负担。标记检索更适用于需要稀有模式或领域外数据的情况（Khandelwal et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib63)），同时与 kNN-LM 及其他类似工作的每标记检索策略配合良好（Yogatama et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib181)；He et al., [2021b](https://arxiv.org/html/2405.06211v3#bib.bib48)；Min et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib105)）。相比之下，文本块可能包含紧凑且完整的信息，冗余和不相关性较少，因此成为 RAG 中的主流检索文本粒度。

RAG 中提出的另一个主要检索粒度是实体检索。与上述类型的粒度不同，实体检索从知识的角度而非语言的角度进行设计。Févry 等人（[2020](https://arxiv.org/html/2405.06211v3#bib.bib40)）引入了实体作为专家（EAE）模型，该模型根据实体身份划分语言模型的参数空间。提出的 EAE 模型旨在从文本中学习实体表示以及其他模型参数，利用维基百科数据库，并通过实体记忆表示知识。在更细粒度的层面上，de Jong 等人（[2022](https://arxiv.org/html/2405.06211v3#bib.bib23)）提出通过学习和检索提及而非实体来构建知识库。总体而言，在 RAG 中应用实体或提及级别的检索对于以实体为中心的任务会更有效，并且相比于逐词检索在空间上更高效。

#### 3.1.3\. 检索前和检索后增强

为了确保检索质量，即提高检索结果的准确性和相关性，已经提出了各种检索前和检索后的策略，以进一步增强检索器的输入和输出。Wang 等人（[2023f](https://arxiv.org/html/2405.06211v3#bib.bib157)）提出了一种查询扩展方法 Query2doc，该方法通过少量示例提示大规模语言模型生成伪文档，并用伪文档中的相关信息扩展查询，以改善查询的歧义消解并指导检索器。他们通过实验证明，这种方法能够提升稀疏和密集检索器的性能（Karpukhin 等人，[2020](https://arxiv.org/html/2405.06211v3#bib.bib62)）在即席信息检索数据集上的表现。类似地，Gao 等人（[2023a](https://arxiv.org/html/2405.06211v3#bib.bib41)）提出了假设文档嵌入（HyDE）方法，该方法指导大规模语言模型为给定查询生成假设文档。然后，假设文档被用作新的查询，进行嵌入并使用密集检索器搜索邻近项。

另一种预检索策略是查询重写 (Ma 等人, [2023a](https://arxiv.org/html/2405.06211v3#bib.bib99))，旨在缩小输入文本和检索所需知识之间的差距，将原始问题重新表述为更有利于检索的版本。具体而言，Ma 等人 ([2023a](https://arxiv.org/html/2405.06211v3#bib.bib99)) 提出了 Rewrite-Retrieve-Read 框架，该框架促使 LLM 生成用于检索功能的查询。重写步骤的动机是明确新查询中的检索需求，以减轻检索功能理解输入和增强输出（即，检索到的相关信息）的负担。他们测试了使用冻结 LLM 和可训练模型作为重写器的设置，两者都优于简单的 RAG 或生成模型，尽管在不同测试的 QA 数据集上表现出不同的性能。Tan 等人 ([2024](https://arxiv.org/html/2405.06211v3#bib.bib147)) 还在他们的模型中制定了一种查询重写策略，该策略将代理生成模型中的启发式答案分解为不同的声明。

Yu 等人 ([2023c](https://arxiv.org/html/2405.06211v3#bib.bib184)) 提出了查询增强的方法，将原始查询和初步生成的输出结合成一个新查询，并进一步用来从外部数据库中检索相关信息。检索到的结果可以激发语言模型重新思考生成的结果并加以改进。与仅使用原始查询相比，这种增强可能会提供更多从语料库中检索的相关信息，以直接澄清查询与输出之间的关系。将初始输出包含在新查询中进一步增强了支持文档与给定问题之间的词汇和语义重叠。查询增强在这些查询增强策略中实现了整体更好的性能，因为它可能在生成答案时集体处理所有检索到的知识 (Wang 等人, [2024c](https://arxiv.org/html/2405.06211v3#bib.bib156))。

后检索增强指的是在将提取的 top-k 文档输入生成器之前，对这些文档进行处理的过程，以便更好地对齐检索和生成阶段（Yang et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib174)），特别是对于如 LLMs 等封闭源生成器。例如，Yang et al. ([2023b](https://arxiv.org/html/2405.06211v3#bib.bib174)) 提出了可插拔奖励驱动上下文适配器（PRCA），它允许在特定数据集上微调轻量级适配器，而不是生成器。它还通过强化学习提取文档，并利用生成器产生的奖励进行精炼。Glass et al. ([2022](https://arxiv.org/html/2405.06211v3#bib.bib45)) 提出了检索-重排序-生成（R²G）方法，该方法通过重排序操作组合不同检索方法的文档，以增强检索结果的鲁棒性。应用后检索增强的另一个考虑因素是，检索到的信息有时可能不相关或包含噪声，这可能对任务生成模型没有帮助，甚至会对生成过程造成更大的损害（Wang et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib160)）。Wang et al. ([2023a](https://arxiv.org/html/2405.06211v3#bib.bib160))、Asai et al. ([2023b](https://arxiv.org/html/2405.06211v3#bib.bib6)) 和 Yu et al. ([2023c](https://arxiv.org/html/2405.06211v3#bib.bib184)) 提出了不同的策略来减轻检索知识文档中的噪声。然而，Xiong et al. ([2023](https://arxiv.org/html/2405.06211v3#bib.bib167)) 通过实证研究发现，这些方法依赖于 LLM 的置信度水平，这可能没有预期的那么精确。为了解决这个问题，Wang et al. ([2024c](https://arxiv.org/html/2405.06211v3#bib.bib156)) 提出了 BlendFilter，该方法同时考虑了预检索查询生成的混合和后检索知识过滤。因此，该方法能够解决复杂问题以及噪声检索知识的问题，从而全面提升 RA-LLM 的性能。

最近，提出了先进的 RAG 流水线，利用 LLM 生成推理路径和计划，并与信息检索 (IR) 模块结合，迭代地检索知识，以增强基于 LLM 的生成 (Yao 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib176); Xu 等, [2023a](https://arxiv.org/html/2405.06211v3#bib.bib173); Shao 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib131))。然而，Zhu 等 ([2023](https://arxiv.org/html/2405.06211v3#bib.bib199)) 指出，如果 IR 和 LLM 的输出质量低，检索和生成过程会相互阻碍，从而影响这种迭代指导流水线。为克服这一障碍，他们提出了一种新的推理方法来增强查询和检索知识。后检索策略也可能有助于提高检索结果与生成模型之间的兼容性。例如，现有 LLM 的主要限制之一是输入令牌的长度，这使得长检索文档无法直接纳入现有 RA-LLMs。针对这一限制，Xu 等 ([2023b](https://arxiv.org/html/2405.06211v3#bib.bib169)) 提出了检索、压缩、前置 (RECOMP)，在生成过程中通过在上下文增强前，将检索到的文档处理为文本摘要来增加一个中间步骤。从另一个角度看，长检索文档列表在生成阶段使用自回归解码时会导致高推理延迟，从而影响模型的效率。针对这一限制，Hofstätter 等 ([2023](https://arxiv.org/html/2405.06211v3#bib.bib51)) 提出了 FiD 模型的轻量版，该版本在将编码向量连接并通过解码器输入之前，先压缩每个检索文档的编码向量，还包括对检索结果的重新排序，然后再将其应用于生成。

| 时间 | 模型 | 引用 | 检索器 | RetTrain | RetAug 阶段 | 前/后检索 | 生成器 | 增强 | 评估 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 2019 | kNN-LM (Khandelwal 等, [2020](https://arxiv.org/html/2405.06211v3#bib.bib63)) | 619 | DR(GP) | 无 | Inf | RA | DT | 输出 | LG |
| 2020 | REALM (Guu 等, [2020](https://arxiv.org/html/2405.06211v3#bib.bib47)) | 1437 | DR(BE,BT) | 是 | PT+FT | / | ET | 输入 | OpenQA(NQ, WQ, CT) |
| 2020 | RAG (Lewis 等, [2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)) | 2125 | DR(DPR) | 是 | FT | / | ED (BART) | 输入 | OpenQA, AQA, Jeopardy QG, FV |
| 2021 | FiD (Izacard 和 Grave, [2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)) | 780 | SR(BM25)/ DR(DPR) | 无 | FT | / | ED (T5/BART) | 输入 | OpenQA |
| 2021 | SE-FiD (Komeili 等, [2022](https://arxiv.org/html/2405.06211v3#bib.bib69)) | 286 | SE(Bing) | 无 | Inf | RQG | FiD | 输入 | WizInt, WoW |
| 2021 | FiD-KD (Izacard 和 Grave, [2021a](https://arxiv.org/html/2405.06211v3#bib.bib54)) | 190 | DR(BE) | 是 | FT | CR | FiD | 输入 | OpenQA |
| 2021 | RETRO (Borgeaud 等, [2022](https://arxiv.org/html/2405.06211v3#bib.bib7)) | 683 | DR(BERT, DPR) | 否 | PT | / | ED | Inter | LM, OpenQA |
| 2021 | EPR (Rubin 等, [2022](https://arxiv.org/html/2405.06211v3#bib.bib127)) | 384 | DR(DPR) | 是 | Inf | CR | GPT-3,J,Neo, CODEX | Demon | UR |
| 2022 | OpenBook (Lazaridou 等, [2022](https://arxiv.org/html/2405.06211v3#bib.bib71)) | 145 | SE+SR | 否 |  | QE | GOPHER LM | Input | QA, FV |
| 2022 | DSP (Khattab 等, [2022](https://arxiv.org/html/2405.06211v3#bib.bib64)) | 117 | ColBERTv2 | 否 | Inf | RQG, RF | GPT-3.5 | Demon | OpenQA, MHQA, CQA |
| 2023 | In-Context RALM (Ram 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib118)) | 211 | DR/SR | 否 | Inf | TRR | GPT-2,J,Neo | Input | LM, OpenQA |
| 2023 | Atlas (Izacard 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib56)) | 367 | DR(OE) | 是 | PT+FT | / | ED | Input | OpenQA, FV, WoW, EL,SF, MMLU |
| 2023 | FLARE (Jiang 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib58)) | 133 | SR(BM25)/ SE(Bing) | 否 | Inf | RQG | GPT-3.5 | Input | MHQA, CR, LongQA, OS |
| 2023 | IRCoT (Trivedi 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib150)) | 114 | SR(BM25) | 否 | Inf | / | GPT-3,Flan-T5 | Input | OpenQA |
| 2023 | Self-RAG (Asai 等, [2023b](https://arxiv.org/html/2405.06211v3#bib.bib6)) | 85 | DR(OE) | 否 | FT | CM | 可调节 LLM |  | OpenQA, LongQA, FV, BG |
| 2023 | REPLUG (Shi 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib136)) | 48 | DR(BE) | 是 | FT | TRA | GPT-2,3 | Input | MMLU, OpenQA |
| 2023 | UDR (Li 等, [2023c](https://arxiv.org/html/2405.06211v3#bib.bib81)) | 42 | DR(DPR) | 是 | FT | CR | GPT-Neo | Demon | 40 NLP 任务 |
| 2023 | ITER-RETGEN (Shao 等, [2023](https://arxiv.org/html/2405.06211v3#bib.bib131)) | 40 | DR(DPR) | 是 | FT | RR | InstructGPT, Llama-2 | Input | MHQA, FV, CR |

表 1\. 高影响力 RAG 和 RA-LLM 模型的基本出版信息和主要技术设计¹

¹¹脚注内容：检索器：[BE: 双编码器（也称为双编码器），OE: 单编码器，BT: BERT 风格的 Transformer，GP: 部分生成，SE: 搜索引擎，SR: 稀疏检索，DPR:(Karpukhin 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib62))]，生成器：[DT: 仅解码器 Transformer，ET: 仅编码器 Transformer，ED: 编码器-解码器]，前/后检索技术：[RQG: 检索查询生成，QE: 查询扩展，（T）RR: （可训练的）重排序器，TRA: 可训练的检索适配器，CR: 候选检索，CM: 评论模型]，增强：[输出: 输出层集成，输入: 输入层集成，中间: 中间层集成，Demon: 示范]，任务：[AQA: 抽象问题回答，QG: 问题生成，NQ: 自然问题，WQ: 网页问题，CT: CuratedTrec，FV: 因素验证，TQA: TriviaQA，WizInt: 网络奇才任务，WoW: 维基百科奇才任务，MHQA: 多跳问答，CQA: 对话问答，EL: 实体链接，SF: 槽填充，MMLU: 大规模多任务语言理解，CR: 常识推理，LongQA: 长篇问答，OS: 开放领域总结，BG: 传记生成，UR: 发言表示，RF: 检索融合]

#### 3.1.4\. 数据库

RAG 中的检索基于外部知识源进行，这些知识源可以是闭源或开源的（Ma 等，[2023a](https://arxiv.org/html/2405.06211v3#bib.bib99); Menick 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib101)），如图[3](https://arxiv.org/html/2405.06211v3#S3.F3 "Figure 3 ‣ 3\. Retrieval-Augmented Large Language Models (RA-LLMs) ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models")所示。闭源数据库通常以键值对形式存储知识，可以通过多种方式构建。键主要用于相似性匹配，如 BM25 中的稀疏向量或从检索编码中得到的密集嵌入。值取决于具体的检索目标，在大多数情况下是原始文本（Guu 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib47); Lewis 等，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75); Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55); Borgeaud 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7); Lewis 等，[2020a](https://arxiv.org/html/2405.06211v3#bib.bib73); Seo 等，[2019](https://arxiv.org/html/2405.06211v3#bib.bib130)）。例如，每篇维基百科文章被拆分成不重叠的 100 字块，总共构成早期 RAG 中的 2100 万文档（Lewis 等，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)）。每个文档由密集嵌入编码，并分别以值和键的形式存储在数据库中。值也可以存储令牌，每个令牌在 kNN-LM（Khandelwal 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib63)）和 SPALM（Yogatama 等，[2021](https://arxiv.org/html/2405.06211v3#bib.bib181)）中应用。数据库的来源取决于具体的应用领域和任务。维基百科是以前 RAG 工作中最常用的一般检索集合之一，它存储了事实结构化信息，并有多个版本，规模从十亿级令牌（Khandelwal 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib63); Yogatama 等，[2021](https://arxiv.org/html/2405.06211v3#bib.bib181); Lewis 等，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75); Guu 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib47); Févry 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib40); de Jong 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib23); Xu 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib169); Shi 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib136); Ram 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib118)）到万亿级令牌（Borgeaud 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)）。领域特定的数据库也用于下游任务。例如，对于代码生成任务，Zan 等（[2022](https://arxiv.org/html/2405.06211v3#bib.bib186)）收集了公共库的 API 信息和代码文件，以构建其 APIretriever 数据库。此外，Zhou 等（Zhou 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib198)）建议在其模型中使用一个经常更新新内容（新发布库）的文档池。

使用互联网搜索引擎（Luo et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib96)），如 Bing 和 Google，可以避免维护搜索索引，并且能够访问最新的知识（Komeili et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib69); Lazaridou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib71)）。与此同时，它提供的知识基础比封闭源数据库（Asai et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib6); Lazaridou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib71)）更为广泛。经过数十年的使用和调整，它还能够提供高质量的排名。互联网搜索已被广泛应用于黑箱 LLMs，并在知识增强（Lazaridou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib71)）、事实核查（Menick et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib101)）和 LLM 代理增强（Yao et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib176)）等不同功能中显示出有效性。与传统的 RAG 相比，由于 LLMs 在理解搜索结果（即检索的文档）和使用工具处理及分析这些结果的非凡能力，互联网搜索在 RA-LLMs 中作为检索器的使用更为广泛（Ma et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib99)）。现有研究（Yu et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib183)）表明，利用搜索引擎（例如，InstrucGPT）对于 LLMs 在零样本知识密集型任务，如 OpenQA 和事实核查中，特别有效。

### 3.2. 生成

生成器的设计很大程度上依赖于下游任务。对于大多数文本生成任务，Decoder-only 和 Encoder-Decoder 是两种主要结构（Zhao et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib195)）。商业封闭源大规模基础模型的最新发展使得黑箱生成模型在 RA-LLMs 中成为主流。在这一部分，我们将简要回顾这两种生成器类型的研究：参数可访问（白箱）和参数不可访问（黑箱）。

#### 3.2.1. 参数可访问生成器（白箱）

*编码器-解码器*的结构独立地使用不同的参数集处理输入和目标，其中开发了一个交叉注意力组件来连接输入标记和目标标记。代表性的编码器-解码器模型包括 T5（Raffel 等人，[2020](https://arxiv.org/html/2405.06211v3#bib.bib117)）和 BART（Lewis 等人，[2020b](https://arxiv.org/html/2405.06211v3#bib.bib74)）。相比之下，*仅解码器模型*在拼接后处理输入和目标，使得两部分的表示逐层构建，同时在网络中传播。这两种生成器类型在现有的 RAG 工作中被广泛应用。例如，RAG（Lewis 等人，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)）和 Re²G（Glass 等人，[2022](https://arxiv.org/html/2405.06211v3#bib.bib45)）采用 BART；FID（Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)）和 EMDR² 使用 T5。还有其他模型（Borgeaud 等人，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)；Li 等人，[2022a](https://arxiv.org/html/2405.06211v3#bib.bib85)）利用基于 Transformer 的编码器-解码器架构，但有一些定制化设计。RAG 中的生成器通过融入检索到的数据来提高生成的准确性和相关性，从而与一般的生成器有所不同。此外，白盒生成器允许参数优化，这可以训练以适应不同的检索和增强方法，从而提高生成的性能。

#### 3.2.2. 无法访问参数的生成器（黑盒）

一定比例的 LLMs 发布时没有透露内部结构或参数的可访问性，特别是那些特别大规模的模型，比如 GPT 系列（Achiam et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib2)）、Codex（Chen et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib13)）和 Claude，这些被称为黑匣子生成模型。这些生成器只允许输入查询（输入）并接收响应（输出），而不允许改变内部结构或更新参数。从另一个角度来看，即使是那些用于微调的 LLMs，由于规模庞大且只有有限的数据量，对于下游领域特定任务的微调也变得困难。因此，黑匣子 RA-LLMs 更多地关注检索和增强过程，试图通过增强输入（在 LLMs 背景中也称为提示）来增强生成器，提供更好的知识、指导或生成示例。例如，Rubin et al. ([2022](https://arxiv.org/html/2405.06211v3#bib.bib127))建议使用语言模型本身标记的数据来训练提示检索器，这可以用于提供更好的上下文学习示例，从而增强最终的生成性能。Xu et al. ([2023b](https://arxiv.org/html/2405.06211v3#bib.bib169))建议在上下文整合之前压缩检索到的文档，这可以减少计算成本，也缓解模型在长文档中识别相关信息的负担。

### 3.3\. 检索整合用于生成增强

增强描述了集成检索和生成部分的技术过程，这是 RA-LLMs 的核心部分。在这一小节中，我们介绍了增强的三个主要设计，分别在生成器的输入、输出和中间层进行，如图[3](https://arxiv.org/html/2405.06211v3#S3.F3 "图 3 ‣ 3\. Retrieval-Augmented Large Language Models (RA-LLMs) ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models")所示。

#### 3.3.1\. 输入层整合

将检索到的信息/文档整合的常见方法是将其与原始输入/查询结合，并共同传递给生成器，这称为输入层整合。例如，In-Context RALM（Ram 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib118)）通过将原始输入和所有检索到的文档串联成一个新的序列作为生成模型的新输入，来应用输入层整合。尽管效果显著，但这种整合受到检索文档数量的限制，因为串联的新输入可能过长，导致生成模型无法处理。In-context RALM 特别通过从新输入的开头移除令牌来缓解这一限制。为了避免这种令牌移除策略带来的信息丢失，FID（Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)）采用了不同的整合方法，该方法在编码器中独立处理每个检索文档。这种策略可以扩展到大量上下文，因为在后续处理过程中只对一个上下文进行自注意力操作。Atlas（Izacard 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib56)）和 REPLUG（Shi 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib136)）通过一次串联查询和一个检索文档的方式应用类似的并行整合。总体而言，大多数基于黑箱生成的 RAG 方法应用输入层整合，因为生成模型的中间层或输出分布是不可访问的。

对于 LLMs 而言，输入层整合可能将检索到的内容作为（额外的）提示或演示，而不仅仅是作为对原始输入的补充，如传统 RAGs（Rubin 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib127)）。提示检索旨在通过检索自动找到合适的自然语言提示，以教会 LLM 在上下文中学习（Brown 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib8)）或促使 LLM 进行推理（Wei 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib163)）。它可能提高 LLMs 的零样本能力，而无需精细的提示工程。例如，Cheng 等（[2023](https://arxiv.org/html/2405.06211v3#bib.bib17)）提出基于输入-提示对数据和冻结 LLM 生成的评分标签来学习一个提示检索器。

#### 3.3.2\. 输出层整合

另一种增强方法是事后整合，即输出层整合，它将检索和生成结果结合起来。例如，kNN-LM (Khandelwal et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib63)) 在预测中插值了两个下一个词分布：一个由语言模型引起，另一个由检索语料库中的最近邻引起。输出层线性整合 (Grave et al., [2017](https://arxiv.org/html/2405.06211v3#bib.bib46); Zhong et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib197)) 应用起来比较灵活，因为它可以插入大多数生成模型中而无需额外训练。然而，输出层整合的简单性也限制了模型对检索文本的推理能力。为了解决这个限制，Yogatama et al. ([2021](https://arxiv.org/html/2405.06211v3#bib.bib181)) 提出了添加一个额外的门控网络来后处理检索数据，从而实现相对更好的性能。对于大型语言模型，输出层整合与输入层整合一样合理和适应。REFEED (Yu et al., [2023c](https://arxiv.org/html/2405.06211v3#bib.bib184)) 提出了一个答案 refining 机制，它应用一个大型语言模型来评估检索的信息并相应调整初始答案，以提高响应的准确性。类似地，Zhang et al. ([2023a](https://arxiv.org/html/2405.06211v3#bib.bib191)) 提出了 COMBO 框架，它基于预训练的判别器将大型语言模型生成的段落与检索到的相应段落匹配成兼容对。然后，由 Fusion-in-Decoder-based (Izacard and Grave, [2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)) 处理这些段落对，以得出最终答案。

#### 3.3.3\. 中间层整合

相比于上述两种非参数方法，一个更具吸引力的增强方式是设计一个半参数模块，通过生成模型的内部层集成检索结果，这被称为中间层集成。这样的集成可能增加额外的复杂性，但有望通过有效的训练提升生成模型的能力。通常，引入一个 Transformer 模块来利用检索到的信息（主要编码成密集表示），与生成过程中的中间阶段表示进行交互。例如，RETRO（Borgeaud 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)）引入了一个 Chunked Cross Attention（CCA）层来处理生成块中的检索块，而 Wu 等（[2022](https://arxiv.org/html/2405.06211v3#bib.bib166)）引入了 kNN-Augmented Attention 层。类似地，EAE（Févry 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib40)）和 TOME（de Jong 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib23)）使用 Entity Memory 和 MemoryAttention 层分别整合检索到的实体和实体提及。这种中间层集成可以频繁且高效地使用许多块，以增强整个 RAG 模型的能力。它提供了一种高效的替代方案，用于整合大量经常检索的文本块，这些文本块由于 LMs 的输入长度限制（Borgeaud 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)）而难以通过输入层集成进行处理。然而，也需要注意，中间层集成要求对生成模型有较高的访问权限，这对大多数通过推理 API 访问的 LLMs（Ma 等，[2023a](https://arxiv.org/html/2405.06211v3#bib.bib99)）来说并不可行。

### 3.4\. 检索增强的必要性和频率

基于 LLM 的生成中的检索操作通常旨在补充知识以增强生成效果。尽管增强检索模型展现出有前景的潜力，但它们也因未能成为普遍解决方案而受到批评（Li 等，[2022b](https://arxiv.org/html/2405.06211v3#bib.bib76)；Petroni 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib110)），因为不加区分地用无关的段落来增强 LLM 可能会覆盖 LLM 已经掌握的潜在正确知识，从而导致错误的回答（Maekawa 等，[2024](https://arxiv.org/html/2405.06211v3#bib.bib100)）。Thakur 等人（[2023](https://arxiv.org/html/2405.06211v3#bib.bib148)）贡献了一个人工标注的数据集，以帮助评估 LLM 在外部检索知识中的错误鲁棒性，并观察到 LLM 在无关检索段落上的幻觉率可能是相关段落的两倍。因此，对于 RA-LLMs 来说，准确回忆先前知识同时在必要时选择性地融入检索信息是至关重要的，这是通向鲁棒 RA-LLMs 的最终路径。

现有的大多数方法通过 LLM 的初步回答或其内部推理结果来确定检索的必要性（Ram 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib118)；Min 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib103)）。例如，Self-RAG（Asai 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib6)）引入了特殊标记来评估检索的必要性并控制检索行为。其他方法设计了迭代提示，以决定在生成过程中是否需要额外的信息，从而需要调用检索或其他操作来处理 LLM（Yao 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib176)；Wei 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib163)）。Wang 等人（[2023a](https://arxiv.org/html/2405.06211v3#bib.bib160)）提出了自知识引导的检索增强（SKR）方法，该方法利用 LLM 自身或显式的小型可训练模型提供自知识作为适应性调用检索器的参考。在传统 RAGs 中，检索必要性判断也已经被探索并提出了直观的方法，例如评估生成模型产生的 logits 的置信度（Jiang 等，[2021](https://arxiv.org/html/2405.06211v3#bib.bib57)；Kadavath 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib60)；He 等，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib48)）。这样的解决方案也适用于 RA-LLMs，例如，FLARE（Jiang 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib58)）在 logits 低于特定阈值时动态触发 RAG。Tan 等人（[2024](https://arxiv.org/html/2405.06211v3#bib.bib147)）引入了一个更灵活的模型 SlimPLM，它通过一个瘦小的代理模型检测 LLM 中缺失的知识，该模型生成一个“启发式答案”。“启发式答案”用于评估检索的必要性，并在必要时促进检索过程中的查询重写。

在传统的 RAGs 中，检索频率（也称为检索步幅）是一个重要的设计方面，用于决定生成中使用检索的程度，从而极大地影响 RAG 模型的整体性能 (Ram et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib118))。检索频率控制了对检索结果的依赖程度，从而影响模型的效率和效果。当没有考虑检索的必要性时，检索频率通常是预定义且固定的，常见的设置有：一次性、每 n 个 token 和每个 token。一次性检索仅在一次操作中调用检索函数，并试图找到所有所需的信息。一次性检索通常在生成过程的开始阶段进行，然后将所有检索到的文档与原始输入一起提供给生成模型，正如 REALM (Guu et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib47)) 中所应用的那样。一种性检索更适用于外部数据库中的信息对 LLMs 明显的情况 (Jiang et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib58))。然而，对于需要长篇输出的语言任务，如开放域总结，生成过程中更重要的是考虑输出中 token 之间的依赖关系。在这些情况下，预先检索的文档（通过一次性检索）可能不足以支持整个输出序列的生成，这需要在生成过程中进行检索操作。为此，In-Context RALM (Ram et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib118)) 和 RETRO (Borgeaud et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib7)) 在生成过程中应用每 n 个 token 检索以获得更好的增强。相比之下，kNN-LM (Khandelwal et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib63)) 采用了更频繁的检索策略，在生成过程中为每个 token 的预测检索信息。总体而言，应用不同的检索频率可以影响整个 RAG 方法的有效性和效率。例如，更频繁的检索可以带来更好的性能，但也增加了计算成本 (Ram et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib118))。选择检索频率几乎是计算成本和性能之间的权衡。

## 4\. RA-LLMs 训练

根据是否需要训练，现有的 RAG 方法可以分为两大类：无训练方法和基于训练的方法。无训练方法通常在推理时直接利用检索到的知识，通过将检索到的文本插入提示中来进行计算，这种方法计算效率较高。然而，一个潜在的挑战是检索器和生成器组件没有针对下游任务进行特定优化，这可能导致对检索知识的利用效果不佳。为了充分利用外部知识，提出了大量方法来微调检索器和生成器，从而引导大型语言模型有效地适应和整合检索到的信息（Sarto 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib128)；Wang 等，[2023c](https://arxiv.org/html/2405.06211v3#bib.bib154)；Schick 等，[2024](https://arxiv.org/html/2405.06211v3#bib.bib129)；Zhu 等，[2024](https://arxiv.org/html/2405.06211v3#bib.bib200)；Shao 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib131)；Shi 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib136)）。

根据训练策略，我们将这些基于训练的方法分为三类：1）独立训练方法独立训练 RAG 过程中的每个组件，2）顺序训练方法先训练一个模块并冻结训练好的组件以指导另一部分的调整过程，以及 3）联合训练方法同时训练检索器和生成器。在接下来的部分，我们将全面回顾无训练、独立训练、顺序训练和联合训练方法。这些不同训练方法的比较如图[5](https://arxiv.org/html/2405.06211v3#S4.F5 "图 5 ‣ 4\. RA-LLMs 训练 ‣ RAG 与 LLMs 的会议：面向检索增强的大型语言模型")所示。

![参见说明](img/1a659a5b01c2ef160b61ce311c78d792.png)

图 5\. 检索增强大型语言模型（RA-LLMs）中不同训练方法的示意图。现有的 RA-LLMs 方法可以分为两类：无训练方法通常在推理时通过将检索到的知识整合到提示中来直接利用检索到的信息，而基于训练的方法则微调检索和生成器，以提高生成性能。根据训练策略，基于训练的方法可以进一步分为三组：独立训练，即检索和生成器组件独立训练；顺序训练，即先训练一个模块并冻结训练好的组件来指导另一部分的调整过程；以及联合训练，即同时训练检索器和生成器。

### 4.1\. 无训练

由于参数数量庞大，LLMs 已展现出与人类相当的智能，并在各种下游任务上取得了有希望的预测性能。然而，频繁进行微调并更新模型参数中存储的知识是极具挑战性的，因为这需要大量的时间和计算资源（Lewis 等人，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)）。最近，许多研究建议通过检索机制来增强 LLMs，使其能够动态地从外部来源获取新知识而无需额外的训练过程（即 *训练自由*）（Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)；Jiang 等人，[2023](https://arxiv.org/html/2405.06211v3#bib.bib58)；Khattab 等人，[2022](https://arxiv.org/html/2405.06211v3#bib.bib64)），而不是仅仅依赖于模型参数中编码的隐含知识。这些方法在各种知识密集型任务上，如开放域问答（Lewis 等人，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)），显示出了显著的性能提升。根据 LLMs 利用检索信息的不同方式，我们将这些训练自由方法分为两类：1) 基于提示工程的方法将检索到的知识直接整合到原始提示中，2) 检索引导的标记生成方法通过检索信息来校准标记生成过程。

#### 4.1.1\. 基于提示工程的方法

由于 LLMs 的生成性能高度依赖于输入查询，许多无训练的 RAG 方法通过改进原始提示来利用外部知识 (Jiang et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib58); Khattab et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib64); Li et al., [2023d](https://arxiv.org/html/2405.06211v3#bib.bib82))。具体来说，检索到的文本通常作为上下文信息使用，并与原始提示结合，以指导 LLMs 的生成 (Izacard and Grave, [2021b](https://arxiv.org/html/2405.06211v3#bib.bib55); Jiang et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib58); Khattab et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib64); Purwar and Sundar, [2023](https://arxiv.org/html/2405.06211v3#bib.bib113); Li et al., [2023d](https://arxiv.org/html/2405.06211v3#bib.bib82); Wang et al., [2023g](https://arxiv.org/html/2405.06211v3#bib.bib159); Kim et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib66))。例如，In-Context RALM (Ram et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib118)) 保持 LLM 参数不变，直接将检索到的文档插入到原始提示之前，以增强生成过程。IRCoT (Trivedi et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib150)) 交替进行思维链（CoT）生成和知识检索步骤，使得与后续推理步骤相关的信息比标准检索方法（仅依赖于问题作为查询）更容易检索到。GENREAD (Yu et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib183)) 则首先提示 LLM 生成基于查询的上下文文档，然后根据给定的上下文和问题生成答案。SKR (Wang et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib160)) 提出了引导 LLMs 判断是否可以根据其内部知识回答给定问题的方案，从而通过选择性调用检索器灵活利用内部和外部知识。TOC (Kim et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib66)) 首先为模糊问题检索相关知识，并通过将模糊问题细化为多个澄清问题来递归构建树结构，进一步聚合以生成长篇答案。

#### 4.1.2\. 检索引导的令牌生成方法

除了直接将外部知识整合到原始提示中，还可以利用辅助信息来调整令牌生成过程。例如，KNN-KMs（Khandelwal 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib63)）首先根据给定的查询从数据存储库中检索 $k$ 个最相关的上下文，并根据距离计算邻居分布。通过插值邻居分布和原始模型的输出分布来校准输出分布。Rest（He 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib50)）被提议用非参数检索数据存储库替代参数化的草稿模型，并根据当前上下文检索相关令牌以进行推测性解码（Chen 等，[2023a](https://arxiv.org/html/2405.06211v3#bib.bib10)；Leviathan 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib72)；Sun 等，[2024](https://arxiv.org/html/2405.06211v3#bib.bib146)）。

### 4.2\. 独立训练

独立训练指的是将检索器和语言模型（LLMs）作为两个完全独立的过程进行训练，在训练过程中检索器和 LLMs 之间没有任何互动（Karpukhin et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib62)；Zhou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib198)；Lan et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib70)）。与免训练方法相比，RAG 增强模型的性能可以通过训练 LLMs 以利用检索到的知识或训练检索器来弥合信息检索与语言生成之间的差距来有效提升。对于 LLMs 的训练，负对数似然损失是最具代表性的训练目标（Radford et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib116)；Touvron et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib149)），其目标是引导 LLMs 根据给定的输入生成期望的输出。关于检索器，它可以分为两种类型：1）稀疏检索器（Ramos et al., [2003](https://arxiv.org/html/2405.06211v3#bib.bib121)；Robertson et al., [2009](https://arxiv.org/html/2405.06211v3#bib.bib126)），和 2）密集检索器（Lan et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib70)；Karpukhin et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib62)；Zhou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib198)）。稀疏检索器通常利用稀疏特征，例如词频，来表示文档并根据特定任务的度量计算相关性分数（Li et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib78)；Ramos et al., [2003](https://arxiv.org/html/2405.06211v3#bib.bib121)；Robertson et al., [2009](https://arxiv.org/html/2405.06211v3#bib.bib126)），如 TF-IDF 和 BM25。至于密集检索器，深度神经网络被用来将查询和文档编码成密集表示，然后通常使用内积来计算相关性分数和检索相关的外部知识。例如，DPR（Karpukhin et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib62)）采用两个独立的 BERT（Devlin et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib26)）网络分别编码查询和段落，并通过对比学习训练这些模型。CoG（Lan et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib70)）提出训练一个前缀编码器和一个短语编码器用于检索，并将文本生成重新表述为从现有源文本集合中进行多个复制和粘贴操作。

### 4.3\. 顺序训练

独立训练是一种高效的方法，可以在生成过程中利用外部知识，因为检索器和生成器可以离线训练，并且可以使用任何现成的模型，从而避免了额外的训练成本。为了更好地增强检索器和生成器之间的协同作用，已经提出了几种方法来顺序训练检索器和大型语言模型（LLMs）。在这些顺序训练方法中，过程通常从检索器或生成器的独立预训练开始，然后将预训练的模块固定，而另一个模块进行训练。需要注意的是，现有的各种模型（例如，BERT（Devlin et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib26); Reimers and Gurevych, [2019](https://arxiv.org/html/2405.06211v3#bib.bib124); Khattab and Zaharia, [2020](https://arxiv.org/html/2405.06211v3#bib.bib65)）、CLIP（Radford et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib114)）、T5（Raffel et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib117)））可以直接用作固定的检索器和生成器，从而绕过首个相关的过程。与独立训练相比，顺序训练涉及检索器和生成器的协调训练，其中可训练模块从固定模块的帮助中受益。根据检索器和生成器之间的训练顺序，顺序训练可以分为两类：1）检索器优先（Sarto et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib128); Wang et al., [2023c](https://arxiv.org/html/2405.06211v3#bib.bib154); Schick et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib129); Zhu et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib200); Asai et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib6))，和 2）大型语言模型优先（Shi et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib136); Wang et al., [2024b](https://arxiv.org/html/2405.06211v3#bib.bib158); Shao et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib131)）。

#### 4.3.1\. 检索器优先

这些方法首先训练检索模型，然后固定它。接着，通过利用检索到的知识来训练大语言模型（LLMs）。例如，RETRO （Borgeaud et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib7)）采用了作为检索器的独立预训练的 BERT 模型，并且训练了一个编码器-解码器架构，以将检索到的片段整合到模型的预测中。RALMs （Yoran et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib182)）采用了 Google 搜索和开源的 COLBERTV2 （Khattab and Zaharia, [2020](https://arxiv.org/html/2405.06211v3#bib.bib65)）作为预训练的检索器，并对 LLM 进行微调，以有效利用检索到的段落。ITER-RTGEN （Ren et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib125)）利用了预训练的 S-BERT （Reimers and Gurevych, [2019](https://arxiv.org/html/2405.06211v3#bib.bib124)）作为检索器，并引入了一种自适应混合检索策略以检索演示。此外，它还利用 T5 （Raffel et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib117)）作为生成器，根据目标标签和输入对其进行进一步的微调，将原始提示与检索到的演示结合。SMALLCAP （Ramos et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib122)）建议使用 CLIP （Radford et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib114)），这是一种强大的预训练多模态网络，用于编码输入图像和外部数据存储中的文本数据，并根据余弦相似度检索最相关的项。训练了一个交叉注意力层，并使用 GPT-2 （Radford et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib116)）作为解码器来生成标题。

<svg class="ltx_picture ltx_centering" height="279.44" id="S4.F6.pic1" overflow="visible" version="1.1" width="690.51"><g fill="#000000" stroke="#000000" transform="translate(0,279.44) matrix(1 0 0 -1 0 0) translate(359.48,0) translate(0,271.63)"><g stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -98.43 -2.48)"><foreignobject height="8.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="196.85">应用程序 <g stroke-width="0.4pt"><g fill="#808080" fill-opacity="0.5" stroke-opacity="0.5" transform="matrix(1.0 0.0 0.0 1.0 2.09 -2.09)"><path d="M -169.92 -51.52 L -248.33 -51.52 C -249.85 -51.52 -251.09 -52.76 -251.09 -54.29 L -251.09 -63.82 C -251.09 -65.35 -249.85 -66.59 -248.33 -66.59 L -169.92 -66.59 C -168.39 -66.59 -167.15 -65.35 -167.15 -63.82 L -167.15 -54.29 C -167.15 -52.76 -168.39 -51.52 -169.92 -51.52 Z M -251.09 -66.59" style="stroke:none"></path></g><g fill="#EDCBC9" stroke-width="0.4pt"><path d="M -169.92 -51.52 L -248.33 -51.52 C -249.85 -51.52 -251.09 -52.76 -251.09 -54.29 L -251.09 -63.82 C -251.09 -65.35 -249.85 -66.59 -248.33 -66.59 L -169.92 -66.59 C -168.39 -66.59 -167.15 -65.35 -167.15 -63.82 L -167.15 -54.29 C -167.15 -52.76 -168.39 -51.52 -169.92 -51.52 Z M -251.09 -66.59"></path></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -247.86 -61.53)"><foreignobject height="8.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="77.49">NLP 应用</foreignobject></g></g> <g stroke-width="0.4pt"><path d="M -27.65 -7.81 L -176.68 -49.89" style="fill:none"><g transform="matrix(-0.96237 -0.27174 0.27174 -0.96237 -176.68 -49.89)"><path d="M 4.98 0 C 3.51 0.28 1.11 1.11 -0.55 2.08 L -0.55 -2.08 C 1.11 -1.11 3.51 -0.28 4.98 0" style="stroke:none"></path></g><g fill="#EDCBC9"><g stroke-width="0.4pt"><g fill="#808080" fill-opacity="0.5" stroke-opacity="0.5" transform="matrix(1.0 0.0 0.0 1.0 2.09 -2.09)"><path d="M -268.34 -110.63 L -346.75 -110.63 C -348.28 -110.63 -349.52 -111.87 -349.52 -113.4 L -349.52 -122.82 C -349.52 -124.35 -348.28 -125.59 -346.75 -125.59 L -268.34 -125.59 C -266.81 -125.59 -265.57 -124.35 -265.57 -122.82 L -265.57 -113.4 C -265.57 -111.87 -266.81 -110.63 -268.34 -110.63 Z M -349.52 -125.59" style="stroke:none"></path></g><g fill="#FAEBD7" stroke-width="0.4pt"><path d="M -268.34 -110.63 L -346.75 -110.63 C -348.28 -110.63 -349.52 -111.87 -349.52 -113.4 L -349.52 -122.82 C -349.52 -124.35 -348.28 -125.59 -346.75 -125.59 L -268.34 -125.59 C -266.81 -125.59 -265.57 -124.35 -265.57 -122.82 L -265.57 -113.4 C -265.57 -111.87 -266.81 -110.63 -268.34 -110.63 Z M -349.52 -125.59"></path></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -346.29 -120.64)"><foreignobject height="8.5" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="77.49">QA 系统</foreignobject></g></g> <path d="M -222.13 -66.86 L -290.35 -107.79" style="fill:none"></path></g><g fill="#000000" transform="matrix(-0.85751 -0.51445 0.51445 -0.85751 -290.35 -107.79)"><path d="M 4.98 0 C 3.51 0.28 1.11 1.11 -0.55 2.08 L -0.55 -2.08 C 1.11 -1.11 3.51 -0.28 4.98 0" style="stroke:none"></path></g><g fill="#EDCBC9"><g

图 6。RA-LLMs 应用的总结，按*NLP 应用*、*下游任务*和*领域特定应用*分类。具体而言，NLP 应用包括 QA 系统、聊天机器人和事实验证；下游任务包括推荐系统和软件工程；领域特定应用包括科学和金融领域的 AI。

#### 4.3.2。LLMs 优先

同样，它也可以先对 LLMs 进行预训练，然后在训练有素的 LLMs 的监督下调整检索器。例如，DKRR（Izacard 和 Grave，[2021a](https://arxiv.org/html/2405.06211v3#bib.bib54)）显示，序列到序列模型的注意力分数可以指示文档的相关性。因此，他们建议利用读者模型的注意力分数来生成合成标签以训练检索器。AAR（Yu 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib185)）建议使用小型语言模型生成监督信号以训练检索器。训练有素的检索器可以进一步用于提高黑箱 LLMs 的性能。RA-DIT（Lin 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib87)）首先微调 LLMs 以增强其利用检索知识的能力，然后训练检索器以更好地对齐其输出与 LLMs。UPRISE（Cheng 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib17)）提出了一种轻量级的方法，通过引入提示检索器来提升 LLMs 在未见任务中的零-shot 性能。冻结的 LLM 被用来指导提示检索器的微调过程，然后该检索器在推理过程中为不同任务检索各种 LLMs 的提示。

### 4.4。联合训练

联合训练方法 (Zhong 等人，[2022](https://arxiv.org/html/2405.06211v3#bib.bib197); Kang 等人，[2023](https://arxiv.org/html/2405.06211v3#bib.bib61); Li 等人，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib80); Xu 等人，[2023c](https://arxiv.org/html/2405.06211v3#bib.bib168); Hu 等人，[2023](https://arxiv.org/html/2405.06211v3#bib.bib52); Cheng 等人，[2024](https://arxiv.org/html/2405.06211v3#bib.bib18)) 采用端到端的范式来同时优化检索器和生成器。与按顺序训练每个模块不同，联合训练方法有效提升了检索器在生成过程中定位外部知识的能力，以及生成器有效利用检索到的信息的能力。例如，RAG (Lewis 等人，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)) 通过最小化负对数似然来联合训练检索器和生成器。REALM (Guu 等人，[2020](https://arxiv.org/html/2405.06211v3#bib.bib47)) 采用了与 RAG (Lewis 等人，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)) 相似的训练范式，而最大内积搜索 (MIPS) (Ram 和 Gray，[2012](https://arxiv.org/html/2405.06211v3#bib.bib120); Chen 等人，[2019](https://arxiv.org/html/2405.06211v3#bib.bib16); Shen 等人，[2015](https://arxiv.org/html/2405.06211v3#bib.bib132); Ding 等人，[2020a](https://arxiv.org/html/2405.06211v3#bib.bib30)) 技术用于定位最相关的文档。使用 MIPS 时，首先对所有外部文档进行嵌入，并为每个嵌入生成一个搜索索引。提出了一种异步索引更新策略 (Guu 等人，[2020](https://arxiv.org/html/2405.06211v3#bib.bib47); Izacard 等人，[2023](https://arxiv.org/html/2405.06211v3#bib.bib56); Siriwardhana 等人，[2023](https://arxiv.org/html/2405.06211v3#bib.bib142); Huang 等人，[2023](https://arxiv.org/html/2405.06211v3#bib.bib53))，以便每几百次训练步骤刷新一次索引，以避免重新索引所有文档的时间消耗。

## 5\. 应用

在本节中，我们将介绍一些代表性的检索增强大语言模型（RA-LLMs）的应用。为了提供 RA-LLMs 应用的清晰概述，我们将从 *NLP 应用*、*下游任务* 和 *领域特定应用* 三个角度对其进行回顾。本节提到的研究在图 [6](https://arxiv.org/html/2405.06211v3#S4.F6 "Figure 6 ‣ 4.3.1\. Retriever First ‣ 4.3\. Sequential Training ‣ 4\. RA-LLMs Training ‣ A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models") 中进行了总结和分类。

### 5.1\. NLP 应用

由于在文本生成中的内在能力，RA-LLMs 在 NLP 领域有多种应用，如问答系统（QA 系统）、聊天机器人和事实验证。

#### 5.1.1\. QA 系统

QA 系统旨在为用户的查询提供准确的答案。然而，即使经过广泛的数据训练，这些系统也可能缺乏最新的信息或未包含在训练数据中的特定领域知识（Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)；Liu 等，[2022b](https://arxiv.org/html/2405.06211v3#bib.bib92)）。为了解决这一局限性，RA-LLMs 的集成在提升 QA 系统的能力方面发挥了关键作用，通过增强它们检索和综合相关信息的能力（Borgeaud 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)；Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)）。具体而言，RA-LLMs 可以通过利用其检索组件访问广泛的知识库，从而提供连贯且具有上下文相关的答案。例如，REALM（Guu 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib47)）集成了一个知识检索器，该检索器可以在预训练、微调和推理过程中从大规模语料库中检索信息。这种方法使得 REALM 能够有效地从广泛的知识库中检索信息，从而提高其回答的准确性。同样，Fusion-in-Decoder（Izacard 和 Grave，[2021b](https://arxiv.org/html/2405.06211v3#bib.bib55)）从支持文档中检索段落，然后将其与问题融合以生成答案，从而实现更高的准确性。此外，Borgeaud 等（[2022](https://arxiv.org/html/2405.06211v3#bib.bib7)）指出，答案的质量可能更多地依赖于检索的输出。

#### 5.1.2\. ChatBot

ChatBot 旨在以自然且对话式的方式与用户互动（Liu 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib88)）。与问答系统不同，ChatBot 专注于与用户保持连贯且富有上下文的对话。为了增强这些能力，最近的方法集中在整合 RA-LLMs（Komeili 等，[2022](https://arxiv.org/html/2405.06211v3#bib.bib69)；Zhang 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib189)；Kang 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib61)），以其能够通过相关的外部知识增强 ChatBot，从而促进与用户的更有趣和富有上下文的互动。例如，一些研究（Ghazvininejad 等，[2018](https://arxiv.org/html/2405.06211v3#bib.bib44)；Chen 等，[2020](https://arxiv.org/html/2405.06211v3#bib.bib15)）从静态数据库（例如维基百科的数据库）中检索相关知识，以增强对话。Komeili 等（[2022](https://arxiv.org/html/2405.06211v3#bib.bib69)）提出从互联网搜索中检索信息，以进一步增强对话性能。考虑到世界知识的动态性，另一种模型（Wang 等，[2023d](https://arxiv.org/html/2405.06211v3#bib.bib153)）进一步访问搜索引擎中的大量动态信息来生成回应。

#### 5.1.3\. 事实验证

事实验证是验证信息准确性和可靠性的关键任务。由于对可信证据的需求，RA-LLMs 被用于增强事实验证的能力（Lewis 等，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)；Izacard 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib56)；Lewis 等，[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)）。Lewis 等（[2020c](https://arxiv.org/html/2405.06211v3#bib.bib75)）首次提出通过检索外部知识来增强一系列知识密集型任务，包括事实验证。另一方面，Atlas（Izacard 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib56)）研究了 RA-LLMs 在少样本学习下的事实验证性能。最近，Self-RAG（Asai 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib6)）通过引入自我反思机制，给人留下了深刻印象。具体来说，Self-RAG 反思检索的信息是否有帮助，并判断检索信息的可靠性，从而大大提高了验证准确性。

### 5.2\. 下游任务

除了自然语言处理应用外，RA-LLMs 也可以应用于各种下游任务，如推荐系统和软件工程。

#### 5.2.1\. 推荐

推荐系统在建模用户偏好和提供个性化推荐方面发挥了重要作用（Zhang et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib190); Wang et al., [2024a](https://arxiv.org/html/2405.06211v3#bib.bib155); Fan et al., [2019](https://arxiv.org/html/2405.06211v3#bib.bib36); Zhao et al., [2024a](https://arxiv.org/html/2405.06211v3#bib.bib196); Fan et al., [2020](https://arxiv.org/html/2405.06211v3#bib.bib37), [2022a](https://arxiv.org/html/2405.06211v3#bib.bib35))。最近，RA-LLMs 在通过集成检索和生成过程提供个性化和语境相关推荐方面展示了巨大潜力（Di Palma, [2023](https://arxiv.org/html/2405.06211v3#bib.bib27); Wu et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib164); Lu et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib95)）。例如，Di Palma ([2023](https://arxiv.org/html/2405.06211v3#bib.bib27)) 提出了一个简单的检索增强推荐模型，利用电影或书籍数据集中的知识来提升推荐效果。此外，Lu et al. ([2021](https://arxiv.org/html/2405.06211v3#bib.bib95)) 进一步从评论中进行检索，以丰富推荐系统中的项目信息。CoRAL（Wu et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib164)）利用强化学习从数据集中检索协作信息，并与语义信息对齐，以提供更准确的推荐。

#### 5.2.2\. 软件工程

RA-LLMs 的兴起影响了软件工程的许多方面（Zhou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib198); Nashid et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib106); Ye et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib178)）。例如，一些研究提出了用于代码生成（Zhou et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib198)）和程序修复（Nashid et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib106)）的检索增强生成范式。类似地，Parvez et al. ([2021](https://arxiv.org/html/2405.06211v3#bib.bib109)) 从代码库中检索排名靠前的代码或摘要，并与输入信息汇总，以增强代码生成和总结。此外，RA-LLMs 在表格数据处理（Ye et al., [2023a](https://arxiv.org/html/2405.06211v3#bib.bib178); Li et al., [2024b](https://arxiv.org/html/2405.06211v3#bib.bib77)）和文本到 SQL 语义解析（Shi et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib135); Poesia et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib112)）中展现了潜力。

### 5.3\. 特定领域应用

RA-LLMs 已广泛应用于各种特定领域的任务，例如科学和金融领域的 AI。

#### 5.3.1\. 科学中的 AI

RA-LLMs 已被证明对科学领域有益，例如分子和蛋白质。分子包括识别分子的属性和预测新分子，从而有利于药物发现。目前，一些 RA-LLMs 通过整合分子结构和生物医学实体（如蛋白质、分子和疾病）的检索已被应用于分子研究（Wang 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib161)；Liu 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib91)；Yang 等，[2023a](https://arxiv.org/html/2405.06211v3#bib.bib175)；Wang 等，[2023e](https://arxiv.org/html/2405.06211v3#bib.bib162)）等。Wang 等（[2023b](https://arxiv.org/html/2405.06211v3#bib.bib161)）；Li 等（[2023a](https://arxiv.org/html/2405.06211v3#bib.bib78)）提出了基于检索的框架，通过从数据库中检索来指导分子生成。Liu 等（[2023](https://arxiv.org/html/2405.06211v3#bib.bib91)）介绍了一种多模态分子结构-文本模型，通过从大规模数据集中检索文本知识来预测分子属性。此外，RA-LLMs 还对蛋白质表示和生成有显著影响（Sun 等，[2023](https://arxiv.org/html/2405.06211v3#bib.bib145)；Ma 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib98)）。例如，RSA（Ma 等，[2023b](https://arxiv.org/html/2405.06211v3#bib.bib98)）查询与数据库中一组结构或功能相似的序列相关的蛋白质序列，以增强蛋白质表示。此外，Lozano 等（[2023](https://arxiv.org/html/2405.06211v3#bib.bib93)）提出了一个基于检索已发布综述文章的临床 QA 系统。

#### 5.3.2\. 财务

在高度数据驱动和信息密集的金融领域，RA-LLMs 已被证明是一项显著的技术，有助于提升决策能力 (Zhang et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib188); Yepes et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib179); Li et al., [2024a](https://arxiv.org/html/2405.06211v3#bib.bib79))。例如，Zhang et al. ([2023b](https://arxiv.org/html/2405.06211v3#bib.bib188)) 从外部来源，如新闻平台（例如 Bloomberg 和 Reuters）和社交媒体平台（例如 Twitter、Reddit），检索金融信息，以结合原始查询来提高金融情感分析的精准度。此外，金融 QA 是金融分析的另一个主要任务，通常从金融文档中提取相关知识。由于专业文档通常以 PDF 格式存储，Lin ([2024](https://arxiv.org/html/2405.06211v3#bib.bib86)) 引入了一个结合 RA-LLMs 的 PDF 解析器，以从金融报告中检索知识。另一方面，Yepes et al. ([2024](https://arxiv.org/html/2405.06211v3#bib.bib179)) 提出了基于结构的文档分块方法，而不是基于段落的分块，从而进一步提高了 RA-LLMs 输出的质量。

## 6\. 未来的挑战与机遇

由于 RA-LLMs 的研究仍处于早期阶段，我们提出了一些未来可以探索的潜在研究方向。

可信赖的 RA-LLMs。开发 RAG 驱动的 LLMs 的基本目标是提升语言模型的能力，从而通过减少冗余和无意义的劳动、提高便利性和促进社会进步来造福用户和社会。然而，最近的研究表明，RA-LLMs 可能会被恶意或无意中操控，做出不可靠的决策并对人类造成伤害（Deng et al., [2024b](https://arxiv.org/html/2405.06211v3#bib.bib24); Zou et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib201)），这可能在安全关键场景中产生严重后果（Liu et al., [2021](https://arxiv.org/html/2405.06211v3#bib.bib89); Fan et al., [2022b](https://arxiv.org/html/2405.06211v3#bib.bib39), [2021](https://arxiv.org/html/2405.06211v3#bib.bib33); Chen et al., [2023b](https://arxiv.org/html/2405.06211v3#bib.bib14), [2022](https://arxiv.org/html/2405.06211v3#bib.bib12))。此外，私人检索数据库存在泄漏的风险，引发了关于 RA-LLMs 隐私的担忧（Zeng et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib187)）。因此，开发可信赖的 RA-LLMs 至关重要，因为它可以显著减轻 LLMs 技术的潜在负面影响，并为人们提供可以完全信赖的强大 AI 模型。具体来说，RA-LLMs 系统的理想可信赖性应具备以下特征：1) 鲁棒性，2) 公平性，3) 可解释性，和 4) 隐私。例如，鲁棒性意味着一个可信赖的 RA-LLMs 系统应能抵御攻击者引入的恶意或无意的扰动。公平性指的是一个可信赖的 RA-LLMs 系统在决策过程中应避免歧视。可解释性要求对 RA-LLMs 系统的内在工作有完全的理解，即 RA-LLMs 系统的预测是可解释和透明的。隐私则涉及在建立可信赖的 RA-LLMs 系统时保护存储在数据存储库中的私人信息的安全。

多语言 RA-LLMs。利用多种语言的知识可以大大增强检索增强语言模型的能力。随着世界日益互联互通，对能够理解和跨语言交流的 AI 系统的需求不断增长。通过融入多语言知识检索和生成，这些模型可以访问和综合来自不同语言源的信息，从而实现更全面和细致的理解和生成能力。此外，多语言模型可以促进跨文化交流和知识共享，打破语言障碍，为全球不同地区的人们带来便利，特别是那些处于少数语言地区的人们 (Kabra et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib59); Li et al., [2023d](https://arxiv.org/html/2405.06211v3#bib.bib82))。例如，来自语言较少的国家的用户可以利用丰富的英语和中文语料库进行知识检索，提高大型语言模型在下游任务中的表现。

多模态 RA-LLMs。多模态检索增强生成扩展了知识源，超越了文本，包括图像、视频和音频等各种数据模态。通过整合多种模态，LLMs 可以利用比单模态 RAG 更丰富的上下文信息，形成对用户需求的更全面理解，从而实现精准、细致和高质量的生成。例如，图像或视频可以提供补充文本信息的有价值的视觉线索，导致更准确的语言生成 (Zhu et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib200); Hu et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib52))。通过融合多种模态，多模态 RA-LLMs 可以形成对世界的更全面理解，从而产生更准确、更有洞察力的输出，惠及包括医疗保健 (Zhu et al., [2024](https://arxiv.org/html/2405.06211v3#bib.bib200))、药物发现 (Shtar, [2021](https://arxiv.org/html/2405.06211v3#bib.bib137))、分子分析 (Liu et al., [2023](https://arxiv.org/html/2405.06211v3#bib.bib91); Andrews et al., [2022](https://arxiv.org/html/2405.06211v3#bib.bib4))等广泛领域。

外部知识的质量。作为当前 RAG 系统中常用的数据存储库，维基百科 (Zhu 等, [2024](https://arxiv.org/html/2405.06211v3#bib.bib200); Karpukhin 等, [2020](https://arxiv.org/html/2405.06211v3#bib.bib62)) 作为一个包含数百万篇涵盖各个学科的文章的外部文本知识库，用于增强生成过程。然而，维基百科内各个文章的可靠性和准确性差异很大，某些偏离事实的文本甚至可能误导模型的生成过程。因此，提升外部知识库的质量，并减轻低质量知识对 LLM 性能的负面影响至关重要。通过提高外部知识的质量并制定稳健机制以筛选低质量或不可靠的信息，RA-LLM 系统可能会生成更准确、更可靠的输出，从而提高其在各种实际应用中的有效性。

## 7\. 结论

检索增强生成（RAG），一种前沿的 AI 技术，在推荐、分子生成、蛋白质表示和软件工程等各种应用中取得了显著成功，这得益于检索在提供补充信息以提升生成性能方面的强大能力。最近，越来越多的努力被投入到缓解大型语言模型（LLMs）如幻觉和过时的内部知识等限制，通过利用检索提供最新的辅助信息，并教会 LLMs 运用检索到的外部知识。随着检索增强大型语言模型（RA-LLMs）的快速进展，对其进行全面和系统的概述变得迫在眉睫。为弥补这一空白，本文从模型架构、训练策略和应用领域等方面对 RA-LLMs 进行了全面评审，为研究人员提供了深入的理解。此外，由于 RA-LLMs 的研究仍处于早期阶段，我们还讨论了当前的局限性和未来研究的若干潜在方向。

## 参考文献

+   (1)

+   Achiam 等 (2023) Josh Achiam, Steven Adler, Sandhini Agarwal, Lama Ahmad, Ilge Akkaya, Florencia Leoni Aleman, Diogo Almeida, Janko Altenschmidt, Sam Altman, Shyamal Anadkat, 等. 2023. Gpt-4 技术报告. *arXiv 预印本 arXiv:2303.08774* (2023)。

+   Agrawal 等 (2023) Sweta Agrawal, Chunting Zhou, Mike Lewis, Luke Zettlemoyer, 和 Marjan Ghazvininejad. 2023. 机器翻译的上下文示例选择. 发表在 *ACL (Findings)*. 计算语言学协会, 8857–8873。

+   Andrews et al. (2022) Miles C Andrews, Junna Oba, Chang-Jiun Wu, Haifeng Zhu, Tatiana Karpinets, Caitlin A Creasy, Marie-Andrée Forget, Xiaoxing Yu, Xingzhi Song, Xizeng Mao, 等。2022。多模态分子程序调控黑色素瘤细胞状态。*自然通讯* 13, 1 (2022), 4000。

+   Asai et al. (2023a) Akari Asai, Sewon Min, Zexuan Zhong 和 Danqi Chen。2023a。基于检索的语言模型及应用。在*第 61 届计算语言学协会年会（第 6 卷：教程摘要）*上。41–46。

+   Asai et al. (2023b) Akari Asai, Zeqiu Wu, Yizhong Wang, Avirup Sil 和 Hannaneh Hajishirzi。2023b。Self-RAG：通过自我反思学习检索、生成和批判。在*第十二届国际学习表征会议*上。

+   Borgeaud et al. (2022) Sebastian Borgeaud, Arthur Mensch, Jordan Hoffmann, Trevor Cai, Eliza Rutherford, Katie Millican, George Bm Van Den Driessche, Jean-Baptiste Lespiau, Bogdan Damoc, Aidan Clark, 等。2022。通过从万亿个标记中检索来改进语言模型。在*国际机器学习会议*上。PMLR，2206–2240。

+   Brown et al. (2020) Tom Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared D Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, 等。2020。语言模型是少量学习者。*神经信息处理系统进展* 33 (2020), 1877–1901。

+   Buttcher et al. (2016) Stefan Buttcher, Charles LA Clarke 和 Gordon V Cormack。2016。*信息检索：实现和评估搜索引擎*。MIT 出版社。

+   Chen et al. (2023a) Charlie Chen, Sebastian Borgeaud, Geoffrey Irving, Jean-Baptiste Lespiau, Laurent Sifre 和 John Jumper。2023a。通过投机采样加速大型语言模型解码。*arXiv 预印本 arXiv:2302.01318* (2023)。

+   Chen et al. (2017) Danqi Chen, Adam Fisch, Jason Weston 和 Antoine Bordes。2017。阅读维基百科以回答开放域问题。在*ACL (1)*。计算语言学协会，1870–1879。

+   Chen et al. (2022) Jingfan Chen, Wenqi Fan, Guanghui Zhu, Xiangyu Zhao, Chunfeng Yuan, Qing Li 和 Yihua Huang。2022。知识增强的黑箱攻击用于推荐。在*第 28 届 ACM SIGKDD 知识发现与数据挖掘会议论文集*。108–117。

+   Chen et al. (2021) Mark Chen, Jerry Tworek, Heewoo Jun, Qiming Yuan, Henrique Ponde de Oliveira Pinto, Jared Kaplan, Harri Edwards, Yuri Burda, Nicholas Joseph, Greg Brockman, 等。2021。评估在代码上训练的大型语言模型。*arXiv 预印本 arXiv:2107.03374* (2021)。

+   Chen et al. (2023b) Xiao Chen, Wenqi Fan, Jingfan Chen, Haochen Liu, Zitao Liu, Zhaoxiang Zhang 和 Qing Li。2023b。公平自适应负采样用于推荐。在*ACM Web 会议 2023 论文集*。3723–3733。

+   Chen et al. (2020) Xiuyi Chen, Fandong Meng, Peng Li, Feilong Chen, Shuang Xu, Bo Xu, 和 Jie Zhou. 2020. 弥合知识选择的先验与后验差距以生成基于知识的对话。*2020 年自然语言处理实证方法会议（EMNLP）论文集*。3426–3437。

+   Chen et al. (2019) Yudong Chen, Zhihui Lai, Yujuan Ding, Kaiyi Lin, 和 Wai Keung Wong. 2019. 基于锚图的深度监督哈希。*IEEE/CVF 国际计算机视觉会议论文集*。9796–9804。

+   Cheng et al. (2023) Daixuan Cheng, Shaohan Huang, Junyu Bi, Yuefeng Zhan, Jianfeng Liu, Yujing Wang, Hao Sun, Furu Wei, Weiwei Deng, 和 Qi Zhang. 2023. UPRISE：用于提高零样本评估的通用提示检索。*2023 年自然语言处理实证方法会议论文集*。12318–12337。

+   Cheng et al. (2024) Xin Cheng, Di Luo, Xiuying Chen, Lemao Liu, Dongyan Zhao, 和 Rui Yan. 2024. 自我提升：利用自我记忆的检索增强文本生成。*神经信息处理系统进展* 36 (2024)。

+   Chowdhery et al. (2023) Aakanksha Chowdhery, Sharan Narang, Jacob Devlin, Maarten Bosma, Gaurav Mishra, Adam Roberts, Paul Barham, Hyung Won Chung, Charles Sutton, Sebastian Gehrmann, 等. 2023. Palm：通过路径扩展语言建模。*机器学习研究期刊* 24, 240 (2023), 1–113。

+   Croft et al. (2010) W Bruce Croft, Donald Metzler, 和 Trevor Strohman. 2010. *搜索引擎：信息检索实践*。第 520 卷。Addison-Wesley Reading。

+   Cui et al. (2021) Leyang Cui, Yu Wu, Jian Liu, Sen Yang, 和 Yue Zhang. 2021. 基于模板的命名实体识别使用 BART。*ACL/IJCNLP（发现）* *(ACL 发现，卷 ACL/IJCNLP 2021)*. 计算语言学协会，1835–1845。

+   Dahl et al. (2024) Matthew Dahl, Varun Magesh, Mirac Suzgun, 和 Daniel E Ho. 2024. 大型法律虚构：分析大型语言模型中的法律幻觉。*arXiv 预印本 arXiv:2401.01301* (2024)。

+   de Jong et al. (2022) Michiel de Jong, Yury Zemlyanskiy, Nicholas FitzGerald, Fei Sha, 和 William W. Cohen. 2022. 提及记忆：通过实体提及注意将文本知识纳入 Transformers。*ICLR*。OpenReview.net。

+   Deng et al. (2024b) Gelei Deng, Yi Liu, Kailong Wang, Yuekang Li, Tianwei Zhang, 和 Yang Liu. 2024b. Pandora：通过检索增强生成的中毒破解 GPTs。*arXiv 预印本 arXiv:2402.08416* (2024)。

+   Deng et al. (2024a) Ziqing Deng, Zhihui Lai, Yujuan Ding, Heng Kong, 和 Xu Wu. 2024a. 大规模图像检索的深度缩放因子量化网络。*ICMR*。ACM，851–859。

+   Devlin et al. (2019) Jacob Devlin, Ming-Wei Chang, Kenton Lee, 和 Kristina Toutanova. 2019. BERT：用于语言理解的深度双向 Transformer 预训练。*NAACL-HLT (1)*. 计算语言学协会，4171–4186。

+   Di Palma（2023）Dario Di Palma。2023 年。检索增强的推荐系统：利用大型语言模型增强推荐系统。在*第 17 届 ACM 推荐系统会议论文集*。1369–1373。

+   Ding 等人（2024）Yujuan Ding, Yunshan Ma, Wenqi Fan, Yige Yao, Tat-Seng Chua, 和 Qing Li。2024 年。FashionReGen: LLM 赋能的时尚报告生成。*arXiv 预印本 arXiv:2403.06660*（2024）。

+   Ding 等人（2023）Yujuan Ding, P. Y. Mok, Yunshan Ma, 和 Yi Bin。2023 年。基于用户协调偏好的个性化时尚搭配生成。*信息处理与管理* 60, 5（2023），103434。

+   Ding 等人（2020a）Yujuan Ding, Wai Keung Wong, Zhihui Lai, 和 Zheng Zhang。2020a 年。基于 2D 图像特征的双线性监督哈希。*IEEE 电路与系统视频技术学报* 30, 2（2020），590–602。

+   Ding 等人（2020b）Yujuan Ding, Wai Keung Wong, Zhihui Lai, 和 Zheng Zhang。2020b 年。用于大规模图像检索的判别性双流深度哈希。*信息处理与管理* 57, 6（2020），102288。

+   Drozdov 等人（2022）Andrew Drozdov, Nathanael Schärli, Ekin Akyürek, Nathan Scales, Xinying Song, Xinyun Chen, Olivier Bousquet, 和 Denny Zhou。2022 年。利用大型语言模型进行组合语义解析。在*第十一届国际学习表征会议*。

+   Fan 等人（2021）Wenqi Fan, Tyler Derr, Xiangyu Zhao, Yao Ma, Hui Liu, Jianping Wang, Jiliang Tang, 和 Qing Li。2021 年。通过复制跨领域用户档案攻击黑箱推荐。在*2021 IEEE 第 37 届国际数据工程会议（ICDE）*。IEEE, 1583–1594。

+   Fan 等人（2024a）Wenqi Fan, Yujuan Ding, Liangbo Ning, Shijie Wang, Hengyun Li, Dawei Yin, Tat-Seng Chua, 和 Qing Li。2024a 年。关于 RAG 会议 LLM 的调查：迈向检索增强的大型语言模型。*第 30 届 ACM SIGKDD 知识发现与数据挖掘会议论文集*（2024）。

+   Fan 等人（2022a）Wenqi Fan, Xiaorui Liu, Wei Jin, Xiangyu Zhao, Jiliang Tang, 和 Qing Li。2022a 年。用于推荐的图趋势过滤网络。在*第 45 届国际 ACM SIGIR 信息检索研究与发展会议论文集*。112–121。

+   Fan 等人（2019）Wenqi Fan, Yao Ma, Qing Li, Yuan He, Eric Zhao, Jiliang Tang, 和 Dawei Yin。2019 年。用于社交推荐的图神经网络。在*全球网络大会*。417–426。

+   Fan 等人（2020）Wenqi Fan, Yao Ma, Qing Li, Jianping Wang, Guoyong Cai, Jiliang Tang, 和 Dawei Yin。2020 年。用于社交推荐的图神经网络框架。*IEEE 知识与数据工程学报*（2020）。

+   Fan 等人（2024b）Wenqi Fan, Shijie Wang, Jiani Huang, Zhikai Chen, Yu Song, Wenzhuo Tang, Haitao Mao, Hui Liu, Xiaorui Liu, Dawei Yin, 等。2024b 年。在大型语言模型（LLMs）时代的图机器学习。*arXiv 预印本 arXiv:2404.14928*（2024）。

+   （2022b 年）范文琦，赵湘宇，陈霄，苏京然，高敬佟，王琳，刘其栋，王奕琦，徐翰，陈蕾，等。2022b。值得信赖的推荐系统全面调查。*arXiv 预印本 arXiv:2209.10117*（2022）。

+   （2020 年）Thibault Févry, Livio Baldini Soares, Nicholas FitzGerald, Eunsol Choi 和 Tom Kwiatkowski。2020 年。实体作为专家：具有实体监督的稀疏内存访问。在*EMNLP（1）*。计算语言学协会，4937-4951。

+   （2023a 年）Luyu Gao, Xueguang Ma, Jimmy Lin 和 Jamie Callan。2023a。无需相关性标签的精确零样密集检索。在*ACL（1）*。计算语言学协会，1762–1777。

+   （2023b 年）Yunfan Gao, Yun Xiong, Xinyu Gao, Kangxiang Jia, Jinliu Pan, Yuxi Bi, Yi Dai, Jiawei Sun 和 Haofen Wang。2023b。用于大型语言模型的检索增强生成：一项调查。*arXiv 预印本 arXiv:2312.10997*（2023）。

+   （2022 年）Izacard Gautier, Caron Mathilde, Hosseini Lucas, Riedel Sebastian, Bojanowski Piotr, Joulin Armand 和 Grave Edouard。2022。使用对比学习进行无监督的稠密信息检索。*机器学习研究交易*（2022）。

+   （2018 年）Marjan Ghazvininejad，Chris Brockett，Ming-Wei Chang，Bill Dolan，Jianfeng Gao，Yihu Wen-tau，Michel Galley。2018。知识基础的神经对话模型。在*人工智能 AAAI 会议论文集*，第 32 卷。

+   （2022 年）Michael R. Glass, Gaetano Rossiello, Md. Faisal Mahbub Chowdhury, Ankita Naik, Pengshan Cai 和 Alfio Gliozzo。2022 年。Re2G：检索，重新排名，生成。在*NAACL-HLT*。计算语言学协会，2701–2715。

+   （2017 年）Edouard Grave, Armand Joulin 和 Nicolas Usunier。2017。使用连续缓存改进神经语言模型。在*ICLR（海报）*。OpenReview.net。

+   （2020 年）Kelvin Guu, Kenton Lee, Zora Tung, Panupong Pasupat 和 Mingwei Chang。2020 年。检索增强的语言模型预训练。在*国际机器学习会议*。PMLR，3929–3938。

+   （2021b 年）Junxian He, Graham Neubig 和 Taylor Berg-Kirkpatrick。2021b。高效的最近邻语言模型。在*EMNLP（1）*。计算语言学协会，5703–5714。

+   （2021a 年）Qiuxiang He, Guoping Huang, Qu Cui, Li Li 和 Lemao Liu。2021a。使用翻译记忆快速准确的神经机器翻译。在*计算语言学协会第 59 届年会和第 11 届国际自然语言处理联合会议（第 1 卷：长篇论文）*。3170–3180。

+   （2023 年）Zhenyu He，Zexuan Zhong，Tianle Cai，Jason D Lee 和 Di He。 2023. REST：基于检索的推测解码。*arXiv 预印本 arXiv:2311.08252*（2023）。

+   Hofstätter 等（2023）Sebastian Hofstätter、Jiecao Chen、Karthik Raman 和 Hamed Zamani。2023。*FiD-Light：高效且有效的检索增强文本生成*。发表于*SIGIR*。ACM，1437–1447。

+   Hu 等（2023）Ziniu Hu、Ahmet Iscen、Chen Sun、Zirui Wang、Kai-Wei Chang、Yizhou Sun、Cordelia Schmid、David A Ross 和 Alireza Fathi。2023。*Reveal：基于多源多模态知识记忆的检索增强视觉语言预训练*。发表于*IEEE/CVF 计算机视觉与模式识别会议论文集*。23369–23379。

+   Huang 等（2023）Jie Huang、Wei Ping、Peng Xu、Mohammad Shoeybi、Kevin Chen-Chuan Chang 和 Bryan Catanzaro。2023。*Raven：基于检索增强的编码器-解码器语言模型的上下文学习*。*arXiv 预印本 arXiv:2308.07922*（2023）。

+   Izacard 和 Grave（2021a）Gautier Izacard 和 Edouard Grave。2021a。*从阅读器到检索器提取知识以进行问题回答*。发表于*ICLR 2021-第 9 届国际学习表示会议*。

+   Izacard 和 Grave（2021b）Gautier Izacard 和 Edouard Grave。2021b。*利用生成模型的段落检索进行开放领域问答*。发表于*EACL 2021-第 16 届欧洲计算语言学协会会议*。计算语言学协会，874–880。

+   Izacard 等（2023）Gautier Izacard、Patrick Lewis、Maria Lomeli、Lucas Hosseini、Fabio Petroni、Timo Schick、Jane Dwivedi-Yu、Armand Joulin、Sebastian Riedel 和 Edouard Grave。2023。*Atlas：基于检索增强语言模型的少样本学习*。*机器学习研究杂志* 24，251（2023），1–43。

+   Jiang 等（2021）郑宝江、Jun Araki、Haibo Ding 和 Graham Neubig。2021。*我们如何知道语言模型知道什么？关于语言模型在问题回答中的校准*。*计算语言学协会会刊* 9（2021），962–977。

+   Jiang 等（2023）郑宝江、Frank F Xu、刘宇高、孙志青、刘倩、Jane Dwivedi-Yu、杨一鸣、Jamie Callan 和 Graham Neubig。2023。*主动检索增强生成*。发表于*2023 年自然语言处理实证方法会议论文集*。7969–7992。

+   Kabra 等（2023）Anubha Kabra、Emmy Liu、Simran Khanuja、Alham Fikri Aji、Genta Winata、Samuel Cahyawijaya、Anuoluwapo Aremu、Perez Ogayo 和 Graham Neubig。2023。*多语言和多文化隐喻语言理解*。发表于*第 61 届计算语言学协会年会*。

+   Kadavath 等（2022）Saurav Kadavath、Tom Conerly、Amanda Askell、Tom Henighan、Dawn Drain、Ethan Perez、Nicholas Schiefer、Zac Hatfield-Dodds、Nova DasSarma、Eli Tran-Johnson 等。2022。*语言模型（大多数情况下）知道它们知道什么*。*arXiv 预印本 arXiv:2207.05221*（2022）。

+   Kang 等 (2023) Minki Kang, Jin Myung Kwak, Jinheon Baek 和 Sung Ju Hwang. 2023. 知识图谱增强的语言模型用于知识基础对话生成。*arXiv 预印本 arXiv:2305.18846* (2023)。

+   Karpukhin 等 (2020) Vladimir Karpukhin, Barlas Oguz, Sewon Min, Patrick S. H. Lewis, Ledell Wu, Sergey Edunov, Danqi Chen 和 Wen-tau Yih. 2020. 用于开放领域问答的密集段落检索。发表于 *EMNLP (1)*。计算语言学协会, 6769–6781。

+   Khandelwal 等 (2020) Urvashi Khandelwal, Omer Levy, Dan Jurafsky, Luke Zettlemoyer 和 Mike Lewis. 2020. 通过记忆实现泛化：最近邻语言模型。发表于 *国际学习表征会议*。

+   Khattab 等 (2022) Omar Khattab, Keshav Santhanam, Xiang Lisa Li, David Hall, Percy Liang, Christopher Potts 和 Matei Zaharia. 2022. Demonstrate-search-predict: 组合检索和语言模型以实现知识密集型 NLP。*arXiv 预印本 arXiv:2212.14024* (2022)。

+   Khattab 和 Zaharia (2020) Omar Khattab 和 Matei Zaharia. 2020. Colbert: 通过在 BERT 上进行上下文化的晚期交互实现高效和有效的段落检索。发表于 *第 43 届国际 ACM SIGIR 信息检索研究与开发会议论文集*。39–48。

+   Kim 等 (2023) Gangwoo Kim, Sungdong Kim, Byeongguk Jeon, Joonsuk Park 和 Jaewoo Kang. 2023. 澄清之树：通过增强检索的大型语言模型回答模糊问题。发表于 *2023 年自然语言处理实证方法会议*。

+   Kim 等 (2022) Hyuhng Joon Kim, Hyunsoo Cho, Junyeob Kim, Taeuk Kim, Kang Min Yoo 和 Sang-goo Lee. 2022. 自生成的上下文学习：利用自回归语言模型作为演示生成器。*arXiv 预印本 arXiv:2206.08082* (2022)。

+   Kobayashi 和 Takeda (2000) Mei Kobayashi 和 Koichi Takeda. 2000. 网络上的信息检索。*ACM 计算调查 (CSUR)* 32, 2 (2000), 144–173。

+   Komeili 等 (2022) Mojtaba Komeili, Kurt Shuster 和 Jason Weston. 2022. 互联网增强对话生成。发表于 *ACL (1)*。计算语言学协会, 8460–8478。

+   Lan 等 (2022) Tian Lan, Deng Cai, Yan Wang, Heyan Huang 和 Xian-Ling Mao. 2022. 复制即所需。发表于 *第十一届国际学习表征会议*。

+   Lazaridou 等 (2022) Angeliki Lazaridou, Elena Gribovskaya, Wojciech Stokowiec 和 Nikolai Grigorev. 2022. 通过少量提示的互联网增强语言模型用于开放领域问答。*arXiv 预印本 arXiv:2203.05115* (2022)。

+   Leviathan 等 (2023) Yaniv Leviathan, Matan Kalman 和 Yossi Matias. 2023. 通过推测解码实现变换器的快速推理。发表于 *国际机器学习会议*。PMLR, 19274–19286。

+   Lewis 等人（2020a）迈克·刘易斯、马尔詹·加兹维尼贾德、加尔吉·戈什、阿门·阿哈贾尼扬、韦斯·王、卢克·泽特尔莫耶。2020a。通过释义进行预训练。*神经信息处理系统进展* 33（2020），18470–18481。

+   Lewis 等人（2020b）迈克·刘易斯、尹汉·刘、纳曼·戈亚尔、马尔詹·加兹维尼贾德、阿卜杜勒拉赫曼·穆罕默德、奥梅尔·利维、维塞林·斯托亚诺夫、卢克·泽特尔莫耶。2020b。BART：用于自然语言生成、翻译和理解的去噪序列到序列预训练。在*ACL*。计算语言学协会，7871–7880。

+   Lewis 等人（2020c）帕特里克·刘易斯、伊桑·佩雷斯、亚历山德拉·皮克图斯、法比奥·佩特罗尼、弗拉基米尔·卡尔普欣、纳曼·戈亚尔、海因里希·库特勒、迈克·刘易斯、易文涛、蒂姆·罗克塔谢尔等。2020c。用于知识密集型 NLP 任务的检索增强生成。*神经信息处理系统进展* 33（2020），9459–9474。

+   Li 等人（2022b）李大亮、安基特·辛格·拉瓦特、曼兹尔·扎希尔、王欣、米哈乌·卢卡西克、安德烈亚斯·费特、费利克斯·余、三吉夫·库马尔。2022b。具有可控工作记忆的大型语言模型。*arXiv 预印本 arXiv:2211.05110*（2022）。

+   Li 等人（2024b）李鸿新、苏婧然、陈云涛、李青、赵向张。2024b。SheetCopilot：通过大型语言模型将软件生产力提升到新水平。*神经信息处理系统进展* 36（2024）。

+   Li 等人（2023a）李佳桐、刘云青、范文奇、魏晓勇、刘辉、唐济良、李青。2023a。利用大型语言模型赋能分子发现用于分子-标题翻译：一个 ChatGPT 的视角。*arXiv 预印本 arXiv:2306.06615*（2023）。

+   Li 等人（2024a）李翔、李振宇、施晨、徐勇、杜青、谭明奎、黄军、林伟。2024a。AlphaFin：基于检索增强的股票链框架进行金融分析的基准测试。*arXiv 预印本 arXiv:2403.12582*（2024）。

+   Li 等人（2023b）李新泽、刘征浩、熊晨艳、石宇、顾宇、刘志远、余戈。2023b。结构感知语言模型预训练提高了结构化数据的密集检索。在*第 61 届计算语言学协会年会*。

+   Li 等人（2023c）李晓楠、吕凯、严杭、林天阳、朱伟、倪原、谢国通、王晓灵、邱西鹏。2023c。用于上下文学习的统一演示检索器。在*ACL（1）*。计算语言学协会，4644–4668。

+   Li 等人（2023d）李晓倩、聂尔聪、梁胜。2023d。从分类到生成：跨语言检索增强 ICL 的见解。在*NeurIPS 2023 指令调优与指令跟随研讨会*。

+   Li 和 Qiu（2023）李晓楠、邱西鹏。2023。MoT：记忆思维使 ChatGPT 能够自我改进。在*2023 年自然语言处理实证方法会议*。计算语言学协会，新加坡，6354–6374。

+   Li 和 Liang (2021) Xiang Lisa Li 和 Percy Liang. 2021. Prefix-Tuning：优化生成的连续提示。载于 *ACL/IJCNLP (1)*。计算语言学协会，4582–4597。

+   Li 等人 (2022a) Zonglin Li, Ruiqi Guo, 和 Sanjiv Kumar. 2022a. 解耦上下文处理用于上下文增强语言建模。*神经信息处理系统进展* 35 (2022), 21698–21710。

+   Lin (2024) Demiao Lin. 2024. 通过增强的 PDF 结构识别革命性地改进检索增强生成。*arXiv 预印本 arXiv:2401.12599* (2024)。

+   Lin 等人 (2023) Xi Victoria Lin, Xilun Chen, Mingda Chen, Weijia Shi, Maria Lomeli, Richard James, Pedro Rodriguez, Jacob Kahn, Gergely Szilvasy, Mike Lewis, 等人. 2023. RA-DIT：检索增强的双重指令调优。载于 *第十二届国际学习表征会议*。

+   Liu 等人 (2020) Haochen Liu, Jamell Dacon, Wenqi Fan, Hui Liu, Zitao Liu, 和 Jiliang Tang. 2020. 性别是否重要？对话系统中的公平性探讨。载于 *第 28 届国际计算语言学大会论文集*。4403–4416。

+   Liu 等人 (2021) Haochen Liu, Yiqi Wang, Wenqi Fan, Xiaorui Liu, Yaxin Li, Shaili Jain, Yunhao Liu, Anil K Jain, 和 Jiliang Tang. 2021. 值得信赖的 AI：一种计算视角。*arXiv 预印本 arXiv:2107.06641* (2021)。

+   Liu 等人 (2022a) Jiachang Liu, Dinghan Shen, Yizhe Zhang, Bill Dolan, Lawrence Carin, 和 Weizhu Chen. 2022a. 什么样的上下文示例对 GPT-3 有效？载于 *DeeLIO@ACL*。计算语言学协会，100–114。

+   Liu 等人 (2023) Shengchao Liu, Weili Nie, Chengpeng Wang, Jiarui Lu, Zhuoran Qiao, Ling Liu, Jian Tang, Chaowei Xiao, 和 Animashree Anandkumar. 2023. 基于文本的多模态分子结构–文本模型用于文本检索和编辑。*自然机器智能* 5, 12 (2023), 1447–1457。

+   Liu 等人 (2022b) Ye Liu, Semih Yavuz, Rui Meng, Dragomir Radev, Caiming Xiong, 和 Yingbo Zhou. 2022b. Uni-Parser：用于知识库和数据库问答的统一语义解析器。载于 *EMNLP*。计算语言学协会，8858–8869。

+   Lozano 等人 (2023) Alejandro Lozano, Scott L Fleming, Chia-Chun Chiang, 和 Nigam Shah. 2023. Clinfo.ai：一个开源检索增强大型语言模型系统，用于使用科学文献回答医学问题。载于 *2024 年太平洋生物计算研讨会*。世界科学出版社，8–23。

+   Lu 等人 (2023) Pan Lu, Liang Qiu, Kai-Wei Chang, Ying Nian Wu, Song-Chun Zhu, Tanmay Rajpurohit, Peter Clark, 和 Ashwin Kalyan. 2023. 通过策略梯度进行动态提示学习，用于半结构化数学推理。载于 *ICLR*。OpenReview.net。

+   Lu 等人 (2021) Yu Lu, Junwei Bao, Yan Song, Zichen Ma, Shuguang Cui, Youzheng Wu, 和 Xiaodong He. 2021. RevCore：基于评论的对话推荐。载于 *ACL/IJCNLP (Findings)* *(ACL 发现集，卷 ACL/IJCNLP 2021)*。计算语言学协会，1161–1173。

+   Luo 等（2023b）Hongyin Luo, Tianhua Zhang, Yung-Sung Chuang, Yuan Gong, Yoon Kim, Xixin Wu, Helen Meng 和 James R. Glass。2023b。《搜索增强的指令学习》。在 *EMNLP (Findings)*。计算语言学协会，3717–3729。

+   Luo 等（2023a）Man Luo, Xin Xu, Zhuyun Dai, Panupong Pasupat, Mehran Kazemi, Chitta Baral, Vaiva Imbrasaite 和 Vincent Y Zhao。2023a。《Dr. icl：演示检索的上下文学习》。*arXiv 预印本 arXiv:2305.14128*（2023）。

+   Ma 等（2023b）Chang Ma, Haiteng Zhao, Lin Zheng, Jiayi Xin, Qintong Li, Lijun Wu, Zhihong Deng, Yang Lu, Qi Liu 和 Lingpeng Kong。2023b。《检索序列增强用于蛋白质表示学习》。*bioRxiv*（2023），2023–02。

+   Ma 等（2023a）Xinbei Ma, Yeyun Gong, Pengcheng He, Hai Zhao 和 Nan Duan。2023a。《用于检索增强的大型语言模型的查询重写》。*arXiv 预印本 arXiv:2305.14283*（2023）。

+   Maekawa 等（2024）Seiji Maekawa, Hayate Iso, Sairam Gurajada 和 Nikita Bhutani。2024。《检索是否有帮助或有害？深入探讨检索增强对语言模型的有效性》。*arXiv 预印本 arXiv:2402.13492*（2024）。

+   Menick 等（2022）Jacob Menick, Maja Trebacz, Vladimir Mikulik, John Aslanides, Francis Song, Martin Chadwick, Mia Glaese, Susannah Young, Lucy Campbell-Gillingham, Geoffrey Irving 等。2022。《教语言模型通过验证的引用来支持答案》。*arXiv 预印本 arXiv:2203.11147*（2022）。

+   Milios 等（2023）Aristides Milios, Siva Reddy 和 Dzmitry Bahdanau。2023。《多标签文本分类的上下文学习》。在 *第 1 届 GenBench 工作坊关于 NLP 中的（基准）泛化*。173–184。

+   Min 等（2022）Sewon Min, Xinxi Lyu, Ari Holtzman, Mikel Artetxe, Mike Lewis, Hannaneh Hajishirzi 和 Luke Zettlemoyer。2022。《重新思考演示的角色：是什么让上下文学习有效？》在 *EMNLP*。计算语言学协会，11048–11064。

+   Min 等（2020）Sewon Min, Julian Michael, Hannaneh Hajishirzi 和 Luke Zettlemoyer。2020。《AmbigQA：回答模糊的开放域问题》。在 *EMNLP (1)*。计算语言学协会，5783–5797。

+   Min 等（2023）Sewon Min, Weijia Shi, Mike Lewis, Xilun Chen, Wen-tau Yih, Hannaneh Hajishirzi 和 Luke Zettlemoyer。2023。《非参数掩蔽语言建模》。在 *ACL (Findings)*。计算语言学协会，2097–2118。

+   Nashid 等（2023）Noor Nashid, Mifta Sintaha 和 Ali Mesbah。2023。《基于检索的代码相关少样本学习提示选择》。在 *2023 IEEE/ACM 第 45 届国际软件工程会议（ICSE）*。IEEE，2450–2462。

+   O’Hare 等（2016）Neil O’Hare, Paloma De Juan, Rossano Schifanella, Yunlong He, Dawei Yin 和 Yi Chang。2016。《利用用户交互信号进行网页图像搜索》。在 *第 39 届国际 ACM SIGIR 信息检索研究与开发会议*。559–568。

+   Ouyang 等人（2022）Long Ouyang、Jeffrey Wu、Xu Jiang、Diogo Almeida、Carroll Wainwright、Pamela Mishkin、Chong Zhang、Sandhini Agarwal、Katarina Slama、Alex Ray 等人。2022。《训练语言模型以遵循带有人类反馈的指令》。*神经信息处理系统进展* 35（2022），27730–27744。

+   Parvez 等人（2021）Md. Rizwan Parvez、Wasi Uddin Ahmad、Saikat Chakraborty、Baishakhi Ray 和 Kai-Wei Chang。2021。《检索增强的代码生成与摘要》。在 *EMNLP (Findings)*。计算语言学协会，2719–2734。

+   Petroni 等人（2020）Fabio Petroni、Patrick S. H. Lewis、Aleksandra Piktus、Tim Rocktäschel、Yuxiang Wu、Alexander H. Miller 和 Sebastian Riedel。2020。《上下文如何影响语言模型的事实预测》。在 *AKBC*。

+   Petroni 等人（2019）Fabio Petroni、Tim Rocktäschel、Patrick Lewis、Anton Bakhtin、Yuxiang Wu、Alexander H Miller 和 Sebastian Riedel。2019。《语言模型作为知识库？》*arXiv 预印本 arXiv:1909.01066*（2019）。

+   Poesia 等人（2022）Gabriel Poesia、Alex Polozov、Vu Le、Ashish Tiwari、Gustavo Soares、Christopher Meek 和 Sumit Gulwani。2022。《Synchromesh：从预训练语言模型中可靠的代码生成》。在 *ICLR*。OpenReview.net。

+   Purwar 和 Sundar（2023）Anupam Purwar 和 Rahul Sundar。2023。《关键词增强检索：与语音接口集成的信息检索新框架》。*arXiv 预印本 arXiv:2310.04205*（2023）。

+   Radford 等人（2021）Alec Radford、Jong Wook Kim、Chris Hallacy、Aditya Ramesh、Gabriel Goh、Sandhini Agarwal、Girish Sastry、Amanda Askell、Pamela Mishkin、Jack Clark 等人。2021。《从自然语言监督中学习可转移的视觉模型》。在 *国际机器学习会议*。PMLR，8748–8763。

+   Radford 等人（2018）Alec Radford、Karthik Narasimhan、Tim Salimans、Ilya Sutskever 等人。2018。《通过生成预训练提高语言理解》。 (2018)。

+   Radford 等人（2019）Alec Radford、Jeffrey Wu、Rewon Child、David Luan、Dario Amodei、Ilya Sutskever 等人。2019。《语言模型是无监督的多任务学习者》。*OpenAI 博客* 1，8（2019），9。

+   Raffel 等人（2020）Colin Raffel、Noam Shazeer、Adam Roberts、Katherine Lee、Sharan Narang、Michael Matena、Yanqi Zhou、Wei Li 和 Peter J Liu。2020。《利用统一的文本到文本变换器探索迁移学习的极限》。*机器学习研究期刊* 21，140（2020），1–67。

+   Ram 等人（2023）Ori Ram、Yoav Levine、Itay Dalmedigos、Dor Muhlgay、Amnon Shashua、Kevin Leyton-Brown 和 Yoav Shoham。2023。《上下文检索增强语言模型》。*计算语言学学会会刊* 11（2023），1316–1331。

+   Ram 等人（2022）Ori Ram、Gal Shachaf、Omer Levy、Jonathan Berant 和 Amir Globerson。2022。《学习在无监督的情况下检索段落》。在 *NAACL-HLT*。计算语言学协会，2687–2700。

+   Ram 和 Gray（2012）Parikshit Ram 和 Alexander G Gray. 2012. 使用锥树进行最大内积搜索. 收录于 *第 18 届 ACM SIGKDD 国际知识发现与数据挖掘会议论文集*。931–939。

+   Ramos 等（2003）Juan Ramos 等. 2003. 使用 tf-idf 确定文档查询中的词汇相关性. 收录于 *第一次机器学习教学会议论文集*，第 242 卷。Citeseer，29–48。

+   Ramos 等（2023）Rita Ramos, Bruno Martins, Desmond Elliott, 和 Yova Kementchedjhieva. 2023. Smallcap：通过检索增强的轻量级图像描述. 收录于 *IEEE/CVF 计算机视觉与模式识别会议论文集*。2840–2849。

+   Reichman 和 Heck（2024）Benjamin Z. Reichman 和 Larry Heck. 2024. 检索增强生成：密集段落检索是否有效？*CoRR* abs/2402.11035（2024）。

+   Reimers 和 Gurevych（2019）Nils Reimers 和 Iryna Gurevych. 2019. Sentence-BERT：使用 Siamese BERT 网络的句子嵌入. 收录于 *2019 年自然语言处理实证方法会议及第 9 届国际联合自然语言处理会议（EMNLP-IJCNLP）*。3982–3992。

+   Ren 等（2023）Yubing Ren, Yanan Cao, Ping Guo, Fang Fang, Wei Ma, 和 Zheng Lin. 2023. Retrieve-and-sample: 文档级事件论元提取通过混合检索增强. 收录于 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*。293–306。

+   Robertson 等（2009）Stephen Robertson, Hugo Zaragoza, 等. 2009. 概率相关框架：BM25 及其扩展。*信息检索基础与趋势®* 3, 4（2009），333–389。

+   Rubin 等（2022）Ohad Rubin, Jonathan Herzig, 和 Jonathan Berant. 2022. 学习检索提示以进行上下文学习. 收录于 *NAACL-HLT*。计算语言学协会，2655–2671。

+   Sarto 等（2022）Sara Sarto, Marcella Cornia, Lorenzo Baraldi, 和 Rita Cucchiara. 2022. 用于图像描述的检索增强变换器. 收录于 *第 19 届基于内容的多媒体索引国际会议论文集*。1–7。

+   Schick 等（2024）Timo Schick, Jane Dwivedi-Yu, Roberto Dessì, Roberta Raileanu, Maria Lomeli, Eric Hambro, Luke Zettlemoyer, Nicola Cancedda, 和 Thomas Scialom. 2024. Toolformer：语言模型可以自我学习使用工具。*神经信息处理系统进展* 36（2024）。

+   Seo 等（2019）Minjoon Seo, Jinhyuk Lee, Tom Kwiatkowski, Ankur P Parikh, Ali Farhadi, 和 Hannaneh Hajishirzi. 2019. 实时开放域问答与密集-稀疏短语索引。*arXiv 预印本 arXiv:1906.05807*（2019）。

+   Shao 等（2023）Zhihong Shao, Yeyun Gong, Minlie Huang, Nan Duan, Weizhu Chen, 等. 2023. 通过迭代检索-生成协同增强检索增强的大型语言模型. 收录于 *2023 年自然语言处理实证方法会议*。

+   Shen 等人（2015）**Fumin Shen**、**Wei Liu**、**Shaoting Zhang**、**Yang Yang** 和 **Heng Tao Shen**。2015 年。学习用于最大内积搜索的二进制编码。在*IEEE 国际计算机视觉会议论文集*。4148–4156。

+   Sheynin 等人（2023）**Shelly Sheynin**、**Oron Ashual**、**Adam Polyak**、**Uriel Singer**、**Oran Gafni**、**Eliya Nachmani** 和 **Yaniv Taigman**。2023 年。kNN-Diffusion：通过大规模检索生成图像。在*ICLR*。OpenReview.net。

+   Shi 等人（2024）**Kaize Shi**、**Xueyao Sun**、**Qing Li** 和 **Guandong Xu**。2024 年。压缩长上下文以增强 RAG 与基于 AMR 的概念蒸馏。*arXiv 预印本 arXiv:2405.03085*（2024）。

+   Shi 等人（2022）**Peng Shi**、**Rui Zhang**、**He Bai** 和 **Jimmy Lin**。2022 年。XRICL：跨语言检索增强的上下文学习用于跨语言文本到 SQL 语义解析。在*EMNLP（发现）*。计算语言学协会，5248–5259。

+   Shi 等人（2023）**Weijia Shi**、**Sewon Min**、**Michihiro Yasunaga**、**Minjoon Seo**、**Rich James**、**Mike Lewis**、**Luke Zettlemoyer** 和 **Wen-tau Yih**。2023 年。Replug：检索增强的黑箱语言模型。*arXiv 预印本 arXiv:2301.12652*（2023）。

+   Shtar（2021）**Guy Shtar**。2021 年。用于药物知识发现的多模态机器学习。在*第 14 届 ACM 国际网络搜索与数据挖掘会议论文集*。1115–1116。

+   Shuster 等人（2021）**Kurt Shuster**、**Spencer Poff**、**Moya Chen**、**Douwe Kiela** 和 **Jason Weston**。2021 年。检索增强减少对话中的幻觉。在*EMNLP（发现）*。计算语言学协会，3784–3803。

+   Sia 和 Duh（2023）**Suzanna Sia** 和 **Kevin Duh**。2023 年。上下文学习作为保持一致性：使用大型语言模型的即时机器翻译研究。*arXiv 预印本 arXiv:2305.03573*（2023）。

+   Singh 等人（2021）**Devendra Singh**、**Siva Reddy**、**Will Hamilton**、**Chris Dyer** 和 **Dani Yogatama**。2021 年。端到端训练的多文档阅读器和检索器，用于开放域问答。*神经信息处理系统进展* 34（2021），25968–25981。

+   Singhal 等人（2001）**Amit Singhal** 等人。2001 年。现代信息检索：简要概述。*IEEE 数据工程快报* 24，4（2001），35–43。

+   Siriwardhana 等人（2023）**Shamane Siriwardhana**、**Rivindu Weerasekera**、**Elliott Wen**、**Tharindu Kaluarachchi**、**Rajib Rana** 和 **Suranga Nanayakkara**。2023 年。改善检索增强生成（RAG）模型的领域适应性，用于开放域问答。*计算语言学协会会刊* 11（2023），1–17。

+   Sparck Jones（1972）**Karen Sparck Jones**。1972 年。术语特异性的统计解释及其在检索中的应用。*文献学杂志* 28，1（1972），11–21。

+   Su 等人（2023）**Hongjin Su**、**Jungo Kasai**、**Chen Henry Wu**、**Weijia Shi**、**Tianlu Wang**、**Jiayi Xin**、**Rui Zhang**、**Mari Ostendorf**、**Luke Zettlemoyer**、**Noah A. Smith** 和 **Tao Yu**。2023 年。选择性注释使语言模型成为更好的少样本学习者。在*ICLR*。OpenReview.net。

+   Sun et al. (2023) 方孙、詹志豪、郭鸿宇、张铭、唐健。2023 年。Graphvf：可控的蛋白质特异性 3D 分子生成，使用变分流。*arXiv 预印本 arXiv:2304.12825* (2023)。

+   Sun et al. (2024) 孙子腾、安南达·提尔塔·苏雷什、罗在熙、艾哈迈德·贝拉米、希曼舒·贾因、费利克斯·余。2024 年。Spectr：通过最优传输实现快速的投机解码。*神经信息处理系统进展* 36 (2024)。

+   Tan et al. (2024) 谭杰军、窦志成、朱宇涛、郭佩栋、范坤、温基荣。2024 年。小模型，大洞察：利用精简代理模型决定何时以及检索什么以供 LLMs 使用。*arXiv 预印本 arXiv:2402.12052* (2024)。

+   Thakur et al. (2023) 南丹·塔库尔、路易斯·博尼法西奥、张欣瑜、奥杜纳约·奥贡德波、埃赫桑·卡马洛、戴维·阿尔丰索-赫梅洛、李小光、刘群、陈博兴、梅赫迪·雷扎戈利扎德，等。2023 年。NoMIRACL：了解何时不知道以实现鲁棒的多语言检索增强生成。*arXiv 预印本 arXiv:2312.11361* (2023)。

+   Touvron et al. (2023) 雨果·图弗龙、路易斯·马丁、凯文·斯通、彼得·阿尔伯特、阿姆贾德·阿尔马赫里、雅斯敏·巴巴伊、尼古拉·巴什利科夫、苏米亚·巴特拉、普拉贾瓦尔·巴尔加瓦、舒尔蒂·博萨尔，等。2023 年。Llama 2：开放基础和微调聊天模型。*arXiv 预印本 arXiv:2307.09288* (2023)。

+   Trivedi et al. (2023) 哈尔什·特里维迪、尼兰詹·巴拉苏布拉马尼安、图沙尔·科特、阿希什·萨巴尔瓦尔。2023 年。将检索与思维链推理交织用于知识密集型多步骤问题。在*第 61 届计算语言学协会年会*。

+   Tu et al. (2022) 屠立夫、肖岑明、周颖博。2022 年。Prompt-Tuning 在跨语言理解中的表现优于 Fine-Tuning，多语言模型的优势。在*EMNLP (Findings)*。计算语言学协会，5478–5485。

+   Vu et al. (2022) 屠武、布莱恩·莱斯特、诺亚·康斯坦特、拉米·阿尔-鲁夫、丹尼尔·塞尔。2022 年。SPoT：通过软提示转移改善冻结模型适应。在*ACL (1)*。计算语言学协会，5039–5059。

+   Wang et al. (2023d) 安特·王、林峰·宋、刘琦、米海涛、王龙跃、涂朝鹏、苏金松、杜东。2023d。搜索引擎增强对话响应生成，采用廉价监督查询生成。*人工智能* 319 (2023)，103874。

+   Wang et al. (2023c) 王博欣、魏平、徐鹏、劳伦斯·麦卡菲、刘紫涵、穆罕默德·肖耶比、董毅、奥列克西·库恰耶夫、李博、肖超伟，等。2023c。我们是否应该通过检索预训练自回归语言模型？一项全面研究。在*2023 年自然语言处理实证方法会议论文集*。7763–7786。

+   Wang et al. (2024a) 韩冰·王、刘晓瑞、范文琦、赵翔宇、维卡塔拉曼·基尼、德文德拉·亚达夫、费伊·王、闻震、唐继良、刘辉。2024a。重新思考用于顺序推荐的大型语言模型架构。*arXiv 预印本 arXiv:2402.09543* (2024)。

+   Wang et al. (2024c) Haoyu Wang, Tuo Zhao, 和 Jing Gao. 2024c. BlendFilter: 通过查询生成混合和知识过滤推进检索增强的大语言模型。 *arXiv 预印本 arXiv:2402.11129* (2024)。

+   Wang et al. (2023f) Liang Wang, Nan Yang, 和 Furu Wei. 2023f. Query2doc: 使用大语言模型进行查询扩展。见 *EMNLP*。计算语言学协会，9414–9423。

+   Wang et al. (2024b) Liang Wang, Nan Yang, 和 Furu Wei. 2024b. 学习检索上下文示例以供大语言模型使用。见 *EACL (1)*。计算语言学协会，1752–1767。

+   Wang et al. (2023g) Xintao Wang, Qianwen Yang, Yongting Qiu, Jiaqing Liang, Qianyu He, Zhouhong Gu, Yanghua Xiao, 和 Wei Wang. 2023g. Knowledgpt: 通过检索和存储访问知识库增强大语言模型。 *arXiv 预印本 arXiv:2308.11761* (2023)。

+   Wang et al. (2023a) Yile Wang, Peng Li, Maosong Sun, 和 Yang Liu. 2023a. 自我知识引导的检索增强用于大语言模型。见 *2023 年自然语言处理经验方法会议*。

+   Wang et al. (2023b) Zichao Wang, Weili Nie, Zhuoran Qiao, Chaowei Xiao, Richard G. Baraniuk, 和 Anima Anandkumar. 2023b. 基于检索的可控分子生成。见 *ICLR*。OpenReview.net。

+   Wang et al. (2023e) Zifeng Wang, Zichen Wang, Balasubramaniam Srinivasan, Vassilis N Ioannidis, Huzefa Rangwala, 和 Rishita Anubhai. 2023e. BioBridge: 通过知识图谱桥接生物医学基础模型。 *arXiv 预印本 arXiv:2310.03320* (2023)。

+   Wei et al. (2022) Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Fei Xia, Ed Chi, Quoc V Le, Denny Zhou 等. 2022. Chain-of-thought 提示引发大语言模型的推理。 *神经信息处理系统进展* 35 (2022), 24824–24837。

+   Wu et al. (2024) Junda Wu, Cheng-Chun Chang, Tong Yu, Zhankui He, Jianing Wang, Yupeng Hou, 和 Julian McAuley. 2024. CoRAL: 协作检索增强的大语言模型改进长尾推荐。 *arXiv 预印本 arXiv:2403.06447* (2024)。

+   Wu et al. (2020) Ledell Wu, Fabio Petroni, Martin Josifoski, Sebastian Riedel, 和 Luke Zettlemoyer. 2020. 可扩展的零样本实体链接与密集实体检索。见 *EMNLP (1)*。计算语言学协会，6397–6407。

+   Wu et al. (2022) Yuhuai Wu, Markus Norman Rabe, DeLesley Hutchins, 和 Christian Szegedy. 2022. 记忆变换器。见 *ICLR*。OpenReview.net。

+   Xiong et al. (2023) Miao Xiong, Zhiyuan Hu, Xinyang Lu, Yifei Li, Jie Fu, Junxian He, 和 Bryan Hooi. 2023. 大语言模型能否表达其不确定性？对大语言模型中信心引导的实证评估。 *arXiv 预印本 arXiv:2306.13063* (2023)。

+   Xu 等（2023c）徐本丰、赵春旭、姜文彬、朱鹏飞、戴松泰、庞超、孙卓、王硕环、孙宇。2023c 年。《检索增强的语言模型领域适应》。载于*第八届自然语言处理表示学习研讨会（RepL4NLP 2023）*。54–64。

+   Xu 等（2023b）徐芳远、石伟佳、崔恩溶。2023b 年。《RECOMP：通过上下文压缩和选择性增强改进检索增强型语言模型》。载于*第十二届国际学习表示会议*。

+   Xu 等（2019）胡旭、刘炳、舒磊、Philip S. Yu。2019 年。《BERT 后训练用于评论阅读理解和基于方面的情感分析》。载于*NAACL-HLT (1)*。计算语言学协会，2324–2335。

+   Xu 等（2020）徐继涛、Josep-Maria Crego、Jean Senellart。2020 年。《通过类似翻译提升神经机器翻译》。载于*计算语言学协会年会*。计算语言学协会，1570–1579。

+   Xu 等（2022）徐静、Arthur Szlam、Jason Weston。2022 年。《超越金鱼记忆：长期开放域对话》。载于*ACL (1)*。计算语言学协会，5180–5197。

+   Xu 等（2023a）徐世城、庞亮、沈华为、程学琦、蔡达生。2023a 年。《链内搜索：针对复杂知识密集型任务的准确、可信和可追溯的内容生成》。*arXiv 预印本 arXiv:2304.14732*（2023 年）。

+   Yang 等（2023b）杨浩言、李志涛、张勇、王建宗、程宁、李铭、肖静。2023b 年。《PRCA：通过可插拔的奖励驱动上下文适配器来适配黑箱大型语言模型以进行检索问答》。载于*EMNLP*。计算语言学协会，5364–5375。

+   Yang 等（2023a）杨玲、黄志林、周向欣、徐敏凯、张文涛、王宇、郑夏武、杨文明、Ron O Dror、洪申达等。2023a 年。《基于提示的三维分子扩散模型用于结构基础药物设计》。2023 年。

+   Yao 等（2023）姚顺宇、Jeffrey Zhao、尤春、杜楠、Izhak Shafran、Karthik R. Narasimhan、曹元。2023 年。《ReAct：在语言模型中协同推理与行动》。载于*ICLR*。OpenReview.net。

+   Ye 等（2023b）叶佳成、吴志勇、冯江涛、余涛、孔凌鹏。2023b 年。《上下文学习的组成示例》。载于*国际机器学习会议*。PMLR，39818–39833。

+   Ye 等（2023a）叶云胡、惠宾远、杨敏、李彬华、黄飞、李永斌。2023a 年。《大型语言模型是多才多艺的分解器：用于表格推理的证据和问题分解》。载于*SIGIR*。ACM，174–184。

+   Yepes 等（2024）Antonio Jimeno Yepes、姚优、Jan Milczek、Sebastian Laverde、Leah Li。2024 年。《财务报告分块以实现有效的检索增强生成》。*arXiv 预印本 arXiv:2402.05131*（2024 年）。

+   Yin et al. (2016) Dawei Yin, Yuening Hu, Jiliang Tang, Tim Daly, Mianwei Zhou, Hua Ouyang, Jianhui Chen, Changsung Kang, Hongbo Deng, Chikashi Nobata, 等. 2016. Yahoo 搜索中的相关性排序. 载于 *第 22 届 ACM SIGKDD 国际知识发现与数据挖掘会议论文集*. 323–332.

+   Yogatama et al. (2021) Dani Yogatama, Cyprien de Masson d’Autume, 和 Lingpeng Kong. 2021. 自适应半参数语言模型. *计算语言学协会会刊* 9 (2021), 362–373.

+   Yoran et al. (2023) Ori Yoran, Tomer Wolfson, Ori Ram, 和 Jonathan Berant. 2023. 使检索增强语言模型对无关上下文具有鲁棒性. 载于 *第十二届国际学习表征会议*.

+   Yu et al. (2023a) Wenhao Yu, Dan Iter, Shuohang Wang, Yichong Xu, Mingxuan Ju, Soumya Sanyal, Chenguang Zhu, Michael Zeng, 和 Meng Jiang. 2023a. 生成而非检索：大型语言模型是强大的上下文生成器. 载于 *ICLR*. OpenReview.net.

+   Yu et al. (2023c) Wenhao Yu, Zhihan Zhang, Zhenwen Liang, Meng Jiang, 和 Ashish Sabharwal. 2023c. 通过即插即用检索反馈改进语言模型. *arXiv 预印本 arXiv:2305.14002* (2023).

+   Yu et al. (2023b) Zichun Yu, Chenyan Xiong, Shi Yu, 和 Zhiyuan Liu. 2023b. 增强适配检索器提高语言模型作为通用插件的泛化能力. 载于 *第 61 届计算语言学协会年会（第 1 卷：长篇论文集）*. 2421–2436.

+   Zan et al. (2022) Daoguang Zan, Bei Chen, Zeqi Lin, Bei Guan, Yongji Wang, 和 Jian-Guang Lou. 2022. 当语言模型遇上私人库. 载于 *EMNLP (发现)*. 计算语言学协会, 277–288.

+   Zeng et al. (2024) Shenglai Zeng, Jiankun Zhang, Pengfei He, Yue Xing, Yiding Liu, Han Xu, Jie Ren, Shuaiqiang Wang, Dawei Yin, Yi Chang, 等. 2024. 好与坏：探索检索增强生成（RAG）中的隐私问题. *arXiv 预印本 arXiv:2402.16893* (2024).

+   Zhang et al. (2023b) Boyu Zhang, Hongyang Yang, Tianyu Zhou, Muhammad Ali Babar, 和 Xiao-Yang Liu. 2023b. 通过检索增强的大型语言模型提升金融情感分析. 载于 *第四届 ACM 国际金融人工智能会议论文集*. 349–356.

+   Zhang et al. (2020) Houyu Zhang, Zhenghao Liu, Chenyan Xiong, 和 Zhiyuan Liu. 2020. 基于常识知识图的引导遍历生成对话. 载于 *ACL*. 计算语言学协会, 2031–2043.

+   Zhang et al. (2024) Jiahao Zhang, Rui Xue, Wenqi Fan, Xin Xu, Qing Li, Jian Pei, 和 Xiaorui Liu. 2024. 线性时间图神经网络用于可扩展推荐. *arXiv 预印本 arXiv:2402.13973* (2024).

+   Zhang et al. (2023a) Yunxiang Zhang, Muhammad Khalifa, Lajanugen Logeswaran, Moontae Lee, Honglak Lee, 和 Lu Wang. 2023a. 融合生成的和检索的知识用于开放领域问答. *arXiv 预印本 arXiv:2310.14393* (2023).

+   Zhang et al. (2023c) Zhuosheng Zhang, Aston Zhang, Mu Li, 和 Alex Smola. 2023c. 大语言模型中的自动思维链提示。在*ICLR*。OpenReview.net。

+   Zhao et al. (2024b) Penghao Zhao, Hailin Zhang, Qinhan Yu, Zhengren Wang, Yunteng Geng, Fangcheng Fu, Ling Yang, Wentao Zhang, 和 Bin Cui. 2024b. AI 生成内容的检索增强生成：综述。*arXiv 预印本 arXiv:2402.19473* (2024)。

+   Zhao et al. (2023a) Ruochen Zhao, Hailin Chen, Weishi Wang, Fangkai Jiao, Xuan Long Do, Chengwei Qin, Bosheng Ding, Xiaobao Guo, Minzhi Li, Xingxuan Li, 等. 2023a. 检索多模态信息以增强生成：综述。*arXiv 预印本 arXiv:2303.10868* (2023)。

+   Zhao et al. (2023b) Wayne Xin Zhao, Kun Zhou, Junyi Li, Tianyi Tang, Xiaolei Wang, Yupeng Hou, Yingqian Min, Beichen Zhang, Junjie Zhang, Zican Dong, 等. 2023b. 大语言模型的综述。*arXiv 预印本 arXiv:2303.18223* (2023)。

+   Zhao et al. (2024a) Zihuai Zhao, Wenqi Fan, Jiatong Li, Yunqing Liu, Xiaowei Mei, Yiqi Wang, Zhen Wen, Fei Wang, Xiangyu Zhao, Jiliang Tang, 等. 2024a. 大语言模型（LLMs）时代的推荐系统。*IEEE 知识与数据工程学报* (2024)。

+   Zhong et al. (2022) Zexuan Zhong, Tao Lei, 和 Danqi Chen. 2022. 使用记忆增强训练语言模型。在*2022 年自然语言处理实证方法大会，EMNLP 2022*。

+   Zhou et al. (2022) Shuyan Zhou, Uri Alon, Frank F Xu, Zhengbao Jiang, 和 Graham Neubig. 2022. Docprompting：通过检索文档生成代码。在*第十一届国际表示学习大会*。

+   Zhu et al. (2023) Yin Zhu, Zhiling Luo, 和 Gong Cheng. 2023. 最远推理与计划评估：具有检索增强的大语言模型的稳定推理路径。*arXiv 预印本 arXiv:2309.12767* (2023)。

+   Zhu et al. (2024) Yinghao Zhu, Changyu Ren, Shiyun Xie, Shukai Liu, Hangyuan Ji, Zixiang Wang, Tao Sun, Long He, Zhoujun Li, Xi Zhu, 等. 2024. REALM：通过大语言模型驱动的多模态电子健康记录分析增强。*arXiv 预印本 arXiv:2402.07016* (2024)。

+   Zou et al. (2024) Wei Zou, Runpeng Geng, Binghui Wang, 和 Jinyuan Jia. 2024. PoisonedRAG：对大语言模型检索增强生成的知识毒化攻击。*arXiv 预印本 arXiv:2402.07867* (2024)。

生成于 2024 年 6 月 17 日 星期一 08:50:07 由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)</foreignobject></g></g></g></svg>
