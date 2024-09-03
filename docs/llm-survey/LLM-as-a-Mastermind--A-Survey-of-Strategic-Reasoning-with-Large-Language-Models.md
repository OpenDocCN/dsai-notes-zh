<!--yml

category: 未分类

date: 2024-09-03 17:29:47

-->

# 大型语言模型作为策士：战略推理的调查

> 来源：[`arxiv.org/html/2404.01230`](https://arxiv.org/html/2404.01230)

1.  [1 引言](https://arxiv.org/html/2404.01230v1#S1 "在大型语言模型作为策士：战略推理的调查")

1.  [2 定义：什么是大型语言模型的战略推理](https://arxiv.org/html/2404.01230v1#S2 "在大型语言模型作为策士：战略推理的调查")

1.  [3 场景：在哪里应用战略推理](https://arxiv.org/html/2404.01230v1#S3 "在大型语言模型作为策士：战略推理的调查")

1.  [4 方法：如何提升大型语言模型的战略推理](https://arxiv.org/html/2404.01230v1#S4 "在大型语言模型作为策士：战略推理的调查")

1.  [5 评估：如何评估大型语言模型的战略推理](https://arxiv.org/html/2404.01230v1#S5 "在大型语言模型作为策士：战略推理的调查")

1.  [6 讨论：对大型语言模型的战略推理展望](https://arxiv.org/html/2404.01230v1#S6 "在大型语言模型作为策士：战略推理的调查")

    1.  [6.1 大型语言模型代理是否真的能够模拟人类战略推理？](https://arxiv.org/html/2404.01230v1#S6.SS1 "在 6 讨论：对大型语言模型的战略推理展望 ‣ 大型语言模型作为策士：战略推理的调查")

    1.  [6.2 弥合分歧：对统一基准的紧迫需求](https://arxiv.org/html/2404.01230v1#S6.SS2 "在 6 讨论：对大型语言模型的战略推理展望 ‣ 大型语言模型作为策士：战略推理的调查")

    1.  [6.3 战略推理：对大型语言模型具有挑战性但充满希望](https://arxiv.org/html/2404.01230v1#S6.SS3 "在 6 讨论：对大型语言模型的战略推理展望 ‣ 大型语言模型作为策士：战略推理的调查")

1.  [7 结论](https://arxiv.org/html/2404.01230v1#S7 "在大型语言模型作为策士：战略推理的调查")

1.  [A 附录](https://arxiv.org/html/2404.01230v1#A1 "在大型语言模型作为策士：战略推理的调查")

    1.  [A.1 推理的认知技能](https://arxiv.org/html/2404.01230v1#A1.SS1 "在附录 A 附录 ‣ 大型语言模型作为策士：战略推理的调查")

    1.  [A.2 战略推理的符号系统](https://arxiv.org/html/2404.01230v1#A1.SS2 "在附录 A 附录 ‣ 大型语言模型作为策士：战略推理的调查")

        1.  [A.2.1 战略推理环境的制定](https://arxiv.org/html/2404.01230v1#A1.SS2.SSS1 "在 A.2 战略推理的符号系统 ‣ 附录 A 附录 ‣ 大型语言模型作为策士：战略推理的调查")

        1.  [A.2.2 目标](https://arxiv.org/html/2404.01230v1#A1.SS2.SSS2 "在 A.2 战略推理的符号系统 ‣ 附录 A 附录 ‣ **大型语言模型作为战略家**：关于使用大型语言模型进行战略推理的调查")

    1.  [A.3 使用大型语言模型进行战略推理与强化学习](https://arxiv.org/html/2404.01230v1#A1.SS3 "在附录 A 附录 ‣ **大型语言模型作为战略家**：关于使用大型语言模型进行战略推理的调查")

\useunder

\ul

# **大型语言模型作为战略家**：关于使用大型语言模型进行战略推理的调查

张亚东¹，毛绍光²，葛涛²，王勋²，阿德里安·德·温特²

闫霞²，吴文山²，宋婷²，兰曼¹，魏甫²

¹ 华东师范大学，² 微软

{yadongzhang@stu, mlan@cs}.ecnu.edu.cn

{shaoguang.mao, tage, fuwei}@microsoft.com 预印本。工作完成于微软亚洲研究院实习期间。

###### 摘要

本文提供了关于大型语言模型（LLMs）在战略推理中现状和机会的综合调查。战略推理是一种复杂的推理形式，需要在多智能体环境中理解和预测对手的行动，并相应地调整策略。战略推理的特点在于关注多智能体间互动的动态和不确定性，其中理解环境和预测他人行为至关重要。我们探讨了与 LLMs 的战略推理相关的范围、应用、方法和评估指标，突显了该领域的新兴发展及其提升决策性能的跨学科方法。本文旨在系统化和澄清该主题上散乱的文献，提供一个系统的回顾，强调战略推理作为一种关键认知能力的重要性，并为未来的研究方向和潜在改进提供见解。

图 1：大型语言模型的战略推理。

## 1 引言

大型语言模型（LLMs）开创了人工智能的新纪元，特别突显了在执行推理任务中的潜力，包括常识问答（Talmor et al., [2022](https://arxiv.org/html/2404.01230v1#bib.bib65)）和数学问题（Miao et al., [2021](https://arxiv.org/html/2404.01230v1#bib.bib50)）等。

战略推理（Van Der Hoek 等，[2005](https://arxiv.org/html/2404.01230v1#bib.bib70)；Duan 等，[2024](https://arxiv.org/html/2404.01230v1#bib.bib13)；Gandhi 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib20)）代表了一种独特的推理艺术。通常，它涉及在多主体环境中合理选择最佳行动策略，考虑他人的可能行动以及自己的决策如何影响他们的选择。对于大型语言模型来说，战略推理的必要性不仅仅是学术上的好奇心；它对于理解和应对物理与社会世界的复杂性至关重要。人类智能不仅预测物理和社会环境中行为的结果，还基于这些预测调整策略。为了赋予人工智能社会属性，使其更具智慧、负责任且具备同理心，深入研究 LLMs 的战略推理是必不可少的。

战略推理与其他形式的推理不同之处在于推理环境的动态性和对手行动的不确定性。我们在表[1](https://arxiv.org/html/2404.01230v1#S1.T1 "Table 1 ‣ 1 Introduction ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models")中比较了不同推理任务所需的核心认知技能。它不仅需要对动态环境（背景）的深刻理解，还需要在预测其他参与者的行为中做出理性决策。战略推理挑战与实际问题高度相关，包括商业分析和政策制定。由于其引人入胜的特性，战略推理受到了学术界越来越多的关注。

| 推理任务 | 逻辑推理 | 背景智能 | 预测分析 | 抽象思维 | 认知同理 |
| --- | --- | --- | --- | --- | --- |
| 常识推理 |  |  |  |  |  |
| 数学推理 |  |  |  |  |  |
| 符号推理 |  |  |  |  |  |
| 因果推理 |  |  |  |  |  |
| 战略推理 |  |  |  |  |  |
| 、和分别表示低、中、高三个级别。 |

表 1：对常见推理任务及其与不同认知技能的对齐进行分析。我们并没有详尽列出所有与推理相关的认知技能，而是主要选择了与不同推理任务相关的一些代表性认知技能。每项认知技能的含义在附录[A.1](https://arxiv.org/html/2404.01230v1#A1.SS1 "A.1 Cognitive Skills of Reasoning ‣ Appendix A Appendix ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models")中进行了解释。

在大型语言模型被广泛采用之前，战略推理仅限于复杂的数字化环境，如空间动作游戏、棋盘游戏和竞争性视频游戏，其中代理的决策能力高度依赖于通过强化学习进行的大规模模拟（Gronauer & Diepold, [2022](https://arxiv.org/html/2404.01230v1#bib.bib24); Arulkumaran et al., [2017](https://arxiv.org/html/2404.01230v1#bib.bib5); Browne et al., [2012](https://arxiv.org/html/2404.01230v1#bib.bib8); Silver et al., [2017](https://arxiv.org/html/2404.01230v1#bib.bib63)）。这些限制了战略推理的应用范围和可迁移性。幸运的是，大型语言模型（LLMs）的出现为战略推理带来了新的机遇。首先，大型语言模型的文本生成能力通过对话式生成代理的实施，促进了更广泛的战略应用。其次，大型语言模型强大的上下文理解能力（Ouyang et al., [2022](https://arxiv.org/html/2404.01230v1#bib.bib53)）使其能够迅速掌握新情境，显著扩展了基于 AI 的战略推理设置的范围，超越了之前的限制。最后，大型语言模型提供的基于文本的推理过程模拟了人类思维（Wei et al., [2022](https://arxiv.org/html/2404.01230v1#bib.bib74); Kojima et al., [2022](https://arxiv.org/html/2404.01230v1#bib.bib39); Wang et al., [2023b](https://arxiv.org/html/2404.01230v1#bib.bib73)），使决策过程更加透明和易于解释。

利用 LLMs 在决策和推理中的优势，最近在扩展应用场景方面取得了蓬勃的发展。同时，来自跨学科领域的方法，如心智理论（Guo et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib27)）和认知层级（Zhang et al., [2024c](https://arxiv.org/html/2404.01230v1#bib.bib92)），正被调整以提升 LLMs 的决策性能。尽管应用和方法论繁多，但在 LLMs 的战略推理使用方面，缺乏系统的综述来组织和阐明这些工作的差异与联系。与多智能体强化学习文献（Huh & Mohapatra, [2023](https://arxiv.org/html/2404.01230v1#bib.bib37)）相比，利用 LLMs 进行战略推理在方法和应用范围上显著不同。关于大语言模型用于代理（Guo et al., [2024b](https://arxiv.org/html/2404.01230v1#bib.bib28); Wang et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib71); Xi et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib79)）、仿真（Gao et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib22)）和游戏（Xu et al., [2024b](https://arxiv.org/html/2404.01230v1#bib.bib85)）的综述文献确实提到了战略推理的一些方面，但作为关键认知能力的战略推理应当被关注并进行系统分析。本文旨在提供 LLMs 在战略推理中的现状的全面概述，揭示它们的能力、应用及未来更有效利用其潜力的道路。

本调查的其余部分按以下顺序组织：第 [2](https://arxiv.org/html/2404.01230v1#S2 "2 Definition: What is Strategic Reasoning with LLMs ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models") 节深入探讨战略推理的定义和范围，概述战略推理如何与其他推理情境区分开来。第 [3](https://arxiv.org/html/2404.01230v1#S3 "3 Scenarios: Where to Apply Strategic Reasoning with LLMs ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models") 节探讨了大型语言模型在战略推理中的应用，分类任务和应用领域。第 [4](https://arxiv.org/html/2404.01230v1#S4 "4 Methods: How to Improve Strategic Reasoning with LLMs ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models") 节讨论了增强大型语言模型在战略推理中的现有方法，分类了在战略思维过程中使用大型语言模型的方法。第 [5](https://arxiv.org/html/2404.01230v1#S5 "5 Evaluations: How to Assess Strategic Reasoning with LLMs ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models") 节讨论了如何评估大型语言模型在战略推理中的表现，包括定量评估和能力的定性分析。最后，第 [6](https://arxiv.org/html/2404.01230v1#S6 "6 Discussions: An Outlook on Strategic Reasoning with LLMs ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models") 节探讨了将大型语言模型应用于战略推理所带来的挑战和机遇，提供了对未来研究方向和基于当前研究局限性的潜在改进的见解。

## 2 定义：什么是战略推理与大型语言模型

战略推理可以定义为在竞争或合作的多智能体环境中，预测和影响他人行为的能力。这涉及到理解他人的动机、意图和潜在行为，以及环境中的因果关系。与其他可能专注于静态问题解决或单一智能体决策的推理形式不同，战略推理本质上是动态和互动的，需要不断评估不断变化的情况和其他智能体的意图。在附录 [A.2](https://arxiv.org/html/2404.01230v1#A1.SS2 "A.2 Symbolic System of Strategic Reasoning ‣ Appendix A Appendix ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models") 中，我们提供了战略推理与大型语言模型的正式定义。

战略推理的核心特征包括：

目标导向：推理过程的目标是实现特定的目标，通常是在竞争或合作的框架内。

互动性：战略推理涉及多个代理之间的互动，每个代理都受到其他代理决策的影响，并对其他代理的决策产生影响。

预测性质：它要求具备基于有限信息和不确定结果预测其他代理行为和响应的能力。

适应性：代理必须能够根据其他代理的行为和环境的变化调整他们的策略。

定义讨论范围外的内容也很重要。具体而言，我们不会讨论缺乏战略复杂性的环境，例如那些不涉及明显战略推理的生成代理模拟（Park et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib54)）。此外，排除的还包括不需要动态环境调整或合作伙伴反馈的多代理协作任务解决场景。这些排除项涵盖了战略推理缺失或显著减少的环境和用例，确保我们专注于 LLM 在需要全面理解目标、竞争和环境动态的上下文中的战略应用。

## 3 个场景：将战略推理应用于 LLM 的地方

\forestset

every leaf node/.style= if n children=0#1 , every tree node/.style= if n children=0minimum width=1em#1 , {forest} for tree= every leaf node=my leaf, font=, every tree node=my node, font=, l sep-=4.5pt, l-=1.pt, anchor=west, inner sep=2pt, minimum height = 15pt, font=, l sep=8pt, s sep=2pt, fit=tight, grow’=east, edge=ultra thin, parent anchor=east, child anchor=west, if n children=0tier=last, edge path= [draw, \forestoptionedge] (!u.parent anchor) – +(5pt,0) |- (.child anchor)\forestoptionedge label; , if=isodd(n_children()) for children= if=equal(n,(n_children("!u")+1)/2)calign with current [场景, draw=gray, color=gray!100, fill=gray!15, very thick, text=black, text width=1.4cm, minimum height = 18pt [ 社会模拟, color=brightlavender!100, fill=brightlavender!15, very thick, text=black [ 社会行为, color=brightlavender!100, fill=brightlavender!15, very thick, text=black [ BigToM(Gandhi et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib21)), SOTOPIA (Zhou et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib94)), UGI (Xu et al., [2023a](https://arxiv.org/html/2404.01230v1#bib.bib82)), Suzuki & Arita ([2024](https://arxiv.org/html/2404.01230v1#bib.bib64)), OpenToM(Xu et al., [2024a](https://arxiv.org/html/2404.01230v1#bib.bib83)) , color=brightlavender!100, very thick, text=black, tier=E ] ] [ 辩论 &

谈判，颜色=亮紫色!100，填充=亮紫色!15，非常粗，文本=黑色 [ Fu 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib19))，Abdelnabi 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib1))，TRIP (Zhang 等，[2024a](https://arxiv.org/html/2404.01230v1#bib.bib90))，WarAgent (Hua 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib33))，Flamino 等 ([2024](https://arxiv.org/html/2404.01230v1#bib.bib18))，Taubenfeld 等 ([2024](https://arxiv.org/html/2404.01230v1#bib.bib67))，Tang 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib66))，Gemp 等 ([2024](https://arxiv.org/html/2404.01230v1#bib.bib23))，Hua 等 ([2024](https://arxiv.org/html/2404.01230v1#bib.bib34))，Schneider 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib59))，Lamparth 等 ([2024](https://arxiv.org/html/2404.01230v1#bib.bib41))，颜色=亮紫色!100，非常粗，文本=黑色，层级=E ] ] ] [ 经济模拟，颜色=浅珊瑚色!100，填充=浅珊瑚色!15，非常粗，文本=黑色 [ 经济学，颜色=浅珊瑚色!100，填充=浅珊瑚色!15，非常粗，文本=黑色 [ Horton ([2023](https://arxiv.org/html/2404.01230v1#bib.bib31))，Xie 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib81))，Chen 等 ([2023b](https://arxiv.org/html/2404.01230v1#bib.bib11))，Li 等 ([2023b](https://arxiv.org/html/2404.01230v1#bib.bib44))，颜色=浅珊瑚色!100，非常粗，文本=黑色，层级=latex 森林层级=D ] ] [ 商业，颜色=浅珊瑚色!100，填充=浅珊瑚色!15，非常粗，文本=黑色 [ Han 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib29))，TradingGPT (Li 等，[2023c](https://arxiv.org/html/2404.01230v1#bib.bib45))，CompeteAI (Zhao 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib93))，Chen 等 ([2023a](https://arxiv.org/html/2404.01230v1#bib.bib9))，OG-Narrator (Xia 等，[2024](https://arxiv.org/html/2404.01230v1#bib.bib80))，颜色=浅珊瑚色!100，非常粗，文本=黑色，层级=E ] ] ] [ 博弈论，颜色=青色!100，填充=青色!15，非常粗，文本=黑色 [ 矩阵游戏，颜色=青色!100，填充=青色!15，非常粗，文本=黑色 [ Guo ([2023](https://arxiv.org/html/2404.01230v1#bib.bib25))，Phelps & Russell ([2023](https://arxiv.org/html/2404.01230v1#bib.bib55))，MAgIC (Xu 等，[2023b](https://arxiv.org/html/2404.01230v1#bib.bib84))，Gandhi 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib20))，Brookins & DeBacker ([2023](https://arxiv.org/html/2404.01230v1#bib.bib6))，Fan 等 ([2024](https://arxiv.org/html/2404.01230v1#bib.bib15))，颜色=青色!100，非常粗，文本=黑色，层级=E ] ] [ 重复博弈，颜色=青色!100，填充=青色!15，非常粗，文本=黑色 [ Akata 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib4))，Alympics (Mao 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib49))，K-Level Reasoning (Zhang 等，[2024c](https://arxiv.org/html/2404.01230v1#bib.bib92))，Wu 等 ([2024b](https://arxiv.org/html/2404.01230v1#bib.bib78))，$\gamma$-Bench (Huang 等，[2024b](https://arxiv.org/html/2404.01230v1#bib.bib36))，颜色=青色!100，非常粗，文本=黑色，层级=E ] ] ] [ 游戏，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色 [ 对话游戏，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色 [ 狼人，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色，文本宽度=1.2cm [ Xu 等 ([2023d](https://arxiv.org/html/2404.01230v1#bib.bib87))，Xu 等 ([2023c](https://arxiv.org/html/2404.01230v1#bib.bib86))，Thinker (Wu 等，[2024a](https://arxiv.org/html/2404.01230v1#bib.bib77))，颜色=浅绿色!100，非常粗，文本=黑色，层级=D，文本宽度=4.45cm] ] [ Avalon，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色，文本宽度=1.2cm [ Avalonbench Light 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib46))，ReCon (Wang 等，[2023a](https://arxiv.org/html/2404.01230v1#bib.bib72))，（Lan 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib42))，颜色=浅绿色!100，非常粗，文本=黑色，层级=D，文本宽度=4.45cm] ] [ 外交，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色，文本宽度=1.2cm [ 福利外交 (Mukobi 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib51))，Cicero († 等（2022）（FAIR）†，Bakhtin、Brown、Dinan、Farina、Flaherty、Fried、Goff、Gray、Hu 等，[FAIR](https://arxiv.org/html/2404.01230v1#bib.bib14))，颜色=浅绿色!100，非常粗，文本=黑色，层级=D，文本宽度=4.45cm] ] [ 其他，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色，文本宽度=1.2cm [ MAgIC(Xu 等，[2023b](https://arxiv.org/html/2404.01230v1#bib.bib84))，Hoodwinked (O’Gara，[2023](https://arxiv.org/html/2404.01230v1#bib.bib52))，Tsai 等 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib68))，Li 等 ([2023a](https://arxiv.org/html/2404.01230v1#bib.bib43))，颜色=浅绿色!100，非常粗，文本=黑色，层级=D，文本宽度=4.45cm] ] ] [ 棋盘和纸牌游戏，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色 [ 扑克，颜色=浅绿色!100，填充=浅绿色!15，非常粗，文本=黑色，文本宽度=1.2cm [ SuspicionAgen (Guo 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib27))，PokerGPT (H

图 2：基于 LLM 的代理人的战略推理场景分类。

本文阐明了 LLM 在战略推理场景中的不同应用方面，展示了这些模型如何在各种环境中进行预测和适应。如图[2](https://arxiv.org/html/2404.01230v1#S3.F2 "图 2 ‣ 3 场景：在哪里应用 LLM 的战略推理 ‣ LLM 作为策划者：对大型语言模型战略推理的调查")所示，我们将这些场景分为社会模拟、经济模拟、博弈论和游戏。每个类别代表了需要战略推理的不同环境或条件，它们共同展示了 LLM 在理解和影响多代理动态方面的多样性和深度。

社会模拟专注于社会系统和互动的模拟，其中 LLM 用于建模和预测复杂社会背景下的人类行为。它涉及多个代理（个人或团体），其互动受社会规范、文化价值观和集体行为的影响。通过模拟这些互动，LLM 可以帮助理解社会趋势、决策过程以及政策或干预的影响。为了推进对 LLM 社会智能的研究，BigToM（Gandhi 等，[2024](https://arxiv.org/html/2404.01230v1#bib.bib21)）、SOTOPIA（Zhou 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib94)）和 OpenToM（Xu 等，[2024a](https://arxiv.org/html/2404.01230v1#bib.bib83)）被引入作为关键框架。这些工具旨在评估 LLM 理解人类心理状态以及其社交技能的能力。在政治辩论领域，Taubenfeld 等（[2024](https://arxiv.org/html/2404.01230v1#bib.bib67)）和 Tang 等（[2023](https://arxiv.org/html/2404.01230v1#bib.bib66)）批判性地评估了 LLM 在模拟类人互动方面的局限性，指出 LLM 代理尽管试图参与多样化的政治视角，但仍倾向于遵循固有的社会偏见。这突显了在实现公正和具有代表性的社会话语模拟方面的挑战。历史冲突的模拟，如 WarAgent（Hua 等，[2023](https://arxiv.org/html/2404.01230v1#bib.bib33)）中所展示的， exemplifies 了 LLM 驱动的 AI 系统重现和分析国际争端的潜力，为理解重大历史事件如世界大战和战国时期的决策及结果提供了新的视角。

经济模拟涉及市场动态、商业操作和财务决策过程的建模。在这种环境下，LLMs 被应用于理解和预测经济决策的结果，模拟市场竞争、资源分配和投资策略等场景。这些模拟需要战略推理以应对复杂的经济环境，根据对其他代理人行为的预测来优化结果。LLMs 展示了它们分析和参与经济系统的能力，展示了在货币和商业环境中的战略思维。[Horton](https://arxiv.org/html/2404.01230v1#bib.bib31)；[Chen et al.](https://arxiv.org/html/2404.01230v1#bib.bib11)；[Xie et al.](https://arxiv.org/html/2404.01230v1#bib.bib81)；[Li et al.](https://arxiv.org/html/2404.01230v1#bib.bib44) 已经为理解如何利用 LLM 提升代理人模拟招聘场景、在经济实验中展示理性决策及预测股票走势做出了贡献。这些研究突显了 LLM 模拟现实工作和消费决策的能力，可能重塑宏观经济建模。CompeteAI (Zhao et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib93)) 框架引入了一个与 GPT-4 模拟的竞争环境，重点关注餐厅和客户代理人之间的互动，这展示了商业竞争的动态。此外，AucArena (Chen et al., [2023a](https://arxiv.org/html/2404.01230v1#bib.bib9)) 展示了 LLM 如何有效参与拍卖，强调了这些模型的适应性和战略思维能力。

博弈论是研究理性决策者之间战略互动的学科。它本质上涉及战略推理，因为它涉及预测和应对在各种游戏环境中其他玩家的行动。参与博弈论模拟的 LLM 被测试在竞争、合作和混合动机情境中制定策略的能力。这不仅展示了 LLM 在抽象战略推理方面的优势，也展示了它们在实际场景中的应用，在这些场景中，理解和预测他人的行为至关重要。在博弈论领域，LLM 在分析和参与战略博弈方面发挥了重要作用，展示了它们在矩阵游戏和重复游戏中建模公平性和合作能力的能力，这在 Xu 等人（[2023b](https://arxiv.org/html/2404.01230v1#bib.bib84)）、Gandhi 等人（[2023](https://arxiv.org/html/2404.01230v1#bib.bib20)）和 Brookins & DeBacker（[2023](https://arxiv.org/html/2404.01230v1#bib.bib6)）的研究中得到了突出。对 Alympics（Mao 等人，[2023](https://arxiv.org/html/2404.01230v1#bib.bib49)）等框架和 k 级推理（Zhang 等人，[2024c](https://arxiv.org/html/2404.01230v1#bib.bib92)）等方法的持续研究展示了 LLM 在多轮战略思维中的熟练程度，提供了对它们长期战略规划能力的洞察。

在游戏（Gaming）的背景下，包括棋盘游戏（Feng et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib17); Kuo et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib40)）、纸牌游戏（Guo et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib27); Huang et al., [2024a](https://arxiv.org/html/2404.01230v1#bib.bib35); Zhang et al., [2024b](https://arxiv.org/html/2404.01230v1#bib.bib91)）和视频游戏（Ma et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib48); Agashe et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib2); Hu et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib32)），战略推理对成功至关重要。LLM 被用来理解游戏机制，制定获胜策略，并适应对手的战术。这一类别展示了 LLM 在互动娱乐中的战略深度参与和提升能力，反映了它们在动态且常常不可预测的环境中推理和决策的潜力。在像狼人杀、变色龙和亚瑟王等对话游戏中，Xu et al. ([2023d](https://arxiv.org/html/2404.01230v1#bib.bib87))、Wu et al. ([2024a](https://arxiv.org/html/2404.01230v1#bib.bib77))和 Light et al. ([2023](https://arxiv.org/html/2404.01230v1#bib.bib46))的研究展示了 LLM 如何增强代理之间的沟通、推理和欺骗检测。在棋盘游戏和纸牌游戏中，Guo et al. ([2023](https://arxiv.org/html/2404.01230v1#bib.bib27))和 Feng et al. ([2024](https://arxiv.org/html/2404.01230v1#bib.bib17))已展示 LLM 如何在扑克游戏中超越传统算法，并在国际象棋中整合策略学习。这些发现表明 LLM 的适用性超越了简单的模拟，可能会改变战略游戏玩法。电子游戏，包括《星际争霸》和《宝可梦》，也从 LLM 的整合中受益。TextStarCraft II（Ma et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib48)）和 PokeLLMon（Hu et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib32)）展示了 LLM 处理游戏信息、推荐策略和在战术战斗中展现与人类相当的表现的能力。

总的来说，LLM 在阐明和提升不同模拟中的战略推理方面至关重要，每个类别都提供了独特的见解和挑战。

## 4 Methods: How to Improve Strategic Reasoning with LLMs

为了提升大型语言模型（LLM）在战略推理挑战中的表现，近期出现了许多方法。我们根据这些方法的基本动机将其分为四类，如图[3](https://arxiv.org/html/2404.01230v1#S4.F3 "Figure 3 ‣ 4 Methods: How to Improve Strategic Reasoning with LLMs ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models")所示。

图 3：提升大型语言模型战略推理的方法。左上：提示工程；左下：模块增强；右上：心智理论；右下：与 LLMs 的模仿学习和强化学习。这些方法不是严格正交的，可以进行整合和互补。

提示工程（Prompt Engineering）指的是构建有效提示的技术和方法，以引导大型语言模型（LLMs）生成有影响力的输出。这包括基于学习的提示（In-context Learning（Brown et al., [2020](https://arxiv.org/html/2404.01230v1#bib.bib7); Wei et al., [2022](https://arxiv.org/html/2404.01230v1#bib.bib74)））和任务特定的提示（零样本链式思维（Kojima et al., [2022](https://arxiv.org/html/2404.01230v1#bib.bib39)））。由于涉及战略推理的任务相比于数学推理具有更复杂的背景，利用提示工程来帮助 LLMs 更清晰地理解场景是一种直接的方法。为了增强大型语言模型（LLMs）的情境意识，并利用游戏历史中的学习，Fu et al.（[2023](https://arxiv.org/html/2404.01230v1#bib.bib19)）、Xu et al.（[2023c](https://arxiv.org/html/2404.01230v1#bib.bib86)）、Wu et al.（[2023](https://arxiv.org/html/2404.01230v1#bib.bib76)）和 Hua et al.（[2024](https://arxiv.org/html/2404.01230v1#bib.bib34)）的研究集中于从历史游戏数据中检索进行 Incontext Learning（Brown et al., [2020](https://arxiv.org/html/2404.01230v1#bib.bib7)）。这些工作旨在通过反馈（Fu et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib19)）和反思（Xu et al., [2023c](https://arxiv.org/html/2404.01230v1#bib.bib86)）来提高 LLMs 在谈判和沟通游戏中的能力。这些研究展示了提示工程如何不仅提升 LLMs 在战略游戏和系统中的理解和参与，还提升其适应和改进这些技能的能力，突出 LLMs 在战略思维和决策中的潜力。

模块化增强代理通过集成记忆模块以重用成功策略和利用外部知识库检索有用信息或领域特定数据，展现了在战略推理场景（如游戏）中的卓越表现。为了增强 LLMs 的沟通和互动效果，Lan 等人（[2023](https://arxiv.org/html/2404.01230v1#bib.bib42)）提出了一个创新且全面的框架，旨在无缝适应 Avalon 游戏，包括用于总结、分析、规划和行动的模块。在谈判背景下，OG-Narrator（Xia 等人，[2024](https://arxiv.org/html/2404.01230v1#bib.bib80)）引入了一个确定性的报价生成器，用于调节买方提议的价格范围，并配备一个基于 LLM 的叙述器，为这些报价生成自然语言句子，实现了相对于基准的利润提升十倍。在复杂的游戏环境中，PokéLLMon（Hu 等人，[2024](https://arxiv.org/html/2404.01230v1#bib.bib32)）和 Thinker（Wu 等人，[2024a](https://arxiv.org/html/2404.01230v1#bib.bib77)）通过检索外部知识应对 LLM 代理面临的幻觉现象。StarCraft 中代理的战略能力一直是长期研究的兴趣所在。在这方面，TextStarCraft II（Ma 等人，[2023](https://arxiv.org/html/2404.01230v1#bib.bib48)）将大型语言模型（LLMs）应用于 StarCraft，引入了一种链式总结方法，包括单帧总结（用于处理原始观察数据）和多帧总结（用于分析游戏信息、提供指令建议以及生成战略决策）。这种全面提升的认知能力使代理在从简单决策到复杂战略推理和动态场景规划的广泛场景中更加自主和有效。

<svg class="ltx_picture" height="317.45" id="S4.p4.1.pic1" overflow="visible" version="1.1" width="476.07"><g transform="translate(0,317.45) matrix(1 0 0 -1 0 0) translate(1.66,0) translate(0,2.21)"><g fill="#000000" stroke="#000000"><g stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 7.66 149.08)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="38.44">2023.7</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 7.66 188.45)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="45.35">2023.10</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 7.66 239.64)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="38.44">2024.1</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 7.66 294.75)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="38.44">2024.3</foreignobject></g></g></g></g></svg>\forestset

每个叶节点/.style= if n children=0#1，每个树节点/.style= if n children=0minimum width=1em#1，{forest} for tree= scale=0.9，每个叶节点=my leaf，font=，每个树节点=my node，font=，l sep-=4.5pt，l-=1.pt，anchor=south，内边距=3pt，最小高度=15pt，font=，s=3pt，适应=紧凑，grow’=north，parent anchor=north，child anchor=south 方法，draw=gray，color=gray!100，fill=gray!15，非常厚，text=black，text width=1.5cm，[ 提示

工程，color=brightlavender!100，fill=brightlavender!15，非常厚，text=black，xshift=13mm，for tree=edge=brightlavender，非常厚，edge=brightlavender，线宽=1.6mm，edge path = [\forestoptionedge,--(0,0)$)..controls+(2:-3.7) .. ($(.childanchor)-(-4mm,0mm)$)\forestoptionedge 标签；[ Xie 等人 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib81))

Fu et al. ([2023](https://arxiv.org/html/2404.01230v1#bib.bib19))，颜色=brightlavender!100，极粗，文本=黑色，填充=白色，边缘路径=[\forestoptionedge，-] ($(!u.north)-(-2mm,-2mm)$) .. 控制点 +(-10:-4mm) .. ($(.childanchor)-(-3mm,0mm)$)\forestoptionedge 标签；，x 轴偏移=0mm，l=12mm] [ Xu et al. ([2023c](https://arxiv.org/html/2404.01230v1#bib.bib86))，颜色=brightlavender!100，极粗，文本=黑色，填充=白色，边缘路径=[\forestoptionedge，-] ($(!u.north)-(0mm,-12mm)$) .. 控制点 +(-10:-4mm) .. ($(.childanchor)-(-3mm,0mm)$)\forestoptionedge 标签；，x 轴偏移=2mm，l=24mm] [ Wu et al. ([2023](https://arxiv.org/html/2404.01230v1#bib.bib76))，颜色=brightlavender!100，极粗，文本=黑色，填充=白色，文本宽度=2cm，边缘路径=[\forestoptionedge，-] ($(!u.north)-(3mm,-24mm)$) .. 控制点 +(-10:-4mm) .. ($(.childanchor)-(-3mm,0mm)$)\forestoptionedge 标签；，x 轴偏移=0mm，l=36mm] [ Hua et al. ([2024](https://arxiv.org/html/2404.01230v1#bib.bib34))，颜色=brightlavender!100，极粗，文本=黑色，边缘=白色!0，线宽=0mm，边缘路径=[\forestoptionedge，-] ($(!u.north)-(1mm,-26mm)$) .. 控制点 +(10:6mm) .. ($(.childanchor)-(-9mm,0mm)$)\forestoptionedge 标签；，文本宽度=2.2cm，填充=白色，l=48mm] ] [ Modular

Enhancements，颜色=lightcoral!100，填充=lightcoral!15，极粗，文本=黑色，x 轴偏移=4mm，树的边缘=lightcoral，超粗，边缘=lightcoral，线宽=1.8mm，边缘路径=[\forestoptionedge，-] ($(!u.north)-(0,0)$)..控制点+(-2:-1.5) .. ($(.childanchor)-(0mm,0)$)\forestoptionedge 标签；[ Lan et al. ([2023](https://arxiv.org/html/2404.01230v1#bib.bib42))，颜色=lightcoral!100，极粗，文本=黑色，填充=白色，边缘路径=[\forestoptionedge，-] ($(!u.north)-(0mm,-6mm)$) .. 控制点 +(-10:-10mm) .. ($(.childanchor)-(-3mm,0mm)$)\forestoptionedge 标签；，x 轴偏移=-13mm，l=24mm] [ TextStarCraft II (Ma et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib48))

SwarmBrain (Shao et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib61))，颜色=lightcoral!100，极粗，文本=黑色，填充=白色，文本宽度=3.8cm，边缘路径=[\forestoptionedge，-] ($(!u.north)-(0mm,-18mm)$) .. 控制点 +(-10:-4mm) .. ($(.childanchor)-(-4mm,0mm)$)\forestoptionedge 标签；，x 轴偏移=-5mm，l=36mm] [ OG-Narrator (Xia et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib80))

Thinker (Wu et al., [2024a](https://arxiv.org/html/2404.01230v1#bib.bib77))

PokéLLMon (Hu et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib32))

，颜色为浅珊瑚色!100，线条粗细为很粗，文字颜色为黑色，边缘路径=[\forestoptionedge, -] ($(!u.north)-(0mm,-38mm)$) .. 控制点 +(-10:-4mm) .. ($(.childanchor)-(-4mm,0mm)$)\forestoptionedge 标签；，文字宽度为 3.6cm，x 轴偏移=-7mm，填充为白色，l=48mm] ] [ Theory Of Mind，颜色为青色!100，填充为青色!15，线条粗细为很粗，文字颜色为黑色，x 轴偏移=-8mm，树的边缘为青色，极粗，边缘为青色，线条宽度为 1.8mm，边缘路径=[\forestoptionedge, -] ($(!u.north)-(0,0)$) .. 控制点 +(2:1.14) .. ($(.childanchor)-(0,0)$)\forestoptionedge 标签；[ Lorè & Heydari ([2023](https://arxiv.org/html/2404.01230v1#bib.bib47))，颜色为青色!100，线条粗细为很粗，文字颜色为黑色，填充为白色，边缘路径=[\forestoptionedge, -] ($(!u.north)-(0,-2mm)$) .. 控制点 +(-10:-0.5) .. ($(.childanchor)-(0,0)$)\forestoptionedge 标签；，x 轴偏移=-14mm，文字宽度为 2.6cm，l=12mm] [ Suspicion-Agent (Guo et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib27))

ReCon (Wang et al., [2023a](https://arxiv.org/html/2404.01230v1#bib.bib72))

Chen et al. ([2023a](https://arxiv.org/html/2404.01230v1#bib.bib9))，Li et al. ([2023a](https://arxiv.org/html/2404.01230v1#bib.bib43))，颜色为青色!100，线条粗细为很粗，文字颜色为黑色，填充为白色，边缘路径=[\forestoptionedge, -] ($(!u.north)-(-2mm,-13mm)$) .. 控制点 +(-10:-0.2) .. ($(.childanchor)-(0,0)$)\forestoptionedge 标签；，文字宽度为 4.1cm，x 轴偏移=-11mm，l=24mm] [ MAgIC (Xu et al., [2023b](https://arxiv.org/html/2404.01230v1#bib.bib84))

SimToM (Wilf et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib75))，颜色为青色!100，线条粗细为很粗，文字颜色为黑色，填充为白色，文字宽度为 3.1cm，边缘路径=[\forestoptionedge, -] ($(!u.north)-(-3mm,-30mm)$) .. 控制点 +(-10:-0.1mm) .. ($(.childanchor)-(0,0)$)\forestoptionedge 标签；，文字宽度为 3.1cm，x 轴偏移=-8mm，l=36mm] [ K-Level Reasoning

(Zhang et al., [2024c](https://arxiv.org/html/2404.01230v1#bib.bib92))

TRIP (Zhang et al., [2024a](https://arxiv.org/html/2404.01230v1#bib.bib90))，颜色为青色!100，线条粗细为很粗，文字颜色为黑色，边缘路径=[\forestoptionedge, -] ($(!u.north)-(-4mm,-39mm)$) .. 控制点 +(-10:-0.1mm) .. ($(.childanchor)-(0,0)$)\forestoptionedge 标签；，文字宽度为 3cm，x 轴偏移=-8mm，填充为白色，l=48mm] [ 微调，颜色为浅绿色!100，填充为浅绿色!15，线条粗细为很粗，x 轴偏移=-18mm，文字颜色为黑色，树的边缘为浅绿色，极粗，边缘为浅绿色，线条宽度为 1.8mm，边缘路径=[\forestoptionedge, -] ($(!u.north)-(0,0)$) .. 控制点 +(-2:3.6) .. ($(.childanchor)-(1mm,0)$)\forestoptionedge 标签；[ Cicero († et al.(2022)(FAIR)†, Bakhtin, Brown, Dinan, Farina, Flaherty, Fried, Goff, Gray, Hu, et al., [FAIR](https://arxiv.org/html/2404.01230v1#bib.bib14))

ChessGPT (Feng et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib17)) , color=lightgreen!100, very thick, text=black, fill=white, edge path= [\forestoptionedge, -] ($(!u.north)-(0mm,-3mm)$) .. controls +(-10:0.1mm) .. ($(.childanchor)-(0,0)$)\forestoptionedge label; , xshift=-11mm, text width=3.4cm, l =12mm ] [ Retroformer (Yao et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib88))

Feng et al. ([2023](https://arxiv.org/html/2404.01230v1#bib.bib16))

Xu et al. ([2023d](https://arxiv.org/html/2404.01230v1#bib.bib87)) , color=lightgreen!100, very thick, text=black, fill=white, edge path= [\forestoptionedge, -] ($(!u.north)-(-2.5mm,-18mm)$) .. controls +(0:0mm) .. ($(.childanchor)-(0mm,0)$)\forestoptionedge label; , xshift=-6mm, text width=3.4cm, l =24mm ] [ LLaMAC (Zhang et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib89))

INA (Ahmad et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib3))

PokerGPT (Huang et al., [2024a](https://arxiv.org/html/2404.01230v1#bib.bib35))

CivRealm (Qi et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib56))

, color=lightgreen!100, very thick, text=black, fill=white, text width=4.2cm, edge path= [\forestoptionedge, -] ($(!u.north)-(-6mm,-29.5mm)$) .. controls +(0:0mm) .. ($(.childanchor)-(-1.5mm,0)$)\forestoptionedge label; , text width=3.7cm, xshift=-10mm, l =36mm ] [ Gemp et al. ([2024](https://arxiv.org/html/2404.01230v1#bib.bib23))

Agent-Pro (Zhang et al., [2024b](https://arxiv.org/html/2404.01230v1#bib.bib91))

Guo et al. ([2024a](https://arxiv.org/html/2404.01230v1#bib.bib26)) , color=lightgreen!100, very thick, text=black, edge path= [\forestoptionedge, -] ($(!u.north)-(-8mm,-47mm)$) .. controls +(0:0mm) .. ($(.childanchor)-(-3mm,0)$)\forestoptionedge label; , edge=white!0, line width=0mm, text width=3.6cm, fill=white, xshift=-5mm, l =51mm ] ] ]

图 4: 基于 LLM 的战略推理工作的概述。

心理理论（ToM）是战略推理中的一个关键概念，使得智能体能够基于他人的心理状态进行预测和策划。Gandhi 等人 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib20)) 和 Suspicion-Agent (Guo 等人，[2023](https://arxiv.org/html/2404.01230v1#bib.bib27)) 使用 ToM 框架将战略推理过程分解为搜索算法、价值评估和信念追踪环境，分别针对矩阵游戏和扑克进行调整。这种方法显著提升了大型语言模型（LLMs）的决策能力。SimTom (Wilf 等人，[2023](https://arxiv.org/html/2404.01230v1#bib.bib75)) 和 K-Level Reasoning (Zhang 等人，[2024c](https://arxiv.org/html/2404.01230v1#bib.bib92)) 证明，当使用对手特定的会话时，对对手行为的预测变得明显更为精准。K-Level Reasoning 进一步阐明，更广泛的对手行为历史记录可以提高预测准确性，展示了 LLMs 的动态适应性。这种适应性显著提升了 LLMs 在 DOOM 中的智能表现 (de Wynter，[2024](https://arxiv.org/html/2404.01230v1#bib.bib12))。此外，Li 等人 ([2023a](https://arxiv.org/html/2404.01230v1#bib.bib43)) 发现，LLMs 在合作任务中展现了 ToM 能力，其表现水平与这些任务中的强化学习基线相当。这些工作共同展示了 ToM 在丰富 LLMs 战略推理能力中的重要作用，揭示了其在各个领域变革决策过程的潜力。

将模仿学习和强化学习（RL）与 LLM 融合，也标志着战略推理能力的重大进展。冯等人 ([2023](https://arxiv.org/html/2404.01230v1#bib.bib16))、郭等人 ([2024a](https://arxiv.org/html/2404.01230v1#bib.bib26)) 和 ChessGPT（冯等人，[2024](https://arxiv.org/html/2404.01230v1#bib.bib17)）的研究在将大型语言模型（LLM）整合到国际象棋领域中起到了关键作用。为了提升 LLM 的国际象棋表现，采用了双重方法：首先，通过模拟人类玩家的经验智慧，从而吸收专家游戏中固有的复杂策略和战术决策；其次，利用 LLM 的预训练推理能力作为价值函数，直接提升其操作效能。Gemp 等人 ([2024](https://arxiv.org/html/2404.01230v1#bib.bib23)) 从更广泛的角度出发，将对话过程概念化为博弈理论构造。在这里，强化学习框架被用于改进 LLM 在复杂交互背景下的表现，如会议安排和公众辩论，展示了强化学习框架在传统游戏领域之外的广泛适用性，包括战略互动和决策过程。这些进展共同强调了将模仿和强化学习融入 LLM 的实用性，展示了它们在复杂决策景观中以前所未有的精细程度进行推理和导航的潜力。

需要注意的是，上述方法论类别之间的界限并非完全正交。例如，属于心智理论的方法可以通过提示工程实现，但其本质在于利用博弈论原理来提升 LLM 的表现，而不仅仅是提供示例以改进 LLM 对任务定义的理解。最后，图 [4](https://arxiv.org/html/2404.01230v1#S4.F4 "Figure 4 ‣ 4 Methods: How to Improve Strategic Reasoning with LLMs ‣ LLM as a Mastermind: A Survey of Strategic Reasoning with Large Language Models") 概述了用于提高 LLM 在战略推理任务中有效性的方法。

## 5 次评估：如何利用 LLM 评估战略推理

战略推理的评估包括在受控环境中测量结果，通过其性能指标如胜率（Qiao et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib57)）、生存率（Mao et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib49)）和奖励来衡量模型的效能。诸如 GTBench（Duan et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib13)）和 LLMArena（Chen et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib10)）等研究，以及其先进的评分系统如标准化相对优势（NRA）和 TrueSkill（Herbrich et al., [2006](https://arxiv.org/html/2404.01230v1#bib.bib30)），分别提供了这一分析的结构化框架。这些工具不仅量化了成功，还允许在各种游戏类型和难度水平之间进行比较，从而提供了 LLM 战略能力的全面视图。

在 LLMs 的战略推理评估中，还包括对推理过程的定量分析。针对游戏中的过程的指标关注于评估 LLM 在感知、预测和适应动态环境以及对手策略方面的能力。例如，MAgIC（Xu et al., [2023b](https://arxiv.org/html/2404.01230v1#bib.bib84)）评估 LLMs 在不完全信息条件下分析对手动作的准确性，而 K-Level Reasoning（Zhang et al., [2024c](https://arxiv.org/html/2404.01230v1#bib.bib92)）则评估基于公开信息预测行为的准确性。过程导向的评估在多智能体环境中至关重要，因为由于对手行为的不确定性，非平稳性会显著影响性能。准确预测对手行为对于减轻这种非平稳性的影响至关重要，从而提供 LLM 战略能力的更清晰视图。

此外，考虑到大语言模型（LLMs）的固有优势，例如其生成推理过程的能力，为评估战略推理提供了独特的视角。与仅关注结果的强化学习方法不同，LLMs 通过详细说明其推理步骤来提供可解释性。这一特征使得评估可以更加专注于模型的输出，从而更好地理解决策过程。因此，将这些见解整合到 LLMs 的定量评估中是至关重要的。

定性评估转向理解 LLM 中战略推理的基本机制，包括欺骗、合作、洞察等能力。这些方面对于在多代理互动中导航至关重要，其中战略的有效性通常取决于对手行为和游戏状态的动态和经常不可预测的性质。例如，在狼人游戏（Xu et al., [2023c](https://arxiv.org/html/2404.01230v1#bib.bib86)）或扑克（Guo et al., [2023](https://arxiv.org/html/2404.01230v1#bib.bib27)）中，有效的虚张声势或合作能力与最终的游戏结果一样能体现战略推理。

定量与定性评估的相互作用对全面理解 LLM 的战略推理能力至关重要。虽然定量分析提供了客观的基准，定性洞察则揭示了 LLM 在复杂现实场景中的战略深度和适应能力。这种双重方法不仅增强了评估框架的稳健性，还缓解了测量战略推理中认知过程固有的挑战。

## 6 讨论：LLM 战略推理的前景展望

### 6.1 LLM 代理真的能模拟人类战略推理吗？

尽管 LLM 和 LLM 代理在各种战略推理场景中得到了应用，一些研究声称在某些模拟中出现了类似人类的智能能力，但我们认为缺乏系统和严谨的研究来确定 LLM 可以在多大程度上模拟不同复杂性和认知难度的战略推理任务。这一系统性和严谨性的研究缺失导致了对 LLM 在这些背景下的可扩展性和局限性的理解存在差距。具体而言，尚不清楚不同规模和配置的 LLM 与其处理复杂战略环境中决策和预测任务的能力之间的关系。在缺乏这些知识的情况下，LLM 在战略推理中的应用可能变得随意，可能忽略了对模型能力、决策过程以及潜在偏见或不足的关键洞察。因此，更加结构化的研究和分类 LLM 在战略推理中的能力的方法对充分发挥其潜力并确保多代理战略模拟中的负责任发展和部署至关重要。

### 6.2 弥合鸿沟：统一基准的紧迫需求

战略推理中的一个关键挑战是缺乏统一的基准。虽然最近有一些基准（Xu et al., [2023b](https://arxiv.org/html/2404.01230v1#bib.bib84); Duan et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib13); Chen et al., [2024](https://arxiv.org/html/2404.01230v1#bib.bib10)）源自经典博弈论问题，但战略推理的广泛应用范围，从商业战略到复杂系统模拟，导致了针对新颖场景的定制解决方案的激增，而不是在明确基准内进行深入探索。这一趋势阻碍了直接方法比较，抑制了在共同标准下的进步。此外，如第五部分所述，在战略推理任务中，通常需要使用定量和定性相结合的评估方法来全面评估大型语言模型（LLMs）在推理过程和结果中的表现，这对设计统一基准提出了挑战。战略推理社区迫切需要合作创建适当的难度水平，认可的涵盖其多样应用的基准。这些基准将有助于算法性能评估、方法比较，并通过定义明确的指标、代表性数据集和评估协议来推动创新。这些努力可以统一领域，增强知识共享，并加速技术发展。

### 6.3 战略推理：对大型语言模型的挑战与机遇

战略推理在大型语言模型（LLMs）中呈现出独特的挑战。这些模型在预训练阶段依赖于下一个 token 的预测，善于从大量静态文本数据中学习模式（Sap et al., [2022](https://arxiv.org/html/2404.01230v1#bib.bib58)），但难以本质上理解战略推理的细微之处。这一限制源于战略推理需要理解多个主体之间复杂的动态互动，而这些互动不能仅从静态文本数据中直接推断出来。尽管如此，用于训练 LLMs 的大量数据使其能够建模广泛的行为和场景，间接捕捉战略思维的元素。通过设计将问题置于战略背景中的提示或算法，这些模型可以生成反映战略考虑的回应。

不过，问题仍然存在：仅仅通过增加通用 LLM 的参数数量和训练数据量，是否足以使通用 LLM 完全掌握战略推理？虽然更大的模型可以捕捉到更细致和复杂的模式，但战略推理根本上涉及理解意图、根据这些意图预测未来行动，并根据不断变化的情况动态调整策略。这些方面不仅仅是模型规模或数据量的函数。我们推测，即使是最强大的通用 LLM 也可能无法完全实现战略推理能力。

## 7 结论

总之，我们的综述突显了 LLM 在战略推理中的关键作用，展示了它们在各个领域复杂决策中的演变和显著优势。未来的努力应集中在跨学科合作上，以弥合理论进展和实际应用之间的差距，提升决策过程和战略发展。随着我们不断前进，对 LLM 的探索和改进有望在人工智能领域带来重大进展，为解决复杂问题和丰富互联世界中的战略决策开辟新途径。这呼吁研究人员和实践者共同努力，解锁 LLM 对战略推理的变革性影响。

#### 致谢

我们要感谢微软研究院（Jindong Wang）和华东师范大学（Li Cai 和 Xinshu Shen）的同事们，感谢他们的宝贵内部讨论和反馈。

## 参考文献

+   Abdelnabi 等（2023）Sahar Abdelnabi、Amr Gomaa、Sarath Sivaprasad、Lea Schönherr 和 Mario Fritz。《Llm-deliberation: Evaluating llms with interactive multi-agent negotiation games》。*arXiv 预印本 arXiv:2309.17234*，2023。

+   Agashe 等（2023）Saaket Agashe、Yue Fan 和 Xin Eric Wang。《Evaluating multi-agent coordination abilities in large language models》。*arXiv 预印本 arXiv:2310.03903*，2023。

+   Ahmad 等（2023）Zishan Ahmad、Suman Saurabh、Vaishakh Sreekanth Menon、Asif Ekbal、Roshni Ramnani 和 Anutosh Maitra。《Ina: An integrative approach for enhancing negotiation strategies with reward-based dialogue agent》。发表于*2023 年自然语言处理经验方法大会*，2023。

+   Akata 等（2023）Elif Akata、Lion Schulz、Julian Coda-Forno、Seong Joon Oh、Matthias Bethge 和 Eric Schulz。《Playing repeated games with large language models》。*arXiv 预印本 arXiv:2305.16867*，2023。

+   Arulkumaran 等（2017）Kai Arulkumaran、Marc Peter Deisenroth、Miles Brundage 和 Anil Anthony Bharath。《Deep reinforcement learning: A brief survey》。*IEEE 信号处理杂志*，34(6):26–38，2017。

+   布鲁金斯 & 德巴克（2023）菲利普·布鲁金斯和贾森·马修·德巴克。与 GPT 一起玩游戏：我们能从经典战略游戏中学到关于大型语言模型的什么？*在 SSRN 4493398 上可用*，2023。

+   布朗等（2020）汤姆·布朗、本杰明·曼恩、尼克·莱德、梅兰妮·萨比亚、贾里德·D·卡普兰、普拉夫拉·达里瓦尔、阿尔文德·尼拉坎坦、普拉纳夫·夏姆、吉里什·萨斯特里、阿曼达·阿斯克尔等。语言模型是少样本学习者。*《神经信息处理系统进展》*，33：1877–1901，2020。

+   布朗等（2012）卡梅伦·B·布朗、爱德华·鲍利、丹尼尔·怀特豪斯、西蒙·M·卢卡斯、彼得·I·考林、菲利普·罗尔夫沙根、斯蒂芬·塔文纳、迭戈·佩雷斯、斯皮里顿·萨莫特拉基斯、西蒙·科尔顿。一项关于蒙特卡罗树搜索方法的调查。*IEEE 计算智能与游戏人工智能期刊*，4（1）：1–43，2012。

+   陈等（2023a）江界陈、袁思雨、叶荣、博地萨特瓦·普拉萨德·马久姆德、凯尔·理查森。把钱投到嘴里去：评估拍卖领域中 llm 代理的战略规划和执行。*arXiv 预印本 arXiv:2310.05746*，2023a。

+   陈等（2024）陈军哲、胡旭明、刘硕迪、黄诗雨、涂伟伟、何兆丰、温丽洁。LLM Arena：评估大型语言模型在动态多智能体环境中的能力。*arXiv 预印本 arXiv:2402.16499*，2024。

+   陈等（2023b）陈怡婷、刘翠璇、游杉、钟松发。GPT 的经济理性出现。*《美国国家科学院院刊》*，120（51）：e2316205120，2023b。

+   德·温特（2024）阿德里安·德·温特。gpt-4 会导致灾难吗？*arXiv 预印本 arXiv:2403.05468*，2024。

+   段等（2024）段金浩、张仁名、詹姆斯·迪芬德费尔、布哈维亚·凯尔库拉、孙力超、伊利亚斯·斯坦格尔-埃斯金、莫希特·班萨尔、陈天龙、徐凯迪。Gtbench：通过博弈论评估揭示 llms 的战略推理限制。*arXiv 预印本 arXiv:2402.12348*，2024。

+   （14）Meta 基础人工智能研究外交团队（FAIR）†，安东·巴赫廷、诺亚·布朗、艾米丽·迪南、加布里埃尔·法里纳、科林·弗拉赫提、丹尼尔·弗里德、安德鲁·戈夫、乔纳森·格雷、恒源·胡等。通过将语言模型与战略推理相结合，实现游戏“外交”的人类级别玩法。*《科学》*，378（6624）：1067–1074，2022。

+   范等（2024）曹云范、陈进斗、金耀辉、何昊。大型语言模型能否作为博弈论中的理性参与者？一种系统的分析。在 *《AAAI 人工智能会议论文集》*，第 38 卷，第 17960–17967 页，2024。

+   冯等（2023）冯西东、万子瑜、文沐宁、文颖、张伟南、王军。类似 AlphaZero 的树搜索可以指导大型语言模型的解码和训练。*arXiv 预印本 arXiv:2309.17179*，2023。

+   冯等（2024）冯西东、罗一诚、王子炎、唐洪瑞、杨梦月、邵昆、大卫·姆古尼、杜雅丽、王军。ChessGPT：桥接策略学习与语言建模。*《神经信息处理系统进展》*，第 36 卷，2024。

+   Flamino et al. (2024) 詹姆斯·弗拉米诺、穆罕默德·沙希德·莫迪、博莱斯瓦夫·K·什济曼斯基、布伦丹·克罗斯和科尔顿·米科拉伊奇克。《大型语言模型在与人类辩论中的局限性》。*arXiv 预印本 arXiv:2402.06049*，2024 年。

+   Fu et al. (2023) 傅瑶、彭浩、图沙尔·科特和米雷拉·拉帕塔。《利用自我对弈和来自 AI 反馈的上下文学习提升语言模型的谈判能力》。*arXiv 预印本 arXiv:2305.10142*，2023 年。

+   Gandhi et al. (2023) 卡尼什克·甘地、多尔萨·萨迪赫和诺亚·D·古德曼。《利用语言模型进行战略推理》。*arXiv 预印本 arXiv:2305.19165*，2023 年。

+   Gandhi et al. (2024) 卡尼什克·甘地、简-菲利普·弗兰肯、托比亚斯·格尔斯滕贝格和诺亚·古德曼。《利用语言模型理解语言模型中的社会推理》。*神经信息处理系统进展*，36，2024 年。

+   Gao et al. (2023) 高辰、蓝晓翀、李念、袁袁、丁晶涛、周志伦、徐风力和李勇。《大型语言模型赋能的基于代理的建模与模拟：综述与展望》。*arXiv 预印本 arXiv:2312.11970*，2023 年。

+   Gemp et al. (2024) 伊恩·根普、约拉姆·巴赫拉赫、马克·兰克托、罗玛·帕特尔、维瓦瓦里·达萨吉、卢克·马里斯、乔治奥斯·皮利乌拉斯和卡尔·图伊尔斯。《状态作为字符串作为策略：利用博弈论求解器引导语言模型》。*arXiv 预印本 arXiv:2402.01704*，2024 年。

+   Gronauer & Diepold (2022) 斯文·格罗瑙尔和克劳斯·迪波尔德。《多智能体深度强化学习：综述》。*人工智能评论*，55(2):895–943，2022 年。

+   Guo (2023) 郭富林。《游戏理论实验中的 GPT》。2023 年。

+   Guo et al. (2024a) 郭鸿义、刘智涵、张宇峰和王兆然。《大型语言模型能否进行游戏？自我对弈方法的案例研究》。*arXiv 预印本 arXiv:2403.05632*，2024a。

+   Guo et al. (2023) 郭家贤、杨博、保罗·尤、林玉辰、岩沢悠介和松尾丰。《怀疑代理：利用具有理论意识的 GPT-4 玩不完全信息游戏》。*arXiv 预印本 arXiv:2309.17277*，2023 年。

+   Guo et al. (2024b) 郭太成、陈秀英、王雅琪、常瑞迪、裴世超、Nitesh V Chawla、Olaf Wiest 和张向亮。《基于大型语言模型的多智能体：进展与挑战综述》。*arXiv 预印本 arXiv:2402.01680*，2024b。

+   Han et al. (2023) 韩旭、吴增庆和肖川。《利用 GPT 的“试验小白鼠”：一种用于研究公司竞争和共谋的新型智能代理建模方法》。*arXiv 预印本 arXiv:2308.10974*，2023 年。

+   Herbrich et al. (2006) 拉尔夫·赫布里希、汤姆·敏卡和托尔·格雷佩尔。《Trueskill™：一种贝叶斯技能评级系统》。*神经信息处理系统进展*，19，2006 年。

+   Horton (2023) 约翰·J·霍顿。《大型语言模型作为模拟经济代理：我们能从 homo silicus 中学到什么？》技术报告，美国国家经济研究局，2023 年。

+   Hu et al. (2024) 胡思浩、黄天生和刘玲。《Pok$\backslash$’ellmon：用于 Pokémon 战斗的人类水平代理与大型语言模型》。*arXiv 预印本 arXiv:2402.01118*，2024 年。

+   Hua 等人 (2023) Wenyue Hua、Lizhou Fan、Lingyao Li、Kai Mei、Jianchao Ji、Yingqiang Ge、Libby Hemphill 和 Yongfeng Zhang。战争与和平（waragent）：基于大语言模型的世界大战多智能体模拟。*arXiv 预印本 arXiv:2311.17227*，2023。

+   Hua 等人 (2024) Yuncheng Hua、Lizhen Qu 和 Gholamreza Haffari。用于社会意识谈判对话的辅助大语言模型代理。*arXiv 预印本 arXiv:2402.01737*，2024。

+   Huang 等人 (2024a) Chenghao Huang、Yanbo Cao、Yinlong Wen、Tao Zhou 和 Yanru Zhang。Pokergpt：通过大语言模型为多人德州扑克提供的端到端轻量级求解器。*arXiv 预印本 arXiv:2401.06781*，2024a。

+   Huang 等人 (2024b) Jen-tse Huang、Eric John Li、Man Ho Lam、Tian Liang、Wenxuan Wang、Youliang Yuan、Wenxiang Jiao、Xing Wang、Zhaopeng Tu 和 Michael R Lyu。我们在 llms 的决策制定上还差多远？评估 llms 在多智能体环境中的游戏能力。*arXiv 预印本 arXiv:2403.11807*，2024b。

+   Huh & Mohapatra (2023) Dom Huh 和 Prasant Mohapatra。多智能体强化学习：一项全面的综述。*arXiv 预印本 arXiv:2312.10256*，2023。

+   Johnson-Laird (1999) Philip N Johnson-Laird。演绎推理。*心理学年评*，50(1)：109–135，1999。

+   Kojima 等人 (2022) Takeshi Kojima、Shixiang Shane Gu、Machel Reid、Yutaka Matsuo 和 Yusuke Iwasawa。大语言模型是零样本推理者。*神经信息处理系统进展*，35：22199–22213，2022。

+   Kuo 等人 (2023) Mu-Tien Kuo、Chih-Chung Hsueh 和 Richard Tzong-Han Tsai。棋盘上的大语言模型：关于 ChatGPT 的正式语言理解和复杂推理能力的研究。*arXiv 预印本 arXiv:2308.15118*，2023。

+   Lamparth 等人 (2024) Max Lamparth、Anthony Corso、Jacob Ganz、Oriana Skylar Mastro、Jacquelyn Schneider 和 Harold Trinkunas。人类 vs. 机器：语言模型与战争游戏。*arXiv 预印本 arXiv:2403.03407*，2024。

+   Lan 等人 (2023) Yihuai Lan、Zhiqiang Hu、Lei Wang、Yang Wang、Deheng Ye、Peilin Zhao、Ee-Peng Lim、Hui Xiong 和 Hao Wang。基于 llm 的代理社会调查：在 Avalon 游戏中的合作与对抗。*arXiv 预印本 arXiv:2310.14985*，2023。

+   Li 等人 (2023a) Huao Li、Yu Quan Chong、Simon Stepputtis、Joseph Campbell、Dana Hughes、Michael Lewis 和 Katia Sycara。通过大语言模型进行多智能体协作的心智理论。*arXiv 预印本 arXiv:2310.10701*，2023a。

+   Li 等人 (2023b) Nian Li、Chen Gao、Yong Li 和 Qingmin Liao。大语言模型赋能的代理用于模拟宏观经济活动。*arXiv 预印本 arXiv:2310.10436*，2023b。

+   Li 等人 (2023c) Yang Li、Yangyang Yu、Haohang Li、Zhi Chen 和 Khaldoun Khashanah。Tradinggpt：具有分层记忆和不同角色的多智能体系统，以提升金融交易表现。*arXiv 预印本 arXiv:2309.03736*，2023c。

+   Light 等人（2023）Jonathan Light、Min Cai、Sheng Shen 和 Ziniu Hu。Avalonbench：评估大语言模型玩 Avalon 游戏的表现。在 *NeurIPS 2023 Foundation Models for Decision Making Workshop*，2023 年。

+   Lorè & Heydari（2023）Nunzio Lorè 和 Babak Heydari。大语言模型的战略行为：游戏结构与上下文框架。*arXiv 预印本 arXiv:2309.05898*，2023 年。

+   Ma 等人（2023）Weiyu Ma、Qirui Mi、Xue Yan、Yuqiao Wu、Runji Lin、Haifeng Zhang 和 Jun Wang。大型语言模型玩《星际争霸 II》：基准测试与链式总结方法。*arXiv 预印本 arXiv:2312.11865*，2023 年。

+   Mao 等人（2023）Shaoguang Mao、Yuzhe Cai、Yan Xia、Wenshan Wu、Xun Wang、Fengyi Wang、Tao Ge 和 Furu Wei。Alympics：语言代理与博弈论的结合。*arXiv 预印本 arXiv:2311.03220*，2023 年。

+   Miao 等人（2021）Shen-Yun Miao、Chao-Chun Liang 和 Keh-Yih Su。用于评估和开发英语数学问题求解器的多样化语料库。*arXiv 预印本 arXiv:2106.15772*，2021 年。

+   Mukobi 等人（2023）Gabriel Mukobi、Hannah Erlebach、Niklas Lauffer、Lewis Hammond、Alan Chan 和 Jesse Clifton。福利外交：语言模型合作的基准测试。*arXiv 预印本 arXiv:2310.08901*，2023 年。

+   O’Gara（2023）Aidan O’Gara。被蒙蔽的：语言模型文本游戏中的欺骗与合作。*arXiv 预印本 arXiv:2308.01404*，2023 年。

+   Ouyang 等人（2022）Long Ouyang、Jeffrey Wu、Xu Jiang、Diogo Almeida、Carroll Wainwright、Pamela Mishkin、Chong Zhang、Sandhini Agarwal、Katarina Slama、Alex Ray 等人。通过人工反馈训练语言模型以遵循指令。*神经信息处理系统进展*，35:27730–27744，2022 年。

+   Park 等人（2023）Joon Sung Park、Joseph O’Brien、Carrie Jun Cai、Meredith Ringel Morris、Percy Liang 和 Michael S Bernstein。生成代理：人类行为的互动模拟。发表于 *第 36 届 ACM 用户界面软件与技术年会论文集*，第 1–22 页，2023 年。

+   Phelps & Russell（2023）Steve Phelps 和 Yvan I Russell。使用实验经济学调查大语言模型中出现的目标行为。*arXiv 预印本 arXiv:2305.07970*，2023 年。

+   Qi 等人（2024）Siyuan Qi、Shuo Chen、Yexin Li、Xiangyu Kong、Junqi Wang、Bangcheng Yang、Pring Wong、Yifan Zhong、Xiaoyuan Zhang、Zhaowei Zhang 等人。Civrealm：决策代理在文明中的学习与推理历程。*arXiv 预印本 arXiv:2401.10568*，2024 年。

+   Qiao 等人（2023）Dan Qiao、Chenfei Wu、Yaobo Liang、Juntao Li 和 Nan Duan。Gameeval：对会话游戏中的大语言模型进行评估。*arXiv 预印本 arXiv:2308.10032*，2023 年。

+   Sap 等人（2022）Maarten Sap、Ronan LeBras、Daniel Fried 和 Yejin Choi。神经心智理论？大语言模型社会智能的局限性。*arXiv 预印本 arXiv:2210.13312*，2022 年。

+   Schneider et al. (2023) Johannes Schneider，Steffi Haag 和 Leona Chandra Kruse. 与 LLMs 谈判：提示技巧、技能差距和推理缺陷。*arXiv preprint arXiv:2312.03720*，2023。

+   Shamay-Tsoory et al. (2009) Simone G Shamay-Tsoory，Judith Aharon-Peretz 和 Daniella Perry. 同理心的两个系统：情感同理心与认知同理心在下额回与腹内侧前额叶损伤中的双重分离。*Brain*，132(3):617–627，2009。

+   Shao et al. (2024) Xiao Shao，Weifu Jiang，Fei Zuo 和 Mengqing Liu. Swarmbrain：通过大型语言模型的实时战略游戏《星际争霸 II》的具身代理。*arXiv preprint arXiv:2401.17749*，2024。

+   Siegel (2013) Eric Siegel. *Predictive analytics: The power to predict who will click, buy, lie, or die*。John Wiley & Sons，2013。

+   Silver et al. (2017) David Silver，Julian Schrittwieser，Karen Simonyan，Ioannis Antonoglou，Aja Huang，Arthur Guez，Thomas Hubert，Lucas Baker，Matthew Lai，Adrian Bolton 等。无需人类知识掌握围棋游戏。*nature*，550(7676):354–359，2017。

+   Suzuki & Arita (2024) Reiji Suzuki 和 Takaya Arita. 使用大型语言模型的与合作行为相关的人格特质进化模型。*Scientific Reports*，14(1):5989，2024。

+   Talmor et al. (2022) Alon Talmor，Ori Yoran，Ronan Le Bras，Chandra Bhagavatula，Yoav Goldberg，Yejin Choi 和 Jonathan Berant. Commonsenseqa 2.0：通过游戏化揭示人工智能的局限性。*arXiv preprint arXiv:2201.05320*，2022。

+   Tang et al. (2023) Xiangru Tang，Anni Zou，Zhuosheng Zhang，Yilun Zhao，Xingyao Zhang，Arman Cohan 和 Mark Gerstein. Medagents：作为零-shot 医疗推理的合作者的大型语言模型。*arXiv preprint arXiv:2311.10537*，2023。

+   Taubenfeld et al. (2024) Amir Taubenfeld，Yaniv Dover，Roi Reichart 和 Ariel Goldstein. LLM 模拟辩论中的系统性偏差。*arXiv preprint arXiv:2402.04049*，2024。

+   Tsai et al. (2023) CF Tsai，X Zhou，SS Liu，J Li，M Yu 和 H Mei. 大型语言模型能否很好地玩文本游戏。*Current State-of-the-Art and Open Questions*，2023。

+   van de Vijver & Willemsen (1993) Fons JR van de Vijver 和 Madde E Willemsen. 抽象思维。在 *Advances in psychology*，第 103 卷，第 317–342 页。Elsevier，1993。

+   Van Der Hoek et al. (2005) Wiebe Van Der Hoek，Wojciech Jamroga 和 Michael Wooldridge. 战略推理的逻辑。在 *Proceedings of the fourth international joint conference on Autonomous agents and multiagent systems*，第 157–164 页，2005。

+   Wang et al. (2024) Lei Wang，Chen Ma，Xueyang Feng，Zeyu Zhang，Hao Yang，Jingsen Zhang，Zhiyuan Chen，Jiakai Tang，Xu Chen，Yankai Lin 等。基于大型语言模型的自主代理调查。*Frontiers of Computer Science*，18(6):1–26，2024。

+   Wang et al. (2023a) Shenzhi Wang, Chang Liu, Zilong Zheng, Siyuan Qi, Shuo Chen, Qisen Yang, Andrew Zhao, Chaofei Wang, Shiji Song, 和 Gao Huang. 亚瓦龙的思想游戏：通过递归思考对抗欺骗。*arXiv 预印本 arXiv:2310.01320*，2023a。

+   Wang et al. (2023b) Zhenhailong Wang, Shaoguang Mao, Wenshan Wu, Tao Ge, Furu Wei, 和 Heng Ji. 释放大语言模型中的涌现认知协同：通过多重自我协作解决任务的智能体。*arXiv 预印本 arXiv:2307.05300*，2023b。

+   Wei et al. (2022) Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Fei Xia, Ed Chi, Quoc V Le, Denny Zhou, 等等。链式思维提示引发大语言模型中的推理。*神经信息处理系统进展*，35:24824–24837，2022。

+   Wilf et al. (2023) Alex Wilf, Sihyun Shawn Lee, Paul Pu Liang, 和 Louis-Philippe Morency. 三思而后行：观点采纳提升大语言模型的理论思维能力。*arXiv 预印本 arXiv:2311.10227*，2023。

+   Wu et al. (2023) Dekun Wu, Haochen Shi, Zhiyuan Sun, 和 Bang Liu. 解码数字侦探：理解多智能体悬疑游戏中的大语言模型行为和能力。*arXiv 预印本 arXiv:2312.00746*，2023。

+   Wu et al. (2024a) Shuang Wu, Liwen Zhu, Tao Yang, Shiwei Xu, Qiang Fu, Yang Wei, 和 Haobo Fu. 在狼人游戏中增强大语言模型的推理能力。*arXiv 预印本 arXiv:2402.02330*，2024a。

+   Wu et al. (2024b) Zengqing Wu, Shuyuan Zheng, Qianying Liu, Xu Han, Brian Inhyuk Kwon, Makoto Onizuka, Shaojie Tang, Run Peng, 和 Chuan Xiao. 我们可以谈谈吗：探索竞争的大语言模型智能体的自发协作。*arXiv 预印本 arXiv:2402.12327*，2024b。

+   Xi et al. (2023) Zhiheng Xi, Wenxiang Chen, Xin Guo, Wei He, Yiwen Ding, Boyang Hong, Ming Zhang, Junzhe Wang, Senjie Jin, Enyu Zhou, 等等。大语言模型基础智能体的崛起与潜力：一项综述。*arXiv 预印本 arXiv:2309.07864*，2023。

+   Xia et al. (2024) Tian Xia, Zhiwei He, Tong Ren, Yibo Miao, Zhuosheng Zhang, Yang Yang, 和 Rui Wang. 测量大语言模型的议价能力：一个基准和一种买方增强方法。*arXiv 预印本 arXiv:2402.15813*，2024。

+   Xie et al. (2023) Qianqian Xie, Weiguang Han, Yanzhao Lai, Min Peng, 和 Jimin Huang. 华尔街新手：对 ChatGPT 在多模态股票走势预测挑战中的零-shot 分析。*arXiv 预印本 arXiv:2304.05351*，2023。

+   Xu et al. (2023a) Fengli Xu, Jun Zhang, Chen Gao, Jie Feng, 和 Yong Li. 城市生成智能（ugi）：在具身城市环境中为智能体提供的基础平台。*arXiv 预印本 arXiv:2312.11813*，2023a。

+   Xu et al. (2024a) Hainiu Xu, Runcong Zhao, Lixing Zhu, Jinhua Du, 和 Yulan He. Opentom：评估大语言模型理论思维推理能力的综合基准。*arXiv 预印本 arXiv:2402.06044*，2024a。

+   Xu et al. (2023b) 林徐、智远胡、大全周、宏宇任、振东、库尔特·凯泽、希-强·吴 和 嘉实·冯。魔法：对大型语言模型驱动的多智能体在认知、适应性、理性和协作中的调查。见于*ICLR 2024 大型语言模型（LLM）代理人研讨会*，2023b。

+   Xu et al. (2024b) 欣润徐、宇鑫王、超逸徐、子洛丁、杰川姜、志明丁 和 博耶·F·卡尔松。关于游戏代理和大型模型的调查：方法、应用和挑战。*arXiv 预印本 arXiv:2403.10249*，2024b。

+   Xu et al. (2023c) 玉壮徐、硕王、鹏李、富文罗、晓龙王、卫东刘 和 杨刘。探索用于交流游戏的大型语言模型：关于狼人杀的实证研究。*arXiv 预印本 arXiv:2309.04658*，2023c。

+   Xu et al. (2023d) 泽莱徐、超宇、飞方、于王 和 易吴。用于狼人杀游戏的强化学习语言代理。*arXiv 预印本 arXiv:2310.18940*，2023d。

+   Yao et al. (2023) 伟然姚、谢尔比·海内克、胡安·卡洛斯·尼布莱斯、志伟刘、易豪丰、乐雪、里特什·穆尔提、泽远陈、建国张、德万什·阿皮特 等。Retroformer：带有策略梯度优化的回顾性大型语言代理。*arXiv 预印本 arXiv:2308.02151*，2023。

+   Zhang et al. (2023) 彬张、杭宇毛、静清阮、颖文、杨李、韶张、志伟徐、大鹏李、子岳李、瑞赵 等。控制基于大型语言模型的代理进行大规模决策：一种演员-评论家方法。*arXiv 预印本 arXiv:2311.13884*，2023。

+   Zhang et al. (2024a) 通张、陈黄、杨邓、宏如梁、佳刘、祖杰温、闻强雷 和 达特-盛·蔡。力量在于差异！通过量体裁衣的战略规划实现有效的非协作对话。*arXiv 预印本 arXiv:2403.06769*，2024a。

+   Zhang et al. (2024b) 闻启张、柯唐、海吴、孟娜王、永亮申、桂阳侯、泽琪谭、鹏李、跃廷庄 和 伟名陆。Agent-pro：通过策略级反思和优化学习进化。*arXiv 预印本 arXiv:2402.17574*，2024b。

+   Zhang et al. (2024c) 亚东张、少光毛、陶葛、迅王、彦夏、满兰 和 富如魏。与大型语言模型的 K 级推理。*arXiv 预印本 arXiv:2402.01521*，2024c。

+   Zhao et al. (2023) 琴林赵、劲东王、益轩张、宜桥金、开杰朱、浩陈 和 兴谢。Competeai：理解基于大型语言模型的代理人的竞争行为。*arXiv 预印本 arXiv:2310.17512*，2023。

+   Zhou et al. (2023) 旭辉周、浩朱、莉娜·马图尔、若宏张、浩飞于、正阳齐、路易斯-菲利普·莫伦西、约纳坦·比斯克、丹尼尔·弗里德、格雷厄姆·纽比 等。Sotopia：用于语言代理的社会智能互动评估。*arXiv 预印本 arXiv:2310.11667*，2023。

## 附录 A 附录

### A.1 推理的认知技能

逻辑推理指的是通过应用明确的逻辑规则（Johnson-Laird，[1999](https://arxiv.org/html/2404.01230v1#bib.bib38)）从前提得出结论的能力。这种推理模式通常遵循形式逻辑的原则，包括演绎推理和归纳推理。演绎推理涉及从一般到具体的过程，其中结论是基于普遍真理得出的。相反，归纳推理是从具体到一般的过程，其中从具体观察中推断出一般结论。逻辑推理需要识别和应用逻辑关系，如因果关系、等价关系和矛盾。

上下文智能指的是在特定背景或情境中理解和解读信息的能力。它涉及识别和解读背景、社会规范以及隐含的意义。此能力要求捕捉给定情境中的细微线索，并理解对话、事件或文本的意义。上下文智能对于语言理解、同理共鸣和社交互动是不可或缺的。

预测分析指的是基于现有信息预测未来事件或趋势的能力（Siegel，[2013](https://arxiv.org/html/2404.01230v1#bib.bib62)）。这包括分析数据、识别模式和趋势，并利用这些信息做出明智的预测。预测能力要求整合过去和现在的信息，使用概率和统计方法，并推理可能的未来情景。

抽象思维是理解超越具体和直接经验的概念、原则和模型的能力（van de Vijver & Willemsen，[1993](https://arxiv.org/html/2404.01230v1#bib.bib69)）。这种思维涉及概括、分类和概念化能力，使个人能够识别不同情境中的相似性和差异，并应用广泛的原则来解决问题。抽象思维对于创新、理论发展和复杂问题解决至关重要。

认知同理心是理解他人思维和感受的技能（Shamay-Tsoory et al., [2009](https://arxiv.org/html/2404.01230v1#bib.bib60)）。认知同理心包括几个方面：1. 视角采择：自然地从他人的角度看问题；2. 幻想：能够将虚构角色与现实联系起来；3. 战术同理心：有意使用视角采择以实现特定目标；4. 情感调节：能够同情他人的情感而不被其压倒。

### A.2 战略推理的符号系统

#### A.2.1 战略推理环境的制定

图 5：多智能体系统（MAS）战略推理中的环境。

我们将战略推理环境称为“游戏”（’GAME’）。形式上，游戏是一个四元组 $\left\langle\mathcal{N},\mathcal{A},\mathcal{H},\mathcal{Z},u,\mathcal{I}\right\rangle$，其中：

+   •

    $\mathcal{N}=\{1,2,...,n\}$ 是一组 $n$ 个代理。在 LLM 基础的代理参与者的初始化中，系统消息是配置所必需的，通常包括角色设定、目标对齐和功能声明。系统消息以消息的形式传递给 LLM，以影响 LLM 的表现。

+   •

    $\mathcal{A}$ 是代理可以采取的行动集合。这是一个全局的状态无关的行动集合；通常，在每个决策点，每个玩家只有合法行动的一个子集可用。LLM 的行动本质上是指 LLM 在给定对话历史或提示时的文本回应。在对话环境中，如辩论场景中，LLM 的任何输出都被视为行动。而在具有定义的有限行动集合的场景中，如投票、竞标、扑克等，LLM 的输出需要解析到一个合法的功能空间中。

+   •

    $\mathcal{H}$ 是一组游戏历史。历史记录是从游戏开始起的一系列行动（包括机会节点“行动”或结果）。在基于 LLM 的环境中，历史信息包括所有玩家对话历史的并集。

+   •

    $\mathcal{Z}\subseteq\mathcal{H}$ 是一组终局历史，每个历史代表一个完成（完全玩过）的游戏。

+   •

    $u:\mathcal{Z}\rightarrow\Delta_{u}^{n}\subseteq\mathfrak{R}^{n}$，其中 $\Delta_{u}=[u_{min},u_{max}]$ 是一个效用（或收益）函数，在游戏结束时给每个玩家分配一个收益，$u_{min}$ 和 $u_{max}$ 是这些收益的下限和上限。

+   •

    $\mathcal{I}$ 是一组信息状态。一般而言，$\mathcal{I}$ 是 $\mathcal{H}$ 的一个划分，使得每个 $i\in\mathcal{I}$ 包含历史记录。在这些状态下玩家做出决策。在基于 LLM 的环境中，每个玩家的信息状态是可观察的对话历史，以及他们自己的行动历史和私人信息。

#### A.2.2 目标

在战略推理领域，我们探讨一个由多个代理组成的环境，每个代理都具备进行复杂推理过程的能力。这些代理在环境中进行导航，目的是实现各自的目标。通过应用战略推理，每个代理评估各种行动的潜在结果，不仅考虑自身的目标，还考虑同一环境中其他代理的可能行动。这种复杂的决策和预期的舞蹈使每个代理能够选择最有可能实现其目标的行动。

令 $u_{i}(s)$ 表示在策略配置 $s$ 下玩家 $i$ 的预期效用。在战略推理中，玩家的目标是最大化他们的预期效用，这可以用符号表示为：

|  | $\max_{s_{i}\in S_{i}}E[u_{i}(s_{i},s_{-i})]$ |  |
| --- | --- | --- |

其中 $s_{-i}$ 代表除玩家 $i$ 外所有其他玩家的策略，$E[\cdot]$ 表示期望算子，基于玩家 $i$ 对其他玩家行动的信念。

### A.3 大型语言模型与强化学习的战略推理

在战略推理中，大型语言模型（LLMs）和强化学习（RL）代表了截然不同但互补的方法。LLMs 在生成连贯语言和利用广泛知识方面表现出色，使其非常适合需要创造力和深刻理解的复杂问题解决，如商业战略制定或地缘政治分析。相反，RL 在通过与环境的试错交互学习最佳行动方面表现出色，适合需要动态决策的场景，如自主系统和游戏优化。然而，这两种方法都面临挑战：LLMs 可能继承其训练数据中的偏见，而 RL 的有效性依赖于精确的奖励定义和环境建模。未来可能会出现结合 LLMs 的全面知识处理与 RL 的自适应决策的协同模型，预示着在多样化和复杂场景中增强战略推理的前景。

| 标准 | 大型语言模型 | 强化学习 |
| --- | --- | --- |
| 知识基础 | 来自多样数据集的广泛知识 | 从特定环境中获得 |
| 语境理解 | 在语言任务中表现优秀 | 限于特定状态空间 |
| 决策制定 | 抽象、人类般的推理 | 数值化、基于奖励 |
| 透明度 | 高，有文本解释 | 低，常为黑箱 |
| 灵活性 | 适应多种场景 | 针对特定任务量身定制 |
| 泛化能力 | 知识在领域间转移良好 | 限于受训练的环境 |
| 互动性 | 适合对话和谈判 | 在环境中优化行动 |
| 实现复杂性 | 较低，使用预训练模型 | 较高，需要奖励系统设计 |
| 实时适应 | 无更新时有限 | 在动态环境中表现优异 |

表 2：大型语言模型与强化学习的战略推理比较

生成于 2024 年 5 月 2 日 18:39:40，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
