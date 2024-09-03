<!--yml

分类：未分类

日期：2024-09-03 17:28:09

-->

# 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查

> 来源：[`arxiv.org/html/2408.02479`](https://arxiv.org/html/2408.02479)

1.  [I 引言](https://arxiv.org/html/2408.02479v1#S1 "在 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

1.  [II 现有工作与调查结构](https://arxiv.org/html/2408.02479v1#S2 "在 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [II-A 现有工作](https://arxiv.org/html/2408.02479v1#S2.SS1 "在 II 现有工作与调查结构 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [II-B 方法论](https://arxiv.org/html/2408.02479v1#S2.SS2 "在 II 现有工作与调查结构 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [II-C 工作的整体结构](https://arxiv.org/html/2408.02479v1#S2.SS3 "在 II 现有工作与调查结构 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

1.  [III 基础](https://arxiv.org/html/2408.02479v1#S3 "在 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [III-A 大型语言模型](https://arxiv.org/html/2408.02479v1#S3.SS1 "在 III 基础 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [III-B 模型架构](https://arxiv.org/html/2408.02479v1#S3.SS2 "在 III 基础 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [III-C 大型语言模型基础代理](https://arxiv.org/html/2408.02479v1#S3.SS3 "在 III 基础 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [III-D 单代理与多代理](https://arxiv.org/html/2408.02479v1#S3.SS4 "在 III 基础 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [III-E LLM 在软件工程中的应用](https://arxiv.org/html/2408.02479v1#S3.SS5 "在 III 基础 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

1.  [IV 需求工程与文档](https://arxiv.org/html/2408.02479v1#S4 "在 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [IV-A LLM 任务](https://arxiv.org/html/2408.02479v1#S4.SS1 "在 IV 需求工程与文档 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [IV-B 基于 LLM 的代理任务](https://arxiv.org/html/2408.02479v1#S4.SS2 "In IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [IV-C 分析](https://arxiv.org/html/2408.02479v1#S4.SS3 "In IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [IV-D 基准测试](https://arxiv.org/html/2408.02479v1#S4.SS4 "In IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [IV-E 评估指标](https://arxiv.org/html/2408.02479v1#S4.SS5 "In IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

1.  [V 代码生成和软件开发](https://arxiv.org/html/2408.02479v1#S5 "In From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [V-A LLMs 任务](https://arxiv.org/html/2408.02479v1#S5.SS1 "In V 代码生成和软件开发 ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [V-B 基于 LLM 的代理任务](https://arxiv.org/html/2408.02479v1#S5.SS2 "In V 代码生成和软件开发 ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [V-C 分析](https://arxiv.org/html/2408.02479v1#S5.SS3 "In V 代码生成和软件开发 ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [V-D 基准测试](https://arxiv.org/html/2408.02479v1#S5.SS4 "In V 代码生成和软件开发 ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [V-E 评估指标](https://arxiv.org/html/2408.02479v1#S5.SS5 "In V 代码生成和软件开发 ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

1.  [VI 自主学习和决策](https://arxiv.org/html/2408.02479v1#S6 "In From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [VI-A LLMs 任务](https://arxiv.org/html/2408.02479v1#S6.SS1 "In VI Autonomous Learning and Decision Making ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [VI-B 基于 LLM 的代理任务](https://arxiv.org/html/2408.02479v1#S6.SS2 "In VI Autonomous Learning and Decision Making ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [VI-C 分析](https://arxiv.org/html/2408.02479v1#S6.SS3 "In VI Autonomous Learning and Decision Making ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")

    1.  [第 VI-D 基准](https://arxiv.org/html/2408.02479v1#S6.SS4 "在 VI 自主学习与决策 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VI-E 评估指标](https://arxiv.org/html/2408.02479v1#S6.SS5 "在 VI 自主学习与决策 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

1.  [第 VII 软件设计与评估](https://arxiv.org/html/2408.02479v1#S7 "在 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VII-A LLM 任务](https://arxiv.org/html/2408.02479v1#S7.SS1 "在 VII 软件设计与评估 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VII-B 基于 LLM 的代理任务](https://arxiv.org/html/2408.02479v1#S7.SS2 "在 VII 软件设计与评估 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VII-C 分析](https://arxiv.org/html/2408.02479v1#S7.SS3 "在 VII 软件设计与评估 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VII-D 基准](https://arxiv.org/html/2408.02479v1#S7.SS4 "在 VII 软件设计与评估 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VII-E 评估指标](https://arxiv.org/html/2408.02479v1#S7.SS5 "在 VII 软件设计与评估 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

1.  [第 VIII 软件测试生成](https://arxiv.org/html/2408.02479v1#S8 "在 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VIII-A LLM 任务](https://arxiv.org/html/2408.02479v1#S8.SS1 "在 VIII 软件测试生成 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VIII-B 基于 LLM 的代理任务](https://arxiv.org/html/2408.02479v1#S8.SS2 "在 VIII 软件测试生成 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VIII-C 分析](https://arxiv.org/html/2408.02479v1#S8.SS3 "在 VIII 软件测试生成 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VIII-D 基准](https://arxiv.org/html/2408.02479v1#S8.SS4 "在 VIII 软件测试生成 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

    1.  [第 VIII-E 评估指标](https://arxiv.org/html/2408.02479v1#S8.SS5 "在 VIII 软件测试生成 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")

1.  [IX 软件安全与维护](https://arxiv.org/html/2408.02479v1#S9 "在 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [IX-A LLM 任务](https://arxiv.org/html/2408.02479v1#S9.SS1 "在 IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

        1.  [IX-A1 程序漏洞](https://arxiv.org/html/2408.02479v1#S9.SS1.SSS1 "在 IX-A LLM 任务 ‣ IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

        1.  [IX-A2 自动化程序修复](https://arxiv.org/html/2408.02479v1#S9.SS1.SSS2 "在 IX-A LLM 任务 ‣ IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

        1.  [IX-A3 渗透测试](https://arxiv.org/html/2408.02479v1#S9.SS1.SSS3 "在 IX-A LLM 任务 ‣ IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [IX-B 基于 LLM 的代理任务](https://arxiv.org/html/2408.02479v1#S9.SS2 "在 IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [IX-C 分析](https://arxiv.org/html/2408.02479v1#S9.SS3 "在 IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [IX-D 基准](https://arxiv.org/html/2408.02479v1#S9.SS4 "在 IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [IX-E 评估指标](https://arxiv.org/html/2408.02479v1#S9.SS5 "在 IX 软件安全与维护 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

1.  [X 讨论](https://arxiv.org/html/2408.02479v1#S10 "在 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [X-A 实验模型](https://arxiv.org/html/2408.02479v1#S10.SS1 "在 X 讨论 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [X-B 话题重叠](https://arxiv.org/html/2408.02479v1#S10.SS2 "在 X 讨论 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

    1.  [X-C 基准与指标](https://arxiv.org/html/2408.02479v1#S10.SS3 "在 X 讨论 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

1.  [XI 结论](https://arxiv.org/html/2408.02479v1#S11 "在 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

1.  [-A 基准](https://arxiv.org/html/2408.02479v1#A0.SS1 "在 从 LLM 到基于 LLM 的软件工程代理：当前挑战与未来展望")

1.  [-B 评估指标](https://arxiv.org/html/2408.02479v1#A0.SS2 "从 LLMs 到 LLM-based Agents 在软件工程中的应用：当前挑战与未来的调查")

# 从 LLMs 到 LLM-based Agents 在软件工程中的应用：当前挑战与未来的调查

Haolin Jin、Linghan Huang、Haipeng Cai、Jun Yan、Bo Li 和 Huaming Chen 均隶属于悉尼大学电气与计算机工程学院，悉尼，2006，澳大利亚。（邮箱：huaming.chen@sydney.edu.au）Haipeng Cai 任职于美国华盛顿州立大学电气工程与计算机科学学院，Jun Yan 任职于澳大利亚卧龙岗大学计算与信息技术学院，Bo Li 任职于美国芝加哥大学计算机科学系。

###### 摘要

随着大型语言模型（LLMs）的兴起，研究人员越来越多地探索它们在各个垂直领域中的应用，如软件工程。LLMs 在代码生成和漏洞检测等领域取得了显著成功。然而，它们也存在许多限制和不足。LLM-based agents 作为一种具有人工通用智能（AGI）潜力的新技术，将 LLMs 作为决策和行动的核心，解决了 LLMs 的一些固有限制，如缺乏自主性和自我改进。尽管已有大量研究和调查探索将 LLMs 应用于软件工程的可能性，但 LLMs 和 LLM-based agents 之间缺乏明确的区分。在这个领域中，尚处于制定统一标准和基准的早期阶段，以将 LLM 解决方案认定为 LLM-based agent。在本次调查中，我们广泛调查了当前 LLMs 和 LLM-based agents 在软件工程中的实践和解决方案。特别是，我们总结了六个关键主题：需求工程、代码生成、自动决策、软件设计、测试生成和软件维护。我们回顾并区分了这六个主题中的 LLMs 和 LLM-based agents 的工作，检查了它们在任务、基准和评估指标上的差异和相似之处。最后，我们讨论了使用的模型和基准，提供了对它们在软件工程中应用和有效性的全面分析。我们预计这项工作将为推动 LLM-based agents 在软件工程中的边界，提供一些启示，为未来的研究奠定基础。

###### 关键词：

大型语言模型、LLM-based Agents、软件工程、基准、软件安全、AI 系统开发

## I 引言

软件工程（SE）在人工智能技术的帮助下经历了蓬勃的发展。传统方法利用神经网络和机器学习促进了各种 SE 主题，如错误检测、代码合成和需求分析[[1](https://arxiv.org/html/2408.02479v1#bib.bib1)][[2](https://arxiv.org/html/2408.02479v1#bib.bib2)]。然而，它们常常存在局限性，包括需要独特的特征工程、可扩展性问题以及在不同代码库中的适应性。大型语言模型（LLMs）的兴起在这一领域带来了新的解决方案和发现。LLMs，如 GPT[[3](https://arxiv.org/html/2408.02479v1#bib.bib3)]和 Codex[[4](https://arxiv.org/html/2408.02479v1#bib.bib4)]，在处理 SE 中的下游任务方面展示了卓越的能力，包括代码生成、调试和文档编写。这些模型利用大量的训练数据生成类似人类的文本，提供了前所未有的流畅性和连贯性。研究表明，LLMs 通过提供智能代码建议、自动化重复任务，甚至从自然语言描述中生成完整代码片段，能够提高软件项目的生产力[[5](https://arxiv.org/html/2408.02479v1#bib.bib5)]。

尽管具有潜力，但将 LLMs 应用于 SE 仍面临重大挑战。其中一个主要问题是它们的上下文长度有限[[6](https://arxiv.org/html/2408.02479v1#bib.bib6)]，这限制了模型理解和管理庞大代码库的能力，使得在长时间交互中保持一致性变得困难。另一个主要问题是模型产生的代码虽然看似合理，但实际上可能是错误或无意义的幻觉[[7](https://arxiv.org/html/2408.02479v1#bib.bib7)]，如果没有经验丰富的开发者仔细审查，可能会引入错误或漏洞。此外，LLMs 无法使用外部工具，限制了它们获取实时数据的能力，阻碍了其在训练范围外执行任务的能力，这降低了其在动态环境中的有效性。这些局限性对 LLMs 在 SE 中的应用产生了重大影响，也突显了专家开发者需要对 LLM 生成的代码进行严谨的修正和验证以确保准确性和安全性[[8](https://arxiv.org/html/2408.02479v1#bib.bib8)]。在复杂项目中，LLMs 的静态特性可能妨碍其适应不断变化的需求或高效地融入新信息。此外，LLMs 通常无法与外部工具或数据库交互，进一步限制了它们在动态和不断发展的 SE 环境中的实用性。

为应对这些挑战，基于 LLM 的智能体已经出现[[9](https://arxiv.org/html/2408.02479v1#bib.bib9)][[10](https://arxiv.org/html/2408.02479v1#bib.bib10)]，结合了 LLM 的优势与外部工具和资源，实现了更动态和自主的操作。这些智能体利用了 AI 领域的最新进展，如检索增强生成（RAG）和工具利用，以执行更复杂和具备上下文感知的任务[[11](https://arxiv.org/html/2408.02479v1#bib.bib11)]。例如，OpenAI 的 Codex 已被集成到 GitHub Copilot 中[[12](https://arxiv.org/html/2408.02479v1#bib.bib12)]，在开发环境中提供实时代码建议和补全。与静态 LLM 不同，基于 LLM 的智能体能够执行广泛的任务，如通过识别和修复错误进行自主调试，主动重构代码以提高效率或可读性，以及生成随着代码库演变的自适应测试用例。这些功能使得基于 LLM 的智能体成为 SE 中强大的工具，能够处理比传统 LLM 更复杂和动态的工作流。

历史上，AI 智能体专注于基于预定义规则或从互动中学习的自主行动[[13](https://arxiv.org/html/2408.02479v1#bib.bib13)][[14](https://arxiv.org/html/2408.02479v1#bib.bib14)]。LLMs 的集成为这一领域带来了新的机遇，提供了更复杂智能体行为所需的语言理解和生成能力。[[10](https://arxiv.org/html/2408.02479v1#bib.bib10)]表明，基于 LLM 的智能体具备自主推理和决策能力，实现了 WS（World Scope）的第三和第四级[[15](https://arxiv.org/html/2408.02479v1#bib.bib15)]，这概述了从自然语言处理（NLP）到通用人工智能的进展。在软件工程中，基于 LLM 的智能体在自主调试、代码重构和自适应测试生成等领域显示出前景，展示了接近人工通用智能（AGI）的能力。

![参考说明](img/2af34ffde00ea7ac872e0c0b6de0ee0e.png)

图 1：2020-2024 年 LLMs 和基于 LLM 的智能体的论文数量

在这项工作中，我们呈现了我们所知的第一个调查，概述了 LLM 向基于 LLM 的智能体在 SE 领域的集成和转化。我们的调查涵盖了 SE 中的六个关键主题：

1.  1.

    需求工程和文档编制：捕捉、分析和记录软件需求，以及生成用户手册和技术文档。

1.  2.

    代码生成和软件开发：自动化代码生成，协助开发生命周期，重构代码，并提供智能代码建议。

1.  3.

    自主学习和决策：突出 LLM 基于智能体在 SE 背景下自主学习、决策和自适应规划的能力。

1.  4.

    软件设计与评估：参与设计过程、架构验证、性能评估和代码质量评估。

1.  5.

    软件测试生成：生成、优化和维护软件测试，包括单元测试、集成测试和系统测试。

1.  6.

    软件安全与维护：增强安全协议、促进维护任务，并协助漏洞检测和修补。

详细来说，我们旨在解决以下研究问题：

+   •

    RQ1: LLMs 和基于 LLM 的代理在软件工程中的最先进技术和实践是什么？（第[IV](https://arxiv.org/html/2408.02479v1#S4 "IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")、[IX](https://arxiv.org/html/2408.02479v1#S9 "IX Software Security and Maintenance ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")节）

+   •

    RQ1: LLMs 和基于 LLM 的代理在软件工程应用中任务表现的关键差异是什么？（第[IV](https://arxiv.org/html/2408.02479v1#S4 "IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")、[IX](https://arxiv.org/html/2408.02479v1#S9 "IX Software Security and Maintenance ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")节）

+   •

    RQ2: 哪些基准数据集和评估指标最常用于评估 LLMs 和基于 LLM 的代理在软件工程任务中的性能？（第[IV](https://arxiv.org/html/2408.02479v1#S4 "IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")、[IX](https://arxiv.org/html/2408.02479v1#S9 "IX Software Security and Maintenance ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")和[X](https://arxiv.org/html/2408.02479v1#S10 "X Discussion ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")节）

+   •

    RQ3: 在利用 LLMs 进行软件工程时，主要采用哪些实验模型和方法？（第[X](https://arxiv.org/html/2408.02479v1#S10 "X Discussion ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")节）

## II 现有研究与调查结构

### II-A 现有工作

近年来，大型语言模型主要应用于帮助程序员生成代码和修复漏洞。这些模型根据用户的输入理解和完成代码或文本，利用其训练数据和推理能力。在以往的调查论文中，例如 Angela Fan 的研究 [[8](https://arxiv.org/html/2408.02479v1#bib.bib8)]，对需求工程的阐述并不多。正如论文中提到的，软件工程师通常不愿依赖 LLM 来进行更高层次的设计目标。然而，随着 LLM 通过提示工程和链式思维（COT）[[16](https://arxiv.org/html/2408.02479v1#bib.bib16)]等多种方法在上下文分析和推理能力上取得了显著进展，其在需求工程中的应用逐渐增加。表 [I](https://arxiv.org/html/2408.02479v1#S2.T1 "TABLE I ‣ II-A Existing works ‣ II EXISTING WORKS AND THE SURVEY STRUCTURE ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future") 总结并分类了需求工程中的任务。许多研究利用模型进行需求分类和生成。由于该集合主要集中在 2023 年下半年及 2024 年 4 月之前，并且有些论文涉及多个任务，因此表格未能反映我们收集的确切论文数量。

表 I：SE 任务的分布

| 分类 | 大语言模型（LLMs） | 基于 LLM 的代理 | 总计 |
| --- | --- | --- | --- |

|

&#124; 需求 &#124;

&#124; 工程 和 &#124;

&#124; 文档 &#124;

|

&#124; 需求分类和提取 (3) &#124;

&#124; 需求生成和描述 (4) &#124;

&#124; 需求满足评估 (1) &#124;

&#124; 规范生成 (3) &#124;

&#124; 质量评估 (2) &#124;

&#124; 模糊检测 (2) &#124;

|

&#124; 半结构化文档生成 (1) &#124;

&#124; 生成安全需求 (1) &#124;

&#124; 自动生成基于 &#124;

&#124; 高级需求 (1) &#124;

&#124; 自动化用户故事质量提升 (2) &#124;

| 19 |
| --- |

|

&#124; 代码生成 &#124;

&#124; 和 &#124;

&#124; 软件 &#124;

&#124; 开发 &#124;

|

&#124; 代码生成调试 (3) &#124;

&#124; 代码评估 (2) &#124;

&#124; 实现 HTTP 服务器 (1) &#124;

&#124; 增强代码生成能力 (3) &#124;

&#124; 专用代码生成 (2) &#124;

&#124; 人工反馈偏好模拟 (1) &#124;

|

&#124; 自动化软件开发过程 (5) &#124;

&#124; 大规模代码和文档生成 (1) &#124;

&#124; 工具和外部 API 使用 (2) &#124;

&#124; 多代理协作和代码优化 (2) &#124;

&#124; 提高代码生成质量 (2) &#124;

| 23 |
| --- |

|

&#124; 自主 &#124;

&#124; 学习 &#124;

&#124; 和决策 &#124;

&#124; 制作 &#124;

|

&#124; 多 LLM 决策 (1) &#124;

&#124; 创造力评估 (1) &#124;

&#124; 自我识别与修正代码 (1) &#124;

&#124; 判断聊天机器人响应 (1) &#124;

&#124; 模仿人类科学调试 (1) &#124;

&#124; 有意识的问题解决 (1) &#124;

|

&#124; 协作决策与多智能体 &#124;

&#124; 系统 (5) &#124;

&#124; 自主推理与决策 (7) &#124;

&#124; 通过反馈学习与适应 (4) &#124;

&#124; 人工智能能力的模拟与评估 &#124;

&#124; 行为 (2) &#124;

| 24 |
| --- |

|

&#124; 软件设计 &#124;

&#124; 和评估 &#124;

|

&#124; 创造力评估 (1) &#124;

&#124; SE 任务中的表现 (1) &#124;

&#124; 教育效用与评估 (1) &#124;

&#124; 效率优化 (2) &#124;

|

&#124; 软件工程过程自动化 (3) &#124;

&#124; 增强问题解决与推理 (4) &#124;

&#124; AI 模型的集成与管理 &#124;

&#124; 工具 (3) &#124;

&#124; 优化与效率提升 (2) &#124;

&#124; 动态环境下的性能评估 &#124;

&#124; (2) &#124;

| 19 |
| --- |

|

&#124; 软件测试 &#124;

&#124; 生成 &#124;

|

&#124; 错误重现与调试 (2) &#124;

&#124; 安全测试 (2) &#124;

&#124; 测试覆盖率 (2) &#124;

&#124; 通用模糊测试 (1) &#124;

|

&#124; 多智能体协作测试生成 (2) &#124;

&#124; 自主测试与对话接口 &#124;

&#124; (3) &#124;

| 11 |
| --- |

|

&#124; 软件安全 &#124;

&#124; 和 &#124;

&#124; 维护 &#124;

|

&#124; 漏洞检测 (6) &#124;

&#124; 漏洞修复 (2) &#124;

&#124; 程序修复 (4) &#124;

&#124; 鲁棒性测试 (1) &#124;

&#124; 需求分析 (1) &#124;

&#124; 模糊测试 (1) &#124;

&#124; 重复条目 (1) &#124;

&#124; 代码生成与调试 (4) &#124;

&#124; 渗透测试与安全评估 (2) &#124;

&#124; 程序分析与调试 (1) &#124;

|

&#124; 自主软件开发与 &#124;

&#124; 维护 (4) &#124;

&#124; 调试与故障定位 (4) &#124;

&#124; 漏洞检测与渗透 &#124;

&#124; 测试 (3) &#124;

&#124; 智能合约审计与修复 (2) &#124;

&#124; 安全性与风险分析 (2) &#124;

&#124; 自适应与沟通代理 (1) &#124;

| 39 |
| --- |

![参见说明](img/6862c43b5fdc8d955492831d36725be4.png)

图 2: 论文分布

尽管其他研究已调查了 LLMs 在一些 SE 任务中的应用[[17](https://arxiv.org/html/2408.02479v1#bib.bib17)] [[8](https://arxiv.org/html/2408.02479v1#bib.bib8)] [[18](https://arxiv.org/html/2408.02479v1#bib.bib18)]，但它们缺乏对一般 SE 领域的广泛覆盖，以融入最新的研究进展。更重要的是，LLMs 是这些工作的主要贡献，但没有区分 LLMs 和基于 LLM 的代理之间的能力。我们在表[II](https://arxiv.org/html/2408.02479v1#S2.T2 "表 II ‣ II-A 现有工作 ‣ II 现有工作和调查结构 ‣ 从 LLMs 到基于 LLM 的工程师：当前、挑战和未来的调查")中总结了我们的工作与其他工作的区别，本调查通过明确分析 LLMs 和基于 LLM 的代理在六个 SE 领域中的应用，提供了全面而最新的评审。从以前的研究中可以看出，LLMs 在各种应用和任务中的表现严重依赖于模型的固有能力[[10](https://arxiv.org/html/2408.02479v1#bib.bib10)]。更重要的是，早期的调查通常展示了跨度较大的出版日期的论文的发现，导致 LLMs 在不同 SE 任务中的内容差异显著。例如，需求工程的研究相对较新，导致以前的调查中这一领域的内容稀少。基于 LLM 的代理的近期兴起，其增强的能力和自主性填补了这些空白。通过关注最新研究并清楚地区分 LLMs 和基于 LLM 的代理，我们的调查提供了对这些技术应用的彻底而深入的概述，以及它们为 SE 带来的新机会。

总结来说，我们总共收集了 117 篇与此主题直接相关的论文，涵盖了前面提到的六个 SE 领域，如图所示。[1](https://arxiv.org/html/2408.02479v1#S1.F1 "图 1 ‣ I 引言 ‣ 从 LLMs 到基于 LLM 的工程师：当前、挑战和未来的调查")。我们的分析区分了 LLM 和基于 LLM 的代理的贡献，提供了比较概述，并解决了以前调查的局限性。考虑到基于 LLM 的代理领域的新颖性和缺乏标准化基准，本工作旨在提供详细的评审，以指导未来的研究，并提供这些技术在 SE 中潜力的更清晰视角。

表 II: 我们的工作与现有 LLM 在 SE 中的工作的比较

| 论文 | 年份 | 领域 | 基准 | 评价指标 |
| --- | --- | --- | --- | --- |

&#124; 代理 &#124;

&#124; 在 SE 中的应用 &#124;

|

&#124; 代理 &#124;

&#124; 区别 &#124;

|

| --- | --- | --- | --- | --- | --- | --- |
| --- | --- | --- | --- | --- | --- | --- |
|  [[19](https://arxiv.org/html/2408.02479v1#bib.bib19)] | 2023 | GenAI 在 SE 中的应用 | ✓ | ✓ | ✓ | ✗ |
|  [[8](https://arxiv.org/html/2408.02479v1#bib.bib8)] | 2023 | LLM 在 SE 中的应用 | ✓ | ✓ | ✓ | ✗ |
|  [[18](https://arxiv.org/html/2408.02479v1#bib.bib18)] | 2023 | LLM 在 SE 中的生成任务 | ✓ | ✓ | ✗ | ✗ |
|  [[20](https://arxiv.org/html/2408.02479v1#bib.bib20)] | 2023 | LLM 在语法理解中的应用 | ✓ | ✓ | ✗ | ✗ |
|  [[21](https://arxiv.org/html/2408.02479v1#bib.bib21)] | 2024 | LLM4Code in SE | ✓ | ✓ | ✗ | ✗ |
|  [[17](https://arxiv.org/html/2408.02479v1#bib.bib17)] | 2024 | LLM 在 SE 中的过程优化 | ✓ | ✓ | ✗ | ✗ |
|  [[22](https://arxiv.org/html/2408.02479v1#bib.bib22)] | 2024 | LLM 在 SE 中的生成任务 | ✓ | ✓ | ✗ | ✗ |
| 我们的 | 2024 | LLM 与基于 LLM 的智能体在 SE 中的应用 | ✓ | ✓ | ✓ | ✓ |

### II-B 方法论

论文收集过程主要涉及搜索 DBLP 和 arXiv 数据库，重点关注 2023 年下半年至 2024 年 5 月的最新研究。该方法确保了最新研究的纳入。我们筛选了与 LLM 无关的论文和页数少于七页的论文。为了进一步细化选择，我们使用了表[III](https://arxiv.org/html/2408.02479v1#S2.T3 "TABLE III ‣ II-C Overall Structure of the Work ‣ II EXISTING WORKS AND THE SURVEY STRUCTURE ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")中的关键词搜索与 SE 相关的工作。然后，我们手动筛选剩余的论文，以去除任何格式错误或学生项目。此外，我们还采用了滚雪球搜索技术，以捕捉可能最初遗漏的重要工作。总体而言，我们确定了 117 篇相关论文。图[2](https://arxiv.org/html/2408.02479v1#S2.F2 "Figure 2 ‣ II-A Existing works ‣ II EXISTING WORKS AND THE SURVEY STRUCTURE ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")展示了这些论文在六个 SE 领域中的分布以及基于 LLM 的智能体研究的比例。然而，由于一些论文可以被归为多类领域，因此图中的文献综述总数超过了 117 篇。

### II-C 工作的总体结构

本文的剩余部分组织如下：第二部分介绍了 LLMs 和基于 LLM 的智能体的架构和背景，包括 RAG 的概述、工具利用以及它们对 SE 的影响。第 3-8 节是比较分析，总结并比较了在六个 SE 领域中 LLM 和基于 LLM 的智能体研究中使用的数据集、任务、基准和指标。第九部分是一般讨论，第十部分是最终结论。

TABLE III: 软件工程主题的关键词

| 主题 | 关键词 |
| --- | --- |
| 软件安全与维护 | 软件安全、漏洞检测、自动程序修复、自我调试、漏洞重现 |
| 代码生成和软件开发 | 代码生成、自动代码合成、代码重构、编程语言翻译、软件开发自动化、代码补全、AI 辅助编码、开发生命周期自动化 |
| 需求工程与文档 | 需求工程、软件需求分析、自动化需求文档、技术文档生成、用户手册生成、文档维护、需求建模、需求获取 |
| 软件设计与评估 | 软件设计自动化、架构验证、设计优化、性能评估、代码质量评估、软件度量、设计模式识别、架构分析、代码结构分析 |
| 软件测试生成 | 测试用例生成、自动化测试、单元测试生成、集成测试生成、系统测试生成、测试套件优化、故障定位、测试维护、回归测试、适应性测试 |
| 自主学习与决策 | 自主学习系统、决策制定、适应性规划、项目管理自动化、自我改善软件、自主软件代理 |

## III 基础知识

在本节中，我们介绍大型语言模型的基础概念，包括其框架的演变及其架构的概述。接下来，我们将讨论基于 LLM 的代理，探索单代理系统和多代理系统。我们还将涵盖这些系统的背景以及它们在软件工程领域中的应用和区别。

### III-A 大型语言模型

大型语言模型与自然语言处理（NLP）之间存在固有的联系，自然语言技术的历史发展可以追溯到 1950 年代。最早期通过机器使用特定规则生成语言对话的尝试可以追溯到 1950 至 1970 年间。1980 年代机器学习技术的出现以及 1990 年代神经网络的突破性引入标志着 NLP 的新纪元[[23](https://arxiv.org/html/2408.02479v1#bib.bib23)]。这些进展促进了 NLP 领域的显著进步，尤其是在文本翻译和生成技术的发展方面。该时期长短期记忆（LSTM）和递归神经网络（RNN）的发展使得对语言数据的顺序性质处理更加有效[[24](https://arxiv.org/html/2408.02479v1#bib.bib24)] [[25](https://arxiv.org/html/2408.02479v1#bib.bib25)]。这些模型解决了上下文依赖性缺失的问题，从而提升了 NLP 在各个领域的应用。

2017 年，谷歌研究团队引入了名为“Transformer”的新框架[[26](https://arxiv.org/html/2408.02479v1#bib.bib26)]。基于自注意力机制的 transformer 模型显著提高了语言模型的效果。位置编码的引入不仅解决了长序列依赖问题，还实现了并行计算，这相比于之前的模型是一个重大改进。2018 年，OpenAI 开发了基于 transformer 架构的生成预训练变换器（GPT）[[3](https://arxiv.org/html/2408.02479v1#bib.bib3)]。GPT-1 的核心理念是利用大量未标注的文本进行预训练，以学习语言的模式和结构，然后进行针对特定任务的微调。在接下来的两年中，OpenAI 发布了 GPT-2 和 GPT-3，将参数数量增加到 1750 亿，并在上下文理解和文本生成方面展示了强大的能力[[27](https://arxiv.org/html/2408.02479v1#bib.bib27)]。GPT-4 由 OpenAI 于 2023 年推出，代表了 GPT-3.5 之后的一个里程碑。尽管 GPT-4 维持了约 1750 亿的参数量，但其性能和多样性有了显著提升。通过更精细的训练技术和算法优化，GPT-4 增强了语言理解和生成的能力，特别是在处理复杂文本和特殊语境方面表现突出。与谷歌的 PaLM 或 Meta 的 OPT 等当代模型相比，GPT-4 在多任务学习和文本生成中的逻辑一致性方面继续突出。尽管谷歌的 PaLM 模型参数量高达 540 亿，GPT-4 在更广泛的自然语言处理任务中显示了更强的泛化能力[[28](https://arxiv.org/html/2408.02479v1#bib.bib28)]。在开源的大型模型中，Meta 的 OPT 模型参数量与 GPT-4 相似，提供了直接的竞争。尽管 OPT 在开放性和可访问性方面具有优势，但 GPT-4 在如创意写作和复杂问题解决等特定应用领域仍保持领先[[29](https://arxiv.org/html/2408.02479v1#bib.bib29)]。

### III-B 模型架构

有三种常见的 LLM 架构，其中一种是编码器-解码器架构，以传统的变压器模型为例。这种架构由六个编码器和六个解码器组成，数据输入系统后，首先会经过编码器，在这里通过模型的自注意力机制进行顺序特征提取。随后，解码器利用编码器生成的词向量来生成输出，这种技术在机器翻译任务中很常见，编码器通过多个注意力层和前馈网络处理来自一种语言的词向量，从而创建上下文的表示。解码器然后使用这些信息逐步构建正确的翻译文本。一个最近的例子是 CodeT5+模型，由 Salesforce AI Research 在 2023 年推出[[30](https://arxiv.org/html/2408.02479v1#bib.bib30)]。该模型是对原始 T5 架构的改进，旨在提高代码理解和生成任务的性能。它结合了灵活的架构和多样化的预训练目标，以优化在这些专业领域的效果。这一发展突显了编码器-解码器架构在应对日益复杂的 NLP 挑战中的能力。

编码器仅架构，如其名称所示，去除了整个结构中的解码器，使数据更加紧凑。与 RNN 不同，这种架构是无状态的，使用掩蔽机制允许输入处理而不依赖于隐藏状态，同时加速了并行处理速度并提供了出色的上下文感知。BERT（Bidirectional Encoder Representations from Transformers）是这种架构的代表模型，该模型完全基于编码器架构。BERT 利用编码器强大的特征提取能力和预训练技术来学习文本的双向表示，在情感分析和上下文分析中取得了出色的结果[[31](https://arxiv.org/html/2408.02479v1#bib.bib31)]。

在变换器框架中，Decoder-only 架构主要涉及解码器接收处理后的词向量并生成输出。利用解码器直接生成文本加快了文本生成和序列预测等任务的速度。这种具有高可扩展性的特性被称为自回归性，这也是为什么像 GPT 这样的流行模型使用这种架构。2020 年，GPT-3 的卓越表现和显著的少样本学习能力展示了 Decoder-only 架构的巨大潜力 [[32](https://arxiv.org/html/2408.02479v1#bib.bib32)]。鉴于从头开始训练模型所需的巨大计算成本和时间，以及参数数量的指数增长，许多研究人员现在更愿意利用预训练模型进行进一步研究。最受欢迎的开源预训练语言模型 LLaMA，由 Meta AI 开发，也采用了 Decoder-only 架构 [[33](https://arxiv.org/html/2408.02479v1#bib.bib33)]，正如之前提到的，这种结构的自回归性和简易性使得模型更容易训练和微调。

### III-C 大型语言模型基础的智能体

智能体的概念甚至可以追溯到 19 世纪，通常被称为智能体，设想其拥有与人类相当的智能。近年来，随着 AI 技术的发展，AI 智能体的能力显著提高，特别是在强化学习方面。这一发展使得 AI 智能体能够自主处理任务，并根据指定的奖惩规则进行学习和改进。值得注意的里程碑包括 AlphaGo [[34](https://arxiv.org/html/2408.02479v1#bib.bib34)]，它利用强化学习击败了围棋比赛的世界冠军。

GPT 的成功进一步推动了这一领域的发展，研究人员探讨了将大语言模型作为 AI 智能体“脑”的可能性，得益于 GPT 强大的文本理解和推理能力。2023 年，复旦大学的研究团队[[10](https://arxiv.org/html/2408.02479v1#bib.bib10)]进行了关于基于 LLM 的智能体的全面调查，考察了它们的感知、行为和认知。传统的 LLM 通常仅基于给定的自然语言描述生成响应，缺乏独立思考和判断的能力。而基于 LLM 的智能体能够通过多轮互动和定制提示来收集更多信息，从而使模型能够自主思考和决策。2023 年，Andrew Zhao 提出了 ExpeL 框架[[35](https://arxiv.org/html/2408.02479v1#bib.bib35)]，它利用 ReAct 作为规划框架，并结合经验池[[36](https://arxiv.org/html/2408.02479v1#bib.bib36)]。这使得 LLM 能够从过去的记录中提取见解，以帮助回答后续相关问题，通过让 LLM 分析为什么之前的回答是错误的，它从经验中学习识别问题。

与此同时，基于 LLM 的具身智能体的应用也成为近年来的热门研究领域。基于 LLM 的具身智能体是将 LLM 与具身智能体[[37](https://arxiv.org/html/2408.02479v1#bib.bib37)]集成的智能系统。这些系统不仅能够处理自然语言，还能通过感知和在物理或虚拟环境中的行动完成任务。通过将语言理解与实际行动相结合，这些智能体能够在更复杂的环境中执行任务。这种集成通常涉及使用视觉领域技术来处理和理解视觉数据，以及使用强化学习算法来训练智能体在环境中采取最佳行动。这些算法通过奖励机制引导智能体学习如何在不同情境下做出最佳决策，而 LLM 则作为大脑来理解用户指令并生成适当的反馈。2023 年，Guanzhi Wang 推出了 VOYAGER，一种具有大语言模型的开放式具身智能体[[38](https://arxiv.org/html/2408.02479v1#bib.bib38)]。它结合了 GPT-4、输入提示、迭代提示机制以及技能库，使得基于 LLM 的智能体能够自主学习并玩 Minecraft，成为该游戏中的首个终身学习智能体。

![参见说明](img/43b8960199227a1a1094ed48f84ed85c.png)

图 3：常见数据增强方法的示意图

目前，各种代理系统不断涌现，它们依赖大型语言模型进行判断，并结合少量学习和多轮对话等技术对模型进行微调。然而，由于数据集的缺乏以及基于 LLM 的代理的创新性，许多研究人员采用不同的方法进行数据增强。常见的方法包括同义词替换，即用同一领域的同义词替换文本中的词语，以增加文本的多样性；反向翻译，即将文本翻译成另一种语言，然后再翻译回原语言，以生成具有略微不同语法结构和词汇选择的新文本；**释义**是指通过手动或自动方式创建的语境相似但表达略有不同的新对话；**合成数据生成**是指使用预训练模型生成合成数据，如图所示。[3](https://arxiv.org/html/2408.02479v1#S3.F3 "Figure 3 ‣ III-C Large Language Model Based Agent ‣ III Preliminaries ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")。在 2023 年，**陈曦·怀特豪斯**探索了使用 LLM 进行数据增强，以提高多语言常识推理数据集的性能，特别是在极端有限的训练数据条件下[[39](https://arxiv.org/html/2408.02479v1#bib.bib39)]。该研究使用了各种 LLM（如 Dolly-v2、StableVicuna、ChatGPT 和 GPT-4）生成新数据。这些模型被提示创建与原始数据类似的新示例，从而增加训练数据的多样性和数量。**提示工程**被提到是与 LLM 有效互动的关键技能。通过应用这些提示模式，用户可以高效地自定义与 LLM 的对话，确保生成高质量的输出，并实现复杂的自动化任务。在 2023 年，**朱尔斯·怀特**提出了一系列方法和模式，以增强提示工程，优化与 LLM（如 ChatGPT）的互动[[40](https://arxiv.org/html/2408.02479v1#bib.bib40)]。该研究将提示工程分为五个主要领域：输入语义、输出定制、错误识别、提示改进和互动，以解决各种问题并适应不同领域。

一个显著的技术是检索增强生成（RAG），输入问题通过与索引库中的文档进行相似度匹配，尝试找到相关结果。如果检索到类似文档，这些文档将与输入问题一起组织生成新的提示，然后输入到大型语言模型中。目前，大型语言模型具备长文本记忆能力，许多研究测试了 Gemini v1.5 在 Needle In A Haystack (NIAH)评估中的表现，以探讨 RAG 是否已经过时[[41](https://arxiv.org/html/2408.02479v1#bib.bib41)]。然而，从成本和开支等多个角度来看，RAG 仍然具有显著优势（RAG 可能比使用所有 tokens 便宜 99%）。此外，长文本可能对响应性能产生负面影响，当输入文本过长时，LLM 的响应速度可能变慢。因此，LLM 在上下文长度方面的进展不会完全取代 RAG 的作用，而是作为彼此的补充。

### III-D 单一与多代理

单一代理系统利用大语言模型（LLM）的能力来执行各种任务，这些代理通常使用单一的 LLM 来理解和回应用户查询、生成内容或根据预定义指令执行自动化任务。单一代理常用于任务接受一般答案且不需要复杂决策的场景。例如，客服聊天机器人、用于调度的虚拟助手和自动内容生成工具。然而，单一代理可能在处理长文本输入时遇到困难，导致回答不一致或无关。处理需要广泛知识或上下文的任务时，这些系统的可扩展性也有限，这个问题通常在长文本中更为严重，因为大型语言模型无法在一次处理中过全面理解和分析过于冗长的信息。大型语言模型的一个主要问题是虚假信息[[7](https://arxiv.org/html/2408.02479v1#bib.bib7)]。虚假信息指的是 LLM 生成的虚构信息或定义，这些信息以看似逻辑合理的语言呈现给用户。大多数关于 LLM 的研究论文都指出了这个问题，尽管提示工程或工具干预可以缓解虚假信息的影响，但无法完全消除。2023 年，Ziwei Ji 对自然语言生成中的虚假信息进行了深入研究[[42](https://arxiv.org/html/2408.02479v1#bib.bib42)]。这项调查回顾了应对 NLG 中虚假信息的进展和挑战，全面分析了不同任务中的虚假信息现象，包括其定义和分类、原因、评估指标和缓解方法。

多代理系统涉及多个 LLM 或代理的协作，以有效解决复杂任务。这些系统充分利用了多个模型的优势，每个模型专注于任务的特定方面，从而减少了单一代理中由多进程引起的开销，代理之间的协作使得问题解决能力更加复杂和稳健。由于其卓越的能力，越来越多的研究人员开始探索基于多 LLM 的代理领域，并开始将其应用于软件工程领域。在 2024 年，许多研究人员将多代理系统应用于实际实验中[[43](https://arxiv.org/html/2408.02479v1#bib.bib43)] [[44](https://arxiv.org/html/2408.02479v1#bib.bib44)]。

多代理系统在以下方面解决了单代理系统的局限性：

+   •

    增强的上下文管理：多个代理可以维护和共享上下文，在长时间交互中生成更连贯和相关的回应。

+   •

    专业化和分工：不同的代理可以专注于问题的特定任务或方面，从而提高效率和效果。

+   •

    稳健性和错误纠正：协作代理可以相互交叉检查和验证彼此的输出，减少错误的可能性并提高整体可靠性。

+   •

    上下文一致性：多代理系统可以更好地管理长对话中的上下文。多个代理的协作提高了事件缓解的效率。

+   •

    可扩展性和灵活性：这些系统可以整合专业化的代理来扩展和处理更复杂的任务。通过多个代理之间的分工，代码生成的质量得到了提升。

+   •

    动态问题解决：通过整合具有不同专业知识的代理，多代理系统可以适应更广泛的问题并提供更准确的解决方案。

### III-E 软件工程中的 LLM

最近，应用于特定垂直领域如医疗和金融的通用人工智能模型的趋势逐渐增多。在软件工程中，新的人工智能代理正在出现，它们比之前的 LLM 应用更加灵活和智能，尽管它们利用了不同的数据和实验。这种持续的创新强调了人工智能代理在各个领域的变革潜力，这些模型在文本理解和生成方面表现出色，推动了软件开发和维护中的创新应用。

LLM 通过促进诸如代码生成、缺陷预测和自动化文档编制等任务，对软件工程产生了深远的影响。将这些模型集成到开发工作流程中，不仅简化了编码过程，还减少了人为错误。基于 LLM 的智能体通过集成决策制定和互动问题解决功能，增强了基本 LLM 的能力。这些智能体可以通过与其他软件工具互动来理解和生成结果，从而优化工作流程，并做出自主决策以改进软件开发实践。在 2023 年，Yann Dubois 介绍了 AlpacaFarm 框架[[45](https://arxiv.org/html/2408.02479v1#bib.bib45)]，该框架使用 LLM 在复杂环境中模拟软件智能体的行为。此外，在自动程序修复（APR）领域进行了重要研究。2024 年，Islem Bouzenia 介绍了 RepairAgent[[46](https://arxiv.org/html/2408.02479v1#bib.bib46)]，这是另一个旨在自动软件修复的基于 LLM 的工具，这一工具减少了开发者修复问题所花费的时间。此外，在 2023 年，Emanuele Musumeci 展示了一个多智能体 LLM 系统[[47](https://arxiv.org/html/2408.02479v1#bib.bib47)]，该系统涉及一个多智能体架构，其中每个智能体在文档生成中扮演特定角色。该系统在没有大量人工监督的情况下显著改善了复杂文档结构的处理。除此之外，LLM 在软件测试、软件设计以及软件安全和维护等新兴领域也做出了杰出贡献。

目前，对于一个 LLM 必须展现的能力，以被认为是基于 LLM 的智能体，没有一个全面而准确的定义。由于 LLM 在软件工程中的应用相对广泛，一些框架已经表现出一定程度的自主性和智能，本研究基于 2024 年上半年的主流定义和文献，定义了 LLM 与基于 LLM 的智能体之间的区别。在本次调查中，当 LLM 架构满足表[IV](https://arxiv.org/html/2408.02479v1#S3.T4 "TABLE IV ‣ III-E LLM in Software Engineering ‣ III Preliminaries ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")中的标准时，它可以被称为智能体。

表 IV: 基于 LLM 的智能体标准

| 标准 |
| --- |
| 1) LLM 作为大脑（信息处理和思想生成的中心）。2) 该框架不仅依赖于 LLM 的语言理解和生成能力，还具备决策和规划能力。3) 如果有工具可用，模型可以自主决定何时使用哪些工具，并将结果整合到预测中，以提高任务完成的效率和准确性。4) 模型可以从多个同质结果中选择最佳解决方案（评估和选择各种可能解决方案的能力）。5) 模型能够处理多次交互并保持上下文理解。6) 模型具有自主学习能力和适应性。 |

## IV 需求工程与文档编制

需求工程是软件工程中的一个关键领域，在软件开发过程中发挥着至关重要的作用，其主要任务是确保软件系统满足所有相关利益相关者的需求。通常，项目开发中的需求工程涉及多个步骤，开发人员需要充分理解用户的需求和期望，以确保软件系统的开发方向符合实际需求。然后，收集到的需求将由开发团队进行组织和评估。需求规范是正式记录分析过的需求的过程，该规范必须准确简洁，并且需要进行需求验证，以确保开发人员构建的是用户所需的，并且符合规范。需求工程还包括需求管理，这是一项贯穿整个软件开发生命周期的任务，开发人员需要持续跟踪、控制并响应开发过程中发生的任何变化，确保这些变化不会对项目的进展和整体质量产生负面影响。

### IV-A LLMs 任务

在需求工程领域，LLMs（大语言模型）在自动化和提升需求获取、分类、生成、规格生成和质量评估等任务方面展示了显著的潜力。需求分类和提取是需求工程中开发过程中的一个关键任务。常常会遇到客户一次性提出多个需求的情况，这需要开发者进行人工分类。通过将需求分类为功能性需求和非功能性需求，开发者可以更好地理解和管理这些需求。得益于 LLMs 在分类任务中的强大性能，许多相关的框架已经被开发出来。PRCBERT 框架利用 BERT 预训练语言模型，通过灵活的提示模板将分类问题转化为一系列二分类任务，从而显著提高了分类性能[[48](https://arxiv.org/html/2408.02479v1#bib.bib48)]。研究表明，PRCBERT 在 PROMISE 数据集上取得了 96.13%的 F1 分数，超越了之前的最先进的 NoRBERT[[49](https://arxiv.org/html/2408.02479v1#bib.bib49)]和 BERT-MLM 模型[[31](https://arxiv.org/html/2408.02479v1#bib.bib31)]。此外，ChatGPT 在需求信息检索中的应用也显示出令人鼓舞的结果，通过对需求文档进行分类和提取，ChatGPT 在零样本设置下达到了相当甚至更好的$F\beta$分数，尤其是在特征提取任务中，其表现超过了基准模型[[50](https://arxiv.org/html/2408.02479v1#bib.bib50)]。正如表[I](https://arxiv.org/html/2408.02479v1#S2.T1 "TABLE I ‣ II-A Existing works ‣ II EXISTING WORKS AND THE SURVEY STRUCTURE ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")中所示，关于使用 LLMs 自动生成需求和描述的文献和研究也非常丰富。

通过自动化生成和描述需求，可以提高需求获取的效率和准确性。研究表明，大型语言模型（LLMs）在需求生成任务中具有显著潜力。例如，使用 ChatGPT 来生成和收集用户需求，研究发现具有专业知识的参与者可以更有效地使用 ChatGPT，这表明领域专业知识对 LLM 辅助需求获取的有效性有影响[[51](https://arxiv.org/html/2408.02479v1#bib.bib51)]。该研究采用了对 LLM 输出的定性评估，按照预定义的需求匹配标准进行评估，包括完全匹配、部分匹配和提取需求的相关性，尽管成功率因任务复杂性和用户经验而异，但结果显示 LLMs 可以有效地协助获取需求，并且在基于大量训练数据的基础上特别有助于识别和建议需求。SRS（软件需求规格说明书）生成是一个重要任务，开发人员通常花费大量时间来完善和验证。在[[52](https://arxiv.org/html/2408.02479v1#bib.bib52)]中，研究人员使用了迭代提示和单一综合提示来评估 LLMs 生成 SRS 的性能。实验对 GPT-4 和 CodeLlama-34b（一个封闭源 LLM 和一个开源 LLM）进行了综合评估，生成的 SRS 将与人工编写的 SRS 进行比较，并最终通过 Likert 量表进行评分。结果表明，人工生成的 SRS 总体上优于 LLMs，但 CodeLlama 在某些特定类别中有时表现更好。CodeLlama 在完整性和内部一致性方面的评分高于 GPT-4，但不够简洁，因此这项研究展示了使用微调 LLMs 生成 SRS 的潜力，并提高了整体项目生产力。另一篇论文也探讨了使用 LLMs 生成规格说明。在[[53](https://arxiv.org/html/2408.02479v1#bib.bib53)]中，作者介绍了一个名为 SpecGen 的框架，用于生成程序规格说明。该框架主要使用 GPT-3.5-turbo 作为基础模型，并结合提示工程和多轮对话生成规格说明。SpecGen 应用了四种变异操作符来修改这些规格说明，并最终使用启发式选择策略来选择最佳变体。结果显示，SpecGen 能够生成 70%的程序规格说明，优于传统工具如 Houdini[[54](https://arxiv.org/html/2408.02479v1#bib.bib54)]和 Daikon¹¹1[`github.com/codespecs/daikon`](https://github.com/codespecs/daikon)。

此外，设计提示模式可以显著增强 LLM 在需求引导和系统设计等任务中的能力。论文提供了 13 种提示模式的目录，每种模式旨在解决软件开发中的特定挑战[[55](https://arxiv.org/html/2408.02479v1#bib.bib55)]。实验测试了这些模式在现实场景中的有效性，以验证它们的实用性。通过应用不同的提示模式，研究发现这些模式可以帮助生成更有结构和模块化的结果，并减少常见错误。自动化需求完整性提升是 LLM 在需求生成中带来的另一个重要好处。研究[[56](https://arxiv.org/html/2408.02479v1#bib.bib56)]使用 BERT 的掩蔽语言模型（MLM）可以检测并填补自然语言需求中的缺失部分，显著提高需求的完整性。BERT 的 MLM 达到了 82%的精确度，表明 82%的预测缺失项是正确的。

LLM 在歧义检测任务中的应用也很重要，旨在检测自然语言需求文档中的歧义，以提高清晰度和减少误解。本研究主要旨在解决相同应用领域内术语歧义的问题（同一术语在不同领域具有不同含义）。尽管当前模型通常具备出色的上下文理解能力，但这是当时机器学习中的一个常见问题。本研究提供了一个优秀的范例，用于后续 LLM 在需求工程中的应用，研究表明基于变换器的机器学习模型可以有效检测和识别需求文档中的歧义，从而增强文档的清晰度和一致性。该框架利用 BERT 和 K-means 聚类来识别在相同应用领域或跨学科项目需求文档中使用的不同上下文术语[[57](https://arxiv.org/html/2408.02479v1#bib.bib57)]。近年来，越来越多的研究者使用 LLM 帮助评估需求文档，质量评估任务确保生成的需求和代码达到预期的质量标准。ChatGPT 在用户故事质量评估中的应用显示了识别质量问题的潜力，但仍需进一步优化和改进[[58](https://arxiv.org/html/2408.02479v1#bib.bib58)]。类似的研究使用 LLM 自动处理需求满足度评估，并评估设计元素是否完全覆盖给定的需求，但研究者指出在实际应用中仍需进一步验证和优化[[59](https://arxiv.org/html/2408.02479v1#bib.bib59)]。

### IV-B 基于 LLM 的代理任务

目前，基于 LLM 的代理在需求工程中的应用仍然处于较为初期的阶段，但已有一些有用的研究帮助我们看到潜在的可能性。基于 LLM 的代理在需求获取、分类、生成和验证等任务中带来了效率和准确性的提升。与传统的 LLM 相比，这些系统通过任务分工和协作展现了更高水平的自动化和精确度。在半结构化文档生成中的多代理系统应用已经显示出显著的效果。在[[60](https://arxiv.org/html/2408.02479v1#bib.bib60)]中，介绍了一个多代理框架，该框架结合了语义识别、信息检索和内容生成任务，以简化公共行政领域半结构化文档的创建和管理。该框架涉及三种主要类型的代理：语义识别代理、信息检索代理和内容生成代理。通过避免单一模型的开销，每个代理被分配了一个特定的任务，并且用户干预最小，遵循设计的框架和工作流程。

此外，AI 辅助的软件开发框架（AISD）还展示了基于 LLM 的代理在需求工程中带来的自主性。[[61](https://arxiv.org/html/2408.02479v1#bib.bib61)] 提出了 AISD 框架，该框架通过持续的用户反馈和互动不断改进和优化生成的用例和代码。在实验过程中，人类需要首先给出一个模糊的需求定义，然后基于 LLM 的代理将根据这些信息改进需求案例，并设计模型并生成系统，然后生成的结果将让人类判断需求是否得到满足。研究结果表明，与没有人类参与的 24.1%相比，AISD 显著提高了用例通过率，达到了 75.2%。AISD 通过允许 LLM 在一个会话中生成所有代码文件，并根据用户反馈持续改进和修改，从而展示了代理的自主学习能力。这也确保了代码的依赖性和一致性，进一步证明了人类在需求分析和系统测试阶段的重要性。

此外，在为自动驾驶生成安全需求方面，基于 LLM 的代理通过引入多模态能力展现了独特的优势。该系统采用 LLM 作为自动化代理，生成和完善安全需求，直到验证阶段，几乎不需要人工干预，这一点是仅靠 LLM 无法实现的。[[62](https://arxiv.org/html/2408.02479v1#bib.bib62)] 描述了一个集成到现有的危害分析和风险评估（HARA）过程中的 LLM 原型，通过自动生成特定的安全相关需求，显著提高了效率。该研究通过三轮设计迭代，逐步提高了 LLM 原型的效率，从几个月减少到一天内完成。在敏捷软件开发中，用户故事的质量直接影响开发周期和客户期望的实现。[[63](https://arxiv.org/html/2408.02479v1#bib.bib63)] 展示了 ALAS 系统在奥地利邮政集团 IT 的六个敏捷团队中的成功应用。通过自动分析和改进，ALAS 系统显著提高了用户故事的清晰度、可理解性和与业务目标的一致性。整个代理框架允许模型在敏捷开发过程中执行特定角色，研究结果表明，ALAS 改进的用户故事获得了团队成员的高度满意。

### IV-C 分析

基于 LLM 的代理在需求工程中的应用已显示出显著的效率提升和质量保证。通过多代理协作和自动化处理，这些系统不仅减少了人工干预，还提高了需求生成和验证的准确性和一致性。我们可以看到，基于 LLM 的代理的任务已不再仅限于简单地生成需求或填补描述中的空白。相反，它们涉及实施自动化流程，生成需求文档只是其中的一部分，将 LLM 集成到代理中，增强了整体系统的自然语言处理和推理能力。在实际应用中，许多任务已经无法仅靠简单的 LLM 来完成，尤其是在高级软件设计方面。基于 LLM 的代理的出现通过以 LLM 为中心的多代理协作系统解决了这一问题，这些代理不断分析和完善需求文档中的不足，这可能是未来 LLM 基于需求工程的主要应用趋势。

![参见说明](img/757e3816d7dce252d7473d4d8bd61bf1.png)

图 4：LLM 基于代理与 LLM 在用户故事改进中的比较框架示意图

基于 LLM 的代理在需求工程中的应用仍然相对有限，大多数努力集中在利用多代理系统的协作优势来生成和完善需求工程文档。正如图中所示。[4](https://arxiv.org/html/2408.02479v1#S4.F4 "图 4 ‣ IV-C 分析 ‣ IV 需求工程和文档 ‣ 从 LLMs 到基于 LLM 的代理：当前挑战与未来的调查")，大致模拟了[[58](https://arxiv.org/html/2408.02479v1#bib.bib58)]和[[63](https://arxiv.org/html/2408.02479v1#bib.bib63)]中提出的架构，这些架构都应用于用户故事的生成和完善，我们可以清晰地比较这两种架构之间的差异。左侧是基于 LLM 的代理架构，而右侧则是单独使用提示工程和 LLMs 来完善用户故事的方法。该图省略了架构的更详细和复杂的方面，以突出这两种方法的核心差异。基于 LLM 的代理可以通过利用共享数据库从不同的专业角度不断改进。虽然关于基于 LLM 的代理的论文不多，但我们可以观察到从 LLMs 到基于 LLM 的代理的趋势和好处。

### IV-D 基准测试

需求工程不同于错误修复和代码生成等任务，没有大量公开的数据集可用，例如常用于代码生成评估的 HumanEval。需求工程中模型的训练数据集大多数是作者自收集的，并非所有数据集都在 Huggingface 上开源，导致需求工程中的数据集数量有限。例如，一些论文并没有提到具体的基准数据集，而是专注于实际案例和示例，以展示所提出的提示模式的有效性[[55](https://arxiv.org/html/2408.02479v1#bib.bib55)]。研究人员让实际的开发者和需求工程师使用生成的需求文档和代码来评估其准确性、可用性和完整性。用户反馈将被收集以进一步改进和优化提示模式。

在[[50](https://arxiv.org/html/2408.02479v1#bib.bib50)]中，主要使用了四个数据集，这些数据集以平均长度、类型-词汇比（TTR）和词汇密度（LD）为特征。NFR 多类分类数据集包括来自 PROMISE NFR 数据集的 15 个项目中 249 个非功能需求（NFRs）。应用评论 NFR 多标签分类数据集包含来自 Google Play 和 Apple App Store 的 1800 条应用评论，这些评论标记了各种 NFR。术语提取数据集包含 100 个智能家居用户故事以及 250 个手动提取的领域术语。最后，特征提取数据集由 50 个应用描述组成，涵盖 10 个应用类别，并手动识别了特征短语。在[[56](https://arxiv.org/html/2408.02479v1#bib.bib56)]中，PURE 数据集由 40 个需求规格组成，总计超过 23,000 个句子，用于测试 BERT 完成需求的能力。在[[64](https://arxiv.org/html/2408.02479v1#bib.bib64)]中，基准数据集包括对六个问题的 36 个回答：6 个由 ChatGPT 生成的回答和 30 个来自五位人类需求工程专家的回答（每位专家提供了 6 个回答）。这些数据集作为模型的评估指标。综合这些论文，我们可以看到，LLM 在需求工程中的基准数据集主要包括各种分类的软件需求以及功能性和非功能性需求，以帮助模型学习该领域，数据集的利用非常灵活且多样化。

在基于 LLM 的需求工程研究中，数据集的选择和构建也很重要。在[[47](https://arxiv.org/html/2408.02479v1#bib.bib47)]中，数据集主要由公共行政领域的语义模板组成。这些模板涵盖了各种半结构化的行政文档形式，如官方证书和公共服务表单。尽管数据集的详细组成没有具体说明，但可以推测这些模板包括大量实际案例和上下文信息，以确保多代理系统生成的文档满足实际需求。

此外，在[[61](https://arxiv.org/html/2408.02479v1#bib.bib61)]中，引入了 CAASD（自动软件开发能力评估）数据集。这个专门构建的基准数据集用于评估 AI 辅助软件开发系统的能力。CAASD 数据集包含来自各种领域的 72 个任务，例如小型游戏和个人网站，每个任务都有参考用例来定义系统需求。构建这个数据集的目的是提供一个覆盖不同类型开发任务的全面评估基准，以测试基于 LLM 的智能体在不同任务中的表现。在[[62](https://arxiv.org/html/2408.02479v1#bib.bib62)]中，该研究主要使用设计科学方法论来设计和评估 LLM 原型，但没有提及具体的数据集，重点在于通过实际应用和案例研究验证模型的有效性。尽管缺乏详细的数据集描述，但这种方法强调迭代改进和实际应用，以确保基于 LLM 的智能体生成的安全需求符合高安全标准。最后，在[[63](https://arxiv.org/html/2408.02479v1#bib.bib63)]中，使用了 25 个合成用户故事，这些故事来自一个移动交付应用项目。该研究通过在奥地利邮政集团 IT 的六个敏捷团队中测试 ALAS 系统的有效性。尽管这些用户故事是为实验设计的合成数据，但它们真实地反映了实际项目中的需求，提供了一个有价值的测试基准。

从这些论文中可以看出，基于 LLM 的智能体在需求工程中的数据集选择和构建通常依赖于实际项目和案例研究，缺乏标准化和大规模数据集。与 LLM 文献相比，所使用的数据集更广泛，处于更高的层级，如实际系统的文件，而不限于非功能需求的分类和纯软件需求规格。研究人员更多地关注通过实际应用和迭代改进来验证模型的有效性，以提高模型性能。虽然这种方法具有灵活性和针对性，但也突显了该领域在数据集标准化和规模化方面的不足。未来，随着更多公共数据集的建设和共享，基于 LLM 的智能体在需求工程中的应用预计将实现更广泛和更深入的发展。

表 V：需求工程和文档中的评估指标

{tblr}

row1 = c, cell24 = c, cell34 = c, cell44 = c, cell54 = c, cell64 = c, cell74 = c, cell84 = c, cell94 = c, cell104 = c, cell114 = c, cell124 = c, cell134 = c, cell144 = c, cell154 = c, cell164 = c, cell174 = c, cell184 = c, cell194 = c, hlines, vlines, 参考文献 & 基准评估指标 智能体

[[51](https://arxiv.org/html/2408.02479v1#bib.bib51)] 对 ActApp 的评估 提取的精确度和召回率

清晰度，一致性和合规性

验收的完整性和准确性

标准 无

[[50](https://arxiv.org/html/2408.02479v1#bib.bib50)] NFR，智能家居用户故事 精确度，召回率和 F\beta（F1 或 F2） 无

[[56](https://arxiv.org/html/2408.02479v1#bib.bib56)] PURE 精确度，F1 分数，召回率 无

[[52](https://arxiv.org/html/2408.02479v1#bib.bib52)] 未指定 Likert 量表 无

[[55](https://arxiv.org/html/2408.02479v1#bib.bib55)] 案例研究 准确识别缺失需求。

生成代码的质量和模块化。

重构建议的正确性。

自动化软件工程的效率

任务 无

[[64](https://arxiv.org/html/2408.02479v1#bib.bib64)] 对六个问题的 36 个回应 抽象性，原子性，一致性，正确性

清晰性，可理解性，可行性 无

[[48](https://arxiv.org/html/2408.02479v1#bib.bib48)] PROMISE NFR-Review，NFR-SO F1 分数，加权 F1 分数（w-F） 无

[[53](https://arxiv.org/html/2408.02479v1#bib.bib53)] SV-COMP，SpecGenBench 通过次数，成功概率

验证者调用次数，用户评分 无

[[65](https://arxiv.org/html/2408.02479v1#bib.bib65)] Jdoctor-data，DocTer-data，

SpecGenBench，SV-COMP 准确性，精确度，召回率，F1 分数 无

[[58](https://arxiv.org/html/2408.02479v1#bib.bib58)] 用户基准评估

使用 AQUSA 工具的故事 协议率，精确度，召回率，特异性，

F1 分数 无

[[57](https://arxiv.org/html/2408.02479v1#bib.bib57)] 从维基百科爬取的文档 手动验证 无

[[59](https://arxiv.org/html/2408.02479v1#bib.bib59)] CM1，CCHIT，Dronology，PTC-A，

PTC-B F\beta 分数，均值平均精确度（MAP） 无

[[49](https://arxiv.org/html/2408.02479v1#bib.bib49)]] PROMISE NFR 精确度（P），召回率（R），F1 分数（F1），

加权平均 F1 分数（A） 无

[[66](https://arxiv.org/html/2408.02479v1#bib.bib66)] CS 特定语料库，PURE 上下文清晰度，用户反馈 无

[[60](https://arxiv.org/html/2408.02479v1#bib.bib60)] 来自公开的语义模板

管理 精确度，及时符合度，用户干预

频率，幻觉率 是

[[61](https://arxiv.org/html/2408.02479v1#bib.bib61)] CAASD 通过率，令牌消耗 是

[[62](https://arxiv.org/html/2408.02479v1#bib.bib62)] AEB，CAEM 性能准确性和相关性，效率，

来自行业的反馈 是

[[63](https://arxiv.org/html/2408.02479v1#bib.bib63)] 25 个合成用户故事

移动交付应用程序 独立性，谈判性，价值，可估计性，

小规模，可测试性。

对专业人士的调查 是

### IV-E 评估指标

在需求工程领域，LLMs 和基于 LLM 的代理使用各种指标进行评估。这些指标不仅包括传统的精准度、召回率和 F1 分数，还包括针对需求工程独特性质的更具体的指标。通过这些评估，我们可以了解这些模型是如何被评估的以及它们如何改变需求工程的实践。具体的评估指标详见表 [V](https://arxiv.org/html/2408.02479v1#S4.T5 "TABLE V ‣ IV-D Benchmarks ‣ IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")。在 [[51](https://arxiv.org/html/2408.02479v1#bib.bib51)] 中，虽然精准度和召回率是评估信息检索效果的基础，但还包括了清晰度、一致性和合规性等额外评估，这些都是需求工程中的关键质量指标。这种多维评估方法不仅衡量了 LLMs 的操作性能，还考察了它们保持需求规格质量的能力。通过这种方法，LLMs 显示了其在自动化和优化需求获取过程中的价值，提高了效率和结果的可靠性。论文 [[52](https://arxiv.org/html/2408.02479v1#bib.bib52)] 使用李克特量表来衡量生成规格的质量，规格将根据其明确性、可理解性、简洁性等进行评分。李克特量表的评分范围从 1 到 5。

对于基于代理的 LLMs，如 [[63](https://arxiv.org/html/2408.02479v1#bib.bib63)] 中所示，评估扩展到评估代理的独立性和可协商性，将其功能提升到一个新的水平。这些代理提供技术解决方案，并且与用户互动，自主调整以满足特定项目需求，从而类似于协作伙伴。这种能力使得基于 LLM 的代理在需求工程中的需求管理和决策优化中具有价值，也突显了 LLMs 通常专注于提高特定任务的准确性和效率，而基于 LLM 的代理在自主性和适应性方面表现出更高的能力。

在表格 [V](https://arxiv.org/html/2408.02479v1#S4.T5 "TABLE V ‣ IV-D Benchmarks ‣ IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")中，我们可以看到，在需求工程中，LLMs 的应用通常需要使用诸如 F1 Score 等常见指标来评估模型的性能。然而，对于基于 LLM 的代理，评估重点从需求文档生成的性能转移到了最终产品的质量。因此，评估指标更加注重用户满意度，如通过率、反馈等。本质上，基于 LLM 的代理仍然利用 LLM 本身来实现更高级别的发展，并且很大程度上依赖于任务的性质。总之，我们可以得出结论，代理模型的特性既反映了它们复杂的决策和学习能力，也揭示了它们在与人类或其他工具协作时提供更高可扩展性和灵活性设计的潜在优势。这一现象暗示了未来软件开发中需求引导和处理的方法有可能变得更加高效、精确，并且通过使用基于 LLM 的代理不断优化，以更好地满足利益相关者的需求。

## V 代码生成与软件开发

代码生成与软件开发是软件工程中的核心领域，它在软件开发过程中发挥着至关重要的作用。使用 LLMs 进行代码生成的主要目的是通过自动化流程提高开发效率和代码质量，从而满足开发者和用户的需求。

近年来，LLMs 在代码生成和软件开发中的应用取得了显著进展，这改变了开发人员的工作方式，并揭示了自动化开发过程的变化。与需求工程相比，LLMs 和基于 LLM 的代理在代码生成和软件开发中的应用研究更为广泛和深入。利用自然语言处理和生成技术，LLMs 可以理解和生成复杂的代码片段，协助开发人员自动化从代码编写和调试到软件优化的各个阶段。基于解码器的大型语言模型，如 GPT-4，在通过提供准确的代码建议和自动化调试方面显示了显著的潜力，大大提高了开发效率。最近，基于 LLM 的代理在软件开发中的应用也引起了关注，这些智能代理不仅可以执行复杂的代码生成任务，还可以进行自主学习和持续优化，从而在动态开发环境中提供灵活的支持。集成 LLMs 的工具，如 GitHub Copilot [[12](https://arxiv.org/html/2408.02479v1#bib.bib12)]，已经展示了在提高编程效率和代码质量方面的优势。

### V-A LLMs 任务

大型语言模型通过自动化和推理优化了代码生成和软件开发中的各种任务，涵盖了代码生成、调试、代码理解、代码补全、代码转换以及多轮互动代码生成等领域。主要方法是从自然语言描述中生成可执行代码，模型利用先前学习的代码片段或应用少量学习来更好地理解用户需求。如今，AI 工具与像 Visual Studio Code²²2[`code.visualstudio.com/`](https://code.visualstudio.com/) 和 JetBrains³³3[`www.jetbrains.com/`](https://www.jetbrains.com/) 等 IDE 深度集成，以增强代码编写和翻译任务，如 OpenAI 的 Codex 模型 [[67](https://arxiv.org/html/2408.02479v1#bib.bib67)]。Codex 在 GitHub 上的公开代码上进行微调，展示了从文档字符串生成 Python 函数的能力，并在 HumanEval 基准测试中超越了其他类似模型。

在[[68](https://arxiv.org/html/2408.02479v1#bib.bib68)]中，研究人员全面评估了多种 LLM 在 L2C（语言到代码）任务上的表现。结果表明，GPT-4 在语义解析、数学推理和 Python 编程等任务中表现出色。通过指令调优和大规模训练数据的支持，该模型能够理解和生成符合用户意图的代码，实现高精度的代码生成。将 LLMs 应用于文本到数据库管理和查询优化也是自然语言到代码生成任务中的一个新研究方向。通过将自然语言查询转换为 SQL 语句，LLMs 帮助开发者快速生成高效的数据库查询代码。在[[69](https://arxiv.org/html/2408.02479v1#bib.bib69)]中，提出了 SQL-PaLM 框架，通过少量示例提示和指令微调显著提高了文本到 SQL 任务的执行准确性和精确匹配率，为复杂的跨领域 SQL 生成任务提供了有效解决方案。SQL-PaLM 模型在准确性和精确匹配上的改进被认为是测试基准中的最先进（SOTA），SQL-PaLM 在测试中表现出色，与现有方法如 T5-3B + PICARD、RASAT + PICARD 甚至 GPT-4 相比，达到了 77.3%的最高测试准确率和 82.7%的执行准确率。多语言代码生成是 LLMs 的另一个重要应用，特别适合变压器架构。在[[70](https://arxiv.org/html/2408.02479v1#bib.bib70)]中，研究人员介绍了 CodeGeeX 模型，该模型在多种编程语言上进行了预训练，并在多语言代码生成和翻译任务中表现优异。实验结果表明，CodeGeeX 在 HumanEval-X 基准测试中优于其他多语言模型。

尽管当前的 LLMs 具备出色的代码生成能力，准确性和编译率达到了可用水平，但生成代码的质量通常依赖于用户的提示。如果提示过于模糊或一般，LLM 通常难以理解用户的真实需求，从而使得在一次尝试中生成所需代码变得困难。在[[71](https://arxiv.org/html/2408.02479v1#bib.bib71)]中，研究人员引入了“打印调试”技术，使用 GPT-4 跟踪变量值和执行流程，通过使用上下文学习技术提高效率和准确性。与橡皮鸭调试方法相比，这种方法特别适用于 Leetcode 中的中等难度问题，在简单 Leetcode 问题上提高了 1.5%的性能，在中等难度问题上提高了 17.9%的性能。

此外，LLM 在提高编程效率方面的应用也引起了广泛关注。像 GitHub Copilot 这样的工具集成了 OpenAI 的 Codex 模型，提供实时代码补全和建议。根据[[72](https://arxiv.org/html/2408.02479v1#bib.bib72)]，研究人员进行了一项受控实验，结果表明使用 Copilot 时，开发人员完成 HTTP 服务器任务的速度提高了 55.8%。另一项类似的研究也使用 LLM 作为编程工具。在[[73](https://arxiv.org/html/2408.02479v1#bib.bib73)]中，研究人员引入了 INCODER 模型，该模型既能进行程序合成，也能进行编辑。通过利用双向上下文，该模型在单行和多行代码填充任务中表现出色，为开发人员提供了更智能的代码编辑工具。这种实时代码生成和补全功能不仅提高了编程效率，还减少了开发人员的负担，使他们能够专注于更高层次的设计，这在软件开发中是一个常见问题，即大量的劳动力和时间浪费在繁琐的编码任务上。

多轮程序合成任务代表了 LLM 在处理复杂编程任务方面的重大突破。在[[74](https://arxiv.org/html/2408.02479v1#bib.bib74)]中，研究人员引入了 CODEGEN 模型，该模型通过多次交互迭代生成程序，显著提高了程序合成质量，使开发过程更加高效和准确。通过逐步生成并不断优化代码，LLM 可以更好地理解用户意图，生成更精确和优化的代码。在实验中，与当时被认为是最先进的代码生成模型 Codex 进行了比较。CODEGEN-MONO 2.7B 在 k=1 和 k=10 的 pass@k 指标上优于相同结果的 Codex 模型。此外，CODEGEN-MONO 16.1B 在某些指标上的表现与最佳 Codex 模型相当或更好，进一步证明了其在代码生成中的 SOTA 性能。通过迭代生成和优化代码，LLM 不断提升其输出质量。在[[75](https://arxiv.org/html/2408.02479v1#bib.bib75)]中，研究人员提出了 Cycle 框架，该框架通过从执行反馈中学习来增强代码语言模型的自我改进能力，在多个基准数据集上将代码生成性能提高了 63.5%。尽管 Cycle 具有一定程度的自主性，但其决策和规划能力主要限于代码生成和改进任务，没有整体规划，执行顺序完全遵循固定模式，因此更适合被归类为高级 LLM 应用。

### V-B 基于 LLM 的代理任务

基于 LLM 的智能体通过多智能体协作显著提高了任务效率和效果，展示了巨大的潜力和优势。与传统 LLM 不同，基于 LLM 的智能体采用了分工合作的方法，将复杂任务分解为多个由专业智能体处理的子任务，这种方法可以提高任务效率，改善生成代码的质量和准确性，从而减轻单一 LLM 的幻觉问题。

在[[76](https://arxiv.org/html/2408.02479v1#bib.bib76)]中，研究人员提出了一个自我协作框架，其中多个 ChatGPT（GPT-3.5-turbo）智能体扮演不同的角色，共同处理复杂的代码生成任务。具体来说，引入软件开发方法论（SDM）将开发过程分为分析、编码和测试三个阶段。每个阶段由特定角色管理，完成任务后，各角色提供反馈并与其他角色协作，以提高生成代码的质量。实验表明，这一自我协作框架在 HumanEval 和 MBPP 基准测试中显著提高了性能，其中 HumanEval 的最高提升达 29.9%，相比于 SOTA 模型 GPT-4。这个结果展示了协作团队在复杂代码生成任务中的潜力。虽然该框架缺乏外部工具集成和动态调整能力，但它展示了基于 LLM 的智能体的共同特征，如角色分配、自我改进能力和优秀的自主决策能力，这些综合能力使其有资格被视为基于 LLM 的智能体。类似地，在[[77](https://arxiv.org/html/2408.02479v1#bib.bib77)]中，LCG 框架也通过多智能体协作和链式思维技术提高了代码生成质量，再次展示了多智能体协作在软件开发过程中的有效性。

上下文窗口的局限性在以前的研究中未被讨论，这在剑桥大学团队 2024 年的研究中得到了深入探讨。在[[78](https://arxiv.org/html/2408.02479v1#bib.bib78)]中，研究人员介绍了 L2MAC 框架，该框架通过多智能体系统动态管理内存和执行上下文，以生成大型代码库，并在系统设计任务的代码生成中取得了 SOTA 性能。该框架主要分为以下几个组件：处理器，负责实际生成任务输出；指令注册表，存储解决用户任务的程序提示；以及文件存储，包含最终和中间输出。控制单元定期检查输出，确保生成的内容在语法和功能上都是正确的。研究人员进行了多次实验，并与 GPT-4、Reflexion 和 AutoGPT 等多种新方法进行了比较，在 HumanEval 基准上取得了 90.2%的 Pass@1 分数，展示了其在生成大规模代码库中的卓越性能。

最近，许多研究开始使用基于 LLM 的智能体来模拟真实的软件开发过程，论文 [[79](https://arxiv.org/html/2408.02479v1#bib.bib79)] 介绍了 MetaGPT 框架，该框架通过在多智能体协作中编码的标准操作程序（SOPs）增强了问题解决能力。多协作框架的整个过程模拟了软件开发的瀑布生命周期，每个智能体扮演不同角色并协作以实现自动化软件开发的目标。基于 LLM 的智能体在自动化软件开发中也表现出强大的能力，[[80](https://arxiv.org/html/2408.02479v1#bib.bib80)] 提出了一个多 GPT 智能体框架，该框架自动化了项目规划、需求工程、软件设计和调试等任务，展示了自动化软件开发的潜力。同样，[[81](https://arxiv.org/html/2408.02479v1#bib.bib81)] 介绍了一种名为 CodePori 的模型，该模型是一个新型模型，旨在基于自然语言提示自动生成大规模和复杂的软件项目代码。在[[82](https://arxiv.org/html/2408.02479v1#bib.bib82)]中，AgentCoder 框架与程序员智能体、测试设计智能体和测试执行智能体协作生成和优化代码，超越了现有方法，在 HumanEval-ET 基准上取得了 77.4%的 Pass@1，相较于之前 69.5%的最先进结果，展示了多智能体系统在代码生成和测试中的优势。

将 LLMs 集成到来自多个框架的代理中的目的是增强整个代理系统的自我反馈和反思能力。由于当前的开源 LLM 在这方面的能力通常远低于专有模型，基于 LLM 的代理的出现可以帮助弥合开源模型与像 GPT-4 这样的专有系统的高级能力之间的差距。[[83](https://arxiv.org/html/2408.02479v1#bib.bib83)] 引入了 OpenCodeInterpreter 框架，该框架通过集成代码生成、执行和人工反馈来提高代码生成模型的准确性。基于 CodeLlama 和 DeepSeekCoder，该框架在 HumanEval 和 MBPP 基准测试中表现接近 GPT-4 代码解释器。使用外部工具或 API 的能力是基于 LLM 的代理的另一个显著优势，[[84](https://arxiv.org/html/2408.02479v1#bib.bib84)] 提出了 Toolformer 模型，该模型通过自我监督学习调用 API，显著提高了任务性能。基于 GPT-J（6.7B 参数）的框架在多个基准任务中取得了显著的性能提升，展示了外部工具所带来的 LLM-based 代理的可能性，工具和架构的多样性使得 LLM 能够持续学习新知识并自我改进。类似地，[[85](https://arxiv.org/html/2408.02479v1#bib.bib85)] 通过 ToolLLM 框架增强了 LLM 与外部 API 的互动，在 ToolBench 和 APIBench 基准测试中超越了 Text-Davinci-003 和 Claude-2，在多工具指令处理方面表现出色。

### V-C 分析

LLM-based 代理与传统 LLM 在软件开发应用中的主要区别主要集中在效率和自主性，特别是在任务分配和协作方面。传统 LLM 通常使用单一模型处理特定任务，如从文本生成代码和代码补全。然而，这种方法在处理复杂任务时存在局限性，特别是涉及上下文窗口限制和对持续反馈的需求。LLM-based 代理通过清晰的劳动分工进行不同的子任务，从而提高任务效率和质量。例如，在代码生成任务中，一个代理生成初始代码，另一个设计测试用例，第三个执行测试并提供反馈，从而实现迭代优化。通过任务分工、多代理系统和工具集成，LLM-based 代理可以处理更复杂、更广泛的任务，提高代码生成的质量和效率。这种方法克服了传统 LLM 的局限性，也为未来的软件开发研究和应用提供了新的方向和思路，解放了程序员免于枯燥的测试套件生成。

![参见说明](img/db72cb549f6968605aaf630f0d765c36.png)

图 5：LLM 基础的代理与 LLM 在代码生成和软件开发中的比较框架示意图

在软件工程任务处理方面，LLMs 和 LLM 基础的代理在任务重点、方法、复杂性、可扩展性、自动化水平和任务管理等方面存在微妙的差异。LLMs 主要关注提升单个 LLM 的代码生成能力，包括调试、精度、评估。这些方法通常通过单一模型改善代码生成或评估的特定方面，集中于在现有限制条件下的性能提升，例如上下文窗口和单任务执行。相比之下，LLM 基础的代理强调通过多个专业化 LLM 或框架的协作来处理更复杂和广泛的任务，整合工具使用、迭代测试和多代理协调，以优化整个开发过程，并轻松超越常规基准测试中的最先进模型。多代理系统的出现也带来了更多的可能性，这种系统可以模拟真实的软件开发人员进行 Scrum 开发。图[5](https://arxiv.org/html/2408.02479v1#S5.F5 "Figure 5 ‣ V-C Analysis ‣ V Code Generation and Software Development ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")利用研究[[77](https://arxiv.org/html/2408.02479v1#bib.bib77)]和[[75](https://arxiv.org/html/2408.02479v1#bib.bib75)]展示了 LLM 基础的代理和 LLMs 在相同代码生成任务上的差异。LLM 基础的代理系统能够进行多代理协作，并模拟行业中的真实 Scrum 开发团队。相比之下，右侧的 LLMs 通常使用多个 LLMs 来分析测试案例中的错误，并完善初始生成的代码，但由于测试案例是由人工生成的，它们缺乏自主性和效率。

### V-D 基准测试

在代码生成和软件开发领域，LLM 和基于 LLM 的代理研究中使用的数据集存在显著的差异和共性。这些数据集为评估模型性能提供了重要的基准，例如**HumanEval**数据集，广泛用于评估代码生成模型，由 OpenAI 手工制作，包含 164 个编程问题，每个问题包括一个函数签名、问题描述、函数体和单元测试。该数据集主要用于评估模型生成正确代码的能力，特别是在将自然语言描述转换为可执行代码的任务中。许多研究利用 HumanEval 测试代码生成模型的性能[[76](https://arxiv.org/html/2408.02479v1#bib.bib76)]。**MBPP**（Mostly Basic Python Programming）数据集是另一个常用的基准，包含 427 个 Python 编程问题，覆盖基本概念和标准库函数，该数据集用于评估模型在各种编程场景中的性能。在[[82](https://arxiv.org/html/2408.02479v1#bib.bib82)]中，研究人员使用 MBPP 数据集测试多代理系统在代码生成和优化中的性能，通过代理协作提高生成代码的准确性和鲁棒性。**HumanEval-ET**和**MBPP-ET**数据集是原始 HumanEval 和 MBPP 数据集的扩展，增加了更多的测试用例和更复杂的问题，以全面评估模型性能[[86](https://arxiv.org/html/2408.02479v1#bib.bib86)]。**Spider**和**BIRD**数据集专注于将自然语言转换为 SQL 查询，评估模型处理复杂查询生成任务的能力。在[[69](https://arxiv.org/html/2408.02479v1#bib.bib69)]中，研究人员使用这些数据集测试 SQL-PaLM 框架，通过少量示例提示和指令微调评估 SQL 生成任务的执行准确性和完全匹配率。**ToolBench**和**APIBench**数据集用于评估模型使用工具和 API 的能力，ToolBench 包含 16,464 条真实世界的 RESTful API 指令，APIBench 通常测试模型对未见过的 API 指令的泛化能力[[85](https://arxiv.org/html/2408.02479v1#bib.bib85)]。**CAASD**（Capability Assessment of Automatic Software Development）数据集是一个新开发的基准，包含来自各种领域的 72 个软件开发任务，每个任务都有一组参考用例，用于评估 AI 辅助的软件开发系统[[61](https://arxiv.org/html/2408.02479v1#bib.bib61)]。

在选择用于大型语言模型（LLMs）和基于 LLM 的智能体的数据集时，有一些明显的共同点，HumanEval 和 MBPP 数据集被广泛用于评估代码生成能力，涵盖了各种编程任务和语言。此外，许多研究还采用了多语言和跨领域的数据集，如 HumanEval-X 和 CodeSearchNet，以评估模型在不同语言和任务中的表现。至于差异，基于 LLM 的智能体倾向于使用多智能体协作框架来处理复杂任务，因此更倾向于使用强调多轮交互和迭代优化的基准数据集，同时关注工具使用和 API 集成能力。TOOLLLM 框架使用 ToolBench 和 APIBench 来评估其工具使用能力，而 Toolformer 则展示了其自主学习使用工具的能力。这些差异主要来源于 LLMs 和基于 LLM 的智能体在任务处理上的不同方法，LLMs 通常通过在相关数据集上进行微调来优化单个模型的性能。

### V-E 评估指标

各种评估指标用于评估 LLMs 和基于 LLM 的智能体在代码生成和软件开发中的表现。这些指标衡量模型在特定任务中的表现以及它们如何改进代码生成和软件开发过程。表[VI](https://arxiv.org/html/2408.02479v1#S5.T6 "TABLE VI ‣ V-E Evaluation Metrics ‣ V Code Generation and Software Development ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")包括了本文引用的评估指标的分布，涵盖了 LLMs 和基于 LLM 的智能体。

在关于 LLMs 和基于 LLM 的智能体的研究中，**Pass@k**是一个常见的评估指标，用于衡量生成代码在前 k 次尝试中通过所有测试用例的比例，这个指标广泛应用于各种数据集。在[[86](https://arxiv.org/html/2408.02479v1#bib.bib86)]中，**Pass@k**被用来评估多轮交互中的代码生成质量，结果显示，通过引入规划阶段，模型的**Pass@k**显著提高。除了**Pass@k**，**BLEU 分数**是另一个常见的评估指标，主要用于测量生成代码与参考代码之间的句法相似性和正确性。在[[73](https://arxiv.org/html/2408.02479v1#bib.bib73)]中，**BLEU 分数**被用来评估生成代码的质量。**完成时间**和**成功率**是其他重要的评估指标，特别是在评估 AI 辅助开发工具的生产力影响时，这些指标至关重要，因为我们期望 LLMs 在保持预期速度的同时生成准确的代码。**置信度校准**和**执行成功率**是用于评估模型生成代码时的置信度水平和执行成功率的指标。研究人员通常使用这些指标来评估不同 LLMs 在理解用户意图和生成高精度正确代码方面的表现。

相较于软件开发中对大语言模型（LLMs）的评估指标，基于 LLM 的智能体也使用**Pass@k**，但采用更多样化的指标以反映其多智能体协作的特点。**胜率**和**一致率**是评估多智能体协作有效性的关键指标。此外，基于 LLM 的智能体通常还使用**执行效果**和**成本效率**等指标来评估其在实际应用中的表现。例如，在 MetaGPT [[79](https://arxiv.org/html/2408.02479v1#bib.bib79)]中，研究人员不仅评估了代码生成的正确性，还分析了执行效果、开发成本和生产力。结果表明，MetaGPT 显著提高了开发效率，降低了开发成本，同时生成了高质量的代码。总体而言，这些智能体都使用传统指标如**Pass@k**、**胜率**和任务完成时间来评估其代码生成能力，这些指标直接反映了模型生成代码的准确性和效率。但基于 LLM 的智能体通常需要更全面和多样化的指标来评估，以帮助评估多个智能体和整个开发过程的表现，这也是为什么我们可以看到**人工修订成本**、**定性反馈**等评估指标。研究人员考虑用户或开发者满意度指标，因为智能体应用通常涉及大规模项目而不是孤立的小规模开发，这些指标关注代码生成的正确性以及智能体系统的资源利用效率。

表 VI：代码生成和软件开发中的评估指标

{tblr}

column4 = c, cell11 = c, cell13 = c, cell12 = c, hlines, vlines, 参考论文与基准评估指标代理

[[71](https://arxiv.org/html/2408.02479v1#bib.bib71)] Leetcode 问题 准确率 否

[[72](https://arxiv.org/html/2408.02479v1#bib.bib72)] JavaScript 中的 HTTP 服务器由

95 程序员 任务完成时间，

任务成功 否

[[68](https://arxiv.org/html/2408.02479v1#bib.bib68)] Spider, WikiTQ, GSM8k,

SVAMP, MBPP, MBPP, DS-1000 执行准确率，

置信度校准

执行率 否

[[45](https://arxiv.org/html/2408.02479v1#bib.bib45)] Alpaca 数据 胜率, 一致性

评分 否

[[86](https://arxiv.org/html/2408.02479v1#bib.bib86)] HumanEval/-X/-ET,

MBPP-sanitized/-ET Pass@k, 平均通过率，

CodeBLEU 否

[[73](https://arxiv.org/html/2408.02479v1#bib.bib73)] HumanEval, CodeXGLUE 通过率, 完全匹配

BLEU 评分 否

[[69](https://arxiv.org/html/2408.02479v1#bib.bib69)] Spider 准确率，

完全匹配 否

[[74](https://arxiv.org/html/2408.02479v1#bib.bib74)] HumanEval, MTPB Pass@k, 通过率 否

[[30](https://arxiv.org/html/2408.02479v1#bib.bib30)] HumanEval, MathQA-Python,

GSM8K-Python, CodeSearchNet,

CosQA, AdvTest Pass@k, BLEU-4,

完全匹配 a

编辑相似度，

平均倒数排名（MRR） 否

[[70](https://arxiv.org/html/2408.02479v1#bib.bib70)] HumanEval/-X Pass@k 否

[[67](https://arxiv.org/html/2408.02479v1#bib.bib67)] HumanEval Pass@k, BLEU 评分 否

[[75](https://arxiv.org/html/2408.02479v1#bib.bib75)] HumanEval, MBPP-S, APPS 通过率, 令牌编辑距离，

完全复制率 否

[[76](https://arxiv.org/html/2408.02479v1#bib.bib76)] MBPP/-ET, HumanEval/-ET Pass@k 是

[[78](https://arxiv.org/html/2408.02479v1#bib.bib78)] HumanEval Pass@1 是

[[87](https://arxiv.org/html/2408.02479v1#bib.bib87)] CAASD 通过率, 令牌消耗 是

[[84](https://arxiv.org/html/2408.02479v1#bib.bib84)] CCNet, SQuAD, Google-RE, T-REx,

ASDiv, SVAMP, MAWPS,

Web Questions, Natural Questions,

TriviaQA, MLQA, TEMPLAMA 零样本性能，

困惑度, 工具使用效果 是

[[82](https://arxiv.org/html/2408.02479v1#bib.bib82)] MBPP/-ET, HumanEval/-ET Pass@1 是

[[79](https://arxiv.org/html/2408.02479v1#bib.bib79)] HumanEval, HumanEval,

SoftwareDev Pass@k, 可执行性, 成本,

代码统计, 生产力，

人工修订成本 是

[[81](https://arxiv.org/html/2408.02479v1#bib.bib81)] HumanEval, MBPP Pass@k, 从业者基础

评估 是

[[85](https://arxiv.org/html/2408.02479v1#bib.bib85)] ToolBench, APIBench 通过率, 胜率 是

[[80](https://arxiv.org/html/2408.02479v1#bib.bib80)] 无特定通过率, 胜率 是

[[77](https://arxiv.org/html/2408.02479v1#bib.bib77)] MBPP/-ET, HumanEval/-ET Pass@1 是

[[83](https://arxiv.org/html/2408.02479v1#bib.bib83)] HumanEval, MBPP, EvalPlus Pass@1 是

[[88](https://arxiv.org/html/2408.02479v1#bib.bib88)] 来自 Meta 的第一方数据

代码库和笔记本 接受率，P

输入代码的百分比，

质量反馈 是

## VI 自主学习与决策制定

自主学习与决策制定是现代软件工程中一个关键且不断发展的领域，尤其是在人工智能和大数据的影响下。自主学习与决策制定的核心任务是通过机器学习算法和智能系统实现自动化数据分析、模型构建和决策优化，从而提高系统的自主性和智能性。

在这个过程中，LLM 和基于 LLM 的代理带来了许多可能性，随着 NLP 技术的发展，LLM 在该领域的应用取得了很多成果。这些模型能够处理复杂的语言任务，还展现了强大的推理和决策能力，关于使用多个 LLM 调用的投票推理的研究揭示了优化性能的新方法，其中最常用的方法称为多数投票[[89](https://arxiv.org/html/2408.02479v1#bib.bib89)]，这提高了推理系统的准确性，并确保选择最佳可能性。此外，LLM 在自动调试和自我修正等任务中的表现提升了系统的自主学习能力，实现了高效的错误识别和修正。同时，基于 LLM 的代理在自主学习和决策制定中的应用也是一个新兴但受欢迎的话题，这些代理可以借助 LLM 执行复杂的推理和决策任务，并通过持续学习和优化提高其在动态环境中的适应性。在此背景下，我们收集了十九篇关于 LLM 基于代理的研究论文。这项调查将对这些研究进行总体回顾，分析自主学习和决策制定中的具体应用和技术实现。

### VI-A LLM 任务

对于 LLM 的 API 调用是一种常见的应用，通常需要持续调用以使模型能够进行判断和推理，但持续增加调用次数是否总能提高性能？在[[90](https://arxiv.org/html/2408.02479v1#bib.bib90)]中，研究人员探讨了增加 LLM 调用对复合推理系统性能的影响。论文分析了投票推理设计系统，结果显示 LLM 调用次数与系统性能之间存在非线性关系；性能最初随着调用次数增加而提高，但在达到某个阈值后会下降。这项研究为优化 LLM 调用提供了理论基础，有助于在实际应用中合理配置资源以实现最佳性能。然而，由于查询难度的多样性，投票推理系统的性能表现出非单调趋势，同时持续增加的成本也需要考虑。

自主学习也应用于错误修复领域，研究人员希望大语言模型（LLMs）能够持续学习修复错误，并最终识别出人为的疏忽或常见错误。在[[91](https://arxiv.org/html/2408.02479v1#bib.bib91)]中，提出了**SELF-DEBUGGING**方法，使 LLMs 能够通过分析执行结果和自然语言解释来调试代码。这一方法显著提高了代码生成任务的准确性和样本效率，特别是对于复杂问题。对 Spider 和 TransCoder 基准测试的实验结果显示，**SELF-DEBUGGING**方法使模型的准确性提高了 2-12%，这展示了 LLMs 在自主学习中调试和纠正任何错误的潜力。另一项类似的研究介绍了**AutoSD**（自动化科学调试）技术[[92](https://arxiv.org/html/2408.02479v1#bib.bib92)]，该技术通过 LLMs 模拟科学调试过程，生成可解释的修补代码。研究人员从可行性、调试器剖析、语言模型变化、开发者收益、开发者接受度和定性分析六个方面评估了**AutoSD**的能力。结果表明，**AutoSD**能够生成有效的补丁，并通过提供解释来提高开发者在评估修补代码时的准确性，其解释功能使得开发者更容易理解和接受自动生成的补丁。尽管上述两项研究主要关注自动化调试技术，但这些研究中设计的框架在收集足够信息后能够自动确定最佳修复方案，并提供具体的代码实现，展示了自主决策和学习的能力。

自从 LLM 在各个领域的应用兴起以来，一个研究方向是对其创造力的理性分析以及探索其持续学习的潜力，这种创造力也高度取决于模型的决策能力。[[93](https://arxiv.org/html/2408.02479v1#bib.bib93)] 从创造力理论的角度分析了 LLM 的输出，探讨了其生成创造性内容的能力，研究使用了价值、新颖性和惊奇等指标，发现当前的 LLM 在生成组合性、探索性和变革性创造力方面存在局限性。尽管 LLM 可以生成高质量的创造性内容，但仍需进一步研究和改进，以实现真正的创造性突破。此外，LLM 生成的创新响应可能伴随有幻觉的可能性，这是大型语言模型长期存在的问题。尽管有许多技术可以减轻其负面影响，但仍无法完全避免。在决策制定中有许多有趣的实验，例如让 LLM 充当法官，以确定一个人是否犯了罪 [[94](https://arxiv.org/html/2408.02479v1#bib.bib94)]。一个熟悉的尝试是让一个主要 LLM 与其他 LLM 进行互动。[[95](https://arxiv.org/html/2408.02479v1#bib.bib95)] 探讨了使用 LLM 作为法官评估其他 LLM 驱动的聊天助手的有效性。研究通过 MT-Bench 和 Chatbot Arena 基准测试验证了 LLM 判断与人类偏好的相符程度，结果显示 GPT-4 的判断在各种任务中与人类判断高度一致。这项研究展示了 LLM 在模拟人类评估方面的潜力，为自动化评估和优化提供了新思路。

### VI-B 基于 LLM 的代理任务

多智能体协作和对话框架也展示了在决策制定和自主学习方面的强大能力。[[96](https://arxiv.org/html/2408.02479v1#bib.bib96)] 探讨了多智能体讨论是否可以增强大型语言模型（LLMs）的推理能力。提出的 CMD 框架模拟了人类群体讨论过程，显示出多智能体讨论可以在没有特定任务示例的情况下改善常识知识和数学推理任务的表现。此外，研究发现多智能体讨论还可以纠正单一智能体中的常见错误，如判断错误和不正确答案的传播，从而提高整体推理准确性。[[97](https://arxiv.org/html/2408.02479v1#bib.bib97)] 研究人员探讨了像 GPT4-Vision 这样的多模态大型语言模型（MLLMs）在增强智能体自主决策过程中的潜力。论文介绍了 PCA-EVAL 基准，并评估了多模态决策能力在自动驾驶、家庭助手和游戏等领域的表现。结果显示，GPT4-Vision 在感知、认知和行动等维度上展现了卓越的性能。

[[98](https://arxiv.org/html/2408.02479v1#bib.bib98)] 提出了 Reflexion 框架，这是一种通过语言反馈而非传统的权重更新来强化学习的新方法，以避免昂贵的重新训练成本。该框架使用自我反思和语言反馈来帮助语言智能体从错误中学习，显著提高了在决策制定、推理和编程任务中的表现。Reflexion 在 HumanEval Python 编程任务上的首次成功率从 80.1%提高到 91.0%，在 ALFWorld 决策任务中的成功率提高了 22%，在 HotPotQA 推理任务中的表现提高了 14%。这些结果表明，Reflexion 框架通过自我反思和语言反馈在各种任务中展示了最先进的性能。

另一个代理框架[[35](https://arxiv.org/html/2408.02479v1#bib.bib35)] 引入了 ExpeL 代理框架，该框架通过自主收集经验和从一系列训练任务中提取知识来增强决策能力，这一经验收集过程类似于人类通过实践获得见解并将其应用于考试。通过访问内部数据库，ExpeL 还减少了幻觉，采用了在[III](https://arxiv.org/html/2408.02479v1#S3 "III Preliminaries ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")中讨论的 RAG 技术。ExpeL 框架不需要参数更新，它通过回忆过去的成功与失败来提升决策能力，充分发挥了 ReAct 框架[[36](https://arxiv.org/html/2408.02479v1#bib.bib36)]的优势。实验显示，ExpeL 能够在多个领域的任务中持续改进，并展示了跨任务转移学习的能力。ExpeL 与 Reflexion 的结合进一步提升了迭代任务尝试中的表现，突显了自主学习和经验积累在开发智能代理中的重要性。ExpeL 框架在几个方面表现出了作为最先进（SOTA）LLM 基础代理的潜力，特别是在跨任务学习、自我改进和记忆机制方面。通过将 ExpeL 与现有的 SOTA 代理如 Reflexion[[98](https://arxiv.org/html/2408.02479v1#bib.bib98)]进行比较，ExpeL 在各种任务环境中优于基线方法。这些研究共同表明，自主学习和改进在 LLM 基础代理中的重要性，代理系统通过自我反馈、自我反思和经验积累不断优化和改进决策过程，相比于传统 LLM 表现出更高的自主性和灵活性。与主要依赖预训练数据和参数更新的传统 LLM 不同，LLM 基础代理通过持续的自我学习和反馈机制实时适应和提升其表现，因此在各种任务中展示了卓越的性能。

[[99](https://arxiv.org/html/2408.02479v1#bib.bib99)] 提出了 AGENTVERSE 多智能体框架，旨在通过协作提高任务完成效率和效果。该框架通过设计一个协作系统的专家代理，借鉴了人类群体动力学，在文本理解、推理、编码和工具使用等任务中展现出卓越的表现。实验表明，AGENTVERSE 框架不仅在独立任务完成中表现良好，而且通过群体协作显著提高了性能，特别是在编码任务中，框架利用 GPT-4 作为代理组的大脑。该框架还在协作过程中观察到了代理的涌现行为，如自发行为、从众行为和破坏性行为，为理解和优化多智能体系统提供了宝贵的见解。

另一项多智能体研究 [[100](https://arxiv.org/html/2408.02479v1#bib.bib100)] 引入了 CAMEL 框架，这是一种著名的智能体框架，旨在探索构建可扩展技术以促进自主协作智能体框架。该研究提出了一种角色扮演协作智能体框架，通过嵌入式提示引导对话智能体完成任务，同时保持与人类意图的一致性。CAMEL 框架生成对话数据以研究智能体社会中的行为和能力，该研究通过微调 LLaMA-7B 模型进一步提升了智能体的性能，验证了生成数据集在提升 LLM 能力方面的有效性。 [[101](https://arxiv.org/html/2408.02479v1#bib.bib101)] 研究了 LLM 增强型自主智能体的全面比较，并提出了一种新的多智能体协调策略，用于通过高效的通信和协调解决复杂任务，称为 BOLAA。实验显示，BOLAA 在 WebShop 环境中，尤其是在高性能 LLM 中，表现优于其他智能体架构。这三项研究都集中在通过增加智能体数量来实现多智能体协作架构。这一趋势表明，更多的框架开始探索多智能体系统的潜力。 [[44](https://arxiv.org/html/2408.02479v1#bib.bib44)] 探索了通过增加智能体数量来提高 LLM 性能的方法。通过采样和投票方法，该研究表明，随着智能体数量的增加，LLM 在算术推理、一般推理和代码生成任务中的表现显著改善。这一方法证明了多智能体协作在提升模型性能方面的有效性。这些研究共同表明了多智能体协作和对话框架在自主学习和决策任务中的重要性。与传统的 LLM 相比，这些多智能体框架在零样本学习下提高了推理准确性，并展示了更高的自主性和灵活性，从而减少了开发者的负担。

基于 LLM 的智能体不仅能执行复杂的数据分析任务，还展现了在模拟和理解人类信任行为方面的潜力。[[102](https://arxiv.org/html/2408.02479v1#bib.bib102)] 介绍了一个名为 SELF 的框架，该框架旨在通过语言反馈实现 LLM 的自我进化，使用 RLHF 训练智能体行为以满足人类对齐。该框架通过自我反馈和自我改进的迭代过程增强模型能力，无需人工干预。在实验中，GSM8K 和 SVAMP 数据集上的测试准确率分别提高了 6.82%和 4.9%，而 Vicuna 测试集和 Evol-Instruct 测试集上的整体任务胜率也分别提高了 10%和 6.9%。另一项类似的研究探讨了基于 LLM 的智能体模拟人类信任行为的潜力。[[103](https://arxiv.org/html/2408.02479v1#bib.bib103)] 还考察了基于 LLM 的智能体是否可以模拟人类信任行为。该研究旨在确定 LLM 智能体是否展现出类似于人类的信任行为，并探讨这些行为是否能与人类信任对齐。通过初始资金分配和回报信任游戏等一系列信任游戏变体，该研究分析了 LLM 智能体在不同情境下的信任决策和行为。结果表明，特别是对于 GPT-4，LLM 智能体在这些信任游戏中展现出的信任行为与人类期望一致，验证了 LLM 智能体在模拟人类信任行为方面的潜力。对各种数据集的高效准确处理凸显了在软件工程等领域的广泛应用前景。在模拟信任行为方面，LLM 智能体通过复杂的信任决策和行为分析展示了类似于人类的行为模式，为未来的人机协作和人类行为模拟提供了重要的理论基础。

将 LLMs 集成到代理中可以处理更复杂的任务。[[104](https://arxiv.org/html/2408.02479v1#bib.bib104)] 提出了一个名为 AgentLite 的轻量级用户友好型库，旨在简化任务导向的 LLM 基于代理系统的开发、原型设计和评估。该研究的主要目标是通过引入灵活的框架来增强 LLM 基于代理的能力和灵活性，从而在各种应用中提高其表现。这个框架通过任务分解和多代理协调来提升任务解决能力，采用了一个层次化的多代理协调方法，其中一个管理代理监督每个代理的任务执行。[[105](https://arxiv.org/html/2408.02479v1#bib.bib105)] 介绍了一个名为 GPTSwarm 的框架，该框架将 LLM 基于代理表示为计算图，以统一现有的提示工程技术，并引入了优化这些图以增强代理性能的方法。研究通过 MMLU、Mini Crosswords 和 HumanEval 等多个基准验证了该框架的有效性。该框架在 GAIA 基准上表现出显著的性能提升，与现有最佳方法相比，改进幅度高达 90.2%。此外，代理在软件工程和安全领域展示了强大的自主学习和决策能力，这将在随后的软件安全部分中介绍 [[106](https://arxiv.org/html/2408.02479v1#bib.bib106)] [[107](https://arxiv.org/html/2408.02479v1#bib.bib107)] [[108](https://arxiv.org/html/2408.02479v1#bib.bib108)] [[109](https://arxiv.org/html/2408.02479v1#bib.bib109)]。

### VI-C 分析

总体而言，LLMs 和 LLM 基于的代理在自主学习和决策方面表现出强大的能力，但视角略有不同。这些差异体现在任务执行的重点上，以及自主性、互动性、学习和适应机制以及与其他系统和模态的集成。从任务执行重点的角度来看，LLMs 主要集中在提高软件工程中的特定功能，如调试、问题解决和自动推理。他们执行的任务通常是静态和定义明确的，例如自动调试，增强调试能力以自主识别和纠正错误，评估创造力以及判断来自其他聊天机器人的响应。相比之下，LLM 基于的代理不仅关注特定任务，还同时管理多个任务，通常涉及动态决策和与其他代理或系统的互动。这些代理任务的例子包括通过多代理讨论增强推理、从经验中持续学习、需要实时动态决策，同时 LLM 基于的代理也可以接触到视觉环境中的多模态任务。

我们可以得出结论，基于大语言模型（LLM）的智能体在自主学习和决策主题中的应用主要涉及通过各种框架设计来探索其在特定任务中的表现。这些研究评估了智能体的自主性和决策能力，以确定它们是否符合人类行为和决策过程。如果我们深入研究具体的任务设计，从自主性和互动性方面来看，LLM 通常被设计为执行高度特定的任务，而不需要适应外部输入或环境变化，它们主要作为单一模型在预定义的范围内处理和响应，这也适用于所有 LLM 应用。另一方面，基于 LLM 的智能体表现出更高的自主性，通常被设计为实时与环境进行互动或适应，它们往往是多智能体系统的一部分，其中协作和沟通是关键组件，例如使用额外的模型或工具来进一步帮助规划阶段。在与其他系统和模态的集成方面，LLM 通常在文本输入输出场景中运行，即使在多模态设置中，它们的角色通常也限于处理和生成基于文本的内容。此外，基于 LLM 的智能体更有可能与其他系统和模态如视觉输入或现实世界感知数据进行集成，使它们能够执行更复杂和基于上下文的决策任务。

![参考说明](img/b345d2f22a9d172bafdaaa45d66ec7b6.png)

图 6：Expel[[35](https://arxiv.org/html/2408.02479v1#bib.bib35)] 框架与 Reflexion[[98](https://arxiv.org/html/2408.02479v1#bib.bib98)] 在经验收集中的应用

关于学习和适应机制，LLMs 的适应和学习通常局限于模型的训练数据和参数范围，尽管它们可以通过新数据更新进行适应，但它们缺乏从实时反馈中持续学习的能力，更倾向于利用现有知识来解决问题和生成响应。相比之下，基于 LLM 的代理通常配备有经验学习和实时反馈适应机制，允许它们根据持续的互动来优化策略和响应。一个很好的 LLM 代理框架的例子是 Expel [[35](https://arxiv.org/html/2408.02479v1#bib.bib35)], 它利用了之前的研究 ReAct [[36](https://arxiv.org/html/2408.02479v1#bib.bib36)] 和 Reflexion [[98](https://arxiv.org/html/2408.02479v1#bib.bib98)] 如图所示。 [6](https://arxiv.org/html/2408.02479v1#S6.F6 "Figure 6 ‣ VI-C Analysis ‣ VI Autonomous Learning and Decision Making ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future"). 该框架利用内存池和见解池来使 LLM 能够从过去的知识中学习，从而帮助后续的决策。这种自主决策能力是传统 LLM 框架无法实现的。

### VI-D 基准测试

在自主学习和决策领域，LLMs 和基于 LLM 的代理使用的基准数据集在任务处理和应用需求上非常相似。我们可以更深入地了解两种方法在不同任务和应用环境中的优势和劣势。有关具体的数据集参考，请参见表 [VII](https://arxiv.org/html/2408.02479v1#S6.T7 "TABLE VII ‣ VI-E Evaluation Metrics ‣ VI Autonomous Learning and Decision Making ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future").

在对大型语言模型（LLMs）的研究中，主要的数据集包括 Defects4J、MMLU、TransCoder 和 MBPP。这些数据集主要用于评估模型在特定领域和任务中的表现。Defects4J 是一个在软件工程领域广泛使用的数据集，包含来自 17 个 Java 项目的 525 个真实缺陷。它旨在通过提供一个标准化的基准来测试自动程序修复和缺陷检测工具的有效性，从而允许研究人员比较不同方法的性能。MMLU（大规模多任务语言理解）是一个大规模的基准数据集，涵盖了 57 个学科，测试模型在多任务语言理解中的广泛知识和推理能力。它包括从基础教育到专业水平的问题，如大学数学、商业伦理和大学化学，挑战模型的多样知识基础和推理能力。TransCoder 数据集专注于跨编程语言的代码翻译，用于评估模型从一种编程语言自动翻译到另一种编程语言的能力。这对多语言软件开发和维护至关重要，因为它可以大大提高开发效率。MBPP（主要基础 Python 编程）在前面的章节中已介绍，它是一个包含 427 个 Python 编程问题的数据集，涵盖基础概念和标准库函数，广泛用于测试模型在不同编程场景下的表现，评估其生成正确和高效代码的能力。

相对而言，基于 LLM 的智能体使用的数据集强调在复杂场景中的多任务处理和决策能力。主要数据集包括 HotpotQA、ALFWorld、FEVER、WebShop 和 MGSM。HotpotQA 是一个多跳问答数据集，要求模型在回答问题时参考来自多个文档的内容，评估其信息综合和推理能力，这个数据集挑战了模型在复杂推理任务中的表现。ALFWorld 是一个基于文本的环境模拟数据集，要求多步骤决策，模型在虚拟家庭环境中完成任务。该数据集结合了自然语言处理和决策制定，评估模型在动态和互动任务中的表现。FEVER（事实提取与验证）数据集用于事实验证任务，模型需要验证给定陈述的真实性并提供证据，评估模型在信息检索和逻辑推理方面的能力。WebShop 是一个在线购物环境模拟数据集，包含 118 万个现实世界的产品和人类指令，用于测试模型在复杂决策任务中的表现，如完成购物任务和属性匹配。MGSM（多模态广义序列建模）是一个多模态数据集，包含与对话、创意写作、数学推理和逻辑推理相关的任务，评估模型在多模态任务中的综合能力。

相比之下，LLM 数据集通常关注于单一的、静态的任务，如代码生成、数学推理和创意写作，适合于在预定义任务范围内工作的模型。像 Defects4J、MMLU 和 MBPP 这样的数据集有助于评估模型在特定领域的能力。基于 LLM 的智能体更适合于复杂、多任务和动态的环境，其中数据集要求模型处理多模态输入和实时决策，这可以展示其在处理复杂交互和多任务场景中的优势。像 HotpotQA、ALFWorld、FEVER 和 WebShop 这样的数据集挑战了模型在信息综合、动态决策/交互和多模态任务中的表现。这种差异源于两者的不同设计目标：LLM 旨在优化单一任务的表现，而基于 LLM 的智能体被设计为处理复杂或多模态任务，这需要更高的自主性和适应性。这也反映了现代应用对高度互动、适应性强和多功能 AI 系统的需求，推动了从单一 LLM 模型到多智能体系统的发展。通过这些分析，我们可以识别 LLM 和基于 LLM 的智能体在自主学习和决策中的不同应用，选择合适的框架以满足现实世界应用中的不同任务需求是非常重要的。

### VI-E 评估指标

在对 LLMs（大语言模型）及基于 LLM 的智能体的研究中，使用了各种评估指标，这些指标用于评估模型在特定任务中的表现，并分析其在该领域的应用效果。下面，我们讨论了几个具有代表性的研究，分析了它们使用的评估指标，并探讨了 LLMs 与基于 LLM 的智能体在这一领域的差异。

在 LLMs 的研究中，评估指标主要集中于模型的准确性和任务完成情况。在[[90](https://arxiv.org/html/2408.02479v1#bib.bib90)]中，研究人员使用了通过期望 0/1 损失（正确响应的比例）来衡量投票推理系统的准确性，以评估模型性能。该指标通过多次调用来评估模型的准确性，反映了 LLMs 通过迭代推理提高结果准确性的能力。文献中的常见评估指标包括准确性和样本效率，准确性指模型做出正确预测的比例，而样本效率衡量达到某一准确性水平所需的样本数量。这些指标评估了模型的预测能力和决策能力，以及其在训练中的数据利用效率。在[[92](https://arxiv.org/html/2408.02479v1#bib.bib92)]中，评估指标包括可能的补丁、正确的补丁、精确度和开发者准确性。可能的补丁指通过所有测试的补丁，而正确的补丁在语义上等同于原始的开发者补丁。精确度衡量可能的补丁中正确补丁的比例，开发者准确性通过人工评估来评估有无解释的补丁的正确性。这些指标强调了模型在自动化代码修复中的解释能力和实际效果，并增加了对人工评估的依赖。为了评估模型的创造力，使用了价值、新颖性和惊讶度作为创造力维度。质量、社会接受度和生成作品的相似性，以及生成创造性产品的能力也被纳入评估范围。[[110](https://arxiv.org/html/2408.02479v1#bib.bib110)]使用了 24 点游戏的成功率和创意写作中生成段落的连贯性作为评估指标。这些指标评估了模型在问题解决和文本生成中的表现，展示了 LLMs 在解决复杂问题和生成连贯文本方面的潜力。在[[95](https://arxiv.org/html/2408.02479v1#bib.bib95)]中，一致性和成功率被用作评估指标，一致性计算了两位评审在随机选择问题上的一致概率，衡量了 LLM 评审与人类偏好的对齐程度。成功率用于特定任务（如 24 点游戏）以衡量正确响应的比例。

相比之下，基于 LLM 的代理使用更多样化的评估指标来反映其多代理协作特性。在[[97](https://arxiv.org/html/2408.02479v1#bib.bib97)]中，评估指标包括感知得分（P-Score）、认知得分（C-Score）和行动得分（A-Score）。这些指标全面评估模型的感知、认知和行动能力，展示了基于 LLM 的代理在处理多模态任务中的综合表现。在多模态应用中，成功率（SR）常作为主要指标，通过 HotpotQA 和 FEVER 等任务评估精准匹配的成功率。这些指标关注任务完成的成功率和准确性，展示了基于 LLM 的代理在不同任务环境中的实际执行能力。在[[111](https://arxiv.org/html/2408.02479v1#bib.bib111)]中，评估指标包括从业者反馈、效率和准确性。从业者反馈使用李克特量表来收集满意度和表现反馈，李克特量表是一种常用的心理测量工具，旨在测量个人对特定陈述的态度或意见。该量表通常包括以下五个选项：强烈不同意、不同意、中立、同意、强烈同意。同时，效率和准确性通过从业者验证的模型执行的定性数据分析效果进行衡量。这些指标评估代理在定性数据分析中的表现，展示其在实际应用中的效用和准确性。

通过比较这些指标，我们发现 LLM 使用传统指标如准确性和样本效率来评估其能力。相比之下，基于 LLM 的代理通过多代理处理更复杂的算法，这需要更全面和多样化的指标来从多个方向评估其性能。基于 LLM 的代理在多模态任务和自我进化任务中强调感知、认知和行动能力的综合表现。这种差异反映了 LLM 在单任务优化中的优势以及基于 LLM 的代理在协作处理复杂任务中的潜力，以及更高的自主学习能力。此外，基于 LLM 的代理的实际应用评估指标，如从业者反馈、效率和准确性，展示了其在现实场景中的效用和用户满意度。这种评估方法不仅评估任务完成情况，还考虑用户体验的综合评估，这也能评估其决策能力的人类对齐情况。

表 VII: 自主学习和决策制定中的评估指标

{tblr}

cell11 = c，cell12 = c，cell13 = c，cell24 = c，cell34 = c，cell44 = c，cell54 = c，cell64 = c，cell74 = c，cell84 = c，cell94 = c，cell104 = c，cell114 = c，cell124 = c，cell134 = c，cell144 = c，cell154 = c，cell164 = c，cell174 = c，cell184 = c，cell194 = c，cell204 = c，cell214 = c，cell224 = c，cell234 = c，cell244 = c，cell254 = c，水平线，垂直线，参考文献与基准评估指标代理

[[90](https://arxiv.org/html/2408.02479v1#bib.bib90)] MMLU 准确性否

[[91](https://arxiv.org/html/2408.02479v1#bib.bib91)] Spider、TransCoder、MBPP 准确性、样本效率否

[[92](https://arxiv.org/html/2408.02479v1#bib.bib92)] Defects4J v1.2，Defects4J v2.0，

几乎正确的 HumanEval 合理补丁，

正确补丁，

精确度，准确性否

[[93](https://arxiv.org/html/2408.02479v1#bib.bib93)] 无特定质量，接受率否

[[110](https://arxiv.org/html/2408.02479v1#bib.bib110)] 24 点游戏、创意写作，

5x5 纵横字谜成功率，一致性否

[[95](https://arxiv.org/html/2408.02479v1#bib.bib95)] MT-Bench，聊天机器人竞技场 一致率，成功率

人类判断否

[[96](https://arxiv.org/html/2408.02479v1#bib.bib96)] ECQA、GSM8K、FOLIO-wiki 准确性是

[[97](https://arxiv.org/html/2408.02479v1#bib.bib97)] PCA-EVAL 准确性、P/C/A-评分是

[[35](https://arxiv.org/html/2408.02479v1#bib.bib35)] HotpotQA、ALFWorld、WebShop、FEVER 成功率是

[[106](https://arxiv.org/html/2408.02479v1#bib.bib106)] 未指定成功率，自主性水平是

[[44](https://arxiv.org/html/2408.02479v1#bib.bib44)] GSM8K、MATH、MMLU、国际象棋、HumanEval 准确性是

[[107](https://arxiv.org/html/2408.02479v1#bib.bib107)] MITRE ATTCK 框架 能力识别漏洞是

[[102](https://arxiv.org/html/2408.02479v1#bib.bib102)] GSM8K、SVAMP、Vicuna 测试集，

Evol-Instruct 测试集准确性，反馈准确性是

[[98](https://arxiv.org/html/2408.02479v1#bib.bib98)] HotPotQA、ALFWorld、HumanEval、MBPP，

LeetcodeHardGym 成功率@1，成功率是

[[111](https://arxiv.org/html/2408.02479v1#bib.bib111)] Github 开发者讨论，BBC 新闻，

社交媒体对话，

深度访谈从业者反馈，

效率与准确性是

[[100](https://arxiv.org/html/2408.02479v1#bib.bib100)] AI 社会、代码、数学、科学，

错位人类评价，

GPT-4 评估是

[[99](https://arxiv.org/html/2408.02479v1#bib.bib99)] FED，Commongen 挑战，

MGSM，逻辑网格谜题，

HumanEval 成功率@1，任务完成率是

[[36](https://arxiv.org/html/2408.02479v1#bib.bib36)] HotpotQA、FEVER、ALFWorld、WebShop 精确匹配、准确性，

成功率，平均分数是

[[103](https://arxiv.org/html/2408.02479v1#bib.bib103)] 信任游戏、独裁者游戏，

MAP 信任游戏，

风险独裁者游戏，

彩票游戏，重复信任游戏 有效响应率，

对齐是

[[104](https://arxiv.org/html/2408.02479v1#bib.bib104)] HotPotQA、WebShop F1-分数，平均奖励是

[[108](https://arxiv.org/html/2408.02479v1#bib.bib108)] 263 个真实智能合约漏洞的 F1 分数，准确率

精度，召回

一致性率。 是

[[109](https://arxiv.org/html/2408.02479v1#bib.bib109)] 15 个真实世界的一天漏洞

来自 CVE 数据库的成功率，成本 是

[[101](https://arxiv.org/html/2408.02479v1#bib.bib101)] WebShop，HotPotQA 与 Wikipedia AP 奖励分数，召回 是

[[105](https://arxiv.org/html/2408.02479v1#bib.bib105)] MMLU, Mini Crosswords, HumanEval，

GAIA 准确率，Pass@1 是

## VII 软件设计与评估

将 LLM 应用于软件设计与评估与之前的主题有很大的重叠，软件设计是软件开发的早期阶段，设计质量直接影响未来开发的质量。现代软件工程方法强调设计与开发的整合，以确保在设计阶段做出的决策无缝转化为高质量的代码。因此，关于软件设计的研究通常探讨与代码生成和开发相关的方面，利用 LLM 在具有特定框架和特殊架构设计的软件开发中。软件设计框架通常涉及多个阶段的持续改进，以实现最佳结果，这可以视为 LLM 在软件开发中应用的一部分 [[83](https://arxiv.org/html/2408.02479v1#bib.bib83)]。类似地，[[85](https://arxiv.org/html/2408.02479v1#bib.bib85)] 和 [[84](https://arxiv.org/html/2408.02479v1#bib.bib84)] 强调在使用 LLM 辅助开发和设计时工具或 API 接口的频繁使用，展示了与代码生成和软件开发主题的重叠。

LLMs 在软件设计和评估中也与自主学习和决策制定广泛交叉，这两个主题是相互关联的领域。软件设计需要考虑系统的适应性和学习能力，以应对动态环境，因此涉及自主学习和决策制定的设计评估自然成为这两个主题交集的焦点。许多 LLM 技术和方法在这两个领域中找到类似的应用，例如基于强化学习的 LLM 可以用于自动化设计决策和评估，也可以用于自我学习和优化。LLMs 在软件工程中的常见应用包括利用提示工程技术对模型进行微调，以持续提升性能，特别是在软件设计和评估方面，通常需要更多的样本学习，以确保模型输出符合用户期望 [[93](https://arxiv.org/html/2408.02479v1#bib.bib93)] [[102](https://arxiv.org/html/2408.02479v1#bib.bib102)] [[44](https://arxiv.org/html/2408.02479v1#bib.bib44)] [[111](https://arxiv.org/html/2408.02479v1#bib.bib111)] [[105](https://arxiv.org/html/2408.02479v1#bib.bib105)] [[96](https://arxiv.org/html/2408.02479v1#bib.bib96)]。此外，需求工程中的需求获取和规范也可以被视为软件设计和评估的一部分 [[51](https://arxiv.org/html/2408.02479v1#bib.bib51)] [[112](https://arxiv.org/html/2408.02479v1#bib.bib112)]。本节回顾了近年来 LLMs 在软件设计和评估方面的主要研究成果，讨论了它们的应用场景和实际效果。

### VII-A LLMs 任务

近年来，关于大语言模型（LLMs）在自动化、优化和代码理解等任务中的应用进行了广泛的研究。ChatGPT 被广泛用于各种软件工程任务，并在日志总结、代

还存在许多新颖的应用设计，LLM 在工程设计中的应用也在不断探索。一项研究探讨了软件/硬件协同设计的策略，以优化 LLM，并将这些策略应用于设计验证[[116](https://arxiv.org/html/2408.02479v1#bib.bib116)]。通过量化、剪枝和操作级优化，这项研究展示了在高级综合（HLS）设计功能验证中的应用。GPT-4 被用于生成包含预定义错误的高级综合（HLS）设计，以创建一个名为 Chrysalis 的数据集，该数据集为评估和优化基于 LLM 的 HLS 调试助手提供了宝贵的资源。经过优化的 LLM 显著提升了推理性能，为电子设计自动化（EDA）领域中的错误检测和修正提供了新的可能性。在[[117](https://arxiv.org/html/2408.02479v1#bib.bib117)]中，研究人员介绍了 RaWi，这是一种数据驱动的 GUI 原型设计方法。该框架允许用户从该库中检索 GUI，进行编辑，并快速创建新的高保真原型。通过将 RaWi 与传统的 GUI 原型设计工具（Mockplus）进行比较实验，测量用户创建原型的速度和效果。结果表明，RaWi 在多个基准测试中表现优异，在 precision@k 指标上提高了 40%。这项研究证明了 LLM 在软件设计原型阶段提高效率的可能性，使设计师能够快速迭代 GUI 设计，促进早期发现设计缺陷。随着 LLM 带来的新可能性，教育领域也进行了广泛讨论，研究人员探讨了大语言模型普及对教育的影响[[118](https://arxiv.org/html/2408.02479v1#bib.bib118)]。研究表明，ChatGPT 在回答软件测试课程问题时展现了显著潜力，但也存在一些局限性[[119](https://arxiv.org/html/2408.02479v1#bib.bib119)]。ChatGPT 能够回答约 77.5%的问题，并且 55.6%的回答是正确或部分正确的。然而，其解释的正确率仅为 53.0%，这表明在教育应用中仍需进一步改进。

### VII-B 基于 LLM 的智能体任务

基于 LLM 的代理在软件设计和评估中的应用提升了开发效率和代码质量，同时展示了 LLM 代理在实际软件工程任务中的广泛适用性和巨大潜力。[[120](https://arxiv.org/html/2408.02479v1#bib.bib120)] 探讨了自主代理在软件工程中的当前能力、挑战和机会。研究评估了 Auto-GPT 在软件开发生命周期（SDLC）不同阶段的表现，包括软件设计、测试和与 GitHub 的集成。论文发现，详细的上下文提示显著提升了代理在复杂软件工程任务中的表现，并提到了上下文丰富的提示在减少错误和提高效率方面的重要性，强调了 LLM 代理在自动化和优化各种 SDLC 任务方面的潜力，从而提高开发效率。本文还评估了 Auto-GPT 的局限性，包括任务或目标跳过、生成不必要的代码或文件（幻觉）、重复或循环响应、缺乏任务完成验证机制。这些局限性可能导致不完整的工作流程、不准确的输出和在实际应用中的性能不稳定。

[[121](https://arxiv.org/html/2408.02479v1#bib.bib121)] 介绍了 ChatDev，这是第一个虚拟聊天驱动的软件开发公司，它的概念不仅使用 LLMs 进行特定任务，还将其作为聊天驱动的多智能体框架中的核心协调者。这种方法允许更结构化、高效和协作的软件开发流程，探索聊天驱动的多智能体系统如何实现高效的软件设计和评估，减少代码漏洞，提高开发效率和质量。实验显示，ChatDev 可以在平均 `409.84` 秒内设计和生成软件，成本仅为 $0.2967，同时显著减少代码漏洞。这表明，基于聊天的多智能体框架能够提高软件开发的效率和质量。微软研究团队介绍了另一个类似的协作框架，[[122](https://arxiv.org/html/2408.02479v1#bib.bib122)] 演示了使用 LLMs，特别是 ChatGPT 作为智能体控制器来管理和执行各种 AI 任务的有效性。HuggingGPT 系统利用 ChatGPT 协调 Hugging Face 中各种 AI 模型的任务执行，目的是测试该系统如何有效处理复杂的 AI 任务，包括语言、视觉和语音任务，通过根据用户请求执行适当的模型。创新在于不仅将 LLMs 作为直接任务执行的工具，还作为核心协调者，利用现有的 AI 模型完成复杂任务，这种方法扩展了 LLMs 在超越典型语言任务的实际应用性。[[123](https://arxiv.org/html/2408.02479v1#bib.bib123)] 提出了 LLMARENA 基准框架来评估 LLMs 在动态多智能体环境中的能力，这一理念类似于 ChatDev，但创新在于将关注点从单一智能体静态任务转向动态和互动的多智能体环境，提供了一个更现实和具有挑战性的环境来评估 LLMs 的实际效用，这种方法反映了现实世界中多个智能体（无论是 AI 还是人类）的互动与协作。实验表明，该框架可以测试 LLMs 在游戏环境中的空间设计、战略规划和团队合作能力，为在多智能体系统中设计和评估 LLMs 提供了新的可能性和工具。

[[124](https://arxiv.org/html/2408.02479v1#bib.bib124)] 介绍了“Flows”概念框架，用于结构化 AI 模型与人类之间的互动，以提高推理和协作能力。该研究提出了将过程概念化为独立的、以目标驱动的实体，通过标准化的消息接口进行互动，从而实现模块化和可扩展的设计。这种方法本质上支持并发，支持开发复杂的嵌套 AI 互动，而无需管理复杂的依赖关系。竞争编码任务中的实验表明，“Flows”框架将 AI 模型的问题解决率提高了 21 个百分点，人类与 AI 的协作率提高了 54 个百分点。这表明模块化设计可以增强 AI 和人类的协作，从而改善软件设计和评估过程。

[[125](https://arxiv.org/html/2408.02479v1#bib.bib125)] 提出了一个新的分类法，以结构化地理解和分析 LLM 集成应用，为软件设计和评估提供了新的理论和方法。这一分类法有助于理解 LLM 组件在软件系统中的集成，为开发更有效和高效的 LLM 集成应用奠定了理论基础。同样，[[126](https://arxiv.org/html/2408.02479v1#bib.bib126)] 探讨了基于 LLM 的代理在软件维护任务中的应用，通过协作框架提高了代码质量和可靠性。这项研究本应归类于软件维护领域，但展现了设计结构的迭代方式。该框架利用任务分解和多代理策略来处理传统一次性方法无法有效处理的复杂工程任务，多个代理可以相互学习，从而改善软件维护结果。实验表明，多代理系统在复杂调试任务中的表现优于单代理系统，这表明这一新框架可以应用于软件设计中，以提供更安全的架构。

### VII-C 分析

总体而言，LLM 在软件设计和评估中的应用通常集中在特定任务的自动化，如代码生成和日志总结，更倾向于评估能力而非设计阶段的实施过程。软件设计过程与软件开发和需求工程密切相关。如前所述，使用 LLM 协助软件开发通常包括软件设计过程的各个方面，特别是在生成相关设计文档方面。因此，专注于使用 LLM 进行更高层次的软件设计任务的研究相对较少。

基于 LLM 的代理通过智能决策和任务执行扩展了 LLM 的能力，这些代理能够协作、动态调整任务，并收集和利用外部信息。在软件设计和评估中，单一模型通常不能全面考虑设计和评估方面，这就是为什么更多的软件开发人员不愿意将高级任务委托给 AI 的原因。基于 LLM 的代理通过协作和更精细的角色划分，可以高效完成设计任务并适应各种应用场景。然而，基于 LLM 的代理在软件设计中的应用通常包括在软件开发中，如前所述，自我反思和行动前的推理发生在软件设计阶段。Chatdev[[121](https://arxiv.org/html/2408.02479v1#bib.bib121)] 框架利用角色分配创建了一个独立的软件设计阶段，这显著提高了后续开发阶段的灵活性和准确性。在效率和成本方面，LLM 在文本生成和漏洞检测方面仍略优于基于 LLM 的代理。然而，处理类似于软件维护和根本原因分析的任务需要更复杂的架构，如多轮对话、知识图谱和 RAG 技术，这些都可以进一步有利于设计和评估阶段。

### VII-D 基准测试

基准测试包括公共数据集和作者自己构造的数据集，应用场景也如表格 [VIII](https://arxiv.org/html/2408.02479v1#S7.T8 "TABLE VIII ‣ VII-E Evaluation Metrics ‣ VII Software Design and Evaluation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")所示存在较大差异。BigCloneBench 是一个用于代码克隆检测的基准数据集，包含大量 Java 函数对。这些对被分类为克隆和非克隆，用于训练和评估克隆检测模型，主要评价指标是正确识别率。Chrysalis 数据集由[[116](https://arxiv.org/html/2408.02479v1#bib.bib116)]创建，包含来自 11 个开源可合成 HLS 数据集的 1000 多个函数级设计，主要用于评估 LLM 调试工具在检测和修正 HLS 设计中注入错误的有效性，主要评价指标是错误检测和修正的有效性。CodexGLUE 数据集是一个综合性的基准数据集，涵盖了各种代码生成和理解任务，如代码补全、代码修复和代码翻译，用于评估代码生成模型在实际编程任务中的表现。除了这些公共数据集，还使用了一些人工模拟的数据集，例如模拟招聘会环境数据集。该数据集模拟了一个包含多个任务场景如面试、招聘和团队项目协调的虚拟招聘会环境。该数据集用于评估生成代理在复杂社会任务中的协调能力，主要评价指标是任务协调成功率和角色匹配准确率。

相对而言，LLM（大规模语言模型）研究往往使用特定且公开的可用数据集，如 BigCloneBench。这些数据集提供了标准化的评估基准，帮助提高结果的可重复性和可比性。基于 LLM 的代理研究倾向于使用定制的实验设置或未指定的数据集，如需求文档，而不指定具体的数据集，但强调实验涉及 70 个用户需求。这种选择通常是因为研究需要从多个角度评估性能，如果使用一些通用数据集，很难完美适应垂直应用场景。LLM 和基于 LLM 的代理都使用多种数据集来评估模型的性能，这些数据集涵盖了从代码生成、代码理解到自然语言生成和任务管理的任务，因为软件设计和评估的主题与其他领域相关性较强。然而，由于基于 LLM 的代理可以扩展到视频和图片等应用场景，像 Auto-GPT 和 HuggingGPT 这样的代理也使用多模态数据集。这些数据集不仅包含代码和文本，还涉及图像和语音等多种数据类型。此外，与单一的 LLM 框架相比，基于 LLM 的代理需要评估更多领域，因此基准测试也需要分别考虑。例如，LLMARENA 专门设计用于测试 LLM 在动态、多代理环境中的性能，涵盖了空间推理、战略规划和风险评估等复杂任务。

### VII-E 评估指标

在软件设计与评估中，各种研究采用了不同的评估指标来衡量大型语言模型（LLMs）和基于 LLM 的代理在各种任务中的表现。无论是 LLM 还是基于 LLM 的代理研究都使用多个指标来全面评估模型性能，LLM 研究倾向于关注传统指标，如准确率、胜率和一致性，而基于 LLM 的代理研究则考虑这些基本指标，同时进一步引入复杂的评估方法，如任务协调成功率和角色匹配准确度。然而，不能明确指出未来的基于 LLM 的代理研究将始终使用更灵活的评估指标来考虑多个维度，这更多依赖于具体的任务和使用的数据集。根据这项调查观察到的现象，主要原因是 LLM 研究中的任务相对单一，主要集中在使用传统评估方法的静态任务，如日志总结。另一方面，基于 LLM 的代理研究涉及更广泛的多代理任务，其评估方法强调互动性和动态性。基于 LLM 的代理研究更注重模型的协作和决策能力，通过使用多维度评估指标来全面评估其在实际应用中的潜力，不仅仅考虑准确性。这解释了尽管在评估指标如准确性和完成时间上相似，基于 LLM 的代理使用灵活的评估指标，包括如互斥性和适当性等指标的原因。

表 VIII：软件设计与评估中的评估指标

| 参考文献 | 基准 | 评估指标 | 代理 |
| --- | --- | --- | --- |

|

&#124; [[113](https://arxiv.org/html/2408.02479v1#bib.bib113)] &#124;

|

&#124; BigCloneBench, &#124;

&#124; Python 函数, &#124;

&#124; Java 方法, &#124;

&#124; 随机日志, &#124;

&#124; 错误报告, &#124;

&#124; 需求规格说明 &#124;

| 准确性 | 否 |
| --- | --- |

|

&#124; [[114](https://arxiv.org/html/2408.02479v1#bib.bib114)] &#124;

| 未指定 | 胜率，一致性评分 | 否 |
| --- | --- | --- |

|

&#124; [[115](https://arxiv.org/html/2408.02479v1#bib.bib115)] &#124;

| 未指定 |
| --- |

&#124; 嵌入式指标, &#124;

&#124; 基于概率的指标, &#124;

&#124; 比较，排名 &#124;

| 否 |
| --- |

|

&#124; [[116](https://arxiv.org/html/2408.02479v1#bib.bib116)] &#124;

| Chrysalis | 效果 | 否 |
| --- | --- | --- |

|

&#124; [[127](https://arxiv.org/html/2408.02479v1#bib.bib127)] &#124;

|

&#124; CommonsenseQA, &#124;

&#124; StrategyQA, GSM8K &#124;

|

&#124; 准确率, &#124;

&#124; 令牌，时间成本 &#124;

| 否 |
| --- |

|

&#124; [[119](https://arxiv.org/html/2408.02479v1#bib.bib119)] &#124;

|

&#124; 31 个问题来自 &#124;

&#124; 软件测试教材. &#124;

| 正确性，效果 | 否 |
| --- | --- |

|

&#124; [[128](https://arxiv.org/html/2408.02479v1#bib.bib128)] &#124;

|

&#124; 医学记录, &#124;

&#124; 亚马逊产品 &#124;

&#124; 描述 &#124;

|

&#124; 覆盖率，&#124;

&#124; 虚假失败率 &#124;

&#124; 对齐。 &#124;

| 否 |
| --- |

|

&#124; [[117](https://arxiv.org/html/2408.02479v1#bib.bib117)] &#124;

| Rico |
| --- |

&#124; Precision@k，&#124;

&#124; NDCG@k，&#124;

&#124; 平均倒排排名，&#124;

&#124; 平均精度，HITS@k &#124;

| 否 |
| --- |

|

&#124; [[120](https://arxiv.org/html/2408.02479v1#bib.bib120)] &#124;

| 未指定 |
| --- |

&#124; 准确性，成功率，&#124;

&#124; 一致性，效果 &#124;

| 是 |
| --- |

|

&#124; [[122](https://arxiv.org/html/2408.02479v1#bib.bib122)] &#124;

|

&#124; Hugging Face 的 &#124;

&#124; 模型仓库。 &#124;

|

&#124; 准确性，&#124;

&#124; 精度，&#124;

&#124; 召回率，&#124;

&#124; F1 分数，&#124;

&#124; 编辑距离，&#124;

&#124; GPT-4 分数，&#124;

&#124; 通过率，&#124;

&#124; 合理性，&#124;

&#124; 成功率。 &#124;

| 是 |
| --- |

|

&#124; [[124](https://arxiv.org/html/2408.02479v1#bib.bib124)] &#124;

| Codeforces，LeetCode | Pass@1 | 是 |
| --- | --- | --- |

|

&#124; [[121](https://arxiv.org/html/2408.02479v1#bib.bib121)] &#124;

| 70 用户需求。 |
| --- |

&#124; 生成的文件数量，&#124;

&#124; 耗时，成本 &#124;

| 是 |
| --- |

|

&#124; [[121](https://arxiv.org/html/2408.02479v1#bib.bib121)] &#124;

| Codeforces |
| --- |

&#124; 完整性，&#124;

&#124; 鲁棒性，简洁性，&#124;

&#124; 互斥性，&#124;

&#124; 解释力，&#124;

&#124; 扩展性。 &#124;

| 是 |
| --- |

|

&#124; [[125](https://arxiv.org/html/2408.02479v1#bib.bib125)] &#124;

| 样本应用。 | BERTScore，BLEU | 是 |
| --- | --- | --- |

|

&#124; [[126](https://arxiv.org/html/2408.02479v1#bib.bib126)] &#124;

| CodexGLUE |
| --- |

&#124; BLEU，METEOR，&#124;

&#124; ROUGE-L，BERTScore &#124;

| 是 |
| --- |

|

&#124; [[129](https://arxiv.org/html/2408.02479v1#bib.bib129)] &#124;

| 生产事件 |
| --- |

&#124; 成功率，&#124;

&#124; 准确性，对齐，&#124;

&#124; 适当性 &#124;

| 是 |
| --- |

|

&#124; [[130](https://arxiv.org/html/2408.02479v1#bib.bib130)] &#124;

|

&#124; 模拟招聘会 &#124;

&#124; 环境 &#124;

|

&#124; 完成时间，&#124;

&#124; 任务进展，&#124;

&#124; 理解水平 &#124;

| 是 |
| --- |

## VIII 软件测试生成

在软件开发中，一个关键的组成部分是软件测试，这需要从系统开发初期到最终部署阶段持续进行。在行业中，通常使用敏捷开发方法，这种方法在每个阶段都持续进行系统测试，以确保整个系统的稳定性。每当新的代码提交到 GitHub 时，就会进行测试以确保更新版本的可用性。一个常见的方法是使用 Jenkins⁴⁴4[`www.jenkins.io/`](https://www.jenkins.io/)来实现持续集成和持续部署。Jenkins 会自动挂钩到开发者将代码推送到 GitHub 的操作，并对新版本运行测试套件。尽管整个过程趋向于自动化开发，但创建和完善测试用例仍然需要大量的人力。

开发中的典型角色包括软件测试，例如编写单元测试、集成测试和模糊测试。研究人员自 2000 年前就开始尝试使用人工智能来帮助生成测试用例。最初的实现通常涉及更简单形式的人工智能和机器学习，以自动化测试用例生成过程的部分环节。随着时间的推移，更多复杂的方法，如自然语言处理和机器学习模型，被应用于提高测试用例生成的精确性和范围。像 Sofy⁵⁵5[`sofy.ai/`](https://sofy.ai/) 这样的在线工具利用机器学习生成应用中的基于上下文的路径，也存在用于辅助生成测试套件。使用大语言模型生成测试用例是一项相对较新的尝试，但发展迅速。在 2020 年，研究人员利用在标注数据上微调的预训练语言模型来生成测试用例。他们开发了一种基于序列到序列的变换器模型，称为“ATHENATEST”，并将其生成的结果与 EvoSuite 和 GPT-3 进行了比较，展示了更好的测试覆盖率[[131](https://arxiv.org/html/2408.02479v1#bib.bib131)]。更多的研究和模型正在致力于测试套件生成实验，例如前面提到的 Codex 模型[[67](https://arxiv.org/html/2408.02479v1#bib.bib67)]，结合链式思维提示，通过 CodeCoT 实现了高质量的测试套件生成，即使在零样本场景下也是如此。引入大语言模型旨在自动化和简化测试过程，使其更加严格，能够处理人类可能容易忽视的方面。

### VIII-A 大语言模型任务

LLM 在软件测试生成中的应用广泛，不仅仅包括测试套件生成。本调查中审查的论文涵盖了多个方面，包括安全测试生成、错误重现、一般错误重现、模糊测试和覆盖驱动测试生成。这些任务通过各种模型和技术实现，显著提高了软件质量并减少了开发人员的工作量。[[132](https://arxiv.org/html/2408.02479v1#bib.bib132)]旨在评估使用 GPT-4 生成安全测试的有效性，演示了如何通过利用依赖性漏洞来进行供应链攻击。该研究尝试了不同的提示风格和模板，以探索不同信息输入对测试生成质量的影响，结果显示，由 ChatGPT 生成的测试成功发现了 55 个应用中的 24 个概念验证漏洞，超越了现有的工具 TRANSFER[[133](https://arxiv.org/html/2408.02479v1#bib.bib133)] 和 SIEGE⁶⁶6[`siegecyber.com.au/services/penetration-testing/`](https://siegecyber.com.au/services/penetration-testing/)。这项研究引入了一种使用 LLM 生成安全测试的新方法，并提供了 LLM 在安全测试领域潜力的实证证据，为开发人员提供了一种处理应用程序库漏洞的新方法。

另一个应用是错误重现，这使得测试人员能够更快、更有效地定位和修复错误。[[134](https://arxiv.org/html/2408.02479v1#bib.bib134)] 解决了当前错误重现方法的局限性，这些方法受到手工模式和预定义词汇表质量及清晰度的限制。论文提出并评估了一种新的方法框架，称为 AdbGPT，该框架使用大型语言模型自动从 Android 错误报告中重现错误。AdbGPT 被描述为在仅针对 Android 系统的自动错误重放方面优于当前的 SOTA 方法。实验结果表明，AdbGPT 在 S2R 实体提取中达到了 90.4% 和 90.8% 的准确率，在错误重现中的成功率为 81.3%，显著优于基线 ReCDroid 和消融研究版本。通过引入提示工程、少样本学习和链式思维推理，AdbGPT 展示了 LLM 在自动错误重现中的强大能力。它还使用 GUI 编码将 GUI 视图层次结构转换为类似 HTML 的语法，提供 LLM 对当前 GUI 状态的清晰理解。虽然 AdbGPT 专门针对 Android 系统，[[135](https://arxiv.org/html/2408.02479v1#bib.bib135)] 提出了 LIBRO 框架，该框架使用 LLM 从错误报告中生成错误重现测试。实验结果表明，LIBRO 成功重现了 Defects4J 数据集中的 33.5% 的错误和 GHRB 数据集中的 32.2% 的错误。通过结合先进的提示工程和后处理技术，LIBRO 展示了 LLM 在生成错误重现测试中的有效性和效率。虽然 LIBRO 相比 AdbGPT 在绝对有效性上较低，但它在更广泛的 Java 应用程序中进行了测试，而不仅限于 Android。因此，尽管 AdbGPT 在专门的 Android 错误重放中表现优异，LIBRO 提供了更广泛的 Java 应用程序错误重现范围。LLM 在安全测试生成、错误重现、模糊测试、程序修复和覆盖驱动测试生成等测试生成任务中的广泛应用突显了它们在提高软件质量和减轻开发人员负担方面的重大潜力。通过各种模型和技术，这些任务展示了 LLM 如何自动化和增强软件测试过程，解决了人类常常忽视的方面。

同样，在模糊测试中，LLM 显示出了潜在的潜力。[[136](https://arxiv.org/html/2408.02479v1#bib.bib136)]开发了一个通用模糊测试工具 Fuzz4All，该工具使用 LLM 生成和修改各种软件系统的输入。该工具解决了传统模糊测试工具与特定语言或系统紧密耦合且缺乏对语言特性演进的支持的问题。该研究进行了各种实验以测试该工具的能力，包括覆盖率比较、bug 发现和有针对性的模糊测试。结果表明，Fuzz4All 在所有测试语言中实现了最高的代码覆盖率，平均增加了 36.8％，并在九个系统中发现了 98 个 bug，这在当时被认为是 LLM 在通用模糊测试中的最新技术。通过自我提示和 LLM 驱动的模糊测试循环，Fuzz4All 展示了 LLM 在模糊测试中的有效性，并通过全面评估展示了它们在多种语言和测试系统（SUTs）下的能力。

[[137](https://arxiv.org/html/2408.02479v1#bib.bib137)]引入了 SymPrompt，一种新的代码感知提示策略，旨在解决现有基于搜索的软件测试（SBST）方法和传统 LLM 提示策略在生成高覆盖率测试用例方面的局限性。通过将原始测试生成过程分解为与测试方法执行路径对齐的多阶段序列，SymPrompt 生成了高覆盖率的测试用例。实验结果表明，SymPrompt 分别增加了 CodeGen2 和 GPT-4 的覆盖率 26％和 105％。通过路径约束提示和上下文构建技术，SymPrompt 展示了 LLM 在生成高覆盖率测试用例方面的潜力。[[138](https://arxiv.org/html/2408.02479v1#bib.bib138)]还关注了测试套件覆盖率，该研究引入了 COVERUP 系统，该系统通过覆盖分析和 LLM 的交互生成高覆盖率的 Python 回归测试。实验结果显示，通过迭代提示和覆盖率驱动方法，COVERUP 将代码覆盖率从 62％提高到 81％，将分支覆盖率从 35％提高到 53％。[[139](https://arxiv.org/html/2408.02479v1#bib.bib139)]提出了 AID 方法，该方法将 LLM 与差分测试结合，以改善“可能正确”软件的故障检测。通过比较 AID 在生成揭示故障的测试输入和检验的有效性，实验表明，AID 将召回率和精度分别提高了 1.80 倍和 2.65 倍，并将 F1 分数提高了 1.66 倍。通过将 LLM 与差分测试集成，AID 展示了 LLM 在检测复杂 bug 方面的强大能力。

### VIII-B 基于 LLM 的代理任务

在软件测试生成领域，基于 LLM 的代理的应用展示了其在自动化测试生成中的潜力。虽然依赖基于 LLM 的代理进行软件测试生成可能看起来过于庞大，但更多的研究则集中在漏洞检测和系统维护上。基于 LLM 的代理通过多代理协作系统分配测试生成、执行和优化等任务，可以提升测试的可靠性和质量。这些多代理系统在错误检测和修复以及覆盖测试方面显著改进。例如，AgentCoder 的多代理框架就是其中一个例子，如在代码生成和软件开发部分所讨论的[[82](https://arxiv.org/html/2408.02479v1#bib.bib82)]。该系统的主要目标是利用多个专业代理迭代优化代码生成，克服单一代理模型在生成有效代码和测试用例方面的局限性。论文介绍了测试设计代理，该代理创建多样化且全面的测试用例；还有测试执行代理，执行测试并提供反馈，达到了 MBPP 数据集的 89.9%通过率。同样，SocraTest 框架属于自主学习和决策制定主题[[106](https://arxiv.org/html/2408.02479v1#bib.bib106)]。该框架通过对话交互自动化测试过程，论文展示了使用 GPT-4 生成和优化测试用例的详细示例，强调了多步骤交互如何提升测试方法并生成测试代码。实验结果表明，通过对话式 LLMs，SocraTest 能够有效生成和优化测试用例，并利用中间件促进 LLM 与各种测试工具之间的交互，实现更先进的自动化测试能力。

论文收集的软件测试生成主题大多基于多代理系统。研究[[140](https://arxiv.org/html/2408.02479v1#bib.bib140)]评估了 LLMs 在生成高质量测试用例方面的有效性，并识别了它们的局限性。它提出了一种新型的多代理框架，称为 TestChain。论文评估了 StarChat、CodeLlama、GPT-3.5 和 GPT-4 在 HumanEval 和 LeetCode-hard 数据集上的表现。实验结果显示，使用 GPT-4 的 TestChain 框架在 LeetCode-hard 数据集上达到了 71.79%的准确率，比基线方法提高了 13.84%。在 HumanEval 数据集上，TestChain 与 GPT-4 达到了 90.24%的准确率。TestChain 框架设计了生成多样化测试输入的代理，使用 ReAct 格式对话链将输入映射到输出，并与 Python 解释器互动以获得准确的测试输出。

LLM 基础代理还可以应用于用户验收测试（UAT），[[141](https://arxiv.org/html/2408.02479v1#bib.bib141)]旨在通过提出一个名为 XUAT-Copilot 的多代理协作系统来增强微信支付 UAT 过程的自动化，该系统使用 LLM 自动生成测试脚本。该研究评估了 XUAT-Copilot 在微信支付 UAT 系统的 450 个测试用例上的表现，将其与单代理系统和没有反射组件的变体进行了比较。实验结果显示，XUAT-Copilot 的 Pass@1 率为 88.55%，而单代理系统为 22.65%，没有反射组件的变体为 81.96%，Complete@1 率为 93.03%。XUAT-Copilot 采用了多代理协作框架，包括行动规划、状态检查和参数选择代理，并使用了先进的提示技术。XUAT-Copilot 展示了 LLM 在自动化 UAT 测试脚本生成中的潜力和可行性。

### VIII-C 分析

![参考说明](img/9ff544184ea657d709183975b3a68df2.png)

图 7：LLM 基础代理[[141](https://arxiv.org/html/2408.02479v1#bib.bib141)]与 LLM[[136](https://arxiv.org/html/2408.02479v1#bib.bib136)]在软件测试生成中的比较框架说明

相比之下，LLM 在单任务实现中表现优异，通过提示工程和少量学习等技术生成高质量测试用例。随着 LLM 能力的提高，相关研究数量也在增加。另一方面，LLM 基础代理通过多代理协作系统，将任务分解为专门处理，从而通过迭代优化和反馈显著提高测试生成和执行的效果和效率。考虑到成本，使用 LLM 进行测试生成已经足够且比使用 LLM 基础代理更具成本效益。然而，如果特定模型表现不佳，可能会影响整个系统的性能。

单个 LLM 可能在处理复杂的多步骤任务时遇到困难。例如，在高覆盖率测试生成中，LLMs 可能需要更复杂的提示和后处理步骤来实现期望的结果。此外，生成结果的质量在很大程度上依赖于提示设计和质量。对于需要精细控制和持续优化的任务，单个 LLM 可能难以应对。如图 Figure.LABEL:testGen 所示，LLM 框架使用 [[136](https://arxiv.org/html/2408.02479v1#bib.bib136)] 作为示例来展示 LLMs 在模糊测试中的使用，提示将通过给定的代码片段（模糊输入）进行优化，并由 LLM 再次选择，以选择未来生成的最佳提示。整体框架缺乏自主性，左侧的 LLM 基于代理 [[141](https://arxiv.org/html/2408.02479v1#bib.bib141)] 框架弥补了这一缺口，并能够感知 UI 并与技能库进行操作。操作代理将接收由检查代理报告的任何错误，并进行自我反思以自主改进过程。然而，正如前面讨论的，仅为软件测试生成任务构建 LLM 基于的代理框架是“过度设计”，因此收集的 LLM 基于的代理系统的论文通常集中于通过生成测试用例或 bug 回放系统进行程序修复，如图 Figure.LABEL:testGen 所示，LLM 基于的代理框架实际上用于自动测试微信支付系统。

### VIII-D 基准测试

在软件测试生成任务中，LLMs 使用的数据集 Defects4J 用于评估 bug 复现和程序修复技术。其他公共数据集如 ReCDroid、ANDROR2+ 和 Themis 主要用于评估移动应用程序的 bug 复现和安全测试生成，特别是针对 Android 平台。GCC、Clang、Go 工具链、Java 编译器（javac）和 Qiskit 涉及了针对各种编程语言和工具链的模糊测试数据集，旨在评估多语言环境下模糊测试的有效性。TrickyBugs 和 EvalPlus 是包含复杂 bug 场景的数据集，用于评估生成测试用例的精确度和召回率，由 CODAMOSA 评估的基准应用程序用于评估基于覆盖率的测试生成工具的有效性。

在 LLM 基础代理研究中使用的数据集也相当常见，HumanEval、MBPP 和 LeetCode-hard 主要用于评估代码生成和测试生成的准确性和覆盖范围，涉及各种编程问题和挑战，这些问题在前面的章节中经常出现。像 Codeflaws、QuixBugs 和 ConDefects 这样的数据集是为了使 LLM 熟悉错误的代码和程序，包含多个程序错误和缺陷，并用于评估自动调试和错误修复的效果。一个独特的数据集是 WeChat Pay UAT 系统，包括实际应用中的用户接受测试用例，用于评估多代理系统在用户接受测试中的性能，特别关注微信的安全系统。

总体来说，用于 LLM 基础的代理研究的数据集更广泛，涵盖了各种编程问题和挑战，而 LLM 研究则更专注于实际生成任务，如在 Android 平台上的错误重现和多语言环境中的模糊测试。这是因为 LLM 基础的代理不仅关注生成测试用例和代码的质量，还评估多代理系统的协作效果和迭代优化能力，因此基准测试还包括用于评估框架性能的数据集。例如，AgentCoder [[82](https://arxiv.org/html/2408.02479v1#bib.bib82)] 通过多代理协作提高了测试生成和执行的效率和准确性，考虑了定性和定量评估，并使用 MBPP、HummanEval 进行评估，对 LLM 基础的代理的研究更强调通过定性评估和用户反馈来验证系统的有效性。

### VIII-E 评估指标

如表 [IX](https://arxiv.org/html/2408.02479v1#S8.T9 "TABLE IX ‣ VIII-E Evaluation Metrics ‣ VIII Software Test Generation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future") 所示，LLMs 研究主要利用传统的定量指标，如缺陷复现率、代码覆盖率、精度和召回率，这些指标直接反映了测试生成的有效性和质量。相比之下，LLM-Based 代理研究不仅关注定量指标，还引入了定性评估，如通过对话交互的改进和多代理系统的协同效果。这种多样化的评估方法提供了对系统实际应用效果的更全面反映。从任务角度来看，LLMs 更倾向于单一任务处理，如生成测试集并考虑生成测试集的覆盖范围。然而，由于代理框架的扩展，基于 LLM 的代理通常倾向于使用生成的测试集来评估是否能够发现漏洞，从而实现更理想的实用性。从设计角度来看，LLM 系统依赖于提示工程和模型自身的生成能力，其评估指标主要集中在模型输出的质量和有效性上，同时也包括系统内的协同效果和效率，如通过多代理协作提高 Pass@1 和 Complete@1 率。总体而言，LLMs 更适合于特定任务的快速测试生成和评估，评估指标直接反映生成的有效性和质量。LLM-Based 代理在处理复杂和多样化任务方面表现出色，通过多代理协作和迭代优化实现更高的系统效率和有效性。

表 IX：软件测试生成中的评估指标

| 参考文献 | 基准测试 | 评估指标 | 代理 |
| --- | --- | --- | --- |

|

&#124; [[132](https://arxiv.org/html/2408.02479v1#bib.bib132)] &#124;

|

&#124; 26 个库和 55 个 &#124;

&#124; 应用程序与 &#124;

&#124; 已知漏洞 &#124;

|

&#124; 应用程序数量 &#124;

&#124; 成功生成的安全测试 &#124;

&#124; 测试的数量 &#124;

&#124; 演示漏洞。 &#124;

| 否 |
| --- |
| [[134](https://arxiv.org/html/2408.02479v1#bib.bib134)] |

&#124; ReCDroid, ANDROR2+ &#124;

&#124; Themis 实证研究数据集 &#124;

|

&#124; S2R 实体提取的准确性。 &#124;

&#124; 缺陷的可重复性。 &#124;

&#124; 运行效率。 &#124;

&#124; 用户满意度。 &#124;

| 否 |
| --- |

|

&#124; [[135](https://arxiv.org/html/2408.02479v1#bib.bib135)] &#124;

| Defects4J, GHRB |
| --- |

&#124; 缺陷复现率。 &#124;

&#124; 精度和召回率。 &#124;

&#124; 执行时间。 &#124;

&#124; 开发者努力。 &#124;

| 否 |
| --- |

|

&#124; [[136](https://arxiv.org/html/2408.02479v1#bib.bib136)] &#124;

|

&#124; GCC 和 Clang. &#124;

&#124; CVC5 和 Z3. &#124;

&#124; Go 工具链. &#124;

&#124; Java 编译器 (javac). &#124;

&#124; Qiskit. &#124;

|

&#124; 代码覆盖率. &#124;

&#124; 有效性率. &#124;

&#124; 命中率. &#124;

&#124; 检测到的缺陷. &#124;

| 不 |
| --- |

|

&#124; [[137](https://arxiv.org/html/2408.02479v1#bib.bib137)] &#124;

|

&#124; 来自 26 个的 897 个焦点方法 &#124;

&#124; 广泛使用的开源 &#124;

&#124; Python 项目. &#124;

|

&#124; 通过率@1. &#124;

&#124; FM Call@1. &#124;

&#124; 正确@1. &#124;

&#124; 行和分支覆盖率. &#124;

| 不 |
| --- |

|

&#124; [[139](https://arxiv.org/html/2408.02479v1#bib.bib139)] &#124;

|

&#124; TrickyBugs &#124;

&#124; EvalPlus 数据集. &#124;

|

&#124; 召回率. &#124;

&#124; 精确度. &#124;

&#124; F1 分数. &#124;

| 不 |
| --- |

|

&#124; [[138](https://arxiv.org/html/2408.02479v1#bib.bib138)] &#124;

|

&#124; 基准测试应用程序最初 &#124;

&#124; 用于评估 CODAMOSA. &#124;

|

&#124; 行覆盖率. &#124;

&#124; 分支覆盖率. &#124;

&#124; 行 + 分支覆盖率. &#124;

| 不 |
| --- |

|

&#124; [[82](https://arxiv.org/html/2408.02479v1#bib.bib82)] &#124;

|

&#124; HumanEval. &#124;

&#124; MBPP. &#124;

&#124; HumanEval-ET. &#124;

&#124; MBPP-ET. &#124;

| 通过率@1 | 是 |
| --- | --- |

|

&#124; [[106](https://arxiv.org/html/2408.02479v1#bib.bib106)] &#124;

| 未指定 |
| --- |

&#124; 通过定性改进 &#124;

&#124; 对话交互. &#124;

| 是 |
| --- |

|

&#124; [[140](https://arxiv.org/html/2408.02479v1#bib.bib140)] &#124;

|

&#124; HumanEval. &#124;

&#124; LeetCode 难度. &#124;

|

&#124; 准确度. &#124;

&#124; 行覆盖率 (Line Cov). &#124;

&#124; 带有缺陷的代码 (CwB). &#124;

| 是 |
| --- |

|

&#124; [[142](https://arxiv.org/html/2408.02479v1#bib.bib142)] &#124;

|

&#124; Codeflaws. &#124;

&#124; QuixBugs. &#124;

&#124; ConDefects. &#124;

|

&#124; 正确补丁数量. &#124;

&#124; 合理补丁数量. &#124;

&#124; 正确率. &#124;

| 是 |
| --- |

|

&#124; [[141](https://arxiv.org/html/2408.02479v1#bib.bib141)] &#124;

|

&#124; 来自的 450 个测试用例 &#124;

&#124; 微信支付 UAT 系统 &#124;

|

&#124; 通过率@1. &#124;

&#124; 完成@1. &#124;

| 是 |
| --- |

## IX 软件安全与维护

在软件工程中，软件安全和维护是 LLMs 应用的热门领域，主要旨在通过现有技术提升软件系统的安全性和稳定性，以满足用户和开发者的需求。这些模型提供了有前景的漏洞检测和修复方法，同时还能实现自动化安全测试和创新的维护过程。LLMs 在软件安全和维护中的应用包括多个方面，如漏洞检测、自动修复、渗透测试和系统稳健性评估。与传统方法相比，LLMs 利用自然语言处理和生成技术来理解和生成复杂的代码和安全策略，从而实现检测和修复任务的自动化。例如，LLMs 可以通过分析代码结构和上下文信息准确识别潜在的漏洞，并生成相应的修复建议，从而提高漏洞恢复的效率和准确性。

此外，LLMs 不仅在漏洞检测中展现出强大的能力，还在渗透测试和安全评估等任务中发挥作用。自动化渗透测试工具，如 PENTESTGPT [[143](https://arxiv.org/html/2408.02479v1#bib.bib143)]，LLMs 在评估系统稳健性方面也展现了显著的优势，通过模拟各种攻击场景来评估系统在不同条件下的表现，帮助开发者更好地识别和解决潜在的安全问题。基于 LLM 的智能代理在软件安全和维护中的研究也在不断增长，这些智能代理能够执行复杂的代码生成和漏洞修复任务，并具备自我学习和优化能力，以应对动态开发环境中遇到的问题。工具如 RITFIS [[144](https://arxiv.org/html/2408.02479v1#bib.bib144)]和 NAVRepair [[145](https://arxiv.org/html/2408.02479v1#bib.bib145)]已展示出通过使用基于 LLM 的代理提高程序修复的精准度和效率的潜力。

### IX-A LLMs 任务

在软件安全和维护领域，关于 LLMs 的研究可以分为三个主要领域：漏洞检测、自动修复和渗透测试，以及一些评估研究。在这些领域中收集的论文展示了 LLMs 的多样化应用和潜力。

#### IX-A1 程序漏洞

在漏洞检测领域，研究人员已经对 LLM 进行了微调，以提高源代码漏洞检测的准确性。[[146](https://arxiv.org/html/2408.02479v1#bib.bib146)] 旨在研究将 LLM 应用于源代码漏洞检测任务的潜力，并确定 CodeBERT 类模型的性能限制是否由于其有限的容量和代码理解能力。该研究对 WizardCoder 模型（StarCoder 的改进版）进行了微调，并将其性能与 ContraBERT 模型在平衡和不平衡数据集上进行了比较。实验结果显示，WizardCoder 在 ROC AUC 和 F1 分数上都优于 ContraBERT，显著提高了 Java 函数漏洞检测的性能，通过将 ROC AUC 从 CodeBERT 的 0.66 提升至 0.69，达到了当时的最先进水平。

有研究主要探讨了纯 LLM 在漏洞检测中的应用，揭示了当前的挑战。[[147](https://arxiv.org/html/2408.02479v1#bib.bib147)] 仅评估了 ChatGPT 和 GPT-3 模型在检测 Java 代码中的漏洞的性能，该研究将 text-davinci-003（GPT-3）和 gpt-3.5-turbo 与基准虚拟分类器进行了比较，涉及二分类和多标签分类任务。实验结果显示，虽然 text-davinci-003 和 gpt-3.5-turbo 在二分类任务中具有较高的准确率和召回率，但它们的 AUC（曲线下面积）得分仅为 0.51，表明性能与随机猜测相当。在多标签分类任务中，GPT-3.5-turbo 和 text-davinci-003 在整体准确率和 F1 分数上并未显著优于基准虚拟分类器。这些发现表明，早期的模型如 GPT-3 在实际漏洞检测任务中的能力有限，建议需要进一步研究和模型优化以提高其在现实应用中的表现，微调和优化 LLM 可以显著提升其在源代码漏洞检测中的性能。然而，这些模型在实际应用中仍面临许多挑战，需要进一步的研究和技术改进，以增强其在现实世界中的有效性和可靠性。

在后期，[[148](https://arxiv.org/html/2408.02479v1#bib.bib148)] 介绍了一种将复杂代码结构直接融入模型学习过程的方法，GRACE 框架结合了图结构信息和上下文学习，使用代码属性图（CPGs）表示代码结构信息。通过整合代码的语义、句法和词汇相似性，GRACE 框架解决了基于文本的 LLM 分析的局限性，提高了漏洞检测任务的精确率和召回率。研究利用了三个漏洞数据集，相比于基线模型，F1 得分提高了 28.65%，一个重要的漏洞检测方面是提升 LLM 在代码安全任务中的性能。[[149](https://arxiv.org/html/2408.02479v1#bib.bib149)] 对 LLMs 进行了针对特定任务的微调，并与现有模型如 ContraBERT 进行了性能评估。研究人员进行了大量实验，以确定最佳模型架构、训练超参数和损失函数，从而优化漏洞检测任务中的性能。研究主要集中在 WizardCoder 和 ContraBERT，通过在平衡和不平衡数据集上的比较来验证它们的性能，并开发了一种有效的批量打包策略，提高了训练速度。结果表明，通过适当的微调和优化，LLMs 可以超越最先进的模型，从而有助于更强健和安全的软件开发实践。

尽管已经开发了许多模型，但仍然需要调查它们的实际有效性。[[150](https://arxiv.org/html/2408.02479v1#bib.bib150)] 探讨了代码语言模型（code LMs）在检测软件漏洞方面的有效性，并识别了现有漏洞数据集和基准中的重大缺陷。研究人员开发了一个新的数据集，称为 PRIMEVUL，并使用它进行了实验，他们将 PRIMEVUL 与现有基准如 BigVul 进行了比较，以评估多个代码 LMs，包括最先进的基础模型如 GPT-3.5 和 GPT-4，采用了各种训练技术和评估指标。结果揭示了现有基准显著高估了代码 LMs 的性能。例如，一个最先进的 7B 模型在 BigVul 上的 F1 得分为 68.26%，但在 PRIMEVUL 上的得分仅为 3.09%，突显了当前代码语言模型的性能与漏洞检测实际需求之间的差距。

#### IX-A2 自动化程序修复

在软件安全和维护领域，LLMs 不仅被应用于漏洞检测，还被广泛用于自动化程序修复。一项研究提出了使用回译翻译（RTT）进行自动化程序修复的方法，研究人员将缺陷代码翻译成另一种语言，然后再翻译回原语言以生成潜在修补程序。该研究使用了各种语言模型和基准测试来评估 RTT 在自动化程序修复（APR）中的表现。实验探讨了 RTT 在使用编程语言作为中间表示时的表现，使用自然语言（英语）作为中间表示时的表现，以及 RTT 生成的修补程序中可以观察到的定性趋势。实验中使用了三种测量标准和八种模型，结果显示 RTT 方法在多个基准测试中取得了显著的修复效果，特别是在编译和可行性方面表现出色 [[151](https://arxiv.org/html/2408.02479v1#bib.bib151)]。类似地，在自动化程序修复中，[[145](https://arxiv.org/html/2408.02479v1#bib.bib145)] 引入了几种创新方法。例如，NAVRepair 专门针对 C/C++ 代码漏洞，通过结合节点类型信息和错误类型。由于 C/C++ 中独特的指针操作和内存管理问题，这种语言具有复杂性。该框架使用抽象语法树（ASTs）提取节点类型信息，并将其与 CWE 派生的漏洞模板结合，生成有针对性的修复建议。研究评估了 NAVRepair 在几种流行的 LLMs（ChatGPT、DeepSeek Coder 和 Magicoder）上的表现，以展示其在提高代码漏洞修复性能方面的有效性。结果显示，NAVRepair 在 C/C++ 程序修复任务中达到了最先进的性能，相比现有方法提高了 26% 的修复准确性。

为了解决现有针对 LLM（大语言模型）程序修复方法的两个主要局限性：缺乏对代码更改逻辑的推理以及与大规模数据集微调相关的高计算成本。[[152](https://arxiv.org/html/2408.02479v1#bib.bib152)] 引入了 MOREPAIR 框架，该框架通过同时优化语法代码转换和代码更改的逻辑推理，提升了 LLM 在自动化程序修复（APR）中的表现。该研究采用了提高微调效率的技术，例如 QLoRA（量化低秩适应）[[153](https://arxiv.org/html/2408.02479v1#bib.bib153)]以减少内存需求，以及 NEFTune（噪声嵌入微调）[[154](https://arxiv.org/html/2408.02479v1#bib.bib154)]以防止微调过程中的过拟合。实验对 MOREPAIR 在四个不同规模和架构的开源 LLM（CodeLlama-13B、CodeLlama-7B、StarChat-alpha 和 Mistral-7B）进行了评估，使用了两个基准，evalrepair-C++和 EvalRepair-Java。结果表明，CodeLlama 在 evalrepair-C++和 EvalRepair-Java 的前 10 个修复建议中的表现分别提高了 11%和 8%。另一项研究介绍了 PyDex 系统，该系统使用 LLM 自动修复入门 Python 编程作业中的语法和语义错误，结合了多模态提示和迭代查询方法来生成修复候选，并利用少量学习提高修复准确性。PyDex 在 286 个真实学生程序上进行了评估，并与三个基线进行了比较。结果显示，与现有基线相比，PyDex 显著提高了修复率和效果[[155](https://arxiv.org/html/2408.02479v1#bib.bib155)]。

[[156](https://arxiv.org/html/2408.02479v1#bib.bib156)] 引入了一种名为 RING 的新系统，该系统利用大型语言模型（LLMCs）在六种编程语言中执行多语言程序修复。RING 采用了一种最小化定制工作量的提示策略，包括三个阶段：故障定位、代码转换和候选排序。结果显示，RING 在 Python 中尤其有效，首次尝试成功修复了 94%的错误。该研究还引入了一个新的 PowerShell 命令修复数据集，为研究社区提供了宝贵的资源，这项研究表明，人工智能驱动的自动化使程序修复更加高效和可扩展。另一项研究，[[157](https://arxiv.org/html/2408.02479v1#bib.bib157)] 进行了对函数级自动程序修复的全面调查，介绍了一种新的基于 LLM 的 APR 技术，称为 SRepair。SRepair 利用双 LLM 框架来增强修复性能，SRepair 框架结合了修复建议模型和补丁生成模型。它使用链式思维根据辅助修复相关信息生成自然语言修复建议，然后利用这些建议生成修复后的函数。结果表明，SRepair 在 Defects4J 数据集上优于现有的 APR 技术，修复了 300 个单函数错误，较之前的技术提高了至少 85%。这项研究证明了双 LLM 框架在函数级修复中的有效性，并首次实现了多函数错误修复，突显了 LLM 在程序修复中的巨大潜力。通过扩展 APR 的范围，SRepair 为 LLM 在实际软件开发和评估中的应用铺平了道路。

#### IX-A3 渗透测试

LLMs 也可以应用于渗透测试领域，在那里它们用于提高自动化渗透测试的效率和效果。尽管不像漏洞检测和自动修复那样频繁研究，但这篇综述包括了两篇相关论文。[[143](https://arxiv.org/html/2408.02479v1#bib.bib143)] 研究了基于 LLM 的自动化渗透测试工具 PENTESTGPT 的开发和评估。这项研究的主要目的是评估 LLM 在实际渗透测试任务中的表现，并解决渗透测试过程中上下文丢失的问题，论文介绍了 PENTESTGPT 的三个自我交互模块（推理、生成和解析），并提供了基于涉及 13 个目标和 182 个子任务的基准的实证研究。它比较了 GPT-3.5、GPT-4 和 Bard 的渗透测试性能。实验结果表明，PENTESTGPT 的任务完成率比 GPT-3.5 高出 228.6%，比 GPT-4 高出 58.6%，这项研究展示了 LLM 在自动化渗透测试中的潜力，有助于识别和解决安全漏洞，从而提升软件系统的安全性和鲁棒性。

一篇类似的研究论文探讨了生成式 AI 在渗透测试中的应用。[[158](https://arxiv.org/html/2408.02479v1#bib.bib158)] 评估了使用生成式 AI 工具（特别是 ChatGPT 3.5）在渗透测试中的有效性、挑战和潜在后果。通过实际应用实验，研究在 VulnHub 上的一个易受攻击的机器上进行了五阶段渗透测试（侦察、扫描、漏洞评估、利用和报告），将 Shell_GPT (sgpt) 与 ChatGPT 的 API 结合，自动化渗透测试过程中的指导。实验结果表明，生成式 AI 工具能够显著加快渗透测试过程，并提供准确和有用的命令，提高测试效率和效果。该研究指出，需要考虑潜在的风险和意外后果，强调了负责任使用和人工监督的重要性。评估系统的鲁棒性也是开发中的关键部分，LLMs 被用来开发和评估新的测试框架，以检测和改进智能软件系统的鲁棒性。[[144](https://arxiv.org/html/2408.02479v1#bib.bib144)] 介绍了一个名为 RITFIS 的鲁棒输入测试框架，旨在评估基于 LLM 的智能软件对自然语言输入的鲁棒性。该研究将 17 种现有的 DNN 测试方法适配到 LLM 场景，并在多个数据集上进行实证验证，以突出 LLM 软件当前的鲁棒性缺陷和局限性。研究表明，RITFIS 能够有效评估 LLM 软件的鲁棒性，并揭示其处理复杂自然语言输入的漏洞。这项研究强调了对基于 LLM 的智能软件进行鲁棒性测试的重要性，并提供了改进测试方法的方向，以提高实际应用中的可靠性和安全性。

### IX-B 基于 LLM 的代理任务

基于 LLM 的智能体主要应用于自主决策、任务特定优化和多智能体协作等领域，这些框架展示了其在主动防御中的强大潜力。[[159](https://arxiv.org/html/2408.02479v1#bib.bib159)] 旨在解决现有调试方法的局限性，这些方法将生成的程序视为不可分割的实体。通过将程序划分为基本块，并基于任务描述验证每个块的正确性，提出的 LDB（大型语言模型调试器）提供了一个更详细和有效的调试工具，更 closely 反映了人工调试实践。该研究的实验涵盖了在多个基准测试上测试 LDB，并与没有调试器的基线模型以及使用传统调试方法（带解释和跟踪的自我调试）进行比较。LDB 在 HumanEval 基准测试上的准确率从基线的 73.8%提高到 82.9%，提高了 9.1%。在漏洞检测领域，研究人员通过将基于角色的访问控制（RBAC）实践与复杂代码结构的深度学习相结合，提高了检测准确性。

[[160](https://arxiv.org/html/2408.02479v1#bib.bib160)] 解决了自动和适当地修复智能合约中的访问控制（AC）漏洞的问题。本文的创新在于将挖掘的 RBAC 实践与 LLMs 结合，创建了一个上下文感知的访问控制漏洞修复框架。该模型主要使用 GPT-4，并通过一种新方法称为 ACFIX 进行增强，ACFIX 从现有智能合约中挖掘常见的 RBAC 实践，并使用多代理辩论（MAD）机制，通过生成器和验证器代理之间的辩论验证生成的补丁以确保正确性。实验结果表明，ACFIX 成功修复了 94.92% 的访问控制漏洞，显著优于基线 GPT-4 的 52.54%。在智能合约的另一个应用中 [[161](https://arxiv.org/html/2408.02479v1#bib.bib161)]，本文介绍了一个两阶段对抗框架 GPTLENS，通过生成和区分阶段提高了漏洞检测准确性。GPTLENS 在检测智能合约漏洞方面取得了 76.9% 的成功率，优于传统方法的 38.5% 成功率。另一项研究 [[109](https://arxiv.org/html/2408.02479v1#bib.bib109)] 研究了使用 GPT-4 自动利用已披露但未修补的漏洞，实验表明，当提供 CVE 描述时，基于 LLM 的代理在利用漏洞方面取得了 87% 的成功率。最后，另一项基于 LLM 的应用是在渗透测试中 [[107](https://arxiv.org/html/2408.02479v1#bib.bib107)]，利用 GPT-3.5 协助渗透测试人员，通过自动化高层次任务规划和低层次漏洞发现，增强了渗透测试能力。实验展示了渗透测试多个阶段的成功自动化，包括高层次策略制定和低层次漏洞发现，展示了 LLMs 在渗透测试中的有效性。

在多代理协作的软件修复领域，[[162](https://arxiv.org/html/2408.02479v1#bib.bib162)] 提出了一个双代理框架，通过迭代提示优化和多代理协作来提升声明性规范修复的自动化和准确性。研究者比较了基于 LLM 的修复管道与几种最先进的 Alloy APR 技术（ARepair、ICEBAR、BeAFix 和 ATR）的有效性。结果表明，该框架在 Alloy4Fun 基准测试中修复了 231 个缺陷，超越了传统工具修复的 278 个缺陷。在 [[142](https://arxiv.org/html/2408.02479v1#bib.bib142)] 中，开发并评估了一个名为 FixAgent 的自动调试框架，该框架通过基于 LLM 的多代理系统改进了故障定位、修复生成和错误分析。尽管这项研究主要集中在自动调试上，涉及了故障定位和自动程序修复（APR）等元素，但它与测试生成，特别是在测试错误修复的验证阶段，有交集。研究评估了 FixAgent 在 Codeflaws、QuixBugs 和 ConDefects 数据集上的表现，并与 16 种基线方法进行比较，包括最先进的 APR 工具和 LLM。实验结果显示，FixAgent 在 QuixBugs 数据集中修复了 79 个错误中的 78 个，包括 9 个之前未修复的错误。在 Codeflaws 数据集中，FixAgent 修复了 2780 个缺陷中的 3982 个，正确率为 96.5%。该框架包括负责定位、修复和分析任务的专用代理，并采用了橡皮鸭调试原则。FixAgent 展示了 LLM 在自动调试中的强大能力，提高了现有 APR 工具和 LLM 的性能，可以被视为基于 LLM 的代理中的最先进框架。

[[46](https://arxiv.org/html/2408.02479v1#bib.bib46)] 介绍了一个名为 RepairAgent 的自动化程序修复代理，该代理可以动态生成提示并整合工具来自动修复软件错误。研究者还讨论了当前基于 LLM 的修复技术的局限性，这些技术通常涉及固定的提示或反馈循环，这些方法无法让模型全面了解错误或代码。RepairAgent 是一个基于 LLM 的代理，旨在交替收集有关错误的信息、收集修复材料并验证修复，类似于人类开发人员修复错误的方式。RepairAgent 在 Defects4J 基准测试中修复了 186 个错误，其中 164 个被正确修复，优于现有的修复技术，达到了最先进的性能。

在软件安全领域，研究人员将 LLM 和安全工程模型相结合，以提高安全分析和设计过程。[[163](https://arxiv.org/html/2408.02479v1#bib.bib163)]旨在提出一种复杂的混合策略，以确保软件系统的可靠性和安全性，这涉及一个概念指导的方法，其中基于 LLM 的代理与系统模型图进行交互，以执行与安全分析相关的任务。[[108](https://arxiv.org/html/2408.02479v1#bib.bib108)]介绍了 TrustLLM 框架，通过将 LLM 功能定制为智能合约代码的特定要求，来提高智能合约审计的准确性和可解释性。本文在一个平衡的数据集上进行了实验，该数据集包括 1,734 个正样本和 1,810 个负样本，比较了 TrustLLM 与其他模型，如 CodeBERT、GraphCodeBERT 以及几种版本的 GPT 和 CodeLlama。TrustLLM 取得了 91.21%的 F1 得分和 91.11%的准确率，优于其他模型。除了软件级安全设计，LLM 还可以集成到自动驾驶系统中。[[164](https://arxiv.org/html/2408.02479v1#bib.bib164)]这一点已经在[IV](https://arxiv.org/html/2408.02479v1#S4 "IV Requirement Engineering and and Documentation ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")中讨论过。

### IX-C 分析

总体而言，基于 LLM 的代理代表了软件安全和维护领域的重大创新进展，展示了各方面的改进。基于 LLM 的代理通过多代理协作和运行时信息跟踪来帮助调试任务，相较于传统的 LLM 方法，后者通常依赖于固定的提示或反馈循环来调试给定的代码片段或程序。在漏洞检测中，基于 LLM 的代理结合了 RBAC 实践和复杂代码结构的深入学习，以提高漏洞检测的准确性和效率，而传统的 LLM 方法通常依赖于大量的人工干预和详细的指导来处理任务。基于 LLM 的代理还通过自动化高层任务规划和低层漏洞探索，在渗透测试中表现出有效性，从而增强了渗透测试能力。相比之下，传统的 LLM 方法更适合被动检测和分析，缺乏主动测试和防御能力。

![参考标题](img/a70990c7a4ccd7dbc8c6f7d3a8c7166f.png)

图 8：LLM-based Agent [[46](https://arxiv.org/html/2408.02479v1#bib.bib46)] 与 LLM [[152](https://arxiv.org/html/2408.02479v1#bib.bib152)] 在软件安全和维护中的比较框架示意图

从自动化的角度来看，基于 LLM 的智能体通过多智能体框架和动态分析工具实现软件错误的检测和修复，从而提高了修复过程的自动化和准确性。传统的 LLM 方法在各种维护或调试任务中也表现良好，但在修复过程中通常缺乏自主决策和动态调整能力。在软件安全方面，智能体通过结合 LLM 和安全工程模型变得更加灵活，以改善安全分析和设计过程，从而增强软件系统的可靠性和安全性。当仅依靠 LLM 处理安全任务时，通常依赖于静态分析，缺乏适应性和优化能力。如图所示。[8](https://arxiv.org/html/2408.02479v1#S9.F8 "Figure 8 ‣ IX-C Analysis ‣ IX Software Security and Maintenance ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")，使用 MOREPAIR [[152](https://arxiv.org/html/2408.02479v1#bib.bib152)] 进行 LLM 对比，使用 RepairAgent [[46](https://arxiv.org/html/2408.02479v1#bib.bib46)] 进行基于 LLM 的智能体对比。LLM 框架利用优化技术（QLoRA，NEFTune）生成修复建议，RepairAgent 在检查过程中利用多个工具，这些工具有助于在修复过程之前提高分析的精度和准确性，这一思路与“行动前推理”非常相似。然后，智能体框架利用状态机和 LLM 进行持续的优化，如果在修复过程中失败，RepairAgent 将进入自我反思阶段，以自主了解原因。

因此，从回顾来看，我们可以说基于 LLM 的智能体在软件安全和维护领域带来了更多的自主性和灵活性。这些改进可以提高任务执行效率和准确性，同时扩展 LLM 在复杂软件工程任务中的应用范围，展示了它们在主动防御、复杂任务处理和满足高可靠性要求方面的强大潜力。

### IX-D 基准测试

在分析 LLM 文献中使用的基准时，有几个公共数据集因其频繁使用和跨不同应用场景的存在而脱颖而出。数据集如 Defects4J、Codeflaws、QuixBugs 和 Common Vulnerability and Exposure (CVE) 数据库通常在漏洞检测和软件安全领域中使用。例如，Defects4J 在 [[46](https://arxiv.org/html/2408.02479v1#bib.bib46)] 和 [[159](https://arxiv.org/html/2408.02479v1#bib.bib159)] 等论文中被广泛使用，以评估自动程序修复工具。类似地，Codeflaws 和 QuixBugs 在 [[142](https://arxiv.org/html/2408.02479v1#bib.bib142)] 等论文中被用来测试调试能力，重点关注通常出现在竞争编程和教育环境中的较小算法问题。这些数据集有效衡量了 LLM 检测漏洞和修改特定代码块的能力。

CVE 是评估 LLM 安全能力的重要基准，它提供了已知漏洞的存储库，允许 LLM 评估其自主检测和利用安全缺陷的能力，从而弥合理论研究与实际网络安全应用之间的差距。另一个值得注意的数据集是 ARepair，使用于 [[162](https://arxiv.org/html/2408.02479v1#bib.bib162)]。该数据集由缺陷规范组成，测试 LLM 理解和修复正式规范的能力。更常见的数据集如 HumanEval 和 MBPP 也经常用于评估 LLM 生成代码的功能正确性。同样，Alloy4Fun 被用来测试 Alloy 框架中声明性规范的修复 [[162](https://arxiv.org/html/2408.02479v1#bib.bib162)]，反映了 LLM 在理解和修复形式语言中的逻辑错误的表现。

专门的数据集如 VulnHub 和 HackTheBox 用于评估 LLM 的渗透测试能力。像 [[107](https://arxiv.org/html/2408.02479v1#bib.bib107)] 这样的论文利用这些环境模拟现实世界的黑客场景，从而评估 LLM 在网络安全中的实际应用。这些基准对于评估基于 LLM 的代理在网络安全环境中的现实有效性至关重要，弥合理论能力与实际应用之间的差距。在智能合约安全的背景下，从 Etherscan 提取的数据集和为 SmartFix 等工具编制的数据集提供了评估 LLM 在区块链应用中识别和修复漏洞能力的基准，强调了去中心化应用的可靠性和安全性。

在比较 LLM 和基于 LLM 的代理研究中使用的基准时，几个关键的相似点和不同点显现出来。两种方法都经常使用像 Defects4J、CVE 和 HumanEval 这样的数据集，突显了它们在评估软件工程任务中的基础作用。然而，基于 LLM 的代理研究通常将这些数据集与像 VulnHub 和 HackTheBox 这样的专门基准结合起来，以测试更具动态性和互动性的能力，特别是在网络安全的背景下。基于 LLM 的代理研究通常更注重实时的自主决策和行动，这在他们选择的基准中得以体现。这些数据集不仅测试代理的知识，还测试他们在现实场景中自主应用这些知识的能力。这与传统的 LLM 研究形成对比，后者通常关注于静态任务，如漏洞修复和代码生成，无需实时互动以及进一步的更改或决策。此外，像 Etherscan 的智能合约数据集这样的专门基准在基于 LLM 的代理研究中的使用，强调了区块链技术的重要性以及在去中心化应用中需要健全的安全措施，这一趋势突显了基于 LLM 的代理在应对软件安全和维护新兴挑战方面的适应性和多样性。这一区别反映了基于 LLM 的代理更广泛和更具互动性的应用场景，同时，公共数据集可能不适用于特别设计的基于 LLM 的代理，因此涌现出大量自收集的基准，提供了更多的灵活性。

### IX-E 评估指标

软件安全和维护中 LLM 的评估指标非常多样。研究人员需要考虑模型或框架的覆盖率、效率和可靠性等多种因素。像成功率和通过率这样的评估指标与 LLM 在不同场景中的表现直接相关。在表格 [X](https://arxiv.org/html/2408.02479v1#S9.T10 "TABLE X ‣ IX-E Evaluation Metrics ‣ IX Software Security and Maintenance ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future") 中，常见的标准如成功率和变化率被频繁使用来评估模型在面对各种输入时的稳健性。时间开销和查询次数用于评估模型在执行特定任务时的效率和资源消耗。此外，ROC AUC、F1 分数和准确率对于评估模型识别漏洞的能力也很重要，尤其是在二分类任务中。在代码修复任务中，像可编译性和合理性这样的指标非常常见，这些指标确保生成的解决方案是正确且可部署的。像 BLEU 和 CodeBLEU 这样的常见标准用于评估生成代码的质量和类人性，这有助于确定模型的能力和性能是否可与人类表现相媲美。此外，领域特定的指标如树编辑距离和测试通过率被用于评估 LLM 在软件工程专业领域中的有效性，这些指标用于应对软件安全和维护带来的局限性。相比之下，虽然 LLM 基于代理也使用类似于 LLM 的评估指标，如成功率，但它们还结合了更多主观的评估指标。这些包括适当性、相关性和充分性，这些都是人工判断的标准。总体而言，代理使用的评估指标往往比 LLM 使用的指标更简单、更易于理解。这可能是因为代理处理高层次任务，例如生成潜在漏洞的成功率和代理调用外部工具的频率，因此它们还需要考虑整体架构的计算和时间开销。

通过比较这些指标，我们可以看到，LLMs 强调单个测试方法的成功率，而基于 LLM 的代理则更注重整体任务完成时间/成本/效果。LLMs 通常使用二元分类指标，如 ROC、AUC 和 F1 分数，而代理则倾向于在生成和验证阶段都强调成功率和准确度，提供全面的评估。对于时间成本和性能，LLMs 主要关注测试方法的执行时间和查询次数，以评估其效率。相比之下，基于 LLM 的代理更注重修复任务的完成时间和 API 调用次数，以确保整体架构的效率和实用性。

表 X：软件安全性和维护中的评估指标

| 参考文献 | 基准测试 | 评估指标 | 代理 |
| --- | --- | --- | --- |

|

&#124; [[144](https://arxiv.org/html/2408.02479v1#bib.bib144)] &#124;

|

&#124; 金融情感分析 &#124;

&#124; 电影评论分析 &#124;

&#124; 新闻分类 &#124;

|

&#124; 成功率、变化率、困惑度、时间开销、查询次数 &#124;

| 否 |
| --- |

|

&#124; [[146](https://arxiv.org/html/2408.02479v1#bib.bib146)] &#124;

|

&#124; CVEfixes &#124;

&#124; 手动策划的数据集 &#124;

&#124; （624 个漏洞跨越 &#124;

&#124; 205 个 Java 项目） &#124;

&#124; VCMatch &#124;

&#124; （10 个热门仓库） &#124;

|

&#124; ROC AUC、F1 分数、准确度、最佳分类、阈值 &#124;

| 否 |
| --- |

|

&#124; [[149](https://arxiv.org/html/2408.02479v1#bib.bib149)] &#124;

|

&#124; CVEfixes &#124;

&#124; 手动策划的数据集 &#124;

&#124; VCMatch &#124;

|

&#124; 精确度、召回率 &#124;

| 否 |
| --- |
| [[143](https://arxiv.org/html/2408.02479v1#bib.bib143)] |

&#124; HackTheBox &#124;

&#124; VulnHub &#124;

|

&#124; 总任务完成度、子任务完成度、任务多样性、挑战 &#124;

&#124; 等级、进度跟踪 &#124;

| 否 |
| --- |

|

&#124; [[151](https://arxiv.org/html/2408.02479v1#bib.bib151)] &#124;

|

&#124; Defects4J v1.2 &#124;

&#124; Defects4J v2.0 &#124;

&#124; QuixBugs &#124;

&#124; HumanEval-Java &#124;

|

&#124; 可编译性、合理性、测试通过率、准确匹配、BLEU &#124;

| 否 |
| --- |
| [[148](https://arxiv.org/html/2408.02479v1#bib.bib148)] |

&#124; Devign &#124;

&#124; Reveal &#124;

&#124; Big-Vul &#124;

|

&#124; F1 分数、准确度、精确度、召回率。 &#124;

| 否 |
| --- |

|

&#124; [[150](https://arxiv.org/html/2408.02479v1#bib.bib150)] &#124;

|

&#124; PRIMEVUL &#124;

&#124; BigVul &#124;

|

&#124; F1 分数、准确度、精确度、召回率、VD-S、成对、评估指标 &#124;

| 否 |
| --- |

|

&#124; [[147](https://arxiv.org/html/2408.02479v1#bib.bib147)] &#124;

|

&#124; 定制的 GitHub 数据集 &#124;

&#124; （308 个二元分类和 &#124;

&#124; 120 个多标签分类） &#124;

|

&#124; 精确度、召回率、F1 分数、AUC、准确度 &#124;

| 否 |
| --- |

|

&#124; [[158](https://arxiv.org/html/2408.02479v1#bib.bib158)] &#124;

|

&#124; VulnHub &#124;

|

&#124; 输出描述 &#124;

| 否 |
| --- |

|

&#124; [[165](https://arxiv.org/html/2408.02479v1#bib.bib165)] &#124;

|

&#124; VulDeePecker &#124;

&#124; SeVC &#124;

|

&#124; 假阳性率，假阴性率，精确度，召回率，F1 分数 &#124;

| 否 |
| --- |
| [[145](https://arxiv.org/html/2408.02479v1#bib.bib145)] | CVEFixes |

&#124; CodeBLEU，树编辑距离，Pass@k &#124;

| 否 |
| --- |

|

&#124; [[152](https://arxiv.org/html/2408.02479v1#bib.bib152)] &#124;

|

&#124; EvalRepair-C++ &#124;

&#124; EvalRepair-Java &#124;

|

&#124; TOP-5 和 TOP-10，修复 &#124;

| 否 |
| --- |
| [[155](https://arxiv.org/html/2408.02479v1#bib.bib155)] |

&#124; 入门级 Python &#124;

&#124; 作业数据集 &#124;

|

&#124; 修复率，标记编辑距离 &#124;

| 否 |
| --- |
| [[156](https://arxiv.org/html/2408.02479v1#bib.bib156)] |

&#124; 多语言数据集 &#124;

&#124; (Excel,Power Fx,Python, &#124;

&#124; JavaScript,C 和 PowerShell) &#124;

| 精确匹配 | 否 |
| --- | --- |

|

&#124; [[157](https://arxiv.org/html/2408.02479v1#bib.bib157)] &#124;

| Defects4J 1.2 和 2.0 |
| --- |

&#124; 合理修补，正确修复 &#124;

| 否 |
| --- |

|

&#124; [[107](https://arxiv.org/html/2408.02479v1#bib.bib107)] &#124;

|

&#124; 易受攻击的虚拟机 &#124;

&#124; (lin.security Linux VM) &#124;

| 成功率 | 是 |
| --- | --- |

|

&#124; [[160](https://arxiv.org/html/2408.02479v1#bib.bib160)] &#124;

| 118 个 AC 漏洞 |
| --- |

&#124; 成功率，基于利用的评估，手动检查 &#124;

&#124; 补丁。 &#124;

| 是 |
| --- |

|

&#124; [[161](https://arxiv.org/html/2408.02479v1#bib.bib161)] &#124;

| 13 个智能合同漏洞 |
| --- |

&#124; 成功率，合同级别，试验级别 &#124;

| 是 |
| --- |

|

&#124; [[142](https://arxiv.org/html/2408.02479v1#bib.bib142)] &#124;

|

&#124; Codeflaws,QuixBugs, &#124;

&#124; ConDefects &#124;

|

&#124; 正确修复的漏洞数量，合理修补的漏洞数量， &#124;

&#124; 生成补丁的正确率 &#124;

| 是 |
| --- |

|

&#124; [[162](https://arxiv.org/html/2408.02479v1#bib.bib162)] &#124;

| ARepair,Alloy4Fun |
| --- |

&#124; Correct@6，运行时和标记使用 &#124;

| 是 |
| --- |

|

&#124; [[163](https://arxiv.org/html/2408.02479v1#bib.bib163)] &#124;

| 系统模型图 |
| --- |

&#124; 准确性，效果，适当性 &#124;

| 是 |
| --- |

|

&#124; [[108](https://arxiv.org/html/2408.02479v1#bib.bib108)] &#124;

|

&#124; 1734 个正样本， &#124;

&#124; 1810 个负样本 &#124;

|

&#124; F1 分数，准确性，一致性 &#124;

| 是 |
| --- |

|

&#124; [[166](https://arxiv.org/html/2408.02479v1#bib.bib166)] &#124;

|

&#124; HumanEval,MBPP, &#124;

&#124; TransCoder &#124;

|

&#124; 准确性，Pass@1 &#124;

| 是 |
| --- |

|

&#124; [[139](https://arxiv.org/html/2408.02479v1#bib.bib139)] &#124;

|

&#124; 13 个 Android 应用 &#124;

&#124; 来自 GitHub &#124;

|

&#124; 召回率，精确度，正确，过拟合，Correct@k &#124;

| 是 |
| --- |

|

&#124; [[164](https://arxiv.org/html/2408.02479v1#bib.bib164)] &#124;

| 系统模型图 |
| --- |

&#124; 相关性，适用性 &#124;

| 是 |
| --- |

|

&#124; [[109](https://arxiv.org/html/2408.02479v1#bib.bib109)] &#124;

| CVE 库中的 15 个漏洞 | 成功率 | 是 |
| --- | --- | --- |

|

&#124; [[46](https://arxiv.org/html/2408.02479v1#bib.bib46)] &#124;

| Defects4J |
| --- |

&#124; 可能的修复措施，正确的修复措施 &#124;

| 是 |
| --- |

## X 讨论

### X-A 实验模型

在第 3-8 节中，我们审查并介绍了最近几年在软件工程中 LLMs 和基于 LLM 的智能代理应用的研究。这些研究有不同的研究方向，我们将它们分成六个子主题进行分类和讨论。随着大型语言模型的发展，成千上万的模型出现在公众视野中，为了更直观地了解大型语言模型在各个领域的应用以及将大型语言模型作为智能代理核心的使用，我们总结了共 117 篇论文，主要讨论了 LLMs 在软件工程领域的使用频率。

通过对 117 篇论文的审阅，我们主要关注作者在实验中使用的模型或框架。这是因为这些论文通常包括在特定领域中测试模型性能，比如评估 LLaMA 在代码生成中的性能。因此，在我们的数据收集过程中，我们还包括了用于比较目的的模型，因为这些模型通常代表了当时各自领域的最新能力。总之，在这 117 篇论文中，我们总共识别出了 79 个独特的大型语言模型。我们利用词云直观地表现了这些模型名称的频率，如图所示[9](https://arxiv.org/html/2408.02479v1#S10.F9 "图 9 ‣ X-A 实验模型 ‣ X 讨论 ‣ 从 LLMs 到基于 LLMs 的智能代理的软件工程：对当前、挑战和未来的调查")。从图中，我们可以观察到，诸如 GPT-3.5、GPT-4、LLaMA2 和 Codex 等模型经常被使用。尽管闭源 LLMs 无法在本地部署或进一步训练，但它们出色的能力使它们成为实验比较或数据增强的常用选择，其中 GPT-4 用于生成额外数据以支持研究模型框架。例如，研究人员可能使用 OpenAI 的 API 生成初始文本，然后使用在本地部署的模型进行进一步处理和优化 [[76](https://arxiv.org/html/2408.02479v1#bib.bib76)] [[122](https://arxiv.org/html/2408.02479v1#bib.bib122)] [[119](https://arxiv.org/html/2408.02479v1#bib.bib119)] [[113](https://arxiv.org/html/2408.02479v1#bib.bib113)]。

因此，不难看出，在过去两年里，使用具有优异性能的一般大型模型来辅助开发或作为衡量标准，在软件工程的垂直领域中逐渐增多。此外，对于一些以前未曾涉及的领域，许多研究人员首先参考模型**ChatGPT**，并在较新的 GPT-4 上进行各种性能实验[[55](https://arxiv.org/html/2408.02479v1#bib.bib55)] [[58](https://arxiv.org/html/2408.02479v1#bib.bib58)] [[64](https://arxiv.org/html/2408.02479v1#bib.bib64)]。这些模型可以集成到更大的系统中，并与其他机器学习模型和工具结合，这些模型可以用于生成自然语言响应，而另一个模型则处理意图识别和对话管理。

![参见说明](img/d7228041e1bad30dab59f63b5f65de54.png)

图 9：实验模型使用词云

尽管词云提供了模型使用频率的粗略概述，但它缺乏详细信息。为了获得更深入的见解，我们结合了分组柱状图和堆叠柱状图，进一步分析了不同子主题中模型的使用情况。相关的柱状图呈现在图[10](https://arxiv.org/html/2408.02479v1#S10.F10 "图 10 ‣ X-A 实验模型 ‣ X 讨论 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前、挑战与未来的调查")中。在分析过程中，我们发现大量模型仅出现过一次。如果将这些模型包括在柱状图中，会使整体表现变得混乱。因此，我们排除了只出现过一次的模型，重点关注了其余模型的多样性。在每个子主题的左侧，我们描绘了 LLM 相关研究中使用的模型，其中 LLM 基于代理的研究使用的模型以红色边框柱突出显示。从图中可以明显看出，在自主学习与决策子主题中，LLM 基于代理研究中使用的模型数量相当高。具体而言，GPT-4 和 GPT-3.5 分别在 18 篇论文中的 10 篇和 15 篇中被使用。在这个子主题中，研究通常使用 GPT-3.5/4 和 LLaMA-2 进行研究和评估。在我们的分析中，我们发现许多关于基于 LLM 的代理的研究评估了代理模仿人类行为和决策或执行一些推理任务的能力[[103](https://arxiv.org/html/2408.02479v1#bib.bib103)] [[111](https://arxiv.org/html/2408.02479v1#bib.bib111)] [[108](https://arxiv.org/html/2408.02479v1#bib.bib108)]。由于这些研究不需要本地部署，它们主要评估了最先进模型在特定方向上的性能，导致 GPT 系列模型的使用频率较高。像[[98](https://arxiv.org/html/2408.02479v1#bib.bib98)] [[36](https://arxiv.org/html/2408.02479v1#bib.bib36)]这样的框架通过调用 GPT-4 API 构建了基于 LLM 的代理，使用口头强化帮助语言代理从错误中学习。由于 GPT 模型的局限性，许多研究也使用 LLaMA 作为代理的 LLM，在生成的数据集上进行微调，以评估知识和能力的出现。总体而言，我们发现，在自主学习与决策子主题中，LLM 基于代理经常在单一任务中使用多个模型进行测试和性能评估，这导致该主题的模型使用频率明显高于其他主题。

![参见标题](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 10：不同子主题中的实验模型使用（REQ 代表“需求工程与文档”，CODE 代表“代码生成与软件开发”，AUTO 代表“自主学习与决策”，DES 代表“软件设计与决策”，SEC 代表“软件安全与维护”）

不仅在自主学习和决策制定子主题中，在其他主题中，我们也观察到 LLM 基于的智能体所使用的模型（由颜色数量表示）的种类相对有限。例如，在需求工程和文档子主题中，仅涉及了 GPT-3.5 和 GPT-4 模型。为了分析这一现象背后的原因，我们需要排除模型只出现一次未被考虑以及智能体研究本身较少的因素。我们认为这主要反映了智能体与大型语言模型之间的集成关系。这两种技术的结合旨在解决大型语言模型在特定任务或方面的局限性。智能体允许研究人员设计更灵活的框架，并将大型语言模型纳入其中。这些模型经过大量数据训练，具有较强的通用性，使其适用于广泛的任务和领域。

因此，研究人员和开发者可以使用同一个模型来解决多个问题，从而减少对各种模型的需求。在代码生成 [[83](https://arxiv.org/html/2408.02479v1#bib.bib83)] [[79](https://arxiv.org/html/2408.02479v1#bib.bib79)]、测试用例生成 [[140](https://arxiv.org/html/2408.02479v1#bib.bib140)] [[142](https://arxiv.org/html/2408.02479v1#bib.bib142)] 和软件安全 [[167](https://arxiv.org/html/2408.02479v1#bib.bib167)] [[159](https://arxiv.org/html/2408.02479v1#bib.bib159)] 方面，已有使用 CodeLlama 的实例。该模型基于 LLaMA 架构进行微调和优化。发布时，它被认为是代码生成和理解任务的最先进模型之一，显示出较其他模型如 Codex 更强的性能和潜力。另一个潜在原因是之前成功的应用和研究成果证明了这些模型的有效性，进一步增强了研究人员对它们的信任和依赖。与在特定领域表现良好的模型相比，在智能体开发中，更倾向于使用通用的大型模型，以确保智能体的核心具有出色的文本理解能力，从而进行进一步的推理、规划和任务执行。从图.[10](https://arxiv.org/html/2408.02479v1#S10.F10 "Figure 10 ‣ X-A Experiment Models ‣ X Discussion ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future") 中我们也可以观察到，代码生成和软件开发领域的研究采用了多种模型，这进一步表明了这一领域受到的广泛关注以及模型在代码生成任务中的出色表现。

![参见标题](img/0c479d443ed78dc33c590ec482504432.png)

图 11: 六个主题中 LLM 和智能体的分布

|  | CODE | REQ | AUTO | DESIGN | SEC | TEST |
| --- | --- | --- | --- | --- | --- | --- |
| CODE | X | 1 | 0 | 2 | 3 | 1 |
| REQ | 1 | X | 1 | 0 | 2 | 0 |
| AUTO | 0 | 1 | X | 6 | 5 | 1 |
| DESIGN | 2 | 0 | 6 | X | 1 | 0 |
| SEC | 3 | 2 | 5 | 1 | X | 2 |
| TEST | 1 | 0 | 1 | 0 | 2 | X |

表 XI：不同主题之间的论文重叠（REQ 表示“需求工程和文档”，CODE 表示“代码生成和软件开发”，AUTO 表示“自主学习和决策”，DES 表示“软件设计和决策”，SEC 表示“软件安全和维护”）

### X-B 主题重叠

图。[11](https://arxiv.org/html/2408.02479v1#S10.F11 "图 11 ‣ X-A 实验模型 ‣ X 讨论 ‣ 从 LLM 到基于 LLM 的软件工程代理：当前挑战和未来展望") 显示了所有收集到的文献在六个主题中的分布。对于 LLM 类型的文献，软件安全和维护主题占比接近 30%，而测试用例生成的比例不到 10%。这一趋势在基于 LLM 的代理文献中也有类似反映。有关使用基于 LLM 的代理来处理需求工程和测试用例生成的研究相对较少。需求工程对于基于 LLM 的代理来说是一个新的领域，而使用整个代理框架来生成测试用例可能被认为是过度的。因此，更多的研究倾向于评估和探索 LLM 在代理框架中带来的变化，例如自主决策能力和软件维护及修复的能力。

表‘[XI](https://arxiv.org/html/2408.02479v1#S10.T11 "TABLE XI ‣ X-A Experiment Models ‣ X Discussion ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future") 展示了涵盖多个主题的论文数量。例如，有五篇论文可以同时归类为软件安全与维护以及自主学习与决策。这两个主题也与其他主题的重叠程度最高，表明 LLMs 和基于 LLM 的代理研究范围广泛，这些任务通常需要整合来自代码生成、设计和测试等多个领域的知识和技术。显著的重叠反映了这些主题与其他领域之间的紧密关系。例如，自主学习和决策通常涉及模型自主学习和优化决策树的能力，这些技术在许多具体的软件工程任务中都有应用。同样，软件安全与维护通常需要结合多种技术来提升安全性，如自动代码生成工具和自动化测试框架 [[71](https://arxiv.org/html/2408.02479v1#bib.bib71)] [[80](https://arxiv.org/html/2408.02479v1#bib.bib80)] [[83](https://arxiv.org/html/2408.02479v1#bib.bib83)] [[102](https://arxiv.org/html/2408.02479v1#bib.bib102)]。文献中的重叠突显了在软件工程中整合不同研究领域的方法和技术的日益需求。例如，确保软件安全不仅依赖于安全措施，还依赖于利用代码生成、自动化测试和设计优化技术。同样，自主学习和决策需要全面考虑需求工程、代码生成和系统设计。此外，这还表明某些技术和方法具有很强的共性。例如，基于 LLM 的代理通过自主学习和决策提升了代码生成、测试自动化和安全分析的能力。这种技术共享促进了软件工程领域内不同领域之间的知识交流和技术传播。

### X-C 基准与指标

如图[12](https://arxiv.org/html/2408.02479v1#A0.F12 "Figure 12 ‣ -A Benchmarks ‣ From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future")所示，它包括了六个主题下常见基准的分布。实际上，使用的基准数据集数量远远超过图中所示的数量。不同的软件工程任务使用各种基准数据集进行评估和测试。例如，在需求工程中，研究人员通常会收集用户故事或需求规格作为数据集[[55](https://arxiv.org/html/2408.02479v1#bib.bib55)] [[63](https://arxiv.org/html/2408.02479v1#bib.bib63)]，这些数据集并不是知名的公共数据集，因此未被纳入统计中。或者，一些研究将他们的数据集指定为“定制的 GitHub 数据集”[[168](https://arxiv.org/html/2408.02479v1#bib.bib168)]。因此，图中所示的基准数据集代表了常用的公共数据集。例如，MBPP 和 HumanEval，在前面的部分中已经介绍过，是使用频率较高的。我们还可以观察到，LLM 和 LLM 基础代理任务中使用的数据集，除了常见的公共数据集外，还存在差异。

例如，FEVER⁷⁷7[`fever.ai/dataset/fever.html`](https://fever.ai/dataset/fever.html) 数据集通常用于与代理相关的研究。在[[35](https://arxiv.org/html/2408.02479v1#bib.bib35)]中，FEVER 数据集用于测试 ExpeL 代理在事实验证任务中的表现。类似地，HotpotQA⁸⁸8[`hotpotqa.github.io/`](https://hotpotqa.github.io/) 数据集也经常用于与代理相关的研究，用于知识密集型推理和问答任务。在处理漏洞修复任务时，LLMs 通常使用 Defects4J⁹⁹9[`github.com/rjust/defects4j`](https://github.com/rjust/defects4j) 基准数据集。该数据集包含来自多个开源 Java 项目的 835 个真实缺陷，分为有缺陷版本和修复版本，通常用于评估自动程序修复技术的有效性。尽管 Defects4J 在 LLM 研究中使用广泛，但在 LLM 基础的代理研究中相对较少使用。我们推测，这可能是因为 Defects4J 主要评估单一代码修复任务，这与 LLM 基础代理的多任务和实时要求并不完全一致。此外，新数据集如 ConDefects 已被引入[[142](https://arxiv.org/html/2408.02479v1#bib.bib142)]，专注于解决数据泄露问题并提供更全面的缺陷定位和修复评估。

如图[13](https://arxiv.org/html/2408.02479v1#A0.F13 "图 13 ‣ -B 评估指标 ‣ 从 LLMs 到 LLM 基础代理在软件工程中的应用：当前挑战和未来的调查")所示，其中包含了 LLM 和 LLM 基础代理的十大评估指标。分析显示，二者使用的评估方法几乎相同。在前面几节中，我们还讨论了对于代理，需要考虑时间和计算资源消耗，这从饼图中可以看出。同时，许多研究集中在 LLMs 的代码生成能力上，因此更多的评估指标涉及生成代码的正确性和精确匹配[[73](https://arxiv.org/html/2408.02479v1#bib.bib73)] [[69](https://arxiv.org/html/2408.02479v1#bib.bib69)] [[30](https://arxiv.org/html/2408.02479v1#bib.bib30)]，但总体而言，LLMs 和 LLM 基础代理在软件工程应用中的评估指标是相似的。

## XI 结论

在本文中，我们对 LLM 及 LLM 基础代理在软件工程中的应用进行了全面的文献综述。我们将软件工程分为六个主题：需求工程和文档编写、代码生成和软件开发、自主学习和决策、软件设计和评估、软件测试生成以及软件安全与维护。对于每个主题，我们分析了任务、基准和评估指标，区分了 LLM 和 LLM 基础代理，并讨论了它们带来的差异和影响。我们进一步分析并讨论了 117 篇收集的论文中的实验模型。此外，我们提供了 LLM 与 LLM 基础代理在数据集和评估指标方面的统计数据和区别。分析显示，LLM 基础代理的出现已经引发了对各种软件工程主题的广泛研究和应用，表现出相对于传统 LLM 在任务、基准和评估指标方面的不同重点。

## 参考文献

+   [1] S. Wang, D. Chollak, D. Movshovitz-Attias, 和 L. Tan, “Bugram: 基于 n-gram 语言模型的错误检测，” 见于第 31 届 IEEE/ACM 国际自动化软件工程大会论文集，第 724–735 页，2016 年。

+   [2] A. Vogelsang 和 M. Borg, “机器学习的需求工程：数据科学家的视角，” 见于 2019 IEEE 第 27 届国际需求工程会议研讨会（REW），（韩国济州），第 245–251 页，2019 年。

+   [3] “Chatgpt: 优化对话的语言模型，” 2022 年 11 月。[在线；访问日期：2024 年 7 月 17 日]。

+   [4] M. Chen, J. Tworek, H. Jun, Q. Yuan, H. P. de Oliveira Pinto, J. Kaplan, H. Edwards, Y. Burda, N. Joseph, G. Brockman, A. Ray, R. Puri, G. Krueger, M. Petrov, H. Khlaaf, G. Sastry, P. Mishkin, B. Chan, S. Gray, N. Ryder, M. Pavlov, A. Power, L. Kaiser, M. Bavarian, C. Winter, P. Tillet, F. P. Such, D. Cummings, M. Plappert, F. Chantzis, E. Barnes, A. Herbert-Voss, W. H. Guss, A. Nichol, A. Paino, N. Tezak, J. Tang, I. Babuschkin, S. Balaji, S. Jain, W. Saunders, C. Hesse, A. N. Carr, J. Leike, J. Achiam, V. Misra, E. Morikawa, A. Radford, M. Knight, M. Brundage, M. Murati, K. Mayer, P. Welinder, B. McGrew, D. Amodei, S. McCandlish, I. Sutskever, 和 W. Zaremba，“评估基于代码的大型语言模型，” arXiv 预印本 arXiv:2107.03374，2021 年。 arXiv:2107.03374 [cs.LG]。

+   [5] N. Jain, S. Vaidyanath, A. Iyer, N. Natarajan, S. Parthasarathy, S. Rajamani, 和 R. Sharma，“Jigsaw: 大型语言模型与程序合成的结合，” 见于第 44 届国际软件工程大会论文集，ICSE ’22，（纽约，NY，美国），页码 1219–1231，计算机协会，2022 年。

+   [6] T. Li, G. Zhang, Q. D. Do, X. Yue, 和 W. Chen，“长上下文的 LLM 在长时间上下文学习中的挑战，” 2024 年。

+   [7] J. Yang, H. Jin, R. Tang, X. Han, Q. Feng, H. Jiang, S. Zhong, B. Yin, 和 X. Hu，“在实践中利用 LLM 的力量：关于 ChatGPT 及其延伸的调查，” 《ACM 知识发现与数据挖掘》, 第 18 卷，2024 年 4 月。

+   [8] A. Fan, B. Gokkaya, M. Harman, M. Lyubarskiy, S. Sengupta, S. Yoo, 和 J. M. Zhang，“大型语言模型在软件工程中的应用：调查与未解问题，” 见于 2023 IEEE/ACM 国际软件工程会议：软件工程的未来（ICSE-FoSE），页码 31–53，2023 年。

+   [9] L. Wang, C. Ma, X. Feng, Z. Zhang, H. Yang, J. Zhang, Z. Chen, J. Tang, X. Chen, Y. Lin, W. X. Zhao, Z. Wei, 和 J. Wen，“基于大型语言模型的自主智能体调查，” 《计算机科学前沿》，第 18 卷，第 6 期，页码 186345–，2024 年。

+   [10] Z. Xi, W. Chen, X. Guo, W. He, Y. Ding, B. Hong, M. Zhang, J. Wang, S. Jin, E. Zhou, R. Zheng, X. Fan, X. Wang, L. Xiong, Y. Zhou, W. Wang, C. Jiang, Y. Zou, X. Liu, Z. Yin, S. Dou, R. Weng, W. Cheng, Q. Zhang, W. Qin, Y. Zheng, X. Qiu, X. Huang, 和 T. Gui，“大型语言模型基础的智能体的崛起和潜力：一项调查，” 2023 年。

+   [11] P. Lewis, E. Perez, A. Piktus, F. Petroni, V. Karpukhin, N. Goyal, H. Küttler, M. Lewis, W.-t. Yih, T. Rocktäschel, S. Riedel, 和 D. Kiela，“针对知识密集型 NLP 任务的检索增强生成，” 见于《神经信息处理系统进展》（H. Larochelle, M. Ranzato, R. Hadsell, M. Balcan, 和 H. Lin 主编），第 33 卷，页码 9459–9474，Curran Associates, Inc.，2020 年。

+   [12] GitHub 公司，“GitHub Copilot: 你的 AI 编程助手。” [`github.com/features/copilot`](https://github.com/features/copilot)，2024 年。[在线; 访问日期：2024 年 7 月 17 日]。

+   [13] S. Russell 和 P. Norvig，《人工智能：现代方法》。皮尔逊教育有限公司，2016 年。

+   [14] N. R. Jennings，“面向代理的软件工程调查，”《知识工程评论》，第 15 卷，第 4 期，第 215–249 页，2000 年。

+   [15] Y. Bisk, A. Holtzman, J. Thomason, J. Andreas, Y. Bengio, J. Chai, M. Lapata, A. Lazaridou, J. May, A. Nisnevich, N. Pinto, 和 J. Turian，“经验奠定语言基础，”2020 年。

+   [16] J. Wei, X. Wang, D. Schuurmans, M. Bosma, F. Xia, E. Chi, Q. V. Le, D. Zhou 等人，“链式思维提示引发大语言模型中的推理，”《神经信息处理系统进展》，第 35 卷，第 24824–24837 页，2022 年。

+   [17] X. Hou, Y. Zhao, Y. Liu, Z. Yang, K. Wang, L. Li, X. Luo, D. Lo, J. Grundy, 和 H. Wang，“大型语言模型在软件工程中的应用：系统文献综述，”2024 年。

+   [18] Z. Zheng, K. Ning, J. Chen, Y. Wang, W. Chen, L. Guo, 和 W. Wang，“理解大型语言模型在软件工程任务中的应用，”2023 年。

+   [19] A. Nguyen-Duc, B. Cabrero-Daniel, A. Przybylek, C. Arora, D. Khanna, T. Herda, U. Rafiq, J. Melegati, E. Guerra, K.-K. Kemell, M. Saari, Z. Zhang, H. Le, T. Quan, 和 P. Abrahamsson，“生成式人工智能在软件工程中的应用——研究议程，”2023 年。

+   [20] W. Ma, S. Liu, Z. Lin, W. Wang, Q. Hu, Y. Liu, C. Zhang, L. Nie, L. Li, 和 Y. Liu，“Lms：理解代码语法和语义用于代码分析，”2024 年。

+   [21] Z. Yang, Z. Sun, T. Z. Yue, P. Devanbu, 和 D. Lo，“大型语言模型在代码中的鲁棒性、安全性、隐私性、可解释性、效率和可用性，”2024 年。

+   [22] Y. Huang, Y. Chen, X. Chen, J. Chen, R. Peng, Z. Tang, J. Huang, F. Xu, 和 Z. Zheng，“生成式软件工程，”2024 年。

+   [23] C. Manning 和 H. Schutze，《统计自然语言处理基础》。MIT 出版社，1999 年。

+   [24] S. Hochreiter 和 J. Schmidhuber，“长短期记忆，”《神经计算》，第 9 卷，第 8 期，第 1735–1780 页，1997 年。

+   [25] S. Hochreiter 和 J. Schmidhuber，“长短期记忆，”《神经计算》，第 9 卷，第 8 期，第 1735–1780 页，1997 年。

+   [26] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez, Ł. Kaiser, 和 I. Polosukhin，“注意力机制是你所需的一切，”《神经信息处理系统进展》，第 30 卷，2017 年。

+   [27] L. Floridi 和 M. Chiriatti，“Gpt-3：其性质、范围、限制和影响，”《思维与机器》，第 30 卷，第 681–694 页，2020 年。

+   [28] A. Chowdhery, S. Narang, J. Devlin, M. Bosma, G. Mishra, A. Roberts, P. Barham, H. W. Chung, C. Sutton, S. Gehrmann 等人，“Palm：通过路径扩展语言建模，”《机器学习研究杂志》，第 24 卷，第 240 期，第 1–113 页，2023 年。

+   [29] S. Zhang, S. Roller, N. Goyal, M. Artetxe, M. Chen, S. Chen, C. Dewan, M. Diab, X. Li, X. V. Lin, T. Mihaylov, M. Ott, S. Shleifer, K. Shuster, D. Simig, P. S. Koura, A. Sridhar, T. Wang, 和 L. Zettlemoyer，“Opt：开放的预训练变换器语言模型，”2022 年。

+   [30] Y. Wang, H. Le, A. D. Gotmare, N. D. Bui, J. Li, 和 S. C. Hoi, “Codet5+：用于代码理解和生成的开放代码大型语言模型，” arXiv 预印本 arXiv:2305.07922, 2023 年。

+   [31] J. Devlin, M.-W. Chang, K. Lee, 和 K. Toutanova, “Bert：深度双向变换器的预训练用于语言理解，” arXiv 预印本 arXiv:1810.04805, 2018 年。

+   [32] T. Brown, B. Mann, N. Ryder, M. Subbiah, J. D. Kaplan, P. Dhariwal, A. Neelakantan, P. Shyam, G. Sastry, A. Askell, 等，“语言模型是少样本学习者，” 神经信息处理系统进展, 第 33 卷，第 1877–1901 页, 2020 年。

+   [33] H. Touvron, T. Lavril, G. Izacard, X. Martinet, M.-A. Lachaux, T. Lacroix, B. Rozière, N. Goyal, E. Hambro, F. Azhar, 等，“Llama：开放且高效的基础语言模型，” arXiv 预印本 arXiv:2302.13971, 2023 年。

+   [34] J. X. Chen, “计算的发展：Alphago，” 计算科学与工程, 第 18 卷，第 4 期，第 4–7 页, 2016 年。

+   [35] A. Zhao, D. Huang, Q. Xu, M. Lin, Y.-J. Liu, 和 G. Huang, “Expel：Llm 代理是经验学习者，” 在人工智能 AAAI 会议论文集中，第 38 卷，第 19632–19642 页, 2024 年。

+   [36] S. Yao, J. Zhao, D. Yu, N. Du, I. Shafran, K. Narasimhan, 和 Y. Cao, “React：在语言模型中协同推理与行动，” arXiv 预印本 arXiv:2210.03629, 2022 年。

+   [37] W. Huang, P. Abbeel, D. Pathak, 和 I. Mordatch, “语言模型作为零样本规划者：为具身智能体提取可操作知识，” 在国际机器学习会议中，第 9118–9147 页, PMLR, 2022 年。

+   [38] G. Wang, Y. Xie, Y. Jiang, A. Mandlekar, C. Xiao, Y. Zhu, L. Fan, 和 A. Anandkumar, “Voyager：一个开放式的具身智能体，基于大型语言模型，” arXiv 预印本 arXiv:2305.16291, 2023 年。

+   [39] C. Whitehouse, M. Choudhury, 和 A. F. Aji, “Llm 驱动的数据增强以提升跨语言性能，” 2023 年。

+   [40] J. White, Q. Fu, S. Hays, M. Sandborn, C. Olea, H. Gilbert, A. Elnashar, J. Spencer-Smith, 和 D. C. Schmidt, “一个提升提示工程的提示模式目录与 ChatGPT，” arXiv 预印本 arXiv:2302.11382, 2023 年。

+   [41] M. Reid, N. Savinov, D. Teplyashin, D. Lepikhin, T. Lillicrap, J.-b. Alayrac, R. Soricut, A. Lazaridou, O. Firat, J. Schrittwieser, 等，“Gemini 1.5：解锁数百万令牌上下文中的多模态理解，” arXiv 预印本 arXiv:2403.05530, 2024 年。

+   [42] Z. Ji, N. Lee, R. Frieske, T. Yu, D. Su, Y. Xu, E. Ishii, Y. J. Bang, A. Madotto, 和 P. Fung, “自然语言生成中的幻觉调查，” ACM 计算调查, 第 55 卷，第 12 期，第 1–38 页, 2023 年。

+   [43] K. An, F. Yang, L. Li, Z. Ren, H. Huang, L. Wang, P. Zhao, Y. Kang, H. Ding, Q. Lin, 等，“Nissist：基于故障排除指南的事件缓解副驾驶，” arXiv 预印本 arXiv:2402.17531, 2024 年。

+   [44] J. Li, Q. Zhang, Y. Yu, Q. Fu, 和 D. Ye, “更多代理就是你所需的全部，” 2024 年。

+   [45] Y. Dubois, C. X. Li, R. Taori, T. Zhang, I. Gulrajani, J. Ba, C. Guestrin, P. S. Liang 和 T. B. Hashimoto, “Alpacafarm：一个从人类反馈中学习的方法的仿真框架”，《神经信息处理系统进展》，第 36 卷，2024 年。

+   [46] I. Bouzenia, P. Devanbu 和 M. Pradel, “Repairagent：一个自主的基于 LLM 的程序修复代理”，arXiv 预印本 arXiv:2403.17134，2024 年。

+   [47] E. Musumeci, M. Brienza, V. Suriani, D. Nardi 和 D. D. Bloisi, “基于 LLM 的公共管理领域半结构化文档的多智能体生成”，在国际人机交互会议，页码 98–117，Springer，2024 年。

+   [48] X. Luo, Y. Xue, Z. Xing 和 J. Sun, “Prcbert：基于 BERT 预训练语言模型的需求分类提示学习”，在第 37 届 IEEE/ACM 自动化软件工程国际会议论文集，页码 1–13，2022 年。

+   [49] T. Hey, J. Keim, A. Koziolek 和 W. F. Tichy, “Norbert：需求分类的迁移学习”，在 2020 年 IEEE 第 28 届国际需求工程会议（RE），页码 169–179，2020 年。

+   [50] J. Zhang, Y. Chen, N. Niu 和 C. Liu, “在零样本设置下对 ChatGPT 进行需求信息检索评估”，可在 SSRN 4450322 获取，2023 年。

+   [51] C. Arora, J. Grundy 和 M. Abdelrazek, “通过生成式 AI 推进需求工程：评估 LLMs 的作用”，在《生成式 AI 用于有效软件开发》，页码 129–148，Springer，2024 年。

+   [52] M. Krishna, B. Gaur, A. Verma 和 P. Jalote, “在软件需求规格中使用 LLMs：实证评估”，2024 年。

+   [53] L. Ma, S. Liu, Y. Li, X. Xie 和 L. Bu, “Specgen：通过大型语言模型自动生成正式程序规范”，2024 年。

+   [54] C. Flanagan 和 K. R. M. Leino, “Houdini，一个用于 ESC/Java 的注释助手”，在 FME 2001：提高软件生产力的形式化方法（J. N. Oliveira 和 P. Zave 主编），（柏林，海德堡），页码 500–517，Springer Berlin Heidelberg，2001 年。

+   [55] J. White, S. Hays, Q. Fu, J. Spencer-Smith 和 D. C. Schmidt, 《ChatGPT 提示模式：提高代码质量、重构、需求引出和软件设计》，页码 71–108。Cham：Springer Nature Switzerland，2024 年。

+   [56] D. Luitel, S. Hassani 和 M. Sabetzadeh, “提高需求完整性：通过大型语言模型的自动化辅助”，《需求工程》，第 29 卷，第 1 期，页码 73–95，2024 年。

+   [57] A. Moharil 和 A. Sharma, “使用基于变换器的机器学习识别领域内歧义”，在第 1 届国际自然语言基础软件工程研讨会（NLBSE ’22）论文集，（纽约，NY，美国），页码 51–58，计算机协会，2023 年。

+   [58] K. Ronanki, B. Cabrero-Daniel, 和 C. Berger，“ChatGPT 作为用户故事质量评估工具：开箱即用的可信度？”，在《敏捷软件工程与极限编程中的工作坊》（P. Kruchten 和 P. Gregory 编），（Cham），第 173–181 页，Springer Nature Switzerland，2024。

+   [59] A. Poudel, J. Lin, 和 J. Cleland-Huang，“利用基于 Transformer 的语言模型自动化需求满意度评估，” 2023。

+   [60] E. Musumeci, M. Brienza, V. Suriani, D. Nardi, 和 D. D. Bloisi，“基于 LLM 的多代理生成公共行政领域的半结构化文档，” 在《HCI 中的人工智能》（H. Degen 和 S. Ntoa 编），（Cham），第 98–117 页，Springer Nature Switzerland，2024。

+   [61] S. Zhang, J. Wang, G. Dong, J. Sun, Y. Zhang, 和 G. Pu，“使用 LLM 进行新编程实践的实验，” 2024。

+   [62] A. Nouri, B. Cabrero-Daniel, F. Törner, H. Sivencrona, 和 C. Berger，“利用大型语言模型为自动驾驶工程安全需求，” 2024。

+   [63] Z. Zhang, M. Rayhan, T. Herda, M. Goisauf, 和 P. Abrahamsson，“基于 LLM 的代理用于自动化提升用户故事质量：初步报告”，在《敏捷软件工程与极限编程》（D. Šmite, E. Guerra, X. Wang, M. Marchesi, 和 P. Gregory 编），（Cham），第 117–126 页，Springer Nature Switzerland，2024。

+   [64] K. Ronanki, C. Berger, 和 J. Horkoff，“探讨 ChatGPT 在需求获取过程中的潜力，” 2023 年第 49 届欧盟微型计算机会议软件工程与高级应用（SEAA），第 354–361 页，2023。

+   [65] D. Xie, B. Yoo, N. Jiang, M. Kim, L. Tan, X. Zhang, 和 J. S. Lee，“大型语言模型对生成软件规格的影响，” 2023。

+   [66] A. Moharil 和 A. Sharma，“Tabasco: 基于 Transformer 的上下文化工具包，” 计算机编程科学，卷 230，第 102994 页，2023。

+   [67] M. Chen, J. Tworek, H. Jun, Q. Yuan, H. P. de Oliveira Pinto, J. Kaplan, H. Edwards, Y. Burda, N. Joseph, G. Brockman, A. Ray, R. Puri, G. Krueger, M. Petrov, H. Khlaaf, G. Sastry, P. Mishkin, B. Chan, S. Gray, N. Ryder, M. Pavlov, A. Power, L. Kaiser, M. Bavarian, C. Winter, P. Tillet, F. P. Such, D. Cummings, M. Plappert, F. Chantzis, E. Barnes, A. Herbert-Voss, W. H. Guss, A. Nichol, A. Paino, N. Tezak, J. Tang, I. Babuschkin, S. Balaji, S. Jain, W. Saunders, C. Hesse, A. N. Carr, J. Leike, J. Achiam, V. Misra, E. Morikawa, A. Radford, M. Knight, M. Brundage, M. Murati, K. Mayer, P. Welinder, B. McGrew, D. Amodei, S. McCandlish, I. Sutskever, 和 W. Zaremba，“评估在代码上训练的大型语言模型，” 2021。

+   [68] A. Ni, P. Yin, Y. Zhao, M. Riddell, T. Feng, R. Shen, S. Yin, Y. Liu, S. Yavuz, C. Xiong, S. Joty, Y. Zhou, D. Radev, 和 A. Cohan，“L2ceval: 评估大型语言模型的语言到代码生成能力，” 2023。

+   [69] R. 孙, S. Ö. 阿里克, A. 穆齐奥, L. 米库利奇, S. 贡达巴图拉, P. 尹, H. 戴, H. 纳赫斯特, R. 辛哈, Z. 王, 等, “Sql-palm: 改进的大型语言模型适应性用于文本到 SQL（扩展），” arXiv 预印本 arXiv:2306.00739, 2023。

+   [70] Q. 郑, X. 夏, X. 邹, Y. 董, S. 王, Y. 薛, Z. 王, L. 沈, A. 王, Y. 李, T. 苏, Z. 杨, 和 J. 唐, “Codegeex: 一种用于代码生成的预训练模型，在 humaneval-x 上进行多语言基准测试，” 2024。

+   [71] X. 胡, K. 匡, J. 孙, H. 杨, 和 F. 吴, “利用打印调试来提高大型语言模型中的代码生成，” 2024。

+   [72] S. 彭, E. 卡利安瓦库, P. 齐洪, 和 M. 德米雷尔, “人工智能对开发者生产力的影响: 来自 GitHub Copilot 的证据，” 2023。

+   [73] D. 弗里德, A. 阿赫贾尼扬, J. 林, S. 王, E. 华莱士, F. 石, R. 钟, W. 陶 Yih, L. 泽特尔莫耶, 和 M. 刘易斯, “Incoder: 用于代码填充和合成的生成模型，” 2023。

+   [74] E. 奈坎普, B. 庞, H. 林, L. 涂, H. 王, Y. 周, S. 萨瓦雷斯, 和 C. 熊, “Codegen: 一个开放的大型语言模型用于代码的多轮程序合成，” 2023。

+   [75] Y. 丁, M. J. 闵, G. 凯瑟, 和 B. 雷, “Cycle: 学习自我改进代码生成，” Proc. ACM Program. Lang., vol. 8, apr 2024。

+   [76] Y. 董, X. 姜, Z. 金, 和 G. 李, “通过 ChatGPT 进行自我协作的代码生成，” 2024。

+   [77] F. 林, D. J. 金, 等, “当基于 LLM 的代码生成遇上软件开发过程，” arXiv 预印本 arXiv:2403.15852, 2024。

+   [78] S. 霍尔特, M. R. Luyten, 和 M. 范德·沙尔, “L2MAC: 大型语言模型自动计算机用于广泛的代码生成，” 在第十二届国际学习表征会议，2024。

+   [79] S. 洪, M. 诸葛, J. 陈, X. 郑, Y. 程, C. 张, J. 王, Z. 王, S. K. S. 邱, Z. 林, L. 周, C. 冉, L. 肖, C. 吴, 和 J. 施密德胡伯, “Metagpt: 多代理协作框架的元编程，” 2023。

+   [80] Z. 拉希德, M. 瓦西姆, K.-K. 凯梅尔, W. 肖峰, A. N. 杜克, K. 苏斯塔, 和 P. 亚伯拉罕森, “软件开发中的自主代理: 远景论文，” arXiv 预印本 arXiv:2311.18440, 2023。

+   [81] Z. 拉希德, M. 瓦西姆, M. 萨阿里, K. 苏斯塔, 和 P. 亚伯拉罕森, “Codepori: 使用多代理的自主软件开发的大规模模型，” arXiv 预印本 arXiv:2402.01411, 2024。

+   [82] D. 黄, Q. 布, J. M. 张, M. Luck, 和 H. 崔, “Agentcoder: 基于多代理的代码生成与迭代测试和优化，” arXiv 预印本 arXiv:2312.13010, 2023。

+   [83] T. 郑, G. 张, T. 沈, X. 刘, B. Y. 林, J. 傅, W. 陈, 和 X. 岳, “Opencodeinterpreter: 将代码生成与执行和改进相结合，” arXiv 预印本 arXiv:2402.14658, 2024。

+   [84] T. 施克, J. 德维维迪-余, R. 德西, R. 雷柳努, M. 洛梅利, E. 汉布罗, L. 泽特尔莫耶, N. 坎塞达, 和 T. 斯奇亚洛姆, “Toolformer: 语言模型可以自我学习使用工具，” 《神经信息处理系统进展》，第 36 卷，2024。

+   [85] Y. Qin, S. Liang, Y. Ye, K. Zhu, L. Yan, Y. Lu, Y. Lin, X. Cong, X. Tang, B. Qian, 等, “Toolllm：帮助大型语言模型掌握 16000+现实世界 API，” arXiv 预印本 arXiv:2307.16789, 2023 年。

+   [86] X. Jiang, Y. Dong, L. Wang, F. Zheng, Q. Shang, G. Li, Z. Jin, 和 W. Jiao, “利用大型语言模型进行自我规划代码生成，” ACM Trans. Softw. Eng. Methodol., 2024 年 6 月。刚刚接受。

+   [87] S. Zhang, J. Wang, G. Dong, J. Sun, Y. Zhang, 和 G. Pu, “用 llms 实验新的编程实践，” arXiv 预印本 arXiv:2401.01062, 2024 年。

+   [88] V. Murali, C. Maddila, I. Ahmad, M. Bolin, D. Cheng, N. Ghorbani, R. Fernandez, 和 N. Nagappan, “Codecompose：大规模工业部署的 AI 辅助代码创作，” arXiv 预印本 arXiv:2305.12050, 2023 年。

+   [89] J. Huang, S. S. Gu, L. Hou, Y. Wu, X. Wang, H. Yu, 和 J. Han, “大型语言模型可以自我改进，” arXiv 预印本 arXiv:2210.11610, 2022 年。

+   [90] L. Chen, J. Q. Davis, B. Hanin, P. Bailis, I. Stoica, M. Zaharia, 和 J. Zou, “更多的 llm 调用是否足够？关于复合推理系统的规模定律，” arXiv 预印本 arXiv:2403.02419, 2024 年。

+   [91] X. Chen, M. Lin, N. Schärli, 和 D. Zhou, “教大型语言模型自我调试，” arXiv 预印本 arXiv:2304.05128, 2023 年。

+   [92] S. Kang, B. Chen, S. Yoo, 和 J.-G. Lou, “通过大型语言模型驱动的科学调试实现可解释的自动调试，” arXiv 预印本 arXiv:2304.02195, 2023 年。

+   [93] G. Franceschelli 和 M. Musolesi, “大型语言模型的创造力，” arXiv 预印本 arXiv:2304.00008, 2023 年。

+   [94] J. Lai, W. Gan, J. Wu, Z. Qi, 和 P. S. Yu, “法律中的大型语言模型：综述，” 2023 年。

+   [95] L. Zheng, W.-L. Chiang, Y. Sheng, S. Zhuang, Z. Wu, Y. Zhuang, Z. Lin, Z. Li, D. Li, E. Xing, 等, “用 mt-bench 和 chatbot arena 评判 llm-as-a-judge，” Advances in Neural Information Processing Systems, 第 36 卷, 2024 年。

+   [96] Q. Wang, Z. Wang, Y. Su, H. Tong, 和 Y. Song, “重新思考 llm 推理的界限：多智能体讨论是否是关键？，” arXiv 预印本 arXiv:2402.18272, 2024 年。

+   [97] L. Chen, Y. Zhang, S. Ren, H. Zhao, Z. Cai, Y. Wang, P. Wang, T. Liu, 和 B. Chang, “通过多模态大型语言模型实现端到端的具身决策：使用 gpt4-vision 及其他的探索，” arXiv 预印本 arXiv:2310.02071, 2023 年。

+   [98] N. Shinn, F. Cassano, A. Gopinath, K. Narasimhan, 和 S. Yao, “Reflexion：具有语言代理的语言代理与语言强化学习，” Advances in Neural Information Processing Systems, 第 36 卷, 2024 年。

+   [99] W. Chen, Y. Su, J. Zuo, C. Yang, C. Yuan, C. Qian, C.-M. Chan, Y. Qin, Y. Lu, R. Xie, 等, “Agentverse：促进多智能体协作和探索智能体中的新兴行为，” arXiv 预印本 arXiv:2308.10848, 2023 年。

+   [100] G. Li, H. Hammoud, H. Itani, D. Khizbullin, 和 B. Ghanem, “Camel：大型语言模型社会中的‘心智’探索沟通代理，” Advances in Neural Information Processing Systems, 第 36 卷，第 51991–52008 页, 2023 年。

+   [101] Z. Liu、W. Yao、J. Zhang、L. Xue、S. Heinecke、R. Murthy、Y. Feng、Z. Chen、J. C. Niebles、D. Arpit 等人，“Bolaa：LLM 增强的自主代理基准测试与调度”，arXiv 预印本 arXiv:2308.05960，2023 年。

+   [102] J. Lu、W. Zhong、W. Huang、Y. Wang、Q. Zhu、F. Mi、B. Wang、W. Wang、X. Zeng、L. Shang、X. Jiang 和 Q. Liu，“Self：通过语言反馈实现自我进化”，2024 年。

+   [103] C. Xie、C. Chen、F. Jia、Z. Ye、K. Shu、A. Bibi、Z. Hu、P. Torr、B. Ghanem 和 G. Li，“大语言模型代理能否模拟人类信任行为？”，arXiv 预印本 arXiv:2402.04559，2024 年。

+   [104] Z. Liu、W. Yao、J. Zhang、L. Yang、Z. Liu、J. Tan、P. K. Choubey、T. Lan、J. Wu、H. Wang 等人，“Agentlite：一个轻量级库，用于构建和推进任务导向的 LLM 代理系统”，arXiv 预印本 arXiv:2402.15538，2024 年。

+   [105] M. Zhuge、W. Wang、L. Kirsch、F. Faccio、D. Khizbullin 和 J. Schmidhuber，“语言代理作为可优化图”，arXiv 预印本 arXiv:2402.16823，2024 年。

+   [106] R. Feldt、S. Kang、J. Yoon 和 S. Yoo，“通过对话式大语言模型迈向自动化测试代理”，发表于 2023 年第 38 届 IEEE/ACM 自动化软件工程国际会议（ASE），第 1688–1693 页，IEEE，2023 年。

+   [107] A. Happe 和 J. Cito，“被 AI 彻底打败：利用大语言模型进行渗透测试”，发表于第 31 届 ACM 联合欧洲软件工程会议及软件工程基础研讨会，第 2082–2086 页，2023 年。

+   [108] W. Ma、D. Wu、Y. Sun、T. Wang、S. Liu、J. Zhang、Y. Xue 和 Y. Liu，“结合微调和基于 LLM 的代理进行直观智能合约审计及其理由”，arXiv 预印本 arXiv:2403.16073，2024 年。

+   [109] R. Fang、R. Bindu、A. Gupta 和 D. Kang，“LLM 代理可以自主利用一天的漏洞”，arXiv 预印本 arXiv:2404.08144，2024 年。

+   [110] S. Yao、D. Yu、J. Zhao、I. Shafran、T. Griffiths、Y. Cao 和 K. Narasimhan，“思想树：使用大语言模型进行深思熟虑的问题解决”，《神经信息处理系统进展》，第 36 卷，2024 年。

+   [111] Z. Rasheed、M. Waseem、A. Ahmad、K.-K. Kemell、W. Xiaofeng、A. N. Duc 和 P. Abrahamsson，“大语言模型能否充当数据分析师？一种多代理协助的定性数据分析方法”，arXiv 预印本 arXiv:2402.01386，2024 年。

+   [112] M. Ataei、H. Cheong、D. Grandi、Y. Wang、N. Morris 和 A. Tessier，“Elicitron：一个基于 LLM 的设计需求引导模拟框架”，arXiv 预印本 arXiv:2404.16045，2024 年。

+   [113] G. Sridhara、S. Mazumdar 等人，“ChatGPT：对其在普遍软件工程任务中的实用性研究”，arXiv 预印本 arXiv:2305.16837，2023 年。

+   [114] M. Desmond、Z. Ashktorab、Q. Pan、C. Dugan 和 J. M. Johnson，“Evalullm：LLM 辅助的生成输出评估”，发表于第 29 届国际智能用户界面会议的伴随论文集，第 30–32 页，2024 年。

+   [115] M. Gao, X. Hu, J. Ruan, X. Pu, 和 X. Wan, “基于 LLM 的 NLG 评估：现状与挑战，” arXiv 预印本 arXiv:2402.01383, 2024。

+   [116] L. J. Wan, Y. Huang, Y. Li, H. Ye, J. Wang, X. Zhang, 和 D. Chen, “LLM 的软件/硬件协同设计及其在设计验证中的应用，” 在 2024 年第 29 届亚洲及南太平洋设计自动化会议（ASP-DAC）中，pp. 435–441, IEEE, 2024。

+   [117] K. Kolthoff, C. Bartelt, 和 S. P. Ponzetto, “通过自然语言基础的 GUI 检索进行数据驱动的原型设计，” 自动化软件工程, 卷 30, 号 1, 页 13, 2023。

+   [118] V. D. Kirova, C. S. Ku, J. R. Laracy, 和 T. J. Marlowe, “软件工程教育必须适应并为 LLM 环境演变，” 在第 55 届 ACM 计算机科学教育技术研讨会第 1 卷中，pp. 666–672, 2024。

+   [119] S. Jalil, S. Rafi, T. D. LaToza, K. Moran, 和 W. Lam, “Chatgpt 和软件测试教育：承诺与危险 (2023),” arXiv 预印本 arXiv:2302.03287, 2023。

+   [120] S. Suri, S. N. Das, K. Singi, K. Dey, V. S. Sharma, 和 V. Kaulgud, “使用自主智能体的软件工程：我们已经到达了吗？，” 在 2023 年第 38 届 IEEE/ACM 自动化软件工程国际会议（ASE）中，pp. 1855–1857, IEEE, 2023。

+   [121] C. Qian, X. Cong, C. Yang, W. Chen, Y. Su, J. Xu, Z. Liu, 和 M. Sun, “用于软件开发的沟通智能体，” arXiv 预印本 arXiv:2307.07924, 2023。

+   [122] Y. Shen, K. Song, X. Tan, D. Li, W. Lu, 和 Y. Zhuang, “Hugginggpt：使用 Chatgpt 及其在 Hugging Face 的朋友解决 AI 任务，” 神经信息处理系统进展, 卷 36, 2024。

+   [123] J. Chen, X. Hu, S. Liu, S. Huang, W.-W. Tu, Z. He, 和 L. Wen, “Llmarena: 评估大型语言模型在动态多智能体环境中的能力，” arXiv 预印本 arXiv:2402.16499, 2024。

+   [124] M. Josifoski, L. Klein, M. Peyrard, Y. Li, S. Geng, J. P. Schnitzler, Y. Yao, J. Wei, D. Paul, 和 R. West, “Flows：推理和协作 AI 的构建块，” arXiv 预印本 arXiv:2308.01285, 2023。

+   [125] I. Weber, “大型语言模型作为软件组件：LLM 集成应用的分类法，” arXiv 预印本 arXiv:2406.10300, 2024。

+   [126] F. Vallecillos Ruiz, “基于智能体的自动软件改进，” 在第 28 届国际软件工程评估与评估会议论文集中，pp. 470–475, 2024。

+   [127] Z. Cheng, J. Kasai, 和 T. Yu, “批量提示：使用大型语言模型 API 的高效推理，” arXiv 预印本 arXiv:2301.08721, 2023。

+   [128] S. Shankar, J. Zamfirescu-Pereira, B. Hartmann, A. G. Parameswaran, 和 I. Arawjo, “谁验证验证者？对齐 LLM 辅助的 LLM 输出评估与人类偏好，” arXiv 预印本 arXiv:2404.12272, 2024。

+   [129] D. Roy, X. Zhang, R. Bhave, C. Bansal, P. Las-Casas, R. Fonseca, 和 S. Rajmohan，“探索基于 LLM 的根本原因分析代理，”发表于《第 32 届 ACM 国际软件工程基础会议伴随论文集》，第 208–219 页，2024 年。

+   [130] Y. Li, Y. Zhang, 和 L. Sun，“Metaagents：通过协作生成代理模拟人类行为的 LLM 任务协调，”arXiv 预印本 arXiv:2310.06500，2023 年。

+   [131] M. Tufano, D. Drain, A. Svyatkovskiy, S. K. Deng, 和 N. Sundaresan，“利用变压器和焦点上下文生成单元测试用例，”arXiv 预印本 arXiv:2009.05617，2020 年。

+   [132] Y. Zhang, W. Song, Z. Ji, N. Meng 等，“LLM 生成安全测试的效果如何？”，arXiv 预印本 arXiv:2310.00710，2023 年。

+   [133] H. J. Kang, T. G. Nguyen, B. Le, C. S. Păsăreanu, 和 D. Lo，“测试模拟以评估库漏洞的可利用性，”发表于《第 31 届 ACM SIGSOFT 国际软件测试与分析研讨会论文集》，第 276–288 页，2022 年。

+   [134] S. Feng 和 C. Chen，“提示即你所需：使用大型语言模型的自动化安卓漏洞重现，”发表于《第 46 届 IEEE/ACM 国际软件工程会议论文集》，第 1–13 页，2024 年。

+   [135] S. Kang, J. Yoon, 和 S. Yoo，“大型语言模型是少量样本测试器：探索基于 LLM 的一般性漏洞再现，”发表于 2023 年 IEEE/ACM 第 45 届国际软件工程会议（ICSE），第 2312–2323 页，IEEE，2023 年。

+   [136] C. S. Xia, M. Paltenghi, J. Le Tian, M. Pradel, 和 L. Zhang，“Fuzz4all：与大型语言模型的通用模糊测试，”发表于《IEEE/ACM 第 46 届国际软件工程会议论文集》，第 1–13 页，2024 年。

+   [137] G. Ryan, S. Jain, M. Shang, S. Wang, X. Ma, M. K. Ramanathan, 和 B. Ray，“代码感知提示：使用 LLM 在回归设置中进行覆盖指导的测试生成研究，”arXiv 预印本 arXiv:2402.00097，2024 年。

+   [138] J. A. Pizzorno 和 E. D. Berger，“Coverup：覆盖指导的基于 LLM 的测试生成，”arXiv 预印本 arXiv:2403.16218，2024 年。

+   [139] K. Liu, Y. Liu, Z. Chen, J. M. Zhang, Y. Han, Y. Ma, G. Li, 和 G. Huang，“LLM 驱动的测试用例生成用于检测棘手的漏洞，”arXiv 预印本 arXiv:2404.10304，2024 年。

+   [140] K. Li 和 Y. Yuan，“大型语言模型作为测试用例生成器：性能评估与增强，”arXiv 预印本 arXiv:2404.13340，2024 年。

+   [141] Z. Wang, W. Wang, Z. Li, L. Wang, C. Yi, X. Xu, L. Cao, H. Su, S. Chen, 和 J. Zhou，“Xuat-copilot：基于大型语言模型的自动化用户验收测试的多代理协作系统，”arXiv 预印本 arXiv:2401.02705，2024 年。

+   [142] C. Lee, C. S. Xia, J.-t. Huang, Z. Zhu, L. Zhang, 和 M. R. Lyu，“通过 LLM 基础的多代理协同实现统一调试方法，”arXiv 预印本 arXiv:2404.17153，2024 年。

+   [143] G. Deng, Y. Liu, V. Mayoral-Vilches, P. Liu, Y. Li, Y. Xu, T. Zhang, Y. Liu, M. Pinzger, 和 S. Rass，“Pentestgpt：一个 llm 驱动的自动化渗透测试工具”，arXiv 预印本 arXiv:2308.06782，2023 年。

+   [144] M. Xiao, Y. Xiao, H. Dong, S. Ji, 和 P. Zhang，“Ritfis：基于 llms 的智能软件的稳健输入测试框架”，arXiv 预印本 arXiv:2402.13518，2024 年。

+   [145] R. Wang, Z. Li, C. Wang, Y. Xiao, 和 C. Gao，“Navrepair：节点类型感知的 C/C++ 代码漏洞修复”，arXiv 预印本 arXiv:2405.04994，2024 年。

+   [146] A. Shestov, A. Cheshkov, R. Levichev, R. Mussabayev, P. Zadorozhny, E. Maslov, C. Vadim, 和 E. Bulychev，“为漏洞检测微调大型语言模型”，arXiv 预印本 arXiv:2401.17010，2024 年。

+   [147] A. Cheshkov, P. Zadorozhny, 和 R. Levichev，“评估 ChatGPT 模型在漏洞检测中的表现”，arXiv 预印本 arXiv:2304.07232，2023 年。

+   [148] G. Lu, X. Ju, X. Chen, W. Pei, 和 Z. Cai，“Grace：通过图结构和上下文学习增强 llm 基础的软件漏洞检测”，《系统与软件期刊》，第 212 卷，第 112031 页，2024 年。

+   [149] H. Li, Y. Hao, Y. Zhai, 和 Z. Qian，“程序分析的搭车指南：与大型语言模型的旅程”，arXiv 预印本 arXiv:2308.00245，2023 年。

+   [150] Y. Ding, Y. Fu, O. Ibrahim, C. Sitawarin, X. Chen, B. Alomair, D. Wagner, B. Ray, 和 Y. Chen，“使用代码语言模型进行漏洞检测：我们距离目标还有多远？”，arXiv 预印本 arXiv:2403.18624，2024 年。

+   [151] F. V. Ruiz, A. Grishina, M. Hort, 和 L. Moonen，“使用大型语言模型进行往返翻译的自动程序修复新方法”，arXiv 预印本 arXiv:2401.07994，2024 年。

+   [152] B. Yang, H. Tian, J. Ren, H. Zhang, J. Klein, T. F. Bissyandé, C. L. Goues, 和 S. Jin，“用于增强程序修复的多目标微调与 llms”，arXiv 预印本 arXiv:2404.12636，2024 年。

+   [153] T. Dettmers, A. Pagnoni, A. Holtzman, 和 L. Zettlemoyer，“Qlora：量化 llms 的高效微调”，2023 年。

+   [154] N. Jain, P. yeh Chiang, Y. Wen, J. Kirchenbauer, H.-M. Chu, G. Somepalli, B. R. Bartoldson, B. Kailkhura, A. Schwarzschild, A. Saha, M. Goldblum, J. Geiping, 和 T. Goldstein，“Neftune：噪声嵌入改进指令微调”，2023 年。

+   [155] J. Zhang, J. P. Cambronero, S. Gulwani, V. Le, R. Piskac, G. Soares, 和 G. Verbruggen，“Pydex：使用 llms 修复入门 Python 作业中的错误”，《ACM 编程语言论文集》，第 8 卷，第 OOPSLA1 期，第 1100–1124 页，2024 年。

+   [156] H. Joshi, J. C. Sanchez, S. Gulwani, V. Le, G. Verbruggen, 和 I. Radiček，“修复几乎是生成：使用 llms 的多语言程序修复”，发表于《AAAI 人工智能会议论文集》，第 37 卷，第 5131–5140 页，2023 年。

+   [157] J. Xiang, X. Xu, F. Kong, M. Wu, H. Zhang, 和 Y. Zhang，“实际函数级程序修复能走多远？”，arXiv 预印本 arXiv:2404.12833，2024 年。

+   [158] E. Hilario, S. Azam, J. Sundaram, K. Imran Mohammed 和 B. Shanmugam，“用于渗透测试的生成 AI：优点、缺点和不足”，《信息安全国际期刊》，第 23 卷，第 3 期，页码 2075–2097，2024 年。

+   [159] L. Zhong, Z. Wang 和 J. Shang，“LDB：通过逐步验证运行时执行的大型语言模型调试器”，arXiv 预印本 arXiv:2402.16906，2024 年。

+   [160] L. Zhang, K. Li, K. Sun, D. Wu, Y. Liu, H. Tian 和 Y. Liu，“ACFix：通过挖掘的常见 RBAC 实践指导 LLM 用于智能合约中的访问控制漏洞的上下文感知修复”，2024 年。

+   [161] S. Hu, T. Huang, F. İlhan, S. F. Tekin 和 L. Liu，“大型语言模型驱动的智能合约漏洞检测：新视角”，2023 年。

+   [162] M. Alhanahnah, M. R. Hasan 和 H. Bagheri，“对预训练大型语言模型进行修复声明性形式规范的实证评估”，arXiv 预印本 arXiv:2404.11050，2024 年。

+   [163] F. Geissler, K. Roscher 和 M. Trapp，“概念引导的 LLM 代理用于人类-AI 安全共同设计”，见《AAAI 研讨会系列论文集》，第 3 卷，页码 100–104，2024 年。

+   [164] A. Nouri, B. Cabrero-Daniel, F. Törner, H. Sivencrona 和 C. Berger，“使用大型语言模型工程化自动驾驶的安全要求”，arXiv 预印本 arXiv:2403.16289，2024 年。

+   [165] C. Thapa, S. I. Jang, M. E. Ahmed, S. Camtepe, J. Pieprzyk 和 S. Nepal，“基于 Transformer 的语言模型用于软件漏洞检测”，见《第 38 届年度计算机安全应用会议论文集》，页码 481–496，2022 年。

+   [166] L. Zhong, Z. Wang 和 J. Shang，“像人类一样调试：通过逐步验证运行时执行的语言模型调试器”，2024 年。

+   [167] N. Alshahwan, M. Harman, I. Harper, A. Marginean, S. Sengupta 和 E. Wang，“确保基于 LLM 的软件工程”，2024 年。

+   [168] A. Cheshkov, P. Zadorozhny 和 R. Levichev，“对 ChatGPT 模型进行漏洞检测的评估”，2023 年。

### -A 基准

![参见说明](img/03b5895a1e8f05ceb81375006382b888.png)

图 12：基准分布

### -B 评估指标

![参见说明](img/a0337131d1fd60a365a99ae08162897b.png)

图 13：前 10 名评估指标

由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/) 生成于 2024 年 8 月 5 日星期一 13:48:05
