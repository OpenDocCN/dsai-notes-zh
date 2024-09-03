<!--yml

分类：未分类

日期：2024-09-03 17:31:06

-->

# 更快更轻的 LLM：当前挑战与前进方向的调查

> 来源：[`arxiv.org/html/2402.01799`](https://arxiv.org/html/2402.01799)

1.  [1 介绍](https://arxiv.org/html/2402.01799v2#S1 "在《更快更轻的 LLM：当前挑战与前进方向的调查》中")

1.  [2 模型压缩：概述](https://arxiv.org/html/2402.01799v2#S2 "在《更快更轻的 LLM：当前挑战与前进方向的调查》中")

    1.  [2.1 深度模型的压缩](https://arxiv.org/html/2402.01799v2#S2.SS1 "在《模型压缩概述》中 ‣ 更快更轻的 LLM：当前挑战与前进方向的调查")

    1.  [2.2 LLM 的压缩](https://arxiv.org/html/2402.01799v2#S2.SS2 "在《模型压缩概述》中 ‣ 更快更轻的 LLM：当前挑战与前进方向的调查")

1.  [3 实验分析](https://arxiv.org/html/2402.01799v2#S3 "在《更快更轻的 LLM：当前挑战与前进方向的调查》中")

1.  [4 挑战与前进方向](https://arxiv.org/html/2402.01799v2#S4 "在《更快更轻的 LLM：当前挑战与前进方向的调查》中")

1.  [5 结论](https://arxiv.org/html/2402.01799v2#S5 "在《更快更轻的 LLM：当前挑战与前进方向的调查》中")

# 更快更轻的 LLM：当前挑战与前进方向的调查

Arnav Chavan^(1,2)    Raghav Magazine¹    Shubham Kushwaha¹    Mérouane Debbah³ &Deepak Gupta²

¹Nyun AI，印度 ²Transmute AI Lab (Texmin Hub)，印度 IIT (ISM) Dhanbad

³KU 6G 研究中心，哈利法科技大学，阿布扎比，阿联酋

arnav.chavan@nyunai.com, guptadeepak2806@gmail.com

###### 摘要

尽管 LLM 的表现令人印象深刻，但其广泛应用面临挑战，因为推理过程中需要大量的计算和内存。近期在模型压缩和系统级优化方法方面取得的进展旨在提升 LLM 的推理能力。本调查概述了这些方法，并强调了最近的发展。通过对 LLaMA(/2)-7B 的实验，我们评估了各种压缩技术，为在统一环境中高效部署 LLM 提供了实用见解。对 LLaMA(/2)-7B 的实证分析突出了这些方法的有效性。根据调查见解，我们识别了当前的局限性，并讨论了改善 LLM 推理效率的潜在未来方向。我们在[`github.com/nyunAI/Faster-LLM-Survey`](https://github.com/nyunAI/Faster-LLM-Survey)发布了代码库，以重现本文中呈现的结果。

## 1 介绍

随着 GPT Brown 等人（[2020](https://arxiv.org/html/2402.01799v2#bib.bib4)）和 LLaMa Touvron 等人（[2023a](https://arxiv.org/html/2402.01799v2#bib.bib55)、[b](https://arxiv.org/html/2402.01799v2#bib.bib56)）等模型的出现，LLMs 的到来标志着语言相关任务的一场新革命，涵盖了从文本理解和总结到语言翻译和生成。这些模型通常由数十亿个参数组成，在捕捉自然语言中复杂图案、细致上下文和语义表征方面表现出了卓越性能。因此，它们已成为各种应用中不可或缺的工具，促进了人工智能、信息检索和人机交互等各个领域的发展。

尽管其无与伦比的性能，LLMs 的广泛应用受到它们大量的计算和内存需求的阻碍，这对在资源受限环境中进行部署提出了挑战。例如，加载 LLaMa-70B 模型需要 140GB VRAM，不包括模型推理所需的内存。对高效部署的需求已经引发了针对 LLMs 专门量身定制的模型压缩以及系统级修改技术的最新研究。然而，当前的改进通常伴随着模型性能的显著降低，并需要找到新的研究方向来找到解决这一问题的理想解决方案。

最近的一项调查研究简要概述了最近提出的 LLM 压缩方法、评估指标以及用来对其进行基准测试的数据（Zhu 等人，[2023](https://arxiv.org/html/2402.01799v2#bib.bib64)）。但是，为了进一步推动 LLMs 的前沿研究向实际推理改进的方向发展，仍然缺少全面的研究。在本次调查论文中，我们探讨了现有方法，旨在通过模型压缩以及系统级优化使 LLMs 变得高效。为了公平地比较各种方法，我们提供了使用不同压缩技术应用于 LLaMa(/2)-7B 的经验观察。我们的评估包括提供实际优势的方法，包括结构剪枝、量化以及现有文献提供的不同推理引擎的系统级优化。我们分享了从这些实验中得出的有价值的见解，以呈现对高效 LLMs 的有用而实际的理解。此外，我们还公开了与实验相关的代码和基准。我们还检验了当前压缩方法在一般深度学习和特别是 LLMs 推断方面存在的困难，并讨论了克服这些问题的潜在研究方向。

总体而言，本文的贡献如下。

+   •

    我们提供了模型压缩领域的简要概述，强调了对轻量化和高效 LLMs 做出显著贡献的关键方法。

+   •

    除了模型压缩，系统级修改在加速 LLM 推理方面也发挥了重要作用，我们也讨论了这些方法。

+   •

    为了提供实际视角，我们展示了在标准化设置下对 LLMs 的知名压缩方法的实证分析。获得的洞见有助于根据部署环境做出关于 LLM 压缩方法选择的明智决策。

+   •

    根据我们调查和实证分析得出的洞见，我们系统地指出了现有的局限性，并提出了实现 LLM 推理最佳效率的可行路径。

## 2 模型压缩：概述

模型压缩技术已经成为一个关键的研究领域，提供了有前景的解决方案来提高资源密集型深度学习模型的效率。开发高效的大型语言模型（LLMs）的领域可以从这一领域的洞见和方法中显著受益。在深入探讨构建高效 LLMs 及其相关现有工作之前，我们先概述了一些在深度学习模型压缩中常用的流行方法。以下，我们首先介绍传统的模型压缩方法，并简要讨论与传统深度学习模型相关的发展。接下来，我们提供了现有文献中与 LLMs 压缩相关的工作概述。

### 2.1 深度模型的压缩

*架构剪枝*是指通过消除冗余或影响较小的连接、神经元或整个层，系统性地减少神经网络的复杂度。该技术旨在提高模型效率，降低计算成本，并减轻过拟合，而不显著影响性能。剪枝涉及根据各种标准，如权重大小、激活模式或敏感性分析，识别并移除连接或单元。剪枝后的模型保留了其关键特征，同时实现了更紧凑的表示，这在计算资源有限的场景中尤为重要，如边缘设备或移动应用。 

在广泛研究的剪枝方法中，**彩票票假设** Frankle 和 Carbin ([2019](https://arxiv.org/html/2402.01799v2#bib.bib16)) 提供了对权重初始化和剪枝网络结构对神经网络剪枝影响的基本见解。网络瘦身 Liu 等人 ([2017](https://arxiv.org/html/2402.01799v2#bib.bib39)); Chavan 等人 ([2022](https://arxiv.org/html/2402.01799v2#bib.bib5)) 介绍了一种通过对通道缩放因子施加稀疏性正则化来剪枝 CNNs 中的通道并减少 Transformers 中权重维度的方法。移动剪枝通过利用一阶信息，即保留远离零的权重，相比于零阶方法保留较大幅度的权重，展示了对 BERT Kenton 和 Toutanova ([2019](https://arxiv.org/html/2402.01799v2#bib.bib28)) 模型的大规模剪枝。Lagunas 等人 ([2021](https://arxiv.org/html/2402.01799v2#bib.bib31)) 在变换器层的权重矩阵中引入了块结构，并对其应用了移动剪枝以实现实际的加速。最近，Jiang 等人 ([2023a](https://arxiv.org/html/2402.01799v2#bib.bib25)) 认为对一阶剪枝来说微调是多余的，并提出了静态模型剪枝 (SMP)，这是一种无需微调的语言模型剪枝方法。

*量化* 减少了神经网络中数值值的精度，通常是从 32 位浮点数到更低位宽的表示，如 8 位整数，从而缩小了模型的内存占用，加快了推理速度，并使得在计算资源有限的硬件上实现更高效的部署。在量化过程中，权重和/或激活值被舍入到离散的值集合中，导致计算效率和模型准确性之间的权衡。即便如此，最先进的量化方法也能将对性能的影响降到最低。

量化感知训练 (QAT) Ni 等人 ([2020](https://arxiv.org/html/2402.01799v2#bib.bib43)) 涉及在整个训练过程中对模型参数进行量化，包括前向传播和反向传播。LSQ Esser 等人 ([2019](https://arxiv.org/html/2402.01799v2#bib.bib15)) 提出了每个权重的可学习步长，以及其他网络参数。Tailor 等人 ([2021](https://arxiv.org/html/2402.01799v2#bib.bib52)) 介绍了一种与架构无关的图神经网络剪枝方法。另一方面，后训练量化 (PTQ) Banner 等人 ([2019](https://arxiv.org/html/2402.01799v2#bib.bib3)) 发现了权重和激活的最佳剪裁范围和通道位宽设置。OSME Choukroun 等人 ([2019](https://arxiv.org/html/2402.01799v2#bib.bib9)) 提出了一个 PTQ 方法，其中最小化了量化张量与相应浮点张量之间的 l2 距离。

*知识蒸馏* 旨在训练一个计算效率高的模型，通常称为学生模型，使其模拟一个更大、更复杂的模型的预测，该模型被称为教师模型。这个过程涉及将嵌入在教师模型中的知识，通常以软概率或中间表示的形式，转移到学生模型。蒸馏在部署资源有限的场景中尤其有用，因为它可以创建较小的模型，而这些模型保留了其较大对手的性能。此外，蒸馏有助于应对过拟合等问题，改善泛化能力，并促进深层复杂模型知识向简单架构的迁移。

知识蒸馏技术可以分为三类，即基于响应的、基于特征的和基于实例关系的。基于响应的蒸馏 Hinton 等人 ([2015](https://arxiv.org/html/2402.01799v2#bib.bib20)) 训练学生模型以模拟教师模型的最终输出，而基于特征的蒸馏 Tian 等人 ([2022](https://arxiv.org/html/2402.01799v2#bib.bib54)) 则训练学生模型以模拟教师模型的中间特征图。基于关系的蒸馏更进一步，通过使用一个目标来建模学生和教师网络中各种特征图的相似性相关性。最近，Chen 等人 ([2023b](https://arxiv.org/html/2402.01799v2#bib.bib8)) 在预训练阶段使用了知识蒸馏，将 BERT 的大小减少了 40%，使其速度提升了 60%，同时保留了 97% 的语言理解能力。

*低秩分解* 通过将权重矩阵分解成更小的低维矩阵来降低模型的计算复杂度，从而近似初始的全秩矩阵。这也减少了需要在模型中存储的参数数量，加快了矩阵乘法的速度，从而减少了内存和延迟需求。

Jaderberg 等人 ([2014](https://arxiv.org/html/2402.01799v2#bib.bib22)) 提出了一个与架构无关的加速卷积层的方法，使用了张量分解和有区分度的微调；而 Denton 等人 ([2014](https://arxiv.org/html/2402.01799v2#bib.bib12)) 提出了具有低秩分解的聚类方法以加快 CNN。Sainath 等人 ([2013](https://arxiv.org/html/2402.01799v2#bib.bib45)) 研究了声学模型中的低秩矩阵分解，其中分解应用于网络的最后一层。Lebedev 等人 ([2015](https://arxiv.org/html/2402.01799v2#bib.bib32)) 介绍了使用非线性最小二乘法计算的典范多项分解，以加速 CNN。Tai 等人 ([2016](https://arxiv.org/html/2402.01799v2#bib.bib51)) 提出了全球分解优化算法，因此表现优于迭代方法。

### 2.2 LLM 的压缩

LLM 的压缩相比于传统深度学习模型表现出独特的挑战，主要是由于前者的规模巨大。许多已建立的压缩方法依赖于执行细调步骤来恢复压缩阶段丢失的性能。然而，当应用于 LLM 时，由于其巨大尺寸，这种方法遇到了显著的限制，因此需要在处理 LLM 压缩时转变为独立且全新的研究领域。

*架构剪枝。* **LLM-Pruner** **Ma**等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib41)）通过利用单步梯度来估计预训练 LLM 的重要部分，使用了泰勒级数展开。**LoRAPrune** **Zhang**等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib63)）通过使用**LoRA** **Hu**等人（[2021](https://arxiv.org/html/2402.01799v2#bib.bib21)）权重的梯度，超越了**LLM-Pruner**，提供了计算效率。**LoRAShear** **Chen**等人（[2023a](https://arxiv.org/html/2402.01799v2#bib.bib7)）识别了 LLM 中的依赖关系，将可训练变量分组，并通过剪枝和细调实现了压缩。**Sheared LLaMA** **Xia**等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib60)）引入了针对性的结构化剪枝和动态批量加载，以进行端到端组件移除。**FLaP** **An**等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib2)）是一种无细调的结构化剪枝方法，使用基于波动的指标来确定各种权重列的重要性评分。

无结构剪枝方法，如**SparseGPT Frantar**和**Alistarh**（[2023](https://arxiv.org/html/2402.01799v2#bib.bib17)），采用了一次性技术，无需细调。**WANDA** **Sun**等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib50)）基于权重值和激活输入的乘积进行剪枝，消除了细调的需求。另一项最近的研究建议融合**OBS** **Hassibi**等人（[1993](https://arxiv.org/html/2402.01799v2#bib.bib19)）和**OBD** **LeCun**等人（[1989](https://arxiv.org/html/2402.01799v2#bib.bib33)）的权重选择标准，并基于从 Hessian 矩阵中得出的敏感性确定层稀疏性**S.**等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib44)）。虽然上述结构化和非结构化方法表现出一定的前景，但观察到的在实现的压缩水平上的性能下降仍然相对较高。进一步的努力在于开发能够导致高效 LLM 的剪枝方法。

*量化.* 这一类方法在压缩 LLMs 方面相对较为成功。LLM.int8() Dettmers 等人（[2022](https://arxiv.org/html/2402.01799v2#bib.bib13)）使得将高位 LLM 权重转换为 8 位成为可能，而不会在训练后性能下降。他们提出了一种两阶段量化方案，包括按向量量化和混合精度分解处理离群值。SmoothQuant Xiao 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib61)），一种无训练的 PTQ 方法，将 LLMs 的权重和激活都压缩至 8 位。QLoRA Dettmers 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib14)）引入了 4 位 NormalFloat（NF4）和双重量化，以节省内存而不损失模型性能。OmniQuant Shao 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib47)）引入了可学习权重裁剪（LWC）和可学习等效变换（LET）。LWC 通过优化裁剪阈值防止权重达到极端值，而 LET 通过量化权重而不是激活来处理激活离群值。SqueezeLLM Kim 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib29)）通过使用基于敏感度的非均匀量化方案实现了高达 3 位的压缩，其中二阶信息用于找到最佳位精度。GPTQ Frantar 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib18)）利用二阶信息将最多达到 1750 亿参数的模型压缩到每个权重仅 3 位，并且精度损失最小，将先前提出的 8 位方法推向了更小的尺寸。Lin 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib38)）观察到，保留 1%的关键权重可以帮助减少量化性能的退化。他们提出了激活感知权重量化（AWQ），该方法找到最佳的通道级缩放，通常在通用语言建模和领域特定任务中超越了现有技术。ZeroQuant-FP Wu 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib59)）专注于浮点量化，发现 FP8 在激活方面优于 INT8，而 FP4 在权重方面与 INT4 相当。他们还将低秩补偿纳入了他们的方法中以进行增强。EXL2¹¹1https://github.com/turboderp/exllamav2 提出了一种混合精度量化算法，其中计算每层的不同精度类型，同时测量量化误差。他们的算法在测量过程中保存所有尝试和相关错误率，并且在给定目标精度的情况下，通过选择每层模块的目标精度来量化模型，选择最低错误率的目标精度。GGUF/GGML²²2https://github.com/ggerganov/ggml 提出了一组混合量化方法，以实现 K-Quant，即大多数为 K 量化输出。例如，4 位 K-Quant 对部分 Attention 和 MLP 层使用 6 位，对其他层使用通常的 4 位。

LLM-QAT 刘等人 ([2023](https://arxiv.org/html/2402.01799v2#bib.bib40)) 提出了一个无数据蒸馏方法，他们查询了一个预训练模型以生成数据，这些数据用于训练一个量化的学生模型，并采用了蒸馏损失。除了权重和激活之外，通过对 KV-cache 的量化，他们可以将 7B、13B 和 30M LLaMA 量化到 4 位。BitNet 王等人 ([2023a](https://arxiv.org/html/2402.01799v2#bib.bib57)) 介绍了一种 1 位 LLM 变换器架构。它主要用 BitLinear 替代了 PyTorch 中的标准 nn.Linear，以训练 1 位权重。随着模型大小的增加，它在综合性能上优于使用 FP16 训练的对应模型。陶等人 ([2022](https://arxiv.org/html/2402.01799v2#bib.bib53)) 提出了基于 token 的对比蒸馏，并使用动态缩放使量化器能够适应不同模块。

*知识蒸馏。* 在知识蒸馏方法中，既有白盒方法也有黑盒方法被用于压缩大型开源语言模型。通用 KD Agarwal 等人 ([2023](https://arxiv.org/html/2402.01799v2#bib.bib1)) 不仅依赖于固定的输出序列，而是通过利用教师对这些序列的反馈来训练学生模型生成的输出序列。TED 梁等人 ([2023](https://arxiv.org/html/2402.01799v2#bib.bib37)) 采用了双阶段训练过程。在第一阶段，任务特定损失训练学生和教师模型中的过滤器。在第二阶段，学生及其过滤器经过任务感知的逐层蒸馏损失以及学生-教师和任务特定损失的训练。在另一个工作中 Jha 等人 ([2023](https://arxiv.org/html/2402.01799v2#bib.bib24))，学生模型用教师模型的子集层进行初始化，并在与教师相同的语料库和目标上进行训练。这有助于在不使用任何蒸馏损失的情况下实现任务无关的压缩。

其他蒸馏方法包括黑箱技术，例如 Lion Jiang 等人（[2023b](https://arxiv.org/html/2402.01799v2#bib.bib26)）的方法，其中学生网络通过一个由模仿、鉴别和生成阶段组成的三阶段对抗循环进行训练。在鉴别阶段，使用专有的 LLM 来找出难度较大的指令，即学生的输出与教师的输出显著不同的指令。作为最后一步，专有的 LLM 生成更多类似于难度指令的样本，学生在这些样本上进行训练，从而完成循环。DISCO Chen 等人（[2023b](https://arxiv.org/html/2402.01799v2#bib.bib8)）是一种反事实知识方法，其中专有的 LLM 被给定一个提示，并生成反事实增强。然后，特定任务的教师模型过滤这些增强，学生模型在这些增强上进行训练。SCOTT Wang 等人（[2023b](https://arxiv.org/html/2402.01799v2#bib.bib58)）使用对比解码从教师那里生成理由，并与通常的问题-答案对一起训练学生模型。

*低秩近似。* TensorGPT Xu 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib62)）通过张量-训练分解压缩了 LLM 的嵌入层，并将其存储在一个减少的矩阵积状态中，这可以以分布式方式计算。LoSparse Li 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib36)）将 LLM 中的权重矩阵近似为稀疏矩阵和另一个低秩近似矩阵的和。低秩矩阵捕捉了神经元之间的表达特征，因为它们涉及进行奇异值分解，而剩余的特征则由稀疏矩阵捕捉。Kaushal 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib27)）表明，将 LLM 中的矩阵简单分解为两个稀疏低秩矩阵的乘积，可以在略微妥协困惑度的情况下显著压缩和加速。

总体而言，使用低秩近似压缩 LLM 的研究方向虽然较新，但展现出提高推理效率的潜力。最近的两项工作表明，低秩近似通常可以通过在权重空间 Sharma 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib48)）和/或潜在特征空间 Chavan 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib6)）的逐层秩降低来改善推理能力并进行压缩。这些方法由于其逐层处理涉及的矩阵，因此在压缩过程中所需的计算资源最小。然而，需要注意的是，使用这些技术所实现的无损压缩水平仍然有限，从实际角度来看需要进一步改进。

*系统级方法。* 在这里，我们重点介绍那些改进 LLM 的补充基础设施和运行时架构的方法。

*分页注意力 Kwon 等人 ([2023](https://arxiv.org/html/2402.01799v2#bib.bib30)) -* 受到操作系统中经典虚拟内存和分页技术的启发，它允许将连续的键和值存储在非连续的内存中。

*张量并行 ism -* 涉及将张量划分为分布在不同 GPU 上的片段，并行处理每个片段，最后在步骤末尾同步结果。

*流水线并行 ism -* 允许在层级上将模型垂直拆分到多个 GPU 上，每个 GPU 处理一个或多个层，从而实现管道中不同阶段的并行处理。

*CPU/GPU 卸载 Song 等人 ([2023](https://arxiv.org/html/2402.01799v2#bib.bib49))-* 涉及将特定权重层转移到 GPU 设备进行矩阵乘法，随后将计算结果传回辅助设备（RAM），从而优化并行处理能力，同时允许辅助设备处理剩余的内存密集型计算。

*闪存注意力(/v2) Dao 等人 ([2022](https://arxiv.org/html/2402.01799v2#bib.bib10)); Dao ([2023](https://arxiv.org/html/2402.01799v2#bib.bib11)) -* 通过使用增量的 softmax 缩减和输入块切割来优化注意力计算，避免了对整个输入的访问需求，并通过存储前向传递中的 softmax 归一化因子来加速反向传递，消除了从高带宽内存 (HBM) 读取大型注意力矩阵的需求。在 FlashAttention 的基础上，FlashAttention-2 最小化非矩阵乘法 FLOPs，优化在线 softmax 技术，引入序列长度上的并行性，并改进了每个线程块内 warps 之间的工作负载划分，以减少同步，从而在现代 GPU 上实现优化性能。

*融合操作 -* 涉及整合多个计算任务，如合并现有内核或创建新内核，以减少与多个内核 API 调用相关的开销。

*猜测性解码 Leviathan 等人 ([2023](https://arxiv.org/html/2402.01799v2#bib.bib34)) -* 高效地从选择的小模型生成多个未来的 tokens，并使用更大的模型并行验证它们，从而实现每步同时解码多个 tokens。

在这一类别中值得注意的实现包括 vLLM³³3https://github.com/vllm-project/vllmKwon 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib30)）、Llama.cpp⁴⁴4https://github.com/ggerganov/llama.cpp、ExLlama(/v2)、TensorRT-LLM⁵⁵5https://github.com/NVIDIA/TensorRT-LLM、MLC-LLM⁶⁶6https://github.com/mlc-ai/mlc-llm、PowerInfer⁷⁷7https://github.com/SJTU-IPADS/PowerInfer Song 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib49)）等。vLLM 通过一个 KV-Cache 管理器实现分页注意力，该管理器分离了逻辑 KV 块和物理 KV 块，从而实现了 KV 缓存的动态增长。ExLlama(/v2) 实现了融合内核，以最小化在处理不连续块时的启动开销和 API 调用开销。Llama.cpp 是 LLaMA 架构的低级 C/C++ 实现，支持多种 BLAS 后端以实现快速处理。它基于 GGUF 量化方案，在 CPU 和 GPU 上进行卸载。MLC-LLM 专注于编译器加速和跨平台原生部署的运行时优化。它将模型执行逻辑封装在一个容器 - 中间表示模块（IRModule）中，该模块捕获计算的层次结构以进行优化和代码生成。它采用分页注意力、融合操作符和为多种硬件平台自动生成优化内核代码。TensorRT-LLM 实现了掩码多头注意力，并对 QKV 元素进行动态预处理。它支持分页注意力、INT8/FP8 缓存、在飞行中的批处理和张量/管道并行性，以提高速度。由于融合的在飞行中批处理与操作融合，额外的改进得以实现。PowerInfer 采用 GPU-CPU 混合方法，通过将一致激活的热神经元预加载到 GPU 上以实现快速访问，在 CPU 上计算可变的冷神经元，并集成自适应预测器和神经元感知稀疏操作符以优化效率。

总体而言，这些方法与模型压缩方法相辅相成，提高了大型语言模型的运行时效率。这些引擎展示了优化软件架构和基础设施以补充模型压缩的可行性和好处。

## 3 实验分析

如上所述，存在多种模型压缩方法，且尚无明确的共识来确定在何时使用哪种方法或哪种方法优于其他方法。因此，我们在此提供对不同 LLM 压缩方法的实验分析，并提供重要的见解。对于所有实验，我们提供了实际的推理指标，包括模型权重内存（WM）、运行时内存消耗（RM）、推理令牌速率和在 Nvidia A100 40GB GPU 上计算的 WikiText2 困惑度。

表 1：通过以下结构化剪枝方法获得的各种压缩变体 LLaMA-7B 模型的性能度量：Wanda-SP、LLM-pruner 和 FLaP。这里，$*$ 指的是经过微调的 LLM-pruner 变体。

| 方法 | 稀疏度 | RM (GB) | WM (GB) | Tokens/s | 困惑度 |
| --- | --- | --- | --- | --- | --- |
| 基线 | - | 26.16 | 12.55 | 30.90 | 12.62 |
| --- | --- | --- | --- | --- | --- |
| Wanda-SP | 20% | - | - | - | 22.12 |
|  | 50% | - | - | - | 366.43 |
| LLM-Pruner | 20% | 10.38 | 10.09 | 32.57 | 19.77 |
|  | 50% | 6.54 | 6.23 | 40.95 | 112.44 |
| LLM-Pruner* | 20% | 10.38 | 10.09 | 32.57 | 17.37 |
|  | 50% | 6.54 | 6.23 | 40.95 | 38.12 |
| FLaP | 20% | 9.72 | 9.44 | 33.90 | 14.62 |
|  | 50% | 6.26 | 6.07 | 42.88 | 31.80 |

*LLaMA-7B 的剪枝。* 在本分析中，我们考察了使用三种最近的大型语言模型（LLM）剪枝方法对 LLaMA-7B 模型的结构化剪枝。表 [1](https://arxiv.org/html/2402.01799v2#S3.T1 "表 1 ‣ 3 实验分析 ‣ 更快更轻的 LLM：当前挑战及未来方向") 展示了这些方法在 20% 和 50% 稀疏度下的性能得分。值得注意的是，所有压缩方法在较低稀疏度水平下在困惑度方面表现出有效的性能。Wanda-SP 表示调整为结构化剪枝的 Wanda，如 An 等人所报告（[2023](https://arxiv.org/html/2402.01799v2#bib.bib2)）。显著的是，Wanda-SP 和 LLM-Pruner 对模型性能的影响，并且在 50% 稀疏度下结果不佳。另一方面，FLaP 和 LLM-Pruner 的微调变体在此水平表现良好。比较 RM、WM 和困惑度，这两种方法表现相似，其中 FLaP 稍微优于基于微调的 LLM-Pruner。值得注意的是，除了优越的性能，FLaP 还不需要训练，这使其成为 LLM 剪枝的首选。

表 2：不同量化方法在压缩 LLaMA2-7B 上的性能比较。这里，WM 和 RM 分别指权重内存和运行内存消耗。

| 方法 | 推理引擎 | WM (GB) | RM (GB) | Tokens/s | 困惑度 |
| --- | --- | --- | --- | --- | --- |
| Baseline FP16 | PyTorch | 12.55 | 26.16 | 30.90 | 5.85 |
| GPTQ 2bit | PyTorch | 2.11 | 2.98 | 20.91 | NaN |
| GPTQ 3bit | PyTorch | 2.87 | 3.86 | 21.24 | 7.36 |
| GPTQ 4bit | PyTorch | 3.63 | 4.65 | 21.63 | 6.08 |
| GPTQ 8bit | PyTorch | 6.67 | 7.62 | 21.36 | 5.86 |
| AWQ 4bit GEMM | PyTorch | 3.68 | 4.64 | 28.51 | 6.02 |
| AWQ 4bit GEMV | PyTorch | 3.68 | 4.64 | 31.81 | 6.02 |
| QLoRA (NF4) | PyTorch | 3.56 | 4.84 | 19.70 | 6.02 |
| LLM.int8() | PyTorch | 6.58 | 7.71 | 5.24 | 5.89 |
| K-Quants 4bit | Llama.cpp | 3.80 | 7.38 | 104.45 | 5.96 |
| OmniQuant 3bit | MLC-LLM | 3.20 | 5.10 | 83.4 | 6.65 |
| OmniQuant 4bit | MLC-LLM | 3.80 | 5.70 | 134.2 | 5.97 |

*量化 LLaMA2-7B。* 表[2](https://arxiv.org/html/2402.01799v2#S3.T2 "表 2 ‣ 3 实验分析 ‣ 更快更轻的 LLMs：当前挑战与未来方向的调研")展示了不同量化方法在提高 LLM 推理效果方面的有效性。对于每种量化方法，我们默认使用 Pytorch 作为推理引擎，当 Pytorch 不支持时使用专有引擎。可以看到，所有模型的困惑度大多保持不变，仅有微小的降级。正如预期的那样，较低的精度导致较低的工作和运行内存消耗。重要的是，我们看到在 4 位精度下，OmniQuant 能够保持最佳性能。然而，GPTQ 和 AWQ 在不同引擎上的支持范围更广。另一个有趣的观察是，尽管低于 4 位的量化导致模型性能下降，但得到的模型仍优于在相似压缩水平下的剪枝模型。

表 3：使用各种推理引擎、不同预测量化以及不同硬件对压缩 LLaMA2-7B 变体的性能比较。在这里，WM 和 RM 分别表示权重内存和运行内存消耗。

| 方法 | 硬件支持 | 量化类型 | WM (GB) | RM (GB) | Tokens/sec | 困惑度 |
| --- | --- | --- | --- | --- | --- | --- |
| Llama.cpp | NVIDIA GPU | GGUF K-Quant 2bit | 2.36 | 3.69 | 102.15 | 6.96 |
|  | AMD GPU | GGUF 4bit | 3.56 | 4.88 | 128.97 | 5.96 |
|  | Apple Silicon | GGUF AWQ 4bit | 3.56 | 4.88 | 129.25 | 5.91 |
|  | CPU | GGUF K-Quant 4bit | 3.59 | 4.90 | 109.72 | 5.87 |
|  |  | GGUF 8bit | 6.67 | 7.78 | 93.39 | 5.79 |
|  |  | GGUF FP16 | 12.55 | 13.22 | 66.81 | 5.79 |
| ExLlama | NVIDIA GPU | GPTQ 4bit | 3.63 | 5.35 | 77.10 | 6.08 |
|  | AMD GPU |  |  |  |  |  |
| ExLlamav2 | NVIDIA GPU | EXL2 2bit | 2.01 | 5.21 | 153.75 | 20.21 |
|  | AMD GPU | EXL2 4bit | 3.36 | 6.61 | 131.68 | 6.12 |
|  |  | GPTQ 4bit | 3.63 | 6.93 | 151.30 | 6.03 |
|  |  | EXL2 8bit | 6.37 | 9.47 | 115.81 | 5.76 |
|  |  | FP16 | 12.55 | 15.09 | 67.70 | 5.73 |
| vLLM | NVIDIA GPU | AWQ GEMM 4bit | 3.62 | 34.55 | 114.43 | 6.02 |
|  | AMD GPU | GPTQ 4bit | 3.63 | 36.51 | 172.88 | 6.08 |
|  |  | FP16 | 12.55 | 35.92 | 79.74 | 5.85 |
| TensorRT-LLM | NVIDIA GPU | AWQ GEMM 4bit | 3.42 | 5.69 | 194.86 | 6.02 |
|  |  | GPTQ 4bit | 3.60 | 5.88 | 202.16 | 6.08 |
|  |  | INT8 | 6.53 | 8.55 | 143.57 | 5.89 |
|  |  | FP16 | 12.55 | 14.61 | 83.43 | 5.85 |
| TGI | AMD GPU | AWQ GEMV 4bit | 3.62 | 36.67 | 106.84 | 6.02 |
|  | NVIDIA GPU | GPTQ 4bit | 3.69 | 37.85 | 163.22 | 6.08 |
|  | Intel GPU | FP4 | 12.55 | 37.21 | 36.91 | 6.15 |
|  | AWS Inferentia2 | NF4 | 12.55 | 37.21 | 36.32 | 6.02 |
|  |  | FP16 | 12.55 | 38.03 | 74.19 | 5.85 |
| MLC-LLM | NVIDIA GPU | OmniQuant 3bit | 3.2 | 5.1 | 83.4 | 6.65 |
|  | AMD GPU, | OmniQuant 4bit | 3.8 | 5.7 | 134.2 | 5.97 |
|  | CPU, WebGPU, | AWQ GEMM 4bit | 3.62 | 6.50 | 23.62 | 6.02 |
|  | Apple Silicon, | Q4F16 | 3.53 | 6.50 | 189.07 | - |
|  | Intel GPU, | Q3F16 | 2.84 | 5.98 | 185.47 | - |
|  | WASM, Adreno Mali | FP16 | 12.55 | 15.38 | 87.37 | 5.85 |

*针对 LLaMA2-7B 的系统级优化。* 我们还考虑了系统级优化方法，并通过采用现有文献中提出的各种推理引擎来提高大模型推理性能。相关结果见表 [3](https://arxiv.org/html/2402.01799v2#S3.T3 "Table 3 ‣ 3 Experimental Analysis ‣ Faster and Lighter LLMs: A Survey on Current Challenges and Way Forward")。可以看出，不同的方法在不同的性能指标上各有优势。TensorRT-LLM 在所有指标上都表现出色，尤其是在 NVIDIA GPU 上。它在 GPTQ 4-bit 量化下提供了最佳的 token 速度，但高效的 4-bit 支持仅适用于新的硬件⁸⁸8Ampere 及更新系列的 GPU 支持 4bit 运行。GPTQ 在相同精度下通常比 AWQ 更快，但困惑度略差。此外，MLC-LLM 的表现相比 TensorRT-LLM 略低，但其对多种硬件的兼容性使其在特定场景下成为一个有利的选择。

## 4 挑战与前景

*大规模剪枝/蒸馏计算密集。* 架构剪枝和知识蒸馏策略因压缩深度学习模型而广受欢迎。然而，这些技术需要多个微调步骤，其计算需求可与初始训练步骤的强度相当或甚至超越。在大模型的背景下，这使得这些技术变得不切实际，因为它们本身已具备巨大的计算需求。尽管有一些努力试图解决这个挑战，但即使是微小的压缩收益也会导致显著的准确性下降。可能的解决方法包括：

+   •

    重新审视无训练剪枝方法，以探索其在大模型中的潜力。例如，知识保留剪枝关注于减少网络中不必要的知识上下文而不是消除权重，这种方法可以改进并适应大模型。由于这些方法大多不需要训练，它们可能在仅增加少量计算预算的情况下提供高效的大模型。

+   •

    探索大模型的逐层剪枝。逐层剪枝的直接实现需要定义局部损失函数以回归损失，并在确保局部输出得以重现的同时压缩子网络。然而，在这种方法中，即使是早期层的小错误也可能会传播到后期层，导致压缩网络性能不佳。

+   •

    局部蒸馏的 LLMs。克服蒸馏问题的一个潜在解决方案是开发局部蒸馏方法。此方法不是将整个教师 LLM 信息压缩到一个更小的学生模型中，而是通过在较小规模的学生子网络中学习教师网络的局部部分。然后可以制定策略，将这些子网络合并成一个完全压缩的学生 LLM。这种方法作为解决 LLM 蒸馏相关计算挑战的潜在解决方案具有希望。

+   •

    培养较小的 LLMs 以达到期望的性能。压缩大型语言模型（LLMs）的主要障碍在于微调过程中的计算挑战，这与模型的巨大规模有关。一个替代性且雄心勃勃的研究方向是利用明确定义的神经网络生长策略，将较小的语言模型（SLMs）培养成 LLMs。这种方法避免了训练全规模的 LLM，最大计算负担由通过 SLMS 生长获得的最终压缩 LLM 确定。

+   •

    使用 PEFT 方法进行微调以提高剪枝效率。为应对剪枝过程中全规模微调的挑战，一种替代方法是采用 PEFT 方法。与传统方法不同，PEFT 不需要更新模型权重；仅更新附加的掩码和 PEFT 参数 Zhang 等人（[2023](https://arxiv.org/html/2402.01799v2#bib.bib63)）。这显著减少了微调过程的计算强度。然而，PEFT 方法目前在实现 LLMs 的大规模压缩方面仍存在局限性，需要进一步研究以开发专门用于压缩 LLMs 的 PEFT 方法。

*即使是实时量化和反量化也会使推理变慢。* 使用如 FP4 等低精度浮点格式在推理过程中会面临内存效率和计算速度的双重挑战。尽管现代硬件通常支持 FP16 和 INT8 等格式，这些格式可以显著减少内存使用，但较低精度的转换通常需要量化（Quant）和反量化（Dequant）操作。这些操作可能会引入计算开销，使推理过程相比使用 FP16 等高精度格式变慢。因此，尽管采用低精度格式可以提高内存效率，但会对推理速度产生不利影响，需要在两者之间找到适当的平衡。一个潜在的解决方案是开发简化的量化-反量化操作，以缓解推理速度的开销。另一种策略是根据使用的硬件规格来调整精度格式的选择。同时，硬件方面的进步也是必要的，需要对更广泛的流行硬件支持低精度格式。

*层次低秩近似中的秩选择很困难。* 虽然低秩近似在 LLM 压缩方面展示了巨大的潜力，但这种方法伴随着一系列挑战，特别是在决定控制秩减少过程的超参数时。对于不同模型普遍适用的低秩近似策略尚未达成明确共识。此外，解决系统级分解系统的计算不可行性增加了复杂性，使得在保持性能的同时实现模型大小的最佳减少变得具有挑战性。

需要认识到，确定在各层之间保留的最佳秩并不是一个容易通过超参数搜索问题来解决的任务。许多此类方法在大规模语言模型（LLMs）的背景下计算成本高昂。必须探索和制定有效的策略来寻找低秩近似时合适的秩。

*现有的评估指标可能不够适用。* 在压缩 LLM 的同时保持其处理大量上下文信息的能力是一项挑战，需要开发合适的评估指标来解决这个问题。另一个因素是保真度的丧失。激进的压缩可能会导致模型保真度的显著丧失，影响语言模型生成准确且上下文相关的输出的能力。 LLM 的几个特征需要在其压缩变体中被捕捉，只有通过选择合适的指标才能识别这些特征。

*Python - 作为一种解释型语言导致执行速度较慢。* 尽管 Python 是一种多功能且广泛使用的编程语言，但它本质上是解释型的，这可能会导致性能瓶颈，尤其是在深度学习等计算密集型任务中。CPython，即默认的 Python 解释器中的全局解释器锁（GIL），进一步限制了多线程的并发执行，限制了该语言充分利用多核处理器的能力。这突显了寻找替代解决方案以提高深度学习工作流程速度的必要性。

随着优化库和框架的发展，如 TensorFlow 和 PyTorch，它们整合了用 C++ 或 CUDA 等低级语言实现的高性能内核，一些问题已经得到解决。然而，Python 在许多方面仍然限制了模型的性能。一个说明性例子是 LLama.cpp，其中转向 C++ 实现的 LLaMA-7B 显著提高了速度。这一转变 exemplifies 了选择优化性能的语言在深度学习模型中的影响。此外，基于 Rust 的模型因其优越的速度而引起了关注。Rust 强调内存安全和性能，在加速计算方面表现出色，尤其是在速度至关重要的场景中。因此，为了优化推理速度，转向 C++、Rust 或其他类似语言可能是未来的发展方向。

*伦理和偏见考虑未必得到维护。* LLM 初始是在广泛的数据集上进行训练的，确保模型在统计上不会对任何特定案例产生偏见。然而，在模型压缩过程中，通常会使用特定的数据集。由于 LLM 可能会失去与目标数据集无关的一些通用特征，可能会通过标准评估实践引入未被注意到的偏见。因此，需要开发创新的评估策略，以确保在压缩的 LLM 中将伦理问题和偏见最小化。

## 5 结论

总结来说，我们的调查广泛探讨了 LLM 压缩，涵盖了模型层面和系统层面的效率提升。我们讨论了各种压缩方法，并提供了在 LLaMA(/2)-7B 上进行实验的实际见解，为优化 LLM 提供了有价值的信息。对调查和实验结果的分析突出了在提升 LLM 推理中的现有瓶颈，表明了实现效率所需的进一步发展。我们希望这项调查能成为推动该领域进步和实现高效 LLM 推理目标的垫脚石。

## 参考文献

+   Agarwal 等人 [2023] R. Agarwal, N. Vieillard, Y. Zhou, P. Stanczyk, S. Ramos, M. Geist, 和 O. Bachem. 自回归语言模型的广义知识蒸馏。arXiv, 2023。

+   An 等人 [2023] Y. An, X. Zhao, T. Yu, M. Tang, 和 J. Wang. 基于波动的适应性结构剪枝用于大型语言模型。arXiv, 2023。

+   Banner 等人 [2019] R. Banner, Y. Nahshan, E. Hoffer, 和 D. Soudry. 用于快速部署的卷积网络的训练后 4 位量化。arXiv, 2019。

+   Brown 等人 [2020] T. Brown, B. Mann, N. Ryder, M. Subbiah, J. D Kaplan, P. Dhariwal, A. Neelakantan, P. Shyam, G. Sastry, A. Askell, 等人. 语言模型是少样本学习者。NeurIPS, 33:1877–1901, 2020。

+   Chavan 等人 [2022] A Chavan, Z Shen, Z Liu, Z Liu, K T Cheng, 和 E P Xing. 视觉变换器瘦身：在连续优化空间中的多维搜索。在 CVPR，页 4931–4941，2022。

+   Chavan 等人 [2023] A. Chavan, N. Lele, 和 D. Gupta. 重新思考压缩：大型语言模型中潜在特征的降阶建模。arXiv，2023。

+   Chen 等人 [2023a] T. Chen, T. Ding, B. Yadav, I. Zharkov, 和 L. Liang. Lorashear: 高效的大型语言模型结构化剪枝与知识恢复。arXiv，2023。

+   Chen 等人 [2023b] Z. Chen, Q. Gao, A. Bosselut, A. Sabharwal, 和 K. Richardson. Disco: 使用大型语言模型提炼反事实。arXiv，2023。

+   Choukroun 等人 [2019] Y. Choukroun, E. Kravchik, F. Yang, 和 P. Kisilev. 神经网络的低位量化以提高推理效率。arXiv，2019。

+   Dao 等人 [2022] T. Dao, D. Fu, S. Ermon, A. Rudra, 和 Christopher Ré. Flashattention: 快速且内存高效的精确注意力机制，具备 IO 感知。NeurIPS，35:16344–16359，2022。

+   Dao [2023] Tri Dao. Flashattention-2: 更快的注意力机制，具有更好的并行性和工作划分。arXiv，2023。

+   Denton 等人 [2014] E. Denton, W. Zaremba, J. Bruna, Y. LeCun, 和 R. Fergus. 利用卷积网络中的线性结构进行高效评估。arXiv，2014。

+   Dettmers 等人 [2022] T. Dettmers, M. Lewis, Y. Belkada, 和 L. Zettlemoyer. Llm.int8(): 大规模变压器的 8 位矩阵乘法。arXiv，2022。

+   Dettmers 等人 [2023] T. Dettmers, A. Pagnoni, A. Holtzman, 和 L. Zettlemoyer. Qlora: 量化大型语言模型的高效微调。arXiv，2023。

+   Esser 等人 [2019] S. K Esser, J. L McKinstry, D. Bablani, R. Appuswamy, 和 D. S Modha. 学习的步长量化。arXiv，2019。

+   Frankle 和 Carbin [2019] J. Frankle 和 M. Carbin. 彩票票据假说：寻找稀疏的可训练神经网络。arXiv，2019。

+   Frantar 和 Alistarh [2023] E. Frantar 和 D. Alistarh. Sparsegpt: 大型语言模型可以通过一次性精确剪枝。arXiv，2023。

+   Frantar 等人 [2023] E. Frantar, S. Ashkboos, T. Hoefler, 和 D. Alistarh. Gptq: 生成预训练变压器的精确后训练量化。arXiv，2023。

+   Hassibi 等人 [1993] B. Hassibi, D. G Stork, 和 G. J Wolff. 最优脑外科医生与通用网络剪枝。ICNN 会议论文，页 293–299。IEEE，1993。

+   Hinton 等人 [2015] G. Hinton, O. Vinyals, 和 J. Dean. 提炼神经网络中的知识。arXiv，2015。

+   Hu 等人 [2021] E. J Hu, P. Wallis, Z. Allen-Zhu, Y. Li, S. Wang, L. Wang, W. Chen, 等人. Lora: 大型语言模型的低秩适应。在 ICLR，2021。

+   Jaderberg 等人 [2014] M. Jaderberg, A. Vedaldi, 和 A. Zisserman. 通过低秩扩展加速卷积神经网络。arXiv，2014。

+   Janowsky [1989] S. A. Janowsky. 神经网络中的剪枝与修剪。Phys. Rev. A，39:6600–6603，1989。

+   Jha et al. [2023] A. H. Jha, T. S., E. P. Walsh, D. Groeneveld, E. Strubell, 和 I. Beltagy. 如何训练你的（压缩版）大型语言模型. arXiv, 2023.

+   Jiang et al. [2023a] T. Jiang, D. Wang, F. Zhuang, R. Xie, 和 F. Xia. 在不微调的情况下剪枝预训练语言模型. arXiv, 2023.

+   Jiang et al. [2023b] Y. Jiang, C. Chan, M. Chen, 和 W. Wang. Lion: 对专有大型语言模型的对抗蒸馏. arXiv, 2023.

+   Kaushal et al. [2023] A. Kaushal, T. Vaidhya, 和 I. Rish. Lord: 单语代码 LLMs 的低秩分解用于单次压缩. arXiv, 2023.

+   Kenton and Toutanova [2019] Jacob Devlin Ming-Wei Chang Kenton 和 L. Kristina Toutanova. Bert: 深度双向变换器的预训练用于语言理解. 在 NAACL-HLT 会议论文集, 第 4171–4186 页, 2019.

+   Kim et al. [2023] S. Kim, C. Hooper, A. Gholami, Z. Dong, X. Li, S. Shen, M. W. Mahoney, 和 K. Keutzer. Squeezellm: 密集与稀疏量化. arXiv, 2023.

+   Kwon et al. [2023] W. Kwon, Z. Li, S. Zhuang, Y. Sheng, L. Zheng, C. H. Yu, J. Gonzalez, H. Zhang, 和 I. Stoica. 通过分页注意力的高效大规模语言模型内存管理. 在第 29 届操作系统原则研讨会论文集, 第 611–626 页, 2023.

+   Lagunas et al. [2021] F. Lagunas, E. Charlaix, V. Sanh, 和 A. M. Rush. 用于更快变换器的块剪枝. arXiv, 2021.

+   Lebedev et al. [2015] V. Lebedev, Y. Ganin, M. Rakhuba, I. Oseledets, 和 V. Lempitsky. 通过精细调优的 CP 分解加速卷积神经网络. arXiv, 2015.

+   LeCun et al. [1989] Y. LeCun, J. Denker, 和 S. Solla. 最优大脑损伤. NeurIPS, 2, 1989.

+   Leviathan et al. [2023] Y. Leviathan, M. Kalman, 和 Y. Matias. 通过推测解码实现变换器的快速推理. 在 ICML, 第 19274–19286 页. PMLR, 2023.

+   Li et al. [2016] H. Li, A. Kadav, I. Durdanovic, H. Samet, 和 H. P. Graf. 剪枝滤波器以提高卷积网络的效率. arXiv, 2016.

+   Li et al. [2023] Y. Li, Y. Yu, Q. Zhang, C. Liang, P. He, W. Chen, 和 T. Zhao. Losparse: 基于低秩和稀疏近似的结构化大型语言模型压缩. arXiv, 2023.

+   Liang et al. [2023] C. Liang, S. Zuo, Q. Zhang, P. He, W. Chen, 和 T. Zhao. 少即是多: 任务感知的逐层蒸馏用于语言模型压缩. arXiv, 2023.

+   Lin et al. [2023] J. Lin, J. Tang, H. Tang, S. Yang, X. Dang, C. Gan, 和 S. Han. Awq: 激活感知的权重量化用于 LLM 压缩和加速. arXiv, 2023.

+   Liu et al. [2017] Z. Liu, J. Li, Z. Shen, G. Huang, S. Yan, 和 C. Zhang. 通过网络瘦身学习高效卷积网络. arXiv, 2017.

+   Liu et al. [2023] Z. Liu, B. Oguz, C. Zhao, E. Chang, P. Stock, Y. Mehdad, Y. Shi, R. Krishnamoorthi, 和 V. Chandra. Llm-qat: 无数据量化感知训练用于大型语言模型. arXiv, 2023.

+   Ma et al. [2023] X. Ma, G. Fang, 和 X. Wang. Llm-pruner: 大型语言模型的结构性剪枝. arXiv, 2023.

+   Molchanov 等人 [2016] P. Molchanov, S. Tyree, T. Karras, T. Aila 和 J. Kautz. 为资源高效推理而剪枝卷积神经网络。ICLR, 2016.

+   Ni 等人 [2020] R. Ni, H. M. Chu, O. Castañeda, P. Y. Chiang, C. Studer 和 T. Goldstein. Wrapnet: 超低分辨率算术的神经网络推理。arXiv, 2020.

+   S. 等人 [2023] Hang S., Bei L. 和 Yanmin Q. 一次性敏感性感知混合稀疏性剪枝的大型语言模型。arXiv, 2023.

+   Sainath 等人 [2013] T. N. Sainath, B. Kingsbury, V. Sindhwani, E. Arisoy 和 B. Ramabhadran. 高维输出目标的深度神经网络训练的低秩矩阵分解。ICASSP, 页 6655–6659, 2013.

+   Sanh 等人 [2020] V. Sanh, T. Wolf 和 A. M. Rush. Movement pruning: Adaptive sparsity by fine-tuning. arXiv, 2020.

+   Shao 等人 [2023] W. Shao, M. Chen, Z. Zhang, P. Xu, L. Zhao, Z. Li, K. Zhang, P. Gao, Y. Qiao 和 P. Luo. Omniquant: 大型语言模型的全方向标定量化。arXiv, 2023.

+   Sharma 等人 [2023] P. Sharma, J. T. Ash 和 D. Misra. 真相在其中：通过层选择性秩约减改善语言模型的推理能力。arXiv, 2023.

+   Song 等人 [2023] Y. Song, Z. Mi, H. Xie 和 H. Chen. Powerinfer: 使用消费者级 GPU 进行快速的大型语言模型服务。arXiv, 2023.

+   Sun 等人 [2023] M. Sun, Z. Liu, A. Bair 和 J. Z. Kolter. 一种简单有效的大型语言模型剪枝方法。arXiv, 2023.

+   Tai 等人 [2016] C. Tai, T. Xiao, Y. Zhang, X. Wang 和 Weinan E. 具有低秩正则化的卷积神经网络。arXiv, 2016.

+   Tailor 等人 [2021] S. A. Tailor, J. F. Marques 和 N. D. Lane. Degree-quant: 针对图神经网络的量化感知训练。arXiv, 2021.

+   Tao 等人 [2022] C. Tao, L. Hou, W. Zhang, L. Shang, X. Jiang, Q. Liu, P. Luo 和 N. Wong. 通过量化压缩生成预训练语言模型。arXiv, 2022.

+   Tian 等人 [2022] Yo. Tian, D. Krishnan 和 P. Isola. 对比表示蒸馏。arXiv, 2022.

+   Touvron 等人 [2023a] H. Touvron, T. Lavril, G. Izacard, X. Martinet, M. A. Lachaux, T. Lacroix, B. Rozière, N. Goyal, E. Hambro, F. Azhar 等人. Llama: 开放和高效的基础语言模型。arXiv, 2023.

+   Touvron 等人 [2023b] H. Touvron, L. Martin, K. Stone, P. Albert, A. Almahairi, Y. Babaei, N. Bashlykov, S. Batra, P. Bhargava, S. Bhosale 等人. Llama 2: 开放基础和微调聊天模型。arXiv, 2023.

+   Wang 等人 [2023a] H. Wang, S. Ma, L. Dong, S. Huang, H. Wang, L. Ma, F. Yang, R. Wang, Y. Wu 和 F. Wei. Bitnet: 扩展 1 位变压器以适应大型语言模型。arXiv, 2023.

+   Wang 等人 [2023b] P. Wang, Z. Wang, Z. Li, Y. Gao, B. Yin 和 X. Ren. Scott: 自一致的思维链蒸馏。arXiv, 2023.

+   Wu 等人 [2023] X. Wu, Z. Yao 和 Y. He. Zeroquant-fp: 使用浮点格式的 LLMs 后训练 W4A8 量化的飞跃。arXiv, 2023.

+   Xia 等人 [2023] M. Xia, T. Gao, Z. Zeng 和 D. Chen。Sheared llama: 通过结构化剪枝加速语言模型预训练。arXiv，2023 年。

+   Xiao 等人 [2023] G. Xiao, J. Lin, M. Seznec, H. Wu, J. Demouth 和 S. Han。Smoothquant: 大型语言模型的准确高效的后训练量化。arXiv，2023 年。

+   Xu 等人 [2023] M. Xu, Y. Lei Xu 和 D. P. Mandic。Tensorgpt: 基于张量-训练分解的嵌入层高效压缩。arXiv，2023 年。

+   Zhang 等人 [2023] M. Zhang, H. Chen, C. Shen, Z. Yang, L. Ou, X. Yu 和 B. Zhuang。Loraprune: 剪枝与低秩参数高效微调相结合。arXiv，2023 年。

+   Zhu 等人 [2023] X. Zhu, J. Li, Y. Liu, C. Ma 和 W. Wang。关于大型语言模型的模型压缩综述。arXiv，2023 年。

生成于 2024 年 4 月 30 日星期二 20:11:48 由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
