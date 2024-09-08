<!--yml

类别：未分类

日期：2024-09-06 19:34:59

-->

# [2401.07187] 关于深度学习的统计理论调查：逼近、训练动态和生成模型

> 来源：[`ar5iv.labs.arxiv.org/html/2401.07187`](https://ar5iv.labs.arxiv.org/html/2401.07187)

# 关于深度学习的统计理论调查：逼近、训练动态和生成模型

Namjoon Suh 和 Guang Cheng 统计与数据科学系，UCLA

###### 摘要

在本文中，我们从三个角度回顾了神经网络的统计理论文献。在第一部分中，回顾了神经网络在非参数回归或分类框架下的超额风险结果。这些结果依赖于神经网络的显式构造，从而实现了超额风险的快速收敛率，因为采用了来自逼近理论的工具。通过这些构造，网络的宽度和深度可以用样本大小、数据维度和函数光滑度来表示。尽管如此，其基础分析仅适用于深度神经网络中高度非凸景观中的全局最小化器。这促使我们在第二部分回顾神经网络的训练动态。具体来说，我们回顾了试图回答“神经网络如何通过基于梯度的方法找到能够在未见数据上良好泛化的解”的论文。特别地，回顾了两个著名的范式：神经切线核（NTK）范式和均值场（MF）范式。在最后一部分，我们回顾了生成模型中的最新理论进展，包括生成对抗网络（GANs）、扩散模型和大语言模型（LLMs）中的上下文学习（ICL）。前两种模型被认为是现代生成 AI 时代的主要支柱，而 ICL 是 LLMs 在上下文中从少量示例中学习的强大能力。最后，我们通过提出若干有前景的深度学习理论研究方向来结束本文。

## 1 引言

近年来，深度学习（Goodfellow et al., 2016）作为机器学习的一个子领域，经历了显著的发展。它的影响已超越传统界限，在医疗（Esteva et al., 2019）、金融（Heaton et al., 2017）、自主系统（Grigorescu et al., 2020）和自然语言处理（Otter et al., 2020）等领域取得了重大进展。神经网络，即我们大脑的数学抽象，处于这一进程的核心。然而，在人工智能持续复兴的背景下，神经网络获得了几乎神话般的地位，传播了它们更像是艺术而非科学的误解。重要的是要揭穿这一观念。尽管神经网络的应用可能令人敬畏，但它们牢牢根植于数学原理中。在这一背景下，深度学习理论的重要性变得显而易见。以下几个关键点强调了它的重要性。

### 1.1 为什么理论很重要？

在本小节中，我们旨在强调在数学和统计框架中理解深度学习的重要性。以下是一些需要考虑的关键点：

1.  1.

    深度学习是一个动态且迅速发展的领域，产生了成千上万的在线出版物。今天的模型具有高度复杂的网络架构，由众多复杂的子组件组成。在这种复杂性中，理解这些模型的基本原理变得至关重要。为了实现这一理解，将这些模型置于统一的数学框架中是必不可少的。这样的框架作为一个有价值的工具，能够提炼出这些复杂模型的核心概念，使我们能够提取和理解驱动其功能的关键原理。

1.  2.

    将统计框架应用于深度学习模型可以与其他统计方法进行有意义的比较。例如，广泛使用的统计估计器，如小波或核方法，可能会引发关于深度神经网络在何时以及为何可能表现更好的问题。这种分析帮助我们理解深度学习在何种情况下优于传统统计方法，从而对理论和实践都有所裨益。

1.  3.

    超参数，如学习率、权重初始化、网络架构选择、激活函数和批量大小，显著影响估计模型的质量。理解这些超参数的适当范围对于理论研究者和实践者都是至关重要的。例如，在大数据时代，当一个数据集中有数百万个样本时，理论智慧告诉我们，为了良好估计组成函数，网络的深度应按样本大小的对数比例进行缩放（Schmidt-Hieber, 2020）。

在本综述中，我们提供了对在精确数学设置下深入探讨这些概念的论文的概述，为读者提供了有关上述主题的具体见解。在这里，我们尽量避免过多的技术细节，使介绍尽可能地对各个领域的统计学家都能理解。

### 1.2 论文路线图

我们将现有的关于神经网络统计理论的文献分为三类。

1.  1.

    近似理论观点。最近，有大量的研究工作将神经网络模型的近似理论（Yarotsky, 2017; Mhaskar, 1996; Petersen 和 Voigtlaender, 2018; Schmidt-Hieber, 2020; Montanelli 和 Du, 2019; Blanchard 和 Bennouna, 2022; Hornik 等, 1989; Hanin, 2019）与经验过程中的工具（Van de Geer, 2000）相结合，以获得回归（Schmidt-Hieber, 2020; Hu 等, 2021）和分类（Hu 等, 2020; Kim 等, 2021）任务下的超额风险的快速收敛速率，尤其是在非参数设置下。近似理论为测量神经网络在特定类别的函数近似中的基本复杂性提供了有用的视角。具体来说，它使得能够明确构建神经网络以进行函数近似，从而我们知道网络的宽度、深度以及活跃参数的数量应如何根据样本大小、数据维度和函数光滑性指标进行调整，以获得良好的收敛速率。为简便起见，我们主要考虑那些将全连接神经网络用作函数估计器的研究。这些研究包括 Schmidt-Hieber (2020); Kim 等 (2021); Shen 等 (2021); Jiao 等 (2021); Lu 等 (2021); Imaizumi 和 Fukumizu (2019, 2022); Suzuki (2018); Chen 等 (2019b); Suzuki 和 Nitanda (2021); Suh 等 (2022) 在各种问题设置下的工作。然而，这些工作假设损失函数的全局最小值是可以获得的，并主要关注这些最小值的统计性质，而没有考虑优化问题。然而，考虑到隐藏层激活函数的非线性，损失函数的非凸性使这一假设变得十分强烈。

1.  2.

    训练动态视角。在这种背景下，理解神经网络模型的非凸损失函数的分布及其对神经网络泛化能力的影响成为文献中的下一步。例如，一项开创性的实证研究（Zhang et al., 2021）揭示了经过充分过参数化的神经网络模型，通过随机梯度下降训练后，可以完美地拟合（有噪声的）数据甚至随机噪声，但同时它们仍能良好地进行泛化。在众多关于过参数化作用的重要发现中，Arora et al. (2019b); Jacot et al. (2018) 发现，具有足够宽度的深度神经网络在通过梯度下降（GD）训练时，在 $\ell_{2}$-损失下，其动态行为类似于在再生核希尔伯特空间（RKHS）中的函数，其中的核与特定的网络结构相关联。许多后续的研究工作在各种设置下研究了神经网络在核范畴下的训练动态和泛化能力（Suh et al., 2021; Hu et al., 2021; Nitanda and Suzuki, 2020）。

    尽管如此，神经网络展示了不仅仅是核回归的能力，例如特征学习（Yang and Hu, 2020）。这种能力通过允许网络参数显著偏离其初始值来实现，这在核范畴中并未提供这种自由。许多研究人员试图填补这一空白（Ghorbani et al., 2020b; Wei et al., 2019），证明了神经网络相较于核范畴网络的统计优势，但仍限制了网络参数可能的移动距离。

    另一重要的研究方向尝试在不同的范畴，即均值场（MF）范畴中解释神经网络的学习动态。在这个范畴中，网络参数可以大幅度偏离其初始值，尽管这需要无限的宽度。最后，我们通过介绍一个统一框架（Yang and Hu, 2020）来结束本节，该框架为核范畴和 MF 范畴提供了一个全面的理解，说明了在基于梯度的方法中，权重初始化选择和学习率缩放如何影响神经网络在其无限宽度极限下的动态。

1.  3.

    生成建模。在本节中，我们回顾了生成模型领域最近的理论进展，包括生成对抗网络（GANs）、扩散模型以及大型语言模型（LLMs）中的上下文学习。过去十年，GANs（Goodfellow 等人，2014）作为一种重要的无监督学习方法脱颖而出，以其学习数据分布并高效采样数据的能力而闻名。在本次综述中，我们将介绍研究 GANs 统计属性的论文（Arora 等人，2017；Liang，2021；Chen 等人，2020a；Bai 等人，2018；Zhang 等人，2017；Schreuder 等人，2021）。最近，另一类生成模型——扩散模型，已在生成高质量的合成数据方面表现出色，涵盖图像（Song 等人，2020；Dhariwal 和 Nichol，2021）、表格数据（Kim 等人，2022；Suh 等人，2023）、医学成像（Müller-Franzes 等人，2022）等数据模态，超越了基于 GAN 的模型。然而，鉴于模型的复杂性质及其在社区中的近期引入，其为何效果如此显著的理论原因仍不清楚。最后，我们将回顾大型语言模型中常见的有趣现象，即上下文学习（ICL）。这指的是 LLMs 在条件提示序列（包括任务的示例（输入-输出对））和新查询输入的基础上，能够准确生成对应的输出。读者可以参考 Gui 等人（2021）；Yang 等人（2022）关于 GANs 和扩散模型在各领域应用的详细描述的综述论文。有关 ICL 的概述，请参见 Dong 等人（2022）的综述，突出了一些关键发现和进展。

### 1.3 深度学习理论的现有调查

据我们了解，目前已有三篇关于深度学习理论的综述论文（Bartlett 等，2021；Fan 等，2021；Belkin，2021）。这些论文在某些主题上存在重叠，但它们的主要关注点不同。Bartlett 等（2021）提供了关于深度神经网络统计理解的全面且技术性的综述。特别是，作者专注于研究过参数化在神经网络中的重要影响，这在使基于梯度的方法发现插值解方面发挥了关键作用。这些方法引入了隐式正则化，如 Neyshabur（2017）所讨论的，或者导致一种称为良性过拟合的现象（Bartlett 等，2020）。Fan 等（2021）介绍了实践中最常用的神经网络架构，如卷积神经网络（CNN）、递归神经网络（RNN）及批量归一化、丢弃等训练技术，从统计角度进行分析。还简要介绍了神经网络的近似理论。类似于 Bartlett 等（2021），Belkin（2021）回顾了过参数化对隐式正则化和良性过拟合的作用，这种现象不仅在神经网络模型中观察到，也在经典统计模型中如加权最近邻预测器中观察到。他们特别提供了关于神经网络的非凸损失景观的过参数化角色的直观理解，通过优化的视角来阐释。

## 2 神经网络的过度风险界限

我们简要概述了全连接网络，这是本文主要关注的对象。从高层次来看，深度神经网络可以视为一类非线性统计模型，它们能够编码数据的高度复杂表示。具体的网络架构 $(L,\mathbf{p})$ 包含一个正整数 $L$，称为隐藏层的数量，以及一个宽度向量 $\mathbf{p}:=(\mathbf{p}_{0},\dots,\mathbf{p}_{L+1})\in\mathbb{N}^{L+2}$。具有架构 $\tilde{f}$ 的全连接神经网络就是任何形式的函数，其输入特征为 $\mathbf{x}\in\mathcal{X}$：

|  | $\displaystyle\tilde{f}:\mathcal{X}\rightarrow{\mathbb{R}},\quad\mathbf{x}\rightarrow{f(\mathbf{x})={W}_{L}\mathbf{\sigma}{W}_{L-1}\mathbf{\sigma}{W}_{L-2}\dots\mathbf{\sigma}{W}_{1}\mathbf{x}},$ |  | (1) |
| --- | --- | --- | --- |

其中 $\mathbf{W}_{i}\in\mathbb{R}^{p_{i+1}\times p_{i}}$ 是一个权重矩阵，且 $\mathbf{p}_{0}=d$，$\mathbf{p}_{L+1}=1$，$\mathbf{v}_{i}\in\mathbb{R}^{p_{i}}$ 是一个偏移向量。

网络函数是通过交替矩阵-向量乘法与非线性激活函数$\sigma$的作用来构建的。设$\|\mathbf{W}_{j}\|_{0}$和$|\mathbf{v}_{j}|_{0}$分别表示第$j^{\text{th}}$隐藏层中$\mathbf{W}_{j}$和$\mathbf{v}_{j}$的非零项数量。我们考虑的神经网络的最终形式为：

|  | $\displaystyle\mathcal{F}(L,\mathbf{p},\mathcal{N}):=\bigg{\{}\tilde{f}\text{ 的形式\leavevmode\nobreak\ \eqref{DNN}}:\sum_{j=1}^{L}\&#124;\mathbf{W}_{j}\&#124;_{0}+&#124;\mathbf{v}_{j}&#124;_{0}\leq\mathcal{N}\bigg{\}}.$ |  | (2) |
| --- | --- | --- | --- |

在这里，网络的复杂性主要通过三个指标来衡量：（1）宽度记为$\mathbf{p}$，（2）深度，记为$L$，以及（3）活动参数的数量，记为网络的$\mathcal{N}$。有关这些指标的深入讨论，请参见 Anthony 和 Bartlett (1999)。

### 2.1 初步问题设定

回归任务。设$\mathcal{X}$和$\mathcal{Y}\subset\mathbb{R}$分别为可测特征空间和输出空间。我们记$\rho$为在乘积空间$\mathcal{Z}:=\mathcal{X}\times\mathcal{Y}$上的联合概率测度，并设$\rho_{\mathcal{X}}$为特征空间$\mathcal{X}$的边际分布。我们假设噪声数据集$\mathcal{D}:=\{(\mathbf{x}_{i},\mathbf{y}_{i})\}_{i=1}^{n}$是从非参数回归模型生成的。

|  | $\displaystyle\mathbf{y}_{i}=f_{\rho}(\mathbf{x}_{i})+\varepsilon_{i},\quad i=1,2,\dots,n,$ |  | (3) |
| --- | --- | --- | --- |

其中噪声$\varepsilon_{i}$被假设为中心化随机变量且$\mathbb{E}(\varepsilon_{i}|\mathbf{x}_{i})=0$。我们的目标是利用给定的噪声数据集$\mathcal{D}$来估计回归函数$f_{\rho}(\mathbf{x})$。这里，很容易看出回归函数$f_{\rho}:=\mathbb{E}(\mathbf{y}|\mathbf{x})$是在$\ell_{2}$-损失下的总体风险$\mathcal{E}(f)$的最小化器，其定义为：

|  | $\displaystyle\mathcal{E}(f):=\mathbb{E}_{(\mathbf{x},\mathbf{y})\sim\rho}\bigg{[}\big{(}\mathbf{y}-f(\mathbf{x})\big{)}^{2}\bigg{]}.$ |  |
| --- | --- | --- |

然而，由于联合分布$\rho$是未知的，我们不能直接找到$f_{\rho}$。相反，我们解决从数据集$\mathcal{D}$中引发的以下经验风险最小化问题：

|  | $\displaystyle\widehat{f}_{n}=\operatorname*{arg\,min}_{f\in\mathcal{F}(L,\mathbf{p},\mathcal{N})}\mathcal{E}_{D}(f):=\operatorname*{arg\,min}_{f\in\mathcal{F}(L,\mathbf{p},\mathcal{N})}\bigg{\{}\frac{1}{n}\sum_{i=1}^{n}\big{(}\mathbf{y}_{i}-f(\mathbf{x}_{i})\big{)}^{2}\bigg{\}}.$ |  | (4) |
| --- | --- | --- | --- |

请注意，函数估计器取自前馈神经网络假设空间 $\mathcal{F}(L,\mathbf{p},\mathcal{N})$¹¹1 因此，今后我们将用简写符号 $\mathcal{F}$ 表示 $\mathcal{F}(L,\mathbf{p},\mathcal{N})$。对 $(L,\mathbf{p},\mathcal{N})$ 的依赖应该隐含理解。定义在 (2)，我们将 (4) 的经验最小化器表示为 $\widehat{f}_{n}$。目标是通过前馈网络 $f\in\mathcal{F}$ 来估计回归函数 $f_{\rho}$。这里，$f_{\rho}(\mathbf{x})$ 通常假设在某些函数类中，如 Hölder（即 $\mathcal{H}^{r}(\mathcal{X},K)$）或 Sobolev（即 $W_{r}^{p}(\mathcal{X})$ 对于 $1\leq p\leq\infty$）空间。符号 $r(>0)$ 表示函数的光滑度，$K$ 表示 Hölder 球的半径，$p$ 表示用于度量函数导数大小的 $L_{p}$-范数。有关函数类的更严格定义，读者可以参考 Schmidt-Hieber (2020); Yarotsky (2017)。

超额风险的分解。超额风险是一个重要的统计对象，衡量真实函数 $f_{\rho}$ 与通过神经网络 $\widehat{f}_{n}\in\mathcal{F}$ 估计的函数之间的距离。从数学上讲，可以证明超额风险是 $f_{\rho}$ 和 $\widehat{f}_{n}$ 的总体风险之间的差异。我们将回顾利用以下超额风险分解的论文：

|  | $\displaystyle\mathcal{E}(\widehat{f}_{n})-\mathcal{E}(f_{\rho})\leq\frac{\text{复杂度度量 $\mathcal{F}$}}{n}+\frac{\text{近似误差}}{\sqrt{n}}+\text{近似误差}^{2}.$ |  | (5) |
| --- | --- | --- | --- |

对上述分解的证明可以在 Suh 等人 (2022) 中找到。在超额风险的界限中，需要注意的是，“近似误差”和神经网络类 $\mathcal{F}$ 的组合“复杂度度量”之间存在权衡；也就是说，网络假设空间 $\mathcal{F}$ 越丰富，我们得到的近似结果就越精细。然而，假设空间 $\mathcal{F}$ 的任意增加最终会导致超额风险界限的增加。需要注意的是，网络架构的规格（即 $(L,\mathbf{p},\mathcal{N})$ 的选择）影响这两个项之间的张力，并为超额风险提供良好的收敛速率。

近似误差和复杂度度量。近似误差的确切数学定义如下：

|  | $\displaystyle\varepsilon_{\text{Apprx}}:=\sup_{f_{\rho}\in\mathcal{G}}\inf_{f\in\mathcal{F}(L,\mathbf{p},\mathcal{N})}\left\&#124;f-f_{\rho}\right\&#124;_{L^{p}},$ |  | (6) |
| --- | --- | --- | --- |

其中，sup 是对函数类 $\mathcal{G}$ 取的，且 $1\leq p\leq\infty$。在本文中，除非另有说明，$\varepsilon_{\text{Apprx}}$ 应理解为 $p=\infty$ 的均匀近似误差。

对于 $\mathcal{F}(L,\mathbf{p},\mathcal{N})$，存在许多复杂度度量，包括 VC 维度（即 $\text{VCdim}(\mathcal{F})$）、伪维度（即 $\text{Pdim}(\mathcal{F})$）或覆盖数（即 $\text{Cov}(\mathcal{F})$）。有关 $\text{VCdim}(\mathcal{F})$ 和 $\text{Pdim}(\mathcal{F})$ 的一个重要结果来自于 Bartlett 等人 (2019)。当 $\mathcal{F}$ 是具有 $\sigma(x)=\text{max}(x,0)$ 的 ReLU 全连接网络时，在 $L\ll\mathcal{N}^{0.99}$ 的范围内，论文提供了 VC 维度和伪维度的紧界限，如下所示：

|  | $\displaystyle\text{VCdim}(\mathcal{F}),\text{Pdim}(\mathcal{F})\asymp\mathcal{O}\big{(}L\mathcal{N}\log(\mathcal{N})\big{)}.$ |  |
| --- | --- | --- |

这里，符号 $\asymp$ 表示渐近等价。对于 $\mathcal{F}$ 的复杂度度量，另一个有趣的度量是覆盖数。最显著的是，Schmidt-Hieber (2020)中的引理 $5$ 给出了 $\mathcal{F}$ 上均匀覆盖数的界限。设 $V:=\Pi_{\ell=0}^{L+1}(p_{\ell}+1)$。然后，对于任何 $\delta>0$，均匀度量下的覆盖熵界限为：

|  | $\displaystyle\log\text{Cov}(\mathcal{F})\leq(\mathcal{N}+1)\log\big{(}2\delta^{-1}(L+1)V^{2}\big{)}.$ |  | (7) |
| --- | --- | --- | --- |

获得上述结果的一个重要假设是对网络结构的参数空间有界性假设，要求 $\mathbf{W}_{j}$ 和 $\mathbf{v}_{j}$ 的最大绝对值在 $j\in[L]$ 时都被限制在 $1$。在 Schmidt-Hieber (2020) 中，证明结果的关键思想是利用网络输出相对于权重参数的 Lipschitz 连续性。自然地，对于参数空间的离散化，需要有界性假设。然而，有界性假设在计算上难以施加，并且可能限制神经网络的近似能力。（读者可以参考 Farrell 等人 (2021) 对有界性假设不切实际性的进一步讨论。）应注意，如果使用伪维度作为复杂度度量，则可以消除有界性假设，即 Farrell 等人 (2021)；Suh 等人 (2022)；Liang (2021)。

### 2.2 通过全连接网络的非参数回归

在本小节中，给出了神经网络在非参数回归任务下超额风险的收敛速度的文献综述。本文介绍的工作基于分解 (5)。在即将介绍的大量文献中，奠基性工作 Schmidt-Hieber (2020) 为这一研究方向开辟了道路。在对参数的有界性假设下，作者构造了一个稀疏的全连接网络 $\tilde{f}\in\mathcal{F}(L,\mathbf{p},\mathcal{N})$ 来逼近 $f_{\rho}\in\mathcal{H}^{r}(\mathcal{X},K)$，其中 $\mathcal{X}:=[0,1]^{d}$。

###### 定理 2.1。

(定理 $5$ 在 Schmidt-Hieber (2020)) 对于任意 $r$-Hölder 函数 $f_{\rho}\in\mathcal{H}^{r}([0,1]^{d},K)$ 以及任意整数 $m\geq 1$ 和 $N\geq(r+1)^{d}\vee(K+1)e^{d}$，存在一个 ReLU 神经网络 $\tilde{f}\in\mathcal{F}(L,\mathbf{p},\mathcal{N})$，使得 $L\asymp m$，$\mathbf{p}_{\text{max}}\lesssim N$ 和 $\mathcal{N}\lesssim Nm$，从而使得逼近误差有界，如下：

|  | $\displaystyle\left\|\tilde{f}-f_{\rho}\right\|_{L^{\infty}([0,1]^{d})}\lesssim N2^{-m}+N^{-\frac{r}{d}}.$ |  |
| --- | --- | --- |

上述界限包含两个部分。第一部分对应于对$f_{\rho}$的前$\lfloor r\rfloor$阶泰勒展开的近似，第二部分对应于展开的余项的近似。整数$m\geq 1$涉及到网络的深度。宽度$N$的界限在数据维度$d$上有指数依赖，这使得$N^{-\frac{r}{d}}$项在光滑参数中以指数速度衰减。稠密全连接神经网络有$\Theta\big{(}N^{2}m\big{)}$个参数。从这个意义上说，神经网络具有稀疏结构，仅需最多$\Theta\big{(}Nm\big{)}$个非零激活参数$\mathcal{N}$。值得注意的是，随着网络的加深，近似误差以指数速度减小。然而，考虑到在(5)中分解的界限，深层神经网络并不保证良好的泛化能力，因为(7)中的均匀覆盖熵界限在$m$上是线性增长的。通过对$N$和$m$进行适当选择，结合(5)和(7)的结果，可以得出在(4)中的经验风险最小化器$\widehat{f}_{n}$可以达到过度风险的最优值，即在 Donoho 和 Johnstone (1998)中为$\mathcal{O}(n^{-2r/(2r+d)})$。

避免维度诅咒。然而，在高维输入（如图像）下，最优值可能会非常缓慢，这无法解释深度神经网络的经验成功。基于此，假设回归函数$f_{\rho}$具有特殊结构是自然的；即要估计的回归函数$f_{\rho}$在(2)具有层次化组合结构。

|  | $\displaystyle f_{\rho}=g_{q}\circ g_{q-1}\circ g_{q-2}\circ\dots\circ g_{0},$ |  |
| --- | --- | --- |

设 $g_{i}:[a_{i},b_{i}]^{d_{i}}\rightarrow{[a_{i+1},b_{i+1}]^{d_{i+1}}}$。用 $g_{i}=(g_{ij})^{\text{T}}_{j=1,\dots,d_{i+1}}$ 表示 $g_{i}$ 的分量，并且让 $t_{i}$ 为每个 $g_{ij}$ 依赖的最大变量数量。这个设置导致 $t_{i}\leq d_{i}$。$g_{i}$ 的 $d_{i+1}$ 个分量属于 $r_{i}$-Hölder 类。最终，考虑的基础函数空间是

|  | $\displaystyle\mathcal{G}(q,\mathbf{d},\mathbf{t},\mathbf{r},K):=\big{\{}f_{\rho}=g_{q}$ | $\displaystyle\circ g_{q-1}\circ\dots\circ g_{0}:g_{i}=(g_{ij})_{j}:[a_{i},b_{i}]^{d_{i}}\rightarrow{[a_{i+1},b_{i+1}]^{d_{i+1}}},$ |  |
| --- | --- | --- | --- |
|  |  | $\displaystyle g_{ij}\in\mathcal{H}^{r_{i}}([a_{i},b_{i}]^{t_{i}},K),\quad\forall&#124;a_{i}&#124;,&#124;b_{i}&#124;\leq K\big{\}},$ |  |

其中 $\mathbf{d}:=(d_{0},\dots,d_{q+1})$，$\mathbf{t}:=(t_{0},\dots,t_{q})$，$\mathbf{r}:=(r_{0},\dots,r_{q})$。根据 Juditsky 等人 (2009)；Ray 和 Schmidt-Hieber (2017) 的研究，$f_{\rho}$ 的诱导光滑度是如下推导的：

|  | $\displaystyle r_{i}^{\star}:=r_{i}\prod_{\ell=i+1}^{q}\big{(}r_{\ell}\wedge 1\big{)},\quad\forall i\in\{0,\dots,q\}.$ |  | (8) |
| --- | --- | --- | --- |

在 Schmidt-Hieber (2020) 的定理 $3$ 中，证明了 $\phi_{n}:=\max_{i=0,\dots,q}n^{-\frac{2r^{\star}_{i}}{2r^{\star}_{i}+t_{i}}}$ 是在有趣的区域 $t_{i}\leq\text{min}\big{(}d_{0},\dots,d_{i-1}\big{)}$ 下，$\mathcal{G}(q,\mathbf{d},\mathbf{t},\mathbf{r},K)$ 类别的最小极大最优速率。该区域避免了 $t_{i}$ 大于输入维度 $d_{0}$。在回归函数的此设置下，作者证明存在一个经验风险最小化器 $\widehat{f}_{n}\in\mathcal{F}(L,\mathbf{p},\mathcal{N})$，其中 $L\asymp\log n$，$\mathbf{p}_{\text{max}}\asymp n^{C}$ 且 $C\geq 1$，$\mathcal{N}\asymp n\phi_{n}\log n$，使其能够实现接近最小极大最优速率，即对过剩风险的收敛为 $C^{\prime}\phi_{n}L\log^{2}n$。常数因子 $C^{\prime}$ 依赖于 $q,\mathbf{d},\mathbf{t},\mathbf{r},K$。重要的是，他们证明了经典的统计方法如小波不能达到最小极大速率，展示了神经网络在估计 $f_{\rho}\in\mathcal{G}(q,\mathbf{d},\mathbf{t},\mathbf{r},K)$ 上的优越适应性。

后续有若干备注。首先，速率 $\phi_{n}$ 依赖于有效维度 $t_{i}$，该维度可能远小于环境维度 $d_{0}$，这表明神经网络可以规避维度灾难。其次，深度 $L$ 应选择与样本大小按 $\log n$ 比例缩放。第三，宽度 $\mathbf{p}_{\text{max}}$ 可以选择与平滑指标无关。最后，结果表明对统计性能重要的不是样本大小，而是正则化的数量。这一点通过有效参数数量 $\mathcal{N}\asymp n\phi_{n}\log n\ll n$ 明确反映出来。

|  | Schmidt-Hieber (定理 5) | Lu 等 (定理 1.1) | Jiao 等 (推论 3.1) |
| --- | --- | --- | --- |
| 深度 | $\mathcal{O}(\lceil\log_{2}(r\vee d)\rceil)$ | $\mathcal{O}(r^{2}+d)$ | $\mathcal{O}((\lfloor r\rfloor+1)^{2})$ |
| 宽度 | $\mathcal{O}((d+\lceil r\rceil)(r+1)^{d})$ | $\mathcal{O}(r^{d+1}d3^{d})$ | $\mathcal{O}((\lfloor r\rfloor+1)^{2}3^{d}d^{\lfloor r\rfloor+1})$ |
| 近似速率 | $\mathcal{O}(6^{d}(r+1)^{d})$ | $\mathcal{O}(8^{r}(r+1)^{d})$ | $\mathcal{O}((\lfloor r\rfloor+1)^{2}d^{\lfloor r\rfloor+(r\vee 1)/2})$ |

表 1：构造的深度 ReLU 网络的深度、宽度和近似率中 $r$ 和 $d$ 依赖性的总结，适用于近似函数 $f\in W^{r}_{\infty}(\mathcal{C}^{d})$，参见 Schmidt-Hieber (2020)；Lu 等 (2021)；Jiao 等 (2021)。

预因子 $C^{\prime}$ 中对 $d$ 的明确依赖。自从 Schmidt-Hieber (2020) 发表之后，一系列工作进一步研究了通过深度 ReLU FNNs 对 $f\in W^{r}_{\infty}(\mathcal{C}^{d})$ 的近似和估计，其中 $\mathcal{C}^{d}$ 是一个 $d$ 维立方体。具体而言，Ghorbani 等人 (2020a) 指出，Schmidt-Hieber (2020) 研究的加法函数在估计误差的预因子 $C^{\prime}$ 中对 $d$ 具有指数依赖，要求样本数量 $n\succsim d^{d}$ 才能获得良好的收敛率。后来，Shen 等人 (2021) 和 Lu 等人 (2021) 跟踪了在近似误差以及建筑组件（即宽度 ($\mathcal{W}$) 和深度 ($L$)）中对 $d$ 的明确依赖，以近似 $f\in C(\mathcal{C}^{d})$（即在 $\mathcal{C}^{d}$ 上的 Lipschitz 连续函数）和 $f\in W^{r}_{\infty}(\mathcal{C}^{d})$。具体而言，Lu 等人 (2021) 改进了预因子 $\mathcal{O}(8^{r}(r+1)^{d})$，与 Schmidt-Hieber (2020) 对近似误差的 $\mathcal{O}(6^{d}(r+1)^{d})$ 相比。最近，Jiao 等人 (2021) 进一步改进了用于近似 $f\in W^{r}_{\infty}(\mathcal{C}^{d})$ 的预因子 $\mathcal{O}((\lfloor r\rfloor+1)^{2}d^{\lfloor r\rfloor+(r\vee 1)/2})$。在表 1 中，总结了 Schmidt-Hieber (2020); Lu 等人 (2021); Jiao 等人 (2021) 中构造的深度 ReLU 网络的深度、宽度和近似率的比较。在这一研究方向上，Suh 等人 (2022) 表明，当平滑指数 $r$ 按照数据维度 $d$ 增长时，即 $r=\mathcal{O}(d)$，深度 ReLU 网络可以避免灾难，只需 $\mathcal{O}(d^{2})$ 个活跃参数就能近似定义在单位球面上的 Hölder 空间中的函数。

通过深度 ReLU FNN 对 $f\in W_{\infty}^{r}(\mathcal{C}^{d})$ 的逼近。深度 ReLU FNN 对函数 $f\in W_{\infty}^{r}(\mathcal{C}^{d})$ 的逼近理论在文献中有着悠久的历史。代表性地，Mhaskar (1996) 显示 $f$ 可以在 $\varepsilon$ 逼近精度内被 $1$ 层神经网络以 $\mathcal{O}(\varepsilon^{-d/r})$ 个神经元和无限可微激活函数进行均匀逼近。后来，对于深度 ReLU 网络，Yarotsky (2017) 证明了网络中的 $\mathcal{N}$ 受限于 $\mathcal{O}(\varepsilon^{-d/r}\log\big{(}\frac{1}{\varepsilon}\big{)})$，深度为 $\mathcal{O}(\log(\frac{1}{\varepsilon}))$。他进一步证明了 $\mathcal{N}$ 的下界为 $\mathcal{O}(\varepsilon^{-d/r})$，这一结果得到了 DeVore 等人 (1989) 的支持。对于 $1\leq p\leq\infty$ 的 $f\in W_{p}^{r}(\mathcal{C}^{d})$，Petersen 和 Voigtlaender (2018) 显示存在一个具有有界和量化权重参数的深度 ReLU 网络，网络规模为 $\mathcal{O}(\varepsilon^{-d/r})$，且深度与 $\varepsilon$ 无关，可以实现 $L_{p}$ 范数下的 $\varepsilon$ 精度。对于 $f\in W_{\infty}^{r}(\mathcal{C}^{d})$ 的逼近，Schmidt-Hieber (2020) 证明了一个规模为 $\mathcal{O}(\varepsilon^{-d/r})$ 且权重参数有界的网络可以在 $L_{\infty}$ 范数下实现 $\varepsilon$ 逼近误差。

具有特殊结构的函数空间。Yarotsky (2017) 的结果暗示深度 ReLU 网络无法摆脱维度灾难，无法有效逼近 $f\in W_{\infty}^{r}(\mathcal{C}^{d})$。许多论文证明，通过考虑不同于 Sobolev 空间但定义在 $\mathcal{C}^{d}$ 上的函数空间，可以避免或减少维度效应。仅举几例，Mhaskar 等人 (2016) 研究了具有正则性 $r$ 的组合结构函数，可以通过一个具有 $\mathcal{O}(\varepsilon^{-2/r})$ 个神经元的神经网络在 $\varepsilon$ 精度内进行逼近。Suzuki (2018) 证明了具有 $\mathcal{O}(\varepsilon^{-1/r})$ 个神经元的深度 ReLU 网络可以避免混合光滑 Besov 空间中函数的维度灾难。Chen 等人 (2019a) 显示，当 $C^{r}$ 函数定义在等距嵌入于 $\mathbb{R}^{d}$ 的黎曼流形上且流形维度 $D$ 满足 $D\ll d$ 时，网络规模按 $\mathcal{O}(\varepsilon^{-D/r})$ 进行缩放。Montanelli 和 Du (2019) 以及 Blanchard 和 Bennouna (2022) 分别展示了深度和浅层 ReLU 网络打破了 Korobov 空间中的维度灾难。

超额风险的估计率。许多研究者还尝试通过在非参数回归框架下考虑特别设计的函数空间来应对神经网络的诅咒。我们仅提供了它们的一个不完整列表。这些结构包括加性岭函数（Fang 和 Cheng，2022），具有层次结构的复合函数空间（Schmidt-Hieber，2020; Han 等，2022），混合 Besov 空间（Suzuki，2018），以及定义在嵌入于$\mathbb{R}^{d}$的低维流形上的 Hölder 空间（Chen 等，2022a）。它们都表明，具有神经网络架构的函数估计器可以减轻诅咒，显示估计器的超额风险被有界在$\mathcal{O}(n^{-2r/(2r+D^{\prime})})$，其中$n$表示带噪声的数据集的大小，$D^{\prime}\ll d$是通过函数空间的特征唯一确定的内在维度，而与最小最大风险$\mathcal{O}(n^{-2r/(2r+d)})$（Donoho 和 Johnstone，1998）进行比较时，$f\in W_{\infty}^{r}(\mathcal{C}^{d})$。

### 2.3 通过全连接网络进行非参数分类

在本小节中，我们考虑通过全连接网络解决二分类问题。使用神经网络构建的分类器能够非常好地处理大规模高维数据，例如来自计算机视觉的面部图像，而传统统计方法通常效果不佳。我们将回顾一些试图为这种高维分类问题中的经验成功提供理论解释的论文，超越现有的统计文献。这是一个比非参数回归研究得较少的领域，尽管深度学习通常用于分类。

二分类任务。  设$\{X_{i},Y_{i}\}_{i=1}^{n}$为独立同分布的随机观测对，其中$X_{i}\in\mathbb{R}^{d}$且$Y_{i}\in\{0,1\}$。记$P_{X}$为$X_{i}$的概率分布，$\pi=\pi_{X,Y}$为$(X,Y)$的联合分布。在分类问题中，主要关注的是估计决策规则，该规则通过一个集合$G$来确定。本文假设$G$是$\mathbb{R}^{d}$的一个 Borel 子集，其中如果$X\in G$则$Y=1$，如果$X\notin G$则$Y=0$。与$G$相关的误分类风险由下式给出：

|  | $\displaystyle R(G):=P(Y\neq\mathbbm{1}(X\in G))=\mathbb{E}[(Y-\mathbbm{1}(X\in G))^{2}].$ |  |
| --- | --- | --- |

众所周知，贝叶斯分类器可以最小化$R(G)$，记为$G^{*}_{\pi}=\{x:\eta^{\star}(x)\geq 1/2\}$，其中$\eta^{\star}(x)=P(Y=1|X=x)$。然而，由于我们没有关于联合分布$\pi$的信息，直接找到$R(G)$的最小化器是困难的。有两种方法可以绕过这个困难。给定数据集$\{X_{i},Y_{i}\}_{i=1}^{n}$，第一种方法是直接估计最小化经验风险的集合；

|  | $\displaystyle R_{n}(G)=\frac{1}{n}\sum_{i=1}^{n}\big{(}Y_{i}-\mathbbm{1}(X_{i}\in G)\big{)}^{2}.$ |  |
| --- | --- | --- |

我们将 $R_{n}(G)$ 的最小化器表示为 $\widehat{G}_{n}$。第二种方法是估计回归函数 $\widehat{\eta}(x)$，然后将 $\widehat{\eta}(x)$ 插入到集合 $G$ 中，记作 $\widehat{G}_{n}:=\{x\in\mathbb{R}^{d}:\widehat{\eta}(x)\geq 1/2\}$。在这些设置下，我们关心 $R(\widehat{G}_{n})$ 收敛到 $R(G_{\pi}^{*})$ 的速度，随着 $n\rightarrow{\infty}$。注意，这两种方法不同在于它们施加了不同的假设以推导 $R(\widehat{G}_{n})$ 收敛到 $R(G_{\pi}^{*})$ 的速率。

现在，我们陈述三个通常施加在联合分布 $\pi$ 上的假设。

1.  1.

    决策集的复杂性假设 (CAD) 通过假设类 $\mathcal{G}$ 具有适当界限的 $\epsilon$-熵来表征贝叶斯分类器 $G_{\pi}^{\star}(\subset\mathcal{G})$ 的边界光滑性。

1.  2.

    回归函数的复杂性假设 (CAR) 指回归函数 $\eta^{\star}(x)$ 足够光滑，并且属于具有适当界限的 $\epsilon$-熵的函数类 $\Sigma$。

1.  3.

    边际假设 (MA) 描述了 $\eta^{\star}(x)$ 在决策边界附近（即 $\eta^{\star}(x)=1/2$）的行为。具体来说，假设参数 $q(\geq 0)$ 描述了回归函数与 $1/2$ 的距离有多远。$q$ 越大，$\eta^{\star}(x)$ 离 $1/2$ 的界限就越远。

对于那些对每个假设的严格处理感兴趣的读者，我们推荐 Mammen 和 Tsybakov (1999)；Tsybakov (2004)；Audibert 和 Tsybakov (2007) 及其中的参考文献。请注意，一般来说，假设 (CAR) 和 (CAD) 之间没有关联。实际上，$G^{*}$ 具有光滑边界并不意味着 $\eta^{\star}(x)$ 是光滑的，反之亦然。然而，正如 Audibert 和 Tsybakov (2007) 所指出的，$\eta^{\star}(x)$ 的光滑度和 (MA) 参数 $q$ 不能同时很大；当光滑的 $\eta^{\star}(x)$ 达到水平 $1/2$ 时，它不能从这个水平上过于突然地“起飞”。

神经网络上的结果。该表总结了研究神经网络二分类问题的超额风险收敛速率的工作中的设置和结果。此后，$\alpha>0$ 表示 CAR 中目标函数类 $(\Sigma)$ 或 CAD 中边界类 $(\mathcal{G})$ 的光滑度指数，$q>0$ 表示边际假设 (MA) 中指数中的项。

| 参考文献 | 函数空间 | 损失 | 条件 | 速率 |
| --- | --- | --- | --- | --- |
| Kim et al. (2021) | ReLU FNNs | Hinge | MA, CAD | $\mathcal{O}\bigg{(}n^{-\frac{\alpha(q+1)}{\alpha(q+2)+(d-1)(q+1)}}\bigg{)}$ |
| MA, CAR | $\mathcal{O}\bigg{(}n^{-\frac{\alpha(q+1)}{\alpha(q+2)+d}}\bigg{)}$ |
| 冯等 (2021) | ReLU CNNs | Hinge | CAR | $\mathcal{O}\bigg{(}n^{-\frac{r}{2\beta(d-1)+r(2-\tau)}}\bigg{)}$ |
| p-范数 | $\mathcal{O}\bigg{(}n^{-\frac{pr}{2(\beta+1)(d-1)+2pr(2-\tau)}}\bigg{)}$ |
| 2-范数 | MA, CAR | $\mathcal{O}\bigg{(}n^{-\frac{2rq}{(2+q)((\beta+1)(d-1)+2\tau)}}\bigg{)}$ |
| 沈等 (2022) | Hinge | MA, CAR | $\mathcal{O}\bigg{(}n^{-\frac{r(q+1)}{d+2r(q+1)}}\bigg{)}$ |
| Logistic | CAR | $\mathcal{O}\bigg{(}n^{-\frac{r}{2d+4r}}\bigg{)}$ |
| 最小二乘法 | $\mathcal{O}\bigg{(}n^{-\frac{4r}{3d+16r}}\bigg{)}$ |
| 周和霍 (2023) | ReLU FNNs | Hinge |

&#124; MA: &#124;

&#124; GMM &#124;

| $\mathcal{O}\bigg{(}n^{-\frac{q+1}{q+2}}\bigg{)}$ |
| --- |
| Ko 等 (2023) | ReLU FNNs | Logistic |

&#124; MA, CAR: &#124;

&#124; BA &#124;

| $\mathcal{O}\bigg{(}n^{-\frac{q+1}{3(q+2)}}\bigg{)}$ |
| --- |
| 胡等 (2020) | ReLU FNNs | 0-1 损失 |

&#124; MA, CAD: &#124;

&#124; 教师-学生 &#124;

| $\mathcal{O}\bigg{(}n^{-\frac{2}{3}}\bigg{)}$ |
| --- |

首篇显著论文 Kim 等 (2021) 证明了在平滑边界（CAD）和光滑回归（CAR）条件下，分别存在神经网络能够实现（几乎）最优的超额风险收敛速度。根据 Tsybakov (2004) 的证明，神经网络能够实现的最小最大最优速度为 $\mathcal{O}\big{(}n^{-\alpha(q+1)/[\alpha(q+2)+(d-1)q]}\big{)}$，而在 CAD 假设下的最优速度是可以实现的。他们的备注中提到，没有其他估计器能在这些场景下同时实现快速收敛速度。

最近的两项研究探讨了 ReLU 卷积神经网络的二分类问题，Feng 等人 (2021) 和 Shen 等人 (2022)。论文 Feng 等人 (2021) 考虑了 $p$-范数损失 $\phi(t):=\max\{0,1-t\}^{p}$，其中 $p\geq 1$，输入数据支持在球面 $\mathcal{S}^{d-1}$ 上。在论文中，在变化的幂条件下推导了近似误差界和超额风险界，并且目标函数类是 Sobolev 空间 $W_{p}^{r}(\mathcal{S}^{d-1})$，其中 $r>0$ 和 $p\geq 1$。在技术上，他们获得了 $L^{p}$ 范数下的近似误差，包括 $p=\infty$ 的情况。速率中涉及的两个量包括 $\beta=\max\{1,(d+3+r)/(2(d-1))\}$ 和 $\tau\in[0,1]$。论文 Shen 等人 (2022) 研究了带有凸损失函数类别的分类的超额风险收敛速率。感兴趣的目标函数同样来自 Sobolev 空间 $W_{p}^{r}([0,1]^{d})$，并且注意特征域是 $[0,1]^{d}$。在这种设定下，这项工作的最有趣的方面是他们跟踪了环境维度 $d$ 在大-$\mathcal{O}$ 符号中隐藏的前因子的依赖关系。他们展示了前因子在 $d$ 上是多项式依赖的。这应当与在小节 2.2 中介绍的工作进行对比，这些工作中前因子具有指数级的依赖。

上表中的最后三项给出了在不同问题设置下，$n$的指数中的无维速率。论文 Zhou 和 Huo (2023) 最近出现在 arXiv 上，研究了通过 ReLU FNNs 学习二元分类器的问题。这个结果的一个有趣方面是，与其他结果 Kim 等人 (2021)；Feng 等人 (2021)；Shen 等人 (2022) 相比，尽管特征域是无界的，但速率在维度和光滑度指标上均无关。获得这一结果的主要思路是利用特征的高斯分布是解析函数且具有快速衰减率这一事实，并且这一点可以通过 ReLU FNNs 捕捉到。另一篇论文 Ko 等人 (2023) 研究了类似的问题，但在不同的设置下。值得注意的是，他们对 Caragea 等人 (2023) 提出的 Barron 逼近 (BA) 空间感兴趣。与 Barron (1993) 中的经典 Barron 空间不同，后者本质上是 Lipschitz 连续函数集合的一个子集，这个空间甚至包括不连续函数，因此更为一般。对 BA 类函数施加了 CAR 假设。他们证明了通过 ReLU FNNs 估计的速率 $\mathcal{O}(n^{-\frac{q+1}{3(q+2)}})$ 是可以实现的，并且这一速率确实是极限最优的。注意到速率慢于参数化速率 $n^{-\frac{1}{2}}$，速率范围从 $n^{-\frac{1}{6}}$ 到 $n^{-\frac{1}{3}}$ 随 $q$ 从 $0$ 变化到 $\infty$。这归因于分布类的大小很大。

最后，Hu 等人 (2020) 研究了神经网络在 Mammen 和 Tsybakov 框架下的超额风险的收敛速率 (1999)。具体来说，论文的作者考虑了一个教师-学生框架。在这个设置中，一个神经网络（称为学生网络）在另一个神经网络（称为教师网络）生成的数据上进行训练。采用这种框架可以帮助理解深度神经网络的工作原理，因为它提供了一个具有界限复杂度的显式目标函数。此外，假设目标分类器是一个具有明确架构的教师网络，可能会对学生分类器需要什么具体架构以实现最佳超额风险提供见解。在这种设置下，给定学生网络比教师网络更深且更大时，经验 $0-1$ 损失最小化器的超额风险的收敛速率被推导为 $\tilde{\mathcal{O}}_{d}(n^{-\frac{2}{3}})$。作者使用符号 $\tilde{\mathcal{O}}_{d}$ 来表示速率依赖于输入维度 $d$ 的对数因子。当数据是可分的时，速率改善为 $\tilde{\mathcal{O}}_{d}(n^{-1})$。相比之下，正如 Mammen 和 Tsybakov (1999) 已经展示的那样，在 CAD 假设下，最佳速率是 $\mathcal{O}(n^{-\alpha(q+1)/[\alpha(q+2)+(d-1)q]})$。显然，这个速率受“维度诅咒”的影响，但有趣的是，当 $\alpha=1$ 和 $\beta\rightarrow{\infty}$ 时，与速率 $\tilde{\mathcal{O}}_{d}(n^{-\frac{2}{3}})$ 一致。如果进一步允许 $\alpha\rightarrow{\infty}$（对应于可分数据），上述经典速率恢复为 $\mathcal{O}(n^{-1})$。论文还表明，通过证明最小最大下界与上界（即 $\tilde{\mathcal{O}}_{d}(n^{-\frac{2}{3}})$）具有相同的阶，这个速率在最小最大意义上是不可改进的。

## 3 过度参数化的神经网络

我们考虑以下浅层神经网络 $f_{\mathbf{W}}(\mathbf{x})$，其中有 $M$ 个隐藏神经元：

|  | $\displaystyle f_{\mathbf{W}}(\mathbf{x})=\frac{\alpha}{M}\sum_{r=1}^{M}a_{r}\sigma(w_{r}^{\top}\mathbf{x}),$ |  | (9) |
| --- | --- | --- | --- |

其中 $\mathbf{x}\subset\mathcal{X}$ 是输入向量，$\{w_{r}\}_{r=1}^{M}$ 是第一隐藏层的权重，$\{a_{r}\}_{r=1}^{M}$ 是输出层的权重。我们用 $\mathbf{W}:=\{(a_{r},w_{r})\}_{r=1}^{M}$ 来表示这一对。网络动态的缩放因子是 $\frac{\alpha}{M}$。如果网络宽度（即 $M$）很小，则缩放因子对网络动态的影响可以忽略不计。但对于足够宽的网络（即，过参数化设置），缩放差异会导致动态行为完全不同。在本综述中，我们将重点关注两种特定的状态： (1) 神经切线核（Neural Tangent Kernel）状态（Jacot et al., 2018; Du et al., 2019; Arora et al., 2019b）其中 $\alpha=\sqrt{M}$，(2) 平均场（Mean Field）状态（Nitanda 和 Suzuki, 2017; Chizat 和 Bach, 2018; Mei et al., 2019）其中 $\alpha=1$。此外，我们还将回顾一项对这两种状态提供统一观点的工作。

在本节中，我们将重点回顾研究 $\ell_{2}$-损失函数的论文：

|  | $\displaystyle\mathcal{L}_{\mathbf{S}}\big{(}\mathbf{W}\big{)}=\frac{1}{2}\sum_{i=1}^{n}\big{(}y_{i}-f_{\mathbf{W}}(\mathbf{x}_{i})\big{)}^{2},$ |  | (10) |
| --- | --- | --- | --- |

我们通过以下梯度下降更新规则来更新模型参数 $\mathbf{W}$。设 $\mathbf{W}_{0}$ 为初始化的权重，我们考虑以下带有步长 $\eta>0$ 的梯度下降更新规则：

|  | $\mathbf{W}_{(k)}=\mathbf{W}_{(k-1)}-\eta\nabla_{\mathbf{W}}\big{(}\mathcal{L}_{\mathcal{S}}(\mathbf{W}_{(k-1)})\big{)},\qquad k\geq 1.$ |  | (11) |
| --- | --- | --- | --- |

### 3.1 神经切线核视角

在过去几年中，神经切线核（Neural Tangent Kernel, NTK）(Arora et al., 2019b; Jacot et al., 2018; Lee et al., 2018; Chizat 和 Bach, 2018) 已成为神经网络理论中的重要发现之一。NTK 类型理论的基本思想来自于观察到，在足够宽的神经网络中，经过梯度下降（GD）更新的模型参数在训练过程中保持接近其初始化值，因此网络的动态可以通过参数初始化时的泰勒一阶展开来近似；即，我们将神经网络的输出记作 $f_{\mathbf{W}_{(k)}}(\mathbf{x})\in\mathbb{R}$，其中输入为 $\mathbf{x}\in\mathcal{X}$，模型参数 $\mathbf{W}_{(k)}$ 在梯度下降的第 $k$ 次迭代中更新，那么 $f_{\mathbf{W}_{(k)}}(\mathbf{x})$ 随 $k\geq 1$ 的动态可以表示如下：

|  | $\displaystyle f_{\mathbf{W}_{(k)}}(\mathbf{x})=f_{\mathbf{W}_{0}}(\mathbf{x})+\langle\nabla f_{\mathbf{W}_{0}}(\mathbf{x}),\mathbf{W_{(k)}}-\mathbf{W}_{0}\rangle+o(\| \mathbf{W_{(k)}}-\mathbf{W}_{0} \|_{\text{F}}^{2}),$ |  | (12) |
| --- | --- | --- | --- |

其中$o(\|\mathbf{W_{(k)}}-\mathbf{W}_{0}\|_{\text{F}}^{2})$是一个随着网络宽度接近无穷大而趋近于$0$的小随机量，用于测量更新的模型参数与其初始化在 Frobenius 范数下的距离。具体来说，可以证明$\|\mathbf{W_{(k)}}-\mathbf{W}_{0}\|_{\text{F}}^{2}\leq\mathcal{O}(\frac{1}{\sqrt{M}})$，当$M$足够大时。（例如，参见 Du et al.（2018）中的 Remark $3.1$。）在这种设置下，（12）的右侧是关于网络参数$\mathbf{W}_{(k)}$的线性函数。因此，使用梯度下降对$\ell_{2}$-损失进行训练会导致关于由特征映射$\phi(\mathbf{x}):=\nabla_{\mathbf{W}_{0}}f(\mathbf{x})$诱导的（随机）核的核回归解，适用于所有$\mathbf{x}\in\mathcal{X}$。两个数据点$\mathbf{x}_{i},\mathbf{x}_{j}$处的特征映射内积记作$\mathbf{K}^{(M)}(\mathbf{x}_{i},\mathbf{x}_{j}):=\langle\phi(\mathbf{x}_{i}),\phi(\mathbf{x}_{j})\rangle$，对于所有$1\leq i,j\leq n$。

设定 ReLU 激活函数（即，$\sigma(\mathbf{x})=\max(\mathbf{x},0)$），$\mathbf{K}^{(M)}(\mathbf{x}_{i},\mathbf{x}_{j})$的显式形式如下：

|  | $\displaystyle\mathbf{K}^{(M)}(\mathbf{x}_{i},\mathbf{x}_{j}):=\frac{1}{M}\sum_{r=1}^{M}a_{r}^{2}\mathbf{x}_{i}\mathbf{x}_{j}\mathbb{I}\{w_{r}^{\top}\mathbf{x}_{i}\geq 0,w_{r}^{\top}\mathbf{x}_{j}\geq 0\}+\frac{1}{M}\sum_{r=1}^{M}\mathbb{I}\{w_{r}^{\top}\mathbf{x}_{i}\geq 0,w_{r}^{\top}\mathbf{x}_{j}\geq 0\}.$ |  |
| --- | --- | --- |

注意到$\mathbf{K}^{(M)}(\cdot,\cdot)$是一个关于初始化$a_{r}$和$\mathbf{w}_{r}$的随机矩阵，定义在$\mathcal{X}\times\mathcal{X}$上。它被证明在概率点上收敛到其确定性极限（即，$M\rightarrow{\infty}$）（Jacot et al.，2018；Arora et al.，2019b；Lee et al.，2018），并在特征空间$\mathcal{X}$上均匀收敛（Lai et al.，2023）。在文献中，该极限矩阵被称为 NTK，表示为$\{\mathbf{K}^{\infty}(\mathbf{x}_{i},\mathbf{x}_{j})\}_{1\leq i,j\leq n}\in\mathbb{R}^{n\times n}$。此后，我们写$\mathbf{K}^{\infty}$的特征分解为$\mathbf{K}^{\infty}=\sum_{j=1}^{n}\lambda_{j}\mathbf{v}_{j}\mathbf{v}_{j}^{\top}$，其中$\lambda_{1}\geq\dots\geq\lambda_{n}\geq 0$，对应的特征向量为$\mathbf{v}_{j}\in\mathbb{R}^{n}$。

后续出现了许多论文来解决 NTK 领域中神经网络的优化和泛化特性。其中，Du 等 (2018) 证明了当网络参数通过固定步长 $\eta=\mathcal{O}\big{(}\frac{\lambda_{0}}{n^{2}}\big{)}$ 的梯度下降更新时，浅层 ReLU 网络训练损失的线性收敛性。具体而言，作者随机初始化 $a_{r}\sim\text{Unif}\{-1,+1\}$ 和 $\mathbf{w}_{r}\sim\mathcal{N}(0,\mathcal{I})$，并在固定输出层的情况下训练 $\mathbf{w}_{r}$，得到了 $\mathbf{K}^{\infty}(\mathbf{x}_{i},\mathbf{x}_{j}):=\mathbb{E}_{\mathbf{W}\sim\mathcal{N}(0,\mathcal{I})}\big{[}\mathbf{x}_{i}\mathbf{x}_{j}\mathbb{I}\{w^{\top}\mathbf{x}_{i}\geq 0,w^{\top}\mathbf{x}_{j}\geq 0\}\big{]}$。这里，线性收敛率意味着 $k$-th 梯度下降更新时，训练损失相对于初始训练损失以几何速率衰减，这在 Du 等 (2018) 的定理 4.1 中明确陈述为：

|  | $\displaystyle\&#124;f_{\mathbf{W}_{(k)}}(\mathbf{x})-\mathbf{y}\&#124;_{2}^{2}\leq\bigg{(}1-\frac{\eta\lambda_{n}}{2}\bigg{)}^{k}\&#124;f_{\mathbf{W}_{(0)}}(\mathbf{x})-\mathbf{y}\&#124;_{2}^{2}.$ |  | (13) |
| --- | --- | --- | --- |

他们的结果要求网络宽度 $M$ 的数量级在 $\Omega\big{(}\frac{n^{6}}{\lambda_{n}}\big{)}$ 的范围内，衰减率依赖于 NTK 的最小特征值 $\lambda_{n}$。在几何衰减率的情况下，$\lambda_{n}$ 需要严格大于 $0$。

之后，出现了几次减少过度参数化规模的尝试。我们所知的工作之一是 Song 和 Yang (2019)，他们使用矩阵 Chernoff 界来将宽度大小减少到 $M=\Omega\big{(}\frac{n^{2}}{\lambda_{n}^{4}}\big{)}$，假设条件比数据非并行假设稍强。几篇后续工作 Allen-Zhu 等 (2018)；Du 等 (2019)；Zou 等 (2018)；Wu 等 (2019)；Oymak 和 Soltanolkotabi (2020)；Suh 等 (2021) 扩展了这些结果，展示了具有 $L$-隐藏层的深度 ReLU 网络训练损失的线性收敛性。关于上述论文中 $M$ 的过度参数化条件的简洁比较，请读者参考 Zou 和 Gu (2019) 的表 1。

受结果的启发（13），研究人员进一步研究了深度神经网络模型的光谱偏差，探讨了为什么神经动态学习函数的低频分量比学习高频分量更快。具体结果以特征值 $\mu_{1}\geq\mu_{2}\geq\dots$ 和对应的正交归一特征函数 $\phi_{1}(\cdot),\phi_{2}(\cdot),\dots$ 表述，这些特征函数属于由 $\mathbf{K}^{\infty}$ 诱导的积分算子 $\mathcal{L}_{\mathbf{K}^{\infty}}$：

|  | $\displaystyle\mathcal{L}_{\mathbf{K}^{\infty}}(f)(\mathbf{x}):=\int_{\mathcal{X}}\mathbf{K}^{\infty}(\mathbf{x},\mathbf{y})f(\mathbf{y})\rho(\mathbf{dy}),\quad\forall f\in\mathcal{L}^{2}(\mathcal{X}).$ |  |
| --- | --- | --- |

具体而言，Cao 等人（2019）；Bietti 和 Mairal（2019）提供了浅层 ReLU 网络中 $(\mu_{k})_{k}$ 的光谱衰减率，当 $x\in\mathcal{S}^{d-1}$ 配备均匀测度 $\mathbf{\tau}$（即 $\mathbf{x}\sim\text{Unif}(\mathcal{S}^{d-1})$）。²²2 注意，$\mathbf{K}^{\infty}$ 的特征值（即 $\{\lambda_{i}\}_{i=1}^{n}$）和 $\mathcal{L}_{k}$ 的特征值（即 $(\mu_{k})_{k}$）是不同的。

###### 命题 3.1.

（定理 $4.3$ 在 Cao 等人（2019），Bietti 和 Mairal（2019）的命题 5）对于对应于二层前馈 ReLU 网络的神经切线核，特征值 $(\mu_{k})_{k}$ 满足以下条件：

|  | <math   alttext="\displaystyle\begin{cases}\mu_{0},\mu_{1}=\Omega(1),\\ \mu_{K}=0,\quad\text{当 $k$ 为奇数时},\\

\mu_{k}=\Omega(k^{-d-1}),\quad k\gg d.\\

\end{cases}" display="inline"><semantics ><mrow ><mo  >{</mo><mtable columnspacing="5pt" rowspacing="0pt"  ><mtr ><mtd columnalign="left"  ><mrow ><mrow ><mrow ><msub ><mi >μ</mi><mn >0</mn></msub><mo >,</mo><msub ><mi >μ</mi><mn >1</mn></msub></mrow><mo >=</mo><mrow ><mi mathvariant="normal" >Ω</mi><mo lspace="0em" rspace="0em" >​</mo><mrow ><mo stretchy="false"  >(</mo><mn >1</mn><mo stretchy="false" >)</mo></mrow></mrow></mrow><mo >,</mo></mrow></mtd></mtr><mtr ><mtd columnalign="left"  ><mrow ><mrow ><msub ><mi >μ</mi><mi >K</mi></msub><mo >=</mo><mrow ><mn  >0</mn><mo rspace="1.167em"  >,</mo><mrow ><mtext >when </mtext><mi >k</mi><mtext > is odd</mtext></mrow></mrow></mrow><mo  >,</mo></mrow></mtd></mtr><mtr ><mtd columnalign="left"  ><mrow ><mrow ><mrow ><msub ><mi >μ</mi><mi >k</mi></msub><mo >=</mo><mrow ><mi mathvariant="normal" >Ω</mi><mo lspace="0em" rspace="0em" >​</mo><mrow ><mo stretchy="false"  >(</mo><msup ><mi >k</mi><mrow ><mrow ><mo >−</mo><mi >d</mi></mrow><mo >−</mo><mn >1</mn></mrow></msup><mo stretchy="false"  >)</mo></mrow></mrow></mrow><mo rspace="1.167em"  >,</mo><mrow ><mi >k</mi><mo >≫</mo><mi >d</mi></mrow></mrow><mo lspace="0em"  >.</mo></mrow></mtd></mtr></mtable></mrow><annotation-xml encoding="MathML-Content" ><apply ><csymbol cd="latexml"  >cases</csymbol><apply ><list ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝜇</ci><cn type="integer" >0</cn></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝜇</ci><cn type="integer" >1</cn></apply></list><apply ><ci >Ω</ci><cn type="integer" >1</cn></apply></apply><ci ><mtext >otherwise</mtext></ci><apply ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝜇</ci><ci >𝐾</ci></apply><list ><cn type="integer" >0</cn><ci ><mrow ><mtext >when </mtext><mi >k</mi><mtext > is odd</mtext></mrow></ci></list></apply><ci ><mtext >otherwise</mtext></ci><apply ><csymbol cd="ambiguous"  >formulae-sequence</csymbol><apply ><apply ><csymbol cd="ambiguous"  >subscript</csymbol><ci >𝜇</ci><ci >𝑘</ci></apply><apply ><ci >Ω</ci><apply ><csymbol cd="ambiguous"  >superscript</csymbol><ci >𝑘</ci><apply ><apply ><ci >𝑑</ci></apply><cn type="integer"  >1</cn></apply></apply></apply></apply><apply ><csymbol cd="latexml"  >much-greater-than</csymbol><ci >𝑘</ci><ci >𝑑</ci></apply></apply><ci ><mtext >otherwise</mtext></ci></apply></annotation-xml><annotation encoding="application/x-tex" >\displaystyle\begin{cases}\mu_{0},\mu_{1}=\Omega(1),\\ \mu_{K}=0,\quad\text{when $k$ is odd},\\ \mu_{k}=\Omega(k^{-d-1}),\quad k\gg d.\\ \end{cases}</annotation></semantics></math> |  |

衰减率在输入维度 $d$ 上呈指数级快速变化。具有特定衰减率的一个有趣好处是我们可以测量由核 $\mathbf{K}^{\infty}$ 诱导的再生核希尔伯特空间（RKHS）的大小。衰减率越慢，RKHS 越大，允许函数的高频信息被包含在函数空间中。这可以通过单位球面上的 RKHS 定义轻松看到：

|  | $\displaystyle\mathcal{H}^{\infty}:=\bigg{\{}f=\sum_{k\geq 0,\mu_{k}\neq 0}\sum_{j=1}^{\mathcal{N}(d,k)}a_{k,j}Y_{k,j}(\cdot)\quad\text{ s.t }\quad\|f\|_{\mathcal{H}^{\infty}}^{2}=\sum_{k\geq 0,\mu_{k}\neq 0}\sum_{j=1}^{\mathcal{N}(d,k)}\frac{a_{k,j}^{2}}{\mu_{k}}<\infty\bigg{\}},$ |  |
| --- | --- | --- |

其中 $Y_{k,j}$ 对于 $j=1,\dots,\mathcal{N}(d,k)$ 是 $d$ 个变量中 $k$ 次的线性独立球面谐波多项式。（我们参考 Frye 和 Efthimiou (2012) 以获得更详细的球面谐波多项式说明。）$\mu_{k}$ 衰减得越慢，越高次 $k$ 的多项式可以被包含在 $\mathcal{H}^{\infty}$ 中。

根据 $\mu_{k}$ 上指定的特征衰减率，Cao 等 (2019) 的定理 $4.2$ 证明了 NTK 范式下神经网络训练的谱偏差。具体来说，只要网络足够宽且样本量足够大，梯度下降法首先沿着具有较大特征值的 NTK 特征方向学习目标函数，然后学习与较小特征值对应的其余分量：

|  | $\displaystyle\frac{1}{\sqrt{n}}\left\| \mathbf{V}_{k}^{\top}(\mathbf{y}-\widehat{\mathbf{y}}^{(T)})\right\|_{2}\leq\frac{2}{\sqrt{n}}\big{(}1-\mu_{k}\big{)}^{T}\left\| \mathbf{V}_{k}^{\top}\mathbf{y}\right\|_{2},$ |  |
| --- | --- | --- |

其中 $\mathbf{V}_{k}:=(n^{-1/2}\phi_{j}(\mathbf{x}_{i}))_{n\times k}$。术语 $\|\mathbf{V}_{k}^{\top}(\mathbf{y}-\widehat{\mathbf{y}}^{(T)})\|_{2}$ 大致表示梯度下降法学习目标函数中前 $k$ 个特征值对应的分量的速度。（见 Cao 等 (2019)的引理 $4.1$。）这里，我们表示 $\mathbf{y}:=(f^{\star}(\mathbf{x}_{1}),\dots,f^{\star}(\mathbf{x}_{n}))$ 其中 $f^{\star}$ 是目标函数。类似地，Hu 等 (2019) 表明梯度下降法在早期训练阶段学习目标函数的线性分量。但关键的是，他们不要求网络具有不成比例的大宽度，且允许网络在训练后期逃脱核范式。

NTK 机制下神经网络的泛化。 在这里，我们回顾一些研究 (9) 泛化能力的重要工作。根据我们所知，Arora 等人 (2019a) 提出了理解 NTK 在神经网络泛化能力中作用的第一步。具体而言，他们展示了对于 $M=\Omega(\frac{n^{2}\log(n)}{\lambda_{\text{min}}})$ 和 $k\geq\tilde{\Omega}\big{(}\frac{1}{\eta\lambda_{\text{min}}}\big{)}$，$f_{\mathbf{W}_{(k)}}(\mathbf{x})$ 的 $\ell_{2}$ 总体损失有界于：

|  | $\displaystyle\mathbb{E}_{(\mathbf{x},\mathbf{y})\sim\mathcal{D}}\big{[}(f_{\mathbf{W}_{(k)}}(\mathbf{x})-\mathbf{y})^{2}\big{]}\leq\mathcal{O}\bigg{(}\sqrt{\frac{\mathbf{y}^{\top}(\mathbf{K}^{\infty})^{-1}\mathbf{y}}{n}}\bigg{)}.$ |  | (14) |
| --- | --- | --- | --- |

观察界限中的分子可以写成 $\mathbf{y}^{\top}(\mathbf{K}^{\infty})^{-1}\mathbf{y}:=\sum_{i=1}^{n}\frac{1}{\lambda_{i}}(\mathbf{v}_{i}^{\top}\mathbf{y})^{2}$。这意味着对应于小特征值 $\lambda_{i}$ 的投影 $\mathbf{v}_{i}^{\top}\mathbf{y}$ 应该对未见数据的良好泛化较小。确实，他们在 MNIST 和 CIFAR-10 数据集上进行了实证实验，显示对于真实标签 $\mathbf{y}$，投影 $\{(\mathbf{v}_{i}^{\top}\mathbf{y})\}_{i=1}^{n}$ 明显下降，而对于随机标签 $\mathbf{y}$，投影接近于均匀。（参见他们论文中的图 $1$。）

然而，这个界限 (14) 是在无噪声的情况下获得的，在存在噪声时变得无效。在这方面，在噪声设置下 (3), Nitanda 和 Suzuki (2020) 证明了

|  | $\displaystyle\mathbb{E}\big{[}\&#124;f_{W_{(T)}}(\mathbf{x})-f^{\star}(\mathbf{x})\&#124;_{L_{2}}^{2}\big{]}\leq\mathcal{O}\big{(}T^{-\frac{2r\beta}{2r\beta+1}}\big{)},$ |  | (15) |
| --- | --- | --- | --- |

其中 $f^{\star}\in\mathcal{L}_{\mathbf{K}^{\infty}}^{r}(\mathcal{L}_{2}(\rho_{\mathbf{x}}))$ 且 $r\in[1/2,1]$。该速率是 minimax 最优的，比 Arora 等人 (2019a) 中的 $\mathcal{O}(\frac{1}{\sqrt{n}})$ 更快。该速率由两个控制参数 $\beta$ 和 $r$ 表征，其中 $\beta>1$ 控制 $\mathcal{H}^{\infty}$ 的复杂性，而 $r\in[1/2,1]$ 控制 $\mathcal{H}^{\infty}$ 子集的复杂性，目标函数 $f^{\star}$ 属于该子集。注意，这两个量 $\beta$ 和 $r$ 之间存在有趣的偏差-方差权衡。对于大的 $\beta$，整个空间 $\mathcal{H}^{\infty}$ 变小，而 $\mathcal{H}^{\infty}$ 的子空间需要尽可能大，以获得更快的收敛速率，反之亦然。

如以下工作 Hu 等人 (2021) 所述，(15) 中的速率要求网络宽度在 $n$ 上是指数级的。（他们没有在主要结果中指定依赖关系，但可以在他们的证明中检查。）Hu 等人 (2021) 在通过梯度下降估计网络参数时，将过参数化的大小减少到了 $\tilde{\Omega}(n^{6})$。该论文证明，过参数化的浅层 ReLU 网络需要 $\ell_{2}$-正则化，以使 GD 达到 minimax 收敛速率 $\mathcal{O}(n^{-\frac{d}{2d-1}})$。注意，这一结果与 (15) 一致，因为假设 $f^{\star}\in\mathcal{H}^{\infty}$ (即 $r=1/2$)，且 $\beta=\frac{d}{d-1}$（见 Hu 等人 (2021) 的引理 $3.1.$）。随后，Suh 等人 (2021) 将结果扩展到了 NTK 机制下的多层深度 ReLU 网络，显示深度网络也需要 $\ell_{2}$-正则化才能实现 minimax 速率。

### 3.2 NTK 的局限性和超越核机制

尽管对梯度下降在损失函数中的训练动态有很好的理论描述，Arora 等人 (2019b); Lee 等人 (2018); Chizat 和 Bach (1812) 通过实证研究发现，NTK 和实际训练之间存在显著的性能差距。这些差距在 Wei 等人 (2019); Allen-Zhu 和 Li (2019); Ghorbani 等人 (2020b); Yehudai 和 Shamir (2019) 的理论研究中得到了探讨，这些研究表明，NTK 的泛化误差明显高于针对特定数据分布和架构训练神经网络的泛化误差。在这里，我们介绍了两项工作：Ghorbani 等人 (2020b); Wei 等人 (2019)。

1.  1.

    Ghorbani 等人 (2020b) 给出了一个高度风格化的尖峰特征模型的示例。考虑以下情况：$\mathbf{x}=\mathbf{Uz_{1}}+\mathbf{U^{\perp}z_{2}}$，其中 $\mathbf{U}\in\mathbb{R}^{d\times d_{0}}$，$\mathbf{U}^{\perp}\in\mathbb{R}^{d\times(d-d_{0})}$，且 $[\mathbf{U}\mid\mathbf{U}^{\perp}]\in\mathbb{R}^{d\times d}$ 是一个正交矩阵。设信号维度 $d_{0}=\lfloor{d^{\eta}}\rfloor$，其中 $\eta\in(0,1)$，以使 $d_{0}\ll d$。在这里，我们将 $\mathbf{z}_{1}$ 称为信号特征，$\mathbf{z}_{2}$ 称为垃圾特征，其方差为 $\textbf{Cov}(\mathbf{z}_{1})=\text{SNR}_{f}\mathcal{I}_{d_{0}}$ 和 $\textbf{Cov}(\mathbf{z}_{2})=\mathcal{I}_{d-d_{0}}$，其中 $\text{SNR}_{f}=d^{\kappa}$，对于 $0\leq\kappa<\infty$。在这种设置下，噪声响应的形式为 $\mathbf{y}=\psi(\mathbf{Uz_{1}})+\varepsilon$，其中 $\varepsilon$ 是一些随机噪声。注意响应仅依赖于信号特征。他们推导并比较了在不同的 $\text{SNR}_{f}$ 水平下，神经网络（NN）、随机特征（RF）和神经切线（NT）模型中逼近 $\mathbf{z_{1}}$ 中 $\ell$-多项式所需的参数数量。

    $\mathcal{F}$  NN  RF NT $\inf_{f\in\mathcal{F}}\|f^{\star}-f\|_{L^{2}}^{2}$ $\text{SNR}_{f}=1$ $d^{\eta\ell}$ $d^{\ell}$ $d^{\ell}$ NN $>$ RF = NT $\text{SNR}_{f}>1$ $d^{\eta\ell}$ $d^{\eta\ell}$ $d^{\eta(\ell-1)+1}$ NN $\sim$ RF $>$ NT

    这里，NN 是一类浅层网络函数 $f_{NN}(\mathbf{x},a,\mathbf{W})=\sum_{r=1}^{M}a_{r}\sigma(\langle w_{r},\mathbf{x}\rangle)$ 其中 $a_{r}\in\mathbb{R}$ 和 $w_{r}\in\mathbb{R}^{d}$，RF（即 NT）是一类线性函数 $f_{RF}(\mathbf{x},a)=\sum_{r=1}^{M}a_{r}\sigma(\langle w_{r}^{0},\mathbf{x}\rangle)$ 其中 $a_{r}\in\mathbb{R}$。（即 $f_{NT}(\mathbf{x},\mathbf{W})=\sum_{r=1}^{M}\langle s_{r},\mathbf{x}\rangle\sigma^{\prime}(\langle w_{r}^{(0)},\mathbf{x}\rangle)$ 其中 $s_{r}\in\mathbb{R}^{d}$.）

    有趣的是，观察到 NN 模型的逼近能力与 $\text{SNR}_{f}$ 无关，而其他两个模型则受到 $\text{SNR}_{f}$ 的影响。在他们的数值模拟（图 $2$）中，他们还展示了较大的 $\text{SNR}_{f}$ 会导致 $\{\text{RF, NT}\}$ 的逼近能力增大，这在上表中有所体现。这也与 NT 模型的谱偏差一致，即该模型比高频分量更快地学习函数的低频分量。

1.  2.

    Wei 等人 (2019) 给出了一个 NTK 或任何核方法在统计上有限的有趣例子，而正则化神经网络具有更好的样本复杂度。考虑这样一个设置，我们有特征空间 $\mathbf{x}\in\mathbb{R}^{d}$，其中 $\mathbf{x}_{i}\sim\{\pm 1\}$，并且函数 $\mathbf{f}(\mathbf{x})=\mathbf{x}_{1}\mathbf{x}_{2}$ 仅仅是 $\mathbf{x}$ 的前两个参数的乘积。我们想通过 NTK 引起的 RKHS 中的函数 $\mathbf{f}^{\text{NTK}}(a;\mathbf{x})=\sum_{r=1}^{M}a_{r}\mathbf{K}^{\infty}(\mathbf{x}_{r},\mathbf{x})$ 和具有 ReLU 激活的两层神经网络中的函数 $\mathbf{f}^{\text{NN}}(\Theta;\mathbf{x})=\sum_{r=1}^{M}a_{r}\sigma(w_{r}^{\top}\mathbf{x})$ 来学习 $\mathbf{f}(\mathbf{x})$。分类器 $\mathbf{f}^{\text{NTK}}(a;\mathbf{x})$ 通过最小化平方损失得到，而 $\mathbf{f}^{\text{NN}}(\Theta;\mathbf{x})$ 通过 $\ell_{2}$-正则化的逻辑损失进行估计。在这种设置下，Wei 等人 (2019) 的定理 $2.1$ 读作：

    “函数 $\mathbf{f}^{\text{NTK}}(a;\mathbf{x})$ 需要 $n=\Omega(d^{2})$ 样本才能以 $\ll\Omega(1)$ 的误差学习问题。相比之下，正则化的 NN 函数 $\mathbf{f}^{\text{NN}}(\Theta;\mathbf{x})$ 只需要 $n=\mathcal{O}(d)$ 样本。”

    结果表明，正则化神经网络和核预测函数之间存在 $\Omega(d)$ 的样本复杂度差距。这个差距的主要直观理解是，正则化使得神经网络能够自适应地找到模型参数 $(a_{r},w_{r})$，从而使得最佳估计器只选择隐藏层中的 $4$ 个神经元。³³3 利用 $|t|:=\sigma(t)+\sigma(-t)$ 对于 $t\in\mathbb{R}$，我们可以很容易地看到函数 $\mathbf{y}=\mathbf{x_{1}}\mathbf{x_{2}}$ 可以重写为 $\mathbf{y}=\frac{1}{2}\big{[}\sigma(\mathbf{x_{1}}+\mathbf{x_{2}})+\sigma(-\mathbf{x_{1}}-\mathbf{x_{2}})-\sigma(\mathbf{x_{1}}-\mathbf{x_{2}})-\sigma(\mathbf{x_{2}}-\mathbf{x_{1}})\big{]}$。 （注意，文献中已知 $\ell_{2}$-正则化的两层神经网络与 $\ell_{1}$-SVM 在 ReLU 特征上的关系 Nayshabur 等人 (2014)。）然而，使用 NTK 时，我们进行现有特征的密集组合，因为网络输出将始终涉及 $\sigma(w^{\top}\mathbf{x})$，其中 $w$ 是一个随机向量，因此它包含了 $\mathbf{x}$ 的所有分量。

超越核范畴。上述两项工作在一些高度理想化的设置下解释了神经网络相较于 NTK 范畴网络的优越性。还有几项理论尝试（Bai 和 Lee，2019；Allen-Zhu 等，2019）解释了通过基于梯度的方法估计的网络如何良好地泛化到未见过的数据，但关键的是它们不依赖于网络动态的线性化。论文 Bai 和 Lee (2019) 研究了通过将网络动态 $f_{\mathbf{W}}(\mathbf{x})$ 与高阶逼近相关联来优化和泛化具有平滑激活函数 $\sigma(\cdot)$ 的浅层网络。关键思想是找到 $\mathbf{W}:=\{(a_{r},w_{r})\}_{r=1}^{M}$ 的子集，使得泰勒展开中的主导项（12）不是线性项（即 $\langle\nabla f_{\mathbf{W}_{0}}(\mathbf{x}),\mathbf{W}-\mathbf{W}_{0}\rangle$），而是二次项（即 $\|\mathbf{W}-\mathbf{W}_{0}\|_{\text{F}}^{2}$）。作者通过在定制正则化损失上运行 SGD 找到了这样的 $\mathbf{W}$：

|  | $\displaystyle\mathbb{E}_{\mathbf{\Sigma},(\mathbf{x},\mathbf{y})\sim\mathcal{D}}\bigg{[}\ell(\mathbf{y},f_{\mathbf{W}_{0}+\mathbf{\Sigma W}_{r}}(\mathbf{x}))\bigg{]}+\lambda\&#124;\mathbf{W}\&#124;_{2,4}^{8}.$ |  | (16) |
| --- | --- | --- | --- |

损失的期望是对角矩阵 $\mathbf{\Sigma}$ 进行的，其中 $\Sigma_{rr}\sim\text{Unif}\{-1,1\}$ 在 $r\in[M]$ 上，这有助于抑制线性项的影响。正则化项 $\|\cdot\|_{2,4}^{8}$ 控制权重移动的距离为 $\mathcal{O}(M^{-1/4})$。作者展示了优化问题的地形（16），其具有一个非常好的特性，即尽管（16）的非凸性，每一个二阶驻点几乎都是全局最优。这些点可以通过 SGD 算法轻松找到。鉴于 $M$ 足够大，即 $M\gtrsim n^{4}$，他们进一步比较了三种不同场景下二次模型和线性模型的样本复杂度。三种场景中估计的真实函数分别是 (1) $f^{\star}(\mathbf{x})=\alpha(\beta^{\top}\mathbf{x})^{p}$ 对于 $\alpha\in\mathbb{R}$，$\beta\in\mathbb{R}^{d}$，和 $p=1\text{ 或者更高}$。 (2) $f^{\star}(\mathbf{x})=\mathbf{x}_{1}\mathbf{x}_{2}$，和 (3) $f^{\star}(\mathbf{x})=\langle\Theta^{\star},\mathbf{x}\mathbf{x}^{\top}\rangle$ 其中 $\Theta^{\star}\in\mathbb{R}^{d\times d}$ 是一个秩为 $r$ 的矩阵。我们在下面的表格中总结了结果。

$\mathcal{X}$ 二次模型 线性模型 $f^{\star}(\mathbf{x})=\alpha(\beta^{\top}\mathbf{x})^{p}$ 足够各向同性 $n\geq\tilde{\mathcal{O}}\bigg{(}\frac{p^{3}\alpha^{2}\|\beta\|_{2}^{2p}}{d\varepsilon^{2}}\bigg{)}$ $n\geq\tilde{\mathcal{O}}\bigg{(}\frac{p^{2}\alpha^{2}\|\beta\|_{2}^{2p}}{\varepsilon^{2}}\bigg{)}$ $f^{\star}(\mathbf{x})=\mathbf{x}_{1}\mathbf{x}_{2}$ $\{-1,+1\}^{d}$ $n\geq\tilde{\mathcal{O}}\bigg{(}\frac{d}{\varepsilon^{2}}\bigg{)}$ $n\geq\Omega(d^{2})$ $f^{\star}(\mathbf{x})=\langle\Theta^{\star},\mathbf{x}\mathbf{x}^{\top}\rangle$ $\text{Unif}(\mathbf{S}^{d-1}(\sqrt{d})$ $n\geq\tilde{\mathcal{O}}\bigg{(}\frac{dr^{2}}{\varepsilon^{2}}\bigg{)}$ $n\geq\tilde{\mathcal{O}}\bigg{(}\frac{d^{2}r^{2}}{\varepsilon^{2}}\bigg{)}$

在所有三种情况下，都表明二次模型的样本复杂度下界比线性 NTK 模型的小 $\tilde{\mathcal{O}}(d)$ 倍。这可能意味着神经动态的高阶近似的表达能力比线性模型更丰富。

### 3.3 平均场视角

“均场”视角是另一种有趣的范式，帮助我们理解神经网络模型的优化景观。回忆一下，均场（MF）状态下的神经网络动态对应于$\alpha=1$（见 9）。NTK（即$\alpha=\sqrt{M}$）和 MF（即$\alpha=1$）之间的尺度差异不仅导致了 GD 或 SGD 训练阶段完全不同的神经网络行为，还影响了可行的数学分析范围。我们在比较表 2 中总结了这些差异。

“均场”一词来源于数学物理中均场模型的类比，这些模型分析许多相同粒子的随机行为（见 Ryzhik 2023）。我们记$\theta_{r}:=(a_{r},w_{r})\in\mathbb{R}^{d+1}$，$\sigma_{\star}(\mathbf{x},\theta_{r}):=a_{r}\sigma(w_{r}^{\top}\mathbf{x})$（见 9）。权重对$\{\theta_{r}\}_{r=1}^{M}$被认为是$\mathcal{D}$维空间中的气体粒子集合，其中$\mathcal{D}:=d+1$。我们考虑有无限多的气体粒子，允许$M\rightarrow{\infty}$，这产生了以下神经动态的积分表示：

|  | $\displaystyle\frac{1}{M}\sum_{r=1}^{M}\sigma_{\star}(\mathbf{x};\mathbf{\theta}_{r})\xrightarrow{M\rightarrow\infty}\int\sigma_{\star}(\mathbf{x};\mathbf{\theta})\rho(d\mathbf{\theta}),$ |  | (17) |
| --- | --- | --- | --- |

其中$\theta_{r}\sim\rho$对于$r=1,\dots,M$。积分表示法（见 17）对于数学分析是方便的，因为它在测度$\rho$方面是线性的。例如，参见 Bengio 等人（2005）。

在这种设置下，开创性工作 Mei 等人（2018）研究了由$k$步单次 SGD（训练示例访问一次）更新的粒子$\theta^{(k)}\in\mathbb{R}^{\mathcal{D}}$的演变，损失函数为$\ell_{2}$。有趣的是，他们证明了粒子$\theta^{(k)}$的经验分布轨迹，记作$\widehat{\rho}^{(M)}_{k}:=\frac{1}{M}\sum_{r=1}^{M}\delta_{\theta^{(k)}_{r}}$，在$k\rightarrow{\infty}$和$M\rightarrow{\infty}$时，弱收敛于确定性极限$\rho_{t}\in\mathcal{P}(\mathbb{R}^{\mathcal{D}})$。测度$\rho_{t}$是以下非线性偏微分方程（PDE）的解：

|  | $\displaystyle\partial_{t}\rho_{t}=\nabla_{\mathbf{\theta}}\cdot\big{(}\rho_{t}\nabla_{\mathbf{\theta}}\mathbf{\Psi}(\mathbf{\theta};\rho_{t})\big{)},\qquad\mathbf{\Psi}(\mathbf{\theta};\rho_{t}):=\mathcal{V}(\mathbf{\theta})+\int\mathcal{U}(\mathbf{\theta},\bar{\mathbf{\theta}})\rho_{t}(d\bar{\mathbf{\theta}}),$ |  | (18) |
| --- | --- | --- | --- |
|  | $\displaystyle\qquad\mathcal{V}(\mathbf{\theta}):=-\mathbb{E}\{\mathbf{y}\sigma_{\star}(\mathbf{x};\mathbf{\theta})\},\qquad\qquad\mathcal{U}(\mathbf{\theta_{1}},\mathbf{\theta_{2}}):=\mathbb{E}\{\sigma_{\star}(\mathbf{x};\mathbf{\theta}_{1})\sigma_{\star}(\mathbf{x};\mathbf{\theta}_{2})\}.$ |  |

上述 PDE 描述了在由所有其他粒子的密度创建的力场中，每个粒子 $(\theta_{r})$ 的演变。设 $\mathcal{R}(\rho_{t}):=\mathbb{E}[(y-f(\mathbf{x};\rho_{t}))^{2}]$，则我们有

|  | $\displaystyle\sup_{0\leq t\leq T}\big{&#124;}\mathcal{R}(\rho_{t})-\mathcal{R}_{M}(\rho_{\lfloor t/\varepsilon\rfloor})\big{&#124;}\leq e^{C(T+1)}\cdot\sqrt{\frac{1}{M}\vee\varepsilon}\cdot\sqrt{D+\log\frac{M}{\varepsilon}}.$ |  | (19) |
| --- | --- | --- | --- |

边界收敛到 $0$ 的条件是 (1) $M\gg D$，(2) $\eta:=\frac{\varepsilon}{2}\ll\frac{1}{D}$，以及 (3) PDE 在 $T=\mathcal{O}(1)$ 次迭代中收敛。值得注意的是，通用 ODE 近似要求步长 $\eta$ 小于模型中参数总数的数量级（即 $\eta\ll\frac{1}{MD}$），而在这种情况下，步长 $\eta\ll\frac{1}{D}$ 应该足够。此外，回顾一下样本量 $n$ 相当于一次 SGD 的迭代步数 $k:=\lfloor\frac{T}{\varepsilon}\rfloor$，其中 $T=\mathcal{O}(1)$。这意味着 $n=\mathcal{O}(D)\ll\mathcal{O}(MD)$ 应该足够以获得良好的近似。另一个值得注意的事实是，与核机制相比，权重 $\theta_{r}$ 的演变是非线性的，特别是在训练过程中，权重会远离其初始化值。实际上，在温和的假设下，我们可以表明，在足够小的步长 $\eta$ 下，在 mean-field 机制中，$\lim_{M\rightarrow\infty}\|\theta^{(k)}-\theta^{(0)}\|_{2}^{2}/M=\Omega(\eta^{2})$，而在线性机制中，$\sup_{t\geq 0}\|\theta^{(t)}-\theta^{(0)}\|_{2}^{2}/M=\mathcal{O}(n/(Md))$。见 Bartlett 等人 (2021)。

|  | NTK 机制 | MF 机制 |
| --- | --- | --- |
| 优点 |

&#124; 1\. 与实践中的缩放相同 &#124;

&#124; 2\. 有限时间收敛速率 &#124;

&#124; 3\. 泛化界限 &#124;

|

&#124; 1\. 不要求 $\theta^{(k)}$ 接近 $\theta^{(0)}$ &#124;

&#124; 2\. 潜在学习更大类的函数 &#124;

|

| 缺点 | 需要 $\theta^{(k)}$ 接近 $\theta^{(0)}$ |
| --- | --- |

&#124; 1\. 与实践中的缩放不同 &#124;

&#124; 2\. 无有限时间收敛速率 &#124;

&#124; 3\. 无泛化界限 &#124;

|

表 2：NTK 与 Mean-Field 机制

尽管通过 DD 对 SGD 动态进行了很好的表征，但在 (19)中的界限仍有改进的空间；神经元的数量 $M$ 依赖于环境数据维度 $d$，而该界限仅适用于短收敛迭代的 SGD，即 $T=\mathcal{O}(1)$。后续工作 Mei 等人 (2019) 尝试解决这些挑战。特别地，他们证明了存在一个常数 $K$，它只依赖于激活和数据分布的内在特征，使得以高概率，以下结果成立：

|  | $\displaystyle\sup_{0\leq t\leq T}\big{&#124;}\mathcal{R}(\rho_{t})-\mathcal{R}_{M}(\rho_{\lfloor t/\varepsilon\rfloor})\big{&#124;}\leq Ke^{K(T\eta)^{3}}\bigg{\{}\sqrt{\frac{\log(M)}{M}}+\sqrt{d+\log(M)}\sqrt{\eta}\bigg{\}}.$ |  | (20) |
| --- | --- | --- | --- |

这一界限的一个显著特点是，只要 $T\eta=\mathcal{O}(1)$ 和 $K=\mathcal{O}(1)$，神经元的数量只需选择 $M\gg 1$，平均场近似就能准确。条件 $T\eta=\mathcal{O}(1)$ 减少了对 $T$ 的指数依赖，并且界限不需要随着环境维度 $d$ 扩展。后来，同一组的研究人员将结果推广到多层设置中 Nguyen 和 Pham (2020)。

### 3.4 NTK 和平均场范围的统一视角

在前面的子章节中，我们讨论了神经网络在两种不同范围内的动态：NTK 和平均场。尽管两者都处于过参数化范围内，但动态的规模差异导致了完全不同的行为。受到这一观察的启发，已经有尝试给出这两种范围的统一视角。

我们知道的第一次尝试是 Chen 等人 (2020b)。本文的动机总结在上表中，同时也列出了 NTK 和均场视角的优缺点。如表 2 所述，MF 分析的一个警告是获取泛化界限的困难，但该视角允许参数远离其初始值。本文的关键思想是引入 NTK，这要求$\|\theta^{(k)}-\theta^{(0)}\|_{\text{2}}^{2}$ 变得很小。相反，他们在概率测度空间$\mathcal{P}(\mathbb{R}^{d})$上工作，最小化以下能量泛函，其中$f(\mathbf{x};\rho):=\alpha\int\sigma_{\star}(\mathbf{x};\mathbf{\theta})\rho(d\mathbf{\theta})$ 是神经动力学的积分表示，参见 (9)。

|  | $\displaystyle\rho^{\star}:=\operatorname*{arg\,min}_{\rho\in\mathcal{P}(\mathbb{R}^{d})}\bigg{\{}\frac{1}{n}\sum_{i=1}^{n}\big{(}\mathbf{y}_{i}-f(\mathbf{x}_{i};\rho)\big{)}^{2}+\lambda\mathcal{D}_{\textbf{KL}}(\rho\parallel\rho_{0})\bigg{\}},$ |  | (21) |
| --- | --- | --- | --- |

其中，超参数$\lambda>0$。在这里，$\rho^{\star}\in\mathcal{P}(\mathbb{R}^{d})$ 是 (21) 的全局最小化器。请注意，他们惩罚的是$\rho$与$\rho_{0}$之间的 KL 散度，而不是$\theta^{(k)}$与$\theta^{(0)}$之间的距离。目标函数的训练 (21) 通常通过 Wasserstein 梯度流实现，参见 Mei 等人 (2018)。请注意，带噪声的梯度下降（NGD）对应于参数空间中 Wasserstein 梯度流的离散化版本，并且已经在 Mei 等人 (2018, 2019)；Chizat 和 Bach (2018) 中进行了广泛研究，NGD 算法近似了联合测度$\rho^{\star}$，这是 (18) 的解，并具有额外的扩散项。

在这种情况下，Chen 等人 (2020b) 展示了具有 $0-1$ 损失的二分类问题的泛化界限。（即 $\ell^{0-1}(y,y^{\prime}):=\mathbbm{1}(yy^{\prime}<0)$。）给定目标函数的形式为 $\mathbf{y}:=f(\mathbf{x};\rho_{\text{true}})$，泛化界限如下：

|  | $\displaystyle\mathbb{E}_{\mathcal{D}}\big{[}\ell^{0-1}\big{(}f(\rho^{\star},\mathbf{x}),\mathbf{y}\big{)}\big{]}\leq\underbrace{\tilde{\mathcal{O}}\bigg{(}\sqrt{\frac{\mathcal{D}_{\mathcal{X}^{2}}(\rho_{\text{true}}&#124;&#124;\rho_{0}\big{)}}{n}}\bigg{)}}_{\text{NTK}\big{(}\alpha=\mathcal{O}(\sqrt{M})\big{)}},\quad\underbrace{\tilde{\mathcal{O}}\bigg{(}\sqrt{\frac{\mathcal{D}_{\text{KL}}(\rho_{\text{true}}&#124;&#124;\rho_{0}\big{)}}{n}}\bigg{)}}_{\text{MF}\big{(}\alpha=\mathcal{O}(1)\big{)}}.$ |  | (22) |
| --- | --- | --- | --- |

这意味着当 $\alpha$ 在 (9) 很大时，即 $\alpha=\mathcal{O}(\sqrt{M})$（或 $\alpha=\mathcal{O}(1)$），通过噪声梯度下降（NGD）训练的无限宽两层神经网络可以学习函数类 $\mathcal{F}_{\mathcal{X}^{2}}$（或函数类 $\mathcal{F}_{\textbf{KL}}$）。这两个函数类定义如下：

|  | $\displaystyle\mathcal{F}_{\mathcal{X}^{2}}:=\bigg{\{}\int\sigma_{\star}(\mathbf{x};\mathbf{\theta})\rho(d\mathbf{\theta}):\mathcal{D}_{\mathcal{X}^{2}}(\rho\parallel\rho_{0})<\infty\bigg{\}},\quad\mathcal{F}_{\textbf{KL}}:=\bigg{\{}\int\sigma_{\star}(\mathbf{x};\mathbf{\theta})\rho(d\mathbf{\theta}):\mathcal{D}_{\textbf{KL}}(\rho\parallel\rho_{0})<\infty\bigg{\}},$ |  |
| --- | --- | --- |

其中 $\mathcal{D}_{\mathcal{X}^{2}}(\rho\parallel\rho_{0})$ 和 $\mathcal{D}_{\textbf{KL}}(\rho\parallel\rho_{0})$ 分别表示 $\rho$ 和 $\rho_{0}$ 之间的 $\mathcal{X}^{2}$ 和 KL 散度。由于 KL 散度小于 $\mathcal{X}^{2}$ 距离，可以检验 $\mathcal{F}_{\mathcal{X}^{2}}\subsetneq\mathcal{F}_{\textbf{KL}}$（符号 $\subsetneq$ 表示严格子集）。这意味着，通过 NGD 在平均场缩放下学习的两层神经网络可能比 NTK 缩放下的网络能够学习更大的函数类。

|  | 定义 | NTK | 平均场 (L=1) | 最大更新 ($\mu P$) |
| --- | --- | --- | --- | --- |

| $a_{\ell}$ | $W_{\ell}=M^{-a_{\ell}}w^{\ell}$ | $\begin{cases}0\qquad\ell=1\\ 1/2\quad\ell>1\end{cases}$ | $\begin{cases}0\quad\ell=1\\ 1\quad\ell=2\end{cases}$ | <math alttext="\begin{cases}-1/2\qquad\ell=1\\ 0\quad\qquad 2\leq\ell\leq L\\

1/2\quad\quad\ell=L+1\\

\end{cases}" display="inline"><semantics ><mrow ><mo  >{</mo><mtable columnspacing="5pt" rowspacing="0pt"  ><mtr ><mtd columnalign="left"  ><mrow ><mrow ><mrow ><mo >−</mo><mrow ><mn >1</mn><mo >/</mo><mn >2</mn></mrow></mrow><mi mathvariant="normal"  >ℓ</mi></mrow><mo >=</mo><mn >1</mn></mrow></mtd></mtr><mtr ><mtd columnalign="left"  ><mrow ><mrow ><mn >0</mn><mn >2</mn></mrow><mo >≤</mo><mi mathvariant="normal"  >ℓ</mi><mo >≤</mo><mi >L</mi></mrow></mtd></mtr><mtr ><mtd columnalign="left"  ><mrow ><mrow ><mrow ><mn >1</mn><mo >/</mo><mn >2</mn></mrow><mi mathvariant="normal"  >ℓ</mi></mrow><mo >=</mo><mrow ><mi >L</mi><mo >+</mo><mn >1</mn></mrow></mrow></mtd></mtr></mtable></mrow><annotation-xml encoding="MathML-Content" ><apply ><csymbol cd="latexml" >cases</csymbol><apply ><list ><apply ><apply ><cn type="integer" >1</cn><cn type="integer" >2</cn></apply></apply><ci >ℓ</ci></list><cn type="integer" >1</cn></apply><ci ><mtext >otherwise</mtext></ci><apply ><apply ><list ><cn type="integer" >0</cn><cn type="integer" >2</cn></list><ci >ℓ</ci></apply><apply ><ci >𝐿</ci></apply></apply><ci ><mtext >otherwise</mtext></ci><apply ><list ><apply ><cn type="integer" >1</cn><cn type="integer" >2</cn></apply><ci >ℓ</ci></list><apply ><ci >𝐿</ci><cn type="integer" >1</cn></apply></apply><ci ><mtext >otherwise</mtext></ci></apply></annotation-xml><annotation encoding="application/x-tex" >\begin{cases}-1/2\qquad\ell=1\\ 0\quad\qquad 2\leq\ell\leq L\\ 1/2\quad\quad\ell=L+1\\ \end{cases}</annotation></semantics></math> |

| $b_{\ell}$ | $w_{\alpha\beta}^{\ell}\sim\mathcal{N}(0,M^{-2b_{\ell}})$ | 0 | 0 | 1/2 |
| --- | --- | --- | --- | --- |
| $c_{\ell}$ | $LR=\eta M^{-c}$ | 0 | -1 | 0 |

另一项工作 Yang 和 Hu (2020) 提供了一个统一的框架，涵盖了在 NTK 和 MF 机制下引发神经动力学的参数化。在重度过参数化的设置下（即网络宽度非常大），这两种机制之间的主要差异来源于 GD 或 SGD 中初始化权重参数和学习率的不同尺度。在论文中，提出的 abc-参数化提供了关于如何选择这些参数尺度的指导。具体来说，请回顾定义为 $L+1$ 层的全连接网络 (1)。在这种情况下，网络的宽度在所有层中保持一致，为 $M$。参数化由一组数字 $\{a_{\ell},b_{\ell}\}_{\ell}\cup\{c\}$ 给出。对 $(a_{\ell},b_{\ell})$ 控制层之间初始化权重参数的尺度，而 $c$ 是与 SGD 的学习率相关的参数。

参数化如下所示：

1.  1.

    参数化 $W_{\ell}=M^{-a_{\ell}}w^{\ell}$ 其中 $w^{\ell}$ 被训练而不是 $W_{\ell}$，适用于所有 $\ell\in[L+1]$。

1.  2.

    初始化每个$w_{\alpha\beta}^{\ell}\sim\mathcal{N}(0,M^{-2b_{\ell}})$。

1.  3.

    SGD 学习率为$\eta M^{-c}$，其中$\eta>0$与宽度无关。

借用论文的符号，我们将$\mathbf{x}_{t}^{\ell}(\mathbf{\xi})$表示为全连接网络第$\ell$层隐藏层的输出（经过激活函数处理后），输入为$\mathbf{\xi}\in\mathbb{R}^{d}$，用于第$t$次 SGD 更新。论文定义了差异向量$\Delta\mathbf{x}_{t}^{\ell}(\mathbf{\xi}):=\mathbf{x}_{t}^{\ell}(\mathbf{\xi})-\mathbf{x}_{0}^{\ell}(\mathbf{\xi})$，适用于所有$\ell\in[L+1]$，其$r$符号为：

|  | $\displaystyle r:=\min(b_{L+1},a_{L+1}+c)+a_{L+1}+c+\min_{\ell=1,\dots,L}[2a_{\ell}-\mathbbm{1}(\ell\neq 1)].$ |  | (23) |
| --- | --- | --- | --- |

在这种设置下，他们考虑了参数化状态$\{a_{\ell},b_{\ell}\}_{\ell}\cup\{c\}$，其中每个$\mathbf{x}_{t}^{\ell}(\mathbf{\xi})$的坐标在所有$\ell\in[L+1]$时不会爆炸。具体来说，考虑当$\Delta\mathbf{x}_{t}^{\ell}(\mathbf{\xi}):=\Theta(M^{-r})$时，$r\geq 0$的状态。这与对$\{a_{\ell},b_{\ell}\}_{\ell}\cup\{c\}$的额外线性约束有关，这些约束确保网络在初始化和训练过程中不会爆炸。（有关细节，请参见杨和胡的定理 3.2（2020））。通过这些约束形成的高维多面体称为稳定的 abc-参数化区域，因为在 SGD 训练过程中，网络动态不会爆炸，他们进一步证明了稳定区域分为两部分，其中动态在无限宽度极限（即$M\rightarrow\infty$）中发生变化（非平凡）或不发生变化（平凡）。非平凡稳定的 abc-参数化可能出现在多面体的以下两个面上：

|  | $\displaystyle a_{L+1}+b_{L+1}+r=1\quad\text{或}\quad 2a_{L+1}+c=1.$ |  | (24) |
| --- | --- | --- | --- |

在这一区域，无限宽度极限要么（1）允许最后一层隐藏层$\mathbf{x}^{L}(\mathbf{\xi})$在$r=0$时非平凡地演化（MF 状态），要么（2）由$r>0$的核梯度下降描述（NTK 状态），但不能同时成立。

上表总结了 NTK 和 MF 区域的$(a_{\ell},b_{\ell})\cup\{c\}$的相应设置。它们只关注与$M$的比例，并忽略对内在维度$d$的依赖。对于 NTK 的设置与 Du et al.(2019)中的定理$5$相匹配，其中$W_{\ell}$的条目是从$\mathcal{N}(0,1/M)$中绘制的，宽度无关的$\eta>0$。在 NTK 区域中看到$\ell=1$时为$a_{\ell}=0$的原因是为了确保网络中每个隐藏层的输出量都是常数，以便参数化处于稳定状态。对于 MF 区域，Mei et al.(2018, 2019)为浅层神经网络提供了宽度无关的权重初始化和学习率的参数设置。请注意输出权重层$(\ell=2)$中的$\frac{1}{M}$比例与 SGD 学习速率的$M$比例相互抵消。

尽管论文中未提到，我们推测这些操作的原因是将参数化放在 MF 区域，以满足约束条件(24). 对于 NTK 的$\{a_{\ell},b_{\ell}\}_{\ell}\cup\{c\}$对满足$r=\frac{1}{2}$，意味着动态是通过核梯度下降描述的，而对于 MF 的对满足$r=0$，允许特征学习。本文的作者展示了在 MF 区域中的特征学习动态可以扩展到多层设置，在这里他们将相应的参数化称为“最大更新参数化（$\mu P$）”。这种参数化在整个网络的$\infty$宽度极限下启用特征学习，属于“最大”意味着特征学习在整个网络层中都被启用。 正如在引言中提到的，特征学习是现代深度学习的本质，使得诸如迁移学习或在大语言模型（LLM）中进行微调等技术成为可能，而在这种情况下，确切的神经动力学在数学上是可解的。

## 生成模型的 4 个统计保证

### 4.1 生成对抗网络（GAN）

在过去的十年里，生成对抗网络 (GANs)（Goodfellow 等人，2014）作为一种重要的无监督学习方法脱颖而出，因其能够学习数据分布并高效地从中采样。GAN 的主要目标是通过生成器和鉴别器之间的对抗训练来学习目标分布 $X\sim\nu$。在这里，生成器从先验分布如高斯或均匀分布（即 $\mathcal{Z}\sim\pi$）中获取输入，并通过变换映射 $g:\mathcal{Z}\rightarrow g(\mathcal{Z})$ 进行推进。在这篇开创性论文中，随机变量 $g(\mathcal{Z})$ 的分布被称为隐式分布 $\mu$。生成器的主要目标是生成来自 $\mu$ 的合成数据，这些数据与目标分布中的样本非常相似。

生成器和鉴别器之间的对抗训练通过优化以下关于生成器类别 $\mathcal{G}$ 和鉴别器类别 $\mathcal{F}$ 函数的最小最大问题来实现：

|  | $\displaystyle(g^{\star},f^{\star})\in\operatorname*{arg\,min}_{g\in\mathcal{G}}\max_{f\in\mathcal{F}}\bigg{\{}\mathbb{E}_{\mathcal{Z}\sim\pi}f(g(\mathcal{Z}))-\mathbb{E}_{X\sim\nu}f(X)\bigg{\}}.$ |  | (25) |
| --- | --- | --- | --- |

实际上，上述期望值可以通过来自 $\nu$ 的 $m$ 个训练数据和从 $\mu$ 中抽取的 $n$ 个样本进行近似。在 (25 ‣ 4 生成模型的统计保证 ‣ 深度学习的统计理论调查：近似、训练动态和生成模型")) 中的内层最大化问题是一个积分概率度量 (IPM,  Müller (1997))，它量化了关于对称函数类别的两个分布 $\mu$ 和 $\nu$ 之间的差异，即 $f\in\mathcal{F}$，则 $-f\in\mathcal{F}$；

|  | $\displaystyle d_{\mathcal{F}}(\mu,\nu)=\max_{f\in\mathcal{F}}\bigg{\{}\mathbb{E}_{x\sim\mu}f(x)-\mathbb{E}_{y\sim\nu}f(y)\bigg{\}}.$ |  | (26) |
| --- | --- | --- | --- |

当 $\mathcal{F}$ 被取为所有 $1$-Lipschitz 函数时，$d_{W_{1}}(\cdot,\cdot)$ 是 Wasserstein-$1$ 距离；当 $\mathcal{F}$ 是所有指示函数的类时，$d_{\text{TV}}(\cdot,\cdot)$ 是总变差距离；当 $\mathcal{F}$ 被取为神经网络的类时，$d_{\text{NN}}(\cdot,\cdot)$ 是“神经网络距离”（参见 Arora 等人 (2017)）。在这种设置下，来自 $\mathcal{G}$ 的生成器试图最小化 $\mu$ 和 $\nu$ 之间的 IPM。

GANs 的泛化。一个自然出现的问题是：“GANs 有效泛化意味着什么？”论文 Arora 等人 (2017) 为 GANs 的泛化提供了一个数学定义。

###### 定义 4.1.

设 $\widehat{\mu}_{n}$ 和 $\widehat{\nu}_{m}$ 为 $\mu$ 和 $\nu$ 的经验分布。对于某个通用化间隙 $\varepsilon>0$，如果以下条件以高概率成立；

|  | $\displaystyle\left\lvert d_{\mathcal{F}}(\mu,\nu)-d_{\mathcal{F}}(\widehat{\mu}_{n},\widehat{\nu}_{m})\right\rvert\leq\varepsilon,$ |  | (27) |
| --- | --- | --- | --- |

当 $n$ 依赖于 $\varepsilon$ 的多项式时，分布之间的发散度 $d_{\mathcal{F}}(\cdot,\cdot)$ 会泛化。

这意味着，如果通过 $n$ 个多项式生成的样本能够任意控制 $\mu$ 和 $\nu$ 的总体发散度与经验发散度之间的绝对差异，则 GAN 能够很好地泛化。相同的论文在这个定义下证明，GAN 无法在 Wasserstein-1 距离和 Jensen-Shannon 发散度方面泛化，因为需要 $n=\tilde{\mathcal{O}}(\varepsilon^{-\text{poly(d)}})$。但在神经网络距离方面，它能够很好地泛化，其中 $n=\tilde{\mathcal{O}}(p\log(L)\cdot\varepsilon^{-2})$，其中 $p$ 是判别神经网络中的参数总数，$L$ 是判别器对参数的 Lipschitz 常数。

尽管如 Chen 等人 (2020a)、Zhang 等人 (2017)、Arora 等人 (2017) 所指出，这一结果存在一些局限性：$(1)$ 样本复杂度涉及未知的判别器 Lipschitz 常数 $L$。$(2)$ 小的神经网络距离并不一定意味着两个分布是接近的。（参见 Arora 等人 (2017) 的第 $3.4$ 节）$(3)$ 样本复杂度与生成器类 $\mathcal{G}$ 的复杂度无关，前提是假设生成器能够足够好地逼近目标数据分布。$(4)$ 没有给出判别器网络的具体架构。一些论文 Zhang 等人 (2017)、Jiang 等人 (2018)、Bai 等人 (2018) 试图解决前两个局限性，其尝试在 Chen 等人 (2020a) 中得到了很好的总结。在这篇综述中，我们介绍了 Chen 等人 (2020a) 和 Liang (2021) 通过神经网络逼近理论的工具，具体解决了 $(3)$ 和 $(4)$ 中提出的问题。

GAN 的统计保证。请注意，判别器和生成器类中的函数可以是经典的非参数回归器，例如随机森林、局部多项式等，或者可以是由神经网络参数化的。在这里，我们关注后者，这种方法更为常用。具体地，我们将 $\mathcal{F}:=\{f_{\omega}(\cdot):\mathbb{R}^{d}\rightarrow\mathbb{R}\}$ 作为判别器类，将 $\mathcal{G}:=\{g_{\theta}(z):\mathbb{R}^{d}\rightarrow\mathbb{R}^{d}\}$ 作为生成器类，其中 $\omega$ 和 $\theta$ 分别表示相应类的网络参数，我们感兴趣的是通过最小化以下优化问题来估计这些参数：

|  | $\displaystyle(\widehat{\theta}_{m,n},\widehat{\omega}_{m,n})\in\operatorname*{arg\,min}_{\theta:g_{\theta}\in\mathcal{G}}\max_{\omega:f_{\omega}\in\mathcal{F}}\bigg{\{}\widehat{\mathbb{E}}_{m}f_{\omega}(g_{\theta}(\mathcal{Z}))-\widehat{\mathbb{E}}_{n}f_{\omega}(X)\bigg{\}},$ |  | (28) |
| --- | --- | --- | --- |

其中 $\widehat{\mathbb{E}}_{m}(\cdot)$（即 $\widehat{\mathbb{E}}_{n}(\cdot)$）表示具有 $m$ 个生成器样本的经验期望。（即 $n$ 个目标样本。）

Liang (2021) 总结了在 (28 ‣ 4 生成模型的统计保证 ‣ 深度学习的统计理论：近似、训练动态和生成模型的调查")) 中给出的生成器 $\widehat{\theta}_{m,n}$ 的最佳参数。Liang (2021) 研究了隐式分布估计器 $\mu_{\widehat{\theta}_{m,n}}$（即随机变量 $g_{\widehat{\theta}_{m,n}}(Z)$ 的分布）与目标分布 $\nu$ 在总变差距离上的接近程度。在假设鉴别函数是均匀有界的（即 $\|f_{\omega}\|_{\infty}\leq B$）的情况下，他们提供了以下的近似-随机误差分解基于的预言不等式：

|  | $\displaystyle\mathbb{E}d_{\text{TV}}^{2}(\nu,\mu_{\widehat{\theta}_{m,n}})$ | $\displaystyle\leq\underbrace{\frac{1}{2}\sup_{\theta}\inf_{\omega}\bigg{\|}\log\frac{p_{\nu}}{p_{\mu_{\theta}}}-f_{\omega}\bigg{\|}_{\infty}}_{:=A_{1}(\mathcal{F},\mathcal{G},\nu)}+\underbrace{\frac{B}{4\sqrt{2}}\cdot\inf_{\theta}\bigg{\|}\log\frac{p_{\mu_{\theta}}}{p_{\nu}}\bigg{\|}_{\infty}^{1/2}}_{:=A_{2}(\mathcal{G},\nu)}$ |  |
| --- | --- | --- | --- |
|  |  | $\displaystyle\quad+\underbrace{C\cdot\sqrt{\text{Pdim}(\mathcal{F})\cdot\bigg{(}\frac{\log m}{m}\vee\frac{\log n}{n}\bigg{)}}\vee\sqrt{\text{Pdim}(\mathcal{F}\circ\mathcal{G})\frac{\log m}{m}}}_{:=S_{n,m}(\mathcal{F},\mathcal{G})},$ |  |

其中 $C>0$ 是一个与 $n$、$m$、$\text{Pdim}(\mathcal{F})$ 和 $\text{Pdim}(\mathcal{F}\circ\mathcal{G})$ 无关的普遍常数。

第一个近似误差 $A_{1}(\mathcal{F},\mathcal{G},\nu)$ 测量鉴别器对 $\nu$ 和 $\mu_{\theta}$ 之间对数密度比的近似程度。第二个近似误差 $A_{2}(\mathcal{G},\nu)$ 反映生成器的表达能力。最后，统计误差 $S_{n,m}(\mathcal{F},\mathcal{G})$ 描述了生成器和鉴别器的统计复杂性。对于固定的 $\nu$，($\mathcal{G}$, $\mathcal{F}$) 的复杂性增加会导致 $A_{2}(\mathcal{G},\nu)$ 减少，$S_{n,m}(\mathcal{F},\mathcal{G})$ 增加，但 $A_{1}(\mathcal{F},\mathcal{G},\nu)$ 可能增加、减少或不变，因为 $A_{1}(\mathcal{F},\mathcal{G},\nu)$ 是对 $\theta$ 的最大值和对 $\nu$ 的最小值。由于 $A_{1}$ 项，经典的偏差-方差权衡的 U 形图不再存在，但作者展示了拥有一个二维调节域（因为鉴别器-生成器对是用户指定的参数）甚至可能产生更好的速率。

具体来说，通过选择 $f_{\omega}\in\mathcal{F}_{D}$ 在以下函数空间中：

|  | $\displaystyle\mathcal{F}_{D}:=\{\log(p_{\nu})-\log(p_{\mu_{\theta}}):\text{ 对所有 }\nu\in\mathcal{D}_{R},\quad\mu_{\theta}\in\mathcal{D}_{G}\},$ |  |
| --- | --- | --- |

如果生成器分布类在某种意义上良好地指定，即 $\mathcal{D}_{\nu}\subseteq\mathcal{D}_{G}$，则 TV 界限简化为 $\mathbb{E}d_{\text{TV}}^{2}(\nu,\mu_{\widehat{\theta}_{m,n}})\leq S_{n,m}(\mathcal{F},\mathcal{G})$ 当 $A_{1}=A_{2}=0$。找到神经网络 $g_{\theta}(z)$ 和 $f_{\omega}$ 使得 $A_{1}=A_{2}=0$ 的关键假设是目标分布 $\nu$ 应该可以由可逆生成器精确实现，即所有的权重矩阵和激活函数应当是可逆的。在这一假设下，Liang（2021）的定理 $19$ 证明了存在满足界限的 $(g_{\theta}(z),f_{\omega})$ 对。

|  | $\displaystyle\mathbb{E}d_{\text{TV}}^{2}(\nu,\mu_{\widehat{\theta}_{m,n}})$ | $\displaystyle\leq\sqrt{d^{2}L\log(dL)\bigg{(}\frac{\log m}{m}\vee\frac{\log n}{n}\bigg{)}}.$ |  | (29) |
| --- | --- | --- | --- | --- |

在速率中（29），$L$和$d$分别是生成器网络的深度和宽度。这个结果允许非常深的网络，$L\leq\sqrt{n\wedge m/\log(n\vee m)}$。值得注意的是，生成器要求网络的宽度与输入维度$d$相同，以便满足生成器的可逆性条件。至于判别器，可以通过连接两个与生成器具有相同架构的网络，并增加两个额外的层来构建，即，网络$f_{\omega}$具有$L+2$层。$g_{\theta}$和$f_{\omega}$分别使用 leaky ReLU 和双重 leaky ReLU 作为激活函数以确保其可逆性。然而，这一可逆性条件在实际使用 GAN 时常常被违反。

Chen 等人（2020a）的后续工作提供了更灵活的网络架构用于$g_{\theta}$和$f_{\omega}$，而不要求生成器和激活函数的可逆性条件，即，作者考虑了 ReLU 激活函数。论文主要关注于三个有趣的场景，其中他们对目标分布$\nu$施加了结构假设：

1.  1.

    目标分布$\nu$被假设为相对于$\mathbb{R}^{d}$中的 Lebesgue 度量具有$\alpha(>0)$-Hölder 密度$p_{\nu}$，并且在紧凸子集$\mathcal{X}\subset\mathbb{R}^{d}$上密度远离$0$有下界。

1.  2.

    目标分布$\nu$支持在数据域$\mathcal{X}\subset\mathbb{R}^{d}$的低维线性子空间上。具体来说，假设子空间由$\mathbb{R}^{q}$的正交基构成，其中$q\ll d$。我们用$A\in\mathbb{R}^{d\times q}$表示其列为正交基的矩阵。假设推送分布$A^{\top}_{\sharp}\nu$的密度函数属于有限半径的$\alpha$-Hölder 类。

1.  3.

    目标分布$\nu$支持在$\mathcal{X}\subset[0,1]^{d}$上，是低维非线性$K$-混合成分。每个成分被假设为$[0,1]^{q}$上$q$维均匀分布的推送分布，其中$q\ll d$，即，$\mu_{k}:=(g_{k})_{\sharp}\mathcal{U}([0,1]^{q})$。推送函数$g_{k}$属于$\alpha_{k}$-Hölder 类，其中$\alpha_{k}\geq 1$，$\forall k\in[K]$。（$\alpha:=\max\alpha_{K}$。）

在第一个场景中，假设判别器类 $\mathcal{F}$ 是 $\beta$-Hölder 类，其中 $\beta>1$。在第二和第三个场景中，$\mathcal{F}$ 被认为是 $1$-Lipschitz 函数的集合，其中在 (26 ‣ 4 生成模型的统计保证 ‣ 深度学习统计理论调查：近似、训练动态和生成模型"))中的 IPM 变为 Wasserstein-$1$ 距离。本文主要考虑生成器类中样本无限多的情况，并且在 (28 ‣ 4 生成模型的统计保证 ‣ 深度学习统计理论调查：近似、训练动态和生成模型"))中的经验期望被真实期望所替代。在这种设置下，给出了上述三种场景下期望 IPM 的收敛速度。此外，作者提供了关于每个场景中生成器和判别器网络的 $(L,\mathbf{p},\mathcal{N})$-元组的明确阶数 回顾 ([2)]。我们在下面的表格中总结了结果。为简便起见，我们仅呈现网络的深度 $L$ 和隐藏层的最大宽度 $P_{\text{max}}$ 的阶数。

$L$ $P_{\text{max}}$ 收敛速度 $\mathbb{E}d_{\mathcal{H}^{\beta}}(\nu,\mu_{\widehat{\theta}_{m,n}})$ $g_{\theta}$ $\mathcal{O}\big{(}\frac{\beta}{2\beta+d}\log n\big{)}$ $\mathcal{O}\big{(}dn^{\frac{\beta d}{(\alpha+1)(2\beta+d)}}\big{)}$ $\tilde{\mathcal{O}}\big{(}n^{-\frac{\beta}{2\beta+d}}\log^{2}n\big{)}$ $f_{\omega}$ $\mathcal{O}\big{(}\frac{\beta}{2\beta+d}\log n\big{)}$ $\mathcal{O}\big{(}n^{\frac{2d}{2\beta+d}}\big{)}$ $\mathbb{E}d_{W_{1}}(\nu,\mu_{\widehat{\theta}_{m,n}})$ $g_{\theta}$ $\mathcal{O}\big{(}\frac{\alpha}{2\alpha+q}\log n\big{)}$ $\mathcal{O}\big{(}qn^{\frac{q\alpha}{(\alpha+1)(2\alpha+d)}}\vee d\big{)}$ $\tilde{\mathcal{O}}\big{(}n^{-\frac{1}{2+q}}\log^{2}n\big{)}$ $f_{\omega}$ $\mathcal{O}\big{(}\frac{1}{2+q}\log n\big{)}$ $\mathcal{O}\big{(}n^{\frac{q}{2+q}}\vee d\big{)}$ $\mathbb{E}d_{W_{1}}(\nu,\mu_{\widehat{\theta}_{m,n}})$ $g_{\theta}$ $\mathcal{O}\big{(}\frac{1}{q}\log n\big{)}$ $\mathcal{O}\big{(}Kdn^{\frac{1}{\alpha}}\big{)}$ $C_{\delta}dn^{-\frac{1}{q+\delta}}$ $f_{\omega}$ $\mathcal{O}\big{(}\log n+d\big{)}$ $\mathcal{O}\big{(}n^{\frac{d}{q}}\big{)}$

在第一种情况下，无法避免对$d$的指数依赖，因为在$\mathcal{H}^{\beta}$ IPM 下估计$\mathcal{H}^{\alpha}$的分布的最小最大下界已知为$\mathcal{O}\big{(}n^{-\frac{\alpha+\beta}{2\alpha+d}}+n^{-\frac{1}{2}}\big{)}$，正如 Tang 和 Yang (2022)所指出的。第二种情况下的结果表明，GAN 可以避免对数据未知低维线性结构的自适应诅咒。值得注意的是，获得的速率比参数化速率$n^{-\frac{1}{2}}$要快得多。然而，集中在低维线性子空间的真实世界数据是稀少的，而混合数据在实际中很常见，例如 MNIST 数据或 CIFAR-10 中的图像。在第三种情况下，观察到速率在$d$上线性依赖，在$q$上指数依赖。这意味着 GAN 能够捕捉由$g_{k}$编码的非线性数据的内在结构。这里，$\delta$是任何正数，$C_{\delta}>0$是一个与$n$无关的普遍常数。有趣的是，所有场景中$g_{\theta}$和$f_{\omega}$的深度都有$\mathcal{O}(\log n)$因子，意味着网络的深度应当随着样本量$n$对数增加。相比之下，Liang (2021)指出，网络的宽度与输入维度$d$不同，这是生成器可逆性的充分条件。

### 4.2 基于评分的扩散模型

基于评分的扩散模型由两个过程组成。第一步，前向过程，将数据转换为噪声。具体来说，基于评分的扩散模型 Song et al. (2020) 使用以下随机微分方程（SDEs）(Särkkä 和 Solin, 2019) 进行数据扰动：

|  | $\displaystyle d\mathbf{x}=f(\mathbf{x},t)dt+g(t)dW_{t},$ |  | (30) |
| --- | --- | --- | --- |

其中 $f(\mathbf{x},t)$ 和 $g(t)$ 分别是漂移和扩散系数，$W_{t}$ 是标准 Wiener 过程（即布朗运动），其索引为时间 $t\in[0,T]$。在这里，$f$ 和 $g$ 函数是用户指定的，Song 等人 (2020) 提出了三种不同类型的 SDE，即方差爆炸（VE）、方差保持（VP）和次方差保持（sub-VP）SDE 用于数据扰动。允许扩散足够长时间，$T$ 足够大，可以证明 $\mathbf{x}_{t}$ 的分布收敛到一些易于采样的分布 $\pi$，例如正态分布或均匀分布。具体来说，当 $f:=-\mathbf{x}_{t}$ 和 $g:=\sqrt{2}$ 时，(30) 被称为 Ornstein-Uhlenbeck（OU）过程，已证明 $p_{t}:=\text{Law}(\mathbf{x}_{t})\rightarrow\pi$，其中 $\pi$ 为正态分布，在 $2$-Wasserstein 距离下以指数速度收敛。见例如 Bakry 等人 (2014)。然而，尽管有这一收敛结果，分析上很难知道 $p_{T}$ 的确切形式，通常在实际中用 $\pi$ 替代它来开始反向过程。

第二步，即反向过程，是一个生成过程，旨在逆转前向过程的效果。这个过程通过逆转 SDEs 来学习将噪声转换回数据，见于 (30)。通过时间 $t\in[t_{0},T]$ 的边际密度 $p_{t}(\mathbf{x})$ 的 Fokker-Planck 方程，可以很容易推导出以下反向 SDE（Anderson, 1982）：

|  | $\displaystyle d\mathbf{x}=\bigg{[}f(\mathbf{x},t)-g(t)^{2}\nabla_{\mathbf{x}}\log p_{t}(\mathbf{x})\bigg{]}dt+g(t)d\bar{W}_{t}.$ |  | (31) |
| --- | --- | --- | --- |

在这里，$\log p_{t}(\mathbf{x})$ 关于扰动数据 $\mathbf{x}(t)$ 的梯度被称为得分函数，$dt$ 在 (31)中是一个微小的负时间步，而 $d\bar{W}_{t}$ 是一个向后运行的 Wiener 过程，即 $t:T\rightarrow t_{0}$。在实践中，$t_{0}$ 通常选择为接近 $0$ 的一个小数，但不能过于接近 $0$，以防得分函数爆炸。有多种方法可以解决 (31)。最常用的方法是离散化方案，如 Euler-Maruyama，或基于理论的方法，如概率流。有关这些方法的详细说明，请参见 Song 等人 (2020)。本文介绍的论文集中在离散化方案上，读者可以参考 Chen 等人 (2023b) 了解扩散模型中概率流的最新理论理解。

得分函数 $\nabla_{\mathbf{x}}\log p_{t}(\mathbf{x})$ 被一个时间依赖的得分基模型 $\mathbf{S}_{\theta}(\mathbf{x}(t),t)$ 近似，实际中该模型由神经网络参数化。网络参数 $\theta$ 通过最小化以下得分匹配损失来估计：

|  | $\displaystyle\theta^{\star}:=\operatorname*{arg\,min}_{\theta}\mathbb{E}_{t\sim\mathcal{U}[t_{0},T]}\mathbb{E}_{\mathbf{x(t)\mid\mathbf{x(0)}}}\mathbb{E}_{\mathbf{x}(0)}\bigg{[}\lambda(t)^{2}\left\|\mathbf{S}_{\theta}(\mathbf{x}(t),t)-\nabla_{\mathbf{x}}\log p_{t}(\mathbf{x}(t)\mid\mathbf{x}(0))\right\|_{2}^{2}\bigg{]},$ |  | (32) |
| --- | --- | --- | --- |

其中 $\mathcal{U}[t_{0},T]$ 是 $[t_{0},T]$ 上的均匀分布，$\lambda(t)(>0)$ 是一个正的加权函数，有助于使匹配损失 $\left\|\mathbf{S}_{\theta}(\mathbf{x}(t),t)-\nabla_{\mathbf{x}}\log p_{0t}(\mathbf{x}(t)\mid\mathbf{x}(0))\right\|_{2}^{2}$ 在时间 $t\in[t_{0},T]$ 上保持在相同的数量级。转移密度 $p_{t}(\mathbf{x}(t)\mid\mathbf{x}(0))$ 是一个可处理的高斯分布，$\mathbf{x}(t)$ 可以通过祖先采样获得 (Ho 等人，2020)。

在这种设置下，我们向读者介绍了两条尝试，旨在回答以下理论问题：

1.  Q1.

    扩散模型能否通过学习到的得分函数估计目标分布 $\nu$？如果可以，那么在 $\nu$ 的哪些条件下，我们可以在总变距或 Wasserstein 距离下获得一般化误差界限 $\varepsilon$ 的多项式收敛保证？

1.  Q2.

    神经网络是否能够很好地逼近和学习分数函数？如果可以，应该如何选择网络架构以及学习的样本复杂度是多少？此外，如果数据分布具有特殊的几何结构，扩散模型是否能适应这种结构，就像 GAN 模型一样？

这两条研究线的主要统计对象是测量目标分布 $\nu$ 和从样本 $\mathbf{x}_{t_{0}}$ 通过解决反向 SDE 得到的估计分布 $\widehat{\mu}_{\theta}$ 之间距离的泛化界限 (31)。这里，分数函数被估计的时间相关神经网络 $\mathbf{S}_{\theta}(\mathbf{x}(t),t)$ 所替代。第一条研究线主要关注扩散模型的采样视角，假设我们对分数函数有很好的估计。第二条研究线则将注意力扩展到通过神经网络进行的分数函数逼近。此外，在一些高度风格化的设置下，他们指定了给出良好泛化保证的明确网络结构。

尝试回答 Q1。早期理论研究对基于分数的扩散模型采样的理解存在不足，要么没有量化 (De Bortoli et al., 2021; Liu et al., 2022)，要么面临维度诅咒 (De Bortoli, 2022; Block et al., 2020)。其中，De Bortoli (2022) 给出了具有有界支持 $\mathcal{M}$ 的分布在 $1$-Wasserstein 距离下的收敛。他们的案例涵盖了在低维流形上支持的分布，其中 TV 或 KL 距离的保证是不可实现的，因为没有保证 $\nu$ 和 $\widehat{\mu}_{\theta}$ 具有相同的支持集。对于一般分布，他们对 $W_{1}(\nu,\widehat{\mu}_{\theta})$ 的界限在流形 $\mathcal{M}$ 的直径上有指数依赖，并且反向过程的截断 $t_{0}$ 为 $\mathcal{O}(\exp(\text{diam}(\mathcal{M})^{2}/t_{0}))$。对于可用 Hessian $\nabla^{2}\log p_{t}$ 的光滑分布，该界限进一步通过对 $t_{0}$ 的多项式依赖得到改进，其中 Hessian 的增长率在 $t\rightarrow 0$ 时是指数级的。

据我们所知，Lee 等人（2022）首次在 $L^{2}$-准确评分下为合理的分布家族提供了 TV 距离的多项式保证。然而，他们的结果基于假设分布满足某些平滑性标准和对数-索博列夫不等式，这基本上将他们发现的适用性限制在具有单一峰值的分布上。最近，两个研究工作：Lee 等人（2023）；Chen 等人（2022b）在线出现，试图避免对数据分布的强假设，并在 TV 或 Wasserstein 等一般度量下获得多项式收敛保证。具体来说，Lee 等人（2023）为任何具有有界支持的分布提供了 $2$-Wasserstein 界限。与 De Bortoli（2022）；Lee 等人（2022）不同，他们提供的结果在没有依赖于分布的功能不等式（如对数-索博列夫不等式）的情况下具有多项式复杂度保证。他们进一步在 Hessian 可用性假设下提供了具有多项式复杂度保证的 TV 界限。类似于 Lee 等人（2022），在一般数据分布假设下，即 $\nu$ 的二阶矩界限和评分函数的 $L$-Lipschitz 连续性，Chen 等人（2022b）提供了多项式 TV 收敛保证，其中只需 $\tilde{\Theta}\big{(}\frac{L^{2}d}{\varepsilon^{2}}\big{)}$ 的离散化。这里，$\varepsilon$ 是 TV 泛化误差，$d$ 是数据维度。

尝试回答 Q2。由于其近期的理论进展，文献中针对第二个问题的研究列表较短。Chen 等人 (2023a) 的一项工作假设数据位于 $\mathbb{R}^{d}$ 的未知低维线性子空间上；即，$\mathbf{x}=A\mathbf{z}$，其中 $A\in\mathbb{R}^{d\times D}$。这里，$\mathbf{z}$ 是一个潜在变量，$D$ 是固有维度，$d$ 是一个环境维度，并且 $D\ll d$。他们将真实评分函数分解为两个组件，$S_{||}$ 属于 $A$ 的列空间，$S_{\perp}$ 则正交于 $A$ 的列空间。由于 $S_{||}$ 和 $S_{\perp}$ 的封闭形式可以相对于 $\mathbf{x}$ 和 $A$ 推导，他们设计了一种具有跳跃连接的编码器-解码器结构的非常具体的网络架构。有趣的是，他们设计的网络结构涉及到稀疏全连接网络 (2)，并且在 $L^{2}$-准确评分下建立了普遍近似保证。这里，网络规模 $L,\mathbf{p},\mathcal{N}$ 在 (2) 中依赖于固有维度 $D$，这要归功于编码器-解码器架构。基于获得的评分函数近似结果，他们证明了平方 $L^{2}$-估计误差的收敛速率为 $\tilde{\mathcal{O}}\big{(}\frac{1}{t_{0}}n^{-\frac{2}{D+5}}\big{)}$。这证实了扩散模型对位于低维子空间中的数据的适应性。进一步，他们提供了目标分布 $\nu$ 在 TV 和 $2$-Wasserstein 距离上的 $\widehat{\mu}_{\theta}$ 的分布恢复保证。

在更一般的情况下，Oko 等人 (2023) 证明了扩散模型中的分布估计器可以实现接近极小极大最优的估计率。具体来说，他们假设真实密度支持在 $[-1,1]^{d}$ 上，并且在具有光滑边界的 Besov 空间中。Besov 空间统一了许多通用的函数空间，如 Hölder、Sobolev、连续的，甚至是非连续的函数类。Oko 等人 (2023) 的结果对于非连续函数类有效，这与前述的 Lee 等人 (2023) 和 Chen 等人 (2022b) 的工作形成对比，后者假设了评分函数的 Lipschitz 连续性。对于具有 $s$-光滑性的 Besov 空间（$s \geq 0$），他们证明了评分网络 $S_{\theta^{\star}}(\mathbf{x}(t),t)$ 对于 $t_{0}=o(\frac{1}{n})$ 和 $T=\mathcal{O}(\log n)$ 的 $L^{2}$-泛化界限达到了极小极大最优率，直到对数因子，即，$n^{-\frac{2s}{2s+d}}\log^{18}n$，用于恢复目标分布 $\nu$ 的评分函数。请注意，评分网络的确切架构在 (2) 中给出。 (2) 中的 $L,\mathbf{p},\mathcal{N}$ 是相对于网络参数 $N=\mathcal{O}(n^{-\frac{d}{2s+d}})$ 表达的。在所获得的网络架构下，他们进一步证明了 $TV(\nu,\widehat{\mu}_{\theta})\asymp\tilde{\mathcal{O}}(n^{-\frac{s}{2s+d}})$ 和 $W_{1}(\nu,\widehat{\mu}_{\theta})\asymp\tilde{\mathcal{O}}(n^{-\frac{s+1-\delta}{2s+d}})$ 对于任何任意固定的 $\delta>0$，其速率接近极小极大最优。

### 4.3 大型语言模型中的上下文学习

我们向读者提供了对 LLM 中观察到的一种有趣现象的最新理论理解，即上下文学习（ICL）。这指的是 LLM 能够基于由任务中的示例（输入输出对）组成的提示序列以及新的查询输入，准确生成相应的输出。以 Garg 等人 (2022) 的一个实例为例，这些模型在被提示了几个这样的翻译之后，可以生成法语单词的英语翻译，例如：

|  | $\displaystyle\underbrace{\text{maison}\rightarrow\text{house},\quad\text{chat}\rightarrow\text{cat},\quad\text{chien}\rightarrow}_{\text{prompt}}\underbrace{\text{dog}}_{\text{completion}}.$ |  |
| --- | --- | --- |

这种能力非常吸引人，因为它使模型能够在不需要在训练后更新模型权重的情况下，实时适应各种下游任务。

为了进一步理解 ICL，研究人员制定了一个明确的问题，即从上下文示例中学习一个函数类$\mathcal{F}$。形式上，设$\mathcal{D}_{\mathcal{X}}$是输入的分布，$\mathcal{D}_{\mathcal{F}}$是$\mathcal{F}$中函数的分布。一个提示$P$是一个序列$(x_{1},f(x_{1}),\dots,x_{k},f(x_{k}),x_{\text{query}})$，其中输入（即$x_{i}$和$x_{\text{query}}$）是从$\mathcal{D}_{\mathcal{X}}$中独立同分布抽取的，$f$是从$\mathcal{D}_{\mathcal{F}}$中抽取的。在上述示例中，可以理解为$\{(x_{1},f(x_{1})),(x_{2},f(x_{2}))\}:=\text{\{(maison, house), (chat, cat)\}}$，$x_{\text{query}}=\text{chien}$，并且$f(x_{\text{query}})=\text{dog}$。现在，我们提供上下文学习的正式定义。

###### 定义 4.2（上下文学习 Garg 等 (2022)）。

模型$M_{\theta}$可以在上下文中学习函数类$\mathcal{F}$，以达到$\varepsilon$，相对于$(\mathcal{D}_{\mathcal{F}},\mathcal{D}_{\mathcal{X}})$，如果它能够以平均误差预测$f(x_{\text{query}})$。

|  | $\displaystyle\mathbb{E}_{P\sim(x_{1},f(x_{1}),\dots,x_{k},f(x_{k}),x_{\text{query}})}\big{[}\ell(M_{\theta}(P),f(x_{\text{query}}))\big{]}\leq\varepsilon,$ |  | (33) |
| --- | --- | --- | --- |

其中$\ell(\cdot,\cdot)$是一些合适的损失函数，例如平方误差。

论文 Garg 等 (2022) 实证研究了 Transformer 架构 Vaswani 等 (2017) 的 ICL，通过对线性函数、两层 ReLU 网络和决策树的随机实例进行模型训练。这里，为了简洁起见，我们省略了 Transformer 的定义。具体而言，他们展示了当模型在来自线性函数类$\mathcal{F}^{\text{Lin}}:=\{f\mid f(x)=w^{\top}x,w\in\mathbb{R}^{d}\}$的实例上进行训练时，Transformers 在提示$P$上的预测行为与普通最小二乘（OLS）类似，其中权重$w$是随机的，$w\sim\mathcal{N}(0,I_{d})$。对于训练在稀疏线性函数上的模型，也观察到了类似的现象，因为其预测行为类似于 Lasso 估计量。

这些有趣的观察引发了对内部机制的众多后续理论研究，Akyürek 等人（2022）；Von Oswald 等人（2023）；Dai 等人（2022），表达能力 Akyürek 等人（2022）；Giannou 等人（2023）以及广义 Li 等人（2023b）。其中，Akyürek 等人（2022）；Von Oswald 等人（2023）的论文研究了当变压器在$\mathcal{F}^{\text{Lin}}$的随机实例上进行训练时的行为，并展示了训练后的变压器的预测模拟了梯度下降的单步。它们进一步提供了实现这种单步梯度下降更新的变压器构造。最近的论文 Zhang 等人（2023）明确证明了通过梯度流估计的模型参数收敛到非凸人口风险景观的全局最小值（见 33）用于学习$\mathcal{F}^{\text{Lin}}$。他们还提供了关于训练变压器对任务偏移（即，$\mathcal{D}_{\mathcal{F}}^{\text{train}}\neq\mathcal{D}_{\mathcal{F}}^{\text{test}}$）和查询偏移（即，$\mathcal{D}_{\text{query}}^{\text{test}}\neq\mathcal{D}_{x}^{\text{test}}$）的鲁棒性的理论解释，但对于协变量分布的偏移（即，$\mathcal{D}_{x}^{\text{train}}\neq\mathcal{D}_{x}^{\text{test}}$）则没有。这些不同类型的偏移行为在 Garg 等人（2022）中有实证观察。然而，论文中的结果是基于没有 softmax 非线性和简化参数化的线性自注意力（LSA）层。

随后，黄等人 (2023) 考虑了 softmax 非线性，并证明了通过梯度下降训练的 Transformer 确实可以在上下文中学习 $\mathcal{F}^{\text{Lin}}$。他们考虑了两种不同的场景，其中所有特征在提示中出现的可能性相同（即，平衡特征），只有一个特征主导出现，其余特征出现的可能性较小（即，不平衡特征）。他们展示了 Transformers 基于不同类型的特征展现不同的训练阶段。然而，这项工作仍然考虑了简化的参数化，并假设特征彼此正交，这里理论与实践之间仍存在差距。一项重要的工作是 Bai 等人 (2023) 展示了存在可以在上下文中实现广泛标准机器学习算法的 Transformers，如最小二乘法、岭回归、Lasso 和两层神经网络的梯度下降。本文更进一步，展示了单个 Transformer 的一个显著能力：能够为不同的 ICL 实例动态选择不同的基础上下文学习（ICL）算法，而无需在输入序列中明确指导使用正确的算法。这一观察是值得注意的，因为它反映了统计学家为模型参数推断选择学习算法的方式。

## 未来工作的 5 个主题

然而，除了这些主题之外，还有一些有前景的领域在本文中没有涵盖。我们将简要介绍其中的一些，希望它们能得到进一步的研究。

合成数据理论。在现代机器学习中，数据虽然宝贵但通常稀缺，被称为“新石油”，这一比喻归功于数学家 Clive Humby。随着深度生成模型如 GANs、扩散模型和 LLMs 的兴起，合成数据迅速填补了真实数据的空白，并在各种下游应用中找到广泛的用途。例如，在医疗领域，合成数据已被用于提高患者数据隐私和改进疾病诊断预测模型的性能 (Chen et al., 2021)。类似地，结构化表格数据是最常见的数据形式，需要使用合成数据来解决隐私问题 (Suh et al., 2023)、缺失值 (Ouyang et al., 2023b) 和可访问性问题 (Choi et al., 2017)。此外，合成数据在构建可靠的 AI 系统中发挥了核心作用，尤其是在隐私 (Li et al., 2023a)、公平性 (Zeng et al., 2022) 和鲁棒性 (Ouyang et al., 2023a) 等有前景的问题上。尽管它在现实世界中普遍存在，但对合成数据的统计分析非常有限。在这方面，需要分析的重要问题包括：

1.  Q1

    通过合成数据训练的模型在真实未见数据上的泛化效果如何？（例如，Xu 等人 (2023a)）

1.  Q2

    人工生成的数据如何在特定任务中帮助统计推断，例如对抗训练？（例如，Xing 等人 (2022a，b)）

1.  Q3

    合成数据在满足某些隐私约束（例如，差分隐私 Dwork (2008））的情况下，在分类或回归等各种下游任务中的表现如何？（例如，Li 等人 (2023a)；Xu 等人 (2023b)）

1.  Q4

    在合成数据的下游任务中，回归和分类哪个任务更容易？我们能否在统计学习框架下分析其表现？

问题 Q1 中的设定通常在文献中被称为“在合成数据上训练，在真实数据上测试”（TSTR）框架 Esteban 等人 (2017)，用于测量合成分布与真实分布的接近程度。我们引用了一篇论文 Xu 等人 (2023a)，探讨了合成数据的泛化，并提出了有效合成数据算法应具备的关键特性，以创建高质量的数据集用于下游学习任务。然而，这一框架在分布转移名下的统计方面（例如，见 Sugiyama 和 Kawanabe (2012)；Ma 等人 (2023)；Pathak 等人 (2022)）仍未得到充分探讨。Q2、Q3 和 Q4 涉及合成数据在下游任务中的实用性。Q4 的动机来自 Suh 等人 (2023)，表 2 中提出的见解，实证地展示了在回归任务中取得强大表现相比于分类任务的挑战更大。

分布转移和稳健性。在许多机器学习任务中，训练集和测试集并不来自相同的分布，这在文献中通常称为分布转移。在统计学中，分布转移进一步细分为几种子类别。其中，当只有特征变量发生变化但条件分布保持不变时，称为“协变量转移”。激励应用包括图像、文本和语音分类，其中输入协变量决定输出标签 Sugiyama 和 Kawanabe (2012)。在统计文献中，我们知道两篇论文 Ma 等 (2023); Pathak 等 (2022) 研究了在非参数回归设置下的协变量转移。在这方面，Ma 等 (2023) 研究了核岭回归估计量在大型 RKHS 类上达到最小最大速率，只要源（例如训练）和目标（例如测试）分布的似然比是均匀有界的。与测量目标和源分布之间的转移的似然比相比，Pathak 等 (2022) 的作者提出了另一种度量（固定半径球体的概率的积分比），用于经典估计量（如 Nadaraya-Watson 估计量）在回归设置中有效地实现 Hölder 类函数的最小最大风险率。尽管统计文献中有丰富的结果，但在深度学习背景下对这一主题的理论理解仍然有限，一些问题可以提出：

1.  Q1

    正如第三部分所讨论的，非常宽的神经网络可以被认为是其内核由网络架构特征化的内核回归器，最近的论文 Yang (2020) 推导了任何网络架构的 NTK。在 Ma 等 (2023) 提出的框架下，一个有趣的研究方向是评估不同架构的神经网络模型在协变量转移下的稳健性。这项探索涉及计算不同网络结构的允许似然比的上界。

1.  Q2

    最近的研究发现 Ahuja 和 Lopez-Paz (2023) 认为变换器在轻微的分布转移下对于 ICL 是稳健的，但在严重转移下这种能力会消失。了解变换器在表现 ICL 能力时的基本极限是一个重要任务。在不使用 NTK 框架的情况下，最近的工作 Han 等 (2023) 研究了在核回归背景下 LLMs 的上下文学习，我们推测 Pathak 等 (2022); Ma 等 (2023) 使用的理论分析可以用于获得阈值极限。

## 参考文献

+   Ahuja and Lopez-Paz [2023] Kartik Ahuja 和 David Lopez-Paz. 在分布偏移下对上下文学习的更深入分析。*arXiv 预印本 arXiv:2305.16704*，2023 年。

+   Akyürek et al. [2022] Ekin Akyürek, Dale Schuurmans, Jacob Andreas, Tengyu Ma 和 Denny Zhou. 什么学习算法是上下文学习？用线性模型的研究。*arXiv 预印本 arXiv:2211.15661*，2022 年。

+   Allen-Zhu and Li [2019] Zeyuan Allen-Zhu 和 Yuanzhi Li. ResNet 能有效学习什么，超越内核？*神经信息处理系统进展*，32，2019 年。

+   Allen-Zhu et al. [2018] Zeyuan Allen-Zhu, Yuanzhi Li 和 Zhao Song. 通过过参数化的深度学习收敛理论。*arXiv 电子预印本*，页面 arXiv–1811，2018 年。

+   Allen-Zhu et al. [2019] Zeyuan Allen-Zhu, Yuanzhi Li 和 Yingyu Liang. 过参数化神经网络中的学习与泛化，超越两层。*神经信息处理系统进展*，32:6158–6169，2019 年。

+   Anderson [1982] Brian DO Anderson. 反向时间扩散方程模型。*随机过程及其应用*，12(3):313–326，1982 年。

+   Anthony and Bartlett [1999] Martin Anthony 和 Peter L Bartlett. *神经网络学习：理论基础*，第 9 卷。剑桥大学出版社，英国剑桥，1999 年。

+   Arora et al. [2017] Sanjeev Arora, Rong Ge, Yingyu Liang, Tengyu Ma 和 Yi Zhang. 生成对抗网络（GANs）中的泛化和均衡。在 *国际机器学习会议*，第 224–232 页。PMLR，2017 年。

+   Arora et al. [2019a] Sanjeev Arora, Simon Du, Wei Hu, Zhiyuan Li 和 Ruosong Wang. 对过参数化的两层神经网络优化和泛化的细粒度分析。在 *国际机器学习会议*，第 322–332 页。PMLR，2019a 年。

+   Arora et al. [2019b] Sanjeev Arora, Simon S Du, Wei Hu, Zhiyuan Li, Russ R Salakhutdinov 和 Ruosong Wang. 关于无限宽神经网络的精确计算。*神经信息处理系统进展*，32:8141–8150，2019b 年。

+   Audibert and Tsybakov [2007] Jean-Yves Audibert 和 Alexandre B Tsybakov. 插件分类器的快速学习速率。*统计年鉴*，35(2):608–633，2007 年。

+   Bai and Lee [2019] Yu Bai 和 Jason D Lee. 超越线性化：关于宽神经网络的二次及更高阶近似。在 *国际学习表征会议*，2019 年。

+   Bai et al. [2018] Yu Bai, Tengyu Ma 和 Andrej Risteski. 鉴别器的可近似性意味着对抗生成网络中的多样性。*arXiv 预印本 arXiv:1806.10586*，2018 年。

+   Bai et al. [2023] Yu Bai, Fan Chen, Huan Wang, Caiming Xiong 和 Song Mei. 变压器作为统计学家：具有上下文算法选择的可证明的上下文学习。*arXiv 预印本 arXiv:2306.04637*，2023 年。

+   Bakry et al. [2014] Dominique Bakry, Ivan Gentil, Michel Ledoux 等人. *Markov 扩散算子的分析与几何*，第 103 卷。Springer，2014 年。

+   Barron [1993] Andrew R Barron. 对 sigmoid 函数叠加的普适逼近界限。*IEEE 信息论学报*，39(3):930–945，1993 年。

+   Bartlett 等 [2019] Peter L Bartlett, Nick Harvey, Christopher Liaw 和 Abbas Mehrabian. 片段线性神经网络的近紧 vc-维度和伪维度界限。*机器学习研究期刊*，20(1):2285–2301，2019 年。

+   Bartlett 等 [2020] Peter L Bartlett, Philip M Long, Gábor Lugosi 和 Alexander Tsigler. 线性回归中的良性过拟合。*国家科学院院刊*，117(48):30063–30070，2020 年。

+   Bartlett 等 [2021] Peter L. Bartlett, Andrea Montanari 和 Alexander Rakhlin. 深度学习：统计视角。*数值分析学报*，30:87–201，2021 年。doi: 10.1017/S0962492921000027。

+   Belkin [2021] Mikhail Belkin. 无惧拟合：通过插值视角观察深度学习的显著数学现象。*数值分析学报*，30:203–248，2021 年。

+   Bengio 等 [2005] Yoshua Bengio, Nicolas Roux, Pascal Vincent, Olivier Delalleau 和 Patrice Marcotte. 凸神经网络。*神经信息处理系统进展*，18，2005 年。

+   Bietti 和 Mairal [2019] Alberto Bietti 和 Julien Mairal. 关于神经切线核的归纳偏差。在 *NeurIPS 2019-第三十三届神经信息处理系统大会*，第 32 卷，页码 12873–12884，2019 年。

+   Blanchard 和 Bennouna [2022] Moise Blanchard 和 Mohammed Amine Bennouna. 浅层和深层网络是 Korobov 函数的近似最优器。在 *国际学习表征大会*，2022 年。

+   Block 等 [2020] Adam Block, Youssef Mroueh 和 Alexander Rakhlin. 使用去噪自编码器和 Langevin 采样的生成建模。*arXiv 预印本 arXiv:2002.00107*，2020 年。

+   Cao 等 [2019] Yuan Cao, Zhiying Fang, Yue Wu, Ding-Xuan Zhou 和 Quanquan Gu. 深度学习的谱偏差研究。*arXiv 预印本 arXiv:1912.01198*，2019 年。

+   Caragea 等 [2023] Andrei Caragea, Philipp Petersen 和 Felix Voigtlaender. 神经网络在 Barron 类中的分类边界的逼近和估计。*应用概率年鉴*，33(4):3039–3079，2023 年。

+   Chen 等 [2019a] Minshuo Chen, Haoming Jiang, Wenjing Liao 和 Tuo Zhao. 低维流形上函数的深度 ReLU 网络的高效逼近。*神经信息处理系统进展*，32，2019a 年。

+   Chen 等 [2019b] Minshuo Chen, Haoming Jiang, Wenjing Liao 和 Tuo Zhao. 使用深度 ReLU 网络对低维流形上的非参数回归：函数逼近和统计恢复。*即将在信息与推断：IMA 学报*，2019b 年。

+   Chen 等 [2020a] Minshuo Chen, Wenjing Liao, Hongyuan Zha 和 Tuo Zhao. 生成对抗网络的分布逼近和统计估计保证。*arXiv 预印本 arXiv:2002.03938*，2020a 年。

+   Chen et al. [2022a] Minshuo Chen, Haoming Jiang, Wenjing Liao, 和 Tuo Zhao. 使用深度 ReLU 网络在低维流形上的非参数回归：函数逼近和统计恢复。*Information and Inference: A Journal of the IMA*, 11(4):1203–1253, 2022a。

+   Chen et al. [2023a] Minshuo Chen, Kaixuan Huang, Tuo Zhao, 和 Mengdi Wang. 扩散模型在低维数据上的分数近似、估计和分布恢复。*arXiv 预印本 arXiv:2302.07194*, 2023a。

+   Chen et al. [2021] Richard J Chen, Ming Y Lu, Tiffany Y Chen, Drew FK Williamson, 和 Faisal Mahmood. 机器学习中的合成数据在医学和医疗保健中的应用。*Nature Biomedical Engineering*, 5(6):493–497, 2021。

+   Chen et al. [2022b] Sitan Chen, Sinho Chewi, Jerry Li, Yuanzhi Li, Adil Salim, 和 Anru R Zhang. 采样就像学习分数一样简单：在最小数据假设下的扩散模型理论。*arXiv 预印本 arXiv:2209.11215*, 2022b。

+   Chen et al. [2023b] Sitan Chen, Sinho Chewi, Holden Lee, Yuanzhi Li, Jianfeng Lu, 和 Adil Salim. 概率流常微分方程是可以证明的快速。*arXiv 预印本 arXiv:2305.11798*, 2023b。

+   Chen et al. [2020b] Zixiang Chen, Yuan Cao, Quanquan Gu, 和 Tong Zhang. 针对两层神经网络的广义神经切线核分析。*Advances in Neural Information Processing Systems*, 33, 2020b。

+   Chizat 和 Bach [1812] Lenaic Chizat 和 Francis Bach. 关于监督可微编程中的懒惰训练的说明。（2018）。*arXiv 预印本 arXiv:1812.07956*, 1812。

+   Chizat 和 Bach [2018] Lénaïc Chizat 和 Francis Bach. 关于使用最优传输的过参数化模型的梯度下降的全局收敛性。在 *第 32 届国际神经信息处理系统会议论文集*，页码 3040–3050，2018。

+   Choi et al. [2017] Edward Choi, Siddharth Biswal, Bradley Malin, Jon Duke, Walter F Stewart, 和 Jimeng Sun. 使用生成对抗网络生成多标签离散患者记录。在 *医疗保健会议的机器学习*，页码 286–305。PMLR, 2017。

+   Dai et al. [2022] Damai Dai, Yutao Sun, Li Dong, Yaru Hao, Zhifang Sui, 和 Furu Wei. 为什么 GPT 能够在上下文中学习？语言模型在暗中执行梯度下降作为元优化器。*arXiv 预印本 arXiv:2212.10559*, 2022。

+   De Bortoli [2022] Valentin De Bortoli. 在流形假设下的去噪扩散模型的收敛性。*arXiv 预印本 arXiv:2208.05314*, 2022。

+   De Bortoli et al. [2021] Valentin De Bortoli, James Thornton, Jeremy Heng, 和 Arnaud Doucet. 扩散薛定谔桥及其在基于分数的生成建模中的应用。*Advances in Neural Information Processing Systems*, 34:17695–17709, 2021。

+   DeVore et al. [1989] Ronald A DeVore, Ralph Howard, 和 Charles Micchelli. 最优非线性逼近。*Manuscripta Mathematica*, 63(4):469–478, 1989。

+   Dhariwal 和 Nichol [2021] Prafulla Dhariwal 和 Alexander Nichol. 扩散模型在图像合成中胜过 GANs。*神经信息处理系统进展*，34:8780–8794，2021 年。

+   Dong 等 [2022] Qingxiu Dong、Lei Li、Damai Dai、Ce Zheng、Zhiyong Wu、Baobao Chang、Xu Sun、Jingjing Xu 和 Zhifang Sui. 关于上下文学习的调查。*arXiv 预印本 arXiv:2301.00234*，2022 年。

+   Donoho 和 Johnstone [1998] David L Donoho 和 Iain M Johnstone. 通过小波收缩进行极小估计。*统计年鉴*，26(3):879–921，1998 年。

+   Du 等 [2019] Simon Du、Jason Lee、Haochuan Li、Liwei Wang 和 Xiyu Zhai. 梯度下降找到深度神经网络的全局最小值。在 *国际机器学习会议*，第 1675–1685 页。PMLR，2019 年。

+   Du 等 [2018] Simon S Du、Xiyu Zhai、Barnabas Poczos 和 Aarti Singh. 梯度下降可证明优化过度参数化神经网络。在 *国际学习表征会议*，2018 年。

+   Dwork [2008] Cynthia Dwork. 差分隐私：结果综述。在 *计算模型理论与应用国际会议*，第 1–19 页。Springer，2008 年。

+   Esteban 等 [2017] Cristóbal Esteban、Stephanie L Hyland 和 Gunnar Rätsch. 使用递归条件 GANs 生成实值（医学）时间序列。*arXiv 预印本 arXiv:1706.02633*，2017 年。

+   Esteva 等 [2019] Andre Esteva、Alexandre Robicquet、Bharath Ramsundar、Volodymyr Kuleshov、Mark DePristo、Katherine Chou、Claire Cui、Greg Corrado、Sebastian Thrun 和 Jeff Dean. 深度学习在医疗保健中的指南。*自然医学*，25(1):24–29，2019 年。

+   Fan 等 [2021] Jianqing Fan、Cong Ma 和 Yiqiao Zhong. 深度学习的选择性概述。*统计科学：数学统计学会评论期刊*，36(2):264，2021 年。

+   Fang 和 Cheng [2022] Zhiying Fang 和 Guang Cheng. 深度卷积神经网络的最优学习率：加性岭函数。*arXiv 预印本 arXiv:2202.12119*，2022 年。

+   Farrell 等 [2021] Max H Farrell、Tengyuan Liang 和 Sanjog Misra. 用于估计和推断的深度神经网络。*Econometrica*，89(1):181–213，2021 年。

+   Feng 等 [2021] Han Feng、Shuo Huang 和 Ding-Xuan Zhou. CNNs 在球面分类上的泛化分析。*IEEE 神经网络与学习系统汇刊*，2021 年。

+   Frye 和 Efthimiou [2012] Christopher Frye 和 Costas J Efthimiou. p 维球面谐波。*arXiv 预印本 arXiv:1205.3548*，2012 年。

+   Garg 等 [2022] Shivam Garg、Dimitris Tsipras、Percy S Liang 和 Gregory Valiant. 变换器在上下文中能学到什么？一个简单函数类的案例研究。*神经信息处理系统进展*，35:30583–30598，2022 年。

+   Ghorbani 等 [2020a] Behrooz Ghorbani、Song Mei、Theodor Misiakiewicz 和 Andrea Montanari. 讨论：“使用 ReLU 激活函数的深度神经网络非参数回归”。2020a 年。

+   Ghorbani 等人 [2020b] Behrooz Ghorbani, Song Mei, Theodor Misiakiewicz, 和 Andrea Montanari. 神经网络何时优于核方法？*arXiv 预印本 arXiv:2006.13409*，2020b 年。

+   Giannou 等人 [2023] Angeliki Giannou, Shashank Rajput, Jy-yong Sohn, Kangwook Lee, Jason D Lee, 和 Dimitris Papailiopoulos. 循环变换器作为可编程计算机。*arXiv 预印本 arXiv:2301.13196*，2023 年。

+   Goodfellow 等人 [2014] Ian Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, 和 Yoshua Bengio. 生成对抗网络。*神经信息处理系统进展*，27，2014 年。

+   Goodfellow 等人 [2016] Ian Goodfellow, Yoshua Bengio, 和 Aaron Courville. *深度学习*。MIT 出版社，2016 年。

+   Grigorescu 等人 [2020] Sorin Grigorescu, Bogdan Trasnea, Tiberiu Cocias, 和 Gigel Macesanu. 自主驾驶的深度学习技术综述。*现场机器人学杂志*，37(3):362–386，2020 年。

+   Gui 等人 [2021] Jie Gui, Zhenan Sun, Yonggang Wen, Dacheng Tao, 和 Jieping Ye. 生成对抗网络综述：算法、理论与应用。*IEEE 知识与数据工程汇刊*，35(4):3313–3332，2021 年。

+   Han 等人 [2023] Chi Han, Ziqi Wang, Han Zhao, 和 Heng Ji. 大型语言模型的上下文学习解释为核回归。*arXiv 预印本 arXiv:2305.12766*，2023 年。

+   Han 等人 [2022] Zhi Han, Siquan Yu, Shao-Bo Lin, 和 Ding-Xuan Zhou. 深度 ReLU 网络在特征提取和泛化中的深度选择。*IEEE 模式分析与机器智能汇刊*，2022 年。

+   Hanin [2019] Boris Hanin. 具有有界宽度和 ReLU 激活的深度神经网络的通用函数逼近。*数学*，7(10):992，2019 年。

+   Heaton 等人 [2017] James B Heaton, Nick G Polson, 和 Jan Hendrik Witte. 深度学习在金融中的应用：深度投资组合。*应用随机模型在商业和工业中的应用*，33(1):3–12，2017 年。

+   Ho 等人 [2020] Jonathan Ho, Ajay Jain, 和 Pieter Abbeel. 去噪扩散概率模型。*神经信息处理系统进展*，33:6840–6851，2020 年。

+   Hornik 等人 [1989] Kurt Hornik, Maxwell Stinchcombe, 和 Halbert White. 多层前馈网络是通用逼近器。*神经网络*，2(5):359–366，1989 年。

+   Hu 等人 [2020] Tianyang Hu, Zuofeng Shang, 和 Guang Cheng. 在教师-学生设置下深度神经网络分类器的最佳收敛速度。*arXiv 预印本 arXiv:2001.06892*，2020 年。

+   Hu 等人 [2021] Tianyang Hu, Wenjia Wang, Cong Lin, 和 Guang Cheng. 正则化的重要性：对过参数化神经网络的非参数视角。发表于*国际人工智能与统计会议*，第 829–837 页。PMLR，2021 年。

+   Hu 等人 [2019] Wei Hu, Zhiyuan Li, 和 Dingli Yu. 针对嘈杂标签数据的简单有效正则化方法，具有泛化保证。发表于*国际学习表征会议*，2019 年。

+   Huang 等人 [2023] 余 Huang、袁程 Cheng 和英宾 Liang。变压器的上下文收敛。*arXiv 预印本 arXiv:2310.05249*，2023。

+   Imaizumi 和 Fukumizu [2019] 今泉正明 Imaizumi 和福水健治 Fukumizu。深度神经网络有效地学习非平滑函数。在 *第 22 届国际人工智能与统计会议* 上，页 869–878。PMLR，2019。

+   Imaizumi 和 Fukumizu [2022] 今泉正明 Imaizumi 和福水健治 Fukumizu。深度神经网络在估计具有奇点的超表面函数中的优势。*机器学习研究期刊*，23:1–54，2022。

+   Jacot 等人 [2018] 亚瑟·Jacot、克莱门特·洪勒 Hongler 和弗朗克·加布里埃尔 Gabriel。神经切线核：神经网络中的收敛性与泛化性。在 *NeurIPS* 上，2018。

+   Jiang 等人 [2018] 浩明 Jiang、哲辉 Chen、敏硕 Chen、锋 Liu、丁丁 Wang 和拓 Zhao。关于生成对抗网络在谱控制下的计算与泛化。在 *国际学习表征会议* 上，2018。

+   Jiao 等人 [2021] 雨灵 Jiao、国浩 Shen、远远 Lin 和建 Huang。对近似低维流形的深非参数回归。*arXiv 预印本 arXiv:2104.06708*，2021。

+   Juditsky 等人 [2009] 阿纳托利·B·朱迪茨基 Juditsky、奥列格·V·列普斯基 Lepski 和亚历山大·B·齐巴科夫 Tsybakov。复合函数的非参数估计。2009。

+   Kim 等人 [2022] 奇勇 Kim、彩晶 Lee 和诺成 Park。Stasy：基于分数的表格数据合成。在 *第十一届国际学习表征会议* 上，2022。

+   Kim 等人 [2021] 永代 Kim、一尚 Ohn 和东夏 Kim。深度神经网络分类的快速收敛速率。*神经网络*，138:179–197，2021。

+   Ko 等人 [2023] 赫允旭 Ko、南俊寿 Su 和肖明霍 Huo。关于神经网络分类器的过剩风险收敛速率。*提交至 IEEE 信息理论汇刊*，2023。

+   Lai 等人 [2023] 闵发 Lai、满云 Xu、瑞 Chen 和乾 Lin。宽神经网络在 $mathbb{R}$ 上的泛化能力。*arXiv 预印本 arXiv:2302.05933*，2023。

+   Lee 等人 [2022] 霍尔顿 Lee、建锋 Lu 和艺鑫 Tan。具有多项式复杂度的基于分数的生成建模的收敛性。*神经信息处理系统进展*，35:22870–22882，2022。

+   Lee 等人 [2023] 霍尔顿 Lee、建锋 Lu 和艺鑫 Tan。针对一般数据分布的基于分数的生成建模的收敛性。在 *国际算法学习理论会议* 上，页 946–985。PMLR，2023。

+   Lee 等人 [2018] 才勋 Lee、雅萨曼·巴赫里 Bahri、罗曼·诺瓦克 Novak、塞缪尔·S·肖恩霍尔兹 Schoenholz、杰弗里·佩宁顿 Pennington 和贾斯查·索尔-迪克斯坦 Sohl-Dickstein。深度神经网络作为高斯过程。在 *国际学习表征会议* 上，2018。

+   Li 等人 [2023a] 西名 Li、晨迪 Wang 和广 Cheng。差分隐私边际数据合成算法的统计理论。*arXiv 预印本 arXiv:2301.08844*，2023a。

+   Li et al. [2023b] Yingcong Li, M Emrullah Ildiz, Dimitris Papailiopoulos, 和 Samet Oymak. Transformers 作为算法：上下文学习中的泛化和隐式模型选择。*arXiv 预印本 arXiv:2301.07067*，2023 年。

+   Liang [2021] Tengyuan Liang. 生成对抗网络学习分布的效果。*机器学习研究期刊*，22(1):10366–10406，2021 年。

+   Liu et al. [2022] Xingchao Liu, Lemeng Wu, Mao Ye, 和 Qiang Liu. 让我们搭建桥梁：理解和扩展扩散生成模型。*arXiv 预印本 arXiv:2208.14699*，2022 年。

+   Lu et al. [2021] Jianfeng Lu, Zuowei Shen, Haizhao Yang, 和 Shijun Zhang. 平滑函数的深度网络逼近。*SIAM 数学分析期刊*，53(5):5465–5506，2021 年。

+   Ma et al. [2023] Cong Ma, Reese Pathak, 和 Martin J Wainwright. 在基于 RKHS 的非参数回归中最优应对协变量偏移。*统计年鉴*，51(2):738–761，2023 年。

+   Mammen and Tsybakov [1999] Enno Mammen 和 Alexandre B Tsybakov. 平滑判别分析。*统计年鉴*，27(6):1808–1829，1999 年。

+   Mei et al. [2018] Song Mei, Andrea Montanari, 和 Phan-Minh Nguyen. 两层神经网络的平均场视角。*美国国家科学院学报*，115(33):E7665–E7671，2018 年。

+   Mei et al. [2019] Song Mei, Theodor Misiakiewicz, 和 Andrea Montanari. 两层神经网络的平均场理论：无维界限和核极限。在*学习理论会议*，第 2388–2464 页。PMLR，2019 年。

+   Mhaskar et al. [2016] Hrushikesh Mhaskar, Qianli Liao, 和 Tomaso Poggio. 学习函数：深度是否比浅层更优。*arXiv 预印本 arXiv:1603.00988*，2016 年。

+   Mhaskar [1996] Hrushikesh N Mhaskar. 神经网络对平滑和解析函数的最优近似。*神经计算*，8(1):164–177，1996 年。

+   Montanelli and Du [2019] Hadrien Montanelli 和 Qiang Du. 使用稀疏网格的深度 ReLU 网络的新误差界限。*SIAM 数据科学期刊*，1(1):78–92，2019 年。

+   Müller [1997] Alfred Müller. 积分概率度量及其生成函数类。*应用概率进展*，29(2):429–443，1997 年。

+   Müller-Franzes et al. [2022] Gustav Müller-Franzes, Jan Moritz Niehues, Firas Khader, Soroosh Tayebi Arasteh, Christoph Haarburger, Christiane Kuhl, Tianci Wang, Tianyu Han, Sven Nebelung, Jakob Nikolas Kather, 等等。扩散概率模型在医学图像中超越 GAN。*arXiv 预印本 arXiv:2212.07501*，2022 年。

+   Neyshabur [2017] Behnam Neyshabur. 深度学习中的隐式正则化。*arXiv 预印本 arXiv:1709.01953*，2017 年。

+   Neyshabur et al. [2014] Behnam Neyshabur, Ryota Tomioka, 和 Nathan Srebro. 寻找真正的归纳偏差：隐式正则化在深度学习中的作用。*arXiv 预印本 arXiv:1412.6614*，2014 年。

+   Nguyen 和 Pham [2020] Phan-Minh Nguyen 和 Huy Tuan Pham. 多层神经网络均场极限的严谨框架。*arXiv 预印本 arXiv:2001.11443*，2020 年。

+   Nitanda 和 Suzuki [2017] Atsushi Nitanda 和 Taiji Suzuki. 无限集的随机粒子梯度下降。*arXiv 预印本 arXiv:1712.05438*，2017 年。

+   Nitanda 和 Suzuki [2020] Atsushi Nitanda 和 Taiji Suzuki. 神经切线核范式下的平均随机梯度下降的最优速率。发表于 *国际学习表示会议*，2020 年。

+   Oko et al. [2023] Kazusato Oko, Shunta Akiyama, 和 Taiji Suzuki. 扩散模型是极小极大最优分布估计器。*arXiv 预印本 arXiv:2303.01861*，2023 年。

+   Otter et al. [2020] Daniel W Otter, Julian R Medina, 和 Jugal K Kalita. 深度学习在自然语言处理中的应用综述。*IEEE 神经网络和学习系统汇刊*，32(2)：604–624，2020 年。

+   Ouyang et al. [2023a] Yidong Ouyang, Liyan Xie, 和 Guang Cheng. 通过对比引导扩散过程提高对抗鲁棒性。发表于 *国际机器学习会议*，页码 26699–26723。PMLR，2023 年。

+   Ouyang et al. [2023b] Yidong Ouyang, Liyan Xie, Chongxuan Li, 和 Guang Cheng. Missdiff：在缺失值表格数据上训练扩散模型。*arXiv 预印本 arXiv:2307.00467*，2023 年。

+   Oymak 和 Soltanolkotabi [2020] Samet Oymak 和 Mahdi Soltanolkotabi. 向适度过参数化迈进：浅层神经网络训练的全局收敛保证。*IEEE 信息理论选择领域期刊*，1(1)：84–105，2020 年。

+   Pathak et al. [2022] Reese Pathak, Cong Ma, 和 Martin Wainwright. 一种新的协变量漂移相似性度量及其在非参数回归中的应用。发表于 *国际机器学习会议*，页码 17517–17530。PMLR，2022 年。

+   Petersen 和 Voigtlaender [2018] Philipp Petersen 和 Felix Voigtlaender. 使用深度 ReLU 神经网络对分段光滑函数的最优逼近。*神经网络*，108：296–330，2018 年。

+   Ray 和 Schmidt-Hieber [2017] Kolyan Ray 和 Johannes Schmidt-Hieber. 非负函数根的正则性类别。*纯粹与应用数学年鉴 (1923-)*，196：2091–2103，2017 年。

+   Ryzhik [2023] Lenya Ryzhik. 数学 272 讲义，2023 年冬季。页码 1–183，2023 年。

+   Särkkä 和 Solin [2019] Simo Särkkä 和 Arno Solin. *应用随机微分方程*，第 10 卷。剑桥大学出版社，2019 年。

+   Schmidt-Hieber [2020] Johannes Schmidt-Hieber. 使用 ReLU 激活函数的深度神经网络的非参数回归。*统计年鉴*，48(4)：1875–1897，2020 年。

+   Schreuder et al. [2021] Nicolas Schreuder, Victor-Emmanuel Brunel, 和 Arnak Dalalyan. 无主导性的生成模型的统计保证。发表于 *算法学习理论*，页码 1051–1071。PMLR，2021 年。

+   Shen et al. [2022] Guohao Shen, Yuling Jiao, Yuanyuan Lin, 和 Jian Huang. 在 Sobolev 空间中使用 CNN 进行近似：及其在分类中的应用。*神经信息处理系统的进展*，第 35 卷:2876–2888，2022 年。

+   Shen et al. [2021] Zuowei Shen, Haizhao Yang, 和 Shijun Zhang. 由神经元数量表征的深度网络近似。*arXiv 预印本 arXiv:1906.05497*，2021 年。

+   Song et al. [2020] Yang Song, Jascha Sohl-Dickstein, Diederik P Kingma, Abhishek Kumar, Stefano Ermon, 和 Ben Poole. 通过随机微分方程的评分基础生成建模。在 *国际学习表征会议*，2020 年。

+   Song and Yang [2019] Zhao Song 和 Xin Yang. 通过矩阵 Chernoff 界限的过参数化的二次充分性。*arXiv 预印本 arXiv:1906.03593*，2019 年。

+   Sugiyama and Kawanabe [2012] Masashi Sugiyama 和 Motoaki Kawanabe. *非平稳环境中的机器学习：协变量偏移适应导论*。麻省理工学院出版社，2012 年。

+   Suh et al. [2021] Namjoon Suh, Hyunouk Ko, 和 Xiaoming Huo. 非参数回归观点：在噪声观测下的过参数化深度 ReLU 网络的泛化。在 *国际学习表征会议*，2021 年。

+   Suh et al. [2022] Namjoon Suh, Tian-Yi Zhou, 和 Xiaoming Huo. 通过深度 ReLU 网络在高维球面上的函数的近似与非参数估计。在 *第十一届国际学习表征会议*，2022 年。

+   Suh et al. [2023] Namjoon Suh, Xiaofeng Lin, Din-Yin Hsieh, Merhdad Honarkhah, 和 Guang Cheng. Autodiff：结合自动编码器和扩散模型进行表格数据合成。*arXiv 预印本 arXiv:2310.15479*，2023 年。

+   Suzuki [2018] Taiji Suzuki. 深度 ReLU 网络在 Besov 和混合平滑 Besov 空间中的适应性：最优速率和维度诅咒。在 *国际学习表征会议*，2018 年。

+   Suzuki and Nitanda [2021] Taiji Suzuki 和 Atsushi Nitanda. 深度学习对各向异性 Besov 空间模型平滑性的内在维度具有适应性。*神经信息处理系统的进展*，第 34 卷:3609–3621，2021 年。

+   Tang and Yang [2022] Rong Tang 和 Yun Yang. 在对抗性损失下，未知子流形上的分布估计的极小极大速率。*arXiv 预印本 arXiv:2202.09030*，2022 年。

+   Tsybakov [2004] Alexander B Tsybakov. 统计学习中的分类器最佳聚合。*统计年鉴*，第 32 卷第 1 期：135–166，2004 年。

+   Van de Geer [2000] Sara A Van de Geer. *M-估计中的经验过程*，第 6 卷。剑桥大学出版社，2000 年。

+   Vaswani et al. [2017] Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N Gomez, Łukasz Kaiser, 和 Illia Polosukhin. 《注意力机制就是你所需要的一切》。*神经信息处理系统的进展*，第 30 卷，2017 年。

+   冯·奥斯瓦尔德等人 [2023] 约翰内斯·冯·奥斯瓦尔德、埃文德·尼克拉松、埃托雷·兰达佐、若昂·萨克拉门托、亚历山大·莫尔丁采夫、安德烈·兹莫金诺夫和马克斯·弗拉季米罗夫。变换器通过梯度下降在上下文中学习。在*国际机器学习会议*，第 35151–35174 页。PMLR，2023 年。

+   韦等人 [2019] 科林·韦、杰森·D·李、强刘和腾宇·马。正则化很重要：神经网络与其诱导核的泛化和优化。*神经信息处理系统进展*，32，2019 年。

+   吴等人 [2019] 小霞吴、Simon S Du 和 Rachel Ward。适应性梯度方法在过参数化神经网络中的全局收敛。*arXiv 预印本 arXiv:1902.07111*，2019 年。

+   邢等人 [2022a] 岳邢、齐凡宋和光程。为什么人工生成的数据有助于对抗鲁棒性。*神经信息处理系统进展*，35:954–966，2022 年。

+   邢等人 [2022b] 岳邢、齐凡宋和光程。无标签数据的帮助：极小极大分析与对抗鲁棒性。在*国际人工智能与统计会议*，第 136–168 页。PMLR，2022 年。

+   徐等人 [2023a] 世荣徐、威尔·魏孙和光程。合成数据生成的效用理论。*arXiv 预印本 arXiv:2305.10015*，2023 年。

+   徐等人 [2023b] 世荣徐、晨迪王、威尔·魏孙和光程。在局部标签差分隐私下使用随机响应机制进行二分类。*机器学习研究会刊*，2023b 年。

+   杨 [2020] 格雷格·杨。张量程序 II：适用于任何架构的神经切线核。*arXiv 预印本 arXiv:2006.14548*，2020 年。

+   杨和胡 [2020] 格雷格·杨和爱德华·J·胡。无限宽度神经网络中的特征学习。*arXiv 预印本 arXiv:2011.14522*，2020 年。

+   杨等人 [2022] 灵杨、志龙张、杨松、申达洪、润生徐、岳赵、英霞邵、文韬张、彬崔和明轩杨。扩散模型：方法与应用的全面综述。*arXiv 预印本 arXiv:2209.00796*，2022 年。

+   雅罗茨基 [2017] 德米特里·雅罗茨基。深度 ReLU 网络的逼近误差界限。*神经网络*，94:103–114，2017 年。

+   叶胡戴和沙米尔 [2019] 吉拉德·叶胡戴和奥哈德·沙米尔。随机特征在理解神经网络中的力量和局限性。*神经信息处理系统进展*，32，2019 年。

+   曾等人 [2022] 线里曾、埃德加·多布里班和光程。在群体公平性下的贝叶斯最优分类器。*arXiv 预印本 arXiv:2202.09724*，2022 年。

+   张等人 [2021] 致远张、萨米·本吉奥、莫里茨·哈特、本杰明·瑞赫特和奥里奥尔·维尼亚尔斯。理解深度学习（仍然）需要重新思考泛化。*ACM 通讯*，64(3):107–115，2021 年。

+   张等人 [2017] 彭川张、强刘、邓永周、陶徐和晓东·何。在 GANs 中对抗性与泛化的权衡。*arXiv 预印本 arXiv:1711.02771*，2017 年。

+   Zhang 等 [2023] Ruiqi Zhang、Spencer Frei 和 Peter L Bartlett。训练的变换器在上下文中学习线性模型。*arXiv 预印本 arXiv:2306.09927*，2023。

+   Zhou 和 Huo [2023] Tian-Yi Zhou 和 Xiaoming Huo。使用深度 ReLU 网络对高斯混合模型生成的数据进行分类。*arXiv 预印本 arXiv:2308.08030*，2023。

+   Zou 和 Gu [2019] Difan Zou 和 Quanquan Gu. 对过参数化深度神经网络训练的改进分析。*神经信息处理系统进展*，2019。

+   Zou 等 [2018] Difan Zou、Yuan Cao、Dongruo Zhou 和 Quanquan Gu。随机梯度下降优化过参数化深度 ReLU 网络。arxiv e-prints, art. *arXiv 预印本 arXiv:1811.08888*，2018。
