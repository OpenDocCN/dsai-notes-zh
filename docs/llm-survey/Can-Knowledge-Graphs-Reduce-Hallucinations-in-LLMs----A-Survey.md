<!--yml

类别：未分类

日期：2024-09-03 17:31:29

-->

# 知识图谱能减少大语言模型中的幻觉吗？：一项调查

> 来源：[`arxiv.org/html/2311.07914`](https://arxiv.org/html/2311.07914)

1.  [1 引言](https://arxiv.org/html/2311.07914v2#S1 "1 Introduction ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

1.  [2 基础知识](https://arxiv.org/html/2311.07914v2#S2 "2 Preliminaries ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

    1.  [2.1 大语言模型](https://arxiv.org/html/2311.07914v2#S2.SS1 "2.1 Large Language Models ‣ 2 Preliminaries ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

    1.  [2.2 知识图谱](https://arxiv.org/html/2311.07914v2#S2.SS2 "2.2 Knowledge Graphs ‣ 2 Preliminaries ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

1.  [3 知识图谱增强的大语言模型](https://arxiv.org/html/2311.07914v2#S3 "3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

    1.  [3.1 知识感知推理](https://arxiv.org/html/2311.07914v2#S3.SS1 "3.1 Knowledge-Aware Inference ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

        1.  [3.1.1 知识图谱增强检索](https://arxiv.org/html/2311.07914v2#S3.SS1.SSS1 "3.1.1 KG-Augmented Retrieval ‣ 3.1 Knowledge-Aware Inference ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

        1.  [3.1.2 知识图谱增强推理](https://arxiv.org/html/2311.07914v2#S3.SS1.SSS2 "3.1.2 KG-Augmented Reasoning ‣ 3.1 Knowledge-Aware Inference ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

        1.  [3.1.3 知识控制生成](https://arxiv.org/html/2311.07914v2#S3.SS1.SSS3 "3.1.3 Knowledge-Controlled Generation ‣ 3.1 Knowledge-Aware Inference ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

    1.  [3.2 知识感知训练](https://arxiv.org/html/2311.07914v2#S3.SS2 "3.2 Knowledge-Aware Training ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

        1.  [3.2.1 知识感知预训练](https://arxiv.org/html/2311.07914v2#S3.SS2.SSS1 "3.2.1 Knowledge-Aware Pre-Training ‣ 3.2 Knowledge-Aware Training ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

        1.  [3.2.2 知识感知微调](https://arxiv.org/html/2311.07914v2#S3.SS2.SSS2 "3.2.2 Knowledge-Aware Fine-Tuning ‣ 3.2 Knowledge-Aware Training ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

    1.  [3.3 知识感知验证](https://arxiv.org/html/2311.07914v2#S3.SS3 "3.3 Knowledge-Aware Validation ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")

1.  [4 讨论、挑战与未来](https://arxiv.org/html/2311.07914v2#S4 "4 Discussion, Challenges and Future ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

    1.  [4.1 资源](https://arxiv.org/html/2311.07914v2#S4.SS1 "4.1 Resources ‣ 4 讨论、挑战与未来 ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

    1.  [4.2 评估指标](https://arxiv.org/html/2311.07914v2#S4.SS2 "4.2 Evaluation Metrics ‣ 4 讨论、挑战与未来 ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

    1.  [4.3 性能分析](https://arxiv.org/html/2311.07914v2#S4.SS3 "4.3 Performance Analysis ‣ 4 讨论、挑战与未来 ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

    1.  [4.4 趋势分析](https://arxiv.org/html/2311.07914v2#S4.SS4 "4.4 Trend Analysis ‣ 4 讨论、挑战与未来 ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

    1.  [4.5 未来方向](https://arxiv.org/html/2311.07914v2#S4.SS5 "4.5 Future Directions ‣ 4 讨论、挑战与未来 ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

1.  [5 结论](https://arxiv.org/html/2311.07914v2#S5 "5 Conclusion ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

1.  [6 局限性](https://arxiv.org/html/2311.07914v2#S6 "6 Limitations ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")

HTML 转换 [有时会显示错误](https://info.dev.arxiv.org/about/accessibility_html_error_messages.html)，由于内容未能正确转换自源文档。本文使用了 HTML 转换工具尚不支持的以下包。对此问题的反馈不必要；这些问题已知并正在处理。

+   失败: inconsolata

+   失败: forest

作者：通过遵循这些 [最佳实践](https://info.arxiv.org/help/submit_latex_best_practices.html) 来从您的 LaTeX 提交中获得最佳 HTML 结果。

许可证: CC ZeroarXiv:2311.07914v2 [cs.CL] 2024 年 3 月 16 日

# 知识图谱能否减少 LLMs 中的幻觉？：一项调查

Garima Agrawal    Tharindu Kumarage    Zeyad Alghamdi    Huan Liu

亚利桑那州立大学

{garima.agrawal, kskumara, zalgham1, huanliu}@asu.edu

###### 摘要

现代大型语言模型（LLMs）容易产生幻觉，这主要源于模型中的知识缺口。为了应对这一关键限制，研究人员采用了多种策略，通过引入外部知识来增强 LLMs，以减少幻觉并提高推理准确性。在这些策略中，利用知识图谱作为外部信息来源已显示出令人鼓舞的结果。在本次调查中，我们全面回顾了这些基于知识图谱的 LLMs 增强技术，重点关注其在减轻幻觉方面的有效性。我们将这些方法系统地分类为三大类，提供了方法学比较和性能评估。最后，本次调查探讨了这些技术的当前趋势和挑战，并概述了未来研究的潜在方向。

知识图谱能否减少大型语言模型中的幻觉？：一项调查

Garima Agrawal    Tharindu Kumarage    Zeyad Alghamdi    Huan Liu 亚利桑那州立大学 {garima.agrawal, kskumara, zalgham1, huanliu}@asu.edu

## 1 引言

大型语言模型（LLMs）通过对大规模数据集进行统计训练来模仿人类智能 Huang and Chang ([2022](https://arxiv.org/html/2311.07914v2#bib.bib35))。LLMs 处理输入文本以预测序列中的下一个标记或词，同时识别单词和短语之间的模式和联系，旨在理解和生成类似人类的文本。由于其随机解码过程，即在序列中采样下一个标记，这些模型表现出概率性行为，可能为相同输入在不同实例中产生不同的输出或预测。此外，如果训练数据中包含虚假信息、偏见或不准确性，这些缺陷可能会在模型生成的内容中得到反映或放大。当上下文模糊且位于模型的知识空白区域时，LLMs 在准确解释短语或术语时也面临挑战，这会导致输出听起来可能有道理但往往无关或不正确 Ji et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib36)); Lenat and Marcus ([2023](https://arxiv.org/html/2311.07914v2#bib.bib46))。这种现象通常被称为“幻觉”，它削弱了这些模型的可靠性 Mallen et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib58))。

![参考说明](img/a69149ed85a2d2701979e0ed27b906f2.png)

图 1：在不同阶段使用的知识图谱（KG）以减少 LLMs 中的幻觉。

{forest}

对于树状结构=增长=东，增长父锚点=西，父锚点=东，子锚点=西，锚点=中心，边路径=[\forestoptionedge,->, >=latex] (!u.parent anchor) – +(10pt,0pt) |- (.child anchor) \forestoptionedge label; [KG-增强 LLM，根，l sep=6mm，[知识感知验证（§ [3.3](https://arxiv.org/html/2311.07914v2#S3.SS3 "3.3 知识感知验证 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），valnode，l sep=6mm，[事实感知 LM Logan IV 等（[2019](https://arxiv.org/html/2311.07914v2#bib.bib55)），SURGE Kang 等（[2022b](https://arxiv.org/html/2311.07914v2#bib.bib41)），FOLK Wang 和 Shu（[2023](https://arxiv.org/html/2311.07914v2#bib.bib96)），批评驱动 Lango 和 Dušek（[2023](https://arxiv.org/html/2311.07914v2#bib.bib45)），valcitenode]] [知识感知训练（§ [3.2](https://arxiv.org/html/2311.07914v2#S3.SS2 "3.2 知识感知训练 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），tranode，l sep=6mm，[微调（§ [3.2.2](https://arxiv.org/html/2311.07914v2#S3.SS2.SSS2 "3.2.2 知识感知微调 ‣ 3.2 知识感知训练 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），tranode，l sep=5mm，[SKILL Moiseev 等（[2022](https://arxiv.org/html/2311.07914v2#bib.bib63)），KGLM Youn 和 Tagkopoulos（[2022](https://arxiv.org/html/2311.07914v2#bib.bib115)），LMSI Huang 等（[2022](https://arxiv.org/html/2311.07914v2#bib.bib34)），CoT 微调 Kim 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib44)），tracitenode]] [预训练（§ [3.2.1](https://arxiv.org/html/2311.07914v2#S3.SS2.SSS1 "3.2.1 知识感知预训练 ‣ 3.2 知识感知训练 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），tranode，l sep=6mm，[知识探测，tranode，l sep=5mm，[重接探测 Meng 等（[2021](https://arxiv.org/html/2311.07914v2#bib.bib61)），知识图谱提取 Kassner 等（[2021](https://arxiv.org/html/2311.07914v2#bib.bib42)）；Swamy 等（[2021](https://arxiv.org/html/2311.07914v2#bib.bib90)），pretracitenode]] [知识融合，tranode，l sep=5mm，[JointLK Sun 等（[2021b](https://arxiv.org/html/2311.07914v2#bib.bib89)），LKPNR Runfeng 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib80)），pretracitenode]] [知识引导掩蔽，tranode，l sep=5mm，[SKEP Tian 等（[2020](https://arxiv.org/html/2311.07914v2#bib.bib91)），GLM Shen 等（[2020](https://arxiv.org/html/2311.07914v2#bib.bib83)）；[Zhang 等](https://arxiv.org/html/2311.07914v2#bib.bib118)，pretracitenode]] [知识增强模型，tranode，l sep=5mm，[ERNIE 3.0 Sun 等（[2021a](https://arxiv.org/html/2311.07914v2#bib.bib88)），KALM Rosset 等（[2020](https://arxiv.org/html/2311.07914v2#bib.bib79)），pretracitenode]]]] [知识感知推理（§ [3.1](https://arxiv.org/html/2311.07914v2#S3.SS1 "3.1 知识感知推理 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），infnode，l sep=6mm，[KG-增强生成（§ [3.1.3](https://arxiv.org/html/2311.07914v2#S3.SS1.SSS3 "3.1.3 知识控制生成 ‣ 3.1 知识感知推理 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），infnode，l sep=5mm，[Know-Prompt Chen 等（[2022](https://arxiv.org/html/2311.07914v2#bib.bib14)），KB-Binder Li 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib48)），BeamQA Atif 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib6)），NeMo guardrails Rebedea 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib78)），ALCUNA Yin 等（[2023a](https://arxiv.org/html/2311.07914v2#bib.bib113)），PRCA Yang 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib108)），infcitenode]] [KG-增强推理（§ [3.1.2](https://arxiv.org/html/2311.07914v2#S3.SS1.SSS2 "3.1.2 KG-增强推理 ‣ 3.1 知识感知推理 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），infnode，l sep=5mm，[IRCoT Trivedi 等（[2022](https://arxiv.org/html/2311.07914v2#bib.bib92)），图谱推理 Luo 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib57)），MindMap Wen 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib105)），MOT Li 和 Qiu（[2023](https://arxiv.org/html/2311.07914v2#bib.bib49)），ReCEval Prasad 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib74)），RAP Hao 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib28)），EoT Yin 等（[2023b](https://arxiv.org/html/2311.07914v2#bib.bib114)），infcitenode]] [KG-增强检索（§ [3.1.1](https://arxiv.org/html/2311.07914v2#S3.SS1.SSS1 "3.1.1 KG-增强检索 ‣ 3.1 知识感知推理 ‣ 3 知识图谱增强的 LLMs ‣ 知识图谱能否减少 LLMs 中的幻觉？：一项调查")），infnode，l sep=5mm，[KAPING Baek 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib7)），StructGPT Jiang 等（[2023](https://arxiv.org/html/2311.07914v2#bib.bib37)），IAG Zhang 等（[2023b](https://arxiv.org/html/2311.07914v2#

图 2：知识图谱增强的大型语言模型分类

由于这些模型的内在概率性质，解决这些模型中的幻觉问题具有挑战性。为了有效解决这一问题，已有持续的研究努力进行知识更新和模型调整 **张** 等人 ([2023c](https://arxiv.org/html/2311.07914v2#bib.bib122))；**米亚龙** 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib62))；**佩特罗尼** 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib72))。然而，添加随机信息并不能改善模型的解释和推理能力。相反，提供更多细粒度和上下文相关的精确信息可以显著帮助模型回忆重要信息 **姜** 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib38))。

一种新兴的研究趋势是通过整合知识表示工具（如知识图谱（KGs））来增强 LLMs **Mruthyunjaya** 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib64))。**郑** 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib123)) 证明，通过来自 KGs 的全面外部知识来增强这些模型可以提升它们的性能，并促进更强大的推理过程。增强 LLMs 的 KGs 的策略可以分为三大类，每类对模型的改进都具有独特的贡献，如图[1](https://arxiv.org/html/2311.07914v2#S1.F1 "Figure 1 ‣ 1 Introduction ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")所示：增强推理过程、改善学习机制以及建立健全的模型决策验证方法。

在本次调查中，我们批判性地审查了用于特定阶段减少 LLMs 幻觉的 KG 增强方法，并提高其性能和可靠性。在第[3](https://arxiv.org/html/2311.07914v2#S3 "3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")节中，我们将这些方法分为三大类：（1）知识感知推理，（2）知识感知学习，以及（3）知识感知验证。此外，在第[4](https://arxiv.org/html/2311.07914v2#S4 "4 Discussion, Challenges and Future ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")节中，我们评估了这些方法的实际效果，并讨论了当前的研究趋势，然后提出了潜在的未来研究方向。

相关工作：有几个相关的调查讨论了使用外部知识来增强大语言模型 Hu et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib33))；Yin et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib112))；AlKhamissi et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib5))；Ye et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib111))；Wei et al. ([2021](https://arxiv.org/html/2311.07914v2#bib.bib102))；Liang et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib50))；Zhang et al. ([2023c](https://arxiv.org/html/2311.07914v2#bib.bib122))；Mialon et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib62))。然而，据我们所知，这是首次专门关注批判性回顾利用知识图谱的结构化知识增强大语言模型的方法的调查。具体来说，我们的重点是通过知识图谱整合来解决大语言模型中的幻觉问题。

## 2 初步知识

我们现在介绍将贯穿整个调查的初步知识和定义。

### 2.1 大语言模型

语言建模，作为自然语言处理（NLP）的关键任务，专注于理解语言的结构和生成文本。近年来它的重要性不断上升。具体来说，在神经概率语言模型 Bengio et al. ([2000](https://arxiv.org/html/2311.07914v2#bib.bib10))中，其目标是估计文本序列的可能性。这涉及计算序列中每个标记 $x_{i}$ 的概率，考虑前面的标记，使用链式法则简化过程。

|  | $p(x)=\prod_{i=1}^{N}p(x_{i}&#124;x_{1},x_{1}...x_{i-1})$ |  | (1) |
| --- | --- | --- | --- |

transformer 架构的引入 Vaswani et al. ([2017](https://arxiv.org/html/2311.07914v2#bib.bib93))显著推动了神经概率语言模型的发展，实现了高效的并行处理和长程依赖关系的识别。结合像指令调整和来自人类反馈的强化学习（RLHF） Ouyang et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib69))等训练进展，这些神经概率语言模型促成了先进的大语言模型（LLMs）的创建，如 GPT-3 Brown et al. ([2020](https://arxiv.org/html/2311.07914v2#bib.bib12))、GPT-4 OpenAI ([2023](https://arxiv.org/html/2311.07914v2#bib.bib68))和 PaLM Chowdhery et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib16))，因其卓越的语言能力而闻名。

### 2.2 知识图谱

知识图谱（KGs）将信息组织成结构化的格式，捕捉现实世界实体之间的关系，使人类和机器都能理解 Hogan 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib31))。它们以图中的三元组形式存储数据，节点表示实体（如人或地点），边表示关系。它们表示复杂相互关系的能力使其在各种领域中得到了应用 Fensel 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib21))。KGs 被用于语义搜索，以增强搜索引擎的语义理解 Singhal ([2012](https://arxiv.org/html/2311.07914v2#bib.bib87))，企业知识管理 Deng 等人 ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib18))，供应链优化 Deng 等人 ([2023a](https://arxiv.org/html/2311.07914v2#bib.bib17))，教育 Agrawal 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib3))，金融欺诈检测 Mao 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib59))，网络安全 Agrawal 等人 ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib4))，推荐系统 Guo 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib26))，以及问答系统 Agrawal 等人 ([2023a](https://arxiv.org/html/2311.07914v2#bib.bib2))；Omar 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib66))；Jiang 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib39))。

## 3 知识图谱增强的 LLMs

LLMs 主要有三点故障：由于缺乏上下文而无法理解问题、缺乏足够的知识以准确回应，或无法记忆特定的事实。提高这些模型的认知能力涉及完善它们的推理过程、优化学习机制，以及建立验证结果的机制。本调查全面回顾了现有的方法，旨在通过这三种技术的知识图谱增强来减轻幻觉现象并提高 LLMs 的推理能力。我们将其分类为知识感知推理、知识感知学习和知识感知验证。图 [2](https://arxiv.org/html/2311.07914v2#S1.F2 "图 2 ‣ 1 介绍 ‣ 知识图谱能否减少 LLMs 的幻觉？：一项调查") 详细说明了这些类别中的关键工作。

![参见说明](img/8c72466cb6d88f837699ec690e9a135e.png)

图 3：通过结合 KG 增强检索的知识感知推理 Baek 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib7))。

### 3.1 知识感知推理

在 LLM 中，“推理”意味着根据输入上下文从预训练模型生成文本或预测。挑战包括由于模糊的输入、不清晰的上下文、知识差距、训练数据偏差或无法对未见场景进行泛化而产生的错误或次优输出。LLM 常常在多步骤推理方面遇到困难，与人类不同，它们不能寻求额外的信息来澄清模糊的查询。为了提高 LLM 的推理能力，研究人员集成了 KGs 以获得结构化的符号知识，主要通过在输入层面上将其纳入以增强上下文理解。这些方法进一步被分类为“KG-增强检索”、“KG-增强推理”和“KG-控制生成”。

#### 3.1.1 KG-增强检索

检索增强生成模型如 RAG Lewis et al. ([2020](https://arxiv.org/html/2311.07914v2#bib.bib47)) 和 RALM Ram et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib77)) 通过在生成过程中提供相关文档来提高 LLM 的上下文意识，从而减少幻觉现象，而不改变 LLM 架构。这些方法对需要外部知识的任务非常有帮助，增强了输入中的 top-k 相关文档。然而，如图 [3](https://arxiv.org/html/2311.07914v2#S3.F3 "Figure 3 ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey") 所示，使用来自结构化来源或知识图谱的组织良好的、策划过的知识，更能与事实准确性紧密对齐。Baek et al. Baek et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib7)) 引入了 KAPING，它将问题中的实体与知识图谱中的相关三元组进行匹配，以实现零样本问答。Wu et al. Wu et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib106)) 发现，将这些三元组转换为文本化陈述能提升 LLM 的性能。Sen et al. Sen et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib82)) 开发了一个在 KGQA 模型上训练的检索器模块，解决了基于相似度检索在复杂问题中的不足。StructGPT Jiang et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib37)) 用知识图谱、表格和数据库中的数据增强 LLM，通过结构化查询进行信息提取。其他值得注意的工作包括 IAG Zhang et al. ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib120))、KICGPT Wei et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib103)) 和 SAFARI Wang et al. ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib97))。

LLMs 作为自然语言接口，提取和生成信息而不依赖其内部知识。像 ChatGPT 插件这样的工具使用 Langchain Chase ([2022](https://arxiv.org/html/2311.07914v2#bib.bib13)) 和 LlamaIndex Liu ([2022](https://arxiv.org/html/2311.07914v2#bib.bib51)) 来整合外部数据，促使 LLMs 提供基于上下文检索的、知识增强的输出。然而，单纯依赖内部数据库可能会因知识库的限制而影响性能。Mallen 等人 Mallen et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib58)) 调查了 LLMs 的事实知识保留，发现用检索到的数据增强能提高性能。然而，这些模型在流行实体和关系上表现良好，但在不太流行的主题上则面临挑战，增加模型规模在这些情况下并不会改善性能。

#### 3.1.2 KG-增强推理

KG-增强检索方法有效地回答事实性问题。然而，需要推理的问题需要更熟练的方法，例如将复杂的多步骤任务分解为可管理的子查询，如 Qiao 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib75)) 和 Liu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib53)) 详细介绍的。这些技术在我们的研究中被称为 KG-增强推理方法。遵循人类推理过程的直觉，Chain of Thought (CoT) Wei et al. ([2022a](https://arxiv.org/html/2311.07914v2#bib.bib101))、Chain of Thought with Self-Consistency (CoT-SC) Wang et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib99))、Program-Aided Language Model (PAL) Gao et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib24)) 和 Reason and Act (ReAct) Yao et al. ([2022](https://arxiv.org/html/2311.07914v2#bib.bib110))、Reflexion Shinn et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib85)) 方法通过一系列中间推理步骤提升 LLMs 的复杂推理能力。这些方法模拟人类逐步推理，帮助理解和调试模型的推理过程。它们对数学问题、常识推理以及通过语言解释步骤解决的符号任务很有用。Tree of Thoughts (ToT) Yao et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib109)) 方法通过探索连贯的文本单元作为中间步骤来增强这一点，使 LLMs 能够考虑多条路径、自我评估并做出明智的决策。

使用知识图谱的不同知识增强技术，受到 CoT 和 ToT 提示的启发，提升了在领域特定和开放领域任务中的推理能力。“基于检索的再思考”He 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib30)) 模型利用从链式思维提示中分解的推理步骤来检索外部知识，从而提供更准确和真实的解释。IRCoT Trivedi 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib92)) 交替生成链式思维 (CoT) 和从图谱中检索知识，迭代引导检索和推理以应对多步骤问题。MindMap Wen 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib105)) 引入了一种即插即用的方法，以激发 LLMs 中的图思维推理。Reasoning on Graphs (RoG) Luo 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib57)) 利用知识图谱基于各种关系创建真实的推理路径，从而实现 LLMs 中的可解释和准确的推理。其他补充进展包括 MoT Li 和 Qiu ([2023](https://arxiv.org/html/2311.07914v2#bib.bib49))、民主化推理 Wang 等人 ([2023c](https://arxiv.org/html/2311.07914v2#bib.bib100))、ReCEval Prasad 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib74))、RAP Hao 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib28))、EoT Yin 等人 ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib114)) 和 Tree Prompting Singh 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib86))，它们各自独特地推动了 LLMs 中推理能力的发展。

探索提示与大型语言模型在推理任务中的互动是一个令人兴奋的研究方向 Liu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib53))。一个关键方面是设计针对特定用例的提示。然而，神经网络是否真正进行“推理”的根本问题仍未解答，而且是否遵循正确的推理路径总能导致准确答案尚不确定 Qiao 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib75))；Jiang 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib38))。

#### 3.1.3 知识控制生成

这些方法使用语言模型生成知识，然后使用探测或 API 调用进行任务。刘等人 Liu 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib52)) 使用第二个模型生成与问题相关的知识声明以进行推理。Binder Cheng 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib15)) 使用 Codex 解析上下文并生成任务 API 调用。KB-Binder Li 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib48)) 还使用 Codex 为问题创建逻辑草稿，整合知识图谱以提供完整的答案。Brate 等人 Brate 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib11)) 为知识图谱中的实体创建填空式提示，通过 SPARQL 查询增强辅助数据，提高召回率和准确性。KnowPrompt 陈等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib14)) 从预训练模型生成提示，并对填空式任务中的关系提取进行调优。BeamQA Atif 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib6)) 使用语言模型生成推理路径，用于基于知识图谱嵌入的链接预测搜索。ALCUNA 尹等人 ([2023a](https://arxiv.org/html/2311.07914v2#bib.bib113)) 和 PRCA 杨等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib108)) 是其他重要的控制生成方法。

生成式人工智能中的保护措施设定了模型的操作边界，确保输出生成的安全性和可靠性。Nvidia 的 NeMo 保护措施 Rebecdea 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib78)) 引导企业应用中的对话流程，以满足安全和保密标准。知识控制生成确保与事实对齐，并防止错误信息。知识图谱本体可以提供特定领域的约束，帮助大型语言模型（LLMs）定义输出生成的边界。

### 3.2 知识感知训练

我们可以在另一个阶段解决大型语言模型中的幻觉问题，即通过改进模型预训练阶段的训练数据质量或通过对预训练语言模型（PLM）进行微调以适应特定任务或领域来优化其学习。我们将这些方法分类为知识感知预训练和知识感知微调。

#### 3.2.1 知识感知预训练

训练数据的质量和多样性对减少大型语言模型（LLMs）的幻觉现象至关重要。整合知识图谱可以提供关于实体及其相互关系的结构化信息，提升 LLMs 的理解能力，并有助于生成更准确反映现实世界实体复杂性的文本。然而，从零开始训练非常耗费资源且成本高昂。研究人员提出了不同的方法来通过在训练数据中增强知识图谱来进行预训练，具体包括 Yu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib116))；Fu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib23))；Deng 等人 ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib18))；Liu 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib54))；Poerner 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib73))；Peters 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib71))。我们将这些方法进一步分类如下：

1.  1.

    知识增强模型：这些方法通过将大规模文本语料库与知识图谱（KGs）结合，来改善语言表示。ERNIE Zhang 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib121)) 使用掩码语言建模（MLM）和下一个句子预测（NSP）进行预训练，以捕捉文本的词汇和句法元素，将上下文与知识事实结合以进行预测。ERNIE 3.0 Sun 等人 ([2021a](https://arxiv.org/html/2311.07914v2#bib.bib88)) 进一步演化，通过将自回归模型与自编码网络整合，解决了单一自回归框架在探索增强知识方面的局限性。与此同时，Rosset 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib79)) 通过实体标记词典引入了知识感知输入，增强了语义理解，而不改变变换器架构。

1.  2.

    知识引导掩码：知识图谱引导的实体掩码方案 Shen 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib83))；[Zhang 等人](https://arxiv.org/html/2311.07914v2#bib.bib118) 利用链接知识图谱掩码文本中的关键实体，通过利用关系知识提升了问答和知识库填充任务的效果。类似地，情感知识增强预训练（SKEP） Tian 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib91)) 采用情感掩码来开发统一的情感表示，从而提升了各种情感分析任务的性能。

1.  3.

    知识融合: 这些方法通过图查询编码器将知识图谱（KGs）集成到大型语言模型（LLMs）中 Wang 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib98)); Ke 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib43)); He 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib29))。如图 [4](https://arxiv.org/html/2311.07914v2#S3.F4 "图 4 ‣ 3.2.1 知识感知预训练 ‣ 3.2 知识感知训练 ‣ 3 知识图谱增强的大型语言模型 ‣ 知识图谱能否减少大型语言模型中的幻觉？：一项调查")所示，JointLK Sun 等人 ([2021b](https://arxiv.org/html/2311.07914v2#bib.bib89)) 采用了知识融合和联合推理用于常识问答，选择性地使用相关的 KG 节点，并在文本和图编码器之间同步更新。LKPNR Runfeng 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib80)) 将 LLMs 与 KGs 结合，通过 KG 增强的编码器来提高复杂新闻文本的语义理解，创建个性化新闻推荐框架。

1.  4.

    知识探测: 知识探测涉及检查语言模型以评估其事实性和常识知识 Petroni 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib72))。这一过程有助于评估和提升模型的性能 Kassner 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib42)); Swamy 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib90))。Rewire-then-Probe Meng 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib61)) 引入了一种自监督对比探测方法，利用生物医学知识图谱学习语言表示。

![参见说明](img/5a528bb8a06b700e24ff50603645707b.png)

图 4: 知识融合下的知识感知预训练  Sun 等人 ([2021b](https://arxiv.org/html/2311.07914v2#bib.bib89))。

#### 3.2.2 知识感知微调

微调通过在相关数据集上训练 LLMs，使其适应特定领域，使用选择的架构和超参数来修改模型的权重，以提高任务性能 Guu 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib27)); Hu 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib32)); Lu 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib56)); Dettmers 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib19))。KGs 还可以进一步调整这些模型，以更新和扩展它们的内部知识，适应领域特定的任务，如自定义命名实体识别 Agrawal 等人 ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib4))，以及文本摘要 Kang 等人 ([2022a](https://arxiv.org/html/2311.07914v2#bib.bib40))。

SKILL Moiseev 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib63)) 使用了从 WikiData 转换的合成句子，Seminar 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib81)) 和 KELM Agarwal 等人 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib1)) 使用了知识图谱（KGs）来微调预训练模型检查点。KGLM Youn 和 Tagkopoulos ([2022](https://arxiv.org/html/2311.07914v2#bib.bib115)) 采用了带有 KG 三元组的实体-关系嵌入层进行链接预测任务。跨语言推理 Foroutan 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib22)) 通过使用自注意力网络对 MultiLM、mBERT 和 mT5 模型进行微调，并利用逻辑数据集来改进。LLMs 通过使用包含少量 CoT 推理提示的数据集和微调进一步提高了性能 Kim 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib44))；Huang 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib34))。

对 ChatGPT 等语言模型进行微调，比从头开始训练更高效，但受限于其 2021 年的最后知识更新。它使用策划的、领域特定的知识图谱处理超出此截止日期的查询。更新的知识在模型中整合的程度仍有待确定。Onoe 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib67)) 的评估框架表明，尽管模型可以回忆新实体的事实，但基于这些事实进行推断更为困难。更新知识对现有实体的影响仍是一个未解的研究问题。

### 3.3 知识感知验证

第三类方法使用结构化数据作为事实检查机制，为模型提供验证信息的参考。知识图谱可以提供全面的解释，并用于证明模型的决策。这些方法还帮助在事实之间强制一致性，避免了繁琐的人工标注数据，并提高了生成内容的可靠性。

事实感知语言模型 KGLM Logan IV 等人 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib55)) 参考知识图谱生成与上下文相关的实体和事实。SURGE Kang 等人 ([2022b](https://arxiv.org/html/2311.07914v2#bib.bib41)) 从知识图谱中检索高相似度的上下文相关三元组作为子图。“文本评论员”分类器 Lango 和 Dušek ([2023](https://arxiv.org/html/2311.07914v2#bib.bib45)) 被提出以通过评估输入数据与生成文本之间的匹配来引导生成。FOLK Wang 和 Shu ([2023](https://arxiv.org/html/2311.07914v2#bib.bib96)) 使用一阶逻辑 (FOL) 谓词在在线虚假信息中进行声明验证。除了验证，FOLK 还生成明确的解释，为人工事实检查员理解和解释模型决策提供了有价值的帮助。这种方法在虚假信息检测的背景下，有助于模型输出的准确性和可解释性。

|  |  | 比较属性 |
| --- | --- | --- |
| 分类 | 代表方法 |

&#124; 下游任务 &#124;

&#124; 任务 &#124;

| KG 数据集 | LLM | 训练 |
| --- | --- | --- |
|  | KAPING Baek 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib7)) | 问答 | Mintaka, WebQSP |

&#124; T5, T0, OPT, &#124;

&#124; GPT-3 &#124;

|  |
| --- |
|  | Rigel Facts Sen 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib82)) | 问答 |

&#124; WebQuestions, ComplexWebQuestions, &#124;

&#124; Mintaka, LC-QuAD &#124;

|

&#124; Flan-T5, T0, &#124;

&#124; OPT, AlexaTM &#124;

|  |
| --- |
| KG-增强检索 |

&#124; 检索-重写-回答 &#124;

&#124; Wu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib106)) &#124;

| 问答 | MetaQA, WebQSP, WebQ, ZJQA |
| --- | --- |

&#124; ChatGPT, Llama 2, &#124;

&#124; Flan-T5, T0, T5 &#124;

| X⃝ |
| --- |
|  | IRCoT Trivedi 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib92)) | 多步骤推理问答 |

&#124; HotpotQA, 2WikiMultihopQA, &#124;

&#124; MusiQue, IIRC &#124;

| GPT3, Flan-T5 |  |
| --- | --- |
|  | MindMap Wen 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib105)) | 医疗诊断 |

&#124; GenMedGPT-5k, &#124;

&#124; CMCQA, ExplainCPE &#124;

| GPT-3.5, GPT-4 |  |
| --- | --- |
| KG-增强推理 | RoG Luo 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib57)) | 推理 |

&#124; WebQSP, &#124;

&#124; 复杂的 WebQuestions (CWQ) &#124;

| Llama 2-Chat-7B | X⃝ |
| --- | --- |
|  | KnowPrompt Chen 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib14)) | 关系抽取和标记 | SemEval, DialogRE, TACRED | RoBERTa_large | 少样本训练 |
|  | BINDER Cheng 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib15)) |

&#124; 信息抽取, &#124;

&#124; 常识问答 &#124;

| WikiTableQuestions, TabFact | Codex |
| --- | --- |

&#124; API 调用 / 少样本 &#124;

&#124; 上下文学习 &#124;

|

| 知识控制生成 | BeamQA Atif 等 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib6)) | 生成问题 | MetaQA, WebQSP, | T5, BART | 微调 4 个 epoch |
| --- | --- | --- | --- | --- | --- |
|  | SKEP Tian 等 ([2020](https://arxiv.org/html/2311.07914v2#bib.bib91)) | 情感分析 |

&#124; SST, 亚马逊, &#124;

&#124; Sem, MPQA &#124;

| BERT, RoBERTa |
| --- |

&#124; 编码器训练于 &#124;

&#124; 3.2m 训练数据 &#124;

|

|  | JointLK Sun 等 ([2021b](https://arxiv.org/html/2311.07914v2#bib.bib89)) |
| --- | --- |

&#124; 常识问题 &#124;

&#124; 答案生成 &#124;

|

&#124; CommonSenseQA, &#124;

&#124; OpenBookQA &#124;

| RoBERTa-Large |
| --- |

&#124; LM/图编码器训练于 &#124;

&#124; 联合训练 20 GPU 小时 &#124;

|

| 知识感知预训练 | LKPNR Runfeng 等 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib80)) |
| --- | --- |

&#124; 个性化新闻 &#124;

&#124; 推荐系统 &#124;

| MIND |
| --- |

&#124; ChatGLM2, &#124;

&#124; Llama 2, RWKV &#124;

|

&#124; LK-Encoders 训练于 &#124;

&#124; 用于 200K 用户点击日志的 GPU &#124;

|

|  | SKILL Moiseev 等 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib63)) | 闭卷 QA 任务 | Wikidata, KELM, MetaQA |
| --- | --- | --- | --- |

&#124; T5-base, L, &#124;

&#124; XXL 模型 &#124;

| T5 经过 50k 步微调 |
| --- |
|  | KGLM Youn 和 Tagkopoulos ([2022](https://arxiv.org/html/2311.07914v2#bib.bib115)) | 链接预测 | WN18RR, FB15k-237, UMLS | RoBERTa Large | 微调 5 个 epoch |
| 知识感知微调 | 神经符号学 Baldazzi 等 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib8)) | 银行客户查询 | Chase EKG | T5-large | 微调 10 个 epoch |
|  | 事实感知 LM Logan IV 等 ([2019](https://arxiv.org/html/2311.07914v2#bib.bib55)) | 事实生成 | 链接 WikiText-2 | TransE |

&#124; Transformer 训练于 &#124;

&#124; 256 维 KG 嵌入 &#124;

|

|  | SURGE Kang 等 ([2022b](https://arxiv.org/html/2311.07914v2#bib.bib41)) | 对话生成 | OpenDialKG | T5-small | X⃝ |
| --- | --- | --- | --- | --- | --- |
| 知识感知验证 | FOLK Wang 和 Shu ([2023](https://arxiv.org/html/2311.07914v2#bib.bib96)) |

&#124; 声明验证于 &#124;

&#124; 在线虚假信息 &#124;

|

&#124; HoVER, FEVEROUS, &#124;

&#124; SciFact-Open &#124;

|

&#124; Llama(7B), Llama(13B), &#124;

&#124; Llama(30B) &#124;

| X⃝ |
| --- |

表 1：知识图谱增强 LLM 方法的比较属性

## 4 讨论、挑战与未来

在本节中，我们探讨了 KG 增强 LLM 技术在减少幻觉和提高 LLM 性能与可靠性方面的有效性。我们还识别了与每种方法相关的关键挑战，并提出了这一不断发展的领域中的潜在研究方向。

### 4.1 资源

表格 [1](https://arxiv.org/html/2311.07914v2#S3.T1 "Table 1 ‣ 3.3 Knowledge-Aware Validation ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey") 详细介绍了不同 KG 增强 LLM 方法的关键特征，强调了它们在特定行业中使用领域特定知识图谱的应用。推理方法使用了通用知识和常识推理数据集进行问答任务，而无需重新训练 LLM。Mindmap Wen 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib105)) 展示了在医疗保健中的应用，通过 GPT-4 扩充临床数据集。Meng 等人 ([2021](https://arxiv.org/html/2311.07914v2#bib.bib61)) 使用生物医学知识图谱 Unified Medical Language System (UMLS) Metathesaurus 对 T5 和 BART 模型进行了预训练。LKPNR Runfeng 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib80)) 在 MIND-200K 用户点击日志上对 LM 和图编码器进行了预训练，以提供个性化新闻推荐。Martino 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib60)) 使用知识注入减少了在回应零售店的在线客户评论时的幻觉。Dong 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib20)) 通过从源文档中链接外部源知识库，展示了在文本摘要任务中对源文档的忠实性改善。Baldazzi 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib8)) 在金融客户服务企业 KG 上对 T5-large 进行了微调。

### 4.2 评估指标

应用了各种标准来评估知识图谱增强在减少 LLM 幻觉方面的有效性。

准确性：与未增强 KG 知识的情况进行准确性比较 Baek 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib7)); Zhang 等人 ([2023b](https://arxiv.org/html/2311.07914v2#bib.bib120))。

Top-K 和 MRR：检索性能通过检索到的三元组对生成答案的相关性来衡量。均值倒数排名（MRR）和 Top-K 准确性确定了正确检索的包含答案的三元组的排名 Baek 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib7)); Sen 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib82))。KG 三元组的有效性被评估为“有帮助”或“有害”，并与“没有知识”提供的情况进行了比较 Wu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib106))。

Hits@1：评估答案的准确性，并检查多选题答案的覆盖范围 Luo 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib57)); Wu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib106)); Wei 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib103))。

执行准确性（EA）：控制生成方法，如 Binder Cheng 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib15))，使用执行准确性（EA）作为度量标准，评估语义解析、API 调用生成和代码执行的成功率。

精确匹配（EM）：模型在微调后的表现通过 EM（精确匹配）分数在测试集上进行评估 Moiseev 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib63))。

人工评估：验证方法手动评估，以评估句子完成的解释质量、覆盖范围、逻辑合理性、流畅性和事实准确性 Wang 和 Shu ([2023](https://arxiv.org/html/2311.07914v2#bib.bib96))；Kang 等人 ([2022b](https://arxiv.org/html/2311.07914v2#bib.bib41))。需要从不同方面评估事实准确性，首先验证信息的准确性和可靠性，其次识别虚构或“幻觉”信息的实例。

### 4.3 性能分析

提取的事实增强了小型语言模型：由于参数空间有限，小型模型在预训练时难以整合大量知识。通过从知识图谱中增强事实，而不是增加模型规模，问答任务的回答正确率提高了超过$80\%$ Baek 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib7))；Sen 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib82))；Wu 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib106))。然而，这些方法在处理复杂查询时的成功率严重依赖于检索模块，而这些模块的能力仅限于知识图谱 BehnamGhader 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib9))。

步骤推理在较大模型中更为有效：CoT 方法的变体提供了具有成本效益的控制和任务特定的调优，提升了模型性能。例如，RoG Luo 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib57)) 报告称，通过知识图谱增强，ChatGPT 的推理任务准确率从$66.8\%$提高到$85.7\%$。类似地，Mindmap Wen 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib105)) 使用临床推理图将疾病诊断和药物推荐的准确率提高到了$88.2\%$。

控制生成提升性能：知识控制生成方法在准确性和上下文相关性方面超越了基线模型，增强了处理多样化查询的能力 Chen 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib14))；Cheng 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib15))；Atif 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib6))。然而，这些方法的质量可能有所不同，有时容易生成不准确或不相关的信息。

预训练和微调成本高：预训练和微调显著提高了领域特定任务的性能。然而，这些改进需要大量的计算资源，如表格[1](https://arxiv.org/html/2311.07914v2#S3.T1 "Table 1 ‣ 3.3 Knowledge-Aware Validation ‣ 3 Knowledge Graph-Enhanced LLMs ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")所示。此外，微调的数据依赖性使其任务特定，限制了其迁移性和泛化能力 Gueta et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib25)); Wang and Shu ([2023](https://arxiv.org/html/2311.07914v2#bib.bib96))。

事实核查确保可靠性：通过事实核查对知识进行验证，可以减少模型生成的数据与知识图谱的不一致，但这会增加计算负担，并可能遗漏一些不准确之处 Kang et al. ([2022b](https://arxiv.org/html/2311.07914v2#bib.bib41)); Lango and Dušek ([2023](https://arxiv.org/html/2311.07914v2#bib.bib45))。

知识增强的效果也受到知识图谱的规模及其对查询响应的影响。标准方法包括对预训练模型进行微调以提高可靠性，但成本较高；以及基于示例的提示，在某些推理任务中效果较差 Brown et al. ([2020](https://arxiv.org/html/2311.07914v2#bib.bib12)); Rae et al. ([2021](https://arxiv.org/html/2311.07914v2#bib.bib76))。Zhang et al. Zhang et al. ([2023a](https://arxiv.org/html/2311.07914v2#bib.bib119))指出，语言模型的不一致性往往源于上下文使用不当。方法选择取决于具体的使用案例和可用资源。Wang et al. Wang et al. ([2023a](https://arxiv.org/html/2311.07914v2#bib.bib95))展示了通过检索对解码器-only LLMs 进行预训练可以提高知识密集型任务的事实准确性，而 Shi et al. Shi et al. ([2023](https://arxiv.org/html/2311.07914v2#bib.bib84))开发了 GraphNarrative，一个旨在减少幻觉的数据库，对微调 LLMs 有帮助。

### 4.4 趋势分析

图 [5](https://arxiv.org/html/2311.07914v2#S4.F5 "图 5 ‣ 4.4 趋势分析 ‣ 4 讨论、挑战与未来 ‣ 知识图谱能否减少 LLMs 的幻觉？：调查") 显示了 2019 年至 2023 年使用不同知识图谱增强技术的研究趋势。此处的气泡大小代表了每个知识图谱增强类别的论文数量，从一篇到八篇不等。通过将知识图谱添加到训练语料库中的预训练方法在语言模型发展初期占主导地位。经过广泛的 GPT 系列 LLMs 后，重新训练数十亿参数的大模型变得不切实际且资源密集。更多的努力集中在使用任务特定数据对模型进行微调，而不是从头开始训练。最近，开始转向使用知识增强的检索、推理、生成和验证方法，而不增加额外的训练成本。

![参考说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 5：研究趋势多年来- 气泡的大小表示我们观察到的每个知识图谱增强类别的论文数量：最小大小（#论文=1），最大大小（#论文=8）

### 4.5 未来方向

这里是一些潜在的未来研究方向供进一步探讨：

提高 KG 质量：a⃝上下文感知：不断适应变化的上下文和新信息的动态 KGs 可以有效改善 LLMs。b⃝解决偏见：KGs 中的公平算法可以确保 KGs 不会传播偏见或错误信息。c⃝跨领域知识：将来自科学、艺术和历史等不同领域的知识整合到一个图谱中可以增强 LLM 响应的深度和细微性。d⃝多模态：将图像、视频和音频等多模态数据添加到 KGs 中可以丰富数据池，改善 LLMs 的上下文响应。

专家混合（MoE）LLMs：正在努力优化 MoE 架构以扩展 LLMs 并增加其容量而不增加计算量 Zhou 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib124))。将 MoE 与知识图谱集成 Yu 等人 ([2022](https://arxiv.org/html/2311.07914v2#bib.bib117)) 可以开发适应性学习策略，用于基于上下文的专家利用，并提高 MoE-LLMs 的可解释性和透明性。

符号-子符号统一：知识结构，如符号化知识图谱（KGs）和子符号向量，使得在大型语言模型（LLMs）中进行多样的推理成为可能，模仿人类思维融合结构化理论的能力 Núñez-Molina 等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib65))。

LLM 和 KG 的协同：LLMs 正在用于链接预测和知识图谱补全，肖等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib107))；维塞利等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib94))。LLM 与 KG 的协同是一种潜在的方向，通过数据和知识的和谐结合，双向推理过程可以使两个组件相互增强其能力，潘等人 ([2023](https://arxiv.org/html/2311.07914v2#bib.bib70))。

因果意识：将因果关系融入知识图谱中，魏等人 ([2022b](https://arxiv.org/html/2311.07914v2#bib.bib104))，将增强大语言模型（LLMs） grasp 因果关系的能力，而不仅仅是识别相关性。这一进展将使 LLMs 更好地理解事件或实体之间的因果关系，显著提升它们的推理和预测能力。

知识图谱的进展有望大大增强 LLMs，使其更加相关、响应迅速且准确。这旨在创建更可靠和值得信赖的语言模型，推动强健和负责任的 AI 系统的发展。

## 5 结论

在这项调查中，我们系统地研究了将知识图谱（KGs）整合到大语言模型（LLMs）中，以减少幻觉现象并提高推理准确性。我们强调了在推理、模型训练和输出验证阶段使用 KGs 提升 LLM 性能的好处。尽管已经取得了显著进展，我们仍强调持续创新的必要性，并提出了未来的方向，以促进更先进的 KG 增强 LLM 的发展。

## 6 限制

在本文中，我们对基于知识图谱的增强技术在 LLMs 中的应用进行了全面回顾，特别关注它们在解决幻觉现象方面的能力。我们识别了这些技术的共同点，并根据其机制和方法将其分为三大类。此外，我们还系统地评估了这些方法的性能。在第[1](https://arxiv.org/html/2311.07914v2#S1 "1 Introduction ‣ Can Knowledge Graphs Reduce Hallucinations in LLMs? : A Survey")节中，我们将我们的工作与现有相关调查进行了比较，并将继续添加更多相关方法。然而，尽管我们付出了努力，但仍需认识到本文中可能存在的某些限制。

参考文献和方法。由于页面限制，我们可能无法包含所有相关参考文献和详细技术信息。我们的研究主要集中于 2019 年至 2023 年间开发的最先进方法，主要来源于 ACL、EMNLP、NAACL、ICLR、ICML 和 arXiv 等知名会议和平台。我们致力于保持我们的工作与时俱进。

分类和比较。我们主要根据其主要增强方法对这些方法进行分类。在某些情况下，结合多种方法的混合研究可能会根据具体标准被归类为不同的类别。需要注意的是，我们的分析基于现有工作的表现，使用当前的实验和数据集。鉴于这一领域的快速发展，基准测试和基线模型可能会发生变化，从而导致这些评估的差异。

## 致谢

本材料基于国家科学基金会资助的工作，资助编号为 2114789。

## 参考文献

+   Agarwal 等人（2020）Oshin Agarwal, Heming Ge, Siamak Shakeri, 和 Rami Al-Rfou. 2020. 基于知识图谱的合成语料库生成用于知识增强语言模型预训练。*arXiv 预印本 arXiv:2010.12688*。

+   Agrawal 等人（2023a）Garima Agrawal, Dimitri Bertsekas, 和 Huan Liu. 2023a. 基于拍卖的知识图谱问答学习。*Information*, 14(6):336。

+   Agrawal 等人（2022）Garima Agrawal, Yuli Deng, Jongchan Park, Huan Liu, 和 Ying-Chih Chen. 2022. 从非结构化文本构建知识图谱：在网络安全教育中的应用和影响分析。*Information*, 13(11):526。

+   Agrawal 等人（2023b）Garima Agrawal, Kuntal Pal, Yuli Deng, Huan Liu, 和 Chitta Baral. 2023b. Aiseckg: 网络安全教育的知识图谱数据集。*AAAI-MAKE 2023: 需要结合机器学习的挑战 2023*。

+   AlKhamissi 等人（2022）Badr AlKhamissi, Millicent Li, Asli Celikyilmaz, Mona Diab, 和 Marjan Ghazvininejad. 2022. 语言模型作为知识库的综述。*arXiv 预印本 arXiv:2204.06031*。

+   Atif 等人（2023）Farah Atif, Ola El Khatib, 和 Djellel Difallah. 2023. Beamqa: 多跳知识图谱问答，结合序列到序列预测和束搜索。在*第 46 届国际 ACM SIGIR 信息检索研究与发展会议论文集*，第 781–790 页。

+   Baek 等人（2023）Jinheon Baek, Alham Fikri Aji, 和 Amir Saffari. 2023. 知识增强语言模型提示用于零样本知识图谱问答。*arXiv 预印本 arXiv:2306.04136*。

+   Baldazzi 等人（2023）Teodoro Baldazzi, Luigi Bellomarini, Stefano Ceri, Andrea Colombo, Andrea Gentili, 和 Emanuel Sallinger. 2023. 通过本体推理微调大型企业语言模型。*arXiv 预印本 arXiv:2306.10723*。

+   BehnamGhader 等人（2022）Parishad BehnamGhader, Santiago Miret, 和 Siva Reddy. 2022. 检索增强语言模型能推理吗？检索器和语言模型之间的责备游戏。*arXiv 预印本 arXiv:2212.09146*。

+   Bengio 等人（2000）Yoshua Bengio, Réjean Ducharme, 和 Pascal Vincent. 2000. 神经概率语言模型。*神经信息处理系统进展*, 13。

+   Brate et al. (2022) Ryan Brate, Minh-Hoang Dang, Fabian Hoppe, Yuan He, Albert Meroño-Peñuela, 和 Vijay Sadashivaiah. 2022. 通过丰富知识图谱的提示改善语言模型预测。发表于 *DL4KG@ ISWC2022*。

+   Brown et al. (2020) Tom Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared D Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, 等人。2020. 语言模型是少样本学习者。*神经信息处理系统进展*，33:1877–1901。

+   Chase (2022) Harrison Chase. 2022. [LangChain](https://github.com/langchain-ai/langchain)。

+   Chen et al. (2022) Xiang Chen, Ningyu Zhang, Xin Xie, Shumin Deng, Yunzhi Yao, Chuanqi Tan, Fei Huang, Luo Si, 和 Huajun Chen. 2022. Knowprompt: 通过协同优化的知识感知提示调优用于关系抽取。发表于 *2022 年 ACM 网页会议论文集*，页码 2778–2788。

+   Cheng et al. (2022) Zhoujun Cheng, Tianbao Xie, Peng Shi, Chengzu Li, Rahul Nadkarni, Yushi Hu, Caiming Xiong, Dragomir Radev, Mari Ostendorf, Luke Zettlemoyer, 等人。2022. 将语言模型绑定于符号语言。*arXiv 预印本 arXiv:2210.02875*。

+   Chowdhery et al. (2022) Aakanksha Chowdhery, Sharan Narang, Jacob Devlin, Maarten Bosma, Gaurav Mishra, Adam Roberts, Paul Barham, Hyung Won Chung, Charles Sutton, Sebastian Gehrmann, 等人。2022. Palm: 通过路径扩展语言建模。*arXiv 预印本 arXiv:2204.02311*。

+   Deng et al. (2023a) Jianfeng Deng, Chong Chen, Xinyi Huang, Wenyan Chen, 和 Lianglun Cheng. 2023a. 供应链管理事件逻辑知识图谱的构建研究。*高级工程信息学*，56:101921。

+   Deng et al. (2023b) Shumin Deng, Chengming Wang, Zhoubo Li, Ningyu Zhang, Zelin Dai, Hehong Chen, Feiyu Xiong, Ming Yan, Qiang Chen, Mosha Chen, 等人。2023b. 十亿规模预训练多模态商业知识图谱的构建与应用。发表于 *2023 IEEE 第 39 届国际数据工程会议 (ICDE)*，页码 2988–3002。IEEE。

+   Dettmers et al. (2023) Tim Dettmers, Artidoro Pagnoni, Ari Holtzman, 和 Luke Zettlemoyer. 2023. Qlora: 高效的量化语言模型微调。*arXiv 预印本 arXiv:2305.14314*。

+   Dong et al. (2022) Yue Dong, John Wieting, 和 Pat Verga. 2022. 忠于文档还是忠于世界？通过实体链接知识在抽象摘要中缓解幻觉。*arXiv 预印本 arXiv:2204.13761*。

+   Fensel et al. (2020) Dieter Fensel, Umutcan Şimşek, Kevin Angele, Elwin Huaman, Elias Kärle, Oleksandra Panasiuk, Ioan Toma, Jürgen Umbrich, Alexander Wahler, Dieter Fensel, 等人。2020. 我们为何需要知识图谱：应用。*知识图谱：方法论、工具和精选案例*，页码 95–112。

+   Foroutan et al. (2023) Negar Foroutan, Mohammadreza Banaei, Karl Aberer, 和 Antoine Bosselut。2023 年。打破语言障碍：通过结构化自注意力提高跨语言推理能力。发表于*计算语言学协会会议：EMNLP 2023*，页码 9422–9442。

+   Fu et al. (2023) Peng Fu, Yiming Zhang, Haobo Wang, Weikang Qiu, 和 Junbo Zhao。2023 年。重新审视知识注入框架。发表于*2023 年自然语言处理经验方法大会论文集*，页码 10983–10997。

+   Gao et al. (2023) Luyu Gao, Aman Madaan, Shuyan Zhou, Uri Alon, Pengfei Liu, Yiming Yang, Jamie Callan, 和 Graham Neubig。2023 年。PAL: 程序辅助语言模型。发表于*国际机器学习大会*，页码 10764–10799。PMLR。

+   Gueta et al. (2023) Almog Gueta, Elad Venezian, Colin Raffel, Noam Slonim, Yoav Katz, 和 Leshem Choshen。2023 年。知识是微调语言模型中权重空间的一个区域。*arXiv 预印本 arXiv:2302.04863*。

+   Guo et al. (2020) Qingyu Guo, Fuzhen Zhuang, Chuan Qin, Hengshu Zhu, Xing Xie, Hui Xiong, 和 Qing He。2020 年。基于知识图谱的推荐系统综述。*IEEE 知识与数据工程学报*，34(8):3549–3568。

+   Guu et al. (2020) Kelvin Guu, Kenton Lee, Zora Tung, Panupong Pasupat, 和 Mingwei Chang。2020 年。检索增强语言模型预训练。发表于*国际机器学习大会*，页码 3929–3938。PMLR。

+   Hao et al. (2023) Shibo Hao, Yi Gu, Haodi Ma, Joshua Jiahua Hong, Zhen Wang, Daisy Zhe Wang, 和 Zhiting Hu。2023 年。用语言模型进行推理就像用世界模型进行规划。*arXiv 预印本 arXiv:2305.14992*。

+   He et al. (2019) Bin He, Di Zhou, Jinghui Xiao, Qun Liu, Nicholas Jing Yuan, Tong Xu, 等人。2019 年。将图上下文知识融入预训练语言模型。*arXiv 预印本 arXiv:1912.00147*。

+   He et al. (2022) Hangfeng He, Hongming Zhang, 和 Dan Roth。2022 年。通过检索重新思考：忠实的大型语言模型推理。*arXiv 预印本 arXiv:2301.00303*。

+   Hogan et al. (2021) Aidan Hogan, Eva Blomqvist, Michael Cochez, Claudia d’Amato, Gerard De Melo, Claudio Gutierrez, Sabrina Kirrane, José Emilio Labra Gayo, Roberto Navigli, Sebastian Neumaier, 等人。2021 年。知识图谱。*ACM 计算调查 (CSUR)*，54(4):1–37。

+   Hu et al. (2021) Edward J Hu, Yelong Shen, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang, Lu Wang, 和 Weizhu Chen。2021 年。Lora: 大型语言模型的低秩适配。*arXiv 预印本 arXiv:2106.09685*。

+   Hu et al. (2023) Linmei Hu, Zeyi Liu, Ziwang Zhao, Lei Hou, Liqiang Nie, 和 Juanzi Li。2023 年。增强知识的预训练语言模型综述。*IEEE 知识与数据工程学报*。

+   Huang et al. (2022) Jiaxin Huang, Shixiang Shane Gu, Le Hou, Yuexin Wu, Xuezhi Wang, Hongkun Yu, 和 Jiawei Han。2022 年。大型语言模型可以自我改进。*arXiv 预印本 arXiv:2210.11610*。

+   Huang 和 Chang (2022) Jie Huang 和 Kevin Chen-Chuan Chang. 2022. Towards reasoning in large language models: A survey. *arXiv preprint arXiv:2212.10403*.

+   Ji 等 (2023) Ziwei Ji, Nayeon Lee, Rita Frieske, Tiezheng Yu, Dan Su, Yan Xu, Etsuko Ishii, Ye Jin Bang, Andrea Madotto, 和 Pascale Fung. 2023. Survey of hallucination in natural language generation. *ACM Computing Surveys*, 55(12):1–38.

+   Jiang 等 (2023) Jinhao Jiang, Kun Zhou, Zican Dong, Keming Ye, Wayne Xin Zhao, 和 Ji-Rong Wen. 2023. Structgpt: A general framework for large language model to reason over structured data. *arXiv preprint arXiv:2305.09645*.

+   Jiang 等 (2020) Zhengbao Jiang, Frank F Xu, Jun Araki, 和 Graham Neubig. 2020. How can we know what language models know? *Transactions of the Association for Computational Linguistics*, 8:423–438.

+   Jiang 等 (2021) Zhixue Jiang, Chengying Chi, 和 Yunyun Zhan. 2021. Research on medical question answering system based on knowledge graph. *IEEE Access*, 9:21094–21101.

+   Kang 等 (2022a) Minki Kang, Jinheon Baek, 和 Sung Ju Hwang. 2022a. Kala: knowledge-augmented language model adaptation. *arXiv preprint arXiv:2204.10555*.

+   Kang 等 (2022b) Minki Kang, Jin Myung Kwak, Jinheon Baek, 和 Sung Ju Hwang. 2022b. Knowledge-consistent dialogue generation with knowledge graphs. 在 *ICML 2022 Workshop on Knowledge Retrieval and Language Models*.

+   Kassner 等 (2021) Nora Kassner, Philipp Dufter, 和 Hinrich Schütze. 2021. Multilingual lama: Investigating knowledge in multilingual pretrained language models. *arXiv preprint arXiv:2102.00894*.

+   Ke 等 (2021) Pei Ke, Haozhe Ji, Yu Ran, Xin Cui, Liwei Wang, Linfeng Song, Xiaoyan Zhu, 和 Minlie Huang. 2021. Jointgt: Graph-text joint representation learning for text generation from knowledge graphs. *arXiv preprint arXiv:2106.10502*.

+   Kim 等 (2023) Seungone Kim, Se June Joo, Doyoung Kim, Joel Jang, Seonghyeon Ye, Jamin Shin, 和 Minjoon Seo. 2023. The cot collection: Improving zero-shot and few-shot learning of language models via chain-of-thought fine-tuning. *arXiv preprint arXiv:2305.14045*.

+   Lango 和 Dušek (2023) Mateusz Lango 和 Ondřej Dušek. 2023. Critic-driven decoding for mitigating hallucinations in data-to-text generation. 在 *Proceedings of the 2023 Conference on Empirical Methods in Natural Language Processing*, 页 2853–2862.

+   Lenat 和 Marcus (2023) Doug Lenat 和 Gary Marcus. 2023. Getting from generative ai to trustworthy ai: What llms might learn from cyc. *arXiv preprint arXiv:2308.04445*.

+   Lewis 等 (2020) Patrick Lewis, Ethan Perez, Aleksandra Piktus, Fabio Petroni, Vladimir Karpukhin, Naman Goyal, Heinrich Küttler, Mike Lewis, Wen-tau Yih, Tim Rocktäschel, 等. 2020. Retrieval-augmented generation for knowledge-intensive nlp tasks. *Advances in Neural Information Processing Systems*, 33:9459–9474.

+   Li 等人（2023）田乐·李、薛光·马、亚历克斯·庄、余·顾、余·苏和文虎·陈。2023 年。面向知识库问答的少量上下文学习。*arXiv 预印本 arXiv:2305.01750*。

+   Li 和 Qiu（2023）肖南·李和习鹏·邱。2023 年。Mot：思维记忆使 ChatGPT 能够自我改进。载于*2023 年自然语言处理实证方法会议*，第 6354–6374 页。

+   Liang 等人（2022）柯·梁、凌远·孟、孟·刘、岳·刘、文轩·涂、思伟·王、思航·周、鑫旺·刘和富春·孙。2022 年。不同类型知识图谱上的推理：静态、时间和多模态。*arXiv 预印本 arXiv:2212.05767*。

+   Liu（2022）杰瑞·刘。2022 年。[LlamaIndex](https://doi.org/10.5281/zenodo.1234)。

+   Liu 等人（2021）贾成·刘、阿丽莎·刘、希铭·卢、西恩·维莱克、彼得·韦斯特、罗南·勒·布拉斯、叶锦·崔和汉娜赫·哈吉什尔兹。2021 年。生成的知识提示用于常识推理。*arXiv 预印本 arXiv:2110.08387*。

+   Liu 等人（2023）彭飞·刘、魏哲·袁、锦兰·傅、郑宝·姜、广树·林和格雷厄姆·纽比格。2023 年。预训练、提示和预测：自然语言处理中的提示方法系统调查。*ACM Computing Surveys*，55(9)：1–35。

+   Liu 等人（2020）魏杰·刘、彭·周、哲·赵、志若·王、齐·朱、浩棠·邓和平·王。2020 年。K-BERT：利用知识图谱进行语言表示。载于*AAAI 人工智能会议论文集*，第 34 卷，第 2901–2908 页。

+   Logan IV 等人（2019）罗伯特·L·洛根 IV、尼尔森·F·刘、马修·E·彼得斯、马特·加德纳和萨米尔·辛格。2019 年。巴拉克的妻子希拉里：利用知识图谱进行事实感知的语言建模。*arXiv 预印本 arXiv:1906.07241*。

+   Lu 等人（2022）潘·卢、梁·邱、凯·魏·张、英年·吴、宋春·朱、坦梅·拉杰普罗希特、彼得·克拉克和阿什温·卡扬。2022 年。通过策略梯度的动态提示学习用于半结构化数学推理。*arXiv 预印本 arXiv:2209.14610*。

+   Luo 等人（2023）林浩·罗、袁芳·李、戈拉姆雷扎·哈法里和石瑞·潘。2023 年。图上的推理：忠实且可解释的大型语言模型推理。*arXiv 预印本 arXiv:2310.01061*。

+   Mallen 等人（2023）亚历克斯·马伦、阿卡里·浅井、维克托·钟、拉贾尔希·达斯、丹尼尔·卡沙比和汉娜赫·哈吉什尔兹。2023 年。当不信任语言模型时：调查参数化和非参数化记忆的有效性。载于*第 61 届计算语言学协会年会（第 1 卷：长论文）*，第 9802–9822 页。

+   Mao 等人（2022）许亭·毛、浩·孙、肖倩·朱和剑平·李。2022 年。使用相关方交易知识图谱进行金融欺诈检测。*Procedia Computer Science*，199：733–740。

+   Martino 等人（2023）阿丽安娜·马丁诺、迈克尔·亚内利和科琳· Truong。2023 年。知识注入以对抗大型语言模型（LLM）的幻觉。载于*欧洲语义网会议*，第 182–185 页。Springer。

+   Meng 等（2021）Zaiqiao Meng、Fangyu Liu、Ehsan Shareghi、Yixuan Su、Charlotte Collins 和 Nigel Collier。2021。重新连接-然后探测：探测预训练语言模型生物医学知识的对比性方法。*arXiv 预印本 arXiv:2110.08173*。

+   Mialon 等（2023）Grégoire Mialon、Roberto Dessì、Maria Lomeli、Christoforos Nalmpantis、Ram Pasunuru、Roberta Raileanu、Baptiste Rozière、Timo Schick、Jane Dwivedi-Yu、Asli Celikyilmaz 等。2023。增强语言模型：一项调查。*arXiv 预印本 arXiv:2302.07842*。

+   Moiseev 等（2022）Fedor Moiseev、Zhe Dong、Enrique Alfonseca 和 Martin Jaggi。2022。Skill：大语言模型的结构化知识注入。*arXiv 预印本 arXiv:2205.08184*。

+   Mruthyunjaya 等（2023）Vishwas Mruthyunjaya、Pouya Pezeshkpour、Estevam Hruschka 和 Nikita Bhutani。2023。重新思考语言模型作为符号知识图谱。*arXiv 预印本 arXiv:2308.13676*。

+   Núñez-Molina 等（2023）Carlos Núñez-Molina、Pablo Mesejo 和 Juan Fernández-Olivares。2023。关于顺序决策的符号、子符号和混合方法的综述。*arXiv 预印本 arXiv:2304.10590*。

+   Omar 等（2023）Reham Omar、Ishika Dhall、Panos Kalnis 和 Essam Mansour。2023。一个用于知识图谱的通用问答平台。*ACM 数据管理学会会议论文集*，1(1):1–25。

+   Onoe 等（2023）Yasumasa Onoe、Michael JQ Zhang、Shankar Padmanabhan、Greg Durrett 和 Eunsol Choi。2023。语言模型能从描述中学习新实体吗？注入知识的传播挑战。*arXiv 预印本 arXiv:2305.01651*。

+   OpenAI（2023）OpenAI。2023。 [GPT-4 技术报告](http://arxiv.org/abs/2303.08774)。

+   Ouyang 等（2022）Long Ouyang、Jeffrey Wu、Xu Jiang、Diogo Almeida、Carroll Wainwright、Pamela Mishkin、Chong Zhang、Sandhini Agarwal、Katarina Slama、Alex Ray 等。2022。训练语言模型以通过人类反馈遵循指令。*神经信息处理系统进展*，35:27730–27744。

+   Pan 等（2023）Shirui Pan、Linhao Luo、Yufei Wang、Chen Chen、Jiapu Wang 和 Xindong Wu。2023。统一大语言模型和知识图谱：一条路线图。*arXiv 预印本 arXiv:2306.08302*。

+   Peters 等（2019）Matthew E Peters、Mark Neumann、Robert L Logan IV、Roy Schwartz、Vidur Joshi、Sameer Singh 和 Noah A Smith。2019。知识增强的上下文词表示。*arXiv 预印本 arXiv:1909.04164*。

+   Petroni 等（2019）Fabio Petroni、Tim Rocktäschel、Patrick Lewis、Anton Bakhtin、Yuxiang Wu、Alexander H Miller 和 Sebastian Riedel。2019。语言模型作为知识库？*arXiv 预印本 arXiv:1909.01066*。

+   Poerner 等（2019）Nina Poerner、Ulli Waltinger 和 Hinrich Schütze。2019。E-bert：高效而有效的 BERT 实体嵌入。*arXiv 预印本 arXiv:1911.03681*。

+   Prasad 等（2023）Archiki Prasad、Swarnadeep Saha、Xiang Zhou 和 Mohit Bansal。2023。Receval：通过正确性和信息量评估推理链。*arXiv 预印本 arXiv:2304.10703*。

+   Qiao et al. (2022) 邱硕飞, 欧益鑫, 张宁宇, 陈翔, 姚云志, 邓淑敏, 谭传棋, 黄飞, 和 陈华君. 2022. 使用语言模型提示进行推理：综述。*arXiv 预印本 arXiv:2212.09597*。

+   Rae et al. (2021) Jack W Rae, Sebastian Borgeaud, Trevor Cai, Katie Millican, Jordan Hoffmann, Francis Song, John Aslanides, Sarah Henderson, Roman Ring, Susannah Young, 等. 2021. 扩展语言模型：来自训练 Gopher 的方法、分析与见解。*arXiv 预印本 arXiv:2112.11446*。

+   Ram et al. (2023) Ori Ram, Yoav Levine, Itay Dalmedigos, Dor Muhlgay, Amnon Shashua, Kevin Leyton-Brown, 和 Yoav Shoham. 2023. 上下文检索增强语言模型。*arXiv 预印本 arXiv:2302.00083*。

+   Rebedea et al. (2023) Traian Rebedea, Razvan Dinu, Makesh Sreedhar, Christopher Parisien, 和 Jonathan Cohen. 2023. Nemo guardrails: 一个用于可控和安全的 LLM 应用的工具包，具有可编程的框架。*arXiv 预印本 arXiv:2310.10501*。

+   Rosset et al. (2020) Corby Rosset, 陈彦雄, Minh Phan, 夏松, Paul Bennett, 和 Saurabh Tiwary. 2020. 知识感知语言模型预训练。*arXiv 预印本 arXiv:2007.00655*。

+   Runfeng et al. (2023) 谢润峰, 崔向阳, 闫周, 王鑫, 宣展伟, 张凯, 等. 2023. Lkpnr: LLM 和 KG 用于个性化新闻推荐框架。*arXiv 预印本 arXiv:2308.12028*。

+   Seminar et al. (2019) 知识图谱研讨会, Nahor Gebretensae, 和 Heiko Paulheim. 2019. Wikidata: 一个免费的协作知识图谱。

+   Sen et al. (2023) Priyanka Sen, Sandeep Mavadia, 和 Amir Saffari. 2023. 知识图谱增强的语言模型用于复杂问题解答。

+   Shen et al. (2020) 沈涛, 毛毅, 贺鹏程, 龙国栋, Adam Trischler, 和 陈伟柱. 2020. 通过图引导的表示学习在文本中利用结构化知识。*arXiv 预印本 arXiv:2004.14224*。

+   Shi et al. (2023) 石晓, 朱正源, 张泽宇, 和 李承开. 2023. 大规模开放领域知识图谱中的生成幻觉缓解。在 *2023 年自然语言处理经验方法会议论文集*，第 12506–12521 页。

+   Shinn et al. (2023) Noah Shinn, Beck Labash, 和 Ashwin Gopinath. 2023. Reflexion: 一个具有动态记忆和自我反思的自主智能体。*arXiv 预印本 arXiv:2303.11366*。

+   Singh et al. (2023) Chandan Singh, John Morris, Alexander M Rush, Jianfeng Gao, 和 Yuntian Deng. 2023. 树提示：无需微调的高效任务适应。在 *2023 年自然语言处理经验方法会议论文集*，第 6253–6267 页。

+   Singhal (2012) Amit Singhal. 2012. 介绍知识图谱：事物，而非字符串，2012 年 5 月。*网址 http://googleblog.blogspot.ie/2012/05/introducing-knowledgegraph-things-not.html*。

+   Sun et al. (2021a) Yu Sun, Shuohuan Wang, Shikun Feng, Siyu Ding, Chao Pang, Junyuan Shang, Jiaxiang Liu, Xuyi Chen, Yanbin Zhao, Yuxiang Lu, 等人. 2021a. Ernie 3.0：大规模知识增强的语言理解和生成预训练。*arXiv 预印本 arXiv:2107.02137*。

+   Sun et al. (2021b) Yueqing Sun, Qi Shi, Le Qi, 和 Yu Zhang. 2021b. Jointlk：与语言模型和知识图谱联合推理用于常识问答。*arXiv 预印本 arXiv:2112.02732*。

+   Swamy et al. (2021) Vinitra Swamy, Angelika Romanou, 和 Martin Jaggi. 2021. 通过知识图谱提取解释语言模型。*arXiv 预印本 arXiv:2111.08546*。

+   Tian et al. (2020) Hao Tian, Can Gao, Xinyan Xiao, Hao Liu, Bolei He, Hua Wu, Haifeng Wang, 和 Feng Wu. 2020. Skep：情感知识增强的预训练用于情感分析。*arXiv 预印本 arXiv:2005.05635*。

+   Trivedi et al. (2022) Harsh Trivedi, Niranjan Balasubramanian, Tushar Khot, 和 Ashish Sabharwal. 2022. 在知识密集型多步骤问题中交错检索与思维链推理。*arXiv 预印本 arXiv:2212.10509*。

+   Vaswani et al. (2017) Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N Gomez, Łukasz Kaiser, 和 Illia Polosukhin. 2017. 注意力机制是你所需要的一切。*神经信息处理系统进展*, 30。

+   Veseli et al. (2023) Blerta Veseli, Simon Razniewski, Jan-Christoph Kalo, 和 Gerhard Weikum. 2023. 评估 GPT 的知识库补全潜力。*EMNLP 2023 发现*。

+   Wang et al. (2023a) Boxin Wang, Wei Ping, Peng Xu, Lawrence McAfee, Zihan Liu, Mohammad Shoeybi, Yi Dong, Oleksii Kuchaiev, Bo Li, Chaowei Xiao, et al. 2023a. 我们是否应该使用检索预训练自回归语言模型？一项全面研究。*arXiv 预印本 arXiv:2304.06762*。

+   Wang and Shu (2023) Haoran Wang 和 Kai Shu. 2023. 通过知识基础推理与大型语言模型的可解释声明验证。*arXiv 预印本 arXiv:2310.05253*。

+   Wang et al. (2023b) Hongru Wang, Minda Hu, Yang Deng, Rui Wang, Fei Mi, Weichao Wang, Yasheng Wang, Wai-Chung Kwan, Irwin King, 和 Kam-Fai Wong. 2023b. 大型语言模型作为个性化知识基础对话的源规划器。*arXiv 预印本 arXiv:2310.08840*。

+   Wang et al. (2021) Xiaozhi Wang, Tianyu Gao, Zhaocheng Zhu, Zhengyan Zhang, Zhiyuan Liu, Juanzi Li, 和 Jian Tang. 2021. Kepler：一个统一的知识嵌入和预训练语言表示模型。*计算语言学协会会刊*, 9:176–194。

+   Wang et al. (2022) Xuezhi Wang, Jason Wei, Dale Schuurmans, Quoc Le, Ed Chi, Sharan Narang, Aakanksha Chowdhery, 和 Denny Zhou. 2022. 自一致性提高了语言模型的思维链推理。*arXiv 预印本 arXiv:2203.11171*。

+   Wang 等（2023c），Zhaoyang Wang，Shaohan Huang，Yuxuan Liu，Jiahai Wang，Minghui Song，Zihan Zhang，Haizhen Huang，Furu Wei，Weiwei Deng，Feng Sun，等。2023c. *民主化推理能力：大型语言模型个性化学习*。在 *自然语言处理中的 2023 年会议论文集*，第 1948-1966 页。

+   Wei 等（2022a），Jason Wei，Xuezhi Wang，Dale Schuurmans，Maarten Bosma，Fei Xia，Ed Chi，Quoc V Le，Denny Zhou，等。2022a. *连贯思维提示诱导大型语言模型进行推理*。*神经信息处理系统的进展*，35：24824-24837。

+   Wei 等（2021），Xiaokai Wei，Shen Wang，Dejiao Zhang，Parminder Bhatia 和 Andrew Arnold。2021. *知识增强的预训练语言模型：全面调查*。*arXiv 预印本 arXiv：2110.08455*。

+   Wei 等（2023），Yanbin Wei，Qiushi Huang，Yu Zhang 和 James Kwok。2023. *Kicgpt：具有上下文中的知识的大型语言模型用于知识图完成*。在 *计算语言学协会发现：EMNLP 2023*，第 8667-8683 页。

+   Wei 等（2022b），Yinwei Wei，Xiang Wang，Liqiang Nie，Shaoyu Li，Dingxian Wang 和 Tat-Seng Chua。2022b. *基于知识图的推荐因果推断*。*IEEE 知识与数据工程交易*。

+   Wen 等（2023），Yilin Wen，Zifeng Wang 和 Jimeng Sun。2023. *思维导图：知识图提示激发大型语言模型的思维图*。*arXiv 预印本 arXiv：2308.09729*。

+   Wu 等（2023），Yike Wu，Nan Hu，Guilin Qi，Sheng Bi，Jie Ren，Anhuan Xie 和 Wei Song。2023. *重写检索回答：用于知识图问题回答的增强知识图到文本的 llms 框架*。*arXiv 预印本 arXiv：2309.11206*。

+   Xiao 等（2023），Zilin Xiao，Ming Gong，Jie Wu，Xingyao Zhang，Linjun Shou 和 Daxin Jiang。2023. *具有检索器的指示语言模型是强大的实体链接器*。在 *自然语言处理中的 2023 年会议论文集*，第 2267-2282 页。

+   Yang 等（2023），Haoyan Yang，Zhitao Li，Yong Zhang，Jianzong Wang，Ning Cheng，Ming Li 和 Jing Xiao。2023. *Prca：通过可插入的奖励驱动上下文适配器，调整黑盒大型语言模型用于检索式问题回答*。在 *自然语言处理中的 2023 年会议论文集*，第 5364-5375 页。

+   Yao 等（2023），Shunyu Yao，Dian Yu，Jeffrey Zhao，Izhak Shafran，Thomas L Griffiths，Yuan Cao 和 Karthik Narasimhan。2023. *思维之树：大型语言模型的有意识问题解决*。*arXiv 预印本 arXiv：2305.10601*。

+   Yao 等（2022），Shunyu Yao，Jeffrey Zhao，Dian Yu，Nan Du，Izhak Shafran，Karthik Narasimhan 和 Yuan Cao。2022. *React：在语言模型中协同推理和行动*。*arXiv 预印本 arXiv：2210.03629*。

+   Ye 等（2022），Hongbin Ye，Ningyu Zhang，Hui Chen 和 Huajun Chen。2022. *生成式知识图构建：综述*。*arXiv 预印本 arXiv：2210.12714*。

+   Yin et al. (2022) Da Yin, Li Dong, Hao Cheng, Xiaodong Liu, Kai-Wei Chang, Furu Wei, 和 Jianfeng Gao. 2022. 预训练语言模型在知识密集型 NLP 中的应用调查。*arXiv 预印本 arXiv:2202.08772*。

+   Yin et al. (2023a) Xunjian Yin, Baizhou Huang, 和 Xiaojun Wan. 2023a. Alcuna: 大语言模型与新知识的结合。在 *2023 年自然语言处理实证方法会议论文集*，第 1397–1414 页。

+   Yin et al. (2023b) Zhangyue Yin, Qiushi Sun, Cheng Chang, Qipeng Guo, Junqi Dai, Xuan-Jing Huang, 和 Xipeng Qiu. 2023b. 思想交流：通过跨模型通信增强大语言模型的能力。在 *2023 年自然语言处理实证方法会议论文集*，第 15135–15153 页。

+   Youn and Tagkopoulos (2022) Jason Youn 和 Ilias Tagkopoulos. 2022. Kglm: 在语言模型中整合知识图谱结构用于链接预测。*arXiv 预印本 arXiv:2211.02744*。

+   Yu et al. (2023) Mengxia Yu, Zhihan Zhang, Wenhao Yu, 和 Meng Jiang. 2023. 预训练语言模型用于比较推理。*arXiv 预印本 arXiv:2305.14457*。

+   Yu et al. (2022) Wenhao Yu, Chenguang Zhu, Lianhui Qin, Zhihan Zhang, Tong Zhao, 和 Meng Jiang. 2022. 利用知识图谱专家的混合方法多样化常识推理中的内容生成。*arXiv 预印本 arXiv:2203.07285*。

+   (118) Denghui Zhang, Zixuan Yuan, Yanchi Liu, Fuzhen Zhuang, 和 Hui Xiong. E-bert: 将 bert 适应于电子商务，通过自适应混合掩码和邻近产品重建。

+   Zhang et al. (2023a) Muru Zhang, Ofir Press, William Merrill, Alisa Liu, 和 Noah A Smith. 2023a. 语言模型幻觉如何滚雪球。*arXiv 预印本 arXiv:2305.13534*。

+   Zhang et al. (2023b) Zhebin Zhang, Xinyu Zhang, Yuanhang Ren, Saijiang Shi, Meng Han, Yongkang Wu, Ruofei Lai, 和 Zhao Cao. 2023b. Iag: 用于回答推理问题的归纳增强生成框架。在 *2023 年自然语言处理实证方法会议论文集*，第 1–14 页。

+   Zhang et al. (2019) Zhengyan Zhang, Xu Han, Zhiyuan Liu, Xin Jiang, Maosong Sun, 和 Qun Liu. 2019. Ernie: 通过信息实体增强语言表示。*arXiv 预印本 arXiv:1905.07129*。

+   Zhang et al. (2023c) Zihan Zhang, Meng Fang, Ling Chen, Mohammad Reza Namazi Rad, 和 Jun Wang. 2023c. 大语言模型如何捕捉不断变化的世界知识？对近期进展的综述。在 *2023 年自然语言处理实证方法会议论文集*，第 8289–8311 页。

+   Zheng et al. (2023) Shen Zheng, Jie Huang, and Kevin Chen-Chuan Chang. 2023. 为什么 chatgpt 在忠实回答问题时会有所不足？*arXiv 预印本 arXiv:2304.10513*。

+   Zhou et al. (2022) Yanqi Zhou, Tao Lei, Hanxiao Liu, Nan Du, Yanping Huang, Vincent Zhao, Andrew M Dai, Quoc V Le, James Laudon, 等. 2022. 专家选择路由的混合专家。*神经信息处理系统进展*，35:7103–7114。

生成于 2024 年 3 月 16 日 星期六 03:19:03，使用了 [LATExml![[LOGO]](img/70e087b9e50c3aa663763c3075b0d6c5.png)](http://dlmf.nist.gov/LaTeXML/)
