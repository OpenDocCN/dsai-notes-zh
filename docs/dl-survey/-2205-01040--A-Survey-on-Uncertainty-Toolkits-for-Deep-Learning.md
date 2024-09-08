<!--yml

类别：未分类

日期：2024-09-06 19:46:46

-->

# [2205.01040] 深度学习中的不确定性工具包调查

> 来源：[`ar5iv.labs.arxiv.org/html/2205.01040`](https://ar5iv.labs.arxiv.org/html/2205.01040)

# 不确定性工具包调查

针对深度学习

马克西米利安·平茨

波恩大学，弗劳恩霍夫 IAIS

比尔林霍芬城堡

53757 圣奥古斯丁，德国

{maximilian.alexander.pintz}@iais.fraunhofer.de

&乔阿希姆·西金、马克西米利安·波雷奇金、马拉姆·阿基拉

弗劳恩霍夫 IAIS

比尔林霍芬城堡

53757 圣奥古斯丁，德国

{joachim.sicking,maximilian.poretschkin,maram.akila}@iais.fraunhofer.de

###### 摘要

深度学习（DL）的成功促进了统一框架的创建，例如 tensorflow 或 pytorch，同时它们的创建又反过来推动了深度学习的发展。拥有共同的构建模块有助于，例如，模型或概念的交流，并使得开发更容易复制。然而，对 DL 模型进行稳健和可靠的评估通常具有挑战性。这与其日益增加的安全相关性相矛盾，最近这一点在“可信机器学习”领域达到了顶峰。我们相信，进一步统一评估和保障方法论，特别是工具包，即小型且专门化的框架衍生物，可能会对可信度和可重复性问题产生积极影响。为此，我们提供了关于深度学习中不确定性估计（UE）工具包的首次调查，因为 UE 是评估模型可靠性的基石。我们调查了 $11$ 个工具包，针对建模和评估能力进行了深入比较，重点比较了最有前景的三个工具包，即 Pyro、Tensorflow Probability 和 Uncertainty Quantification 360。前两个工具包提供了较大的灵活性和无缝集成到各自框架中的能力，而最后一个则具有更大的方法学范围。

## 1 引言

监督深度学习（DL）推动了计算机视觉（Mahony 等，2019; Chai 等，2021）、自然语言处理（Torfi 等，2020）和语音识别（Alam 等，2020）等多个应用领域的进步，并越来越多地应用于安全关键系统，如自动驾驶汽车（Yurtsever 等，2020）或医疗诊断系统（Hafiz & Bhat，2020）。这些系统可能对环境造成危害，破坏设备或使人类面临风险（Sommerville，2010），例如，当无法识别脆弱的道路使用者（在自动驾驶情况下）或严重的疾病（在诊断系统情况下）时。值得信赖的机器学习领域（Brundage 等，2020; Chatila 等，2021; Liu 等，2021; Houben 等，2021）旨在识别和缓解这些机器学习系统的风险，以实现其负责任和安全的运行。为此，提出了一种更全面的质量观念，不仅超越任务表现，还考虑公平性、可解释性和可靠性等方面。其中的核心是识别和处理不确定性，即影响系统的因素，但往往没有或仅有较差的考虑。这些不确定性在深度学习中普遍存在，例如，来自数据（如测量噪声和错误注释）或训练过程中的变异性（如超参数、初始化和有限的训练数据）。量化这些因素对系统的影响可以有助于其安全性：例如，识别异常传感器输入的自动驾驶汽车，可能会切换到保守的行驶模式或激活冗余的安全系统。

对不确定性估计（UE）的期望适应性（Sicking 等，2022）常常受到高实现复杂性的阻碍。这种适应性可以通过开源工具包加快，该工具包通过提供易于使用的构建模块和最小工作示例形式的指导来减少这一努力。由于被社区使用和审查，工具包还可能增强 UE 组件的技术质量并推进常见实践。后者，即使用常见工具和标准，可能推动该领域的进一步进展，因为它促进了更容易的审查和重用现有工作。

鉴于此，我们首次调查了深度不确定性工具包。调查结构如下：我们首先简要概述 DL 软件和 UE（第二部分）。接下来，我们从 180 个考虑的仓库中选择了 11 个公开可用的开源深度不确定性工具包（第三部分），并提出了一套评估这些工具包的标准（第四部分）。然后，我们将这些标准应用于收集的工具包进行比较分析（第五部分），描述其优缺点。最后，我们在讨论中突出当前深度不确定性工具包的局限性和期望的未来发展（第六部分）。

## 2 相关工作

我们首先描述两种类型的深度学习（DL）软件，即在本次调查中讨论的**DL 框架**和**专业工具包**。接下来，我们概述了关于 DL 软件的调查，并在第二段中勾勒出其方法论和重点。为了为随后的 UE 工具包调查提供基础，第三段回顾了 UE 的一些基础概念，特别是关于其建模和评估的内容。一些简单的 UE 能力作为标准 DL 框架（如 tensorflow 和 pytorch）的一部分进行发布。我们在本节的最后一段概述了这些“默认”能力并勾勒了它们的局限性。

##### **DL 框架**和**专业工具包**

DL 软件涵盖了深度学习的不同方面。两种特殊类型，即**DL 框架**和**专业工具包**，在本次调查中是重点讨论的内容，并在以下内容中进行描述。

**DL 框架**提供了一组全面、可靠（经过良好测试/维护）且高度可用（模块化结构，高级接口）的基础组件，用于构建和评估深度学习系统。它们通常提供可以组合成自定义模型架构的层模块和用于模型训练的基于梯度下降的优化器。它们在设计时考虑了 DL 特定的软件需求，包括灵活的数据管道、自动微分和高效处理（GPU/多核利用，设备分配）。示例包括 tensorflow（Abadi 等，2015），pytorch（Paszke 等，2019）和 MXNet（Chen 等，2015）。

专用工具包扩展了 DL 框架的能力。它们通常在深度学习的一个子领域中提供一组常用工具。示例包括用于自然语言处理的 spaCy (Honnibal et al., 2020)，用于计算机视觉的 GluonCV (Guo et al., 2020) 以及对抗鲁棒性工具箱 (Nicolae et al., 2018)。本研究中分析的 UE 工具包属于这一类别的 DL 软件。

##### DL 软件的调查

DL 软件的调查主要集中在对 DL 框架的系统评估（Nguyen et al., 2019; Wang et al., 2019; Landset et al., 2015; Druzhkov & Kustikova, 2016; Bahrampour et al., 2015）。分析的典型标准包括提供组件的范围、GPU/多处理支持、大数据框架的集成以及一般软件标准，如效率/可扩展性、易用性和框架设计/扩展性。关于专用工具包的研究很少，例如 Zacharias et al. (2018) 关注于智能用户界面的库，或 Agarwal & Das (2020) 比较了可解释机器学习工具包在提供方法和使用案例方面的范围。我们希望通过这项关于 UE 工具包的调查扩展对可信 AI 软件的概述。

##### 不确定性估计的元素

在接下来的部分中，我们总结了不确定性估计的核心方面，以便分析本次调查。对这些方面的进一步细节请参阅附录中的方法学“深入探讨”（第 6.1 节）。

DL 系统受到几种不确定性类型的影响（Hüllermeier & Waegeman, 2021）。可以区分可减少的知识不确定性，这种不确定性源于对解决任务的完美模型缺乏知识，包括训练数据的缺乏或近似误差，以及不可减少的偶然不确定性，这包括数据生成过程中的固有随机性（例如传感器噪声或标签歧义）。

UE 方法旨在量化这些不确定性。在本调查中，我们将其按照两个独立的“轴”进行分类：它们在给定模型中的集成深度和它们所基于的方法框架。在前一个轴上，我们区分（i）内在方法，这些方法将不确定性估计直接集成到架构或训练过程中（例如，dropout 层或集成训练），（ii）后验方法，这些方法为标准深度学习模型提供概率估计，以及（iii）重新校准方法，这些方法旨在改善现有的不确定性估计（Guo et al., 2017; Kuleshov et al., 2018; Navrátil et al., 2021）。

方法论的“轴”包括以下内容。(i) 参数似然方法考虑网络直接输出分布参数而不是点估计，并通过似然优化进行训练 (Nix & Weigend, 1994; Amini et al., 2020; Sensoy et al., 2018)。 (ii) 贝叶斯神经网络 (BNN) 通过在网络参数上引入 (认识论的) 不确定性扩展了这些方法。示例包括基于变分推断的 BNN (VI-BNN, Graves (2011); Blundell et al. (2015); Rezende & Mohamed (2015))，其基于丢弃采样的变体 (Gal & Ghahramani, 2016; Kendall & Gal, 2017))，马尔可夫链蒙特卡洛采样 (MCMC, Neal et al. (2011); Welling & Teh (2011); Li et al. (2016)) 或假设密度过滤 (ADF-BNN, Hernández-Lobato & Adams (2015); Gast & Roth (2018))。相关的贝叶斯方法还有高斯过程 (GP, Rasmussen & Williams (2006)) 及其可扩展变体 (Hensman et al., 2013)，它们在函数空间中引入不确定性。(iii) 频率学派方法直接利用不同模型的组合进行不确定性估计，例如深度集成 (Lakshminarayanan et al., 2017; Wen et al., 2019; Durasov et al., 2021) 或切除法 (Giordano et al., 2019; Alaa & Van Der Schaar, 2020; Kim et al., 2020)。

已开发出多种评估技术，用于对不确定性方法进行基准测试并评估其质量。最常见的评估技术包括 (i) (适当的) 评分规则 (Gneiting & Raftery, 2007)，这些规则测量预测分布与真实值的拟合程度（例如，负对数似然 (NLL) 或 Brier 分数），(ii) 校准测试 (Guo et al., 2017; Kuleshov et al., 2018; Navrátil et al., 2021)，评估与验证数据集的一致性（例如，可靠性图，预期校准误差 (ECE)），(iii) 定性评估（例如，检查预测分布或数据集上的平均预测方差），以及 (iv) 辅助任务的性能，例如 Ovadia et al. (2019) 中的基于不确定性的分布内和分布外数据点的分离。

##### 标准深度学习框架中的不确定性估计

常见的深度学习框架原生提供了基本的不确定性估计构件。TensorFlow/Keras¹¹Keras 最初是一个独立的库，但已成为 TensorFlow 的一部分。它提供了用于模型构建、训练和评估的高级 API。MXNet 或 Pytorch²²我们在分析中考虑的不确定性工具包是基于这三个深度学习框架的。提供了原本用于正则化的 dropout 函数（Srivastava 等，2014），但也可以用于构建基于 dropout 的不确定性模型。Pytorch 展示了分布包，它使用重新参数化技巧（Kingma 等，2015）实现了兼容反向传播的概率分布。所有提到的框架都支持基本的评估技术，例如均方误差或直方图。尽管有这些实现，构建一个功能齐全的不确定性模型仍然通常需要大量的实现工作。例如，实现一个 VI-BNN 需要自定义的层模块，这些模块在网络参数上施加概率分布，并优化一个自定义目标函数。我们则专注于那些基于这些现有功能并提供更高抽象层次以减少实现工作量的工具包。

## 深度不确定性工具包的选择

我们系统性调查的第一步是编制一个深度不确定性估计的开源工具包集合，这是本节的目标。为此，我们首先描述了编制潜在代码库预选的过程。接下来，我们收集了一个代码库需要满足的基本标准，以便在本工作的范围内被视为不确定性工具包。最后，我们将这些标准应用于预选，获得了一组 $11$ 个深度不确定性工具包，这些工具包用于我们的比较分析（见第五部分）。

##### 搜索与深度学习中的不确定性估计相关的代码库

在这项调查中，我们重点关注在 `github.com` 上可用的开源代码库。我们集中在 github 上，因为它是最大的开源代码托管平台，并且据我们所知，托管了大多数公开可用的深度不确定性估计软件。我们使用 github 的公共搜索功能来查找与不确定性相关的代码库。特别地，我们利用“主题”，即用于标记代码库的特定关键字，使其他用户能够更容易地找到这些代码库。此外，用户可以为他们特别感兴趣的代码库“加星”，这是一种书签式的标记方法。我们检查了“uncertainty-quantification”、“uncertainty-estimation”这些主题，并且还搜索了关键字“uncertainty”和“probabilistic”，并将搜索限制在“machine-learning”和“deep-learning”主题的代码库中。在每种情况下，我们按收到的“星标”总数对搜索结果进行排序，并检查了结果列表中的前 $30$ 个代码库，总计 $180$ 个代码库。在这些代码库中，有深度不确定性估计库、各种配套研究论文的实现，以及一些不明确集中在深度学习上的软件，例如关于数值模型的灵敏度分析的通用库。

##### 组成不确定性工具包的标准

由于我们的工作重点是监督式深度学习中的工具包，我们进一步筛选了这 $180$ 个代码库。如果一个软件库包含至少一种以下方法，我们将其视为 *深度不确定性工具包*：

+   •

    构建和训练一个（内在地）支持 UE 的深度学习模型（内在方法），

+   •

    扩展给定的深度学习模型以包含不确定性估计（事后方法），

+   •

    改进已经存在的不确定性估计（重新校准）或

+   •

    通过指标或可视化来评估不确定性估计。

此外，我们要求工具包提供对广泛场景普遍适用的方法，特别是对不同数据集或网络架构。必须提供充分的文档，并且需要有应用编程接口（API）或（交互式）图形用户界面（GUI）应用程序（如果是独立程序）。工具包应明确集中于深度学习，从文档中可以看出，并且应与常见的 DL 框架集成。

##### 选择的工具包

在$180$个仓库中，有$11$个满足上述不确定性工具包的标准。它们列在附录中的表 1。其中，我们发现了专门用于深度不确定性估计的工具包（专门的 UE）以及提供 UE 能力的范围更广的库。后者类别包括**GluonTS**（GTS, Alexandrov 等人 (2020))，一个概率时间序列库，以及多个深度概率编程库（PPLs），这些库旨在指定通用贝叶斯网络并为这些模型执行推断（van de Meent 等人, 2018）。具体包括**Tensorflow 概率**（TFP, Dillon 等人 (2017))、**Pyro**（Bingham 等人, 2019）、**Edward2**（ED2, Tran 等人 (2018))、**ZhuSuan**（ZS, Shi 等人 (2017)) 和**MXFusion**（MXF, Meissner 等人 (2019))。

在专门的 UE 工具包中，例如**不确定性量化 360**（UQ360, Ghosh 等人 (2021))，它提供了多个不确定性估计工具，并且是 IBM 研究开发的更大工具包集的一部分，每个工具包针对 AI 可信度的不同维度，包括“**AI 公平性 360**”（Bellamy 等人, 2018）和“**AI 可解释性 360**”（Arya 等人, 2020）。我们还发现了几种功能范围较窄的库：**不确定性工具箱**（UT, Chung 等人 (2021)) 专注于标准回归任务中的不确定性估计的再校准和评估。**不确定性向导**（UW, Weiss & Tonella (2021)) 是一个扩展 keras 模型以支持丢弃和基于集成的不确定性估计能力的包。**贝叶斯火炬**（BT, Krishnan 等人 (2022)) 提供了用于构建变分贝叶斯神经网络的 pytorch 层模块，而**Keras-ADF**（KADF, Maces & Contributors (2019)) 提供了用于假定密度滤波的 keras 层模块。所有这些工具包均在宽松的自由软件许可证下发布（即 Apache-2.0, MIT 或 BSD3），附带的限制非常少，并允许包括商业使用在内的多种使用方式。

## 4 不确定性工具包的评估标准

在本节中，我们详细介绍了用于分析不确定性估计工具包的标准，这些工具包在 5 中进行了比较分析。我们将标准和分析分为“核心”部分，所有工具包都进行评估，以及对选定的最具多功能性的工具进行更深入的扩展分析，我们还考虑了“附加”质量标准。“核心”部分着重于框架支持的不确定性建模和评估技术的范围以及它兼容的神经架构和数据类型/结构。“附加”标准还考虑了代码质量，包括与标准深度学习框架的集成程度以及文档、模块化和测试水平。

*核心标准*

##### 支持的不确定性方法范围

每种不确定性估计方法都有其自身的优缺点，包括估计质量、计算/存储成本、可实践性（实施、培训和评估的难易程度）、灵活性或理论合理性。这意味着，根据具体应用场景，有些方法可能比其他方法更合适。因此，我们将构建或改进不确定性模型或扩展标准（确定性）模型的功能范围视为相关（核心）评估标准。

##### 支持的评估技术范围

深度学习模型的研究和开发中一个关键部分是评估其预测质量并与其他模型进行比较。为了使不确定性模型能够进行这种评估，工具包应提供专门的指标来测量不确定性估计的质量，如适当的评分规则、校准或辅助评分。由于没有任何指标适用于所有应用场景，工具包应覆盖各种不同的不确定性指标，可能还配有可视化（如校准图或置信区间）。

##### 支持的架构和数据结构范围

仅支持多层感知器架构的工具包在计算机视觉任务中几乎没有用处，因为它不支持卷积层或图像输入。这表明，为了适用于不同的使用案例，工具包应支持广泛的网络架构、优化器和数据结构，我们将其视为评估的相关标准。

*附加标准*

##### 与深度学习框架的集成

深度学习软件通常具有一套特殊的需求，包括灵活的数据管道、高效的优化（自动微分、GPU/多核利用）、可重复性（超参数、种子和配置的记录）和模块化模型构建。像 tensorflow 或 pytorch 这样的深度学习框架 (i) 满足这些需求，(ii) 维护良好，并拥有庞大的开发者和用户社区，(iii) 可以被视为开发深度学习软件的事实标准。为了利用这些属性，一个不确定性工具包应积极使用深度学习框架中的工具，并与其高度互操作，例如，通过提供可以插入现有框架本地模型的层模块。

##### 软件质量

我们还根据一般软件质量标准对工具包进行评估，包括 (i) 可用性和文档质量，(ii) 模块化和可集成性以及 (iii) 维护和测试。一个高可用的工具包通常具有简单的安装过程、易于理解和操作的代码架构/API，并且文档完善。一个高度模块化的工具包提供灵活的构建块，理想情况下，在从高层（易于使用，但灵活性较差）到低层（最高自定义级别，但实现难度更大且需要更高的技术理解）的不同抽象层次上，可以相互组合。代码维护的重要方面包括积极支持代码贡献、遵循编码风格规范（例如，通过代码检查）和强制代码测试（例如，持续集成和报告代码覆盖率）。

## 5 选定不确定性工具包的比较分析

接下来，我们首先根据核心标准分析第三部分中的所有不确定性工具包，包括支持的不确定性方法、评估技术和架构/数据结构（参见第四部分）。基于此分析，我们选择了三个最相关的工具包，即 UQ360、Pyro 和 TFP，在 5.2 节进行深入分析。此分析还将包括第四部分中的扩展评估标准。在这两种情况下，我们都按照标准而不是工具包来组织分析，以便更好地对比工具包之间的差异。

### 5.1 针对核心标准的分析

我们现在简要比较所有 $11$ 个不确定性工具包，这些工具包在第三部分中被选择，重点关注核心标准。每个工具包的简要总结可以在附录中的表 2 的上部找到。

##### 支持的不确定性方法范围

UQ360 提供最广泛的方法，包括内在、后验和重新校准方法。所有其他工具包仅覆盖内在方法，除了 UT，其关注于基本的重新校准方法。深度 PPLs 提供内在贝叶斯方法，主要是 MCMC、VI-BNNs 或高斯过程。与 BT 或 UQ360 的可比方法相比，它们通常涵盖更广泛的先验、似然和变分后验分布。时间序列库 GTS 仅提供参数化似然方法，但支持大量分布（尤其是相比 UQ360 仅支持高斯似然）。UW、BT 和 KADF 是专门的 UE 库，分别专注于内在方法 dropout/ensembling、VI-BNN 和 ADF-BNN。

##### 支持的评估技术范围

UQ360 和 UT 拥有最全面的评估工具集，从评分规则到校准评分和绘图功能，其次是 TFP，缺乏绘图功能。GTS 提供评分规则以及用于绘制带置信区间的预测时间序列的函数。相比之下，Pyro、ED2 和 ZS 的能力较为狭窄，专注于贝叶斯推断中的标准评估指标，即计算预测分布的对数概率。一些工具包（UW、BT、KADF 和 MXF）不包含任何评估能力。

##### 支持的架构和数据结构范围

深度概率编程语言（PPLs）旨在实现对各种不同架构模型的贝叶斯推断。UW、BT 和 KDF 提供对分类和回归模型的支持。前者提供基于 Keras 的模型接口，而 BT 和 KDF 则提供密集层和卷积层的替代方案。BT 还通过包含概率长短期记忆层（Hochreiter & Schmidhuber, 1997）来覆盖递归模型。相比之下，GTS 和 UT 专注于特定领域，如时间序列建模（GTS）或一维回归（UT）。

总体而言，我们发现 TFP、Pyro 和 UQ360 提供了最全面的模型、评估技术和支持架构目录。

### 5.2 TFP、Pyro 和 UQ360 的详细分析

我们现在扩展了对三种最有前景的工具包的分析，即 UQ360、Pyro 和 TFP。特别是，我们提供了更多关于核心标准的细节，并考虑了两个“额外”标准：与深度学习框架的集成和软件质量。有关结果的表格摘要，请参见附录中表 2 的底部部分。

##### 支持的不确定性方法范围

如前所述，UQ360 提供了不同集成深度下的广泛方法。具体来说，它的内在方法包括通过高斯似然进行的纯偶然不确定性估计，以及通过 VI-BNNs 或深度集成进行的偶然和认知不确定性的联合建模方法。事后方法包括无穷小的拔刀法（Giordano et al., 2019）和替代模型方法（Chen et al., 2019）。此外，UQ360 还是唯一提供了除标准 Platt 缩放或等距回归外的重新校准方法的工具包，并额外包括了例如辅助区间预测器（Thiagarajan et al., 2020）和 UCC 重新缩放（Navrátil et al., 2021）。

PPLs TFP 和 Pyro 涵盖了内在方法，如参数似然（偶然不确定性）、VI-BNNs（偶然 + 认知）和（变分）高斯过程（功能不确定性）。它们还提供了非参数后验采样方法，如哈密顿蒙特卡洛（Hamiltonian Monte Carlo）（Neal et al., 2011）或一般的梅特罗波利斯-哈斯廷斯方法（Metropolis et al., 1953; Hastings, 1970），由于其高估计准确性，对于研究人员可能很有用，但通常在大规模模型中难以应用。TFP 还提供了一个更具可扩展性的变体，即 SGLD（Welling & Teh, 2011; Li et al., 2016）。从设计上讲，与 UQ360 的相应模块相比，PPLs 支持更广泛的先验、似然和变分后验分布。例如，可以使用归一化流（Rezende & Mohamed, 2015）来实现更灵活的先验或后验分布。

##### 支持的评估技术范围

UQ360 提供了广泛的评估技术。它涵盖了标准指标，即回归的高斯负对数似然（Gaussian NLL）、分类的期望校准误差（ECE）和布里尔评分（Brier score），以及一些不常用的评分，如风险-拒绝率曲线下面积（Franc & Prusa，2019）或不确定性校准曲线（UCC，Navrátil et al. (2021））。除了这些指标外，它还有一些有用的评估“工具”，如一个将类别概率样本分解为偶然不确定性和认知不确定性的函数，或各种绘图函数（例如，校准曲线和预测区间）。

相比之下，TFP 在将不确定性估计与真实标签进行比较时具有较窄的评估能力，并为此目的提供了上述标准指标。与标量值不同，TFP 模型预测分布对象。这些对象提供了计算标准统计数据的函数，如对数概率、矩、分位数、相关性、累积分布函数 (cdf’s) 和与其他分布的 KL 散度。这些统计数据可以计算广泛的分布范围，除了高斯分布，还包括例如多变量分布和混合模型。

Pyro 提供了一个用于从给定贝叶斯模型的预测分布中进行近似采样的模块，作为进一步评估的基础。为此，它提供了通用的统计工具（例如计算分位数、自相关或预测区间）和 CRPS (Gneiting & Raftery, 2007) 作为评分规则。

##### 支持的架构和数据结构范围

UQ360 的方法目录涵盖了回归和分类场景（主要是 1D）。然而，许多模型类（例如 VI-BNN 或深度集成）具有预写的训练程序或甚至架构，这限制了将给定深度学习模型扩展为包含不确定性估计的能力。输入通常要求为（2D）表格形式，限制了处理序列数据或其他数据类型的能力。相比之下，TFP 是一组较小的构建块，提供了可以用作标准 tensorflow 模块的补充或替代的层和优化器模块。例如，它提供了概率的替代模块，用于密集层或卷积层，以将给定的 NNs 转换为 BNNs。对于 pytorch，Pyro 提供了将 NNs 转换为 BNNs 的类似能力，主要通过对相应的 NN 类进行子类化，并用随机模块替换 pytorch 参数。这两个 PPL 的高度模块化结构允许构建具有各种不同架构和输入的模型，例如多维回归和序列数据。

##### 与深度学习框架的集成

由于 Tensorflow Probability (TFP) 是 Tensorflow 生态系统的一部分，它的模块旨在与 tensorflow/keras 的其他模块无缝接口。特别是，它与 keras 模型 API 集成，这使得开发者可以使用 keras 的原生 `compile` 和 `fit` 函数来构建和训练概率模型。Pyro 利用其基础框架 pytorch 的层、优化器、数据和分布函数。在 Pyro 中构建 BNN 时，除了新提供的随机模块外，还可以使用标准的 pytorch 模块（例如层和激活函数）。此外，模型和推理过程可以被封装为 pytorch 模块，从而能够创建用于部署的 TorchScript 程序。

UQ360 的大多数模型类基于 pytorch。这些类易于使用，但不如 TFP 为 keras 模型提供的构建块那样灵活和模块化。更改网络架构、输入管道或训练过程通常需要修改代码，而不是简单地将不同的模块（例如优化器和数据加载器）传递给模型类。

##### 软件质量

三个工具包都有简单的安装过程，并且在 Python 包索引中列出。除了 TFP 需要事先安装兼容的 tensorflow 版本外，这些工具包及其所有依赖项都可以通过单个 pip 命令进行安装。Pyro 除了提供 pip，还提供了一个用于安装的 docker 镜像。各工具包之间的依赖选择合理，使用了基础的深度学习框架以及 numpy、scipy、matplotlib 或 pandas 等标准库。所有工具包都在积极维护中，欢迎提交问题和拉取请求，并提供明确的贡献文档（通过 readme）。TFP 和 Pyro 遵循编码风格指南（例如 PEP8³³3PEP8 是官方 python 发行版使用的编码风格指南），以确保新增代码符合编码规范，并且采用持续集成进行代码测试。

接下来，我们讨论工具包的接口结构。UQ360 具有简单的类似 scikit-learn 的 API（即模型类提供`fit`和`predict`函数，接收 numpy 数组作为输入），理解起来同样直观。TFP 采用 keras 模型 API，这个 API 非常灵活且易于理解。Pyro 的 API 则更侧重于不确定性估计的贝叶斯建模视角。用户需要定义两个单独的类（或函数），其中一个定义模型及其先验和似然分布，另一个（所谓的 guide）定义变分后验分布。由于 Pyro 使用的 API 结构与广泛知晓的 API（例如 sklearn 或 keras）不同，用户可能更难迅速上手。另一方面，自动生成标准后验分布（例如均值场 VI）或创建约束的网络参数（例如分布的正尺度参数）的可能性提高了 API 的可用性。与 TFP 相比，Pyro 缺乏对标准层的直接替代品，这导致自定义实现的工作量更大。

UQ360 的代码简单且高度可读，但可以更频繁地进行输入检查（例如类型或形状）和适当的异常处理。Pyro 和 TFP 的代码基础设计得更加灵活，以满足其各自基础库（pytorch 或 tensorflow）的兼容性要求（例如实现超类的函数），因此其结构较为复杂且隐蔽。整体质量较高，体现在适当的输入检查和异常处理，以及干净且一致的编码风格上。

## 6 讨论

可靠的模型应该能够识别它们正常工作的边界。寻找不确定性来源并量化其对模型性能的影响有助于这一方面。尽管已经开发了许多不确定性估计方法，但它们的使用仍面临技术复杂性等障碍。通过提供高质量的软件组件，不确定性评估工具包有助于克服这些障碍，并促进标准化评估。为了帮助读者选择合适的工具包，我们提供了现有深度不确定性工具包的第一次调查。我们定义了这些工具包的最低要求，并分析了$11$个工具包在支持的不确定性方法、评估技术、架构和数据结构方面的表现。我们还在与深度学习框架的集成和软件质量方面进一步检查了三个最相关的工具包（TFP、Pyro 和 UQ360）。所有分析的工具包都提供了简化不确定性模型开发和评估的模块。它们包括专注于将贝叶斯推断引入深度学习模型的深度概率编程库（例如 Pyro、MXF、ZS），以及涵盖更广泛方法或评估的专用不确定性工具包（例如 UQ360、UT）。我们计划在未来的工作迭代中将详细分析扩展到更多工具包。调查还揭示了对不确定性评估软件的期望改进和未来的激励措施，接下来将讨论这些内容。

##### 扩展不确定性工具包的技术能力

考虑的 UE 工具包要么更全面（例如 UQ360），要么更模块化并且与 DL 框架具有互操作性（例如 TFP，Pyro，UW）。 UE 工具包理想情况下应该结合这两个方面。目前可用工具包技术全面性的进一步具体改进包括：（i）提供更多的事后方法，在重新构建模型或重新训练成本高昂的情景中尤为重要；（ii）将不确定性注入到特定于应用的网络组件中，例如注入到计算机视觉模型的非最大抑制或聚类过程中（如 Meyer et al。（2019）; Harakeh et al.（2020））；（iii）提供考虑不确定性的任务性能基准测试工具（例如基于假设检验的，如（Gorman＆Bedrick，2019））。

##### 与其他工具包的接口

在深度学习中，除了不确定性估计之外，还有大量相关任务和问题。例如，考虑到 AI 的可信度的不同方面，会采用不同的指标和方法来评估和确保 AI 的可信度，如鲁棒性、可解释性或公平性。为了同时解决多个这样的问题，工具包应提供可互操作的接口。如果工具包能与相同的 DL 框架（如我们评估的那样）无缝集成，这种互操作性可能会更加便利。工具包之间的互操作性甚至可以直接影响 UE。例如，数据增强工具包（例如 augLy（Papakipos＆Bitton， 2022））提供了用于超出分布评估的输入损坏，而在线学习工具包（例如 river（Montiel 等，2020）） 可用于将不确定性模型调整到未来观察中。未来的展望是将多个 AI 可信度工具包（例如 AI Fairness 360(Bellamy 等，2018)，对抗性鲁棒性工具包（Nicolae 等，2018））组合成一个高度全面的测试框架。

##### 正确使用工具的指导

通过提供可用的高级接口，工具包降低了广泛用户使用（可能非常复杂）算法的门槛。此外，它们还应支持正确使用所提供的工具，例如，通过提供全面的指南。UQ360 的文档提供了选择不确定性方法和向利益相关者传达不确定性估计的指导，我们认为这是朝着正确方向迈出的第一步。其他支持更明智和有效使用 UE 的手段包括将不确定性归因于具体来源（即数据、超参数调整、初始化等产生了多少不确定性）、减少不确定性的说明，以及对比评估分数并描述其属性。视觉和互动界面可以进一步帮助正确使用工具。为了普遍改善文档实践，可以制定工具包及其工具的文档标准，例如“模型卡”（Mitchell 等，2019）。

##### 维护代码质量

开源似乎是可靠评估标准实现的一个前提条件，许多被审查的工具包主要重视代码质量，这通过支持代码贡献或采用自动化测试工具可以看出。但这并不足以确保高质量和避免关键错误。特别是在可信 AI 和安全关键系统的背景下，我们认为这是 UE 的一个重要应用领域，这可能会成为一个问题。为了进一步改善这一点，似乎有必要激励系统化的代码审查，例如通过为主要工具包引入漏洞赏金计划，并通常提高对该话题的关注（例如，通过专门的代码质量研讨会）。

#### 致谢

本出版物的开发得到了北莱茵-威斯特法伦州经济事务、创新、数字化和能源部的支持，作为旗舰项目 ZERTIFIZIERTE KI 的一部分。

## 参考文献

+   Abadi 等（2015） Martín Abadi, Ashish Agarwal, Paul Barham, Eugene Brevdo, Zhifeng Chen, Craig Citro, Greg S. Corrado, Andy Davis, Jeffrey Dean, Matthieu Devin, Sanjay Ghemawat, Ian Goodfellow, Andrew Harp, Geoffrey Irving, Michael Isard, Yangqing Jia, Rafal Jozefowicz, Lukasz Kaiser, Manjunath Kudlur, Josh Levenberg, Dandelion Mané, Rajat Monga, Sherry Moore, Derek Murray, Chris Olah, Mike Schuster, Jonathon Shlens, Benoit Steiner, Ilya Sutskever, Kunal Talwar, Paul Tucker, Vincent Vanhoucke, Vijay Vasudevan, Fernanda Viégas, Oriol Vinyals, Pete Warden, Martin Wattenberg, Martin Wicke, Yuan Yu, and Xiaoqiang Zheng. TensorFlow: 大规模异构系统上的机器学习, 2015. 网址 [`www.tensorflow.org/`](https://www.tensorflow.org/)。软件可从 tensorflow.org 获得。

+   Agarwal & Das (2020) Namita Agarwal 和 Saikat Das. 可解释的机器学习工具：综述。见 *2020 IEEE 计算智能研讨会（SSCI）*，第 1528–1534 页。IEEE，2020 年。

+   Alaa & Van Der Schaar (2020) Ahmed Alaa 和 Mihaela Van Der Schaar. 判别性切除法：通过高阶影响函数量化深度学习中的不确定性。见 Hal Daumé III 和 Aarti Singh (编)，*第 37 届国际机器学习大会论文集*，第 119 卷，*机器学习研究论文集*，第 165–174 页。PMLR，2020 年 7 月 13–18 日。网址 [`proceedings.mlr.press/v119/alaa20a.html`](https://proceedings.mlr.press/v119/alaa20a.html)。

+   Alam et al. (2020) M. Alam, M.D. Samad, L. Vidyaratne, A. Glandon 和 K.M. Iftekharuddin. 语音和视觉系统中的深度神经网络综述。*神经计算*，417:302–321，2020 年。ISSN 0925-2312。doi: https://doi.org/10.1016/j.neucom.2020.07.053。网址 [`www.sciencedirect.com/science/article/pii/S0925231220311619`](https://www.sciencedirect.com/science/article/pii/S0925231220311619)。

+   Alexandrov et al. (2020) Alexander Alexandrov, Konstantinos Benidis, Michael Bohlke-Schneider, Valentin Flunkert, Jan Gasthaus, Tim Januschowski, Danielle C. Maddix, Syama Rangapuram, David Salinas, Jasper Schulz, Lorenzo Stella, Ali Caner Türkmen 和 Yuyang Wang. GluonTS：Python 中的概率和神经时间序列建模。*机器学习研究杂志*，21(116):1–6，2020 年。网址 [`jmlr.org/papers/v21/19-820.html`](http://jmlr.org/papers/v21/19-820.html)。

+   Amini et al. (2020) Alexander Amini, Wilko Schwarting, Ava Soleimany 和 Daniela Rus. 深度证据回归。见 H. Larochelle, M. Ranzato, R. Hadsell, M. F. Balcan 和 H. Lin (编)，*神经信息处理系统进展*，第 33 卷，第 14927–14937 页。Curran Associates, Inc.，2020 年。网址 [`proceedings.neurips.cc/paper/2020/file/aab085461de182608ee9f607f3f7d18f-Paper.pdf`](https://proceedings.neurips.cc/paper/2020/file/aab085461de182608ee9f607f3f7d18f-Paper.pdf)。

+   Arya et al. (2020) Vijay Arya, Rachel K. E. Bellamy, Pin-Yu Chen, Amit Dhurandhar, Michael Hind, Samuel C. Hoffman, Stephanie Houde, Q. Vera Liao, Ronny Luss, Aleksandra Mojsilović, Sami Mourad, Pablo Pedemonte, Ramya Raghavendra, John Richards, Prasanna Sattigeri, Karthikeyan Shanmugam, Moninder Singh, Kush R. Varshney, Dennis Wei 和 Yunfeng Zhang. Ai explainability 360: 实用教程。见 *2020 年公平性、问责制与透明度会议论文集*，FAT* ’20，第 696 页，美国纽约，2020 年。计算机协会。ISBN 9781450369367。doi: 10.1145/3351095.3375667。网址 [`doi.org/10.1145/3351095.3375667`](https://doi.org/10.1145/3351095.3375667)。

+   Bahrampour et al. (2015) Soheil Bahrampour, Naveen Ramakrishnan, Lukas Schott 和 Mohak Shah. 深度学习软件框架的比较研究。*arXiv: Learning*，2015 年。

+   Bellamy 等（2018）Rachel K. E. Bellamy, Kuntal Dey, Michael Hind, Samuel C. Hoffman, Stephanie Houde, Kalapriya Kannan, Pranay Kr. Lohia, Jacquelyn Martino, Sameep Mehta, Aleksandra Mojsilovic, Seema Nagar, Karthikeyan Natesan Ramamurthy, John T. Richards, Diptikalyan Saha, Prasanna Sattigeri, Moninder Singh, Kush R. Varshney, 和 Yunfeng Zhang. AI 公平性 360：检测、理解和减轻不希望的算法偏见的可扩展工具包。*ArXiv*, abs/1810.01943, 2018。

+   Beluch 等（2018）William H. Beluch, Tim Genewein, Andreas Nurnberger, 和 Jan M. Kohler. 集成方法在图像分类中的主动学习能力。见 *2018 IEEE/CVF Conference on Computer Vision and Pattern Recognition*, pp. 9368–9377, 2018. doi: 10.1109/CVPR.2018.00976。

+   Bingham 等（2019）Eli Bingham, Jonathan P. Chen, Martin Jankowiak, Fritz Obermeyer, Neeraj Pradhan, Theofanis Karaletsos, Rohit Singh, Paul A. Szerlip, Paul Horsfall, 和 Noah D. Goodman. Pyro: 深度通用概率编程。*J. Mach. Learn. Res.*, 20:28:1–28:6, 2019. URL [`jmlr.org/papers/v20/18-403.html`](http://jmlr.org/papers/v20/18-403.html)。

+   Blundell 等（2015）Charles Blundell, Julien Cornebise, Koray Kavukcuoglu, 和 Daan Wierstra. 神经网络中的权重不确定性。见 *Proceedings of the 32nd International Conference on International Conference on Machine Learning - Volume 37*, ICML’15, pp. 1613–1622. JMLR.org, 2015。

+   Brundage 等（2020）Miles Brundage, Shahar Avin, Jasmine Wang, Haydn Belfield, Gretchen Krueger, Gillian K. Hadfield, Heidy Khlaaf, Jingying Yang, Helen Toner, Ruth Fong, Tegan Maharaj, Pang Wei Koh, Sara Hooker, Jade Leung, Andrew Trask, Emma Bluemke, Jonathan Lebensbold, Cullen O’Keefe, Mark Koren, Theo Ryffel, J. B. Rubinovitz, Tamay Besiroglu, Federica Carugati, Jack Clark, Peter Eckersley, Sarah de Haas, Maritza L. Johnson, Ben Laurie, Alex Ingerman, Igor Krawczuk, Amanda Askell, Rosario Cammarota, Andrew J. Lohn, David Krueger, Charlotte Stix, Peter Henderson, Logan Graham, Carina E. A. Prunkl, Bianca Martin, Elizabeth Seger, Noa Zilberman, Se’an ’O h’Eigeartaigh, Frens Kroeger, Girish Sastry, Rebecca Kagan, Adrian Weller, Brian Tse, Elizabeth Barnes, Allan Dafoe, Paul Scharre, Ariel Herbert-Voss, Martijn Rasser, Shagun Sodhani, Carrick Flynn, Thomas Krendl Gilbert, Lisa Dyer, Saif Khan, Yoshua Bengio, 和 Markus Anderljung. 朝向值得信赖的 AI 发展：支持可验证声明的机制。*ArXiv*, abs/2004.07213, 2020。

+   Chai 等（2021）Junyi Chai, Hao Zeng, Anming Li, 和 Eric W.T. Ngai. 计算机视觉中的深度学习：新兴技术和应用场景的关键综述。*Machine Learning with Applications*, 6:100134, 2021. ISSN 2666-8270. doi: https://doi.org/10.1016/j.mlwa.2021.100134. URL [`www.sciencedirect.com/science/article/pii/S2666827021000670`](https://www.sciencedirect.com/science/article/pii/S2666827021000670)。

+   Chatila 等（2021）Raja Chatila、Virginia Dignum、Michael Fisher、Fosca Giannotti、Katharina Morik、Stuart Russell 和 Karen Yeung。在*人工智能对人类的反思*中，值得信赖的人工智能，页码 13–39。Springer，2021 年。

+   Chen 等（2015）Tianqi Chen、Mu Li、Yutian Li、Min Lin、Naiyan Wang、Minjie Wang、Tianjun Xiao、Bing Xu、Chiyuan Zhang 和 Zheng Zhang。在*CoRR*中，Mxnet：一种灵活高效的异构分布式系统机器学习库，abs/1512.01274，2015 年。URL [`dblp.uni-trier.de/db/journals/corr/corr1512.html#ChenLLLWWXXZZ15`](http://dblp.uni-trier.de/db/journals/corr/corr1512.html#ChenLLLWWXXZZ15)。

+   Chen 等（2019）陈同飞、Jirí Navrátil、Vijay Iyengar 和 Karthikeyan Shanmugam。在*第 22 届国际人工智能与统计会议*上，使用白盒元模型和线性分类器探针进行置信度评分，页码 1467–1475。PMLR，2019 年。

+   Chung 等（2021）Youngseog Chung、Ian Char、Han Guo、Jeff Schneider 和 Willie Neiswanger。在*arXiv 预印本 arXiv:2109.10254*中，不确定性工具箱：一个用于评估、可视化和改进不确定性量化的开源库，2021 年。

+   Dillon 等（2017）Joshua V. Dillon、Ian Langmore、Dustin Tran、Eugene Brevdo、Srinivas Vasudevan、Dave Moore、Brian Patton、Alex Alemi、Matthew D. Hoffman 和 Rif A. Saurous。在*CoRR*中，Tensorflow 分布，abs/1711.10604，2017 年。URL [`arxiv.org/abs/1711.10604`](http://arxiv.org/abs/1711.10604)。

+   Druzhkov & Kustikova（2016）Paul Druzhkov 和 Valentina Kustikova。在*模式识别与图像分析*中，深度学习方法和软件工具的综述，26:9–15，2016 年 01 月。doi: 10.1134/S1054661816010065。

+   Durasov 等（2021）N. Durasov、T. Bagautdinov、P. Baque 和 P. Fua。在*CVPR*上，不确定性估计的 Masksembles，2021 年。

+   Fan 等（2021）Xinjie Fan、Shujian Zhang、Korawat Tanwisuth、Xiaoning Qian 和 Mingyuan Zhou。在*第 9 届国际学习表征会议，ICLR 2021，虚拟会议，奥地利，2021 年 5 月 3-7 日*中，情境丢弃：一种高效的样本依赖丢弃模块。OpenReview.net，2021 年。URL [`openreview.net/forum?id=ct8_a9h1M`](https://openreview.net/forum?id=ct8_a9h1M)。

+   Franc & Prusa（2019）Vojtech Franc 和 Daniel Prusa。在 Kamalika Chaudhuri 和 Ruslan Salakhutdinov（编辑），*第 36 届国际机器学习大会论文集*中，关于预测不确定性的辨别学习，*机器学习研究论文集*第 97 卷，页码 1963–1971。PMLR，2019 年 6 月 09–15 日。URL [`proceedings.mlr.press/v97/franc19a.html`](https://proceedings.mlr.press/v97/franc19a.html)。

+   Gal & Ghahramani (2016) Yarin Gal 和 Zoubin Ghahramani。Dropout 作为贝叶斯近似：在深度学习中表示模型不确定性。见于 Maria-Florina Balcan 和 Kilian Q. Weinberger (编辑)，*第 33 届国际机器学习大会论文集, ICML 2016, 纽约市, NY, USA, 2016 年 6 月 19-24 日*，*JMLR 工作坊和会议论文集*第 48 卷，第 1050–1059 页。JMLR.org，2016 年。网址 [`proceedings.mlr.press/v48/gal16.html`](http://proceedings.mlr.press/v48/gal16.html)。

+   Gal et al. (2017) Yarin Gal, Riashat Islam 和 Zoubin Ghahramani。带有图像数据的深度贝叶斯主动学习。见于 *第 34 届国际机器学习大会论文集 - 第 70 卷*，ICML’17，第 1183–1192 页。JMLR.org，2017 年。

+   Gast & Roth (2018) Jochen Gast 和 Stefan Roth。轻量级概率深度网络。见于 *2018 IEEE 计算机视觉与模式识别会议，CVPR 2018, 盐湖城, UT, USA, 2018 年 6 月 18-22 日*，第 3369–3378 页。IEEE 计算机学会，2018 年。doi: 10/gfx44n。

+   Gawlikowski et al. (2021) Jakob Gawlikowski, Cedrique Rovile Njieutcheu Tassi, Mohsin Ali, Jongseok Lee, Matthias Humt, Jianxiang Feng, Anna Kruspe, Rudolph Triebel, Peter Jung, Ribana Roscher 等人。深度神经网络中的不确定性调查。*arXiv 预印本 arXiv:2107.03342*，2021 年。

+   Ghosh et al. (2021) Soumya Ghosh, Q. Vera Liao, Karthikeyan Natesan Ramamurthy, Jiri Navratil, Prasanna Sattigeri, Kush R. Varshney 和 Yunfeng Zhang。 不确定性量化 360：量化和传达人工智能不确定性的全方位工具包，2021 年。

+   Giordano et al. (2019) Ryan Giordano, William T. Stephenson, Runjing Liu, Michael I. Jordan 和 Tamara Broderick。瑞士军刀微小化。见于 *AISTATS*，2019 年。

+   Gneiting & Raftery (2007) Tilmann Gneiting 和 Adrian E Raftery。严格的适当评分规则、预测和估计。*美国统计协会杂志*，102(477):359–378，2007 年。

+   Gorman & Bedrick (2019) Kyle Gorman 和 Steven Bedrick。我们需要讨论标准拆分。见于 *第 57 届计算语言学协会年会论文集*，第 2786–2791 页，意大利佛罗伦萨，2019 年 7 月。计算语言学协会。doi: 10.18653/v1/P19-1267。网址 [`aclanthology.org/P19-1267`](https://aclanthology.org/P19-1267)。

+   Graves (2011) Alex Graves。神经网络的实用变分推断。见于 J. Shawe-Taylor, R. Zemel, P. Bartlett, F. Pereira 和 K. Q. Weinberger (编辑)，*神经信息处理系统进展*，第 24 卷。Curran Associates, Inc.，2011 年。网址 [`proceedings.neurips.cc/paper/2011/file/7eb3c8be3d411e8ebfab08eba5f49632-Paper.pdf`](https://proceedings.neurips.cc/paper/2011/file/7eb3c8be3d411e8ebfab08eba5f49632-Paper.pdf)。

+   Guo et al. (2017) 全·郭、杰夫·普利斯、余·孙和基利安·Q·温伯格。现代神经网络的校准。在多伊娜·普雷库普和易·惠·特（编辑），*第 34 届国际机器学习大会论文集，ICML 2017，澳大利亚悉尼，2017 年 8 月 6-11 日*，第 70 卷*机器学习研究论文集*，第 1321–1330 页。PMLR，2017 年。URL [`proceedings.mlr.press/v70/guo17a.html`](http://proceedings.mlr.press/v70/guo17a.html)。

+   Guo et al. (2020) 简·郭、何赫、童赫、伦纳德·劳森、穆·李、海滨·林、邢建·石、程光·王、俊远·谢、盛扎、阿斯顿·张、杭张、智张、钟跃·张、帅郑和易朱。Gluoncv 和 gluonnlp：深度学习在计算机视觉和自然语言处理中的应用。*机器学习研究杂志*，21(23):1–7，2020。URL [`jmlr.org/papers/v21/19-429.html`](http://jmlr.org/papers/v21/19-429.html)。

+   Hafiz & Bhat (2020) 阿卜杜勒·穆伊德·哈菲兹和古拉姆·穆希丁·巴特。*医学诊断中的深度学习技术综述*，第 161–170 页。Springer，2020 年。

+   Harakeh et al. (2020) 阿里·哈拉克、迈克尔·斯马特和史蒂文·L·瓦斯兰德。BayesOD：一种用于深度目标检测器不确定性估计的贝叶斯方法。在*2020 IEEE 国际机器人与自动化会议（ICRA）*，第 87–93 页。IEEE，2020 年。

+   Hastings (1970) W·K·海斯廷斯。使用马尔可夫链的蒙特卡洛采样方法及其应用。*生物计量学*，57(1):97–109，1970 年。ISSN 00063444。URL [`www.jstor.org/stable/2334940`](http://www.jstor.org/stable/2334940)。

+   Hensman et al. (2013) 詹姆斯·亨斯曼、尼科洛·富西和尼尔·D·劳伦斯。大数据的高斯过程。在*第二十九届人工智能不确定性会议论文集*，UAI’13，第 282–290 页，美国弗吉尼亚州阿灵顿，2013 年。AUAI 出版社。

+   Hernández-Lobato & Adams (2015) 何塞·米格尔·埃尔南德斯-洛巴托和瑞安·P·亚当斯。可扩展学习贝叶斯神经网络的概率反向传播。在*第 32 届国际机器学习大会论文集 - 第 37 卷*，ICML’15，第 1861–1869 页。JMLR.org，2015 年。

+   Hochreiter & Schmidhuber (1997) 塞普·霍赫赖特和尤尔根·施密德胡伯。长短期记忆。*神经计算*，9(8):1735–1780，1997 年。

+   Honnibal et al. (2020) 马修·霍尼巴尔、伊内斯·蒙塔尼、索菲·范·兰德赫姆和阿德里安·博伊德。spacy：工业级自然语言处理工具，2020 年。

+   Houben et al. (2021) Sebastian Houben、Stephanie Abrecht、Maram Akila、Andreas Bär、Felix Brockherde、Patrick Feifel、Tim Fingscheidt、Sujan Sai Gannamaneni、Seyed Eghbal Ghobadi、Ahmed Hammam、Anselm Haselhoff、Felix Hauser、Christian Heinzemann、Marco Hoffmann、Nikhil Kapoor、Falk Kappel、Marvin Klingner、Jan Kronenberger、Fabian Küppers、Jonas Löhdefink、Michael Mlynarski、Michael Mock、Firas Mualla、Svetlana Pavlitskaya、Maximilian Poretschkin、Alexander Pohl、Varun Ravi Kumar、Julia Rosenzweig、Matthias Rottmann、Stefan Rüping、Timo Sämann、Jan David Schneider、Elena Schulz、Gesina Schwalbe、Joachim Sicking、Toshika Srivastava、Serin Varghese、Michael Weber、Sebastian Wirkert、Tim Wirtz 和 Matthias Woehrle。检查、理解、克服：AI 安全的实用方法综述。*CoRR*，abs/2104.14235，2021 年。网址 [`arxiv.org/abs/2104.14235`](https://arxiv.org/abs/2104.14235)。

+   Hüllermeier & Waegeman (2021) Eyke Hüllermeier 和 Willem Waegeman。机器学习中的偶然性和认知不确定性：概念和方法简介。*机器学习*，110(3):457–506，2021。

+   Kendall & Gal (2017) Alex Kendall 和 Yarin Gal。计算机视觉中的贝叶斯深度学习需要哪些不确定性？在 Isabelle Guyon、Ulrike von Luxburg、Samy Bengio、Hanna M. Wallach、Rob Fergus、S. V. N. Vishwanathan 和 Roman Garnett (编者) 主编的 *神经信息处理系统进展 30：2017 年神经信息处理系统年会，2017 年 12 月 4-9 日，加利福尼亚州长滩，USA* 中，第 5574–5584 页，2017 年。网址 [`proceedings.neurips.cc/paper/2017/hash/2650d6089a6d640c5e85b2b88265dc2b-Abstract.html`](https://proceedings.neurips.cc/paper/2017/hash/2650d6089a6d640c5e85b2b88265dc2b-Abstract.html)。

+   Kim et al. (2020) Byol Kim、Chen Xu 和 Rina Barber。预测推断在 jackknife+-after-bootstrap 中是免费的。*神经信息处理系统进展*，33:4138–4149，2020。

+   Kingma et al. (2015) Diederik P. Kingma、Tim Salimans 和 Max Welling。变分丢弃法和局部重参数化技巧。收录于 *第 28 届国际神经信息处理系统会议 - 第 2 卷*，NIPS’15，第 2575–2583 页。MIT 出版社，2015 年。页数：9 地点：加拿大蒙特利尔。

+   Krishnan et al. (2022) Ranganath Krishnan、Pi Esposito 和 Mahesh Subedar。Bayesian-Torch：用于不确定性估计的贝叶斯神经网络层。 [`github.com/IntelLabs/bayesian-torch`](https://github.com/IntelLabs/bayesian-torch)，2022 年 1 月。网址 [`doi.org/10.5281/zenodo.5908307`](https://doi.org/10.5281/zenodo.5908307)。

+   Kuleshov et al. (2018) Volodymyr Kuleshov, Nathan Fenner, 和 Stefano Ermon. 使用校准回归的深度学习准确不确定性。收录于 Jennifer Dy 和 Andreas Krause (编), *第 35 届国际机器学习大会论文集*, *机器学习研究论文集*第 80 卷, 第 2796–2804 页。PMLR, 2018。网址 [`proceedings.mlr.press/v80/kuleshov18a.html`](https://proceedings.mlr.press/v80/kuleshov18a.html). tex.pdf: http://proceedings.mlr.press/v80/kuleshov18a/kuleshov18a.pdf。

+   Lakshminarayanan et al. (2017) Balaji Lakshminarayanan, Alexander Pritzel, 和 Charles Blundell. 使用深度集成进行简单且可扩展的预测不确定性估计。收录于 Isabelle Guyon, Ulrike von Luxburg, Samy Bengio, Hanna M. Wallach, Rob Fergus, S. V. N. Vishwanathan, 和 Roman Garnett (编), *第 30 届神经信息处理系统年会：2017 年 12 月 4-9 日，美国加利福尼亚州长滩*, 第 6402–6413 页, 2017。网址 [`proceedings.neurips.cc/paper/2017/hash/9ef2ed4b7fd2c810847ffa5fa85bce38-Abstract.html`](https://proceedings.neurips.cc/paper/2017/hash/9ef2ed4b7fd2c810847ffa5fa85bce38-Abstract.html)。

+   Landset et al. (2015) Sara Landset, Taghi Khoshgoftaar, Aaron Richter, 和 Tawfiq Hasanin. 关于 Hadoop 生态系统中大数据机器学习的开源工具调查。*大数据杂志*, 2, 11 2015。doi: 10.1186/s40537-015-0032-1。

+   Li et al. (2016) Chunyuan Li, Changyou Chen, David E. Carlson, 和 Lawrence Carin. 用于深度神经网络的预处理随机梯度朗之万动力学。收录于 Dale Schuurmans 和 Michael P. Wellman (编), *第三十届 AAAI 人工智能会议论文集, 2016 年 2 月 12-17 日, 美国亚利桑那州凤凰城*, 第 1788–1794 页。AAAI Press, 2016。网址 [`www.aaai.org/ocs/index.php/AAAI/AAAI16/paper/view/11835`](http://www.aaai.org/ocs/index.php/AAAI/AAAI16/paper/view/11835)。

+   Liu et al. (2021) Haochen Liu, Yiqi Wang, Wenqi Fan, Xiaorui Liu, Yaxin Li, Shaili Jain, Yunhao Liu, Anil K Jain, 和 Jiliang Tang. 可信赖的人工智能：计算视角。*arXiv 预印本 arXiv:2107.06641*, 2021。

+   Liu et al. (2020) Jeremiah Liu, Zi Lin, Shreyas Padhy, Dustin Tran, Tania Bedrax Weiss, 和 Balaji Lakshminarayanan. 通过距离感知进行简单而有原则的不确定性估计。*神经信息处理系统进展*, 33:7498–7512, 2020。

+   Maces & Contributors (2019) Jan Maces 和 Repository Contributors. keras-adf 的 Github 仓库, 2019。网址 [`github.com/jmaces/keras-adf`](https://github.com/jmaces/keras-adf)。

+   MacKay (1992) David JC MacKay. 用于反向传播网络的实用贝叶斯框架。*神经计算*, 4(3):448–472, 1992。

+   Mahony 等人（2019）**奈尔·O’马霍尼**、**肖恩·坎贝尔**、**安德森·卡瓦略**、**苏曼·哈拉帕纳赫利**、**古斯塔沃·阿道夫·维拉斯科-埃尔南德斯**、**连卡·克尔帕尔科娃**、**丹尼尔·里奥丹** 和 **约瑟夫·沃尔什**。深度学习与传统计算机视觉。在 *CVC*，2019。

+   Meissner 等人（2019）**埃里克·梅斯纳**、**甄文·戴**、**汤姆·迪特** 和 **仓库贡献者**。MXFusion 的 GitHub 仓库，2019。网址 [`github.com/amzn/MXFusion`](https://github.com/amzn/MXFusion)。

+   Metropolis 等人（1953）**尼古拉斯·梅特罗波利斯**、**阿丽安娜·W·罗森布鲁斯**、**马歇尔·N·罗森布鲁斯**、**奥古斯塔·H·泰勒** 和 **爱德华·泰勒**。通过快速计算机进行状态方程计算。*化学物理学杂志*，21(6)：1087–1092，1953。doi: 10.1063/1.1699114。网址 [`doi.org/10.1063/1.1699114`](https://doi.org/10.1063/1.1699114)。

+   Meyer 等人（2019）**格雷戈里·P·迈耶**、**安基特·拉达**、**埃里克·基**、**卡洛斯·瓦莱斯皮-冈萨雷斯** 和 **卡尔·K·威灵顿**。Lasernet：一种高效的概率性三维物体检测器用于自动驾驶。在 *CVPR*，第 12677–12686 页。计算机视觉基金会 / IEEE，2019。网址 [`dblp.uni-trier.de/db/conf/cvpr/cvpr2019.html#MeyerLKVW19`](http://dblp.uni-trier.de/db/conf/cvpr/cvpr2019.html#MeyerLKVW19)。

+   Mitchell 等人（2019）**玛格丽特·米切尔**、**西蒙·吴**、**安德鲁·扎尔迪瓦尔**、**帕克·巴恩斯**、**露西·瓦瑟曼**、**本·哈钦森**、**埃琳娜·斯皮策**、**伊尼奥鲁瓦·黛博拉·拉吉** 和 **提姆尼特·盖布鲁**。模型卡片用于模型报告。在 *公平性、问责制和透明度会议论文集*，FAT* ’19，第 220–229 页，美国纽约，2019。计算机协会。ISBN 9781450361255。doi: 10.1145/3287560.3287596。网址 [`doi.org/10.1145/3287560.3287596`](https://doi.org/10.1145/3287560.3287596)。

+   Montiel 等人（2020）**雅各布·蒙蒂尔**、**马克斯·哈尔福德**、**绍罗·马尔蒂耶洛·马斯特林尼**、**杰奥夫里·博尔米耶**、**拉斐尔·苏尔蒂**、**罗宾·维斯**、**阿迪尔·祖伊廷**、**海托尔·穆里洛·戈梅斯**、**杰西·里德**、**塔莱尔·阿卜杜萨勒姆** 和 **阿尔贝特·比费**。River：用于流数据的机器学习工具，2020。

+   Navrátil 等人（2021）**吉里·纳夫拉蒂尔**、**本杰明·埃尔德**、**马修·阿诺德**、**苏玛雅·舒布拉·戈什** 和 **普拉萨纳·萨蒂吉里**。不确定性特征曲线：预测区间的系统评估。*ArXiv*，abs/2106.00858，2021。

+   Neal 等人（2011）**拉德福德·M·尼尔** 等人。使用哈密顿动力学的 MCMC。*马尔科夫链蒙特卡洛手册*，2(11)：2，2011。

+   Nguyen 等人（2018）**光阮·V**、**英震·李**、**汤常·D·布伊** 和 **理查德·E·特纳**。变分持续学习。在 *国际学习表征会议*，2018。

+   Nguyen 等人（2019）**江阮**、**斯特凡·杜洛林斯基**、**马丁·博巴克**、**越·陈**、**阿尔瓦罗·洛佩斯·加西亚**、**伊格纳西奥·埃雷迪亚**、**彼得·马利克** 和 **拉迪斯拉夫·赫卢赫**。大规模数据挖掘的机器学习和深度学习框架与库：综述。*人工智能评论*，52(1)：77–124，2019 年 6 月。ISSN 0269-2821。doi: 10.1007/s10462-018-09679-z。网址 [`doi.org/10.1007/s10462-018-09679-z`](https://doi.org/10.1007/s10462-018-09679-z)。

+   Nicolae 等人 (2018) Maria-Irina Nicolae, Mathieu Sinn, Minh Ngoc Tran, Beat Buesser, Ambrish Rawat, Martin Wistuba, Valentina Zantedeschi, Nathalie Baracaldo, Bryant Chen, Heiko Ludwig, Ian Molloy, 和 Ben Edwards. 对抗性鲁棒性工具箱 v1.2.0. *CoRR*, 1807.01069, 2018. URL [`arxiv.org/pdf/1807.01069`](https://arxiv.org/pdf/1807.01069)。

+   Nix & Weigend (1994) D.A. Nix 和 A.S. Weigend. 估计目标概率分布的均值和方差. 在 *1994 年 IEEE 国际神经网络会议论文集 (ICNN’94)* 中, 第 1 卷, 页码 55–60 第 1 卷, 1994. doi: 10/fth5jt。

+   Osawa 等人 (2019) Kazuki Osawa, Siddharth Swaroop, Mohammad Emtiyaz E Khan, Anirudh Jain, Runa Eschenhagen, Richard E Turner, 和 Rio Yokota. 基于贝叶斯原则的实用深度学习. *神经信息处理系统进展*, 32, 2019。

+   Ovadia 等人 (2019) Yaniv Ovadia, Emily Fertig, Jie Ren, Zachary Nado, D. Sculley, Sebastian Nowozin, Joshua V. Dillon, Balaji Lakshminarayanan, 和 Jasper Snoek. 你能相信你模型的不确定性吗？在数据集变化下评估预测不确定性. 在 *第 33 届神经信息处理系统国际会议论文集* 中. Curran Associates Inc., 2019. 页数：12 tex.articleno: 1254。

+   Papakipos & Bitton (2022) Zoe Papakipos 和 Joanna Bitton. Augly: 数据增强以提高鲁棒性, 2022。

+   Paszke 等人 (2019) Adam Paszke, Sam Gross, Francisco Massa, Adam Lerer, James Bradbury, Gregory Chanan, Trevor Killeen, Zeming Lin, Natalia Gimelshein, Luca Antiga, Alban Desmaison, Andreas Kopf, Edward Yang, Zachary DeVito, Martin Raison, Alykhan Tejani, Sasank Chilamkurthy, Benoit Steiner, Lu Fang, Junjie Bai, 和 Soumith Chintala. Pytorch: 一种命令式风格的高性能深度学习库. 在 H. Wallach, H. Larochelle, A. Beygelzimer, F. d'Alché-Buc, E. Fox, 和 R. Garnett (编), *神经信息处理系统进展 32*, 页码 8024–8035. Curran Associates, Inc., 2019。

+   Rasmussen & Williams (2006) Carl Edward Rasmussen 和 Christopher K. I. Williams. *机器学习中的高斯过程*. 自适应计算与机器学习. MIT Press, 2006. ISBN 026218253X。

+   Rezende & Mohamed (2015) Danilo Jimenez Rezende 和 Shakir Mohamed. 使用归一化流的变分推断. 在 *第 32 届国际机器学习会议论文集 - 第 37 卷* 中, ICML’15, 页码 1530–1538. JMLR.org, 2015. 地点：法国里尔 页数：9。

+   Ritter 等人 (2018) Hippolyt Ritter, Aleksandar Botev, 和 David Barber. 神经网络的可扩展拉普拉斯近似. 在 *国际学习表征会议* 中, 2018. URL [`openreview.net/forum?id=Skdvd2xAZ`](https://openreview.net/forum?id=Skdvd2xAZ)。

+   Sensoy 等人 (2018) Murat Sensoy, Lance Kaplan, 和 Melih Kandemir. 证据深度学习以量化分类不确定性. *神经信息处理系统进展*, 31, 2018。

+   Shi et al. (2017) Jiaxin Shi, Jianfei Chen, Jun Zhu, Shengyang Sun, Yucen Luo, Yihong Gu, 和 Yuhao Zhou. ZhuSuan: 一个用于贝叶斯深度学习的库。*arXiv 预印本 arXiv:1709.05870*，2017 年。

+   Sicking et al. (2021) Joachim Sicking, Maram Akila, Maximilian Pintz, Tim Wirtz, Asja Fischer, 和 Stefan Wrobel. Wasserstein dropout，2021 年。URL [`arxiv.org/abs/2012.12687`](https://arxiv.org/abs/2012.12687)。

+   Sicking et al. (2022) Joachim Sicking, Maram Akila, Jan David Schneider, Fabian Hüger, Peter Schlicht, Tim Wirtz, 和 Stefan Wrobel. 针对深度学习系统的定制不确定性估计，2022 年。URL [`arxiv.org/abs/2204.13963`](https://arxiv.org/abs/2204.13963)。

+   Sommerville (2010) Ian Sommerville. *软件工程*。Addison-Wesley，哈罗英国，第 9 版，2010 年。ISBN 978-0-13-703515-1。

+   Srivastava et al. (2014) Nitish Srivastava, Geoffrey Hinton, Alex Krizhevsky, Ilya Sutskever, 和 Ruslan Salakhutdinov. Dropout：防止神经网络过拟合的简单方法。*机器学习研究期刊*，15(1):1929–1958，2014 年。

+   Thiagarajan et al. (2020) Jayaraman J. Thiagarajan, Bindya Venkatesh, Prasanna Sattigeri, 和 Peer-Timo Bremer. 通过与辅助区间预测器的不确定性匹配构建校准深度模型。见于 *AAAI*，2020 年。

+   Torfi et al. (2020) Amirsina Torfi, Rouzbeh A Shirvani, Yaser Keneshloo, Nader Tavaf, 和 Edward A Fox. 深度学习推动的自然语言处理进展：一项调查。*arXiv 预印本 arXiv:2003.01200*，2020 年。

+   Tran et al. (2016) Dustin Tran, Rajesh Ranganath, 和 David M Blei. 变分高斯过程。见于 *第 4 届国际学习表征大会，ICLR 2016*，2016 年。

+   Tran et al. (2018) Dustin Tran, Matthew D. Hoffman, Dave Moore, Christopher Suter, Srinivas Vasudevan, Alexey Radul, Matthew Johnson, 和 Rif A. Saurous. 简单、分布式和加速的概率编程。见于 *神经信息处理系统*，2018 年。

+   van de Meent et al. (2018) Jan-Willem van de Meent, Brooks Paige, Hongseok Yang, 和 Frank Wood. 概率编程导论。*arXiv 预印本 arXiv:1809.10756*，2018 年。

+   Vyas et al. (2018) Apoorv Vyas, Nataraj Jammalamadaka, Xia Zhu, Dipankar Das, Bharat Kaul, 和 Theodore L Willke. 使用自监督留出分类器的分布外检测。见于 *欧洲计算机视觉大会（ECCV）*，第 550–564 页，2018 年。

+   Wang et al. (2019) Zhaobin Wang, Ke Liu, Jian Li, Ying Zhu, 和 Yaonan Zhang. 机器学习和深度学习的各种框架和库：一项调查。*计算方法工程档案*，2019 年 2 月。doi: 10.1007/s11831-018-09312-w。

+   Weiss & Tonella (2021) Michael Weiss 和 Paolo Tonella. Uncertainty-wizard: 快速且用户友好的神经网络不确定性量化。见于 *2021 年第 14 届 IEEE 软件测试、验证与验证会议（ICST）*，第 436–441 页。IEEE，2021 年。

+   Welling & Teh (2011) Max Welling 和 Yee Whye Teh. 通过随机梯度朗之万动力学的贝叶斯学习。发表于*第 28 届国际机器学习大会论文集*，ICML’11, pp. 681–688, 麦迪逊, WI, USA, 2011. Omnipress. ISBN 9781450306195.

+   Wen 等人 (2019) Yeming Wen, Dustin Tran 和 Jimmy Ba. Batchensemble：一种高效的集成和终身学习的替代方法。发表于*国际学习表征大会*，2019.

+   Yurtsever 等人 (2020) Ekim Yurtsever, Jacob Lambert, Alexander Carballo 和 Kazuya Takeda. 自主驾驶调查：常见做法与新兴技术。*IEEE Access*, 8:58443–58469, 2020. doi: 10.1109/ACCESS.2020.2983149.

+   Zacharias 等人 (2018) Jan Zacharias, Michael Barz 和 Daniel Sonntag. 智能用户界面的深度学习工具包与库调查。*CoRR*, abs/1803.04818, 2018. URL [`arxiv.org/abs/1803.04818`](http://arxiv.org/abs/1803.04818).

+   Zhao 等人 (2020) Shengjia Zhao, Tengyu Ma 和 Stefano Ermon. 基于随机预测的个体校准。发表于*国际机器学习大会*，pp. 11387–11397. PMLR, 2020.

## 附录

### 6.1 不确定性建模与评估的详细概述

以下部分提供了关于深度学习中不确定性估计的文献综述，描述了不确定性的来源、估计和评估的不确定性方法及其应用。它提供了第二部分中“不确定性估计的元素”段落的进一步细节。

神经网络存在几种不确定性（Hüllermeier & Waegeman, 2021）。我们通常不知道所选择的神经网络模型是否最适合给定任务。此外，优化过程还会引入近似误差（例如由于（次优的）超参数选择、随机初始化、数据不足等）。这些因对给定任务的最优模型缺乏了解而产生的不确定性被统称为认识不确定性，它在理论上可以通过选择更好的模型或提供更多的训练数据来减少。此外，还有不可减少的随机不确定性，即由本质上随机的因素引起的训练过程结果的随机性，最重要的是数据（例如传感器噪声、标签错误的输入或信息不完善）。除了用于量化预测和估计的方差外，不确定性估计也被探索用于辅助任务，如检测分布外的输入（Ovadia et al., 2019; Vyas et al., 2018）、主动学习（Gal et al., 2017; Beluch et al., 2018）、对抗样本检测（Ritter et al., 2018; Amini et al., 2020）和持续学习（Osawa et al., 2019; Nguyen et al., 2018）。深度不确定性估计的主要工具是概率分布，通常是网络输出的分布。期望值作为主要的网络预测，而不确定性则通过方差、分位数或熵来量化。不确定性估计的方法包括以下几种（详见 Gawlikowski et al. (2021) 的综合调查）：

+   •

    在参数化似然（PL）方法中，网络输出的是分布参数而非点估计，通过似然优化进行训练（Nix & Weigend, 1994; Amini et al., 2020; Sensoy et al., 2018）。这些方法通常用于估计随机不确定性，并且与其他方法结合以同时纳入认识不确定性（Kendall & Gal, 2017）。

+   •

    贝叶斯神经网络（BNNs）扩展了参数化似然方法，通过基于贝叶斯规则估计后验和预测分布来引入（认识上的）不确定性。针对深度学习（DL）考虑了不同的后验估计程序，包括变分推断（VI-BNNs, Graves (2011); Blundell et al. (2015); Rezende & Mohamed (2015))，其中 dropout 采样（Gal & Ghahramani, 2016; Kingma et al., 2015）是一个重要的变体，期望传播（Hernández-Lobato & Adams, 2015; Gast & Roth, 2018），马尔可夫链蒙特卡洛采样（MCMC, Neal et al. (2011); Welling & Teh (2011); Li et al. (2016)) 或拉普拉斯近似（MacKay, 1992; Ritter et al., 2018）。高斯过程（GP, Rasmussen & Williams (2006)) 是一种相关的贝叶斯方法，它在更一般的函数空间中引入不确定性，而不是网络的参数空间。标准 GP 对于大规模模型在计算上不可行。然而，存在可扩展的变体（Hensman et al., 2013），这些变体甚至可以用作可微分网络组件（Tran et al., 2016）以及深度学习模型中 UE 的构建块（Liu et al., 2020）。

+   •

    频率主义方法直接利用不同模型的组合来进行不确定性估计。常见的方法基于集成方法（Lakshminarayanan et al., 2017; Wen et al., 2019; Durasov et al., 2021)) 或者切除法（Giordano et al., 2019; Alaa & Van Der Schaar, 2020; Kim et al., 2020)。

不确定性方法可以进一步分类为：（i）内在方法，这些方法将不确定性估计直接集成到架构或训练过程中（例如，集成训练（Lakshminarayanan et al., 2017）和基于 dropout 的方法（Gal & Ghahramani, 2016; Kendall & Gal, 2017; Fan et al., 2021; Sicking et al., 2021）），（ii）后处理方法，这些方法扩展标准深度学习模型（例如，拉普拉斯近似、微小切除、代理模型（Chen et al., 2019））以及（iii）重新校准方法，这些方法旨在改进现有的不确定性估计（Guo et al., 2017; Kuleshov et al., 2018; Navrátil et al., 2021）。

现在我们讨论几种评估不确定性估计质量的技术。

+   •

    （适当的）评分规则是逐点度量，用于衡量预测分布与真实值的拟合程度，通常在保留的验证数据集上进行评估。常见的评分规则包括布雷尔分数、负对数似然（NLL）、连续排名概率分数（CRPS）或区间分数（见 Gneiting & Raftery (2007)）。

+   •

    信心校准衡量的是信心估计与验证数据集的对齐程度（例如，$90\%$ 的信心区间应包含 $90\%$ 的正确标签）。校准可以通过可靠性图或曲线（Guo et al., 2017; Navrátil et al., 2021）在视觉上进行评估，这些图表绘制了信心水平与正确性指标（例如分类准确性）之间的关系。定量指标通常考虑上述曲线下的面积，最著名的是预期校准误差（ECE）（Guo et al., 2017; Kuleshov et al., 2018）。对抗性组校准（Zhao et al., 2020）是一种更严格的校准评估变体，它考虑了信心估计与数据集每个子集的对齐程度，而不仅仅是整个数据集。

+   •

    不确定性估计也可以通过定性方式进行评估，例如通过视觉检查预测分布、信心区间与真实值的关系。考虑数据集中的平均不确定性（也称为锐度）在校准评估中至关重要，正如 Kuleshov et al. (2018) 所讨论的那样。

+   •

    辅助分数衡量不确定性估计在辅助任务中的表现，如异常检测。标准的评估方法包括二分类阈值分类器（例如，区分真阳性与假阳性）的精确度-召回率和接收者操作特征曲线用于视觉评估，或计算平均精确度或 AUCROC 分数。另一种方法是比较来自每个类别（例如，分布内或分布外）的不确定性估计（例如，方差或预测熵）的直方图，正如 Ovadia et al. (2019) 所做的那样。

### 6.2 选择的不确定性工具包的比较分析

本节提供了两个表格，包含有关工具包的附加信息。表格 1 列出了所有工具包及其许可证、预期用途和在本次调查中考虑的确切版本。表格 2 提供了我们分析结果的简要总结，来自第五部分。

表 1：所考察的不确定性估计工具包的一般信息。所有工具包均使用 Python 作为编程语言。对于没有版本号的情况，我们提供 GitHub 提交号。

| UE 工具包 | 开发者 | 许可证 | 版本/提交 | 基础库/框架 | 工具包类型 |
| --- | --- | --- | --- | --- | --- |
| TFP | Dillon 等人 (2017)（Google Brain） | Apache-2.0 | `0.15.0` | Tensorflow/ Keras | PPL |
| Pyro | Bingham 等人 (2019)（Uber AI Labs） | Apache-2.0 | `1.8.0` | Pytorch, JAX | PPL |
| MXF | Meissner 等人 (2019)（Amazon Web Services） | Apache-2.0 | `0.3.1` | MXNet | PPL |
| ZS | Shi 等人 (2017) | MIT | `4386b2a` | Tensorflow | PPL |
| ED2 | Tran 等人 (2018)（Google Brain） | Apache-2.0 | `f420d83` | Tensorflow/ Keras | PPL |
| GTS | Alexandrov 等人 (2020)（Amazon Web Services） | Apache-2.0 | `0.9.0` | MXNet, Pytorch | 时间序列 |
| UQ360 | Ghosh 等人 (2021)（IBM Research） | Apache-2.0 | `2378bfa` | Pytorch | 专用 UE |
| UT | Chung 等人 (2021) | MIT | `v0.1.0` | Scipy, Scikit-learn | 专用 UE |
| UW | Weiss & Tonella (2021) | MIT | `v0.2.0` | Tensorflow/ Keras | 专用 UE |
| BT | Krishnan 等人 (2022)（Intel Labs） | BSD3 | `99876f3` | Pytorch | 专用 UE |
| KADF | Maces & Contributors (2019) | MIT | `19.1.0` | Tensorflow/ Keras | 专用 UE |

表 2：在第三部分中选择的不确定性工具包的分析总结。顶部表格考虑了所有工具包相对于我们的核心标准（参见 第四部分）。底部表格提供了额外标准，并考虑了相对于核心标准的三种表现最佳的工具包。“标准统计”指的是一般的（样本）度量，如方差、分位数或相关性。

| UE 工具包 | 支持的不确定性方法范围 | 支持的评估技术范围 | 支持的架构和数据结构范围 |
| --- | --- | --- | --- |
| TFP | • 内在（PL, VI-BNN, GP, MCMC） • 支持的分布范围广 | • 广泛的标准统计 • 评分规则（NLL, Brier） • 分类校准（ECE） | • 回归、分类、序列 |
| Pyro | • 内在（PL, VI-BNN, GP, MCMC） • 支持的分布范围广 | • 标准统计 • 评分规则（NLL, CRPS） | • 回归、分类、序列 |
| ED2 | • 内在（PL, VI-BNN, GP, MCMC） • 支持的分布范围广 | • 狭窄的评分规则范围（NLL） | • 回归、分类、序列 |
| ZS | • 内在（PL, VI-BNN, MCMC） • 支持的分布范围广 | • 标准统计范围窄 • 评分规则范围窄（NLL） | • 回归、分类、序列 |
| MXF | • 内在（PL, VI-BNN, GP） | [无] | • 回归、分类 |
| GTS | • 内在（PL） | • 评分规则 • 置信区间绘图函数 | • 序列 |
| UQ360 | • 内在（PL, VI-BNN, 集成） • 后验（基于切片的，代理模型） • 再校准 | • 评分规则 • 校准评估（ECE） • 绘图功能 | • 回归、分类 • 表格输入 • 内在方法灵活性低 |
| UT | • 基本再校准 | • 广泛的评分规则 • 校准评估（ECE, AGC） • 绘图功能 | • 1D 回归 |
| UW | • 内在（集成，dropout） | [无] | • 回归、分类 • 自定义不确定性量化器 |
| BT | • 内在（VI-BNN） | [无] | • 回归、分类、递归 |
| KADF | • 内在（VI-ADF） | [无] | • 回归、分类 |

缩写：PL：参数似然，VI-BNN：基于变分推断的贝叶斯神经网络，GP：高斯过程，VI-ADF：假设密度过滤贝叶斯神经网络（期望传播的一种变体），MCMC：基于马尔科夫链蒙特卡罗的后验采样方法，AGC：对抗组校准（Zhao et al., 2020）

| UE 工具包 | 与深度学习框架集成 | 软件质量 |
| --- | --- | --- |
| TFP | • TensorFlow 生态系统的一部分 • 与 keras 模型 API 高集成 | • 代码质量高 • 持续测试 • 文档详尽 |
| Pyro | • 基于 pytorch 的实现 • 模型/推断过程可以封装为 torch 模块 | • 代码质量高 • 持续测试 • 文档详尽 |
| UQ360 | • 基于 pytorch 的实现 • 可以将自定义 pytorch 模型传递给某些模块 | • 简单、易用的类似 sklearn 的 API • 文档详尽，提供关于不确定性方法/指标的用户指导 |
