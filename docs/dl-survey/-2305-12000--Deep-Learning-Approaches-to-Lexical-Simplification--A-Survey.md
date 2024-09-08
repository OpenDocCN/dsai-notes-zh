<!--yml

分类: 未分类

日期: 2024-09-06 19:39:30

-->

# [2305.12000] 深度学习方法在词汇简化中的应用：综述

> 来源：[`ar5iv.labs.arxiv.org/html/2305.12000`](https://ar5iv.labs.arxiv.org/html/2305.12000)

# 深度学习方法在词汇简化中的应用：综述

Kai North¹, Tharindu Ranasinghe², Matthew Shardlow³, Marcos Zampieri¹

¹乔治·梅森大学，美国，²阿斯顿大学，英国

³曼彻斯特城市大学，英国

knorth8@gmu.edu

###### 摘要

**词汇简化（LS）**的任务是将句子中的复杂词汇替换为更简单的词汇，同时保持句子的原始意义。**词汇简化（LS）**是**文本简化（TS）**的词汇组件，旨在使文本对各种目标人群更加可访问。一项过去的调查 Paetzold 和 Specia (2017b) 提供了**词汇简化（LS）**的详细概述。然而，自此调查以来，AI/NLP 社区因深度学习的最新进展，特别是大型语言模型（LLM）和提示学习的引入而发生了巨大变化。这些模型的高性能激发了对**词汇简化（LS）**的新兴趣。为了反映这些最新进展，我们提供了对 2017 年至 2023 年间关于**词汇简化（LS）**及其子任务的论文的全面综述，特别关注深度学习。我们还提供了**词汇简化（LS）**系统未来发展的基准数据集。

## 1 引言

**词汇简化（LS）**旨在提高任何给定文本的可读性，以帮助词汇和读写能力的发展。**词汇简化（LS）**通过用更简单的替代词替换句子中的复杂词汇来实现这一目标。**词汇简化（LS）**返回一个简化的句子，可以传递给**文本简化（TS）**系统进行进一步的句法和语法简化。被替换的复杂词汇是指一般或特定人群认为难以阅读、解释或理解的词汇。以前的**词汇简化（LS）**系统旨在为儿童、第二语言学习者、阅读障碍或低读写能力的个人简化复杂词汇 Paetzold 和 Specia (2017b)。因此，**词汇简化（LS）**为开发者和用户提供了一种通过 seq2seq 或生成式**文本简化（TS）**系统无法实现的个性化程度 Yeung 和 Lee (2018); Lee 和 Yeung (2018a)。

深度学习，尤其是大型语言模型（LLM）和提示学习，已经彻底改变了我们处理许多自然语言处理（NLP）任务的方法，包括**词汇简化（LS）**。以前的**词汇简化（LS）**系统依赖于词汇表、基于规则的、统计学、n-gram 和词嵌入模型来识别和简化复杂词汇 Paetzold 和 Specia (2017b)。这些方法会识别出复杂词汇，例如“bombardment”，认为其需要简化，并建议“attack”作为合适的替代词（图 1），此处称为候选替换。

最先进的深度学习模型，如 BERT Devlin et al. (2019)、RoBERTa Liu et al. (2019)、GPT-3 Brown et al. (2020)等，能够自动生成、选择和排序候选替代词，其表现优于传统方法。这些传统方法包括依赖于现有词典、简化规则或工程特征 Saggion et al. (2022)。目前尚无关于深度学习方法用于词汇简化（LS）的综述文章。Paetzold 和 Specia (2017b) 的论文是最近期的词汇简化综述，但它早于展示最先进深度学习方法所取得进展的研究。Al-Thanyyan 和 Azmi (2021) 于 2021 年发表了一项广泛的综合性文本简化综述。然而，该综述同样未涵盖领域内的最新进展，也未专门聚焦于词汇简化。因此，本论文通过提供最新深度学习方法在词汇简化及其子任务（包括替代词生成（SG）、选择（SS）和排序（SR））的更新综述，继续扩展现有文献。

## 2 流程

我们围绕词汇简化流程的主要组成部分：SG、SS 和 SR（第三部分）来构建本综述。我们还提供了最近数据集的概述（第四部分），并讨论了词汇简化中的开放挑战（第 5.1 节）。通常，词汇简化流程从复杂词识别（CWI）开始。然而，由于它通常被视为一个独立的前置步骤，我们建议读者参考 North et al. (2022b)，以获取关于 CWI 方法的详细综述。

`<svg height="381.9" overflow="visible" version="1.1" width="453.86"><g transform="translate(0,381.9) matrix(1 0 0 -1 0 0) translate(108.54,0) translate(0,281.69)" fill="#000000" stroke="#000000"><g stroke-width="0.4pt"><g transform="matrix(1.0 0.0 0.0 1.0 -94.36 -95.32)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 184.49)"><g transform="matrix(1 0 0 1 0 178.34)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 39.01 0)"><g transform="matrix(1 0 0 -1 0 178.34)"><g transform="matrix(1 0 0 1 0 178.34)"><g transform="matrix(1 0 0 -1 0 0)"><g transform="matrix(1 0 0 -1 0 172.19)"><g transform="matrix(1 0 0 1 0 175.65)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 0 0)"><foreignobject width="110.7" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">复杂句</foreignobject></g></g></g></g></g></g></g></g><g transform="matrix(1 0 0 1 0 187.95)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 0 0)"><text transform="matrix(1 0 0 -1 0 0)">政权军队的轰炸</text></g></g></g></g><g transform="matrix(1.0 0.0 0.0 1.0 -88.04 -186.06)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 46.635)"><g transform="matrix(1 0 0 1 0 41.83)"><g transform="matrix(1 0 0 -1 0 0)"><g transform="matrix(1 0 0 -1 0 41.83)"><g transform="matrix(1 0 0 1 0 41.83)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 0 0)"><g transform="matrix(1 0 0 -1 0 35.68)"><g transform="matrix(1 0 0 1 0 39.14)"><g transform="matrix(1 0 0 -1 0 0)"><foreignobject width="177.61" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">复杂词汇识别</foreignobject></g></g></g></g></g></g></g></g><g transform="matrix(1 0 0 1 0 51.44)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 26.23 0)"><foreignobject width="123.61" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">CWI: 轰炸</foreignobject></g></g></g></g><g transform="matrix(1.0 0.0 0.0 1.0 -73.56 -276.8)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 45.29)"><g transform="matrix(1 0 0 1 0 39.14)"><g transform="matrix(1 0 0 -1 6.57 0)"><g transform="matrix(1 0 0 -1 0 39.14)"><g transform="matrix(1 0 0 1 0 39.14)"><g transform="matrix(1 0 0 -1 0 0)"><g transform="matrix(1 0 0 -1 0 34.335)"><g transform="matrix(1 0 0 1 0 39.14)"><g transform="matrix(1 0 0 -1 0 0)"><foreignobject width="133.97" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">替代生成</foreignobject></g></g></g></g></g></g></g></g><g transform="matrix(1 0 0 1 0 48.75)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 0 0)"><foreignobject width="147.11" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">SG: 攻击, 袭击, 打击</foreignobject></g></g></g></g><g transform="matrix(1.0 0.0 0.0 1.0 165.01 -22.14)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 38.13)"><g transform="matrix(1 0 0 1 0 31.98)"><g transform="matrix(1 0 0 -1 12.95 0)"><g transform="matrix(1 0 0 -1 0 31.98)"><g transform="matrix(1 0 0 1 0 31.98)"><g transform="matrix(1 0 0 -1 0 0)"><g transform="matrix(1 0 0 -1 0 25.83)"><g transform="matrix(1 0 0 1 0 29.3)"><g transform="matrix(1 0 0 -1 0 0)"><foreignobject width="117.61" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">简化句</foreignobject></g></g></g></g></g></g></g></g><g transform="matrix(1 0 0 1 0 41.59)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 0 0)"><text transform="matrix(1 0 0 -1 0 0)">政权军队的攻击</text></g></g></g></g><g transform="matrix(1.0 0.0 0.0 1.0 152.81 -118.35)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 47.98)"><g transform="matrix(1 0 0 1 0 41.83)"><g transform="matrix(1 0 0 -1 25.21 0)"><g transform="matrix(1 0 0 -1 0 41.83)"><g transform="matrix(1 0 0 1 0 41.83)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 0 0)"><g transform="matrix(1 0 0 -1 0 35.68)"><g transform="matrix(1 0 0 1 0 39.14)"><g transform="matrix(1 0 0 -1 0 0)"><foreignobject width="117.5" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">替代排名</foreignobject></g></g></g></g></g></g></g></g><g transform="matrix(1 0 0 1 0 51.44)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 0 0)"><foreignobject width="167.93" height="12.3" transform="matrix

图 1：LS 流程图。SG、SS 和 SR 是 LS 的主要组件。

#### 替代生成

SG 返回一个数字：k，表示适合替换先前识别的复杂词的候选替代。通常，LS 系统会生成 k = [1、3、5 或 10] 范围内的候选替代，其中前 k 名是最合适的候选。这些候选替代需要比原始复杂词更简单，因此更易于阅读、解释或理解。候选替代还需要保留原始复杂词的含义，特别是在其提供的上下文中。

#### 替代选择

SS 过滤生成的前 k 名候选替代，移除不合适的那些。例如，不同义于原始复杂词或更复杂的候选替代通常会被移除。

#### 替代排名

SR 将剩余的前 k 个候选替代按从最适合到最不适合的顺序排列。然后，用最合适的候选替代替换原始复杂词。

### 2.1 评估指标

LS 流程图的所有子任务都使用精度、准确率、召回率和 F1 分数进行评估。还使用了一些额外的度量：潜力、均值平均精度（MAP）和前 k 名准确率。潜力是预测候选替代中至少一个前 k 名候选替代是否在金标准标签中的比例（Saggion 等 (2022)）。MAP 评估返回的前 k 名候选替代是否匹配金标准标签，以及它们是否具有相同的位置排名。前 k 名准确率 = [1、2 或 3] 是至少一个候选替代在 k 名中是否在金标准标签中的比例。

## 3 种深度学习方法

| 深度学习方法 | ACC | ACC@1 | ACC@3 | MAP@3 | Potential@3 | 论文 |
| --- | --- | --- | --- | --- | --- | --- |
| SG | SS & SR | TSAR-2022 (EN) |  |
| GPT-3+Prompts | GPT-3 | 0.8096 | 0.4289 | 0.6863 | 0.5834 | 0.9624 | Aumiller 和 Gertz (2022) |
| MLM | LLM+嵌入+频率 | 0.6568 | 0.3190 | 0.5388 | 0.4730 | 0.8766 | Li 等 (2022) |
| LLM+Prompt | MLM 预测分数 | 0.6353 | 0.2895 | 0.5308 | 0.4244 | 0.8739 | Vásquez-Rodríguez 等 (2022) |
| SG | SS & SR | TSAR-2022 (ES) |  |
| GPT-3+Prompts | GPT-3 | 0.6521 | 0.3505 | 0.5788 | 0.4281 | 0.8206 | Aumiller 和 Gertz (2022) |
| MLM | 嵌入+POS | 0.3695 | 0.2038 | 0.3288 | 0.2145 | 0.5842 | Whistely 等 (2022) |
| LLM+Prompt | MLM 预测分数 | 0.3668 | 0.160 | 0.2690 | 0.2128 | 0.5326 | Vásquez-Rodríguez 等 (2022) |
| SG | SS & SR | TSAR-2022 (PT) |  |
| GPT-3+Prompts | GPT-3 | 0.7700 | 0.4358 | 0.6299 | 0.5014 | 0.9171 | Aumiller 和 Gertz (2022) |
| MLM | MLM 预测分数 | 0.4812 | 0.2540 | 0.3957 | 0.2816 | 0.6871 | North 等 (2022a) |
| MLM | Freq+BinaryClassifier | 0.3689 | 0.1737 | 0.2673 | 0.1983 | 0.5240 | Wilkens 等人（2022） |

表 1：TSAR-2022 数据集上的前 3 名深度学习方法。最佳表现以**粗体**显示。

在深度学习方法出现之前，词典、基于规则的、统计、n-gram 和词嵌入模型是 SG、同义词消歧（SS）和同义词替换（SR）领域的最先进技术。如前所述，Paetzold 和 Specia（2017b）提供了一项全面的调查，详细介绍了这些方法及其性能，以及它们对语言学文献的影响。以下部分扩展了 Paetzold 和 Specia（2017b）所做的工作。我们引入了新的深度学习方法，并开始对语言学流水线的 SG 阶段进行调查。North 等人（2022b）对流水线中的 CWI 步骤的最新进展进行了广泛调查。

### 3.1 替代词生成

在 2017 年，词嵌入模型是同义词生成（SG）领域的最先进技术。词嵌入模型，如 Word2Vec Mikolov 等（2013），与传统方法（如查询词典或基于某些规则生成候选替代词 Paetzold 和 Specia（2017b））一起使用。词嵌入模型通过将潜在的候选替代词转换为向量，即词嵌入，然后计算这些向量与目标复杂词向量的余弦相似度或余弦距离，从而进行 SG。这些向量随后被转换回词形，并被认为是前 k 个候选替代词。

#### 词嵌入 + 大型语言模型（LLMs）

2017 年后，词嵌入模型继续在 SG 中得到应用。然而，它们现在与 LLMs 生成的词嵌入或 LLM 的预测得分结合在一起。Alarcón 等人 (2021a) 对各种词嵌入模型进行了实验，以生成西班牙语的候选替代词。他们使用了诸如 Word2Vec、Sense2Vec Trask 等 (2015) 和 FastText Bojanowski 等 (2016) 等词嵌入模型，以及预训练的 LLM BERT，来生成这些词嵌入。研究发现，一种更传统的方法，通过查询现有词典生成候选替代词，在潜在性和召回率方面都优于这些词嵌入模型，但在精确度方面稍逊于这些词嵌入模型。传统方法在 EASIER 数据集上达到了 0.898 的潜在性、0.597 的召回率和 0.043 的精确度。另一方面，表现最好的词嵌入模型（Sense2Vec）分别达到了 0.506、0.282 和 0.056 的潜在性、召回率和精确度。令人惊讶的是，这与词嵌入模型由于其先进的声誉而表现更优的假设相悖。Paetzold 和 Specia (2017a) 的研究也表明了这一点。在错误分析过程中发现，这些词嵌入模型经常将目标复杂词的反义词作为候选替代词。这是由于词嵌入模型计算词向量之间的相似度的方式所致。

Seneviratne 等人 (2022) 使用了一个词嵌入模型和一个预训练的 LLM：XLNet Yang 等 (2019)，以产生嵌入相似度得分和 SG 的预测得分。他们采用了与 Arefyev 等人 (2020) 相似的方法。Arefyev 等人 (2020) 使用了 context2vec Melamud 等 (2016) 和 ELMo Peters 等 (2018) 对目标复杂词的上下文进行编码，以获取每个词属于特定上下文的概率分布。然后，他们使用这个概率分布来估算一个潜在候选替代词替换目标复杂词的可能性或适当性。这个得分与来自 BERT、RoBERTa 或 XLNet 的 LLM 预测得分一起使用，以生成最终的 top-k 候选替代词列表。Seneviratne 等人 (2022) 和 Arefyev 等人 (2020) 发现，他们将词嵌入模型与预训练 LLM 预测得分结合使用的方法未能超越单一预训练 LLM 的表现。例如，Seneviratne 等人 (2022) 在 TSAR-2022 数据集上被 North 等人 (2022a) 超越。

#### 掩码语言建模

预训练的大型语言模型（LLM）的引入，同时也带来了掩码语言建模（MLM）用于同义词生成（SG）。Przybyła 和 Shardlow（2020）使用了以 MLM 目标训练的 LLM 进行多词同义词生成，而 Qiang 等人（2020）是首次将 MLM 应用于西班牙语 SG。MLM 随后成为 SG 的一种流行方法。在提交给 TSAR-2022 的 11 份系统报告中，有 7 份 Saggion 等人（2022）描述了他们的方法包含 MLM 目标。

被称为 LSBert 的模型，由 Qiang 等人（2020）提出，使用了预训练的 LLM BERT。句子取自 LS 数据集 LexMTurkHorn 等人（2014）、BenchLS Paetzold 和 Specia（2016b）和 NNSeval Paetzold 和 Specia（2016c）。每个句子有两个版本被连接在一起，中间用[SEP]特殊标记分隔。它们被输入到 LLM 中。第一个句子与从数据集中提取的句子相同，而第二个句子的复杂词被替换为[MASK]特殊标记。LLM 然后试图预测被[MASK]特殊标记替换的词，考虑到其左右上下文以及之前的原始句子。通过这种方式，LLM 提供了与周围上下文最匹配且与原始句子中的目标复杂词相似的候选替换词。对于 top-k=1 的候选替换，LSBert 在三个数据集 LexMTurk Horn 等人（2014）、BenchLS Paetzold 和 Specia（2016b）和 NNSeval Paetzold 和 Specia（2016c）上分别达到了 0.259、0.272 和 0.218 的 F1 分数。这些表现超越了所有先前的方法 Paetzold 和 Specia（2017b）。之前的最高 F1 分数由一个词嵌入模型 Paetzold 和 Specia（2017a）取得，分别为 0.195、0.236 和 0.218。

在 TSAR-2022 共享任务发布之前，Saggion et al. (2022)，Ferres 和 Saggion (2022) 引入了一个新数据集：ALEXSIS（TSAR-2022 ES），该数据集后来（以及额外的英语和葡萄牙语数据集）组成了 TSAR-2022 数据集 Saggion et al. (2022)。使用他们的西班牙语数据集，他们实验了多种在西班牙语数据上预训练的单语 LLM 以及几种多语言 LLM，例如 mBERT 和 RoBERTa。Ferres 和 Saggion (2022) 采用了 LSBert 使用的 MLM 方法。他们实验了西班牙语 LLM：BETO Cañete et al. (2020)、BERTIN De la Rosa 和 Fernández (2022)、RoBERTa-base-BNE 和 RoBERTA-large-BNE Fandiño et al. (2022) 用于 SG。他们发现，最大的预训练西班牙语 LLM：RoBERTA-large-BNE，达到了最佳的 SG 性能，此前他们还去除了与复杂词相等的候选替代项，不论大小写或重音，并且字符数少于 2。

North et al. (2022a) 受到 Ferres 和 Saggion (2022) 展示的单语 LLM 成功的启发。他们同样测试了多种具有 MLM 目标的 LLM，包括多语言 LLLMs：mBERT 和 XLM-R Conneau et al. (2020)，以及几种单语 LLM，包括英语的 Electra Clark et al. (2020)、西班牙语的 RoBERTA-large-BNE 和葡萄牙语的 BERTimbau Souza et al. (2020)。他们的单语 LLM 在英语、西班牙语和葡萄牙语 TSAR-2022 数据集上的 acc@1 分别为 0.517、0.353 和 0.481。Whistely et al. (2022) 也对类似的单语 LLM 进行了 SG 实验。他们使用了英语的 BERT、西班牙语的 BETO 和葡萄牙语的 BERTimbau。有趣的是，他们的模型表现低于 North et al. (2022a)，尽管他们的葡萄牙语 LS 系统使用了相同的语言模型。Whistely et al. (2022) 分别在英语、西班牙语和葡萄牙语上取得了 0.378、0.250 和 0.3074 的 acc@1 分数。这可能是由于 Whistely et al. (2022) 实施了额外的 SS 和 SR 步骤，而 North et al. (2022a) 的 LS 系统中则缺少这些步骤（见 3.2）。

Wilkens 等人 (2022) 也使用了一系列单语 LLMs 用于 SG。然而，他们使用了一组 BERT 类模型，采用了三种不同的掩码策略：1). 复制策略，2). 查询扩展策略，3). 释义策略。复制策略复用了 LSBert Qiang 等人 (2020) 的方法，其中两句话被输入到 LLM 中，并用 [SEP] 特殊标记连接。第一句话是原始句子的未修改版本，第二句话则将复杂词汇进行了掩码。查询扩展策略使用 FastText 生成与目标复杂词具有最高余弦相似度的五个相关词。在查询扩展策略的第 2a) 轮中，第一句话是原始未修改句子，第二句话用 FastText 生成的一个相似词替换了复杂词，而第三句话是掩码句子。该策略的第 2b) 轮与第 2a) 轮相同，但第二句话现在包括所有五个建议词。最后，释义策略为每个复杂词生成了 10 个新语境，这些语境由原始句子的释义组成。这些新语境被限制在 512 个标记内。这三种掩码策略使用的模型包括英语的 BERT 和 RoBERTa LLMs、西班牙语的多个 BETO LLMs，以及葡萄牙语的多个 BERTimbau LLMs。释义策略的表现最差，MAP/Potential@1 分数为 0.217，而查询扩展策略在英语、西班牙语和葡萄牙语中的 MAP/Potential@1 分数分别为 0.528、0.477 和 0.476。这超越了释义策略和 LSBert 使用的原始复制策略的表现，无论使用何种 LLMs。

#### 提示学习

提示学习也被用于简化生成（SG），并且目前是最先进的技术（表格 3）。提示学习涉及向大型语言模型（LLM）输入以描述任务并返回期望输出的内容。PromptLS 是应用于 SG 的提示学习的一个例子。由 Vásquez-Rodríguez 等人 (2022) 创建的 PromptLS 包含了多种在多个词汇简化（LS）数据集上微调的预训练 LLM。这些微调过的 LLM 然后接收了四种提示组合：a). “bombardment 的一个更简单的词是”，b). “bombardment 的一个简单词是”，c). “bombardment 的一个更简单的同义词是”，以及 d). “bombardment 的一个简单同义词是”。这些提示组合被提供给 RoBERTa LLM，应用于从 LexMTurk Horn 等人 (2014)、BenchLS Paetzold 和 Specia (2016b)、NNSeval Paetzold 和 Specia (2016c)、和 CERF-LS Uchida 等人 (2018) 收集的所有英语数据上。它们还被翻译并输入到在 EASIER 上微调的 BERTIN，以及在 SIMPLEX-PB Hartmann 和 Aluísio (2020) 提供的所有葡萄牙语数据上微调的 BR-BERTo 中。Vásquez-Rodríguez 等人 (2022) 还在零样本条件下使用了这些提示。研究发现，微调后的 LLM 在所有条件下的表现优于零样本模型，性能在所有指标（acc@1, acc@3, MAP@3 和 Precision@3）上平均提高了 0.3 到 0.4。产生最佳候选替代词的提示组合是英语中的“easier word”，西班牙语中的“palabra simple”和“palabra fácil”，以及葡萄牙语中的“palavra simples”和“sinônimo simples”。

提示学习同样被应用于因果语言模型，如 GPT-3。Aumiller 和 Gertz (2022) 试验了各种不同的提示，并将它们输入到 GPT-3 中。这些提示有四种类型：1). 带上下文的零-shot，2). 带上下文的单-shot，双-shot 带上下文，3). 不带上下文的零-shot，以及 4). 不带上下文的单-shot。每次输入的大小：n，指的是提示被输入到 GPT-3 中的次数。例如，带上下文的提示会输入一个给定的句子，然后问“根据上述上下文，列出 $<$复杂词汇$>$ 的十个更易理解的替代词。”，重复 n 次。而不带上下文的提示则会输入 n 次以下内容：“给我 $<$复杂词汇$>$ 的十个简化同义词。”Aumiller 和 Gertz (2022) 还将所有类型的提示结合在一个集成体中，从每种提示类型生成候选替代词，然后通过多数投票和额外的 SS 和 SR 步骤（第 3.2 节）来决定最终的候选替代词。他们的集成方法优于所有其他提示类型和提交给 TSAR-2022 的 SG 模型 Saggion 等 (2022)（表 3）。

### 3.2 替代词选择和排序

传统的 SS 方法仍然在 SG 后实现。像 POS 标记和反义词过滤、语义或句子阈值这样的技术已被用于去除不适当的候选替代词，这些词是在上述深度学习方法生成后产生的 Saggion 等 (2022)。然而，大多数现代深度学习方法的 SS 最小，SS 通常在 SG 或 SR 过程中同时进行。例如，用于生成 top-k 候选替代词的指标，通常是词嵌入之间的相似性，或预训练 LLM 的预测分数，往往不会建议被其他 SS 方法认为不适当的候选替代词。同样，SR 技术将候选替代词按其适当性排序，将不适当的简化进一步移动到 top-k 候选替代词列表的末尾，直到不再被考虑。

#### 词嵌入

即使在预训练的 LLMs（如 BERT）出现后，词嵌入模型仍继续用于 SS。例如，Song 等人 (2020) 创建了一个独特的 LS 系统，该系统通过应用语义相似性阈值来筛选候选替换，仅匹配与目标复杂词具有相同 POS 标签的候选替换，计算上下文相关性，这是替换复杂词后句子的合理性和流畅性的衡量标准，并使用词嵌入之间的余弦相似度对候选替换进行排名。他们通过 Word2Vec 生成词嵌入，并在 LS-2007 数据集 McCarthy 和 Navigli (2007) 上评估了模型的表现。结果发现，使用 Word2Vec 提升了模型的表现，取得了 0.269 的 acc@1。没有使用 Word2Vec 嵌入的第二高表现模型的 acc@1 为 0.218。

#### 神经回归

Maddela 和 Xu (2018) 为 SR 创建了神经可读性排序器（NNR）。NNR 包含一个特征提取模块、一个基于高斯的特征向量化层和一个特定任务的输出节点，是一种能够根据感知复杂性对候选替换进行排名的深度学习算法。它执行回归，通过在词汇复杂性词典（WCL）上进行训练，以及将若干特征和字符 n-grams 转换为高斯向量，它能够提供一个介于 0 和 1 之间的值，表示任何给定词汇的复杂性。它通过进行成对聚合来实现这一点。对于每对潜在的候选替换，模型预测一个值，以定义哪个候选替换比另一个更复杂或更简单。返回的正值表示第一个候选替换比第二个更复杂，而负值则表示第二个候选替换比第一个更复杂。这一方法应用于复杂词汇的所有候选替换组合。每个候选替换随后根据其与所有其他潜在候选替换的比较复杂性进行排名。Maddela 和 Xu (2018) 将他们的 NNR 模型应用于 LS-2012 数据集，并超越了之前的 SR 词嵌入技术。他们获得了 0.673 的 Prec@1，而 Paetzold 和 Specia (2017a) 提供的之前的最先进模型则获得了 0.656 的 Prec@1。

#### 词嵌入 + LLMs

对于 SS 和 SR 最常用的方法之一是使用词嵌入和 LLMs。Seneviratne 等人（2022）基于与 SG 相同的综合评分对前 k=20 个候选替换进行了筛选和排名。评分包括其 MLM 模型对生成候选词的预测分数以及目标词的嵌入和潜在候选替换的嵌入之间的内积。这些前 k=20 个候选替换随后经过了三种额外排名指标中的一种。第一个排名指标（CILex_1）根据候选替换与原句的余弦相似度对候选替换进行排名，候选替换替换了其复杂词。第二和第三个排名指标利用了目标复杂词及其候选替换的词典定义。他们计算了每个定义的嵌入与目标复杂词句子的嵌入之间的余弦相似度。那些具有最高余弦相似度的定义 a). 目标复杂词的定义和候选替换的定义（CILex_2），或 b). 目标复杂词的定义和原句中复杂词被候选替换词替换后的词嵌入（CILex_3），用于确定每个候选替换的排名。他们发现这三种指标在 TSAR-2022 数据集上表现相似，CILex 1、2 和 3 分别达到了 0.375、0.380 和 0.386 的 acc@1 得分。

Li 等人（2022）使用了一组来自 LSBert 的特征，并结合了他们所称的等效评分。等效评分是为了衡量候选替换和复杂词之间的语义相似度，其表达能力超过了词嵌入之间的余弦相似度。为了获得这个等效评分，他们使用了一个经过预训练的 RoBERTa LLM，该模型经过自然语言推理（NLI）的训练，预测一个句子是否包含另一个句子的可能性。该模型在一个多类型语料库上进行训练，目标是 MLM。返回的原句与候选替换前置的原句和反向的原句的可能性相乘，等于等效评分。由于 Li 等人（2022）使用了与 LSBert 相同的 SG 方法，只是将 LLM 更改为 RoBERTa，他们得出结论，他们系统的优越性能是其独特 SR 的结果。他们在英语 TSAR-2022 数据集上达到了 0.659 的 acc@1，而 LSBert 在 Saggion 等人（2022）的数据集上达到了 0.598 的 acc@1。

Aleksandrova 和 Brochu Dufour (2022) 根据三个指标对候选替代项进行排名：a). 语法性，b). 意义保留，和 c). 简单性。语法性通过首先确定候选替代项在语法类别（如人称、数、情态、时态等）是否匹配来计算。如果在所有 POS 标签类别上匹配，则赋值为 1；如果至少一个类别不匹配，则赋值为 0。意义保留通过使用 BERTScore 生成原句与替代复杂词后的句子嵌入之间的余弦相似度来确定。最后，通过使用在英语词汇配置文件 (EVP) 数据上训练的 CEFR 词汇分类器来获得保留。用于训练 CEFR 分类器的数据首先被掩码，并输入到预训练 LLM：BERT 中。输出的编码然后用于训练 SVM 模型，从而形成他们的 CEFR 分类器。他们的模型在 TSAR-2022 的 acc@1 性能上未能超越基线 LSBert 模型，得分为 0.544。

#### MLM 预测分数

LS 系统也完全依赖于 MLM 预测分数来进行 SS 和 SR。North 等人 (2022a) 和 Vásquez-Rodríguez 等人 (2022) 采用了这种方法。他们没有额外的 SR 步骤，而是根据生成的 MLM 预测分数对候选替代项进行排序。然而，他们确实进行了基本的过滤，两项研究都去除了重复项以及与复杂词相同的候选替代项。令人惊讶的是，最小 SR 已被证明优于其他更技术性的 approaches (Table 3)。North 等人 (2022a) 在 TSAR-2022 葡萄牙语数据集上达到了最先进的性能，而 Vásquez-Rodríguez 等人 (2022) 在英语和西班牙语 TSAR-2022 数据集上 consistently 提供了高性能。只有基于 GPT-3 的模型超越了这些表现 Aumiller 和 Gertz (2022) (Table 3)。

## 资源

2017 年后创建的 LS 数据集已经覆盖了 LS 流程中的所有子任务或用于特定目的 (Appendix, Table 2)。最近的国际竞赛（共享任务）也提供了他们自己的 LS 数据集 (*)。LS 资源可用于多种语言，主要包括英语（EN）、西班牙语（ES）、葡萄牙语（PT）、法语（FR）、日语（JP）和中文（ZH）。

### 4.1 英语

#### 个性化 LS

Lee 和 Yeung (2018b) 为个性化语言简化（LS）构建了一个包含 12,000 个英语单词的数据集。这些单词根据五级李克特量表进行了排名。15 位以日语为母语的评估者负责对每个单词的复杂度进行评分。这些复杂度评分随后被应用于 BenchLS，从而为日语使用者个性化了数据集。

#### WCL

Maddela 和 Xu (2018) 介绍了单词复杂度词典（WCL）。WCL 是一个由 15,000 个带有复杂度评分的英语单词组成的数据集。标注者是 11 位非母语英语使用者，使用六级李克特量表进行标注。

#### LCP-2021*

在 LCP-2021 共享任务（CompLex）中提供的数据集（Shardlow et al. (2020）是通过众包方式开发的。10,800 个复杂单词的语境从涵盖《圣经》、生物医学文章和欧洲议会记录的三个语料库中选择。它们的词汇复杂度使用了 5 级李克特量表进行标注。

#### SimpleText-2021*

SimpleText-2021 共享任务中，Ermakova 等人 (2021) 引入了三个试点任务：1) 选择需要简化的段落，2) 识别这些段落中的复杂概念，3) 简化这些复杂概念以生成更易理解的段落。他们为参与者提供了两个数据来源，这些数据分别是引用网络数据集、DBLP+Citation、ACM 引用网络，以及从《卫报》报纸中提取的带有手动标注关键词的标题。

#### TSAR-2022*

TSAR-2022 Saggion 等人 (2022) 提供了英文、西班牙文和葡萄牙文的数据集。这些数据集中包含了来自新闻文本和维基百科文章的目标单词及其上下文，以及由位于英国、西班牙和巴西的众包标注者提供的 10 个候选替换词（原始数据中约为 20 个）。候选替换词根据建议频率进行了排名。这些数据集的英文、西班牙文和葡萄牙文实例分别为 386、381 和 386 个。

### 4.2 其他语言的数据集

#### 西班牙语

ALexS-2020 共享任务中，Zambrano 和 Ráez (2020) 包含了一个西班牙语数据集，其中包含来自记录转录本的 723 个复杂单词。Merejildo (2021) 提供了西班牙语 CWI 语料库（ES-CWI）。40 名西班牙语母语标注者在 3,887 篇学术文本中识别了复杂单词。EASIER 语料库（Alarcón et al. (2021b））包含了 5,310 个西班牙语复杂单词的上下文，并提供了 7,892 个候选替换词。还有一个小版本的语料库，包含 500 个实例（EASIER-500）。

#### 葡萄牙语

PorSimples 数据集 Aluísio 和 Gasperin（2010）包含从巴西报纸中提取的片段。数据集被分为九个子语料库，按简化程度和来源文本进行区分。PorSimplesSent 数据集 Leal 等（2018）是从之前的 PorSimples 数据集中改编的。它包含对 PorSimples 原始句子的强简化和自然简化。SIMPLEX-PB Hartmann 和 Aluísio（2020）提供了每个候选替换的特征选择。

#### 法语

ReSyf 包含了按阅读难度排名的法语同义词，使用了 SVM Billami 等（2018）。它由 57,589 个实例组成，总共有 148,648 个候选替换。FrenchLys 是 Rolin 等（2021）设计的一个 LS 工具。它提供了自己的数据集，包括从法语 TS 数据集 ALECTOR 和法国教科书中抽取的句子。候选替换由 20 名讲法语的标注者提供。

#### 日语

日语词汇替换（JLS）数据集 Kajiwara 和 Yamamoto（2015）包含 243 个目标词，每个目标词有 10 个上下文（总共 2,430 个实例）。众包标注者提供并排序了候选替换。JLS 平衡数据集 Kodaira 等（2016）扩展了之前的 JLS 数据集，使其更具代表性，并包含 2,010 个泛化实例。Nishihara 和 Kajiwara（2020）创建了一个新的数据集（JWCL & JSSL），增加了日本教育词汇表（JEV）。它包含 18,000 个日语词汇，分为三个难度等级：简单、中等或困难。

#### 汉语

Personalized-ZH Lee 和 Yeung（2018a）包含 600 个中文词汇。每个词汇的复杂性由八名中文学习者在 5 点评分量表上进行排名。HanLS 由 Qiang 等（2021）构建。它包含 534 个中文复杂词汇。5 名以中文为母语的标注者提供并排名了候选替换。每个复杂词汇平均有 8 个候选替换。

## 5 讨论与结论

自从 2017 年 Paetzold 和 Specia 的 LS 调查（2017b）以来，深度学习方法在这一领域取得了新的进展。MLM 现在是 SG 的首选方法，最近的大多数 LS 研究都采用了 MLM 目标。对话语言模型 GPT-3，在进行提示学习时超越了所有其他方法的表现，尤其是当考虑到提示的集合时（表 3）。MLM 或对话语言建模的预测分数已取代了各种 SS 和 SR 技术。那些除了对 LLM 的预测分数进行排名之外，几乎不使用 SS 和不使用 SR 的 LS 系统，已超越了更多技术性、特征导向和无监督的排名方法（表 3）。然而，关于等效分数 Li 等（2022）的研究表明，它在 SR 方面仍然有效。

未来的 LS 系统将利用深度学习的新进展。我们相信，鉴于其在 SG 领域的最先进表现，**prompt learning**和类似 GPT-3 的模型将变得越来越受欢迎。使用各种提示的集合进行 SS 和 SR 可能会提升 LS 的表现。此外，创建类似于等效分数的新指标也将是有益的。

### 5.1 LS 中的开放挑战

LS 有许多未解决或现有工作尚无结论的开放研究领域。在这一简要部分，我们通过概述一些关键领域来总结这项调查，为 LS 研究的未来发展提供方向。

#### 评估：

我们用于评估 LS 的指标并不完美（第 2.1 节）。将广泛问题压缩成单一数值分数的自动化指标可能会对人类参与者的结果产生负面影响。开发更可靠的资源以及与简化系统的预期用户群体进行直接评估是未来工作的一个有益方向。这可以通过考虑数据注释的变异，而不是像当前大多数可用数据集中那样汇总的唯一注释标签来完成。

#### 可解释性：

词汇简化本质上比句子简化更具可解释性，因为操作直接在词汇层面上进行。然而，是否简化以及选择哪个词的决策过程越来越隐藏在模型的黑箱中。解释和解读这些决策的工作将帮助研究人员更好地理解将现代 NLP 技术应用于 LS 研究的机遇和威胁。

#### 个性化：

一种模型并不适用于所有人。语言学习者、脑卒中患者和儿童的简化需求各不相同。建模这些需求并利用它们个性化 LS 系统，将允许提供更符合特定用户群体需求的个性化简化输出。

#### Perspectivism:

即使在具有共同特征的群体中，每个个体也会对简化的内容和方式带来独特的视角。能够根据每个用户的需求调整输出的系统，将提供超越我们当前技术的适应性简化。这反过来将改善对 LS 模型的评估，正如本节之前讨论的那样。

#### Integration:

LS 只是更广泛简化拼图的一部分。将 LS 系统与解释生成、冗余去除和句子拆分整合，将进一步加速自动化简化实践的推广，让这些技术超越研究领域，触及更广泛的受众。

## References

+   Al-Thanyyan 和 Azmi（2021）Suha S. Al-Thanyyan 和 Aqil M. Azmi. 2021. 自动化文本简化：综述。*ACM Comput. Surv.*，54(2)。

+   Alarcón 等（2021a）Rodrigo Alarcón、Lourdes Moreno 和 Paloma Martínez. 2021a. 探索西班牙语词嵌入用于词汇简化。在*CTTS 会议录*中。

+   Alarcón 等（2021b）Rodrigo Alarcón、Lourdes Moreno 和 Paloma Martínez. 2021b. 改进网页可访问性的词汇简化系统。*IEEE Access*，9:58755–58767。

+   Aleksandrova 和 Brochu Dufour（2022）Desislava Aleksandrova 和 Olivier Brochu Dufour. 2022. RCML 在 TSAR-2022 共享任务中的应用：带有模块化替代候选排名的词汇简化。在*TSAR 会议录*中。

+   Aluísio 和 Gasperin（2010）Sandra Maria Aluísio 和 Caroline Gasperin. 2010. 促进数字包容性和可访问性：porsimples 项目用于简化葡萄牙语文本。在*YIWCALA 会议录*中。

+   Arefyev 等（2020）Nikolay Arefyev、Boris Sheludko、Alexander Podolskiy 和 Alexander Panchenko. 2020. 始终牢记目标：研究语义并提高神经词汇替代的表现。在*COLING 会议录*中。

+   Aumiller 和 Gertz（2022）Dennis Aumiller 和 Michael Gertz. 2022. UniHD 在 TSAR-2022 共享任务中的应用：计算是否是词汇简化所需的一切？在*TSAR 会议录*中。

+   Billami 等（2018）Mokhtar B. Billami、Thomas François 和 Núria Gala. 2018. ReSyf：一个带有排名同义词的法语词典。在*ACL 会议录*中。

+   Bojanowski 等（2016）Piotr Bojanowski、Edouard Grave、Armand Joulin 和 Tomas Mikolov. 2016. 通过子词信息丰富词向量。*arXiv 预印本 arXiv:1607.04606*。

+   Brown 等（2020）Tom B. Brown、Benjamin Mann、Nick Ryder、Melanie Subbiah、Jared Kaplan、Prafulla Dhariwal 和其他人. 2020. 语言模型是少样本学习者。在*NeurIPS 会议录*中。

+   Cañete et al. (2020) José Cañete, Gabriel Chaperon, Rodrigo Fuentes, Jou-Hui Ho, Hojin Kang 和 Jorge Pérez. 2020. 西班牙语预训练 BERT 模型及评估数据。见于 *PML4DC at ICLR 会议论文集*。

+   Clark et al. (2020) Kevin Clark, Minh-Thang Luong, Quoc Le 和 Christopher Manning. 2020. ELECTRA: 预训练文本编码器作为判别器而非生成器。见于 *ICLR 会议论文集*。

+   Conneau et al. (2020) Alexis Conneau, Kartikay Khandelwal, Naman Goyal, Vishrav Chaudhary 和其他人。2020. 大规模无监督跨语言表示学习。见于 *ACL 会议论文集*。

+   De la Rosa and Fernández (2022) Javier De la Rosa 和 Andres Fernández. 2022. 基于 BERTIN GPT-J-6B 的西班牙语零样本阅读理解与推理。见于 *SEPLN 会议论文集*。

+   Devlin et al. (2019) Jacob Devlin, Ming-Wei Chang, Kenton Lee 和 Kristina Toutanova. 2019. Bert: 深度双向变换器的预训练用于语言理解。见于 *NAACL 会议论文集*。

+   Ermakova et al. (2021) Liana Ermakova, Patrice Bellot, Pavel Braslavski, Jaap Kamps, Josiane Mothe 和其他人。2021. SimpleText CLEF 2021 研讨会及试点任务概述。见于 *LREC 会议论文集*。

+   Fandiño et al. (2022) Asier Gutiérrez Fandiño, Jordi Armengol Estapé, Marc Pàmies, Joan Llop Palao, Joaquin Silveira Ocampo 和其他人。2022. Maria: 西班牙语语言模型。*Procesamiento del Lenguaje Natural*, 68。

+   Ferres and Saggion (2022) Daniel Ferres 和 Horacio Saggion. 2022. ALEXSIS: 用于西班牙语词汇简化的数据集。见于 *LREC 会议论文集*。

+   Hartmann and Aluísio (2020) Nathan Siegle Hartmann 和 Sandra Maria Aluísio. 2020. 巴西葡萄牙语信息文本的自动词汇适应。*Linguamática*, 12(2):3–27。

+   Horn et al. (2014) Colby Horn, Cathryn Manduca 和 David Kauchak. 2014. 使用维基百科学习词汇简化器。见于 *ACL 会议论文集*。

+   Kajiwara and Yamamoto (2015) Tomoyuki Kajiwara 和 Kazuhide Yamamoto. 2015. 用于日语词汇简化的评估数据集和系统。见于 *ACL 会议论文集*。

+   Kodaira et al. (2016) Tomonori Kodaira, Tomoyuki Kajiwara 和 Mamoru Komachi. 2016. 用于日语词汇简化的受控和平衡数据集。见于 *ACL 会议论文集*。

+   Leal et al. (2018) Sidney Evaldo Leal, Magali Sanches Duran 和 Sandra Maria Aluísio. 2018. 用于评估葡萄牙语句子可读性的非平凡句子语料库。见于 *COLING 会议论文集*。

+   Lee and Yeung (2018a) John Lee 和 Chak Yan Yeung. 2018a. 为汉语作为外语学习者自动预测词汇知识。见于 *ICNLSP 会议论文集*。

+   Lee and Yeung (2018b) John Lee 和 Chak Yan Yeung. 2018b. 个性化词汇简化。见于 *COLING 会议论文集*。

+   Li et al. (2022) Xiaofei Li, Daniel Wiechmann, Yu Qiao 和 Elma Kerz. 2022. MANTIS 在 TSAR-2022 共享任务中的应用：基于预训练编码器的改进无监督词汇简化。见于 *TSAR 会议论文集*。

+   Liu 等 (2019) Yinhan Liu, Myle Ott, Naman Goyal, Jingfei Du 和其他人。2019. Roberta：一种稳健优化的 BERT 预训练方法。*arXiv 预印本 arXiv:1907.11692*。

+   Maddela 和 Xu (2018) Mounica Maddela 和 Wei Xu. 2018. 一种词汇复杂性词典和用于词汇简化的神经可读性排名模型。在 *EMNLP 会议论文集* 中。

+   McCarthy 和 Navigli (2007) Diana McCarthy 和 Roberto Navigli. 2007. SemEval-2007 任务 10：英语词汇替代任务。在 *SemEval 会议论文集* 中。

+   Melamud 等 (2016) Oren Melamud, Jacob Goldberger 和 Ido Dagan. 2016. context2vec：通过双向 LSTM 学习通用上下文嵌入。在 *SIGNLL 会议论文集* 中。

+   Merejildo (2021) Borbor Merejildo. 2021. 创建西班牙语大学文本语料库以识别复杂词汇在词汇简化领域的应用。硕士论文，瓜亚基尔大学。

+   Mikolov 等 (2013) Tomas Mikolov, Kai Chen, Greg Corrado 和 Jeffrey Dean. 2013. 在向量空间中有效估计词表示。在 *ICLR 会议论文集* 中。

+   Nishihara 和 Kajiwara (2020) Daiki Nishihara 和 Tomoyuki Kajiwara. 2020. 用于日语词汇简化的词汇复杂性估计。在 *LREC 会议论文集* 中。

+   North 等 (2022a) Kai North, Alphaeus Dmonte, Tharindu Ranasinghe 和 Marcos Zampieri. 2022a. GMU-WLV 在 TSAR-2022 共享任务中的表现：评估词汇简化模型。在 *TSAR 会议论文集* 中。

+   North 等 (2022b) Kai North, Marcos Zampieri 和 Matthew Shardlow. 2022b. 词汇复杂性预测：概述。*ACM 计算机调查*，55(9)。

+   Paetzold 和 Specia (2016a) Gustavo Paetzold 和 Lucia Specia. 2016a. SemEval 2016 任务 11：复杂词汇识别。在 *SemEval 会议论文集* 中。

+   Paetzold 和 Specia (2017a) Gustavo Paetzold 和 Lucia Specia. 2017a. 使用神经排名的词汇简化。在 *EACL 会议论文集* 中。

+   Paetzold 和 Specia (2017b) Gustavo H. Paetzold 和 Lucia Specia. 2017b. 词汇简化调查。*J. Artif. Int. Res.*，60(1):549–593。

+   Paetzold 和 Specia (2016b) Gustavo Henrique Paetzold 和 Lucia Specia. 2016b. 词汇简化系统的基准测试。在 *LREC 会议论文集* 中。

+   Paetzold 和 Specia (2016c) Gustavo Henrique Paetzold 和 Lucia Specia. 2016c. 针对非母语者的无监督词汇简化。在 *AAAI 会议论文集* 中。

+   Peters 等 (2018) Matthew E. Peters, Mark Neumann, Mohit Iyyer, Matt Gardner, Christopher Clark, Kenton Lee 和 Luke Zettlemoyer. 2018. 深度上下文化词表示。在 *NAACL 会议论文集* 中。

+   Przybyła 和 Shardlow (2020) Piotr Przybyła 和 Matthew Shardlow. 2020. 多词汇词汇简化。在 *COLING 会议论文集* 中。

+   Qiang 等 (2020) Jipeng Qiang, Yun Li, Zhu Yi, Yunhao Yuan 和 Xindong Wu. 2020. 使用预训练编码器进行词汇简化。在 *AAAI 会议论文集* 中。

+   Qiang 等 (2021) Jipeng Qiang、Xinyu Lu、Yun Li、Yunhao Yuan 和 Xindong Wu。2021。中文词汇简化。*IEEE/ACM 音频、语音和语言处理期刊*, 29:1819–1828。

+   Rolin 等 (2021) Eva Rolin、Quentin Langlois、Patrick Watrin 和 Thomas François。2021。FrenLyS：一种自动简化法语普通语言文本的工具。在 *RANLP 会议录* 中。

+   Saggion 等 (2022) Horacio Saggion、Sanja Štajner、Daniel Ferrés、Kim Cheng Sheang、Matthew Shardlow、Kai North 和 Marcos Zampieri。2022。TSAR-2022 共享任务中多语言词汇简化的发现。在 *TSAR 会议录* 中。

+   Seneviratne 等 (2022) Sandaru Seneviratne、Elena Daskalaki 和 Hanna Suominen。2022。CILS 在 TSAR-2022 共享任务中的表现：探讨词汇替换方法在词汇简化中的适用性。在 *TSAR 会议录* 中。

+   Shardlow (2013) Matthew Shardlow。2013。CW 语料库：评估复杂词识别的新资源。在 *ACL 会议录* 中。

+   Shardlow 等 (2020) Matthew Shardlow、Michael Cooper 和 Marcos Zampieri。2020。CompLex - 一个新的 Likert 量表数据词汇复杂性预测语料库。在 *READI 会议录* 中。

+   Song 等 (2020) Jiayin Song、Jingyue Hu、Leung-Pun Wong、Lap-Kei Lee 和 Tianyong Hao。2020。基于混合排名的社区导向词汇简化的新方法。在 *DASFAA 会议录* 中。

+   Souza 等 (2020) Fábio Souza、Rodrigo Nogueira 和 Roberto Lotufo。2020。BERTimbau：针对巴西葡萄牙语的预训练 BERT 模型。在 *BRACIS 会议录* 中。

+   Specia 等 (2012) Lucia Specia、Kumar Jauhar、Sujay 和 Rada Mihalcea。2012。Semeval - 2012 任务 1：英语词汇简化。在 *SemEval 会议录* 中。

+   Trask 等 (2015) Andrew Trask、Phil Michalak 和 John Liu。2015。sense2vec - 一种快速准确的词义消歧方法，基于神经词嵌入。*ArXiv*, abs/1511.06388。

+   Uchida 等 (2018) Satoru Uchida、Shohei Takada 和 Yuki Arase。2018。基于 CEFR 的词汇简化数据集。在 *LREC 会议录* 中。

+   Vásquez-Rodríguez 等 (2022) Laura Vásquez-Rodríguez、Nhung Nguyen、Sophia Ananiadou 和 Matthew Shardlow。2022。UoM&MMU 在 TSAR-2022 共享任务中的表现：用于词汇简化的提示学习。在 *TSAR 会议录* 中。

+   Whistely 等 (2022) Peniel John Whistely、Sandeep Mathias 和 Galiveeti Poornima。2022。PresiUniv 在 TSAR-2022 共享任务中的表现：多语言复杂词的简化替代词生成与排序。在 *TSAR 会议录* 中。

+   Wilkens 等 (2022) Rodrigo Wilkens、David Alfter、Rémi Cardon、Isabelle Gribomont 和其他人。2022。CENTAL 在 TSAR-2022 共享任务中的表现：上下文如何影响 BERT 生成的词汇简化替代词？在 *TSAR 会议录* 中。

+   Yang 等人 (2019) Zhilin Yang, Zihang Dai, Yiming Yang, Jaime Carbonell, Ruslan Salakhutdinov 和 Quoc V. Le. 2019. XLNet：语言理解的广义自回归预训练。在 *NeurIPS 论文集* 中。

+   Yeung 和 Lee (2018) Chak Yan Yeung 和 John Lee. 2018. 针对中文学习者的个性化文本检索。在 *COLING 论文集* 中。

+   Yimam 等人 (2018) Seid Muhie Yimam, Chris Biemann, Shervin Malmasi, Gustavo Paetzold, Luci Specia, Sanja Štajner, Anaïs Tack 和 Marcos Zampieri. 2018. 关于复杂词识别共享任务 2018 的报告。在 *BEA 论文集* 中。

+   Zambrano 和 Ráez (2020) Jenny Alexandra Ortiz Zambrano 和 Arturo Montejo Ráez. 2020. ALexS 2020 概述：SEPLN 首次词汇分析研讨会。在 *ALexS 论文集* 中。

## 附录 A 附录

|  | 数据集 | LS 流程 | 语言 | # CWs | 平均 # Subs | 领域 | 注释员 | 论文 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pre-2017 | LS–2007* | SG, SS | EN | 201 | 1 | 混合 | 5 英国基础。 | McCarthy 和 Navigli (2007) |
| PorSimples | SG, SS | PT | 3066 | 1 | 新闻 | 1 语言学家。 | Aluísio 和 Gasperin (2010) |
| LS–2012* | SG, SS, SR | EN | 201 | 5 | 混合 | L1 英语说话者。 | Specia 等人 (2012) |
| CW Corpus | SS | EN | 731 | 0 | Wikipedia | Wikipedia 编辑。 | Shardlow (2013) |
| LexMTurk | SG, SS, SR | EN | 500 | 50 | Wikipedia | 50 美国基础。 | Horn 等人 (2014) |
| JLS | SG, SS, SR | JP | 243 | 5 | 混合 | 5 L1 JP 说话者。 | Kajiwara 和 Yamamoto (2015) |
| JLS Balanced | SG, SS, SR | JP | 2,010 | 5 | 混合 | L1 JP 说话者 | Kodaira 等人 (2016) |
| CWI–2016* | SS | EN | 90,458 | 0 | 新闻 | 400 L2 EN 说话者。 | Paetzold 和 Specia (2016a) |
| BenchLS | SG, SS, SR | EN | 929 | 7 | 混合 | 美国基础。 | Paetzold 和 Specia (2016b) |
| NNSeval | SG, SS, SR | EN | 239 | 7 | 混合 | 400 L2 EN 说话者。 | Paetzold 和 Specia (2016c) |
| Post-2017 | CERF-LS | SG, SS, SR | EN | 406 | 12 | 学术 | 1 L1 EN 说话者。 | Uchida 等人 (2018) |
| Personalized-ZH | SG, SS, SR | ZH | 600 | 7 | 混合 | 8 L1 ZH 说话者 | Lee 和 Yeung (2018a) |
| WCL | SS, SR | EN | 15,000 | 0 | 混合 | 11 L2 EN 说话者。 | Maddela 和 Xu (2018) |
| ReSyf | SG, SS | FR | 57,589 | 3 | 混合 | L1 FR 说话者。 | Billami 等人 (2018) |
| Personalized-LS | SG, SS, SR | EN | 929 | 7 | 混合 | 15 L2 EN 说话者。 | Lee 和 Yeung (2018b) |
| CWI–2018* | SS, SR | EN, FR, GR, ES | 62,550 | 0 | 新闻 | L1&L2 EN 说话者。 | Yimam 等人 (2018) |
| PorSimplesSent | SG, SS | PT | 6109 | 1 | 新闻 | 3 语言学家。 | Leal 等人 (2018) |
| LCP-2021* | SS, SR | EN | 10,800 | 0 | 混合 | 7 美国/英国/澳大利亚基础。 | Shardlow 等人 (2020) |
| SIMPLEX-PB | SG, SS, SR | PT | 730 | 5 | 学术 | pt-BR 说话者。 | Hartmann 和 Aluísio (2020) |
| JWCL-JSSL | SG | JP | 18,000 | 0 | 综合 | 5 名母语日语使用者。 | Nishihara 和 Kajiwara (2020) |
| ALexS-2020* | SG | ES | 723 | 0 | 学术 | 430 名西班牙语使用者。 | Zambrano 和 Ráez (2020) |
| SimpleText-2021* | SG, SS, SR | EN | 1000 | 10 | 学术 | 参与团队。 | Ermakova 等 (2021) |
| ES-CWI | SG | ES | 3,887 | 0 | 学术 | 40 名母语西班牙语使用者。 | Merejildo (2021) |
| EASIER | SG, SS | ES | 5,310 | 3 | 新闻 | 母语西班牙语使用者。 | Alarcón 等 (2021b) |
| FrenLys | SG, SS, SR | FR | 57,589 | 3 | 综合 | 20 名母语法语使用者。 | Rolin 等 (2021) |
| HanLS | SG, SS, SR | ZH | 534 | 8 | 综合 | 5 名母语中文使用者。 | Qiang 等 (2021) |
| TSAR-2022* | SG, SS, SR | EN, ES, PT | 1153 | 20 | 新闻 | 21 名来自英国/西班牙/巴西的使用者。 | Saggion 等 (2022) |

表 2：按时间顺序排列的可用于语言服务的 数据集。标记数据集 (*) 在基准测试中使用。L1 和 L2 指第一语言和第二语言的使用者。
