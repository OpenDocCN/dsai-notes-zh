<!--yml

类别: 未分类

日期: 2024-09-03 17:31:02

-->

# 大规模 LLM 服务的有效调用方法调查

> 来源：[`arxiv.org/html/2402.03408`](https://arxiv.org/html/2402.03408)

1.  [1 引言](https://arxiv.org/html/2402.03408v2#S1 "1 引言 ‣ 大规模 LLM 服务的有效调用方法调查")

1.  [2 背景](https://arxiv.org/html/2402.03408v2#S2 "2 背景 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [2.1 任务定义](https://arxiv.org/html/2402.03408v2#S2.SS1 "2.1 任务定义 ‣ 2 背景 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [2.2 LLM 服务调用框架](https://arxiv.org/html/2402.03408v2#S2.SS2 "2.2 LLM 服务调用框架 ‣ 2 背景 ‣ 大规模 LLM 服务的有效调用方法调查")

1.  [3 输入摘要](https://arxiv.org/html/2402.03408v2#S3 "3 输入摘要 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [3.1 句子简化](https://arxiv.org/html/2402.03408v2#S3.SS1 "3.1 句子简化 ‣ 3 输入摘要 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [3.2 提示优化](https://arxiv.org/html/2402.03408v2#S3.SS2 "3.2 提示优化 ‣ 3 输入摘要 ‣ 大规模 LLM 服务的有效调用方法调查")

1.  [4 语义缓存](https://arxiv.org/html/2402.03408v2#S4 "4 语义缓存 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [4.1 传统缓存](https://arxiv.org/html/2402.03408v2#S4.SS1 "4.1 传统缓存 ‣ 4 语义缓存 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [4.2 神经缓存](https://arxiv.org/html/2402.03408v2#S4.SS2 "4.2 神经缓存 ‣ 4 语义缓存 ‣ 大规模 LLM 服务的有效调用方法调查")

1.  [5 解决方案设计](https://arxiv.org/html/2402.03408v2#S5 "5 解决方案设计 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [5.1 评分函数](https://arxiv.org/html/2402.03408v2#S5.SS1 "5.1 评分函数 ‣ 5 解决方案设计 ‣ 大规模 LLM 服务的有效调用方法调查")

    1.  [5.2 LLM 路由器](https://arxiv.org/html/2402.03408v2#S5.SS2 "5.2 LLM 路由器 ‣ 5 解决方案设计 ‣ 大规模 LLM 服务的有效调用方法调查")

1.  [6 输出增强](https://arxiv.org/html/2402.03408v2#S6 "6 输出增强 ‣ 大规模 LLM 服务的有效调用方法调查")

1.  [7 结论与挑战](https://arxiv.org/html/2402.03408v2#S7 "7 结论与挑战 ‣ 大规模 LLM 服务的有效调用方法调查")

HTML 转换 [有时会显示错误](https://info.dev.arxiv.org/about/accessibility_html_error_messages.html)，这是由于内容未能正确从源文件转换。这篇论文使用了 HTML 转换工具尚不支持的以下包。对这些问题的反馈并非必要；这些问题已知并正在处理。

+   失败：森林

+   失败：newunicodechar

作者：通过遵循这些 [最佳实践](https://info.arxiv.org/help/submit_latex_best_practices.html) 从您的 LaTeX 提交中获得最佳 HTML 结果。

许可证：CC BY 4.0arXiv:2402.03408v2 [cs.SE] 2024 年 3 月 1 日

￥¥

# 大规模语言模型服务的有效调用方法调研

王${}^{1}$    张博林${}^{1}$    隋电博${}^{1}$    涂智英${}^{1}$ 通讯作者。    刘晓宇 ${}^{1}$    康佳宝 ${}^{1}$    ${}^{1}$哈尔滨工业大学，

23B903072@stu.hit.edu.cn, {brolin, tzy_hit,suidianbo}@hit.edu.cn,

2201110719@stu.hit.edu.cn, 18538796936@163.com

###### 摘要

语言模型即服务（LMaaS）使用户无需专门知识即可完成任务，只需支付服务提供商费用。然而，许多提供商提供的大规模语言模型（LLM）服务在延迟、性能和定价上各不相同。因此，构建成本节省的 LLM 服务调用策略，确保低延迟和高性能响应以满足特定任务需求，成为一个迫切的挑战。本文提供了 LLM 服务调用方法的全面概述。从技术上讲，我们对 LMaaS 中构建有效调用策略的问题进行了正式定义，并提出了 LLM 服务调用框架。该框架将现有方法分类为四个不同的组件，包括输入抽象、语义缓存、解决方案设计和输出增强，这些组件可以自由组合。最后，我们强调了在这一任务中尚未得到很好解决的开放挑战，并对未来研究进行了展望。

## 1 引言

大规模语言模型（LLM）正成为各种自然语言处理任务的基础工具 杨等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib49))，它们展示了惊人的突现能力，如上下文学习、多步骤推理、指令跟随和工具学习。由于商业原因、潜在的误用风险和昂贵的调优成本，LLM，如 GPT-3、GPT-4 和 Claude，通常通过应用程序编程接口（API）作为 LLM 服务发布，而不是开源模型权重 余等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib51))，这被称为语言模型即服务（LMaaS）。

| 提供商 | LLM | 输入成本 | 输出成本 |
| --- | --- | --- | --- |
| [OpenAI](https://openai.com/pricing) | gpt-4 | $30.0 | $60.0 |
| gpt-4-turbo | $10.0 | $30.0 |
| gpt-3.5-turbo-1106 | $1.00 | $2.00 |
| [Anthropic](https://www-files.anthropic.com/production/images/model_pricing_july2023.pdf) | Claude-2.0 | $11.02 | $32.68 |
| Claude-instant-1.2 | $1.63 | $5.51 |
| [AI21](https://www.ai21.com/studio/pricing) | Jurassic-2 Ultra | $15.0 | $15.0 |
| Jurassic-2 Mid | $10.0 | $10.0 |
| Jurassic-2 Light | $3.00 | $3.00 |
| [Textsynth](https://textsynth.com/pricing.html) | M2M100 1.2B | $0.15 | $3.00 |
| GPT-J 6B | $0.20 | $5.00 |
| Falcon 7B | $0.20 | $5.00 |
| Mistral 7B | $0.20 | $2.00 |
| Llama2 7B | $0.20 | $2.00 |
| Flan-T5-XXL | $0.20 | $5.00 |
| Falcon 40B | $3.30 | $10.00 |
| [Cohere](https://textsynth.com/pricing.html) | command | $1.00 | $2.00 |
| command-light | $0.30 | $0.60 |
| [百度](https://cloud.baidu.com/doc/WENXINWORKSHOP/s/Blfmc9dlf) | Llama-2-13B-Chat | ￥6.00 | ￥6.00 |
| Llama-2-70B-Chat | ￥35.0 | ￥35.0 |
| ERNIE-Bot 4.0 | ￥150 | ￥300 |
| ChatGLM2-6B-32K | ￥4.00 | ￥4.00 |
| Llama-2-7B-Chat | ￥4.00 | ￥4.00 |
| ERNIE-Bot | ￥12.0 | ￥12.0 |
| BLOOMZ-7B | ￥4.00 | ￥4.00 |
| ERNIE-Bot-turbo-0922 | ￥8.00 | ￥12.0 |

表 1：不同 LMaaS 的价格列表。费用按每 100 万标记计价。请注意，百度的 LLM 服务以人民币（￥）计价，而其他 LLM 服务以美元（$）计价。数据更新至 2024 年 1 月 24 日。

通过访问这些强大的 LLM 服务及其开放 API，新手用户无需具备大量的计算资源和深度学习专业知识，只需通过制定特定任务的输入查询即可解决感兴趣的任务。然而，调用 LLM 服务并非免费，使用它们进行高吞吐量应用可能非常昂贵。根据 Claudia Slowik 的估算，支持 15000 个客户交互的 text-davinci-003 每月的费用可能超过$14,400。

通常，调用大型语言模型（LLM）服务的成本包括两个部分：（1）输入成本（与输入提示的长度成正比），（2）输出成本（与生成序列的长度成正比）。在表格[1](https://arxiv.org/html/2402.03408v2#S1.T1 "Table 1 ‣ 1 Introduction ‣ A Survey on Effective Invocation Methods of Massive LLM Services")中，我们展示了使用 25 种不同 LLM 服务的成本，这些服务来自一些顶级提供商，如 OpenAI、Anthropic、AI21 和 Textsynth。从表格中，我们可以发现不同 LLM 服务的成本可以相差两个数量级：例如，OpenAI 的 GPT-4 处理 100 万标记的输入成本为$10，而 Textsynth 提供的 Mistral 7B 仅为$0.2。

除了成本考虑外，各种因素，包括相同输入查询的性能和响应时间，也会影响 LLM 服务的用户体验。Ahia 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib1)）；Lai 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib21)）发现，不同的语言、提示方法或简单增强的加入也可能导致性能的显著变化。同时，Chen 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib13)）发现，经济型 LLM 通常能补充昂贵的 LLM。例如，在 CoQA Reddy 等人（[2019](https://arxiv.org/html/2402.03408v2#bib.bib35)）数据集上，GPT-4 在约 11%的问题上出错，而便宜且较小的 GPJ-J 能给出正确答案。

考虑到定价的异质性不一定与用户体验相关，因此有必要探索在实践中对 LLM 服务进行有效调用的方法。如图[1](https://arxiv.org/html/2402.03408v2#S1.F1 "Figure 1 ‣ 1 Introduction ‣ A Survey on Effective Invocation Methods of Massive LLM Services")所示，我们期望利用大规模 LLM 服务根据不同的方法构建有效的调用策略，以在不同场景中实现目标。为此，我们尝试对 LMaaS 中有效调用方法的发展及最新进展进行全面研究。具体而言，我们首先将构建有效调用策略的任务形式化为一个多目标优化问题。这涉及到延迟、性能和成本因素的综合考虑。然后，我们提出了一种分类法，以提供对 LMaaS 中有效调用方法的统一视角，其中现有方法被分类为：输入抽象、语义缓存、解决方案设计和输出增强。这四个组件可以在灵活的框架中灵活组合和统一。最后，我们突出了挑战和潜在方向，希望我们的工作能为有兴趣的初学者提供有用的路线图，并为未来的研究提供启示。

![参考标题](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：大规模 LLM 服务高效调用策略构建的愿景。

{forest}

分叉边，树=grow=east，反向=true，锚点=base west，父锚点=east，子锚点=west，基础=left，字体=，矩形，绘制=hidden-draw，圆角，对齐=left，最小宽度=4em，边+=darkgray，线宽=1pt，s sep=3pt，内部 xsep=2pt，内部 ysep=3pt，线宽=0.8pt，ver/.style=旋转=90，子锚点=north，父锚点=south，锚点=center，，其中 level=1text width=7.4em,font=，，其中 level=2text width=8.5em,font=，，其中 level=3text width=5.8em,font=，，其中 level=4text width=5em,font=，，[ 调用策略，ver [ 输入

抽象 (§[3](https://arxiv.org/html/2402.03408v2#S3 "3 输入摘要 ‣ 大规模 LLM 服务有效调用方法调查")) [ 句子

简化 (§[3.1](https://arxiv.org/html/2402.03408v2#S3.SS1 "3.1 句子简化 ‣ 3 输入摘要 ‣ 大规模 LLM 服务有效调用方法调查")) [ 提取

方法 [ TCRA-LLM Liu 等人 ([2023a](https://arxiv.org/html/2402.03408v2#bib.bib23)), Mondrian Si 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib42)),

学习的 Token 剪枝（LTP）Kim 等人 ([2022](https://arxiv.org/html/2402.03408v2#bib.bib20)), , leaf, text width=25em ] ] [ 生成

方法 [ 商业模型 Ahia 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib1)), TCRA-LLM Liu 等人 ([2023a](https://arxiv.org/html/2402.03408v2#bib.bib23)),

OverPrompt Li 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib22)) , leaf, text width=30em ] ] ] [ 提示

优化 (§[3.2](https://arxiv.org/html/2402.03408v2#S3.SS2 "3.2 提示优化 ‣ 3 输入摘要 ‣ 大规模 LLM 服务有效调用方法调查")) [ 提示

选择 [ LeanContext Arefeen 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib5)), 成本有效 L Zhou 等人 ([2020](https://arxiv.org/html/2402.03408v2#bib.bib54)),

Frugal-Prompting Santra 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib39)) , leaf, text width=30em ] ] [ 提示

扩增 [ 黑箱调整 Yu 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib51)), 成本有效 L Zhou 等人 ([2020](https://arxiv.org/html/2402.03408v2#bib.bib54)),

Vision-Transformer Haurum 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib15)), 事实一致性 Liu 等人 ([2023c](https://arxiv.org/html/2402.03408v2#bib.bib25)),

Chain-of-Thought Wu 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib47)) , leaf, text width=34em ] ] ] ] [ 语义

技术 (§[4](https://arxiv.org/html/2402.03408v2#S4 "4 语义缓存 ‣ 大规模 LLM 服务有效调用方法调查")) [ 传统

缓存 (§[4.1](https://arxiv.org/html/2402.03408v2#S4.SS1 "4.1 传统缓存 ‣ 4 语义缓存 ‣ 大规模 LLM 服务有效调用方法调查")) [ GPTCache Bang ([2023](https://arxiv.org/html/2402.03408v2#bib.bib7)), 基于检索的对话 Tao 等人 ([2021](https://arxiv.org/html/2402.03408v2#bib.bib43)),

服务缓存 Barrios 和 Kumar ([2024](https://arxiv.org/html/2402.03408v2#bib.bib8)), 最优缓存 Zhu 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib55)) , leaf, text width=34em ] ] [ 神经

缓存 (§[4.2](https://arxiv.org/html/2402.03408v2#S4.SS2 "4.2 神经缓存 ‣ 4 语义缓存 ‣ 大规模 LLM 服务有效调用方法调查")) [ 缓存-蒸馏 Ramírez 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib32)), VaryGen Rasool 等人 ([2024](https://arxiv.org/html/2402.03408v2#bib.bib33)),

基于检索的对话 Tao 等人 ([2021](https://arxiv.org/html/2402.03408v2#bib.bib43))，leaf，文本宽度=30em ] ] ] [ 解决方案

设计 (§[5](https://arxiv.org/html/2402.03408v2#S5 "5 解决方案设计 ‣ 关于大规模 LLM 服务的有效调用方法的调查")) [ 评分

功能 (§[5.1](https://arxiv.org/html/2402.03408v2#S5.SS1 "5.1 评分函数 ‣ 5 解决方案设计 ‣ 关于大规模 LLM 服务的有效调用方法的调查")) [ 定义

度量 [ Cache-Distil Ramírez 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib32))，MOT Yue 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib52))，

最优缓存 Zhu 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib55))，Reward-guided Lu 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib26))，leaf，文本宽度=30em ] ] [ 评分者 [ FrugalGPT Chen 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib13))，FORC Sakota 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib38))，

Model-Routing Shnitzer 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib41))，EcoAssistant Zhang 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib53))，

HYBRID LLM 匿名 ([2024](https://arxiv.org/html/2402.03408v2#bib.bib3))，AutoMix Madaan 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib28))，leaf，文本宽度=32em ] ] ] [ LLMs

路由器 (§[5.2](https://arxiv.org/html/2402.03408v2#S5.SS2 "5.2 LLM 路由器 ‣ 5 解决方案设计 ‣ 关于大规模 LLM 服务的有效调用方法的调查")) [ 顺序

结构 [ FrugalGPT Chen 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib13))，Cache-Distil Ramírez 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib32))，

MOT Yue 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib52))，EcoAssistant Zhang 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib53))，leaf，文本宽度=28em ] ] [ 其他

结构 [ LLM-Blender Jiang 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib19))，BRANCH-SOLVE-MERGE Saha 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib37))，

FORC Sakota 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib38))，Reward-guided Lu 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib26))，

AutoMix Madaan 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib28))，MCDM Hosseinzadeh 等人 ([2020](https://arxiv.org/html/2402.03408v2#bib.bib16))，

服务选择 Manqele 等人 ([2017](https://arxiv.org/html/2402.03408v2#bib.bib29))，leaf，文本宽度=34em ] ] ] ] [ 输出

增强 (§[6](https://arxiv.org/html/2402.03408v2#S6 "6 输出增强 ‣ 关于大规模 LLM 服务的有效调用方法的调查")) [ Prompt-survey Liu 等人 ([2023b](https://arxiv.org/html/2402.03408v2#bib.bib24))，FrugalMCT Chen 等人 ([2022](https://arxiv.org/html/2402.03408v2#bib.bib12))，Aligh-suevey Shen 等人 ([2023](https://arxiv.org/html/2402.03408v2#bib.bib40))，leaf，文本宽度=44em ] ] ]

图 2: LMaaS 有效调用方法的分类

本次调查的贡献总结如下：

+   •

    综合分类。如图[2](https://arxiv.org/html/2402.03408v2#S1.F2 "Figure 2 ‣ 1 Introduction ‣ A Survey on Effective Invocation Methods of Massive LLM Services")所示，提出了 LMaaS 有效调用方法的分类，从输入摘要、语义缓存、解决方案设计和输出增强四个不同方面对现有方法进行分类。

+   •

    灵活框架。如图[3](https://arxiv.org/html/2402.03408v2#S2.F3 "Figure 3 ‣ 2.2 LLM Services Invocation Framework ‣ 2 Background ‣ A Survey on Effective Invocation Methods of Massive LLM Services")所示，该框架可以统一四种类型的组件，使它们在 LLM 服务调用生命周期中可以独立或同时工作。

+   •

    相关资源。为了方便该任务的方法，流行 LMaaS 产品的价格规则列在表[1](https://arxiv.org/html/2402.03408v2#S1.T1 "Table 1 ‣ 1 Introduction ‣ A Survey on Effective Invocation Methods of Massive LLM Services")中，现有工作的论文列表可用。¹¹1[`github.com/W-caner/Effective-strategy-for-LMaas`](https://github.com/W-caner/Effective-strategy-for-LMaas)

本文的其余部分组织如下。第[2](https://arxiv.org/html/2402.03408v2#S2 "2 Background ‣ A Survey on Effective Invocation Methods of Massive LLM Services")节描述了构建 LMaaS 有效调用策略的任务定义，并概述了统一的 LLM 服务调用框架。第[3](https://arxiv.org/html/2402.03408v2#S3 "3 Input Abstract ‣ A Survey on Effective Invocation Methods of Massive LLM Services")节回顾了输入摘要组件，第[4](https://arxiv.org/html/2402.03408v2#S4 "4 Semantic Cache ‣ A Survey on Effective Invocation Methods of Massive LLM Services")节回顾了语义缓存组件，第[5](https://arxiv.org/html/2402.03408v2#S5 "5 Solution Design ‣ A Survey on Effective Invocation Methods of Massive LLM Services")节回顾了解决方案设计组件，第[6](https://arxiv.org/html/2402.03408v2#S6 "6 Output Enhancement ‣ A Survey on Effective Invocation Methods of Massive LLM Services")节回顾了输出增强组件。第[7](https://arxiv.org/html/2402.03408v2#S7 "7 Conclusion and Challenges ‣ A Survey on Effective Invocation Methods of Massive LLM Services")节强调了该任务的开放挑战和未来方向，并总结了论文。

## 2 背景

### 2.1 任务定义

在我们的主题中，问题被定义为如何在大量 LLM 服务 $LLMs$ 中构建一个有效的（低延迟、高性能和节省成本的）调用策略 $s$，给定一个任务 $T$。给定的任务 $T$ 包含多个相同的查询-回答对，表示为 $T=\{(q_{1},a_{1}),(q_{2},a_{2}),...(q_{n},a_{n})\}$，其中 $q$ 代表输入查询，$a$ 代表输出答案。考虑一个固定的 $LLM$，通过 API 发布的 LLM 服务。输入一个查询 $q$，通过调用服务，获取响应 $\tilde{a}$ 的过程可以表示为：

|  | $\tilde{a}=LLM(q)$ |  | (1) |
| --- | --- | --- | --- |

为了描述给定查询 $q$ 和 LLM 服务 $LLM$ 时构建有效调用策略的关注点，我们使用三个函数：延迟 $f_{l}(LLM,q)$、性能 $f_{p}(LLM,q)$ 和成本 $f_{c}(LLM,q)$。这三个函数在特定的实际调用中是固定值，可以使用某些方法进行估算。例如，$f_{l}$ 可能是输入和输出令牌长度的函数。$f_{p}$ 通常使用度量函数 $r(·,·)$ 来比较 $a$ 和 $\tilde{a}$ 之间的差异。而 $f_{c}$ 涉及我们之前提到的两个不同的定价组件。我们采用的定义是输入令牌数量乘以输入令牌的价格与生成的令牌数量乘以生成令牌的价格之和，如 Eq. [2](https://arxiv.org/html/2402.03408v2#S2.E2 "2 ‣ 2.1 Task Definition ‣ 2 Background ‣ A Survey on Effective Invocation Methods of Massive LLM Services") 所示，其中 $\alpha_{i}$ 是表示单价的常数。

|  | $f_{c}\triangleq\alpha_{1}&#124;&#124;\tilde{a}&#124;&#124;+\alpha_{2}&#124;&#124;q&#124;&#124;+\alpha_{3}$ |  | (2) |
| --- | --- | --- | --- |

然后我们将单一的 LLM 服务扩展为 $K$ 个不同的 LLM 服务，$LLM_{s}=\{LLM_{1},LLM_{2},...LLM_{K}\}$。我们的问题被形式化为 Eq. [3](https://arxiv.org/html/2402.03408v2#S2.E3 "3 ‣ 2.1 Task Definition ‣ 2 Background ‣ A Survey on Effective Invocation Methods of Massive LLM Services")，在搜索空间 $S$ 中，我们寻求最优的调用策略 $s$，以最小化延迟 $f_{l}$、最大化性能 $f_{p}$ 并最小化任务 $T$ 的成本 $f_{c}$。最佳策略 $s$ 包括一系列选择的 LLM 服务，表示为 $s=\{LLM_{1},LLM_{i},...,LLM_{k}\},k\leq K$，具有很高的灵活性，例如选择单一服务或以特定顺序访问一些服务。

|  | $\min\sum_{LLM_{i}\in s,q_{j}\in T}F(f_{l}(LLM_{i},q_{j}),-f_{p}(LLM_{i},q_{j})% ,f_{c}(LLM_{i},q_{j}))$ |  | (3) |
| --- | --- | --- | --- |

这是一个多目标优化问题，在这里，我们通过使用函数$F$将它们以简化形式结合起来。在具体调用的构建策略中，可能会使用加权平均，或者引入约束，将某些目标作为条件，同时优化其他目标。例如，在资金有限的情况下，成本$f_{c}$作为条件来获得一个具有高性能$f_{p}$和低延迟$f_{l}$的调用策略。

### 2.2 LLM 服务调用框架

同样，我们只关注与 LLM 服务调用相关的方法，不考虑与 LLM 内部细节相关的其他方法。根据不同的构建方式，这些方法被总结为四类，如图[2](https://arxiv.org/html/2402.03408v2#S1.F2 "Figure 2 ‣ 1 Introduction ‣ A Survey on Effective Invocation Methods of Massive LLM Services")所示。

使用分类法，我们提出了一个有效的 LLM 服务调用框架，如图[3](https://arxiv.org/html/2402.03408v2#S2.F3 "Figure 3 ‣ 2.2 LLM Services Invocation Framework ‣ 2 Background ‣ A Survey on Effective Invocation Methods of Massive LLM Services")所示，其中不同的类别以组件形式表示，可以独立工作或同时工作。按照构建有效调用策略需要了解 LLM 服务生命周期中的关键资源的观点[Bai et al. ([2024](https://arxiv.org/html/2402.03408v2#bib.bib6))]，我们将 LLM 服务调用分为三个阶段：调用前、调用中和调用后。

在调用前，用户输入一个查询$q$，我们认为通常情况下，$q$由一个问题和多个可能的提示组成。问题代表用户的目标，而提示是帮助实现目标的可选信息。

处理输入查询$q$，以更简洁的语言表达更有意义的信息是构建有效调用策略的第一步。这方面的方法总结为输入抽象（第[3](https://arxiv.org/html/2402.03408v2#S3 "3 Input Abstract ‣ A Survey on Effective Invocation Methods of Massive LLM Services")节），根据不同的方式分为句子简化和提示优化。前者通过简化查询而不改变其语义来减少延迟$f_{l}$和成本$f_{c}$。后者则用于改进提示以获得更好的性能$f_{p}$。

语义缓存（第 [4](https://arxiv.org/html/2402.03408v2#S4 "4 Semantic Cache ‣ A Survey on Effective Invocation Methods of Massive LLM Services") 节）也是一种重要的策略，用于在调用之前提高服务性能、减少延迟和成本，按不同结构分为传统缓存和神经缓存。它检查缓存中是否存在语义上相似的查询，如果存在，则直接返回；否则进入调用阶段。

解决方案设计（第 [5](https://arxiv.org/html/2402.03408v2#S5 "5 Solution Design ‣ A Survey on Effective Invocation Methods of Massive LLM Services") 节）旨在通过利用大规模 LLM 服务的互补能力来构建最佳调用解决方案 $s$。它评估给定查询 $q$ 的 LLM 服务 $LLM_{i}$，评估方法称为评分函数。评分通常在调用之前进行，例如，$f_{c}$ 的估算可以用来指导低成本解决方案的设计。在调用阶段，评分函数用于指导服务之间的有序路由，这称为 LLM 路由器。通过不同的路由结构，利用不同服务的优势，构建用户满意的解决方案。

调用后，输出增强（第 [6](https://arxiv.org/html/2402.03408v2#S6 "6 Output Enhancement ‣ A Survey on Effective Invocation Methods of Massive LLM Services") 节）关注于返回给用户的信息。输出 $\tilde{a}$ 被调整以适应不同的目标，并以合适的形式返回。此外，这次调用的输入和输出会存储到语义缓存中，以备将来调用使用。

![参见说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 3：LLM 服务调用框架，展示了调用的各个阶段。

## 3 输入摘要

输入摘要旨在减少输入查询的长度而不改变语义，同时优化提示，以更低的成本和延迟更好地调用给定的 LLM。

一般化和上下文能力使得 LLM 服务能够在未训练的样本上获得良好的答案 Dong 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib14)）。因此，通过输入不同的查询可以完成各种不同的自然语言任务。这也导致了 LLM 服务在调用时对输入的依赖。服务被选定后，输入内容和质量直接影响服务的延迟、价格和性能。例如，将提示“只告诉我选项，不要解释其他内容”与问题连接作为 LLM 的输入，会生成较短的输出，从而减少调用成本和延迟。然而，这可能会导致 LLM 失去逐步思考的能力，导致性能下降。

我们将这些方法根据不同的目标分为两类。大多数 LLM 服务根据令牌长度收费。因此，通过缩短输入长度，句子简化可以有效减少使用成本和延迟。提示优化确保信息质量并提高调用性能。

### 3.1 句子简化

句子简化旨在通过减少语言表达的复杂性和长度来提高语言模型的性能，降低延迟和成本。简而言之，它是通过修改、删除或替换句子中的词语、短语或结构，使输入更加简洁，同时保留其核心意义的过程。

这个问题类似于总结任务，许多用于总结的方法也可以应用于 Huang 等人（[2021](https://arxiv.org/html/2402.03408v2#bib.bib17)）；Watanangura 等人（[2024](https://arxiv.org/html/2402.03408v2#bib.bib46)）；Antony 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib4)）；Mridha 等人（[2021](https://arxiv.org/html/2402.03408v2#bib.bib31)）。我们整理了 LMaaS 的可用方法，并根据它们是否完全源自原始输入，将其分为提取式和生成式方法。

提取式方法。从长原始输入中，提取式方法通过提取关键句子或短语来选择句子以形成新输入，其中内容完全来源于原始输入。根据与上下文的相关性修剪语义上无关的词语是一个不错的选择 Liu 等人（[2023a](https://arxiv.org/html/2402.03408v2#bib.bib23)）。通过使用中间“攻击者”并采用贪婪调用，执行对输入的迭代删除和替换操作 Si 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib42)）。Kim 等人（[2022](https://arxiv.org/html/2402.03408v2#bib.bib20)）基于注意力机制，去除不重要的词语。

这种方法简单高效，使其非常方便立即使用。然而，提取的思想可能忽视全局信息。此外，它在语言翻译等任务中存在局限性，因为它无法判断哪些部分需要翻译或删除。

生成方法。生成方法指的是基于原始输入对内容进行压缩和改写，从而生成新词。语言编码是一种简单的处理方法，应用于输入，Ahia et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib1)) 在不同语言和分词器上进行了广泛的实验，其中成本变化高达 5 倍。AE.studio ²²2Prompt Reducer-Cut Down GPT-4 Token Costs ([`www.promptreducer.com/`](https://www.promptreducer.com/)) 采用加密技术提供了一个在线平台，牺牲了可读性，将输入标记的长度减少了一半。利用快速且低成本的生成自然语言模型，Liu et al. ([2023a](https://arxiv.org/html/2402.03408v2#bib.bib23))；Li et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib22)) 也提出了句子简化的可行选项。

这一类方法更为灵活，因为生成的句子包含较少的冗余信息，同时保留了主要内容。然而，它可能会引入语法或事实错误。这种方法可能依赖于图、树或神经网络等复杂结构。

### 3.2 提示优化

提示优化是设计和调整用户提供的输入提示，以引导 LLM 生成更准确、有用或量身定制的输出。提示优化的有效性源于 LLM 从少量示例甚至零示例中学习的能力（Liu et al. ([2023b](https://arxiv.org/html/2402.03408v2#bib.bib24))），适当的提示可以补充任务的上下文、突出关键信息或提高解释能力。

基于优化目标的不同粒度，我们区分了两种类型的提示优化方法。通过选择或组合一些提示，可以引导 LLM 更有效、更高效地处理各种输入。提示增强关注于内容的质量，旨在最大化上下文的潜力。

提示选择。提示选择从可能的提示中选择最有意义的提示，以准确引导 LLM。它去除了无关提示的干扰，并有助于高效调用。Zhou 等人（[2020](https://arxiv.org/html/2402.03408v2#bib.bib54)）选择了代表性样本，这在少量样本任务中非常有益。另一种提示选择的方法是结合相同类型任务的提示，使 LLM 一次性处理由多个查询共享的提示信息。Santra 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib39)）结合了涉及指令、示例和附加背景的各种方法，提出了一种更紧凑的方法，用于在对话中提供历史信息。Arefeen 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib5)）考虑了提示的连接，并使用比较方法检索最重要的 k 个句子，实现了类似问题的提示共享。

提示选择可以直接引导 LLM 关注信息的特定方面，更准确地理解用户需求。对于一些通用任务，可以使用标准选择方法而不需过多个性化。然而，对于复杂的提示，这种方法并不能充分发挥其潜力，因为没有引入额外的知识。

提示增强。提示增强考虑了 LLM 的理解能力，以引发更准确和理想的响应。知识检索是增强的直接方法，它有助于在模型推理过程中实现全面理解。Haurum 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib15)）研究了 LLM 中事实知识的局限性，并以最小检索成本优化推理过程。通过微调的优化是近期的进展，Yu 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib51)）；Zhou 等人（[2020](https://arxiv.org/html/2402.03408v2#bib.bib54)）提出了一种黑箱微调框架，该框架仅通过 API 访问，以非导数方法优化连续提示。模型对齐 Liu 等人（[2023c](https://arxiv.org/html/2402.03408v2#bib.bib25)）和思维链推理 Wu 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib47)），也是提示优化的关键关注点。

尽管提示增强可能导致更复杂的处理过程，但在调用性能方面的改善是显著的。通用方法难以探索，这需要一些专业知识。

## 4 语义缓存

语义缓存是一种通过存储和快速检索语义信息来提高 LLM 调用效率和性能的方法。与传统的数据缓存不同，语义缓存更关注于存储数据的高级语义，如意义、上下文和关系，而不仅仅是原始数据。在调用服务之前会检查语义缓存。如果命中缓存，系统将直接返回缓存提供的输出，而无需执行繁琐的后续过程。

缓存技术通常需要长期的数据积累，不适用于冷启动场景。然而，随着 LLM 规模的逐步扩大，它在加速计算、降低数据传输成本和支持高并发请求方面发挥着越来越重要的作用 Miao et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib30))，为用户提供低成本、低延迟和高性能的服务。

在 LMaaS 中，语义缓存的实现有两种典型结构，与其他子部分不同，它们通常不能一起使用。传统缓存使用键值对进行存储和检索。当类似的输入再次出现时，系统可以通过键快速搜索语义缓存并返回相同的值。神经缓存借鉴了神经网络的思想，以预测而非检索的方式进行响应。它学习输入数据之间的语义关系，而不依赖于特定的存储结构。

### 4.1 传统缓存

传统缓存的当前范式由三部分组成：缓存管理器、相似度评估器和后处理器。缓存管理器负责以键值对的形式存储内容并管理缓存淘汰。相似度评估器用于确定缓存中的任何键是否与输入查询匹配。后处理器组织最终返回给用户的响应。如果在缓存中未找到类似的查询，后处理器会调用 LLM 服务生成输出，然后将生成的输出存储在缓存中。

Bang ([2023](https://arxiv.org/html/2402.03408v2#bib.bib7)) 代表了传统缓存的一个典型应用，它利用问题嵌入进行相似性匹配，并提供了精确匹配和嵌入距离等多种匹配方法。开源应用程序 Zep ³³3Zep: Fast, scalable building blocks for LLM apps ([`github.com/getzep/zep`](https://github.com/getzep/zep)) 也支持 LLM 应用的存储、聚合、嵌入和索引。通过理论证明，Zhu et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib55)) 提出了考虑查询频率的最低预期成本的缓存方案。此外，查询和对话缓存的方法 Tao et al. ([2021](https://arxiv.org/html/2402.03408v2#bib.bib43)); Barrios and Kumar ([2024](https://arxiv.org/html/2402.03408v2#bib.bib8)) 可以轻松迁移到 LMaaS。

实现传统缓存通常相对简单，只需要基本的数据结构，如易于管理的哈希。此方法很通用，但由于过于依赖键匹配，可能无法捕捉输入之间的语义相似性。

### 4.2 神经缓存

神经缓存使用神经网络或深度学习模型来学习和存储数据表示。它通过学习数据的表示，将输入数据映射到高维空间。学到的表示应该捕捉输入数据的语义相似性，以便相似的输入在表示空间中接近。

Ramírez 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib32)）使用 T5-base⁴⁴4T5-base 模型（[`huggingface.co/docs/transformers/model_doc/t5`](https://huggingface.co/docs/transformers/model_doc/t5)）训练一个学生模型，用于在分类任务中提供早期反馈，并且模型会定期更新。为了应对语义缓存的有效性测试问题，Rasool 等人（[2024](https://arxiv.org/html/2402.03408v2#bib.bib33)）生成相似的输入以尽可能多地命中缓存。此外，基于检索的对话响应选择模型也可以作为另一种选择。Tao 等人（[2021](https://arxiv.org/html/2402.03408v2#bib.bib43)）提供了一个将大多数模型分类为三种框架的调查，其中，基于表示的模型可以作为神经缓存使用。

这些方法在特定领域的问题中通常优于传统缓存。然而，它们的实现和更新可能相对复杂。重要的是要仔细考虑缓存的有效性，以避免不必要的浪费。

![参考说明](img/9df2a699c179d7d103da938773675ba1.png)

图 4：由现有方法组成的简单调用策略，包括输入抽象中的 Prompt Reducer、语义缓存中的 Zep、解决方案设计中的 FrugalGPT，以及输出增强中的无。

## 5 解决方案设计

解决方案设计是一种利用具有异质成本和性能的 LLM 服务的方法。它考虑不同的场景和目标，根据查询动态选择一个或多个最适合特定调用的 LLM 服务，并以某种形式组织它们，以提供灵活而高效的解决方案。这种方法允许用户选择最符合特定需求的 LLM 服务。当新的查询出现或需求发生变化时，可以灵活更新解决方案的配置，以实现最佳的性能和成本效益。

解决方案设计有两个主要部分，这两个部分协同工作以实现动态 LLM 服务的选择和路由。评分函数负责评估每个可用 LLM 服务的性能，这可以反映调用中的关注指标，如质量、速度等。路由器根据评分函数的评估结果，在服务之间执行查询路由，并以动态方式选择合适的服务。

### 5.1 评分函数

评分函数是对特定任务或查询给定的 LLM 服务的综合评估，考虑目标和场景，通常用于指导解决方案中的路由路径。它可能受到多个因素的影响，如响应时间、查询成本、答案准确性等。评分函数在决策中发挥作用，有助于理解每个 LLM 服务的相对性能，以便做出更智能的选择。

定义的指标。定义的指标提供了一种可测量的方式来直接量化关注的因素。例如，分类任务中的准确率、生成任务中的 BLEU 分数、诸如数据包丢失和服务质量（QoS）等指标都是适用的指标。Ramírez 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib32)）使用区间采样和预测熵来确定是否调用 LLM 服务以应对不同时间维度的调用。考虑到一致性的三个来源，LLM 服务的决策是通过采样和投票来进行的，Yue 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib52)）进行决策。计算两个模型之间的成本预期，Zhu 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib55)）将选择调用扩展到多个 LLM。Lu 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib26)）通过不同服务提供的答案的奖励排名作为评估标准，从而在解决方案中产生最小的计算成本。

定义的指标直观且易于理解。它们通常基于统计数据或实验，提供高可靠性且不易受到主观因素的影响。然而，设置阈值可能具有挑战性，并且可能不适应动态和变化的环境。此外，某些关键因素可能难以通过特定指标捕捉，从而导致评分的局限性。

评分工具。评分工具是一种用于根据未由特定公式定义的指标对每个 LLM 服务进行评分的工具。评分工具利用先前的知识、训练数据或规则，以一种通常较难解释的方式提供评分，通常使用较小的神经网络 Chen et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib13))。AlBert 被用作评分工具，以查询和预测输出作为$x$，预测输出和标签的准确度作为$y$进行训练 Sakota et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib38))。另一种方法涉及使用 DistilBert 作为评分模型，以查询和模型 ID 作为$x$，以及它是否能够解决问题作为$y$进行训练 Shnitzer et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib41))。对 LLM 在不同基准数据集上的表现进行了比较，Zhang et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib53))将其建模为二元选择问题，提供指导建议。对于特定任务，如代码生成任务中的执行结果 Zhang et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib53))，根据问题和答案任务中的查询难度的分类器 Anonymous ([2024](https://arxiv.org/html/2402.03408v2#bib.bib3)); Madaan et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib28))，以及评估 LLM 服务在数据集基准测试任务中的能力 Shnitzer et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib41)) 都是合理的评分工具。

与由公式定义的指标相比，评分工具可以根据实时数据和反馈进行更新，展示出在不同场景中的强泛化能力。然而，这种方法相当于使用更强大的模型进行评分，从而产生评分工具自身的训练和使用成本。而且，它仍然需要一些标记的示例，这使得当查询数据集的大小大于训练数据集时才有意义。

### 5.2 LLM 路由器

LLM 路由强调服务之间的组织结构，以特定的逻辑顺序连接多个独立的服务。它专注于构建一个灵活且可重用的 LLM 服务解决方案，以应对不断变化的查询或目标。根据不同的评分函数和使用的位置，LLM 路由可以构建以目标为导向的解决方案，如成本导向或性能导向。

顺序结构。最简单的方法是从大量的 LLM 服务中选择一个或多个模型，并按顺序调用它们。使用评分函数来决定是否接受答案或继续进行路由的下一步 Chen et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib13))。使用顺序结构时，模型的数量通常限制为三种，并通过排列确定可能的选项，并应用修剪技术 Ramírez et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib32)); Yue et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib52))。使用小模型作为缓存，当缓存未命中时按顺序调用大模型，可以被视为一种固定的顺序结构 Ramírez et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib32)); Yue et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib52))。对于代码生成等问题 Zhang et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib53))，使用成本效益高的 LLM 获取初步响应，并将成功的信息作为后续查询的上下文进行跟踪。

这种结构简单有效，且可以在整个空间中快速搜索有限的排列。然而，顺序结构可能会导致按顺序调用所有模型。而且，当适应新需求时，结构的扩展较为困难，需要重新排列所有模型。

其他结构。与机器学习中的袋装法和提升法类似，平行结构可以增强 LLM 服务的正确性和一致性，其中任务分解和合并是关键方面 Jiang et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib19))。星形结构，如 Sakota et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib38)); Lu et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib26))所示，涉及由元模型进行决策，将当前查询分配给最合适的模型。对于第三类无法解决的查询，Madaan et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib28)) 采用修剪方法，以避免对特别困难的问题产生不必要的费用。树状结构被认为是有前途的，它结合了星形和顺序结构的方面。它最初将查询路由到最可能的分支，然后按顺序调用服务。此外，某些针对 HTTP 服务的选择解决方案 Hosseinzadeh et al. ([2020](https://arxiv.org/html/2402.03408v2#bib.bib16)); Manqele et al. ([2017](https://arxiv.org/html/2402.03408v2#bib.bib29))也值得借鉴。

## 6 输出增强

输出增强是指进一步优化和调整生成的调用结果的过程。该过程旨在提高生成结果的语法正确性、语义准确性和整体流畅性，以满足用户和特定场景的需求。

据我们所知，输出增强方法仍然依赖于上述方法，但它强调根据具体任务的需求进行定制，提升模型的应用适应性，减少后续人工干预的需求，并为用户提供低延迟、高性能的服务。例如，刘等人（[2023b](https://arxiv.org/html/2402.03408v2#bib.bib24)）指导 LLM 给出简洁的回答可以减少不必要的输出 token。将多个低成本模型的响应聚合是提升质量的另一种方式，陈等人（[2022](https://arxiv.org/html/2402.03408v2#bib.bib12)）提出了这种方法，并且它通常用于多标签任务。模型对齐的研究，沈等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib40)）也可以用来纠正语法和逻辑，从而减少后续的人工工作需求。

## 7 结论与挑战

总之，本文对 LMaaS 领域中有效调用方法进行了全面的概述。通过建立分类体系，我们将现有方法分为四类：输入抽象、语义缓存、解决方案设计和输出增强。接着我们将有效 LLM 服务策略构建的问题进行形式化，并提出了一个 LLM 服务调用框架。框架中的每个组件可以独立工作，也可以同时工作，从而形成有效的 LLM 服务调用策略，具有低延迟、高性能和节约成本的特点。

现有方法往往只关注框架的一个组件，我们可以将其作为插件使用。图 [4](https://arxiv.org/html/2402.03408v2#S4.F4 "Figure 4 ‣ 4.2 Neural Cache ‣ 4 Semantic Cache ‣ A Survey on Effective Invocation Methods of Massive LLM Services")展示了一个由三种现有方法构建的简单调用策略。该领域的发展前景广阔，但仍面临一些开放性挑战。

输入抽象。在输入抽象组件中，面临的主要挑战之一是多模态输入处理，参考文献包括 Yin 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib50)）。需要更全面和平衡的方法来缩短和优化文本、图像和语音等多种类型的输入。还值得探索针对动态变化输入的输入抽象方法，例如实时数据流处理，参考文献包括 Räth 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib34)）或用户与系统的交互。此外，根据粒度，输入抽象还可以分为文档级、句子级和短语级。不同粒度的方法可能会互操作，并且通常会组成多阶段的方法。

语义缓存。在语义缓存部分，如何设计和选择缓存方法以更高效地适应不同类型的输入和查询是传统缓存面临的主要挑战，而语义表示则是神经缓存所关注的重点，参考文献包括 Brais 等人（[2021](https://arxiv.org/html/2402.03408v2#bib.bib9)）和 Brito（[2023](https://arxiv.org/html/2402.03408v2#bib.bib10)）。

解决方案设计。在解决方案设计方面，LLM 服务的评估问题，参考文献包括 Chang 等人（[2023](https://arxiv.org/html/2402.03408v2#bib.bib11)），是评分函数的扩展，需要在未来更多关注适应性和可解释性。而 LLM 路由器将重点设计更强大的服务集成方法，不仅关注任务本身，还考虑不同资源的需求，参考文献包括 Xu 等人（[2024](https://arxiv.org/html/2402.03408v2#bib.bib48)）。两者的更有效结合，例如动态决策，将导致更好的解决方案。

输出增强。输出增强的重要性也逐渐被人们认识到。输出的规范性和多样性之间的平衡是一个关键问题。当任务完成时，用户的满意度成为衡量服务质量的重要指标，未来的研究可能会集中于构建更加智能和以用户为导向的输出增强方法，参考文献包括 Jeung 和 Huang（[2023](https://arxiv.org/html/2402.03408v2#bib.bib18)）。

其他挑战。基础工作如实验中的定性描述和定量比较仍存在空白，数据集的缺乏使得服务方法比较没有统一标准。一些技术细节，如如何选择最短输入的分词器 Alyafeai et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib2))，缓存大小的指导 Vavouliotis et al. ([2022](https://arxiv.org/html/2402.03408v2#bib.bib45))，以及相同 LLM 服务的不同定价方法选择，需要深入探讨。此外，我们特别呼吁关注公平性 Sah et al. ([2024](https://arxiv.org/html/2402.03408v2#bib.bib36))和隐私问题 Luo et al. ([2024](https://arxiv.org/html/2402.03408v2#bib.bib27))；Utpala et al. ([2023](https://arxiv.org/html/2402.03408v2#bib.bib44))在 LMaaS 中的应用。使用中间件高效构建的方法可能被利用以谋取个人利益或恶意目的。我们期待未来研究进一步推动该领域的发展，为用户提供低延迟、高性能和成本效益高的 LLM 服务解决方案，并促进 LMaaS 生态系统的健康发展。

## 参考文献

+   Ahia et al. [2023] Orevaoghene Ahia, Sachin Kumar, Hila Gonen, Jungo Kasai, David R. Mortensen, Noah A. Smith, and Yulia Tsvetkov. 所有语言的代价相同吗？商业语言模型时代的分词。在 EMNLP 会议论文集中，2023。

+   Alyafeai et al. [2023] Zaid Alyafeai, Maged Saeed AlShaibani, Mustafa Ghaleb, and Irfan Ahmad. 针对阿拉伯文本分类的各种分词器评估。Neural Process. Lett., 2023。

+   Anonymous [2024] Anonymous. 混合 LLM：成本高效且质量意识的查询路由。在 ICLR 会议论文集中，2024。

+   Antony et al. [2023] Dinu Antony, Sumit Abhishek, Sujata Singh, Siddu Kodagali, Narayana Darapaneni, Mukesh Rao, Anwesh Reddy Paduri, and Sudha BG. 高级高效文本摘要方法的综述。在第 13 届 IEEE 年度计算与通信研讨会暨会议，CCWC 2023，拉斯维加斯，NV，美国，2023 年 3 月 8-11 日，2023。

+   Arefeen et al. [2023] Md. Adnan Arefeen, Biplob Debnath, and Srimat Chakradhar. Leancontext：利用 LLMs 的成本高效领域特定问答。CoRR，2023。

+   Bai et al. [2024] Guangji Bai, Zheng Chai, Chen Ling, Shiyu Wang, Jiaying Lu, Nan Zhang, Tingwei Shi, Ziyang Yu, Mengdan Zhu, Yifei Zhang, Carl J. Yang, Yue Cheng, and Liang Zhao. 超越效率：资源高效大型语言模型的系统综述。CoRR，2024。

+   Bang [2023] Fu Bang. Gptcache：一种开源语义缓存，用于 LLM 应用，加速回答和节省成本。2023。

+   Barrios and Kumar [2024] Carlos Barrios and Mohan Kumar. 边缘服务缓存和计算重用策略：综述。ACM Comput. Surv., 2024。

+   Brais et al. [2021] Hadi Brais, Rajshekar Kalayappan, and Preeti Ranjan Panda. 缓存模拟器综述。ACM Comput. Surv., 2021。

+   Brito [2023] 爱德华多·布里托。通过语义相似性解释的资源感知表示学习。博士论文，2023 年。

+   Chang et al. [2023] 常宇鹏、王旭、王金栋、吴元、朱凯杰、陈浩、杨林毅、易晓源、王存翔、王亦东、叶伟、张越、常易、Philip S. Yu、杨强和谢兴。大语言模型评估综述。CoRR，2023 年。

+   Chen et al. [2022] 陈灵娇、Matei Zaharia 和 James Zou。多标签分类任务的高效在线机器学习 API 选择。在 ICML 会议论文集中，2022 年。

+   Chen et al. [2023] 陈灵娇、Matei Zaharia 和 James Zou。FrugalGPT：如何在降低成本和提高性能的同时使用大语言模型。CoRR，2023 年。

+   Dong et al. [2023] 董青修、李雷、戴大迈、郑策、吴志勇、常宝宝、孙旭、徐晶晶、李雷和隋智芳。上下文学习综述，2023 年。

+   Haurum et al. [2023] Joakim Bruslund Haurum、Sergio Escalera、Graham W. Taylor 和 Thomas B. Moeslund。使用哪些令牌？研究视觉变换器中的令牌减少。在 ICCV 会议论文集中，2023 年。

+   Hosseinzadeh et al. [2020] Mehdi Hosseinzadeh、Hawkar Kamaran Hama、Marwan Yassin Ghafour、Mohammad Masdari、Omed Hassan Ahmed 和 Hemn Khezri。基于多标准决策的服务选择：全面概述。《网络系统管理杂志》，2020 年。

+   Huang et al. [2021] 黄益忠、冯夏冲、冯小程和秦冰。抽象文本摘要中的事实不一致问题：综述。CoRR，2021 年。

+   Jeung and Huang [2023] Jun Li Jeung 和 Yi-Ching Janet Huang。如果我错了，请纠正我：探索 AI 输出如何影响用户感知和信任。在计算机支持的协作工作和社会计算会议，CSCW 2023，明尼阿波利斯，MN，美国，2023 年 10 月 14-18 日。

+   Jiang et al. [2023] 江东福、任翔和 Bill Yuchen Lin。LLM-Blender：通过成对排名和生成融合集成大语言模型。在 ACL 会议论文集中，2023 年。

+   Kim et al. [2022] Kim Sehoon、Sheng Shen、David Thorsley、Amir Gholami、Woosuk Kwon、Joseph Hassoun 和 Kurt Keutzer。变换器的学习令牌修剪。在 KDD 会议论文集中，2022 年。

+   Lai et al. [2023] 黎越达、吴义重、Amir Pouran Ben Veyseh、Hieu Man、Franck Dernoncourt、Trung Bui 和阮天。ChatGPT 超越英语：多语言学习中大语言模型的全面评估。在 EMNLP Findings 会议论文集中，2023 年。

+   Li et al. [2023] 李佳政、赵润聪、何玉兰和桂林。Overprompt：通过高效的上下文学习方法增强 ChatGPT 能力。CoRR，2023 年。

+   Liu et al. [2023a] 刘俊熙、李亮智、项彤、王博文和钱一鸣。TCRA-LLM：用于推理成本降低的令牌压缩检索增强大语言模型。在 EMNLP Findings 会议论文集中，2023 年。

+   刘等人 [2023b] 彭飞·刘、韦哲·袁、金兰·傅、郑宝·姜、广明·林和格雷厄姆·纽比格。预训练、提示和预测：自然语言处理中的提示方法系统性调查。ACM Comput. Surv., 2023。

+   刘等人 [2023c] 易欣·刘、布达迪亚·德布、米拉格罗·特雷乌尔、亚伦·哈夫凯、德拉戈米尔·拉德夫和艾哈迈德·哈桑·阿瓦达拉。通过自然语言反馈改善摘要的事实一致性。在 ACL 会议录中，2023 年。

+   陆等人 [2023] 柯铭·陆、洪毅·袁、润基·林、俊阳·林、郑元、常周和晶仁·周。专家路由：高效的奖励引导大型语言模型集成。CoRR, 2023。

+   罗等人 [2024] 景龙·罗、叶红·张、佳琪·张、辛穆、辉·王、岳宇和曾林·徐。Secformer：致力于快速而准确的大型语言模型隐私保护推理。CoRR, 2024。

+   马丹等人 [2023] 阿曼·马丹、普兰贾尔·阿格拉瓦尔、安基特·安南、斯里维德亚·普拉纳维·波塔拉朱、斯瓦鲁普·米什拉、佩伊·周、阿迪亚·古普塔、迪拉吉·拉贾戈帕尔、卡尔提克·卡帕甘图、易鸣·杨、夏姆·乌帕德亚和毛萨姆。Automix：自动混合语言模型。CoRR, 2023。

+   曼克莱等人 [2017] 林德尔维伊兹维兹·曼克莱、姆切莱·E·德洛德、路易斯·科特齐和乔治·西比亚。动态环境下的服务选择方法调查。在 IEEE AFRICON 2017 中，南非开普敦，2017 年 9 月 18-20 日，2017 年。

+   苗等人 [2023] 旭鹏·苗、加布里埃尔·奥利亚罗、志豪·张、欣浩·程、洪毅·金、天奇·陈和志豪·贾。朝着高效的生成型大型语言模型服务：从算法到系统的调查。CoRR, 2023。

+   米尔达等人 [2021] 穆罕默德·F·米尔达、阿克利玛·阿克特·利玛、卡姆鲁丁·努尔、苏乔伊·钱德拉·达斯、马赫穆德·哈桑和穆罕默德·莫辛·卡比尔。自动文本摘要调查：进展、过程与挑战。IEEE Access, 2021。

+   拉米雷斯等人 [2023] 吉列姆·拉米雷斯、马蒂亚斯·林德曼、亚历山德拉·伯奇和伊万·提托夫。缓存与蒸馏：优化对大型语言模型的 API 调用。CoRR, 2023。

+   拉苏尔等人 [2024] 扎法里亚布·拉苏尔、斯科特·巴尼特、大卫·威利、斯特凡努斯·库尔尼亚万、谢尔温·巴鲁戈、斯里坎特·图杜穆和穆罕默德·阿卜杜勒拉泽克。用于语义缓存的测试输入生成的 LLMs，2024 年。

+   雷斯等人 [2023] 提莫·雷斯、恩戈齐丘库卡·奥纳和凯-乌维·萨特勒。实时流应用的交互数据清洗。在 HILDA 2023 数据分析人工智能工作坊会议录中，2023 年 6 月 18 日，西雅图，华盛顿，美国，2023 年。

+   雷迪等人 [2019] 希瓦·雷迪、丹琪·陈和克里斯托弗·D·曼宁。Coqa：一个对话式问答挑战。Trans. Assoc. Comput. Linguistics, 2019。

+   萨赫等人 [2024] 钱丹·库马尔·萨赫、肖莉·联和穆罕默德·米拉朱尔·伊斯兰。揭示大型语言模型公平性评估中的偏见：音乐和电影推荐系统的关键文献综述。CoRR, 2024。

+   Saha 等人 [2023] Swarnadeep Saha、Omer Levy、Asli Celikyilmaz、Mohit Bansal、Jason Weston 和 Xian Li. Branch-solve-merge 改进了大型语言模型的评估和生成。CoRR，2023 年。

+   Sakota 等人 [2023] Marija Sakota、Maxime Peyrard 和 Robert West. 飞溅还是大炮？通过元建模选择具有成本效益的语言模型。CoRR，2023 年。

+   Santra 等人 [2023] Bishal Santra、Sakya Basak、Abhinandan De、Manish Gupta 和 Pawan Goyal. 对话模型的节俭提示。发表于 EMNLP Findings 会议论文集，2023 年。

+   Shen 等人 [2023] Tianhao Shen、Renren Jin、Yufei Huang、Chuang Liu、Weilong Dong、Zishan Guo、Xinwei Wu、Yan Liu 和 Deyi Xiong. 大型语言模型的对齐：一项调查。CoRR，2023 年。

+   Shnitzer 等人 [2023] Tal Shnitzer、Anthony Ou、Mírian Silva、Kate Soule、Yuekai Sun、Justin Solomon、Neil Thompson 和 Mikhail Yurochkin. 大型语言模型的路由与基准数据集。CoRR，2023 年。

+   Si 等人 [2023] Wai Man Si、Michael Backes 和 Yang Zhang. Mondrian：针对大型语言模型的提示抽象攻击以降低 API 定价。CoRR，2023 年。

+   Tao 等人 [2021] Chongyang Tao、Jiazhan Feng、Rui Yan、Wei Wu 和 Daxin Jiang. 基于检索的对话中的响应选择调查。发表于 IJCAI 会议论文集，2021 年。

+   Utpala 等人 [2023] Saiteja Utpala、Sara Hooker 和 Pin-Yu Chen. 使用零-shot 提示进行局部差分隐私文档生成。发表于 EMNLP Findings 会议论文集，2023 年。

+   Vavouliotis 等人 [2022] Georgios Vavouliotis、Gino Chacon、Lluc Alvarez、Paul V. Gratz、Daniel A. Jiménez 和 Marc Casas. 页面大小感知的缓存预取。发表于 MICRO 会议论文集，2022 年。

+   Watanangura 等人 [2024] Patcharapruek Watanangura、Sukit Vanichrudee、On Minteer、Theeranat Sringamdee、Nattapong Thanngam 和 Thitirat Siriborvornratanakul. 文本摘要技术的比较调查。SN Comput. Sci.，2024 年。

+   Wu 等人 [2023] Dingjun Wu、Jing Zhang 和 Xinmei Huang. 思维链提示引发知识增强。发表于 ACL Findings 会议论文集，2023 年。

+   Xu 等人 [2024] Mengwei Xu、Wangsong Yin、Dongqi Cai、Rongjie Yi、Daliang Xu、Qipeng Wang、Bingyang Wu、Yihao Zhao、Chen Yang、Shihe Wang、Qiyang Zhang、Zhenyan Lu、Li Zhang、Shangguang Wang、Yuanchun Li、Yunxin Liu、Xin Jin 和 Xuanzhe Liu. 资源高效的 LLM 和多模态基础模型调查。CoRR，2024 年。

+   Yang 等人 [2023] Jingfeng Yang、Hongye Jin、Ruixiang Tang、Xiaotian Han、Qizhang Feng、Haoming Jiang、Bing Yin 和 Xia Hu. 实践中利用 llms 的力量：关于 chatgpt 及其扩展的调查。CoRR，2023 年。

+   Yin 等人 [2023] Shukang Yin、Chaoyou Fu、Sirui Zhao、Ke Li、Xing Sun、Tong Xu 和 Enhong Chen. 多模态大型语言模型的调查。CoRR，2023 年。

+   Yu 等人 [2023] Lang Yu、Qin Chen、Jiaju Lin 和 Liang He. 视觉-语言模型的黑箱提示调优作为服务。发表于 IJCAI 会议论文集，2023 年。

+   Yue 等人 [2023] Murong Yue, Jie Zhao, Min Zhang, Liang Du 和 Ziyu Yao. 具有思维混合表示的大型语言模型级联，用于成本高效推理。CoRR, 2023。

+   Zhang 等人 [2023] Jieyu Zhang, Ranjay Krishna, Ahmed Hassan Awadallah 和 Chi Wang. Ecoassistant：以更经济和准确的方式使用 LLM 助手。CoRR, 2023。

+   Zhou 等人 [2020] Jianyi Zhou, Feng Li, Jinhao Dong, Hongyu Zhang 和 Dan Hao. 通过输入减少对深度学习模型的成本效益测试。发表于第 31 届 IEEE 国际软件可靠性工程研讨会，ISSRE 2020，葡萄牙科英布拉，2020 年 10 月 12-15 日，2020 年。

+   Zhu 等人 [2023] Banghua Zhu, Ying Sheng, Lianmin Zheng, Clark W. Barrett, Michael I. Jordan 和 Jiantao Jiao. 关于大型模型推理的最佳缓存和模型复用。CoRR, 2023。

生成于 2024 年 3 月 1 日 星期五 03:26:58，由 [LATExml![[LOGO]](img/70e087b9e50c3aa663763c3075b0d6c5.png)](http://dlmf.nist.gov/LaTeXML/)
