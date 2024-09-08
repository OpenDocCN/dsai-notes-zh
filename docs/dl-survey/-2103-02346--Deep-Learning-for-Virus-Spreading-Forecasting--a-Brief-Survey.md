<!--yml

分类：未分类

日期：2024-09-06 19:56:33

-->

# [2103.02346] 深度学习用于病毒传播预测：简要综述

> 来源：[`ar5iv.labs.arxiv.org/html/2103.02346`](https://ar5iv.labs.arxiv.org/html/2103.02346)

# 深度学习用于病毒传播预测：简要综述

Federico Baldo¹    Lorenzo Dall’Olio¹    Mattia Ceccarelli¹    Riccardo Scheda¹    Michele Lombardi^(1,2)    Andrea Borghesi^(1,2)    Stefano Diciotti^(1,2)&Michela Milano^(1,2)

¹博洛尼亚大学

²阿尔玛母校人本人工智能研究所

{federico.baldo2, lorenzo.dallolio4, riccardo.scheda2, mattia.ceccarelli5, michele.lombardi2, andrea.borghesi3, stefano.diciotti, michela.milano}@unibo.it

###### 摘要

新冠疫情的到来激发了对能够预测病毒传播的预测模型的兴趣，特别是为了促进和支持决策过程。本文将概述主要的深度学习方法，旨在预测疾病在空间和时间上的传播。目的是展示该领域的新兴趋势，并提供对解决该问题可能策略的一般视角。在此过程中，我们将主要关注两个宏观类别：经典深度学习方法和混合模型。最后，我们将讨论不同模型的主要优缺点，并强调改进这些方法的最有前景的发展方向。

## 1 引言

21 世纪的特点是全球互联互通的不断增加，这一方面为人类活动和技术进步创造了新的可能性，另一方面也为新病原体的迅速传播铺平了道路。许多科学报告将环境入侵性的人类活动与新型人畜共患病毒的出现联系起来 Bengis et al. (2004)。其中，空气传播的疾病最令人担忧，因为它们具有快速传播的能力（如 SARS、MERS、H1N1）。尤其值得注意的是，最近爆发的 Sars-CoV-2 Velavan 和 Meyer (2020)，于 2020 年（可能甚至 2019 年）在中国武汉首次出现，给我们的社会带来了巨大挑战。

因此，能够预测病毒短期和长期动态的预测系统的存在对抗击疫情至关重要。关于适当遏制病毒传播的政策决策过程依赖于准确的预测系统，因为它们可以评估不同的情景和干预计划。为此，过去开发了许多流行病学模型来近似疾病的动态 Duan et al. (2015)。然而，鉴于近期计算能力的提升，新可能性正在出现。

近年来，我们见证了机器学习（ML）在创建预测模型方面的蓬勃应用。通过信息和通信技术，特别是智能手机和社交媒体，获得的大量信息推动了研究向基于 ML 的预测模型发展。在这些模型中，深度学习（DL）因其适应各种问题的能力，已被证明是最有效的工具之一。

在本次调查中，我们重点关注 DL 模型在近似疾病动态和生产能够预测空气传播病毒扩散的预测系统方面的应用。我们决定尽可能广泛地考虑相关疾病。然而，不可忽视的是最近关于 COVID-19 的众多研究。尽管如此，如果做出适当修改，本论文中概述的方法可以应用于任何疾病。

我们的目标之一是提供一种可以部署以解决此问题的不同 DL 方法的通用分类法。相关的科学文献主要有两个方向：一个是专注于纯 DL 模型的应用，无论是简单使用还是结合不同的人工神经网络（ANN），以最小化假设或人为干预进行预测；另一个方向则尝试将成熟的流行病学方法与 DL 结合，利用数十年的模型和见解，产生更具解释性的预测。特别是，第二类方法依赖于将特定领域的知识嵌入预测模型中的理念，这在 ML 领域中是一种新趋势。这种方法的基本原则是将先前的信息或技术整合到学习过程中，以提高性能并建立定制模型（例如，端到端学习）。

本文其余部分结构如下：在第二部分，我们简要讨论流行病学数据；接着，我们将对不同方法进行比较修订：流行病的深度学习（第三部分）和流行病的混合深度学习（第四部分）；接下来，在第五部分，我们将讨论并比较前述节中介绍的方法；第六部分总结了论文。

## 2 流行病学数据

深度学习是一种数据驱动的方法，因此其性能依赖于准确和一致的数据。因此，数据收集策略在处理学习任务时具有高度相关性。从这个角度来看，新冠疫情使得我们能够收集大量信息，成为智能手机和大数据系统时代的首个全球性疫情。

我们可以区分两类关于病毒的数据，这隐含地定义了不同的学习目标：临床数据，描述疾病的医学方面（例如，医院记录、症状、药物使用），以及时空数据，描述病毒的传播情况，通常以感染、康复和死亡的个体为单位。许多科学综述历史上重点关注第一类数据 Baldominos et al. (2020)，而在本文中我们将仅关注第二类数据，研究近似病毒动态和预测其传播的技术。

除了与疾病直接相关的数据外，描述疫情的背景信息可能有助于提高预测模型的准确性。例如，特定区域温度趋势的知识可能增加捕捉病毒季节性行为的机会（如果存在的话），而关于人口密度的信息则有助于识别个体之间接触率较高的场景，从而增加感染的可能性。此外，由于一些病毒具有高度传染性以及跨境人口流动频繁，大多数疫情中，各国不能被视为孤立的。因此，关于邻国的信息可以显著改善对疫情的理解。

我们还将考虑哪些技术可以用于获取关于病毒传播的数据。在主要信息来源中，我们可以区分以下几类：

+   •

    政府和健康记录：政府、医院管理部门和健康组织可以自愿公开关于公民的记录，这些记录可能是公开的，也可能是针对特定项目的。例如，疾病控制中心（CDC）已经发布了有关季节性流感的记录 Adhikari et al. (2019)。

+   •

    移动数据：智能手机在我们生活中的普及使得收集关于我们的习惯、个人移动和接触模式的信息变得更加容易 Oliver et al. (2020)，这为流行病控制和病毒传播预测提供了有价值的信息。

+   •

    社交媒体和搜索引擎：随着智能手机的使用增加，社交媒体和搜索引擎可以成为重要的信息来源，从报告的症状（从公共帖子中推断）到搜索查询。一个有趣的例子是 Santos 和 Matos (2014)中展示的，其中使用了 Twitter 消息和网络查询来估计流感趋势。

+   •

    传感器：信息还可以通过使用特定的硬件或传感器来收集，如 Sareen et al. (2018)所示，其中使用射频识别（RFID）技术来收集有关个体在小环境中接触的数据，然后重建可能的感染链。

数据收集基础设施的存在改善了研究中数据的数量和质量。然而，对于这些系统对人类隐私和个人自由可能带来的后果，存在许多问题，并且对这些系统的更严格规则和安全设计的需求不断增加（Simko et al. 2020）。

最终，深度学习模型的质量依赖于可用数据的数量，但不幸的是，信息可能会稀缺，特别是在流行病的初期阶段。一些作者特别针对这个问题提出了数据增强方法，如 Wang et al. (2020a)中提出的，或利用历史数据的智能策略，如 Adhikari et al. (2019)中提出的。

## 3 深度学习在流行病中的应用

在科学文献中，我们可以区分应用深度学习预测病毒传播的两个主要趋势。特别是，一方面，许多研究人员应用了传统且成熟的深度学习方法，并对超参数进行了一些微调（我们将这些技术称为 vanilla）。另一方面，我们观察到复合方法的使用越来越成功，这些方法整合了多种类型的人工神经网络（ANN），以建模流行病的不同方面，从而间接利用已知的物理现象机制。

### 3.1 Vanilla 深度学习

在本节中，我们回顾了传统深度学习方法在预测流行病学中的应用。在这里，我们观察到两种观点的流行：一方面，应用历史上设计用于建模序列数据的技术，因此特别适合处理时间数据（即时间序列）；另一方面，将深度学习方法应用于空间信息的实现，以处理时间信息。

#### 递归神经网络。

传统上，这类方法由于其结构和开发长期记忆的能力，被广泛应用于近似传染病的动态（以及更一般的顺序数据）。在 RNN 家族中，我们包括长短期记忆网络（**LSTM**）和门控递归单元（**GRU**），它们特别适用于时间序列。RNN 的标准应用涉及通过根据回溯天数（即在进行预测时作为输入的过去天数）安排每个特征来构建一个适当的数据集。这允许在预测过程中融入有关流行病曲线的一般趋势的信息。

RNN 的一个近期应用可以在 Shahid 等人（2020）的研究中看到，作者使用 LSTM 和 GRU 对不同国家的 COVID-19 疫情数据（即感染、死亡和恢复病例的数量）进行了建模，结果表明这些方法在历史数据的预测准确性方面优于传统的机器学习方法，如支持向量回归（**SVR**）、径向基函数（**RBF**）核和自回归积分滑动平均（**ARIMA**）。在同一研究中，作者通过使用双向 LSTM（**Bi-LSTM**）来提高模型开发长期记忆的能力。尽管经典的 RNN 方法按特定顺序处理顺序数据，即从过去到未来，Bi-LSTM 允许信息在时间序列的两个方向（即过去-未来，未来-过去）流动，从而提高了性能，也相对于 LSTM 和 GRU。

在 Shastri 等人（2020）的研究中，提出了一种进一步应用 LSTM 于流行病数据的方法。这个想法是堆叠多个 LSTM 层，每个中间层的输出作为下一个层的输入，从而生成更复杂和更深的模型。这种方法被称为堆叠 LSTM（**Stacked-LSTM**），由于其通过层的分层化提高了对输入的抽象能力，因此显著提高了性能。

尽管递归网络可以准确地逼近时间序列，但它们通常不包含可能对一致捕捉病毒动态相关的上下文信息，如空间或季节数据。这个问题在 Venna 等人（2019）的研究中得到了直接解决，作者提出了一种基于 LSTM 的方法，结合了地理邻近信息和气候变量（例如湿度、温度、降水量）来预测人群中的流感病例数量。该方法分为两个步骤：第一阶段，LSTM 神经网络在流感时间序列上进行训练；第二阶段，将气候变量的影响和时空调整添加到 LSTM 模型估计的流感计数中。通过对变量进行线性组合，并与实际预测的每日新病例数量相乘，将上下文特征集成到学习过程中。

#### 卷积神经网络（CNN）。

这种深度学习工具是处理输入数据空间邻近性的最广泛使用的方法之一。这些方面在预测流行病学趋势时非常有用。由于 CNN 在处理空间邻近性方面已被证明有效（通过提取嵌入空间位置的特征），它们也可以用于处理时间邻近性，例如在有序序列数据的情况下。

大多数基础 CNN 应用依赖有序时间序列作为输入，并要求模型预测序列中的下一个数据点；然而，CNN 通常容易对历史数据过拟合。然而，在存在较差的上下文数据时，这种方法可能足以超越 LSTM 或更简单的算法，如决策树（DT）（Kunjir 等人，2020）。通过向模型输入多个相关的时间序列，可以改进预测。例如，在 Huang 等人（2020a）的研究中，作者使用了确诊、死亡和康复病例的数据来预测每日感染数量。CNN 与 LSTM、GRU 和 MLP 模型在 7 个不同的中国城市进行了比较，显示出相对于其他模型，尤其是 MLP，具有更小的准确性误差。

一种利用卷积神经网络（CNN）的方法，在预测流行病学领域尚未得到充分探索，是**时间卷积网络（TCN）**，其表现与循环神经网络（RNN）相当，甚至更好。该方法最初由 Lea 等人（2016）提出，基于因果卷积用于序列到序列学习任务。在这种方法中，卷积核仅应用于当前时间步或序列中的前几个输入点的数据，避免了从未来到过去的信息泄漏。网络架构基于与输入数据长度相同的一维全卷积层。这种方法正受到深度学习社区的越来越多关注，我们认为它在未来的流行病预测系统研究中是一个有价值的方向。

### 3.2 组合深度学习模型

在许多情况下，结合多种基于深度学习（DL）的方法可以大大提高最终预测的准确性。例如，集成一个近似时间特征的模型和一个封装空间特征的模型，可以提升整体性能。因此，近年来提出了大量集成一种或多种深度学习方法的工作。

#### 递归网络自编码器。

在预测流行病学领域中，有一组有趣的基于深度学习的方法，使用了所谓的**LSTM 自编码器**。一般来说，自编码器由两个部分组成：一个编码器，它创建输入序列的内部表示，即用于建模序列的 LSTM 单元的内部状态，以及一个解码器，它将嵌入映射到输出特征空间（即，通过一系列密集层来最小化重建损失）。

这种方法的一个应用在 Adhikari 等人（2019）中提出，在流感视野任务¹¹1[`www.citizenscience.gov/catalog/171/`](https://www.citizenscience.gov/catalog/171/)的背景下进行了应用，这是 CDC 发起的一个挑战，旨在推进关于季节性流感预测的研究。提出的模型基于过去 20 年的季节性流感历史数据进行训练。作者实现了一个基于 LSTM 与注意力机制配对的系统，将历史数据嵌入到潜在空间中，而解码器则执行实际的预测。当前流感季节的趋势数据通过潜在空间上的深度聚类技术与最相似的历史系列嵌入匹配。历史流行病曲线被重建，并用于预测正在进行的流感爆发的演变。

另一个例子是由 Ibrahim 等人提出的，灵感来自变分自编码器（Variation Autoencoder）（2020）。该模型基于一个变分 LSTM 自编码器，由并行训练的两个分支组成。第一个分支是一个自注意力 LSTM 编码器，其输入是每日的新感染病例，以及政府政策和城市特征（人口密度、生育率等）。第二个分支是一个编码器，其输入是使用国家地理位置计算的距离加权邻接矩阵。编码器的输出是一组潜变量，这些变量与第一个分支的输出连接起来，并传递给一个 LSTM，输出每个国家每日病例的预测。

#### 结合递归和卷积神经网络。

我们在前一节中看到，RNNs 和 CNNs 都可以成为模拟疾病动态的合适选择。在 Shastri 等人中提出了一种同时结合这两种方法的应用，即 Convolutional LSTM (Conv-LSTM) (2020)。该模型由一个堆叠的 LSTM 组成，其中每一层都不是传统的矩阵乘法，而是交替使用卷积算子。该模型与其他 RNNs 方法进行了比较，包括 Bi-LSTM 和 Stacked-LSTM，显示了更高的准确性。

在同一行上，黄等人提出了一种结合时间信息（即 1D 时间序列）和邻近国家疾病动态等空间信息的方法（Huang et al.，2020b）。该模型结合了两个不同流水线的结果：第一个流水线以过去 5 天的新每日恢复病例、死亡病例、确诊病例和累积计数作为输入。这些输入被串行地输入到一个 1D-CNN 中，再结合一个双向 GRU 来提取输入趋势的时间模式。第二个流水线，给定代表不同地区流行趋势的 2D 矩阵，通过使用 2D-CNN 提取空间相关模式。这样的输入矩阵模拟了流行趋势中高度相关和依赖的邻近国家的存在。最终，两个流水线的输出被连接起来，并使用一个辍学层来防止数据稀缺时的过拟合。

吴等人（2018）提出了一种类似的方法用于流感疫情。研究人员考虑了美国和日本的数据，即每个州或地区的每周报告患者数量。在这项工作中，作者使用了卷积神经网络（CNNs）来融合来自不同数据源（例如，不同地区）的信息，并使用了门控递归单元（GRUs）来捕捉时间序列中的长期相关性，并结合了残差结构。残差结构的采用是为了引入信息流中的高度相关的长跳跃（例如，捕捉年度流行病学模式）。我们可以观察到，CNNs 被用来学习信号之间的相关性，而 GRUs 则关注每个单一信号中的相关性。然而，这项工作中真正创新的解决方案是使用相邻最近邻矩阵作为每个国家卷积核的滤波器。这种相邻卷积使得参数更加关注局部信息，与传统的网格卷积相对，这意味着单个滤波器能够表示更复杂的模式，而这些模式通常需要多个滤波器在使用传统网格卷积时来捕捉。

#### 图神经网络

几何深度学习，更具体地说，图神经网络（GNNs），在许多研究领域取得了显著成果。尽管 GNNs 在计算流行病学中的应用目前仍有限，我们认为它是病毒传播预测中最有前途的框架之一。许多传统的流行病学模型已经部署了复杂网络来描述流行病的动态。因此，GNNs 能够将这一原理扩展到这样的数据结构上。基于此，我们认为一个非常有前途的方向是探索 GNNs，明确地建模编码流行病传播核心的拓扑关系的图结构（例如，人际互动、地理分布等）。

Mežnar 等人（2021）研究了多种图神经网络（GNNs）在该问题上的应用，其中测试了这种方法的多种变体在合成数据集上的表现。主要思想是从一个可以以特定方式相互作用的个体网络（即节点）开始建模传播。然后，通过节点回归来近似将顶点映射到表示感染节点数量的正实数的函数，假设在人群中存在一些初始感染。这种方法可以基于纯粹的 GNNs，也可以基于命题学习者，其中第一种在模型训练过程中使用相邻矩阵，而第二种则不使用。节点回归最终实现了基于图的方法，例如图注意力网络（Graph Attention Networks）和图同构网络（Graph Isomorphic Networks），或者梯度提升模型，即 XGBoost。

这种方法应用的另一个例子由邓等人提供（2020），即 Cola-GNN，一个旨在产生可靠长期流行病预测的模型。Cola-GNN 是最早将图神经网络应用于流行病预测的原创工作之一。该框架由三个主要组件组成：一个位置感知注意力元素，通过 RNN 捕捉空间局部依赖，一个时间卷积层，负责近似时间特征，以及一个全局图神经网络，它封装了前两个层的输出，并以消息传递的方式更新节点，模拟病毒的传播。

## 4 混合深度学习在流行病中的应用

深度学习在不同领域的广泛应用催生了一类新型模型：特别地，我们在这里指的是一类方法，通过采用特定领域的技术来引导学习过程，从而提高模型的可解释性和准确性。这一现象也涉及到旨在预测流行病演变的模型。

### 4.1 自回归集成

在逼近时间序列的最常用方法中，自回归模型（AR）是一种。这类模型提供了多种定制化解决方案，捕捉序列数据的不同方面，如向量自回归模型（VAR）、自回归积分滑动平均（ARIMA）和季节性 ARIMA（SARIMA）。AR 的关键思想是利用过去的信息来预测未来，更具体地说，是预测变量的线性组合。虽然这些方法在流行病数据的情况下已经证明有效，但 AR 技术的固有特性通常不适合捕捉特征中的非线性。许多研究直接解决了这个问题，主要是将 AR 和深度学习结合在一起，以集成的方式减轻它们各自的缺陷。在 Chakraborty 等人（2019）和 Wei 等人（2016）的研究中，重点正是逼近数据的线性和非线性方面；这是通过将 ARIMA 模型和神经自回归网络（NNAR）结合在残差上来实现的。王等人（2020b）提出了这一方法的略微改进版本，依赖于 SARIMA 模型，该模型明确地封装了季节性成分。AR 和 DL 的融合在预测准确性上相对于传统方法显示出稳定的改进。然而，这些模型仅考虑数据的时间组件，而使用上下文信息和空间数据可能对获得高质量预测至关重要。王等人（2019）提出了朝这个方向迈出的一步，其中基于 SARIMA 的方法通过将外生输入整合到训练过程中进行了改进，这些输入是指与学习目标没有直接关系但会影响它的一组变量或序列。

### 4.2 区隔模型

最近，基于人工神经网络（ANN）的方法的发展趋势依赖于领域特定知识的整合 Muralidhar 等人 (2018)。其总体思路是设计学习过程，结合特定领域某些方面的数据和技术。在预测流行病学的情况下，这一趋势已经在结合分 compartmental 模型和深度学习的混合方法中体现出来。历史上，许多关于病毒传播的预测方法已被提出 Duan 等人 (2015)。其中最显著的是 compartmental 模型，即将人口分为表示不同流行病状况的类别的数学模型，并通过微分方程（例如 SIR：易感-感染-恢复）描述病毒的传播。

在 Farooq 和 Bazaz (2020) 的研究中，这一思路被应用于预测印度 COVID-19 疫情的演变。更具体地说，提出的框架基于 SIRVD（易感-感染-恢复-接种-死亡）动态系统，该系统通过增量学习方法来逼近流行病曲线；描述不同 compartment 的过渡的参数通过增量学习方法获得。这个思路是使用前馈神经网络（FFNN）来迭代逼近输入数据，这些数据会根据疫情的发展进行更新；这允许在每次数据更新时，无需对整个数据集进行 ANN 训练，从而提高模型的表现。类似地，Jo 等人 (2020) 提出了用于 SIR 模型的前向-逆向神经网络。这一解决方案可以视为一种端到端的方法，其中每个时间步骤的参数和 compartment（或类别，如感染个体）由基于 COVID-19 在韩国历史数据的时间依赖 FFNN 进行估计。该模型展示了使用混合框架所带来的可解释性上的收益。

王等人（2020a）引入了另一种利用隔室系统的模型。在这种情况下，提出的方法旨在通过数据增强框架解决与稀缺数据相关的问题，用于预测美国的流感样疾病（ILI）发病率。这个模型被称为基于理论引导的深度学习流行病预测与合成信息（TDEFSI），它结合了深度神经网络的优势和对复杂网络中流行病过程的高分辨率模拟。数据增强是通过生成合成数据来完成的，这些合成数据是利用计算机模拟的因果过程捕捉流行病动态生成的：例如，给定一个美国州和一个现有的疾病模型（如易感-暴露-感染-恢复模型），对模型中的每个参数估计一个边际分布。然后，通过从学习到的边际分布中采样，为目标美国州生成一个合成训练数据集。核心模型由一个双分支的 LSTM 深度神经网络组成，该网络捕捉季节内观察和季节间观察的时间动态。该方法的主要优势在于能够基于流行病学理论从模拟中合成大量时间序列，从而减少在训练模型时的过拟合风险。同时，这种方法也带来了最小化合成数据与真实数据之间差距的挑战，这本身就是一个非平凡的问题。

| 分类 | 子类别 | 论文 | 类型 | S | E | C | OD | MR | DA | X |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 深度学习 | 简单 | Shahid 等人（2020） | Bi-LSTM |  |  |  |  |  |  |  |
|  |  | Venna 等人（2019） | LSTM |  |  |  |  |  |  |  |
|  |  | Kunjir 等人（2020） | CNN |  |  |  |  |  |  |  |
|  |  | Shastri 等人（2020） | Conv-LSTM |  |  |  |  |  |  |  |
|  |  | Huang 等人（2020a） | CNN |  |  |  |  |  |  |  |
|  | 组合 | Adhikari 等人 (2019) | AE + LSTM + 聚类 |  |  |  |  |  |  |  |
|  |  | Shastri 等人 (2020) | Conv-LSTM |  |  |  |  |  |  |  |
|  |  | Ibrahim 等人 (2020) | VAE + LSTM |  |  |  |  |  |  |  |
|  |  | Huang 等人 (2020b) | CNN + Bi-GRU |  |  |  |  |  |  |  |
|  |  | Wu 等人 (2018) | CNN + GRU |  |  |  |  |  |  |  |
|  |  | Mežnar 等人 (2021) | GNN |  |  |  |  |  |  |  |
|  |  | Deng 等人 (2020) | GNN + RNN + CNN |  |  |  |  |  |  |  |
| 混合深度学习 | 自回归 | Chakraborty 等人 (2019) | ARIMA + NNAR |  |  |  |  |  |  |  |
|  |  | Wei 等人 (2016) | ARIMA + NNAR |  |  |  |  |  |  |  |
|  |  | Wang 等人 (2020b) | SARIMA + NNAR |  |  |  |  |  |  |  |
|  |  | Wang 等人 (2019) | SARIMA + NNARX |  |  |  |  |  |  |  |
|  | 分隔模型 | Farooq 和 Bazaz (2020) | FFNN + SIRVD |  |  |  |  |  |  |  |
|  |  | Jo 等 (2020) | FFNN + SIR |  |  |  |  |  |  |  |
|  |  | Wang 等 (2020a) | LSTM + SEIR |  |  |  |  |  |  |  |

表 1：模型特征：空间数据 (S)：空间或地理数据；可解释性 (E)；代码可用性 (C)；开放数据 (OD)：数据公开可用；多个国家/地区 (MR)：模型考虑多个区域和国家；数据增强 (DA)；背景/外生信息 (X)：模型集成了与学习任务不直接相关但影响预测结果的输入信息。

## 5 讨论

在前面的部分中，我们概述了基于流行病学的深度学习预测模型创建的两个趋势。我们观察到一组方法采用纯深度学习方法，使用传统的（即，简单）人工神经网络应用或结合不同模型以针对数据中的不同方面的更复杂实现。另一个趋势则集中在混合深度学习模型。这些方法专注于寻找将传统预测流行病学技术，即自回归和分隔动态系统，与人工神经网络结合的方式。

两种方法似乎都能有效地解决当前任务（即疫情传播预测），然而，我们想指出这些方法论策略的一些主要优缺点。

深度人工神经网络（ANNs）提供的灵活性和抽象能力生成了准确的模型，这些模型证明能够捕捉到至少是疫情的总体趋势。此外，学习过程对当前问题的假设要求极少，几乎不需要在训练过程中进行人为干预。这在面对新的和未探索的情况（如 COVID-19）时非常有用，因为我们希望在没有偏见的情况下分析现象。纯深度学习方法也能够自然适应不断变化的条件，如疫情反应导致的流动模式和日常惯例的变化。

我们还观察到这些模型可以通过两种方式持续改进：首先，通过添加上下文信息，如季节性或城市环境特征；其次，开发更复杂的方法，例如结合不同类型的网络。这在处理空间和时间数据时特别有用，因为每个子网络可以处理数据的特定方面，从而分解总体问题。

*最终*，除了更经典的 RNN 和 CNN 应用外，我们还识别出建立流行病预测系统的新可能方法。特别是，我们简要讨论了 TCN 和 GNN 的应用，它们可能会提高预测准确性。不幸的是，这些领域到目前为止研究相对较少，我们认为这里存在巨大的潜力尚待开发；我们希望未来的研究会探索这些方向。最重要的是，我们相信 GNN 可以让我们以适合表征流行病学场景的方式来制定学习任务，并表示时空数据，以及模拟病毒传播的过程。

纯粹的深度学习方法无法利用预测流行病学领域的领域知识。此外，这些模型在结果的可解释性方面存在不足，这可能是一个关键方面，特别是当预测作为决策过程的基础时；广义而言，能够解释和说明预测结果在涉及人类健康时是一个强制性要求 Ahmad 等人 (2018)。

为此，混合模型往往更有效地融合了成熟的实践，并提供可解释的结果。特别是， compartmental 模型和深度学习的整合似乎是最有前景的研究方向之一。这些模型可以基于流行病学的简单和已知原则获得可解释的预测。然而，它们也可能继承一些经典方法的假设和僵化性（例如，描述疫情的有限 compartment 数量），因此可能需要进一步调整以适应特定疾病。幸运的是， compartmental 模型具有高度的可定制性 Giordano 等人 (2020)，因此易于根据所研究的病毒进行调整。

*最终*，将领域特定的方法整合到学习过程中，可能有助于将模型推广到训练数据之外，在疫情信息稀缺的情况下特别有用。因此，我们相信混合模型可能更适合支持特定的控制政策，并提供评估与多个干预计划相关的不同场景的手段。

一个重要的开放研究领域是如何最好地考虑隔离措施对疫情传播的影响，目前在这一领域进展甚微。这种能力是支持决策者确定最佳方法以管理健康、社会和经济成本之间权衡的关键要求。在主要依赖数据的方法中考虑这些因素可能非常具有挑战性，因为有关隔离措施的数据通常很稀缺（尤其是在疫情初期），而有关历史疫情的数据在新病原体出现时可能并不完全可靠。

## 6 结论

最近的冠状病毒爆发证明了我们对意外情境的准备不足。在这种情况下，能够准确预测病毒在空间和时间中传播的模型至关重要，以便做出明智且有科学依据的决策以遏制病毒。使用深度学习解决这一问题的应用已大幅增加，相较于更传统的方法显示了有趣的改进。鉴于当前的情况，这类方法将在未来几年中越来越多地应用于解决这个问题。因此，我们尝试概述该领域的主要趋势，希望为接触这一挑战的读者提供一个起点。

## 参考文献

+   Adhikari 等（2019）B. Adhikari, X. Xu, N. Ramakrishnan 和 B. A. Prakash。EpiDeep: 利用嵌入进行疫情预测，页 577–586。Association for Computing Machinery, New York, NY, USA, 2019。

+   Ahmad 等（2018）M. A. Ahmad, C. Eckert 和 A. Teredesai。医疗领域的可解释机器学习。在 2018 年 ACM 国际生物信息学、计算生物学和健康信息学会议论文集，页 559–560，2018。

+   Baldominos 等（2020）A. Baldominos, A. Puello, H. Oğul, T. Aşuroğlu 和 R. Colomo-Palacios。使用计算智能预测感染 – 系统综述。IEEE Access, 8:31083–31102, 2020。

+   Bengis 等（2004）R. G. Bengis, F. A. Leighton, J. R. Fischer, M. Artois, T. Morner 和 C. M. Tate。野生动物在新兴和再现 zoonoses 中的角色。Revue scientifique et technique-office international des epizooties, 23(2):497–512, 2004。

+   Chakraborty 等（2019）T. Chakraborty, S. Chattopadhyay 和 I. Ghosh。利用混合方法预测登革热疫情。Physica A: Statistical Mechanics and its Applications, 527:121266, 2019。

+   Deng 等（2020）S. Deng, S. Wang, H. Rangwala, L. Wang 和 Y. Ning。Cola-GNN: 基于跨位置注意力的图神经网络用于长期 ILI 预测，页 245–254。Association for Computing Machinery, New York, NY, USA, 2020。

+   Duan 等（2015）W. Duan, Z. Fan, P. Zhang, G. Guo 和 X. Qiu。流行病建模的数学和计算方法：全面综述。Frontiers of Computer Science, 9(5):806–826, 2015。

+   Farooq 和 Bazaz（2020）J. Farooq 和 M. A. Bazaz. 一种新的自适应深度学习模型用于 COVID-19，重点关注降低死亡率的策略。混沌、孤立子与分形，138:110148，2020 年。

+   Giordano 等人（2020）G. Giordano, F. Blanchini, R. Bruno, P. Colaneri, A. Di Filippo, A. Di Matteo, M. Colaneri 等人。意大利 COVID-19 疫情的 SIDARTHE 模型。arXiv 预印本 arXiv:2003.09861，2020 年。

+   Huang 等人（2020a）C. J. Huang, Y. H. Chen, Y. Ma, 和 P. H. Kuo. 针对中国 COVID-19 预测的多输入深度卷积神经网络模型。medRxiv，2020 年。

+   Huang 等人（2020b）C. J. Huang, Y. Shen, P. H. Kuo, 和 Y. H. Chen. 新型时空特征提取并行深度神经网络用于预测 2019 年冠状病毒病的确诊病例。medRxiv，2020 年。

+   Ibrahim 等人（2020）M. R. Ibrahim, J. Haworth, A. Lipani, N. Aslam, T. Cheng, 和 N. Christie. 变分 LSTM 自编码器预测全球冠状病毒传播。medRxiv，2020 年。

+   Jo 等人（2020）H. Jo, H. Son, H. J. Hwang, 和 S. Y. Jung. 使用时间依赖参数和深度学习分析 COVID-19 在韩国的传播。medRxiv，2020 年。

+   Kunjir 等人（2020）A. Kunjir, D. Joshi, R. Chadha, T. Wadiwala, 和 V. Trikha. COVID-19 趋势与分析的预测机器学习算法的比较研究。发表于 2020 IEEE 国际系统、人工与控制论会议（SMC），第 3407–3412 页，2020 年。

+   Lea 等人（2016）C. Lea, R. Vidal, A. Reiter, 和 G. D. Hager. 时间卷积网络：一种统一的动作分割方法。发表于 G. Hua 和 H. Jégou 编辑的《计算机视觉 – ECCV 2016 研讨会》，第 47–54 页，Cham，2016 年。施普林格国际出版社。

+   Mežnar 等人（2021）S. Mežnar, N. Lavrač, 和 B. Škrlj. 利用图神经网络预测流行病传播的影响。发表于 R. M. Benito, C. Cherifi, H. Cherifi, E. Moro, L. M. Rocha, 和 M. Sales-Pardo 编辑的《复杂网络及其应用 IX》，第 420–431 页，Cham，2021 年。施普林格国际出版社。

+   Muralidhar 等人（2018）N. Muralidhar, M. R. Islam, M. Marwah, A. Karpatne, 和 N. Ramakrishnan. 将先验领域知识纳入深度神经网络。发表于 2018 IEEE 国际大数据会议（Big Data），第 36–45 页，2018 年。

+   Oliver 等人（2020）N. Oliver, E. Letouzé, H. Sterly, S. Delataille, M. De Nadai, B. Lepri, R. Lambiotte, R. Benjamins, C. Cattuto, V. Colizza, N. de Cordes, S. P. Fraiberger, T. Koebe, S. Lehmann, J. Murillo, A. Pentland, P. N. Pham, F. Pivetta, A. Ali Salah, J. Saramäki, S. V. Scarpino, M. Tizzoni, S. Verhulst, 和 P. Vinck. 手机数据与 COVID-19：错失的机会？，2020 年。

+   Santos 和 Matos（2014）J. C. Santos 和 S. Matos. 分析 Twitter 和网络查询以预测流感趋势。理论生物学与医学建模，11(1):1–11，2014 年。

+   Sareen 等人 (2018) S. Sareen, S. K. Sood, 和 S. K. Gupta. 基于物联网的云框架以控制埃博拉病毒爆发。环境智能与人性化计算杂志, 9:459 – 476, 2018。

+   Shahid 等人 (2020) F. Shahid, A. Zameer, 和 M. Muneeb. 使用深度学习模型 LSTM, GRU 和 BI-LSTM 对 Covid-19 的预测。混沌、孤立子与分形, 140:110212, 2020。

+   Shastri 等人 (2020) S. Shastri, K. Singh, S. Kumar, P. Kour, 和 V. Mansotra. 使用深度学习模型对 Covid-19 进行时间序列预测：印度-美国比较案例研究。混沌、孤立子与分形, 140:110227, 2020。

+   Simko 等人 (2020) L. Simko, R. Calo, F. Roesner, 和 T. Kohno. Covid-19 联系追踪与隐私：研究意见与偏好, 2020。

+   Velavan 和 Meyer (2020) T. P. Velavan 和 C. G. Meyer. Covid-19 流行病。热带医学与国际健康, 25(3):278, 2020。

+   Venna 等人 (2019) S. R. Venna, A. Tavanaei, R. N. Gottumukkala, V. V. Raghavan, A. S. Maida, 和 S. Nichols. 一种用于实时流感预测的新型数据驱动模型。IEEE Access, 7:7691–7701, 2019。

+   Wang 等人 (2019) Y. Wang, C. Xu, S. Zhang, Z. Wang, L. Yang, Y. Zhu, 和 J. Yuan. 使用新型 sarima-narnnx 混合模型分析 1997 年至 2025 年中国大陆结核病发病率的时间趋势。BMJ Open, 9(7), 2019。

+   Wang 等人 (2020a) L. Wang, J. Chen, 和 M. Marathe. Tdefsi: 基于理论引导的深度学习流行病预测与合成信息。ACM Trans. Spatial Algorithms Syst., 6(3), 2020 年 4 月。

+   Wang 等人 (2020b) Y. Wang, C. Xu, Y. Li, W. Wu, L. Gui, J. Ren, 和 S. Yao. 一种用于青海省结核病发病率时间序列预测的先进数据驱动混合模型 sarima-nnnar。感染与药物抗性, 13:867, 2020。

+   Wei 等人 (2016) W. Wei, J. Jiang, H. Liang, L. Gao, B. Liang, J. Huang, N. Zang, Y. Liao, J. Yu, J. Lai, F. Qin, J. Su, L. Ye, 和 H. Chen. 结合自回归积分滑动平均 (arima) 和广义回归神经网络 (grnn) 的模型在预测中国恒县肝炎发病率中的应用。PLOS ONE, 11(6):1–13, 06 2016。

+   Wu 等人 (2018) Y. Wu, Y. Yang, H. Nishiura, 和 M. Saitoh. 用于流行病预测的深度学习。在第 41 届国际 ACM SIGIR 信息检索研究与发展大会，SIGIR ’18, 页 1085–1088, 纽约, NY, USA, 2018\. 计算机协会。