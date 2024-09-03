<!--yml

类别：未分类

日期：2024-09-03 17:29:35

-->

# 当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析

> 来源：[`arxiv.org/html/2405.10255`](https://arxiv.org/html/2405.10255)

1.  [1 介绍](https://arxiv.org/html/2405.10255v1#S1 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中")

1.  [2 背景](https://arxiv.org/html/2405.10255v1#S2 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中")

    1.  [2.1 3D 表示](https://arxiv.org/html/2405.10255v1#S2.SS1 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 2 背景")

    1.  [2.2 大语言模型（LLM）](https://arxiv.org/html/2405.10255v1#S2.SS2 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 2 背景")

        1.  [2.2.1 LLM 架构](https://arxiv.org/html/2405.10255v1#S2.SS2.SSS1 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 2.2 大语言模型（LLM） ‣ 2 背景")

        1.  [2.2.2 LLM 新兴能力](https://arxiv.org/html/2405.10255v1#S2.SS2.SSS2 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 2.2 大语言模型（LLM） ‣ 2 背景")

        1.  [2.2.3 LLM 微调](https://arxiv.org/html/2405.10255v1#S2.SS2.SSS3 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 2.2 大语言模型（LLM） ‣ 2 背景")

    1.  [2.3 2D 视觉-语言模型](https://arxiv.org/html/2405.10255v1#S2.SS3 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 2 背景")

    1.  [2.4 视觉基础模型（VFMs）](https://arxiv.org/html/2405.10255v1#S2.SS4 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 2 背景")

1.  [3 任务与指标](https://arxiv.org/html/2405.10255v1#S3 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中")

    1.  [3.1 3D 字幕生成（3D $\rightarrow$ 文本）](https://arxiv.org/html/2405.10255v1#S3.SS1 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 3 任务与指标")

    1.  [3.2 3D 定位（3D + 文本 $\rightarrow$ 3D 位置）](https://arxiv.org/html/2405.10255v1#S3.SS2 "在《当 LLM 进入 3D 世界：通过多模态大语言模型的 3D 任务调查与元分析》中 3 任务与指标")

    1.  [3.3 3D 对话（3D + 文本 $\rightarrow$ 文本）](https://arxiv.org/html/2405.10255v1#S3.SS3 "在 3 个任务和指标中 ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

    1.  [3.4 3D 具身代理（3D + 文本 $\rightarrow$ 行动）](https://arxiv.org/html/2405.10255v1#S3.SS4 "在 3 个任务和指标中 ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

    1.  [3.5 文本到 3D 生成（文本 $\rightarrow$ 3D）](https://arxiv.org/html/2405.10255v1#S3.SS5 "在 3 个任务和指标中 ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

1.  [4 个 3D 任务中的 LLMs](https://arxiv.org/html/2405.10255v1#S4 "在当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

    1.  [4.1 大型语言模型如何处理 3D 场景信息？](https://arxiv.org/html/2405.10255v1#S4.SS1 "在 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

    1.  [4.2 增强 3D 任务表现的 LLMs](https://arxiv.org/html/2405.10255v1#S4.SS2 "在 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

        1.  [4.2.1 知识增强方法](https://arxiv.org/html/2405.10255v1#S4.SS2.SSS1 "在 4.2 中增强 3D 任务表现的 LLMs ‣ 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

        1.  [4.2.2 推理增强方法](https://arxiv.org/html/2405.10255v1#S4.SS2.SSS2 "在 4.2 中增强 3D 任务表现的 LLMs ‣ 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

    1.  [4.3 用于 3D 多任务学习的 LLMs](https://arxiv.org/html/2405.10255v1#S4.SS3 "在 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

        1.  [4.3.1 多任务学习的数据](https://arxiv.org/html/2405.10255v1#S4.SS3.SSS1 "在 4.3 中用于 3D 多任务学习的 LLMs ‣ 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

        1.  [4.3.2 为多个 3D 任务训练 LLM](https://arxiv.org/html/2405.10255v1#S4.SS3.SSS2 "在 4.3 中用于 3D 多任务学习的 LLMs ‣ 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

    1.  [4.4 LLMs 作为 3D 多模态接口](https://arxiv.org/html/2405.10255v1#S4.SS4 "在 4 个 3D 任务中的 LLMs ‣ 当 LLMs 进入 3D 世界时：通过多模态大型语言模型对 3D 任务的调查与元分析")

    1.  [4.5 大型语言模型在具身智能体中的应用](https://arxiv.org/html/2405.10255v1#S4.SS5 "在《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

        1.  [4.5.1 3D 任务规划](https://arxiv.org/html/2405.10255v1#S4.SS5.SSS1 "在《4.5 大型语言模型在具身智能体中的应用》中 ‣ 《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

        1.  [4.5.2 3D 导航](https://arxiv.org/html/2405.10255v1#S4.SS5.SSS2 "在《4.5 大型语言模型在具身智能体中的应用》中 ‣ 《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

        1.  [4.5.3 3D 对象操控](https://arxiv.org/html/2405.10255v1#S4.SS5.SSS3 "在《4.5 大型语言模型在具身智能体中的应用》中 ‣ 《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

    1.  [4.6 大型语言模型在 3D 生成中的应用](https://arxiv.org/html/2405.10255v1#S4.SS6 "在《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

        1.  [4.6.1 对象级生成](https://arxiv.org/html/2405.10255v1#S4.SS6.SSS1 "在《4.6 大型语言模型在 3D 生成中的应用》中 ‣ 《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

        1.  [4.6.2 场景规模生成](https://arxiv.org/html/2405.10255v1#S4.SS6.SSS2 "在《4.6 大型语言模型在 3D 生成中的应用》中 ‣ 《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

        1.  [4.6.3 程序生成与操控](https://arxiv.org/html/2405.10255v1#S4.SS6.SSS3 "在《4.6 大型语言模型在 3D 生成中的应用》中 ‣ 《4 个 3D 任务与大型语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

1.  [5 视觉语言模型的 3D 任务](https://arxiv.org/html/2405.10255v1#S5 "在《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

    1.  [5.1 开放词汇的 3D 场景理解](https://arxiv.org/html/2405.10255v1#S5.SS1 "在《5 个 3D 任务与视觉语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

    1.  [5.2 文本驱动的 3D 生成](https://arxiv.org/html/2405.10255v1#S5.SS2 "在《5 个 3D 任务与视觉语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

    1.  [5.3 3D 视觉与语言的端到端架构](https://arxiv.org/html/2405.10255v1#S5.SS3 "在《5 个 3D 任务与视觉语言模型》中 ‣ 《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

1.  [6 个数据集](https://arxiv.org/html/2405.10255v1#S6 "在《当大型语言模型进入 3D 世界：多模态大型语言模型的 3D 任务的调查与元分析》中")

1.  [7 挑战与机遇](https://arxiv.org/html/2405.10255v1#S7 "在《当大型语言模型进入 3D 世界：通过多模态大型语言模型对 3D 任务的调查与元分析》中")

1.  [8 结论](https://arxiv.org/html/2405.10255v1#S8 "在《当大型语言模型进入 3D 世界：通过多模态大型语言模型对 3D 任务的调查与元分析》中")

\WarningFilter

caption 未知文档类（或包）

# 当大型语言模型进入 3D 世界：通过多模态大型语言模型对 3D 任务的调查与元分析

马贤正 *、雅什·巴尔加特 *、布兰登·斯玛特 *、帅晨、邢辉·李、简丁，

金东顾、戴夫·振宇·陈、宋钰鹏、贾旺·边、

菲利普·H·托尔、马克·波雷费斯、马蒂亚斯·尼斯纳、伊恩·D·里德、安吉尔·X·张，

伊罗·莱纳、维克多·阿德里安·普里萨卡留 * 贡献相等。列出顺序随机。马贤正、雅什·巴尔加特、布兰登·斯玛特、帅晨、邢辉·李、金东顾、菲利普·托尔、伊罗·莱纳和维克多·阿德里安·普里萨卡留均来自牛津大学。简丁来自阿卜杜拉国王科技大学。戴夫·振宇·陈和马蒂亚斯·尼斯纳来自慕尼黑工业大学。贾旺·边和伊恩·D·里德来自穆罕默德·本·扎耶德人工智能大学。安吉尔·X·张来自西蒙弗雷泽大学。宋钰鹏和马克·波雷费斯来自苏黎世联邦理工学院。通讯邮箱：xianzheng@robots.ox.ac.uk 或 yashsb@robots.ox.ac.uk

###### 摘要

随着大型语言模型（LLMs）的发展，它们与 3D 空间数据（3D-LLMs）的结合取得了快速进展，为理解和与物理空间互动提供了前所未有的能力。本调查提供了使 LLMs 能够处理、理解和生成 3D 数据的方法论的全面概述。我们突出 LLMs 的独特优势，如上下文学习、逐步推理、开放词汇能力和广泛的世界知识，强调它们在增强嵌入式人工智能（AI）系统中的空间理解和互动潜力。我们的研究涵盖了各种 3D 数据表示形式，从点云到神经辐射场（NeRFs）。它还检查了这些数据表示与 LLMs 的整合，用于 3D 场景理解、描述、问答和对话等任务，以及基于 LLMs 的代理进行空间推理、规划和导航。本文还简要回顾了其他结合 3D 和语言的方法。本文中提出的元分析揭示了显著的进展，但也强调了需要新的方法来充分发挥 3D-LLMs 的潜力。因此，通过本文，我们旨在为未来的研究制定路线图，探索和扩展 3D-LLMs 在理解和与复杂 3D 世界互动方面的能力。为了支持这项调查，我们建立了一个项目页面，整理并列出了与我们主题相关的论文：[`github.com/ActiveVisionLab/Awesome-LLM-3D`](https://github.com/ActiveVisionLab/Awesome-LLM-3D)。

###### 索引词：

3D 场景理解、大型语言模型、视觉语言模型、计算机视觉。

## 1 介绍

大型语言模型（LLMs）的出现标志着自然语言处理领域的一个变革时代，使机器能够以以前未曾想象的方式理解、生成和互动人类语言。然而，我们周围的物理世界本质上是三维的，理解空间 3D 环境对于许多涉及感知、导航和在这些 3D 空间中互动的现实应用至关重要。随着最近的进展，LLMs 的应用已远远超出了文本。将 LLMs 与 3D 数据融合为增强计算模型对物理世界的理解和互动提供了独特机会，进而推动了多个领域的创新，包括自主系统 [[1](https://arxiv.org/html/2405.10255v1#bib.bib1), [2](https://arxiv.org/html/2405.10255v1#bib.bib2), [3](https://arxiv.org/html/2405.10255v1#bib.bib3), [4](https://arxiv.org/html/2405.10255v1#bib.bib4), [5](https://arxiv.org/html/2405.10255v1#bib.bib5)]、增强现实 [[6](https://arxiv.org/html/2405.10255v1#bib.bib6), [7](https://arxiv.org/html/2405.10255v1#bib.bib7), [8](https://arxiv.org/html/2405.10255v1#bib.bib8), [9](https://arxiv.org/html/2405.10255v1#bib.bib9)]、机器人导航 [[10](https://arxiv.org/html/2405.10255v1#bib.bib10), [11](https://arxiv.org/html/2405.10255v1#bib.bib11), [12](https://arxiv.org/html/2405.10255v1#bib.bib12)] 和机器人操作 [[13](https://arxiv.org/html/2405.10255v1#bib.bib13), [14](https://arxiv.org/html/2405.10255v1#bib.bib14), [15](https://arxiv.org/html/2405.10255v1#bib.bib15)]。

最近的研究工作展示了将大型语言模型（LLMs）与 3D 数据结合的潜力，以在复杂的 3D 环境中进行解释、推理或规划，利用 LLMs 的固有优势，包括零样本学习 [[16](https://arxiv.org/html/2405.10255v1#bib.bib16), [17](https://arxiv.org/html/2405.10255v1#bib.bib17)]、高级推理 [[13](https://arxiv.org/html/2405.10255v1#bib.bib13), [18](https://arxiv.org/html/2405.10255v1#bib.bib18), [19](https://arxiv.org/html/2405.10255v1#bib.bib19)] 和广泛的知识 [[20](https://arxiv.org/html/2405.10255v1#bib.bib20), [21](https://arxiv.org/html/2405.10255v1#bib.bib21)]。然而，将 LLMs 与 3D 数据结合并非易事。诸如 3D 数据表示、模型扩展性和计算效率等问题仍然是重大障碍。此外，确保模型能够在现实世界环境中运行还需要克服与数据多样性和环境复杂性相关的障碍。解决这些挑战对于充分实现 LLMs 在 3D 应用中的潜力，以创建动态且上下文感知的 AI 系统至关重要。

本文提供了对 LLMs 与 3D 数据交集的关键审视，提供了当前方法、应用和挑战的详尽概述。我们首先介绍了常见 3D 表示的相关背景，对 LLMs 进行了简要介绍，并在第[2](https://arxiv.org/html/2405.10255v1#S2 "2 Background ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节中概述了视觉语言模型（VLMs）和视觉基础模型（VFMs）。在第[3](https://arxiv.org/html/2405.10255v1#S3 "3 Tasks and Metrics ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节中，我们详细描述了当前方法旨在解决的 3D 视觉语言任务，概述了当前的评估指标和协议。

![参见说明](img/86e30294941797bbf8d29973530b5aa6.png)

图 1：通向 3D 中大型语言模型（LLMs）的方法的一般时间线。

接下来，在第[4](https://arxiv.org/html/2405.10255v1#S4 "4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节中，我们分析了数据格式、处理技术和模型架构，这些方法在通过 LLM 能力提升 3D 理解方面表现出前景。我们展示了 LLM 和 3D 数据融合成功的各种领域，如：利用 LLM 的世界知识 [[20](https://arxiv.org/html/2405.10255v1#bib.bib20), [22](https://arxiv.org/html/2405.10255v1#bib.bib22)] 和推理能力 [[21](https://arxiv.org/html/2405.10255v1#bib.bib21), [23](https://arxiv.org/html/2405.10255v1#bib.bib23)] 提升 3D 任务表现，使用 LLM 作为多模态接口 [[24](https://arxiv.org/html/2405.10255v1#bib.bib24), [18](https://arxiv.org/html/2405.10255v1#bib.bib18)] 和具身体代理 [[15](https://arxiv.org/html/2405.10255v1#bib.bib15), [13](https://arxiv.org/html/2405.10255v1#bib.bib13)]，或使用 LLM 生成复杂场景 [[25](https://arxiv.org/html/2405.10255v1#bib.bib25), [26](https://arxiv.org/html/2405.10255v1#bib.bib26)]。除了 LLM 之外，还有一些研究工作提出了将 3D 感知与语言能力统一的端到端架构 [[27](https://arxiv.org/html/2405.10255v1#bib.bib27), [28](https://arxiv.org/html/2405.10255v1#bib.bib28)]。此外，许多研究探讨了从现成的 2D 视觉语言模型（VLMs）中提炼知识以实现开放词汇的 3D 场景理解 [[29](https://arxiv.org/html/2405.10255v1#bib.bib29), [30](https://arxiv.org/html/2405.10255v1#bib.bib30)] 以及文本驱动的 3D 生成 [[31](https://arxiv.org/html/2405.10255v1#bib.bib31), [32](https://arxiv.org/html/2405.10255v1#bib.bib32)]。这项调查在第[5](https://arxiv.org/html/2405.10255v1#S5 "5 3D Tasks with VLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节提供了这些方法的完整概述，以展示 3D+语言领域的全貌。然后，我们在第[6](https://arxiv.org/html/2405.10255v1#S6 "6 Datasets ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节中概述了用于训练和评估这些方法的数据集。最后，第[7](https://arxiv.org/html/2405.10255v1#S7 "7 Challenges and Opportunities ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节突出了该领域的挑战和未来的潜在研究方向。

## 2 背景

本节提供了关于 3D 表示、大型语言模型（LLMs）、2D 视觉语言模型（VLMs）和视觉基础模型（VFMs）的基本背景知识。

### 2.1 3D 表示

选择三维表示方法来描述、建模和理解我们的世界是一个关键话题，这有助于理解当前在 3D-LLMs 方面的进展。这也是计算机视觉中的一个基本研究领域。由于深度学习、计算资源和三维数据可用性的进步，该领域最近经历了显著增长。我们简要描述了目前使用的最常见的三维表示方法。

点云用一组空间中的数据点来表示三维形状，存储每个点在三维笛卡尔坐标系统中的位置。除了存储位置外，还可以存储其他信息（例如颜色、法线）。基于点云的方法 [[33](https://arxiv.org/html/2405.10255v1#bib.bib33), [34](https://arxiv.org/html/2405.10255v1#bib.bib34), [35](https://arxiv.org/html/2405.10255v1#bib.bib35), [36](https://arxiv.org/html/2405.10255v1#bib.bib36), [37](https://arxiv.org/html/2405.10255v1#bib.bib37), [38](https://arxiv.org/html/2405.10255v1#bib.bib38), [39](https://arxiv.org/html/2405.10255v1#bib.bib39), [40](https://arxiv.org/html/2405.10255v1#bib.bib40), [41](https://arxiv.org/html/2405.10255v1#bib.bib41), [42](https://arxiv.org/html/2405.10255v1#bib.bib42), [43](https://arxiv.org/html/2405.10255v1#bib.bib43)] 以其低存储占用而闻名，但缺乏表面拓扑信息。获取点云的典型来源包括激光雷达传感器、结构光扫描仪、飞行时间相机、立体视图、摄影测量等。

体素网格 [[44](https://arxiv.org/html/2405.10255v1#bib.bib44), [45](https://arxiv.org/html/2405.10255v1#bib.bib45), [46](https://arxiv.org/html/2405.10255v1#bib.bib46), [47](https://arxiv.org/html/2405.10255v1#bib.bib47), [48](https://arxiv.org/html/2405.10255v1#bib.bib48), [49](https://arxiv.org/html/2405.10255v1#bib.bib49), [50](https://arxiv.org/html/2405.10255v1#bib.bib50), [51](https://arxiv.org/html/2405.10255v1#bib.bib51)] 由三维空间中的单元立方体组成，类似于二维中的像素表示 [[52](https://arxiv.org/html/2405.10255v1#bib.bib52)]。每个体素至少编码了占用信息（二进制或概率形式），但还可以额外编码到表面的距离，例如在带符号距离函数（SDF）[[53](https://arxiv.org/html/2405.10255v1#bib.bib53), [54](https://arxiv.org/html/2405.10255v1#bib.bib54), [55](https://arxiv.org/html/2405.10255v1#bib.bib55), [56](https://arxiv.org/html/2405.10255v1#bib.bib56), [57](https://arxiv.org/html/2405.10255v1#bib.bib57)] 或截断带符号距离函数（TSDF）[[58](https://arxiv.org/html/2405.10255v1#bib.bib58), [59](https://arxiv.org/html/2405.10255v1#bib.bib59), [60](https://arxiv.org/html/2405.10255v1#bib.bib60), [61](https://arxiv.org/html/2405.10255v1#bib.bib61), [62](https://arxiv.org/html/2405.10255v1#bib.bib62), [63](https://arxiv.org/html/2405.10255v1#bib.bib63)] 中。尽管如此，当需要高分辨率细节时，内存占用可能会变得过于庞大。

多边形网格表示由顶点和表面组成，紧凑地描述了复杂的 3D 形状。然而，它们的非结构化和不可微分性质[[64](https://arxiv.org/html/2405.10255v1#bib.bib64)]在将它们与神经网络集成以实现端到端的可微分管道时带来了挑战。一些解决这一问题的方法，如基于梯度近似的方法[[65](https://arxiv.org/html/2405.10255v1#bib.bib65), [66](https://arxiv.org/html/2405.10255v1#bib.bib66), [67](https://arxiv.org/html/2405.10255v1#bib.bib67), [68](https://arxiv.org/html/2405.10255v1#bib.bib68)]，只能使用手工计算的梯度。其他解决方案如可微分光栅化器[[69](https://arxiv.org/html/2405.10255v1#bib.bib69), [70](https://arxiv.org/html/2405.10255v1#bib.bib70), [71](https://arxiv.org/html/2405.10255v1#bib.bib71)]可能会导致模糊的渲染结果。

神经场[[72](https://arxiv.org/html/2405.10255v1#bib.bib72)]近年来在 3D 研究社区中引起了越来越多的关注，逐渐脱离了依赖几何原语的传统表示方法[[73](https://arxiv.org/html/2405.10255v1#bib.bib73)]。神经场是从空间坐标到场景属性（如占用情况、颜色、辐射等）的映射，但与体素网格不同——在体素网格中，映射是从离散单元到该体素的值——在神经场中，映射是一个学习到的函数，通常是一个多层感知器。通过这种方式，神经场隐式地学习了紧凑的、连续的、可微分的 3D 形状和场景表示。

一类神经场专注于隐式表面表示。占用网络[[74](https://arxiv.org/html/2405.10255v1#bib.bib74), [75](https://arxiv.org/html/2405.10255v1#bib.bib75), [76](https://arxiv.org/html/2405.10255v1#bib.bib76)]通过神经网络表示的连续 3D 占用函数来编码形状，利用 3D 点位置和来自点云、低分辨率体素或图像的特征来估计占用概率。同时，Deep SDF 网络[[77](https://arxiv.org/html/2405.10255v1#bib.bib77), [78](https://arxiv.org/html/2405.10255v1#bib.bib78), [79](https://arxiv.org/html/2405.10255v1#bib.bib79), [80](https://arxiv.org/html/2405.10255v1#bib.bib80)]使用神经网络从 3D 坐标和潜在向量中估计 SDF。最近的方法如 NeuS[[79](https://arxiv.org/html/2405.10255v1#bib.bib79)]和 NeuS2[[80](https://arxiv.org/html/2405.10255v1#bib.bib80)]显著提高了静态和动态物体的表面重建保真度和效率。

另一类方法被称为神经辐射场（NeRF） [[81](https://arxiv.org/html/2405.10255v1#bib.bib81), [82](https://arxiv.org/html/2405.10255v1#bib.bib82), [83](https://arxiv.org/html/2405.10255v1#bib.bib83), [84](https://arxiv.org/html/2405.10255v1#bib.bib84), [85](https://arxiv.org/html/2405.10255v1#bib.bib85), [86](https://arxiv.org/html/2405.10255v1#bib.bib86), [87](https://arxiv.org/html/2405.10255v1#bib.bib87), [88](https://arxiv.org/html/2405.10255v1#bib.bib88), [89](https://arxiv.org/html/2405.10255v1#bib.bib89), [90](https://arxiv.org/html/2405.10255v1#bib.bib90), [91](https://arxiv.org/html/2405.10255v1#bib.bib91), [92](https://arxiv.org/html/2405.10255v1#bib.bib92), [93](https://arxiv.org/html/2405.10255v1#bib.bib93), [94](https://arxiv.org/html/2405.10255v1#bib.bib94)]，展示了对 3D 世界的强大光现实渲染能力。这些方法使用位置编码技术 [[95](https://arxiv.org/html/2405.10255v1#bib.bib95), [96](https://arxiv.org/html/2405.10255v1#bib.bib96), [90](https://arxiv.org/html/2405.10255v1#bib.bib90), [97](https://arxiv.org/html/2405.10255v1#bib.bib97)]对场景细节进行编码，并利用 MLPs 预测沿相机射线的辐射值（颜色和透明度）。然而，MLPs 需要为每个采样点（包括空白区域）推断颜色和占据细节，这需要大量计算资源。因此，减少 NeRF 的计算开销以满足实时应用的需求具有强烈的动机。

混合表示法尝试将 NeRF 技术与传统的体积方法相结合，以促进高质量、实时渲染 [[98](https://arxiv.org/html/2405.10255v1#bib.bib98), [99](https://arxiv.org/html/2405.10255v1#bib.bib99), [100](https://arxiv.org/html/2405.10255v1#bib.bib100), [101](https://arxiv.org/html/2405.10255v1#bib.bib101), [102](https://arxiv.org/html/2405.10255v1#bib.bib102), [103](https://arxiv.org/html/2405.10255v1#bib.bib103), [104](https://arxiv.org/html/2405.10255v1#bib.bib104), [105](https://arxiv.org/html/2405.10255v1#bib.bib105), [106](https://arxiv.org/html/2405.10255v1#bib.bib106), [107](https://arxiv.org/html/2405.10255v1#bib.bib107)]。例如，将体素网格 [[95](https://arxiv.org/html/2405.10255v1#bib.bib95), [96](https://arxiv.org/html/2405.10255v1#bib.bib96), [98](https://arxiv.org/html/2405.10255v1#bib.bib98), [97](https://arxiv.org/html/2405.10255v1#bib.bib97)] 或多分辨率哈希网格 [[102](https://arxiv.org/html/2405.10255v1#bib.bib102)]与神经网络结合，可以大大减少 NeRF 的训练和推断时间。

3D Gaussian Splatting [[103](https://arxiv.org/html/2405.10255v1#bib.bib103), [106](https://arxiv.org/html/2405.10255v1#bib.bib106), [107](https://arxiv.org/html/2405.10255v1#bib.bib107)] 是点云的一种变体，其中每个点包含表示该点周围空间区域发射的辐射的附加信息，这些信息以各向异性的 3D 高斯“斑点”形式存在。这些 3D 高斯通常从 SfM 点云初始化 [[108](https://arxiv.org/html/2405.10255v1#bib.bib108)]，并使用可微分渲染进行优化。通过利用高效的光栅化 [[109](https://arxiv.org/html/2405.10255v1#bib.bib109)] 而非光线追踪，3D Gaussian Splatting 以极少的计算量实现了最先进的新视角合成。

### 2.2 大型语言模型（LLM）

传统的自然语言处理（NLP）涵盖了广泛的任务，旨在使系统能够理解、生成和处理文本。早期的 NLP 方法依赖于规则系统、统计模型和早期的神经网络架构，如递归神经网络 [[110](https://arxiv.org/html/2405.10255v1#bib.bib110), [111](https://arxiv.org/html/2405.10255v1#bib.bib111)]。最近引入的大型语言模型（LLMs），采用变换器架构 [[95](https://arxiv.org/html/2405.10255v1#bib.bib95)] 并在大量文本语料库上进行训练 [[112](https://arxiv.org/html/2405.10255v1#bib.bib112)]，实现了前所未有的性能，并在该领域引发了新的兴奋浪潮。由于本文重点关注 3D LLM，我们在这里提供有关 LLM 的相关背景知识。有关 LLM 的深入探讨，请参考该领域的最新调查 [[113](https://arxiv.org/html/2405.10255v1#bib.bib113), [114](https://arxiv.org/html/2405.10255v1#bib.bib114), [115](https://arxiv.org/html/2405.10255v1#bib.bib115), [116](https://arxiv.org/html/2405.10255v1#bib.bib116), [117](https://arxiv.org/html/2405.10255v1#bib.bib117)]。

#### 2.2.1 LLM 架构

在 LLM 的背景下，“编码器-解码器”和“仅解码器”架构被广泛用于自然语言处理（NLP）任务。

编码器-解码器架构 [[95](https://arxiv.org/html/2405.10255v1#bib.bib95)、[118](https://arxiv.org/html/2405.10255v1#bib.bib118)、[119](https://arxiv.org/html/2405.10255v1#bib.bib119)] 由两个主要组件组成：编码器 $f_{enc}$ 和解码器 $f_{dec}$。编码器和解码器组件通常使用 transformers [[95](https://arxiv.org/html/2405.10255v1#bib.bib95)] 实现，这些 transformers 使用注意力机制来捕捉输入和输出序列中的长距离依赖关系。编码器接受输入序列 $X=(x_{1},x_{2},\ldots,x_{N})$ 并将其映射到一系列捕捉上下文信息的潜在表示 $H=(h_{1},h_{2},\ldots,h_{N})$，解码器则根据 $H$ 生成输出序列 $Y=(y_{1},y_{2},\ldots,y_{T})$。数学上，编码过程可以表示为 $H=f_{enc}(X)$，整个潜在序列 $H$ 一次性从 $X$ 生成。然而，解码器则顺序生成输出序列 $Y$：$y_{t}=f_{dec}(y_{<t},H)$，其中 $y_{<t}=(y_{1},y_{2},\ldots,y_{t-1})$。

仅解码器架构 [[120](https://arxiv.org/html/2405.10255v1#bib.bib120)、[121](https://arxiv.org/html/2405.10255v1#bib.bib121)、[122](https://arxiv.org/html/2405.10255v1#bib.bib122)]，则是 transformer 架构的一个变体，仅使用解码器组件。这种架构特别适合语言建模任务，其中目标是基于前面的 tokens 预测下一个 token。仅解码器架构可以数学上表示为 $y_{t}=f_{dec}(y_{<t})$。

分词是将输入文本拆分成一系列基本数据单元（即“tokens”）的预处理方法。tokens 的数量是有限的，每个 token 可以对应一个单词、子词或一个字母。在推理过程中，输入文本被转换成 tokens 序列并传递给模型，模型预测的输出 tokens 会被转换回文本。分词对语言模型的性能有很大的影响，因为它会影响模型对文本的感知。使用了各种分词技术，如词级分词、子词分词（例如字节对编码 [[123](https://arxiv.org/html/2405.10255v1#bib.bib123)]、WordPiece [[124](https://arxiv.org/html/2405.10255v1#bib.bib124)]、SentencePiece [[125](https://arxiv.org/html/2405.10255v1#bib.bib125)]），以及字符级分词 [[126](https://arxiv.org/html/2405.10255v1#bib.bib126)]。

#### 2.2.2 LLM 生成能力

LLM（大语言模型）和传统非 LLM 方法之间的一个主要区别是**大模型**中出现的**新兴能力**，而小模型中没有这些能力[[115](https://arxiv.org/html/2405.10255v1#bib.bib115)]。术语“新兴能力”指的是随着 LLM 在规模和复杂性上的扩展而出现的新且复杂的能力。这些能力使得高级自然语言理解和生成、在各种领域的无特定训练的问题解决，以及通过上下文学习适应新任务成为可能。接下来，我们介绍一些 LLM 范围内的常见新兴能力。

上下文学习[[127](https://arxiv.org/html/2405.10255v1#bib.bib127), [128](https://arxiv.org/html/2405.10255v1#bib.bib128), [129](https://arxiv.org/html/2405.10255v1#bib.bib129)]指的是 LLM 基于提示中的上下文理解和响应新任务或查询的能力，而无需明确的重新训练或微调。里程碑论文（GPT-2/GPT-3[[130](https://arxiv.org/html/2405.10255v1#bib.bib130), [127](https://arxiv.org/html/2405.10255v1#bib.bib127)]）展示了几次示例方式的上下文学习，其中模型在提示中提供了一些任务示例，然后被要求处理不同的示例，而没有事先明确的训练。最先进的 LLM，例如 GPT-4[[131](https://arxiv.org/html/2405.10255v1#bib.bib131)]，展现了显著的上下文学习能力，能够理解复杂指令，执行从简单翻译到生成代码和创造性写作的广泛任务，所有这些都基于提示中提供的上下文。

在大型语言模型（LLMs）的背景下，**推理**，通常被称为“思维链”提示 [[132](https://arxiv.org/html/2405.10255v1#bib.bib132), [133](https://arxiv.org/html/2405.10255v1#bib.bib133)]，涉及模型在解决复杂问题或问题时生成中间步骤或推理路径。这种方法使得 LLMs 能够将任务分解为更小、更易管理的部分，从而促进更结构化和可理解的解决过程。为了实现这一点，训练涉及包括各种问题解决任务的数据集 [[134](https://arxiv.org/html/2405.10255v1#bib.bib134), [135](https://arxiv.org/html/2405.10255v1#bib.bib135)]、逻辑谜题 [[136](https://arxiv.org/html/2405.10255v1#bib.bib136), [137](https://arxiv.org/html/2405.10255v1#bib.bib137)]，以及设计用于模拟不确定性下推理的数据集 [[138](https://arxiv.org/html/2405.10255v1#bib.bib138)]。当前最先进的 LLMs [[127](https://arxiv.org/html/2405.10255v1#bib.bib127), [131](https://arxiv.org/html/2405.10255v1#bib.bib131), [139](https://arxiv.org/html/2405.10255v1#bib.bib139), [140](https://arxiv.org/html/2405.10255v1#bib.bib140), [141](https://arxiv.org/html/2405.10255v1#bib.bib141), [142](https://arxiv.org/html/2405.10255v1#bib.bib142), [143](https://arxiv.org/html/2405.10255v1#bib.bib143)] 通常在模型规模达到 60B 到 100B 参数时展现出先进的推理能力 [[132](https://arxiv.org/html/2405.10255v1#bib.bib132)]。

**指令遵循** [[144](https://arxiv.org/html/2405.10255v1#bib.bib144), [127](https://arxiv.org/html/2405.10255v1#bib.bib127), [140](https://arxiv.org/html/2405.10255v1#bib.bib140), [145](https://arxiv.org/html/2405.10255v1#bib.bib145), [146](https://arxiv.org/html/2405.10255v1#bib.bib146)] 指的是模型理解和执行命令的能力，或按照用户指定的指令进行操作。这包括解析指令、理解其意图，并生成适当的回应或行动。将这种能力适应于新任务可能需要从包含各种指令及其正确响应或行动的数据集中进行指令调优 [[114](https://arxiv.org/html/2405.10255v1#bib.bib114)]。监督学习、从人类反馈中进行强化学习和互动学习等技术可以进一步提升性能。

#### 2.2.3 LLM 微调

在 3D-LLM 的背景下，LLM 要么直接以预训练状态使用，要么经过微调以适应新的多模态任务。然而，由于涉及大量参数，对 LLM 所有参数进行微调会带来显著的计算和内存挑战。因此，参数高效微调（PEFT） [[147](https://arxiv.org/html/2405.10255v1#bib.bib147)] 已变得越来越流行，通过仅更新模型参数的相对小部分来适应特定任务，而不是重新训练整个模型。以下部分列出了四种在 LLM 中常用的 PEFT 方法。

低秩适应（LoRA）及其变体 [[148](https://arxiv.org/html/2405.10255v1#bib.bib148), [149](https://arxiv.org/html/2405.10255v1#bib.bib149), [150](https://arxiv.org/html/2405.10255v1#bib.bib150)] 通过低秩矩阵更新参数。在数学上，LoRA [[148](https://arxiv.org/html/2405.10255v1#bib.bib148)] 在微调过程中的前向传播可以表示为 $h=W_{0}x+BAx$。$W_{0}$ 是 LLM 的冻结权重，而 $BA$ 是由新引入的矩阵 $A$ 和 $B$ 参数化的低秩矩阵，这些矩阵在微调阶段进行更新。这种方法具有几个明显的好处。在微调过程中，仅优化 $B$ 和 $A$，显著减少了与梯度计算和参数更新相关的计算开销。一旦微调结束并且权重被合并，与原始模型相比，不会有额外的推理成本，如方程所示：$h=(W_{0}+BA)x$。此外，无需为不同任务保存多个 LLM 副本，因为可以保存多个 LoRA 实例，从而减少存储占用。

层冻结 [[151](https://arxiv.org/html/2405.10255v1#bib.bib151), [142](https://arxiv.org/html/2405.10255v1#bib.bib142), [152](https://arxiv.org/html/2405.10255v1#bib.bib152)] 冻结预训练模型的选定层，同时在训练过程中更新其他层。这通常适用于模型输入或输出较近的层，具体取决于任务的性质和模型架构。例如，在 3D-LLM 方法中，除了输入和输出嵌入 [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)] 外的所有层可能会被冻结，以减轻任务特定数据集的过拟合风险，保留预训练的一般知识并减少需要优化的参数。

提示调优 [[154](https://arxiv.org/html/2405.10255v1#bib.bib154), [155](https://arxiv.org/html/2405.10255v1#bib.bib155), [156](https://arxiv.org/html/2405.10255v1#bib.bib156)] 通过将任务框定在提示中来引导大语言模型（LLMs）执行特定任务，这与传统的微调方法（调整模型参数）不同。手动提示工程 [[132](https://arxiv.org/html/2405.10255v1#bib.bib132), [157](https://arxiv.org/html/2405.10255v1#bib.bib157), [158](https://arxiv.org/html/2405.10255v1#bib.bib158), [159](https://arxiv.org/html/2405.10255v1#bib.bib159)] 是最直观的方法，但经验丰富的提示调优工程师很难找到最佳提示。另一组方法是自动提示生成和优化。一种常见的方法是寻找确切的最佳输入提示文本，称为硬提示，如 [[160](https://arxiv.org/html/2405.10255v1#bib.bib160), [161](https://arxiv.org/html/2405.10255v1#bib.bib161), [162](https://arxiv.org/html/2405.10255v1#bib.bib162), [163](https://arxiv.org/html/2405.10255v1#bib.bib163)]。或者，可以使用优化方法来优化提示的嵌入（软提示） [[154](https://arxiv.org/html/2405.10255v1#bib.bib154), [164](https://arxiv.org/html/2405.10255v1#bib.bib164), [165](https://arxiv.org/html/2405.10255v1#bib.bib165), [166](https://arxiv.org/html/2405.10255v1#bib.bib166), [167](https://arxiv.org/html/2405.10255v1#bib.bib167), [168](https://arxiv.org/html/2405.10255v1#bib.bib168), [169](https://arxiv.org/html/2405.10255v1#bib.bib169), [170](https://arxiv.org/html/2405.10255v1#bib.bib170)]。

自适应微调通过添加或移除层或模块来定制模型架构以适应特定任务 [[171](https://arxiv.org/html/2405.10255v1#bib.bib171), [172](https://arxiv.org/html/2405.10255v1#bib.bib172), [173](https://arxiv.org/html/2405.10255v1#bib.bib173)]。这可以包括将视觉信息等新数据模态与文本数据相结合。自适应微调的核心思想是利用插入在预训练模型层之间的小型神经网络模块。在自适应微调过程中，只有这些适配器模块的参数会被更新，而原始模型权重保持不变。

### 2.3 2D 视觉-语言模型

视觉-语言模型是一类旨在捕捉和利用文本与图像/视频之间关系的模型，能够在这两种模态之间执行交互任务。大多数视觉-语言模型采用基于变换器的架构。通过利用注意力模块，视觉和文本内容相互条件化，从而实现相互交互。在接下来的段落中，我们将简要介绍视觉-语言模型在判别性和生成性任务中的应用。

判别任务涉及预测数据的某些特征。VLMs，如 CLIP [[174](https://arxiv.org/html/2405.10255v1#bib.bib174)] 和 ALIGN [[175](https://arxiv.org/html/2405.10255v1#bib.bib175)]，在图像分类中的零-shot 转移能力表现卓越。两个模型都包含两个模块：视觉编码器和文本编码器。给定一张图像及其类别，CLIP 和 ALIGN 通过最大化图像嵌入与“a photo of a {image category}”句子的文本嵌入之间的相似性来进行训练。零-shot 转移能力通过在推理过程中将“{image category}”替换为可能的候选项并寻找与图像匹配最好的句子来实现。这两项工作激发了许多后续研究，如 [[176](https://arxiv.org/html/2405.10255v1#bib.bib176), [177](https://arxiv.org/html/2405.10255v1#bib.bib177), [178](https://arxiv.org/html/2405.10255v1#bib.bib178), [179](https://arxiv.org/html/2405.10255v1#bib.bib179)]，进一步提高了图像分类的准确性。这些模型还可以提炼学到的知识用于其他任务，包括目标检测 [[180](https://arxiv.org/html/2405.10255v1#bib.bib180), [181](https://arxiv.org/html/2405.10255v1#bib.bib181), [182](https://arxiv.org/html/2405.10255v1#bib.bib182), [183](https://arxiv.org/html/2405.10255v1#bib.bib183)]、图像分割 [[184](https://arxiv.org/html/2405.10255v1#bib.bib184), [185](https://arxiv.org/html/2405.10255v1#bib.bib185), [186](https://arxiv.org/html/2405.10255v1#bib.bib186), [187](https://arxiv.org/html/2405.10255v1#bib.bib187), [188](https://arxiv.org/html/2405.10255v1#bib.bib188)]、文档理解 [[189](https://arxiv.org/html/2405.10255v1#bib.bib189), [190](https://arxiv.org/html/2405.10255v1#bib.bib190)] 和视频识别 [[191](https://arxiv.org/html/2405.10255v1#bib.bib191)]。

生成任务利用 VLMs 从输入数据生成文本或图像。通过利用大规模的训练数据，单个 VLM 通常可以执行多个图像到文本生成任务，如图像标题生成和视觉问答（VQA）。显著的例子包括 SimVLM [[192](https://arxiv.org/html/2405.10255v1#bib.bib192)]、BLIP [[193](https://arxiv.org/html/2405.10255v1#bib.bib193)] 和 OFA [[194](https://arxiv.org/html/2405.10255v1#bib.bib194)]，*等*。更强大的 VLMs，如 BLIP-2 [[195](https://arxiv.org/html/2405.10255v1#bib.bib195)]、Flamingo [[196](https://arxiv.org/html/2405.10255v1#bib.bib196)] 和 LLaVA [[197](https://arxiv.org/html/2405.10255v1#bib.bib197)]，能够处理基于输入图像的多轮对话和推理。继扩散模型引入后，文本到图像生成也成为研究社区的重点 [[198](https://arxiv.org/html/2405.10255v1#bib.bib198)、[199](https://arxiv.org/html/2405.10255v1#bib.bib199)]。通过对大量图像-文本对进行训练，扩散模型 [[200](https://arxiv.org/html/2405.10255v1#bib.bib200)、[201](https://arxiv.org/html/2405.10255v1#bib.bib201)] 可以基于文本输入生成高质量图像。这种能力也扩展到生成视频 [[202](https://arxiv.org/html/2405.10255v1#bib.bib202)]、3D 场景 [[31](https://arxiv.org/html/2405.10255v1#bib.bib31)] 和动态 3D 物体 [[203](https://arxiv.org/html/2405.10255v1#bib.bib203)]。除了生成任务，还可以通过文本提示编辑现有图像 [[204](https://arxiv.org/html/2405.10255v1#bib.bib204)、[205](https://arxiv.org/html/2405.10255v1#bib.bib205)、[206](https://arxiv.org/html/2405.10255v1#bib.bib206)、[207](https://arxiv.org/html/2405.10255v1#bib.bib207)]。

### 2.4 视觉基础模型（VFMs）

视觉基础模型（VFMs）是大型神经网络，旨在提取图像表示，这些表示足够多样和表达力强，可以直接用于各种下游任务，类似于预训练的 LLMs 在下游 NLP 任务中所起的作用。一个显著的例子是 DINO [[208](https://arxiv.org/html/2405.10255v1#bib.bib208)]，它使用自监督的师生训练范式。所学的表示在图像分类和语义图像匹配上都取得了良好的结果。DINO 中的注意力权重还可以作为观察场景的语义组件的分割掩码。后续工作如 iBOT [[209](https://arxiv.org/html/2405.10255v1#bib.bib209)]和 DINOv2 [[210](https://arxiv.org/html/2405.10255v1#bib.bib210)]通过引入遮挡图像建模（MIM）损失进一步改进了表示。SAM，一个基于变换器的图像分割模型 [[211](https://arxiv.org/html/2405.10255v1#bib.bib211)]，在包含 11 亿张图像和语义掩码的数据集上进行训练，并展示了强大的零样本迁移能力。DINO (Zhang *et al.*) [[212](https://arxiv.org/html/2405.10255v1#bib.bib212)] —— 不要与 DINO (Caron *et al.*) [[208](https://arxiv.org/html/2405.10255v1#bib.bib208)] 混淆 —— 采用类似 DETR 的 [[213](https://arxiv.org/html/2405.10255v1#bib.bib213)] 架构和混合查询选择进行目标检测。后续工作 Grounding-DINO [[214](https://arxiv.org/html/2405.10255v1#bib.bib214)] 引入文本监督以提高准确性。Stable Diffusion [[201](https://arxiv.org/html/2405.10255v1#bib.bib201)]，一个文本到图像生成器，也被用作‘真实’图像的特征提取器，通过在干净或人工噪声图像上运行一次扩散步骤，并提取中间特征 [[215](https://arxiv.org/html/2405.10255v1#bib.bib215), [169](https://arxiv.org/html/2405.10255v1#bib.bib169)] 或注意力掩码 [[216](https://arxiv.org/html/2405.10255v1#bib.bib216)]。这些特征最近被用于分割 [[216](https://arxiv.org/html/2405.10255v1#bib.bib216)] 和图像匹配 [[215](https://arxiv.org/html/2405.10255v1#bib.bib215), [169](https://arxiv.org/html/2405.10255v1#bib.bib169)] 任务，考虑到用于扩散模型的训练集的规模和多样性，以及扩散特征的观察到的突现属性，如图像间的零样本对应 [[215](https://arxiv.org/html/2405.10255v1#bib.bib215)]。

## 3 任务和指标

要理解语言在 3D 理解中的作用，首先需要了解 3D 视觉-语言模型试图解决的任务。研究已扩展到包括广泛的研究任务，每个任务都有其常用的数据集和评估指标。在这里，我们旨在列出当前的 3D 视觉-语言任务及其对应的评估指标。我们根据任务的输入和输出模态对任务进行广泛分类。

然后，我们在第 [4](https://arxiv.org/html/2405.10255v1#S4 "4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models") 和第 [5](https://arxiv.org/html/2405.10255v1#S5 "5 3D Tasks with VLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models") 节开始分析解决这些任务的方法。然后，在第 [6](https://arxiv.org/html/2405.10255v1#S6 "6 Datasets ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models") 节中，我们详细介绍了目前用于训练和评估这些任务的数据集。

### 3.1 3D 字幕生成（3D $\rightarrow$ 文本）

给定场景或对象的 3D 数据，3D 字幕生成的任务是生成相应的简短自然语言描述。在这里，我们将这一任务分解为几种常见的变体，基于数据的类型和生成的字幕类型。

对象级字幕生成要求模型生成单个 3D 对象的简短自然语言描述。这个字幕应关注对象的关键特征，包括其形状和语义特征。

场景级字幕生成指的是为整个 3D 场景生成简短的自然语言字幕。这些字幕通常关注全局场景信息（如房间类型和风格）、场景中的关键对象及其关系。我们认为“有根字幕生成”是场景字幕生成的一种变体，其中模型输出描述场景中对象之间关系的文字，并可能包括这些对象的位置数据。

3D 密集字幕生成指的是在 3D 场景中定位对象实例并用自然语言字幕描述它们的联合任务。在这种情况下，输出可能还包含关于被描述对象的位置信息。通常，来自 3D 定位数据集的参考描述被用来生成 3D 密集字幕所需的字幕和位置数据。例如，Scan2Cap 的字幕[[217](https://arxiv.org/html/2405.10255v1#bib.bib217)] 是使用来自 ScanRefer 的参考表达[[218](https://arxiv.org/html/2405.10255v1#bib.bib218)] 生成的。

3D 字幕生成的评估指标需要将生成的字幕与测试样本的真实字幕进行比较。

精确匹配（EM）要求生成的字幕与真实情况完全匹配。精确匹配有不同的准确度阈值，记作 EM@$K$，这意味着正确答案在模型生成的前“$K$”个答案中。常用的阈值是 EM@1 和 EM@10。然而，自然语言字幕具有相同语义的表述方式多种多样，因此字幕的主要指标是自动文本生成指标 [[219](https://arxiv.org/html/2405.10255v1#bib.bib219)]，这些指标旨在衡量匹配的 n-gram 或语义相似性，而不是完整的句子匹配。BLEU [[220](https://arxiv.org/html/2405.10255v1#bib.bib220)] 匹配预测字幕和真实字幕之间的 n-gram，其中“BLEU@$x$”指的是长度为“$x$”的 n-gram 匹配（典型值在 1-4 范围内）。这仍然需要精确匹配单词，但对短语的重排稍微更为鲁棒。ROUGE [[221](https://arxiv.org/html/2405.10255v1#bib.bib221)] 类似地旨在匹配 n-gram，常用的 ROUGE-L 集中于句子的结构相似性。METEOR [[222](https://arxiv.org/html/2405.10255v1#bib.bib222)] 基于单一词匹配的精确度和召回率，其中“匹配”也存在于同义词和形态变体之间。CIDEr [[223](https://arxiv.org/html/2405.10255v1#bib.bib223)] 通过 n-gram 的频率进行加权，高频 n-gram 给予较低的权重。由于上述指标依赖于 n-gram 匹配，因此无法考虑语义上相似但不同的单词。因此，已经引入了各种度量，测量通过学习的嵌入空间中的相似性来衡量语义内容的重叠（例如，SentenceSim [[224](https://arxiv.org/html/2405.10255v1#bib.bib224)]和 BERT Score [[225](https://arxiv.org/html/2405.10255v1#bib.bib225)]）。

对于密集字幕，其中字幕局部化到场景的部分，需要调整基准测试。通常仍然使用 BLEU、ROUGE、METEOR 和 CIDEr 评分，但如果预测的边界框与对象之间的交并比（IoU）低于阈值“$k$”，则评分设为零。典型的“$k$”值为 0.25 和 0.5 [[19](https://arxiv.org/html/2405.10255v1#bib.bib19)、[217](https://arxiv.org/html/2405.10255v1#bib.bib217)、[226](https://arxiv.org/html/2405.10255v1#bib.bib226)]。然而，这些指标侧重于字幕的召回率，同时忽略了假阳性。这一问题在更近期的工作中得到了解决，这些工作还测量了生成字幕的精确度和 F-1 分数相对于 BLEU、ROUGE、METEOR 和 CIDEr 指标 [[227](https://arxiv.org/html/2405.10255v1#bib.bib227)]。

### 3.2 3D 定位（3D + 文本 $\rightarrow$ 3D 位置）

给定一个 3D 场景和一个描述场景中对象相对于其他对象的“指代表达”，3D 定位涉及为目标对象生成位置、边界框或分割掩模。

单对象定位涉及在给定参考信息（如语言描述[[218](https://arxiv.org/html/2405.10255v1#bib.bib218)、[228](https://arxiv.org/html/2405.10255v1#bib.bib228)]或额外手势[[229](https://arxiv.org/html/2405.10255v1#bib.bib229)]）的情况下，在场景中定位一个单独的查询对象。

多对象定位涉及使用指代表达式来定位多个对象。这种定位有两个主要变体。第一个变体涉及一个可能模糊的单句描述，可能指代 3D 场景中零个、一个或多个相同类别的目标对象[[230](https://arxiv.org/html/2405.10255v1#bib.bib230)]。第二个变体使用段落长度的指代表达式来描述属于不同类别的多个对象，以及它们之间的空间关系[[231](https://arxiv.org/html/2405.10255v1#bib.bib231)]。

3D 定位的评估指标需要将预测位置（通常以边界框的形式）与测试样本中的真实位置进行比较。Acc@$K$IoU[[218](https://arxiv.org/html/2405.10255v1#bib.bib218)]是 3D 视觉定位中广泛使用的指标，它衡量与真实位置交集比（IoU）大于阈值$K$的正预测百分比，该阈值通常设置为 0.25 或 0.5。值得注意的是，一些数据集在不同场景中评估性能。例如，ScanRefer[[218](https://arxiv.org/html/2405.10255v1#bib.bib218)]将数据集划分为独特/多个/总体分割。一些方法测量平均 IoU[[153](https://arxiv.org/html/2405.10255v1#bib.bib153)、[232](https://arxiv.org/html/2405.10255v1#bib.bib232)]，而其他方法测量边界框中心之间的平均距离[[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]。对于多对象定位，使用 F1 分数作为指标[[230](https://arxiv.org/html/2405.10255v1#bib.bib230)]。他们首先根据 IoU 获得预测和真实边界框之间的一对一匹配。然后，将 IoU 高于阈值的对视为真正的正例。

### 3.3 3D 对话（3D + 文本 $\rightarrow$ 文本）

还可以考虑关于 3D 场景的问题任务，无论是在单轮设置还是更自然的多轮对话设置中。

3D 问答（3D-QA）是一个任务，要求模型根据 3D 场景生成对用户提问的答案。问题的主题范围多样，模型必须理解 3D 场景和问题，以生成正确的回答。问题包括简单任务，如确定一个物体的存在，以及更困难的任务，如空间推理。由于有几个成熟的基准测试，并且基准测试中的大多数问题都是具有唯一答案的事实性问题，因此 3D-QA 是评估多任务模型能力的一个热门任务。

3D 定位问答（3D-SQA）是 3D-QA 的一个特殊情况。主要区别在于 3D-QA 需要模型从一个能够访问场景所有信息的旁观者的角度回答问题，而 3D-SQA 需要从一个预定义情境中的玩家的角度提供答案。例如，3D-SQA 可能会问“我面前有多少把椅子？”这基于“站在餐桌后面并面向餐桌”的情境。

3D 对话要求模型与用户进行关于 3D 场景的连贯和自然的多轮对话，而不是单轮问答。例如，用户可能想了解一个房间，所以他们会不断问关于房间每个部分的问题，而模型则需正确且连贯地回应。

评估指标涉及将模型的回答与测试样本的真实答案进行比较。对于 3D-QA 和 3D-SQA，主要的指标是准确匹配（EM），这意味着模型生成的答案必须与正确答案完全匹配。这是因为现有的 3D-QA 基准测试中大多数问题[[233](https://arxiv.org/html/2405.10255v1#bib.bib233), [234](https://arxiv.org/html/2405.10255v1#bib.bib234), [235](https://arxiv.org/html/2405.10255v1#bib.bib235), [236](https://arxiv.org/html/2405.10255v1#bib.bib236)] 都是只有一个明确正确答案的事实性问题。对于 3D 对话和任务规划，其答案可能不唯一，语义指标如 BLEU [[220](https://arxiv.org/html/2405.10255v1#bib.bib220)], ROUGE [[221](https://arxiv.org/html/2405.10255v1#bib.bib221)], METEOR [[222](https://arxiv.org/html/2405.10255v1#bib.bib222)], CIDEr [[223](https://arxiv.org/html/2405.10255v1#bib.bib223)], 和 SPICE [[237](https://arxiv.org/html/2405.10255v1#bib.bib237)] 被用于评估生成回答与基准提供的参考答案之间的相似性。它们也用于 3D-QA，特别是 ScanQA 基准，以测量语义相似性和准确性。

### 3.4 3D 具身智能体（3D + 文本 $\rightarrow$ 行动）

考虑涉及与 3D 场景交互的任务，也基于描述所需动作或目标的特定文本提示，通常是很有用的。

3D 任务规划是用户提供高层次目标，模型需要概述低层次步骤以实现这一目标的任务。例如，给定一个房间的 3D 场景，用户可能会询问如何清洁房间，模型需要提供详细的清洁步骤。

3D 导航指的是使 3D 代理（如机器人或虚拟角色）在 3D 空间内移动和定向的任务。这涉及到理解和解释 3D 环境、识别障碍物，并规划安全、高效的路径以达到指定的目标。

3D 操作指的是 3D 代理在其环境中与物体进行物理交互的能力。这可以包括拾取和移动物体，以及更复杂的动作序列，如组装部件或打开门。

3D 任务规划的评估指标也依赖于将模型的文本/标记输出与测试样本的地面真实动作进行匹配。BLEU [[220](https://arxiv.org/html/2405.10255v1#bib.bib220)]、ROUGE [[221](https://arxiv.org/html/2405.10255v1#bib.bib221)]、METEOR [[222](https://arxiv.org/html/2405.10255v1#bib.bib222)]、CIDEr [[223](https://arxiv.org/html/2405.10255v1#bib.bib223)]和 SPICE [[237](https://arxiv.org/html/2405.10255v1#bib.bib237)]被应用于评估生成的响应与地面真实答案之间的相似性。

对于 3D 导航，主要有两个指标来评估性能。1) 成功率（SR）衡量 3D 代理是否在预定义的距离阈值内到达目标位置。2) 由路径长度加权的成功率（SPL）[[238](https://arxiv.org/html/2405.10255v1#bib.bib238)]，该指标计算为 SR 加权地面真实长度与实际路径长度的比率，旨在反映模型实现目标的效率。其他指标包括 Oracle 成功率（OSR）、轨迹长度（TL）和目标过程（GP）[[239](https://arxiv.org/html/2405.10255v1#bib.bib239)]。除了上述衡量代理是否成功到达目标及其效率的指标外，还需要考虑代理路径与语言指定路径（当语言用于指定详细路径时）的匹配程度。一个这样的指标是基于归一化动态时间规整的成功率（SDTW）[[240](https://arxiv.org/html/2405.10255v1#bib.bib240)]，它将 SR 与给定指令的代理路径和地面真实路径之间的差异相结合。请注意，我们的讨论专注于 3D-LLMs 方法中使用的指标。我们鼓励读者参考 Gu *et al.* [[241](https://arxiv.org/html/2405.10255v1#bib.bib241)]以获取导航指标的总结。

对于 3D 操作，关键指标是成功率 [[242](https://arxiv.org/html/2405.10255v1#bib.bib242)]，操作的成功率定义为成功操作的次数除以任务样本的总数。如在第 [4.5](https://arxiv.org/html/2405.10255v1#S4.SS5 "4.5 LLMs for Embodied Agents ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models") 节讨论，不同的数据集在文本表示操作的方式上有不同的惯例，例如使用结构化输出、标准化数值评分或引入新的标记。

### 3.5 文本到 3D 生成（Text $\rightarrow$ 3D）

除了使用文本描述和与现有的 3D 场景互动外，还可以通过语言规范生成 3D 对象和场景。这里我们简要总结了这一领域的内容，详细信息请参见 Lee *et al.* [[243](https://arxiv.org/html/2405.10255v1#bib.bib243)]。

3D 对象生成涉及从文本描述生成单个对象的 3D 模型。文本输入可以提供关于对象类别、属性、部件结构和其他应在生成的 3D 形状中体现的特征的详细信息。

3D 场景生成是创建完整 3D 环境（如房间或户外空间）的任务，这些环境基于文本场景描述。这涉及生成文本中指定的对象的 3D 模型，以及根据文本中指定的约束（如对象类别、数量、空间关系和场景属性）智能地排列和组合多个 3D 对象模型。

![参见说明](img/031e0c886c393d19ba1413fbad148a67.png)

图 2：对齐 3D 和文本的 LLM 架构。在这里，我们展示了四种高级架构：(a) 仅 3D 模型，将 3D 特征与 LLM 的输入空间对齐，(b) 3D+文本模型，其中 3D 特征和文本都对齐，(c) Q-Former 风格模型，在对齐 3D 特征时使用文本进行条件化，并可选地提供给 LLM 本身（虚线箭头），以及 (d) 仅文本的方法，将 3D 表示转换为文本字符串，避免了训练对齐模块的需求。

3D 编辑指的是根据文本指令修改现有的 3D 资产，如形状或场景。这可能包括添加、删除或变换对象，改变材料或颜色，或根据给定文本修改高层场景属性。

3D 生成任务的评估指标评估生成形状/场景的质量以及生成内容与输入文本的匹配程度。用于测量生成几何体的常见指标包括 Chamfer 距离（CD）和网格体积/表面距离（MVD）。CD 通过对比真实 3D 数据的点对点距离的平方和来计算，而 MVD 通过计算两个网格之间的体积/表面来衡量几何误差。为了评估整体质量，分类准确度检查语义属性是否得到保留，而 Fréchet Inception Distance（FID）则捕捉现实性和多样性。为了检查生成的形状是否与输入文本匹配，通常会测量文本与对齐的 3D 形状嵌入（例如 ULIP [[244](https://arxiv.org/html/2405.10255v1#bib.bib244)]）或渲染图像（例如 CLIP [[174](https://arxiv.org/html/2405.10255v1#bib.bib174)]）之间的相似度。也常常使用人工研究来进行评估。然而，最近的研究 [[245](https://arxiv.org/html/2405.10255v1#bib.bib245)] 表明，使用类似 GPT-v4 的 LVLMs 作为替代人工评审的方式是可能的。对于基于文本的 3D 编辑，CD 和 IoU 评估指令编辑应用于输入几何体的效果，且不产生过度的扭曲。

## 4 个与 LLMs 相关的 3D 任务

3D 场景理解任务已被广泛研究。其核心在于识别和分类指定 3D 环境中的所有物体，这一过程称为语义 [[246](https://arxiv.org/html/2405.10255v1#bib.bib246), [247](https://arxiv.org/html/2405.10255v1#bib.bib247), [248](https://arxiv.org/html/2405.10255v1#bib.bib248), [46](https://arxiv.org/html/2405.10255v1#bib.bib46), [249](https://arxiv.org/html/2405.10255v1#bib.bib249), [250](https://arxiv.org/html/2405.10255v1#bib.bib250)] 或实例级别 [[251](https://arxiv.org/html/2405.10255v1#bib.bib251), [252](https://arxiv.org/html/2405.10255v1#bib.bib252), [253](https://arxiv.org/html/2405.10255v1#bib.bib253), [254](https://arxiv.org/html/2405.10255v1#bib.bib254), [255](https://arxiv.org/html/2405.10255v1#bib.bib255), [256](https://arxiv.org/html/2405.10255v1#bib.bib256), [257](https://arxiv.org/html/2405.10255v1#bib.bib257)] 理解。这个阶段至关重要，因为它构成了更为细致解读的基础。随后，更高级别的场景理解则侧重于空间理解，即构建空间场景图 [[258](https://arxiv.org/html/2405.10255v1#bib.bib258), [259](https://arxiv.org/html/2405.10255v1#bib.bib259)] 和对象关系的语义 [[260](https://arxiv.org/html/2405.10255v1#bib.bib260), [261](https://arxiv.org/html/2405.10255v1#bib.bib261)]。进一步而言，还可以预测潜在的互动，例如功能性 [[262](https://arxiv.org/html/2405.10255v1#bib.bib262), [13](https://arxiv.org/html/2405.10255v1#bib.bib13), [14](https://arxiv.org/html/2405.10255v1#bib.bib14), [15](https://arxiv.org/html/2405.10255v1#bib.bib15), [263](https://arxiv.org/html/2405.10255v1#bib.bib263)]、场景变化 [[264](https://arxiv.org/html/2405.10255v1#bib.bib264), [265](https://arxiv.org/html/2405.10255v1#bib.bib265)] 和对场景更广泛背景的理解，例如功能和美学风格 [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)]。3D 数据还面临一些 2D 数据所不存在的独特挑战，例如获取和标注 3D 数据的成本相对较高、稀疏的 3D 数据结构不均匀密集或对齐到网格的情况，以及需要协调同一物体的多个（可能被遮挡的）视角 [[261](https://arxiv.org/html/2405.10255v1#bib.bib261), [256](https://arxiv.org/html/2405.10255v1#bib.bib256)]。为此，研究人员利用了语言的力量，将 3D 世界中的语义和关系嵌入其中。近期将大型语言模型（LLMs）与 3D 数据集成的努力显示出实现多层次理解和互动的潜力，充分利用了 LLMs 固有的优势，即零样本学习、上下文学习、逐步推理和广泛的世界知识。

在第[4.1 节](https://arxiv.org/html/2405.10255v1#S4.SS1 "4.1 LLMs 如何处理 3D 场景信息？ ‣ 4 3D 任务与 LLMs ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")中，以及图[2](https://arxiv.org/html/2405.10255v1#S3.F2 "图 2 ‣ 3.5 文本到 3D 生成（文本→3D） ‣ 3 任务和指标 ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")中，我们简要描述了 LLMs 如何处理 3D 场景信息，强调了 3D 特征如何与语言对齐，以便通过 LLMs 进行解释和推理，这为后续章节奠定了基础。该部分的其余部分按照图[3](https://arxiv.org/html/2405.10255v1#S4.F3 "图 3 ‣ 4 3D 任务与 LLMs ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")中展示的分类法进行结构化，该图描述了 LLMs 在解决 3D 任务中所扮演的角色。我们从展示 LLMs 的世界知识（有时称为‘常识知识’）和推理能力如何提升 3D 任务的性能开始，见第[4.2 节](https://arxiv.org/html/2405.10255v1#S4.SS2 "4.2 LLMs 在提升 3D 任务性能中的作用 ‣ 4 3D 任务与 LLMs ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")。在第[4.3 节](https://arxiv.org/html/2405.10255v1#S4.SS3 "4.3 LLMs 用于 3D 多任务学习 ‣ 4 3D 任务与 LLMs ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")中，我们详细说明了如何将多个 3D 任务集成到一个 LLM 中以实现多任务学习。我们探索了 LLMs 如何作为统一接口来结合其他模态，在第[4.4 节](https://arxiv.org/html/2405.10255v1#S4.SS4 "4.4 LLMs 作为 3D 多模态接口 ‣ 4 3D 任务与 LLMs ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")中。然后，在第[4.5 节](https://arxiv.org/html/2405.10255v1#S4.SS5 "4.5 LLMs 作为具身代理 ‣ 4 3D 任务与 LLMs ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")中，我们描述了 LLMs 如何作为具身代理与 3D 世界互动。最后，在第[4.6 节](https://arxiv.org/html/2405.10255v1#S4.SS6 "4.6 LLMs 用于 3D 生成 ‣ 4 3D 任务与 LLMs ‣ 当 LLMs 进入 3D 世界：通过多模态大型语言模型的 3D 任务调查与元分析")中，我们展示了 LLMs 如何作为助手生成语义多样的 3D 对象和场景。

此外，我们提供了[I](https://arxiv.org/html/2405.10255v1#S4.T1 "Table I ‣ 4.2 LLMs for Enhancing 3D Task Performance ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")表，以对比在三个轴上的 3D-LLMs 方法：3D 组件、LLMs 组件，以及 3D 视觉和语言的对齐，旨在提供对这个不断发展的领域内各种方法的高层次见解。

![参考说明](img/41f4bc8df41650b0be50d203c2f027d8.png)

图 3：LLM 方法的 3D 分类。在[4](https://arxiv.org/html/2405.10255v1#S4 "4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节中，我们从五个角度分析了 LLMs 在解决 3D 任务中所扮演的角色：增强 3D 任务、多任务学习、3D 多模态接口、具身代理和 3D 生成。

### 4.1 LLMs 如何处理 3D 场景信息？

传统的 LLMs 仅限于文本作为输入和输出，这使得处理 3D 信息的能力成为所有 3D-LLM 方法的主要关注点。一般的思路是将 3D 对象或场景信息映射到语言空间，使 LLMs 能够理解和处理这些 3D 输入。具体来说，这通常涉及两个步骤：（i）使用预训练的 3D 编码器处理相应的 3D 表示，生成原始的 3D 特征；（ii）使用对齐模块将这些 3D 特征转换为 LLMs 可以处理的 3D 令牌，类似于在[2.2.1](https://arxiv.org/html/2405.10255v1#S2.SS2.SSS1 "2.2.1 LLM Architectures ‣ 2.2 Large Language Model (LLM) ‣ 2 Background ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节中提到的令牌化过程。然后，预训练的 LLMs 可以在生成输出时使用这些对齐的 3D 令牌。

考虑到 3D 表示的多样性，如第[2.1 节](https://arxiv.org/html/2405.10255v1#S2.SS1 "2.1 3D Representations ‣ 2 Background ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")所述，获取 3D 特征的方式有很多种。如在表[I](https://arxiv.org/html/2405.10255v1#S4.T1 "Table I ‣ 4.2 LLMs for Enhancing 3D Task Performance ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")中的 3D 几何列所示，点云[[21](https://arxiv.org/html/2405.10255v1#bib.bib21), [24](https://arxiv.org/html/2405.10255v1#bib.bib24), [19](https://arxiv.org/html/2405.10255v1#bib.bib19), [171](https://arxiv.org/html/2405.10255v1#bib.bib171), [172](https://arxiv.org/html/2405.10255v1#bib.bib172), [267](https://arxiv.org/html/2405.10255v1#bib.bib267), [268](https://arxiv.org/html/2405.10255v1#bib.bib268), [269](https://arxiv.org/html/2405.10255v1#bib.bib269), [153](https://arxiv.org/html/2405.10255v1#bib.bib153), [270](https://arxiv.org/html/2405.10255v1#bib.bib270), [271](https://arxiv.org/html/2405.10255v1#bib.bib271), [266](https://arxiv.org/html/2405.10255v1#bib.bib266), [272](https://arxiv.org/html/2405.10255v1#bib.bib272)]由于其简单性和与各种预训练 3D 编码器的兼容性而最为常见，这使得它们成为多任务和多模态学习方法的热门选择。多视角图像[[11](https://arxiv.org/html/2405.10255v1#bib.bib11), [14](https://arxiv.org/html/2405.10255v1#bib.bib14), [17](https://arxiv.org/html/2405.10255v1#bib.bib17), [20](https://arxiv.org/html/2405.10255v1#bib.bib20), [270](https://arxiv.org/html/2405.10255v1#bib.bib270), [273](https://arxiv.org/html/2405.10255v1#bib.bib273)]也经常使用，因为 2D 特征提取的研究已经非常成熟，这意味着 3D 特征提取只需额外的 2D 到 3D 提升方案即可。RGB-D 数据通过深度相机轻松获得，通常用于 3D 嵌入体代理系统，以提取与视点相关的信息用于导航和理解。3D 场景图是一种更抽象的 3D 表示，在建模物体的存在及其关系方面表现出色，并能捕捉场景的高层信息。它们通常用于 3D 场景分类[[274](https://arxiv.org/html/2405.10255v1#bib.bib274)]和规划任务[[275](https://arxiv.org/html/2405.10255v1#bib.bib275)]。NeRFs 目前在 3D-LLM 方法中使用较少[[21](https://arxiv.org/html/2405.10255v1#bib.bib21)]。我们认为这是由于其隐式特性使其更难以进行标记化和与前馈神经网络集成。

目前的方法使用不同的架构（见图 [2](https://arxiv.org/html/2405.10255v1#S3.F2 "Figure 2 ‣ 3.5 Text-to-3D Generation (Text → 3D) ‣ 3 Tasks and Metrics ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")）和模块来将 3D 特征与 LLM 输入空间对齐（见表 [I](https://arxiv.org/html/2405.10255v1#S4.T1 "Table I ‣ 4.2 LLMs for Enhancing 3D Task Performance ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")）。对于仅接受 3D 输入的模型（图 [2](https://arxiv.org/html/2405.10255v1#S3.F2 "Figure 2 ‣ 3.5 Text-to-3D Generation (Text → 3D) ‣ 3 Tasks and Metrics ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")a），使用线性层 [[269](https://arxiv.org/html/2405.10255v1#bib.bib269), [24](https://arxiv.org/html/2405.10255v1#bib.bib24), [266](https://arxiv.org/html/2405.10255v1#bib.bib266)] 或 MLP [[171](https://arxiv.org/html/2405.10255v1#bib.bib171), [172](https://arxiv.org/html/2405.10255v1#bib.bib172)] 作为对齐模块，将 3D 特征转换为 LLM 输入空间。接受 3D 和文本作为输入的模型通常使用两个独立的分支来对齐 3D 特征和文本（图 [2](https://arxiv.org/html/2405.10255v1#S3.F2 "Figure 2 ‣ 3.5 Text-to-3D Generation (Text → 3D) ‣ 3 Tasks and Metrics ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")b）。一些研究 [[171](https://arxiv.org/html/2405.10255v1#bib.bib171), [172](https://arxiv.org/html/2405.10255v1#bib.bib172)] 使用单层原始变换器来允许 3D 对象特征在对齐过程中相互关注。其他研究，例如 [[270](https://arxiv.org/html/2405.10255v1#bib.bib270), [271](https://arxiv.org/html/2405.10255v1#bib.bib271)]，创建基于变换器的对齐模块，其中标准的变换器架构被调整以更好地适应不同类型的 3D 数据，如密集点云和稀疏 LiDAR 扫描。同时，文本使用预先存在的 LLM 文本嵌入表进行编码。其他研究 [[153](https://arxiv.org/html/2405.10255v1#bib.bib153), [268](https://arxiv.org/html/2405.10255v1#bib.bib268), [276](https://arxiv.org/html/2405.10255v1#bib.bib276)] 采用了 [[195](https://arxiv.org/html/2405.10255v1#bib.bib195)] 的 Q-Former 风格方法来对齐 3D 特征和文本（图 [2](https://arxiv.org/html/2405.10255v1#S3.F2 "Figure 2 ‣ 3.5 Text-to-3D Generation (Text → 3D) ‣ 3 Tasks and Metrics ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")c），引入固定长度的查询标记作为附加输入，并遵循基于 BERT 的结构来促进 3D 和文本特征在对齐过程中的互动。通常，这三种类型的架构通过利用 3D 标注数据集 [[218](https://arxiv.org/html/2405.10255v1#bib.bib218)] 来实现对齐，其中使用标注损失，即 LLM 生成的标注与场景简要的真实描述之间的交叉熵损失，来微调对齐模块，同时冻结预训练的 3D 特征提取器和 LLM。

最后，一些模型[[21](https://arxiv.org/html/2405.10255v1#bib.bib21)、[20](https://arxiv.org/html/2405.10255v1#bib.bib20)、[22](https://arxiv.org/html/2405.10255v1#bib.bib22)、[23](https://arxiv.org/html/2405.10255v1#bib.bib23)、[273](https://arxiv.org/html/2405.10255v1#bib.bib273)、[12](https://arxiv.org/html/2405.10255v1#bib.bib12)、[275](https://arxiv.org/html/2405.10255v1#bib.bib275)、[277](https://arxiv.org/html/2405.10255v1#bib.bib277)、[14](https://arxiv.org/html/2405.10255v1#bib.bib14)、[17](https://arxiv.org/html/2405.10255v1#bib.bib17)]使用了如 ChatGPT 这样的封闭源模型，并且完全没有训练对齐模块（图[2](https://arxiv.org/html/2405.10255v1#S3.F2 "Figure 2 ‣ 3.5 Text-to-3D Generation (Text → 3D) ‣ 3 Tasks and Metrics ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")d）。这些模型并不将 3D 特征与 LLM 输入空间对齐，而是直接从 3D 数据生成文本描述，例如描述 3D 边界框、位置和关系，或使用已有的标题。这些文本描述被输入到 ChatGPT 中。这些工作中没有提出额外的对齐模块，因此无需进行训练。

### 4.2 提升 3D 任务性能的 LLMs

在大量数据上训练的 LLMs 已被证明获得了有关世界的常识性知识[[278](https://arxiv.org/html/2405.10255v1#bib.bib278)]。LLMs 的世界知识和推理能力的潜力已经被探索，以增强 3D 场景理解和重新制定多个 3D 任务的流程。在这一部分，我们关注旨在利用 LLMs 改善现有 3D 视觉语言任务性能的方法。应用 LLMs 于 3D 任务时，我们可以将其使用分类为两个不同的组：知识增强型和推理增强型方法。知识增强型方法利用 LLMs 中蕴藏的丰富世界知识来提升 3D 任务性能。这可能提供上下文洞察，填补知识空白，或增强对 3D 环境的语义理解。相对而言，推理增强型方法则利用 LLMs 逐步推断的能力，从而提供更好的泛化能力，以应对更复杂的 3D 挑战。以下两个部分分别描述了这些方法。

3D 组件 LLM 组件 3D+LLM 方法 小节 3D 几何视觉模型 调优 LLM 能力 微调 LLM 基础 # 参数 硬件 对齐模块 日期 陈*等人* [[274](https://arxiv.org/html/2405.10255v1#bib.bib274)] 3.2 SG CLIP F WK 无 GPT2 1.5B 1 RTX3080 - 09/22 ConceptFusion [[18](https://arxiv.org/html/2405.10255v1#bib.bib18)] 3.2/3.4 RGB-D OpenSeg F IF/R 无 GPT3 175B 1 3090 - 02/23 ViewRefer [[20](https://arxiv.org/html/2405.10255v1#bib.bib20)] 3.2 MVI 多视图变换器 T WK 无 GPT3 175B 4 A100 变换器 03/23 LLM-Grounder [[21](https://arxiv.org/html/2405.10255v1#bib.bib21)] 3.2 PC/NeRF OpenScene/LERF F IF/ICL/R 无 GPT3.5/4 - - - 09/23 Abdelreheem *等人* [[22](https://arxiv.org/html/2405.10255v1#bib.bib22)] 3.2 网格视觉变换器 F IF/WK 无 GPT3.5 - 1 3090 - 09/23 Transcribe3D [[23](https://arxiv.org/html/2405.10255v1#bib.bib23)] 3.2 PC 无组变换器 F IF/R 无 GPT3.5/4 - - - 10/23 zero-shot 3DVG [[16](https://arxiv.org/html/2405.10255v1#bib.bib16)] 3.2 RGB-D Mask3d F IF/ICL/R 无 GPT3.5/4 - - 变换器 11/23 3DAP [[273](https://arxiv.org/html/2405.10255v1#bib.bib273)] 3.2 MVI - - IF/ICL PT GPT4V - - - 12/23 3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)] 3.3 PC Mask2Former/SAM F IF/ICL/R LF OPT/Flan-T5 9B/2.7B/3B 64 V100 QFormer 07/23 Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)] 3.3 PC Point-BERT F IF/ICL/R AF Vicuna 7B - 线性层 08/23 LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)] 3.3 PC/MVI OpenClip/PointNet++ F IF/ICL/R LoRA Vicuna 7B 8 A100 变换器 11/23 LL3DA [[19](https://arxiv.org/html/2405.10255v1#bib.bib19)] 3.3 PC/3D-BB ScanNet 场景编码器 F IF/ICL/R AF OPT 1.3B 8 3090 QFormer 11/23 Point-LLM [[267](https://arxiv.org/html/2405.10255v1#bib.bib267)] 3.3 PC Point-BERT F IF/ICL/R 完整 LLaMA 7B/13B 8 A100 线性层 12/23 GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)] 3.3 PC Point-BERT F IF/ICL/R LF OPT/Flan-T5 6.7B/3B 8 A100 QFormer 12/23 Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)] 3.3 PC Uni-3D F IF/ICL/R AF Vicuna 7B 4 A40 MLP 12/23 LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] 3.3 PC/VM VoxelNet F IF/ICL/R AF LLaMA 7B 4 A100 变换器 12/23 3DMIT [[269](https://arxiv.org/html/2405.10255v1#bib.bib269)] 3.3 PC EPCL/Uni3D F IF/ICL/R LoRA Vicuna 7B 8 A100 线性层 01/24 Scene-LLM [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)] 3.3 PC/VM ConceptFusion F IF/ICL/R LF LLaMA-2 7B 32 A100 线性层 03/24 Point-Bind [[272](https://arxiv.org/html/2405.10255v1#bib.bib272)] 3.4 PC I2P-MAE F IF/ICL/R LF LLaMA 7B 8 A100 线性层 09/23 JM3D-LLM [[279](https://arxiv.org/html/2405.10255v1#bib.bib279)] 3.4 PC PointNet++/PointMLP/Point-BERT F IF/ICL/R LF Vicuna 7B 3 A100 MLP 10/23 LLM-Planner [[12](https://arxiv.org/html/2405.10255v1#bib.bib12)] 3.5 VM Seg&Depth F IF/ICL/R 无 GPT3 175B - - 03/23 SayPlan [[275](https://arxiv.org/html/2405.10255v1#bib.bib275)] 3.5 SG SG 生成器 F IF/ICL/R 无 GPT4 - - - 07/23 VoxPoser [[13](https://arxiv.org/html/2405.10255v1#bib.bib13)] 3.5 RGB-D OWL-ViT/SAM F IF/ICL/R 无 GPT4 - - - 07/23 UniHSI [[277](https://arxiv.org/html/2405.10255v1#bib.bib277)] 3.5 RGB-D - - IF/ICL/R 无 GPT3.5/4 - 1 A100 - 09/23 LAN-grasp [[14](https://arxiv.org/html/2405.10255v1#bib.bib14)] 3.5 MVI OWL-ViT F IF/ICL/R 无 GPT4 - - - 10/23 Agent3D-Zero [[17](https://arxiv.org/html/2405.10255v1#bib.bib17)] 3.3/3.5 MVI - - IF/ICL/R PT GPT4V - - - 03/24 NaviLLM [[11](https://arxiv.org/html/2405.10255v1#bib.bib11)] 3.5 MVI EVA-CLIP-Large F IF/ICL/R LF Vicuna 7B 8 A100 变换器 12/23 MultiPLY [[24](https://arxiv.org/html/2405.10255v1#bib.bib24)] 3.3/3.4/3.5 PC ConceptGraph T IF/ICL/R AF Vicuna 13B 128 V100 线性层 01/24 ManipLLM [[15](https://arxiv.org/html/2405.10255v1#bib.bib15)] 3.5 RGB-D CLIP F IF/ICL/R AF LLaMA 7B 1 A100 线性层 03/24 3D-VLA [[276](https://arxiv.org/html/2405.10255v1#bib.bib276)] 3.3/3.5 PC/MVI Mask2Former/SAM F IF/ICL/R LoRA Flan-T5 3B 384 V100 QFormer 03/24 PolyGen [[280](https://arxiv.org/html/2405.10255v1#bib.bib280)] 3.6 n-gon 网格 自定义变换器 F - 完整 自定义 - 4 V100 - 02/20 LLMR [[281](https://arxiv.org/html/2405.10255v1#bib.bib281)] 3.6 Unity, 网格 Dall-E-2, CLIP F IF/ICL/R 无 GPT4 - 1 3080 - 09/23 3D-GPT [[26](https://arxiv.org/html/2405.10255v1#bib.bib26)] 3.6 Blender, 网格 - - IF/R 无 GPT3.5/4 - - - 10

表 I：3D-LLMs 方法汇总。3D 几何列收集每种方法使用的 3D 几何信息，如点云（PC）、多视图图像（MVI）、RGB+深度（RGB-D）、3D 边界框（3D-BB）、场景图（SG）、体素图（VM）和 NeRF。调优列概述了视觉模型在训练过程中是否进行了微调（真/假）。IF、ICL、R 和 WK 分别表示指令跟随、上下文学习、推理和世界知识的 LLM 能力。微调列总结了 LLM 组件的微调方式，如提示微调（PT）、低秩适应（LoRA）、自适应微调（AF）、层冻结（LF）或完全微调（Full）。硬件列显示了训练方法是否涉及使用 Nvidia GPU 的数量和具体 GPU 类型或没有训练。

#### 4.2.1 知识增强方法

有几种方法利用 LLM 的世界知识。Chen *et al.* [[274](https://arxiv.org/html/2405.10255v1#bib.bib274)] 使用 LLMs 进行 RGB-D 图像的 3D 房间分类。在这里，LLMs 中嵌入的知识用于根据房间中包含的物体类别信息确定房间类别。首先，这种方法从 Matterport3D [[285](https://arxiv.org/html/2405.10255v1#bib.bib285)] 数据中创建场景图，节点包括区域和物体，对象节点链接到房间节点。接下来，选择关键对象形成每种房间类型的查询。LLMs 对从选择的对象中提取的描述进行评分，最高得分预测房间标签。空间信息如尺寸或位置也可以提供。

ViewRefer [[20](https://arxiv.org/html/2405.10255v1#bib.bib20)] 使用大型语言模型（LLMs）通过视图相关的描述扩展基础文本。例如，给定原始文本“面对沙发的前方，沙发右侧的桌子”，LLM 被用来创建一个类似的句子，但从另一个说话者的视角，例如“背对沙发的前方，选择沙发左侧的桌子”。通过对输入文本及其对立视图同义词进行多次改写，模型提高了跨视图的基础对接。它还采用了一个融合变换器，具有视图间注意机制，并包含可学习的多视图原型，这些原型捕捉了视图间的知识，并进一步提升了 3D 基础对接性能。

Abdelreheem *et al.* [[22](https://arxiv.org/html/2405.10255v1#bib.bib22)] 解决了 3D 形状中的语义对应问题。他们通过将渲染的视图输入到 BLIP2 模型中来分类 3D 形状，以生成类别提议列表。ChatGPT [[286](https://arxiv.org/html/2405.10255v1#bib.bib286)] 将这些提议统一为每个形状的单一类别。ChatGPT 还生成语义部件名称和成对映射（例如，手臂 $\rightarrow$ 翼）。然后，3D 分割器基于语义区域对形状进行分割，利用部件映射生成稀疏对应图。

上述知识增强策略在没有特定对象或场景类型的标注 3D 数据的零样本场景中表现出色。这允许对对象部件、关系和语义进行开放式推理，超越固定的本体论，正如 (i) 陈 *等* [[274](https://arxiv.org/html/2405.10255v1#bib.bib274)] 生成空间和语义对象描述，(ii) ViewRefer [[20](https://arxiv.org/html/2405.10255v1#bib.bib20)] 描述多视角对象关系，以及 (iii) Abdelreheem *等* [[22](https://arxiv.org/html/2405.10255v1#bib.bib22)] 在不同形状之间生成和匹配对象部件语义所示。

| 方法 |
| --- |

&#124; 对象 &#124;

&#124; 标注 &#124;

|

&#124; 场景 &#124;

&#124; 标注 &#124;

|

&#124; 稠密 &#124;

&#124; 标注 &#124;

| 定位 | QA |
| --- | --- |

&#124; 情境 &#124;

&#124; QA &#124;

| 对话 | 规划 | 导航 | 操作 |
| --- | --- | --- | --- |
| 3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)] | ✓ | ✓ |  | ✓ | ✓ |  | ✓ | ✓ | ✓ |  |
| Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)] | ✓ |  |  |  | ✓ |  |  |  |  |  |
| LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)] | ✓ | ✓ |  |  | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| LL3DA [[19](https://arxiv.org/html/2405.10255v1#bib.bib19)] | ✓ | ✓ | ✓ |  | ✓ |  | ✓ | ✓ |  |  |
| PointLLM [[267](https://arxiv.org/html/2405.10255v1#bib.bib267)] | ✓ |  |  |  | ✓ |  | ✓ |  |  |  |
| GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)] | ✓ |  |  |  | ✓ |  | ✓ |  |  |  |
| Chat-3D V2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)] | ✓ | ✓ | ✓ | ✓ | ✓ |  |  |  |  |  |
| LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] | ✓ | ✓ |  | ✓ | ✓ | ✓ |  | ✓ | ✓ |  |
| 3DMIT [[269](https://arxiv.org/html/2405.10255v1#bib.bib269)] | ✓ | ✓ |  | ✓ | ✓ |  | ✓ |  |  |  |
| MultiPLY [[24](https://arxiv.org/html/2405.10255v1#bib.bib24)] | ✓ |  |  |  | ✓ | ✓ | ✓ |  | ✓ |  |
| 3D-VLA [[276](https://arxiv.org/html/2405.10255v1#bib.bib276)] | ✓ |  | ✓ | ✓ | ✓ | ✓ |  | ✓ |  | ✓ |
| Agent3D-Zero [[17](https://arxiv.org/html/2405.10255v1#bib.bib17)] |  | ✓ |  | ✓ | ✓ |  | ✓ | ✓ | ✓ | ✓ |
| Scene-LLM [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)] | ✓ |  | ✓ |  | ✓ |  | ✓ | ✓ |  |  |

表 II: 比较各种 3D 多任务学习方法所包含的任务。QA 代表问题回答。这些方法按时间顺序从上到下（从最早到最近）排序。

#### 4.2.2 推理增强方法

除了世界知识，LLMs 的推理能力还帮助解决其他 3D 任务，特别是在具有详细几何形状和多个物体的复杂 3D 场景中的视觉基础。在这种情况下，物体的文本描述应包括其外观和与周围物体的空间关系。普通的基础方法 [[287](https://arxiv.org/html/2405.10255v1#bib.bib287)] 通常在这种环境下表现不佳，因为它们无法理解详细的文本描述。LLM-Grounder [[21](https://arxiv.org/html/2405.10255v1#bib.bib21)]、Transcribe3D [[23](https://arxiv.org/html/2405.10255v1#bib.bib23)] 和零样本 3DVG [[16](https://arxiv.org/html/2405.10255v1#bib.bib16)] 通过利用 LLMs 的推理能力分析文本描述，并生成一系列指令来定位物体，使用现有的基础工具箱。具体来说，LLM 首先从文本描述中识别锚点和目标物体。然后，它基于基础工具返回的坐标分析多个候选物体之间的空间关系（或描述的属性），以选择最符合文本描述的候选物体。此外，(i) Transcribe3D [[23](https://arxiv.org/html/2405.10255v1#bib.bib23)] 和 LLM-Grounder [[21](https://arxiv.org/html/2405.10255v1#bib.bib21)] 采用多轮互动问答过程来帮助用户澄清他们的意图，促使他们提供更多信息的指令以获得更准确的结果，而(ii) LLM-Grounder 包括多种基础工具选择，如 OpenScene [[29](https://arxiv.org/html/2405.10255v1#bib.bib29)] 或 LERF [[30](https://arxiv.org/html/2405.10255v1#bib.bib30)]，以适应不同的 3D 表示，如点云或 NeRF。这些方法的一个共同缺点是 LLM 的“盲点”，因为它仅提供 3D 场景的抽象文本描述，而不是场景的原始点云。这可能导致关键场景细节的丧失。因此，当 3D 场景包含多个相同类别的物体时，缺乏必要的场景细节意味着文本引用的歧义无法解决，这限制了整体性能。

除了视觉基础，LLMs 的推理能力还促进了其他任务。3DAP [[273](https://arxiv.org/html/2405.10255v1#bib.bib273)] 利用 GPT-4V 通过视觉提示技术从 2D 图像中推断物体的 3D 信息，其中它通过 3D 坐标轴标注输入图像，以增强 LLM 对 3D 尺度的感知。ConceptFusion [[18](https://arxiv.org/html/2405.10255v1#bib.bib18)] 使用 GPT3 生成指令，利用预定义的基本空间比较模块，通过其提出的 3D 特征图来实现更复杂的空间推理。

### 4.3 LLMs 用于 3D 多任务学习

许多研究致力于利用 LLMs 的指令跟随和上下文学习能力，将多个 3D 任务统一到一个语言空间中。通过使用不同的文本提示来标记不同的任务，这些研究旨在使 LLMs 作为统一的对话接口。使用 LLM 实现多任务学习通常涉及几个关键步骤，首先是构建 3D-文本数据对 [[19](https://arxiv.org/html/2405.10255v1#bib.bib19), [153](https://arxiv.org/html/2405.10255v1#bib.bib153), [270](https://arxiv.org/html/2405.10255v1#bib.bib270)]。这些数据对需要以文本形式编写任务指令，并定义每个不同任务的输出。接下来，将 3D 数据（通常是点云形式）输入到 3D 编码器中 [[288](https://arxiv.org/html/2405.10255v1#bib.bib288), [34](https://arxiv.org/html/2405.10255v1#bib.bib34)] 以提取 3D 特征。对齐模块 [[171](https://arxiv.org/html/2405.10255v1#bib.bib171), [153](https://arxiv.org/html/2405.10255v1#bib.bib153), [172](https://arxiv.org/html/2405.10255v1#bib.bib172), [266](https://arxiv.org/html/2405.10255v1#bib.bib266)] 随后用于 (i) 在多个层次（对象级别、关系级别和场景级别）对齐 3D 特征与来自 LLMs 的文本嵌入，以及 (ii) 将 3D 特征转换为 LLMs 可解释的标记。最后，需要选择适当的训练策略 [[272](https://arxiv.org/html/2405.10255v1#bib.bib272), [19](https://arxiv.org/html/2405.10255v1#bib.bib19), [153](https://arxiv.org/html/2405.10255v1#bib.bib153), [270](https://arxiv.org/html/2405.10255v1#bib.bib270), [269](https://arxiv.org/html/2405.10255v1#bib.bib269)]，例如单阶段或多阶段的 3D-语言对齐训练和多任务指令微调。

在本节的剩余部分，我们将详细探讨这些方面。我们还在表 [II](https://arxiv.org/html/2405.10255v1#S4.T2 "Table II ‣ 4.2.1 Knowledge-enhanced approaches ‣ 4.2 LLMs for Enhancing 3D Task Performance ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models") 中总结了本节回顾的每种方法的范围和能力。

#### 4.3.1 多任务学习的数据

如表[II](https://arxiv.org/html/2405.10255v1#S4.T2 "Table II ‣ 4.2.1 Knowledge-enhanced approaches ‣ 4.2 LLMs for Enhancing 3D Task Performance ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")所示，我们将任务分为四类：标题生成、定位、问答（QA）和具身智能体任务（即规划、导航和操作）。因此，每类任务的文本输出遵循预定义的格式。对于标题生成和问答任务，输出为纯文本，并且没有特定的格式限制。定位任务的输出是一个 3D 边界框，通常是指对象中心的坐标以及其 3D 尺寸。通常，点和尺寸的值被归一化到 0-255 的范围内[[19](https://arxiv.org/html/2405.10255v1#bib.bib19)]，这限制了 LLM 需要预测的 token 范围。对于规划，模型输出一系列步骤来执行任务，以文本形式呈现；而对于导航，输出是一系列空间坐标。对于操作，输出是文本形式的动作序列。现有方法遵循这些指南来构建它们的多任务指令微调数据集。

一旦确定了文本格式，不同的方法会采用不同的策略来为其数据集获取文本注释。一些方法利用人工标注员为每个样本生成“真实值”注释[[218](https://arxiv.org/html/2405.10255v1#bib.bib218), [228](https://arxiv.org/html/2405.10255v1#bib.bib228), [234](https://arxiv.org/html/2405.10255v1#bib.bib234), [233](https://arxiv.org/html/2405.10255v1#bib.bib233)]，然而这可能是一个昂贵且耗时的过程。另一种方法是使用 ChatGPT [[286](https://arxiv.org/html/2405.10255v1#bib.bib286)] 为每个样本生成文本注释，这是 3DMIT [[269](https://arxiv.org/html/2405.10255v1#bib.bib269)]、LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)]、Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)] 和 Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)] 等方法所采用的策略。在这种方法中，3D 场景数据被转换为文本（通常通过文字描述对象边界框和空间关系），并创建任务描述以说明期望的输出。为了引导 ChatGPT 朝着期望的任务输出格式进行，提供了示例，这允许 ChatGPT 通过上下文学习生成其他 3D 场景的合理文本注释。另一种选择是通过简单地合并现有的 3D 视觉-语言 (VL) 数据集 [[218](https://arxiv.org/html/2405.10255v1#bib.bib218), [228](https://arxiv.org/html/2405.10255v1#bib.bib228), [234](https://arxiv.org/html/2405.10255v1#bib.bib234), [153](https://arxiv.org/html/2405.10255v1#bib.bib153)] 来构建其他多任务数据集 [[19](https://arxiv.org/html/2405.10255v1#bib.bib19), [266](https://arxiv.org/html/2405.10255v1#bib.bib266)]。一些多任务数据集是使用这三种方法的组合构建的，例如 LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]、LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] 和 3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]，旨在结合人工注释的准确性与通过使用 LLM 生成的注释提供的可扩展性。

#### 4.3.2 训练一个多任务 3D 的 LLM

训练用于多种 3D 任务的 LLM 的第一步涉及获取有意义的 3D 特征，其中提取方法根据 3D 场景的类型有所不同。对于单个物体的点云，Point-LLM [[267](https://arxiv.org/html/2405.10255v1#bib.bib267)]、Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)]和 GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)]使用 Point-BERT [[288](https://arxiv.org/html/2405.10255v1#bib.bib288)]来提取 3D 物体特征。对于室内场景，LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]使用 PointNet++ [[34](https://arxiv.org/html/2405.10255v1#bib.bib34)]进行特征提取，而 Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)]和 3DMIT [[269](https://arxiv.org/html/2405.10255v1#bib.bib269)]则对场景进行分割，并使用 Uni-3D [[289](https://arxiv.org/html/2405.10255v1#bib.bib289)]提取每个分割部分的特征。同时，MultiPLY [[24](https://arxiv.org/html/2405.10255v1#bib.bib24)]将提取的物体特征整合到一个场景图 [[290](https://arxiv.org/html/2405.10255v1#bib.bib290)]中，以表示整个场景。3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]和 Scene-LLM [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)]将 2D 多视图图像中的特征提升为 3D 表示。3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]从 Mask2Former [[291](https://arxiv.org/html/2405.10255v1#bib.bib291)]或 SAM [[211](https://arxiv.org/html/2405.10255v1#bib.bib211)]中提升 2D 语义特征。Scene-LLM [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)]遵循 ConceptFusion [[18](https://arxiv.org/html/2405.10255v1#bib.bib18)]融合全局信息和局部细节，将像素级的 CLIP 特征映射到点级 3D 特征。对于户外 3D 场景，LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)]使用 VoxelNet [[292](https://arxiv.org/html/2405.10255v1#bib.bib292)]提取 3D 体素特征。

关于对齐模块，如第[4.1 节](https://arxiv.org/html/2405.10255v1#S4.SS1 "4.1 How do LLMs process 3D scene information? ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")所讨论的，使用了各种网络架构。值得注意的是，MultiPLY [[24](https://arxiv.org/html/2405.10255v1#bib.bib24)]采用不同的线性层来对齐来自每种模态的特征。Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)]和 Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)]使用单层 vanilla transformer 来使 3D 对象特征在对齐过程中相互关注。LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]和 LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)]利用改进的 transformers 作为它们的对齐模块，以更好地适应不同类型的 3D 数据（密集点云与稀疏 LiDAR）。LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]修改了自注意机制，以明确编码点云中对象对之间的空间关系。相比之下，LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)]则采用了自注意和交叉注意机制来将鸟瞰图（BEV）特征与文本特征对齐。3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]和 GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)]采用 Q-Former，而 LL3DA[[19](https://arxiv.org/html/2405.10255v1#bib.bib19)]在 Q-Former 上添加了一个额外的分支，使查询令牌可以与用户提供的视觉提示进行交互。

LLMs 可以通过第[2.2.3](https://arxiv.org/html/2405.10255v1#S2.SS2.SSS3 "2.2.3 LLM Fine-tuning ‣ 2.2 Large Language Model (LLM) ‣ 2 Background ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")节中讨论的不同策略进行微调，以融入多种 3D 任务。LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)] 和 3DMIT [[269](https://arxiv.org/html/2405.10255v1#bib.bib269)] 使用低秩适应（LoRA）进行微调。因此，包括对齐模块和 3D 编码器在内的总可训练参数不到原始 LLMs 参数的 10%，显著提高了训练效率。Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)]、LL3DA [[19](https://arxiv.org/html/2405.10255v1#bib.bib19)]、Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)]、LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] 和 MultiPLY [[24](https://arxiv.org/html/2405.10255v1#bib.bib24)] 采用自适应微调。具体来说，这些模型包括将 3D 场景中的空间信息与语言对齐的模块，例如一个 transformer 层，以捕捉物体关系。这些模块与预训练的 3D 编码器和 LLMs 一同进行对齐微调。3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]、Scene-LLM [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)]、Point-LLM [[267](https://arxiv.org/html/2405.10255v1#bib.bib267)] 和 GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)] 采用层冻结。通过冻结大多数 LLM 层并微调如嵌入层等特定层，这一策略保留了语言能力，同时提高了 3D 理解能力。最后，Agent3D-Zero [[17](https://arxiv.org/html/2405.10255v1#bib.bib17)] 使用提示微调，这是一种无训练的引导 LLMs 理解 3D 任务的方法。这种方法利用量身定制的提示，在 3D 场景的 BEV 图像上添加网格线和刻度标记，帮助 2D VLMs 理解 3D 几何。

训练这些模型以进行 3D 多任务学习还涉及到 3D 语言特征对齐的微调。Point-LLM [[267](https://arxiv.org/html/2405.10255v1#bib.bib267)]、3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]、Scene-LLM [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)]、LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]和 GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)]都采用了单阶段对齐方法。具体而言，Point-LLM [[267](https://arxiv.org/html/2405.10255v1#bib.bib267)]仅使用标注数据训练 MLP，并额外更新输入嵌入层以适应新添加的标记，标记点云标记的开始和结束（$\langle$p_start$\rangle$，$\langle$p_end$\rangle$）。3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)]使用自定义数据集来训练对齐模块，同时更新输入和输出嵌入层的权重，以适应新添加的位置标记。Scene-LLM [[266](https://arxiv.org/html/2405.10255v1#bib.bib266)]仅训练一个线性层，使 LLMs 能够理解自我中心和场景中心的视角，通过在相机和世界坐标系中使用 3D 帧-语言对任务来实现。同时，它也更新输入嵌入层以适应新添加的标记，标记 3D 标记的开始和结束（$\langle$3D$\rangle$，$\langle$/3D$\rangle$）。LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]也使用标注任务训练对齐模块，但独特地收集了三种类型的标注数据：对象级别 [[293](https://arxiv.org/html/2405.10255v1#bib.bib293)]、场景中的对象 [[228](https://arxiv.org/html/2405.10255v1#bib.bib228)、[294](https://arxiv.org/html/2405.10255v1#bib.bib294)]和场景级别 [[295](https://arxiv.org/html/2405.10255v1#bib.bib295)]，使用所有三种数据集训练其对齐模块。GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)]遵循 BLIP2 [[195](https://arxiv.org/html/2405.10255v1#bib.bib195)]的结构和训练策略，通过三个任务实现对齐：点-文本对比（PTC）、点-文本匹配（PTM）和点标注生成（PTG）。

与这些单阶段对齐方法相比，LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)]、Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)]和 Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)]各自采用了 2 阶段的 3D 语言对齐过程。LiDAR-LLM [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)]专注于通过 3D 描述任务提升局部和全局场景感知，分两个阶段进行：首先，集中于单视角描述，然后扩展到全景场景描述。他们通过描述和基础任务的结合发展实例级别的感知能力。Chat-3D [[171](https://arxiv.org/html/2405.10255v1#bib.bib171)]首先使用 3D 对象分类数据集 [[296](https://arxiv.org/html/2405.10255v1#bib.bib296)、[293](https://arxiv.org/html/2405.10255v1#bib.bib293)、[297](https://arxiv.org/html/2405.10255v1#bib.bib297)]将 3D 对象与文本对齐，旨在通过仅更新对齐模块来最大化映射的 3D 对象特征与对象类别词嵌入之间的余弦相似度。在场景级别对齐的第二阶段，它利用 ScanRefer [[218](https://arxiv.org/html/2405.10255v1#bib.bib218)]来启用描述能力，专门更新一个额外的变换层以建模对象的空间关系。类似地，Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)]结合了对象级别和场景级别的对齐，第二阶段额外训练了一个位置嵌入层。为了提高训练效率，LL3DA [[19](https://arxiv.org/html/2405.10255v1#bib.bib19)]和 3DMIT [[269](https://arxiv.org/html/2405.10255v1#bib.bib269)]跳过了对齐阶段，专注于下面描述的指令微调阶段。

几乎所有的多任务学习方法**最终**都需要基于指令完成各种 3D 任务。因此，作为训练的**最终**阶段，每种方法通常使用自己构建的多任务指令跟随数据集进行指令微调¹¹1 指令微调指的是在由（指令，输出）对组成的数据集上进一步微调 LLMs 的过程[[298](https://arxiv.org/html/2405.10255v1#bib.bib298)]。由于所有任务输出都统一为文本形式，使用的训练损失是 LLMs 中标准的自回归损失。这个阶段通常涉及对齐模块和 LLM 的联合训练。一个例外是 Agent3D-Zero [[17](https://arxiv.org/html/2405.10255v1#bib.bib17)]，它通过将来自不同视角的 2D 图像输入到 GPT4V 中来完成各种 3D 任务，因此不需要任何训练。

### 4.4 LLMs 作为 3D 多模态接口

除了探索 3D 多任务学习者外，一些近期研究还将跨不同模态的信息纳入进来，以进一步提高模型的能力并实现新颖的交互。除了文本和 3D 场景，多模态 3D-LLMs 还可能将 2D 图像、音频或触摸信息作为输入纳入场景。

大多数工作旨在构建跨不同模态的共同表示空间。由于一些现有工作[[299](https://arxiv.org/html/2405.10255v1#bib.bib299), [300](https://arxiv.org/html/2405.10255v1#bib.bib300)] 已经提供了将文本、图像或音频映射到共同空间的预训练编码器，一些工作选择学习一个 3D 编码器，将 3D 嵌入对齐到其他模态的预训练编码器的嵌入空间。JM3D-LLM [[279](https://arxiv.org/html/2405.10255v1#bib.bib279)] 学习了一个 3D 点云编码器，将点云的嵌入空间对齐到 SLIP [[301](https://arxiv.org/html/2405.10255v1#bib.bib301)] 的文本-图像嵌入空间。在训练过程中，它渲染点云的一系列图像，并构建一个层次化的文本树，以实现详细的对齐。Point-Bind [[272](https://arxiv.org/html/2405.10255v1#bib.bib272)] 也学习了类似的 3D 编码器，并将其对齐到 ImageBind [[302](https://arxiv.org/html/2405.10255v1#bib.bib302)]，以统一图像、文本、音频和点云的嵌入空间。这使得可以使用不同的任务头来处理各种模态之间的检索、分类和生成等不同任务。然而，一个显著的限制是这种方法仅适用于小规模的对象级场景，因为对于一个 3D 编码器来说，处理包含数百万个点的大场景在计算上是昂贵的。此外，大多数预训练的多模态编码器，如 CLIP，都是为单一对象场景设计的，不适用于具有多个对象和局部细节的大型场景。

大场景需要更为细致的设计来融合多种模态。ConceptFusion[[18](https://arxiv.org/html/2405.10255v1#bib.bib18)]构建了一个增强的特征图，将全球信息和每个组成图像的局部细节融合在一起。这是通过使用已经对不同模态（包括文本和音频）对齐的预训练特征提取器[[187](https://arxiv.org/html/2405.10255v1#bib.bib187), [188](https://arxiv.org/html/2405.10255v1#bib.bib188)]来实现的。然后，利用传统的 SLAM 方法将特征图映射到场景的点云上。MultiPLY[[24](https://arxiv.org/html/2405.10255v1#bib.bib24)]采用了类似于 ConceptGraph[[290](https://arxiv.org/html/2405.10255v1#bib.bib290)]的表示方法。它识别场景中的所有显著物体，获取每个物体的全局嵌入，最后构建场景图。最终的表示是与 Llama[[140](https://arxiv.org/html/2405.10255v1#bib.bib140)]的嵌入空间对齐的场景嵌入。包括音频、温度和触觉在内的其他模态的嵌入也可以通过线性投影映射到相同的空间。所有嵌入被标记化并一次性发送到 LLM。与对象级场景的方法相比，可以处理大场景的方法通过依赖预训练的编码器来弥合模态差距，减少了成本，而不是从头学习新的编码器。

### 4.5 具身智能体的 LLMs

3D 具身智能体可以利用 LLMs 的规划、工具使用和决策能力来创建。这些能力使 LLMs 能够生成涵盖 3D 环境内导航[[270](https://arxiv.org/html/2405.10255v1#bib.bib270), [275](https://arxiv.org/html/2405.10255v1#bib.bib275), [11](https://arxiv.org/html/2405.10255v1#bib.bib11)]、与物体的交互[[14](https://arxiv.org/html/2405.10255v1#bib.bib14)]以及选择合适的工具执行特定任务[[24](https://arxiv.org/html/2405.10255v1#bib.bib24)]的智能决策。该部分描述了 3D 具身智能体如何执行规划、导航和操作任务。

#### 4.5.1 3D 任务规划

对于具身智能体而言，“任务规划”指的是在给定任务描述和 3D 环境的情况下，生成执行特定任务的步骤的能力。任务规划通常是导航和操作任务的先决条件[[12](https://arxiv.org/html/2405.10255v1#bib.bib12), [275](https://arxiv.org/html/2405.10255v1#bib.bib275)]，因为规划的准确性直接影响后续任务的表现。

LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)] 和 LLM-Planner [[12](https://arxiv.org/html/2405.10255v1#bib.bib12)] 利用大型语言模型（LLMs）生成逐步计划，并根据环境感知动态调整。LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)] 强调基于当前场景配置的场景感知规划，而 LLM-Planner [[12](https://arxiv.org/html/2405.10255v1#bib.bib12)] 采用 GPT3 [[127](https://arxiv.org/html/2405.10255v1#bib.bib127)] 将规划分解为高层次子目标和低层次动作，并在任务执行过程中遇到困难时重新规划。3D-VLA [[276](https://arxiv.org/html/2405.10255v1#bib.bib276)] 通过生成世界模型整合了 3D 感知、推理和行动。它通过利用生成模型预测未来状态表示（例如目标图像和点云）来增强规划能力。Agent3D-Zero [[17](https://arxiv.org/html/2405.10255v1#bib.bib17)] 引入了 Set-of-Line Prompting (SoLP)，通过生成多样的观察视角来增强视觉语言模型（VLM）对场景几何特征的理解。具体来说，SoLP 在 BEV 图像上叠加网格线和刻度标记，并提示 VLM 提供更准确的相机位置和方向，从而使 VLM 能够理解 3D 空间概念。UniHSI [[277](https://arxiv.org/html/2405.10255v1#bib.bib277)] 解决了人类-场景互动（HSI）的任务，即根据输入的语言命令生成在 3D 环境中人类与物体之间的互动。它使用大型语言模型作为规划工具，将语言命令转换为任务计划，表示为“接触链”（Chains of Contacts, CoC），这是一种表示人类关节点和物体位置之间时间关系的序列。虽然上述方法专注于单一场景中的规划，但 SayPlan [[275](https://arxiv.org/html/2405.10255v1#bib.bib275)] 能够处理多个房间和楼层，通过 (i) 利用 3D 场景图进行语义搜索，以及 (ii) 结合经典路径规划与迭代重新规划流程进行计划优化。

#### 4.5.2 3D 导航

3D 导航指的是具身体代理在 3D 环境中移动和定位的能力，通常基于视觉输入和语言指令。每种描述的方法——LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]、Agent3D-Zero [[17](https://arxiv.org/html/2405.10255v1#bib.bib17)]、LLM-Planner [[12](https://arxiv.org/html/2405.10255v1#bib.bib12)] 和 NaviLLM [[11](https://arxiv.org/html/2405.10255v1#bib.bib11)]——以不同的方式实现 3D 导航。LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)] 处理自我中心的 2D 图像和物体中心的 3D 点云，以及文本指令。它生成一系列对应于可执行导航命令的动作标记，如‘前进’或‘右转’。LEO 采用‘最短路径导航试验’，与人类演示相比，提供了一个噪声更少、更直接的学习环境。Agent3D-Zero [[17](https://arxiv.org/html/2405.10255v1#bib.bib17)] 通过不断选择新的视点来进行导航，基于对环境的评估。它结合了来自先前视点的历史数据，以优化其导航路径，向特定目标前进，例如在办公室环境中找到打印机。LLM-Planner [[12](https://arxiv.org/html/2405.10255v1#bib.bib12)] 采用分层方法，首先生成作为子目标序列的高层次计划，然后由低层次规划器将其转换为一系列原始动作。这使得整体过程可以适应即时环境。NaviLLM [[11](https://arxiv.org/html/2405.10255v1#bib.bib11)] 将各种具身导航任务转化为生成问题，使用基于模式的指令。这些指令包括 $4$ 个元素：由词序列定义的任务、所有可达视点的观察、过去视觉观察的历史，以及指导动作生成的输出提示（例如选择方向或物体）。

#### 4.5.3 3D 物体操作

在 3D 具身体代理的背景下，操作指的是它们与物体进行物理互动的能力，从移动物体到复杂的序列，如组装部件或开门。使 LLM 执行操作任务的核心思想在于将动作序列标记化。为了让 LLM 输出特定动作，首先需要定义允许 LLM 生成这些动作的动作标记，这些标记基于任务和 3D 场景上下文。随后，像 CLIPort [[242](https://arxiv.org/html/2405.10255v1#bib.bib242)] 或机器人手臂中的运动规划模块将这些标记化的动作转化为由代理执行的物理运动。

LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)]、MultiPLY [[24](https://arxiv.org/html/2405.10255v1#bib.bib24)] 和 3D-VLA [[276](https://arxiv.org/html/2405.10255v1#bib.bib276)] 各自使用不同的动作标记将口头或书面指令转换为机器人在三维空间中的动作。LEO [[270](https://arxiv.org/html/2405.10255v1#bib.bib270)] 使用了超过 500 个特定标记，以使机器人动作更加精确。具体来说，对于 CLIPort [[242](https://arxiv.org/html/2405.10255v1#bib.bib242)] 任务，动作姿势通过 516 个标记进行编码：320 个标记用于 x 轴姿势区间，160 个标记用于 y 轴，36 个标记用于 z 轴旋转区间。MultiPLY [[24](https://arxiv.org/html/2405.10255v1#bib.bib24)] 在此基础上扩展了功能，引入了如 $\langle$SELECT$\rangle$（用于对象交互）、$\langle$NAVIGATE$\rangle$（用于移动）、$\langle$OBSERVE$\rangle$（用于观察）、$\langle$TOUCH$\rangle$（用于触觉反馈）、$\langle$HIT$\rangle$（用于听觉反馈）、$\langle$PICK-UP$\rangle$ 和 $\langle$PUT-DOWN$\rangle$（用于操作）、以及 $\langle$LOOK-AROUND$\rangle$（用于感知）的标记。这种方法还整合了触觉、温度和听觉等感官反馈，增强了机器人与其环境的互动。3D-VLA [[276](https://arxiv.org/html/2405.10255v1#bib.bib276)] 则包含了（i）对象标记（$\langle$obj$\rangle$$\langle$/obj$\rangle$）用于识别被操作的对象，（ii）位置标记（$\langle$loc0-255$\rangle$）用于空间定位，以及（iii）用于机器人动作的专用标记，如手臂位置/旋转/抓手状态。这些标记通过 $\langle$ACT SEP$\rangle$ 分隔。这种标记结构使得理解和执行复杂的三维操作成为可能。

尽管这些系统使机器人能够通过将指令映射到动作来执行复杂任务，但它们忽视了对可操控对象的语义理解，并且通常无法区分适合和不适合操作的部件。为了解决这个问题，VoxPoser [[13](https://arxiv.org/html/2405.10255v1#bib.bib13)], LAN-grasp [[14](https://arxiv.org/html/2405.10255v1#bib.bib14)], 和 ManipLLM [[15](https://arxiv.org/html/2405.10255v1#bib.bib15)] 关注“可操作性”，并创建可操作性地图来表示对象及其周围的特征，这些特征可以用于执行特定任务，如可抓取的手柄 [[14](https://arxiv.org/html/2405.10255v1#bib.bib14), [15](https://arxiv.org/html/2405.10255v1#bib.bib15)], 可按压的按钮 [[15](https://arxiv.org/html/2405.10255v1#bib.bib15)], 或可移动的对象 [[13](https://arxiv.org/html/2405.10255v1#bib.bib13)]。具体而言，VoxPoser [[13](https://arxiv.org/html/2405.10255v1#bib.bib13)]使用 LLM 来分解自由形式的语言指令，推断可操作性和约束，并通过与 VLMs 交互使用代码接口来组成 3D 体素地图。这些地图能够生成对动态变化具有鲁棒性的闭环机器人轨迹，并具备在接触丰富环境中从在线经验中学习的能力。LAN-grasp [[14](https://arxiv.org/html/2405.10255v1#bib.bib14)]利用基础模型通过结合多个模型来加深机器人对对象的理解，以实现语义上合适的抓取，而无需重新训练。ManipLLM [[15](https://arxiv.org/html/2405.10255v1#bib.bib15)]通过从文本提示、RGB 图像和深度图中识别接触点和夹持器方向的 3D 坐标来预测操作结果。

### 4.6 LLMs 用于 3D 生成

传统上，3D 建模是一个复杂且耗时的过程，具有较高的入门门槛，需要详细关注几何形状、纹理和光照，以实现逼真的结果。在本节中，我们将深入探讨 LLMs 与 3D 生成技术的结合，展示语言如何提供生成场景中上下文化对象的方法，并为 3D 内容创建和处理提供创新解决方案。

#### 4.6.1 对象级生成

Shape-GPT [[283](https://arxiv.org/html/2405.10255v1#bib.bib283)] 使用形状特定的 3D VQ-VAE 将 3D 形状量化为离散的“形状词”标记。这使得可以将形状数据与文本和图像一起集成到 T5 语言模型 [[139](https://arxiv.org/html/2405.10255v1#bib.bib139)] 的多模态输入中。这种多模态表示使 T5 能够学习跨模态交互，例如文本到形状生成和形状编辑/补全。GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)] 采用了双流方法 - 通过 Point-QFormer 对齐点云几何体与文本，然后将其输入到耦合的 LLM 和扩散路径中，用于文本理解和生成符合文本输入的高保真 3D 对象。

相比之下，MeshGPT [[282](https://arxiv.org/html/2405.10255v1#bib.bib282)] 和 PolyGen [[280](https://arxiv.org/html/2405.10255v1#bib.bib280)] 不根据文本进行生成，但它们仍采用类似于 LLMs 的自回归方法。MeshGPT 使用图卷积将网格几何/拓扑编码为通过残差向量量化压缩的丰富嵌入，并将其输入到 GPT 风格的变换器中，自动回归地预测生成具有所需属性的网格的标记/嵌入。PolyGen [[280](https://arxiv.org/html/2405.10255v1#bib.bib280)] 是一个基于自回归的 3D 网格变换器模型，利用指针网络。它由一个无条件建模网格顶点的顶点模型和一个根据输入顶点使用自回归网络建模网格面的面模型组成，以输出面索引和顶点坐标，从而生成多样化的高质量网格。

#### 4.6.2 场景规模生成

Holodeck [[284](https://arxiv.org/html/2405.10255v1#bib.bib284)] 和 GALA-3D [[25](https://arxiv.org/html/2405.10255v1#bib.bib25)] 使用多阶段管道将初始粗略的 3D 场景布局从文本逐步细化为详细的真实 3D 环境。Holodeck 采用专门的模块来制作基本布局、选择材料，并根据 GPT-4 的空间推理和位置/风格建议加入门窗等元素。然后，它用与 GPT-4 的文本描述匹配的 Objaverse 资产填充布局。优化器根据 GPT-4 获得的空间关系约束安排这些对象，鼓励现实的对象布局和交互。

GALA-3D [[25](https://arxiv.org/html/2405.10255v1#bib.bib25)] 首先使用 LLM 从文本生成粗略布局，然后将其转换为 3D 高斯表示。这种表示作为创建详细 3D 内容的基础，利用实例级文本到图像扩散先验。它采用组合优化来微调布局引导的高斯参数，确保最终场景与文本在物体放置、规模和交互方面对齐。

两者都利用了 LLM 的互补优势来提取高级语义布局，并使用生成模型/优化将这些布局转换为几何和物理上合理的 3D 场景。

#### 4.6.3 程序生成与操作

LLMR [[281](https://arxiv.org/html/2405.10255v1#bib.bib281)]、3D-GPT [[26](https://arxiv.org/html/2405.10255v1#bib.bib26)] 和 SceneCraft [[303](https://arxiv.org/html/2405.10255v1#bib.bib303)] 采用模块化架构，具有用于互动 3D 世界创建和从自然语言生成代码的专用组件/代理。LLMR 包含用于生成代码以在 Unity 中构建场景、理解现有场景对象和属性以便进行修改、识别执行指令所需的功能以及评估最终代码质量的不同组件。类似地，3D-GPT 具有用于解释指令和确定所需生成函数的组件、通过详细建模属性丰富描述、以及将丰富描述翻译为 Blender API 的 Python 代码的组件。总体而言，这些方法展示了任务分解和 LLM 组件专门化，以处理指令解释、功能映射和稳健的代码生成。

## 5 个使用 VLM 的 3D 任务

虽然 [第四部分](https://arxiv.org/html/2405.10255v1#S4 "4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models") 讨论了在 3D 任务中整合 LLM 的方法，但大量研究通过 2D 视觉语言模型（VLMs）的视角探索了 3D 理解的各个方面。VLMs 包含了丰富的视觉信息，这些信息可以直接与 3D 相关联。本节回顾了一系列近期论文的贡献，这些论文涵盖了语言驱动的开放世界理解、实例级理解、统一的端到端架构、空间推理、生成等方面。

### 5.1 开放词汇 3D 场景理解

开放词汇 3D 场景理解旨在使用自然语言描述来识别和描述场景元素，而不是预定义的类别标签。OpenScene [[29](https://arxiv.org/html/2405.10255v1#bib.bib29)] 采用了零样本方法，通过预测与 CLIP 的文本和图像像素嵌入共同嵌入在共享特征空间中的 3D 场景点的密集特征，实现任务无关的训练和开放词汇查询，用于识别对象、材料、功能、活动和房间类型。CLIP-FO3D [[304](https://arxiv.org/html/2405.10255v1#bib.bib304)] 采用类似的方法，修改 CLIP 从 3D 场景中提取密集像素特征，这些特征被投影到点云中，然后通过蒸馏训练 3D 模型以转移 CLIP 的知识。Semantic Abstraction [[305](https://arxiv.org/html/2405.10255v1#bib.bib305)] 从 CLIP 中提取相关性图作为抽象对象表示，以推广到新语义、词汇和领域。Open-Fusion [[306](https://arxiv.org/html/2405.10255v1#bib.bib306)] 将 SEEM [[307](https://arxiv.org/html/2405.10255v1#bib.bib307)] 视觉-语言模型与 TSDF 3D 映射相结合，用于实时开放词汇场景创建和查询，利用基于区域的嵌入和置信度图。

像 PLA [[308](https://arxiv.org/html/2405.10255v1#bib.bib308)] 和 RegionPLC [[309](https://arxiv.org/html/2405.10255v1#bib.bib309)] 这样的 approaches 利用对比学习将标题与 2D 和 3D 数据模态结合，以关联视觉和语义信息。PLA [[308](https://arxiv.org/html/2405.10255v1#bib.bib308)] 使用 3D-caption 对和对比学习，将多视角图像与标题关联以学习视觉-语义表示，而 RegionPLC [[309](https://arxiv.org/html/2405.10255v1#bib.bib309)] 提出了区域感知对比学习，通过将 2D 模型中的区域级标题映射到 3D 点来实现。OVIR-3D [[310](https://arxiv.org/html/2405.10255v1#bib.bib310)] 将 2D 区域提议和来自现成 2D 探测器的文本对齐特征融合到 3D 实例中，以实现高效的开放词汇检索。CoDA [[311](https://arxiv.org/html/2405.10255v1#bib.bib311)] 在其 3D Novel Object Discovery (3D-NOD) 策略中使用了来自标注基础类别的 3D 几何先验和 CLIP 的 2D 语义先验。其 Discovery-driven Cross-Modal Alignment (DCMA) 将 3D 和图像/文本特征对齐，用于新颖对象的定位和分类。

实例级场景理解工作，如 OpenMask3D [[312](https://arxiv.org/html/2405.10255v1#bib.bib312)] 和 Open3DIS [[313](https://arxiv.org/html/2405.10255v1#bib.bib313)]，利用预测的类无关 3D 实例掩码和 2D 段级 CLIP 嵌入来实现开放词汇 3D 实例分割。OpenIns3D [[314](https://arxiv.org/html/2405.10255v1#bib.bib314)] 在没有对齐图像的情况下实现了开放词汇理解，使用一种“Mask-Snap-Lookup”流程，预测 3D 掩码提议，生成合成场景图像，并通过语言模块将类别分配给掩码。Rozenberszki *等人* [[315](https://arxiv.org/html/2405.10255v1#bib.bib315)] 提出了利用 CLIP 特征来基于 3D 特征学习进行 3D 语义和实例分割的方法。

使用 NeRFs 进行语言对齐在开放词汇场景理解中表现出了良好的结果。几种方法，如 DFF [[316](https://arxiv.org/html/2405.10255v1#bib.bib316)]、LERF [[30](https://arxiv.org/html/2405.10255v1#bib.bib30)]、VL-Fields [[317](https://arxiv.org/html/2405.10255v1#bib.bib317)] 和 3D-OVS [[318](https://arxiv.org/html/2405.10255v1#bib.bib318)]，通过最小化体积渲染特征相对于 2D 特征的误差，将 2D 特征提取器如 DINO 或 CLIP 的知识蒸馏到 3D 特征场中，从而实现基于查询的局部编辑和将语言对齐到神经隐式表示。LERF [[30](https://arxiv.org/html/2405.10255v1#bib.bib30)] 通过体积渲染 CLIP 嵌入来优化一个密集的、尺度条件的 3D 语言场。LangSplat [[319](https://arxiv.org/html/2405.10255v1#bib.bib319)] 和 N2F2 [[320](https://arxiv.org/html/2405.10255v1#bib.bib320)] 通过利用分层监督和多尺度特征场，在 3D 高斯点云表示中展示了高效的开放词汇查询和交互。

### 5.2 基于文本的 3D 生成

[第 4.6 节](https://arxiv.org/html/2405.10255v1#S4.SS6 "4.6 LLMs for 3D Generation ‣ 4 3D Tasks with LLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models") 涵盖了使用 LLMs 进行 3D 生成的方法。在这里，我们调查了利用 2D VLMs [[174](https://arxiv.org/html/2405.10255v1#bib.bib174)] 和基于文本的图像扩散模型 [[321](https://arxiv.org/html/2405.10255v1#bib.bib321), [322](https://arxiv.org/html/2405.10255v1#bib.bib322)] 进行文本到 3D 生成的方法，这些方法使用了可微渲染。早期工作如 DreamFields [[323](https://arxiv.org/html/2405.10255v1#bib.bib323)]、CLIP-Mesh [[32](https://arxiv.org/html/2405.10255v1#bib.bib32)]、CLIP-Forge [[324](https://arxiv.org/html/2405.10255v1#bib.bib324)] 和 Text2Mesh [[325](https://arxiv.org/html/2405.10255v1#bib.bib325)] 探索了由 CLIP 指导的零样本 3D 生成。

DreamFusion [[31](https://arxiv.org/html/2405.10255v1#bib.bib31)] 引入了评分蒸馏采样（SDS），其中通过使从任意视角渲染的 3D 表示看起来非常逼真来优化其参数，这些逼真程度由预训练的 2D 扩散模型评估。它使用文本到图像的 Imagen 模型 [[322](https://arxiv.org/html/2405.10255v1#bib.bib322)] 通过 SDS 优化 NeRF 表示。Magic3D [[326](https://arxiv.org/html/2405.10255v1#bib.bib326)] 提出了一个两阶段框架：首先使用低分辨率扩散先验和稀疏 3D 哈希网格生成粗略模型，然后使用高效的可微分渲染器和高分辨率潜在扩散模型 [[321](https://arxiv.org/html/2405.10255v1#bib.bib321)] 优化一个纹理化的 3D 网格模型。Fantasia3D [[327](https://arxiv.org/html/2405.10255v1#bib.bib327)] 解耦几何和外观，使用混合 DMTet [[328](https://arxiv.org/html/2405.10255v1#bib.bib328)] 表示和空间变化的 BRDFs。ProlificDreamer [[329](https://arxiv.org/html/2405.10255v1#bib.bib329)] 引入了变分评分蒸馏（VSD），这是一个基于粒子的框架，将 3D 参数视为随机变量，以提高保真度和多样性。Dream3D [[330](https://arxiv.org/html/2405.10255v1#bib.bib330)] 利用显式的 3D 形状先验和文本到图像的扩散模型以增强文本引导的 3D 合成。MVDream [[331](https://arxiv.org/html/2405.10255v1#bib.bib331)] 使用一个在少量数据上可训练的多视角一致扩散模型进行个性化生成。Text2NeRF [[332](https://arxiv.org/html/2405.10255v1#bib.bib332)] 将 NeRF 表示与预训练的文本到图像扩散模型结合，生成多样的室内/室外 3D 场景。除了同时生成几何体和外观外，若干研究还探索了基于给定几何体单独合成纹理的可能性 [[333](https://arxiv.org/html/2405.10255v1#bib.bib333), [334](https://arxiv.org/html/2405.10255v1#bib.bib334), [335](https://arxiv.org/html/2405.10255v1#bib.bib335)]。

对于人类头像，AvatarCraft [[336](https://arxiv.org/html/2405.10255v1#bib.bib336)] 使用扩散模型来指导神经隐式场几何/纹理学习，通过文本提示。此外，它还通过一个显式的变形场来对这些人类头像进行动画处理，该变形场将目标人类网格映射到模板人类网格。AvatarCLIP [[337](https://arxiv.org/html/2405.10255v1#bib.bib337)] 提出了一个零样本 CLIP 监督框架，用于从文本生成 3D 头像、几何雕刻、纹理映射和动作合成。CG-HOI [[338](https://arxiv.org/html/2405.10255v1#bib.bib338)] 使用扩散模型从文本中描述动态的人物-物体交互。GenZI [[339](https://arxiv.org/html/2405.10255v1#bib.bib339)] 通过预训练的视觉-语言模型提炼有关人类交互的信息，从文本提示中生成零样本 3D 人类-场景交互合成。

在探索组合生成方面，CG3D [[340](https://arxiv.org/html/2405.10255v1#bib.bib340)] 通过组合个体对象而不使用边界框，利用显式 3D 高斯辐射场生成可扩展的 3D 场景。Po 等人 [[341](https://arxiv.org/html/2405.10255v1#bib.bib341)] 介绍了通过文本提示和边界框进行局部条件扩散以实现粒度场景控制。GraphDreamer [[342](https://arxiv.org/html/2405.10255v1#bib.bib342)] 通过将场景图分解为全局-局部描述以优化对象 SDF，从场景图生成组合场景。

总体而言，这些方法结合了扩散模型、视觉-语言模型、神经表示和 3D 先验，用于对象、头像和场景的文本到 3D 生成。

### 5.3 端到端 3D 视觉与语言架构

预训练于大规模 3D 文本数据集的 Transformer 模型学习到强大的联合表示，这些表示桥接了视觉和语言模态。3D-VisTA [[343](https://arxiv.org/html/2405.10255v1#bib.bib343)] 是一个使用自注意力机制联合建模 3D 视觉和文本数据的 Transformer 模型，能够有效地在目标如掩码语言/对象建模和场景-文本匹配上进行预训练。UniT3D [[227](https://arxiv.org/html/2405.10255v1#bib.bib227)] 采取统一的 Transformer 方法，结合了 PointGroup 3D 检测主干网络、BERT 文本编码器和多模态融合模块，并在合成生成的 3D 语言数据上进行联合预训练。SpatialVLM [[344](https://arxiv.org/html/2405.10255v1#bib.bib344)] 采用不同的方法，共同训练 VLMs 在大型合成 3D 空间推理数据集上，提升了 3D 空间视觉问答任务的表现，并使得机器人能够进行链式思维推理。Multi-CLIP [[345](https://arxiv.org/html/2405.10255v1#bib.bib345)] 预训练了一个 3D 场景编码器，以将场景特征与 CLIP 的文本和图像嵌入对齐，旨在将 CLIP 的知识转移到如视觉问答等任务上的 3D 理解中。

除了预训练方法，研究人员还探索了在端到端框架中统一 3D 感知与语言能力的架构。D3Net [[27](https://arxiv.org/html/2405.10255v1#bib.bib27)] 结合了密集描述和视觉定位，配备了一个 3D 对象检测器、一个用于生成描述的发言器和一个用于使用描述区分对象的听众。Uni3DL [[28](https://arxiv.org/html/2405.10255v1#bib.bib28)] 在点云上操作，具有文本编码、点编码、语义/掩码预测模块，以及多样的任务输出，如分割、检测、定位和描述。InstanceRefer [[346](https://arxiv.org/html/2405.10255v1#bib.bib346)] 使用全景分割和语言线索来过滤基于语言描述的实例候选，以便进行 3D 点云中的视觉定位任务，而 LanguageRefer [[347](https://arxiv.org/html/2405.10255v1#bib.bib347)] 结合了语言嵌入和来自 3D 边界框的空间嵌入。3DVG-Transformer [[348](https://arxiv.org/html/2405.10255v1#bib.bib348)] 也处理 3D 点云中的定位，具有坐标引导的上下文聚合模块和多重注意力机制，以实现有效的特征融合。

| 数据集 |     对象描述 |     场景描述 |     密集描述 |     单一对象定位 |     多对象定位 |     问答 |     情境问答 |     对话 |     任务规划 |     真实 |     合成 |     对象 |     室内 |     室外 |     人工标注 |     模型标注 |     基于模板 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Cap3D [[349](https://arxiv.org/html/2405.10255v1#bib.bib349)] | ✓ |  |  |  |  |  |  |  |  | ✓ | ✓ | ✓ |  |  |  | ✓ |  |
| Text2Shape [[350](https://arxiv.org/html/2405.10255v1#bib.bib350)] | ✓ |  |  |  |  |  |  |  |  |  | ✓ | ✓ |  |  | ✓ |  | ✓ |
| SceneVerse [[351](https://arxiv.org/html/2405.10255v1#bib.bib351)] | ✓ | ✓ |  | ✓ |  |  |  |  |  | ✓ | ✓ |  | ✓ |  | ✓ | ✓ | ✓ |
| nu-Caption [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] |  | ✓ |  |  |  |  |  |  |  | ✓ |  |  |  | ✓ | ✓ | ✓ |  |
| nu-Grounding [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] |  | ✓ |  | ✓ |  |  |  |  |  | ✓ |  |  |  | ✓ | ✓ | ✓ |  |
| ScanRefer [[218](https://arxiv.org/html/2405.10255v1#bib.bib218)] |  |  | ✓ | ✓ |  |  |  |  |  | ✓ |  |  | ✓ |  | ✓ |  |  |
| ReferIt3D [[228](https://arxiv.org/html/2405.10255v1#bib.bib228)] |  |  | ✓ | ✓ |  |  |  |  |  | ✓ |  |  | ✓ |  | ✓ |  | ✓ |
| Multi3DRefer [[230](https://arxiv.org/html/2405.10255v1#bib.bib230)] |  |  | ✓ |  | ✓ |  |  |  |  | ✓ |  |  | ✓ |  | ✓ | ✓ |  |
| Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)] |  | ✓ |  | ✓ |  |  |  |  |  | ✓ |  |  | ✓ |  |  | ✓ |  |
| EmbodiedScan [[352](https://arxiv.org/html/2405.10255v1#bib.bib352)] |  |  |  | ✓ |  |  |  |  |  | ✓ |  |  | ✓ |  |  | ✓ | ✓ |
| ScanEnts3D [[353](https://arxiv.org/html/2405.10255v1#bib.bib353)] |  |  | ✓ | ✓ |  |  |  |  |  | ✓ |  |  | ✓ |  | ✓ |  |  |
| WildRefer [[354](https://arxiv.org/html/2405.10255v1#bib.bib354)] |  |  |  | ✓ |  |  |  |  |  | ✓ |  |  | ✓ | ✓ | ✓ |  |  |
| RIORefer [[355](https://arxiv.org/html/2405.10255v1#bib.bib355)] |  |  |  | ✓ |  |  |  |  |  | ✓ |  |  | ✓ |  | ✓ |  |  |
| ARKitSceneRefer [[356](https://arxiv.org/html/2405.10255v1#bib.bib356)] |  |  |  | ✓ |  |  |  |  |  | ✓ |  |  | ✓ |  | ✓ | ✓ |  |
| ScanERU [[229](https://arxiv.org/html/2405.10255v1#bib.bib229)] |  |  |  | ✓ |  |  |  |  |  | ✓ | ✓ |  | ✓ |  | ✓ |  |  |
| DenseGrounding [[231](https://arxiv.org/html/2405.10255v1#bib.bib231)] |  |  |  |  | ✓ |  |  |  |  | ✓ |  |  | ✓ |  | ✓ |  |  |
| ScanQA (Azuma *et al.*) [[234](https://arxiv.org/html/2405.10255v1#bib.bib234)] |  |  |  |  |  | ✓ |  |  |  | ✓ |  |  | ✓ |  | ✓ |  |  |
| ScanQA (Ye *et al.*) [[357](https://arxiv.org/html/2405.10255v1#bib.bib357)] |  |  |  |  |  | ✓ |  |  |  | ✓ |  |  | ✓ |  | ✓ |  |  |
| 3DMV-VQA [[236](https://arxiv.org/html/2405.10255v1#bib.bib236)] |  |  |  |  |  | ✓ |  |  |  | ✓ |  |  | ✓ |  |  |  | ✓ |
| NuScenes-QA [[235](https://arxiv.org/html/2405.10255v1#bib.bib235)] |  |  |  |  |  | ✓ |  |  |  | ✓ |  |  |  | ✓ |  |  | ✓ |
| CLEVR3D [[358](https://arxiv.org/html/2405.10255v1#bib.bib358)] |  |  |  |  |  | ✓ |  |  |  | ✓ | ✓ |  | ✓ |  |  |  | ✓ |
| SQA-3D [[233](https://arxiv.org/html/2405.10255v1#bib.bib233)] |  |  |  |  |  |  | ✓ |  |  | ✓ |  |  | ✓ |  | ✓ |  |  |
| 3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)] | ✓ | ✓ | ✓ | ✓ |  | ✓ | ✓ | ✓ | ✓ | ✓ |  |  | ✓ |  |  | ✓ |  |
| ScanScribe [[294](https://arxiv.org/html/2405.10255v1#bib.bib294)] |  |  | ✓ | ✓ |  | ✓ | ✓ |  |  | ✓ | ✓ |  | ✓ |  | ✓ | ✓ | ✓ |
| M3DBench [[359](https://arxiv.org/html/2405.10255v1#bib.bib359)] |  | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |  |  | ✓ |  | ✓ | ✓ | ✓ |
| GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)] | ✓ |  |  |  |  | ✓ |  | ✓ |  | ✓ | ✓ | ✓ |  |  |  | ✓ |  |
| LAMM [[360](https://arxiv.org/html/2405.10255v1#bib.bib360)] | ✓ | ✓ |  |  |  | ✓ |  | ✓ |  | ✓ | ✓ | ✓ | ✓ |  |  | ✓ | ✓ |

表格 III: 3D 相关任务使用的大型语言模型数据集概述。对于每个数据集，我们展示了该数据集用于演示的任务、数据是从现实世界捕获的还是合成生成的、3D 数据是对象、室内场景还是室外场景，以及注释是如何获得的。我们主要关注用于评估近期研究论文中方法的新数据集。

## 6 数据集

我们现在提供了一个关于用于训练和评估 3D 视觉语言模型的数据集的高层次概述。在表格[III](https://arxiv.org/html/2405.10255v1#S5.T3 "Table III ‣ 5.3 End-to-End Architectures for 3D Vision & Language ‣ 5 3D Tasks with VLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")中，我们列出了数据集以及它们所用的任务，还有关于 3D 扫描和注释的信息。在图[4](https://arxiv.org/html/2405.10255v1#S6.F4 "Figure 4 ‣ 6 Datasets ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")中，我们展示了这些数据集的时间线，显示了每个数据集的 3D 信息来源。当前的 3D 视觉语言数据集几乎完全是通过获取现有的 3D 视觉数据集，并对样本应用人工、模型或模板化的注释生成的。如表格[III](https://arxiv.org/html/2405.10255v1#S5.T3 "Table III ‣ 5.3 End-to-End Architectures for 3D Vision & Language ‣ 5 3D Tasks with VLMs ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")所示，大多数现有数据集关注于真实的室内场景，这部分原因可以通过观察到大多数现有数据集使用来自 ScanNet [[361](https://arxiv.org/html/2405.10255v1#bib.bib361)] 和 3RScan [[295](https://arxiv.org/html/2405.10255v1#bib.bib295)]的 3D 扫描来解释。这里展示的许多数据集共享相同的 3D 数据，而主要通过它们的注释策略选择和设计用于的 3D 视觉语言任务有所不同。

使用语言进行 3D 导航和操作的数据集通常围绕特定要求进行设计，并与现有研究有很大重叠。我们建议读者参考现有的调查论文 [[362](https://arxiv.org/html/2405.10255v1#bib.bib362), [363](https://arxiv.org/html/2405.10255v1#bib.bib363)] 来了解这些数据集的概况。同样，对于文本到 3D 生成数据集，我们建议读者查看 Lee *et al.* [[243](https://arxiv.org/html/2405.10255v1#bib.bib243)] 的最新调查。由于已有大量讨论，我们在这里省略进一步讨论，因为许多方法使用的是 2D 视觉-语言数据，而非特定于 3D 的数据集。

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 4：数据集时间线。时间线展示了现有数据集如何结合和注释以形成新的 3D 视觉语言任务数据集。橙色的数据集是没有语言注释的基础 3D 数据集，蓝色的数据集是用于 3D 视觉语言任务的标注数据集。许多现有数据集使用来自相同来源的 3D 数据，如 ScanNet 和 3RScan，主要在于注释策略和目标 3D 视觉任务的选择上有所不同。请注意，WildRefer 还为视觉-语言任务引入了新的 3D 数据和注释。

Cap3D [[349](https://arxiv.org/html/2405.10255v1#bib.bib349)] 是一个基于 Objaverse [[293](https://arxiv.org/html/2405.10255v1#bib.bib293)] 数据集中的 66 万个对象开发的 3D 对象描述数据集。它通过从 3D 对象的多个视角生成 2D 图像描述，并使用图像-文本对齐和大型语言模型（LLMs）来整合这些描述。

Text2Shape [[350](https://arxiv.org/html/2405.10255v1#bib.bib350)] 是 ShapeNet [[296](https://arxiv.org/html/2405.10255v1#bib.bib296)] 中 8,447 个桌子和 6,591 个椅子的人工标注形式，结合了基于模板的描述标签的原始形状数据集。它最初用于生成性文本到 3D 形状任务。

SceneVerse [[351](https://arxiv.org/html/2405.10255v1#bib.bib351)] 是一个大规模、多用途的注释场景数据集，通过编译 68,000 个来自现有 3D 数据集的场景而成。SceneVerse 包含 250 万对视觉-语言对，用于对象描述、场景描述和生成相关描述，主要通过 3D 场景图和大型语言模型生成。

nu-Caption [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] 是对 nuScenes [[364](https://arxiv.org/html/2405.10255v1#bib.bib364)] 数据集中 42 万个 LiDAR 扫描的标注版本，使用 GPT-4 和 2D 大型语言模型进行注释。描述包括一般场景描述、对象及其关系的详细描述，以及识别道路上的潜在风险。

nu-Grounding [[271](https://arxiv.org/html/2405.10255v1#bib.bib271)] 在 nu-Caption 的基础上，专注于基础任务，利用来自 nuScenes 的注释创建了 280k 对用于视觉基础和基础字幕的问答对。

ScanRefer [[218](https://arxiv.org/html/2405.10255v1#bib.bib218)] 引入了使用自然语言表达进行 3D RGB-D 基础的任务，通过创建 51,583 条人工标注的“指代表达”来描述 800 个 ScanNet 场景中的 11,046 个对象。输入包括扫描的 3D 场景的点云和指定目标对象的自由形式描述，输出是对象的相应边界框。ScanRefer 提供了一个评估服务器和在线基准测试 [`kaldir.vc.in.tum.de/scanrefer_benchmark/`](https://kaldir.vc.in.tum.de/scanrefer_benchmark/)，以便于不同方法之间的比较。

ReferIt3D [[228](https://arxiv.org/html/2405.10255v1#bib.bib228)] 引入了多个数据集（Nr3D、Sr3D 和 Sr3D+），这些数据集包含来自 707 个 ScanNet 场景的对象。与 ScanRefer 类似，这些对象被标注了指代表达，重点在于场景中包含多个目标类别的实例的查询，并且需要指代表达来区分它们。Nr3D 包含 41,503 条人工标注的自由形式的表达来指代 3D 场景中的对象，Sr3D 包含 83,572 条基于模板的表达，而 SR3D+ 是 Sr3D 的一个版本，具有扩展的表达。ReferIt3D 还提供了一个评估服务器和在线基准测试 [`referit3d.github.io/benchmarks.html`](https://referit3d.github.io/benchmarks.html)，以便于不同方法之间的比较。

Multi3DRefer [[230](https://arxiv.org/html/2405.10255v1#bib.bib230)] 是 ScanRefer 数据集的修改版本。与始终指代场景中一个对象的指代表达不同，Multi3DRefer 包含 6688 个零目标、42,060 个单目标和 13,178 个多目标的指代描述，这些描述是为 800 个 ScanNet 场景中的 11,609 个对象收集的。ChatGPT [[286](https://arxiv.org/html/2405.10255v1#bib.bib286)] 也被用于重新表述指代表达。

Chat-3D v2 [[172](https://arxiv.org/html/2405.10255v1#bib.bib172)] 是 ScanRefer 的另一种修改形式，其中使用了来自 ScanNet 中 705 个场景的指代表达来构建描述场景中对象之间关系的场景字幕。这些场景字幕使用 GPT-4 [[365](https://arxiv.org/html/2405.10255v1#bib.bib365)] 生成，通过向模型提供关于对象的真实信息来实现。生成的字幕包含对显式的“对象标识符”的引用，直接代表场景中的每个对象。

EmbodiedScan [[352](https://arxiv.org/html/2405.10255v1#bib.bib352)] 是 Matterport3D [[285](https://arxiv.org/html/2405.10255v1#bib.bib285)]、3RScan [[295](https://arxiv.org/html/2405.10255v1#bib.bib295)] 和 ScanNet [[361](https://arxiv.org/html/2405.10255v1#bib.bib361)] 的一个标注组合，设计为一个多模态、自我中心的数据集，用于 3D 场景理解。Segment Anything [[366](https://arxiv.org/html/2405.10255v1#bib.bib366)] 和其他标注工具用于提供 3D 边界框、语义占用，以及 970k 个基于模板的语言描述，涵盖总计 5185 个场景。

ScanEnts3D [[353](https://arxiv.org/html/2405.10255v1#bib.bib353)] 扩展了 ScanRefer [[218](https://arxiv.org/html/2405.10255v1#bib.bib218)] 和 ReferIt3D [[228](https://arxiv.org/html/2405.10255v1#bib.bib228)]，通过使用专业标注员将参考句子中提到的每个对象与 3D 场景中的相应实例关联。在原始论文中，此数据集仅用于训练目的，发现它能够提高模型在其他视觉定位和图像描述数据集上的表现。

WildRefer [[354](https://arxiv.org/html/2405.10255v1#bib.bib354)] 展示了 STRefer 和 LifeRefer 数据集，强调在实际环境中的以人为中心的 3D 定位，具有全面的 3D 和语言人工标注。STRefer 包含了 5,458 条关于 662 个场景中物体的参考表达，而 LifeRefer 包含了 25,380 条关于 3,172 个场景中物体的参考表达，这些场景来自为此数据集新获得的一组 3D 扫描。

RIORefer [[355](https://arxiv.org/html/2405.10255v1#bib.bib355)] 是 3RScan [[295](https://arxiv.org/html/2405.10255v1#bib.bib295)] 的一个人工标注版本，用于 3D 定位。它包含了 63k 条关于 1,380 个场景中物体的描述。此数据集被引入作为测试模型跨数据集泛化能力的一种方式，如在提出的“从 ScanRefer 到 RIORefer 泛化”和“从 RIORefer 到 ScanRefer 泛化”任务中。

ARKitSceneRefer [[356](https://arxiv.org/html/2405.10255v1#bib.bib356)] 是 ARKitScenes [[368](https://arxiv.org/html/2405.10255v1#bib.bib368)] 的一个标注版本，重点关注现实世界室内环境中小型日常物体的 3D 定位。它包含了 15k 条对 1,605 个场景中物体的描述。

ScanERU [[229](https://arxiv.org/html/2405.10255v1#bib.bib229)] 是对 ScanNet 的一种修改版和人工标注版，结合了来自 ScanRefer 的 46k 个参考表达和 706 个 ScanNet 场景，这些场景经过修改以包含一个 3D 人体模型，模型在指向所提及的对象时使用了由人工标注者指定的位置。

DenseGrounding [[231](https://arxiv.org/html/2405.10255v1#bib.bib231)]，与 Multi3DRefer 类似，旨在将 3D 定位任务扩展到包括多个对象。然而，与单个引用表达式指代多个对象不同，每个输入是一个包含单个对象的引用查询的合成段落。这些段落通过结合来自 ScanRefer 和 ReferIt3D 的随机对象的最近邻和它们的引用表达式来构建。

ScanQA（Azuma *et al.*）[[234](https://arxiv.org/html/2405.10255v1#bib.bib234)] 是 ScanNet 的一个注释版本，涵盖了 800 个场景中的 41,000 个问答对。问题是通过使用 ScanRefer 中的引用表达式自动生成的，然后由人工注释员进行修正，而答案则完全由人工注释员得出。这就是通常所称的“ScanQA”数据集。

ScanQA（Ye *et al.*）[[357](https://arxiv.org/html/2405.10255v1#bib.bib357)] 与 ScanQA（Azuma *et al.*）同时发布，也是一种人工注释的 ScanNet 形式，用作 3D 问答数据集。Ye *et al.* 包含 806 个 ScanNet 场景的 10,000 个问答对。而 Azuma *et al.*最初使用 ScanRefer 中的引用表达式生成问题，Ye *et al.*则由人工注释员完成整个问题的创建。

3DMV-VQA [[236](https://arxiv.org/html/2405.10255v1#bib.bib236)] 是对 Habitat-Matterport 3D 数据集（HM3D）[[369](https://arxiv.org/html/2405.10255v1#bib.bib369)]中 5000 个场景的注释版本，利用 HM3DSem [[370](https://arxiv.org/html/2405.10255v1#bib.bib370)]中的语义信息生成了 50,000 个四种类型的问题：“概念”，“计数”，“关系”和“比较”。这些问题作为模板生成，然后转化为自然语言问题。

NuScenes-QA [[235](https://arxiv.org/html/2405.10255v1#bib.bib235)] 包含来自 nuScenes [[364](https://arxiv.org/html/2405.10255v1#bib.bib364)]的 34,000 个场景，注释了 460,000 个模板式的问答对，这些问答对是使用构建的场景图生成的。问题分为 5 种类型：“存在”，“计数”，“查询对象”，“查询状态”和“比较”，并且可以包括空间推理。

CLEVR3D [[358](https://arxiv.org/html/2405.10255v1#bib.bib358)] 是 3RScan [[295](https://arxiv.org/html/2405.10255v1#bib.bib295)]的一个注释版本，旨在用于室内 3D QA 任务。使用来自 3DSSG [[371](https://arxiv.org/html/2405.10255v1#bib.bib371)]的场景图注释生成模板式的问题和答案。最初为 1,333 个场景生成了 44,000 个问题，但它们使用了“组合场景操作”技术，从生成的对象池中随机替换场景图中的对象，从而人为地生成了 171,000 个问题，覆盖 8,771 个场景。

SQA-3D [[233](https://arxiv.org/html/2405.10255v1#bib.bib233)] 是 ScanNet 的另一个人工注释版本，提出了“情境问答”问题，每个查询包括对代理当前地点和情况的描述，以及与场景相关的查询。SQA-3D 包含 33.4k 个问题，涵盖 650 个场景。

3D-LLM [[153](https://arxiv.org/html/2405.10255v1#bib.bib153)] 是 Objaverse、ScanNet 和 HM3D/HM3DSem 的注释版本，旨在处理涉及 3D 视觉和语言的各种任务。BLIP-2 [[195](https://arxiv.org/html/2405.10255v1#bib.bib195)] 和 ChatGPT [[286](https://arxiv.org/html/2405.10255v1#bib.bib286)] 用于生成 30 万实例的‘3D 语言数据’，用于各种 3D 视觉语言任务。

ScanScribe [[294](https://arxiv.org/html/2405.10255v1#bib.bib294)] 是从 ScanNet 和 3RScan 中注释的 1,185 个场景的版本，旨在作为大规模的 3D 场景-文本对数据集，用于预训练 3D 视觉语言模型。它利用 ScanQA、ScanRefer 和 ReferIt3D 处理 ScanNet 数据，并使用 GPT-3 提示生成 3RScan 的注释，创建了总计 27.8 万 个场景描述。为了增加数据集的多样性，场景通过随机替换场景中 10%的物体为来自 Objaverse 的同类物体来合成生成。

M3DBench [[359](https://arxiv.org/html/2405.10255v1#bib.bib359)] 是一个多模态指令跟随数据集，包含 327k 个指令-响应对，涵盖了广泛的任务。数据收集自大量现有数据集（见图 [4](https://arxiv.org/html/2405.10255v1#S6.F4 "Figure 4 ‣ 6 Datasets ‣ When LLMs step into the 3D World: A Survey and Meta-Analysis of 3D Tasks via Multi-modal Large Language Models")），同时使用 GPT 提示生成额外的注释。

GPT4Point [[268](https://arxiv.org/html/2405.10255v1#bib.bib268)] 是来自 Objaverse-XL 的超过 100 万个物体的注释版本，设计用于 3D 标注、3D QA 和其他 3D 任务。注释通过一个层次化的管道自动生成，该管道融合并改进了来自多个视角的描述。

LAMM [[360](https://arxiv.org/html/2405.10255v1#bib.bib360)] 是一个大规模的多模态指令调优数据集，涵盖了 2D 和 3D 视觉任务。3D 数据来自 3RScan [[295](https://arxiv.org/html/2405.10255v1#bib.bib295)]、CLEVR3D [[358](https://arxiv.org/html/2405.10255v1#bib.bib358)]、3DSSG [[371](https://arxiv.org/html/2405.10255v1#bib.bib371)] 和 ShapeNet [[296](https://arxiv.org/html/2405.10255v1#bib.bib296)]，并使用 GPT [[365](https://arxiv.org/html/2405.10255v1#bib.bib365)] 和基于模板的响应进行注释。

## 7 Challenges and Opportunities

尽管在将 LLMs 与 3D 数据整合方面取得了进展，但数据表示、计算效率和基准测试仍然存在挑战，迫切需要创新解决方案。

表示选择对 3D 视觉语言模型的性能有很大影响。目前，由于点云的简便性和与神经网络的兼容性，点云主要用于表示室内（例如网格的顶点）和室外（例如 LiDAR 点云）环境。然而，它们在捕捉对准确丰富空间模型至关重要的细节方面存在困难。开发新型的 3D 场景表示方法，更有效地弥合空间信息和语言之间的差距，可能会解锁新的理解和互动层次。通过找到创新的方式在 3D 表示中编码语言和语义信息，如使用精炼的语言和语义嵌入 [[30](https://arxiv.org/html/2405.10255v1#bib.bib30), [316](https://arxiv.org/html/2405.10255v1#bib.bib316)]，可以帮助弥合这两种模态之间的差距。

3D 数据处理和 LLMs 的计算需求带来了重大挑战。随着 3D 环境复杂性和语言模型规模的增加，可扩展性仍然是一个问题。为适应性和计算效率设计的 LLM 架构的进展可能会显著拓宽其应用范围。

改进基准测试对于全面评估和推动多模态 LLMs 在 3D 任务中的能力至关重要。目前的基准测试范围有限，特别是在 3D 推理方面，限制了对空间推理能力的评估以及 3D 决策/互动系统的发展。此外，现有的指标无法全面捕捉 LLMs 在 3D 环境中的全部能力。制定特定任务的指标，以更精确地测量不同 3D 任务中的性能至关重要。最后，目前场景理解基准测试的细粒度过于简单，限制了对复杂 3D 环境理解的洞察。需要更多样化的任务。

使用 LLMs 进行 3D 理解时，安全性和伦理问题必须考虑。LLMs 可能会产生幻觉和输出不准确、不安全的信息，导致关键 3D 应用中的错误决策。此外，LLMs 经常以不可预测且难以解释的方式失败。它们还可能继承训练数据中存在的社会偏见，在现实世界 3D 场景中预测时对某些群体造成不公平的劣势。必须谨慎使用 LLMs 于 3D 环境中，采用策略创建更具包容性的数据集，建立稳健的评估框架以检测和纠正偏见，并采取机制最小化幻觉，确保负责任和公平的结果。

## 8 结论

本调查论文提供了对大语言模型与 3D 数据集成的深入探索。系统回顾了大语言模型在处理、理解和生成 3D 数据方面的方法论、应用和新兴能力，调查强调了大语言模型在一系列 3D 任务中的变革潜力。从增强 3D 环境中的空间理解和互动到推动具身 AI 系统的能力，大语言模型在推进该领域中起到了关键作用。

主要发现包括识别大语言模型的独特优势，如零样本学习、高级推理和广泛的世界知识，这些都是弥合文本信息与空间解释之间差距的关键。论文展示了大语言模型与 3D 数据集成成功的广泛任务。与大语言模型一起探索其他 3D 视觉-语言方法揭示了一个丰富的研究领域，旨在加深我们对 3D 世界的理解。

此外，调查还突出了数据表示、模型可扩展性和计算效率等重大挑战，建议克服这些困难对于充分实现大语言模型在 3D 应用中的潜力至关重要。总之，这项调查不仅提供了使用大语言模型的 3D 任务当前状态的全面概述，还为未来的研究方向奠定了基础。它呼吁进行合作努力，以探索和扩展大语言模型在理解和互动复杂 3D 世界中的能力，为空间智能领域的进一步进展铺平道路。

## 参考文献

+   [1] L. Chen 等。驾驶与 LLMS：融合对象级向量模态以实现可解释的自动驾驶。arXiv 预印本 arXiv:2310.01957, 2023。

+   [2] H. Sha 等。LanguageMPC：作为自动驾驶决策者的大语言模型。arXiv 预印本 arXiv:2310.03026, 2023。

+   [3] D. Fu 等。像人一样驾驶：用大语言模型重新思考自动驾驶。在 WACV 上，第 910–919 页，2024 年。

+   [4] Z. Xu 等。DriveGPT4：通过大语言模型实现可解释的端到端自动驾驶。arXiv 预印本 arXiv:2310.01412, 2023。

+   [5] X. Ma 等。风格和雾霾都重要：用于语义雾霾场景理解的累积领域适应。在 CVPR 上，第 18922–18931 页，2022 年。

+   [6] R. T. Azuma. 增强现实的调查。Presence: teleoperators & virtual environments, 6(4):355–385, 1997。

+   [7] J. Carmigniani 和 B. Furht. 增强现实：概述。增强现实手册，第 3–46 页，2011 年。

+   [8] A. B. Craig. 理解增强现实：概念与应用。Newnes, 2013。

+   [9] S. Feiner 等。一台巡游机器：原型设计 3D 移动增强现实系统以探索城市环境。Personal Technologies, 1:208–217, 1997。

+   [10] A. Brohan 等。RT-2：视觉-语言-行动模型将网络知识转移到机器人控制中。在 arXiv 预印本 arXiv:2307.15818, 2023。

+   [11] D. Zheng 等人。致力于学习通用模型以实现具身导航。arXiv 预印本 arXiv:2312.02010，2023 年。

+   [12] C. H. Song 等人。Llm-planner：针对具身代理的少样本基础规划与大型语言模型。在 ICCV 上，pp. 2998–3009，2023 年。

+   [13] W. Huang 等人。Voxposer：用于机器人操作的可组合 3d 价值图与语言模型。arXiv 预印本 arXiv:2307.05973，2023 年。

+   [14] R. Mirjalili 等人。Lan-grasp：使用大型语言模型进行语义对象抓取。arXiv 预印本 arXiv:2310.05239，2023 年。

+   [15] X. Li 等人。Manipllm：用于对象中心机器人操作的具身多模态大型语言模型。arXiv 预印本 arXiv:2312.16217，2023 年。

+   [16] Z. Yuan 等人。用于零样本开放词汇 3d 视觉定位的视觉编程。arXiv 预印本 arXiv:2311.15383，2023 年。

+   [17] S. Zhang 等人。Agent3d-zero：一个用于零样本 3d 理解的代理，2024 年。

+   [18] K. M. Jatavallabhula 等人。Conceptfusion：开放集多模态 3d 映射。arXiv 预印本 arXiv:2302.07241，2023 年。

+   [19] S. Chen 等人。Ll3da：用于全 3d 理解、推理和规划的视觉互动指令调整。arXiv 预印本 arXiv:2311.18651，2023 年。

+   [20] Z. Guo 等人。Viewrefer：利用 GPT 和原型指导掌握多视角知识进行 3d 视觉定位。arXiv 预印本 arXiv:2303.16894，2023 年。

+   [21] J. Yang 等人。Llm-grounder：使用大型语言模型作为代理的开放词汇 3d 视觉定位。arXiv 预印本 arXiv:2309.12311，2023 年。

+   [22] A. Abdelreheem 等人。零样本 3d 形状对应。在 SIGGRAPH Asia 2023 会议论文中，pp. 1–11，2023 年。

+   [23] J. Fang 等人。Transcribe3d：利用转录信息进行 3d 参照推理的 LLMs 基础。第二届语言与机器人学习研讨会：语言作为基础，2023 年。

+   [24] Y. Hong 等人。Multiply：一个多感官对象中心的具身大型语言模型在 3d 世界中的应用。arXiv 预印本 arXiv:2401.08577，2024 年。

+   [25] X. Zhou 等人。Gala3d：通过布局引导生成高斯散布进行文本到 3d 复杂场景生成。arXiv 预印本 arXiv:2402.07207，2024 年。

+   [26] C. Sun 等人。3d-gpt：使用大型语言模型的程序化 3d 建模。arXiv 预印本 arXiv:2310.12945，2023 年。

+   [27] D. Z. Chen 等人。D3net：用于 3d 密集标注和视觉定位的统一说话人-听众架构。在 ECCV 上，pp. 487–505。Springer，2022 年。

+   [28] X. Li 等人。Uni3dl：用于 3d 和语言理解的统一模型。arXiv:2310.09478，2023 年。

+   [29] S. Peng 等人。Openscene：利用开放词汇进行 3d 场景理解。在 CVPR 上，2023 年。

+   [30] J. Kerr 等人。Lerf：语言嵌入辐射场。在 ICCV 上，2023 年。

+   [31] B. Poole 等人。Dreamfusion：使用 2d 扩散进行文本到 3d 的生成。arXiv 预印本 arXiv:2209.14988，2022 年。

+   [32] N. M. Khalid 等人。Clip-mesh：使用预训练图像-文本模型从文本生成纹理网格。arXiv 预印本 arXiv:2203.13333，2022 年。

+   [33] C. R. Qi 等人。Pointnet：在点集上进行 3D 分类和分割的深度学习。发表于 CVPR，2017 年。

+   [34] C. R. Qi 等人。Pointnet++：在度量空间中的点集深层次层次特征学习。发表于 NeurIPS，第 30 期，2017 年。

+   [35] R. Roveri 等人。PointProNets：通过卷积神经网络整合点云。发表于 CGF，2018 年。

+   [36] X. Liu 等人。Flownet3d：在 3D 点云中学习场景流。发表于 CVPR，2019 年。

+   [37] Z. Wang 等人。Flownet3d++：用于深度场景流估计的几何损失。发表于 WACV，2020 年。

+   [38] W. Yifan 等人。用于点基几何处理的可微表面喷溅。发表于 ACM TOG，2019 年。

+   [39] O. Wiles 等人。SynSin：从单张图像进行端到端视图合成。发表于 CVPR，2020 年。

+   [40] C.-H. Lin 等人。学习高效点云生成用于密集 3D 物体重建。发表于 AAAI，2018 年。

+   [41] L. Li 等人。端到端学习 3D 点云的局部多视图描述符。发表于 CVPR，2020 年。

+   [42] E. Insafutdinov 和 A. Dosovitskiy。基于可微分点云的无监督形状和姿态学习。发表于 NeurIPS，2018 年。

+   [43] B. Fei 等人。基于深度学习的 3D 点云补全处理和分析的全面综述。IEEE 智能交通系统汇刊，2022 年。

+   [44] X. Yan 等人。透视变换网络：在没有 3D 监督的情况下学习单视图 3D 物体重建。发表于 NeurIPS，2016 年。

+   [45] A. Dai 等人。使用 3D 编码器-预测器 CNN 和形状合成进行形状补全。发表于 CVPR，pp. 5868–5877，2017 年。

+   [46] A. Dai 和 M. Nießner。3DMV：用于 3D 语义场景分割的联合 3D 多视图预测。发表于 ECCV，pp. 452–468，2018 年。

+   [47] S. Tulsiani 等人。通过可微分光线一致性进行单视图重建的多视图监督。发表于 IEEE TPAMI，2019 年。

+   [48] P. Henzler 等人。逃离柏拉图的洞穴：从对抗渲染中获取 3D 形状。发表于 ICCV，2019 年。

+   [49] S. Lombardi 等人。神经体积：从图像中学习动态可渲染体积。发表于 ACM TOG，2019 年。

+   [50] Y. Jiang 等人。Sdfdiff：用于 3D 形状优化的有符号距离场的可微渲染。发表于 CVPR，2020 年。

+   [51] K. Schwarz 等人。Voxgraf：基于稀疏体素网格的快速 3D 相关图像合成。发表于 NeurIPS，2022 年。

+   [52] Q. Xu 等人。基于深度学习的 3D 形状生成综述。发表于 Computational Visual Media，2023 年。

+   [53] D. Peng 等人。一种基于 PDE 的快速局部水平集方法。计算物理学杂志，1999 年。

+   [54] S. Osher 等人。水平集方法和动态隐式表面。应用力学评论，2004 年。

+   [55] V. A. Prisacariu 和 I. Reid。共享形状空间。发表于 ICCV，2011 年。

+   [56] Q. Xu 等人。Disn：高质量单视图 3D 重建的深度隐式表面网络。发表于 NeurIPS，2019 年。

+   [57] Y. Jiang 等人。Sdfdiff：用于 3D 形状优化的有符号距离场的可微渲染。发表于 CVPR，2020 年。

+   [58] B. Curless 和 M. Levoy. 从范围图像构建复杂模型的体积方法. 发表在第 23 届计算机图形学与交互技术年会, 1996.

+   [59] R. A. Newcombe 等人. Kinectfusion: 实时稠密表面映射与跟踪. 发表在 ISMAR, 2011.

+   [60] M. Niessner 等人. 使用体素哈希的实时 3D 重建. ACM TOG, 2013.

+   [61] A. Dai 等人. Bundlefusion: 使用即时表面再集成的实时全球一致 3D 重建. ACM TOG, 36(4):1, 2017.

+   [62] A. Dai 等人. Sg-nn: 稀疏生成神经网络用于自监督场景完成 RGB-D 扫描. 发表在 CVPR, 第 849–858 页, 2020.

+   [63] P. Mittal 等人. Autosdf: 形状先验用于 3D 完成、重建和生成. 发表在 CVPR, 2022.

+   [64] H. Kato 等人. 可微分渲染: 一项综述. 发表在 arXiv, 2020.

+   [65] H. Kato 等人. 神经 3D 网格渲染器. 发表在 CVPR, 2018.

+   [66] K. Genova 等人. 无监督训练用于 3D 可变形模型回归. 发表在 CVPR, 2018.

+   [67] M. M. Loper 和 M. J. Black. OpenDR: 一种近似可微分渲染器. 发表在 ECCV, 2014.

+   [68] H. Kato 和 T. Harada. 学习单视图 3D 重建的视图先验. 发表在 CVPR, 2019.

+   [69] H. Rhodin 等人. 一种多用途场景模型与可微分可见性应用于生成姿态估计. 发表在 ICCV, 2015.

+   [70] S. Liu 等人. Soft Rasterizer: 一种用于基于图像的 3D 推理的可微分渲染器. 发表在 ICCV, 2019.

+   [71] W. Chen 等人. 使用基于插值的可微分渲染器学习预测 3D 物体. 发表在 NeurIPS, 2019.

+   [72] Y. Xie 等人. 视觉计算及其超越的神经场. 发表在 CGF, 2022.

+   [73] A. Tewari 等人. 神经渲染的最新进展. 发表在 CGF, 2020.

+   [74] L. Mescheder 等人. 占据网络: 在函数空间中学习 3D 重建. 发表在 CVPR, 2019.

+   [75] S. Peng 等人. 卷积占据网络. 发表在 ECCV, 2020.

+   [76] Z. Chen 和 H. Zhang. 学习隐式场用于生成形状建模. 发表在 CVPR, 2019.

+   [77] J. J. Park 等人. Deepsdf: 学习用于形状表示的连续符号距离函数. 发表在 CVPR, 2019.

+   [78] V. Sitzmann 等人. 场景表示网络: 连续 3D 结构感知神经场景表示. 发表在 NeurIPS, 2019.

+   [79] P. Wang 等人. Neus: 通过体积渲染学习神经隐式表面用于多视图重建. 发表在 NeurIPS, 2021.

+   [80] Y. Wang 等人. Neus2: 快速学习用于多视图重建的神经隐式表面. 发表在 ICCV, 2023.

+   [81] B. Mildenhall 等人. NeRF: 作为神经辐射场的场景表示用于视图合成. 发表在 ECCV, 2020.

+   [82] R. Martin-Brualla 等人. NeRF in the Wild: 神经辐射场用于无约束照片集合. 发表在 CVPR, 2021.

+   [83] K. Zhang 等人. Nerf++: 分析和改进神经辐射场. arXiv:2010.07492, 2020.

+   [84] Z. Wang 等人. NeRF$--$: 没有已知相机参数的神经辐射场. arXiv 预印本 arXiv:2102.07064, 2021.

+   [85] Z. Li 等. 用于动态场景的时空神经场景流场。在 CVPR, 2021。

+   [86] A. Pumarola 等. D-nerf：用于动态场景的神经辐射场。在 CVPR, 2021。

+   [87] K. Schwarz 等. Graf：用于 3D 觉知图像合成的生成性辐射场。在 NeurIPS, 2020。

+   [88] M. Niemeyer 和 A. Geiger. Giraffe：将场景表示为组合生成神经特征场。在 CVPR, 2021。

+   [89] D. Rebain 等. Derf：分解的辐射场。在 CVPR, 2021。

+   [90] K. Park 等. 可变形神经辐射场。ICCV, 2021。

+   [91] W. Xian 等. 时空神经辐射场用于自由视点视频。在 CVPR, 2021。

+   [92] W. Bian 等. Nope-nerf：优化无姿态先验的神经辐射场。在 CVPR, 2023。

+   [93] J.-W. Bian 等. Porf：用于准确神经表面重建的姿态残差场。arXiv 预印本 arXiv:2310.07449, 2023。

+   [94] J. T. Barron 等. Mip-nerf 360：无界的抗锯齿神经辐射场。在 CVPR, 2022。

+   [95] A. Vaswani 等. 注意力机制即一切所需。在 NeurIPS, 2017。

+   [96] M. Tancik 等. 傅里叶特征使网络能够学习低维域中的高频函数。在 NeurIPS, 2020。

+   [97] S.-F. Chng 等. 高斯激活的神经辐射场用于高保真重建和姿态估计。在 ECCV, 2022。

+   [98] L. Liu 等. 神经稀疏体素场。NeurIPS, 2020。

+   [99] C. Sun 等. 直接体素网格优化：辐射场重建的超快收敛。在 CVPR, 2022。

+   [100] A. Yu 等. Plenoxels：没有神经网络的辐射场。CVPR, 2022。

+   [101] Z. Chen 等. Mobilenerf：利用多边形光栅化管线在移动架构上高效渲染神经场。在 CVPR, 2023。

+   [102] T. Müller 等. 具有多分辨率哈希编码的即时神经图形原语。ACM TOG, 2022。

+   [103] B. Kerbl 等. 3D 高斯喷洒用于实时辐射场渲染。ACM 图形学通讯, 2023。

+   [104] C. Reiser 等. Merf：用于实时视图合成的内存高效辐射场。SIGGRAPH, 2023。

+   [105] D. Duckworth 等. Smerf：用于实时大场景探索的可流式内存高效辐射场。arXiv 预印本 arXiv:2312.07541, 2023。

+   [106] T. Lu 等. Scaffold-gs：用于视图自适应渲染的结构化 3D 高斯。CVPR, 2024。

+   [107] J. C. Lee 等. 用于辐射场的紧凑 3D 高斯表示。CVPR, 2024。

+   [108] J. L. Schönberger 和 J.-M. Frahm. 运动重建的结构再访。在 CVPR, 2016。

+   [109] C. Lassner 和 M. Zollhofer. Pulsar：高效的基于球体的神经渲染。在 CVPR, 2021。

+   [110] J. L. Elman. 寻找时间中的结构。认知科学, 1990。

+   [111] S. Hochreiter 和 J. Schmidhuber. 长短期记忆。神经计算, 1997。

+   [112] J. Kaplan 等. 神经语言模型的缩放法则。arXiv 预印本 arXiv:2001.08361, 2020。

+   [113] W. X. Zhao 等。大型语言模型调查。arXiv 预印本 arXiv:2303.18223，2023 年。

+   [114] S. Minaee 等。大型语言模型：一项调查。arXiv 预印本 arXiv:2402.06196，2024 年。

+   [115] J. Wei 等。大型语言模型的新兴能力。arXiv 预印本 arXiv:2206.07682，2022 年。

+   [116] Q. Dong 等。关于上下文学习的调查。arXiv 预印本 arXiv:2301.00234，2023 年。

+   [117] T. Lin 等。变压器的调查。AI open，2022 年。

+   [118] M. Lewis 等。巴特：用于自然语言生成、翻译和理解的去噪序列到序列预训练。arXiv 预印本 arXiv:1910.13461，2019 年。

+   [119] C. Raffel 等。探索统一文本到文本变换器的迁移学习极限。在 JMLR，2020 年。

+   [120] P. J. Liu 等。通过总结长序列生成维基百科。arXiv 预印本 arXiv:1801.10198，2018 年。

+   [121] A. Radford 等。通过生成式预训练改善语言理解。OpenAI，2018 年。

+   [122] T. Le Scao 等。Bloom：一个开放访问的 176b 参数多语言语言模型。ArXiv，abs/2211.05100，2022 年。

+   [123] R. Sennrich 等。带有子词单元的罕见词的神经机器翻译。arXiv 预印本 arXiv:1508.07909，2015 年。

+   [124] M. Schuster 和 K. Nakajima。日语和韩语语音搜索。在国际会议上，声学、语音和信号处理中，页码：5149-5152，2012 年。

+   [125] T. Kudo 和 J. Richardson。Sentencepiece：用于神经文本处理的简单且与语言无关的子词分词和解词器。arXiv 预印本 arXiv:1808.06226，2018 年。

+   [126] Y. Kim 等。结构化注意力网络。arXiv 预印本 arXiv:1702.00887，2017 年。

+   [127] T. Brown 等。语言模型是少样本学习者。NeurIPS，33:1877-1901，2020 年。

+   [128] J. Liu 等。什么才是 gpt-$3$的良好上下文示例？arXiv 预印本 arXiv:2101.06804，2021 年。

+   [129] S. Min 等。重新思考演示的作用：是什么使上下文学习起作用？arXiv 预印本 arXiv:2202.12837，2022 年。

+   [130] A. Radford 等。语言模型是无监督的多任务学习者。OpenAI 博客，1(8)：9，2019 年。

+   [131] J. Achiam 等。Gpt-4 技术报告。arXiv 预印本 arXiv:2303.08774，2023 年。

+   [132] J. Wei 等。思维链提示引发大型语言模型的推理。NeurIPS，35:24824–24837，2022 年。

+   [133] Z. Zhang 等。大型语言模型的自动思维链提示。在 ICLR，2023 年。

+   [134] D. Hendrycks 等。用数学数据集衡量数学问题解决能力。NeurIPS，2021 年。

+   [135] D. Saxton 等。分析神经模型的数学推理能力。ICLR，2019 年。

+   [136] A. Patel 等。NLP 模型真的能解决简单的数学文字问题吗？在 2021 年北美计算语言学协会年会论文集：人类语言技术中，2021 年。

+   [137] S.-y. Miao 等. 用于评估和开发英语数学问题解答者的多样化语料库。见第 58 届计算语言学协会年会论文集，第 975–984 页，2020 年。

+   [138] A. Wang 等. Glue：用于自然语言理解的多任务基准和分析平台。ICLR，2019 年。

+   [139] C. Raffel 等. 通过统一的文本到文本变换器探索迁移学习的极限。机器学习研究期刊（JMLR），2020 年。

+   [140] H. Touvron 等. Llama：开放且高效的基础语言模型。arXiv 预印本 arXiv:2302.13971，2023 年。

+   [141] H. Touvron 等. Llama 2：开放基础和微调聊天模型。arXiv 预印本 arXiv:2307.09288，2023 年。

+   [142] J. Devlin 等. Bert：用于语言理解的深度双向变换器预训练。arXiv 预印本 arXiv:1810.04805，2018 年。

+   [143] M. AI. 介绍 Meta Llama 3：迄今为止最强大的开放可用 llm。 [`ai.meta.com/blog/meta-llama-3/`](https://ai.meta.com/blog/meta-llama-3/)，2024 年 4 月。

+   [144] L. Ouyang 等. 训练语言模型以遵循指令与人类反馈。NeurIPS，2022 年。

+   [145] R. Taori 等. Stanford alpaca：一个指令跟随的 llama 模型。 [`github.com/tatsu-lab/stanford_alpaca`](https://github.com/tatsu-lab/stanford_alpaca)，2023 年。

+   [146] H. W. Chung 等. 扩展指令微调语言模型。arXiv 预印本 arXiv:2210.11416，2022 年。

+   [147] S. Mangrulkar 等. Peft：最先进的参数高效微调方法。 [`github.com/huggingface/peft`](https://github.com/huggingface/peft)，2022 年。

+   [148] E. J. Hu 等. Lora：大型语言模型的低秩适配。arXiv 预印本 arXiv:2106.09685，2021 年。

+   [149] T. Dettmers 等. Qlora：高效量化 llms 的微调。NeurIPS，36，2024 年。

+   [150] L. Zhang 等. Lora-fa：用于大型语言模型微调的内存高效低秩适配。arXiv 预印本 arXiv:2308.03303，2023 年。

+   [151] J. Yosinski 等. 深度神经网络中的特征可迁移性如何？NeurIPS，2014 年。

+   [152] J. Howard 和 S. Ruder. 通用语言模型微调用于文本分类。见第 56 届计算语言学协会年会论文集（卷 1：长篇论文），2018 年。

+   [153] Y. Hong 等. 3d-llm：将 3d 世界注入大型语言模型。NeurIPS，2023 年。

+   [154] B. Lester 等. 参数高效提示调优的规模效应。在 2021 年自然语言处理实证方法会议论文集中，第 3045–3059 页，2021 年。

+   [155] P. Liu 等. 预训练、提示和预测：自然语言处理中的提示方法系统综述。ACM 计算机调查，55(9)：1–35，2023。

+   [156] J. Gu 等. 视觉-语言基础模型的提示工程系统综述。arXiv 预印本 arXiv:2307.12980，2023 年。

+   [157] T. Kojima 等. 大型语言模型是零-shot 推理者。见 NeurIPS，2022 年。

+   [158] Y. Wang 等. 超自然指令: 通过声明性指令在 1600+ 自然语言处理任务上实现泛化. arXiv 预印本 arXiv:2204.07705, 2022。

+   [159] V. Sanh 等. 多任务提示训练实现零样本任务泛化. 发表在 ICLR, 2022。

+   [160] T. Shin 等. Autoprompt: 通过自动生成的提示从语言模型中引出知识. arXiv 预印本 arXiv:2010.15980, 2020。

+   [161] Z. Jiang 等. 我们如何知道语言模型知道什么？计算语言学协会会刊, 2020。

+   [162] A. Prasad 等. Grips: 无梯度、基于编辑的指令搜索以提示大型语言模型. arXiv 预印本 arXiv:2203.07281, 2022。

+   [163] Y. Wen 等. 轻松实现硬提示: 基于梯度的离散优化用于提示调整和发现. NeurIPS, 2024。

+   [164] T. Vu 等. Spot: 通过软提示迁移实现更好的冻结模型适应. arXiv 预印本 arXiv:2110.07904, 2021。

+   [165] X. L. Li 和 P. Liang. Prefix-tuning: 优化连续提示以进行生成. arXiv 预印本 arXiv:2101.00190, 2021。

+   [166] Y. Gu 等. Ppt: 预训练提示调整以进行少样本学习. 发表在 ACL, pp. 8410–8423, 2022。

+   [167] Y. Su 等. 提示调整在自然语言处理中的可转移性. arXiv 预印本 arXiv:2111.06719, 2021。

+   [168] H. Wu 和 X. Shi. 跨领域情感分析的对抗性软提示调整. 第 60 届计算语言学协会年会会议录, 2022。

+   [169] X. Li 等. Sd4match: 学习提示稳定扩散模型以进行语义匹配. arXiv 预印本 arXiv:2310.17569, 2023。

+   [170] J. Wu 等. Infoprompt: 用于自然语言理解的信息论软提示调整. NeurIPS, 2024。

+   [171] Z. Wang 等. Chat-3d: 数据高效地调整大型语言模型以实现 3d 场景的通用对话, 2023。

+   [172] H. Huang 等. Chat-3d v2: 通过对象标识符桥接 3d 场景和大型语言模型. arXiv 预印本 arXiv:2312.08168, 2023。

+   [173] J. Pfeiffer 等. Adapterhub: 一个用于调整转换器的框架. arXiv 预印本 arXiv:2007.07779, 2020。

+   [174] A. Radford 等. 从自然语言监督中学习可转移的视觉模型. 发表在 ICML, pp. 8748–8763, PMLR, 2021。

+   [175] C. Jia 等. 通过噪声文本监督扩展视觉和视觉-语言表示学习. 发表在 ICML, 2021。

+   [176] J. Yang 等. 图像-文本-标签空间中的统一对比学习. 发表在 CVPR, 2022。

+   [177] W. Kim 等. Vilt: 无卷积或区域监督的视觉-语言转换器. 发表在 ICML, 2021。

+   [178] Y. Li 等. 监督无处不在：一种数据高效的对比语言-图像预训练范式. 发表在 ICLR, 2022。

+   [179] A. Singh 等. Flava: 一个基础的语言和视觉对齐模型. 发表在 CVPR, pp. 15638–15650, 2022。

+   [180] X. Gu 等. 通过视觉和语言知识蒸馏进行开放词汇检测. arXiv 预印本 arXiv:2104.13921, 2021。

+   [181] H. Rasheed 等. 弥合对象和图像级表示之间的差距以进行开放词汇检测. 在 NeurIPS, 2022。

+   [182] M. Minderer 等. 使用视觉变换器的简单开放词汇对象检测. 在 ECCV, 2022。

+   [183] Y. Zhong 等. Regionclip: 基于区域的语言-图像预训练. 在 CVPR, 2022。

+   [184] T. Lüddecke 和 A. Ecker. 使用文本和图像提示的图像分割. 在 CVPR, 2022。

+   [185] F. Liang 等. 使用掩码适应的剪辑的开放词汇语义分割. 在 CVPR, 2023。

+   [186] J. Ding 等. 解耦零-shot 语义分割. 在 CVPR, 第 11583–11592 页, 2022。

+   [187] B. Li 等. 语言驱动的语义分割. 在 ICLR, 2022。

+   [188] G. Ghiasi 等. 扩展开放词汇图像分割与图像级标签. 在 ECCV, 2022。

+   [189] G. Kim 等. 无 OCR 的文档理解变换器. 在 ECCV, 2022。

+   [190] Y. Xu 等. Layoutlm: 文本和布局的预训练用于文档图像理解. 在第 26 届 ACM SIGKDD 国际会议上，知识发现与数据挖掘会议论文集, 2020。

+   [191] B. Ni 等. 扩展语言-图像预训练模型以进行通用视频识别. 在 ECCV, 2022。

+   [192] Z. Wang 等. SimVLM: 使用弱监督的简单视觉语言模型预训练. 在 ICLR, 2022。

+   [193] J. Li 等. Blip: 用于统一视觉-语言理解和生成的语言-图像预训练. 在 ICML, 第 12888–12900 页\. PMLR, 2022。

+   [194] P. Wang 等. Ofa: 通过简单的序列到序列学习框架统一架构、任务和模态. 在 ICML, 第 23318–23340 页\. PMLR, 2022。

+   [195] J. Li 等. Blip-2: 使用冻结图像编码器和大型语言模型的语言-图像预训练. arXiv 预印本 arXiv:2301.12597, 2023。

+   [196] J.-B. Alayrac 等. Flamingo: 用于少样本学习的视觉语言模型. NeurIPS, 35:23716–23736, 2022。

+   [197] H. Liu 等. 视觉指令调整. 在 NeurIPS, 2024。

+   [198] J. Ho 等. 去噪扩散概率模型. 在 NeurIPS, 2020。

+   [199] Y. Song 等. 基于分数的生成建模通过随机微分方程. 在 ICLR, 2021。

+   [200] J. Ho 和 T. Salimans. 无分类器扩散引导. arXiv 预印本 arXiv:2207.12598, 2022。

+   [201] R. Rombach 等. 使用潜在扩散模型的高分辨率图像合成. 在 CVPR, 2022。

+   [202] J. Ho 等. Imagen 视频: 使用扩散模型生成高分辨率视频. arXiv 预印本 arXiv:2210.02303, 2022。

+   [203] U. Singer 等. 文本到 4D 动态场景生成. arXiv 预印本 arXiv:2301.11280, 2023。

+   [204] A. Hertz 等. 使用交叉注意力控制的 prompt-to-prompt 图像编辑. arXiv 预印本 arXiv:2208.01626, 2022。

+   [205] T. Brooks 等. Instructpix2pix: 学习跟随图像编辑指令. 在 CVPR, 2023。

+   [206] R. Mokady 等. 使用引导扩散模型编辑真实图像的 Null-text 反演. 在 CVPR, 2023。

+   [207] J. Wu 等人。Gaussctrl: 多视角一致的文本驱动 3D 高斯斑点编辑，2024 年。

+   [208] M. Caron 等人。自监督视觉变换器中的新兴特性。收录于 ICCV，2021 年。

+   [209] J. Zhou 等人。ibot: 使用在线分词器的图像 BERT 预训练。收录于 ICLR，2022 年。

+   [210] M. Oquab 等人。Dinov2: 无监督学习鲁棒视觉特征。arXiv 预印本 arXiv:2304.07193，2023 年。

+   [211] A. Kirillov 等人。Segment anything。arXiv 预印本 arXiv:2304.02643，2023 年。

+   [212] H. Zhang 等人。DINO: DETR 的改进去噪锚框用于端到端物体检测。arXiv 预印本 arXiv:2203.03605，2022 年。

+   [213] N. Carion 等人。基于变换器的端到端物体检测。收录于 ECCV，2020 年。

+   [214] S. Liu 等人。Grounding dino: 将 DINO 与有监督预训练结合用于开放集物体检测。arXiv 预印本 arXiv:2303.05499，2023 年。

+   [215] L. Tang 等人。从图像扩散中获得的突现对应关系。NeurIPS，2024 年。

+   [216] J. Tian 等人。Diffuse, attend, and segment: 使用稳定扩散的无监督零-shot 分割。arXiv 预印本 arXiv:2308.12469，2023 年。

+   [217] Z. Chen 等人。Scan2cap: 在 RGB-D 扫描中的上下文感知密集标注。收录于 CVPR，页码 3193–3203，2021 年。

+   [218] D. Z. Chen 等人。Scanrefer: 使用自然语言在 RGB-D 扫描中进行 3D 物体定位。收录于 ECCV，2020 年。

+   [219] A. Celikyilmaz 等人。文本生成评估：一项综述。arXiv 预印本 arXiv:2006.14799，2020 年。

+   [220] K. Papineni 等人。Bleu: 一种用于机器翻译自动评估的方法。收录于第 40 届计算语言学协会年会论文集，页码 311–318，2002 年。

+   [221] C.-Y. Lin。Rouge: 用于自动摘要评估的工具包。收录于《文本摘要的分支发展》，页码 74–81，2004 年。

+   [222] S. Banerjee 和 A. Lavie。Meteor: 一种改进与人工评估相关性的自动评价指标。收录于 ACL 机器翻译和/或摘要的内在与外在评估测量研讨会论文集，页码 65–72，2005 年。

+   [223] R. Vedantam 等人。Cider: 基于共识的图像描述评估。收录于 CVPR，页码 4566–4575，2015 年。

+   [224] N. Reimers 和 I. Gurevych。Sentence-bert: 使用 Siamese BERT 网络的句子嵌入。arXiv 预印本 arXiv:1908.10084，2019 年。

+   [225] T. Zhang 等人。BERTScore: 使用 BERT 评估文本生成。arXiv 预印本 arXiv:1904.09675，2019 年。

+   [226] S. Chen 等人。使用 vote2cap-detr 的端到端 3D 密集标注。收录于 CVPR，页码 11124–11133，2023 年。

+   [227] Z. Chen 等人。Unit3d: 一种用于 3D 密集标注和视觉定位的统一变换器。收录于 ICCV，页码 18109–18119，2023 年。

+   [228] P. Achlioptas 等人。Referit3d: 用于真实场景中细粒度 3D 物体识别的神经监听器。收录于 ECCV，页码 422–440。Springer，2020 年。

+   [229] Z. Lu 等人。Scaneru: 基于具象参考理解的交互式 3D 视觉定位。arXiv 预印本 arXiv:2303.13186，2023 年。

+   [230] Y. Zhang 等. Multi3drefer: 将文本描述与多个 3d 对象对接. 发表在 ICCV 上，页码 15225–15236, 2023.

+   [231] W. Huang 等. 3d 场景中的稠密目标定位. 发表在第 31 届 ACM 国际多媒体会议论文集上，页码 5017–5026, 2023.

+   [232] P.-H. Huang 等. 文本引导的图神经网络用于 3d 实例分割. 发表在 AAAI 上，第 35 卷，页码 1610–1618, 2021.

+   [233] X. Ma 等. Sqa3d: 在 3d 场景中的情境问答. arXiv 预印本 arXiv:2210.07474, 2022.

+   [234] D. Azuma 等. Scanqa: 空间场景理解的 3d 问答. 发表在 CVPR 上，2022.

+   [235] T. Qian 等. Nuscenes-qa: 自主驾驶场景的多模态视觉问答基准. arXiv 预印本 arXiv:2305.14836, 2023.

+   [236] Y. Hong 等. 从多视图图像中学习和推理 3d 概念. 发表在 CVPR 上，页码 9202–9212, 2023.

+   [237] P. Anderson 等. Spice: 语义命题图像标题评估. 发表在 ECCV 上，页码 382–398\. Springer, 2016.

+   [238] P. Anderson 等. 关于具身导航代理的评估. arXiv 预印本 arXiv:1807.06757, 2018.

+   [239] P. Anderson 等. 视觉与语言导航: 在真实环境中解读视觉基础导航指令. 发表在 CVPR 上，页码 3674–3683, 2018.

+   [240] G. Ilharco 等. 使用动态时间规整的指令条件导航的通用评估. arXiv 预印本 arXiv:1907.05446, 2019.

+   [241] J. Gu 等. 视觉与语言导航: 任务、方法和未来方向的综述. arXiv 预印本 arXiv:2203.12667, 2022.

+   [242] M. Shridhar 等. Cliport: 机器人操作的“什么和哪里”路径. 发表在机器人学习会议上，页码 894–906\. PMLR, 2022.

+   [243] H.-H. Lee 等. 文本到 3d 形状生成. arXiv 预印本 arXiv:2403.13289, 2024.

+   [244] L. Xue 等. Ulip: 学习语言、图像和点云的统一表示以进行 3d 理解. 发表在 CVPR 上，页码 1179–1189, 2023.

+   [245] T. Wu 等. Gpt-4v (ision) 是一种与人类对齐的文本到 3d 生成评估器. arXiv 预印本 arXiv:2401.04092, 2024.

+   [246] I. Armeni 等. 大规模室内空间的 3d 语义解析. 发表在 CVPR 上，页码 1534–1543, 2016.

+   [247] S. Sengupta 等. 使用立体视觉的城市 3d 语义建模. 发表在 ICRA 上，页码 580–585\. IEEE, 2013.

+   [248] J. McCormac 等. Semanticfusion: 基于卷积神经网络的稠密 3d 语义映射. 发表在 ICRA 上，页码 4628–4635\. IEEE, 2017.

+   [249] J. Huang 等. 通过动态图学习的生成性 3d 部件组装. 发表在 NeurIPS 上，2020.

+   [250] J. Cheng 等. Score-pa: 基于评分的 3d 部件组装. 英国机器视觉会议, 2023.

+   [251] L. Jiang 等. Pointgroup: 3d 实例分割的双集合点分组. 发表在 CVPR 上，页码 4867–4876, 2020.

+   [252] J. Hou 等. 3d-sis: RGB-D 扫描的 3d 语义实例分割. 发表在 CVPR 上，页码 4421–4430, 2019.

+   [253] W. Wang 等. Sgpn: 用于 3d 点云实例分割的相似性组提议网络. 发表在 CVPR 上，页码 2569–2578, 2018.

+   [254] L. Han 等人。Occuseg：关注占用的 3D 实例分割。CVPR 会议，pp. 2940–2949，2020 年。

+   [255] X. Song 等人。Apollocar3d：一个用于自主驾驶的大规模 3D 汽车实例理解基准。CVPR 会议，pp. 5452–5462，2019 年。

+   [256] G. Zhan 等人。野外的模态真实和补全。CVPR 会议，2024 年。

+   [257] G. Zhan 等人。稳定扩散对 3D 场景了解多少？在 arXiv:2310.06836，2023 年。

+   [258] M. Feng 等人。探索用于 3D 点云场景图预测的层次空间布局线索。IEEE 多媒体学报，2023 年。

+   [259] C. Zhang 等人。通过隐式表示从单幅图像进行整体 3D 场景理解。CVPR 会议，pp. 8833–8842，2021 年。

+   [260] C. Zhang 等人。Deeppanocontext：通过整体场景上下文图和基于关系的优化进行全景 3D 场景理解。ICCV 会议，pp. 12632–12641，2021 年。

+   [261] G. Zhan 等人。一个三层插件以改进遮挡检测。英国机器视觉会议，2022 年。

+   [262] A. Delitzas 等人。Scenefun3d：3D 场景中的细粒度功能性和适用性理解。CVPR 会议，2024 年。

+   [263] K. Cheng 等人。在遮挡下学习环境感知适用性以进行 3D 关节物体操作。NeurIPS 会议，2023 年。

+   [264] Y. Qiu 等人。基于多视图图像的 3D 感知场景变化字幕。IEEE 机器人与自动化快报，2020 年。

+   [265] S. Looper 等人。3D vsg：通过 3D 变量场景图进行长期语义场景变化预测。ICRA 会议，pp. 8179–8186，IEEE，2023 年。

+   [266] R. Fu 等人。Scene-llm：扩展语言模型以进行 3D 视觉理解和推理，2024 年。

+   [267] R. Xu 等人。Pointllm：赋能大型语言模型理解点云。arXiv 预印本 arXiv:2308.16911，2023 年。

+   [268] Z. Qi 等人。Gpt4point：一个统一的点语言理解和生成框架。arXiv 预印本 arXiv:2312.02980，2023 年。

+   [269] Z. Li 等人。3dmit：用于场景理解的 3D 多模态指令调整。arXiv 预印本 arXiv:2401.03201，2024 年。

+   [270] J. Huang 等人。一个在 3D 世界中的具身通用体。ICML 会议，2024 年。

+   [271] S. Yang 等人。Lidar-llm：探索大型语言模型在 3D 激光雷达理解中的潜力。arXiv 预印本 arXiv:2312.14074，2023 年。

+   [272] Z. Guo 等人。Point-bind & point-llm：将点云与多模态对齐以进行 3D 理解、生成和指令跟随。arXiv 预印本 arXiv:2309.00615，2023 年。

+   [273] D. Liu 等人。3daxiesprompts：释放 gpt-4v 的 3D 空间任务能力。arXiv 预印本 arXiv:2312.09738，2023 年。

+   [274] W. Chen 等人。利用大型语言模型进行机器人 3D 场景理解。arXiv 预印本 arXiv:2209.05629，2022 年。

+   [275] K. Rana 等人。Sayplan：利用 3D 场景图将大型语言模型与任务规划结合起来。arXiv 预印本 arXiv:2307.06135，2023 年。

+   [276] H. Zhen 等人。3d-vla：一个 3D 视觉-语言-行动生成世界模型。arXiv 预印本 arXiv:2403.09631，2024 年。

+   [277] Z. Xiao 等. 通过提示链式接触实现统一的人类-场景交互。arXiv 预印本 arXiv:2309.07918，2023 年。

+   [278] X. L. Li 等. 大型语言模型中常识知识的系统研究。在 Y. Goldberg 等编者的《2022 年自然语言处理实证方法会议论文集》中，第 11838–11855 页，阿布扎比，阿联酋，2022 年 12 月。计算语言学协会。

+   [279] H. Wang 等. 超越第一印象：整合联合多模态线索以实现全面的 3D 表示。在第 31 届 ACM 国际多媒体会议论文集中，第 3403–3414 页，2023 年。

+   [280] C. Nash 等. Polygen：一种自回归的 3D 网格生成模型。在 ICML，第 7220–7229 页。PMLR，2020 年。

+   [281] F. De La Torre 等. Llmr：使用大型语言模型实时提示互动世界。arXiv 预印本 arXiv:2309.12276，2023 年。

+   [282] Y. Siddiqui 等. Meshgpt：使用仅解码器的变换器生成三角网格。arXiv 预印本 arXiv:2311.15475，2023 年。

+   [283] F. Yin 等. Shapegpt：通过统一的多模态语言模型进行 3D 形状生成。arXiv 预印本 arXiv:2311.17618，2023 年。

+   [284] Y. Yang 等. Holodeck：语言指导的 3D 具身 AI 环境生成。在 CVPR，第 30 卷，第 20–25 页。IEEE/CVF，2024 年。

+   [285] A. Chang 等. Matterport3d：从室内环境中的 RGB-D 数据中学习。国际 3D 视觉会议（3DV），2017 年。

+   [286] Chatgpt. [`openai.com/blog/chatgpt`](https://openai.com/blog/chatgpt)。访问时间：2023-07-22。

+   [287] D. He 等. Transrefer3d：用于细粒度 3D 视觉定位的实体和关系感知变换器。在第 29 届 ACM 国际多媒体会议论文集中，第 2344–2352 页，2021 年。

+   [288] X. Yu 等. Point-bert：通过掩码点建模预训练 3D 点云变换器。在 CVPR，第 19313–19322 页，2022 年。

+   [289] J. Zhou 等. Uni3d：探索大规模统一的 3D 表示。在 ICLR，2024 年。

+   [290] Q. Gu 等. Conceptgraphs：用于感知和规划的开放词汇 3D 场景图。arXiv 预印本 arXiv:2309.16650，2023 年。

+   [291] B. Cheng 等. 每像素分类并不是语义分割所需的一切。在 NeurIPS，2021 年。

+   [292] Y. Zhou 和 O. Tuzel. Voxelnet：基于点云的 3D 对象检测的端到端学习。在 CVPR，第 4490–4499 页，2018 年。

+   [293] M. Deitke 等. Objaverse：一个标注的 3D 对象宇宙。在 CVPR，第 13142–13153 页，2023 年。

+   [294] Z. Zhu 等. 3d-vista：用于 3D 视觉和文本对齐的预训练变换器。在 ICCV，第 2911–2921 页，2023 年。

+   [295] J. Wald 等. Rio：在变化的室内环境中进行 3D 对象实例重新定位。在 ICCV，第 7658–7667 页，2019 年。

+   [296] A. X. Chang 等. Shapenet：一个信息丰富的 3D 模型库。arXiv 预印本 arXiv:1512.03012，2015 年。

+   [297] M. A. Uy 等. 重新审视点云分类：基于真实世界数据的新基准数据集和分类模型。在 ICCV，2019 年。

+   [298] S. Zhang 等人。大型语言模型的指令调优：综述。arXiv 预印本 arXiv:2308.10792，2023 年。

+   [299] R. Beaumont。Clip 检索：轻松计算 clip 嵌入并构建 clip 检索系统，2022 年。

+   [300] A. Guzhov 等人。Audioclip：将 clip 扩展到图像、文本和音频。在 ICASSP 2022-2022 IEEE 国际声学、语音和信号处理会议（ICASSP）上，第 976–980 页，2022 年。

+   [301] N. Mu 等人。Slip：自我监督与语言图像预训练的结合。在 ECCV 会议上，第 529–544 页，2022 年。

+   [302] R. Girdhar 等人。Imagebind：一个绑定所有内容的嵌入空间。在 CVPR 会议上，第 15180–15190 页，2023 年。

+   [303] Z. Hu 等人。SceneCraft：一个用于将 3D 场景合成 Blender 代码的 LLM 代理。在 ICLR 2024 大型语言模型（LLM）代理研讨会中，2024 年。

+   [304] J. Zhang 等人。Clip-fo3d：从 2D 密集剪辑中学习自由开放世界的 3D 场景表示。在 ICCV 会议上，第 2048–2059 页，2023 年。

+   [305] H. Ha 和 S. Song。语义抽象：基于 2D 视觉语言模型的开放世界 3D 场景理解。在 CoRL 会议上，2022 年。

+   [306] K. Yamazaki 等人。Open-fusion：实时开放词汇 3D 映射和可查询场景表示。arXiv 预印本 arXiv:2310.03923，2023 年。

+   [307] X. Zou 等人。Segment everything everywhere all at once。在 NeurIPS 会议上，第 36 期，2024 年。

+   [308] R. Ding 等人。Pla：基于语言的开放词汇 3D 场景理解。在 CVPR 会议上，2023 年。

+   [309] J. Yang 等人。Regionplc：面向开放世界 3D 场景理解的区域点语言对比学习。arXiv 预印本 arXiv:2304.00962，2023 年。

+   [310] S. Lu 等人。Ovir-3d：无需在 3D 数据上训练的开放词汇 3D 实例检索。在机器人学习会议上，第 1610–1620 页。PMLR，2023 年。

+   [311] Y. Cao 等人。Coda：开放词汇 3D 物体检测的协作新盒发现和跨模态对齐。在 NeurIPS 会议上，第 36 期，2023 年。

+   [312] A. Takmaz 等人。OpenMask3D：开放词汇 3D 实例分割。在 NeurIPS 会议上，2023 年。

+   [313] P. D. Nguyen 等人。Open3dis：基于 2D 掩膜指导的开放词汇 3D 实例分割。arXiv 预印本 arXiv:2312.10671，2023 年。

+   [314] Z. Huang 等人。Openins3d：3D 开放词汇实例分割的快照和查找。arXiv 预印本，2023 年。

+   [315] D. Rozenberszki 等人。基于语言的室内 3D 语义分割。在 ECCV 会议上，第 125–141 页。Springer，2022 年。

+   [316] S. Kobayashi 等人。通过特征场蒸馏解构 nerf 进行编辑。在 NeurIPS 会议上，第 35 卷：23311–23330，2022 年。

+   [317] N. Tsagkas 等人。Vl-fields：迈向语言基础的神经隐式空间表示。arXiv 预印本 arXiv:2305.12427，2023 年。

+   [318] K. Liu 等人。弱监督的 3D 开放词汇分割。在 NeurIPS 会议上，第 36 期，2024 年。

+   [319] M. Qin 等人。Langsplat：3D 语言高斯溅射。arXiv 预印本 arXiv:2312.16084，2023 年。

+   [320] Y. Bhalgat 等人。N2f2：具有嵌套神经特征场的层次化场景理解，2024 年。

+   [321] R. Rombach 等人。使用潜在扩散模型进行高分辨率图像合成。在 CVPR 会议上，第 10684–10695 页，2022 年。

+   [322] C. Saharia 等. 具有深度语言理解的照片级真实文本到图像扩散模型. NeurIPS, 35:36479–36494, 2022.

+   [323] A. Jain 等. 零-shot 文本引导的对象生成与梦想场. 在 CVPR, 页码 867–876, 2022.

+   [324] A. Sanghi 等. Clip-forge: 朝着零-shot 文本到形状生成迈进. 在 CVPR, 页码 18603–18613, 2022.

+   [325] O. Michel 等. Text2mesh: 基于文本的网格神经风格化. 在 CVPR, 页码 13492–13502, 2022.

+   [326] C.-H. Lin 等. Magic3d: 高分辨率的文本到 3d 内容创作. arXiv 预印本 arXiv:2211.10440, 2022.

+   [327] R. Chen 等. Fantasia3d: 解开几何和外观以创建高质量的文本到 3d 内容. 在 ICCV, 页码 22246–22256, 2023.

+   [328] T. Shen 等. Deep marching tetrahedra: 用于高分辨率 3d 形状合成的混合表示. 在 NeurIPS, 2021.

+   [329] Z. Wang 等. Prolificdreamer: 高保真和多样化的文本到 3d 生成与变分评分蒸馏. NeurIPS, 36, 2024.

+   [330] J. Xu 等. Dream3d: 使用 3d 形状先验和文本到图像扩散模型的零-shot 文本到 3d 合成. 在 CVPR, 页码 20908–20918, 2023.

+   [331] Y. Shi 等. Mvdream: 多视角扩散用于 3d 生成. arXiv 预印本 arXiv:2308.16512, 2023.

+   [332] J. Zhang 等. Text2nerf: 基于文本的 3d 场景生成与神经辐射场. IEEE Transactions on Visualization and Computer Graphics, 2024.

+   [333] E. Richardson 等. Texture: 基于文本的 3d 形状纹理化. 在 ACM SIGGRAPH 2023 会议论文集, 页码 1–11, 2023.

+   [334] D. Z. Chen 等. Text2tex: 基于文本的纹理合成通过扩散模型. 在 ICCV, 页码 18558–18568, 2023.

+   [335] D. Z. Chen 等. Scenetex: 通过扩散先验进行室内场景的高质量纹理合成. arXiv 预印本 arXiv:2311.17261, 2023.

+   [336] R. Jiang 等. Avatarcraft: 将文本转换为具有参数化形状和姿态控制的神经人类头像. 在 ICCV, 页码 14371–14382, 2023.

+   [337] F. Hong 等. Avatarclip: 零-shot 基于文本的 3d 头像生成和动画. ACM TOG, 41(4):1–19, 2022.

+   [338] C. Diller 和 A. Dai. Cg-hoi: 联系引导的 3d 人类-物体交互生成. 在 CVPR, 2024.

+   [339] L. Li 和 A. Dai. Genzi: 零-shot 3d 人类场景交互生成. 在 CVPR, 2024.

+   [340] A. Vilesov 等. Cg3d: 通过高斯喷洒进行文本到 3d 的组成生成. arXiv 预印本 arXiv:2311.17907, 2023.

+   [341] R. Po 和 G. Wetzstein. 使用局部条件扩散的组成 3d 场景生成. arXiv 预印本 arXiv:2303.12218, 2023.

+   [342] G. Gao 等. Graphdreamer: 从场景图中合成 3d 场景. 在 CVPR, 2024.

+   [343] Z. Ziyu 等. 3d-vista: 预训练的变压器用于 3d 视觉和文本对齐. 在 ICCV, 2023.

+   [344] B. Chen 等. Spatialvlm: 赋予视觉-语言模型空间推理能力. arXiv 预印本 arXiv:2401.12168, 2024.

+   [345] A. Delitzas 等人。Multi-clip: 对比视觉-语言预训练在 3D 场景中的问答任务。arXiv 预印本 arXiv:2306.02329，2023 年。

+   [346] Z. Yuan 等人。Instancerefer: 通过实例多级上下文引用进行点云的协作全局理解。发表于 ICCV，第 1791–1800 页，2021 年。

+   [347] J. Roh 等人。Languagerefer: 用于 3D 视觉基础的空间语言模型。发表于 Conference on Robot Learning，第 1046–1056 页。PMLR，2022 年。

+   [348] L. Zhao 等人。3dvg-transformer: 点云上的视觉基础关系建模。发表于 ICCV，第 2928–2937 页，2021 年。

+   [349] T. Luo 等人。使用预训练模型的可扩展 3D 标注。发表于 NeurIPS，第 36 卷，2024 年。

+   [350] K. Chen 等人。Text2shape: 通过学习联合嵌入从自然语言生成形状。发表于 ACCV，第 100–116 页。Springer，2019 年。

+   [351] B. Jia 等人。Sceneverse: 扩展 3D 视觉-语言学习以实现扎根的场景理解。arXiv 预印本 arXiv:2401.09340，2024 年。

+   [352] T. Wang 等人。Embodiedscan: 面向具身 AI 的全面多模态 3D 感知套件。arXiv 预印本 arXiv:2312.16170，2023 年。

+   [353] A. Abdelreheem 等人。Scanents3d: 利用短语到 3D 对象的对应关系改进 3D 场景中的视觉语言模型。发表于 WACV，第 3524–3534 页，2024 年。

+   [354] Z. Lin 等人。Wildrefer: 利用多模态视觉数据和自然语言进行大规模动态场景中的 3D 对象定位。arXiv 预印本 arXiv:2304.05645，2023 年。

+   [355] T. Miyanishi 等人。Cross3dvg: 用于跨数据集的 3D 视觉基础的基线和数据集。arXiv 预印本 arXiv:2305.13876，2023 年。

+   [356] S. Kato 等人。Arkitscenerefer: 在多样的现实世界 3D 室内场景中基于文本的小物体定位。发表于 Findings of the Association for Computational Linguistics: EMNLP 2023，第 784–799 页，2023 年。

+   [357] S. Ye 等人。3D 问答，2021 年。

+   [358] X. Yan 等人。通过组合场景操作对点云进行全面的视觉问答。IEEE Transactions on Visualization & Computer Graphics，第 1–13 页，2023 年。

+   [359] M. Li 等人。M3dbench: 使用多模态 3D 提示指导大型模型。arXiv 预印本 arXiv:2312.10763，2023 年。

+   [360] Z. Yin 等人。Lamm: 语言辅助的多模态指令调优数据集、框架和基准。arXiv 预印本 arXiv:2306.06687，2023 年。

+   [361] A. Dai 等人。Scannet: 丰富注释的室内场景 3D 重建。发表于 CVPR，2017 年。

+   [362] F. Zeng 等人。用于机器人技术的大型语言模型：一项调查。arXiv 预印本 arXiv:2311.07226，2023 年。

+   [363] H. Zhou 等人。语言条件下的机器人操作学习：一项调查。arXiv 预印本 arXiv:2312.10807，2023 年。

+   [364] H. Caesar 等人。nuscenes: 一种用于自动驾驶的多模态数据集。arXiv 预印本 arXiv:1903.11027，2019 年。

+   [365] OpenAI。GPT-4 技术报告。arXiv 预印本 arXiv:2303.08774，2023 年。

+   [366] A. Kirillov 等人。Segment anything。arXiv 预印本 arXiv:2304.02643，2023 年。

+   [367] P. Cong 等. Stcrowd：一个用于拥挤场景中行人感知的多模态数据集。发表于 CVPR，页码 19608–19617，2022 年。

+   [368] G. Baruch 等. Arkitscenes：一个用于使用移动 RGB-D 数据进行 3D 室内场景理解的多样化现实世界数据集。arXiv 预印本 arXiv:2111.08897，2021 年。

+   [369] S. K. Ramakrishnan 等. Habitat-Matterport 3D 数据集 (HM3d)：用于具身 AI 的 1000 个大规模 3D 环境。发表于第三十五届神经信息处理系统会议数据集与基准测试分会 (第二轮)，2021 年。

+   [370] K. Yadav 等. Habitat-Matterport 3D 语义数据集。arXiv 预印本 arXiv:2210.05633，2022 年。

+   [371] J. Wald 等. 从 3D 室内重建中学习 3D 语义场景图。发表于 CVPR，2020 年。

生成于 2024 年 5 月 16 日 16:49:07，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
