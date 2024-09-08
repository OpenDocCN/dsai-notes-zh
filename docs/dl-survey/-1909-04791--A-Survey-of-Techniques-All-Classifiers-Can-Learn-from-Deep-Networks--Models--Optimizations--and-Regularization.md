<!--yml

分类：未分类

日期：2024-09-06 20:04:50

-->

# [1909.04791] 从深度网络中所有分类器可以学习的技术调查：模型、优化和正则化

> 来源：[`ar5iv.labs.arxiv.org/html/1909.04791`](https://ar5iv.labs.arxiv.org/html/1909.04791)

# 从深度网络中所有分类器可以学习的技术调查：模型、优化和正则化

Alireza Ghods

计算机科学系

华盛顿州立大学

普尔曼, WA 99163

alireza.ghods@wsu.edu

&Diane J. Cook

计算机科学系

华盛顿州立大学

普尔曼, WA 99163

djcook@wsu.edu

###### 摘要

深度神经网络为机器学习社区引入了新颖且有用的工具。其他类型的分类器也可以利用这些工具来提升其性能和泛化能力。本文回顾了当前在深度神经网络之外使用的深度学习分类器技术的最新进展。非网络分类器可以利用深度神经网络架构中发现的许多组件。本文回顾了构成深度网络技术核心的特征学习、优化和正则化方法。接着，我们调查了非神经网络学习算法如何创新性地使用这些方法来改善分类。由于仍然存在许多机会和挑战，我们讨论了可以探索的方向，以扩展深度学习在各种分类算法中的应用领域。

*关键词* 深度学习  $\cdot$ 深度神经网络  $\cdot$  $\cdot$ 正则化

## 1 引言

监督学习算法的目标是根据给定的训练数据集，识别输入特征与输出值之间的最佳映射。一个正在引起大量研究和工业关注的监督学习方法是**深度神经网络**（DNN）。DNN 对我们的日常生活产生了深远的影响；它们被应用于搜索引擎 [1] [2]、自动驾驶汽车 [3] [4] [5]、医疗保健系统 [6]，以及智能手机和相机等消费设备 [7]。卷积神经网络（CNN）已成为处理图像的标准 [8] [9] [10]，而递归神经网络（RNN）主导了对文本和语音等序列数据的处理 [11] [12] [13] [14]。DNN 使机器能够自动发现用于检测或分类原始输入所需的表示 [15]。此外，神经网络社区开发了无监督算法以帮助学习未标记的数据。这些无监督方法已经在实际应用中找到了用武之地，例如创建生成对抗网络（GANs）来设计服装 [16]。术语“深度”被用来区分这些网络与只有一个隐藏层的浅层网络；相比之下，DNN 具有多个隐藏层。术语“深度学习”和“深度神经网络”通常是同义的。然而，我们观察到“深度学习”本身具有更广泛的含义，这也可以塑造神经网络算法之外的机器学习领域。

最近深度神经网络的显著进展得益于海量计算能力和标记数据的可用性。然而，这些进展并未解决与 DNN 相关的所有困难。例如，在许多现实场景中，例如分析电力分配数据 [17]，由于数据收集的复杂性和成本，存在大量的注释数据集。而像临床医学诊断的解读这类应用需要学习的模型是可理解的，但由于复杂性，大多数 DNN 仍然难以解释 [18]。DNN 对噪声训练数据可能不够敏感 [19] [20] [21]，同时它们还需要适当的参数初始化以便收敛 [22] [23]。

尽管存在这些不足，但 DNN 在许多数据集上报告的预测准确率高于其他监督学习方法，只要有足够的监督数据和计算资源。深度模型提供了结构上的优势，这可能提高在复杂数据集上的学习质量，正如 Bengio 通过实证研究所示[24]。最近，研究人员设计了混合方法，将独特的 DNN 技术与其他分类器相结合，以解决一些已识别的问题或提升其他分类器。本文综述了这些方法，回顾了将 DNN 技术适应到其他分类器的分类器。

### 1.1 研究目标与大纲

尽管深度神经网络（DNN）研究发展迅速，但本文旨在对深度学习方法进行更广泛的概述。尽管一些研究提供了证据，表明 DNN 模型在处理复杂数据时比经典机器学习算法具有更好的泛化能力[25] [26] [27] [28] [29]，但并没有一种“万灵药”式的方法来进行概念学习[30]。大量比较 DNN 和其他监督学习算法的研究[31] [32] [33] [34] [35]观察到，算法的选择依赖于数据——没有一种理想的算法可以在所有类型的数据上都能做到最佳泛化。因此，我们认识到其他分类器所扮演的独特而重要的角色，旨在研究非网络机器学习算法如何从深度神经网络的进展中受益。许多深度学习综述论文已经出版，提供了关于这一主题的入门介绍[36]，或强调了如目标检测[37]、医疗记录分析[38]、活动识别[39]和自然语言处理[40]等多种应用。在这项综述中，我们不仅关注深度神经网络模型，还关注深度学习如何激发更广泛的分类器。我们专注于将非网络分类器转变为深度学习者的研究突破。此外，我们回顾了诸如随机梯度下降等深度网络技术，这些技术可以被更广泛地使用，并讨论了非网络模型如何受益于受网络启发的深度学习创新。

文献提供的证据表明，与深度网络相比，非网络模型可能在泛化能力上有所改善，具体取决于可用数据的数量和类型。通过调查将非网络分类器转变为深度学习者的方法，这些方法可以成为更强的学习者。为了提供持续研究这一主题的必要性的证据，我们还实现了一组浅层和深层学习者，这些学习者包括网络和非网络分类器，以比较它们的性能。图 1 突出了我们在本次调查中讨论的深度学习组件。该图还总结了我们调查的深度分类器以及我们强调的技术之间的关系。

{forest}

对于树形图：字体=，绘制，半粗，圆角，居中对齐，内边距=1mm，边缘=半粗，-stealth，l sep=0.5cm，s sep=0.2cm，fork sep=1mm，父锚点=south，子锚点=north，边缘路径= [-Stealth[], \forestoptionedge，细] (!u.parent anchor) – +(0,-5pt) -| (.child anchor)\forestoptionedge 标签；，/tikz/>=LaTeX，，[深度学习，[训练方法，树形图=填充=gray!20 [优化，树形图=文件夹，grow’=0 [梯度下降 [DNDF] [mGBDT] [ML-SVM] ] ] [正则化，树形图=文件夹，grow’=0 [特征惩罚 [GRRF] [NLP-SVM] [RRF] [SCAD-SVM] ] [丢弃 [DART] ] ] ] [分类器，树形图=填充=pink!20 [基于网络的，树形图=文件夹，grow’=0 [AE [VAE] ] [CNN] [GAN] [MLP] [SNN] [RNN [LSTM] [GRU] ] ] [基于树的，树形图=文件夹，grow’=0 [ANT] [DF] [DNDF] [eForest] [FSDT] [GAF] [mGBDT] [SDF] [DNDT] ] [基于 SVM 的，树形图=文件夹，grow’=0 [深度 SVM] [DTA-LS-SVM] [ML-SVM] [R2SVM] ] [基于统计的，树形图=文件夹，grow’=0 [DBN] [DGP] [DKF] ] [混合，树形图=文件夹，grow’=0 [CondNN] [DBT] [DCCA] [深度 PCA] [DNDF] [LMM] ] ] ]

图 1：本次调查中涵盖的方法内容图。

## 2 深度神经网络的简要概述

### 2.1 起源

1985 年，Rosenblatt 介绍了感知机 [41]，这是一种在线二分类器，通过权重向量将输入流向输出层。感知机学习使用一种梯度下降形式来调整输入层和输出层之间的权重，以优化损失函数 [42]。几年后，Minsky 证明了单层感知机无法学习非线性函数，包括 XOR 函数 [43]。多层感知机（MLPs，完整的缩写列表见表 4）通过在网络中添加隐藏单元的层，并对每个节点应用替代的可微激活函数，如 sigmoid，来解决非线性问题。然后，随机梯度下降被应用于 MLP，以确定各层之间的权重，从而最小化函数近似误差 [44]。然而，计算能力的不足使得 DNN 研究在几十年内停滞不前，其他分类器逐渐受到欢迎。2006 年，DNN 研究迎来了复兴，受到深度信念网络（DBNs） [45] 引入的推动。

### 2.2 深度神经网络架构

随着深度学习的日益流行，许多 DNN 架构被引入，其中包括神经图灵机 [46] 和胶囊神经网络 [47] 等变体。在本文中，我们总结了 DNN 的一般形式以及不仅出现在 DNN 中的建筑组件，还可以被纳入其他模型。我们首先回顾了已引入的流行 DNN 类型，这些类型在学习中扮演着互补的角色。

### 2.3 监督学习

#### 2.3.1 多层感知器

多层感知器（MLP）是许多深度学习算法的基本组成部分之一。MLP 的目标是通过学习函数 $y=f(X,\theta)$ 将输入 $X$ 映射到类别 $y$，其中 $\theta$ 代表最佳的函数近似。例如，在图 2 中，MLP 使用函数 $f(x)=f^{(3)}(f^{(2)}(f^{(1)}(x)))$ 将输入 $X$ 映射到 $y$，其中 $f^{(1)}$ 是第一层，$f^{(2)}$ 是第二层，$f^{(3)}$ 代表第三层，即输出层。这种链式结构是许多 DNN 架构的常见组件。网络深度等于链的长度，而每一层的宽度表示该层中的节点数量 [48]。

在像 MLP 这样的网络中，连接不是循环的，因此属于一种叫做前馈网络的 DNN 类别。前馈网络中的信息仅沿一个方向流动，从输入层到输出层。图 2 描述了一种特定类型的前馈网络，即完全连接的多层感知器，因为每一层的每个节点都与下一层的所有节点相连。前馈网络和 MLP 的特殊情况最近引起了相当大的关注，我们接下来将进行描述。

<svg   height="179.43" overflow="visible" version="1.1" width="300.08"><g transform="translate(0,179.43) matrix(1 0 0 -1 0 0) translate(39.65,0) translate(0,83.66)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1.8 0.0 0.0 1.8 -9.34 -53.6)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\vdots$</foreignobject></g><g transform="matrix(1.8 0.0 0.0 1.8 69.4 -16.69)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\vdots$</foreignobject></g><g transform="matrix(1.8 0.0 0.0 1.8 148.14 -16.69)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\vdots$</foreignobject></g><g transform="matrix(1.8 0.0 0.0 1.8 226.88 -18.17)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\vdots$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -30.64 51.68)" fill="#000000" stroke="#000000"><foreignobject width="11.78" height="8.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -30.64 22.15)" fill="#000000" stroke="#000000"><foreignobject width="11.78" height="8.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{2}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -30.64 -7.38)" fill="#000000" stroke="#000000"><foreignobject width="11.78" height="8.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{3}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -32.1 -67.26)" fill="#000000" stroke="#000000"><foreignobject width="14.71" height="7.63" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{m}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 70.49 39.65)" fill="#000000" stroke="#000000"><foreignobject width="16.5" height="11.95" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$H_{1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 70.29 -36.93)" fill="#000000" stroke="#000000"><foreignobject width="16.9" height="12.15" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$H_{k}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 149.23 39.65)" fill="#000000" stroke="#000000"><foreignobject width="16.5" height="11.95" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$H_{1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 149.35 -35.56)" fill="#000000" stroke="#000000"><foreignobject width="16.26" height="13.52" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$H_{j}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 238.95 29.69)" fill="#000000" stroke="#000000"><foreignobject width="11.15" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 238.56 -29.36)" fill="#000000" stroke="#000000"><foreignobject width="11.93" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{n}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -16.72 63.94)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 21.06)"><g transform="matrix(1 0 0 1 0 14.91)"><g transform="matrix(1 0 0 -1 0 0)"><g  transform="matrix(1 0 0 -1 0 8.835)"><g  transform="matrix(1 0 0 1 0 12.23)"><g transform="matrix(1 0 0 -1 0 0)"><text transform="matrix(1 0 0 -1 0 0)">输入</text></g></g></g></g></g><g transform="matrix(1 0 0 1 0 24.52)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 2.29 0)"><text transform="matrix(1 0 0 -1 0 0)">层</text></g></g></g></g><g transform="matrix(1.0 0.0 0.0 1.0 57.02 63.94)" fill="#000000" stroke="#000000"><g  transform="matrix(1 0 0 -1 0 18.53)"><g  transform="matrix(1 0 0 1 0 12.38)"><g transform="matrix(1 0 0 -1 0 0)"><g  transform="matrix(1 0 0 -1 0 7.575)"><g transform="matrix(1 0 0 1 0 12.38)"><g transform="matrix(1 0 0 -1 0 0)"><text transform="matrix(1 0 0 -1 0 0)">隐藏</text></g></g></g></g></g><g transform="matrix(1 0 0 1 0 21.99)"><g class="ltx_tikzmatrix_col ltx_nopad_l ltx_nopad_r" transform="matrix(1 0 0 -1 7.28 0)"><text transform="matrix(1 0 0 -1 0 0)">层</text></g></g></g></g><g transform="matrix(1.0 0.0 0.0 1.0 135.76 63.94)" fill="#000000" stroke="#000000"><g  transform="matrix(1 0 0 -1 0 18.53)"><g  transform="matrix(1 0 0 1 0 12.38)"><g transform="matrix(1 0 0 -1 0 0)"><g  transform="matrix(1 0 0 -1 0 7.575)"><g transform="matrix(1 0 0 1 0 12.38)"><g transform="matrix(1 0 0 -1 0 0)"><text transform="matrix(1 0 0 -1 0 0)">隐藏</text></g></g></g></g></g><g transform="matrix(1 0 0 1 0 21.99)"><g class="

图 2：具有$j$个节点的第一隐藏层和具有$k$个节点的第二层的三层 MLP 示意图。

#### 2.3.2 深度卷积神经网络

卷积神经网络（CNN）[49] 是一种专门用于处理可以离散呈现的数据的前馈深度神经网络（DNN）。可以从 CNN 中受益的数据示例包括可以作为离散规律时间间隔样本呈现的时间序列数据以及作为离散位置的二维像素样本呈现的图像数据。大多数 CNN 涉及三个阶段：卷积操作；一个激活函数，如修正线性激活（ReLU）函数[50]；以及一个池化函数，如最大池化[51]。卷积操作是一个加权平均或平滑估计的窗口输入。卷积操作的一个优势是通过学习一个小内核来忽略不重要的特征，从而使网络中节点之间的连接变得更加稀疏。卷积的另一个好处是参数共享。CNN 假设一个为某一输入位置学习的内核可以在每个位置上使用，与每个连接部署一个权重矩阵的单独元素的多层感知器（MLP）相对。频繁应用卷积操作通常会提高网络的学习能力。

池化函数通过统计汇总替换特定附近节点的输出。例如，最大池化函数返回矩形邻域中的最大值。添加池化层的动机是，统计下采样特征数量使表示在小的输入平移下大致不变，通过保持基本特征。学习者的最终输出通过卷积层和最大池化层后出现的全连接（FC）层生成（参见图 3 以获取过程示意）。

<svg height="177.15" overflow="visible" version="1.1" width="360.61"><g transform="translate(0,177.15) matrix(1 0 0 -1 0 0) translate(13.89,0) translate(0,49.2)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1.0 0.0 0.0 1.0 -9.27 -44.59)" fill="#000000" stroke="#000000"><foreignobject width="50.04" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">| 输入 |

| 层 | </foreignobject></g>  <g transform="matrix(1.0 0.0 0.0 1.0 28.33 -44.59)" fill="#000000" stroke="#000000"><foreignobject width="100.82" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible"> | 卷积 |
| --- | --- | --- |
| 层 + ReLU | </foreignobject></g>  <g transform="matrix(1.0 0.0 0.0 1.0 130.33 73.52)" fill="#000000" stroke="#000000"><foreignobject width="93.67" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible"> | 最大池化 |
| 层 | </foreignobject></g>  <g transform="matrix(1.0 0.0 0.0 1.0 166.13 -44.59)" fill="#000000" stroke="#000000"><foreignobject width="100.82" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible"> | 卷积 |
| 层 + ReLU | </foreignobject></g>  <g transform="matrix(1.0 0.0 0.0 1.0 248.44 73.52)" fill="#000000" stroke="#000000"><foreignobject width="93.67" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible"> | 最大池化 |
| 层 | </foreignobject></g>  <g transform="matrix(1.0 0.0 0.0 1.0 252.86 -44.59)" fill="#000000" stroke="#000000"><foreignobject width="45.47" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible"> | 全连接 |

| 层 |</foreignobject></g></g></svg>

图 3：一个三层卷积神经网络（CNN）的示意图，其中包括六个卷积滤波器，后跟六个最大池化滤波器作为第一层，第二层包括八个卷积滤波器，后跟七个最大池化滤波器。最后一层是一个全连接层（FC）。

#### 2.3.3 循环神经网络

循环神经网络（RNN）是一种序列模型，可以捕捉序列中各项之间的关系。与传统神经网络不同，传统神经网络中的所有输入彼此独立，而 RNN 包含一个或多个反馈回路的人工神经元。反馈回路是时间或序列上的递归循环，如图 4 所示。一个已知的 RNN 问题是梯度爆炸或梯度消失。对于长数据序列，梯度可能变得越来越小或越来越大，从而阻碍学习。为了解决这个问题，Hochreiter 等人 [52] 提出了长短期记忆（LSTM）模型，而 Cho 等人 [53] 提出了门控循环单元（GRU）模型。这两种网络都允许梯度在网络中不变地流动，从而防止梯度爆炸或梯度消失。

<svg height="157.48" overflow="visible" version="1.1" width="349.36"><g transform="translate(0,157.48) matrix(1 0 0 -1 0 0) translate(14.76,0) translate(0,78.74)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1.0 0.0 0.0 1.0 -6.27 -63.78)" fill="#000000" stroke="#000000"><foreignobject width="12.55" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$X$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -3.99 -4.8)" fill="#000000" stroke="#000000"><foreignobject width="7.97" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$h$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -5.55 54.33)" fill="#000000" stroke="#000000"><foreignobject width="11.11" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$Y$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 46.56 -4.8)" fill="#000000" stroke="#000000"><foreignobject width="40.74" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">展开</foreignobject></g><g transform="matrix(1.2 0.0 0.0 1.2 107.95 -1.78)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\cdots$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 160.71 -60.79)" fill="#000000" stroke="#000000"><foreignobject width="17.16" height="8.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{t-1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 160.68 -3.56)" fill="#000000" stroke="#000000"><foreignobject width="17.23" height="12.11" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$h_{t-1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 161.02 57.42)" fill="#000000" stroke="#000000"><foreignobject width="16.54" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{t-1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 215.12 -60.84)" fill="#000000" stroke="#000000"><foreignobject width="10.71" height="8.34" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{t}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 215.09 -3.61)" fill="#000000" stroke="#000000"><foreignobject width="10.77" height="11.99" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$h_{t}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 215.43 57.42)" fill="#000000" stroke="#000000"><foreignobject width="10.08" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{t}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 261.35 -60.46)" fill="#000000" stroke="#000000"><foreignobject width="20.61" height="9.1" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{t+1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 261.32 -3.23)" fill="#000000" stroke="#000000"><foreignobject width="20.67" height="12.75" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$h_{t+1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 261.66 57.65)" fill="#000000" stroke="#000000"><foreignobject width="19.98" height="9.1" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{t+1}$</foreignobject></g><g transform="matrix(1.2 0.0 0.0 1.2 316.61 -1.78)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\cdots$</foreignobject></g></g></svg>

图 4：一个简单的 RNN 及其在时间$t$上的展开结构的示意图。

#### 2.3.4 Siamese 神经网络

在一些设置中，训练样本的数量有限，例如在面部识别场景中，每个人只有一张图片。在每个类别的样本数量有限时，深度神经网络（DNN）在模型泛化方面会遇到困难。解决这个问题的一种策略是学习相似度函数。该函数计算两个样本之间的差异程度，而不是学习每个类别。例如，设$x_{1}$代表一张面部图像，$x_{2}$代表另一张。如果$d(x_{1},x_{2})\leq\tau$，我们可以得出这些图像属于同一个人，而$d(x_{1},x_{2})>\tau$则意味着他们是不同的人。Siamese 神经网络（SNN）[54]基于这一思想，通过在两个具有共享参数的 DNN 上编码样本$x_{i}$和$x_{j}$来进行。SNN 学习一个函数$d$，使用编码特征，如图 5 所示。网络然后输出$y>0$用于相似对象（即，当$d$小于阈值时），否则输出$y<0$。因此，SNN 可以通过学习对象间的距离函数用于相似度学习。除了对有限样本的监督学习有价值外，SNN 对于无监督学习任务[55] [56]也有益处。

<svg height="177.72" overflow="visible" version="1.1" width="349.35"><g transform="translate(0,177.72) matrix(1 0 0 -1 0 0) translate(83.32,0) translate(0,98.7)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1.0 0.0 0.0 1.0 -24.97 46.81)" fill="#000000" stroke="#000000"><foreignobject width="10.58" height="8.51" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{i}$</foreignobject></g> <g transform="matrix(1.0 0.0 0.0 1.0 -0.08 26.92)" fill="#000000" stroke="#000000"><foreignobject width="78.91" height="24.91" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">| Network-1 |</foreignobject></g> <g transform="matrix(1.0 0.0 0.0 1.0 -25.46 -69.9)" fill="#000000" stroke="#000000"><foreignobject width="11.54" height="10.02" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{j}$</foreignobject></g> <g transform="matrix(1.0 0.0 0.0 1.0 -0.08 -71.51)" fill="#000000" stroke="#000000"><foreignobject width="78.91" height="24.91" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">| Network-2 |</foreignobject></g> <g transform="matrix(1.0 0.0 0.0 1.0 -78.71 -13.3)" fill="#000000" stroke="#000000"><foreignobject width="113.19" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">Shared parameters</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 102.95 46.81)" fill="#000000" stroke="#000000"><foreignobject width="10.64" height="12.16" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$h_{i}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 102.46 -73.55)" fill="#000000" stroke="#000000"><foreignobject width="11.61" height="13.67" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$h_{j}$</foreignobject></g><g stroke-opacity="1" fill="#000000" fill-opacity="1" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 123 -13)"><foreignobject width="46.36" height="14.44" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$d(h_{i},h_{j})$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 186.3 -0.89)" fill="#000000" stroke="#000000"><foreignobject width="70.32" height="12.98" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$-1\leq y_{i,j}\leq 1$</foreignobject></g></g></svg>

图 5：SNN 的示意图。在这个图中，$x_{i}$和$x_{j}$是来自训练集的一对数据向量。两个网络共享相同的权重，并将输入映射到新的表示中。通过使用诸如欧几里得距离等距离度量比较网络的输出，我们可以确定实例$x_{i}$和$x_{j}$之间的兼容性。

### 2.4 无监督学习

#### 2.4.1 生成对抗网络

直到调查的这一点，我们一直关注于深度学习在分类数据点方面的强大能力。然而，研究人员也利用深度学习进行其他用途，例如生成具有已知真实数据特征的合成数据。创建合成数据的一种方法是学习生成模型。生成模型根据对真实数据点的观察，学习支配某一分布的参数。然后可以使用学习到的模型生成任意数量的合成数据，这些数据模拟真实数据的观察。最近，研究人员发现了一种利用多人游戏来改进生成机器学习算法的方法。在对抗训练场景中，两个代理相互竞争，灵感来自于 Samuel [57]，他设计了一个计算机程序让其与自己下跳棋。Goodfellow 等人[58]将这一思想应用于开发生成对抗网络（GANs），在这种网络中，一个 DNN（生成器）试图生成与真实数据非常相似的合成数据，从而欺骗其对手 DNN（判别器），判别器的工作是区分真实数据和虚假数据（参见图 6）。GANs 的目标是同时提高生成器产生逼真数据的能力和判别器区分合成数据与真实数据的能力。GANs 在包括将文本翻译为图像[59]、发现药物[60]、以及将草图转化为图像[61] [62]等各种任务中取得了成功的应用。

<svg   height="177.72" overflow="visible" version="1.1" width="335.2"><g transform="translate(0,177.72) matrix(1 0 0 -1 0 0) translate(98.7,0) translate(0,98.7)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1.0 0.0 0.0 1.0 47.99 44.26)" fill="#000000" stroke="#000000"><foreignobject width="61.5" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">真实数据</foreignobject></g> <g transform="matrix(1.0 0.0 0.0 1.0 107.69 14.46)" fill="#000000" stroke="#000000"><foreignobject width="99.59" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">| 判别器 |

| 网络 | </foreignobject></g> <g transform="matrix(1.0 0.0 0.0 1.0 202.99 44.26)" fill="#000000" stroke="#000000"><foreignobject width="27.1" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">真实</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 202.6 24.87)" fill="#000000" stroke="#000000"><foreignobject width="27.87" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">虚假</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -93.36 -54.17)" fill="#000000" stroke="#000000"><foreignobject width="88.29" height="9.61" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">随机噪声</foreignobject></g> <g transform="matrix(1.0 0.0 0.0 1.0 0.62 -83.96)" fill="#000000" stroke="#000000"><foreignobject width="77.51" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible"> | 生成器 |
| --- | --- | --- |
| 网络 | </foreignobject></g>  <g transform="matrix(1.0 0.0 0.0 1.0 134.28 -83.96)" fill="#000000" stroke="#000000"><foreignobject width="46.39" height="49.81" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible"> | 虚假 |

| 数据 |</foreignobject></g></g></svg>

图 6：GAN 的示意图。判别网络的目标是区分真实数据和虚假数据，而生成网络的目标是利用来自判别器的反馈生成判别器无法区分的真实数据。

#### 2.4.2 自编码器

深度神经网络的另一个目的就是提供数据压缩和维度减少。自编码器（AE）是一种通过创建与输入层类似的输出层、使用由中间层表示的减少术语集来实现这一目标的 DNN [48]。从架构上看，自编码器结合了两个网络。第一个网络称为编码器，它学习具有较少特征的输入 $x$ 的新表示 $h=f(x)$；第二部分称为解码器，它将 $h$ 映射到输入空间的重构 $\hat{y}=g(h)$，如图 7 所示。自编码器的目标不仅仅是重建输入特征。相反，自编码器学习输入特征的近似，以识别数据的有用属性。自编码器是维度减少 [63]、特征学习 [64]、图像着色 [65]、高分辨率数据生成 [66] 和潜在空间聚类 [67] 的重要工具。此外，变分自编码器（VAEs） [68] 等其他版本的自编码器也可以用作生成模型。

`<svg height="167.68" overflow="visible" version="1.1" width="305.94"><g transform="translate(0,167.68) matrix(1 0 0 -1 0 0) translate(39.65,0) translate(0,83.66)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1.8 0.0 0.0 1.8 -9.34 -53.6)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\vdots$</foreignobject></g><g transform="matrix(1.8 0.0 0.0 1.8 226.88 -53.6)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="12.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$\vdots$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 249.06 51.87)" fill="#000000" stroke="#000000"><foreignobject width="11.15" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 249.06 22.34)" fill="#000000" stroke="#000000"><foreignobject width="11.15" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{2}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 249.06 -7.18)" fill="#000000" stroke="#000000"><foreignobject width="11.15" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{3}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 247.6 -66.24)" fill="#000000" stroke="#000000"><foreignobject width="14.08" height="8.65" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$y_{m}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -30.64 51.68)" fill="#000000" stroke="#000000"><foreignobject width="11.78" height="8.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -30.64 22.15)" fill="#000000" stroke="#000000"><foreignobject width="11.78" height="8.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{2}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -30.64 -7.38)" fill="#000000" stroke="#000000"><foreignobject width="11.78" height="8.45" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{3}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -32.1 -67.26)" fill="#000000" stroke="#000000"><foreignobject width="14.71" height="7.63" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$x_{m}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -24.91 66.9)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 7.705)"><g transform="matrix(1 0 0 1 0 12.52)"><g transform="matrix(1 0 0 -1 0 0)"><text transform="matrix(1 0 0 -1 0 0)">编码器</text></g></g></g></g><g transform="matrix(1.0 0.0 0.0 1.0 211.51 66.9)" fill="#000000" stroke="#000000"><g transform="matrix(1 0 0 -1 0 7.705)"><g transform="matrix(1 0 0 1 0 12.52)"><g transform="matrix(1 0 0 -1 0 0)"><text transform="matrix(1 0 0 -1 0 0)">解码器</text></g></g></g></g></g></svg>`

图 7：自编码器的示意图。网络的第一部分称为编码器，通过学习函数 $h=f(x)$ 将输入压缩到潜在空间。第二部分称为解码器，通过学习函数 $\hat{y}=g(h)$ 从潜在空间表示中重建输入。

### 2.5 深度神经网络的训练优化

在前一节中，我们描述了常见的 DNN 架构组件。在本节中，我们简要概述了训练 DNN 的优化方法。学习方法可以通过修改模型参数（例如，更改 DNN 权重）来优化函数 $f(x)$（例如，最小化损失函数）。然而，正如 Bengio 等人 [69] 所指出的那样，训练过程中的 DNN 优化可能会因局部极小值和不良条件而变得更加复杂（请参见图 8 以查看不良条件的插图）。

DNN 最常用的优化策略是梯度下降。这种直观的方法通过计算相对于网络中 Ir 级层的误差导数来学习层间连接的权重，从而减少网络的目标函数。输入 $x$ 被前向传递通过网络以预测 $\hat{y}$。成本函数 $J(\theta)$ 衡量网络在输出层的误差。然后，梯度下降通过计算目标函数的梯度 $\nabla_{\theta}J(\theta)$ 来将成本值反向传递通过网络。这个过程有时被称为反向传播，因为训练误差从输出层向输入层反向传播。许多梯度下降的变种已被用于 DNN 优化，如随机梯度下降、迷你批量梯度下降、动量 [70]、Ada-Grad [71] 和 Adam [72]。

深度网络优化是一个活跃的研究领域。除了梯度下降，许多其他算法如无导数优化 [73] 和反馈对齐 [74] 也已经出现。然而，这些算法都没有梯度下降算法那么流行。

图 8：左侧的损失表面描绘了一个良好条件的模型，其中局部极小值可以从所有方向达到。右侧的损失表面描绘了一个不良条件的模型，其中有多种方式可以超越或永远无法到达极小值。

### 2.6 正则化

正则化在 DNNs 发展之前几十年一直是优化的基础。将正则化项添加到分类器中的理由是为了避免过拟合问题，即分类器过于贴合训练集而不能很好地推广到整个数据空间。Goodfellow 等人[48]将正则化定义为“对学习算法的任何修改，其目的是减少其泛化误差而不是训练误差”。虽然像 bagging 这样的正则化方法在神经网络和其他分类器中很受欢迎，但最近 DNN 社区开发了一些独特于深度神经网络的新型正则化方法。在某些情况下，完全连接的 DNN 的反向传播训练效果不如浅层结构，因为更深的结构容易陷入局部最小值并对训练数据进行过拟合。为了提高 DNN 的泛化能力，因此在训练过程中采用了正则化方法。在这里，我们回顾了目前在 DNN 中最常见的正则化方法的直觉。

#### 2.6.1 参数范数惩罚

避免过拟合的传统方法是通过将 p-范数惩罚函数添加到形式为$f(x)+$ p-norm$(x)$的优化函数中来惩罚大权重，其中权重$w$的 p-范数$p$表示为$||w||_{p}=(\sum_{i}|w_{i}|^{p})^{\frac{1}{p}}$。流行的 p-范数包括$L_{1}$和$L_{2}$范数，这些范数在 DNNs 出现之前已被其他分类器（如逻辑回归和支持向量机）使用。$L_{1}$在目标函数中添加一个正则化项$\Omega(\theta)=||w||_{1}$，而$L_{2}$则添加一个正则化项$\Omega(\theta)=||w||_{2}$。$L_{1}$和$L_{2}$范数惩罚函数的区别在于，$L_{1}$通过将相应的边权重设置为零来对特征施加更严格的惩罚，相比之下$L_{2}$则较轻。因此，使用$L_{1}$范数惩罚的分类器倾向于选择稀疏模型。$L_{2}$范数惩罚比$L_{1}$范数惩罚更为常见。然而，当训练数据量较小而特征数量较大时，建议使用$L_{1}$范数惩罚，以避免噪声和不重要的特征。由于其稀疏性，$L_{1}$惩罚函数是 LASSO 特征选择的关键组成部分[75]。

#### 2.6.2 Dropout

减少泛化误差的一种强大方法是创建分类器的集成。多个模型分别训练，然后作为一个集成输出模型对测试点的预测组合。一些集成方法的例子包括 bagging [76]，它在具有替换的$k$个不同随机样本折叠上训练$k$个模型，以及 boosting [77]，它对加权数据应用类似过程。各种 DNN 使用 boosting 来实现较低的泛化误差[45] [78] [79]。

Dropout [80] 是一种流行的 DNN 正则化方法，可以看作是对深度网络的计算上廉价的 bagging 应用。对 DNN 应用 dropout 的一种常见方式是对每个小批量数据禁用随机选择的 50%的隐藏节点和随机选择的 20%的输入节点。bagging 与 dropout 的区别在于，bagging 中的模型彼此独立，而在 dropout 中，每个模型从父深度网络继承了一部分参数。

#### 2.6.3 数据增强

深度神经网络（DNNs）在拥有更多训练数据时能够更好地泛化；然而，可用的数据量通常有限。解决这个限制的一种方法是从与训练集相同的分布中生成人工数据。数据增强在分类任务中尤其有效。数据增强的目标是通过转换$X$输入，从原始训练集$(X,y)$生成新的训练样本。数据增强可能包括生成噪声数据以提高鲁棒性（去噪）或创建额外的训练数据以进行正则化（合成数据生成）。数据集增强已被应用于图像识别[81] [82]、语音识别[83]和活动识别[84]等各种任务。此外，GANs [85] [86]和 AEs [87] [88]，在 2.4.1 和 2.4.2 节中描述的，可以用来生成这样的新示例。

将噪声注入输入副本是另一种数据增强方法。尽管 DNN 对噪声的鲁棒性并不一致[89]，但 Poole 等人[90]表明，DNN 可以从精心调整的噪声中受益。

## 3 种深度学习架构，超越深度神经网络

最近的研究引入了许多对基础神经网络架构的增强，特别是对于深度网络，提升了网络的分类能力。在这一部分，我们调查了那些也利用这些进展的非网络分类器。

### 3.1 监督学习

#### 3.1.1 前馈学习

一个深度神经网络（DNN）涉及多个层的操作，这些操作是顺序执行的。创建一个操作序列的想法，每个操作在将数据传递给下一个操作符之前对数据进行处理，可以用于改进许多类型的分类器。构建深度前馈架构模型的一种方法是使用堆叠泛化 [91] [92]。堆叠泛化分类器由多个层叠在一起的分类器组成，如同在深度神经网络（DNNs）中所发现的那样。在堆叠泛化分类器中，一层通过将其自己的输入与其输出连接起来来生成下一层的输入。与同时前向和后向传播信息的 DNNs 不同，堆叠泛化分类器通常只实现前向传播。

通常，使用堆叠泛化的学习方法可以分为两种策略。在第一种堆叠泛化策略中，当前层的新特征空间来自于将上一层的预测输出与原始特征向量连接。在这里，层不是指神经网络操作的层，而是指其他类型操作的序列。这种策略的例子包括深度森林（DF） [93] 和深度传输加性核最小二乘支持向量机（DTA-LS-SVM） [94]。在任何给定的层中，对于每个实例 $x$，DF 将 $x$ 的先前特征向量扩展为包括先前层对该实例的预测类别值。该预测表示所有森林中的树的类别值分布的平均值。此外，Zhou 等人 [93] 提出了一种称为多粒度扫描的方法，以提高 DF 的准确性。受 CNNs 和 RNNs 启发，这些网络中特征之间的空间关系至关重要，多粒度扫描通过在特征上移动窗口，将 $D$ 维特征向量拆分为更小的片段。例如，给定 400 个特征和 100 的窗口大小，原始特征转换为 301 个长度为 100 的特征，$\{<1-100>,<2-101>,\ldots,<301-400>\}$，其中新的实例与原始实例具有相同的标签。这些由原始特征子集描述的新样本可能具有错误关联的标签。乍一看，这些噪声数据似乎可能会影响泛化。但正如 Breiman 所示 [95]，扰动一部分训练标签实际上可能有助于泛化。

此外，Ho [96] 证明特征子采样可以增强随机森林的泛化能力。Zhou 等人[93]测试了三种不同的窗口大小（$D/4$，$D/8$，和$D/16$），每种窗口大小的数据适合 DF 模型的不同层级。然后，这三层中新学习到的表示被输入到一个多层 DF 中，当转换后的特征过长时应用子采样。多粒度扫描可以提高 DF 模型在连续数据上的性能，因为 Zhou 等人[93]报告称，MNIST [97]数据集上的准确率提高了 1.24%。另一种方法，DTA-LS-SVM，在每一层应用加性核最小二乘支持向量机（AK-LS-SVM）[98] [99]，并将原始特征向量$x$与前一层的预测连接起来，以输入到下一层。此外，DTA-LS-SVM 在源（前一层学习者）和目标（下一层学习者）之间引入了参数转移方法，以增强较高层次的分类能力。

在第二种堆叠泛化策略中，当前层的新特征空间来源于所有前一层的预测与原始输入特征向量的连接。该策略的例子包括深度支持向量机（D-SVM）[100]和随机递归支持向量机（R2-SVM）[101]。D-SVM 包含多个支持向量机层，其中第一层以正常方式训练。之后，每一层都使用来自前一层的核激活与期望标签。R2-SVM 是一个多层支持向量机模型，在每一层根据所有前一层输出的投影的 sigmoid 来转换数据。对于数据$(X,Y)$，其中$X\in R^{D}$和$Y\in R^{C}$，随机投影矩阵是$W\in R^{D\times C}$，其中每个元素从$N(0,1)$中抽样。下一层的输入数据为：

|  | $X_{l+1}=\sigma(d+\beta W_{l+1}[o_{1}^{T},o_{2}^{T},...,o_{l}^{T}]^{T}),$ |  | (1) |
| --- | --- | --- | --- |

其中$\beta$是一个权重参数，控制数据样本在$X_{l+1}$中从上一层移动的程度，$\sigma(.)$是 sigmoid 函数，$W_{l+1}$是$l$个随机投影矩阵的连接$[W_{l+1,1},W_{l+1,2},...,W_{l+1,l}]$，每个矩阵对应于前一层，每一层的输出为$o$。将 sigmoid 函数添加到递归模型中可以防止模型退化为类似于多层感知机（MLPs）的平凡线性模型。随机投影的目的是将来自不同类别的数据推向不同的方向。

需要注意的是，堆叠泛化可以在深度神经网络（DNNs）以及非网络分类器中找到。具有堆叠泛化的 DNN 示例包括深度堆叠网络 [102] [103] 和凸堆叠架构 [104] [102]。这显然是对所有类型分类器策略的一个增强。然而，目前没有证据表明堆叠泛化可以为模型增加非线性。

DNN 分类器在每一层学习数据的新表示，目标是使新学习的表示能最大限度地分隔类别。无监督的 DNN 通常也有这个目标。例如，深度主成分分析模型 [105] 由两层组成，每层通过应用零分量分析（ZCA）白化滤波器 [106]，然后进行主成分分析（PCA） [107] 来学习新的数据表示。最终的数据表示是由两层的输出拼接而成。应用 ZCA 白化滤波器的动机是迫使模型关注高阶相关性。结合第一层和第二层的输出的一个动机可能是为了保留第一层学到的表示，并在每层应用 PCA 后防止特征丢失。实验表明，相比于标准 PCA 和没有白化滤波器的两层 PCA，深度 PCA 在面部识别任务中表现更佳。然而，正如 Damianou 等人 [108] 实证确认的那样，堆叠 PCA 不一定会导致数据表示的改进，因为深度 PCA 无法在每层学习非线性数据表示。Damianou 等人 [108] 将高斯分布输入深度 PCA，并观察到模型在每一层仅学习了输入高斯分布的较低秩。

正如本调查中早先指出的，深度置信网络（DBN）的发明[45]引起了研究人员对开发深度模型的关注。DBN 可以视为一个堆叠的限制玻尔兹曼机（RBM），每一层单独训练，并在隐藏单元和输入单元之间交替功能。在这个模型中，隐藏层学习到的特征表示为下一层的输入。RBM 是一种生成模型，包含一个隐藏层。与玻尔兹曼机不同，限制模型中的隐藏单元彼此不连接，并且包含来自可见单元（输入）的无向对称连接。RBM 中的每一层单元通过将当前单元状态输入到另一层来并行更新。这个更新过程会重复，直到系统从平衡分布中采样。RBM 的学习规则如方程 2 所示。

|  | $\frac{\partial\log P(v)}{\partial W_{ij}}\approx<v_{i}h_{j}>_{data}-<v_{i}h_{j}>_{reconstruction}$ |  | (2) |
| --- | --- | --- | --- |

在这个方程中，$W_{ij}$表示可见单元$v_{i}$和隐藏单元$h_{j}$之间的权重向量，$<.>$是所有训练样本的平均值。自 DBN 引入以来，已经提出了许多不同变体的深度 RBM，例如时间 RBM[109]、门控 RBM[110]和基数 RBM[111]。

深度置信网络的另一种新颖形式是深度高斯过程（DGP）模型[108]。DGP 是一个深度有向图，其中多层高斯过程将原始特征映射到一系列潜在空间。DGP 提供了高斯过程（GP）[112]的更一般形式，其中单层 DGP 由一个 GP 组成，$f$。在多层 DGP 中，每个 GP，$f_{l}$，将数据从一个潜在空间映射到下一个。如方程 3 所示，每个数据点$Y$是由对应的函数$f_{l}$生成的，$\epsilon$ 高斯噪声施加在从上一层获得的数据$X_{l}$上。

|  | $Y=f_{l}(X_{l})+\epsilon_{l},\indent\epsilon_{l}\sim\mathcal{N}(0,\sigma^{2}_{l}I)$ |  | (3) |
| --- | --- | --- | --- |

图 9 展示了一个 DGP，它被表示为一系列高斯过程，将数据从一个潜在空间映射到下一个。函数 $f_{l}$ 来自一个高斯过程，即 $f(x)\sim\mathcal{GP}(0,k(x,x^{\prime}))$。在这种设置下，协方差函数 $k$ 定义了映射函数的属性。DGP 可以用于监督学习和无监督学习。在监督学习中，顶层隐藏层是观察到的，而在无监督学习中，顶层隐藏层被设置为单位高斯作为一种相对不具信息量的先验。DGP 是一个强大的非参数模型，但它仅在小型数据集上进行了测试。此外，我们注意到研究人员开发了具有替代架构的深度高斯过程模型，例如递归高斯过程 [113]、卷积高斯过程 [114] 和变分自编码深度高斯过程 [115]。关于这一主题存在大量文献，提供了关于深度高斯过程的额外见解 [116] [117] [118]。

<svg height="90.85" overflow="visible" version="1.1" width="349.6"><g transform="translate(0,90.85) matrix(1 0 0 -1 0 0) translate(98.62,0) translate(0,2.26)" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g transform="matrix(1.0 0.0 0.0 1.0 -94.01 69.09)" fill="#000000" stroke="#000000"><foreignobject width="10.38" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">X</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 -6.07 70.36)" fill="#000000" stroke="#000000"><foreignobject width="12.14" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$f_{1}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 72.67 70.36)" fill="#000000" stroke="#000000"><foreignobject width="12.14" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$f_{2}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 151.41 70.36)" fill="#000000" stroke="#000000"><foreignobject width="12.14" height="12.3" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$f_{3}$</foreignobject></g><g transform="matrix(1.0 0.0 0.0 1.0 230.67 69.09)" fill="#000000" stroke="#000000"><foreignobject width="11.11" height="9.46" transform="matrix(1 0 0 -1 0 16.6)" overflow="visible">$Y$</foreignobject></g></g></svg>

图 9：具有两个隐藏层的深度高斯过程。

正如我们讨论的那样，已经设计出包含多个操作层的非网络分类器，类似于 DNN。我们观察到，创建深度非网络模型的一种常见策略是将前一层或几层的预测添加到原始输入特征中。同样，可以应用新方法在每一层学习数据的新表示。接下来我们讨论这些方法。

#### 3.1.2 孪生模型

如第 2.3.4 节讨论的，SNN（孪生神经网络）代表了一种强大的相似性学习方法。然而，SNN 的一个问题是当训练样本数量较少时会过拟合。Siamese Deep Forest (SDF) [119] 是一种基于 DF（深度森林）的方法，提供了一个替代标准 SNN 的选项。与 SNN 不同，SDF 仅使用一个 DF。训练 SDF 的第一步是修改训练样本。训练集由原始集合中每对样本的串联组成。如果样本点 $x_{i}$ 和 $x_{j}$ 在语义上相似，则相应的类别标签设置为零；否则，类别标签设置为一。SDF 和 DF 在训练中的区别在于，Siamese Deep Forest 将原始特征向量与树类概率的加权和串联在一起。SDF 的训练类似于 DF；主要区别在于 SDF 在每层单独为每个森林学习类别概率权重 $w$。通过最小化方程 4 中的函数可以完成对每个森林权重的学习。

|  | $\min\limits_{w}J_{q}(w)=\min\limits_{w}\sum_{i,j}l(x_{i},x_{j},y_{ij},w)+\lambda R(w)$ |  | (4) |
| --- | --- | --- | --- |

这里，$w$ 代表向量 $w^{k}$ 的串联，$k=1,...,M$，$q$ 是 SDF 层，$R(w)$ 是正则化项，而 $\lambda$ 是控制正则化的超参数。最小化方程 4 的详细说明可以在文献中找到 [119]。SDF 实验的结果表明，SDF 可以在小数据集上实现比 DF 更好的分类准确性。一般来说，所有学习数据表示的非网络模型都可以利用类似 SDF 的 Siamese 架构。

### 3.2 无监督学习

#### 3.2.1 生成对抗模型

GANs 中一个常见的元素是鉴别器中包含一个全连接层（FC）。全连接层的问题之一是它无法处理局部最小值周围没有球形井的恶劣条件，如图 8 所示。生成对抗森林（GAF）[120] 用深度神经决策森林（DNDF）替代鉴别器的全连接层，这在第四部分中讨论。GAF 和 DNDF 的区别在于叶节点值的学习方式。与 DNDF 迭代学习叶节点值不同，GAF 在集成成员之间并行学习这些值。决策森林的强大区分能力是作者推荐这种方法代替全连接鉴别器层的原因。

在这项早期工作中，鉴别器被替换为一种非常规模型。我们假设，将鉴别器替换为其他分类器，如随机森林、支持向量机（SVM）或基于数据的 K 近邻，可能会导致多样化的 GAN 策略，每种策略可能对不同的学习问题提供好处。

#### 3.2.2 自动编码器

正如我们在第 2.4.2 节中讨论的，自动编码器（AE）提供了从压缩信息中进行降维和数据重建的策略。自动编码方法可以在神经网络、非网络和混合方法中找到。例如，多层 SVM（ML-SVM）自动编码器是具有与输入特征相同数量的输出节点和单一隐藏层（该层的节点数少于输入特征）的 ML-SVM 的一种变体。ML-SVM 是一个具有与 MLP 相同结构的模型。不同之处在于，该网络包含 SVM 模型作为其节点。ML-SVM 的综述讨论在第四部分中。隐藏节点的输出被作为输入传递到每个 SVM 输出节点 $c$ 中，如下所示：

|  | $g_{c}(f(X&#124;\theta))=\sum_{i=1}^{l}(\alpha_{i}^{c*}-\alpha_{i}^{c})K_{o}(f(x_{i}&#124;\theta),f(x&#124;\theta))+b_{c},$ |  | (5) |
| --- | --- | --- | --- |

其中 $\alpha_{i}^{c*}$ 和 $\alpha_{i}^{c}$ 是支持向量系数，$K_{o}$ 是核函数，$b_{c}$ 是它们的偏置。误差通过网络反向传播以更新参数。

另一个令人兴奋的新兴研究领域是卡尔曼滤波器与深度网络的结合。卡尔曼滤波器是一个著名的算法，它通过一系列噪声观察来估计系统的最优状态。经典的卡尔曼滤波器 [121] 是一个线性动态系统，因此无法建模复杂现象。正因为如此，研究人员开发了非线性版本的卡尔曼滤波器。在一个开创性的贡献中，Krishnan 等人 [122] 提出了一个模型，将变分自编码器与卡尔曼滤波器结合，用于患者信息的反事实推断。在标准自编码器中，模型学习一个潜在空间，该空间表示原始数据减去多余的信息或“信号噪声”。相比之下，变分自编码器（VAE） [68] 为编码器增加了一个约束，要求其学习原始输入数据的高斯分布。因此，VAE 能够通过从学习到的高斯分布中采样生成潜在向量。深度卡尔曼滤波器（DKF）从观察到的序列 $\vec{x}=(x_{1},\cdots,x_{T})$ 和动作 $\vec{u}=(u_{1},\cdots u_{T-1})$ 学习一个生成模型，并具有一个相应的潜在空间 $\vec{z}=(z_{1},\cdots,z_{T})$，具体如下：

|  | <math   alttext="\begin{split}&amp;z_{1}\sim\mathcal{N}(\mu_{0},\Sigma_{0})\\ &amp;z_{t}\sim\mathcal{N}(G_{\alpha}(z_{t-1},u_{t-1},\Delta_{t}),S_{\beta}(z_{t-1},y_{t-1},\Delta_{t}))\\

&amp;x_{t}\sim\Pi(F_{k}(z_{t})),\\

\end{split}" display="block"><semantics ><mtable columnspacing="0pt" displaystyle="true" rowspacing="0pt" ><mtr ><mtd columnalign="left" ><mrow ><msub ><mi  >z</mi><mn >1</mn></msub><mo >∼</mo><mrow ><mi >𝒩</mi><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><msub ><mi >μ</mi><mn >0</mn></msub><mo >,</mo><msub ><mi mathvariant="normal"  >Σ</mi><mn >0</mn></msub><mo stretchy="false"  >)</mo></mrow></mrow></mrow></mtd></mtr><mtr ><mtd  columnalign="left" ><mrow ><msub ><mi >z</mi><mi  >t</mi></msub><mo >∼</mo><mrow ><mi >𝒩</mi><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><mrow ><msub ><mi  >G</mi><mi >α</mi></msub><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><msub ><mi >z</mi><mrow ><mi >t</mi><mo >−</mo><mn >1</mn></mrow></msub><mo >,</mo><msub ><mi >u</mi><mrow ><mi >t</mi><mo >−</mo><mn >1</mn></mrow></msub><mo >,</mo><msub ><mi mathvariant="normal"  >Δ</mi><mi >t</mi></msub><mo stretchy="false"  >)</mo></mrow></mrow><mo >,</mo><mrow ><msub ><mi >S</mi><mi >β</mi></msub><mo lspace="0em" rspace="0em" >​</mo><mrow ><mo stretchy="false" >(</mo><msub ><mi >z</mi><mrow ><mi >t</mi><mo >−</mo><mn >1</mn></mrow></msub><mo >,</mo><msub ><mi >y</mi><mrow ><mi >t</mi><mo >−</mo><mn >1</mn></mrow></msub><mo >,</mo><msub ><mi mathvariant="normal"  >Δ</mi><mi >t</mi></msub><mo stretchy="false"  >)</mo></mrow></mrow><mo stretchy="false"  >)</mo></mrow></mrow></mrow></mtd></mtr><mtr ><mtd  columnalign="left" ><mrow ><mrow ><msub ><mi  >x</mi><mi >t</mi></msub><mo >∼</mo><mrow ><mi mathvariant="normal"  >Π</mi><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><mrow ><msub ><mi >F</mi><mi  >k</mi></msub><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><msub ><mi >z</mi><mi >t</mi></msub><mo stretchy="false" >)</mo></mrow></mrow><mo stretchy="false" >)</mo></mrow></mrow></mrow><mo >,</mo></mrow></mtd></mtr></mtable><annotation-xml encoding="MathML-Content" ><apply ><apply  ><csymbol cd="latexml"  >similar-to</csymbol><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑧</ci><cn type="integer" >1</cn></apply><apply ><ci >𝒩</ci><interval closure="open" ><apply  ><csymbol cd="ambiguous"  >subscript</csymbol><ci >𝜇</ci><cn type="integer" >0</cn></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >Σ</ci><cn type="integer" >0</cn></apply></interval><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑧</ci><ci >𝑡</ci></apply></apply></apply><apply ><csymbol cd="latexml" >similar-to</csymbol><apply ><ci  >𝒩</ci><interval closure="open"  ><apply ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝐺</ci><ci  >𝛼</ci></apply><vector ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑧</ci><apply ><ci >𝑡</ci><cn type="integer" >1</cn></apply></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑢</ci><apply ><ci >𝑡</ci><cn type="integer" >1</cn></apply></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >Δ</ci><ci >𝑡</ci></apply></vector></apply><apply ><apply  ><csymbol cd="ambiguous"  >subscript</csymbol><ci >𝑆</ci><ci >𝛽</ci></apply><vector ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑧</ci><apply ><ci >𝑡</ci><cn type="integer" >1</cn></apply></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑦</ci><apply ><ci >𝑡</ci><cn type="integer" >1</cn></apply></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >Δ</ci><ci >𝑡</ci></apply></vector></apply></interval><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑥</ci><ci >𝑡</ci></apply></apply></apply><apply ><csymbol cd="latexml" >similar-to</csymbol><apply ><ci  >Π</ci><apply ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝐹</ci><ci  >𝑘</ci></apply><apply ><csymbol cd="ambiguous"  >subscript</csymbol><ci >𝑧</ci><ci >𝑡</ci></apply></apply></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" >\begin{split}&z_{1}\sim\mathcal{N}(\mu_{0},\Sigma_{0})\\ &z_{t}\sim\mathcal{N}(G_{\alpha}(z_{t-1},u_{t-1},\Delta_{t}),S_{\beta}(z_{t-1},y_{t-1},\Delta_{t}))\\ &x_{t}\sim\Pi(F_{k}(z_{t})),\\ \end{split}</annotation></semantics></math> |  | (6) |

其中$\mu_{0}=0$和$\Sigma_{0}=I_{d}$，$\Delta_{t}$表示时间$t$与$t-1$之间的差异，$\Pi$表示观测$x_{t}$上的分布（例如，二值数据的伯努利分布）。函数$G_{\alpha}$、$S_{\beta}$、$F_{k}$由神经网络参数化。因此，自编码器将学习$\theta=\{\alpha,\beta,k\}$参数。此外，Shashua 等人[123]引入了带有卡尔曼滤波器的深度 Q 学习，Lu 等人[124]提出了一种用于视频压缩的深度卡尔曼滤波器模型。

正如我们在本节中强调的，已经设计了受自编码器（AEs）启发的非网络方法。尽管 ML-SVM 模仿了 AEs 的架构，但其计算成本使得该算法无法成为实际的选择。DKF 利用变分自编码器（VAE）的思想，在其中间层学习卡尔曼滤波器。此外，Feng 等人[125]引入了一种编码器森林模型，该模型受到 DNN 自编码器的启发。由于编码器森林不是深度模型，因此我们没有在本次调查中包含该算法的细节。

## 4 深度学习优化：超越深度神经网络

正如 2.5 节中讨论的那样，梯度下降一直是 DNN 的主要优化算法；然而，它在非网络分类器中的应用不足。文献中找到了一些显著的例外情况。我们在这里进行讨论。

构建深度模型的一种资源丰富的方法是从 DNN 架构开始，然后用非网络分类器替换节点。例如，多层 SVM（ML-SVM）[126]用标准 SVM 替换了 MLP 中的节点。ML-SVM 是一种包含网络内 SVM 的多类分类器。在输出层，ML-SVM 包含的 SVM 数量与感知器输出层学习的类别数量相同。ML-SVM 输出层中的每个 SVM 都以一对多的方式为其中一个类别进行训练。当观察到一个新数据点时，ML-SVM 输出对应于生成最高置信度的 SVM 的类别标签。在每个隐藏层中，SVM 与学习潜在变量的每个节点相关联。这些变量随后被送到输出层。在隐藏层$f(X|\theta)$中，其中$X$是训练集，$\theta$表示 SVM 的可训练参数，ML-SVM 将隐藏层特征映射到输出值，如下所示：

|  | $g(f(X&#124;\theta))=\sum^{l}_{i=1}y^{c}_{i}\alpha^{c}_{i}K_{o}(f(x_{i}&#124;\theta),f(X&#124;\theta))+b_{c},$ |  | (7) |
| --- | --- | --- | --- |

其中$g$是输出层函数，$y_{i}^{c}\in\{-1,1\}$表示每个类别$c$，$K_{o}$是输出层的核函数，$\alpha_{i}^{c}$是输出层 SVM 节点的支持向量系数，$b_{c}$是它们的偏差。ML-SVM 的目标是学习每个 SVM 在输出层的最大支持向量系数，目标函数为$J_{c}(.)$，如方程 8 所示。

|  | $\min_{w^{c},b,\xi,\theta}J_{c}=\frac{1}{2}&#124;&#124;w^{c}&#124;&#124;^{2}+C\sum_{i}^{l}\xi_{i}$ |  | (8) |
| --- | --- | --- | --- |

在这里，$w^{c}$表示类别$c$的权重集，$C$表示边界宽度和误分类风险之间的权衡，$\xi_{i}$是松弛变量。ML-SVM 通过梯度上升来调整其支持向量系数，以趋向于$J_{c}(.)$的局部最大值。支持向量系数对于小于零的值定义为零，对于大于$C$的值则赋值为$C$。数据通过计算目标函数的梯度类似于传统的 MLPs 在网络中反向传播。

隐藏层中的 SVMs 是相同的。给定相同的输入，它们会生成相同的输出。为了使 SVMs 具有多样性，隐藏层在训练集的扰动版本上进行训练，以消除在训练组合的 ML-SVM 模型之前生成相似输出的问题。隐藏层节点的输出被限制在$[-1\ldots 1]$范围内。尽管 ML-SVMs 努力学习多层数据表示，但由于添加新节点对大数据集来说会带来巨大的计算开销，这种方法目前并不实用。

Kontschieder 等人[127]进一步将梯度下降算法融入随机森林（RF）中，RF 是一种流行的分类方法。RF 的一个缺点是它不像深度神经网络（DNNs）那样传统地学习新的内部表示。深度网络决策森林（DNDF）[127]将 DNN 集成到森林中的每棵决策树内，以减少每个决策节点的不确定性。在 DNDF 中，决策节点$d_{n}(x,\Theta)$的结果对应于 DNN $f_{n}(x,\Theta)$的输出，其中$x$是输入，$\Theta$是决策节点的参数。DNDF 必须具有可微分的决策树，以便能够将梯度下降应用于更新决策节点的过程。在标准决策树中，决策节点$d_{n}(x,\Theta)$的结果是确定性的。DNDF 用一个 sigmoid 函数$d_{n}(x,\Theta)=\sigma(f_{n}(x;\Theta))$替代传统的决策节点，以创建一个随机决策节点。从根节点到叶节点$l$的所有决策节点输出的乘积计算到达叶节点$l$的概率，在这种情况下表示为$\mu_{l}$。叶节点集合$\mathcal{L}$学习类分布$\pi$，其中概率最高的类是树的预测结果。DNDF 的目标是最小化相对于决策节点参数$\Theta$和叶节点集合$\mathcal{L}$的类分布$\pi$的经验风险，使用对数损失函数进行优化。

经验风险的优化是一个两步过程，迭代执行。第一步是优化叶节点的类分布$\pi_{\mathcal{L}}$，同时固定决策节点参数和相应的 DNN。在优化开始时（迭代 0），类分布$\pi^{{0}}$被设为所有叶节点上的均匀分布。DNDF 随后迭代更新叶节点上的类分布，更新过程如下所示，适用于迭代 t+1：

|  | $\pi_{l_{y}}^{(t+1)}=\frac{1}{Z_{l}^{(t)}}\sum_{(x,y^{\prime})\in\mathcal{T}}\frac{\mathbbm{1}_{y=y^{\prime}}\pi_{l_{y}^{(t)}}\mu_{l}(x&#124;\Theta)}{\mathbb{P}_{T}[y&#124;x,\Theta,\pi^{(t)}]},$ |  | (9) |
| --- | --- | --- | --- |

其中$Z_{l}^{(t)}$是一个归一化因子，确保$\sum_{y}\pi^{t+1}_{l_{y}}=1$，$\mathbbm{1}_{q}$是对参数$q$的指示函数，$\mathbb{P}_{T}$是树的预测。

第二步是在固定类分布$\pi_{\mathcal{L}}$的情况下优化决策节点参数$\Theta$。DNDF 使用梯度下降来最小化相对于$\Theta$的对数损失，具体如下：

|  | $\frac{\partial L}{\partial\Theta}(\Theta,\pi;x,y)=\sum_{n\in\mathcal{N}}\frac{\partial L(\Theta,\pi;x,y)}{\partial f_{n}(x;\Theta)}\frac{\partial f_{n}(x;\Theta)}{\partial\Theta}.$ |  | (10) |
| --- | --- | --- | --- |

方程 10 中的第二项是 DNN 的梯度。由于这是广为人知的，我们仅讨论可微决策树的梯度计算。这里，可微决策树的梯度由下式给出：

|  | $\frac{\partial L(\Theta,\pi;x,y)}{\partial f_{n}(x;\Theta)}=d_{n}(x;\Theta)A_{n_{r}}-\bar{d}_{n}(x;\Theta)A_{n_{l}},$ |  | (11) |
| --- | --- | --- | --- |

其中 $d_{n}$ 是转到左子节点的概率，$\bar{d}_{n}=1-d_{n}$ 是通过 DNN 前向传播计算的转到右子节点的概率，$n_{l}$ 和 $n_{r}$ 表示节点 $n$ 的左子节点和右子节点。为了计算方程 11 中的项 $A$，DNDF 通过可微决策树执行一次前向传播和一次反向传播。在完成前向传播后，可以初步计算每个叶子节点的 $A_{l}$ 值，如下所示：

|  | $A_{l}=\frac{\pi_{l_{y}}\mu_{l}}{\sum_{l}\pi_{l_{y}}\mu_{l}}.$ |  | (12) |
| --- | --- | --- | --- |

接下来，利用每个叶子节点的 $A_{l}$ 值来计算每个内部节点 $m$ 的 $A_{m}$ 值。为此，通过决策树进行反向传播，在此过程中，值计算为 $A_{m}=A_{n_{l}}+A_{n_{r}}$，其中 $n_{l}$ 和 $n_{r}$ 分别表示节点 $m$ 的左子节点和右子节点。

标准 DNN 的每一层在层 $i$ 产生输出 $o_{i}$。如前所述，DNN 的目标是学习一个映射函数 $F_{i}:o_{i-1}\rightarrow o_{i}$，以最小化训练集上 DNN 最后一层的经验损失。由于每个 $F_{i}$ 是可微的，DNN 通过应用梯度下降法来高效地更新其参数，以减少经验损失。

采用不同的方法论，Frosst 等人 [128] 将神经网络提炼成一种软决策树。这个模型结合了基于神经网络的表示学习和基于决策树的概念解释。在 Frosst 软决策树（FSDT）中，每棵树的内部节点学习一个滤波器 $w_{i}$ 和一个偏置 $b_{i}$，叶子节点 $l$ 学习一个类别分布。类似于神经网络的隐藏单元，树的每个内部节点通过以下方式确定输入 $x$ 在节点 $i$ 的概率：

|  | $p_{i}(x)=\sigma(\beta(xw_{i}+b_{i}))$ |  | (13) |
| --- | --- | --- | --- |

其中 $\sigma$ 代表 sigmoid 函数，$\beta$ 代表一个逆温度，其功能是避免树中的软决策。滤波器激活将样本 $x$ 对于 $p_{i}$ 小于 $0.5$ 的值路由到左支，其他情况则路由到右支。每个叶子节点 $l$ 的概率分布 $Q^{l}$ 代表该叶子节点上的学习参数 $\phi^{l}$ 对于可能的 $k$ 输出类别：

|  | $Q_{k}^{l}=\frac{\exp(\phi_{k}^{l})}{\sum_{k^{\prime}}\exp(\phi_{k^{\prime}}^{l})}.$ |  | (14) |
| --- | --- | --- | --- |

类别上的预测分布通过遍历最大概率路径进行计算。为了训练这个软决策树，Frosst 等人 [128] 计算了一个损失函数 $L$，该函数最小化每个叶子之间的交叉熵，按输入向量 $x$ 的路径概率和目标分布 $T$ 加权，如下所示：

|  | $L(x)=-\log\Big{(}\sum_{l\in LeafNodes}P^{l}(x)\sum_{k}T_{k}\log Q_{k}^{l}\Big{)}$ |  | (15) |
| --- | --- | --- | --- |

其中 $P^{l}(x)$ 是给定输入 $x$ 到达叶子节点 $l$ 的概率。Frosst 等人 [128] 还引入了一个正则化项，以避免内部节点将所有数据点路由到特定路径，并鼓励它们沿左支和右支均匀路由数据。惩罚函数计算从根节点到节点 $i$ 的所有内部节点的总和，如下所示：

|  | $C=-\lambda\sum_{i\in InnerNodes}0.5\log(\alpha_{i})+0.5\log(1-\alpha_{i})$ |  | (16) |
| --- | --- | --- | --- |

其中 $\lambda$ 是在训练前设置的超参数，用于确定惩罚的效果。节点 $i$ 的交叉熵 $\alpha$ 是从根节点到节点 $i$ 的路径概率 $P^{i}(x)$ 乘以该节点的概率 $p_{i}$ 除以路径概率的总和，如下所示：

|  | $\alpha_{i}=\frac{\sum_{x}P^{i}(x)p_{i}(x)}{\sum_{x}P^{i}(x)}.$ |  | (17) |
| --- | --- | --- | --- |

由于倒数第二层节点的概率分布不均匀，这种惩罚函数可能实际上会伤害到泛化能力。作者通过将惩罚函数 $\lambda$ 的强度以节点深度 $d$ 指数级衰减到 $2^{d}$ 来解决这个问题。另一个挑战是，在任何给定的数据批次中，随着数据下沉到树中，样本数量呈指数级减少。因此，估计的概率在树的更深层次上准确性进一步降低。Frosst 等人建议通过使用时间窗口对实际概率的移动平均进行衰减，该窗口指数级地与节点深度成正比 [128]。尽管作者报告该模型的准确性低于深度神经网络，但该模型提供了概念可解释性的优势。

DNDF 和软决策树都将学习到的树的深度固定为预定义的值。相比之下，Tanno 等人 [129] 引入了自适应神经树（ANT），该树可以生长到任意深度。ANT 架构类似于决策树，但在每个内部节点和边上，ANT 学习新的数据表示。例如，一个 ANT 可能在每个内部节点包含一个或多个卷积层，然后是一个全连接层，在每个边上包含一个或多个卷积层，随后是一个激活函数，如 ReLU 或 tanh，以及在每个叶子节点的线性分类器。

训练 ANT 需要两个阶段：生长和精化。在生长阶段，从根节点开始，以广度优先的顺序选择一个节点。然后，学习者评估三个选择：1) 切分节点并添加子树，2) 通过添加另一层卷积来加深边缘转换，或 3) 保持当前模型。模型通过梯度下降最小化对数似然来优化新添加组件的参数，同时固定树的先前部分的参数。最终，模型选择具有最低对数似然的选择。这个过程重复进行，直到模型收敛。在精化阶段，模型对最终架构执行梯度下降。精化阶段的目的是纠正生长阶段可能发生的次优决策。作者在多个标准测试集上评估了他们的方法，结果表明 ANT 在这些任务中与许多深度网络和非网络学习者具有竞争力。

杨等人 [130] 采取了不同的方法；他们没有将人工神经元集成到树中，而是使用神经网络获得了决策树。深度神经决策树（DNDT）采用软分箱函数来学习树的分裂规则。DNDT 构建了一个一层神经网络，使用 softmax 作为其激活函数。该网络的目标函数为：

|  | $\text{softmax}\big{(}\frac{wx+b}{\tau}\big{)}.$ |  | (18) |
| --- | --- | --- | --- |

在这里，对于连续变量 $x$，我们希望将其分箱为 $n+1$，$w=[1,2,\cdots,n+1]$ 是一个不可训练的常数，$b$ 是一个可学习的箱子或树中的切分规则，$\tau$ 是一个温度变量。训练此模型后，决策树通过 Kronecker 积 $\otimes$ 构造。给定一个具有 $D$ 个特征的输入 $x\in R^{D}$，到达叶子节点的树规则为：

|  | $z=f_{1}(x_{1})\otimes f_{2}(x_{2})\otimes\cdots\otimes f_{D}(x_{D})$ |  | (19) |
| --- | --- | --- | --- |

在这里，$z$ 是一个几乎一热编码的向量，指示叶子节点的索引。这种方法的一个缺点是无法处理高维数据集，因为计算 Kronecker 积的成本变得过于昂贵。为了解决这个问题，作者通过在特征的随机子集上训练每棵树来学习分类器森林。

在某些情况下，映射函数不可微分。Feng 等人 [131] 提出了一个新的学习范式来训练多层梯度提升决策树 (mGBDT) [131]，其中 $F_{i}$ 是不可微分的。梯度提升决策树 (GBDT) 是一种迭代方法，它学习一个回归预测器的集成。在 GBDT 中，决策树首先在训练集上学习一个模型，然后计算每个训练样本的相应误差残差。一个新树在误差残差上学习一个模型，通过结合这两棵树，GBDT 能够学习一个更复杂的模型。该算法按照此过程迭代，直到满足预设的训练树的数量。

由于梯度下降不适用于 mGBDT，Feng 等人 [131] 获取了一个“伪逆”映射。在这个映射中，$G^{t}_{i}$ 代表第 $t$ 次迭代中 $F^{t-1}_{i}$ 的伪逆，使得 $G^{t}_{i}(F^{t-1}_{i}(o_{i-1}))\sim o_{i-1}$。在执行反向传播并计算 $G^{t}_{i}$ 后，通过从 $G^{t}_{i}$ 拟合伪标签 $z^{t}_{i-1}$ 到 $F^{t-1}_{i}$ 来执行前向传播。最后一层 $F_{m}$ 根据第 $t$ 次迭代中的真实标签计算 $z^{t}_{m}$，其中 $i\in\{2\ldots m\}$。在此步骤之后，通过伪逆映射计算前层的伪标签。为了在第 $t=0$ 次迭代中初始化 mGBDT，每个中间（隐藏）层输出高斯噪声，$F^{0}_{i}$ 代表将来会被细化的深度约束树。因此，Feng 等人 [131] 创造了一种受梯度下降启发但适用于无法有效应用真正梯度下降的情况的方法。

在这一部分，我们探讨了将梯度下降应用于非网络模型的方法。正如我们所观察到的，利用梯度下降的一种方式是用像 SVM 这样的可微分算法替代网络中的隐藏单元。另一个我们认识到的常见主题是将确定性决策树节点转变为提供更大表征能力的随机版本。或者，也可以使用神经网络构建树或其他基于规则的模型。

## 5 深度学习在深度神经网络之外的正则化

我们在第 2.6 节中讨论了 DNNs 使用的一些常见正则化方法。现在我们关注这些方法如何在文献中应用于非网络分类器。值得一提的是，尽管本节介绍的大多数模型不是深度模型，但我们研究了非网络模型如何通过应用通常与 DNNs 中深度操作相关的正则化方法来提高其性能。

### 5.1 参数范数惩罚

当从包含大量冗余特征的数据中学习模型时，会出现问题。例如，选择与不同类型癌症相关的基因具有挑战性，因为基因的长特征字符串中可能存在大量冗余。消除冗余特征的两种常见方法是：第一种方法是执行特征选择，然后从选定的特征中训练分类器；第二种方法是同时执行特征选择和分类。在第 2.6.1 节中，我们讨论了 DNNs 应用$L_{1}$或$L_{2}$惩罚函数来惩罚大权重。在本节中，我们研究了如何将传统 DNN 惩罚特征的思想应用于非网络分类器，以同时选择高排名特征并执行分类。

标准支持向量机（SVM）采用$L_{2}$范数惩罚来惩罚权重，这与深度神经网络（DNNs）类似。然而，牛顿线性规划支持向量机（NLP-SVM）[132]用$L_{1}$范数惩罚替代了$L_{2}$范数惩罚。这种方法的效果是将小的超参数系数设为零，从而使 NLP-SVM 能够自动选择重要特征。另一种惩罚不重要特征的方式是使用平滑剪切绝对偏差（SCAD）[133]函数。$L_{1}$惩罚函数可能存在偏差，因为它对大系数施加了更大的惩罚；相比之下，SCAD 可以对大系数提供几乎无偏的估计。SCAD 学习了一个非凸的惩罚函数，如方程 20 所示。

|  | <math alttext="p_{\lambda}(&#124;w&#124;)=\begin{cases}\lambda&#124;w&#124;&amp;\text{if }&#124;w&#124;\leq\lambda\\ -\frac{(&#124;w&#124;^{2}-2a\lambda&#124;w&#124;+\lambda^{2})}{2(a-1)}&amp;\text{if }\lambda<&#124;w&#124;\leq a\lambda\\

\frac{(a+1)\lambda^{2}}{2}&amp;\text{如果 }&#124;w&#124;>a\lambda\end{cases}" display="block"><semantics ><mrow  ><mrow ><msub ><mi  >p</mi><mi >λ</mi></msub><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><mrow  ><mo stretchy="false"  >&#124;</mo><mi >w</mi><mo stretchy="false" >&#124;</mo></mrow><mo stretchy="false" >)</mo></mrow></mrow><mo  >=</mo><mrow ><mo  >{</mo><mtable columnspacing="5pt" displaystyle="true" rowspacing="0pt" ><mtr  ><mtd columnalign="left"  ><mrow ><mi >λ</mi><mo lspace="0em" rspace="0em" >​</mo><mrow ><mo stretchy="false" >&#124;</mo><mi >w</mi><mo stretchy="false" >&#124;</mo></mrow></mrow></mtd><mtd columnalign="left"  ><mrow ><mrow  ><mtext >如果 </mtext><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >&#124;</mo><mi >w</mi><mo stretchy="false" >&#124;</mo></mrow><mo >≤</mo><mi >λ</mi></mrow></mtd></mtr><mtr ><mtd  columnalign="left" ><mrow  ><mo >−</mo><mstyle displaystyle="false" ><mfrac ><mrow  ><mo stretchy="false"  >(</mo><mrow ><mrow ><msup ><mrow ><mo stretchy="false"  >&#124;</mo><mi >w</mi><mo stretchy="false"  >&#124;</mo></mrow><mn >2</mn></msup><mo >−</mo><mrow ><mn >2</mn><mo lspace="0em" rspace="0em"  >​</mo><mi >a</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >λ</mi><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false"  >&#124;</mo><mi >w</mi><mo stretchy="false"  >&#124;</mo></mrow></mrow></mrow><mo >+</mo><msup ><mi >λ</mi><mn >2</mn></msup></mrow><mo stretchy="false"  >)</mo></mrow><mrow ><mn >2</mn><mo lspace="0em" rspace="0em" >​</mo><mrow ><mo stretchy="false" >(</mo><mrow ><mi >a</mi><mo >−</mo><mn >1</mn></mrow><mo stretchy="false" >)</mo></mrow></mrow></mfrac></mstyle></mrow></mtd><mtd columnalign="left"  ><mrow ><mrow ><mtext  >如果 </mtext><mo lspace="0em" rspace="0em"  >​</mo><mi >λ</mi></mrow><mo ><</mo><mrow ><mo stretchy="false" >&#124;</mo><mi >w</mi><mo stretchy="false" >&#124;</mo></mrow><mo >≤</mo><mrow  ><mi >a</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >λ</mi></mrow></mrow></mtd></mtr><mtr ><mtd columnalign="left"  ><mstyle displaystyle="false"  ><mfrac ><mrow ><mrow ><mo stretchy="false" >(</mo><mrow ><mi >a</mi><mo >+</mo><mn >1</mn></mrow><mo stretchy="false" >)</mo></mrow><mo lspace="0em" rspace="0em"  >​</mo><msup ><mi >λ</mi><mn >2</mn></msup></mrow><mn >2</mn></mfrac></mstyle></mtd><mtd columnalign="left"  ><mrow ><mrow  ><mtext >如果 </mtext><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >&#124;</mo><mi >w</mi><mo stretchy="false" >&#124;</mo></mrow></mrow><mo >></mo><mrow ><mi  >a</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >λ</mi></mrow></mrow></mtd></mtr></mtable></mrow></mrow><annotation-xml encoding="MathML-Content" ><apply  ><apply ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑝</ci><ci  >𝜆</ci></apply><apply ><ci >𝑤</ci></apply></apply><apply ><csymbol cd="latexml"  >cases</csymbol><apply ><ci >𝜆</ci><apply ><ci  >𝑤</ci></apply></apply><apply ><apply ><ci  ><mtext >如果 </mtext></ci><apply ><ci >𝑤</ci></apply></apply><ci >𝜆</ci></apply><apply ><apply  ><apply ><apply ><apply ><csymbol cd="ambiguous"  >superscript</csymbol><apply ><ci >𝑤</ci></apply><cn type="integer"  >2</cn></apply><apply ><cn type="integer"  >2</cn><ci >𝑎</ci><ci >𝜆</ci><apply ><ci >𝑤</ci></apply></apply></apply><apply ><csymbol cd="ambiguous"  >superscript</csymbol><ci >𝜆</ci><cn type="integer"  >2</cn></apply></apply><apply ><cn type="integer" >2</cn><apply ><ci >𝑎</ci><cn type="integer"  >1</cn></apply></apply></apply></apply><apply ><apply ><apply  ><ci ><mtext >如果 </mtext></ci><ci >𝜆</ci></apply><apply ><ci  >𝑤</ci></apply></apply><apply ><apply ><ci  >𝑎</ci><ci >𝜆</ci></apply></apply></apply><apply ><apply ><apply ><ci >𝑎</ci><cn type="integer" >1</cn></apply><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝜆</ci><cn type="integer" >2</cn></apply></apply><cn type="integer" >2</cn></apply><apply ><apply ><ci  ><mtext >如果 </mtext></ci><apply ><ci >𝑤</ci></apply><apply ><ci  >𝑎</ci><ci >𝜆</ci></apply></apply></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" >p_{\lambda}(&#124;w&#124;)=\begin{cases}\lambda&#124;w&#124;&\text{如果 }&#124;w&#124;\leq\lambda\\ -\frac{(&#124;w&#124;^{2}-2a\lambda&#124;w&#124;+\lambda^{2})}{2(a-1)}&\text{如果 }\lambda<&#124;w&#124;\leq a\lambda\\ \frac{(a+1)\lambda^{2}}{2}&\text{如果 }&#124;w&#124;>a\lambda\end{cases}</annotation></semantics></math> |  | (20) |

SCAD 与 $L_{1}$ 惩罚函数等效，直到 $|w|=\lambda$，然后平滑过渡到二次函数，直到 $|w|=a\lambda$，之后对所有 $|w|>a\lambda$ 保持不变。如 Fan 等人所示 [134]，SCAD 比 $L_{1}$ 函数具有更好的理论性质。

决策树分类器的一个限制是，随着树的深度增加，每个分支上可以选择的训练实例数量会减少。这种向下采样可能导致在树的底部选择较少相关或冗余的特征。为了解决这个问题，Dang 等人 [135] 提出了对在构建树的过程中从未被选择的特征施加惩罚。在一个 Regularized Random Forest (RRF) [135] 中，特征 $j$ 的信息增益被指定如下：

|  | $Gain(j)=\begin{cases}\lambda.Gain(j)&amp;\text{$j\not\in F$}\\ Gain(f_{i})&amp;\text{$j\in F$}\end{cases}$ |  | (21) |
| --- | --- | --- | --- |

其中 $F$ 是路径中早期使用的特征集，$f_{i}\in F$，而 $\lambda\in[0,1]$ 是惩罚系数。RRF 避免包含新特征 $j$，除非 $Gain(j)$ 的值大于 $\max\limits_{i}\big{(}Gain(f_{i})\big{)}$。

为了改进 RRF，Guided RRF (GRRF) [136] 为每个特征分配不同的惩罚系数 $\lambda_{j}$，而不是为所有特征分配相同的惩罚系数。GRRF 利用在训练集上预训练 RF 的重要性评分来优化在特定节点的特征选择。特征 $j$ 在一个具有 $T$ 棵树的 RF 中的重要性评分是 RF 中特征增益的均值。重要性评分评估特征对预测类别的贡献。GRRF 使用归一化的重要性评分来控制惩罚系数的正则化程度，如下所示：

|  | $\lambda_{j}=(1-\gamma)\lambda_{0}+\gamma Imp^{\prime}_{j},$ |  | (22) |
| --- | --- | --- | --- |

其中 $\lambda_{0}\in(0,1]$ 是基础惩罚系数，$\gamma\in[0,1]$ 控制归一化重要性评分的权重。GRRF 和 RRF 是计算开销小的方法，能够选择更强的特征并避免冗余特征。

### 5.2 Dropout

如第 2.6.2 节所述，dropout 是一种通过在训练过程中随机丢弃节点来防止 DNN 过拟合的方法。Dropout 可以通过两种方法添加到其他机器学习算法中：通过丢弃特征或在集成方法的情况下丢弃模型。Dropout 也被应用于通过丢弃输入特征进行训练 [137] [138]。在这里，我们查看了为丢弃输入特征而研究的技术，特别是在非网络分类器中。

Rashmi 等人[139]将 dropout 应用于多个加性回归树（MART）[140] [141]。MART 是一种回归树集成，通过不断添加拟合损失函数导数的树来迭代地完善模型。由于后期添加的树可能仅对训练集的一个小部分产生影响，因此可能过度特化，研究人员之前使用了收缩来排除在每次添加树的步骤中随机选择的一部分叶节点。最近，Rashmi 等人将深度学习中的 dropout 思想整合到 MART 中。通过使用 dropout，临时丢弃部分树。基于丢弃树的损失函数创建新树。将这棵新树与之前丢弃的树组合成一个新的集成。这种方法，即 Dropout Multiple Additive Regression Trees（DART）[139]，将新树和重新整合树的投票权重调整到与原始树集相同的效果。其他研究人员也尝试了永久性移除丢弃树的策略子集[142]。

### 5.3 早停

早停的核心概念是当验证集上的性能不再提升时终止 DNN 训练。与 DNNs 相比，Deep Forest [93]的一个潜在优势是 DF 可以自动确定模型的深度。在 DF 中，如果在添加新层后模型性能在验证集上没有提升，则学习终止。与 DNNs 不同，DF 可能避免了随着层数增加而过拟合的趋势。因此，虽然早停不一定能主要防止这种过拟合，但它可以提供额外的好处，如缩短在搜索最佳树深度过程中的验证周期。

### 5.4 数据增强

如第 2.6.3 节所讨论的，数据增强是提高 DNN 泛化能力的强大方法。然而，关于数据增强方法对非网络分类器影响的研究很少。正如 Wong 等人[143]所示，SVM 分类器并不总是能从数据增强中受益，这与 DNNs 不同。然而，Xu[144]对合成数据集进行了几次数据增强实验，并观察到数据增强确实提升了随机森林分类器的性能。解释在何种情况下这种增强是有益的，是未来研究需要探讨的领域。

## 6 混合模型

混合模型可以定义为两种或多种类别模型的组合。有许多方法来构建混合模型，例如 DNDF [127]，它将深度网络集成到决策森林中，如第四部分所解释。在本节中，我们讨论其他混合模型的示例。

结合多种模型的一个动机是为了在分类准确性和计算成本之间找到平衡。移动设备和云服务器的能耗对响应式应用程序和绿色计算日益成为关注点。决策森林由于决策树的条件属性，计算成本低廉。相对而言，尽管卷积神经网络（CNN）效率较低，但由于其表示学习能力，它们能够实现更高的准确性。Ioannou 等人[145] 引入了条件神经网络（CondNN），通过引入类似于决策树的路由方法来减少 CNN 模型中的计算。在 CondNN 中，层 $l$ 中的每个节点连接到上一层 $l-1$ 的一个子集节点。给定一个完全训练好的网络，对于每两个连续层，矩阵 $\Lambda_{(l-1,l)}$ 存储这两层的激活值。通过根据对角线中每个类别的高活跃对来重新排列 $\Lambda_{(l-1,l)}$ 的元素，并将非对角线元素置零，CondNN 通过网络中的节点开发出明确的路由 $\Lambda_{(l,l-1)}^{route}$。与其他深度神经网络（DNN）相比，CondNN 在测试时的计算成本显著降低；而且，CondNN 的准确性保持与更大模型相似。我们注意到，通过使用贝叶斯优化（如 Blundell 等人[146] 和 Fortunato 等人[147] 研究的那样），DNN 的规模也可以被缩小。这些早期的努力提供了证据，表明贝叶斯神经网络能够在保持类似准确性水平的同时进一步减小网络规模。

将深度网络与非网络分类器融合的另一个方向是通过深度网络学习更好的数据表示来改进非网络模型。Zoran 等人[148]引入了可微分边界树（DBT），以将 DNN 集成到边界树中[149]，以学习更好的数据表示。新学到的数据表示导致了更简单的边界树，因为类别被很好地分开。边界树是一种在线算法，其中树中的每个节点对应于训练集中的一个样本。第一个样本及其标签被确立为树根。给定一个新的查询样本$z$，样本从根节点开始遍历树，以基于欧几里得距离函数等某种距离函数找到最接近的节点$n$。如果树中最近节点的标签与查询样本不同，则将包含查询$z$的新节点作为树中最接近节点$n$的子节点添加；否则，查询节点$z$被丢弃。因此，树中的每条边标记了两个类别之间的边界，每个节点趋向于接近这些边界。

标准边界树中的节点之间的转换是确定性的。DBT 将 SoftMax 成本函数与边界树结合，导致随机转换。设$x$为训练样本，$c$为该样本的独热编码标签。给定树中的当前节点$x_{i}$和查询节点$z$，从节点$x_{i}$到节点$x_{j}$的转换概率，其中$x_{j}\in\{child(x_{i}),x_{i}\}$是$x_{j}$与$z$之间负距离的 SoftMax。这在方程 23 中展示。

|  | $\begin{gathered}p(x_{i}\rightarrow x_{j}\mid z)=\underset{i,j\in child(i)}{\operatorname{SoftMax}}(-d(x_{j},z))\\ =\frac{\exp(-d(x_{j},z))}{\underset{j^{\prime}\in\{i,j\in child(i)\}}{\sum}\exp(-d(x_{j},z))}\end{gathered}$ |  | (23) |
| --- | --- | --- | --- |

给定查询节点$z$，边界树中遍历特定路径的概率是从根节点到最终节点$x_{final^{*}}$沿路径每个转换概率的乘积。DBT 的最终类别对数概率是通过将所有转移到$x_{final^{*}}$的父节点的概率与最终节点及其兄弟节点的概率相加来计算的。集合$sibling(x_{i})$由所有与节点$x_{i}$共享相同父节点的节点以及节点$x_{i}$本身组成。如前所述，DNN $f_{\theta}(x)$转换输入以学习更好的表示。查询节点$z$的最终类别对数概率计算如下：

|  | $\begin{gathered}\log p(c | f_{\theta}(z))=\smashoperator[]{\sum_{x_{i}\rightarrow x_{j}\in path^{\dagger} | f_{\theta}(z)}^{}}\log p(f_{\theta}(x_{i})\rightarrow f_{\theta}(x_{j}) | f_{\theta}(z))\\ +\log\smashoperator[]{\sum_{x_{k}\in sibling(x_{final^{*}})}^{}}p(parent(f_{\theta}(x_{k}))\rightarrow f_{\theta}(x_{k}) | f_{\theta}(z))c(x_{k}).\end{gathered}$ |  | (24) |
| --- | --- | --- | --- | --- | --- | --- | --- |

在方程 24 中，$path^{\dagger}$ 表示 $path^{*}$（到最终节点 $x_{final^{*}}$ 的路径）但不包括最后一个过渡，$sibling(x)$ 表示节点 $x$ 以及所有与节点 $x$ 共享相同父节点的其他节点。梯度下降算法可以通过插入损失函数来学习 DNN 的参数 $\theta$，从而应用于方程 24。然而，由于图中的节点和边操作，梯度下降不能轻易应用于 DBT。为了解决这个问题，DBT 通过 DNN 转换一小部分训练样本，并基于转换后的样本构建边界树。接下来，DBT 通过相同的 DNN 转换查询节点 $z$，并根据方程 24 计算类别的对数概率。DNN 使用梯度下降来更新其参数，通过传播对数损失概率的梯度来实现。DBT 丢弃这个边界树，并按照描述的方式迭代构建新的边界树，直到满足收敛标准。在所描述的方法中，作者设定了一个特定的损失值阈值以终止训练。DBT 能够在 MNIST 数据集上以比原始边界树更简单的树实现更高的准确性[97]。DBT 的最大优势之一是其可解释性。然而，DBT 是一个计算成本较高的方法，因为需要构建新的计算图，这使得批处理效率低下。另一个限制是算法需要在构建树和更新树之间切换。因此，扩展到大型数据集相当困难。

构建混合模型的另一种方法是使用 DNN 学习数据的新表示，然后将结果特征向量交给其他分类器进行建模。Tang [150] 探索了用线性 SVM 替换 DNN 的最后一层以进行分类任务。倒数第二层的激活值作为输入传递给带有 $L_{2}$ 正则化器的 SVM。通过对倒数第二层激活值对 SVM 目标函数进行求导，低层的权重通过动量梯度下降进行学习。作者在 MNIST [97] 和 CIFAR-10 [151] 数据集上的实验表明，将 CNN 的 SoftMax 输出层替换为 SVM 可以降低测试误差。Tang 等人 [150] 认为性能提升是由于 SVM 损失函数具有更优的正则化效果。

值得一提的是，在他们对 MNIST 的实验中 [97]，Tang 首先使用 PCA 来减少特征，然后将减少后的特征向量作为输入提供给他们的模型。此外，Niu 等人 [152] 将 CNN 的最后一层替换为 SVM，这同样导致了与 CNN 相比在 MNIST 数据集上降低了测试误差。类似于这些方法，Zareapoor 等人 [153]、Nagi 等人 [154]、Bellili 等人 [155] 和 Azevedo 等人 [156] 将 DNN 的最后一层替换为 SVM。在这些情况下，他们在多个数据集上的结果表明，将 SVM 作为神经网络的最后一层可以提高网络的泛化能力。

Zhao 等人 [157] 将深度网络的最后一层替换为视觉层次树，以寻找更好的图像分类解决方案。一个具有 $L$ 层的视觉层次树根据视觉相似性在其节点中组织 $N$ 个对象类别。树越深，组之间的分隔越明显，其中每个叶节点应包含一个类别的实例。类别 $c_{i}$ 和 $c_{j}$ 之间的类别相似性定义如下：

|  | $S_{i,j}=S(c_{i},c_{j})=\exp\Big{(}-\frac{d(x_{i},x_{j})}{\sigma}\Big{)}.$ |  | (25) |
| --- | --- | --- | --- |

在这里，$d(x_{i},x_{j})$ 代表了类别 $c_{i}$ 和 $c_{j}$ 实例深度表示之间的距离，而 $\sigma$ 由自调整技术自动确定。在计算矩阵 $S$ 后，采用层次聚类来学习一个视觉层次树。

在传统的视觉层次树中，一些对象可能会被分配到错误的组。级别混合模型（LMM）[157] 旨在通过通过 DNN 学习数据的新表示来改进这个视觉层次树，然后在训练过程中更新树。对于给定的树，矩阵 $\Psi_{y_{i},t_{i}}$ 表示标签 $y$ 的对象属于树中组 $t$ 的概率。首先，LMM 更新 DNN 参数和视觉层次树，与传统的 DNN 做法相同。唯一的区别在于计算两个梯度，一个基于 DNN 的参数，另一个基于树的参数。其次，LMM 分别为每个训练样本更新矩阵 $\Psi_{y_{i},t_{i}}$，然后更新 DNN 和树的参数。为了更新 $\Psi$，计算对象 $x_{i}$ 分配组 $t_{i}$ 的后验概率，基于在组 $t$ 中具有与 $x_{i}$ 相同标签 $y$ 的样本数量。对于给定的测试图像，LMM 基于 DNN 学习图像的新表示，然后通过遍历树来获得预测。LMM 的一个优点是，随着时间的推移，通过 DNN 学习更好的数据表示，算法可以更新视觉层次树。

在某些情况下，可以使用两种不同的数据视图。例如，一种视图可能包含视频，另一种视图可能包含声音。典型相关分析（CCA）[158] 和核典型相关分析（KCCA）[159] 提供了学习视图表示的标准统计方法，每种方法都能使另一种视图最具可预测性。KCCA 学习的非线性表示可以比 CCA 学习的线性表示达到更高的相关性。尽管 KCCA 有其优势，但核函数也面临一些缺陷。具体来说，表示受限于固定的核。此外，由于模型是非参数的，训练时间以及计算新数据表示的时间会随着训练集大小的增加而显著增长。

Andrews 等人 [160] 提出了应用深度网络来学习非线性数据表示，而不是使用核函数。他们提出的深度典型相关分析（DCCA）由两个独立的深度网络组成，用于学习每个视图的新表示。由网络最终层 $H_{1}$ 和 $H_{2}$ 学习的新表示被输入到 CCA 中。为了计算 DCCA 的目标梯度，可以按以下方式计算相关目标输出相对于新表示的梯度：

|  | $\frac{\partial_{corr}(H_{1},H_{2})}{\partial H_{1}}$ |  | (26) |
| --- | --- | --- | --- |

在此计算之后，应用反向传播来找到所有参数的梯度。关于公式 26 中梯度计算的详细信息由作者 [160] 提供。

尽管研究人员还创建了利用树结构的 LSTM 方法 [161] [162]，但这些方法利用数据结构来改善网络模型，而不是采用基于树的学习算法。类似地，其他研究将非网络分类器整合到网络结构中。Cimino 等 [163] 和 Agarap [164] 引入了混合模型。这两种方法分别应用 LSTM 和 GRU 来学习网络表示。与传统的 DNN 不同，最后一层使用 SVM 进行分类。

本节调查的工作提供了证据表明，深度神经网络是学习高层特征的有效方法。这些特征反过来可以用于提高多种类型监督分类器的建模能力。

表 1：将深度网络组件整合到非网络分类器中的分类器总结。

|  | 方法 | 分类器 |
| --- | --- | --- |
| 架构 | 前馈 | ANT [129]，DNDT [130]，DBN [45]，深度 PCA [105]，DF [93]，DPG [116]，R2-SVM [101]，D-SVM [100]，DTA-LS-SVM [94]，SFDT [128] |
| 自编码器 | DKF [122]，eForest [125]，ML-SVM [126] |
| 孪生模型 | SDF [119] |
| 生成对抗模型 | GAF [120] |
| 优化 | 梯度下降 | DNDF [127]，mGBDT [131]，ML-SVM [126] |
| 正则化 | 参数范数惩罚 | NLP-SVM [132]，GRRF [136]，RRF [135]，SCAD-SVM [133] |
| Dropout | DART [139] |
| 混合模型 |  | CondCNN [145]，DBT [148]，DCCA [160]，DNDF [127]，DNN+SVM [150] [152] [153] [154] [155] [156]，LMM [157] |

在本调查中，我们旨在提供对利用深度网络模型独特特征的非网络模型的全面评估。表 1 总结了这些非网络模型，基于深度网络的四个方面：模型架构、优化、正则化和混合模型融合。与非网络模型相比，传统深度网络的已知优势是能够学习到更好的输入特征表示。受各种深度网络架构的启发，非网络分类器的深度学习也产生了学习新特征表示的方法。非网络分类器受益于最近深度网络研究的另一个领域是应用反向传播优化以提高泛化能力。该表总结了应用正则化技术以提高神经网络泛化能力的已发布工作。最后一类模型结合了深度网络分类器和非网络分类器，以提高整体性能。

## 7 实验

在本文中，我们调查了各种模型和方法。我们的目标是展示不同类型的模型如何从深度学习技术中受益。为了突出这一点，我们实证比较了本调查中描述的许多技术的性能。这一比较包括深度和浅层网络以及非网络学习算法。由于调查了各种分类器，我们基于学习到的模型结构组织了比较。

首先，我们比较了与 DNN 最相似的模型。这些模型应能在大型数据集可用时学习到更好的数据表示。我们在表 2 中报告了作者提供的 MNIST 和 CIFAR-10 数据集的测试错误。如果某些数据集的模型性能不可用，我们使用作者的代码进行了实验。对于原论文中未指定的参数值，采用默认参数。如果作者未提供代码，我们未报告任何结果。这些遗漏避免了由于实现差异导致的错误性能报告。

MNIST 数据集在计算机视觉和深度网络社区中一直是比较模型选择的热门测试数据集。MNIST 实例包含$28\times 28$像素的手写数字灰度图像及其标签。MNIST 标签来自 10 个对象类别，共有 6000 个训练样本和 1000 个测试样本。CIFAR-10 也是一个著名的数据集，包含 10 个对象类别，每个类别大约有 5000 个样本，每个样本是$32\times 32$像素的 RGB 图像。

表 2：分类错误率（%）比较。

| 数据集/模型 | RF | ANT$\dagger$ [129] | DF [93] | R2SVM [101] | SFDT [128] | DNDF [127] | CondCNN [145] | DBT [148] | DNN+SVM [150] |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| MNIST | 3.21 | 0.29 | 0.74 | 4.03^∗ | 5.55 | 0.7 | - | 1.85 | 0.87 |
| CIFAR-10 | 50.17 | 7.71 | 31.0 | 20.3 | - | - | 10.12 | 13.06 | 11.9 |

+   •

    * 基于作者的代码。

+   •

    $\dagger$ 报告的结果反映了一个 ANT 集成模型。

在下一组实验中，我们比较了设计用于处理小型或结构化数据集的模型，如表 3 所示。这些方法的作者测试了广泛的数据集来评估他们的方法。在这项调查中，我们在 UCI 人类活动识别（HAR）数据集[165]上进行了一系列实验。这里的人类活动识别数据是从 30 名参与者在进行六种预设活动（步行、上楼、下楼、坐着、站着和躺着）时收集的，参与者佩戴了智能手机。数据集包含从传感器（包括加速度计和陀螺仪）提取的 561 个特征。训练集包含来自 70%志愿者的 7352 个样本，测试集包含来自剩余 30%志愿者的 2947 个样本。

表 3：分类错误率（%）比较。

| 数据集/模型 | RF | SVM | MLP | DART [139] | RRF [135] | GRRF [136] | mGBDT [131] |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HAR | 6.96 | 4.69 | 4.69 | 6.55 | 3.77 | 3.74 | 7.68 |

从表中可以看出，代表多层机器学习模型的模型，如 DF、R2SVM 和 mGBDT，在 MNIST 和 CIFAR-10 数据集上的表现不佳。与 DNNs 相比，这些模型计算开销更大，需要过多的资源，而且不具备可解释性的优势。

另一类模型利用神经网络来学习更好的数据表示。这些模型，如 DNDF 和 DNN+SVM，在新学习的表示上应用了更传统的机器学习模型。当神经网络在大型数据集上进行训练时，这种技术可能会有益。例如，DNDF 利用 GoogLeNet 提取特征，并在 ImageNet 测试集上实现了 $6.38\%$ 的错误率。相比之下，GoogLeNet 的错误率为 $10.02\%$。另一类模型通过整合人工神经元（如 ANT、SFDT 和 DBT）来增强树模型。这些模型巧妙地将神经网络与决策树结合，改善了解释性，同时提供了表示学习的好处。

另一种混合策略专注于降低深度神经网络（DNNs）的计算复杂度。CondCNN 是一种神经网络，它采用类似于决策树的路由机制来实现这一目标。另一条成功的研究方向是将神经网络中常用的正则化器添加到类似于 DART、RRF 和 GRRF 的其他分类器中。

我们实验的结果表明，网络分类器和非网络分类器都从深度学习中受益。本文调查并在这些实验中评估的方法表明，通过将 DNN 组件融入算法中，非网络机器学习模型的性能确实得到了提升。尽管没有特征学习的模型（如 RF）通常在非结构化数据（如图像）上表现不佳，但我们观察到，将深度学习添加到这些模型中能显著提高其性能，如表 2 所示。此外，通过添加正则化器，非深度模型在结构化数据上的性能也可能得到改善，如表 3 所示。本文调查的方法表明，深度学习组件可以添加到任何类型的机器学习模型中，并非特定于 DNNs。深度学习策略的融入是所有类型分类器（包括网络方法和非网络方法）的一个有前景的方向。

## 8 结论和正在进行的研究方向

DNN（深度神经网络）在过去几年中已经成为机器学习领域中的一股强大力量。本文综述了将传统上存在于 DNN 中的方法融入其他学习算法的最新尝试。DNN 在拥有大量训练数据和计算能力时表现良好。DNN 在各种数据集和竞赛中 consistently yield 强劲的结果，例如赢得了大规模视觉识别挑战赛[166]，在能源需求预测[167]、文本作者性别识别[168]、中风预测[169]、网络入侵检测[170]、语音情感识别[171]和出租车目的地预测[172]中也取得了优异的成绩。由于许多应用缺乏大量的训练数据，或需要可解释性强的学习模型，因此有必要将 DNN 的优势与其他分类算法结合起来。其他分类器在某些数据类型上的表现有所改善，因此该领域可以通过研究将深度学习元素与网络及非网络方法相结合的方式来受益。

尽管迄今为止一些工作提供了 DNN 技术可以被其他分类器有效使用的证据，但研究人员仍需解决许多挑战，以改善 DNN 并将深度学习扩展到其他类型的分类器。基于我们对现有工作的调查，下面列出了监督学习者可以从独特的 DNN 方法中受益的一些相关领域。

DNN 最显著的特点是其深度架构以及学习数据新表示的能力。已经开发了各种堆叠泛化方法，使其他机器学习方法也能利用深度架构。这些方法结合了多个分类步骤，其中下一层的输入表示前一层输出与原始特征向量的串联，如 3.1.1 节中所讨论的那样。未来的工作可以探索许多其他可能性，以改善每一层输入特征，从而在每一层更好地区分每个类别的实例。

以往的研究提供了 DNN 作为有效数据生成器的证据[173] [174]，而在某些情况下，非网络分类器可能实际上是更好的区分器。未来的研究可以考虑在生成对抗模型中使用 DNN 作为生成器和其他分类器作为区分器。融入这种模型多样性可能会提高模型的鲁棒性。

梯度下降可以应用于任何可微分的算法。我们观察到 Kontschieder 等人[127]、Frosst 等人[128]、Tanno 等人[129]和 Zoran 等人[148]都通过使两种不同的基于树的算法可微分来应用梯度下降。未来，可以将其他分类器改造成可微分的。将梯度下降应用于其他算法可能是调整参数概率分布的有效方式。

另一个至关重要的研究领域是网络定制的正则化方法在非网络分类器中的应用。如在第五部分中讨论的那样，非网络分类器可以从 DNN 特有的正则化方法中受益。然而，这些正则化方法可以有多种不同的方式被非网络分类器适应，以提高模型的泛化能力。

一个重要的研究领域是可解释模型。由于其敏感性，像信用评分、保险风险、健康状态等应用需要模型具有可解释性。进一步的研究需要探索 DNN 在可解释模型中的应用，例如 DNDT[130]。

正如我们在本调查中讨论的那样，一个新兴的研究领域是结合统计模型与神经网络的互补优势。统计模型提供了数学形式以及可能的解释能力。这种结合可能提供比单独使用任何一种方法更有效的模型。

在一些情况下，真实标签数据量有限，但从相同或类似分布中可以获得大量标记数据。一个可能的研究方向是将用于从未标记数据中学习的 DNN 与用于从标记数据中学习的其他分类器策略相结合。从标记数据中学到的简单模型可以被利用来进一步调整和改进 DNN 中的学习表示模式。

我们观察到，目前机器学习社区普遍关注将新的深度网络发展转移到其他分类器中。虽然已经做了大量工作将深度学习思想融入一般机器学习领域，但继续这项工作可能会激发新的学习范式的产生。然而，基于网络的学习者和非网络学习者之间的好处是双向的。由于各种分类器在广泛的应用中表现优越，未来的研究可以不仅关注 DNN 技术如何改进非网络分类器，还可以关注 DNN 如何融合并受益于非网络学习思想。

表 4：本调查中使用的缩写及其描述列表。

| 缩写 | 描述 |
| --- | --- |
| AE | 自编码器 |
| ANT | 自适应神经树 |
| CNN | 卷积神经网络 |
| CondNN | 条件神经网络 |
| DART | Dropout 多重加法回归树 |
| DBT | 可微分边界树 |
| DBN | 深度信念网络 |
| DCCA | 深度典型相关分析 |
| Deep PCA | 深度主成分分析 |
| DF | 深度森林 |
| DGP | 深度高斯过程 |
| DKF | 深度卡尔曼滤波器 |
| DNDT | 深度网络决策树 |
| DNDF | 深度网络决策森林 |
| DNN | 深度神经网络 |
| DSVM | 深度支持向量机 |
| DTA-LS-SVM | 深度迁移加法核最小二乘支持向量机 |
| eForest | 编码森林 |
| FC | 全连接 |
| GAF | 生成对抗森林 |
| GAN | 生成对抗网络 |
| GRRF | 指导性正则化随机森林 |
| LMM | 层次混合模型 |
| mGBDT | 多层梯度决策树 |
| ML-SVM | 多层支持向量机 |
| MLP | 多层感知器 |
| NLP-SVM | 牛顿线性规划支持向量机 |
| R2-SVM | 随机递归支持向量机 |
| RBM | 限制玻尔兹曼机 |
| RNN | 循环神经网络 |
| RRF | 正则化随机森林 |
| SCAD-SVM | 平滑修剪绝对偏差支持向量机 |
| SDF | 孪生深度森林 |
| SNN | 孪生神经网络 |
| FSDT | Frosst 软决策树 |
| VAE | 变分自编码器 |

## 致谢

作者感谢 Tharindu Adikari、Chris Choy、Ji Feng、Yani Ioannou、Stanislaw Jastrzebski 和 Marco A. Wiering 在提供代码和额外算法实现细节方面的宝贵帮助。我们还感谢 Samaneh Aminikhanghahi 和 Tinghui Wang 对本调查中描述的方法的反馈和指导。该材料基于国家科学基金会 1543656 号资助的工作。

## 参考文献

+   [1] 凯德·梅茨。人工智能正在改变谷歌搜索，接下来是网络的其他部分，2016 年。

+   [2] 内森·西克斯。深度学习和搜索引擎优化的未来，2015 年。

+   [3] 亚历克斯·戴维斯。数字不会撒谎：自动驾驶汽车正在变得越来越好，2017 年。

+   [4] 尼尔·布代特。特斯拉的自动驾驶系统在致命车祸中被清除，2017 年。

+   [5] 自动驾驶汽车脱离报告 2017，2017 年。

+   [6] 费江、杨江、惠智、易东、郝力、苏峰马、易龙王、强东、海鹏申和永军王。医疗保健中的人工智能：过去、现在和未来。《中风与血管神经学》，2(4):230–243，2017 年。

+   [7] 梁切·陈和玉坤·朱。使用 DeepLab 进行 TensorFlow 中的语义图像分割，2018 年。

+   [8] 李万、马修·泽勒、思新·张、扬·勒昆和罗布·费格斯。利用 dropconnect 对神经网络进行正则化。在国际机器学习会议，页码 1058–1066，2013 年。

+   [9] 本杰明·格雷厄姆。分数最大池化。arXiv 预印本 arXiv:1412.6071，2014 年。

+   [10] Djork-Arné Clevert, Thomas Unterthiner, 和 Sepp Hochreiter. 通过指数线性单元（ELUs）实现快速准确的深度网络学习。arXiv 预印本 arXiv:1511.07289，2015 年。

+   [11] Karl Moritz Hermann, Tomas Kocisky, Edward Grefenstette, Lasse Espeholt, Will Kay, Mustafa Suleyman, 和 Phil Blunsom. 教导机器阅读与理解。发表于神经信息处理系统进展论文集，第 1693–1701 页，2015 年。

+   [12] Guillaume Lample, Miguel Ballesteros, Sandeep Subramanian, Kazuya Kawakami, 和 Chris Dyer. 命名实体识别的神经架构。arXiv 预印本 arXiv:1603.01360，2016 年。

+   [13] Dzmitry Bahdanau, Jan Chorowski, Dmitriy Serdyuk, Philemon Brakel, 和 Yoshua Bengio. 基于注意力机制的端到端大词汇量语音识别。发表于声学、语音与信号处理（ICASSP）2016 IEEE 国际会议论文集，第 4945–4949 页。IEEE，2016 年。

+   [14] Dario Amodei, Sundaram Ananthanarayanan, Rishita Anubhai, Jingliang Bai, Eric Battenberg, Carl Case, Jared Casper, Bryan Catanzaro, Qiang Cheng, Guoliang Chen 等人。Deep Speech 2：英中文语音识别的端到端方法。发表于国际机器学习会议论文集，第 173–182 页，2016 年。

+   [15] Yann LeCun, Yoshua Bengio, 和 Geoffrey Hinton. 深度学习。自然，521(7553)：436，2015 年。

+   [16] Thuy Ong. 亚马逊的新算法通过分析大量图片设计服装，2017 年。

+   [17] Chenghui Tang, Yishen Wang, Jian Xu, Yuanzhang Sun, 和 Baosen Zhang. 考虑空间和时间相关性的多个可再生能源电厂的高效情景生成。应用能源，221：348–357，2018 年。

+   [18] Rich Caruana, Yin Lou, Johannes Gehrke, Paul Koch, Marc Sturm, 和 Noemie Elhadad. 医疗领域的可解释模型：预测肺炎风险和医院 30 天再入院。发表于第 21 届 ACM SIGKDD 国际知识发现与数据挖掘大会论文集，第 1721–1730 页。ACM，2015 年。

+   [19] Anh Nguyen, Jason Yosinski, 和 Jeff Clune. 深度神经网络容易被欺骗：对不可识别图像的高置信度预测。发表于 IEEE 计算机视觉与模式识别会议论文集，第 427–436 页，2015 年。

+   [20] Chiyuan Zhang, Samy Bengio, Moritz Hardt, Benjamin Recht, 和 Oriol Vinyals. 理解深度学习需要重新思考泛化。arXiv 预印本 arXiv:1611.03530，2016 年。

+   [21] David Krueger, Nicolas Ballas, Stanislaw Jastrzebski, Devansh Arpit, Maxinder S Kanwal, Tegan Maharaj, Emmanuel Bengio, Asja Fischer, 和 Aaron Courville. 深度网络并非通过记忆来学习。2017 年。

+   [22] Dmytro Mishkin 和 Jiri Matas. 你需要的只是一个好的初始化。arXiv 预印本 arXiv:1511.06422，2015 年。

+   [23] Siddharth Krishna Kumar. 深度神经网络中的权重初始化问题。arXiv 预印本 arXiv:1704.08863，2017 年。

+   [24] Yoshua Bengio 等人. 学习深度架构用于人工智能。机器学习基础与趋势®，2(1)：1–127，2009 年。

+   [25] Christian Szegedy, Wei Liu, Yangqing Jia, Pierre Sermanet, Scott Reed, Dragomir Anguelov, Dumitru Erhan, Vincent Vanhoucke 和 Andrew Rabinovich. 深入卷积神经网络。收录于 IEEE 计算机视觉与模式识别会议论文集，页码 1–9, 2015。

+   [26] Yonghui Wu, Mike Schuster, Zhifeng Chen, Quoc V Le, Mohammad Norouzi, Wolfgang Macherey, Maxim Krikun, Yuan Cao, Qin Gao, Klaus Macherey 等. 谷歌的神经机器翻译系统：弥合人类和机器翻译之间的差距。arXiv 预印本 arXiv:1609.08144, 2016。

+   [27] Rafal Jozefowicz, Oriol Vinyals, Mike Schuster, Noam Shazeer 和 Yonghui Wu. 探索语言建模的极限。arXiv 预印本 arXiv:1602.02410, 2016。

+   [28] Alex Graves, Abdel-rahman Mohamed 和 Geoffrey Hinton. 使用深度递归神经网络进行语音识别。收录于 2013 IEEE 国际声学、语音和信号处理会议论文集，页码 6645–6649。IEEE, 2013。

+   [29] Shuiwang Ji, Wei Xu, Ming Yang 和 Kai Yu. 3D 卷积神经网络用于人体动作识别。IEEE 计算机学会模式分析与机器智能期刊，35(1):221–231, 2013。

+   [30] David H Wolpert, William G Macready 等. 优化的无免费午餐定理。IEEE 进化计算期刊，1(1):67–82, 1997。

+   [31] Ross D. King, Cao Feng 和 Alistair Sutherland. Statlog：大规模真实问题上分类算法的比较。应用人工智能国际期刊，9(3):289–333, 1995。

+   [32] Tjen-Sien Lim, Wei-Yin Loh 和 Yu-Shan Shih. 三十三种旧算法和新算法的预测准确性、复杂性和训练时间比较。机器学习，40(3):203–228, 2000。

+   [33] Rich Caruana 和 Alexandru Niculescu-Mizil. 监督学习算法的实证比较。收录于第 23 届国际机器学习会议论文集，页码 161–168。ACM, 2006。

+   [34] Rich Caruana, Nikos Karampatziakis 和 Ainur Yessenalina. 高维空间中监督学习的实证评估。收录于第 25 届国际机器学习会议论文集，页码 96–103。ACM, 2008。

+   [35] Philipp Baumann, DS Hochbaum 和 YT Yang. 领先的机器学习技术与两种新优化算法的比较研究。欧洲运筹学期刊，272(3):1041–1057, 2019。

+   [36] Samira Pouyanfar, Saad Sadiq, Yilin Yan, Haiman Tian, Yudong Tao, Maria Presa Reyes, Mei-Ling Shyu, Shu-Ching Chen 和 SS Iyengar. 深度学习综述：算法、技术和应用。ACM 计算机调查（CSUR），51(5):92, 2018。

+   [37] Benjamin Shickel, Patrick James Tighe, Azra Bihorac 和 Parisa Rashidi. 深度 EHR：电子健康记录（EHR）分析中深度学习技术的最新进展综述。IEEE 生物医学与健康信息学期刊，22(5):1589–1604, 2018。

+   [38] Junwei Han、Dingwen Zhang、Gong Cheng、Nian Liu 和 Dong Xu。《用于显著性和类别特定目标检测的先进深度学习技术：综述》。IEEE 信号处理杂志，35(1)：84–100，2018 年。

+   [39] Jindong Wang、Yiqiang Chen、Shuji Hao、Xiaohui Peng 和 Lisha Hu。《基于传感器的活动识别的深度学习：综述》。模式识别通讯，119：3–11，2019 年。

+   [40] William Grant Hatcher 和 Wei Yu。《深度学习调查：平台、应用和新兴研究趋势》。IEEE Access，6：24411–24432，2018 年。

+   [41] Frank Rosenblatt。《感知器：一种用于信息存储和组织的大脑概率模型》。心理学评论，65(6)：386，1958 年。

+   [42] Bernard Widrow 和 Marcian E Hoff。《自适应开关电路》。技术报告，斯坦福大学加州斯坦福电子实验室，1960 年。

+   [43] Marvin Minsky 和 Seymour A Papert。《感知器：计算几何导论》。MIT 出版社，1969 年。

+   [44] David E Rumelhart、Geoffrey E Hinton 和 Ronald J Williams。《通过误差传播学习内部表示》。技术报告，加州大学圣地亚哥分校 La Jolla 认知科学研究所，1985 年。

+   [45] Geoffrey E Hinton、Simon Osindero 和 Yee-Whye Teh。《深度信念网络的快速学习算法》。神经计算，18(7)：1527–1554，2006 年。

+   [46] Alex Graves、Greg Wayne 和 Ivo Danihelka。《神经图灵机》。arXiv 预印本 arXiv:1410.5401，2014 年。

+   [47] Sara Sabour、Nicholas Frosst 和 Geoffrey E Hinton。《胶囊之间的动态路由》。在 I. Guyon、U. V. Luxburg、S. Bengio、H. Wallach、R. Fergus、S. Vishwanathan 和 R. Garnett 主编的《神经信息处理系统进展 30》中，第 3856–3866 页。Curran Associates, Inc.，2017 年。

+   [48] Ian Goodfellow、Yoshua Bengio、Aaron Courville 和 Yoshua Bengio。《深度学习》，第 1 卷。MIT 出版社，剑桥，2016 年。

+   [49] Yann LeCun 等。《泛化和网络设计策略》。连接主义的视角，第 143–155 页，1989 年。

+   [50] Alex Krizhevsky、Ilya Sutskever 和 Geoffrey E Hinton。《使用深度卷积神经网络进行 ImageNet 分类》。在 F. Pereira、C. J. C. Burges、L. Bottou 和 K. Q. Weinberger 主编的《神经信息处理系统进展 25》中，第 1097–1105 页。Curran Associates, Inc.，2012 年。

+   [51] Yi-Tong Zhou 和 Rama Chellappa。《使用神经网络计算光流》。在 IEEE 国际神经网络会议中，第 1998 卷，第 71–78 页，1988 年。

+   [52] Sepp Hochreiter 和 Jürgen Schmidhuber。《长短期记忆》。神经计算，9(8)：1735–1780，1997 年。

+   [53] Kyunghyun Cho、Bart Van Merriënboer、Caglar Gulcehre、Dzmitry Bahdanau、Fethi Bougares、Holger Schwenk 和 Yoshua Bengio。《使用 rnn 编码器-解码器进行统计机器翻译的短语表示学习》。arXiv 预印本 arXiv:1406.1078，2014 年。

+   [54] Yaniv Taigman, Ming Yang, Marc’Aurelio Ranzato, 和 Lior Wolf. Deepface: 缩小人脸验证中与人类水平性能的差距. 见于 IEEE 计算机视觉与模式识别会议论文集, 页码 1701–1708, 2014.

+   [55] Rachid Riad, Corentin Dancette, Julien Karadayi, Neil Zeghidour, Thomas Schatz, 和 Emmanuel Dupoux. 用于无监督语音表示学习的孪生网络中的采样策略. arXiv 预印本 arXiv:1804.11297, 2018.

+   [56] Zara Alaverdyan, Julien Jung, Romain Bouet, 和 Carole Lartizien. 用于脑部多参数磁共振成像的无监督异常检测的正则化孪生神经网络: 适用于癫痫病灶筛查. 2018.

+   [57] Arthur L Samuel. 使用跳棋游戏的机器学习研究. IBM 研究与开发期刊, 3(3):210–229, 1959.

+   [58] Ian Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, 和 Yoshua Bengio. 生成对抗网络. 见于 Z. Ghahramani, M. Welling, C. Cortes, N. D. Lawrence, 和 K. Q. Weinberger 主编, 《神经信息处理系统进展 27》, 页码 2672–2680\. Curran Associates, Inc., 2014.

+   [59] Scott Reed, Zeynep Akata, Xinchen Yan, Lajanugen Logeswaran, Bernt Schiele, 和 Honglak Lee. 生成对抗文本到图像合成. arXiv 预印本 arXiv:1605.05396, 2016.

+   [60] Artur Kadurin, Alexander Aliper, Andrey Kazennov, Polina Mamoshina, Quentin Vanhaelen, Kuzma Khrabrov, 和 Alex Zhavoronkov. 有意义线索的丰富源泉: 应用深度对抗自编码器于肿瘤学中的新分子开发. Oncotarget, 8(7):10883, 2017.

+   [61] Wengling Chen 和 James Hays. Sketchygan: 迈向多样化和真实的草图到图像合成. 见于 IEEE 计算机视觉与模式识别会议论文集, 页码 9416–9425, 2018.

+   [62] Taesung Park, Ming-Yu Liu, Ting-Chun Wang, 和 Jun-Yan Zhu. Gaugan: 基于空间自适应归一化的语义图像合成. 见于 ACM SIGGRAPH 2019 实时演示!, 页码 2\. ACM, 2019.

+   [63] Geoffrey E Hinton 和 Ruslan R Salakhutdinov. 使用神经网络减少数据的维度. science, 313(5786):504–507, 2006.

+   [64] Pascal Vincent, Hugo Larochelle, Yoshua Bengio, 和 Pierre-Antoine Manzagol. 使用去噪自编码器提取和组合鲁棒特征. 见于第 25 届国际机器学习会议论文集, 页码 1096–1103\. ACM, 2008.

+   [65] Richard Zhang, Phillip Isola, 和 Alexei A Efros. 色彩丰富的图像上色. 见于欧洲计算机视觉会议, 页码 649–666. Springer, 2016.

+   [66] Detian Huang, Weiqin Huang, Zhenguo Yuan, Yanming Lin, Jian Zhang, 和 Lixin Zheng. 基于改进的稀疏自编码器的图像超分辨率算法. Information, 9(1):11, 2018.

+   [67] Chih-Kuan Yeh, Wei-Chieh Wu, Wei-Jen Ko, 和 Yu-Chiang Frank Wang. 学习深度潜在空间进行多标签分类. 见于 AAAI, 页码 2838–2844, 2017.

+   [68] Diederik P Kingma 和 Max Welling. 自编码变分贝叶斯。arXiv 预印本 arXiv:1312.6114，2013 年。

+   [69] Yoshua Bengio. 表示的深度学习：展望。在统计语言和语音处理国际会议中，页 1–37。Springer，2013 年。

+   [70] Ilya Sutskever, James Martens, George Dahl 和 Geoffrey Hinton. 初始化和动量在深度学习中的重要性。在国际机器学习大会中，页 1139–1147，2013 年。

+   [71] John Duchi, Elad Hazan 和 Yoram Singer. 用于在线学习和随机优化的自适应子梯度方法。机器学习研究杂志，12（7 月）：2121–2159，2011 年。

+   [72] Diederik P Kingma 和 Jimmy Ba. Adam：一种随机优化方法。arXiv 预印本 arXiv:1412.6980，2014 年。

+   [73] Luis Miguel Rios 和 Nikolaos V Sahinidis. 无导数优化：算法综述及软件实现比较。全球优化杂志，56(3):1247–1293，2013 年。

+   [74] Arild Nøkland. 直接反馈对齐在深度神经网络中的学习效果。在神经信息处理系统进展中，页 1037–1045，2016 年。

+   [75] Robert Tibshirani. 通过套索进行回归收缩和选择。皇家统计学会 B 系列（方法论），页 267–288，1996 年。

+   [76] Leo Breiman. 提升预测器。机器学习，24(2):123–140，1996 年。

+   [77] Yoav Freund. 通过多数投票提升弱学习算法。信息与计算，121(2):256–285，1995 年。

+   [78] Mohammad Moghimi, Serge J Belongie, Mohammad J Saberian, Jian Yang, Nuno Vasconcelos 和 Li-Jia Li. 提升卷积神经网络。在 BMVC，2016 年。

+   [79] Jesse Eickholt 和 Jianlin Cheng. Dndisorder: 使用提升和深度网络预测蛋白质无序性。BMC 生物信息学，14(1):88，2013 年。

+   [80] Nitish Srivastava, Geoffrey Hinton, Alex Krizhevsky, Ilya Sutskever 和 Ruslan Salakhutdinov. Dropout：防止神经网络过拟合的简单方法。机器学习研究杂志，15(1):1929–1958，2014 年。

+   [81] Luis Perez 和 Jason Wang. 数据增强在图像分类中的有效性：使用深度学习。arXiv 预印本 arXiv:1712.04621，2017 年。

+   [82] Ekin D Cubuk, Barret Zoph, Dandelion Mane, Vijay Vasudevan 和 Quoc V Le. Autoaugment：从数据中学习增强策略。arXiv 预印本 arXiv:1805.09501，2018 年。

+   [83] Navdeep Jaitly 和 Geoffrey E Hinton. 声道长度扰动（vtlp）改善语音识别。在 ICML 深度学习用于音频、语音和语言研讨会中，卷 117，2013 年。

+   [84] Hiroki OHASHI, Mohammad AL-NASER, Sheraz AHMED, Takayuki AKIYAMA, Takuto SATO, Phong NGUYEN, Katsuyuki NAKAMURA 和 Andreas DENGEL. 通过物理约束增强可穿戴传感器数据以用于基于 DNN 的人类动作识别。2017 年。

+   [85] Christopher Bowles, Liang Chen, Ricardo Guerrero, Paul Bentley, Roger Gunn, Alexander Hammers, David Alexander Dickie, Maria Valdés Hernández, Joanna Wardlaw 和 Daniel Rueckert。GAN 增强：使用生成对抗网络增强训练数据。arXiv 预印本 arXiv:1810.10863，2018 年。

+   [86] Antreas Antoniou, Amos Storkey 和 Harrison Edwards。数据增强生成对抗网络。arXiv 预印本 arXiv:1711.04340，2017 年。

+   [87] Javier Jorge, Jesús Vieco, Roberto Paredes, Joan-Andreu Sánchez 和 José-Miguel Benedí。关于变分自编码器在数据增强中的应用的实证评估。发表于 VISIGRAPP (5: VISAPP)，第 96–104 页，2018 年。

+   [88] Xiaofeng Liu, Yang Zou, Lingsheng Kong, Zhihui Diao, Junliang Yan, Jun Wang, Site Li, Ping Jia 和 Jane You。通过潜在空间插值进行图像分类的数据增强。发表于 2018 年第 24 届国际模式识别会议 (ICPR)，第 728–733 页。IEEE，2018 年。

+   [89] Yichuan Tang 和 Chris Eliasmith。用于鲁棒视觉识别的深度网络。发表于第 27 届国际机器学习会议 (ICML-10) 论文集，第 1055–1062 页。Citeseer，2010 年。

+   [90] Ben Poole, Jascha Sohl-Dickstein 和 Surya Ganguli。分析自编码器和深度网络中的噪声。arXiv 预印本 arXiv:1406.1831，2014 年。

+   [91] David H Wolpert。堆叠泛化。神经网络，5(2)：241–259，1992 年。

+   [92] Kai Ming Ting 和 Ian H Witten。堆叠泛化中的问题。人工智能研究杂志，10：271–289，1999 年。

+   [93] Zhi-Hua Zhou 和 Ji Feng。深度森林：深度神经网络的替代方案。arXiv 预印本 arXiv:1702.08835，2017 年。

+   [94] Guanjin Wang, Guangquan Zhang, Kup-Sze Choi 和 Jie Lu。用于分类的深度加性最小二乘支持向量机与模型迁移。IEEE 系统、人与控制论学报：系统，2017 年。

+   [95] Leo Breiman。通过随机化输出来提高预测准确性。机器学习，40(3)：229–242，2000 年。

+   [96] Tin Kam Ho。随机决策森林。发表于文档分析与识别，1995 年，第三届国际会议论文集，第 1 卷，第 278–282 页。IEEE，1995 年。

+   [97] Yann LeCun。手写数字的 MNIST 数据库。http://yann.lecun.com/exdb/mnist/，1998 年。

+   [98] Gavin C Cawley。基于留一法交叉验证的加权 ls-svm 模型选择标准。发表于神经网络，2006 年。IJCNN’06 国际联合会议，第 1661–1668 页。IEEE，2006 年。

+   [99] Hao Yang 和 Jianxin Wu。具有加性核的大规模分类的实用方法。发表于亚洲机器学习会议，第 523–538 页，2012 年。

+   [100] Azizi Abdullah, Remco C Veltkamp 和 Marco A Wiering。用于图像分类的深度支持向量机集成。发表于软计算与模式识别，2009 年。SOCPAR’09 国际会议，第 301–306 页。IEEE，2009 年。

+   [101] 奥里奥尔·维尼亚尔斯、杨青·贾、李登和特雷弗·达雷尔。使用递归感知表示进行学习。发表于《神经信息处理系统进展》中，页面 2825–2833，2012 年。

+   [102] 李登、董宇和约翰·普拉特。可扩展堆叠与学习以构建深度架构。发表于 2012 年 IEEE 国际会议《声学、语音与信号处理（ICASSP）》上，页面 2133–2136。IEEE，2012 年。

+   [103] 布赖恩·哈钦森、李登和董宇。张量深度堆叠网络。《IEEE 模式分析与机器智能汇刊》，35(8):1944–1957，2013 年。

+   [104] 李登和董宇。深度凸网络：一种用于语音模式分类的可扩展架构。发表于第十二届国际语音通信协会年会上，2011 年。

+   [105] 威尼斯·艾琳·李昂、季闻·鲁和刚·王。使用深度 PCA 的人脸识别。发表于 2013 年第 9 届国际信息、通信与信号处理会议上，页面 1–5。IEEE，2013 年。

+   [106] 亚历克斯·克里热夫斯基和杰弗里·辛顿。学习来自微小图像的多层特征。技术报告，Citeseer，2009 年。

+   [107] 乔纳森·什伦斯。主成分分析教程。arXiv 预印本 arXiv:1404.1100，2014 年。

+   [108] 安德里亚斯·达米亚努和尼尔·劳伦斯。深度高斯过程。发表于《人工智能与统计》上，页面 207–215，2013 年。

+   [109] 伊利亚·苏茨克弗和杰弗里·辛顿。为高维序列学习多级分布式表示。发表于《人工智能与统计》上，页面 548–555，2007 年。

+   [110] 罗兰·梅米塞维奇和杰弗里·辛顿。无监督图像变换学习。发表于 2007 年 IEEE 计算机视觉与模式识别会议上，页面 1–8。IEEE，2007 年。

+   [111] 凯文·斯沃斯基、伊利亚·苏茨克弗、丹尼尔·塔洛、理查德·S·泽梅尔、鲁斯兰·R·萨拉赫丁诺夫和瑞安·P·亚当斯。基数限制玻尔兹曼机。发表于《神经信息处理系统进展》中，页面 3293–3301，2012 年。

+   [112] 卡尔·爱德华·拉斯穆森。机器学习中的高斯过程。发表于《机器学习暑期学校》中，页面 63–71。Springer，2003 年。

+   [113] 塞萨尔·林肯·C·马托斯、甄文·戴、安德里亚斯·达米亚努、杰瑞米·福斯、吉尔赫尔梅·A·巴雷托和尼尔·D·劳伦斯。递归高斯过程。arXiv 预印本 arXiv:1511.06644，2015 年。

+   [114] 马克·范德·威尔克、卡尔·爱德华·拉斯穆森和詹姆斯·亨斯曼。卷积高斯过程。发表于《神经信息处理系统进展》中，页面 2849–2858，2017 年。

+   [115] 甄文·戴、安德里亚斯·达米亚努、哈维尔·冈萨雷斯和尼尔·劳伦斯。变分自编码深度高斯过程。arXiv 预印本 arXiv:1511.06455，2015 年。

+   [116] 安德里亚斯·达米亚努。深度高斯过程与变分不确定性传播。博士论文，谢菲尔德大学，2015 年。

+   [117] 马修·M·邓洛普、马克·A·吉罗拉米、安德鲁·M·斯图尔特和阿瑞莎·L·特克恩特鲁普。深度高斯过程有多深？《机器学习研究杂志》，19(1):2100–2145，2018 年。

+   [118] David Duvenaud, Oren Rippel, Ryan Adams, 和 Zoubin Ghahramani. 避免非常深层网络中的病态现象。在人工智能与统计学会议上，第 202–210 页，2014。

+   [119] Lev V Utkin 和 Mikhail A Ryabinin. 一种 Siamese 深度森林。arXiv 预印本 arXiv:1704.08715, 2017。

+   [120] Yan Zuo, Gil Avraham, 和 Tom Drummond. 生成对抗森林用于更好的对抗学习。arXiv 预印本 arXiv:1805.05185, 2018。

+   [121] Rudolph Emil Kalman. 一种新的线性滤波和预测问题的方法。基础工程学报，82(1):35–45, 1960。

+   [122] Rahul G. Krishnan, Uri Shalit, 和 David Sontag. 深度 Kalman 滤波器。arXiv 预印本 arXiv:1511.05121, 2015。

+   [123] Shirli Di-Castro Shashua 和 Shie Mannor. 深度鲁棒 Kalman 滤波器。arXiv 预印本 arXiv:1703.02310, 2017。

+   [124] Guo Lu, Wanli Ouyang, Dong Xu, Xiaoyun Zhang, Zhiyong Gao, 和 Ming-Ting Sun. 用于视频压缩伪影减少的深度 Kalman 滤波网络。在欧洲计算机视觉会议（ECCV）上，第 568–584 页，2018。

+   [125] Ji Feng 和 Zhi-Hua Zhou. 通过森林的自编码器。arXiv 预印本 arXiv:1709.09018, 2017。

+   [126] Marco A Wiering 和 Lambert RB Schomaker. 多层支持向量机。正则化、优化、核函数和支持向量机，第 457 页，2014。

+   [127] Peter Kontschieder, Madalina Fiterau, Antonio Criminisi, 和 Samuel Rota Bulo. 深度神经决策森林。在计算机视觉（ICCV）上，2015 年 IEEE 国际会议，第 1467–1475 页。IEEE，2015。

+   [128] Nicholas Frosst 和 Geoffrey Hinton. 将神经网络提炼为软决策树。arXiv 预印本 arXiv:1711.09784, 2017。

+   [129] Ryutaro Tanno, Kai Arulkumaran, Daniel C Alexander, Antonio Criminisi, 和 Aditya Nori. 自适应神经树。arXiv 预印本 arXiv:1807.06699, 2018。

+   [130] Yongxin Yang, Irene Garcia Morillo, 和 Timothy M Hospedales. 深度神经决策树。arXiv 预印本 arXiv:1806.06988, 2018。

+   [131] Ji Feng, Yang Yu, 和 Zhi-Hua Zhou. 多层梯度提升决策树。arXiv 预印本 arXiv:1806.00007, 2018。

+   [132] Glenn M Fung 和 Olvi L Mangasarian. 用于支持向量机分类的特征选择牛顿法。计算优化与应用，28(2):185–202, 2004。

+   [133] Hao Helen Zhang, Jeongyoun Ahn, Xiaodong Lin, 和 Cheolwoo Park. 使用具有非凸惩罚的支持向量机进行基因选择。生物信息学，22(1):88–95, 2005。

+   [134] Jianqing Fan 和 Runze Li. 通过非凹惩罚似然和其 oracle 属性进行变量选择。美国统计协会期刊，96(456):1348–1360, 2001。

+   [135] Houtao Deng 和 George Runger. 通过正则化树进行特征选择。在 2012 年国际联合神经网络会议（IJCNN）上，第 1–8 页。IEEE，2012。

+   [136] Houtao Deng 和 George Runger. 使用引导正则化随机森林进行基因选择。模式识别，46(12):3483–3489, 2013。

+   [137] Sida Wang 和 Christopher D Manning。基线和二元模型：简单的良好情感与主题分类。发表于第 50 届计算语言学协会年会：短论文卷 2，第 90–94 页。计算语言学协会，2012 年。

+   [138] Sida Wang 和 Christopher Manning。快速 dropout 训练。发表于国际机器学习大会，第 118–126 页，2013 年。

+   [139] Rashmi Korlakai Vinayak 和 Ran Gilad-Bachrach。Dart：Dropouts 遇见多重加性回归树。发表于《人工智能与统计学》，第 489–497 页，2015 年。

+   [140] Jerome H Friedman。贪婪函数近似：一种梯度提升机器。《统计年鉴》，第 1189–1232 页，2001 年。

+   [141] Jerome H Friedman。随机梯度提升。《计算统计与数据分析》，38(4)：367–378，2002 年。

+   [142] Claudio Lucchese, Franco Maria Nardini, Salvatore Orlando, Raffaele Perego, 和 Salvatore Trani。X-dart：融合 dropout 和剪枝以提高排名学习效率。发表于第 40 届国际 ACM SIGIR 信息检索研究与发展会议，第 1077–1080 页。ACM，2017 年。

+   [143] Sebastien C Wong, Adam Gatt, Victor Stamatescu, 和 Mark D McDonnell。理解分类的数据增强：何时进行变形？arXiv 预印本 arXiv:1609.08764，2016 年。

+   [144] Ruo Xu。对随机森林方法的改进。2013 年。

+   [145] Yani Ioannou, Duncan Robertson, Darko Zikic, Peter Kontschieder, Jamie Shotton, Matthew Brown, 和 Antonio Criminisi。决策森林、卷积网络及介于两者之间的模型。arXiv 预印本 arXiv:1603.01250，2016 年。

+   [146] Charles Blundell, Julien Cornebise, Koray Kavukcuoglu, 和 Daan Wierstra。神经网络中的权重不确定性。arXiv 预印本 arXiv:1505.05424，2015 年。

+   [147] Meire Fortunato, Charles Blundell, 和 Oriol Vinyals。贝叶斯递归神经网络。CoRR, abs/1704.02798，2017 年。

+   [148] Daniel Zoran, Balaji Lakshminarayanan, 和 Charles Blundell。利用可微分边界树学习深度最近邻表示。arXiv 预印本 arXiv:1702.08833，2017 年。

+   [149] Charles Mathy, Nate Derbinsky, José Bento, Jonathan Rosenthal, 和 Jonathan S Yedidia。边界森林算法用于在线监督和无监督学习。发表于 AAAI，第 2864–2870 页，2015 年。

+   [150] Yichuan Tang。使用线性支持向量机的深度学习。arXiv 预印本 arXiv:1306.0239，2013 年。

+   [151] Alex Krizhevsky, Vinod Nair, 和 Geoffrey Hinton。Cifar-10（加拿大高级研究所）。

+   [152] Xiao-Xiao Niu 和 Ching Y Suen。一种新型混合 cnn–svm 分类器用于识别手写数字。《模式识别》，45(4)：1318–1325，2012 年。

+   [153] Masoumeh Zareapoor, Pourya Shamsolmoali, Deepak Kumar Jain, Haoxiang Wang, 和 Jie Yang。利用深度学习的核化支持向量机：一种高效的极端多类数据集方法。《模式识别快报》，2017 年。

+   [154] Jawad Nagi, Gianni A Di Caro, Alessandro Giusti, Farrukh Nagi, Luca Maria Gambardella,等。卷积神经支持向量机：多机器人系统的混合视觉模式分类器。在 ICMLA（1）上，第 27-32 页。2012 年。

+   [155] Abdel Bellili, Michel Gilloux, and Patrick Gallinari. 混合 mlp-svm 手写数字识别器。在 2001 年文档分析和识别国际会议（ICDAR）上，第 28-32 页。IEEE，2001 年。

+   [156] Washington W Azevedo and Cleber Zanchet. 用于草书识别的 mlp-svm 混合模型。在神经网络（IJCNN）上，2011 年国际联合会议，第 843-850 页。IEEE，2011 年。

+   [157] Tianyi Zhao, Baopeng Zhang, Ming He, Wei Zhanga, Ning Zhou, Jun Yu, and Jianping Fan. 采用深度网络嵌入大规模视觉识别的视觉层次结构。IEEE 图像处理交易，2018 年。

+   [158] Harold Hotelling. 两组变量之间的关系。在统计学突破中，第 162-190 页。Springer，1992 年。

+   [159] David R Hardoon, Sandor Szedmak, and John Shawe-Taylor. 典型相关性分析：概述及应用于学习方法。神经计算，16(12)：2639-2664，2004 年。

+   [160] Galen Andrew, Raman Arora, Jeff Bilmes, and Karen Livescu. 深度典型相关性分析。在国际机器学习会议上，第 1247-1255 页。2013 年。

+   [161] Kai Sheng Tai, Richard Socher, and Christopher D Manning. 改进的树状长短时记忆网络的语义表示。arXiv 预印本 arXiv:1503.00075，2015 年。

+   [162] David Alvarez-Melis and Tommi S Jaakkola. 具有双重递归神经网络的树形解码。2016 年。

+   [163] Andrea Cimino and Felice Dell’Orletta. 用于情感分析的串联 lstm-svm 方法。2016 年 12 月 7 日最终研讨会上，那不勒斯，第 172 页。2016 年。

+   [164] Abien Fred M Agarap. 一种结合门控循环单元（GRU）和支持向量机（SVM）的神经网络架构，用于网络流量数据入侵检测。在 2018 年第 10 届国际机器学习和计算会议上，第 26-30 页。ACM，2018 年。

+   [165] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra,和 Jorge Luis Reyes-Ortiz。使用智能手机进行人体活动识别的公共领域数据集。在 ESANN 上，2013 年。

+   [166] 大规模视觉识别挑战 2017（ilsvrc2017），2017 年。

+   [167] Nikolaos G Paterakis, Elena Mocanu, Madeleine Gibescu, Bart Stappers, and Walter van Alst. 深度学习与传统机器学习方法在聚合能源需求预测中的比较。在创新智能电网技术欧洲会议（ISGT-Europe）上，2017 IEEE PES，第 1-6 页。IEEE，2017 年。

+   [168] Alexander Sboev, Ivan Moloshnikov, Dmitry Gudovskikh, Anton Selivanov, Roman Rybka,和 Tatiana Litvinova。在 rusprofiling 文本的作者性别识别中，深度学习神经网络与传统机器学习的比较。计算机科学会议记录，123：424-431，2018 年。

+   [169] 陈英鸿、陈伟臣、赖柏村、林景恒和李志群。比较深度神经网络与其他机器学习算法在大规模人群基础电子医疗索赔数据库中的中风预测。载于《医学与生物学工程学会（EMBC）》，2017 年第 39 届 IEEE 国际年会，页码 3110–3113。IEEE，2017 年。

+   [170] 袁传龙、朱越飞、费金龙和何欣正。基于递归神经网络的入侵检测深度学习方法。《IEEE Access》，5:21954–21961，2017 年。

+   [171] 海瑟姆·M·法耶克、玛格丽特·莱赫和劳伦斯·卡维顿。评估用于语音情感识别的深度学习架构。《神经网络》，92:60–68，2017 年。

+   [172] 亚历山大·德·布雷比松、艾蒂安·西蒙、亚历克斯·奥沃拉特、帕斯卡尔·文森特和约书亚·本吉奥。应用于出租车目的地预测的人工神经网络。arXiv 预印本 arXiv:1508.00021，2015 年。

+   [173] 亚历克·拉德福德、卢克·梅茨和苏密特·钦塔拉。利用深度卷积生成对抗网络的无监督表示学习。arXiv 预印本 arXiv:1511.06434，2015 年。

+   [174] 朱迪·霍夫曼、埃里克·曾、朴泰成、朱俊燕、菲利普·伊索拉、凯特·萨恩科、阿列克谢·A·埃夫罗斯和特雷弗·达雷尔。Cycada：周期一致的对抗性领域自适应。arXiv 预印本 arXiv:1711.03213，2017 年。
