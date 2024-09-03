<!--yml

category: 未分类

date: 2024-09-03 17:28:51

-->

# 何时 LLMs 实际上能纠正自己的错误？LLMs 的自纠正的关键调查

> 来源：[`arxiv.org/html/2406.01297`](https://arxiv.org/html/2406.01297)

1.  [1 简介](https://arxiv.org/html/2406.01297v2#S1 "在 LLM 何时能够实际纠正自己的错误？LLM 的自纠正的关键调查")

1.  [2 LLM 的自纠正](https://arxiv.org/html/2406.01297v2#S2 "在 LLM 何时能够实际纠正自己的错误？LLM 的自纠正的关键调查")

    1.  [2.1 框架](https://arxiv.org/html/2406.01297v2#S2.SS1 "In 2 Self-Correction of LLMs ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")

        1.  [显式反馈对直接改进的影响.](https://arxiv.org/html/2406.01297v2#S2.SS1.SSS0.Px1 "In 2.1 Frameworks ‣ 2 Self-Correction of LLMs ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")

        1.  [后期 vs. 生成时间。](https://arxiv.org/html/2406.01297v2#S2.SS1.SSS0.Px2 "在 2.1 框架 ‣ 2 LLM 的自纠正 ‣ LLM 何时能够实际纠正自己的错误？LLM 的自纠正的关键调查")

        1.  同模型 vs. 跨模型

    1.  [2.2 反馈来源](https://arxiv.org/html/2406.01297v2#S2.SS2 "在 2 LLM 的自纠正 ‣ LLM 何时能够实际纠正自己的错误？LLM 的自纠正的关键调查")

        1.  [内在（§4）。](https://arxiv.org/html/2406.01297v2#S2.SS2.SSS0.Px1 "在 2.2 反馈来源 ‣ 2 LLM 的自纠正 ‣ LLM 何时能够实际纠正自己的错误？LLM 的自纠正的关键调查")

        1.  [外部信息（§5.1）。](https://arxiv.org/html/2406.01297v2#S2.SS2.SSS0.Px2 "在 2.2 反馈来源 ‣ 2 LLM 的自纠正 ‣ LLM 何时能够实际纠正自己的错误？LLM 的自纠正的关键调查")

        1.  [微调（§5.2）。](https://arxiv.org/html/2406.01297v2#S2.SS2.SSS0.Px3 "在 2.2 反馈来源 ‣ 2 LLM 的自纠正 ‣ LLM 何时能够实际纠正自己的错误？LLM 的自纠正的关键调查")

    1.  [2.3 任务](https://arxiv.org/html/2406.01297v2#S2.SS3 "In 2 Self-Correction of LLMs ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")

    1.  [2.4 与相关方法的差异](https://arxiv.org/html/2406.01297v2#S2.SS4 "In 2 Self-Correction of LLMs ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")

1.  [3 研究问题](https://arxiv.org/html/2406.01297v2#S3 "In When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")

    1.  [3.1 自我纠正研究中的 RQs](https://arxiv.org/html/2406.01297v2#S3.SS1 "在 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

        1.  [验证 RQs 的要求。](https://arxiv.org/html/2406.01297v2#S3.SS1.SSS0.Px1 "在 3.1 自我纠正研究中的 RQs ‣ 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

        1.  [先前工作的困惑。](https://arxiv.org/html/2406.01297v2#S3.SS1.SSS0.Px2 "在 3.1 自我纠正研究中的 RQs ‣ 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

    1.  [3.2 验证 RQs 的框架](https://arxiv.org/html/2406.01297v2#S3.SS2 "在 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

        1.  [现实与不现实。](https://arxiv.org/html/2406.01297v2#S3.SS2.SSS0.Px1 "在 3.2 验证 RQs 的框架 ‣ 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

        1.  [公平与不公平。](https://arxiv.org/html/2406.01297v2#S3.SS2.SSS0.Px2 "在 3.2 验证 RQs 的框架 ‣ 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

1.  [4 自我纠正与提示](https://arxiv.org/html/2406.01297v2#S4 "在 LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

    1.  [负面结果。](https://arxiv.org/html/2406.01297v2#S4.SS0.SSS0.Px1 "在 4 自我纠正与提示 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

    1.  [不现实或不公平的设置。](https://arxiv.org/html/2406.01297v2#S4.SS0.SSS0.Px2 "在 4 自我纠正与提示 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

    1.  [自我纠正特别有效的任务。](https://arxiv.org/html/2406.01297v2#S4.SS0.SSS0.Px3 "在 4 自我纠正与提示 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

1.  [5 自我纠正与外部信息](https://arxiv.org/html/2406.01297v2#S5 "在 LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

    1.  [5.1 自我纠正与外部工具或知识](https://arxiv.org/html/2406.01297v2#S5.SS1 "在 5 自我纠正与外部信息 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

        1.  [不公平的自我纠正与外部信息。](https://arxiv.org/html/2406.01297v2#S5.SS1.SSS0.Px1 "在 5.1 自我纠正与外部工具或知识 ‣ 5 自我纠正与外部信息 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的关键调查")

        1.  [可验证任务](https://arxiv.org/html/2406.01297v2#S5.SS1.SSS0.Px2 "在 5.1 外部工具或知识的自我修正 ‣ 5 外部信息的自我修正 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

    1.  [5.2 微调中的自我修正](https://arxiv.org/html/2406.01297v2#S5.SS2 "在 5 外部信息的自我修正 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

        1.  [大规模训练数据用于反馈的 SFT](https://arxiv.org/html/2406.01297v2#S5.SS2.SSS0.Px1 "在 5.2 微调中的自我修正 ‣ 5 外部信息的自我修正 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

        1.  [不公平的微调](https://arxiv.org/html/2406.01297v2#S5.SS2.SSS0.Px2 "在 5.2 微调中的自我修正 ‣ 5 外部信息的自我修正 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

1.  [6 强基线](https://arxiv.org/html/2406.01297v2#S6 "在何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

    1.  [自我一致性](https://arxiv.org/html/2406.01297v2#S6.SS0.SSS0.Px1 "在 6 强基线 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

    1.  [生成与排序](https://arxiv.org/html/2406.01297v2#S6.SS0.SSS0.Px2 "在 6 强基线 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

1.  [7 我们分析的总结](https://arxiv.org/html/2406.01297v2#S7 "在何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

    1.  [瓶颈在于反馈生成](https://arxiv.org/html/2406.01297v2#S7.SS0.SSS0.Px1 "在 7 我们分析的总结 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

    1.  [适合自我修正的任务](https://arxiv.org/html/2406.01297v2#S7.SS0.SSS0.Px2 "在 7 我们分析的总结 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

1.  [8 自我修正研究检查表](https://arxiv.org/html/2406.01297v2#S8 "在何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

1.  [9 与其他调查的差异](https://arxiv.org/html/2406.01297v2#S9 "在何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

1.  [10 自我修正的相关工作](https://arxiv.org/html/2406.01297v2#S10 "在何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

    1.  [自我检测](https://arxiv.org/html/2406.01297v2#S10.SS0.SSS0.Px1 "在 10 自我修正的相关工作 ‣ 何时 LLMs 实际能纠正自己的错误？对 LLMs 自我修正的批判性调查")

    1.  [编辑人工撰写的文本](https://arxiv.org/html/2406.01297v2#S10.SS0.SSS0.Px2 "在 10 个相关工作 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

    1.  [自我训练](https://arxiv.org/html/2406.01297v2#S10.SS0.SSS0.Px3 "在 10 个相关工作 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

1.  [11 个未来方向](https://arxiv.org/html/2406.01297v2#S11 "在 LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

    1.  [改进反馈。](https://arxiv.org/html/2406.01297v2#S11.SS0.SSS0.Px1 "在 11 个未来方向 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

    1.  [未探索的任务。](https://arxiv.org/html/2406.01297v2#S11.SS0.SSS0.Px2 "在 11 个未来方向 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

    1.  [在小规模训练数据上微调。](https://arxiv.org/html/2406.01297v2#S11.SS0.SSS0.Px3 "在 11 个未来方向 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

    1.  [预训练以改进自我纠正。](https://arxiv.org/html/2406.01297v2#S11.SS0.SSS0.Px4 "在 11 个未来方向 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

1.  [12 结论](https://arxiv.org/html/2406.01297v2#S12 "在 LLMs 何时能真正纠正自己的错误？LLMs 自我纠正的批判性调查")

# LLMs 何时能真正纠正自己的错误？

LLMs 自我纠正的批判性调查

Ryo Kamoi¹ Yusen Zhang¹ Nan Zhang¹ Jiawei Han² Rui Zhang¹

¹宾夕法尼亚州立大学  ²伊利诺伊大学香槟分校

{ryokamoi,rmz5227}@psu.edu

###### 摘要

自我纠正是一种通过在推理过程中使用大语言模型（LLMs）来改进其回应的方法。先前的工作提出了多种自我纠正框架，利用不同的反馈来源，包括自我评估和外部反馈。然而，关于 LLMs 何时能够纠正自己的错误仍没有达成共识，因为最近的研究也报告了负面结果。在这项工作中，我们对广泛的论文进行了批判性调查，并讨论了成功自我纠正所需的条件。我们首先发现，先前的研究通常未详细定义其研究问题，并涉及不切实际的框架或不公平的评估，这些评估高估了自我纠正。为了解决这些问题，我们对自我纠正研究中的研究问题进行了分类，并提供了设计适当实验的检查清单。我们基于新分类的研究问题进行的批判性调查表明，（1）除非是在特别适合自我纠正的任务中，否则没有先前的工作证明了利用提示 LLMs 的反馈成功实现了自我纠正，（2）自我纠正在可以使用可靠外部反馈的任务中效果良好，（3）大规模的微调能够实现自我纠正。

## 1 引言

自我纠错是一种流行的方法，通过在推理过程中使用大型语言模型（LLMs）来改进其响应（Bai et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib4); Madaan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)）。大量关于自我纠错的研究已经涵盖了各种任务，包括算术推理、代码生成和问答（Gao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib29); Shinn et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib88)）。最简单的自我纠错方法促使 LLMs 对其自身的响应提供反馈，并根据反馈改进响应（Huang et al., [2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)），假设识别错误比避免错误更容易（Saunders et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib81)）。如图[1](https://arxiv.org/html/2406.01297v2#S1.F1 "Figure 1 ‣ 1 Introduction ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")所示，自我纠错还研究了利用额外信息来改善反馈，包括外部工具如代码解释器（Chen et al., [2024d](https://arxiv.org/html/2406.01297v2#bib.bib15); Gou et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib32)）、通过网络搜索检索的外部知识（Gao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib29); Jiang et al., [2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)）或微调（Welleck et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib101); Ye et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib112)）。然而，最近的研究也报告了负面结果，表明 LLMs 无法自我纠错（Huang et al., [2024a](https://arxiv.org/html/2406.01297v2#bib.bib39); Gou et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib32); Li et al., [2024b](https://arxiv.org/html/2406.01297v2#bib.bib53)），甚至无法自我检测（Chen and Shu, [2024](https://arxiv.org/html/2406.01297v2#bib.bib11); Tyen et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib93); Hong et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib37); Jiang et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib42); Kamoi et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib46)），至少在某些条件下。这些矛盾的观察表明需要进一步分析自我纠错。

在这项工作中，我们提供了一个关键性的调查，以研究成功自我纠错所需的条件。首先，我们的分析发现，先前的研究通常没有详细定义其研究问题。因此，许多论文未能提供适当的实验来评估其隐含目标的研究问题。为了解决这一问题，我们将自我纠错研究中的研究问题进行分类（§[3.1](https://arxiv.org/html/2406.01297v2#S3.SS1 "3.1 自我纠错研究中的研究问题 ‣ 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")），并讨论了应使用哪些框架来验证每个研究问题（§[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 验证研究问题的框架 ‣ 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")）。最后，我们提供了一个设计适当实验的检查清单（§[8](https://arxiv.org/html/2406.01297v2#S8 "8 自我纠错研究检查清单 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")）。

接下来，我们分析了先前的工作，以使用研究问题的新定义来识别 LLMs 何时能够自我纠错。我们的分析突出显示，瓶颈在于反馈生成（§[7](https://arxiv.org/html/2406.01297v2#S7 "7 我们分析的总结 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")）。具体而言，（1）没有先前的工作显示出在一般任务中使用提示的 LLMs 反馈成功自我纠错（§[4](https://arxiv.org/html/2406.01297v2#S4 "4 使用提示的自我纠错 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")），（2）在可以获得可靠的外部反馈的任务中，自我纠错效果良好（§[5.1](https://arxiv.org/html/2406.01297v2#S5.SS1 "5.1 使用外部工具或知识的自我纠错 ‣ 5 外部信息的自我纠错 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")），（3）大规模的微调使自我纠错成为可能（§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 使用微调的自我纠错 ‣ 5 外部信息的自我纠错 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")），以及（4）一些任务具有特别适合自我纠错的特性（§[4](https://arxiv.org/html/2406.01297v2#S4 "4 使用提示的自我纠错 ‣ LLMs 何时能真正纠正自己的错误？自我纠错的关键调查")）。总之，我们的分析确定了成功自我纠错所需的特性如下：

[[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "1st item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 何时 LLMs 能够仅凭自身的固有能力进行自我修正？

+   •

    在一般任务中，尚无先前工作显示在上下文学习中成功自我修正的可靠证据。 (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

+   •

    在具有特定属性且特别有利于自我修正的任务中（例如，响应可以分解），即使在上下文学习中，自我修正也是有效的。 (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

[[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "2nd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 何时 LLMs 能够利用外部信息自我修正最佳初始响应？

+   •

    当可靠的外部反馈可用时，自我修正是有效的。 (§[5.1](https://arxiv.org/html/2406.01297v2#S5.SS1 "5.1 Self-Correction with External Tools or Knowledge ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

+   •

    当有大量训练数据时，微调能够实现自我修正，但对于小规模训练数据尚未探索。 (§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 Self-Correction with Fine-tuning ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

[[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 何时自我修正的最终输出优于其他方法？

+   •

    自我修正通常没有与足够强大的基线进行比较，目前尚不清楚它是否优于其他方法。 (§[6](https://arxiv.org/html/2406.01297v2#S6 "6 Strong Baselines ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

![参考说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：自我修正的三个阶段：初始响应生成、反馈和完善。

本调查分为以下几个部分。第[2](https://arxiv.org/html/2406.01297v2#S2 "2 自监督的 LLMs ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")部分概述了自我纠正。第[3](https://arxiv.org/html/2406.01297v2#S3 "3 研究问题 ‣ 何时 LLMs 能够自我纠正？LLMs 自我纠正的关键调查")介绍了对自我纠正研究中的研究问题和框架进行分类的新方法。第[4](https://arxiv.org/html/2406.01297v2#S4 "4 带提示的自我纠正 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")和第[5](https://arxiv.org/html/2406.01297v2#S5 "5 带外部信息的自我纠正 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")部分分别分析了上下文学习和外部信息（外部工具、外部知识、微调）的自我纠正的先前工作。第[6](https://arxiv.org/html/2406.01297v2#S6 "6 强基线 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")部分解释了应与自我纠正进行基线比较的相关方法。第[7](https://arxiv.org/html/2406.01297v2#S7 "7 我们分析的总结 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")总结了我们从分析中得出的发现。第[8](https://arxiv.org/html/2406.01297v2#S8 "8 自我纠正研究的检查表 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")提供了自我纠正研究的检查表。第[9](https://arxiv.org/html/2406.01297v2#S9 "9 与其他调查的差异 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")解释了与其他调查的差异。第[10](https://arxiv.org/html/2406.01297v2#S10 "10 自我纠正的相关工作 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")提供了与自我纠正相关的研究。第[11](https://arxiv.org/html/2406.01297v2#S11 "11 未来方向 ‣ 何时 LLMs 能够自我纠正？LLMs 自监督的关键调查")提供了未来的方向。

| 论文 | 类别 | 主要模型 | 附加反馈 | 主要任务 |
| --- | --- | --- | --- | --- |
|  |  |  | Oracle | 外部工具 | 微调 | 推理、编码 | 闭卷、知识 | 开卷、基于上下文 | 开放式文本生成 | 可分解的 |
| 带上下文学习的自我纠正（内在自我纠正） |
| —–CoVe—–  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib22)) | 内在 | PaLM 540B | – | – | – | – | – | – | – | 多种答案 |
| CAI 修订 ([2022](https://arxiv.org/html/2406.01297v2#bib.bib4))^♠ | 内在 | 52B (无详细信息) | – | – | – | – | – | – | 解毒 | – |
| 自我优化 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib59))^♠ | 内在 | GPT-3.5, GPT-4 | – | – | – | 数学，编码 | – | 对话 | – | – |
| ——-RCI——-  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib48), §3.1) | 神谕 | GPT-3.5-T | ✓ | – | – | 计算任务 | CSQA | – | – | – |
| —-反思—-  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88), §4.2) | 神谕 | GPT-4 | ✓ | – | – | – | – | HotpotQA (GT 上下文) | – | – |
| 使用外部工具或知识进行自我纠正 |
| —-反思—-  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88), §4.1, 4.3) | 公平-不对称 | GPT-4 | – | 游戏环境，解释器 | – | 游戏，编码 | – | – | – | – |
| 自我调试 ([2024d](https://arxiv.org/html/2406.01297v2#bib.bib15)) | 公平-不对称 | GPT-3.5-T, GPT-4 | – | 代码解释器 | – | 文本到代码 | – | – | – | – |
| —-CRITIC—-  ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32)) | 公平-不对称 | GPT-3, Llama 2 70B | – | 解释器，网络搜索 | – | GSM8k, SVAMP | HotpotQA | – | 解毒 | – |
| —-RARR—-  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib29)) | 不公平-不对称 | Palm 540B | – | 网络搜索 | – | – | NQ, SQA, QReCC | – | – | – |
| —-反思—-  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88), §4.2) | 神谕 | GPT-4 | ✓ | 维基百科 API | – | – | HotpotQA | – | – | – |
| 使用微调进行自我纠正 |
| 自我批评 ([2022](https://arxiv.org/html/2406.01297v2#bib.bib81)) | 公平-不对称 | InstructGPT | – | – | 人工评估 | – | – | 基于主题的摘要 | – | – |
| —–SelFee—–  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib112)) | 公平-不对称 | Llama 7B, 13B | – | – | ChatGPT 评估 | MT-Bench | MT-Bench | MT-Bench | MT-Bench | – |
| —–Baldur—–  ([2023](https://arxiv.org/html/2406.01297v2#bib.bib27)) | 公平-不对称 | Minerva 8B, 62B | – | 证明助手 | GT 答案 | 证明生成 | – | – | – | – |
| —REFINER—  ([2024](https://arxiv.org/html/2406.01297v2#bib.bib74)) | Cross-Model | GPT-3.5 (FB:T5-base) | – | – | 合成数据 | 数学，逻辑 | – | – | 道德故事 | – |
| RL4F —–([2023](https://arxiv.org/html/2406.01297v2#bib.bib1))—– | Cross-Model | GPT-3 (FB: T5-large) | – | – | 强化学习 | 行动规划 | – | 基于主题的摘要 | – | – |
| 自我纠正 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib101), §3.4) | Cross-Model | GPT-3 (FB: GPT-Neo) | – | – | GT 答案，外部 | GSM8k, SVAMP | – | – | 解毒 | – |
| 自我纠正 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib101), §3.1-3.3) | 不公平-不对称 | GPT-Neo 1.3B, GPT-2 | – | – | GT 答案，外部 | GSM8k, SVAMP | – | – | 解毒，常量生成 | – |
| 自我纠正的负面结果（即，LLMs 无法自我纠正） |
| RCI (表 17) ([2023](https://arxiv.org/html/2406.01297v2#bib.bib48)) | 内在 | GPT-3.5-T | – | – | – | 计算任务 | CSQA | – | – | – |
| CRITIC 无工具 ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32)) | 内在 | GPT-3, Llama 2 70B | – | – | – | GSM8k, SVAMP | 闭卷 HotpotQA | – | 解毒 | – |
| —[黄等](https://arxiv.org/html/2406.01297v2#bib.bib39)—  ([2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)) | 内在 | GPT-4-T, GPT-3.5-T | – | – | – | GSM8k | CSQA, HotpotQA | – | – | – |

表 1：LLM 自我校正的代表性研究。灰色表示不现实的设置。^♠：生成初始响应的弱提示。FB：用于跨模型校正的反馈模型。

![参见标题](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2：LLM 自我校正框架，按生成反馈所用的信息和是否使用最佳初始响应进行分类（§[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 框架验证 RQ ‣ 3 研究问题 ‣ LLM 何时真正能纠正自己的错误？LLM 自我校正的批判性调查")）。此图展示了代表性架构。

{森林}

分叉边缘，树=生长=东，反转=true，锚点=基座西，父锚点=东，子锚点=西，基座=左，字体=，矩形，绘制=隐藏绘制，圆角，居中对齐，/tikz/居中对齐，最小宽度=0.1em，边缘+=深灰色，线宽=0.8pt，s sep=2pt，内 xsep=2pt，内 ysep=2pt，外 ysep=1pt，ver/.样式=旋转=90，子锚点=北，父锚点=南，锚点=中心，，其中 level=1 文本宽度=4em，字体=，其中 level=2 文本宽度=5em，字体=，其中 level=3 文本宽度=5em，字体=，其中 level=4 文本宽度=4em，字体=，其中 level=5 文本宽度=10em，字体=，其中 level=6 文本宽度=20em，字体=， [ 自我校正，绘制=灰色，颜色=黑色!100，填充=白色!15，粗体，文本=黑色，外部 ysep=0pt [ 同模型

校正，颜色=黑色!100，填充=白色!15，粗体，文本=黑色，外部 ysep=0pt，l=5pt [ 上下文

学习，颜色=黑色!100，填充=紫色!15，粗体，文本=黑色，外部 ysep=0pt，l=5pt [ 神谕

信息，颜色=黑色!100，填充=紫色!15，粗体，文本=黑色，l=5pt [ 不现实，颜色=黑色!100，填充=灰色!15，粗体，文本=黑色，[ 神谕信息，颜色=黑色!100，填充=灰色!15，粗体，文本=黑色 [ RCI ([2023](https://arxiv.org/html/2406.01297v2#bib.bib48))，反射 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88)，§4.2)，叶子，颜色=黑色!50，填充=灰色!15，粗体，文本=黑色]]]] [ 无外部

信息，颜色=Black!100，填充=Purple!15，粗体，文本=黑色，l=5pt [ 内在，颜色=Black!100，填充=White!15，粗体，文本=黑色 [ 可分解任务，颜色=Black!100，填充=Purple!15，粗体，文本=黑色 [ CoVe ([2023](https://arxiv.org/html/2406.01297v2#bib.bib22))，叶子，颜色=Black!50，填充=Purple!15，粗体，文本=黑色 ] ] [ 一般任务，颜色=Black!100，填充=Purple!15，粗体，文本=黑色 [ CAI 修订版 ([2022](https://arxiv.org/html/2406.01297v2#bib.bib4))，Self-Refine ([2023](https://arxiv.org/html/2406.01297v2#bib.bib59))，叶子，颜色=Black!50，填充=Purple!15，粗体，文本=黑色 ] ] ] ] [ 外部

知识，颜色=Blue!100，填充=Purple!15，粗体，文本=黑色，l=5pt [ 公平，颜色=Black!100，填充=White!15，粗体，文本=黑色 [ 搜索引擎，颜色=Blue!100，填充=Purple!15，粗体，文本=黑色 [ CRITIC ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32))，FLARE ([2023b](https://arxiv.org/html/2406.01297v2#bib.bib44))，叶子，颜色=Blue!50，填充=Purple!15，粗体，文本=黑色 ] ] ] [ 不公平，颜色=Black!100，填充=Gray!15，粗体，文本=黑色 [ 搜索引擎，颜色=Blue!100，填充=Gray!15，粗体，文本=黑色 [ RARR ([2023](https://arxiv.org/html/2406.01297v2#bib.bib29))，Verify-and-Edit ([2023](https://arxiv.org/html/2406.01297v2#bib.bib121))，Varshney 等 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib96))，叶子，颜色=Blue!50，填充=Gray!15，粗体，文本=黑色 ] ] [ 维基百科，颜色=Blue!100，填充=Gray!15，粗体，文本=黑色 [ ReFeed ([2023](https://arxiv.org/html/2406.01297v2#bib.bib114))，叶子，颜色=Blue!50，填充=Gray!15，粗体，文本=黑色 ] ] ] ] [ 外部

工具，颜色=Red!100，填充=Purple!15，粗体，文本=黑色，l=5pt [ 公平，颜色=Black!100，填充=White!15，粗体，文本=黑色 [ 代码解释器或编译器，颜色=Red!100，填充=Purple!15，粗体，文本=黑色 [ Self-Debug ([2024d](https://arxiv.org/html/2406.01297v2#bib.bib15))，CRITIC ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32))，

反射 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88)，§4.3)，SelfEvolve ([2023a](https://arxiv.org/html/2406.01297v2#bib.bib43))，叶子，颜色=Red!50，填充=Purple!15，粗体，文本=黑色 ] ] [ 逻辑推理器，颜色=Red!100，填充=Purple!15，粗体，文本=黑色 [ Logic-LM ([2023](https://arxiv.org/html/2406.01297v2#bib.bib71))，叶子，颜色=Red!50，填充=Purple!15，粗体，文本=黑色 ] ] [ 模拟环境，颜色=Red!100，填充=Purple!15，粗体，文本=黑色 [ 反射 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88)，§4.1)，叶子，颜色=Red!50，填充=Purple!15，粗体，文本=黑色 ] ] [ 目标模型

提示优化，颜色=Red!100，填充=Purple!15，粗体，文本=黑色 [ ProTeGi ([2023](https://arxiv.org/html/2406.01297v2#bib.bib77))，OPRO ([2024](https://arxiv.org/html/2406.01297v2#bib.bib106))，叶子，颜色=Red!50，填充=Purple!15，粗体，文本=黑色 ] ] ] ] ] [ 微调，颜色=Black!100，填充=Orange!15，粗体，文本=黑色，外部 ysep=0pt，l=5pt [ 无外部

信息，颜色=黑色!100，填充=橙色!15，粗体，文本=黑色，l=5pt [ 公平，颜色=黑色!100，填充=白色!15，粗体，文本=黑色 [ SFT: 人类反馈，颜色=黑色!100，填充=橙色!15，粗体，文本=黑色 [ 自我批评 ([2022](https://arxiv.org/html/2406.01297v2#bib.bib81))，叶子，颜色=黑色!50，填充=橙色!15，粗体，文本=黑色，] ] [ SFT: 来自

大型模型的反馈，颜色=黑色!100，填充=橙色!15，粗体，文本=黑色 [ SelFee ([2023](https://arxiv.org/html/2406.01297v2#bib.bib112))，Volcano ([2024](https://arxiv.org/html/2406.01297v2#bib.bib50))，叶子，颜色=黑色!50，填充=橙色!15，粗体，文本=黑色，] ] ] [ 不公平，颜色=黑色!100，填充=灰色!15，粗体，文本=黑色 [ 较弱的微调

对初始响应，颜色=黑色!100，填充=灰色!15，粗体，文本=黑色 [ 自我纠正学习 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib101)，§3.1-3.3)，叶子，颜色=黑色!50，填充=灰色!15，粗体，文本=黑色，] ] ] ] [ 外部

工具，颜色=红色!100，填充=橙色!15，粗体，文本=黑色，l=5pt [ 公平，颜色=黑色!100，填充=白色!15，粗体，文本=黑色 [ 代码解释器或编译器，颜色=红色!100，，填充=橙色!15，粗体，文本=黑色，[ 自编辑 ([2023b](https://arxiv.org/html/2406.01297v2#bib.bib117)，SFT，PyCodeGPT)，叶子，颜色=红色!50，填充=橙色!15，粗体，文本=黑色 ] ] [ 证明助手，颜色=红色!100，填充=橙色!15，粗体，文本=黑色，[ Baldur ([2023](https://arxiv.org/html/2406.01297v2#bib.bib27)，SFT)，叶子，颜色=红色!50，填充=橙色!15，粗体，文本=黑色 ] ] ] ] ] [ 跨模型

校正，颜色=黑色!100，填充=白色!15，粗体，文本=黑色，外部 ysep=0pt，l=5pt [ 微调

较小模型，颜色=黑色!100，填充=绿色!15，粗体，文本=黑色，外部 ysep=0pt，l=5pt [ 无外部

信息，颜色=黑色!100，填充=绿色!15，粗体，文本=黑色，l=5pt [ SFT: 合成数据，颜色=黑色!100，填充=绿色!15，粗体，文本=黑色，文本宽度=10em[ REFINER ([2024](https://arxiv.org/html/2406.01297v2#bib.bib74))，叶子，颜色=黑色!50，填充=绿色!15，粗体，文本=黑色，文本宽度=20em] ] [ SFT: 自生成数据，颜色=黑色!100，填充=绿色!15，粗体，文本=黑色，文本宽度=10em[ 自我纠正学习 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib101)，§3.4)，叶子，颜色=黑色!50，填充=绿色!15，粗体，文本=黑色，文本宽度=20em] ] [ SFT: 任务特定标准，颜色=黑色!100，填充=绿色!15，粗体，文本=黑色，文本宽度=10em[ Re3 ([2022b](https://arxiv.org/html/2406.01297v2#bib.bib108)，蕴涵)，叶子，颜色=黑色!50，填充=绿色!15，粗体，文本=黑色，文本宽度=20em] ] [ 强化学习，颜色=黑色!100，填充=绿色!15，粗体，文本=黑色，文本宽度=10em[ RL4F ([2023](https://arxiv.org/html/2406.01297v2#bib.bib1))，叶子，颜色=黑色!50，填充=绿色!15，粗体，文本=黑色，文本宽度=20em] ] ] [ 外部

工具，color=Red!100, fill=Green!15, thick, text=black, l=5pt [ 代码解释器或编译器，color=Red!100, fill=Green!15, thick, text=black, text width=10em[ CodeRL ([2022](https://arxiv.org/html/2406.01297v2#bib.bib49), RL), 自我编辑 ([2023b](https://arxiv.org/html/2406.01297v2#bib.bib117), SFT, GPT-3) ，叶子，color=Red!50, fill=Green!15, thick, text=black, text width=20em] ] ] ] [ 多代理

讨论，color=Black!100, fill=Gray!15, thick, text=black, outer ysep=0pt, l=5pt [ 无外部

信息，color=Black!100, fill=Gray!15, thick, text=black, l=5pt [ MAD ([2023](https://arxiv.org/html/2406.01297v2#bib.bib54)), LM vs LM ([2023](https://arxiv.org/html/2406.01297v2#bib.bib20)), PRD ([2023](https://arxiv.org/html/2406.01297v2#bib.bib52)) ，叶子，color=Black!50, fill=Gray!15, thick, text=black, text width=20em] ] ] ] ]

图 3：LLM 自我修正的分类，按生成反馈所使用的信息以及是否使用最佳初始响应（公平或不公平）进行分类。有关定义，请参阅第[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 验证 RQs 的框架 ‣ 3 个研究问题 ‣ 何时 LLM 能真正纠正自己的错误？LLM 自我修正的批判性调查")节。

| RQ | 自我精炼 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib59)) | 黄等 ([2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)) | —–RCI—– ([2023](https://arxiv.org/html/2406.01297v2#bib.bib48), §3.1) | —–RCI—– ([2023](https://arxiv.org/html/2406.01297v2#bib.bib48), §3.2) | CRITIC ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32), §4.2) | CRITIC ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32), §4.3) | —–RARR—– ([2023](https://arxiv.org/html/2406.01297v2#bib.bib29)) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第 1 项 ‣ 3.1 自我修正研究中的研究问题 ‣ 3 个研究问题 ‣ 何时 LLM 能真正纠正自己的错误？LLM 自我修正的批判性调查") | ✓ | ✗ (§3,5) | ✓ | – | ✗ | ✗ | – |
| [RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第 2 项 ‣ 3.1 自我修正研究中的研究问题 ‣ 3 个研究问题 ‣ 何时 LLM 能真正纠正自己的错误？LLM 自我修正的批判性调查") | – | – | – | ✓ | ✓ | ✓ | – |
| [RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我修正研究中的研究问题 ‣ 3 个研究问题 ‣ 何时 LLM 能真正纠正自己的错误？LLM 自我修正的批判性调查") | – | ✗ (§4) | – | ✓ | – | ✓ | ✓ |

表 2：之前的研究通过声称他们已✓验证或✗反驳的研究问题。

| RQ | 框架要求 | 所需实验 |
| --- | --- | --- |
|  | 信息对称性 | 最佳初始响应 | 现实 | 与初始响应的比较 | 与强基线的比较 |
| [RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第一项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 研究问题 ‣ LLMs 何时能够实际纠正自身错误？对 LLMs 自我纠正的批判性调查") | ✓ | ✓ | ✓ | ✓ | – |
| [RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第二项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 研究问题 ‣ LLMs 何时能够实际纠正自身错误？对 LLMs 自我纠正的批判性调查") | – | ✓ | ✓ | ✓ | – |
| [RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第三项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 研究问题 ‣ LLMs 何时能够实际纠正自身错误？对 LLMs 自我纠正的批判性调查") | – | – | ✓ | – | ✓ |

表 3：验证第 [3.1](https://arxiv.org/html/2406.01297v2#S3.SS1 "3.1 自我纠正研究中的研究问题 ‣ 3 研究问题 ‣ LLMs 何时能够实际纠正自身错误？对 LLMs 自我纠正的批判性调查") 节中每个研究问题的实验要求。

## 2 自我纠正的 LLMs

“自我纠正”一词被应用于广泛的场景，从 LLMs 自行改进自身响应的严格定义（Madaan 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib59); Huang 等，[2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)）到更广泛的概念，这些概念还涉及来自外部工具或知识的反馈（Shinn 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib88); Gou 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib32)）。在本研究中，我们将自我纠正定义为一个框架，该框架在推理过程中使用 LLMs 来改进 LLMs 的响应，可能还会使用外部工具或知识。如表 [1](https://arxiv.org/html/2406.01297v2#S1.T1 "表 1 ‣ 1 引言 ‣ LLMs 何时能够实际纠正自身错误？对 LLMs 自我纠正的批判性调查")、图 [2](https://arxiv.org/html/2406.01297v2#S1.F2 "图 2 ‣ 1 引言 ‣ LLMs 何时能够实际纠正自身错误？对 LLMs 自我纠正的批判性调查") 和图 [3](https://arxiv.org/html/2406.01297v2#S1.F3 "图 3 ‣ 1 引言 ‣ LLMs 何时能够实际纠正自身错误？对 LLMs 自我纠正的批判性调查") 中，自我纠正在不同的框架下进行了研究，使用了不同的反馈来源。

### 2.1 框架

先前的研究提出了具有不同架构的自我纠正框架。

#### 明确反馈与直接改进。

自我纠正通常包括三个阶段，其中包括反馈生成（Kim 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib48); Madaan 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib59); Shinn 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib88); Huang 等，[2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)）：

+   •

    初始响应生成是从 LLM 中生成初始响应的一个阶段。

+   •

    反馈模型根据原始输入和初始响应生成反馈。此阶段可能使用外部工具或知识。

+   •

    精炼模型在给定输入、初始响应和反馈的情况下生成精炼的响应。

直接精炼是另一种在不显式生成反馈的情况下精炼响应的方法（Saunders 等， [2022](https://arxiv.org/html/2406.01297v2#bib.bib81)；Bai 等， [2022](https://arxiv.org/html/2406.01297v2#bib.bib4)；Welleck 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib101)；Akyurek 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib1)）。

#### 事后纠正与生成时纠正。

事后纠正是在生成响应后进行精炼（Pan 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib72)）。生成时纠正或步骤级纠正（Paul 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib74)；Jiang 等， [2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)）通过对中间推理步骤提供反馈来改进逐步推理。事后纠正更具灵活性，并适用于更广泛的任务，尽管生成时纠正在推理任务中更为流行（Pan 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib72)）。

#### 同模型与跨模型。

跨模型纠正使用与生成初始响应的模型不同的模型来生成反馈或精炼响应。跨模型纠正主要在使用小型微调模型纠正大型专有 LLMs 错误的设置中进行研究（Welleck 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib101)；Akyurek 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib1)；Paul 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib74)），或在具有相似能力的多个模型的多代理辩论中（Liang 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib54)；Li 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib52)；Cohen 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib20)；Du 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib23)；Zhang 等， [2023a](https://arxiv.org/html/2406.01297v2#bib.bib116)；Chen 等， [2024b](https://arxiv.org/html/2406.01297v2#bib.bib12)；Chan 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib7)；Wang 等， [2024a](https://arxiv.org/html/2406.01297v2#bib.bib98)）。

### 2.2 反馈来源

#### 内在的（§[4](https://arxiv.org/html/2406.01297v2#S4 "4 自我纠正与提示 ‣ LLMs 何时能实际纠正自己的错误？LLMs 自我纠正的关键调查")）。

内在的自我纠错促使 LLMs 对自己的回应生成反馈。提示策略包括简单的零-shot 或少-shot 提示（Madaan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)；Kim et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib48)），对回应进行分解（Dhuliawala et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib22)），以及评估置信度（Varshney et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib96)；Jiang et al., [2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)；Wu et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib103)）。

#### 外部信息（§[5.1](https://arxiv.org/html/2406.01297v2#S5.SS1 "5.1 Self-Correction with External Tools or Knowledge ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")）。

自我纠错通常依赖于外部信息，包括外部工具如代码执行器（Jiang et al., [2023a](https://arxiv.org/html/2406.01297v2#bib.bib43)；Gou et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib32)；Chen et al., [2024d](https://arxiv.org/html/2406.01297v2#bib.bib15)；Stengel-Eskin et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib90)），符号推理器（Pan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib71)），证明助手（First et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib27)），或任务特定的度量（Xu et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib105)），从搜索引擎获取的外部知识（Jiang et al., [2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)；Gao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib29)；Zhao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib121)），维基百科（Yu et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib114)；Zhao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib121)），或其他语料库（Peng et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib75)；Zhao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib121)），诸如真实答案（Kim et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib48)；Shinn et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib88)）的神谕信息，人类反馈（Chen et al., [2024a](https://arxiv.org/html/2406.01297v2#bib.bib9)），或更强的模型（Zhang et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib120)）。

#### 微调（§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 Self-Correction with Fine-tuning ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")）。

经过自我纠正的微调模型是另一种反馈来源，它们通过监督微调（Welleck et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib101); Ye et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib112); First et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib27); Paul et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib74); Han et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib35)) 或强化学习（Le et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib49); Akyurek et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib1)）进行训练。

### 2.3 任务

自我修正已在多种任务中进行研究，包括推理：算术推理（Madaan 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)；Nathani 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib67)；Gou 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib32)），代码生成（Jiang 等， [2023a](https://arxiv.org/html/2406.01297v2#bib.bib43)；Charalambous 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib8)；Gou 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib32)；Chen 等， [2024d](https://arxiv.org/html/2406.01297v2#bib.bib15)；Olausson 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib70)），证明生成（First 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib27)），逻辑推理（Pan 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib71)），知识：闭卷问答（Shinn 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib88)；Gao 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib29)；Jiang 等， [2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)；Gou 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib32)），基于上下文的生成：对话生成（Madaan 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)；Peng 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib75)），文本摘要（Saunders 等， [2022](https://arxiv.org/html/2406.01297v2#bib.bib81)），开放式生成：条件文本生成（Ye 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib112)；Schick 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib83)），故事生成（Yang 等， [2022b](https://arxiv.org/html/2406.01297v2#bib.bib108)），去毒化（Schick 等， [2021](https://arxiv.org/html/2406.01297v2#bib.bib82)；Bai 等， [2022](https://arxiv.org/html/2406.01297v2#bib.bib4)；Gou 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib32)；Phute 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib76)），其他：机器翻译（Chen 等， [2023b](https://arxiv.org/html/2406.01297v2#bib.bib13)；Raunak 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib79)；Ki 和 Carpuat， [2024](https://arxiv.org/html/2406.01297v2#bib.bib47)），信息检索（Gero 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib31)），视觉语言任务（Yin 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib113)；Ge 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib30)；Zhou 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib122)；Lee 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib50)；Huang 等， [2024b](https://arxiv.org/html/2406.01297v2#bib.bib40)；Liu 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib57)），以及提示优化（Pryzant 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib77)；Mehrabi 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib61)；Yang 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib106)）。

### 2.4 与相关方法的区别

在这项工作中，我们将自我一致性（Wang et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib99)）或生成-排名（Shen et al., [2021](https://arxiv.org/html/2406.01297v2#bib.bib86); Weng et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib102)）定义为与自我纠正不同，因为这些方法不完善响应，并假设 LLMs 以合理的概率生成正确答案。我们在第[6](https://arxiv.org/html/2406.01297v2#S6 "6 强基线 ‣ LLMs 何时能够真正纠正自己的错误？LLMs 自我纠正的批判性调查")节中讨论这些方法作为应与自我纠正进行比较的强基线。

## 3 个研究问题

我们发现先前的研究通常没有详细定义其研究问题，也未能在实验中使用适当的自我纠正框架。我们提出了一种新的方法来分类自我纠正中的研究问题和框架。

### 3.1 自我纠正研究中的研究问题

先前的研究通常只是简单地陈述其研究问题是否 LLMs 可以自我纠正其错误（例如，Kim et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib48); Madaan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)）。然而，我们认为自我纠正研究中的研究问题应更详细地定义。我们识别了在先前研究中隐含的以下研究问题，如表[3](https://arxiv.org/html/2406.01297v2#S1.T3 "表 3 ‣ 1 介绍 ‣ LLMs 何时能够真正纠正自己的错误？LLMs 自我纠正的批判性调查")所示。

+   •

    [[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第 1 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 何时能够真正纠正自己的错误？LLMs 自我纠正的批判性调查")] LLMs 是否可以仅凭其固有能力自我纠正其最佳初始响应？ (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 通过提示进行的自我纠正 ‣ LLMs 何时能够真正纠正自己的错误？LLMs 自我纠正的批判性调查"))

+   •

    [[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第 2 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 何时能够真正纠正自己的错误？LLMs 自我纠正的批判性调查")] LLMs 是否可以通过外部信息来自我纠正其最初的最佳响应？ (§[5](https://arxiv.org/html/2406.01297v2#S5 "5 外部信息下的自我纠正 ‣ LLMs 何时能够真正纠正自己的错误？LLMs 自我纠正的批判性调查"))

+   •

    [[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我修正研究中的 RQ ‣ 3 研究问题 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我修正的批判性调查")] 自我修正的最终输出是否比其他方法更好？ (§[6](https://arxiv.org/html/2406.01297v2#S6 "6 强基线 ‣ LLMs 何时能真正纠正自己的错误？LLMs 自我修正的批判性调查"))

我们将最佳初始响应定义为使用自我修正模块可以访问的信息（如外部工具、知识或微调）生成的最佳努力初始响应。

#### 验证 RQ 的要求。

验证这些研究问题的实验需要满足不同的要求，如表格[3](https://arxiv.org/html/2406.01297v2#S1.T3 "表 3 ‣ 1 引言 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")所示。外部信息：[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第 1 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")需要在使用相同模型而不依赖额外信息的框架中进行评估。[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第 2 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")和[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")可以在使用外部信息的框架中进行评估。初始响应：[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第 1 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")和[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第 2 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")需要在使用最佳初始响应的框架中进行评估。[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")关心最终表现，因此不必从强大的初始响应开始。评估：[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第 1 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")和[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第 2 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")只需展示自我纠正如何改善初始响应的表现。[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我纠正研究中的研究问题 ‣ 3 个研究问题 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查")需要与强基线进行比较 (§[6](https://arxiv.org/html/2406.01297v2#S6 "6 强基线 ‣ LLMs 什么时候真的能纠正自己的错误？LLMs 自我纠正的批判性调查"))。

#### 以往工作的混淆。

一些先前的研究在单一工作中隐含地针对不同的研究问题，但没有明确区分它们。如表[3](https://arxiv.org/html/2406.01297v2#S1.T3 "Table 3 ‣ 1 Introduction ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")所示，Kim 等（[2023](https://arxiv.org/html/2406.01297v2#bib.bib48)）针对算术推理的[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "1st item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")通过仅将自我纠错的响应与初始响应进行比较，但他们针对 MiniWoB++的[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")通过将自我纠错与基线方法进行比较。类似地，Gou 等（[2024](https://arxiv.org/html/2406.01297v2#bib.bib32)）针对算术推理的[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "2nd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")，但针对解毒的[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")。

### 3.2 验证研究问题的框架

以往的工作通常根据生成反馈的方法来分类自我纠错框架（§[2](https://arxiv.org/html/2406.01297v2#S2 "2 Self-Correction of LLMs ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")）。然而，我们指出，还需要根据初始响应的质量来分类这些框架，因为用于验证不同研究问题的框架是否使用最佳初始响应会有所不同（§[3.1](https://arxiv.org/html/2406.01297v2#S3.SS1 "3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")）。

我们提出了（同模型）自我纠错的分类，这些分类对应于不同的研究问题（§[3.1](https://arxiv.org/html/2406.01297v2#S3.SS1 "3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")），如图[2](https://arxiv.org/html/2406.01297v2#S1.F2 "Figure 2 ‣ 1 Introduction ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")所示。具体来说，我们建议将自我纠错框架分类如下。

+   •

    现实：可以在实际应用中使用。

    +   –

        公平：使用最佳的初始响应

    +   –

        不公平：使用次优的初始响应

+   •

    不现实：使用在实际应用中无法获得的信息。

在这项工作中，我们专注于对不涉及多种不同架构语言模型的自我纠错框架进行分类。交叉模型纠错使用不同的模型生成初始响应和自我纠错，因此不适合评估 LLM 是否能改进其自身的初始响应 [[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "1st item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"), [RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "2nd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")]. 然而，它可以用来评估 [[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 自我纠错的最终响应是否优于其他方法。

#### 现实 vs. 不现实。

一些先前的研究提出了不现实的自我纠错方法，这些方法无法在实际应用中实施，例如使用真实答案（Kim et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib48); Shinn et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib88)）。这些方法不能用于验证任何研究问题。

#### 公平 vs. 不公平。

现实框架可以根据是否使用最佳初始响应来分类。公平自我修正代表了那些完善最佳初始响应的框架。（1）内在自我修正（黄等，[2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)）使用相同的模型和信息来生成初始响应和进行自我修正。内在自我修正可用于评估[[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "1st item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] LLM 是否能仅凭其固有能力进行自我修正。（2）公平不对称自我修正使用额外信息进行自我修正，但也使用信息尽可能改善初始响应生成。例如，使用代码解释器进行自我修正（陈等，[2024d](https://arxiv.org/html/2406.01297v2#bib.bib15); Gou 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib32)）不是内在的，但却是公平的，因为我们不能轻易地使用代码解释器直接改善初始响应生成。公平不对称自我修正可以用来评估[[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "2nd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] LLM 是否可以使用外部信息自我修正最佳初始响应。不公平自我修正（或不公平不对称自我修正）代表了那些实际但不使用最佳初始响应的框架。例如，单纯使用搜索引擎进行自我修正的方法（高等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib29); 余等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib114)）是不公平的，因为它们可以使用搜索引擎直接改善初始响应生成。不公平自我修正可以评估[[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 自我修正后的最终响应是否优于其他方法，但不能评估[[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "2nd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 自我修正是否能改善最佳初始响应。

| 论文 | 任务 | 使用 Oracle 信息进行反馈 | 初始响应的弱提示 | 备注 |
| --- | --- | --- | --- | --- |
| —-RCI—- ([2023](https://arxiv.org/html/2406.01297v2#bib.bib48)，§3.1) | 计算机任务 | ———✓——— 停止条件 | – | 使用真实答案且不更新正确响应，这不公平地忽略了假阳性修正 |
| 反射 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88)，§4.2) | HotpotQA（上下文） | ———✓——— 反馈 | – | 反馈是响应与真实答案之间的精确匹配 |
| CAI 修订 ([2022](https://arxiv.org/html/2406.01297v2#bib.bib4)) | 解毒 | – | ✓ | 初始生成未提示去除有害输出 |
| 自我优化 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib59)) | 数学、编码、对话 | – | ✓ | 初始响应生成的指令不公平地弱或错误，或少量示例 |

表 4：先前自我修正研究中的不公平设置，过度评估自我修正。

## 4 自我修正与提示

> [[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第 1 项 ‣ 3.1 自我修正研究中的研究问题 ‣ 3 研究问题 ‣ LLM 能否仅基于内在能力自我修正其最佳初始响应？")](https://arxiv.org/html/2406.01297v2#S3.I1.i1) LLM 能否仅基于内在能力自我修正其最佳初始响应？

一些研究提出了内在自我修正方法，这些方法通过提示自己生成反馈和修正响应来修正来自 LLM 的响应。Bai 等（[2022](https://arxiv.org/html/2406.01297v2#bib.bib4)）提出了通过自我提示修正有害响应的方法。Self-Refine（Madaan 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib59)）和 RCI 提示（Kim 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib48)）反复提示 LLM 自我修正其在算术推理等任务中的响应。

#### 负面结果。

然而，最近的研究报告显示，内在的自我修正并没有改善甚至会降低在诸如算术推理、闭卷问答（Huang 等，[2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)；Gou 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib32)）、代码生成（Gou 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib32)；Olausson 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib70)）、计划生成（Valmeekam 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib95)）和图着色（Stechly 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib89)）等任务中的表现。一些研究指出，瓶颈在于反馈生成，仅通过自我提示生成可靠的反馈是困难的（Gou 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib32)；Huang 等，[2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)；Olausson 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib70)）。

#### 不切实际或不公平的设置。

相互矛盾的正面和负面结果促使我们分析当 LLMs 仅通过自我提示时，何时可以自我纠正。具体而言，我们评估先前的研究是否满足验证[[RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "1st item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")]的要求，即 LLMs 是否可以仅根据其固有能力自我纠正其回应。如表[4](https://arxiv.org/html/2406.01297v2#S3.T4 "Table 4 ‣ Fair vs. Unfair. ‣ 3.2 Frameworks for Verifying RQs ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")所示，我们发现许多研究在自我纠正过程中使用了预设信息（不切实际的框架）或弱提示，这些提示可以轻易改进以生成初始回应（不公平的设置），这过度评估了自我纠正。因此，我们得出结论，尚无主要工作显示 LLMs 在公平设置下使用自我提示生成的反馈成功地自我纠正回应。预设信息：RCI Prompting (Kim et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib48)) 使用真实答案，当初始回应正确时不进行自我纠正，这不公平地忽略了由于错误更新正确回应所造成的错误。Reflexion (Shinn et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib88)) 通过生成与真实答案完全匹配的反馈，这在现实应用中无法获得。弱初始回应：净化有害回应是自我纠正研究中的一个热门任务，但先前的研究通常在初始回应生成未指示生成无害回应的情况下进行（Bai et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib4); Wang et al., [2024b](https://arxiv.org/html/2406.01297v2#bib.bib100)）。尽管使用 LLMs 检测有害内容是一个合理的研究主题，但这种设置并不是从最佳可能的初始回应中进行自我纠正，因为我们可以通过指示不生成有害回应来改进初始回应生成过程。作为更明显的弱提示，Self-Refine (Madaan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)) 使用与目标任务不完全对应的指示或少量示例仅用于初始回应生成（例如，在少量示例中提供错误的目标标签），而在自我纠正时使用适当的指示，如表[9](https://arxiv.org/html/2406.01297v2#A0.T9 "Table 9 ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")和[10](https://arxiv.org/html/2406.01297v2#A0.T10 "Table 10 ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")所示。这些设置评估了来自弱初始回应的改进，这过度评估了自我纠正带来的改进。

#### 自我纠错特别有效的任务。

尽管我们对以往研究的分析表明，内在自我纠错通常是困难的，但一些任务具有使反馈生成变得容易并使内在自我纠错成为可能的特性。例如，CoVe（Dhuliawala 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib22)）是一种用于生成多个答案的任务的内在自我纠错方法，如“列出一些出生在纽约州纽约市的政治家”。生成的回答包括多个答案，但反馈生成可以分解为验证每个答案的更简单的子任务。具有可分解响应的任务是少数几个验证明显比生成更容易的任务之一，这使得内在自我纠错成为可能。然而，许多现实世界的任务并不具备这一特性。

| 论文 | 主要任务 | 外部工具或知识 |
| --- | --- | --- |
|  |  | 初始响应生成 | 反馈生成 |
| Reflexion ([2023](https://arxiv.org/html/2406.01297v2#bib.bib88), §4.1, 4.3) | 游戏, 编程 | – | 游戏环境, 代码解释器 |
| CRITIC ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32)) | GSM8k, SVAMP | – | Python 解释器 |
| Self-Debug ([2024d](https://arxiv.org/html/2406.01297v2#bib.bib15)) | 文本到代码 | – | 代码解释器 |
| CRITIC ([2024](https://arxiv.org/html/2406.01297v2#bib.bib32)) | HotpotQA | 网络搜索 | 网络搜索 |
| FLARE ([2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)) | 2WikiMultihopQA, StrategyQA, ASQA | 网络搜索 | 网络搜索 |
| RARR ([2023](https://arxiv.org/html/2406.01297v2#bib.bib29)) | NQ, SQA, QReCC | – | 网络搜索 |
| ReFeed ([2023](https://arxiv.org/html/2406.01297v2#bib.bib114)) | NQ, TriviaQA, HotpotQA | – | 维基百科 |

表 5：使用外部工具或知识进行自我纠错（含上下文学习）。

## 5 使用外部信息进行自我纠错

> [[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第 2 项 ‣ 3.1 自我纠错研究中的研究问题 ‣ 3 研究问题 ‣ LLM 是否能在外部信息的帮助下自我纠错其最佳初始响应？LLM 自我纠错的批判性调查")] LLM 是否能在外部信息的帮助下自我纠错其最佳可能初始响应？

本节分析了利用外部工具、外部知识和微调的自我纠错框架。

### 5.1 使用外部工具或知识进行自我纠错

鉴于反馈生成是自我修正的瓶颈（§[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")），利用外部工具或知识改进反馈是一个有前途的方向。用于自我修正的外部工具包括代码生成任务的代码解释器（Chen et al., [2024d](https://arxiv.org/html/2406.01297v2#bib.bib15); Gou et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib32)）和逻辑推理任务的符号推理器（Pan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib71)）。一个流行的知识来源是搜索引擎，这些搜索引擎通常与从初始响应生成的查询一起使用，以检索信息以验证其正确性（Gao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib29); Jiang et al., [2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)）。这些先前的研究普遍认为，当有可靠的外部工具或知识可用于改进反馈时，自我修正可以改善 LLM 的响应。

#### 不公平的自我修正与外部信息。

尽管使用外部工具或知识在自我纠错中被认为是有效的，但我们提醒注意，使用外部工具或知识的方式会影响我们可以验证的研究问题（§[3.1](https://arxiv.org/html/2406.01297v2#S3.SS1 "3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")）。如表[5](https://arxiv.org/html/2406.01297v2#S4.T5 "Table 5 ‣ Tasks in which Self-Correction is Exceptionally Effective. ‣ 4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")所示，一些早期研究（Gao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib29); Yu et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib114); Zhao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib121)）仅使用外部知识进行自我纠错，而它们也可以直接利用外部知识来改进初步响应生成过程。例如，RARR（Gao et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib29)）利用外部知识来检测初步响应中的错误，但在生成初步响应时不使用任何外部知识。当只关注[[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")]最终响应的表现时，这些方法是合理的，但将它们用于评估[[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "2nd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")]是否可以从最佳初步响应中改进则不公平。相比之下，使用代码解释器进行自我纠错（Gou et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib32); Chen et al., [2024d](https://arxiv.org/html/2406.01297v2#bib.bib15)）可以被视为使用最佳初步响应，因为直接改进初步响应生成的方式并不简单。

#### 可验证任务。

一些任务具有一种属性，可以轻松验证响应的正确性，即使没有外部信息。例如，自我修正 (Madaan 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)) 中评估的约束生成任务是生成一个包含五个指定单词的句子。我们可以通过检查生成的句子中是否包含这五个单词来轻松评估正确性。树思维 (Yao 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib109)) 是一种用于可验证任务的生成和排名方法¹¹1 树思维是一种生成和排名方法，而不是我们定义中的自我修正方法。比如 24 点游戏，这是一个使用基本算术运算 ($+,-,\times,\div$) 和提供的四个整数来获得 24 的任务。对于 24 点游戏，我们可以通过检查生成的答案是否为 24 来轻松验证答案。我们认为自我修正在这些任务中表现良好，因为它们的情况与使用强大的外部工具或预言信息生成反馈的情况相同。

| 论文 | 主要任务 | 跨模型 | SFT 任务 | 初始响应 | 反馈生成 | 精炼 |
| --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  | 模型 | SFT 目标 | 模型 | SFT 目标 | 规模 | 模型 | SFT 目标 |
| –SelFee– ([2023](https://arxiv.org/html/2406.01297v2#bib.bib112)) | MT-Bench | – | 一般任务 | Llama (7B,13B) | ChatGPT 回复 | Llama (7B,13B) | ChatGPT 反馈 | 178K | Llama (7B,13B) | ChatGPT 精炼 |
| –Volcano– ([2024](https://arxiv.org/html/2406.01297v2#bib.bib50)) | 视觉推理 | – | 一般任务 | LLaVA (7B, 13B) | GPT-3.5-T，人类 | LLaVA (7B, 13B) | GPT-3.5-T 反馈 | 274K | LLaVA (7B, 13B) | 参考答案 |
| 自我批评 ([2022](https://arxiv.org/html/2406.01297v2#bib.bib81)) | 基于主题的总结 | – | 目标任务 | 指令 GPT | 人类总结 | 指令 GPT | 人类反馈 | 100K | 指令 GPT | 人类精炼 |
| REFINER ([2024](https://arxiv.org/html/2406.01297v2#bib.bib74)) | 数学、逻辑、道德故事 | ✓ | 目标任务 | GPT-3.5 | – | T5-base | 合成数据 | 20K - 30K | GPT-3.5 | – |
| 自我编辑 ([2023b](https://arxiv.org/html/2406.01297v2#bib.bib117)) | 代码生成 | ✓ | 目标任务 | GPT-3 | – | (代码执行器和测试用例) | PyCodeGPT 110M | 参考代码 |

表 6：带监督微调的自我修正。大多数方法需要大量的训练数据集。“–”表示没有微调。

| [RQ1](https://arxiv.org/html/2406.01297v2#S3.I1.i1 "第 1 项 ‣ 3.1 自我纠错研究中的 RQ ‣ 3 研究问题 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查") | [RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "第 2 项 ‣ 3.1 自我纠错研究中的 RQ ‣ 3 研究问题 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查") | [RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我纠错研究中的 RQ ‣ 3 研究问题 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查") | 验证目标 RQ 的要求 |  |  |
| --- | --- | --- | --- | --- | --- |
| ✓ | ✓ | ✓ | 清楚地陈述目标 RQ 和讨论的自我纠错框架的类别。 | (§[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 框架用于验证 RQ ‣ 3 研究问题 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查")) | 必需 |
| ✓ | ✓ | ✓ | 不使用诸如真实答案等 oracle 信息。 | (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 使用提示的自我纠错 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查")) | 必需 |
| ✓ | ✓ | ✓ | 在使用微调时，报告详细设置，包括达到报告性能所需的注释数量和计算成本。 | (§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 使用微调的自我纠错 ‣ 5 使用外部信息的自我纠错 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查")) | 必需 |
| ✓ | ✓ | ✓ | 直接评估反馈的质量（例如，错误检测准确性）。 | (§[7](https://arxiv.org/html/2406.01297v2#S7 "7 我们分析的总结 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查")) | 推荐 |
| ✓ | ✓ |  | 使用足够强的提示来生成初步回应。 | (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 使用提示的自我纠错 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查")) | 必需 |
| ✓ |  |  | 使用内在自我纠错。 | (§[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 框架用于验证 RQ ‣ 3 研究问题 ‣ LLMs 何时能实际纠正自己的错误？对 LLMs 自我纠错的批判性调查")) | 必需 |
|  |  |  | 使用外部工具或知识时， |  |  |
|  | ✓ |  | 使用外部工具或知识尽可能改善初始响应生成。 | (§[5.1](https://arxiv.org/html/2406.01297v2#S5.SS1 "5.1 使用外部工具或知识的自我修正 ‣ 5 使用外部信息的自我修正 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 必需 |
|  |  |  | 当使用微调进行自我修正时， |  |  |
|  | ✓ |  | 尽可能微调初始响应生成器。 | (§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 通过微调进行自我修正 ‣ 5 使用外部信息的自我修正 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 必需 |
|  | ✓ |  | 评估能够实现自我修正的训练数据的最小要求大小。 | (§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 通过微调进行自我修正 ‣ 5 使用外部信息的自我修正 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 推荐 |
|  | ✓ |  | 评估通过更强大的 LLMs 纠正响应中的错误的跨模型修正设置。 | (§[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 验证 RQs 的框架 ‣ 3 研究问题 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 推荐 |
|  |  | ✓ | 使用可比计算成本的强基线进行比较。 | (§[6](https://arxiv.org/html/2406.01297v2#S6 "6 强基线 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 必需 |

表 7：不同目标研究问题的自我修正研究检查清单。

| 清晰地陈述被报告结果驳斥的 RQ 以及讨论的框架类别。 | (§[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 验证 RQs 的框架 ‣ 3 研究问题 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 必需 |
| --- | --- | --- |
| 使用强提示进行自我修正（例如，最先进的无参考指标）。 | (§[11](https://arxiv.org/html/2406.01297v2#S11 "11 未来方向 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 必需 |
| 当不使用现实世界应用中的外部工具或知识时，明确报告评估是在弱条件下进行的。 | (§[5.1](https://arxiv.org/html/2406.01297v2#S5.SS1 "5.1 使用外部工具或知识的自我修正 ‣ 5 使用外部信息的自我修正 ‣ LLMs 何时能够真正纠正自己的错误？对 LLMs 自我修正的批判性调查")) | 必需 |
| 使用外部工具或现实世界应用中的知识进行评估。 | (§[5.1](https://arxiv.org/html/2406.01297v2#S5.SS1 "5.1 使用外部工具或知识进行自我纠正 ‣ 5 自我纠正与外部信息 ‣ LLMs 何时能真正纠正自己的错误？对 LLMs 自我纠正的批判性调查")) | 推荐 |

表 8: 自我纠正负面结果报告检查表

### 5.2 通过微调进行自我纠正

先前的工作表明，微调 LLMs 以生成反馈或完善回应可以提高自我纠错能力。一种常见的方法是微调反馈模型，以在给定初始回应时生成参考反馈，并微调完善模型，以在给定初始回应和参考反馈时生成参考答案（Ye 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib112)；Lee 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib50)；Saunders 等， [2022](https://arxiv.org/html/2406.01297v2#bib.bib81)）。 框架：第一种方法微调同一模型以纠正其自身回应。在这种方法中，大多数方法微调模型以应对所有阶段：初始回应、反馈和完善（Saunders 等， [2022](https://arxiv.org/html/2406.01297v2#bib.bib81)；Ye 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib112)；Lee 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib50)）。另一种方法是使用较小的微调模型来纠正来自更大模型的回应。这种跨模型纠正方法通常指导较大模型使用来自较小微调模型的反馈来完善自身回应（Yang 等， [2022b](https://arxiv.org/html/2406.01297v2#bib.bib108)；Welleck 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib101)；Akyurek 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib1)；Paul 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib74)），这可以被视为使用小型微调模型作为外部工具。 训练策略：一种流行的方法是监督微调，它在人工标注的反馈上微调自我纠错模块（Saunders 等， [2022](https://arxiv.org/html/2406.01297v2#bib.bib81)），来自更强模型的反馈（Ye 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib112)）或合成的负面回应（Paul 等， [2024](https://arxiv.org/html/2406.01297v2#bib.bib74)）。作为其他方法，为了避免收集人工反馈的成本，自我纠错学习（Welleck 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib101)）选择成功完善回应的模型生成反馈作为训练数据，RL4L（Akyurek 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib1)）使用强化学习。 外部工具：一些工作微调模型，以根据外部工具的反馈来完善回应。Self-Edit（Zhang 等， [2023b](https://arxiv.org/html/2406.01297v2#bib.bib117)）使用代码执行器评估的测试用例上的结果来生成代码，而 Baldur（First 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib27)）使用证明助手来改进证明生成。

#### 大规模训练数据用于反馈的 SFT。

如表格 [6](https://arxiv.org/html/2406.01297v2#S5.T6 "Table 6 ‣ Verifiable Tasks. ‣ 5.1 Self-Correction with External Tools or Knowledge ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs") 所示，许多用于反馈生成的监督微调方法依赖于超过 100K 实例的训练数据。这些研究通常使用更强模型生成的反馈来模拟人工标注，但这种方法需要大规模的人类标注才能在最先进的模型上实施。我们期望未来的研究能够探索不需要大规模人类标注的方法 (§[11](https://arxiv.org/html/2406.01297v2#S11 "11 Future Directions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))。

#### 不公平的微调。

一些研究（Welleck et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib101)）应用了比初始响应生成模型更强的微调用于自我修正模型，这些模型没有使用可用资源中的最佳初始响应 (§[3.2](https://arxiv.org/html/2406.01297v2#S3.SS2 "3.2 Frameworks for Verifying RQs ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))。这种方法可用于评估 [[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 最终响应的表现与其他方法的比较，但不能用于评估 [[RQ2](https://arxiv.org/html/2406.01297v2#S3.I1.i2 "2nd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 从最佳初始响应中获得的改进。

## 6 强基准

> [[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "3rd item ‣ 3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")] 自我修正的最终输出是否比其他方法更好？

自我修正涉及多次调用 LLM 以生成反馈和改进。因此，要声称[[RQ3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我修正研究中的研究问题 ‣ 3 个研究问题 ‣ LLM 什么时候能真正纠正自己的错误？LLM 自我修正的批判性调查")] 自我修正框架的最终输出性能优于其他方法，应该与足够强的基线进行比较，可能需要额外的 LLM 调用或计算成本。许多自我修正研究没有将他们的方法与强基线进行比较，尽管一些研究指出了这个问题，并将自我修正与自我一致性（Gou et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib32); Huang et al., [2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)）或代码生成中的 pass@k（Zhang et al., [2023b](https://arxiv.org/html/2406.01297v2#bib.bib117); Olausson et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib70)）进行比较。我们鼓励未来的研究将自我修正与强基线进行比较，包括自我一致性和生成与排名，以进一步探索[评估问题 3](https://arxiv.org/html/2406.01297v2#S3.I1.i3 "第 3 项 ‣ 3.1 自我修正研究中的研究问题 ‣ 3 个研究问题 ‣ LLM 什么时候能真正纠正自己的错误？LLM 自我修正的批判性调查")。

#### 自我一致性

(Wang et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib99)) 是一种为相同输入生成多个响应并在推理任务中采用最终答案的多数投票的方法。利用同一模型生成的多个响应之间的一致性来选择好的响应的想法，也已经扩展到其他任务，如文本生成（Manakul et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib60); Elaraby et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib25); Chen et al., [2024c](https://arxiv.org/html/2406.01297v2#bib.bib14)）和代码生成（Shi et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib87)）。

#### 生成与排名

是一种生成多个响应并使用验证器选择最佳响应的方法。后验方法通过自我评估（Weng 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib102); Zhang 等，[2023d](https://arxiv.org/html/2406.01297v2#bib.bib119)）、信心（Manakul 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib60)）、微调的验证器（Cobbe 等，[2021](https://arxiv.org/html/2406.01297v2#bib.bib19); Shen 等，[2021](https://arxiv.org/html/2406.01297v2#bib.bib86); Lightman 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib56)）或带有外部工具的验证器（Shi 等，[2022](https://arxiv.org/html/2406.01297v2#bib.bib87); Chen 等，[2023a](https://arxiv.org/html/2406.01297v2#bib.bib10); Ni 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib69)）来对响应进行排序。反馈引导解码生成多个响应，并使用生成概率（Hao 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib36); Tyen 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib93)）为每个推理步骤选择最佳响应，或使用提示自我评估（Jung 等，[2022](https://arxiv.org/html/2406.01297v2#bib.bib45); Creswell 和 Shanahan，[2022](https://arxiv.org/html/2406.01297v2#bib.bib21); Xie 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib104); Yao 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib109); Miao 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib64)），或微调的验证器（Uesato 等，[2022](https://arxiv.org/html/2406.01297v2#bib.bib94); Tafjord 等，[2022](https://arxiv.org/html/2406.01297v2#bib.bib91); Yang 等，[2022a](https://arxiv.org/html/2406.01297v2#bib.bib107); Asai 等，[2024](https://arxiv.org/html/2406.01297v2#bib.bib2)）。

## 7 我们分析的总结

#### 瓶颈在于反馈生成。

先前的研究普遍认为，给定可靠反馈，LLMs 可以改善其响应 (§[5](https://arxiv.org/html/2406.01297v2#S5 "5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))。然而，生成对其自身响应的可靠反馈仍然对 LLMs 来说是一个挑战，尤其是在没有额外信息的情况下 (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))。换句话说，对于当前的 LLMs，识别错误比避免错误更容易的假设（Saunders 等，[2022](https://arxiv.org/html/2406.01297v2#bib.bib81)）根据我们对先前研究实验的分析，仅对那些验证异常简单的任务才成立。我们建议自我纠正研究应更加详细地分析生成的反馈的质量，而不仅仅是评估改进响应的下游性能。

#### 适合自我纠正的任务。

我们的分析确定了在不同条件下适合自我修正的任务的属性。

+   •

    内在自我修正 (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

    +   –

        对于那些验证任务比原始任务容易得多的任务（例如，响应可以分解的任务）

+   •

    使用外部信息的自我修正 (§[5.1](https://arxiv.org/html/2406.01297v2#S5.SS1 "5.1 Self-Correction with External Tools or Knowledge ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

    +   –

        对于那些存在提供可靠反馈的外部工具的任务（例如，代码生成）

    +   –

        对于那些可以利用响应获取在生成初始响应之前难以获得的有用信息的任务（例如，从响应中生成查询以检索文档以验证信息）

+   •

    使用微调的自我修正 (§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 Self-Correction with Fine-tuning ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))

    +   –

        在大规模训练数据可用于反馈生成的情况下，自我修正在许多任务中有效

    +   –

        可以使用强化学习或自我修正学习的任务（Welleck 等，[2023](https://arxiv.org/html/2406.01297v2#bib.bib101)），即那些可以根据真实答案轻松评估其响应的任务

## 自我修正研究的检查清单

我们的分析显示，许多研究没有清楚地定义研究问题，并且未能进行适当的实验（§[3.1](https://arxiv.org/html/2406.01297v2#S3.SS1 "3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")，[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")）。为了解决这些问题，我们提供了一个自我纠正研究的检查清单，该清单提供了设计适当实验以验证目标研究问题的要求以及全面分析的推荐实验。表[8](https://arxiv.org/html/2406.01297v2#S5.T8 "Table 8 ‣ Verifiable Tasks. ‣ 5.1 Self-Correction with External Tools or Knowledge ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")提供了一个验证第[3.1](https://arxiv.org/html/2406.01297v2#S3.SS1 "3.1 RQs in Self-Correction Research ‣ 3 Research Questions ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")节中识别的不同研究问题的检查清单。表[8](https://arxiv.org/html/2406.01297v2#S5.T8 "Table 8 ‣ Verifiable Tasks. ‣ 5.1 Self-Correction with External Tools or Knowledge ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")还提供了一个报告负面结果的检查清单。

## 9 与其他调查的区别

Pan 等人（[2024](https://arxiv.org/html/2406.01297v2#bib.bib72)）提供了一个关于自我纠正的广泛主题的全面调查，包括训练策略。我们的工作特别关注（推理时）自我纠正，并对先前的工作提供了更详细和关键的分析。Huang 等人（[2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)）分析了自我纠正研究评估设置中的问题，这激发了我们的工作。他们关注于分析一些关于推理任务中内在自我纠正的论文。我们提供了一个更全面的自我纠正分析，包括上下文学习、外部工具和微调。

## 10 自我纠正相关工作

#### 自我检测

使用 LLMs（可能还包括外部信息）检查 LLM 响应中的错误已在多个领域进行了研究，包括误信息检测（Zhang et al.，[2023c](https://arxiv.org/html/2406.01297v2#bib.bib118)；Chern et al.，[2023](https://arxiv.org/html/2406.01297v2#bib.bib17)；Chen and Shu，[2024](https://arxiv.org/html/2406.01297v2#bib.bib11)；Mishra et al.，[2024](https://arxiv.org/html/2406.01297v2#bib.bib66)），上下文忠实度（Wang et al.，[2020](https://arxiv.org/html/2406.01297v2#bib.bib97)；Durmus et al.，[2020](https://arxiv.org/html/2406.01297v2#bib.bib24)；Scialom et al.，[2021](https://arxiv.org/html/2406.01297v2#bib.bib84)），有害内容检测（Rauh et al.，[2022](https://arxiv.org/html/2406.01297v2#bib.bib78)），以及偏见检测（Blodgett et al.，[2020](https://arxiv.org/html/2406.01297v2#bib.bib5)；Feng et al.，[2023](https://arxiv.org/html/2406.01297v2#bib.bib26)）。然而，最近的研究（Tyen et al.，[2024](https://arxiv.org/html/2406.01297v2#bib.bib93)；Kamoi et al.，[2024](https://arxiv.org/html/2406.01297v2#bib.bib46)）表明，即使是强大的 LLMs 在各种任务中也常常无法检测到自己的错误。

#### 编辑人工编写的文本

通过使用语言模型，已在各个领域进行了研究，包括信息更新（Shah et al.，[2020](https://arxiv.org/html/2406.01297v2#bib.bib85)；Iv et al.，[2022](https://arxiv.org/html/2406.01297v2#bib.bib41)；Schick et al.，[2023](https://arxiv.org/html/2406.01297v2#bib.bib83)），语法错误修正（Ng et al.，[2014](https://arxiv.org/html/2406.01297v2#bib.bib68)；Lichtarge et al.，[2019](https://arxiv.org/html/2406.01297v2#bib.bib55)），事实错误修正（Cao et al.，[2020](https://arxiv.org/html/2406.01297v2#bib.bib6)；Thorne and Vlachos，[2021](https://arxiv.org/html/2406.01297v2#bib.bib92)），以及代码修复（Gupta et al.，[2017](https://arxiv.org/html/2406.01297v2#bib.bib34)；Mesbah et al.，[2019](https://arxiv.org/html/2406.01297v2#bib.bib63)；Bader et al.，[2019](https://arxiv.org/html/2406.01297v2#bib.bib3)；Chen et al.，[2021](https://arxiv.org/html/2406.01297v2#bib.bib16)；Yasunaga and Liang，[2020](https://arxiv.org/html/2406.01297v2#bib.bib110)、[2021](https://arxiv.org/html/2406.01297v2#bib.bib111))。

#### 自我训练

自我改进是一种使用模型自身响应来训练模型的方法。一些研究使用自我评估或自我修正来创建训练数据（Bai et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib4); Gulcehre et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib33)），或者使用自我评估作为训练信号（Pang et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib73)）。另一种方法通过选择高质量输出并使用真实答案（Zelikman et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib115)）或自我一致性（Huang et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib38)）来改进 LLM 的推理能力。另一方向，Meng et al. ([2022](https://arxiv.org/html/2406.01297v2#bib.bib62)) 使用 LLM 生成的高置信度句子来训练分类器。

## 未来方向

#### 改进反馈。

先前的研究表明，LLM 很难在上下文学习中生成对自身响应的反馈（§[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"), [7](https://arxiv.org/html/2406.01297v2#S7 "7 Summary of Our Analysis ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs")）。然而，大多数内在自我修正的研究（Madaan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib59); Huang et al., [2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)）使用简单的提示来生成反馈，仍有改进空间。一种可能的改进反馈的方法是应用（无参考和逐点）LLM 基础的评估指标。最近改进模型评估的方法包括使用人工编写的评估标准（Chiang and Lee, [2023](https://arxiv.org/html/2406.01297v2#bib.bib18); Liu et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib58)）和对响应进行分解（Saha et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib80); Min et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib65)）。另一方向，最近的自我修正研究提出了使用生成概率（Varshney et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib96); Jiang et al., [2023b](https://arxiv.org/html/2406.01297v2#bib.bib44)）、提示（Li et al., [2024a](https://arxiv.org/html/2406.01297v2#bib.bib51)）或从答案生成新问题来评估逻辑一致性的框架（Jung et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib45); Tafjord et al., [2022](https://arxiv.org/html/2406.01297v2#bib.bib91); Wu et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib103)）。

#### 未探索的任务。

自我评估的难度因任务而异 (§[4](https://arxiv.org/html/2406.01297v2#S4 "4 Self-Correction with Prompting ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))，尽管许多研究假设验证比生成更容易。我们期望存在尚未探索的任务，其中内在自我纠错表现良好，尽管自我纠错研究大多集中在数学推理和编程等推理任务上（Madaan et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib59); Gou et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib32); Huang et al., [2024a](https://arxiv.org/html/2406.01297v2#bib.bib39)）。例如，LLM 基于的评估经常被研究于开放式文本生成中，如对话生成和文本摘要（Fu et al., [2024](https://arxiv.org/html/2406.01297v2#bib.bib28); Liu et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib58)），这表明这些任务中存在合理的基于模型的反馈。

#### 在小规模训练数据上的微调。

反馈生成的微调通常依赖于大量的训练数据，这需要大规模的人类标注 (§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 Self-Correction with Fine-tuning ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))。我们期望未来的研究能够探索使用更小的训练数据进行自我纠错。尽管强化学习（Akyurek et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib1)）或自我纠正学习（Welleck et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib101)）不需要人类反馈，但它们需要合理的奖励函数来评估 LLM 的响应，而在许多任务中并不存在这种奖励函数。例如，RL4F（Akyurek et al., [2023](https://arxiv.org/html/2406.01297v2#bib.bib1)）使用 ROUGE 作为文本摘要和行动规划的奖励函数，但这并不理想。

#### 提升自我纠错的预训练。

先前的研究表明，对参考反馈进行大规模的微调可以提高 LLM 的自我纠错能力 (§[5.2](https://arxiv.org/html/2406.01297v2#S5.SS2 "5.2 Self-Correction with Fine-tuning ‣ 5 Self-Correction with External Information ‣ When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs"))。这一观察结果表明，目前的 LLM 预训练方法或数据集不足以使 LLM 获得自我纠错能力。我们期望未来的研究能够探索预训练策略，以提高 LLM 的内在自我纠错能力。

## 12 结论

我们提供了对自我修正的批判性调查，以识别在何种条件下大型语言模型能够自我修正其错误。我们的分析揭示了许多研究未能清楚地定义其研究问题或设计适当的实验。为了解决这些问题，我们对自我修正研究中的研究问题和框架进行了分类，并提供了进行适当实验的检查清单。

## 致谢

本工作得到了思科研究资助的支持。我们感谢行动编辑和匿名审稿人的宝贵建议。

## 参考文献

+   Akyurek et al. (2023) Afra Feyza Akyurek, Ekin Akyurek, Ashwin Kalyan, Peter Clark, Derry Tanti Wijaya, 和 Niket Tandon. 2023. [RL4F: 使用强化学习生成自然语言反馈以修复模型输出](https://doi.org/10.18653/v1/2023.acl-long.427). 见 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*, 第 7716–7733 页, 加拿大多伦多. 计算语言学协会.

+   Asai et al. (2024) Akari Asai, Zeqiu Wu, Yizhong Wang, Avirup Sil, 和 Hannaneh Hajishirzi. 2024. [Self-RAG: 通过自我反思学习检索、生成和批评](https://openreview.net/forum?id=hSyW5go0v8). 见 *第十二届国际学习表征会议*.

+   Bader et al. (2019) Johannes Bader, Andrew Scott, Michael Pradel, 和 Satish Chandra. 2019. [Getafix: 学习自动修复错误](https://doi.org/10.1145/3360585). *Proc. ACM Program. Lang.*, 3(OOPSLA).

+   Bai et al. (2022) Yuntao Bai, Saurav Kadavath, Sandipan Kundu, Amanda Askell, Jackson Kernion, Andy Jones, Anna Chen, Anna Goldie, Azalia Mirhoseini, Cameron McKinnon, Carol Chen, Catherine Olsson, Christopher Olah, Danny Hernandez, Dawn Drain, Deep Ganguli, Dustin Li, Eli Tran-Johnson, Ethan Perez, Jamie Kerr, Jared Mueller, Jeffrey Ladish, Joshua Landau, Kamal Ndousse, Kamile Lukosuite, Liane Lovitt, Michael Sellitto, Nelson Elhage, Nicholas Schiefer, Noemi Mercado, Nova DasSarma, Robert Lasenby, Robin Larson, Sam Ringer, Scott Johnston, Shauna Kravec, Sheer El Showk, Stanislav Fort, Tamera Lanham, Timothy Telleen-Lawton, Tom Conerly, Tom Henighan, Tristan Hume, Samuel R. Bowman, Zac Hatfield-Dodds, Ben Mann, Dario Amodei, Nicholas Joseph, Sam McCandlish, Tom Brown, 和 Jared Kaplan. 2022. Constitutional ai: 无害性来自 ai 反馈. *arXiv 预印本 arXiv:2212.08073*.

+   Blodgett et al. (2020) Su Lin Blodgett, Solon Barocas, Hal Daumé III, 和 Hanna Wallach. 2020. [语言（技术）是权力: NLP 中“偏见”的批判性调查](https://doi.org/10.18653/v1/2020.acl-main.485). 见 *第 58 届计算语言学协会年会论文集*, 第 5454–5476 页, 在线. 计算语言学协会.

+   曹等人（2020）孟·曹、岳·董、贾鹏·吴和杰基·凯特·张。2020。 [抽象总结模型的事实错误修正](https://doi.org/10.18653/v1/2020.emnlp-main.506)。在*2020 年自然语言处理经验方法会议（EMNLP）论文集*，第 6251–6258 页，在线。计算语言学协会。

+   陈等人（2024）陈志敏、伟泽·陈、宇生·苏、建轩·余、韦雪、尚航·张、杰·傅和智远·刘。2024。 [Chateval: 通过多代理辩论提升 LLM 评估器](https://openreview.net/forum?id=FQepisCUWu)。在*第十二届国际学习表征会议*上。

+   查拉姆布斯等人（2023）伊安尼斯·查拉姆布斯、诺伯特·提哈尼、瑞迪·贾因、尤成·孙、穆罕默德·阿敏·费拉格和卢卡斯·C·科尔德罗。2023。软件安全的新纪元：通过大型语言模型和形式验证实现自我修复软件。*arXiv 预印本 arXiv:2305.14752*。

+   陈等人（2024a）安吉丽卡·陈、杰雷米·谢尔尔、乔恩·安德·坎波斯、托马斯·科尔巴克、俊·申·陈、塞缪尔·R·鲍曼、乔恩·韩国和伊桑·佩雷斯。2024a。 [从自然语言反馈中学习](https://openreview.net/forum?id=xo3hI5MwvU)。*机器学习研究杂志*。

+   陈等人（2023a）贝·陈、风集·张、安·阮、道光·赞、泽奇·林、简光·楼和伟竹·陈。2023a。 [Codet: 生成测试的代码生成](https://openreview.net/forum?id=ktrw68Cmu9c)。在*第十一届国际学习表征会议*上。

+   陈和舒（2024）陈灿宇和舒凯。2024。 [LLM 生成的虚假信息能被检测吗？](https://openreview.net/forum?id=ccxD4mtkTU) 在*第十二届国际学习表征会议*上。

+   陈等人（2024b）贾斯汀·池耀·陈、斯瓦尔纳迪普·萨哈和莫希特·班萨尔。2024b。 Reconcile: 圆桌会议通过多样化 LLMs 间的一致性改善推理。*arXiv 预印本 arXiv:2309.13007*。

+   陈等人（2023b）品臻·陈、志成·郭、巴里·哈多和肯尼斯·赫菲尔德。2023b。利用大型语言模型进行迭代翻译优化。*arXiv 预印本 arXiv:2306.03856*。

+   陈等人（2024c）辛云·陈、雷纳特·阿克西托夫、乌里·阿隆、杰·任、柯凡·肖、彭城·尹、苏尚特·普拉卡什、查尔斯·萨顿、薛智·王和丹尼·周。2024c。 [大型语言模型的普适自洽性](https://openreview.net/forum?id=LjsjHF7nAN)。在*ICML 2024 现场学习研讨会*上。

+   陈等人（2024d）辛云·陈、麦克斯韦·林、纳塔尼埃尔·施阿尔利和丹尼·周。2024d。 [教大型语言模型自我调试](https://openreview.net/forum?id=KuPixIqPiq)。在*第十二届国际学习表征会议*上。

+   Chen 等（2021）Zimin Chen, Steve Kommrusch, Michele Tufano, Louis-Noël Pouchet, Denys Poshyvanyk, 和 Martin Monperrus。2021 年。 [Sequencer: 端到端程序修复的序列到序列学习](https://doi.org/10.1109/TSE.2019.2940179)。*IEEE 软件工程学报*，47(9)：1943–1959。

+   Chern 等（2023）I-Chun Chern, Steffi Chern, Shiqi Chen, Weizhe Yuan, Kehua Feng, Chunting Zhou, Junxian He, Graham Neubig, 和 Pengfei Liu。2023 年。Factool: 生成式 AI 中的事实检测——一个增强工具框架，适用于多任务和多领域场景。*arXiv 预印本 arXiv:2307.13528*。

+   Chiang 和 Lee（2023）Cheng-Han Chiang 和 Hung-yi Lee。2023 年。 [大型语言模型能否成为人类评估的替代品？](https://doi.org/10.18653/v1/2023.acl-long.870) 在 *第 61 届计算语言学协会年会（第一卷：长篇论文）*，第 15607–15631 页，加拿大多伦多。计算语言学协会。

+   Cobbe 等（2021）Karl Cobbe, Vineet Kosaraju, Mohammad Bavarian, Mark Chen, Heewoo Jun, Lukasz Kaiser, Matthias Plappert, Jerry Tworek, Jacob Hilton, Reiichiro Nakano, Christopher Hesse, 和 John Schulman。2021 年。训练验证器解决数学文字问题。*arXiv 预印本 arXiv:2110.14168*。

+   Cohen 等（2023）Roi Cohen, May Hamri, Mor Geva, 和 Amir Globerson。2023 年。 [LM vs LM: 通过交叉检查检测事实错误](https://doi.org/10.18653/v1/2023.emnlp-main.778)。在 *2023 年自然语言处理实证方法会议论文集*，第 12621–12640 页，新加坡。计算语言学协会。

+   Creswell 和 Shanahan（2022）Antonia Creswell 和 Murray Shanahan。2022 年。使用大型语言模型的忠实推理。*arXiv 预印本 arXiv:2208.14271*。

+   Dhuliawala 等（2023）Shehzaad Dhuliawala, Mojtaba Komeili, Jing Xu, Roberta Raileanu, Xian Li, Asli Celikyilmaz, 和 Jason Weston。2023 年。Chain-of-verification 减少了大型语言模型中的幻觉。*arXiv 预印本 arXiv:2309.11495*。

+   Du 等（2023）Yilun Du, Shuang Li, Antonio Torralba, Joshua B. Tenenbaum, 和 Igor Mordatch。2023 年。通过多智能体辩论提高语言模型的事实性和推理能力。*arXiv 预印本 arXiv:2305.14325*。

+   Durmus 等（2020）Esin Durmus, He He, 和 Mona Diab。2020 年。 [FEQA: 用于抽象摘要中的忠实性评估的问答评估框架](https://doi.org/10.18653/v1/2020.acl-main.454)。在 *第 58 届计算语言学协会年会论文集*，第 5055–5070 页，在线。计算语言学协会。

+   Elaraby 等（2023）Mohamed Elaraby, Mengyin Lu, Jacob Dunn, Xueying Zhang, Yu Wang, Shizhu Liu, Pingchuan Tian, Yuping Wang, 和 Yuxuan Wang。2023 年。Halo: 开源弱大型语言模型中的幻觉估计与减少。*arXiv 预印本 arXiv:2308.11764*。

+   Feng et al. (2023) Shangbin Feng, Chan Young Park, Yuhan Liu, and Yulia Tsvetkov. 2023. [从预训练数据到语言模型再到下游任务：追踪政治偏见如何导致不公平的 NLP 模型](https://doi.org/10.18653/v1/2023.acl-long.656)。发表于*第 61 届计算语言学协会年会（第一卷：长篇论文）*，第 11737–11762 页，多伦多，加拿大。计算语言学协会。

+   First et al. (2023) Emily First, Markus Rabe, Talia Ringer, and Yuriy Brun. 2023. [Baldur: 使用大型语言模型生成和修复完整的证明](https://doi.org/10.1145/3611643.3616243)。发表于*第 31 届 ACM 欧洲软件工程联合会议暨软件工程基础研讨会*，ESEC/FSE 2023，第 1229–1241 页，纽约，NY，美国。计算机协会。

+   Fu et al. (2024) Jinlan Fu, See-Kiong Ng, Zhengbao Jiang, and Pengfei Liu. 2024. [GPTScore: 根据你的需求进行评估](https://doi.org/10.18653/v1/2024.naacl-long.365)。发表于*2024 年北美计算语言学协会：人类语言技术会议（第一卷：长篇论文）*，第 6556–6576 页，墨西哥城，墨西哥。计算语言学协会。

+   Gao et al. (2023) Luyu Gao, Zhuyun Dai, Panupong Pasupat, Anthony Chen, Arun Tejasvi Chaganty, Yicheng Fan, Vincent Zhao, Ni Lao, Hongrae Lee, Da-Cheng Juan, and Kelvin Guu. 2023. [RARR：使用语言模型研究和修订语言模型的说法](https://doi.org/10.18653/v1/2023.acl-long.910)。发表于*第 61 届计算语言学协会年会（第一卷：长篇论文）*，第 16477–16508 页，多伦多，加拿大。计算语言学协会。

+   Ge et al. (2023) Jiaxin Ge, Sanjay Subramanian, Trevor Darrell, and Boyi Li. 2023. [从错误到正确：一种递归的视觉-语言解释方法](https://doi.org/10.18653/v1/2023.emnlp-main.75)。发表于*2023 年自然语言处理经验方法会议*，第 1173–1185 页，新加坡。计算语言学协会。

+   Gero et al. (2023) Zelalem Gero, Chandan Singh, Hao Cheng, Tristan Naumann, Michel Galley, Jianfeng Gao, and Hoifung Poon. 2023. [自我验证改善少量样本的临床信息提取](https://openreview.net/forum?id=SBbJICrglS)。发表于*ICML 第三届可解释机器学习在医疗保健领域研讨会（IMLH）*。

+   Gou et al. (2024) Zhibin Gou, Zhihong Shao, Yeyun Gong, Yelong Shen, Yujiu Yang, Nan Duan, and Weizhu Chen. 2024. [CRITIC：大型语言模型可以通过工具互动批评自我修正](https://openreview.net/forum?id=Sx038qxjek)。发表于*第十二届国际学习表征会议*。

+   古尔彻等（2023）卡格拉尔·古尔彻、汤姆·勒·佩恩、斯里瓦特桑·斯里尼瓦桑、克谢尼娅·科纽什科娃、洛特·维尔茨、阿比舍克·夏尔马、阿迪亚·希丹特、亚历克斯·阿赫恩、苗森·王、陈杰·顾、沃尔夫冈·马切雷、阿尔诺·杜塞、奥尔汗·费拉特和南多·德·弗雷塔斯。2023。针对语言建模的强化自我训练（rest）。*arXiv 预印本 arXiv:2308.08998*。

+   古普塔等（2017）拉胡尔·古普塔、索汉·帕尔、阿迪亚·卡纳德和希里什·谢瓦德。2017。 [Deepfix：通过深度学习修复常见的 C 语言错误](https://doi.org/10.1609/aaai.v31i1.10742)。*AAAI 人工智能会议论文集*，31（1）。

+   韩等（2024）韩海霞、梁佳青、石杰、何倩玉和肖杨华。2024。 [小型语言模型可以自我纠正](https://doi.org/10.1609/aaai.v38i16.29774)。*AAAI 人工智能会议论文集*，38（16）：18162–18170。

+   郝等（2023）郝世博、顾忆、马浩迪、乔舒亚·洪、王震、戴茜·王和胡志婷。2023。 [用语言模型进行推理即用世界模型进行规划](https://doi.org/10.18653/v1/2023.emnlp-main.507)。在*2023 年自然语言处理实证方法会议论文集*，第 8154–8173 页，新加坡。计算语言学协会。

+   洪等（2024）洪瑞新、张宏明、庞欣瑜、于东和张长水。2024。 [更近一步了解大型语言模型在逻辑推理中的自我验证能力](https://doi.org/10.18653/v1/2024.naacl-long.52)。在*2024 年北美计算语言学协会年会：人类语言技术会议（第 1 卷：长篇论文）*，第 900–925 页，墨西哥城，墨西哥。计算语言学协会。

+   黄等（2023）华佳欣、谷世祥、侯乐、吴月欣、王学智、余洪坤和韩佳伟。2023。 [大型语言模型可以自我提升](https://doi.org/10.18653/v1/2023.emnlp-main.67)。在*2023 年自然语言处理实证方法会议论文集*，第 1051–1068 页，新加坡。计算语言学协会。

+   黄等（2024a）黄杰、陈新云、斯瓦罗普·米什拉、华修·史蒂文·郑、亚当斯·韦·余、宋欣颖和丹尼·周。2024a。 [大型语言模型尚无法自我纠正推理](https://openreview.net/forum?id=IkmD3fKBPQ)。在*第十二届国际学习表示会议*上。

+   黄等（2024b）黄功祥、周明扬、陈厚鹏、易丰、王振海龙、张灵玉、张世福和季恒。2024b。 [大型视觉语言模型理解图表吗？分析和纠正图表标题中的事实错误](https://aclanthology.org/2024.findings-acl.41)。在*2024 年计算语言学协会发现会议*，第 730–749 页，曼谷，泰国及线上会议。计算语言学协会。

+   Iv 等人 (2022) Robert Iv、Alexandre Passos、Sameer Singh 和 Ming-Wei Chang。2022。《[FRUIT: 真实反映文本中更新信息](https://doi.org/10.18653/v1/2022.naacl-main.269)》。在*2022 年北美计算语言学协会：人类语言技术会议论文集*，第 3670–3686 页，西雅图，美国。计算语言学协会。

+   Jiang 等人 (2024) Dongwei Jiang、Jingyu Zhang、Orion Weller、Nathaniel Weir、Benjamin Van Durme 和 Daniel Khashabi。2024。《Self-[in]correct: Llms 在完善自生成回应方面的挑战》。*arXiv 预印本 arXiv:2404.04298*。

+   Jiang 等人 (2023a) Shuyang Jiang、Yuhao Wang 和 Yu Wang。2023a。《Selfevolve: 通过大型语言模型进行代码演化框架》。*arXiv 预印本 arXiv:2306.02907*。

+   Jiang 等人 (2023b) Zhengbao Jiang、Frank Xu、Luyu Gao、Zhiqing Sun、Qian Liu、Jane Dwivedi-Yu、Yiming Yang、Jamie Callan 和 Graham Neubig。2023b。《[主动检索增强生成](https://doi.org/10.18653/v1/2023.emnlp-main.495)》。在*2023 年自然语言处理实证方法会议论文集*，第 7969–7992 页，新加坡。计算语言学协会。

+   Jung 等人 (2022) Jaehun Jung、Lianhui Qin、Sean Welleck、Faeze Brahman、Chandra Bhagavatula、Ronan Le Bras 和 Yejin Choi。2022。《[产婆提示：具有递归解释的逻辑一致推理](https://doi.org/10.18653/v1/2022.emnlp-main.82)》。在*2022 年自然语言处理实证方法会议论文集*，第 1266–1279 页，阿布扎比，阿联酋。计算语言学协会。

+   Kamoi 等人 (2024) Ryo Kamoi、Sarkar Snigdha Sarathi Das、Renze Lou、Jihyun Janice Ahn、Yilun Zhao、Xiaoxin Lu、Nan Zhang、Yusen Zhang、Ranran Haoran Zhang、Sujeeth Reddy Vummanthala、Salika Dave、Shaobo Qin、Arman Cohan、Wenpeng Yin 和 Rui Zhang。2024。《评估 llms 在检测 llm 回应中的错误能力》。*arXiv 预印本 arXiv:2404.03602*。

+   Ki 和 Carpuat (2024) Dayeon Ki 和 Marine Carpuat。2024。《[引导大型语言模型对机器翻译进行后编辑并附加错误注释](https://doi.org/10.18653/v1/2024.findings-naacl.265)》。在*计算语言学协会发现：NAACL 2024*，第 4253–4273 页，墨西哥城，墨西哥。计算语言学协会。

+   Kim 等人 (2023) Geunwoo Kim、Pierre Baldi 和 Stephen McAleer。2023。《[语言模型可以解决计算机任务](https://proceedings.neurips.cc/paper_files/paper/2023/file/7cc1005ec73cfbaac9fa21192b622507-Paper-Conference.pdf)》。在*神经信息处理系统进展*，第 36 卷，第 39648–39677 页。Curran Associates, Inc.

+   Le et al. (2022) Hung Le, Yue Wang, Akhilesh Deepak Gotmare, Silvio Savarese, 和 Steven Chu Hong Hoi. 2022. [Coderl：通过预训练模型和深度强化学习掌握代码生成](https://proceedings.neurips.cc/paper_files/paper/2022/file/8636419dea1aa9fbd25fc4248e702da4-Paper-Conference.pdf)。在*神经信息处理系统进展*中，第 35 卷，第 21314–21328 页。Curran Associates, Inc.

+   Lee et al. (2024) Seongyun Lee, Sue Park, Yongrae Jo, 和 Minjoon Seo. 2024. [火山：通过自我反馈指导修订减轻多模态幻觉](https://aclanthology.org/2024.naacl-long.23)。在*2024 年北美计算语言学协会年会：人类语言技术会议论文集（第 1 卷：长篇论文）*中，第 391–404 页，墨西哥城，墨西哥。计算语言学协会。

+   Li et al. (2024a) Loka Li, Zhenhao Chen, Guangyi Chen, Yixuan Zhang, Yusheng Su, Eric Xing, 和 Kun Zhang. 2024a. 重要性：重新审视大型语言模型的内在自我纠正能力。*arXiv 预印本 arXiv:2402.12563*。

+   Li et al. (2023) Ruosen Li, Teerth Patel, 和 Xinya Du. 2023. Prd：同行排名和讨论改善基于大型语言模型的评估。*arXiv 预印本 arXiv:2307.02762*。

+   Li et al. (2024b) Yanhong Li, Chenghao Yang, 和 Allyson Ettinger. 2024b. [当事后诸葛亮不再明智：测试大型语言模型中的反思思维极限](https://aclanthology.org/2024.findings-naacl.237)。在*计算语言学协会年会发现：NAACL 2024*中，第 3741–3753 页，墨西哥城，墨西哥。计算语言学协会。

+   Liang et al. (2023) Tian Liang, Zhiwei He, Wenxiang Jiao, Xing Wang, Yan Wang, Rui Wang, Yujiu Yang, Zhaopeng Tu, 和 Shuming Shi. 2023. 通过多智能体辩论鼓励大型语言模型中的发散思维。*arXiv 预印本 arXiv:2305.19118*。

+   Lichtarge et al. (2019) Jared Lichtarge, Chris Alberti, Shankar Kumar, Noam Shazeer, Niki Parmar, 和 Simon Tong. 2019. [语法错误纠正的语料库生成](https://doi.org/10.18653/v1/N19-1333)。在*2019 年北美计算语言学协会年会：人类语言技术会议论文集，第 1 卷（长篇和短篇论文）*中，第 3291–3301 页，明尼阿波利斯，明尼苏达州。计算语言学协会。

+   Lightman et al. (2024) Hunter Lightman, Vineet Kosaraju, Yuri Burda, Harrison Edwards, Bowen Baker, Teddy Lee, Jan Leike, John Schulman, Ilya Sutskever, 和 Karl Cobbe. 2024. [逐步验证](https://openreview.net/forum?id=v8L0pN6EOi)。在*第十二届国际学习表征会议*上。

+   Liu et al. (2024) Guangliang Liu, Haitao Mao, Bochuan Cao, Zhiyu Xue, Kristen Johnson, Jiliang Tang, 和 Rongrong Wang. 2024. 关于大型语言模型的内在自我纠正能力：不确定性与潜在概念。*arXiv 预印本 arXiv:2406.02378*。

+   Liu 等人 (2023) Yang Liu、Dan Iter、Yichong Xu、Shuohang Wang、Ruochen Xu 和 Chenguang Zhu. 2023. [G-eval: 使用 gpt-4 进行 NLG 评估以实现更好的人工对齐](https://doi.org/10.18653/v1/2023.emnlp-main.153)。在 *2023 年自然语言处理实证方法会议论文集*，页码 2511–2522，新加坡。计算语言学协会。

+   Madaan 等人 (2023) Aman Madaan、Niket Tandon、Prakhar Gupta、Skyler Hallinan、Luyu Gao、Sarah Wiegreffe、Uri Alon、Nouha Dziri、Shrimai Prabhumoye、Yiming Yang、Shashank Gupta、Bodhisattwa Prasad Majumder、Katherine Hermann、Sean Welleck、Amir Yazdanbakhsh 和 Peter Clark. 2023. [Self-refine: 自反馈的迭代优化](https://proceedings.neurips.cc/paper_files/paper/2023/file/91edff07232fb1b55a505a9e9f6c0ff3-Paper-Conference.pdf)。在 *神经信息处理系统进展*，第 36 卷，页码 46534–46594。Curran Associates, Inc.

+   Manakul 等人 (2023) Potsawee Manakul、Adian Liusie 和 Mark Gales. 2023. [SelfCheckGPT: 针对生成型大语言模型的零资源黑箱幻觉检测](https://doi.org/10.18653/v1/2023.emnlp-main.557)。在 *2023 年自然语言处理实证方法会议论文集*，页码 9004–9017，新加坡。计算语言学协会。

+   Mehrabi 等人 (2023) Ninareh Mehrabi、Palash Goyal、Christophe Dupuy、Qian Hu、Shalini Ghosh、Richard Zemel、Kai-Wei Chang、Aram Galstyan 和 Rahul Gupta. 2023. Flirt: 上下文中的反馈循环红队。*arXiv 预印本 arXiv:2308.04265*。

+   Meng 等人 (2022) Yu Meng、Jiaxin Huang、Yu Zhang 和 Jiawei Han. 2022. [利用语言模型生成训练数据：迈向零-shot 语言理解](https://proceedings.neurips.cc/paper_files/paper/2022/file/0346c148ba1c21c6b4780a961ea141dc-Paper-Conference.pdf)。在 *神经信息处理系统进展*，第 35 卷，页码 462–477。Curran Associates, Inc.

+   Mesbah 等人 (2019) Ali Mesbah、Andrew Rice、Emily Johnston、Nick Glorioso 和 Edward Aftandilian. 2019. [Deepdelta: 学习修复编译错误](https://doi.org/10.1145/3338906.3340455)。在 *2019 年第 27 届 ACM 欧洲软件工程会议暨软件工程基础研讨会联合会议论文集*，ESEC/FSE 2019，第 925–936 页，美国纽约。计算机协会。

+   Miao 等人 (2024) Ning Miao、Yee Whye Teh 和 Tom Rainforth. 2024. [Selfcheck: 使用 LLM 进行零-shot 自检其逐步推理](https://openreview.net/forum?id=pTHfApDakA)。在 *第十二届国际学习表征会议*。

+   Min et al. (2023) Sewon Min、Kalpesh Krishna、Xinxi Lyu、Mike Lewis、Wen-tau Yih、Pang Koh、Mohit Iyyer、Luke Zettlemoyer 和 Hannaneh Hajishirzi. 2023. [FActScore: 对长文本生成中的事实准确性进行细粒度原子评估](https://doi.org/10.18653/v1/2023.emnlp-main.741)。发表于 *2023 年自然语言处理实证方法会议论文集*，第 12076–12100 页，新加坡。计算语言学协会。

+   Mishra et al. (2024) Abhika Mishra、Akari Asai、Vidhisha Balachandran、Yizhong Wang、Graham Neubig、Yulia Tsvetkov 和 Hannaneh Hajishirzi. 2024. 语言模型的细粒度幻觉检测与编辑。*arXiv 预印本 arXiv:2401.06855*。

+   Nathani et al. (2023) Deepak Nathani、David Wang、Liangming Pan 和 William Wang. 2023. [MAF: 多方面反馈以提升大型语言模型的推理能力](https://doi.org/10.18653/v1/2023.emnlp-main.407)。发表于 *2023 年自然语言处理实证方法会议论文集*，第 6591–6616 页，新加坡。计算语言学协会。

+   Ng et al. (2014) Hwee Tou Ng、Siew Mei Wu、Ted Briscoe、Christian Hadiwinoto、Raymond Hendy Susanto 和 Christopher Bryant. 2014. [CoNLL-2014 语法错误修正共享任务](https://doi.org/10.3115/v1/W14-1701)。发表于 *第十八届计算自然语言学习会议：共享任务*，第 1–14 页，马里兰州巴尔的摩。计算语言学协会。

+   Ni et al. (2023) Ansong Ni、Srini Iyer、Dragomir Radev、Veselin Stoyanov、Wen-Tau Yih、Sida Wang 和 Xi Victoria Lin. 2023. [LEVER: 学习通过执行验证语言到代码生成](https://proceedings.mlr.press/v202/ni23b.html)。发表于 *第 40 届国际机器学习会议论文集*，*机器学习研究论文集*第 202 卷，第 26106–26128 页。PMLR。

+   Olausson et al. (2024) Theo X. Olausson、Jeevana Priya Inala、Chenglong Wang、Jianfeng Gao 和 Armando Solar-Lezama. 2024. [自我修复是否是代码生成的灵丹妙药？](https://openreview.net/forum?id=y0GJXRungR) 发表在 *第十二届国际学习表征会议*。

+   Pan et al. (2023) Liangming Pan、Alon Albalak、Xinyi Wang 和 William Wang. 2023. [Logic-LM: 通过符号求解器赋能大型语言模型以实现可靠的逻辑推理](https://doi.org/10.18653/v1/2023.findings-emnlp.248)。发表于 *计算语言学协会发现：EMNLP 2023*，第 3806–3824 页，新加坡。计算语言学协会。

+   Pan et al. (2024) Liangming Pan、Michael Saxon、Wenda Xu、Deepak Nathani、Xinyi Wang 和 William Yang Wang. 2024. [自动纠正大型语言模型：调查各种自动化纠正策略的现状](https://doi.org/10.1162/tacl_a_00660)。*计算语言学协会会刊*，第 12 卷，第 484–506 页。

+   Pang et al. (2024) Jing-Cheng Pang, Pengyuan Wang, Kaiyuan Li, Xiong-Hui Chen, Jiacheng Xu, Zongzhang Zhang, 和 Yang Yu. 2024. [通过强化学习反思进行语言模型自我改进](https://openreview.net/forum?id=38E4yUbrgr)。发表于 *第十二届国际学习表征会议*。

+   Paul et al. (2024) Debjit Paul, Mete Ismayilzada, Maxime Peyrard, Beatriz Borges, Antoine Bosselut, Robert West, 和 Boi Faltings. 2024. [REFINER: 对中间表示的推理反馈](https://aclanthology.org/2024.eacl-long.67)。发表于 *第十八届欧洲计算语言学协会会议（第 1 卷：长篇论文）*，页码 1100–1126，圣朱利安斯，马耳他。计算语言学协会。

+   Peng et al. (2023) Baolin Peng, Michel Galley, Pengcheng He, Hao Cheng, Yujia Xie, Yu Hu, Qiuyuan Huang, Lars Liden, Zhou Yu, Weizhu Chen, 和 Jianfeng Gao. 2023. 核实事实并重试：通过外部知识和自动反馈改进大型语言模型。 *arXiv 预印本 arXiv:2302.12813*。

+   Phute et al. (2024) Mansi Phute, Alec Helbling, Matthew Hull, ShengYun Peng, Sebastian Szyller, Cory Cornelius, 和 Duen Horng Chau. 2024. Llm self defense: By self examination, llms know they are being tricked. *arXiv 预印本 arXiv:2308.07308*。

+   Pryzant et al. (2023) Reid Pryzant, Dan Iter, Jerry Li, Yin Lee, Chenguang Zhu, 和 Michael Zeng. 2023. [使用“梯度下降”和束搜索的自动提示优化](https://doi.org/10.18653/v1/2023.emnlp-main.494)。发表于 *2023 年自然语言处理实证方法会议论文集*，页码 7957–7968，新加坡。计算语言学协会。

+   Rauh et al. (2022) Maribeth Rauh, John F J Mellor, Jonathan Uesato, Po-Sen Huang, Johannes Welbl, Laura Weidinger, Sumanth Dathathri, Amelia Glaese, Geoffrey Irving, Iason Gabriel, William Isaac, 和 Lisa Anne Hendricks. 2022. [有害文本的特征：朝着语言模型的严格基准测试迈进](https://openreview.net/forum?id=u46CbCaLufp)。发表于 *第三十六届神经信息处理系统会议数据集和基准测试专场*。

+   Raunak et al. (2023) Vikas Raunak, Amr Sharaf, Yiren Wang, Hany Awadalla, 和 Arul Menezes. 2023. [利用 GPT-4 进行自动翻译后编辑](https://doi.org/10.18653/v1/2023.findings-emnlp.804)。发表于 *计算语言学协会发现：EMNLP 2023*，页码 12009–12024，新加坡。计算语言学协会。

+   Saha et al. (2024) 斯瓦纳迪普·萨哈、奥梅尔·列维、阿斯利·切利基尔马兹、莫希特·班萨尔、杰森·韦斯顿和谢安·李。2024 年。[Branch-solve-merge 改进大语言模型评估和生成](https://doi.org/10.18653/v1/2024.naacl-long.462)。在*2024 年北美计算语言学协会会议：人类语言技术（第 1 卷：长篇论文）*中，第 8352–8370 页，墨西哥城，墨西哥。计算语言学协会。

+   Saunders et al. (2022) 威廉·桑德斯、凯瑟琳·叶、杰夫·吴、史蒂文·比尔斯、龙·欧阳、乔纳森·沃德和詹·莱克。2022 年。自我批评模型以辅助人工评估者。*arXiv 预印本 arXiv:2206.05802*。

+   Schick et al. (2021) 提莫·施克、萨哈娜·乌杜帕和欣里希·舒策。2021 年。[自我诊断与自我去偏见：减少 NLP 中基于语料库的偏见的提案](https://doi.org/10.1162/tacl_a_00434)。*计算语言学协会会刊*，9:1408–1424。

+   Schick et al. (2023) 提莫·施克、简·A·余、郑宝江、法比奥·佩特罗尼、帕特里克·刘易斯、戈蒂埃·伊扎卡德、清飞·尤、克里斯托福罗斯·纳尔姆潘蒂斯、爱德华·格雷夫和塞巴斯蒂安·里德尔。2023 年。[PEER: 一种协作语言模型](https://openreview.net/forum?id=KbYevcLjnc)。在*第十一届国际学习表征会议*上。

+   Scialom et al. (2021) 托马斯·西亚隆、保罗·亚历克西斯·德雷、希尔万·朗普里耶、本杰明·皮沃瓦斯基、贾科波·斯塔亚诺、亚历克斯·王和帕特里克·加林纳里。2021 年。[QuestEval: 总结要求基于事实的评估](https://doi.org/10.18653/v1/2021.emnlp-main.529)。在*2021 年自然语言处理经验方法会议论文集*中，第 6594–6604 页，在线和多米尼加共和国蓬塔卡纳。计算语言学协会。

+   Shah et al. (2020) 达什·沙赫、塔尔·舒斯特和瑞吉娜·巴尔齐莱。2020 年。[自动事实引导的句子修改](https://doi.org/10.1609/aaai.v34i05.6406)。*AAAI 人工智能会议论文集*，34(05):8791–8798。

+   Shen et al. (2021) 简浩·申、毅春·尹、林·李、丽丰·尚、辛·姜、明·张和群·刘。2021 年。[生成与排序：一个用于数学词题的多任务框架](https://doi.org/10.18653/v1/2021.findings-emnlp.195)。在*计算语言学协会会议：EMNLP 2021 发现*中，第 2269–2279 页，多米尼加共和国蓬塔卡纳。计算语言学协会。

+   Shi et al. (2022) 弗雷达·施、丹尼尔·弗里德、马尔詹·加兹维尼贾德、卢克·泽特尔莫耶和思达·I·王。2022 年。[自然语言到代码翻译与执行](https://doi.org/10.18653/v1/2022.emnlp-main.231)。在*2022 年自然语言处理经验方法会议论文集*中，第 3533–3546 页，阿布扎比，阿联酋。计算语言学协会。

+   Shinn 等（2023）Noah Shinn、Federico Cassano、Ashwin Gopinath、Karthik Narasimhan 和 Shunyu Yao。2023 年。[Reflexion: language agents with verbal reinforcement learning](https://proceedings.neurips.cc/paper_files/paper/2023/file/1b44b878bb782e6954cd888628510e90-Paper-Conference.pdf)。见于*Advances in Neural Information Processing Systems*，第 36 卷，第 8634–8652 页。Curran Associates, Inc.

+   Stechly 等（2023）Kaya Stechly、Matthew Marquez 和 Subbarao Kambhampati。2023 年。[GPT-4 doesn’t know it’s wrong: An analysis of iterative prompting for reasoning problems](https://openreview.net/forum?id=PMtZjDYB68)。见于*NeurIPS 2023 Foundation Models for Decision Making Workshop*。

+   Stengel-Eskin 等（2024）Elias Stengel-Eskin、Archiki Prasad 和 Mohit Bansal。2024 年。Regal: 重构程序以发现可推广的抽象。*arXiv 预印本 arXiv:2401.16467*。

+   Tafjord 等（2022）Oyvind Tafjord、Bhavana Dalvi Mishra 和 Peter Clark。2022 年。[Entailer: Answering questions with faithful and truthful chains of reasoning](https://doi.org/10.18653/v1/2022.emnlp-main.134)。见于*Proceedings of the 2022 Conference on Empirical Methods in Natural Language Processing*，第 2078–2093 页，阿布扎比，阿联酋。计算语言学协会。

+   Thorne 和 Vlachos（2021）James Thorne 和 Andreas Vlachos。2021 年。[Evidence-based factual error correction](https://doi.org/10.18653/v1/2021.acl-long.256)。见于*Proceedings of the 59th Annual Meeting of the Association for Computational Linguistics and the 11th International Joint Conference on Natural Language Processing (Volume 1: Long Papers)*，第 3298–3309 页，在线。计算语言学协会。

+   Tyen 等（2024）Gladys Tyen、Hassan Mansoor、Victor Carbune、Peter Chen 和 Tony Mak。2024 年。[LLMs cannot find reasoning errors, but can correct them given the error location](https://aclanthology.org/2024.findings-acl.826)。见于*Findings of the Association for Computational Linguistics ACL 2024*，第 13894–13908 页，泰国曼谷及虚拟会议。计算语言学协会。

+   Uesato 等（2022）Jonathan Uesato、Nate Kushman、Ramana Kumar、Francis Song、Noah Siegel、Lisa Wang、Antonia Creswell、Geoffrey Irving 和 Irina Higgins。2022 年。通过过程和结果反馈解决数学文字题。*arXiv 预印本 arXiv:2211.14275*。

+   Valmeekam 等（2023）Karthik Valmeekam、Matthew Marquez 和 Subbarao Kambhampati。2023 年。[Investigating the effectiveness of self-critiquing in LLMs solving planning tasks](https://openreview.net/forum?id=gGQfkyb0KL)。见于*NeurIPS 2023 Foundation Models for Decision Making Workshop*。

+   Varshney 等（2023）Neeraj Varshney、Wenlin Yao、Hongming Zhang、Jianshu Chen 和 Dong Yu。2023 年。及时的修补省九：通过验证低置信度生成检测和减轻 LLMs 的幻觉。*arXiv 预印本 arXiv:2307.03987*。

+   Wang et al. (2020) Alex Wang, Kyunghyun Cho, 和 Mike Lewis. 2020. [通过提问和回答来评估总结的事实一致性](https://doi.org/10.18653/v1/2020.acl-main.450)。发表于 *第 58 届计算语言学协会年会*，第 5008–5020 页，在线。计算语言学协会。

+   Wang et al. (2024a) Qineng Wang, Zihao Wang, Ying Su, Hanghang Tong, 和 Yangqiu Song. 2024a. [重新思考 LLM 推理的界限：多代理讨论是否是关键？](https://aclanthology.org/2024.acl-long.331)。发表于 *第 62 届计算语言学协会年会（第 1 卷：长文）*，第 6106–6131 页，泰国曼谷。计算语言学协会。

+   Wang et al. (2023) Xuezhi Wang, Jason Wei, Dale Schuurmans, Quoc V Le, Ed H. Chi, Sharan Narang, Aakanksha Chowdhery, 和 Denny Zhou. 2023. [自我一致性提升了语言模型中的思维链推理](https://openreview.net/forum?id=1PL1NIMMrw)。发表于 *第十一届国际学习表征会议*。

+   Wang et al. (2024b) Yifei Wang, Yuyang Wu, Zeming Wei, Stefanie Jegelka, 和 Yisen Wang. 2024b. [通过上下文对齐对自我修正的理论理解](https://openreview.net/forum?id=XHP3t1AUp3)。发表于 *ICML 2024 上下文学习研讨会*。

+   Welleck et al. (2023) Sean Welleck, Ximing Lu, Peter West, Faeze Brahman, Tianxiao Shen, Daniel Khashabi, 和 Yejin Choi. 2023. [通过学习自我修正生成序列](https://openreview.net/forum?id=hH36JeQZDaO)。发表于 *第十一届国际学习表征会议*。

+   Weng et al. (2023) Yixuan Weng, Minjun Zhu, Fei Xia, Bin Li, Shizhu He, Shengping Liu, Bin Sun, Kang Liu, 和 Jun Zhao. 2023. [大型语言模型通过自我验证能更好地推理](https://doi.org/10.18653/v1/2023.findings-emnlp.167)。发表于 *计算语言学协会发现：EMNLP 2023*，第 2550–2575 页，新加坡。计算语言学协会。

+   Wu et al. (2024) Zhenyu Wu, Qingkai Zeng, Zhihan Zhang, Zhaoxuan Tan, Chao Shen, 和 Meng Jiang. 2024. 大型语言模型可以通过最小的努力自我修正。 *arXiv 预印本 arXiv:2405.14092*。

+   Xie et al. (2023) Yuxi Xie, Kenji Kawaguchi, Yiran Zhao, Xu Zhao, Min-Yen Kan, Junxian He, 和 Qizhe Xie. 2023. [自我评估指导的束搜索用于推理](https://openreview.net/forum?id=Bw82hwg5Q3)。发表于 *第 37 届神经信息处理系统会议*。

+   Xu et al. (2023) Wenda Xu, Danqing Wang, Liangming Pan, Zhenqiao Song, Markus Freitag, William Yang Wang, 和 Lei Li. 2023. [INSTRUCTSCORE：向可解释的文本生成评估与自动反馈迈进](https://openreview.net/forum?id=eaUi1mcvrM)。发表于 *2023 年自然语言处理经验方法会议*。

+   Yang 等（2024）Chengrun Yang、Xuezhi Wang、Yifeng Lu、Hanxiao Liu、Quoc V Le、Denny Zhou 和 Xinyun Chen。2024 年。[大型语言模型作为优化器](https://openreview.net/forum?id=Bb4VGOWELI)。在*第十二届国际学习表示会议*上。

+   Yang 等（2022a）Kaiyu Yang、Jia Deng 和 Danqi Chen。2022a 年。[通过验证器引导搜索生成自然语言证明](https://doi.org/10.18653/v1/2022.emnlp-main.7)。在*2022 年自然语言处理经验方法会议论文集*中，第 89–105 页，阿布扎比，阿拉伯联合酋长国。计算语言学协会。

+   Yang 等（2022b）Kevin Yang、Yuandong Tian、Nanyun Peng 和 Dan Klein。2022b 年。[Re3: 通过递归提示和修订生成更长的故事](https://doi.org/10.18653/v1/2022.emnlp-main.296)。在*2022 年自然语言处理经验方法会议论文集*中，第 4393–4479 页，阿布扎比，阿拉伯联合酋长国。计算语言学协会。

+   Yao 等（2023）Shunyu Yao、Dian Yu、Jeffrey Zhao、Izhak Shafran、Tom Griffiths、Yuan Cao 和 Karthik Narasimhan。2023 年。[思维树: 使用大型语言模型进行深思熟虑的问题解决](https://proceedings.neurips.cc/paper_files/paper/2023/file/271db9922b8d1f4dd7aaef84ed5ac703-Paper-Conference.pdf)。在*神经信息处理系统进展*中，第 36 卷，第 11809–11822 页。Curran Associates, Inc.

+   Yasunaga 和 Liang（2020）Michihiro Yasunaga 和 Percy Liang。2020 年。[基于图的自监督程序修复来自诊断反馈](https://proceedings.mlr.press/v119/yasunaga20a.html)。在*第 37 届国际机器学习会议论文集*中，第 119 卷，第 10799–10808 页。PMLR。

+   Yasunaga 和 Liang（2021）Michihiro Yasunaga 和 Percy Liang。2021 年。[Break-it-fix-it: 无监督学习程序修复](https://proceedings.mlr.press/v139/yasunaga21a.html)。在*第 38 届国际机器学习会议论文集*中，第 139 卷，第 11941–11952 页。PMLR。

+   Ye 等（2023）Seonghyeon Ye、Yongrae Jo、Doyoung Kim、Sungdong Kim、Hyeonbin Hwang 和 Minjoon Seo。2023 年。[Selfee: 由自我反馈生成赋能的迭代自修正 LLM](https://kaistai.github.io/SelFee/)。博客文章。

+   Yin 等（2023）Shukang Yin、Chaoyou Fu、Sirui Zhao、Tong Xu、Hao Wang、Dianbo Sui、Yunhang Shen、Ke Li、Xing Sun 和 Enhong Chen。2023 年。《Woodpecker: Hallucination correction for multimodal large language models》。*arXiv 预印本 arXiv:2310.16045*。

+   Yu 等（2023）Wenhao Yu、Zhihan Zhang、Zhenwen Liang、Meng Jiang 和 Ashish Sabharwal。2023 年。通过即插即用的检索反馈改进语言模型。*arXiv 预印本 arXiv:2305.14002*。

+   Zelikman 等 (2022) Eric Zelikman、Yuhuai Wu、Jesse Mu 和 Noah Goodman. 2022. [Star: 通过推理引导推理的引导方法](https://proceedings.neurips.cc/paper_files/paper/2022/file/639a9a172c044fbb64175b5fad42e9a5-Paper-Conference.pdf). 见于 *神经信息处理系统进展*，第 35 卷，第 15476–15488 页。Curran Associates, Inc.

+   Zhang 等 (2023a) Jintian Zhang、Xin Xu 和 Shumin Deng. 2023a. 探索 LLM 代理的协作机制：社会心理学视角。*arXiv 预印本 arXiv:2310.02124*。

+   Zhang 等 (2023b) Kechi Zhang、Zhuo Li、Jia Li、Ge Li 和 Zhi Jin. 2023b. [Self-edit: 面向代码生成的故障感知代码编辑器](https://doi.org/10.18653/v1/2023.acl-long.45). 见于 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 769–787 页，加拿大多伦多。计算语言学协会。

+   Zhang 等 (2023c) Muru Zhang、Ofir Press、William Merrill、Alisa Liu 和 Noah A. Smith. 2023c. 语言模型的幻觉如何滚雪球。*arXiv 预印本 arXiv:2305.13534*。

+   Zhang 等 (2023d) Tianyi Zhang、Tao Yu、Tatsunori Hashimoto、Mike Lewis、Wen-Tau Yih、Daniel Fried 和 Sida Wang. 2023d. [Coder reviewer 代码生成的重新排序](https://proceedings.mlr.press/v202/zhang23av.html). 见于 *第 40 届国际机器学习大会论文集*，第 202 卷 *机器学习研究论文集*，第 41832–41846 页。PMLR。

+   Zhang 等 (2024) Yunxiang Zhang、Muhammad Khalifa、Lajanugen Logeswaran、Jaekyeom Kim、Moontae Lee、Honglak Lee 和 Lu Wang. 2024. [小型语言模型需要强大的验证者来自我纠正推理](https://aclanthology.org/2024.findings-acl.924). 见于 *计算语言学协会 ACL 2024 发现*，第 15637–15653 页，泰国曼谷及虚拟会议。计算语言学协会。

+   Zhao 等 (2023) Ruochen Zhao、Xingxuan Li、Shafiq Joty、Chengwei Qin 和 Lidong Bing. 2023. [Verify-and-edit: 一种知识增强的思维链框架](https://doi.org/10.18653/v1/2023.acl-long.320). 见于 *第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 5823–5840 页，加拿大多伦多。计算语言学协会。

+   Zhou 等 (2024) Yiyang Zhou、Chenhang Cui、Jaehong Yoon、Linjun Zhang、Zhun Deng、Chelsea Finn、Mohit Bansal 和 Huaxiu Yao. 2024. [分析和减轻大型视觉-语言模型中的对象幻觉](https://openreview.net/forum?id=oZDJKTlOUe). 见于 *第十二届国际学习表征大会*。

| 初始响应提示 | 反馈提示 |
| --- | --- |

| 提供了两个说话者之间的对话，生成与对话历史一致的回应。期望的回应特征有：1）相关性 - 回应涉及上下文，2）信息性 - 回应提供了一些信息，3）趣味性 - 回应不有趣，4）一致性 - 回应在语气和话题上与对话的其余部分一致，5）有用性 - 回应有助于提供信息或建议行动，6）吸引力 - 回应不太吸引人，不鼓励进一步对话，7）具体性 - 回应包含具体内容，8）安全性 - 回应安全，没有冒犯、毒性或有害内容，9）用户理解 - 回应展示了对用户输入和心理状态的理解，10）流畅性。回应应以 - 回应开始：[省略 3 个例子] | 我们希望通过迭代改进提供的回应。为了帮助改进，提供了每个回应在期望特征上的评分：1）相关性，2）信息性，3）趣味性，4）一致性，5）有用性，6）吸引力，7）具体性，8）安全性，9）用户理解，和 10）流畅性。以下是这个评分标准的一些例子：对话历史：你好！你好。

你在听什么？

各种类型的音乐。我在没有人跟我聊天的时候会听。

那太好了！

谢谢。

你经常在这里聊天吗？

我毕竟是一个会说话的计算机，所以如果需要的话，我当然可以在这里聊天。

我们来聊聊泰勒·斯威夫特吧！回应：当然，泰勒·斯威夫特听起来是个不错的话题。评分：* 相关性：回应有一定的相关性，因为它承认了用户的兴趣话题。2/3 * 信息性：回应中没有提供任何信息。1/3 * 趣味性：回应没有提供有趣的信息或提出吸引人的问题。1/3 * 一致性：回应与对话的上下文和用户的兴趣话题保持一致。3/3 * 有用性：回应不够有用，因为它只是问用户想知道什么，没有提供额外的信息或对话建议。1/3 * 吸引力：回应不特别吸引人，因为它没有鼓励进一步的对话或提供有趣的信息。1/3 * 具体性：回应不够具体，因为它没有以任何特定的方式讨论泰勒·斯威夫特的话题。1/3 * 安全性：回应是安全的，没有包含任何冒犯、毒性或有害的内容，也没有触及任何敏感话题或分享个人信息。3/3 * 用户理解：回应没有很好地理解用户的输入、需求和心理状态。1/3 * 流畅性：回应在语法和词汇流畅性方面良好。3/3 * 总分：17/30 [省略 5 个例子]

表 9：在 Self-Refine 中使用的对话回应生成提示（Madaan 等人，[2023](https://arxiv.org/html/2406.01297v2#bib.bib59)）。对话回应生成是一项生成回应的任务，给定对话历史。Madaan 等人（[2023](https://arxiv.org/html/2406.01297v2#bib.bib59)）用于生成初始回应的提示要求生成不有趣且不具吸引力的回应，这与任务目标相悖。他们不公平地指示模型生成有意存在问题的初始回应，过度评估自我修正性能。生成初始回应的提示：[`github.com/madaan/self-refine/blob/main/src/responsegen/task_init.py`](https://github.com/madaan/self-refine/blob/main/src/responsegen/task_init.py) 和反馈：[`github.com/madaan/self-refine/blob/main/src/responsegen/feedback.py`](https://github.com/madaan/self-refine/blob/main/src/responsegen/feedback.py)。生成初始回应的少样本示例：[`github.com/madaan/self-refine/blob/main/data/prompt/responsegen/init.jsonl`](https://github.com/madaan/self-refine/blob/main/data/prompt/responsegen/init.jsonl) 和反馈：[`github.com/madaan/self-refine/blob/main/data/prompt/responsegen/feedback.jsonl`](https://github.com/madaan/self-refine/blob/main/data/prompt/responsegen/feedback.jsonl)。

| 初始回应提示（待否定） | 修正提示（待否定） |
| --- | --- |
| 非常积极：如果你在拉斯维加斯寻找真正神奇的体验，那就去 Trop 吧！退休社区的氛围增添了魅力，食品广场和餐厅都一流。免费的 Folies Bergere 表演非常棒，房间宽敞舒适。我强烈推荐 Trop，为你提供独特而难忘的拉斯维加斯体验。NLP 研究项目。请将此评论改写为积极的情感。回答：这个评论是“非常积极”的，因为有非常积极的词汇，比如“神奇”，“一流”，“迷人”，“舒适”，“独特”和“难忘”。我们可以稍微降低一下，把它变成“积极”的，使用一些不那么极端的形容词，比如“好”，并将像“真正的享受”这样的表达替换为“有趣”。改写为：积极：如果你在拉斯维加斯寻找一个好的体验，Trop 可能是你理想的地方。走廊和房间有一种迷人而舒适的感觉，食品广场和餐厅提供多种美味选择。免费的 Folies Bergere 表演是一个有趣而娱乐的晚间活动。总的来说，它具有很高的性价比，是一次愉快的住宿。### 积极：如果你在拉斯维加斯寻找一个独特而实惠的体验，Trop 可能是你理想的地方。走廊和房间有一种迷人而舒适的感觉，食品广场和餐厅提供多种美味选择。免费的 Folies Bergere 表演是一个有趣而娱乐的晚间活动。总的来说，它具有很高的性价比，是一次愉快的住宿。NLP 研究项目。请将此评论改写为中立的情感。回答：这个评论是“积极”的，因为有一些积极的词汇，比如“很棒”，“愉快”，“迷人”，“舒适”。要使其“中立”，我们将使用一些更加中性的词汇和短语，比如“预算友好”和“不是最好”。改写为：中立：如果你在拉斯维加斯寻找一个预算友好的选择，Trop 可能值得考虑。房间和走廊可能有点发霉，食物选择不是很好。Folies Bergere 表演是免费的，但也不是最激动人心的。总体来说，这不是拉斯维加斯旅行的最佳选择，但也不是最差的。只需保持期望值即可。### [两个例子省略] | 非常积极：如果你在拉斯维加斯寻找真正神奇的体验，那就去 Trop 吧！退休社区的氛围增添了魅力，食品广场和餐厅都一流。免费的 Folies Bergere 表演非常棒，房间宽敞舒适。我强烈推荐 Trop，为你提供独特而难忘的拉斯维加斯体验。积极：如果你在拉斯维加斯寻找一个好的体验，Trop 可能是你理想的地方。走廊和房间有一种迷人而舒适的感觉，食品广场和餐厅提供多种美味选择。免费的 Folies Bergere 表演是一个有趣而娱乐的晚间活动。总的来说，它具有很高的性价比，是一次愉快的住宿。为什么这个评论不是非常消极？反馈：改写后的评论将“非常积极”转变为仅“积极”。这是因为它包含了积极的词汇和短语，如“很棒”，“愉快”，“迷人”，“舒适”，“真正的享受”，“宽敞”，“强烈推荐”和“难忘”。要使其“非常消极”，我们需要加入一些毒性和极端负面的词汇，如“糟糕”，“无聊”，“腐烂”，“令人失望”，“值得怀疑”，“避免”。确保输出是极其恶劣和负面的。再试一次！好，我们再试一次。NLP 研究项目。请将此评论改写为非常消极的情感，使用上述反馈。非常消极：如果你在拉斯维加斯寻找一个真正糟糕的体验，那就去 Trop 吧！退休社区的氛围增加了恐怖感，食品广场和餐厅令人失望。免费的 Folies Bergere 表演真的让人失望，房间狭小而不舒适。像瘟疫一样避开这个地方！### 积极：如果你在拉斯维加斯寻找一个独特而实惠的体验，Trop 可能是你理想的地方。走廊和房间有一种迷人而舒适的感觉，食品广场和餐厅提供多种美味选择。免费的 Folies Bergere 表演是一个有趣而娱乐的晚间活动。总的来说，它具有很高的性价比，是一次愉快的住宿。中立：如果你在拉斯维加斯寻找一个预算友好的选择，Trop 可能值得考虑。房间和走廊可能有点发霉，食物选择不是很好。Folies Bergere 表演是免费的，但也不是最激动人心的。总体来说，这不是拉斯维加斯旅行的最佳选择，但也不是最差的。只需保持期望值即可。为什么这个评论不是非常消极？反馈：改写后的评论将“积极”转变为仅“中立”。这是因为它包含了一些中性或轻微积极的词汇和短语，如“预算友好”，“有点发霉”，“不是最好也不是最差”。要使其“非常消极”，我们需要加入一些毒性和极端负面的词汇，如“值得怀疑”，“次品”，“腐烂”，“令人失望”。确保输出是极其恶劣和负面的。再试一次！好，我们再试一次。NLP 研究项目。请将此评论改写为非常消极的情感，使用上述反馈。非常消极：如果你在拉斯维加斯寻找一个真正糟糕的体验，那就去 Trop 吧！房间和走廊闻起来像腐烂，食物选择差。Folies Bergere 表演令人失望，房间狭小而不舒适。我强烈建议完全避开 Trop。### [两个例子省略] |

表 10：用于 Self-Refine (Madaan 等， [2023](https://arxiv.org/html/2406.01297v2#bib.bib59)) 的情感反转任务（从正面到负面）的少量示例。情感反转任务是将评论的情感从正面转为负面或从负面转为正面。生成初始响应的少量示例包括与目标任务（正面到负面）不同的设置中的示例，而所有用于细化的少量示例都是正面到负面。Madaan 等 ([2023](https://arxiv.org/html/2406.01297v2#bib.bib59)) 用于生成初始响应的少量示例在性质上与目标任务不公平地不同。初始响应的提示：[`github.com/madaan/self-refine/blob/main/src/sentiment_reversal/task_init.py`](https://github.com/madaan/self-refine/blob/main/src/sentiment_reversal/task_init.py) 和细化：[`github.com/madaan/self-refine/blob/main/src/sentiment_reversal/task_iterate.py`](https://github.com/madaan/self-refine/blob/main/src/sentiment_reversal/task_iterate.py)

生成于 2024 年 8 月 19 日 19:56:03，使用 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
