<!--yml

category: 未分类

日期：2024-09-03 17:28:41

-->

# 《基于 LLM 的 AI 聊天机器人完整调查》

> 来源：[`arxiv.org/html/2406.16937`](https://arxiv.org/html/2406.16937)

1.  [I 引言](https://arxiv.org/html/2406.16937v1#S1 "在《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [I-A 现有调查、评论和案例研究](https://arxiv.org/html/2406.16937v1#S1.SS1 "在 I 引言 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [I-B 我们的贡献](https://arxiv.org/html/2406.16937v1#S1.SS2 "在 I 引言 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

1.  [II 概述](https://arxiv.org/html/2406.16937v1#S2 "在《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [II-A 预 LLM 时代的聊天机器人](https://arxiv.org/html/2406.16937v1#S2.SS1 "在 II 概述 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [II-B 大型语言模型（LLMs）](https://arxiv.org/html/2406.16937v1#S2.SS2 "在 II 概述 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [II-C 基于 LLM 的聊天机器人](https://arxiv.org/html/2406.16937v1#S2.SS3 "在 II 概述 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

1.  [III 应用](https://arxiv.org/html/2406.16937v1#S3 "在《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [III-A 教育](https://arxiv.org/html/2406.16937v1#S3.SS1 "在 III 应用 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [III-B 研究](https://arxiv.org/html/2406.16937v1#S3.SS2 "在 III 应用 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [III-C 医疗](https://arxiv.org/html/2406.16937v1#S3.SS3 "在 III 应用 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [III-D 杂项应用](https://arxiv.org/html/2406.16937v1#S3.SS4 "在 III 应用 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

1.  [IV 开放挑战](https://arxiv.org/html/2406.16937v1#S4 "在《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [IV-A 从技术角度](https://arxiv.org/html/2406.16937v1#S4.SS1 "在 IV 开放挑战 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [IV-B 从伦理角度](https://arxiv.org/html/2406.16937v1#S4.SS2 "在 IV 开放挑战 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [IV-C 从误用角度](https://arxiv.org/html/2406.16937v1#S4.SS3 "在 IV 开放挑战 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

1.  [V 未来展望](https://arxiv.org/html/2406.16937v1#S5 "在《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [V-A 技术改进](https://arxiv.org/html/2406.16937v1#S5.SS1 "在 V 未来展望 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

    1.  [V-B 道德指南与负责任的使用](https://arxiv.org/html/2406.16937v1#S5.SS2 "在 V 未来展望 ‣ 《基于 LLM 的 AI 聊天机器人完整调查》中")

1.  [VI 结论](https://arxiv.org/html/2406.16937v1#S6 "在《基于 LLM 的 AI 聊天机器人完整调查》中")

\UseTblrLibrary

booktabs, caption

# 《基于 LLM 的 AI 聊天机器人完整调查》

Sumit Kumar Dam, Choong Seon Hong, Yu Qiao,

和张超宁、Sumit Kumar Dam、洪忠善、乔宇及张超宁在韩国京畿道龙仁市 17104 的庆熙大学计算机学院工作（电子邮件：skd160205@khu.ac.kr；cshong@khu.ac.kr；qiaoyu@khu.ac.kr；chaoningzhang1990@gmail.com）。(Sumit Kumar Dam 和洪忠善对这项工作贡献相同。)(通讯作者：张超宁。)

###### 摘要

过去几十年见证了数据的激增，这为数据需求巨大的学习型 AI 技术奠定了基础。对话代理，通常称为 AI 聊天机器人，严重依赖这些数据来训练大型语言模型（LLMs）并生成新的内容（知识）以响应用户的提示。随着 OpenAI 的 ChatGPT 的出现，基于 LLM 的聊天机器人在 AI 社区中树立了新的标准。本文全面调查了 LLM 基于聊天机器人的发展与应用。我们首先总结了基础聊天机器人的发展，然后是 LLM 的演变，再提供了目前在用和开发阶段的基于 LLM 的聊天机器人的概述。我们将 AI 聊天机器人视为生成新知识的工具，探索它们在各个行业中的多样化应用。随后，我们讨论了开放性挑战，考虑到用于训练 LLM 的数据以及生成知识的误用可能引发的多个问题。最后，我们探讨了未来展望，以提高它们在众多应用中的效率和可靠性。通过探讨关键的里程碑和基于 LLM 的聊天机器人的现状，我们的调查邀请读者深入这个领域，反思下一代将如何重塑对话 AI。

###### 索引词：

大型语言模型，聊天机器人，知识，数据，ChatGPT

## I 引言

最近几年数据的指数增长改变了数字信息的世界。在 2023 年，全球创建、捕获、复制和消耗的数据总量达到了约 120 兹字节，预计到 2024 年将达到 147 兹字节，并有望在 2025 年超过 180 兹字节 [[1](https://arxiv.org/html/2406.16937v1#bib.bib1)]。图 [1](https://arxiv.org/html/2406.16937v1#S1.F1 "Figure 1 ‣ I Introduction ‣ A Complete Survey on LLM-based AI Chatbots") 说明了

![请参阅说明](img/6e77ac034d4249f615bfff25d2e39b9a.png)

图 1：数据量随时间的增长 [[1](https://arxiv.org/html/2406.16937v1#bib.bib1)]。

从 2010 年到 2023 年数据量的增加，以及 2024 年和 2025 年的预测值。这种数据生态系统的快速扩展为人工智能（AI）开创性创新铺平了道路，导致了多个机器学习模型的开发。其中，大型语言模型（LLMs）由于其卓越的理解、生成和操控人类语言的能力 [[2](https://arxiv.org/html/2406.16937v1#bib.bib2)]，已成为一个突出的子集 [[3](https://arxiv.org/html/2406.16937v1#bib.bib3)]。

![参见说明](img/99ec0ee794bf03ab1a7a9ff9407d39ab.png)

图 2：Google 搜索兴趣随时间变化 [[4](https://arxiv.org/html/2406.16937v1#bib.bib4)]。

表 I：聊天机器人文献总结

{tblr}

width = colspec = —Q[c,m,0.0663]—Q[c,m,0.05427]—Q[c,m,0.05427]—Q[c,m,0.1064]—Q[c,m,0.1064]—Q[c,m,0.0555]—Q[c,m,0.0555]—Q[c,m,0.0555]—Q[j,m,0.2272]—, row1 = font=, c, row1-16 = font=, hlines, cell12 = c=2, cell22 = c=1halign=c,valign=m, cell23 = c=1halign=c,valign=m, cell14 = c=2, cell24 = c=1halign=c,valign=m, cell25 = c=1halign=c,valign=m, cell16 = c=3, cell26 = c=1halign=c,valign=m, cell27 = c=1halign=c,valign=m, cell28 = c=1halign=c,valign=m, cell11 = r=2halign=c,valign=m, cell19 = r=2halign=c,valign=m, 参考文献 & \SetCell[c=2]c 覆盖的聊天机器人 \SetCell[c=2]c 应用范围 \SetCell[c=3]c 讨论的挑战 备注

单一 多重 单学科 多学科 技术 伦理 误用

[[5](https://arxiv.org/html/2406.16937v1#bib.bib5)] - - ✔ ✔ • 将讨论限制在 ChatGPT 上，没有提及其他聊天机器人如 BARD、Bing Chat 等。

• 忽视了技术问题。

[[6](https://arxiv.org/html/2406.16937v1#bib.bib6)] - - ✔ ✔ • 未涉及技术问题。

• 探讨了用户体验下的伦理问题和误用案例，结果内容欠缺。

[[7](https://arxiv.org/html/2406.16937v1#bib.bib7)] - - ✔ • 对技术问题和误用案例的讨论不足，缺乏深度和细节。

[[8](https://arxiv.org/html/2406.16937v1#bib.bib8)] - - ✔ ✔ ✔ • 缺乏对关键问题的结构化分类，导致读者难以找到具体信息。

[[9](https://arxiv.org/html/2406.16937v1#bib.bib9)] - - • 仅考虑了 ChatGPT 的初始版本（v3.5）。

• 缺乏对教育问题的分类和深度讨论。

[[10](https://arxiv.org/html/2406.16937v1#bib.bib10)] - - • 缺乏对各个领域应用和挑战的分类。

[[11](https://arxiv.org/html/2406.16937v1#bib.bib11)] - - ✔ ✔ ✔ • 过于依赖叙述内容，缺乏分析深度。

• 缺乏足够的视觉辅助（例如图形、图表、条形图等），使数据解读变得复杂，减少了读者的参与感。

[[12](https://arxiv.org/html/2406.16937v1#bib.bib12)] - - ✔ ✔ ✔ • 包含了来自 43 位专家的重叠见解，导致文档杂乱且过长。

[[13](https://arxiv.org/html/2406.16937v1#bib.bib13)] - - ✔ ✔ ✔ •  缺乏对应用和挑战的细粒度分类。

[[14](https://arxiv.org/html/2406.16937v1#bib.bib14)] - - •  缺乏对关键问题的讨论。

我们的调查 - - ✔ ✔ ✔ •  涵盖了 ChatGPT 之外的广泛聊天机器人，包括 BARD、Bing Chat、Claude 等。

•  提供了应用和挑战的详细分类，每个分类都分为不同的子类别。

* ✔（完全讨论）；  （部分讨论）；  （未讨论）； - （不适用）；

* （单一聊天机器人或单学科）；  （两个聊天机器人或两个学科）；

* （三个聊天机器人或三个学科）；  （超过三个聊天机器人或超过三个学科）。

在 AI 驱动的聊天机器人时代 [[15](https://arxiv.org/html/2406.16937v1#bib.bib15)、[16](https://arxiv.org/html/2406.16937v1#bib.bib16)、[17](https://arxiv.org/html/2406.16937v1#bib.bib17)]，大语言模型（LLM）在推动聊天功能和促进类似人类的互动方面发挥了重要作用 [[2](https://arxiv.org/html/2406.16937v1#bib.bib2)、[7](https://arxiv.org/html/2406.16937v1#bib.bib7)]。数据的大幅增长和计算知识的进步提升了基于 LLM 的聊天机器人的功能，使其在各个领域越来越受欢迎并被广泛采用。它们以前所未有的上下文相关性和准确性理解和回应人类语言，加上处理大量信息流的能力，使其在教育 [[18](https://arxiv.org/html/2406.16937v1#bib.bib18)、[19](https://arxiv.org/html/2406.16937v1#bib.bib19)、[20](https://arxiv.org/html/2406.16937v1#bib.bib20)]、研究 [[21](https://arxiv.org/html/2406.16937v1#bib.bib21)、[22](https://arxiv.org/html/2406.16937v1#bib.bib22)、[23](https://arxiv.org/html/2406.16937v1#bib.bib23)]、医疗 [[24](https://arxiv.org/html/2406.16937v1#bib.bib24)、[25](https://arxiv.org/html/2406.16937v1#bib.bib25)、[8](https://arxiv.org/html/2406.16937v1#bib.bib8)] 及其他多个领域 [[26](https://arxiv.org/html/2406.16937v1#bib.bib26)、[27](https://arxiv.org/html/2406.16937v1#bib.bib27)、[28](https://arxiv.org/html/2406.16937v1#bib.bib28)] 中成为不可或缺的工具。鉴于基于 LLM 的聊天机器人的巨大潜力和令人鼓舞的前景，它们的使用增加和优化需求带来了许多挑战，这些挑战需要进行深入的研究和评估。随着基于 LLM 的聊天机器人领域迅速扩展，这些需求变得更加明显，导致了学者、专业人士和新手面临的研究文献的数量庞大。因此，我们的工作提供了一个及时且全面的基于 LLM 的聊天机器人的调查，以应对这些不断发展的需求。

在 LLM 和基于 LLM 的聊天机器人出现之前，对话式 AI 面临着若干挑战。早期的聊天机器人具有有限的上下文理解能力和领域特异性，常常提供不准确的回答。缺乏复杂的语言理解限制了它们以类似人类的方式互动的能力，导致了机械和支离破碎的用户体验。跨行业的可扩展性也是一个问题，因为处理大量信息流并实时响应具有挑战性。LLM 的出现彻底改变了聊天机器人，开启了 AI 驱动互动的新纪元。2023 年 3 月，OpenAI 发布了其最新的奇迹 GPT-4（也称为 ChatGPT Plus [[29](https://arxiv.org/html/2406.16937v1#bib.bib29)]），继 ChatGPT 3.5 在 2022 年 11 月首次亮相后的轰动效应 [[30](https://arxiv.org/html/2406.16937v1#bib.bib30)，[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]。图[2](https://arxiv.org/html/2406.16937v1#S1.F2 "Figure 2 ‣ I Introduction ‣ A Complete Survey on LLM-based AI Chatbots")展示了 ChatGPT（以蓝色标出）自初次发布以来人气的指数增长，突显了其在 5G（以黄色标出）、物联网（以绿色标出）和区块链（以红色标出）等广泛技术中的主导地位。其创新能力迎来了前所未有的人气激增，标志着 AI 驱动通信的新篇章。在相关发展中，谷歌于 2 月 6 日宣布了其首个基于 LLM 的聊天机器人 BARD [[32](https://arxiv.org/html/2406.16937v1#bib.bib32)]，并于 3 月 21 日提供了早期访问 [[33](https://arxiv.org/html/2406.16937v1#bib.bib33)]。此外，还有许多其他基于 LLM 的聊天机器人正在开发中。鉴于这些技术的深远影响，本调查旨在提供基于 LLM 的聊天机器人的精炼、最新概述，包括其发展、行业应用、主要挑战和提高其有效性及可靠性的策略。我们的目标是将这些不同的研究整合成一个组织良好的综述，以促进对基于 LLM 的聊天机器人的深入理解，并为未来的研究提供指导。

### I-A 现有的调查、综述和案例研究

一些文章已经回顾了基于 LLM 的聊天机器人的广泛应用，突显了它们的重大影响以及它们在各个领域所带来的复杂挑战。在这里，我们讨论了一些这些文章，并展示了我们的调查如何扩展和不同于它们。

[[5](https://arxiv.org/html/2406.16937v1#bib.bib5)] 探讨了 AI 和聊天机器人在学术领域中的应用及其对研究和教育的伦理影响。它调查了这些技术对教育评估诚信的影响及其变革学术研究的潜力。此外，它建议了有效的解决方案，以缓解这些工具在教育和研究领域中的伦理挑战和可能的误用。[[6](https://arxiv.org/html/2406.16937v1#bib.bib6)] 对 ChatGPT 如何提升在线学习进行了案例研究。研究结果表明，学生们偏爱这些工具用于教育活动，认为其提供了更加互动和引人入胜的学习环境。Koubaa 等人 [[7](https://arxiv.org/html/2406.16937v1#bib.bib7)] 对 ChatGPT 的技术创新进行了详细的回顾。接着，他们在调查中开发了一个独特的分类法用于研究分类，并探索了 ChatGPT 在各个领域的应用。此外，他们还突出了显著的挑战和未来的研究方向。[[8](https://arxiv.org/html/2406.16937v1#bib.bib8)] 提供了对 ChatGPT 在医疗保健领域的系统评审，重点关注教育、研究和实践。作者概述了 ChatGPT 在科学写作和个性化学习中的潜力。该评审批判性地分析了其好处，同时承认了诸如伦理和准确性问题等显著担忧。另一篇综述文章 [[9](https://arxiv.org/html/2406.16937v1#bib.bib9)] 评估了 ChatGPT 对教育的影响，指出其在经济学、编程、法律、医学教育和数学等学科中的表现差异。论文强调了这一工具的潜力和挑战，如准确性问题和剽窃，建议更新评估方法和教育政策以实现负责任的使用。在 [[10](https://arxiv.org/html/2406.16937v1#bib.bib10)] 中，作者通过虚拟和面对面的反馈进行了一项探索性调查，分析了 ChatGPT 在教育、医疗保健和研究中的影响。调查展示了 ChatGPT 如何改善个性化学习、临床任务和研究效率。他们还讨论了主要的伦理和实际问题，建议在有力的伦理准则指导下谨慎部署 AI 以应对这些挑战。在类似的背景下，[[11](https://arxiv.org/html/2406.16937v1#bib.bib11)] 提供了对 ChatGPT 的全面分析，重点关注其演变、多样化的应用和关键挑战。与[[10](https://arxiv.org/html/2406.16937v1#bib.bib10)] 采用直接反馈的调查不同，[[11](https://arxiv.org/html/2406.16937v1#bib.bib11)] 汇总了现有研究的发现，以评估 ChatGPT 的影响和挑战，提供了一个更为概括的视角，而没有进行初级数据收集。进一步探讨，[[12](https://arxiv.org/html/2406.16937v1#bib.bib12)] 和 [[13](https://arxiv.org/html/2406.16937v1#bib.bib13)] 深入研究了 ChatGPT 的更广泛的跨学科应用。[[12](https://arxiv.org/html/2406.16937v1#bib.bib12)] 汇集了多个学科的见解，以评估其在营销、教育和医疗保健等领域的影响，而 [[13](https://arxiv.org/html/2406.16937v1#bib.bib13)] 引入了 ChatGPT 研究的分类法，详细描述了其在医疗保健、金融和环境科学等领域的应用。此外，这两篇论文还讨论了有关伦理考虑和实际部署的基本挑战。另一篇最近的文章 [[14](https://arxiv.org/html/2406.16937v1#bib.bib14)] 使用单案例研究方法评估了 ChatGPT 和 Bing Chat 在化学教育中的有效性。研究分析了这两个工具与模拟学生之间的广泛互动，以改善创造力、问题解决和个性化学习。研究结果显示，这两个聊天机器人作为有价值的“思考伙伴”发挥了作用。然而，ChatGPT 在提供更全面和上下文准确的响应方面明显优于 Bing Chat。

与现有工作不同，我们的调查扩展了对具体聊天机器人的典型关注，例如 ChatGPT，涵盖了包括 BARD、Bing Chat 和 Claude 在内的广泛模型。此外，我们探讨了多个领域的应用，并讨论了各种挑战，每个挑战都在几个子类别中详细说明。表 [I](https://arxiv.org/html/2406.16937v1#S1.T1 "TABLE I ‣ I Introduction ‣ A Complete Survey on LLM-based AI Chatbots") 总结了讨论文章的发现，便于比较理解它们的贡献。

![参见说明](img/8c01abb8518c0e53801f2c6001715acb.png)

图 3：调查大纲。

### I-B 我们的贡献

我们的调查旨在回答以下问题：

+   •

    聊天机器人是如何从简单的自动化系统演变为我们今天看到的 LLM 基础变体的？LLM 的哪些基础进展自预 LLM 时代以来重新定义了聊天机器人的能力？

+   •

    LLM（大型语言模型）基础的聊天机器人在不同领域中的关键应用是什么？它们如何影响这些领域中的操作动态和用户互动？

+   •

    LLM 基础聊天机器人的广泛使用带来了哪些挑战？这些挑战如何影响它们的性能和可靠性？

+   •

    对于 LLM 基础聊天机器人而言，哪些技术改进是至关重要的？实施伦理准则将如何确保其负责任的使用？

针对这些问题，我们提供了聊天机器人历史的全面概述。此外，我们讨论了 LLM 的基础，重点介绍了基于变换器的自注意力机制以及 GPT 模型中的创新特性，如上下文学习和思维链（CoT）提示。接着，我们提供了 LLM 基础聊天机器人的详细分类，按照其功能和在教育、研究和医疗等领域的应用进行组织。我们还承认它们在软件工程和金融领域日益增长的重要性。接下来，我们从技术方面探讨了开放挑战，包括从知识时效性到幻觉的问题，以及数据透明性、偏见、隐私风险和不公平等伦理考量。然后，我们从误用的角度进行总结，重点关注学术误用、过度依赖和错误信息传播等问题。最后，我们讨论了 LLM 基础聊天机器人的未来展望，从技术改进如模型优化到遵守伦理准则以及在各个领域推广负责任的使用。我们的贡献总结如下：

+   •

    与大多数集中于特定聊天机器人或其有限方面的文章不同，我们的调查涵盖了各种 LLM 基础模型，包括 ChatGPT、BARD、Bing Chat 以及其他许多模型。

+   •

    虽然大多数文章集中于应用于一个或多个领域的单一聊天机器人，且没有详细分类，我们的调查扩展到各种应用领域的广泛聊天机器人。我们提供了详细的应用分类，结构化地深入探讨了不同聊天机器人在教育、研究、医疗保健、软件工程和金融等行业中的表现。

+   •

    我们讨论了从技术、伦理和滥用角度的几个开放挑战。此外，我们围绕知识和数据这两个 LLM 的核心支柱展开讨论。这种方法展示了聊天机器人与大量训练数据互动以及随后生成新内容（知识）之间的动态互动。

调查的其余部分组织如下：第[II](https://arxiv.org/html/2406.16937v1#S2 "II Overview ‣ A Complete Survey on LLM-based AI Chatbots")节涵盖了聊天机器人的基础年、LLM 的崛起以及基于 LLM 的聊天机器人的概述。第[III](https://arxiv.org/html/2406.16937v1#S3 "III Applications ‣ A Complete Survey on LLM-based AI Chatbots")节突出显示了这些聊天机器人在教育、研究和医疗保健中的应用。还包括软件工程和金融等其他应用。第[IV](https://arxiv.org/html/2406.16937v1#S4 "IV Open Challenges ‣ A Complete Survey on LLM-based AI Chatbots")节深入探讨了这些聊天机器人固有的挑战，而第[V](https://arxiv.org/html/2406.16937v1#S5 "V Future Outlook ‣ A Complete Survey on LLM-based AI Chatbots")节则探索了该领域的未来前景。最后，第[VI](https://arxiv.org/html/2406.16937v1#S6 "VI Conclusion ‣ A Complete Survey on LLM-based AI Chatbots")节总结了调查的关键发现和总体贡献。我们的调查大纲如图[3](https://arxiv.org/html/2406.16937v1#S1.F3 "Figure 3 ‣ I-A Existing Surveys, Reviews, and Case Studies ‣ I Introduction ‣ A Complete Survey on LLM-based AI Chatbots")所示。

## II 概述

在本节中，我们深入探讨了聊天机器人的演变，从其起源到现代时代。图中的维恩图[4](https://arxiv.org/html/2406.16937v1#S2.F4 "Figure 4 ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots")展示了早期聊天机器人、LLM 的发展以及代表该技术前沿的基于 LLM 的聊天机器人之间的关系。我们首先回顾聊天机器人的前 LLM 时代，以了解该领域的早期发展。接下来，我们介绍了大型语言模型（LLMs），解释它们对聊天机器人技术的变革性影响。最后，我们概述了基于 LLM 的聊天机器人，突出了行业中的领军者以及当前在开发中的机器人。

![参见说明](img/163c223f9575f7f7c8435cf574419b20.png)

图 4：前 LLM 聊天机器人遇见 LLMs。

### II-A 前 LLM 时代的聊天机器人

![参见图例](img/ce0d582c088b140234fcd1c12af5ccf3.png)

图 5: 早期的聊天机器人。

聊天机器人起源于 1950 年的一个简单想法：“机器能思考吗？”这个被称为图灵测试的想法由艾伦·图灵提出[[34](https://arxiv.org/html/2406.16937v1#bib.bib34), [35](https://arxiv.org/html/2406.16937v1#bib.bib35)]。测试中，一名人类参与者与一个看不见的个体进行文字对话，尝试预测这个个体是机器还是另一个人类。这成为了聊天机器人的基础。多年来，聊天机器人发生了很多变化，如今它们使用复杂的高级计算机程序，称为大型语言模型（LLMs），以更加复杂的方式与我们互动。现在，在这一小节中，我们首先讨论大型语言模型到来之前的聊天机器人时代。

1960–1980: 早期基础。这个时期出现了几个聊天机器人。其中之一是 1966 年在 MIT 开发的 ELIZA。它模拟了一个罗杰斯式心理治疗师，通过关键字识别和模式匹配进行功能操作，但它并不理解输入的含义[[36](https://arxiv.org/html/2406.16937v1#bib.bib36)]。尽管其功能原始且知识库有限，ELIZA 因其能让用户相信其具有人类特质，甚至形成情感联系而受到关注，这也引发了一些伦理问题[[37](https://arxiv.org/html/2406.16937v1#bib.bib37)]。另一个早期的聊天机器人 PARRY，创建于 1972 年，被设计用来模拟一个有偏执型精神分裂症的人[[38](https://arxiv.org/html/2406.16937v1#bib.bib38)]。它甚至可以与 ELIZA 聊天，并被视为向前迈出的一步，因为它能够展示更受控的结构和情感反应[[39](https://arxiv.org/html/2406.16937v1#bib.bib39), [40](https://arxiv.org/html/2406.16937v1#bib.bib40)]。

1981–2009 年：进展与主流整合。在此期间，聊天机器人变得更加先进。1984 年，Racter 作为一种人工智能程序出现，能够生成英文散文并模仿聊天机器人的对话行为[[41](https://arxiv.org/html/2406.16937v1#bib.bib41)]。与此同时，另一个人工智能项目 Jabberwacky 于 1988 年启动。它旨在以友好的方式模拟休闲的人类对话[[42](https://arxiv.org/html/2406.16937v1#bib.bib42)]。它通过与人类的互动不断发展，从对话中存储关键短语以增强其知识库，然后利用来自动态扩展数据库的上下文感知算法选择相关回复[[43](https://arxiv.org/html/2406.16937v1#bib.bib43), [44](https://arxiv.org/html/2406.16937v1#bib.bib44)]。1990 年代带来了进一步的创新，Creative Labs 的 Dr. Sbaitso 是为 MS-DOS 计算机设计的聊天机器人。它配合当时的多个声卡，提供了一个简单的交互界面，具有蓝色背景和白色文本。然而，它在早期文本转语音技术的利用方面具有创新性，通过语音合成和声卡实现了这一点[[45](https://arxiv.org/html/2406.16937v1#bib.bib45)]。然后，在 1995 年，美国科学家 Richard S. Wallace 创建了 A.L.I.C.E.（人工语言互联网计算实体），也被称为 Alicebot 或简单地叫 Alice。它通过利用大幅扩展的知识库和采用人工智能标记语言（AIML）建立聊天指南，为聊天机器人技术带来了新能力[[46](https://arxiv.org/html/2406.16937v1#bib.bib46)]。ELIZA 是 Alice 开发的灵感来源。Alice 首次亮相时因其能力获得了极大的赞誉，并在 2000 年代三次获得 Loebner 奖[[47](https://arxiv.org/html/2406.16937v1#bib.bib47)]。然而，由于某些限制，它未能通过图灵测试[[48](https://arxiv.org/html/2406.16937v1#bib.bib48)]。在此基础上，2001 年见证了另一项重大进展，当时 ActiveBuddy 在 AIM 平台上推出了 SmarterChild。这是最早帮助用户处理日常任务如天气更新和股票价格查询的聊天机器人之一[[49](https://arxiv.org/html/2406.16937v1#bib.bib49)]。继续发展聊天机器人，2008 年英国人工智能科学家 Rollo Carpenter 推出了 Cleverbot。它是 1988 年聊天机器人 Jabberwacky 的继任者。Cleverbot 独特的策略是从人类输入中学习，而不是依赖预编程的回应，这使它相对于其他聊天机器人具有独特的优势。此外，Cleverbot 在 2011 年 Techniche 节的正式图灵测试中表现出色，获得了 59.3%的类人评分，考虑到人类参与者的评分略高于 63.3%，这是一个值得注意的结果[[50](https://arxiv.org/html/2406.16937v1#bib.bib50)]。

2010–2016: 智能语音助手的时代。2011 年，IBM 推出了 Watson，这是一种对话 AI，在《危险边缘》竞赛节目中两次获胜。继成功之后，Watson 在医疗行业找到了很多应用[[51](https://arxiv.org/html/2406.16937v1#bib.bib51), [52](https://arxiv.org/html/2406.16937v1#bib.bib52)]。然后，在 2014 年，微软推出了 XiaoICE [[53](https://arxiv.org/html/2406.16937v1#bib.bib53)]。这个基于情感计算框架的聊天机器人能够处理智力和情感方面的查询。微软同一团队还创建了另一个聊天机器人，名为 Tay。Tay 于 2016 年首次出现在 Twitter 上。然而，在推出不久后，Tay 开始发布攻击性推文，迫使微软在发布后仅十六小时内关闭了它。在此期间，聊天机器人的集成通过即时消息应用和各种平台上的语音和搜索代理变得更加突出[[54](https://arxiv.org/html/2406.16937v1#bib.bib54), [55](https://arxiv.org/html/2406.16937v1#bib.bib55)]。苹果公司于 2010 年率先进行了这一集成，推出了 Siri，这款 iOS 应用到 2011 年成为 iOS 系统的一部分。作为个人助手，Siri 可以通过语音命令执行一系列任务，例如打电话、设置提醒和收集信息[[56](https://arxiv.org/html/2406.16937v1#bib.bib56)]。随后，在 2012 年，谷歌推出了 Google Now，将语音输入转化为搜索结果。然后微软于 2014 年推出了 Windows 平台上的 Cortana，利用 Bing 处理用户查询。同年，亚马逊发布了 Alexa 和 Echo 扬声器。随后在 2016 年，谷歌进一步推进了领域，推出了 Google Assistant，后者后来被集成到 Google Home 扬声器和 Pixel 智能手机中。尽管这些语音助手提供了快速的互联网连接响应，但它们在多语言支持、隐私和安全方面存在一些问题[[57](https://arxiv.org/html/2406.16937v1#bib.bib57)]。

表 II: LLMs 概述

|  | 数据集 | 参数 | 上下文窗口 |
| --- | --- | --- | --- |
| GPT-1 |

&#124; BooksCorpus &#124;

&#124; (4.5GB) &#124;

| 1.17 亿 | 512 个 token |
| --- | --- |
| BERT |

&#124; BooksCorpus，&#124;

&#124; 英语维基百科 &#124;

&#124; (大小: 无) &#124;

|

&#124; BERT-Base: 1.1 亿 &#124;

&#124; BERT-Large: 3.4 亿 &#124;

| 512 个 token |
| --- |
| GPT-2 |

&#124; Webtext &#124;

&#124; (40GB) &#124;

| 15 亿 | 1024 个 token |
| --- | --- |
| GPT-3 |

&#124; Common Crawl &#124;

&#124; (45TB) &#124;

| 1750 亿 | 2048 个 token |
| --- | --- |
| GPT-3.5 | 无 | 无 | 2048 个 token |
| PaLM |

&#124; 网页，书籍，新闻，&#124;

&#124; 社交媒体对话，&#124;

&#124; 维基百科，Github &#124;

&#124; (大小: 无) &#124;

|

&#124; 5400 亿 &#124;

&#124; 较小版本：&#124;

&#124; 800 万和 620 亿 &#124;

| 无 |
| --- |
| LLaMA |

&#124; Common Crawl，C4，&#124;

&#124; 书籍，Github，维基百科 &#124;

&#124; ArXiv，Stack Exchange &#124;

&#124; (大小: 不适用) &#124;

|

&#124; 6.7, 13, 32.5, &#124;

&#124; 和 65.2 亿 &#124;

| 2048 tokens |
| --- |
| GPT-4 | 不适用 | 不适用 | 8195 tokens |
| PaLM 2 |

&#124; 20 编程, &#124;

&#124; 语言, 超过 100 种 &#124;

&#124; 口语语言, 数学 &#124;

&#124; 和科学文本 &#124;

&#124; (大小: 不适用) &#124;

| 340 亿 | 8000 tokens |
| --- | --- |
| LLaMA 2 |

&#124; 公开数据混合 &#124;

&#124; 可用的在线资源 &#124;

&#124; (大小: 不适用) &#124;

|

&#124; 7, 13, 和 &#124;

&#124; 70 亿 &#124;

| 4096 tokens |
| --- |

图 [5](https://arxiv.org/html/2406.16937v1#S2.F5 "Figure 5 ‣ II-A Pre-LLM Era of Chatbots ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots") 提供了至今提到的所有聊天机器人的完整时间线。现在，尽管这些进展贯穿了几十年，但新的聊天机器人时代始于 2020 年，随着 LLMs 的崛起 [[58](https://arxiv.org/html/2406.16937v1#bib.bib58), [59](https://arxiv.org/html/2406.16937v1#bib.bib59)]。通过在大量预训练变换器上的广泛训练，LLMs 使聊天机器人能够提供更详细和细致的回应。接下来的部分将讨论这些 LLMs 以及基于这种技术构建的流行 AI 驱动聊天机器人。

### II-B 大型语言模型（LLMs）

LLMs 的出现彻底改变了自然语言处理领域，特别是聊天机器人的发展和功能。在这里，我们讨论 LLMs 的世界，提供它们的架构、工作原理、在聊天机器人中的应用、优点和局限性的概述。

基于 LLM 的聊天机器人，如 ChatGPT 和 BARD，最近在媒体[[60](https://arxiv.org/html/2406.16937v1#bib.bib60), [61](https://arxiv.org/html/2406.16937v1#bib.bib61), [62](https://arxiv.org/html/2406.16937v1#bib.bib62)]、政策制定者[[63](https://arxiv.org/html/2406.16937v1#bib.bib63), [64](https://arxiv.org/html/2406.16937v1#bib.bib64), [65](https://arxiv.org/html/2406.16937v1#bib.bib65)]和各领域学者[[11](https://arxiv.org/html/2406.16937v1#bib.bib11), [8](https://arxiv.org/html/2406.16937v1#bib.bib8), [66](https://arxiv.org/html/2406.16937v1#bib.bib66), [67](https://arxiv.org/html/2406.16937v1#bib.bib67)]中获得了广泛赞誉。LLM，通常称为变换器语言模型，经过大量文本数据训练，包含数十亿个参数。第一个引起人们注意的 LLM 是 OpenAI 的 GPT[[68](https://arxiv.org/html/2406.16937v1#bib.bib68)]，即生成预训练变换器，发布于 2018 年。自那时以来，我们见证了更大、更复杂的语言模型的发展，包括 GPT-2[[69](https://arxiv.org/html/2406.16937v1#bib.bib69)]、GPT-3[[3](https://arxiv.org/html/2406.16937v1#bib.bib3)]、GPT-3.5[[70](https://arxiv.org/html/2406.16937v1#bib.bib70)]以及最新的 GPT-4[[29](https://arxiv.org/html/2406.16937v1#bib.bib29)]，以及其他模型如 BERT[[71](https://arxiv.org/html/2406.16937v1#bib.bib71)]、PaLM[[72](https://arxiv.org/html/2406.16937v1#bib.bib72)]和 LLaMA[[73](https://arxiv.org/html/2406.16937v1#bib.bib73)]。表格[II](https://arxiv.org/html/2406.16937v1#S2.T2 "TABLE II ‣ II-A Pre-LLM Era of Chatbots ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots")概述了这些 LLM，而图[6](https://arxiv.org/html/2406.16937v1#S2.F6 "Figure 6 ‣ II-B Large Language Models (LLMs) ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots")展示了它们的发展时间线。目前，编码器-解码器、因果解码器和前缀解码器是构建 LLM 的三种基本变换器架构类型。

香草变换器模型，由 Vaswani 等人[[74](https://arxiv.org/html/2406.16937v1#bib.bib74)]在其论文《Attention is All You Need》中提出，建立在编码器-解码器架构之上。编码器生成输入数据的抽象表示，并通过一系列具有多头自注意力机制的层，关注输入序列的不同部分。

![参见说明](img/96e23c32f6febcb4b0d89a2646f01285.png)

图 6：LLM 的时间线。

解码器然后自回归地生成输出序列，使用这些表示上的交叉注意力（见图[7](https://arxiv.org/html/2406.16937v1#S2.F7 "Figure 7 ‣ II-B Large Language Models (LLMs) ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots")）。GPT 系列模型[[3](https://arxiv.org/html/2406.16937v1#bib.bib3), [75](https://arxiv.org/html/2406.16937v1#bib.bib75)]使用自回归或因果解码器架构，并配备单向注意力掩码，这样每个输入令牌在处理时只考虑之前出现的元素和自身（见图[8](https://arxiv.org/html/2406.16937v1#S2.F8 "Figure 8 ‣ II-B Large Language Models (LLMs) ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots")）。这使得处理更像自然对话的流动。输入和输出令牌在这一框架中经历类似的处理。非因果或前缀解码器架构[[76](https://arxiv.org/html/2406.16937v1#bib.bib76)]对前缀令牌执行双向注意力，即考虑前后令牌。在自回归预测输出令牌时使用相同的编码参数集，它执行单向注意力[[77](https://arxiv.org/html/2406.16937v1#bib.bib77), [78](https://arxiv.org/html/2406.16937v1#bib.bib78)]。

LLM 的工作原理包括一系列步骤。过程始于词嵌入，即将单词表示为高维空间中的向量。在这里，相似的单词被聚集在特定的组或类别中。这种单词的聚类使模型能够理解其含义，从而帮助 LLM 做出准确的预测。模型在大量文本语料库（如新闻文章或书籍）上进行训练，在训练过程中，它学习预测单词在特定上下文中出现的可能性。位置编码进一步增加了对序列中单词顺序的理解，这对于翻译、摘要和问答等任务至关重要。接下来是这些模型的核心，即 Transformer 架构。它由自注意力机制组成

![参见标题](img/06c0b15ad967871ed1517e84976506e3.png)

图 7：Transformer 模型架构[[74](https://arxiv.org/html/2406.16937v1#bib.bib74)]。

![参见标题](img/49ca38420e75ec77bdf29f378ee0f237.png)

图 8：GPT 系列中的 Transformer 模型架构[[68](https://arxiv.org/html/2406.16937v1#bib.bib68)]。

它通过为单词分配不同的权重来帮助理解文本依赖关系。这是通过计算实现的：

|  | $Attention(Q,K,V)=softmax(\frac{QK^{T}}{\sqrt{d_{k}}})V=AV,$ |  | (1) |
| --- | --- | --- | --- |

其中矩阵 Q（查询）、K（键）和 V（值）分别代表当前元素、其他元素和需要聚合的信息。查询和键矩阵之间的相似度通过点积操作计算。然后通过 $\frac{1}{\sqrt{d_{k}}}$ 进行缩放，以防止梯度消失问题，随后使用 SoftMax 激活函数进行归一化，生成注意力矩阵 A。通过对 A 和 V 进行矩阵乘法得到更新后的表示。这种加权值的聚合形成了一个新的表示，捕捉了文本中的固有关联。算法 [1](https://arxiv.org/html/2406.16937v1#alg1 "Algorithm 1 ‣ II-B Large Language Models (LLMs) ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots") 描述了自注意力机制的逐步过程。最后，模型使用自回归方法生成与给定提示相关的文本，其中模型一次生成一个单词来构建输出序列。通过人类反馈的强化学习（RLHF）的整合进一步增强了 LLMs 从人类互动中学习的能力，不断优化其性能。

算法 1 自注意力机制

0: 矩阵 $Q$（查询）、$K$（键）、$V$（值）0: 矩阵 $Z$（更新后的表示）1: 计算查询与键的点积：$D\leftarrow QK^{T}$2: 缩放点积：$D\leftarrow D/\sqrt{d_{k}}$3: 应用 SoftMax 归一化：$A\leftarrow\text{SoftMax}(D)$4: 计算值的加权和：$Z\leftarrow AV$5: 返回 $Z$

在 GPT-3 [[3](https://arxiv.org/html/2406.16937v1#bib.bib3)] 中引入的上下文学习（ICL）功能使 LLMs 能够在对话上下文中理解和回应新信息，而无需额外的训练。LLMs 可以遵循输入文本的指令，并尽可能地产生符合这些指令的输出。通过指令调整（一个微调过程），LLMs 在多任务数据集的混合上进一步训练，每个数据集都附带自然语言指令，这增强了模型在类似指令描述的不熟悉任务上的泛化能力 [[79](https://arxiv.org/html/2406.16937v1#bib.bib79), [80](https://arxiv.org/html/2406.16937v1#bib.bib80), [81](https://arxiv.org/html/2406.16937v1#bib.bib81)]。与小型语言模型不同，LLMs 可以通过使用一种称为链式思维（CoT）提示的策略来处理涉及多个推理步骤的复杂任务 [[82](https://arxiv.org/html/2406.16937v1#bib.bib82)]。这一策略帮助 LLMs 概述达到最终解决方案所需的中间步骤。换句话说，与其一步到位地从问题跳到解决方案，CoT 提示将任务分解成多个部分，LLMs 可以依次解决，从而得到最终解决方案。

尽管大型语言模型（LLMs）能够有效生成连贯的文本，但它们缺乏语义理解。这是因为它们并不真正理解内容。它们只是根据从训练数据中学到的知识预测后续的文本。LLMs 还可以处理和生成多语言文本，只要有足够的多语言训练数据。然而，不同语言的熟练程度因数据的质量和数量而异。此外，还有其他一些局限性。例如，它们偶尔会产生幻觉 [[29](https://arxiv.org/html/2406.16937v1#bib.bib29), [83](https://arxiv.org/html/2406.16937v1#bib.bib83), [84](https://arxiv.org/html/2406.16937v1#bib.bib84)]，即响应中包含事实错误，或在某些情况下可能被认为是有风险的。在生成具有复杂结构约束的文本时，LLMs 展现了在局部规划方面的卓越能力。也就是说，它们可以有效地处理紧邻句子之间的互动。然而，它们可能在全球规划或维持长篇文本的连贯性和相关性方面存在困难 [[85](https://arxiv.org/html/2406.16937v1#bib.bib85)]。

总之，LLMs 通过提供强大的理解和生成类似人类文本的能力，已经改变了自然语言处理的格局。尽管取得了显著进展，但仍存在一些局限性。为了确保它们在各个领域的伦理和适当应用，我们必须在前进的过程中不断改进它们。

### II-C 基于 LLM 的聊天机器人

高级聊天机器人的发展得益于 LLMs。如今市场上提供了各种各样的聊天机器人，其中 ChatGPT 处于领先地位。在这里，我们讨论了目前使用的聊天机器人以及那些正在开发中的聊天机器人。

ChatGPT。2022 年 11 月，我们见证了 ChatGPT 的出现，这是一款由 OpenAI 开发的 AI 聊天机器人 [[86](https://arxiv.org/html/2406.16937v1#bib.bib86)]。它属于更大的生成预训练变换器（GPT）家族，具体来说是 GPT-3.5 的微调版本 [[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]。ChatGPT 利用大量互联网文本数据进行训练，能够对众多提示和询问生成类似人类的回复。在相对较短的时间内，ChatGPT 因其在多个主题上提供连贯且令人信服的真实响应而获得广泛赞誉。在 ChatGPT 取得前所未有的成功之后，OpenAI 于去年 3 月 14 日发布了 GPT-4 [[87](https://arxiv.org/html/2406.16937v1#bib.bib87)]。GPT-4 是 GPT 系列的第四个也是最新的版本，同时也是 ChatGPT Plus 的基础架构。

BARD。自发布以来，ChatGPT 对搜索引擎产生了巨大的影响，以至于 Google 针对其出现宣布了“代码红色”[[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]。鉴于 ChatGPT 的潜力，Google 推出了 BARD，这是一个面向公众的 LLM 合作生成 AI 用户界面。BARD 于去年 2 月 6 日推出，并于 3 月 21 日向公众开放[[33](https://arxiv.org/html/2406.16937v1#bib.bib33)]。它使用了 LaMDA（对话应用的语言模型）的优化变体，经过广泛公开资源的预训练。在发布时，ChatGPT 和 BARD 之间的主要区别之一是，ChatGPT 的回应无法使用最新信息，因为其知识局限于 2021 年的数据，而 BARD 则利用了更多的最新信息[[88](https://arxiv.org/html/2406.16937v1#bib.bib88)]。然而，自去年 9 月以来，ChatGPT 也获得了搜索最新内容的能力[[89](https://arxiv.org/html/2406.16937v1#bib.bib89)]，并通过更新的知识库增强了包括 2023 年 4 月的信息[[90](https://arxiv.org/html/2406.16937v1#bib.bib90)]。不过，Google 还进一步解决了准确性、偏见和漏洞等领域的持续研究和改进问题。值得注意的是，截至 2024 年 2 月 8 日，Google 已将 BARD 更名为‘Gemini’[[91](https://arxiv.org/html/2406.16937v1#bib.bib91)]。本调查主要引用了 2023 年的出版物，当时该平台被普遍认知为 BARD。因此，本文件中提到的所有 BARD 均指现在称为 Gemini 的聊天机器人。

Bing Chat。去年 2 月 7 日，紧接着 Google 宣布 BARD，微软推出了 Bing Chat[[92](https://arxiv.org/html/2406.16937v1#bib.bib92)]。它是由 GPT-4 驱动的搜索引擎功能，让用户可以与 AI 聊天机器人互动，而不是手动输入搜索查询。在发布时，Bing Chat 相较于 ChatGPT 等竞争对手具有显著优势，因为它提供了实时互联网访问和引用支持的回应，使用户能够验证信息的真实性[[93](https://arxiv.org/html/2406.16937v1#bib.bib93), [94](https://arxiv.org/html/2406.16937v1#bib.bib94)]。值得注意的是，Bing Chat 还通过提供用户可选择的回应风格如‘更多创意’，‘更多平衡’，或‘更精准’，根据用户的查询提供定制化的互动[[95](https://arxiv.org/html/2406.16937v1#bib.bib95)]。

Claude。Anthropic 的 Claude 第一次迭代，版本 1.0，于去年 3 月 14 日发布，同时推出了简化版 Claude Instant 1.1 [[96](https://arxiv.org/html/2406.16937v1#bib.bib96)]。随后在 7 月 11 日发布了更高级的 Claude 2，并在 8 月 9 日推出了 Claude Instant 的第二次迭代，版本 1.2 [[97](https://arxiv.org/html/2406.16937v1#bib.bib97)]。然后，Claude 2.1 于 11 月 21 日发布 [[97](https://arxiv.org/html/2406.16937v1#bib.bib97)]。尽管 Claude Instant 比其他两个模型稍快且更轻便，但 Claude 2 以其全面的推理能力和更安全的响应而脱颖而出。这是通过由 Anthropic 研究人员开发的宪法人工智能（constitutional AI）细化过程实现的 [[98](https://arxiv.org/html/2406.16937v1#bib.bib98)]。然而，Claude 2 的知识库包含的数据截至 2022 年，且无法连接互联网。因此，它缺乏此后时期的实时数据 [86]。Claude 2 的另一个关键特点是其 100,000 个标记的广泛上下文窗口，大约 75,000 个词，这使得用户能够对大型文档进行深入分析 [[98](https://arxiv.org/html/2406.16937v1#bib.bib98), [99](https://arxiv.org/html/2406.16937v1#bib.bib99), [100](https://arxiv.org/html/2406.16937v1#bib.bib100)]。

Ernie Bot。百度的 Ernie（通过知识整合增强表示）首次于去年 3 月 16 日发布 [[101](https://arxiv.org/html/2406.16937v1#bib.bib101)]。它也被称为文心一言（语言与思想合一）。Ernie 通过大量的数据进行训练，包括数万亿的网页，数十亿的语音数据，搜索数据，图像数据，以及包含 5500 亿事实的知识图谱，这是一个令人印象深刻的成就 [[102](https://arxiv.org/html/2406.16937v1#bib.bib102)]。尽管在早期测试中出现了一些幻觉和基础数学错误的问题，Ernie 已显示出阅读各种中文方言文本的能力 [[103](https://arxiv.org/html/2406.16937v1#bib.bib103)]。百度计划将 Ernie 集成到其众多产品中，包括自动驾驶汽车和其主要搜索引擎 [[102](https://arxiv.org/html/2406.16937v1#bib.bib102)]。百度的战略可能并不旨在与 ChatGPT 直接竞争，而是为了在 ChatGPT 当前不可用的国内市场建立主导地位 [[104](https://arxiv.org/html/2406.16937v1#bib.bib104)]。

![参见标题](img/fb19989a347e27d3af17a86107c8ad87.png)

图 9：基于 LLM 的聊天机器人时间线。

除了这五种之外，还有其他多个聊天机器人也在开发中，像 DeepMind 的 Sparrow [[105](https://arxiv.org/html/2406.16937v1#bib.bib105)] 和 xAI 的 Grok [[106](https://arxiv.org/html/2406.16937v1#bib.bib106), [107](https://arxiv.org/html/2406.16937v1#bib.bib107)] 等有前景的候选者。图 [9](https://arxiv.org/html/2406.16937v1#S2.F9 "Figure 9 ‣ II-C LLM-based Chatbots ‣ II Overview ‣ A Complete Survey on LLM-based AI Chatbots") 展示了所有这些聊天机器人的视觉时间轴。Meta 也有一个名为 BlenderBot 的聊天机器人 [[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]。然而，用户发现与 BlenderBot 的互动有些乏味，这可能是因为开发者对其输出的严格限制，限制了聊天机器人的创造力，降低了用户满意度 [[108](https://arxiv.org/html/2406.16937v1#bib.bib108)]。尽管如此，随着我们见证这一快速进展，持续研究、跨学科合作和伦理规范的开发实践变得至关重要。在创新与伦理考虑之间取得平衡，将是确保这些工具负责任利用的关键。

## III 应用

与传统的聊天机器人仅限于基本对话框架不同，基于大语言模型（LLM）的聊天机器人已成为生成知识的新方式。由于这种新角色，它们已成为各个领域的重要组成部分，重新塑造了行业如何运作以及与客户互动。在教育、研究和医疗等领域，这些聊天机器人提供了极大的效率、准确性和个性化参与。现在，在这一部分，我们将深入探讨基于 LLM 的聊天机器人的多种应用，突显它们在不同领域的深远影响。

### III-A 教育

基于 LLM 的聊天机器人在教育领域带来了显著的提升。在这里，我们总结了这些智能系统如何为教育卓越和改善学习成果提供独特的机会。

学习。基于 LLM 的聊天机器人在 K-12、本科和研究生阶段都有巨大的潜力，在这些教育层次中可以发挥各种支持性作用，增强这些教育层次的学习体验。例如，[[109](https://arxiv.org/html/2406.16937v1#bib.bib109)]的一项研究探讨了 ChatGPT 和必应聊天在 STEM 教育中的有前景的途径。该研究表明，这些聊天机器人作为“用于思考的对象”可以改变 STEM 教育，鼓励积极参与，并培养用户友好的环境。随后，另一项研究[[110](https://arxiv.org/html/2406.16937v1#bib.bib110)]调查了三种 SOTA LLMs，ChatGPT、必应聊天和 BARD，在满足越南学生教育需求方面的表现。该研究使用越南国家高中毕业考试（VNHSGE）数据集[[111](https://arxiv.org/html/2406.16937v1#bib.bib111)]对学生在九个科目的学术成绩进行了比较分析。尽管所有的聊天机器人表现相当，但必应聊天在大多数科目上都表现更有优势。它在数学、英语、物理、历史和公民教育方面取得了显著的成绩，准确率分别为 60%、92.4%、66%、88.5%和 85.5%。BARD 在化学、生物和地理等科目中表现也相当不错，准确率分别为 73%、69.5%和 82%。相比之下，ChatGPT 只在文学方面表现出色，准确率为 68%，但在其他科目上得分较低。除此之外，GPT-4 的元提示功能允许在对话过程中进行角色定制，比如选择“苏格拉底导师模式”来增强学生的批判性思维和问题解决能力[[112](https://arxiv.org/html/2406.16937v1#bib.bib112)]。类似的方法也可以在 ChatGPT Turbo 中看到，其功能包括“数学导师”、“创意写作教练”、“数据分析”等，为用户提供定制化的学习体验[[113](https://arxiv.org/html/2406.16937v1#bib.bib113)]。

学术写作。2020 年国家科学基金会科学与工程指标强调了国际学者在美国博士后项目中的重要贡献，近 49%的博士后来自海外。在数学和工程领域，国际学生获得 60%的博士学位 [[114](https://arxiv.org/html/2406.16937v1#bib.bib114)]。因此，有效的学术写作对研究出版物的质量和成功至关重要。然而，对于许多国际博士后和学生来说，掌握学术写作仍然是一个巨大的挑战。对此，ChatGPT 通过修正标点、拼写和语法错误显著提升了用户体验，这进而提高了内容质量和个人写作技能 [[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]。此外，ChatGPT 还帮助用户发展独特的写作风格。例如，它提供风格建议，提高内容深度，并为读者打造引人入胜的最终产品 [[115](https://arxiv.org/html/2406.16937v1#bib.bib115)]。

教学。基于大型语言模型的聊天机器人也可以作为教师的助手。[[6](https://arxiv.org/html/2406.16937v1#bib.bib6)] 中指出，ChatGPT 可以成为教师的有价值工具，通过提供结构化的大纲帮助他们制定课程。[[9](https://arxiv.org/html/2406.16937v1#bib.bib9)] 的研究确定了 ChatGPT 在两个主要类别中的五个关键角色：协助教学准备（如创建课程材料、提供建议和进行语言翻译）和帮助评估（例如制定评估任务和评分学术表现）。表[III](https://arxiv.org/html/2406.16937v1#S3.T3 "TABLE III ‣ III-A Education ‣ III Applications ‣ A Complete Survey on LLM-based AI Chatbots") 说明了 ChatGPT 在支持教师教学任务方面的实用性。另一个研究 [[116](https://arxiv.org/html/2406.16937v1#bib.bib116)] 表明，ChatGPT 有效地创建了一个统计学课程的本科大纲，只需稍作调整，这进一步证明了其有用性和精确性。继这一趋势之后，知名在线教育平台可汗学院目前正在探索将如 GPT-4 等人工智能工具集成到其“Khanmingo”项目中，以改善电子学习 [[117](https://arxiv.org/html/2406.16937v1#bib.bib117)]，而 Duolingo 已经在使用 GPT-4 来增强语言学习中的角色扮演互动 [[118](https://arxiv.org/html/2406.16937v1#bib.bib118)]。

表 III：人工智能在教育支持中的能力

{tblr}

width = colspec = —Q[c,m,0.14]—Q[c,m,0.19]—Q[c,m,0.42]—, row1 = font=, c, row1-6 = font=, hlines, cell21 = r=3halign=c,valign=m, cell51 = r=2halign=c,valign=m, Aspect & Function Representative Quote

协助教学准备 创建课程材料 ‘我们要求 ChatGPT 为 DialogFlow 集成格式化对话，它成功地提供了所需的格式’ [[119](https://arxiv.org/html/2406.16937v1#bib.bib119)]。

提供建议 ‘在得知有学习困难的学习者时，ChatGPT 推荐了适当的学习资源’ [[120](https://arxiv.org/html/2406.16937v1#bib.bib120)]。

提供语言翻译 ‘ChatGPT 能够将教育内容翻译成不同的语言’ [[18](https://arxiv.org/html/2406.16937v1#bib.bib18)]。

帮助评估 制定评估任务 ‘ChatGPT 的一个显著应用在于其生成课堂使用的实际练习和测试的能力’ [[121](https://arxiv.org/html/2406.16937v1#bib.bib121)]。

评分 学术表现 ‘ChatGPT 可以评估学生的论文，这使得教师能够将更多的注意力放在其他职责上’ [[121](https://arxiv.org/html/2406.16937v1#bib.bib121)]。

除了我们迄今讨论的内容外，基于 LLM 的聊天机器人还通过许多其他创新方法改变教育。例如，它们提供语法练习、互动讨论、即时反馈，并协助翻译，从而提高语言流利度和理解能力。它们还可以帮助学生提高阅读技能。 [[122](https://arxiv.org/html/2406.16937v1#bib.bib122)] 展示了 LLM 如何协助复杂文本的总结和对单词及短语的解释，以便学生理解即使是微妙的含义。此外，这些聊天机器人与语音转文本和文本转语音工具的集成有可能使视力障碍学习者受益 [[122](https://arxiv.org/html/2406.16937v1#bib.bib122)]。总之，基于 LLM 的聊天机器人代表了教育发展中的一个重要里程碑，提供了多样化和创新的解决方案，增强了学习体验，满足了个体需求，并为更具活力的学习环境铺平了道路。

### III-B 研究

以下讨论探讨了基于 LLM 的聊天机器人如何为学术研究开辟新途径，涵盖了从文献综述和释义到先进的数据分析技术和增强的创意生成过程。

文献综述和改写。全面的文献综述对研究人员来说可能是一个耗时且费力的任务。例如，AI 驱动的 Semantic Scholar 搜索引擎已索引了惊人的**2 亿**篇学术出版物。在这样浩瀚的信息海洋中，找到相关的研究论文并提取关键见解可能像是在大海捞针。ChatGPT 通过在给定主题上寻找相关文献，简化了对大量论文的探索 [[123](https://arxiv.org/html/2406.16937v1#bib.bib123)]。此外，类似于 SciSpace Copilot，ChatGPT 还可以用多种语言解释科学文献和数学，这有助于更好地理解研究文章 [[123](https://arxiv.org/html/2406.16937v1#bib.bib123)]。此外，作为一个多功能的语言模型，ChatGPT 在各种自然语言处理任务中扩展了其实用性。例如，在最近的一项研究 [[124](https://arxiv.org/html/2406.16937v1#bib.bib124)] 中，ChatGPT 在改写与“医疗保健中的数字双胞胎”相关的摘要方面显示出有希望的结果。然而，其在文献综述中的应用仍处于初级阶段。虽然 ChatGPT 的文献综述能力正在发展，但其提高研究人员效率和专注于核心研究的潜力备受期待。另一篇最近的论文 [[21](https://arxiv.org/html/2406.16937v1#bib.bib21)] 探讨了使用 Google BARD 生成文献综述。作者从 Google Scholar 中收集了近年来（2021–2023）发表的十篇 Metaverse 文章，并使用 BARD 改写它们的摘要。随后，作者询问 Google BARD，“什么是 Metaverse？”所有文本随后都通过 iThenticate 抄袭检查器进行了审查。虽然结果令人鼓舞，但作者观察到改写的文本显示出**12%**的抄袭匹配率，这比 BARD 在回应 Metaverse 查询时观察到的**1%**的抄袭匹配率要高得多。尽管如此，这项实验突显了基于 LLM 的聊天机器人潜力，表明它们在学术研究中的重要性日益增加。

数据分析。准备和组织科学数据以供分析的过程可能是一个耗时的任务，通常需要几个月的时间。此外，研究人员还需要掌握如 Python 或 R 等编程技能。将 ChatGPT 集成到数据处理中的转型变化，提高了研究效率和方法。例如，[[22](https://arxiv.org/html/2406.16937v1#bib.bib22)] 中的一项研究显示，ChatGPT 能够高效处理一个包含 100,000 名具有不同年龄和风险档案的医疗工作者的模拟数据集。另一篇最近的文章[[125](https://arxiv.org/html/2406.16937v1#bib.bib125)] 证明了基于 LLM 的聊天机器人，如 ChatGPT 3.5 和 4，可以有效地使用 Pandas DataFrame Agent 进行基本数据汇总任务。这些模型可以回答基本的探索性数据分析（EDA）问题，如识别最高平均价格的日期或确定两个变量之间的相关性。然而，它们有时会在生成有意义的上下文时遇到困难，例如产生不合理的重叠时间段。尽管存在这些局限性，ChatGPT 4 在通过提示工程和价值链分析工作流生成有关投资机会、风险和服务的宝贵见解方面显示了显著的潜力。挑战在于用户上传大量数据，如财报电话会议记录和年度报告，导致数据流和延迟问题，通常会引发运行时错误。一种实际的解决方案是将文档分成多个部分，并使用内存缓冲区来汇总响应。此外，通过自定义代理整合来自多个来源的文本和数值数据，可以增强聊天机器人的上下文理解能力，提供更深入的见解。

创意生成。研究的一个基本组成部分是批判性思维和生成创新想法的能力。基于 LLM 的聊天机器人可以通过作为先进的创意生成工具来帮助学生和教师进行研究。[[23](https://arxiv.org/html/2406.16937v1#bib.bib23)] 证明了 ChatGPT 在研究中的重要作用，从激发创意生成到提供扩展现有想法的建议。[[126](https://arxiv.org/html/2406.16937v1#bib.bib126)] 进一步说明了 ChatGPT 如何从多个角度提供见解，探讨 COVID-19 大流行的后果，分析其对医疗系统、社会经济影响和个人健康实践的多维度效果。这种从不同视角分析问题的能力有助于生成全面且多角度的想法。

在 2022 年之前，人们认为人工智能最适合处理简单任务，创造性工作的领域仍将掌握在人类手中。尽管这些工具并非总是准确，但它们的无偏见方法在研究的各个方面带来了显著的改善，有时在创造力方面甚至超过了普通人。

### III-C 医疗保健

在这里，我们总结了基于 LLM 的聊天机器人如何重塑医疗领域，提供先进的支持以解决复杂的医学问题、患者护理和治疗建议。

问答系统。基于大型语言模型（LLM）的聊天机器人一个关键亮点是其庞大的知识库，这在医疗领域的自动问答系统中尤为明显。例如，[[127](https://arxiv.org/html/2406.16937v1#bib.bib127)] 显示了 ChatGPT 处理美国医学执照考试（USMLE）第一步和第二步考试问题的能力。研究然后将 ChatGPT 的回答与 InstructGPT 和 GPT-3 的回答进行比较，其中 ChatGPT 的表现平均比 InstructGPT 高出 8.15%，而 GPT-3 的回答则不够一致。ChatGPT 还显示出类似于三年级医学生的及格水平。另一项研究 [[128](https://arxiv.org/html/2406.16937v1#bib.bib128)] 评估了 Claude 和 ChatGPT 3.5 在使用 MIMIC-III 临床笔记（来自 TREC CDS 2016 主题 [[129](https://arxiv.org/html/2406.16937v1#bib.bib129)]）回答临床问题的能力。研究随后在准确性、一致性、相关性和覆盖面等方面对这些回答进行了比较。Kruskal-Wallis 方差分析 [[130](https://arxiv.org/html/2406.16937v1#bib.bib130)] 进一步验证了这些发现。结果表明，Claude 和 ChatGPT 3.5 都能有效回答基于入院记录的临床问题，在各种情况下提供准确、相关和清晰的回答。另一篇近期文章 [[131](https://arxiv.org/html/2406.16937v1#bib.bib131)] 调查了 ChatGPT 和 Bing Chat（GPT-4）对房颤（AF）患者和临床医生问题的回应。作者准备了十八个以患者为中心的提示，并咨询了 AF 管理方面的专家，同时准备了另外十八个以临床医生为中心的提示。结果显示，ChatGPT 准确回答了 83.3% 的患者查询。对于以临床医生为基础的提示，ChatGPT 和 Bing Chat 显示文本准确率分别为 33.3% 和 66.6%，参考文献的准确率分别为 55.5% 和 50%。

患者教育。在最近的发展中，GPT-4 和 Med-PaLM 2 在健康评估中表现出了显著的效果，标志着患者护理技术领域的重大进展 [[112](https://arxiv.org/html/2406.16937v1#bib.bib112), [132](https://arxiv.org/html/2406.16937v1#bib.bib132)]。一项研究 [[133](https://arxiv.org/html/2406.16937v1#bib.bib133)] 展示了大型语言模型如何提供个性化的患者教育，提高了理解和参与度。一个最近的例子是 Macy，一款 AI 药剂师。它使用 ChatGPT 作为其基础架构，并配备了一个逼真的虚拟形象进行用户互动。Macy 成功地在不到 30 分钟的时间内以实惠的成本提供了关于主要症状、剂量和注意事项的药物指导 [[134](https://arxiv.org/html/2406.16937v1#bib.bib134)]。

治疗建议。基于 LLM 的聊天机器人也可以协助提供治疗建议。研究[[135](https://arxiv.org/html/2406.16937v1#bib.bib135)]评估了 ChatGPT 与国家综合癌症网络（NCCN）乳腺癌、前列腺癌和肺癌治疗指南的一致性。作者为 26 种癌症诊断开发了四个零样本提示模板，共生成了 104 个没有正确答案示例的提示。四名经过认证的肿瘤科医生使用五种不同标准评估了 ChatGPT 对 NCCN 指南的符合度，得出总分为 520。肿瘤科医生对 61.9%（520 分中的 322 分）的评分达成一致。这些结果表明，约三分之二的 ChatGPT 治疗建议与既定的 NCCN 指南一致，突显了其在医疗指导中的潜在有效性。另一项研究[[136](https://arxiv.org/html/2406.16937v1#bib.bib136)]评估了 ChatGPT-3.5、ChatGPT-4 和 Google BARD 在利用 25 个神经退行性疾病案例的总结预测神经病理学诊断的能力。这些总结均来自梅奥诊所脑库临床病理会议。聊天机器人提供了多个诊断和理由，随后与实际诊断进行比较。ChatGPT-3.5、ChatGPT-4 和 Google BARD 的初步诊断准确率分别为 32%、52%和 40%，而正确诊断的比例分别为 76%、84%和 76%。这强调了基于 LLM 的聊天机器人在神经病理学中的潜力。另一项类似的研究[[137](https://arxiv.org/html/2406.16937v1#bib.bib137)]评估了 ChatGPT 3.5、Google BARD（实验版）和 Bing Chat（精准版）在回答生理学案例小节中的能力。两名生理学家准备了 77 个案例小节，另外两位专家进行了验证。随后，两名生理学家对聊天机器人的回答进行 0-4 分的评分，反映从基础到高级的学习成果。ChatGPT 的得分最高，为 3.19±0.3，其次是 BARD 的 2.91±0.5 和 Bing 的 2.15±0.6，表明 ChatGPT 在这一背景下表现优越。此外，还有一篇文章[[138](https://arxiv.org/html/2406.16937v1#bib.bib138)]评估了 ChatGPT-3.5、ChatGPT-4 和 Google BARD 在回应近视相关问题中的表现。研究涉及 31 个近视相关问题，这些问题被分为六个领域：诊断、临床表现、发病机制、风险因素、治疗与预防以及预后。三名儿科眼科医生对每个聊天机器人的回答进行三点评分（良好、边缘、差），最终分数通过多数共识确定。‘良好’的回答进一步在五点评分中进行深度评估，而‘差’的回答则被要求自我改进并重新评估准确性。ChatGPT-4 显示出更高的准确性，其‘良好’回答的比例为 80.6%，而 ChatGPT-3.5 为 61.3%，Google BARD 为 54.8%。在全面性方面，三款聊天机器人均表现出较高的平均分，其中 Google BARD 得分 4.35，ChatGPT-4 得分 4.23，ChatGPT-3.5 得分 4.11（满分 5）。它们也展现了显著的自我修正能力。ChatGPT-4 中 66.7%、ChatGPT-3.5 中 40%和 Google BARD 中 60%的回答在修正后有所提高。此外，所有聊天机器人在每个领域表现一致，ChatGPT-4 在‘治疗与预防’方面表现出色，获得了 70%的‘良好’评分，明显高于 ChatGPT-3.5 的 40%和 Google BARD 的 45%。

表 IV: 不同领域的基于 LLM 的聊天机器人

{tblr}

width = colspec = —Q[c,m,0.085]—Q[c,m,0.085]—Q[c,m,0.397]—Q[c,m,0.0655]—Q[c,m,0.0655]—Q[c,m,0.0655]—Q[c,m,0.0655]—, row1 = font=, c, row1-31 = font=, hlines, cell21 = r=7halign=c,valign=m, cell91 = r=7halign=c,valign=m, cell161 = r=8halign=c,valign=m, cell241 = r=4halign=c,valign=m, cell281 = r=4halign=c,valign=m, 部门 & 参考文章 主要目标 ChatGPT BARD Bing Chat 其他聊天机器人

教育 [[109](https://arxiv.org/html/2406.16937v1#bib.bib109)] 转变 STEM 教育 ✔ - ✔ - [[110](https://arxiv.org/html/2406.16937v1#bib.bib110)] 满足越南学生的教育需求 ✔ ✔ ✔ - [[31](https://arxiv.org/html/2406.16937v1#bib.bib31)] 提升国际学者的学术写作技能 ✔ - - - [[115](https://arxiv.org/html/2406.16937v1#bib.bib115)] 协助发展独特且吸引人的写作风格 ✔ - - - [[6](https://arxiv.org/html/2406.16937v1#bib.bib6)] 辅助课程设计 ✔ - - - [[9](https://arxiv.org/html/2406.16937v1#bib.bib9)] 协助教学准备和评估任务 ✔ - - - [[116](https://arxiv.org/html/2406.16937v1#bib.bib116)] 为本科统计课程草拟教学大纲 ✔ - - - 研究 [[123](https://arxiv.org/html/2406.16937v1#bib.bib123)] 查找相关文献 ✔ - - - [[124](https://arxiv.org/html/2406.16937v1#bib.bib124)] 改写摘要 ✔ - - - [[21](https://arxiv.org/html/2406.16937v1#bib.bib21)] 生成文献综述 - ✔ - - [[22](https://arxiv.org/html/2406.16937v1#bib.bib22)] 处理模拟数据集 ✔ - - - [[125](https://arxiv.org/html/2406.16937v1#bib.bib125)] 协助数据分析任务 ✔ - - - [[23](https://arxiv.org/html/2406.16937v1#bib.bib23)] 协助新想法的生成 ✔ - - - [[126](https://arxiv.org/html/2406.16937v1#bib.bib126)] 从各个维度分析 COVID-19 的影响 ✔ - - - 医疗 [[127](https://arxiv.org/html/2406.16937v1#bib.bib127)] 回答 USMLE 问题 ✔ - - ✔

[[128](https://arxiv.org/html/2406.16937v1#bib.bib128)] 回答临床问题 ✔ - - ✔

[[131](https://arxiv.org/html/2406.16937v1#bib.bib131)] 解答有关房颤的问题 ✔ - ✔ - [[134](https://arxiv.org/html/2406.16937v1#bib.bib134)] 开创智能机器人辅助 ✔ - - - [[135](https://arxiv.org/html/2406.16937v1#bib.bib135)] 提供癌症治疗建议 ✔ - - - [[136](https://arxiv.org/html/2406.16937v1#bib.bib136)] 预测神经病理诊断 ✔ ✔ - - [[137](https://arxiv.org/html/2406.16937v1#bib.bib137)] 解答生理学案例片段 ✔ ✔ ✔ - [[138](https://arxiv.org/html/2406.16937v1#bib.bib138)] 解答有关近视的问题 ✔ ✔ - - 杂项应用（软件工程） [[139](https://arxiv.org/html/2406.16937v1#bib.bib139)] 提供编程支持 ✔ - - - [[140](https://arxiv.org/html/2406.16937v1#bib.bib140)] 修复漏洞并提供清晰解释 ✔ - - - [[26](https://arxiv.org/html/2406.16937v1#bib.bib26)] 执行软件工程任务 ✔ ✔ - - [[141](https://arxiv.org/html/2406.16937v1#bib.bib141)] 生成用于矩阵乘法的 Java 代码 ✔ ✔ ✔ ✔

杂项应用（金融） [[142](https://arxiv.org/html/2406.16937v1#bib.bib142)] 提供金融研究见解 ✔ - - - [[143](https://arxiv.org/html/2406.16937v1#bib.bib143)] 分析经济数据并提供投资建议 ✔ - - - [[27](https://arxiv.org/html/2406.16937v1#bib.bib27)] 提供投资建议 ✔ ✔ - - [[144](https://arxiv.org/html/2406.16937v1#bib.bib144)] 支持分析师进行战略决策 - - ✔ -

总体而言，像 ChatGPT、BARD、Bing Chat 和 Claude 这样的基于 LLM 的聊天机器人在医疗领域的有效性显而易见。从回答复杂的医学问题到提供个性化的患者教育和治疗建议，它们在改善医疗领域和患者互动方面发挥了至关重要的作用。此外，像 GPT-4 这样能够处理多层次提示、图像和文档的技术进步表明，这些聊天机器人很快将能够分析多媒体，这将进一步提升医疗领域。

### III-D 杂项应用

超越在教育、研究和医疗中的角色，基于 LLM 的聊天机器人在软件工程和金融等领域也越来越受欢迎。在这里，我们讨论了基于 LLM 的聊天机器人如何在这些行业中提供更有效和可扩展的解决方案，具有无与伦比的效率和定制化。

软件工程。与传统的基于命令的软件开发支持相比，LLM（大语言模型）聊天机器人更注重用户的意图，并且采用对话式的方法[[26](https://arxiv.org/html/2406.16937v1#bib.bib26)]。开发者讨论他们的需求或期望结果，而不需要指定实现方法。这一转变使得 LLM 聊天机器人能够处理众多任务，如编写代码、查找和修复错误以及测试软件质量。例如，[[139](https://arxiv.org/html/2406.16937v1#bib.bib139)]中的研究探讨了 ChatGPT 如何作为互动教学工具，提供语言选择建议、代码语法指导、最佳实践见解、库或包推荐、替代方法建议、IDE 介绍和编程环境建议。此外，ChatGPT 还可以修复漏洞，并对复杂主题提供清晰解释，确保全面的学习体验[[140](https://arxiv.org/html/2406.16937v1#bib.bib140)]。与通过 Google 或 Stack Overflow 及 GeeksforGeeks 等网站寻找编码指导不同，ChatGPT 为学习者提供了直接且常实用的编程问题解决方案。另一篇文章[[26](https://arxiv.org/html/2406.16937v1#bib.bib26)]对“搜索与救援”场景进行了案例研究，展示了 BARD 和 ChatGPT 在软件工程任务中的应用。BARD 以提供抽象的、高层次的建议而著称，强调整体概念和策略，如提出理论测试和讨论复杂算法。另一方面，ChatGPT 提供详细、可行的解决方案，专注于具体编码实践和带有实际框架的单元测试。这一区别突显了 BARD 在战略指导方面的优势和 ChatGPT 在提供精确、可实施解决方案方面的能力，强调了它们在软件开发任务中的互补作用[[141](https://arxiv.org/html/2406.16937v1#bib.bib141)]。该研究进一步评估了几个基于 LLM 的聊天机器人生成矩阵乘法 Java 代码的能力，特别关注多线程。测试包括 ChatGPT 3.5 和 4、BARD、Bing Chat、YouChat、GitHub Copilot 和 GitLab Duo。其中大多数聊天机器人在第一次尝试时生成了正确的代码，除了 Google BARD 需要人工协助。YouChat 以最快的代码生成时间（446 毫秒）脱颖而出，而 Bing Chat 表现最慢（1899 毫秒）。然而，值得注意的是，GitHub Copilot、Bing Chat 和 YouChat 往往生成简短但不详细的代码。

此外，用户可以要求这些聊天机器人解释一段代码。聊天机器人将解释每个部分，包括变量和命令。它们还可以总结代码的功能，提升代码的清晰度和理解。总之，基于 LLM 的聊天机器人提供了一种变革性的软件工程方法，通过支持基于意图和对话的互动，涵盖了从代码生成到调试、软件测试以及提供教育支持的一系列任务。这一能力不仅提高了生产力，还使软件工程专业知识对各级程序员更加可及。

表 V：聊天机器人挑战：知识和数据观点

{tblr}

width = colspec = —Q[c,m,0.075]—Q[c,m,0.22]—Q[c,m,0.375]—Q[c,m,0.1035]—Q[c,m,0.1035]—, row1 = font=, c, row1-11 = font=, hlines, cell14 = c=2, cell24 = c=1halign=c,valign=m, cell25 = c=1halign=c,valign=m, cell11 = r=2halign=c,valign=m, cell12 = r=2halign=c,valign=m, cell13 = r=2halign=c,valign=m, cell31 = r=3halign=c,valign=m, cell61 = r=4halign=c,valign=m, cell101 =r=3halign=c,valign=m, Perspective & Challenge Discussion Topic \SetCell[c=2]c Viewpoint

知识 数据

从技术角度来看 知识时效 维护最新知识的挑战 - ✔

逻辑推理 多步推理问题的表现差距 ✔ -

幻觉 生成不正确和不可靠的回应 ✔ -

从伦理角度来看 透明度 聊天机器人推理过程中的不明确性 ✔ ✔

偏见 聊天机器人训练和回应中的数据偏见 ✔ ✔

隐私风险 隐私问题和数据保护问题 ✔ ✔

不公平 语言和经济上的不公平性 - ✔

从滥用角度来看 学术滥用 维护学术诚信的挑战 ✔ -

过度依赖 对批判性思维技能的影响 ✔ -

错误信息的传播 可能传播误导性信息 ✔ -

财务。基于 LLM 的聊天机器人在金融领域取得了突破。它们将资源与客户需求相匹配的能力提升了服务的有效性，并帮助员工更高效地管理日常工作负载。例如，一项研究[[142](https://arxiv.org/html/2406.16937v1#bib.bib142)]探讨了 ChatGPT 在金融行业中的应用。首先，它考察了使用机器学习分析金融数据的潜力及其在金融领域的应用。接下来，提出了“Bananarama 猜想”，该猜想认为 ChatGPT 能够比传统方法提供更好的金融研究见解。另一项研究[[143](https://arxiv.org/html/2406.16937v1#bib.bib143)]探讨了 ChatGPT 如何有效分析金融信息，以识别趋势、市场观点和动向。其分析经济数据并提供投资建议的能力对公司和金融家来说是一个福音。[[27](https://arxiv.org/html/2406.16937v1#bib.bib27)]进一步评估了 ChatGPT 和 BARD 在金融领域为不同语言和方言提供投资建议的表现，包括英语、非洲裔美国英语（AAVE）和泰卢固语。与 ChatGPT 相比，BARD 通过多个草稿提供了多样化的响应，但未能在每次查询中完善内容。此外，BARD 不理解泰卢固语，显示出多语言的局限性。另一方面，ChatGPT 始终纠正错误并随着时间的推移适应 AAVE，尽管它在泰卢固语的准确性上仍有困难。研究显示，BARD 的个性化率较低（53%），错误率较高（15.38%），而 ChatGPT 的个性化率为 46.15%，错误率为 7.69%，ChatGPT 也面临 15.38%的语法错误率。尽管存在这些问题，它们在分析大量金融数据方面的潜力显而易见，展示了在处理复杂信息方面的显著能力。另一篇文章[[144](https://arxiv.org/html/2406.16937v1#bib.bib144)]评估了 Bing Chat 在协助分析师进行投资建议和投资组合推荐中的作用。Bing Chat 分析了 2019 至 2022 年的金融文件，以推荐来自 BIST100 的股票投资组合，选择了六家特定公司。它还指导投资组合构成，建议基于投资组合规模的特定股票数量。总体而言，Bing Chat 提供了有价值的金融见解和建议，支持分析师在战略决策中的作用。

总结来说，这些只是基于 LLM 的聊天机器人在不同领域应用中的一部分。随着技术的发展，这些聊天机器人将变得更加融入我们的生活，重塑我们与技术和彼此之间的互动。此外，由于 AI 技术的进步，聊天机器人的使用不断增长，这回应了消费者偏好的变化和对改进互动技术的需求。补充我们的讨论，表格 [IV](https://arxiv.org/html/2406.16937v1#S3.T4 "TABLE IV ‣ III-C Healthcare ‣ III Applications ‣ A Complete Survey on LLM-based AI Chatbots") 提供了在不同部门中用于各种目的的特定聊天机器人的概述。它突出显示了它们的角色，并将它们与各自参考的文章关联起来。寻求对特定聊天机器人实施的进一步了解的读者可以查阅这些文章以获取更多信息。

## IV 开放挑战

随着基于 LLM 的聊天机器人的发展，它们在不同领域面临着众多挑战。在这一部分，我们将讨论这些挑战，从技术、伦理和误用的角度提供有见地的概述。表格 [V](https://arxiv.org/html/2406.16937v1#S3.T5 "TABLE V ‣ III-D Miscellaneous Applications ‣ III Applications ‣ A Complete Survey on LLM-based AI Chatbots") 按照知识或数据的视角对挑战进行了分类，提供了一个结构化的提纲，以便为读者澄清背景。

### IV-A 从技术角度来看

在这里，我们探讨了基于 LLM 的聊天机器人在知识时效性、逻辑推理和幻觉方面的技术限制。

知识时效性。保持最新的知识对基于 LLM 的聊天机器人来说是一个显著的挑战，因为它们通常在需要超出最近训练的信息的任务上表现困难。虽然通过定期用新数据更新 LLM 是一个直接的解决方案，但这昂贵且在增量训练过程中存在灾难性遗忘的风险。这使得调整 LLM 的内置知识成为一个复杂的任务 [[145](https://arxiv.org/html/2406.16937v1#bib.bib145), [146](https://arxiv.org/html/2406.16937v1#bib.bib146)]。此外，缺乏多样化的高质量数据源也提出了未来的限制 [[147](https://arxiv.org/html/2406.16937v1#bib.bib147), [148](https://arxiv.org/html/2406.16937v1#bib.bib148)]。

逻辑推理。聊天机器人缺乏理性的人类思维。因此，它们既不能像人类一样思考，也不能像人类一样推理[[149](https://arxiv.org/html/2406.16937v1#bib.bib149), [150](https://arxiv.org/html/2406.16937v1#bib.bib150)]。一项[[151](https://arxiv.org/html/2406.16937v1#bib.bib151)]研究评估了使用基础科学和临床科学自我评估计划的 250 个问题，然后将 ChatGPT-3.5、ChatGPT-4 和 Bing Chat 的表现与人类参与者的进行比较。人类的平均准确率为 72.2%。ChatGPT-3.5 得分最低，仅为 58.8%，而 ChatGPT-4 和 Bing Chat 表现出类似的结果，准确率分别为 71.6%和 71.2%。在单步推理问题中，所有三个聊天机器人表现良好，ChatGPT-3.5、ChatGPT-4 和 Bing Chat 的准确率分别为 68.4%、80.0%和 81.0%。然而，它们在多步推理问题中的表现显著下降，其中 ChatGPT-3.5 的得分仅为 40.0%，ChatGPT-4 和 Bing Chat 分别为 64.5%和 60.0%。另一篇最近的论文[[152](https://arxiv.org/html/2406.16937v1#bib.bib152)]评估了 BARD 的逻辑推理能力。作者使用 TPTP 问题 PUZ001+1 提出了一个具体问题，并利用 TPTP World 的工具分析了 BARD 的回答。研究结果表明，BARD 的推理是有缺陷的，导致从所提供的数据得出了不正确的结论，这归因于缺乏形式推理能力。然而，该研究还承认，这个测试集中在特定的推理任务上，BARD 可能在其他任务中表现更好。[[153](https://arxiv.org/html/2406.16937v1#bib.bib153)]进一步强调了数学中有限的逻辑推理能力，因为 BARD 在越南国家高中毕业考试（VNHSGE）数学测试中表现不佳，仅显示出 38.8%的准确率。

**幻觉**。基于 LLM 的聊天机器人在生成事实文本时面临一个显著挑战，即**幻觉**[[2](https://arxiv.org/html/2406.16937v1#bib.bib2), [83](https://arxiv.org/html/2406.16937v1#bib.bib83)]，其中生成的信息要么与现有来源相矛盾（内在幻觉），要么无法通过现有来源确认（外在幻觉）。简单来说，幻觉是聊天机器人自信地给出的回答，但这些回答既不正确也不可靠。例如，[[139](https://arxiv.org/html/2406.16937v1#bib.bib139)]强调了 ChatGPT 在被要求为综述论文寻找相关引用时，如何生成完全虚构的出版物。另一项研究[[103](https://arxiv.org/html/2406.16937v1#bib.bib103)]通过询问 ChatGPT-3.5、GPT-4、Bing Chat 和 BARD 关于高等教育中被引用最多的 ChatGPT 文章，来比较它们的表现。所有聊天机器人的结果都令人失望。例如，ChatGPT 给出了五个完全不相关的参考文献，时间回溯到 1975 年。GPT-4 有所改进，但 Bing Chat 和 BARD 提供的参考文献完全是虚构的。在医疗保健中使用聊天机器人的担忧还包括幻觉，其中输出看起来可信但实际上是事实不准确的。[[135](https://arxiv.org/html/2406.16937v1#bib.bib135)]的研究评估了 ChatGPT 根据 2021 年 NCCN 指南对乳腺癌、前列腺癌和肺癌的推荐。作者准备了四个零样本提示模板，从 26 种癌症诊断中生成 104 个提示，而没有正确回答的示例。然后，三位获得认证的肿瘤学专家使用五个标准对这 104 个提示的回答进行评估，共计 520 个评分。在这些回答中，13 个（12.5%）被识别为幻觉，即它们与任何推荐的治疗不一致。此外，另一项研究[[131](https://arxiv.org/html/2406.16937v1#bib.bib131)]表明，尽管 ChatGPT 和 Bing Chat 在回答关于房颤的查询时提供了准确的答案，但一些回答包括虚构的或错误引用的参考文献。与 ChatGPT 相比，Bing Chat 在回答的准确性上表现更高，但不准确参考文献的频率相当。尽管 GPT-4 在减少幻觉方面相比于之前的版本有所改进，但仍需继续研究以进一步减少这一问题。

除了这些，基于 LLM 的聊天机器人还存在一致性问题，常常对相同的输入生成不同的响应[[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]。研究人员正在通过提示工程[[154](https://arxiv.org/html/2406.16937v1#bib.bib154)]来改进这一问题。还需要注意的是，这些聊天机器人缺乏自我意识、情感或主观体验，尽管它们能够回答问题并生成连贯的文本[[155](https://arxiv.org/html/2406.16937v1#bib.bib155)]。关于机器是否真的能拥有自我意识的争论仍在继续，目前尚未建立明确的定义或测量方法。

### IV-B 从伦理角度

在本小节中，我们讨论了基于 LLM 的聊天机器人的伦理问题，重点关注透明性、偏见、隐私风险和不公平等关键领域。

透明性。由于从输入查询生成答案的过程复杂，LLM（大型语言模型）常常被描述为黑箱模型。因此，基于 LLM 的聊天机器人缺乏透明性，使得很难理解特定输出或决策背后的推理[[156](https://arxiv.org/html/2406.16937v1#bib.bib156)]。例如，在医疗领域，LLM 基于聊天机器人的透明性问题是一个重要关注点，因为健康响应和遗传因素在不同人群中差异很大[[157](https://arxiv.org/html/2406.16937v1#bib.bib157)]。此外，训练数据的透明性，可能未经过领域特定的准确性验证，导致了‘垃圾进，垃圾出’的问题。这对于像 GPT-3.5 这样的模型也是成立的，因为它不验证训练数据的准确性[[3](https://arxiv.org/html/2406.16937v1#bib.bib3)]。此外，OpenAI 从非营利组织转型为以商业为中心的组织，也引发了关于其在披露技术进展细节方面透明性的担忧。例如，GPT-4 技术报告[[29](https://arxiv.org/html/2406.16937v1#bib.bib29)]主要集中于其相较于前代模型的改进性能，但在解释实现这些改进所使用的基础技术方法方面有所不足。

偏见。另一个关于基于 LLM 的聊天机器人问题是偏见。这发生在模型训练时使用了有偏见的数据，这些数据可能代表社会中的种族、性别或社会经济不平等。如[[158](https://arxiv.org/html/2406.16937v1#bib.bib158)]所指出，大型预训练模型模仿自然语言时，可能会重复这些偏见。此外，聊天机器人的回答受其接收的输入影响。如果用户经常提出有偏见的问题，模型可能会学习并复制这些问题[[159](https://arxiv.org/html/2406.16937v1#bib.bib159)]。此外，当模型被微调以优化特定指标，如准确性或用户参与度时，可能存在算法偏见的风险，即回答可能会与这些目标一致，而不考虑固有的偏见。在医疗治疗中，使用在有偏见数据上训练的聊天机器人可能导致不准确的医疗结果，可能对患者和社区造成伤害。例如，聊天机器人可能由于偏见训练而误诊医疗状况，并推荐错误的治疗方案。一项[[160](https://arxiv.org/html/2406.16937v1#bib.bib160)]的研究强调了一个用于皮肤病诊断的 AI 系统，该系统产生了高假阳性率。这个问题导致了不必要的活检程序，并增加了患者的焦虑。另一项研究[[161](https://arxiv.org/html/2406.16937v1#bib.bib161)]观察到 Bing Chat 和 Google BARD 存在偏见，倾向于推荐主要是男性的眼科医生。此外，在学术研究中，这些聊天机器人可能产生不准确或有偏见的结果。例如，一个使用有偏见数据训练的聊天机器人可能在社会科学研究中产生错误的发现，从而导致错误的结论，这可能对边缘化群体产生负面影响[[5](https://arxiv.org/html/2406.16937v1#bib.bib5)]。此外，[[162](https://arxiv.org/html/2406.16937v1#bib.bib162)]发现 ChatGPT 在创作爱尔兰打油诗时表现出政治偏见，偏向自由主义观点。在民主国家的政治选举审查中，ChatGPT 也被发现具有左翼自由主义偏见[[163](https://arxiv.org/html/2406.16937v1#bib.bib163)]。

隐私风险。从透明度和偏见问题转向 LLM 基于聊天机器人的另一个重要问题是用户隐私和数据保护。意大利最近在数据泄露后对 ChatGPT 实施了禁令，突显了隐私问题和缺乏年龄验证，这可能会将未成年人暴露于不适当内容之中[[164](https://arxiv.org/html/2406.16937v1#bib.bib164)]。这些聊天机器人在训练时使用的大量数据集中通常包括敏感的用户信息，如聊天记录和个人详细信息，这可能会导致隐私问题。此外，聊天机器人可以根据用户的查询生成个性化的输出。例如，如果用户输入了诸如健康或财务数据等机密信息，聊天机器人可能会不小心将这些信息透露给其他人[[159](https://arxiv.org/html/2406.16937v1#bib.bib159)]。此外，重要的是要认识到，根据其隐私政策，OpenAI 可能会收集输入中包含的任何个人信息[[165](https://arxiv.org/html/2406.16937v1#bib.bib165)]。因此，个人信息的这种误用可能对用户造成有害的后果，尤其是当这些信息落入犯罪分子之手时。

不公平性。训练数据中的偏见可能导致语言模型在学习过程中增加不公平性，常常边缘化较小的群体。由于大多数关于大型语言模型的研究主要服务于英语使用者，因此其他语言的研究存在显著的空白，引入了一层语言上的不公平性。这可能会使以英语为母语的用户在教育过程中受益，而将讲其他语言的用户排除在这些技术进步之外，从而限制他们的获取[[122](https://arxiv.org/html/2406.16937v1#bib.bib122)]。此外，获取基于 LLM 的聊天机器人的经济不公平性，如 ChatGPT Plus 的费用，可能会以空前的方式扩大教育差距[[122](https://arxiv.org/html/2406.16937v1#bib.bib122), [31](https://arxiv.org/html/2406.16937v1#bib.bib31), [166](https://arxiv.org/html/2406.16937v1#bib.bib166)]。

因此，在创建和使用基于 LLM 的聊天机器人时，优先考虑伦理标准至关重要。解决透明度、偏见、隐私风险和不公平性的问题是维护伦理完整性，同时确保用户信任和安全的必要条件。

### IV-C 从误用的角度

在这里，我们讨论了基于 LLM 的聊天机器人的实际挑战，重点关注学术误用、过度依赖和错误信息传播等方面，突显其在现实世界中的影响。

学术滥用。基于 LLM 的聊天机器人在学术写作中常被误用，学生和研究人员可能在考试和研究论文中使用生成的内容而没有适当的引用。许多机构已禁用这些工具，理由是它们可能破坏评估标准和教育价值[[31](https://arxiv.org/html/2406.16937v1#bib.bib31), [167](https://arxiv.org/html/2406.16937v1#bib.bib167)]。一项在[[168](https://arxiv.org/html/2406.16937v1#bib.bib168)]的研究探讨了对高等教育中抄袭的日益担忧以及使用 ChatGPT 作弊的情况。此外，[[101](https://arxiv.org/html/2406.16937v1#bib.bib101), [103](https://arxiv.org/html/2406.16937v1#bib.bib103), [169](https://arxiv.org/html/2406.16937v1#bib.bib169)]显示 ChatGPT 可以生成复杂且真实的内容，通常无法被标准的反抄袭软件如 iThenticate 或 Turnitin[[170](https://arxiv.org/html/2406.16937v1#bib.bib170), [171](https://arxiv.org/html/2406.16937v1#bib.bib171), [172](https://arxiv.org/html/2406.16937v1#bib.bib172)]检测到，这进一步质疑了在线考试的公正性。

过度依赖。另一个日益引起关注的问题是对基于 LLM 的聊天机器人的依赖增加。例如，[[21](https://arxiv.org/html/2406.16937v1#bib.bib21)]展示了使用 Google BARD 生成文献综述的情况。虽然 BARD 生成的文本最初含有一些抄袭，但可以通过使用改写工具解决。另一项研究[[173](https://arxiv.org/html/2406.16937v1#bib.bib173)]评估了 Bing Chat 在满足越南学生学术需求方面的表现，涵盖了数学、英语、物理、化学、生物、文学、历史、地理和公民教育等多个学科。结果显示，Bing Chat 在大多数学科上优于 ChatGPT，唯独在文学方面 ChatGPT 表现更好。此外，Bing Chat 在越南的可访问性及其在回答中包含超链接和引用的能力进一步强调了其优势。随着这些智能系统的兴起，学生们获得了大量计算能力，这在很大程度上帮助了他们的学术工作[[167](https://arxiv.org/html/2406.16937v1#bib.bib167)]。然而，这种依赖和赋能通常会削弱独立思考和批判性思维的能力。

错误信息的传播。如前所述，基于 LLM 的聊天机器人像一个黑箱一样运作，难以解释它们如何处理和做出决策[[174](https://arxiv.org/html/2406.16937v1#bib.bib174), [175](https://arxiv.org/html/2406.16937v1#bib.bib175)]。除非特别要求，否则回应不会被引用或解释，并且任何解释的可靠性都不确定。因此，基于这些 LLM 的聊天机器人一个显著的问题是它们有可能像传播真实信息一样传播错误信息[[31](https://arxiv.org/html/2406.16937v1#bib.bib31), [176](https://arxiv.org/html/2406.16937v1#bib.bib176), [155](https://arxiv.org/html/2406.16937v1#bib.bib155)]。例如，[[177](https://arxiv.org/html/2406.16937v1#bib.bib177)]中的一项研究强调，用户可能会误用 ChatGPT 来虚假地建议医疗诊断，通过提供看似准确和可靠的信息。另一项调查[[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]显示，这些聊天机器人可以用来为博客、媒体、报纸或互联网创建大量虚假文章。这些文章可能看起来很真实，但它们可能是假的，根本不存在，这使得区分事实与虚构变得更加困难。此外，微软将 Bing Chat 整合到其搜索引擎中，可能会显著加速互联网假信息的传播。如果没有适当的控制，这种快速传播的信息不实可能对公众信息安全造成损害。此外，一些近期文章[[178](https://arxiv.org/html/2406.16937v1#bib.bib178), [179](https://arxiv.org/html/2406.16937v1#bib.bib179), [180](https://arxiv.org/html/2406.16937v1#bib.bib180)]探讨了与这些聊天机器人相关的潜在漏洞和威胁，包括各种攻击向量、信息提取以及有害内容的创建。[[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]强调，黑客可能利用 ChatGPT 的编程技能开发恶意软件[[181](https://arxiv.org/html/2406.16937v1#bib.bib181)]，如病毒或木马，用于网络攻击、数据盗窃或劫持其他计算机系统，这可能对用户造成重大伤害。此外，恶意网络用户可能会用有针对性的提示操控 ChatGPT，生成有害内容来攻击其他用户[[176](https://arxiv.org/html/2406.16937v1#bib.bib176)]。

总结来说，尽管基于 LLM 的聊天机器人在多个领域提供了宝贵的优势，但其潜在的误用带来了重大的风险。用户必须确保适当引用以防止学术不端，避免过度依赖这些工具以保持批判性和独立思考能力，并仔细验证所提供信息的准确性。

## 未来展望

在本节中，我们将探讨基于 LLM 的聊天机器人未来的前景，从提高效率和可持续性的技术改进到指导其负责任使用的伦理考量。

![参见标题](img/0b3debae013de464ef7e054b02f096d9.png)

图 10：模型规模与平均 MMLU 分数之间的关联 [[182](https://arxiv.org/html/2406.16937v1#bib.bib182)]。

### V-A 技术改进

在这里，我们重点关注模型压缩和优化以提高效率，利用绿色 AI 技术应对环境问题，提示工程的进展，以及超越文本的多模态能力的出现。

模型压缩与优化。基于 Transformer 的语言模型随着参数数量的增加表现出更强的能力[[183](https://arxiv.org/html/2406.16937v1#bib.bib183), [184](https://arxiv.org/html/2406.16937v1#bib.bib184)]。例如，在模型超过某些规模阈值时，像上下文学习[[3](https://arxiv.org/html/2406.16937v1#bib.bib3)]和思维链（CoT）提示[[82](https://arxiv.org/html/2406.16937v1#bib.bib82)]等显著进展变得愈加明显。比如，图 [10](https://arxiv.org/html/2406.16937v1#S5.F10 "Figure 10 ‣ V Future Outlook ‣ A Complete Survey on LLM-based AI Chatbots") 展示了在不同规模模型中，Massive Multitask Language Understanding (MMLU) 基准测试的 CoT 提示平均得分[[182](https://arxiv.org/html/2406.16937v1#bib.bib182), [185](https://arxiv.org/html/2406.16937v1#bib.bib185)]。图表显示，随着参数数量从 Flan-T5-XL 的 30 亿增加到 Gemini Ultra 的约 1760 亿，MMLU 得分有了显著上升。然而，尽管这些大型语言模型在自然语言处理方面取得了进展，但根据扩展定律[[184](https://arxiv.org/html/2406.16937v1#bib.bib184)]，其巨大的规模，通常超过 1000 亿个参数，仍然带来实际挑战，包括存储、分发和部署的高成本。为了解决这些问题，未来的研究应更多关注模型压缩和优化[[184](https://arxiv.org/html/2406.16937v1#bib.bib184)]。这些对在现实世界中使用现代聊天机器人至关重要。实现这一目标有几种方法。基于蒸馏的方法通过使用较大的模型的数据训练一个较小的模型[[186](https://arxiv.org/html/2406.16937v1#bib.bib186), [187](https://arxiv.org/html/2406.16937v1#bib.bib187), [188](https://arxiv.org/html/2406.16937v1#bib.bib188)]。基于剪枝的方法通过移除冗余权重来减少模型大小[[189](https://arxiv.org/html/2406.16937v1#bib.bib189), [190](https://arxiv.org/html/2406.16937v1#bib.bib190)]，而量化则减少了模型权重的存储大小[[191](https://arxiv.org/html/2406.16937v1#bib.bib191), [192](https://arxiv.org/html/2406.16937v1#bib.bib192)]。然而，这些方法可能需要专用硬件。有兴趣的读者可以参考[[193](https://arxiv.org/html/2406.16937v1#bib.bib193)]获取更多细节。

绿色 AI。基于大语言模型（LLM）的聊天机器人日益普及，关注点转向环境问题，因为它们在训练过程中依赖大量计算资源。这些聊天机器人基于大型预训练模型，往往承载着来自多个数据源的固有偏见，使得减轻偏见成为一个具有挑战性的任务，因其开发过程复杂。相比之下，传统聊天机器人的偏见较少，但无法生成流利且多样的自然语言内容。通过知识图谱（KGs）增强 LLM 可能会改善其知识库 [[194](https://arxiv.org/html/2406.16937v1#bib.bib194), [195](https://arxiv.org/html/2406.16937v1#bib.bib195)]。然而，这种整合尚未提供完全透明的推理过程。尽管如此，机器学习模型规模和资源需求的增加使绿色 AI 成为关注焦点 [[196](https://arxiv.org/html/2406.16937v1#bib.bib196), [197](https://arxiv.org/html/2406.16937v1#bib.bib197)]。绿色学习（GL）技术旨在实现更环保的 AI 系统，采用较小、较简单的模型，对于开发具有简化推理过程和减少资源需求的聊天机器人至关重要。它们还可以在各种应用中提供与深度学习（DL）相当的性能 [[196](https://arxiv.org/html/2406.16937v1#bib.bib196)]。基于 GL 的聊天机器人可能涉及将 LLM 分为两个模块：一个基于 GL 的模块专注于用户交互，处理自然语言理解和生成相关任务，另一个模块则专注于知识存储、扩展以及通过 KGs 进行推理。这种方法可能为更透明、可扩展且无偏见的聊天机器人铺平道路，有助于开发更公平的 AI 系统。

提示工程。提示工程也变得对有效使用人工智能聊天机器人至关重要，影响从日常任务到复杂数据分析的广泛应用。提示的质量至关重要，因为它决定了人工智能回应的相关性和准确性，体现了输出质量仅与输入质量相当的理念。有效的提示通常包括四个要素。它们是背景设置、具体指令、格式或结构，以及可选示例。背景设置提供背景信息，帮助人工智能理解回应的背景。具体指令明确任务或问题，旨在从语言模型（LLM）中获得相关回应。格式或结构特征决定回应的结构，包括字数、要点或表格和图形等视觉元素。最后，可选示例，从零-shot 到少-shot 提示，进一步提高回应质量。这些示例展示了回应的理想格式或结构。最近的一项研究 [[82](https://arxiv.org/html/2406.16937v1#bib.bib82)] 显示，提示可以在语言模型中引发类推理回应。毫无疑问，这将推动提示技术的进一步创新。总之，提示工程的重要性日益增加，从最近的出版物中可以看出，这意味着实现人工通用智能（AGI）可能需要比单纯增加模型规模和数据量更具创造性的方法。未来在这一领域的工作有望探索实现这一目标的新方法。

多模态性。将基于 LLM 的聊天机器人与计算机视觉和机器人技术整合，扩展了这些系统的能力，超越了传统的文本互动。例如，ChatGPT、Claude 和 Bing Chat 可以根据用户输入生成视觉内容的描述，回答有关图像的问题，并处理包括 PDF 和 CSV 在内的文档。另一方面，BARD 在视觉内容解释方面表现出色，但缺乏处理文档的功能。另一个探索领域是转移学习技术的进步，使 ChatGPT 和其他聊天机器人能够有效地从语言和视觉领域中吸收知识。对模型进行大规模数据集的预训练，例如结合文本和图像数据的 Conceptual Captions 数据集 [[198](https://arxiv.org/html/2406.16937v1#bib.bib198)]，可以加深聊天机器人对语言与视觉信息之间关系的理解。聊天机器人与计算机视觉技术的前景整合预示着 AI 的新时代。这包括像绘画 [[199](https://arxiv.org/html/2406.16937v1#bib.bib199)] 这样的艺术创作、智能车辆操作 [[200](https://arxiv.org/html/2406.16937v1#bib.bib200)、[201](https://arxiv.org/html/2406.16937v1#bib.bib201)、[202](https://arxiv.org/html/2406.16937v1#bib.bib202)]、工业自动化 [[203](https://arxiv.org/html/2406.16937v1#bib.bib203)] 以及视觉互动对话系统 [[204](https://arxiv.org/html/2406.16937v1#bib.bib204)]。除了计算机视觉，将这些聊天机器人与化学系统整合，使用如 SMILES [[205](https://arxiv.org/html/2406.16937v1#bib.bib205)] 等技术，可能会彻底改变对化学成分的解读和互动方式。这种整合也可能简化复杂的化学分析，并提升在药理学和材料科学等领域的研究能力。

总而言之，基于大语言模型（LLM）的聊天机器人的未来在于优化模型效率，整合绿色 AI 以实现环境可持续性，增强提示工程以改善互动动态，以及拥抱超越单纯文本通信的多模态能力。

### V-B 伦理指南与负责任使用

在这里，我们讨论了基于 LLM 的聊天机器人在伦理考量和负责任使用方面的关键因素。我们探讨了用户互动的隐私和数据保护，强调语言多样性和权利平等以促进普遍可达性，并讨论了学术和医疗协议以确保教育和医疗中的公平与责任。

隐私和数据保护。训练基于 LLM 的聊天机器人需要大量数据集，通常包含聊天记录和个人详细信息等敏感用户信息。因此，确保用户数据的隐私和安全对于维护对该技术的信任至关重要[[7](https://arxiv.org/html/2406.16937v1#bib.bib7), [206](https://arxiv.org/html/2406.16937v1#bib.bib206), [207](https://arxiv.org/html/2406.16937v1#bib.bib207)]。此外，在医疗保健领域，在训练过程中对患者数据进行匿名化和保护是必须的，以符合 HIPAA 等隐私法律的规定[[208](https://arxiv.org/html/2406.16937v1#bib.bib208)]。研究人员和开发人员必须实施严格的隐私和安全措施，例如加密、数据匿名化和对数据的受控访问。此外，在医疗保健领域使用这些技术时，患者批准、透明度和道德标准同样重要[[208](https://arxiv.org/html/2406.16937v1#bib.bib208)]。

语言多样性和平等待遇。尽管像 GPT-4 和 ChatGPT 这样的 AI 工具已经取得了进展，但由于数据集有限，非英语语言仍存在显著的性能差距 [[209](https://arxiv.org/html/2406.16937v1#bib.bib209), [210](https://arxiv.org/html/2406.16937v1#bib.bib210)]。因此，生成型 AI 工具的开发者面临确保这些技术在多种语言和用户需求中都是包容、公平且有效的挑战。因此，未来开发者必须专注于创建能够服务广泛用户的 AI 技术，包括那些处于弱势地位或有残疾的人，通过提供多模态互动选项。此外，还必须避免训练数据中的偏见和不公平，因为像 ChatGPT 这样的聊天机器人可能会因使用偏见数据而无意中支持刻板印象或歧视某些人。另一方面，公平意味着平等对待每一位用户，不允许他们的背景影响他们所获得的服务。因此，开发者必须在训练阶段完成后继续监控聊天机器人，确保任何偏见能够被及时识别和修正。这将确保所有用户平等获取信息和服务，在聊天机器人的开发和使用过程中维持伦理标准和公平性 [[7](https://arxiv.org/html/2406.16937v1#bib.bib7), [211](https://arxiv.org/html/2406.16937v1#bib.bib211), [12](https://arxiv.org/html/2406.16937v1#bib.bib12)]。未来的工作还应考虑以用户为中心的设计原则，强调社会、情感、认知和教育方面 [[212](https://arxiv.org/html/2406.16937v1#bib.bib212)]。借鉴 Duolingo 和 Khan Academy 等平台的灵感，开发者可以利用 ChatGPT 和其他聊天机器人在各个教育层次提供个性化学习体验和实时反馈。这包括利用聊天机器人进行互动临床沟通模块和同伴学习体验，从而增强专业培训的深度和实用性。

学术和医疗协议。一个日益关注的问题是在教育中滥用基于 LLM 的聊天机器人。在教育中使用这些聊天机器人需要谨慎取舍，因为虽然它们提供了宝贵的见解，但不能取代人类独特的创造和批判性思维能力。正如[[213](https://arxiv.org/html/2406.16937v1#bib.bib213), [8](https://arxiv.org/html/2406.16937v1#bib.bib8), [214](https://arxiv.org/html/2406.16937v1#bib.bib214)]所指出的，禁止这些聊天机器人并不是一个可行的解决方案。相反，应该制定责任、诚信、透明和诚实的规则和法规。多项研究[[215](https://arxiv.org/html/2406.16937v1#bib.bib215), [216](https://arxiv.org/html/2406.16937v1#bib.bib216), [166](https://arxiv.org/html/2406.16937v1#bib.bib166)]调查了 ChatGPT 在学术写作中的应用，强调了关于作者身份、透明度和偏见的担忧，要求建立道德准则和承诺最佳实践。需要仔细考虑哪些学术技能对研究人员至关重要。学术界应该发起基于 LLM 的聊天机器人在研究中的发展和负责任的使用，遵循全面的道德准则，以确保道德和专业标准得到维护。此外，将批判性思维和问题解决练习融入课程中可以有效地指导学生从早期就发展创造性技能[[31](https://arxiv.org/html/2406.16937v1#bib.bib31)]。

在教育领域的 AI 整合这一更广泛的背景下，尽管聊天机器人在从小学到大学的各个层面得到广泛应用，医疗机构仍处于利用这一技术的初级阶段。随着生成性 AI 工具和基于 LLM 的聊天机器人在教育中的作用日益增加，医疗领域的教育者和学生面临着独特的挑战和机遇。管理员必须制定策略，将新技术负责任地融入医疗教育中。这些策略包括为 AI 工具在作业中的使用创建指南，使用文本检测工具如 Originality AI、Turnitin 和 ZeroGPT，以及进行有效和伦理的 AI 使用培训 [[217](https://arxiv.org/html/2406.16937v1#bib.bib217)]。另一方面，教育者应拥抱这些技术，并将其融入医疗课程中。这包括更新课程内容，以涵盖 AI 在医学中的作用，例如药物发现，并设计需要更高层次思维的作业。同时，教育者必须避免过度依赖 AI，并鼓励学生批判性地评估 AI 生成的回应 [[218](https://arxiv.org/html/2406.16937v1#bib.bib218)]。学生则应意识到 LLMs 的局限性，包括隐私、版权、透明度和偏见问题。他们应以伦理和建设性的方式使用这些工具，提升医疗实践技能，同时在工作中正确引用 LLM 的使用，并确保 AI 的负责任使用 [[218](https://arxiv.org/html/2406.16937v1#bib.bib218), [217](https://arxiv.org/html/2406.16937v1#bib.bib217)]。

尽管新兴的聊天机器人预计会提供更准确和安全的内容，并且具有真实的引用和更少的错误，但在当前和提议的国际监管框架下，可解释性和透明度的充分性仍然不明确 [[219](https://arxiv.org/html/2406.16937v1#bib.bib219), [220](https://arxiv.org/html/2406.16937v1#bib.bib220)]。因此，减少不适当医疗建议的一种策略是将大型语言模型（LLM）的训练限制在受控和验证的医疗文本上。例如，GatorTronGPT 在 82 亿个匿名临床文本的训练下，在回答医疗问题时显示出比以前的模型更高的准确性 [[221](https://arxiv.org/html/2406.16937v1#bib.bib221)]。此外，由于医疗研究和文档可能并不总是最新或准确，旨在医疗应用的 LLM 开发者应从一开始就实施质量管理系统。这与当前监管框架中定义的协议以及未来的 AI 安全要求一致。

总结来说，本节概述了基于 LLM 的聊天机器人的负责任使用的伦理考量和实践。我们强调了保护隐私和数据的重要性、确保语言多样性和公平权利的必要性，以及制定学术和医疗协议。这些措施对于聊天机器人技术的伦理进步至关重要，确保它们在不同用户群体中既公平又有益。

## VI 结论

在这项综合调查中，我们探讨了基于 LLM 的聊天机器人领域。我们从聊天机器人发展的初期阶段开始，接着探索 LLM，包括它们的底层架构、工作原理和开创性特征，随后概述了现有和新兴的基于 LLM 的聊天机器人。接下来，我们考察了在教育、研究、医疗等各个领域的多种应用。除了它们的潜力外，我们还讨论了它们在技术、伦理和误用方面面临的挑战。最后，我们通过审视技术升级和伦理标准来结束我们的调查，强调它们在提高效率、可持续性和责任承诺方面的进展。随着我们调查的结束，我们希望它能作为一个宝贵的资源，在不断发展的人工智能领域中促进关于通用人工智能和 LLM 角色的讨论和反思。

## 参考文献

+   [1] P. Taylor, “2010 年至 2025 年全球创建、捕获、复制和消费的数据/信息量，” 2023，[在线]. 可用: [`www.statista.com/statistics/871513/worldwide-data-created/`](https://www.statista.com/statistics/871513/worldwide-data-created/)。 [访问日期: 2024 年 4 月 24 日]。

+   [2] W. X. Zhao, K. Zhou, J. Li, T. Tang, X. Wang, Y. Hou, Y. Min, B. Zhang, J. Zhang, Z. Dong *等*, “大型语言模型的调查，” *arXiv 预印本 arXiv:2303.18223*, 2023。

+   [3] T. Brown, B. Mann, N. Ryder, M. Subbiah, J. D. Kaplan, P. Dhariwal, A. Neelakantan, P. Shyam, G. Sastry, A. Askell *等*, “语言模型是少样本学习者，” *神经信息处理系统进展*, vol. 33, pp. 1877–1901, 2020。

+   [4] Google, “Google 趋势 - 探索，” 2024，[在线]. 可用: [`trends.google.com/trends/explore?date=2022-11-30%202024-04-25&q=ChatGPT,5G,IoT,Blockchain&hl=en`](https://trends.google.com/trends/explore?date=2022-11-30%202024-04-25&q=ChatGPT,5G,IoT,Blockchain&hl=en)。 [访问日期: 2024 年 4 月 25 日]。

+   [5] C. Kooli, “教育和研究中的聊天机器人：伦理影响及解决方案的批判性审查，” *Sustainability*, vol. 15, no. 7, p. 5614, 2023。

+   [6] A. Tlili, B. Shehata, M. A. Adarkwah, A. Bozkurt, D. T. Hickey, R. Huang, 和 B. Agyemang, “如果魔鬼是我的守护天使：以 ChatGPT 为案例研究聊天机器人在教育中的应用，” *Smart Learning Environments*, vol. 10, no. 1, p. 15, 2023。

+   [7] A. Koubaa, W. Boulila, L. Ghouti, A. Alzahem, 和 S. Latif, “探索 ChatGPT 的能力和局限性：对 NLP 变革者的批判性回顾，” 2023 年。

+   [8] M. Sallam, “ChatGPT 在医疗保健教育、研究和实践中的效用：关于前景和有效关注点的系统综述，” 发表在 *医疗保健*，第 11 卷，第 6 期，MDPI，2023 年，页码 887。

+   [9] C. K. Lo, “ChatGPT 对教育的影响是什么？文献的快速综述，” *教育科学*，第 13 卷，第 4 期，页码 410，2023 年。

+   [10] M. Hosseini, C. A. Gao, D. M. Liebovitz, A. M. Carvalho, F. S. Ahmad, Y. Luo, N. MacDonald, K. L. Holmes, 和 A. Kho, “关于在教育、医疗和研究中使用 ChatGPT 的探索性调查，” *Plos one*，第 18 卷，第 10 期，页码 e0292216，2023 年。

+   [11] P. P. Ray, “ChatGPT：背景、应用、主要挑战、偏见、伦理、局限性和未来范围的综合评述，” *物联网与网络物理系统*，2023 年。

+   [12] Y. K. Dwivedi, N. Kshetri, L. Hughes, E. L. Slade, A. Jeyaraj, A. K. Kar, A. M. Baabdullah, A. Koohang, V. Raghavan, M. Ahuja *等*，“‘如果 ChatGPT 写了它，那又如何？’ 从多学科角度看生成对话 AI 在研究、实践和政策中的机会、挑战和影响，” *国际信息管理期刊*，第 71 卷，页码 102642，2023 年。

+   [13] S. S. Sohail, F. Farhat, Y. Himeur, M. Nadeem, D. Ø. Madsen, Y. Singh, S. Atalla, 和 W. Mansoor, “解码 ChatGPT：现有研究的分类、当前挑战和可能的未来方向，” *国王沙特大学计算机与信息科学期刊*，页码 101675，2023 年。

+   [14] R. P. d. Santos, “利用 ChatGPT 和 Bing Chat 增强化学学习作为思考工具的案例研究，” *arXiv 预印本 arXiv:2305.11890*，2023 年。

+   [15] C.-C. Lin, A. Y. Huang, 和 S. J. Yang, “基于人工智能的对话聊天机器人实施方法和挑战综述（1999–2022），” *可持续性*，第 15 卷，第 5 期，页码 4012，2023 年。

+   [16] H. Khosravi, M. R. Shafie, M. Hajiabadi, A. S. Raihan, 和 I. Ahmed, “聊天机器人与 ChatGPT：Web of Science 和 Scopus 数据库中出版物的文献计量分析和系统评审，” *arXiv 预印本 arXiv:2304.05436*，2023 年。

+   [17] B. A. Alazzam, M. Alkhatib, 和 K. Shaalan, “人工智能聊天机器人：经典与深度机器学习技术的调查，” 2023 年。

+   [18] D. Baidoo-Anu 和 L. Owusu Ansah, “生成性人工智能（AI）时代的教育：理解 ChatGPT 在促进教学和学习方面的潜在好处，” *可在 SSRN 4337484 查阅*，2023 年。

+   [19] D. Song, E. Y. Oh, 和 H. Hong, “使用不同态度的学生聊天机器人进行教学模拟对预备教师效能的影响，” *教育技术与社会*，第 25 卷，第 3 期，页码 46–59，2022 年。

+   [20] D. Lee 和 S. Yeo，“开发基于 AI 的聊天机器人以实践数学响应式教学”，*计算机与教育*，第 191 卷，第 104646 页，2022 年。

+   [21] Ö. AYDIN，“谷歌 Bard 生成的文献综述：元宇宙”，*人工智能期刊*，第 7 卷，第 1 期，第 1-14 页，2023 年。

+   [22] C. Macdonald, D. Adeloye, A. Sheikh 和 I. Rudan，“ChatGPT 能撰写研究文章吗？：人口级疫苗效果分析的一个例子”，*全球健康期刊*，第 13 卷，2023 年。

+   [23] K. Girotra, L. Meincke, C. Terwiesch 和 K. T. Ulrich，“点子稀松平常：大语言模型在创新中的创意生成”，*SSRN 4526071 可用*，2023 年。

+   [24] S. Ayanouz, B. A. Abdelhakim 和 M. Benhmed，“基于 NLP 和机器学习的智能聊天机器人架构用于医疗援助”，在*第三届国际网络、信息系统与安全会议论文集*中，2020 年，第 1-6 页。

+   [25] L. Athota, V. K. Shukla, N. Pandey 和 A. Rana，“基于人工智能的医疗系统聊天机器人”，在*2020 年第八届国际可靠性、信息通信技术与优化（趋势与未来方向）（ICRITO）*中。 IEEE，2020 年，第 619-622 页。

+   [26] L. Belzner, T. Gabor 和 M. Wirsing，“大语言模型辅助的软件工程：前景、挑战和案例研究”，在*弥合 AI 与现实之间的差距国际会议*中。 Springer，2023 年，第 355-374 页。

+   [27] K. Lakkaraju, S. K. R. Vuruma, V. Pallagani, B. Muppasani 和 B. Srivastava，“大语言模型能成为优秀的财务顾问吗？：个人决策优化结果的初步研究”，*arXiv 预印本 arXiv:2307.07422*，2023 年。

+   [28] S. Patel，“十大聊天机器人实际应用案例”，2023，[在线]. 可用：[`www.revechat.com/blog/chatbots-use-cases/`](https://www.revechat.com/blog/chatbots-use-cases/)。[访问日期：2024 年 5 月 1 日]。

+   [29] OpenAI，“GPT-4 技术报告”，2023 年。

+   [30] A. Bahrini, M. Khamoshifar, H. Abbasimehr, R. J. Riggs, M. Esmaeili, R. M. Majdabadkohne 和 M. Pasehvar，“ChatGPT：应用、机会与威胁”，在*2023 年系统与信息工程设计研讨会（SIEDS）*中。 IEEE，2023 年，第 274-279 页。

+   [31] C. Zhang, C. Zhang, C. Li, Y. Qiao, S. Zheng, S. K. Dam, M. Zhang, J. U. Kim, S. T. Kim, J. Choi *等*，“生成型 AI 的一小步，AGI 的一大步：对 AIGC 时代 ChatGPT 的全面调查”，*arXiv 预印本 arXiv:2304.06488*，2023 年。

+   [32] S. Ortiz，“什么是谷歌 Bard？这是你需要知道的一切”，2023，[在线]. 可用：[`www.zdnet.com/article/what-is-google-bard-heres-everything-you-need-to-know/`](https://www.zdnet.com/article/what-is-google-bard-heres-everything-you-need-to-know/)。[访问日期：2024 年 4 月 25 日]。

+   [33] 维基百科，“Bard（聊天机器人）”，2023，[在线]. 可用：[`en.wikipedia.org/wiki/Bard_(chatbot)`](https://en.wikipedia.org/wiki/Bard_(chatbot))。[访问日期：2024 年 4 月 25 日]。

+   [34] J. Xue, Y.-C. Wang, C. Wei, X. Liu, J. Woo, 和 C.-C. J. Kuo, “聊天机器人中的偏见与公平：概述”，*arXiv 预印本 arXiv:2309.08836*，2023 年。

+   [35] A. M. Turing, *计算机器和智能*。   Springer，2009 年。

+   [36] J. Weizenbaum, “Eliza——一个用于研究人类与机器之间自然语言沟通的计算机程序”，*ACM 通讯*，第 9 卷，第 1 期，页码 36–45，1966 年。

+   [37] A. Zimmerman, J. Janhonen, 和 E. Beer, “人类/人工智能关系：挑战、缺点及其对人类/人类关系的影响”，*人工智能与伦理*，页码 1–13，2023 年。

+   [38] K. M. Colby, S. Weber, 和 F. D. Hilf, “人工偏执”，*人工智能*，第 2 卷，第 1 期，页码 1–25，1971 年。

+   [39] K. M. Colby, “建模一个偏执的思维”，*行为与脑科学*，第 4 卷，第 4 期，页码 515–534，1981 年。

+   [40] M. T. Zemčík, “聊天机器人的简史”，*DEStech 计算机科学与工程学会论文集*，第 10 卷，2019 年。

+   [41] Wikipedia, “Racter”，2023 年，[在线]。可用: [`en.wikipedia.org/wiki/Racter`](https://en.wikipedia.org/wiki/Racter)。 [访问时间：2024 年 5 月 2 日]。

+   [42] B. A. Shawar 和 E. Atwell, “通过自适应对话导师促进语言学习者自主”，见 *第四届语料库语言学会议论文集*，第 3 卷，2007 年，页码 186–193。

+   [43] A. Kerlyl, P. Hall, 和 S. Bull, “将聊天机器人引入教育：面向自然语言协商开放学习者模型”，见 *国际创新技术与人工智能应用会议*。   Springer，2006 年，页码 179–192。

+   [44] S. Singh 和 H. K. Thakur, “基于技术的各种人工智能聊天机器人调查”，见 *2020 年第 8 届国际可靠性、信息通信技术与优化会议（趋势与未来方向）（ICRITO）*。   IEEE，2020 年，页码 1074–1079。

+   [45] O. Deryugina, “聊天机器人”，*科学技术信息处理*，第 37 卷，页码 143–147，2010 年。

+   [46] R. S. Wallace, *ALICE 的解剖学*。   Springer，2009 年。

+   [47] L. Bradeško 和 D. Mladenić, “通过洛布纳奖竞赛调查聊天机器人系统”，见 *斯洛文尼亚语言技术学会第八届语言技术会议论文集*，第 2 卷。   sn，2012 年，页码 34–37。

+   [48] H.-Y. Shum, X.-d. He, 和 D. Li, “从 Eliza 到小冰：社交聊天机器人的挑战与机遇”，*信息技术与电子工程前沿*，第 19 卷，页码 10–26，2018 年。

+   [49] E. Adamopoulou 和 L. Moussiades, “聊天机器人：历史、技术与应用”，*机器学习与应用*，第 2 卷，页码 100006，2020 年。

+   [50] Wikipedia, “Cleverbot”，2023 年，[在线]。可用: [`en.wikipedia.org/wiki/Cleverbot`](https://en.wikipedia.org/wiki/Cleverbot)。 [访问时间：2024 年 5 月 9 日]。

+   [51] Y. Chen, J. E. Argentinis, 和 G. Weber, “IBM Watson：认知计算如何应用于生命科学研究中的大数据挑战”，*临床治疗*，第 38 卷，第 4 期，页码 688–701，2016 年。

+   [52] R. High，“认知系统的时代：深入了解 IBM Watson 及其工作原理”，*IBM 公司，Redbooks*，第 1 卷，第 16 页，2012 年。

+   [53] L. Zhou, J. Gao, D. Li, 和 H.-Y. Shum，“小冰的设计与实现：一个富有同情心的社交聊天机器人”，*计算语言学*，第 46 卷，第 1 期，第 53-93 页，2020 年。

+   [54] M. B. Hoy，“Alexa，Siri，Cortana 和更多：语音助手介绍”，*医学参考服务季刊*，第 37 卷，第 1 期，第 81-88 页，2018 年。

+   [55] V. Kepuska 和 G. Bohouta，“下一代虚拟个人助理（微软 Cortana，苹果 Siri，亚马逊 Alexa 和谷歌 Home）”，在*2018 IEEE 第 8 届年度计算与通信研讨会与会议（CCWC）*。 IEEE，2018 年，第 99-103 页。

+   [56] J. Aron，“苹果的新语音助手 Siri 有多创新？”2011 年。

+   [57] T. Bolton, T. Dargahi, S. Belguith, M. S. Al-Rakhami, 和 A. H. Sodhro，“关于虚拟助理的安全性和隐私挑战”，*传感器*，第 21 卷，第 7 期，第 2312 页，2021 年。

+   [58] C. Wei, Y.-C. Wang, B. Wang, 和 C.-C. J. Kuo，“语言模型概述：近期发展与展望”，*arXiv 预印本 arXiv:2303.05759*，2023 年。

+   [59] C. Zhou, Q. Li, C. Li, J. Yu, Y. Liu, G. Wang, K. Zhang, C. Ji, Q. Yan, L. He *等*，“预训练基础模型的全面调查：从 BERT 到 ChatGPT 的历史”，*arXiv 预印本 arXiv:2302.09419*，2023 年。

+   [60] K. Antonopoulos，“什么是 ChatGPT，它对记者为何重要？”2023 年，[在线]。可用：[`institute.aljazeera.net/en/ajr/article/2229`](https://institute.aljazeera.net/en/ajr/article/2229)。 [访问日期：2024 年 5 月 8 日]。

+   [61] C. Metz，“谷歌 Bard 可以做什么（以及它不能做什么）”，2023 年，[在线]。可用：[`www.nytimes.com/2023/03/21/technology/google-bard-guide-test.html`](https://www.nytimes.com/2023/03/21/technology/google-bard-guide-test.html)。 [访问日期：2024 年 5 月 8 日]。

+   [62] S. Schechner，“谷歌的 Bard AI 聊天机器人增加更多语言以挑战 ChatGPT”，2023 年，[在线]。可用：[`www.wsj.com/articles/googles-bard-ai-chatbot-adds-more-languages-to-take-on-chatgpt-a2acfc5b`](https://www.wsj.com/articles/googles-bard-ai-chatbot-adds-more-languages-to-take-on-chatgpt-a2acfc5b)。 [访问日期：2024 年 4 月 25 日]。

+   [63] D. Bartz，“随着 ChatGPT 的流行激增，美国立法者开始关注”，2023 年，[在线]。可用：[`www.reuters.com/technology/chatgpts-popularity-explodes-us-lawmakers-take-an-interest-2023-02-13/`](https://www.reuters.com/technology/chatgpts-popularity-explodes-us-lawmakers-take-an-interest-2023-02-13/)。 [访问日期：2024 年 4 月 25 日]。

+   [64] C. David 和 J. Paul，“ChatGPT 和大型语言模型：风险是什么？”2023 年，[在线]。可用：[`www.ncsc.gov.uk/blog-post/chatgpt-and-large-language-models-whats-the-risk`](https://www.ncsc.gov.uk/blog-post/chatgpt-and-large-language-models-whats-the-risk)。 [访问日期：2024 年 5 月 8 日]。

+   [65] T. Lieu, “我是一名编程国会议员。人工智能让我感到恐惧，” 2023, [在线]. 可用: [`www.nytimes.com/2023/01/23/opinion/ted-lieu-ai-chatgpt-congress.html`](https://www.nytimes.com/2023/01/23/opinion/ted-lieu-ai-chatgpt-congress.html)。 [访问时间: 2024 年 4 月 24 日]。

+   [66] J. Choi, K. Hickman, A. Monahan, 和 D. Schwarcz, “Chatgpt 进入法学院。明尼苏达法律研究论文第 23-03 号. 2023,” 2023。

+   [67] F. C. Kitamura, “Chatgpt 正在塑造医疗写作的未来，但仍需人类判断，” p. e230171, 2023。

+   [68] A. Radford, K. Narasimhan, T. Salimans, I. Sutskever *等*, “通过生成预训练改善语言理解，” 2018。

+   [69] A. Radford, J. Wu, R. Child, D. Luan, D. Amodei, I. Sutskever *等*, “语言模型是无监督的多任务学习者，” *OpenAI 博客*, 卷 1, 第 8 期, p. 9, 2019。

+   [70] J. Ye, X. Chen, N. Xu, C. Zu, Z. Shao, S. Liu, Y. Cui, Z. Zhou, C. Gong, Y. Shen *等*, “对 GPT-3 和 GPT-3.5 系列模型的全面能力分析，” *arXiv 预印本 arXiv:2303.10420*, 2023。

+   [71] J. Devlin, M.-W. Chang, K. Lee, 和 K. Toutanova, “Bert: 深度双向 transformers 的预训练用于语言理解，” *arXiv 预印本 arXiv:1810.04805*, 2018。

+   [72] A. Chowdhery, S. Narang, J. Devlin, M. Bosma, G. Mishra, A. Roberts, P. Barham, H. W. Chung, C. Sutton, S. Gehrmann *等*, “Palm: 通过路径扩展语言建模，” *arXiv 预印本 arXiv:2204.02311*, 2022。

+   [73] H. Touvron, T. Lavril, G. Izacard, X. Martinet, M.-A. Lachaux, T. Lacroix, B. Rozière, N. Goyal, E. Hambro, F. Azhar *等*, “Llama: 开放和高效的基础语言模型，” *arXiv 预印本 arXiv:2302.13971*, 2023。

+   [74] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez, Ł. Kaiser, 和 I. Polosukhin, “注意力机制就是你所需的一切，” *神经信息处理系统进展*, 卷 30, 2017。

+   [75] T. Wolf, L. Debut, V. Sanh, J. Chaumond, C. Delangue, A. Moi, P. Cistac, T. Rault, R. Louf, M. Funtowicz *等*, “Transformers: 最新自然语言处理技术，” 收录于 *2020 年自然语言处理经验方法会议论文集: 系统展示*, 2020, 页 38–45。

+   [76] B. Zhang, B. Ghorbani, A. Bapna, Y. Cheng, X. Garcia, J. Shen, 和 O. Firat, “检验语言模型架构在机器翻译中的扩展性和迁移性，” 收录于 *国际机器学习会议*. PMLR, 2022, 页 26 176–26 192。

+   [77] P. Liu, W. Yuan, J. Fu, Z. Jiang, H. Hayashi, 和 G. Neubig, “预训练、提示和预测: 自然语言处理中的提示方法系统综述，” *ACM 计算机调查*, 卷 55, 第 9 期, 页 1–35, 2023。

+   [78] L. Dong, N. Yang, W. Wang, F. Wei, X. Liu, Y. Wang, J. Gao, M. Zhou, 和 H.-W. Hon, “统一语言模型预训练用于自然语言理解和生成，” *神经信息处理系统进展*, 卷 32, 2019。

+   [79] J. 魏，M. 鲍斯马，V. Y. 赵，K. 古，A. W. 于，B. 莱斯特，N. 杜，A. M. 戴和 Q. V. 勒，“Finetuned 语言模型是零-shot 学习者”，*arXiv preprint arXiv:2109.01652*，2021。

+   [80] V. 山，A. 韦布森，C. 拉菲尔，S. H. 巴赫，L. Sutawika，Z. Alyafeai，A. 查芬，A. 施蒂格勒，T. L. Scao，A. 拉贾等，“多任务提示训练实现零-shot 任务泛化”，*arXiv preprint arXiv:2110.08207*，2021 年。

+   [81] L. 欧阳，J. 吴，X. 江，D. 阿尔梅达，C. 韦恩莱特，P. 米什金，C. 张，S. 阿加瓦尔，K. 斯拉马，A. 雷等，“用人类反馈训练语言模型遵循指示”，*神经信息处理系统进展*，vol. 35，pp. 27 730–27 744，2022 年。

+   [82] J. 魏，X. 王，D. 斯库曼斯，M. 鲍斯马，E. 池，Q. 乐，和 D. 周，“一连串的思考提示引发大语言模型的推理”，*arXiv preprint arXiv:2201.11903*，2022 年。

+   [83] Y. 邦，S. 卡海瓦加亚，N. 李，W. 戴，D. 苏，B. 威利，H. 洛文尼亚，Z. 吉，T. 余，W. 钟等，“Chatgpt 在推理，幻觉和交互性上的多任务，多语言，多模态评估”，*arXiv preprint arXiv:2302.04023*，2023 年。

+   [84] 吴，S. 何，J. 刘，S. 孙，K. 刘，Q.-L. 韩，和 Y. 唐，“Chatgpt 简介: 历史，现状和潜在未来发展的简要概述”，*IEEE/CAA Journal of Automatica Sinica*，vol. 10，no. 5，pp. 1122–1136，2023 年。

+   [85] S. 布贝克，V. 钱德拉塞卡兰，R. 埃尔丹，J. 格尔克，E. 霍尔维兹，E. 卡玛尔，P. 李，Y. T. 李，Y. 李，S. 兰德伯格等，“人工通用智能的火花: GPT-4 的早期实验”，*arXiv preprint arXiv:2303.12712*，2023 年。

+   [86] 维基百科，“Chatgpt”，2023 年，[在线]. 可访问：[`en.wikipedia.org/wiki/ChatGPT`](https://en.wikipedia.org/wiki/ChatGPT)。[访问日期：2024 年 5 月 9 日]。

+   [87] R. 阿里，O. Y. 唐，I. D. 康诺利，J. S. 弗里德利，J. H. 申，P. L. Z. 沙利文，D. Cielo，A. A. Oyelese，C. E. 多伯斯坦，A. E. 特弗恩等，“Chatgpt，GPT-4 和 Google 巴尔德在神经外科口头委员会准备问题库上的表现”，*神经外科*，pp. 10–1227，2022 年。

+   [88] A. 赫特莱，“Bard vs. chatgpt: 有什么不同？” 2023，[在线]. 可访问：[`www.techtarget.com/whatis/feature/Bard-vs-ChatGPT-Whats-the-difference`](https://www.techtarget.com/whatis/feature/Bard-vs-ChatGPT-Whats-the-difference)。[访问日期：2024 年 5 月 9 日]。

+   [89] A. 贾法，“Chatgpt 现在可以浏览互联网以获取更新的信息”，2023，[在线]. 可访问：[`www.aljazeera.com/news/2023/9/28/chatgpt-can-now-browse-the-internet-for-updated-information`](https://www.aljazeera.com/news/2023/9/28/chatgpt-can-now-browse-the-internet-for-updated-information)。[访问日期：2024 年 5 月 2 日]。

+   [90] A. 约翰斯，“GPT-4 turbo: OpenAI 宣布 GPT-4 turbo 更快、更便宜”，2023，[在线]. 可访问：[`blog.securecortex.com/2023/11/gpt-4-turbo-openai-announced-gpt-4.html`](https://blog.securecortex.com/2023/11/gpt-4-turbo-openai-announced-gpt-4.html)。[访问日期：2024 年 5 月 8 日]。

+   [91] PCWorld, “Google Bard AI 正式更名为 Gemini，非正式地变得无关紧要，” 2023, [在线]. 网址：[`www.pcworld.com/article/2230933/google-bard-ai-is-officially-gemini-unofficially-irrelevant.html`](https://www.pcworld.com/article/2230933/google-bard-ai-is-officially-gemini-unofficially-irrelevant.html). [访问日期：2024 年 5 月 8 日]。

+   [92] S. Ortiz, “什么是 Bing 聊天？这里是你需要知道的一切，” 2023, [在线]. 网址：[`www.zdnet.com/article/what-is-the-new-bing-heres-everything-you-need-to-know/`](https://www.zdnet.com/article/what-is-the-new-bing-heres-everything-you-need-to-know/). [访问日期：2024 年 4 月 24 日]。

+   [93] M. Freeman-Mills, “Bing 聊天是什么，如何运作？AI 聊天解释，” 2023, [在线]. 网址：[`www.pocket-lint.com/what-is-bing-chat-explained/`](https://www.pocket-lint.com/what-is-bing-chat-explained/). [访问日期：2024 年 4 月 24 日]。

+   [94] A. Conway, “Bing 聊天：它是什么，以及如何运作？” 2023, [在线]. 网址：[`www.xda-developers.com/bing-chat/`](https://www.xda-developers.com/bing-chat/). [访问日期：2024 年 5 月 2 日]。

+   [95] Simplilearn, “什么是 Bing 聊天？释放 GPT-4 的强大功能与 Bing 聊天，” 2023, [在线]. 网址：[`www.simplilearn.com/bing-chat-article`](https://www.simplilearn.com/bing-chat-article). [访问日期：2024 年 5 月 9 日]。

+   [96] Anthropic, “介绍 Claude，” 2023, [在线]. 网址：[`www.anthropic.com/news/introducing-claude`](https://www.anthropic.com/news/introducing-claude). [访问日期：2024 年 5 月 2 日]。

+   [97] J. Gillham, “2023 年第四季度 75+Claude AI 模型统计数据，” 2023, [在线]. 网址：[`originality.ai/blog/claude-ai-statistics`](https://originality.ai/blog/claude-ai-statistics). [访问日期：2024 年 4 月 25 日]。

+   [98] E. Lozić和 B. Štular, “ChatGPT、Bard、Bing、Claude 2、Aria 与人类专家。AI 聊天机器人在科学写作中的表现如何？（版本 23q3）,” *arXiv 预印本 arXiv:2309.08636*，2023。

+   [99] Y. Bai, S. Kadavath, S. Kundu, A. Askell, J. Kernion, A. Jones, A. Chen, A. Goldie, A. Mirhoseini, C. McKinnon *等*, “宪法 AI：来自 AI 反馈的无害性，” *arXiv 预印本 arXiv:2212.08073*，2022。

+   [100] Y. Bai, A. Jones, K. Ndousse, A. Askell, A. Chen, N. DasSarma, D. Drain, S. Fort, D. Ganguli, T. Henighan *等*, “通过人类反馈的强化学习训练一个有帮助且无害的助手，” *arXiv 预印本 arXiv:2204.05862*，2022。

+   [101] N. Y. Motlagh, M. Khajavi, A. Sharifi 和 M. Ahmadi, “人工智能对数字教育演变的影响：OpenAI 文本生成工具的比较研究，包括 ChatGPT、Bing 聊天、Bard 和 Ernie，” *arXiv 预印本 arXiv:2309.02029*，2023。

+   [102] Z. Yang, “中国科技巨头百度刚刚发布了它对 ChatGPT 的回应，” 2023, [在线]. 网址：[`www.technologyreview.com/2023/03/16/1069919/baidu-ernie-bot-chatgpt-launch/`](https://www.technologyreview.com/2023/03/16/1069919/baidu-ernie-bot-chatgpt-launch/). [访问日期：2024 年 4 月 25 日]。

+   [103] J. Rudolph, S. Tan, 和 S. Tan, “聊天机器人大战: Bard、Bing Chat、ChatGPT、Ernie 及其他。新的 AI 金矿热潮及其对高等教育的影响，” *Journal of Applied Learning and Teaching*，第 6 卷，第 1 期，2023 年。

+   [104] Z. Huang, “中国首款主要聊天机器人无需像 ChatGPT 那样优秀，” 2023 年，[在线]. 可用链接: [`www.bloomberg.com/news/newsletters/2023-03-21/baidu-s-ernie-bot-aims-to-be-first-in-chatgpt-free-market-in-china`](https://www.bloomberg.com/news/newsletters/2023-03-21/baidu-s-ernie-bot-aims-to-be-first-in-chatgpt-free-market-in-china). [访问日期: 2024 年 5 月 1 日]。

+   [105] J. Rodriguez, “深入了解 Sparrow: DeepMind 的 ChatGPT 替代品的基础，” 2023 年，[在线]. 可用链接: [`jrodthoughts.medium.com/inside-sparrow-the-foundation-of-deepminds-chatgpt-alternative-854df43569fd`](https://jrodthoughts.medium.com/inside-sparrow-the-foundation-of-deepminds-chatgpt-alternative-854df43569fd). [访问日期: 2024 年 4 月 25 日]。

+   [106] Wikipedia, “Grok (聊天机器人),” 2023 年，[在线]. 可用链接: [`en.wikipedia.org/wiki/Grok_(chatbot)`](https://en.wikipedia.org/wiki/Grok_(chatbot)). [访问日期: 2024 年 5 月 9 日]。

+   [107] D. Milmo, “埃隆·马斯克推出 Grok，一款具有‘叛逆’特质的 AI 聊天机器人，” 2023 年，[在线]. 可用链接: [`www.theguardian.com/technology/2023/nov/05/elon-musk-unveils-grok-an-ai-chatbot-with-a-rebellious-streak`](https://www.theguardian.com/technology/2023/nov/05/elon-musk-unveils-grok-an-ai-chatbot-with-a-rebellious-streak). [访问日期: 2024 年 4 月 25 日]。

+   [108] K. Piper, “为什么 Meta 的新 AI 聊天机器人这么糟？” 2023 年，[在线]. 可用链接: [`www.vox.com/future-perfect/23307252/meta-facebook-bad-ai-chatbot-blenderbot`](https://www.vox.com/future-perfect/23307252/meta-facebook-bad-ai-chatbot-blenderbot). [访问日期: 2024 年 5 月 1 日]。

+   [109] M. A. R. Vasconcelos 和 R. P. d. Santos, “通过 ChatGPT 和 Bing Chat 作为思考对象来增强 STEM 学习: 一项案例研究，” *arXiv 预印本 arXiv:2305.02202*，2023 年。

+   [110] X.-Q. Dao, “在越南教育中应该使用哪个大型语言模型: ChatGPT、Bing Chat 还是 Bard？” *Bing Chat, or Bard*，2023 年。

+   [111] D. Xuan-Quy, L. Ngoc-Bich, V. The-Duy, P. Xuan-Dung, N. Bac-Bien, N. Van-Tien, N. Thi-My-Thanh, 和 N. Hong-Phuoc, “Vnhsge: 越南高中毕业考试数据集用于大型语言模型，” *arXiv 预印本 arXiv:2305.12199*，2023 年。

+   [112] A. J. Thirunavukarasu, D. S. J. Ting, K. Elangovan, L. Gutierrez, T. F. Tan, 和 D. S. W. Ting, “医学中的大型语言模型，” *Nature medicine*，第 29 卷，第 8 期，页码 1930–1940，2023 年。

+   [113] T. AI, “探索 Chat GPT 的增强功能: Turbo、个性化和图像编辑，” 2024 年，[在线]. 可用链接: [`www.toolify.ai/ai-news/exploring-the-enhanced-features-of-chat-gpt-turbo-personalization-and-image-editing-1170215`](https://www.toolify.ai/ai-news/exploring-the-enhanced-features-of-chat-gpt-turbo-personalization-and-image-editing-1170215). [访问日期: 2024 年 5 月 1 日]。

+   [114] N. S. Foundation，“美国科学与工程领域的外籍学生和工作人员”，2020 年，[在线]。可用链接： [`www.nsf.gov/nsb/sei/one-pagers/Foreign-Born.pdf`](https://www.nsf.gov/nsb/sei/one-pagers/Foreign-Born.pdf)。 [访问日期：2024 年 4 月 25 日]。

+   [115] S. Kim，“用 Openai Chatgpt 替代 Grammarly Premium”，2023 年，[在线]。可用链接： [`medium.com/geekculture/replace-grammarly-premium-with-openai-chatgpt-320049179c79`](https://medium.com/geekculture/replace-grammarly-premium-with-openai-chatgpt-320049179c79)。 [访问日期：2024 年 4 月 25 日]。

+   [116] F. M. Megahed, Y.-J. Chen, J. A. Ferris, S. Knoth 和 L. A. Jones-Farmer，“生成型 AI 模型如 Chatgpt 在 SPC 实践、教育和研究中的（误）用：一项探索性研究”，*质量工程*，页码 1–29，2023 年。

+   [117] S. Khan，“利用 GPT-4 使所有学生受益：一种非营利性平等访问方法”，*可汗学院*，2023 年。

+   [118] D. Team，“推出 Duolingo Max：由 GPT-4 驱动的学习体验”，*检索于 3 月*，第 15 卷，2023 年。

+   [119] O. Topsakal 和 E. Topsakal，“为儿童开发的外语教学软件框架：利用 AR、语音机器人和 Chatgpt（大型语言模型）”，*认知系统期刊*，第 7 卷，第 2 期，页码 33–38，2022 年。

+   [120] X. Zhai，“Chatgpt 用于下一代科学学习”，*XRDS: Crossroads, The ACM Magazine for Students*，第 29 卷，第 3 期，页码 42–46，2023 年。

+   [121] X. Wang, Z. Gong, G. Wang, J. Jia, Y. Xu, J. Zhao, Q. Fan, S. Wu, W. Hu 和 X. Li，“Chatgpt 在中国国家医学执照考试中的表现”，2023 年。

+   [122] E. Kasneci, K. Seßler, S. Küchemann, M. Bannert, D. Dementieva, F. Fischer, U. Gasser, G. Groh, S. Günnemann, E. Hüllermeier *等*，“Chatgpt 的好处？大型语言模型在教育中的机遇与挑战”，*学习与个体差异*，第 103 卷，页码 102274，2023 年。

+   [123] S. Chandha, R. Sucheth 和 T. Ghosal，“背景介绍：人工智能如何重塑我们消费和传递研究的方式”，*Upstream*，2023 年。

+   [124] Ö. Aydın 和 E. Karaarslan，“Openai chatgpt 生成的文献综述：医疗保健中的数字双胞胎”，*可在 SSRN 4308687 获取*，2022 年。

+   [125] Y. Jiang，“基于 LLM 的金融分析聊天机器人”，2023 年，[在线]。可用链接： [`www.linkedin.com/pulse/llm-based-financial-analytics-chatbot-yicheng-jiang/`](https://www.linkedin.com/pulse/llm-based-financial-analytics-chatbot-yicheng-jiang/)。 [访问日期：2024 年 5 月 8 日]。

+   [126] M.-H. Temsah, A. Jamal 和 J. A. Al-Tawfiq，“关于新冠疫情后超额死亡的 Chatgpt 反思”，2023 年。

+   [127] A. Gilson, C. W. Safranek, T. Huang, V. Socrates, L. Chi, R. A. Taylor, D. Chartash *等*，“Chatgpt 在美国医学执照考试中的表现如何？大型语言模型对医学教育和知识评估的影响”，*JMIR 医学教育*，第 9 卷，第 1 期，页码 e45312，2023 年。

+   [128] A. Hamidi 和 K. Roberts, “针对患者特定 EHR 问题的 AI 聊天机器人评估，” *arXiv 预印本 arXiv:2306.02549*，2023 年。

+   [129] R. Kirk, S. Simpson Matthew, M. Voorhees Ellen 和 R. Hersh William, “TREC 2016 临床决策支持赛道概述，” 见 *第 15 届文本检索会议论文集*，2016 年。

+   [130] W. H. Kruskal 和 W. A. Wallis, “在单一标准方差分析中使用秩次，” *美国统计协会期刊*，第 47 卷，第 260 期，第 583–621 页，1952 年。

+   [131] Z. Azizi, P. Alipour, S. Gomez, C. Broadwin, S. Islam, A. Sarraju, A. Rogers, A. T. Sandhu 和 F. Rodriguez, “评估从基于聊天的人工智能算法中获得的关于房颤的建议：对患者和临床医生的评估，” *循环：心律失常与电生理学*，第 e012015 页，2023 年。

+   [132] H. Nori, N. King, S. M. McKinney, D. Carignan 和 E. Horvitz, “GPT-4 在医学挑战问题上的能力，” *arXiv 预印本 arXiv:2303.13375*，2023 年。

+   [133] R. Yang, T. F. Tan, W. Lu, A. J. Thirunavukarasu, D. S. W. Ting 和 N. Liu, “大型语言模型在医疗保健中的发展、应用与挑战，” *健康科学*，第 2 卷，第 4 期，第 255–263 页，2023 年。

+   [134] K. Leung, “Macy the ai pharmacist!” 2023 年，[在线]. 可用： [`www.linkedin.com/posts/kennethleungty_generativeai-ai-pharmacist-activity-7031533843429949440-pVZb/`](https://www.linkedin.com/posts/kennethleungty_generativeai-ai-pharmacist-activity-7031533843429949440-pVZb/)。 [访问日期：2024 年 4 月 25 日]。

+   [135] S. Chen, B. H. Kann, M. B. Foote, H. J. Aerts, G. K. Savova, R. H. Mak 和 D. S. Bitterman, “使用人工智能聊天机器人获取癌症治疗信息，” *JAMA 肿瘤学*，第 9 卷，第 10 期，第 1459–1462 页，2023 年。

+   [136] S. Koga, N. B. Martin 和 D. W. Dickson, “评估大型语言模型的性能：Chatgpt 和 Google Bard 在神经退行性疾病的临床病理会议中生成鉴别诊断的表现，” *脑病理学*，第 e13207 页，2023 年。

+   [137] A. K. D. Dhanvijay, M. J. Pinjar, N. Dhokane, S. R. Sorte, A. Kumari, H. Mondal 和 A. K. Dhanvijay, “大型语言模型（Chatgpt、Bing 搜索和 Google Bard）在解决生理学案例小样中的表现，” *Cureus*，第 15 卷，第 8 期，2023 年。

+   [138] Z. W. Lim, K. Pushpanathan, S. M. E. Yew, Y. Lai, C.-H. Sun, J. S. H. Lam, D. Z. Chen, J. H. L. Goh, M. C. J. Tan, B. Sheng *等*，“大型语言模型在近视护理中的性能基准：对 Chatgpt-3.5、Chatgpt-4.0 和 Google Bard 的比较分析，” *EBioMedicine*，第 95 卷，2023 年。

+   [139] J. G. Meyer, R. J. Urbanowicz, P. C. Martin, K. O’Connor, R. Li, P.-C. Peng, T. J. Bright, N. Tatonetti, K. J. Won 和 G. Gonzalez-Hernandez *等*，“Chatgpt 和大型语言模型在学术界的机会与挑战，” *生物数据挖掘*，第 16 卷，第 1 期，第 20 页，2023 年。

+   [140] N. M. S. Surameery 和 M. Y. Shakor, “使用 ChatGPT 解决编程错误，” *国际信息技术与计算机工程杂志 (IJITC) ISSN: 2455-5290*，第 3 卷，第 01 期，第 17–22 页，2023 年。

+   [141] M. Nejjar, L. Zacharias, F. Stiehle 和 I. Weber, “科学领域的 LLMs：用于代码生成和数据分析，” *arXiv 预印本 arXiv:2311.16733*，2023 年。

+   [142] M. Dowling 和 B. Lucey, “ChatGPT 在（金融）研究中的应用：香蕉拉玛猜想，” *金融研究快报*，第 53 卷，第 103662 页，2023 年。

+   [143] S. S. Gill 和 R. Kaur, “ChatGPT：愿景与挑战，” *物联网与网络物理系统*，第 3 卷，第 262–271 页，2023 年。

+   [144] İ. M. Altan 和 M. KILIÇ, “科幻到现实：Bing AI 作为投资顾问，” *经济经营与管理期刊*，第 7 卷，第 2 期，第 240–260 页。

+   [145] D. Dai, L. Dong, Y. Hao, Z. Sui, B. Chang 和 F. Wei, “预训练变换器中的知识神经元，” *arXiv 预印本 arXiv:2104.08696*，2021 年。

+   [146] K. Meng, D. Bau, A. Andonian 和 Y. Belinkov, “在 GPT 中定位和编辑事实关联，” *神经信息处理系统进展*，第 35 卷，第 17,359–17,372 页，2022 年。

+   [147] E. M. Bender, T. Gebru, A. McMillan-Major 和 S. Shmitchell, “随机鹦鹉的危险：语言模型能否过大？” 收录于 *2021 年 ACM 公平性、问责制和透明度会议论文集*，2021 年，第 610–623 页。

+   [148] P. Villalobos, J. Sevilla, L. Heim, T. Besiroglu, M. Hobbhahn 和 A. Ho, “我们会数据枯竭吗？对机器学习数据集扩展限制的分析，” *arXiv 预印本 arXiv:2211.04325*，2022 年。

+   [149] S. Saghafian, “ChatGPT 背后的分析科学：人类、算法，还是人类-算法半人马？” 2023 年。

+   [150] M. Agarwal, P. Sharma 和 A. Goswami, “分析 ChatGPT、Bard 和 Bing 在医学生理学中生成基于推理的多项选择题的适用性，” *Cureus*，第 15 卷，第 6 期，2023 年。

+   [151] L. Z. Cai, A. Shaheen, A. Jin, R. Fukui, S. Y. Jonathan, N. Yannuzzi 和 C. Alabiad, “生成性大语言模型在眼科学 board 风格问题上的表现，” *美国眼科学杂志*，2023 年。

+   [152] G. Sutcliffe, J. McKeown 和 A. Steen, “与 Bard 对话，” 收录于 *第 14 届国际逻辑实现研讨会论文集*，2023 年。

+   [153] P. Nguyen, P. Nguyen, P. Bruneau, L. Cao, J. Wang 和 H. Truong, “评估 Google Bard 在越南国家高中毕业考试数学测试中的数学表现，” 2023 年。

+   [154] S. Wang, H. Scells, B. Koopman 和 G. Zuccon, “ChatGPT 能否编写出有效的布尔查询以进行系统评价文献检索？” *arXiv 预印本 arXiv:2302.03495*，2023 年。

+   [155] A. Borji, “ChatGPT 失败的分类档案，” *arXiv 预印本 arXiv:2302.03494*，2023 年。

+   [156] C. Rudin，“停止为高风险决策解释黑箱机器学习模型，改用可解释模型，” *Nature machine intelligence*，第 1 卷，第 5 期，第 206–215 页，2019 年。

+   [157] A. Rao, J. Kim, M. Kamineni, M. Pang, W. Lie, 和 M. D. Succi，“评估 chatgpt 作为放射决策辅助工具，” *medRxiv*，第 2023–02 页，2023 年。

+   [158] P. Schramowski, C. Turan, N. Andersen, C. A. Rothkopf 和 K. Kersting，“大型预训练语言模型包含类似人类的对错偏见，” *Nature Machine Intelligence*，第 4 卷，第 3 期，第 258–268 页，2022 年。

+   [159] M. Fraiwan 和 N. Khasawneh，“chatgpt 在教育、营销、软件工程和医疗保健中的应用综述：优点、缺点及研究方向，” *arXiv 预印本 arXiv:2305.00237*，2023 年。

+   [160] M. Phillips, H. Marsden, W. Jaffe, R. N. Matin, G. N. Wali, J. Greenhalgh, E. McGrath, R. James, E. Ladoyanni, A. Bewley *等*，“评估人工智能算法检测皮肤病变图像中黑色素瘤的准确性，” *JAMA network open*，第 2 卷，第 10 期，第 e1 913 436–e1 913 436 页，2019 年。

+   [161] M. C. Oca, L. Meller, K. Wilson, A. O. Parikh, A. McCoy, J. Chang, R. Sudharshan, S. Gupta 和 S. Zhang-Nunes，“AI 聊天机器人眼科医生建议中的偏见和不准确性，” *Cureus*，第 15 卷，第 9 期，2023 年。

+   [162] R. W. McGee，“chat gpt 是否对保守派有偏见？一项实证研究，” *实证研究（2023 年 2 月 15 日）*，2023 年。

+   [163] J. Hartmann, J. Schwenzow 和 M. Witte，“对话 AI 的政治意识形态：chatgpt 的亲环境、左自由主义取向的汇聚证据，” *arXiv 预印本 arXiv:2301.01768*，2023 年。

+   [164] S. McCallum，“chatgpt 因隐私问题在意大利被禁，” *BBC News*，2023 年。

+   [165] OpenAI，“隐私政策，” 2023 年 5 月 10 日，[在线]。可用：[`openai.com/policies/privacy-policy`](https://openai.com/policies/privacy-policy)。 [访问时间：2024 年 4 月 25 日]。

+   [166] M. Liebrenz, R. Schleifer, A. Buadze, D. Bhugra 和 A. Smith，“使用 chatgpt 生成学术内容：医学出版中的伦理挑战，” *The Lancet Digital Health*，第 5 卷，第 3 期，第 e105–e106 页，2023 年。

+   [167] A. Shiri，“chatgpt 与学术诚信，” *Information Matters*，第 3 卷，第 2 期，2023 年。

+   [168] M. R. King 和 ChatGPT，“关于人工智能、聊天机器人和高等教育中的抄袭的对话，” *Cellular and Molecular Bioengineering*，第 16 卷，第 1 期，第 1–2 页，2023 年。

+   [169] M. Khalil 和 E. Er，“chatgpt 会让你被抓住吗？重新思考抄袭检测，” *arXiv 预印本 arXiv:2302.04335*，2023 年。

+   [170] T. Susnjak, “Chatgpt：在线考试诚信的终结？” *arXiv 预印本 arXiv:2212.09292*，2022 年。

+   [171] K. Wiggers，“Openai 发布检测 AI 生成文本（包括 chatgpt）的工具，” *2023 年 3 月*，第 12 期，第 2023 页，2023 年。

+   [172] H. Gimpel, K. Hall, S. Decker, T. Eymann, L. Lämmermann, A. Mädche, M. Röglinger, C. Ruiner, M. Schoch, M. Schoop *等*，“解锁 GPT-4 和 ChatGPT 等生成式 AI 模型及系统在高等教育中的潜力：学生和讲师的指南”，霍恩海姆商业、经济与社会科学讨论论文，技术报告，2023 年。

+   [173] X.-Q. Dao 和 N.-B. Le，“ChatGPT 很好，但 Bing Chat 对越南学生来说更好”， *arXiv 预印本 arXiv:2307.08272*，2023 年。

+   [174] T. F. Tan, A. J. Thirunavukarasu, J. P. Campbell, P. A. Keane, L. R. Pasquale, M. D. Abramoff, J. Kalpathy-Cramer, F. Lum, J. E. Kim, S. L. Baxter *等*， “通过 ChatGPT 和其他大型语言模型在眼科学中的生成式人工智能：临床应用与挑战”， *Ophthalmology Science*，第 3 卷，第 4 期，页码 100394，2023 年。

+   [175] M. D. Abràmoff, B. Cunningham, B. Patel, M. B. Eydelman, T. Leng, T. Sakamoto, B. Blodi, S. M. Grenon, R. M. Wolf, A. K. Manrai *等*，“使用眼科图像的人工智能基础考虑”， *Ophthalmology*，第 129 卷，第 2 期，页码 e14–e32，2022 年。

+   [176] T. Y. Zhuo, Y. Huang, C. Chen 和 Z. Xing，“探讨 ChatGPT 的人工智能伦理：诊断分析”， *arXiv 预印本 arXiv:2301.12867*，2023 年。

+   [177] A. J. Thirunavukarasu, R. Hassan, S. Mahmood, R. Sanghera, K. Barzangi, M. El Mukashfi 和 S. Shah，“在普通实践中试用大型语言模型（ChatGPT）与应用知识测试：观察研究展示了初级护理中的机会和局限性”， *JMIR 医学教育*，第 9 卷，第 1 期，页码 e46599，2023 年。

+   [178] G. Sebastian，“ChatGPT 和其他 AI 聊天机器人中的隐私和数据保护：保护用户信息的策略”， *可在 SSRN 4454761 上获得*，2023 年。

+   [179] M. Al-Hawawreh, A. Aljuhani 和 Y. Jararweh，“ChatGPT 在网络安全中的应用：实际应用、挑战与未来方向”， *Cluster Computing*，第 26 卷，第 6 期，页码 3421–3436，2023 年。

+   [180] E. Derner 和 K. Batistič，“超越安全保障：探索 ChatGPT 的安全风险”， *arXiv 预印本 arXiv:2305.08005*，2023 年。

+   [181] B. Dash 和 P. Sharma，“ChatGPT 和深度伪造算法是否危害了网络安全行业？一项综述”， *国际工程与应用科学杂志*，第 10 卷，第 1 期，2023 年。

+   [182] P. with Code，“在 MMLU 上的多任务语言理解”，2024 年，[在线]。可用： [`paperswithcode.com/sota/multi-task-language-understanding-on-mmlu?tag_filter=318`](https://paperswithcode.com/sota/multi-task-language-understanding-on-mmlu?tag_filter=318)。 [访问时间：2024 年 5 月 1 日]。

+   [183] J. Wei, Y. Tay, R. Bommasani, C. Raffel, B. Zoph, S. Borgeaud, D. Yogatama, M. Bosma, D. Zhou, D. Metzler *等*，“大型语言模型的突现能力”， *arXiv 预印本 arXiv:2206.07682*，2022 年。

+   [184] J. Kaplan, S. McCandlish, T. Henighan, T. B. Brown, B. Chess, R. Child, S. Gray, A. Radford, J. Wu, 和 D. Amodei，“神经语言模型的扩展规律，” *arXiv 预印本 arXiv:2001.08361*，2020 年。

+   [185] D. Hendrycks, C. Burns, S. Basart, A. Zou, M. Mazeika, D. Song, 和 J. Steinhardt，“大规模多任务语言理解的测量，” *arXiv 预印本 arXiv:2009.03300*，2020 年。

+   [186] X. Jiao, Y. Yin, L. Shang, X. Jiang, X. Chen, L. Li, F. Wang, 和 Q. Liu，“TinyBERT：为自然语言理解提炼 BERT，” *arXiv 预印本 arXiv:1909.10351*，2019 年。

+   [187] G. Hinton, O. Vinyals, 和 J. Dean，“在神经网络中提炼知识，” *arXiv 预印本 arXiv:1503.02531*，2015 年。

+   [188] Z. Sun, H. Yu, X. Song, R. Liu, Y. Yang, 和 D. Zhou，“MobileBERT：一种适用于资源受限设备的紧凑型任务无关 BERT，” *arXiv 预印本 arXiv:2004.02984*，2020 年。

+   [189] M. A. Gordon, K. Duh, 和 N. Andrews，“压缩 BERT：研究权重修剪对迁移学习的影响，” *arXiv 预印本 arXiv:2002.08307*，2020 年。

+   [190] T. Chen, J. Frankle, S. Chang, S. Liu, Y. Zhang, Z. Wang, 和 M. Carbin，“针对预训练 BERT 网络的彩票票假设，” *神经信息处理系统进展*，第 33 卷，页码 15 834–15 846，2020 年。

+   [191] S. Shen, Z. Dong, J. Ye, L. Ma, Z. Yao, A. Gholami, M. W. Mahoney, 和 K. Keutzer，“Q-BERT：基于 Hessian 的 BERT 超低精度量化，” 收录于 *AAAI 人工智能会议论文集*，第 34 卷，第 05 期，2020 年，页码 8815–8821。

+   [192] H. Bai, W. Zhang, L. Hou, L. Shang, J. Jin, X. Jiang, Q. Liu, M. Lyu, 和 I. King，“BinaryBERT：推动 BERT 量化的极限，” *arXiv 预印本 arXiv:2012.15701*，2020 年。

+   [193] Y. Cheng, D. Wang, P. Zhou, 和 T. Zhang，“深度神经网络模型压缩与加速的综述，” *arXiv 预印本 arXiv:1710.09282*，2017 年。

+   [194] S. Pan, L. Luo, Y. Wang, C. Chen, J. Wang, 和 X. Wu，“统一大型语言模型和知识图谱：一个路线图，” *arXiv 预印本 arXiv:2306.08302*，2023 年。

+   [195] J. Sun, C. Xu, L. Tang, S. Wang, C. Lin, Y. Gong, H.-Y. Shum, 和 J. Guo，“Think-on-Graph：大型语言模型与知识图谱的深度与负责任的推理，” *arXiv 预印本 arXiv:2307.07697*，2023 年。

+   [196] C.-C. J. Kuo 和 A. M. Madni，“绿色学习：简介、示例与展望，” *视觉通信与图像表征期刊*，第 90 卷，文章编号 103685，2023 年。

+   [197] R. Schwartz, J. Dodge, N. A. Smith, 和 O. Etzioni，“绿色人工智能，” *计算机协会通讯*，第 63 卷，第 12 期，页码 54–63，2020 年。

+   [198] P. Sharma, N. Ding, S. Goodman, 和 R. Soricut，“概念化标题：一个清理过的、超义词化的图像替代文本数据集用于自动图像描述，” 收录于 *第 56 届计算语言学协会年会（第 1 卷：长篇论文）*，2018 年，页码 2556–2565。

+   [199] C. 郭，Y. 卢，Y. 斗，和 F.-Y. 王，“ChatGPT 能否促进艺术创作：平行艺术对想象力智能的需求”，*IEEE/CAA 自动化学报*，第 10 卷，第 4 期，pp. 835–838，2023 年。

+   [200] H. 杜，S. 滕，H. 陈，J. 马，X. 王，C. 购，B. 李，S. 马，Q. 苗，X. 纳 *等*，“与 ChatGPT 谈论智能车辆：IEEE TIV 视角”，*IEEE 智能车辆学报*，2023 年。

+   [201] Y. 高，W. 汤，E. Q. 吴，W. 陈，G. 朱，和 F.-Y. 王，“与 ChatGPT 谈论智能驾驶的互动引擎”，*IEEE 智能车辆学报*，2023 年。

+   [202] J. 张，J. 普，J. 薛，M. 杨，X. 许，X. 王，和 F.-Y. 王，“Hivegpt：人机增强的智能车辆与生成预训练变换器”，*IEEE 智能车辆学报*，2023 年。

+   [203] F.-Y. 王，J. 杨，X. 王，J. 李，和 Q.-L. 韩，“与 ChatGPT 谈论工业 5.0：智能产业的学习与决策”，*IEEE/CAA 自动化学报*，第 10 卷，第 4 期，pp. 831–834，2023 年。

+   [204] F.-Y. 王，J. 李，R. 秦，J. 朱，H. 莫，和 B. 胡，“ChatGPT 在计算社会系统中的应用：从对话应用到以人为本的操作系统”，*IEEE 计算社会系统学报*，第 10 卷，第 2 期，pp. 414–425，2023 年。

+   [205] D. 韦宁格，“SMILES，一种化学语言和信息系统。1. 方法学和编码规则介绍”，*化学信息与计算科学学报*，第 28 卷，第 1 期，pp. 31–36，1988 年。

+   [206] H. 哈尔库斯，K. 法瓦兹，K. G. 辛，和 K. 阿贝尔，“$\{$PriBots$\}$：与聊天机器人进行对话隐私保护”，在*第十二届可用隐私与安全研讨会（SOUPS 2016）*，2016 年。

+   [207] M. 哈萨尔，J. 诺瓦科娃，K. 阿赫迈德·萨盖尔，H. 阿卜杜拉，V. 斯纳谢尔，和 L. 奥吉拉，“聊天机器人：安全性、隐私、数据保护和社会方面”，*并发计算：实践与经验*，第 33 卷，第 19 期，第 e6426 页，2021 年。

+   [208] B. 梅斯科和 E. J. 托波尔，“对医疗保健领域大语言模型（或生成 AI）的监管监督的必要性”，*npj 数字医学*，第 6 卷，第 1 期，第 120 页，2023 年。

+   [209] A. 阿赫迈德，N. 阿里，M. 阿尔祖拜迪，W. 扎赫乌安尼，A. A. 阿卜杜拉扎克，和 M. 豪斯，“自由提供的阿拉伯语语料库：范围审查”，*生物医学计算方法与程序更新*，第 2 卷，第 100049 页，2022 年。

+   [210] A. 阿赫迈德，N. 阿里，M. 阿尔祖拜迪，W. 扎赫乌安尼，A. 阿卜杜拉扎克，和 M. 豪斯，“阿拉伯语聊天机器人技术：范围审查”，*生物医学计算方法与程序更新*，第 2 卷，第 100057 页，2022 年。

+   [211] H. 比阿提，L. 沃特金斯，W. H. 罗宾逊，A. 鲁宾，和 S. 沃特金斯，“测量和减轻 AI 聊天机器人的偏见”，在*2022 IEEE 国际自主保障大会（ICAA）*。IEEE，2022 年，pp. 117–123。

+   [212] M. A. Kuhail, N. Alturki, S. Alramlawi, 和 K. Alhejori， “与教育聊天机器人互动：系统综述”， *教育与信息技术*，第 28 卷，第 1 期，页码 973–1018，2023 年。

+   [213] M. Hosseini, D. B. Resnik, 和 K. Holmes， “在撰写学术手稿中披露人工智能工具使用的伦理问题”， *研究伦理*，页码 17470161231180449，2023 年。

+   [214] E. A. Van Dis, J. Bollen, W. Zuidema, R. van Rooij, 和 C. L. Bockting， “Chatgpt：研究的五大优先事项”， *自然*，第 614 卷，第 7947 期，页码 224–226，2023 年。

+   [215] O. Evans, O. Wale-Awe, E. Osuji, O. Ayoola, R. Alenoghena, 和 S. Adeniji， “Chatgpt 对访问效率、就业、教育和伦理的影响：AI 语言模型的社会经济学”， *BizEcons 季刊*，第 16 卷，第 1 期，页码 1–17，2023 年。

+   [216] B. D. Lund, T. Wang, N. R. Mannuru, B. Nie, S. Shimray, 和 Z. Wang， “Chatgpt 与新学术现实：人工智能生成的研究论文与大型语言模型在学术出版中的伦理问题”， *信息科学与技术协会期刊*，第 74 卷，第 5 期，页码 570–581，2023 年。

+   [217] J. Rudolph, S. Tan, 和 S. Tan， “Chatgpt：废话制造者还是高等教育传统评估的终结？” *应用学习与教学期刊*，第 6 卷，第 1 期，2023 年。

+   [218] A. Abd-Alrazaq, R. AlSaad, D. Alhuwail, A. Ahmed, P. M. Healy, S. Latifi, S. Aziz, R. Damseh, S. A. Alrazak, J. Sheikh *等*， “医学教育中的大型语言模型：机遇、挑战与未来方向”， *JMIR 医学教育*，第 9 卷，第 1 期，页码 e48291，2023 年。

+   [219] E. Union， “2017 年 4 月 5 日欧洲议会和理事会关于医疗器械的第（EU）2017/745 号条例，修订了指令 2001/83/EC，第（EC）号 178/2002 号条例和第（EC）号 1223/2009 号条例，并废除了理事会指令 90/385/EEC 和 93/42/EEC”，2017 年，[在线]。可用链接：[`eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32017R0745&from=EN`](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32017R0745&from=EN)。 [访问时间：2024 年 5 月 8 日]。

+   [220] U. D. of Health and H. Services， “行业和食品药品管理局员工指导”，2022 年，[在线]。可用链接：[`www.fda.gov/media/109618/download`](https://www.fda.gov/media/109618/download)。 [访问时间：2024 年 5 月 9 日]。

+   [221] X. Yang, A. Chen, N. PourNejatian, H. C. Shin, K. E. Smith, C. Parisien, C. Compas, C. Martin, A. B. Costa, M. G. Flores *等*， “用于电子健康记录的大型语言模型”， *NPJ 数字医学*，第 5 卷，第 1 期，页码 194，2022 年。

| ![[无说明图片]](img/f872e4dfb23dca0f5032d9e360387749.png) | Sumit Kumar Dam 是韩国庆熙大学人工智能系的博士研究员。他于 2020 年获得了孟加拉国库尔纳大学计算机科学与工程的理学学士学位。他的研究兴趣包括对抗性鲁棒性、计算机视觉、自监督学习和机器学习。 |
| --- | --- |
| ![[未加标题的图片]](img/2b58f70d39f58ea25706ce98407946e9.png) | Choong Seon Hong (S’95-M’97-SM’11-F’23) 毕业于韩国首尔的庆熙大学，分别获得电子工程学士和硕士学位，时间分别是 1983 年和 1985 年，随后于 1997 年从日本东京的庆熙大学获得博士学位。1988 年加入韩国京畿道的 KT 公司，担任技术人员一职，参与宽带网络项目。自 1993 年以来一直在庆熙大学工作。曾任 KT 电信网络实验室的高级技术人员以及网络研究小组的主任，直至 1999 年。自 1999 年以来一直在庆熙大学计算机科学与工程系担任教授。他的研究领域包括未来互联网、智能边缘计算、网络管理和网络安全。Hong 博士是计算机协会（ACM）、电子、信息和通信工程师协会（IEICE）、日本信息处理学会（IPSJ）、韩国信息科学家工程师协会（KIISE）、韩国通信和信息科学院（KICS）、韩国信息处理学会（KIPS）以及开放标准和 ICT 协会（OSIA）的成员。他曾担任国际会议的总主席、技术计划委员会主席/成员或组织委员会成员，例如网络运营与管理研讨会（NOMS）、综合网络管理国际研讨会（IM）、亚太网络运营与管理研讨会（APNOMS）、端到端监控技术与服务（E2EMON）、IEEE 消费者通信与网络会议（CCNC）、分布式系统和网络保障（ADSN）、并行处理国际会议（ICPP）、数据集成与挖掘（DIM）、世界信息安全应用大会（WISA）、宽带融合网络（BcN）、电信信息网络架构（TINA）、应用与互联网国际研讨会（SAINT）以及信息网络国际会议（ICOIN）。他曾担任 IEEE 网络与服务管理交易、IEEE 通讯与网络期刊以及国际网络管理期刊的副编辑。此外，他还曾担任 IEEE 通信杂志的副技术编辑。目前他是《国际网络管理》和《未来互联网》期刊的副编辑。 |
| ![[无标题图片]](img/eeb42612598ab58bc172f1047b238134.png) | 余巧（S’24）于 2016 年和 2019 年分别获得南京信息工程大学（NUIST），中国南京的物联网工程学士学位和计算机科学与技术硕士学位。他目前在韩国庆熙大学（KHU）人工智能系攻读博士学位。在攻读博士学位之前，他曾在 2019 至 2022 年期间担任上海 Spreadtrum Communications（UNISOC）的相机软件工程师。他的兴趣包括机器学习、联邦学习、对抗性机器学习、自监督学习和分布式边缘智能。 |
| ![[无标题图片]](img/f4c84c9d42ace5c64462ac94fb58b431.png) | 张超宁于 2012 年和 2015 年分别获得哈尔滨工业大学的电气工程学士学位和硕士学位，并于 2021 年获得 KAIST 的博士学位。自 2022 年起，他在庆熙大学计算学院人工智能系担任助理教授。在此之前，他曾在 KAIST 担任博士后研究员。他的研究兴趣包括但不限于对抗性机器学习和自监督学习，以解决计算机视觉及其他领域中的模型鲁棒性和数据效率问题。 |

生成于 2024 年 6 月 17 日星期一 09:34:00，通过 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
