<!--yml

分类：未分类

日期：2024-09-03 17:27:51

-->

# 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》

> 来源：[`arxiv.org/html/2408.04643`](https://arxiv.org/html/2408.04643)

1.  [I 引言](https://arxiv.org/html/2408.04643v1#S1 "在《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

1.  [II 相关工作](https://arxiv.org/html/2408.04643v1#S2 "在《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

1.  [III 方法论](https://arxiv.org/html/2408.04643v1#S3 "在《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [III-A 查找相关文献](https://arxiv.org/html/2408.04643v1#S3.SS1 "在 III 方法论 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [III-B 过滤标准](https://arxiv.org/html/2408.04643v1#S3.SS2 "在 III 方法论 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [III-C 数据收集](https://arxiv.org/html/2408.04643v1#S3.SS3 "在 III 方法论 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [III-D 综合与分析](https://arxiv.org/html/2408.04643v1#S3.SS4 "在 III 方法论 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

1.  [IV 与 LLMs 相关的风险](https://arxiv.org/html/2408.04643v1#S4 "在《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [IV-A 隐私问题](https://arxiv.org/html/2408.04643v1#S4.SS1 "在 IV 与 LLMs 相关的风险 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [IV-B 对抗攻击的易感性](https://arxiv.org/html/2408.04643v1#S4.SS2 "在 IV 与 LLMs 相关的风险 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [IV-C 伦理关注](https://arxiv.org/html/2408.04643v1#S4.SS3 "在 IV 与 LLMs 相关的风险 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [IV-D 偏见与公平性](https://arxiv.org/html/2408.04643v1#S4.SS4 "在 IV 与 LLMs 相关的风险 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [IV-E 不良环境影响](https://arxiv.org/html/2408.04643v1#S4.SS5 "在 IV 与 LLMs 相关的风险 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [IV-F 违反法律或监管要求](https://arxiv.org/html/2408.04643v1#S4.SS6 "在 IV 与 LLMs 相关的风险 ‣ 《大规模语言模型（LLMs）的风险、原因和缓解措施：一项调查》中")

    1.  [IV-G 人类生活中的干扰](https://arxiv.org/html/2408.04643v1#S4.SS7 "在 IV 与大型语言模型相关的风险 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

1.  [V 风险原因](https://arxiv.org/html/2408.04643v1#S5 "在 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-A 训练数据的过度记忆](https://arxiv.org/html/2408.04643v1#S5.SS1 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-B 大型语言模型的固有复杂性](https://arxiv.org/html/2408.04643v1#S5.SS2 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-C 对大型语言模型的认知不足](https://arxiv.org/html/2408.04643v1#S5.SS3 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-D 测试和评估缺陷](https://arxiv.org/html/2408.04643v1#S5.SS4 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-E 不断演变的威胁格局](https://arxiv.org/html/2408.04643v1#S5.SS5 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-F 政策制定缺乏力度](https://arxiv.org/html/2408.04643v1#S5.SS6 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-G 安全漏洞](https://arxiv.org/html/2408.04643v1#S5.SS7 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [V-H 数据质量差](https://arxiv.org/html/2408.04643v1#S5.SS8 "在 V 风险原因 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

1.  [VI 缓解策略](https://arxiv.org/html/2408.04643v1#S6 "在 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [VI-A 稳健模型开发](https://arxiv.org/html/2408.04643v1#S6.SS1 "在 VI 缓解策略 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [VI-B 隐私保护技术](https://arxiv.org/html/2408.04643v1#S6.SS2 "在 VI 缓解策略 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [VI-C 监管合规](https://arxiv.org/html/2408.04643v1#S6.SS3 "在 VI 缓解策略 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [VI-D 安全数据处理](https://arxiv.org/html/2408.04643v1#S6.SS4 "在 VI 缓解策略 ‣ 大型语言模型（LLMs）的广泛部署的风险、原因和缓解措施：调研")

    1.  [VI-E 偏见检测与缓解](https://arxiv.org/html/2408.04643v1#S6.SS5 "在 VI 缓解策略 ‣ 大型语言模型（LLMs）广泛部署的风险、原因及缓解措施：调查")

    1.  [VI-F 可解释性与问责制](https://arxiv.org/html/2408.04643v1#S6.SS6 "在 VI 缓解策略 ‣ 大型语言模型（LLMs）广泛部署的风险、原因及缓解措施：调查")

    1.  [VI-G 使用参数高效模型](https://arxiv.org/html/2408.04643v1#S6.SS7 "在 VI 缓解策略 ‣ 大型语言模型（LLMs）广泛部署的风险、原因及缓解措施：调查")

1.  [VII 结论](https://arxiv.org/html/2408.04643v1#S7 "在风险、原因及缓解措施：大型语言模型（LLMs）的广泛部署调查")

# 大型语言模型（LLMs）广泛部署的风险、原因及缓解措施：调查

Md Nazmus Sakib 计算机科学与工程系

帕布纳科技大学

和技术

帕布纳，孟加拉国

nazmus.200103@s.pust.ac.bd    Md Athikul Islam 计算机科学系

博伊西州立大学

博伊西，ID，美国

mdathikulislam@u.boisestate.edu    Royal Pathak 计算机科学系

博伊西州立大学

博伊西，ID，美国

royalpathak@u.boisestate.edu    Md Mashrur Arifin 计算机科学系

博伊西州立大学

博伊西，ID，美国

mdmashrurarifin@u.boisestate.edu

###### 摘要

大型语言模型（LLMs）的近期进展，如 ChatGPT 和 LLaMA，凭借其在文本生成、摘要和分类方面的卓越能力，显著改变了自然语言处理（NLP）。然而，它们的广泛应用带来了诸多挑战，包括学术诚信、版权、环境影响等问题，以及数据偏见、公平性和隐私等伦理考虑。LLMs 的快速发展也引发了对其评估可靠性和泛化性的担忧。本文提供了对这些主题的文献综述，系统地从 Google Scholar 中收集和综合相关资料。我们的研究深入分析了特定 LLMs 相关的风险，识别了子风险、其原因及潜在解决方案。此外，我们还探讨了与 LLMs 相关的更广泛挑战，详细描述了其原因并提出了缓解策略。通过这项文献分析，我们的调查旨在加深对这些强大模型的影响和复杂性的理解。

###### 关键词：

大型语言模型，LLMs，LLMs 风险，隐私，偏见，可解释性，生成式 AI，自然语言处理，GPT，ChatGPT

## 引言

LLMs（大语言模型）在大量语料库上进行预训练，拥有庞大的参数量，在文本生成、摘要、分类、机器翻译和问答等各种 NLP 任务中表现优异[[4](https://arxiv.org/html/2408.04643v1#bib.bib4)、[5](https://arxiv.org/html/2408.04643v1#bib.bib5)、[17](https://arxiv.org/html/2408.04643v1#bib.bib17)、[22](https://arxiv.org/html/2408.04643v1#bib.bib22)]。在 2023 年，多个主要的 LLMs 被发布，包括 OpenAI 的 ChatGPT[[38](https://arxiv.org/html/2408.04643v1#bib.bib38)]、Meta AI 的 LLaMA[[50](https://arxiv.org/html/2408.04643v1#bib.bib50)]和 Databricks 的 Dolly 2.0。这些模型展示了参数量呈指数级增长的趋势，例如，GPT-2 拥有 15 亿个参数，GPT-3 拥有 1750 亿个参数[[13](https://arxiv.org/html/2408.04643v1#bib.bib13)]。这些模型的应用范围涵盖聊天代理、计算生物学、编程、创意领域、知识工作、医学、推理、机器人技术和社会科学[[27](https://arxiv.org/html/2408.04643v1#bib.bib27)]。

尽管 LLMs 取得了显著的成功，但它们也带来了前所未有的挑战[[27](https://arxiv.org/html/2408.04643v1#bib.bib27)]。各个组织正在部署集成 LLMs 的应用程序，同时现有应用程序和功能也在不断更新这些新的 LLMs[[41](https://arxiv.org/html/2408.04643v1#bib.bib41)]。然而，这些快速更新引发了各种问题，包括学术诚信、版权问题和环境影响[[41](https://arxiv.org/html/2408.04643v1#bib.bib41)]。此外，随着 LLMs 规模的增长，它们对数据的需求变得明显。现在，这些模型训练在如此庞大的数据上，以至于人类无法全部手动审查[[28](https://arxiv.org/html/2408.04643v1#bib.bib28)]。另外，评估结果可能存在缺陷，因为训练数据可能包含测试数据中的实例[[27](https://arxiv.org/html/2408.04643v1#bib.bib27)]。这种大规模的预训练还带来了偏见和公平性等问题，以及伦理担忧。

当引入新的语言模型时，研究人员通常会调查其挑战和限制[[51](https://arxiv.org/html/2408.04643v1#bib.bib51), [39](https://arxiv.org/html/2408.04643v1#bib.bib39)]。此外，一些研究专注于识别和缓解这些模型相关的特定风险[[51](https://arxiv.org/html/2408.04643v1#bib.bib51)]。随着语言模型的迅速发展，迫切需要针对这些领域的综合文献。涵盖语言模型相关问题、解决方案及其根本原因的调查或综述是必不可少的。虽然现有的调查可能涵盖了一般 AI 风险和解决方案[[40](https://arxiv.org/html/2408.04643v1#bib.bib40)]，或语言模型的安全性和隐私方面[[57](https://arxiv.org/html/2408.04643v1#bib.bib57), [39](https://arxiv.org/html/2408.04643v1#bib.bib39)]，或像 ChatGPT 这样的特定模型的挑战和解决方案[[53](https://arxiv.org/html/2408.04643v1#bib.bib53), [18](https://arxiv.org/html/2408.04643v1#bib.bib18)]，但仍需要更为多样化的调查。这样的调查将系统地概述与个别语言模型相关的风险、原因和缓解措施。为了填补这一空白，我们提出了一项全面的调查，以识别特定语言模型所带来的风险，探讨这些风险背后的原因，并提出潜在的缓解技术。

我们的调查分析并讨论了大规模部署 LLMs 所涉及的风险、原因和缓解措施。调查首先列出特定 LLMs 相关的主要风险，然后通过从相关文献中收集的综合数据识别子风险。对于每个子风险，调查识别了受影响的 LLMs，定义了根本原因，并提供了可能的缓解措施。所有解释均由文献检索中提取的论文支持。在最后阶段，调查列出了与 LLMs 相关的风险的一般原因，并讨论了解决这些原因的缓解技术。

论文组织如下几个部分。[第二部分](https://arxiv.org/html/2408.04643v1#S2 "II Related Work ‣ Risks, Causes, and Mitigations of Widespread Deployments of Large Language Models (LLMs): A Survey")回顾了有关人工智能（AI）、LLMs 或特定 LLM 的挑战、原因和解决方案的以往调查工作。[第三部分](https://arxiv.org/html/2408.04643v1#S3 "III Methodology ‣ Risks, Causes, and Mitigations of Widespread Deployments of Large Language Models (LLMs): A Survey")讨论了方法论。[第四部分](https://arxiv.org/html/2408.04643v1#S4 "IV Risks Associated with LLMs ‣ Risks, Causes, and Mitigations of Widespread Deployments of Large Language Models (LLMs): A Survey")考察了与特定 LLM 相关的风险及其子风险。[第五部分](https://arxiv.org/html/2408.04643v1#S5 "V Causes of Risks ‣ Risks, Causes, and Mitigations of Widespread Deployments of Large Language Models (LLMs): A Survey")探讨了这些风险的根本原因，[第六部分](https://arxiv.org/html/2408.04643v1#S6 "VI Mitigation Strategies ‣ Risks, Causes, and Mitigations of Widespread Deployments of Large Language Models (LLMs): A Survey")提供了应对这些风险的缓解技术。最后，[第七部分](https://arxiv.org/html/2408.04643v1#S7 "VII Conclusion ‣ Risks, Causes, and Mitigations of Widespread Deployments of Large Language Models (LLMs): A Survey")总结了论文的关键要点。

## 第二部分 相关工作

有关挑战和解决方案的相关工作分为三类，包括对人工智能（AI）或大型语言模型（LLMs）的总体调查，以及专注于特定 LLM 的调查。

第一类调查研究涉及人工智能（AI）和机器学习（ML）中的风险和潜在解决方案 [[40](https://arxiv.org/html/2408.04643v1#bib.bib40), [49](https://arxiv.org/html/2408.04643v1#bib.bib49)]。Park 等人进行了详细调查，涵盖了各种 AI 欺诈行为，包括欺诈、选举干预、操控和虚假行为，并提出了诸如风险评估、文档记录、记录保存、透明度和人工监督等缓解技术 [[40](https://arxiv.org/html/2408.04643v1#bib.bib40)]。相反，Tian 等人调查了不同的中毒攻击策略，如标签和数据操控，并提出了相应的对策，包括基于数据和模型的方法 [[49](https://arxiv.org/html/2408.04643v1#bib.bib49)]。

第二类调查集中于评估 LLMs 的一般风险和解决方案。Yao 等人研究了与 LLMs 相关的安全性和隐私问题，识别了它们对代码安全、数据安全和隐私的积极贡献，以及它们在针对硬件、操作系统、软件、网络和用户的各种攻击中的参与[[57](https://arxiv.org/html/2408.04643v1#bib.bib57)]。类似地，Dong 等人对 LLMs 在训练和推理阶段的广泛攻击进行了调查，并讨论了防御策略[[8](https://arxiv.org/html/2408.04643v1#bib.bib8)]。Hadi 等人旨在调查应用、挑战、局限性和未来前景，但主要提供了对生成 AI 和 LLMs 的概述，专注于它们的任务和应用，而不是全面覆盖所有方面[[19](https://arxiv.org/html/2408.04643v1#bib.bib19)]。

最终类别涉及关注个体 LLMs 的调查，实践者主要考察了 ChatGPT，因为它最近取得了成功。Wang 等人阐明了 AI 生成内容（AIGC）随时间的演变，特别是最新引入的预训练大型模型[[53](https://arxiv.org/html/2408.04643v1#bib.bib53)]。他们的研究深入探讨了 AIGC 的各种应用，同时揭示了对 AIGC 服务构成风险的安全和隐私威胁，以 ChatGPT 作为中心参考点。类似地，Yang 等人专门对 ChatGPT 进行了调查[[56](https://arxiv.org/html/2408.04643v1#bib.bib56)]。他们首先构建了 LLMs 的进化树，然后简要介绍了如 BERT 和 ChatGPT 等流行模型。此外，他们还从数据角度探讨了关键问题，并以对 ChatGPT 的效率和可信度的考察结束了讨论。

我们的调查通过关注个体 LLMs 所带来的独特风险、揭示其根本原因，并提出可行的解决方案，使其区别于以往的文献。

## III 方法论

方法论概述了进行调查的详细步骤。这些步骤包括查找相关文献、应用筛选标准、收集和提取数据，以及综合和分析结果。

### III-A 搜索相关文献

我们使用了 Google Scholar 来搜索与 LLMs 相关的风险、原因和缓解措施的现有文献。搜索策略集中在包含如“LLMs”、“大型语言模型”、“风险评估”和“风险缓解”等关键词的文献上。

### III-B 筛选标准

我们包括了与自然语言处理、信息安全、人工智能、隐私以及文献中提到的特定语言模型等领域相关的 LLM 文献 [[56](https://arxiv.org/html/2408.04643v1#bib.bib56)]。我们排除了作为教程、演讲、评论、讨论和主题演讲发布的论文。此外，我们考虑了 2000 年至 2024 年间发表的文献。

### III-C 数据收集

我们采用了 Kitchenham 和 Charters [[30](https://arxiv.org/html/2408.04643v1#bib.bib30)] 所述的数据收集方法，遵循了选择文献的特定质量标准：

+   •

    评估上下文和数据源的保留与呈现。

+   •

    评估报告的清晰度和连贯性。

+   •

    检查对伦理考量的关注。

第一作者对从 Google Scholar 检索的每个搜索结果的标题和摘要进行了彻底分析，确定了被认为相关的论文以供进一步审查。随后，所有作者共同对选定的文献进行了全文审阅，应用了过滤和质量标准，最终纳入了 47 篇论文用于研究。

### III-D 综合与分析

本研究的综合涉及提取关于 LLM 风险、原因和解决方案的总结发现。为了记录这些风险，我们开发了一个表格，并手动识别了其相应的原因。此外，我们创建了另一个表格来对通用原因进行分类。这些表格后来在论文中以表格和列表的形式呈现。

## IV LLM 相关的风险

| 风险 | 子风险 | 相关的 LLM | 原因 | 可能的缓解措施 | 参考文献 |
| --- | --- | --- | --- | --- | --- |
| 1\. 隐私问题 | 泄露用户数据 | GPT-Neo, GPT-3 | 记忆训练数据 | 筛选和更改训练数据的分布 | [[3](https://arxiv.org/html/2408.04643v1#bib.bib3), [59](https://arxiv.org/html/2408.04643v1#bib.bib59), [55](https://arxiv.org/html/2408.04643v1#bib.bib55), [61](https://arxiv.org/html/2408.04643v1#bib.bib61)] |
|  | 检索和训练数据的泄漏 | Llama-7b-Chat, GPT-3.5-turbo | 记忆检索和训练数据于 RAG | 隐私保护的提示调整 | [[59](https://arxiv.org/html/2408.04643v1#bib.bib59), [34](https://arxiv.org/html/2408.04643v1#bib.bib34)] |
|  | 揭示用户活动 | Bard | 使用活动数据进行训练 | 选择退出选项、同意书 | [[18](https://arxiv.org/html/2408.04643v1#bib.bib18)] |
| 2\. 易受对抗攻击的影响 | 有害内容生成 | GPT | 提示注入 | 过滤检索到的信息 | [[54](https://arxiv.org/html/2408.04643v1#bib.bib54)] |
|  | 脆弱的句子嵌入 | GPT, BERT | 嵌入中敏感信息的捕获 | 四舍五入、隐私保护映射、子空间投影 | [[39](https://arxiv.org/html/2408.04643v1#bib.bib39)] |
|  | 偷窃 API 服务 | BERT | 容易模仿受害者模型 | 软化预测、预测扰动 | [[20](https://arxiv.org/html/2408.04643v1#bib.bib20)] |
| 3\. 伦理问题 | 缺乏可靠性、可信度和责任感 | BERT、RoBERTa、Gemma-7b、Llama-2-7b | 对抗攻击、过拟合 | 正则化、对抗训练、随机平滑 | [[25](https://arxiv.org/html/2408.04643v1#bib.bib25), [32](https://arxiv.org/html/2408.04643v1#bib.bib32), [31](https://arxiv.org/html/2408.04643v1#bib.bib31), [36](https://arxiv.org/html/2408.04643v1#bib.bib36), [15](https://arxiv.org/html/2408.04643v1#bib.bib15)] |
|  | 高定价 | T5、BERT、GPT 等 | 更高的能耗 | 更轻量和减少参数化的模型、更快的硬件 | [[37](https://arxiv.org/html/2408.04643v1#bib.bib37)] |
| 4\. 偏见与公平性 | 社会和环境偏见 | GPT-4、Claude-2、Llama-2-70b、Zephyr-7b | 偏见的训练数据和模型架构 | 超参数调整、指令指导、去偏见调整 | [[10](https://arxiv.org/html/2408.04643v1#bib.bib10), [7](https://arxiv.org/html/2408.04643v1#bib.bib7)] |
|  | 人类般的偏见和刻板印象 | BERT、ELMo、GPT、GPT-2、RoBERTa、DeBERTa、T5 | 大量带有偏见的人类书写训练语料 | 去偏见损失、自动去偏见、提示工程、模型微调 | [[17](https://arxiv.org/html/2408.04643v1#bib.bib17), [29](https://arxiv.org/html/2408.04643v1#bib.bib29), [48](https://arxiv.org/html/2408.04643v1#bib.bib48), [22](https://arxiv.org/html/2408.04643v1#bib.bib22), [2](https://arxiv.org/html/2408.04643v1#bib.bib2), [7](https://arxiv.org/html/2408.04643v1#bib.bib7), [35](https://arxiv.org/html/2408.04643v1#bib.bib35)] |
| 5\. 不利的环境影响 | 财务不稳定和高 CO2 排放 | 所有 LLMs | 高能耗 | 更轻量和减少参数化的模型、更快的硬件 | [[37](https://arxiv.org/html/2408.04643v1#bib.bib37), [44](https://arxiv.org/html/2408.04643v1#bib.bib44), [2](https://arxiv.org/html/2408.04643v1#bib.bib2)] |
| 6\. 违反法律或监管要求 | 可能使用版权数据 | 专有 LLMs | 训练中使用的版权数据副本或近似变体 | 版权回归、softmax 回归 | [[5](https://arxiv.org/html/2408.04643v1#bib.bib5), [55](https://arxiv.org/html/2408.04643v1#bib.bib55)] |
| 7\. 对人类生活的干扰 | 健康和福祉 | 包括 GPT-3 在内的所有 LLMs | 大量文本生成、低质量科学文献 | 制定政策 | [[6](https://arxiv.org/html/2408.04643v1#bib.bib6)] |
|  | 财务不稳定 | 所有 LLMs | 高效的 LLMs | 强大的政策制定 | [[9](https://arxiv.org/html/2408.04643v1#bib.bib9)] |

表 I：使用三种方法评估的消融研究结果。

### IV-A 隐私问题

过度记忆训练数据的模型容易过拟合，可能会危及用户隐私。特别是，像 GPT-Neo 这样的巨大模型倾向于保留大量的训练数据，往往会导致重复模式和隐私泄露的风险增加 [[3](https://arxiv.org/html/2408.04643v1#bib.bib3)]。在检索增强生成（RAG）模型，如 Llama-7b-Chat 和 GPT3.5-turbo 中，检索和训练数据集数据库可能暴露私人数据，进一步增加了隐私风险 [[59](https://arxiv.org/html/2408.04643v1#bib.bib59)]。像 Bard 这样的模型使用用户活动数据来训练模型以及原始训练数据，这可能会导致透露用户活动信息的倾向 [[18](https://arxiv.org/html/2408.04643v1#bib.bib18)]。

### IV-B 对抗攻击的易受性

GPT 模型，特别是 ChatGPT，容易受到各种安全漏洞的影响。例如，对手可能会指示 ChatGPT 生成对社会有害的文本、创建恶意代码，甚至分发恶意代码库 [[54](https://arxiv.org/html/2408.04643v1#bib.bib54)]。此外，像 BERT、GPT 或 GPT-2 这样的语言模型生成的句子嵌入可能被攻击者逆向工程，潜在地暴露敏感信息 [[39](https://arxiv.org/html/2408.04643v1#bib.bib39)]。此外，微调后的公开 BERT 模型 API 允许攻击者提取目标 BERT 模型的本地副本，从而使他们能够对原始模型进行对抗性攻击 [[20](https://arxiv.org/html/2408.04643v1#bib.bib20)]。

### IV-C 伦理问题

使用 GPU 进行 LLM 的预训练需要大量的 RAM，这导致公司成本增加 [[37](https://arxiv.org/html/2408.04643v1#bib.bib37)]。此外，若没有适当的监管，LLM 服务提供商可能会向用户收取高额费用。重要的是，LLM 应该对具有相同语义的文本产生一致的输出。然而，它们在这些情况下的可变响应引发了伦理问题，包括可靠性、可信度和问责制等问题。像 BERT 和 RoBERTa 这样的模型已经展示了这些脆弱性 [[25](https://arxiv.org/html/2408.04643v1#bib.bib25), [32](https://arxiv.org/html/2408.04643v1#bib.bib32), [31](https://arxiv.org/html/2408.04643v1#bib.bib31)]。

### IV-D 偏见与公平性

由于训练在庞大的数据集上，某些 LLMs，如 GPT-4、Claude-2、Llama-2-70b、Zephyr-7b，表现出对当前社会和环境话题的偏见，这表明它们受到当代社会政治话语的显著影响[[10](https://arxiv.org/html/2408.04643v1#bib.bib10), [1](https://arxiv.org/html/2408.04643v1#bib.bib1)]。此外，大型 BERT 变体的掩蔽语言建模（MLM），如 RoBERTa、DeBERTa、T5，显示出对男性和女性性别的情感和人类偏见[[17](https://arxiv.org/html/2408.04643v1#bib.bib17), [29](https://arxiv.org/html/2408.04643v1#bib.bib29), [48](https://arxiv.org/html/2408.04643v1#bib.bib48), [2](https://arxiv.org/html/2408.04643v1#bib.bib2)]。情感偏见是像 BERT 这样的模型的另一大关注点，这些模型在解释和生成文本时通常显示出显著的偏见[[22](https://arxiv.org/html/2408.04643v1#bib.bib22)]。GPT-3 在训练过程中使用了 Common Crawl 数据集，可能会产生即使在提示句子无毒时也具有高毒性的句子[[2](https://arxiv.org/html/2408.04643v1#bib.bib2)]。

### IV-E 不利的环境影响

尽管大型语言模型（LLMs）取得了成功，但它们也带来了一些负面的环境影响，比如高能耗和加剧数字鸿沟[[41](https://arxiv.org/html/2408.04643v1#bib.bib41), [2](https://arxiv.org/html/2408.04643v1#bib.bib2)]。例如，像 T5 和 BERT 这样的 LLMs 消耗大量的能源，导致显著更高的 CO2 排放[[37](https://arxiv.org/html/2408.04643v1#bib.bib37), [44](https://arxiv.org/html/2408.04643v1#bib.bib44)]。即使在没有超参数调整的情况下，训练一个 BERT 模型所需的能量也相当于一次跨美洲航班[[2](https://arxiv.org/html/2408.04643v1#bib.bib2)]。

### IV-F 违反法律或监管要求

训练在广泛数据集上的 LLMs 可能会生成违反法律或监管要求的输出，或者与受版权保护的材料非常相似[[5](https://arxiv.org/html/2408.04643v1#bib.bib5)]。这些模型通常使用来源于互联网的数据、公开可用的数据集，以及偶尔的专有信息[[55](https://arxiv.org/html/2408.04643v1#bib.bib55)]。随着 LLMs 的快速扩展，确保专有数据未被未经授权使用变得越来越具挑战性。对这些模型的监管也很复杂。另一个风险是在与 LLMs 交互时意外暴露私人数据；例如，三星电子在多次与 ChatGPT 互动时泄露了敏感信息[[55](https://arxiv.org/html/2408.04643v1#bib.bib55)]。

### IV-G 人类生活中的干扰

大量由 LLM 生成的文本可能导致在医学领域的误用，从而可能对公共健康构成风险[[6](https://arxiv.org/html/2408.04643v1#bib.bib6)]。此外，这种大量文本的涌入可能导致信息过载和焦虑。像 ChatGPT 这样的 LLM 也可能生成低质量的科学文献，这可能对人类健康产生不利影响[[6](https://arxiv.org/html/2408.04643v1#bib.bib6)]。LLM 所提供的先进能力和自动化已经使许多人类工作面临风险，接近 19%的职位经历了至少 50%的任务由 LLM 覆盖[[9](https://arxiv.org/html/2408.04643v1#bib.bib9)]。这可能导致显著的经济干扰。

## 风险的原因

以下是与 LLM 相关的风险的一般原因。

### V-A 训练数据的过度记忆

深度语言模型倾向于记住训练数据，导致过拟合[[36](https://arxiv.org/html/2408.04643v1#bib.bib36), [24](https://arxiv.org/html/2408.04643v1#bib.bib24), [47](https://arxiv.org/html/2408.04643v1#bib.bib47)]。这种记忆通常会导致私人数据泄露。Liu 等人展示了 BERT 模型由于记住训练数据而表现出较差的泛化能力[[36](https://arxiv.org/html/2408.04643v1#bib.bib36)]。类似地，Zhou 等人观察到 GPT-Neo 模型有记忆倾向，而 OPT 和 Llama 等模型则表现出较少的记忆倾向[[61](https://arxiv.org/html/2408.04643v1#bib.bib61)]。另一个发现是较大的模型比小模型记忆更多[[42](https://arxiv.org/html/2408.04643v1#bib.bib42)]。

### V-B LLM 的固有复杂性

随着 LLM 规模的不断增加及其执行类似于人类能力的任务的能力，理解它们变得越来越复杂。这种固有的复杂性阻碍了 LLM 在科学研究和数据分析中的应用[[46](https://arxiv.org/html/2408.04643v1#bib.bib46)]。TripoSR 和 GemMoE-Beta-1 模型在推理的透明度方面比 Gemma-7b 和 Llama-2-7b 模型表现更佳[[15](https://arxiv.org/html/2408.04643v1#bib.bib15)]。

### V-C 对 LLM 缺乏认知

最终用户、政策制定者、各种利益相关者甚至开发者自己可能缺乏对 LLM 所带来的严重风险的深入了解。例如，在公共健康的背景下，关键是要认识到 CareCall 聊天机器人偶尔会做出类似于人类能力的承诺，尽管其无法实现这些承诺[[26](https://arxiv.org/html/2408.04643v1#bib.bib26)]。允许这种行为可能对企业造成严重后果。

### V-D 测试和评估缺陷

有时，LLM 的训练使用了基准数据集的开发和测试集，导致了不当评估，这种现象被称为基准泄露 [[60](https://arxiv.org/html/2408.04643v1#bib.bib60)]。这一问题引发了对 LLM 测试公平性和可靠性的担忧。值得注意的是，像 OpenLLaMA-3B 和 LLaMA-2-7B 这样的模型由于基准泄露而在评估中表现不佳 [[60](https://arxiv.org/html/2408.04643v1#bib.bib60)]。

### V-E 威胁形势的演变

LLMs 周围的威胁形势随着其扩展而迅速演变。其中一个安全问题是 “越狱提示”的出现，这种提示绕过 LLM 的安全措施，迫使它们生成有害内容。这些提示的最新迭代显示出惊人的成功率，有些甚至在最新的模型如 ChatGPT (GPT-3.5) 和 GPT-4 上达到了 99% 的攻击成功率 (ASR) [[43](https://arxiv.org/html/2408.04643v1#bib.bib43)]。另一个新兴攻击向量被称为 “间接提示注入”，它迫使 LLM 集成的应用将预期的对抗性内容传递给最终用户。例如，基于 GPT-4 模型的 Bing Chat 已经展示了对这种攻击的脆弱性 [[16](https://arxiv.org/html/2408.04643v1#bib.bib16)]。

### V-F 缺乏强有力的政策制定

不足的政策，特别是在数据保护和安全方面，可能使 LLMs 和其用户面临风险。例如，LLM 的第三方提供商可能在未经适当同意或提供有关数据使用的明确说明的情况下收集用户数据 [[55](https://arxiv.org/html/2408.04643v1#bib.bib55)]。这会导致严重的隐私泄露。

### V-G 安全漏洞

LLMs 内在的安全漏洞使它们易于在输出生成中被操控。这些漏洞可能被利用来制造假新闻、垃圾邮件以及其他欺骗性内容 [[11](https://arxiv.org/html/2408.04643v1#bib.bib11)]。针对 LLMs 的对抗性攻击包括多种策略，例如模型盗窃，旨在提取模型形状和参数，数据构建以模拟训练数据，数据中毒以引入恶意数据，以及模型劫持以执行未经授权的任务 [[11](https://arxiv.org/html/2408.04643v1#bib.bib11)]。此外，对 LLM 应用的攻击包括提示注入，导致输出不一致，以及隐私泄露攻击 [[11](https://arxiv.org/html/2408.04643v1#bib.bib11)]。例如：ChatGPT 和 Azure OpenAI (GPT-3.5 turbo) 易受提示注入攻击。

### V-H 数据质量差

鉴于 LLM 依赖于使用大数据集进行预训练，确保这些数据集的质量变得至关重要。预处理和策划如此庞大的数据集带来了重大挑战 [[19](https://arxiv.org/html/2408.04643v1#bib.bib19)]。如果数据集本身包含偏见、文化规范和刻板印象，则在这些数据上训练 LLM 会将这些局限性传播到模型中 [[1](https://arxiv.org/html/2408.04643v1#bib.bib1)]。Agiza 等人展示了意识形态和政治偏见如何被深植于 Mistral-7b-v0.2 模型中 [[1](https://arxiv.org/html/2408.04643v1#bib.bib1)]。

## VI 缓解策略

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：树状图中的框代表 LLM 风险的根本原因，每个原因下的列表提到针对该特定原因的缓解技术。

以下是针对 LLM 根本风险的缓解技术。图 [1](https://arxiv.org/html/2408.04643v1#S6.F1 "图 1 ‣ VI 缓解策略 ‣ 大型语言模型（LLMs）广泛部署的风险、原因和缓解措施：调查") 说明了这些针对 LLM 相关风险原因的缓解技术。

### VI-A 强健的模型开发

LLM 需要经过彻底的开发，包括广泛的测试和评估过程，以解决安全漏洞和偏见。存在各种技术来缓解过拟合问题，包括正则化、丢弃、批量归一化和标签平滑 [[24](https://arxiv.org/html/2408.04643v1#bib.bib24)]。遵循工业标准指南和最佳实践对于缓解对抗性攻击也至关重要。此外，对抗性训练和集成方法也是预防对抗性攻击的广泛使用技术 [[58](https://arxiv.org/html/2408.04643v1#bib.bib58), [52](https://arxiv.org/html/2408.04643v1#bib.bib52)]。

### VI-B 隐私保护技术

保护数据隐私有多种技术可用。一种方法涉及集中隐私设置，由服务提供商代表最终用户配置隐私设置 [[45](https://arxiv.org/html/2408.04643v1#bib.bib45), [33](https://arxiv.org/html/2408.04643v1#bib.bib33)]。相反，其他方法则赋予最终用户自行设置数据隐私措施的能力。一个例子是隐私保护的提示调整（RAPT） [[34](https://arxiv.org/html/2408.04643v1#bib.bib34)]。

### VI-C 法规遵从

随着语言模型和人工智能的不断扩展，建立健全的监管合规措施至关重要。应对合规挑战包括确保数据隐私和安全、减轻偏见、促进公平以及增强透明度 [[23](https://arxiv.org/html/2408.04643v1#bib.bib23)]。制定全面的治理框架对于有效解决这些问题是至关重要的 [[23](https://arxiv.org/html/2408.04643v1#bib.bib23)]。必须优先考虑伦理语言模型的发展，以防止偏见、促进公平和维护问责制 [[23](https://arxiv.org/html/2408.04643v1#bib.bib23)]。政策应认识到当今大语言模型的广泛功能和限制，倡导透明、负责任和伦理的应用 [[15](https://arxiv.org/html/2408.04643v1#bib.bib15)]。持续监控对于及时识别和纠正合规问题是不可或缺的。建立伦理指导方针和治理框架可以确保大语言模型符合社会价值观和民主原则 [[1](https://arxiv.org/html/2408.04643v1#bib.bib1)]。此外，Chu 等人提出了一种 softmax 回归方法，以帮助模型在训练和推理过程中避免生成版权数据 [[5](https://arxiv.org/html/2408.04643v1#bib.bib5)]。

### VI-D 安全数据处理

遵循行业最佳实践，如加密和访问控制，对于保护数据免受未经授权的访问至关重要。实施强大的加密协议可确保私密或敏感信息的安全存储和传输。此外，在与最终用户互动并管理其数据时，必须具备有效的同意管理程序，以透明地传达数据将如何收集和处理 [[23](https://arxiv.org/html/2408.04643v1#bib.bib23)]。

### VI-E 偏见检测与缓解

Fleisig 等人提出了一种对抗性学习方法，而 Dong 等人则使用了条件生成的探测框架来识别和解决性别偏见 [[12](https://arxiv.org/html/2408.04643v1#bib.bib12), [7](https://arxiv.org/html/2408.04643v1#bib.bib7)]。其他减轻偏见的技术包括预处理、数据过滤、提示修改和微调 [[35](https://arxiv.org/html/2408.04643v1#bib.bib35)]。例如，GPT-3.5-turbo 可以通过微调进一步去除偏见 [[35](https://arxiv.org/html/2408.04643v1#bib.bib35)]。此外，Huang 等人利用了少样本学习和链式思维（CoT）方法来减轻代码生成中的偏见 [[21](https://arxiv.org/html/2408.04643v1#bib.bib21)]。

### VI-F 可解释性与问责制

高度可解释的 LLM 更容易被最终用户接受 [[15](https://arxiv.org/html/2408.04643v1#bib.bib15)]。医学和科学领域需要高度可解释的 LLM 以确保其有效利用。LLM 的可解释性可以分为两种方法：局部和全局。局部可解释性侧重于解释单个输出，而全局可解释性旨在阐明整个 LLM [[46](https://arxiv.org/html/2408.04643v1#bib.bib46)]。局部方法，如基于扰动的方法、基于梯度的方法和线性近似，用于计算特征重要性。此外，计算 Shapley 值代表了 LLM 的一种独特归因方法 [[14](https://arxiv.org/html/2408.04643v1#bib.bib14)]。另一方面，全局解释方法包括探测和理解训练数据的分布 [[46](https://arxiv.org/html/2408.04643v1#bib.bib46)]。

### VI-G 使用参数高效模型

较大的模型通常比紧凑的模型更容易记住训练数据，这使得后者在某些场景中更为可取 [[3](https://arxiv.org/html/2408.04643v1#bib.bib3)]。例如，DistilBERT 是 BERT 模型的一个显著精简版，其参数减少了 40%，在各种 NLP 任务中表现出强大的性能，相比于其母模型 BERT [[37](https://arxiv.org/html/2408.04643v1#bib.bib37)]。值得注意的是，DistilBERT 保留了 BERT 97% 的理解能力，同时提供了显著更快的推理时间 [[37](https://arxiv.org/html/2408.04643v1#bib.bib37)]。像 DistilBERT 这样的较小模型更容易部署，成本更低，所需资源更少，从而有助于环境和财务的效率。此外，它们减少的记忆和过拟合倾向也降低了隐私和安全风险。此外，较小的模型通常更具可解释性，有助于更清晰地洞察模型决策过程。

## VII 结论

总结来说，我们的综述论文通过提供对部署风险的深入审查、识别潜在原因，并审查可行的缓解解决方案，为 LLM 的实施做出了宝贵贡献。研究突出了与 LLM 采用相关的各种风险，包括伦理、隐私、安全、偏见、环境和合规问题。我们分析了导致这些风险的因素，如模型过拟合、复杂架构、有限的意识、AI 伦理立法的不统一、不断变化的威胁环境和对数据质量的控制不足。为应对这些挑战，我们强调了主动措施，如构建稳健模型、采用隐私保护实践、实施监管合规措施、引入偏见检测机制、使用可解释性工具和采纳参数高效模型。通过应用这些建议，研究人员和相关方可以推动 LLM 的负责任发展和部署，从而提高可靠性、保护用户隐私、提升 AI 公平性，并减少环境影响。

## 参考文献

+   [1] A. Agiza, M. Mostagir, 和 S. Reda. 分析数据选择和微调对 LLM 中的经济和政治偏见的影响，2024 年。

+   [2] E. M. Bender, T. Gebru, A. McMillan-Major, 和 S. Shmitchell. 关于随机鹦鹉的危险：语言模型是否可以太大？在《2021 年 ACM 公平性、问责制和透明度会议论文集》，FAccT ’21，第 610–623 页，美国纽约，2021 年。计算机协会。

+   [3] N. Carlini, D. Ippolito, M. Jagielski, K. Lee, F. Tramer, 和 C. Zhang. 量化神经语言模型的记忆化，2023 年。

+   [4] I. Chalkidis, E. Fergadiotis, P. Malakasiotis, 和 I. Androutsopoulos. 大规模多标签文本分类在欧盟立法中的应用。在 A. Korhonen, D. Traum, 和 L. Màrquez 编辑的《第 57 届计算语言学协会年会论文集》，第 6314–6322 页，意大利佛罗伦萨，2019 年 7 月。计算语言学协会。

+   [5] T. Chu, Z. Song, 和 C. Yang. 如何在大型语言模型优化中保护版权数据？《美国人工智能协会会议论文集》，38(16):17871–17879，2024 年 3 月。

+   [6] L. De Angelis, F. Baglivo, G. Arzilli, G. P. Privitera, P. Ferragina, A. E. Tozzi, 和 C. Rizzo. ChatGPT 与大型语言模型的崛起：公共健康中新型 AI 驱动的信息疫情威胁。《公共健康前沿》，11:1166120，2023 年。

+   [7] X. Dong, Y. Wang, P. S. Yu, 和 J. Caverlee. 透露和缓解 LLM 中的性别偏见，2024 年。

+   [8] Z. Dong, Z. Zhou, C. Yang, J. Shao, 和 Y. Qiao. 关于 LLM 对话安全的攻击、防御和评估：综述，2024 年。

+   [9] T. Eloundou, S. Manning, P. Mishkin, 和 D. Rock. GPTs 就是 GPTs：大型语言模型对劳动力市场影响的初步研究，2023 年。

+   [10] A. Elrod. 揭示大型语言模型中的神学和伦理偏见：一种综合解释学方法，采用希伯来圣经文本。HIPHIL Novum，9(1):2–45，2024 年 2 月。

+   [11] A. Esmradi, D. W. Yip, 和 C. F. Chan. 大型语言模型中的攻击技术、实现和缓解策略的综合调查。收录于 G. Wang, H. Wang, G. Min, N. Georgalas, 和 W. Meng 主编的《无处不在的安全》，第 76–95 页，新加坡，2024 年。Springer Nature Singapore。

+   [12] E. Fleisig 和 C. Fellbaum. 通过对抗学习缓解机器翻译中的性别偏见，2022 年。

+   [13] L. Floridi 和 M. Chiriatti. GPT-3：其性质、范围、限制和后果。Minds and Machines，30:681–694，2020 年。

+   [14] C. Frye, D. de Mijolla, T. Begley, L. Cowton, M. Stanley, 和 I. Feige. 数据流形上的 Shapley 可解释性，2021 年。

+   [15] K. Fujiwara, M. Sasaki, A. Nakamura, 和 N. Watanabe. 测量五种大型语言模型的可解释性和可说明性。

+   [16] K. Greshake, S. Abdelnabi, S. Mishra, C. Endres, T. Holz, 和 M. Fritz. 不是你所期望的：通过间接提示注入破坏现实世界的大型语言模型集成应用。收录于《第 16 届 ACM 人工智能与安全研讨会论文集》，AISec ’23，第 79–90 页，美国纽约，2023 年。计算机协会。

+   [17] Y. Guo, Y. Yang, 和 A. Abbasi. 自动去偏：使用自动化偏见提示去除掩蔽语言模型的偏见。收录于 S. Muresan, P. Nakov, 和 A. Villavicencio 主编的《第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文）》，第 1012–1023 页，都柏林，爱尔兰，2022 年 5 月。计算语言学协会。

+   [18] M. Gupta, C. Akiri, K. Aryal, E. Parker, 和 L. Praharaj. 从 ChatGPT 到 ThreatGPT：生成式人工智能在网络安全和隐私中的影响。IEEE Access，11:80218–80245，2023 年。

+   [19] M. U. Hadi, R. Qureshi, A. Shah, M. Irfan, A. Zafar, M. B. Shaikh, N. Akhtar, J. Wu, S. Mirjalili 等人。大型语言模型：应用、挑战、限制和未来前景的综合调查。Authorea Preprints，2023 年。

+   [20] X. He, L. Lyu, L. Sun, 和 Q. Xu. 模型提取与对抗性转移，你的 BERT 易受攻击！收录于 K. Toutanova, A. Rumshisky, L. Zettlemoyer, D. Hakkani-Tur, I. Beltagy, S. Bethard, R. Cotterell, T. Chakraborty, 和 Y. Zhou 主编的《第 2021 届北美计算语言学协会会议：人类语言技术论文集》，第 2006–2012 页，在线，2021 年 6 月。计算语言学协会。

+   [21] D. Huang, Q. Bu, J. Zhang, X. Xie, J. Chen, 和 H. Cui. 基于大型语言模型的代码生成中的偏见测试与缓解，2024 年。

+   [22] P.-S. Huang, H. Zhang, R. Jiang, R. Stanforth, J. Welbl, J. Rae, V. Maini, D. Yogatama, 和 P. Kohli. 通过反事实评估减少语言模型中的情感偏见，2020 年。

+   [23] K. Hubert. 法规合规性与伦理考量：大数据与 AI 整合中的合规挑战与机遇，2024 年。

+   [24] T. Ishida, I. Yamane, T. Sakai, G. Niu, 和 M. Sugiyama. 在实现零训练错误后，我们还需要零训练损失吗？在 H. D. III 和 A. Singh 主编的《第 37 届国际机器学习会议论文集》中，机器学习研究第 119 卷，页面 4604–4614。PMLR，2020 年 7 月 13–18 日。

+   [25] D. Jin, Z. Jin, J. T. Zhou, 和 P. Szolovits. BERT 是否真的稳健？对文本分类和推理的自然语言攻击的强基线。在人工智能领域的 AAAI 会议论文集中，第 34 卷，页面 8018–8025，2020 年。

+   [26] E. Jo, D. A. Epstein, H. Jung, 和 Y.-H. Kim. 理解利用大型语言模型进行公共健康干预的对话 AI 的好处和挑战。在 2023 年 CHI 计算机系统人因会议论文集中，CHI ’23，纽约，NY，USA，2023 年。计算机协会。

+   [27] J. Kaddour, J. Harris, M. Mozes, H. Bradley, R. Raileanu, 和 R. McHardy. 大型语言模型的挑战与应用，2023 年。

+   [28] J. Kaplan, S. McCandlish, T. Henighan, T. B. Brown, B. Chess, R. Child, S. Gray, A. Radford, J. Wu, 和 D. Amodei. 神经语言模型的规模定律，2020 年。

+   [29] S. Katsarou, B. Rodríguez-Gálvez, 和 J. Shanahan. 测量上下文化嵌入中的性别偏差。计算机科学与数学论坛，3(1)，2022 年。

+   [30] S. Keele 等. 软件工程中的系统文献综述指南，2007 年。

+   [31] T. Le, N. Park, 和 D. Lee. SHIELD：使用随机多专家补丁器防御文本神经网络免受多重黑箱对抗攻击。在 S. Muresan, P. Nakov, 和 A. Villavicencio 主编的《第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文）》中，页面 6661–6674，爱尔兰都柏林，2022 年 5 月。计算语言学协会。

+   [32] L. Li, R. Ma, Q. Guo, X. Xue, 和 X. Qiu. BERT-ATTACK：使用 BERT 对抗 BERT 的对抗攻击。在 B. Webber, T. Cohn, Y. He, 和 Y. Liu 主编的《2020 年自然语言处理经验方法会议（EMNLP）》论文集中，页面 6193–6202，在线，2020 年 11 月。计算语言学协会。

+   [33] X. Li, F. Tramèr, P. Liang, 和 T. Hashimoto. 大型语言模型可以是强大的差分隐私学习者，2022 年。

+   [34] Y. Li, Z. Tan, 和 Y. Liu. 大型语言模型服务的隐私保护提示调整，2023 年。

+   [35] L. Lin, L. Wang, J. Guo, 和 K.-F. Wong. 调查基于 LLM 的偏差检测中的偏差：LLM 与人类感知之间的差异，2024 年。

+   [36] Q. Liu、R. Zheng、B. Rong、J. Liu、Z. Liu、Z. Cheng、L. Qiao、T. Gui、Q. Zhang 和 X. Huang. Flooding-X：通过损失限制微调提高 BERT 对抗性攻击的抵抗力。在 S. Muresan、P. Nakov 和 A. Villavicencio 主编的《第 60 届计算语言学协会年会论文集（第 1 卷：长论文）》中，第 5634–5644 页，2022 年 5 月，爱尔兰都柏林。计算语言学协会。

+   [37] V. Liu 和 Y. Yin. 绿色 AI：探索大型语言模型训练中的碳足迹、缓解策略和权衡。arXiv 预印本 arXiv:2404.01157，2024 年。

+   [38] OpenAI 和 J. A. 等人. GPT-4 技术报告，2024 年。

+   [39] X. Pan、M. Zhang、S. Ji 和 M. Yang. 通用语言模型的隐私风险。在 2020 年 IEEE 安全与隐私研讨会（SP）中，第 1314–1331 页，2020 年。

+   [40] P. S. Park、S. Goldstein、A. O’Gara、M. Chen 和 D. Hendrycks. AI 欺骗：实例、风险与潜在解决方案的调查，2023 年。

+   [41] M. C. Rillig、M. Ågerstrand、M. Bi、K. A. Gould 和 U. Sauerland. 大型语言模型对环境的风险与收益。《环境科学与技术》，57(9):3464–3466，2023 年。

+   [42] A. Schwarzschild、Z. Feng、P. Maini、Z. C. Lipton 和 J. Z. Kolter. 从对抗性压缩的角度重新思考大型语言模型的记忆化，2024 年。

+   [43] X. Shen、Z. Chen、M. Backes、Y. Shen 和 Y. Zhang. “现在做任何事”：对大型语言模型上的现实世界越狱提示进行特征化和评估，2023 年。

+   [44] J. Shi、Z. Yang 和 D. Lo. 面向软件工程的高效与绿色大型语言模型：愿景与未来道路，2024 年。

+   [45] W. Shi、R. Shea、S. Chen、C. Zhang、R. Jia 和 Z. Yu. 只需微调两次：大型语言模型的选择性差分隐私，2022 年。

+   [46] C. Singh、J. P. Inala、M. Galley、R. Caruana 和 J. Gao. 在大型语言模型时代重新思考可解释性，2024 年。

+   [47] K. Takeoka、K. Akimoto 和 M. Oyamada. 通过预训练语言模型进行低资源分类系统丰富化。M.-F. Moens、X. Huang、L. Specia 和 S. W.-t. Yih 主编，《2021 年自然语言处理经验方法会议论文集》，第 2747–2758 页，2021 年 11 月，在线及多米尼加共和国蓬塔卡纳。计算语言学协会。

+   [48] Y. Tal、I. Magar 和 R. Schwartz. 错误减少，但刻板印象增加？模型规模对性别偏见的影响，2022 年。

+   [49] Z. Tian、L. Cui、J. Liang 和 S. Yu. 机器学习中的中毒攻击及其对策的全面调查。《ACM 计算机调查》，55(8)，2022 年 12 月。

+   [50] H. Touvron、T. Lavril、G. Izacard、X. Martinet、M.-A. Lachaux、T. Lacroix、B. Rozière、N. Goyal、E. Hambro、F. Azhar、A. Rodriguez、A. Joulin、E. Grave 和 G. Lample. LLAMA：开放且高效的基础语言模型，2023 年。

+   [51] T. Trust, J. Whalen, 和 C. Mouza. 编辑部：Chatgpt：教师教育中的挑战、机遇和影响。技术与教师教育的当代问题，23(1):1–23，2023 年 3 月。

+   [52] B. Wang, S. Wang, Y. Cheng, Z. Gan, R. Jia, B. Li, 和 J. Liu. Infobert：从信息理论角度提高语言模型的鲁棒性，2021。

+   [53] Y. Wang, Y. Pan, M. Yan, Z. Su, 和 T. H. Luan. 关于 ChatGPT 的调查：AI 生成内容、挑战与解决方案。IEEE 计算机协会开放期刊，4(01):280–302，2023 年 1 月。

+   [54] X. Wu, R. Duan, 和 J. Ni. 揭示 ChatGPT 的安全、隐私和伦理问题。信息与智能期刊，2(2):102–115，2024。

+   [55] B. Yan, K. Li, M. Xu, Y. Dong, Y. Zhang, Z. Ren, 和 X. Cheng. 关于保护大型语言模型（llms）数据隐私的调查，2024。

+   [56] J. Yang, H. Jin, R. Tang, X. Han, Q. Feng, H. Jiang, S. Zhong, B. Yin, 和 X. Hu. 实践中利用 llms 的力量：ChatGPT 及其他的调查。ACM 知识发现与数据转化期刊，18(6)，2024 年 4 月。

+   [57] Y. Yao, J. Duan, K. Xu, Y. Cai, Z. Sun, 和 Y. Zhang. 关于大型语言模型（llm）安全与隐私的调查：好、坏与丑。高信度计算，4(2):100211，2024。

+   [58] J. Zeng, J. Xu, X. Zheng, 和 X. Huang. 通过随机化[MASK]认证文本对抗攻击的鲁棒性。计算语言学，49(2):395–427，2023 年 6 月。

+   [59] S. Zeng, J. Zhang, P. He, Y. Xing, Y. Liu, H. Xu, J. Ren, S. Wang, D. Yin, Y. Chang, 和 J. Tang. 好与坏：探讨检索增强生成（rag）中的隐私问题，2024。

+   [60] K. Zhou, Y. Zhu, Z. Chen, W. Chen, W. X. Zhao, X. Chen, Y. Lin, J.-R. Wen, 和 J. Han. 不要让你的 llm 成为评估基准作弊者，2023。

+   [61] Z. Zhou, J. Xiang, C. Chen, 和 S. Su. 量化和分析大型语言模型中的实体级记忆。人工智能协会会议论文集，38(17):19741–19749，2024 年 3 月。

生成于 2024 年 8 月 1 日周四 21:17:23，由 LaTeXML![吉祥物萨米](http://dlmf.nist.gov/LaTeXML/)
