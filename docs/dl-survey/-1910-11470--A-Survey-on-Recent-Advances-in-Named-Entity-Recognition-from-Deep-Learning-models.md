<!--yml

分类：未分类

日期：2024-09-06 20:04:19

-->

# [1910.11470] 关于深度学习模型中命名实体识别的最新进展调查

> 来源：[`ar5iv.labs.arxiv.org/html/1910.11470`](https://ar5iv.labs.arxiv.org/html/1910.11470)

# 关于深度学习模型中命名实体识别的最新进展调查

维卡斯·亚达夫

亚利桑那大学

vikasy@email.arizona.edu

\AndSteven Bethard

亚利桑那大学

bethard@email.arizona.edu

###### 摘要

命名实体识别（NER）是自然语言处理（NLP）系统中的一个关键组件，用于问答、信息检索、关系抽取等。NER 系统已经被广泛研究和开发了几十年，但使用深度神经网络（NN）的准确系统仅在最近几年才被引入。我们提供了一个关于 NER 的深度神经网络架构的综合调查，并将其与基于特征工程和其他监督或半监督学习算法的早期 NER 方法进行了对比。我们的结果突出了神经网络所取得的改进，并展示了如何借鉴过去基于特征的 NER 系统中的一些经验教训，从而获得进一步的改进。

## 1 引言

⁰⁰脚注：本工作采用知识共享署名 4.0 国际许可证。许可证详情： http://creativecommons.org/licenses/by/4.0/

命名实体识别是识别文本中命名实体（如人名、地点、组织、药物、时间、临床程序、生物蛋白等）的任务。NER 系统通常作为问答、信息检索、共指消解、主题建模等的第一步。因此，突出命名实体识别的最新进展，特别是最近的神经 NER 架构，这些架构以最少的特征工程实现了最先进的性能，非常重要。

第一个 NER 任务由 ?) 在第六届消息理解会议上组织。从那时起，出现了许多 NER 任务 [Tjong Kim Sang 和 De Meulder (2003, Tjong Kim Sang (2002, Piskorski 等 (2017, Segura Bedmar 等 (2013, Bossy 等 (2013, Uzuner 等 (2011]。早期的 NER 系统基于手工规则、词典、正字法特征和本体。这些系统随后被基于特征工程和机器学习的 NER 系统所取代 [Nadeau 和 Sekine (2007]。从 ? 开始，具有最小特征工程的神经网络 NER 系统变得流行。这些模型受到欢迎，因为它们通常不需要特定领域的资源，如词典或本体，因此更具领域独立性。提出了各种神经架构，主要基于字符、子词和/或词嵌入上的某种形式的递归神经网络（RNN）。

我们提供了一项关于命名实体识别（NER）近期进展的全面调查。我们描述了基于知识和特征工程的 NER 系统，这些系统结合了领域内知识、词典、拼写及其他特征，并采用了监督或半监督学习。我们将这些系统与基于最小特征工程的神经网络架构进行对比，并比较了不同表示方法的神经模型。我们在表 1 和表 2 中展示，并在第七部分讨论了神经 NER 系统如何在性能上优于以往的工作，包括监督、半监督和基于知识的 NER 系统。例如，NN 模型在新闻语料库上提高了西班牙语 1.59%、德语 2.34%、英语 0.36%和荷兰语 0.14%的先前最佳水平，而无需任何外部资源或特征工程。我们提供了资源，包括 NER 共享任务的链接，以及每种类别 NER 系统的代码链接。据我们所知，这是首个专注于 NER 神经网络架构并与以往基于特征系统进行比较的调查。

我们首先在 2 节讨论先前的 NER 总结研究。然后我们在 3 节解释我们的选择标准和方法论，以选择需要审查的系统。我们在 4 节突出介绍标准的、过去和最新的 NER 数据集（来自共享任务和其他研究），以及 5 节的评估指标。然后，我们在 6 节描述 NER 系统，分类为基于知识的（6.1 节），自举（6.2 节），特征工程的（6.3 节）和神经网络的（6.4 节）。

## 2 先前的调查

第一个全面的 NER 调查是?），它涵盖了各种监督、半监督和无监督的 NER 系统，突出了当时 NER 系统使用的共同特征，并解释了至今仍在使用的 NER 评估指标。?) 提供了一个更新的 NER 调查，也包括了监督、半监督和无监督 NER 系统，并介绍了一些初步的神经网络 NER 系统。还有一些调查专注于特定领域和语言的 NER 系统，包括生物医学 NER，[Leaman 和 Gonzalez (2008]，中文临床 NER [Lei et al. (2013]，阿拉伯语 NER [Shaalan (2014，Etaiwi et al. (2017]，以及印度语言的 NER [Patil et al. (2016]。

现有的调查主要涵盖了特征工程机器学习模型（包括监督、半监督和无监督系统），并且大多集中在单一语言或单一领域。我们了解到，目前还没有全面的现代神经网络命名实体识别（NER）系统的调查，也没有在多语言（CoNLL 2002 和 CoNLL 2003）和多领域（如新闻和医疗）环境下比较特征工程和神经网络系统的调查。

## 3 方法论

为了识别用于本次调查的文章，我们搜索了 Google、Google Scholar 和 Semantic Scholar。我们的查询词包括命名实体识别、用于命名实体识别的神经架构、基于神经网络的命名实体识别模型、用于命名实体识别的深度学习模型等。我们按引用次数对每个查询返回的论文进行了排序，并至少阅读了前三篇，考虑将论文纳入我们的调查，如果它要么介绍了一种用于命名实体识别的神经架构，要么代表了在 NER 数据集上表现优秀的模型。我们仅在文章首次介绍了该架构的情况下才包含介绍神经架构的文章；否则，我们追溯引用，直到找到该架构的原始来源。我们对特征工程 NER 系统采用了相同的方法。我们还包括了为不同语言或领域实现这些系统的文章。总共审阅了 154 篇文章，其中 83 篇文章被选入调查。

## 4 个 NER 数据集

自从第一个 NER 共享任务[Grishman 和 Sundheim (1996]¹¹1 共享任务: https://www-nlpir.nist.gov/related_projects/muc/，许多 NER 共享任务和数据集被创建。CoNLL 2002 [Tjong Kim Sang (2002]²²2 共享任务: https://www.clips.uantwerpen.be/conll2002/ner/和 CoNLL 2003 [Tjong Kim Sang 和 De Meulder (2003]³³3 共享任务: https://www.clips.uantwerpen.be/conll2003/ner/，分别从四种不同语言（西班牙语、荷兰语、英语和德语）的新闻稿中创建，重点关注 4 种实体 - PER（人）、LOC（地点）、ORG（组织）和 MISC（其他，包括所有其他类型的实体）。

NER 共享任务还针对各种其他语言组织过，包括印度语言 [Rajeev Sangal 和 Singh (2008]，阿拉伯语 [Shaalan (2014]，德语 [Benikova 等 (2014] 和斯拉夫语言 [Piskorski 等 (2017]。命名实体类型根据数据集的来源和语言差异很大。例如，？）的东南亚语言数据具有命名实体类型为人、职称、时间表达、缩写、物体编号、品牌等。？）的数据基于德语维基百科和在线新闻，具有类似于 CoNLL 2002 和 2003 的命名实体类型：PERson、ORGanization、LOCation 和 OTHer。由？）组织的共享任务⁴⁴4 共享任务: http://bsnlp.cs.helsinki.fi/shared_task.html 涵盖了 7 种斯拉夫语言（克罗地亚语、捷克语、波兰语、俄语、斯洛伐克语、斯洛文尼亚语、乌克兰语），也包括了人、地点、组织和杂项作为命名实体类型。

在生物医学领域，?) 组织了一个针对 MedLine 摘要的 BioNER 任务，重点关注蛋白质、DNA、RNA 和细胞属性实体类型。?) 提出了一个临床笔记去标识化任务，要求 NER 定位需要匿名化的个人患者数据短语。2010 年的 I2B2 NER 任务⁵⁵5 共享任务: https://www.i2b2.org/NLP/Relations/ [Uzuner et al. (2011]，该任务考虑了临床数据，重点关注临床问题、测试和治疗实体类型。?) 作为 SemEval 2013 任务 9 的一部分，组织了一个药物 NER 共享任务⁶⁶6 共享任务: https://www.cs.york.ac.uk/semeval-2013/task9/index.html，重点关注药物、品牌、类别和药物 _n（未经批准或新药）实体类型。[Krallinger et al. (2015] 引入了类似的 CHEMDNER 任务 ⁷⁷7 类似数据集可以在此找到: http://www.biocreative.org，更多关注化学和药物实体，如常见名称、系统名称、缩写、公式、家族、标识符等。生物学和微生物学 NER 数据集⁸⁸8 共享任务: http://2016.bionlp-st.org/tasks/bb2 [Hirschman et al. (2005、Bossy et al. (2013、Delėger et al. (2016] 从 PubMed 和生物学网站收集，主要关注细菌、栖息地和地理位置实体。在生物医学 NER 系统中，临床和药物实体的分割被认为是一项困难的任务，因为命名实体的复杂正字法结构 [Liu et al. (2015]。

NER 任务也在社交媒体数据上组织，例如 Twitter，其中经典 NER 系统的性能由于正字法变化和语法不完整句子等问题而下降 [Baldwin et al. (2015]。Twitter 上的实体类型也更加多样化（个人、公司、设施、乐队、运动队、电影、电视节目等），因为它们基于 Twitter 上的用户行为。

尽管大多数命名实体标注是平面的，但一些数据集包括更复杂的结构。?) 构建了一个嵌套命名实体的数据集，其中一个命名实体可以包含另一个命名实体。?) 突出了实体和实体头短语。并且在化学和临床 NER 数据集中，不连续的实体是常见的 [Krallinger et al. (2015]。?) 对各种 NER 系统进行了调查，重点关注化学 NER。

## 5 个命名实体识别（NER）评估指标

?) 基于类型对 NER 性能进行了评分，不管实体边界如何，预测标签是否正确；以及文本，对预测的实体边界是否正确，不管标签如何。对于每个评分类别，精确度被定义为系统正确预测的实体数量与系统预测的实体数量之比，召回率被定义为系统正确预测的实体数量与人工标注者识别的实体数量之比，(微观) F 分数被定义为精确度和召回率的调和平均数，涵盖了类型和文本。

CoNLL 引入的精确匹配指标 [Tjong Kim Sang and De Meulder (2003, Tjong Kim Sang (2002] 仅当完整实体的预测标签与该实体的黄金标签完全匹配时，才认为预测正确。CoNLL 还使用了（微）F 值，计算精确匹配的 F 值的调和均值。

放宽的 F1 和严格的 F1 指标已在许多 NER 共享任务中使用 [Segura Bedmar et al. (2013, Krallinger et al. (2015, Bossy et al. (2013, Delėger et al. (2016]。放宽的 F1 只要部分命名实体被正确识别，就认为预测正确。严格的 F1 要求预测的字符偏移量与人工标注完全匹配。在这些数据中，与 CoNLL 不同，未提供词偏移量，因此放宽的 F1 旨在允许比较，尽管不同系统由于不同的分词技术而具有不同的词边界 [Liu et al. (2015]。

## 6 个 NER 系统

### 6.1 基于知识的系统

基于知识的 NER 系统不需要标注的训练数据，因为它们依赖于词典资源和领域特定知识。当词典详尽时，这些系统表现良好，但例如，在 DrugNER 数据集中，每个 drug_n 类的例子都失败了 [Segura Bedmar et al. (2013]，因为 drug_n 定义为未经批准或新药，而这些药物的定义本质上不在 DrugBank 词典中 [Knox et al. (2010]。由于词典的存在，基于知识的 NER 系统的精确度通常很高，但由于领域和语言特定规则以及不完整的词典，召回率往往较低。基于知识的 NER 系统的另一个缺点是需要领域专家来构建和维护知识资源。

### 6.2 无监督和自举系统

一些最早的系统只需非常少量的训练数据。?) 仅使用了标记种子和 7 种特征，包括正字法（例如，大小写）、实体的上下文、命名实体中包含的词等，用于分类和提取命名实体。?) 提出了一个无监督系统，通过将 8 种通用模式提取器应用于开放网页文本（例如，NP“是一个” $<$class1$>$，NP1“例如” NPList2），以提高 NER 系统的召回率。?) 提出了一个基于?) 和?) 的无监督系统，用于建立地名词典和命名实体歧义解决，结合了一个提取的地名词典和常用的地名词典，在 MUC-7 [Chinchor and Robinson (1997] 上实现了 88%、61%和 59%的 F 值，分别对应地点、人物和组织实体。

?) 使用浅层句法知识和逆文档频率（IDF）用于生物学 [Kim et al. (2004] 和医学 [Uzuner et al. (2011] 数据上的无监督 NER 系统，分别达到了 53.8%和 69.5%的准确率。他们的模型使用种子发现具有潜在命名实体的文本，检测名词短语并过滤低 IDF 值的短语，然后将过滤后的列表输入分类器 [Alfonseca and Manandhar (2002] 来预测命名实体标签。

### 6.3 特征工程监督系统

监督机器学习模型通过在示例输入及其预期输出上进行训练，学习进行预测，并可以替代人工制定的规则。隐马尔可夫模型（HMM）、支持向量机（SVM）、条件随机场（CRF）和决策树是 NER（命名实体识别）常用的机器学习系统。

?) 使用 HMM [Rabiner and Juang (1986, Bikel et al. (1997] 在 MUC-6 和 MUC-7 数据上进行 NER 系统的实现，分别取得了 96.6%和 94.1%的 F 分数。他们包括了 11 个正字法特征（1 个数字，2 个数字，4 个数字，全大写，数字和字母，是否包含下划线等），一个命名实体的触发词列表（例如，地点实体类别的 36 个触发词和词缀，如 river），以及来自各种地名词典的 10000 个词（用于人名实体类别）。

?) 通过添加多个特征比较了 HMM 与最大熵（ME）。他们的最佳模型包括了大写、一个词是否是句子的第一个词、一个词是否之前出现过且有已知姓氏，以及从各种词典中收集的 13281 个名字。该模型在西班牙语和荷兰语 CoNLL 2002 数据集上分别达到了 73.66%和 68.08%的 F 分数。

CoNLL 2002 的获胜者 [Carreras et al. (2002] 使用了二元 AdaBoost 分类器，这是一种结合小型固定深度决策树的提升算法 [Schapire (2013]。他们使用了如大写、触发词、先前标签预测、词袋、词典等特征来表示简单的二元关系，这些关系与先前预测的标签结合使用。他们在西班牙语和荷兰语 CoNLL 2002 数据集上分别达到了 81.39%和 77.05%的 F 分数。

?) 在 CoNLL 2003 数据集和 CMU 研讨会文档上实现了 SVM 模型。他们尝试了多种窗口大小、来自邻近词的特征（正字法、前缀、后缀、标签等），根据位置加权邻近词特征，以及用以平衡正负类别的类权重。他们使用了两个 SVM 分类器，一个用于检测命名实体的开始，另一个用于检测结束。他们在英文 CoNLL 2003 数据上取得了 88.3%的 F 分数。

在 MUC6 数据上，?) 使用了词性（POS）标签、正字法特征、中心词左侧和右侧各 3 个单词的窗口，以及最后 3 个单词的标签作为 SVM 的特征。最终标签由多个一对一 SVM 输出的投票决定。

?) 实现了结构学习 [Ando and Zhang (2005b]，将主要任务分解为多个辅助任务，例如，通过仅查看上下文和屏蔽当前词来预测标签。根据每个辅助任务的置信度选择最佳分类器。该模型在英语和德语上的 F 分数分别达到了 89.31%和 75.27%。

?) 开发了一个半监督系统⁹⁹9 代码：https://github.com/ixa-ehu/ixa-pipe-nerc，向 NER 分类器提供了包括正字法、字符 n-gram、词典、前缀、后缀、大词组、三词组以及来自布朗语料库、克拉克语料库和使用词嵌入的开放文本 k 均值聚类的无监督聚类特征等特征。他们在 CoNLL 数据集上取得了接近最先进的表现：西班牙语 84.16%、荷兰语 85.04%、英语 91.36%、德语 76.42%。

在 DrugNER [Segura Bedmar et al. (2013] 中，?) 通过使用具有来自食品药品监督管理局（FDA）、DrugBank、Jochem [Hettne et al. (2009] 的词典资源和词嵌入（在 MedLine 语料库上训练）的 CRF 取得了最先进的结果。在同一任务中，?) 使用了具有来自词典（例如 Jochem [Hettne et al. (2009]）、本体（ChEBI 本体）、化学实体的前后缀等构造特征的 CRF。

### 6.4 特征推断神经网络系统

?) 提出了首批用于 NER 的神经网络架构之一，特征向量由正字法特征（例如首字母大写）、词典和词汇表构成。后来的工作用词嵌入 [Collobert et al. (2011] 替代了这些手动构造的特征向量，词嵌入是在$n$维空间中的词的表示，通常通过无监督过程如 skip-gram 模型 [Mikolov et al. (2013] 从大量未标记数据中学习得到。研究表明，这种预训练的词嵌入对基于神经网络的 NER 系统至关重要 [Habibi et al. (2017]，同样对于中文等字符语言中的预训练字符嵌入也具有类似的重要性 [Li et al. (2015, Yin et al. (2016]。

现代 NER 神经网络架构可以根据其对句子中单词的表示大致分为几类。例如，表示可以基于单词、字符、其他子词单元或这些的任何组合。

#### 6.4.1 单词级架构

`<svg   height="142.03" overflow="visible" version="1.1" width="575.54"><g transform="translate(0,142.03) matrix(1 0 0 -1 0 0) translate(70.77,0) translate(0,2.21)" fill="#000000" stroke="#000000"><g stroke-width="0.4pt"><g transform="matrix(0.8 0.0 0.0 0.8 -31.17 18.2)" fill="#000000" stroke="#000000"><foreignobject width="38.55" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Words</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -58.27 41.33)" fill="#000000" stroke="#000000"><foreignobject width="105.93" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Word Embedding</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -51.89 62.3)" fill="#000000" stroke="#000000"><foreignobject width="90.36" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Word LSTM-F</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -52.2 84.35)" fill="#000000" stroke="#000000"><foreignobject width="91.13" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Word LSTM-B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -67.08 107.47)" fill="#000000" stroke="#000000"><foreignobject width="128.72" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Word Representation</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -29.2 128.44)" fill="#000000" stroke="#000000"><foreignobject width="33.25" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Label</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 68.02 18.27)" fill="#000000" stroke="#000000"><foreignobject width="26.79" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Best</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 60.41 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 147.56 19.34)" fill="#000000" stroke="#000000"><foreignobject width="24.79" height="12.15" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Buy</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 141.07 128.5)" fill="#000000" stroke="#000000"><foreignobject width="41.03" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">I-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 232.5 18.2)" fill="#000000" stroke="#000000"><foreignobject width="9.3" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">’s</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 231.92 128.5)" fill="#000000" stroke="#000000"><foreignobject width="10.76" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">O</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 302.89 18.27)" fill="#000000" stroke="#000000"><foreignobject width="30.17" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">CEO</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 310.66 128.5)" fill="#000000" stroke="#000000"><foreignobject width="10.76" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">O</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 376.47 18.2)" fill="#000000" stroke="#000000"><foreignobject width="43.09" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Hubert</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 376.33 128.5)" fill="#000000" stroke="#000000"><foreignobject width="43.43" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-PER</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 462.37 19.28)" fill="#000000" stroke="#000000"><foreignobject width="25.18" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Joly</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 456.99 128.5)" fill="#000000" stroke="#000000"><foreignobject width="38.63" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">I-PER</foreignobject></g></g></g></svg>`

图 1：用于 NER 的词级神经网络架构

在这种架构中，句子的单词作为输入提供给递归神经网络（RNN），每个单词由其词嵌入表示，如图 1 所示。

第一个词级神经网络模型由?）提出¹⁰¹⁰10 代码： https://ronan.collobert.com/senna/。该架构类似于图 1 中所示，但使用了卷积层代替了 Bi-LSTM 层，并将卷积层的输出传递给 CRF 层进行最终预测。作者通过包括地名词典和 SENNA 嵌入，在英文 CoNLL 2003 数据集上达到了 89.59%的 F1 分数。

?）提出了一个词级 LSTM 模型（图 1），并展示了在词 LSTM 顶部添加 CRF 层可以提高性能，在英文 CoNLL 2003 数据集上达到了 84.26%的 F1 分数。类似系统应用于其他领域：DrugNER 由?）在 MedLine 测试数据上（非正式评估）达到了 85.19%的 F1 分数[Segura Bedmar 等（2013]，以及?）在疾病 NER 语料库上使用此架构实现了 80.22%的 F1 分数。在类似任务中，?）为多语言 POS 标注实现了相同的模型。

?）实现了用于英语、德语和阿拉伯语 NER 的词级前馈神经网络、双向 LSTM（bi-LSTM）和窗口 bi-LSTM，尽管有所不同。他们还突出了添加各种特征（如 CRF、大小写、POS、词嵌入）后的性能改进，在英语上达到了 88.91%的 F1 分数，在德语上达到了 76.12%的 F1 分数。

#### 6.4.2 字符级架构

<svg   height="126.44" overflow="visible" version="1.1" width="614.47"><g transform="translate(0,126.44) matrix(1 0 0 -1 0 0) translate(85.29,0) translate(0,-13.38)" fill="#000000" stroke="#000000"><g stroke-width="0.4pt"><g transform="matrix(0.8 0.0 0.0 0.8 -57.69 18.2)" fill="#000000" stroke="#000000"><foreignobject width="65.5" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -72.79 41.33)" fill="#000000" stroke="#000000"><foreignobject width="102.86" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符嵌入</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -66.41 62.3)" fill="#000000" stroke="#000000"><foreignobject width="87.29" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符 LSTM-F</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -66.72 84.35)" fill="#000000" stroke="#000000"><foreignobject width="88.06" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符 LSTM-B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -81.6 107.47)" fill="#000000" stroke="#000000"><foreignobject width="125.65" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符表示</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -44.95 128.44)" fill="#000000" stroke="#000000"><foreignobject width="33.25" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">标签</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 46.47 18.27)" fill="#000000" stroke="#000000"><foreignobject width="9.8" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 32.06 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 98.33 19.66)" fill="#000000" stroke="#000000"><foreignobject width="6.15" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">e</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 82.45 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 149 19.66)" fill="#000000" stroke="#000000"><foreignobject width="5.46" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">s</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 132.85 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 199.42 18.64)" fill="#000000" stroke="#000000"><foreignobject width="5.38" height="8.51" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">t</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 183.24 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 247.82 19.28)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">␣</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 233.64 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0

图 2：命名实体识别的字符级神经网络架构

在这个模型中，句子被视为字符序列。这个序列经过 RNN 处理，为每个字符预测标签（图 2）在单词的字符序列上使用了高速公路网络（highway networks），然后使用了另一层的 LSTM + softmax 进行最终的预测。

?) 对越南语 NER 进行了模型实现，并在?）的越南语测试数据上取得了 80.23％的 F 分数。字符模型还在其他各种语言中得到了应用，比如在中国语[Dong et al. (2016]中，它取得了接近最前沿的性能。

?) 提出了 CharNER ¹¹¹¹11Code： https://github.com/ozanarkancan/char-ner，它在 7 种不同的语言上实现了字符 RNN 模型用于 NER。在这个字符模型中，对字符的标签预测通过维特比译码器被转换成单词标签[Forney (1973]，在西班牙语上的性能达到了 82.18％，荷兰语上的性能达到了 79.36％，在英语上的性能达到了 84.52％，在德语 CoNLL 数据集上的性能达到了 70.12％。他们还在阿拉伯语上达到了 78.72％，在捷克语上达到了 72.19％，在土耳其语上达到了 91.30％的 F 分数。 ?) 提出了使用 RNN（Bi-LSTM）来表示单词，利用单词的字符，并在包括英语 PTB 在内的多种语言上，使用这种表示来取得了最先进的结果，包括英语 PTB 上的 97.78％的准确率[Marcus et al. (1993]。

?) 实现了序列到序列模型（Byte 到 Span- BTS），使用编码器解码器架构在一个窗口内的 60 个字符的单词序列上。每个字符都以字节编码，BTS 在 CoNLL 2002 和 2003 数据集上取得了很高的性能，并且没有进行任何特征工程。BTS 分别在西班牙语、荷兰语、英语和德语 CoNLL 数据集上分别取得了 82.95％、82.84％、86.50％和 76.22％的 F 分数。

#### 6.4.3 字符+单词级架构

结合词上下文和词字符的系统已被证明是强大的 NER 系统，只需很少的领域特定知识或资源。此类别有两种基本模型。第一种模型将词表示为词嵌入和词字符上的卷积的组合，然后在句子的词表示上进行 Bi-LSTM 层处理，最后在 Bi-LSTM 上使用 softmax 或 CRF 层生成标签。该模型的架构图与 Figure 3 相同，但将字符 Bi-LSTM 替换为 CNN¹²¹²12Code: https://github.com/LopezGG/NN_NER_tensorFlow。

?) 实现了该模型，在 CoNLL 2003 英语数据集上达到了 91.21% 的 F1 分数，在 PTB 的 WSJ 部分达到了 97.55% 的 POS 标记准确率 [Marcus et al. (1993]。他们还展示了该模型在词汇外词上的性能较低。

?) 通过向该模型添加词典和大写特征，在 CoNLL 2003 英语数据集上达到了 91.62% 的 F1 分数，在 Onto notes 5.0 数据集上达到了 86.28% 的 F 分数 [Pradhan et al. (2013]。词典特征以 B(begin)、I(inside) 或 E(end) PER、LOC、ORG 和 MISC 的形式编码，具体取决于字典中的匹配情况。

该模型也被用于像日语这样的语言中的 NER，其中 ?) 证明了这一架构在组织实体类别上优于其他神经架构。

?) 为 Twitter NER 实现了一个字符+词级别的 NER 模型 [Baldwin et al. (2015]，通过连接在字符上的 CNN、字符的正字法特征 CNN、词嵌入和词的正字法特征嵌入来实现。这个连接的表示经过另一个 Bi-LSTM 层，并将输出传递给 CRF 进行预测。该模型在仅分割上达到了 65.89% 的 F 分数，在分割和分类上达到了 52.41% 的 F 分数。

?) 实现了一个模型，该模型在词字符上应用 CNN，并将中央词及其邻居的词嵌入连接，输入到前馈网络中，然后通过维特比算法预测每个词的标签。该模型在西班牙语 CoNLL 2002 数据上达到了 82.21% 的 F 分数，在葡萄牙语 NER 数据上达到了 71.23% 的 F 分数 [Santos 和 Cardoso (2007]。

`<svg height="213.49" overflow="visible" version="1.1" width="614.91"><g transform="translate(0,213.49) matrix(1 0 0 -1 0 0) translate(70.77,0) translate(0,73.68)" fill="#000000" stroke="#000000"><g stroke-width="0.4pt"><g transform="matrix(0.8 0.0 0.0 0.8 -41.95 -69.99)" fill="#000000" stroke="#000000"><foreignobject width="65.5" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -57.04 -46.86)" fill="#000000" stroke="#000000"><foreignobject width="102.86" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符嵌入</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -50.66 -25.89)" fill="#000000" stroke="#000000"><foreignobject width="87.29" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符 LSTM-F</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -50.97 -3.84)" fill="#000000" stroke="#000000"><foreignobject width="88.06" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符 LSTM-B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -51.25 18.2)" fill="#000000" stroke="#000000"><foreignobject width="88.75" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词汇特征</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -67.08 41.33)" fill="#000000" stroke="#000000"><foreignobject width="128.72" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词汇表示</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -51.89 62.3)" fill="#000000" stroke="#000000"><foreignobject width="90.36" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词汇 LSTM-F</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -52.2 84.35)" fill="#000000" stroke="#000000"><foreignobject width="91.13" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词汇 LSTM-B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -42.52 106.39)" fill="#000000" stroke="#000000"><foreignobject width="66.92" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词汇 CRF</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -29.2 128.44)" fill="#000000" stroke="#000000"><foreignobject width="33.25" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">标签</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 74.82 -69.92)" fill="#000000" stroke="#000000"><foreignobject width="9.8" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 115.65 -68.53)" fill="#000000" stroke="#000000"><foreignobject width="6.15" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">e</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 155.3 -68.53)" fill="#000000" stroke="#000000"><foreignobject width="5.46" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">s</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 194.7 -69.55)" fill="#000000" stroke="#000000"><foreignobject width="5.38" height="8.51" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">t</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -10.3 18.27)" fill="#000000" stroke="#000000"><foreignobject width="26.79" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">最佳</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -16.95 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 271.67 -69.92)" fill="#000000" stroke="#000000"><foreignobject width="9.8" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 311.89 -68.53)" fill="#000000" stroke="#000000"><foreignobject width="7.69" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">u</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 351.41 -67.45)" fill="#000000" stroke="#000000"><foreignobject width="7.3" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">y</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -2.58 19.34)" fill="#000000" stroke="#000000"><foreignobject width="24.79" height="12.15" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">购买</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -8.11 128.5)" fill="#000000" stroke="#000000"><foreignobject width="41.03" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">I-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 470.91 -69.99)" fill="#000000" stroke="#000000"><foreignobject width="3.84" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">’</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 509.63 -68.53)" fill="#000000" stroke="#000000"><foreignobject width="5.46" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">s</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 10.53 18.2)" fill="#000000" stroke="#000000"><foreignobject width="9.

图 3: 用于 NER 的词+字符级别神经网络架构

第二种模型将词嵌入与 LSTM（有时是双向的）连接，通过另一个句子级 Bi-LSTM 处理这种表示，并使用最终的 softmax 或 CRF 层预测最终标签（图 3）。?)¹³¹³13 代码: https://github.com/glample/tagger 引入了这一架构，并在 CoNLL 2002 和 2003 数据集中分别在西班牙语、荷兰语、英语和德语 NER 数据上取得了 85.75%、81.74%、90.94% 和 78.76% 的 F 值。

?) 在 NeuroNER 工具包中实现了该模型¹⁴¹⁴14 代码: http://neuroner.com，主要目标是提供易用性，并允许轻松绘制模型的实时性能和学习统计数据。BRAT 注释工具¹⁵¹⁵15 代码: http://brat.nlplab.org/ 也与 NeuroNER 集成，以便于在新领域开发 NN NER 模型。NeuroNER 在英语 CoNLL 2003 数据上取得了 90.50% 的 F 值。

?) 实现了该模型用于各种生物医学 NER 任务，并取得了比大多数其他参与者更高的性能。例如，他们在 CHEMDNER 数据上取得了 83.71 的 F 值 [Krallinger et al. (2015]。

?)¹⁶¹⁶16 代码: https://github.com/dmort27/epitran 在 NER 中利用了来自 Epitran 的音素，除了字符和词之外。他们还利用了字符序列的注意力知识，并将其与词嵌入和词的字符表示进行连接。该模型在西班牙语 CoNLL 2002 数据集上达到了前沿性能（85.81% F 值）。

?) 提出了一个稍有改进的系统，该系统专注于多任务和多语言联合学习，其中由 GRU（门控递归单元）单元生成的词表示和词嵌入经过另一个 RNN 层处理，并将输出传递给为不同任务（如词性标注、短语块划分和命名实体识别）训练的 CRF 模型。?) 进一步提出了多任务和多学习的迁移学习，并在 CoNLL 2002 和 2003 NER 数据上展示了小幅改进，分别在西班牙语、荷兰语和英语上取得了 85.77%、85.19% 和 91.26% 的 F 值。

#### 6.4.4 字符 + 词 + 前缀模型

<svg   height="213.49" overflow="visible" version="1.1" width="614.91"><g transform="translate(0,213.49) matrix(1 0 0 -1 0 0) translate(70.77,0) translate(0,73.68)" fill="#000000" stroke="#000000"><g stroke-width="0.4pt"><g transform="matrix(0.8 0.0 0.0 0.8 -41.95 -69.99)" fill="#000000" stroke="#000000"><foreignobject width="65.5" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -57.04 -46.86)" fill="#000000" stroke="#000000"><foreignobject width="102.86" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符嵌入</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -50.66 -25.89)" fill="#000000" stroke="#000000"><foreignobject width="87.29" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符 LSTM-F</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -50.97 -3.84)" fill="#000000" stroke="#000000"><foreignobject width="88.06" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">字符 LSTM-B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -51.25 18.2)" fill="#000000" stroke="#000000"><foreignobject width="88.75" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词汇特征</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -67.08 41.33)" fill="#000000" stroke="#000000"><foreignobject width="128.72" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词表示</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -51.89 62.3)" fill="#000000" stroke="#000000"><foreignobject width="90.36" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词 LSTM-F</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -52.2 84.35)" fill="#000000" stroke="#000000"><foreignobject width="91.13" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词 LSTM-B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -42.52 106.39)" fill="#000000" stroke="#000000"><foreignobject width="66.92" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">词 CRF</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -29.2 128.44)" fill="#000000" stroke="#000000"><foreignobject width="33.25" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">标签</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 74.82 -69.92)" fill="#000000" stroke="#000000"><foreignobject width="9.8" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 115.65 -68.53)" fill="#000000" stroke="#000000"><foreignobject width="6.15" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">e</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 155.3 -68.53)" fill="#000000" stroke="#000000"><foreignobject width="5.46" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">s</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 194.7 -69.55)" fill="#000000" stroke="#000000"><foreignobject width="5.38" height="8.51" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">t</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -10.09 18.27)" fill="#000000" stroke="#000000"><foreignobject width="21.41" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">最</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -7.35 18.64)" fill="#000000" stroke="#000000"><foreignobject width="16.99" height="8.51" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">佳</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -10.3 18.27)" fill="#000000" stroke="#000000"><foreignobject width="26.79" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">最佳</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -16.95 128.5)" fill="#000000" stroke="#000000"><foreignobject width="45.84" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B-ORG</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 271.67 -69.92)" fill="#000000" stroke="#000000"><foreignobject width="9.8" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">B</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 311.89 -68.53)" fill="#000000" stroke="#000000"><foreignobject width="7.69" height="5.96" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">u</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 351.41 -67.45)" fill="#000000" stroke="#000000"><foreignobject width="7.3" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">y</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -4.52 19.34)" fill="#000000" stroke="#000000"><foreignobject width="24.79" height="12.15" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">购买</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -3.55 19.34)" fill="#000000" stroke="#000000"><foreignobject width="24.79" height="12.15" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">购买</foreignobject></g><g transform="matrix(0.8 0.0 0.0 0.8 -2.58 19.34)" fill="#000000" stroke="#000000"><foreignobject width="24.79" height="12

图 4：用于 NER 的词+字符+词缀级别 NN 结构

?) 实现了一种将字符+词 NN 结构与特征工程方法中最成功的特征之一：词缀，结合的模型。词缀特征在早期的命名实体识别（NER）系统中用于 CoNLL 2002 [Tjong Kim Sang (2002，Cucerzan 和 Yarowsky (2002] 和 2003 [Tjong Kim Sang 和 De Meulder (2003] 以及生物医学 NER [Saha 等 (2009] 中，但在神经 NER 系统中尚未使用。他们扩展了 ?) 字符+词模型，以学习词缀嵌入¹⁷¹⁷17 代码：https://github.com/vikas95/Pref_Suff_Span_NN 以及词嵌入和字符 RNN (图 4)。他们考虑了训练语料库中所有的 n-gram 前缀和后缀，并仅选择了那些频率高于阈值 $T$ 的前缀和后缀。他们的词+字符+词缀模型在西班牙语、荷兰语、英语和德语 CoNLL 数据集上的准确率分别达到了 87.26%、87.54%、90.86%、79.01%。?) 还表明，词缀嵌入捕捉到的信息与 RNN 捕捉到的字符信息互补，选择高频（现实的）词缀很重要，并且嵌入词缀比简单扩展其他嵌入以达到类似的超参数数量效果更好。

## 7 讨论

表 1 显示了在 CoNLL 2002 和 2003 数据集上讨论的所有不同类别系统的结果。该表还指示了每个模型是否使用了外部知识，如字典或地名集。表 2 提供了 SemEval 2013 任务 9 [Segura Bedmar 等 (2013] 的 DrugNER 数据集的类似分析。

| 特征工程机器学习系统 | 字典 | SP | DU | EN | GE |
| --- | --- | --- | --- | --- | --- |
| ?) 二元 AdaBoost 分类器 | 是 | 81.39 | 77.05 | - | - |
| ?) - 最大熵 (ME) + 特征 | 是 | 73.66 | 68.08 | - | - |
| ?) 带类别权重的 SVM | 是 | - | - | 88.3 | - |
| ?) CRF | 是 | - | - | 90.90 | - |
| ?) 半监督的最先进方法 | 否 | - | - | 89.31 | 75.27 |
| ?) | 是 | 84.16 | 85.04 | 91.36 | 76.42 |
| 特征推断神经网络词模型 |  |  |  |  |  |
| ?) 普通 NN +SLL / Conv-CRF | 否 | - | - | 81.47 | - |
| ?) Bi-LSTM+CRF | 否 | - | - | 84.26 | - |
| ?) Win-BiLSTM (英语)，FF (德语)（许多特征） | 是 | - | - | 88.91 | 76.12 |
| ?) Conv-CRF (SENNA+地名集) | 是 | - | - | 89.59 | - |
| ?) Bi-LSTM+CRF+ (SENNA+Gazetteer) | 是 | - | - | 90.10 | - |
| 特征推断神经网络字符模型 |  |  |  |  |  |
| ?) – BTS | 否 | 82.95 | 82.84 | 86.50 | 76.22 |
| ?) CharNER | 否 | 82.18 | 79.36 | 84.52 | 70.12 |
| 特征推断神经网络词汇 + 字符模型 |  |  |  |  |  |
| ?) | 是 | 85.77 | 85.19 | 91.26 | - |
| ?) | 是 | - | - | 91.20 | - |
| ?) | 是 | - | - | 91.62 | - |
| ?) | 否 | - | - | 91.21 | - |
| ?) | 否 | 82.21 | - | - | - |
| ?) | 否 | 85.75 | 81.74 | 90.94 | 78.76 |
| ?) | 是 | 85.81 | - | - | - |
| ?) | 否 | - | - | 90.5 | - |
| 特征推断神经网络词汇 + 字符 + 词缀模型 |  |  |  |  |  |
| Re-implementation of ?) (100 Epochs) | 否 | 85.34 | 85.27 | 90.24 | 78.44 |
| ?)(100 Epochs) | 否 | 86.92 | 87.50 | 90.69 | 78.56 |
| ?) (150 Epochs) | 否 | 87.26 | 87.54 | 90.86 | 79.01 |

表 1：四种语言的 NER 系统比较：CoNLL 2002 西班牙语（SP），CoNLL 2002 荷兰语（DU），CoNLL 2003 英语（EN），和 CoNLL 2003 德语（GE）。字典表示该方法是否使用了字典查找。每个类别中的最佳性能以**粗体**突出显示。

|  |  | MedLine (80.10% ) | DrugBank (19.90% ) | 完整数据集 |
| --- | --- | --- | --- | --- |
|  | 字典 | P | R | F1 | P | R | F1 | P | R | F1 |
| 特征工程机器学习系统 |  |  |  |  |  |  |  |  |  |  |
| ?) | 是 | 60.70 | 55.80 | 58.10 | 88.10 | 87.50 | 87.80 | 73.40 | 69.80 | 71.50 |
| ?) (基线) | 否 | - | - | - | - | - | - | 78.41 | 67.78 | 72.71 |
| ?) (MED. emb.) | 否 | - | - | - | - | - | - | 82.70 | 69.68 | 75.63 |
| ?) (最新技术) | 是 | 78.77 | 60.21 | 68.25 | 90.60 | 88.82 | 89.70 | 84.75 | 72.89 | 78.37 |
| NN 词汇模型 |  |  |  |  |  |  |  |  |  |  |
| ?) (放宽性能) | 否 | 52.93 | 52.57 | 52.75 | 87.07 | 83.39 | 85.19 | - | - | - |
| NN 词汇 + 字符模型 |  |  |  |  |  |  |  |  |  |  |
| ?) | 否 | 73.00 | 62.00 | 67.00 | 87.00 | 86.00 | 87.00 | 79.00 | 72.00 | 75.00 |
| NN 词汇 + 字符 + 词缀模型 |  |  |  |  |  |  |  |  |  |  |
| ?) | 否 | 74.00 | 64.00 | 69.00 | 89.00 | 86.00 | 87.00 | 81.00 | 74.00 | 77.00 |

表 2：DrugNER 在 MedLine 和 DrugBank 测试数据上的结果（分别占测试数据的 80.10%和 19.90%）。?) 实验报告没有小数位数，因为它们是在共享任务结束后运行的，官方评估脚本不输出小数位数。

我们从调查中得到的第一个发现是，尽管特征工程系统具有访问领域特定规则、知识、特征和词典的优势，特征推断的神经网络系统仍然优于特征工程系统。例如，西班牙语的最佳特征工程系统 ?)，比最佳特征推断神经网络系统[Lample et al. (2016]低 1.59%，比包含词汇资源的最佳神经网络系统[Bharadwaj et al. (2016]低 1.65%。类似地，德语的最佳特征工程系统 ?)，比最佳特征推断神经网络系统 ?)，低 2.34%。荷兰语和英语的差异较小，但在这两种情况下，最佳特征工程模型都不如最佳神经网络模型。在 DrugNER 中，词+字符神经网络模型在 MedLine 测试数据上优于特征工程系统 8.90%，在整体数据集上优于 3.50%。

我们的下一个发现是，词+字符混合模型通常优于基于词语和基于字符的模型。例如，英语的最佳混合神经网络模型 ?)，比最佳基于词语的模型 ?)，高 0.52%，比最佳基于字符的模型[Kuru et al. (2016]高 5.12%。类似地，德语的最佳混合神经网络模型 ?)，比最佳基于词语的模型 ?)，高 2.64%，比最佳基于字符的模型[Kuru et al. (2016]高 2.54%。在 DrugNER 中，词+字符混合模型在 MedLine 测试数据上比基于词语的模型好 14.25%，在 DrugBank 测试数据上好 1.81%。

我们的最终发现是，通过将过去特征工程模型的关键特性融入现代神经网络架构，仍然可以取得有趣的进展。?）对 ?) 的简单扩展，融入词缀特征，产生了一个非常强大的新模型，在西班牙语、荷兰语和德语中达到了新的最先进水平，并在英语中表现接近最佳模型的 1%以内。

## 8 结论

我们对命名实体识别模型的调查，包括经典的特征工程机器学习模型和现代的特征推断神经网络模型，带来了几个重要的见解。神经网络模型通常优于特征工程模型，字符+词语混合神经网络通常优于其他表示选择，进一步的改进可以通过将过去的见解应用于当前的神经网络模型来实现，正如我们提出的基于词缀的字符+词语混合模型的最先进性能所示。

## 参考文献

+   [Agerri and Rigau (2016] Rodrigo Agerri 和 German Rigau. 2016. 具有浅层半监督特征的鲁棒多语言命名实体识别。人工智能，238:63–82。

+   [Alfonseca 和 Manandhar (2002] Enrique Alfonseca 和 Suresh Manandhar. 2002. 一种用于通用命名实体识别和自动化概念发现的无监督方法。发表于第 1 届国际 WordNet 会议论文集，印度迈索尔，第 34–43 页。

+   [Ando 和 Zhang (2005a] Rie Kubota Ando 和 Tong Zhang. 2005a. 从多任务和未标记数据中学习预测结构的框架。机器学习研究杂志，6（11 月）：1817–1853。

+   [Ando 和 Zhang (2005b] Rie Kubota Ando 和 Tong Zhang. 2005b. 从多任务和未标记数据中学习预测结构的框架。机器学习研究杂志，6（11 月）：1817–1853。

+   [Baldwin 等 (2015] Timothy Baldwin、Marie-Catherine de Marneffe、Bo Han、Young-Bum Kim、Alan Ritter 和 Wei Xu. 2015. 2015 年关于嘈杂用户生成文本的研讨会共享任务：Twitter 词汇规范化和命名实体识别。发表于嘈杂用户生成文本研讨会论文集，第 126–135 页。

+   [Benikova 等 (2014] Darina Benikova、Chris Biemann 和 Marc Reznicek. 2014. 德语的 Nosta-d 命名实体注释：指南和数据集。发表于 LREC，第 2524–2531 页。

+   [Bharadwaj 等 (2016] Akash Bharadwaj、David R. Mortensen、Chris Dyer 和 Carlos de Juan Carbonell. 2016. 低资源转移设置下的语音意识神经模型用于命名实体识别。发表于 EMNLP。

+   [Bikel 等 (1997] Daniel M Bikel、Scott Miller、Richard Schwartz 和 Ralph Weischedel. 1997. Nymble：一种高性能学习命名发现器。发表于第五届应用自然语言处理会议论文集，第 194–201 页。计算语言学协会。

+   [Bossy 等 (2013] Robert Bossy、Wiktoria Golik、Zorana Ratkovic、Philippe Bessières 和 Claire Nédellec. 2013. BioNLP 共享任务 2013–细菌生态任务概述。发表于 BioNLP 共享任务 2013 研讨会论文集，第 161–169 页。

+   [Carreras 等 (2002] Xavier Carreras、Lluís Màrquez 和 Lluís Padró. 2002. 使用 adaboost 进行命名实体提取，发表于第 6 届自然语言学习会议论文集。8 月，31:1–4。

+   [Chalapathy 等 (2016] Raghavendra Chalapathy、Ehsan Zare Borzeshi 和 Massimo Piccardi. 2016. 对药物名称识别的递归神经架构的研究。arXiv 预印本 arXiv:1609.07585。

+   [Chinchor 和 Robinson (1997] Nancy Chinchor 和 Patricia Robinson. 1997. Muc-7 命名实体任务定义。发表于第 7 届信息理解会议论文集，第 29 卷。

+   [Chiu 和 Nichols (2015] Jason PC Chiu 和 Eric Nichols. 2015. 使用双向 LSTM-CNNs 的命名实体识别。arXiv 预印本 arXiv:1511.08308。

+   [Collins 和 Singer (1999] Michael Collins 和 Yoram Singer. 1999. 用于命名实体分类的无监督模型。发表于 1999 年联合 SIGDAT 会议上的自然语言处理和非常大语料库的经验方法。

+   [Collobert 和 Weston (2008] Ronan Collobert 和 Jason Weston. 2008. 自然语言处理的统一架构：具有多任务学习的深度神经网络。在第 25 届国际机器学习大会论文集，第 160–167 页。ACM。

+   [Collobert 等 (2011] Ronan Collobert, Jason Weston, Léon Bottou, Michael Karlen, Koray Kavukcuoglu 和 Pavel Kuksa. 2011. 从零开始的自然语言处理。机器学习研究期刊, 12(8):2493–2537。

+   [Cucerzan 和 Yarowsky (2002] Silviu Cucerzan 和 David Yarowsky. 2002. 使用内部和上下文证据的统一模型进行语言无关的命名实体识别。在第 6 届自然语言学习会议论文集-第 20 卷，第 1–4 页。计算语言学协会。

+   [Delėger 等 (2016] Louise Delėger, Robert Bossy, Estelle Chaix, Mouhamadou Ba, Arnaud Ferrė, Philippe Bessieres 和 Claire Nėdellec. 2016. 2016 年 BioNLP 共享任务的细菌生境任务概述。在第 4 届 BioNLP 共享任务研讨会论文集，第 12–22 页。

+   [Dernoncourt 等 (2017] Franck Dernoncourt, Ji Young Lee 和 Peter Szolovits. 2017. Neuroner：基于神经网络的易用命名实体识别程序。arXiv 预印本 arXiv:1705.05487。

+   [Dong 等 (2016] Chuanhai Dong, Jiajun Zhang, Chengqing Zong, Masanori Hattori 和 Hui Di. 2016. 基于字符的 lstm-crf 和部首级特征用于中文命名实体识别。在《自然语言理解与智能应用》，第 239–250 页。Springer。

+   [Eltyeb 和 Salim (2014] Safaa Eltyeb 和 Naomie Salim. 2014. 化学命名实体识别：方法和应用综述。化学信息学杂志, 6(1):17。

+   [Etaiwi 等 (2017] Wael Etaiwi, Arafat Awajan 和 Dima Suleiman. 2017. 统计阿拉伯语命名实体识别方法：综述。Procedia 计算机科学, 113:57–64。

+   [Etzioni 等 (2005] Oren Etzioni, Michael Cafarella, Doug Downey, Ana-Maria Popescu, Tal Shaked, Stephen Soderland, Daniel S Weld 和 Alexander Yates. 2005. 从网络中无监督的命名实体提取：实验研究。人工智能, 165(1):91–134。

+   [Forney (1973] G David Forney. 1973. 维特比算法。IEEE 会议录, 61(3):268–278。

+   [Gillick 等 (2015] Dan Gillick, Cliff Brunk, Oriol Vinyals 和 Amarnag Subramanya. 2015. 从字节开始的多语言处理。arXiv 预印本 arXiv:1512.00103。

+   [Grishman 和 Sundheim (1996] Ralph Grishman 和 Beth Sundheim. 1996. 消息理解会议-6：简要历史。在 COLING 1996 第 1 卷：第 16 届国际计算语言学大会，第 1 卷。

+   [Habibi 等 (2017] Maryam Habibi, Leon Weber, Mariana Neves, David Luis Wiegandt 和 Ulf Leser. 2017. 使用词嵌入的深度学习改进生物医学命名实体识别。生物信息学, 33(14):i37–i48。

+   [Hettne 等 (2009] Kristina M Hettne, Rob H Stierum, Martijn J Schuemie, Peter JM Hendriksen, Bob JA Schijvenaars, Erik M van Mulligen, Jos Kleinjans, 和 Jan A Kors. 2009. 用于识别自由文本中的小分子和药物的词典. 生物信息学, 25(22):2983–2991.

+   [Hirschman 等 (2005] Lynette Hirschman, Alexander Yeh, Christian Blaschke, 和 Alfonso Valencia. 2005. BioCreative 概述: 生物学信息提取的关键评估.

+   [Huang 等 (2015] Zhiheng Huang, Wei Xu, 和 Kai Yu. 2015. 用于序列标记的双向 LSTM-CRF 模型. arXiv 预印本 arXiv:1508.01991.

+   [Kim 等 (2004] Jin-Dong Kim, Tomoko Ohta, Yoshimasa Tsuruoka, Yuka Tateisi, 和 Nigel Collier. 2004. 介绍 jnlpba 的生物实体识别任务. 在国际联合研讨会论文集，生物医学和其应用中的自然语言处理, 页码 70–75. 计算语言学协会.

+   [Kim 等 (2016] Yoon Kim, Yacine Jernite, David Sontag, 和 Alexander M Rush. 2016. 面向字符的神经语言模型. 在 AAAI, 页码 2741–2749.

+   [Knox 等 (2010] Craig Knox, Vivian Law, Timothy Jewison, Philip Liu, Son Ly, Alex Frolkis, Allison Pon, Kelly Banco, Christine Mak, Vanessa Neveu 等. 2010. Drugbank 3.0: 一项关于药物的‘omics’研究的综合资源. 核酸研究, 39(suppl_1):D1035–D1041.

+   [Krallinger 等 (2015] Martin Krallinger, Obdulia Rabal, Florian Leitner, Miguel Vazquez, David Salgado, Zhiyong Lu, Robert Leaman, Yanan Lu, Donghong Ji, Daniel M Lowe 等. 2015. ChemDNER 化学品和药物语料库及其注释原则. 化学信息学期刊, 7(S1):S2.

+   [Kuru 等 (2016] Onur Kuru, Ozan Arkan Can, 和 Deniz Yuret. 2016. Charner: 字符级命名实体识别. 在 COLING 2016 论文集, 第 26 届国际计算语言学大会: 技术论文, 页码 911–921.

+   [Lample 等 (2016] Guillaume Lample, Miguel Ballesteros, Sandeep Subramanian, Kazuya Kawakami, 和 Chris Dyer. 2016. 用于命名实体识别的神经架构. arXiv 预印本 arXiv:1603.01360.

+   [Leaman 和 Gonzalez (2008] Robert Leaman 和 Graciela Gonzalez. 2008. Banner: 一项关于生物医学命名实体识别进展的可执行调查。在 Biocomputing 2008, 页码 652–663\. World Scientific.

+   [Lei 等 (2013] Jianbo Lei, Buzhou Tang, Xueqin Lu, Kaihua Gao, Min Jiang, 和 Hua Xu. 2013. 对中文临床文本中命名实体识别的综合研究. 美国医学信息学协会期刊, 21(5):808–814.

+   [Li 等 (2005] Yaoyong Li, Kalina Bontcheva, 和 Hamish Cunningham. 2005. 基于 SVM 的信息提取学习系统. 在机器学习中的确定性和统计方法, 页码 319–339\. Springer.

+   [Li 等 (2015] Yanran Li, Wenjie Li, Fei Sun, 和 Sujian Li. 2015. 组件增强的中文字符嵌入. arXiv 预印本 arXiv:1508.06669.

+   [Limsopatham 和 Collier (2016)] Nut Limsopatham 和 Nigel Henry Collier. 2016. 用于 Twitter 消息中命名实体识别的双向 LSTM。

+   [Ling 等 (2015)] Wang Ling, Tiago Luís, Luís Marujo, Ramón Fernandez Astudillo, Silvio Amir, Chris Dyer, Alan W Black 和 Isabel Trancoso. 2015. 在形式中寻找功能：开放词汇表单词表示的组合字符模型。arXiv 预印本 arXiv:1508.02096。

+   [Liu 等 (2015)] Shengyu Liu, Buzhou Tang, Qingcai Chen 和 Xiaolong Wang. 2015. 语义特征对基于机器学习的药物名称识别系统的影响：词嵌入与手工构建的词典。《信息》，6(4)：848–865。

+   [Luo (2015)] 2015. 联合命名实体识别与歧义消解，9 月。

+   [Ma 和 Hovy (2016)] Xuezhe Ma 和 Eduard Hovy. 2016. 通过双向 LSTM-CNNs-CRF 的端到端序列标注。arXiv 预印本 arXiv:1603.01354。

+   [Malouf (2002)] Robert Malouf. 2002. 语言无关的命名实体识别的马尔可夫模型，第六届自然语言学习会议论文集。8 月，31：1–4。

+   [Marcus 等 (1993)] Mitchell P Marcus, Mary Ann Marcinkiewicz 和 Beatrice Santorini. 1993. 构建大型注释语料库的英语：宾州树库。《计算语言学》，19(2)：313–330。

+   [Mikolov 等 (2013)] Tomas Mikolov, Kai Chen, Greg Corrado 和 Jeffrey Dean. 2013. 高效的词向量空间表示估计。arXiv 预印本 arXiv:1301.3781。

+   [Misawa 等 (2017)] Shotaro Misawa, Motoki Taniguchi, Yasuhide Miura 和 Tomoko Ohkuma. 2017. 基于字符的双向 LSTM-CRF，结合单词和字符用于日语命名实体识别。发表于《第一次子词和字符级模型在 NLP 中的研讨会》，页码 97–102。

+   [Nadeau 和 Sekine (2007)] David Nadeau 和 Satoshi Sekine. 2007. 命名实体识别与分类的调查。《语言学调查》，30(1)：3–26。

+   [Nadeau 等 (2006)] David Nadeau, Peter D Turney 和 Stan Matwin. 2006. 无监督命名实体识别：生成地名辞典和解决歧义。发表于《加拿大计算智能学会会议》，页码 266–277。Springer。

+   [Nguyen 等 (2016)] TS Nguyen, LM Nguyen 和 XC Tran. 2016. 在 VLSP 2016 评估活动中的越南语命名实体识别。发表于《第四届国际越南语语言和语音处理研讨会》。

+   [Ohta 等 (2002)] Tomoko Ohta, Yuka Tateisi 和 Jin-Dong Kim. 2002. GENIA 语料库：分子生物学领域的注释研究摘要语料库。发表于《第二届国际人类语言技术研究会议》，页码 82–86。Morgan Kaufmann Publishers Inc.

+   [Passos 等 (2014)] Alexandre Passos, Vineet Kumar 和 Andrew McCallum. 2014. 词典增强的短语嵌入用于命名实体解析。arXiv 预印本 arXiv:1404.5367。

+   [Patil 等人 (2016)] Nita Patil、Ajay S Patil 和 BV Pawar。2016。关于印度和外国语言的命名实体识别系统的调查。《国际计算机应用期刊》，134(16)。

+   [Pham 和 Le-Hong (2017)] Thai-Hoang Pham 和 Phuong Le-Hong。2017。用于越南语命名实体识别的端到端递归神经网络模型：词级别与字符级别。arXiv 预印本 arXiv:1705.04044。

+   [Piskorski 等人 (2017)] Jakub Piskorski、Lidia Pivovarova、Jan Šnajder、Josef Steinberger、Roman Yangarber 等。2017。首届跨语言挑战：斯拉夫语言中的命名实体识别、规范化和匹配。在第六届波罗-斯拉夫自然语言处理研讨会论文集中。计算语言学协会。

+   [Plank 等人 (2016)] Barbara Plank、Anders Søgaard 和 Yoav Goldberg。2016。利用双向长短期记忆模型和辅助损失进行多语言词性标注。arXiv 预印本 arXiv:1604.05529。

+   [Pradhan 等人 (2013)] Sameer Pradhan、Alessandro Moschitti、Nianwen Xue、Hwee Tou Ng、Anders Björkelund、Olga Uryupina、Yuchen Zhang 和 Zhi Zhong。2013。使用 Ontonotes 实现稳健的语言分析。在第十七届计算自然语言学习会议论文集中，页码 143–152。

+   [Rabiner 和 Juang (1986)] Lawrence Rabiner 和 B Juang。1986。隐马尔可夫模型简介。IEEE ASSP 杂志，3(1)：4–16。

+   [Rajeev Sangal 和 Singh (2008)] Dipti Misra Sharma Rajeev Sangal 和 Anil Kumar Singh，编辑。2008。南亚和东南亚语言命名实体识别的 IJCNLP-08 研讨会论文集。亚洲自然语言处理联盟，印度海得拉巴，1 月。

+   [Rocktäschel 等人 (2013)] Tim Rocktäschel、Torsten Huber、Michael Weidlich 和 Ulf Leser。2013。Wbi-ner：领域特定特征对药物提及识别和分类性能的影响。在 SemEval@ NAACL-HLT，页码 356–363。

+   [Saha 等人 (2009)] Sujan Kumar Saha、Sudeshna Sarkar 和 Pabitra Mitra。2009。基于最大熵的生物医学命名实体识别的特征选择技术。《生物医学信息学杂志》，42(5)：905 – 911。生物医学自然语言处理。

+   [Santos 和 Cardoso (2007)] Diana Santos 和 Nuno Cardoso。2007。葡萄牙语中提到的实体识别：文档和《哈伦》第一次评估联合会议记录。

+   [Santos 和 Guimaraes (2015)] Cicero Nogueira dos Santos 和 Victor Guimaraes。2015。通过神经字符嵌入提升命名实体识别。arXiv 预印本 arXiv:1505.05008。

+   [Schapire (2013)] Robert E Schapire。2013。解释 AdaBoost。在《经验推断》中，页码 37–52。施普林格。

+   [Segura Bedmar 等人 (2013)] Isabel Segura Bedmar、Paloma Martínez 和 María Herrero Zazo。2013。Semeval-2013 任务 9：从生物医学文本中提取药物-药物相互作用 (ddiextraction 2013)。计算语言学协会。

+   [Shaalan (2014] Khaled Shaalan. 2014. 阿拉伯语命名实体识别和分类的综述。计算语言学，第 40 卷第 2 期，第 469–510 页。

+   [Sharnagat (2014] Rahul Sharnagat. 2014. 命名实体识别：文献综述。印度语言技术中心。

+   [Strassel et al. (2003] Stephanie Strassel、Alexis Mitchell 和 Shudong Huang. 2003. 实体提取的多语言资源。发表于 ACL 2003 多语言和混合语言命名实体识别研讨会论文集-第 15 卷，第 49–56 页。计算语言学协会。

+   [Takeuchi and Collier (2002] Koichi Takeuchi 和 Nigel Collier. 2002. 在扩展的命名实体识别中使用支持向量机。发表于第六届自然语言学习会议论文集-第 20 卷，第 1–7 页。计算语言学协会。

+   [Tjong Kim Sang and De Meulder (2003] Erik F Tjong Kim Sang 和 Fien De Meulder. 2003. CONLL-2003 共享任务介绍：语言无关的命名实体识别。发表于第七届自然语言学习会议 HLT-NAACL 2003 论文集-第 4 卷，第 142–147 页。计算语言学协会。

+   [Tjong Kim Sang (2002] Erik F Tjong Kim Sang. 2002. CONLL-2002 共享任务介绍：语言无关的命名实体识别，发表于第六届自然语言学习会议论文集。8 月 31 日，第 1–4 页。

+   [Uzuner et al. (2007] Özlem Uzuner、Yuan Luo 和 Peter Szolovits. 2007. 评估自动去标识化的最先进技术。美国医学信息学学会期刊，第 14 卷第 5 期，第 550–563 页。

+   [Uzuner et al. (2011] Özlem Uzuner、Brett R South、Shuying Shen 和 Scott L DuVall. 2011. 2010 i2b2/va 挑战赛：临床文本中的概念、主张和关系。美国医学信息学学会期刊，第 18 卷第 5 期，第 552–556 页。

+   [Xu et al. (2017] Kai Xu、Zhanfan Zhou、Tianyong Hao 和 Wenyin Liu. 2017. 基于双向 LSTM 和条件随机场的医学命名实体识别方法。发表于国际先进智能系统与信息学会议，第 355–365 页。Springer。

+   [Yadav et al. (2018] Vikas Yadav、Rebecca Sharp 和 Steven Bethard. 2018. 深度词缀特征改善神经命名实体识别器。发表于第七届词汇与计算语义学联合会议论文集，第 167–172 页。

+   [Yan et al. (2016] Shao Yan、Christian Hardmeier 和 Joakim Nivre. 2016. 使用混合神经网络的多语言命名实体识别。发表于第六届瑞典语言技术会议（SLTC）。

+   [Yang et al. (2016] Zhilin Yang、Ruslan Salakhutdinov 和 William Cohen. 2016. 从零开始的多任务跨语言序列标注。arXiv 预印本 arXiv:1603.06270。

+   [Yang et al. (2017] Zhilin Yang、Ruslan Salakhutdinov 和 William W Cohen. 2017. 使用层次递归网络进行序列标注的迁移学习。arXiv 预印本 arXiv:1703.06345。

+   [尹等 (2016)](https://example.org) Rongchao Yin, Quan Wang, Peng Li, Rui Li, 和 Bin Wang. 2016. 多粒度中文词嵌入. 见于 2016 年自然语言处理实证方法会议论文集，第 981–986 页。

+   [张和 Elhadad (2013)](https://example.org) Shaodian Zhang 和 Noémie Elhadad. 2013. 无监督生物医学命名实体识别：临床和生物文本的实验. 《生物医学信息学杂志》，46(6):1088–1098。

+   [周和苏 (2002)](https://example.org) GuoDong Zhou 和 Jian Su. 2002. 使用基于 HMM 的块标注器进行命名实体识别. 见于第 40 届计算语言学协会年会论文集，第 473–480 页。计算语言学协会。
