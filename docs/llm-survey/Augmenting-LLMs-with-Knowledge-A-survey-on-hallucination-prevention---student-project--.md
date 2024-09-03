<!--yml

分类：未分类

日期：2024-09-03 17:31:46

-->

# 用知识增强 LLMs 预防幻觉的调查 — 学生项目 —

> 来源：[`arxiv.org/html/2309.16459`](https://arxiv.org/html/2309.16459)

1.  I 引言

1.  II 背景

    1.  II-A 生成语言模型

    1.  II-B 自回归模型

    1.  II-C 序列到序列模型

    1.  II-D Transformers

    1.  II-E Beam 搜索

    1.  II-F 文本语料库

    1.  II-G 向量数据库

    1.  II-H 密集向量索引

    1.  II-I 三元组知识库

    1.  II-J 图卷积网络

    1.  II-K 关系图卷积网络

1.  III 知识库增强生成

    1.  III-A 检索增强生成 (RAG) ‣ III 知识库增强生成 ‣ 用知识增强 LLMs 预防幻觉的调查 — 学生项目 —")

    1.  [III-B REALM [30]](#S3.SS2 "III-B REALM [30] ‣ III 知识库增强生成 ‣ 用知识增强 LLMs 预防幻觉的调查 — 学生项目 —")

    1.  III-C 解码器中的融合 (FiD) ‣ III 知识库增强生成 ‣ 用知识增强 LLM 对幻觉预防的调查 — 学生项目 —")

    1.  III-D Atlas

    1.  III-E RETRO

    1.  III-F GRAFT-Net

    1.  [III-G PullNet [11]](#S3.SS7 "III-G PullNet [11] ‣ III 知识库增强生成 ‣ 用知识增强 LLM 对幻觉预防的调查 — 学生项目 —")

1.  IV 搜索引擎增强生成

    1.  IV-A 互联网增强对话生成 (IADG) ‣ IV 搜索引擎增强生成 ‣ 用知识增强 LLM 对幻觉预防的调查 — 学生项目 —")

    1.  IV-B SeeKeR

    1.  IV-C LaMDA

1.  V 限制与讨论

1.  VI 结论

\usetikzlibrary

automata,arrows,positioning,calc

# 用知识增强 LLM

关于幻觉预防的调查

— 学生项目 —

Konstantinos Andriopoulos 代尔夫特理工大学

荷兰代尔夫特

A.Konstantinos@student.tudelft.nl    Johan Pouwelse 代尔夫特理工大学

荷兰代尔夫特

J.A.Pouwelse@tudelft.nl

###### 摘要

大型预训练语言模型已展示出在其参数中存储事实知识的能力，并在针对下游自然语言处理任务进行微调时取得了显著成果。然而，这些模型在精确访问和操作知识的能力上仍然受到限制，与任务特定架构相比，在知识密集型任务上的表现存在差异。此外，提供模型决策的来源以及保持世界知识的最新状态仍然是开放的研究前沿。为了解决这些限制，将预训练模型与可微分的显式非参数记忆访问机制整合起来，成为一种有前景的解决方案。本调查深入探讨了增强语言模型（LMs）以访问外部知识源的领域，包括外部知识库和搜索引擎。在遵循预测缺失标记的标准目标的同时，这些增强的 LMs 利用多样的、可能是非参数的外部模块来增强其上下文处理能力，突破了传统语言建模范式。通过对在知识增强的大型语言模型方面的最新进展的探索，本研究总结认为这一新兴研究方向有潜力解决传统 LMs 中的普遍问题，如幻觉、无基础的回应和可扩展性挑战。

## 我们的研究导言

大型语言模型（LLMs）在自然语言处理（NLP）领域带来了显著的进展，并且现在是各种广泛使用的产品的核心，包括 Copilot[1]、Google 的搜索引擎以及更近期的基于 GPT3 的聊天机器人 Chat-GPT[2]。这些模型不仅具有记忆能力，还具备强大的组合能力，在从语言理解到文本生成等任务中表现出前所未有的性能，为更复杂的人机交互开辟了道路。

然而，LLMs 也存在其局限性。它们经常产生看似合理但实际上不正确的预测，这种现象被称为幻觉[3]，导致在各种情境中出现可以避免的错误。此外，LLMs 的许多突破性能力似乎随着模型的可训练参数的规模而扩展。尽管最近的努力已产生了保留能力的较小 LLMs[4]，但训练和维护大型模型的实际问题仍然存在，其中持续学习对于这些模型仍然是一个持续的研究问题[5]。

这些局限性根源于大型语言模型（LLMs）存在的一个根本问题：它们主要用于统计语言建模，依赖于单一的参数模型和相对有限的上下文，通常是前面的”n”个标记。尽管硬件和软件方面有所进步，但大多数模型的上下文大小仍相对较小，相较于所有场景中准确语言建模所需的广泛上下文。因此，实现超越即时上下文的知识存储的必要规模已成为一种需求。

针对这一问题，出现了一种新的研究趋势，逐步脱离传统的统计语言建模范式。一种方法通过结合从外部文档中提取的信息来增强 LLMs 的相关性，从而解决了上下文大小有限的问题[6] [7]。通过为语言模型配备从数据库中检索相关文档的模块，能够在使用更少参数的情况下复制较大 LLMs 的某些能力[8] [9]。

此外，在这一不断发展的领域中，利用结构化知识的先锋模型[10] [11]尤其突出。这些模型利用知识图谱以及支持文档的语料库，通过图卷积神经网络（CNNs）共同处理。通过利用基于图的表示，这些结构化知识增强模型在生成开放领域问题的精准回答方面表现出色。这种对结构化知识的创新使用标志着语言模型的显著进步，展示了研究人员在解决当代 LLMs 局限性方面采用的多样化策略。

值得注意的是，这些方法将生成的模型转变为非参数模型，因为它们现在能够有效地查询外部数据源。

另一种策略是使 LLMs 能够利用外部工具[12]，例如搜索引擎[13] [14] [12]，从而允许它们用模型权重中不包含的重要信息来增强当前上下文。尽管这些努力大多旨在解决 LLMs 的个别不足，但显然，更全面的知识工具整合有可能显著提升这些模型的能力。

鉴于自然语言处理领域的这些最新发展，迫切需要一个全面的增强语言模型分类法以及对技术术语的明确定义，这些术语有时带有不同的解释和意图。

## II 背景

当我们深入探讨如何将外部知识增强大型语言模型（LLMs）时，建立对支撑这一变革性领域的关键概念的基础理解是至关重要的。知识增强策略，如利用知识图谱、采用束搜索技术、利用三元组存储数据库和整合序列到序列模型，构成了先进语言模型的基石。在这一部分，我们将全面探索这些关键概念，揭示它们的意义、方法和相互关系。通过阐明这些基础构建块，我们为深入理解现代 LLM 如何利用外部知识实现前所未有的语言成就铺平道路。

### II-A 生成式语言模型

生成式语言模型被训练来生成新文本，给定一组输入标记。它们通过学习大规模文本语料库中单词和短语之间的统计关系来实现这一点。当给定提示时，生成式模型会尝试生成与其学到的统计模式一致的文本。

自然语言处理领域一些最受欢迎的生成模型包括自回归模型 [15]、变分自编码器（VAEs） [16] 和生成对抗网络（GANs） [17]。在这次文献综述中，我们将主要探讨变换器、自回归模型以及另一种生成式语言模型——序列到序列模型。

### II-B 自回归模型

自回归模型 [15] 是一种用于生成数据序列的神经网络，其中序列中的每个元素都是基于先前生成的元素逐一预测的。换句话说，该模型通过将其预测条件于迄今为止生成的数据来生成数据。自回归模型通常用于文本生成、时间序列预测和语音合成等任务。

自然语言处理领域最著名的自回归模型之一是 GPT（生成式预训练变换器）系列，例如 GPT-2 [18] 和 GPT-3 [2]。这些模型通过根据前面的单词预测句子中的下一个单词来生成文本。它们使用自注意力 [19] 机制来捕捉序列中不同位置单词之间的依赖关系，使其能够生成连贯且上下文相关的文本。

### II-C 序列到序列模型

序列到序列（seq2seq）模型 [20] 预测一个标记在给定词序列中的下一个标记的概率。

它由一个编码器和一个解码器组成。编码器逐步读取输入序列，并生成整个序列的固定维度向量表示。这个向量称为上下文向量，它是输入序列所有有意义信息的表示。上下文向量随后传递给解码器，解码器生成输出序列。

序列到序列模型通常使用最大似然目标进行训练，这意味着它们被训练以生成最可能跟随输入序列的输出序列。总之，seq2seq 模型被设计用于涉及将一个序列转换为另一个序列的任务，通常这些序列的长度和结构有所不同。它们通常应用于机器翻译、文本摘要和问答等任务，在这些任务中，输入和输出序列之间的关系不是纯线性的，或者输入和输出序列的长度可以显著变化。

从这一点开始，我们将序列到序列模型简称为 seq2seq。

### II-D Transformers

Transformer 架构 [19] 标志着自然语言处理领域的一次突破性进展。自其诞生以来，Transformers 已成为各种最先进语言模型的骨干，支撑着许多最新的增强语言模型的发展。

在核心层面上，Transformer 架构通过引入注意力机制彻底革新了序列到序列的建模。与早期的递归神经网络（RNNs）[21] [22] 和卷积神经网络（CNNs）[23] 不同，Transformers 依赖自注意力机制来捕捉序列中元素之间的依赖关系，使其具备高度的并行化能力，并且在处理长距离依赖时效率极高。

该架构由两个主要组件组成：编码器和解码器。编码器处理输入序列，而解码器生成输出序列。每个组件包含多个层，每层包括一个多头自注意力机制和前馈神经网络。这些自注意力机制使 Transformers 能够高效地捕捉上下文信息，使其在理解和生成数据序列的任务中表现尤为出色。

在语言建模的背景下，Transformers 可以适配为仅解码器模型。在仅解码器的 Transformers 中，编码输入序列的编码器组件被移除。这些模型保留了核心的 Transformer 架构，但专注于生成令牌序列，使其特别适合自回归语言建模任务。

仅解码器 Transformer 以自回归方式运行。它们一次生成一个标记，每个标记的预测都基于先前生成的标记。这种自回归方法使它们能够生成连贯且上下文相关的文本。仅解码器 Transformer 在各种文本生成任务中发挥了重要作用，包括机器翻译、文本摘要和文本补全。

自 Transformer 架构引入以来，出现了许多变体和扩展，每一种都针对 NLP 中的特定挑战。这些变体包括诸如 BERT（双向编码器表示的变换器）[24]、GPT（生成式预训练变换器）[18] [2] 和 T5（文本到文本转移变换器）[25] 等模型。许多这些模型为增强语言模型与外部知识奠定了基础，这是最近 NLP 研究中的一个重要话题。

### II-E Beam Search

Beam Search 是一种启发式搜索算法，它通过每一步只扩展 K（束宽）个最有前途的节点来探索图 G。Beam Search 模拟了广度优先搜索的行为。更具体地说，它使用 BFS 创建一个搜索树。在树的每一层，它检查当前层的所有后继节点，只保留前 K 个，同时修剪其他节点。这个过程会重复，直到找到 K 个叶子节点。Beam Search 将返回最大化某个给定评分函数的叶子节点。

在自然语言处理（NLP）的背景下，当使用生成模型时，Beam Search 被用来找到最有可能出现在输入序列`x`之后的序列<math alttext="y=(y_{1},...,y_{n})" class="ltx_Math" display="inline" id="S2.SS5.p2.1.m1.3"><semantics id="S2.SS5.p2.1.m1.3a"><mrow id="S2.SS5.p2.1.m1.3.3" xref="S2.SS5.p2.1.m1.3.3.cmml"><mi id="S2.SS5.p2.1.m1.3.3.4" xref="S2.SS5.p2.1.m1.3.3.4.cmml">y</mi><mo id="S2.SS5.p2.1.m1.3.3.3" xref="S2.SS5.p2.1.m1.3.3.3.cmml">=</mo><mrow id="S2.SS5.p2.1.m1.3.3.2.2" xref="S2.SS5.p2.1.m1.3.3.2.3.cmml"><mo id="S2.SS5.p2.1.m1.3.3.2.2.3" stretchy="false" xref="S2.SS5.p2.1.m1.3.3.2.3.cmml">(</mo><msub id="S2.SS5.p2.1.m1.2.2.1.1.1" xref="S2.SS5.p2.1.m1.2.2.1.1.1.cmml"><mi id="S2.SS5.p2.1.m1.2.2.1.1.1.2" xref="S2.SS5.p2.1.m1.2.2.1.1.1.2.cmml">y</mi><mn id="S2.SS5.p2.1.m1.2.2.1.1.1.3" xref="S2.SS5.p2.1.m1.2.2.1.1.1.3.cmml">1</mn></msub><mo id="S2.SS5.p2.1.m1.3.3.2.2.4" xref="S2.SS5.p2.1.m1.3.3.2.3.cmml">,</mo><mi id="S2.SS5.p2.1.m1.1.1" mathvariant="normal" xref="S2.SS5.p2.1.m1.1.1.cmml">…</mi><mo id="S2.SS5.p2.1.m1.3.3.2.2.5" xref="S2.SS5.p2.1.m1.3.3.2.3.cmml">,</mo><msub id="S2.SS5.p2.1.m1.3.3.2.2.2" xref="S2.SS5.p2.1.m1.3.3.2.2.2.cmml"><mi id="S2.SS5.p2.1.m1.3.3.2.2.2.2" xref="S2.SS5.p2.1.m1.3.3.2.2.2.2.cmml">y</mi><mi id="S2.SS5.p2.1.m1.3.3.2.2.2.3" xref="S2.SS5.p2.1.m1.3.3.2.2.2.3.cmml">n</mi></msub><mo id="S2.SS5.p2.1.m1.3.3.2.2.6" stretchy="false" xref="S2.SS5.p2.1.m1.3.3.2.3.cmml">)</mo></mrow></mrow><annotation-xml encoding="MathML-Content" id="S2.SS5.p2.1.m1.3b"><apply id="S2.SS5.p2.1.m1.3.3.cmml" xref="S2.SS5.p2.1.m1.3.3"><ci id="S2.SS5.p2.1.m1.3.3.4.cmml" xref="S2.SS5.p2.1.m1.3.3.4">𝑦</ci><vector id="S2.SS5.p2.1.m1.3.3.2.3.cmml" xref="S2.SS5.p2.1.m1.3.3.2.2"><apply id="S2.SS5.p2.1.m1.2.2.1.1.1.cmml" xref="S2.SS5.p2.1.m1.2.2.1.1.1"><csymbol cd="ambiguous" id="S2.SS5.p2.1.m1.2.2.1.1.1.1.cmml" xref="S2.SS5.p2.1.m1.2.2.1.1.1">subscript</csymbol><ci id="S2.SS5.p2.1.m1.2.2.1.1.1.2.cmml" xref="S2.SS5.p2.1.m1.2.2.1.1.1.2">𝑦</ci><cn id="S2.SS5.p2.1.m1.2.2.1.1.1.3.cmml" type="integer" xref="S2.SS5.p2.1.m1.2.2.1.1.1.3">1</cn></apply><ci id="S2.SS5.p2.1.m1.1.1.cmml" xref="S2.SS5.p2.1.m1.1.1">…</ci><apply id="S2.SS5.p2.1.m1.3.3.2.2.2.cmml" xref="S2.SS5.p2.1.m1.3.3.2.2.2"><csymbol cd="ambiguous" id="S2.SS5.p2.1.m1.3.3.2.2.2.1.cmml" xref="S2.SS5.p2.1.m1.3.3.2.2.2">subscript</csymbol><ci id="S2.SS5.p2.1.m1.3.3.2.2.2.2.cmml" xref="S2.SS5.p2.1.m1.3.3.2.2.2.2">𝑦</ci><ci id="S2.SS5.p2.1.m1.3.3.2.2.2.3.cmml" xref="S2.SS5.p2.1.m1.3.3.2.2.2.3">𝑛</ci></apply></vector></apply></annotation-xml><annotation encoding="application/x-tex" id="S2.SS5.p2.1.m1.3c">y=(y_{1},...,y_{n})</annotation><annotation encoding="application/x-llamapun" id="S2.SS5.p2.1.m1.3d">italic_y = ( italic_y start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT , … , italic_y start_POSTSUBSCRIPT italic_n end_POSTSUBSCRIPT )</annotation></semantics></math>。在数学符号中，最大化的概率是：

|  | <math alttext="\begin{split}p(y&#124;x)&amp;=p(y_{n}&#124;x,y_{1...n-1})\cdot p(y{1...n-1}&#124;x)\\ &amp;=p(y_{n}&#124;x,y_{1...n-1})\cdot p(y_{n-1}&#124;x,y_{1...n-2})\cdot...\cdot p(y_{1}&#124;x)% \\ \end{split}" class="ltx_Math" display="block" id="S2.E1.m1.73"><semantics id="S2.E1.m1.73a"><mtable columnspacing="0pt" displaystyle="true" id="S2.E1.m1.73.73.12" rowspacing="0pt" xref="S2.E1.m1.67.67.6.cmml"><mtr id="S2.E1.m1.73.73.12a" xref="S2.E1.m1.67.67.6.cmml"><mtd class="ltx_align_right" columnalign="right" id="S2.E1.m1.73.73.12b" xref="S2.E1.m1.67.67.6.cmml"><mrow id="S2.E1.m1.68.68.7.62.30.7" xref="S2.E1.m1.67.67.6.cmml"><mi id="S2.E1.m1.1.1.1.1.1.1" xref="S2.E1.m1.1.1.1.1.1.1.cmml">p</mi><mo id="S2.E1.m1.68.68.7.62.30.7.8" xref="S2.E1.m1.67.67.6a.cmml">⁢</mo><mrow id="S2.E1.m1.68.68.7.62.30.7.7.1" xref="S2.E1.m1.67.67.6.cmml"><mo id="S2.E1.m1.2.2.2.2.2.2" stretchy="false" xref="S2.E1.m1.67.67.6a.cmml">(</mo><mrow id="S2.E1.m1.68.68.7.62.30.7.7.1.1" xref="S2.E1.m1.67.67.6.cmml"><mi id="S2.E1.m1.3.3.3.3.3.3" xref="S2.E1.m1.3.3.3.3.3.3.cmml">y</mi><mo fence="false" id="S2.E1.m1.4.4.4.4.4.4" xref="S2.E1.m1.4.4.4.4.4.4.cmml">&#124;</mo><mi id="S2.E1.m1.5.5.5.5.5.5" xref="S2.E1.m1.5.5.5.5.5.5.cmml">x</mi></mrow><mo id="S2.E1.m1.6.6.6.6.6.6" stretchy="false" xref="S2.E1.m1.67.67.6a.cmml">)</mo></mrow></mrow></mtd><mtd class="ltx_align_left" columnalign="left" id="S2.E1.m1.73.73.12c" xref="S2.E1.m1.67.67.6.cmml"><mrow id="S2.E1.m1.70.70.9.64.32.25" xref="S2.E1.m1.67.67.6.cmml"><mo id="S2.E1.m1.7.7.7.7.1.1" xref="S2.E1.m1.7.7.7.7.1.1.cmml">=</mo><mrow id="S2.E1.m1.70.70.9.64.32.25.25" xref="S2.E1.m1.67.67.6.cmml"><mrow id="S2.E1.m1.69.69.8.63.31.24.24.1" xref="S2.E1.m1.67.67.6.cmml"><mrow id="S2.E1.m1.69.69.8.63.31.24.24.1.1" xref="S2.E1.m1.67.67.6.cmml"><mi id="S2.E1.m1.8.8.8.8.2.2" xref="S2.E1.m1.8.8.8.8.2.2.cmml">p</mi><mo id="S2.E1.m1.69.69.8.63.31.24.24.1.1.2" xref="S2.E1.m1.67.67.6a.cmml">⁢</mo><mrow id="S2.E1.m1.69.69.8.63.31.24.24.1.1.1.1" xref="S2.E1.m1.67.67.6.cmml"><mo id="S2.E1.m1.9.9.9.9.3.3" stretchy="false" xref="S2.E1.m1.67.67.6a.cmml">(</mo><mrow id="S2.E1.m1.69.69.8.63.31.24.24.1.1.1.1.1" xref="S2.E1.m1.67.67.6.cmml"><msub id="S2.E1.m1.69.69.8.63.31.24.24.1.1.1.1.1.2" xref="S2.E1.m1.67.67.6.cmml"><mi id="S2.E1.m1.10.10.10.10.4.4" xref="S2.E1.m1.10.10.10.10.4.4.cmml">y</mi><mi id="S2.E1.m1.11.11.11.11.5.5.1" xref="S2.E1.m1.11.11.11.11.5.5.1.cmml">n</mi></msub><mo fence="false" id="S2.E1.m1.12.12.12.12.6.6" xref="S2.E1.m1.12.12.12.12.6.6.cmml">&#124;</mo><mrow id="S2.E1.m1.69.69.8.63.31.24.24.1.1.1.1.1.1.1" xref="S2.E1.m1.67.67.6.cmml"><mi id="S2.E1.m1.13.13.13.13.7.7" xref="S2.E1.m1.13.13.13.13.7.7.cmml">x</mi><mo id="S2.E1.m1.14.14.14.14.8.8" xref="S2.E1.m1.67.67.6a.cmml">,</mo><msub id="S2.E1.m1.69.69.8.63.31.24.24.1.1.1.1.1.1.1.1" xref="S2.E1.m1.67.67.6.cmml"><mi id="S2.E1.m1.15.15.15.15.9.9" xref="S2.E1.m1.15.15.15.15.9.9.cmml">y</mi><mrow id="S2.E1.m1.16.16.16.16.10.10.1" xref="S2.E1.m1.16.16.16.16.10.10.1.cmml"><mrow id="S2.E1.m1.16.16.16.16.10.10.1.2" xref="S2.E1.m1.16.16.16.16.10.10.1.2.cmml"><mn id="S2.E1.m1.16.16.16.16.10.10.1.2.2" xref="S2.E1.m1.16.16.16.16.10.10.1.2.2.cmml">1</mn><mo id="S2.E1.m1.16.16.16.16.10.10.1.2.1" xref="S2.E1.m1.16.16.16.16.10.10.1.2.1.cmml">⁢</mo><mi id="S2.E1.m1.16.16.16.16.10.10.1.2. |
| --- | --- |

每次不是选择概率最高的输出标记，而是选择概率最高的前 K 个标记，并递归地探索生成的序列，直到我们遇到一个<math alttext="<EOS>" class="ltx_Math" display="inline" id="S2.SS5.p4.1.m1.1"><semantics id="S2.SS5.p4.1.m1.1a"><mrow id="S2.SS5.p4.1.m1.1.1.1" xref="S2.SS5.p4.1.m1.1.1.2.cmml"><mo fence="true" id="S2.SS5.p4.1.m1.1.1.1.2" rspace="0em" xref="S2.SS5.p4.1.m1.1.1.2.1.cmml"><</mo><mrow id="S2.SS5.p4.1.m1.1.1.1.1" xref="S2.SS5.p4.1.m1.1.1.1.1.cmml"><mi id="S2.SS5.p4.1.m1.1.1.1.1.2" xref="S2.SS5.p4.1.m1.1.1.1.1.2.cmml">E</mi><mo id="S2.SS5.p4.1.m1.1.1.1.1.1" xref="S2.SS5.p4.1.m1.1.1.1.1.1.cmml">⁢</mo><mi id="S2.SS5.p4.1.m1.1.1.1.1.3" xref="S2.SS5.p4.1.m1.1.1.1.1.3.cmml">O</mi><mo id="S2.SS5.p4.1.m1.1.1.1.1.1a" xref="S2.SS5.p4.1.m1.1.1.1.1.1.cmml">⁢</mo><mi id="S2.SS5.p4.1.m1.1.1.1.1.4" xref="S2.SS5.p4.1.m1.1.1.1.1.4.cmml">S</mi></mrow><mo fence="true" id="S2.SS5.p4.1.m1.1.1.1.3" lspace="0em" xref="S2.SS5.p4.1.m1.1.1.2.1.cmml">></mo></mrow><annotation-xml encoding="MathML-Content" id="S2.SS5.p4.1.m1.1b"><apply id="S2.SS5.p4.1.m1.1.1.2.cmml" xref="S2.SS5.p4.1.m1.1.1.1"><csymbol cd="latexml" id="S2.SS5.p4.1.m1.1.1.2.1.cmml" xref="S2.SS5.p4.1.m1.1.1.1.2">expectation</csymbol><apply id="S2.SS5.p4.1.m1.1.1.1.1.cmml" xref="S2.SS5.p4.1.m1.1.1.1.1"><ci id="S2.SS5.p4.1.m1.1.1.1.1.2.cmml" xref="S2.SS5.p4.1.m1.1.1.1.1.2">𝐸</ci><ci id="S2.SS5.p4.1.m1.1.1.1.1.3.cmml" xref="S2.SS5.p4.1.m1.1.1.1.1.3">𝑂</ci><ci id="S2.SS5.p4.1.m1.1.1.1.1.4.cmml" xref="S2.SS5.p4.1.m1.1.1.1.1.4">𝑆</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S2.SS5.p4.1.m1.1c"><EOS></annotation><annotation encoding="application/x-llamapun" id="S2.SS5.p4.1.m1.1d">< italic_E italic_O italic_S ></annotation></semantics></math>（序列结束）标记。然后，它返回序列<math alttext="y" class="ltx_Math" display="inline" id="S2.SS5.p4.2.m2.1"><semantics id="S2.SS5.p4.2.m2.1a"><mi id="S2.SS5.p4.2.m2.1.1" xref="S2.SS5.p4.2.m2.1.1.cmml">y</mi><annotation-xml encoding="MathML-Content" id="S2.SS5.p4.2.m2.1b"><ci id="S2.SS5.p4.2.m2.1.1.cmml" xref="S2.SS5.p4.2.m2.1.1">𝑦</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.SS5.p4.2.m2.1c">y</annotation><annotation encoding="application/x-llamapun" id="S2.SS5.p4.2.m2.1d">italic_y</annotation></semantics></math>（K 个序列中的一个）来最大化<math alttext="p(y|x)" class="ltx_Math" display="inline" id="S2.SS5.p4.3.m3.1"><semantics id="S2.SS5.p4.3.m3.1a"><mrow id="S2.SS5.p4.3.m3.1.1" xref="S2.SS5.p4.3.m3.1.1.cmml"><mi id="S2.SS5.p4.3.m3.1.1.3" xref="S2.SS5.p4.3.m3.1.1.3.cmml">p</mi><mo id="S2.SS5.p4.3.m3.1.1.2" xref="S2.SS5.p4.3.m3.1.1.2.cmml">⁢</mo><mrow id="S2.SS5.p4.3.m3.1.1.1.1" xref="S2.SS5.p4.3.m3.1.1.1.1.1.cmml"><mo id="S2.SS5.p4.3.m3.1.1.1.1.2" stretchy="false" xref="S2.SS5.p4.3.m3.1.1.1.1.1.cmml">(</mo><mrow id="S2.SS5.p4.3.m3.1.1.1.1.1" xref="S2.SS5.p4.3.m3.1.1.1.1.1.cmml"><mi id="S2.SS5.p4.3.m3.1.1.1.1.1.2" xref="S2.SS5.p4.3.m3.1.1.1.1.1.2.cmml">y</mi><mo fence="false" id="S2.SS5.p4.3.m3.1.1.1.1.1.1" xref="S2.SS5.p4.3.m3.1.1.1.1.1.1.cmml">|</mo><mi id="S2.SS5.p4.3.m3.1.1.1.1.1.3" xref="S2.SS5.p4.3.m3.1.1.1.1.1.3.cmml">x</mi></mrow><mo id="S2.SS5.p4.3.m3.1.1.1.1.3" stretchy="false" xref="S2.SS5.p4.3.m3.1.1.1.1.1.cmml">)</mo></mrow></mrow><annotation-xml encoding="MathML-Content" id="S2.SS5.p4.3.m3.1b"><apply id="S2.SS5.p4.3.m3.1.1.cmml" xref="S2.SS5.p4.3.m3.1.1"><ci id="S2.SS5.p4.3.m3.1.1.3.cmml" xref="S2.SS5.p4.3.m3.1.1.3">𝑝</ci><apply id="S2.SS5.p4.3.m3.1.1.1.1.1.cmml" xref="S

在接下来的几节中，我们将探讨一些对理解最先进的 LLMs 增强至关重要的概念。

### II-F 文本语料库

一个文本语料库，<math alttext="D" class="ltx_Math" display="inline" id="S2.SS6.p1.1.m1.1"><semantics id="S2.SS6.p1.1.m1.1a"><mi id="S2.SS6.p1.1.m1.1.1" xref="S2.SS6.p1.1.m1.1.1.cmml">D</mi><annotation-xml encoding="MathML-Content" id="S2.SS6.p1.1.m1.1b"><ci id="S2.SS6.p1.1.m1.1.1.cmml" xref="S2.SS6.p1.1.m1.1.1">𝐷</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.SS6.p1.1.m1.1c">D</annotation><annotation encoding="application/x-llamapun" id="S2.SS6.p1.1.m1.1d">italic_D</annotation></semantics></math> 是一组文档： <math alttext="{d_{1},...,d_{|D|}}" class="ltx_Math" display="inline" id="S2.SS6.p1.2.m2.4"><semantics id="S2.SS6.p1.2.m2.4a"><mrow id="S2.SS6.p1.2.m2.4.4.2" xref="S2.SS6.p1.2.m2.4.4.3.cmml"><msub id="S2.SS6.p1.2.m2.3.3.1.1" xref="S2.SS6.p1.2.m2.3.3.1.1.cmml"><mi id="S2.SS6.p1.2.m2.3.3.1.1.2" xref="S2.SS6.p1.2.m2.3.3.1.1.2.cmml">d</mi><mn id="S2.SS6.p1.2.m2.3.3.1.1.3" xref="S2.SS6.p1.2.m2.3.3.1.1.3.cmml">1</mn></msub><mo id="S2.SS6.p1.2.m2.4.4.2.3" xref="S2.SS6.p1.2.m2.4.4.3.cmml">,</mo><mi id="S2.SS6.p1.2.m2.2.2" mathvariant="normal" xref="S2.SS6.p1.2.m2.2.2.cmml">…</mi><mo id="S2.SS6.p1.2.m2.4.4.2.4" xref="S2.SS6.p1.2.m2.4.4.3.cmml">,</mo><msub id="S2.SS6.p1.2.m2.4.4.2.2" xref="S2.SS6.p1.2.m2.4.4.2.2.cmml"><mi id="S2.SS6.p1.2.m2.4.4.2.2.2" xref="S2.SS6.p1.2.m2.4.4.2.2.2.cmml">d</mi><mrow id="S2.SS6.p1.2.m2.1.1.1.3" xref="S2.SS6.p1.2.m2.1.1.1.2.cmml"><mo id="S2.SS6.p1.2.m2.1.1.1.3.1" stretchy="false" xref="S2.SS6.p1.2.m2.1.1.1.2.1.cmml">|</mo><mi id="S2.SS6.p1.2.m2.1.1.1.1" xref="S2.SS6.p1.2.m2.1.1.1.1.cmml">D</mi><mo id="S2.SS6.p1.2.m2.1.1.1.3.2" stretchy="false" xref="S2.SS6.p1.2.m2.1.1.1.2.1.cmml">|</mo></mrow></msub></mrow><annotation-xml encoding="MathML-Content" id="S2.SS6.p1.2.m2.4b"><list id="S2.SS6.p1.2.m2.4.4.3.cmml" xref="S2.SS6.p1.2.m2.4.4.2"><apply id="S2.SS6.p1.2.m2.3.3.1.1.cmml" xref="S2.SS6.p1.2.m2.3.3.1.1"><csymbol cd="ambiguous" id="S2.SS6.p1.2.m2.3.3.1.1.1.cmml" xref="S2.SS6.p1.2.m2.3.3.1.1">subscript</csymbol><ci id="S2.SS6.p1.2.m2.3.3.1.1.2.cmml" xref="S2.SS6.p1.2.m2.3.3.1.1.2">𝑑</ci><cn id="S2.SS6.p1.2.m2.3.3.1.1.3.cmml" type="integer" xref="S2.SS6.p1.2.m2.3.3.1.1.3">1</cn></apply><ci id="S2.SS6.p1.2.m2.2.2.cmml" xref="S2.SS6.p1.2.m2.2.2">…</ci><apply id="S2.SS6.p1.2.m2.4.4.2.2.cmml" xref="S2.SS6.p1.2.m2.4.4.2.2"><csymbol cd="ambiguous" id="S2.SS6.p1.2.m2.4.4.2.2.1.cmml" xref="S2.SS6.p1.2.m2.4.4.2.2">subscript</csymbol><ci id="S2.SS6.p1.2.m2.4.4.2.2.2.cmml" xref="S2.SS6.p1.2.m2.4.4.2.2.2">𝑑</ci><apply id="S2.SS6.p1.2.m2.1.1.1.2.cmml" xref="S2.SS6.p1.2.m2.1.1.1.3"><ci id="S2.SS6.p1.2.m2.1.1.1.1.cmml" xref="S2.SS6.p1.2.m2.1.1.1.1">𝐷</ci></apply></apply></list></annotation-xml><annotation encoding="application/x-tex" id="S2.SS6.p1.2.m2.4c">{d_{1},...,d_{|D|}}</annotation><annotation encoding="application/x-llamapun" id="S2.SS6.p1.2.m2.4d">italic_d start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT , … , italic_d start_POSTSUBSCRIPT | italic_D | end_POSTSUBSCRIPT</annotation></semantics></math> 其中每个文档是一个词的序列： <math alttext="d_{i}=(w_{1},...,w_{|d_{i}|})" class="ltx_Math" display="inline" id="S2.SS6.p1.3.m3.4"><semantics id="S2.SS6.p1.3.m3.4a"><mrow id="S2.SS6.p1.3.m3.4.4" xref="S2.SS6.p1.3.m3.4.4.cmml"><msub id="S2.SS6.p1.3.m3.4.4.4" xref="S2.SS6.p1.3.m3.4.4.4.cmml"><mi id="S2.SS6.p1.3.m3.4.4.4.2" xref="S2.SS6.p1.3.m3.4.4.4.2.cmml">d</mi><mi id="S2.SS6.p1.3.m3.4.4.4.3" xref="S2.SS6.p1.3.m3.4.4.4.3.cmml">i</mi></msub><mo id="S2.SS6.p1.3.m3.4.4.3" xref="S2.SS6.p1.3.m3.4

正如我们稍后在本调查中看到的，文本语料库被认为是非结构化知识库，通常组织在向量数据库中。

### II-G 向量数据库

在向量数据库中，文档可以对应一个向量或多个向量，具体取决于数据库的具体实现。单个向量捕获文档的整体含义。这通常通过平均文档中单词的向量来实现。在其他情况下，文档可能由文档中每个单词的向量表示。当需要跟踪文档中的单个单词时，通常会这样做。

当语言模型从向量数据库中检索信息时，它实际上是访问存储在其参数（权重）之外的知识。因此，向量数据库是一种非参数记忆形式，用于 LLMs。

### II-H 密集向量索引

在向量数据库中的索引是将数据库中的向量以一种高效的方式进行组织，以便于搜索和检索相似向量（具有高内积的向量）。这通过创建一个数据结构来实现，该结构将每个向量映射到一组与其相似的其他向量。

最大内积搜索（MIPS）是一种特定类型的向量搜索，旨在找到数据库中与给定查询向量具有最高内积的向量。MIPS 用于多种应用中，如推荐系统、机器学习和图像检索。

FAISS [26] 是一个流行的开源库，用于高效的相似性搜索和密集向量的聚类。FAISS 包含多种 MIPS 算法，以及其他类型的向量搜索。FAISS 被许多公司和组织使用，包括 Google、Facebook 和 Microsoft。

### II-I 三元组知识库

三元组知识库是由主语-谓语-宾语三元组组成的数据库。这样的一个三元组示例是：（主语：阿尔伯特·爱因斯坦，谓语：出生在，宾语：德国乌尔姆）。三元组是表示事实知识的好形式，因为它们捕捉了主语和宾语之间关系的性质，并且可以被 LLMs 轻松处理。可以将这个知识库可视化为一个图，其中顶点是各种主语和宾语（实体），谓语是这些实体之间的边。

每个边都有一个类型（例如：“出生在”），描述了连接的实体之间的关系类型。具有多种关系类型的三元组知识库称为异构知识库。

三元存储库是我们所称的结构化知识库的一个极佳示例。它们可以通过一组实体链接与非结构化知识库合并：`(v,d_{p})`，将实体`v`与文档中位置为`p`的词连接起来，文档为`d`。

### II-J 图卷积网络

图卷积网络（GCNs）是一种神经网络类型，可用于学习结构化知识库（如图形）中节点的表示。GCNs 特别适合于节点分类任务，其中目标是预测图中每个节点的标签（例如：节点是否包含给定问题的答案）。

GCN 通过迭代地从每个节点的邻居处汇总信息来工作。在每一层，GCN 收集所有邻居的嵌入，对其进行平均，然后应用线性变换和非线性激活函数。该层的输出被用作下一层的输入。

GCN 的层数越多，模型能够执行的多跳推理就越多，因为它会从更远的邻居那里收集信息。这使得 GCNs 非常适合于那些节点的标签依赖于其邻居标签的任务，如社交网络分析和欺诈检测。

以下是 GCN 在节点分类中的高层次概述：

1.  1.

    初始化图中所有节点的嵌入。

1.  2.

    对于图中的每个节点：

    1.  (a)

        收集所有节点邻居的嵌入。

    1.  (b)

        对节点邻居的嵌入进行平均。

    1.  (c)

        对平均嵌入应用线性变换和非线性激活函数。

    1.  (d)

        该函数的输出是节点的新嵌入。

1.  3.

    对固定数量的层重复步骤 2。

1.  4.

    每个节点的最终嵌入被用作分类器的输入，以预测节点的标签。

### II-K 关系图卷积网络

当知识库图异质时出现的一个问题是，我们希望在平均嵌入之前考虑节点与其邻居的关系类型。

关系 GCN [27] 与普通的 GCN 类似，但它为每种关系类型使用一个单独的矩阵。因此，在使用关系 GCN 时，我们将所有具有特定关系的邻居的嵌入汇总，然后将平均的嵌入传递给每种关系的单独 CNN 层。

## III 知识库增强生成

语言模型具有在其参数中存储知识的能力。或者，可以通过从外部知识库中检索将自然语言形式的知识完全从语言模型中卸载。记忆增强策略帮助语言模型避免生成非事实信息，并减少所需参数的数量，从而实现与显著更大语言模型相当的性能。根据其结构，知识库可以是非结构化的（基于文本）或结构化的（基于图形）。在这次文献综述中，我们将探讨这两个领域的工作。

![参见说明](img/657da9c5ff73a90efccaa4df22b61ab4.png)

图 1：Izacard 等人论文中语言模型知识增强的概述[7]。输入查询（浅黄色）以及若干检索到的相关文档（浅蓝色）通过生成的 seq2seq 模型生成输出回应。

### III-A 检索增强生成（RAG）

RAG [6] 使用参数化和非参数化记忆来生成更准确、更有信息的回应。

具体来说，RAG 架构包括：

+   •

    一个生成器：一个 BART-large [28] 序列到序列的语言模型，经过大规模文本和代码数据集的预训练（参数化记忆）。

+   •

    知识库：维基百科数据库的密集向量索引（非参数记忆）。知识库中的所有文档也使用**BERT_{BASE}** [24] 文档编码器进行编码。

+   •

    一个检索器：一个负责从知识库中检索与输入查询最相关文档的组件。它遵循 DPR（密集段落检索）架构[29]，包括一个文档编码器，<math alttext="BERT_{d}" class="ltx_Math" display="inline" id="S3.I1.i3.p1.1.m1.1"><semantics id="S3.I1.i3.p1.1.m1.1a"><mrow id="S3.I1.i3.p1.1.m1.1.1" xref="S3.I1.i3.p1.1.m1.1.1.cmml"><mi id="S3.I1.i3.p1.1.m1.1.1.2" xref="S3.I1.i3.p1.1.m1.1.1.2.cmml">B</mi><mo id="S3.I1.i3.p1.1.m1.1.1" xref="S3.I1.i3.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I1.i3.p1.1.m1.1.3" xref="S3.I1.i3.p1.1.m1.1.3.cmml">E</mi><mo id="S3.I1.i3.p1.1.m1.1.1a" xref="S3.I1.i3.p1.1.m1.1.1.cmml">⁢</mo><mi id="S3.I1.i3.p1.1.m1.1.4" xref="S3.I1.i3.p1.1.m1.1.4.cmml">R</mi><mo id="S3.I1.i3.p1.1.m1.1.1b" xref="S3.I1.i3.p1.1.m1.1.1.cmml">⁢</mo><msub id="S3.I1.i3.p1.1.m1.1.5" xref="S3.I1.i3.p1.1.m1.1.5.cmml"><mi id="S3.I1.i3.p1.1.m1.1.5.2" xref="S3.I1.i3.p1.1.m1.1.5.2.cmml">T</mi><mi id="S3.I1.i3.p1.1.m1.1.5.3" xref="S3.I1.i3.p1.1.m1.1.5.3.cmml">d</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.I1.i3.p1.1.m1.1b"><apply id="S3.I1.i3.p1.1.m1.1.1.cmml" xref="S3.I1.i3.p1.1.m1.1.1"><ci id="S3.I1.i3.p1.1.m1.1.1.2.cmml" xref="S3.I1.i3.p1.1.m1.1.1.2">𝐵</ci><ci id="S3.I1.i3.p1.1.m1.1.3.cmml" xref="S3.I1.i3.p1.1.m1.1.3">𝐸</ci><ci id="S3.I1.i3.p1.1.m1.1.4.cmml" xref="S3.I1.i3.p1.1.m1.1.4">𝑅</ci><apply id="S3.I1.i3.p1.1.m1.1.5.cmml" xref="S3.I1.i3.p1.1.m1.1.5"><csymbol cd="ambiguous" id="S3.I1.i3.p1.1.m1.1.5.1.cmml" xref="S3.I1.i3.p1.1.m1.1.5">subscript</csymbol><ci id="S3.I1.i3.p1.1.m1.1.5.2.cmml" xref="S3.I1.i3.p1.1.m1.1.5.2">𝑇</ci><ci id="S3.I1.i3.p1.1.m1.1.5.3.cmml" xref="S3.I1.i3.p1.1.m1.1.5.3">𝑑</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I1.i3.p1.1.m1.1c">BERT_{d}</annotation><annotation encoding="application/x-llamapun" id="S3.I1.i3.p1.1.m1.1d">italic_B italic_E italic_R italic_T start_POSTSUBSCRIPT italic_d end_POSTSUBSCRIPT</annotation></semantics></math>和一个查询编码器，<math alttext="BERT_{q}" class="ltx_Math" display="inline" id="S3.I1.i3.p1.2.m2.1"><semantics id="S3.I1.i3.p1.2.m2.1a"><mrow id="S3.I1.i3.p1.2.m2.1.1" xref="S3.I1.i3.p1.2.m2.1.1.cmml"><mi id="S3.I1.i3.p1.2.m2.1.1.2" xref="S3.I1.i3.p1.2.m2.1.1.2.cmml">B</mi><mo id="S3.I1.i3.p1.2.m2.1.1.1" xref="S3.I1.i3.p1.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.I1.i3.p1.2.m2.1.3" xref="S3.I1.i3.p1.2.m2.1.3.cmml">E</mi><mo id="S3.I1.i3.p1.2.m2.1.1a" xref="S3.I1.i3.p1.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.I1.i3.p1.2.m2.1.4" xref="S3.I1.i3.p1.2.m2.1.4.cmml">R</mi><mo id="S3.I1.i3.p1.2.m2.1.1b" xref="S3.I1.i3.p1.2.m2.1.1.1.cmml">⁢</mo><msub id="S3.I1.i3.p1.2.m2.1.5" xref="S3.I1.i3.p1.2.m2.1.5.cmml"><mi id="S3.I1.i3.p1.2.m2.1.5.2" xref="S3.I1.i3.p1.2.m2.1.5.2.cmml">T</mi><mi id="S3.I1.i3.p1.2.m2.1.5.3" xref="S3.I1.i3.p1.2.m2.1.5.3.cmml">q</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.I1.i3.p1.2.m2.1b"><apply id="S3.I1.i3.p1.2.m2.1.1.cmml" xref="S3.I1.i3.p1.2.m2.1.1"><ci id="S3.I1.i3.p1.2.m2.1.1.2.cmml" xref="S3.I1.i3.p1.2.m2.1.1.2">𝐵</ci><ci id="S3.I1.i3.p1.2.m2.1.1.3.cmml" xref="S3.I1.i3.p1.2.m2.1.1.3">𝐸</ci><ci id="S3.I1.i3.p1.2.m2.1.4.cmml" xref="S3.I1.i3.p1.2.m2.1.4">𝑅</ci><apply id="S3.I1.i3.p1.2.m2.1.5.cmml" xref="S3.I1.i3.p1.2.m2.1.5"><csymbol cd="ambiguous" id="S3.I1.i3.p1.2.m2.1.5.1.cmml" xref="S3.I1.i3.p1.2.m2.1.5">subscript</csymbol><ci id="S3.I1.i3.p1.2.m2.1.5.2.cmml" xref="S3.I1.i3.p1.2.m2.1.5.2">𝑇</ci><ci id="S3.I1.i3.p1.2.m2.1.5.3

    +   —

        计算输入查询的嵌入，使用 `<math alttext="BERT_{q}" class="ltx_Math" display="inline" id="S3.I1.i3.I1.i1.p1.1.m1.1"><semantics id="S3.I1.i3.I1.i1.p1.1.m1.1a"><mrow id="S3.I1.i3.I1.i1.p1.1.m1.1.1" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.cmml"><mi id="S3.I1.i3.I1.i1.p1.1.m1.1.1.2" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.2.cmml">B</mi><mo id="S3.I1.i3.I1.i1.p1.1.m1.1.1.1" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I1.i3.I1.i1.p1.1.m1.1.1.3" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.3.cmml">E</mi><mo id="S3.I1.i3.I1.i1.p1.1.m1.1.1.1a" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I1.i3.I1.i1.p1.1.m1.1.1.4" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.4.cmml">R</mi><mo id="S3.I1.i3.I1.i1.p1.1.m1.1.1.1b" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.1.cmml">⁢</mo><msub id="S3.I1.i3.I1.i1.p1.1.m1.1.1.5" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.cmml"><mi id="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.2" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.2.cmml">T</mi><mi id="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.3" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.3.cmml">q</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.I1.i3.I1.i1.p1.1.m1.1b"><apply id="S3.I1.i3.I1.i1.p1.1.m1.1.1.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1"><ci id="S3.I1.i3.I1.i1.p1.1.m1.1.1.2.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.2">𝐵</ci><ci id="S3.I1.i3.I1.i1.p1.1.m1.1.1.3.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.3">𝐸</ci><ci id="S3.I1.i3.I1.i1.p1.1.m1.1.1.4.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.4">𝑅</ci><apply id="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.5"><csymbol cd="ambiguous" id="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.1.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.5">subscript</csymbol><ci id="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.2.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.2">𝑇</ci><ci id="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.3.cmml" xref="S3.I1.i3.I1.i1.p1.1.m1.1.1.5.3">𝑞</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I1.i3.I1.i1.p1.1.m1.1c">BERT_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.I1.i3.I1.i1.p1.1.m1.1d">italic_B italic_E italic_R italic_T start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>` 编码器。

    +   —

        在索引的知识库中进行最大内积搜索（MIPS），以找到与输入查询最相似的 K 个文档。

根据 RAG 的作者，训练和微调 <math alttext="BERT_{d}" class="ltx_Math" display="inline" id="S3.SS1.p3.1.m1.1"><semantics id="S3.SS1.p3.1.m1.1a"><mrow id="S3.SS1.p3.1.m1.1.1" xref="S3.SS1.p3.1.m1.1.1.cmml"><mi id="S3.SS1.p3.1.m1.1.2" xref="S3.SS1.p3.1.m1.1.2.cmml">B</mi><mo id="S3.SS1.p3.1.m1.1.1" xref="S3.SS1.p3.1.m1.1.1.cmml">⁢</mo><mi id="S3.SS1.p3.1.m1.1.3" xref="S3.SS1.p3.1.m1.1.3.cmml">E</mi><mo id="S3.SS1.p3.1.m1.1.1a" xref="S3.SS1.p3.1.m1.1.1.cmml">⁢</mo><mi id="S3.SS1.p3.1.m1.1.4" xref="S3.SS1.p3.1.m1.1.4.cmml">R</mi><mo id="S3.SS1.p3.1.m1.1.1b" xref="S3.SS1.p3.1.m1.1.1.cmml">⁢</mo><msub id="S3.SS1.p3.1.m1.1.5" xref="S3.SS1.p3.1.m1.1.5.cmml"><mi id="S3.SS1.p3.1.m1.1.5.2" xref="S3.SS1.p3.1.m1.1.5.2.cmml">T</mi><mi id="S3.SS1.p3.1.m1.1.5.3" xref="S3.SS1.p3.1.m1.1.5.3.cmml">d</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.SS1.p3.1.m1.1b"><apply id="S3.SS1.p3.1.m1.1.cmml" xref="S3.SS1.p3.1.m1.1"><ci id="S3.SS1.p3.1.m1.1.2.cmml" xref="S3.SS1.p3.1.m1.1.2">𝐵</ci><ci id="S3.SS1.p3.1.m1.1.3.cmml" xref="S3.SS1.p3.1.m1.1.3">𝐸</ci><ci id="S3.SS1.p3.1.m1.1.4.cmml" xref="S3.SS1.p3.1.m1.1.4">𝑅</ci><apply id="S3.SS1.p3.1.m1.1.5.cmml" xref="S3.SS1.p3.1.m1.1.5"><csymbol cd="ambiguous" id="S3.SS1.p3.1.m1.1.5.1.cmml" xref="S3.SS1.p3.1.m1.1.5">subscript</csymbol><ci id="S3.SS1.p3.1.m1.1.5.2.cmml" xref="S3.SS1.p3.1.m1.1.5.2">𝑇</ci><ci id="S3.SS1.p3.1.m1.1.5.3.cmml" xref="S3.SS1.p3.1.m1.1.5.3">𝑑</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS1.p3.1.m1.1c">BERT_{d}</annotation><annotation encoding="application/x-llamapun" id="S3.SS1.p3.1.m1.1d">italic_B italic_E italic_R italic_T start_POSTSUBSCRIPT italic_d end_POSTSUBSCRIPT</annotation></semantics></math> 编码器的参数是非常计算密集的，并且在准确性上效果也不是很好。具体来说，如果他们要训练 <math alttext="BERT_{d}" class="ltx_Math" display="inline" id="S3.SS1.p3.2.m2.1"><semantics id="S3.SS1.p3.2.m2.1a"><mrow id="S3.SS1.p3.2.m2.1.1" xref="S3.SS1.p3.2.m2.1.1.cmml"><mi id="S3.SS1.p3.2.m2.1.1.2" xref="S3.SS1.p3.2.m2.1.1.2.cmml">B</mi><mo id="S3.SS1.p3.2.m2.1.1.1" xref="S3.SS1.p3.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.SS1.p3.2.m2.1.1.3" xref="S3.SS1.p3.2.m2.1.1.3.cmml">E</mi><mo id="S3.SS1.p3.2.m2.1.1.1a" xref="S3.SS1.p3.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.SS1.p3.2.m2.1.1.4" xref="S3.SS1.p3.2.m2.1.1.4.cmml">R</mi><mo id="S3.SS1.p3.2.m2.1.1.1b" xref="S3.SS1.p3.2.m2.1.1.1.cmml">⁢</mo><msub id="S3.SS1.p3.2.m2.1.1.5" xref="S3.SS1.p3.2.m2.1.1.5.cmml"><mi id="S3.SS1.p3.2.m2.1.1.5.2" xref="S3.SS1.p3.2.m2.1.1.5.2.cmml">T</mi><mi id="S3.SS1.p3.2.m2.1.1.5.3" xref="S3.SS1.p3.2.m2.1.1.5.3.cmml">d</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.SS1.p3.2.m2.1b"><apply id="S3.SS1.p3.2.m2.1.1.cmml" xref="S3.SS1.p3.2.m2.1.1"><ci id="S3.SS1.p3.2.m2.1.1.2.cmml" xref="S3.SS1.p3.2.m2.1.1.2">𝐵</ci><ci id="S3.SS1.p3.2.m2.1.1.3.cmml" xref="S3.SS1.p3.2.m2.1.1.3">𝐸</ci><ci id="S3.SS1.p3.2.m2.1.1.4.cmml" xref="S3.SS1.p3.2.m2.1.1.4">𝑅</ci><apply id="S3.SS1.p3.2.m2.1.1.5.cmml" xref="S3.SS1.p3.2.m2.1.1.5"><csymbol cd="ambiguous" id="S3.SS1.p3.2.m2.1.1.5.1.cmml" xref="S3.SS1.p3.2.m2.1.1.5">subscript</csymbol><ci id="S3.SS1.p3.2.m2.1.1.5.2.cmml" xref="S3.SS1.p3.2.m2.1.1.5.2">𝑇</ci><ci id="S3.SS1.p3.2.m2.1.1.5.3.cmml" xref="S3.SS1.p3.2.m2.1.1.5.3">𝑑</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS1.p3.2.m2.1c">BERT_{d}</annotation><annotation encoding

因此，他们使用一个完全预训练的<math alttext="BERT_{d}" class="ltx_Math" display="inline" id="S3.SS1.p4.1.m1.1"><semantics id="S3.SS1.p4.1.m1.1a"><mrow id="S3.SS1.p4.1.m1.1.1" xref="S3.SS1.p4.1.m1.1.1.cmml"><mi id="S3.SS1.p4.1.m1.1.1.2" xref="S3.SS1.p4.1.m1.1.2.cmml">B</mi><mo id="S3.SS1.p4.1.m1.1.1.1" xref="S3.SS1.p4.1.m1.1.1.cmml">⁢</mo><mi id="S3.SS1.p4.1.m1.1.3" xref="S3.SS1.p4.1.m1.1.3.cmml">E</mi><mo id="S3.SS1.p4.1.m1.1.1a" xref="S3.SS1.p4.1.m1.1.1.cmml">⁢</mo><mi id="S3.SS1.p4.1.m1.1.4" xref="S3.SS1.p4.1.m1.1.4.cmml">R</mi><mo id="S3.SS1.p4.1.m1.1.1b" xref="S3.SS1.p4.1.m1.1.1.cmml">⁢</mo><msub id="S3.SS1.p4.1.m1.1.5" xref="S3.SS1.p4.1.m1.1.5.cmml"><mi id="S3.SS1.p4.1.m1.1.5.2" xref="S3.SS1.p4.1.m1.1.5.2.cmml">T</mi><mi id="S3.SS1.p4.1.m1.1.5.3" xref="S3.SS1.p4.1.m1.1.5.3.cmml">d</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.SS1.p4.1.m1.1b"><apply id="S3.SS1.p4.1.m1.1.1.cmml" xref="S3.SS1.p4.1.m1.1.1"><ci id="S3.SS1.p4.1.m1.1.2.cmml" xref="S3.SS1.p4.1.m1.1.2">𝐵</ci><ci id="S3.SS1.p4.1.m1.1.3.cmml" xref="S3.SS1.p4.1.m1.1.3">𝐸</ci><ci id="S3.SS1.p4.1.m1.1.4.cmml" xref="S3.SS1.p4.1.m1.1.4">𝑅</ci><apply id="S3.SS1.p4.1.m1.1.5.cmml" xref="S3.SS1.p4.1.m1.1.5"><csymbol cd="ambiguous" id="S3.SS1.p4.1.m1.1.5.1.cmml" xref="S3.SS1.p4.1.m1.1.5">subscript</csymbol><ci id="S3.SS1.p4.1.m1.1.5.2.cmml" xref="S3.SS1.p4.1.m1.1.5.2">𝑇</ci><ci id="S3.SS1.p4.1.m1.1.5.3.cmml" xref="S3.SS1.p4.1.m1.1.5.3">𝑑</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS1.p4.1.m1.1c">BERT_{d}</annotation><annotation encoding="application/x-llamapun" id="S3.SS1.p4.1.m1.1d">italic_B italic_E italic_R italic_T start_POSTSUBSCRIPT italic_d end_POSTSUBSCRIPT</annotation></semantics></math>编码器，并且在微调阶段，他们只微调查询编码器的参数<math alttext="BERT_{q}" class="ltx_Math" display="inline" id="S3.SS1.p4.2.m2.1"><semantics id="S3.SS1.p4.2.m2.1a"><mrow id="S3.SS1.p4.2.m2.1.1" xref="S3.SS1.p4.2.m2.1.1.cmml"><mi id="S3.SS1.p4.2.m2.1.1.2" xref="S3.SS1.p4.2.m2.1.1.2.cmml">B</mi><mo id="S3.SS1.p4.2.m2.1.1.1" xref="S3.SS1.p4.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.SS1.p4.2.m2.1.3" xref="S3.SS1.p4.2.m2.1.3.cmml">E</mi><mo id="S3.SS1.p4.2.m2.1.1a" xref="S3.SS1.p4.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.SS1.p4.2.m2.1.4" xref="S3.SS1.p4.2.m2.1.4.cmml">R</mi><mo id="S3.SS1.p4.2.m2.1.1b" xref="S3.SS1.p4.2.m2.1.1.1.cmml">⁢</mo><msub id="S3.SS1.p4.2.m2.1.5" xref="S3.SS1.p4.2.m2.1.5.cmml"><mi id="S3.SS1.p4.2.m2.1.5.2" xref="S3.SS1.p4.2.m2.1.5.2.cmml">T</mi><mi id="S3.SS1.p4.2.m2.1.5.3" xref="S3.SS1.p4.2.m2.1.5.3.cmml">q</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.SS1.p4.2.m2.1b"><apply id="S3.SS1.p4.2.m2.1.1.cmml" xref="S3.SS1.p4.2.m2.1.1"><ci id="S3.SS1.p4.2.m2.1.1.2.cmml" xref="S3.SS1.p4.2.m2.1.1.2">𝐵</ci><ci id="S3.SS1.p4.2.m2.1.3.cmml" xref="S3.SS1.p4.2.m2.1.3">𝐸</ci><ci id="S3.SS1.p4.2.m2.1.4.cmml" xref="S3.SS1.p4.2.m2.1.4">𝑅</ci><apply id="S3.SS1.p4.2.m2.1.5.cmml" xref="S3.SS1.p4.2.m2.1.5"><csymbol cd="ambiguous" id="S3.SS1.p4.2.m2.1.5.1.cmml" xref="S3.SS1.p4.2.m2.1.5">subscript</csymbol><ci id="S3.SS1.p4.2.m2.1.5.2.cmml" xref="S3.SS1.p4.2.m2.1.5.2">𝑇</ci><ci id="S3.SS1.p4.2.m2.1.5.3.cmml" xref="S3.SS1.p4.2.m2.1.5.3">𝑞</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS1.p4.2.m2.1c">BERT_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.SS1.p4.2.m2.1d">italic_B italic_E italic_R italic_T start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>

RAG 的一个有趣方面是它如何融合所有检索到的文献中的知识，以产生最终的回答。在 RAG 的两个提议版本中，RAG-token 和 RAG-sequence，融合是在解码器之后立即进行的。

具体来说，RAG-token：

+   •

    对于每个检索到的文档<math alttext="z" class="ltx_Math" display="inline" id="S3.I2.i1.p1.1.1"><semantics id="S3.I2.i1.p1.1.1a"><mi id="S3.I2.i1.p1.1.1.1" xref="S3.I2.i1.p1.1.1.1.cmml">z</mi><annotation-xml encoding="MathML-Content" id="S3.I2.i1.p1.1.1b"><ci id="S3.I2.i1.p1.1.1.1.cmml" xref="S3.I2.i1.p1.1.1.1">𝑧</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.I2.i1.p1.1.1c">z</annotation><annotation encoding="application/x-llamapun" id="S3.I2.i1.p1.1.1d">italic_z</annotation></semantics></math>，计算每个标记<math alttext="y_{i}" class="ltx_Math" display="inline" id="S3.I2.i1.p1.2.1"><semantics id="S3.I2.i1.p1.2.1a"><msub id="S3.I2.i1.p1.2.1.1" xref="S3.I2.i1.p1.2.1.1.cmml"><mi id="S3.I2.i1.p1.2.1.1.2" xref="S3.I2.i1.p1.2.1.1.2.cmml">y</mi><mi id="S3.I2.i1.p1.2.1.1.3" xref="S3.I2.i1.p1.2.1.1.3.cmml">i</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I2.i1.p1.2.1b"><apply id="S3.I2.i1.p1.2.1.1.cmml" xref="S3.I2.i1.p1.2.1.1"><csymbol cd="ambiguous" id="S3.I2.i1.p1.2.1.1.1.cmml" xref="S3.I2.i1.p1.2.1.1">subscript</csymbol><ci id="S3.I2.i1.p1.2.1.1.2.cmml" xref="S3.I2.i1.p1.2.1.1.2">𝑦</ci><ci id="S3.I2.i1.p1.2.1.1.3.cmml" xref="S3.I2.i1.p1.2.1.1.3">𝑖</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I2.i1.p1.2.1c">y_{i}</annotation><annotation encoding="application/x-llamapun" id="S3.I2.i1.p1.2.1d">italic_y start_POSTSUBSCRIPT italic_i end_POSTSUBSCRIPT</annotation></semantics></math>在词汇表中成为序列中的下一个标记的概率：

    |  | <math alttext="p_{\theta}(y_{i}&#124;x,z,y_{1:i-1})\\ " class="ltx_Math" display="block" id="S3.E2.m1.3"><semantics id="S3.E2.m1.3a"><mrow id="S3.E2.m1.3.3" xref="S3.E2.m1.3.3.cmml"><msub id="S3.E2.m1.3.3.3" xref="S3.E2.m1.3.3.3.cmml"><mi id="S3.E2.m1.3.3.3.2" xref="S3.E2.m1.3.3.3.2.cmml">p</mi><mi id="S3.E2.m1.3.3.3.3" xref="S3.E2.m1.3.3.3.3.cmml">θ</mi></msub><mo id="S3.E2.m1.3.3.2" xref="S3.E2.m1.3.3.2.cmml">⁢</mo><mrow id="S3.E2.m1.3.3.1.1" xref="S3.E2.m1.3.3.1.1.1.cmml"><mo id="S3.E2.m1.3.3.1.1.2" stretchy="false" xref="S3.E2.m1.3.3.1.1.1.cmml">(</mo><mrow id="S3.E2.m1.3.3.1.1.1" xref="S3.E2.m1.3.3.1.1.1.cmml"><msub id="S3.E2.m1.3.3.1.1.1.3" xref="S3.E2.m1.3.3.1.1.1.3.cmml"><mi id="S3.E2.m1.3.3.1.1.1.3.2" xref="S3.E2.m1.3.3.1.1.1.3.2.cmml">y</mi><mi id="S3.E2.m1.3.3.1.1.1.3.3" xref="S3.E2.m1.3.3.1.1.1.3.3.cmml">i</mi></msub><mo fence="false" id="S3.E2.m1.3.3.1.1.1.2" xref="S3.E2.m1.3.3.1.1.1.2.cmml">&#124;</mo><mrow id="S3.E2.m1.3.3.1.1.1.1.1" xref="S3.E2.m1.3.3.1.1.1.1.2.cmml"><mi id="S3.E2.m1.1.1" xref="S3.E2.m1.1.1.cmml">x</mi><mo id="S3.E2.m1.3.3.1.1.1.1.1.2" xref="S3.E2.m1.3.3.1.1.1.1.2.cmml">,</mo><mi id="S3.E2.m1.2.2" xref="S3.E2.m1.2.2.cmml">z</mi><mo id="S3.E2.m1.3.3.1.1.1.1.1.3" xref="S3.E2.m1.3.3.1.1.1.1.2.cmml">,</mo><msub id="S3.E2.m1.3.3.1.1.1.1.1.1" xref="S3.E2.m1.3.3.1.1.1.1.1.1.cmml"><mi id="S3.E2.m1.3.3.1.1.1.1.1.1.2" xref="S3.E2.m1.3.3.1.1.1.1.1.1.2.cmml">y</mi><mrow id="S3.E2.m1.3.3.1.1.1.1.1.1.3" xref="S3.E2.m1.3.3.1.1.1.1.1.1.3.cmml"><mn id="S3.E2.m1.3.3.1.1.1.1.1.1.3.2" xref="S3.E2.m1.3.3.1.1.1.1.1.1.3.2.cmml">1</mn><mo id="S3.E2.m1.3.3.1.1.1.1.1.1.3.1" lspace="0.278em" rspace="0.278em" xref="S3.E2.m1.3.3.1.1.1.1.1.1.3.1.cmml">:</mo><mrow id="S3.E2.m1.3.3.1.1.1.1.1.1.3.3" xref="S3.E2.m1.3.3.1.1.1.1.1.1.3.3.cmml"><mi id="S3.E2.m1.3.3.1.1.1.1.1.1.3.3.2" xref="S3.E2.m1.3.3.1.1.1.1.1.1.3.3.2.cmml">i</mi><mo id="S3.E2.m1.3.3.1.1.1.1.1.1.3.3.1" xref="S3.E2.m1.3.3.1.1.1.1.1.1.3.3.1.cmml">−</mo><mn id="S3.E2.m1.3.3.1.1.1.1.1.1.3.3.3" xref="S3.E2.m1.3.3.1.1.1.1.1.1.3.3.3.cmml">1</mn></mrow></mrow></msub></mrow></mrow><mo id="S3.E2.m1.3.3.1.1.3" stretchy="false" xref="S3.E2.m1.3.3.1.1.1.cmml">)</mo></mrow></mrow><annotation-xml encoding="MathML-Content" id="S3.E2.m1.3b"><apply id="S3.E2.m1.3.3.cmml" xref="S3.E2.m1.3.3"><apply id="S3.E2.m1.3.3.3.cmml" xref="S3.E2.m1.3.3.3"><csymbol cd="ambiguous" id="S3.E2.m1.3.3.3.1.cmml" xref="S3.E2.m1.3.3.3">下标</csymbol><ci id="S3.E2.m1.3.3.3.2.cmml" xref="S3.E2.m1.3.3.3.2">𝑝</ci><ci id="S3.E2.m1.3.3.3.3.cmml" xref="S3.E2.m1.3.3.3.3">𝜃</ci></apply><apply id="S3.E2.m1.3.3.1.1.1.cmml" xref="S3.E2.m1.3.3.1.1"><csymbol cd="latexml" id="S3.E2.m1.3.3.1.1.1.2.cmml" xref="S3.E2.m1.3.3.1.1.1.2">条件</csymbol><apply id="S3.E2.m1.3.3.1.1.1.3.cmml" xref="S3.E2.m1.3.3.1.1.1.3"><csymbol cd="ambiguous" id="S3.E2.m1.3.3.1.1.1.3.1.cmml" xref="S3.E2.m1.3.3.1.1.1.3">下标</csymbol><ci id="S3.E2.m1.3.3.1.1.1.3.2.cmml" xref="S3.E2.m1.3.3.1.1.1.3.2">𝑦</ci><ci id="S3.E2.m1.3.3.1.1.1.3.3.cmml" xref="S3.E2.m1.3.3.1.1.1.3.3">𝑖</ci></apply><list id="S3 |
    | --- | --- |

+   •

    对所有检索到的文档进行概率求和（边际化）：

    | 该公式为 **p_{\theta}^{{}^{\prime}}(y_{i}&#124;x,y_{1:i-1})=\sum_{z}{p_{\eta}(z&#124;x)\cdot p_{% \theta}(y_{i}&#124;x,z,y_{1:i-1})}\\**。 |
    | --- |

+   •

    运行 Beam Search 以找到 K 个最可能的下一个标记

+   •

    选择具有最高转换概率的标记，`y_{i}`

RAG-sequence 模型相对容易掌握。它仅考虑每个生成序列中的一个检索文档。具体来说，对于每个检索文档，它进行 Beam Search 以生成 K 个序列。然后，它简单地返回具有最高概率的序列。

### III-B REALM [30]

REALM 是第一个成功实现检索器和生成器联合预训练的方法。REALM 的作者提出了针对该架构的三个训练阶段：

+   •

    初始化

+   •

    预训练

+   •

    微调

REALM 面临的一个重大挑战是，在训练开始时，查询和文档编码器，<math alttext="Embed_{input}" class="ltx_Math" display="inline" id="S3.SS2.p2.1.m1.1"><semantics id="S3.SS2.p2.1.m1.1a"><mrow id="S3.SS2.p2.1.m1.1.1" xref="S3.SS2.p2.1.m1.1.1.cmml"><mi id="S3.SS2.p2.1.m1.1.1.2" xref="S3.SS2.p2.1.m1.1.1.2.cmml">E</mi><mo id="S3.SS2.p2.1.m1.1.1.1" xref="S3.SS2.p2.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.SS2.p2.1.m1.1.1.3" xref="S3.SS2.p2.1.m1.1.1.3.cmml">m</mi><mo id="S3.SS2.p2.1.m1.1.1.1a" xref="S3.SS2.p2.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.SS2.p2.1.m1.1.1.4" xref="S3.SS2.p2.1.m1.1.1.4.cmml">b</mi><mo id="S3.SS2.p2.1.m1.1.1.1b" xref="S3.SS2.p2.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.SS2.p2.1.m1.1.1.5" xref="S3.SS2.p2.1.m1.1.1.5.cmml">e</mi><mo id="S3.SS2.p2.1.m1.1.1.1c" xref="S3.SS2.p2.1.m1.1.1.1.cmml">⁢</mo><msub id="S3.SS2.p2.1.m1.1.6" xref="S3.SS2.p2.1.m1.1.6.cmml"><mi id="S3.SS2.p2.1.m1.1.6.2" xref="S3.SS2.p2.1.m1.1.6.2.cmml">d</mi><mrow id="S3.SS2.p2.1.m1.1.6.3" xref="S3.SS2.p2.1.m1.1.6.3.cmml"><mi id="S3.SS2.p2.1.m1.1.6.3.2" xref="S3.SS2.p2.1.m1.1.6.3.2.cmml">i</mi><mo id="S3.SS2.p2.1.m1.1.6.3.1" xref="S3.SS2.p2.1.m1.1.6.3.1.cmml">⁢</mo><mi id="S3.SS2.p2.1.m1.1.6.3.3" xref="S3.SS2.p2.1.m1.1.6.3.3.cmml">n</mi><mo id="S3.SS2.p2.1.m1.1.6.3.1a" xref="S3.SS2.p2.1.m1.1.6.3.1.cmml">⁢</mo><mi id="S3.SS2.p2.1.m1.1.6.3.4" xref="S3.SS2.p2.1.m1.1.6.3.4.cmml">p</mi><mo id="S3.SS2.p2.1.m1.1.6.3.1b" xref="S3.SS2.p2.1.m1.1.6.3.1.cmml">⁢</mo><mi id="S3.SS2.p2.1.m1.1.6.3.5" xref="S3.SS2.p2.1.m1.1.6.3.5.cmml">u</mi><mo id="S3.SS2.p2.1.m1.1.6.3.1c" xref="S3.SS2.p2.1.m1.1.6.3.1.cmml">⁢</mo><mi id="S3.SS2.p2.1.m1.1.6.3.6" xref="S3.SS2.p2.1.m1.1.6.3.6.cmml">t</mi></mrow></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.SS2.p2.1.m1.1b"><apply id="S3.SS2.p2.1.m1.1.1.cmml" xref="S3.SS2.p2.1.m1.1.1"><ci id="S3.SS2.p2.1.m1.1.1.2.cmml" xref="S3.SS2.p2.1.m1.1.1.2">𝐸</ci><ci id="S3.SS2.p2.1.m1.1.1.3.cmml" xref="S3.SS2.p2.1.m1.1.1.3">𝑚</ci><ci id="S3.SS2.p2.1.m1.1.1.4.cmml" xref="S3.SS2.p2.1.m1.1.1.4">𝑏</ci><ci id="S3.SS2.p2.1.m1.1.1.5.cmml" xref="S3.SS2.p2.1.m1.1.1.5">𝑒</ci><apply id="S3.SS2.p2.1.m1.1.1.6.cmml" xref="S3.SS2.p2.1.m1.1.1.6"><csymbol cd="ambiguous" id="S3.SS2.p2.1.m1.1.6.1.cmml" xref="S3.SS2.p2.1.m1.1.6">subscript</csymbol><ci id="S3.SS2.p2.1.m1.1.6.2.cmml" xref="S3.SS2.p2.1.m1.1.6.2">𝑑</ci><apply id="S3.SS2.p2.1.m1.1.6.3.cmml" xref="S3.SS2.p2.1.m1.1.6.3"><ci id="S3.SS2.p2.1.m1.1.6.3.2.cmml" xref="S3.SS2.p2.1.m1.1.6.3.2">𝑖</ci><ci id="S3.SS2.p2.1.m1.1.6.3.3.cmml" xref="S3.SS2.p2.1.m1.1.6.3.3">𝑛</ci><ci id="S3.SS2.p2.1.m1.1.6.3.4.cmml" xref="S3.SS2.p2.1.m1.1.6.3.4">𝑝</ci><ci id="S3.SS2.p2.1.m1.1.6.3.5.cmml" xref="S3.SS2.p2.1.m1.1.6.3.5">𝑢</ci><ci id="S3.SS2.p2.1.m1.1.6.3.6.cmml" xref="S3.SS2.p2.1.m1.1.6.3.6">𝑡</ci></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS2.p2.1.m1.1c">Embed_{input}</annotation><annotation encoding="application/x-llamapun" id="S3.SS2.p2.1.m1.1d">italic_E italic_m italic_b italic_e italic_d start_POSTSUBSCRIPT italic_i italic_n italic_p italic_u italic_t end_POSTSUBSCRIPT</annotation></semantics></math> 和 <math alttext="Embed_{doc}" class="ltx_Math" display="inline" id="S3.SS2.p2.2.m2.1"><semantics id="S3.SS2.p2.2.m2.1a"><mrow id="S3.SS2.p2.2.m2.1.1" xref="S3.SS2.p2.

为了避免这种冷启动问题，作者通过一种称为逆克洛兹任务（Inverse Cloze Task，ICT）的训练目标来进行暖启动（初始化）Retriever (`Embed_{input}` + `Embed_{doc}`)，[31]。该任务的目标是：给定一个句子，模型的最终目的是检索出包含该句子的文档。

在生成器的情况下，作者们使用 BERT 的预训练[24]来热启动它，并使用不区分大小写的 BERT-base 模型（12 层，768 隐藏单元，12 个注意力头）。

在初始化阶段之后，REALM 提出了一种无监督的预训练方法。在预训练迭代过程中，REALM：

1.  1.

    从文本语料库中随机选择句子，并对每个句子的特定标记进行掩码处理

1.  2.

    接收一个掩码查询 q 作为输入。这个查询的例子可能是：“金字塔的[MASK]”

1.  3.

    输出它的标记预测（正确答案是“金字塔”）

1.  4.

    通过参数进行反向传播，<math alttext="\theta" class="ltx_Math" display="inline" id="S3.I4.i4.p1.1.m1.1"><semantics id="S3.I4.i4.p1.1.m1.1a"><mi id="S3.I4.i4.p1.1.m1.1.1" xref="S3.I4.i4.p1.1.m1.1.1.cmml">θ</mi><annotation-xml encoding="MathML-Content" id="S3.I4.i4.p1.1.m1.1b"><ci id="S3.I4.i4.p1.1.m1.1.1.cmml" xref="S3.I4.i4.p1.1.m1.1.1">𝜃</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.I4.i4.p1.1.m1.1c">\theta</annotation><annotation encoding="application/x-llamapun" id="S3.I4.i4.p1.1.m1.1d">italic_θ</annotation></semantics></math> 的检索器 <math alttext="p_{\theta}(z|x)" class="ltx_Math" display="inline" id="S3.I4.i4.p1.2.m2.1"><semantics id="S3.I4.i4.p1.2.m2.1a"><mrow id="S3.I4.i4.p1.2.m2.1.1" xref="S3.I4.i4.p1.2.m2.1.1.cmml"><msub id="S3.I4.i4.p1.2.m2.1.1.3" xref="S3.I4.i4.p1.2.m2.1.1.3.cmml"><mi id="S3.I4.i4.p1.2.m2.1.1.3.2" xref="S3.I4.i4.p1.2.m2.1.1.3.2.cmml">p</mi><mi id="S3.I4.i4.p1.2.m2.1.1.3.3" xref="S3.I4.i4.p1.2.m2.1.1.3.3.cmml">θ</mi></msub><mo id="S3.I4.i4.p1.2.m2.1.1.2" xref="S3.I4.i4.p1.2.m2.1.1.2.cmml">⁢</mo><mrow id="S3.I4.i4.p1.2.m2.1.1.1.1" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.cmml"><mo id="S3.I4.i4.p1.2.m2.1.1.1.1.2" stretchy="false" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.cmml">(</mo><mrow id="S3.I4.i4.p1.2.m2.1.1.1.1.1" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.cmml"><mi id="S3.I4.i4.p1.2.m2.1.1.1.1.1.2" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.2.cmml">z</mi><mo fence="false" id="S3.I4.i4.p1.2.m2.1.1.1.1.1.1" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.1.cmml">|</mo><mi id="S3.I4.i4.p1.2.m2.1.1.1.1.1.3" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.3.cmml">x</mi></mrow><mo id="S3.I4.i4.p1.2.m2.1.1.1.1.3" stretchy="false" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.cmml">)</mo></mrow></mrow><annotation-xml encoding="MathML-Content" id="S3.I4.i4.p1.2.m2.1b"><apply id="S3.I4.i4.p1.2.m2.1.1.cmml" xref="S3.I4.i4.p1.2.m2.1.1"><apply id="S3.I4.i4.p1.2.m2.1.1.3.cmml" xref="S3.I4.i4.p1.2.m2.1.1.3"><csymbol cd="ambiguous" id="S3.I4.i4.p1.2.m2.1.1.3.1.cmml" xref="S3.I4.i4.p1.2.m2.1.1.3">subscript</csymbol><ci id="S3.I4.i4.p1.2.m2.1.1.3.2.cmml" xref="S3.I4.i4.p1.2.m2.1.1.3.2">𝑝</ci><ci id="S3.I4.i4.p1.2.m2.1.1.3.3.cmml" xref="S3.I4.i4.p1.2.m2.1.1.3.3">𝜃</ci></apply><apply id="S3.I4.i4.p1.2.m2.1.1.1.1.1.cmml" xref="S3.I4.i4.p1.2.m2.1.1.1.1"><csymbol cd="latexml" id="S3.I4.i4.p1.2.m2.1.1.1.1.1.1.cmml" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.1">conditional</csymbol><ci id="S3.I4.i4.p1.2.m2.1.1.1.1.1.2.cmml" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.2">𝑧</ci><ci id="S3.I4.i4.p1.2.m2.1.1.1.1.1.3.cmml" xref="S3.I4.i4.p1.2.m2.1.1.1.1.1.3">𝑥</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I4.i4.p1.2.m2.1c">p_{\theta}(z|x)</annotation><annotation encoding="application/x-llamapun" id="S3.I4.i4.p1.2.m2.1d">italic_p start_POSTSUBSCRIPT italic_θ end_POSTSUBSCRIPT ( italic_z | italic_x )</annotation></semantics></math>，以及生成器 <math alttext="\phi" class="ltx_Math" display="inline" id="S3.I4.i4.p1.3.m3.1"><semantics id="S3.I4.i4.p1.3.m3.1a"><mi id="S3.I4.i4.p1.3.m3.1.1" xref="S3.I4.i4.p1.3.m3.1.1.cmml">ϕ</mi><annotation-xml encoding="MathML-Content" id="S3.I4.i4.p1.3.m3.1b"><ci id="S3.I4.i4.p1.3.m3.1.1.cmml" xref="S3.I4.i4.p1.3.m3.1.1">italic-ϕ</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.I4.i4.p1.3.m3.1c">\phi</annotation><annotation encoding="application/x-llamapun" id="S3.I4.i4.p1.3.m3.1d">italic_ϕ</annotation></semantics></math>，的 <math alttext="p_{\phi}(z|x)" class="ltx_Math" display="inline" id="S3.I4.i4.p1.4.m4.1"><semantics id="S3.I4.i4.p1.4.m4.1a"><mrow id="S3.I4.i4.p1.4.m4.1.1" xref="S3.I4.i4.p1.4.m4.1.1.cmml"><msub id="S3.I4.i4.p1.4.m4.1.1.3" xref="S3.I4.i4.p1.4.m4.

在预训练过程中，`Embed_{doc}` 和 `Embed_{input}` 组件会被更新。由于在预训练过程中，`Embed_{doc}` 和 `Embed_{input}` 的参数也会进行更新，以确保维基百科知识库中的文档嵌入与更新后的 Retriever 保持同步，因此在每次反向传播步骤后，REALM 需要：

1.  1.

    重新计算文档嵌入

1.  2.

    重新计算文档索引（以执行 MIPS）

这是一个计算成本高昂的任务，特别是对于像 Wikipedia 这样的大型数据库。因此，REALM 的设计使得嵌入更新每 100 次反向传播步骤后进行，作为一个异步过程。

作者们用于评估 REALM 在开放域问答（Open-QA）上的监督微调方法如下：1\. 他们收集了问答对，例如：（”等边三角形的角度是多少”，“60 度”）。4\. REALM 接收问题作为输入。5\. 它输出其预测结果。6\. 类似于预训练阶段，REALM 通过检索器的参数进行反向传播 `<math alttext="p_{\theta}(z|x)" class="ltx_Math" display="inline" id="S3.SS2.p8.1.m1.1"><semantics id="S3.SS2.p8.1.m1.1a"><mrow id="S3.SS2.p8.1.m1.1.1" xref="S3.SS2.p8.1.m1.1.1.cmml"><msub id="S3.SS2.p8.1.m1.1.1.3" xref="S3.SS2.p8.1.m1.1.1.3.cmml"><mi id="S3.SS2.p8.1.m1.1.1.3.2" xref="S3.SS2.p8.1.m1.1.1.3.2.cmml">p</mi><mi id="S3.SS2.p8.1.m1.1.1.3.3" xref="S3.SS2.p8.1.m1.1.1.3.3.cmml">θ</mi></msub><mo id="S3.SS2.p8.1.m1.1.1.2" xref="S3.SS2.p8.1.m1.1.1.2.cmml">⁢</mo><mrow id="S3.SS2.p8.1.m1.1.1.1.1" xref="S3.SS2.p8.1.m1.1.1.1.1.1.cmml"><mo id="S3.SS2.p8.1.m1.1.1.1.1.2" stretchy="false" xref="S3.SS2.p8.1.m1.1.1.1.1.1.cmml">(</mo><mrow id="S3.SS2.p8.1.m1.1.1.1.1.1" xref="S3.SS2.p8.1.m1.1.1.1.1.1.cmml"><mi id="S3.SS2.p8.1.m1.1.1.1.1.1.2" xref="S3.SS2.p8.1.m1.1.1.1.1.1.2.cmml">z</mi><mo fence="false" id="S3.SS2.p8.1.m1.1.1.1.1.1.1" xref="S3.SS2.p8.1.m1.1.1.1.1.1.1.cmml">|</mo><mi id="S3.SS2.p8.1.m1.1.1.1.1.1.3" xref="S3.SS2.p8.1.m1.1.1.1.1.1.3.cmml">x</mi></mrow><mo id="S3.SS2.p8.1.m1.1.1.1.1.3" stretchy="false" xref="S3.SS2.p8.1.m1.1.1.1.1.1.cmml">)</mo></mrow></mrow><annotation-xml encoding="MathML-Content" id="S3.SS2.p8.1.m1.1b"><apply id="S3.SS2.p8.1.m1.1.cmml" xref="S3.SS2.p8.1.m1.1"><apply id="S3.SS2.p8.1.m1.1.3.cmml" xref="S3.SS2.p8.1.m1.1.3"><csymbol cd="ambiguous" id="S3.SS2.p8.1.m1.1.3.1.cmml" xref="S3.SS2.p8.1.m1.1.3">subscript</csymbol><ci id="S3.SS2.p8.1.m1.1.3.2.cmml" xref="S3.SS2.p8.1.m1.1.3.2">𝑝</ci><ci id="S3.SS2.p8.1.m1.1.3.3.cmml" xref="S3.SS2.p8.1.m1.1.3.3">𝜃</ci></apply><apply id="S3.SS2.p8.1.m1.1.1.1.1.1.cmml" xref="S3.SS2.p8.1.m1.1.1.1.1"><csymbol cd="latexml" id="S3.SS2.p8.1.m1.1.1.1.1.1.1.cmml" xref="S3.SS2.p8.1.m1.1.1.1.1.1.1">conditional</csymbol><ci id="S3.SS2.p8.1.m1.1.1.1.1.1.2.cmml" xref="S3.SS2.p8.1.m1.1.1.1.1.1.2">𝑧</ci><ci id="S3.SS2.p8.1.m1.1.1.1.1.1.3.cmml" xref="S3.SS2.p8.1.m1.1.1.1.1.1.3">𝑥</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS2.p8.1.m1.1c">p_{\theta}(z|x)</annotation><annotation encoding="application/x-llamapun" id="S3.SS2.p8.1.m1.1d">italic_p start_POSTSUBSCRIPT italic_θ end_POSTSUBSCRIPT ( italic_z | italic_x )</annotation></semantics></math>，和 `<math alttext="\phi" class="ltx_Math" display="inline" id="S3.SS2.p8.2.m2.1"><semantics id="S3.SS2.p8.2.m2.1a"><mi id="S3.SS2.p8.2.m2.1.1" xref="S3.SS2.p8.2.m2.1.1.cmml">ϕ</mi><annotation-xml encoding="MathML-Content" id="S3.SS2.p8.2.m2.1b"><ci id="S3.SS2.p8.2.m2.1.1.cmml" xref="S3.SS2.p8.2.m2.1.1">italic-ϕ</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.SS2.p8.2.m2.1c">\phi</annotation><annotation encoding="application/x-llamapun" id="S3.SS2.p8.2.m2.1d">italic_ϕ</annotation></semantics></math>`，生成器的 `<math alttext="p_{\phi}(z|x)" class="ltx_Math" display="inline" id="S3.SS2.p8.3.m3.1"><semantics id="S3.SS2.p8.3.m3.1a"><mrow id="S3.SS2.p8.3.m3.1.1" xref="S3.SS2.p8.3.m3.1.1.cmml"><msub id="S3.SS2.p8.3.m3.1.1.3" xref="S3.SS2.p8.3.m3.1.1.3.cmml"><mi id="S3.SS2.p8.3.m3.1.1.3.2" xref="S3.SS2.p8.3.m3.1.1.3.2.cmml">p</mi><mi id="S3.SS2.p8.3.m3.1.1.3.3" xref="S3.SS2.p8.3.m3.1.1.3.3.cmml">ϕ</mi></msub><mo id="S3.SS2.p8.3.m3.1.1.2" xref="S3.SS2.p8.3.m3.1.1.2.cmml">⁢</mo><mrow id="S3.SS2.p8.3.m3.1.1.1.1" xref="S3.SS2.p8.3.m3.1.1.1.1.1.cmml"><mo id="S3.SS2.p8.3.m3.1.1.1.1.2" stretchy="false" xref="S3.SS

### III-C 解码器中的融合（FiD）

FiD [7] 采用了类似但更简单的思路与 RAG 相比。然而，它们的主要区别在于它们执行检索知识融合的方式。

类似于 RAG，在 FiD 中，我们有两个主要模型：

+   •

    该检索器可以访问一个 <math alttext="BERT_{BASE}" class="ltx_Math" display="inline" id="S3.I6.i1.p1.1.m1.1"><semantics id="S3.I6.i1.p1.1.m1.1"><mrow id="S3.I6.i1.p1.1.m1.1.1" xref="S3.I6.i1.p1.1.m1.1.1.cmml"><mi id="S3.I6.i1.p1.1.m1.1.1.2" xref="S3.I6.i1.p1.1.m1.1.1.2.cmml">B</mi><mo id="S3.I6.i1.p1.1.m1.1.1.1" xref="S3.I6.i1.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I6.i1.p1.1.m1.1.1.3" xref="S3.I6.i1.p1.1.m1.1.1.3.cmml">E</mi><mo id="S3.I6.i1.p1.1.m1.1.1.1a" xref="S3.I6.i1.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I6.i1.p1.1.m1.1.1.4" xref="S3.I6.i1.p1.1.m1.1.1.4.cmml">R</mi><mo id="S3.I6.i1.p1.1.m1.1.1.1b" xref="S3.I6.i1.p1.1.m1.1.1.1.cmml">⁢</mo><msub id="S3.I6.i1.p1.1.m1.1.1.5" xref="S3.I6.i1.p1.1.m1.1.1.5.cmml"><mi id="S3.I6.i1.p1.1.m1.1.1.5.2" xref="S3.I6.i1.p1.1.m1.1.1.5.2.cmml">T</mi><mrow id="S3.I6.i1.p1.1.m1.1.1.5.3" xref="S3.I6.i1.p1.1.m1.1.1.5.3.cmml"><mi id="S3.I6.i1.p1.1.m1.1.1.5.3.2" xref="S3.I6.i1.p1.1.m1.1.1.5.3.2.cmml">B</mi><mo id="S3.I6.i1.p1.1.m1.1.1.5.3.1" xref="S3.I6.i1.p1.1.m1.1.1.5.3.1.cmml">⁢</mo><mi id="S3.I6.i1.p1.1.m1.1.1.5.3.3" xref="S3.I6.i1.p1.1.m1.1.1.5.3.3.cmml">A</mi><mo id="S3.I6.i1.p1.1.m1.1.1.5.3.1a" xref="S3.I6.i1.p1.1.m1.1.1.5.3.1.cmml">⁢</mo><mi id="S3.I6.i1.p1.1.m1.1.1.5.3.4" xref="S3.I6.i1.p1.1.m1.1.1.5.3.4.cmml">S</mi><mo id="S3.I6.i1.p1.1.m1.1.1.5.3.1b" xref="S3.I6.i1.p1.1.m1.1.1.5.3.1.cmml">⁢</mo><mi id="S3.I6.i1.p1.1.m1.1.1.5.3.5" xref="S3.I6.i1.p1.1.m1.1.1.5.3.5.cmml">E</mi></mrow></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.I6.i1.p1.1.m1.1b"><apply id="S3.I6.i1.p1.1.m1.1.1.cmml" xref="S3.I6.i1.p1.1.m1.1.1"><ci id="S3.I6.i1.p1.1.m1.1.1.2.cmml" xref="S3.I6.i1.p1.1.m1.1.1.2">𝐵</ci><ci id="S3.I6.i1.p1.1.m1.1.1.3.cmml" xref="S3.I6.i1.p1.1.m1.1.1.3">𝐸</ci><ci id="S3.I6.i1.p1.1.m1.1.1.4.cmml" xref="S3.I6.i1.p1.1.m1.1.1.4">𝑅</ci><apply id="S3.I6.i1.p1.1.m1.1.1.5.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5"><csymbol cd="ambiguous" id="S3.I6.i1.p1.1.m1.1.1.5.1.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5">subscript</csymbol><ci id="S3.I6.i1.p1.1.m1.1.1.5.2.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5.2">𝑇</ci><apply id="S3.I6.i1.p1.1.m1.1.1.5.3.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5.3"><ci id="S3.I6.i1.p1.1.m1.1.1.5.3.2.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5.3.2">𝐵</ci><ci id="S3.I6.i1.p1.1.m1.1.1.5.3.3.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5.3.3">𝐴</ci><ci id="S3.I6.i1.p1.1.m1.1.1.5.3.4.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5.3.4">𝑆</ci><ci id="S3.I6.i1.p1.1.m1.1.1.5.3.5.cmml" xref="S3.I6.i1.p1.1.m1.1.1.5.3.5">𝐸</ci></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I6.i1.p1.1.m1.1c">BERT_{BASE}</annotation><annotation encoding="application/x-llamapun" id="S3.I6.i1.p1.1.m1.1d">italic_B italic_E italic_R italic_T start_POSTSUBSCRIPT italic_B italic_A italic_S italic_E end_POSTSUBSCRIPT</annotation></semantics></math> 的检索器，其中文档被表示为密集向量，并通过使用 FAISS 库运行最大内积搜索（MIPS）来检索最相关的文档 [26]。

+   •

    生成器是一个序列到序列的模型，它接收输入查询和检索到的段落的拼接，并被训练以生成答案。对于他们的实验，他们使用了预训练的 T5 [25] seq2seq 模型。

在 FiD 中，检索文档中的知识融合是在解码器之前进行的。具体来说，类似于 RAG，他们将输入查询与每个检索到的段落拼接，并将每个拼接单独输入到编码器（并行）。然而，之后，所有生成的编码向量被拼接在一起（融合），并作为单一向量输入到解码器中，解码器在所有检索到的文档之间执行注意力机制（交叉注意力）。

![参见说明](img/148b2a15d713dae19ad1d6e3480ce1d5.png)

图 2: Fusion-in-Decoder (FiD)[7] 技术概述。输入问题与每个相关段落拼接在一起，所有拼接并行编码。生成的嵌入被拼接在一起（融合），并作为输入传递给解码器。

### III-D Atlas

Atlas [9] 实质上是 RAG 和 FiD 的下一代，但它专注于少量样本学习任务。Atlas 建立在 REALM [30] 之上，并提议联合预训练检索器和生成器模型，与 RAG 不同，RAG 使用预训练模型，并仅在微调阶段联合训练它们。

在执行任务时，从问答到生成维基百科文章，Atlas 首先从大量文本语料库中检索 top-k 相关文档。然后，这些文档与查询一起输入到语言模型中，语言模型生成输出。检索器和语言模型都基于预训练的变换器网络。

Atlas 类似于 FiD，遵循检索器-生成器架构：

+   •

    检索器基于 Contriever 模型 [32]，该模型包括一个 `<math alttext="BERT_{q}" class="ltx_Math" display="inline" id="S3.I7.i1.p1.1.m1.1"><semantics id="S3.I7.i1.p1.1.m1.1a"><mrow id="S3.I7.i1.p1.1.m1.1.1" xref="S3.I7.i1.p1.1.m1.1.1.cmml"><mi id="S3.I7.i1.p1.1.m1.1.1.2" xref="S3.I7.i1.p1.1.m1.1.1.2.cmml">B</mi><mo id="S3.I7.i1.p1.1.m1.1.1.1" xref="S3.I7.i1.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I7.i1.p1.1.m1.1.1.3" xref="S3.I7.i1.p1.1.m1.1.1.3.cmml">E</mi><mo id="S3.I7.i1.p1.1.m1.1.1.1a" xref="S3.I7.i1.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I7.i1.p1.1.m1.1.1.4" xref="S3.I7.i1.p1.1.m1.1.1.4.cmml">R</mi><mo id="S3.I7.i1.p1.1.m1.1.1.1b" xref="S3.I7.i1.p1.1.m1.1.1.1.cmml">⁢</mo><msub id="S3.I7.i1.p1.1.m1.1.5" xref="S3.I7.i1.p1.1.m1.1.5.cmml"><mi id="S3.I7.i1.p1.1.m1.1.5.2" xref="S3.I7.i1.p1.1.m1.1.5.2.cmml">T</mi><mi id="S3.I7.i1.p1.1.m1.1.5.3" xref="S3.I7.i1.p1.1.m1.1.5.3.cmml">q</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.I7.i1.p1.1.m1.1b"><apply id="S3.I7.i1.p1.1.m1.1.1.cmml" xref="S3.I7.i1.p1.1.m1.1.1"><ci id="S3.I7.i1.p1.1.m1.1.1.2.cmml" xref="S3.I7.i1.p1.1.m1.1.1.2">𝐵</ci><ci id="S3.I7.i1.p1.1.m1.1.1.3.cmml" xref="S3.I7.i1.p1.1.m1.1.1.3">𝐸</ci><ci id="S3.I7.i1.p1.1.m1.1.1.4.cmml" xref="S3.I7.i1.p1.1.m1.1.4">𝑅</ci><apply id="S3.I7.i1.p1.1.m1.1.5.cmml" xref="S3.I7.i1.p1.1.m1.1.5"><csymbol cd="ambiguous" id="S3.I7.i1.p1.1.m1.1.5.1.cmml" xref="S3.I7.i1.p1.1.m1.1.5">subscript</csymbol><ci id="S3.I7.i1.p1.1.m1.1.5.2.cmml" xref="S3.I7.i1.p1.1.m1.1.5.2">𝑇</ci><ci id="S3.I7.i1.p1.1.m1.1.5.3.cmml" xref="S3.I7.i1.p1.1.m1.1.5.3">𝑞</ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I7.i1.p1.1.m1.1c">BERT_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.I7.i1.p1.1.m1.1d">italic_B italic_E italic_R italic_T start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>` 编码器和一个 `<math alttext="BERT_{d}" class="ltx_Math" display="inline" id="S3.I7.i1.p1.2.m2.1"><semantics id="S3.I7.i1.p1.2.m2.1a"><mrow id="S3.I7.i1.p1.2.m2.1.1" xref="S3.I7.i1.p1.2.m2.1.1.cmml"><mi id="S3.I7.i1.p1.2.m2.1.1.2" xref="S3.I7.i1.p1.2.m2.1.1.2.cmml">B</mi><mo id="S3.I7.i1.p1.2.m2.1.1.1" xref="S3.I7.i1.p1.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.I7.i1.p1.2.m2.1.1.3" xref="S3.I7.i1.p1.2.m2.1.1.3.cmml">E</mi><mo id="S3.I7.i1.p1.2.m2.1.1.1a" xref="S3.I7.i1.p1.2.m2.1.1.1.cmml">⁢</mo><mi id="S3.I7.i1.p1.2.m2.1.1.4" xref="S3.I7.i1.p1.2.m2.1.1.4.cmml">R</mi><mo id="S3.I7.i1.p1.2.m2.1.1.1b" xref="S3.I7.i1.p1.2.m2.1.1.1.cmml">⁢</mo><msub id="S3.I7.i1.p1.2.m2.1.1.5" xref="S3.I7.i1.p1.2.m2.1.1.5.cmml"><mi id="S3.I7.i1.p1.2.m2.1.1.5.2" xref="S3.I7.i1.p1.2.m2.1.1.5.2.cmml">T</mi><mi id="S3.I7.i1.p1.2.m2.1.1.5.3" xref="S3.I7.i1.p1.2.m2.1.1.5.3.cmml">d</mi></msub></mrow><annotation-xml encoding="MathML-Content" id="S3.I7.i1.p1.2.m2.1b"><apply id="S3.I7.i1.p1.2.m2.1.1.cmml" xref="S3.I7.i1.p1.2.m2.1.1"><ci id="S3.I7.i1.p1.2.m2.1.1.2.cmml" xref="S3.I7.i1.p1.2.m2.1.1.2">𝐵</ci><ci id="S3.I7.i1.p1.2.m2.1.1.3.cmml" xref="S3.I7.i1.p1.2.m2.1.1.3">𝐸</ci><ci id="S3.I7.i1.p1.2.m2.1.1.4.cmml" xref="S3.I7.i1.p1.2.m2.1.1.4">𝑅</ci><apply id="S3.I7.i1.p1.2.m2.1.1.5.cmml" xref="S3.I7.i1.p1.2.m2.1.1.5"><csymbol cd="ambiguous" id="S3.I7.i1.p1.2.m2.1.1.5.1.cmml" xref="S3.I7.i1.p1.2.m2.1.1.5">subscript</csymbol><ci id="S3.I7.i1.p1.2.m2.1.1.5.2.cmml" xref="S3.I7.i1.p1.2.m2.1.1

+   •

    生成器使用 T5 seq2seq 模型 [25]，并应用 FiD 技术，该技术在编码器中单独处理每个文档，然后在进入解码器之前将嵌入向量连接起来。

与 RAG 相反，Atlas 训练了 <math alttext="BERT_{q}" class="ltx_Math" display="inline" id="S3.SS4.p4.1.m1.1">𝐵𝐸𝑅𝑇q</math> 和 <math alttext="BERT_{d}" class="ltx_Math" display="inline" id="S3.SS4.p4.2.m2.1">𝐵𝐸𝑅𝑇d</math> 的嵌入（不仅限于 <math alttext="BERT_{q}" class="ltx_Math" display="inline" id="S3.SS4.p4.3.m3.1">𝐵𝐸𝑅𝑇q</math>）。因此，需要定期更新知识库中每个文档的 <math alttext="BERT_{q}" class="ltx_Math" display="inline" id="S3.SS4.p4.4.m4.1">𝐵𝐸𝑅𝑇q</math> 嵌入，以使其与更新的 <math alttext="BERT_{d}" class="ltx_Math" display="inline" id="S3.SS4.p4.5.m5.1">𝐵𝐸𝑅𝑇d</math> 编码器保持同步。这是一个计算密集型任务。

### III-E RETRO

RETRO 的创建者 [8] 成功地在前所未有的规模上实现了增强语言模型。该工作的突破在于，它成功地用一个相对较小的 Transformer 模型（参数量是 GPT-3 [2] 的 25 倍少）进行了预训练和增强，并且拥有一个 2 万亿标记大的数据库（<math alttext="10^{3}" class="ltx_Math" display="inline" id="S3.SS5.p1.1.m1.1"><semantics id="S3.SS5.p1.1.m1.1a"><msup id="S3.SS5.p1.1.m1.1.1" xref="S3.SS5.p1.1.m1.1.1.cmml"><mn id="S3.SS5.p1.1.m1.1.1.2" xref="S3.SS5.p1.1.m1.1.1.2.cmml">10</mn><mn id="S3.SS5.p1.1.m1.1.1.3" xref="S3.SS5.p1.1.m1.1.3.cmml">3</mn></msup><annotation-xml encoding="MathML-Content" id="S3.SS5.p1.1.m1.1b"><apply id="S3.SS5.p1.1.m1.1.1.cmml" xref="S3.SS5.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S3.SS5.p1.1.m1.1.1.1.cmml" xref="S3.SS5.p1.1.m1.1.1">superscript</csymbol><cn id="S3.SS5.p1.1.m1.1.2.cmml" type="integer" xref="S3.SS5.p1.1.m1.1.2">10</cn><cn id="S3.SS5.p1.1.m1.1.3.cmml" type="integer" xref="S3.SS5.p1.1.m1.1.3">3</cn></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS5.p1.1.m1.1c">10^{3}</annotation><annotation encoding="application/x-llamapun" id="S3.SS5.p1.1.m1.1d">10 start_POSTSUPERSCRIPT 3 end_POSTSUPERSCRIPT</annotation></semantics></math>×大于类似的检索增强型 LLMs）。

正如我们在之前的工作中看到的，例如 RAG、REALM 和 Atlas，将 LLMs 与外部知识库增强的主要困难之一是训练检索器可能会非常耗费计算资源，因为尽管文档编码器变得更好，但数据库中每个段落的嵌入需要重新计算。

在这篇论文中，他们通过使用一个冻结的 BERT 检索器 [24] 完全绕过了这一挑战，该检索器包含了一个预训练的文档编码器。因此，在 RETRO 中，他们在开始时计算文档嵌入，并且不会再次更新它们。结果，访问外部数据库所需的主要瓶颈是检索与输入查询最相关的 K 个文档，他们使用 SCaNN 库 [33] 实现了这一点。这是一个亚线性复杂度的任务，这意味着我们可以在 10 毫秒内查询他们的 2 万亿标记数据库。

RETRO 与以往工作的主要区别在于，RETRO 不检索单个文档（句子），而是检索块（一个检索到的句子及其后续句子）。这使得生成模型能够获取更多上下文信息，并生成更准确的答案。

这里是 RETRO 如何对输入查询 q 生成答案的概述：

1.  1.

    将输入查询拆分成 4 个标记的块

1.  2.

    对于每个块，cq 的 q，RETRO：

    1.  (a)

        计算块的嵌入

    1.  (b)

        在其知识库中找到 2 个最近邻（最相关的文档）

    1.  (c)

        通过编码器对 cq 进行编码

    1.  (d)

        通过编码器对 2 个最近邻进行编码

    1.  (e)

        将最近邻的编码与查询块的嵌入交替使用，以执行交叉注意力。第一个块的邻居仅影响第一个块的最后一个标记和第二个块的第一个标记。

通过这种技术，RETRO 能够在与检索到的段落数量线性相关的复杂度下执行注意力机制。

### III-F GRAFT-Net

GRAFT-Net [10] 是一种新颖的模型，旨在增强问答（QA）性能，特别是在存在结构化图形知识库（三元组存储）和大量文本语料库的场景中。GRAFT-Net 利用图表示学习的进展，通过创建包含文本和知识库实体及关系的问题特定子图来提取答案。

在一系列基准测试中的结果表明，GRAFT-Net 在测试结构化知识库或文本语料库时，表现出与最先进的方法相竞争的性能。

Graft-Net 包括以下阶段：

1.  1.

    问题子图（<math alttext="G_{q}" class="ltx_Math" display="inline" id="S3.I9.i1.p1.1.m1.1"><semantics id="S3.I9.i1.p1.1.m1.1a"><msub id="S3.I9.i1.p1.1.m1.1.1" xref="S3.I9.i1.p1.1.m1.1.1.cmml"><mi id="S3.I9.i1.p1.1.m1.1.1.2" xref="S3.I9.i1.p1.1.m1.1.1.2.cmml">G</mi><mi id="S3.I9.i1.p1.1.m1.1.1.3" xref="S3.I9.i1.p1.1.m1.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I9.i1.p1.1.m1.1b"><apply id="S3.I9.i1.p1.1.m1.1.1.cmml" xref="S3.I9.i1.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S3.I9.i1.p1.1.m1.1.1.1.cmml" xref="S3.I9.i1.p1.1.m1.1.1">subscript</csymbol><ci id="S3.I9.i1.p1.1.m1.1.1.2.cmml" xref="S3.I9.i1.p1.1.m1.1.1.2">𝐺</ci><ci id="S3.I9.i1.p1.1.m1.1.3.cmml" xref="S3.I9.i1.p1.1.m1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I9.i1.p1.1.m1.1c">G_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.I9.i1.p1.1.m1.1d">italic_G start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>) 检索阶段：这是早期融合的特征，即在模型中早期将来自三元组知识库和文本的信息进行结合，即在使用图神经网络之前。

1.  2.

    答案选择阶段，在此阶段，GRAFT-Net 使用一个图卷积网络（GCN）变体 [34] [35] [27] 对<math alttext="G_{q}" class="ltx_Math" display="inline" id="S3.I9.i2.p1.1.m1.1"><semantics id="S3.I9.i2.p1.1.m1.1a"><msub id="S3.I9.i2.p1.1.m1.1.1" xref="S3.I9.i2.p1.1.m1.1.1.cmml"><mi id="S3.I9.i2.p1.1.m1.1.1.2" xref="S3.I9.i2.p1.1.m1.1.1.2.cmml">G</mi><mi id="S3.I9.i2.p1.1.m1.1.1.3" xref="S3.I9.i2.p1.1.m1.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I9.i2.p1.1.m1.1.1.cmml" xref="S3.I9.i2.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S3.I9.i2.p1.1.m1.1.1.1.cmml" xref="S3.I9.i2.p1.1.m1.1.1">subscript</csymbol><ci id="S3.I9.i2.p1.1.m1.1.1.2.cmml" xref="S3.I9.i2.p1.1.m1.1.1.2">𝐺</ci><ci id="S3.I9.i2.p1.1.m1.1.1.3.cmml" xref="S3.I9.i2.p1.1.m1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I9.i2.p1.1.m1.1c">G_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.I9.i2.p1.1.m1.1d">italic_G start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>节点进行二分类（答案，不是答案）。

问题子图<math alttext="G_{q}" class="ltx_Math" display="inline" id="S3.SS6.p4.1.m1.1"><semantics id="S3.SS6.p4.1.m1.1a"><msub id="S3.SS6.p4.1.m1.1.1" xref="S3.SS6.p4.1.m1.1.1.cmml"><mi id="S3.SS6.p4.1.m1.1.1.2" xref="S3.SS6.p4.1.m1.1.1.2.cmml">G</mi><mi id="S3.SS6.p4.1.m1.1.1.3" xref="S3.SS6.p4.1.m1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.SS6.p4.1.m1.1b"><apply id="S3.SS6.p4.1.m1.1.1.cmml" xref="S3.SS6.p4.1.m1.1.1"><csymbol cd="ambiguous" id="S3.SS6.p4.1.m1.1.1.1.cmml" xref="S3.SS6.p4.1.m1.1.1">subscript</csymbol><ci id="S3.SS6.p4.1.m1.1.1.2.cmml" xref="S3.SS6.p4.1.m1.1.2">𝐺</ci><ci id="S3.SS6.p4.1.m1.1.3.cmml" xref="S3.SS6.p4.1.m1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS6.p4.1.m1.1c">G_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.SS6.p4.1.m1.1d">italic_G start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>本质上是整个知识库图的一个副本，其中与给定问题<math alttext="q" class="ltx_Math" display="inline" id="S3.SS6.p4.2.m2.1"><semantics id="S3.SS6.p4.2.m2.1a"><mi id="S3.SS6.p4.2.m2.1.1" xref="S3.SS6.p4.2.m2.1.1.cmml">q</mi><annotation-xml encoding="MathML-Content" id="S3.SS6.p4.2.m2.1b"><ci id="S3.SS6.p4.2.m2.1.1.cmml" xref="S3.SS6.p4.2.m2.1.1">𝑞</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.SS6.p4.2.m2.1c">q</annotation><annotation encoding="application/x-llamapun" id="S3.SS6.p4.2.m2.1d">italic_q</annotation></semantics></math>无关的节点和边会被修剪。此外，问题子图还包含文本文档，但仅包含那些可能包含问题<math alttext="q" class="ltx_Math" display="inline" id="S3.SS6.p4.3.m3.1"><semantics id="S3.SS6.p4.3.m3.1a"><mi id="S3.SS6.p4.3.m3.1.1" xref="S3.SS6.p4.3.m3.1.1.cmml">q</mi><annotation-xml encoding="MathML-Content" id="S3.SS6.p4.3.m3.1b"><ci id="S3.SS6.p4.3.m3.1.1.cmml" xref="S3.SS6.p4.3.m3.1.1">𝑞</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.SS6.p4.3.m3.1c">q</annotation><annotation encoding="application/x-llamapun" id="S3.SS6.p4.3.m3.1d">italic_q</annotation></semantics></math>答案的可能文本文档。

问题子图的检索，<math alttext="G_{q}" class="ltx_Math" display="inline" id="S3.SS6.p5.1.m1.1"><semantics id="S3.SS6.p5.1.m1.1"><msub id="S3.SS6.p5.1.m1.1.1" xref="S3.SS6.p5.1.m1.1.1.cmml"><mi id="S3.SS6.p5.1.m1.1.1.2" xref="S3.SS6.p5.1.m1.1.1.2.cmml">G</mi><mi id="S3.SS6.p5.1.m1.1.1.3" xref="S3.SS6.p5.1.m1.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.SS6.p5.1.m1.1b"><apply id="S3.SS6.p5.1.m1.1.1.cmml" xref="S3.SS6.p5.1.m1.1.1"><csymbol cd="ambiguous" id="S3.SS6.p5.1.m1.1.1.1.cmml" xref="S3.SS6.p5.1.m1.1.1">subscript</csymbol><ci id="S3.SS6.p5.1.m1.1.1.2.cmml" xref="S3.SS6.p5.1.m1.1.1.2">𝐺</ci><ci id="S3.SS6.p5.1.m1.1.1.3.cmml" xref="S3.SS6.p5.1.m1.1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS6.p5.1.m1.1c">G_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.SS6.p5.1.m1.1d">italic_G start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>发生在两个并行管道中：

1.  1.

    知识库检索

1.  2.

    文本检索

在知识库检索过程中，会检索三元组知识库的子图。具体来说，GRAFT-Net：

1.  1.

    检索一组种子实体，<math alttext="Sq" class="ltx_Math" display="inline" id="S3.I11.i1.p1.1.m1.1"><semantics id="S3.I11.i1.p1.1.m1.1a"><mrow id="S3.I11.i1.p1.1.m1.1.1" xref="S3.I11.i1.p1.1.m1.1.1.cmml"><mi id="S3.I11.i1.p1.1.m1.1.1.2" xref="S3.I11.i1.p1.1.m1.1.1.2.cmml">S</mi><mo id="S3.I11.i1.p1.1.m1.1.1.1" xref="S3.I11.i1.p1.1.m1.1.1.1.cmml">⁢</mo><mi id="S3.I11.i1.p1.1.m1.1.1.3" xref="S3.I11.i1.p1.1.m1.1.1.3.cmml">q</mi></mrow><annotation-xml encoding="MathML-Content" id="S3.I11.i1.p1.1.m1.1b"><apply id="S3.I11.i1.p1.1.m1.1.1.cmml" xref="S3.I11.i1.p1.1.m1.1.1"><ci id="S3.I11.i1.p1.1.m1.1.2.cmml" xref="S3.I11.i1.p1.1.m1.1.1.2">𝑆</ci><ci id="S3.I11.i1.p1.1.m1.1.3.cmml" xref="S3.I11.i1.p1.1.m1.1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I11.i1.p1.1.m1.1c">Sq</annotation><annotation encoding="application/x-llamapun" id="S3.I11.i1.p1.1.m1.1d">italic_S italic_q</annotation></semantics></math>，这些实体与问题<math alttext="q" class="ltx_Math" display="inline" id="S3.I11.i1.p1.2.m2.1"><semantics id="S3.I11.i1.p1.2.m2.1a"><mi id="S3.I11.i1.p1.2.m2.1.1" xref="S3.I11.i1.p1.2.m2.1.1.cmml">q</mi><annotation-xml encoding="MathML-Content" id="S3.I11.i1.p1.2.m2.1b"><ci id="S3.I11.i1.p1.2.m2.1.1.cmml" xref="S3.I11.i1.p1.2.m2.1.1">𝑞</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.I11.i1.p1.2.m2.1c">q</annotation><annotation encoding="application/x-llamapun" id="S3.I11.i1.p1.2.m2.1d">italic_q</annotation></semantics></math>相关。

1.  2.

    运行个性化 PageRank（PPR）方法[36]以识别其他可能作为问题答案的实体。在 PPR 过程中，我们给种子实体周围的边分配权重。每条边的权重本质上是以下两个向量之间的余弦相似度：

    +   •

        问题向量，v(q)：问题中所有词向量的平均值

    +   •

        关系向量，v(r)：与该边对应的关系中所有词向量的平均值

1.  3.

    保留顶级 E 实体 <math alttext="v_{1}" class="ltx_Math" display="inline" id="S3.I11.i3.p1.1.m1.1"><semantics id="S3.I11.i3.p1.1.m1.1a"><msub id="S3.I11.i3.p1.1.m1.1.1" xref="S3.I11.i3.p1.1.m1.1.1.cmml"><mi id="S3.I11.i3.p1.1.m1.1.1.2" xref="S3.I11.i3.p1.1.m1.1.1.2.cmml">v</mi><mn id="S3.I11.i3.p1.1.m1.1.1.3" xref="S3.I11.i3.p1.1.m1.1.1.3.cmml">1</mn></msub><annotation-xml encoding="MathML-Content" id="S3.I11.i3.p1.1.m1.1b"><apply id="S3.I11.i3.p1.1.m1.1.1.cmml" xref="S3.I11.i3.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S3.I11.i3.p1.1.m1.1.1.1.cmml" xref="S3.I11.i3.p1.1.m1.1.1">subscript</csymbol><ci id="S3.I11.i3.p1.1.m1.1.1.2.cmml" xref="S3.I11.i3.p1.1.m1.1.1.2">𝑣</ci><cn id="S3.I11.i3.p1.1.m1.1.1.3.cmml" type="integer" xref="S3.I11.i3.p1.1.m1.1.1.3">1</cn></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I11.i3.p1.1.m1.1c">v_{1}</annotation><annotation encoding="application/x-llamapun" id="S3.I11.i3.p1.1.m1.1d">italic_v start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT</annotation></semantics></math>，…，<math alttext="v_{E}" class="ltx_Math" display="inline" id="S3.I11.i3.p1.2.m2.1"><semantics id="S3.I11.i3.p1.2.m2.1a"><msub id="S3.I11.i3.p1.2.m2.1.1" xref="S3.I11.i3.p1.2.m2.1.1.cmml"><mi id="S3.I11.i3.p1.2.m2.1.1.2" xref="S3.I11.i3.p1.2.m2.1.1.2.cmml">v</mi><mi id="S3.I11.i3.p1.2.m2.1.1.3" xref="S3.I11.i3.p1.2.m2.1.1.3.cmml">E</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I11.i3.p1.2.m2.1b"><apply id="S3.I11.i3.p1.2.m2.1.1.cmml" xref="S3.I11.i3.p1.2.m2.1.1"><csymbol cd="ambiguous" id="S3.I11.i3.p1.2.m2.1.1.1.cmml" xref="S3.I11.i3.p1.2.m2.1.1">subscript</csymbol><ci id="S3.I11.i3.p1.2.m2.1.1.2.cmml" xref="S3.I11.i3.p1.2.m2.1.1.2">𝑣</ci><ci id="S3.I11.i3.p1.2.m2.1.1.3.cmml" xref="S3.I11.i3.p1.2.m2.1.1.3">𝐸</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I11.i3.p1.2.m2.1c">v_{E}</annotation><annotation encoding="application/x-llamapun" id="S3.I11.i3.p1.2.m2.1d">italic_v start_POSTSUBSCRIPT italic_E end_POSTSUBSCRIPT</annotation></semantics></math> 根据 PPR 分数，以及它们之间的任何边，并将它们添加到问题子图 <math alttext="G_{q}" class="ltx_Math" display="inline" id="S3.I11.i3.p1.3.m3.1"><semantics id="S3.I11.i3.p1.3.m3.1a"><msub id="S3.I11.i3.p1.3.m3.1.1" xref="S3.I11.i3.p1.3.m3.1.1.cmml"><mi id="S3.I11.i3.p1.3.m3.1.1.2" xref="S3.I11.i3.p1.3.m3.1.1.2.cmml">G</mi><mi id="S3.I11.i3.p1.3.m3.1.1.3" xref="S3.I11.i3.p1.3.m3.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I11.i3.p1.3.m3.1b"><apply id="S3.I11.i3.p1.3.m3.1.1.cmml" xref="S3.I11.i3.p1.3.m3.1.1"><csymbol cd="ambiguous" id="S3.I11.i3.p1.3.m3.1.1.1.cmml" xref="S3.I11.i3.p1.3.m3.1.1">subscript</csymbol><ci id="S3.I11.i3.p1.3.m3.1.1.2.cmml" xref="S3.I11.i3.p1.3.m3.1.1.2">𝐺</ci><ci id="S3.I11.i3.p1.3.m3.1.1.3.cmml" xref="S3.I11.i3.p1.3.m3.1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I11.i3.p1.3.m3.1c">G_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.I11.i3.p1.3.m3.1d">italic_G start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>

在文本检索阶段，GRAFT-Net 从维基百科数据库中检索与问题<math alttext="q" class="ltx_Math" display="inline" id="S3.SS6.p9.1.m1.1"><semantics id="S3.SS6.p9.1.m1.1a"><mi id="S3.SS6.p9.1.m1.1.1" xref="S3.SS6.p9.1.m1.1.1.cmml">q</mi><annotation-xml encoding="MathML-Content" id="S3.SS6.p9.1.m1.1b"><ci id="S3.SS6.p9.1.m1.1.1.cmml" xref="S3.SS6.p9.1.m1.1.1">𝑞</ci></annotation-xml><annotation encoding="application/x-tex" id="S3.SS6.p9.1.m1.1c">q</annotation><annotation encoding="application/x-llamapun" id="S3.SS6.p9.1.m1.1d">italic_q</annotation></semantics></math>相关的文档（句子）。文本检索阶段包括以下步骤。GRAFT-Net:

1.  1.

    通过使用加权词袋模型[37]，检索出最相关的 5 篇维基百科文章（文档集合）。

1.  2.

    将这些文章中的句子填充到一个 Lucene 索引 [38] 中（方便在大规模文本语料库中进行数据搜索），并检索排名最高的句子：<math alttext="d_{1}" class="ltx_Math" display="inline" id="S3.I12.i2.p1.1.m1.1"><semantics id="S3.I12.i2.p1.1.m1.1a"><msub id="S3.I12.i2.p1.1.m1.1.1" xref="S3.I12.i2.p1.1.m1.1.1.cmml"><mi id="S3.I12.i2.p1.1.m1.1.1.2" xref="S3.I12.i2.p1.1.m1.1.1.2.cmml">d</mi><mn id="S3.I12.i2.p1.1.m1.1.1.3" xref="S3.I12.i2.p1.1.m1.1.3.cmml">1</mn></msub><annotation-xml encoding="MathML-Content" id="S3.I12.i2.p1.1.m1.1b"><apply id="S3.I12.i2.p1.1.m1.1.1.cmml" xref="S3.I12.i2.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S3.I12.i2.p1.1.m1.1.1.1.cmml" xref="S3.I12.i2.p1.1.m1.1.1">subscript</csymbol><ci id="S3.I12.i2.p1.1.m1.1.1.2.cmml" xref="S3.I12.i2.p1.1.m1.1.1.2">𝑑</ci><cn id="S3.I12.i2.p1.1.m1.1.1.3.cmml" type="integer" xref="S3.I12.i2.p1.1.m1.1.3">1</cn></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I12.i2.p1.1.m1.1c">d_{1}</annotation><annotation encoding="application/x-llamapun" id="S3.I12.i2.p1.1.m1.1d">italic_d start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT</annotation></semantics></math>，…，<math alttext="d_{D}" class="ltx_Math" display="inline" id="S3.I12.i2.p1.2.m2.1"><semantics id="S3.I12.i2.p1.2.m2.1a"><msub id="S3.I12.i2.p1.2.m2.1.1" xref="S3.I12.i2.p1.2.m2.1.1.cmml"><mi id="S3.I12.i2.p1.2.m2.1.1.2" xref="S3.I12.i2.p1.2.m2.1.1.2.cmml">d</mi><mi id="S3.I12.i2.p1.2.m2.1.1.3" xref="S3.I12.i2.p1.2.m2.1.1.3.cmml">D</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I12.i2.p1.2.m2.1b"><apply id="S3.I12.i2.p1.2.m2.1.1.cmml" xref="S3.I12.i2.p1.2.m2.1.1"><csymbol cd="ambiguous" id="S3.I12.i2.p1.2.m2.1.1.1.cmml" xref="S3.I12.i2.p1.2.m2.1.1">subscript</csymbol><ci id="S3.I12.i2.p1.2.m2.1.1.2.cmml" xref="S3.I12.i2.p1.2.m2.1.1.2">𝑑</ci><ci id="S3.I12.i2.p1.2.m2.1.1.3.cmml" xref="S3.I12.i2.p1.2.m2.1.1.3">𝐷</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I12.i2.p1.2.m2.1c">d_{D}</annotation><annotation encoding="application/x-llamapun" id="S3.I12.i2.p1.2.m2.1d">italic_d start_POSTSUBSCRIPT italic_D end_POSTSUBSCRIPT</annotation></semantics></math>。

最终问题图<math alttext="G_{q}" class="ltx_Math" display="inline" id="S3.SS6.p11.1.m1.1"><semantics id="S3.SS6.p11.1.m1.1a"><msub id="S3.SS6.p11.1.m1.1.1" xref="S3.SS6.p11.1.m1.1.1.cmml"><mi id="S3.SS6.p11.1.m1.1.1.2" xref="S3.SS6.p11.1.m1.1.1.2.cmml">G</mi><mi id="S3.SS6.p11.1.m1.1.1.3" xref="S3.SS6.p11.1.m1.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.SS6.p11.1.m1.1b"><apply id="S3.SS6.p11.1.m1.1.1.cmml" xref="S3.SS6.p11.1.m1.1.1"><csymbol cd="ambiguous" id="S3.SS6.p11.1.m1.1.1.1.cmml" xref="S3.SS6.p11.1.m1.1.1">subscript</csymbol><ci id="S3.SS6.p11.1.m1.1.2.cmml" xref="S3.SS6.p11.1.m1.1.2">𝐺</ci><ci id="S3.SS6.p11.1.m1.1.3.cmml" xref="S3.SS6.p11.1.m1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS6.p11.1.m1.1c">G_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.SS6.p11.1.m1.1d">italic_G start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>包括：

+   •

    <math alttext="V_{q}" class="ltx_Math" display="inline" id="S3.I13.i1.p1.1.m1.1"><semantics id="S3.I13.i1.p1.1.m1.1a"><msub id="S3.I13.i1.p1.1.m1.1.1" xref="S3.I13.i1.p1.1.m1.1.1.cmml"><mi id="S3.I13.i1.p1.1.m1.1.1.2" xref="S3.I13.i1.p1.1.m1.1.1.2.cmml">V</mi><mi id="S3.I13.i1.p1.1.m1.1.1.3" xref="S3.I13.i1.p1.1.m1.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I13.i1.p1.1.m1.1b"><apply id="S3.I13.i1.p1.1.m1.1.1.cmml" xref="S3.I13.i1.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S3.I13.i1.p1.1.m1.1.1.1.cmml" xref="S3.I13.i1.p1.1.m1.1.1">subscript</csymbol><ci id="S3.I13.i1.p1.1.m1.1.2.cmml" xref="S3.I13.i1.p1.1.m1.1.2">𝑉</ci><ci id="S3.I13.i1.p1.1.m1.1.3.cmml" xref="S3.I13.i1.p1.1.m1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I13.i1.p1.1.m1.1c">V_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.I13.i1.p1.1.m1.1d">italic_V start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>：所有检索到的实体和文档

+   •

    <math alttext="E_{q}" class="ltx_Math" display="inline" id="S3.I13.i2.p1.1.m1.1"><semantics id="S3.I13.i2.p1.1.m1.1a"><msub id="S3.I13.i2.p1.1.m1.1.1" xref="S3.I13.i2.p1.1.m1.1.1.cmml"><mi id="S3.I13.i2.p1.1.m1.1.1.2" xref="S3.I13.i2.p1.1.m1.1.1.2.cmml">E</mi><mi id="S3.I13.i2.p1.1.m1.1.1.3" xref="S3.I13.i2.p1.1.m1.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.I13.i2.p1.1.m1.1b"><apply id="S3.I13.i2.p1.1.m1.1.1.cmml" xref="S3.I13.i2.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S3.I13.i2.p1.1.m1.1.1.1.cmml" xref="S3.I13.i2.p1.1.m1.1.1">subscript</csymbol><ci id="S3.I13.i2.p1.1.m1.1.1.2.cmml" xref="S3.I13.i2.p1.1.m1.1.2">𝐸</ci><ci id="S3.I13.i2.p1.1.m1.1.3.cmml" xref="S3.I13.i2.p1.1.m1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.I13.i2.p1.1.m1.1c">E_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.I13.i2.p1.1.m1.1d">italic_E start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>：检索到的实体之间的所有关系以及实体和文档之间的所有实体链接

由于图的顶点可以是实体或文档，因此图被认为是：异质的。

### III-G PullNet [11]

PullNet 基于 GRAFT-Net 的进展，利用文本语料库来补充从三元组知识库中提取的信息，以回答多跳问题。三元组中的主语和宾语包含指向文本语料库中相关文档的链接，而 PullNet 使用这些链接生成更多基于事实的答案。

类似于 GRAFT-Net，PullNet 也有一个初始阶段，在这个阶段中，它检索一个问题子图 <math alttext="G_{q}" class="ltx_Math" display="inline" id="S3.SS7.p2.1.m1.1"><semantics id="S3.SS7.p2.1.m1.1a"><msub id="S3.SS7.p2.1.m1.1.1" xref="S3.SS7.p2.1.m1.1.1.cmml"><mi id="S3.SS7.p2.1.m1.1.1.2" xref="S3.SS7.p2.1.m1.1.1.2.cmml">G</mi><mi id="S3.SS7.p2.1.m1.1.1.3" xref="S3.SS7.p2.1.m1.1.1.3.cmml">q</mi></msub><annotation-xml encoding="MathML-Content" id="S3.SS7.p2.1.m1.1b"><apply id="S3.SS7.p2.1.m1.1.1.cmml" xref="S3.SS7.p2.1.m1.1.1"><csymbol cd="ambiguous" id="S3.SS7.p2.1.m1.1.1.1.cmml" xref="S3.SS7.p2.1.m1.1.1">subscript</csymbol><ci id="S3.SS7.p2.1.m1.1.1.2.cmml" xref="S3.SS7.p2.1.m1.1.1.2">𝐺</ci><ci id="S3.SS7.p2.1.m1.1.1.3.cmml" xref="S3.SS7.p2.1.m1.1.1.3">𝑞</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S3.SS7.p2.1.m1.1c">G_{q}</annotation><annotation encoding="application/x-llamapun" id="S3.SS7.p2.1.m1.1d">italic_G start_POSTSUBSCRIPT italic_q end_POSTSUBSCRIPT</annotation></semantics></math>。然而，PullNet 学习如何构建子图，而不是使用临时的子图构建策略。更具体地说，PullNet 依赖于一小组检索操作，每个操作通过从知识库或语料库中检索新信息来扩展图节点。它通过另一个图 CNN 分类器学习何时以及在哪里应用这些“拉取”操作。这个“拉取”分类器是弱监督的，使用问答对进行训练。

最终结果是一个学习到的迭代子图构建过程，它以一个仅包含问题文本及其所含实体的小子图开始，然后逐渐扩展子图，包含来自知识库和语料库的可能有用的信息。这个过程对于多跳问题尤其有效。

## IV 搜索引擎增强生成

使用搜索引擎增强大型语言模型代表了 AI 驱动自然语言处理发展的下一步。搜索引擎为模型提供了通向一个广泛的知识宇宙的门户，这远远超过了外部知识库的访问范围。通过利用搜索引擎的强大功能，这些模型能够接触到全球范围内不断扩展的信息库。这种动态访问不仅提供了丰富的信息，还确保文本生成保持最新，跟上最新的发展，这是外部知识库经常难以实现的，因为它们需要不断更新。

然而，至关重要的是要认识到，通过搜索引擎获得对开放网络的新访问权带来了潜在风险。互联网的信息环境是多样化的，既包含宝贵的知识，也遗憾地存在有害或恶意的内容。当与增强的大型语言模型集成时，可能会不经意间将模型暴露于不适当或不安全的内容中。这引发了对生成响应的可靠性和安全性的担忧，因为模型可能会不小心将有害信息纳入其输出中。

如我们将在接下来的章节中看到的，基于搜索引擎的查询具有这样一个好处：这些查询本质上是为了被人类理解而设计的，从而增强了模型响应的可解释性，并且通过直接注释或反馈具有持续改进的潜力。然而，为了利用 AI 驱动的语言模型与搜索引擎所提供的广泛知识领域的这种共生融合的巨大潜力，必须开发出强有力的保护措施和机制，以减轻与访问潜在有害或恶意内容相关的风险。这将确保将语言模型与搜索引擎相结合不仅能够拓宽其视野，而且保持其输出的完整性和安全性，开创负责任和知情的自然语言理解与互动的新纪元。

### IV-A 互联网增强对话生成（IADG）

如前所述的基于 FAISS 的方法，例如 RAG (III-A ‣ III 知识库增强生成 ‣ 增强 LLM 的知识 误差防范调研 — 学生项目 —")) 和 FiD (III-C ‣ III 知识库增强生成 ‣ 增强 LLM 的知识 误差防范调研 — 学生项目 —"))，可以利用许多为 QA 和对话任务开发的现有方法，但也存在几个缺点。首先，它们可能难以实时更新网络文档。此外，本地 FAISS 部署中可以存储的文档数量可能有限。最后，这些方法将无法利用互联网搜索引擎几十年使用中精细调整的高质量排名。因此，Facebook AI 研究的作者考虑直接使用互联网搜索引擎进行知识检索。

IADG [13] 由两个主要组件组成：

+   •

    一个搜索查询生成器：一个编码器-解码器 Transformer，它将对话上下文作为输入，并生成一个搜索查询。这个查询被传递给黑箱搜索引擎 API，并返回 N 篇文档。

+   •

    一种 FiD 风格的生成器：一个编码器-解码器模型，它单独编码每个文档（连同对话上下文），在进入编码器之前将嵌入连接起来，最终生成下一个响应。

这些组件中的每一个都可以单独训练，前提是拥有两个任务的监督数据。查询生成器需要：（上下文，搜索查询）对，而响应生成器需要：（上下文，响应）对。

搜索引擎在该系统中是一个黑箱（类似于 LaMDA），并且可以被任何方法替换。在 IADG 中，他们使用 Bing 搜索 API [39] 进行实验，以生成每个查询的 URL 列表。然后，他们使用这些 URL 作为键来查找页面内容。

### IV-B SeeKeR

SeeKeR [14]（搜索引擎知识→响应）引入了一种创新的方法，通过使用单一的语言模型来连续处理三个不同的模块任务：信息搜索、知识生成和最终响应的构建。在这项研究工作中，SeeKeR 探索了一种模块化框架，该框架基于 IADG [13] 的基础，同时融合了各种现有解决方案中的最有效元素。

SeeKeR 模型遵循标准 Transformer [19] 的基础架构，但通过以模块化方式反复使用相同模型来加以区分。在每个模块中，编码器（或解码器）使用不同的特殊标记来指示被激活的特定模块。每个模块生成的输出随后被输入到下一个模块，并与原始上下文一起处理。SeeKeR 包含三个专门的模块，每个模块都专注于独特的功能，即：

+   •

    搜索模块：从编码的输入上下文生成一个搜索查询。随后，该查询被发送到 Bing Web 搜索 API [39]，启动一个检索过程，生成 5 个最相关的文档作为结果。

+   •

    知识模块：利用编码的输入上下文和检索到的文档池生成有意义的响应。该响应包括一个或多个直接从检索文档中提取的相关短语或句子。值得注意的是，FiD [7] 方法用于对上下文和文档进行编码。

+   •

    响应模块：在编码的输入上下文与知识响应合并后操作，生成与输入一致且具有上下文相关性的连贯继续部分。

必须强调的是，知识模块本质上涉及一个“复制”机制，因为它不涉及创建新令牌；而是其复杂性在于准确选择相关知识以进行复制。

SeeKeR 的作者将 GPT2 转换器 [18] 作为基础模型，并对其进行微调以成为 SeeKeR 模型。因此，他们在这种情况下没有进行任何预训练。对于他们的实验，他们考虑了中型、大型和 XL（345M、762M 和 1.5B 参数）模型。

### IV-C LaMDA

在 Google 的这篇论文中，LaMDA 的作者 [12] 设法用他们称之为工具集（TS）的黑箱外部知识源来增强语言生成模型。工具集包括：

1.  1.

    一个计算器

1.  2.

    一个翻译器

1.  3.

    一个信息检索系统（类似于搜索引擎）

TS 接受一个字符串作为输入，并输出一个或多个字符串的列表。TS 中的每个工具都期待一个字符串并返回一个字符串列表。例如，信息检索系统可以接收“拉法埃尔·纳达尔多大了？”作为输入，并输出 [“拉法埃尔·纳达尔 / 年龄 / 35”]。

信息检索系统还能够从开放网页中返回内容片段及其对应的 URL。TS 在其所有工具上尝试输入字符串，并通过按以下顺序连接每个工具的输出列表来生成最终输出字符串列表：计算器、翻译器和信息检索系统。如果工具无法解析输入（例如，计算器无法解析“拉法埃尔·纳达尔多大了？”），则工具将返回一个空的结果列表，因此不参与最终输出列表。

必须注意，除了包含一个数据库之外，LaMDA 论文中对信息检索系统如何工作的描述非常有限，但它也可以提供带有 URL 的网页片段。

LaMDA 包含两个主要的子模型，这些子模型遵循仅解码器的 Transformer 架构：

1.  1.

    LaMDA-Base：一种在大数据集上进行预训练的常规生成模型。LaMDA-Base 是第一个接收用户查询的模型。它随后生成一个响应，该响应由 LaMDA-Research 进行检查和完善。

1.  2.

    LaMDA-Research：一种生成模型，通常接收 LaMDA-Base 的输出作为输入，并经过微调以选择其输出的接收者（TS 或用户）。一般来说，LaMDA-Research 在循环中查询 TS，直到获得足够的信息生成最终回应给用户。

| 年份 | ALM | 知识来源 | 检索器 | 生成器 |
| --- | --- | --- | --- | --- |
| 2018 | GRAFT-Net | 图 + 文本 | 个性化 PageRank + DrQA | GCNN |
| 2019 | PullNet | 图 + 文本 | Pull | GCNN |
| 2020 | RAG | 文本 | BERT | seq2seq |
| 2020 | REALM | 文本 | BERT | seq2seq |
| 2021 | FiD | 文本 | BERT | seq2seq |
| 2021 | IADG | 互联网 | seq2seq + 搜索引擎 | 编码器-解码器 Transformer |
| 2022 | LaMDA | 互联网 | 黑箱信息检索系统 | 仅解码器 Transformer |
| 2022 | Atlas | 文本 | Contriever | seq2seq |
| 2022 | RETRO | 文本 | BERT | 编码器-解码器 Transformer |
| 2022 | SeeKeR | 文本 | 编码器-解码器 Transformer | 编码器-解码器 Transformer |

表 I：提到的增强语言模型（ALM）架构概览

## V 限制与讨论

增强的大型语言模型面临一系列重复出现的挑战。这些问题包括偶尔的不一致性、矛盾、事实不准确、潜在的重复以及有限的推理深度等 [40] [41]。

此外，关于生成包含有毒语言和偏见内容的担忧逐渐显现，尤其是在特定的背景和主题中 [42] [43]。另一个值得关注的问题是互联网来源的文档对模型输出的影响，可能导致检索到不希望的内容。许多研究实验依赖于外部开发的搜索引擎，在优化和可靠性方面提供了优势。然而，建立自己的检索系统，如在问答（QA）和语言建模（LM）研究中常见的情况，需要从头开始。

尽管搜索引擎擅长爬取和索引最新的新闻和文档，但这一过程需要大量的工程工作，并对各种应用至关重要。相反，文献中的方法通常依赖于固定的文档数据库，这些数据库随着时间的推移而变得过时。此外，搜索引擎设计用于人机交互，使用自然语言查询和有限的上下文。相比之下，机器生成的查询，如 RAG [6] 等模型，可能编码更多上下文或采用向量编码的查询，尽管这会降低人类可解释性。搜索引擎基于的查询的一个好处是其人类可读性，提供了解释性和通过直接注释或反馈进行改进的潜力。

采用增强技术的语言模型解决了虚假信息的问题，但不能保证事实依据。冲突的检索实例可能导致混合回应。为了提高可靠性，引入信任机制、对检索结果分配不同权重是一个潜在途径。另一个问题是生成的响应可能过于通用，忽视了所包含的知识。

在这项调查中，我们强调了增强型大语言模型面临的这些常见挑战和限制，揭示了语言生成不断发展的格局以及对创新解决方案的迫切需求。

## VI 结论

在这项文献调查中，我们探讨了多项工作，其中语言模型（LMs）通过外部知识的补充，生成了更多上下文相关和最新的响应。在这些研究中，LMs 通过整合相关信息展示了增强上下文的能力，从而促进了对各种问题的有信息的回答。这种增强通常涉及非参数模块的集成，标志着语言建模范式的转变，将这些模型归类为增强型语言模型。

然而，必须承认这种范式转变中的某些限制。虽然增强了外部知识的语言模型（LMs）表现出较少的虚假信息，但它们并不能提供绝对的事实依据。当出现相互冲突的检索结果时，会导致混合答案，这突显了在这一领域继续改进的必要性。此外，当前研究中对推理增强与知识整合相互作用的有限探索，突显了未来研究中的一条有前景的途径。

当我们反思增强型语言模型的格局时，很明显这一领域充满了巨大潜力和兴奋。它代表了朝着深度学习系统下一代迈进的重要一步，这些系统可以进行复杂且有意义的人机交互，同时最小化参数占用。实现增强型 LMs 的全部潜力的旅程仍在继续，未来的创新和调查机会等待着那些希望塑造这一动态领域未来的人。

## 参考文献

+   [1] M. Chen, J. Tworek, H. Jun, Q. Yuan, H. P. de Oliveira Pinto, J. Kaplan, H. Edwards, Y. Burda, N. Joseph, G. Brockman, A. Ray, R. Puri, G. Krueger, M. Petrov, H. Khlaaf, G. Sastry, P. Mishkin, B. Chan, S. Gray, N. Ryder, M. Pavlov, A. Power, L. Kaiser, M. Bavarian, C. Winter, P. Tillet, F. P. Such, D. Cummings, M. Plappert, F. Chantzis, E. Barnes, A. Herbert-Voss, W. H. Guss, A. Nichol, A. Paino, N. Tezak, J. Tang, I. Babuschkin, S. Balaji, S. Jain, W. Saunders, C. Hesse, A. N. Carr, J. Leike, J. Achiam, V. Misra, E. Morikawa, A. Radford, M. Knight, M. Brundage, M. Murati, K. Mayer, P. Welinder, B. McGrew, D. Amodei, S. McCandlish, I. Sutskever, 和 W. Zaremba，“评估在代码上训练的大型语言模型，” 2021。

+   [2] T. B. Brown, B. Mann, N. Ryder, M. Subbiah, J. Kaplan, P. Dhariwal, A. Neelakantan, P. Shyam, G. Sastry, A. Askell, S. Agarwal, A. Herbert-Voss, G. Krueger, T. Henighan, R. Child, A. Ramesh, D. M. Ziegler, J. Wu, C. Winter, C. Hesse, M. Chen, E. Sigler, M. Litwin, S. Gray, B. Chess, J. Clark, C. Berner, S. McCandlish, A. Radford, I. Sutskever, 和 D. Amodei，“语言模型是少样本学习者，” 2020。

+   [3] S. Welleck, I. Kulikov, S. Roller, E. Dinan, K. Cho, 和 J. Weston，“神经文本生成与不确定性训练，” 2019。

+   [4] J. Hoffmann, S. Borgeaud, A. Mensch, E. Buchatskaya, T. Cai, E. Rutherford, D. de Las Casas, L. A. Hendricks, J. Welbl, A. Clark, T. Hennigan, E. Noland, K. Millican, G. van den Driessche, B. Damoc, A. Guy, S. Osindero, K. Simonyan, E. Elsen, J. W. Rae, O. Vinyals, 和 L. Sifre，“训练计算最优的大型语言模型，” 2022。

+   [5] T. Scialom, T. Chakrabarty, 和 S. Muresan，“微调的语言模型是持续学习者，” 2022。

+   [6] P. Lewis, E. Perez, A. Piktus, F. Petroni, V. Karpukhin, N. Goyal, H. Küttler, M. Lewis, W.-t. Yih, T. Rocktäschel *等*，“用于知识密集型自然语言处理任务的检索增强生成，” *神经信息处理系统进展*，第 33 卷，第 9459–9474 页，2020。

+   [7] G. Izacard 和 E. Grave，“利用生成模型的段落检索进行开放领域问答，” 2021。

+   [8] S. Borgeaud, A. Mensch, J. Hoffmann, T. Cai, E. Rutherford, K. Millican, G. van den Driessche, J.-B. Lespiau, B. Damoc, A. Clark, D. de Las Casas, A. Guy, J. Menick, R. Ring, T. Hennigan, S. Huang, L. Maggiore, C. Jones, A. Cassirer, A. Brock, M. Paganini, G. Irving, O. Vinyals, S. Osindero, K. Simonyan, J. W. Rae, E. Elsen, 和 L. Sifre，“通过从万亿个标记中检索来改进语言模型，” 2022。

+   [9] G. Izacard, P. Lewis, M. Lomeli, L. Hosseini, F. Petroni, T. Schick, J. Dwivedi-Yu, A. Joulin, S. Riedel, 和 E. Grave，“Atlas: 通过检索增强的语言模型进行少样本学习，” 2022。

+   [10] H. Sun, B. Dhingra, M. Zaheer, K. Mazaitis, R. Salakhutdinov, 和 W. Cohen, “开放领域问答的早期融合知识库和文本”，见 *《2018 年自然语言处理实证方法会议论文集》*。比利时布鲁塞尔：计算语言学协会，2018 年 10 月-11 月，第 4231–4242 页。 [在线]。可用： [`aclanthology.org/D18-1455`](https://aclanthology.org/D18-1455)

+   [11] H. Sun, T. Bedrax-Weiss, 和 W. W. Cohen, “Pullnet：基于知识库和文本的迭代检索开放领域问答”，2019。

+   [12] R. Thoppilan, D. D. Freitas, J. Hall, N. Shazeer, A. Kulshreshtha, H.-T. Cheng, A. Jin, T. Bos, L. Baker, Y. Du, Y. Li, H. Lee, H. S. Zheng, A. Ghafouri, M. Menegali, Y. Huang, M. Krikun, D. Lepikhin, J. Qin, D. Chen, Y. Xu, Z. Chen, A. Roberts, M. Bosma, V. Zhao, Y. Zhou, C.-C. Chang, I. Krivokon, W. Rusch, M. Pickett, P. Srinivasan, L. Man, K. Meier-Hellstern, M. R. Morris, T. Doshi, R. D. Santos, T. Duke, J. Soraker, B. Zevenbergen, V. Prabhakaran, M. Diaz, B. Hutchinson, K. Olson, A. Molina, E. Hoffman-John, J. Lee, L. Aroyo, R. Rajakumar, A. Butryna, M. Lamm, V. Kuzmina, J. Fenton, A. Cohen, R. Bernstein, R. Kurzweil, B. Aguera-Arcas, C. Cui, M. Croak, E. Chi, 和 Q. Le, “Lamda：对话应用的语言模型”，2022。

+   [13] M. Komeili, K. Shuster, 和 J. Weston, “互联网增强的对话生成”，2021。

+   [14] K. Shuster, M. Komeili, L. Adolphs, S. Roller, A. Szlam, 和 J. Weston, “寻求知识的语言模型：对话和提示生成的模块化搜索”，2022。

+   [15] Y. Bengio, R. Ducharme, 和 P. Vincent, “一种神经概率语言模型”，见 *《神经信息处理系统进展》*，T. Leen, T. Dietterich, 和 V. Tresp 编辑，第 13 卷。MIT Press，2000。 [在线]。可用： [`proceedings.neurips.cc/paper_files/paper/2000/file/728f206c2a01bf572b5940d7d9a8fa4c-Paper.pdf`](https://proceedings.neurips.cc/paper_files/paper/2000/file/728f206c2a01bf572b5940d7d9a8fa4c-Paper.pdf)

+   [16] D. P. Kingma 和 M. Welling, “变分自编码器简介”，*《机器学习基础与趋势》*，第 12 卷，第 4 期，第 307–392 页，2019。 [在线]。可用： [`doi.org/10.1561%2F2200000056`](https://doi.org/10.1561%2F2200000056)

+   [17] I. J. Goodfellow, J. Pouget-Abadie, M. Mirza, B. Xu, D. Warde-Farley, S. Ozair, A. Courville, 和 Y. Bengio, “生成对抗网络”，2014。

+   [18] A. Radford, J. Wu, R. Child, D. Luan, D. Amodei, I. Sutskever *等*，“语言模型是无监督多任务学习者”，*OpenAI 博客*，第 1 卷，第 8 期，第 9 页，2019。

+   [19] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez, L. Kaiser, 和 I. Polosukhin, “注意力机制就是你所需要的”，2023。

+   [20] I. Sutskever, O. Vinyals, 和 Q. V. Le, “序列到序列学习与神经网络”，2014。

+   [21] D. E. Rumelhart, G. E. Hinton, R. J. Williams *等*，“通过误差传播学习内部表示，” 1985 年。

+   [22] M. I. Jordan, “序列顺序：一种并行分布式处理方法，” 见 *心理学进展*。 爱思唯尔，1997 年，第 121 卷，页码 471–495。

+   [23] Y. LeCun, B. Boser, J. Denker, D. Henderson, R. Howard, W. Hubbard 和 L. Jackel, “使用反向传播网络进行手写数字识别，” *神经信息处理系统进展*，第 2 卷，1989 年。

+   [24] J. Devlin, M.-W. Chang, K. Lee 和 K. Toutanova, “Bert: 用于语言理解的深度双向变换器预训练，” 2019 年。

+   [25] C. Raffel, N. Shazeer, A. Roberts, K. Lee, S. Narang, M. Matena, Y. Zhou, W. Li 和 P. J. Liu, “利用统一的文本到文本变换器探索迁移学习的极限，” 2020 年。

+   [26] J. Johnson, M. Douze 和 H. Jégou, “使用 GPU 进行百亿级相似性搜索，” *IEEE 大数据学报*，第 7 卷，第 3 期，页码 535–547，2021 年。

+   [27] M. Schlichtkrull, T. N. Kipf, P. Bloem, R. Van Den Berg, I. Titov 和 M. Welling, “使用图卷积网络建模关系数据，” 见 *语义网：第 15 届国际会议，ESWC 2018，希腊克里特岛赫拉克利翁，2018 年 6 月 3 日至 7 日，会议录 15*。 施普林格，2018 年，页码 593–607。

+   [28] M. Lewis, Y. Liu, N. Goyal, M. Ghazvininejad, A. Mohamed, O. Levy, V. Stoyanov 和 L. Zettlemoyer, “Bart: 用于自然语言生成、翻译和理解的去噪序列到序列预训练，” 2019 年。

+   [29] V. Karpukhin, B. Oğuz, S. Min, P. Lewis, L. Wu, S. Edunov, D. Chen 和 W. tau Yih, “开放域问答的密集段落检索，” 2020 年。

+   [30] K. Guu, K. Lee, Z. Tung, P. Pasupat 和 M.-W. Chang, “Realm: 检索增强语言模型预训练，” 2020 年。

+   [31] K. Lee, M.-W. Chang 和 K. Toutanova, “用于弱监督开放域问答的潜在检索，” 2019 年。

+   [32] G. Izacard, M. Caron, L. Hosseini, S. Riedel, P. Bojanowski, A. Joulin 和 E. Grave, “通过对比学习进行无监督密集信息检索，” 2022 年。

+   [33] R. Guo, P. Sun, E. Lindgren, Q. Geng, D. Simcha, F. Chern 和 S. Kumar, “通过各向异性向量量化加速大规模推理，” 2020 年。

+   [34] T. N. Kipf 和 M. Welling, “使用图卷积网络进行半监督分类，” 2017 年。

+   [35] Y. Li, D. Tarlow, M. Brockschmidt 和 R. Zemel, “门控图序列神经网络，” 2017 年。

+   [36] T. H. Haveliwala, “主题敏感的 PageRank，” 见 *第 11 届国际万维网会议论文集*，系列 WWW ’02。 纽约，NY，USA：计算机协会，2002 年，页码 517–526。 [在线]. 可用: [`doi.org/10.1145/511446.511513`](https://doi.org/10.1145/511446.511513)

+   [37] D. Chen, A. Fisch, J. Weston 和 A. Bordes, “通过阅读维基百科回答开放域问题，” 2017 年。

+   [38] A. S. Foundation. (2011) Apache lucene - 评分。最后访问时间：2011 年 10 月 20 日。[在线]. 可用： [`lucene.apache.org/java/3_4_0/scoring.html`](http://lucene.apache.org/java/3_4_0/scoring.html)

+   [39] Microsoft, “Bing 网络搜索 API，” 2023 年。[在线]. 可用： [`www.microsoft.com/en-us/bing/apis/bing-web-search-api`](https://www.microsoft.com/en-us/bing/apis/bing-web-search-api)

+   [40] S. Roller, E. Dinan, N. Goyal, D. Ju, M. Williamson, Y. Liu, J. Xu, M. Ott, K. Shuster, E. M. Smith, Y.-L. Boureau, 和 J. Weston, “构建开放领域聊天机器人的建议，” 2020 年。

+   [41] L. Ouyang, J. Wu, X. Jiang, D. Almeida, C. L. Wainwright, P. Mishkin, C. Zhang, S. Agarwal, K. Slama, A. Ray, J. Schulman, J. Hilton, F. Kelton, L. Miller, M. Simens, A. Askell, P. Welinder, P. Christiano, J. Leike, 和 R. Lowe, “训练语言模型以遵循人类反馈的指示，” 2022 年。

+   [42] J. Xu, D. Ju, M. Li, Y.-L. Boureau, J. Weston, 和 E. Dinan, “开放领域聊天机器人的安全性建议，” 2021 年。

+   [43] E. Dinan, A. Fan, A. Williams, J. Urbanek, D. Kiela, 和 J. Weston, “女王也很强大：减轻对话生成中的性别偏见，” 见 *2020 年自然语言处理实证方法会议论文集（EMNLP）*。 在线：计算语言学协会，2020 年 11 月，第 8173–8188 页。[在线]. 可用： [`aclanthology.org/2020.emnlp-main.656`](https://aclanthology.org/2020.emnlp-main.656)

生成于 2023 年 9 月 28 日 14:07:29，由 [LATExml![[LOGO]](img/70e087b9e50c3aa663763c3075b0d6c5.png)](http://dlmf.nist.gov/LaTeXML/)

本文使用了以下尚未转换为 HTML 的包。这些是已知问题，正在处理之中。有空闲的开发时间吗？ [我们欢迎贡献者](https://github.com/brucemiller/LaTeXML/issues)。

+   失败：csvsimple

+   失败：datatool
