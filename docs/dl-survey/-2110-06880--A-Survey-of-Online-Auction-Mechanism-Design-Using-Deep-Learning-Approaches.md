<!--yml

类别：未分类

日期：2024-09-06 19:50:33

-->

# [2110.06880] 使用深度学习方法的在线拍卖机制设计综述

> 来源：[`ar5iv.labs.arxiv.org/html/2110.06880`](https://ar5iv.labs.arxiv.org/html/2110.06880)

# 使用深度学习方法的在线拍卖机制设计综述

张展豪

统计学系

哥伦比亚大学

zz2760@columbia.edu

###### 摘要

在线拍卖在近年来变得非常普及。平台管理员正在努力完善他们的拍卖机制，以实现高利润，同时保持公平的资源分配。随着计算技术的进步和理论框架的瓶颈，研究人员正转向使用深度学习方法的在线拍卖设计。在本文中，我们总结了一些在拍卖机制设计中采用的常见深度学习基础设施，并展示了这些架构的演变过程。我们还讨论了研究人员如何在大型和动态的工业环境中应对约束和关注点。最后，我们指出了几个目前尚未解决的问题，以供未来的研究方向参考。

## 1 介绍

拍卖作为一种交换商品和货物的方式已经被采用了几个世纪。传统上，广义第二价格拍卖（GSP）和维克雷-克拉克-格罗夫斯拍卖（VCG）被广泛使用。然而，如果卖方有多个物品进行竞标，GSP 不再是一个真实的机制。VCG 是一种基于封闭第二价格拍卖的拍卖机制，获胜者根据其他参与者社会福利的减少来收取费用。然而，VCG 机制产生的卖方收入较低，并且未能在竞标者集和竞标金额中强制卖方收入的单调性。它也是一种不真实的机制，易受到同一人多次竞标或失败竞标者的勾结[5]。

拥有激励兼容性（IC）和个体理性（IR）属性的拍卖机制非常理想。如果一个拍卖是 IC 的，那么所有竞标者将真实地揭示他们对物品的私人估价，这样平台管理员就不必考虑竞标者的策略行为，因此能够建立一个可靠且可预测的系统。如果拍卖系统是 IR 的，那么所有参与者都保证具有非负效用，这是一项非常重要的特性，使得系统能够在长期内留住客户。

Myerson 的开创性工作[20]定义了销售单一物品的最佳策略无关拍卖，但在此设置之外，对于策略无关和收益最大化的拍卖的特征化进展有限[14]。在线拍卖平台的动态性质[6, 27, 31]使问题变得更加复杂，因为竞标者、物品和平台的目标随着时间的推移而变化。同时，需要考虑多个性能指标，以使拍卖系统对竞标者、卖家和平台具有吸引力[16, 27, 31]。

随着技术的进步，研究人员正在将焦点转向深度学习方法来设计拍卖机制。根据我们所知，深度学习架构建立在混合多层感知机基础设施、RegretNet 基础设施[9]、强化学习基础设施或 DeepSet 基础设施[30]之上。得益于现代计算能力，研究人员不仅能够最大化收益，还能处理数据稀疏性和高维数据，优化多个性能指标，防止欺诈，并提升公平性。

本文组织结构如下：我们将首先介绍拍卖机制设计中深度神经网络的四种常见基础设施。接着，我们将讨论研究人员如何解决除最大化总收益之外的约束和问题。最后，我们将指出一些未解决的问题和潜在的未来方向。

## 2 混合多层感知机 (MLP) 基础设施

许多神经网络结构通过将几个 MLP 结构堆叠成一个连贯的网络来构建[24, 32, 25, 17]。该网络通常由多个组件组成，每个组件是一个完全连接的前馈神经网络。

最精致的架构是 MenuNet [24]，它由机制网络和买家网络组成。机制网络以一维 1 为输入，输出分配矩阵和定价向量。分配矩阵包含所有物品的分配，该矩阵通过一个全连接层及其后跟的 sigmoid 激活函数获得。支付向量是通过将常数 1 乘以一个向量获得的，用于表示不同菜单项的价格。买家网络不需要任何训练。它从机制网络获取输出，并根据买家的价值配置计算最终效用。由于网络结构非常简单，MenuNet 的训练非常快。它基于税收原则 [28]，该原则表明，仅让买家进行选择即可提供 IC 机制。它不需要买家的效用函数，因为网络只输出买家的策略。它不对买家的估值做任何假设，也不需要对网络施加任何额外的约束（如 IC 和 IR）。理论证明表明，MenuNet 总是返回在菜单大小为 2 或 3 时 IC 满足的收入最优机制。

Zhou 等人提出了用于点击率预测的 Deep Interest Network [32]。该网络基于 MLP 结构，但旨在解决传统 MLP 中固定长度表示向量所带来的瓶颈，这种固定长度表示向量在捕捉用户丰富历史行为中的多样兴趣方面能力有限。作者设计了一种局部激活单元，能够根据特定广告从历史行为中自适应地学习用户兴趣的表示。他们采用的数据自适应激活是 Dice（方程 1 基础设施 ‣ 基于深度学习方法的在线拍卖机制设计调查")），这是 PReLu [13] 的一种推广。

|  | $f(s)=p(s)\cdot s+(1-p(s))\cdot\alpha s,p(s)=\frac{1}{1+e^{-\frac{s-E[s]}{\sqrt{Var[s]+\epsilon}}}}$ |  | (1) |
| --- | --- | --- | --- |

在训练阶段，$E[s]$ 和 $Var[s]$ 是每个小批量输入的均值和方差，而在测试阶段，$E[s]$ 和 $Var[s]$ 是数据上 $E[s]$ 和 $Var[s]$ 的移动平均。$\epsilon$ 是一个小常数，作者将其设置为 $10^{-8}$。

他们对不同的广告采用不同的表示向量。嵌入层结合了单一嵌入向量（one-hot）和多个嵌入向量（multi-hot）。添加了池化和连接层，将嵌入向量列表转换为相同长度，以便网络可以允许不同用户有不同数量的行为。

Shin 等人使用深度学习框架将充电调度问题转化为拍卖问题[25]。该设计基于 Myerson 拍卖的概念[20]，这是最有效的单项拍卖之一，能够实现收入最优化。充电调度的一个主要挑战是对竞标者数量分布缺乏先验知识。当买家的真实估值信息不准确，且买家不知道其他买家的私人真实价值时，使用拍卖方法非常有用。买家的价值由无人机的紧迫性表示，而卖家的收入来自于资源分配的支付。由于 Myerson 拍卖系统要求完全了解竞标分布以计算期望支付，Shin 等人使用深度神经网络对虚拟估值函数、分配规则和支付规则进行参数化。

网络从一个单调网络开始，该网络使用由网络参数化的虚拟估值函数$\phi^{mononet}$将无人机的竞标 $b_{i}$ 转换为 $\bar{b}_{i}$。在 $\phi^{mononet}$ 中，$\phi^{shared}$ 的所有结果（方程 3）都使用相同的权重计算，而 $\phi_{i}$（方程 2）则使用不同的权重计算每个竞标的结果。

|  | $b_{i}^{\prime}=\phi_{i}(b_{i})=\min_{1\leq g\leq\mathcal{G}}\{\max_{1\leq n\leq\mathcal{N}}(w_{g,n}^{i}b_{i}+\beta_{g,n}^{i})\}$ |  | (2) |
| --- | --- | --- | --- |
|  | $\bar{b}_{i}=\phi_{i}^{shared}(b_{i}^{\prime})=\min_{1\leq g\leq\mathcal{G}}\{\max_{1\leq n\leq\mathcal{N}}(w_{g,n}^{shared}b_{i}^{\prime}+\beta_{g,n}^{shared})\}$ |  | (3) |

支付规则网络接收来自单调网络的输出 $\bar{b}_{i}$，并根据方程 4 返回 $\bar{p}_{i}$。然后，支付值使用 $\phi^{mononet}$ 的逆函数（方程 5，6）计算。最后，分配规则网络将最高的胜出概率分配给具有正变换竞标的最高竞标者。

|  | $\bar{p}_{i}=ReLU\{\max_{j\neq i}(\bar{b}_{i})\}$ |  | (4) |
| --- | --- | --- | --- |
|  | $p_{i}^{\prime}=\phi_{shared}^{-1}(\bar{p}_{i})=\max_{1\leq g\leq\mathcal{G}}\{\min_{1\leq n\leq\mathcal{N}}(w_{g,n}^{shared})^{-1}(\bar{p}_{i}-\beta_{g,n}^{shared})\}$ |  | (5) |
|  | $p_{i}=\phi_{i}^{-1}(p_{i}^{\prime})=\max_{1\leq g\leq\mathcal{G}}\{\min_{1\leq n\leq\mathcal{N}}(w_{g,n}^{i})^{-1}(p_{i}^{\prime}-\beta_{g,n}^{i})\}$ |  | (6) |

Luong 等人基于分析解 [20] 构建了一种神经网络 [17] 用于边缘计算资源管理，该网络在确保 IC 和 IR 的同时保证了收入最大化。网络结构还具有三个关键组件，如 [25] 中所示：将竞标转化为转换版本的单调变换函数的神经网络参数化、将转换后的竞标映射到分配概率向量的分配规则，以及基于最大非负转换竞标的条件支付规则。分配和支付规则是从 SPA-0 推导出的，即具有 0 保留价的第二价格拍卖，其中保留价是卖家愿意从买家那里接受的最低价格。

Dutting 等人提出的 RochetNet [9] 也是 MLP 的一种应用。RochetNet 是一种单层神经网络，它接收竞标并输出最大非负转换值。它用于建模非负、单调、凸和 Lipschitz 效用函数，使用 $J$ 个具有非负系数的线性函数。RochetNet 很容易扩展到具有单位需求估值的单一竞标者¹¹单位需求估值：子集的价值是该子集内的最大个人估值。RochetNet 中的每个线性函数对应于菜单上的一个选项，其分配概率和支付通过其斜率和截距进行编码。

Golowich 等人提出的 MoulinNet [11] 也采用了 MLP 的结构，用于确定代理人偏好的最优设施位置。MoulinNet 是一种单调前馈神经网络，它学习广义中位数规则 [19]。对于单设施机制，方程 7 中的机制是策略无关的，它选择代理人最偏好的位置的中位数（代理人的峰值）。网络的输入是二进制编码向量 $\nu(S)$，表示 $S$ 中竞标的项目是否被选择。$w$ 和 $b$ 是 MoulinNet 中的参数。$u_{i}$ 是代理人 $i$ 的效用函数，$\tau$ 表示设施的峰值。网络的输出是基于效用的最优选择规则。

|  | $f^{w,b}(u)=\min_{S\subseteq N}\{\max_{i\in S}\{\tau(u_{i}),h^{w,b}(\nu(S))\}\}$ |  | (7) |
| --- | --- | --- | --- |

## 3 RegretNet 基础设施

RegretNet [9]由 Dutting 等人提出，包含一个分配网络和一个支付网络。这两者都基于 MLP 基础设施，但 RegretNet 已在各种设置中的拍卖设计中被采用和扩展[10，11，21，14]。

RegretNet 架构需要两个基本假设：加性估值²²2 加性估值：代理人对一个子集物品的估值是单个物品估值的总和。和单位需求估值。分配网络和支付网络都将投标作为输入，将其输入到具有独立参数的 MLP 结构网络中，然后根据两个网络的输出返回总支付。因此，这两个网络一起进行训练。网络使用 sigmoidal 单元将支付向量标准化为[0, 1]，以确保 IR 约束得到执行，即投标人不会为分配支付超出其预期价值的费用。

目标函数旨在最小化经验损失（负收入），同时满足 IC 和 IR 约束。IC 约束可以通过投标人的经验后悔概念来执行，即考虑所有可能的不诚实投标的情况下，效用的最大增加。经验后悔由经验后悔估计，表示为$\hat{rgt}_{i}(w)$。因此，目标函数变为（方程式 8）：

|  | $\begin{split}\min_{w\in\mathbb{R}^{d}}-\frac{1}{L}\sum_{l=1}^{L}\sum_{i=1}^{n}p_{i}^{w}(v^{(l)})\\ \text{s.t. }\hat{rgt}_{i}(w)=0,\forall i\in N.\end{split}$ |  | (8) |
| --- | --- | --- | --- |

优化通过拉格朗日乘数实现，增加了一个二次惩罚项以违反约束（方程式 9）：

|  | $\mathcal{C}_{\rho}(w;\lambda)=-\frac{1}{L}\sum_{l=1}^{L}\sum_{i=1}^{n}p_{i}^{w}(v^{(l)})+\sum_{i\in N}\lambda_{i}\hat{rgt}_{i}(w)+\frac{\rho}{2}\sum_{i\in N}(\hat{rgt}_{i}(w))^{2}$ |  | (9) |
| --- | --- | --- | --- |

Feng 等人构建了一个基于 RegretNet 结构的神经网络[10]，包括一个分配网络和一个支付网络。它通过结合预算约束以及处理 Bayesian Incentive Compatible (BIC) ³³3Bayesian Incentive Compatible：在其他投标人诚实报告的情况下，真诚告知是对投标人最优策略。和条件 IC 约束来扩展 RegretNet 基础设施。Dutting 等人通过要求经验后悔为零来执行 IC，而 Feng 等人通过构建适当的后悔概念来处理更一般的 IC 形式。

假设我们有一个规则为 $(a,p)$ 的拍卖。为处理 BIC，Feng 等人将经验中期后悔 $rgt_{i}(a,p)$（方程 10）约束为零。为处理条件 IC/BIC，他们将经验条件后悔约束为零。他们还将个体理性（IR） $irp_{i}(a,p)$（方程 11）和预算约束（BC） $bcp_{i}(a,p)$（方程 12）作为惩罚。

|  | $rgt_{i}(a,p)=E_{t_{i}\sim F_{i}}[\max_{t_{i}^{\prime}\in\mathcal{T}_{i}}1_{\mathcal{P}_{i}(t_{i}^{\prime})\leq b_{i}}(\mathcal{U}_{i}(t_{i},t_{i}^{\prime})-\mathcal{U}_{i}(t_{i},t_{i}))]$ |  | (10) |
| --- | --- | --- | --- |
|  | $irp_{i}(a,p)=E_{t_{i}\sim F_{i}}[\max\{0,-\mathcal{U}_{i}(t_{i},t_{i})\}]$ |  | (11) |
|  | $bcp_{i}(a,p)=E_{t_{i}\sim F_{i}}[\max\{0,\mathcal{P}_{i}(t_{i})-b_{i}\}]$ |  | (12) |

损失函数是负期望收益 $\mathcal{L}(a,p)=-E_{t\sim F}[\sum_{i=1}^{n}p_{i}(t)]$。令 $w\in\mathbb{R}^{d}$ 表示分配网络的参数，由 $a^{w}$ 表示的诱导分配规则，以及 $w^{\prime}\in\mathbb{R}^{d^{\prime}}$ 表示支付网络的参数，由 $p^{w^{\prime}}$ 表示的诱导支付规则。目标函数最终在方程 13 中给出。目标函数使用 Augmented Lagrangian Solver 进行训练，如 Dutting 等所述，其中对每个约束添加了二次罚项。

|  | <math   alttext="\begin{split}\min_{w\in\mathbb{R}^{d},w^{\prime}\in\mathbb{R}^{d^{\prime}}}\mathcal{L}(a^{w},p^{w^{\prime}})\\ \text{s.t. }rgt_{i}(a^{w},p^{w^{\prime}})=0,\forall i\in[n]\\

$irp_{i}(a^{w},p^{w^{\prime}})=0,\forall i\in[n]\\$

bcp_{i}(a^{w},p^{w^{\prime}})=0,\forall i\in[n]\\

\end{split}" display="block"><semantics ><mtable displaystyle="true" rowspacing="0pt" ><mtr ><mtd columnalign="right" ><mrow ><mrow ><munder ><mi >min</mi><mrow ><mrow  ><mi >w</mi><mo >∈</mo><msup ><mi >ℝ</mi><mi >d</mi></msup></mrow><mo >,</mo><mrow ><msup ><mi >w</mi><mo >′</mo></msup><mo >∈</mo><msup ><mi >ℝ</mi><msup ><mi >d</mi><mo >′</mo></msup></msup></mrow></mrow></munder><mo lspace="0.167em"  >⁡</mo><mi >ℒ</mi></mrow><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><msup ><mi >a</mi><mi >w</mi></msup><mo >,</mo><msup ><mi >p</mi><msup ><mi  >w</mi><mo >′</mo></msup></msup><mo stretchy="false"  >)</mo></mrow></mrow></mtd></mtr><mtr ><mtd  columnalign="right" ><mrow ><mrow ><mrow ><mtext  >s.t. </mtext><mo lspace="0em" rspace="0em"  >​</mo><mi >r</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >g</mi><mo lspace="0em" rspace="0em"  >​</mo><msub ><mi  >t</mi><mi >i</mi></msub><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><msup ><mi >a</mi><mi >w</mi></msup><mo >,</mo><msup ><mi >p</mi><msup ><mi >w</mi><mo >′</mo></msup></msup><mo stretchy="false"  >)</mo></mrow></mrow><mo >=</mo><mn >0</mn></mrow><mo >,</mo><mrow ><mrow ><mo rspace="0.167em" >∀</mo><mi >i</mi></mrow><mo >∈</mo><mrow ><mo stretchy="false"  >[</mo><mi >n</mi><mo stretchy="false"  >]</mo></mrow></mrow></mrow></mtd></mtr><mtr ><mtd  columnalign="right" ><mrow ><mrow ><mrow ><mi  >i</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >r</mi><mo lspace="0em" rspace="0em"  >​</mo><msub ><mi  >p</mi><mi >i</mi></msub><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><msup ><mi >a</mi><mi >w</mi></msup><mo >,</mo><msup ><mi >p</mi><msup ><mi >w</mi><mo >′</mo></msup></msup><mo stretchy="false"  >)</mo></mrow></mrow><mo >=</mo><mn >0</mn></mrow><mo >,</mo><mrow ><mrow ><mo rspace="0.167em" >∀</mo><mi >i</mi></mrow><mo >∈</mo><mrow ><mo stretchy="false"  >[</mo><mi >n</mi><mo stretchy="false"  >]</mo></mrow></mrow></mrow></mtd></mtr><mtr ><mtd  columnalign="right" ><mrow ><mrow ><mrow ><mi  >b</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >c</mi><mo lspace="0em" rspace="0em"  >​</mo><msub ><mi  >p</mi><mi >i</mi></msub><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >(</mo><msup ><mi >a</mi><mi >w</mi></msup><mo >,</mo><msup ><mi >p</mi><msup ><mi >w</mi><mo >′</mo></msup></msup><mo stretchy="false"  >)</mo></mrow></mrow><mo >=</mo><mn >0</mn></mrow><mo >,</mo><mrow ><mrow ><mo rspace="0.167em" >∀</mo><mi >i</mi></mrow><mo >∈</mo><mrow ><mo stretchy="false"  >[</mo><mi >n</mi><mo stretchy="false"  >]</mo></mrow></mrow></mrow></mtd></mtr></mtable><annotation-xml encoding="MathML-Content" ><apply ><csymbol cd="ambiguous" >formulae-sequence</csymbol><apply ><csymbol cd="ambiguous" >formulae-sequence</csymbol><apply ><apply ><apply ><apply ><csymbol cd="ambiguous" >subscript</csymbol><apply ><csymbol cd="ambiguous" >formulae-sequence</csymbol><apply ><ci >𝑤</ci><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >ℝ</ci><ci >𝑑</ci></apply></apply><apply ><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑤</ci><ci >′</ci></apply><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >ℝ</ci><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑑</ci><ci >′</ci></apply></apply></apply></apply></apply><ci >ℒ</ci></apply><interval closure="open"  ><apply ><csymbol cd="ambiguous"  >superscript</csymbol><ci >𝑎</ci><ci >𝑤</ci></apply><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑝</ci><apply  ><csymbol cd="ambiguous"  >superscript</csymbol><ci >𝑤</ci><ci >′</ci></apply></apply></interval><ci ><mtext >s.t. </mtext></ci><ci >𝑟</ci><ci  >𝑔</ci><apply ><csymbol cd="ambiguous"  >subscript</csymbol><ci >𝑡</ci><ci >𝑖</ci></apply><interval closure="open" ><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑎</ci><ci >𝑤</ci></apply><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑝</ci><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑤</ci><ci >′</ci></apply></apply></interval></apply><cn type="integer"  >0</cn></apply><apply ><apply ><apply ><csymbol cd="latexml"  >for-all</csymbol><ci >𝑖</ci></apply><apply ><apply ><csymbol cd="latexml"  >delimited-[]</csymbol><ci >𝑛</ci></apply><ci >𝑖</ci><ci >𝑟</ci><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑝</ci><ci >𝑖</ci></apply><interval closure="open" ><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑎</ci><ci >𝑤</ci></apply><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑝</ci><apply ><csymbol cd="ambiguous" >superscript</csymbol><ci >𝑤</ci><ci >′</ci></apply></apply></interval></apply></apply><apply ><cn type="integer"  >0</cn></apply></apply></apply><apply ><apply ><apply ><csymbol cd="latexml" >for-all</csymbol><ci >𝑖</ci></apply><apply ><apply ><csymbol cd="latexml" >delimited-[]</csymbol><ci >𝑛</ci></apply

Golowich 等人提出了 RegretNet-nm [11]，它能够提供不受现有多设施位置问题表征结果限制的一般机制。悔恨的概念扩展到设施位置机制中，作为代理通过误报其偏好而能够实现的最大期望效用增益。

网络结构与 RegretNet 相同，只是输入是代理的峰值。误报告的峰值在 $[0,1]$ 范围内均匀采样，粒度为 $\frac{1}{M}$。事后悔恨被集成到目标函数中，使用增广拉格朗日求解器，该求解器使用二次惩罚项。RegretNet-nm 为使用神经网络方法进行无金钱设置的机制设计（如匹配和分配问题）开辟了新天地。

PreferenceNet [21] 是 RegretNet 的另一个扩展。它在拍卖设计中编码了人类的偏好。网络结构由 RegretNet 和一个 3 层的 MLP 组成。这两个组件以 EM 方式进行训练：首先使用均匀抽取的分配样本训练 MLP，并基于真实标签使用二元交叉熵损失进行优化。然后，使用增广拉格朗日求解器训练 RegretNet。

整个 PreferenceNet 的损失函数在方程 14 中定义，其中 $\mathcal{L}_{s}$ 是训练好的 MLP 的输出。最后，从部分训练好的 RegretNet 中每 $c$ 轮采样分配和支付，并用它们来增强 MLP 的训练集，以适应训练过程中分配的分布变化。

|  | $\begin{split}\mathcal{C}_{\rho}(w;\lambda)=-\frac{1}{L}\sum_{l=1}^{L}\sum_{i\in N}p_{i}^{w}(v^{(l)})+\mathcal{L}_{rgt}-\mathcal{L}_{s}\\ \text{其中 }\mathcal{L}_{rgt}=\sum_{i\in N}\lambda_{(r,i)}\text{rgt}_{i}(w)+\frac{\rho_{r}}{2}(\sum_{i\in N}\text{rgt}_{i}(w))^{2},\mathcal{L}_{s}=\sum_{j\in M}s_{j}\end{split}$ |  | (14) |
| --- | --- | --- | --- |

Peri 等人提出了偏好分类准确度（PCA）指标来评估学习到的拍卖模型满足任意约束的程度。PCA 是通过满足真实约束的测试投标比例来计算的。然后，作者通过分配之间的成对比较来引出偏好。每组输入分配都与其他 n 个分配在其偏好分数上进行比较，并根据其偏好分数是否高于大多数其他分配，将其标记为正面或负面样本。

Kuo 等人提出的 ProportionNet [14] 也基于 RegretNet 的基础设施。与大多数处理拍卖机制设计的神经网络一样，它在组合估值设置下不起作用。在加性估值和单位需求估值的假设下，估值的输入空间从 $2^{M}$ 减少到 $M$，其中 $M$ 是物品数量。

|  | $\mathcal{C}_{\rho}(w;\lambda)=-\frac{1}{L}\sum_{l=1}^{L}\sum_{i\in N}p_{i}^{w}(v^{(l)})+\mathcal{L}_{rgt}+\mathcal{L}_{unf}$ |  | (15) |
| --- | --- | --- | --- |

Kuo 等人遵循了 RegretNet 的核心思想：在贝叶斯拍卖设置中，人们知道可以从中抽取样本的估值分布。同时，由于分配和支付规则都是函数，我们可以使用神经网络对其进行参数化。可以通过添加约束来强制策略无关性，这些约束可以通过增强拉格朗日优化器解决。

它采用了与 RegretNet 相同的神经网络架构，但在损失函数中增加了不公平性的约束 15，以减少不同人群之间的歧视性广告分配。遗憾项 $\mathcal{L}_{rgt}$ 与 RegretNet 中的定义一致。项 $\mathcal{L}_{unf}$ 用于量化拍卖系统中的不公平性和歧视，这将在第 6.4 节中详细描述。

## 4 强化学习 (RL) 基础设施

由于在线拍卖通常是一个动态系统，其用户和平台目标随着时间的推移而不断变化，研究人员更倾向于使用动态训练的模型来适应当前的现状，利用强化学习基础设施 [6, 27, 31]。

与 RegretNet 基础设施一样，Cai 等人也采用了无悔学习，在这种情况下，代理人只需要考虑自己的策略及其与环境的互动，而不必了解竞争者的价值或计算长期轮次中的收益最大化策略。考虑其他方策略通常需要强大的认知假设和高昂的计算能力，而大多数代理人无法获得这些。

基于著名的多臂老虎机算法，Cai 等人识别出了卖家的四种可能策略。

1.  1.

    $\epsilon-$Greedy [29]: 以概率 $\epsilon$，每个卖家随机均匀选择一个策略。以概率 $1-\epsilon$，选择具有最佳观察到的经验均值收益的策略。

1.  2.

    $\epsilon-$First: 在 $\mathcal{T}$ 轮的视野中，卖家在前 $\epsilon\cdot\mathcal{T}$ 轮中均匀随机选择策略，然后选择最大化观察到的奖励经验均值的策略用于所有后续轮次。

1.  3.

    指数加权算法用于探索和利用（Exp3）[2, 4]: 简而言之，Exp3 根据加权分布选择价格，然后根据收益调整权重。更具体地说，假设有 $K+1$ 个可能的价格，轮次 $t$ 中这些价格的概率分布 $\pi_{i}(t)$ 在公式 16 中定义，其中 $w_{i}(t)$ 是轮次 $t$ 中 $i^{th}$ 价格的当前权重，$\gamma$ 是 $[0,1]$ 之间的实数。

    |  | $\pi_{i}(t)=(1-\gamma)\frac{w_{i}(t)}{\sum_{j=1}^{K+1}w_{j}(t)}+\gamma\frac{1}{K+1}$ |  | (16) |
    | --- | --- | --- | --- |

    根据上述分布选择价格 $p_{j}(t)$ 并计算其收益 $u_{j}(t)$，然后根据公式 17 更新 $j^{th}$ 价格的权重，而其他所有价格的权重保持不变。

    |  | $w_{j}(t+1)=w_{j}(t)e^{\gamma\frac{u_{j}(t)}{(K+1)\pi_{j}(t)}}$ |  | (17) |
    | --- | --- | --- | --- |

1.  4.

    上置信界算法（UCB1）[1, 3]: 在前 $K+1$ 轮中，从 $[0,\frac{1}{K},\dots,1]$ 中选择一个之前未使用的价格，然后在随后的轮次中选择具有最大加权值的价格。

    将所有价格的权重初始化为 0。在任何轮次 $t\in\{0,\dots.K\}$ 中，卖家选择一个价格 $p_{j}$ 使得 $p_{j}\in[0,\frac{1}{K},\dots,1]$，计算效用 $u_{j}(t)$，并将 $j^{th}$ 价格的权重更新为 $x_{j}(t)=\frac{x_{j}(t-1)+u_{j}(t)}{t}$，其余价格的权重保持不变。

    对于任何轮次 $t\geq K+1$，卖家根据公式选择价格 $p_{j}$。

    |  | $p_{j}(t)=argmax_{j\in\{0,\frac{1}{K},\dots,1\}}x_{j}(t)+\frac{\log_{2}t}{\sum_{\tau=1}^{t}1_{\{p_{j}\text{ 在轮次 }\tau\text{ 被选择}\}}}$ |  | (18) |
    | --- | --- | --- | --- |

$\epsilon-$First 和 $\epsilon-Greedy$ 在探索与利用之间有明显的区别，属于半均匀策略的范畴。Exp3 对奖励没有分布假设，广泛用于全信息设置，并在对抗性赌博反馈模型中有效 [4]。UCB1 对较少被选择的行为保持一定的乐观态度，并使用观察到的行为的经验均值来选择下一轮的行为。UCB1 最适用于奖励遵循某些未知分布的场景 [6]。

这些卖家模型可以模拟具有不同复杂程度或定价理念的卖家，并且与近期关于算法机制设计的文献一致，在建模复杂动态环境中的代理理性方面。

之前的研究人员已经提出了一些强化学习模型的变体。深度 Q 网络 (DQN) [18] 的缺点是它不能处理连续动作或高维动作空间，因为随机演员-评论家算法很难收敛。确定性策略梯度 (DPG) 算法 [26] 是为了训练具有参数向量的确定性策略。DPG 由评论家和演员组成。评论家近似动作价值函数，而演员则调整确定性策略的参数。然后提出了深度确定性策略梯度 (DDPG) [15]，因为 DPG 受到高时间相关性的严重影响，导致高方差。DDPG 在每个时间步将代理的经验存储在回放缓冲区中，并从中随机均匀抽取小批量进行学习，从而消除时间相关性。DDPG 还采用目标网络来对学习算法进行正则化，以较慢的速度更新参数。

然而，随着卖家数量的增加，动作空间的大小急剧膨胀，因此直接应用 DDPG 会导致不收敛。此外，DDPG 无法处理卖家集合上的变异性，因为该算法使用了一个两层的全连接网络，而每个卖家的位置发挥了重要作用 [6]。

Cai 等人提出了 IA(GRU) [6] 算法，旨在缓解 DDPG 的问题。它采用了 DDPG 的框架，通过维护一个子演员网络和一个子评论家网络来实现。在每一步训练中，如果利用一个背景网络通过根据某些指标对卖家进行排列变换，从而保持排列不变性。同时，它在卖家的历史记录上应用了递归神经网络 (RNN)。排列变换的输出和 RNN 在历史记录上的输出被整合在一起，作为子演员和子评论家网络的输入。

实际上，在线拍卖的参与者在信息和计算方面都受到限制，因此他们并不完全理性。此外，历史数据可能仅限于由仅少数参数集定义的机制生成的数据，因此我们对过去数据的探索不足。参与者和拍卖系统设计师受到多种复杂因素的影响，因此他们的决策随着时间变化。为了克服这些困难，Tang 等人将每个玩家建模为一个独立的局部马尔科夫决策过程[27]，其中局部状态编码了玩家迄今为止可以观察到的历史行动和结果的一部分。

Tang 等人使用 DDPG 基础设施处理连续动作空间，但它将原始神经网络分解为一组子网络，每个卖家一个，以处理大量状态。它依赖于卖家相互独立和多个卖家之间 Q 值可加的假设。它使用 LSTM 从过去的竞标数据和反馈中自适应地学习，以预测未来的竞标分布，而不明确建模每个广告主的竞标策略。为了优化设计师的马尔科夫决策过程，它将动作空间离散化，然后使用蒙特卡罗树搜索（MCTS）[23]来加速前瞻性搜索。实验和案例研究表明，Tang 等人提出的动态定价方案在大幅度超越所有静态方案。

动态在线拍卖系统中的另一个挑战是用户和设计师在决策时考虑的绩效指标种类，而大多数先进的拍卖机制只优化单一绩效指标，如收入或社会福利。Zhang 等人确定了一份性能指标列表[31]，用户、广告商和广告平台可以考虑这些指标。

1.  1.

    每千次展示的收入（RPM）：$RPM=\frac{\sum click\times PPC}{\sum impression}\times 1000$，其中 PPC 是赢得广告的付款。

1.  2.

    点击率（CTR）：$CTR=\frac{\sum click}{\sum impression}$。

1.  3.

    加入购物车率（ACR）：$ACR=\frac{\sum add-to-cart}{\sum impression}$。

1.  4.

    转化率（CVR）：$CVR=\frac{\sum order}{\sum impression}$。

1.  5.

    每千次展示的商品交易额（GPM）：$GPM=\frac{\sum merchandisevolume}{\sum impression}\times 1000$。

Zhang 等人提出了深度 GSP [31]，它可以优化多个性能指标，如公式 19，其中$b$是用户的竞标向量，$\mathcal{M}$是拍卖机制，$f_{j}$是第$j$个绩效指标函数，$w_{j}$是与第$j$个绩效指标相关的权重，可以由拍卖平台管理员不时调整。

|  | <math   alttext="\begin{split}\mathcal{M}=argmax_{\mathcal{M}}E_{b\sim\mathcal{D}}[\sum_{j=1}^{L}w_{j}\times f_{j}(b;\mathcal{M})]\\ \text{s.t. 游戏均衡约束，}\\

\text{平滑过渡约束}\end{split}" display="block"><semantics ><mtable displaystyle="true" rowspacing="0pt" ><mtr  ><mtd columnalign="right"  ><mrow ><mi >ℳ</mi><mo >=</mo><mrow ><mi  >a</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >r</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >g</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >m</mi><mo lspace="0em" rspace="0em"  >​</mo><mi >a</mi><mo lspace="0em" rspace="0em"  >​</mo><msub ><mi >x</mi><mi >ℳ</mi></msub><mo lspace="0em" rspace="0em" >​</mo><msub ><mi >E</mi><mrow ><mi >b</mi><mo >∼</mo><mi >𝒟</mi></mrow></msub><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false" >[</mo><mrow ><munderover ><mo lspace="0em" movablelimits="false" >∑</mo><mrow ><mi >j</mi><mo >=</mo><mn >1</mn></mrow><mi >L</mi></munderover><mrow ><mrow ><msub ><mi  >w</mi><mi >j</mi></msub><mo lspace="0.222em" rspace="0.222em"  >×</mo><msub ><mi >f</mi><mi >j</mi></msub></mrow><mo lspace="0em" rspace="0em"  >​</mo><mrow ><mo stretchy="false"  >(</mo><mi >b</mi><mo >;</mo><mi >ℳ</mi><mo stretchy="false"  >)</mo></mrow></mrow></mrow><mo stretchy="false"  >]</mo></mrow></mrow></mrow></mtd></mtr><mtr ><mtd columnalign="right"  ><mtext >s.t. 游戏均衡约束，</mtext></mtd></mtr><mtr  ><mtd columnalign="right"  ><mtext >平滑过渡约束</mtext></mtd></mtr></mtable><annotation-xml encoding="MathML-Content" ><apply  ><ci >ℳ</ci><apply ><ci  >𝑎</ci><ci >𝑟</ci><ci >𝑔</ci><ci  >𝑚</ci><ci >𝑎</ci><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑥</ci><ci  >ℳ</ci></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝐸</ci><apply ><csymbol cd="latexml"  >similar-to</csymbol><ci >𝑏</ci><ci >𝒟</ci></apply></apply><apply ><csymbol cd="latexml" >delimited-[]</csymbol><apply ><apply ><csymbol cd="ambiguous" >superscript</csymbol><apply ><csymbol cd="ambiguous" >subscript</csymbol><apply ><ci >𝑗</ci><cn type="integer" >1</cn></apply></apply><ci >𝐿</ci></apply><apply ><apply  ><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑤</ci><ci >𝑗</ci></apply><apply ><csymbol cd="ambiguous" >subscript</csymbol><ci >𝑓</ci><ci >𝑗</ci></apply></apply><list ><ci >𝑏</ci><ci >ℳ</ci></list></apply></apply></apply><ci ><mtext  >s.t. 游戏均衡约束，</mtext></ci><ci ><mtext  >平滑过渡约束</mtext></ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" >\begin{split}\mathcal{M}=argmax_{\mathcal{M}}E_{b\sim\mathcal{D}}[\sum_{j=1}^{L}w_{j}\times f_{j}(b;\mathcal{M})]\\ \text{s.t. 游戏均衡约束，}\\ \text{平滑过渡约束}\end{split}</annotation></semantics></math> |  | (19) |

深度 GSP 拍卖建立在经典的广义第二价格拍卖的基础上。它将项目的特征（例如类别、历史点击率）、用户资料（例如性别、年龄、收入）以及用户偏好（例如预算、市场需求）作为输入，送入深度神经网络，该网络将这些特征与竞标结合成一个输入向量 $x_{i}$，并将其映射到一个排名得分 $r_{i}=R_{\theta}(b_{i};x_{i})$，其中 $R_{\theta}(b_{i};x_{i})$ 是映射函数。然后，投标者根据其排名得分按非递增顺序排序，前 K 名投标者将赢得拍卖。获胜投标者的支付基于下一个最高投标者的投标。

映射函数 $R_{\theta}(b_{i};x_{i})$ 需要对投标 $b_{i}$ 保持单调性，以满足博弈均衡约束。一些早期研究通过设计特定的神经网络架构来强制单调性，但这增加了训练过程的计算复杂度。因此，张等人通过在损失函数中引入逐点单调性惩罚项（方程 20 基础设施 ‣ 使用深度学习方法的在线拍卖机制设计调查")）来直接纳入单调性约束，其中 $\pi_{\theta}(b_{i};x_{i})$ 是一个非线性函数，并通过深度神经网络参数化。

|  | $\begin{split}\mathcal{L}_{mono}=&amp;\sum_{i=1}^{N}\max(0,-\triangledown_{b}R_{\theta}(b_{i};x_{i}))\\ =&amp;\sum_{i=1}^{N}\max(0,-(\pi_{\theta}(b_{i};x_{i})+b_{i}\triangledown_{b}\pi_{\theta}(b_{i};x_{i})))\end{split}$ |  | (20) |
| --- | --- | --- | --- |

平滑过渡约束在方程 21 基础设施 ‣ 使用深度学习方法的在线拍卖机制设计调查")中施加，这确保了当拍卖机制切换到另一个目标时，广告主的效用不会波动太大。

|  | $u_{i}(\mathcal{M})\geq(1-\epsilon)\times\bar{u}_{i}(\mathcal{M}_{0})$ |  | (21) |
| --- | --- | --- | --- |

## 5 深度集基础设施

大多数深度神经网络对每个输入的位置有隐含约束，而实际上拍卖中的物品并没有固有的排序。蔡等人通过根据一些指标对卖家进行排序来使用排列变换来缓解位置效应。刘等人进一步通过完全消除排序效应迈出了步伐。他们引入了基于 DeepSets [30] 架构的深度神经拍卖（DNA） [16]。

DNA 的集合编码器由两组层 $\phi_{1}$ 和 $\phi_{2}$ 组成。每个实例 $x_{i}$ 首先通过共享的全连接层 $\phi_{1}$ 映射到高维潜在空间，然后通过指数线性单元（ELU） [7] 激活函数 $\sigma$ 处理。接着，通过对称聚合池化（例如 avgpool）处理，以另一全连接层 $\phi_{2}$ 为每个广告 $i$ 构建最终的集合嵌入 $h_{i}^{\prime}$。整个过程在方程 22 中描述，其中 $h_{-i}$ 表示除 $i$ 外所有竞标者的隐藏状态。

|  | $\begin{split}h_{i}=\sigma(\phi_{1}(x_{i}))\\ h_{i}^{\prime}=\sigma(\phi_{2}(\text{avgpool}(h_{-i})))\end{split}$ |  | (22) |
| --- | --- | --- | --- |

DNA 使用上下文感知的排名分数，利用相对于投标的严格单调神经网络，并在给定下一个最高排名分数时支持高效的逆变换。排名分数可以使用方程 23 获得，价格可以使用方程 24 获得，其中 $w_{qz}$、$w_{qz}^{\prime}$ 和 $\alpha_{qz}$ 是神经网络的权重。

|  | $r_{i}=\min_{q\in[Q]}\max_{z\in[Z]}(e^{w_{qz}}\times b_{i}+w_{qz}^{\prime}\times x_{i}^{\prime}+\alpha_{qz})$ |  | (23) |
| --- | --- | --- | --- |
|  | $p_{i}=\max_{z\in[Z]}\min_{q\in[Q]}e^{-W_{qz}}(r_{i+1}-\alpha_{qz}-w_{qz}^{\prime}\times x_{i}^{\prime})$ |  | (24) |

由方程 23 表示的部分单调 MIN-MAX 神经网络已经被证明能够近似任何函数 [8]。

|  | $\hat{M}_{r}[k,:]=\text{softmax}(\frac{(N+1-2k)r-A_{r}\mathbbm{1}}{\tau})$ |  | (25) |
| --- | --- | --- | --- |

DNA 还在神经网络框架内建模了整个分配和支付过程，因为将分配和支付视为一个不可知环境可能会限制深度学习的结果。其中一个挑战是，分配和支付都建立在一个基本的排序操作上，而这个操作是不可微分的。Liu 等人通过提出一个适用于多插槽拍卖中前 K 名选择的可微分排序引擎——Neural-Sort [12] 来克服这个问题。

在方程 25 中，$\hat{M}_{r}[k,:]$ 的直观解释是获取第 $k^{th}$ 高物品的所有元素上的选择概率。其中 $A_{r}[i,j]=|r_{i}-r_{j}|$，$\mathbbm{1}$ 表示全为一的列向量。因此，顶级支付可以通过方程 26 中的简单矩阵乘法来恢复。

|  | $f_{pay}=\hat{M}_{r}[1:K,:]\cdot[p_{1},p_{2},\dots,p_{N}]^{T}$ |  | (26) |
| --- | --- | --- | --- |

## 6 约束和关注点

在线拍卖系统是一个复杂的游戏系统，涉及竞标者、卖家和拍卖系统管理员。仅考虑一个方的收入或社会福利通常是次优的。据我们了解，我们已经识别出在设计拍卖系统时管理员面临的四大类约束和关注点：IC & IR、数据稀疏性与高维性、多种性能指标和目标，以及公平性与防欺诈。我们将在下面说明这些约束的重要性，然后总结当前研究人员如何应对这些问题。

### 6.1 激励兼容性 (IC) 和个人理性 (IR)

拍卖平台设计者通常更关注于最大化长期目标 [27]。因此，建立一个能够适应动态和复杂环境的可靠系统对成功至关重要。

IC 性质确保所有代理通过真实报告其价值来获得最佳结果。拍卖参与者可能来自不同的背景，因此信息、认知和计算约束会在不同程度上限制他们的理性。如果无法满足 IC，系统的稳定性和可靠性将更难维持，因为设计者和代理必须考虑所有其他代理的潜在策略行为。一些研究人员通过采用理论框架来实现 IC，例如 DNA 的 GSP [16] 和 MenuNet [24] 的税收原则 [28]。其他研究人员 [9, 10, 11, 14, 21] 通过将事后遗憾 [9] 强制为零来实现 IC。

IR 性质也很重要，因为它确保所有代理都能获得非负的收益。可以通过基于 Myerson 系统的理论结果来确保 IR [20]。也可以通过将额外约束集成到目标函数中并使用增强拉格朗日求解器 [9, 10] 来强制执行。

### 6.2 数据稀疏性与高维性

随着代理数量的增加，动作空间可能迅速膨胀。动作空间中的高维度可能会引入严重的计算负担。为了减轻计算负担，唐等人和蔡等人将神经网络分解为每个卖家的子网络，并对动作空间进行离散化 [27, 6]。

此外，许多特征是高维的独热编码向量，因此数据可能非常稀疏。原始正则化方法会将整个向量纳入计算，并且正则化向量在大多数位置上都有非零条目，这会大幅增加稀疏数据的计算时间。周等人提出了一种小批量感知的正则化 [32] 方法，其中只有出现在小批量中的特征参数参与正则化的计算。

|  | $w_{j}\leftarrow w_{j}-\eta[\frac{1}{\lvert\mathcal{B}_{m}\rvert}\sum_{(x,y)\in\mathcal{B}_{m}}\frac{\partial L(p(x),y)}{\partial w_{j}}+\lambda\frac{\max_{(x,y)\in\mathcal{B}_{m}}1_{x_{j}\neq 0}}{n_{j}}w_{j}]$ |  | (27) |
| --- | --- | --- | --- |

小批量感知的正则化如方程 27 中所示，其中 $\eta$ 是学习率，$\mathcal{B}_{m}$ 是第 $m$ 批次，$w_{j}$ 是第 $j$ 特征的权重，$n_{j}$ 是第 $j$ 特征的出现次数。分子 $\max_{(x,y)\in\mathcal{B}_{m}}1_{x_{j}\neq 0}$ 表示第 $m$ 批次中是否至少有一个实例具有特征 $j$。

### 6.3 多重性能指标与目标

对于大多数拍卖设计师来说，最直观的目标是最大化他们的利润。然而，为了适应现代在线拍卖系统的动态和复杂性质，设计师们可能需要考虑多个性能指标。张等人列出了几个常用的性能指标（见 4 基础设施 ‣ 深度学习方法在线拍卖机制设计调查")）。张等人和刘等人优化了这些指标的线性组合，其中线性权重和这些指标的函数都由拍卖设计师指定 [31, 16]。随着时间的推移，如果目标发生变化，设计师可以自由调整权重和函数。

### 6.4 公平性与防欺诈

由于训练数据中的偏差，许多在线平台在不同人群中的广告分配存在歧视 [14]。与在线广告相关的一个主要社会问题是在就业市场上的使用，其中不公平性可能对平等和保护弱势群体造成严重损害。

为了减轻不公平性，PreferenceNet [21] 将三种公平性定义集成到模型中，这些定义将分配 $g(b)$ 映射到 $\mathbb{R}$。在所有这些方程（方程 28、方程 29 和方程 30）中，$i$ 指代第 $i$ 项，而 $j$ 和 $j^{\prime}$ 分别指代第 $j$ 个和第 $j^{\prime}$ 个代理。

1.  1.

    总变差公平性（方程 28）：分配之间的距离不能大于这两个用户之间的差异。

    |  | $\sum_{i\in C_{k}}&#124;g(b)_{i,j}-g(b)_{i,j^{\prime}}&#124;\leq d^{k}(j,j^{\prime}),\forall k\in\{1,\dots,c\},\forall j,j^{\prime}\in M$ |  | (28) |
    | --- | --- | --- | --- |

1.  2.

    熵（方程 29）：一个代理的分配趋向于更均匀分布。

    |  | $\max-\sum_{i=1}^{n}P(\frac{g(b)_{i.}}{\sum_{j}g(b)_{ij}})\log P(\frac{g(b)_{i.}}{\sum_{j}g(b)_{ij}})$ |  | (29) |
    | --- | --- | --- | --- |

1.  3.

    配额（方程 30）：对任何代理的最小分配应大于某个阈值。

    |  | $\min_{j}(\frac{g(b)_{.j}}{\sum_{i}g(b)_{ij}})>t$ |  | (30) |
    | --- | --- | --- | --- |

ProportionNet [14] 也采用了总变差公平性的概念，以确保对相似用户的分配差异不会过大。它将方程 28 转化为一个不公平性约束（方程 31），可以输入到扩展拉格朗日求解器中，从而使我们能够量化所有相关用户的拍卖结果不公平性。

|  | $unf_{j}=\sum_{j^{\prime}\in M}\sum_{C_{k}\in C}\max(0,\sum_{i\in C_{k}}\max(0,z_{ij}-z_{ij^{\prime}}))-d^{k}(j,j^{\prime}))$ |  | (31) |
| --- | --- | --- | --- |

虽然拍卖机制中的偏见可能引入不公平，但拍卖中的虚假竞标行为也会导致不公平。卖家可以采用各种虚假竞标策略来抬高物品的最终售价。已经确定了常见的四种虚假竞标策略[22]：

1.  1.

    评估者：在早期时间以高额出价进行单次竞标。

1.  2.

    冲刺：在最后时刻进行单次竞标，不留下任何其他人超出出价的机会。

1.  3.

    揭示：在短时间内进行多次竞标，意图暴露最大出价或最高竞标者的概率。

1.  4.

    怀疑者：每次以最低可能的出价进行多次竞标。

## 7 结论

在本文中，我们回顾了基于深度学习的在线拍卖系统的粗略演变过程。使用 MLP 基础设施设计的机制通常建立在一些理论结果之上，MLP 结构用于表示理论中给出的函数。随着 RegretNet 的出现，出现了更复杂的结构，该结构使用独立的网络对分配规则和支付规则进行参数化。许多研究人员通过将更多约束集成到目标函数中或稍微调整网络结构来构建 RegretNet 的扩展，但仍保持分配和支付网络的分离。在线拍卖的动态特性促使研究人员采用深度强化学习框架，这通常是一种模型无关的方法，要求对数据的假设较少，并能够随着时间的推移不断适应。由于大多数传统神经网络对输入的位置有隐含约束，它将拍卖参与者的排序集成到模型训练中，而实际上它们之间没有固有的排序。因此，基于 DeepSet 基础设施的深度学习应运而生，这可以完全消除位置的影响。我们还讨论了拍卖设计师面临的约束和问题，并指出了研究人员如何尝试解决这些问题。

尽管研究人员在开发一种在长期内可靠且有利可图的在线拍卖机制方面进展迅速，但仍有许多未解决的问题留待未来的研究者调查。由于在线拍卖系统的用户规模通常非常庞大，高维数据的计算约束和收敛问题仍然是不可忽视的问题。研究人员要么将数据映射到较低维度，要么通过离散化减少动作空间，但我们究竟损失了多少信息仍不清楚。此外，大多数模型假设单位需求和加性估值，而这一假设在现实世界中可能并不成立。最后但同样重要的是，由于大多数机制框架依赖于拍卖参与者彼此独立的假设，它们的 IC 和 IR 约束也在个体层面进行计算。因此，它们的策略可能对参与者之间的勾结行为不够稳健。

## 参考文献

+   [1] 拉吉夫·阿格拉瓦尔。《基于样本均值的多臂老虎机问题的 o(log n)遗憾指数策略》。应用概率学进展，27(4):1054–1078，1995 年。

+   [2] P·奥尔，N·切萨-比安奇，Y·弗伦德，和 R·E·沙皮雷。《在一个被操控的赌场里赌博：对抗性多臂老虎机问题》。在 IEEE 第 36 届年度计算机科学基础会议论文集中，322–331 页，1995 年。

+   [3] 彼得·奥尔，尼科洛·切萨-比安奇，和保罗·费舍尔。《多臂老虎机问题的有限时间分析》。机器学习，47(2–3):235–256，2002 年。

+   [4] 彼得·奥尔，尼科洛·切萨-比安奇，约阿夫·弗伦德，和罗伯特·E·沙皮雷。《非随机多臂老虎机问题》。SIAM 计算杂志，32(1):48–77，2003 年 1 月。

+   [5] 劳伦斯·M·奥苏贝尔和保罗·米尔格罗姆。《可爱但孤独的维克雷拍卖》。在《组合拍卖》，第一章，17–40 页。麻省理工学院出版社，2006 年。

+   [6] 蔡青鹏，阿里斯·费洛斯-拉西卡斯，唐平中，和张艺伟。《电子商务的强化机制设计》，2018 年。

+   [7] 乔克-阿尔内·克莱维特，托马斯·乌特特纳，和塞普·霍赫赖特。《通过指数线性单元（elus）进行快速准确的深度网络学习》，2016 年。

+   [8] 亨尼·丹尼尔斯和玛丽娜·维利科娃。《单调和部分单调神经网络》。IEEE 神经网络学报，21(6):906–917，2010 年。

+   [9] 保罗·杜廷，冯哲，哈里克里希纳·纳拉西曼，大卫·C·帕克斯，和赛·斯里瓦萨·拉文德拉纳斯。《通过深度学习实现最优拍卖》，2020 年。

+   [10] 冯哲，哈里克里希纳·纳拉西曼，和大卫·C·帕克斯。《用于预算的收益最优拍卖的深度学习》。在第 17 届国际自主代理和多代理系统会议论文集中，AAMAS ’18，第 354–362 页，南卡罗来纳州里士满，2018 年。国际自主代理和多代理系统基金会。

+   [11] Noah Golowich, Harikrishna Narasimhan 和 David C. Parkes. 多设施位置机制设计的深度学习。发表于第二十七届国际人工智能联合会议论文集，IJCAI-18，页面 261–267。国际人工智能联合会议组织，2018 年 7 月。

+   [12] Aditya Grover, Eric Wang, Aaron Zweig 和 Stefano Ermon. 通过连续松弛的排序网络的随机优化，2019 年。

+   [13] Kaiming He, Xiangyu Zhang, Shaoqing Ren 和 Jian Sun. 深入研究整流器：在 Imagenet 分类上超越人类水平的表现。发表于 2015 年 IEEE 国际计算机视觉会议（ICCV），页面 1026–1034，2015 年。

+   [14] Kevin Kuo, Anthony Ostuni, Elizabeth Horishny, Michael J. Curry, Samuel Dooley, Ping Yeh Chiang, Tom Goldstein 和 John P. Dickerson. Proportionnet: 在拍卖设计中平衡公平性和收益，利用深度学习，2020 年。

+   [15] Timothy P. Lillicrap, Jonathan J. Hunt, Alexander Pritzel, Nicolas Heess, Tom Erez, Yuval Tassa, David Silver 和 Daan Wierstra. 深度强化学习的连续控制，2019 年。

+   [16] Xiangyu Liu, Chuan Yu, Zhilin Zhang, Zhenzhe Zheng, Yu Rong, Hongtao Lv, Da Huo, Yiqing Wang, Dagui Chen, Jian Xu, Fan Wu, Guihai Chen 和 Xiaoqiang Zhu. 神经拍卖：电子商务广告的端到端拍卖机制学习，2021 年。

+   [17] Nguyen Cong Luong, Zehui Xiong, Ping Wang 和 Dusit Niyato. 针对移动区块链网络中的边缘计算资源管理的最优拍卖：一种深度学习方法，2017 年。

+   [18] Volodymyr Mnih, Koray Kavukcuoglu, David Silver, Andrei A. Rusu, Joel Veness, Marc G. Bellemare, Alex Graves, Martin Riedmiller, Andreas K. Fidjeland, Georg Ostrovski, Stig Petersen, Charles Beattie, Amir Sadik, Ioannis Antonoglou, Helen King, Dharshan Kumaran, Daan Wierstra, Shane Legg 和 Demis Hassabis. 通过深度强化学习实现人类水平的控制。自然，518(7540):529–533，2015 年 2 月。

+   [19] H. Moulin. 关于策略无关性和单峰性的研究。公共选择，35(4):437–455，1980 年。

+   [20] Roger B. Myerson. 最优拍卖设计。运筹学数学，6(1):58–73，1981 年。

+   [21] Neehar Peri, Michael J. Curry, Samuel Dooley 和 John P. Dickerson. Preferencenet: 用深度学习在拍卖设计中编码人类偏好，2021 年。

+   [22] Saurabh R. Sangwan 和 Anshika Arora. 基于监督学习的买家竞标行为检测在线拍卖。社会科学研究网络，2019 年。

+   [23] Weiran Shen, Binghui Peng, Hanpeng Liu, Michael Zhang, Ruohan Qian, Yan Hong, Zhi Guo, Zongyao Ding, Pengjun Lu 和 Pingzhong Tang. 强化机制设计及其在赞助搜索拍卖中的动态定价应用，2017 年。

+   [24] Weiran Shen, Pingzhong Tang 和 Song Zuo. 通过神经网络实现自动化机制设计，2021 年。

+   [25] MyungJae Shin, Joongheon Kim, 和 Marco Levorato. 基于拍卖的充电调度与深度学习框架用于多无人机网络。IEEE 车辆技术学报, 68(5):4235–4248, 2019。

+   [26] David Silver, Guy Lever, Nicolas Heess, Thomas Degris, Daan Wierstra, 和 Martin Riedmiller. 确定性策略梯度算法。见于第 31 届国际机器学习大会论文集 - 第 32 卷，ICML’14，第 I–387–I–395 页。JMLR.org, 2014。

+   [27] Pingzhong Tang. 强化机制设计。见于第 26 届国际人工智能联合会议论文集，IJCAI-17，第 5146–5150 页，2017 年。

+   [28] Rakesh Vohra. 机制设计：线性规划方法。《机制设计：线性规划方法》，2010 年 1 月。

+   [29] Christopher John Cornish Hellaby Watkins. 从延迟奖励中学习。博士论文，剑桥大学国王学院，英国，1989 年 5 月。

+   [30] Manzil Zaheer, Satwik Kottur, Siamak Ravanbakhsh, Barnabás Póczos, Ruslan Salakhutdinov, 和 Alexander J. Smola. 深度集合。CoRR, abs/1703.06114, 2017。

+   [31] Zhilin Zhang, Xiangyu Liu, Zhenzhe Zheng, Chenrui Zhang, Miao Xu, Junwei Pan, Chuan Yu, Fan Wu, Jian Xu, 和 Kun Gai. 使用深度 GSP 拍卖优化多种性能指标用于电子商务广告, 2021。

+   [32] Guorui Zhou, Chengru Song, Xiaoqiang Zhu, Ying Fan, Han Zhu, Xiao Ma, Yanghui Yan, Junqi Jin, Han Li, 和 Kun Gai. 点击率预测的深度兴趣网络, 2018。
