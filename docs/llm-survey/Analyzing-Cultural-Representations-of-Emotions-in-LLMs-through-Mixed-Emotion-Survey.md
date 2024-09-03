<!--yml

类别：未分类

日期：2024-09-03 17:28:11

-->

# 通过混合情感调查分析大语言模型中的文化情感表现

> 来源：[`arxiv.org/html/2408.02143`](https://arxiv.org/html/2408.02143)

1.  [I 引言](https://arxiv.org/html/2408.02143v1#S1 "在通过混合情感调查分析大语言模型中的文化情感表现")

1.  [II 相关工作](https://arxiv.org/html/2408.02143v1#S2 "在通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [II-A 评估大语言模型的情感技能](https://arxiv.org/html/2408.02143v1#S2.SS1 "在 II 相关工作 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [II-B 跨文化情感研究](https://arxiv.org/html/2408.02143v1#S2.SS2 "在 II 相关工作 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [II-C 大语言模型中的文化表现](https://arxiv.org/html/2408.02143v1#S2.SS3 "在 II 相关工作 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

1.  [III 方法](https://arxiv.org/html/2408.02143v1#S3 "在通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [III-A 具有人的混合情感实验](https://arxiv.org/html/2408.02143v1#S3.SS1 "在 III 方法 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [III-B 在大语言模型上运行混合情感调查](https://arxiv.org/html/2408.02143v1#S3.SS2 "在 III 方法 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [III-C 评估](https://arxiv.org/html/2408.02143v1#S3.SS3 "在 III 方法 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

1.  [IV 实验](https://arxiv.org/html/2408.02143v1#S4 "在通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [IV-A 研究 1：英语与日语](https://arxiv.org/html/2408.02143v1#S4.SS1 "在 IV 实验 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [IV-B 研究 2：使用上下文提示的英语与日语](https://arxiv.org/html/2408.02143v1#S4.SS2 "在 IV 实验 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

    1.  [IV-C 研究 3：比较东亚语言与西方语言](https://arxiv.org/html/2408.02143v1#S4.SS3 "在 IV 实验 ‣ 通过混合情感调查分析大语言模型中的文化情感表现")

1.  [V 结论](https://arxiv.org/html/2408.02143v1#S5 "在通过混合情感调查分析大语言模型中的文化情感表现")

# 通过混合情感调查分析大语言模型中的文化情感表现

Shiran Dudy4, Ibrahim Said Ahmad4, Ryoko Kitajima2 和 Agata Lapedriza43 4 东北大学，波士顿，MA，美国

2 独立研究员

3 巴萨罗那开放大学，西班牙

电子邮件: {s.dudy,i.ahmad,a.lapedriza}@northeastern.edu

###### 摘要

大型语言模型（LLMs）已在全球范围内广泛采用，展示了多种语言的先进语言能力。学术界对利用这些模型模拟和研究人类行为的兴趣日益增加。然而，必须认识到，LLMs 在特定语言中的能力可能无法完全涵盖与其文化相关的规范和价值观。由于西方和美国的训练数据占主导地位，出现了对以英语为中心的文化和价值观的潜在偏见的担忧。本研究集中于分析 LLMs 中的情感文化表征，特别是在混合情感情境下。我们的方法基于 Miyamoto 等人（2010）的研究，该研究确定了日本和美国人类反应中的独特情感指标。我们首先将他们的混合情感调查应用于五种不同的 LLMs 并分析其输出。其次，我们通过实验背景变量来探索响应的变化，考虑语言和说话者来源。第三，我们扩展调查范围，涵盖额外的东亚和西欧语言，以评估它们与各自文化的契合度，预计会有更接近的匹配。我们发现：（1）模型与文献中的证据对齐有限；（2）书面语言对 LLMs 响应的影响大于参与者来源信息；（3）LLMs 的响应在东亚语言中更为相似，而在西欧语言中则不然。

###### 关键词:

文化表征、情感 LLMs、稳定 LLMs 响应

## I 引言

随着大型语言模型（LLMs）如 ChatGPT 的广泛应用，人们对如何在 LLMs 中表现不同文化的兴趣增加了[[1](https://arxiv.org/html/2408.02143v1#bib.bib1), [2](https://arxiv.org/html/2408.02143v1#bib.bib2)]。了解 LLMs 中的文化表征至关重要，原因有很多，例如确保基于 LLMs 的沟通工具具有包容性（能够处理不同的观点和价值观）和有效性（能够在不同文化背景下进行恰当的解读和回应）。情感在沟通中扮演着重要角色，因为它们对信息的表达和感知有着强烈的影响[[3](https://arxiv.org/html/2408.02143v1#bib.bib3)]。这促使了近期对 LLMs 中情感技能的研究[[4](https://arxiv.org/html/2408.02143v1#bib.bib4), [5](https://arxiv.org/html/2408.02143v1#bib.bib5), [6](https://arxiv.org/html/2408.02143v1#bib.bib6), [7](https://arxiv.org/html/2408.02143v1#bib.bib7)]。

本文明确研究了 LLM 中情感的文化表现。具体而言，我们专注于通过研究 LLM 对各种混合情感情况的情感响应，比较西方文化和东亚文化的情感表现。我们的研究基于 Miyamoto 等人（2010）进行的*混合情感实验*[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]。在他们的工作中，作者设计了一项调查，描述了 13 种混合情感情况，参与者需要对他们在每种情况中的感受进行评分。调查由北美参与者和日本参与者用各自的语言回答，结果显示了两个研究人群之间的有趣差异（*混合情感实验*的更多细节[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]请参见[III-A](https://arxiv.org/html/2408.02143v1#S3.SS1 "III-A The Mixed Emotion Experiment with Human Participants ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")）。在我们的工作中，我们利用了与[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]中相同的情感响应调查，分别在日语和英语中进行，以调查不同 LLM 生成的响应是否与 Miyamoto 等人（2010）进行的人类实验中的发现一致[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]。我们的工作与 Havaldar 等人（2023）[[9](https://arxiv.org/html/2408.02143v1#bib.bib9)]的工作密切相关，后者研究了 LLM 中具有文化意识的情感响应。该工作研究的是混合情感现象，而不是 LLM 中普遍情感的存在。

更一般而言，我们的研究涉及三个研究问题：

+   •

    RQ1: 在[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]中的发现程度在 LLM 中得到重复的程度如何？

+   •

    RQ2: 当使用不同来源的背景信息提示 LLM 时，其响应会有什么影响？

+   •

    RQ3: 在具有更高文化亲和力的语言中，LLM 的响应有多相似？

为了解决这些研究问题，我们进行了 3 项研究，详见第[IV](https://arxiv.org/html/2408.02143v1#S4 "IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")节。研究 1 比较了当 LLMs 用英语与日语进行调查时，响应的差异。同时，它还研究了 LLMs 获得的结果与宫本等人[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]在对人类受试者实验中的结果的一致性。研究 2 分析了向提示中添加不同背景信息的效果。例如，用英语进行提示，但在提示中添加文本信息*请将[调查]评估为日本参与者*。最后，研究 3 比较了不同语言之间的响应，包括 4 种西方语言（英语、西班牙语、德语和法语）以及 4 种东亚语言（中文、日语、韩语和越南语）。

我们的研究基于 5 种广泛使用的 LLMs：三种开源模型（mistral-7b-instruct [[10](https://arxiv.org/html/2408.02143v1#bib.bib10)]，gemma-7b-it:free [[11](https://arxiv.org/html/2408.02143v1#bib.bib11)]，和 llama-2-70b-chat [[12](https://arxiv.org/html/2408.02143v1#bib.bib12)]）和两种最受欢迎的私人系统（gpt-3.5-turbo¹¹1[`platform.openai.com/docs/models`](https://platform.openai.com/docs/models) 和 gpt-4-turbo-preview²²2[`openai.com/contributions/gpt-4v`](https://openai.com/contributions/gpt-4v)）。我们的结果表明，LLMs 与我们研究现象的对齐程度有限（即模型对调查的响应与人类实验结果的对齐度不强）。我们还发现，相比于用户来源的背景信息，语言对 LLM 生成的响应有更强的影响，并且东亚语言的 LLM 响应之间的相关性大于欧洲语言的响应。除了这些有趣的观察外，我们认为本文所使用的方法论可以激发未来关于 LLMs 中文化表现的研究。

## II 相关工作

### II-A 评估大型语言模型的情感技能

一些近期研究尝试评估和量化大型语言模型（LLMs）的情感技能。例如，Schaaff 等人 2023 年[[4](https://arxiv.org/html/2408.02143v1#bib.bib4)]研究了基于 GPT-3.5 的 ChatGPT 在展现同理反应和情感表达方面的程度。在实验中，ChatGPT 被指示将中性句子改写为六种情感句子：喜悦、愤怒、恐惧、爱、悲伤和惊讶。然后，ChatGPT 的回应使用五个标准化问卷进行评估。这项研究展示了 ChatGPT 在使用相同基础句子传达多种情感方面的良好结果。

Tran 等人 [[5](https://arxiv.org/html/2408.02143v1#bib.bib5)] 介绍了一种评估情感识别系统的鲁棒性和偏见的方法。他们结合了 GPT-3 和基于规则的约束来创建不同语言能力水平的文本变体。这些文本用于检查性能偏见，重点关注语言能力，并使用 COSMIC 模型 [[6](https://arxiv.org/html/2408.02143v1#bib.bib6)] 和基准数据集来研究模型无关的效果。

最后，Broekens 等人 [[7](https://arxiv.org/html/2408.02143v1#bib.bib7)] 探索了如何仅通过提示让 ChatGPT 执行情感计算任务。这项方法包括通过与 ChatGPT 进行对话实验来探索其细粒度的情感处理能力。论文使用了基于 OCC 模型的规则逻辑模型作为提示 [[13](https://arxiv.org/html/2408.02143v1#bib.bib13)]，评估 ChatGPT 是否能根据特定框架预测情感。他们还使用人类专家评分者作为基准映射了刺激集，并创建了一组反映 OCC 模型中不同情感的情境。研究表明，ChatGPT 能够准确提取情境和词语中的细粒度情感，与微调模型的表现相当。它展示了对情感维度和情感词的适度理解，并成功地基于 OCC 评价模型进行了基本的情感引发。

### II-B 跨文化情感研究

情感被广泛研究，以比较东亚文化和西方文化。Tsai 等人 [[14](https://arxiv.org/html/2408.02143v1#bib.bib14)] 显示，在北美文化背景下，人们倾向于感受到兴奋、热情、精力充沛等“高唤起积极”状态，而在东亚文化背景下，人们一般更喜欢感受到平静、安宁等“低唤起积极”状态。Tsai 等人 [[15](https://arxiv.org/html/2408.02143v1#bib.bib15)] 的后续研究显示，来自北美背景的人（重视高唤起情感状态）倾向于喜欢刺激性活动，如跳伞，而来自东亚背景的人（重视低唤起情感状态）则喜欢宁静的活动，如在海滩上悠闲地度过时光。

此外，Tsai 等人 [[14](https://arxiv.org/html/2408.02143v1#bib.bib14)] 表明，在欧洲裔美国人中，人们经历高唤醒正面状态的越少，他们的抑郁程度越高，而在香港华人中，人们经历低唤醒正面状态的越少，他们的抑郁程度越高。与之前的见解一致，Chentsova-Dutton 等人 [[16](https://arxiv.org/html/2408.02143v1#bib.bib16)] 发现抑郁的欧洲裔美国人表现出较少的情感表达，但抑郁的东亚裔美国人则不然，实际上可能会表达更多的情感。在我们的研究中，我们重点关注了 Miyamoto 等人 [[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]，他们比较了北美人和日本人，显示出后者在积极事件中更可能感到糟糕和良好（“混合”情感），并且在面对负面事件时的反应有所不同。

### II-C 大语言模型中的文化表现

一些早期研究已经分析了大语言模型中的文化表现。例如，Naous 等人 [[17](https://arxiv.org/html/2408.02143v1#bib.bib17)] 评估了大语言模型对阿拉伯文化和西方文化的偏见，重点关注了故事生成、命名实体识别（NER）、情感分析、上下文提示分析和文本填充。研究表明，多语言和阿拉伯语单语的大语言模型对与西方文化相关的实体存在偏见。该研究进一步引入了一个名为 CAMeL 的资源，其中包含对比阿拉伯和西方文化的自然发生的提示和实体。与此一致，Atari 等人 [[18](https://arxiv.org/html/2408.02143v1#bib.bib18)] 显示，大语言模型在心理认知任务中的表现类似于大多数西方工业化教育富裕民主（WIERD）人群的表现，这是一项关于大语言模型的大规模跨语言研究。类似地，Arora 等人 [[19](https://arxiv.org/html/2408.02143v1#bib.bib19)] 在他们基于世界价值调查的研究中发现 [`www.worldvaluessurvey.org/WVSContents.jsp`](https://www.worldvaluessurvey.org/WVSContents.jsp)，尽管模型中引发的价值观因文化而异，但其偏见与现有的大规模价值调查中概述的价值观不一致。更广泛地说，大语言模型的文化表现已开始引起主流媒体的关注 [[20](https://arxiv.org/html/2408.02143v1#bib.bib20), [21](https://arxiv.org/html/2408.02143v1#bib.bib21)]。

除了输出分析，Wendler 等人 [[22](https://arxiv.org/html/2408.02143v1#bib.bib22)] 最近的一项研究探讨了多语言模型是否将英语作为内部枢纽语言，重点关注 Llama-2 系列的变换器模型，对 LLMs 进行内部探测。该研究通过跟踪中间嵌入和逻辑透镜分析，基于构造的非英语提示以及唯一正确的单词延续，提供了令人信服的证据，表明多语言模型确实可能以细微且概念上有偏见的方式将英语用作内部枢纽语言。

## III 方法

### III-A 人类参与者的混合情感实验

在这项工作中，我们遵循了 Miyamoto 等人（2010 年）[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)] 制定的协议，他们研究了美国人和日本人在体验混合情感时的相似性和差异，重点关注美国人和日本人在日常生活中的合理情境中同时经历的正面和负面情感。具体来说，该研究考虑了 13 种情境，这些情境分为三种类型：自我成功、过渡和自我失败。然后，参与者需要评估他们会在多大程度上体验到正面或负面情感，以及他们会在多大程度上体验到具体的正面情感（幸福、骄傲、同情、宽慰、希望和友好感）或具体的负面情感（悲伤、焦虑、愤怒、自责、恐惧、对自己愤怒、羞耻、内疚、嫉妒、挫折、尴尬、怨恨和担心给别人带来麻烦）。此外，参与者还回答了三个使用 6 分制量表的评估问题：（1）他们会对他人的感受感到多么负责；（2）他人对他们的感受负责的程度。最后，为了研究参与者控制局势的动机，参与者被问到*你会多大程度上考虑影响或改变周围的人、事件或物品，以符合自己的愿望？* 同样使用 6 分制量表。结果显示，在自我成功情境中，日本参与者的混合情感表现得比美国参与者更多。除了混合情感外，在自我失败情境中，这些群体在改变局势的动机和自我责任归属方面也存在显著差异，这将在接下来的部分中讨论。

我们的工作遵循了[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]中使用的研究协议。具体来说，我们复制了调查，重点关注那些在该研究中显示出日本人和美国人之间显著差异的问题。我们将我们的发现与[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]中的发现进行对比，这些发现总结在表格[I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中。

### III-B 在 LLMs 上运行混合情感调查

根据[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]中的原始示例，我们使用 ChatGPT 生成了五个自我成功情况和五个自我失败情况，这些情况构成了调查，同时结合了论文中描述的原始指示。以下两个情况分别是自我成功和自我失败的示例：

+   •

    （自我成功情况）*你获得了极好的绩效评价和晋升，这让你感到开心。然而，你的同事因为表现不佳而收到警告，这让你感到混合的情绪。*

+   •

    （自我失败情况）*你的密友在社交聚会中成为关注的中心，轻松结交朋友并建立联系，这让你为他们的社交技能感到自豪。然而，你在社交场合中挣扎，感到被排斥，产生了对他们的钦佩和对自己的失望混合的情感。*

对于研究 3，每份调查都由母语为越南语、韩语、中文、法语、德语和西班牙语的讲者翻译，他们也精通英语。为了查询 LLMs，我们使用了 LangChain Python 包⁴⁴[`python.langchain.com/docs/get_started/introduction`](https://python.langchain.com/docs/get_started/introduction)，并仅包括了所有 24 个问题的完整回答。调查问题被分为三个部分，因为目前模型无法一次性回答所有 24 个问题。我们评估每种情况的情感反应，假设每种情况可以单独询问，且其他问题的存在不会影响回答。

### III-C 评估

在比较分布时，我们在研究 1 中使用了独立的单尾配对 t 检验，在研究 2 和 3 中使用了双尾 t 检验。关于研究 1，特别是将 LLMs 与 Miyamoto 等人进行的人类实验的比较[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]，我们将我们的结果与[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]中的相关发现进行比较，这些发现总结在表格[I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中。

表 I：由 Miyamoto 等人（2010）获得的参与者实验结果 [[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]。主要发现集中在两种情境类型，涵盖了不同的情感。他们的发现基于单尾 t 检验（及其相关的$p$值），指示组之间（JP 或 AM，分别对应日本人和美国人）的关系。

| 情境类型 | 情感 | 关系 | p 值 |
| --- | --- | --- | --- |
| 自我成功 | 改变动机 | JP $>$ AM | $p<0.05$ |
| 我对他人负责 | JP $>$ AM | $p<0.01$ |
| 快乐和 |  |  |
| 担心打扰他人 | JP $>$ AM | $p<0.01$ |
| 积极和消极 | JP $>$ AM | $p<0.1$ |
| 自我失败 | 改变动机 | JP $<$ AM | $p<0.001$ |
| 我对他人负责 | JP $>$ AM | $p<0.001$ |
| 其他人对我负责 | JP $<$ AM | $p<0.07$ |

## IV 实验

### IV-A 研究 1: 英语与日语

我们评估了 LLM 在英语与日语提示下调查响应的差异。我们还将 LLM 的响应与 Miyamoto 等人 [[8](https://arxiv.org/html/2408.02143v1#bib.bib8)] 在其对人类受试者的研究中获得的结果进行了比较。

我们对每种语言、每个 LLM 运行调查$n$次，以模拟$n$个响应。我们寻找稳定的$n$值，使得下次抽取$n$个响应时，两次抽样的分布相似——这表明样本稳定性。我们发现$n=80$能提供稳定的分布，并在第[IV-A 节](https://arxiv.org/html/2408.02143v1#S4.SS1 "IV-A Study 1: English vs. Japanese ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中详细说明了搜索过程。

表[II](https://arxiv.org/html/2408.02143v1#S4.T2 "TABLE II ‣ IV-A Study 1: English vs. Japanese ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")总结了每个系统在表[I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中呈现的每种情感反应的结果。为了制作这个表格，我们进行了单尾 t 检验，其中$H_{0}$假设为组间没有差异，而$H_{1}$假设则表明存在表[I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中指定方向的差异。如果 t 检验结果在预期方向上拒绝了$H_{0}$，我们用‘+’表示。随后，我们进行了另一个相反方向的 t 检验，如果结果拒绝了$H_{0}$，则用‘-’表示。如果$H_{0}$没有被拒绝，则该单元格留空。结果收集后，我们汇总了整体表现，其中‘+’和‘-’分别计为$+1$和$-1$，在 7 个测试中进行统计。最后，结果被标准化为范围为$[-100\%,100\%]$的百分比分数，对应于所有测试中的完全失败和完全成功。

表 II：五种最先进 LLM 的情感反应。每个 LLM 被标记为‘+’，‘$-$’，或一个空单元格，表示在日本与美国人之间发现的关系。例如，在 gemma 中，对于自我成功情境下改变动机的单尾 t 检验结果显著，且方向与表[I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中显示的原始研究一致（JP$>$AM），因此标记为‘+’。另一方面，对于自我失败情境下改变动机，gemma 在与原始研究相反的方向上显示了显著结果（gemma: JP$>$AM，表[I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey"): JP$<$AM），因此标记为‘-’。对于在任何方向上都不显著的结果，该单元格为空。在底部，我们汇总了‘+’和‘$-$’的数量。最后，阅读总结，例如 gpt4 的结果可以是：gpt4 在 3 次测试中与原始研究结果一致，但在 3 次测试中与之相反，结果为$0$。结果已被标准化。

| 情境类型 | 情感 | mistral -7b-Instruct | gemma -7b-IT:Free | llama -2-70b-Chat | gpt-3.5 -Turbo | gpt-4 -Turbo-Preview | 原始研究 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 自我成功 | 改变的动机 | + | + | + | + | $-$ | $p<0.05$ |
| 我对他人负责 | + | $-$ | $-$ | + | + | $p<0.01$ |
| 快乐和 |  |  |  |  |  |  |
| 担心麻烦他人 | + | + | + | + | $-$ | $p<0.01$ |
| 积极与消极 | $-$ |  |  |  |  | $p<0.1$ |
| 自我失败 | 改变的动机 |  | $-$ | $-$ | $-$ | + | $p<0.001$ |
| 我对他人负责 | $-$ | $-$ | $-$ | + | + | $p<0.001$ |
| 他人为我负责 | $-$ | + | + | $-$ | $-$ | $p<0.07$ |
|  |  |  |  |  |  |  |  |
|  | 性能计数 $x\in[-7,7]$ | $3-3=0$ | $3-3=0$ | $3-3=0$ | $4-2=2$ | $3-3=0$ |  |
|  | 归一化成功 $x\in[-100\%,100\%]$ | $0\%$ | $0\%$ | $0\%$ | $28.5\%$ | $0\%$ |  |

在表格 [II](https://arxiv.org/html/2408.02143v1#S4.T2 "TABLE II ‣ IV-A Study 1: English vs. Japanese ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中，我们观察到大多数模型在与人类受试者研究对齐的测试数量上取得了类似的平衡 ([I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey"))。GPT-3.5 达到了 $28.5\%$，显示出与其他模型相比的最佳对齐度，但它并未完全与原始文献中的结果对齐。为了进一步调查 LLMs 的反应，图 [1](https://arxiv.org/html/2408.02143v1#S4.F1 "Figure 1 ‣ IV-A Study 1: English vs. Japanese ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey") 描述了每个 LLM 的四种评分分布类型：（自我成功，改变的动机）、（自我失败，改变的动机）、（自我成功，我对他人负责）和（自我失败，我对他人负责）。我们注意到在（自我成功，改变的动机）的分布上存在差异，这是第一行的内容。Gemma 表明日式和美式之间有明显的分离，而 mistral 的人群更加混合。我们看到，尽管大多数模型在表格 [II](https://arxiv.org/html/2408.02143v1#S4.T2 "TABLE II ‣ IV-A Study 1: English vs. Japanese ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中的调查问题上与人类实验对齐，但分布在视觉上似乎不同，gemma、llama、gpt3.5 和 gpt4 的两个群体的分离程度有所不同。这可能表明它们的底层机制可能有所不同。我们发现的分离也可能表明，即使 LLMs 在后台进行翻译，它们也可能展现出一定程度的文化敏感性。

相反，图 1 的前两行展示了视觉上类似的分布，尽管它们对应于自我成功和自我失败的情景，而表[I]中指出了相反的回应。这种相似性可能表明对情境类型的敏感性降低。

图 1 的最后两行也展示了不同情境类型的每个模型类似的分布。在这种情况下，表[I]指示日本人和美国人之间的关系保持不变。因此，这些回应与研究结果一致。

鉴于这两个发现，我们无法确定是否对情境类型不敏感，或者这是所有模型的一次性错误。

总的来说，我们发现 LLM 的回应与宫本等人有限的对齐[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]。 这种有限的对齐在模型之间表现出不同的响应测试的方式。然而，我们也观察到了相似之处，许多模型对相同的文本信息显示出很低的敏感性。

![标题参考](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：LLM 的情感反应。这张图展示了五种 LLM 在两种不同情境（自我成功和自我失败）下对两种不同情感（“改变的动机”和“对他人负责”）的反应。首先，每行，我们可以注意到 LLM 的分布是不同的。例如，第一行的 gemma 清楚地区分了日本人和美国人，在 mistral 中它们混合在一起。这些差异可能表明不同的 LLM 可能没有相同的基础机制。此外，我们还可以看到 gemma、llama 和 gpt3.5 可能并不只是从英语中翻译提示，因为这两个人口之间的相对差异。

确定所需样本数 $n$：尽管 Miyamoto 等人 [[8](https://arxiv.org/html/2408.02143v1#bib.bib8)] 强调了获得相关结果所需的人类参与者数量的重要性，但我们的研究重点是确保 LLM 的响应稳定性，以便实现结果的可重复性（在该版本中）。我们通过执行相同实验 $n$ 次，然后基于 $n$ 次运行中获得的响应平均值计算结果来实现这一点。本小节的最后部分详细介绍了我们为确定在所有实验中使用的参数 $n$ 而执行的实验。具体来说，我们确定了从模型中抽取的最小样本数 $n$，以确保样本稳定性，这意味着当抽取一组新的 $n$ 样本时，分布特性（$\mu$，$\sigma$）保持一致。

为了确定 $n$，我们在 10 到 300 个样本范围内以 10 为间隔施行了一部分调查问题。对于每个 $n$，我们生成了 20 个分布，并对所有唯一的分布对进行双尾 t 检验。图 [2](https://arxiv.org/html/2408.02143v1#S4.F2 "图 2 ‣ IV-A 研究 1：英语与日语 ‣ IV 实验 ‣ 通过混合情感调查分析 LLM 中的情感文化表现") 展示了日语的箱形图，显示了每个 $n$ 的所有模型中的 $p$-值中位数（每个 $n$ 五个 $p$-值中位数对应不同的模型）。根据观察，我们发现 $n$ 的中位数 $p$-值高于 0.5 的情况下提供了稳定的分布。基于这一观察，确定所需的最小 $n$ 为 80。

![参考说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2：实验以确定确保不同模型中 LLM 输出稳定性所需的运行次数 ($n$)。我们定义当绘制两次（或更多） $n$ 响应时，配对 t 检验未显示低 p 值时即为稳定。这个 $n$ 是分别针对日语和英语响应以及我们实验的 LLM 进行搜索的。经验上，我们寻找的 $n$ 使其 p 值中位数分布（如每个箱形图所示）高于 $0.5$，图示出对于日语（其稳定性低于英语），需要 $n=80$ 才能实现稳定。因此 $n=80$ 在我们的所有实验中都被固定使用。

### IV-B 研究 2：使用上下文提示的英语与日语比较。

本部分的目标是理解不同类型的语境对回应的影响。我们设定了调查两种语境模式的效果：1）书面调查的语言（用($w$)表示），以及 2）说话者的原始语言（LLM 需要模拟的），用($o$)表示，从而形成了回应分布描述为$(w,o)$。我们在调查中添加了额外的请求‘请按[placeholder]参与者进行评分’，其中 placeholder 可以是‘Japanese’或‘American’，这两种语言都被应用于四种书面语言和原始语言组合 $(w,o)$：$(en,en)$,$(en,jp)$,$(jp,jp)$,$(jp,en)$。例如，$(en,jp)$ 是一个用英语书写的调查，模拟了来自日本的参与者。我们假设由于语言相似性或模拟参与者的原始语言相似性，我们可能会发现不同($w$,$o$)组合之间的相关性。对于每两个($w$,$o$)对，我们进行了双尾 t 检验，以评估 7 个 t 检验中分布的相似性，详见表[I](https://arxiv.org/html/2408.02143v1#S3.T1 "TABLE I ‣ III-C Evaluations ‣ III Methods ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")。例如，在表[III](https://arxiv.org/html/2408.02143v1#S4.T3 "TABLE III ‣ IV-B Study 2: English vs. Japanese using context prompts. ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中，gemma 模型在比较($(en,jp)$)和$(en,en)$)时的回应在 7 个应用的测试中有 3 个相似。根据此表，我们提出了三个假设，以理解书面语言($w$)和参与者的原始语言($o$)的影响，这些假设在表[IV](https://arxiv.org/html/2408.02143v1#S4.T4 "TABLE IV ‣ IV-B Study 2: English vs. Japanese using context prompts. ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中显示：（1）共享语言和不同原始语言之间是否存在相似性？；（2）相似原始语言但不同语言之间是否存在相似性？；（3）在第 1 项研究中($w$,-)的回应与在本节中共享相同书面语言($w$,$o$)的回应之间是否存在相似性？

表 [IV](https://arxiv.org/html/2408.02143v1#S4.T4 "TABLE IV ‣ IV-B Study 2: English vs. Japanese using context prompts. ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")总结了基于表 [III](https://arxiv.org/html/2408.02143v1#S4.T3 "TABLE III ‣ IV-B Study 2: English vs. Japanese using context prompts. ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")的原始结果的发现。我们发现问题（1）引发了大多数模型中最多的相关性，表明这可以归因于书面语言，相较于共享来源（2）作为上下文来源。然而，令人惊讶的是，假设（3）不成立，因为我们没有发现研究 1 与研究 2 中的相同语言之间的相关性。

Mistral 显示了最多的相似性，但仍然有一半的预期相关性缺失。在表 [III](https://arxiv.org/html/2408.02143v1#S4.T3 "TABLE III ‣ IV-B Study 2: English vs. Japanese using context prompts. ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")中，我们发现 mistral 还展示了$(en,en)$和$(jp,jp)$之间的相似性，这实际上可能是一个警告信号，提示整体生成过于相关的分布。因此，尽管 Mistral 的相关性高，但这可能表明响应之间的相似性更大，这与文化敏感性相悖。

在本研究中，我们发现语言对响应的影响比参与者的来源（或可能其他文本信息）更强。然而，当共享语言与研究 1 的响应进行比较时，我们没有发现任何相关性，这使得这些响应在行为上不一致。

表 III：文本语言与参与者来源的交叉。这个表格是一个混淆矩阵，每一个（$w$=书面语言，$o$=参与者的来源）表示对调查的单一响应。例如，（en,jp）是一个用英语书写的调查的 LLM 响应，而参与者的来源是日本。由于我们与研究 1 的结果进行了比较，而在研究 1 中我们没有指明任何来源，标记为（jp,-），指的是研究 1 中的日语调查。每个（$w$，$o$）分布都与表中的另一个分布进行了比较。例如，（en,en）仅在 mistral 中与（jp,en）相关，其中 7 个测试中的 2 个发现相似。

| ($w$, $o$) | (en, en) | (en, jp) | (jp, en) | (jp, jp) | (jp, -) |
| --- | --- | --- | --- | --- | --- |
| (en, -) |  |  |  |  |  |
| (en, en) |  | mistral: 7 gemma: 3 llama: 6 gpt3.5: 4 | mistral: 2 | mistral: 3 |  |
| (en, jp) |  |  | mistral: 2 gpt4: 1 | mistral: 3 |  |
| (jp, en) |  |  |  | mistral: 7 gemma: 5 llama: 3 gpt3.5: 2 gpt4: 2 |  |
| (jp, jp) |  |  |  |  |  |

表 IV：评估不同上下文的效果。后处理表 [III](https://arxiv.org/html/2408.02143v1#S4.T3 "TABLE III ‣ IV-B Study 2: English vs. Japanese using context prompts. ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey")。在这里，我们评估了由于共享书写语言（如 a. 所示的 $w_{0}=w_{1}$）、参与者的相同来源（如 b. 所示的 $o_{0}=o1$）或与研究 1（c.）中的实验相似性，以及研究 2 中相同语言的影响。例如，对于假设 a.，gpt4 仅发现了一个相关性，即 (jp,jp) 和 (jp,en) 之间的相关性。

| $H_{0}$ | Mistral-7b-Instruct | Gemma-7b-IT:Free | Llama-2-70b-Chat | GPT-3.5-Turbo | GPT-4-Turbo-Preview |
| --- | --- | --- | --- | --- | --- |
| a. $w_{0}=w_{1},o_{0}\neq o_{1}$ | 1.(en,en) 和 (en,jp) 2.(jp,jp) 和 (jp,en) | 1.(en,en) 和 (en,jp) 2.(jp,jp) 和 (jp,en) | 1.(en,en) 和 (en,jp) 2.(jp,jp) 和 (jp,en) | 1.(en,en) 和 (en,jp) 2.(jp,jp) 和 (jp,en) | 1.(jp,jp) 和 (jp,en) |
| b. $w_{0}\neq w_{1},o_{0}=o_{1}$ | 1.(en,jp) 和 (jp,jp) 2.(en,en) 和 (jp,en) |  |  |  |  |
| c. $w_{0}=w_{1},o_{0}=\emptyset,o_{1}$ |  |  |  |  |  |
|  |  |  |  |  |  |
| 性能总结 $x\in[0,8]$ | 2+2=4 | 2 | 2 | 2 | 1 |
| 归一化成功率 $x\in[0\%,100\%]$ | $50\%$ | $25\%$ | $25\%$ | $25\%$ | $12.5\%$ |

### IV-C 研究 3：比较东亚语言与西方语言

Schimmack 等人 [schimmack2002cultural] 认为“可能亚洲方言文化中的人们更容易识别事件中的愉快和不愉快方面，从而产生愉快和不愉快情绪的混合感。”这一假设与东亚文化的集体主义（与个人主义）特性有关 [Charlotte2023Understanding, grossmann2017mixed]。在研究 3 中，我们分析了东亚和美洲-欧洲文化亲和力语言之间的相似性，预期日语和美洲文化之间的相似性较大。

我们扩展了调查，新增了三种东亚语言（中文 (ch)、韩文 (kr) 和越南文 (vt)），以及三种欧洲语言（法语 (fr)、德语 (gr) 和西班牙语 (sp)）。我们翻译了研究 1 中的调查，并比较了语言对，假设 LLM 对相关语言的回应会相似。与研究 2 类似，我们对所有语言对进行了 7 次 t 检验。我们在表 [V](https://arxiv.org/html/2408.02143v1#S4.T5 "TABLE V ‣ IV-C Study 3: Comparing East Asian vs. Western Languages ‣ IV Experiments ‣ Analyzing Cultural Representations of Emotions in LLMs through Mixed Emotion Survey") 中总结了我们的结果。

我们观察到，大多数大型语言模型（LLMs）对东亚语言生成的响应分布比对欧洲语言更相似。一方面，这可能是一个期望的结果，因为这可能反映了大型语言模型对这些语言的文化敏感性。另一方面，根据互联网社会基金会的数据⁵⁵5[互联网按语言分布的数据](https://tinyurl.com/5yuczd4c)，互联网使用最多的语言是英语（$55\%$）、西班牙语（$5\%$）、德语、法语，然后是日语和中文，这可能为大型语言模型的训练数据提供了一个代理，导致其对区分不同东亚文化的响应不够细致。由于我们看到欧洲语言的相关性较低，我们假设更多的数据有助于更好地区分欧洲语言。

与研究 2 类似，没有语言与英语相关，这可能是由于其不成比例的体量（$55\%$）主要反映了美国文化及其多种方面，从而影响了训练。⁶⁶6 参见训练数据集 [[23](https://arxiv.org/html/2408.02143v1#bib.bib23)] 和 [内容创作者数量](https://www.statista.com/statistics/1279537/digital-content-creators-worldwide-by-country/)

在这里，与研究 2 类似，Mistral 展现了最多的相似对，导致了最高的跨文化相关性。基于研究 2 和研究 3，我们建议 Mistral 展示了一种跨响应的过度相似模式，无论语言和文本变异如何。这表明 Mistral 的响应对文化、内容和语言差异的敏感性较低。

表 V：评估相关语言的相似性。该表总结了五种大型语言模型在各语言之间的结果。我们假设相关的东亚语言可能基于双尾 t 检验（如 a. 所示）被发现相似，并对欧洲语言进行了相似性假设（如 b. 所示）。我们将语言名称缩写为 vt、kr、ch、jp、fr、gr、sp、en，分别对应越南语、韩语、中文、日语、法语、德语、西班牙语和英语。例如，我们发现 Mistral 在假设 b. 中有两个相关性：一个是德语和法语（gr,fr），另一个是德语和西班牙语（gr,sp），因此总共有两个。总体而言，东亚语言的响应相似性高于欧洲语言。由于东亚语言资源在互联网中的数量较少，存在对大型语言模型在这些语言内区分能力和如何将文化身份归并到东亚的担忧。

| $H_{0}$ | Mistral-7b-Instruct | Gemma-7b-IT:Free | Llama-2-70b-Chat | GPT-3.5-Turbo | GPT-4-Turbo-Preview |
| --- | --- | --- | --- | --- | --- |
| a. $w\in W_{EastAsian}$ | 1.(kr,vt), 2.(ch,jp), 3.(jp,vt) | 1.(kr,vt), 2.(jp,vt), 3.(ch,vt) | 1.(kr,vt) | 1.(jp,kr) | 1.(jp,kr), 2.(jp,vt) |
| b. $w\in W_{European}$ | 1.(gr,fr), 2.(gr,sp) | 1.(gr,fr), 2.(gr,sp) |  | 1.(gr,fr) |  |
|  |  |  |  |  |  |
| 性能总结 $x\in[0,12]$ | 3+2=5 | 3+2=5 | 1 | 1+1=2 | 2 |
| 标准化成功 $x\in[0\%,100\%]$ | $41.6\%$ | $41.6\%$ | $8.3\%$ | $16.6\%$ | $16.6\%$ |

## V 结论

在这项工作中，我们研究了大型语言模型（LLMs）在混合情感背景下的文化对齐问题。混合情感现象与东方集体主义规范相关联[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]。Tim Lomas 等人[[25](https://arxiv.org/html/2408.02143v1#bib.bib25)]的研究的核心前提是，个人主义通常与西方文化相关，而集体主义则与东方文化更为紧密地联系在一起。基于这一前提，我们旨在调查 LLMs 对超越西方背景的文化的敏感性。我们通过考察 LLMs 对混合情感情境的反应来实现这一目标，因为这些情境被认为会引发集体主义或个人主义规范，这取决于文化与最初研究文化的接近程度。

我们的研究结果表明，在用英语和日语复制 Miyamoto 等人的研究[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]时，领先的 LLMs 的回答与[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]中获得的人类回答的匹配程度有限。

我们还比较了用英语或日语提示大型语言模型（LLMs）与明确使用文化背景的文本描述之间的效果。这些实验的目标是让模型的回答像是针对西方文化或日本文化的人提出的问题。我们发现，语言本身对回答的影响比其文本背景描述更大。

最后，我们评估了 LLMs 在多种语言下的回应，包括东亚语言（中文、韩语和越南语）以及美洲和欧洲（或西方）语言（法语、德语和西班牙语）。我们发现，被调查 LLMs 在东亚语言和西方语言之间的回答相似性差异显著。东亚语言组的回答相关性更多，使其与西方语言组相比更为相似。这与我们期望两个组的相关性率相似的预期不符。

随着 LLMs 在全球范围内的日益普及，以及越来越多的研究人员探索它们模拟人类行为的潜力，我们对它们如何准确反映我们多样的价值观和文化有着日益增长的需求。我们希望这里展示的方法，通过复制经过同行评审的人类受试者研究，为深入理解基于研究社区积累的各种文化的文化对齐提供了一条路径。此外，我们希望我们的发现的观察和讨论能激发更多关于 LLMs 中情感文化表现的研究。

## 伦理影响声明

普适性限制（对其他文化的适用性）。我们的方法依赖于现有的同行评审文献，限制了我们对研究较少文化的探索。对于这些研究不足的文化，我们建议开发专注于理解文化规范和情感差异（相对于由 LLMs 训练的主流文化）的调查，以更有效地评估人类受试者的反应与 LLMs 的文化对齐。

普适性限制（更广泛的文化代表性）。尽管根据标准统计方法，结果具有显著性，但我们基于七项测试评估了混合情感现象。这些结果突出了与混合情感相关的特定文化差异，但无法得出关于整体文化代表性的更广泛结论。

验证。一项担忧是 Miyamoto 等人所进行实验的有效性[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]，我们认识到可能会存在关于混合情感的文化认知偏移。尽管混合情感现象仍然是研究的主题[[24](https://arxiv.org/html/2408.02143v1#bib.bib24)]，我们计划在未来使用人类参与者重复原始研究。

研究 3 假设的有效性。在这一部分，我们预期了基于地理接近度（即假定会导致文化相似性）的回应相似性，并基于文献支持在不同类型的社会中混合情感的类似行为的可能性。我们强调，研究 3 并非旨在证明这一现象的存在，而是了解英语-欧洲语言和东亚语言中是否存在文化相似性。

偏差。我们遵循了 Miyamoto 等人[[8](https://arxiv.org/html/2408.02143v1#bib.bib8)]所概述的协议，包括调查指示，其中情况内容引入了潜在的混合情感，这可能偏倚了结果。然而，研究结果表明，尽管在所有实验中均均匀引入了偏差，模型的响应并未表现出一致的模式。

## 致谢

本研究部分由西班牙科学部、研究国家机构和 FEDER（欧盟）基金资助。我们感谢 Sophie Wang、Tuan Ann Dinh、Joy Jee 和 Yale Kim、Parfait Atchadé以及 Michael Dabis 将调查问卷翻译成中文、越南语、韩语、法语和德语。

## 参考文献

+   [1] W. Q. Leong, J. G. Ngui, Y. Susanto, H. Rengarajan, K. Sarveswaran, 和 W. C. Tjhi, “Bhasa: 面向大型语言模型的全面东南亚语言和文化评估套件，” *arXiv 预印本 arXiv:2309.06085*，2023。

+   [2] N. Buttrick, “将大型语言模型视为人类文化的压缩算法进行研究，” *认知科学趋势*，2024。

+   [3] P. A. Andersen 和 L. K. Guerrero, “社交互动中的沟通与情感原则，” 在 *沟通与情感手册*。爱思唯尔, 1996, pp. 49–96。

+   [4] K. Schaaff, C. Reinig, 和 T. Schlippe, “探索 ChatGPT 的同理能力，” 在 *2023 第 11 届国际情感计算与智能交互会议 (ACII)*。IEEE, 2023, pp. 1–8。

+   [5] Q. Tran, K. Shpileuskaya, E. Zaunseder, J. Salg, L. Putzar, 和 S. Blankenburg, “稳健性分析揭示了情感识别系统中的语言能力偏见，” 在 *2023 第 11 届国际情感计算与智能交互会议 (ACII)*。IEEE, 2023, pp. 1–8。

+   [6] D. Ghosal, N. Majumder, A. Gelbukh, R. Mihalcea, 和 S. Poria, “COSMIC：对话中情感识别的常识知识，” 在 *计算语言学协会发现：EMNLP 2020*，T. Cohn, Y. He, 和 Y. Liu 编. 在线：计算语言学协会, 2020 年 11 月, pp. 2470–2481. [在线]. 可用: [`aclanthology.org/2020.findings-emnlp.224`](https://aclanthology.org/2020.findings-emnlp.224)

+   [7] J. Broekens, B. Hilpert, S. Verberne, K. Baraka, P. Gebhard, 和 A. Plaat, “大型语言模型中出现的细粒度情感处理能力，” 在 *2023 第 11 届国际情感计算与智能交互会议 (ACII)*。IEEE, 2023, pp. 1–8。

+   [8] Y. Miyamoto, Y. Uchida, 和 P. C. Ellsworth, “文化与混合情感：日本和美国的正负情感共现。” *Emotion*, vol. 10, no. 3, p. 404, 2010。

+   [9] S. Havaldar, B. Singhal, S. Rai, L. Liu, S. C. Guntuku, 和 L. Ungar, “多语言模型并非多文化：情感的案例研究，” 在 *第 13 届计算方法在主观性、情感与社交媒体分析研讨会论文集*，2023, pp. 202–214。

+   [10] A. Q. Jiang, A. Sablayrolles, A. Mensch, C. Bamford, D. S. Chaplot, D. d. l. Casas, F. Bressand, G. Lengyel, G. Lample, L. Saulnier *等人*, “Mistral 7b,” *arXiv 预印本 arXiv:2310.06825*, 2023。

+   [11] G. Team, T. Mesnard, C. Hardin, R. Dadashi, S. Bhupatiraju, S. Pathak, L. Sifre, M. Rivière, M. S. Kale, J. Love *等人*, “Gemma：基于双子研究和技术的开放模型，” *arXiv 预印本 arXiv:2403.08295*, 2024。

+   [12] H. Touvron, L. Martin, K. Stone, P. Albert, A. Almahairi, Y. Babaei, N. Bashlykov, S. Batra, P. Bhargava, S. Bhosale *等人*, “Llama 2：开放基础和微调聊天模型，” *arXiv 预印本 arXiv:2307.09288*, 2023。

+   [13] A. Ortony, G. L. Clore, 和 A. Collins, *情感的认知结构*。剑桥大学出版社, 2022。

+   [14] J. L. Tsai, B. Knutson, 和 H. H. Fung, “情感评估中的文化差异。” *人格与社会心理学杂志*, vol. 90, no. 2, p. 288, 2006。

+   [15] J. L. Tsai, F. F. Miao, E. Seppala, H. H. Fung, 和 D. Y. Yeung，“**影响与调整目标：理想情感中的文化差异来源**。” *人格与社会心理学杂志*，第 92 卷，第 6 期，第 1102 页，2007。

+   [16] Y. E. Chentsova-Dutton, J. P. Chu, J. L. Tsai, J. Rottenberg, J. J. Gross, 和 I. H. Gotlib，“**抑郁症与情绪反应性：东亚裔美国人与欧洲裔美国人的差异**。” *异常心理学杂志*，第 116 卷，第 4 期，第 776 页，2007。

+   [17] T. Naous, M. J. Ryan, 和 W. Xu，“**祷告后喝啤酒？测量大语言模型中的文化偏见**，” *arXiv 预印本 arXiv:2305.14456*，2023。

+   [18] M. Atari, M. J. Xue, P. S. Park, D. Blasi, 和 J. Henrich，“**哪些人类？**” 2023。

+   [19] A. Arora, L.-A. Kaffee, 和 I. Augenstein，“**探查预训练语言模型中的跨文化价值观差异**，” *跨文化考虑在 NLP@ EACL*，第 114 页，2023。

+   [20] R. Piir，“**芬兰的 chatgpt 替代品也开始用爱沙尼亚语思考**，” 2023。 [在线]。可用： [`news.err.ee/1609120697/finland-s-chatgpt-equivalent-begins-to-think-in-estonian-as-well`](https://news.err.ee/1609120697/finland-s-chatgpt-equivalent-begins-to-think-in-estonian-as-well)

+   [21] A. Akira，“**我检查了在商业和教育领域广泛传播的 chatgpt 的跨文化理解**，” 2023。 [在线]。可用： [`serai.jp/living/1124372`](https://serai.jp/living/1124372)

+   [22] C. Wendler, V. Veselovsky, G. Monea, 和 R. West，“**驼羊在英语中有效吗？关于多语言变换器的潜在语言**，” *arXiv 预印本 arXiv:2402.10588*，2024。

+   [23] T. Brown, B. Mann, N. Ryder, M. Subbiah, J. D. Kaplan, P. Dhariwal, A. Neelakantan, P. Shyam, G. Sastry, A. Askell *等*，“**语言模型是少样本学习者**，” *神经信息处理系统进展*，第 33 卷，第 1877–1901 页，2020。

+   [24] V. Y. Oh 和 E. M. Tong，“**混合情绪研究中的特异性：一个理论框架**，” *人格与社会心理学评论*，第 26 卷，第 4 期，第 283–314 页，2022。

+   [25] T. Lomas, P. Diego-Rosell, K. Shiba, P. Standridge, M. T. Lee, B. Case, A. Y. Lai, 和 T. J. VanderWeele，“**复杂化的个人主义与集体主义和西方与东方：在盖洛普世界调查中探索全球视角的多样性**，” *跨文化心理学杂志*，第 54 卷，第 1 期，第 61–89 页，2023。

生成于 2024 年 8 月 4 日 20:50:36，通过 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
