<!--yml

分类: 未分类

日期: 2024-09-06 19:34:34

-->

# [2402.05617] 基于深度学习的计算工作市场分析：关于从职位发布中提取和分类技能的调查

> 来源：[`ar5iv.labs.arxiv.org/html/2402.05617`](https://ar5iv.labs.arxiv.org/html/2402.05617)

# 基于深度学习的计算工作市场分析：

关于从职位发布中提取和分类技能的调查

Elena Senger^(1,3), Mike Zhang², Rob van der Goot², Barbara Plank^(1,2)

¹MaiNLP, 信息与语言处理中心, 慕尼黑大学, 德国

²哥本哈根 IT 大学计算机科学系, 丹麦

³弗劳恩霍夫国际管理与知识经济中心 IMW, 德国

elena.senger@cis.lmu.de, {mikz, robv}@itu.dk, b.plank@lmu.de

###### 摘要

近年来，自然语言处理（NLP）取得了显著进展，使得*计算工作市场分析*领域得以快速发展。这个应用领域的核心任务是*从职位发布中提取和分类技能*。由于其快速增长和跨学科性质，目前尚无对这一新兴领域的全面评估。本次调查旨在通过提供关于 NLP 驱动的技能提取和分类的深度学习方法、数据集和术语的全面概述来填补这一空白。我们对公开可用数据集的全面目录弥补了有关数据集创建和特征的整合信息缺乏的问题。最后，对术语的关注解决了当前在硬技能和软技能等重要概念，以及与技能提取和分类相关术语的定义不一致的问题。

基于深度学习的计算工作市场分析：

关于从职位发布中提取和分类技能的调查

Elena Senger^(1,3), Mike Zhang², Rob van der Goot², Barbara Plank^(1,2) ¹MaiNLP, 信息与语言处理中心, 慕尼黑大学, 德国 ²哥本哈根 IT 大学计算机科学系, 丹麦 ³弗劳恩霍夫国际管理与知识经济中心 IMW, 德国 elena.senger@cis.lmu.de, {mikz, robv}@itu.dk, b.plank@lmu.de

## 1 引言

技能提取和分类最近受到越来越多的关注（Zhang et al., 2023; Clavié 和 Soulié, 2023），这在大量的出版物中得到了体现，主要是由于自然语言处理（NLP）技术的进步。例如，通过大语言模型（LLMs），可以通过使用合成训练数据来处理低资源任务的技能提取（Clavié 和 Soulié, 2023; Decorte et al., 2023）。关于技能提取的调查正在出现（Khaouja et al., 2021a; Papoutsoglou et al., 2019），尽管如此，从 NLP 的角度出发，仍然缺乏全面的概述——这是我们希望在本次调查中填补的空白。我们的贡献包括：

+   •

    首先，我们旨在解决该领域中标准术语缺乏的问题，为硬技能和软技能等术语以及与技能提取和分类相关的短语带来清晰度。

+   •

    此外，本次调查首次检查了各种公开可访问的数据集，并揭示了它们的创建方法。

+   •

    与以往的调查相比，我们采用了以 NLP 为中心的重点，深入探讨了神经方法在技能提取和分类方面的最新进展。

虽然已有先前的调查存在，但它们通常关注于*技能计数*和*主题建模*方法来提取技能。技能计数是通过手动操作或将 n-grams 与技能库匹配来进行的。主题建模是一种无监督方法，利用词分布来识别文档中的潜在主题。由于主要基于统计，并且缺乏定义的技能范围或标签，主题建模以及技能计数方法在本次调查中未被涵盖。有关技能计数的更多细节，请参阅 Khaouja 等人 (2021a) 和 Ternikov (2022)，有关主题建模，请参考 Khaouja 等人 (2021a)、Ternikov (2022) 和 Ao 等人 (2023)。

##### 研究方法论

对于我们的搜索策略，我们使用了多个学术数据库，包括 ACL Anthology、Google Scholar、arXiv、IEEE、ACM、Science Direct 和 Springer Link。主要搜索词是“skill extraction”和“job”。为了进一步优化搜索，我们在 Google Scholar 和 Science Direct 数据库中添加了“deep learning”、“machine learning”或“natural language processing”等术语。这使我们纳入了 26 篇关于从职位发布（JPs）中提取神经技能的文献，这些文献均在 2023 年 11 月之前发表。

## 2 其他调查

以往的调查为我们的调查提供了基础。值得注意的贡献包括来自社会科学领域的研究，特别是 Napierala 和 Kvetan (2023) 在《政策计算社会科学手册》（第十三章）中的工作。它从社会科学的角度关注动态世界中的技能变化。此外，Papoutsoglou 等人 (2019) 关注于软件工程劳动力市场的研究。除了 JPs，他们还研究了其他来源，如社交网络或问答网站。最后，Khaouja 等人 (2021a) 关于从 JPs 中识别技能的调查最接近本次调查。它综述了使用技能计数、主题建模、技能嵌入和其他基于机器学习的方法的论文。在本次调查中，我们避免了手动和主题建模方法，深入探讨了最近的提取方法和基于深度学习的创新。

## 3 技能相关术语

术语技能提取、识别（Li et al., 2023）、检测（Beauchemin et al., 2022）、标准化（Li et al., 2023）和分类使用方式不同，有时可以互换，描述相同或不同的任务。我们提供以下定义（参见附录中表 3 中的示例）：

+   •

    技能提取（$E$）：作为检索技能相关信息的通用（父类）类别。技能提取$E:\text{JP}\rightarrow(S)$，其中$E$将职位发布（JP）映射到一组技能$S$。

+   •

    技能识别/检测（$I$）：指在没有任何预定义标签的情况下提取技能的过程。它可以表示为$I:\text{JP}\rightarrow S$，其中技能，特别是技能跨度，从 JPs 中提取。它也可以形式化为一个分类问题，即$I:\text{Span}\rightarrow\{0,1\}$，以确定给定的 JP 跨度是否表示技能（1）或不表示技能（0）。

+   •

    粗标签技能提取（$E_{C}$）：指识别技能跨度的更广泛类别。它被形式化为$E_{C}:\text{JP}\rightarrow\{SC_{1},SC_{2},\dots,SC_{n}\}$，其中每个$SC_{i}$代表一个具有粗略标签的技能跨度。

+   •

    技能标准化（$Std$）：作为技能术语的规范化过程，形式化为$Std:S\rightarrow S^{\prime}$，将初始技能集$S$映射到标准化的技能集$S^{\prime}$。

+   •

    直接技能分类（$C_{D}$）：作为将技能映射到预定义技能库以分配细粒度标签的过程。这个过程可以形式化为$C_{D}:S\rightarrow L$，其中$C_{D}$将一组已经提取的技能$S$映射到一组细粒度标签$L$。

+   •

    技能分类与提取（$C_{E}$）：作为将 JPs 映射到预定义技能库以分配细粒度标签的过程。这个过程可以形式化为$C_{E}:JP\rightarrow L$，其中$C_{E}$将一组已经提取的技能$S$整个 JP 或原始 JP 片段映射到一组细粒度标签$L$。

根据这些定义，技能提取步骤可以在不同的粒度级别上发生（输入的粒度）。一些工作在每个 JP（$E_{JP}$，整体文档）、每个句子（$E_{sentence}$）或每个 n-gram（$E_{n-gram}$）上提取技能。技能跨度（$E_{span}$）是一个连续的 n-gram 序列，捕捉一个技能。

技能库（$B$）是一个包含技能实体和术语的知识库。分类学是一个分层结构的技能库，而本体论通过概念之间的关系提供结构（Khaouja et al., 2021a）。一些工作使用“技能词典”一词来指代技能库，这通常指的是一个非结构化的技能库或技能列表（Gugnani and Misra, 2020; Yao et al., 2022）。两个由领域专家创建的流行的公开技能库，且经常使用和维护的是欧洲技能、能力、资格和职业（ESCO；le Vrang et al., 2014）分类学和美国职业信息网络（O*NET；Council et al., 2010）。更多技能库的例子请参考 Khaouja et al. (2021a)。

## 4 什么是技能？关于技能定义

理解*技能*的概念在技能提取领域至关重要。在这一部分，我们调查了各种出版物和机构对技能的多种定义，旨在识别不同来源之间的共性和差异，这对于在这个新兴领域建立共同基础非常重要。

*技能*的概念可以被视为一个广泛的概念（Green et al., 2022; Wild et al., 2021; Fang et al., 2023），也可以分为子类别，分割的可能性有多种。在最新版本的 ESCO 分类学中，“技能支柱”被分为四个类别：“横向技能”、“技能”、“知识”和“语言技能与知识”。¹¹1 [`esco.ec.europa.eu/en/classification/skill_main`](https://esco.ec.europa.eu/en/classification/skill_main) O*NET 结构为六个领域（Council et al., 2010），最适合从 JP 中提取技能的领域是“工人要求”。该领域包括四个子类别：基本技能、跨职能技能、知识和教育。²²2 [`www.onetcenter.org/content.html`](https://www.onetcenter.org/content.html) 但在本次调查中考虑的定义技能的出版物主要区分硬技能和软技能（Tamburri et al., 2020; Beauchemin et al., 2022; Sayfullina et al., 2018），因此本次调查也使用这一划分。

##### 硬技能

Tamburri 等人（2020）将硬技能定义为与组织职能、流程和角色相关的专业能力、活动或知识，这些都是成功完成特定任务所必需的。这个定义强调了硬技能在专业环境中的实用性和功能性。与此一致，Beauchemin 等人（2022）的研究将硬技能视为面向任务的技术能力，借鉴了 Lyu 和 Liu（2021）的定义，将其定义为执行特定任务的正式技术能力。此外，Gugnani 和 Misra（2020）通过引入技术术语来识别技能，扩展了这一观点，因此将知识整合为硬技能的一个基本组成部分。

通过将知识作为硬技能的一个组成部分，硬技能的定义与 O*NET 和 ESCO 的知识类别可以结合起来。O*NET 对硬技能的定义表示，它们是使学习或知识获取成为可能的能力，并与其对知识的定义“组织原则和事实的集合，适用于一般领域”相结合。³³3 见脚注 2。这个全面的定义不仅强调了技术熟练度，还强调了适应和应用知识的能力。同样，ESCO 参考了欧洲资格框架，将技能定义为“应用知识和使用技能以完成任务和解决问题的能力”，同时将知识定义为“通过学习吸收信息的结果”。⁴⁴4[`esco.ec.europa.eu/en/about-esco/escopedia/escopedia/knowledge`](https://esco.ec.europa.eu/en/about-esco/escopedia/escopedia/knowledge) 和 [`esco.ec.europa.eu/en/about-esco/escopedia/escopedia/skill`](https://esco.ec.europa.eu/en/about-esco/escopedia/escopedia/skill)

总之，我们将硬技能定义为各种专业能力，从可测量的技术技能到更一般的学习和有效应用知识的能力。它们是可量化和可教授的能力，主要是技术性的，但与适应和在不同专业场景中应用它们的能力密切相关。

##### 软技能

Sayfullina 等人 (2018) 参考 Collins 词典（HarperCollins Publishers，2023），将软技能视为与生俱来的非技术性特质，这些特质在就业中受到高度重视，与依赖获得的知识有所不同。在更为社会化的背景下，Tamburri 等人 (2020) 将软技能定义为涵盖个人、情感、社会或智力方面的能力，进一步被称为行为技能或能力。与此观点相呼应，Beauchemin 等人 (2022) 从 Lyu 和 Liu (2021) 的研究中得出结论，将软技能识别为一系列个人属性和行为，这些技能对于有效的工作场所互动、协作和适应性至关重要。  

除此之外，ESCO 将软技能描述为*横向技能*，突显了其在各类职业和领域中的广泛适用性及其在个人成长中的基础性作用。[`esco.ec.europa.eu/en/about-esco/escopedia/escopedia/transversal-knowledge-skills-and-competences`](https://esco.ec.europa.eu/en/about-esco/escopedia/escopedia/transversal-knowledge-skills-and-competences) 同样，O*NET 将这些技能归类为跨职能技能，定义为提升各种工作中常见活动表现的能力，包括社会技能和复杂问题解决技能。[6See footnote 2.] 两个来源都强调了软技能的普遍相关性。

这些先前的定义促成了我们的汇聚定义，即软技能涵盖了广泛的个人、社会和智力能力，这些能力对于成功的人际交往和职业环境中的个人发展是不可或缺的。  

## **技能定义的操作化**  

在本节中，我们探讨了在技能提取和分类研究中操作化技能定义的各种方法。  

##### **使用技能库**  

利用给定的技能库，技能库的作者提供了概念的预定义定义。许多研究使用了既定的技能库，如 ESCO 分类法（Zhang 等人，2023, 2022b; Clavié 和 Soulié，2023; Decorte 等人，2023, 2022）或 O*NET（Gugnani 和 Misra，2020）。然而，这些研究是否使用了所有子类别或仅使用特定子类别常常不明确（Li 等人，2023; Decorte 等人，2022; Gugnani 和 Misra，2020）。一些论文明确提到使用了所有子类（Zhang 等人，2022b, a; Gnehm 等人，2022a），而其他情况下可以从使用的技能范围数量中推断出来（Clavié 和 Soulié，2023; Decorte 等人，2023）。然而，需要注意的是，ESCO 定义的解释会根据 ESCO 版本和作者的视角有所不同。Zhang 等人（2022a, b）使用了 ESCO 1.0 版本，其软技能类别与第四部分讨论的不同，并实现了两个标签：“知识”与 ESCO 的“Knowledge”类别对齐，“技能”作为硬技能和软技能的融合。相比之下，Colombo 等人（2019）使用相同的 ESCO 版本，但将软技能与硬技能分开处理。大多数出版物将所有子类别作为技能使用而不做区分（Clavié 和 Soulié，2023; Gnehm 等人，2022a; Decorte 等人，2023）。

除此之外，还有其他技能库，例如 Botov 等人（2019）中的俄罗斯职业标准或 Cao 和 Zhang（2021）；Cao 等人（2021）使用的中国职业分类大典。此外，还存在非官方的技能库，如 Sayfullina 等人（2018）中的 1K 软技能列表或 LinkedIn 的内部分类法（Shi 等人，2020）。一般来说，为了保证透明性和可重复性，说明使用了技能库的哪个细化标签子集 $L$ 和哪个技能库版本是很有帮助的。

##### 利用自动化工具

一些研究利用自动化工具如 AutoPhrase (Shang et al., 2018) 或 Microsoft Azure Analytics Service 进行初步技能术语检测，然后进行人工验证和改进 (Yao et al., 2022; Kortum et al., 2022)。此外，Vermeer et al. (2022) 使用自动化工具提取部分训练数据，而其他数据则来自技能库。⁷⁷7[`www.textkernel.com/de/`](https://www.textkernel.com/de/) 最后，Gugnani 和 Misra (2020) 使用 IBM 工具进行技能识别，这属于更大技能识别框架的一部分。⁸⁸8[`www.ibm.com/products/natural-language-understanding`](https://www.ibm.com/products/natural-language-understanding) 虽然一些早期工作未进行人工验证 (Gugnani 和 Misra, 2020; Vermeer et al., 2022)，但我们建议进行人工验证，以减少工具对数据的自动化偏差影响。

##### 通过标注定义

领域专家在标注数据中发挥着关键作用，因此影响技能定义的实施方式 (Shi et al., 2020; Tamburri et al., 2020; Beauchemin et al., 2022)。Tamburri et al. (2020) 还提供了一个技能定义的编码书，以解决歧义问题。Shi et al. (2020) 使用了由招聘专家识别的下一步技能和成功申请者中常见的技能作为训练数据。Bhola et al. (2020) 通过使用公司提交的职位发布标签，将这些公司视为领域专家 (参见第六部分)。除了领域专家外，众包工人和编写指南的人通常决定哪些术语是技能。一些研究没有提及谁标注了数据 (Wild et al., 2021; Cao 和 Zhang, 2021; Botov et al., 2019)。我们建议明确标注过程和指南，使其公开以便透明化和重用/标准化，并尽可能使用领域专家进行准确标注。

## 6 数据

在这一部分，我们提供了对公开可用数据集的全面描述，概述见表 1。

| 发表 | 方法 | 粒度 | 技能类型 | 使用案例 | 大小 | \faBook |
| --- | --- | --- | --- | --- | --- | --- |
| (Sayfullina et al., 2018) | 众包 | 范围级 | 软 | $I$ | 7411 范围 | \faRemove |
| (Green et al., 2022) | 众包 | 范围级 | 硬 + 软 | $E_{C}$ | 10,606 范围 | \faCheck |
| (Beauchemin 等，2022) | 专家 | 范围级别 | 软技能 | $E_{C}$ | 47 JPs - 932 范围 | \faRemove |
| (Zhang 等，2022a) | 专家 | 范围级别 | 硬技能 + 软技能 | $E_{C}$ | 265 JP - 9,633 范围 | \faCheck |
| (Zhang 等，2022b) | 专家 | 范围级别 | 硬技能 + 软技能 | $E_{C}$+$C_{D}$ | 60 JP - 920 范围 | \faCheck |
| (Decorte 等，2022) | 手动 | 范围级别 | 硬技能 + 软技能 | $I$+$C_{D}$ | 1,618 范围 | \faCheck |
| (Gnehm 等，2022b) | 专家 | 范围级别 | 硬技能 + 软技能 | $E_{C}$+$C_{D}$ | 10,995 范围 | \faRemove |
| (Bhola 等，2020) | 技能清单 | 文档级别 | 未知 | $C_{E}$ | 20,298 JP | \faRemove |

表 1：公开可用的标注数据集概述。 \faBook 表示作者是否使用了指南（不一定是公开可用的）。

##### SAYFULLINA

由 Sayfullina 等（2018）创建的数据集来源于一个公开可用的 Kaggle 数据集，包含来自英国的 JP，代表了各种行业。⁹⁹9[`www.kaggle.com/datasets/airiddha/trainrev1/?select=Train_rev1.csv`](https://www.kaggle.com/datasets/airiddha/trainrev1/?select=Train_rev1.csv) 作者通过与 1,072 个软技能列表进行精确匹配来提取软技能范围。每个识别出的范围伴随最多 10 个周围的词。通过众包确定突出技能是否属于求职者。为了确保可靠性，工人在一小部分 JP 上进行了测试，每个片段至少由三名工人评估。这一过程导致了一个具有高度类别不平衡的数据集，因为正面例子较多。为此，添加了额外的技能范围，包括那些通常不描述候选人的（标记为负面）和那些一致标记为正面的。

##### GREEN

由 Green 等（2022）使用了与 SAYFULLINA 相同的 Kaggle 数据集。标签是通过众包完成的，他们没有使用专家，而只包括通过测试的工人，并鼓励他们遵循指南。除了“技能”标签捕捉硬技能和软技能外，还在 BIO 方案中使用了“职业”、“领域”、“经验”、“资格”和“无”标签。作者通过对标签进行聚合来减少错误，偏向于高性能工人的标签。此外，他们将特定的“经验”范围重新分类为“技能”范围，并手动将多词范围拆分为独立的范围。

##### FIJO

由 Beauchemin 等（2022）与加拿大保险公司合作创建，包含 2009 年至 2020 年发布的清理和去标识化的法语 JPs。该数据集专注于软技能，包括 867 个 JP，其中 47 个由领域专家选择和标注。标注的范围在“四个类别”中分布不均： “思维”、“结果”、“关系”和“个人”。

##### SKILLSPAN

由 Zhang 等人 (2022a) 提供的内容包括三个 JP 数据集中的匿名原始数据和技能及知识范围的注释，其中一个由于许可问题无法公开。可用的数据集包括：

+   •

    HOUSE: 一个静态的内部数据集，包含 2012-2020 年的不同类型的 JP

+   •

    TECH: StackOverflow JP 平台，主要包括 2020 年 6 月到 2021 年 9 月间收集的技术职位。

公开的注释指南的开发经历了一个迭代过程，从少量 JP 开始，通过三位领域专家的多轮注释和改进进行推进。

##### KOMPETENCER

由 Zhang 等人 (2022b) 提供的 KOMPETENCER 包含丹麦的 JP，附有技能和知识范围的注释，详见附录中的表格 4。注释使用了与 SKILLSPAN 相同的技能定义、指南和指标。该数据集可以用于粗略标签的技能提取，但作者还添加了细粒度的注释，以评估与 ESCO 分类法的分类。对于细粒度注释，他们查询了 ESCO API 以获取注释的范围，并使用 Levenshtein 距离来确定每个获得标签的相关性。然后，通过人工评估来评估这些远程监督标签的质量。他们还重复了这个过程对英语 SKILLSPAN 数据集进行了检查，但仅手动检查了样本以计算统计数据。

##### DECORTE

由 Decorte 等人 (2022) 提供的 DECORTE 是 SKILLSPAN 数据集的一个变体，附有标注的 ESCO 标签。他们使用了识别出的技能，但没有技能和知识标签，不过可以通过将数据集与 SKILLSPAN 匹配来重新创建，详见附录中的表格 4。与 KOMPETENCER 不同，他们手动将技能与适配的 ESCO 标签（如果存在）匹配，以创建一个黄金标准。

##### GNEHM-ICT

由 Gnehm 等人 (2022b) 提供的 GNEHM-ICT 是一个瑞士-德国数据集，其中进行了信息和通信技术（ICT）相关实体识别的注释。这些可能包括 ICT 任务、技术栈、职责等。使用的数据集是两个其他瑞士数据集的组合，即瑞士就业市场监测器和一个在线招聘广告数据集 Gnehm 和 Clematide (2020); Buchmann 等人 (2022)。数据集中约有 25,000 个句子。

##### BHOLA

由 Bhola 等人 (2020) 获得，数据来源于新加坡的一个政府网站¹⁰¹⁰10[`www.mycareersfuture.gov.sg/`](https://www.mycareersfuture.gov.sg/)。该英语数据集的预处理步骤包括将文本转换为小写字母，去除停用词和不常用词。提交 JPs 的公司添加了技能标签，这些标签被映射到整个 JP 文档。这使得该数据集适合通过预测给定 JP 所需的一组技能来进行多标签分类。

## 7 方法

| 论文 | 模型 | 技能类型 | 粒度 | 用例 |
| --- | --- | --- | --- | --- |
| (Fang 等, 2023) | 自定义预训练语言模型 | soft + hard | word-level | $E_{C}$ |
| (Goyal 等, 2023) | FastText skip-gram, GNN | unknown | word-level | $C_{E}$ |
| (Clavié和 Soulié, 2023) | GPT-4 | soft + hard | span-level | $C_{E}$ |
| (李等, 2023) | XMLC - LLM | soft + hard | document-level | $C_{E}$ |
| (Decorte 等, 2023) | GPT-3.5 | soft + hard | sentence-level | $C_{E}$ |
| (张等, 2023) | 多语言 XLM-R | soft + hard | span-level | $E_{C}$ |
| (Decorte 等, 2022) | RoBERTa | soft + hard | sentence-level | $C_{E}$ |
| (张等, 2022c) | RoBERTa, JobBERT | soft + hard | span-level | $C_{D}$ |
| (Gnehm 等, 2022a) | JobBERT-de, SBERT | soft + hard | span-level | $E_{C}$ + $C_{D}$ |
| (张等, 2022b) | BERTbase , DaBERT | soft + hard | span-level | $C_{E}$ |
| (Beauchemin 等, 2022) | Bi-LSTM, CamemBERT | soft | span-level | $E_{C}$ |
| (姚等, 2022) | BERT, word2vec | unknown | word-level | $I$ |
| (Anand 等, 2022) | LaBSE 模型 | soft + hard | title | $C_{E}$ |
| (Vermeer 等, 2022) | RobBERT | soft + hard | document-level | $C_{E}$ |
| (Wild 等, 2021) | BERT, spaCy | soft + hard | span-level | $I$ |
| (Khaouja 等, 2021b) | Sent2vec, SBERT | soft + hard | sentence-level | $C_{E}$ |
| (曹等, 2021) | BERT-BiLSTM-CRF | soft + hard | span-level | $I$ |
| (曹和张, 2021) | BERT-BiLSTM-CRF | soft + hard | span-level | $I$ |
| (李等, 2020) | Deep Averaging Network, FastText | unknown | span-level | $C_{E}$ |
| (Tamburri 等, 2020) | BERT 多语言 Cased | soft + hard | sentence-level | $I$ |
| (Bhola 等, 2020) | BERTbase | unknown | document-level | $C_{E}$ |
| (Gugnani 和 Misra, 2020) | Word2vec | soft + hard | span-level | $I$ |
| (Botov 等, 2019) | Word2vec | unknown | span-level | $C_{E}$ |
| (贾等, 2018) | LSTM | unknown | word-level | $I$ |
| (Sayfullina 等, 2018) | CNN, LSTM, HAN | soft | span-level | $I$ |
| (Javed et al., 2017) | Word2vec | 软+硬 | 跨度级别 | $C_{E}$ |

表 2：有关神经技能提取和分类的出版物。在某些情况下，技能类型并未明确提到，而是从论文中给出的示例推导出来的。

在这一部分，我们调查了技能提取和分类的方法。与第三部分一样，提取的目标是识别带有（$E_{C}$）或不带有粗略标签（$I$）的技能跨度。分类部分涵盖了直接分类方法（$C_{D}$）和带有提取的分类方法（$C_{E}$），两者都旨在检索细粒度的技能标签。

### 7.1 技能提取

本章描述了技能提取方法的演变，分为三类：作为跨度标注的技能识别、通过二分类进行的技能识别以及带有粗略跨度标签的技能提取。从 2018 年的 LSTM 神经网络开始，所有三章的方法在 2019 年引入 BERT（Devlin et al., 2019）之后，广泛使用了 BERT 及其基于 BERT 的模型。最近的进展继续丰富这一领域，整合了更多的语言模型（LMs）。

#### 7.1.1 技能识别作为跨度标注

在这一类别中，将技能识别视为一个跨度标注任务。主要目标是准确识别技能跨度，包括相关技能短语的识别及其精确边界。贾等人（2018）是首批在 2018 年使用序列标注方法从职位描述中识别技能的作者。作者们使用了预训练的 LSTM 神经网络（Lample 等人，2016）来识别词级别的技能术语。Tamburri 等人（2020）也采用了二分类方法，但在句子级别，使用了荷兰职位描述数据集。他们表现最佳的模型 BERT Multilingual Cased，在专家标注的职位描述句子上进行了微调，建议通过更多的数据和优化可以进一步改进。进一步的研究检索了使用预训练 BERT 模型的嵌入（Wild 等人，2021；Cao 和 Zhang，2021；Cao 等人，2021）。值得注意的是，Cao 等人（2021）和 Cao 与 Zhang（2021）将 BERT 的预训练向量与 Bi-LSTM 和 CRF 层结合，以进行更精细的实体分类。这种方法与之前的研究一致，展示了 CRF 层在命名实体识别任务中的有效性（Souza 等人，2020）。在张等人（2023）的研究中，他们进一步建立了领域自适应预训练范式（Gururangan 等人，2020）。他们利用 ESCO 分类法（le Vrang 等人，2014），并将其整合到多语言 XLM-R 模型（Conneau 等人，2020）中，通过这种基于分类法的预训练方法，他们在所有技能识别基准中引入了新的最先进水平。在分析中，他们表明，尤其是对于较短技能的表现有所提高，因为 ESCO 技能通常较短。

与这些单模型方法相比，Gugnani 和 Misra（2020）采用了一种多方面的方法来预测已识别技能跨度的相关性。他们的方法包括四个模块：使用词性标注（PoS），解析具有技能基础的句子（O*NET、Hope 和 Wikipedia），利用现成的序列标注解决方案，以及使用预训练的 word2vec 模型通过余弦相似度确定最终得分。¹¹¹¹11[`www.ibm.com/products/natural-language-understanding`](https://www.ibm.com/products/natural-language-understanding)。

#### 7.1.2 将技能识别视为二分类任务

在这一类别中，技能识别被框定为二分类任务。重点在于确定给定的序列是否构成或包含（特定的）技能。Sayfullina 等人（2018）的任务与其他出版物不同。他们通过精确匹配提取技能跨度，并旨在决定这些技能跨度是否指向一个候选人或其他事物，比如公司。他们尝试了各种分类器和输入表示方法，如软技能掩码、嵌入和标记，发现 LSTM 分类器与技能标记在他们的数据集上效果最佳。Tamburri 等人（2020）在句子级别采用二分类方法，以确定句子是否包含技能。他们表现最好的模型，BERT Multilingual Cased，经过了在荷兰 JP 数据集上使用专家标注的 JP 句子进行的微调。Yao 等人（2022）将单词分类为与技能相关或不相关。他们将 JP 拆分为单个单词，通过字符级和词级编码器分析每个单词，整合了如词性标签和大小写等语言特征。他们的初始训练采用了 AutoPhrase（Shang 等人，2018）进行自动技能术语识别，随后进行手动验证和专家标注样本。该模型进一步通过正负标记学习进行精炼，其中分类器对未标记数据的预测帮助扩展技能库，以实现持续适应。

#### 7.1.3 使用粗略标签的技能提取

本节探讨了使用粗略标签进行技能提取的进展，其中每篇出版物的提取范围跨越了两个到四个不同的类别。Gnehm 等人（2022a）和 Zhang 等人（2022a）的研究都利用了基于序列标注的模型。Gnehm 等人（2022a）专注于使用 jobBERT-de（一种针对 JP 的德语语言模型）进行迭代训练和标注。Zhang 等人（2022a）比较了基于 BERT（Devlin 等人，2019）和基于 SpanBERT（Joshi 等人，2020）的模型，强调了领域适应的重要性。另一方面，Beauchemin 等人（2022）和 Fang 等人（2023）深入探讨了为技能提取训练和优化语言模型的复杂性。Beauchemin 等人（2022）研究了 Bi-LSTM 和 CamemBERT Martin 等人（2020）模型对训练数据量的敏感性，其中 CamemBERT 解冻后表现出最高的均值逐词准确率。Fang 等人（2023）提出了 RecruitPro，这是一种专门用于从招聘文本中提取技能的模型，采用了处理数据噪声和标签不平衡的创新技术。这些论文共同强调了模型开发中量体裁衣的方法和持续创新的必要性。

### 7.2 技能分类

虽然通过分类可以实现技能的标准化，但其他方法如聚类（Bernabé-Moreno 等，2019；Lukauskas 等，2023）、基于字符串相似性的 n-gram 匹配（Boselli 等，2018），或者识别语义相似的技能（Bernabé-Moreno 等，2019；Colombo 等，2019；Grüger 和 Schneider，2019）也能导致标准化的技能范围。这些方法简化了技能范围的多样性和数量，而无需分配标准化标签。从这些方法过渡，我们现在关注技能分类，这是为有效组织和理解技能分配标准化标签的关键步骤。大多数出版物跳过传统的提取步骤，直接将 JPs 匹配到技能库（$C_{E}$），这可以看作是针对技能库的技能提取。例外的是 Gnehm 等人（2022a），他们在细粒度分类步骤之前进行粗略标签的技能范围提取，以及 Zhang 等人（2022b），他们依赖于先前的工作进行提取，并仅关注技能范围与 ESCO（$C_{D}$）的匹配。我们将出版物按方法分为基于语义相似性的匹配和使用极端多标签分类解决匹配任务的两类。

#### 7.2.1 基于相似性的的方法

使用基于相似性的研究将职位发布信息分割成句子或 n-grams 后再进行匹配。以下所有的研究都使用了技能嵌入方法，这可以被看作是技能计数方法的进步（见第一部分"）。随着时间推移，文本嵌入技术的进步体现在方法的范围上。虽然 Javed 等人（2017）和 Botov 等人（2019）使用 word2vec 嵌入（Mikolov 等人，2013）改进了匹配，后来的 Li 等人（2020）则使用了 FastText（Bojanowski 等人，2017），通过利用子词信息来处理词汇外词汇，并捕捉更详细的语义和句法信息。Khaouja 等人（2021b）比较了使用在维基百科句子上训练的 sent2vec 和在数百万句子上训练的 SBERT（Reimers 和 Gurevych，2019）作为嵌入。此外，Zhang 等人（2022c）使用了像 RoBERTa 和 JobBERT 这样的语言模型，将职位发布中的 n-grams 与 ESCO 分类法进行匹配。他们还实验了上下文和频率感知的嵌入。Gnehm 等人（2022a）使用上下文感知的嵌入和与 Zhang 等人（2022c）类似的 SBERT 模型进行直接技能提取，此外，他们还使用层次结构在范围和本体术语中对技能领域进行上下文化。该研究探索了增强 BERT 模型相似性的技术，包括领域内预训练、基于变换器的序列去噪自编码器（TSDAE；Wang 等人，2021）用于领域特定术语，以及用于训练句子嵌入的 Siamese BERT 网络（Reimers 和 Gurevych，2019）。他们进一步利用了 Siamese 网络中的 MNR 损失（Henderson 等人，2017），使用本体数据创建正文本对以更好地匹配标签。SkillGPT Li 等人（2023）是第一个使用 LLM 进行匹配任务的工具，他们将 ESCO 条目转换为结构化文档，并由语言模型向量化。然后，他们总结输入文本，并使用总结的嵌入来检索最接近的 ESCO 条目。

#### 7.2.2 极端多标签分类方法

Bhola 等人 (2020) 首次将技能提取对技能库的极端多标签分类（XMLC）进行公式化。他们使用 BHOLA 数据集的标签（约 2500 个标签）作为技能库，对每个文档进行多标签分类。他们的 BERT–XMLC 框架包括一个文本编码器，使用预训练的 BERTbase 模型将 JP 文本转换为密集的向量表示，一个瓶颈层通过压缩这些表示来减少过拟合（Liu 等人，2017），然后是一个全连接层用于技能的多标签分类。改进包括关注语义技能标签表示和技能共现，使用自助法增强训练数据，并改进技能关联捕捉。他们的模型优于 XMLC 基准。Vermeer 等人 (2022) 采用了这种方法，使用 RobBERT 和额外的线性层，在 BHOLA 和一个非公开的荷兰数据集上进行了验证。同样，Anand 等人 (2022) 将模型扩展到使用 LaBSE 编码的 Feng 等人 (2022) 职位标题来预测技能重要性，根据 0-1 重要性尺度从内部数据库中对技能进行排序。

随后的出版物集中于使用 ESCO 分类法进行技能提取和分类，标签约为 13000 个。对于已经识别的技能范围的纯技能分类，Zhang 等人 (2022b) 通过查询 ESCO API 来进行远程监督，以获得细粒度的技能标签。在模型训练中，他们采用零样本跨语言迁移学习技术，使用各种 BERT 模型，并在丹麦 JPs 上进行微调。这些模型的有效性在适应版的 SKILLSPAN 和 KOMPETENCER 上进行了测试。同年，Decorte 等人 (2022) 针对句子级别的 XMLC 任务进行了研究，再次使用 ESCO 分类法进行远程监督。他们通过三种负采样策略来增强二分类技能分类器的训练，包括 ESCO 层次中的兄弟节点、Levenshtein 距离和 RoBERTa 编码技能名称的余弦相似度。他们的模型采用了冻结的预训练 RoBERTa 进行句子表示的均值池化，然后是针对每个技能的单独二分类器，在 DECORTE 上进行了评估。

就基于相似度的方法而言，LLM 在近期的 XMLC 方法中非常突出。与 Li 等人 (2023) 不同，Decorte 等人 (2023) 仅在训练过程中使用 LLM，以减少延迟并增强可重复性。他们使用 LLM 创建一个合成训练数据集，然后通过对比训练优化一个双编码器，有效地在同一空间中将技能名称和相应的句子表示得更接近。这种方法优于 Decorte 等人 (2022) 的距离监督基线（见附录中的表格 5）。类似地，Clavié 和 Soulié (2023) 将技能提取和分类任务视为单独的二分类问题，使用 GPT-3.5 如同 Decorte 等人 (2023)，但为合成训练生成更多的跨度。他们提出了两种提取方法：一种是针对每个技能使用线性分类器，采用硬负样本采样（Robinson 等人，2021）以改进技能区分；另一种是基于相似度，利用 E5-LARGE-V2 嵌入（Wang 等人，2022）进行 JP 提取和 ESCO 标签或合成句子之间的余弦相似度计算。潜在技能随后通过 LLM 进行重新排序。在使用 DECORTE 数据集的评估中，他们的方法在 GPT-4 上取得了高性能，尽管 GPT-3.5 的结果低于 Decorte 等人 (2023)，详见附录中的表格 5。

Goyal 等人 (2023) 提出了 JobXMLC，这是一个独特的 XMLC 任务框架，与现有方法不同。 JobXMLC 整合了一个工作-技能图来表示工作和技能之间的联系，利用 GNN 从图的结构中进行多跳嵌入，并结合了基于数据集中的技能频率的技能注意力极端分类系统。该框架的有效性在 BHOLA 和一个专有的 StackOverflow 数据集上得到了验证，详见附录中的表格 5。

## 8 结论和未来方向

最近的出版物表明了技能提取中的两个新兴趋势。首先，基于技能库（如 ESCO）提取技能正越来越受欢迎，这有助于跨行业和地区的比较。其次，LLM 在技能提取和分类中的应用越来越多，尤其由于该领域训练数据稀缺，LLM 显得特别有利。

未来在技能提取和分类方面的研究可以聚焦于新兴技能和隐性技能的提取。像 Javed 等人（2017）和 Khaouja 等人（2021b）的方法通过新兴技术和常用关键词更新技能库，但在没有标准基准的情况下评估这些方法仍然困难。隐性技能的提取（即在职位描述中未直接陈述的技能）也受到关注。技术包括引导大型语言模型生成隐性技能的训练数据（Clavié 和 Soulié，2023）和使用完整句子涵盖显性和隐性技能（Decorte 等人，2022，2023）。然而，这些方法需要彻底评估，为未来探索提供了开放领域。

## 限制

需要考虑的一个限制是，本论文仅调查了英文出版物（尽管数据来源于多种语言）。其次，为了更深入地聚焦于话题建模的出版物被排除，即使它们使用了基于深度学习的方法。

## 致谢

我们感谢审稿人提供的有见地的反馈。ES 感谢德国联邦经济事务和气候行动部提供的资金支持，这些资金是根据德国联邦议院通过的第 46SKD127X 号（GENESIS）拨款提供的。MZ 得到了丹麦独立研究基金（DFF）9131-00019B 号资助的支持，BP 则得到了 ERC Consolidator Grant DIALECT 101043235 的资助。

## 参考文献

+   Anand 等人（2022 年）Sarthak Anand、Jens-Joris Decorte 和 Niels Lowie。2022 年。[这是必需的吗？为职位名称排名所需的技能](http://arxiv.org/abs/2212.08553)。

+   Ao 等人（2023 年）Ziqiao Ao、Gergely Horváth、Chunyuan Sheng、Yifan Song 和 Yutong Sun。2023 年。[职位广告中的技能要求：基于工资回归的技能分类方法比较](https://doi.org/https://doi.org/10.1016/j.ipm.2022.103185)。*Information Processing & Management*，60(2):103185。

+   Beauchemin 等人（2022 年）David Beauchemin、Julien Laumonier、Yvan Le Ster 和 Marouane Yassine。2022 年。[“fijo”：一个法语保险软技能检测数据集](https://arxiv.org/abs/2204.05208)。

+   Bernabé-Moreno 等人（2019 年）Juan Bernabé-Moreno、Álvaro Tejeda-Lorente、Julio Herce-Zelaya、Carlos Porcel 和 Enrique Herrera-Viedma。2019 年。[一种基于主题专家知识提取和语义匹配的自动技能标准化方法](https://doi.org/https://doi.org/10.1016/j.procs.2019.12.060)。*Procedia Computer Science*，162:857–864。第七届国际信息技术与定量管理会议（ITQM 2019）：基于人工智能的信息技术与定量管理。

+   Bhola 等人（2020）Akshay Bhola、Kishaloy Halder、Animesh Prasad 和 Min-Yen Kan。2020 年。[从职位描述中检索技能：基于语言模型的极端多标签分类框架](https://doi.org/10.18653/v1/2020.coling-main.513)。在*第 28 届国际计算语言学会议论文集*，第 5832–5842 页，西班牙巴塞罗那（线上）。国际计算语言学委员会。

+   Bojanowski 等人（2017）Piotr Bojanowski、Edouard Grave、Armand Joulin 和 Tomas Mikolov。2017 年。[通过子词信息丰富词向量](https://doi.org/10.1162/tacl_a_00051)。*计算语言学协会会刊*，5:135–146。

+   Boselli 等人（2018）Roberto Boselli、Mirko Cesarini、Fabio Mercorio 和 Mario Mezzanzanica。2018 年。[通过机器学习分类在线职位广告](https://doi.org/https://doi.org/10.1016/j.future.2018.03.035)。*未来一代计算机系统*，86:319–328。

+   Botov 等人（2019）Dmitriy Botov、Julius Klenin、Andrey Melnikov、Yuri Dmitrin、Ivan Nikolaev 和 Mikhail Vinel。2019 年。[使用分布式语义模型和深度学习挖掘劳动市场需求](https://doi.org/10.1007/978-3-030-20482-2_15)。在*商业信息系统 - 第 22 届国际会议，BIS 2019，西班牙塞维利亚，2019 年 6 月 26-28 日，会议记录，第二部分*，第 354 卷的*商业信息处理讲义*，第 177–190 页。施普林格。

+   Buchmann 等人（2022）Marlis Buchmann、Helen Buchs、Felix Busch、Simon Clematide、Ann-Sophie Gnehm 和 Jan Müller。2022 年。瑞士劳动力市场监测器：丰富的需求方微观数据来源。*欧洲社会学评论*。

+   Cao 和 Zhang（2021）Lina Cao 和 Jian Zhang。2021 年。[基于命名实体识别的数据分析师技能需求分析](https://doi.org/10.1109/ICBDIE52740.2021.00023)。在*2021 年第二届国际大数据与信息化教育会议（ICBDIE）*，第 64–68 页。

+   Cao 等人（2021）Lina Cao、Jian Zhang、Xinquan Ge 和 Jindong Chen。2021 年。[基于在线职位广告的职业画像：以数据分析与处理工程技术员为例](https://api.semanticscholar.org/CorpusID:235609409)。*PLoS ONE*，16。

+   Clavié和 Soulié（2023）Benjamin Clavié和 Guillaume Soulié。2023 年。[大型语言模型作为内置零样本 ESCO 技能匹配器](https://arxiv.org/abs/2307.03539)。

+   Colombo 等人（2019）Emilio Colombo、Fabio Mercorio 和 Mario Mezzanzanica。2019 年。[人工智能与劳动力市场的结合：探索自动化与技能之间的联系](https://doi.org/https://doi.org/10.1016/j.infoecopol.2019.05.003)。*信息经济与政策*，47:27–37。人工智能与机器学习的经济学。

+   Conneau 等（2020）亚历克西斯·孔诺、卡尔提凯·坎德尔瓦尔、纳曼·戈亚尔、维什拉夫·乔杜里、吉约姆·温泽克、弗朗西斯科·古兹曼、爱德华·格拉夫、迈尔·奥特、卢克·泽特尔莫耶和维塞林·斯托扬诺夫。2020 年。[大规模无监督跨语言表示学习](https://doi.org/10.18653/v1/2020.acl-main.747)。在*第 58 届计算语言学协会年会论文集*，第 8440–8451 页，在线。计算语言学协会。

+   美国国家研究委员会等（2010）国家研究委员会、南希·托马斯·蒂平斯、玛格丽特·L·希尔顿等。2010 年。*变化经济中的数据库：职业信息网络（O* NET）评审*。国家科学院出版社。

+   德科特等（2022）延斯-乔里斯·德科特、耶伦·范·豪特、约翰内斯·德勒、克里斯·德维尔德和托马斯·德梅斯特。2022 年。[设计用于远程监督技能提取的负采样策略](https://ceur-ws.org/Vol-3218/RecSysHR2022-paper_4.pdf)。在*第 2 届人力资源推荐系统研讨会（RecSys-in-HR 2022）论文集*，第 3218 卷，第 7 页。CEUR。

+   德科特等（2023）延斯-乔里斯·德科特、塞维琳·费尔林登、耶伦·范·豪特、约翰内斯·德勒、克里斯·德维尔德和托马斯·德梅斯特。2023 年。[使用大型语言模型进行极端多标签技能提取训练](https://arxiv.org/abs/2307.10778)。

+   德夫林等（2019）雅各布·德夫林、明-魏·张、肯顿·李和克里斯蒂娜·图塔诺娃。2019 年。[BERT：深度双向变换器的预训练用于语言理解](https://doi.org/10.18653/v1/N19-1423)。在*第 2019 届北美计算语言学协会会议：人类语言技术（长短篇论文卷）*，第 4171–4186 页，美国明尼阿波利斯。计算语言学协会。

+   方等（2023）方楚宇、秦川、张奇、姚凯春、张敬帅、朱恒树、庄福真和熊辉。2023 年。[Recruitpro：一种具有技能感知提示学习的预训练语言模型，用于智能招聘](https://doi.org/10.1145/3580305.3599894)。在*第 29 届 ACM SIGKDD 知识发现与数据挖掘会议论文集*，KDD ’23，第 3991–4002 页，美国纽约。计算机协会。

+   冯等（2022）冯方晓宇、杨银飞、丹尼尔·瑟尔、纳文·阿里瓦扎根和王伟。2022 年。[语言无关的 BERT 句子嵌入](https://doi.org/10.18653/v1/2022.acl-long.62)。在*第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 878–891 页，爱尔兰都柏林。计算语言学协会。

+   Gnehm 等（2022a）Ann-sophie Gnehm, Eva Bühlmann, Helen Buchs, 和 Simon Clematide。2022a。[德语招聘广告中技能要求的细粒度提取与分类](https://aclanthology.org/2022.nlpcss-1.2)。在*第五届自然语言处理与计算社会科学研讨会（NLP+CSS）论文集*中，页码 14–24，阿布扎比，阿联酋。计算语言学协会。

+   Gnehm 等（2022b）Ann-Sophie Gnehm, Eva Bühlmann, 和 Simon Clematide。2022b。[用于分析德语招聘广告的迁移学习和领域适应的评估](https://aclanthology.org/2022.lrec-1.414)。在*第十三届语言资源与评估会议论文集*中，页码 3892–3901，法国马赛。欧洲语言资源协会。

+   Gnehm 和 Clematide（2020）Ann-Sophie Gnehm 和 Simon Clematide。2020。[德语、法语和英语招聘广告的文本分区和分类](https://doi.org/10.18653/v1/2020.nlpcss-1.10)。在*第四届自然语言处理与计算社会科学研讨会论文集*中，页码 83–93，在线。计算语言学协会。

+   Goyal 等（2023）Nidhi Goyal, Jushaan Kalra, Charu Sharma, Raghava Mutharaju, Niharika Sachdeva, 和 Ponnurangam Kumaraguru。2023。[JobXMLC：利用图神经网络对职位技能进行极端多标签分类](https://aclanthology.org/2023.findings-eacl.163)。在*计算语言学协会：EACL 2023 发现*中，页码 2181–2191，克罗地亚杜布罗夫尼克。计算语言学协会。

+   Green 等（2022）Thomas Green, Diana Maynard, 和 Chenghua Lin。2022。[支持职位描述中实体识别的基准语料库的开发](https://aclanthology.org/2022.lrec-1.128)。在*第十三届语言资源与评估会议论文集*中，页码 1201–1208，法国马赛。欧洲语言资源协会。

+   Grüger 和 Schneider（2019）Joscha Grüger 和 Georg Schneider。2019。[在线招聘广告中计算机科学家职位要求的自动化分析](https://doi.org/10.5220/0008068202260233)。在*第十五届国际网络信息系统与技术会议论文集*中，WEBIST 2019，页码 226–233，葡萄牙塞图巴尔。SCITEPRESS - 科学与技术出版公司。

+   Gugnani 和 Misra（2020）Akshay Gugnani 和 Hemant Misra。2020。[使用文档嵌入进行隐性技能提取及其在职位推荐中的应用](https://aaai.org/ojs/index.php/AAAI/article/view/7038)。在*第三十四届 AAAI 人工智能大会，AAAI 2020，第三十二届人工智能创新应用大会，IAAI 2020，第十届 AAAI 教育进展研讨会，EAAI 2020，美国纽约，2020 年 2 月 7-12 日*中，页码 13286–13293。AAAI 出版社。

+   Gururangan et al. (2020) Suchin Gururangan, Ana Marasović, Swabha Swayamdipta, Kyle Lo, Iz Beltagy, Doug Downey, 和 Noah A. Smith. 2020. [不要停止预训练：将语言模型适应领域和任务](https://doi.org/10.18653/v1/2020.acl-main.740)。在*第 58 届计算语言学协会年会论文集*中，第 8342–8360 页，在线。计算语言学协会。

+   HarperCollins Publishers (2023) HarperCollins Publishers. 2023. Collins COBUILD 高级学习者词典：软技能。 [`www.collinsdictionary.com/dictionary/english/soft-skills`](https://www.collinsdictionary.com/dictionary/english/soft-skills).

+   Henderson et al. (2017) Matthew Henderson, Rami Al-Rfou, Brian Strope, Yun hsuan Sung, Laszlo Lukacs, Ruiqi Guo, Sanjiv Kumar, Balint Miklos, 和 Ray Kurzweil. 2017. [智能回复的高效自然语言响应建议](http://arxiv.org/abs/1705.00652).

+   Javed et al. (2017) Faizan Javed, Phuong Hoang, Thomas Mahoney, 和 Matt McNair. 2017. 大规模职业技能规范化以支持在线招聘。在*AAAI 人工智能会议论文集*中，第 31 卷，第 4627–4634 页.

+   Jia et al. (2018) Shanshan Jia, Xiaoan Liu, Ping Zhao, Chang Liu, Lianying Sun, 和 Tao Peng. 2018. 人工智能中的职业技能表示与知识图谱分析。在*2018 IEEE 产品合规工程亚洲研讨会（ISPCE-CN）*中，第 1–6 页。IEEE.

+   Joshi et al. (2020) Mandar Joshi, Danqi Chen, Yinhan Liu, Daniel S. Weld, Luke Zettlemoyer, 和 Omer Levy. 2020. [SpanBERT：通过表示和预测跨度来改进预训练](https://doi.org/10.1162/tacl_a_00300)。*计算语言学协会会刊*, 8:64–77.

+   Khaouja et al. (2021a) Imane Khaouja, Ismail Kassou, 和 Mounir Ghogho. 2021a. [从在线招聘广告中识别技能的调查](https://doi.org/10.1109/ACCESS.2021.3106120)。*IEEE Access*, 9:118134–118153.

+   Khaouja et al. (2021b) Imane Khaouja, Ghita Mezzour, 和 Ismail Kassou. 2021b. [从招聘广告中无监督技能识别](https://doi.org/10.1109/IRI51335.2021.00026)。在*2021 IEEE 第 22 届信息重用与数据科学整合国际会议（IRI）*中，第 147–151 页.

+   Kortum et al. (2022) Henrik Kortum, Jonas Rebstadt, 和 Oliver Thomas. 2022. [AI 招聘广告的解剖：基于文本挖掘的计算机视觉和自然语言处理领域员工技能分析](http://hdl.handle.net/10125/79973)。在*第 55 届夏威夷国际系统科学会议，HICSS 2022，虚拟活动 / 美国夏威夷毛伊岛，2022 年 1 月 4-7 日*中，第 1–10 页。ScholarSpace.

+   Lample 等（2016）Guillaume Lample, Miguel Ballesteros, Sandeep Subramanian, Kazuya Kawakami 和 Chris Dyer。2016 年。[命名实体识别的神经网络架构](https://doi.org/10.18653/v1/N16-1030)。在 *2016 年北美计算语言学协会：人类语言技术会议论文集*，页码 260–270，加利福尼亚州圣地亚哥。计算语言学协会。

+   le Vrang 等（2014）Martin le Vrang, Agis Papantoniou, Erika Pauwels, Pieter Fannes, Dominique Vandensteen 和 Johan De Smedt。2014 年。[ESCO：通过语义互操作性提升欧洲的职位匹配](https://doi.org/10.1109/MC.2014.283)。*计算机*，47(10):57–64。

+   Li 等（2023）Nan Li, Bo Kang 和 Tijl De Bie。2023 年。[Skillgpt：用于技能提取和标准化的大型语言模型的 RESTful API 服务](https://arxiv.org/abs/2304.11060)。

+   Li 等（2020）Shan Li, Baoxu Shi, Jaewon Yang, Ji Yan, Shuai Wang, Fei Chen 和 Qi He。2020 年。[LinkedIn 上的深度职位理解](https://doi.org/10.1145/3397271.3401403)。在 *第 43 届国际 ACM SIGIR 信息检索研究与开发大会论文集，SIGIR 2020，虚拟会议，中国，2020 年 7 月 25-30 日*，页码 2145–2148。ACM。

+   Liu 等（2017）Jingzhou Liu, Wei-Cheng Chang, Yuexin Wu 和 Yiming Yang。2017 年。[用于极端多标签文本分类的深度学习](https://doi.org/10.1145/3077136.3080834)。在 *第 40 届国际 ACM SIGIR 信息检索研究与开发大会论文集，2017 年 8 月 7-11 日，新宿，东京，日本*，页码 115–124。ACM。

+   Lukauskas 等（2023）Mantas Lukauskas, Viktorija Šarkauskaitė, Vaida Pilinkienė, Alina Stundziene, Andrius Grybauskas 和 Jurgita Bruneckienė。2023 年。[通过使用自然语言处理和聚类技术对招聘广告进行分割以增强技能需求理解](https://doi.org/10.3390/app13106119)。*应用科学*，13。

+   Lyu 和 Liu（2021）Wenjing Lyu 和 Jin Liu。2021 年。[软技能与硬技能：什么最重要？来自招聘信息的证据](https://doi.org/https://doi.org/10.1016/j.apenergy.2021.117307)。*应用能源*，300:117307。

+   Martin 等（2020）Louis Martin, Benjamin Muller, Pedro Javier Ortiz Suárez, Yoann Dupont, Laurent Romary, Éric de la Clergerie, Djamé Seddah 和 Benoît Sagot。2020 年。[CamemBERT：一款美味的法语语言模型](https://doi.org/10.18653/v1/2020.acl-main.645)。在 *第 58 届计算语言学协会年会论文集*，页码 7203–7219，在线。计算语言学协会。

+   Mikolov 等（2013）Tomas Mikolov, Kai Chen, Greg Corrado 和 Jeffrey Dean。2013 年。[在向量空间中高效估计词表示](http://arxiv.org/abs/1301.3781)。

+   Napierala 和 Kvetan（2023）Joanna Napierala 和 Vladimir Kvetan。2023 年。[*在变化的世界中改变的职位技能*](https://doi.org/10.1007/978-3-031-16624-2_13)，页码 243–259。Springer International Publishing，Cham。

+   Papoutsoglou 等（2019）Maria Papoutsoglou、Apostolos Ampatzoglou、Nikolaos Mittas 和 Lefteris Angelis。2019 年。[从在线来源提取软件工程劳动市场的知识：一个映射研究](https://doi.org/10.1109/ACCESS.2019.2949905)。*IEEE Access*，7:157595–157613。

+   Reimers 和 Gurevych（2019）Nils Reimers 和 Iryna Gurevych。2019 年。[Sentence-BERT：使用 Siamese BERT 网络的句子嵌入](https://doi.org/10.18653/v1/D19-1410)。在 *2019 年自然语言处理经验方法会议及第 9 届国际自然语言处理联合会议（EMNLP-IJCNLP）*，页码 3982–3992，香港，中国。计算语言学协会。

+   Robinson 等（2021）Joshua David Robinson、Ching-Yao Chuang、Suvrit Sra 和 Stefanie Jegelka。2021 年。[带有困难负样本的对比学习](https://openreview.net/forum?id=CR1XOQ0UTh-)。在 *第 9 届国际学习表示会议，ICLR 2021，虚拟会议，奥地利，2021 年 5 月 3-7 日*。OpenReview.net。

+   Sayfullina 等（2018）Luiza Sayfullina、Eric Malmi 和 Juho Kannala。2018 年。为软技能匹配学习表示。在 *图像、社交网络和文本分析*，页码 141–152，Cham。Springer International Publishing。

+   Shang 等（2018）Jingbo Shang、Jialu Liu、Meng Jiang、Xiang Ren、Clare R. Voss 和 Jiawei Han。2018 年。[从大规模文本语料库中自动化短语挖掘](https://doi.org/10.1109/TKDE.2018.2812203)。*IEEE 知识与数据工程汇刊*，30(10):1825–1837。

+   Shi 等（2020）Baoxu Shi、Jaewon Yang、Feng Guo 和 Qi He。2020 年。[面向市场的显著性和技能提取用于职位目标定位](https://dl.acm.org/doi/10.1145/3394486.3403338)。在 *KDD ’20：第 26 届 ACM SIGKDD 知识发现与数据挖掘会议，虚拟会议，CA，美国，2020 年 8 月 23-27 日*，页码 2871–2879。ACM。

+   Souza 等（2020）Fábio Souza、Rodrigo Nogueira 和 Roberto Lotufo。2020 年。[使用 bert-crf 的葡萄牙语命名实体识别](http://arxiv.org/abs/1909.10649)。

+   Tamburri 等（2020）Damian A. Tamburri、Willem-Jan Van Den Heuvel 和 Martin Garriga。2020 年。[社会智能的数据操作：用于劳动市场技能提取和匹配的数据管道](https://doi.org/10.1109/IRI49571.2020.00063)。在 *2020 IEEE 第 21 届信息重用与集成数据科学国际会议（IRI）*，页码 391–394。

+   Ternikov（2022）Andrei Ternikov。2022 年。[软技能与硬技能识别：来自 CIS 地区 IT 职位广告的见解](https://doi.org/https://doi.org/10.7717/peerj-cs.946)。

+   Vermeer 等人（2022）宁南德·费尔梅尔、维拉·普罗瓦托罗娃、大卫·格劳斯、提利纳·拉贾帕克塞和塞皮德赫·梅斯巴。2022 年。使用 RobBERT 和极端多标签分类从荷兰职位描述中提取隐性和显性技能。在*compjobs ’22：计算工作市场，2022 年 2 月 25 日*。ACM。

+   Wang 等人（2021）柯欣·王、尼尔斯·雷默斯和伊琳娜·古列维奇。2021 年。[TSDAE：使用基于变换器的序列去噪自编码器进行无监督句子嵌入学习](https://doi.org/10.18653/v1/2021.findings-emnlp.59)。在*计算语言学协会会议记录：EMNLP 2021*，页码 671–688，多米尼加共和国蓬塔卡纳。计算语言学协会。

+   Wang 等人（2022）梁旺、南杨、肖龙黄、彬兴焦、林俊杨、大新姜、兰根·马朱姆德和富如·魏。2022 年。[通过弱监督对比预训练的文本嵌入](http://arxiv.org/abs/2212.03533)。

+   Wild 等人（2021）西蒙·怀尔德、索扬·帕尔拉尔、托马斯·汉恩和罗尔夫·多恩贝格。2021 年。[朴素贝叶斯和命名实体识别用于职位发布中的需求挖掘](https://doi.org/10.1109/ICNLP52887.2021.00032)。在*2021 年第三届国际自然语言处理会议（ICNLP）*，页码 155–161。

+   Yao 等人（2022）开春姚、靖帅张、川秦、鹏王、恒书朱和慧雄。2022 年。[知识增强的人岗匹配用于人才招聘](https://doi.org/10.1109/ICDE53745.2022.00325)。在*2022 IEEE 第 38 届国际数据工程会议（ICDE）*，页码 3467–3480。

+   Zhang 等人（2022a）迈克·张、克里斯蒂安·詹森、西夫·索尼克斯和芭芭拉·普兰克。2022a。[SkillSpan：从英语职位发布中提取硬技能和软技能](https://doi.org/10.18653/v1/2022.naacl-main.366)。在*2022 年北美计算语言学协会会议：人类语言技术会议论文集*，页码 4962–4984，美国西雅图。计算语言学协会。

+   Zhang 等人（2022b）迈克·张、克里斯蒂安·诺尔加德·詹森和芭芭拉·普兰克。2022b。[Kompetencer：通过远程监督和迁移学习在丹麦职位发布中进行细粒度技能分类](https://aclanthology.org/2022.lrec-1.46)。在*第十三届语言资源与评估会议论文集*，页码 436–447，法国马赛。欧洲语言资源协会。

+   Zhang 等人（2022c）迈克·张、克里斯蒂安·诺尔加德·詹森、罗布·范德·古特和芭芭拉·普兰克。2022c。使用弱监督从职位发布中提取技能。在*RecSys in HR’22：第二届人力资源推荐系统研讨会，与第 16 届 ACM 推荐系统会议联合举办，2022 年 9 月 18–23 日，美国西雅图*。CEUR 研讨会论文集。

+   张等人（2023）迈克·张，罗布·范·德·古特，芭芭拉·普朗克。2023 年。[ESCOXLM-R: 多语言分类驱动的预训练用于职业市场领域](https://doi.org/10.18653/v1/2023.acl-long.662)。见于 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，页码 11871–11890，多伦多，加拿大。计算语言学协会。

## 附录 A 附录

### A.1 术语示例

在表格 3 中，我们展示了一个示例句子，以便更好地理解术语。

|  | 熟悉 | 使用 | python | 构建 | 测试 |
| --- | --- | --- | --- | --- | --- |
| $I$: | O | O | B | I | O | B |
| $E_{C}$: | O | O | B[skill] | I[skill] | O | B[knowl.] |
| $C_{D}/C_{E}$: | “Python (计算机编程)”，“计划” |
|  | “软件测试” |

表格 3：展示了第 3 节中描述的不同任务的注释示例。对于技能分类 ($C$)，我们在此示例中使用了 ESCO 分类法，对于具有粗略标签的技能提取 ($E_{C}$)，我们遵循了 SkillSpan 张等人 (2022a) 的指导方针。

| 来源 | 技能跨度数量 | 知识跨度数量 |
| --- | --- | --- |
| SKILLSPAN - HOUSE | 2,146 | 1,418 |
| DECORTE - HOUSE | 509* | 210* |
| SKILLSPAN - TECH | 2,241 | 3,828 |
| DECORTE - TECH | 419 | 480* |
| KOMPETENCER | 665 | 255 |

表格 4：标注跨度数量。星号 * 表示 Decorte HOUSE 测试数据集中发现的两个值（标记为知识）实际上来自 Skillspan TECH 数据集；在 Decorte TECH 测试数据集中发现的八个值（四个技能跨度，四个知识跨度）实际上来自 Skillspan HOUSE 数据集。

### A.2 技能和知识跨度数量

在表格 4 中，我们展示了 SKILLSPAN 张等人 (2022a)、DECORTE Decorte 等人 (2022) 和 KOMPETENCER 张等人 (2022b) 数据集中技能和知识的标注跨度数量。

### A.3 选定模型的得分

在表格 5 中，我们展示了 DECORTE Decorte 等人 (2022) 数据集中最近基于 LMM 方法的得分以供比较。此外，我们还展示了张等人 (2023)；戈亚尔等人 (2023) 和（Bhola 等人，2020）在 BHOLA Bhola 等人 (2020) 数据集上的结果。

| 模型 | 来源 | HOUSE* | TECH* | BHOLA |
| --- | --- | --- | --- | --- |
|  |  | MRR | RP@5 | RP@10 | MRR | RP@5 | RP@10 | MRR | R@5 | R@10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| $Classifier^{neg}$ | (Decorte 等, 2022) | 0.299 | 30.82 | 38.69 | 0.326 | 31.71 | 39.09 | 不适用 | 不适用 | 不适用 |
| $GPTsentences^{aug}$ | (Decorte 等, 2023) | 0.428 | 45.74 | 不适用 | 0.529 | 54.62 | 不适用 | 不适用 | 不适用 | 不适用 |
| $GPT3.5Re-ranking$ | (Clavié 和 Soulié, 2023) | 0.427 | 43.57 | 51.44 | 0.488 | 52.50 | 59.75 | 不适用 | 不适用 | 不适用 |
| $GPT4Re-ranking$ | (Clavié 和 Soulié, 2023) | 0.495 | 53.34 | 61.02 | 0.537 | 61.50 | 68.94 | 不适用 | 不适用 | 不适用 |
| $BERT\textendash XMLC+CAB$ | (Bhola 等, 2020) | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 | 0.9049 | 21.67 | 40.49 |
| $JobXMLC$ | (Goyal 等, 2023) | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 | 0.90 | 18.29 | 32.33 |
| $ESCOXML-R$ | (Zhang 等, 2023) | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 | 0.907 | 不适用 | 不适用 |

表 5: 选定模型在 DECORTE 和 BHOLA 基准数据集上的评分。
