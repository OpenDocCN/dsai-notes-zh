<!--yml

类别：未分类

日期：2024-09-03 17:30:03

-->

# 知识冲突与大型语言模型（LLMs）：一项调研

> 来源：[`arxiv.org/html/2403.08319`](https://arxiv.org/html/2403.08319)

1.  [1 引言](https://arxiv.org/html/2403.08319v2#S1 "在《知识冲突与大型语言模型（LLMs）：一项调研》中")

1.  [2 上下文-记忆冲突](https://arxiv.org/html/2403.08319v2#S2 "在《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [2.1 原因](https://arxiv.org/html/2403.08319v2#S2.SS1 "在 2 上下文-记忆冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [2.2 模型行为分析](https://arxiv.org/html/2403.08319v2#S2.SS2 "在 2 上下文-记忆冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [2.3 解决方案](https://arxiv.org/html/2403.08319v2#S2.SS3 "在 2 上下文-记忆冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

1.  [3 上下文间冲突](https://arxiv.org/html/2403.08319v2#S3 "在《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [3.1 原因](https://arxiv.org/html/2403.08319v2#S3.SS1 "在 3 上下文间冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [3.2 模型行为分析](https://arxiv.org/html/2403.08319v2#S3.SS2 "在 3 上下文间冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [3.3 解决方案](https://arxiv.org/html/2403.08319v2#S3.SS3 "在 3 上下文间冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

1.  [4 内存冲突](https://arxiv.org/html/2403.08319v2#S4 "在《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [4.1 原因](https://arxiv.org/html/2403.08319v2#S4.SS1 "在 4 内存冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [4.2 模型行为分析](https://arxiv.org/html/2403.08319v2#S4.SS2 "在 4 内存冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [4.3 解决方案](https://arxiv.org/html/2403.08319v2#S4.SS3 "在 4 内存冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

        1.  [4.3.1 提升一致性](https://arxiv.org/html/2403.08319v2#S4.SS3.SSS1 "在 4.3 解决方案 ‣ 4 内存冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

        1.  [4.3.2 提升事实性](https://arxiv.org/html/2403.08319v2#S4.SS3.SSS2 "在 4.3 解决方案 ‣ 4 内存冲突 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

1.  [5 挑战与未来方向](https://arxiv.org/html/2403.08319v2#S5 "在《知识冲突与大型语言模型（LLMs）：一项调研》中")

1.  [6 结论](https://arxiv.org/html/2403.08319v2#S6 "在《知识冲突与大型语言模型（LLMs）：一项调研》中")

1.  [A 附录](https://arxiv.org/html/2403.08319v2#A1 "在《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [A.1 定量分析与比较](https://arxiv.org/html/2403.08319v2#A1.SS1 "在附录 A 附录 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [A.2 知识冲突影响的定量结果](https://arxiv.org/html/2403.08319v2#A1.SS2 "在附录 A 附录 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

    1.  [A.3 缓解策略有效性的定量结果](https://arxiv.org/html/2403.08319v2#A1.SS3 "在附录 A 附录 ‣ 《知识冲突与大型语言模型（LLMs）：一项调研》中")

# ![[未标注的图片]](img/5ef62bde5736f5f34fe024e9df6e0e39.png) LLMs 的知识冲突：一项调查

徐荣武^(1†∗)、祁泽汉^(1†∗)、郭志江^(2†),

王存祥³、王洪如⁴、张悦³、徐伟¹

¹清华大学 ²剑桥大学

³西湖大学 ⁴香港中文大学 {xrw22, qzh23}@mails.tsinghua.edu.cn ^† 主要作者， ^∗ 等贡献

###### 摘要

本调查提供了对大型语言模型（LLMs）知识冲突的深入分析，突出它们在融合上下文和参数知识时遇到的复杂挑战。我们关注三种类型的知识冲突：上下文记忆冲突、上下文之间的冲突以及记忆内部冲突。这些冲突可能显著影响 LLMs 的可靠性和性能，特别是在噪音和虚假信息普遍存在的实际应用中。通过对这些冲突进行分类、探讨原因、考察 LLMs 在此类冲突下的行为以及回顾现有解决方案，本调查旨在揭示提升 LLMs 鲁棒性的策略，从而成为推动该领域研究的宝贵资源。

[![[未标注的图片]](img/fefc7992c4c074fad120a480db18175e.png)](https://github.com/pillowsofwind/Knowledge-Conflicts-Survey)

[`github.com/pillowsofwind/Knowledge-Conflicts-Survey`](https://github.com/pillowsofwind/Knowledge-Conflicts-Survey)

## 1 引言

大型语言模型（LLMs; Brown et al. [2020](https://arxiv.org/html/2403.08319v2#bib.bib14); Touvron et al. [2023](https://arxiv.org/html/2403.08319v2#bib.bib171); OpenAI [2024](https://arxiv.org/html/2403.08319v2#bib.bib133)）因其封装了大量世界知识而闻名，Roberts et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib150)); Hu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib65)) 称之为*参数化知识*。这些模型在包括问答 Petroni et al. ([2019](https://arxiv.org/html/2403.08319v2#bib.bib140))、事实核查 Gao et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib49))、对话系统 Wang et al. ([2023e](https://arxiv.org/html/2403.08319v2#bib.bib183))、知识生成 Chen et al. ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib24)) 等知识密集型任务中表现出色。同时，LLMs 在部署后继续与外部*上下文知识*进行交互 Pan et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib136))，包括用户提示 Liu et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib109))、互动对话 Zhang et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib210)); Wang et al. ([2024a](https://arxiv.org/html/2403.08319v2#bib.bib182))，或从网络上检索的文档 Lewis et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib97)); Shi et al. ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib158))，以及工具 Schick et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib152)); Zhuang et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib221))。

![参见说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 1：LLM 可能会遇到三种不同类型的知识冲突，这些冲突源于知识来源——无论是上下文的（*I. 上下文*，黄色聊天框）还是固有于 LLM 参数的（*II. 记忆*，蓝色聊天框）。当面对涉及复杂冲突的用户问题（紫色聊天框）时，LLM 需要解决这些差异以提供准确的回答。

![参见说明](img/9df2a699c179d7d103da938773675ba1.png)

图 2：我们将知识冲突不仅视为一个独立现象，还视为连接各种因果触发因素（原因）与 LLM 行为的枢纽。虽然现有文献主要关注*II. 分析*，但我们的调查涉及系统地观察这些冲突，提供了关于其出现和对 LLM 行为影响的见解，以及期望的行为和相关解决方案。

将上下文知识整合到大型语言模型（LLMs）中，使其能够跟上时事动态 Kasai 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib85)) 并生成更准确的回应 Shuster 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib161))，但这也可能由于丰富的知识来源而引发冲突。上下文与模型的参数知识之间的差异被称为*知识冲突* Chen 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib21))；Xie 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195))。在本文中，我们将知识冲突分为三种不同的类型，如[图 1](https://arxiv.org/html/2403.08319v2#S1.F1 "Figure 1 ‣ 1 Introduction ‣ Knowledge Conflicts for LLMs: A Survey")所示的那样。正如[图 1](https://arxiv.org/html/2403.08319v2#S1.F1 "Figure 1 ‣ 1 Introduction ‣ Knowledge Conflicts for LLMs: A Survey")中的示例，当利用 LLM 回应用户问题时，用户可能会提供额外的提示，而 LLM 也会利用搜索引擎从网络上获取相关文档以增强其知识 Lewis 等人 ([2020](https://arxiv.org/html/2403.08319v2#bib.bib97))。用户提示、对话历史和检索到的文档的组合构成了上下文知识 (*context*)。上下文知识可能会与 LLM 参数中所包含的参数知识 (*memory*) 发生冲突 (Longpre 等人，[2021](https://arxiv.org/html/2403.08319v2#bib.bib111)；Xie 等人，[2023](https://arxiv.org/html/2403.08319v2#bib.bib195))，这种现象我们称之为上下文-记忆冲突（CM，[§ 2](https://arxiv.org/html/2403.08319v2#S2 "2 Context-Memory Conflict ‣ Knowledge Conflicts for LLMs: A Survey")）。在现实场景中，外部文档可能充斥着噪音 Zhang 和 Choi ([2021](https://arxiv.org/html/2403.08319v2#bib.bib208)) 或甚至是故意编造的虚假信息 Du 等人 ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib39))；Pan 等人 ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib135))，这使得其处理和准确回应的能力变得复杂 Chen 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib21))。我们将不同上下文知识之间的冲突称为上下文间冲突（IC，[§ 3](https://arxiv.org/html/2403.08319v2#S3 "3 Inter-Context Conflict ‣ Knowledge Conflicts for LLMs: A Survey")）。为了减少回应中的不确定性，用户可能会以不同的形式提出问题。因此，LLM 的参数知识可能会对这些不同措辞的问题给出不同的回答。这种差异可以归因于 LLM 参数中嵌入的冲突知识，这些知识源自复杂且多样的预训练数据集中的不一致性 Huang 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib67))。这引发了我们称之为记忆内冲突（IM，[§ 4](https://arxiv.org/html/2403.08319v2#S4 "4 Intra-Memory Conflict ‣ Knowledge Conflicts for LLMs: A Survey")）的现象。

知识冲突最初源于开放域问答研究。这个概念在 Longpre 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib111)) 的研究中引起了关注，他们专注于参数知识和外部文献之间的实体基础冲突。同时，多个文献之间的差异也随之被 Chen 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib21)) 进行了审视。随着 LLMs 的最新出现，知识冲突引起了显著关注。例如，近期研究发现 LLMs 既坚持参数知识，又容易受到上下文影响 Xie 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195))，当这些外部知识事实不正确时，这可能会导致问题 Pan 等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib137))。鉴于对 LLMs 的可信度 (Du 等人，[2022b](https://arxiv.org/html/2403.08319v2#bib.bib39))、实时准确性 (Kasai 等人，[2022](https://arxiv.org/html/2403.08319v2#bib.bib85)) 和鲁棒性 (Ying 等人，[2023](https://arxiv.org/html/2403.08319v2#bib.bib202)) 的影响，深入理解和解决知识冲突是至关重要的 (Xie 等人，[2023](https://arxiv.org/html/2403.08319v2#bib.bib195)；Wang 等人，[2023h](https://arxiv.org/html/2403.08319v2#bib.bib187))。

截至撰写时，据我们所知，尚无系统性的调查专门研究知识冲突。现有的综述文献如 Zhang 等人 ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib211))；Wang 等人 ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib178))；Feng 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib45)) 在其更广泛的背景中提及了知识冲突。虽然 Feng 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib45)) 对知识冲突进行了更系统的检查，将其分类为外部冲突和内部冲突。然而，他们的综述仅提供了相关工作的简要概述，并主要关注特定场景。为了填补这一空白，我们旨在提供一份全面的综述，涵盖知识冲突的分类、原因及行为分析，以及解决各种知识冲突的方案。

我们将*知识冲突的生命周期*概念化为既是导致各种行为的*原因*，也是由于知识的复杂性而产生的*结果*，如[图 2](https://arxiv.org/html/2403.08319v2#S1.F2 "Figure 2 ‣ 1 Introduction ‣ Knowledge Conflicts for LLMs: A Survey")所示。知识冲突在原因和模型行为之间起着关键的中介作用。例如，它们显著导致模型生成事实错误的信息，即幻觉 Ji et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib74))； Zhang et al. ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib211))。我们的研究类似于弗洛伊德的精神分析，强调了理解这些冲突来源的重要性。虽然现有分析 Chen et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib21))； Xie et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195))； Wang et al. ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)) 倾向于人为构造这些冲突，但我们认为这些分析并未充分解决问题的互联性。

{森林}

分叉边缘，树=生长=东，反转=true，锚点=基础西，父锚点=东，子锚点=西，基础=左，字体=，矩形，绘制=隐藏绘制，圆角，左对齐，最小宽度=0.1em，边缘+=深灰色，线宽=0.8pt，s sep=2pt，内部 xsep=2pt，内部 ysep=2pt，ver/.style=旋转=90，子锚点=北，父锚点=南，锚点=中心，，其中 level=1text width=3.5em，font=，，其中 level=2text width=1.8em，font=，，其中 level=3text width=5.2em，font=，，其中 level=4text width=4em，font=，，其中 level=5text width=8em，font=，， [ 知识冲突，绘制=灰色，颜色=灰色!100，填充=灰色!15，粗线，文本=黑色，ver [ 上下文-记忆

冲突 ([§ 2](https://arxiv.org/html/2403.08319v2#S2 "2 Context-Memory Conflict ‣ Knowledge Conflicts for LLMs: A Survey")) ，颜色=lightcoral!100，填充=lightcoral!15，粗线，文本=黑色 [ 原因

([§ 2.1](https://arxiv.org/html/2403.08319v2#S2.SS1 "2.1 Causes ‣ 2 Context-Memory Conflict ‣ Knowledge Conflicts for LLMs: A Survey")) ，颜色=lightcoral!100，填充=lightcoral!15，粗线，文本=黑色 [ 时间错位 ，颜色=lightcoral!100，填充=lightcoral!15，粗线，文本=黑色 [ Lazaridou et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib93))，Luu et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib112))，Jang et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib70))，

Jang et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib69))，Liska et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib108))，Dhingra et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib35))，

片井等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib85))、Margatina 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib116))、Cheang 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib18))，叶子，文本宽度 = 12em，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色] ] [ 错误信息污染，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色 [ 杜等人 ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib39))、潘等人 ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib135))、潘等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib137))，

徐等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197))、Weller 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib191))，叶子，文本宽度 = 12em，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色] ] ] [ 分析

([§ 2.2](https://arxiv.org/html/2403.08319v2#S2.SS2 "2.2 模型行为分析 ‣ 2 上下文-记忆冲突 ‣ LLM 的知识冲突：调查"))，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色 [ 开放域 QA，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色 [ Longpre 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib111))、陈等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib21))、谭等人 ([2024](https://arxiv.org/html/2403.08319v2#bib.bib167))，叶子，文本宽度 = 12em，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色] ] [ 一般，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色 [ 谢等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195))、王等人 ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187))、应等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib202))，

钱等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib144))、徐等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197))、金等人 ([2024a](https://arxiv.org/html/2403.08319v2#bib.bib76))，叶子，文本宽度 = 12em，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色] ] ] [ 解决方案

([§ 2.3](https://arxiv.org/html/2403.08319v2#S2.SS3 "2.3 解决方案 ‣ 2 上下文-记忆冲突 ‣ LLM 的知识冲突：调查"))，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色 [ 忠于上下文，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色 [ 微调，颜色=lightcoral!100，填充=lightcoral!15，粗体，文本=黑色 [ KAFT (Li 等人，[2022a](https://arxiv.org/html/2403.08319v2#bib.bib98)) ![参见说明](img/bb54ce29c4a84b827d724bf024185d28.png)，

TrueTeacher (Gekhman 等人，[2023](https://arxiv.org/html/2403.08319v2#bib.bib51)) ![参见说明](img/bb54ce29c4a84b827d724bf024185d28.png)，

K-DIAL (Xue et al., [2023](https://arxiv.org/html/2403.08319v2#bib.bib199)) ![参见说明](img/bb54ce29c4a84b827d724bf024185d28.png)![参见说明](img/2d0113f09fd841f1064a3b776c1b6dfb.png) , leaf, color=lightcoral!100, fill=lightcoral!15, thick, text=black ] ] [ 提示 , color=lightcoral!100, fill=lightcoral!15, thick, text=black [ OPIN (Zhou et al., [2023d](https://arxiv.org/html/2403.08319v2#bib.bib220)) ![参见说明](img/bb54ce29c4a84b827d724bf024185d28.png) , leaf, color=lightcoral!100, fill=lightcoral!15, thick, text=black ] ] [ 解码 , color=lightcoral!100, fill=lightcoral!15, thick, text=black [ CAD (Shi et al., [2023a](https://arxiv.org/html/2403.08319v2#bib.bib156)) ![参见说明](img/2d0113f09fd841f1064a3b776c1b6dfb.png),

, leaf, color=lightcoral!100, fill=lightcoral!15, thick, text=black ] ] [ 知识插件 , color=lightcoral!100, fill=lightcoral!15, thick, text=black [ CuQA (Lee et al., [2022a](https://arxiv.org/html/2403.08319v2#bib.bib94)) ![参见说明](img/bb54ce29c4a84b827d724bf024185d28.png) , leaf, color=lightcoral!100, fill=lightcoral!15, thick, text=black ] ] [ 预训练 , color=lightcoral!100, fill=lightcoral!15, thick, text=black [ ICLM (Shi et al., [2023b](https://arxiv.org/html/2403.08319v2#bib.bib157)) ![参见说明](img/bb54ce29c4a84b827d724bf024185d28.png) , leaf, color=lightcoral!100, fill=lightcoral!15, thick, text=black ] ] [ 预测事实有效性 , color=lightcoral!100, fill=lightcoral!15, thick, text=black [ Zhang 和 Choi ([2023](https://arxiv.org/html/2403.08319v2#bib.bib209)) ![参见说明](img/2d0113f09fd841f1064a3b776c1b6dfb.png) , leaf, color=lightcoral!100, fill=lightcoral!15, thick, text=black ] ] ] [ 辨别虚假信息

(忠于记忆)，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色 [ 提示，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色 [ Pan et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib137)) ![Refer to caption](img/bb54ce29c4a84b827d724bf024185d28.png)，Xu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197)) ![Refer to caption](img/2d0113f09fd841f1064a3b776c1b6dfb.png)，叶子，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色] ] [ 查询增强，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色 [ Weller et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib191)) ![Refer to caption](img/2d0113f09fd841f1064a3b776c1b6dfb.png)，叶子，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色] ] [ 训练鉴别器，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色 [ Hong et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib63)) ![Refer to caption](img/bb54ce29c4a84b827d724bf024185d28.png)，叶子，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色] ] ] [ 解开来源，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色 [ DisentQA (Neeman et al., [2022](https://arxiv.org/html/2403.08319v2#bib.bib128)) ![Refer to caption](img/bb54ce29c4a84b827d724bf024185d28.png)，Wang et al. ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)) ![Refer to caption](img/2d0113f09fd841f1064a3b776c1b6dfb.png)，叶子，文本宽度=12em，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色] ] [ 提高事实准确性，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色 [ COMBO (Zhang et al., [2023e](https://arxiv.org/html/2403.08319v2#bib.bib212)) ![Refer to caption](img/bb54ce29c4a84b827d724bf024185d28.png)![Refer to caption](img/2d0113f09fd841f1064a3b776c1b6dfb.png)，CD${}^{\text{2}}$ (Jin et al., [2024a](https://arxiv.org/html/2403.08319v2#bib.bib76)) ![Refer to caption](img/2d0113f09fd841f1064a3b776c1b6dfb.png)，叶子，文本宽度=12em，颜色=lightcoral!100，填充=lightcoral!15，厚，文字=黑色] ] ] ] [ 跨上下文

冲突 ([§ 3](https://arxiv.org/html/2403.08319v2#S3 "3 Inter-Context Conflict ‣ Knowledge Conflicts for LLMs: A Survey"))，颜色=lightyellow!100，填充=lightyellow!15，厚，文字=黑色 [ 原因

([§ 3.1](https://arxiv.org/html/2403.08319v2#S3.SS1 "3.1 Causes ‣ 3 Inter-Context Conflict ‣ Knowledge Conflicts for LLMs: A Survey"))，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色 [ 错误信息，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色 [ Chen 和 Shu ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib20))、Vergho 等 ([2024](https://arxiv.org/html/2403.08319v2#bib.bib174))、Chen 等 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib23))，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色，文本宽度=12em ] ] [ 过时信息，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色 [ Zhang 和 Choi ([2021](https://arxiv.org/html/2403.08319v2#bib.bib208))、Kasai 等 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib85))，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色，文本宽度=12em ] ] ] [ 分析

([§ 3.2](https://arxiv.org/html/2403.08319v2#S3.SS2 "3.2 Analysis of Model Behaviors ‣ 3 Inter-Context Conflict ‣ Knowledge Conflicts for LLMs: A Survey"))，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色，[ 性能影响，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色，[ Chen 等 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib21))、Xie 等 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195))、Pan 等 ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib135))，

Zhang 和 Choi ([2021](https://arxiv.org/html/2403.08319v2#bib.bib208))、Du 等 ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib39))、Jin 等 ([2024a](https://arxiv.org/html/2403.08319v2#bib.bib76))，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色，文本宽度=12em ] ] [ 检测能力，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色，[ Li 等 ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib99))、Zheng 等 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib215))、Wan 等 ([2024](https://arxiv.org/html/2403.08319v2#bib.bib176))，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色，文本宽度=12em ] ] ] [ 解决方案

([§ 3.3](https://arxiv.org/html/2403.08319v2#S3.SS3 "3.3 Solutions ‣ 3 Inter-Context Conflict ‣ Knowledge Conflicts for LLMs: A Survey"))，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色 [ 消除冲突，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色 [ 专门模型，颜色=lightyellow!100，填充=lightyellow!15，粗体，文本=黑色 [ PCNN (Hsu 等，[2021](https://arxiv.org/html/2403.08319v2#bib.bib64)) ![参考说明](img/bb54ce29c4a84b827d724bf024185d28.png)，Pielka 等 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib141)) ![参考说明](img/bb54ce29c4a84b827d724bf024185d28.png)，

Wu 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib193)) ![参考说明](img/bb54ce29c4a84b827d724bf024185d28.png)，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色，文字宽度=8.8em ] ] [ 通用模型，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色 [ Leite 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib96)) ![参考说明](img/bb54ce29c4a84b827d724bf024185d28.png)，Cheung 和 Lam ([2023](https://arxiv.org/html/2403.08319v2#bib.bib27)) ![参考说明](img/bb54ce29c4a84b827d724bf024185d28.png)，

Chern 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib26)) ![参考说明](img/bb54ce29c4a84b827d724bf024185d28.png)，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色，文字宽度=8.8em ] ] ] [ 提升鲁棒性，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色 [ 训练方法，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色 [ Hong 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib63)) ![参考说明](img/bb54ce29c4a84b827d724bf024185d28.png)，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色，文字宽度=8.8em ] ] [ 查询增强，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色 [ CAR (Weller 等人，[2022](https://arxiv.org/html/2403.08319v2#bib.bib191)) ![参考说明](img/2d0113f09fd841f1064a3b776c1b6dfb.png)，叶子，颜色=lightyellow!100，填充=lightyellow!15，粗线条，文字=黑色，文字宽度=8.8em ] ] ] ] ] [ 内存内

冲突 ([§ 4](https://arxiv.org/html/2403.08319v2#S4 "4 内存内冲突 ‣ 大型语言模型的知识冲突：调查"))，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色 [ 原因

([§ 4.1](https://arxiv.org/html/2403.08319v2#S4.SS1 "4.1 原因 ‣ 4 内存内冲突 ‣ 大型语言模型的知识冲突：调查"))，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色 [ 训练语料库中的偏差，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色 [ Wang 等人 ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib181))，Xu 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib196))，叶子，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色，文字宽度=12em ] ] [ 解码策略，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色 [ Lee 等人 ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib95))，Huang 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib67))，叶子，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色，文字宽度=12em ] ] [ 知识编辑，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色 [ Yao 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib200))，Li 等人 ([2023f](https://arxiv.org/html/2403.08319v2#bib.bib106))，叶子，颜色=cyan!100，填充=cyan!15，粗线条，文字=黑色，文字宽度=12em ] ] ] [ 分析

([§ 4.2](https://arxiv.org/html/2403.08319v2#S4.SS2 "4.2 模型行为分析 ‣ 4 内存冲突 ‣ 知识冲突：对大型语言模型的调查")) ，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ 自我不一致，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ Dong 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib37)), Zhao 等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib214)), Manakul 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib115)),

Dhuliawala 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib36)), Zhang 等人 ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib207)), Mündler 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib126)),

Agrawal 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib2)), Hase 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib58)) ，叶子，颜色=青色!100，填充=青色!15，粗线条，文本=黑色，文本宽度=12em ] ] [ 潜在表示

知识，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ Chuang 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib28)), Li 等人 ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib101)) ，叶子，颜色=青色!100，填充=青色!15，粗线条，文本=黑色，文本宽度=12em ] ] [ 跨语言不一致，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ Wang 等人 ([2023f](https://arxiv.org/html/2403.08319v2#bib.bib185)), Qi 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib143)) ，叶子，颜色=青色!100，填充=青色!15，粗线条，文本=黑色，文本宽度=12em ] ] ] [ 解决方案

([§ 4.3](https://arxiv.org/html/2403.08319v2#S4.SS3 "4.3 解决方案 ‣ 4 内存冲突 ‣ 知识冲突：对大型语言模型的调查")) ，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ 提高一致性，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ 微调，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ Elazar 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib42)) ![参见标题](img/bb54ce29c4a84b827d724bf024185d28.png)，Li 等人 ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib104)) ![参见标题](img/bb54ce29c4a84b827d724bf024185d28.png)，叶子，颜色=青色!100，填充=青色!15，粗线条，文本=黑色，文本宽度=8em ] ] [ 插件，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ CRM (Jang 和 Lukasiewicz, [2023](https://arxiv.org/html/2403.08319v2#bib.bib71)) ![参见标题](img/bb54ce29c4a84b827d724bf024185d28.png) ，叶子，颜色=青色!100，填充=青色!15，粗线条，文本=黑色，文本宽度=8em ] ] [ 输出集成，颜色=青色!100，填充=青色!15，粗线条，文本=黑色 [ ConCoRD (Mitchell 等人, [2022](https://arxiv.org/html/2403.08319v2#bib.bib125)) ![参见标题](img/2d0113f09fd841f1064a3b776c1b6dfb.png)，

Zhao 等 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib214)) ![参考图注](img/2d0113f09fd841f1064a3b776c1b6dfb.png), leaf, color=cyan!100, fill=cyan!15, thick, text=black, text width=8em ] ] ] [ 改善真实性, color=cyan!100, fill=cyan!15, thick, text=black [ ITI (Li 等, [2023c](https://arxiv.org/html/2403.08319v2#bib.bib101)) ![参考图注](img/2d0113f09fd841f1064a3b776c1b6dfb.png), DoLa (Chuang 等, [2023](https://arxiv.org/html/2403.08319v2#bib.bib28)) ![参考图注](img/2d0113f09fd841f1064a3b776c1b6dfb.png), leaf, color=cyan!100, fill=cyan!15, thick, text=black, text width=12em ] ] ] ] ]

图 3：知识冲突的分类。我们主要列出 LLM 时代的工作。![参考图注](img/bb54ce29c4a84b827d724bf024185d28.png) 表示事前解决方案，![参考图注](img/2d0113f09fd841f1064a3b776c1b6dfb.png) 表示事后解决方案。

超越审查和分析原因及行为，我们深入探讨以提供系统的解决方案，旨在减少知识冲突的不良后果，即鼓励模型表现出*符合特定目标的期望行为*（请注意，这些*目标可能有所不同*，具体取决于特定情境）。根据潜在冲突的时间相对性，策略分为两类：*事前*和*事后*策略。它们的关键区别在于调整是*在*潜在冲突发生之前还是*之后*进行¹¹另一种解释是事前策略是主动的，而事后策略是反应性的。知识冲突的分类见 [图 3](https://arxiv.org/html/2403.08319v2#S1.F3 "图 3 ‣ 1 介绍 ‣ LLM 的知识冲突：一项调查")。我们依次讨论三种知识冲突，详细说明每种冲突的原因、模型行为的分析以及根据其各自目标组织的可用解决方案。相关数据集见 [表 1](https://arxiv.org/html/2403.08319v2#S1.T1 "表 1 ‣ 1 介绍 ‣ LLM 的知识冲突：一项调查")。

| 数据集 | 方法¹ | 基础² | 大小 | 冲突 |
| --- | --- | --- | --- | --- |
| Xie 等 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195)) | 生成 | PopQA ([2023](https://arxiv.org/html/2403.08319v2#bib.bib114)), StrategyQA (Geva 等, [2021](https://arxiv.org/html/2403.08319v2#bib.bib52))) | 20,091 | CM³ |
| KC ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)) | Sub | N/A (LLM 生成) | 9,803 | CM |
| KRE ([2023](https://arxiv.org/html/2403.08319v2#bib.bib202)) | 生成 | MuSiQue ([2022](https://arxiv.org/html/2403.08319v2#bib.bib172)), SQuAD2.0 ([2018](https://arxiv.org/html/2403.08319v2#bib.bib148)), ECQA ([2021](https://arxiv.org/html/2403.08319v2#bib.bib1)), e-CARE ([2022a](https://arxiv.org/html/2403.08319v2#bib.bib38)) | 11,684 | CM |
| Farm ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197)) | 生成 | BoolQ ([2019](https://arxiv.org/html/2403.08319v2#bib.bib30)), NQ ([2019](https://arxiv.org/html/2403.08319v2#bib.bib90)), TruthfulQA ([2022](https://arxiv.org/html/2403.08319v2#bib.bib107)) | 1,952 | 上下文-记忆 |
| Tan et al. ([2024](https://arxiv.org/html/2403.08319v2#bib.bib167)) | 生成 | NQ ([2019](https://arxiv.org/html/2403.08319v2#bib.bib90)), TriviaQA ([2017](https://arxiv.org/html/2403.08319v2#bib.bib78)) | 14,923 | 上下文-记忆 |
| WikiContradiction ([2021](https://arxiv.org/html/2403.08319v2#bib.bib64)) | 人工 | Wikipedia | 2,210 | 跨上下文 |
| ClaimDiff ([2022](https://arxiv.org/html/2403.08319v2#bib.bib87)) | 人工 | 不适用 | 2,941 | 内部记忆 |
| Pan et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib135)) | 生成, 替换 | SQuAD v1.1 ([2016](https://arxiv.org/html/2403.08319v2#bib.bib149)) | 52,189 | 内部记忆 |
| ContraDoc ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib99)) | 生成 | CNN-DailyMail ([2015](https://arxiv.org/html/2403.08319v2#bib.bib60)), NarrativeQA ([2018](https://arxiv.org/html/2403.08319v2#bib.bib88)), WikiText ([2017](https://arxiv.org/html/2403.08319v2#bib.bib122)) | 449 | 内部记忆 |
| ConflictingQA ([2024](https://arxiv.org/html/2403.08319v2#bib.bib176)) | 生成 | 不适用 | 238 | 内部记忆 |
| ParaRel ([2021](https://arxiv.org/html/2403.08319v2#bib.bib42)) | 人工 | T-REx ([2018](https://arxiv.org/html/2403.08319v2#bib.bib43)) | 328 | 内部记忆 |

+   •

    1\. 方法指的是冲突的构造方式，包括实体级别的替换（Sub）、使用 LLM 的生成方法（Gen）和人工标注（Hum）。

+   •

    2\. 基础数据集指的是用作生成冲突基础的数据集（如果适用）。

+   •

    3\. ![[无标题图像]](img/ebb17c4cc7cc9df00a33d741a1bf8410.png) 使用 CM 数据集时，冲突源于特定模型的参数化知识，这些知识可能在模型之间有所不同。因此，选择一个与测试模型知识对齐的数据集子集至关重要。

表 1：评估 LLM 遇到知识冲突时行为的数据集。CM: 上下文-记忆冲突，IC: 跨上下文冲突，IM: 内部记忆冲突。

## 2 上下文-记忆冲突

上下文-记忆冲突被认为是三种冲突类型中研究得最为广泛的一种。LLMs 的特点是固定的参数化知识，这是由于大量的相关过程 Sharir et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib154)); Hoffmann et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib61)); Smith ([2023](https://arxiv.org/html/2403.08319v2#bib.bib164))。这种静态的参数化知识与外部信息的动态特性形成鲜明对比，后者迅速演变 De Cao et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib32)); Kasai et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib85))。

### 2.1 原因

背景记忆冲突的核心在于背景知识与参数知识之间的差异。我们考虑了两个主要原因：时间不匹配 Lazaridou 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib93)）；Luu 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib112)）；Dhingra 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib35)）和虚假信息污染 Du 等人（[2022b](https://arxiv.org/html/2403.08319v2#bib.bib39)）；Pan 等人（[2023a](https://arxiv.org/html/2403.08319v2#bib.bib135)）。

时间不匹配。时间不匹配*自然地*出现在基于过去收集的数据训练的模型中，因为这些模型可能无法准确反映当代或未来的现实（即，部署后的背景知识）Luu 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib112)）；Lazaridou 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib93)）；Liska 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib108)）。这种不匹配可能会随着时间的推移降低模型的性能和相关性，因为它可能无法捕捉新的趋势、语言使用的变化、文化变迁或知识更新。研究人员指出，时间不匹配降低了模型在各种 NLP 任务上的表现 Luu 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib112)）；Zhang 和 Choi（[2021](https://arxiv.org/html/2403.08319v2#bib.bib208)）；Dhingra 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib35)）；Kasai 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib85)）；Cheang 等人（[2023](https://arxiv.org/html/2403.08319v2#bib.bib18)）。此外，随着预训练范式的使用和扩展模型的成本增加，时间不匹配的问题预计会加剧（Kaplan 等人，[2020](https://arxiv.org/html/2403.08319v2#bib.bib83)）。

先前的工作试图通过关注三种策略来解决时间不对齐的问题：*知识编辑（KE）* 旨在直接更新现有预训练模型的参数知识（Sinitsin et al., [2020](https://arxiv.org/html/2403.08319v2#bib.bib163); De Cao et al., [2021](https://arxiv.org/html/2403.08319v2#bib.bib32); Mitchell et al., [2021](https://arxiv.org/html/2403.08319v2#bib.bib124); Onoe et al., [2023](https://arxiv.org/html/2403.08319v2#bib.bib131)）。*检索增强生成（RAG）* 利用检索模块从外部来源（如数据库、网络）中获取相关文档，以补充模型的知识而不改变其参数（Karpukhin et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib84)); Guu et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib57)); Lewis et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib97)); Lazaridou et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib92)); Borgeaud et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib12)); Peng et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib138)); Vu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib175))）。*持续学习（CL）* 旨在通过对新数据和更新数据的持续预训练来更新内部知识（Lazaridou et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib93)); Jang et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib70), [2022](https://arxiv.org/html/2403.08319v2#bib.bib69))）。然而，这些缓解时间不对齐的方法并不是万无一失的解决方案。KE 可能带来知识冲突的副作用，导致知识不一致（即一种记忆内冲突），甚至可能增强 LLMs 的幻觉（Li et al. ([2023f](https://arxiv.org/html/2403.08319v2#bib.bib106)); Pinter and Elhadad ([2023](https://arxiv.org/html/2403.08319v2#bib.bib142)）。对于 RAG，由于模型参数未更新，知识冲突是不可避免的（Chen et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib25)); Zhang and Choi ([2021](https://arxiv.org/html/2403.08319v2#bib.bib208)）。CL 面临灾难性遗忘问题，并且需要大量计算资源（De Lange et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib33)); He et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib59)); Wang et al. ([2023g](https://arxiv.org/html/2403.08319v2#bib.bib186)）。

信息污染。信息污染成为另一种导致上下文记忆冲突的因素，特别是对于时间不变的知识 Jang et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib70))。对手通过将虚假或误导性信息引入检索文档的网络语料库来利用这一漏洞 Pan et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib135), [b](https://arxiv.org/html/2403.08319v2#bib.bib137)); Weller et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib191)) 和用户对话 Xu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197)); Hu et al. ([2024](https://arxiv.org/html/2403.08319v2#bib.bib66))。后者构成了实际威胁，因为对手可以利用如*提示注入*攻击 Liu et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib110)); Greshake et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib54)); Yi et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib201))等技术。这种漏洞构成了实际威胁，因为模型可能在没有审查的情况下将误导性输入纳入，从而无意中传播错误信息 Xie et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195)); Pan et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib137)); Xu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197))。

虚构的恶意虚假信息可能显著破坏自动事实检查的准确性 Du et al. ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib39)) 和开放领域问答系统 Pan et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib135), [b](https://arxiv.org/html/2403.08319v2#bib.bib137))。此外，最近的研究还强调了模型倾向于迎合用户意见，即*谄媚*，进一步加剧了这一问题 Perez et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib139)); Turpin et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib173)); Wei et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib188)); Sharma et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib155))。在当前的 LLMs 环境下，NLP 社区对 LLMs 生成虚假信息的潜在风险表示越来越多的担忧 Ayoobi et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib6)); Kidd 和 Birhane ([2023](https://arxiv.org/html/2403.08319v2#bib.bib86)); Carlini et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib16)); Zhou et al. ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib219)); Spitale et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib166)); Chen 和 Shu ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib20))。研究人员承认检测 LLMs 生成的虚假信息的挑战 Tang et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib168)); Chen 和 Shu ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib19)); Jiang et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib75))。这凸显了在情境虚假信息背景下解决 LLMs 带来的细微挑战的紧迫性。

![[未标注的图片]](img/1a659a5b01c2ef160b61ce311c78d792.png)

备注。时间错位和虚假信息污染是引发上下文记忆冲突的两种不同情况。对于前者，最新的上下文信息被视为准确的。*相反*，对于后者，上下文信息包含虚假信息，因此被认为是不正确的。

### 2.2 模型行为分析

*LLMs 如何应对上下文记忆冲突？* 本节将详细介绍相关研究，尽管它们提供了相当不同的答案。根据场景的不同，我们首先介绍开放领域问答（ODQA）设置，然后关注一般设置。

ODQA。在早期的 ODQA 文献中，Longpre 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib111)）探讨了当提供的上下文信息与已学知识相矛盾时，QA 模型的表现。作者创建了一个自动化框架，用于识别具有命名实体答案的 QA 实例，然后用替代实体替换金标准文档中的实体提及，从而制造出冲突上下文。这项研究揭示了这些模型过度依赖参数知识的趋势。Chen 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib21)）重新审视了这一设置，并报告了不同的观察结果，他们指出模型在最佳表现的设置中主要依赖于上下文知识。他们将这一发现的分歧归因于两个因素。首先，Longpre 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib111)）使用的实体替换方法可能减少了扰动段落的语义连贯性。其次，Longpre 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib111)）的研究基于单一证据段落，而 Chen 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib21)）则利用了多个证据段落。最近，随着真正“巨大”的语言模型如 ChatGPT（Ouyang 等人，[2022](https://arxiv.org/html/2403.08319v2#bib.bib134)；OpenAI，[2023](https://arxiv.org/html/2403.08319v2#bib.bib132)）和 Llama 2（Touvron 等人，[2023](https://arxiv.org/html/2403.08319v2#bib.bib171)）的出现，研究人员重新审视了这一问题。Tan 等人（[2024](https://arxiv.org/html/2403.08319v2#bib.bib167)）研究了 LLMs 如何在 ODQA 设置中将检索到的上下文与生成的知识融合，并发现模型倾向于偏向参数知识，这受到这些生成的上下文与输入问题的更大相似性以及检索信息通常不完整的影响，尤其是在冲突源的范围内。

一般而言。谢等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195)) 利用 LLMs 生成与记忆知识冲突的背景。他们发现，LLMs 对外部证据非常敏感，即使这些证据与它们的参数相冲突，只要外部知识是连贯和有说服力的。同时，他们还发现 LLMs 存在明显的确认偏误 Nickerson ([1998](https://arxiv.org/html/2403.08319v2#bib.bib129))，即这些模型倾向于偏爱与其内部记忆一致的信息，即使面对相矛盾的外部证据。王等人 ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)) 认为，当 LLM 遇到冲突时，应该采取的行为是找出冲突并提供明确的答案。虽然 LLMs 在识别知识冲突的存在方面表现良好，但它们在确定具体冲突片段并在冲突信息中产生明确答案方面却存在困难。应等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib202)) 从两个角度分析了 LLMs 在冲突中的稳健性：事实稳健性（从提示或记忆中识别正确事实的能力）和决策风格（根据认知理论将 LLMs 的行为分类为直观、依赖或理性）。研究发现，LLMs 对误导性提示特别敏感，尤其是在常识知识的背景下。钱等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib144)) 更系统地评估了参数知识与外部知识之间的潜在互动，合作知识图（KG）。他们揭示了 LLMs 在面对直接冲突或详细上下文变化时，通常会偏离其参数知识。许等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197)) 研究了 LLMs 在互动会话中如何响应知识冲突。他们的研究结果表明，LLMs 倾向于偏爱逻辑结构良好的知识，即使它与事实准确性相矛盾。

![[无标题图片]](img/b70cd20838f82652e09cae77fa4eec83.png)

备注。*I. 制造冲突知识。* 通过人工制造冲突知识来分析模型在上下文与记忆冲突下的行为，早期通过实体级替代，更近来通过使用 LLMs 生成语义连贯的冲突。

*结论是什么？* 目前没有明确的规则来判断模型是否优先考虑上下文知识或参数知识。然而，通常情况下，*语义连贯、逻辑清晰和有说服力* 的知识比一般的冲突信息更受模型的青睐。

### 2.3 解决方案

解决方案根据其目标进行组织，即我们期望 LLM 在遇到冲突时表现出的期望行为。现有策略可分为以下目标：*忠实于背景*策略旨在与背景知识保持一致，侧重于背景优先级。*歧视错误信息*策略鼓励对可疑背景持怀疑态度，支持参数化知识。*解开来源*策略将背景和知识分开处理，并提供解开的答案。*提高事实性*策略旨在通过合并背景和参数化知识来实现集成回应，朝向更真实的解决方案。

忠实于背景。*微调*。Li 等人（[2022a](https://arxiv.org/html/2403.08319v2#bib.bib98)）认为 LLM 应优先考虑与任务相关信息的背景，当背景无关时依赖内部知识。他们将这两个特性命名为可控性和鲁棒性。他们引入了知识感知微调（KAFT）来通过将反事实和无关背景纳入标准训练数据集来增强这两个性质。TrueTeacher（Gekhman 等人，[2023](https://arxiv.org/html/2403.08319v2#bib.bib51)）致力于通过用 LLM 注释模型生成的摘要来改进摘要的事实一致性。这种方法有助于保持对原始文档背景的忠实，确保生成的摘要保持准确，不会被无关或错误的细节误导。DIAL（Xue 等人，[2023](https://arxiv.org/html/2403.08319v2#bib.bib199)）通过直接知识增强和强化学习来提高对话系统的事实一致性（RLFC），以便将回答与提供的事实知识准确地对齐。

*提示*。Zhou 等人（[2023d](https://arxiv.org/html/2403.08319v2#bib.bib220)）探索通过专门的提示策略来增强 LLM 对背景的遵循，具体包括基于观点的提示和反事实演示。这些技术被证明可以通过确保它们保持对相关背景的忠实而在上下文敏感性任务中显着提高 LLM 的性能，而不需要额外的训练。

*解码*。Shi 等人（[2023a](https://arxiv.org/html/2403.08319v2#bib.bib156)）引入了上下文感知解码（CAD）来通过增强有无背景下输出概率的差异来减少幻觉，类似于对比解码的概念 Li 等人（[2022c](https://arxiv.org/html/2403.08319v2#bib.bib103)）。CAD 通过优先考虑相关背景而不是模型的先验知识来增强 LLM 的忠实性，尤其是在存在冲突信息的任务中。

*知识插件。* Lee 等人（[2022a](https://arxiv.org/html/2403.08319v2#bib.bib94)）提出了持续更新 QA（CuQA）以提高 LMs 集成新知识的能力。他们的方法使用即插即用模块来存储更新的知识，确保原始模型不受影响。与传统的继续预训练或微调方法不同，CuQA 可以解决知识冲突。

*预训练。* ICLM（Shi 等人，[2023b](https://arxiv.org/html/2403.08319v2#bib.bib157)）是一种新的预训练方法，扩展了 LLM 处理长篇和多样化上下文的能力。该方法有可能通过使模型能够从更广泛的上下文中综合信息，从而提高其对相关知识的理解和应用，来帮助解决知识冲突。

*预测事实有效性。* Zhang 和 Choi（[2023](https://arxiv.org/html/2403.08319v2#bib.bib209)）通过引入事实持续时间预测来解决知识冲突，以识别和丢弃 LLM 中过时的事实。这种方法通过确保遵守最新的上下文信息来提高模型在 ODQA 等任务上的表现。

辨别虚假信息（忠于记忆）。*提示。* 为了应对虚假信息污染，Pan 等人（[2023b](https://arxiv.org/html/2403.08319v2#bib.bib137)）提出了防御策略，如虚假信息检测和警惕提示，旨在增强模型在潜在虚假信息中保持忠实于事实和参数信息的能力。同样，Xu 等人（[2023](https://arxiv.org/html/2403.08319v2#bib.bib197)）利用系统提示来提醒 LLM 在回应前要小心潜在的虚假信息，并验证其记忆中的知识。这一方法旨在提升 LLM 保持忠实性的能力。

*查询增强。* Weller 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib191)）利用大语料库中信息的冗余性来防御虚假信息污染。他们的方法包括查询增强，以找到一组多样化的、不太可能被污染的段落，并结合名为“答案冗余的信心”的信心方法，该方法比较预测答案在检索上下文中的一致性。这一策略通过从多个来源交叉验证答案来缓解知识冲突，从而确保模型的忠实性。

*训练判别器。* Hong 等人（[2023](https://arxiv.org/html/2403.08319v2#bib.bib63)）对一个较小的语言模型进行微调作为判别器，并结合提示技术来提高模型区分可靠与不可靠信息的能力，帮助模型在面对误导性上下文时保持忠实。

源头解缠。DisentQA (Neeman 等, [2022](https://arxiv.org/html/2403.08319v2#bib.bib128)) 训练一个模型，该模型为给定问题预测两种类型的答案：一种基于上下文知识，另一种基于参数化知识。Wang 等 ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)) 介绍了一种方法来改善 LLMs 对知识冲突的处理。他们的方法是一个三步过程，旨在帮助 LLMs 检测冲突，准确识别冲突片段，并基于冲突数据生成不同的、知情的响应，旨在获得更精确和细致的模型输出。

改善事实性。Zhang 等 ([2023e](https://arxiv.org/html/2403.08319v2#bib.bib212)) 提出了 COMBO，这是一种将兼容的生成和检索段落配对以解决不一致的框架。它使用在银标上训练的判别器来评估段落的兼容性，通过利用 LLM 生成的（参数化）和外部检索的知识来改善 ODQA 性能。Jin 等 ([2024a](https://arxiv.org/html/2403.08319v2#bib.bib76)) 介绍了一种基于对比解码的算法，即 CD²，它最大化知识冲突下各种 logits 之间的差异，并校准模型对真实答案的信心。

![[未标注图片]](img/3aa5d7ae0235d0a558fb54e0bffad5c5.png)

备注。当前的缓解方法目标相互矛盾，因为它们在考虑冲突情景时没有区分知识冲突的两种原因。盲目地“忠实”于上下文或知识是不可取的。一些研究人员认为 LLM 不应仅依赖于参数化或上下文信息，而应赋予 LLM 用户基于不同答案做出知情决策的权力 (Wang 等, [2023h](https://arxiv.org/html/2403.08319v2#bib.bib187); Floridi, [2023](https://arxiv.org/html/2403.08319v2#bib.bib47))。

## 3 内部上下文冲突

内部上下文冲突在将外部信息源纳入大型语言模型（LLMs）时表现出来，这一挑战在 RAG 技术出现后更加突出。RAG 通过将从检索文档中获取的内容整合到上下文中来丰富 LLM 的响应。然而，这种整合可能会导致提供的上下文中的不一致，因为外部文档可能包含彼此冲突的信息 Zhang 和 Choi ([2021](https://arxiv.org/html/2403.08319v2#bib.bib208)); Kasai 等 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib85)); Li 等 ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib99))。

### 3.1 原因

虚假信息。虚假信息长期以来一直是现代数字时代的重要问题 Shu et al. ([2017](https://arxiv.org/html/2403.08319v2#bib.bib159)); Zubiaga et al. ([2018](https://arxiv.org/html/2403.08319v2#bib.bib222)); Kumar and Shah ([2018](https://arxiv.org/html/2403.08319v2#bib.bib89)); Meel and Vishwakarma ([2020](https://arxiv.org/html/2403.08319v2#bib.bib119)); Fung et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib48)); Wang et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib179))。RAG 的出现将外部文档纳入其中，以提高 LLMs 的生成质量。虽然 RAG 有可能通过多样化的知识来源丰富内容，但它也存在包含虚假信息的风险，例如假新闻 Chen et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib23))。此外，还出现了使用 AI 技术创建或传播虚假信息的情况 Weidinger et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib189)); Zhou et al. ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib219)); Vergho et al. ([2024](https://arxiv.org/html/2403.08319v2#bib.bib174))。LLMs 的先进生成能力加剧了这一问题，导致这些系统生成的虚假信息增加。这一趋势令人担忧，因为它不仅助长了虚假信息的传播，还挑战了检测 LLMs 生成虚假信息的能力 Chen and Shu ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib20)); Menczer et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib120)); Barrett et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib7)); Bengio et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib10)); Wang et al. ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib180)); Solaiman et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib165)); Weidinger et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib190)); Ferrara ([2023](https://arxiv.org/html/2403.08319v2#bib.bib46)); Goldstein et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib53)).

过时的信息。除了虚假信息的挑战外，重要的是要认识到事实可能会发展。检索到的文档可能同时包含来自网络的更新和过时的信息，从而导致这些文档之间的冲突 Chen et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib25)); Liska et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib108)); Zhang and Choi ([2021](https://arxiv.org/html/2403.08319v2#bib.bib208)); Kasai et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib85)); Schlichtkrull et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib153)).

![[未标注的图片]](img/b5dd8a4974f126b9fcaa8e5bd2dcaf58.png)

备注。语境中的冲突经常发生在**虚假信息**与**准确信息**之间，以及**过时信息**与**更新信息**之间。这两种冲突对 LLM 的影响不同，需要进行具体分析。与虚假信息冲突不同，另一个重要挑战是处理来源于不同时间戳的文档之间的冲突，特别是当用户的提示指定了特定时间段时。

### 3.2 模型行为分析

性能影响。以往研究通过实证证明，预训练语言模型的性能可以受到特定语境中**虚假信息**Zhang 和 Choi（[2021](https://arxiv.org/html/2403.08319v2#bib.bib208)）或**过时信息**Du 等（[2022b](https://arxiv.org/html/2403.08319v2#bib.bib39)）的显著影响。在最近的研究中，Pan 等（[2023a](https://arxiv.org/html/2403.08319v2#bib.bib135)）引入了一种**虚假信息攻击策略**，涉及创建虚假的维基百科文章版本，然后将其插入到真实的维基百科语料库中。他们的研究结果揭示了现有语言模型对虚假信息攻击的易感性，无论虚假文章是手动编写还是由模型生成。为了更深入地了解 LLM 在遇到矛盾语境时的表现，Chen 等（[2022](https://arxiv.org/html/2403.08319v2#bib.bib21)）主要使用 Fusion-in-Decoder 在 NQ-Open Kwiatkowski 等（[2019](https://arxiv.org/html/2403.08319v2#bib.bib90)）和 TriviaQA Joshi 等（[2017](https://arxiv.org/html/2403.08319v2#bib.bib78)）上进行实验。他们发现，知识来源的矛盾对模型的信心水平影响甚微。这些模型倾向于偏向与查询直接相关的上下文以及与模型固有的参数知识相一致的上下文。Xie 等（[2023](https://arxiv.org/html/2403.08319v2#bib.bib195)）在 PopQA Mallen 等（[2022](https://arxiv.org/html/2403.08319v2#bib.bib113)）和 StrategyQA Geva 等（[2021](https://arxiv.org/html/2403.08319v2#bib.bib52)）中对闭源 LLM 和开源 LLM 进行实验。获得的结果与 Chen 等（[2022](https://arxiv.org/html/2403.08319v2#bib.bib21)）的结果一致，表明 LLM 表现出显著的偏向于与模型的参数记忆一致的证据。他们还发现 LLM 倾向于强调与更高人气实体相关的信息以及在给定上下文中被更多文档证实的答案。此外，这些模型对数据引入的顺序表现出显著的敏感性。Jin 等（[2024a](https://arxiv.org/html/2403.08319v2#bib.bib76)）发现，随着冲突跳跃数的增加，LLM 在推理中面临更大的挑战。

检测能力。除了评估 LLM 在面对矛盾上下文时的表现外，一些研究还探讨了它们识别这种矛盾的能力。Zheng 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib215)）研究了包括 BERT、RoBERTa 和 ERNIE 在内的各种模型在检测中文对话中的矛盾表现。实验显示，识别对话中的矛盾陈述对这些模型来说是一个重大挑战。Li 等人（[2023a](https://arxiv.org/html/2403.08319v2#bib.bib99)）分析了 GPT-4、PaLM-2 和 Llama 2 在识别新闻文章中的矛盾文件的表现 Hermann 等人（[2015](https://arxiv.org/html/2403.08319v2#bib.bib60)）、故事 Kočiský等人（[2018](https://arxiv.org/html/2403.08319v2#bib.bib88)）和维基百科 Merity 等人（[2017](https://arxiv.org/html/2403.08319v2#bib.bib122)）。作者发现平均检测准确率不佳。研究还发现，LLM 在处理某些类型的矛盾时面临特定挑战，特别是涉及主观情感或观点的矛盾。此外，文档的长度和自我矛盾的多样性对检测性能的影响较小。Wan 等人（[2024](https://arxiv.org/html/2403.08319v2#bib.bib176)）调查了在面对冲突信息时影响 LLM 评估文档可信度的文本特征。他们发现现有模型严重依赖于文档与查询的相关性，但经常忽略人类认为重要的风格特征，例如科学参考文献的存在或文本的中立语气。Jin 等人（[2024a](https://arxiv.org/html/2403.08319v2#bib.bib76)）发现 LLM 在区分真实信息与虚假信息方面遇到困难。此外，他们发现 LLM 倾向于偏爱在上下文中最频繁出现的证据，并对与其内部记忆一致的外部信息表现出确认偏误。

![[未标注的图片]](img/3056f7567a8d8df15b27f17313e6bd21.png)

备注。当在给定的上下文中遇到冲突时，LLM 表现出的知识受到显著影响。然而，确定模型如何响应各种上下文细微差别仍然是一个需要进一步探讨的领域。虽然不同模型可能具有某些共同点，但由于训练数据的变化，行为差异也随之产生。此外，由于模型的知识来源于文本信息，其识别虚假信息的方法与人类大相径庭。

### 3.3 解决方案

消除冲突。*专用模型。* Hsu 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib64)) 开发了一个名为 Pairwise Contradiction Neural Network (PCNN) 的模型，利用微调的 Sentence-BERT 嵌入来计算文章的矛盾概率。Pielka 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib141)) 建议将语言学知识纳入学习过程中，因为发现 XLM-RoBERTa 在有效把握对准确矛盾检测至关重要的句法和语义特征方面存在困难。Wu 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib193)) 提出了一个创新的方法，将文本的拓扑表示整合到语言模型中，以增强矛盾检测能力，并在 MultiNLI 数据集上评估了他们的方法 Williams 等人 ([2018](https://arxiv.org/html/2403.08319v2#bib.bib192))。

*通用模型。* Chern 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib26)) 提出了一个事实核查框架，将大语言模型与包括 Google 搜索、Google 学术、代码解释器和 Python 在内的各种工具结合起来，用于检测文本中的事实错误。Leite 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib96)) 运用大语言模型生成与预定义的可信度信号相关的弱标签，并通过弱监督技术汇总这些标签，以对输入文本的真实性进行预测。

提升鲁棒性。*训练方法。* Hong 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib63)) 提出了一种新颖的微调方法，该方法涉及使用共享编码器同时训练一个判别器和一个解码器。此外，作者还提出了另外两种策略来提高模型的鲁棒性，包括在生成响应之前让 GPT-3 识别扰动文档，并将判别器的输出整合到 GPT-3 的提示中。他们的实验结果表明，微调方法产生了最有前景的结果。

*查询增强。* Weller 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib191)) 探讨了一种查询增强技术，该技术促使 GPT-3 从原始问题中生成新问题。然后，他们通过参考检索到的相应段落来评估每个答案的可信度。根据可信度，他们决定是否依赖原始问题的预测，或者将高可信度分数的增强问题的预测结果进行汇总。

![[未标注的图片]](img/c83e69920eb76c9c681272549a16b4d8.png)

备注。解决上下文间冲突的策略主要依赖于模型知识或利用外部知识，如检索到的文档。最近，增强 LLM 与外部工具的结合已成为一种新范式。探索利用外部工具来支持 LLM 解决上下文间冲突可能是一个有前途的方法。另一方面，制定统一高效的方法来处理各种冲突类型仍然是一个巨大的挑战。

## 4 内存冲突

随着大型语言模型（LLMs）的发展，它们在知识密集型问答系统中得到了广泛应用 Gao et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib50)); Yu et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib203)); Petroni et al. ([2019](https://arxiv.org/html/2403.08319v2#bib.bib140)); Chen et al. ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib24))。有效部署 LLMs 的一个关键方面是确保它们在各种具有类似含义或意图的表达中产生一致的输出。尽管这种需求存在，但一个显著的挑战是内存冲突——即 LLMs 在处理语义等价但句法不同的输入时表现出不可预测的行为并生成不同的响应 Chang and Bergen ([2023](https://arxiv.org/html/2403.08319v2#bib.bib17)); Chen et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib22)); Raj et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib146)); Rabinovich et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib145)); Raj et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib147)); Bartsch et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib8))。内存冲突本质上通过引入一定程度的不确定性，削弱了 LLMs 的可靠性和实用性。

### 4.1 原因

LLMs 中的内存冲突可以归因于三个主要因素：训练语料库的偏差 Wang et al. ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib181)); Xu et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib196))，解码策略 Lee et al. ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib95)); Huang et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib67))，以及知识编辑 Yao et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib200)); Li et al. ([2023f](https://arxiv.org/html/2403.08319v2#bib.bib106))。这些因素分别涉及训练阶段、推理阶段以及随后的知识优化。

训练语料中的偏见。近期研究表明，LLM 中知识获取的主要阶段主要发生在预训练阶段 Zhou et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib217)); Kaddour et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib80)); Naveed et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib127)); Akyürek et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib4)); Singhal et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib162))。预训练语料库主要从互联网爬取，数据质量多样，可能包括不准确或误导性的信息 Bender et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib9)); Weidinger et al. ([2021](https://arxiv.org/html/2403.08319v2#bib.bib189))。当 LLM 在包含错误知识的数据上进行训练时，它们可能会记住并无意中放大这些不准确性 Lin et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib107)); Elazar et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib41)); Lam et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib91)); Grosse et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib55))，导致 LLM 的参数中共存冲突的知识。

此外，先前的研究表明，LLM（大型语言模型）倾向于编码其训练数据中常见的表面关联，而不是真正理解其中蕴含的基本知识 Li et al. ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib102)); Kang and Choi ([2023](https://arxiv.org/html/2403.08319v2#bib.bib82)); Zhao et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib213)); Kandpal et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib81))。这可能导致 LLM 表现出生成基于训练数据虚假关联的预设响应的倾向。由于依赖虚假关联，LLM 在面对具有不同句法结构但传达相同语义的提示时，可能会提供不同的答案。

解码策略。LLMs 的直接输出是潜在下一个标记的概率分布。从该分布中确定生成内容的关键一步是进行抽样。已提出了各种抽样技术，包括贪婪抽样、top-p 抽样、top-k 抽样等 Jawahar 等人（[2020](https://arxiv.org/html/2403.08319v2#bib.bib72)）；Massarelli 等人（[2020](https://arxiv.org/html/2403.08319v2#bib.bib118)），广泛分类为确定性和随机抽样方法。随机抽样作为 LLMs 采用的主要解码策略 Fan 等人（[2018](https://arxiv.org/html/2403.08319v2#bib.bib44)）；Holtzman 等人（[2020](https://arxiv.org/html/2403.08319v2#bib.bib62)）。然而，随机抽样方法的随机本质会引入不确定性到生成的内容中。此外，由于 LLMs 固有的从左到右的生成模式，抽样标记的选择会对随后的生成产生重大影响。使用随机抽样可能导致 LLMs 产生完全不同的内容，甚至在提供相同上下文的情况下，造成内存内部冲突 Lee 等人（[2022b](https://arxiv.org/html/2403.08319v2#bib.bib95)）；Huang 等人（[2023](https://arxiv.org/html/2403.08319v2#bib.bib67)）；Dziri 等人（[2021](https://arxiv.org/html/2403.08319v2#bib.bib40)）。

知识编辑。随着模型参数呈指数增长，微调 LLM 变得越来越具挑战性和资源密集型。为了应对这一挑战，研究人员探索知识编辑技术，作为一种有效修改 LLMs 中编码知识范围的手段 Meng 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib121)）；Ilharco 等人（[2022](https://arxiv.org/html/2403.08319v2#bib.bib68)）；Zhong 等人（[2023](https://arxiv.org/html/2403.08319v2#bib.bib216)）。确保修改的一致性带来了重大挑战。由于编辑方法固有的潜在限制，修改后的知识无法有效地进行概括。这可能导致 LLMs 在处理相同知识在不同情况下产生不一致的响应 Li 等人（[2023f](https://arxiv.org/html/2403.08319v2#bib.bib106)）；Yao 等人（[2023](https://arxiv.org/html/2403.08319v2#bib.bib200)）。在知识编辑的背景下，内存冲突主要被认为是一个副作用。

![[无题图像]](img/e8558e92e4e2dd65a15c6abd02f7105c.png)

备注。在大型语言模型（LLMs）中，内存冲突源于三个不同阶段的不同原因。其中，训练语料库的偏差被认为是根本性催化剂。训练数据集中知识的不一致导致了模型参数中知识的矛盾。此外，解码策略间接加剧了这些冲突。在推理过程中，采样过程的固有随机性放大了模型响应中的不一致性。知识编辑旨在对模型知识进行后期更新，但可能会无意中将冲突信息引入 LLM 的记忆中。

### 4.2 模型行为分析

自我不一致性。Elazar 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib42)) 开发了一种评估语言模型知识一致性的方法，特别关注知识三元组。作者主要使用 BERT、RoBERTa 和 ALBERT 进行实验。他们的研究发现，这些模型的一致性较差，准确率仅在 50% 到 60% 之间。Hase 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib58)) 使用了与 Elazar 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib42)) 相同的指标，但他们使用了更多样化的数据集。他们的研究还揭示了 RoBERTa-base 和 BART-base 在释义背景中的一致性不足。赵等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib214)) 重新表述问题，然后评估 LLM 对这些重新表述问题的回答的一致性。他们的研究结果显示，即使是 GPT-4 在常识问答任务中的不一致率也达到 13%。他们进一步发现，LLMs 在面对不常见知识时更容易产生不一致性。Dong 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib37)) 对多个开源 LLM 进行了实验，发现所有这些模型都表现出较强的不一致性。Li 等人 ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib104)) 探讨了 LLMs 可能在回答问题时给出初步答案，但在被问及该答案是否正确时可能会否认之前的答案的不一致性。他们的实验重点是 Close-Book Question Answering，揭示 Alpaca-30B 仅在 50% 的情况下显示出一致性。

为了进一步分析 LLMs 表现出的不一致性，Li et al. ([2022b](https://arxiv.org/html/2403.08319v2#bib.bib102)) 的研究揭示了基于编码器的模型往往更依赖于位置接近且高度共现的词汇，而不是依赖于知识的词汇，从而生成错误的事实。这一现象源于这些模型倾向于从训练数据集中过度学习不适当的关联。Kang 和 Choi ([2023](https://arxiv.org/html/2403.08319v2#bib.bib82)) 强调了 LLMs 中的共现偏差，即模型更倾向于选择经常共现的词汇而不是正确答案，尤其是在回忆事实时，当主题和宾语在预训练数据集中很少共现时，即使进行了微调。此外，他们的研究表明，LLMs 在回忆事实时面临挑战，尤其是在主题和宾语在预训练数据集中很少一起出现的情况下，即使这些事实在微调过程中出现过。

知识的潜在表示。现代大规模语言模型（LLMs）固有的多层变压器架构促成了复杂的内存冲突，具有不同知识表示分散在各个层级的特点。之前的研究表明，LLMs 在较浅的层级存储低级信息，而在较深的层级存储语义信息 Tenney et al. ([2019](https://arxiv.org/html/2403.08319v2#bib.bib169)); Rogers et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib151)); Wang et al. ([2019](https://arxiv.org/html/2403.08319v2#bib.bib177)); Jawahar et al. ([2019](https://arxiv.org/html/2403.08319v2#bib.bib73)); Cui et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib31)). Chuang et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib28)) 在 LLMs 的背景下探索了这一方面，发现 LLMs 中的事实知识通常集中在特定的变压器层级中，并且不同层级之间存在不一致的知识。此外，Li et al. ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib101)) 发现正确的知识确实存储在模型的参数中，但在生成过程中可能未能准确表达。作者对同一 LLM 进行了两项实验，一项集中于生成准确性，另一项利用知识探测器检查知识的包含情况。这些实验的结果揭示了知识探测器准确性与生成准确性之间存在高达 40%的显著差异。

跨语言不一致性。真正知识的普遍性超越了表面形式的变化 Ohmer 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib130))，这一原则理想情况下应适用于大语言模型（LLMs）。然而，大语言模型在不同语言之间保持不同的知识集合，这导致了不一致性 Ji 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib74)); Xue 等人 ([2024](https://arxiv.org/html/2403.08319v2#bib.bib198))。Wang 等人 ([2023f](https://arxiv.org/html/2403.08319v2#bib.bib185)) 研究了大语言模型在跨语言扩展编辑知识时面临的挑战，建议不同语言相关的知识在模型参数中被单独存储。Qi 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib143)) 提出了一个名为 RankC 的指标，用于评估大语言模型事实知识的跨语言一致性。他们使用该指标分析了多个模型，并揭示了大语言模型存储的知识存在显著的语言依赖性，随着模型规模的增加，跨语言一致性没有显著改善。

![[未标注的图片]](img/ad7a264d510c6691d57fa3b785a103a1.png)

备注。大语言模型中的记忆冲突现象主要表现为对语义相同查询的响应不一致。这种不一致主要归因于预训练阶段使用的数据集质量不佳。解决这一挑战需要开发高效且经济的解决方案，这仍然是一个重要的难题。此外，大语言模型的知识电路多样，这显著影响了其对特定查询的响应机制。对这些知识电路的探索和详细检查代表了未来研究的一个有前途的方向。

### 4.3 解决方案

#### 4.3.1 提高一致性

*微调*。Elazar 等人 ([2021](https://arxiv.org/html/2403.08319v2#bib.bib42)) 提出了一个一致性损失函数，并使用一致性损失与标准 MLM 损失的组合来训练语言模型。Li 等人 ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib104)) 利用一个语言模型的双重功能：作为生成器生成响应，并作为验证器评估这些响应的准确性。该过程包括查询生成器以获得响应，然后由验证器评估其准确性。仅保留那些被认为是一致的响应对。这些一致的响应对随后用于微调模型，旨在提高生成一致响应对的可能性。

*插件。* Jang 和 Lukasiewicz ([2023](https://arxiv.org/html/2403.08319v2#bib.bib71)) 利用中间训练技术，利用词汇定义对从词典中重新训练语言模型，提升其对符号意义的理解。随后，他们提出了一种高效的参数集成方法，将这些增强的参数与现有语言模型的参数融合。此方法旨在通过增强模型理解意义的能力来纠正模型的不一致行为。

*输出集成。* Mitchell 等人 ([2022](https://arxiv.org/html/2403.08319v2#bib.bib125)) 通过利用两个模型的架构来缓解语言模型的不一致性，其中包括一个基础模型生成一组潜在答案，然后是一个关系模型评估这些答案之间的逻辑一致性。最终答案是通过考虑基础模型和关系模型的信念来选择的。Zhao 等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib214)) 提出了一个检测问题是否可能导致 LLM 不一致的方法。具体来说，他们首先使用 LLM 重述原始问题并获得相应的答案。然后，他们对这些答案进行聚类并检查差异。检测是基于差异水平来确定的。

#### 4.3.2 改善事实性

Chuang 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib28)) 提出了一个名为 DoLa 的新型对比解码方法。具体来说，作者开发了一种动态层选择策略，选择适当的早期层和成熟层。接下来的词输出概率通过计算早期层和成熟层的对数概率差异来确定。Li 等人 ([2023c](https://arxiv.org/html/2403.08319v2#bib.bib101)) 提出了类似的方法，名为 ITI。他们首先识别出一组稀疏的注意力头，这些头在 TruthfulQA 评估中显示出高线性探测准确率。推理阶段，ITI 沿着通过知识探测获得的与真实性相关的方向移动激活。这个干预过程在完成时对每个标记进行自回归重复。DoLa 和 ITI 都解决了模型不同层之间的知识不一致性，以减少 LLM 中的事实错误。

![[未标注的图像]](img/af21439121a8b5ca2d01bbfe4a931ed3.png)

备注。在 LLMs 中解决记忆冲突通常包括三个阶段：训练、生成和事后处理。训练阶段的方法主要集中在减少模型参数之间的内部不一致性。相反，生成和事后阶段主要涉及算法干预，旨在缓解模型行为不一致的发生。然而，挑战仍然在于解决参数知识的不一致性而不对 LLMs 的整体性能产生负面影响。

## 5 个挑战与未来方向

在本节中，我们提供了总结并突出了当前研究中的挑战，同时概述了知识冲突领域的潜在未来方向。

知识冲突的实际情况。目前，知识冲突的生成主要依赖于人为生成不正确或误导性的信息。在现实世界中，知识冲突最常见的情况之一是发生在 RALMs（检索增强语言模型）中，在这些模型中，冲突存在于从网络中直接检索到的文档中。当前分析方法在知识冲突的实验设置上存在差距，这表明那些环境中的研究发现（Xie 等 [2023](https://arxiv.org/html/2403.08319v2#bib.bib195); Wang 等 [2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)）可能难以转移到实际应用中。最近的研究已经开始通过基于 Google 实际搜索结果策划冲突文档来调查实际情况（Wan 等 [2024](https://arxiv.org/html/2403.08319v2#bib.bib176)）。展望未来，人们对评估 LLMs 在现实世界情境中表现的研究越来越感兴趣，而不是人工生成的冲突，以更好地理解它们的能力。

更精细的解决方案。目前，由于知识冲突的固有复杂性，还没有一种通用的解决方案。现有方案要么假设先前已有知识 Shi et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib157))，要么专注于冲突的某个子类 Wang et al. ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187))。我们认为，解决这个问题需要一种更精细的方法，考虑多个因素。首先，用户查询的性质起着关键作用。主观或有争议的问题自然会导致冲突，因为它们可能有多种有效答案 Bjerva et al. ([2020](https://arxiv.org/html/2403.08319v2#bib.bib11)); Wan et al. ([2024](https://arxiv.org/html/2403.08319v2#bib.bib176))。其次，冲突信息的来源可以不同，包括错误信息、过时的事实或部分正确的数据 Guo et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib56)); Akhtar et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib3))。最后，还需要考虑用户的期望，例如，他们是否希望 LLM 提供单一明确的答案，还是对多种观点持开放态度 Floridi ([2023](https://arxiv.org/html/2403.08319v2#bib.bib47))。鉴于这些考虑，未来缓解知识冲突的解决方案必须深入这些细微差别，认识到知识冲突包含了一系列具有不同原因、表现和潜在解决方案的问题。希望 NLP 和 HCI 研究人员之间的合作能够开展全面的调查并开发有效的解决方案。

下游任务的评估。目前，对 LLM 中知识冲突的研究主要集中在评估它们在常见 QA 数据集上的表现，包括 NQ-Open、TriviaQA、OPQA 和 StrategyQA。这个重点忽略了知识冲突的更广泛影响，特别是它们如何影响下游任务。探索知识冲突对更广泛应用领域的影响，可能会为创建更稳健可靠的模型提供洞见。例如，在需要高精度和一致性的任务中，如法律文件分析 Shui et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib160)); Martin et al. ([2024](https://arxiv.org/html/2403.08319v2#bib.bib117))、医疗诊断 Zhou et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib218)); Thirunavukarasu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib170))、金融分析 Zhang et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib205)); Li et al. ([2023e](https://arxiv.org/html/2403.08319v2#bib.bib105)) 和教育工具 Caines et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib15)); Milano et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib123))，未解决的知识冲突可能会削弱模型的实用性。

冲突间的相互作用。当前对 LLMs 知识冲突的研究主要集中于单一类型冲突的调查 Wang et al. ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)); Chen et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib21)); Li et al. ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib104)) 或对上下文-记忆冲突的联合研究 Jin et al. ([2024a](https://arxiv.org/html/2403.08319v2#bib.bib76)); Xie et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195))。然而，关于内部记忆冲突与其他两种冲突类型之间的相互作用的研究明显不足。几篇论文提出了 LLMs 中存在知识电路的概念 Chughtai et al. ([2024](https://arxiv.org/html/2403.08319v2#bib.bib29)); Huang et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib67))，这与内部记忆冲突密切相关。解决这一空白对于理解模型内部知识不一致与其对上下文响应行为之间的关系至关重要。此外，探索各种冲突类型的协同效应可能揭示 LLMs 知识表示和处理的潜在机制，并帮助我们在实践中开发出更强大、更准确的 LLMs。

解释性。最近的研究分析了大型语言模型（LLMs）在输出层知识冲突中的行为 Xie et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195)); Wang et al. ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187))。尽管一些研究观察并探讨了模型对其输出的信心，即 logits Xu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197)); Jin et al. ([2024a](https://arxiv.org/html/2403.08319v2#bib.bib76)); Wang et al. ([2024b](https://arxiv.org/html/2403.08319v2#bib.bib184))，但对模型的内部机制，如冲突期间的具体注意力头或神经元激活，关注较少。这一空白突显了需要更多微观的研究，以更好地理解模型在遇到冲突时的决策过程。Jin et al. ([2024b](https://arxiv.org/html/2403.08319v2#bib.bib77)) 的一项最近研究通过信息流分析推动了这一领域的进展，明确了冲突缓解的关键点。他们发现，某些注意力头在后续层中具有相反的效果，其中记忆头可以从内部记忆中回忆知识，而上下文头可以从外部上下文中检索知识。受此启发，引入了通过路径修剪的头来高效解决冲突而无需更新模型参数。

多语言性。迄今为止，关于知识冲突的研究主要集中在英语语言上。未来的研究可以朝两个方向扩展。首先，通过检查 LLMs 在非英语提示中解决知识冲突，利用许多先进的非英语模型（例如，GLM Zeng et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib204))用于中文）或具有多语言能力的 LLMs（例如，GPT-4 OpenAI ([2024](https://arxiv.org/html/2403.08319v2#bib.bib133)))，并注意英语和其他语言之间的差异，以考虑独特的语言特征。其次，解决跨上下文冲突，其中可能会检索到多种语言的多个文档，可能涉及跨语言知识冲突。解决方案包括使用翻译系统 Dementieva and Panchenko ([2021](https://arxiv.org/html/2403.08319v2#bib.bib34))，或对于资源稀缺的语言，利用高资源语言的证据（Xue et al., [2024](https://arxiv.org/html/2403.08319v2#bib.bib198)）或采用知识蒸馏技术。

多模态性。当前关于知识冲突的研究主要集中在文本模态上，留待未来探索的一个有前景的领域是这些冲突在多模态环境中的研究。随着大型语言模型（LLMs）不断发展，能够处理各种格式的信息——图像 Alayrac et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib5)); Li et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib100)), 视频 Ju et al. ([2022](https://arxiv.org/html/2403.08319v2#bib.bib79)); Zhang et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib206)), 和音频 Borsos et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib13)); Wu et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib194))——冲突的潜力在不断增加。例如，文本文件可能与视觉数据发生冲突，或音频片段的语气可能与附带字幕的内容相矛盾。未来关于多模态知识冲突的研究可以集中在打造擅长跨模态推理和解决冲突的先进 LLMs 上。这项工作需要提高模型在不同模态之间复杂动态的导航能力，并开发针对性的数据显示以实现有效的训练和评估。此外，探索用户如何感知和管理多模态冲突，例如文本和图像之间的差异，将为改进 LLMs 以实现更好的人工交互提供宝贵的见解。

## 6 结论

通过这项调查，我们广泛研究了知识冲突，揭示了其分类、原因、LLM 对这些冲突的反应以及可能的解决方案。我们的发现揭示了知识冲突是一个多面的问题，模型的行为与特定类型的冲突知识密切相关。此外，这三种冲突之间似乎存在更复杂的相互作用。我们还观察到，现有解决方案主要处理人为构造的场景，忽略了通过依赖假定的先验来解决冲突的细微差别，从而牺牲了细节和广度。鉴于检索增强语言模型的使用日益增多，我们预计 LLM 面临的知识冲突将变得更加复杂，这突显了需要更全面研究的必要性。

## 局限性

鉴于知识冲突领域研究的迅速扩展和大量的学术文献，我们可能会遗漏一些最新或相关性较低的发现。尽管如此，我们已确保在我们的调查中包含了所有必要的材料。

## 伦理声明

我们主要在 Google Scholar 和 ACL Anthology 上使用包括“知识冲突”、“知识不一致”、“知识差距”等关键术语，搜索了 2021 年之后发表的论文。在初步识别这些论文后，作者通过阅读对其进行分类，并通过引用跟踪相关但被忽视的论文。我们还使用 Google Scholar 跟进最新的引用这些论文的文献，以避免遗漏。

对于定量分析和比较部分（[§ A.1](https://arxiv.org/html/2403.08319v2#A1.SS1 "A.1 Quantitative Analysis and Comparison ‣ Appendix A Appendix ‣ Knowledge Conflicts for LLMs: A Survey")），我们没有进行计算实验，而是简单地整理了其他文献中报告的结果。

## 参考文献

+   Aggarwal 等（2021）Shourya Aggarwal、Divyanshu Mandowara、Vishwajeet Agrawal、Dinesh Khandelwal、Parag Singla 和 Dinesh Garg. 2021. [CommonsenseQA 的解释：新数据集和模型](https://doi.org/10.18653/v1/2021.acl-long.238)。在 *第 59 届年度计算语言学协会年会和第 11 届国际联合自然语言处理会议（卷 1：长文）*，第 3050–3065 页，在线。计算语言学协会。

+   Agrawal 等（2023）Ayush Agrawal、Lester Mackey 和 Adam Tauman Kalai. 2023. [语言模型是否知道它们在幻觉参考？](https://arxiv.org/abs/2305.18248) *ArXiv 预印本*，abs/2305.18248。

+   Akhtar 等 (2023) 穆巴沙拉·阿赫塔、迈克尔·施利希特库尔、郭志江、奥安娜·科卡拉斯库、埃琳娜·辛佩尔、和安德烈亚斯·弗拉霍斯。2023。 [多模态自动事实核查：综述](https://doi.org/10.18653/V1/2023.FINDINGS-EMNLP.361)。见 *计算语言学协会会议发现：EMNLP 2023，新加坡，2023 年 12 月 6-10 日*，第 5430–5448 页。计算语言学协会。

+   Akyürek 等 (2022) 埃金·阿基尤雷克、托尔加·博卢克巴西、弗雷德里克·刘、宾宾·熊、伊恩·特尼、雅各布·安德烈亚斯、和凯尔文·古。2022。《追踪语言模型中的知识回到训练数据》。见 *计算语言学协会会议发现：EMNLP 2022*，第 2429–2446 页。

+   Alayrac 等 (2022) 让-巴普蒂斯特·阿拉伊拉克、杰夫·多纳休、保琳·卢克、安托万·米赫、伊恩·巴尔、雅娜·哈松、卡雷尔·伦茨、阿瑟·门施、凯瑟琳·米利肯、马尔科姆·雷诺兹等。2022。《Flamingo: 一种用于少量样本学习的视觉语言模型》。*神经信息处理系统进展*，35:23716–23736。

+   Ayoobi 等 (2023) 纳维德·阿尤比、萨达特·沙赫里亚尔、和阿尔君·穆克吉。2023。《假冒和 LLM 生成的 LinkedIn 个人资料的迫在眉睫威胁：检测和预防的挑战与机遇》。见 *第 34 届 ACM 超文本与社交媒体会议论文集*，第 1–10 页。

+   Barrett 等 (2023) 克拉克·巴雷特、布拉德·博伊德、埃利·布尔斯坦、尼古拉斯·卡尔尼、布拉德·陈、池智赫、阿姆里塔·罗伊·乔杜里、米哈伊·克里斯托多雷斯库、阿努帕姆·达塔、索赫伊尔·费兹等。2023。《识别和缓解生成 AI 的安全风险》。*隐私与安全的基础与趋势®*，6(1):1–52。

+   Bartsch 等 (2023) 亨宁·巴特施、奥勒·约根森、多梅尼克·罗萨蒂、贾森·霍尔舍-奥伯迈尔、和雅各布·福。2023。 [大型语言模型在模糊性下的自我一致性](https://arxiv.org/abs/2310.13439)。*ArXiv 预印本*，abs/2310.13439。

+   Bender 等 (2021) 艾米丽·M·本德、蒂姆尼特·盖布鲁、安吉丽娜·麦克米兰-梅杰、和香农·施密切尔。2021。《关于随机鹦鹉的危险：语言模型会不会过大？》见 *2021 年 ACM 公平性、问责制与透明度会议论文集*，第 610–623 页。

+   Bengio 等 (2023) 约书亚·本吉奥、杰弗里·辛顿、安德鲁·姚、道恩·宋、彼得·阿比尔、尤瓦尔·诺亚·哈拉里、张亚勤、兰雪、沙伊·沙列夫-施瓦茨、吉莉安·哈德菲尔德等。2023。 [在快速进展时代管理 AI 风险](https://arxiv.org/abs/2310.17688)。*ArXiv 预印本*，abs/2310.17688。

+   Bjerva 等 (2020) 约翰内斯·比耶尔瓦、尼基塔·布塔尼、贝赫扎德·戈尔尚、王-张澄、和伊莎贝尔·奥根斯坦。2020。 [SubjQA: 主观性和评论理解数据集](https://doi.org/10.18653/v1/2020.emnlp-main.442)。见 *2020 年自然语言处理实证方法会议（EMNLP）论文集*，第 5480–5494 页，在线。计算语言学协会。

+   Borgeaud 等 (2022) Sebastian Borgeaud、Arthur Mensch、Jordan Hoffmann、Trevor Cai、Eliza Rutherford、Katie Millican、George Bm Van Den Driessche、Jean-Baptiste Lespiau、Bogdan Damoc、Aidan Clark 等。2022. 通过从万亿个标记中检索来改进语言模型。在 *国际机器学习大会* 上，页码 2206–2240。PMLR。

+   Borsos 等 (2023) Zalán Borsos、Raphaël Marinier、Damien Vincent、Eugene Kharitonov、Olivier Pietquin、Matt Sharifi、Dominik Roblek、Olivier Teboul、David Grangier、Marco Tagliasacchi 等。2023. Audiolm：一种用于音频生成的语言建模方法。*IEEE/ACM 音频、语音和语言处理交易*。

+   Brown 等 (2020) Tom B Brown、Benjamin Mann、Nick Ryder、Melanie Subbiah、Jared Kaplan、Prafulla Dhariwal、Arvind Neelakantan、Pranav Shyam、Girish Sastry、Amanda Askell、Sandhini Agarwal、Ariel Herbert-Voss、Gretchen Krueger、Tom Henighan、Rewon Child、Aditya Ramesh、Daniel M Ziegler、Jeffrey Wu、Clemens Winter、Christopher Hesse、Mark Chen、Eric Sigler、Mateusz Litwin、Scott Gray、Benjamin Chess、Jack Clark、Christopher Berner、Sam McCandlish、Alec Radford、Ilya Sutskever 和 Dario Amodei。2020. [语言模型是少样本学习者](https://proceedings.neurips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html)。在 *NeurIPS 2020 神经信息处理系统年会：第 33 届神经信息处理系统大会，2020 年 12 月 6-12 日，虚拟* 上。

+   Caines 等 (2023) Andrew Caines、Luca Benedetto、Shiva Taslimipoor、Christopher Davis、Yuan Gao、Oeistein Andersen、Zheng Yuan、Mark Elliott、Russell Moore、Christopher Bryant 等。2023. [大型语言模型在语言教学和评估技术中的应用](https://arxiv.org/abs/2307.08393)。*ArXiv 预印本*，abs/2307.08393。

+   Carlini 等 (2023) Nicholas Carlini、Matthew Jagielski、Christopher A Choquette-Choo、Daniel Paleka、Will Pearce、Hyrum Anderson、Andreas Terzis、Kurt Thomas 和 Florian Tramèr。2023. [毒化网络规模训练数据集是实际可行的](https://arxiv.org/abs/2302.10149)。*ArXiv 预印本*，abs/2302.10149。

+   Chang 和 Bergen (2023) Tyler A Chang 和 Benjamin K Bergen. 2023. [语言模型行为：综合调查](https://arxiv.org/abs/2303.11504)。*ArXiv 预印本*，abs/2303.11504。

+   Cheang 等 (2023) Chi Cheang、Hou Chan、Derek Wong、Xuebo Liu、Zhaocong Li、Yanming Sun、Shudong Liu 和 Lidia Chao。2023. 语言模型能否泛化到未来的数据？对文本摘要的实证分析。在 *2023 年自然语言处理实证方法会议论文集* 上，页码 16205–16217。

+   Chen 和 Shu (2023a) Canyu Chen 和 Kai Shu. 2023a. 大型语言模型生成的虚假信息能被检测出来吗？在 *NeurIPS 2023 指令调优与指令跟随研讨会* 上。

+   陈和舒（2023b）陈灿宇和舒凯。2023b。[在 LLMs 时代对抗虚假信息：机遇与挑战](https://arxiv.org/abs/2311.05656)。*ArXiv 预印本*，abs/2311.05656。

+   陈等（2022）陈宏婷、张明杰和崔恩硕。2022。[丰富的知识来源带来复杂的知识冲突：重新校准模型以反映冲突证据](https://arxiv.org/abs/2210.13701)。*ArXiv 预印本*，abs/2210.13701。

+   陈等（2023a）陈江杰、施伟、傅子全、程思杰、李雷和肖杨华。2023a。[说清楚你想表达的！大语言模型对负面常识知识评价过于积极](https://arxiv.org/abs/2305.05976)。*ArXiv 预印本*，abs/2305.05976。

+   陈等（2023b）陈佳伟、林宏宇、韩宪培和孙乐。2023b。[基准测试大语言模型在检索增强生成中的表现](https://arxiv.org/abs/2309.01431)。*ArXiv 预印本*，abs/2309.01431。

+   陈等（2023c）梁陈、杨邓、雅涛边、泽宇秦、冰哲吴、蔡达生和黄锦辉。2023c。超越事实性：大语言模型作为知识生成器的综合评估。发表于*2023 年自然语言处理经验方法会议论文集*，第 6325–6341 页。

+   陈等（2021）陈文虎、王欣怡和王威廉·杨。2021。[一个回答时间敏感问题的数据集](https://arxiv.org/abs/2108.06314)。*ArXiv 预印本*，abs/2108.06314。

+   陈等（2023）I 陈、斯特菲·陈、石齐、袁伟哲、冯克华、周春婷、何俊贤、格雷厄姆·纽比格、刘鹏飞等。2023。[Factool：生成式 AI 中的事实性检测—一个增强工具框架，用于多任务和多领域场景](https://arxiv.org/abs/2307.13528)。*ArXiv 预印本*，abs/2307.13528。

+   张和林（2023）张俊贤和林健满。2023。Factllama：利用外部知识优化指令跟随语言模型以进行自动化事实核查。发表于*2023 年亚太信号与信息处理协会年会及会议（APSIPA ASC）*，第 846–853 页。IEEE。

+   庄等（2023）庄永生、谢雨佳、罗洪银、金云、詹姆斯·格拉斯和何鹏程。2023。[Dola：通过对比层解码提高大语言模型的事实性](https://arxiv.org/abs/2309.03883)。*ArXiv 预印本*，abs/2309.03883。

+   丘赫泰等（2024）比拉尔·丘赫泰、艾伦·库尼和尼尔·南达。2024。[总结事实：LLMs 中事实回忆的加性机制](https://arxiv.org/abs/2402.07321)。*ArXiv 预印本*，abs/2402.07321。

+   Clark 等（2019）Christopher Clark、Kenton Lee、Ming-Wei Chang、Tom Kwiatkowski、Michael Collins 和 Kristina Toutanova。2019 年。[BoolQ：探索自然是/否问题的惊人难度](https://doi.org/10.18653/v1/N19-1300)。在*2019 年北美计算语言学协会年会：人类语言技术会议，第 1 卷（长篇和短篇论文）*的论文集中，第 2924–2936 页，明尼阿波利斯，明尼苏达州。计算语言学协会。

+   Cui 等（2020）Leyang Cui、Sijie Cheng、Yu Wu 和 Yue Zhang。2020 年。[BERT 是否通过常识知识解决常识任务](https://arxiv.org/abs/2008.03945)。*ArXiv 预印本*，abs/2008.03945。

+   De Cao 等（2021）Nicola De Cao、Wilker Aziz 和 Ivan Titov。2021 年。《编辑语言模型中的事实知识》。在*2021 年自然语言处理经验方法会议论文集*中，第 6491–6506 页。

+   De Lange 等（2021）Matthias De Lange、Rahaf Aljundi、Marc Masana、Sarah Parisot、Xu Jia、Aleš Leonardis、Gregory Slabaugh 和 Tinne Tuytelaars。2021 年。《持续学习调查：在分类任务中抗拒遗忘》。*IEEE 模式分析与机器智能汇刊*，44(7):3366–3385。

+   Dementieva 和 Panchenko（2021）Daryna Dementieva 和 Alexander Panchenko。2021 年。[跨语言证据改善单语言虚假新闻检测](https://doi.org/10.18653/v1/2021.acl-srw.32)。在*第 59 届计算语言学协会年会及第 11 届国际自然语言处理联合会议：学生研究工作坊*的论文集中，第 310–320 页，在线。计算语言学协会。

+   Dhingra 等（2022）Bhuwan Dhingra、Jeremy R Cole、Julian Martin Eisenschlos、Daniel Gillick、Jacob Eisenstein 和 William W Cohen。2022 年。《时间感知语言模型作为时间知识库》。*计算语言学协会汇刊*，10:257–273。

+   Dhuliawala 等（2023）Shehzaad Dhuliawala、Mojtaba Komeili、Jing Xu、Roberta Raileanu、Xian Li、Asli Celikyilmaz 和 Jason Weston。2023 年。[链式验证减少大语言模型中的幻觉](https://arxiv.org/abs/2309.11495)。*ArXiv 预印本*，abs/2309.11495。

+   Dong 等（2023）Qingxiu Dong、Jingjing Xu、Lingpeng Kong、Zhifang Sui 和 Lei Li。2023 年。《大语言模型的统计知识评估》。在*第 37 届神经信息处理系统大会*上。

+   Du 等（2022a）Li Du、Xiao Ding、Kai Xiong、Ting Liu 和 Bing Qin。2022a 年。《e-care：探索可解释因果推理的新数据集》。在*第 60 届计算语言学协会年会（第 1 卷：长篇论文）*的论文集中，第 432–446 页。

+   Du et al. (2022b) 俞冰杜、安托万·博塞卢特和克里斯托弗·D·曼宁。2022b。对自动化事实验证系统的合成虚假信息攻击。见于*AAAI 人工智能会议论文集*，第 36 卷，页码 10581–10589。

+   Dziri et al. (2021) 诺哈·兹里、安德烈亚·马多托、奥斯马尔·扎伊安和阿维谢克·乔伊·博斯。2021。[神经路径猎手：通过路径基础减少对话系统中的幻觉](https://arxiv.org/abs/2104.08455)。*ArXiv 预印本*，abs/2104.08455。

+   Elazar et al. (2022) 亚奈·艾拉扎、诺拉·卡斯纳、绍利·拉夫福戈尔、阿米尔·费德尔、阿比拉莎·拉维钱德、马里乌斯·莫斯巴赫、约纳坦·贝林科夫、赫尔里希·舒茨和约阿夫·戈德伯格。2022。[测量数据统计对语言模型“事实”预测的因果效应](https://arxiv.org/abs/2207.14251)。*ArXiv 预印本*，abs/2207.14251。

+   Elazar et al. (2021) 亚奈·艾拉扎、诺拉·卡斯纳、绍利·拉夫福戈尔、阿比拉莎·拉维钱德、爱德华·霍维、赫尔里希·舒茨和约阿夫·戈德伯格。2021。测量和改进预训练语言模型的一致性。*计算语言学协会会刊*，9：1012–1031。

+   Elsahar et al. (2018) 哈迪·艾尔萨赫、帕夫洛斯·沃吉奥克利斯、阿斯伦·雷马西、克里斯托夫·格拉维耶、乔纳森·赫雷、弗雷德里克·拉福雷斯特和埃琳娜·辛珀尔。2018。[T-REx：自然语言与知识库三元组的大规模对齐](https://aclanthology.org/L18-1544)。见于*第十一届语言资源与评估国际会议（LREC 2018）*，日本宫崎。欧洲语言资源协会（ELRA）。

+   Fan et al. (2018) 安吉拉·范、迈克·刘易斯和扬·多芬。2018。[层次神经故事生成](https://doi.org/10.18653/v1/P18-1082)。见于*第 56 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，页码 889–898，澳大利亚墨尔本。计算语言学协会。

+   Feng et al. (2023) 张银锋、马伟涛、余伟江、黄磊、王浩天、陈强龙、彭伟华、冯小城、秦冰等。2023。[知识与大型语言模型整合的趋势：方法、基准和应用的调查与分类](https://arxiv.org/abs/2311.05876)。*ArXiv 预印本*，abs/2311.05876。

+   Ferrara (2023) 埃米利奥·费拉拉。2023。[反人类的生成人工智能：生成人工智能和大型语言模型的恶意应用](https://arxiv.org/abs/2310.00737)。*ArXiv 预印本*，abs/2310.00737。

+   Floridi (2023) 卢西亚诺·弗洛里迪。2023。没有智能的代理：关于 ChatGPT、大型语言模型和其他生成模型。*哲学与技术*，36(1)：15。

+   Fung et al. (2022) 易仁·冯、黄功翔、普雷斯拉夫·纳科夫和季恒。2022。打击虚假信息和应对媒体偏见的前线。见于*第 28 届 ACM SIGKDD 知识发现与数据挖掘大会论文集*，页码 4790–4791。

+   Gao et al. (2023a) Luyu Gao, Zhuyun Dai, Panupong Pasupat, Anthony Chen, Arun Tejasvi Chaganty, Yicheng Fan, Vincent Zhao, Ni Lao, Hongrae Lee, Da-Cheng Juan, 等. 2023a. Rarr：研究和修订语言模型的输出，利用语言模型。在*第 61 届计算语言学协会年会（第 1 卷：长论文）*中，页码 16477–16508。

+   Gao et al. (2023b) Yunfan Gao, Yun Xiong, Xinyu Gao, Kangxiang Jia, Jinliu Pan, Yuxi Bi, Yi Dai, Jiawei Sun, 和 Haofen Wang. 2023b. [检索增强生成的大型语言模型：综述](https://arxiv.org/abs/2312.10997)。*ArXiv 预印本*，abs/2312.10997。

+   Gekhman et al. (2023) Zorik Gekhman, Jonathan Herzig, Roee Aharoni, Chen Elkind, 和 Idan Szpektor. 2023. [Trueteacher：使用大型语言模型学习事实一致性评估](https://arxiv.org/abs/2305.11171)。*ArXiv 预印本*，abs/2305.11171。

+   Geva et al. (2021) Mor Geva, Daniel Khashabi, Elad Segal, Tushar Khot, Dan Roth, 和 Jonathan Berant. 2021. 亚里士多德使用过笔记本电脑吗？一个隐性推理策略的问答基准。*计算语言学协会会刊*，9:346–361。

+   Goldstein et al. (2023) Josh A Goldstein, Girish Sastry, Micah Musser, Renee DiResta, Matthew Gentzel, 和 Katerina Sedova. 2023. [生成语言模型与自动化影响操作：新兴威胁及潜在缓解措施](https://arxiv.org/abs/2301.04246)。*ArXiv 预印本*，abs/2301.04246。

+   Greshake et al. (2023) Kai Greshake, Sahar Abdelnabi, Shailesh Mishra, Christoph Endres, Thorsten Holz, 和 Mario Fritz. 2023. 比你要求的更多：对应用集成大型语言模型的新型提示注入威胁的全面分析。*arXiv 电子印刷版*，页码 arXiv–2302。

+   Grosse et al. (2023) Roger Grosse, Juhan Bae, Cem Anil, Nelson Elhage, Alex Tamkin, Amirhossein Tajdini, Benoit Steiner, Dustin Li, Esin Durmus, Ethan Perez, 等. 2023. [通过影响函数研究大型语言模型的泛化能力](https://arxiv.org/abs/2308.03296)。*ArXiv 预印本*，abs/2308.03296。

+   Guo et al. (2022) Zhijiang Guo, Michael Schlichtkrull, 和 Andreas Vlachos. 2022. 自动化事实核查的综述。*计算语言学协会会刊*，10:178–206。

+   Guu et al. (2020) Kelvin Guu, Kenton Lee, Zora Tung, Panupong Pasupat, 和 Ming-Wei Chang. 2020. [检索增强语言模型预训练](http://proceedings.mlr.press/v119/guu20a.html)。在*第 37 届国际机器学习会议论文集，ICML 2020，2020 年 7 月 13-18 日，虚拟会议*中，第 119 卷*机器学习研究论文集*，页码 3929–3938。PMLR。

+   Hase et al. (2023) Peter Hase, Mona Diab, Asli Celikyilmaz, Xian Li, Zornitsa Kozareva, Veselin Stoyanov, Mohit Bansal 和 Srinivasan Iyer。2023。衡量、更新和可视化语言模型中事实信念的方法。在*第 17 届欧洲计算语言学分会年会论文集*，第 2706-2723 页。

+   He et al. (2021) Tianxing He, Jun Liu, Kyunghyun Cho, Myle Ott, Bing Liu, James Glass 和 Fuchun Peng。2021。[分析开放域对话响应模型预训练微调中的遗忘问题](https://aclanthology.org/2021.eacl-main.95)。在*第 16 届欧洲计算语言学分会年会论文集：主要卷*，第 1121–1133 页，在线。计算语言学协会。

+   Hermann et al. (2015) Karl Moritz Hermann, Tomás Kociský, Edward Grefenstette, Lasse Espeholt, Will Kay, Mustafa Suleyman 和 Phil Blunsom。2015。[教机器阅读和理解](https://proceedings.neurips.cc/paper/2015/hash/afdec7005cc9f14302cd0474fd0f3c96-Abstract.html)。在*第 28 届神经信息处理系统大会：2015 年神经信息处理系统年会，2015 年 12 月 7-12 日，加拿大魁北克蒙特利尔*，第 1693-1701 页。

+   Hoffmann et al. (2022) Jordan Hoffmann, Sebastian Borgeaud, Arthur Mensch, Elena Buchatskaya, Trevor Cai, Eliza Rutherford, Diego de Las Casas, Lisa Anne Hendricks, Johannes Welbl, Aidan Clark 等。2022。[训练计算优化的大型语言模型](https://arxiv.org/abs/2203.15556)。*ArXiv 预印本*，abs/2203.15556。

+   Holtzman et al. (2020) Ari Holtzman, Jan Buys, Li Du, Maxwell Forbes 和 Yejin Choi. 2020 年。[神经文本退化的奇异案例](https://openreview.net/forum?id=rygGQyrFvH)。在*第八届国际学习表示会议，ICLR 2020，埃塞俄比亚亚的斯亚巴巴，2020 年 4 月 26-30 日*。OpenReview.net。

+   Hong et al. (2023) Giwon Hong, Jeonghwan Kim, Junmo Kang, Sung-Hyon Myaeng 和 Joyce Jiyoung Whang。2023。[识别和回答：用鉴别器减轻检索增强模型中误信息的影响](https://arxiv.org/abs/2305.01579)。*ArXiv 预印本*，abs/2305.01579。

+   Hsu et al. (2021) Cheng Hsu, Cheng-Te Li, Diego Saez-Trumper 和 Yi-Zhan Hsu。2021。维基矛盾：检测维基百科上的自相矛盾文章。在*2021 年 IEEE 国际大数据会议（Big Data）*，第 427–436 页。IEEE。

+   Hu et al. (2023) Xuming Hu, Junzhe Chen, Xiaochuan Li, Yufei Guo, Lijie Wen, Philip S. Yu 和 Zhijiang Guo。2023。[大型语言模型了解事实吗？](https://doi.org/10.48550/ARXIV.2310.05177)*CoRR*，abs/2310.05177。

+   Hu et al. (2024) Xuming Hu, Xiaochuan Li, Junzhe Chen, Yinghui Li, Yangning Li, Xiaoguang Li, Yasheng Wang, Qun Liu, Lijie Wen, Philip S. Yu 和 Zhijiang Guo。2024。[评估生成式搜索引擎对敌对事实问题的鲁棒性](https://doi.org/10.48550/ARXIV.2403.12077)。*CoRR*，abs/2403.12077。

+   Huang 等人（2023）Lei Huang、Weijiang Yu、Weitao Ma、Weihong Zhong、Zhangyin Feng、Haotian Wang、Qianglong Chen、Weihua Peng、Xiaocheng Feng、Bing Qin 等。2023. [关于大语言模型中的幻觉的调查：原理、分类、挑战和未解问题](https://arxiv.org/abs/2311.05232)。*ArXiv 预印本*，abs/2311.05232。

+   Ilharco 等人（2022）Gabriel Ilharco、Marco Tulio Ribeiro、Mitchell Wortsman、Suchin Gururangan、Ludwig Schmidt、Hannaneh Hajishirzi 和 Ali Farhadi。2022. [用任务算术编辑模型](https://arxiv.org/abs/2212.04089)。*ArXiv 预印本*，abs/2212.04089。

+   Jang 等人（2022）Joel Jang、Seonghyeon Ye、Changho Lee、Sohee Yang、Joongbo Shin、Janghoon Han、Gyeonghun Kim 和 Minjoon Seo。2022. Temporalwiki：一个用于训练和评估不断演变的语言模型的终身基准。在*2022 年自然语言处理经验方法会议论文集*，第 6237–6250 页。

+   Jang 等人（2021）Joel Jang、Seonghyeon Ye、Sohee Yang、Joongbo Shin、Janghoon Han、KIM Gyeonghun、Stanley Jungkyu Choi 和 Minjoon Seo。2021. 朝着语言模型的持续知识学习发展。在*学习表征国际会议*。

+   Jang 和 Lukasiewicz（2023）Myeongjun Erik Jang 和 Thomas Lukasiewicz。2023. [通过从词典学习概念角色来提高语言模型的意义理解和一致性](https://arxiv.org/abs/2310.15541)。*ArXiv 预印本*，abs/2310.15541。

+   Jawahar 等人（2020）Ganesh Jawahar、Muhammad Abdul-Mageed 和 Laks Lakshmanan，V.S. 2020. [自动检测机器生成文本：关键调查](https://doi.org/10.18653/v1/2020.coling-main.208)。在*第 28 届国际计算语言学会议论文集*，第 2296–2309 页，西班牙巴塞罗那（在线）。国际计算语言学委员会。

+   Jawahar 等人（2019）Ganesh Jawahar、Benoît Sagot 和 Djamé Seddah。2019. [BERT 对语言结构的学习情况如何？](https://doi.org/10.18653/v1/P19-1356) 在*第 57 届计算语言学协会年会论文集*，第 3651–3657 页，意大利佛罗伦萨。计算语言学协会。

+   Ji 等人（2023）Ziwei Ji、Nayeon Lee、Rita Frieske、Tiezheng Yu、Dan Su、Yan Xu、Etsuko Ishii、Ye Jin Bang、Andrea Madotto 和 Pascale Fung。2023. 自然语言生成中的幻觉调查。*ACM 计算机调查*，55(12)：1–38。

+   Jiang 等人（2023）Bohan Jiang、Zhen Tan、Ayushi Nirmal 和 Huan Liu。2023. [虚假信息检测：在大语言模型时代演变中的挑战](https://arxiv.org/abs/2309.15847)。*ArXiv 预印本*，abs/2309.15847。

+   Jin 等人（2024a）Zhuoran Jin、Pengfei Cao、Yubo Chen、Kang Liu、Xiaojian Jiang、Jiexin Xu、Qiuxia Li 和 Jun Zhao。2024a. [知识的拔河：探索和解决检索增强语言模型中的知识冲突](https://arxiv.org/abs/2402.14409)。*ArXiv 预印本*，abs/2402.14409。

+   Jin 等（2024b）Zhuoran Jin、Pengfei Cao、Hongbang Yuan、Yubo Chen、Jiexin Xu、Huaijun Li、Xiaojian Jiang、Kang Liu 和 Jun Zhao。2024b 年。[切断头部结束冲突：一种解释和缓解语言模型知识冲突的机制](https://arxiv.org/abs/2402.18154) *ArXiv 预印本*，abs/2402.18154。

+   Joshi 等（2017）Mandar Joshi、Eunsol Choi、Daniel Weld 和 Luke Zettlemoyer。2017 年。[TriviaQA：用于阅读理解的大规模远程监督挑战数据集](https://doi.org/10.18653/v1/P17-1147)。在*第 55 届计算语言学协会年会论文集（第 1 卷：长篇论文）*中，页面 1601–1611，加拿大温哥华。计算语言学协会。

+   Ju 等（2022）Chen Ju、Tengda Han、Kunhao Zheng、Ya Zhang 和 Weidi Xie。2022 年。为高效的视频理解提示视觉语言模型。在*欧洲计算机视觉大会*中，页面 105–124。Springer。

+   Kaddour 等（2023）Jean Kaddour、Joshua Harris、Maximilian Mozes、Herbie Bradley、Roberta Raileanu 和 Robert McHardy。2023 年。[大型语言模型的挑战与应用](https://arxiv.org/abs/2307.10169) *ArXiv 预印本*，abs/2307.10169。

+   Kandpal 等（2023）Nikhil Kandpal、Haikang Deng、Adam Roberts、Eric Wallace 和 Colin Raffel。2023 年。大型语言模型在学习长尾知识方面的困难。在*国际机器学习会议*中，页面 15696–15707。PMLR。

+   Kang 和 Choi（2023）Cheongwoong Kang 和 Jaesik Choi。2023 年。[共现对大型语言模型事实知识的影响](https://arxiv.org/abs/2310.08256) *ArXiv 预印本*，abs/2310.08256。

+   Kaplan 等（2020）Jared Kaplan、Sam McCandlish、Tom Henighan、Tom B. Brown、Benjamin Chess、Rewon Child、Scott Gray、Alec Radford、Jeffrey Wu 和 Dario Amodei。2020 年。[神经语言模型的规模定律](http://arxiv.org/abs/2001.08361)。*CoRR*，abs/2001.08361。

+   Karpukhin 等（2020）Vladimir Karpukhin、Barlas Oguz、Sewon Min、Patrick Lewis、Ledell Wu、Sergey Edunov、Danqi Chen 和 Wen-tau Yih。2020 年。[密集段落检索用于开放域问答](https://doi.org/10.18653/v1/2020.emnlp-main.550)。在*2020 年自然语言处理实证方法会议（EMNLP）*中，页面 6769–6781，在线。计算语言学协会。

+   Kasai 等（2022）Jungo Kasai、Keisuke Sakaguchi、Yoichi Takahashi、Ronan Le Bras、Akari Asai、Xinyan Yu、Dragomir Radev、Noah A Smith、Yejin Choi 和 Kentaro Inui。2022 年。[实时问答：现在的答案是什么？](https://arxiv.org/abs/2207.13332) *ArXiv 预印本*，abs/2207.13332。

+   Kidd 和 Birhane（2023）Celeste Kidd 和 Abeba Birhane。2023 年。人工智能如何扭曲人类信念。*Science*，380(6651):1222–1223。

+   Ko et al. (2022) Miyoung Ko, Ingyu Seong, Hwaran Lee, Joonsuk Park, Minsuk Chang, 和 Minjoon Seo. 2022. [Claimdiff: 比较和对比争议问题的主张](https://arxiv.org/abs/2205.12221). *ArXiv 预印本*, abs/2205.12221.

+   Kočiský et al. (2018) Tomáš Kočiský, Jonathan Schwarz, Phil Blunsom, Chris Dyer, Karl Moritz Hermann, Gábor Melis, 和 Edward Grefenstette. 2018. [NarrativeQA 阅读理解挑战](https://doi.org/10.1162/tacl_a_00023). *计算语言学协会会刊*, 6:317–328.

+   Kumar and Shah (2018) Srijan Kumar 和 Neil Shah. 2018. [网络和社交媒体上的虚假信息：调查](https://arxiv.org/abs/1804.08559). *ArXiv 预印本*, abs/1804.08559.

+   Kwiatkowski et al. (2019) Tom Kwiatkowski, Jennimaria Palomaki, Olivia Redfield, Michael Collins, Ankur Parikh, Chris Alberti, Danielle Epstein, Illia Polosukhin, Jacob Devlin, Kenton Lee, Kristina Toutanova, Llion Jones, Matthew Kelcey, Ming-Wei Chang, Andrew M. Dai, Jakob Uszkoreit, Quoc Le, 和 Slav Petrov. 2019. [自然问题：问答研究的基准](https://doi.org/10.1162/tacl_a_00276). *计算语言学协会会刊*, 7:452–466.

+   Lam et al. (2022) Tsz Kin Lam, Eva Hasler, 和 Felix Hieber. 2022. [分析影响函数在神经机器翻译中用于实例特定数据过滤的使用](https://arxiv.org/abs/2210.13281). *ArXiv 预印本*, abs/2210.13281.

+   Lazaridou et al. (2022) Angeliki Lazaridou, Elena Gribovskaya, Wojciech Stokowiec, 和 Nikolai Grigorev. 2022. [通过少量提示的互联网增强语言模型用于开放领域问答](https://arxiv.org/abs/2203.05115). *ArXiv 预印本*, abs/2203.05115.

+   Lazaridou et al. (2021) Angeliki Lazaridou, Adhi Kuncoro, Elena Gribovskaya, Devang Agrawal, Adam Liska, Tayfun Terzi, Mai Gimenez, Cyprien de Masson d’Autume, Tomas Kocisky, Sebastian Ruder 等. 2021. 注意差距：评估神经语言模型的时间泛化能力。*神经信息处理系统进展*, 34:29348–29363.

+   Lee et al. (2022a) Kyungjae Lee, Wookje Han, Seung-won Hwang, Hwaran Lee, Joonsuk Park, 和 Sang-Woo Lee. 2022a. 即插即用的适应方法用于持续更新的 QA。在 *计算语言学协会会议成果：ACL 2022*, 页 438–447.

+   Lee et al. (2022b) Nayeon Lee, Wei Ping, Peng Xu, Mostofa Patwary, Pascale N Fung, Mohammad Shoeybi, 和 Bryan Catanzaro. 2022b. 增强真实性的语言模型用于开放式文本生成。*神经信息处理系统进展*, 35:34586–34599.

+   Leite et al. (2023) João A Leite, Olesya Razuvayevskaya, Kalina Bontcheva, 和 Carolina Scarton. 2023. [通过 LLM 预测的可信度信号和弱监督检测虚假信息](https://arxiv.org/abs/2309.07601). *ArXiv 预印本*, abs/2309.07601.

+   Lewis et al. (2020) Patrick S. H. Lewis, Ethan Perez, Aleksandra Piktus, Fabio Petroni, Vladimir Karpukhin, Naman Goyal, Heinrich Küttler, Mike Lewis, Wen-tau Yih, Tim Rocktäschel, Sebastian Riedel, 和 Douwe Kiela. 2020. [检索增强生成用于知识密集型 NLP 任务](https://proceedings.neurips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html). 发表在 *神经信息处理系统进展 33：神经信息处理系统 2020 年年会，NeurIPS 2020，2020 年 12 月 6-12 日，虚拟*。

+   Li et al. (2022a) Daliang Li, Ankit Singh Rawat, Manzil Zaheer, Xin Wang, Michal Lukasik, Andreas Veit, Felix Yu, 和 Sanjiv Kumar. 2022a. [具有可控工作记忆的大型语言模型](https://arxiv.org/abs/2211.05110). *ArXiv 预印本*, abs/2211.05110。

+   Li et al. (2023a) Jierui Li, Vipul Raheja, 和 Dhruv Kumar. 2023a. [Contradoc：理解文档中的自我矛盾](https://arxiv.org/abs/2311.09182). *ArXiv 预印本*, abs/2311.09182。

+   Li et al. (2023b) Junnan Li, Dongxu Li, Silvio Savarese, 和 Steven Hoi. 2023b. Blip-2：通过冻结的图像编码器和大型语言模型来引导语言-图像预训练。发表于 *国际机器学习会议*, 页码 19730–19742. PMLR。

+   Li et al. (2023c) Kenneth Li, Oam Patel, Fernanda Viégas, Hanspeter Pfister, 和 Martin Wattenberg. 2023c. [推理时间干预：从语言模型中引出真实答案](https://arxiv.org/abs/2306.03341). *ArXiv 预印本*, abs/2306.03341。

+   Li et al. (2022b) Shaobo Li, Xiaoguang Li, Lifeng Shang, Zhenhua Dong, Chengjie Sun, Bingquan Liu, Zhenzhou Ji, Xin Jiang, 和 Qun Liu. 2022b. [预训练语言模型如何捕捉事实知识？一种因果启发分析](https://arxiv.org/abs/2203.16747). *ArXiv 预印本*, abs/2203.16747。

+   Li et al. (2022c) Xiang Lisa Li, Ari Holtzman, Daniel Fried, Percy Liang, Jason Eisner, Tatsunori Hashimoto, Luke Zettlemoyer, 和 Mike Lewis. 2022c. [对比解码：将开放式文本生成视为优化](https://arxiv.org/abs/2210.15097). *ArXiv 预印本*, abs/2210.15097。

+   Li et al. (2023d) Xiang Lisa Li, Vaishnavi Shrivastava, Siyan Li, Tatsunori Hashimoto, 和 Percy Liang. 2023d. [基准测试和改进语言模型生成器-验证器一致性](https://arxiv.org/abs/2310.01846). *ArXiv 预印本*, abs/2310.01846。

+   Li et al. (2023e) Yinheng Li, Shaofei Wang, Han Ding, 和 Hang Chen. 2023e. 大型语言模型在金融中的应用：一项综述。发表于 *第四届 ACM 国际金融人工智能会议论文集*, 页码 374–382。

+   Li et al. (2023f) Zhoubo Li, Ningyu Zhang, Yunzhi Yao, Mengru Wang, Xi Chen, 和 Huajun Chen. 2023f. [揭示大型语言模型知识编辑的陷阱](https://arxiv.org/abs/2310.02129). *ArXiv 预印本*, abs/2310.02129。

+   Lin 等人（2022）**斯蒂芬妮·林**、**雅各布·希尔顿** 和 **欧温·埃文斯**。2022。Truthfulqa：衡量模型如何模拟人类虚假信息。在 *第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 3214–3252 页。

+   Liska 等人（2022）**亚当·利斯卡**、**托马斯·科西基**、**艾琳娜·格里博夫斯卡娅**、**泰芬·特尔齐**、**厄伦·塞泽内尔**、**德万格·阿格拉瓦尔**、**D’Autume Cyprien De Masson**、**蒂姆·斯科尔特斯**、**曼齐尔·扎希尔**、**苏珊娜·杨** 等人。2022。Streamingqa：问答模型在知识随时间适应的基准。在 *国际机器学习会议*，第 13604–13622 页。PMLR。

+   Liu 等人（2023a）**彭飞·刘**、**韦哲·袁**、**金兰·傅**、**郑宝·姜**、**林弘晃** 和 **格雷厄姆·纽比格**。2023a。预训练、提示和预测：自然语言处理中的提示方法系统调查。 *ACM 计算调查*，55(9)：1–35。

+   Liu 等人（2023b）**易刘**、**格磊·邓**、**岳康·李**、**凯龙·王**、**天伟·张**、**叶磅·刘**、**浩宇·王**、**严正** 和 **杨刘**。2023b。 [对 LLM 集成应用的提示注入攻击](https://arxiv.org/abs/2306.05499)。 *ArXiv 预印本*，abs/2306.05499。

+   Longpre 等人（2021）**谢恩·朗普雷**、**卡尔提克·佩里塞特拉**、**安东尼·陈**、**尼基尔·拉梅什**、**克里斯·杜布瓦** 和 **萨米尔·辛格**。2021。基于实体的知识冲突在问答中的表现。在 *2021 年自然语言处理实证方法会议论文集*，第 7052–7063 页。

+   Luu 等人（2021）**凯尔文·卢**、**丹尼尔·卡沙比**、**苏钦·古鲁拉根**、**卡里什玛·曼迪亚姆** 和 **诺亚·A·史密斯**。2021。 [时间不等人！对时间错位的分析和挑战](https://arxiv.org/abs/2111.07408)。 *ArXiv 预印本*，abs/2111.07408。

+   Mallen 等人（2022）**亚历克斯·马伦**、**浅井明理**、**维克多·钟**、**拉贾尔希·达斯**、**哈娜赫·哈吉什尔齐** 和 **丹尼尔·卡沙比**。2022。 [何时不信任语言模型：调查参数化和非参数化记忆的有效性和局限性](https://arxiv.org/abs/2212.10511)。 *ArXiv 预印本*，abs/2212.10511。

+   Mallen 等人（2023）**亚历克斯·马伦**、**浅井明理**、**维克多·钟**、**拉贾尔希·达斯**、**丹尼尔·卡沙比** 和 **哈娜赫·哈吉什尔齐**。2023。何时不信任语言模型：调查参数化和非参数化记忆的有效性。在 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 9802–9822 页。

+   Manakul 等人（2023）**波萨维·马纳库尔**、**阿迪安·刘西** 和 **马克·JF·盖尔斯**。2023。 [Selfcheckgpt: 无资源黑箱幻觉检测用于生成大型语言模型](https://arxiv.org/abs/2303.08896)。 *ArXiv 预印本*，abs/2303.08896。

+   Margatina 等人（2023）**凯特里娜·马尔加蒂娜**、**帅王**、**尤加尔希·维亚斯**、**内哈·安娜·约翰**、**亚辛·贝纳吉巴** 和 **米格尔·巴列斯特罗斯**。2023。 [面向时间概念漂移的掩码语言模型的动态基准测试](https://arxiv.org/abs/2302.12297)。 *ArXiv 预印本*，abs/2302.12297。

+   Martin et al. (2024) Lauren Martin, Nick Whitehouse, Stephanie Yiu, Lizzie Catterson, 和 Rivindu Perera. 2024. [更好地调用 GPT，比较大型语言模型与律师](https://arxiv.org/abs/2401.16212)。*ArXiv 预印本*，abs/2401.16212。

+   Massarelli et al. (2020) Luca Massarelli, Fabio Petroni, Aleksandra Piktus, Myle Ott, Tim Rocktäschel, Vassilis Plachouras, Fabrizio Silvestri, 和 Sebastian Riedel. 2020. [解码策略如何影响生成文本的可验证性](https://doi.org/10.18653/v1/2020.findings-emnlp.22)。在 *计算语言学协会会议论文集：EMNLP 2020*，第 223–235 页，在线。计算语言学协会。

+   Meel and Vishwakarma (2020) Priyanka Meel 和 Dinesh Kumar Vishwakarma. 2020. 假新闻、谣言、社交媒体和网络中的信息污染：当代的前沿技术、挑战与机遇调查。*专家系统与应用*，153:112986。

+   Menczer et al. (2023) Filippo Menczer, David Crandall, Yong-Yeol Ahn, 和 Apu Kapadia. 2023. 解决 AI 生成的非真实内容的危害。*自然机器智能*，5(7):679–680。

+   Meng et al. (2022) Kevin Meng, David Bau, Alex Andonian, 和 Yonatan Belinkov. 2022. 定位和编辑 GPT 中的事实关联。*神经信息处理系统进展*，35:17359–17372。

+   Merity et al. (2017) Stephen Merity, Caiming Xiong, James Bradbury, 和 Richard Socher. 2017. [指针哨兵混合模型](https://openreview.net/forum?id=Byj72udxe)。在 *第五届国际学习表示会议，ICLR 2017，法国图卢兹，2017 年 4 月 24-26 日，会议记录*。OpenReview.net。

+   Milano et al. (2023) Silvia Milano, Joshua A McGrane, 和 Sabina Leonelli. 2023. 大型语言模型挑战未来高等教育。*自然机器智能*，5(4):333–334。

+   Mitchell et al. (2021) Eric Mitchell, Charles Lin, Antoine Bosselut, Chelsea Finn, 和 Christopher D Manning. 2021. [大规模快速模型编辑](https://arxiv.org/abs/2110.11309)。*ArXiv 预印本*，abs/2110.11309。

+   Mitchell et al. (2022) Eric Mitchell, Joseph J Noh, Siyan Li, William S Armstrong, Ananth Agarwal, Patrick Liu, Chelsea Finn, 和 Christopher D Manning. 2022. [通过自然语言推理增强预训练语言模型的自一致性和性能](https://arxiv.org/abs/2211.11875)。*ArXiv 预印本*，abs/2211.11875。

+   Mündler et al. (2023) Niels Mündler, Jingxuan He, Slobodan Jenko, 和 Martin Vechev. 2023. [大型语言模型的自我矛盾幻觉：评估、检测和缓解](https://arxiv.org/abs/2305.15852)。*ArXiv 预印本*，abs/2305.15852。

+   Naveed et al. (2023) Humza Naveed, Asad Ullah Khan, Shi Qiu, Muhammad Saqib, Saeed Anwar, Muhammad Usman, Nick Barnes, 和 Ajmal Mian. 2023. [大型语言模型的全面概述](https://arxiv.org/abs/2307.06435)。*ArXiv 预印本*，abs/2307.06435。

+   Neeman 等人（2022）Ella Neeman, Roee Aharoni, Or Honovich, Leshem Choshen, Idan Szpektor, 和 Omri Abend。2022。 [Disentqa：通过反事实问答解开参数和上下文知识的纠缠](https://arxiv.org/abs/2211.05655)。 *ArXiv 预印本*，abs/2211.05655。

+   Nickerson（1998）Raymond S Nickerson。1998。确认偏差：多种伪装下的普遍现象。 *一般心理学评论*，2(2):175–220。

+   Ohmer 等人（2023）Xenia Ohmer, Elia Bruni, 和 Dieuwke Hupkes。2023。形式与意义的分离：使用自洽性量化多重感知下的任务理解。 *CoRR*。

+   Onoe 等人（2023）Yasumasa Onoe, Michael JQ Zhang, Shankar Padmanabhan, Greg Durrett, 和 Eunsol Choi。2023。 [大语言模型能从描述中学习新实体吗？传播注入知识的挑战](https://arxiv.org/abs/2305.01651)。 *ArXiv 预印本*，abs/2305.01651。

+   OpenAI（2023）OpenAI。2023。 [ChatGPT](https://openai.com/chatgpt)。

+   OpenAI（2024）OpenAI。2024。 [GPT-4 技术报告](http://arxiv.org/abs/2303.08774)。

+   Ouyang 等人（2022）Long Ouyang, Jeffrey Wu, Xu Jiang, Diogo Almeida, Carroll Wainwright, Pamela Mishkin, Chong Zhang, Sandhini Agarwal, Katarina Slama, Alex Ray, 等人。2022。训练语言模型以跟随指令与人类反馈。 *神经信息处理系统进展*，35:27730–27744。

+   Pan 等人（2023a）Liangming Pan, Wenhu Chen, Min-Yen Kan, 和 William Yang Wang。2023a。通过注入虚假信息攻击开放领域问答。 *IJCNLP-AACL. ACL*。

+   Pan 等人（2022）Xiaoman Pan, Wenlin Yao, Hongming Zhang, Dian Yu, Dong Yu, 和 Jianshu Chen。2022。知识背景：迈向有知识的半参数语言模型。发表于 *第十一届国际学习表示会议*。

+   Pan 等人（2023b）Yikang Pan, Liangming Pan, Wenhu Chen, Preslav Nakov, Min-Yen Kan, 和 William Yang Wang。2023b。 [大语言模型中的虚假信息污染风险](https://arxiv.org/abs/2305.13661)。 *ArXiv 预印本*，abs/2305.13661。

+   Peng 等人（2023）Baolin Peng, Michel Galley, Pengcheng He, Hao Cheng, Yujia Xie, Yu Hu, Qiuyuan Huang, Lars Liden, Zhou Yu, Weizhu Chen, 等人。2023。 [检查你的事实并再试一次：通过外部知识和自动反馈改进大语言模型](https://arxiv.org/abs/2302.12813)。 *ArXiv 预印本*，abs/2302.12813。

+   Perez 等人（2022）Ethan Perez, Sam Ringer, Kamilė Lukošiūtė, Karina Nguyen, Edwin Chen, Scott Heiner, Craig Pettit, Catherine Olsson, Sandipan Kundu, Saurav Kadavath, 等人。2022。 [通过模型生成评估发现语言模型行为](https://arxiv.org/abs/2212.09251)。 *ArXiv 预印本*，abs/2212.09251。

+   Petroni et al. (2019) Fabio Petroni、Tim Rocktäschel、Sebastian Riedel、Patrick Lewis、Anton Bakhtin、Yuxiang Wu 和 Alexander Miller. 2019. [语言模型作为知识库？](https://doi.org/10.18653/v1/D19-1250) 见于 *2019 年自然语言处理实证方法会议和第 9 届国际联合自然语言处理会议（EMNLP-IJCNLP）论文集*，第 2463–2473 页，中国香港。计算语言学协会。

+   Pielka et al. (2022) Maren Pielka、Felix Rode、Lisa Pucknat、Tobias Deußer 和 Rafet Sifa. 2022. 对基于机器学习的矛盾检测模型的语言学研究：实证分析与未来展望。见于 *2022 年第 21 届 IEEE 国际机器学习与应用会议（ICMLA）*，第 1649–1653 页。IEEE。

+   Pinter 和 Elhadad (2023) Yuval Pinter 和 Michael Elhadad. 2023. 用勺子排空海洋：我们应该编辑模型吗？见于 *计算语言学协会发现：EMNLP 2023*，第 15164–15172 页。

+   Qi et al. (2023) Jirui Qi、Raquel Fernández 和 Arianna Bisazza. 2023. [多语言模型中的事实知识的跨语言一致性](https://arxiv.org/abs/2310.10378)。*ArXiv 预印本*，abs/2310.10378。

+   Qian et al. (2023) Cheng Qian、Xinran Zhao 和 Sherry Tongshuang Wu. 2023. [“合并冲突！” 探索外部干扰对参数知识图的影响](https://arxiv.org/abs/2309.08594)。*ArXiv 预印本*，abs/2309.08594。

+   Rabinovich et al. (2023) Ella Rabinovich、Samuel Ackerman、Orna Raz、Eitan Farchi 和 Ateret Anaby-Tavor. 2023. [通过语义一致性预测大型语言模型的问答性能](https://arxiv.org/abs/2311.01152)。*ArXiv 预印本*，abs/2311.01152。

+   Raj et al. (2023) Harsh Raj、Vipul Gupta、Domenic Rosati 和 Subhabrata Majumdar. 2023. [确保大型语言模型可靠性的语义一致性](https://arxiv.org/abs/2308.09138)。*ArXiv 预印本*，abs/2308.09138。

+   Raj et al. (2022) Harsh Raj、Domenic Rosati 和 Subhabrata Majumdar. 2022. [通过语义一致性测量大型语言模型的可靠性](https://arxiv.org/abs/2211.05853)。*ArXiv 预印本*，abs/2211.05853。

+   Rajpurkar et al. (2018) Pranav Rajpurkar、Robin Jia 和 Percy Liang. 2018. [知道你不知道什么：SQuAD 的不可回答问题](https://doi.org/10.18653/v1/P18-2124)。见于 *第 56 届计算语言学协会年会（第 2 卷：短篇论文）*，第 784–789 页，澳大利亚墨尔本。计算语言学协会。

+   Rajpurkar et al. (2016) Pranav Rajpurkar、Jian Zhang、Konstantin Lopyrev 和 Percy Liang. 2016. [SQuAD：用于机器理解文本的 100,000+个问题](https://doi.org/10.18653/v1/D16-1264)。见于 *2016 年自然语言处理实证方法会议论文集*，第 2383–2392 页，美国德克萨斯州奥斯汀。计算语言学协会。

+   Roberts et al. (2020) Adam Roberts, Colin Raffel, 和 Noam Shazeer. 2020. [你能将多少知识装入语言模型的参数中？](https://doi.org/10.18653/v1/2020.emnlp-main.437) 载于*2020 年自然语言处理实证方法会议（EMNLP）论文集*，页码 5418–5426，在线。计算语言学协会。

+   Rogers et al. (2020) Anna Rogers, Olga Kovaleva, 和 Anna Rumshisky. 2020. [BERT 学：我们对 BERT 如何工作的了解](https://doi.org/10.1162/tacl_a_00349)。*计算语言学协会会刊*，8:842–866。

+   Schick et al. (2023) Timo Schick, Jane Dwivedi-Yu, Roberto Dessì, Roberta Raileanu, Maria Lomeli, Luke Zettlemoyer, Nicola Cancedda, 和 Thomas Scialom. 2023. [Toolformer：语言模型可以自学使用工具](https://arxiv.org/abs/2302.04761)。*ArXiv 预印本*，abs/2302.04761。

+   Schlichtkrull et al. (2023) Michael Schlichtkrull, Zhijiang Guo, 和 Andreas Vlachos. 2023. [Averitec：一个用于现实世界声明验证的数据集，来自网络证据](http://papers.nips.cc/paper_files/paper/2023/hash/cd86a30526cd1aff61d6f89f107634e4-Abstract-Datasets_and_Benchmarks.html)。载于*神经信息处理系统进展 36：2023 年神经信息处理系统年会（NeurIPS 2023），美国路易斯安那州新奥尔良，2023 年 12 月 10 日至 16 日*。

+   Sharir et al. (2020) Or Sharir, Barak Peleg, 和 Yoav Shoham. 2020. [训练 NLP 模型的成本：简明概述](https://arxiv.org/abs/2004.08900)。*ArXiv 预印本*，abs/2004.08900。

+   Sharma et al. (2023) Mrinank Sharma, Meg Tong, Tomasz Korbak, David Duvenaud, Amanda Askell, Samuel R Bowman, Newton Cheng, Esin Durmus, Zac Hatfield-Dodds, Scott R Johnston, et al. 2023. [了解语言模型中的谄媚行为](https://arxiv.org/abs/2310.13548)。*ArXiv 预印本*，abs/2310.13548。

+   Shi et al. (2023a) Weijia Shi, Xiaochuang Han, Mike Lewis, Yulia Tsvetkov, Luke Zettlemoyer, 和 Scott Wen-tau Yih. 2023a. [信任你的证据：在上下文感知解码中减少幻觉](https://arxiv.org/abs/2305.14739)。*ArXiv 预印本*，abs/2305.14739。

+   Shi et al. (2023b) Weijia Shi, Sewon Min, Maria Lomeli, Chunting Zhou, Margaret Li, Victoria Lin, Noah A Smith, Luke Zettlemoyer, Scott Yih, 和 Mike Lewis. 2023b. [上下文预训练：超越文档边界的语言建模](https://arxiv.org/abs/2310.10638)。*ArXiv 预印本*，abs/2310.10638。

+   Shi et al. (2023c) Weijia Shi, Sewon Min, Michihiro Yasunaga, Minjoon Seo, Rich James, Mike Lewis, Luke Zettlemoyer, 和 Wen-tau Yih. 2023c. [Replug：检索增强的黑箱语言模型](https://arxiv.org/abs/2301.12652)。*ArXiv 预印本*，abs/2301.12652。

+   Shu et al. (2017) Kai Shu, Amy Sliva, Suhang Wang, Jiliang Tang, 和 Huan Liu. 2017. 社交媒体上的假新闻检测：一种数据挖掘视角。*ACM SIGKDD 探索通讯*，19(1):22–36。

+   Shui 等人（2023）Ruihao Shui, Yixin Cao, Xiang Wang 和 Tat-Seng Chua. 2023. [大规模语言模型在法律判决预测中的综合评估](https://arxiv.org/abs/2310.11761)。*ArXiv 预印本*，abs/2310.11761。

+   Shuster 等人（2021）Kurt Shuster, Spencer Poff, Moya Chen, Douwe Kiela 和 Jason Weston. 2021. 检索增强减少对话中的幻觉。在 *计算语言学协会年会：EMNLP 2021*，第 3784–3803 页。

+   Singhal 等人（2022）Karan Singhal, Shekoofeh Azizi, Tao Tu, S Sara Mahdavi, Jason Wei, Hyung Won Chung, Nathan Scales, Ajay Tanwani, Heather Cole-Lewis, Stephen Pfohl 等人. 2022. [大型语言模型编码临床知识](https://arxiv.org/abs/2212.13138)。*ArXiv 预印本*，abs/2212.13138。

+   Sinitsin 等人（2020）Anton Sinitsin, Vsevolod Plokhotnyuk, Dmitriy Pyrkin, Sergei Popov 和 Artem Babenko. 2020. [可编辑神经网络](https://openreview.net/forum?id=HJedXaEtvS)。在 *第 8 届国际学习表征会议（ICLR 2020），埃塞俄比亚亚的斯亚贝巴，2020 年 4 月 26-30 日*。OpenReview.net。

+   Smith（2023）Craig S. Smith. 2023. [大型模型的代价 – 没有免费的 AI 午餐](https://www.forbes.com/sites/craigsmith/2023/09/08/what-large-models-cost-you--there-is-no-free-ai-lunch/?sh=3ae2bf574af7)。

+   Solaiman 等人（2023）Irene Solaiman, Zeerak Talat, William Agnew, Lama Ahmad, Dylan Baker, Su Lin Blodgett, Hal Daumé III, Jesse Dodge, Ellie Evans, Sara Hooker 等人. 2023. [评估生成型 AI 系统在系统与社会中的社会影响](https://arxiv.org/abs/2306.05949)。*ArXiv 预印本*，abs/2306.05949。

+   Spitale 等人（2023）Giovanni Spitale, Nikola Biller-Andorno 和 Federico Germani. 2023. [AI 模型 GPT-3（不）比人类更能告知我们](https://arxiv.org/abs/2301.11924)。*ArXiv 预印本*，abs/2301.11924。

+   Tan 等人（2024）Hexiang Tan, Fei Sun, Wanli Yang, Yuanzhuo Wang, Qi Cao 和 Xueqi Cheng. 2024. [被生成的上下文所盲目：语言模型如何将生成的和检索的上下文融合用于开放域问答？](https://arxiv.org/abs/2401.11911) *ArXiv 预印本*，abs/2401.11911。

+   Tang 等人（2023）Ruixiang Tang, Yu-Neng Chuang 和 Xia Hu. 2023. [检测 LLM 生成文本的科学](https://arxiv.org/abs/2303.07205)。*ArXiv 预印本*，abs/2303.07205。

+   Tenney 等人（2019）Ian Tenney, Dipanjan Das 和 Ellie Pavlick. 2019. [BERT 重新发现经典的 NLP 流水线](https://doi.org/10.18653/v1/P19-1452)。在 *第 57 届计算语言学协会年会会议录*，第 4593–4601 页，意大利佛罗伦萨。计算语言学协会。

+   Thirunavukarasu 等人（2023）Arun James Thirunavukarasu, Darren Shu Jeng Ting, Kabilan Elangovan, Laura Gutierrez, Ting Fang Tan 和 Daniel Shu Wei Ting. 2023. 大型语言模型在医学中的应用。*自然医学*，29(8)：1930–1940。

+   Touvron 等人（2023）Hugo Touvron, Louis Martin, Kevin Stone, Peter Albert, Amjad Almahairi, Yasmine Babaei, Nikolay Bashlykov, Soumya Batra, Prajjwal Bhargava, Shruti Bhosale 等。2023。[Llama 2：开放基础和微调聊天模型](https://arxiv.org/abs/2307.09288)。*ArXiv 预印本*，abs/2307.09288。

+   Trivedi 等人（2022）Harsh Trivedi, Niranjan Balasubramanian, Tushar Khot, 和 Ashish Sabharwal。2022。Musique：通过单跳问题组合实现多跳问题。*计算语言学协会会刊*，10:539–554。

+   Turpin 等人（2023）Miles Turpin, Julian Michael, Ethan Perez, 和 Samuel R Bowman。2023。[语言模型并不总是说出它们的想法：链式思考提示中的不忠实解释](https://arxiv.org/abs/2305.04388)。*ArXiv 预印本*，abs/2305.04388。

+   Vergho 等人（2024）Tyler Vergho, Jean-Francois Godbout, Reihaneh Rabbany, 和 Kellin Pelrine。2024。[比较 gpt-4 和开源语言模型在误信息缓解中的表现](https://arxiv.org/abs/2401.06920)。*ArXiv 预印本*，abs/2401.06920。

+   Vu 等人（2023）Tu Vu, Mohit Iyyer, Xuezhi Wang, Noah Constant, Jerry Wei, Jason Wei, Chris Tar, Yun-Hsuan Sung, Denny Zhou, Quoc Le 等。2023。[Freshllms：通过搜索引擎增强刷新大型语言模型](https://arxiv.org/abs/2310.03214)。*ArXiv 预印本*，abs/2310.03214。

+   Wan 等人（2024）Alexander Wan, Eric Wallace, 和 Dan Klein。2024。[语言模型发现什么证据是令人信服的？](https://arxiv.org/abs/2402.11782) *ArXiv 预印本*，abs/2402.11782。

+   Wang 等人（2019）Cunxiang Wang, Shuailong Liang, Yue Zhang, Xiaonan Li, 和 Tian Gao。2019。[它有意义吗？为什么？对意义构建和解释的初步研究](https://doi.org/10.18653/v1/P19-1393)。在*第 57 届计算语言学协会年会论文集*，第 4020–4026 页，佛罗伦萨，意大利。计算语言学协会。

+   Wang 等人（2023a）Cunxiang Wang, Xiaoze Liu, Yuanhao Yue, Xiangru Tang, Tianhang Zhang, Cheng Jiayang, Yunzhi Yao, Wenyang Gao, Xuming Hu, Zehan Qi, Yidong Wang, Linyi Yang, Jindong Wang, Xing Xie, Zheng Zhang, 和 Yue Zhang。2023a。[大语言模型中的真实性调查：知识、检索和领域特异性](http://arxiv.org/abs/2310.07521)。

+   Wang 等人（2023b）Cunxiang Wang, Zhikun Xu, Qipeng Guo, Xiangkun Hu, Xuefeng Bai, Zheng Zhang, 和 Yue Zhang。2023b。[利用抽象意义表示进行开放领域问答](https://doi.org/10.18653/v1/2023.findings-acl.131)。在*计算语言学协会年会论文集：ACL 2023*，第 2083–2096 页，多伦多，加拿大。计算语言学协会。

+   Wang 等 (2023c) Cunxiang Wang, Haofei Yu, 和 Yue Zhang. 2023c. [RFiD: Towards rational fusion-in-decoder for open-domain question answering](https://doi.org/10.18653/v1/2023.findings-acl.155)。在 *Findings of the Association for Computational Linguistics: ACL 2023* 中，第 2473–2481 页，多伦多，加拿大。计算语言学协会。

+   Wang 等 (2023d) Fei Wang, Wenjie Mo, Yiwei Wang, Wenxuan Zhou, 和 Muhao Chen. 2023d. [A causal view of entity bias in (large) language models](https://arxiv.org/abs/2305.14695)。*ArXiv 预印本*，abs/2305.14695。

+   Wang 等 (2024a) Hongru Wang, Wenyu Huang, Yang Deng, Rui Wang, Zezhong Wang, Yufei Wang, Fei Mi, Jeff Z. Pan, 和 Kam-Fai Wong. 2024a. [Unims-rag: A unified multi-source retrieval-augmented generation for personalized dialogue systems](http://arxiv.org/abs/2401.13256)。

+   Wang 等 (2023e) Hongru Wang, Lingzhi Wang, Yiming Du, Liang Chen, Jingyan Zhou, Yufei Wang, 和 Kam-Fai Wong. 2023e. [A survey of the evolution of language model-based dialogue systems](http://arxiv.org/abs/2311.16789)。

+   Wang 等 (2024b) Hongru Wang, Boyang Xue, Baohang Zhou, Tianhua Zhang, Cunxiang Wang, Guanhua Chen, Huimin Wang, 和 Kam fai Wong. 2024b. [Self-dc: When to retrieve and when to generate? self divide-and-conquer for compositional unknown questions](http://arxiv.org/abs/2402.13514)。

+   Wang 等 (2023f) Jiaan Wang, Yunlong Liang, Zengkui Sun, Yuxuan Cao, 和 Jiarong Xu. 2023f. [Cross-lingual knowledge editing in large language models](https://arxiv.org/abs/2309.08952)。*ArXiv 预印本*，abs/2309.08952。

+   Wang 等 (2023g) Liyuan Wang, Xingxing Zhang, Qian Li, Mingtian Zhang, Hang Su, Jun Zhu, 和 Yi Zhong. 2023g. 融入神经启发适应性以实现人工智能的持续学习。*Nature Machine Intelligence*，第 1–13 页。

+   Wang 等 (2023h) Yike Wang, Shangbin Feng, Heng Wang, Weijia Shi, Vidhisha Balachandran, Tianxing He, 和 Yulia Tsvetkov. 2023h. [Resolving knowledge conflicts in large language models](https://arxiv.org/abs/2310.00935)。*ArXiv 预印本*，abs/2310.00935。

+   Wei 等 (2023) Jerry Wei, Da Huang, Yifeng Lu, Denny Zhou, 和 Quoc V Le. 2023. [Simple synthetic data reduces sycophancy in large language models](https://arxiv.org/abs/2308.03958)。*ArXiv 预印本*，abs/2308.03958。

+   Weidinger 等 (2021) Laura Weidinger, John Mellor, Maribeth Rauh, Conor Griffin, Jonathan Uesato, Po-Sen Huang, Myra Cheng, Mia Glaese, Borja Balle, Atoosa Kasirzadeh, 等. 2021. [Ethical and social risks of harm from language models](https://arxiv.org/abs/2112.04359)。*ArXiv 预印本*，abs/2112.04359。

+   Weidinger 等 (2023) Laura Weidinger, Maribeth Rauh, Nahema Marchal, Arianna Manzini, Lisa Anne Hendricks, Juan Mateos-Garcia, Stevie Bergman, Jackie Kay, Conor Griffin, Ben Bariach, 等. 2023. [Sociotechnical safety evaluation of generative ai systems](https://arxiv.org/abs/2310.11986)。*ArXiv 预印本*，abs/2310.11986。

+   Weller et al. (2022) Orion Weller, Aleem Khan, Nathaniel Weir, Dawn Lawrie 和 Benjamin Van Durme. 2022. [防御开放领域问答中的虚假信息攻击](https://arxiv.org/abs/2212.10002)。*ArXiv 预印本*，abs/2212.10002。

+   Williams et al. (2018) Adina Williams, Nikita Nangia 和 Samuel Bowman. 2018. [用于通过推理理解句子的广覆盖挑战语料库](https://doi.org/10.18653/v1/N18-1101)。发表于*2018 年北美计算语言学协会年会：人类语言技术，第 1 卷（长篇论文）*，第 1112–1122 页，路易斯安那州新奥尔良市。计算语言学协会。

+   Wu et al. (2022) Xiangcheng Wu, Xi Niu 和 Ruhani Rahman. 2022. 文本中的矛盾拓扑分析。发表于*第 45 届国际 ACM SIGIR 信息检索研究与发展会议论文集*，第 2478–2483 页。

+   Wu et al. (2023) Yusong Wu, Ke Chen, Tianyu Zhang, Yuchen Hui, Taylor Berg-Kirkpatrick 和 Shlomo Dubnov. 2023. 大规模对比语言-音频预训练与特征融合和关键词到字幕增强。发表于*ICASSP 2023-2023 IEEE 国际声学、语音与信号处理会议（ICASSP）*，第 1–5 页。IEEE。

+   Xie et al. (2023) Jian Xie, Kai Zhang, Jiangjie Chen, Renze Lou 和 Yu Su. 2023. [适应性变色龙还是固执的树懒：揭示大型语言模型在知识冲突中的行为](https://arxiv.org/abs/2305.13300)。*ArXiv 预印本*，abs/2305.13300。

+   Xu et al. (2022) Nan Xu, Fei Wang, Bangzheng Li, Mingtao Dong 和 Muhao Chen. 2022. [你的模型是否合理分类实体？ 诊断和缓解实体类型中的虚假相关性](https://arxiv.org/abs/2205.12640)。*ArXiv 预印本*，abs/2205.12640。

+   Xu et al. (2023) Rongwu Xu, Brian S Lin, Shujian Yang, Tianqi Zhang, Weiyan Shi, Tianwei Zhang, Zhixuan Fang, Wei Xu 和 Han Qiu. 2023. [地球是平的因为……：通过说服性对话调查大语言模型对虚假信息的信念](https://arxiv.org/abs/2312.09085)。*ArXiv 预印本*，abs/2312.09085。

+   Xue et al. (2024) Boyang Xue, Hongru Wang, Weichao Wang, Rui Wang, Sheng Wang, Zeming Liu 和 Kam-Fai Wong. 2024. [大规模语言模型中的多语言信心估计综合研究](http://arxiv.org/abs/2402.13606)。

+   Xue et al. (2023) Boyang Xue, Weichao Wang, Hongru Wang, Fei Mi, Rui Wang, Yasheng Wang, Lifeng Shang, Xin Jiang, Qun Liu 和 Kam-Fai Wong. 2023. 通过知识增强和对齐提高知识驱动对话系统的事实一致性。发表于*计算语言学协会发现：EMNLP 2023*，第 7829–7844 页。

+   Yao et al. (2023) Yunzhi Yao, Peng Wang, Bozhong Tian, Siyuan Cheng, Zhoubo Li, Shumin Deng, Huajun Chen 和 Ningyu Zhang. 2023. [编辑大型语言模型：问题、方法与机会](https://arxiv.org/abs/2305.13172)。*ArXiv 预印本*，abs/2305.13172。

+   易等（2023）景伟·易、跃琦·谢、斌·朱、基根·海恩斯、埃姆雷·基西曼、光中·孙、星·谢和方钊·吴。2023 年。[对大型语言模型的间接提示注入攻击进行基准测试和防御](https://arxiv.org/abs/2312.14197)。*ArXiv 预印本*，abs/2312.14197。

+   应等（2023）佳豪·应、易鑫·曹、凯·熊、义东·何、龙·崔和永斌·刘。2023 年。[直观还是依赖？调查大型语言模型对冲突提示的鲁棒性](https://arxiv.org/abs/2309.17415)。*ArXiv 预印本*，abs/2309.17415。

+   Yu 等（2022）温浩·余、丹·伊特尔、朔航·王、逸崇·徐、明轩·巨、苏玛亚·萨尼亚尔、成光·朱、迈克尔·曾和孟江。2022 年。[生成而非检索：大型语言模型是强大的上下文生成器](https://arxiv.org/abs/2209.10063)。*ArXiv 预印本*，abs/2209.10063。

+   曾等（2022）澳汉·曾、小刘、郑晓·杜、子涵·王、汉宇·赖、明·丁、卓毅·杨、义凡·徐、文迪·郑、小夏等。2022 年。Glm-130b：一个开放的双语预训练模型。见于*第十一届国际学习表示会议*。

+   张等（2023a）博宇·张、洪阳·杨、天宇·周、穆罕默德·阿里·巴巴尔和肖阳·刘。2023a。通过检索增强的大型语言模型提升金融情感分析。见于*第四届 ACM 国际金融人工智能会议论文集*，第 349–356 页。

+   张等（2023b）杭·张、辛·李和李东·冰。2023b。Video-llama：一种用于视频理解的指令调优音视频语言模型。见于*2023 年自然语言处理实证方法会议：系统演示文稿*，第 543–553 页。

+   张等（2023c）佳鑫·张、卓航·李、卡玛莉卡·达斯、布拉德利·A·马林和斯里查兰·库马尔。2023c。[Sac³：通过语义感知交叉检查一致性在黑箱语言模型中可靠地检测幻觉](https://arxiv.org/abs/2311.01740)。*ArXiv 预印本*，abs/2311.01740。

+   张和崔（2021）迈克尔·JQ·张和恩索尔·崔。2021 年。[Situatedqa：将额外语言环境纳入 QA](https://arxiv.org/abs/2109.06157)。*ArXiv 预印本*，abs/2109.06157。

+   张和崔（2023）迈克尔·JQ·张和恩索尔·崔。2023 年。[通过丢弃过时的事实减轻时间错位](https://arxiv.org/abs/2305.14824)。*ArXiv 预印本*，abs/2305.14824。

+   张等（2020）义哲·张、思齐·孙、米歇尔·加利、严纯·陈、克里斯·布罗克特、向·高、剑锋·高、晶晶·刘和比尔·多兰。2020 年。[DIALOGPT：大规模生成预训练对话响应生成](https://doi.org/10.18653/v1/2020.acl-demos.30)。见于*第 58 届计算语言学协会年会：系统演示文稿*，第 270–278 页，在线。计算语言学协会。

+   Zhang et al. (2023d) Yue Zhang, Yafu Li, Leyang Cui, Deng Cai, Lemao Liu, Tingchen Fu, Xinting Huang, Enbo Zhao, Yu Zhang, Yulong Chen, Longyue Wang, Anh Tuan Luu, Wei Bi, Freda Shi, 和 Shuming Shi. 2023d. [AI 海洋中的海妖之歌: 大语言模型中的幻觉调查](http://arxiv.org/abs/2309.01219)。

+   Zhang et al. (2023e) Yunxiang Zhang, Muhammad Khalifa, Lajanugen Logeswaran, Moontae Lee, Honglak Lee, 和 Lu Wang. 2023e. [合并生成和检索知识用于开放域问答](https://arxiv.org/abs/2310.14393)。*ArXiv 预印本*，abs/2310.14393。

+   Zhao et al. (2023a) Haiyan Zhao, Hanjie Chen, Fan Yang, Ninghao Liu, Huiqi Deng, Hengyi Cai, Shuaiqiang Wang, Dawei Yin, 和 Mengnan Du. 2023a. 大语言模型的可解释性: 一项综述。*ACM 智能系统与技术期刊*。

+   Zhao et al. (2023b) Yukun Zhao, Lingyong Yan, Weiwei Sun, Guoliang Xing, Chong Meng, Shuaiqiang Wang, Zhicong Cheng, Zhaochun Ren, 和 Dawei Yin. 2023b. [了解 llms 不知道的东西: 一种简单但有效的自我检测方法](https://arxiv.org/abs/2310.17918)。*ArXiv 预印本*，abs/2310.17918。

+   Zheng et al. (2022) Chujie Zheng, Jinfeng Zhou, Yinhe Zheng, Libiao Peng, Zhen Guo, Wenquan Wu, Zhengyu Niu, Hua Wu, 和 Minlie Huang. 2022. [Cdconv: 中文对话中的矛盾检测基准](https://arxiv.org/abs/2210.08511)。*ArXiv 预印本*，abs/2210.08511。

+   Zhong et al. (2023) Zexuan Zhong, Zhengxuan Wu, Christopher D Manning, Christopher Potts, 和 Danqi Chen. 2023. [Mquake: 通过多跳问题评估语言模型中的知识编辑](https://arxiv.org/abs/2305.14795)。*ArXiv 预印本*，abs/2305.14795。

+   Zhou et al. (2023a) Chunting Zhou, Pengfei Liu, Puxin Xu, Srini Iyer, Jiao Sun, Yuning Mao, Xuezhe Ma, Avia Efrat, Ping Yu, Lili Yu, 等. 2023a. [Lima: 对齐的少即是多](https://arxiv.org/abs/2305.11206)。*ArXiv 预印本*，abs/2305.11206。

+   Zhou et al. (2023b) Hongjian Zhou, Boyang Gu, Xinyu Zou, Yiru Li, Sam S Chen, Peilin Zhou, Junling Liu, Yining Hua, Chengfeng Mao, Xian Wu, 等. 2023b. [医学中大语言模型的综述: 进展、应用和挑战](https://arxiv.org/abs/2311.05112)。*ArXiv 预印本*，abs/2311.05112。

+   Zhou et al. (2023c) Jiawei Zhou, Yixuan Zhang, Qianni Luo, Andrea G Parker, 和 Munmun De Choudhury. 2023c. 合成谎言: 理解 AI 生成的虚假信息并评估算法和人工解决方案。收录于 *2023 年计算机系统人因会议 (CHI)*，第 1–20 页。

+   Zhou et al. (2023d) Wenxuan Zhou, Sheng Zhang, Hoifung Poon, 和 Muhao Chen. 2023d. [面向大语言模型的上下文忠实提示](https://arxiv.org/abs/2303.11315)。*ArXiv 预印本*，abs/2303.11315。

+   Zhuang et al. (2023) Yuchen Zhuang, Yue Yu, Kuan Wang, Haotian Sun, 和 Chao Zhang. 2023. [Toolqa: 一个用于外部工具问答的 llm 数据集](https://arxiv.org/abs/2306.13304)。*ArXiv 预印本*，abs/2306.13304。

+   Zubiaga 等人（2018）Arkaitz Zubiaga, Ahmet Aker, Kalina Bontcheva, Maria Liakata 和 Rob Procter。2018 年。《社交媒体中的谣言检测与解决：综述》。*ACM 计算调查 (CSUR)*，51(2)：1–36。

| 参考文献 | 模型 | 数据集 | 定量结果 |
| --- | --- | --- | --- |
| *上下文记忆冲突* |
| Pan 等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib137)) | ChatGPT | NQ-1500 和 CovidNews | 上下文中的虚假信息可能导致性能显著下降（最高达 87%）。 |
| Xie 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib195)) | ChatGPT, GPT-4, PaLM2, Qwen, Llama2 和 Vicuna | POPQA 和 STRATEGYQA | 对于基于实体替换的反记忆，只有 ChatGPT, GPT-4 和 PaLM2 选择参数记忆的概率超过 60%。对于基于生成的反记忆，所有模型选择上下文知识的概率均超过 80%。 |
| Xu 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib197)) | ChatGPT, GPT-4, Llama2 和 Vicuna | Farm, BoolQ, TruthfulQA 和 NQ | 在多轮对话中，随着反记忆上下文数量的增加，LLMs 信念改变的累积比例从 20.7% 到 78.2% 不等。 |
| *跨上下文冲突* |
| Jin 等人 ([2024a](https://arxiv.org/html/2403.08319v2#bib.bib76)) | ChatGPT, Llama2, Baichuan2, FLAN-UL2 和 FLAN-T5 | NQ, TriviaQA, PopQA 和 MuSiQue | 面对冲突证据时，ChatGPT 的召回率下降最少，但仍超过 10%。 |
| Chen 等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib23)) | ChatGPT, ChatGLM, Vicuna, Qwen 和 BELLE | RGB | 随着证据中的噪声增加，模型的性能将逐渐下降。当噪声率超过 0.8 时，所有模型的性能下降超过 20%。 |
| Li 等人 ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib99)) | GPT-4, ChatGPT, PaLM2 和 Llama2 | CONTRADOC | 面对自我矛盾的文档时，gpt4 识别矛盾发生的概率超过 70%，而其他模型低于 50%。 |
| *内部记忆冲突* |
| Mündler 等人 ([2023](https://arxiv.org/html/2403.08319v2#bib.bib126)) | GPT-4, ChatGPT, Llama2 和 Vicuna | MainTestSet | LLMs 生成矛盾内容的概率在 15.7% 到 22.9% 之间。更强大的模型生成的矛盾结果较少。 |
| Zhao 等人 ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib214)) | ChatGPT, GPT-4, Vicuna 和 Llama2 | FaVIQ, ComQA, GSM-8K, SVAMP, ARCChallenge 和 CommonsenseQA | 他们的研究发现，即使是 GPT-4 在 FaVIQ 中也会表现出 32% 的不一致率。 |

表 2：各种类型知识冲突对定量结果的影响比较。

## 附录 A 附录

### A.1 定量分析与比较

在调查论文的背景下，虽然包括定量结果和有关知识冲突对各种类型冲突的影响及不同减轻策略的性能比较的分析是有益的，但这并不是严格要求。我们认识到进行此类定量实验的*复杂性和不切实际性*，尤其是由于在行为分析中使用了不同的数据集，以及 LLMs 在不同知识截止快照中的固有知识差异，如[表 1](https://arxiv.org/html/2403.08319v2#S1.T1 "Table 1 ‣ 1 Introduction ‣ Knowledge Conflicts for LLMs: A Survey")中详细描述的。

此外，在减轻策略部分建立“公平”比较本身就面临一系列挑战，因为目标的多样性受到各种假定先验的影响，例如上下文的感知准确性或固有知识，如主文本中所讨论的。尽管存在这些复杂性，我们选择通过汇总各种论文的现有评估来呈现定量结果。然而，*必须小心对待这种分析，认识到原作者可能使用了不同的数据集、LLM 变体，甚至追求了不同的目标*。

### A.2 知识冲突影响的定量结果

对三种类型的知识冲突影响的定量结果比较见于[表 2](https://arxiv.org/html/2403.08319v2#A0.T2 "Table 2 ‣ Knowledge Conflicts for LLMs: A Survey")。我们挑选了代表性的行为分析文献的结果进行比较。

### A.3 减轻策略有效性的定量结果

| 参考文献 | 模型 | 数据集 | 定量结果 |
| --- | --- | --- | --- |
| *忠于上下文* |
| Shi et al. ([2023a](https://arxiv.org/html/2403.08319v2#bib.bib156)) | Llama, OPT, GPT-Neo 和 FLAN | NQ-SWAP, MemoTrap 和 NQ | 他们的方法使 GPT-Neo 20B 在 Memotrap 上提高了 54.4%，在 NQ-SWAP 上提高了 128%，其中 LLMs 需要遵循给定的上下文。 |
| Zhou et al. ([2023d](https://arxiv.org/html/2403.08319v2#bib.bib220)) | ChatGPT 和 Llama2 | MRC 和 Re-TACRED | 与零样本基础提示相比，他们的提示方法在 GPT-3.5 上减少了 32.2%用于维护 MRC 的参数知识，并减少了 10.9%用于 Re-TACRED。同样，在 Llama2 上，MRC 减少了 39.4%，Re-TACRED 减少了 57.3%。 |
| *辨别虚假信息* |
| Hong et al. ([2023](https://arxiv.org/html/2403.08319v2#bib.bib63)) | ChatGPT 和 FiD | NQ 和 TQA | 作者训练了一个 F1 分数约为 80%的判别器，并利用它来提高模型性能超过 5%。 |
| Pan et al. ([2023b](https://arxiv.org/html/2403.08319v2#bib.bib137)) | ChatGPT | NQ-1500 和 CovidNews | 作者的减轻方法使准确性提高了超过 10%。 |
| *解开来源* |
| Wang et al. ([2023h](https://arxiv.org/html/2403.08319v2#bib.bib187)) | ChatGPT | 知识冲突 | 作者的方法在上下文知识冲突检测上达到了超过 80%的 F1 分数。 |

表 3：各种缓解策略的效果与其目标的定量结果比较。

各种缓解策略的效果在[表 3](https://arxiv.org/html/2403.08319v2#A1.T3 "Table 3 ‣ A.3 Quantitative Results on the Effectiveness of Mitigation Strategies ‣ Appendix A Appendix ‣ Knowledge Conflicts for LLMs: A Survey")中进行了定量比较。需要注意的是，我们的分析仅限于处理*三种主要类型缓解目标*的研究，这些研究在内存冲突的背景下进行。这一选择是经过深思熟虑的，因为在不同冲突类别中的其他类型缓解目标尚未有足够的研究成果来进行有意义的跨方法比较。

生成于 2024 年 6 月 22 日星期六 08:30:59，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
