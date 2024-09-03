<!--yml

分类：未分类

日期：2024-09-03 17:28:46

-->

# 下一代数据库接口：基于 LLM 的文本到 SQL 的调查

> 来源：[`arxiv.org/html/2406.08426`](https://arxiv.org/html/2406.08426)

1.  [I 引言](https://arxiv.org/html/2406.08426v3#S1 "在下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

1.  [II 概述](https://arxiv.org/html/2406.08426v3#S2 "在下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

    1.  [II-A 文本到 SQL 中的挑战](https://arxiv.org/html/2406.08426v3#S2.SS1 "在 II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-A1 语言复杂性与模糊性](https://arxiv.org/html/2406.08426v3#S2.SS1.SSS1 "在 II-A 文本到 SQL 中的挑战 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-A2 模式理解与表示](https://arxiv.org/html/2406.08426v3#S2.SS1.SSS2 "在 II-A 文本到 SQL 中的挑战 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-A3 稀有与复杂的 SQL 操作](https://arxiv.org/html/2406.08426v3#S2.SS1.SSS3 "在 II-A 文本到 SQL 中的挑战 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-A4 跨领域泛化](https://arxiv.org/html/2406.08426v3#S2.SS1.SSS4 "在 II-A 文本到 SQL 中的挑战 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

    1.  [II-B 进化过程](https://arxiv.org/html/2406.08426v3#S2.SS2 "在 II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-B1 基于规则的方法](https://arxiv.org/html/2406.08426v3#S2.SS2.SSS1 "在 II-B 进化过程 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-B2 基于深度学习的方法](https://arxiv.org/html/2406.08426v3#S2.SS2.SSS2 "在 II-B 进化过程 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-B3 基于 PLM 的实现](https://arxiv.org/html/2406.08426v3#S2.SS2.SSS3 "在 II-B 进化过程 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [II-B4 基于 LLM 的实现](https://arxiv.org/html/2406.08426v3#S2.SS2.SSS4 "在 II-B 进化过程 ‣ II 概述 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

1.  [III 基准与评估](https://arxiv.org/html/2406.08426v3#S3 "在下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

    1.  [III-A 数据集](https://arxiv.org/html/2406.08426v3#S3.SS1 "在 III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [III-A1 跨领域数据集](https://arxiv.org/html/2406.08426v3#S3.SS1.SSS1 "在 III-A 数据集 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 的调查中")

        1.  [III-A2 知识增强数据集](https://arxiv.org/html/2406.08426v3#S3.SS1.SSS2 "在 III-A 数据集 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

        1.  [III-A3 上下文依赖数据集](https://arxiv.org/html/2406.08426v3#S3.SS1.SSS3 "在 III-A 数据集 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

        1.  [III-A4 鲁棒性数据集](https://arxiv.org/html/2406.08426v3#S3.SS1.SSS4 "在 III-A 数据集 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

        1.  [III-A5 跨语言数据集](https://arxiv.org/html/2406.08426v3#S3.SS1.SSS5 "在 III-A 数据集 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

    1.  [III-B 评估指标](https://arxiv.org/html/2406.08426v3#S3.SS2 "在 III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

        1.  [III-B1 基于内容匹配的指标](https://arxiv.org/html/2406.08426v3#S3.SS2.SSS1 "在 III-B 评估指标 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

        1.  [III-B2 执行基指标](https://arxiv.org/html/2406.08426v3#S3.SS2.SSS2 "在 III-B 评估指标 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

1.  [IV 方法](https://arxiv.org/html/2406.08426v3#S4 "在下一代数据库接口：基于 LLM 的文本到 SQL 调研")

    1.  [IV-A 上下文学习](https://arxiv.org/html/2406.08426v3#S4.SS1 "在 IV 方法 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

    1.  [IV-B 微调](https://arxiv.org/html/2406.08426v3#S4.SS2 "在 IV 方法 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

1.  [V 期望](https://arxiv.org/html/2406.08426v3#S5 "在下一代数据库接口：基于 LLM 的文本到 SQL 调研")

    1.  [V-A 实际应用中的鲁棒性](https://arxiv.org/html/2406.08426v3#S5.SS1 "在 V 期望 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

    1.  [V-B 计算效率](https://arxiv.org/html/2406.08426v3#S5.SS2 "在 V 期望 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

    1.  [V-C 数据隐私与可解释性](https://arxiv.org/html/2406.08426v3#S5.SS3 "在 V 期望 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

    1.  [V-D 扩展](https://arxiv.org/html/2406.08426v3#S5.SS4 "在 V 期望 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调研")

# 下一代数据库接口：

基于 LLM 的文本到 SQL 调研

洪紫金¹、袁正²、张青刚²、陈浩²、董俊南²、黄飞然¹ 和黄晓²1 * 通讯作者。¹暨南大学，中国广州 ²香港理工大学，中国香港特别行政区 hongzijin@stu2020.jnu.edu.cn, yzheng.yuan@connect.polyu.hk, qinggangg.zhang@connect.polyu.hk, sundaychenhao@gmail.com, hanson.dong@connect.polyu.hk, huangfr@jnu.edu.cn, xiaohuang@comp.polyu.edu.hk

###### 摘要

从自然语言问题（文本到 SQL）生成准确的 SQL 一直是一个长期存在的挑战，因为这涉及到用户问题理解、数据库模式理解和 SQL 生成的复杂性。传统的文本到 SQL 系统，包括人工工程和深度神经网络，已经取得了实质性的进展。随后，预训练语言模型（PLMs）被开发并用于文本到 SQL 任务，取得了令人鼓舞的表现。随着现代数据库变得越来越复杂，相应的用户问题也变得更加具有挑战性，这导致参数受限的 PLM 生成错误的 SQL。因此，需要更复杂和量身定制的优化方法，这反过来又限制了基于 PLM 系统的应用。最近，大型语言模型（LLMs）随着模型规模的增加，在自然语言理解方面表现出了显著的能力。因此，集成基于 LLM 的实现可以为文本到 SQL 研究带来独特的机会、改进和解决方案。在本综述中，我们对基于 LLM 的文本到 SQL 进行了全面的回顾。具体而言，我们简要概述了文本到 SQL 的技术挑战和发展过程。接着，我们详细介绍了用于评估文本到 SQL 系统的数据集和度量指标。之后，我们对基于 LLM 的文本到 SQL 的最新进展进行了系统分析。最后，我们讨论了该领域仍存在的挑战，并提出了对未来研究方向的期望。

###### 索引词：

文本到 SQL、大型语言模型、数据库、自然语言理解

## I 引言

![参考说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：来自 BIRD 数据集的基于 LLM 的文本到 SQL 的示例。用户提出了一个关于足球联赛的问题。LLM 将问题和其对应数据库的模式作为输入，然后生成一个 SQL 查询作为输出。该 SQL 查询可以在数据库中执行，并检索内容“最多比赛的 5 个联赛”以回答用户的问题。

文本到 SQL（Text-to-SQL）是自然语言处理研究中的一个长期任务。其目标是将自然语言问题转换（翻译）为数据库可执行的 SQL 查询。图 [1](https://arxiv.org/html/2406.08426v3#S1.F1 "Figure 1 ‣ I Introduction ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL") 展示了一个基于大语言模型（LLM-based）的文本到 SQL 系统的示例。给定一个用户问题，比如“您能告诉我所有时间中比赛最多的 5 个联赛的名称以及这些联赛进行的比赛数量吗？”，LLM 将问题及其对应的数据库模式作为输入，然后生成一个 SQL 查询作为输出。这个 SQL 查询可以在数据库中执行，以检索相关内容来回答用户的问题。上述系统使用 LLMs 构建了一个自然语言接口到数据库（NLIDB）。由于 SQL 仍然是最广泛使用的编程语言之一，超过一半（51.52%）的专业开发者在工作中使用 SQL，值得注意的是，只有大约三分之一（35.29%）的开发者接受了系统的培训¹¹1[`survey.stackoverflow.co/2023`](https://survey.stackoverflow.co/2023)，NLIDB 使得非技术用户能够像专业数据库工程师一样访问结构化数据库[[1](https://arxiv.org/html/2406.08426v3#bib.bib1), [2](https://arxiv.org/html/2406.08426v3#bib.bib2)]，同时也加速了人机互动[[3](https://arxiv.org/html/2406.08426v3#bib.bib3)]。此外，在 LLMs 的研究热点中，文本到 SQL 通过将数据库中的现实内容纳入其中，提供了一个潜在的解决方案，以填补 LLMs 的知识空白，从而应对普遍存在的幻觉问题[[4](https://arxiv.org/html/2406.08426v3#bib.bib4), [5](https://arxiv.org/html/2406.08426v3#bib.bib5)]。文本到 SQL 的显著价值和潜力引发了一系列关于其与 LLMs 集成和优化的研究[[7](https://arxiv.org/html/2406.08426v3#bib.bib7), [8](https://arxiv.org/html/2406.08426v3#bib.bib8), [9](https://arxiv.org/html/2406.08426v3#bib.bib9), [10](https://arxiv.org/html/2406.08426v3#bib.bib10)]；因此，基于 LLM 的文本到 SQL 仍然是 NLP 和数据库社区中备受讨论的研究领域。

先前的研究在实现文本到 SQL 的转换方面取得了显著进展，并经历了漫长的演变过程。早期的努力主要基于设计良好的规则和模板[[11](https://arxiv.org/html/2406.08426v3#bib.bib11)]，特别适用于简单的数据库场景。近年来，由于基于规则的方法带来的高劳动成本[[12](https://arxiv.org/html/2406.08426v3#bib.bib12)]和数据库环境的日益复杂[[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [14](https://arxiv.org/html/2406.08426v3#bib.bib14), [15](https://arxiv.org/html/2406.08426v3#bib.bib15)]，为每种场景设计规则或模板变得越来越困难和不切实际。深度神经网络的发展推动了文本到 SQL 转换的进展[[16](https://arxiv.org/html/2406.08426v3#bib.bib16), [17](https://arxiv.org/html/2406.08426v3#bib.bib17)]，它可以自动学习用户问题到相应 SQL 的映射[[18](https://arxiv.org/html/2406.08426v3#bib.bib18), [19](https://arxiv.org/html/2406.08426v3#bib.bib19)]。随后，具有强大语义解析能力的预训练语言模型（PLMs）成为文本到 SQL 系统的新范式[[20](https://arxiv.org/html/2406.08426v3#bib.bib20)]，将其性能提升到了一个新的水平[[21](https://arxiv.org/html/2406.08426v3#bib.bib21), [22](https://arxiv.org/html/2406.08426v3#bib.bib22), [23](https://arxiv.org/html/2406.08426v3#bib.bib23)]。基于 PLM 的优化的增量研究，如表内容编码[[24](https://arxiv.org/html/2406.08426v3#bib.bib24), [19](https://arxiv.org/html/2406.08426v3#bib.bib19), [25](https://arxiv.org/html/2406.08426v3#bib.bib25)]和预训练[[20](https://arxiv.org/html/2406.08426v3#bib.bib20), [26](https://arxiv.org/html/2406.08426v3#bib.bib26)]，进一步推动了这一领域的进展。最近，通过上下文学习（ICL）[[8](https://arxiv.org/html/2406.08426v3#bib.bib8)]和微调（FT）[[10](https://arxiv.org/html/2406.08426v3#bib.bib10)] 实现文本到 SQL 转换的 LLM 基于的方法，达到了最新的精度，并且在设计良好的框架和比 PLMs 更强的理解能力方面表现更佳。

基于 LLM 的文本到 SQL 的整体实现细节可以分为三个方面：1\. 问题理解：自然语言问题是用户意图的语义表示，相应生成的 SQL 查询预计与之对齐；2\. 模式理解：模式提供了数据库的表和列结构，文本到 SQL 系统需要识别与用户问题匹配的目标组件；3\. SQL 生成：这涉及到结合上述解析，然后预测正确的语法以生成可执行的 SQL 查询，从而检索所需的答案。LLMs 已证明在基础实现方面表现良好 [[7](https://arxiv.org/html/2406.08426v3#bib.bib7), [27](https://arxiv.org/html/2406.08426v3#bib.bib27)]，得益于更丰富的训练语料库提供的更强大的语义解析能力 [[28](https://arxiv.org/html/2406.08426v3#bib.bib28), [29](https://arxiv.org/html/2406.08426v3#bib.bib29)]。对增强 LLMs 在问题理解 [[8](https://arxiv.org/html/2406.08426v3#bib.bib8), [9](https://arxiv.org/html/2406.08426v3#bib.bib9)]、模式理解 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30), [31](https://arxiv.org/html/2406.08426v3#bib.bib31)] 和 SQL 生成 [[32](https://arxiv.org/html/2406.08426v3#bib.bib32)]的进一步研究正在不断发布。

![参见说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2：从实现范式的角度来看，文本到 SQL 研究的演变过程草图。每个阶段都展示了两种代表性的实现技术。各阶段的时间戳并不完全准确；我们根据每种实现范式的代表性作品的发布时间设置了每个时间戳，误差大约为前后一年。该格式的灵感来源于 [[29](https://arxiv.org/html/2406.08426v3#bib.bib29)]。

{森林}

forked edges, for tree= grow=east, reversed=true, anchor=base west, parent anchor=east, child anchor=west, base=left, font=, rectangle, draw=hidden-draw, rounded corners, align=left, minimum width=1em, edge+=darkgray, line width=1pt, s sep=3pt, inner xsep=0pt, inner ysep=3pt, line width=0.8pt, ver/.style=rotate=90, child anchor=north, parent anchor=south, anchor=center, , [LLM-based Text-to-SQL, leaf-head, ver [ 数据集

(§[III-A](https://arxiv.org/html/2406.08426v3#S3.SS1 "III-A 数据集 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调查"))，leaf-datasets, text width=5em [ 原始

数据集

&

后注释

数据集, leaf-datasets, text width=6em [ 交叉-

领域，叶子数据集，文本宽度=5.5em [BIRD [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)], DuSQL [[34](https://arxiv.org/html/2406.08426v3#bib.bib34)], CoSQL [[35](https://arxiv.org/html/2406.08426v3#bib.bib35)], Spider [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)], WikiSQL [[14](https://arxiv.org/html/2406.08426v3#bib.bib14)], KaggleDBQA [[36](https://arxiv.org/html/2406.08426v3#bib.bib36)], ADVETA [[37](https://arxiv.org/html/2406.08426v3#bib.bib37)],

Spider-SS [[38](https://arxiv.org/html/2406.08426v3#bib.bib38)], Spider-CG [[38](https://arxiv.org/html/2406.08426v3#bib.bib38)], Spider-DK [[39](https://arxiv.org/html/2406.08426v3#bib.bib39)], Spider-SYN [[40](https://arxiv.org/html/2406.08426v3#bib.bib40)], Spider-Realistic [[41](https://arxiv.org/html/2406.08426v3#bib.bib41)], CSpider [[42](https://arxiv.org/html/2406.08426v3#bib.bib42)],

SParC [[43](https://arxiv.org/html/2406.08426v3#bib.bib43)], 模型节点数据集，文本宽度=43.5em] ] [ 知识

增强型，叶子数据集，文本宽度=5.5em [BIRD [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)], SQUALL [[44](https://arxiv.org/html/2406.08426v3#bib.bib44)], Spider-DK [[39](https://arxiv.org/html/2406.08426v3#bib.bib39)], 模型节点数据集，文本宽度=43.5em] ] [ 跨

语言，叶子数据集，文本宽度=5.5em [DuSQL [[34](https://arxiv.org/html/2406.08426v3#bib.bib34)], CSpider [[42](https://arxiv.org/html/2406.08426v3#bib.bib42)], 模型节点数据集，文本宽度=43.5em] ] [ 上下文

依赖，叶子数据集，文本宽度=5.5em [CoSQL [[35](https://arxiv.org/html/2406.08426v3#bib.bib35)], Spider-SS [[38](https://arxiv.org/html/2406.08426v3#bib.bib38)], Spider-CG [[38](https://arxiv.org/html/2406.08426v3#bib.bib38)], SparC [[43](https://arxiv.org/html/2406.08426v3#bib.bib43)], 模型节点数据集，文本宽度=43.5em] ] [ 鲁棒性，叶子数据集，文本宽度=5.5em [ADVETA [[37](https://arxiv.org/html/2406.08426v3#bib.bib37)], Spider-SYN [[40](https://arxiv.org/html/2406.08426v3#bib.bib40)], Spider-Realistic [[41](https://arxiv.org/html/2406.08426v3#bib.bib41)], 模型节点数据集，文本宽度=43.5em] ] ] ] [ 评估

指标

(§[III-B](https://arxiv.org/html/2406.08426v3#S3.SS2 "III-B 评估指标 ‣ III 基准与评估 ‣ 下一代数据库接口：基于 LLM 的文本到 SQL 调查"))，叶子指标，文本宽度=5em [ 内容

匹配

基于，叶子指标，文本宽度=6em [组件匹配 (CM) [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)], 精确匹配 (EM) [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)], 模型节点指标，文本宽度=50.7em] ] [ 执行

基于，叶子指标，文本宽度=6em [执行准确性 (EX) [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)], 有效效率分数 (VES) [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)], 模型节点指标，文本宽度=50.7em] ] ] [ 方法

(§[IV](https://arxiv.org/html/2406.08426v3#S4 "IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")), leaf-methods, text width=5em [ In-context

Learning

Paradigm

(§[IV-A](https://arxiv.org/html/2406.08426v3#S4.SS1 "IV-A In-context Learning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")), leaf-methods, text width=6em [ Trivial

Prompt, leaf-methods, text width=6.5em [ Zero-shot, modelnode-methods, text width=4.5em [[[7](https://arxiv.org/html/2406.08426v3#bib.bib7)], [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)], [[27](https://arxiv.org/html/2406.08426v3#bib.bib27)], [[45](https://arxiv.org/html/2406.08426v3#bib.bib45)], [[46](https://arxiv.org/html/2406.08426v3#bib.bib46)], [[47](https://arxiv.org/html/2406.08426v3#bib.bib47)], [[48](https://arxiv.org/html/2406.08426v3#bib.bib48)], [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)], [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)], [[50](https://arxiv.org/html/2406.08426v3#bib.bib50)], modelnode-methods, text width=36.2em]] [ Few-shot, modelnode-methods, text width=4.5em [[[33](https://arxiv.org/html/2406.08426v3#bib.bib33)], [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)], [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)], [[52](https://arxiv.org/html/2406.08426v3#bib.bib52)], [[53](https://arxiv.org/html/2406.08426v3#bib.bib53)], [[54](https://arxiv.org/html/2406.08426v3#bib.bib54)], [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)], [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)], [[32](https://arxiv.org/html/2406.08426v3#bib.bib32)], [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)] , modelnode-methods, text width=36.2em]] ] [ Decomposition, leaf-methods, text width=6.5em [Coder-Reviewer [[56](https://arxiv.org/html/2406.08426v3#bib.bib56)], DIN-SQL [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)], QDecomp [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)], C3 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)], MAC-SQL [[57](https://arxiv.org/html/2406.08426v3#bib.bib57)], DEA-SQL [[58](https://arxiv.org/html/2406.08426v3#bib.bib58)],

SGU-SQL [[32](https://arxiv.org/html/2406.08426v3#bib.bib32)], MetaSQL [[59](https://arxiv.org/html/2406.08426v3#bib.bib59)], PET-SQL [[60](https://arxiv.org/html/2406.08426v3#bib.bib60)], PURPLE [[61](https://arxiv.org/html/2406.08426v3#bib.bib61)], modelnode-methods, text width=42.5em] ] [ Prompt

Optimization, leaf-methods, text width=6.5em [DESEM+P [[62](https://arxiv.org/html/2406.08426v3#bib.bib62)], StructGPT [[63](https://arxiv.org/html/2406.08426v3#bib.bib63)], SD+SA+Voting [[52](https://arxiv.org/html/2406.08426v3#bib.bib52)], RAG+SP&DRC [[64](https://arxiv.org/html/2406.08426v3#bib.bib64)], C3 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)], DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)],

ODIS [[54](https://arxiv.org/html/2406.08426v3#bib.bib54)], ACT-SQL [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)], FUSED [[65](https://arxiv.org/html/2406.08426v3#bib.bib65)], DELLM [[31](https://arxiv.org/html/2406.08426v3#bib.bib31)], 模型节点方法、文本宽度=42.5em] ] [ 推理

增强、叶节点方法、文本宽度=6.5em[CoT [[51](https://arxiv.org/html/2406.08426v3#bib.bib51), [33](https://arxiv.org/html/2406.08426v3#bib.bib33), [9](https://arxiv.org/html/2406.08426v3#bib.bib9), [32](https://arxiv.org/html/2406.08426v3#bib.bib32)], QDecomp [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)], Least-to-Most [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)], SQL-PaLM [[53](https://arxiv.org/html/2406.08426v3#bib.bib53)], ACT-SQL [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)], POT [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)],

SQL-CRAFT [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)], FUXI [[66](https://arxiv.org/html/2406.08426v3#bib.bib66)], 模型节点方法、文本宽度=42.5em] ] [ 执行

精炼、叶节点方法、文本宽度=6.5em[MBR-Exec [[67](https://arxiv.org/html/2406.08426v3#bib.bib67)], Coder-Reviewer [[56](https://arxiv.org/html/2406.08426v3#bib.bib56)], LEVER [[68](https://arxiv.org/html/2406.08426v3#bib.bib68)], SELF-DEBUGGING [[48](https://arxiv.org/html/2406.08426v3#bib.bib48)], DESEM+P [[62](https://arxiv.org/html/2406.08426v3#bib.bib62)],

DIN-SQL [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)], SD+SA+Voting [[52](https://arxiv.org/html/2406.08426v3#bib.bib52)], SQL-PaLM [[53](https://arxiv.org/html/2406.08426v3#bib.bib53)], RAG+SP&DRC [[64](https://arxiv.org/html/2406.08426v3#bib.bib64)], C3 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)], MAC-SQL [[57](https://arxiv.org/html/2406.08426v3#bib.bib57)],

DELLM [[31](https://arxiv.org/html/2406.08426v3#bib.bib31)], SQL-CRAFT [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)], FUXI [[66](https://arxiv.org/html/2406.08426v3#bib.bib66)], PET-SQL [[60](https://arxiv.org/html/2406.08426v3#bib.bib60)], PURPLE [[61](https://arxiv.org/html/2406.08426v3#bib.bib61)], 模型节点方法、文本宽度=42.5em] ] ] [ 微调

范式

(§[IV-B](https://arxiv.org/html/2406.08426v3#S4.SS2 "IV-B Fine-tuning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")), 叶节点方法、文本宽度=6em [ Vanilla

微调、叶节点方法、文本宽度=6.5em [[[45](https://arxiv.org/html/2406.08426v3#bib.bib45)], [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)], [[50](https://arxiv.org/html/2406.08426v3#bib.bib50)], [[53](https://arxiv.org/html/2406.08426v3#bib.bib53)], 模型节点方法、文本宽度=42.5em] ] [ 增强

架构、叶节点方法、文本宽度=6.5em [CLLMs [[69](https://arxiv.org/html/2406.08426v3#bib.bib69)], 模型节点方法、文本宽度=42.5em] ] [ 预训练、叶节点方法、文本宽度=6.5em [CodeS [[10](https://arxiv.org/html/2406.08426v3#bib.bib10)], 模型节点方法、文本宽度=42.5em] ] [ 数据

增强方法、叶子方法，文本宽度=6.5em [DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)], Symbol-LLM [[50](https://arxiv.org/html/2406.08426v3#bib.bib50)], CodeS [[10](https://arxiv.org/html/2406.08426v3#bib.bib10)], StructLM [[70](https://arxiv.org/html/2406.08426v3#bib.bib70)], 模型节点方法，文本宽度=42.5em] ] [ 分解、叶子方法，文本宽度=6.5em [DTS-SQL [[71](https://arxiv.org/html/2406.08426v3#bib.bib71)], 模型节点方法，文本宽度=42.5em] ] ] ]

图 3：基于 LLM 的文本到 SQL 研究的分类树。每个节点中的展示顺序按发布时序排列。该格式改编自[[72](https://arxiv.org/html/2406.08426v3#bib.bib72)]。

尽管在文本到 SQL 研究中取得了显著进展，但仍然存在几个挑战，阻碍了鲁棒且通用的文本到 SQL 系统的发展[[73](https://arxiv.org/html/2406.08426v3#bib.bib73)]。近年来的相关工作调查了深度学习方法中的文本到 SQL 系统，并提供了对以前深度神经网络和 PLM 基础研究的见解[[74](https://arxiv.org/html/2406.08426v3#bib.bib74), [2](https://arxiv.org/html/2406.08426v3#bib.bib2), [29](https://arxiv.org/html/2406.08426v3#bib.bib29)]。在本次调查中，我们旨在跟上最新的进展，并提供对基于 LLM 的文本到 SQL 当前最先进模型和方法的全面回顾。我们首先介绍与文本到 SQL 相关的基本概念和挑战，强调这一任务在各个领域中的重要性。然后，我们深入探讨文本到 SQL 系统的实现范式演变，讨论该领域的关键进展和突破。在概述之后，我们详细介绍和分析了整合 LLM 的文本到 SQL 的最新进展。具体来说，我们的调查涵盖了与基于 LLM 的文本到 SQL 相关的一系列内容，包括：

+   •

    数据集与基准测试：我们详细介绍了用于评估基于 LLM 的文本到 SQL 系统的常用数据集和基准测试。我们讨论了它们的特性、复杂性以及它们对文本到 SQL 开发和评估所带来的挑战。

+   •

    评估指标：我们介绍了用于评估基于 LLM 的文本到 SQL 系统性能的评估指标，包括内容匹配和执行基础的范式。然后我们简要介绍了每个指标的特点。

+   •

    方法与模型：我们对用于基于 LLM 的文本到 SQL 的不同方法和模型进行了系统分析，包括上下文学习和基于微调的范式。我们讨论了它们的实现细节、优势，以及在不同实现视角下特定于文本到 SQL 任务的适应情况。

+   •

    期望与未来方向：我们讨论了基于 LLM 的文本到 SQL 的剩余挑战和限制，如现实世界的鲁棒性、计算效率、数据隐私和扩展。我们还概述了潜在的未来研究方向和改进与优化的机会。

我们希望这项调查提供最近研究的清晰概述，并激发未来的研究。图[3](https://arxiv.org/html/2406.08426v3#S1.F3 "Figure 3 ‣ I Introduction ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")展示了一个总结我们调查结构和内容的分类树。

## II 概述

文本到 SQL 是一个将自然语言问题转换为可以在关系数据库中执行的 SQL 查询的任务。正式地，给定一个用户问题$\mathcal{Q}$（也称为用户查询、自然语言问题等）和一个数据库模式$\mathcal{S}$，该任务的目标是生成一个 SQL 查询$Y$，从数据库中检索所需内容以回答用户问题。文本到 SQL 有潜力通过允许用户使用自然语言与数据库交互，而无需专门的 SQL 编程知识，来使数据访问民主化[[75](https://arxiv.org/html/2406.08426v3#bib.bib75)]。这可以使各个领域受益，例如商业智能、客户支持和科学研究，通过使非技术用户轻松检索目标内容并促进更高效的数据分析。

### II-A 文本到 SQL 的挑战

文本到 SQL 实施的技术挑战可以总结如下：

#### II-A1 语言复杂性和模糊性

自然语言问题通常包含复杂的语言表示，例如嵌套子句、指代和省略，这使得准确映射到对应的 SQL 查询部分具有挑战性[[41](https://arxiv.org/html/2406.08426v3#bib.bib41)]。此外，自然语言本质上是模糊的，对于给定用户问题有多种可能的表示[[76](https://arxiv.org/html/2406.08426v3#bib.bib76), [77](https://arxiv.org/html/2406.08426v3#bib.bib77)]。解决这些模糊性并理解用户问题的意图需要深刻的自然语言理解能力和结合上下文与领域知识的能力[[33](https://arxiv.org/html/2406.08426v3#bib.bib33)]。

#### II-A2 模式理解和表示

为了生成准确的 SQL 查询，文本到 SQL 系统需要全面理解数据库模式，包括表名、列名和各表之间的关系。然而，数据库模式可能复杂且在不同领域中有显著差异[[13](https://arxiv.org/html/2406.08426v3#bib.bib13)]。以可以被文本到 SQL 模型有效利用的方式表示和编码模式信息是一项具有挑战性的任务。

#### II-A3 罕见和复杂的 SQL 操作

一些 SQL 查询涉及罕见或复杂的操作和语法，在具有挑战性的场景中，例如嵌套子查询、外连接和窗口函数。这些操作在训练数据中不常见，给文本到 SQL 系统的准确生成带来了挑战。设计能够推广到各种 SQL 操作的模型，包括罕见和复杂的场景，是一个重要的考虑因素。

#### II-A4 跨域泛化

文本到 SQL 系统往往难以跨各种数据库场景和领域泛化。针对特定领域训练的模型可能在其他领域提出的问题上表现不佳，因为词汇、数据库模式结构和问题模式的多样性。开发能够有效泛化到新领域的系统，并且只需最少的领域特定训练数据或微调适应，是一个重大挑战 [[78](https://arxiv.org/html/2406.08426v3#bib.bib78)]。

### II-B 进化过程

文本到 SQL 的研究领域在自然语言处理（NLP）社区经历了显著的进展，从基于规则的方法发展到基于深度学习的方法，最近更是整合了预训练语言模型（PLMs）和大型语言模型（LLMs），演变过程的概要见图 [2](https://arxiv.org/html/2406.08426v3#S1.F2 "Figure 2 ‣ I Introduction ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")。

#### II-B1 基于规则的方法

早期的文本到 SQL 系统严重依赖于基于规则的方法 [[11](https://arxiv.org/html/2406.08426v3#bib.bib11), [12](https://arxiv.org/html/2406.08426v3#bib.bib12), [26](https://arxiv.org/html/2406.08426v3#bib.bib26)]，通过手动制定的规则和启发式方法将自然语言问题映射到 SQL 查询。这些方法通常涉及广泛的特征工程和特定领域知识。尽管基于规则的方法在某些简单领域取得了成功，但它们缺乏处理多样化和复杂问题所需的灵活性和泛化能力。

#### II-B2 基于深度学习的方法

随着深度神经网络、序列到序列模型和编码器-解码器结构的兴起，如 LSTMs [[79](https://arxiv.org/html/2406.08426v3#bib.bib79)] 和 transformers [[17](https://arxiv.org/html/2406.08426v3#bib.bib17)]，这些模型被调整用于从自然语言输入生成 SQL 查询 [[80](https://arxiv.org/html/2406.08426v3#bib.bib80), [19](https://arxiv.org/html/2406.08426v3#bib.bib19)]。通常，RYANSQL [[19](https://arxiv.org/html/2406.08426v3#bib.bib19)] 引入了中间表示和基于草图的槽填充等技术，以处理复杂的问题并提高跨领域泛化能力。最近，研究人员通过利用模式依赖图来捕捉数据库元素之间的关系，引入了图神经网络 (GNNs) 用于文本到 SQL 任务 [[18](https://arxiv.org/html/2406.08426v3#bib.bib18), [81](https://arxiv.org/html/2406.08426v3#bib.bib81)]。

#### II-B3 基于 PLM 的实现

预训练语言模型 (PLMs) 已成为解决文本到 SQL 的强大方案，利用了在预训练过程中捕捉的大量语言知识和语义理解。早期在文本到 SQL 中采用 PLMs 主要集中于在标准文本到 SQL 数据集上对现成的 PLMs 进行微调，如 BERT [[24](https://arxiv.org/html/2406.08426v3#bib.bib24)] 和 RoBERTa [[82](https://arxiv.org/html/2406.08426v3#bib.bib82)]。这些 PLMs 在大量训练语料上预训练，捕捉了丰富的语义表示和语言理解能力。通过在文本到 SQL 任务上进行微调，研究人员旨在利用 PLMs 的语义和语言理解能力生成准确的 SQL 查询 [[80](https://arxiv.org/html/2406.08426v3#bib.bib80), [20](https://arxiv.org/html/2406.08426v3#bib.bib20), [83](https://arxiv.org/html/2406.08426v3#bib.bib83)]。另一研究方向则关注于将模式信息纳入 PLMs，以提高其对数据库结构的理解能力，并使其能够生成更可执行的 SQL 查询。模式感知 PLMs 被设计用于捕捉数据库结构中存在的关系和约束 [[21](https://arxiv.org/html/2406.08426v3#bib.bib21)]。

#### II-B4 基于 LLM 的实现

大型语言模型（LLMs），如 GPT 系列 [[84](https://arxiv.org/html/2406.08426v3#bib.bib84), [85](https://arxiv.org/html/2406.08426v3#bib.bib85), [86](https://arxiv.org/html/2406.08426v3#bib.bib86)]，近年来由于其生成连贯流畅文本的能力而受到广泛关注。研究人员已经开始探索 LLMs 在文本到 SQL 中的潜力，通过利用其广泛的知识储备和优越的生成能力 [[7](https://arxiv.org/html/2406.08426v3#bib.bib7), [9](https://arxiv.org/html/2406.08426v3#bib.bib9)]。这些方法通常涉及提示工程，以引导专有 LLMs 进行 SQL 生成 [[47](https://arxiv.org/html/2406.08426v3#bib.bib47)]，或对开源 LLMs 进行文本到 SQL 数据集上的微调 [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)]。

LLM 在文本到 SQL 中的整合仍然是一个新兴的研究领域，具有巨大的进一步探索和改进的潜力。研究人员正在探索更好地利用 LLM 的知识和推理能力的方法，整合领域特定知识 [[33](https://arxiv.org/html/2406.08426v3#bib.bib33), [31](https://arxiv.org/html/2406.08426v3#bib.bib31)]，并开发更高效的微调策略 [[10](https://arxiv.org/html/2406.08426v3#bib.bib10)]。随着该领域的不断发展，我们预计会出现更多先进和优越的基于 LLM 的实现，这将把文本到 SQL 的性能和泛化能力提升到新的高度。

## III 基准与评估

在本节中，我们介绍了文本到 SQL 的基准测试，涵盖了著名的数据集和评估指标。

表 I：按发布时间排序的文本到 SQL 的著名数据集的统计和分析。原始数据集表示该数据集设计了相应的数据库，而后注释数据集则涉及在现有数据集和数据库中注释新组件，而不是发布新的数据库。

| 原始数据集 | 发布时间 | 示例数量 | 数据库数量 | 表/数据库 | 行/数据库 | 特征 |
| --- | --- | --- | --- | --- | --- | --- |
| BIRD [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | 2023 年 5 月 | 12,751 | 95 | 7.3 | 549K | 跨领域，知识增强 |
| KaggleDBQA [[36](https://arxiv.org/html/2406.08426v3#bib.bib36)] | 2021 年 6 月 | 272 | 8 | 2.3 | 280K | 跨领域 |
| DuSQL [[34](https://arxiv.org/html/2406.08426v3#bib.bib34)] | 2020 年 11 月 | 23,797 | 200 | 4.1 | - | 跨领域，跨语言 |
| SQUALL [[44](https://arxiv.org/html/2406.08426v3#bib.bib44)] | 2020 年 10 月 | 11,468 | 1,679 | 1 | - | 知识增强 |
| CoSQL [[35](https://arxiv.org/html/2406.08426v3#bib.bib35)] | 2019 年 9 月 | 15,598 | 200 | - | - | 跨领域，上下文依赖 |
| Spider [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | 2018 年 9 月 | 10,181 | 200 | 5.1 | 2K | 跨领域 |
| WikiSQL [[14](https://arxiv.org/html/2406.08426v3#bib.bib14)] | 2017 年 8 月 | 80,654 | 26,521 | 1 | 17 | 跨领域 |
| 后注释数据集 | 发布时间 | 源数据集 | 特殊设置 | 特性 |
| ADVETA [[37](https://arxiv.org/html/2406.08426v3#bib.bib37)] | 2022 年 12 月 | Spider 等 | 对抗表格扰动 | 鲁棒性 |
| Spider-SS&CG [[38](https://arxiv.org/html/2406.08426v3#bib.bib38)] | 2022 年 5 月 | Spider | 将示例拆分为子示例 | 上下文依赖 |
| Spider-DK [[39](https://arxiv.org/html/2406.08426v3#bib.bib39)] | 2021 年 9 月 | Spider | 添加领域知识 | 知识增强 |
| Spider-SYN [[40](https://arxiv.org/html/2406.08426v3#bib.bib40)] | 2021 年 6 月 | Spider | 手动同义词替换 | 鲁棒性 |
| Spider-Realistic [[41](https://arxiv.org/html/2406.08426v3#bib.bib41)] | 2020 年 10 月 | Spider | 在问题中移除列名 | 鲁棒性 |
| CSpider [[42](https://arxiv.org/html/2406.08426v3#bib.bib42)] | 2019 年 9 月 | Spider | Spider 的中文版本 | 跨语言 |
| SParC [[43](https://arxiv.org/html/2406.08426v3#bib.bib43)] | 2019 年 6 月 | Spider | 注释对话内容 | 上下文依赖 |

### III-A 数据集

如表[I](https://arxiv.org/html/2406.08426v3#S3.T1 "TABLE I ‣ III Benchmarks & evalution ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")所示，我们将数据集分为“原始数据集”和“后注释数据集”，具体依据是它们是否与原始数据集和数据库一同发布，或是通过对现有数据集和数据库进行特定设置而创建的。对于原始数据集，我们提供详细的分析，包括示例数量、数据库数量、每个数据库中的表格数量以及每个数据库中的行数。对于后注释数据集，我们识别其源数据集并描述应用于它们的特殊设置。为了说明每个数据集的潜在机会，我们根据其特性进行了注释。注释列在表[I](https://arxiv.org/html/2406.08426v3#S3.T1 "TABLE I ‣ III Benchmarks & evalution ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")的最右侧一列中，下面我们将详细讨论这些内容。

#### III-A1 跨领域数据集

这指的是背景信息来自不同领域的多种数据库的数据集。由于现实世界中的文本到 SQL 应用通常涉及来自多个领域的数据库，因此大多数原始的文本到 SQL 数据集[[14](https://arxiv.org/html/2406.08426v3#bib.bib14)、[13](https://arxiv.org/html/2406.08426v3#bib.bib13)、[35](https://arxiv.org/html/2406.08426v3#bib.bib35)、[34](https://arxiv.org/html/2406.08426v3#bib.bib34)、[36](https://arxiv.org/html/2406.08426v3#bib.bib36)、[33](https://arxiv.org/html/2406.08426v3#bib.bib33)]以及后期注释的数据集[[43](https://arxiv.org/html/2406.08426v3#bib.bib43)、[42](https://arxiv.org/html/2406.08426v3#bib.bib42)、[39](https://arxiv.org/html/2406.08426v3#bib.bib39)、[40](https://arxiv.org/html/2406.08426v3#bib.bib40)、[41](https://arxiv.org/html/2406.08426v3#bib.bib41)、[37](https://arxiv.org/html/2406.08426v3#bib.bib37)、[38](https://arxiv.org/html/2406.08426v3#bib.bib38)]都是跨领域设置的，以适应跨领域应用的要求。

#### III-A2 知识增强数据集

近年来，将领域特定知识融入文本到 SQL 任务中的兴趣显著增加。BIRD[[33](https://arxiv.org/html/2406.08426v3#bib.bib33)]利用人类数据库专家为每个文本到 SQL 样本注释外部知识，这些知识被分类为数值推理知识、领域知识、同义词知识和值说明。类似地，Spider-DK[[39](https://arxiv.org/html/2406.08426v3#bib.bib39)]定义并添加了五种类型的领域知识，用于 Spider 数据集的人工整理版本[[13](https://arxiv.org/html/2406.08426v3#bib.bib13)]：选择列提及的遗漏、需要简单推理、单元值词中的同义词替换、一个非单元值词生成条件、以及容易与其他领域冲突。这两项研究发现，人类注释的知识显著提高了对需要外部领域知识的样本的 SQL 生成性能。此外，SQUALL[[44](https://arxiv.org/html/2406.08426v3#bib.bib44)]手动注释了自然语言问题中的词与 SQL 中实体之间的对齐，提供了比其他数据集更细粒度的监督。

#### III-A3 上下文依赖数据集

SParC [[43](https://arxiv.org/html/2406.08426v3#bib.bib43)] 和 CoSQL [[35](https://arxiv.org/html/2406.08426v3#bib.bib35)] 通过构建对话式数据库查询系统来探索上下文依赖的 SQL 生成。与传统的文本到 SQL 数据集只有一个问题-SQL 对的示例不同，SParC 将 Spider 数据集中的问题-SQL 示例分解为多个子问题-SQL 对，以构建一个模拟和有意义的互动，包括帮助 SQL 生成的相关子问题和增强数据多样性的无关子问题。相比之下，CoSQL 涉及自然语言中的对话交互，模拟现实世界场景以增加复杂性和多样性。此外，Spider-SS&CG [[38](https://arxiv.org/html/2406.08426v3#bib.bib38)] 将 Spider 数据集中的自然语言问题 [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] 分割成多个子问题和子 SQL，展示了对这些子示例进行训练可以提高文本到 SQL 系统在分布外样本上的泛化能力。

#### III-A4 稳健性数据集

评估文本到 SQL 系统在污染或扰动的数据库内容（例如模式和表）下的准确性对于评估鲁棒性至关重要。Spider-Realistic [[41](https://arxiv.org/html/2406.08426v3#bib.bib41)] 从自然语言问题中去除显式模式相关词汇，而 Spider-SYN [[40](https://arxiv.org/html/2406.08426v3#bib.bib40)] 则用手动选择的同义词替换这些词汇。ADVETA [[37](https://arxiv.org/html/2406.08426v3#bib.bib37)] 引入了对抗表扰动（ATP），通过用误导性替代品替换原始列名和插入与高语义关联但低语义等效的新列来扰动表。这些扰动导致准确性显著下降，因为低鲁棒性的文本到 SQL 系统可能会因自然语言问题和数据库实体之间的错误匹配而受到误导。

#### III-A5 跨语言数据集

SQL 关键字、函数名称、表名称和列名称通常用英语书写，这给其他语言的应用带来了挑战。CSpider [[42](https://arxiv.org/html/2406.08426v3#bib.bib42)] 将 Spider 数据集翻译成中文，识别出中文问题与英文数据库内容之间的词语分割和跨语言匹配的新挑战。DuSQL [[34](https://arxiv.org/html/2406.08426v3#bib.bib34)] 引入了一个实用的文本到 SQL 数据集，提供了中文问题和英文及中文数据库内容。

### III-B 评估指标

我们介绍了四种广泛使用的文本到 SQL 任务的评估指标：基于 SQL 内容匹配的组件匹配和精确匹配，以及基于执行结果的执行准确率和有效性得分。

#### III-B1 基于内容匹配的指标

SQL 内容匹配指标侧重于根据结构和语法相似性比较预测的 SQL 查询与实际 SQL 查询。

+   •

    组件匹配 (CM) [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] 通过使用 F1 得分测量预测的 SQL 组件与实际 SQL 组件之间的精确匹配来评估文本到 SQL 系统的性能——包括 SELECT、WHERE、GROUP BY、ORDER BY 和 KEYWORDS。每个组件被分解为子组件集合，并进行精确匹配的比较，考虑到没有顺序约束的 SQL 组件。

+   •

    精确匹配 (EM) [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] 测量预测 SQL 查询与实际 SQL 查询完全相同的示例的百分比。仅当预测 SQL 查询的所有组件（如 CM 所述）与实际查询的组件完全匹配时，预测 SQL 被视为正确。

#### III-B2 基于执行的指标

执行结果指标通过比较在目标数据库上执行查询所获得的结果与预期结果来评估生成的 SQL 查询的正确性。

+   •

    执行准确性 (EX) [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] 通过在相应数据库中执行预测 SQL 查询，并将执行结果与实际查询获得的结果进行比较，来衡量预测 SQL 查询的正确性。

+   •

    有效效率得分 (VES) [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)] 被定义为测量有效 SQL 查询的效率。有效 SQL 查询是指其执行结果完全匹配实际结果的预测 SQL 查询。具体而言，VES 评估预测 SQL 查询的效率和准确性。对于具有 $N$ 个示例的文本数据集，可以通过以下公式计算 VES：

    |  | $\text{VES}=\frac{1}{N}\sum_{n=1}^{N}\mathbbm{1}(V_{n},\hat{V}_{n})\cdot\textbf{R}(Y_{n},\hat{Y}_{n}),$ |  | (1) |
    | --- | --- | --- | --- |

    其中 $\hat{Y}_{n}$ 和 $\hat{V}_{n}$ 是预测的 SQL 查询及其执行结果，$Y_{n}$ 和 $V_{n}$ 是实际 SQL 查询及其对应的执行结果。$\mathbbm{1}(V_{n},\hat{V}_{n})$ 是一个指示函数，其中：

    |  | $\mathbbm{1}(V_{n},\hat{V}_{n})=\begin{cases}1,V_{n}=\hat{V}_{n}\\ 0,V_{n}\neq\hat{V}_{n}\end{cases}$ |  | (2) |
    | --- | --- | --- | --- |

    然后，$\textbf{R}(Y_{n},\hat{Y}_{n})=\sqrt{E(Y_{n})/E(\hat{Y}_{n})}$ 表示预测的 SQL 查询相对于实际查询的相对执行效率，其中 $E(\cdot)$ 是数据库中每个 SQL 的执行时间。BIRD 基准 [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)] 通过计算每个示例 100 次运行的 $\textbf{R}(Y_{n},\hat{Y}_{n})$ 的平均值来确保此指标的稳定性。

最近的大多数基于 LLM 的文本到 SQL 研究集中在这四个数据集上：Spider [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)]，Spider-Realistic [[41](https://arxiv.org/html/2406.08426v3#bib.bib41)]，Spider-SYN [[40](https://arxiv.org/html/2406.08426v3#bib.bib40)]，和 BIRD [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)]；以及这三种评估方法：EM，EX 和 VES，我们将在以下分析中重点关注它们。

## IV 方法

当前基于 LLM 的应用程序的实现主要依赖于上下文学习（ICL）（提示工程）[[87](https://arxiv.org/html/2406.08426v3#bib.bib87)、[88](https://arxiv.org/html/2406.08426v3#bib.bib88)、[89](https://arxiv.org/html/2406.08426v3#bib.bib89)] 和微调（FT）[[90](https://arxiv.org/html/2406.08426v3#bib.bib90)、[91](https://arxiv.org/html/2406.08426v3#bib.bib91)]范式，因为强大的专有模型和设计良好的开源模型正大量发布[[86](https://arxiv.org/html/2406.08426v3#bib.bib86)、[45](https://arxiv.org/html/2406.08426v3#bib.bib45)、[92](https://arxiv.org/html/2406.08426v3#bib.bib92)、[93](https://arxiv.org/html/2406.08426v3#bib.bib93)、[94](https://arxiv.org/html/2406.08426v3#bib.bib94)、[95](https://arxiv.org/html/2406.08426v3#bib.bib95)]。基于 LLM 的文本到 SQL 系统遵循这些范式进行实现。在本调查中，我们将相应地讨论这些范式。

### IV-A 上下文学习

通过广泛且广为认可的研究，提示工程已被证明在 LLM 的性能中发挥了决定性作用[[96](https://arxiv.org/html/2406.08426v3#bib.bib96)、[28](https://arxiv.org/html/2406.08426v3#bib.bib28)]，同时也影响了不同提示风格下的 SQL 生成[[9](https://arxiv.org/html/2406.08426v3#bib.bib9)、[46](https://arxiv.org/html/2406.08426v3#bib.bib46)]。因此，在上下文学习（ICL）范式中开发文本到 SQL 方法对实现有前途的改进具有重要价值。LLM 基础的文本到 SQL 过程生成可执行 SQL 查询$Y$可以被表述为：

|  | $Y=f(\mathcal{Q},\mathcal{S},\mathcal{I}\mid\theta),$ |  | (3) |
| --- | --- | --- | --- |

其中，$\mathcal{Q}$ 代表用户问题。$\mathcal{S}$ 是数据库模式/内容，可以分解为 $\mathcal{S}=\langle\mathcal{C},\mathcal{T},\mathcal{K}\rangle$，其中 $\mathcal{C}=\{c_{1},c_{2},...\}$ 和表 $\mathcal{T}=\{t_{1},t_{2},...\}$ 代表各种列和表的集合，$\mathcal{K}$ 是潜在的外部知识（例如外键关系 [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)]，模式链接 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)] 和领域知识 [[33](https://arxiv.org/html/2406.08426v3#bib.bib33), [31](https://arxiv.org/html/2406.08426v3#bib.bib31)]）。$\mathcal{I}$ 代表文本到 SQL 任务的指令，它提供了指示性指导来触发 LLM 生成准确的 SQL 查询。$f(\cdot\mid\theta)$ 是一个具有参数 $\theta$ 的 LLM。在上下文学习（ICL）范式中，我们利用一个现成的文本到 SQL 模型（即，模型的参数 $\theta$ 固定）来生成预测的 SQL 查询。在 ICL 范式中采用了多种精心设计的方法用于基于 LLM 的文本到 SQL 任务。我们将它们分为五类 $\mathbf{C}_{0:4}$，包括 $\mathbf{C}_{0}$-简单提示，$\mathbf{C}_{1}$-分解，$\mathbf{C}_{2}$-提示优化，$\mathbf{C}_{3}$-推理增强和 $\mathbf{C}_{4}$-执行优化，每类的代表性方法见表 [II](https://arxiv.org/html/2406.08426v3#S4.T2 "TABLE II ‣ 𝐂₀-Trivial Prompt ‣ IV-A In-context Learning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")。

#### $\mathbf{C}_{0}$-简单提示

通过大量数据训练，LLMs 在不同下游任务中具有强大的整体能力，能够处理零-shot 和少-shot 提示 [[97](https://arxiv.org/html/2406.08426v3#bib.bib97)，[90](https://arxiv.org/html/2406.08426v3#bib.bib90)，[98](https://arxiv.org/html/2406.08426v3#bib.bib98)]，这在现实世界应用中得到了广泛认可和使用。在我们的调查中，我们将上述提示方法中没有经过精心设计的框架的归类为简单提示（基础提示工程）。如上所述，公式 [3](https://arxiv.org/html/2406.08426v3#S4.E3 "In IV-A In-context Learning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL") 公式化了基于 LLM 的文本到 SQL 过程，也可以代表零-shot 提示。整体输入 $\mathcal{P}_{0}$ 可以通过将 $\mathcal{I}$、$\mathcal{S}$ 和 $\mathcal{Q}$ 连接得到：

|  | $\mathcal{P}_{0}=\mathcal{I}\oplus\mathcal{S}\oplus\mathcal{Q}.$ |  | (4) |
| --- | --- | --- | --- |

为了规范提示过程，OpenAI 演示²²2 按照 OpenAI 平台的官方文档设置的提示风格: [`platform.openai.com/examples/default-sql-translate`](https://platform.openai.com/examples/default-sql-translate) 被定为文本到 SQL 的标准（平凡）提示 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)]。

表 II：用于基于 LLM 的文本到 SQL 的上下文学习（ICL）的典型方法。现有方法的完整表格，包括分类 $\mathbf{C}_{1:4}$ 和更多细节，列在表 [III](https://arxiv.org/html/2406.08426v3#S4.T3 "TABLE III ‣ 𝐂₀-Trivial Prompt ‣ IV-A In-context Learning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")。

| 方法 | 被采用 | 应用的 LLMs |
| --- | --- | --- |
| $\mathbf{C}_{0}$-平凡提示 | Zero-shot [[7](https://arxiv.org/html/2406.08426v3#bib.bib7)] | ChatGPT |
| Few-shot [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] | ChatGPT |
| $\mathbf{C}_{1}$-分解 | DIN-SQL [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)] | GPT-4 |
| $\mathbf{C}_{2}$-提示优化 | DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] | GPT-4 |
| $\mathbf{C}_{3}$-推理增强 | ACT-SQL [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)] | GPT-4 |
| $\mathbf{C}_{4}$-执行优化 | LEVER [[68](https://arxiv.org/html/2406.08426v3#bib.bib68)] | Codex |

表 III：用于基于 LLM 的文本到 SQL 的上下文学习（ICL）范式的设计良好方法，按发布顺序排列。这些方法根据其实现视角分为四类：$\mathbf{C}_{1}$-分解，$\mathbf{C}_{2}$-提示优化，$\mathbf{C}_{3}$-推理增强，$\mathbf{C}_{4}$-执行优化。将分别介绍多个类别中的方法。^* 相应方法中有多个应用的 LLMs，我们展示了具有代表性表现的选定 LLM。^† CoT 方法在多个场所报道：NeurIPS’23 [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)], EMNLP’23 [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)], VLDB’24 [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)], arXiv’24 [[32](https://arxiv.org/html/2406.08426v3#bib.bib32)]。

| 方法 | 应用的 LLMs | 数据集 | 指标 | $\mathbf{C}_{1}$ | $\mathbf{C}_{2}$ | $\mathbf{C}_{3}$ | $\mathbf{C}_{4}$ | 发布时间 | 发表场所 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| MBR-Exec [[67](https://arxiv.org/html/2406.08426v3#bib.bib67)] | Codex | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  |  |  | ✓ | 2022 年 4 月 | EMNLP’22 |
| Coder-Reviewer [[56](https://arxiv.org/html/2406.08426v3#bib.bib56)] | Codex | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX | ✓ |  |  | ✓ | 2022 年 11 月 | ICML’23 |
| LEVER [[68](https://arxiv.org/html/2406.08426v3#bib.bib68)] | Codex | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  |  |  | ✓ | 2023 年 2 月 | ICML’23 |
| SELF-DEBUGGING [[48](https://arxiv.org/html/2406.08426v3#bib.bib48)] | StarCoder^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  |  |  | ✓ | 2023 年 4 月 | ICLR’24 |
| DESEM+P [[62](https://arxiv.org/html/2406.08426v3#bib.bib62)] | ChatGPT | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [40](https://arxiv.org/html/2406.08426v3#bib.bib40)] | EX |  | ✓ |  | ✓ | 2023 年 4 月 | PRICAI’23 |
| DIN-SQL [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)] | GPT-4^* | [[33](https://arxiv.org/html/2406.08426v3#bib.bib33), [13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX, EM, VES | ✓ |  |  | ✓ | 2023 年 4 月 | NeurIPS’23 |
| CoT [[51](https://arxiv.org/html/2406.08426v3#bib.bib51), [33](https://arxiv.org/html/2406.08426v3#bib.bib33), [9](https://arxiv.org/html/2406.08426v3#bib.bib9), [32](https://arxiv.org/html/2406.08426v3#bib.bib32)] | GPT-4 | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [41](https://arxiv.org/html/2406.08426v3#bib.bib41), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | EX, VES |  |  | ✓ |  | 2023 年 5 月 | 多个场合^† |
| StructGPT [[63](https://arxiv.org/html/2406.08426v3#bib.bib63)] | ChatGPT^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [40](https://arxiv.org/html/2406.08426v3#bib.bib40), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)] | EX |  | ✓ |  |  | 2023 年 5 月 | EMNLP’23 |
| SD+SA+Voting [[52](https://arxiv.org/html/2406.08426v3#bib.bib52)] | ChatGPT^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [40](https://arxiv.org/html/2406.08426v3#bib.bib40), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)] | EX |  | ✓ |  | ✓ | 2023 年 5 月 | EMNLP’23 发现 |
| QDecomp [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)] | Codex | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)] | EX | ✓ |  | ✓ |  | 2023 年 5 月 | EMNLP’23 |
| Least-to-Most [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)] | Codex | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  |  | ✓ |  | 2023 年 5 月 | EMNLP’23 |
| SQL-PaLM [[53](https://arxiv.org/html/2406.08426v3#bib.bib53)] | PaLM-2 | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  |  | ✓ | ✓ | 2023 年 5 月 | arXiv’23 |
| RAG+SP&DRC [[64](https://arxiv.org/html/2406.08426v3#bib.bib64)] | ChatGPT | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  | ✓ |  | ✓ | 2023 年 7 月 | ICONIP’23 |
| C3 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)] | ChatGPT | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX | ✓ | ✓ |  | ✓ | 2023 年 7 月 | arXiv’23 |
| DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)] | EX, EM, VES |  | ✓ |  |  | 2023 年 8 月 | VLDB’24 |
| ODIS [[54](https://arxiv.org/html/2406.08426v3#bib.bib54)] | Codex^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  | ✓ |  |  | 2023 年 10 月 | EMNLP’23 Findings |
| ACT-SQL [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [40](https://arxiv.org/html/2406.08426v3#bib.bib40)] | EX, EM |  | ✓ | ✓ |  | 2023 年 10 月 | EMNLP’23 Findings |
| MAC-SQL [[57](https://arxiv.org/html/2406.08426v3#bib.bib57)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | EX, EM, VES | ✓ |  |  | ✓ | 2023 年 12 月 | arXiv’23 |
| DEA-SQL [[58](https://arxiv.org/html/2406.08426v3#bib.bib58)] | GPT-4 | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX | ✓ |  |  |  | 2024 年 2 月 | ACL’24 Findings |
| FUSED [[65](https://arxiv.org/html/2406.08426v3#bib.bib65)] | ChatGPT^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX |  | ✓ |  |  | 2024 年 2 月 | arXiv’24 |
| DELLM [[31](https://arxiv.org/html/2406.08426v3#bib.bib31)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | EX, VES |  | ✓ |  | ✓ | 2024 年 2 月 | ACL’24 Findings |
| SGU-SQL [[32](https://arxiv.org/html/2406.08426v3#bib.bib32)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | EX, EM | ✓ |  |  |  | 2024 年 2 月 | arXiv’24 |
| POT [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | EX |  |  | ✓ |  | 2024 年 2 月 | arXiv’24 |
| SQL-CRAFT [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | EX |  |  | ✓ | ✓ | 2024 年 2 月 | arXiv’24 |
| FUXI [[66](https://arxiv.org/html/2406.08426v3#bib.bib66)] | GPT-4^* | [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | EX |  |  | ✓ | ✓ | 2024 年 2 月 | arXiv’24 |
| MetaSQL [[59](https://arxiv.org/html/2406.08426v3#bib.bib59)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX, EM | ✓ |  |  |  | 2024 年 2 月 | ICDE’24 |
| PET-SQL [[60](https://arxiv.org/html/2406.08426v3#bib.bib60)] | GPT-4 | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | EX | ✓ |  |  | ✓ | 2024 年 3 月 | arXiv’24 |
| PURPLE [[61](https://arxiv.org/html/2406.08426v3#bib.bib61)] | GPT-4^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [40](https://arxiv.org/html/2406.08426v3#bib.bib40), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)] | EX, EM | ✓ |  |  | ✓ | 2024 年 3 月 | ICDE’24 |

Zero-shot: 许多研究工作[[7](https://arxiv.org/html/2406.08426v3#bib.bib7), [27](https://arxiv.org/html/2406.08426v3#bib.bib27), [46](https://arxiv.org/html/2406.08426v3#bib.bib46)] 利用零样本提示，主要研究提示构建风格的影响以及各种 LLM 在文本到 SQL 的零样本性能。作为实证评估，[[7](https://arxiv.org/html/2406.08426v3#bib.bib7)] 评估了不同早期开发的 LLM[[99](https://arxiv.org/html/2406.08426v3#bib.bib99), [85](https://arxiv.org/html/2406.08426v3#bib.bib85), [100](https://arxiv.org/html/2406.08426v3#bib.bib100)] 在文本到 SQL 方面的基准能力及不同提示风格的表现。结果表明，提示设计对性能至关重要，通过错误分析，[[7](https://arxiv.org/html/2406.08426v3#bib.bib7)] 提出更多的数据库内容可能会损害整体准确性。由于 ChatGPT 在对话场景和代码生成方面展现出令人印象深刻的能力[[101](https://arxiv.org/html/2406.08426v3#bib.bib101)]，[[27](https://arxiv.org/html/2406.08426v3#bib.bib27)] 评估了其在文本到 SQL 方面的表现。在零样本设置下，结果表明，与最先进的基于 PLM 的系统相比，ChatGPT 在文本到 SQL 方面表现出色。为了公平比较，[[47](https://arxiv.org/html/2406.08426v3#bib.bib47)] 揭示了 LLM 基础的文本到 SQL 的有效提示构建；他们研究了不同的提示构建风格，并基于比较得出零样本提示设计的结论。

主键和外键包含了不同表之间的连续知识。[[49](https://arxiv.org/html/2406.08426v3#bib.bib49)] 通过将这些键融入各种提示风格和不同的数据库内容来研究它们的影响，以分析零样本提示结果。基准评估[[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] 也研究了外键的影响，采用了五种不同的提示表示风格，每种风格可以视为指令、规则含义和外键的排列组合。除了外键，本研究还探讨了将“无解释”规则含义与零样本提示相结合以收集简洁输出的情况。得益于人类专家注释的外部知识，[[33](https://arxiv.org/html/2406.08426v3#bib.bib33)] 遵循标准提示，通过结合提供的注释 oracle 知识取得了改进。

随着开源 LLMs 的爆炸式增长，根据类似评估的结果，这些模型也能够处理零样本文本到 SQL 任务 [[45](https://arxiv.org/html/2406.08426v3#bib.bib45), [50](https://arxiv.org/html/2406.08426v3#bib.bib50), [46](https://arxiv.org/html/2406.08426v3#bib.bib46)]，尤其是代码生成模型 [[48](https://arxiv.org/html/2406.08426v3#bib.bib48), [46](https://arxiv.org/html/2406.08426v3#bib.bib46)]。对于零样本提示优化，[[46](https://arxiv.org/html/2406.08426v3#bib.bib46)] 提出了设计有效提示模板的挑战；前者提示构建缺乏结构统一性，这使得很难找出构建提示模板中的具体元素对 LLMs 性能的影响。他们通过研究更统一的一系列提示模板，涵盖不同的前缀、中缀和后缀，来解决这一挑战。

少样本：少样本提示技术在实际应用和精心设计的研究中被广泛使用，已被证明对提高 LLMs 的性能有效 [[28](https://arxiv.org/html/2406.08426v3#bib.bib28), [102](https://arxiv.org/html/2406.08426v3#bib.bib102)]。基于 LLM 的少样本方法的整体输入提示可以被表示为 Eq. [3](https://arxiv.org/html/2406.08426v3#S4.E3 "In IV-A In-context Learning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL") 的扩展：

|  | $\mathcal{P}_{n}=\{\mathcal{F}_{1},\mathcal{F}_{2},\ldots,\mathcal{F}_{n}\}% \oplus\mathcal{P}_{0},$ |  | (5) |
| --- | --- | --- | --- |

其中 $\mathcal{P}_{n}$ 代表用于 $n$-shot 学习的输入提示，$n$ 是提供的实例（示例）数量；$\mathcal{F}$ 表示少样本实例，可以分解为 $\mathcal{F}_{i}=(\mathcal{S}_{i},\mathcal{Q}_{i},Y_{i})$，$i$ 是实例的序号。少样本提示的研究集中在表示的数量和少样本实例的选择上。

作为实证研究，针对文本到 SQL 的少量示例提示在多个数据集和各种大型语言模型（LLMs）中进行了评估[[8](https://arxiv.org/html/2406.08426v3#bib.bib8), [32](https://arxiv.org/html/2406.08426v3#bib.bib32)]，在与零-shot 提示的比较中表现出稳固的性能。[[33](https://arxiv.org/html/2406.08426v3#bib.bib33)] 提供了一个 1-shot 详细示例，用于触发文本到 SQL 模型以生成准确的 SQL。[[55](https://arxiv.org/html/2406.08426v3#bib.bib55)] 研究了少量示例的数量对性能的影响。[[52](https://arxiv.org/html/2406.08426v3#bib.bib52)] 关注采样策略，通过研究不同演示之间的相似性和多样性，设置随机采样作为基线，并评估不同策略及其组合以进行比较。此外，在基于相似性的选择之上，[[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] 评估了掩码问题相似性选择和不同数量少量示例的相似性方法的上限。一项关于难度级别样本选择的研究[[51](https://arxiv.org/html/2406.08426v3#bib.bib51)] 比较了少量 Codex [[100](https://arxiv.org/html/2406.08426v3#bib.bib100)] 的表现，通过随机选择和基于难度的选择来进行对比，数据集按照难度进行分类[[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)]。三种基于难度的选择策略是根据不同难度级别的选定样本数量制定的。[[49](https://arxiv.org/html/2406.08426v3#bib.bib49)] 利用一种混合策略来选择样本，该策略结合了静态示例和基于相似性的动态示例进行少量示例提示。在他们的设置中，他们还评估了不同输入模式样式和各种静态及动态示例数量的影响。

跨领域少量示例的影响也在研究中[[54](https://arxiv.org/html/2406.08426v3#bib.bib54)]。当结合不同数量的领域内和领域外示例时，领域内的演示优于零-shot 和领域外示例，并且随着示例数量的增加，领域外示例的表现也会更好。为了探讨输入提示的详细构建，[[53](https://arxiv.org/html/2406.08426v3#bib.bib53)] 比较了简洁和冗长的提示设计方法。前者通过竖线分隔模式、列名以及主键和外键，后者则将其组织为自然语言描述。

#### $\mathbf{C}_{1}$-分解

作为一种直观的解决方案，将具有挑战性的用户问题分解为更简单的子问题或使用多组件进行实现可以减少整体文本到 SQL 任务的复杂性 [[51](https://arxiv.org/html/2406.08426v3#bib.bib51), [8](https://arxiv.org/html/2406.08426v3#bib.bib8)]。处理较少的复杂性，LLMs 具有生成更准确 SQL 的潜力。基于分解的方法用于 LLM 基于的文本到 SQL 分为两种范式：（1）子任务分解，通过将整体文本到 SQL 任务分解为更可管理的有效子任务（例如，模式链接 [[71](https://arxiv.org/html/2406.08426v3#bib.bib71)]、领域分类 [[54](https://arxiv.org/html/2406.08426v3#bib.bib54)]）来提供额外的解析以协助最终的 SQL 生成。（2）子问题分解，将用户问题划分为子问题以降低问题的复杂性和难度，然后通过解决这些问题生成子 SQL 以推导最终的 SQL 查询。分解范式的技术新颖性

DIN-SQL [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)] 提出了一个分解式的上下文学习方法，包括四个模块：模式链接、分类与分解、SQL 生成和自我修正。DIN-SQL 首先生成用户问题与目标数据库之间的模式链接；随后模块将用户问题分解为相关的子问题并进行难度分类。基于上述信息，SQL 生成模块生成相应的 SQL，而自我修正模块识别并修正预测 SQL 中的潜在错误。这种方法将子问题分解全面考虑为子任务分解的一个模块。Coder-Reviewer [[56](https://arxiv.org/html/2406.08426v3#bib.bib56)] 框架提出了一种重新排序的方法，将 Coder 模型用于生成，将 Reviewer 模型用于评估指令的可能性。参考 Chain-of-Thought [[103](https://arxiv.org/html/2406.08426v3#bib.bib103)] 和 Least-to-Most prompting [[104](https://arxiv.org/html/2406.08426v3#bib.bib104)]，QDecomp [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)] 引入了问题分解提示，它遵循 least-to-most prompting 中的问题简化阶段，并指示 LLM 将原始复杂问题分解为中间推理步骤。C3 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)] 包含三个关键组件：清晰提示、校准偏差提示和一致性；这些组件通过为 ChatGPT 分配不同的任务来实现。首先，清晰提示组件生成模式链接和精炼的问题相关模式作为清晰提示。然后，利用关于 text-to-SQL 提示的多轮对话作为校准偏差提示，它与清晰提示结合以指导 SQL 生成。生成的 SQL 查询通过一致性和基于执行的投票来选择，以获得最终 SQL。MAC-SQL [[57](https://arxiv.org/html/2406.08426v3#bib.bib57)] 提出了一个多代理协作框架；text-to-SQL 过程作为代理的协作完成：Selector、Decomposer 和 Refiner。Selector 保留与用户问题相关的表；Decomposer 将用户问题分解为子问题并提供解决方案；最后，Refiner 验证并修正缺陷 SQL。DEA-SQL [[58](https://arxiv.org/html/2406.08426v3#bib.bib58)] 引入了一种工作流范式，旨在通过分解增强基于 LLM 的 text-to-SQL 的注意力和问题解决范围。该方法将整体任务分解，使 SQL 生成模块具有相应的前置（信息确定、问题分类）和后续（自我修正、主动学习）子任务。工作流范式使 LLM 能够生成更准确的 SQL 查询。SGU-SQL [[32](https://arxiv.org/html/2406.08426v3#bib.bib32)] 是一个结构到 SQL 的框架，利用固有的结构信息来辅助 SQL 生成。具体来说，该框架分别为用户问题和相应的数据库构建图结构，然后使用编码的图来构建结构链接 [[105](https://arxiv.org/html/2406.08426v3#bib.bib105), [106](https://arxiv.org/html/2406.08426v3#bib.bib106)]。一个元操作符使用语法树分解用户问题，并最终设计带有元操作的 SQL 输入提示。MetaSQL [[59](https://arxiv.org/html/2406.08426v3#bib.bib59)] 引入了三阶段的 SQL 生成方法：分解、生成和排名。分解阶段使用语义分解和元数据组合来处理用户问题。以之前处理的数据作为输入，使用元数据条件生成的 text-to-SQL 模型生成一些候选 SQL 查询。最后，应用两阶段排名管道以获得全局最优 SQL 查询。PET-SQL [[60](https://arxiv.org/html/2406.08426v3#bib.bib60)] 提出了一个增强提示的两阶段框架。首先，一个详细的提示指示 LLM 生成初步 SQL（PreSQL），其中基于相似性选择一些少量示例。然后，基于 PreSQL 查找模式链接并结合提示 LLM 生成最终 SQL（FinSQL）。最后，利用多个 LLM 生成 FinSQL，确保基于执行结果的一致性。

#### $\mathbf{C}_{2}$-提示优化

如前所述，少量学习在提示大语言模型（LLMs）的研究中得到广泛关注[[85](https://arxiv.org/html/2406.08426v3#bib.bib85)]。对于基于 LLM 的文本到 SQL 的上下文学习，简单的少量学习方法已经取得了令人满意的结果[[33](https://arxiv.org/html/2406.08426v3#bib.bib33), [8](https://arxiv.org/html/2406.08426v3#bib.bib8), [9](https://arxiv.org/html/2406.08426v3#bib.bib9)]，进一步优化少量学习提示有可能带来更好的表现。由于现成 LLM 中 SQL 生成的准确性在很大程度上依赖于相应输入提示的质量[[107](https://arxiv.org/html/2406.08426v3#bib.bib107)]，许多决定性因素影响提示质量已成为当前研究的重点[[9](https://arxiv.org/html/2406.08426v3#bib.bib9)]（例如，少量学习组织中的质量和数量、用户问题与少量学习实例之间的相似性、外部知识/提示）。提高提示质量的过程可以总结为提示优化，包括先进的少量学习采样策略、模式信息增强和外部知识整合。

DESEM [[62](https://arxiv.org/html/2406.08426v3#bib.bib62)] 是一个具备去语义化和骨架检索的提示工程框架。该框架首先使用领域特定的词汇屏蔽模块，去除用户问题中的语义标记，以保留意图。接着，它利用一个可调节的提示模块，检索具有相同问题意图的少量示例，并结合模式相关性过滤来指导 LLM 的 SQL 生成。QDecomp [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)] 框架引入了 InterCOL 机制，以逐步融合带有相关表和列名的分解子问题。通过基于难度的选择，QDecomp 的少量示例为难度级别样本。除了相似性-多样性采样，[[52](https://arxiv.org/html/2406.08426v3#bib.bib52)] 提出了 SD+SA+Voting（相似性-多样性+模式增强+投票）采样策略。他们首先利用语义相似性和 $k$-均值聚类多样性来采样少量示例，然后通过模式知识（语义或结构增强）来增强提示。C3 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)] 框架包括一个清晰的提示组件，它将问题和模式作为 LLM 的输入，生成一个清晰的提示，其中包含一个去除与用户问题无关的冗余信息的模式和模式链接，并且还有一个提供提示的校准组件。LLM 将其组成部分作为上下文增强提示用于 SQL 生成。引入了一个带有样本感知提示的检索增强框架 [[64](https://arxiv.org/html/2406.08426v3#bib.bib64)]，它简化原始问题并从简化问题中提取问题骨架，然后根据骨架相似性完成在库中的样本检索。检索到的样本与原始问题结合进行少量提示。ODIS [[54](https://arxiv.org/html/2406.08426v3#bib.bib54)] 引入了从域外示例和域内合成数据中选择样本的机制，检索来自混合来源的少量示例以增强提示表示。DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] 提出了一种新方法来解决少量采样和组织中的问题，呈现出在少量示例的质量和数量之间的更好平衡。DAIL 选择首先屏蔽用户和少量示例问题中的领域特定词汇，然后根据嵌入的欧氏距离对候选示例进行排名。同时，计算预预测 SQL 查询之间的相似性。最后，选择机制根据预设标准获取按相似性排序的候选示例。通过这种方法，少量示例与问题和 SQL 查询的相似性得到保证。ACT-SQL [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)] 提出了在少量提示中动态选择示例的方法，依据相似性得分进行选择。FUSED [[65](https://arxiv.org/html/2406.08426v3#bib.bib65)] 旨在通过无需人工干预的多轮合成来构建一个高多样性的示例库，以提高少量示例的多样性。FUSED 的流程通过聚类对示例进行采样，然后融合采样示例以构建库，从而增强少量学习。Knowledge-to-SQL [[31](https://arxiv.org/html/2406.08426v3#bib.bib31)] 框架旨在构建一个数据专家 LLM（DELLM）以提供 SQL 生成的知识。DELLM 通过使用人工专家注释 [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)] 的监督微调进行训练，并通过数据库反馈进一步通过偏好学习进行精炼。DELLM 生成四类知识，精心设计的方法（例如 DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)], MAC-SQL [[57](https://arxiv.org/html/2406.08426v3#bib.bib57)]）结合生成的知识，以实现基于 LLM 的文本到 SQL 的更好性能。

#### $\mathbf{C}_{3}$-推理增强

LLMs 在涉及常识推理、符号推理和算术推理的任务中表现出了令人鼓舞的能力[[108](https://arxiv.org/html/2406.08426v3#bib.bib108)]。对于文本到 SQL 的任务，数字和同义词推理在现实场景中经常发生[[33](https://arxiv.org/html/2406.08426v3#bib.bib33), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)]。LLMs 推理的提示策略有可能提升 SQL 生成能力。最近的研究主要集中于整合精心设计的推理增强方法用于文本到 SQL 的适配，提升 LLMs 应对需要复杂推理的难题的能力³³3 多步骤推理（例如思维链）与分解范式的区别在于，前者研究专注于在单轮生成中推进固有推理，而后者研究涉及使用不同的组件通过多次调用 LLMs 来辅助最终生成。以及 SQL 生成中的自洽性。

Chain-of-Thoughts (CoT) 提示技术 [[103](https://arxiv.org/html/2406.08426v3#bib.bib103)] 涉及一种综合推理过程，指导 LLMs 进行准确的推断，引发 LLMs 的推理。基于 LLM 的文本到 SQL 的研究利用 CoT 提示作为规则推导 [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)]，在提示构建中设置“让我们一步步思考”的指令 [[33](https://arxiv.org/html/2406.08426v3#bib.bib33), [51](https://arxiv.org/html/2406.08426v3#bib.bib51), [9](https://arxiv.org/html/2406.08426v3#bib.bib9), [32](https://arxiv.org/html/2406.08426v3#bib.bib32)]。然而，直接的（原始）CoT 策略在文本到 SQL 任务中未能展示出其在其他推理任务中的潜力；对 CoT 进行适应性研究仍在进行中 [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)]。由于 CoT 提示始终使用带有人为标注的静态示例进行演示，这需要通过经验判断来有效选择少量示例，并且手动标注也是一个必要需求。作为解决方案，ACT-SQL [[49](https://arxiv.org/html/2406.08426v3#bib.bib49)] 提出了自动生成 CoT 示例的方法。具体而言，ACT-SQL 在给定问题时，会截取问题的一组切片，然后枚举在相应 SQL 查询中出现的每一列。每一列会通过相似性函数与其最相关的切片连接，并添加到 CoT 提示中。通过系统化研究以增强 LLMs SQL 生成结合 CoT 提示，QDecomp [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)] 提出了一个新框架，以解决 CoT 如何提出推理步骤以预测 SQL 查询的挑战。该框架利用 SQL 查询的每一个切片来构建 CoT 推理中的逻辑步骤，然后使用自然语言模板来表达 SQL 查询的每一个切片，并按逻辑执行顺序排列它们。Least-to-Most [[104](https://arxiv.org/html/2406.08426v3#bib.bib104)] 是另一种提示技术，它将问题分解为子问题，然后逐步解决它们。作为迭代提示，初步实验 [[51](https://arxiv.org/html/2406.08426v3#bib.bib51)] 证明它可能在文本到 SQL 解析中是不必要的。使用详细的推理步骤往往会导致更多的错误传播问题。作为 CoT 的变体，Program-of-Thoughts (PoT) 提示策略 [[109](https://arxiv.org/html/2406.08426v3#bib.bib109)] 被提出以增强 LLMs 的算术推理。通过评估 [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)]，PoT 提升了 LLM 在 SQL 生成中的表现，特别是在复杂数据集 [[33](https://arxiv.org/html/2406.08426v3#bib.bib33)]。SQL-CRAFT [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)] 被提出以增强基于 LLM 的 SQL 生成，它结合了 PoT 提示用于 Python 增强推理。PoT 策略要求模型同时生成 Python 代码和 SQL 查询，强制模型在推理过程中结合 Python 代码。Self-Consistency [[110](https://arxiv.org/html/2406.08426v3#bib.bib110)] 是一种提升 LLMs 推理的提示策略，它利用了复杂推理问题通常允许多种不同思维方式，从而得出唯一正确答案的直觉。在文本到 SQL 任务中，自一致性被适应为采样一组不同的 SQL 并通过执行反馈进行一致性投票 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30), [53](https://arxiv.org/html/2406.08426v3#bib.bib53)]。类似地，SD+SA+Voting [[52](https://arxiv.org/html/2406.08426v3#bib.bib52)] 框架排除了那些由确定性数据库管理系统（DBMS）识别的执行错误，并选择获得多数票的预测。此外，受近期扩展 LLMs 能力研究的启发，FUXI [[66](https://arxiv.org/html/2406.08426v3#bib.bib66)] 被提出以通过有效调用精心设计的工具来增强 LLMs SQL 生成。

#### $\mathbf{C}_{4}$-执行细化

在设计准确 SQL 生成的标准时，优先考虑的始终是生成的 SQL 是否能够成功执行并检索内容以正确回答用户问题 [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)]。作为一项复杂的编程任务，一次性生成正确的 SQL 是具有挑战性的。直观上，考虑 SQL 生成中的执行反馈/结果有助于对齐相应的数据库环境，这使得 LLM 能够收集潜在的执行错误和结果，以细化生成的 SQL 或进行多数投票 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)]。文本到 SQL 的执行感知方法主要有两种方式：1) 通过第二轮提示纳入反馈进行再生成，对于每个在初始响应中生成的 SQL 查询，将在相应的数据库中执行，从而获得数据库的反馈。这些反馈可能是错误，也可能是会附加到第二轮提示中的结果。通过这种反馈的上下文学习，LLM 能够细化或重新生成原始 SQL，从而提高准确性。2) 利用基于执行的选择策略对生成的 SQL 进行选择，从 LLM 中采样多个生成的 SQL 查询，并在数据库中执行每个查询。根据每个 SQL 查询的执行结果，使用选择策略（例如，自我一致性，多数投票 [[60](https://arxiv.org/html/2406.08426v3#bib.bib60)]）从 SQL 集中定义一个符合标准的 SQL 查询作为最终预测的 SQL。

MRC-EXEC [[67](https://arxiv.org/html/2406.08426v3#bib.bib67)] 引入了一个自然语言到代码（NL2Code）翻译框架，并且进行了执行，该框架执行每个采样的 SQL 查询，并选择执行结果最小的 Bayes 风险的示例 [[111](https://arxiv.org/html/2406.08426v3#bib.bib111)]。LEVER [[68](https://arxiv.org/html/2406.08426v3#bib.bib68)] 提出了一个验证 NL2Code 执行的方法，利用生成和执行模块分别收集采样的 SQL 集及其执行结果，然后使用学习到的验证器输出正确性的概率。类似地，SELF-DEBUGGING [[48](https://arxiv.org/html/2406.08426v3#bib.bib48)] 框架旨在通过少量示例教导 LLM 调试其预测的 SQL。该模型能够通过检查执行结果和用自然语言解释生成的 SQL 来修正其错误，而无需人工干预。

如前所述，为了将精心设计的框架与执行反馈结合，广泛使用两阶段的含义：1\. 采样一组 SQL 查询。2\. 多数投票（自我一致性）。具体而言，C3 [[30](https://arxiv.org/html/2406.08426v3#bib.bib30)] 框架去除错误并识别最一致的 SQL；检索增强框架 [[64](https://arxiv.org/html/2406.08426v3#bib.bib64)] 引入了动态修订链，将细粒度的执行消息与数据库内容结合，促使 LLM 将生成的 SQL 查询转换为自然语言解释；LLM 被要求识别语义差距并修订其生成的 SQL。尽管模式过滤方法提升了 SQL 生成，但生成的 SQL 可能无法执行。DESEM [[62](https://arxiv.org/html/2406.08426v3#bib.bib62)] 采用回退修订来解决这一问题；它根据不同类型的错误修订和再生成 SQL，并设置终止标准以避免循环。DIN-SQL [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)] 在其自我修正模块中设计了通用且温和的提示；通用提示要求 LLM 识别和纠正错误，而温和提示要求模型检查潜在问题。多代理框架 MAC-SQL [[57](https://arxiv.org/html/2406.08426v3#bib.bib57)] 包含一个修正代理，该代理能够检测和自动纠正 SQL 错误，利用 SQLite 错误和异常类来再生成修正后的 SQL。由于不同的问题可能需要不同数量的修订，SQL-CRAFT [[55](https://arxiv.org/html/2406.08426v3#bib.bib55)] 框架引入了互动修正和自动控制确定过程，以避免过度修正或不足修正。FUXI [[66](https://arxiv.org/html/2406.08426v3#bib.bib66)] 在工具化推理中考虑了错误反馈用于 SQL 生成。Knowledge-to-SQL [[31](https://arxiv.org/html/2406.08426v3#bib.bib31)] 引入了一个偏好学习框架，将数据库执行反馈与直接偏好优化 [[112](https://arxiv.org/html/2406.08426v3#bib.bib112)] 结合，用于优化提出的 DELLM。PET-SQL [[60](https://arxiv.org/html/2406.08426v3#bib.bib60)] 提出了交叉一致性，包括两个变体：1) 朴素投票：指示多个 LLM 生成 SQL 查询，然后利用多数投票来确定最终 SQL 基于不同的执行结果；2) 细粒度投票：基于难度级别对朴素投票进行细化，以减轻投票偏差。

### IV-B 微调

表 IV：用于 LLM 基于文本到 SQL 的微调（FT）的精心设计方法。每个类别中的方法按发布时间排序。^*这些方法在多个开源 LLM 中被使用；我们选择一个代表性模型进行展示。

| 类别 | 采用者 | 应用的 LLM | 数据集 | EX | EM | VES | 发布时点 | 发表场所 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 增强架构 | CLLMs [[69](https://arxiv.org/html/2406.08426v3#bib.bib69)] | Deepseek^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] | ✓ |  |  | 2024 年 3 月 | ICML’24 |
| 预训练 | CodeS [[10](https://arxiv.org/html/2406.08426v3#bib.bib10)] | StarCoder | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | ✓ |  | ✓ | 2024 年 2 月 | SIGMOD’24 |
| 数据增强 | DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] | LLaMA^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)] | ✓ | ✓ |  | 2023 年 8 月 | VLDB’24 |
| Symbol-LLM [[50](https://arxiv.org/html/2406.08426v3#bib.bib50)] | CodeLLaMA | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] |  | ✓ |  | 2023 年 11 月 | ACL’24 |
| CodeS [[10](https://arxiv.org/html/2406.08426v3#bib.bib10)] | StarCoder | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)] | ✓ |  | ✓ | 2024 年 2 月 | SIGMOD’24 |
| StructLM [[70](https://arxiv.org/html/2406.08426v3#bib.bib70)] | CodeLLaMA | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13)] |  | ✓ |  | 2024 年 2 月 | arXiv’24 |
| 分解 | DTS-SQL [[71](https://arxiv.org/html/2406.08426v3#bib.bib71)] | Mistral^* | [[13](https://arxiv.org/html/2406.08426v3#bib.bib13), [40](https://arxiv.org/html/2406.08426v3#bib.bib40)] | ✓ | ✓ |  | 2024 年 2 月 | arXiv’24 |

由于有监督的微调（SFT）是 LLM 训练中的主流方法 [[29](https://arxiv.org/html/2406.08426v3#bib.bib29), [91](https://arxiv.org/html/2406.08426v3#bib.bib91)]，对于开源 LLM（例如，LLaMA-2 [[94](https://arxiv.org/html/2406.08426v3#bib.bib94)], Gemma [[113](https://arxiv.org/html/2406.08426v3#bib.bib113)]），使模型快速适应特定领域的最直接方法是使用收集到的领域标签对模型进行 SFT。SFT 阶段通常是精心设计的训练框架的初步阶段 [[112](https://arxiv.org/html/2406.08426v3#bib.bib112), [114](https://arxiv.org/html/2406.08426v3#bib.bib114)]，以及文本到 SQL 的微调。SQL 查询 $Y$ 的自回归生成过程可以表示如下：

|  | $P_{\pi}(Y\mid\mathcal{P})=\prod_{k=1}^{n}P_{\pi}(y_{k}\mid\mathcal{P},Y_{1:k-1% }),$ |  | (6) |
| --- | --- | --- | --- |

其中 $Y=\{y_{1},y_{2},\ldots,y_{n}\}$ 是一个长度为 $n$ 的 SQL 查询，$y_{k}$ 是 SQL 查询的第 $k^{th}$ 个标记，$Y_{1:k-1}$ 是位于标记 $y_{k}$ 之前的 $Y$ 的前缀序列。$P_{\pi}(y_{k}\mid\cdot)$ 是 LLM $\pi$ 基于输入提示 $\mathcal{P}$ 和前缀序列生成 $Y$ 的第 $k^{th}$ 个标记的条件概率。

给定一个基本的开源模型 $\pi^{0}$，SFT 的目标是通过最小化交叉熵损失来获得一个模型 $\pi^{SFT}$：

|  | $\mathcal{L}_{SFT}=-\sum_{k=1}^{n}\operatorname{log}P_{\pi^{0}}(\hat{y}_{k}=y_{k}\mid\mathcal{P},Y_{1:k-1}),$ |  | (7) |
| --- | --- | --- | --- |

其中 $\hat{y}_{k}$ 是生成的 SQL 查询 $\hat{Y}$ 的第 $k$ 个标记，$Y$ 是对应的真实标签。

SFT 方法，也就是一种传统的文本到 SQL 的微调方法，在各种开源 LLM 的文本到 SQL 研究中已被广泛采用[[10](https://arxiv.org/html/2406.08426v3#bib.bib10), [46](https://arxiv.org/html/2406.08426v3#bib.bib46), [9](https://arxiv.org/html/2406.08426v3#bib.bib9)]。与上下文学习（ICL）方法相比，微调范式更倾向于成为 LLM 基于文本到 SQL 的起点。目前，已经发布了若干研究以探索更好的微调方法。我们根据其机制将设计良好的微调方法分为不同的组，如 Tab. [IV](https://arxiv.org/html/2406.08426v3#S4.T4 "TABLE IV ‣ IV-B Fine-tuning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")所示。

#### 增强架构

广泛使用的生成预训练变换器（GPT）框架利用了仅解码器的变换器架构和传统的自回归解码进行文本生成。对 LLM 效率的最新研究揭示了一个共同的挑战：在使用自回归范式生成长序列时，必须引入注意力机制，这导致 LLM 的延迟时间较高[[115](https://arxiv.org/html/2406.08426v3#bib.bib115), [116](https://arxiv.org/html/2406.08426v3#bib.bib116)]。在基于 LLM 的文本到 SQL 转换中，生成 SQL 查询的速度明显慢于传统语言建模[[21](https://arxiv.org/html/2406.08426v3#bib.bib21), [28](https://arxiv.org/html/2406.08426v3#bib.bib28)]，这已成为构建高效本地 NLIDB 的挑战。

作为解决方案之一，CLLMs [[69](https://arxiv.org/html/2406.08426v3#bib.bib69)] 旨在通过增强的模型架构来解决上述挑战，并实现 SQL 生成的加速。

#### 数据增强

在微调过程中，影响模型性能的最直接因素是训练标签的质量[[117](https://arxiv.org/html/2406.08426v3#bib.bib117)]。在低质量或缺乏训练标签的情况下进行微调就像是“无米之炊”，使用高质量或增强的数据进行微调总是优于对低质量或原始数据的精细设计[[74](https://arxiv.org/html/2406.08426v3#bib.bib74), [29](https://arxiv.org/html/2406.08426v3#bib.bib29)]。在文本到 SQL 的领域，数据增强的微调取得了显著进展，重点在于提升 SFT 过程中的数据质量。

DAIL-SQL [[9](https://arxiv.org/html/2406.08426v3#bib.bib9)] 设计为一种上下文学习框架，利用采样策略来改善少量样本的表现。在 SFT 过程中融入采样实例提升了开源 LLMs 的性能。Symbol-LLM [[50](https://arxiv.org/html/2406.08426v3#bib.bib50)] 提出了数据增强指令调优的注入和注入阶段。CodeS [[10](https://arxiv.org/html/2406.08426v3#bib.bib10)] 在 ChatGPT 的帮助下通过双向生成增强了训练数据。StructLM [[70](https://arxiv.org/html/2406.08426v3#bib.bib70)] 在多个结构化知识任务上进行训练，以提高整体能力。

#### 预训练

预训练是完整微调过程中的一个基础阶段，旨在通过在广泛数据上的自回归训练来获得文本生成能力 [[118](https://arxiv.org/html/2406.08426v3#bib.bib118)]。传统上，当前强大的专有 LLMs（如 ChatGPT [[119](https://arxiv.org/html/2406.08426v3#bib.bib119]）、GPT-4 [[86](https://arxiv.org/html/2406.08426v3#bib.bib86]）、Claude [[120](https://arxiv.org/html/2406.08426v3#bib.bib120]））在混合语料库上进行预训练，这主要受益于展现文本生成能力的对话场景 [[85](https://arxiv.org/html/2406.08426v3#bib.bib85)]。代码特定的 LLMs（如 CodeLLaMA [[121](https://arxiv.org/html/2406.08426v3#bib.bib121]）、StarCoder [[122](https://arxiv.org/html/2406.08426v3#bib.bib122]））在代码数据上进行预训练 [[100](https://arxiv.org/html/2406.08426v3#bib.bib100)]，各种编程语言的混合使得 LLMs 能够生成符合用户指令的代码 [[123](https://arxiv.org/html/2406.08426v3#bib.bib123)]。作为代码生成的一个子任务，SQL 特定的预训练技术的主要挑战是 SQL/数据库相关内容仅占整个预训练语料库的一小部分。因此，相对有限的综合能力（与 ChatGPT、GPT-4 相比）的开源 LLMs 在预训练过程中没有获得对如何将 NL 问题转换为 SQL 的良好理解。

CodeS [[10](https://arxiv.org/html/2406.08426v3#bib.bib10)] 模型的预训练阶段包括三个逐步预训练的阶段。从一个基础的代码特定 LLM [[122](https://arxiv.org/html/2406.08426v3#bib.bib122)] 开始，CodeS 在一个混合训练语料库上进行增量预训练，包括 SQL 相关数据、NL 到代码数据和 NL 相关数据。文本到 SQL 的理解和性能显著提高。

#### 分解

将任务分解为多个步骤或使用多个模型来解决任务是一种直观的解决复杂场景的方案，正如我们在 Sec. [IV-A](https://arxiv.org/html/2406.08426v3#S4.SS1.SSSx2 "𝐂₁-Decomposition ‣ IV-A In-context Learning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")中介绍的 ICL 范式。ICL 方法中使用的专有模型具有大量的参数，这些参数水平不及在微调方法中使用的开源模型。这些模型本质上具有良好执行指定子任务的能力（通过如少样本学习等机制）[[30](https://arxiv.org/html/2406.08426v3#bib.bib30), [57](https://arxiv.org/html/2406.08426v3#bib.bib57)]。因此，为了在 ICL 方法中复制这种范式的成功，有必要合理地将相应的子任务分配给开源模型（如生成外部知识、模式链接和模式提炼），进行子任务特定的微调，并构建相应的数据进行微调，从而协助最终的 SQL 生成。

DTS-SQL [[71](https://arxiv.org/html/2406.08426v3#bib.bib71)] 提出了一个两阶段分解的文本到 SQL 微调框架，并设计了一个在最终 SQL 生成之前的模式链接预生成任务。

## V 期望

尽管在文本到 SQL 的研究中取得了显著进展，但仍然存在若干挑战需要解决。在这一部分，我们讨论了我们期望在未来工作中克服的剩余挑战。

### V-A 现实世界应用中的鲁棒性

由 LLMs 实现的文本到 SQL 转换预期能够在实际应用中的复杂场景中表现出广泛的泛化能力和鲁棒性。尽管最近的进展在专注于鲁棒性的数据集上取得了显著进展[[37](https://arxiv.org/html/2406.08426v3#bib.bib37), [41](https://arxiv.org/html/2406.08426v3#bib.bib41)]，其表现仍然未能满足实际应用的需求[[33](https://arxiv.org/html/2406.08426v3#bib.bib33)]。未来研究仍面临挑战。从用户角度来看，用户并不总是明确的问题提出者，这意味着用户的问题可能没有确切的数据库值，并且可能与标准数据集有所不同，包括同义词、拼写错误和模糊表述[[40](https://arxiv.org/html/2406.08426v3#bib.bib40)]。例如，模型在微调范式下对明确指示性问题进行训练，且表达清晰。由于模型尚未学习现实问题与相应数据库的映射，这导致在实际应用中存在知识差距[[33](https://arxiv.org/html/2406.08426v3#bib.bib33)]。根据对包含同义词和不完整指令的数据集的评估[[7](https://arxiv.org/html/2406.08426v3#bib.bib7), [51](https://arxiv.org/html/2406.08426v3#bib.bib51)]，ChatGPT 生成的 SQL 查询约有 40%执行错误，比原始评估低 10%[[51](https://arxiv.org/html/2406.08426v3#bib.bib51)]。同时，微调本地文本到 SQL 数据集可能包含非标准化的样本和标签。例如，表或列的名称并不总是准确表示其内容，这导致训练数据构建中的不一致，并可能导致数据库模式与用户问题之间的语义差距。为解决这一挑战，将 LLMs 与意图偏差对齐，并设计针对噪声场景的训练策略将有利于近期进展。同时，实际应用中的数据量相对较小，低于以研究为导向的基准。由于通过人工标注扩展大量数据会带来高劳动成本，设计数据增强方法以获取更多问题-SQL 对将支持 LLM 应对数据稀缺。此外，将微调的开源 LLM 适应本地小规模数据集也可能具有潜在的益处。此外，未来研究应全面研究多语言[[42](https://arxiv.org/html/2406.08426v3#bib.bib42), [124](https://arxiv.org/html/2406.08426v3#bib.bib124)]和多模态场景[[125](https://arxiv.org/html/2406.08426v3#bib.bib125)]的扩展，这将使更多语言群体受益，并帮助构建更通用的数据库接口。

### V-B 计算效率

计算效率由推理速度和计算资源的成本决定，这在应用和研究工作中都值得考虑[[69](https://arxiv.org/html/2406.08426v3#bib.bib69), [49](https://arxiv.org/html/2406.08426v3#bib.bib49)]。随着数据库在最新的文本到 SQL 基准测试中的复杂性增加[[15](https://arxiv.org/html/2406.08426v3#bib.bib15), [33](https://arxiv.org/html/2406.08426v3#bib.bib33)]，数据库将承载更多的信息（包括更多的表和列），数据库模式的令牌长度将相应增加，带来一系列挑战。处理超复杂的数据库时，将相应的模式作为输入可能会遇到调用专有 LLM 的成本显著增加的挑战，可能会超出模型的最大令牌长度，特别是在实现具有较短上下文长度的开源模型时。同时，另一个明显的挑战是大多数工作使用完整模式作为模型输入，这引入了显著的冗余[[57](https://arxiv.org/html/2406.08426v3#bib.bib57)]。从用户端提供给 LLM 一个与问题相关的精确过滤模式以减少成本和冗余是提高计算效率的潜在解决方案[[30](https://arxiv.org/html/2406.08426v3#bib.bib30)]。设计一种准确的模式过滤方法仍然是未来的方向。尽管上下文学习范式取得了令人鼓舞的准确性，但作为计算效率方面的关注点，具有多阶段框架或扩展上下文的精心设计方法，尽管提高了性能，但也导致了成本的大幅上升[[8](https://arxiv.org/html/2406.08426v3#bib.bib8)]。如相关方法所报告[[49](https://arxiv.org/html/2406.08426v3#bib.bib49)]，应仔细考虑性能与计算效率之间的权衡，并设计一种成本更低（甚至更好的）上下文学习方法将是一项实际的实施，仍在探索中。与 PLM 基础方法相比，基于 LLM 的方法的推理速度明显较慢[[28](https://arxiv.org/html/2406.08426v3#bib.bib28), [21](https://arxiv.org/html/2406.08426v3#bib.bib21)]。通过缩短输入长度和减少实现中的阶段数来加速推理，对于上下文学习范式将是直观的。对于本地 LLM，从起点[[69](https://arxiv.org/html/2406.08426v3#bib.bib69)]来看，可以在未来的探索中研究更多的加速策略，以增强模型的架构。

### V-C 数据隐私与可解释性

作为 LLMs 研究的一部分，基于 LLM 的文本到 SQL 也面临 LLM 研究中存在的一些一般性挑战[[126](https://arxiv.org/html/2406.08426v3#bib.bib126)，[4](https://arxiv.org/html/2406.08426v3#bib.bib4)，[127](https://arxiv.org/html/2406.08426v3#bib.bib127)]。从文本到 SQL 的角度来看，这些挑战也有望带来潜在的改进，从而广泛造福 LLMs 的研究。正如在第 IV-A 节中所讨论的那样[IV-A](https://arxiv.org/html/2406.08426v3#S4.SS1 "IV-A In-context Learning ‣ IV Methods ‣ Next-Generation Database Interfaces: A Survey of LLM-based Text-to-SQL")，基于上下文的学习范式在最近的研究中占据了主导地位，大部分工作使用专有模型进行实现[[8](https://arxiv.org/html/2406.08426v3#bib.bib8)，[9](https://arxiv.org/html/2406.08426v3#bib.bib9)]。一个直接的挑战是关于数据隐私的，因为调用专有 API 处理具有保密性的本地数据库可能会导致数据泄露风险。使用本地微调范式可以部分解决这个问题。然而，目前普通微调的性能并不理想[[9](https://arxiv.org/html/2406.08426v3#bib.bib9)]，并且先进的微调框架潜在地依赖于专有 LLMs 进行数据增强[[10](https://arxiv.org/html/2406.08426v3#bib.bib10)]。基于当前的状态，文本到 SQL 的本地微调范式需要得到广泛关注。总的来说，深度学习的发展在可解释性方面不断面临挑战[[127](https://arxiv.org/html/2406.08426v3#bib.bib127)，[128](https://arxiv.org/html/2406.08426v3#bib.bib128)]。作为一个长期存在的挑战，已经进行了相当多的研究来解决这个问题[[129](https://arxiv.org/html/2406.08426v3#bib.bib129)，[130](https://arxiv.org/html/2406.08426v3#bib.bib130)]。然而，在文本到 SQL 的研究中，基于 LLM 的实现的可解释性仍然没有被讨论，无论是在上下文学习还是微调范式中。具有分解阶段的方法从逐步生成的角度解释了文本到 SQL 的实现过程[[8](https://arxiv.org/html/2406.08426v3#bib.bib8)，[51](https://arxiv.org/html/2406.08426v3#bib.bib51)]。在此基础上，结合可解释性的高级研究[[131](https://arxiv.org/html/2406.08426v3#bib.bib131)，[132](https://arxiv.org/html/2406.08426v3#bib.bib132)]，以提高文本到 SQL 的性能并从数据库知识角度解释本地模型架构，仍然是未来的方向。

### V-D Extensions

作为 LLM 和自然语言理解研究的一个子领域，这些领域中的许多研究已经被应用于文本到 SQL 任务，推动了其发展 [[103](https://arxiv.org/html/2406.08426v3#bib.bib103), [110](https://arxiv.org/html/2406.08426v3#bib.bib110)]。然而，文本到 SQL 的研究也可以扩展到这些领域的更大范围的研究中。例如，SQL 生成是代码生成的一部分。在代码生成中的设计良好的方法也在文本到 SQL 中取得了有希望的性能 [[68](https://arxiv.org/html/2406.08426v3#bib.bib68), [48](https://arxiv.org/html/2406.08426v3#bib.bib48)]，实现了跨各种编程语言的泛化。一些量身定制的文本到 SQL 框架向 NL 到代码研究的潜在扩展也可以讨论。例如，集成执行输出的 NL 到代码框架在 SQL 生成中也能取得良好的表现 [[8](https://arxiv.org/html/2406.08426v3#bib.bib8)]。扩展执行感知方法到文本到 SQL 与其他先进模块 [[31](https://arxiv.org/html/2406.08426v3#bib.bib31), [30](https://arxiv.org/html/2406.08426v3#bib.bib30)] 的尝试值得讨论。从另一个角度来看，我们之前讨论了文本到 SQL 如何通过提供事实信息来增强基于 LLM 的问答（QA）。数据库可以存储作为结构信息的关系知识，而基于结构的 QA 可以从文本到 SQL 中获益（例如，基于知识的问答，KBQA [[133](https://arxiv.org/html/2406.08426v3#bib.bib133), [134](https://arxiv.org/html/2406.08426v3#bib.bib134)]）。构建具有数据库结构的事实知识，然后将文本到 SQL 系统纳入信息检索，这可以在进一步的问答中提供更准确的事实知识 [[135](https://arxiv.org/html/2406.08426v3#bib.bib135)]。预计未来的工作中会有更多文本到 SQL 研究的扩展。

## 参考文献

+   [1] L. Wang, B. Qin, B. Hui, B. Li, M. Yang, B. Wang, B. Li, J. Sun, F. Huang, L. Si, 和 Y. Li, “Proton: 从预训练语言模型中探测模式链接信息以进行文本到 SQL 解析，” 发表在 *知识发现与数据挖掘会议（KDD）*，2022 年。

+   [2] B. Qin, B. Hui, L. Wang, M. Yang, J. Li, B. Li, R. Geng, R. Cao, J. Sun, L. Si *等人*, “关于文本到 SQL 解析的调查：概念、方法和未来方向，” *arXiv 预印本 arXiv:2208.13629*，2022 年。

+   [3] S. Xu, S. Semnani, G. Campagna, 和 M. Lam, “Autoqa: 从数据库到 QA 语义解析器，仅使用合成训练数据，” 发表在 *自然语言处理中的实证方法（EMNLP）*，2020 年。

+   [4] Y. Zhang, Y. Li, L. Cui, D. Cai, L. Liu, T. Fu, X. Huang, E. Zhao, Y. Zhang, Y. Chen *等人*, “AI 海洋中的海妖之歌：关于大语言模型中的幻觉的调查，” *arXiv 预印本 arXiv:2309.01219*，2023 年。

+   [5] P. Manakul, A. Liusie, 和 M. J. Gales, “Selfcheckgpt: 零资源黑箱幻觉检测用于生成大型语言模型，” 在 *自然语言处理中的实证方法（EMNLP）*，2023。

+   [6] S. Lin, J. Hilton, 和 O. Evans, “Truthfulqa: 衡量模型如何模仿人类的虚假信息，” 在 *计算语言学协会（ACL）*，2021。

+   [7] N. Rajkumar, R. Li, 和 D. Bahdanau, “评估大型语言模型的文本到 SQL 能力，” *arXiv 预印本 arXiv:2204.00498*，2022。

+   [8] M. Pourreza 和 D. Rafiei, “DIN-SQL: 基于自我纠正的文本到 SQL 的上下文学习分解，” 在 *神经信息处理系统进展（NeurIPS）*，2023。

+   [9] D. Gao, H. Wang, Y. Li, X. Sun, Y. Qian, B. Ding, 和 J. Zhou, “大型语言模型增强的文本到 SQL：基准评估，” 在 *国际大型数据会议（VLDB）*，2024。

+   [10] H. Li, J. Zhang, H. Liu, J. Fan, X. Zhang, J. Zhu, R. Wei, H. Pan, C. Li, 和 H. Chen, “Codes: 致力于构建用于文本到 SQL 的开源语言模型，” 在 *数据管理会议（SIGMOD）*，2024。

+   [11] F. Li 和 H. V. Jagadish, “构建一个交互式自然语言界面用于关系数据库，” 在 *国际大型数据会议（VLDB）*，2014。

+   [12] T. Mahmud, K. A. Hasan, M. Ahmed, 和 T. H. C. Chak, “一种基于规则的自然语言处理查询处理方法，” 在 *国际电气信息与通信技术会议（EICT）*，2015。

+   [13] T. Yu, R. Zhang, K. Yang, M. Yasunaga, D. Wang, Z. Li, J. Ma, I. Li, Q. Yao, S. Roman, Z. Zhang, 和 D. Radev, “Spider: 一个大规模人工标注的数据集，用于复杂和跨领域的语义解析和文本到 SQL 任务，” 在 *自然语言处理中的实证方法（EMNLP）*，2018。

+   [14] V. Zhong, C. Xiong, 和 R. Socher, “Seq2sql: 利用强化学习从自然语言生成结构化查询，” *arXiv 预印本 arXiv:1709.00103*，2017。

+   [15] M. Pourreza 和 D. Rafiei, “评估跨领域文本到 SQL 模型和基准测试，” 在 *自然语言处理中的实证方法（EMNLP）*，2023。

+   [16] I. Sutskever, O. Vinyals, 和 Q. V. Le, “基于神经网络的序列到序列学习，” 在 *神经信息处理系统进展（NeurIPS）*，2014。

+   [17] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez, Ł. Kaiser, 和 I. Polosukhin, “注意力即你所需，” 在 *神经信息处理系统进展（NeurIPS）*，2017。

+   [18] B. Hui, X. Shi, R. Geng, B. Li, Y. Li, J. Sun, 和 X. Zhu, “通过模式依赖学习改进文本到 SQL，” *arXiv 预印本 arXiv:2103.04399*，2021。

+   [19] D. Choi, M. C. Shin, E. Kim, 和 D. R. Shin, “Ryansql: 递归应用基于草图的槽填充用于复杂的跨领域数据库文本到 SQL，” *计算语言学*，2021。

+   [20] P. Yin, G. Neubig, W.-t. Yih, 和 S. Riedel, “Tabert：预训练用于文本和表格数据的联合理解，” *arXiv 预印本 arXiv:2005.08314*，2020。

+   [21] H. Li, J. Zhang, C. Li, 和 H. Chen, “Resdsql：将模式链接和骨架解析解耦用于文本到 SQL，” 在 *人工智能会议 (AAAI)*，2023。

+   [22] J. Li, B. Hui, R. Cheng, B. Qin, C. Ma, N. Huo, F. Huang, W. Du, L. Si, 和 Y. Li, “Graphix-t5：将预训练变换器与图感知层混合用于文本到 SQL 解析，” 在 *人工智能会议 (AAAI)*，2023。

+   [23] D. Rai, B. Wang, Y. Zhou, 和 Z. Yao, “改进语言模型基础的文本到 SQL 语义解析中的泛化：两种简单的语义边界技术，” 在 *计算语言学协会 (ACL)*，2023。

+   [24] J. Devlin, M.-W. Chang, K. Lee, 和 K. Toutanova, “BERT：用于语言理解的深度双向变换器的预训练，” 在 *北美计算语言学协会：人类语言技术 (NAACL-HLT)*，2019。

+   [25] Q. Lyu, K. Chakrabarti, S. Hathi, S. Kundu, J. Zhang, 和 Z. Chen, “用于文本到 SQL 的混合排序网络，” *arXiv 预印本 arXiv:2008.04759*，2020。

+   [26] T. Yu, C.-S. Wu, X. V. Lin, bailin wang, Y. C. Tan, X. Yang, D. Radev, richard socher, 和 C. Xiong, “Grappa：用于表格语义解析的语法增强预训练，” 在 *国际学习表示会议 (ICLR)*，2021。

+   [27] A. Liu, X. Hu, L. Wen, 和 P. S. Yu, “对 ChatGPT 的零样本文本到 SQL 能力的全面评估，” *arXiv 预印本 arXiv:2303.13547*，2023。

+   [28] J. Yang, H. Jin, R. Tang, X. Han, Q. Feng, H. Jiang, S. Zhong, B. Yin, 和 X. Hu, “实际应用中的大型语言模型的力量：对 ChatGPT 及其后的调查，” *ACM 数据知识发现事务 (TKDD)*，2024。

+   [29] W. X. Zhao, K. Zhou, J. Li, T. Tang, X. Wang, Y. Hou, Y. Min, B. Zhang, J. Zhang, Z. Dong *等*，“大型语言模型综述，” *arXiv 预印本 arXiv:2303.18223*，2023。

+   [30] X. Dong, C. Zhang, Y. Ge, Y. Mao, Y. Gao, J. Lin, D. Lou *等*，“C3：使用 ChatGPT 的零样本文本到 SQL，” *arXiv 预印本 arXiv:2307.07306*，2023。

+   [31] Z. Hong, Z. Yuan, H. Chen, Q. Zhang, F. Huang, 和 X. Huang, “知识到 SQL：利用数据专家 LLM 提升 SQL 生成，” *arXiv 预印本 arXiv:2402.11517*，2024。

+   [32] Q. Zhang, J. Dong, H. Chen, W. Li, F. Huang, 和 X. Huang, “结构指导的大型语言模型用于 SQL 生成，” *arXiv 预印本 arXiv:2402.13284*，2024。

+   [33] J. Li, B. Hui, G. QU, J. Yang, B. Li, B. Li, B. Wang, B. Qin, R. Geng, N. Huo, X. Zhou, C. Ma, G. Li, K. Chang, F. Huang, R. Cheng, 和 Y. Li, “LLM 是否已经可以作为数据库接口？一个用于大规模数据库基础文本到 SQL 的 BIg 基准，” 在 *神经信息处理系统进展 (NeurIPS)*，2023。

+   [34] L. Wang, A. Zhang, K. Wu, K. Sun, Z. Li, H. Wu, M. Zhang, 和 H. Wang，“DuSQL：一个大规模且实用的中文文本到 SQL 数据集”，发表于*自然语言处理中的实证方法 (EMNLP)*，2020 年。

+   [35] T. Yu, R. Zhang, H. Er, S. Li, E. Xue, B. Pang, X. V. Lin, Y. C. Tan, T. Shi, Z. Li, Y. Jiang, M. Yasunaga, S. Shim, T. Chen, A. Fabbri, Z. Li, L. Chen, Y. Zhang, S. Dixit, V. Zhang, C. Xiong, R. Socher, W. Lasecki, 和 D. Radev，“CoSQL：一个面向跨领域自然语言接口的对话式文本到 SQL 挑战”，发表于*自然语言处理中的实证方法和国际自然语言处理联合会议 (EMNLP-IJCNLP)*，2019 年。

+   [36] C.-H. Lee, O. Polozov, 和 M. Richardson，“KaggleDBQA：文本到 SQL 解析器的现实评估”，发表于*计算语言学协会和国际自然语言处理联合会议 (ACL-IJCNLP)*，2021 年。

+   [37] X. Pi, B. Wang, Y. Gao, J. Guo, Z. Li, 和 J.-G. Lou，“提升文本到 SQL 模型在自然和现实对抗性表扰动下的鲁棒性”，发表于*计算语言学协会 (ACL)*，2022 年。

+   [38] Y. Gan, X. Chen, Q. Huang, 和 M. Purver，“通过组件对齐测量和提升文本到 SQL 的组合泛化能力”，发表于*北美计算语言学协会发现 (NAACL)*，2022 年。

+   [39] Y. Gan, X. Chen, 和 M. Purver，“探索跨领域文本到 SQL 泛化的未被充分研究的限制”，发表于*自然语言处理中的实证方法 (EMNLP)*，2021 年。

+   [40] Y. Gan, X. Chen, Q. Huang, M. Purver, J. R. Woodward, J. Xie, 和 P. Huang，“提升文本到 SQL 模型在同义词替换下的鲁棒性”，发表于*计算语言学协会和国际自然语言处理联合会议 (ACL-IJCNLP)*，2021 年。

+   [41] X. Deng, A. H. Awadallah, C. Meek, O. Polozov, H. Sun, 和 M. Richardson，“基于结构的文本到 SQL 预训练”，发表于*北美计算语言学协会：人类语言技术 (NAACL-HLT)*，2021 年。

+   [42] Q. Min, Y. Shi, 和 Y. Zhang，“中文 SQL 语义解析的初步研究”，发表于*自然语言处理中的实证方法和国际自然语言处理联合会议 (EMNLP-IJCNLP)*，2019 年。

+   [43] T. Yu, R. Zhang, M. Yasunaga, Y. C. Tan, X. V. Lin, S. Li, H. Er, I. Li, B. Pang, T. Chen, E. Ji, S. Dixit, D. Proctor, S. Shim, J. Kraft, V. Zhang, C. Xiong, R. Socher, 和 D. Radev，“SParC：跨领域上下文中的语义解析”，发表于*计算语言学协会 (ACL)*，2019 年。

+   [44] T. Shi, C. Zhao, J. Boyd-Graber, H. Daumé III, 和 L. Lee，“词汇-逻辑对齐在 SQL 查询语义解析中的潜力”，发表于*自然语言处理中的实证方法发现 (EMNLP)*，2020 年。

+   [45] S. Xue, C. Jiang, W. Shi, F. Cheng, K. Chen, H. Yang, Z. Zhang, J. He, H. Zhang, G. Wei, W. Zhao, F. Zhou, D. Qi, H. Yi, S. Liu, 和 F. Chen，“Db-gpt：通过私人大型语言模型赋能数据库交互，” *arXiv 预印本 arXiv:2312.17449*，2024 年。

+   [46] B. Zhang, Y. Ye, G. Du, X. Hu, Z. Li, S. Yang, C. H. Liu, R. Zhao, Z. Li, 和 H. Mao，“大型语言模型的文本到 SQL 能力基准测试：综合评估，” *arXiv 预印本 arXiv:2403.02951*，2024 年。

+   [47] S. Chang 和 E. Fosler-Lussier，“如何提示 LLMs 进行文本到 SQL：零样本、单领域和跨领域设置的研究，” 发表在 *NeurIPS 2023 第二届表格表示学习研讨会（NeurIPS）*，2023 年。

+   [48] X. Chen, M. Lin, N. Schärli, 和 D. Zhou，“教大型语言模型自我调试，” 发表在 *国际学习表征会议（ICLR）*，2024 年。

+   [49] H. Zhang, R. Cao, L. Chen, H. Xu, 和 K. Yu，“ACT-SQL：用于文本到 SQL 的上下文学习与自动生成的思维链，” 发表在 *自然语言处理实证方法发现（EMNLP）*，2023 年。

+   [50] F. Xu, Z. Wu, Q. Sun, S. Ren, F. Yuan, S. Yuan, Q. Lin, Y. Qiao, 和 J. Liu，“Symbol-llm：面向大型语言模型的基础符号中心接口，” *arXiv 预印本 arXiv:2311.09278*，2024 年。

+   [51] C.-Y. Tai, Z. Chen, T. Zhang, X. Deng, 和 H. Sun，“探索思维链风格提示的文本到 SQL，” 发表在 *自然语言处理实证方法（EMNLP）*，2023 年。

+   [52] L. Nan, Y. Zhao, W. Zou, N. Ri, J. Tae, E. Zhang, A. Cohan, 和 D. Radev，“提升大型语言模型的文本到 SQL 能力：关于提示设计策略的研究，” 发表在 *自然语言处理实证方法发现（EMNLP）*，2023 年。

+   [53] R. Sun, S. O. Arik, H. Nakhost, H. Dai, R. Sinha, P. Yin, 和 T. Pfister， “Sql-palm: 改进的大型语言模型适应文本到 SQL，” *arXiv 预印本 arXiv:2306.00739*，2023 年。

+   [54] S. Chang 和 E. Fosler-Lussier，“跨领域文本到 SQL 的选择性示范，” 发表在 *自然语言处理实证方法发现（EMNLP）*，2023 年。

+   [55] H. Xia, F. Jiang, N. Deng, C. Wang, G. Zhao, R. Mihalcea, 和 Y. Zhang，“Sql-craft：通过交互式优化和增强推理的文本到 SQL，” *arXiv 预印本 arXiv:2402.14851*，2024 年。

+   [56] T. Zhang, T. Yu, T. B. Hashimoto, M. Lewis, W. tau Yih, D. Fried, 和 S. I. Wang，“代码生成的代码审阅器重排序，” 发表在 *国际机器学习会议（ICML）*，2023 年。

+   [57] B. Wang, C. Ren, J. Yang, X. Liang, J. Bai, L. Chai, Z. Yan, Q.-W. Zhang, D. Yin, X. Sun, 和 Z. Li，“Mac-sql：一种多代理协作框架用于文本到 SQL，” *arXiv 预印本 arXiv:2312.11242*，2024 年。

+   [58] Y. Xie, X. Jin, T. Xie, M. Lin, L. Chen, C. Yu, L. Cheng, C. Zhuo, B. Hu, 和 Z. Li，“增强注意力的分解：通过工作流范式改进基于 LLM 的文本到 SQL，” *arXiv 预印本 arXiv:2402.10671*，2024 年。

+   [59] Y. Fan, Z. He, T. Ren, C. Huang, Y. Jing, K. Zhang, 和 X. S. Wang，“Metasql: 一种生成-排序框架用于自然语言到 SQL 翻译，” 2024 年。

+   [60] Z. Li, X. Wang, J. Zhao, S. Yang, G. Du, X. Hu, B. Zhang, Y. Ye, Z. Li, R. Zhao, 和 H. Mao，“Pet-sql: 一种增强提示的双阶段文本到 SQL 框架，具有交叉一致性，” *arXiv 预印本 arXiv:2403.09732*，2024 年。

+   [61] T. Ren, Y. Fan, Z. He, R. Huang, J. Dai, C. Huang, Y. Jing, K. Zhang, Y. Yang, 和 X. S. Wang，“Purple: 使大型语言模型成为更好的 SQL 编写者，” 在*国际数据工程会议 (ICDE)*，2024 年。

+   [62] C. Guo, Z. Tian, J. Tang, P. Wang, Z. Wen, K. Yang, 和 T. Wang，“对 GPT-3.5 的文本到 SQL 提示，结合去语义化和骨架检索，” 在*亚太人工智能国际会议 (PRICAI)*，2024 年。

+   [63] J. Jiang, K. Zhou, Z. Dong, K. Ye, X. Zhao, 和 J.-R. Wen，“StructGPT: 大型语言模型推理结构化数据的通用框架，” 在*自然语言处理实证方法 (EMNLP)*，2023 年。

+   [64] C. Guo, Z. Tian, J. Tang, S. Li, Z. Wen, K. Wang, 和 T. Wang，“基于 GPT-3.5 的检索增强文本到 SQL 框架，带有样本感知提示和动态修订链，” 在*国际神经信息处理会议 (ICONIP)*，2024 年。

+   [65] D. Wang, L. Dou, X. Zhang, Q. Zhu, 和 W. Che，“通过无人工融合提升示例多样性用于文本到 SQL，” *arXiv 预印本 arXiv:2402.10663*，2024 年。

+   [66] Y. Gu, Y. Shu, H. Yu, X. Liu, Y. Dong, J. Tang, J. Srinivasa, H. Latapie, 和 Y. Su，“llms 的中间件：工具在复杂环境中的语言代理中的作用，” *arXiv 预印本 arXiv:2402.14672*，2024 年。

+   [67] F. Shi, D. Fried, M. Ghazvininejad, L. Zettlemoyer, 和 S. I. Wang，“自然语言到代码的翻译与执行，” 在*自然语言处理实证方法 (EMNLP)*，2022 年。

+   [68] A. Ni, S. Iyer, D. Radev, V. Stoyanov, W.-t. Yih, S. I. Wang, 和 X. V. Lin，“Lever: 学习通过执行验证语言到代码生成，” 在*国际机器学习会议 (ICML)*，2023 年。

+   [69] S. Kou, L. Hu, Z. He, Z. Deng, 和 H. Zhang，“Cllms: 一致性大型语言模型，” *arXiv 预印本 arXiv:2403.00835*，2024 年。

+   [70] A. Zhuang, G. Zhang, T. Zheng, X. Du, J. Wang, W. Ren, S. W. Huang, J. Fu, X. Yue, 和 W. Chen，“Structlm: 朝着构建通用模型以支持结构化知识基础，” *arXiv 预印本 arXiv:2402.16671*，2024 年。

+   [71] M. Pourreza 和 D. Rafiei，“Dts-sql: 使用小型大型语言模型进行分解的文本到 SQL 转换，” *arXiv 预印本 arXiv:2402.01117*，2024 年。

+   [72] D. Xu, W. Chen, W. Peng, C. Zhang, T. Xu, X. Zhao, X. Wu, Y. Zheng, 和 E. Chen，“生成信息提取的大型语言模型：综述，” *arXiv 预印本 arXiv:2312.17617*，2023 年。

+   [73] G. Katsogiannis-Meimarakis 和 G. Koutrika，“文本到 SQL 的深度学习方法综述，” *VLDB 期刊*，2023 年。

+   [74] N. Deng、Y. Chen 和 Y. Zhang，“文本到 SQL 的最新进展：我们所拥有的和期望的调查”，发表于 *国际计算语言学会议（COLING）*，2022 年。

+   [75] P. Ma 和 S. Wang，“Mt-teql：评估和增强真实世界语言和模式变体中的神经 NLIDB”，发表于 *国际大数据会议（VLDB）*，2021 年。

+   [76] P. Rajpurkar、J. Zhang、K. Lopyrev 和 P. Liang，“SQuAD：用于机器理解文本的 100,000+ 问题”，发表于 *自然语言处理实证方法（EMNLP）*，2016 年。

+   [77] P. Rajpurkar、R. Jia 和 P. Liang，“了解你不知道的：SQuAD 的无法回答的问题”，发表于 *计算语言学协会（ACL）*，2018 年。

+   [78] H. Yang、Y. Zhang、J. Xu、H. Lu、P.-A. Heng 和 W. Lam，“揭示微调大型语言模型的泛化能力”，发表于 *北美计算语言学协会：人类语言技术（NAACL-HLT）*，2024 年。

+   [79] S. Hochreiter 和 J. Schmidhuber，“长短期记忆”，*神经计算*，1997 年。

+   [80] J. Guo、Z. Zhan、Y. Gao、Y. Xiao、J.-G. Lou、T. Liu 和 D. Zhang，“在跨域数据库中实现复杂的文本到 SQL 的中间表示”，*arXiv 预印本 arXiv:1905.08205*，2019 年。

+   [81] X. Xu、C. Liu 和 D. Song，“Sqlnet：从自然语言生成结构化查询无需强化学习”，*arXiv 预印本 arXiv:1711.04436*，2017 年。

+   [82] Y. Liu、M. Ott、N. Goyal、J. Du、M. Joshi、D. Chen、O. Levy、M. Lewis、L. Zettlemoyer 和 V. Stoyanov，“Roberta：一种强健优化的 BERT 预训练方法”，*arXiv 预印本 arXiv:1907.11692*，2019 年。

+   [83] L. Dou、Y. Gao、X. Liu、M. Pan、D. Wang、W. Che、D. Zhan、M.-Y. Kan 和 J.-G. Lou，“通过公式知识实现知识密集型文本到 SQL 的语义解析”，发表于 *自然语言处理实证方法（EMNLP）*，2022 年。

+   [84] A. Radford、K. Narasimhan、T. Salimans、I. Sutskever *等*，“通过生成预训练提高语言理解”，*OpenAI 博客*，2018 年。

+   [85] T. Brown、B. Mann、N. Ryder、M. Subbiah、J. D. Kaplan、P. Dhariwal、A. Neelakantan、P. Shyam、G. Sastry、A. Askell、S. Agarwal、A. Herbert-Voss、G. Krueger、T. Henighan、R. Child、A. Ramesh、D. Ziegler、J. Wu、C. Winter、C. Hesse、M. Chen、E. Sigler、M. Litwin、S. Gray、B. Chess、J. Clark、C. Berner、S. McCandlish、A. Radford、I. Sutskever 和 D. Amodei，“语言模型是少样本学习者”，发表于 *神经信息处理系统进展（NeurIPS）*，2020 年。

+   [86] J. Achiam、S. Adler、S. Agarwal、L. Ahmad、I. Akkaya、F. L. Aleman、D. Almeida、J. Altenschmidt、S. Altman、S. Anadkat *等*，“Gpt-4 技术报告”，*arXiv 预印本 arXiv:2303.08774*，2023 年。

+   [87] P. Sahoo、A. K. Singh、S. Saha、V. Jain、S. Mondal 和 A. Chadha，“大型语言模型中提示工程的系统性调查：技术与应用”，*arXiv 预印本 arXiv:2402.07927*，2024 年。

+   [88] J. Wang, E. Shi, S. Yu, Z. Wu, C. Ma, H. Dai, Q. Yang, Y. Kang, J. Wu, H. Hu *等*，“医疗保健的提示工程：方法论与应用，” *arXiv 预印本 arXiv:2304.14670*，2023 年。

+   [89] B. Chen, Z. Zhang, N. Langrené, 和 S. Zhu, “释放大型语言模型中的提示工程潜力：全面回顾，” *arXiv 预印本 arXiv:2310.14735*，2023 年。

+   [90] J. Wei, M. Bosma, V. Y. Zhao, K. Guu, A. W. Yu, B. Lester, N. Du, A. M. Dai, 和 Q. V. Le, “微调语言模型是零样本学习者，” *arXiv 预印本 arXiv:2109.01652*，2021 年。

+   [91] Y. Zheng, R. Zhang, J. Zhang, Y. Ye, 和 Z. Luo, “Llamafactory: 100+语言模型的统一高效微调，” *arXiv 预印本 arXiv:2403.13372*，2024 年。

+   [92] T. Wang, H. Lin, X. Han, L. Sun, X. Chen, H. Wang, 和 Z. Zeng, “Dbcopilot: 将自然语言查询扩展到大规模数据库，” *arXiv 预印本 arXiv:2312.03463*，2023 年。

+   [93] H. Touvron, T. Lavril, G. Izacard, X. Martinet, M.-A. Lachaux, T. Lacroix, B. Rozière, N. Goyal, E. Hambro, F. Azhar *等*，“Llama: 开放且高效的基础语言模型，” *arXiv 预印本 arXiv:2302.13971*，2023 年。

+   [94] H. Touvron, L. Martin, K. Stone, P. Albert, A. Almahairi, Y. Babaei, N. Bashlykov, S. Batra, P. Bhargava, S. Bhosale *等*，“Llama 2: 开放基础和微调聊天模型，” *arXiv 预印本 arXiv:2307.09288*，2023 年。

+   [95] J. Bai, S. Bai, Y. Chu, Z. Cui, K. Dang, X. Deng, Y. Fan, W. Ge, Y. Han, F. Huang *等*，“Qwen 技术报告，” *arXiv 预印本 arXiv:2309.16609*，2023 年。

+   [96] A. Radford, J. Wu, R. Child, D. Luan, D. Amodei, I. Sutskever *等*，“语言模型是无监督的多任务学习者，” *OpenAI 博客*，2019 年。

+   [97] L. Reynolds 和 K. McDonell, “大型语言模型的提示编程：超越少样本范式，” 收录于 *计算机系统人因会议（CHI）*，2021 年。

+   [98] X. Ye 和 G. Durrett, “在少样本提示中解释的不可靠性，” 收录于 *神经信息处理系统进展（NeurIPS）*，2022 年。

+   [99] C. Raffel, N. Shazeer, A. Roberts, K. Lee, S. Narang, M. Matena, Y. Zhou, W. Li, 和 P. J. Liu, “通过统一的文本到文本转换器探索迁移学习的极限，” *机器学习研究杂志（JMLR）*，2020 年。

+   [100] M. Chen, J. Tworek, H. Jun, Q. Yuan, H. P. d. O. Pinto, J. Kaplan, H. Edwards, Y. Burda, N. Joseph, G. Brockman *等*，“评估训练于代码的大型语言模型，” *arXiv 预印本 arXiv:2107.03374*，2021 年。

+   [101] P. P. Ray, “Chatgpt: 关于背景、应用、关键挑战、偏见、伦理、局限性及未来范围的全面回顾，” *物联网与网络物理系统*，2023 年。

+   [102] J. Zamfirescu-Pereira, R. Y. Wong, B. Hartmann, 和 Q. Yang, “为什么 Johnny 不能提示：非人工智能专家如何尝试（和失败）设计 LLM 提示，” 收录于 *计算机系统人因会议（CHI）*，2023 年。

+   [103] J. Wei, X. Wang, D. Schuurmans, M. Bosma, F. Xia, E. Chi, Q. V. Le 和 D. Zhou，“思维链提示引发大语言模型的推理”，发表于*神经信息处理系统进展（NeurIPS）*，2022 年。

+   [104] D. Zhou, N. Schärli, L. Hou, J. Wei, N. Scales, X. Wang, D. Schuurmans, C. Cui, O. Bousquet, Q. Le *等*，“最少到最多的提示使大语言模型能够进行复杂推理”，*arXiv 预印本 arXiv:2205.10625*，2022 年。

+   [105] W. Lei, W. Wang, Z. Ma, T. Gan, W. Lu, M.-Y. Kan 和 T.-S. Chua，“重新审视模式链接在文本到 SQL 中的作用”，发表于*自然语言处理经验方法（EMNLP）*，2020 年。

+   [106] Q. Liu, D. Yang, J. Zhang, J. Guo, B. Zhou 和 J.-G. Lou，“从预训练语言模型中唤醒潜在的基础语义进行语义解析”，发表于*计算语言学协会成果（ACL）*，2021 年。

+   [107] Z. Tan, X. Liu, Q. Shu, X. Li, C. Wan, D. Liu, Q. Wan 和 G. Liao，“通过定制提示提升大语言模型的文本到 SQL 能力”，发表于*国际计算语言学会议、语言资源与评估（LREC-COLING）*，2024 年。

+   [108] J. Huang 和 K. C.-C. Chang，“大语言模型中的推理：综述”，发表于*计算语言学协会成果（ACL）*，2023 年。

+   [109] W. Chen, X. Ma, X. Wang 和 W. W. Cohen，“思维提示程序：将计算与推理分离以应对数值推理任务”，*机器学习研究交易（TMLR）*，2023 年。

+   [110] X. Wang, J. Wei, D. Schuurmans, Q. V. Le, E. H. Chi, S. Narang, A. Chowdhery 和 D. Zhou，“自一致性提高语言模型中的思维链推理”，发表于*学习表示国际会议（ICLR）*，2023 年。

+   [111] M. Müller 和 R. Sennrich，“理解神经机器翻译中最小贝叶斯风险解码的属性”，发表于*计算语言学协会与国际自然语言处理联合会议（ACL-IJCNLP）*，2021 年。

+   [112] R. Rafailov, A. Sharma, E. Mitchell, C. D. Manning, S. Ermon 和 C. Finn，“直接偏好优化：你的语言模型实际上是奖励模型”，发表于*神经信息处理系统进展（NeurIPS）*，2023 年。

+   [113] G. Team, T. Mesnard, C. Hardin, R. Dadashi, S. Bhupatiraju, S. Pathak, L. Sifre, M. Rivière, M. S. Kale, J. Love *等*，“Gemma：基于双子研究和技术的开放模型”，*arXiv 预印本 arXiv:2403.08295*，2024 年。

+   [114] L. Ouyang, J. Wu, X. Jiang, D. Almeida, C. Wainwright, P. Mishkin, C. Zhang, S. Agarwal, K. Slama, A. Ray *等*，“通过人类反馈训练语言模型以遵循指令”，发表于*神经信息处理系统进展（NeurIPS）*，2022 年。

+   [115] Y. Leviathan, M. Kalman 和 Y. Matias，“通过投机解码实现变换器的快速推理”，发表于*国际机器学习大会（ICML）*，2023 年。

+   [116] C. Chen, S. Borgeaud, G. Irving, J.-B. Lespiau, L. Sifre, 和 J. Jumper，"通过推测性采样加速大语言模型的解码"，*arXiv 预印本 arXiv:2302.01318*，2023 年。

+   [117] H. Song, M. Kim, D. Park, Y. Shin, 和 J.-G. Lee，"使用深度神经网络从噪声标签中学习：一项综述"，*IEEE 神经网络与学习系统汇刊（TNNLS）*，2023 年。

+   [118] D. Erhan, A. Courville, Y. Bengio, 和 P. Vincent，"为什么无监督预训练有助于深度学习？"，发表于 *人工智能与统计（AISTATS）*，2010 年。

+   [119] Y. Liu, T. Han, S. Ma, J. Zhang, Y. Yang, J. Tian, H. He, A. Li, M. He, Z. Liu *等*，"ChatGPT 相关研究综述及对大语言模型未来的展望"，*Meta-Radiology*，2023 年。

+   [120] Anthropic，"介绍 Claude"，2023 年。

+   [121] B. Roziere, J. Gehring, F. Gloeckle, S. Sootla, I. Gat, X. E. Tan, Y. Adi, J. Liu, T. Remez, J. Rapin *等*，"Code llama：开放的代码基础模型"，*arXiv 预印本 arXiv:2308.12950*，2023 年。

+   [122] R. Li, L. B. allal, Y. Zi, N. Muennighoff, D. Kocetkov, C. Mou, M. Marone, C. Akiki, J. LI, J. Chim, Q. Liu, E. Zheltonozhskii, T. Y. Zhuo, T. Wang, O. Dehaene, J. Lamy-Poirier, J. Monteiro, N. Gontier, M.-H. Yee, L. K. Umapathi, J. Zhu, B. Lipkin, M. Oblokulov, Z. Wang, R. Murthy, J. T. Stillerman, S. S. Patel, D. Abulkhanov, M. Zocca, M. Dey, Z. Zhang, U. Bhattacharyya, W. Yu, S. Luccioni, P. Villegas, F. Zhdanov, T. Lee, N. Timor, J. Ding, C. S. Schlesinger, H. Schoelkopf, J. Ebert, T. Dao, M. Mishra, A. Gu, C. J. Anderson, B. Dolan-Gavitt, D. Contractor, S. Reddy, D. Fried, D. Bahdanau, Y. Jernite, C. M. Ferrandis, S. Hughes, T. Wolf, A. Guha, L. V. Werra, 和 H. de Vries，"Starcoder：愿源代码与你同在！"，*机器学习研究汇刊（TMLR）*，2023 年。

+   [123] Y. Wang, W. Zhong, L. Li, F. Mi, X. Zeng, W. Huang, L. Shang, X. Jiang, 和 Q. Liu，"将大语言模型与人类对齐：一项综述"，*arXiv 预印本 arXiv:2307.12966*，2023 年。

+   [124] A. Tuan Nguyen, M. H. Dao, 和 D. Q. Nguyen，"越南语文本到 SQL 语义解析的初步研究"，发表于 *自然语言处理实证方法发现（EMNLP）*，2020 年。

+   [125] Y. Song, R. C.-W. Wong, 和 X. Zhao，"语音到 SQL：基于自然语言问题的语音驱动 SQL 查询生成"，*VLDB 杂志*，2024 年。

+   [126] B. Yan, K. Li, M. Xu, Y. Dong, Y. Zhang, Z. Ren, 和 X. Cheng，"保护大语言模型（LLMs）数据隐私：一项综述"，*arXiv 预印本 arXiv:2403.05156*，2024 年。

+   [127] C. Singh, J. P. Inala, M. Galley, R. Caruana, 和 J. Gao，"在大语言模型时代重新思考可解释性"，*arXiv 预印本 arXiv:2402.01761*，2024 年。

+   [128] D. Dai, L. Dong, Y. Hao, Z. Sui, B. Chang, 和 F. Wei，"预训练变换器中的知识神经元"，发表于 *计算语言学协会（ACL）*，2022 年。

+   [129] N. Zhang, Y. Yao, B. Tian, P. Wang, S. Deng, M. Wang, Z. Xi, S. Mao, J. Zhang, Y. Ni *等*，“对大型语言模型的知识编辑的全面研究，” *arXiv 预印本 arXiv:2401.01286*，2024。

+   [130] K. Meng, A. S. Sharma, A. J. Andonian, Y. Belinkov, 和 D. Bau, “在变换器中大规模编辑记忆，” 在 *学习表示国际会议 (ICLR)*，2023。

+   [131] K. Meng, D. Bau, A. Andonian, 和 Y. Belinkov, “定位和编辑 GPT 中的事实关联，” *神经信息处理系统进展 (NeurIPS)*，2022。

+   [132] C. Zheng, L. Li, Q. Dong, Y. Fan, Z. Wu, J. Xu, 和 B. Chang, “我们能通过上下文学习编辑事实知识吗？” 在 *自然语言处理经验方法 (EMNLP)*，2023。

+   [133] H. Luo, Z. Tang, S. Peng, Y. Guo, W. Zhang, C. Ma, G. Dong, M. Song, W. Lin *等*，“Chatkbqa: 一个生成后检索框架用于知识库问答，通过微调的大型语言模型，” *arXiv 预印本 arXiv:2310.08975*，2023。

+   [134] Z. Li, S. Fan, Y. Gu, X. Li, Z. Duan, B. Dong, N. Liu, 和 J. Wang, “Flexkbqa: 一个灵活的 LLM 驱动的少样本知识库问答框架，” 在 *人工智能会议 (AAAI)*，2024。

+   [135] G. Xiong, J. Bao, 和 W. Zhao, “Interactive-kbqa: 多轮交互用于大型语言模型的知识库问答，” *arXiv 预印本 arXiv:2402.15131*，2024。

+   [136] R. Anil, A. M. Dai, O. Firat, M. Johnson, D. Lepikhin, A. Passos, S. Shakeri, E. Taropa, P. Bailey, Z. Chen *等*，“Palm 2 技术报告，” *arXiv 预印本 arXiv:2305.10403*，2023。

+   [137] Z. Hong 和 J. Liu, “朝着更好的问题生成在基于 QA 的事件抽取中，” *arXiv 预印本 arXiv:2405.10517*，2024。

+   [138] Y. Liu, H. He, T. Han, X. Zhang, M. Liu, J. Tian, Y. Zhang, J. Wang, X. Gao, T. Zhong *等*，“理解 LLM: 从训练到推理的全面概述，” *arXiv 预印本 arXiv:2401.02038*，2024。

+   [139] A. Zeng, X. Liu, Z. Du, Z. Wang, H. Lai, M. Ding, Z. Yang, Y. Xu, W. Zheng, X. Xia, W. L. Tam, Z. Ma, Y. Xue, J. Zhai, W. Chen, Z. Liu, P. Zhang, Y. Dong, 和 J. Tang, “GLM-130b: 一个开放的双语预训练模型，” 在 *学习表示国际会议 (ICLR)*，2023。

+   [140] Q. Zhang, J. Dong, Q. Tan, 和 X. Huang, “集成实体属性以实现错误感知的知识图谱嵌入，” *IEEE 知识与数据工程汇刊 (TKDE)*，2024。

+   [141] Q. Zhang, J. Dong, H. Chen, X. Huang, D. Zha, 和 Z. Yu, “Knowgpt: 大型语言模型的黑箱知识注入，” *arXiv 预印本 arXiv:2312.06185*，2023。

+   [142] F. Huang, Z. Yang, J. Jiang, Y. Bei, Y. Zhang, 和 H. Chen, “用于冷启动项目推荐的大型语言模型交互模拟器，” *arXiv 预印本 arXiv:2402.09176*，2024。

+   [143] Y. Bei, H. Xu, S. Zhou, H. Chi, M. Zhang, Z. Li 和 J. Bu, “CPDG：动态图神经网络的对比预训练方法，” *arXiv 预印本 arXiv:2307.02813*，2023 年。

+   [144] Y. Bei, H. Chen, S. Chen, X. Huang, S. Zhou 和 F. Huang, “非递归集群尺度图交互模型用于点击率预测，” 发表在 *信息与知识管理国际会议 (CIKM)*，2023 年。

+   [145] H. Chen, Y. Bei, Q. Shen, Y. Xu, S. Zhou, W. Huang, F. Huang, S. Wang 和 X. Huang, “宏图神经网络用于在线亿级推荐系统，” 发表在 *国际万维网会议 (WWW)*，2024 年。

+   [146] X. Chen, T. Wang, T. Qiu, J. Qin 和 M. Yang, “Open-SQL 框架：提升开源大型语言模型上的文本到 SQL，” *arXiv 预印本 arXiv:2405.06674*，2024 年。

+   [147] S. Xue, D. Qi, C. Jiang, W. Shi, F. Cheng, K. Chen, H. Yang, Z. Zhang, J. He 和 H. Zhang *等*，“DB-GPT 演示：下一代数据交互系统由大型语言模型驱动，” *arXiv 预印本 arXiv:2404.10209*，2024 年。

+   [148] D. G. Thorpe, A. J. Duberstein 和 I. A. Kinsey, “Dubo-sql：多样化检索增强生成与微调用于文本到 SQL，” *arXiv 预印本 arXiv:2404.12560*，2024 年。

+   [149] A. Lozhkov, R. Li, L. B. Allal, F. Cassano, J. Lamy-Poirier, N. Tazi, A. Tang, D. Pykhtar, J. Liu, Y. Wei *等*，“Starcoder 2 和 Stack v2：下一代，” *arXiv 预印本 arXiv:2402.19173*，2024 年。

+   [150] W. Huang, X. Ma, H. Qin, X. Zheng, C. Lv, H. Chen, J. Luo, X. Qi, X. Liu 和 M. Magno, “低位量化 Llama3 模型表现如何？一项实证研究，” *arXiv 预印本 arXiv:2404.14047*，2024 年。

+   [151] G. Katsogiannis-Meimarakis 和 G. Koutrika, “对文本到 SQL 系统的深度学习方法的深入探讨，” 发表在 *数据管理会议 (SIGMOD)*，2021 年。

+   [152] A. Kumar, P. Nagarkar, P. Nalhe 和 S. Vijayakumar, “深度学习驱动的自然语言文本到 SQL 查询转换：综述，” *arXiv 预印本 arXiv:2208.04415*，2022 年。

生成于 2024 年 7 月 16 日 星期二 07:55:40，来自 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
