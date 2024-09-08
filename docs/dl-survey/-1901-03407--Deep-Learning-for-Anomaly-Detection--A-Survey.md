<!--yml

类别：未分类

日期：2024-09-06 20:06:46

-->

# [1901.03407] 深度学习异常检测综述

> 来源：[`ar5iv.labs.arxiv.org/html/1901.03407`](https://ar5iv.labs.arxiv.org/html/1901.03407)

missing 2⟧E_#1⟦ #2 ⟧ 1⟧⟦#1 ⟧ 1⟧¹¹1Sanjay: #1

# 深度学习异常检测综述

Raghavendra Chalapathy

悉尼大学，

资本市场合作研究中心（CMCRC）

rcha9612@uni.sydney.edu.au

&Sanjay Chawla

卡塔尔计算研究院（QCRI），HBKU

schawla@qf.org.qa

###### 摘要

异常检测是一个重要的问题，已在各种研究领域和应用领域中进行了深入研究。本调查的目标有两个：首先，我们呈现了基于深度学习的异常检测研究方法的结构化和全面概述。此外，我们还回顾了这些方法在各个应用领域中的采用情况，并评估了它们的有效性。我们将最先进的深度异常检测研究技术根据基本假设和采用的方法分成了不同类别。在每个类别中，我们概述了基本的异常检测技术及其变种，展示了关键假设，以区分正常行为和异常行为。此外，对于每个类别，我们还介绍了其优点和限制，并讨论了这些技术在实际应用领域中的计算复杂性。最后，我们概述了研究中的未解决问题和在将深度异常检测技术应用于实际问题时面临的挑战。

*K*eywords 异常、离群点、新颖性、深度学习

## 1 引言

在分析真实世界的数据集时，一个常见的需求是确定哪些实例与其他所有实例明显不同。这些实例被称为*异常*，而*异常检测*（也称为*离群点检测*）的目标是以数据驱动的方式确定所有这样的实例（chandola2007outlier）。异常可能是数据错误造成的，但有时也可能是表明一种新的、之前未知的潜在过程；hawkins 将离群点定义为偏离其他观察值如此显著的观察值，以至于引起怀疑它是由不同机制生成的。在更广泛的机器学习领域，近年来深度神经网络的激增带来了在各种应用领域前所未有的成果。深度学习是机器学习的一个子集，通过学习将数据表示为神经网络层中的嵌套概念层次来实现良好的性能和灵活性。随着数据规模的增加，深度学习优于传统机器学习，如图 1 所示。近年来，基于深度学习的异常检测算法变得越来越流行，并被应用于各种任务，如图 2 所示；研究表明，深度学习完全超越了传统方法（javaid2016deep；peng2015multi）。本调查的目标有两个：首先，我们提供了对深度异常检测（DAD）研究方法的结构化和全面的回顾。此外，我们还讨论了 DAD 方法在各个应用领域的采用情况，并评估其有效性。

⟦h⟧ ![参考标题](img/7310de803425b6effac1396bba508f25.png)scale=0.5⟧images/traditionalVsDeepLearning

图 1：基于深度学习的算法与传统算法的性能比较 deeplearningVstraditionalAlgorithms。

⟦h⟧ ![参考标题](img/7310de803425b6effac1396bba508f25.png)scale=0.5⟧images/applications

图 2：基于深度学习的异常检测算法的应用。

(a) 视频监控、图像分析：非法交通检测 xie2017real, (b) 医疗保健：检测视网膜损伤 schlegl2017unsupervised

(c) 网络：网络入侵检测 javaid2016deep (d) 传感器网络：物联网 (IoT) 大数据异常检测 mohammadi2017deep

## 2 什么是异常？

在数据挖掘和统计文献中，异常也被称为异常值、偏差点或离群点（aggarwal2013introduction）。如图 4 所示，$N_{1}$和$N_{2}$是包含大多数观察值的区域，因此被认为是正常数据实例区域，而区域$O_{3}$和数据点$O_{1}$及$O_{2}$是位于数据点大多数区域远离的少量数据点，因此被认为是异常值。异常的产生原因多种多样，如恶意行为、系统故障、故意欺诈。这些异常揭示了数据中令人兴奋的见解，并常常传达有关数据的有价值信息。因此，异常检测被认为是各种决策系统中的一个重要步骤。

![参见说明](img/7310de803425b6effac1396bba508f25.png)

scale=0.35⟧images/anomalies.png

图 3：二维数据集中的异常说明。

![参见说明](img/7310de803425b6effac1396bba508f25.png)

scale=0.35⟧images/novel.png

图 4：图像数据集中新奇点的说明。

## 3 什么是新奇点？

新奇检测是识别数据中的新（未观察到的）模式（miljkovic2010review）。检测到的新奇点并不被视为异常数据点；相反，它们被应用于常规数据模型。可以为这些以前未见的数据点分配新奇分数，使用决策阈值分数（pimentel2014review）。显著偏离该决策阈值的点可能被认为是异常值或离群点。例如，在图 4 中，常规老虎中的（白虎）可能被视为新奇点，而（马、猎豹、狮子和美洲豹）的图像则被视为异常。用于异常检测的技术通常也用于新奇检测，反之亦然。

## 4 动机和挑战：深度异常检测（DAD）技术

+   •

    传统算法在检测图像（例如医学图像）和序列数据集中的离群点的性能在图像（例如医学图像）和序列数据集中表现不佳，因为它无法捕捉数据中的复杂结构。

+   •

    大规模异常检测的需求：随着数据量的增加，例如达到千兆字节，传统方法几乎无法扩展到如此大规模的数据中以发现异常值。

+   •

    深度异常检测（DAD）技术从数据中学习层次化的判别特征。这种自动特征学习能力消除了由领域专家开发手动特征的需求，因此提倡在如文本和语音识别等领域以端到端的方式解决问题，从原始输入数据开始。

+   •

    在多个数据领域中，正常行为和异常（错误）行为之间的边界通常没有明确界定，并且这一边界不断演变。这种缺乏明确代表正常边界的情况对传统和基于深度学习的算法都带来了挑战。

⟦ht!⟧ 1 2 3 4 5 6 7 方法 监督 ✓ 无监督 ✓ 混合模型 ✓ 单类神经网络 ✓ 应用 欺诈检测 ✓ ✓ 网络入侵检测 ✓ ✓ 医疗异常检测 ✓ ✓ 传感器网络异常检测 ✓ ✓ 物联网 (IoT) 大数据异常检测 ✓ ✓ 日志异常检测 ✓ 视频监控 ✓ ✓ 工业损害检测 ✓

表 1：我们调查与其他相关调查文章的比较。

1 —我们的调查，2 —Kwon 和 Donghwoon  kwon2017survey, 5 —John 和 Derek  ball2017comprehensive

3 —Kiran 和 Thomas  kiran2018overview, 6 —Mohammadi 和 Al-Fuqaha  mohammdi2017deep

4 —Adewumi 和 Andronicus  adiwumi2017survey 7 —Geert 和 Kooi 等人  litjens2017survey.

## 5 相关工作

尽管深度学习方法在许多机器学习问题上取得了显著进展，但在异常检测领域中，深度学习方法相对较少。 adiwumi2017survey 提供了对基于深度学习的欺诈检测方法的全面调查。 kwon2017survey 对深度异常检测（DAD）技术在网络入侵检测中的应用进行了广泛的回顾。 litjens2017survey 对 DAD 技术在医疗领域的应用进行了详尽的综述。 mohammadi2017deep 对物联网 (IoT) 和大数据异常检测的 DAD 技术进行了概述。 ball2017comprehensive 对传感器网络异常检测进行了回顾。 kiran2018overview 提出了用于视频异常检测的最先进的深度学习方法及其各种类别。尽管有一些关于应用 DAD 技术的综述，但缺乏对用于异常检测的深度学习架构的比较分析。例如，虽然使用深度自编码器进行异常检测的研究量很大，但针对特定数据集和应用领域的最佳深度架构的全面调查仍然缺乏。我们希望本次调查能够弥补这一空白，并为希望利用深度学习进行异常检测的研究人员和工程师提供全面的参考。 表 1 techniques ‣ Deep Learning for Anomaly Detection: A Survey") 显示了我们调查所涵盖的研究方法和应用领域。

⟦h⟧ ![参考说明](img/7310de803425b6effac1396bba508f25.png)scale=0.45⟧images/AnomalyDetectionTaxonomy

图 5：与基于深度学习的异常检测技术相关的关键组件。

## 6 我们的贡献

我们遵循了(chandola2007outlier)的深度异常检测（DAD）调查方法。我们的调查提供了对 DAD 技术研究和应用的详细且结构化的概述。我们总结了我们的主要贡献如下：

+   •

    现有的大多数 DAD 技术综述要么专注于特定的应用领域，要么专注于特定的研究领域（kiran2018overview；mohammadi2017deep；litjens2017survey；kwon2017survey；adewumi2017survey；ball2017comprehensive）。本综述旨在提供 DAD 技术前沿研究的全面概述，以及这些技术在多个实际应用中的表现。

+   •

    近年来，几种基于深度学习的新型异常检测技术在计算需求大幅减少的情况下得到发展。本文的目的是对这些技术进行综述，并将其分类为一个有组织的模式，以便更好地理解。我们介绍了两种额外的子类别：混合模型（erfani2016high）和一类神经网络技术（chalapathy2018anomaly），如图 5 所示，基于训练目标的选择。对于每个类别，我们讨论了为获得最佳性能所采用的假设和技术。此外，在每个类别中，我们还展示了挑战、优点和缺点，并提供了 DAD 方法的计算复杂性概述。

## 7 组织结构

本章的组织结构遵循图 5 中描述的结构。在第八部分中，我们确定了决定问题制定的各种方面，并突出了与异常检测相关的丰富性和复杂性。我们介绍并定义了两种类型的模型：上下文异常和集体或群体异常。在第九部分中，我们简要描述了深度学习异常检测应用的不同领域。在随后的章节中，我们根据所属研究领域对深度学习技术进行分类。基于使用的训练目标和标签的可用性，深度学习异常检测技术可以分类为监督（第 10.1)、无监督（第 10.5)、混合（第 10.3)，和一类神经网络（第 10.4)。对于每类技术，我们还讨论了它们在训练和测试阶段的计算复杂性。在第 8.4 节中，我们讨论了点状、上下文和集体（群体）基于深度学习的异常检测技术。在第十二部分中，我们对各种现有技术的局限性和相对性能进行了一些讨论。第十三部分包含结论性评述。

## 8 深度学习基础的异常检测的不同方面。

本节识别并讨论了深度学习基础的异常检测的不同方面。

### 8.1 输入数据的性质

在深度异常检测方法中，深度神经网络架构的选择主要取决于输入数据的性质。输入数据大致可以分为顺序数据（如语音、文本、音乐、时间序列、蛋白质序列）或非顺序数据（如图像、其他数据）。表 8.2.1 展示了输入数据的性质以及在异常检测中使用的深度模型架构。此外，输入数据根据特征（或属性）的数量还可以进一步分类为低维数据或高维数据。DAD 技术已被用于学习高维原始输入数据中的复杂层次特征关系（lecun2015deep）。DAD 技术中使用的层数由输入数据的维度驱动，较深的网络在高维数据上显示出更好的性能。随后，在第十部分中，详细审查了用于异常值检测的各种模型。

### 8.2 基于标签的可用性

标签指示选择的数据实例是否为正常或异常值。异常情况是稀有的，因此获取其标签具有挑战性。此外，异常行为可能随时间变化，例如，Maroochy 水处理厂的异常性质发生了如此显著的变化，以至于在很长时间内未被注意，最终导致 150 万升未经处理的污水泄漏到当地水道中（ramotsoela2018survey）。

深度异常检测（DAD）模型可以根据标签的可用程度大致分为三类：（1）监督式深度异常检测。（2）半监督式深度异常检测。（3）无监督式深度异常检测。

#### 8.2.1 监督式深度异常检测

监督式深度异常检测涉及训练一个深度监督的二分类或多分类分类器，使用正常和异常数据实例的标签。例如，作为多分类分类器的监督 DAD 模型有助于检测稀有品牌、禁止药物名称提及以及欺诈性的医疗交易（chalapathy2016investigation; chalapathy2016bidirectional）。尽管监督 DAD 方法的性能有所提高，但由于标记训练样本的可用性不足，这些方法不如半监督或无监督方法受欢迎。此外，由于类不平衡（正类实例总数远多于负类数据总数），深度监督分类器在异常检测中的表现次优。因此，我们在本次调查中不考虑监督 DAD 方法的回顾。

| 数据类型 | 示例 | DAD 模型架构 |
| --- | --- | --- |
| ⟦0.5ex⟧ 顺序 | 视频、语音 |  |
|  | 蛋白质序列、时间序列 | CNN、RNN、LSTM |
|  | 文本（自然语言） |  |
| 非顺序 | 图像、传感器 |  |
| 其他（数据） | CNN、AE 及其变体 |

表 2：表格说明了输入数据的性质及文献中提出的相应深度异常检测模型架构。CNN：卷积神经网络，LSTM：长短期记忆网络，AE：自编码器。

#### 8.2.2 半监督深度异常检测

正常实例的标签比异常实例更容易获取，因此，半监督 DAD 技术更为广泛采用，这些技术利用单一（通常为正类）的现有标签来分离离群点。使用深度自编码器进行异常检测的一种常见方法是用没有异常的数据样本以半监督的方式进行训练。通过足够的训练样本，正常类的自编码器会对正常实例产生低重建误差，对异常事件则会有较高误差（wulsin2010semi; nadeem2016semi; song2017hybrid）。我们将在第 10.2 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")节中详细回顾这些方法。

⟦h⟧ ![参考说明](img/7310de803425b6effac1396bba508f25.png)scale=0.7⟧images/TypeOfModels

图 6：基于深度学习模型类型的分类。

#### 8.2.3 无监督深度异常检测

无监督深度异常检测技术仅根据数据实例的内在属性来检测异常值。由于标签数据非常难以获得（patterson2017deep），无监督 DAD 技术用于自动标记未标记的数据样本。无监督 DAD 模型的变体（tuor2017deep）在健康和网络安全等应用领域中显示出优于传统方法，如主成分分析（PCA）（wold1987principal）、支持向量机（SVM）（cortes1995support）和隔离森林（liu2008isolation）技术的效果。自编码器是所有无监督 DAD 模型的核心。这些模型假设正常实例的出现频率高于异常数据实例，否则会导致高假阳性率。此外，讨论了无监督学习算法，如限制玻尔兹曼机（RBM）（sutskever2009recurrent）、深度玻尔兹曼机（DBM）、深度置信网络（DBN）（salakhutdinov2010efficient）、广义去噪自编码器（vincent2008extracting）、递归神经网络（RNN）（rodriguez1999recurrent）和长短期记忆网络（lample2016neural），用于检测异常值，详见第 11.7 节 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey").

### 8.3 基于训练目标

在这项调查中，我们介绍了两种基于训练目标的新型深度异常检测（DAD）技术：1）深度混合模型（DHM）。2）单类神经网络（OC-NN）。

#### 8.3.1 深度混合模型（DHM）

深度混合模型用于异常检测，主要使用深度神经网络（如自编码器）作为特征提取器，自编码器中的隐藏表示所学到的特征被输入到传统的异常检测算法中，如一类 SVM（OC-SVM），以检测异常点 (andrews2016detecting)。图 7 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 展示了用于异常检测的深度混合模型架构。在迁移学习成功获取来自大数据集预训练模型的丰富表示特征之后，混合模型也利用这些预训练迁移学习模型作为特征提取器取得了很大成功 (pan2010survey)。ergen2017unsupervised 提出了一个混合模型的变体，该模型考虑了特征提取器与 OC-SVM（或 SVDD）目标的联合训练，以最大化检测性能。这些混合方法的一个显著缺陷是缺乏为异常检测量身定制的可训练目标，因此这些模型未能提取丰富的差异特征以检测异常点。为了解决这一限制，引入了针对异常检测的定制目标，如深度一类分类 (ruff2018deep)和一类神经网络 (chalapathy2018anomaly)。

![参考标题](img/7310de803425b6effac1396bba508f25.png)

scale=0.7⟧images/HybridDeepModels

图 7: 深度混合模型架构。

#### 8.3.2 一类神经网络（OC-NN）

一类神经网络（OC-NN）*chalapathy2018anomaly*方法的灵感来源于基于核的一类分类，这种方法结合了深度网络提取逐步丰富的数据表示的能力与围绕正常数据创建紧密包络的一类目标。OC-NN 方法在以下关键原因上开辟了新领域：隐藏层中的数据表示由 OC-NN 目标驱动，因此为异常检测量身定制。这不同于其他方法，这些方法使用自编码器学习深度特征，然后将特征输入到像一类支持向量机（OC-SVM）这样的单独异常检测方法中。有关一类神经网络的训练和评估的详细信息见第 10.4。另一种一类神经网络架构的变体——深度支持向量数据描述（Deep SVDD）*ruff2018deep*通过将正常数据实例紧密映射到球体中心来训练深度神经网络，以提取常见变化因子，并在 MNIST *(lecun2010mnist)* 和 CIFAR-10 *(krizhevsky2009learning)* 数据集上显示了性能改进。

### 8.4 异常类型

异常可以大致分为三种类型：点异常、上下文异常和集体异常。深度异常检测（DAD）方法已被证明能够成功地检测这三种类型的异常。

⟦h⟧ ![参见说明](img/7310de803425b6effac1396bba508f25.png)scale=0.7⟧images/TypeOfAnomaly

图 8：基于异常类型的深度学习技术分类。

#### 8.4.1 点异常

大多数文献中的工作都集中在点异常上。点异常通常表示一种随机发生的不规则性或偏差，可能没有特定的解释。例如，在图 10 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")中，一笔在摩纳哥餐馆记录的高支出信用卡交易似乎是一个点异常，因为它显著偏离了其他交易。考虑到点异常检测的几个现实应用在第 9 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")节中进行了回顾。

#### 8.4.2 上下文异常检测

上下文异常，也称为条件异常，是一种在特定上下文中可能被认为是异常的数据实例（song2007conditional）。上下文异常通过同时考虑上下文和行为特征来识别。通常使用的上下文特征包括时间和空间。而行为特征可能是消费模式、系统日志事件的发生频率或描述正常行为的任何特征。图 9(a) ‣ Figure 9 ‣ 8.4.2 Contextual Anomaly Detection ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 通过温度数据的急剧下降例子来说明上下文异常；这种下降在 6 月之前并不表示一个正常值。图 9(b) ‣ Figure 9 ‣ 8.4.2 Contextual Anomaly Detection ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 通过基于深度长短期记忆（LSTM）(hochreiter1997long) 的模型来识别给定上下文中的异常系统日志事件（du2017deeplog），例如事件 53 被检测为异常。

⟦htp⟧

![参见说明](img/7310de803425b6effac1396bba508f25.png)

scale=0.35⟧images/temperature.png

(a) 温度数据 hayes2015contextual。

![参见说明](img/7310de803425b6effac1396bba508f25.png)

scale=0.35⟧images/deeplog.png

(b) 系统日志 du2017deeplog。

图 9：上下文异常检测的说明。

#### 8.4.3 集体或群体异常检测。

单个数据点的异常集合被称为集体或群体异常，其中每个单独的数据点在孤立时看起来是正常的数据实例，而在群体中观察时则表现出异常特征。例如，考虑一个欺诈信用卡交易的示例，在图 10 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")中显示的日志数据中，如果出现了一笔单独的“杂项”交易，它可能不会显得特别异常。接下来的这些价值为$\$75$的交易确实似乎是集体或群体异常的候选者。群体异常检测（GAD）强调不规则的群体分布（例如，使用变体的自编码器模型检测不规则的图像像素混合(chalapathy2018group; bontemps2016collective; araya2016collective; zhuang2017group)）。

⟦h⟧ ![参见说明](img/7310de803425b6effac1396bba508f25.png)scale=0.5⟧images/PointAndCollectiveAnomaly

图 10：信用卡欺诈检测：展示点异常和集体异常。

### 8.5 DAD 技术的输出

异常检测方法的一个关键方面是异常的检测方式。通常，异常检测方法产生的输出是异常分数或二元标签。

#### 8.5.1 异常分数：

异常分数描述了每个数据点的异常程度。数据实例可以根据异常分数进行排名，领域专家将选择一个领域特定的阈值（通常称为决策分数）来识别异常。通常，决策分数比二元标签揭示更多信息。例如，在 Deep SVDD 方法中，决策分数是数据点与球心的距离的度量，离中心较远的数据点被认为是异常的(pmlrv80ruff18a)。

#### 8.5.2 标签：

一些技术可能会分配一个类别标签，标记为正常或异常，而不是分配分数。使用自编码器的无监督异常检测技术通过测量残差向量（即重建误差）的大小来获得异常分数，之后，重建误差由领域专家进行排序或设定阈值，以标记数据实例。

## 9 深度异常检测的应用

在这一部分，我们探讨了深度异常检测的几种应用。对于每个应用领域，我们讨论以下四个方面：—异常的概念；—数据的性质；—检测异常相关的挑战；—现有的深度异常检测技术。

### 9.1 入侵检测

入侵检测系统（IDS）指的是识别计算机相关系统中的恶意活动（phoha2002internet）。IDS 可以部署在单个计算机上称为主机入侵检测（HIDS），也可以部署在大型网络中称为网络入侵检测（NIDS）。入侵检测的深度异常检测技术分类见图 11: ‣ 9.1 Intrusion Detection ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")。根据检测方法，IDS 分为基于签名或基于异常的方法。使用基于签名的 IDS 对于检测没有特定签名模式的新攻击并不高效，因此基于异常的检测方法更为流行。在本次调查中，我们专注于入侵检测中采用的深度异常检测（DAD）方法和架构。

#### 9.1.1 基于主机的入侵检测系统（HIDS）：

这类系统是安装的软件程序，它们通过监听系统调用或发生在该主机上的事件来监控单个主机或计算机的恶意活动或政策违规（vigna2005host）。系统调用日志可以由程序生成，也可以由用户交互产生，日志示例见图 9(b) ‣ Figure 9 ‣ 8.4.2 Contextual Anomaly Detection ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")。恶意交互会导致这些系统调用以不同的顺序执行。HIDS 还可能监控系统的状态、存储的信息，包括随机存取内存（RAM）、文件系统、日志文件或其他地方的有效序列。应用于 HIDS 的深度异常检测（DAD）技术需要处理数据的可变长度和序列性质。DAD 技术必须要么对序列数据建模，要么计算序列之间的相似性。一些成功的 DAD 技术用于 HIDS 的示例见表 3: ‣ 9.1 Intrusion Detection ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")。

#### 9.1.2 网络入侵检测系统 (NIDS):

NIDS 系统通过检查每一个网络数据包来监控整个网络中的可疑流量。由于实时流行为的特性，这些数据的性质类似于具有高容量、速度和多样性的“大数据”。网络数据还具有时间方面的特征。NIDS 的一些成功的 DAD 技术如表 4: ‣ 9.1 Intrusion Detection ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 中有所说明。这份调查还列出了用于评估 DAD 入侵检测方法的数据集，如表 5: ‣ 9.1 Intrusion Detection ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")。DAD 技术在入侵检测中面临的挑战是，异常的性质会随着入侵者适应网络攻击以规避现有的入侵检测解决方案而不断变化。

![参见说明](img/7310de803425b6effac1396bba508f25.png)

scale=0.4⟧images/IDS

图 11: 深度学习方法在入侵检测中的分类。

表 3: HIDS 中采用的 DAD 技术示例 CNN: 卷积神经网络，LSTM: 长短期记忆网络 GRU: 门控递归单元，DNN: 深度神经网络 SPN: 求和乘积网络

| 技术 | 模型架构 | 部分 | 参考文献 |
| --- | --- | --- | --- |
| 判别性 | LSTM、CNN-LSTM-GRU、DNN | 节点 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础上的异常检测不同方面 ‣ 深度学习用于异常检测：综述"), 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础上的异常检测不同方面 ‣ 深度学习用于异常检测：综述"), 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础上的异常检测不同方面 ‣ 深度学习用于异常检测：综述") | kim2016lstm,chawla2018host,chen2018henet,sohi2018recurrent,vinayakumar2017applying |
| 混合 | GAN | 部分  10.3 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习异常检测的不同方面 ‣ 深度学习异常检测：综述") | aghakhani2018detecting, li2018anomaly |
| 生成 | AE, SPN | 部分  11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习异常检测的不同方面 ‣ 深度学习异常检测：综述"), 11.3 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 其他技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习异常检测的不同方面 ‣ 深度学习异常检测：综述") | gao2014intrusion, peharz2018probabilistic, umer2018two |

表 4：在 NIDS 中使用的 DAD 技术示例。CNN：卷积神经网络，LSTM：长短期记忆网络，RNN：递归神经网络，RBM：限制玻尔兹曼机，DCA：扩张卷积自编码器，DBN：深度信念网络，AE：自编码器，SAE：堆叠自编码器，GAN：生成对抗网络，CVAE：卷积变分自编码器。

| 技术 | 模型架构 | 部分 | 参考文献 |
| --- | --- | --- | --- |
| 生成模型 | DCA、SAE、RBM、DBN、CVAE | 节 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测: 综述"), 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测: 综述"), 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测: 综述"), 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测: 综述") | yu2017network, thing2017ieee, zolotukhin2016increasing, cordero2016analyzing, alrawashdeh2016toward, tang2016deep, lopez2017conditional, al2018deep, mirsky2018kitsune, aygun2017network |
| 混合 | GAN | 部分 10.3 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习用于异常检测：综述") | lin2018idsgan, yin2018enhancing, ring2018flow, latah2018deep, intrator2018mdgan, matsubara2018anomaly, nicolau2016hybrid, rigaki2017adversarial. |
| 区分性 | RNN, LSTM, CNN | 部分 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习用于异常检测：综述"), 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习用于异常检测：综述") | yu2017network, malaiya2018empirical, kwon2018empirical, gao2014intrusion, staudemeyer2015applying, naseer2018enhanced |

表 5: 入侵检测中使用的数据集

| 数据集 | IDS | 描述 | 类型 | 参考文献 |
| --- | --- | --- | --- | --- |
| CTU-UNB | NIDS | CTU-UNB ucsdAnomalyDetect2017 数据集包括来自 CTU-13 数据集 ⟦20⟧ 的各种僵尸网络流量和来自 UNB ISCX IDS 2012 数据集的正常流量 shiravi2012toward | 十六进制 | yu2017network |
| Contagio-CTU-UNB | NIDS | Contagio-CTU-UNB 数据集包含六种类型的网络流量数据。 adam2008robust | 文本 |  yu2017network. |
| NSL-KDD ²²2http://nsl.cs.unb.ca/NSL-KDD/ | NIDS | NSL-KDD 数据集是其前身 KDD-99 数据集的改进版。 ucsdAnomalyDetect2017 | 文本 |  yin2017deep, javaid2016deep,  tang2016deep, yousefi2017autoencoder, mohammadi2017new,  lopez2017conditional |
| DARPA KDD- CUP 99 | NIDS | DARPA KDD stolfo2000cost 竞赛任务是构建一个网络入侵检测器，这是一种能够区分“坏”连接（称为入侵或攻击）和“好”正常连接的预测模型。 | 文本 |  alrawashdeh2016toward , van2017anomaly, mohammadi2017new |
| MAWI | NIDS | MAWI fontugne2010mawilab 数据集由捕获自日本和美国之间骨干链路的网络流量组成。从 2007 年起的每天 | 文本 |  cordero2016analyzing |
| 现实全球网络环境 (RGCE) | NIDS | RGCE jamkRGCE 包含了现实的互联网服务提供商（ISP）和许多不同的网络服务，如同真实的互联网。 | 文本 |  zolotukhin2016increasing |
| ADFA-LD | HIDS | ADFA Linux 数据集 (ADFA-LD)。该数据集提供了一个现代的 Linux 数据集，用于传统 HIDS 的评估 creech2014semantic | 文本 |  kim2016lstm, chawla2018host |
| UNM-LPR | HIDS | 包含用于评估 HIDS 系统的系统调用 ImmuneDatasets | 文本 |  kim2016lstm |
| 被感染的 PDF 样本 | HIDS | 包含一组被感染的 PDF 样本，用于监控恶意流量 | 文本 |  chen2018henet |

### 9.2 欺诈检测

欺诈是为了获取有价值资源而故意进行的欺骗行为 (abdallah2016fraud)。普华永道（PwC）2018 年的全球经济犯罪调查 (Lavion2018; zhao2013fraud)发现，他们调查的 7200 家公司中有一半经历过某种形式的欺诈。欺诈检测指的是在各种行业中检测非法活动，具体如 12 ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测: 综述")中所示。

⟦h⟧ ![参见说明](img/7310de803425b6effac1396bba508f25.png)scale=0.5⟧images/AreasOfFraud

图 12：各个应用领域的欺诈检测。

电信、保险（健康、汽车等）索赔、银行（税务申报、信用卡交易等）中的诈骗在政府和私营企业中都构成了重大问题。检测和防止诈骗不是一项简单的任务，因为诈骗是一种适应性犯罪。许多传统的机器学习算法在诈骗检测中取得了成功（sorournejad2016survey）。检测诈骗面临的挑战在于它需要实时检测和防止。本节重点讨论用于诈骗检测的深度异常检测（DAD）技术。

#### 9.2.1 银行诈骗

信用卡已成为在线购物中一种流行的支付方式。信用卡诈骗涉及盗取支付卡的详细信息，并将其作为交易中的欺诈性资金来源。近年来，已经提出了许多信用卡诈骗检测技术（zhou2018state；suganya2015survey）。我们将简要回顾一些如表 6 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 中所示的 DAD 技术。信用卡诈骗检测的挑战在于诈骗行为没有一致的模式。信用卡诈骗检测的典型方法是为每个用户维护一个使用档案，并监控用户档案以检测任何偏差。由于信用卡用户数量众多，这种用户档案方法的可扩展性不高。由于 DAD 技术具有固有的可扩展性，这些技术在信用卡诈骗检测中得到了广泛的应用。

表 6: 信用卡诈骗检测中使用的 DAD 技术示例。AE: 自编码器，LSTM：长短期记忆网络，RBM：限制玻尔兹曼机，DNN：深度神经网络，GRU：门控循环单元，RNN：递归神经网络，CNN：卷积神经网络，VAE：变分自编码器，GAN：生成对抗网络

| 使用的技术 | 部分 | 参考文献 |
| --- | --- | --- |
| AE | 章节 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习异常检测综述") | schreyer2017detection, wedge2017solving, paula2016deep, renstrom2018fraud, kazemi2017using, zheng2018one, pumsirirat2018credit |
| RBM | 章节 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习异常检测综述") | pumsirirat2018credit |
| DBN | 章节 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习异常检测综述") | seeja2014fraudminer |
| VAE | 部分 11.5 | sweers2018autoencoding |
| GAN | 部分 11.5 | fiore2017using, choi2018generative |
| DNN | 部分 11.1 | dorronsoro1997neural, gomez2018end |
| LSTM,RNN,GRU | 节点  11.7 |  wiese2009credit,  jurgovsky2018sequence, heryadi2017learning, ando2016detecting, wang2017session, alowais2012credit, amarasinghe2018critical, abroyan2017neural, lp2018transaction |
| CNN | 节点  11.6 |  shen2007application, chouiekh2018convnets, abroyan2017convolutional, fu2016credit, lu2017deep, wang2018credit, abroyan2017neural , zhang2018model |

#### 9.2.2 移动蜂窝网络欺诈

近年来，移动蜂窝网络经历了快速的部署和演进，支持了数十亿用户和各种各样的移动设备。由于这种广泛的采用和低廉的移动蜂窝服务费率，移动蜂窝网络现在面临着诸如语音诈骗（旨在窃取客户私人信息）和与消息相关的诈骗（旨在敲诈客户钱财）等欺诈行为。检测这些欺诈行为极其重要，但由于移动蜂窝网络的数量和速度，这并非易事。传统的机器学习方法和静态特征工程技术无法适应不断演变的欺诈行为。表格 7 列出了用于移动蜂窝网络欺诈检测的 DAD 技术。

表 7：用于移动蜂窝网络欺诈检测的 DAD 技术示例。CNN: 卷积神经网络，DBN: 深度置信网络，SAE: 堆叠自编码器，DNN: 深度神经网络，GAN: 生成对抗网络

| 使用的技术 | 节点 | 参考文献 |
| --- | --- | --- |
| CNN | 节点  11.6 |  chouiekh2018convnets |
| SAE, DBN | 第 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 根据标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 基于深度学习的异常检测: 一份综述") |  alsheikh2016mobile, badhe2017click |
| DNN | 第 11.1 ‣ 11 深度神经网络用于异常定位的体系结构 ‣ 10.6.6 深度异常检测的统计技术 ‣ 10.6 其他技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 根据标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 基于深度学习的异常检测: 一份综述") |  akhter2012detecting, jain2017perspective |
| GAN | 章节 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测: 一项综述") | zheng2018generative |

#### 9.2.3 保险欺诈

一些传统的机器学习方法已成功应用于保险索赔中的欺诈检测 (joudaki2015using; roy2017detecting)。传统的欺诈检测方法基于作为欺诈指标的特征。这些传统方法的挑战在于需要手动专业知识来提取可靠的特征。另一个挑战是保险欺诈检测中，欺诈事件的发生远少于索赔总数，并且每个欺诈事件都是独特的。为了克服这些限制，提出了几种 DAD 技术，这些技术在表格 8 ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测: 一项综述") 中有所示。

表格 8: 用于保险欺诈检测的 DAD 技术示例。DBN: 深度置信网络，DNN: 深度神经网络，CNN: 卷积神经网络，VAE: 变分自编码器，GAN: 生成对抗网络

| DBN | 部分  11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习异常检测：综述") |  viaene2005auto |
| --- | --- | --- |
| VAE | 部分  11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习异常检测：综述") |  fajardo2018vos |
| GAN | 部分  11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习异常检测：综述") |  fiore2017using, choi2018generative |
| DNN | 部分 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测：调查") | keung2009neural |
| CNN | 部分 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测：调查") | shen2007application, zhang2018model |

#### 9.2.4 医疗欺诈

医疗保健是人们生活中不可或缺的一部分，浪费、滥用和欺诈每年将医疗成本推高数百亿美元。医疗保险索赔欺诈是医疗成本增加的一个重要因素，但通过欺诈检测可以减轻其影响。多种机器学习模型已在医疗保险欺诈中有效使用 (bauder2017medicare)。表 9 ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测：调查") 概述了用于医疗欺诈识别的 DAD 方法。

表 9: 用于医疗欺诈检测的 DAD 技术示例。RBM: 受限玻尔兹曼机，GAN: 生成对抗网络

| 使用的技术 | 部分 | 参考文献 |
| --- | --- | --- |
| RBM | 第 11.1 |  lasaga2018deep |
| GAN | 第 11.5 |  ghasedi2018semi, finlayson2018adversarial |
| CNN | 第 11.6 |  esteva2017dermatologist |

### 9.3 恶意软件检测

恶意软件（Malware）是恶意软件的缩写。为了保护合法用户免受恶意软件的侵害，提出了基于机器学习的高效恶意软件检测方法（ye2017survey）。在传统机器学习方法中，恶意软件检测过程通常分为两个阶段：特征提取和分类/聚类。传统恶意软件检测方法的性能在很大程度上依赖于提取的特征和分类/聚类的方法。恶意软件检测问题的挑战在于数据的庞大规模，例如，将数据视为字节的情况下，某个特定序列分类问题可能达到两百万个时间步。此外，恶意软件具有很强的适应性，攻击者会使用先进技术来隐藏恶意行为。一些有效解决这些挑战并检测恶意软件的 DAD 技术见表 10 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")。

表 10：用于恶意软件检测的 DAD 技术示例。AE：自编码器，LSTM：长短期记忆网络，RBM：限制玻尔兹曼机，DNN：深度神经网络，GRU：门控循环单元，RNN：循环神经网络，CNN：卷积神经网络，VAE：变分自编码器，GAN：生成对抗网络，CNN-BiLSTM：CNN-双向 LSTM

| 技术名称 | 章节 | 参考文献 |
| --- | --- | --- |
| AE | 章节 11.8 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") | yousefi2017autoencoder, hardy2016dl4md, yousefi2017autoencoder, de2018malware, sewak2018investigation, kebede2017classification, de2018malware, david2015deepsign |
| word2vec | 部分 11.4 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习异常检测：综述") | cakir2018malware, silva2018improving |
| CNN | 部分 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习异常检测：综述") | kolosnjaji2018adversarial, sucui2018exploring, srisakaokul2018muldef, srisakaokul2018muldef, king2018artificial, huang2017r2, guo2017malware, abdelsalam2018malware, raff2017malware, karbab2018maldozer, martinelli2017evaluating, mclaughlin2017deep, gibert2018using, kolosnjaji2017empowering |
| DNN | 部分 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习异常检测：综述") | rosenberg2018end, wang2017adversary |
| DBN | 部分 11.1 ‣ 11 深度神经网络架构用于异常检测 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习在异常检测中的应用: 调查") |  david2015deepsign, yang2016application, ding2016application, yuxin2017malware, selvaganapathy2018deep, yuxin2017malware, hou2017deep |
| LSTM | 部分 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习在异常检测中的应用: 调查") |  tobiyama2016malware, hu2017black, tobiyama2018method, passalislong |
| CNN-BiLSTM | 章节  11.6, 11.7 |  le2018deep, wang2017adversary |
| GAN | 章节  11.5 |  kim2018zero |
| 混合模型（AE-CNN），（AE-DBN） | 部分 10.3 | wang2018effective, li2015hybrid |
| RNN | 部分 11.7 | haddadpajouh2018deep |

### 9.4 医疗异常检测

已进行多个研究以了解深度学习在医学和生物信息学中的理论和实际应用（min2017deep; cao2018deep; zhao2016deep; khan2018review）。在医学图像分析、临床脑电图（EEG）记录等领域发现稀有事件（异常）能够帮助诊断并提供预防性治疗。基于深度学习的架构在检测医学异常方面取得了巨大的成功，如表 11 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 所示。医学领域大量的不平衡数据给检测异常值带来了重大挑战。此外，深度学习技术长期以来被认为是黑箱技术。尽管深度学习模型表现出色，但这些模型缺乏可解释性。最近提出了具有良好可解释性的模型，并且显示出达到最先进的性能（gugulothusparse; amarasinghe2018toward; choi2018doctor）。

表 11：用于医学异常检测的 DAD 技术示例。AE：自编码器，LSTM：长短期记忆网络，GRU：门控递归单元，RNN：递归神经网络，CNN：卷积神经网络，VAE：变分自编码器，GAN：生成对抗网络，KNN：K 近邻，RBM：限制玻尔兹曼机。

| 使用的技术 | 部分 | 参考文献 |
| --- | --- | --- |
| AE | 部分 11.8 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") | wang2016research; cowton2018combined, sato2018primitive |
| DBN | 节点 11.1 | turner2014 深度, sharma2016 异常, wulsin2010 半监督, ma2018 无监督, zhang2016 自动, wulsin2011 建模, wu2015 自适应 |
| RBM | 节点 11.1 | liao2016 增强 |
| VAE | 节点 11.5 | xu2018 无监督, lu2018 异常 |
| GAN | 部分 11.5 |  ghasedi2018semi, chen2018unsupervised |
| LSTM ,RNN,GRU | 部分 11.7 |  yang2018toward, jagannatha2016bidirectional, cowton2018combined, o2016recurrent, latif2018phonocardiographic, zhang2018time, chauhan2015anomaly, gugulothusparse; amarasinghe2018toward |
| CNN | 部分 11.6 |  schmidt2018artificial, esteva2017dermatologist, wang2016research, iakovidis2018detecting |
| 混合（AE + KNN） | 部分 11.6 | song2017hybrid |

### 9.5 社交网络中的深度学习异常检测

近年来，在线社交网络已成为日常生活的一部分。社交网络中的异常是指个人在社交网络中表现出的不规则或非法行为模式；这些个人可能被识别为垃圾邮件发送者、性掠夺者、在线诈骗者、虚假用户或谣言散布者。检测这些不规则模式至关重要，因为如果未被发现，这些个人的行为可能会造成严重的社会影响。文献中对传统异常检测技术及其在社交网络中检测异常的挑战进行了广泛研究（liu2017social；savage2014anomaly；anand2017anomaly；yu2016survey；cao2018automatic；yu2016survey）。数据的异质性和动态性对 DAD 技术提出了重大挑战。尽管面临这些挑战，表 12 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 中所示的几种 DAD 技术表现优于最新方法。

表 12：用于检测社交网络中异常的 DAD 技术示例。CNN：卷积神经网络，LSTM：长短期记忆网络 AE：自编码器，DAE：去噪自编码器 SVM：支持向量机，DNN：深度神经网络

| 使用的技术 | 部分 | 参考文献 |
| --- | --- | --- |
| AE,DAE | 节点  11.8 |  zhang2017detecting, castellini2017fake |
| CNN-LSTM | 节点  11.6,  11.7 |  sun2018detecting, shu2017doc, yang2018anomaly |
| DNN | 部分 11.1 ‣ 11 用于定位异常的深度神经网络架构 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：调查") | li2017detecting |
| 混合模型 (CNN-LSTM-SVM) | 部分 10.3 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：调查") | wei2017new |

### 9.6 日志异常检测

日志文件中的异常检测旨在寻找可能指示系统故障原因和性质的文本。最常见的方法是根据以往经验构造特定领域的正则表达式，通过模式匹配发现新的故障。这种方法的限制在于，它无法有效检测到新的故障信息（memon2008log）。日志数据在格式和语义上的非结构化和多样性给日志异常检测带来了重大挑战。异常检测技术应该适应生成的日志数据的并发集，并实时检测异常。继深度神经网络在实时文本分析中的成功之后，表 13 ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：调查") 中所示的几种 DAD 技术将日志数据建模为自然语言序列，这在检测异常方面表现得非常有效。

表 13: 系统日志中使用的深度学习异常检测技术的示例。CNN: 卷积神经网络, LSTM: 长短期记忆网络 GRU: 门控循环单元, DNN: 深度神经网络 AE: 自编码器, DAE: 去噪自编码器

| 技术 | 节点 | 参考文献 |
| --- | --- | --- |
| LSTM | 节点  11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测综述") |  hochreiter1997long, brown2018recurrent, tuor2017deep, das2018desh, malhotra2015long |
| AE | 节点  11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测综述") |  du2017deeplog, andrews2016detecting , sakurada2014anomaly, nolle2018analyzing, nolle2016unsupervised |
| LSTM-AE | 部分 11.7 | grover2018anomaly, wolpher2018anomaly |
| RNN | 部分 11.7 | brown2018recurrent, zhang2018role, nanduri2016anomaly, fengming2017anomaly |
| DAE | 章节 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习用于异常检测：综述") | marchi2015non, nolle2016unsupervised |
| CNN | 章节 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习用于异常检测：综述") | lu2018detecting, yuan2018insider, racki2018compact, zhou2016spatial, gorokhov2017convolutional, liao2017deep, cheng2017deep, zhang2018alphamex |

### 9.7 物联网 (IoT) 大数据异常检测

物联网（IoT）被定义为一个由软件、服务器、传感器等互联的设备网络。在物联网领域，由天气站、射频识别（RFID）标签、IT 基础设施组件以及其他一些传感器生成的数据大多是时间序列数据。在这些物联网网络中，异常检测识别这些大规模互联设备的欺诈性和故障行为。与异常检测相关的挑战在于异质设备的互联使得系统变得更加复杂。对使用深度学习（DL）来促进物联网领域分析和学习的全面概述由(mohammadi2018deep)提供。表 14 Big Data Anomaly Detection ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")展示了在物联网设备中应用的 DAD 技术。

表 14：在物联网（IoT）大数据异常检测中使用的 DAD 技术示例。AE：自编码器，LSTM：长短期记忆网络，DBN：深度置信网络。

| 技术 | 部分 | 参考文献 |
| --- | --- | --- |
| AE | 部分 11.8 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") |  luo2018distributed, mohamadi2018neural |
| DBN | 部分 11.1 ‣ 11 用于定位异常的深度神经网络架构 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测综述") | kakanakova2017outlier |
| LSTM | 部分 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测综述") | zhang2018lstm, mudassar2018unsupervised |

### 9.8 工业异常检测

由风力涡轮机、发电厂、高温能源系统、储存设备以及旋转机械部件组成的工业系统每天都承受着巨大的压力。这些系统的损坏不仅导致经济损失，还损害声誉，因此尽早检测和修复至关重要。已经使用了几种机器学习技术来检测工业系统中的此类损坏（ramotsoela2018survey; marti2015anomaly）。利用深度学习模型检测早期工业损坏的几篇论文显示了极大的前景（atha2018evaluation; de2018automatic; wang2018residential）。由于设备损坏是罕见事件，因此检测此类事件可以被表述为异常检测问题。在这个领域，异常检测面临的挑战包括数据量以及数据的动态性质，因为故障是由多种因素引起的。表 15 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")中说明了在各个行业中应用的一些 DAD 技术。

表 15：工业操作中使用的 DAD 技术示例。CNN：卷积神经网络，LSTM：长短期记忆网络，GRU：门控递归单元，DNN：深度神经网络，AE：自编码器，DAE：去噪自编码器，SVM：支持向量机，SDAE：堆叠去噪自编码器，RNN：递归神经网络。

| 技术 | 部分 | 参考文献 |
| --- | --- | --- |
| LSTM | 第 11.7 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") | inoue2017anomaly, thi2017one, kravchik2018detecting, huang2018deep, park2018lired, chang2018review |
| AE | 部分 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  yuan2015distributed, araya2017ensemble, qu2017detection, sakurada2014anomaly, bhattad2018detecting |
| DNN | 部分 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  lodhi2017power |
| CNN | 部分 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或组异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  faghih2016deep, christiansen2016deepanomaly, lee2016convolutional, faghih2016deep, dong2016camera, nanduri2016anomaly, fuentes2017robust, huang2018deep, chang2018review |
| SDAE,DAE | 节点  11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测综述") |  yan2015accurate, luo2017gas, dai2017cleaning |
| RNN | 节点  11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测综述") |  banjanovic2017neural, thi2017one |
| 混合模型 (DNN-SVM) | 节点  10.3 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习异常检测综述") |  inoue2017anomaly |

### 9.9 时间序列中的异常检测

记录在一段时间内连续的数据称为时间序列。时间序列数据可以大致分为单变量时间序列和多变量时间序列。在单变量时间序列中，只有一个变量（或特征）随时间变化。例如，从房间内的温度传感器每秒收集的数据就是单变量时间序列数据。多变量时间序列包含多个随时间变化的变量（或特征）。一个每秒为每个轴 $(x,y,z)$ 生成三维数据的加速度计就是多变量时间序列数据的完美例子。在文献中，单变量和多变量时间序列中的异常类型被分类为以下几组：（1）点异常。8.4.1 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") （2）上下文异常。8.4.2 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") （3）集体异常。8.4.3 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey")。近年来，许多深度学习模型已被提出用于检测单变量和多变量时间序列数据中的异常，如表 16 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 和表 17 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 分别所示。使用深度学习模型检测时间序列中的异常面临的一些挑战是：

+   •

    异常发生的定义模式可能未被明确。

+   •

    输入数据中的噪声严重影响算法的性能。

+   •

    随着时间序列数据长度的增加，计算复杂度也会增加。

+   •

    时间序列数据通常是非平稳的、非线性的，并且动态演变。因此，DAD 模型应能够实时检测异常。

#### 9.9.1 单变量时间序列深度异常检测

深度学习领域的进展提供了提取丰富层次特征的机会，这可以大大提高单变量时间序列数据中的异常检测能力。有关单变量和多变量时间序列数据异常检测算法的行业标准工具和数据集（包括基于深度学习和非深度学习的）列表，已在 Github 仓库 [`github.com/rob-med/awesome-TS-anomaly-detection`](https://github.com/rob-med/awesome-TS-anomaly-detection) 上展示和维护。表 16 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 说明了在单变量时间序列数据中用于异常检测的各种深度架构。

表 16：用于单变量时间序列数据的 DAD 技术示例。CNN：卷积神经网络，GAN：生成对抗网络，DNN：深度神经网络，AE：自编码器，DAE：去噪自编码器，VAE：变分自编码器，SDAE：堆叠去噪自编码器，LSTM：长短期记忆网络，GRU：门控循环单元 RNN：递归神经网络，RNN：复制神经网络

| 技术 | 部分 | 参考文献 |
| --- | --- | --- |
| LSTM | 部分 11.7 | shipmon2017time, hundman2018detecting, zhu2017deep, malhotra2015long, chauhan2015anomaly, assendorp2017deep, ahmad2017unsupervised, malhotra2016lstm, bontemps2016collective, taylor2016anomaly, cheng2016ms, loganathan2018sequence, chauhan2015anomaly, malhotra2015long, gorokhov2017convolutional, munir2018deepant |
| AE, LSTM-AE, CNN-AE, GRU-AE | 部分 11.8 | Dominique, malhotra2016multi, filonov2016multivariate, sugimoto2018deep, oh2018residual, ebrahimzadehmulti, veeramachaneni2016ai, dau2014anomaly |
| RNN | 部分 11.7 | wielgosz2017recurrent, saurav2018online, wielgosz2018model, guo2016robust, filonov2017rnn |
| CNN, CNN-LSTM | 章节  11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：调查") 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：调查") |  kanarachos2017detecting, dumodeling, gorokhov2017convolutional, napoletano2018anomaly, shanmugam2018jiffy,medel2016anomaly |
| LSTM-VAE | 部分 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测: 调查"), 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测: 调查") | park2018multimodal, solch2016variational |
| DNN | 部分 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测: 调查") | amarasinghe2018toward |
| GAN | 部分  11.5 |  li2018anomaly, zenati2018efficient, lim2018doping, laptevanogen,wei2018unsupervised |

#### 9.9.2 多变量时间序列深度异常检测

多变量时间序列数据中的异常检测是一项具有挑战性的任务。有效的多变量异常检测能够实现故障隔离诊断。基于 RNN 和 LSTM 的方法 ⁴⁴4[`github.com/pnnl/safekit`](https://github.com/pnnl/safekit) 在检测多变量时间序列数据集中的可解释异常方面表现良好。DeepAD 是一个基于深度学习的多变量时间序列异常检测通用框架，由 (buda2018deepad) 提出。利用深度注意力模型设计的可解释异常检测系统在解释检测到的异常方面非常有效 (yuan2018muvan; guo2018exploring)。表  17 说明了在多变量时间序列数据中用于异常检测的各种深度架构。

表 17: 用于多变量时间序列数据的 DAD 技术示例。CNN：卷积神经网络，GAN：生成对抗网络，DNN：深度神经网络，AE：自编码器，DAE：去噪自编码器，VAE：变分自编码器，SDAE：堆叠去噪自编码器，LSTM：长短期记忆网络，GRU：门控递归单元

| 技术 | 部分 | 参考文献 |
| --- | --- | --- |
| LSTM | 部分  11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础上的异常检测的不同方面 ‣ 深度学习异常检测综述") |  nucci2018real, hundman2018detecting, Assendorp2017DeepLF, nolle2018binet |
| AE,LSTM-AE,CNN-AE,GRU-AE | 部分  11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础上的异常检测的不同方面 ‣ 深度学习异常检测综述") |  zhang2018deep guo2018multidimensional, fu2019aircraft, kieu2018outlier |
| CNN, CNN-LSTM | 节 11.6, 11.7 | basumallik2019packet, shanmugam2018jiffy |
| LSTM-VAE | 章节 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述"), 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") |  ikeda2018estimation, park2018multimodal |
| GAN | 章节 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") |  assendorp2017deep, li2018anomaly, li2019mad cowton2018combined |
| DNN-RNN | 部分 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于的异常检测的不同方面 ‣ 异常检测中的深度学习: 综述") | tuor2017deep, tuor2018recurrent |

⟦!htbp⟧ ⟦t⟧ 数据集描述 参考文献 NASA 航天飞机阀门数据¹ 包括来自火星科学实验室和 SMAP 任务的航天器异常数据及实验 hundman2018detecting² 船只³ 船只行为异常检测的多变量时间序列数据分析 multivariate17 SWaT 和 WADI 安全水处理 (SWaT) 和水分配 (WADI) li2019mad 信用卡欺诈检测 匿名化的信用卡交易，标记为欺诈或真实 dal2015calibrating 纽约市出租车乘客数量⁵ 纽约市出租车乘客数据流 cui2016comparative

表 18: 多变量异常检测中使用的数据集。

+   •

    ⟦1⟧ [`cs.fit.edu/~pkc/nasa/data/`](https://cs.fit.edu/~pkc/nasa/data/)

+   •

    ⟦2⟧ [`github.com/khundman/telemanom`](https://github.com/khundman/telemanom)

+   •

    ⟦3⟧ [`conferences.inf.ed.ac.uk/EuroDW2018/papers/eurodw18-Maia.pdf`](http://conferences.inf.ed.ac.uk/EuroDW2018/papers/eurodw18-Maia.pdf)

+   •

    ⟦4⟧ [`www.kaggle.com/peterkim95/multivariate-gaussian-anomaly-detection/data`](https://www.kaggle.com/peterkim95/multivariate-gaussian-anomaly-detection/data)

+   •

    ⟦5⟧ [`github.com/chickenbestlover/RNN-Time-series-Anomaly-Detection`](https://github.com/chickenbestlover/RNN-Time-series-Anomaly-Detection)

表 19: 视频监控中使用的 DAD 技术示例。CNN: 卷积神经网络，LSTM: 长短期记忆网络 RBM: 受限玻尔兹曼机，DNN: 深度神经网络 AE: 自编码器，DAE: 去噪自编码器 OCSVM: 一类支持向量机，CAE: 卷积自编码器 SDAE: 堆叠去噪自编码器，STN: 空间变换网络

| 使用的技术 | 部分 | 参考文献 |
| --- | --- | --- |
| CNN | 第  11.6 | dong2016camera,andrewsaanomaly,sabokrou2016fully,sabokrou2017deep,munawar2017spatio,li2017transferred,qiao2017abnormal,tripathi2018convolutional,nogas2018deepfall,christiansen2016deepanomaly,li2017transferred, |
| SAE (AE-CNN-LSTM) | 第 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：一项综述"), 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：一项综述"), 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：一项综述") | chong2017abnormal, qiao2017abnormal, khaleghi2018improved |
| AE | 第 11.8 | qiao2017abnormal, yang2015unsupervised, chen2015detecting, gutoskidetection, d2017autoencoder, dotti2017unsupervised, yang2015unsupervised, chen2015detecting, sabokrou2016video, tran2017anomaly, chen2015detecting, d2017autoencoder, hasan2016learning, yang2015unsupervised, cinelli2017anomaly, sultani2018real |
| 混合模型（CAE-OCSVM） | 第 10.3 | gutoskidetection, dotti2017unsupervised |
| LSTM-AE | 部分 11.7, 11.8 | d2017autoencoder |
| STN | 部分 11.2 | chianucci2016unsupervised |
| RBM | 章节 11.1 ‣ 11 定位异常的深度神经网络架构 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") | munawar2017spatio |
| LSTM | 章节 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") | medel2016anomaly, luo2017remembering, ben2018attentioned, singh2017anomaly |
| RNN | 章节 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") | luo2017revisit, zhou2015abnormal, hu2016video, chong2015modeling |
| AAE | 章节  11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督式深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  ravanbakhsh2017training |

### 9.10 视频监控

视频监控，也被称为闭路电视 (CCTV)，涉及监控指定的关注区域以确保安全。在视频监控应用中，未标记的数据量巨大，这对监督式机器学习和深度学习方法构成了重大挑战。因此，由于缺乏标记数据，视频监控应用被建模为异常检测问题。一些研究工作已经研究了最先进的深度模型用于视频异常检测，并根据模型类型和检测标准对其进行了分类  (kiran2018overview; chong2015modeling)。关于 robust 24/7 视频监控系统的挑战，详细讨论见  (boghossian2005challenges)。在实际视频监控中缺乏对异常的明确定义也是一个显著问题，这影响了 DAD 方法的性能。视频监控中使用的 DAD 技术在表  19 ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督式深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基于异常检测的不同方面 ‣ 深度学习用于异常检测：综述")中进行了说明。

## 10 深度异常检测 (DAD) 模型

在本节中，我们讨论了根据标签的可用性和训练目标分类的各种 DAD 模型。对于每种模型类型领域，我们讨论以下四个方面：—假设；—模型架构的类型；—计算复杂性；—优缺点；

### 10.1 监督式深度异常检测

与无监督异常检测技术相比，有监督异常检测技术的性能更优，因为这些技术使用标记样本（gornitz2013toward）。有监督异常检测从一组注释数据实例（训练）中学习分隔边界，然后使用学习到的模型将测试实例分类为正常或异常类别（测试）。假设：深度监督学习方法依赖于分隔数据类别，而无监督技术则侧重于解释和理解数据的特征。基于多类别分类的异常检测技术假设训练数据包含多个正常类别的标记实例（shilton2013combined；jumutc2014multi；kim2015deep；erfani2017shared）。多类别异常检测技术学习一个分类器，以区分异常类别与其余类别。通常，基于监督深度学习的异常检测分类方案有两个子网络，一个是特征提取网络，另一个是分类器网络。深度模型需要大量的训练样本（以千计或百万计）来学习特征表示，以有效区分各种类别实例。由于缺乏干净的数据标签，有监督深度异常检测技术不像半监督和无监督方法那样流行。计算复杂性：基于深度监督异常检测方法的计算复杂性取决于输入数据维度和使用反向传播算法训练的隐藏层数量。高维数据往往具有更多的隐藏层，以确保输入特征的有意义的分层学习。计算复杂性也随着隐藏层数量线性增加，并需要更长的模型训练和更新时间。

优势和劣势：有监督的 DAD 技术的优点如下：

+   •

    有监督的 DAD 方法比半监督和无监督模型更准确。

+   •

    分类基于技术的测试阶段非常快速，因为每个测试实例需要与预先计算的模型进行比较。

有监督的 DAD 技术的缺点如下：

+   •

    多类别监督技术需要准确的标签来表示各种正常类别和异常实例，这通常是不可用的。

+   •

    如果特征空间高度复杂且非线性，深度监督技术无法将正常数据与异常数据分开。

### 10.2 半监督深度异常检测

半监督或（单类分类）DAD 技术假设所有训练实例只有一个类别标签。kiran2018overview 和 min2018ids 提供了基于深度学习的半监督异常检测技术的综述。DAD 技术学习围绕正常实例的判别边界。与多数类不符的测试实例被标记为异常（perera2018learning；blanchard2010semi）。各种半监督 DAD 模型架构如表 20 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") 中进行了说明。

表 20：半监督 DAD 模型概述 AE：自编码器，DAE：去噪自编码器，KNN：K-最近邻，CorGAN：腐蚀生成对抗网络，DBN：深度置信网络，AAE：对抗自编码器，CNN：卷积神经网络，SVM：支持向量机。

| 技术 | 部分 | 参考文献 |
| --- | --- | --- |
| AE | 部分 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") | edmunds2017deep，estiri2018semi |
| RBM | 章节 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") |  jia2014novel |
| DBN | 章节 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") |  wulsin2010semi, wulsin2011modeling |
| CorGAN,GAN | 章节 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习在异常检测中的应用：综述") |  gu2018semi  akcay2018ganomaly, sabokrou2018adversarially |
| AAE | 部分 11.5 |  dimokranitou2017adversarial |
| 混合模型 (DAE-KNN altman1992introduction), (DBN-随机森林 ho1995random), CNN-Relief kira1992feature, CNN-SVM cortes1995support | 部分 8.3.1 |  song2017hybrid, shi2017semi, zhu2018hybrid |
| CNN | 部分 11.6 |  racah2017extremeweather, perera2018learning |
| RNN | 章节 11.7 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") |  wu2018semi |
| GAN | 章节 11.5 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") |  kliger2018novelty, gu2018semi |

假设：提出的半监督 DAD 方法依赖于以下假设之一，以对数据实例进行异常评分。

+   •

    **接近性**与**连续性**：在输入空间和学习特征空间中相互接近的点更可能共享相同的标签。

+   •

    **鲁棒的特征**在深度神经网络的隐藏层中学习，并保留了区分正常数据点与异常数据点的属性。

计算复杂度：半监督 DAD 方法的计算复杂度类似于监督 DAD 技术，主要取决于输入数据的维度和用于代表性特征学习的隐藏层数量。

优点与缺点：半监督深度异常检测技术的优点如下：

+   •

    在半监督学习模式下训练的生成对抗网络（GANs）显示出极大的潜力，即使有非常少的标记数据。

+   •

    使用标记数据（通常为单一类别）可以在性能上显著优于无监督技术。

半监督技术所呈现的基本缺点（lu2009fundamental）即使在深度学习背景下也适用。此外，隐藏层中提取的层次特征可能无法代表较少的异常实例，因此容易出现过拟合问题。

表 21：混合 DAD 技术的示例。CNN：卷积神经网络，LSTM：长短期记忆网络，DBN：深度置信网络，DNN：深度神经网络。AE：自编码器，DAE：去噪自编码器，SVM：支持向量机 cortés1995support，SVDD：支持向量数据描述，RNN：递归神经网络 Relief：特征选择算法 kira1992feature，KNN：K-近邻算法 altman1992introduction，CSI：捕获、评分和整合 ruchansky2017csi。

| 技术 | 部分 | 参考文献 |
| --- | --- | --- |
| AE-OCSVM，AE-SVM | 部分 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习异常检测的不同方面 ‣ 深度学习用于异常检测：综述"), | andrews2016detecting |
| DBN-SVDD，AE-SVDD | 部分 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习异常检测的不同方面 ‣ 深度学习用于异常检测：综述"), | erfani2016high，kim2015deep |
| DNN-SVM | 21D | inoue2017anomaly |
| DAE-KNN，DBN-Random Forest ho1995random，CNN-Relief，CNN-SVM | 部分 11.1 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 杂项技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习异常检测的不同方面 ‣ 深度学习用于异常检测：综述")，11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  song2017hybrid，shi2017semi，zhu2018hybrid；urbanowicz2018relief |
| AE-CNN, AE-DBN | 部分 11.1 ‣ 11 定位异常的深度神经网络架构 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 其他技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测：综述"), 11.6 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测：综述"), 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  wang2018effective, li2015hybrid |
| AE+ KNN | 第 11.8 |  song2017hybrid |
| CNN-LSTM-SVM | 第 11.6, 11.7 |  wei2017new |
| RNN-CSI | 节 11.7 |  ruchansky2017csi |
| CAE-OCSVM | 节 11.8 |  gutoskidetection,  dotti2017unsupervised |

### 10.3 混合深度异常检测

深度学习模型被广泛用作特征提取器，以学习鲁棒特征 (andrews2016detecting)。在深度混合模型中，深度模型中学到的代表性特征被输入到传统算法，如单类径向基函数（RBF）、支持向量机（SVM）分类器。混合模型采用两步学习，并显示出最新的成果 (erfani2016high; erfani2016robust; wu2015harvesting)。用于异常检测的深度混合架构见表 21。

假设：用于异常检测的深度混合模型依赖于以下假设之一来检测异常值：

+   •

    在深度神经网络的隐藏层中提取的鲁棒特征，有助于分离那些可能掩盖异常存在的无关特征。

+   •

    在复杂的高维空间中构建一个稳健的异常检测模型需要特征提取器和异常检测器。各种异常检测器的使用情况在表格 21 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测。 ‣ 8.4 异常类型 ‣ 8.3.2 一类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 有监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测的不同方面。 ‣ 深度学习在异常检测中的应用：综述") 中进行了说明。

计算复杂性：混合模型的计算复杂性包括深度架构和内部使用的传统算法的复杂性。此外，深度网络架构和参数的非平凡选择问题涉及在较大的空间中搜索优化参数，从而引入了混合模型中使用深层的计算复杂性。此外，经典算法如线性 SVM 的预测复杂性为 $O(d)$，其中 d 是输入维度的数量。对于大多数核，包括多项式和 RBF，复杂性为 $O(nd)$，其中 $n$ 是支持向量的数量，但对于使用 RBF 核的 SVM，通常考虑 $O(d^{2})$ 的近似复杂性。

优势和劣势 混合 DAD 技术的优势如下：

+   •

    特征提取器显著减少了“维度诅咒”，特别是在高维领域中。

+   •

    混合模型更具可扩展性和计算效率，因为线性或非线性核模型在降维输入上操作。

混合 DAD 技术的显著劣势包括：

+   •

    混合方法是不够理想的，因为它无法影响特征提取器的隐藏层中的表示学习，因为使用的是通用损失函数而不是针对异常检测定制的目标函数。

+   •

    如果个别层是(saxe2011random)，则深层混合模型的表现往往更好，但这会引入计算开销。

### 10.4 一类神经网络 (OC-NN) 在异常检测中的应用

一类神经网络（OC-NN）结合了深度网络提取逐步丰富的数据表示的能力以及一类目标，例如超平面 (chalapathy2018anomaly) 或超球面 (ruff2018deep)，以将所有正常数据点与异常点分开。OC-NN 方法的新颖性在于以下关键原因：隐藏层中的数据表示是通过优化为异常检测定制的目标函数来学习的，正如实验结果所示 (chalapathy2018anomaly; ruff2018deep) 证明，OC-NN 可以在复杂数据集上实现与现有最先进方法相当或更好的性能，同时相比现有方法具有合理的训练和测试时间。

假设：为异常检测提出的 OC-NN 模型依赖以下假设来检测异常点：

+   •

    OC-NN 模型在深度神经网络的隐藏层中提取数据分布中的共同变化因素。

+   •

    执行联合表示学习，并为测试数据实例生成异常分数。

+   •

    异常样本不包含共同的变化因素，因此隐藏层无法捕捉异常点的表示。

计算复杂性：OC-NN 模型的计算复杂性与混合模型相比，只包括所选深度网络的复杂性 (saxe2011random)。OC-NN 模型不需要存储数据以进行预测，因此具有非常低的内存复杂性。然而，很明显，OC-NN 的训练时间与输入维度成正比。

优势和劣势：OC-NN 的优势如下：

+   •

    OC-NN 模型在输出空间中优化一个数据包络超球面或超平面的同时联合训练深度神经网络。

+   •

    OC-NN 提出了一个交替最小化算法，用于学习 OC-NN 模型的参数。我们观察到，OC-NN 目标的子问题等同于解决一个量分选问题，这个问题是明确定义的。

OC-NN 在异常检测方面的显著劣势是：

+   •

    对于高维输入数据，训练时间和模型更新时间可能更长。

+   •

    由于输入空间的变化，模型更新也需要更长时间。

### 10.5 无监督深度异常检测

无监督 DAD 是基础机器学习研究和工业应用中的一个重要研究领域。提出了若干种深度学习框架来应对无监督异常检测中的挑战，并且这些框架如表 22 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础上的异常检测不同方面 ‣ 深度学习异常检测：调查") 所示，表现出最先进的性能。自编码器是用于异常检测的基本无监督深度架构 (baldi2012autoencoders)。

表 22：无监督 DAD 技术示例。CNN：卷积神经网络，LSTM：长短期记忆网络，DNN：深度神经网络，GAN：生成对抗网络，AE：自编码器，DAE：去噪自编码器，SVM：支持向量机，STN：空间变换网络，RNN：递归神经网络，AAE：对抗自编码器，VAE：变分自编码器。

| 技术 | 部分 | 参考文献 |
| --- | --- | --- |
| LSTM | 部分 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签 ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础上的异常检测不同方面 ‣ 深度学习异常检测：调查") | singh2017anomaly, chandola2008comparative, dasigi2014modeling, malhotra2015long |

| AE | 章节 11.8 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  abati2018and、zong2018deep、tagawa2015structured、dau2014anomaly、sakurada2014anomaly、wu2015adaptive、xu2015learning、hawkins2002outlier、zhao2015robust、qi2014robust、chalapathy2017robust、yang2015unsupervised、

zhai2016deep、lyudchik2016outlier、lu2017unsupervised、mehrotra2017deep、meng2018relational、parchami2017using |

| STN | 章节 11.2 ‣ 11 深度神经网络架构用于定位异常 ‣ 10.6.6 统计技术深度异常检测 ‣ 10.6 其他技术 ‣ 10 深度异常检测 (DAD) 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  chianucci2016unsupervised |
| --- | --- | --- |
| GAN | 章节 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测的应用 ‣ 8.5.2 标签： ‣ 8.5 DAD 技术的输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 基于深度学习的异常检测的不同方面 ‣ 深度学习用于异常检测：综述") |  lawson2017finding |
| RNN | 部分 11.7 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测不同方面 ‣ 深度学习用于异常检测：综述") |  dasigi2014modeling,filonov2017rnn |
| AAE | 部分 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测不同方面 ‣ 深度学习用于异常检测：综述") |  dimokranitou2017adversarial, leveau2017adversarial |
| VAE | 部分 11.5 模型 ‣ 9.10 视频监控 ‣ 9 深度异常检测应用 ‣ 8.5.2 标签: ‣ 8.5 DAD 技术输出 ‣ 8.4.3 集体或群体异常检测 ‣ 8.4 异常类型 ‣ 8.3.2 单类神经网络 (OC-NN) ‣ 8.3 基于训练目标 ‣ 8.2.3 无监督深度异常检测 ‣ 8.2.2 半监督深度异常检测 ‣ 8.2.1 监督深度异常检测 ‣ 8.2 基于标签的可用性 ‣ 8 深度学习基础的异常检测不同方面 ‣ 深度学习用于异常检测：综述") |  an2015variational, suh2016echo, solch2016variational, xu2018unsupervised, mishra2017generative |

假设：用于异常检测的深度无监督模型依赖于以下假设之一来检测离群点：

+   •

    “正常”区域与原始或潜在特征空间中的“异常”区域可以区分。

+   •

    大多数数据实例与数据集的其余部分相比是正常的。

+   •

    无监督异常检测算法基于数据集的内在属性（如距离或密度）生成数据实例的异常值评分。深度神经网络的隐藏层旨在捕捉数据集中的这些内在属性（goldstein2016comparative）。

计算复杂度：自编码器是用于异常检测的最常见架构，其具有二次成本，优化问题是非凸的，类似于其他任何神经网络架构。模型的计算复杂度取决于操作数量、网络参数和隐藏层。然而，训练自编码器的计算复杂度远高于传统方法，如主成分分析（PCA），因为 PCA 基于矩阵分解（meng2018relational；parchami2017using）。

优势和劣势：无监督深度异常检测技术的优势如下：

+   •

    学习数据的内在特征以将正常数据点与异常数据点区分开。这项技术识别数据中的共性并促进异常检测。

+   •

    成本效益高的技术来发现异常，因为它不需要标注数据来训练算法。

无监督深度异常检测技术的显著劣势是：

+   •

    在复杂和高维空间中，常常很难学习数据中的共性。

+   •

    在使用自编码器时，选择合适的压缩程度，即降维，通常是一个需要调整的超参数，以获得最佳结果。

+   •

    无监督技术对噪声和数据损坏非常敏感，通常不如监督或半监督技术准确。

### 10.6 杂项技术

本节探讨了各种被证明有效且有前景的 DAD 技术，我们讨论了这些技术背后的关键思想及其适用领域。

#### 10.6.1 基于迁移学习的异常检测

深度学习长期以来因需要足够的数据来产生良好结果而受到批评。litjens2017survey 和 pan2010survey 评审了深度迁移学习方法，并说明了其学习良好特征表示的意义。迁移学习是解决训练数据不足的基本问题的一个重要工具。它旨在通过放宽训练数据和未来数据必须处于相同特征空间且具有相同分布的假设，将知识从源领域转移到目标领域。深度迁移表示学习已由（andrews2016transfer; vercruyssen2017transfer; li2012detecting; almajai2012anomaly; kumar2017transfer; liang2018transfer）探索，结果显示出非常有前景的结果。使用迁移学习进行异常检测的开放研究问题是迁移能力的程度，即定义特征如何转移知识并改善从一个任务到另一个任务的分类性能。

#### 10.6.2 基于零样本学习的异常检测

零样本学习（ZSL）旨在识别训练集中从未见过的对象（romera2015embarrassingly）。ZSL 在两个阶段中实现这一目标：首先，捕获关于对象的自然语言描述或属性（通常称为元数据）的知识，其次，将这些知识用于在新的类别集内对实例进行分类。这个设置在现实世界中很重要，因为可能无法在训练时获得所有可能类别的图像。与这种方法相关的主要挑战是获取数据实例的元数据。然而，使用 ZSL 进行异常检测和新颖性检测的几种方法已被证明产生了最先进的结果（mishra2017generative; socher2013zero; xian2017zero; liu2017generalized; rivero2017grassmannian）。

#### 10.6.3 基于集成的异常检测

深度神经网络的一个显著问题是它们对输入数据中的噪声非常敏感，并且通常需要大量的训练数据才能稳定地执行（kim2016lstm）。为了在噪声数据中实现鲁棒性，随机变化自编码器的连接架构的想法已被证明能获得显著更好的性能。chen2017outlier 通过包含各种随机连接自编码器的自编码器集群进行了实验，在几个基准数据集上取得了有希望的结果。集成方法仍然是一个活跃的研究领域，已被证明可以提高多样性，从而避免过拟合问题，同时减少训练时间。

#### 10.6.4 基于聚类的异常检测

文献中已提出了几种基于聚类的异常检测算法 (ester1996density)。聚类涉及根据提取的特征将相似的模式分组，以检测新的异常。随着需要聚类的类别数量的增加，时间和空间复杂度线性增长 (sreekanth2010generalized)，这使得基于聚类的异常检测在实时实际应用中显得不可行。通过在深度神经网络的隐藏层中提取特征来降低输入数据的维度，这确保了对复杂和高维数据集的可扩展性。深度学习启用的聚类方法异常检测利用例如 word2vec (mikolov2013efficient) 模型来获取正常数据和异常的语义表示，形成聚类并检测离群点 (yuan2017deep)。一些工作依赖于与自编码器一起使用的混合模型变体，以获得用于聚类的代表性特征，从而发现异常。

#### 10.6.5 基于深度强化学习 (DRL) 的异常检测

深度强化学习 (DRL) 方法因其在高维数据空间中学习复杂行为的能力而引起了广泛关注。利用深度强化学习检测异常的努力已经被 (de2017learning; rlanomaly) 提出。基于 DRL 的异常检测器不考虑异常概念的任何假设，通过不断增强其知识来识别新的异常。基于 DRL 的异常检测是一个非常新颖的概念，需要进一步调查和识别研究差距及其应用。

#### 10.6.6 统计技术深度异常检测

希尔伯特变换是一种统计信号处理技术，它推导了实值信号的解析表示。此属性被 (kanarachos2015anomaly) 用于实时检测健康相关时间序列数据集中的异常，显示出这是一个非常有前景的技术。该算法以顺序的方式结合了小波分析、神经网络和希尔伯特变换的能力，以检测实时异常。统计技术深度异常检测 (DAD) 技术的话题需要进一步研究，以全面理解它们的潜力和适用性。

## 11 深度神经网络架构用于定位异常

### 11.1 深度神经网络 (DNN)

“深度”在“深度神经网络”中指的是通过数据特征提取的层数 (schmidhuber2015deep; bengio2009learning)。深度架构克服了传统机器学习方法在可扩展性和对数据中新变异的泛化能力 (lecun2015deep) 以及对手动特征工程的需求的限制。深度信念网络（DBNs）是一类深度神经网络，包含多个图形模型层，这些模型被称为限制玻尔兹曼机（RBMs）。使用 DBNs 进行异常检测的假设是 RBMs 被用作具有反向传播算法的有向编码器-解码器网络 (werbos1990backpropagation)。DBNs 无法捕捉异常样本的特征变异，导致重建误差较高。DBNs 已证明能够有效扩展到大数据，并提高解释能力 (wulsin2010semi)。

### 11.2 时空网络 (STN)

研究人员长期以来一直探索学习空间和时间关系特征的技术 (zhang2018detecting)。深度学习架构在学习空间方面（使用 CNNs）和时间特征（使用 LSTMs）方面表现良好。时空网络 (STNs) 结合了深度神经架构，结合了 CNNs 和 LSTMs 以提取时空特征。时间特征（通过 LSTM 建模临近时间点之间的相关性），空间特征（通过局部 CNNs 建模局部空间相关性）已被证明在检测异常值方面有效 (lee2018stan; szeker2014spatio; nie2018spatio; dereszynski2011spatiotemporal)。

### 11.3 求和-乘积网络 (SPN)

求和-乘积网络 (SPNs) 是具有变量作为叶子节点的有向无环图，内部节点和加权边构成了求和和乘积。SPNs 被认为是混合模型的组合，能够在多层上进行快速精确的概率推断 (poon2011sum; peharz2018probabilistic)。SPNs 的主要优点在于，与图形模型不同，SPNs 在高树宽模型上更易追踪，而不需要近似推断。此外，SPNs 已证明能够以令人信服的方式捕捉输入的不确定性，从而实现稳健的异常检测 (peharz2018probabilistic)。SPNs 在众多数据集上表现出色，但关于异常值检测仍有许多需要进一步探索的地方。

### 11.4 Word2vec 模型

Word2vec 是一组用于生成词嵌入的深度神经网络模型（mikolov2013efficient）。这些模型能够捕捉数据实例（如句子、时间序列数据）中的顺序关系。获取词嵌入特征作为输入已被证明能提高多个深度学习架构的性能（rezaeinia2017improving; naili2017comparative; altszyler2016comparative）。利用 word2vec 嵌入的异常检测模型被证明能显著提高性能（schnabel2015evaluation; bertero2017experience; bakarov2018anomaly; bamler2017dynamic）。

### 11.5 生成模型

生成模型旨在学习准确的数据分布，以生成具有一些变化的新数据点。两种最常见和高效的生成方法是变分自编码器（VAE）（kingma2013auto）和生成对抗网络（GAN）（NIPS2014_5423; goodfellow2014generative）。一种称为对抗自编码器（AAE）的 GAN 架构变体（makhzani2015adversarial），通过对抗训练在自编码器隐藏层学习的潜在编码上施加任意先验，也被证明能有效地学习输入分布。利用这种学习输入分布的能力，提出的几个基于生成对抗网络的异常检测（GAN-AD）框架（li2018anomaly; deecke2018anomaly; schlegl2017unsupervised; ravanbakhsh2017abnormal; eide2018applying）在高维和复杂数据集上的异常检测中表现有效。然而，与深度生成模型相比，传统方法如 K 近邻（KNN）在异常数量较少的情况下表现更好（vskvara2018generative）。

### 11.6 卷积神经网络

卷积神经网络（CNN）是分析视觉图像的热门神经网络选择（krizhevsky2012imagenet）。CNN 从高维数据中提取复杂隐藏特征的能力使其可以作为特征提取器用于顺序和图像数据集的异常检测（gorokhov2017convolutional; kim2014convolutional）。基于 CNN 的异常检测框架的评估仍然是一个活跃的研究领域（kwon2018empirical）。

### 11.7 序列模型

循环神经网络（RNNs） (williams1989complexity) 已被证明能够捕捉时间序列数据的特征。RNNs 的局限性在于随着时间步的增加，它们无法捕捉上下文，为了解决这个问题，引入了长短期记忆（LSTM）(hochreiter1997long) 网络，它们是一种特殊类型的 RNNs，包含一个可以存储先前时间步信息的记忆单元。门控循环单元（GRU）(cho2014learning) 类似于 LSTM，但使用一组门来控制信息的流动，而不是单独的记忆单元。由于其在各种工程问题中的应用，序列数据中的异常检测在文献中引起了广泛关注，如第 9.9 ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 章节所示。基于长短期记忆（LSTM）神经网络的异常检测算法已经被研究，并报告显示其在性能上显著优于传统方法 (ergen2017unsupervised)。

### 11.8 自编码器

具有单层和线性激活函数的自编码器与主成分分析（PCA）（pearson1901liii）几乎等效。虽然 PCA 限于线性降维，自编码器则可以实现线性或非线性变换（liou2008modeling; liou2014autoencoder）。自编码器的一个热门应用是异常检测。自编码器也被称为复制神经网络（RNN）（hawkins2002outlier，williams2002comparative）。自编码器通过重构输入数据来表示数据在多个隐藏层中的形式，从而有效地学习了一个身份函数。当自编码器仅在正常数据实例（在异常检测任务中占多数）上进行训练时，它们无法重构异常数据样本，从而产生较大的重构误差。产生高残差误差的数据样本被认为是离群点。图 13 Models ‣ 9.10 Video Surveillance ‣ 9 Applications of Deep Anomaly Detection ‣ 8.5.2 Labels: ‣ 8.5 Output of DAD Techniques ‣ 8.4.3 Collective or Group Anomaly Detection. ‣ 8.4 Type of Anomaly ‣ 8.3.2 One-Class Neural Networks (OC-NN) ‣ 8.3 Based on the training objective ‣ 8.2.3 Unsupervised deep anomaly detection ‣ 8.2.2 Semi-supervised deep anomaly detection ‣ 8.2.1 Supervised deep anomaly detection ‣ 8.2 Based on Availability of labels ‣ 8 Different aspects of deep learning-based anomaly detection. ‣ Deep Learning for Anomaly Detection: A Survey") 中展示的几种自编码器架构变体在异常检测中产生了有希望的结果。自编码器架构的选择取决于数据的性质，卷积网络更适合图像数据集，而基于长短期记忆（LSTM）的模型在序列数据上往往产生良好的结果。将卷积层和 LSTM 层相结合的努力，其中编码器是卷积神经网络（CNN），解码器是多层 LSTM 网络以重构输入图像，被证明在检测数据中的异常时非常有效。使用组合模型，如门控递归单元自编码器（GRU-AE）、卷积神经网络自编码器（CNN-AE）、长短期记忆自编码器（LSTM-AE），消除了准备手工特征的需要，并在异常检测任务中支持使用原始数据，最小化预处理。尽管自编码器是简单而有效的离群点检测架构，但由于噪声训练数据，性能会下降（zhou2017anomaly）。

<svg height="48.89" overflow="visible" version="1.1" width="657.64"><g transform="translate(0,48.89) matrix(1 0 0 -1 0 0) translate(328.82,0) translate(0,24.44) matrix(1.0 0.0 0.0 1.0 -324.21 -19.83)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1 0 0 -1 0 19.835)"><g transform="matrix(1 0 0 1 0 19.83)"><g transform="matrix(1 0 0 -1 0 0) translate(324.21,0) matrix(1.0 0.0 0.0 1.0 -319.6 5.53)" fill="#000000" stroke="#000000"><foreignobject width="20.76" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">\Tree⟦.自编码器 ⟦.图像 ⟦CAE CNN-AE CNN-LSTM-AE DAE ⟧ ⟧ ⟦.序列数据 ⟦ LSTM-AE GRU-AE AE SDAE ⟧⟧⟧</foreignobject></g></g></g></g></svg>

图 13：用于异常检测的自编码器架构。 AE：自编码器 liou2014autoencoder，LSTM：长短期记忆网络 hochreiter1997long，SDAE：堆叠去噪自编码器 vincent2010stacked，DAE：去噪自编码器 vincent2010stacked，GRU：门控递归单元 cho2014learning，CNN：卷积神经网络 krizhevsky2012imagenet，CNN-LSTM-AE：卷积长短期记忆自编码器 haque2018image，CAE：卷积自编码器 masci2011stacked

## 12 相对优缺点：深度异常检测方法

之前讨论的深度异常检测（DAD）技术各有其独特的优缺点。理解哪种异常检测技术最适合特定的异常检测问题上下文至关重要。鉴于 DAD 是一个活跃的研究领域，不可能为每一个异常检测问题提供这样的理解。因此，在本节中，我们分析了不同类别技术在一些简单问题设置下的相对优缺点。在 10.1 节中说明的基于分类的监督 DAD 技术在正常实例和异常实例数量相等的场景中是更好的选择。监督 DAD 技术的计算复杂性是一个关键方面，特别是在该技术应用于实际领域时。虽然基于分类的监督或半监督技术训练时间较长，但测试通常很快，因为它使用了预训练模型。10.5 节中介绍的无监督 DAD 技术被广泛使用，因为标签获取是一个昂贵且耗时的过程。大多数无监督深度异常检测需要对异常分布做出假设，因此这些模型在处理噪声数据时的鲁棒性较差。10.3 节中展示的混合模型在深度神经网络的隐藏层中提取鲁棒特征，并将其提供给表现最好的经典异常检测算法。混合模型方法是次优的，因为它无法影响隐藏层中的表示学习。10.4 节中描述的单类神经网络（OC-NN）结合了深度网络提取数据逐步丰富表示的能力与单类目标，例如超平面 (chalapathy2018anomaly) 或超球面 (ruff2018deep)，以将所有正常数据点与异常数据点分离。进一步的研究和探索对于更好地理解这一新架构的好处是必要的。

## 13 结论

在这篇综述论文中，我们讨论了基于深度学习的异常检测的各种研究方法及其在不同领域的应用。本文讨论了深度异常检测中的挑战，并提出了几种现有的解决方案。对于每种类别的深度异常检测技术，我们介绍了关于正常数据和异常数据的假设及其优缺点。本综述的目标是调查和识别各种用于异常检测的深度学习模型，并评估其对特定数据集的适用性。在为特定领域或数据选择深度学习模型时，这些假设可以作为评估该领域技术有效性的指导原则。基于深度学习的异常检测仍然是一个活跃的研究领域，未来的一个可能工作是随着更复杂技术的提出，扩展和更新此综述。

## 参考文献

+   1⟧#1 1⟧#1

+   [1] Chandola et al.(2007)Chandola, Banerjee, and Kumar⟧chandola2007outlier Varun Chandola, Arindam Banerjee 和 Vipin Kumar。异常检测：综述。*ACM 计算调查*，2007 年。

+   [2] Hawkins(1980)⟧hawkins D. Hawkins。*异常值识别*。Chapman and Hall，伦敦，1980 年。

+   [3] Javaid et al.(2016)Javaid, Niyaz, Sun, and Alam⟧javaid2016deep Ahmad Javaid, Quamar Niyaz, Weiqing Sun 和 Mansoor Alam。用于网络入侵检测系统的深度学习方法。在*第九届 EAI 国际生物启发信息与通信技术会议（前身为 BIONETICS）论文集*中，第 21–26 页。ICST（计算机科学、社会信息学和电信工程研究所），2016 年。

+   [4] Peng and Marculescu(2015)⟧peng2015multi Huan-Kai Peng 和 Radu Marculescu。多尺度组合性：使用深度学习识别社会动态的组合结构。*PloS one*，10(4)：e0118309，2015 年。

+   [5] Alejandro(2016)⟧deeplearningVstraditionalAlgorithms Bahnsen Alejandro, Correa. 使用深度学习构建 AI 应用程序。2016 年。网址 [`blog.easysol.net/wp-content/uploads/2017/06/image1.png`](https://blog.easysol.net/wp-content/uploads/2017/06/image1.png)。

+   [6] Xie et al.(2017)Xie, Wang, Chen, Shi, and Zhao⟧xie2017real Xuemei Xie, Chenye Wang, Shu Chen, Guangming Shi 和 Zhifu Zhao。基于深度学习的实时非法停车检测系统。在*2017 年国际深度学习技术会议论文集*中，第 23–27 页。ACM，2017 年。

+   [7] Schlegl et al.(2017)Schlegl, Seeböck, Waldstein, Schmidt-Erfurth, and Langs⟧schlegl2017unsupervised Thomas Schlegl, Philipp Seeböck, Sebastian M Waldstein, Ursula Schmidt-Erfurth 和 Georg Langs。使用生成对抗网络进行无监督异常检测以指导标记发现。在*国际医学影像处理会议*中，第 146–157 页。Springer，2017 年。

+   [8] Mohammadi 等 (2017)Mohammadi, Al-Fuqaha, Sorour 和 Guizani⟧mohammadi2017deep Mehdi Mohammadi, Ala Al-Fuqaha, Sameh Sorour 和 Mohsen Guizani。面向物联网大数据和流媒体分析的深度学习：综述。*arXiv 预印本 arXiv:1712.04301*，2017 年。

+   [9] Aggarwal (2013)⟧aggarwal2013introduction Charu C Aggarwal。离群点分析简介。在*离群点分析*，第 1–40 页。Springer，2013 年。

+   [10] Miljković (2010)⟧miljkovic2010review Dubravko Miljković。新颖性检测方法的综述。在*2010 年 MIPRO 第 33 届国际大会论文集*，第 593–598 页。IEEE，2010 年。

+   [11] Pimentel 等 (2014)Pimentel, Clifton, Clifton 和 Tarassenko⟧pimentel2014review Marco AF Pimentel, David A Clifton, Lei Clifton 和 Lionel Tarassenko。新颖性检测的综述。*信号处理*，99:215–249，2014 年。

+   [12] Kwon 等 (2017)Kwon, Kim, Kim, Suh, Kim 和 Kim⟧kwon2017survey Donghwoon Kwon, Hyunjoo Kim, Jinoh Kim, Sang C Suh, Ikkyun Kim 和 Kuinam J Kim。基于深度学习的网络异常检测调查。*集群计算*，第 1–13 页，2017 年。

+   [13] Ball 等 (2017)Ball, Anderson 和 Chan⟧ball2017comprehensive John E Ball, Derek T Anderson 和 Chee Seng Chan。深度学习在遥感中的综合调查：理论、工具和社区挑战。*应用遥感杂志*，11(4):042609，2017 年。

+   [14] Kiran 等 (2018)Kiran, Thomas 和 Parakkal⟧kiran2018overview B Ravi Kiran, Dilip Mathew Thomas 和 Ranjith Parakkal。基于深度学习的方法在视频中的无监督和半监督异常检测的概述。*arXiv 预印本 arXiv:1801.03149*，2018 年。

+   [15] Adewumi 和 Akinyelu (2017)⟧adewumi2017survey Aderemi O Adewumi 和 Andronicus A Akinyelu。关于基于机器学习和自然启发的信用卡欺诈检测技术的调查。*国际系统保障工程与管理杂志*，8(2):937–953，2017 年。

+   [16] Litjens 等 (2017)Litjens, Kooi, Bejnordi, Setio, Ciompi, Ghafoorian, Van Der Laak, Van Ginneken 和 Sánchez⟧litjens2017survey Geert Litjens, Thijs Kooi, Babak Ehteshami Bejnordi, Arnaud Arindra Adiyoso Setio, Francesco Ciompi, Mohsen Ghafoorian, Jeroen Awm Van Der Laak, Bram Van Ginneken 和 Clara I Sánchez。医学图像分析中的深度学习综述。*医学图像分析*，42:60–88，2017 年。

+   [17] Erfani 等 (2016a)Erfani, Rajasegarar, Karunasekera 和 Leckie⟧erfani2016high Sarah M Erfani, Sutharshan Rajasegarar, Shanika Karunasekera 和 Christopher Leckie。使用深度学习的线性一类支持向量机进行高维和大规模异常检测。*模式识别*，58:121–134，2016 年。

+   [18] Chalapathy 等 (2018a)Chalapathy, Menon 和 Chawla⟧chalapathy2018anomaly Raghavendra Chalapathy, Aditya Krishna Menon 和 Sanjay Chawla。使用一类神经网络进行异常检测。*arXiv 预印本 arXiv:1802.06360*，2018 年。

+   [19] LeCun 等(2015)LeCun, Bengio, 和 Hinton⟧lecun2015deep Yann LeCun, Yoshua Bengio, 和 Geoffrey Hinton. 深度学习。*自然*, 521(7553):436, 2015.

+   [20] Ramotsoela 等(2018)Ramotsoela, Abu-Mahfouz, 和 Hancke⟧ramotsoela2018survey Daniel Ramotsoela, Adnan Abu-Mahfouz, 和 Gerhard Hancke. 工业无线传感器网络异常检测的综述，以关键水系统基础设施为案例研究。*传感器*, 18(8):2491, 2018.

+   [21] Chalapathy 等(2016a)Chalapathy, Borzeshi, 和 Piccardi⟧chalapathy2016investigation Raghavendra Chalapathy, Ehsan Zare Borzeshi, 和 Massimo Piccardi. 药物名称识别的递归神经网络结构研究。*arXiv 预印本 arXiv:1609.07585*, 2016a.

+   [22] Chalapathy 等(2016b)Chalapathy, Borzeshi, 和 Piccardi⟧chalapathy2016bidirectional Raghavendra Chalapathy, Ehsan Zare Borzeshi, 和 Massimo Piccardi. 双向 lstm-crf 临床概念提取。*arXiv 预印本 arXiv:1611.08373*, 2016b.

+   [23] Wulsin 等(2010)Wulsin, Blanco, Mani, 和 Litt⟧wulsin2010semi Drausin Wulsin, Justin Blanco, Ram Mani, 和 Brian Litt. 使用深度置信网络的 EEG 波形半监督异常检测。在 *机器学习与应用 (ICMLA), 2010 第九届国际会议*, 页码 436–441\. IEEE, 2010.

+   [24] Nadeem 等(2016)Nadeem, Marshall, Singh, Fang, 和 Yuan⟧nadeem2016semi Mutahir Nadeem, Ochaun Marshall, Sarbjit Singh, Xing Fang, 和 Xiaohong Yuan. 半监督深度神经网络用于网络入侵检测。2016.

+   [25] Song 等(2017)Song, Jiang, Men, 和 Yang⟧song2017hybrid Hongchao Song, Zhuqing Jiang, Aidong Men, 和 Bo Yang. 一种混合半监督异常检测模型用于高维数据。*计算智能与神经科学*, 2017, 2017.

+   [26] Patterson 和 Gibson(2017)⟧patterson2017deep Josh Patterson 和 Adam Gibson. *深度学习：实践者指南*。“ O’Reilly 媒体公司”, 2017.

+   [27] Tuor 等(2017)Tuor, Kaplan, Hutchinson, Nichols, 和 Robinson⟧tuor2017deep Aaron Tuor, Samuel Kaplan, Brian Hutchinson, Nicole Nichols, 和 Sean Robinson. 用于结构化网络安全数据流中无监督内部威胁检测的深度学习。*arXiv 预印本 arXiv:1710.00811*, 2017.

+   [28] Wold 等(1987)Wold, Esbensen, 和 Geladi⟧wold1987principal Svante Wold, Kim Esbensen, 和 Paul Geladi. 主成分分析。*化学计量学与智能实验室系统*, 2(1-3):37–52, 1987.

+   [29] Cortes 和 Vapnik(1995)⟧cortes1995support Corinna Cortes 和 Vladimir Vapnik. 支持向量网络。*机器学习*, 20(3):273–297, 1995.

+   [30] Liu 等(2008)Liu, Ting, 和 Zhou⟧liu2008isolation Fei Tony Liu, Kai Ming Ting, 和 Zhi-Hua Zhou. 隔离森林。发表于 *数据挖掘, 2008\. ICDM’08\. 第八届 IEEE 国际会议*, 页码 413–422\. IEEE, 2008.

+   [31] Sutskever 等人 (2009) Sutskever, Hinton, 和 Taylor⟧sutskever2009recurrent Ilya Sutskever, Geoffrey E Hinton, 和 Graham W Taylor. 循环时间限制玻尔兹曼机。见 *神经信息处理系统进展*，第 1601–1608 页，2009 年。

+   [32] Salakhutdinov 和 Larochelle (2010)⟧salakhutdinov2010efficient Ruslan Salakhutdinov 和 Hugo Larochelle. 深度玻尔兹曼机的高效学习。见 *第十三届人工智能与统计国际会议论文集*，第 693–700 页，2010 年。

+   [33] Vincent 等人 (2008) Vincent, Larochelle, Bengio, 和 Manzagol⟧vincent2008extracting Pascal Vincent, Hugo Larochelle, Yoshua Bengio, 和 Pierre-Antoine Manzagol. 使用去噪自编码器提取和组合鲁棒特征。见 *第 25 届国际机器学习大会论文集*，第 1096–1103 页。ACM，2008 年。

+   [34] Rodriguez 等人 (1999) Rodriguez, Wiles, 和 Elman⟧rodriguez1999recurrent Paul Rodriguez, Janet Wiles, 和 Jeffrey L Elman. 一个能学习计数的递归神经网络。*连接科学*，11(1):5–40，1999 年。

+   [35] Lample 等人 (2016) Lample, Ballesteros, Subramanian, Kawakami, 和 Dyer⟧lample2016neural Guillaume Lample, Miguel Ballesteros, Sandeep Subramanian, Kazuya Kawakami, 和 Chris Dyer. 用于命名实体识别的神经网络结构。*arXiv 预印本 arXiv:1603.01360*，2016 年。

+   [36] Andrews 等人 (2016a) Andrews, Morton, 和 Griffin⟧andrews2016detecting Jerone TA Andrews, Edward J Morton, 和 Lewis D Griffin. 使用自编码器检测异常数据。*国际机器学习与计算期刊*，6(1):21，2016 年。

+   [37] Pan 等人 (2010) Pan, Yang, 等⟧pan2010survey Sinno Jialin Pan, Qiang Yang, 等。迁移学习综述。*IEEE 知识与数据工程学报*，22(10):1345–1359，2010 年。

+   [38] Ergen 等人 (2017) Ergen, Mirza, 和 Kozat⟧ergen2017unsupervised Tolga Ergen, Ali Hassan Mirza, 和 Suleyman Serdar Kozat. 使用 LSTM 神经网络的无监督和半监督异常检测。*arXiv 预印本 arXiv:1710.09207*，2017 年。

+   [39] Ruff 等人 (2018a) Ruff, Görnitz, Deecke, Siddiqui, Vandermeulen, Binder, Müller, 和 Kloft⟧ruff2018deep Lukas Ruff, Nico Görnitz, Lucas Deecke, Shoaib Ahmed Siddiqui, Robert Vandermeulen, Alexander Binder, Emmanuel Müller, 和 Marius Kloft. 深度单类分类。见 *国际机器学习大会*，第 4390–4399 页，2018 年。

+   [40] LeCun 等人 (2010) LeCun, Cortes, 和 Burges⟧lecun2010mnist Yann LeCun, Corinna Cortes, 和 Christopher JC Burges. Mnist 手写数字数据库。*AT&T 实验室 ⟦在线⟧。可用链接: http://yann.lecun.com/exdb/mnist*，2，2010。

+   [41] Krizhevsky 和 Hinton (2009)⟧krizhevsky2009learning Alex Krizhevsky 和 Geoffrey Hinton. 从小图像中学习多个层次的特征。技术报告，2009 年。

+   [42] Song 等(2007)Song, Wu, Jermaine 和 Ranka⟧song2007conditional Xiuyao Song, Mingxi Wu, Christopher Jermaine 和 Sanjay Ranka. 条件异常检测. *IEEE 知识与数据工程学报*, 19(5):631–645, 2007。

+   [43] Hochreiter 和 Schmidhuber(1997)⟧hochreiter1997long Sepp Hochreiter 和 Jürgen Schmidhuber. 长短期记忆. *神经计算*, 9(8):1735–1780, 1997。

+   [44] Du 等(2017)Du, Li, Zheng 和 Srikumar⟧du2017deeplog Min Du, Feifei Li, Guineng Zheng 和 Vivek Srikumar. Deeplog: 通过深度学习从系统日志中检测和诊断异常. 在 *2017 年 ACM SIGSAC 计算机与通信安全会议论文集* 中, 页 1285–1298. ACM, 2017。

+   [45] Hayes 和 Capretz(2015)⟧hayes2015contextual Michael A Hayes 和 Miriam AM Capretz. 面向大规模传感器数据的上下文异常检测框架. *大数据杂志*, 2(1):2, 2015。

+   [46] Chalapathy 等(2018b)Chalapathy, Toth 和 Chawla⟧chalapathy2018group Raghavendra Chalapathy, Edward Toth 和 Sanjay Chawla. 使用深度生成模型进行群体异常检测. *arXiv 预印本 arXiv:1804.04876*, 2018b。

+   [47] Bontemps 等(2016)Bontemps, McDermott, Le-Khac 等⟧bontemps2016collective Loïc Bontemps, James McDermott, Nhien-An Le-Khac 等. 基于长短期记忆递归神经网络的集体异常检测. 在 *未来数据与安全工程国际会议* 中, 页 141–152. Springer, 2016。

+   [48] Araya 等(2016)Araya, Grolinger, ElYamany, Capretz 和 Bitsuamlak⟧araya2016collective Daniel B Araya, Katarina Grolinger, Hany F ElYamany, Miriam AM Capretz 和 G Bitsuamlak. 智能建筑的集体上下文异常检测框架. 在 *神经网络 (IJCNN), 2016 年国际联合会议* 中, 页 511–518. IEEE, 2016。

+   [49] Zhuang 等(2017)Zhuang, Yusufu, Ye 和 Hua⟧zhuang2017group Naifan Zhuang, Tuoerhongjiang Yusufu, Jun Ye 和 Kien A Hua. 使用差分递归卷积神经网络进行群体活动识别. 在 *自动面部与姿态识别 (FG 2017), 2017 年第十二届 IEEE 国际会议* 中, 页 526–531. IEEE, 2017。

+   [50] Ruff 等(2018b)Ruff, Vandermeulen, Goernitz, Deecke, Siddiqui, Binder, Müller 和 Kloft⟧pmlrv80ruff18a Lukas Ruff, Robert Vandermeulen, Nico Goernitz, Lucas Deecke, Shoaib Ahmed Siddiqui, Alexander Binder, Emmanuel Müller 和 Marius Kloft. 深度一类分类. 在 Jennifer Dy 和 Andreas Krause 编辑的 *第 35 届国际机器学习会议论文集* 中, *机器学习研究论文集* 第 80 卷, 页 4393–4402, 斯德哥尔摩斯美展览中心, 瑞典斯德哥尔摩, 2018 年 7 月 10–15 日。PMLR。网址 [`proceedings.mlr.press/v80/ruff18a.html`](http://proceedings.mlr.press/v80/ruff18a.html)。

+   [51] Phoha(2002)⟧phoha2002internet Vir V Phoha. *互联网安全词典*, 第 1 卷. Taylor & Francis, 2002。

+   [52] Vigna 和 Kruegel（2005）⟧vigna2005host Giovanna Vigna 和 Christopher Kruegel 共同编写。基于主机的入侵检测。2005。

+   [53] Kim 等（2016）⟧kim2016lstm Gyuwan Kim、Hayoon Yi、Jangho Lee、Yunheung Paek 和 Sungroh Yoon 共同编写。基于 LSTM 的系统调用语言建模和鲁棒集成方法，用于设计基于主机的入侵检测系统。*arXiv 预印本 arXiv:1611.01726*，2016。

+   [54] Chawla 等（2018）⟧chawla2018host Ashima Chawla、Brian Lee、Sheila Fallon 和 Paul Jacob 共同编写。基于主机的入侵检测系统，结合了 cnn/rnn 模型。见于 *第二届国际安全人工智能研讨会论文集*，2018。

+   [55] Chen 等（2018）⟧chen2018henet Li Chen、Salmin Sultana 和 Ravi Sahita 共同编写。Henet：一种基于英特尔®处理器跟踪的深度学习方法，用于有效的漏洞检测。见于 *2018 IEEE 安全与隐私研讨会 (SPW)*，第 109–115 页。IEEE，2018。

+   [56] Sohi 等（2018）⟧sohi2018recurrent Soroush M Sohi、Fatemeh Ganji 和 Jean-Pierre Seifert 共同编写。递归神经网络用于增强基于签名的网络入侵检测系统。*arXiv 预印本 arXiv:1807.03212*，2018。

+   [57] Vinayakumar 等（2017）⟧vinayakumar2017applying R Vinayakumar、KP Soman 和 Prabaharan Poornachandran 共同编写。应用卷积神经网络进行网络入侵检测。见于 *计算、通信与信息学进展 (ICACCI) 2017 国际会议*，第 1222–1228 页。IEEE，2017。

+   [58] Aghakhani 等（2018）⟧aghakhani2018detecting Hojjat Aghakhani、Aravind Machiry、Shirin Nilizadeh、Christopher Kruegel 和 Giovanni Vigna 共同编写。使用生成对抗网络检测虚假评论。*arXiv 预印本 arXiv:1805.10364*，2018。

+   [59] Li 等（2018）⟧li2018anomaly Dan Li、Dacheng Chen、Jonathan Goh 和 See-kiong Ng 共同编写。基于生成对抗网络的多变量时间序列异常检测。*arXiv 预印本 arXiv:1809.04758*，2018。

+   [60] Gao 等（2014）⟧gao2014intrusion 由 Ni Gao、Ling Gao、Quanli Gao 和 Hai Wang 共同编写。基于深度置信网络的入侵检测模型。见于 *2014 第二届国际云计算与大数据会议 (CBD)*，第 247–252 页。IEEE，2014。

+   [61] Peharz 等（2018）⟧peharz2018probabilistic Robert Peharz、Antonio Vergari、Karl Stelzner、Alejandro Molina、Martin Trapp、Kristian Kersting 和 Zoubin Ghahramani 共同编写。使用随机和积网络的概率深度学习。*arXiv 预印本 arXiv:1806.01910*，2018。

+   [62] Umer 等（2018）⟧umer2018two Muhammad Fahad Umer、Muhammad Sher 和 Yaxin Bi 共同编写。面向下一代网络的两阶段流量基础入侵检测模型。*PloS one*，13(1)：e0180945，2018。

+   [63] Yu 等（2017）Yang Yu, Jun Long 和 Zhiping Cai。通过堆叠扩张卷积自编码器进行网络入侵检测。*安全与通信网络*，2017 年。

+   [64] Thing（2017）Vrizlynn LL Thing。IEEE 802.11 网络异常检测与攻击分类：一种深度学习方法。见 *无线通信与网络会议（WCNC），2017 IEEE*，第 1–6 页。IEEE，2017 年。

+   [65] Zolotukhin 等（2016）Mikhail Zolotukhin, Timo Hämäläinen, Tero Kokkonen 和 Jarmo Siltanen。通过检测加密流量中的应用层 DDoS 攻击来提高 Web 服务的可用性。见 *电信（ICT），2016 年第 23 届国际会议*，第 1–6 页。IEEE，2016 年。

+   [66] Cordero 等（2016）Carlos García Cordero, Sascha Hauke, Max Mühlhäuser 和 Mathias Fischer。使用复制神经网络分析基于流的异常入侵检测。见 *隐私、安全与信任（PST），2016 年第 14 届年度会议*，第 317–324 页。IEEE，2016 年。

+   [67] Alrawashdeh 和 Purdy（2016）Khaled Alrawashdeh 和 Carla Purdy。基于深度学习的在线异常入侵检测系统。见 *机器学习与应用（ICMLA），2016 年第 15 届 IEEE 国际会议*，第 195–200 页。IEEE，2016 年。

+   [68] Tang 等（2016）Tuan A Tang, Lotfi Mhamdi, Des McLernon, Syed Ali Raza Zaidi 和 Mounir Ghogho。软件定义网络中的网络入侵检测深度学习方法。见 *无线网络与移动通信（WINCOM），2016 国际会议*，第 258–263 页。IEEE，2016 年。

+   [69] Lopez-Martin 等（2017）Manuel Lopez-Martin, Belen Carro, Antonio Sanchez-Esguevillas 和 Jaime Lloret。用于预测和特征恢复的条件变分自编码器应用于物联网中的入侵检测。*传感器*，17(9)：1967，2017 年。

+   [70] Al-Qatf 等（2018）Al-Qatf, Alhabib, Al-Sabahi 等。深度学习方法结合稀疏自编码器与支持向量机进行网络入侵检测。*IEEE Access*，2018 年。

+   [71] Mirsky 等（2018）Yisroel Mirsky, Tomer Doitshman, Yuval Elovici 和 Asaf Shabtai。Kitsune：用于在线网络入侵检测的自编码器集成。*arXiv 预印本 arXiv:1802.09089*，2018 年。

+   [72] Aygun 和 Yavuz（2017）R Can Aygun 和 A Gokhan Yavuz。通过随机改进的自编码器模型进行网络异常检测。见 *网络安全与云计算（CSCloud），2017 IEEE 第 4 届国际会议*，第 193–198 页。IEEE，2017 年。

+   [73] Lin 等（2018）Lin、Shi 和 Xue⟧lin2018idsgan Zilong Lin、Yong Shi 和 Zhi Xue。Idsgan：用于入侵检测的攻击生成对抗网络。*arXiv 预印本 arXiv:1809.02077*，2018。

+   [74] Yin 等（2018）Yin、Zhu、Liu、Fei 和 Zhang⟧yin2018enhancing Chuanlong Yin、Yuefei Zhu、Shengli Liu、Jinlong Fei 和 Hetong Zhang。使用生成对抗网络的机器人网络检测增强框架。发表于 *2018 国际人工智能与大数据会议（ICAIBD）*，第 228–234 页。IEEE，2018。

+   [75] Ring 等（2018）Ring、Schlör、Landes 和 Hotho⟧ring2018flow Markus Ring、Daniel Schlör、Dieter Landes 和 Andreas Hotho。基于流的网络流量生成使用生成对抗网络。*arXiv 预印本 arXiv:1810.07795*，2018。

+   [76] Latah（2018）⟧latah2018deep Majd Latah。深度学习遇上安全。*arXiv 预印本 arXiv:1807.04739*，2018。

+   [77] Intrator 等（2018）Intrator、Katz 和 Shabtai⟧intrator2018mdgan Yotam Intrator、Gilad Katz 和 Asaf Shabtai。Mdgan：使用多判别器生成对抗网络提升异常检测。*arXiv 预印本 arXiv:1810.05221*，2018。

+   [78] Matsubara 等（2018）Matsubara、Tachibana 和 Uehara⟧matsubara2018anomaly Takashi Matsubara、Ryosuke Tachibana 和 Kuniaki Uehara。通过未正则化评分的深度生成模型进行异常机器部件检测。发表于 *2018 国际神经网络联合会议（IJCNN）*，第 1–8 页。IEEE，2018。

+   [79] Nicolau 等（2016）Nicolau、McDermott 等⟧nicolau2016hybrid Miguel Nicolau、James McDermott 等。用于异常检测的混合自编码器和密度估计模型。发表于 *自然启发的并行问题解决国际会议*，第 717–726 页。Springer，2016。

+   [80] Rigaki（2017）⟧rigaki2017adversarial Maria Rigaki。对抗深度学习用于入侵检测分类器，2017。

+   [81] Malaiya 等（2018）Malaiya、Kwon、Kim、Suh、Kim 和 Kim⟧malaiya2018empirical Ritesh K Malaiya、Donghwoon Kwon、Jinoh Kim、Sang C Suh、Hyunjoo Kim 和 Ikkyun Kim。深度学习在网络异常检测中的经验评估。发表于 *2018 国际计算、网络和通信会议（ICNC）*，第 893–898 页。IEEE，2018。

+   [82] Kwon 等（2018）Kwon、Natarajan、Suh、Kim 和 Kim⟧kwon2018empirical Donghwoon Kwon、Kathiravan Natarajan、Sang C Suh、Hyunjoo Kim 和 Jinoh Kim。使用卷积神经网络进行网络异常检测的经验研究。发表于 *2018 IEEE 第 38 届国际分布式计算系统会议（ICDCS）*，第 1595–1598 页。IEEE，2018。

+   [83] Staudemeyer（2015）⟧staudemeyer2015applying Ralf C Staudemeyer。将长短期记忆递归神经网络应用于入侵检测。*南非计算机期刊*，56(1):136–154，2015。

+   [84] Naseer et al.(2018)Naseer, Saleem, Khalid, Bashir, Han, Iqbal, and Han⟧naseer2018enhanced Sheraz Naseer, Yasir Saleem, Shehzad Khalid, Muhammad Khawar Bashir, Jihun Han, Muhammad Munwar Iqbal, 和 Kijun Han。基于深度神经网络的增强网络异常检测。*IEEE Access*，6:48231–48246，2018 年。

+   [85] ucs(2017)⟧ucsdAnomalyDetect2017 UCSD 异常检测数据集。2017 年。

+   [86] Shiravi et al.(2012)Shiravi, Shiravi, Tavallaee, and Ghorbani⟧shiravi2012toward Ali Shiravi, Hadi Shiravi, Mahbod Tavallaee, 和 Ali A Ghorbani。朝着开发生成入侵检测基准数据集的系统方法迈进。*计算机与安全*，31(3):357–374，2012 年。

+   [87] Adam et al.(2008)Adam, Rivlin, Shimshoni, and Reinitz⟧adam2008robust Amit Adam, Ehud Rivlin, Ilan Shimshoni, 和 Daviv Reinitz。使用多个固定位置监视器进行鲁棒的实时异常事件检测。*IEEE 模式分析与机器智能汇刊*，30(3):555–560，2008 年。

+   [88] Yin et al.(2017)Yin, Zhu, Fei, and He⟧yin2017deep Chuanlong Yin, Yuefei Zhu, Jinlong Fei, 和 Xinzheng He。使用递归神经网络的深度学习入侵检测方法。*IEEE Access*，5:21954–21961，2017 年。

+   [89] Yousefi-Azar et al.(2017)Yousefi-Azar, Varadharajan, Hamey, and Tupakula⟧yousefi2017autoencoder Mahmood Yousefi-Azar, Vijay Varadharajan, Len Hamey, 和 Uday Tupakula。基于自编码器的网络安全应用特征学习。在*神经网络（IJCNN），2017 年国际联合会议*，第 3854–3861 页。IEEE，2017 年。

+   [90] Mohammadi and Namadchian(2017)⟧mohammadi2017new Shahriar Mohammadi 和 Amin Namadchian。一种基于记忆分类器的异常检测新深度学习方法。*国际计算机、通信与控制杂志*，12(5)，2017 年。

+   [91] Stolfo et al.(2000)Stolfo, Fan, Lee, Prodromidis, and Chan⟧stolfo2000cost J Stolfo, Wei Fan, Wenke Lee, Andreas Prodromidis, 和 Philip K Chan。基于成本的建模与评估在数据挖掘中的应用，尤其是在欺诈和入侵检测中。*Salvatore 的 JAM 项目结果*，第 1–15 页，2000 年。

+   [92] Van et al.(2017)Van, Thinh, and Sach⟧van2017anomaly Nguyen Thanh Van, Tran Ngoc Thinh, 和 Le Thanh Sach。基于异常的网络入侵检测系统使用深度学习。在*系统科学与工程（ICSSE），2017 年国际会议*，第 210–214 页。IEEE，2017 年。

+   [93] Fontugne et al.(2010)Fontugne, Borgnat, Abry, and Fukuda⟧fontugne2010mawilab Romain Fontugne, Pierre Borgnat, Patrice Abry, 和 Kensuke Fukuda。Mawilab：结合多种异常检测器进行自动异常标记和性能基准测试。在*第六届国际会议论文集*，第 8 页。ACM，2010 年。

+   [94] jam(2009)⟧jamkRGCE Jamk 应用科技大学，现实全球网络环境（RGCE）。2009 年。

+   [95] Creech and Hu(2014)⟧creech2014semantic Gideon Creech 和 Jiankun Hu. 使用连续和不连续系统调用模式的基于主机的入侵检测系统的语义方法。*IEEE 计算机学报*，63(4):807–819，2014 年。

+   [96] University(2012)⟧ImmuneDatasets 新墨西哥大学。计算机免疫系统数据集。2012 年。

+   [97] Abdallah et al.(2016)Abdallah, Maarof, and Zainal⟧abdallah2016fraud Aisha Abdallah, Mohd Aizaini Maarof, 和 Anazida Zainal. 欺诈检测系统：一项调查。*网络与计算机应用杂志*，68:90–113，2016 年。

+   [98] Lavion(2018)⟧Lavion2018 Didier; et al Lavion. PwC 全球经济犯罪与欺诈调查 2018。PwC.com，2018 年。网址 [`www.pwc.com/gx/en/forensics/global-economic-crime-and-fraud-survey-2018.pdf`](https://www.pwc.com/gx/en/forensics/global-economic-crime-and-fraud-survey-2018.pdf)。

+   [99] Zhao(2013)⟧zhao2013fraud Lucy Ma Zhao. 欺诈检测系统，2013 年 12 月 12 日。美国专利申请号 13/494,741。

+   [100] Sorournejad et al.(2016)Sorournejad, Zojaji, Atani, and Monadjemi⟧sorournejad2016survey Samaneh Sorournejad, Zahra Zojaji, Reza Ebrahimi Atani, 和 Amir Hassan Monadjemi. 信用卡欺诈检测技术的调查：数据和技术导向的视角。*CoRR abs/1611.06439*，2016 年。

+   [101] Zhou et al.(2018)Zhou, Cheng, Zhu, Guo, Zhou, Xu, Xue, and Zhang⟧zhou2018state Xun Zhou, Sicong Cheng, Meng Zhu, Chengkun Guo, Sida Zhou, Peng Xu, Zhenghua Xue, 和 Weishi Zhang. 基于数据挖掘的欺诈检测和信用评分的最先进调查。在 *MATEC Web of Conferences*，第 189 卷，第 03002 页。EDP Sciences，2018 年。

+   [102] Suganya and Kamalraj(2015)⟧suganya2015survey S Suganya 和 N Kamalraj. 信用卡欺诈检测的调查。*国际计算机科学与移动计算杂志*，4:241–244，2015 年。

+   [103] Schreyer et al.(2017)Schreyer, Sattarov, Borth, Dengel, and Reimer⟧schreyer2017detection Marco Schreyer, Timur Sattarov, Damian Borth, Andreas Dengel, 和 Bernd Reimer. 使用深度自编码网络检测大规模会计数据中的异常。*arXiv 预印本 arXiv:1709.05254*，2017 年。

+   [104] Wedge et al.(2017)Wedge, Kanter, Rubio, Perez, and Veeramachaneni⟧wedge2017solving Roy Wedge, James Max Kanter, Santiago Moral Rubio, Sergio Iglesias Perez, 和 Kalyan Veeramachaneni. 解决欺诈预测中的“假阳性”问题。*arXiv 预印本 arXiv:1710.07709*，2017 年。

+   [105] Paula et al.(2016)Paula, Ladeira, Carvalho, and Marzagão⟧paula2016deep Ebberth L Paula, Marcelo Ladeira, Rommel N Carvalho, 和 Thiago Marzagão. 深度学习异常检测作为支持巴西出口欺诈调查和反洗钱。在 *2016 年第 15 届 IEEE 国际会议：机器学习与应用（ICMLA）*，第 954–960 页。IEEE，2016 年。

+   [106] Renström and Holmsten(2018)⟧renstrom2018fraud Martin Renström 和 Timothy Holmsten. 使用无监督机器学习进行未标记数据的欺诈检测，2018 年。

+   [107] Kazemi 和 Zarrabi（2017）⟧kazemi2017using Zahra Kazemi 和 Houman Zarrabi. 使用深度网络进行信用卡交易中的欺诈检测。在*知识基础工程与创新（KBEI），2017 IEEE 第四届国际会议*，第 0630–0633 页。IEEE，2017。

+   [108] Zheng 等人（2018a）Zheng, Yuan, Wu, Li 和 Lu⟧zheng2018one Panpan Zheng, Shuhan Yuan, Xintao Wu, Jun Li 和 Aidong Lu. 一类对抗网络用于欺诈检测。*arXiv 预印本 arXiv:1803.01798*，2018a。

+   [109] Pumsirirat 和 Yan（2018）⟧pumsirirat2018credit Apapan Pumsirirat 和 Liu Yan. 基于自编码器和限制玻尔兹曼机的深度学习信用卡欺诈检测。*国际高级计算机科学与应用期刊*，9(1):18–25，2018。

+   [110] Seeja 和 Zareapoor（2014）⟧seeja2014fraudminer KR Seeja 和 Masoumeh Zareapoor. Fraudminer: 基于频繁项集挖掘的创新信用卡欺诈检测模型。*科学世界期刊*，2014，2014。

+   [111] Sweers 等人（2018）Sweers, Heskes 和 Krijthe⟧sweers2018autoencoding Tom Sweers, Tom Heskes 和 Jesse Krijthe. 自动编码信用卡欺诈。2018。

+   [112] Fiore 等人（2017）Fiore, De Santis, Perla, Zanetti 和 Palmieri⟧fiore2017using Ugo Fiore, Alfredo De Santis, Francesca Perla, Paolo Zanetti 和 Francesco Palmieri. 使用生成对抗网络提高信用卡欺诈检测中的分类效果。*信息科学*，2017。

+   [113] Choi 和 Jang（2018）⟧choi2018generative Hyunsun Choi 和 Eric Jang. 生成对抗集成用于鲁棒异常检测。*arXiv 预印本 arXiv:1810.01392*，2018。

+   [114] Dorronsoro 等人（1997）Dorronsoro, Ginel, Sánchez 和 Santa Cruz⟧dorronsoro1997neural Jose R Dorronsoro, Francisco Ginel, Carmen R Sánchez 和 Carlos Santa Cruz. 神经网络欺诈检测在信用卡操作中的应用。*IEEE 神经网络交易*，1997。

+   [115] Gómez 等人（2018）Gómez, Arévalo, Paredes 和 Nin⟧gomez2018end Jon Ander Gómez, Juan Arévalo, Roberto Paredes 和 Jordi Nin. 面向信用卡支付欺诈评分的端到端神经网络架构。*模式识别通讯*，105:175–181，2018。

+   [116] Wiese 和 Omlin（2009）⟧wiese2009credit Bénard Wiese 和 Christian Omlin. 信用卡交易、欺诈检测和机器学习：用 LSTM 循环神经网络建模时间。在*神经信息范式与应用的创新*，第 231–268 页。Springer，2009。

+   [117] Jurgovsky 等人（2018）Jurgovsky, Granitzer, Ziegler, Calabretto, Portier, He-Guelton 和 Caelen⟧jurgovsky2018sequence Johannes Jurgovsky, Michael Granitzer, Konstantin Ziegler, Sylvie Calabretto, Pierre-Edouard Portier, Liyun He-Guelton 和 Olivier Caelen. 信用卡欺诈检测的序列分类。*专家系统与应用*，100:234–245，2018。

+   [118] Heryadi and Warnars(2017)⟧heryadi2017learning Yaya Heryadi 和 Harco Leslie Hendric Spits Warnars. 使用 CNN、堆叠 LSTM 和 CNN-LSTM 学习交易金额的时间表示以识别欺诈交易。在*控制论与计算智能（CyberneticsCom），2017 年 IEEE 国际会议*，第 84–89 页。IEEE，2017。

+   [119] Ando et al.(2016)Ando, Gomi, and Tanaka⟧ando2016detecting Yoshihiro Ando, Hidehito Gomi, and Hidehiko Tanaka. 使用递归神经网络检测欺诈行为。2016。

+   [120] Wang et al.(2017a)Wang, Liu, Gao, Qu, and Xu⟧wang2017session Shuhao Wang, Cancheng Liu, Xiang Gao, Hongtao Qu, and Wei Xu. 基于会话的在线电子商务交易欺诈检测，使用递归神经网络。在*欧洲联合会议：机器学习与数据库中的知识发现*，第 241–252 页。Springer，2017a。

+   [121] Alowais and Soon(2012)⟧alowais2012credit Mohammed Ibrahim Alowais 和 Lay-Ki Soon. 信用卡欺诈检测：个性化还是聚合模型。在*移动、普适与智能计算（MUSIC），2012 年第三届 FTRA 国际会议*，第 114–119 页。IEEE，2012。

+   [122] Amarasinghe et al.(2018a)Amarasinghe, Aponso, and Krishnarajah⟧amarasinghe2018critical Thushara Amarasinghe, Achala Aponso 和 Naomi Krishnarajah. 对基于机器学习的金融交易欺诈检测方法的批判性分析。在*2018 国际会议上机器学习技术的论文集*，第 12–17 页。ACM，2018a。

+   [123] Abroyan(2017a)⟧abroyan2017neural Narek Abroyan. 金融市场风险分类的神经网络。2017a。

+   [124] Lp et al.(2018)Lp, Yu, Luwang, Zheng, Qiu, Zhao, Xia, and Li⟧lp2018transaction Xurui Lp, Wei Yu, Tianyu Luwang, Jianbin Zheng, Xuetao Qiu, Jintao Zhao, Lei Xia, and Yujiao Li. 使用基于 GRU 的三明治结构模型进行交易欺诈检测。在*2018 IEEE 第 22 届计算机支持协同设计国际会议（CSCWD）*，第 467–472 页。IEEE，2018。

+   [125] Shen et al.(2007)Shen, Tong, and Deng⟧shen2007application Aihua Shen, Rencheng Tong 和 Yaochen Deng. 分类模型在信用卡欺诈检测中的应用。在*服务系统与服务管理，2007 国际会议*，第 1–4 页。IEEE，2007。

+   [126] Chouiekh and Haj(2018)⟧chouiekh2018convnets Alae Chouiekh 和 EL Hassane Ibn EL Haj. 用于欺诈检测分析的卷积网络。*Procedia 计算机科学*，127：133–138，2018。

+   [127] Abroyan(2017b)⟧abroyan2017convolutional Narek Abroyan. 实时数据分类的卷积和递归神经网络。在*创新计算技术（INTECH），2017 年第七届国际会议*，第 42–45 页。IEEE，2017b。

+   [128] Fu 等人（2016）Fu, Cheng, Tu, 和 Zhang⟧fu2016credit Kang Fu, Dawei Cheng, Yi Tu, 和 Liqing Zhang。使用卷积神经网络进行信用卡欺诈检测。在 *国际神经信息处理会议*，第 483–490 页。Springer，2016 年。

+   [129] Lu（2017）⟧lu2017deep Yifei Lu。深度神经网络与欺诈检测，2017 年。

+   [130] Wang 等人（2018a）Wang, Wang, Ye, Yan, Cai, 和 Pan⟧wang2018credit Chunzhi Wang, Yichao Wang, Zhiwei Ye, Lingyu Yan, Wencheng Cai, 和 Shang Pan。基于鲸鱼算法优化的 BP 神经网络的信用卡欺诈检测。在 *2018 年第 13 届计算机科学与教育国际会议（ICCSE）*，第 1–4 页。IEEE，2018a。

+   [131] Zhang 等人（2018a）Zhang, Zhou, Zhang, Wang, 和 Wang⟧zhang2018model Zhaohui Zhang, Xinxin Zhou, Xiaobo Zhang, Lizhi Wang, 和 Pengwei Wang。基于卷积神经网络的在线交易欺诈检测模型。*安全与通信网络*，2018 年，2018a。

+   [132] Alsheikh 等人（2016）Alsheikh, Niyato, Lin, Tan, 和 Han⟧alsheikh2016mobile Mohammad Abu Alsheikh, Dusit Niyato, Shaowei Lin, Hwee-Pink Tan, 和 Zhu Han。利用深度学习和 Apache Spark 进行移动大数据分析。*IEEE 网络*，30(3)：22–29，2016 年。

+   [133] Badhe（2017）⟧badhe2017click Anup Badhe。在程序化库存中提供的移动广告的点击欺诈检测。*神经网络与机器学习*，1(1)：1–1，2017 年。

+   [134] Akhter 和 Ahamad（2012）⟧akhter2012detecting Mohammad Iquebal Akhter 和 Mohammad Gulam Ahamad。通过数据挖掘使用神经网络检测电信欺诈。*国际科学与工程研究期刊*，3(3)：601–606，2012 年。

+   [135] Jain（2017）⟧jain2017perspective Vanita Jain。利用数据流分析和基于神经网络分类的数据挖掘进行电信欺诈检测的视角分析。*国际信息技术期刊*，9(3)：303–310，2017 年。

+   [136] Zheng 等人（2018b）Zheng, Zhou, Sheng, Xue, 和 Chen⟧zheng2018generative Yu-Jun Zheng, Xiao-Han Zhou, Wei-Guo Sheng, Yu Xue, 和 Sheng-Yong Chen。基于生成对抗网络的电信欺诈检测，在接收银行。*神经网络*，102：78–86，2018b。

+   [137] Joudaki 等人（2015）Joudaki, Rashidian, Minaei-Bidgoli, Mahmoodi, Geraili, Nasiri, 和 Arab⟧joudaki2015using Hossein Joudaki, Arash Rashidian, Behrouz Minaei-Bidgoli, Mahmood Mahmoodi, Bijan Geraili, Mahdi Nasiri, 和 Mohammad Arab。使用数据挖掘来检测医疗保健欺诈和滥用：文献综述。*全球健康科学杂志*，7(1)：194，2015 年。

+   [138] Roy 和 George（2017）⟧roy2017detecting Riya Roy 和 K Thomas George。使用机器学习技术检测保险索赔欺诈。在 *电路、电源和计算技术（ICCPCT），2017 年国际会议*，第 1–6 页。IEEE，2017 年。

+   [139] Viaene 等人（2005）Viaene、Dedene 和 Derrig⟧viaene2005auto Stijn Viaene、Guido Dedene 和 Richard A Derrig。使用贝叶斯学习神经网络进行汽车索赔欺诈检测。*专家系统与应用*，29（3）：653–666，2005。

+   [140] Fajardo 等人（2018）Fajardo、Findlay、Houmanfar、Jaiswal、Liang 和 Xie⟧fajardo2018vos Val Andrei Fajardo、David Findlay、Roshanak Houmanfar、Charu Jaiswal、Jiaxi Liang 和 Honglei Xie。Vos：一种变分过采样不平衡数据的方法。*arXiv 预印本 arXiv:1809.02596*，2018。

+   [141] Keung 等人（2009）Keung、Karel 和 Bright⟧keung2009neural Phillip Keung、Joycelin Karel 和 Curtis Bright。用于保险欺诈检测的神经网络，2009。

+   [142] Bauder 和 Khoshgoftaar（2017）⟧bauder2017medicare Richard A Bauder 和 Taghi M Khoshgoftaar。利用机器学习方法进行医疗保险欺诈检测。在 *2017 年第 16 届 IEEE 国际机器学习与应用会议（ICMLA）* 上，页码 858–865。IEEE，2017。

+   [143] Lasaga 和 Santhana（2018）⟧lasaga2018deep Daniel Lasaga 和 Prakash Santhana。利用深度学习检测医疗治疗欺诈。在 *KDD 2017 财务异常检测研讨会* 上，页码 114–120，2018。

+   [144] Ghasedi Dizaji 等人（2018）Ghasedi Dizaji、Wang 和 Huang⟧ghasedi2018semi Kamran Ghasedi Dizaji、Xiaoqian Wang 和 Heng Huang。用于基因表达推断的半监督生成对抗网络。在 *第 24 届 ACM SIGKDD 国际知识发现与数据挖掘大会论文集* 上，页码 1435–1444。ACM，2018。

+   [145] Finlayson 等人（2018）Finlayson、Kohane 和 Beam⟧finlayson2018adversarial Samuel G Finlayson、Isaac S Kohane 和 Andrew L Beam。针对医疗深度学习系统的对抗攻击。*arXiv 预印本 arXiv:1804.05296*，2018。

+   [146] Esteva 等人（2017）Esteva、Kuprel、Novoa、Ko、Swetter、Blau 和 Thrun⟧esteva2017dermatologist Andre Esteva、Brett Kuprel、Roberto A Novoa、Justin Ko、Susan M Swetter、Helen M Blau 和 Sebastian Thrun。利用深度神经网络进行皮肤癌的皮肤科医生级分类。*Nature*，542（7639）：115，2017。

+   [147] Ye 等人（2017）Ye、Li、Adjeroh 和 Iyengar⟧ye2017survey Yanfang Ye、Tao Li、Donald Adjeroh 和 S Sitharama Iyengar。利用数据挖掘技术进行恶意软件检测的综述。*ACM 计算机调查（CSUR）*，50（3）：41，2017。

+   [148] Hardy 等人（2016）Hardy、Chen、Hou、Ye 和 Li⟧hardy2016dl4md William Hardy、Lingwei Chen、Shifu Hou、Yanfang Ye 和 Xin Li。Dl4md：一个用于智能恶意软件检测的深度学习框架。在 *国际数据挖掘会议（DMIN）* 上，页码 61。世界计算机科学、计算机工程和应用计算大会（WorldComp）指导委员会，2016。

+   [149] De Paola 等（2018）De Paola, Favaloro, Gaglio, Lo Re, 和 Morana⟧de2018malware Alessandra De Paola, Salvatore Favaloro, Salvatore Gaglio, G Lo Re, 和 Marco Morana。通过低级特征和堆叠去噪自编码器进行恶意软件检测。见于*第二届意大利网络安全会议，ITASEC 2018*，第 2058 卷。CEUR-WS，2018 年。

+   [150] Sewak 等（2018）Sewak, Sahay, 和 Rathore⟧sewak2018investigation Mohit Sewak, Sanjay K Sahay, 和 Hemant Rathore。基于深度学习的恶意软件检测系统调查。见于*第 13 届国际可用性、可靠性与安全性会议*，第 26 页。ACM，2018 年。

+   [151] Kebede 等（2017）Kebede, Djaneye-Boundjou, Narayanan, Ralescu, 和 Kapp⟧kebede2017classification Temesguen Messay Kebede, Ouboti Djaneye-Boundjou, Barath Narayanan Narayanan, Anca Ralescu, 和 David Kapp。使用基于自编码器的深度学习架构对恶意软件程序进行分类，并应用于微软恶意软件分类挑战（big 2015）数据集。见于*2017 年 IEEE 国家航空航天与电子会议（NAECON）*，第 70–75 页。IEEE，2017 年。

+   [152] David 和 Netanyahu（2015）⟧david2015deepsign Omid E David 和 Nathan S Netanyahu。Deepsign：用于自动恶意软件签名生成和分类的深度学习。见于*神经网络（IJCNN），2015 年国际联合会议*，第 1–8 页。IEEE，2015 年。

+   [153] Cakir 和 Dogdu（2018）⟧cakir2018malware Bugra Cakir 和 Erdogan Dogdu。使用深度学习方法进行恶意软件分类。见于*ACMSE 2018 会议论文集*，第 10 页。ACM，2018 年。

+   [154] Silva 等（2018）Silva, Akhavan-Masouleh, 和 Li⟧silva2018improving Pedro Silva, Sepehr Akhavan-Masouleh, 和 Li Li。通过提取图标信息提高恶意软件检测准确性。见于*2018 IEEE 多媒体信息处理与检索会议（MIPR）*，第 408–411 页。IEEE，2018 年。

+   [155] Kolosnjaji 等（2018）Kolosnjaji, Demontis, Biggio, Maiorca, Giacinto, Eckert, 和 Roli⟧kolosnjaji2018adversarial Bojan Kolosnjaji, Ambra Demontis, Battista Biggio, Davide Maiorca, Giorgio Giacinto, Claudia Eckert, 和 Fabio Roli。对抗性恶意软件二进制文件：规避用于恶意软件检测的深度学习。*arXiv 预印本 arXiv:1803.04173*，2018 年。

+   [156] Suciu 等（2018）Suciu, Coull 和 Johns⟧suciu2018exploring Octavian Suciu, Scott E Coull, 和 Jeffrey Johns。探讨恶意软件检测中的对抗性样本。*arXiv 预印本 arXiv:1810.08280*，2018 年。

+   [157] Srisakaokul 等（2018）Srisakaokul, Zhong, Zhang, Yang, 和 Xie⟧srisakaokul2018muldef Siwakorn Srisakaokul, Zexuan Zhong, Yuhao Zhang, Wei Yang, 和 Tao Xie。Muldef：基于多模型的神经网络对抗样本防御。*arXiv 预印本 arXiv:1809.00065*，2018 年。

+   [158] King 等（2018）⟧king2018artificial Thomas King, Nikita Aggarwal, Mariarosaria Taddeo 和 Luciano Floridi。人工智能犯罪：对可预见威胁和解决方案的跨学科分析。2018 年。

+   [159] Huang 和 Kao（2017）⟧huang2017r2 TonTon Hsien-De Huang 和 Hung-Yu Kao。R2-d2: 基于颜色启发的卷积神经网络（CNN）安卓恶意软件检测。*arXiv 预印本 arXiv:1705.04448*，2017 年。

+   [160] Guo 等（2017）⟧guo2017malware Wei Guo, Tenghai Wang 和 Jizeng Wei。使用硬件事件的卷积神经网络恶意软件检测。见于 *CCF 全国计算机工程与技术大会*，第 104–115 页。Springer，2017 年。

+   [161] Abdelsalam 等（2018）⟧abdelsalam2018malware Mahmoud Abdelsalam, Ram Krishnan, Yufei Huang 和 Ravi Sandhu。使用卷积神经网络进行云基础设施中的恶意软件检测。见于 *2018 IEEE 第十一届国际云计算会议（CLOUD）*，第 162–169 页。IEEE，2018 年。

+   [162] Raff 等（2017）⟧raff2017malware Edward Raff, Jon Barker, Jared Sylvester, Robert Brandon, Bryan Catanzaro 和 Charles Nicholas。通过处理整个 exe 文件进行恶意软件检测。*arXiv 预印本 arXiv:1710.09435*，2017 年。

+   [163] Karbab 等（2018）⟧karbab2018maldozer ElMouatez Billah Karbab, Mourad Debbabi, Abdelouahid Derhab 和 Djedjiga Mouheb。Maldozer：基于深度学习的安卓恶意软件自动检测框架。*数字调查*，24:S48–S59，2018 年。

+   [164] Martinelli 等（2017）⟧martinelli2017evaluating Fabio Martinelli, Fiammetta Marulli 和 Francesco Mercaldo。评估卷积神经网络在移动恶意软件检测中的有效性。*计算机科学程序*，112:2372–2381，2017 年。

+   [165] McLaughlin 等（2017）⟧mclaughlin2017deep Niall McLaughlin, Jesus Martinez del Rincon, BooJoong Kang, Suleiman Yerima, Paul Miller, Sakir Sezer, Yeganeh Safaei, Erik Trickel, Ziming Zhao, Adam Doupe 等。深度安卓恶意软件检测。见于 *第七届 ACM 数据与应用安全与隐私会议论文集*，第 301–308 页。ACM，2017 年。

+   [166] Gibert 等（2018）⟧gibert2018using Daniel Gibert, Carles Mateu, Jordi Planes 和 Ramon Vicens。利用卷积神经网络对图像表示的恶意软件进行分类。*计算机病毒与黑客技术杂志*，第 1–14 页，2018 年。

+   [167] Kolosnjaji 等 (2017)Kolosnjaji, Eraisha, Webster, Zarras, 和 Eckert⟧kolosnjaji2017empowering Bojan Kolosnjaji, Ghadir Eraisha, George Webster, Apostolis Zarras, 和 Claudia Eckert. 为恶意软件分类和分析赋能卷积网络。在 *2017 国际联合神经网络会议 (IJCNN)*，第 3838–3845 页。IEEE，2017 年。

+   [168] Rosenberg 等 (2018)Rosenberg, Sicard, 和 David⟧rosenberg2018end Ishai Rosenberg, Guillaume Sicard, 和 Eli Omid David. 用于国家级恶意软件自动分析的端到端深度神经网络和迁移学习。*熵*，20(5):390，2018 年。

+   [169] Wang 等 (2017b)Wang, Guo, Zhang, Ororbia II, Xing, Liu, 和 Giles⟧wang2017adversary Qinglong Wang, Wenbo Guo, Kaixuan Zhang, Alexander G Ororbia II, Xinyu Xing, Xue Liu, 和 C Lee Giles. 具有应用于恶意软件检测的对抗性深度神经网络。在 *第 23 届 ACM SIGKDD 国际知识发现与数据挖掘会议论文集*，第 1145–1153 页。ACM，2017b 年。

+   [170] YANG 等 (2016)YANG, ZHANG, MAO, 和 CHEN⟧yang2016application JIA YANG, HUIXIANG ZHANG, BAOLEI MAO, 和 CHUNLEI CHEN. 深度置信网络在安卓恶意软件检测中的应用。*ICIC 快报。B 部分，应用：国际研究与调查期刊*，7(7):1505–1510，2016 年。

+   [171] Ding 等 (2016)Ding, Chen, 和 Xu⟧ding2016application Yuxin Ding, Sheng Chen, 和 Jun Xu. 基于操作码的恶意软件检测的深度置信网络应用。在 *2016 国际联合神经网络会议 (IJCNN)*，第 3901–3908 页。IEEE，2016 年。

+   [172] Yuxin 和 Siyi (2017)⟧yuxin2017malware Ding Yuxin 和 Zhu Siyi. 基于深度学习算法的恶意软件检测。*神经计算与应用*，第 1–12 页，2017 年。

+   [173] Selvaganapathy 等 (2018)Selvaganapathy, Nivaashini, 和 Natarajan⟧selvaganapathy2018deep ShymalaGowri Selvaganapathy, Mathappan Nivaashini, 和 HemaPriya Natarajan. 基于深度置信网络的恶意网址检测与分类。*信息安全期刊：全球视角*，27(3):145–161，2018 年。

+   [174] Hou 等 (2017)Hou, Saas, Chen, Ye, 和 Bourlai⟧hou2017deep Shifu Hou, Aaron Saas, Lingwei Chen, Yanfang Ye, 和 Thirimachos Bourlai. 用于自动安卓恶意软件检测的深度神经网络。在 *2017 IEEE/ACM 国际社会网络分析与挖掘会议论文集*，第 803–810 页。ACM，2017 年。

+   [175] Tobiyama 等 (2016)Tobiyama, Yamaguchi, Shimada, Ikuse, 和 Yagi⟧tobiyama2016malware Shun Tobiyama, Yukiko Yamaguchi, Hajime Shimada, Tomonori Ikuse, 和 Takeshi Yagi. 使用进程行为的深度神经网络恶意软件检测。在 *计算机软件与应用大会 (COMPSAC)，2016 IEEE 第 40 届年会*，第 2 卷，第 577–582 页。IEEE，2016 年。

+   [176] Hu 和 Tan (2017)⟧hu2017black Weiwei Hu 和 Ying Tan. 针对基于 RNN 的恶意软件检测算法的黑箱攻击。*arXiv 预印本 arXiv:1705.08131*，2017 年。

+   [177] 托比亚马等人（2018）托比亚马、山口、长谷川、岛田、秋山和矢木⟧tobiyama2018method Shun Tobiyama、Yukiko Yamaguchi、Hirokazu Hasegawa、Hajime Shimada、Mitsuaki Akiyama 和 Takeshi Yagi。基于 seq2seq 模型的进程恶意性估计方法。发表于 *2018 年国际信息网络会议（ICOIN）*，第 255–260 页。IEEE，2018 年。

+   [178] Passalis 和 Tefas()⟧passalislong Nikolaos Passalis 和 Anastasios Tefas。用于深度神经网络随机优化的长期时间平均。*神经计算与应用*，第 1–13 页。

+   [179] 乐等人（2018）乐、博伊德尔、麦克内米和斯坎隆⟧le2018deep Quan Le、Oisín Boydell、Brian Mac Namee 和 Mark Scanlon。浅层深度学习：面向非领域专家的恶意软件分类。*数字调查*，26:S118–S126，2018 年。

+   [180] 金等人（2018）金、朴和赵⟧kim2018zero Jin-Young Kim、Seok-Jun Bu 和 Sung-Bae Cho。基于深度自编码器的迁移生成对抗网络的零日恶意软件检测。*信息科学*，460:83–102，2018 年。

+   [181] 王等人（2018b）王、赵和王⟧wang2018effective Wei Wang、Mengxue Zhao 和 Jigang Wang。基于深度自编码器和卷积神经网络的混合模型在安卓恶意软件检测中的有效性。*环境智能与人性化计算杂志*，第 1–9 页，2018b 年。

+   [182] 李等人（2015）李、马和焦⟧li2015hybrid Yuancheng Li、Rong Ma 和 Runhai Jiao。基于深度学习的混合恶意代码检测方法。*methods*，9(5)，2015 年。

+   [183] HaddadPajouh 等人（2018）HaddadPajouh、Dehghantanha、Khayami 和 Choo⟧haddadpajouh2018deep Hamed HaddadPajouh、Ali Dehghantanha、Raouf Khayami 和 Kim-Kwang Raymond Choo。基于深度递归神经网络的物联网恶意软件威胁猎捕方法。*未来一代计算机系统*，85:88–96，2018 年。

+   [184] 闵等人（2017）闵、李和尹⟧min2017deep Seonwoo Min、Byunghan Lee 和 Sungroh Yoon。生物信息学中的深度学习。*生物信息学简报*，18(5):851–869，2017 年。

+   [185] 曹等人（2018a）曹、刘、谭、宋、舒、李、周、博和谢⟧cao2018deep Chensi Cao、Feng Liu、Hai Tan、Deshou Song、Wenjie Shu、Weizhong Li、Yiming Zhou、Xiaochen Bo 和 Zhi Xie。深度学习及其在生物医学中的应用。*基因组学、蛋白质组学与生物信息学*，2018a 年。

+   [186] 赵等人（2016）赵、严、陈、毛、王和高⟧zhao2016deep Rui Zhao、Ruqiang Yan、Zhenghua Chen、Kezhi Mao、Peng Wang 和 Robert X Gao。深度学习及其在机器健康监测中的应用：综述。*arXiv 预印本 arXiv:1612.07640*，2016 年。

+   [187] Khan 和 Yairi（2018）⟧khan2018review Samir Khan 和 Takehisa Yairi。关于深度学习在系统健康管理中应用的综述。*机械系统与信号处理*，107:241–265，2018 年。

+   [188] Gugulothu 等人（Gugulothu, Malhotra, Vig, 和 Shroff）⟧gugulothusparse Narendhar Gugulothu, Pankaj Malhotra, Lovekesh Vig, 和 Gautam Shroff。用于高维时间序列异常检测的稀疏神经网络。

+   [189] Amarasinghe 等人（2018b）（Amarasinghe, Kenney, 和 Manic）⟧amarasinghe2018toward Kasun Amarasinghe, Kevin Kenney, 和 Milos Manic。迈向可解释的深度神经网络基于异常检测。见于 *2018 年第 11 届人机交互国际会议（HSI）*，第 311–317 页。IEEE, 2018b。

+   [190] Choi（2018）⟧choi2018doctor Edward Choi。*Doctor AI: 可解释的深度学习用于建模电子健康记录*。博士论文，乔治亚理工学院，2018。

+   [191] Wang 等人（2016）（Wang, Zhao, Xiong, Fan, Sun, Ma, 和 Liu）⟧wang2016research Kai Wang, Youjin Zhao, Qingyu Xiong, Min Fan, Guotan Sun, Longkun Ma, 和 Tong Liu。基于深度学习的健康异常检测模型研究，来自多个时间序列生理信号。 *科学编程*，2016，2016。

+   [192] Cowton 等人（2018）（Cowton, Kyriazakis, Plötz, 和 Bacardit）⟧cowton2018combined Jake Cowton, Ilias Kyriazakis, Thomas Plötz, 和 Jaume Bacardit。用于早期检测猪呼吸疾病的结合深度学习 GRU-自动编码器，利用多个环境传感器。 *传感器*，18(8):2521, 2018。

+   [193] Sato 等人（2018）（Sato, Hanaoka, Nomura, Takenaga, Miki, Yoshikawa, Hayashi, 和 Abe）⟧sato2018primitive Daisuke Sato, Shouhei Hanaoka, Yukihiro Nomura, Tomomi Takenaga, Soichiro Miki, Takeharu Yoshikawa, Naoto Hayashi, 和 Osamu Abe。基于自动编码器的无监督异常检测在急诊头部 CT 图像中的初步研究。见于 *2018 年医学成像：计算机辅助诊断*，第 10575 卷，第 105751P 页。国际光学与光子学学会，2018。

+   [194] Turner 等人（2014）（Turner, Page, Mohsenin, 和 Oates）⟧turner2014deep JT Turner, Adam Page, Tinoosh Mohsenin, 和 Tim Oates。在高分辨率多通道脑电图数据上使用深度信念网络进行癫痫检测。见于 *2014 AAAI 春季研讨会系列*，2014。

+   [195] Sharma 等人（2016）（Sharma, Sheet, 和 Biswas）⟧sharma2016abnormality Manoj Kumar Sharma, Debdoot Sheet, 和 Prabir Kumar Biswas。异常检测深度信念网络。见于 *国际信息通信技术与计算进展会议论文集*，第 11 页。ACM, 2016。

+   [196] Ma 等人（2018）（Ma, Peng, Wang, 和 Leong）⟧ma2018unsupervised Ning Ma, Yu Peng, Shaojun Wang, 和 Philip HW Leong。无监督深度高光谱异常检测器。 *传感器*，18(3):693, 2018。

+   [197] Zhang 等人（2016）（Zhang, Wu, Bai, 和 Chen）⟧zhang2016automatic Junming Zhang, Yan Wu, Jing Bai, 和 Fuqiang Chen。基于稀疏深度信念网络和多分类器组合的自动睡眠阶段分类。 *测量与控制学报*，38(4):435–451, 2016。

+   [198] Wulsin 等（2011）Wulsin、Gupta、Mani、Blanco 和 Litt⟧wulsin2011modeling DF Wulsin、JR Gupta、R Mani、JA Blanco 和 B Litt。使用半监督深度置信网络对脑电图波形进行建模：快速分类和异常测量。*神经工程期刊*，8(3)：036015，2011 年。

+   [199] Wu 等（2015a）Wu、Guo 和 Ma⟧wu2015adaptive C Wu、Y Guo 和 Y Ma。使用深度网络的自适应异常检测。在*第七届自适应与自我适应系统与应用国际会议论文集*，2015 年。

+   [200] Liao 等（2016）Liao、Jin 和 Pavel⟧liao2016enhanced Linxia Liao、Wenjing Jin 和 Radu Pavel。增强的限制玻尔兹曼机与预后正则化，用于预后和健康评估。*IEEE 工业电子学报*，63(11)：7076–7083，2016 年。

+   [201] Xu 等（2018）Xu、Chen、Zhao、Li、Bu、Li、Liu、Zhao、Pei、Feng 等⟧xu2018unsupervised Haowen Xu、Wenxiao Chen、Nengwen Zhao、Zeyan Li、Jiahao Bu、Zhihan Li、Ying Liu、Youjian Zhao、Dan Pei、Yang Feng 等。通过变分自编码器进行季节性 KPI 的无监督异常检测。 在*2018 年全球信息网会议论文集*，页 187–196。国际全球信息网会议指导委员会，2018 年。

+   [202] Lu 和 Xu（2018）⟧lu2018anomaly Yuchen Lu 和 Peng Xu。使用变分自编码器进行皮肤病图像的异常检测。*arXiv 预印本 arXiv:1807.01349*，2018 年。

+   [203] Chen 和 Konukoglu（2018）⟧chen2018unsupervised Xiaoran Chen 和 Ender Konukoglu。使用约束对抗自编码器对脑 MRI 中的病变进行无监督检测。*arXiv 预印本 arXiv:1806.04972*，2018 年。

+   [204] Yang 和 Gao（2018）⟧yang2018toward Hangzhou Yang 和 Huiying Gao。朝向可持续虚拟化医疗：使用深度神经网络从中文在线健康咨询中提取医学实体。*可持续性*，10(9)：3292，2018 年。

+   [205] Jagannatha 和 Yu（2016）⟧jagannatha2016bidirectional Abhyuday N Jagannatha 和 Hong Yu。用于电子健康记录中医学事件检测的双向 RNN。在*会议论文集。计算语言学协会。北美章节。会议*，卷 2016，第 473 页。NIH 公共访问，2016 年。

+   [206] O’Shea 等（2016）O’Shea、Clancy 和 McGwier⟧o2016recurrent Timothy J O’Shea、T Charles Clancy 和 Robert W McGwier。递归神经网络无线电异常检测。*arXiv 预印本 arXiv:1611.00301*，2016 年。

+   [207] Latif 等（2018）Latif、Usman、Rana 和 Qadir⟧latif2018phonocardiographic Siddique Latif、Muhammad Usman、Rajib Rana 和 Junaid Qadir。使用深度学习进行异常心跳检测的心音图传感。*IEEE 传感器期刊*，18(22)：9393–9400，2018 年。

+   [208] 张和邹（2018）⟧zhang2018time 张润天和邹倩。利用 LSTM 神经网络对光变曲线进行时间序列预测和异常检测。载于*《物理学杂志：会议系列》*，第 1061 卷，第 012012 页。IOP 出版，2018 年。

+   [209] 查汉和维格（2015）⟧chauhan2015anomaly 苏切塔·查汉和洛维克什·维格。通过深度长短期记忆网络对 ECG 时间信号进行异常检测。载于*数据科学与高级分析（DSAA），2015 年 IEEE 国际会议*，第 1–7 页。IEEE，2015 年。

+   [210] 施密特-厄尔弗斯等（2018）施密特-厄尔弗斯、萨德吉普尔、吉伦达斯、瓦尔德斯坦和博古诺维奇⟧schmidt2018artificial 乌尔苏拉·施密特-厄尔弗斯、阿米尔·萨德吉普尔、比安卡·S·吉伦达斯、塞巴斯蒂安·M·瓦尔德斯坦和赫尔沃耶·博古诺维奇。视网膜中的人工智能。*视网膜与眼部研究进展*，2018 年。

+   [211] 伊亚科维季斯等（2018）伊亚科维季斯、乔治卡波洛斯、瓦西拉卡基斯、库劳基季斯和普拉吉安纳科斯⟧iakovidis2018detecting 迪米特里斯·K·伊亚科维季斯、斯皮罗斯·V·乔治卡波洛斯、迈克尔·瓦西拉卡基斯、阿纳斯塔西奥斯·库劳基季斯和瓦西利斯·P·普拉吉安纳科斯。利用深度学习和迭代集群统一检测和定位胃肠道异常。*IEEE 医学影像学报*，2018 年。

+   [212] 刘与查瓦拉（2017）⟧liu2017social 柳岩和桑贾伊·查瓦拉。社交媒体异常检测：挑战与解决方案。载于*第十届 ACM 国际网页搜索与数据挖掘会议论文集*，第 817–818 页。ACM，2017 年。

+   [213] 萨维奇等（2014）萨维奇、张、于、周和王⟧savage2014anomaly 大卫·萨维奇、张秀珍、于兴华、周宝琳和王青麦。在线社交网络中的异常检测。*社会网络*，39：62–70，2014 年。

+   [214] 安南等（2017）安南、库玛和安南⟧anand2017anomaly 凯坦·安南、杰伊·库玛和库纳尔·安南。在线社交网络中的异常检测：综述。载于*2017 国际通信与计算技术会议（ICICCT）*，第 456–459 页。IEEE，2017 年。

+   [215] 于等（2016）于、邱、温、林和刘⟧yu2016survey 罗斯·于、邱慧达、温臻、林景勇和刘岩。社交媒体异常检测综述。*ACM SIGKDD 探索通讯*，18(1)：1–14，2016 年。

+   [216] 曹等（2018b）曹、郭、李、金、郭和李⟧cao2018automatic 曹娟、郭俊波、李熙荣、金智伟、郭涵和李金涛。微博上的自动谣言检测：综述。*arXiv 预印本 arXiv:1807.03505*，2018b 年。

+   [217] 张等（2017）张、陈、杨、刘和李⟧zhang2017detecting 张岩、陈伟凌、蔡健杨、刘朝栋和李佑星。利用多层自编码器检测在线社交网络上的谣言。载于*2017 IEEE 技术与工程管理会议（TEMSCON）*，第 437–441 页。IEEE，2017 年。

+   [218] Castellini et al.(2017)Castellini, Poggioni, and Sorbi⟧castellini2017fake Jacopo Castellini, Valentina Poggioni, and Giulia Sorbi. 通过去噪自编码器检测虚假 Twitter 粉丝。见于*国际网络智能会议论文集*，第 195-202 页。ACM，2017 年。

+   [219] Sun et al.(2018)Sun, Zhang, Ding, and Quan⟧sun2018detecting Xiao Sun, Chen Zhang, Shuai Ding, and Changqin Quan. 基于深度学习方法，通过社交网络的大数据检测异常情感。*多媒体工具与应用*，第 1-22 页，2018 年。

+   [220] Shu et al.(2017)Shu, Xu, and Liu⟧shu2017doc Lei Shu, Hu Xu, and Bing Liu. Doc: 文本文件的深度开放分类。*arXiv 预印本 arXiv:1709.08716*，2017 年。

+   [221] Yang et al.(2018)Yang, Cao, Ni, and Zou⟧yang2018anomaly Biao Yang, Jinmeng Cao, Rongrong Ni, and Ling Zou. 通过时空自编码和附加注意力在移动人群中进行异常检测。*多媒体进展*，2018 年。

+   [222] Li et al.(2017a)Li, Sun, Zhu, and Lin⟧li2017detecting Ze Li, Duoyong Sun, Renqi Zhu, and Zihan Lin. 使用优化神经网络模型检测组织网络中的事件相关变化。*PloS one*，12(11):e0188733，2017 年。

+   [223] Wei(2017)⟧wei2017new Wei. 社交网络中的异常检测混合模型。*arXiv 预印本 arXiv:1709.08716*，2017 年。

+   [224] Memon(2008)⟧memon2008log Ahmed Umar Memon. *基于语法推断的日志文件分类和异常分析*。博士论文，2008 年。

+   [225] Brown et al.(2018)Brown, Tuor, Hutchinson, and Nichols⟧brown2018recurrent Andy Brown, Aaron Tuor, Brian Hutchinson, and Nicole Nichols. 用于可解释系统日志异常检测的递归神经网络注意机制。*arXiv 预印本 arXiv:1803.04967*，2018 年。

+   [226] Das et al.(2018)Das, Mueller, Siegel, and Vishnu⟧das2018desh Anwesha Das, Frank Mueller, Charles Siegel, and Abhinav Vishnu. Desh: 深度学习用于高性能计算中的系统健康预测。见于*第 27 届国际高性能并行和分布式计算研讨会论文集*，第 40-51 页。ACM，2018 年。

+   [227] Malhotra et al.(2015)Malhotra, Vig, Shroff, and Agarwal⟧malhotra2015long Pankaj Malhotra, Lovekesh Vig, Gautam Shroff, and Puneet Agarwal. 用于时间序列异常检测的长短期记忆网络。见于*论文集*，第 89 页。洛万大学出版社，2015 年。

+   [228] Sakurada and Yairi(2014)⟧sakurada2014anomaly Mayu Sakurada and Takehisa Yairi. 使用自编码器和非线性降维的异常检测。见于*MLSDA 2014 第二届感知数据分析机器学习研讨会论文集*，第 4 页。ACM，2014 年。

+   [229] Nolle et al.(2018a)Nolle, Luettgen, Seeliger, and Mühlhäuser⟧nolle2018analyzing Timo Nolle, Stefan Luettgen, Alexander Seeliger, and Max Mühlhäuser. 使用自编码器分析业务流程异常。*机器学习*，第 1-19 页，2018 年。

+   [230] Nolle 等（2016）蒂莫·诺勒、亚历山大·西利格和马克斯·缪尔豪斯。使用去噪自编码器进行噪声业务过程事件日志的无监督异常检测。在 *国际发现科学会议* 中，第 442–456 页。Springer，2016。

+   [231] Grover（2018）阿里什·格罗弗。应用日志数据的异常检测。2018 年。

+   [232] Wolpher（2018）马克西姆·沃尔弗。使用 LSTM 自编码器在非结构化时间序列数据中进行异常检测，2018 年。

+   [233] 张等（2018b）张东雪、郑阳、温宇雀、王景戎、余杨和孟丹。基于角色的日志分析应用深度学习进行内部威胁检测。在 *第 1 届计算机架构和处理器安全设计研讨会论文集* 中，第 18–20 页。ACM，2018b。

+   [234] Nanduri 和 Sherry（2016）安瓦尔德·南杜里和兰斯·谢里。使用递归神经网络（rnn）进行航空数据异常检测。在 *2016 年集成通信导航与监视会议（ICNS）* 中，第 5C2–1 页。IEEE，2016。

+   [235] 冯铭等（2017）冯铭、舒芳、郭志敏、吴博、田世铭和潘明明。基于编码器-解码器框架和递归神经网络的智能电网异常检测。*中国邮电大学学报*，24(6)：67–73，2017 年。

+   [236] Marchi 等（2015）埃里克·马尔奇、法比奥·维斯佩里尼、费利克斯·维宁格、弗洛里安·艾本、斯特凡诺·斯夸尔蒂尼和比约恩·舒勒。使用 LSTM 递归神经网络进行声学新奇检测的非线性预测。在 *2015 年国际联合神经网络大会（IJCNN）* 中，第 1–7 页。IEEE，2015。

+   [237] 陆等（2018）陆思洋、魏翔、李艳东和王立强。使用卷积神经网络在大数据系统日志中检测异常。在 *2018 年 IEEE 第 16 届可靠、自主与安全计算国际会议、第 16 届普适智能与计算国际会议、第 4 届大数据智能与计算国际会议和网络科学与技术大会（DASC/PiCom/DataCom/CyberSciTech）* 中，第 151–158 页。IEEE，2018。

+   [238] 袁等（2018a）袁芳芳、曹亚楠、商艳敏、刘艳冰、谭建龙和方宾兴。基于深度神经网络的内部威胁检测。在 *国际计算科学会议* 中，第 43–54 页。Springer，2018a。

+   [239] Racki 等人（2018）的研究⟧racki2018compact 多明·拉奇，德扬·托马泽维奇和达尼耶尔·斯科贾伊。(2018 年)。用于纹理表面异常检测的紧凑型卷积神经网络。在《2018 年 IEEE 冬季计算机视觉应用研讨会 (WACV)》上，第 1331-1339 页。IEEE，2018 年。

+   [240] Zhou 等人（2016）的研究⟧zhou2016spatial 周世福，申伟，曾丹，方媚，韦源旺和张志江。(2016 年)。拥挤场景中的异常检测和定位的时空卷积神经网络。《Signal Processing: Image Communication》，47:358-368，2016 年。

+   [241] Gorokhov 等人（2017）的研究⟧gorokhov2017convolutional Oleg Gorokhov，Mikhail Petrovskiy 和 Igor Mashechkin。(2017 年)。用于无监督文本数据异常检测的卷积神经网络。在《智能数据工程和自动化学习国际会议》上，第 500-507 页。Springer，2017 年。

+   [242] Liao 等人（2017）的研究⟧liao2017deep Nicholas Liao，Matthew Guzdial 和 Mark Riedl。(2017 年)。在日志和关卡数据上进行深度卷积玩家建模。在《数字游戏基础国际会议的论文集》上，第 41 页。ACM，2017 年。

+   [243] Cheng 等人（2017）的研究⟧cheng2017deep 程杰超，任锐，王雷和战剑峰。(2017 年)。分布式系统上用于异常事件分类的深度卷积神经网络。《arXiv 预印本 arXiv:1710.09052》，2017 年。

+   [244] Zhang 等人（2018c）的研究⟧zhang2018alphamex 张博学，赵祺，冯文全和吕述昌。(2018 年 c)。Alphamex: 一种更智能的卷积神经网络全局池化方法。《Neurocomputing》，321:36-48，2018 年。

+   [245] Mohammadi 等人（2018）的研究⟧mohammadi2018deep Mehdi Mohammadi，Ala Al-Fuqaha，Sameh Sorour 和 Mohsen Guizani。(2018 年)。物联网大数据和流式分析的深度学习：一项调查。《IEEE 通信调查与教程》，2018 年。

+   [246] Luo 和 Nagarajany（2018）的研究⟧luo2018distributed 卢奥和赛·G·纳加拉贾亚。(2018 年)。分布式自编码神经网络在物联网中用于无线传感器网络的异常检测。在《2018 IEEE 国际通信大会 (ICC)》上，第 1-6 页。IEEE, 2018 年。

+   [247] Mohammadi 和 Kwasinski（2018）的研究⟧mohammadi2018neural Fatemeh Shah Mohammadi 和 Andres Kwasinski。(2018 年)。神经网络认知引擎用于自治和分布式下行动态谱访问。《arXiv 预印本 arXiv:1806.11038》，2018 年。

+   [248] Kakanakova 和 Stoyanov（2017）的研究⟧kakanakova2017outlier Irina Kakanakova 和 Stefan Stoyanov。(2017 年)。通过深度学习架构进行异常检测。在《第 18 届计算机系统和技术国际会议的论文集》上，第 73-79 页。ACM，2017 年。

+   [249] Zhang et al.(2018d) Zhang, Guo, Liu, Liu, Zhou, Li, Lu, and Yang⟧zhang2018lstm Weishan Zhang、Wuwu Guo、Xin Liu、Yan Liu、Jiehan Zhou、Bo Li、Qinghua Lu 和 Su Yang。基于 lstm 的工业物联网设备分析。 *IEEE Access*，6：23551–23560，2018d。

+   [250] Mudassar et al.(2018) Mudassar, Ko, and Mukhopadhyay⟧mudassar2018unsupervised Burhan A Mudassar、Jong Hwan Ko 和 Saibal Mukhopadhyay。具有类别感知源分离的无监督异常事件检测框架。见于 *2018 IEEE 国际声学、语音和信号处理会议（ICASSP）*，第 2671–2675 页。IEEE，2018 年。

+   [251] Martí et al.(2015) Martí, Sanchez-Pi, Molina, and Garcia⟧marti2015anomaly Luis Martí、Nayat Sanchez-Pi、José Manuel Molina 和 Ana Cristina Bicharra Garcia。基于传感器数据的石油工业应用中的异常检测。 *传感器*，15(2)：2774–2797，2015 年。

+   [252] Atha and Jahanshahi(2018)⟧atha2018evaluation Deegan J Atha 和 Mohammad R Jahanshahi。基于卷积神经网络的腐蚀检测深度学习方法评估。 *结构健康监测*，17(5)：1110–1128，2018 年。

+   [253] de Deijn(2018)⟧de2018automatic Jeffrey de Deijn。使用卷积神经网络的自动汽车损伤识别。2018 年。

+   [254] Wang et al.(2018c) Wang, Kerekes, Xu, and Wang⟧wang2018residential Fan Wang、John P Kerekes、Zhuoyi Xu 和 Yandong Wang。基于深度学习的住宅屋顶条件评估系统。 *应用遥感期刊*，12(1)：016040，2018c。

+   [255] Inoue et al.(2017) Inoue, Yamagata, Chen, Poskitt, and Sun⟧inoue2017anomaly Jun Inoue、Yoriyuki Yamagata、Yuqi Chen、Christopher M Poskitt 和 Jun Sun。基于无监督机器学习的水处理系统异常检测。见于 *数据挖掘研讨会（ICDMW），2017 IEEE 国际会议*，第 1058–1065 页。IEEE，2017 年。

+   [256] Thi et al.(2017) Thi, Le-Khac, et al.⟧thi2017one 吳·阮、李克赫等。一类集合异常检测基于 lstm-rnns。见于 *大规模数据和知识中心系统交易 XXXVI*，第 73–85 页。施普林格，2017 年。

+   [257] Kravchik and Shabtai(2018)⟧kravchik2018detecting Moshe Kravchik 和 Asaf Shabtai。使用卷积神经网络检测工业控制系统中的网络攻击。见于 *2018 年网络物理系统安全与隐私研讨会论文集*，第 72–83 页。ACM，2018 年。

+   [258] Huang et al.(2018) Huang, Chu, and Wu⟧huang2018deep 关杰·黄、楚和吴。基于深度学习的睡眠阶段分类方法，使用生理信号。见于 *国际智能健康大会*，第 249–260 页。施普林格，2018 年。

+   [259] Park et al.(2018a) Park, Kim, An, and Jung⟧park2018lired Donghyun Park, Seulgi Kim, Yelin An, 和 Jae-Yoon Jung。Lired：一种轻量级实时故障检测系统，适用于边缘计算，使用 lstm 递归神经网络。 *传感器*，18(7)：2110，2018a。

+   [260] Chang 等（2018）Chang、Lee 和 Liu⟧chang2018review Chih-Wen Chang、Hau-Wei Lee 和 Chein-Hung Liu。智能机床中使用的人工智能算法综述。*Inventions*，3(3):41，2018 年。

+   [261] Yuan 和 Jia（2015）⟧yuan2015distributed Ye Yuan 和 Kebin Jia。利用智能电表数据的分布式异常检测方法。发表于*2015 年智能信息隐藏与多媒体信号处理国际会议（IIH-MSP）*，第 310–313 页。IEEE，2015 年。

+   [262] Araya 等（2017）Araya、Grolinger、ElYamany、Capretz 和 Bitsuamlak⟧araya2017ensemble Daniel B Araya、Katarina Grolinger、Hany F ElYamany、Miriam AM Capretz 和 Girma Bitsuamlak。用于建筑能耗异常检测的集成学习框架。*Energy and Buildings*，144:191–206，2017 年。

+   [263] Qu 等（2017）Qu、He、Deutsch 和 He⟧qu2017detection Yongzhi Qu、Miao He、Jason Deutsch 和 David He。使用深度稀疏自编码器检测齿轮中的点蚀。*Applied Sciences*，7(5):515，2017 年。

+   [264] Bhattad 等（2018）Bhattad、Rock 和 Forsyth⟧bhattad2018detecting Anand Bhattad、Jason Rock 和 David Forsyth。使用‘no peeking’自编码器检测异常人脸。*arXiv 预印本 arXiv:1802.05798*，2018 年。

+   [265] Lodhi 等（2017）Lodhi、Hasan、Hasan 和 Awwadl⟧lodhi2017power Faiq Khalid Lodhi、Syed Rafay Hasan、Osman Hasan 和 Falah Awwadl。用于运行时硬件木马检测的微控制器指令集功率分析，无需黄金电路模型。发表于*欧洲设计、自动化与测试会议论文集*，第 294–297 页。欧洲设计与自动化协会，2017 年。

+   [266] Faghih-Roohi 等（2016）Faghih-Roohi、Hajizadeh、Núñez、Babuska 和 De Schutter⟧faghih2016deep Shahrzad Faghih-Roohi、Siamak Hajizadeh、Alfredo Núñez、Robert Babuska 和 Bart De Schutter。用于检测轨道表面缺陷的深度卷积神经网络。发表于*2016 年国际联合神经网络会议（IJCNN）*，第 2584–2589 页。IEEE，2016 年。

+   [267] Christiansen 等（2016）Christiansen、Nielsen、Steen、Jørgensen 和 Karstoft⟧christiansen2016deepanomaly Peter Christiansen、Lars N Nielsen、Kim A Steen、Rasmus N Jørgensen 和 Henrik Karstoft。Deepanomaly：结合背景减除和深度学习用于检测农业领域中的障碍物和异常。*Sensors*，16(11):1904，2016 年。

+   [268] Lee 等（2016）Lee、Siu、Cruz 和 Yetman⟧lee2016convolutional Dean Lee、Vincent Siu、Rick Cruz 和 Charles Yetman。卷积神经网络与轴承故障分析。发表于*2016 年国际数据挖掘会议（ICDM）巴塞罗那论文集*，第 194–200 页，2016 年。

+   [269] Dong 等（2016）Dong、Zhang、Wen 和 Wu⟧dong2016camera Lingping Dong、Yongliang Zhang、Conglin Wen 和 Hongtao Wu。基于形态学分析和深度学习的摄像头异常检测。发表于*2016 年 IEEE 国际数字信号处理会议（DSP）*，第 266–270 页。IEEE，2016 年。

+   [270] Fuentes 等(2017)Fuentes, Yoon, Kim, 和 Park⟧fuentes2017robust Alvaro Fuentes, Sook Yoon, Sang Cheol Kim, 和 Dong Sun Park。基于深度学习的实时番茄植物疾病和害虫识别的鲁棒检测器。*Sensors*，17(9):2022，2017 年。

+   [271] Yan 和 Yu(2015)⟧yan2015accurate Weizhong Yan 和 Lijie Yu。气体涡轮燃烧器的准确和可靠异常检测：一种深度学习方法。见于 *预测与健康管理学会年会论文集*，2015 年。

+   [272] Luo 和 Zhong(2017)⟧luo2017gas Hui Luo 和 Shisheng Zhong。使用具有高斯分布的深度学习进行气体涡轮发动机气体路径异常检测。见于 *预测与系统健康管理会议（PHM-Harbin），2017 年*，第 1–6 页。IEEE，2017 年。

+   [273] Dai 等(2017)Dai, Song, Sheng, 和 Jiang⟧dai2017cleaning Jiejie Dai, Hui Song, Gehao Sheng, 和 Xiuchen Jiang。基于堆叠去噪自编码器的电力设备状态监测数据清洗方法。*IEEE Access*，5:22863–22870，2017 年。

+   [274] Banjanovic-Mehmedovic 等(2017)Banjanovic-Mehmedovic, Hajdarevic, Kantardzic, Mehmedovic, 和 Dzananovic⟧banjanovic2017neural Lejla Banjanovic-Mehmedovic, Amel Hajdarevic, Mehmed Kantardzic, Fahrudin Mehmedovic, 和 Izet Dzananovic。基于神经网络的数据驱动热电厂异常检测建模。*Automatika*，58(1):69–79，2017 年。

+   [275] Shipmon 等(2017a)Shipmon, Gurevitch, Piselli, 和 Edwards⟧shipmon2017time Dominique T Shipmon, Jason M Gurevitch, Paolo M Piselli, 和 Stephen T Edwards。时间序列异常检测；在噪声高度周期性数据中，通过有限特征和稀疏样本检测异常下降。*arXiv 预印本 arXiv:1708.03665*，2017 年。

+   [276] Hundman 等(2018)Hundman, Constantinou, Laporte, Colwell, 和 Soderstrom⟧hundman2018detecting Kyle Hundman, Valentino Constantinou, Christopher Laporte, Ian Colwell, 和 Tom Soderstrom。使用 LSTM 和非参数动态阈值检测航天器异常。*arXiv 预印本 arXiv:1802.04431*，2018 年。

+   [277] Zhu 和 Laptev(2017)⟧zhu2017deep Lingxue Zhu 和 Nikolay Laptev。对 Uber 的时间序列进行深度和自信预测。见于 *数据挖掘研讨会（ICDMW），2017 IEEE 国际会议*，第 103–110 页。IEEE，2017 年。

+   [278] Assendorp(2017)⟧assendorp2017deep Jan Paul Assendorp。*多变量时间序列数据中的深度学习异常检测*。博士论文，汉堡应用科技大学，2017 年。

+   [279] Ahmad 等(2017)Ahmad, Lavin, Purdy, 和 Agha⟧ahmad2017unsupervised Subutai Ahmad, Alexander Lavin, Scott Purdy, 和 Zuha Agha。用于流数据的无监督实时异常检测。*Neurocomputing*，262:134–147，2017 年。

+   [280] Malhotra 等人（2016a）Malhotra, Ramakrishnan, Anand, Vig, Agarwal 和 Shroff⟧malhotra2016lstm Pankaj Malhotra, Anusha Ramakrishnan, Gaurangi Anand, Lovekesh Vig, Puneet Agarwal 和 Gautam Shroff。基于 LSTM 的编码器-解码器用于多传感器异常检测。*arXiv 预印本 arXiv:1607.00148*，2016a。

+   [281] Taylor 等人（2016）Taylor, Leblanc 和 Japkowicz⟧taylor2016anomaly Adrian Taylor, Sylvain Leblanc 和 Nathalie Japkowicz。利用长短期记忆网络对汽车控制网络数据进行异常检测。在 *数据科学与高级分析（DSAA），2016 IEEE 国际会议*，第 130–139 页。IEEE，2016。

+   [282] Cheng 等人（2016）Cheng, Xu, Lv, Liu, Li, Wang 等⟧cheng2016ms Min Cheng, Qian Xu, Jianming Lv, Wenyin Liu, Qing Li, Jianping Wang 等。MS-LSTM：一种用于 BGP 异常检测的多尺度 LSTM 模型。在 *2016 IEEE 第 24 届国际网络协议会议（ICNP）*，第 1–6 页。IEEE，2016。

+   [283] Loganathan 等人（2018）Loganathan, Samarabandu 和 Wang⟧loganathan2018sequence Gobinath Loganathan, Jagath Samarabandu 和 Xianbin Wang。用于实时网络流量异常检测的序列到序列模式学习算法。在 *2018 IEEE 加拿大电气与计算机工程会议（CCECE）*，第 1–4 页。IEEE，2018。

+   [284] Munir 等人（2018）Munir, Siddiqui, Dengel 和 Ahmed⟧munir2018deepant Mohsin Munir, Shoaib Ahmed Siddiqui, Andreas Dengel 和 Sheraz Ahmed。Deepant：一种用于时间序列无监督异常检测的深度学习方法。*IEEE Access*，2018。

+   [285] Shipmon 等人（2017b）Shipmon, Gurevitch, Piselli 和 Edwards⟧Dominique Dominique Shipmon, Jason Gurevitch, Paolo M Piselli 和 Steve Edwards。时间序列异常检测：在噪声周期数据中使用有限特征和稀疏示例检测异常下降。技术报告，谷歌公司，2017b。网址 [`arxiv.org/abs/1708.03665`](https://arxiv.org/abs/1708.03665)。

+   [286] Malhotra 等人（2016b）Malhotra, TV, Ramakrishnan, Anand, Vig, Agarwal 和 Shroff⟧malhotra2016multi Pankaj Malhotra, Vishnu TV, Anusha Ramakrishnan, Gaurangi Anand, Lovekesh Vig, Puneet Agarwal 和 Gautam Shroff。基于 LSTM 编码器-解码器的无监督健康指数的多传感器预测。*arXiv 预印本 arXiv:1608.06154*，2016b。

+   [287] Filonov 等人（2016）Filonov, Lavrentyev 和 Vorontsov⟧filonov2016multivariate Pavel Filonov, Andrey Lavrentyev 和 Artem Vorontsov。多变量工业时间序列与网络攻击模拟：使用基于 LSTM 的预测数据模型进行故障检测。*arXiv 预印本 arXiv:1612.06676*，2016。

+   [288] Sugimoto 等人（2018）Sugimoto, Lee 和 Okada⟧sugimoto2018deep Kaiji Sugimoto, Saerom Lee 和 Yoshifumi Okada。基于深度学习的 ECG 数据周期性异常波检测。在 *国际工程师和计算机科学家多会议论文集*，第 1 卷，2018。

+   [289] Oh 和 Yun(2018)⟧oh2018residual Dong Yul Oh 和 Il Dong Yun。基于残差误差的异常检测，使用自动编码器处理 SMD 机器声音。*传感器（巴塞尔，瑞士）*，18(5)，2018 年。

+   [290] Ebrahimzadeh 和 Kleinberg()⟧ebrahimzadehmulti Zahra Ebrahimzadeh 和 Samantha Kleinberg。在多变量时间序列中的多尺度变点检测。

+   [291] Veeramachaneni 等(2016)Veeramachaneni, Arnaldo, Korrapati, Bassias 和 Li⟧veeramachaneni2016ai Kalyan Veeramachaneni, Ignacio Arnaldo, Vamsi Korrapati, Constantinos Bassias 和 Ke Li。AI^ 2：训练大型数据机器进行防御。在*云计算大数据安全（BigDataSecurity），IEEE 高性能与智能计算国际会议（HPSC）以及 IEEE 智能数据与安全国际会议（IDS），2016 IEEE 第二届国际会议*，第 49–54 页。IEEE，2016 年。

+   [292] Dau 等(2014)Dau, Ciesielski 和 Song⟧dau2014anomaly Hoang Anh Dau, Vic Ciesielski 和 Andy Song。利用在单类样本上训练的复制神经网络进行异常检测。在*亚太模拟进化与学习会议*，第 311–322 页。Springer，2014 年。

+   [293] Wielgosz 等(2017)Wielgosz, Skoczeń和 Mertik⟧wielgosz2017recurrent Maciej Wielgosz, Andrzej Skoczeń和 Matej Mertik。用于 LHC 超导磁体事后时间序列异常检测的递归神经网络。*arXiv 预印本 arXiv:1702.00833*，2017 年。

+   [294] Saurav 等(2018)Saurav, Malhotra, TV, Gugulothu, Vig, Agarwal 和 Shroff⟧saurav2018online Sakti Saurav, Pankaj Malhotra, Vishnu TV, Narendhar Gugulothu, Lovekesh Vig, Puneet Agarwal 和 Gautam Shroff。使用递归神经网络进行在线异常检测，并适应概念漂移。在*ACM 印度联合国际数据科学与数据管理会议论文集*，第 78–87 页。ACM，2018 年。

+   [295] Wielgosz 等(2018)Wielgosz, Mertik, Skoczeń和 De Matteis⟧wielgosz2018model Maciej Wielgosz, Matej Mertik, Andrzej Skoczeń和 Ernesto De Matteis。基于递归神经网络和自适应量化的高亮 LHC 磁体异常检测模型。*人工智能工程应用*，74:166–185，2018 年。

+   [296] Guo 等(2016)Guo, Xu, Yao, Chen, Aberer 和 Funaya⟧guo2016robust Tian Guo, Zhao Xu, Xin Yao, Haifeng Chen, Karl Aberer 和 Koichi Funaya。使用递归神经网络进行稳健的在线时间序列预测。在*数据科学与高级分析（DSAA），2016 IEEE 国际会议*，第 816–825 页。IEEE，2016 年。

+   [297] Filonov 等(2017)Filonov, Kitashov 和 Lavrentyev⟧filonov2017rnn Pavel Filonov, Fedor Kitashov 和 Andrey Lavrentyev。基于 RNN 的田纳西东曼过程早期网络攻击检测。*arXiv 预印本 arXiv:1709.02232*，2017 年。

+   [298] Kanarachos 等(2017)Kanarachos, Christopoulos, Chroneos, 和 Fitzpatrick⟧kanarachos2017detecting Stratis Kanarachos, Stavros-Richard G Christopoulos, Alexander Chroneos, 和 Michael E Fitzpatrick。通过结合小波变换、神经网络和希尔伯特变换的深度学习算法检测时间序列数据中的异常。*应用专家系统*，85：292–304，2017 年。

+   [299] Du 等()Du, Pandey, 和 Xing⟧dumodeling Shuyang Du, Madhulima Pandey, 和 Cuiqun Xing。时间序列预测和异常检测的建模方法。

+   [300] Napoletano 等(2018)Napoletano, Piccoli, 和 Schettini⟧napoletano2018anomaly Paolo Napoletano, Flavio Piccoli, 和 Raimondo Schettini。基于卷积神经网络的自相似性在纳米纤维材料中的异常检测。*传感器*，18(1)：209，2018 年。

+   [301] Shanmugam 等(2018)Shanmugam, Blalock, 和 Guttag⟧shanmugam2018jiffy Divya Shanmugam, Davis Blalock, 和 John Guttag。Jiffy：一种学习时间序列相似性的卷积方法。2018 年。

+   [302] Medel 和 Savakis(2016)⟧medel2016anomaly Jefferson Ryan Medel 和 Andreas Savakis。使用预测卷积长短期记忆网络进行视频中的异常检测。*arXiv 预印本 arXiv:1612.00390*，2016 年。

+   [303] Park 等(2018b)Park, Hoshi, 和 Kemp⟧park2018multimodal Daehyung Park, Yuuna Hoshi, 和 Charles C Kemp。基于 LSTM 的变分自编码器的机器人辅助喂食的多模态异常检测器。*IEEE 机器人与自动化通讯*，3(3)：1544–1551，2018 年。

+   [304] Sölch 等(2016)Sölch, Bayer, Ludersdorfer, 和 van der Smagt⟧solch2016variational Maximilian Sölch, Justin Bayer, Marvin Ludersdorfer, 和 Patrick van der Smagt。高维时间序列中的在线异常检测的变分推断。*arXiv 预印本 arXiv:1602.07109*，2016 年。

+   [305] Zenati 等(2018)Zenati, Foo, Lecouat, Manek, 和 Chandrasekhar⟧zenati2018efficient Houssam Zenati, Chuan Sheng Foo, Bruno Lecouat, Gaurav Manek, 和 Vijay Ramaseshan Chandrasekhar。基于生成对抗网络的高效异常检测。*arXiv 预印本 arXiv:1802.06222*，2018 年。

+   [306] Lim 等(2018)Lim, Loo, Tran, Cheung, Roig, 和 Elovici⟧lim2018doping Swee Kiat Lim, Yi Loo, Ngoc-Trung Tran, Ngai-Man Cheung, Gemma Roig, 和 Yuval Elovici。Doping：使用生成对抗网络的无监督异常检测的数据增强。*arXiv 预印本 arXiv:1808.07632*，2018 年。

+   [307] Laptev()⟧laptevanogen Nikolay Laptev。Anogen：深度异常生成器。

+   [308] Wei 等(2018)Wei, Zhao, Zhao, 和 Zhao⟧wei2018unsupervised JiaYi Wei, JianFei Zhao, YanYun Zhao, 和 ZhiCheng Zhao。基于背景建模的交通监控无监督异常检测。载于*IEEE 计算机视觉与模式识别会议研讨会论文集*，第 129–136 页，2018 年。

+   [309] Buda 等（2018）Buda、Caglayan 和 Assem⟧buda2018deepad Teodora Sandra Buda、Bora Caglayan 和 Haytham Assem。Deepad：基于深度学习的时间序列异常检测通用框架。在*太平洋-亚洲知识发现与数据挖掘会议*上，页码 577–588。Springer，2018 年。

+   [310] Yuan 等（2018b）Yuan、Xun、Ma、Wang、Du、Jia、Su 和 Zhang⟧yuan2018muvan Ye Yuan、Guangxu Xun、Fenglong Ma、Yaqing Wang、Nan Du、Kebin Jia、Lu Su 和 Aidong Zhang。Muvan：用于多变量时间数据的多视角注意力网络。在*2018 IEEE 国际数据挖掘会议（ICDM）*上，页码 717–726。IEEE，2018b。

+   [311] Guo 和 Lin（2018）⟧guo2018exploring Tian Guo 和 Tao Lin。探索 LSTM 神经网络在多变量数据上的可解释性。2018 年。

+   [312] Nucci 等（2018）Nucci、Cui、Garrett、Singh 和 Croley⟧nucci2018real Antonio Nucci、Song Cui、John Garrett、Gurvinder Singh 和 Kenneth Croley。用于下一代网络的实时多变量多时间尺度异常检测系统。2018 年。

+   [313] Assendorp 等（2017）Assendorp、Meisel、Bohlen 和 Sommer⟧Assendorp2017DeepLF Jan Paul Assendorp、Andreas Meisel、H. Glenn Bohlen 和 C Sommer。用于多变量时间序列数据异常检测的深度学习。2017 年。

+   [314] Nolle 等（2018b）Nolle、Seeliger 和 Mühlhäuser⟧nolle2018binet Timo Nolle、Alexander Seeliger 和 Max Mühlhäuser。Binet：使用深度学习的多变量业务流程异常检测。在*国际业务流程管理会议*上，页码 271–287。Springer，2018b。

+   [315] Zhang 等（2018e）Zhang、Song、Chen、Feng、Lumezanu、Cheng、Ni、Zong、Chen 和 Chawla⟧zhang2018deep Chuxu Zhang、Dongjin Song、Yuncong Chen、Xinyang Feng、Cristian Lumezanu、Wei Cheng、Jingchao Ni、Bo Zong、Haifeng Chen 和 Nitesh V Chawla。用于多变量时间序列数据的无监督异常检测和诊断的深度神经网络。*arXiv 预印本 arXiv:1811.08055*，2018e。

+   [316] Guo 等（2018）Guo、Liao、Wang、Yu、Ji 和 Li⟧guo2018multidimensional Yifan Guo、Weixian Liao、Qianlong Wang、Lixing Yu、Tianxi Ji 和 Pan Li。多维时间序列异常检测：一种基于 GRU 的高斯混合变分自编码器方法。在*亚洲机器学习会议*上，页码 97–112，2018 年。

+   [317] Fu 等（2019）Fu、Luo、Zhong 和 Lin⟧fu2019aircraft Xuyun Fu、Hui Luo、Shisheng Zhong 和 Lin Lin。基于分组卷积去噪自编码器的飞机发动机故障检测。*中国航空学报*，2019 年。

+   [318] Kieu 等（2018）Kieu、Yang 和 Jensen⟧kieu2018outlier Tung Kieu、Bin Yang 和 Christian S Jensen。使用深度神经网络的多维时间序列异常检测。在*2018 年第 19 届 IEEE 国际移动数据管理会议（MDM）*上，页码 125–134。IEEE，2018 年。

+   [319] Basumallik 等（2019）Sagnik Basumallik, Rui Ma 和 Sara Eftekharnejad。基于 PMU 的状态估计中的数据包异常检测，使用卷积神经网络。*国际电力与能源系统期刊*，107:690–702，2019。

+   [320] Ikeda 等（2018）Yasuhiro Ikeda, Kengo Tajiri, Yuusuke Nakano, Keishiro Watanabe 和 Keisuke Ishibashi。利用变分自编码器估计对检测到的异常有贡献的维度。*arXiv 预印本 arXiv:1811.04576*，2018。

+   [321] Li 等（2019）Dan Li, Dacheng Chen, Lei Shi, Baihong Jin, Jonathan Goh 和 See-Kiong Ng。MAD-GAN：基于生成对抗网络的多变量时间序列数据异常检测。*arXiv 预印本 arXiv:1901.04997*，2019。

+   [322] Tuor 等（2018）Aaron Randall Tuor, Ryan Baerwolf, Nicolas Knowles, Brian Hutchinson, Nicole Nichols 和 Robert Jasper。用于开放词汇事件级网络异常检测的递归神经网络语言模型。见于*第三十二届 AAAI 人工智能会议研讨会*，2018。

+   [323] Maia（2017）Rui Maia。多变量时间数据分析用于船舶行为异常检测。2017。

+   [324] Dal Pozzolo 等（2015）Andrea Dal Pozzolo, Olivier Caelen, Reid A Johnson 和 Gianluca Bontempi。通过欠采样对不平衡分类进行概率校准。见于*2015 年 IEEE 计算智能学术研讨会*，第 159–166 页。IEEE，2015。

+   [325] Cui 等（2016）Yuwei Cui, Chetan Surpur, Subutai Ahmad 和 Jeff Hawkins。HTM 与其他神经网络模型在流数据在线序列学习中的比较研究。见于*2016 年国际联合会议（IJCNN）神经网络*，第 1530–1538 页。IEEE，2016。

+   [326] Andrewsa 等（无日期）Andrewsa, Jaccarda, Rogersa, Tanaya 和 Griffina。用于安全成像的异常检测。

+   [327] Sabokrou 等（2016a）Mohammad Sabokrou, Mohsen Fayyaz, Mahmood Fathy 等。完全卷积神经网络用于在拥挤场景中快速异常检测。*arXiv 预印本 arXiv:1609.00866*，2016a。

+   [328] Sabokrou 等（2017）Mohammad Sabokrou, Mohsen Fayyaz, Mahmood Fathy 和 Reinhard Klette。Deep-cascade：级联 3D 深度神经网络用于在拥挤场景中快速异常检测和定位。*IEEE 图像处理学报*，26(4):1992–2004，2017。

+   [329] Munawar 等人(2017)Munawar, Vinayavekhin 和 De Magistris⟧munawar2017spatio Asim Munawar, Phongtharin Vinayavekhin 和 Giovanni De Magistris。通过在无监督特征空间中的预测进行工业机器人时空异常检测。见于 *2017 IEEE 冬季计算机视觉应用会议 (WACV)*，第 1017–1025 页。IEEE，2017 年。

+   [330] Li 等人(2017b)Li, Wu 和 Du⟧li2017transferred Wei Li, Guodong Wu 和 Qian Du。用于高光谱图像异常检测的转移深度学习。*IEEE 地球科学与遥感快报*，14(5):597–601，2017 年。

+   [331] Qiao 等人(2017)Qiao, Wang, Li, Li, Lin 和 Snoussi⟧qiao2017abnormal Meina Qiao, Tian Wang, Jiakun Li, Ce Li, Zhiwei Lin 和 Hichem Snoussi。基于深度自编码器融合光流的异常事件检测。见于 *2017 年第 36 届中国控制会议 (CCC)*，第 11098–11103 页。IEEE，2017 年。

+   [332] Tripathi 等人(2018)Tripathi, Singh 和 Vishwakarma⟧tripathi2018convolutional Gaurav Tripathi, Kuldeep Singh 和 Dinesh Kumar Vishwakarma。用于人群行为分析的卷积神经网络：综述。*视觉计算机*，第 1–24 页，2018 年。

+   [333] Nogas 等人(2018)Nogas, Khan 和 Mihailidis⟧nogas2018deepfall Jacob Nogas, Shehroz S Khan 和 Alex Mihailidis。Deepfall–通过深度时空卷积自编码器进行非侵入式跌倒检测。*arXiv 预印本 arXiv:1809.00977*，2018 年。

+   [334] Chong 和 Tay(2017)⟧chong2017abnormal Yong Shean Chong 和 Yong Haur Tay。使用时空自编码器进行视频中的异常事件检测。见于 *国际神经网络研讨会*，第 189–196 页。Springer，2017 年。

+   [335] Khaleghi 和 Moin(2018)⟧khaleghi2018improved Ali Khaleghi 和 Mohammad Shahram Moin。基于深度学习方法的监控视频改进异常检测。见于 *2018 年第 8 届 AI 与机器人会议及第 10 届 RoboCup 伊朗公开国际研讨会 (IRANOPEN)*，第 73–81 页。IEEE，2018 年。

+   [336] Yang 等人(2015)Yang, Wang, Lin, Wipf, Guo 和 Guo⟧yang2015unsupervised Huan Yang, Baoyuan Wang, Stephen Lin, David Wipf, Minyi Guo 和 Baining Guo。通过鲁棒递归自编码器进行视频亮点的无监督提取。见于 *IEEE 国际计算机视觉会议论文集*，第 4633–4641 页，2015 年。

+   [337] Chen 等人(2015)Chen, Tian, Zeng 和 Huang⟧chen2015detecting Zhengying Chen, Yonghong Tian, Wei Zeng 和 Tiejun Huang。基于模糊聚类和多个自编码器的监控视频异常行为检测。见于 *2015 IEEE 国际多媒体与博览会 (ICME)*，第 1–6 页。IEEE，2015 年。

+   [338] Gutoski 等人() Gutoski, Aquino, Ribeiro, Lazzaretti 和 Lopes⟧gutoskidetection Matheus Gutoski, Nelson Marcelo Romero Aquino, Manassés Ribeiro, André Engênio Lazzaretti 和 Heitor Silvério Lopes。使用卷积自编码器和单类支持向量机进行视频异常检测。

+   [339] D’Avino 等（2017）D’Avino, Cozzolino, Poggi,和 Verdoliva⟧d2017autoencoder Dario D’Avino, Davide Cozzolino, Giovanni Poggi, 和 Luisa Verdoliva. 基于递归神经网络的自动编码器用于视频伪造检测。*电子成像*，2017（7）：92–99，2017。

+   [340] Dotti 等（2017）Dotti, Popa,和 Asteriadis⟧dotti2017unsupervised Dario Dotti, Mirela Popa, 和 Stylianos Asteriadis。无监督发现室内和室外环境中的正常与异常活动模式。载于*VISIGRAPP（5：VISAPP）*，第 210–217 页，2017。

+   [341] Sabokrou 等（2016b）Sabokrou, Fathy,和 Hoseini⟧sabokrou2016video M Sabokrou, M Fathy, 和 M Hoseini。基于稀疏性和自动编码器重建误差的视频异常检测与定位。*电子快报*，52（13）：1122–1124，2016b。

+   [342] Tran 和 Hogg（2017）⟧tran2017anomaly Hanh TM Tran 和 DC Hogg。使用卷积胜者通吃自动编码器的异常检测。载于*2017 年英国机器视觉会议论文集*。利兹，2017。

+   [343] Hasan 等（2016）Hasan, Choi, Neumann, Roy-Chowdhury, 和 Davis⟧hasan2016learning Mahmudul Hasan, Jonghyun Choi, Jan Neumann, Amit K Roy-Chowdhury, 和 Larry S Davis。学习视频序列中的时间规律。载于*IEEE 计算机视觉与模式识别会议论文集*，第 733–742 页，2016。

+   [344] Cinelli（2017）⟧cinelli2017anomaly Lucas Pinheiro Cinelli。*使用深度残差网络的监控视频异常检测*。博士论文，里约热内卢联邦大学，2017。

+   [345] Sultani 等（2018）Sultani, Chen, 和 Shah⟧sultani2018real Waqas Sultani, Chen Chen, 和 Mubarak Shah。现实世界中的监控视频异常检测。*中央佛罗里达大学计算机视觉研究中心（CRCV）*，2018。

+   [346] Chianucci 和 Savakis（2016）⟧chianucci2016unsupervised Dan Chianucci 和 Andreas Savakis. 使用空间变换网络的无监督变化检测。载于*信号处理研讨会（WNYISPW），2016 IEEE Western New York Image and*，第 1–5 页。IEEE，2016。

+   [347] Luo 等（2017a）Luo, Liu, 和 Gao⟧luo2017remembering Weixin Luo, Wen Liu, 和 Shenghua Gao。使用卷积 LSTM 记忆历史进行异常检测。载于*多媒体与博览会（ICME），2017 IEEE 国际会议*，第 439–444 页。IEEE，2017a。

+   [348] Ben-Ari 和 Shwartz-Ziv（2018）⟧ben2018attentioned Itamar Ben-Ari 和 Ravid Shwartz-Ziv。用于视频异常检测的注意力卷积 LSTM 修复网络。*arXiv 预印本 arXiv:1811.10228*，2018。

+   [349] Singh（2017）⟧singh2017anomaly Akash Singh。使用长短期记忆（LSTM）的时间序列数据异常检测，2017。

+   [350] Luo 等（2017b）Luo, Liu, 和 Gao⟧luo2017revisit Weixin Luo, Wen Liu, 和 Shenghua Gao。基于稀疏编码的异常检测在堆叠 RNN 框架中的重新审视。*ICCV，10 月*，1（2）：3，2017b。

+   [351] Zhou 和 Zhang(2015)⟧zhou2015abnormal Xu-Gang Zhou 和 Li-Qing Zhang. 使用递归神经网络的异常事件检测。收录于*计算机科学与应用 (CSA), 2015 国际会议*，页码 222–226\. IEEE, 2015。

+   [352] Hu 等(2016)Hu, Hu, Huang, Zhang, 和 Wu⟧hu2016video Xing Hu, Shiqiang Hu, Yingping Huang, Huanlong Zhang, 和 Hanbing Wu. 使用深度增量慢特征分析网络的视频异常检测。*IET 计算机视觉*, 10(4):258–265, 2016。

+   [353] Chong 和 Tay(2015)⟧chong2015modeling Yong Shean Chong 和 Yong Haur Tay. 使用深度学习对视频进行异常检测的建模表示：综述。*arXiv 预印本 arXiv:1505.00523*, 2015。

+   [354] Ravanbakhsh 等(2017a)Ravanbakhsh, Sangineto, Nabi, 和 Sebe⟧ravanbakhsh2017training Mahdyar Ravanbakhsh, Enver Sangineto, Moin Nabi, 和 Nicu Sebe. 用于跨通道异常事件检测的对抗性判别器训练。*arXiv 预印本 arXiv:1706.07680*, 2017a。

+   [355] Boghossian 和 Black(2005)⟧boghossian2005challenges B Boghossian 和 J Black. 强健的 24/7 视频监控系统面临的挑战。2005。

+   [356] Görnitz 等(2013)Görnitz, Kloft, Rieck, 和 Brefeld⟧gornitz2013toward Nico Görnitz, Marius Kloft, Konrad Rieck, 和 Ulf Brefeld. 朝向监督异常检测。*人工智能研究杂志*, 46:235–262, 2013。

+   [357] Shilton 等(2013)Shilton, Rajasegarar, 和 Palaniswami⟧shilton2013combined Alistair Shilton, Sutharshan Rajasegarar, 和 Marimuthu Palaniswami. 用于大规模无线传感器网络的组合多类分类和异常检测。收录于*智能传感器、传感器网络与信息处理，第八届国际 IEEE 会议*，页码 491–496。IEEE, 2013。

+   [358] Jumutc 和 Suykens(2014)⟧jumutc2014multi Vilen Jumutc 和 Johan AK Suykens. 多类监督新颖性检测。*IEEE 计算机视觉与模式分析汇刊*, 36(12):2510–2523, 2014。

+   [359] Kim 等(2015)Kim, Choi, 和 Lee⟧kim2015deep Sangwook Kim, Yonghwa Choi, 和 Minho Lee. 基于支持向量数据描述的深度学习。*神经计算*, 165:111–117, 2015。

+   [360] Erfani 等(2017)Erfani, Baktashmotlagh, Moshtaghi, Nguyen, Leckie, Bailey, 和 Ramamohanarao⟧erfani2017shared Sarah M Erfani, Mahsa Baktashmotlagh, Masud Moshtaghi, Vinh Nguyen, Christopher Leckie, James Bailey, 和 Kotagiri Ramamohanarao. 从共享子空间到共享标记点：一种稳健的多源分类方法。收录于*AAAI*，页码 1854–1860, 2017。

+   [361] Min 等(2018)Min, Long, Liu, Cui, Cai, 和 Ma⟧min2018ids Erxue Min, Jun Long, Qiang Liu, Jianjing Cui, Zhiping Cai, 和 Junbo Ma. Su-ids：一种半监督和无监督的网络入侵检测框架。收录于*国际云计算与安全大会*，页码 322–334\. Springer, 2018。

+   [362] Perera 和 Patel (2018)⟧perera2018learning Pramuditha Perera 和 Vishal M Patel. 用于一类分类的深度特征学习。*arXiv 预印本 arXiv:1801.05365*，2018 年。

+   [363] Blanchard 等 (2010)Blanchard, Lee 和 Scott⟧blanchard2010semi Gilles Blanchard, Gyemin Lee 和 Clayton Scott. 半监督新奇检测。*机器学习研究杂志*，11（11）：2973–3009，2010 年。

+   [364] Edmunds 和 Feinstein (2017)⟧edmunds2017deep Riley Edmunds 和 Efraim Feinstein. 动态目标异常检测的深度半监督嵌入。2017 年。

+   [365] Estiri 和 Murphy (2018)⟧estiri2018semi Hossein Estiri 和 Shawn Murphy. 临床观察数据中的半监督编码用于异常检测。*bioRxiv*，第 334771 页，2018 年。

+   [366] Jia 等 (2014)Jia, Li, Li 和 Zhang⟧jia2014novel Xiaowei Jia, Kang Li, Xiaoyi Li 和 Aidong Zhang. 一种新颖的半监督深度学习框架用于 EEG 信号的情感状态识别。在 *生物信息学与生物工程 (BIBE)，2014 IEEE 国际会议论文集*，第 30–37 页。IEEE，2014 年。

+   [367] Gu 等 (2018)Gu, Schubert, 和 Tresp⟧gu2018semi Jindong Gu, Matthias Schubert 和 Volker Tresp. 使用生成对抗框架的半监督异常检测。2018 年。

+   [368] Akcay 等 (2018)Akcay, Atapour-Abarghouei, 和 Breckon⟧akcay2018ganomaly Samet Akcay, Amir Atapour-Abarghouei 和 Toby P Breckon. Ganomaly：通过对抗训练的半监督异常检测。*arXiv 预印本 arXiv:1805.06725*，2018 年。

+   [369] Sabokrou 等 (2018)Sabokrou, Khalooei, Fathy, 和 Adeli⟧sabokrou2018adversarial Mohammad Sabokrou, Mohammad Khalooei, Mahmood Fathy 和 Ehsan Adeli. 对抗性学习的一类分类器用于新奇检测。在 *IEEE 计算机视觉与模式识别会议论文集*，第 3379–3388 页，2018 年。

+   [370] Dimokranitou (2017)⟧dimokranitou2017adversarial Asimenia Dimokranitou. *用于图像中异常事件检测的对抗自编码器*。博士论文，2017 年。

+   [371] Altman (1992)⟧altman1992introduction Naomi S Altman. 核方法与最近邻非参数回归的介绍。*美国统计学家*，46(3)：175–185，1992 年。

+   [372] Ho (1995)⟧ho1995random Tin Kam Ho. 随机决策森林。在 *文档分析与识别，1995 年第三届国际会议论文集*，第 1 卷，第 278–282 页。IEEE，1995 年。

+   [373] Kira 和 Rendell (1992)⟧kira1992feature Kenji Kira 和 Larry A Rendell. 特征选择问题：传统方法与新算法。在 *Aaai*，第 2 卷，第 129–134 页，1992 年。

+   [374] Shi 等 (2017)Shi, Yuan 和 Nick⟧shi2017semi Ningxin Shi, Xiaohong Yuan 和 William Nick. 用于入侵检测网络的半监督随机森林，2017 年。

+   [375] Zhu et al.(2018)Zhu, Yang, Wang, and Yuan⟧zhu2018hybrid Bing Zhu, Wenchuan Yang, Huaxuan Wang 和 Yuan Yuan. 一种用于消费者信用评分的混合深度学习模型。在*2018 年国际人工智能与大数据大会 (ICAIBD)*，第 205–208 页。IEEE，2018。

+   [376] Racah et al.(2017)Racah, Beckham, Maharaj, Kahou, Prabhat, and Pal⟧racah2017extremeweather Evan Racah, Christopher Beckham, Tegan Maharaj, Samira Ebrahimi Kahou, Mr Prabhat 和 Chris Pal. Extremeweather：一个用于半监督检测、定位和理解极端天气事件的大规模气候数据集。在*神经信息处理系统进展*，第 3402–3413 页，2017。

+   [377] Wu 和 Prasad(2018)⟧wu2018semi Hao Wu 和 Saurabh Prasad. 使用伪标签的半监督深度学习用于高光谱图像分类。*IEEE Transactions on Image Processing*, 27(3):1259–1270, 2018。

+   [378] Kliger 和 Fleishman(2018)⟧kliger2018novelty Mark Kliger 和 Shachar Fleishman. 使用 GAN 的新奇检测。*arXiv 预印本 arXiv:1802.10560*，2018。

+   [379] Lu(2009)⟧lu2009fundamental Tyler Tian Lu. 半监督学习的基本限制。硕士论文，滑铁卢大学，2009。

+   [380] Ruchansky et al.(2017)Ruchansky, Seo, and Liu⟧ruchansky2017csi Natali Ruchansky, Sungyong Seo 和 Yan Liu. CSI：用于虚假新闻检测的混合深度模型。在*2017 年 ACM 信息与知识管理会议论文集*，第 797–806 页。ACM，2017。

+   [381] Urbanowicz et al.(2018)Urbanowicz, Meeker, La Cava, Olson, and Moore⟧urbanowicz2018relief Ryan J Urbanowicz, Melissa Meeker, William La Cava, Randal S Olson 和 Jason H Moore. 基于 Relief 的特征选择：介绍与综述。*Journal of Biomedical Informatics*，2018。

+   [382] Erfani et al.(2016b)Erfani, Baktashmotlagh, Moshtaghi, Nguyen, Leckie, Bailey, and Kotagiri⟧erfani2016robust Sarah Erfani, Mahsa Baktashmotlagh, Masoud Moshtaghi, Vinh Nguyen, Christopher Leckie, James Bailey 和 Ramamohanarao Kotagiri. 通过强制分布不变性进行鲁棒的领域泛化。在*第二十五届国际人工智能联合会议论文集*，第 1455–1461 页。AAAI Press/国际人工智能联合会议，2016b。

+   [383] Wu et al.(2015b)Wu, Wang, Wang, and Yu⟧wu2015harvesting Ruobing Wu, Baoyuan Wang, Wenping Wang 和 Yizhou Yu. 使用深度 CNN 特征进行场景分类的判别性元对象收获。在*IEEE 国际计算机视觉大会论文集*，第 1287–1295 页，2015b。

+   [384] Saxe et al.(2011)Saxe, Koh, Chen, Bhand, Suresh, and Ng⟧saxe2011random Andrew M Saxe, Pang Wei Koh, Zhenghao Chen, Maneesh Bhand, Bipin Suresh 和 Andrew Y Ng. 关于随机权重和无监督特征学习。在*ICML*，第 1089–1096 页，2011。

+   [385] Baldi（2012 年）⟧baldi2012autoencoders Pierre Baldi。自编码器、无监督学习与深度架构。见于*ICML 无监督与迁移学习研讨会论文集*，第 37–49 页，2012 年。

+   [386] Chandola 等人（2008 年）Chandola, Mithal, 和 Kumar⟧chandola2008comparative Varun Chandola, Varun Mithal, 和 Vipin Kumar。对序列数据异常检测技术的比较评估。见于*数据挖掘, 2008\. ICDM’08\. 第八届 IEEE 国际会议*，第 743–748 页。IEEE，2008 年。

+   [387] Dasigi 和 Hovy（2014 年）⟧dasigi2014modeling Pradeep Dasigi 和 Eduard Hovy。使用神经网络对新闻事件进行建模以进行异常检测。见于*COLING 2014 第 25 届计算语言学国际会议：技术论文集*，第 1414–1422 页，2014 年。

+   [388] Abati 等人（2018 年）Abati, Porrello, Calderara, 和 Cucchiara⟧abati2018and Davide Abati, Angelo Porrello, Simone Calderara, 和 Rita Cucchiara。And: 自回归新颖性检测器。*arXiv 预印本 arXiv:1807.01653*，2018 年。

+   [389] Zong 等人（2018 年）Zong, Song, Min, Cheng, Lumezanu, Cho, 和 Chen⟧zong2018deep Bo Zong, Qi Song, Martin Renqiang Min, Wei Cheng, Cristian Lumezanu, Daeki Cho, 和 Haifeng Chen。深度自编码高斯混合模型用于无监督异常检测。2018 年。

+   [390] Tagawa 等人（2015 年）Tagawa, Tadokoro, 和 Yairi⟧tagawa2015structured Takaaki Tagawa, Yukihiro Tadokoro, 和 Takehisa Yairi。用于故障检测和分析的结构化去噪自编码器。见于*亚洲机器学习会议*，第 96–111 页，2015 年。

+   [391] Xu 等人（2015 年）Xu, Ricci, Yan, Song, 和 Sebe⟧xu2015learning Dan Xu, Elisa Ricci, Yan Yan, Jingkuan Song, 和 Nicu Sebe。学习外观和动作的深度表示用于异常事件检测。*arXiv 预印本 arXiv:1510.01553*，2015 年。

+   [392] Hawkins 等人（2002 年）Hawkins, He, Williams, 和 Baxter⟧hawkins2002outlier Simon Hawkins, Hongxing He, Graham Williams, 和 Rohan Baxter。使用复制神经网络进行异常检测。见于*国际数据仓库与知识发现会议*，第 170–180 页。Springer，2002 年。

+   [393] Zhao 等人（2015 年）Zhao, Guo, Wu, Ning, 和 Yan⟧zhao2015robust Dan Zhao, Baolong Guo, Jinfu Wu, Weikang Ning, 和 Yunyi Yan。通过改进的自编码器从非高斯噪声图像中学习鲁棒特征。见于*成像系统与技术（IST），2015 年 IEEE 国际会议*，第 1–5 页。IEEE，2015 年。

+   [394] Qi 等人（2014 年）Qi, Wang, Zheng, 和 Wu⟧qi2014robust Yu Qi, Yueming Wang, Xiaoxiang Zheng, 和 Zhaohui Wu。通过堆叠自编码器与最大互相关准则进行鲁棒特征学习。见于*声学、语音与信号处理（ICASSP），2014 年 IEEE 国际会议*，第 6716–6720 页。IEEE，2014 年。

+   [395] Chalapathy et al. (2017)⟧chalapathy2017robust Raghavendra Chalapathy, Aditya Krishna Menon, 和 Sanjay Chawla。稳健的深度和归纳异常检测。见于*欧洲机器学习与数据库知识发现联合会议*，页码 36–51。Springer，2017 年。

+   [396] Zhai et al. (2016)⟧zhai2016deep Shuangfei Zhai, Yu Cheng, Weining Lu, 和 Zhongfei Zhang。用于异常检测的深度结构能量模型。*arXiv 预印本 arXiv:1605.07717*，2016 年。

+   [397] Lyudchik (2016)⟧lyudchik2016outlier Olga Lyudchik。使用自编码器进行异常检测。技术报告，2016 年。

+   [398] Lu et al. (2017)⟧lu2017unsupervised Weining Lu, Yu Cheng, Cao Xiao, Shiyu Chang, Shuai Huang, Bin Liang, 和 Thomas Huang。使用深度架构的无监督序列异常检测。*IEEE 图像处理汇刊*，26(9):4321–4330，2017 年。

+   [399] Mehrotra et al. (2017)⟧mehrotra2017deep Rishabh Mehrotra, Ahmed Hassan Awadallah, Milad Shokouhi, Emine Yilmaz, Imed Zitouni, Ahmed El Kholy, 和 Madian Khabsa。用于任务满意度预测的深度序列模型。见于*2017 年 ACM 信息与知识管理大会论文集*，页码 737–746。ACM，2017 年。

+   [400] Meng et al. (2018)⟧meng2018relational Qinxue Meng, Daniel Catchpoole, David Skillicorn, 和 Paul J Kennedy。用于特征提取的关系自编码器。*arXiv 预印本 arXiv:1802.03145*，2018 年。

+   [401] Parchami et al. (2017)⟧parchami2017using Mostafa Parchami, Saman Bashbaghi, Eric Granger, 和 Saif Sayed。使用深度自编码器学习稳健的领域不变表示，用于静态到视频的面部识别。见于*2017 年第 14 届 IEEE 国际视频与信号监控会议*，页码 1–6。IEEE，2017 年。

+   [402] Lawson et al. (2017)⟧lawson2017finding Wallace E Lawson, Esube Bekele, 和 Keith Sullivan。使用生成对抗网络寻找巡逻机器人的异常。见于*CVPR 研讨会*，页码 484–485，2017 年。

+   [403] Leveau and Joly (2017)⟧leveau2017adversarial Valentin Leveau 和 Alexis Joly。用于新颖性检测的对抗自编码器。2017 年。

+   [404] An and Cho (2015)⟧an2015variational Jinwon An 和 Sungzoon Cho。基于变分自编码器的异常检测使用重建概率。*IE 特别讲座*，2:1–18，2015 年。

+   [405] Suh et al. (2016)⟧suh2016echo Suwon Suh, Daniel H Chae, Hyon-Goo Kang, 和 Seungjin Choi。用于异常检测的回声状态条件变分自编码器。见于*2016 年国际联合神经网络会议*，页码 1015–1022。IEEE，2016 年。

+   [406] Mishra 等人（2017）Mishra, Reddy, Mittal 和 Murthy⟧mishra2017generative 阿什什·米什拉、M·雷迪、阿努拉格·米特尔和赫玛·A·穆尔提。使用条件变分自编码器的生成模型进行零样本学习。*arXiv 预印本 arXiv:1709.00663*，2017 年。

+   [407] Goldstein 和 Uchida（2016）⟧goldstein2016comparative 马库斯·戈尔德斯坦和内田精一。对多变量数据的无监督异常检测算法的比较评估。*PloS one*，11(4):e0152173，2016 年。

+   [408] Andrews 等人（2016b）Andrews, Tanay, Morton 和 Griffin⟧andrews2016transfer Jerone TA Andrews、托马斯·塔奈、爱德华·J·摩顿和刘易斯·D·格里芬。用于异常检测的迁移表示学习。ICML，2016b 年。

+   [409] Vercruyssen 等人（2017）Vercruyssen, Meert 和 Davis⟧vercruyssen2017transfer 文森特·维尔克鲁伊森、瓦内斯·梅尔特和杰西·戴维斯。时间序列异常检测的迁移学习。*IAL ECML PKDD 2017*，第 27 页，2017 年。

+   [410] Li 等人（2012）Li, Du 和 Zhang⟧li2012detecting 康·李、南·杜和艾东·张。通过转导迁移学习检测心电图异常。载于*ACM 生物信息学、计算生物学与生物医学会议论文集*，第 210–217 页，ACM，2012 年。

+   [411] Almajai 等人（2012）Almajai, Yan, de Campos, Khan, Christmas, Windridge 和 Kittler⟧almajai2012anomaly 易卜拉欣·阿尔马贾伊、费·燕、特奥菲洛·德·坎波斯、阿夫塔布·汗、威廉·圣诞、大卫·温德里奇和约瑟夫·基特勒。自动体育视频注释中的异常检测和知识迁移。载于*稀有视听线索的检测与识别*，第 109–117 页，Springer，2012 年。

+   [412] Kumar 和 Vaidehi（2017）⟧kumar2017transfer PM·阿什克·库马尔和 V·瓦伊德希。使用神经模糊方法的交通视频迁移学习框架。*Sādhanā*，42(9):1431–1442，2017 年。

+   [413] Liang 等人（2018）Liang, Yang, Chen, Xiao 和 Lan⟧liang2018transfer 彭·梁、海东·杨、文思·陈、思源·肖和赵泽·兰。通过深度神经网络进行铝挤压电力消耗异常检测的迁移学习。*国际计算机集成制造杂志*，31(4-5):396–405，2018 年。

+   [414] Romera-Paredes 和 Torr（2015）⟧romera2015embarrassingly 伯纳迪诺·罗梅拉-帕雷德斯和菲利普·托尔。一个令人尴尬的简单零样本学习方法。载于*国际机器学习会议*，第 2152–2161 页，2015 年。

+   [415] Socher 等人（2013）Socher, Ganjoo, Manning 和 Ng⟧socher2013zero 理查德·索彻、米林德·甘久、克里斯托弗·D·曼宁和安德鲁·吴。通过跨模态迁移进行零样本学习。载于*神经信息处理系统进展*，第 935–943 页，2013 年。

+   [416] Xian 等人（2017）Xian, Schiele 和 Akata⟧xian2017zero 永钦·谢安、贝恩特·施皮尔和泽内普·阿卡塔。零样本学习——好、坏和丑。*arXiv 预印本 arXiv:1703.04394*，2017 年。

+   [417] Liu et al.(2017) Liu, Liu, Ma, Huang, 和 Dong⟧liu2017generalized Kun Liu, Wu Liu, Huadong Ma, Wenbing Huang, 和 Xiongxiong Dong. 基于网页规模视频数据的广义零样本学习用于动作识别。*arXiv 预印本 arXiv:1710.07455*，2017 年。

+   [418] Rivero et al.(2017) Rivero, Ribeiro, Chen, 和 Leite⟧rivero2017grassmannian Jorge Rivero, Bernardete Ribeiro, Ning Chen, 和 Fátima Silva Leite. 一种草曼流形方法用于网络入侵检测中的零样本学习。见于*国际神经信息处理会议*，第 565–575 页。Springer，2017 年。

+   [419] Chen et al.(2017) Chen, Sathe, Aggarwal, 和 Turaga⟧chen2017outlier Jinghui Chen, Saket Sathe, Charu Aggarwal, 和 Deepak Turaga. 基于自编码器集成的异常检测。见于*2017 年 SIAM 国际数据挖掘会议论文集*，第 90–98 页。SIAM，2017 年。

+   [420] Ester et al.(1996) Ester, Kriegel, Sander, Xu, 等⟧ester1996density Martin Ester, Hans-Peter Kriegel, Jörg Sander, Xiaowei Xu, 等. 一种基于密度的算法用于发现大规模空间数据库中的聚类。见于*Kdd*，第 96 卷，第 226–231 页，1996 年。

+   [421] Sreekanth et al.(2010) Sreekanth, Vedaldi, Zisserman, 和 Jawahar⟧sreekanth2010generalized V Sreekanth, Andrea Vedaldi, Andrew Zisserman, 和 C Jawahar. 高效检测的广义 rbf 特征映射。2010 年。

+   [422] Mikolov et al.(2013) Mikolov, Chen, Corrado, 和 Dean⟧mikolov2013efficient Tomas Mikolov, Kai Chen, Greg Corrado, 和 Jeffrey Dean. 高效的词向量空间估计。*arXiv 预印本 arXiv:1301.3781*，2013 年。

+   [423] Yuan et al.(2017) Yuan, Li, Yao, 和 Zhang⟧yuan2017deep Guiqin Yuan, Bo Li, Yiyang Yao, 和 Simin Zhang. 一种深度学习驱动的子空间谱集成聚类方法用于网络异常检测。见于*神经网络（IJCNN），2017 年国际联合会议*，第 3896–3903 页。IEEE，2017 年。

+   [424] de La Bourdonnaye et al.(2017) de La Bourdonnaye, Teulière, Chateau, 和 Triesch⟧de2017learning François de La Bourdonnaye, Céline Teulière, Thierry Chateau, 和 Jochen Triesch. 使用深度强化学习进行双眼注视的学习。见于*神经网络（IJCNN），2017 年国际联合会议*，第 760–767 页。IEEE，2017 年。

+   [425] Chengqiang Huang(2016)⟧rlanomaly Yuan Zuo Ke Pei Geyong Huang, Yulei Wu. 通过强化学习实现经验异常检测器。*第三十二届 AAAI 人工智能大会（AAAI-18）*，2016 年。

+   [426] Kanarachos et al.(2015) Kanarachos, Mathew, Chroneos, 和 Fitzpatrick⟧kanarachos2015anomaly S Kanarachos, J Mathew, A Chroneos, 和 M Fitzpatrick. 使用小波、神经网络和希尔伯特变换组合进行时间序列数据中的异常检测。见于*IISA*，第 1–6 页，2015 年。

+   [427] Schmidhuber(2015)⟧schmidhuber2015deep Jürgen Schmidhuber. 神经网络中的深度学习：概述。*神经网络*，61:85–117，2015 年。

+   [428] Bengio et al.(2009)⟧bengio2009learning Yoshua Bengio 等人。为人工智能学习深度架构。*机器学习的基础与趋势®*，2(1):1–127，2009 年。

+   [429] Werbos(1990)⟧werbos1990backpropagation Paul J Werbos. 通过时间的反向传播：它的作用及如何实现。*IEEE 会议录*，78(10):1550–1560，1990 年。

+   [430] Zhang et al.(2018f)Zhang, Zheng, and Yu⟧zhang2018detecting Huichu Zhang, Yu Zheng, and Yong Yu. 使用多个时空数据源检测城市异常。*ACM 互动、移动、可穿戴和普适技术会议录*，2(1):54，2018f。

+   [431] Lee et al.(2018)Lee, Kim, and Ro⟧lee2018stan Sangmin Lee, Hak Gu Kim, and Yong Man Ro. Stan: 时空对抗网络用于异常事件检测。*arXiv 预印本 arXiv:1804.08381*，2018 年。

+   [432] SZEKÉR(2014)⟧szeker2014spatio MÁTÉ SZEKÉR. 流数据轨迹中的时空异常检测，2014 年。

+   [433] Nie et al.(2018)Nie, Li, and Kong⟧nie2018spatio Laisen Nie, Yongkang Li, and Xiangjie Kong. 基于卷积神经网络的车载自组网时空网络流量估计与异常检测。*IEEE Access*，6:40168–40176，2018 年。

+   [434] Dereszynski and Dietterich(2011)⟧dereszynski2011spatiotemporal Ethan W Dereszynski and Thomas G Dietterich. 动态环境监测活动中的数据异常检测的时空模型。*ACM 传感器网络交易（TOSN）*，8(1):3，2011 年。

+   [435] Poon and Domingos(2011)⟧poon2011sum Hoifung Poon and Pedro Domingos. 和积网络：一种新的深度架构。载于*2011 年 IEEE 国际计算机视觉会议研讨会*，页码 689–690。IEEE，2011 年。

+   [436] Rezaeinia et al.(2017)Rezaeinia, Ghodsi, and Rahmani⟧rezaeinia2017improving Seyed Mahdi Rezaeinia, Ali Ghodsi, and Rouhollah Rahmani. 改进预训练词嵌入在情感分析中的准确性。*arXiv 预印本 arXiv:1711.08609*，2017 年。

+   [437] Naili et al.(2017)Naili, Chaibi, and Ghezala⟧naili2017comparative Marwa Naili, Anja Habacha Chaibi, and Henda Hajjami Ben Ghezala. 话题分割中的词嵌入方法比较研究。*Procedia 计算机科学*，112:340–349，2017 年。

+   [438] Altszyler et al.(2016)Altszyler, Sigman, Ribeiro, and Slezak⟧altszyler2016comparative Edgar Altszyler, Mariano Sigman, Sidarta Ribeiro, and Diego Fernández Slezak. 小语料库中 lsa 与 word2vec 嵌入的比较研究：以梦境数据库为例。*arXiv 预印本 arXiv:1610.01520*，2016 年。

+   [439] Schnabel et al.(2015)Schnabel, Labutov, Mimno, and Joachims⟧schnabel2015evaluation Tobias Schnabel, Igor Labutov, David Mimno, and Thorsten Joachims. 无监督词嵌入的评估方法。载于*2015 年自然语言处理实证方法会议录*，页码 298–307，2015 年。

+   [440] Bertero 等（2017）Bertero, Roy, Sauvanaud 和 Trédan⟧bertero2017experience Christophe Bertero, Matthieu Roy, Carla Sauvanaud 和 Gilles Trédan. 经验报告：使用自然语言处理的日志挖掘及其在异常检测中的应用。见于*软件可靠性工程（ISSRE），2017 IEEE 第 28 届国际研讨会*，第 351–360 页。IEEE，2017。

+   [441] Bakarov 等（2018）Bakarov, Yadrintsev 和 Sochenkov⟧bakarov2018anomaly Amir Bakarov, Vasiliy Yadrintsev 和 Ilya Sochenkov. 短文本异常检测：识别你的聊天机器人是否应该从目标导向对话转向闲聊。见于*数字化转型与全球社会国际会议*，第 289–298 页。Springer，2018。

+   [442] Bamler 和 Mandt（2017）⟧bamler2017dynamic Robert Bamler 和 Stephan Mandt. 动态词嵌入。*arXiv 预印本 arXiv:1702.08359*，2017。

+   [443] Kingma 和 Welling（2013）⟧kingma2013auto Diederik P Kingma 和 Max Welling. 自编码变分贝叶斯。*arXiv 预印本 arXiv:1312.6114*，2013。

+   [444] Goodfellow 等（2014a）Goodfellow, Pouget-Abadie, Mirza, Xu, Warde-Farley, Ozair, Courville 和 Bengio⟧NIPS2014_5423 Ian Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville 和 Yoshua Bengio. 生成对抗网络。见于 Z. Ghahramani, M. Welling, C. Cortes, N. D. Lawrence 和 K. Q. Weinberger 编辑的*神经信息处理系统进展 27*，第 2672–2680 页。Curran Associates, Inc.，2014a。网址 [`papers.nips.cc/paper/5423-generative-adversarial-nets.pdf`](http://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf)。

+   [445] Goodfellow 等（2014b）Goodfellow, Pouget-Abadie, Mirza, Xu, Warde-Farley, Ozair, Courville 和 Bengio⟧goodfellow2014generative Ian Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville 和 Yoshua Bengio. 生成对抗网络。见于*神经信息处理系统进展*，第 2672–2680 页，2014b。

+   [446] Makhzani 等（2015）Makhzani, Shlens, Jaitly, Goodfellow 和 Frey⟧makhzani2015adversarial Alireza Makhzani, Jonathon Shlens, Navdeep Jaitly, Ian Goodfellow 和 Brendan Frey. 对抗自编码器。*arXiv 预印本 arXiv:1511.05644*，2015。

+   [447] Deecke 等（2018）Deecke, Vandermeulen, Ruff, Mandt 和 Kloft⟧deecke2018anomaly Lucas Deecke, Robert Vandermeulen, Lukas Ruff, Stephan Mandt 和 Marius Kloft. 使用生成对抗网络进行异常检测。2018。

+   [448] Ravanbakhsh 等（2017b）Ravanbakhsh, Nabi, Sangineto, Marcenaro, Regazzoni 和 Sebe⟧ravanbakhsh2017abnormal Mahdyar Ravanbakhsh, Moin Nabi, Enver Sangineto, Lucio Marcenaro, Carlo Regazzoni 和 Nicu Sebe. 利用生成对抗网络进行视频中的异常事件检测。见于*图像处理（ICIP），2017 IEEE 国际会议*，第 1577–1581 页。IEEE，2017b。

+   [449] Eide(2018)⟧eide2018applying 阿克塞尔·威尔赫尔姆·沃尔德·艾德。应用生成对抗网络进行高光谱遥感图像中的异常检测。硕士论文，NTNU，2018。

+   [450] Škvára et al.(2018)Škvára, Pevnỳ, and Šmídl⟧vskvara2018generative 维特·什克瓦拉，托马斯·佩夫尼，和瓦茨拉夫·什米德尔。生成深度模型在新颖性检测中的表现是否真的更好？*arXiv 预印本 arXiv:1807.05027*，2018。

+   [451] Krizhevsky et al.(2012)Krizhevsky, Sutskever, and Hinton⟧krizhevsky2012imagenet 亚历克斯·克里日夫斯基，伊利亚·苏茨克弗，和杰弗里·E·辛顿。使用深度卷积神经网络进行 Imagenet 分类。收录于*神经信息处理系统进展*，第 1097–1105 页，2012 年。

+   [452] Kim(2014)⟧kim2014convolutional 尹金。用于句子分类的卷积神经网络。*arXiv 预印本 arXiv:1408.5882*，2014。

+   [453] Williams(1989)⟧williams1989complexity 罗纳德·J·威廉姆斯。递归神经网络精确梯度计算算法的复杂性。技术报告，技术报告 NU-CCS-89-27，波士顿：东北大学，1989。

+   [454] Cho et al.(2014)Cho, Van Merriënboer, Gulcehre, Bahdanau, Bougares, Schwenk, and Bengio⟧cho2014learning 金贤熙，巴特·范·梅里恩博尔，恰格拉尔·古尔切赫，兹米特里·巴赫丹诺，费提·布加雷斯，霍尔格·施温克，和约书亚·本吉奥。使用 RNN 编码器-解码器学习短语表示以进行统计机器翻译。*arXiv 预印本 arXiv:1406.1078*，2014。

+   [455] Pearson(1901)⟧pearson1901liii 卡尔·皮尔逊。Liii. 关于空间中点系的最佳拟合线和面。*伦敦、爱丁堡和都柏林哲学杂志及科学期刊*，2(11):559–572, 1901。

+   [456] Liou et al.(2008)Liou, Huang, and Yang⟧liou2008modeling 李承元，黄昭琪，和杨文奇。使用 Elman 网络建模词汇感知。*神经计算*，71(16-18):3150–3157，2008。

+   [457] Liou et al.(2014)Liou, Cheng, Liou, and Liou⟧liou2014autoencoder 李承元，魏晨，刘俊伟，和刘道然。用于词汇的自编码器。*神经计算*，139:84–96，2014。

+   [458] Williams et al.(2002)Williams, Baxter, He, Hawkins, and Gu⟧williams2002comparative 格雷厄姆·威廉姆斯，罗汉·巴克斯特，洪兴·何，西蒙·霍金斯，和李芳·顾。数据挖掘中用于异常检测的 rnn 的比较研究。收录于*数据挖掘，2002\. ICDM 2003\. 2002 年 IEEE 国际会议*，第 709–712 页。IEEE，2002。

+   [459] Zhou and Paffenroth(2017)⟧zhou2017anomaly 钟冲和兰迪·C·帕芬罗特。使用稳健深度自编码器进行异常检测。收录于*第 23 届 ACM SIGKDD 国际知识发现与数据挖掘会议论文集*，第 665–674 页。ACM，2017。

+   [460] Vincent 等人（2010）Vincent, Larochelle, Lajoie, Bengio, 和 Manzagol。堆叠去噪自编码器：在深度网络中使用局部去噪标准学习有用表示。*机器学习研究杂志*，11（12 月）：3371–3408，2010 年。

+   [461] Haque 等人（2018）Haque, Yousuf, 和 Rana。图像去噪和恢复使用 CNN-LSTM 编码器解码器及直接注意机制。*arXiv 预印本 arXiv:1801.05141*，2018 年。

+   [462] Masci 等人（2011）Masci, Meier, Cireşan, 和 Schmidhuber。用于层次特征提取的堆叠卷积自编码器。发表于*国际人工神经网络会议*，第 52–59 页。施普林格，2011 年。
