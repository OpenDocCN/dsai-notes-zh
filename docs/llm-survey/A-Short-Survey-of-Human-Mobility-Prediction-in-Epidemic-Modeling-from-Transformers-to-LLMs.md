<!--yml

类别：未分类

日期：2024 年 09 月 03 日 17:29:40

-->

# 《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》

> 来源：[`arxiv.org/html/2404.16921`](https://arxiv.org/html/2404.16921)

1.  [1 简介](https://arxiv.org/html/2404.16921v1#S1 "《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》")

1.  [2 人类流动任务](https://arxiv.org/html/2404.16921v1#S2 "《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》")

1.  [3 变压器在人类流动中的应用](https://arxiv.org/html/2404.16921v1#S3 "《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》")

1.  [4 大型语言模型在人类流动中的应用](https://arxiv.org/html/2404.16921v1#S4 "《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》")

1.  [5 挑战与限制](https://arxiv.org/html/2404.16921v1#S5 "《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》")

1.  [6 结论](https://arxiv.org/html/2404.16921v1#S6 "《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》")

# 《从变压器到 LLMs 的流行病建模中人类流动预测的简短调查》

Christian N. Mayemba¹ D’Jeff K. Nkashama^(1,2) Jean Marie Tshimula^(1,3) Maximilien V. Dialufuma^(1,7)

Jean Tshibangu Muabila^(1,4) Mbuyi Mukendi Didier^(1,3,8,9) Hugues Kanda¹ René Manassé Galekwa^(1,3,5)

Heber Dibwe Fita¹ Serge Mundele¹ Kalonji Kalala^(1,6) Aristarque Ilunga^(1,3) Lambert Mukendi Ntobo¹⁰

Dominique Muteba¹¹ Aaron Aruna Abedi¹¹ ¹Prospection and Data Valuation Research Group (Greprovad), Global ²GRIC, Université de Sherbrooke, 加拿大 ³Kinshasa 大学, 刚果民主共和国 (DRC) ⁴LISV-UVSQ, Université Paris-Saclay, 法国 ⁵克拉根福大学, 奥地利 ⁶渥太华大学电气工程与计算机科学学院, 加拿大 ⁷蒙特利尔行为医学中心, 蒙特利尔北岛综合大学健康与社会服务理事会 (CIUSSS-NIM), 加拿大 ⁸孔科雷医院生物医学研究部, 金沙萨, 刚果民主共和国 ⁹佛罗里达大学, 美国 ¹⁰非洲人类锥虫病国家防治计划 (PNLTHA), 刚果民主共和国卫生部流行病监测局 ¹¹国家流行病情报中心 (CNIEP), 刚果民主共和国卫生部流行病监测局。通讯邮箱：jeanmarie.tshimula@unikin.ac.cd 和 christian.mayemba@greprovad.org

###### 摘要

本文提供了关于利用机器学习技术，特别是 Transformer 模型，在预测人类流动模式方面的最新进展的全面综述。了解人们在疫情期间的移动方式对于疾病传播建模和制定有效应对策略至关重要。预测人口流动对于告知流行病学模型和促进公共卫生紧急情况中的有效应对规划至关重要。预测流动模式可以使当局更好地预测疾病的地理和时间传播，优化资源配置，并实施有针对性的干预措施。我们回顾了利用预训练语言模型如 BERT 和专门针对流动预测任务调整的大型语言模型（LLMs）的一系列方法。这些模型在捕捉复杂的时空依赖关系和文本数据中的上下文模式方面展示了显著的潜力。

## 1 引言

在疾病爆发期间预测人口流动是一个复杂但至关重要的任务，对公共卫生决策和制定流行病控制策略具有重要影响。近期的 COVID-19 大流行强调了了解人类流动性在预测和控制传染病传播中的重要性。人类流动数据可以与其他数据源结合，以帮助理解流动模式。这为减缓疾病的迅速传播提供了宝贵的见解。此外，它有助于分析疫情感染案例与公园等休闲区域人类活动之间的相关性。此外，它还能够实现早期检测和迅速隔离病毒感染。流动数据来自各种来源，如通话详细记录、全球定位系统、社交网络和地区专家知识 Isaacman et al. ([2012](https://arxiv.org/html/2404.16921v1#bib.bib13)); Ebrahimpour et al. ([2020](https://arxiv.org/html/2404.16921v1#bib.bib10)); Sobral et al. ([2020](https://arxiv.org/html/2404.16921v1#bib.bib31))。

尽管传统流行病学模型在很大程度上依赖流动数据，采用如聚类技术、微分方程和统计建模等方法 Kulkarni et al. ([2019](https://arxiv.org/html/2404.16921v1#bib.bib16)); Rahman et al. ([2021](https://arxiv.org/html/2404.16921v1#bib.bib27))，近年来却见证了向使用深度学习方法，特别是预训练于大规模语料库的 Transformer 架构的范式转变。这些先进技术旨在解决建模人类流动动态过程中固有的复杂性 Ma et al. ([2022a](https://arxiv.org/html/2404.16921v1#bib.bib22)); Kobayashi et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib15))。

贡献。在本文中，我们提供了一个全面的概述，介绍了近年来旨在利用机器学习技术，特别是 Transformer 模型，以提升人类移动模式预测的研究努力。我们重点介绍了预训练语言模型和专门针对移动预测任务的大型语言模型（LLMs）的贡献。此外，我们讨论了这一新兴领域的挑战和未来方向，强调了这些先进建模技术在提供更准确和可操作的流行病学模型方面的潜力。

![参见说明](img/9c460db5de3a839386a0e202d0bdec40.png)

图 1：人类移动建模任务分类

作者：Luca 等人（[2021](https://arxiv.org/html/2404.16921v1#bib.bib21)）。

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 2：基于 Transformer 的移动预测：编码移动轨迹以预测未来位置。

## 2 人类移动任务

移动模式描述了在给定观察期内考虑人群的移动。人类移动建模任务可以分为两个主要任务：生成任务，即生成现实的移动数据，以及预测任务，即预测个人和集体层面的未来移动模式（Luca 等人（[2021](https://arxiv.org/html/2404.16921v1#bib.bib21)））。在我们的研究背景下，轨迹对应于与个人运动相关的时空信息序列。根据任务的不同，轨迹可以按地理区域进行汇总。给定两个区域，流动表示从一个区域（起点）到另一个区域（目的地）的个体移动的频率。图 [2](https://arxiv.org/html/2404.16921v1#S1.F2 "图 2 ‣ 1 介绍 ‣ 从 Transformer 到 LLMs 的流行病建模中的人类移动预测简短调查") 展示了生成任务，包括流动生成和轨迹生成等子任务，其中生成模型，包括 Transformer 和 LLMs，发挥着至关重要的作用。另一方面，预测任务包括人群流动预测和下一个位置预测，需采用稳健的预测模型。

我们的论文提供了一个关于利用 Transformer 和 LLMs 建模人类移动模式，特别是在流行病控制背景下的最新进展的全面概述（见表 [1](https://arxiv.org/html/2404.16921v1#S3.T1 "表 1 ‣ 3 人类移动中的 Transformer ‣ 从 Transformer 到 LLMs 的流行病建模中的人类移动预测简短调查")）。该表提供了涉及 Transformer 和 LLMs 在流行病建模背景下建模人类移动模式的最新研究所使用的方法、应用和数据集的信息。

## 3 人类移动中的 Transformer

| 论文 | 年份 | 方法 | 应用 | 数据集 |
| --- | --- | --- | --- | --- |
| WiFiMod: 基于 Transformer 的室内人类移动建模使用被动传感 Trivedi 等 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib36)) | 2021 | WiFiMod (基于 Transformer 的模型) | 预测室内人类移动 | 企业 WiFi 系统日志 |
| MobTCast: 利用辅助轨迹预测进行人类移动预测 Xue 等 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib50)) | 2021 | Transformer | 人类移动预测 | Gowalla, Foursquare-NYC (FS-NYC) 和 Foursquare-Tokyo (FS-TKY) |
| 通过考虑类别和区域之间的相互关系来预测人类行为 Osawa 等 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib26)) | 2021 | Transformer | 预测人类移动 | 未指定 |
| TraceBERT—基于 BERT 训练过程对离散位置序列中不完整运动轨迹重构空间–时间间隙的可行性研究 Crivellari 等 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib6)) | 2022 | BERT | 轨迹重构 | 短期游客的大规模实际轨迹数据集 (CDRs) |
| 整合 Transformer 和 GCN 进行 COVID-19 预测 Li 等 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib19)) | 2022 | Transformer 和 GCN | COVID-19 预测 | Nytimes Coronavirus (COVID-19) 数据 |
| 大型语言模型用于空间轨迹模式挖掘 Zhang 等 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib54)) | 2023 | 如 GPT-4 和 Claude-2 的 LLMs | 移动数据中的异常检测 | GEOLIFE, PATTERNS-OF-LIFE |
| 你怎么去哪里？通过使用 Transformers 学习旅行模式信息来改善下一个位置预测 Hong 等 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib12)) | 2022 | Transformer | 下一个位置预测 | Green Class (GC) 和 Yumuv |
| GeoFormer: 使用生成预训练 Transformer 预测人类移动 Solatorio ([2023](https://arxiv.org/html/2404.16921v1#bib.bib32)) | 2023 | 基于 GPT 的模型 | 预测人类移动 | HuMob 挑战 2023 数据集 |
| 使用具有日期编码的 Transformer 建模和生成人工移动轨迹 Kobayashi 等 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib15)) | 2023 | 带日期编码的 Transformer | 建模和生成人工移动轨迹 | HuMob 数据集 |
| CrowdFlowTransformer: 捕捉时空依赖以预测人类流动 Choya 等 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib5)) | 2023 | Transformer | 人群流动预测 | 未指定 |
| TrafFormer: 一种用于预测长期交通的 Transformer 模型 Tedjopurnomo 等 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib34)) | 2023 | Transformer | 长期交通预测 | METR-LA, PEMS-BAY |
| 我接下来会去哪儿？大型语言模型作为人类移动预测器 Wang 等人 ([2023a](https://arxiv.org/html/2404.16921v1#bib.bib40)) | 2023 | LMM | 人类移动预测 | GEOLIFE, FSQ-NYC |
| 通过人类移动轨迹进行用户再识别的 Siamese Transformer 网络 Wang 等人 ([2023a](https://arxiv.org/html/2404.16921v1#bib.bib40)) | 2023 | Siamese Transformer 网络 | 用户再识别 | Gowalla, Brightkite 和 Foursquare (NYC, TKY) |
| 探索大型语言模型在公共事件下的人类移动预测 Liang 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib20)) | 2023 | LLM | 公共事件下的人类移动预测 | 公开事件信息和出租车行程数据 |
| 使用基于 Transformer 的模型学习日常人类移动 Wang 和 Osaragi ([2024](https://arxiv.org/html/2404.16921v1#bib.bib43)) | 2024 | Transformer | 人类移动建模 | 东京大都市区 |
| Health-LLM：通过可穿戴传感器数据进行健康预测的大型语言模型 Kim 等人 ([2024](https://arxiv.org/html/2404.16921v1#bib.bib14)) | 2024 | LLM | 流行病控制 | PMData, LifeSnaps, GLOBEM, AW_FB, MITBIH 和 MIMIC-III |
| 超越模仿：通过上下文感知推理生成大型语言模型的人类移动 Shao 等人 ([2024](https://arxiv.org/html/2404.16921v1#bib.bib29)) | 2024 | LLM | 移动生成 | 腾讯和移动数据集 |
| 大型语言模型作为城市居民：一个 LLM 代理框架用于个人移动生成 Wang 等人 ([2024a](https://arxiv.org/html/2404.16921v1#bib.bib42)) | 2024 | LLM | 个人移动生成 | 未指定 |
| MobilityGPT：使用 GPT 模型增强的人类移动建模 Haydari 等人 ([2024](https://arxiv.org/html/2404.16921v1#bib.bib11)) | 2024 | GPT | 移动建模 | 现实世界数据集 |
| COLA: 跨城市移动转换器用于人类轨迹模拟 Wang 等人 ([2024b](https://arxiv.org/html/2404.16921v1#bib.bib46)) | 2024 | Transformer | 人类轨迹模拟 | GeoLife, Yahoo, New York, Singapore |

表 1：用于流行病控制的人类移动模式建模的 Transformer 和 LLM 文献综述

Transformers 是一种深度学习架构，包含两个部分：编码器和解码器 Vaswani 等人 ([2017](https://arxiv.org/html/2404.16921v1#bib.bib38))。它们在我们观察到的各种机器学习任务的最新突破中发挥了重要作用。这些任务包括但不限于文本到图像生成、机器翻译和文本摘要。Transformer 成功的一个关键因素是注意力机制。这个机制使模型能够优先考虑最相关的输入数据，例如在给定上下文的情况下预测下一个词。尽管最初它主要应用于文本数据，但后来已经证明 Transformer 在多种应用中都很有效，包括预测，在这些应用中它们显示出了比前辈更优越的表现 Vaswani 等人 ([2017](https://arxiv.org/html/2404.16921v1#bib.bib38))；Trivedi 等人 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib36))；Osawa 等人 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib26))；Solatorio ([2023](https://arxiv.org/html/2404.16921v1#bib.bib32))；Xu 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib49))；Kobayashi 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib15))；Tedjopurnomo 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib34))；Wang 等人 ([2023a](https://arxiv.org/html/2404.16921v1#bib.bib40)，[2024b](https://arxiv.org/html/2404.16921v1#bib.bib46))。

此外，Transformers 是多模态的，意味着它们可以结合不同类型的数据源，例如文本、图像、图表等。因此，它们的应用在近年来显著增加，包括在预测流行病建模中的人类流动模式方面。Li 等人 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib18))；Devyatkin 等人 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib9))；Xue 等人 ([2022a](https://arxiv.org/html/2404.16921v1#bib.bib51))；Cui 等人 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib7))；Xue 等人 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib50))；Mai 等人 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib24))；Li 等人 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib19))；Hong 等人 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib12))；Shen 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib30))；Ren 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib28))；Botz 等人 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib3))；Terashima 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib35))；Bengio 等人 ([2020](https://arxiv.org/html/2404.16921v1#bib.bib2))；Xu 等人 ([2021](https://arxiv.org/html/2404.16921v1#bib.bib48))；Ma 等人 ([2022b](https://arxiv.org/html/2404.16921v1#bib.bib23))；Aragão 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib1))；Violos 等人 ([2022](https://arxiv.org/html/2404.16921v1#bib.bib39))；Choya 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib5))；Mao 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib25))；Wang 等人 ([2023b](https://arxiv.org/html/2404.16921v1#bib.bib41))；Chen 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib4))。图[2](https://arxiv.org/html/2404.16921v1#S1.F2 "Figure 2 ‣ 1 Introduction ‣ A Short Survey of Human Mobility Prediction in Epidemic Modeling from Transformers to LLMs")展示了一个用于流动预测的 Transformer 模型的架构。该模型接收一系列位置和时间数据，表示一个流动轨迹作为输入。这一轨迹通过 Transformer 的编码器组件进行编码，捕捉序列中的时间和空间依赖关系。生成的编码随后传递给解码器，生成对轨迹中下一个位置的预测。这个自包含的框架利用 Transformer 的注意力机制，有效捕捉流动数据中的长程依赖和时空模式，从而准确预测未来的位置。

最初，像 BERT 这样基于 Transformer 架构的模型表现出了在基于文本和位置数据进行流动性流向预测上的潜力，（Devlin 等，[2018](https://arxiv.org/html/2404.16921v1#bib.bib8); Li 等，[2021](https://arxiv.org/html/2404.16921v1#bib.bib18); Crivellari 等，[2022](https://arxiv.org/html/2404.16921v1#bib.bib6)）。然而，在推广到新位置和爆发场景方面仍存在挑战（Devyatkin 等，[2021](https://arxiv.org/html/2404.16921v1#bib.bib9)）。Terashima 等人（[2023](https://arxiv.org/html/2404.16921v1#bib.bib35)）引入了 LP-BERT，用于使用 Transformer 架构预测人类流动轨迹。LP-BERT 能够实现并行预测，减少训练和预测时间，这对于需要快速了解人口流动情况的流行病建模等任务可能是有益的。

Botz 等人（[2022](https://arxiv.org/html/2404.16921v1#bib.bib3)）在讨论流行病模型时，讨论了早期警报、流行病监测和公共卫生危机决策支持的建模方法。它强调了人口层面的计算建模，包括机器学习技术，在加强抗击呼吸系统感染的卫生系统方面的重要性。作者强调了预测爆发影响、监测疾病传播和评估干预效果的重要性。

此外，马等人（[2022a](https://arxiv.org/html/2404.16921v1#bib.bib22)）讨论了在控制 COVID-19 传播中人类轨迹完成的重要性，提出了基于 Transformer 的解决方案，并使用开源人类流动数据集对其进行评估。所提出的解决方案涉及使用 Transformer 和深度学习模型来估计轨迹中的缺失元素。

同样，Li 等人（[2021](https://arxiv.org/html/2404.16921v1#bib.bib18)）提出了一种基于 Transformer 的模型，用于季节性流感爆发的长期预测。所提出的模型通过利用 Transformer 捕获长程依赖关系的能力来解决传统预测方法的局限性，并引入了基于曲线相似度测量的源选择模块，以整合空间依赖关系。

贝尔格尼奥等人（[2020](https://arxiv.org/html/2404.16921v1#bib.bib2)）开发了先进的深度学习模型，用于预测 COVID-19 大流行期间的传染性，以便进行积极的接触者追踪，介绍了积极的接触者追踪（PCT）的概念，并讨论了使用深度学习预测器在尊重隐私约束的同时局部预测个体的传染性的情况。该研究突出了基于深度学习的 PCT 方法在减少疾病传播方面的效果，相对于其他追踪方法，表明它们在平衡病毒传播和经济成本的同时保持强大隐私措施方面的潜力。

最近的研究在利用先进的深度学习技术来预测和建模 COVID-19 大流行的各个方面方面取得了显著进展（Devyatkin 等人，[2021](https://arxiv.org/html/2404.16921v1#bib.bib9)；Cui 等人，[2021](https://arxiv.org/html/2404.16921v1#bib.bib7)；Violos 等人，[2022](https://arxiv.org/html/2404.16921v1#bib.bib39)；Xu 等人，[2021](https://arxiv.org/html/2404.16921v1#bib.bib48)）。这些研究利用循环神经网络和类 Transformer 的结构、多范围编码-解码框架、自注意力模型和生成对抗网络来分析社会经济影响、预测 COVID-19 病例、预测城市地区的人类密度以及模拟人类流动轨迹。

Devyatkin 等人（[2021](https://arxiv.org/html/2404.16921v1#bib.bib9)）开发了深度神经网络模型，用于预测 COVID-19 在俄罗斯地区的社会影响，特别是关注莫斯科及其邻近地区的区域集群。这些基于循环和类 Transformer 的结构的模型利用了包括每日病例、年龄人口统计、交通可用性和医院容量在内的异质数据来源。研究表明，结合人口统计和医疗保健特征可以提高对经济影响的预测准确性，并且邻近地区的数据可以增强对医疗和经济影响的预测。总的来说，该研究强调了在大流行期间预测以解决地区间不平等的重要性。Cui 等人（[2021](https://arxiv.org/html/2404.16921v1#bib.bib7)）提出了一种用于 COVID-19 预测的多范围编码-解码框架，利用历史病例数据、人类流动模式以及报告的病例和死亡来增强预测的准确性。通过在多个暴露-感染范围中嵌入特征，并利用时间片段之间的信息传递，该模型在周和日常预测任务中超过了现有方法。消融研究证实了关键组件的有效性，展示了该模型能够在有或没有流动数据的情况下表现良好。该框架解决了不完整数据和未知疾病因素带来的挑战，为精准及时的 COVID-19 预测提供了一种有望的方法。

Violos et al. ([2022](https://arxiv.org/html/2404.16921v1#bib.bib39)) 提出了基于自注意力的编码-解码模型，用于预测城市区域的人口密度，该模型结合了深度学习方法和地理空间特征预处理。该研究通过提供对人口流动模式的洞察，增强了流行病建模中的人类流动预测，帮助分析疾病传播动态，并支持实施战略性干预措施以减缓流行病的传播。Xu et al. ([2021](https://arxiv.org/html/2404.16921v1#bib.bib48)) 提出了 DeltaGAN，一种用于合成连续时间人类流动轨迹的生成模型。DeltaGAN 捕捉真实的流动动态，而无需离散化访问时间，从而实现更准确的轨迹生成和分析。在研究 COVID-19 的传播中，其效用得到了验证，显示出与真实数据相比的人口分布小幅偏差。

时空流行病预测模型已被开发用于通过将领域知识与神经网络整合来预测流行病传播动态（Mao et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib25)); Ma et al. ([2022b](https://arxiv.org/html/2404.16921v1#bib.bib23))）。Mao et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib25)) 介绍了一种名为 MPSTAN 的时空流行病预测模型，该模型将领域知识与神经网络结合，以准确预测流行病传播。该研究强调了选择合适领域知识进行预测的重要性，并提出了一种动态图结构以捕捉时间上变化的区域间相互作用。Ma et al. ([2022b](https://arxiv.org/html/2404.16921v1#bib.bib23)) 提出了一种方法，即层次时空图神经网络（HiSTGNN），用于利用大规模流动数据进行流行病预测。HiSTGNN 结合了两级神经网络架构和基于 Transformer 的模型，以层次化方式捕捉空间和时间信息。该模型在预测 COVID-19 案例数量方面优于现有基准，展示了其卓越的预测能力。该研究突出了利用流动数据进行流行病预测的重要性，并解决了现有图神经网络在捕捉流动图中的社区结构方面的局限性。

此外，像 CF-Transformer 和 MSP-STTN 这样的模型被提出用于捕捉空间-时间依赖性，以进行人群流动预测，进而贡献于流行病建模中的人类流动性预测 Choya et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib5))；Xie et al. ([2022](https://arxiv.org/html/2404.16921v1#bib.bib47))。更具体地说，Choya et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib5)) 引入了 CrowdFlowTransformer (CF-Transformer) 模型，该模型结合了 Transformer 和图卷积，以捕捉空间-时间依赖性进行人群流动预测，旨在通过考虑人群流动数据的时间和空间方面来提高预测准确性，从而应用于流行病中的人类流动性预测。Xie et al. ([2022](https://arxiv.org/html/2404.16921v1#bib.bib47)) 提出了 MSP-STTN 模型，用于短期和长期人群流动预测，重点关注基于网格的人群数据分析。MSP-STTN 通过提供对长期人群流动模式的洞察，为流行病建模中的人类流动性预测做出了贡献，有助于城市规划和交通管理。其应用扩展到超出人群流动分析的各种基于网格的预测问题，如天气预报和空气污染预测。

这些进展突显了机器学习在增强我们对疾病动态的理解以及在流行病期间为公共卫生干预提供信息中的关键作用。

## 4 大型语言模型在人类流动性中的应用

最近，针对高保真度人类流动性模拟和预测的大型语言模型（LLMs）开发出现了激增 Xue et al. ([2022b](https://arxiv.org/html/2404.16921v1#bib.bib52))；Liang et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib20))；Wang et al. ([2023c](https://arxiv.org/html/2404.16921v1#bib.bib44))；Zhang et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib54))；Tang et al. ([2024](https://arxiv.org/html/2404.16921v1#bib.bib33))；Shao et al. ([2024](https://arxiv.org/html/2404.16921v1#bib.bib29))；Kim et al. ([2024](https://arxiv.org/html/2404.16921v1#bib.bib14))；Wang et al. ([2024b](https://arxiv.org/html/2404.16921v1#bib.bib46))；Haydari et al. ([2024](https://arxiv.org/html/2404.16921v1#bib.bib11))。这些模型在配备辅助信息的大量流动数据语料上进行训练，展示了在各种政策和疾病条件下生成合理的流动轨迹的能力。尽管有这些进展，但确保覆盖范围、透明度和现实世界流行病学应用的安全性仍然面临挑战。

进一步探索，Xue 等人 ([2022b](https://arxiv.org/html/2404.16921v1#bib.bib52)) 提出了一个管道，该管道利用语言基础模型进行人类流动性预测，通过将数值时间序列转化为句子进行预测任务。通过将语言模型与流动性提示相结合，这项研究提供了该方法在发现序列模式方面的有效性的实证证据，这对预测流行病建模场景中的人类流动性和潜在疾病传播具有重要价值。同样，Liang 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib20)) 探索了 LLMs 在公共事件期间预测人类流动性模式的应用（LLM-MPE）。针对将在线事件描述中的文本数据纳入流动性预测模型的挑战，LLM-MPE 将原始事件描述转化为标准化格式，并将历史流动性数据进行分段，以考虑常规和事件相关组件进行需求预测。这种方法可以通过提供有关旅行模式和事件期间潜在疾病传播动态的见解，间接为流行病建模提供信息，从而有助于开发更准确的流行病模型。

在另一项进展中，Wang 等人 ([2023c](https://arxiv.org/html/2404.16921v1#bib.bib44)) 介绍了 LLM-Mob，一个利用 LLMs 进行人类流动性预测的框架，捕捉长期和短期依赖关系，并采用包含上下文的提示。LLM-Mob 通过提供可解释的预测，为流行病建模做出贡献，强调了 LLMs 在推进人类流动性预测技术以应对流行病传播方面的潜力。

Tang 等人 ([2024](https://arxiv.org/html/2404.16921v1#bib.bib33)) 提出了一种将 LLMs 与空间优化结合的城市旅行行程规划方法。重点解决在线城市行程规划（OUIP）问题，本研究通过离线和在线实验展示了所提出系统的有效性。该方法包括使用如 GPT-3.5 和 GPT-4 的 LLMs 进行行程生成，并结合空间优化技术和基于规则的评估指标。这种方法通过基于自然语言请求高效生成个性化和连贯的行程，可以在流行病建模中对人类流动性预测做出贡献，这有助于理解和预测城市环境中流行病期间的人类移动模式。此外，通过利用 LLMs 进行行程生成和空间优化，该系统可以适应多样化的用户需求，并提供量身定制的旅行计划，这对建模和预测流行病期间人类流动性变化以便更好地进行公共卫生规划和管理具有重要价值。

最近，Shao 等人 ([2024](https://arxiv.org/html/2404.16921v1#bib.bib29)) 提出了一个名为 MobiGeaR 的方法，用于利用 LLMs 和机械重力模型生成人类移动数据。MobiGeaR 涉及利用 LLM 推理和分工协调机制来有效生成移动模式。该方法显著降低了每个轨迹的 token 成本，并通过数据增强提升了移动预测模型的准确性。MobiGeaR 方法可以通过生成高质量数据来增强稀疏数据集，从而为疫情建模中的人类移动预测做出贡献，使基于历史数据的未来轨迹预测变得可能。通过在下游移动预测任务中提供更好的增强，特别是在意图型预测方面，这种方法可以提高对疫情控制及其他需要准确移动性的应用的预测性能。

## 5 个挑战与局限性

尽管表现出色，Transformers 和 LLMs 在应用于疫情建模中的人类移动预测任务时仍面临若干挑战。一个主要挑战是相关数据源的可用性和质量，这可能存在偏差或错误，从而影响模型性能 Kulkarni 等人 ([2019](https://arxiv.org/html/2404.16921v1#bib.bib16))。此外，这些先进模型的适用性不仅限于资源丰富的地区，还包括低中收入国家 (LMICs) 和资源有限的环境中电子健康记录不发达的地区 Tshimula 等人 ([2023](https://arxiv.org/html/2404.16921v1#bib.bib37))。在这些情况下，利用机器学习技术进行人类移动预测可以显著提高对疫情的理解和管理，即使在数据和基础设施有限的情况下，也能提供有价值的见解。

在疫情背景下，掌握某一环境中移动速度和活动次数可以帮助制定适当的公共卫生策略。以一个村庄的睡眠病筛查活动为例，该村庄的流行病水平已知，且居民的主要活动是农业，移动定义为黎明和黄昏时分居住地与田间地之间的往返，如果医疗专业人员未考虑这种移动，可能会导致大量缺席者和未回应者，尽管这些人已经被计划和计算在内。

另一方面，在工业化国家的背景下，交通工具包括飞机、地铁、高速列车，并且存在大型表面和游乐园，移动速度和数量也会很高；在这种环境下，流行病的传播率与流动性直接成正比。因此，掌握这种人群的流动数据并在公共卫生背景下使用它来遏制流行病是重要的。

在低收入和中等收入国家（LMICs）实施人工智能（AI）模型面临重大挑战，主要由于在与当地数据集集成时其初始性能可能无法复现，以及缺乏监管框架 Wang et al. ([2023d](https://arxiv.org/html/2404.16921v1#bib.bib45))。解决这一挑战对确保在 LMICs 中用于人类流动建模的 Transformers 或 LLMs 的有效性和可靠性至关重要，最终有助于提升流行病监测和当地人群的健康结果。虽然针对特定应用推荐对这些 AI 模型进行微调 Yang et al. ([2023](https://arxiv.org/html/2404.16921v1#bib.bib53)); Li et al. ([2019](https://arxiv.org/html/2404.16921v1#bib.bib17))，但特别是在 LMICs 的背景下，计划使用当地数据集对这些模型进行交叉验证，以提高和再现模型的原始性能是至关重要的。

此外，在使用这些模型进行监测或根据模型预测做出公共卫生干预决策时，可能会出现伦理问题。因此，确保这些技术的负责任部署，尤其是在资源匮乏的地区，对于实现公平有效的流行病控制策略至关重要。

## 6 结论

这一新兴领域显示出通过先进的流动性预测改善流行病建模的潜力。继续在整合多模态数据流和专家知识方面取得进展，可以通过提供更真实的人类移动动态模型，在危机期间显著增强公共卫生决策。然而，进一步的工作对于克服现有局限性和确保 LLMs 的负责任部署仍然是必要的。

成功在 LMICs 中实施 Transformers 或 LLMs 模型需要仔细考虑模型在当地环境中的适用性，并对训练和验证数据集进行调整。在 LMICs 中实施这些 AI 模型的范围在于开发更具上下文适应性的模型，整合当地数据集，并促进合作以提高性能和可重复性。

未来的研究工作应优先考虑在不同地理和社会经济背景下提升模型的通用性。此外，还应将努力方向集中在将这些先进建模技术适应于资源受限的环境，特别是低收入和中等收入国家（LMICs），这些国家可能面临数据和计算资源有限的挑战。这包括探索在 LMICs 收集和处理人类流动数据的创新方法，以及调整大规模语言模型以适应不同的社会文化背景。

解决这些挑战对于确保基于机器学习的方法在流行病建模和全球公共卫生决策中的广泛适用性和影响至关重要。这将有助于在全球范围内制定更公平和有效的流行病应对策略。

## 致谢

作者感谢所有 Greprovad 成员对早期草稿的有益讨论和评论。

## 参考文献

+   Aragão et al. (2023) D. P. Aragão, A. G. d. S. Junior, A. Mondini, C. Distante, 和 L. M. G. Gonçalves. 2023. 巴西阿拉拉夸拉的 Covid-19 模式：一种多模态分析。*国际环境研究与公共卫生杂志*, 20(6):4740。

+   Bengio et al. (2020) Y. Bengio, P. Gupta, T. Maharaj, N. Rahaman, M. Weiss, T. Deleu, E. Muller, M. Qu, V. Schmidt, P. St-Charles, 等. 2020. 预测传染性以进行主动接触追踪。*arXiv 预印本 arXiv:2010.12536*。

+   Botz et al. (2022) J. Botz, D. Wang, N. Lambert, N. Wagner, M. Génin, E. Thommes, S. Madan, L. Coudeville, 和 H. Fröhlich. 2022. 针对流行病情况的早期预警和监测以及决策支持的建模方法。*公共卫生前沿*, 10:994949。

+   Chen et al. (2023) J. Chen, X. Shi, H. Zhang, W. Li, P. Li, Y. Yao, S. Miyazawa, X. Song, 和 R. Shibasaki. 2023. Mobcovid：城市热点人群的确诊病例动态驱动的时间序列预测。*IEEE 神经网络与学习系统汇刊*。

+   Choya et al. (2023) T. Choya, N. Tamura, S. Katayama, K. Urano, T. Yonezawa, 和 N. Kawaguchi. 2023. Crowdflowtransformer：捕捉空间-时间依赖以预测人类流动。在 *2023 IEEE 国际普适计算与通信研讨会及相关活动（PerCom 研讨会）*，第 496–501 页。IEEE。

+   Crivellari et al. (2022) A. Crivellari, B. Resch, 和 Y. Shi. 2022. [Tracebert—通过对离散位置序列进行 BERT 训练过程重建空间-时间缺口的可行性研究](https://doi.org/10.3390/s22041682)。*传感器*。

+   Cui et al. (2021) Y. Cui, C. Zhu, G. Ye, Z. Wang, 和 K. Zheng. 2021. 进入不可观测领域：一种多范围编码器-解码器框架用于 Covid-19 预测。在 *第 30 届 ACM 国际信息与知识管理会议论文集*，第 292–301 页。

+   Devlin 等人（2018）J. Devlin、M.W. Chang、K. Lee 和 K. Toutanova。2018 年。BERT：用于语言理解的深度双向变换器预训练。*arXiv preprint arXiv:1810.04805*。

+   Devyatkin 等人（2021）D. Devyatkin、Y. Otmakhova 和 N. Usenko。2021 年。预测 COVID-19 扩散的社会经济影响及俄罗斯地区的区域差异。见于 *E3S Web of Conferences*，第 301 卷，第 02002 页。EDP Sciences。

+   Ebrahimpour 等人（2020）Z. Ebrahimpour、W. Wan、J.L. Velázquez García、O. Cervantes 和 L. Hou。2020 年。使用大规模社交媒体数据分析社会地理人类移动模式。*ISPRS International Journal of Geo-Information*，9(2):125。

+   Haydari 等人（2024）A. Haydari、D. Chen、Z. Lai 和 C.-. Chuah。2024 年。 [Mobilitygpt: 使用 GPT 模型增强的人类移动建模](https://doi.org/10.48550/arxiv.2402.03264)。*arXiv.org*。

+   Hong 等人（2022）Y. Hong、H. Martin 和 M. Raubal。2022 年。你如何去到哪里？通过使用变换器学习旅行模式信息来改进下一个位置预测。见于 *Proceedings of the 30th International Conference on Advances in Geographic Information Systems*，第 1–10 页。

+   Isaacman 等人（2012）S. Isaacman、R. Becker、R. Cáceres、M. Martonosi、J. Rowland、A. Varshavsky 和 W. Willinger。2012 年。大都市规模的人类移动建模。见于 *Proc. of the 10th international conference on Mobile systems, applications, and services*，第 239–252 页。

+   Kim 等人（2024）Y. Kim、X. Xu、D. McDuff、Cy. Breazeal 和 H.W. Park。2024 年。Health-llm: 通过可穿戴传感器数据进行健康预测的大型语言模型。*arXiv preprint arXiv:2401.06866*。

+   Kobayashi 等人（2023）A. Kobayashi、N. Takeda、Y. Yamazaki 和 D. Kamisaka。2023 年。使用带有日编码的变换器建模和生成人类移动轨迹。见于 *Proc. of the 1st International Workshop on the Human Mobility Prediction Challenge*，第 7–10 页。

+   Kulkarni 等人（2019）V. Kulkarni、A. Mahalunkar、B. Garbinato 和 J. D. Kelleher。2019 年。探讨人类移动性的可预测性极限。*Entropy*，21(4):432。

+   Li 等人（2019）F. Li、Y. Jin、W. Liu、B.P.S. Rawat、P. Cai、H. Yu 等。2019 年。对大规模电子健康记录笔记进行双向编码器表示模型（BERT）微调：一项实证研究。*JMIR medical informatics*，7(3):e14830。

+   Li 等人（2021）L. Li、Y. Jiang 和 B. Huang。2021 年。使用基于变换器的模型对季节性流感的长期预测。*Journal of biomedical informatics*，122:103894。

+   Li 等人（2022）Y. Li、Y. Wang 和 K. Ma。2022 年。 [结合变换器和 GCN 进行 COVID-19 预测](https://doi.org/10.3390/su141610393)。*Sustainability*。

+   Liang 等人（2023）Y. Liang、Y. Liu、X. Wang 和 Z. Zhao。2023 年。探索大型语言模型在公共事件下的人类移动预测。*arXiv preprint arXiv:2311.17351*。

+   Luca et al. (2021) M. Luca, G. Barlacchi, B. Lepri, 和 L. Pappalardo. 2021. 人类流动性的深度学习调查。*ACM Computing Surveys (CSUR)*, 55(1):1–44。

+   Ma et al. (2022a) J. Ma, C. Yang, S. Mao, J. Zhang, S. C. G. Periaswamy, 和 J. Patton. 2022a. 使用变换器进行人类轨迹补全。见 *ICC 2022-IEEE 国际通信会议*, 页 3346–3351。

+   Ma et al. (2022b) Y. Ma, P. Gerard, Y. Tian, Z. Guo, 和 N. V. Chawla. 2022b. 用于疫情预测的层次时空图神经网络。见 *第 31 届 ACM CIKM 会议论文集*, 页 1481–1490。

+   Mai et al. (2022) S. T. Mai, H. T. Phi, A. Abubakar, P. Kilpatrick, H. Q. V. Nguyen, 和 H. Vandierendonck. 2022. 登革热: 从极端气候到疫情预测。见 *2022 IEEE ICDM*, 页 1083–1088。IEEE。

+   Mao et al. (2023) J. Mao, Y. Han, 和 B. Wang. 2023. Mpstan: 基于元人口的时空注意网络用于流行病预测。*arXiv 预印本 arXiv:2306.12436*。

+   Osawa et al. (2021) R. Osawa, K. Suekane, R. Nakamura, A. Inagaki, T. Takagi, 和 I. Munemasa. 2021. [考虑类别和区域之间相互关系的变换器预测人类行为](https://doi.org/10.1109/mipr51284.2021.00029)。*Multimedia Information Processing and Retrieval 会议*。

+   Rahman et al. (2021) M. M. Rahman, K. C. Paul, M. A. Hossain, G. M. N. Ali, M. S. Rahman, 和 J.-C. Thill. 2021. 关于新冠疫情、人类流动性和空气质量的机器学习综述。*IEEE Access*, 9:72420–72450。

+   Ren et al. (2023) J. Ren, M. Liu, Y. Liu, 和 J. Liu. 2023. Transcode: 通过深度学习揭示新冠疫情传播模式。*Infectious Diseases of Poverty*, 12(1):1–20。

+   Shao et al. (2024) C. Shao, F. Xu, B. Fan, J. Ding, Y. Yuan, M. Wang, 和 Y. Li. 2024. 超越模仿: 从上下文感知推理中生成大型语言模型的人类流动性。*arXiv 预印本 arXiv:2402.09836*。

+   Shen et al. (2023) T. Shen, Y. Li, 和 J. M. F. Moura. 2023. 预测新冠疫情动态: 聚类、广义时空注意和流动性及地理接近性的影响。见 *2023 IEEE ICDE*, 页 2892–2904。IEEE。

+   Sobral et al. (2020) T. Sobral, T. Galvão, 和 J. Borges. 2020. 一种基于本体的知识辅助城市流动数据集成和可视化的方法。*Expert Systems with Applications*, 150:113260。

+   Solatorio (2023) A. V. Solatorio. 2023. [Geoformer: 使用生成预训练变换器 (gpt) 预测人类流动性](https://doi.org/10.1145/3615894.3628499)。*HuMob-Challenge@SIGSPATIAL*。

+   Tang et al. (2024) Y. Tang, Z. Wang, A. Qu, Y. Yan, K. Hou, D. Zhuang, X. Guo, J. Zhao, Z. Zhao, 和 W. Ma. 2024. 将空间优化与大型语言模型结合用于开放域城市行程规划。*arXiv 预印本 arXiv:2402.07204*。

+   Tedjopurnomo et al. (2023) D. A. Tedjopurnomo, F. M. Choudhury, 和 A. K. Qin. 2023. [Trafformer: 一种用于预测长期交通的变压器模型](https://doi.org/10.48550/arxiv.2302.12388)。*arXiv.org*。

+   Terashima et al. (2023) H. Terashima, N. Tamura, K. Shoji, S. Katayama, K. Urano, T. Yonezawa, 和 N. Kawaguchi. 2023. 人类移动预测挑战：使用时空 BERT 的下一个位置预测。在 *第 1 届人类移动预测挑战国际研讨会论文集*，第 1–6 页。

+   Trivedi et al. (2021) A. Trivedi, K. Silverstein, E. Strubell, P. Shenoy, 和 M. Iyyer. 2021. [Wifimod: 基于变压器的室内人类移动建模使用被动传感](https://doi.org/10.1145/3460112.3471951)。*The Compass*。

+   Tshimula et al. (2023) J.M. Tshimula, D. K. Nkashama, K. Kalala, M. V. Dialufuma, M. Mukendi Didier, H. Kanda, J. Tshibangu Muabila, 和 C. N. Mayemba. 2023. 重新设计电子健康记录系统以支持发展中国家。在 *2023 年第 7 届国际医学与健康信息学会议论文集*，第 216–221 页。

+   Vaswani et al. (2017) A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A.N. Gomez, Ł. Kaiser, 和 I. Polosukhin. 2017. 注意力即是你所需的一切。*神经信息处理系统进展*，30。

+   Violos et al. (2022) J. Violos, T. Theodoropoulos, A.-C. Maroudis, A. Leivadeas, 和 K. Tserpes. 2022. 基于自注意力的编码器-解码器用于多步骤人类密度预测。*城市移动性杂志*，2:100022。

+   Wang et al. (2023a) B. Wang, M. Zhang, P. Ding, T. Yang, Y. Jin, 和 Y. Xu. 2023a. [通过使用孪生变压器网络的人类移动轨迹进行用户再识别](https://doi.org/10.1007/s10489-023-05234-8)。*Applied intelligence (Boston)*。

+   Wang et al. (2023b) H. Wang, C. Gao, Y. Wu, D. Jin, L. Yao, 和 Y. Li. 2023b. Pategail：一种通过模仿学习的隐私保护移动轨迹生成器。在 *AAAI 人工智能会议论文集*，第 37 卷，第 14539–14547 页。

+   Wang et al. (2024a) J. Wang, R. Jiang, C. Yang, Z. Wu, M. Onizuka, R. Shibasaki, 和 C. Xiao. 2024a. 大型语言模型作为城市居民：个人移动生成的 LLM 代理框架。*arXiv 预印本 arXiv:2402.14744*。

+   Wang and Osaragi (2024) W. Wang 和 T. Osaragi. 2024. 使用基于变压器的模型学习日常人类移动。*ISPRS 国际地理信息学杂志*，13(2):35。

+   Wang et al. (2023c) X. Wang, M. Fang, Z. Zeng, 和 T. Cheng. 2023c. 我接下来会去哪儿？大型语言模型作为人类移动预测器。*arXiv 预印本 arXiv:2308.15197*。

+   Wang et al. (2023d) X. Wang, H.M. Sanders, Y. Liu, K. Seang, B.X. Tran, A.G. Atanasov, Y. Qiu, S. Tang, J. Car, Y.X. Wang, 等. 2023d. ChatGPT: 在低收入和中等收入国家部署的前景和挑战。*The Lancet Regional Health–Western Pacific*，41。

+   Wang et al. (2024b) Y. Wang, T. Zheng, Y. Liang, S. Liu, 和 M. Song. 2024b. Cola: 跨城市移动变换器用于人类轨迹模拟。*arXiv 预印本 arXiv:2403.01801*。

+   Xie et al. (2022) Y. Xie, J. Niu, Y. Zhang, 和 F. Ren. 2022. 多尺寸补丁空间-时间变换器网络用于短期和长期人群流动预测。*IEEE 智能运输系统汇刊*，23(11):21548–21568。

+   Xu et al. (2021) N. Xu, L. Trinh, S. Rambhatla, Z. Zeng, J. Chen, S. Assefa, 和 Y. Liu. 2021. 模拟连续时间人类移动轨迹。见 *第 9 届国际学习表征会议论文集*，页 1–9。

+   Xu et al. (2023) P. Xu, X. Zhu, 和 D.A. Clifton. 2023. 多模态学习与变换器: 综述。*IEEE 模式分析与机器智能汇刊*。

+   Xue et al. (2021) H. Xue, F. Salim, Y. Ren, 和 N. Oliver. 2021. Mobtcast: 利用辅助轨迹预测进行人类移动预测。*神经信息处理系统进展*，34:30380–30391。

+   Xue et al. (2022a) H. Xue, F. D. Salim, Y. Ren, 和 C. L. A. Clarke. 2022a. 通过自然语言生成转换人类移动预测。见 *第十五届 ACM 国际网络搜索与数据挖掘会议论文集*，页 1224–1233。

+   Xue et al. (2022b) H. Xue, B. P. Voutharoja, 和 F. D. Salim. 2022b. 利用语言基础模型进行人类移动预测。见 *第 30 届地理信息系统进展国际会议论文集*，页 1–9。

+   Yang et al. (2023) J. Yang, H. Jin, R. Tang, X. Han, Q. Feng, H. Jiang, S. Zhong, B. Yin, 和 X. Hu. 2023. 实践中利用大型语言模型的力量: 关于 ChatGPT 及其他的综述。*ACM 数据知识发现汇刊*。

+   Zhang et al. (2023) Q. Zhang, H. Amiri, Z. Liu, A. Züfle, 和 L. Zhao. 2023. [大型语言模型在空间轨迹模式挖掘中的应用](https://doi.org/10.48550/arxiv.2310.04942)。*arXiv.org*。

生成于 2024 年 4 月 25 日星期四 17:47:04 由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
