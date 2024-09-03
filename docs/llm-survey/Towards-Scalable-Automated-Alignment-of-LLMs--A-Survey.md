<!--yml

类别: 未分类

日期: 2024-09-03 17:28:55

-->

# 朝着可扩展的自动对齐 LLMs: 综述

> 来源：[`arxiv.org/html/2406.01252`](https://arxiv.org/html/2406.01252)

1.  [1 引言](https://arxiv.org/html/2406.01252v2#S1 "在 朝着可扩展的自动对齐 LLMs: 综述")

1.  [2 概述](https://arxiv.org/html/2406.01252v2#S2 "在 朝着可扩展的自动对齐 LLMs: 综述")

    1.  [2.1 自动对齐的范围](https://arxiv.org/html/2406.01252v2#S2.SS1 "在 2 概述 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

    1.  [2.2 分类](https://arxiv.org/html/2406.01252v2#S2.SS2 "在 2 概述 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [通过归纳偏差对齐 (§3)](https://arxiv.org/html/2406.01252v2#S2.SS2.SSS0.Px1 "在 2.2 分类 ‣ 2 概述 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [通过行为模仿对齐 (§4)](https://arxiv.org/html/2406.01252v2#S2.SS2.SSS0.Px2 "在 2.2 分类 ‣ 2 概述 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [通过模型反馈对齐 (§5)](https://arxiv.org/html/2406.01252v2#S2.SS2.SSS0.Px3 "在 2.2 分类 ‣ 2 概述 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [通过环境反馈对齐 (§6)](https://arxiv.org/html/2406.01252v2#S2.SS2.SSS0.Px4 "在 2.2 分类 ‣ 2 概述 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [自动对齐的潜在机制 (§7)](https://arxiv.org/html/2406.01252v2#S2.SS2.SSS0.Px5 "在 2.2 分类 ‣ 2 概述 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

1.  [3 通过归纳偏差对齐](https://arxiv.org/html/2406.01252v2#S3 "在 朝着可扩展的自动对齐 LLMs: 综述")

    1.  [3.1 从 LLM 特征中的归纳偏差](https://arxiv.org/html/2406.01252v2#S3.SS1 "在 3 通过归纳偏差对齐 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [3.1.1 H1: 不确定性作为有用性的指标](https://arxiv.org/html/2406.01252v2#S3.SS1.SSS1 "在 3.1 从 LLM 特征中的归纳偏差 ‣ 3 通过归纳偏差对齐 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

            1.  [H1: 讨论](https://arxiv.org/html/2406.01252v2#S3.SS1.SSS1.Px1 "在 3.1.1 H1: 不确定性作为有用性的指标 ‣ 3.1 从 LLM 特征中的归纳偏差 ‣ 3 通过归纳偏差对齐 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [3.1.2 H2: LLMs 可以判断、批评、改进等](https://arxiv.org/html/2406.01252v2#S3.SS1.SSS2 "在 3.1 从 LLM 特征中的归纳偏差 ‣ 3 通过归纳偏差对齐 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

            1.  [H2: 讨论](https://arxiv.org/html/2406.01252v2#S3.SS1.SSS2.Px1 "在 3.1.2 H2: LLMs 可以判断、批评、改进等 ‣ 3.1 从 LLM 特征中的归纳偏差 ‣ 3 通过归纳偏差对齐 ‣ 朝着可扩展的自动对齐 LLMs: 综述")

        1.  [3.1.3 H3: 大型语言模型能够有效地进行上下文学习](https://arxiv.org/html/2406.01252v2#S3.SS1.SSS3 "在 3.1 LLMs 特征的归纳偏置 ‣ 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

            1.  [H3: 讨论](https://arxiv.org/html/2406.01252v2#S3.SS1.SSS3.Px1 "在 3.1.3 H3: LLMs 能够有效地进行上下文学习 ‣ 3.1 LLMs 特征的归纳偏置 ‣ 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

    1.  [3.2 LLMs 组织的归纳偏置](https://arxiv.org/html/2406.01252v2#S3.SS2 "在 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

        1.  [3.2.1 H4: 任务分解](https://arxiv.org/html/2406.01252v2#S3.SS2.SSS1 "在 3.2 LLMs 组织的归纳偏置 ‣ 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

        1.  [3.2.2 H5: 自我对弈](https://arxiv.org/html/2406.01252v2#S3.SS2.SSS2 "在 3.2 LLMs 组织的归纳偏置 ‣ 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

            1.  [H5.1: 生成器-鉴别器](https://arxiv.org/html/2406.01252v2#S3.SS2.SSS2.Px1 "在 3.2.2 H5: 自我对弈 ‣ 3.2 LLMs 组织的归纳偏置 ‣ 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

            1.  [H5.2: 辩论](https://arxiv.org/html/2406.01252v2#S3.SS2.SSS2.Px2 "在 3.2.2 H5: 自我对弈 ‣ 3.2 LLMs 组织的归纳偏置 ‣ 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

        1.  [3.2.3 讨论](https://arxiv.org/html/2406.01252v2#S3.SS2.SSS3 "在 3.2 LLMs 组织的归纳偏置 ‣ 3 通过归纳偏置对齐 ‣ 朝着可扩展的自动对齐：调研")

1.  [4 通过行为模仿对齐](https://arxiv.org/html/2406.01252v2#S4 "在 朝着可扩展的自动对齐：调研")

    1.  [4.1 指令构建](https://arxiv.org/html/2406.01252v2#S4.SS1 "在 4 通过行为模仿对齐 ‣ 朝着可扩展的自动对齐：调研")

    1.  [4.2 从强到弱的蒸馏](https://arxiv.org/html/2406.01252v2#S4.SS2 "在 4 通过行为模仿对齐 ‣ 朝着可扩展的自动对齐：调研")

        1.  [4.2.1 响应引导的蒸馏](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS1 "在 4.2 从强到弱的蒸馏 ‣ 4 通过行为模仿对齐 ‣ 朝着可扩展的自动对齐：调研")

            1.  [指令跟随](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS1.Px1 "在 4.2.1 响应引导的蒸馏 ‣ 4.2 从强到弱的蒸馏 ‣ 4 通过行为模仿对齐 ‣ 朝着可扩展的自动对齐：调研")

            1.  [数学](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS1.Px2 "在 4.2.1 响应引导蒸馏 ‣ 4.2 从强到弱的蒸馏 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

            1.  [编码](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS1.Px3 "在 4.2.1 响应引导蒸馏 ‣ 4.2 从强到弱的蒸馏 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

            1.  [代理](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS1.Px4 "在 4.2.1 响应引导蒸馏 ‣ 4.2 从强到弱的蒸馏 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

        1.  [4.2.2 偏好引导蒸馏](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS2 "在 4.2 从强到弱的蒸馏 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

            1.  [基于分数](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS2.Px1 "在 4.2.2 偏好引导蒸馏 ‣ 4.2 从强到弱的蒸馏 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

            1.  [基于精炼](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS2.Px2 "在 4.2.2 偏好引导蒸馏 ‣ 4.2 从强到弱的蒸馏 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

            1.  [基于来源](https://arxiv.org/html/2406.01252v2#S4.SS2.SSS2.Px3 "在 4.2.2 偏好引导蒸馏 ‣ 4.2 从强到弱的蒸馏 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

    1.  [4.3 从弱到强的对齐](https://arxiv.org/html/2406.01252v2#S4.SS3 "在 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

    1.  [4.4 讨论](https://arxiv.org/html/2406.01252v2#S4.SS4 "在 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

        1.  [数据质量](https://arxiv.org/html/2406.01252v2#S4.SS4.SSS0.Px1 "在 4.4 讨论 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

        1.  [教师的偏差](https://arxiv.org/html/2406.01252v2#S4.SS4.SSS0.Px2 "在 4.4 讨论 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

        1.  [对超级对齐的理解不足](https://arxiv.org/html/2406.01252v2#S4.SS4.SSS0.Px3 "在 4.4 讨论 ‣ 4 行为模仿对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

1.  [5 通过模型反馈对齐](https://arxiv.org/html/2406.01252v2#S5 "在 面向可扩展自动对齐的 LLMs：综述")

    1.  [5.1 标量奖励](https://arxiv.org/html/2406.01252v2#S5.SS1 "在 5 通过模型反馈对齐 ‣ 面向可扩展自动对齐的 LLMs：综述")

        1.  [5.1.1 人类反馈的强化学习](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS1 "在 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

        1.  [5.1.2 奖励建模的改进](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS2 "在 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

            1.  [奖励模型预训练](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS2.Px1 "在 5.1.2 奖励建模的改进 ‣ 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

            1.  [一致的偏好数据构建](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS2.Px2 "在 5.1.2 奖励建模的改进 ‣ 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

            1.  [细粒度反馈收集](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS2.Px3 "在 5.1.2 奖励建模的改进 ‣ 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

            1.  [训练优化](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS2.Px4 "在 5.1.2 奖励建模的改进 ‣ 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

        1.  [5.1.3 来自 AI 反馈的强化学习](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS3 "在 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

            1.  [排名多个响应](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS3.Px1 "在 5.1.3 来自 AI 反馈的强化学习 ‣ 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

            1.  [生成正面和负面反馈](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS3.Px2 "在 5.1.3 来自 AI 反馈的强化学习 ‣ 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

        1.  [5.1.4 奖励模型引导解码](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS4 "在 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

        1.  [5.1.5 使用奖励模型筛选 SFT 数据](https://arxiv.org/html/2406.01252v2#S5.SS1.SSS5 "在 5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

    1.  [5.2 二元验证器](https://arxiv.org/html/2406.01252v2#S5.SS2 "在 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

        1.  [结果验证器](https://arxiv.org/html/2406.01252v2#S5.SS2.SSS0.Px1 "在 5.2 二元验证器 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的自动化对齐 LLM 的调查")

        1.  [过程验证器](https://arxiv.org/html/2406.01252v2#S5.SS2.SSS0.Px2 "在 5.2 二元验证器 ‣ 5 通过模型反馈进行对齐 ‣ 面向可扩展的 LLM 自动对齐：调查")

    1.  [5.3 文本评论](https://arxiv.org/html/2406.01252v2#S5.SS3 "在 5 通过模型反馈进行对齐 ‣ 面向可扩展的 LLM 自动对齐：调查")

1.  [6 通过环境反馈进行对齐](https://arxiv.org/html/2406.01252v2#S6 "在 面向可扩展的 LLM 自动对齐：调查")

    1.  [6.1 社会互动](https://arxiv.org/html/2406.01252v2#S6.SS1 "在 6 通过环境反馈进行对齐 ‣ 面向可扩展的 LLM 自动对齐：调查")

    1.  [6.2 人类共享价值](https://arxiv.org/html/2406.01252v2#S6.SS2 "在 6 通过环境反馈进行对齐 ‣ 面向可扩展的 LLM 自动对齐：调查")

    1.  [6.3 工具执行反馈](https://arxiv.org/html/2406.01252v2#S6.SS3 "在 6 通过环境反馈进行对齐 ‣ 面向可扩展的 LLM 自动对齐：调查")

    1.  [6.4 具身环境](https://arxiv.org/html/2406.01252v2#S6.SS4 "在 6 通过环境反馈进行对齐 ‣ 面向可扩展的 LLM 自动对齐：调查")

    1.  [6.5 讨论](https://arxiv.org/html/2406.01252v2#S6.SS5 "在 6 通过环境反馈进行对齐 ‣ 面向可扩展的 LLM 自动对齐：调查")

1.  [7 自动对齐的潜在机制](https://arxiv.org/html/2406.01252v2#S7 "在 面向可扩展的 LLM 自动对齐：调查")

    1.  [7.1 当前对齐的潜在机制是什么？](https://arxiv.org/html/2406.01252v2#S7.SS1 "在 7 自动对齐的潜在机制 ‣ 面向可扩展的 LLM 自动对齐：调查")

        1.  [基于特征的分析](https://arxiv.org/html/2406.01252v2#S7.SS1.SSS0.Px1 "在 7.1 当前对齐的潜在机制是什么？ ‣ 7 自动对齐的潜在机制 ‣ 面向可扩展的 LLM 自动对齐：调查")

        1.  [知识干预](https://arxiv.org/html/2406.01252v2#S7.SS1.SSS0.Px2 "在 7.1 当前对齐的潜在机制是什么？ ‣ 7 自动对齐的潜在机制 ‣ 面向可扩展的 LLM 自动对齐：调查")

        1.  [实证评估](https://arxiv.org/html/2406.01252v2#S7.SS1.SSS0.Px3 "在 7.1 当前对齐的潜在机制是什么？ ‣ 7 自动对齐的潜在机制 ‣ 面向可扩展的 LLM 自动对齐：调查")

        1.  [‣ 7.1 当前对齐的潜在机制是什么？](https://arxiv.org/html/2406.01252v2#S7.SS1.SSS0.Px4 "在 7.1 当前对齐的潜在机制是什么？ ‣ 7 自动对齐的潜在机制 ‣ 面向可扩展的 LLM 自动对齐：调查")

    1.  [7.2 为什么自我反馈有效？](https://arxiv.org/html/2406.01252v2#S7.SS2 "在 7 自动对齐的潜在机制 ‣ 面向可扩展的 LLM 自动对齐：调查")

    1.  [7.3 为什么从弱到强是可行的？](https://arxiv.org/html/2406.01252v2#S7.SS3 "在自动对齐的基本机制中 ‣ 朝向可扩展的自动对齐 LLMs：调查")

1.  [8 结论](https://arxiv.org/html/2406.01252v2#S8 "在可扩展的自动对齐的 LLMs：调查中")

# 朝向可扩展的自动对齐 LLMs：调查

\name 曹博熙^(1,3)¹¹1 相等贡献，陆克明²¹¹1 相等贡献，吕欣宇^(1,3)¹¹1 相等贡献，陈家伟^(1,3)，任梦洁^(1,3)，

方向向^(1,3)、刘佩林^(1,3)、卢耀杰¹、何本³、韩宪培¹、孙乐¹，

林宏宇¹²²2 通讯作者，余博文²²²2 通讯作者。

\addr ¹中国科学院软件研究所信息处理实验室

²阿里巴巴集团

³中国科学院大学

对应联系：hongyu@iscas.ac.cn, yubowen.ybw@alibaba-inc.com

###### 摘要

对齐是构建符合人类需求的大型语言模型（LLMs）中最关键的一步。随着 LLMs 的快速发展逐渐超越人类能力，基于人工标注的传统对齐方法越来越无法满足可扩展性的要求。因此，迫切需要探索新的自动对齐信号来源和技术方法。本文系统地回顾了近期出现的自动对齐方法，尝试探索在 LLMs 能力超越人类时如何实现有效、可扩展的自动对齐。具体来说，我们根据对齐信号的来源将现有的自动对齐方法分为 4 大类，并讨论了每一类的现状和潜在发展。此外，我们探讨了使自动对齐成为可能的基本机制，并讨论了从对齐的基本作用出发，使自动对齐技术可行和有效的关键因素。

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：自动对齐的四种代表性范式的示意图。图由 DALL·E (Ramesh et al., [2021](https://arxiv.org/html/2406.01252v2#bib.bib173)) 生成。

## 1 引言

近年来，大型语言模型（LLMs）的快速进展极大地重塑了人工智能的格局（Ouyang et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib160); Touvron et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib213); OpenAI, [2023c](https://arxiv.org/html/2406.01252v2#bib.bib158)）。对齐是塑造 LLMs 行为以符合人类意图和价值观的核心（Yao et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib270); Shen et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib187)），例如，教导 LLMs 在回应时遵循“有益、无害和诚实（HHH）”原则（Askell et al., [2021](https://arxiv.org/html/2406.01252v2#bib.bib13)）。因此，为了使 LLMs 满足人类要求，已经投入了越来越多的努力，这使其成为 LLM 时代的一个热点研究方向（Wang et al., [2023g](https://arxiv.org/html/2406.01252v2#bib.bib234), [2024g](https://arxiv.org/html/2406.01252v2#bib.bib229); Ji et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib92)）。

以往的对齐研究主要依赖于手动标注的对齐数据，这些数据包含了人类偏好信息，通过在预训练模型上进行后训练来实现对齐（Stiennon et al., [2020](https://arxiv.org/html/2406.01252v2#bib.bib199)）。具体而言，有两种主要形式的对齐数据：1）指令-响应对，这通常包括一个查询和一个人工编写的黄金参考。这种形式的数据常用于对 LLMs 进行监督微调，将人类偏好信息注入模型中（Taori et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib211); Peng et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib167); Ding et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib51)）；2）偏好数据，通常包括一个查询、几个潜在的响应，以及人类对这些响应的偏好（Cui et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib47)）。偏好数据可以通过 DPO（Rafailov et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib171)）、IPO（Azar et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib14)）和 PRO（Song et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib196)）等算法进行直接的偏好优化。此外，它还可以用于训练奖励模型，通过对模型响应提供反馈，使目标策略 LLM 与数据中的偏好信息对齐（Stiennon et al., [2020](https://arxiv.org/html/2406.01252v2#bib.bib199); Bai et al., [2022a](https://arxiv.org/html/2406.01252v2#bib.bib15); Ouyang et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib160)）。然而，无论是指令-响应对还是偏好数据的构建过程，都需要非常昂贵、细致的人类标注，并且具有高质量标准，这使得扩展这些方法的每一步都非常昂贵（Ouyang et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib160); Touvron et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib213); Zhou et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib301)）。

尽管成本如此高昂，这些依赖人工标注的对齐方法的可扩展性仍然难以维持。首先，随着 LLM 的快速发展，LLM 的能力在许多方面逐渐接近甚至超过了人类，这使得人类越来越难以产生对 LLM 有意义的对齐数据（Bowman et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib21); Burns et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib25)）。实际上，许多研究发现，LLM 生成的数据质量在许多方面已经超过了普通人工标注者标注的数据质量（Zheng et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib296); Chen et al., [2024d](https://arxiv.org/html/2406.01252v2#bib.bib35); Wei et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib237)）。这一现象不仅显著提高了获取单一有意义的人工标注数据的成本（因为需要越来越昂贵的高质量标注者），还大幅减少了人工标注数据对 LLM 的潜在益处。其次，随着 LLM 能力逐渐超越人类能力的边界，人类越来越难以有效判断 LLM 生成的回应质量。这导致人工生成的偏好信号质量显著下降，无法准确反映人类需求，从而使得为 LLM 提供有效指导变得具有挑战性。因此，基于人工标注的对齐方法越来越无法应对 LLM 能力的快速提升，使得对 LLM 实现可扩展监督变得困难。

为应对这些挑战，自动化对齐最近引起了极大的关注（Yuan et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib282); Chen et al., [2024g](https://arxiv.org/html/2406.01252v2#bib.bib40)）。与之前依赖人工标注以获取对齐信号的方法不同，自动化对齐的目标是构建具有最小人工干预的可扩展且高质量的对齐系统。因此，自动化对齐有可能解决 LLM 快速发展带来的核心挑战，即人工标注既不可行又极其昂贵。对于自动化对齐来说，最关键的部分是找到一种可扩展的对齐信号，以替代人工手动创建的偏好信号，并在 LLM 快速发展中保持有效。

为此，本调查将快速发展的自动对齐方法按构建不同对齐信号的机制进行分类，总结了各个方向的当前进展，并讨论了发展轨迹和潜在的未来方向。具体而言，本调查探讨了以下构建对齐信号以实现自动对齐的代表性方向，包括：

+   •

    通过归纳偏差进行对齐 (§[3](https://arxiv.org/html/2406.01252v2#S3 "3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))，通过引入适当的假设和约束自动引导模型朝向期望的行为，而无需使用额外的训练信号。

+   •

    通过行为模仿进行对齐 (§[4](https://arxiv.org/html/2406.01252v2#S4 "4 Aligning Through Behavior Imitation ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))，通过模仿另一个对齐模型的行为来实现自动对齐。例如，使用一个对齐良好的模型生成指令-响应对，然后使用模仿学习训练目标模型。

+   •

    通过模型反馈进行对齐 (§[5](https://arxiv.org/html/2406.01252v2#S5 "5 Aligning Through Model Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))，涉及通过从其他模型获得反馈来指导目标模型的对齐优化。

+   •

    通过环境反馈进行对齐 (§[6](https://arxiv.org/html/2406.01252v2#S6 "6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))，涉及通过与环境互动自动获取对齐信号或反馈，从而实现目标模型的自动对齐。

此外，本调查还探讨了使自动对齐成为可能的潜在机制 (§[7](https://arxiv.org/html/2406.01252v2#S7 "7 Underlying Mechanism of Automated Alignment ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))，并从对齐的基本作用出发，讨论了使自动对齐技术可行和有效的关键因素。

本调查的其余部分组织如下：第[2](https://arxiv.org/html/2406.01252v2#S2 "2 Overview ‣ Towards Scalable Automated Alignment of LLMs: A Survey")节描述了本调查涵盖的自动化对齐的范围，以及我们的分类法。第[3](https://arxiv.org/html/2406.01252v2#S3 "3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey")节到第[6](https://arxiv.org/html/2406.01252v2#S6 "6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey")节对自动化对齐中四个前述代表性方向的进展和局限性进行了详细介绍。第[7](https://arxiv.org/html/2406.01252v2#S7 "7 Underlying Mechanism of Automated Alignment ‣ Towards Scalable Automated Alignment of LLMs: A Survey")节探讨了自动化对齐的基本机制。我们在第[8](https://arxiv.org/html/2406.01252v2#S8 "8 Conclusions ‣ Towards Scalable Automated Alignment of LLMs: A Survey")节中包含了对本调查的总体结论¹¹1 我们公开发布了一个相应的论文列表，该列表将在[`github.com/cascip/awesome-auto-alignment`](https://github.com/cascip/awesome-auto-alignment)上定期更新。

{forest}

for tree= forked edges, grow’=0, draw, rounded corners, node options=align=center,, text width=2.7cm, s sep=6pt, calign=edge midpoint, , [Scalable

Automated Alignment, fill=gray!45, parent [Inductive

偏差 §[3](https://arxiv.org/html/2406.01252v2#S3 "3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey")，对于树=获取 [来自 LLMs 的特征，[不确定性过滤，获取 [自我一致性（Wang et al., [2023e](https://arxiv.org/html/2406.01252v2#bib.bib231)）；自我改进（Huang et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib86)）；西方（Pace et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib161)）；等等，acquisition_work] ] [自我评估/批评/精炼，获取 [宪法 AI（Bai et al., [2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）；思维树（Yao et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib272)）；自我奖励（Yuan et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)）；等等，acquisition_work] ] [上下文蒸馏，获取 [对齐实验室（Askell et al., [2021](https://arxiv.org/html/2406.01252v2#bib.bib13)）；骆驼（Sun et al., [2023d](https://arxiv.org/html/2406.01252v2#bib.bib205)）；Llama-2-Chat（Touvron et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib213)）；RLCD（Yang et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib263)）；等等，acquisition_work] ] ] [来自 LLMs 的组织，[任务分解，获取 [最少到最多（Zhou et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib302)）；IDA（Christiano et al., [2018](https://arxiv.org/html/2406.01252v2#bib.bib44)）；等等，acquisition_work] ] [自我游戏，获取 [SPIN（Chen et al., [2024g](https://arxiv.org/html/2406.01252v2#bib.bib40)）；共识游戏（Jacob et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib91)）；等等，acquisition_work] [辩论（Irving et al., [2018](https://arxiv.org/html/2406.01252v2#bib.bib90)）；SPAG（Cheng et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib42)）；等等，acquisition_work] ] ] ] [行为

模仿 §[4](https://arxiv.org/html/2406.01252v2#S4 "4 Aligning Through Behavior Imitation ‣ Towards Scalable Automated Alignment of LLMs: A Survey")，针对树状表示 [ 指令构建，[ 不自然指令 (Honovich et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib83)); 自我指导 (Wang et al., [2023f](https://arxiv.org/html/2406.01252v2#bib.bib233)); 演变指令 (Xu et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib255)); 座头鲸 (Li et al., [2024f](https://arxiv.org/html/2406.01252v2#bib.bib120)); 等，表示工作 _2 ] ] [ 从强到弱的蒸馏，[响应引导，表示 [ LLaMA-GPT4 (Peng et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib167)); 斯坦福 Alpaca (Taori et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib211)); Ultrachat (Ding et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib51)); 等，表示工作 ] ] [ 偏好引导，表示 [ Zephyr (Tunstall et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib214)); IterAlign (Chen et al., [2024e](https://arxiv.org/html/2406.01252v2#bib.bib37)); Openchat (Wang et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib219)); 等，表示工作 ] ] ] [ 从弱到强的对齐，[ Weak2Strong (Burns et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib25)); IaR (Somerstep et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib195)); Liu 和 Alahi ([2024](https://arxiv.org/html/2406.01252v2#bib.bib136)); Hase et al. ([2024](https://arxiv.org/html/2406.01252v2#bib.bib74)); 等，表示工作 _2 ] ] ] [模型

反馈 §[5](https://arxiv.org/html/2406.01252v2#S5 "5 Aligning Through Model Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey")，用于树形=探测 [标量奖励，[RLHF，探测 [InstructGPT (Ouyang et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib160))；DPRM (Li et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib113))；等等，探测 _ 工作] ] [RLAIF，探测 [RLAIF (Lee et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib110))；RLCD (Yang et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib263))；等等，探测 _ 工作] ] [反馈引导解码，探测 [评论驱动解码 (Lango and Dusek, [2023](https://arxiv.org/html/2406.01252v2#bib.bib106))；RAD (Deng and Raffel, [2023](https://arxiv.org/html/2406.01252v2#bib.bib49))；等等，探测 _ 工作] ] [筛选 SFT 数据，探测 [Quark (Lu et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib138))；RRHF (Yuan et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib280))；RAFT (Dong et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib52))；等等，探测 _ 工作] ] ] [二进制验证器，[结果验证器，探测 [V-STaR (Hosseini et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib84))；SORMs (Havrilla et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib75))；等等，探测 _ 工作] ] [过程验证器，探测 [MATH-SHEPHERD (Wang et al., [2024e](https://arxiv.org/html/2406.01252v2#bib.bib225))；MiPS (Wang et al., [2024h](https://arxiv.org/html/2406.01252v2#bib.bib235)) 等等，探测 _ 工作] ] ] [文本评论，探测 [ILF (Scheurer et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib178))；LEMA (An et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib8))；等等，cus_ 探测 _ 工作] ] ] [环境

反馈 §[6](https://arxiv.org/html/2406.01252v2#S6 "6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey")，用于树=编辑 [ 社会互动，编辑 [StableAlignment (刘等，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib131)); MoralDial (孙等，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib201)); SOTOPIA-$\pi$  (王等，[2024f](https://arxiv.org/html/2406.01252v2#bib.bib226)); 等，编辑工作] ] [人类共享价值，编辑 [MGE (克林格福德等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib100)); 集体宪法 AI (Anthropic，[2023](https://arxiv.org/html/2406.01252v2#bib.bib9)) 等，编辑工作] ] [工具执行，编辑 [自我调试 (乔等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib169)); CodeRL (乔等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib169)); SelfEvlove (姜等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib94)); CRITIC (沟等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib68)); 等，编辑工作 ] ] [具身环境，编辑 [GLAM (卡尔塔等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib26)); E2WM (向等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib252)); TWOSOME (谭等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib207)); 等，编辑工作 ] ] ] [机制 §[7](https://arxiv.org/html/2406.01252v2#S7 "7 Underlying Mechanism of Automated Alignment ‣ Towards Scalable Automated Alignment of LLMs: A Survey")，用于树=应用 [对齐

机制、应用 [LIMA (周等，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib301)); Rethinking (任等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib175)); URIAL (林等，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib128)); ICL&IT (段等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib53)); 行为转变 (吴等，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib249)) 等，application_work] ] [自反馈的内部工作，应用 [GV-consistency(李等，[2024g](https://arxiv.org/html/2406.01252v2#bib.bib121)); CriticBench (林等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib129)); 自奖励 (袁等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)); Humback (李等，[2024f](https://arxiv.org/html/2406.01252v2#bib.bib120)); LLM-as-a-Judge (郑等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib296)) 等，application_work] ] [弱到强的可行性，应用 [Easy2Hard (孙等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib206); 长谷等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib74)); Weak2Strong (伯恩斯等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib25)); Principle2Behavior (白等，[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16); 孙等，[2023d](https://arxiv.org/html/2406.01252v2#bib.bib205)) 等，application_work] ] ] ]

图 2：本文通过对齐信号来源的视角回顾了可扩展自动化对齐的研究工作。

## 2 概述

在本节中，我们将讨论本次调查涵盖的自动化对齐的范围，并介绍我们的分类体系。

### 2.1 自动化对齐的范围

在快速发展的人工智能领域，对齐研究在确保机器行为与人类价值观和期望一致方面发挥着关键作用。随着 AI 系统，尤其是大型语言模型（LLMs），变得越来越复杂和强大，将这些模型与细致的人类标准对齐变得越来越具挑战性和资源密集。这一需求推动了被称为“自动化对齐”的方法论的发展。

自动化对齐并不意味着完全没有人类参与。相反，它的目标是最小化人类干预，同时构建可扩展、高质量的系统，这些系统严格遵循期望的对齐结果。自动化对齐的本质在于通过自动化过程动态调整和响应对齐标准，从而减少对持续人类监督的依赖。根据对齐信号的来源，目前对自动化对齐的研究可以分为四大类。首先，归纳偏差涉及通过增强模型的假设性概括或规则，使其在没有明确外部指导的情况下产生更好对齐的响应。其次，行为模仿技术包括通过模仿已经对齐模型的输出训练 AI 系统，利用模仿学习传播期望的行为。第三，自动化对齐通过整合反馈机制得到支持。模型反馈通过结合其他模型反馈的见解来对齐目标模型。第四，环境反馈自动从操作环境本身获取对齐目标，使模型能够根据实时数据和互动进行调整。

向自动化对齐的演变表明了一种范式，其中 AI 系统不仅可以根据预定义的对齐协议自我调节，还可以通过持续学习和适应自主演化这些协议。这一转变有望在 AI 治理中取得重大进展，使在更大规模上部署既有效又值得信赖的 AI 解决方案成为可能。然而，尽管有这些进展，人类监督的必要性仍然至关重要，以确保 AI 系统即使在获得自主权的情况下，也不会偏离伦理界限或社会规范。这种将自动化对齐与战略性人类监督相结合的方式，概括了当前人工智能对齐领域的轨迹和复杂性。

### 2.2 分类体系

在本节中，我们将详细描述我们的分类体系，如图[2](https://arxiv.org/html/2406.01252v2#S1.F2 "Figure 2 ‣ 1 Introduction ‣ Towards Scalable Automated Alignment of LLMs: A Survey")所示。

##### 通过归纳偏差进行对齐 (§[3](https://arxiv.org/html/2406.01252v2#S3 "3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))

讨论了通过引入额外假设来增强模型，使其能够利用自生成的信号进行进一步改进。目前，有两种类型的归纳偏差 (Mitchell, [1980](https://arxiv.org/html/2406.01252v2#bib.bib149)) 促进了大型语言模型的自我改进。第一种类型包括源自 LLM 本身特征的归纳偏差。例如，Wei 等人 ([2022](https://arxiv.org/html/2406.01252v2#bib.bib236)); Kojima 等人 ([2022](https://arxiv.org/html/2406.01252v2#bib.bib101)); Wang 等人 ([2023e](https://arxiv.org/html/2406.01252v2#bib.bib231)); Wang 和 Zhou ([2024](https://arxiv.org/html/2406.01252v2#bib.bib230)) 专注于利用模型输出概率中的模式来引导更好的结果。此外，Bai 等人 ([2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)); Yao 等人 ([2023b](https://arxiv.org/html/2406.01252v2#bib.bib272)); Saunders 等人 ([2022](https://arxiv.org/html/2406.01252v2#bib.bib177)); Shinn 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib190)) 利用模型的能力来批评、评估和改进其响应，从而提高安全性和质量。另一类工作 (Ganguli 等人, [2022](https://arxiv.org/html/2406.01252v2#bib.bib61); Lin 等人, [2024a](https://arxiv.org/html/2406.01252v2#bib.bib128)) 发现仅仅在上下文中提供对齐目标信号就可以让 LLMs 利用其强大的上下文学习能力进行自动对齐。第二种类型涉及源自 LLM 组织结构的归纳偏差。例如，基于分解认知的假设，Khot 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib98)); Zhou 等人 ([2023b](https://arxiv.org/html/2406.01252v2#bib.bib302)); Wang 等人 ([2023b](https://arxiv.org/html/2406.01252v2#bib.bib223)) 使用任务分解来使 LLMs 解决复杂任务。此外，受 AlphaGo Zero (Silver 等人, [2018](https://arxiv.org/html/2406.01252v2#bib.bib192)) 成功的启发，几项研究建议通过让 LLMs 在对抗中进行自我游戏来增强它们 (Fu 等人, [2023a](https://arxiv.org/html/2406.01252v2#bib.bib59); Chen 等人, [2024g](https://arxiv.org/html/2406.01252v2#bib.bib40))。

##### 通过行为模仿进行对齐 (§[4](https://arxiv.org/html/2406.01252v2#S4 "4 Aligning Through Behavior Imitation ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))

旨在通过模仿将目标模型的行为与教师模型的行为对齐。根据教师模型和目标模型的特点，通过行为模仿进行对齐的研究可以分为两种主要范式：强到弱的蒸馏和弱到强的对齐。具体来说，强到弱的蒸馏涉及使用一个对齐良好且强大的 LLM 生成训练数据，然后将目标模型的行为与教师模型的响应（Taori et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib211); Peng et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib167); Xu et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib255)）或偏好（Tunstall et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib214); Cui et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib47)）进行对齐。相比之下，弱到强的对齐则使用一个较弱的模型作为监督者，引导更强的目标模型进一步对齐（Burns et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib25); Zheng et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib295); Hase et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib74)）。

##### 通过模型反馈对齐 (§[5](https://arxiv.org/html/2406.01252v2#S5 "5 Aligning Through Model Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))

旨在通过引入来自额外模型的反馈来指导目标模型的对齐优化。这些反馈通常分为三类：1）标量信号（Christiano 等，[2017](https://arxiv.org/html/2406.01252v2#bib.bib45)；Stiennon 等，[2020](https://arxiv.org/html/2406.01252v2#bib.bib199)；Ouyang 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib160)）。这些信号通常由一个基于偏好数据对训练的奖励模型提供。奖励模型被期望从偏好数据中学习对齐信号，并对在强化学习过程中获得的未见样本进行泛化。此外，来自奖励模型的反馈还可以指导指令调优数据的选择（Zhou 等，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib301)；Touvron 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib213)；Yuan 等，[2023b](https://arxiv.org/html/2406.01252v2#bib.bib283)）以及模型解码（Lango 和 Dusek，[2023](https://arxiv.org/html/2406.01252v2#bib.bib106)；Deng 和 Raffel，[2023](https://arxiv.org/html/2406.01252v2#bib.bib49)）。2）二进制信号。这些信号在数学推理任务中广泛使用，用于提供结果正确性的二进制反馈。由于大多数数学任务需要多个推理步骤来解决，因此二进制验证器可以分为结果验证器，它们估计最终结果的正确性（Zelikman 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib286)；Singh 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib193)；Havrilla 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib75)），以及过程验证器，它们可以进一步对中间步骤提供反馈（Lightman 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib127)；Uesato 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib215)；Ying 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib275)；Shao 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib182)）。3）文本信号。这些信号通常由 LLMs 生成，以提供对人类更直观的反馈（Scheurer 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib178)；Chen 等，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib29)）。

##### 通过环境反馈对齐（§[6](https://arxiv.org/html/2406.01252v2#S6 "6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey")）

旨在自动从现有环境中获得对齐信号或反馈，而不是来自训练模型，例如社会互动（Liu et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib131)；Sun et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib201)），公众意见（Anthropic, [2023](https://arxiv.org/html/2406.01252v2#bib.bib9)），外部工具（Qiao et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib169)；Jiang et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib94)）和具身环境（Bousmalis et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib20)；Xu et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib258)）。环境反馈作为之前对齐信号来源的重要补充，使 AI 系统能够更好地适应现实应用场景。然而，如何有效利用环境反馈仍然是一个亟待进一步探索的研究方向。

##### 自动对齐的潜在机制（§[7](https://arxiv.org/html/2406.01252v2#S7 "7 Underlying Mechanism of Automated Alignment ‣ Towards Scalable Automated Alignment of LLMs: A Survey")）

除了回顾上述代表性自动对齐技术外，我们还对自动对齐的潜在机制进行了深入讨论。具体来说，我们致力于探讨以下三个关于自动对齐的关键问题：

+   •

    当前对齐的潜在机制是什么？

+   •

    自我反馈为何有效？

+   •

    为什么从弱到强是可行的？

对这些问题的探索对于实现可扩展的自动对齐至关重要。对于每个问题，我们总结了现有的研究和观点，提出了开放性问题，并讨论了它们的局限性和未来方向。

## 3 通过归纳偏差进行对齐

> 自我教育是我坚定相信的唯一教育方式。
> 
> 艾萨克·阿西莫夫

![参考说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 3：展示了通过 3 种代表性归纳偏差对齐的插图，这些偏差源于 LLMs 的固有特征。

目前，通过归纳偏差进行对齐是实现自动对齐的最有前景的方向之一。归纳偏差（Mitchell, [1980](https://arxiv.org/html/2406.01252v2#bib.bib149)）是一组本质上引导模型学习和决策过程的假设或约束。通过仔细选择和实施合适的归纳偏差，我们可以引导模型朝向更符合人类标准和期望的行为和决策，这些行为和决策能够推广到未见过的数据分布中。

与其他自动对齐方法相比，通过归纳偏差进行对齐有两个主要优势：

+   1)

    它不需要超出模型本身的额外监督信号，从而避免了获取额外标注数据的高成本。考虑到当前训练数据稀缺或已经耗尽的现状，这一点尤为相关²²在本文讨论的对齐背景下，我们期望模型能够持续提高其有用性，从而为对齐过程提供更有效的帮助。对齐的范围实际上代表了一种预训练后的过程，而不是对模型的引导。（Xue et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib260)）。

+   2)

    它有潜力解决可扩展监督问题（Bowman et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib21)）。随着 LLMs 潜力的不断扩展，人类提供超越自身知识水平的监督信号变得越来越困难。然而，通过归纳偏差，模型可以不断自我提升，超越人类知识的局限性。

在对相关文献进行全面审查后，我们发现，通过语言模型本身进行自我提升的现有努力可以分解为一组$\mathcal{H}$的五种归纳偏差。这些归纳偏差分为两个大类：1) 源于 LLMs 固有特征的那些（§[3.1](https://arxiv.org/html/2406.01252v2#S3.SS1 "3.1 Inductive Bias from Features of LLMs ‣ 3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey")），和 2) 源于 LLMs 组织结构的那些（§[3.2](https://arxiv.org/html/2406.01252v2#S3.SS2 "3.2 Inductive Bias from Organization of LLMs ‣ 3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey")）。

对于每种归纳偏差类型，我们将首先介绍其来源。接下来，我们将列举利用这种归纳偏差作为单步策略改进策略的工作。然后，我们将讨论那些使用它进行迭代训练以实现持续改进的工作。最后，我们将解决与给定归纳偏差相关的开放研究问题。

### 3.1 LLMs 特征的归纳偏差

LLMs 具有可以作为归纳偏差的内在特征。这些特征主要来源于对大规模数据集进行深度 Transformer 网络的预训练（H1, H3），而有些也源于旨在提高模型有用性的初步对齐程序（H2）。在本节中，我们将总结三种关键的归纳偏差，如图[3](https://arxiv.org/html/2406.01252v2#S3.F3 "Figure 3 ‣ 3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey")所示。需要注意的是，这些归纳偏差并不完全独立；相反，它们代表了基于 LLMs 特征的自动对齐的三种不同视角。

#### 3.1.1 H1: 不确定性作为有用性的指示器

模型的概率分布可以表示不确定性。正如 Kadavath 等人（[2022](https://arxiv.org/html/2406.01252v2#bib.bib95)）发现的，当提示设计得当时，从预训练 LLMs 获得的响应可以很好地校准，且校准程度可以随着参数数量和示例数量的增加而增加。换句话说，LLM 为给定答案分配的概率越高，该答案正确的可能性就越大。这一假设也得到了 Wang 等人（[2021](https://arxiv.org/html/2406.01252v2#bib.bib227)）和 He 等人（[2023](https://arxiv.org/html/2406.01252v2#bib.bib77)）的验证。类似地，Manakul 等人（[2023](https://arxiv.org/html/2406.01252v2#bib.bib147)）发现对齐模型输出的概率与事实性之间存在相关性。

在机器学习文献中，早期对这种归纳偏差的应用在一系列利用自我训练（Scudder，[1965](https://arxiv.org/html/2406.01252v2#bib.bib180)）进行半监督学习的工作中显而易见（Nigam 和 Ghani，[2000](https://arxiv.org/html/2406.01252v2#bib.bib155)；Amini 和 Gallinari，[2002](https://arxiv.org/html/2406.01252v2#bib.bib6)）。这些工作的基本范式涉及使用在监督数据上训练的学习者继续从自信分类的未标记数据中学习，从而通过未标记数据提高监督学习性能。这种方法已应用于分类任务中，采用了如伪标签（Lee 等，[2013](https://arxiv.org/html/2406.01252v2#bib.bib108)；Ferreira 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib56)）和熵最小化（Grandvalet 和 Bengio，[2004](https://arxiv.org/html/2406.01252v2#bib.bib69)）等方法。He 等人（[2020](https://arxiv.org/html/2406.01252v2#bib.bib78)）将这种方法扩展到序列生成 NLP 任务中，强调了偏置采样和噪声扰动是自我训练在这些任务中成功的关键因素。Pace 等人（[2024](https://arxiv.org/html/2406.01252v2#bib.bib161)）将自我训练的范式扩展到对齐问题，通过让奖励模型从为查询生成的候选池中最高分和最低分的答案中迭代学习，从而提高了模型的鲁棒性。

特定答案的频率也反映了不确定性。因此，从多个抽样中合成候选答案比依赖单一样本能获得更好的性能。这种方法在 LLMs 用于需要深思熟虑的任务（例如，解决数学问题）时尤其有效，因为单一的 Chain-of-Thought (CoT)（魏等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib236)）推理路径有时可能陷入局部最优，生成看似合理但不忠实的答案。自洽性（王等，[2023e](https://arxiv.org/html/2406.01252v2#bib.bib231)）通过加权求和汇总多个推理路径，可以通过边际化模型对推理路径的可能性来缓解这个问题。有趣的是，发现未加权的求和（即多数投票）也能达到类似的性能，这归因于所有推理路径上的“类似可能”概率。王和周（[2024](https://arxiv.org/html/2406.01252v2#bib.bib230)）进一步发现，当推理没有任何提示技术时，CoT 推理路径的存在与否与最终答案的概率相关。

为巩固这种提升，自我改进（黄等，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib86)）将带自洽性的 CoT 视为政策改进操作符，通过从自洽性中获得的推理路径的迭代学习，显著提升了 LLMs 的推理能力和潜力。张和帕克斯（[2023](https://arxiv.org/html/2406.01252v2#bib.bib291)）展示了通过课程“提炼”CoT 答案为直接答案，LMs 可以在大数相加问题上自我改进，而无需显式推理。Quiet-STAR（泽利克曼等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib287)）考虑了回滚理由对后续 token 概率的影响作为反馈信号，鼓励模型使用强化学习技术生成更有帮助的隐含思维过程。

##### H1: 讨论

![参考说明](img/9df2a699c179d7d103da938773675ba1.png)

图 4：Kadavath 等（[2022](https://arxiv.org/html/2406.01252v2#bib.bib95)）；He 等（[2023](https://arxiv.org/html/2406.01252v2#bib.bib77)）；OpenAI（[2023c](https://arxiv.org/html/2406.01252v2#bib.bib158)）；Zhang 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib293)）观察到的校准图。x 轴表示与模型输出相关的概率，而 y 轴表示回答正确的概率。在低概率区域，灰色区域可能反映了“不了解”响应替代一些低置信度的答案。在高概率区域，灰色区域表示过度自信。预训练 LLM 与对齐 LLM 之间的比较表明，为了有用性进行对齐可能会导致校准错误，这对迭代自我改进有害。

对于对齐模型，保持校准和不确定性仍然至关重要，因为校准错误可能会削弱迭代自我改进的潜力。许多研究（Kadavath 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib95)；He 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib77)；OpenAI，[2023c](https://arxiv.org/html/2406.01252v2#bib.bib158)；Zhang 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib293)）已经指出，对齐过程可能会损害 LLM 的校准（如图 [4](https://arxiv.org/html/2406.01252v2#S3.F4 "Figure 4 ‣ H1: Discussion ‣ 3.1.1 H1: Uncertainty as a indicator of helpfulness ‣ 3.1 Inductive Bias from Features of LLMs ‣ 3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey") 所示）。这一观察有几个合理的原因：1) 当前的表面对齐过程旨在使模型避免生成有害或不正确的回答。这涉及在一定程度上用拒绝响应的概率替代错误回答的概率，从而在低概率区域创造了一个灰色地带。2) 在对齐过程中，模型还会学习响应格式。对响应格式的信心增加可能会在某种程度上影响对回答本身的信心（He 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib77)）。此外，模型会重新学习正确答案，这可能导致过度自信（在高概率区域表示为灰色地带）。在自我对齐中，概率分布的极端化可能更为明显（Wu 等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib248)），因为这是一个涉及自我采样和训练的迭代过程。这意味着所有的令牌已经在非常高的概率分布中，使它们更可能被采样为响应。

当模型变得过于自信时，会导致模型生成输出的多样性和探索性下降。为缓解这一问题，一个有前景的方法是使用推断时干预（例如，高温度（Kadavath et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib95)），保真度（Zhang et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib293)））来降低预期的校准误差。另一个潜在的解决方案是过滤伪标签样本，以避免有害的重复训练，这需要了解何时未标记样本会有效（Grandvalet and Bengio, [2004](https://arxiv.org/html/2406.01252v2#bib.bib69)）。

#### 3.1.2 H2：LLMs 可以判断、批评、改进等

预训练的 LLMs 常常难以直接响应指令。然而，模仿学习的广泛应用（Chiang et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib43)）和反馈学习（Bai et al., [2022a](https://arxiv.org/html/2406.01252v2#bib.bib15)）显著提高了 LLMs 的零样本有效性。利用这些通用有效性改进所激发和增强的推理能力，出现了一系列工作，利用模型的能力通过判断、批评、改进等来提高响应质量和安全性。

判断指的是确定模型响应的质量。判断标准通常作为原则或指南纳入指令，使得监管者能够以更具规模化的方式监督 LLM 的行为（Bai et al., [2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)；Yuan et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)），相较于对人工标注者反馈的高度依赖（Bai et al., [2022a](https://arxiv.org/html/2406.01252v2#bib.bib15)）。这种方法允许及时的监管，帮助灵活和可控地对齐语言模型，这有助于防止如奖励黑客攻击等问题在迭代训练中出现（Sun et al., [2023c](https://arxiv.org/html/2406.01252v2#bib.bib204)），并促进按政策强化学习训练（Guo et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib72)）。

自我判断可以表现为两种主要形式：1) 区分两个响应的相对质量（AI 反馈（Bai 等，[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）），评估结果以部分序的形式表示。例如，Tan 等（[2023](https://arxiv.org/html/2406.01252v2#bib.bib208)）使用提示比较哪个回答更好地遵循 HHH 原则。然后，他们将选择的选项重新输入模型，以进一步增强其判断能力。Bai 等（[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）促使模型根据采样原则选择优越的响应，并随后使用偏好过程实现模型的帕累托改进。2) 为响应提供绝对评分（LLM 作为评判者（Zheng 等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib296)）），评估结果为标量形式。Yao 等（[2023b](https://arxiv.org/html/2406.01252v2#bib.bib272)）、Besta 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib18)）和 Xie 等（[2023](https://arxiv.org/html/2406.01252v2#bib.bib253)）介绍了用于推理过程中的思维状态的实时评估模块。这些模块在搜索过程中作为先验，帮助模型探索需要深思熟虑的问题的行动空间。类似地，RAIN（Li 等，[2024h](https://arxiv.org/html/2406.01252v2#bib.bib124)）利用二元评分提示进行自我评估，以判断生成是否可能有害，从而通过推理时间树搜索增强响应的安全性。Yuan 等（[2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)）使用五点评分提示对模型的指令响应输出进行评分，然后将这些评分转化为部分序，以便使用 DPO 进行迭代训练。

回顾 H1，可以明显看出 H1 作为 H2 的基础，因为评判的准确性直接与 LLM 的校准相关。因此，只有在 H1 有效的情况下，H2 才会有效（Bai 等，[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）。

批评指的是生成修改建议。通过利用 LLM 本身进行批评，建议可以解决错误和不足，例如总结中的错误（Saunders 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib177)）、机器翻译（Fernandes 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib54)）、数学推理（Lin 等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib129)）、决策和编程任务（Saunders 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib177)）。建议也可以涉及抽象价值标准，例如 HHH 相关原则（Chen 等，[2024e](https://arxiv.org/html/2406.01252v2#bib.bib37)；Bai 等，[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）。

改进指的是 LLM 能够提升给定文本的能力。大多数自我改进的工作基于批评模块提供的自然语言理由来修改响应（Bai 等人，[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)；Tan 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib208)；Madaan 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib145)）。一些研究还展示了直接基于标量奖励进行修改的可能性（Shinn 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib190)）。信息较少的批评者对 LLM 而言可能更具挑战，因为它们必须通过推理自行补充更多信息。另一条工作线使用 LLM 对提示进行自我改进（Fernando 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib55)；Yang 等人，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib261)）。

其他：一个有用的 LLM 可以在各种能力上帮助对齐过程，有效替代人类指导。例如，它可以对思维的中间状态进行质量投票（Yao 等人，[2023b](https://arxiv.org/html/2406.01252v2#bib.bib272)），根据问题中预测的条件验证结果（Weng 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib240)），以及自动生成、筛选（Yue 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib285)）和演变指令（Wang 等人，[2023f](https://arxiv.org/html/2406.01252v2#bib.bib233)；Li 等人，[2024f](https://arxiv.org/html/2406.01252v2#bib.bib120)；Xu 等人，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib254)），以及其他任务。

关于持久化过程，从这些方法中获得的改进可以通过 SFT（即专家迭代）、DPO、RM-PPO 等技术进一步提炼到模型中。此外，评判/批评-改进过程可以迭代进行。

##### H2: 讨论

随着判断、批评和改进能力越来越多地被纳入模型反馈和学习过程中，需要对这些能力进行系统评估。在这种背景下，几个研究方向值得深入探讨：

+   1)

    对现有模型在这些原子能力上的性能进行基准测试，如 Sun 等人的工作（[2024a](https://arxiv.org/html/2406.01252v2#bib.bib202)）和 Lin 等人的工作（[2024b](https://arxiv.org/html/2406.01252v2#bib.bib129)）。

+   2)

    对模型的判断、批评和改进能力的形成过程进行因果研究，并调查哪些形式的预训练和微调数据可以影响这些能力。

+   3)

    评估分布变化对这些能力的影响。如果模型没有在相应的指令和响应对上进行训练，它们是否仍然具备可靠的评估和改进能力？这对于可扩展监督问题尤为相关，该问题假设指令缺乏直接监督。

+   4)

    收集实证证据以证明自我批评、判断和改进能力可以在公平合理的实验环境中提升模型性能。一些研究指出，这种改进可能来自于使用更强的模型（Sharma et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib184)）和黄金标签（Huang et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib86)）。

#### 3.1.3 H3：LLMs 可以有效地进行上下文学习

![参考说明](img/ebb17c4cc7cc9df00a33d741a1bf8410.png)

图 5：通过三种代表性的归纳偏差的对齐示意图，这些归纳偏差源自于 LLMs 的组织结构。

上下文学习（ICL）指的是 LLMs 在推理过程中通过示例或经验初始化任务特定模型的能力（Brown et al., [2020](https://arxiv.org/html/2406.01252v2#bib.bib23)）。鉴于某些研究（Dai et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib48)；von Oswald et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib217)）建议 ICL 与参数梯度下降之间存在相似之处，可以将其视为一种多功能且有效的“学习”方法。

从自动化对齐的角度来看，ICL 提供了一种从预训练 LLM 开始冷启动的高效手段。借助 ICL，仅需几个上下文中的对话样本即可产生一个略微对齐的模型（Ganguli et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib61)；Sun et al., [2023d](https://arxiv.org/html/2406.01252v2#bib.bib205)；Lin et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib128)）。同样，通过在上下文中添加一些标注的示例，ICL 也可以在某种程度上引发预训练 LLM 的判断和批评能力，或提升与零-shot 设置相比的性能（Bai et al., [2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）。此外，ICL 提供了一种适应不同社会规范和规定的潜在方法（Xu et al., [2023c](https://arxiv.org/html/2406.01252v2#bib.bib257)）。

然而，在上述上下文中前置少量示例会使推断效率降低（Gim 等， [2023](https://arxiv.org/html/2406.01252v2#bib.bib66)），并且会干扰与不相关的查询（Shi 等， [2023](https://arxiv.org/html/2406.01252v2#bib.bib188)）。因此，从 ICL 中获得的自生成标签可以直接用作伪标签，并仅与查询配对地回流到 LLMs 中。这种范式称为上下文提炼（Askell 等， [2021](https://arxiv.org/html/2406.01252v2#bib.bib13)）。例如，在 Llama-2 的对齐过程中（Touvron 等， [2023](https://arxiv.org/html/2406.01252v2#bib.bib213)），上下文提炼用于缓解系统提示的长期依赖问题。在 Dromedary（Sun 等， [2023d](https://arxiv.org/html/2406.01252v2#bib.bib205)）中，基础语言模型通过直接在多个 ICL 过程中获得的样本上训练，转变为安全且有用的对齐模型，标注最少。Padmanabhan 等（[2023](https://arxiv.org/html/2406.01252v2#bib.bib162)）展示了上下文提炼还可以通过从实体定义中学习继续注入新知识到模型中。此外，Yang 等（[2024b](https://arxiv.org/html/2406.01252v2#bib.bib263)）展示了将由对比上下文约束生成的偏好对回流到模型中的有效性。

此外，ICL 的学习内容还可以包括探索性体验（Shinn 等， [2023](https://arxiv.org/html/2406.01252v2#bib.bib190)）和工具定义（Yao 等， [2022](https://arxiv.org/html/2406.01252v2#bib.bib271)；Tang 等， [2023](https://arxiv.org/html/2406.01252v2#bib.bib209)）。换句话说，配备工具和经验的代理可能比没有这些条件的代理表现更好。这表明，通过经验和工具改进的轨迹在提炼回模型中有类似的潜力，以持续提升同一模型。

##### H3: 讨论

不幸的是，ICL 本身的黑箱特性对对齐提出了重大挑战（Anwar 等， [2024](https://arxiv.org/html/2406.01252v2#bib.bib12)）。由于对 LLMs 如何在上下文中学习缺乏全面理解，上下文提炼方法可能会通过放大模型中固有的偏见和错误而引发问题。此外，长期上下文学习的能力（Agarwal 等， [2024](https://arxiv.org/html/2406.01252v2#bib.bib3)；Li 等， [2024e](https://arxiv.org/html/2406.01252v2#bib.bib119)）需要进一步探讨，因为它促进了更高效的提炼，并且在模型需要理解冗长的专业文档或广泛的自我游戏历史的可扩展监督设置中至关重要。

### 3.2 LLMs 组织的归纳偏差

除了源自 LLMs 共享特征的归纳偏差外，另一组偏差来自多个 LLMs 的组合或组织，如图 [5](https://arxiv.org/html/2406.01252v2#S3.F5 "Figure 5 ‣ 3.1.3 H3: LLMs can effectively learn in-context ‣ 3.1 Inductive Bias from Features of LLMs ‣ 3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey") 所示。根据构成 LLMs 之间的关系是合作还是对抗，两种代表性的归纳偏差出现了：“任务分解”和“自我对抗”。值得注意的是，随着这一领域的发展，我们预计后续文献将采用更复杂的组织和学习结构。对抗和合作模式可能成为复杂代理系统的关键组成部分。然而，在当前阶段，任务分解和自我对抗作为实用的分类方法。后续部分将深入探讨这些概念。

#### 3.2.1 H4: 任务分解

任务分解长期以来被认为是解决复杂问题的有效方法（Lee 和 Anderson，[2001](https://arxiv.org/html/2406.01252v2#bib.bib109)）。例如，在基于集体理性的合作游戏中，联盟所获得的总体收益超过了个人收益的总和（Shapley，[1971](https://arxiv.org/html/2406.01252v2#bib.bib183)）。此外，分而治之的范式和递归是解决大规模和复杂问题时在算法设计中使用的成熟有效手段（Hoare，[1961](https://arxiv.org/html/2406.01252v2#bib.bib80)；Wilf，[2002](https://arxiv.org/html/2406.01252v2#bib.bib243)）。

这种范式的讨论可以追溯到分解认知的假设（Ought, [2017](https://arxiv.org/html/2406.01252v2#bib.bib159)）。它主张认知任务可以递归地分解。如果一个 AI 或人类遇到难以解决的任务，它可以将任务分解，将分解后的问题分配给一系列自己的副本进行并行处理，最后合并这些结果。这些副本专注于短期工作并独立工作。一系列提示方法隐式或部分地采用了分解认知的假设来实现自动对齐。例如，Zhou 等人 ([2023b](https://arxiv.org/html/2406.01252v2#bib.bib302)) 和 Wang 等人 ([2023b](https://arxiv.org/html/2406.01252v2#bib.bib223)) 提示 LLM 分解问题，然后引导其按顺序解决子问题。人们也认为任务分解是一种解决“从简单到困难”泛化的有效方法（Zhou 等人, [2023b](https://arxiv.org/html/2406.01252v2#bib.bib302)），即在简单样本上构建分解提示并在上下文中填充，允许 LLM 有可能对困难样本进行泛化。Khot 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib98)) 进一步实现了递归任务分解。

基于分解认知的假设，迭代蒸馏与放大（IDA）（Christiano 等人, [2018](https://arxiv.org/html/2406.01252v2#bib.bib44)）将每个分解-合并过程视为一种放大的形式，并认为从最终合并结果中学习是一种蒸馏的形式。尽管原始 IDA 论文以人机协作的方式构建了这一理论框架，其中人类监督初始任务分解步骤，但鉴于 H1、H2 和 H3（Zhang 和 Parkes, [2023](https://arxiv.org/html/2406.01252v2#bib.bib291)），这一过程很可能可以在没有过多人工监督的情况下启动。

值得注意的是，IDA 代表了实现可扩展监督的一条有前途的途径，通过将任务分解为更易处理的子问题，使得可以解决难以由人类直接监督的长期任务。例如，像“对这项调查进行同行评审”这样的数据点标签在现实世界中可能需要几个月的时间来收集。这些问题可以通过分解认知更快地解决。尽管一些工作部分地展示了 IDA 在现实世界任务上的有效性，如书籍长度的总结（Wu 等，[2021a](https://arxiv.org/html/2406.01252v2#bib.bib244)）和复杂的代码错误修复（Wen 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib239)），但这一理念仍然依赖于一些关键假设：1) 仍不清楚是否将问题分解是解决问题的最困难部分，如果认知负担无法分配，IDA 可能难以发挥作用。2) 错误不会积累。尽管这一范式不要求代理之间的合作效率（Christiano 等，[2018](https://arxiv.org/html/2406.01252v2#bib.bib44)），但过多的错误仍然可能是问题。3) 任务的并行化程度。如果任务解决过程大部分是顺序的，则收集信号的时间可能会增加，但考虑到当前 LLM 的部署速度，这似乎是一个次要问题。总体而言，由于这些假设难以证明或证伪，我们倡导在这个方向上进行更多的实证研究。

#### 3.2.2 H5: 自我对弈

复杂性源于对抗性（Bansal 等，[2018](https://arxiv.org/html/2406.01252v2#bib.bib17)）。自我对弈指的是一种通过不断地与自己对弈来学习的范式，这是一种非合作性博弈（Nash 等，[1951](https://arxiv.org/html/2406.01252v2#bib.bib154)），在这种博弈中，每个代理都旨在最大化自身效用。它作为许多成功的专业超人类 AI 系统的基础，如 AlphaGo Zero（Silver 等，[2018](https://arxiv.org/html/2406.01252v2#bib.bib192)）和 StockFish（StockFish，[2023](https://arxiv.org/html/2406.01252v2#bib.bib200)）。鉴于这些成功，自我对弈似乎是使 LLM 实现通用超人类智能的潜在方法。两种代表性的自我对弈方法是生成器-判别器和辩论方法，后者涉及 $N\geq 2$ 个对抗生成器和一个判别器在一个游戏环境中。

##### H5.1: 生成器-判别器

在生成器-判别器自我对弈框架中，判别器的角色是评估生成器产生的输出，确定这些输出的质量是高还是低。

如 H2 中所讨论的，评判和评论模型通常被视为一种判别器。例如，袁等人 ([2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)) 利用 LLM-as-a-Judge 的奖励来识别生成器生成的高质量和低质量响应，从而优化生成器，使其朝着更高质量的方向发展。然而，判别器和生成器之间的对抗设置是有限的，因为唯一的假设是判别器的能力可以通过一般的有益训练来提高。在训练过程中，判别器几乎保持静态（提示未改变），这使得生成器可能过度优化于判别器，从而导致奖励破解。因此，有效改进评判和评论模块以及生成器是一个关键问题。一个合理的方法是使用在线 AIF 设置，正如郭等人 ([2024a](https://arxiv.org/html/2406.01252v2#bib.bib72)) 所建议的。此外，程等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib41)) 提出了一个策略与奖励模型之间的对抗游戏，通过一个约束的最小-最大损失来实现。另一种引入更多对抗设置的方法是在推理时优化游戏问题，如 Jacob 等人 ([2024](https://arxiv.org/html/2406.01252v2#bib.bib91)) 在 Consensus Game 中所展示的那样。该方法采用 piKL 无悔学习算法来迭代更新生成器和判别器的策略，最终收敛到纳什均衡。然后，使用这个均衡策略对候选响应进行排序，优先考虑那些被双方玩家都认可的响应。

由于生成对抗网络（GANs）（Goodfellow 等，[2014](https://arxiv.org/html/2406.01252v2#bib.bib67)）已成为传统自然语言处理（NLP）（Zhang 等，[2016](https://arxiv.org/html/2406.01252v2#bib.bib294)；Wu 等，[2021b](https://arxiv.org/html/2406.01252v2#bib.bib247)）中的成熟方法，另一类工作涉及使用类似 GAN 的判别器来区分模型当前预测的分布和真实分布。例如，Chen 等（[2024g](https://arxiv.org/html/2406.01252v2#bib.bib40)）发现，一种特定类型的迭代 DPO 训练，将策略生成的响应始终视为负面而真实响应视为正面，可以被视为一个自我对弈的过程。在这个过程中，DPO 的隐式奖励函数充当了模型预测和真实样本之间的判别器。在此基础上，Shaikh 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib181)）进一步添加了早期模型与真实样本之间的重放对比信号，以及模型与其后续模型在自我对弈过程中的对比。然而，对于开放性问题，真实分布有时仍然是次优的，这种情况下生成比真实响应更好的响应的可能性是不存在的。

##### H5.2：辩论

辩论范式（Irving 等，[2018](https://arxiv.org/html/2406.01252v2#bib.bib90)）在很大程度上受到分解认知和 AlphaGo（Silver 等，[2018](https://arxiv.org/html/2406.01252v2#bib.bib192)）的启发。在 AlphaGo 的学习算法中，整合了三个不同的组件：一个玩家、一个对手（即自身）和一个评估每个棋盘状态的胜率的价值模型。通过使用蒙特卡洛树搜索（MCTS），该算法进行模拟自我对弈，直到游戏结束。这些模拟通过基于结果的向后更新来提高价值估计的准确性，同时通过利用先前导致胜利的策略来不断优化策略。

围棋游戏与使用自然语言辩论解决可扩展监督问题有相似之处。在围棋游戏的开始或中期，即使是经验丰富的专家也可能难以判断哪一方获胜的概率更高，就像人类在判断超出人类知识水平的问题时也有小概率会出现错误。然而，随着游戏接近结束，结果通常会变得明确，以至于即使是非专家评判者也可以自信地评估围棋大师所生成的棋盘。在辩论比赛中，胜者通常可以由评委总结出来。

这提供了一种可能的监管解决方案，以构建值得信赖的超人类 AI 系统。Irving 等人（[2018](https://arxiv.org/html/2406.01252v2#bib.bib90)）通过概念验证实验表明，在辩论范式中，诚实比撒谎更佳策略。作为这一研究的扩展，Brown-Cohen 等人（[2023](https://arxiv.org/html/2406.01252v2#bib.bib24)）提出了一套新的辩论协议，其中诚实策略可以通过涉及仅多项式数量步骤的模拟始终取得成功。Khan 等人（[2024](https://arxiv.org/html/2406.01252v2#bib.bib97)）对在 LLMs 上实现辩论范式的可行性进行了彻底的实证研究：研究发现，辩论范式可以显著提高真实性，而更具说服力的（Anthropic，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib10)）辩论者能够带来更真实的结果。

除了经典的自然语言辩论外，一系列工作已将辩论范式应用于游戏场景。一个代表性的领域是谈判任务（Nash et al., [1950](https://arxiv.org/html/2406.01252v2#bib.bib153)）。Fu et al. ([2023a](https://arxiv.org/html/2406.01252v2#bib.bib59)) 关注谈判的零和变体，其中气球卖家旨在以更高的价格出售，而买家则寻求更低的价格。他们观察到不同 LLM 之间的谈判能力存在显著差异，以及它们从游戏体验和反馈中学习的能力。Cheng et al. ([2024](https://arxiv.org/html/2406.01252v2#bib.bib42)) 实现了对抗性语言游戏对抗禁忌（Yao et al., [2021](https://arxiv.org/html/2406.01252v2#bib.bib273)），其中攻击者和防御者围绕仅攻击者可见的目标词进行对话。攻击者微妙地引导防御者无意识地说出目标词，而防御者则尽量避免这样做，并从上下文中猜测目标词。两名玩家通过模仿学习从教师 LLM 中获取基本的游戏技能，然后通过自我对弈完善策略。有趣的是，能力较差的 LLM 玩家不仅提高了在这个特定游戏中的胜率，还提升了它们的整体推理能力。Ma et al. ([2023a](https://arxiv.org/html/2406.01252v2#bib.bib143)) 介绍了红队游戏，这是一个更复杂的对抗性团队游戏，其中 LLMs 被初始化为一组联合的红队策略，以促使目标 LLM 产生有害内容。他们提出了一种求解器，以确保最终的元策略在一定的 $\epsilon$ 范围内接近纳什均衡。Zheng et al. ([2024c](https://arxiv.org/html/2406.01252v2#bib.bib298)) 建议通过允许攻击者提示防御者 LLM 生成可能导致低奖励的回答来解决对齐问题，而防御者则尝试最大化这些提示的奖励。这个游戏的解决方案被认为是一个具有约束的迭代最小最大优化过程。

#### 3.2.3 讨论

任务分解和自我对抗都要求大型语言模型（LLMs）充当代理。然而，将 LLMs 作为代理进行对齐的挑战比作为聊天机器人进行对齐要复杂，因为这需要考虑行为层次的对齐（Pan et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib163)）、环境和自我约束的动态（Garrabrant and Demski, [2018](https://arxiv.org/html/2406.01252v2#bib.bib64); Shavit et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib185); Yang et al., [2024f](https://arxiv.org/html/2406.01252v2#bib.bib269)）。我们强调这一研究方向的重要性，并倡导在这一领域增加努力。此外，更复杂的问题在于证明多代理系统的理论安全性和可信度。尽管该领域的研究仍处于初期阶段（Yang and Wang, [2020](https://arxiv.org/html/2406.01252v2#bib.bib267); DiGiovanni and Zell, [2021](https://arxiv.org/html/2406.01252v2#bib.bib50)），但博弈论的进展（Hazra and Anjaria, [2022](https://arxiv.org/html/2406.01252v2#bib.bib76)）、自动定理证明技术（Polu and Sutskever, [2020](https://arxiv.org/html/2406.01252v2#bib.bib168)）和现实世界模拟技术（Brooks et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib22)）可能会为解决这一挑战提供见解。

虽然对抗性自我对抗提供了一种可能的解决方案来应对可扩展监督的挑战，但它也可能导致出现更多的欺骗性（Hubinger et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib89)）、具有说服力和自主性的代理（Tao et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib210)）。这些发展可能带来显著的社会影响和伦理风险，例如模型生成的文章比人类更具说服力，可能被用于政治操控。令人鼓舞的是，几家主要的模型引擎提供商已经采取措施来监控和减轻这些潜在副作用。例如，OpenAI 的 Preparedness 团队已经建立了与说服力和自主性相关的基准（OpenAI, [2023a](https://arxiv.org/html/2406.01252v2#bib.bib156)）。他们将模型风险分为四个等级：低、中、高和关键，规定高风险阈值以上的模型不能开发，中风险以上的模型不能部署。我们呼吁学术界和第三方组织在高度能力代理的安全框架的开发和审查中投入更多努力。

## 4 通过行为模仿进行对齐

> 模仿是觉醒的心灵的第一本能。
> 
> 玛利亚·蒙特梭利

通过行为模仿进行对齐是另一种广泛使用的自动化对齐策略，它通过模仿另一个已对齐模型的行为来对齐目标模型。具体而言，如图 [6](https://arxiv.org/html/2406.01252v2#S4.F6 "图 6 ‣ 4 通过行为模仿对齐 ‣ 朝着可扩展的 LLM 自动化对齐：一项调查")所示，该方法开始时收集高质量的指令作为任务描述（Wang et al., [2023f](https://arxiv.org/html/2406.01252v2#bib.bib233)）。然后，使用一个监督模型生成对齐信号，这些信号通常包括指令-响应对（Taori et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib211)），成对的偏好数据（Cui et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib47)）以及其他对齐信号（Fränken et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib58)）。最终，目标模型通过模仿这些生成的行为进行对齐。

基于监督模型和目标模型之间的能力比较，通过行为模仿对齐的研究可以分为强对弱蒸馏（§[4.2](https://arxiv.org/html/2406.01252v2#S4.SS2 "4.2 强对弱蒸馏 ‣ 4 通过行为模仿对齐 ‣ 朝着可扩展的 LLM 自动化对齐：一项调查")）和弱对强对齐（§[4.3](https://arxiv.org/html/2406.01252v2#S4.SS3 "4.3 弱对强对齐 ‣ 4 通过行为模仿对齐 ‣ 朝着可扩展的 LLM 自动化对齐：一项调查")）。对于每个类别，我们将彻底回顾代表性研究，总结当前进展和局限性，并讨论未来方向。

![参见标题](img/1a659a5b01c2ef160b61ce311c78d792.png)

图 6: 通过行为模仿对齐的代表性研究插图。

### 4.1 指令构建

收集大规模的高质量、多样化的指令是通过行为模仿实现对齐的基础。最直观的策略涉及从人工编写的指令中筛选出高质量的数据。然而，这种方法需要大量的人力和专业知识，同时也引入了显著的噪声。因此，许多研究集中在利用 LLM 进行自动指令生成，从而显著减少对人工注释的依赖。基于指令构建的信息，目前有 3 种代表性策略：

上下文生成，通过提供上下文演示来指导 LLM 生成指令。例如，Honovich 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib83)); Wang 等人 ([2023f](https://arxiv.org/html/2406.01252v2#bib.bib233)); Taori 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib211)) 从一小组人工编写的指令开始。这些指令被随机选择，以创建上下文示例，提示 LLM 生成额外的指令。为了进一步提高生成指令的规模和多样性，LaMini-LM (Wu 等人，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib246)) 还引入了维基数据进行主题引导的指令生成，从而构建了一个大型的离线蒸馏指令数据集。Dynosaur (Yin 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib274)) 利用现有 NLP 数据集中的元信息来创建一个动态增长的指令调优数据集。此外，LLM2LLM (Lee 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib111)) 通过迭代引入模型无法正确回答的示例来增强指令的难度和复杂性。

指令进化，涉及根据预定义的进化原则重写现有指令。Evol-Instruct (Xu 等人，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib255)) 利用 LLM 基于手写原则进行指令进化，从而减少对人工标注的需求，并增强模型管理复杂任务的能力。在此基础上，TeaMs-RL (Gu 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib70)) 通过强化学习训练另一个模型，以生成优化的进化轨迹。考虑到对手动编写原则的依赖，Auto Evol-Instruct (Zeng 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib290)) 提出了自动化原则构建方法，进一步增强了进化指令的多样性和复杂性。

指令回译，利用 LLM 根据从人工手写文本或网页文档中提取的响应预测指令。LongForm (Köksal 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib103))，TEGIT (Chen 等人，[2023e](https://arxiv.org/html/2406.01252v2#bib.bib38)) 和 Humpback (Li 等人，[2024f](https://arxiv.org/html/2406.01252v2#bib.bib120)) 提示 LLM 根据清洗后的网络语料库构建指令。REInstruct (Chen 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib33)) 从未标记的语料库中构建指令，并重写未标记的文本以提高其作为响应的质量。

### 4.2 强到弱的蒸馏

基于收集到的指令，从强到弱的蒸馏试图通过模仿由另一个更强大和良好对齐的模型生成的响应或偏好数据来调整较弱的目标模型。在接下来的小节中，我们将分别介绍响应引导和偏好引导蒸馏的代表性研究。

#### 4.2.1 响应引导蒸馏

在响应引导蒸馏中，目标模型通过直接学习不同指令的响应来模拟教师模型，这是通过调整指令来实现的。这种方法启发了许多研究，旨在从教师模型蒸馏出各种能力给目标模型。这些能力不仅包括通用的指令跟随能力，还包括领域特定的能力，如数学、编程和与代理相关的任务。

##### 指令跟随

在构建指令数据之后，可以轻松地从教师模型开发相应的响应。使用这些指令-响应对进行训练，可以模拟教师按指令执行的能力。例如，LLaMA-GPT4 （Peng et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib167)）利用 GPT-4 生成由 Alpaca（Taori et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib211)）的指令衍生的响应。除了单回合数据，一些研究专注于从教师模型收集多轮轨迹。Baize（Xu et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib256)）和 Ultrachat（Ding et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib51)）使用两个 ChatGPT API 扮演用户和助手的角色，生成多轮对话。Parrot（Sun et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib203)）训练模型模拟人类生成指令，并使用这些训练模型与 ChatGPT 就各种话题进行多轮对话。

##### 数学

Wizardmath (Luo et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib140)) 采用 Evol-Instruct 方法构建了一个专门用于数学推理任务的全面数据集。MetaMath (Yu et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib277)) 利用 ChatGPT 通过从多个角度重新表述问题来引导数学问题，而不引入额外的知识。MAmmoTH (Yue et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib284)) 生成了一个数据集，包含数学问题和模型生成的解决方案，这些解决方案通过链式思维 (CoT) 和程序化思维 (PoT) 推理的独特组合来区分。MathCoder (Wang et al., [2024d](https://arxiv.org/html/2406.01252v2#bib.bib222)) 使用 GPT-4 代码解释器生成创新且高质量的数学问题及其基于代码的解决方案。MathGenie (Lu et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib139)) 通过问题回译的过程生成多样化且可靠的数学问题。MARIO (Liao et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib126)) 利用 GSM8K 和 MATH 作为种子数据，生成了 26.9K 个由 GPT 和人工专家标注的解决方案。除了纯数学数据外，还有几项研究提出通过生成详细的 CoT 响应，将商业 LLM 的核心推理能力转移到小型模型中 (Shridhar et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib191); Fu et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib60); Hsieh et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib85); Magister et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib146); Ho et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib79); Li et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib118), [2023a](https://arxiv.org/html/2406.01252v2#bib.bib112); Zhou et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib303); Hong et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib82))。

##### 编码

最先进的 LLM，如 GPT-4，在编码任务中表现出色。除了在原始代码数据上进行预训练，一些方法还旨在通过指令调优将编码能力从教师模型转移。Code Alpaca (Chaudhary, [2023](https://arxiv.org/html/2406.01252v2#bib.bib28)) 和 WizardCoder (Luo et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib142)) 遵循通用的自动指令构建范式。Code Alpaca 使用 Self-Instruct 在 20K 指令跟随数据上，从而将 Alpaca 的能力扩展到编码领域。WizardCoder 采用 Evol-Instruct 方法处理编码领域，从简单的编码和编程指令生成复杂的代码和程序指令。WaveCoder (Yu et al., [2024c](https://arxiv.org/html/2406.01252v2#bib.bib279)) 和 Magicoder (Wei et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib238)) 利用开源代码数据集创建高质量的指令数据。WaveCoder 通过开源代码片段提升 LLM 的能力，为编码任务生成更优质的指令数据。Magicoder 根据 Self-Instruct 的技术创建多任务数据。OpenCodeInterpreter (Zheng et al., [2024d](https://arxiv.org/html/2406.01252v2#bib.bib299)) 利用 GPT-3.5 和 GPT-4 通过集成的文本解释和代码片段改进解决方案，结合执行和反馈进行动态代码优化。

##### 智能体

尽管开源 LLM 在许多方面已实现与商业模型相当的性能，但其在智能体相关功能上的能力，如工具使用和复杂任务规划，仍然有限。为了解决这一问题，ToolLLM (Qin et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib170)) 创建了一个名为 ToolBench 的指令调优数据集，与 ChatGPT 合作，以零样本的方式获得一般工具使用能力。类似的工作还包括 Graph-ToolFormer (Zhang, [2023](https://arxiv.org/html/2406.01252v2#bib.bib292))、Gorilla (Patil et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib166))、GPT4Tools (Yang et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib264))、ToolAlpaca (Tang et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib209)) 等。除了工具使用，一些研究还关注任务规划。例如，FIREACT (Chen et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib30))、AgentTuning (Zeng et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib288))、ReAct Meets ActRe (Aksitov et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib5))、ReST meets ReAct (Yang et al., [2024e](https://arxiv.org/html/2406.01252v2#bib.bib268)) 和 ETO (Song et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib198))。

#### 4.2.2 偏好引导蒸馏

尽管响应引导蒸馏可以提升学生模型的性能（Wang 等人，[2022](https://arxiv.org/html/2406.01252v2#bib.bib232)），但并不能有效地帮助学生模型与人类偏好对齐（Xu 等人，[2024c](https://arxiv.org/html/2406.01252v2#bib.bib259)）。因此，一些工作集中于偏好引导蒸馏，该方法将学生模型与老师模型输出中反映的偏好对齐。在这一范式中，老师模型被引导生成偏好数据，形式为部分序对，然后利用直接偏好优化算法如 DPO（Rafailov 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib171)）、IPO（Azar 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib14)）和 PRO（Song 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib196)）来对齐学生模型。基于构建部分序信号的方法，当前的工作主要包括三种范式：1）基于分数的，涉及对响应进行评分和排名；2）基于改进的，涉及利用 AI 反馈改进现有响应；和 3）基于来源的，专注于学习不同数据源的人类偏好。

##### 基于分数的

通过精心设计的多样化指令和模型响应的实施，以及 GPT-4 提供的详细的数值和文本反馈，UltraFeedback（Cui 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib47)）生成了一个大规模、高质量的细粒度注释的偏好数据集。此外，Zephyr（Tunstall 等人，[2023](https://arxiv.org/html/2406.01252v2#bib.bib214)）利用 UltraFeedback 上的蒸馏直接偏好优化来开发小型但高效的 LLMs。CodeUltraFeedback（Weyssow 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib242)）利用 GPT 的 LLM 作为评判器，评估来自 14 种不同 LLM 池的响应，并根据五种编码偏好进行对齐。

##### 基于改进的

其他研究使用强大的模型来改进初始响应。Aligner (Ji et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib93)) 和 MetaAligner (Yang et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib262)) 利用如 GPT-4 等模型来修订原始响应并构建偏好数据。IterAlign (Chen et al., [2024e](https://arxiv.org/html/2406.01252v2#bib.bib37)) 使用 LLM 自动发现新的构造，并优化从红队数据集中生成的响应，以创建偏好数据。Safer-Instruct (Shi et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib189)) 采用反向指令调优、指令归纳和专家模型评估，利用原始文本和 GPT-4 生成的响应来构建高质量的偏好数据。UltraInteract (Yuan et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib281)) 为每个指令构建一个偏好树，其中轨迹是根到叶的路径，配对的正确和错误节点或轨迹可以用于对齐。

##### 基于源

从单一模型中学习偏好可能缺乏多样性并放大偏见。因此，一些研究从不同的数据源构建部分顺序信号。AlMoST (Kim et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib99))、CycleAlign (Hong et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib81)) 和 Openchat (Wang et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib219)) 专注于从不同的数据源学习比较偏好。Kim et al. ([2023](https://arxiv.org/html/2406.01252v2#bib.bib99)) 将人类偏好转化为一系列经验先验规则，利用不同规模的 LLM 生成偏好数据。Wang et al. ([2024b](https://arxiv.org/html/2406.01252v2#bib.bib219)) 将不同的数据源视为粗粒度的奖励标签，通过 GPT-3 和 ShareGPT 生成混合质量的数据。Hong et al. ([2023](https://arxiv.org/html/2406.01252v2#bib.bib81)) 通过比较白盒和黑盒模型在一系列响应中的一致性排名对响应进行排名，并通过这种排名构建偏好数据作为背景。

### 4.3 从弱到强的对齐

正如我们在第[1](https://arxiv.org/html/2406.01252v2#S1 "1 Introduction ‣ Towards Scalable Automated Alignment of LLMs: A Survey")节中提到的，规模化监督的挑战成为了人工智能系统持续发展的重要障碍。具体来说，困难在于随着人工智能系统的能力逐渐超越人类，如何有效地提供监督。由于强到弱的蒸馏方法不切实际，*弱到强的对齐*成为了实现自动化规模化监督的最有前景的方向之一（Burns 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib25)）。以往的研究主要集中于人类与人工智能之间的弱到强的泛化，例如迭代放大方法（Christiano 等，[2018](https://arxiv.org/html/2406.01252v2#bib.bib44)），通过迭代放大弱专家来监督强学习者。最近的研究开始探索使用较弱的模型来指导较强的模型以实现超级对齐（Burns 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib25); Liu 和 Alahi，[2024](https://arxiv.org/html/2406.01252v2#bib.bib136)）。根据对齐信号的来源，这些研究可以分为两类：1）使用较小但已对齐的模型来生成信号，以及 2）使用较弱的模型来指导较强的模型生成信号。此外，一些研究探讨了模型是否可以从简单任务中的行为中学习，以提高其在更具挑战性任务中的表现，虽然这不是经典的行为模仿，但仍然值得注意（Hase 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib74); Sun 等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib206)）。在接下来的子章节中，我们将分别介绍每个类别中的代表性研究。

Burns 等人（[2023](https://arxiv.org/html/2406.01252v2#bib.bib25)）采用较弱的 LLM 作为教师，使用弱到强的方法训练较强的 LLM。他们基于较小但对齐的模型生成的标签来微调较大的预训练模型，并观察到较大的目标模型始终优于较小的监督模型。Liu 和 Alahi（[2024](https://arxiv.org/html/2406.01252v2#bib.bib136)）则致力于通过与多样的专业教师群体共同监督强学生，进一步提升强模型的对齐效果。Somerstep 等人（[2024](https://arxiv.org/html/2406.01252v2#bib.bib195)）将弱到强的泛化视为迁移学习问题，通过标签细化过程实现这一点。Yang 等人（[2024d](https://arxiv.org/html/2406.01252v2#bib.bib266)）研究了弱到强泛化中的多目标对齐，并发现强学生可能会欺骗弱教师，以在其他维度获得高奖励，这可以通过使用中间模型来缓解。此外，Aligner（Ji 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib93)）和 MetaAligner（Yang 等人，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib262)）通过使用显著较小但对齐的模型来优化强模型的响应，从而创建部分顺序数据。

除了直接从弱模型生成信号之外，实现弱到强对齐的另一种可能方法是使用弱模型来指导强模型生成信号。Li 等人（[2024c](https://arxiv.org/html/2406.01252v2#bib.bib116)）发现，弱和强 LLM 在感知指令难度和选择数据的能力上高度一致。因此，可以利用较小和较弱的模型来为更大更强的模型选择数据进行微调。同样，SAMI（Fränken 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib58)）使用弱模型为强基线模型编写宪法以进行对齐。

上述工作在一定程度上实现了弱到强的对齐，并探讨了实现超对齐的潜在方向。然而，较弱的模型可能不适合作为更复杂任务的有效指导者。因此，一些研究尝试使用从简单任务中获得的信号来对齐模型，这些信号更容易生成和学习，从而提高在更困难任务上的表现。例如，Hase 等人（[2024](https://arxiv.org/html/2406.01252v2#bib.bib74)）观察到，当前的语言模型通常能从简单数据很好地推断到复杂数据，甚至可以与直接在复杂数据上训练的模型竞争。Sun 等人（[2024b](https://arxiv.org/html/2406.01252v2#bib.bib206)）使用在简单任务上训练的奖励模型来评估和指导在更具挑战性任务上的策略模型，从而实现任务泛化。

### 4.4 讨论

当前的研究利用教师模型的响应或偏好，以促进在各种任务中的有效泛化和扩展性，从而显著减少对人工标注的需求。然而，这些方法也存在显著的局限性，包括数据质量问题、教师模型固有的偏差以及对超对齐的探索不足。

##### 数据质量

合成数据的质量仍然是一个重要的关注点。许多研究强调了数据质量对于对齐的重要性（Zhou et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib301); Chen et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib31)）。由于模型生成过程中的固有随机性，从教师模型中获取的训练信号往往会很嘈杂。为了解决这个问题，近期的研究集中在两个主要范式上：首先，通过制定详细和精细的原则来生成高质量的数据，如 Orcas（Mukherjee et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib152); Mitra et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib150)）和 AttrPrompt（Yu et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib278)）；其次，通过建立评估指标或采用过滤范式，从现有数据集中提取相对高质量的数据，如 Reflection-Tuning（Li et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib114), [2024b](https://arxiv.org/html/2406.01252v2#bib.bib115)）和 Phis（Li et al., [2023d](https://arxiv.org/html/2406.01252v2#bib.bib123); Abdin et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib1), [2024](https://arxiv.org/html/2406.01252v2#bib.bib2)) ³³3 由于许多研究，例如 Wang et al. ([2024c](https://arxiv.org/html/2406.01252v2#bib.bib221))，对数据选择进行了详细调查，我们在此不深入探讨。此外，一些研究表明对齐算法具有一定的鲁棒性（Gao et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib63)）。因此，开发更鲁棒的训练算法可能是减轻数据质量相关问题的另一种方法。

##### 教师模型的偏差

此外，依赖教师模型可能会引入教师模型固有的偏差和局限性，这可能会影响对齐效果。一些研究建议引入多个教师模型来对齐学生模型（Cui et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib47); Liu and Alahi, [2024](https://arxiv.org/html/2406.01252v2#bib.bib136)），从而减少模型对单一教师模型偏差的过拟合可能性。利用多个教师还可以增加信号的多样性，显著提高对齐效果（Song et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib197)）。

##### 对超对齐的理解不足

实现超对齐仍然是一个重大挑战。我们仍然缺乏对超对齐的强有力的科学理解 (Burns et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib25))，这阻碍了对弱到强对齐的进一步探索。此外，目前的大多数方法仍然需要一个充分对齐的“弱”模型，而如何利用一个真正的弱模型来实现超对齐仍然是一个问题。一些研究提出了理解弱到强泛化的理论框架 (Charikar et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib27); Lang et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib105); Somerstep et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib195))，但应用范围仍然有限。一个有趣的路径是 ExPO (Zheng et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib295))。ExPO 直接从一个 SFT 模型和一个对齐模型的权重中外推，获得了一个更好对齐的模型，而无需额外的训练，展示了一种从弱到强的有前景的方法。

总之，尽管在指令和行为构建方面取得了显著进展，但当前的方法仍然存在重大局限。强到弱方法的核心问题在于对齐的上限受制于教师模型。相反，关于弱到强对齐的研究仍处于起步阶段，缺乏理论分析和普遍方法。未来必须解决几个关键问题，包括有效提升数据质量、开发更稳健的训练算法、实施多教师模仿，并对一般任务中的弱到强对齐进行理论分析。解决这些挑战将为 LLMs 的进一步发展铺平可行的道路。此外，我们还在第 [7](https://arxiv.org/html/2406.01252v2#S7 "7 Underlying Mechanism of Automated Alignment ‣ Towards Scalable Automated Alignment of LLMs: A Survey") 节提供了关于弱到强对齐的基本机制的深入讨论，这有助于对该领域有更深刻的理解。

## 5 通过模型反馈进行对齐

> 我们都需要有人给我们反馈。这就是我们进步的方式。
> 
> 比尔·盖茨

人类反馈反映了人类的价值观，可以用来对齐 LLMs，使 LLMs 能够生成有帮助和安全的响应，同时纠正错误和有毒输出。不幸的是，由于低效和高成本，训练过程中获取人类反馈具有挑战性。为了解决这一问题，引入了模型反馈作为估计人类反馈的一种方式。这种方法在强化学习中被广泛利用，其中奖励模型生成反馈。与依赖于人类生成的有限反馈数据相比，奖励模型可以在更广泛的分布上进行反馈预测，从而实现更高效的对齐。通过自动生成的模型反馈进行对齐提供了一种有效的将 LLMs 与人类价值观对齐的方法，展示了实现自动化对齐的有希望的途径。在本节中，我们解释了如何利用模型提供的反馈将其与人类价值观对齐。如图 [7](https://arxiv.org/html/2406.01252v2#S5.F7 "图 7 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的 LLMs 自动化对齐：综述")所示，相关方法可以根据反馈信号的形式分为三类：标量（§ [5.1](https://arxiv.org/html/2406.01252v2#S5.SS1 "5.1 标量奖励 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的 LLMs 自动化对齐：综述")），二进制（§ [5.2](https://arxiv.org/html/2406.01252v2#S5.SS2 "5.2 二进制验证器 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的 LLMs 自动化对齐：综述")），和文本信号（§ [5.3](https://arxiv.org/html/2406.01252v2#S5.SS3 "5.3 文本评论 ‣ 5 通过模型反馈对齐 ‣ 朝着可扩展的 LLMs 自动化对齐：综述")）。

![参见说明](img/b70cd20838f82652e09cae77fa4eec83.png)

图 7：通过奖励模型生成的模型反馈对齐的示意图。奖励模型将自动生成 LLMs 响应的标量、二进制或文本格式反馈。

### 5.1 标量奖励

标量信号通常由奖励模型生成，该模型以 LLMs 的响应作为输入，生成用于估计人类偏好的标量信号。奖励模型常用于强化学习，以使 LLMs 与人类价值观对齐。通过这种方式，LLMs 可以利用奖励模型提供的大量和多样的反馈自动对齐人类价值观。为了实现更有效的自动化对齐，近期研究集中在如何训练更高质量的奖励模型，并通过模型生成或预训练减少对人类注释的依赖。此外，奖励模型生成的标量信号还可以用于优化 LLMs 在解码过程中的生成，并筛选用于指令微调的训练数据。

#### 5.1.1 来自人类反馈的强化学习

来自人类反馈的强化学习 (RLHF) 是将大型语言模型 (LLMs) 与人类价值观对齐的重要范式 (Christiano et al., [2017](https://arxiv.org/html/2406.01252v2#bib.bib45); Stiennon et al., [2020](https://arxiv.org/html/2406.01252v2#bib.bib199); Ouyang et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib160))。它通常包括三个步骤：1) 监督微调 (SFT)，在标注数据上训练 LLMs，以改善它们对提示的响应；2) 训练奖励模型以预测人类对模型响应的反馈；3) 使用诸如 Proximal Policy Optimization (PPO) (Schulman et al., [2017](https://arxiv.org/html/2406.01252v2#bib.bib179)) 的强化学习算法来对齐模型。在 RLHF 中，奖励模型通常基于人类标注的偏好数据进行训练，生成模仿人类反馈的标量信号，作为学习的指导信号。奖励模型的表现决定了模型对齐的潜在上限，因此训练奖励模型至关重要 (Zheng et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib297))。在接下来的部分中，我们首先介绍有关增强奖励模型的相关工作。然后，我们介绍如何在没有人工努力的情况下生成偏好数据。最后，我们介绍奖励模型在强化学习之外的功能，包括解码阶段的对齐和 SFT 数据过滤。

#### 5.1.2 奖励建模的改进

为了实现更有效的自动对齐，提高模型反馈的质量至关重要。因此，近期的研究集中在学习高质量的奖励模型。训练奖励模型的主要挑战包括数据收集和模型优化。收集到的偏好数据通常稀疏且缺乏一致性和细节，而模型优化可能会受到过拟合等问题的阻碍。

##### 奖励模型预训练

由于现有数据集的数据稀疏性和人工注释的成本，很难为自动对齐训练一个高质量的奖励模型。为此，Askell 等人 ([2021](https://arxiv.org/html/2406.01252v2#bib.bib13)) 提出了奖励模型预训练方法。通过从网络中收集对比数据，包括 StackExchange、Reddit 和 Wikipedia，他们构建了一个排名数据集来预训练一个偏好模型。通过利用奖励模型预训练，减少了对人工注释的依赖 (Bai et al., [2022a](https://arxiv.org/html/2406.01252v2#bib.bib15))，这有助于更高效地训练奖励模型并提高自动对齐的效果。

##### 一致性偏好数据构建

由于人工标注者有不同的评估原则和主观视角，反馈也因此多样化，包含了多个观点。以往的研究采用了诸如多模型集成（Rame 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib172)；Touvron 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib213)）、多目标学习（Zeng 等，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib289)；Zhong 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib300)；Guo 等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib73)；Yang 等，[2024c](https://arxiv.org/html/2406.01252v2#bib.bib265)）等策略来缓解多样性数据带来的负面影响。与生成单一评分的奖励模型不同，Li 等（[2024a](https://arxiv.org/html/2406.01252v2#bib.bib113)）引入了分布偏好奖励模型（DPRM），用于预测偏好分布。

##### 细粒度反馈收集

奖励模型在处理复杂情况如安全性和推理等挑战性任务时，通常难以提供细粒度的反馈。为了解决这个问题，一些研究集中于改进奖励模型的训练。Chen 等（[2024f](https://arxiv.org/html/2406.01252v2#bib.bib39)）引入了一种可以在令牌级别提供精确反馈的令牌级奖励模型，适用于推理等复杂任务。Wu 等（[2023b](https://arxiv.org/html/2406.01252v2#bib.bib250)）建议训练多个能够在文本跨度级别提供详细反馈的奖励模型。

##### 训练优化

奖励模型的学习过程通常面临过度优化的问题。也就是说，通过学习，奖励模型的表现反而变差。Gao 等（[2023](https://arxiv.org/html/2406.01252v2#bib.bib62)）通过实验分析了这一现象，并发现奖励模型的缩放规律以指导学习。Zhu 等（[2023a](https://arxiv.org/html/2406.01252v2#bib.bib304)）对 RLHF 中奖励模型训练进行了理论分析，并展示了训练过程中引入悲观主义的重要性。此外，还有一些其他工作采用了多种方式来提高奖励模型的性能，包括归一化（Zheng 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib297)）和迭代学习（Touvron 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib213)）。

尽管奖励模型的目的是预测人类反馈，但建模奖励却具有挑战性。因此，如何构建更全面的奖励模型以实现自动化对齐是一个重要的研究问题。

#### 5.1.3 来自 AI 反馈的强化学习

奖励模型通常依靠人类反馈进行训练，而这种反馈的标注既困难又昂贵。为了减少人工工作量并提高对齐的自动化，有些研究利用现有的大型语言模型生成偏好数据。AI 反馈强化学习（RLAIF）（Lee 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib110)）通过 LLM 的偏好数据训练奖励模型，并且可以达到与 RLHF 相当或更优的性能。这些方法主要分为两种，包括对多个模型的响应进行排序和直接生成正面与负面响应。通过这种方式，可以在整个强化学习过程中实现自动对齐，无需人工干预。

##### 排序多个响应

随着 LLM 能力的提升，直接使用它们对多个响应进行排名可以提供偏好数据（Tunstall 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib214); Hong 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib81); Guo 等，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib72); Pace 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib161); Yuan 等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)）。这种排序的偏好数据也可以通过最小的人工监督生成，例如通过人工定义的原则（Bai 等，[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16); Sun 等，[2023c](https://arxiv.org/html/2406.01252v2#bib.bib204)）或规则（Kim 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib99)）。为了提高生成偏好数据的质量，Shi 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib189)）提出了一个精心设计的流程，包括反向指令调整、指令诱导和专家模型评估。Liu 等（[2024a](https://arxiv.org/html/2406.01252v2#bib.bib130)）提出使用对比提示对响应进行评分，这相比直接使用单一提示生成的反馈可以实现更好的性能。

##### 生成正面和负面响应

一些研究通过提示 LLM 直接生成偏好数据，包括生成正面响应和负面响应（Chen 等，[2024c](https://arxiv.org/html/2406.01252v2#bib.bib34)）。Yang 等（[2024b](https://arxiv.org/html/2406.01252v2#bib.bib263)）使用间接方法，通过不同的提示分别生成正面和负面响应。

尽管前景广阔，但主要挑战在于偏好数据的质量。由于 LLMs 在生成过程中常常受到许多因素的干扰，如位置偏差（Zheng et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib296); Wang et al., [2023c](https://arxiv.org/html/2406.01252v2#bib.bib224)），生成高质量的偏好数据仍需进一步探索。随着 LLMs 的持续改进，使用 LLM 减少人工工作将是未来自动对齐模型的关键策略。

#### 5.1.4 奖励模型指导的解码

除了直接从偏好数据中学习外，LLM 的生成可以通过奖励模型提供的标量信号来增强。这使得对齐可以直接在输出中实现，而不是通过重新加权令牌的概率在模型内实现（Mudgal et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib151)）。Lango 和 Dusek ([2023](https://arxiv.org/html/2406.01252v2#bib.bib106)) 提出了一个基于评论驱动的解码方法，通过二元分类器作为评论模型在生成过程中调整令牌的概率。Deng 和 Raffel ([2023](https://arxiv.org/html/2406.01252v2#bib.bib49)) 提出了奖励增强解码（RAD），它使用属性特定的奖励模型在解码时重新加权前 k 个最高概率。为了在不同任务中实现灵活对齐，Liu et al. ([2024b](https://arxiv.org/html/2406.01252v2#bib.bib132)) 提出了解码时重新对齐（DeRa）来控制解码过程中的对齐水平。

仅在解码阶段执行自动对齐是一种简单的方法，可以避免消耗大量计算资源。然而，解码过程中的对齐通常需要更多时间进行推理，响应的质量仍需进一步提高。

#### 5.1.5 使用奖励模型筛选 SFT 数据

高质量的 SFT 在提升 LLM 性能方面发挥着关键作用（Zhou et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib301)）。因此，一些研究使用奖励模型来筛选训练数据。主要的范式被分为从最佳响应学习和从排名结果学习。从最佳响应学习通常被称为 Best of N 或 Reject sampling（Touvron et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib213); Yuan et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib283)）。这种方法通常涉及使用奖励模型从多个响应中选择高质量数据以改进模型（Dong et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib52)）。除了从顶级响应中学习，LLM 还可以从排名数据中学习。Yuan et al.（[2023a](https://arxiv.org/html/2406.01252v2#bib.bib280)）提出了 Rank Responses 以对齐人类反馈（RRHF），通过排名损失对齐 LLM。Lu et al.（[2022](https://arxiv.org/html/2406.01252v2#bib.bib138)）提出使用奖励模型根据评分对数据进行分级，并使用各种奖励令牌来调节生成。这种方法有助于防止学习不良行为。

除了强化学习，SFT 也是实现对齐的重要方式。通过奖励模型筛选数据，LLM 可以通过 SFT 自动对齐人类价值观。与之前的问题类似，SFT 数据的质量高度依赖于奖励模型的质量，需要进一步研究。

### 5.2 二元验证器

对于一些客观任务，例如数学问题，奖励模型通常转变为具有二元信号的验证器。考虑到数学问题通常需要复杂的逐步推理，验证器可以分为结果验证器和过程验证器。结果验证器用于估计最终答案的正确性。过程验证器访问中间步骤，这需要大量的监督数据。通过二元验证器，LLM 可以在这些客观任务上实现自动对齐。

##### 结果验证器

为了提高 LLMs 的推理能力，一些研究集中在使用黄金答案来选择由 LLMs 生成的推理路径进行训练（Zelikman 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib286)；Singh 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib193)）。由于获取黄金答案的成本较高，因此使用结果验证器来预测生成答案的正确性。这种验证器通常使用 LLM 生成的正确和错误推理进行训练（Cobbe 等，[2021](https://arxiv.org/html/2406.01252v2#bib.bib46)），并通过包括直接调优（Liu 等，[2023c](https://arxiv.org/html/2406.01252v2#bib.bib135)）和迭代训练（Hosseini 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib84)）等不同策略来微调 LLM。由于结果验证器无法评估推理步骤的正确性，Havrilla 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib75)）提出了逐步结果奖励模型（SORMs），用于预测某一步是否会导致正确答案。除了训练之外，Yu 等（[2024a](https://arxiv.org/html/2406.01252v2#bib.bib276)）提出了结果监督值模型（OVM），用于指导解码。

##### 过程验证器

即使最终答案是正确的，推理过程仍可能存在错误，这限制了结果验证器的有效性。为了解决这个问题，采用过程验证器来评估推理步骤的正确性，以进行更详细的验证（Lightman 等， [2023](https://arxiv.org/html/2406.01252v2#bib.bib127)；Uesato 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib215)）。过程验证器可以用于训练更有效的推理器（Ying 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib275)；Shao 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib182)）。受人类推理机制的启发，Zhu 等（[2023b](https://arxiv.org/html/2406.01252v2#bib.bib305)）提出了合作推理（CoRe），以生成用于推理的综合训练数据，其中过程验证器用于生成器的反馈。由于收集逐步监督信号的困难，许多研究致力于使用自动生成的数据来训练验证器。Wang 等（[2024e](https://arxiv.org/html/2406.01252v2#bib.bib225)）和 Wang 等（[2024h](https://arxiv.org/html/2406.01252v2#bib.bib235)）通过蒙特卡洛采样收集的自动构建数据训练过程验证器。此外，过程验证器可以应用于解码，以选择正确的推理路径（Khalifa 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib96)）。一些研究集中于如何高效地完成最终的推理路径。Ma 等（[2023b](https://arxiv.org/html/2406.01252v2#bib.bib144)）提出了一种基于验证器反馈的启发式贪心搜索算法。Li 等（[2023c](https://arxiv.org/html/2406.01252v2#bib.bib122)）提出使用验证器过滤通过多样化提示生成的推理步骤。

二元验证器对实现数学等目标任务的自动对齐至关重要。然而，训练验证器，尤其是过程验证器非常困难，并且需要大量的标注数据。因此，未来，为了进一步实现自动对齐，研究人员可以集中于如何自动构建过程验证器。

### 5.3 文本批评

文本信号包含比标量和二元信号更多的语义，使模型能够直观地与人类对齐。通过整合文本反馈，LLMs 可以改善其输出与人类的一致性。这些精炼的输出可以作为监督数据，用于进一步对齐 LLMs（Scheurer et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib178); Chen et al., [2024a](https://arxiv.org/html/2406.01252v2#bib.bib29)）。由批评模型生成的文本信号已经显示出改善 LLM 输出的潜力，反馈通常通过提示 LLMs 来获得。文本批评者可以是其他 LLMs（如 GPT-4）（Koutcheme et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib102); An et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib8)）或 LLM 自身（即自我批评）（Saunders et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib177); Wang et al., [2023d](https://arxiv.org/html/2406.01252v2#bib.bib228)）。由于 LLM 的自我批评仍然是一个挑战（Luo et al., [2023b](https://arxiv.org/html/2406.01252v2#bib.bib141)），对齐的文本信号仍然未被充分探索。

现有研究主要集中于通过改善 LLMs 的输出，利用文本批评者实现自动对齐。未来，探索如何使用文本批评者实现更多样化的自动对齐（例如在训练中）是一个重要的研究方向。

## 6 通过环境反馈进行对齐

> 我们不是从经验中学习……我们是从对经验的反思中学习。
> 
> 约翰·杜威

本节涉及从现有环境中自动获取对齐目标或反馈，以实现目标模型的自动对齐。如图 [8](https://arxiv.org/html/2406.01252v2#S6.F8 "Figure 8 ‣ 6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey") 所示，根据模型与环境的交互类别，本节概述了当前研究的四条线索，并系统地回顾了每部分的代表性工作：

+   •

    社会互动 (§ [6.1](https://arxiv.org/html/2406.01252v2#S6.SS1 "6.1 Social Interactions ‣ 6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))，其中模型之间进行通信，以建立多代理系统，并通过这种互动通信收集对齐信号。

+   •

    人类共享价值 (§ [6.2](https://arxiv.org/html/2406.01252v2#S6.SS2 "6.2 Human Shared-Values ‣ 6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey"))，其中模型接受来自人类社会的判断，以校准其内部价值观。

+   •

    工具执行反馈（§ [6.3](https://arxiv.org/html/2406.01252v2#S6.SS3 "6.3 Tool Execution Feedback ‣ 6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey")），模型与外部工具互动以获得即时反馈，并通过学习聪明地使用工具实现各种智能。

+   •

    体现环境（§ [6.4](https://arxiv.org/html/2406.01252v2#S6.SS4 "6.4 Embodied Environment ‣ 6 Aligning Through Environment Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey")），模型作为物理世界中的语言接口，根据任务目标获得奖励。

![参见标题](img/3aa5d7ae0235d0a558fb54e0bffad5c5.png)

图 8：通过各种类型的环境反馈，如社交互动、人类共享价值观、工具执行的信号或体现的环境，来实现对齐。

### 6.1 社交互动

社交互动是人类社会的基本特征之一，其中许多社会规范以隐性方式传达和遵循。近期大型语言模型的进展提供了构建基于 LLM 的代理系统的机会，以模拟人类社会中的此类互动，从而构建沙箱环境以收集对齐信号，具有更大的可扩展性，并且更接近真实世界（Park et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib165)）。通过模拟的社交互动，如道德讨论，研究提供了增强 AI 系统与人类价值观和伦理原则对齐的有希望的途径。

例如，稳定对齐（Liu et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib131)）从人类如何学习导航社会规范和通过讨论达成对社会问题的价值判断的共识中获得灵感。他们引入了一种基于 LLM 的多智能体框架来模拟人类社会中的社交互动，突出特点是包含模仿、自我批评和重新对齐的三层方法。在模拟过程中，相应地提取对齐数据集。Wang et al. ([2024f](https://arxiv.org/html/2406.01252v2#bib.bib226)) 将这种方法扩展到现实社交场景下的多轮互动。他们提出了一种互动学习方法，通过不同社会角色之间的社交互动来教语言代理达到目标。Pang et al. ([2024](https://arxiv.org/html/2406.01252v2#bib.bib164)) 引入了社交场景模拟，利用 LLM 在相对于指令的场景中扮演不同社会角色，使模型能够考虑指令背后的社会后果，从而相应地修正其初始响应。在类似模拟社交互动的方法基础上，其他工作探讨了道德讨论（Sun et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib201)）、政治辩论（Taubenfeld et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib212)）和任务导向对话（Ulmer et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib216)），其中 AI 系统由一些预定义的讨论模式引导。

### 6.2 人类共享价值观

另一种弥补模拟社交互动的方法涉及依靠人类的集体努力来推导出 AI 应对齐的原则。目前，在这一领域的工作中，对齐信号通常被称为规范（Ammanabrolu et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib7)），经验法则（RoTs）（Forbes et al., [2020](https://arxiv.org/html/2406.01252v2#bib.bib57)；Ziems et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib306)），或宪法（Bai et al., [2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）在不同的上下文中，这些方法相比于传统 NLP 和 RLHF 数据收集中数据点级别的注释提供了更大的可扩展性。在宪法 AI（CAI）（Bai et al., [2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)）中，研究人员设计了一套 AI 宪法。然而，由研究团队成员编制的这些内部宪法不足以广泛代表不同群体的价值观。

为了在群体中达成对人工智能系统应遵循的基本原则的共识，并通过将各种人类思想综合成一组模型对齐的目标来实现人类共享价值，后续工作致力于让更广泛的公众共同塑造人工智能系统的行为。例如，在一个名为**“民主输入到人工智能”**的项目中，发布了关于促进人工智能民主过程的原型系统设计的公开征集。具体而言，该项目旨在使代表性人群能够交流观点，并最终达成人工智能系统应遵循的规则的共识。随后，在**集体宪法人工智能**（CCAI）项目中（Anthropic，[2023](https://arxiv.org/html/2406.01252v2#bib.bib9)；Huang et al.，[2024](https://arxiv.org/html/2406.01252v2#bib.bib88)），研究人员建立了一个多阶段的过程，通过问卷将公众输入整合到语言模型中。通过集体宪法起草的方式，参与者可以评估现有的宪法原则，评分其接受度，并提出他们认为人工智能应更好遵守的新宪法，从而减少对齐大语言模型的偏见。除了这些开创性的研究，大语言模型本身也参与其中，以更高效地从人群中总结共享价值。Klingefjord et al. ([2024](https://arxiv.org/html/2406.01252v2#bib.bib100)) 提出了**道德图谱引导**（MGE）来引导和调和来自人类参与者的价值观，该方法利用语言模型对参与者进行特定背景下的价值观访谈。

### **6.3 工具执行反馈**

工具在扩展大语言模型能力方面至关重要，使它们能够超越基本能力的限制，并更有效地与环境互动。此外，工具执行的准确和详细反馈为大语言模型提供了直接的信号，用于验证和增强其初始输出（Chen et al.，[2023d](https://arxiv.org/html/2406.01252v2#bib.bib36)；Gou et al.，[2024](https://arxiv.org/html/2406.01252v2#bib.bib68)），这有助于减少对人类反馈的依赖。此外，从工具执行反馈中学习规划和使用工具的过程可以得到改进（Wang et al.，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib218)），其中大语言模型对其行为进行反馈，并以互动的方式从成功和失败中学习。

工具的执行反馈可以作为超越人工劳动力语料库的附加信号，以更好地将模型与工具使用对齐，并减少它们在与工具互动时的幻觉。代码生成任务提供了这样的例子。**CodeRL**（Le 等，[2022](https://arxiv.org/html/2406.01252v2#bib.bib107)）通过代码编译器进行单元测试，以接收反馈信号，并利用这些信号训练一个批评模型，进而使用深度强化学习进一步训练代码生成模型。**Self-debugging**（Chen 等，[2023d](https://arxiv.org/html/2406.01252v2#bib.bib36)）设计了一个互动代码调试管道，通过在代码执行反馈旁边添加代码解释阶段，在这些反馈信息下要求 LLMs 调试自身生成的代码。类似地，**SelfEvolve**（Jiang 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib94)）从解释器接收错误消息，并根据此反馈完善答案代码。

除了代码生成，还有研究设计统一框架以将语言模型与来自多个其他来源的执行反馈对齐。**CRITIC**（Gou 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib68)）利用验证-修正过程从各种外部工具中获取反馈，包括搜索引擎、代码解释器和文本 API，从而使语言模型能够通过工具互动批评来修正输出。更进一步，Wang 等人（[2024a](https://arxiv.org/html/2406.01252v2#bib.bib218)）增强了 LLMs 的动态记忆机制，使 LLMs 能够逐步学习如何准确使用工具。Qiao 等人（[2024](https://arxiv.org/html/2406.01252v2#bib.bib169)）提出了带有执行反馈的强化学习，以增强 LLMs 对工具执行结果的理解。

### 6.4 具身环境

具身智能涉及能够感知信号并在某些物理环境中采取行动的代理，这不仅要求语言理解，还需要在具有大量状态的空间中进行推理和决策能力（Roy 等，[2021](https://arxiv.org/html/2406.01252v2#bib.bib176)）。在具身 AI 环境中利用大型语言模型代表了一项引人注目的工作，这可以从两个方面带来好处。一方面，LLM 的强大泛化能力可以用于在无需初步学习的情况下促进自然语言中的行动计划。另一方面，LLM 的常识知识和物理理解能力可以与环境反馈信号对齐。

近期研究显示了大语言模型（LLMs）在机器人技术中用于真实世界交互的潜力，同时也提出了将 LLMs 与物理世界对接的挑战（Wang et al., [2023a](https://arxiv.org/html/2406.01252v2#bib.bib220); Ahn et al., [2022](https://arxiv.org/html/2406.01252v2#bib.bib4)）。为了更好地对齐那些未在具体环境中预训练的语言模型，Xiang et al. ([2023](https://arxiv.org/html/2406.01252v2#bib.bib252)) 采用了一种具象化的模拟器作为世界模型，以在 LLMs 与对象交互并在有任务目标或无任务目标的环境中执行动作时提供反馈信号。然后，探索到的世界状态将被收集为具象经验，随后用于离线微调 LLM。同时，其他研究利用在线强化学习（Carta et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib26); Tan et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib207)）学习或迭代离线学习框架（Song et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib198)）通过试错法更新具象体代理的策略。在孤立环境中对齐专用代理之外，Xi et al. ([2024](https://arxiv.org/html/2406.01252v2#bib.bib251)) 引入了一种名为 AGENTGYM 的新框架，通过促进其在多样环境和任务中的演变，开发具有一般能力的基于 LLM 的代理。

### 6.5 讨论

在这一部分，我们回顾了一些可以从环境反馈对齐的角度统一观察到的当前研究。虽然大多数工作针对特定的下游应用，但从环境中主动学习始终是人工智能中的关键追求。尽管它们做出了宝贵的贡献，当前的方法仍显示出局限性，并为未来的研究留下了未解的问题。其中一个主要的局限性来自于研究中检查的环境信号与现实世界中的信号之间的差距。

一方面，模拟环境可能缺乏完全捕捉现实世界复杂性的表现能力。例如，为了推导用于对齐的社会互动信号，目前的大多数工作都基于模拟环境，而来自现实环境的反馈可能更加嘈杂或模糊。例如，刘等人 ([2023a](https://arxiv.org/html/2406.01252v2#bib.bib131)) 指出，目前的研究通常假设社会规范是静态的，忽视了其动态和演变的特性。同样，对于具身环境的工作，研究通常在沙箱环境中进行，不同的设置是相互独立的。这些模拟环境的行动空间仍然有限 (Tan et al., [2024](https://arxiv.org/html/2406.01252v2#bib.bib207))，与可能具有无限自由度的现实环境相比。因此，在一种设置中训练的模型可能无法很好地推广到其他设置中，确保模型在不同环境中保持对齐仍然是一个挑战。

另一方面，即使与现实世界环境相关联，人类共享价值观的信号仍可能存在偏见。例如，从小型社会群体中采样的价值观可能与普遍认可的价值观差异很大。此外，互联网上的声音不一定能代表现实世界中大多数人的实际价值观，人的认知也容易受到社交媒体的影响。由于与人类共享价值观的对齐仍然是一个新兴领域，目前的大多数工作都是试探性的，并且参与者人数有限，不超过数千人。当规模扩大到数十万人时，当前方法可能面临未曾预料到的挑战。因此，如何以全面而一致的方式将人类价值观注入 AI 系统，以实现尽可能无偏的对齐，仍然是一个未解的问题。

总结来说，将环境反馈融入 AI 对齐的主题开启了一个充满潜力和新兴的方向，但仍然存在需要探索的重大研究问题。未来的研究可以集中于弥合模拟环境与现实环境之间的差距，以开发更具适应性、可靠性和公正性的 AI。

## 自动对齐的潜在机制

如前所述，已有大量研究致力于提高自动对齐方法的效率、有效性和可靠性。尽管如此，关于对齐机制的系统性研究仍明显不足。例如，许多方法（Liu 等，[2024c](https://arxiv.org/html/2406.01252v2#bib.bib133)；Li 等，[2024d](https://arxiv.org/html/2406.01252v2#bib.bib117)；等等）被提出以过滤指令数据，但尚不清楚是否需要特定的过滤标准或过程以及其背后的理由。同样，许多工作提出了各种从弱到强的对齐算法，但我们仍不清楚从弱到强泛化成功的原因及其是否依赖于特定条件。相关研究的缺失可能会妨碍对当前对齐和自动对齐方法的理解，从而阻碍这些方法的进一步优化。

因此，在本节中，我们将对自动对齐的机制进行系统性的研究。通过系统地组织和分析自动对齐的基本机制，我们可以识别当前自动对齐方法的缺点和局限性，并揭示改进方法的设计方向。如前所述，自动对齐的技术繁多。在本次调查中，我们选择了以下三个核心研究问题，这些问题对于实现可扩展的自动对齐至关重要：

+   •

    RQ1: 当前对齐的基本机制是什么？对齐的基本机制是自动对齐研究的基础。了解自动对齐的可行性、边界和优化方向对于自动对齐的研究至关重要。

+   •

    RQ2: 为什么自我反馈有效？自我反馈在各种自动对齐范式中广泛应用，例如在第 [3.1.2](https://arxiv.org/html/2406.01252v2#S3.SS1.SSS2 "3.1.2 H2: LLMs can judge, critic, refine and more ‣ 3.1 Inductive Bias from Features of LLMs ‣ 3 Aligning Through Inductive Bias ‣ Towards Scalable Automated Alignment of LLMs: A Survey") 节中作为归纳偏差，构建第 [5](https://arxiv.org/html/2406.01252v2#S5 "5 Aligning Through Model Feedback ‣ Towards Scalable Automated Alignment of LLMs: A Survey") 节中的偏好学习数据，并作为自动迭代对齐的关键技术（Yuan 等，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)；等等）。理解自我反馈为何有效对于理解和提升涉及自我反馈的所有范式至关重要。

+   •

    RQ3: 为什么从弱到强是可行的？作为实现可扩展监督的一个有前景的方向，理解从弱到强的可行性及其基本机制对于优化和设计更有效的从弱到强的方法至关重要，尤其是在对齐超人类模型时。

对于每个研究问题，我们总结了现有的研究和观点，并讨论了这些分析工作的局限性以及仍需探索的领域。

### 7.1 当前对齐的基础机制是什么？

了解当前对齐的机制对于评估自动对齐的潜力、检查自动对齐面临的关键挑战以及引导当前自动对齐方法的优化方向至关重要。以前的研究（Zhou 等人，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib301)；Ren 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib175)；Mecklenburg 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib148)；等）主要关注对齐机制的两个方面：行为规范转移和知识学习。围绕哪个方面更为关键进行了分析和讨论。

一些研究发现，当前对齐的主要作用是行为规范的转变，而不是额外世界知识的学习。 Zhou 等人 ([2023a](https://arxiv.org/html/2406.01252v2#bib.bib301)) 提出了“表面对齐假设”，即模型的知识和能力几乎完全在预训练期间学习，而对齐则教会它在与用户互动时应使用哪个子分布格式。此外，后续研究采用了三种不同的分析方法，以深入探讨对齐过程中的模型行为。

##### 基于特征的分析

通过比较 LLM 预测令牌的概率分布在对齐前后的变化（DPO&RLHF），Lin 等人 ([2024a](https://arxiv.org/html/2406.01252v2#bib.bib128)) 发现，分布的变化主要发生在风格性令牌上，而知识密集型令牌的分布变化较小，并且随着预测长度的增加，分布变化减少，表明对齐涉及形式上的对齐而非知识注入。同时，Duan 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib53)) 发现 ICL 和 IFT 在 LLM 的隐藏状态中表现出高一致性，而在基础 LLM 的隐藏层状态中表现出低一致性，这表明对齐的作用在于模型从写作延续到回应的行为规范转变。此外，通过使用基于梯度的输入输出归因方法并分析注意力头和前馈层，Wu 等人 ([2023a](https://arxiv.org/html/2406.01252v2#bib.bib249)) 揭示了 IFT 使 LLM 能够识别用户指令组件并据此调整响应，而不改变语言结构。

##### 知识干预

Ren 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib175)）引入了一种知识干预框架，以解耦 IFT 的潜在基础因素，并发现对于 IFT，世界知识与参数知识不一致的学习几乎没有好处，甚至可能造成额外的损害，在所有同质、领域内和领域外的评估中均是如此。此外，Ren 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib175)）发现有效 IFT 的本质在于在完成行为规范转变的同时保持模型参数知识的一致性。Gekhman 等（[2024](https://arxiv.org/html/2406.01252v2#bib.bib65)）也通过观察模型在通过 IFT 引入不同比例新知识时的表现，突出了添加新事实的风险。

##### 实证评估

LIMA（Zhou 等，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib301)）、AlpaGasus（Chen 等，[2023c](https://arxiv.org/html/2406.01252v2#bib.bib32)）和 LTD（Chen 等，[2023b](https://arxiv.org/html/2406.01252v2#bib.bib31)）通过在使用少量指令数据的 IFT 下取得了令人印象深刻的表现，提供了对“表面对齐假说”的实验证据。此外，Gudibande 等（[2023](https://arxiv.org/html/2406.01252v2#bib.bib71)）显示，通过行为模仿进行的对齐可以成功提高 LLM 的风格、角色和遵循指令的能力，但无法提高 LLM 在更复杂维度上的表现，如真实性和问题解决能力。

尽管这些研究得出了类似的结论，但它们未能界定所审查模型所实现的具体对齐情况。在不同程度或需求下对齐的潜在机制差异仍未被探讨。此外，当前研究主要集中在传统的自然语言处理任务和一般对话场景。然而，一些研究（Mecklenburg 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib148)；Singhal 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib194)；等）发现，领域特定的对齐确实可以提高模型在相关领域的表现，这表明对齐在学习额外领域知识中可能发挥着至关重要的作用。在编码和数学等各种场景下，对齐的潜在机制仍然是一个悬而未决的问题。

### 7.2 为什么自反馈有效？

反馈能力指的是根据特定标准对给定输入提供信息或指导的能力。如上所述，这种能力在各种自动化对齐范式中被广泛应用。例如，在 RLAIF 中，LLM 本身替代人类评估来构建偏好数据（Yuan et al., [2024b](https://arxiv.org/html/2406.01252v2#bib.bib282); 等等）。此外，LLM 可以基于自我反馈持续优化其输出，这一过程称为自我精炼（Bai et al., [2022b](https://arxiv.org/html/2406.01252v2#bib.bib16); Madaan et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib145); Tan et al., [2023](https://arxiv.org/html/2406.01252v2#bib.bib208); 等等）。然而，关于 LLM 是否以及为什么能对自己的回应提供有效反馈存在很多争论。接下来，我们将系统总结每个代表性的观点。

Li 等人 ([2024g](https://arxiv.org/html/2406.01252v2#bib.bib121)) 和 Lin 等人 ([2024b](https://arxiv.org/html/2406.01252v2#bib.bib129)) 表明模型拥有某些知识，这些知识无法直接用于生成，但可以用于提供反馈。Li 等人 ([2024g](https://arxiv.org/html/2406.01252v2#bib.bib121)) 还发现 LLM 在生成和验证答案时存在显著的生成器-验证器不一致。类似地，Lin 等人 ([2024b](https://arxiv.org/html/2406.01252v2#bib.bib129)) 发现 LLM 拥有大量无法通过生成和修正表达但可以用于批评的知识。此外，其他研究（Yuan 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)；Li 等人，[2024f](https://arxiv.org/html/2406.01252v2#bib.bib120)）认为反馈能力是模型遵循指令能力的副产品。因此，在对齐过程中，模型的反馈能力会随着其遵循指令能力的提高而提升，这一现象得到了实验证据的支持（Yuan 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib282)；Li 等人，[2024f](https://arxiv.org/html/2406.01252v2#bib.bib120)）。然而，一些其他研究认为 LLM 的反馈能力是虚幻的，暗示它可能依赖特定数据并存在偏见。West 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib241)) 指出，尽管当前的 LLM 通过训练获得了生成专家级输出的能力，但它们缺乏与批评相关的理解能力。此外，Huang 等人 ([2023b](https://arxiv.org/html/2406.01252v2#bib.bib87)) 观察到，对于推理任务，LLM 在自我修正后有时会出现性能下降，因为它们无法正确判断推理的正确性。此外，Zheng 等人 ([2024b](https://arxiv.org/html/2406.01252v2#bib.bib296)) 发现，尽管像 GPT-4 这样的强大 LLM 实现了与人类评估者的高度一致性，类似于人际一致水平，但 LLM 基于的评估面临各种挑战，如位置偏见（Zheng 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib296)；Wang 等人，[2023c](https://arxiv.org/html/2406.01252v2#bib.bib224)），冗长偏见（Zheng 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib296)；Wu 和 Aji，[2023](https://arxiv.org/html/2406.01252v2#bib.bib245)），自我增强偏见（Zheng 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib296)；Liu 等人，[2023b](https://arxiv.org/html/2406.01252v2#bib.bib134)），以及在某些场景下如数学评分、推理问题（Zheng 等人，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib296)），高质量总结（Shen 等人，[2023a](https://arxiv.org/html/2406.01252v2#bib.bib186)）等方面的能力有限（Lan 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib104)）。研究人员提出了许多进一步提高自我反馈能力的方法，如元批评（Sun 等人，[2024a](https://arxiv.org/html/2406.01252v2#bib.bib202)），自动校准（Liu 等人，[2023d](https://arxiv.org/html/2406.01252v2#bib.bib137)），拆分与合并（Li 等人，[2023e](https://arxiv.org/html/2406.01252v2#bib.bib125)）以及使用外部工具（如搜索引擎、代码解释器等）进行交叉检查（Gou 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib68)），从而完善其初始回应等。

讨论 尽管大量工作已致力于探索模型提供自我反馈的能力，但有关其有效性边界和潜在原因的问题仍未解答。此外，模型自我反馈与人类期望之间的差异和合理性也尚未探索。此外，在自我反馈和修正的两步优化模型输出中已经展示了有希望的结果（Bai 等，[2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)；Madaan 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib145)；Tan 等，[2023](https://arxiv.org/html/2406.01252v2#bib.bib208)）。然而，研究主要集中于前者，而后者则大多未被探索。尽管研究人员（Lan 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib104)；Gou 等，[2024](https://arxiv.org/html/2406.01252v2#bib.bib68)）发现 LLM 具有类似于人类的能力，可以根据反馈修改其响应，但基于其生成的反馈进行修正的能力仍未被探索。此外，LLM 的整体性能提升依赖于修正错误响应的数量是否超过修正正确响应的数量。对于何时自我修正可以提升或削弱性能及其潜在原因的全面分析仍然缺乏。

### 7.3 为什么“弱到强”是可行的？

正如我们上面讨论的，一个有前景的可扩展监督方法是“弱到强”的概念，它通过有限或简化的监督培养稳健的能力。虽然对于“弱到强”有一些成功的实际工作，但“弱到强”的潜在机制仍需进一步研究，这限制了“弱到强”的进一步优化和方法设计。目前，普遍的观点是，预训练于大量语料库的 LLM 可以利用其出色的泛化能力，在有限或简化的监督下实现稳健的能力。接下来，我们将介绍这种泛化能力如何使 LLM 通过有限或简化的监督实现自动对齐。

Bai 等人 ([2022b](https://arxiv.org/html/2406.01252v2#bib.bib16))、Sun 等人 ([2023d](https://arxiv.org/html/2406.01252v2#bib.bib205)) 和 Fränken 等人 ([2024](https://arxiv.org/html/2406.01252v2#bib.bib58)) 观察到，仅仅向 LLM 提供核心对齐原则就能使其自动实现显著的对齐效果。这表明模型从原则到行为的泛化能力。例如，Bai 等人 ([2022b](https://arxiv.org/html/2406.01252v2#bib.bib16)) 通过提供原则来提示 LLM 以优化响应，从而完成 IFT 和 RLAIF。Sun 等人 ([2023d](https://arxiv.org/html/2406.01252v2#bib.bib205)) 利用 16 条手动设计的规则来引导基础模型生成高质量指令，然后进行自我蒸馏以实现自我对齐。Chen 等人 ([2024e](https://arxiv.org/html/2406.01252v2#bib.bib37)) 进一步使用更强的 LLM 自动发现这些构成。类似地，Fränken 等人 ([2024](https://arxiv.org/html/2406.01252v2#bib.bib58)) 使用更强的基础模型通过较弱的指令细化模型进行对齐。Burns 等人 ([2023](https://arxiv.org/html/2406.01252v2#bib.bib25)) 发现简单的方法常常能显著提高 LLM 的弱到强的泛化能力：例如，当用 GPT-2 级别的监督和附加的置信度损失对 GPT-4 进行微调时，GPT-4 在 NLP 任务中能接近 GPT-3.5 的表现。这展示了模型从有限监督到更强性能的泛化能力。此外，Sun 等人 ([2024b](https://arxiv.org/html/2406.01252v2#bib.bib206)) 和 Hase 等人 ([2024](https://arxiv.org/html/2406.01252v2#bib.bib74)) 发现，经过简单任务训练的 LLM 能够成功地泛化到困难任务。近期研究还讨论了在理论框架下弱到强泛化的可行性（Somerstep 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib195); Lang 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib105); Charikar 等人，[2024](https://arxiv.org/html/2406.01252v2#bib.bib27)）。

讨论 当前的 LLM 展示了强大的泛化能力。然而，当前 LLM 与早期预训练 LM 之间泛化能力显著差异的根本原因仍待探索。此外，还需要进一步探索泛化的边界，即哪些可以泛化，哪些不能，以及理解其中的根本原因，这对于识别关键挑战和确定对齐及自动对齐的未来研究方向至关重要。

## 8 结论

本调查探索了可扩展自动对齐的各种技术，并将其分为四个主要领域：与归纳偏差对齐、行为模仿、模型反馈和环境反馈。现有研究展示了实现自动对齐的多条途径，主要解决了可扩展监督等关键挑战。尽管有这些进展，但我们在调查当前对齐机制时发现了显著的研究空白，特别是在自我反馈的可靠性和从弱到强的泛化可行性方面。解决这些尚未探索的问题对于推动自动对齐至关重要，使大型语言模型在实际场景中安全有效地应用。未来的研究工作预计将弥合这些空白，确保 LLM 可靠地运行，并与预期的人类价值观保持一致。

此外，在最乐观的预测中，LLM 能力的逐步增强最终可能会导致模型能够独立进行对齐研究，从而提升自身的安全性。例如，超级对齐项目（OpenAI，[2023b](https://arxiv.org/html/2406.01252v2#bib.bib157)）简要概述了一个雄心勃勃的计划，旨在开发一个专注于对齐研究的专家，转移人类从生成对齐研究提案到评估对齐研究提案的认知负担。最新的 LLM 进展（Anthropic，[2024b](https://arxiv.org/html/2406.01252v2#bib.bib11)）显示了它们解决领域特定专家级问题的潜力，正如 GPQA（Rein et al.，[2023](https://arxiv.org/html/2406.01252v2#bib.bib174)）基准测试所证明的那样，模型在某些环境中接近博士生的表现。此外，跨科学学科的 AI 驱动研究的进展，例如自主化学实验代理（Boiko et al.，[2023](https://arxiv.org/html/2406.01252v2#bib.bib19)），展示了 AI 系统如何最终以超过人类能力的速度和彻底性解决对齐问题。

## 参考文献

+   Abdin 等人（2023 年）Marah Abdin、Jyoti Aneja、Sebastien Bubeck、Caio César Teodoro Mendes、Weizhu Chen、Allie Del Giorno、Ronen Eldan、Sivakanth Gopi、Suriya Gunasekar、Mojan Javaheripi、Piero Kauffmann、Yin Tat Lee、Yuanzhi Li、Anh Nguyen、Gustavo de Rosa、Olli Saarikivi、Adil Salim、Shital Shah、Michael Santacroce、Harkirat Singh Behl、Adam Taumann Kalai、Xin Wang、Rachel Ward、Philipp Witte、Cyril Zhang 和 Yi Zhang。《Phi-2：小型语言模型的惊人力量》，2023 年。网址 [`www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models`](https://www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models)。

+   Abdin 等人（2024）Marah Abdin, Sam Ade Jacobs, Ammar Ahmad Awan, Jyoti Aneja, Ahmed Awadallah, Hany Awadalla, Nguyen Bach, Amit Bahree, Arash Bakhtiari, Harkirat Behl, Alon Benhaim, Misha Bilenko, Johan Bjorck, Sébastien Bubeck, Martin Cai, Caio César Teodoro Mendes, Weizhu Chen, Vishrav Chaudhary, Parul Chopra, Allie Del Giorno, Gustavo de Rosa, Matthew Dixon, Ronen Eldan, Dan Iter, Amit Garg, Abhishek Goswami, Suriya Gunasekar, Emman Haider, Junheng Hao, Russell J. Hewett, Jamie Huynh, Mojan Javaheripi, Xin Jin, Piero Kauffmann, Nikos Karampatziakis, Dongwoo Kim, Mahoud Khademi, Lev Kurilenko, James R. Lee, Yin Tat Lee, Yuanzhi Li, Chen Liang, Weishung Liu, Eric Lin, Zeqi Lin, Piyush Madan, Arindam Mitra, Hardik Modi, Anh Nguyen, Brandon Norick, Barun Patra, Daniel Perez-Becker, Thomas Portet, Reid Pryzant, Heyang Qin, Marko Radmilac, Corby Rosset, Sambudha Roy, Olatunji Ruwase, Olli Saarikivi, Amin Saied, Adil Salim, Michael Santacroce, Shital Shah, Ning Shang, Hiteshi Sharma, Xia Song, Masahiro Tanaka, Xin Wang, Rachel Ward, Guanhua Wang, Philipp Witte, Michael Wyatt, Can Xu, Jiahang Xu, Sonali Yadav, Fan Yang, Ziyi Yang, Donghan Yu, Chengruidong Zhang, Cyril Zhang, Jianwen Zhang, Li Lyna Zhang, Yi Zhang, Yue Zhang, Yunan Zhang, 和 Xiren Zhou。Phi-3 技术报告：一个在你手机上本地运行的高能力语言模型，2024 年。

+   Agarwal 等人（2024）Rishabh Agarwal, Avi Singh, Lei M Zhang, Bernd Bohnet, Stephanie Chan, Ankesh Anand, Zaheer Abbas, Azade Nova, John D Co-Reyes, Eric Chu 等人。多样化上下文学习。*ArXiv 预印本*，abs/2404.11018，2024 年。网址 [`arxiv.org/abs/2404.11018`](https://arxiv.org/abs/2404.11018)。

+   Ahn 等人（2022）Michael Ahn, Anthony Brohan, Noah Brown, Yevgen Chebotar, Omar Cortes, Byron David, Chelsea Finn, Chuyuan Fu, Keerthana Gopalakrishnan, Karol Hausman, Alex Herzog, Daniel Ho, Jasmine Hsu, Julian Ibarz, Brian Ichter, Alex Irpan, Eric Jang, Rosario Jauregui Ruano, Kyle Jeffrey, Sally Jesmonth, Nikhil J Joshi, Ryan Julian, Dmitry Kalashnikov, Yuheng Kuang, Kuang-Huei Lee, Sergey Levine, Yao Lu, Linda Luu, Carolina Parada, Peter Pastor, Jornell Quiambao, Kanishka Rao, Jarek Rettinghouse, Diego Reyes, Pierre Sermanet, Nicolas Sievers, Clayton Tan, Alexander Toshev, Vincent Vanhoucke, Fei Xia, Ted Xiao, Peng Xu, Sichun Xu, Mengyuan Yan, 和 Andy Zeng。尽力而为，不要只是口头上说：将语言与机器人功能对接，2022 年。

+   Aksitov 等人（2023）Renat Aksitov, Sobhan Miryoosefi, Zonglin Li, Daliang Li, Sheila Babayan, Kavya Kopparapu, Zachary Fisher, Ruiqi Guo, Sushant Prakash, Pranesh Srinivasan, Manzil Zaheer, Felix Yu, 和 Sanjiv Kumar。休息与反应：多步骤推理 LLM 代理的自我改进，2023 年。

+   Amini 和 Gallinari（2002）Massih-Reza Amini 和 Patrick Gallinari。半监督逻辑回归。在 *ECAI*，第 2 卷，第 11 页，2002 年。

+   Ammanabrolu et al. (2022) Prithviraj Ammanabrolu, Liwei Jiang, Maarten Sap, Hannaneh Hajishirzi 和 Yejin Choi。在互动叙事中对齐社会规范和价值观。载于 *2022 年北美计算语言学协会：人类语言技术会议论文集*，第 5994–6017 页，美国西雅图，2022。计算语言学协会。doi: 10.18653/v1/2022.naacl-main.439。网址 [`aclanthology.org/2022.naacl-main.439`](https://aclanthology.org/2022.naacl-main.439)。

+   An et al. (2024) Shengnan An, Zexiong Ma, Zeqi Lin, Nanning Zheng, Jian-Guang Lou 和 Weizhu Chen。**从错误中学习使 LLM 成为更好的推理者**，2024。

+   Anthropic (2023) Anthropic. **集体宪法 AI**：将语言模型与公众意见对齐，2023。网址 [`www.anthropic.com/news/collective-constitutional-ai-aligning-a-language-model-with-public-input`](https://www.anthropic.com/news/collective-constitutional-ai-aligning-a-language-model-with-public-input)。

+   Anthropic (2024a) Anthropic. **衡量语言模型的说服力**，2024a。网址 [`www.anthropic.com/research/measuring-model-persuasiveness/`](https://www.anthropic.com/research/measuring-model-persuasiveness/)。

+   Anthropic (2024b) Anthropic. **Claude 3.5 诗篇模型卡补充**，2024b。网址 [`www-cdn.anthropic.com/fed9cc193a14b84131812372d8d5857f8f304c52/Model_Card_Claude_3_Addendum.pdf`](https://www-cdn.anthropic.com/fed9cc193a14b84131812372d8d5857f8f304c52/Model_Card_Claude_3_Addendum.pdf)。

+   Anwar et al. (2024) Usman Anwar, Abulhair Saparov, Javier Rando, Daniel Paleka, Miles Turpin, Peter Hase, Ekdeep Singh Lubana, Erik Jenner, Stephen Casper, Oliver Sourbut 等。确保大规模语言模型对齐和安全性的基础挑战。*ArXiv 预印本*，abs/2404.09932，2024。网址 [`arxiv.org/abs/2404.09932`](https://arxiv.org/abs/2404.09932)。

+   Askell et al. (2021) Amanda Askell, Yuntao Bai, Anna Chen, Dawn Drain, Deep Ganguli, Tom Henighan, Andy Jones, Nicholas Joseph, Ben Mann, Nova DasSarma 等。**作为对齐实验室的通用语言助手**。*ArXiv 预印本*，abs/2112.00861，2021。网址 [`arxiv.org/abs/2112.00861`](https://arxiv.org/abs/2112.00861)。

+   Azar et al. (2024) Mohammad Gheshlaghi Azar, Zhaohan Daniel Guo, Bilal Piot, Remi Munos, Mark Rowland, Michal Valko 和 Daniele Calandriello。**理解从人类偏好中学习的通用理论范式**。载于 *国际人工智能与统计会议*，第 4447–4455 页。PMLR，2024。

+   Bai et al. (2022a) Yuntao Bai, Andy Jones, Kamal Ndousse, Amanda Askell, Anna Chen, Nova DasSarma, Dawn Drain, Stanislav Fort, Deep Ganguli, Tom Henighan 等。使用来自人类反馈的强化学习训练一个有帮助且无害的助手。*ArXiv 预印本*，abs/2204.05862，2022a。网址 [`arxiv.org/abs/2204.05862`](https://arxiv.org/abs/2204.05862)。

+   Bai 等人（2022b）Yuntao Bai、Saurav Kadavath、Sandipan Kundu、Amanda Askell、Jackson Kernion、Andy Jones、Anna Chen、Anna Goldie、Azalia Mirhoseini、Cameron McKinnon 等。宪法 AI：来自 AI 反馈的无害性。*ArXiv 预印本*，abs/2212.08073，2022b。网址 [`arxiv.org/abs/2212.08073`](https://arxiv.org/abs/2212.08073)。

+   Bansal 等人（2018）Trapit Bansal、Jakub Pachocki、Szymon Sidor、Ilya Sutskever 和 Igor Mordatch。通过多智能体竞争出现的复杂性。发表于 *第六届国际学习表征会议，ICLR 2018，温哥华，加拿大，2018 年 4 月 30 日 - 5 月 3 日，会议论文集*。OpenReview.net，2018 年。网址 [`openreview.net/forum?id=Sy0GnUxCb`](https://openreview.net/forum?id=Sy0GnUxCb)。

+   Besta 等人（2024）Maciej Besta、Nils Blach、Ales Kubicek、Robert Gerstenberger、Michal Podstawski、Lukas Gianinazzi、Joanna Gajda、Tomasz Lehmann、Hubert Niewiadomski、Piotr Nyczyk 等。思想图：使用大型语言模型解决复杂问题。发表于 *AAAI 人工智能会议论文集*，第 38 卷，第 17682–17690 页，2024 年。

+   Boiko 等人（2023）Daniil A Boiko、Robert MacKnight、Ben Kline 和 Gabe Gomes。使用大型语言模型进行自主化学研究。*自然*，624(7992)：570–578，2023 年。

+   Bousmalis 等人（2023）Konstantinos Bousmalis、Giulia Vezzani、Dushyant Rao、Coline Devin、Alex X. Lee、Maria Bauza、Todor Davchev、Yuxiang Zhou、Agrim Gupta、Akhil Raju、Antoine Laurens、Claudio Fantacci、Valentin Dalibard、Martina Zambelli、Murilo Martins、Rugile Pevceviciute、Michiel Blokzijl、Misha Denil、Nathan Batchelor、Thomas Lampe、Emilio Parisotto、Konrad Żołna、Scott Reed、Sergio Gómez Colmenarejo、Jon Scholz、Abbas Abdolmaleki、Oliver Groth、Jean-Baptiste Regli、Oleg Sushkov、Tom Rothörl、José Enrique Chen、Yusuf Aytar、Dave Barker、Joy Ortiz、Martin Riedmiller、Jost Tobias Springenberg、Raia Hadsell、Francesco Nori 和 Nicolas Heess。Robocat：一个自我改进的通用机器人操作代理，2023 年。

+   Bowman 等人（2022）Samuel R Bowman、Jeeyoon Hyun、Ethan Perez、Edwin Chen、Craig Pettit、Scott Heiner、Kamilė Lukošiūtė、Amanda Askell、Andy Jones、Anna Chen 等。衡量大型语言模型可扩展监督的进展。*ArXiv 预印本*，abs/2211.03540，2022 年。网址 [`arxiv.org/abs/2211.03540`](https://arxiv.org/abs/2211.03540)。

+   Brooks 等人（2024）Tim Brooks、Bill Peebles、Connor Holmes、Will DePue、Yufei Guo、Li Jing、David Schnurr、Joe Taylor、Troy Luhman、Eric Luhman、Clarence Ng、Ricky Wang 和 Aditya Ramesh。视频生成模型作为世界模拟器。2024。网址 [`openai.com/research/video-generation-models-as-world-simulators`](https://openai.com/research/video-generation-models-as-world-simulators)。

+   Brown 等（2020） Tom B. Brown、Benjamin Mann、Nick Ryder、Melanie Subbiah、Jared Kaplan、Prafulla Dhariwal、Arvind Neelakantan、Pranav Shyam、Girish Sastry、Amanda Askell、Sandhini Agarwal、Ariel Herbert-Voss、Gretchen Krueger、Tom Henighan、Rewon Child、Aditya Ramesh、Daniel M. Ziegler、Jeffrey Wu、Clemens Winter、Christopher Hesse、Mark Chen、Eric Sigler、Mateusz Litwin、Scott Gray、Benjamin Chess、Jack Clark、Christopher Berner、Sam McCandlish、Alec Radford、Ilya Sutskever 和 Dario Amodei. 语言模型是少样本学习者。在 Hugo Larochelle、Marc’Aurelio Ranzato、Raia Hadsell、Maria-Florina Balcan 和 Hsuan-Tien Lin 主编的 *神经信息处理系统进展 33：2020 年神经信息处理系统年会，NeurIPS 2020，2020 年 12 月 6-12 日，虚拟* 中，2020。网址 [`proceedings.neurips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html`](https://proceedings.neurips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html)。

+   Brown-Cohen 等（2023） Jonah Brown-Cohen、Geoffrey Irving 和 Georgios Piliouras. 通过双重高效辩论实现可扩展的 AI 安全。*ArXiv 预印本*，abs/2311.14125，2023。网址 [`arxiv.org/abs/2311.14125`](https://arxiv.org/abs/2311.14125)。

+   Burns 等（2023） Collin Burns、Pavel Izmailov、Jan Hendrik Kirchner、Bowen Baker、Leo Gao、Leopold Aschenbrenner、Yining Chen、Adrien Ecoffet、Manas Joglekar、Jan Leike、Ilya Sutskever 和 Jeff Wu. 从弱到强的泛化：通过弱监督引发强能力，2023。网址 [`arxiv.org/abs/2312.09390`](https://arxiv.org/abs/2312.09390)。

+   Carta 等（2023） Thomas Carta、Clément Romac、Thomas Wolf、Sylvain Lamprier、Olivier Sigaud 和 Pierre-Yves Oudeyer. 在交互环境中通过在线强化学习为大型语言模型奠定基础，2023。

+   Charikar 等（2024） Moses Charikar、Chirag Pabbaraju 和 Kirankumar Shiragur. 定量化从弱到强的泛化增益，2024。

+   Chaudhary（2023） Sahil Chaudhary. 代码 alpaca：一种用于代码生成的指令跟随 llama 模型。网址 [`github.com/sahil280114/codealpaca`](https://github.com/sahil280114/codealpaca)，2023。

+   Chen 等（2024a） Angelica Chen、Jérémy Scheurer、Jon Ander Campos、Tomasz Korbak、Jun Shern Chan、Samuel R. Bowman、Kyunghyun Cho 和 Ethan Perez. 从自然语言反馈中学习。*机器学习研究交易*，2024a。ISSN 2835-8856。网址 [`openreview.net/forum?id=xo3hI5MwvU`](https://openreview.net/forum?id=xo3hI5MwvU)。

+   Chen 等（2023a） Baian Chen、Chang Shu、Ehsan Shareghi、Nigel Collier、Karthik Narasimhan 和 Shunyu Yao. Fireact：朝向语言代理的微调，2023a。

+   Chen 等（2023b） Hao Chen、Yiming Zhang、Qi Zhang、Hantao Yang、Xiaomeng Hu、Xuetao Ma、Yifan Yanggong 和 Junbo Zhao. 也许只需要 0.5% 的数据：低训练数据指令调优的初步探索。*arXiv 预印本 arXiv:2305.09246*，2023b。

+   陈等（2023c）力畅·陈、世扬·李、俊·阎、海·王、卡尔帕·古纳拉特纳、维卡斯·亚达夫、郑·唐、维贾伊·斯里尼瓦桑、天一·周、恒·黄和红霞·金。《Alpagasus：用更少的数据训练更好的 Alpaca》，2023c。网址 [`arxiv.org/abs/2307.08701`](https://arxiv.org/abs/2307.08701)。

+   陈等（2024b）舒·陈、新燕·关、耀杰·卢、洪宇·林、冯先培和乐·孙。《Reinstruct：从未标记语料库中构建指令数据》。在*第 62 届计算语言学协会年会论文集*中，2024b。

+   陈等（2024c）维新·陈、道恩·宋和博·李。《Grath：大型语言模型的渐进自真化》，2024c。

+   陈等（2024d）肖杨·陈、彭·赫、洪宇·林、冯先培、天舒·王、博熙·曹、乐·孙和盈飞·孙。《沉默的螺旋：大型语言模型如何扼杀信息检索？—开放域问答案例研究》。*arXiv 预印本 arXiv:2404.10496*，2024d。

+   陈等（2023d）欣云·陈、麦克斯韦·林、纳撒尼尔·施亚利和丹尼·周。《教大型语言模型自我调试》，2023d。

+   陈等（2024e）秀思·陈、洪志·温、斯雷亚希·纳格、陈·罗、青瑜·尹、瑞瑞·李、郑·李和魏·王。《Iteralign：大型语言模型的迭代性宪法对齐》。*ArXiv 预印本*，abs/2403.18341，2024e。网址 [`arxiv.org/abs/2403.18341`](https://arxiv.org/abs/2403.18341)。

+   陈等（2023e）永瑞·陈、海云·姜、新婷·黄、树鸣·石和桂林·齐。《Tegit：通过文本驱动任务设计生成高质量的指令调整数据》，2023e。

+   陈等（2024f）志鹏·陈、昆·周、韦恩·辛·赵、君辰·万、傅征·张、迪·张和季荣·温。《通过最小编辑约束的细粒度强化学习改进大型语言模型》，2024f。

+   陈等（2024g）紫祥·陈、易赫·邓、慧卓·袁、开轩·纪和全全·顾。《自我游戏微调将弱语言模型转变为强语言模型》。*ArXiv 预印本*，abs/2401.01335，2024g。网址 [`arxiv.org/abs/2401.01335`](https://arxiv.org/abs/2401.01335)。

+   程等（2023）彭宇·程、依凡·杨、简·李、永·戴和南·杜。《对抗性偏好优化》。*arXiv 预印本 arXiv:2311.08045*，2023。

+   程等（2024）彭宇·程、天浩·胡、韩·徐、志松·张、永·戴、雷·韩和南·杜。《自我对弈对抗语言游戏增强 LLM 推理》。*ArXiv 预印本*，abs/2404.10642，2024。网址 [`arxiv.org/abs/2404.10642`](https://arxiv.org/abs/2404.10642)。

+   江等（2023）魏林·江、卓瀚·李、紫·林、英·盛、张浩·吴、浩·张、联敏·郑、思远·庄、永浩·庄、约瑟夫·E·冈萨雷斯、伊昂·斯托伊卡和埃里克·P·辛。《Vicuna：一个开源聊天机器人以 90%* chatgpt 质量令 GPT-4 印象深刻》，2023 年。网址 [`lmsys.org/blog/2023-03-30-vicuna/`](https://lmsys.org/blog/2023-03-30-vicuna/)。

+   Christiano 等 (2018) Paul Christiano、Buck Shlegeris 和 Dario Amodei。通过放大弱专家来监督强学习者。*ArXiv 预印本*，abs/1810.08575，2018 年。网址 [`arxiv.org/abs/1810.08575`](https://arxiv.org/abs/1810.08575)。

+   Christiano 等 (2017) Paul F. Christiano、Jan Leike、Tom B. Brown、Miljan Martic、Shane Legg 和 Dario Amodei。从人类偏好中进行深度强化学习。在 Isabelle Guyon、Ulrike von Luxburg、Samy Bengio、Hanna M. Wallach、Rob Fergus、S. V. N. Vishwanathan 和 Roman Garnett 主编的 *神经信息处理系统 30：2017 年神经信息处理系统年会，2017 年 12 月 4-9 日，加州长滩，USA* 中，第 4299–4307 页，2017 年。网址 [`proceedings.neurips.cc/paper/2017/hash/d5e2c0adad503c91f91df240d0cd4e49-Abstract.html`](https://proceedings.neurips.cc/paper/2017/hash/d5e2c0adad503c91f91df240d0cd4e49-Abstract.html)。

+   Cobbe 等 (2021) Karl Cobbe、Vineet Kosaraju、Mohammad Bavarian、Mark Chen、Heewoo Jun、Lukasz Kaiser、Matthias Plappert、Jerry Tworek、Jacob Hilton、Reiichiro Nakano、Christopher Hesse 和 John Schulman。训练验证器解决数学词题，2021 年。

+   Cui 等 (2024) Ganqu Cui、Lifan Yuan、Ning Ding、Guanming Yao、Wei Zhu、Yuan Ni、Guotong Xie、Zhiyuan Liu 和 Maosong Sun。Ultrafeedback：通过高质量反馈提升语言模型，2024 年。网址 [`openreview.net/forum?id=pNkOx3IVWI`](https://openreview.net/forum?id=pNkOx3IVWI)。

+   Dai 等 (2023) Damai Dai、Yutao Sun、Li Dong、Yaru Hao、Shuming Ma、Zhifang Sui 和 Furu Wei。为什么 GPT 能够在上下文中学习？语言模型秘密地作为元优化器执行梯度下降。在 Anna Rogers、Jordan Boyd-Graber 和 Naoaki Okazaki 主编的 *计算语言学协会会议发现：ACL 2023* 中，第 4005–4019 页，多伦多，加拿大，2023 年。计算语言学协会。doi: 10.18653/v1/2023.findings-acl.247。网址 [`aclanthology.org/2023.findings-acl.247`](https://aclanthology.org/2023.findings-acl.247)。

+   Deng 和 Raffel (2023) Haikang Deng 和 Colin Raffel。奖励增强解码：使用单向奖励模型进行高效控制的文本生成。在 Houda Bouamor、Juan Pino 和 Kalika Bali 主编的 *2023 年自然语言处理实证方法会议论文集* 中，第 11781–11791 页，新加坡，2023 年。计算语言学协会。doi: 10.18653/v1/2023.emnlp-main.721。网址 [`aclanthology.org/2023.emnlp-main.721`](https://aclanthology.org/2023.emnlp-main.721)。

+   DiGiovanni 和 Zell (2021) Anthony DiGiovanni 和 Ethan C Zell。强化学习中自我对弈的调查。*ArXiv 预印本*，abs/2107.02850，2021 年。网址 [`arxiv.org/abs/2107.02850`](https://arxiv.org/abs/2107.02850)。

+   丁等人（2023）宁丁、陈雨林、徐博凯、秦宇佳、胡胜丁、刘志远、孙茂松和周博文。通过扩展高质量的指令性对话来增强聊天语言模型。在霍达·布阿莫尔、胡安·皮诺和卡利卡·巴利（编辑），*2023 年自然语言处理实证方法会议论文集*，第 3029–3051 页，新加坡，2023 年。计算语言学协会。doi: 10.18653/v1/2023.emnlp-main.183。网址 [`aclanthology.org/2023.emnlp-main.183`](https://aclanthology.org/2023.emnlp-main.183)。

+   董等人（2023）董汉泽、熊伟、深安书·戈亚尔、张怡涵、周玮妮、潘锐、刁世哲、张纪鹏、邱顺和和张同。RAFT：用于生成基础模型对齐的奖励排名微调。*机器学习研究期刊*，2023 年。ISSN 2835-8856。网址 [`openreview.net/forum?id=m7p5O7zblY`](https://openreview.net/forum?id=m7p5O7zblY)。

+   段等人（2023）段寒瑜、唐怡萱、杨怡、艾哈迈德·阿巴西和卡尔·燕·谭。探索上下文学习与指令调优之间的关系，2023 年。网址 [`arxiv.org/abs/2311.10367`](https://arxiv.org/abs/2311.10367)。

+   弗南德斯等人（2023）帕特里克·弗南德斯、丹尼尔·德意志、玛拉·芬克尔斯坦、帕克·赖利、安德烈·马丁斯、格雷厄姆·纽比、安库什·戈格、乔纳森·克拉克、马克斯·弗雷塔格和奥尔汉·费拉特。错误中的魔鬼：利用大型语言模型进行细粒度机器翻译评估。在菲利普·科恩、巴里·哈多和汤姆·科克米（编辑），*第八届机器翻译会议论文集*，第 1066–1083 页，新加坡，2023 年。计算语言学协会。doi: 10.18653/v1/2023.wmt-1.100。网址 [`aclanthology.org/2023.wmt-1.100`](https://aclanthology.org/2023.wmt-1.100)。

+   费尔南多等人（2023）克里桑莎·费尔南多、迪伦·巴纳斯、亨里克·米哈维斯基、西蒙·奥辛德罗和蒂姆·洛克塔谢尔。Promptbreeder：通过提示进化实现自我参照的自我改进。*ArXiv 预印本*，abs/2309.16797，2023 年。网址 [`arxiv.org/abs/2309.16797`](https://arxiv.org/abs/2309.16797)。

+   费雷拉等人（2023）拉斐尔·EP·费雷拉、李永宰和若昂·RR·多雷亚。使用伪标签提高深度神经网络在动物识别中的性能。*科学报告*，13(1):13875，2023 年。网址 [`doi.org/10.1038/s41598-023-40977-x`](https://doi.org/10.1038/s41598-023-40977-x)。

+   福布斯等人（2020）麦克斯韦·福布斯、珍娜·D·黄、维雷德·施瓦茨、马滕·萨普和叶金·崔。社会化学 101：学习推理社会和道德规范。在*2020 年自然语言处理实证方法会议论文集（EMNLP）*，第 653–670 页，在线，2020 年。计算语言学协会。doi: 10.18653/v1/2020.emnlp-main.48。网址 [`aclanthology.org/2020.emnlp-main.48`](https://aclanthology.org/2020.emnlp-main.48)。

+   Fränken 等人 (2024) Jan-Philipp Fränken、Eric Zelikman、Rafael Rafailov、Kanishk Gandhi、Tobias Gerstenberg 和 Noah D. Goodman。通过互信息进行自监督对齐：学习在没有偏好标签的情况下遵循原则，2024。网址 [`arxiv.org/abs/2404.14313`](https://arxiv.org/abs/2404.14313)。

+   Fu 等人 (2023a) Yao Fu、Hao Peng、Tushar Khot 和 Mirella Lapata。通过自我博弈和来自 AI 反馈的上下文学习改进语言模型的谈判。*ArXiv 预印本*，abs/2305.10142，2023a。网址 [`arxiv.org/abs/2305.10142`](https://arxiv.org/abs/2305.10142)。

+   Fu 等人 (2023b) Yao Fu、Hao Peng、Litu Ou、Ashish Sabharwal 和 Tushar Khot。将较小的语言模型专门化以进行多步骤推理，2023b。

+   Ganguli 等人 (2022) Deep Ganguli、Liane Lovitt、Jackson Kernion、Amanda Askell、Yuntao Bai、Saurav Kadavath、Ben Mann、Ethan Perez、Nicholas Schiefer、Kamal Ndousse 等人。通过红队测试语言模型以减少危害：方法、扩展行为和经验教训。*ArXiv 预印本*，abs/2209.07858，2022。网址 [`arxiv.org/abs/2209.07858`](https://arxiv.org/abs/2209.07858)。

+   Gao 等人 (2023) Leo Gao、John Schulman 和 Jacob Hilton。奖励模型过度优化的扩展规律。见 Andreas Krause、Emma Brunskill、Kyunghyun Cho、Barbara Engelhardt、Sivan Sabato 和 Jonathan Scarlett 主编，*第 40 届国际机器学习大会论文集*，第 202 卷，*机器学习研究论文集*，第 10835–10866 页。PMLR，2023。网址 [`proceedings.mlr.press/v202/gao23h.html`](https://proceedings.mlr.press/v202/gao23h.html)。

+   Gao 等人 (2024) Yang Gao、Dana Alon 和 Donald Metzler。偏好噪声对生成语言模型对齐性能的影响，2024。

+   Garrabrant 和 Demski (2018) Scott Garrabrant 和 Abram Demski。嵌入式代理，2018。网址 [`www.alignmentforum.org/s/Rm6oQRJJmhGCcLvxh/p/i3BTagvt3HbPMx6PN`](https://www.alignmentforum.org/s/Rm6oQRJJmhGCcLvxh/p/i3BTagvt3HbPMx6PN)。

+   Gekhman 等人 (2024) Zorik Gekhman、Gal Yona、Roee Aharoni、Matan Eyal、Amir Feder、Roi Reichart 和 Jonathan Herzig。微调大语言模型以适应新知识是否会促使幻觉的产生？，2024。网址 [`arxiv.org/abs/2405.05904`](https://arxiv.org/abs/2405.05904)。

+   Gim 等人 (2023) In Gim、Guojun Chen、Seung-seob Lee、Nikhil Sarda、Anurag Khandelwal 和 Lin Zhong。提示缓存：低延迟推理的模块化注意力重用。*ArXiv 预印本*，abs/2311.04934，2023。网址 [`arxiv.org/abs/2311.04934`](https://arxiv.org/abs/2311.04934)。

+   Goodfellow 等人 (2014) Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron C. Courville, 和 Yoshua Bengio。生成对抗网络。在 Zoubin Ghahramani, Max Welling, Corinna Cortes, Neil D. Lawrence, 和 Kilian Q. Weinberger 主编的 *Neural Information Processing Systems 27：2014 年神经信息处理系统年度会议，2014 年 12 月 8-13 日，加拿大蒙特利尔*，第 2672–2680 页，2014。网址 [`proceedings.neurips.cc/paper/2014/hash/5ca3e9b122f61f8f06494c97b1afccf3-Abstract.html`](https://proceedings.neurips.cc/paper/2014/hash/5ca3e9b122f61f8f06494c97b1afccf3-Abstract.html)。

+   Gou 等人 (2024) Zhibin Gou, Zhihong Shao, Yeyun Gong, Yelong Shen, Yujiu Yang, Nan Duan, 和 Weizhu Chen。Critic：大型语言模型可以通过工具交互批评进行自我修正，2024。网址 [`arxiv.org/abs/2305.11738`](https://arxiv.org/abs/2305.11738)。

+   Grandvalet 和 Bengio (2004) Yves Grandvalet 和 Yoshua Bengio。通过熵最小化的半监督学习。在 *Neural Information Processing Systems 17 [神经信息处理系统，NIPS 2004，2004 年 12 月 13-18 日，加拿大不列颠哥伦比亚省温哥华]*，第 529–536 页，2004。网址 [`proceedings.neurips.cc/paper/2004/hash/96f2b50b5d3613adf9c27049b2a888c7-Abstract.html`](https://proceedings.neurips.cc/paper/2004/hash/96f2b50b5d3613adf9c27049b2a888c7-Abstract.html)。

+   Gu 等人 (2024) Shangding Gu, Alois Knoll, 和 Ming Jin。通过强化学习教导 LLM 自我改进指令，2024。网址 [`openreview.net/forum?id=wlRp8IdLkN`](https://openreview.net/forum?id=wlRp8IdLkN)。

+   Gudibande 等人 (2023) Arnav Gudibande, Eric Wallace, Charlie Snell, Xinyang Geng, Hao Liu, Pieter Abbeel, Sergey Levine, 和 Dawn Song。模仿专有 LLM 的虚假承诺，2023。网址 [`arxiv.org/abs/2305.15717`](https://arxiv.org/abs/2305.15717)。

+   Guo 等人 (2024a) Shangmin Guo, Biao Zhang, Tianlin Liu, Tianqi Liu, Misha Khalman, Felipe Llinares, Alexandre Rame, Thomas Mesnard, Yao Zhao, Bilal Piot, 等人。来自在线 AI 反馈的直接语言模型对齐。*ArXiv 预印本*，abs/2402.04792，2024a。网址 [`arxiv.org/abs/2402.04792`](https://arxiv.org/abs/2402.04792)。

+   Guo 等人 (2024b) Yiju Guo, Ganqu Cui, Lifan Yuan, Ning Ding, Jiexin Wang, Huimin Chen, Bowen Sun, Ruobing Xie, Jie Zhou, Yankai Lin, Zhiyuan Liu, 和 Maosong Sun。可控偏好优化：迈向可控的多目标对齐，2024b。

+   Hase 等人 (2024) Peter Hase, Mohit Bansal, Peter Clark, 和 Sarah Wiegreffe。简单训练数据在难任务中的非凡有效性，2024。网址 [`arxiv.org/abs/2401.06751`](https://arxiv.org/abs/2401.06751)。

+   Havrilla 等人（2024）Alex Havrilla, Sharath Raparthy, Christoforus Nalmpantis, Jane Dwivedi-Yu, Maksym Zhuravinskyi, Eric Hambro, 和 Roberta Railneau. Glore：何时、何地以及如何通过全球和局部的改进提升 LLM 推理，2024 年。

+   Hazra 和 Anjaria（2022）Tanmoy Hazra 和 Kushal Anjaria. 博弈论在深度学习中的应用：综述。*多媒体工具与应用*，81(6):8963–8994，2022 年。

+   He 等人（2023）Guande He, Peng Cui, Jianfei Chen, Wenbo Hu, 和 Jun Zhu. 在多项选择设置下研究对齐语言模型的不确定性校准。*ArXiv 预印本*，abs/2310.11732，2023 年。URL [`arxiv.org/abs/2310.11732`](https://arxiv.org/abs/2310.11732)。

+   He 等人（2020）Junxian He, Jiatao Gu, Jiajun Shen, 和 Marc’Aurelio Ranzato. 重新审视神经序列生成的自我训练。在*第 8 届学习表征国际会议，ICLR 2020，埃塞俄比亚亚的斯亚贝巴，2020 年 4 月 26-30 日*中。OpenReview.net，2020 年。URL [`openreview.net/forum?id=SJgdnAVKDH`](https://openreview.net/forum?id=SJgdnAVKDH)。

+   Ho 等人（2023）Namgyu Ho, Laura Schmid, 和 Se-Young Yun. 大型语言模型是推理老师。在 Anna Rogers, Jordan Boyd-Graber, 和 Naoaki Okazaki 编辑的*第 61 届计算语言学协会年会会议录（第 1 卷：长篇论文）*中，第 14852–14882 页，加拿大多伦多，2023 年。计算语言学协会。doi: 10.18653/v1/2023.acl-long.830。URL [`aclanthology.org/2023.acl-long.830`](https://aclanthology.org/2023.acl-long.830)。

+   Hoare（1961）Charles Antony Richard Hoare. 算法 64：快速排序。*ACM 通讯*，4(7):321，1961 年。

+   Hong 等人（2023）Jixiang Hong, Quan Tu, Changyu Chen, Xing Gao, Ji Zhang, 和 Rui Yan. Cyclealign：从黑箱 LLM 到白箱模型的迭代蒸馏以实现更好的人工对齐，2023 年。

+   Hong 等人（2024）Ruixin Hong, Hongming Zhang, Xiaoman Pan, Dong Yu, 和 Changshui Zhang. 思维抽象使语言模型成为更好的推理者，2024 年。

+   Honovich 等人（2023）Or Honovich, Thomas Scialom, Omer Levy, 和 Timo Schick. 不自然的指令：用（几乎）不需要人工劳动来调整语言模型。在 Anna Rogers, Jordan Boyd-Graber, 和 Naoaki Okazaki 编辑的*第 61 届计算语言学协会年会会议录（第 1 卷：长篇论文）*中，第 14409–14428 页，加拿大多伦多，2023 年。计算语言学协会。doi: 10.18653/v1/2023.acl-long.806。URL [`aclanthology.org/2023.acl-long.806`](https://aclanthology.org/2023.acl-long.806)。

+   Hosseini 等人（2024）Arian Hosseini, Xingdi Yuan, Nikolay Malkin, Aaron Courville, Alessandro Sordoni, 和 Rishabh Agarwal. V-star：训练自学推理者的验证器，2024 年。

+   Hsieh 等（2023）Cheng-Yu Hsieh, Chun-Liang Li, Chih-kuan Yeh, Hootan Nakhost, Yasuhisa Fujii, Alex Ratner, Ranjay Krishna, Chen-Yu Lee, 和 Tomas Pfister. 分步提炼！用更少的训练数据和更小的模型尺寸超越更大的语言模型。发表于 Anna Rogers, Jordan Boyd-Graber, 和 Naoaki Okazaki 主编的*计算语言学协会会议成果：ACL 2023*，第 8003–8017 页，加拿大多伦多，2023 年。计算语言学协会。doi: 10.18653/v1/2023.findings-acl.507。网址 [`aclanthology.org/2023.findings-acl.507`](https://aclanthology.org/2023.findings-acl.507)。

+   Huang 等（2023a）Jiaxin Huang, Shixiang Shane Gu, Le Hou, Yuexin Wu, Xuezhi Wang, Hongkun Yu, 和 Jiawei Han. 大型语言模型可以自我提升。发表于*2023 年自然语言处理经验方法会议*，2023a 年。网址 [`openreview.net/forum?id=uuUQraD4XX`](https://openreview.net/forum?id=uuUQraD4XX)。

+   Huang 等（2023b）Jie Huang, Xinyun Chen, Swaroop Mishra, Huaixiu Steven Zheng, Adams Wei Yu, Xinying Song, 和 Denny Zhou. 大型语言模型尚无法自我纠正推理，2023b 年。网址 [`arxiv.org/abs/2310.01798`](https://arxiv.org/abs/2310.01798)。

+   Huang 等（2024）Saffron Huang, Divya Siddarth, Liane Lovitt, Thomas I. Liao, Esin Durmus, Alex Tamkin, 和 Deep Ganguli. 集体宪法人工智能：使语言模型与公众输入对齐。发表于*2024 年 ACM 公平性、问责制和透明度会议*，FAccT ’24。ACM，2024 年 6 月。doi: 10.1145/3630106.3658979。网址 [`dx.doi.org/10.1145/3630106.3658979`](http://dx.doi.org/10.1145/3630106.3658979)。

+   Hubinger 等（2024）Evan Hubinger, Carson Denison, Jesse Mu, Mike Lambert, Meg Tong, Monte MacDiarmid, Tamera Lanham, Daniel M Ziegler, Tim Maxwell, Newton Cheng 等人. 潜伏者：训练能够通过安全训练的欺骗性大语言模型。*arXiv 预印本 arXiv:2401.05566*，2024 年。

+   Irving 等（2018）Geoffrey Irving, Paul Christiano, 和 Dario Amodei. 通过辩论进行人工智能安全。*ArXiv 预印本*，abs/1805.00899，2018 年。网址 [`arxiv.org/abs/1805.00899`](https://arxiv.org/abs/1805.00899)。

+   Jacob 等（2024）Athul Paul Jacob, Yikang Shen, Gabriele Farina, 和 Jacob Andreas. 共识游戏：通过平衡搜索生成语言模型。发表于*第十二届国际学习表征会议*，2024 年。网址 [`openreview.net/forum?id=n9xeGcI4Yg`](https://openreview.net/forum?id=n9xeGcI4Yg)。

+   Ji 等（2023）Jiaming Ji, Tianyi Qiu, Boyuan Chen, Borong Zhang, Hantao Lou, Kaile Wang, Yawen Duan, Zhonghao He, Jiayi Zhou, Zhaowei Zhang, Fanzhi Zeng, Kwan Yee Ng, Juntao Dai, Xuehai Pan, Aidan O’Gara, Yingshan Lei, Hua Xu, Brian Tse, Jie Fu, Stephen McAleer, Yaodong Yang, Yizhou Wang, Song-Chun Zhu, Yike Guo, 和 Wen Gao. 人工智能对齐：综合调查，2023 年。网址 [`arxiv.org/abs/2310.19852`](https://arxiv.org/abs/2310.19852)。

+   Ji et al. (2024) Jiaming Ji, Boyuan Chen, Hantao Lou, Donghai Hong, Borong Zhang, Xuehai Pan, Juntao Dai, 和 Yaodong Yang. Aligner: 通过弱到强的校正实现高效对齐，2024 年。

+   Jiang et al. (2023) Shuyang Jiang, Yuhao Wang, 和 Yu Wang. Selfevolve: 通过大型语言模型的代码演变框架，2023 年。

+   Kadavath et al. (2022) Saurav Kadavath, Tom Conerly, Amanda Askell, Tom Henighan, Dawn Drain, Ethan Perez, Nicholas Schiefer, Zac Hatfield-Dodds, Nova DasSarma, Eli Tran-Johnson, 等. 语言模型（大多数情况）知道它们知道什么。 *ArXiv 预印本*, abs/2207.05221, 2022 年。网址 [`arxiv.org/abs/2207.05221`](https://arxiv.org/abs/2207.05221)。

+   Khalifa et al. (2023) Muhammad Khalifa, Lajanugen Logeswaran, Moontae Lee, Honglak Lee, 和 Lu Wang. GRACE: 判别器指导的思维链推理。在 Houda Bouamor, Juan Pino, 和 Kalika Bali 编輯的 *计算语言学协会发现：EMNLP 2023*，第 15299–15328 页，新加坡，2023 年。计算语言学协会。doi: 10.18653/v1/2023.findings-emnlp.1022。网址 [`aclanthology.org/2023.findings-emnlp.1022`](https://aclanthology.org/2023.findings-emnlp.1022)。

+   Khan et al. (2024) Akbir Khan, John Hughes, Dan Valentine, Laura Ruis, Kshitij Sachan, Ansh Radhakrishnan, Edward Grefenstette, Samuel R Bowman, Tim Rocktäschel, 和 Ethan Perez. 与更具说服力的语言模型辩论会产生更真实的答案。 *ArXiv 预印本*, abs/2402.06782, 2024 年。网址 [`arxiv.org/abs/2402.06782`](https://arxiv.org/abs/2402.06782)。

+   Khot et al. (2023) Tushar Khot, Harsh Trivedi, Matthew Finlayson, Yao Fu, Kyle Richardson, Peter Clark, 和 Ashish Sabharwal. 分解提示：解决复杂任务的模块化方法。发表于 *第十一届国际学习表征会议*, 2023 年。网址 [`openreview.net/forum?id=_nGgzQjzaRy`](https://openreview.net/forum?id=_nGgzQjzaRy)。

+   Kim et al. (2023) Sungdong Kim, Sanghwan Bae, Jamin Shin, Soyoung Kang, Donghyun Kwak, Kang Yoo, 和 Minjoon Seo. 通过合成反馈对齐大型语言模型。在 Houda Bouamor, Juan Pino, 和 Kalika Bali 编輯的 *2023 年自然语言处理实证方法会议论文集*，第 13677–13700 页，新加坡，2023 年。计算语言学协会。doi: 10.18653/v1/2023.emnlp-main.844。网址 [`aclanthology.org/2023.emnlp-main.844`](https://aclanthology.org/2023.emnlp-main.844)。

+   Klingefjord et al. (2024) Oliver Klingefjord, Ryan Lowe, 和 Joe Edelman. 什么是人类价值观，我们如何使人工智能与这些价值观对齐？，2024 年。网址 [`arxiv.org/pdf/2404.10636`](https://arxiv.org/pdf/2404.10636)。

+   Kojima et al. (2022) Takeshi Kojima, Shixiang Shane Gu, Machel Reid, Yutaka Matsuo, 和 Yusuke Iwasawa. 大型语言模型是零-shot 推理器。 *神经信息处理系统进展*, 35:22199–22213, 2022 年。

+   Koutcheme 等 (2024) Charles Koutcheme, Nicola Dainese, Sami Sarsa, Arto Hellas, Juho Leinonen 和 Paul Denny. 开源语言模型可以提供反馈: 评估 llms 帮助学生的能力，使用 gpt-4-as-a-judge，2024。

+   Köksal 等 (2024) Abdullatif Köksal, Timo Schick, Anna Korhonen 和 Hinrich Schütze. Longform: 通过反向指令有效的指令调优，2024。

+   Lan 等 (2024) Tian Lan, Wenwei Zhang, Chen Xu, Heyan Huang, Dahua Lin, Kai Chen 和 Xian-ling Mao. Criticbench: 评估大型语言模型作为评论者，2024。网址 [`arxiv.org/abs/2402.13764`](https://arxiv.org/abs/2402.13764)。

+   Lang 等 (2024) Hunter Lang, David Sontag 和 Aravindan Vijayaraghavan. 弱到强的泛化理论分析，2024。

+   Lango 和 Dusek (2023) Mateusz Lango 和 Ondrej Dusek. 通过评论驱动的解码减轻数据到文本生成中的幻觉。在 Houda Bouamor, Juan Pino 和 Kalika Bali 主编的 *2023 年自然语言处理实证方法会议论文集* 中，第 2853–2862 页，新加坡，2023。计算语言学协会。doi: 10.18653/v1/2023.emnlp-main.172。网址 [`aclanthology.org/2023.emnlp-main.172`](https://aclanthology.org/2023.emnlp-main.172)。

+   Le 等 (2022) Hung Le, Yue Wang, Akhilesh Deepak Gotmare, Silvio Savarese 和 Steven C. H. Hoi. Coderl: 通过预训练模型和深度强化学习掌握代码生成，2022。

+   Lee 等 (2013) Dong-Hyun Lee 等. 伪标签: 一种简单高效的深度神经网络半监督学习方法。在 *ICML 表示学习挑战研讨会*，第 3 卷，第 896 页。亚特兰大，2013。

+   Lee 和 Anderson (2001) Frank J Lee 和 John R Anderson. 学习复杂任务是否必须复杂?: 一项关于学习分解的研究。*认知心理学*，42(3):267–316，2001。

+   Lee 等 (2023) Harrison Lee, Samrat Phatale, Hassan Mansoor, Thomas Mesnard, Johan Ferret, Kellie Lu, Colton Bishop, Ethan Hall, Victor Carbune, Abhinav Rastogi 和 Sushant Prakash. Rlaif: 通过人工反馈扩展强化学习，使用 ai 反馈，2023。

+   Lee 等 (2024) Nicholas Lee, Thanakul Wattanawong, Sehoon Kim, Karttikeya Mangalam, Sheng Shen, Gopala Anumanchipali, Michael W. Mahoney, Kurt Keutzer 和 Amir Gholami. Llm2llm: 通过新型迭代数据增强提升 llms，2024。

+   Li 等 (2023a) Chengpeng Li, Zheng Yuan, Hongyi Yuan, Guanting Dong, Keming Lu, Jiancan Wu, Chuanqi Tan, Xiang Wang 和 Chang Zhou. 查询和响应增强无法帮助域外数学推理泛化，2023a。

+   Li 等 (2024a) Dexun Li, Cong Zhang, Kuicai Dong, Derrick Goh Xin Deik, Ruiming Tang 和 Yong Liu. 通过分布式偏好奖励建模对齐众包反馈，2024a。

+   Li 等人 (2023b) Ming Li、Lichang Chen、Jiuhai Chen、Shwai He 和 Tianyi Zhou。Reflection-tuning: Recycling data for better instruction-tuning。在 *NeurIPS 2023 Workshop on Instruction Tuning and Instruction Following*，2023b。URL [`openreview.net/forum?id=xaqoZZqkPU`](https://openreview.net/forum?id=xaqoZZqkPU)。

+   Li 等人 (2024b) Ming Li、Lichang Chen、Jiuhai Chen、Shwai He、Jiuxiang Gu 和 Tianyi Zhou。选择性反射调优：学生选择的数据回收用于 llm 指令调优，2024b。

+   Li 等人 (2024c) Ming Li、Yong Zhang、Shwai He、Zhitao Li、Hongyu Zhao、Jianzong Wang、Ning Cheng 和 Tianyi Zhou。超过滤：从弱到强的数据过滤用于快速指令调优，2024c。

+   Li 等人 (2024d) Ming Li、Yong Zhang、Zhitao Li、Jiuhai Chen、Lichang Chen、Ning Cheng、Jianzong Wang、Tianyi Zhou 和 Jing Xiao。从数量到质量：通过自我引导的数据选择提升 llm 性能，2024d。URL [`arxiv.org/abs/2308.12032`](https://arxiv.org/abs/2308.12032)。

+   Li 等人 (2022) Shiyang Li、Jianshu Chen、Yelong Shen、Zhiyu Chen、Xinlu Zhang、Zekun Li、Hong Wang、Jing Qian、Baolin Peng、Yi Mao、Wenhu Chen 和 Xifeng Yan。来自大型语言模型的解释使小型推理器变得更好，2022。

+   Li 等人 (2024e) Tianle Li、Ge Zhang、Quy Duc Do、Xiang Yue 和 Wenhu Chen。长上下文 llms 在长时间上下文学习中的困境。*arXiv preprint arXiv:2404.02060*，2024e。

+   Li 等人 (2024f) Xian Li、Ping Yu、Chunting Zhou、Timo Schick、Omer Levy、Luke Zettlemoyer、Jason E Weston 和 Mike Lewis。通过指令回译自我对齐。在 *The Twelfth International Conference on Learning Representations*，volume abs/2308.06259，2024f。URL [`openreview.net/forum?id=1oijHJBRsT`](https://openreview.net/forum?id=1oijHJBRsT)。

+   Li 等人 (2024g) Xiang Lisa Li、Vaishnavi Shrivastava、Siyan Li、Tatsunori Hashimoto 和 Percy Liang。Benchmarking and improving generator-validator consistency of language models。在 *The Twelfth International Conference on Learning Representations*，volume abs/2310.01846，2024g。URL [`openreview.net/forum?id=phBS6YpTzC`](https://openreview.net/forum?id=phBS6YpTzC)。

+   Li 等人 (2023c) Yifei Li、Zeqi Lin、Shizhuo Zhang、Qiang Fu、Bei Chen、Jian-Guang Lou 和 Weizhu Chen。通过步态感知验证器提升语言模型的推理能力。在 Anna Rogers、Jordan Boyd-Graber 和 Naoaki Okazaki 主编的 *Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)*，第 5315–5333 页，多伦多，加拿大，2023c。Association for Computational Linguistics。doi: 10.18653/v1/2023.acl-long.291。URL [`aclanthology.org/2023.acl-long.291`](https://aclanthology.org/2023.acl-long.291)。

+   Li 等人 (2023d) Yuanzhi Li、Sébastien Bubeck、Ronen Eldan、Allie Del Giorno、Suriya Gunasekar 和 Yin Tat Lee。教科书就是你所需的 ii：phi-1.5 技术报告，2023d。

+   Li et al. (2024h) Yuhui Li, Fangyun Wei, Jinjing Zhao, Chao Zhang, 和 Hongyang Zhang。RAIN：你的语言模型可以在无需微调的情况下自我对齐。在*第十二届国际学习表征会议*，卷 abs/2309.07124，2024h。网址 [`openreview.net/forum?id=pETSfWMUzy`](https://openreview.net/forum?id=pETSfWMUzy)。

+   Li et al. (2023e) Zongjie Li, Chaozheng Wang, Pingchuan Ma, Daoyuan Wu, Shuai Wang, Cuiyun Gao, 和 Yang Liu。分割与合并：在大型语言模型基础评估者中对齐位置偏差，2023e。网址 [`arxiv.org/abs/2310.01432`](https://arxiv.org/abs/2310.01432)。

+   Liao et al. (2024) Minpeng Liao, Wei Luo, Chengxi Li, Jing Wu, 和 Kai Fan。Mario：使用代码解释器输出的数学推理 – 一个可复现的管道，2024。

+   Lightman et al. (2023) Hunter Lightman, Vineet Kosaraju, Yura Burda, Harri Edwards, Bowen Baker, Teddy Lee, Jan Leike, John Schulman, Ilya Sutskever, 和 Karl Cobbe。逐步验证，2023。

+   Lin et al. (2024a) Bill Yuchen Lin, Abhilasha Ravichander, Ximing Lu, Nouha Dziri, Melanie Sclar, Khyathi Chandu, Chandra Bhagavatula, 和 Yejin Choi。基础 LLMs 的解锁咒语：通过上下文学习重新思考对齐。在*第十二届国际学习表征会议*，卷 abs/2312.01552，2024a。网址 [`openreview.net/forum?id=wxJ0eXwwda`](https://openreview.net/forum?id=wxJ0eXwwda)。

+   Lin et al. (2024b) Zicheng Lin, Zhibin Gou, Tian Liang, Ruilin Luo, Haowei Liu, 和 Yujiu Yang。Criticbench：针对批评性推理的 LLM 基准测试。*ArXiv 预印本*，abs/2402.14809，2024b。网址 [`arxiv.org/abs/2402.14809`](https://arxiv.org/abs/2402.14809)。

+   Liu et al. (2024a) Aiwei Liu, Haoping Bai, Zhiyun Lu, Xiang Kong, Simon Wang, Jiulong Shan, Meng Cao, 和 Lijie Wen。通过自奖励对比提示蒸馏实现直接的大型语言模型对齐，2024a。网址 [`arxiv.org/abs/2402.11907`](https://arxiv.org/abs/2402.11907)。

+   Liu et al. (2023a) Ruibo Liu, Ruixin Yang, Chenyan Jia, Ge Zhang, Denny Zhou, Andrew M. Dai, Diyi Yang, 和 Soroush Vosoughi。基于模拟社交互动训练社会对齐语言模型，2023a。

+   Liu et al. (2024b) Tianlin Liu, Shangmin Guo, Leonardo Bianco, Daniele Calandriello, Quentin Berthet, Felipe Llinares, Jessica Hoffmann, Lucas Dixon, Michal Valko, 和 Mathieu Blondel。解码时的语言模型重新对齐，2024b。

+   Liu et al. (2024c) Wei Liu, Weihao Zeng, Keqing He, Yong Jiang, 和 Junxian He。什么样的数据适合对齐？对指令调优中的自动数据选择进行全面研究。在*第十二届国际学习表征会议*，2024c。网址 [`openreview.net/forum?id=BTKAeLqLMw`](https://openreview.net/forum?id=BTKAeLqLMw)。

+   Liu 等 (2023b) 杨·刘、丹·伊特、宜崇·徐、朔航·王、若辰·徐、成光·朱。《G-eval：使用 GPT-4 进行更好人类对齐的 NLG 评估》，2023b。网址 [`arxiv.org/abs/2303.16634`](https://arxiv.org/abs/2303.16634)。

+   Liu 等 (2023c) 易新·刘、阿维·辛格、C. 丹尼尔·弗里曼、约翰·D·科-雷耶斯、彼得·J·刘。《提升大型语言模型对数学问题的微调》，2023c。

+   Liu 和 Alahi (2024) 岳江·刘、亚历山大·阿拉希。《协同监督学习：通过专家层次混合提升从弱到强的泛化能力》，2024。

+   Liu 等 (2023d) 禹轩·刘、天驰·杨、绍汉·黄、子涵·张、海臻·黄、富如·魏、伟伟·邓、风·孙、琪·张。《校准基于 LLM 的评估器》，2023d。网址 [`arxiv.org/abs/2309.13308`](https://arxiv.org/abs/2309.13308)。

+   Lu 等 (2022) 西明·陆、肖恩·韦莱克、杰克·赫塞尔、李伟·姜、连辉·秦、彼得·韦斯特、普里特维拉杰·阿曼纳布鲁鲁、叶进·崔。《夸克：通过强化反学习进行可控文本生成》，2022。

+   Lu 等 (2024) 子木·陆、奥俊·周、侯兴·任、克·王、伟康·石、俊婷·潘、明杰·詹、洪生·李。《数学天才：通过问题反向翻译生成合成数据，以增强 LLM 的数学推理》，2024。

+   Luo 等 (2023a) 海鹏·罗、庆峰·孙、灿·徐、朴·赵、建广·楼、崇阳·陶、修博·耿、庆伟·林、世锋·陈、董梅·张。《巫师数学：通过强化 evol-instruct 提升大型语言模型的数学推理》，2023a。

+   Luo 等 (2023b) 梁晨·罗、子林·李、银霄·刘、雷·舒、云·朱、晶博·商、雷·孟。《大型语言模型的批评能力》，2023b。

+   Luo 等 (2024) 子阳·罗、灿·徐、朴·赵、庆峰·孙、修博·耿、文祥·胡、崇阳·陶、晶·马、庆伟·林、大欣·姜。《巫师编码器：通过 evol-instruct 增强代码大型语言模型》。在 *第十二届国际学习表征会议* 上，2024。网址 [`openreview.net/forum?id=UnUwSIgK5W`](https://openreview.net/forum?id=UnUwSIgK5W)。

+   Ma 等 (2023a) 程东·马、自然·杨、敏权·高、海·词、俊·高、学海·潘、耀东·杨。《红队游戏：一种红队语言模型的博弈论框架》。*ArXiv 预印本*，abs/2310.00322，2023a。网址 [`arxiv.org/abs/2310.00322`](https://arxiv.org/abs/2310.00322)。

+   Ma 等 (2023b) 钱力·马、浩天·周、廷凯·刘、建博·袁、鹏飞·刘、杨·尤、红霞·杨。《逐步奖励：逐步奖励模型作为推理的导航员》，2023b。

+   Madaan 等（2023）**Aman Madaan**、**Niket Tandon**、**Prakhar Gupta**、**Skyler Hallinan**、**Luyu Gao**、**Sarah Wiegreffe**、**Uri Alon**、**Nouha Dziri**、**Shrimai Prabhumoye**、**Yiming Yang**、**Shashank Gupta**、**Bodhisattwa Prasad Majumder**、**Katherine Hermann**、**Sean Welleck**、**Amir Yazdanbakhsh** 和 **Peter Clark**。《Self-refine：迭代自反馈的精炼》。收录于 *第 37 届神经信息处理系统会议*，第 36 卷，第 46534–46594 页，2023。网址 [`openreview.net/forum?id=S37hOerQLB`](https://openreview.net/forum?id=S37hOerQLB)。

+   Magister 等（2023）**Lucie Charlotte Magister**、**Jonathan Mallinson**、**Jakub Adamek**、**Eric Malmi** 和 **Aliaksei Severyn**。教小型语言模型推理。收录于 **Anna Rogers**、**Jordan Boyd-Graber** 和 **Naoaki Okazaki** 主编的 *第 61 届计算语言学协会年会论文集（第 2 卷：短篇论文）*，第 1773–1781 页，加拿大多伦多，2023。计算语言学协会。doi: 10.18653/v1/2023.acl-short.151。网址 [`aclanthology.org/2023.acl-short.151`](https://aclanthology.org/2023.acl-short.151)。

+   Manakul 等（2023）**Potsawee Manakul**、**Adian Liusie** 和 **Mark Gales**。《SelfCheckGPT：用于生成大型语言模型的零资源黑箱幻觉检测》。收录于 **Houda Bouamor**、**Juan Pino** 和 **Kalika Bali** 主编的 *2023 年自然语言处理实证方法会议论文集*，第 9004–9017 页，新加坡，2023。计算语言学协会。doi: 10.18653/v1/2023.emnlp-main.557。网址 [`aclanthology.org/2023.emnlp-main.557`](https://aclanthology.org/2023.emnlp-main.557)。

+   Mecklenburg 等（2024）**Nick Mecklenburg**、**Yiyou Lin**、**Xiaoxiao Li**、**Daniel Holstein**、**Leonardo Nunes**、**Sara Malvar**、**Bruno Silva**、**Ranveer Chandra**、**Vijay Aski**、**Pavan Kumar Reddy Yannam**、**Tolga Aktas** 和 **Todd Hendry**。通过监督微调将新知识注入大型语言模型，2024。网址 [`arxiv.org/abs/2404.00213`](https://arxiv.org/abs/2404.00213)。

+   Mitchell（1980）**Tom M Mitchell**。学习概括中的偏差需求，1980。

+   Mitra 等（2023）**Arindam Mitra**、**Luciano Del Corro**、**Shweti Mahajan**、**Andres Codas**、**Clarisse Simoes**、**Sahaj Agarwal**、**Xuxi Chen**、**Anastasia Razdaibiedina**、**Erik Jones**、**Kriti Aggarwal**、**Hamid Palangi**、**Guoqing Zheng**、**Corby Rosset**、**Hamed Khanpour** 和 **Ahmed Awadallah**。《Orca 2：教小型语言模型如何推理》，2023。

+   Mudgal 等（2024）**Sidharth Mudgal**、**Jong Lee**、**Harish Ganapathy**、**YaGuang Li**、**Tao Wang**、**Yanping Huang**、**Zhifeng Chen**、**Heng-Tze Cheng**、**Michael Collins**、**Trevor Strohman**、**Jilin Chen**、**Alex Beutel** 和 **Ahmad Beirami**。《从语言模型中进行受控解码》，2024。

+   Mukherjee 等（2023）**Subhabrata Mukherjee**、**Arindam Mitra**、**Ganesh Jawahar**、**Sahaj Agarwal**、**Hamid Palangi** 和 **Ahmed Awadallah**。《Orca：从 GPT-4 的复杂解释轨迹中进行渐进学习》，2023。

+   Nash 等（1950）**John F Nash** 等。《讨价还价问题》，*经济计量学*，18(2)：155–162，1950。

+   Nash et al. (1951) John F Nash 等. 非合作博弈。第 286–295 页，1951 年。

+   Nigam and Ghani (2000) Kamal Nigam 和 Rayid Ghani. 分析共训练的有效性和适用性。载于 *第九届国际信息与知识管理会议论文集*，第 86–93 页，2000 年。

+   OpenAI (2023a) OpenAI. 准备框架（测试版），2023a。网址 [`cdn.openai.com/openai-preparedness-framework-beta.pdf`](https://cdn.openai.com/openai-preparedness-framework-beta.pdf)。

+   OpenAI (2023b) OpenAI. 介绍超对齐，2023b。网址 [`openai.com/index/introducing-superalignment/`](https://openai.com/index/introducing-superalignment/)。

+   OpenAI (2023c) OpenAI. GPT-4 技术报告。*ArXiv 预印本*，abs/2303.08774，2023c。网址 [`arxiv.org/abs/2303.08774`](https://arxiv.org/abs/2303.08774)。

+   Ought (2017) Ought. 分解认知，2017。网址 [`ought.org/research/factored-cognition`](https://ought.org/research/factored-cognition)。

+   Ouyang et al. (2022) Long Ouyang, Jeff Wu, Xu Jiang, Diogo Almeida, Carroll L. Wainwright, Pamela Mishkin, Chong Zhang, Sandhini Agarwal, Katarina Slama, Alex Ray, John Schulman, Jacob Hilton, Fraser Kelton, Luke Miller, Maddie Simens, Amanda Askell, Peter Welinder, Paul Christiano, Jan Leike 和 Ryan Lowe. 训练语言模型以遵循人类反馈的指令，2022。网址 [`arxiv.org/abs/2203.02155`](https://arxiv.org/abs/2203.02155)。

+   Pace et al. (2024) Alizée Pace, Jonathan Mallinson, Eric Malmi, Sebastian Krause 和 Aliaksei Severyn. West-of-n: 为了改进奖励建模的合成偏好生成。*ArXiv 预印本*，abs/2401.12086，2024。网址 [`arxiv.org/abs/2401.12086`](https://arxiv.org/abs/2401.12086)。

+   Padmanabhan et al. (2023) Shankar Padmanabhan, Yasumasa Onoe, Michael JQ Zhang, Greg Durrett 和 Eunsol Choi. 通过蒸馏传播知识更新到语言模型。载于 *第三十七届神经信息处理系统大会*，2023。网址 [`openreview.net/forum?id=DFaGf3O7jf`](https://openreview.net/forum?id=DFaGf3O7jf)。

+   Pan et al. (2023) Alexander Pan, Jun Shern Chan, Andy Zou, Nathaniel Li, Steven Basart, Thomas Woodside, Hanlin Zhang, Scott Emmons 和 Dan Hendrycks. 奖励是否值得？在 Machiavelli 基准中测量奖励与伦理行为之间的权衡。载于 *国际机器学习会议*，第 26837–26867 页。PMLR，2023。

+   Pang et al. (2024) Xianghe Pang, Shuo Tang, Rui Ye, Yuxin Xiong, Bolun Zhang, Yanfeng Wang 和 Siheng Chen. 通过多代理社会模拟实现大型语言模型的自对齐。载于 *ICLR 2024 大型语言模型（LLM）代理研讨会*，2024。网址 [`openreview.net/forum?id=8jUdgJdxTw`](https://openreview.net/forum?id=8jUdgJdxTw)。

+   Park et al. (2023) Joon Sung Park, Joseph C. O’Brien, Carrie J. Cai, Meredith Ringel Morris, Percy Liang 和 Michael S. Bernstein. 生成代理：人类行为的互动仿真，2023。

+   Patil 等（2023）Shishir G. Patil、Tianjun Zhang、Xin Wang 和 Joseph E. Gonzalez. Gorilla: 连接大量 API 的大型语言模型，2023。

+   Peng 等（2023）Baolin Peng、Chunyuan Li、Pengcheng He、Michel Galley 和 Jianfeng Gao. 使用 GPT-4 的指令调优，2023。

+   Polu 和 Sutskever（2020）Stanislas Polu 和 Ilya Sutskever. 用于自动定理证明的生成语言建模。*arXiv 预印本*，abs/2009.03393，2020。网址 [`arxiv.org/abs/2009.03393`](https://arxiv.org/abs/2009.03393)。

+   Qiao 等（2024）Shuofei Qiao、Honghao Gui、Chengfei Lv、Qianghuai Jia、Huajun Chen 和 Ningyu Zhang. 通过执行反馈提升语言模型的工具学习能力，2024。

+   Qin 等（2023）Yujia Qin、Shihao Liang、Yining Ye、Kunlun Zhu、Lan Yan、Yaxi Lu、Yankai Lin、Xin Cong、Xiangru Tang、Bill Qian、Sihan Zhao、Lauren Hong、Runchu Tian、Ruobing Xie、Jie Zhou、Mark Gerstein、Dahai Li、Zhiyuan Liu 和 Maosong Sun. Toolllm: 促进大型语言模型掌握 16000+ 现实世界 API，2023。

+   Rafailov 等（2023）Rafael Rafailov、Archit Sharma、Eric Mitchell、Stefano Ermon、Christopher D. Manning 和 Chelsea Finn. 直接偏好优化：你的语言模型实际上是一个奖励模型，2023。网址 [`arxiv.org/abs/2305.18290`](https://arxiv.org/abs/2305.18290)。

+   Rame 等（2023）Alexandre Rame、Guillaume Couairon、Corentin Dancette、Jean-Baptiste Gaya、Mustafa Shukor、Laure Soulier 和 Matthieu Cord. 奖励的汤：通过在多样化奖励上插值微调权重以实现 Pareto 最优对齐。发表于 *第 37 届神经信息处理系统会议*，2023。网址 [`openreview.net/forum?id=lSbbC2VyCu`](https://openreview.net/forum?id=lSbbC2VyCu)。

+   Ramesh 等（2021）Aditya Ramesh、Mikhail Pavlov、Gabriel Goh、Scott Gray、Chelsea Voss、Alec Radford、Mark Chen 和 Ilya Sutskever. 零-shot 文本到图像生成。发表于 *国际机器学习大会*，第 8821–8831 页。PMLR，2021。

+   Rein 等（2023）David Rein、Betty Li Hou、Asa Cooper Stickland、Jackson Petty、Richard Yuanzhe Pang、Julien Dirani、Julian Michael 和 Samuel R Bowman. Gpqa: 一项研究生级别的 Google-proof 问答基准。*arXiv 预印本 arXiv:2311.12022*，2023。

+   Ren 等（2024）Mengjie Ren、Boxi Cao、Hongyu Lin、Cao Liu、Xianpei Han、Ke Zeng、Guanglu Wan、Xunliang Cai 和 Le Sun. 学习还是自我对齐？重新思考指令微调，2024。网址 [`arxiv.org/abs/2402.18243`](https://arxiv.org/abs/2402.18243)。

+   Roy 等（2021）Nicholas Roy, Ingmar Posner, Tim D. Barfoot, Philippe Beaudoin, Yoshua Bengio, Jeannette Bohg, Oliver Brock, Isabelle Depatie, Dieter Fox, Daniel E. Koditschek, Tomás Lozano-Pérez, Vikash Mansinghka, Christopher J. Pal, Blake A. Richards, Dorsa Sadigh, Stefan Schaal, Gaurav S. Sukhatme, Denis Thérien, Marc Toussaint 和 Michiel van de Panne. 从机器学习到机器人技术：具身智能的挑战与机遇。*ArXiv 预印本*，abs/2110.15245，2021。网址 [`arxiv.org/abs/2110.15245`](https://arxiv.org/abs/2110.15245)。

+   Saunders 等（2022）William Saunders, Catherine Yeh, Jeff Wu, Steven Bills, Long Ouyang, Jonathan Ward 和 Jan Leike. 自我批评模型用于辅助人类评估者。*ArXiv 预印本*，abs/2206.05802，2022。网址 [`arxiv.org/abs/2206.05802`](https://arxiv.org/abs/2206.05802)。

+   Scheurer 等（2022）Jérémy Scheurer, Jon Ander Campos, Jun Shern Chan, Angelica Chen, Kyunghyun Cho 和 Ethan Perez. 使用语言反馈训练语言模型，2022。

+   Schulman 等（2017）John Schulman, Filip Wolski, Prafulla Dhariwal, Alec Radford 和 Oleg Klimov. 近端策略优化算法，2017。

+   Scudder（1965）H. Scudder. 一些自适应模式识别机器的错误概率。*IEEE 信息理论学报*，11(3):363–371，1965。doi: 10.1109/TIT.1965.1053799。

+   Shaikh 等（2024）Omar Shaikh, Michelle Lam, Joey Hejna, Yijia Shao, Michael Bernstein 和 Diyi Yang. 展示，不要告知：使语言模型与展示反馈对齐。*arXiv 预印本 arXiv:2406.00888*，2024。

+   Shao 等（2024）Zhihong Shao, Peiyi Wang, Qihao Zhu, Runxin Xu, Junxiao Song, Mingchuan Zhang, Y. K. Li, Y. Wu 和 Daya Guo. Deepseekmath：推动开放语言模型中的数学推理极限，2024。

+   Shapley（1971）Lloyd S Shapley. 凸游戏的核心。*国际博弈论杂志*，1:11–26，1971。

+   Sharma 等（2024）Archit Sharma, Sedrick Keh, Eric Mitchell, Chelsea Finn, Kushal Arora 和 Thomas Kollar. 对 AI 反馈在对齐大型语言模型中的关键评估。*ArXiv 预印本*，abs/2402.12366，2024。网址 [`arxiv.org/abs/2402.12366`](https://arxiv.org/abs/2402.12366)。

+   Shavit 等（2023）Yonadav Shavit, Sandhini Agarwal, Miles Brundage, Steven Adler, Cullen O’Keefe, Rosie Campbell, Teddy Lee, Pamela Mishkin, Tyna Eloundou, Alan Hickey 等。代理 AI 系统治理实践。2023。

+   Shen 等（2023a）Chenhui Shen, Liying Cheng, Xuan-Phi Nguyen, Yang You 和 Lidong Bing. 大型语言模型尚未达到人类水平的抽象总结评估能力。在 Houda Bouamor, Juan Pino 和 Kalika Bali 主编的 *计算语言学协会发现：EMNLP 2023* 中，页码 4215–4233，新加坡，2023a。计算语言学协会。doi: 10.18653/v1/2023.findings-emnlp.278。网址 [`aclanthology.org/2023.findings-emnlp.278`](https://aclanthology.org/2023.findings-emnlp.278)。

+   Shen 等（2023b）Tianhao Shen、Renren Jin、Yufei Huang、Chuang Liu、Weilong Dong、Zishan Guo、Xinwei Wu、Yan Liu 和 Deyi Xiong。大型语言模型对齐：综述，2023b。网址 [`arxiv.org/abs/2309.15025`](https://arxiv.org/abs/2309.15025)。

+   Shi 等（2023）Freda Shi、Xinyun Chen、Kanishka Misra、Nathan Scales、David Dohan、Ed H Chi、Nathanael Schärli 和 Denny Zhou。大型语言模型容易被无关上下文分散注意力。在《*国际机器学习会议*》，第 31210–31227 页。PMLR，2023 年。

+   Shi 等（2024）Taiwei Shi、Kai Chen 和 Jieyu Zhao。Safer-instruct：利用自动化偏好数据对齐语言模型，2024 年。

+   Shinn 等（2023）Noah Shinn、Federico Cassano、Edward Berman、Ashwin Gopinath、Karthik Narasimhan 和 Shunyu Yao。Reflexion：具备语言强化学习的语言代理，2023 年。

+   Shridhar 等（2023）Kumar Shridhar、Alessandro Stolfo 和 Mrinmaya Sachan。将推理能力提炼到更小的语言模型中。在 Anna Rogers、Jordan Boyd-Graber 和 Naoaki Okazaki 主编的《*计算语言学协会发现：ACL 2023*》，第 7059–7073 页，多伦多，加拿大，2023 年。计算语言学协会。doi: 10.18653/v1/2023.findings-acl.441。网址 [`aclanthology.org/2023.findings-acl.441`](https://aclanthology.org/2023.findings-acl.441)。

+   Silver 等（2018）David Silver、Thomas Hubert、Julian Schrittwieser、Ioannis Antonoglou、Matthew Lai、Arthur Guez、Marc Lanctot、Laurent Sifre、Dharshan Kumaran、Thore Graepel 等。通过自我对弈掌握国际象棋、将棋和围棋的一般强化学习算法。《*科学*》，362（6419）：1140–1144，2018 年。

+   Singh 等（2024）Avi Singh、John D Co-Reyes、Rishabh Agarwal、Ankesh Anand、Piyush Patil、Xavier Garcia、Peter J Liu、James Harrison、Jaehoon Lee、Kelvin Xu、Aaron T Parisi、Abhishek Kumar、Alexander A Alemi、Alex Rizkowsky、Azade Nova、Ben Adlam、Bernd Bohnet、Gamaleldin Fathy Elsayed、Hanie Sedghi、Igor Mordatch、Isabelle Simpson、Izzeddin Gur、Jasper Snoek、Jeffrey Pennington、Jiri Hron、Kathleen Kenealy、Kevin Swersky、Kshiteej Mahajan、Laura A Culp、Lechao Xiao、Maxwell Bileschi、Noah Constant、Roman Novak、Rosanne Liu、Tris Warkentin、Yamini Bansal、Ethan Dyer、Behnam Neyshabur、Jascha Sohl-Dickstein 和 Noah Fiedel。超越人类数据：使用语言模型扩展自我训练以解决问题。《*机器学习研究交易*》，2024 年。ISSN 2835-8856。网址 [`openreview.net/forum?id=lNAyUngGFK`](https://openreview.net/forum?id=lNAyUngGFK)。专家认证。

+   Singhal et al. (2023) Karan Singhal, Tao Tu, Juraj Gottweis, Rory Sayres, Ellery Wulczyn, Le Hou, Kevin Clark, Stephen Pfohl, Heather Cole-Lewis, Darlene Neal, Mike Schaekermann, Amy Wang, Mohamed Amin, Sami Lachgar, Philip Mansfield, Sushant Prakash, Bradley Green, Ewa Dominowska, Blaise Aguera y Arcas, Nenad Tomasev, Yun Liu, Renee Wong, Christopher Semturs, S. Sara Mahdavi, Joelle Barral, Dale Webster, Greg S. Corrado, Yossi Matias, Shekoofeh Azizi, Alan Karthikesalingam, 和 Vivek Natarajan. 《朝着专家级医疗问答目标的大型语言模型》，2023 年. URL [`arxiv.org/abs/2305.09617`](https://arxiv.org/abs/2305.09617).

+   Somerstep et al. (2024) Seamus Somerstep, Felipe Maia Polo, Moulinath Banerjee, Ya’acov Ritov, Mikhail Yurochkin, 和 Yuekai Sun. 《弱到强泛化的统计框架》，2024 年.

+   Song et al. (2023) Feifan Song, Bowen Yu, Minghao Li, Haiyang Yu, Fei Huang, Yongbin Li, 和 Houfeng Wang. 《人类对齐的偏好排序优化》，2023 年. URL [`arxiv.org/abs/2306.17492`](https://arxiv.org/abs/2306.17492).

+   Song et al. (2024a) Feifan Song, Bowen Yu, Hao Lang, Haiyang Yu, Fei Huang, Houfeng Wang, 和 Yongbin Li. 《在人工对齐中的数据多样性扩展》. 在 Nicoletta Calzolari, Min-Yen Kan, Veronique Hoste, Alessandro Lenci, Sakriani Sakti, 和 Nianwen Xue 编辑的 *《2024 年联合国际计算语言学会议、语言资源与评估（LREC-COLING 2024）论文集》* 中，14358–14369 页，意大利都灵，2024a. ELRA 和 ICCL. URL [`aclanthology.org/2024.lrec-main.1251`](https://aclanthology.org/2024.lrec-main.1251).

+   Song et al. (2024b) Yifan Song, Da Yin, Xiang Yue, Jie Huang, Sujian Li, 和 Bill Yuchen Lin. 《试错法：基于探索的轨迹优化用于 LLM 代理》，2024b.

+   Stiennon et al. (2020) Nisan Stiennon, Long Ouyang, Jeffrey Wu, Daniel M. Ziegler, Ryan Lowe, Chelsea Voss, Alec Radford, Dario Amodei, 和 Paul F. Christiano. 《通过人类反馈学习总结》. 在 Hugo Larochelle, Marc’Aurelio Ranzato, Raia Hadsell, Maria-Florina Balcan, 和 Hsuan-Tien Lin 编辑的 *《神经信息处理系统进展 33：2020 年神经信息处理系统年会，NeurIPS 2020，2020 年 12 月 6-12 日，虚拟会议》* 中，2020 年. URL [`proceedings.neurips.cc/paper/2020/hash/1f89885d556929e98d3ef9b86448f951-Abstract.html`](https://proceedings.neurips.cc/paper/2020/hash/1f89885d556929e98d3ef9b86448f951-Abstract.html).

+   StockFish (2023) StockFish. Stockfish - 开源国际象棋引擎，2023 年. [`stockfishchess.org/`](https://stockfishchess.org/).

+   Sun 等（2023a）Hao Sun、Zhexin Zhang、Fei Mi、Yasheng Wang、Wei Liu、Jianwei Cui、Bin Wang、Qun Liu 和 Minlie Huang。《MoralDial：通过道德讨论训练和评估道德对话系统的框架》。在 Anna Rogers、Jordan Boyd-Graber 和 Naoaki Okazaki 主编的*第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*中，页码 2213–2230，加拿大多伦多，2023a。计算语言学协会。doi: 10.18653/v1/2023.acl-long.123。网址 [`aclanthology.org/2023.acl-long.123`](https://aclanthology.org/2023.acl-long.123)。

+   Sun 等（2024a）Shichao Sun、Junlong Li、Weizhe Yuan、Ruifeng Yuan、Wenjie Li 和 Pengfei Liu。《批评的批评》。*ArXiv 预印本*，abs/2401.04518，2024a。网址 [`arxiv.org/abs/2401.04518`](https://arxiv.org/abs/2401.04518)。

+   Sun 等（2023b）Yuchong Sun、Che Liu、Jinwen Huang、Ruihua Song、Fuzheng Zhang、Di Zhang、Zhongyuan Wang 和 Kun Gai。《Parrot：通过学习提问来增强多轮对话模型》，2023b。

+   Sun 等（2023c）Zhiqing Sun、Yikang Shen、Hongxin Zhang、Qinhong Zhou、Zhenfang Chen、David Cox、Yiming Yang 和 Chuang Gan。《Salmon：具有原则遵循奖励模型的自我对齐》，2023c。网址 [`openreview.net/forum?id=xJbsmB8UMx`](https://openreview.net/forum?id=xJbsmB8UMx)。

+   Sun 等（2023d）Zhiqing Sun、Yikang Shen、Qinhong Zhou、Hongxin Zhang、Zhenfang Chen、David Cox、Yiming Yang 和 Chuang Gan。《从头开始的原则驱动语言模型自我对齐，最低人类监督》。在 A. Oh、T. Naumann、A. Globerson、K. Saenko、M. Hardt 和 S. Levine 主编的*神经信息处理系统进展*中，第 36 卷，页码 2511–2565。Curran Associates, Inc.，2023d。网址 [`proceedings.neurips.cc/paper_files/paper/2023/file/0764db1151b936aca59249e2c1386101-Paper-Conference.pdf`](https://proceedings.neurips.cc/paper_files/paper/2023/file/0764db1151b936aca59249e2c1386101-Paper-Conference.pdf)。

+   Sun 等（2024b）Zhiqing Sun、Longhui Yu、Yikang Shen、Weiyang Liu、Yiming Yang、Sean Welleck 和 Chuang Gan。《从易到难的泛化：超越人类监督的可扩展对齐》，2024b。网址 [`arxiv.org/abs/2403.09472`](https://arxiv.org/abs/2403.09472)。

+   Tan 等（2024）Weihao Tan、Wentao Zhang、Shanqi Liu、Longtao Zheng、Xinrun Wang 和 Bo An。《真正的知识来自实践：通过强化学习将大型语言模型与具身环境对齐》，2024 年。

+   Tan 等（2023）**Xiaoyu Tan**, **Shaojie Shi**, **Xihe Qiu**, **Chao Qu**, **Zhenting Qi**, **Yinghui Xu** 和 **Yuan Qi**。自我批评: 使大语言模型与其对有用性、诚实性和无害性的理解一致。见 **Mingxuan Wang** 和 **Imed Zitouni** 主编，*2023 年自然语言处理实证方法会议：工业轨道会议论文集*，第 650–662 页，新加坡，2023 年。计算语言学协会。doi: 10.18653/v1/2023.emnlp-industry.62。网址 [`aclanthology.org/2023.emnlp-industry.62`](https://aclanthology.org/2023.emnlp-industry.62)。

+   Tang 等（2023）**Qiaoyu Tang**, **Ziliang Deng**, **Hongyu Lin**, **Xianpei Han**, **Qiao Liang** 和 **Le Sun**。Toolalpaca: 针对语言模型的广泛工具学习，包含 3000 个模拟案例。*ArXiv 预印本*，abs/2306.05301，2023 年。网址 [`arxiv.org/abs/2306.05301`](https://arxiv.org/abs/2306.05301)。

+   Tao 等（2024）**Zhengwei Tao**, **Ting-En Lin**, **Xiancai Chen**, **Hangyu Li**, **Yuchuan Wu**, **Yongbin Li**, **Zhi Jin**, **Fei Huang**, **Dacheng Tao**, 和 **Jingren Zhou**。关于大语言模型自我进化的调查。*arXiv 预印本 arXiv:2404.14387*，2024 年。

+   Taori 等（2023）**Rohan Taori**, **Ishaan Gulrajani**, **Tianyi Zhang**, **Yann Dubois**, **Xuechen Li**, **Carlos Guestrin**, **Percy Liang** 和 **Tatsunori B. Hashimoto**。斯坦福 alpaca: 一种遵循指令的 llama 模型。网址 [`github.com/tatsu-lab/stanford_alpaca`](https://github.com/tatsu-lab/stanford_alpaca)，2023 年。

+   Taubenfeld 等（2024）**Amir Taubenfeld**, **Yaniv Dover**, **Roi Reichart** 和 **Ariel Goldstein**。大语言模型在辩论模拟中的系统性偏差，2024 年。

+   Touvron 等（2023）**Hugo Touvron**, **Louis Martin**, **Kevin Stone**, **Peter Albert**, **Amjad Almahairi**, **Yasmine Babaei**, **Nikolay Bashlykov**, **Soumya Batra**, **Prajjwal Bhargava**, **Shruti Bhosale** 等人。Llama 2: 开放基础和微调的聊天模型。*ArXiv 预印本*，abs/2307.09288，2023 年。网址 [`arxiv.org/abs/2307.09288`](https://arxiv.org/abs/2307.09288)。

+   Tunstall 等（2023）**Lewis Tunstall**, **Edward Beeching**, **Nathan Lambert**, **Nazneen Rajani**, **Kashif Rasul**, **Younes Belkada**, **Shengyi Huang**, **Leandro von Werra**, **Clémentine Fourrier**, **Nathan Habib**, **Nathan Sarrazin**, **Omar Sanseviero**, **Alexander M. Rush** 和 **Thomas Wolf**。Zephyr: 语言模型对齐的直接蒸馏，2023 年。

+   Uesato 等（2022）**Jonathan Uesato**, **Nate Kushman**, **Ramana Kumar**, **Francis Song**, **Noah Siegel**, **Lisa Wang**, **Antonia Creswell**, **Geoffrey Irving** 和 **Irina Higgins**。通过基于过程和结果的反馈解决数学应用题，2022 年。

+   Ulmer 等（2024）**Dennis Ulmer**, **Elman Mansimov**, **Kaixiang Lin**, **Justin Sun**, **Xibin Gao** 和 **Yi Zhang**。通过自我对话引导基于 LLM 的任务导向对话代理的引导，2024 年。

+   von Oswald et al. (2023) 约翰内斯·冯·奥斯瓦尔德、埃文德·尼克拉松、马克西米连·施莱格尔、小林清人、尼古拉斯·祖切特、尼诺·谢雷、诺兰·米勒、马克·桑德勒、马克斯·弗拉基米罗夫、拉兹万·帕斯卡努等。揭示变换器中的中层优化算法。*ArXiv 预印本*，abs/2309.05858，2023。URL [`arxiv.org/abs/2309.05858`](https://arxiv.org/abs/2309.05858)。

+   Wang et al. (2024a) 王博时、方浩、杰森·艾斯纳、本杰明·范·杜尔梅和苏瑜。想象馆中的 LLMs：通过模拟试错学习工具，2024a。

+   Wang et al. (2024b) 管王、程思杰、詹贤元、李献刚、宋森和刘杨。Openchat：通过混合质量数据推进开源语言模型。在*第十二届国际学习表征会议*，2024b。URL [`openreview.net/forum?id=AOJyfhWYHf`](https://openreview.net/forum?id=AOJyfhWYHf)。

+   Wang et al. (2023a) 关志王、谢玉琪、蒋云帆、阿贾伊·曼德尔卡、肖超伟、朱宇克、范林熙和安尼玛·安南德库马尔。Voyager：一个开放式的具身代理与大语言模型，2023a。

+   Wang et al. (2024c) 王佳豪、张博霖、杜千龙、张佳俊和朱典辉。关于 LLM 指令调优的数据选择综述，2024c。

+   Wang et al. (2024d) 王可、任厚兴、周奥军、卢紫沐、罗四春、施伟康、张仁瑞、宋麟齐、詹名杰和李洪生。Mathcoder：LLMs 中的无缝代码集成以增强数学推理。在*第十二届国际学习表征会议*，2024d。URL [`openreview.net/forum?id=z8TW0ttBPp`](https://openreview.net/forum?id=z8TW0ttBPp)。

+   Wang et al. (2023b) 王磊、徐婉玉、蓝义怀、胡志强、蓝云石、李凯伟和林易鹏。计划-解决提示：通过大语言模型提升零-shot 链式思维推理。在安娜·罗杰斯、乔丹·博伊德-格雷伯和冈崎直明编辑的*第 61 届计算语言学协会年会会议录（第 1 卷：长篇论文）*中，第 2609–2634 页，多伦多，加拿大，2023b。计算语言学协会。doi: 10.18653/v1/2023.acl-long.147。URL [`aclanthology.org/2023.acl-long.147`](https://aclanthology.org/2023.acl-long.147)。

+   Wang et al. (2023c) 王佩怡、李磊、陈亮、蔡泽凡、朱大伟、林炳怀、曹云博、刘琪、刘天宇和隋志芳。大语言模型不是公平的评估者，2023c。URL [`arxiv.org/abs/2305.17926`](https://arxiv.org/abs/2305.17926)。

+   Wang et al. (2024e) 王佩怡、李磊、邵志洪、R. X. 徐、戴大麦、李一飞、陈德力、吴瑜和隋志芳。Math-shepherd：逐步验证和增强 LLMs，无需人工标注，2024e。

+   Wang et al. (2024f) 王瑞怡、余浩飞、张文欣、齐郑阳、马尔滕·萨普、格雷厄姆·纽比格、乔纳坦·比斯克和朱浩。Sotopia-$\pi$：社会智能语言代理的互动学习，2024f。

+   Wang et al. (2021) Shuohang Wang, Yang Liu, Yichong Xu, Chenguang Zhu, and Michael Zeng. 想要减少标注成本？GPT-3 可以帮忙。在 *计算语言学协会会议成果：EMNLP 2021*，第 4195–4205 页，多米尼加共和国蓬塔卡纳，2021。计算语言学协会。doi: 10.18653/v1/2021.findings-emnlp.354。网址 [`aclanthology.org/2021.findings-emnlp.354`](https://aclanthology.org/2021.findings-emnlp.354)。

+   Wang et al. (2023d) Tianlu Wang, Ping Yu, Xiaoqing Ellen Tan, Sean O’Brien, Ramakanth Pasunuru, Jane Dwivedi-Yu, Olga Golovneva, Luke Zettlemoyer, Maryam Fazel-Zarandi, and Asli Celikyilmaz. Shepherd：语言模型生成的评论者，2023d。网址 [`arxiv.org/abs/2308.04592`](https://arxiv.org/abs/2308.04592)。

+   Wang et al. (2024g) Xinpeng Wang, Shitong Duan, Xiaoyuan Yi, Jing Yao, Shanlin Zhou, Zhihua Wei, Peng Zhang, Dongkuan Xu, Maosong Sun, and Xing Xie. 关于本质与前景：大模型对齐方法的调查，2024g。网址 [`arxiv.org/abs/2403.04204`](https://arxiv.org/abs/2403.04204)。

+   Wang and Zhou (2024) Xuezhi Wang and Denny Zhou. 无提示的思维链推理。*ArXiv 预印本*，abs/2402.10200，2024。网址 [`arxiv.org/abs/2402.10200`](https://arxiv.org/abs/2402.10200)。

+   Wang et al. (2023e) Xuezhi Wang, Jason Wei, Dale Schuurmans, Quoc V Le, Ed H. Chi, Sharan Narang, Aakanksha Chowdhery, and Denny Zhou. 自一致性改善语言模型中的思维链推理。在 *第十一届国际学习表征会议*，2023e。网址 [`openreview.net/forum?id=1PL1NIMMrw`](https://openreview.net/forum?id=1PL1NIMMrw)。

+   Wang et al. (2022) Yizhong Wang, Swaroop Mishra, Pegah Alipoormolabashi, Yeganeh Kordi, Amirreza Mirzaei, Atharva Naik, Arjun Ashok, Arut Selvan Dhanasekaran, Anjana Arunkumar, David Stap, Eshaan Pathak, Giannis Karamanolakis, Haizhi Lai, Ishan Purohit, Ishani Mondal, Jacob Anderson, Kirby Kuznia, Krima Doshi, Kuntal Kumar Pal, Maitreya Patel, Mehrad Moradshahi, Mihir Parmar, Mirali Purohit, Neeraj Varshney, Phani Rohitha Kaza, Pulkit Verma, Ravsehaj Singh Puri, Rushang Karia, Savan Doshi, Shailaja Keyur Sampat, Siddhartha Mishra, Sujan Reddy A, Sumanta Patro, Tanay Dixit, and Xudong Shen. 超自然指令：通过声明性指令在 1600+ NLP 任务上的泛化。在 *2022 年自然语言处理经验方法会议论文集*，第 5085–5109 页，阿布扎比，阿联酋，2022。计算语言学协会。网址 [`aclanthology.org/2022.emnlp-main.340`](https://aclanthology.org/2022.emnlp-main.340)。

+   Wang et al. (2023f) Yizhong Wang, Yeganeh Kordi, Swaroop Mishra, Alisa Liu, Noah A. Smith, Daniel Khashabi, 和 Hannaneh Hajishirzi. Self-instruct: 将语言模型与自生成的指令对齐。在 Anna Rogers, Jordan Boyd-Graber, 和 Naoaki Okazaki 主编的 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）* 中，第 13484–13508 页，多伦多，加拿大，2023f。计算语言学协会。doi: 10.18653/v1/2023.acl-long.754。网址 [`aclanthology.org/2023.acl-long.754`](https://aclanthology.org/2023.acl-long.754)。

+   Wang et al. (2023g) Yufei Wang, Wanjun Zhong, Liangyou Li, Fei Mi, Xingshan Zeng, Wenyong Huang, Lifeng Shang, Xin Jiang, 和 Qun Liu. 将大型语言模型与人类对齐：调查，2023g。网址 [`arxiv.org/abs/2307.12966`](https://arxiv.org/abs/2307.12966)。

+   Wang et al. (2024h) Zihan Wang, Yunxuan Li, Yuexin Wu, Liangchen Luo, Le Hou, Hongkun Yu, 和 Jingbo Shang. 通过验证器的多步骤问题解决：基于模型引发的过程监督的实证分析，2024h。

+   Wei et al. (2022) Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Fei Xia, Ed Chi, Quoc V Le, Denny Zhou 等。链式思维提示在大型语言模型中引发推理。*神经信息处理系统进展*，35:24824–24837，2022。

+   Wei et al. (2024) Jerry Wei, Chengrun Yang, Xinying Song, Yifeng Lu, Nathan Hu, Dustin Tran, Daiyi Peng, Ruibo Liu, Da Huang, Cosmo Du 等。大型语言模型中的长篇事实性。*arXiv 预印本 arXiv:2403.18802*，2024。

+   Wei et al. (2023) Yuxiang Wei, Zhe Wang, Jiawei Liu, Yifeng Ding, 和 Lingming Zhang. Magicoder: 你只需源代码，2023。

+   Wen et al. (2024) Jiaxin Wen, Ruiqi Zhong, Pei Ke, Zhihong Shao, Hongning Wang, 和 Minlie Huang. 学习任务分解以协助人类进行竞赛编程。*arXiv 预印本 arXiv:2406.04604*，2024。

+   Weng et al. (2023) Yixuan Weng, Minjun Zhu, Fei Xia, Bin Li, Shizhu He, Shengping Liu, Bin Sun, Kang Liu, 和 Jun Zhao. 大型语言模型在自我验证下表现更好的推理能力。在 Houda Bouamor, Juan Pino, 和 Kalika Bali 主编的 *计算语言学协会会议论文集：EMNLP 2023* 中，第 2550–2575 页，新加坡，2023 年。计算语言学协会。doi: 10.18653/v1/2023.findings-emnlp.167。网址 [`aclanthology.org/2023.findings-emnlp.167`](https://aclanthology.org/2023.findings-emnlp.167)。

+   West et al. (2023) Peter West, Ximing Lu, Nouha Dziri, Faeze Brahman, Linjie Li, Jena D. Hwang, Liwei Jiang, Jillian Fisher, Abhilasha Ravichander, Khyathi Chandu, Benjamin Newman, Pang Wei Koh, Allyson Ettinger, 和 Yejin Choi. 生成性人工智能悖论：“它可以创造的，可能不一定理解”，2023。网址 [`arxiv.org/abs/2311.00059`](https://arxiv.org/abs/2311.00059)。

+   Weyssow 等人（2024）Martin Weyssow, Aton Kamanda, 和 Houari Sahraoui。Codeultrafeedback：一个 llm-as-a-judge 数据集，用于将大型语言模型与编码偏好对齐，2024。

+   Wilf（2002）Herbert S Wilf。*算法与复杂性*。AK Peters/CRC 出版社，2002。

+   Wu 等人（2021a）Jeff Wu, Long Ouyang, Daniel M Ziegler, Nisan Stiennon, Ryan Lowe, Jan Leike, 和 Paul Christiano。利用人类反馈递归总结书籍。*ArXiv 预印本*，abs/2109.10862，2021a。网址 [`arxiv.org/abs/2109.10862`](https://arxiv.org/abs/2109.10862)。

+   Wu 和 Aji（2023）Minghao Wu 和 Alham Fikri Aji。重形式而非内容：大型语言模型的评估偏差，2023。网址 [`arxiv.org/abs/2307.03025`](https://arxiv.org/abs/2307.03025)。

+   Wu 等人（2024a）Minghao Wu, Abdul Waheed, Chiyu Zhang, Muhammad Abdul-Mageed, 和 Alham Aji。LaMini-LM：来自大规模指令的多样化精炼模型群。见于 Yvette Graham 和 Matthew Purver 主编，*第 18 届欧洲计算语言学协会会议论文集（第 1 卷：长篇论文）*，第 944–964 页，马耳他圣朱利安，2024a。计算语言学协会。网址 [`aclanthology.org/2024.eacl-long.57`](https://aclanthology.org/2024.eacl-long.57)。

+   Wu 等人（2021b）Qingyang Wu, Lei Li, 和 Zhou Yu。Textgail：用于文本生成的生成对抗模仿学习。见于 *第三十五届人工智能 AAAI 会议，AAAI 2021，第三十三届人工智能创新应用会议，IAAI 2021，第十一届人工智能教育进展研讨会，EAAI 2021，虚拟活动，2021 年 2 月 2-9 日*，第 14067–14075 页。AAAI 出版社，2021b。网址 [`ojs.aaai.org/index.php/AAAI/article/view/17656`](https://ojs.aaai.org/index.php/AAAI/article/view/17656)。

+   Wu 等人（2024b）Ting Wu, Xuefeng Li, 和 Pengfei Liu。进步还是退步？训练后自我改善的逆转。见于 *AI for Math Workshop @ ICML 2024*，2024b。网址 [`openreview.net/forum?id=MG18DR2dAN`](https://openreview.net/forum?id=MG18DR2dAN)。

+   Wu 等人（2023a）Xuansheng Wu, Wenlin Yao, Jianshu Chen, Xiaoman Pan, Xiaoyang Wang, Ninghao Liu, 和 Dong Yu。从语言建模到指令跟随：理解指令调整后 llm 的行为转变，2023a。网址 [`arxiv.org/abs/2310.00492`](https://arxiv.org/abs/2310.00492)。

+   Wu 等人（2023b）Zeqiu Wu, Yushi Hu, Weijia Shi, Nouha Dziri, Alane Suhr, Prithviraj Ammanabrolu, Noah A. Smith, Mari Ostendorf, 和 Hannaneh Hajishirzi。精细化的人类反馈为语言模型训练提供了更好的奖励。见于 *第三十七届神经信息处理系统会议*，2023b。网址 [`openreview.net/forum?id=CSbGXyCswu`](https://openreview.net/forum?id=CSbGXyCswu)。

+   Xi 等（2024）席智恒、丁一文、陈文翔、洪博洋、郭红林、王俊哲、杨丁文、廖晨阳、郭欣、何伟、高松洋、陈璐、郑睿、邹一城、桂涛、张琦、裘希鹏、黄轩静、吴祖轩和姜宇刚。Agentgym：在多样环境中进化的大型语言模型基础代理。*ArXiv 预印本*，abs/2406.04151，2024。网址 [`arxiv.org/abs/2406.04151`](https://arxiv.org/abs/2406.04151)。

+   Xiang 等（2023）向建南、陶天华、顾忆、舒天敏、王梓锐、杨子超和胡志婷。语言模型遇见世界模型：体现经验提升语言模型，2023。

+   Xie 等（2023）谢玉溪、川口健二、赵怡然、赵旭、甘敏彦、何俊贤和谢奇哲。自我评估引导的 beam search 用于推理。发表于*第三十七届神经信息处理系统会议*，2023 年。网址 [`openreview.net/forum?id=Bw82hwg5Q3`](https://openreview.net/forum?id=Bw82hwg5Q3)。

+   Xu 等（2023a）徐灿、孙庆锋、郑凯、耿修博、赵浦、冯佳展、陶崇阳和蒋大欣。Wizardlm：赋能大型语言模型以遵循复杂指令。*ArXiv 预印本*，abs/2304.12244，2023a。网址 [`arxiv.org/abs/2304.12244`](https://arxiv.org/abs/2304.12244)。

+   Xu 等（2024a）徐灿、孙庆锋、郑凯、耿修博、赵浦、冯佳展、陶崇阳、林庆伟和蒋大欣。WizardLM：赋能大型预训练语言模型以遵循复杂指令。发表于*第十二届国际学习表示会议*，2024a。网址 [`openreview.net/forum?id=CfXh93NDgH`](https://openreview.net/forum?id=CfXh93NDgH)。

+   Xu 等（2023b）徐灿文、郭达亚、段楠和朱利安·麦考利。Baize：一个开放源代码的聊天模型，通过自聊数据进行参数高效调优。在 Houda Bouamor、Juan Pino 和 Kalika Bali 主编的*2023 年自然语言处理实证方法会议论文集*中，第 6268-6278 页，新加坡，2023b。计算语言学协会。doi: 10.18653/v1/2023.emnlp-main.385。网址 [`aclanthology.org/2023.emnlp-main.385`](https://aclanthology.org/2023.emnlp-main.385)。

+   Xu 等（2023c）徐春璞、陈思菲、陈以涵、张歌、王泽坤、刘瑞博、李晶、傅杰和刘鹏飞。即时对齐：将聊天机器人行为适配于既定规范。*ArXiv 预印本*，abs/2312.15907，2023c。网址 [`arxiv.org/abs/2312.15907`](https://arxiv.org/abs/2312.15907)。

+   Xu 等（2024b）徐杰、张汉博、李兴航、刘化平、蓝旭光和孔涛。Sinvig：一个自我进化的互动视觉代理，用于人机交互，2024b。

+   Xu 等（2024c）徐晓涵、李明、陶崇阳、申涛、郑锐、李金阳、徐灿、陶大成和周天奕。关于大型语言模型知识蒸馏的综述，2024c。

+   Xue et al. (2023) Fuzhao Xue, Yao Fu, Wangchunshu Zhou, Zangwei Zheng, 和 Yang You. 要重复还是不重复: 从标度下的 token 危机中获得的见解。在 A. Oh, T. Neumann, A. Globerson, K. Saenko, M. Hardt, 和 S. Levine 主编的 *神经信息处理系统进展* 第 36 卷，第 59304–59322 页。Curran Associates, Inc.，2023。网址 [`proceedings.neurips.cc/paper_files/paper/2023/file/b9e472cd579c83e2f6aa3459f46aac28-Paper-Conference.pdf`](https://proceedings.neurips.cc/paper_files/paper/2023/file/b9e472cd579c83e2f6aa3459f46aac28-Paper-Conference.pdf)。

+   Yang et al. (2023a) Chengrun Yang, Xuezhi Wang, Yifeng Lu, Hanxiao Liu, Quoc V Le, Denny Zhou, 和 Xinyun Chen. 大语言模型作为优化器。*ArXiv 预印本*，abs/2309.03409，2023a。网址 [`arxiv.org/abs/2309.03409`](https://arxiv.org/abs/2309.03409)。

+   Yang et al. (2024a) Kailai Yang, Zhiwei Liu, Qianqian Xie, Tianlin Zhang, Nirui Song, Jimin Huang, Ziyan Kuang, 和 Sophia Ananiadou. Metaaligner: 条件性弱到强的校正用于语言模型的可泛化多目标对齐，2024a。

+   Yang et al. (2024b) Kevin Yang, Dan Klein, Asli Celikyilmaz, Nanyun Peng, 和 Yuandong Tian. RLCD: 从对比蒸馏中进行的强化学习以实现语言模型对齐。在 *第十二届国际学习表征会议*，2024b。网址 [`openreview.net/forum?id=v3XXtxWKi6`](https://openreview.net/forum?id=v3XXtxWKi6)。

+   Yang et al. (2023b) Rui Yang, Lin Song, Yanwei Li, Sijie Zhao, Yixiao Ge, Xiu Li, 和 Ying Shan. Gpt4tools: 通过自我指令教大语言模型使用工具。在 A. Oh, T. Neumann, A. Globerson, K. Saenko, M. Hardt, 和 S. Levine 主编的 *神经信息处理系统进展* 第 36 卷，第 71995–72007 页。Curran Associates, Inc.，2023b。网址 [`proceedings.neurips.cc/paper_files/paper/2023/file/e393677793767624f2821cec8bdd02f1-Paper-Conference.pdf`](https://proceedings.neurips.cc/paper_files/paper/2023/file/e393677793767624f2821cec8bdd02f1-Paper-Conference.pdf)。

+   Yang et al. (2024c) Rui Yang, Xiaoman Pan, Feng Luo, Shuang Qiu, Han Zhong, Dong Yu, 和 Jianshu Chen. 奖励-情境: 使用动态偏好调整的基础模型多目标对齐，2024c。

+   Yang et al. (2024d) Wenkai Yang, Shiqi Shen, Guangyao Shen, Zhi Gong, 和 Yankai Lin. Super(ficial)-alignment: 强大的模型可能会在弱到强的泛化中欺骗弱模型，2024d。

+   Yang and Wang (2020) Yaodong Yang 和 Jun Wang. 从博弈理论视角概述多智能体强化学习。*ArXiv 预印本*，abs/2011.00583，2020。网址 [`arxiv.org/abs/2011.00583`](https://arxiv.org/abs/2011.00583)。

+   Yang et al. (2024e) Zonghan Yang, Peng Li, Ming Yan, Ji Zhang, Fei Huang, 和 Yang Liu. React meets actre: 当语言代理享受训练数据自主权时，2024e。

+   Yang et al. (2024f) 宗汉·杨、安·刘、子俊·刘、凯明·刘、方舟·熊、一乐·王、泽源·杨、庆远·胡、欣瑞·陈、振赫·张等。朝向代理、人类和环境之间的统一对齐。*ArXiv 预印本*，abs/2402.07744，2024f。网址 [`arxiv.org/abs/2402.07744`](https://arxiv.org/abs/2402.07744)。

+   Yao et al. (2023a) 靖·姚、小元·易、细婷·王、金东·王和兴·谢。从指令到内在的人类价值——大模型对齐目标的调查，2023a。网址 [`arxiv.org/abs/2308.12014`](https://arxiv.org/abs/2308.12014)。

+   Yao et al. (2022) 顺宇·姚、杰弗里·赵、点·余、南·杜、伊扎克·沙夫兰、卡尔蒂克·R·纳拉辛汉和袁·曹。React：在语言模型中协同推理与行动。发表于*第十一届国际学习表示会议*，2022。

+   Yao et al. (2023b) 顺宇·姚、点·余、杰弗里·赵、伊扎克·沙夫兰、托马斯·L·格里菲斯、袁·曹和卡尔蒂克·R·纳拉辛汉。思维树：利用大型语言模型进行深思熟虑的问题解决。发表于*第 37 届神经信息处理系统会议*，2023b。网址 [`openreview.net/forum?id=5Xc1ecxO1h`](https://openreview.net/forum?id=5Xc1ecxO1h)。

+   Yao et al. (2021) 元·姚、浩熙·钟、征言·张、旭·韩、小志·王、凯·张、超俊·肖、国洋·曾、志远·刘和毛松·孙。用于高级自然语言智能的对抗性语言游戏。发表于*第 35 届美国人工智能协会会议，AAAI 2021，第 33 届创新人工智能应用会议，IAAI 2021，第十一届人工智能教育进展研讨会，EAAI 2021，虚拟会议，2021 年 2 月 2-9 日*，第 14248–14256 页。AAAI 出版社，2021。网址 [`ojs.aaai.org/index.php/AAAI/article/view/17676`](https://ojs.aaai.org/index.php/AAAI/article/view/17676)。

+   Yin et al. (2023) 大·尹、小·刘、范·尹、明·钟、赫里提克·班萨尔、家伟·韩和凯-伟·张。Dynosaur：一种用于指令调优数据策划的动态增长范式。发表于 Houda Bouamor、Juan Pino 和 Kalika Bali 编，《2023 年自然语言处理实证方法会议论文集》，第 4031–4047 页，新加坡，2023。计算语言学协会。doi: 10.18653/v1/2023.emnlp-main.245。网址 [`aclanthology.org/2023.emnlp-main.245`](https://aclanthology.org/2023.emnlp-main.245)。

+   Ying et al. (2024) 怀远·英、硕·张、林扬·李、哲建·周、云凡·邵、朝晔·费、一川·马、家伟·洪、奎坤·刘、子逸·王、宇东·王、子健·吴、帅斌·李、风哲·周、宏伟·刘、松杨·张、文伟·张、杭·颜、西鹏·邱、佳宇·王、凯·陈和大华·林。Internlm-math：面向可验证推理的开放数学大语言模型，2024。

+   Yu et al. (2024a) 飞·余、安宁哲·高和本友·王。Ovm：数学推理中的结果监督价值模型，2024a。

+   Yu 等 (2024b) Longhui Yu, Weisen Jiang, Han Shi, Jincheng YU, Zhengying Liu, Yu Zhang, James Kwok, Zhenguo Li, Adrian Weller 和 Weiyang Liu. Metamath: 为大型语言模型创建自己的数学问题。收录在*第十二届国际学习表示会议*上，2024b，链接 [`openreview.net/forum?id=N8N0hgNDRt`](https://openreview.net/forum?id=N8N0hgNDRt)。

+   Yu 等 (2023) Yue Yu, Yuchen Zhuang, Jieyu Zhang, Yu Meng, Alexander J Ratner, Ranjay Krishna, Jiaming Shen 和 Chao Zhang. 大型语言模型作为属性训练数据生成器：多样性和偏见的故事。在 A. Oh, T. Neumann, A. Globerson, K. Saenko, M. Hardt 和 S. Levine，编辑，*神经信息处理系统进展*，第 36 卷，第 55734–55784 页，Curran Associates，Inc.，2023，链接 [`proceedings.neurips.cc/paper_files/paper/2023/file/ae9500c4f5607caf2eff033c67daa9d7-Paper-Datasets_and_Benchmarks.pdf`](https://proceedings.neurips.cc/paper_files/paper/2023/file/ae9500c4f5607caf2eff033c67daa9d7-Paper-Datasets_and_Benchmarks.pdf)。

+   Yu 等 (2024c) Zhaojian Yu, Xin Zhang, Ning Shang, Yangyu Huang, Can Xu, Yishujie Zhao, Wenxiang Hu 和 Qiufeng Yin. Wavecoder: 通过精化数据生成进行广泛和多功能的增强指令调整，2024c。

+   Yuan 等 (2023a) Hongyi Yuan, Zheng Yuan, Chuanqi Tan, Wei Wang, Songfang Huang 和 Fei Huang. RRHF: 将响应排名与人类反馈与语言模型对齐。收录在*第三十七届神经信息处理系统会议*上，2023a，链接 [`openreview.net/forum?id=EdIGMCHk4l`](https://openreview.net/forum?id=EdIGMCHk4l)。

+   Yuan 等 (2024a) Lifan Yuan, Ganqu Cui, Hanbin Wang, Ning Ding, Xingyao Wang, Jia Deng, Boji Shan, Huimin Chen, Ruobing Xie, Yankai Lin, Zhenghao Liu, Bowen Zhou, Hao Peng, Zhiyuan Liu 和 Maosong Sun. 通过偏好树推进大型语言模型推理通才，2024a，链接 [`arxiv.org/abs/2404.02078`](https://arxiv.org/abs/2404.02078)。

+   Yuan 等 (2024b) Weizhe Yuan, Richard Yuanzhe Pang, Kyunghyun Cho, Sainbayar Sukhbaatar, Jing Xu 和 Jason Weston. 自奖励语言模型。*ArXiv preprint*，abs/2401.10020，2024b，链接 [`arxiv.org/abs/2401.10020`](https://arxiv.org/abs/2401.10020)。

+   Yuan 等 (2023b) Zheng Yuan, Hongyi Yuan, Chengpeng Li, Guanting Dong, Keming Lu, Chuanqi Tan, Chang Zhou 和 Jingren Zhou. 大型语言模型学习数学推理的规模关系，2023b。

+   Yue 等 (2024a) Xiang Yue, Xingwei Qu, Ge Zhang, Yao Fu, Wenhao Huang, Huan Sun, Yu Su 和 Wenhu Chen. MAmmoTH: 通过混合指令调整构建数学通才模型。收录在*第十二届国际学习表示会议*上，2024a，链接 [`openreview.net/forum?id=yLClGs770I`](https://openreview.net/forum?id=yLClGs770I)。

+   Yue et al. (2024b) Xiang Yue, Tuney Zheng, Ge Zhang, 和 Wenhu Chen. Mammoth2: 扩展来自网络的指令。 *ArXiv 预印本*，abs/2405.03548，2024b。网址 [`arxiv.org/abs/2405.03548`](https://arxiv.org/abs/2405.03548)。

+   Zelikman et al. (2022) Eric Zelikman, Yuhuai Wu, Jesse Mu, 和 Noah Goodman. Star: 通过推理引导推理。在 S. Koyejo, S. Mohamed, A. Agarwal, D. Belgrave, K. Cho, 和 A. Oh 编辑的 *神经信息处理系统进展*，第 35 卷，第 15476–15488 页。Curran Associates, Inc.，2022。网址 [`proceedings.neurips.cc/paper_files/paper/2022/file/639a9a172c044fbb64175b5fad42e9a5-Paper-Conference.pdf`](https://proceedings.neurips.cc/paper_files/paper/2022/file/639a9a172c044fbb64175b5fad42e9a5-Paper-Conference.pdf)。

+   Zelikman et al. (2024) Eric Zelikman, Georges Harik, Yijia Shao, Varuna Jayasiri, Nick Haber, 和 Noah D Goodman. Quiet-star: 语言模型可以自我学习在发言前思考。 *ArXiv 预印本*，abs/2403.09629，2024。网址 [`arxiv.org/abs/2403.09629`](https://arxiv.org/abs/2403.09629)。

+   Zeng et al. (2023) Aohan Zeng, Mingdao Liu, Rui Lu, Bowen Wang, Xiao Liu, Yuxiao Dong, 和 Jie Tang. Agenttuning: 为大型语言模型启用通用的智能体能力，2023。

+   Zeng et al. (2024a) Dun Zeng, Yong Dai, Pengyu Cheng, Longyue Wang, Tianhao Hu, Wanshun Chen, Nan Du, 和 Zenglin Xu. 关于大型语言模型对齐的多样化偏好，2024a。

+   Zeng et al. (2024b) Weihao Zeng, Can Xu, Yingxiu Zhao, Jian-Guang Lou, 和 Weizhu Chen. 针对大型语言模型的自动指令演化，2024b。

+   Zhang and Parkes (2023) Hugh Zhang 和 David Parkes. 思维链推理是一种策略改进操作符。在 *NeurIPS 2023 指令调优与跟随研讨会*，2023。网址 [`openreview.net/forum?id=bH64KCBzqS`](https://openreview.net/forum?id=bH64KCBzqS)。

+   Zhang (2023) Jiawei Zhang. Graph-toolformer: 通过 ChatGPT 增强的提示赋予大型语言模型图形推理能力，2023。

+   Zhang et al. (2024) Mozhi Zhang, Mianqiu Huang, Rundong Shi, Linsen Guo, Chong Peng, Peng Yan, Yaqian Zhou, 和 Xipeng Qiu. 通过引导忠实度来校准大型语言模型的信心。 *ArXiv 预印本*，abs/2404.02655，2024。网址 [`arxiv.org/abs/2404.02655`](https://arxiv.org/abs/2404.02655)。

+   Zhang et al. (2016) Yizhe Zhang, Zhe Gan, 和 Lawrence Carin. 通过对抗训练生成文本。在 *NIPS 对抗训练研讨会*，第 21 卷，第 21–32 页。Academia.edu，2016。

+   Zheng et al. (2024a) Chujie Zheng, Ziqi Wang, Heng Ji, Minlie Huang, 和 Nanyun Peng. 弱到强的外推加速了对齐，2024a。

+   Zheng et al. (2024b) Lianmin Zheng、Wei-Lin Chiang、Ying Sheng、Siyuan Zhuang、Zhanghao Wu、Yonghao Zhuang、Zi Lin、Zhuohan Li、Dacheng Li、Eric Xing 等。通过 MT-bench 和聊天机器人竞技场评判 LLM 作为裁判的能力。*神经信息处理系统进展*，36:46595–46623，2024b。网址 [`proceedings.neurips.cc/paper_files/paper/2023/hash/91f18a1287b398d378ef22505bf41832-Abstract-Datasets_and_Benchmarks.html`](https://proceedings.neurips.cc/paper_files/paper/2023/hash/91f18a1287b398d378ef22505bf41832-Abstract-Datasets_and_Benchmarks.html)。

+   Zheng et al. (2023) Rui Zheng、Shihan Dou、Songyang Gao、Yuan Hua、Wei Shen、Binghai Wang、Yan Liu、Senjie Jin、Qin Liu、Yuhao Zhou、Limao Xiong、Lu Chen、Zhiheng Xi、Nuo Xu、Wenbin Lai、Minghao Zhu、Cheng Chang、Zhangyue Yin、Rongxiang Weng、Wensen Cheng、Haoran Huang、Tianxiang Sun、Hang Yan、Tao Gui、Qi Zhang、Xipeng Qiu 和 Xuanjing Huang。大型语言模型中的 RLHF 秘密第一部分：PPO，2023。

+   Zheng et al. (2024c) Rui Zheng、Hongyi Guo、Zhihan Liu、Xiaoying Zhang、Yuanshun Yao、Xiaojun Xu、Zhaoran Wang、Zhiheng Xi、Tao Gui、Qi Zhang 等。通过双人游戏实现最优的 LLM 对齐。*arXiv 预印本 arXiv:2406.10977*，2024c。

+   Zheng et al. (2024d) Tianyu Zheng、Ge Zhang、Tianhao Shen、Xueling Liu、Bill Yuchen Lin、Jie Fu、Wenhu Chen 和 Xiang Yue。Opencodeinterpreter：将代码生成与执行和优化集成，2024d。

+   Zhong et al. (2024) Yifan Zhong、Chengdong Ma、Xiaoyuan Zhang、Ziran Yang、Haojun Chen、Qingfu Zhang、Siyuan Qi 和 Yaodong Yang。Panacea：通过偏好适应实现 LLM 的 Pareto 对齐，2024。

+   Zhou et al. (2023a) Chunting Zhou、Pengfei Liu、Puxin Xu、Srinivasan Iyer、Jiao Sun、Yuning Mao、Xuezhe Ma、Avia Efrat、Ping Yu、LILI YU、Susan Zhang、Gargi Ghosh、Mike Lewis、Luke Zettlemoyer 和 Omer Levy。Lima：少即是多的对齐方法。在 A. Oh、T. Neumann、A. Globerson、K. Saenko、M. Hardt 和 S. Levine 编辑的*神经信息处理系统进展*，第 36 卷，页面 55006–55021。Curran Associates, Inc.，2023a。网址 [`proceedings.neurips.cc/paper_files/paper/2023/file/ac662d74829e4407ce1d126477f4a03a-Paper-Conference.pdf`](https://proceedings.neurips.cc/paper_files/paper/2023/file/ac662d74829e4407ce1d126477f4a03a-Paper-Conference.pdf)。

+   Zhou et al. (2023b) Denny Zhou、Nathanael Schärli、Le Hou、Jason Wei、Nathan Scales、Xuezhi Wang、Dale Schuurmans、Claire Cui、Olivier Bousquet、Quoc V Le 和 Ed H. Chi。最少到最多的提示使大型语言模型能够进行复杂推理。发表于*第十一届国际学习表征会议*，2023b。网址 [`openreview.net/forum?id=WZH7099tgfM`](https://openreview.net/forum?id=WZH7099tgfM)。

+   Zhou et al. (2024) Kun Zhou、Beichen Zhang、Jiapeng Wang、Zhipeng Chen、Wayne Xin Zhao、Jing Sha、Zhichao Sheng、Shijin Wang 和 Ji-Rong Wen。Jiuzhang3.0：通过训练小数据合成模型高效提升数学推理，2024。

+   Zhu et al. (2023a) Banghua Zhu, Michael Jordan, 和 Jiantao Jiao. 基于人类反馈的原则性强化学习，通过成对或 k-组比较。收录于 Andreas Krause, Emma Brunskill, Kyunghyun Cho, Barbara Engelhardt, Sivan Sabato 和 Jonathan Scarlett 主编的*第 40 届国际机器学习会议论文集*，第 202 卷的*机器学习研究论文集*，第 43037–43067 页。PMLR，2023a。网址 [`proceedings.mlr.press/v202/zhu23f.html`](https://proceedings.mlr.press/v202/zhu23f.html)。

+   Zhu et al. (2023b) Xinyu Zhu, Junjie Wang, Lin Zhang, Yuxiang Zhang, Yongfeng Huang, Ruyi Gan, Jiaxing Zhang 和 Yujiu Yang. 通过合作推理生成的语言模型解决数学文字题。收录于 Anna Rogers, Jordan Boyd-Graber 和 Naoaki Okazaki 主编的*第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 4471–4485 页，加拿大多伦多，2023b。计算语言学协会。doi: 10.18653/v1/2023.acl-long.245。网址 [`aclanthology.org/2023.acl-long.245`](https://aclanthology.org/2023.acl-long.245)。

+   Ziems et al. (2022) Caleb Ziems, Jane Yu, Yi-Chia Wang, Alon Halevy 和 Diyi Yang. 道德完整性语料库：伦理对话系统的基准。收录于*第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 3755–3773 页，爱尔兰都柏林，2022。计算语言学协会。doi: 10.18653/v1/2022.acl-long.261。网址 [`aclanthology.org/2022.acl-long.261`](https://aclanthology.org/2022.acl-long.261)。

生成于 2024 年 7 月 17 日 星期三 03:27:13，通过 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
