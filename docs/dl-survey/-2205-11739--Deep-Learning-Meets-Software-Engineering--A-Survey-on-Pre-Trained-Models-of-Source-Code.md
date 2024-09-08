<!--yml

分类：未分类

日期：2024-09-06 19:46:16

-->

# [2205.11739] 深度学习与软件工程：源代码预训练模型的综述

> 来源：[`ar5iv.labs.arxiv.org/html/2205.11739`](https://ar5iv.labs.arxiv.org/html/2205.11739)

# 深度学习与软件工程：

源代码预训练模型的综述

常安·牛¹    楚安·李¹    卜宾¹ 和 文森特·吴²

¹南京大学新型软件技术国家重点实验室，中国南京

²人类语言技术研究所，德克萨斯大学达拉斯分校，美国德克萨斯州理查森

niu.ca@outlook.com, {lcy,luobin}@nju.edu.cn, vince@hlt.utdallas.edu

###### 摘要

近年来，深度学习在软件工程（SE）中的成功应用已经显著。特别是，源代码预训练模型的发展和使用使得在各种软件工程任务中取得了最先进的成果。本文概述了这一快速发展的研究领域，并反思了未来的研究方向。

## 1 引言

从前，软件工程（SE）中的软件智能状态非常原始，许多决策依赖于直觉，最多通过咨询资深开发者 Hassan 和 Xie (2010)。随着多年来软件开发和演化生命周期中生成的数据不断增加，软件开发和演化的范式也从基于人类经验转变为数据驱动的决策。虽然人工智能研究者完全意识到深度学习对计算机视觉和自然语言处理（NLP）等人工智能应用领域的影响，但许多人并未意识到近年来深度学习技术在软件工程任务中的广泛而成功的应用。

尽管取得了成功，深度学习的应用仍然面临挑战。其中一个挑战是需要一个大型、通常成本高昂的注释训练集，以训练深度神经网络中的数百万甚至数十亿个参数。为了应对这一数据注释瓶颈，自然语言处理（NLP）研究人员提出了一种可以被认为是近期深度学习研究突破的想法，即预训练**Dai 和 Le** (2015)；**Howard 和 Ruder** (2018)；**Peters 等** (2018)。与从头开始训练模型（即，使用随机初始化的网络权重）不同，这通常需要大量特定任务的注释数据，可以先在一个或多个所谓的自监督任务（即可以自动生成注释数据，因此大量训练数据随时可用的任务）上进行预训练，以使其权重编码关于语言的一般语言学和常识知识，然后可以将得到的预训练模型微调以使用（可能少量的）特定任务注释训练数据来学习目标任务。已经开发了大量预训练语言模型，并在 NLP 中广泛使用，例如**BERT** **Devlin 等** (2018)，**XLNet** **Yang 等** (2019)，**RoBERTa** **Liu 等** (2019)，**ELECTRA** **Clark 等** (2019)，**GPT-2** **Radford 等** (2019)，**T5** **Raffel 等** (2020)，和**BART** **Lewis 等** (2020)。

这些预训练模型可以应用于软件工程（SE）任务吗？由于源代码可以被视为代码令牌的序列，就像自然语言（NL）可以被视为单词令牌的序列一样，我们原则上可以对这些模型进行源代码的再训练，并将其应用于 SE 任务。然而，在实践中，这并不理想，因为存在一些代码特有的特征，可能没有被这些模型妥善考虑。例如，源代码不像 NL 那样同质化：它由函数体中的代码（用编程语言（PL）编写）和用 NL 编写的可选注释组成。以统一的方式（即，将两者视为令牌序列）对待代码和注释可能不是最好的利用这两种信息源的方法。此外，代码具有语法结构（如在抽象语法树（ASTs）中定义）和语义结构（如在控制流图（CFGs）中定义）。虽然最近 NLP 社区开发了一些语法感知的预训练模型（例如**Xu 等 Xu 等** (2021)），但大多数现有的预训练模型未能利用结构化信息。因此，SE 研究人员在过去几年中开发了许多考虑到源代码特定特征的预训练模型（CodePTMs）。

我们在本文中的目标是提升 AI 受众对 AI 技术（在这种情况下是预训练模型的开发和使用）对 SE（一个重要的 AI 应用领域）影响的意识，特别是通过提供 CodePTMs 的最新发展及其在 SE 任务中的成功应用的调查。我们相信这项调查将特别吸引（1）NLP 研究人员，特别是那些专注于文本摘要和生成的研究人员，因为许多 SE 任务（例如代码摘要）涉及到 NL 生成；以及（2）应用机器学习研究人员，因为这些模型的发展可能会对 SE 产生重大影响。尽管我们的目标受众是 AI 研究人员，但我们认为这篇论文对 SE 技术提供者也非常有吸引力，提升他们对 AI 技术在增强 SE 工具方面的附加价值的认识，以应对软件系统日益增加的复杂性。

| 类型 | I-O | 任务 | 定义 | ID - 数据集 | 指标 |
| --- | --- | --- | --- | --- | --- |
| Und. | C-V | WB | 错误的二进制运算符：检查给定代码是否包含任何不正确的二进制运算符。 | K1 - Kanade et al. Kanade et al. (2020) | Acc |
| ET | 异常类型：预测精确的异常类型。 | K1 - Kanade et al. Kanade et al. (2020) | Acc |
| BD | 错误检测 / 缺陷检测：检查给定函数是否包含缺陷。 | D1 - Devign Zhou et al. (2019) | Acc |
| P1 - Pradel et al. Pradel and Sen (2018) | Acc |
| CD | 克隆检测：确定两个代码片段是否在语义上等价。 | B1 - BigCloneBench Svajlenko et al. (2014) | F1 |
| C1 - CLCDSA Nafi et al. (2019) | P/R/F1 |
| CC | 代码分类：对给定函数的类别进行分类。 | P2 - POJ-104 Mou et al. (2016) | Acc/MAP@R |
| FD | 函数-文档字符串不匹配：确定给定函数与文档字符串是否相符。 | K1 - Kanade et al. Kanade et al. (2020) | Acc |
| C-C | CR | 代码到代码检索：检索与给定查询代码在语义上相似的代码。 | C1 - CLCDSA Nafi et al. (2019) | Acc/MRR/NDCG |
| P2 - POJ-104 Mou et al. (2016) | MAP@R |
| VM | 变量误用定位和修复：识别误用变量的位置并返回正确的变量。 | V1 - Vasic et al. Vasic et al. (2019) | Acc |
| CT | 填空测试：从代码中预测被遮蔽的标记。 | D2 - De Sousa et al. de Sousa and Hasselbring (2021) | Acc |
| NL-C | CS | 代码搜索 / 文本到代码检索：从候选集中找到与给定自然语言描述最相关的代码。 | C2 - CodeSearchNet Husain et al. (2019) | MRR |
| C3 - AdvText Lu et al. (2021) | MRR/F1/Acc |
| Gen. | C-C | CP | 代码补全：预测给定代码上下文中的缺失/后续标记。 | S1 - Svyatkovskiy 等人 Svyatkovskiy 等人 (2020) | RL/EditSim. |
| L1 - Liu 等人 Liu 等人 (2020) | Acc |
| A1 - Alon 等人 Alon 等人 (2020) | Acc@k |
| TL | 代码翻译：将一种编程语言中的代码翻译成另一种编程语言中的代码。 | C4 - Chen 等人 Chen 等人 (2018) | BLEU/Acc/CBLEU |
| T1 - TransCorder Roziere 等人 (2020) | Acc |
| C1 - CLCDSA Nafi 等人 (2019) | BLEU/RL/CIDER |
| BF | 错误修复：通过生成正确版本修复有错误的代码。 | T2 - Tufano 等人 Tufano 等人 (2019b) | BLEU/Acc/CBLEU |
| MG | 变异生成：在有效代码中注入一个真实错误的变异体。 | T3 - Tufano 等人 Tufano 等人 (2019a) | Acc |
| AG | 断言生成：生成正确的单元测试断言语句。 | W1 - Watson 等人 Watson 等人 (2020) | Acc@k |
| C-NL | SU | 代码总结 / 代码文档：生成描述函数功能的文本描述。 | C2 - CodeSearchNet Husain 等人 (2019) | BLEU |
| H1 - Haque 等人 Haque 等人 (2020) | BLEU/RL |
| H2 - Hu 等人 Hu 等人 (2018a) | BLEU |
| H3 - Hu 等人 Hu 等人 (2018b) | BLEU/METEOR |
| M1 - Miceli 等人 Miceli-Barone 和 Sennrich (2017) | BLEU |
| MN | 方法命名 / 极端代码总结：预测给定函数体的函数名称。 | A2 - Allamanis 等人 Allamanis 等人 (2016) | P/R/F1 |
| E1 - ETH Py150 Raychev 等人 (2016) | P/R/F1 |
| NL-C | CG | 代码生成：根据自然语言描述生成代码。 | C5 - CONCODE Iyer 等人 (2018) | BLEU/Acc/CBLEU |

表 1：应用 CodePTMs 的 18 个 SE 任务的分类。

## 2 SE 任务、数据集和评估指标

SE 研究涉及软件系统的设计、开发、维护、测试和演化问题。表格 1 列出了应用预训练模型的关键 SE 任务。从前两列可以看出，我们将每个任务分为两个维度：(1) 任务是否涉及理解（Und.）或生成（Gen.）；以及 (2) 任务假设的输入类型和生成的输出类型（I-O），其中 C、NL 和 V 分别表示代码、自然语言和提取/预测值。

此外，表格 1 显示了每个任务的基准数据集和相应的评估指标。这些指标相当标准。对于检索和分类任务，通常使用诸如 Acc（准确率 Kanade et al. (2020))、Acc@k（前 $k$ 个预测答案的准确率 Watson et al. (2020))、Precision(P)/Recall(R)/F1 Nafi et al. (2019)、MRR（平均倒数排名 Husain et al. (2019))、MAP@R（均值平均精度 Mou et al. (2016)) 和 NDCG（标准化折扣累积增益 Nafi et al. (2019)) 等指标。对于生成任务，使用 NLP 社区为摘要和翻译任务开发的指标，如 BLEU Papineni et al. (2002)、ROUGE-L (RL) Haque et al. (2020)、METEOR Hu et al. (2018b)、CIDER Zhang et al. (2021) 和 EditSim Svyatkovskiy et al. (2020)（基于编辑距离的指标），以及 SE 社区开发的变体，如 CodeBLEU (CBLEU) Ren et al. (2020)。 |

## 3 代码预训练模型

在本节中，我们概述了 SE 社区最近开发的 20 种代码预训练模型。为了使读者更好地了解它们的相似性和差异，以及它们的相对优缺点，我们将它们从四个维度进行分类，如下所述。

### 3.1 架构

|  | 类型 | 任务 | 完整名称及描述 |
| --- | --- | --- | --- |
| N L P | LM | FLM  Svyatkovskiy et al. (2020) | 前向语言模型：通过将前面的词作为上下文，最大化所有词的条件概率。 |
| FNP Qi et al. (2021) | 未来 N-gram 预测：FLM 的一种变体，涉及同时预测下一个 $n$ 个 ($n>1$) 标记，而不是一个标记。 |
| BiLM  Karampatsis and Sutton (2020) | 双向语言模型：结合前向语言模型和后向语言模型，联合最大化两个方向上标记的可能性。 |
| MLM | BMLM  de Sousa and Hasselbring (2021) | MLM 的基础版本：随机遮蔽输入中某个百分比的标记，然后预测这些被遮蔽的标记。 |
| WWM  Buratti et al. (2020) | 全词遮蔽：如果一个词被遮蔽，则遮蔽该词中的所有子词/标记；然后预测这些被遮蔽的标记。 |
| MASS  Niu et al. (2022) | 遮蔽序列到序列：在编码器-解码器框架中，根据句子的其余部分重建句子片段。 |
| SMLM  Mastropaolo et al. (2021) | Seq2Seq MLM：在输入中随机遮蔽一组标记范围，并在编码器-解码器框架中顺序预测这些标记。 |
| DAE | DAE  Ahmad 等人 (2021) | 去噪自编码：通过掩盖、删除 tokens 等方式损坏输入，并使用模型恢复原始输入。 |
| CTL | NSP  Kanade 等人 (2020) | 下一句预测：确定给定的两句话（即逻辑行代码）是否连贯。 |
| RTD  Feng 等人 (2020) | 替换 token 检测：识别输入中被替换的 tokens（即由小型生成网络生成的 tokens）。 |
| S E | CA | IMLM  Liu 等人 (2020) | 标识符 MLM：一种对源代码进行 MLM 的适应，只掩盖代码文本中的标识符。 |
| SIMLM  Wang 等人 (2021b) | Seq2Seq IMLM：对源代码的 Seq2Seq MLM 适应，仅掩盖代码文本中的标识符。 |
| IT  Wang 等人 (2021b) | 标识符标记：通过二分类确定每个位置的输入 token 是否为标识符。 |
| CCL  Peng 等人 (2021) | 代码对比学习：最小化/最大化相似/不相似代码片段表示之间的距离。 |
| SA | EP  Guo 等人 (2021) | 边预测：掩盖 DFG 中随机选择的节点连接的边，然后预测掩盖的边。 |
| NOP  Jiang 等人 (2021) | 节点顺序预测：随机更改 AST 中某些节点的顺序，然后判断是否发生了变化。 |
| C M A | CN | BDG  Wang 等人 (2021b) | 双模态双生成：如果给定代码，则生成 NL 摘要；如果给定 NL，则生成代码。 |
| MNG  Niu 等人 (2022) | 方法名生成：基于给定的方法体生成方法名的子 token 序列。 |
| CS | NA  Guo 等人 (2021) | 节点对齐：在 DFG 中采样节点，掩盖连接每个节点与其代码 token 的边，然后预测掩盖的边。 |
| TMLM  Jiang 等人 (2021) | 树状 MLM：在编码器/解码器侧掩盖 AST/code 中的某些终端节点/标识符，然后生成完整的代码序列。 |
| VGVAE  Zhang 等人 (2021) | vMF-高斯变分自编码器：在掩盖 AST 的监督下，将代码语义与代码语法解耦。 |
| CAP  Niu 等人 (2022) | 代码-AST 预测：确定给定的代码和 AST 是否相互对应。 |
| CLR  Zhang 等人 (2021) | 跨语言重建：从其他编程语言中功能等效的代码片段重建一种编程语言中的代码片段。 |
| PD  Zhang 等人 (2021) | 后验分布：减少在不同编程语言中功能等效的代码片段在代码语义上的分布差异。 |
| ACP  Zhang 等人 (2021) | 注意力代码位置：通过注意力机制预测 AST 中代码 token 的节点类型。 |
| CNS | MCL  王等人 (2021a) | 多模态对比学习：最大化/最小化正样本/负样本之间的表示相似性。 |

表 2：现有 CodePTMs 使用的预训练任务的分类和描述。

首先，现有的 CodePTMs 在底层网络架构上有所不同。为了理解网络架构，我们需要简要介绍编码和解码的概念。编码器将输入序列编码为固定长度的向量表示，而解码器则根据输入的表示生成输出序列。

SE 研究人员并未设计新的网络架构，而是基于现有架构设计 CodePTMs。从大体上来看，这些架构可以分为四类：（1）长短期记忆网络（LSTM Hochreiter and Schmidhuber (1997))，这是一种经典的递归神经网络架构；（2）Transformer (TF) Vaswani et al. (2017)，这是一种较新的编码器-解码器架构¹¹1 回忆一下，编码器-解码器架构通常用于序列到序列的任务，其中编码器将输入序列编码为固定长度的、通常特定于任务的表示，而解码器则根据输入及已生成的令牌逐个生成输出序列。比 LSTM 更快地训练并且能更好地捕捉长距离依赖；（3）Transformer-Encoder (TE)，对应于 TF 的编码器部分架构；（4）Transformer-Decoder (TD)，对应于 TF 的解码器部分架构。虽然可以使用仅编码器模型（如 TE）和仅解码器模型（如 TD）进行序列到序列（seq2seq）任务，但研究表明，这样做是不利且不切实际的 Niu et al. (2022)。特别是，仅编码器模型和仅解码器模型在应用于生成/解码和分类任务时，分别存在劣势。

### 3.2 模态

在使用神经模型处理源代码时，能够将嵌入在代码中的自然语言（例如文档、变量名）与代码结构（例如 AST）结合起来，可以提高模型对代码的理解能力 Ernst (2017); Hu et al. (2018b); LeClair et al. (2019); Zügner et al. (2021)。因此，除了代码本身，使用自然语言和代码结构作为输入已成为 CodePTMs 中的一种常见做法。由于代码、自然语言和结构在表示和处理上存在差异，它们可以被视为不同输入模态的特征。因此，在第二个维度上，我们将 CodePTMs 分为三类——单模态（Uni）、双模态（Bi）和多模态（Multi）——基于它们所采用的输入模态数量。

当一个模型使用多个输入模态时，我们可以选择（1）将从不同模态提取的特征连接起来形成一个训练实例，或者（2）使用从不同模态提取的特征来创建不同的训练实例。我们将这两种策略分别称为 Together 和 Standalone。可以想象，Together 相对于 Standalone 的一个优势是前者允许模型学习跨模态表示。

### 3.3 预训练任务

在第三维度上，我们根据用于预训练 CodePTMs 的任务进行区分。从高层次来看，我们可以根据任务是否源于 NLP（NLP）或专门为源代码设计（SE）来将这些任务分为两类，如表 2 所示。

从表中可以看出，NLP 预训练任务可以细分为四类：（1）语言建模（LM）Qiu 等人（2020），指的是旨在根据上下文预测给定单词的任务；（2）掩码语言建模（MLM）Devlin 等人（2018），指的是旨在预测被掩盖的标记的任务；（3）去噪自编码（DAE）Lewis 等人（2020），旨在从受损文本中恢复原始（即未损坏）文本；（4）对比学习（CTL）Jain 等人（2021），使模型能够学习数据点的相似性或差异性。另一方面，SE 预训练任务可以根据其输入模态分为三类：（1）代码感知（CA）任务，旨在从代码文本中挖掘潜在信息；（2）结构感知（SA）任务，旨在学习代码结构的表示；（3）跨模态感知（CMA）任务，旨在从多个输入模态中获取知识。CMA 任务可以根据涉及的输入模态进一步细分为三类，即 Code-NL（CN）、Code-Structure（CS）和 Code-NL-Structure（CNS）。

| Arch. | Mod. | Pre-Training Tasks | PL | CodePTM | SE Understanding Tasks | SE Generation Tasks |
| --- | --- | --- | --- | --- | --- | --- |
| NLP | CA | SA | CMA | WB | ET | BD | CD | CC | FD | CR | VM | CT | CS | CP | TL | BF | MG | AG | SU | MN | CG |
| LSTM | Uni | ✓ |  |  |  | Mono | SCELMo |  |  | P1 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| Bi |  |  |  | ✓ | Multi | CodeDisen |  |  |  | C1 |  |  | C1 |  |  |  |  | C1 |  |  |  |  |  |  |
| TE | Uni | ✓ |  |  |  | Mono | CuBERT | K1 | K1 |  |  |  | P2 |  | V1 |  |  |  |  |  |  |  |  |  |  |
|  |  |  | C-BERT |  |  | D1 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  | JavaBERT |  |  |  |  |  |  |  |  | D2 |  |  |  |  |  |  |  |  |  |
| ✓ | ✓ |  |  | Multi | CugLM |  |  |  |  |  |  |  |  |  |  | L1 |  |  |  |  |  |  |  |
| Bi | ✓ |  |  |  | Multi | CodeBERT |  |  |  |  |  |  |  |  |  | C2 |  |  |  |  |  | C2 |  |  |
| ✓ | ✓ |  |  | Mono | OSCAR |  |  |  |  | P2 |  | P2 |  |  |  |  |  |  |  |  |  |  |
| Multi | ✓ |  |  | ✓ | Multi | GraphCodeBERT |  |  |  | B1 |  |  |  |  |  | C2 |  | C4 | T2 |  |  |  |  |  |
| ✓ | ✓ | ✓ | ✓ | Multi | SynCoBERT |  |  | D1 | B1 |  |  | P2 |  | C2,C3 | C4 |  |  |  |  |  |  |
| TD | Uni | ✓ |  |  |  | Multi | GPT-C |  |  |  |  |  |  |  |  |  |  | S1 |  |  |  |  |  |  |  |
| TF | Uni |  | ✓ |  |  | Multi | DOBF |  |  |  | B1 |  |  |  |  |  | C3 |  | T1 |  |  |  | C2 |  |  |
| ✓ |  |  |  | Mono | DeepDebug |  |  |  |  |  |  |  |  |  |  |  |  | T2 |  |  |  |  |  |
| Bi | ✓ |  |  |  | Mono | T5-learning |  |  |  |  |  |  |  |  |  |  |  |  | T2 | T3 | W1 | H1 |  |  |
|  |  |  | Multi | PLBART |  |  | D1 | B1 |  |  |  |  |  |  |  | C4 |  |  |  | C2 |  | C5 |
|  |  |  | CoTexT |  |  | D1 |  |  |  |  |  |  |  |  |  | T2 |  |  | C2 |  | C5 |
|  |  |  | ProphetNet-Code |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | C2 |  |  |
| ✓ | ✓ |  | ✓ | Multi | CodeT5 |  |  | D1 | B1 |  |  |  |  |  |  |  | C4 | T2 |  |  | C2 |  | C5 |
|  |  | ✓ | ✓ | Multi | TreeBERT |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | H2 | A2,E1 |
| Multi | ✓ |  |  | ✓ | Multi | SPT-Code |  |  |  |  |  |  |  |  |  | C2 | A1 | C4 | T2 |  | C2,H3,M1 |  |

表 3：现有 CodePTMs 在四个维度的分类及其在下游 SE 任务上的表现。如果一个 CodePTM 应用于某个任务，我们列出该 CodePTM 被评估的基准数据集的 ID（参见表 1 以获取与每个数据集相关的 ID），如果 CodePTM 在相应数据集上获得了 SOTA 结果，则加粗该 ID。

当多个任务用于预训练 CodePTM 时，涉及的任务可以同时学习（即，每个数据实例支持所有相关任务²²2 数据实例支持一个任务，如果该任务的损失可以基于实例计算。例如，仅有代码的数据实例（即，没有配对文档的代码片段）支持 MLM 和 NSP，因为可以基于代码片段计算这两个任务的损失。然而，它不支持 BDG，因为 BDG 需要代码与文档的对齐。任务的损失可以联合最小化）、顺序（即，模型首先在第一个任务上训练指定的步数，然后逐个训练其余任务）或交替（即，任务以随机方式优化，在训练过程中随机选择特定任务的数据实例批次）。因此，同时预训练对数据和任务的要求最严格，因为它要求每个数据实例能够在一次前向传播中完成所有预训练任务，以便它们的损失可以加在一起形成最终的优化目标，并在反向传播期间联合最小化。换句话说，如果它能够执行同时预训练，那么也可以执行顺序/交替预训练，但反之则不然。然而，在现有 CodePTM 中，预训练策略的选择似乎在多种选项可用时是随机的³³3 例如，CodeT5 中的 IT 可以与其他任务同时预训练，但仍然是交替预训练的。

### 3.4 编程语言

在最后一个维度上，我们将 CodePTM 分类为是否在一个编程语言（单语（Mono））或多个编程语言（多语（Multi））上进行预训练。

| CodePTM | 输入 | 目标 | 数据集 | 数据集大小 |
| --- | --- | --- | --- | --- |
| SCELMo Karampatsis 和 Sutton (2020) | 代码 | BiLM | JS GitHub 代码库 | 150K 文件 |
| CodeDisen Zhang 等人 (2021) | 代码 + AST 序列 | VGVAE + CLR + PD + ACP | CLCDSA | 26K 函数 |
| CuBERT Kanade 等人 (2020) | 代码 | BMLM + NSP | Python 来自 BigQuery | 7.4M 文件 |
| C-BERT Buratti 等人 (2020) | 代码 | WWM | C GitHub 代码库 | 5.8GB |
| JavaBERT de Sousa 和 Hasselbring (2021) | 代码 | BMLM | Java GitHub 代码库 | 3M 文件 |
| CugLM Liu 等人 (2020) | 代码 | IMLM + NSP + FLM | Java, TS GitHub 代码库 | 617K 文件 |
| CodeBERT Feng 等人 (2020) | 代码 + 文档 | BMLM & RTD | CodeSearchNet | 6.5M 函数 |
| OSCAR Peng 等人 (2021) | IR + AEI | BMLM + CCL | C/C++ GitHub 代码库 | 500K 函数 |
| GraphCodeBERT Guo 等人 (2021) | 代码 + 文档 + DFG 节点 | BMLM + EP + NA | CodeSearchNet（双模态） | 2.3M 函数 |
| SynCoBERT Wang 等人 (2021a) | 代码 + 文档 + AST 序列 | BMLM + IT + TEP + MCL | CodeSearchNet | 6.5M 函数 |
| GPT-C Svyatkovskiy 等 (2020) | 代码 | FLM | Python, C#, JS/TS GitHub 仓库 | 4.7M 文件 |
| DOBF Roziere 等 (2021) | 代码 | SIMLM（Seq2Seq IMLM） | 从 BigQuery 获取的 Java, Python | 11.5M 文件 |
| DeepDebug Drain 等 (2021) | 代码 | SMLM（Seq2Seq MLM） | Java GitHub 仓库 | 8M 文件 |
| T5-learning Mastropaolo 等 (2021) | 代码 | SMLM（Seq2Seq MLM） | CodeSearchNet（Java） | 1.5M 函数 |
| PLBART Ahmad 等 (2021) | 代码与帖子 | DAE（掩码 / 删除 / 填充） | Java, Python GitHub 仓库 | 680M 函数 |
| StackOverflow 帖子 | 47M 帖子 |
| CoTexT Phan 等 (2021) | 代码 + 文档 | SMLM（Seq2Seq MLM） | CodeSearchNet | 6.5M 函数 |
| 从 BigQuery 获取的 Java, Python | 6.4M 函数 |
| ProphetNet-Code Qi 等 (2021) | 代码与文档 | FNP | CodeSearchNet（双模态） | 2.3M 函数 |
| CodeT5 Wang 等 (2021b) | 代码 + 文档 | SMLM（Seq2Seq MLM） / IT / | CodeSearchNet | 6.5M 函数 |
| SIMLM（Seq2seq IMLM） / BDG | 从 BigQuery 获取的 C, C# | 1.85M 函数 |
| TreeBERT Jiang 等 (2021) | 代码 + AST 路径 | TMLM + NOP | 从 BigQuery 获取的 Java, Python | 21.3M 文件 |
| SPT-Code Niu 等 (2022) | 代码 + 名称 + AST 序列 | CAP & MASS & MNG | CodeSearchNet | 6.5M 函数 |

表 4：CodePTM 的预训练细节。每个 CodePTM 的预训练方案的特征包括 (1) 输入模态（如果涉及多个模态，可以通过 Together (+) 或 Standalone (&) 策略处理）；(2) 预训练目标（如果涉及多个预训练目标，可以通过联合学习（+）、顺序学习（&）或交替学习（/））；(3) CodePTM 的预训练数据集；以及 (4) 数据集的规模。

### 3.5 分类与预训练细节

表 3 的前五列对 20 种 CodePTM 进行分类，涉及前述子章节讨论的四个维度，即架构（Arch.）、模态（Mod.）、预训练任务（Pre-Training Tasks）和编程语言（PL）。我们相信这种分类可以帮助读者更好地理解不同 CodePTM 之间的相似性和差异性。

然而，请注意，表 3 仅提供了 CodePTMs 的高级分类。例如，我们仍然不知道双模态 CodePTM 使用了哪两种输入模态，也不知道多语言 CodePTM 使用了哪些 PL 进行预训练。表 4 填补了这一空白，提供了每个 CodePTM 如何进行预训练的详细信息。具体而言，CodePTM 引用了提出每个 CodePTM 的论文，而 Input、Objective 和 Dataset 显示了输入模态、预训练任务和参与预训练每个 CodePTM 的 PL。数据集可以分为四类，即 GitHub Repos（从 GitHub 获取的数据集，例如，JS GitHub Repos 是由 GitHub JavaScript 仓库构建的数据集）、BigQuery（包括来自超过 300 万个开源 GitHub 仓库的活动的平台，例如，“Python from BigQuery”是通过在 BigQuery 上查询 Python 函数收集的数据集）、CodeSearchNet Husain 等人 (2019)（通过抓取开源仓库并将单个函数与其文档字符串配对获得的数据集，包含超过 640 万行代码，涵盖 Java、Python、JavaScript、PHP、Go 和 Ruby 等 6 种 PL），以及 CLCDSA Nafi 等人 (2019)（从四种 PL（即 Java、Python、C# 和 C++）的在线评测（OJ）网站收集的数据集，其中提供了针对给定问题用不同 PL 编写的功能类似的解决方案）。

## 4 讨论

接下来，我们探讨 CodePTMs（第三部分）与 SE 任务（第二部分）之间的关系。表 3 的右半部分展示了这种关系，通过显示 CodePTM 是否已应用于特定的 SE 任务，以及如果是的话，在哪些基准数据集上进行了评估，以及是否达到了最先进（SOTA）的结果。下面我们将讨论我们的关键观察，这些观察部分基于表 3，部分基于从文献中得出的结论。

#### 架构。

如表 3 所示，基于 TE 的 CodePTMs 主要用于理解任务，而基于 TD 和 TF 的 CodePTMs 则主要用于生成任务。这是可以理解的。如第 3.1 节所述，只有编码器的模型在应用于生成任务时处于劣势。原因在于它们只能将输入序列映射到长度已知的输出序列，但对于生成任务，输出长度通常是未知的。相比之下，基于 TD 和 TF 的 CodePTMs 中解码器的存在自然使它们更适合生成任务。

#### 模态。

我们做了两个与模态相关的观察。首先，对于使用结构化信息作为输入的 CodePTMs（例如，从 DFGs、ASTs 中提取的特征，以及 AEI⁴⁴4AEI（抽象环境信息）用数学方式描述程序行为的语义），从输入中去除这些信息总是会降低它们在下游 SE 任务中的表现 Guo et al. (2021); Zhang et al. (2021); Wang et al. (2021a); Jiang et al. (2021)。

其次，只有当 NL 存在于任务的输入或输出中时，作为输入模态的 NL 才会对模型在下游任务上的性能产生积极贡献 Feng et al. (2020); Niu et al. (2022)。否则，使用 NL 可能会导致性能下降 Phan et al. (2021); Niu et al. (2022)。例如，CodeT5 使用 NL 和 Code 进行预训练，在所有相关的 NL SE 任务中（如 TL、SU 和 MN）都达到了 SOTA 结果，但在 CD 这一仅与 Code 相关的任务中，其性能被仅在 Code 上预训练的 SynCoBERT 超越。

#### 预训练任务。

我们做了两个与预训练任务相关的观察。首先，在任务特定训练数据上进行微调后，预训练模型通常在 SE 下游任务上的结果优于仅在任务特定训练数据上训练的“无预训练”对照模型，并且当任务特定训练数据量较少时，这种性能差异尤为明显 Zhou et al. (2021); Kanade et al. (2020); Buratti et al. (2020); Roziere et al. (2021)。即使底层的预训练模型来自 NLP 领域，例如 RoBERTa，而未在源代码上再次预训练，这一点也是成立的 Feng et al. (2020); Ahmad et al. (2021)。

其次，将预训练任务的类型保持尽可能接近下游任务的类型往往能取得最佳效果。理论上，预训练对于下游任务的好处在于预训练过程中学到的知识能够在模型学习下游任务时被成功利用。如果预训练任务与下游任务更接近，这种知识迁移通常会更加有效。例如，对于理解任务，使用一个也是理解任务的预训练任务，如 MLM，会更好。注意，所有在理解任务上达到 SOTA 结果的模型，如 CuBERT，都使用了 MLM。相比之下，专注于生成任务的(I)MASS，作为预训练任务比专注于理解的(I)MLM 在 seq2seq 下游任务（如代码摘要）上效果要好得多（Jiang et al. (2021)）。

#### 编程语言。

我们做出了两个与编程语言相关的观察。首先，如果 CodePTM 在语法上与下游任务使用的编程语言相似的语言上进行训练，那么知识迁移往往会更加有效。相比之下，CodePTM 从与下游任务使用的编程语言在语法上不同的语言中学到的知识甚至可能导致性能下降。例如，预训练于 Java 和 Python 的 PLBART 在 C#代码翻译上表现更好，但在 PHP 代码摘要上表现比仅在 NL 文本上训练的 RoBERTa 更差。原因是 C#在语法上与 Java 相似，而 PHP 与 Java 和 Python 的语法不匹配。

其次，多语言预训练和微调通常比单语言预训练和微调效果更佳。例如，预训练于 6 种编程语言的 CodeT5 在代码翻译上优于仅预训练于 Java 的 T5-learning 和 DeepDebug。此外，当进行多语言预训练时，语言感知的预训练（例如，通过向输入中添加特定语言的符号或将语言类型嵌入附加到每个标记）往往能够生成一个能更好区分编程语言的预训练模型，相比于语言无关的预训练，这一点在 GPT-C 的代码补全任务中得到了验证。

## 5 CodePTMs 的有效性如何？

CodePTM 已成功应用于各种 SE 任务，但它们的有效性如何？为了让读者对这个问题有深入了解，我们在本节中展示了一些定量结果。具体而言，我们在表格 5 中展示了每个 SE 任务中 CodePTM 在每个常用评估数据集上的最佳结果（见“最佳 CodePTM”列）。为了帮助读者评估 CodePTM 的有效性，我们在“最佳非 CodePTM”列中展示了不涉及预训练的每个数据集上方法的最佳结果。如所示，许多最佳的非 CodePTM 基于方法是涉及 Tree-LSTM 和 Transformer 的神经模型。例如，表格的最后一列显示了每个数据集的相对误差减少率，该率是通过最佳表现的 CodePTM 相对于最佳非 CodePTM 系统在数据集上的误差减少计算得出的。正值表示使用 CodePTM 达到了 SOTA 结果。如所示，所有数据集上的 SOTA 结果都是使用 CodePTM 实现的，相对误差减少率在 0.9–78.7% 之间。这些结果提供了 CodePTM 是各种 SE 任务有前景的方法的暗示性证据。然而，显然 CodePTM 在某些 SE 任务/数据集上的相对误差减少效果优于其他任务/数据集。需要进一步分析以确定原因。

| Task | DS | 最佳 CodePTM | 最佳非 CodePTM | ER |
| --- | --- | --- | --- | --- |
| WB | K1 | 82.3 (CuBERT Kanade et al. (2020)) | 73.8 (GREAT Hellendoorn et al. (2020)) | 32.4 |
| ET | K1 | 79.1 (CuBERT Kanade et al. (2020)) | 49.5 (Transformer Kanade et al. (2020)) | 58.6 |
| BD | D1 | 65.7 (CodeT5 Wang et al. (2021b)) | 62.4 (code2vec Coimbra et al. (2021)) | 8.8 |
| CD | B1 | 97.4 (SynCoBERT Wang et al. (2021a)) | 95.0 (FA-AST Wang et al. (2020)) | 48.0 |
| C1 | 90.0 (CodeDisen Zhang et al. (2021)) | 81.0 (Tree-LSTM Shido et al. (2019) ) | 47.3 |
| CC | P2 | 98.0 (OSCAR Peng et al. (2021)) | 96.6 (ProGraML Peng et al. (2021)) | 43.2 |
| FD | K1 | 98.0 (CuBERT Kanade et al. (2020)) | 91.0 (Transformer Kanade et al. (2020)) | 78.7 |
| CR | C1 | 31.6 (CodeDisen Zhang et al. (2021)) | 16.6 (Pontes et al. Pontes et al. (2018) ) | 17.9 |
| P2 | 88.2 (SynCoBERT Wang et al. (2021a)) | 82.4 (MISIM Ye et al. (2020) ) | 32.9 |
| VM | V1 | 95.2 (CuBERT Kanade et al. (2020)) | 80.5 (BiLSTM Kanade et al. (2020)) | 75.4 |
| CT | D2 | 94.4 (JavaBERT de Sousa and Hasselbring (2021)) | $-$ |  |
| CS | C2 | 74.0 (SynCoBERT Wang et al. (2021a)) | 41.9 (Transformer Guo et al. (2021)) | 55.2 |
| C3 | 38.1 (SynCoBERT Wang et al. (2021a)) | $-$ |  |
| CP | S1 | 82.8 (GPT-C Svyatkovskiy et al. (2020)) | $-$ |  |
| L1 | 81.9 (CugLM Liu et al. (2020)) | 71.7 (Transformer-XL Dai et al. (2019)) | 36.0 |
| A1 | 26.5 (SPT-Code Niu et al. (2022)) | 24.7 (SLM Alon et al. (2020)) | 2.4 |
| TL | C4 | 66.4 (CodeT5 Wang et al. (2021b)) | 35.4 (Transformer Ahmad et al. (2021)) | 47.9 |
| T1 | 41.8 (DOBF Roziere et al. (2021)) | 34.7 (Transformer Roziere et al. (2021)) | 10.9 |
| C1 | 29.7 (CodeDisen Zhang et al. (2021)) | 25.8 (Tree-LSTM Shido et al. (2019)) | 5.3 |
| BF | T2 | 18.3 (CodeT5 Wang et al. (2021b)) | 12.7 (S2S+COPY Panthaplackel et al. (2021)) | 6.5 |
| MG | T3 | 28.0 (T5-learning Mastropaolo et al. (2021)) | 17.0 (Tufano Tufano et al. (2019a)) | 13.3 |
| AG | W1 | 66.0 (T5-learning Mastropaolo et al. (2021)) | 65.0 (Watson et al. Watson et al. (2020)) | 2.9 |
| SU | C2 | 19.7 (CodeT5 Wang et al. (2021b)) | 15.5 (Transformer Kanade et al. (2020)) | 4.9 |
| H1 | 21.0 (T5-learning Mastropaolo et al. (2021)) | 19.0 (Haque et al. Haque et al. (2020)) | 2.5 |
| H2 | 20.4 (TreeBERT Jiang et al. (2021)) | 19.7 (GNN+GRU LeClair et al. (2020)) | 0.9 |
| H3 | 49.1 (SPT-Code Niu et al. (2022)) | 48.2 (AST-Trans Tang et al. (2022)) | 1.6 |
| M1 | 36.1 (SPT-Code Niu et al. (2022)) | 34.7 (AST-Trans Tang et al. (2022)) | 2.1 |
| MN | A2 | 60.1 (TreeBERT Jiang et al. (2021)) | 57.5 (GNN+GRU LeClair et al. (2020)) | 6.1 |
| E1 | 39.0 (TreeBERT Jiang et al. (2021)) | 34.4 (GNN+GRU LeClair et al. (2020)) | 7.0 |
| CG | C5 | 22.3 (CodeT5 Wang et al. (2021b)) | 12.2 (Iyer et al. Iyer et al. (2019)) | 11.5 |

表 5：CodePTMs 在 SE 任务/数据集上的相对误差减少率。 ”DS”展示了每个 SE 任务的常用评估数据集（见表 1 了解这些数据集的详细信息）。 ”最佳 CodePTM”展示了 CodePTM 在相应数据集上迄今为止取得的最佳结果及其名称。 ”最佳非 CodePTM”展示了在相应数据集上迄今为止取得的最佳结果及其名称（注意“$-$”表示非 CodePTM 方法尚未应用于相应的数据集）。 ”ER”展示了每个数据集的相对误差减少率。每个数据集使用的评估指标的信息可以在表 1 中找到。

## 6 结论性评述

尽管 CodePTMs 在 SE 领域已经证明了其成功，我们认为它们还未发挥出全部潜力。在本节中，我们概述了一些有前景的未来方向。

### 6.1 超越 NLP 的思考

#### 分词和嵌入。

目前，CodePTMs 使用在 NLP 中开发的分词和嵌入方法。例如，它们使用 SentencePiece 作为分词器，以及标记和位置嵌入。然而，代码并不完全等同于自然语言：代码包含不同类型的词汇标记，如变量、控制符号和关键字。我们推测，NLP 的分词和嵌入方法可能不会为 CodePTMs 提供最佳性能，并建议研究人员探索开发这些方法的代码特定版本的可能性。

#### 预训练方法。

需要进行更好的利用代码特定特性的预训练任务（例如，代码结构、分支的存在以及使用从广泛不受限制的词汇中提取的不同标识符来表达相同含义）以训练更强大的 CodePTMs。目前大多数现有的 SE 特定预训练任务（见第 3.3 节）仍然未完全跳出 NLP 思维方式。例如，IMLM 只是对 MLM 的一个版本，它掩盖了标识符，实际上，IMLM 上的预训练甚至比 MLM 上的预训练在 DOBF Roziere 等人的研究中（2021）效果更差。我们认为，代码特定预训练方法的设计目前在一定程度上受到现有 NLP 分词和嵌入方法的限制，可能需要对代码特定预训练方法的设计进行根本性的改革，这包括设计代码特定的分词和嵌入方法。

### 6.2 学习代码形式和功能

代码既有形式，这由特定代码标识符的组合定义，也有功能，这与任何特定的代码标识符无关 贾因等人 (2021)。请注意，表 4 中列出的 CodePTMs 都是从“形式”而非“功能”角度学习源代码的。然而，学习代码功能无疑将帮助 CodePTMs 更好地理解代码，并在软件工程（SE）任务中取得更高的性能。因此，我们认为设计能够同时学习代码形式和代码功能的 CodePTMs 将是一个有价值的研究方向。

### 6.3 对下游任务的适应

目前，微调是将预训练过程中获得的知识转移到下游任务的主要方法。然而，微调可能效率低下，因为所有模型参数都需要更新。为了缓解这个问题，自然语言处理（NLP）社区提出了几种解决方案，例如（1）模型重新编程（即，冻结 PTMs 的原始参数，并为特定任务添加小的可微调适配模块 陈 (2022))，（2）使用提示微调 布朗等人 (2020)，以及（3）使用模型压缩（如，剪枝和知识蒸馏）。如何调整或扩展这些方法以微调 CodePTMs 是一个有前景的研究方向。

### 6.4 适用于特定应用的代码预训练模型（CodePTMs）

与其尝试设计一个在所有 SE 任务中表现良好的单一 CodePTM，我们建议为不同类别的 SE 任务（例如，理解与生成）设计专门的 CodePTMs。我们的建议基于我们早期的观察，即不同的模型设计选择可能更适合不同类型的任务。例如，从理论上讲，基于 TE 的模型在理解任务中往往比基于 TD 和 TF 的模型表现更好，而在生成任务中则通常相反。甚至可以设计任务特定的 CodePTMs。原因在于，具有与下游任务更相似的预训练任务可以更有效地转移预训练过程中获得的知识，如前所述。我们相信，专门化的 CodePTMs 还有一个额外的优势：它们通常更小，因此可能更高效，从而有助于解决与模型架构（第 6.1 节）和微调（第 6.3 节）相关的效率问题。

### 6.5 统一评估与分析

我们对现有 CodePTMs 的优缺点的理解目前受到它们被评估的任务的限制。为了更好地理解 CodePTMs，重要的是对所有 CodePTMs 在我们讨论的 18 个 SE 任务相关的所有基准数据集上进行系统评估。除了全面的定量评估外，还需要进行定性分析，以分析每个模型常见的错误。

## 致谢

我们感谢三位匿名审稿人对早期稿件提供的宝贵意见。此项工作部分得到了中国国家自然科学基金（No. 61802167）和美国国家科学基金会（Grant IIS-1528037）的支持。本文中表达的任何观点、发现、结论或建议均为作者个人观点，并不一定反映资助机构的官方意见或政策。李传意为通讯作者。

## 参考文献

+   Ahmad 等 [2021] Wasi Ahmad, Saikat Chakraborty, Baishakhi Ray, 和 Kai-Wei Chang. 统一预训练用于程序理解和生成。发表于 NAACL-HLT, 2021。

+   Allamanis 等 [2016] Miltiadis Allamanis, Hao Peng, 和 Charles Sutton. 用于源代码极端摘要的卷积注意力网络。发表于 ICML, 2016。

+   Alon 等 [2020] Uri Alon, Roy Sadaka, Omer Levy, 和 Eran Yahav. 代码的结构性语言模型。发表于 ICML, 2020。

+   Brown 等 [2020] Tom Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared D Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, Sandhini Agarwal, Ariel Herbert-Voss, Gretchen Krueger, Tom Henighan, Rewon Child, Aditya Ramesh, Daniel Ziegler, Jeffrey Wu, Clemens Winter, Chris Hesse, Mark Chen, Eric Sigler, Mateusz Litwin, Scott Gray, Benjamin Chess, Jack Clark, Christopher Berner, Sam McCandlish, Alec Radford, Ilya Sutskever, 和 Dario Amodei. 语言模型是少量样本学习者。发表于 NeurIPS, 2020。

+   Buratti 等 [2020] Luca Buratti, Saurabh Pujar, Mihaela Bornea, Scott McCarley, Yunhui Zheng, Gaetano Rossiello, Alessandro Morari, Jim Laredo, Veronika Thost, Yufan Zhuang 等。通过神经语言模型探索软件自然性。arXiv:2006.12641, 2020。

+   Chen 等 [2018] Xinyun Chen, Chang Liu, 和 Dawn Song. 树到树的神经网络用于程序翻译。发表于 NeurIPS, 2018。

+   Chen [2022] Pin-Yu Chen. 模型重编程：资源高效的跨域机器学习。arXiv 预印本 arXiv:2202.10629, 2022。

+   Clark 等 [2019] Kevin Clark, Minh-Thang Luong, Quoc V Le, 和 Christopher D Manning. Electra：将文本编码器作为判别器而非生成器进行预训练。发表于 ICLR, 2019。

+   Coimbra 等 [2021] David Coimbra, Sofia Reis, Rui Abreu, Corina Păsăreanu, 和 Hakan Erdogmus. 使用源代码的分布式表示来检测 C 语言安全漏洞。CoRR, 2021。

+   Dai 和 Le [2015]  Andrew M. Dai 和 Q. V. Le. 半监督序列学习。 在 NIPS, 2015.

+   Dai 等 [2019]  Zihang Dai, Zhilin Yang, Yiming Yang, Jaime Carbonell, Quoc V Le, 和 Ruslan Salakhutdinov. Transformer-xl: 超越固定长度上下文的关注语言模型。 在 ACL, 2019.

+   de Sousa 和 Hasselbring [2021]  Nelson Tavares de Sousa 和 Wilhelm Hasselbring. Javabert: 为 Java 编程语言训练的基于变压器的模型。 arXiv:2110.10404, 2021.

+   Devlin 等 [2018]  Jacob Devlin, Ming-Wei Chang, Kenton Lee, 和 Kristina Toutanova. Bert: 深度双向转换器的语言理解预训练。 arXiv:1810.04805, 2018.

+   Drain 等 [2021]  Dawn Drain, Chen Wu, Alexey Svyatkovskiy, 和 Neel Sundaresan. 使用预训练变压器生成错误修复。 在第 5 届 ACM SIGPLAN 国际机器编程研讨会, 2021.

+   Ernst [2017]  Michael D. Ernst. 自然语言是一种编程语言: 将自然语言处理应用于软件开发中。 在第 2 届高级编程语言峰会, 2017.

+   Feng 等 [2020]  Zhangyin Feng, Daya Guo, Duyu Tang, Nan Duan, Xiaocheng Feng, Ming Gong, Linjun Shou, Bing Qin, Ting Liu, Daxin Jiang, 等等. Codebert: 用于编程和自然语言的预训练模型。 在 EMNLP: Findings, 2020.

+   Guo 等 [2021]  Daya Guo, Shuo Ren, Shuai Lu, Zhangyin Feng, Duyu Tang, Shujie Liu, Long Zhou, Nan Duan, Alexey Svyatkovskiy, Shengyu Fu, Michele Tufano, Shao Kun Deng, Colin Clement, Dawn Drain, Neel Sundaresan, Jian Yin, Daxin Jiang, 和 Ming Zhou. Graphcodebert: 使用数据流预训练代码表示。 在 ICLR, 2021.

+   Haque 等 [2020]  Sakib Haque, Alexander LeClair, Lingfei Wu, 和 Collin McMillan. 通过关注文件上下文改进子程序的自动摘要。 在 MSR, 2020.

+   Hassan 和  Xie [2010]  Ahmed E Hassan 和 Tao Xie. 软件智能: 开采软件工程数据的未来。 在 FSE/SDP 研讨会, 2010.

+   Hellendoorn 等 [2020]  Vincent J Hellendoorn, Charles Sutton, Rishabh Singh, Petros Maniatis, 和 David Bieber. 源代码的全局关系模型. 在 ICLR, 2020.

+   Hochreiter 和 Schmidhuber [1997]  Sepp Hochreiter 和 Jürgen Schmidhuber. 长短期记忆。 神经计算, 1997.

+   Howard 和  Ruder [2018]  Jeremy Howard 和 Sebastian Ruder. 通用语言模型微调用于文本分类. 在 ACL, 2018.

+   Hu 等 [2018a]  Xing Hu, Ge Li, Xin Xia, David Lo, 和 Zhi Jin. 深层代码注释生成。 在 ICPC, 2018.

+   Hu 等 [2018b]  Xing Hu, Ge Li, Xin Xia, David Lo, Shuai Lu, 和 Zhi Jin. 用转移的 API 知识概括源代码。 在 IJCAI, 2018.

+   Husain 等 [2019]  Hamel Husain, Ho-Hsiang Wu, Tiferet Gazit, Miltiadis Allamanis, 和 Marc Brockschmidt. Codesearchnet 挑战: 评估语义代码搜索的状态。 arXiv:1909.09436, 2019.

+   Iyer 等人 [2018] Srinivasan Iyer, Ioannis Konstas, Alvin Cheung 和 Luke Zettlemoyer。在编程上下文中将语言映射到代码。发表于 EMNLP，2018 年。

+   Iyer 等人 [2019] Srinivasan Iyer, Alvin Cheung 和 Luke Zettlemoyer。学习可扩展的语义解析编程习语。发表于 EMNLP，2019 年。

+   Jain 等人 [2021] Paras Jain, Ajay Jain, Tianjun Zhang, Pieter Abbeel, Joseph Gonzalez 和 Ion Stoica。对比代码表示学习。发表于 EMNLP，2021 年。

+   Jiang 等人 [2021] Xue Jiang, Zhuoran Zheng, Chen Lyu, Liang Li 和 Lei Lyu。Treebert：一种基于树的预训练编程语言模型。发表于 UAI，2021 年。

+   Kanade 等人 [2020] Aditya Kanade, Petros Maniatis, Gogul Balakrishnan 和 Kensen Shi。学习和评估源代码的上下文嵌入。发表于 ICML，2020 年。

+   Karampatsis 和 Sutton [2020] Rafael-Michael Karampatsis 和 Charles Sutton。Scelmo：来自语言模型的源代码嵌入。arXiv:2004.13214，2020 年。

+   LeClair 等人 [2019] Alexander LeClair, Siyuan Jiang 和 Collin McMillan。生成程序子例程自然语言摘要的神经模型。发表于 ICSE，2019 年。

+   LeClair 等人 [2020] Alexander LeClair, Sakib Haque, Lingfei Wu 和 Collin McMillan。通过图神经网络改进代码摘要。发表于 ICPC，2020 年。

+   Lewis 等人 [2020] Mike Lewis, Yinhan Liu, Naman Goyal, Marjan Ghazvininejad, Abdelrahman Mohamed, Omer Levy, Veselin Stoyanov 和 Luke Zettlemoyer。Bart：用于自然语言生成、翻译和理解的序列到序列去噪预训练。发表于 ACL，2020 年。

+   Liu 等人 [2019] Yinhan Liu, Myle Ott, Naman Goyal, Jingfei Du, Mandar Joshi, Danqi Chen, Omer Levy, Mike Lewis, Luke Zettlemoyer 和 Veselin Stoyanov。Roberta：一种鲁棒优化的 BERT 预训练方法。arXiv:1907.11692，2019 年。

+   Liu 等人 [2020] Fang Liu, Ge Li, Yunfei Zhao 和 Zhi Jin。基于多任务学习的预训练语言模型用于代码补全。发表于 ASE，2020 年。

+   Lu 等人 [2021] Shuai Lu, Daya Guo, Shuo Ren, Junjie Huang, Alexey Svyatkovskiy, Ambrosio Blanco, Colin Clement, Dawn Drain, Daxin Jiang, Duyu Tang, Ge Li, Lidong Zhou, Linjun Shou, Long Zhou, Michele Tufano, MING GONG, Ming Zhou, Nan Duan, Neel Sundaresan, Shao Kun Deng, Shengyu Fu 和 Shujie LIU。CodeXGLUE：用于代码理解和生成的机器学习基准数据集。发表于 NeurIPS 数据集和基准 Track (Round 1)，2021 年。

+   Mastropaolo 等人 [2021] Antonio Mastropaolo, Simone Scalabrino, Nathan Cooper, David Nader Palacio, Denys Poshyvanyk, Rocco Oliveto 和 Gabriele Bavota。研究使用文本到文本转换 Transformer 支持代码相关任务。发表于 ICSE，2021 年。

+   Miceli-Barone 和 Sennrich [2017] Antonio Valerio Miceli-Barone 和 Rico Sennrich。用于自动化代码文档和代码生成的 Python 函数及文档字符串的平行语料库。发表于 IJCNLP，2017 年。

+   Mou 等人 [2016] Lili Mou, Ge Li, Lu Zhang, Tao Wang, 和 Zhi Jin. 基于树结构的卷积神经网络用于编程语言处理. 见于 AAAI, 2016.

+   Nafi 等人 [2019] Kawser Wazed Nafi, Tonny Shekha Kar, Banani Roy, Chanchal K Roy, 和 Kevin A Schneider. CLCDSA: 利用语法特征和 API 文档进行跨语言代码克隆检测. 见于 ASE, 2019.

+   Niu 等人 [2022] Changan Niu, Chuanyi Li, Vincent Ng, Jidong Ge, Liguo Huang, 和 Bin Luo. SPT-CODE: 序列到序列的预训练以学习源代码表示. arXiv:2201.01549, 2022.

+   Panthaplackel 等人 [2021] Sheena Panthaplackel, Miltiadis Allamanis, 和 Marc Brockschmidt. 复制它! 通过复制跨度编辑序列. 见于 AAAI, 2021.

+   Papineni 等人 [2002] Kishore Papineni, Salim Roukos, Todd Ward, 和 Wei-Jing Zhu. BLEU: 一种自动评估机器翻译的方法. 见于 ACL, 2002.

+   Peng 等人 [2021] Dinglan Peng, Shuxin Zheng, Yatao Li, Guolin Ke, Di He, 和 Tie-Yan Liu. 神经网络如何理解程序？ 见于 ICML, 2021.

+   Peters 等人 [2018] Matthew E. Peters, Mark Neumann, Mohit Iyyer, Matt Gardner, Christopher Clark, Kenton Lee, 和 Luke Zettlemoyer. 深度上下文化词表示. 见于 NAACL-HLT, 2018.

+   Phan 等人 [2021] Long Phan, Hieu Tran, Daniel Le, Hieu Nguyen, James Anibal, Alec Peltekian, 和 Yanfang Ye. COTEXT: 基于代码-文本转换器的多任务学习. arXiv:2105.08645, 2021.

+   Pontes 等人 [2018] Elvys Linhares Pontes, Stéphane Huet, Andréa Carneiro Linhares, 和 Juan-Manuel Torres-Moreno. 使用 Siamese CNN 和 LSTM 预测语义文本相似性. 见于 TALN, 2018.

+   Pradel 和 Sen [2018] Michael Pradel 和 Koushik Sen. Deepbugs: 基于名称的缺陷检测学习方法. ACM 编程语言学会会议录, 2018.

+   Qi 等人 [2021] Weizhen Qi, Yeyun Gong, Yu Yan, Can Xu, Bolun Yao, Bartuer Zhou, Biao Cheng, Daxin Jiang, Jiusheng Chen, Ruofei Zhang 等人. Prophetnet-x: 大规模预训练模型用于英语、中文、多语言、对话及代码生成. arXiv:2104.08006, 2021.

+   Qiu 等人 [2020] Xipeng Qiu, Tianxiang Sun, Yige Xu, Yunfan Shao, Ning Dai, 和 Xuanjing Huang. 自然语言处理的预训练模型: 调查. Science China Technological Sciences, 2020.

+   Radford 等人 [2019] Alec Radford, Jeffrey Wu, Rewon Child, David Luan, Dario Amodei, Ilya Sutskever 等人. 语言模型是无监督的多任务学习者. 见于 OpenAI Blog, 2019.

+   Raffel 等人 [2020] Colin Raffel, Noam Shazeer, Adam Roberts, Katherine Lee, Sharan Narang, Michael Matena, Yanqi Zhou, Wei Li, 和 Peter J Liu. 使用统一的文本到文本转换器探索迁移学习的极限. JMLR, 2020.

+   Raychev 等人 [2016] Veselin Raychev, Pavol Bielik, 和 Martin Vechev. 基于决策树的代码概率模型. 见于 OOPSLA, 2016.

+   Ren et al. [2020] Shuo Ren, Daya Guo, Shuai Lu, Long Zhou, Shujie Liu, Duyu Tang, Neel Sundaresan, Ming Zhou, Ambrosio Blanco, 和 Shuai Ma。Codebleu: 一种自动评估代码合成的方法。arXiv:2009.10297, 2020。

+   Roziere et al. [2020] Baptiste Roziere, Marie-Anne Lachaux, Lowik Chanussot, 和 Guillaume Lample。无监督编程语言翻译。发表于 NeurIPS, 2020。

+   Roziere et al. [2021] Baptiste Roziere, Marie-Anne Lachaux, Marc Szafraniec, 和 Guillaume Lample。Dobf: 一种用于编程语言的去混淆预训练目标。arXiv:2102.07492, 2021。

+   Shido et al. [2019] Yusuke Shido, Yasuaki Kobayashi, Akihiro Yamamoto, Atsushi Miyamoto, 和 Tadayuki Matsumura。使用扩展树-LSTM 的自动源代码总结。发表于 IJCNN, 2019。

+   Svajlenko et al. [2014] Jeffrey Svajlenko, Judith F Islam, Iman Keivanloo, Chanchal K Roy, 和 Mohammad Mamun Mia。迈向大数据策划的跨项目代码克隆基准。发表于 ICSME, 2014。

+   Svyatkovskiy et al. [2020] Alexey Svyatkovskiy, Shao Kun Deng, Shengyu Fu, 和 Neel Sundaresan。Intellicode compose: 使用 Transformer 进行代码生成。发表于 ESEC/FSE, 2020。

+   Tang et al. [2022] Ze Tang, Xiaoyu Shen, Chuanyi Li, Jidong Ge, Liguo Huang, Zhelin Zhu, 和 Bin Luo。Ast-trans: 高效树结构注意力的代码总结。发表于 ICSE, 2022。

+   Tufano et al. [2019a] Michele Tufano, Jevgenija Pantiuchina, Cody Watson, Gabriele Bavota, 和 Denys Poshyvanyk。通过神经机器翻译学习有意义的代码更改。发表于 ICSE, 2019。

+   Tufano et al. [2019b] Michele Tufano, Cody Watson, Gabriele Bavota, Massimiliano Di Penta, Martin White, 和 Denys Poshyvanyk。关于通过神经机器翻译学习现实环境中的错误修复补丁的实证研究。发表于 TOSEM, 2019。

+   Vasic et al. [2019] Marko Vasic, Aditya Kanade, Petros Maniatis, David Bieber, 和 Rishabh Singh。通过联合学习定位和修复实现神经程序修复。发表于 ICLR, 2019。

+   Vaswani et al. [2017] Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N Gomez, Łukasz Kaiser, 和 Illia Polosukhin。注意力机制是你所需的一切。发表于 NeurIPS, 2017。

+   Wang et al. [2020] Wenhan Wang, Ge Li, Bo Ma, Xin Xia, 和 Zhi Jin。使用图神经网络和流增强抽象语法树检测代码克隆。发表于 SANER, 2020。

+   Wang et al. [2021a] Xin Wang, Yasheng Wang, Fei Mi, Pingyi Zhou, Yao Wan, Xiao Liu, Li Li, Hao Wu, Jin Liu, 和 Xin Jiang。Syncobert: 语法引导的多模态对比预训练用于代码表示。arXiv:2108.04556, 2021。

+   Wang et al. [2021b] Yue Wang, Weishi Wang, Shafiq Joty, 和 Steven CH Hoi。Codet5: 识别符感知的统一预训练编码器-解码器模型用于代码理解和生成。发表于 EMNLP, 2021。

+   Watson et al. [2020] Cody Watson, Michele Tufano, Kevin Moran, Gabriele Bavota, 和 Denys Poshyvanyk。学习有意义的断言语句用于单元测试用例。发表于 ICSE, 2020。

+   Xu 等人 [2021] Zenan Xu, Daya Guo, Duyu Tang, Qinliang Su, Linjun Shou, Ming Gong, Wanjun Zhong, Xiaojun Quan, Daxin Jiang 和 Nan Duan. 语法增强的预训练模型。发表于 ACL/IJCNLP (1), 2021。

+   Yang 等人 [2019] Zhilin Yang, Zihang Dai, Yiming Yang, Jaime Carbonell, Russ R Salakhutdinov 和 Quoc V Le. Xlnet: 一种用于语言理解的广义自回归预训练方法。发表于 NeurIPS, 32, 2019。

+   Ye 等人 [2020] Fangke Ye, Shengtian Zhou, Anand Venkat, Ryan Marcus, Nesime Tatbul, Jesmin Jahan Tithi, Niranjan Hasabnis, Paul Petersen, Timothy Mattson, Tim Kraska 等人。Misim: 一种使用上下文感知语义结构的神经代码语义相似度系统。发表于 CoRR, 2020。

+   Zhang 等人 [2021] Jingfeng Zhang, Haiwen Hong, Yin Zhang, Yao Wan, Ye Liu 和 Yulei Sui. 针对多种编程语言的解耦代码表示学习。发表于 ACL: Findings, 2021。

+   Zhou 等人 [2019] Yaqin Zhou, Shangqing Liu, Jingkai Siow, Xiaoning Du 和 Yang Liu. Devign: 通过图神经网络学习全面的程序语义来有效识别漏洞。发表于 NeurIPS, 2019。

+   Zhou 等人 [2021] Xin Zhou, DongGyun Han 和 David Lo. 评估 CodeBERT 的泛化能力。发表于 ICSME, 2021。

+   Zügner 等人 [2021] Daniel Zügner, Tobias Kirschstein, Michele Catasta, Jure Leskovec 和 Stephan Günnemann. 从结构和上下文中进行语言无关的源代码表示学习。发表于 ICLR, 2021。
