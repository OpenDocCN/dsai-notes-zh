<!--yml

category: 未分类

date: 2024-09-03 17:28:22

-->

# LLM 推理服务：最近的进展和机会调查

> 来源: [`arxiv.org/html/2407.12391`](https://arxiv.org/html/2407.12391)

1.  [I 简介](https://arxiv.org/html/2407.12391v1#S1 "在 LLM 推理服务：最近的进展和机会调查")

1.  [II 背景](https://arxiv.org/html/2407.12391v1#S2 "在 LLM 推理服务：最近的进展和机会调查")

    1.  [II-A 基于 Transformer 的 LLM 架构概述](https://arxiv.org/html/2407.12391v1#S2.SS1 "在 II 背景 ‣ LLM 推理服务：最近的进展和机会调查")

    1.  [II-B LLM 推理概览](https://arxiv.org/html/2407.12391v1#S2.SS2 "在 II 背景 ‣ LLM 推理服务：最近的进展和机会调查")

1.  [III 存储管理和缓存](https://arxiv.org/html/2407.12391v1#S3 "在 LLM 推理服务：最近的进展和机会调查")

    1.  [III-A 有效管理 KV 缓存](https://arxiv.org/html/2407.12391v1#S3.SS1 "在 III 存储管理和缓存 ‣ LLM 推理服务：最近的进展和机会调查")

    1.  [III-B 长上下文应用的支持](https://arxiv.org/html/2407.12391v1#S3.SS2 "在 III 存储管理和缓存 ‣ LLM 推理服务：最近的进展和机会调查")

    1.  [III-C KV 缓存的压缩](https://arxiv.org/html/2407.12391v1#S3.SS3 "在 III 存储管理和缓存 ‣ LLM 推理服务：最近的进展和机会调查")

1.  [IV 计算任务调度](https://arxiv.org/html/2407.12391v1#S4 "在 LLM 推理服务：最近的进展和机会调查")

    1.  [IV-A 请求批处理](https://arxiv.org/html/2407.12391v1#S4.SS1 "在 IV 计算任务调度 ‣ LLM 推理服务：最近的进展和机会调查")

    1.  [IV-B 非集中式推理](https://arxiv.org/html/2407.12391v1#S4.SS2 "在 IV 计算任务调度 ‣ LLM 推理服务：最近的进展和机会调查")

    1.  [IV-C 模型并行性](https://arxiv.org/html/2407.12391v1#S4.SS3 "在 IV 计算任务调度 ‣ LLM 推理服务：最近的进展和机会调查")

1.  [V 云中的 LLM](https://arxiv.org/html/2407.12391v1#S5 "在 LLM 推理服务：最近的进展和机会调查")

    1.  [V-A 云部署成本](https://arxiv.org/html/2407.12391v1#S5.SS1 "在 V 云中的 LLM ‣ LLM 推理服务：最近的进展和机会调查")

    1.  [V-B 云效率](https://arxiv.org/html/2407.12391v1#S5.SS2 "在 V 云中的 LLM ‣ LLM 推理服务：最近的进展和机会调查")

1.  [VI 新兴研究领域](https://arxiv.org/html/2407.12391v1#S6 "在 LLM 推理服务：最近的进展和机会调查")

    1.  [VI-A 检索增强生成](https://arxiv.org/html/2407.12391v1#S6.SS1 "在 VI 新兴研究领域 ‣ LLM 推理服务：最近的进展和机会调查")

    1.  [VI-B 专家混合推理](https://arxiv.org/html/2407.12391v1#S6.SS2 "在 VI 新兴研究领域 ‣ LLM 推理服务：近期进展和机会的调查")

    1.  [VI-C 杂项领域](https://arxiv.org/html/2407.12391v1#S6.SS3 "在 VI 新兴研究领域 ‣ LLM 推理服务：近期进展和机会的调查")

1.  [VII 结论](https://arxiv.org/html/2407.12391v1#S7 "在 LLM 推理服务中：近期进展和机会的调查")

\pdfcolInitStack

tcb@breakable

# LLM 推理服务：近期进展和机会的调查

李宝林 1, 姜彦凯 1, 维贾伊·戈德帕利 2, 德维什·蒂瓦里 1

1 东北大学，2 麻省理工学院

###### 摘要

本调查提供了对大型语言模型（LLM）服务系统近期进展的全面概述，重点关注自 2023 年以来的研究。我们特别审查了系统级的改进，这些改进在不改变核心 LLM 解码机制的情况下提高了性能和效率。通过选择和审查来自权威机器学习和系统领域的高质量论文，我们突出了关键创新和在实际生产环境中部署和扩展 LLM 的实际考虑因素。本调查为希望跟上这一快速发展的领域的 LLM 从业者提供了宝贵的资源。

## I 引言

自从 ChatGPT 发布以来，大型语言模型（LLM）迅速获得了巨大的流行。然而，在生产环境中部署和扩展这些强大的 AI 模型带来了重大挑战。LLM 的计算和内存需求通常需要使用高性能 GPU 服务器，但即使这些资源也可能因模型的庞大规模和处理的长文本序列而面临压力。

对 LLM 驱动的应用需求的不断增长促进了对 LLM 服务系统的研究激增。本文呈现了这些系统的综合调查，重点关注自 2023 年以来的进展。虽然之前已经存在 LLM 系统研究，但在过去一年中，研究格局发生了戏剧性变化。几乎每个主要系统会议现在都有专门的 LLM 会议，特别强调服务系统，因为它们的广泛部署和低延迟性能对用户体验至关重要。

在如此短的时间内发布的研究数量庞大，使得 LLM 从业者很难跟上最新发展并识别出最有前景的实际部署方法。本调查旨在提供当前最先进技术的清晰概述，突出创新的关键领域和生产环境中的实际考虑因素。

在本调查中，我们精心选择了所有专注于 LLM 服务系统的高质量研究论文，这些论文发表于 2023 年 1 月至 2024 年 6 月之间。我们的选择标准优先考虑了来自权威机器学习（ML）和系统会议（如 ASPLOS、MLSys、OSDI）的出版物，以及来自知名行业和学术研究团队的有影响力的 arXiv 投稿。值得注意的是，我们排除了那些修改 LLM 解码算法的研究（如多解码头[[1](https://arxiv.org/html/2407.12391v1#bib.bib1)]，前瞻解码[[2](https://arxiv.org/html/2407.12391v1#bib.bib2)]，关键标记选择[[3](https://arxiv.org/html/2407.12391v1#bib.bib3)]），而专注于保持标准 LLM 解码过程完整性的系统级增强。

尽管已有一些关于 LLM 推理系统的调查[[4](https://arxiv.org/html/2407.12391v1#bib.bib4), [5](https://arxiv.org/html/2407.12391v1#bib.bib5), [6](https://arxiv.org/html/2407.12391v1#bib.bib6)]，这些调查通常涵盖的范围较广，未专门强调系统研究。此外，这些调查中讨论的许多论文涉及解码算法的修改，这可能会影响模型的准确性。与此不同，我们的调查明确聚焦于不改变核心 LLM 解码机制的系统级解决方案。此外，我们的调查还包括了这些早期调查发布之后的大量研究，从而提供了对该领域更全面和最新的概述。

我们将 LLM 服务系统的最新进展组织成四个不同的类别，每个类别都有其自身的挑战和机遇，我们将在接下来的章节中详细探讨。

KV 缓存和内存管理。高效的内存管理对于处理 KV 缓存的动态增长至关重要，这些缓存存储之前的键值对，以加速 LLM 推理。近期的研究探索了非连续内存分配、分布式管理和智能缓存策略，以优化内存利用率。压缩技术也正在被研究，以减少整体内存占用，从而通过支持更长的上下文长度和更低的内存开销来提高 LLM 性能和可扩展性。

LLM 计算优化。优化 LLM 计算的工作重点是请求批处理，以最大化资源利用率。此外，将推理过程分解为预填充和解码阶段，使得可以独立优化和进行硬件专业化。模型并行性，采用各种技术，促进了多个 GPU 上的高效执行。这些策略共同提升了 LLM 执行效率和硬件利用率。

云端 LLM 部署。云平台提供了一个可扩展且具有成本效益的 LLM 推理基础。然而，在优化成本和资源利用方面仍然存在挑战。研究通过诸如临时实例管理、无服务器优化、智能资源分配和电源管理等技术来解决这些问题。此外，云任务共定位和令牌交付优化等策略提高了用户体验和整体云效率。

新兴研究领域。LLM 服务的新兴领域包括检索增强生成（RAG）和专家混合（MoE）推理。RAG 面临着由于检索到的文档导致的输入长度增加的计算开销问题，而 MoE 推理则在分布式专家之间的高效通信和负载均衡方面存在挑战。其他研究工作则解决了 LLM 服务中的伦理问题，如公平性和环境可持续性，我们提供了相关研究的综合列表。

## II 背景

### II-A 基于 Transformer 的 LLM 架构概述

主流 LLM 基于多个 Transformer 块 [[7](https://arxiv.org/html/2407.12391v1#bib.bib7)]。每个相同的 Transformer 主要由基于自注意力的 *多头注意力*（MHA）操作和 *前馈网络*（FFN）组成。最初，Transformer 对输入 $X$（输入文本序列的编码表示）应用三个权重矩阵（$W^{Q},W^{K},W^{V}$）来计算查询 $Q$、键 $K$ 和值 $V$。然后，*自注意力* 被计算为：

|  | $\displaystyle\begin{split}Q=XW^{Q};K=XW^{K};V=XW^{V}\\ \text{注意力}(Q,K,V)=\text{softmax}(\frac{QK^{T}}{\sqrt{d_{k}}})V\end{split}$ |  |
| --- | --- | --- |

这是一个注意力头（$H_{i}$）的计算，多个头会被拼接并线性投影到最终的注意力结果中：

|  | $\displaystyle\begin{split}H_{i}=\text{注意力}(XW^{Q}_{i},XW^{K}_{i},XW^{Q}_% {i})\\ \text{多头注意力}=\text{Concat}(H_{1},H_{2},...,H_{h})W^{O}\end{split}$ |  |
| --- | --- | --- |

MHA 使变压器在不同的表示空间中关注序列的不同部分。接下来，跟随 MHA 块，归一化的输出被送入一个位置-wise FFN，该 FFN 由两个带有 ReLU 激活的线性变换组成。

|  | $\displaystyle\begin{split}\text{FFN}(x)=\text{max}(0,xW_{1}+b_{1})W_{2}+b_{2}% \end{split}$ |  |
| --- | --- | --- |

FFN 可以分别应用于每个位置，进一步提炼 MHA 块捕获的信息。输出的维度与输入 $X$ 相同。图 [1](https://arxiv.org/html/2407.12391v1#S2.F1 "图 1 ‣ II-A 基于 Transformer 的 LLM 架构概述 ‣ II 背景 ‣ LLM 推理服务：近期进展与机会调查") 提供了 LLM 架构的可视化。

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：基于 Transformer 的 LLM 架构，包括多头注意力机制和前馈网络。

### II-B LLM 推理概述

LLM 推理根据初始输入序列$P$自回归地生成输出令牌[[8](https://arxiv.org/html/2407.12391v1#bib.bib8)]，这些输入序列称为*提示*。这个过程分为两个主要阶段：预填充阶段和解码阶段。预填充阶段对设置模型以高效生成文本至关重要，而解码阶段处理生成后续令牌的过程。我们在图[2](https://arxiv.org/html/2407.12391v1#S2.F2 "图 2 ‣ II-B LLM 推理概述 ‣ II 背景 ‣ LLM 推理服务：近期进展与机会调查")中可视化了这个过程。

预填充阶段以经过层次的 Transformer 的令牌化和编码表示的提示开始。请注意，在预填充阶段，所有 Transformer 块生成的键值（$KV$）对会被缓存，称为 KV 缓存[[9](https://arxiv.org/html/2407.12391v1#bib.bib9)]。这确保了模型可以更高效地生成令牌，而无需重新计算所有先前令牌的 KV 向量。设输入提示为$P=[p_{1},p_{2},...,p_{n}]$，在预填充阶段生成一个新令牌，记作$P_{n+1}$，并将新的$K$和$V$缓存为$[(k_{1},v_{1}),(k_{2},v_{2}),...,(k_{n},v_{n})]$。

解码阶段是模型自回归地生成新令牌的阶段。LLM 预测下一个令牌，将新生成的令牌$p_{n+1}$附加到原始提示$P$上，并更新 KV 缓存。请注意，KV 缓存随着生成的令牌数量线性增长。自回归 LLM 推理过程在算法[1](https://arxiv.org/html/2407.12391v1#alg1 "算法 1 ‣ II-B LLM 推理概述 ‣ II 背景 ‣ LLM 推理服务：近期进展与机会调查")中概述。

算法 1 自回归 LLM 推理

1:输入$P$：编码输入序列$[p_{1},p_{2},...,p_{n}]$ 2:输出$X$：生成的新序列$[]$。3:前向传播($[p_{1},p_{2},...,p_{n}]$) 4:存储 KV 缓存：$[(k_{1},v_{1}),(k_{2},v_{2}),...,(k_{n},v_{n})]$ 5:对$i$从 1 到 M 执行 6:预测下一个令牌$p_{n+i}$，使用 KV 缓存。 7:将$(k_{n+i},v_{n+i})$存储到 KV 缓存中。 8:$X\leftarrow X\cup\{p_{n+i}\}$ 9:如果$p_{n+i}$是 EOS 令牌或 len($X$)$>$最大长度，则 10:中断 ![参考标题](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2：LLM 推理中的预填充和解码阶段。

## III 内存管理和缓存

在这一部分，我们探讨了内存管理技术，以减轻在 LLM 推理过程中内存占用和访问开销。虽然模型参数保持不变，中间激活量相对较小，但用于存储注意力信息的 KV 缓存随着生成的令牌数量的增加而显著增长。因此，近期的研究集中在高效的 KV 缓存管理上，以支持更大的批处理大小和更长的上下文处理。

### III-A KV 缓存的高效管理

PagedAttention [[10](https://arxiv.org/html/2407.12391v1#bib.bib10)] 发现，KV 缓存会随着模型生成新令牌而动态增长和缩小，但请求生成的生命周期和长度事先未知。因此，它建议将 KV 缓存管理为不连续的内存块。与连续的 KV 缓存相比，不连续的 KV 缓存管理显著减少了预分配和碎片化的内存浪费。由于其使用页的高效内存管理，PagedAttention 已成为 LLM 服务框架中的行业标准，由 TGI [[11](https://arxiv.org/html/2407.12391v1#bib.bib11)]、vLLM [[10](https://arxiv.org/html/2407.12391v1#bib.bib10)] 和 TensorRT-LLM [[12](https://arxiv.org/html/2407.12391v1#bib.bib12)] 支持。

尽管取得了一定成功，研究人员仍然发现其缺点在于 PagedAttention 需要重写注意力内核以适应不连续的内存块，它的内存管理器增加了软件复杂性和冗余，并且引入了性能开销。最近，vAttention [[13](https://arxiv.org/html/2407.12391v1#bib.bib13)] 被提出以保留 KV 缓存于连续虚拟内存中。它利用现有的低级系统调用进行需求分页，这是一种标准的操作系统特性，可以减少软件复杂性。vAttention 将内存分配与计算重叠，提前预分配内存，并推迟内存回收，以隐藏内存分配的延迟并提高系统的整体性能。

除了系统内存管理，其他努力也针对应用特定的 KV 缓存效率展开。Prompt Cache [[14](https://arxiv.org/html/2407.12391v1#bib.bib14)] 为用户提交请求设计了特定的提示模式，以便这些预定义模块（例如，系统提示）的注意力状态可以在多个提示之间重复使用。AttentionStore [[15](https://arxiv.org/html/2407.12391v1#bib.bib15)] 发现，人类与 ChatGPT 等应用的互动大多是多轮对话。然而，当用户会话变得不活跃时，LLM 引擎会丢弃 KV 缓存，以释放 HBM 空间用于其他活跃会话，并在会话变为活跃时重新计算整个 KV 缓存，导致额外的预填充成本。AttentionStore 利用较慢的介质（例如，CPU 内存和磁盘），将 KV 缓存加载与计算重叠，并设计智能的预取和驱逐策略。

### III-B 长上下文应用程序的支持

服务长上下文 LLM 应用程序尤其具有挑战性，因为 KV 缓存的大小随着令牌数量的增加而增长。有限的内存限制了 LLM 处理长序列的能力，需要更高效的内存解决方案。环形注意力 [[16](https://arxiv.org/html/2407.12391v1#bib.bib16)] 是一种新颖的分布式方法，利用多设备间对长序列的块状计算注意力和前馈。它高效地将 KV 缓存通信与计算重叠，并通过设备数量扩展上下文长度。Infinite-LLM [[17](https://arxiv.org/html/2407.12391v1#bib.bib17)] 是另一种分布式解决方案，它将 KV 缓存分解为称为 rBlocks 的较小可管理单元，并通过动态内存共享和协调有效管理它们。MemServe [[18](https://arxiv.org/html/2407.12391v1#bib.bib18)] 通过引入 MemPool，统一处理 LLM 服务的请求间和请求内优化，MemPool 是一个分布式内存池，用于管理所有集群内存中的 KV 缓存，并采用全局调度器最大化 KV 缓存重用。

当上下文超过 GPU 内存限制时，大多数系统会将 KV 缓存卸载到 CPU。InfiniGen [[19](https://arxiv.org/html/2407.12391v1#bib.bib19)] 是一种解决方案，通过在前一层中复习当前层的注意力计算，推测重要的 KV 缓存条目，并仅将关键条目预取到 GPU，从而减少数据传输开销。LoongServe [[20](https://arxiv.org/html/2407.12391v1#bib.bib20)] 引入了一种新的并行范式称为弹性序列并行（ESP），以动态适应请求和请求阶段（预填充和解码）之间的资源使用变化。它减少了服务长序列时 KV 缓存迁移开销和 KV 缓存碎片化。

### III-C KV 缓存的压缩

由于 LLM 服务的巨大内存占用，一些系统采取了压缩 KV 缓存的方法。在内存聚合和通信调度之上，FlexGen [[21](https://arxiv.org/html/2407.12391v1#bib.bib21)] 使用细粒度分组量化将权重和 KV 缓存压缩到 4 位。KIVI [[22](https://arxiv.org/html/2407.12391v1#bib.bib22)] 分析 LLM KV 缓存的元素分布，并对 Key 和 Value 缓存应用了不对称量化。KIVI 按通道（在通道维度上分组元素）对 key 缓存进行量化，对 value 缓存进行逐令牌量化，以实现最小量化误差。Gear [[23](https://arxiv.org/html/2407.12391v1#bib.bib23)] 通过对大多数类似幅度的条目进行量化，接近无损高比 KV 缓存压缩，并采用低秩矩阵来近似量化误差。MiniCache [[24](https://arxiv.org/html/2407.12391v1#bib.bib24)] 观察到 KV 缓存状态在 LLM 的中到深层之间表现出高度相似性。基于这一见解，MiniCache 利用这种高相似性将其合并为共享表示，以减少冗余，同时识别并保留对保持模型性能至关重要的不同状态，防止在压缩过程中信息丢失。

## IV 计算任务调度

除了内存和 KV 缓存管理外，LLM 的计算还面临重大系统挑战。由于自回归生成过程中令牌之间的顺序依赖，LLM 每次请求只能生成一个令牌。因此，LLM 推理工作负载的资源效率低于为大规模并行执行设计的 GPU 硬件上的训练工作负载。基于这一动机，我们调查了在推理过程中优化计算任务调度的系统解决方案。

### IV-A 请求批处理

当单个请求无法高效利用 GPU 时，将多个推理请求批量处理以提升 GPU 核心的占用率是直观的。然而，由于对不同提示的响应长度可能差异很大，当批量处理时，较短的响应被迫等待较长的响应完成，导致计算浪费。响应长度感知和序列调度[[25](https://arxiv.org/html/2407.12391v1#bib.bib25)]指导 LLM 在开始生成实际响应之前预测响应长度，并将具有相似预测响应长度的查询进行批处理，以减少计算浪费。类似的方法，$S^{3}$ [[26](https://arxiv.org/html/2407.12391v1#bib.bib26)]，对 Distillbert 模型进行序列长度预测的微调。当预测错误时，它会预防超过分配内存的序列，并重新训练预测器以从错误中学习。

由于对预测器的强烈依赖，基于生成长度预测的批处理方法不够实用。Orca [[27](https://arxiv.org/html/2407.12391v1#bib.bib27)] 提出了在令牌级别而非请求级别进行连续批处理的方法。它在当前批次中的一个请求完成后，会立即将新的请求调度到批次中。连续批处理现在已成为 LLM 服务框架中的行业标准，被集成到 TGI、vLLM 和 TensorRT-LLM 的软件中。基于连续批处理，DeepSpeed-FastGen [[28](https://arxiv.org/html/2407.12391v1#bib.bib28)] 提出了动态 SplitFuse 机制，将长提示分解为多个小块，在多次迭代中调度，并将短提示组合在一起，以保持推理运行在高吞吐量区域（由 GPU 计算限制而非内存带宽限制）。类似的想法在 Sarathi-Serve [[29](https://arxiv.org/html/2407.12391v1#bib.bib29)] 中得到了探索，它将预填充请求拆分为更小的块，并与正在进行的解码请求一起调度而不会造成停顿（无停顿批处理）。这允许新的请求加入正在运行的批次，而无需暂停正在进行的解码，从而最小化管道气泡。

### IV-B 解耦推理

LLM 推理经历一个预填充阶段来处理提示、填充 KV 缓存，并开始解码阶段生成令牌（第 [II](https://arxiv.org/html/2407.12391v1#S2 "II Background ‣ LLM Inference Serving: Survey of Recent Advances and Opportunities")节）。现有的 LLM 服务系统将这两个阶段结合在一起，对所有用户和请求的预填充和解码计算进行批处理。然而，这两个阶段表现出不同的特征，当预填充阶段的请求与解码阶段的请求批处理在一起时，可能会相互干扰。TetriInfer [[30](https://arxiv.org/html/2407.12391v1#bib.bib30)] 将预填充和解码实例分开，允许每个阶段独立运行，防止批处理式的预填充任务和延迟敏感的解码任务之间的干扰。它采用了一种两级调度算法，结合了预测的资源使用情况，以避免在解码阶段调度热点，确保高效的资源分配并最小化争用。

Splitwise [[31](https://arxiv.org/html/2407.12391v1#bib.bib31)] 广泛描述了在不同代 GPU（异构硬件）上预填充和解码阶段的执行和利用模式的差异。Splitwise 提议将这两个阶段拆分到不同的机器上，从而为每个阶段提供专用硬件，以实现更好的利用，降低硬件拥有成本，并节省能源。DistServe [[32](https://arxiv.org/html/2407.12391v1#bib.bib32)] 设计了一种放置算法来调度预填充和解码阶段的计算任务。在高速度跨节点网络的集群中，DistServe 独立优化预填充和解码实例的并行配置，以实现最佳的每 GPU 吞吐量；在带宽有限的跨节点集群中，确保同一阶段的预填充和解码实例共置于单个节点内，并优化节点内的并行配置。

### IV-C 模型并行性

LLMs 可以拥有数百亿个参数，要求在多个 GPU 上进行模型并行执行。Pope 等人 [[9](https://arxiv.org/html/2407.12391v1#bib.bib9)] 开发了一种用于推理效率的分析模型，使得能够选择针对 TPU v4 切片的最佳多维分区技术，以满足特定应用需求。HeteGen [[33](https://arxiv.org/html/2407.12391v1#bib.bib33)] 引入了一个使用 CPU 和 GPU 的异构并行计算框架。它采用异构并行计算算法，在其混合异构并行框架内分配计算任务，并实现异步重叠，以缓解 CPU 和 GPU 之间的 I/O 瓶颈。

ExeGPT [[34](https://arxiv.org/html/2407.12391v1#bib.bib34)] 能够找到一个最优的批量大小和张量并行度的调度控制变量，以在遵循给定延迟限制的同时最大化推理吞吐量。它利用输入和输出序列长度的分布来有效分配资源，并确定最佳的并行配置。Helix [[35](https://arxiv.org/html/2407.12391v1#bib.bib35)] 旨在将 LLM 划分到异构 GPU 和不同类型的网络连接中。它将模型分区场景表述为有向加权图的最大流问题，其中节点代表 GPU 实例，边缘通过在最大流问题中的容量捕获 GPU 和网络的异质性。

## V 云中的 LLMs

LLM 部署计算密集且通常需要大量基础设施以有效运行。云平台提供了一种可扩展且具有成本效益的 LLM 部署解决方案，消除了对昂贵硬件投资的需求。云部署的灵活性使组织能够根据需要轻松调整资源，确保最佳性能并最小化停机时间。然而，与云计算资源相关的显著成本以及确保其高效利用的挑战可能是 LLM 服务提供商面临的主要障碍。

### V-A 云部署成本

现代云平台提供多种临时实例（例如，AWS EC2 Spot 实例、Azure Spot 虚拟机、Google Cloud Spot VM）。这些实例在闲置容量上运行，并以大幅折扣的价格提供，但当其他实例需要容量时，可能会被抢占。SpotServe [[36](https://arxiv.org/html/2407.12391v1#bib.bib36)] 解决了使用这些实例进行 LLM 服务的挑战，例如如何快速适应可用实例的变化以及如何在发生中断时最小化迁移实例的成本。它还引入了一个有状态的推理恢复机制，允许推理引擎在标记级别提交其进度并有效恢复中断的请求。

Serverless（无服务器）是一种新兴的云计算范式，用户可以将模型提交到云端，云服务提供商则负责所有基础设施的提供和根据不同的推理请求负载进行扩展，同时为客户节省未使用的硬件成本。无服务器的主要挑战之一是缓解冷启动问题，即服务实例在一段时间未被访问后会被关闭，一旦新请求到达，则会经历与重新初始化服务实例相关的延迟峰值。ServerlessLLM [[37](https://arxiv.org/html/2407.12391v1#bib.bib37)] 通过利用 GPU 服务器上未充分利用的存储和内存资源来解决这些延迟问题。它引入了一种新的检查点格式和加载系统，以加速 LLM 模型加载，引入了一个实时迁移机制以避免中断正在进行的推理，并采用了局部感知的服务器分配策略以最小化 LLM 推理的冷启动延迟。

云服务提供商通常提供各种异构实例选择，标记为不同的价格。Mélange [[38](https://arxiv.org/html/2407.12391v1#bib.bib38)] 是一个云资源分配框架，考虑了三个关键 LLM 服务特性：请求大小、请求率和服务级别目标。它自动在 GPU 选项空间中导航，以确定给定 LLM 服务的最具成本效益的异构 GPU 分配。资源分配和模型托管在 GPU 上后，Llumnix [[39](https://arxiv.org/html/2407.12391v1#bib.bib39)] 是一个动态调度系统，旨在通过在运行时跨多个模型实例重新调度异构和不可预测的请求来应对挑战——类似于操作系统在核心之间的上下文切换。Llumnix 引入了一种高效的请求及其内存状态的实时迁移机制，最小化了重新调度过程中的停机时间，并采用了一种动态调度策略，统一了负载均衡、碎片整理、优先级排序和自动扩展等各种重新调度场景。这种效率带来了显著的成本节约，同时实现了类似的尾延迟。

### V-B 云计算效率

云数据中心的一个关键瓶颈资源是电力，由于其不断增长的计算需求，大型语言模型（LLMs）正在迅速饱和。POLCA [[40](https://arxiv.org/html/2407.12391v1#bib.bib40)] 描述了云中 LLMs 的电力消耗模式，并发现虽然训练 LLMs 需要大量电力，可能会对数据中心的电力基础设施造成压力，但推理任务由于其不那么可预测的电力需求，提供了更多的电力管理灵活性。POLCA 设计了一个框架，通过动态应用如 GPU 频率锁定和电力限制等技术来管理 LLM 推理集群中的电力。PerLLM [[41](https://arxiv.org/html/2407.12391v1#bib.bib41)] 将 LLM 推理带入了边缘云协作场景中，在这里它利用了边缘计算（低延迟、减少能耗）和云计算（高处理能力）的优势来高效处理 LLM 推理任务。PerLLM 使用约束满足上置信界（CS-UCB）算法来优化服务调度和资源分配，同时遵守处理时间、带宽和计算能力等约束——实现能源上的 LLM 效率。

工作负载通常会在云环境中共存。FlexLLM [[42](https://arxiv.org/html/2407.12391v1#bib.bib42)] 是一个旨在高效服务 LLM 推理和参数高效微调（PEFT）请求的系统。LLM 推理，即逐词生成文本，主要受到内存带宽的限制，因为每次生成令牌时都需要访问所有模型参数。相反，PEFT 同时处理请求的所有令牌，主要受到计算资源的限制，例如 GPU 上的张量核心。FlexLLM 引入了一种令牌级别的微调机制，将微调过程分解为更小、更易管理的令牌级计算，以最小化内存使用和推理延迟，从而使共同服务成为可能。

由于 LLM 推理是逐词生成的，用户也逐字阅读响应。Andes [[43](https://arxiv.org/html/2407.12391v1#bib.bib43)] 定义了一种文本流服务的用户体验指标——体验质量（QoE）。该指标通过将请求的实际令牌交付时间线（TDT）与预期 TDT 进行比较来制定。预期 TDT 由预期首次令牌时间（TTFT）和预期令牌交付速度（TDS）决定，这些因素可能会根据用户的典型阅读速度有所不同。直观上，生成文本速度过快（超过用户阅读速度）不会带来 QoE 好处，反而浪费云资源。Andes 通过在多个请求之间战略性地分配 GPU 资源来解决这一问题，以优化 QoE。它采用了一种基于动态优先级的抢占调度器，该调度器在令牌级别运行，优先处理紧急请求并抢占那些已经得到充分服务的请求。Andes 提高了平均 QoE，并且能够在保持类似令牌生成吞吐量的情况下处理更高的请求速率。

## VI 新兴研究领域

### VI-A 检索增强生成

检索增强生成（RAG）[[44](https://arxiv.org/html/2407.12391v1#bib.bib44)] 是一种通过引入外部信息源来增强 LLM 的技术。它解决了 LLM 在保持事实知识方面的局限性以及生成不准确或虚构信息（幻觉）的倾向。RAG 分为两个阶段：检索和生成。在检索阶段，系统根据给定的查询从外部知识库或语料库中识别最相关的上下文。一旦相关上下文被检索到，它们就会在 LLM 的生成过程中与其他过程集成，包括拼接（将检索到的上下文直接附加到查询中）和交叉注意（LLM 在生成过程中关注检索到的上下文）。

稀疏 RAG [[45](https://arxiv.org/html/2407.12391v1#bib.bib45)]观察到，由于检索文档导致的输入长度增加，RAG 可能会计算开销较大。它首先并行编码检索到的文档，以消除由长程注意力引起的延迟，然后通过仅关注通过特殊控制令牌提示 LLM 选择的高度相关缓存来选择性地解码输出。RAGCache [[46](https://arxiv.org/html/2407.12391v1#bib.bib46)]使用知识树缓存外部知识的中间状态，以组织和存储中间状态。缓存的知识可以在多个查询中共享，以减少冗余计算。另一种知识缓存技术是 CacheBlend [[47](https://arxiv.org/html/2407.12391v1#bib.bib47)]，它根据输入中的前文选择性地重新计算 KV 缓存的一小部分。

### VI-B 专家混合推理

专家混合（MoE）被用于大语言模型（LLMs）中，以提高效率和性能。它将模型分成专门的子网络，称为“专家”，每个专家专注于特定的任务。一个“门控”网络然后将输入引导到最合适的专家。在 MoE 变换器的推理过程中，输入首先通过一个门控网络。这个网络决定哪个专家，或一组专家，最适合处理特定的输入。MoE 的稀疏激活专家子集避免了每次推理都需要处理整个模型的大量计算需求。

MoE 通信。Lina [[48](https://arxiv.org/html/2407.12391v1#bib.bib48)]是一个旨在解决分布式 MoE 中全对全通信瓶颈的系统。全对全通信发生在分布式 MoE 将令牌发送到其选定的专家进行处理，然后将结果发送回原始设备。在推理过程中，Lina 根据专家的流行程度动态调度资源，平衡跨设备的全对全通信的传输大小和带宽。ExFlow [[49](https://arxiv.org/html/2407.12391v1#bib.bib49)]是一种优化技术，用于加速分布式 MoE 的推理。它利用层间专家亲和性，即不同 MoE 层之间的专家选择相关性。通过根据专家的亲和性将专家放置在相应的 GPU 上，ExFlow 减少了跨 GPU 路由延迟，提高了推理吞吐量。

专家卸载。SiDA-MoE [[50](https://arxiv.org/html/2407.12391v1#bib.bib50)]（稀疏性驱动的数据感知）通过利用 MoE 模型中专家激活的内在稀疏性，结合主内存和 GPU 内存。SiDA-MoE 包含两个并行线程：推理线程和哈希构建线程。哈希构建线程预测每个层级中每个令牌将激活哪些专家，并将这些预测存储在哈希表中。然后，推理线程利用这些信息动态加载激活的专家到 GPU 上，并将非活动的专家卸载到主内存，从而最大化 GPU 内存的利用率。MoE-Infinity [[51](https://arxiv.org/html/2407.12391v1#bib.bib51)] 采用了不同的专家卸载方法。该系统利用了 MoE 模型在推理过程中表现出稀疏激活和时间局部性的观察，即只有少数专家会重复激活以处理特定序列。MoE-Infinity 在序列级别追踪专家激活，从而预测哪些专家将被需要并相应地预取它们。

MoE 效率。Fiddler [[52](https://arxiv.org/html/2407.12391v1#bib.bib52)] 是一个设计用于在有限数量的 GPU 上高效运行这些模型的系统，即使模型的大小通常会超过 GPU 的内存容量。Fiddler 战略性地分配模型的组件。经常使用的非专家层保留在 GPU 上。基于使用频率选择的一部分专家层也放置在 GPU 上。其余的则保留在 CPU 的内存中。Huang 等人 [[53](https://arxiv.org/html/2407.12391v1#bib.bib53)] 提出了三种优化技术来解决 MoE 推理效率低下的问题。 (i) 动态门控允许每个专家处理的令牌数量变化，这避免了静态门控中的资源过度配置，并减少了计算浪费、通信开销和内存消耗。 (ii) 专家缓存利用了专家激活通常是稀疏的并具有时间局部性的观察。通过将频繁使用（热点）专家缓存到 GPU 内存中，并将较少活动的专家缓冲到 CPU 内存中，专家缓存减少了 GPU 上的静态内存分配。 (iii) 不平衡的令牌分配给专家可能导致瓶颈和性能下降。专家负载均衡确保了在设备之间更均匀的工作负载分配。

### VI-C 杂项领域

伦理与环境可持续性。Sheng 等人 [[54](https://arxiv.org/html/2407.12391v1#bib.bib54)] 通过引入虚拟代币计数器（VTC）来确保 LLM 服务的公平性。VTC 基于一个成本函数定义 LLM 服务的公平性，该函数考虑了处理的输入和输出代币的数量。它通过跟踪每个客户端收到的服务并优先考虑服务最少的客户端来实现公平，同时也考虑处理输入和输出代币的不同成本。Sprout [[55](https://arxiv.org/html/2407.12391v1#bib.bib55)] 关注 LLM 的环境可持续性，并设计了一个框架来减少 LLM 推理服务的碳足迹。Sprout 引入了“生成指令”来指导自回归生成过程，在可持续性需求与高质量生成需求之间取得平衡。

推理管道优化。FlashDecoding++ [[56](https://arxiv.org/html/2407.12391v1#bib.bib56)] 进行推理引擎性能优化，解决了软最大同步、GPU 内核和数据流等多个问题。例如，解码阶段进行线性 GEMM 操作，其中涉及的批量大小维度远小于其他维度。FlashDecoding++ 通过双缓冲加速平坦 GEMM，该加速技术重叠计算和数据传输，并隐藏加载输入矩阵的内存延迟。Parrot [[57](https://arxiv.org/html/2407.12391v1#bib.bib57)] 旨在优化涉及多个 LLM 请求的复杂工作流的 LLM 应用性能。Parrot 进行数据流分析，发现多个 LLM 请求之间的相关性，并引入一系列优化以提高性能。FlashAttention-3 [[58](https://arxiv.org/html/2407.12391v1#bib.bib58)] 是一种加速大语言模型和长上下文应用中注意力的方法。它引入了如 warp 专门化和异步块操作等技术，以优化 GPU 利用率。与前任相比，FlashAttention-3 在 Hopper GPU 上实现了显著的加速，并减少了 FP8 计算中的数值误差。

节俭推理。FrugalGPT [[59](https://arxiv.org/html/2407.12391v1#bib.bib59)] 提出了几种减少推理成本的解决方案，例如提示缓存和 LLM 级联，后者使用一系列 LLM，从便宜的开始，只有在必要时才使用更昂贵的 LLM。SpecInfer [[60](https://arxiv.org/html/2407.12391v1#bib.bib60)] 采用了推测解码，使用较小的推测模型预测 LLM 的输出，从而减少计算资源。这些预测组织成树状结构，其准确性与 LLM 进行并行验证。RouteLLM [[61](https://arxiv.org/html/2407.12391v1#bib.bib61)] 在推理过程中动态选择更强的或较弱的 LLM，以优化成本与响应质量之间的平衡。

## 结论

本调查系统全面介绍了 LLM 服务系统最新进展，强调了系统级解决方案对提高性能和效率的重要性。我们强调了部署和扩展 LLM 的关键创新，为 LLM 服务系统未来的发展铺平了道路。

## 致谢

该资料基于通过助理国防部长研究与工程在空军合同编号 FA8702-15-D-0001 支持的工作，并且基于美国空军研究实验室合作协议编号 FA8750-19-2-1000。 本材料中的任何观点，发现，结论或建议均为作者个人意见，并不一定反映助理国防部长研究与工程或美国空军的观点。未经本文中的任何版权通知，美国政府有权为政府目的复制和分发再版。

## 参考文献

+   [1] T. Cai, Y. Li, Z. Geng, H. Peng, J. D. Lee, D. Chen,和 T. Dao，“Medusa: 多头解码的简单 LLM 推断加速框架”，*arXiv 预印本 arXiv:2401.10774*，2024 年。

+   [2] Y. Fu, P. Bailis, I. Stoica, and H. Zhang，“通过前瞻解码打破 llm 推断的顺序依赖”，*arXiv 预印本 arXiv:2402.02057*，2024 年。

+   [3] M. Adnan, A. Arunkumar, G. Jain, P. Nair, I. Soloveychik,和 P. Kamath，“Keyformer: 通过密钥标记选择减少 KV 缓存以实现高效生成推断”，*机器学习与系统论文集*，第 6 卷，114–127 页，2024 年。

+   [4] X. Miao, G. Oliaro, Z. Zhang, X. Cheng, H. Jin, T. Chen,和 Z. Jia，“走向高效的生成大型语言模型服务：从算法到系统的调查”，*arXiv 预印本 arXiv:2312.15234*，2023 年。

+   [5] Z. Yuan, Y. Shang, Y. Zhou, Z. Dong, C. Xue, B. Wu, Z. Li, Q. Gu, Y. J. Lee, Y. Yan 等，“LLM 推断揭秘：调查和屋脊线模型见解”，*arXiv 预印本 arXiv:2402.16363*，2024 年。

+   [6] Z. Zhou, X. Ning, K. Hong, T. Fu, J. Xu, S. Li, Y. Lou, L. Wang, Z. Yuan, X. Li 等，“关于大型语言模型高效推断的调查”，*arXiv 预印本 arXiv:2404.14294*，2024 年。

+   [7] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez, Ł. Kaiser,和 I. Polosukhin，“注意力就是你需要的一切”，*神经信息处理系统进展*，第 30 卷，2017 年。

+   [8] A. Radford, K. Narasimhan, T. Salimans, I. Sutskever 等，“通过生成式预训练来改善语言理解”，2018 年。

+   [9] R. Pope, S. Douglas, A. Chowdhery, J. Devlin, J. Bradbury, J. Heek, K. Xiao, S. Agrawal,和 J. Dean，“高效扩展变压器推断”，*机器学习与系统论文集*，第 5 卷，606–624 页，2023 年。

+   [10] W. 权, Z. 李, S. 庄, Y. 盛, L. 郑, C. H. 余, J. 冯, H. 张, 和 I. 斯托伊卡, “大型语言模型服务的高效内存管理与 pagedattention,” 载于 *第 29 届操作系统原理研讨会论文集*, 2023, 第 611–626 页.

+   [11] “文本生成推理: 一个用于文本生成推理的 rust、python 和 grpc 服务器。” [在线]. 可用: https://github.com/huggingface/text-generation-inference

+   [12] “Tensorrt-llm: 一个优化的大型语言模型推理的 tensorrt 工具箱。” [在线]. 可用: https://github.com/NVIDIA/TensorRT-LLM

+   [13] R. 普拉布, A. 纳亚克, J. 莫汉, R. 拉姆吉, 和 A. 潘瓦尔, “vattention: 为无 pagedattention 的 llms 服务提供动态内存管理,” *arXiv 预印本 arXiv:2405.04437*, 2024.

+   [14] I. 金, G. 陈, S.-s. 李, N. 萨尔达, A. 坎德尔瓦尔, 和 L. 钟, “Prompt cache: 低延迟推理的模块化注意力重用,” *机器学习与系统会议论文集*, 第 6 卷, 第 325–338 页, 2024.

+   [15] B. 高, Z. 贺, P. Sharma, Q. 康, D. 叶夫季奇, J. 邓, X. 杨, Z. 于, 和 P. 左, “针对多轮对话的成本效益大型语言模型服务与 CachedAttention,” 载于 *2024 年 USENIX 年会技术会议 (USENIX ATC 24)*.   圣克拉拉, CA: USENIX 协会, 2024 年 7 月, 第 111–126 页. [在线]. 可用: https://www.usenix.org/conference/atc24/presentation/gao-bin-cost

+   [16] H. 刘, M. 扎哈里亚, 和 P. 阿贝尔, “使用块状变换器的环形注意力以应对接近无限上下文,” *arXiv 预印本 arXiv:2310.01889*, 2023.

+   [17] B. 林, T. 彭, C. 张, M. 孙, L. 李, H. 赵, W. 肖, Q. 许, X. 邱, S. 李 *等*, “Infinite-llm: 使用 distattention 和分布式 kvcache 的长上下文高效 llm 服务,” *arXiv 预印本 arXiv:2401.02669*, 2024.

+   [18] C. 胡, H. 黄, J. 胡, J. 徐, X. 陈, T. 谢, C. 王, S. 王, Y. 包, N. 孙 *等*, “Memserve: 用于分离式 llm 服务的上下文缓存与弹性内存池,” *arXiv 预印本 arXiv:2406.17565*, 2024.

+   [19] W. 李, J. 李, J. 徐, 和 J. 沈, “Infinigen: 动态 kv 缓存管理下的大型语言模型高效生成推理,” *arXiv 预印本 arXiv:2406.19707*, 2024.

+   [20] B. 吴, S. 刘, Y. 钟, P. 孙, X. 刘, 和 X. 金, “Loongserve: 使用弹性序列并行处理长上下文大型语言模型的高效服务,” *arXiv 预印本 arXiv:2404.09526*, 2024.

+   [21] Y. 盛, L. 郑, B. 袁, Z. 李, M. 瑞亚宾, B. 陈, P. 梁, C. Ré, I. 斯托伊卡, 和 C. 张, “Flexgen: 使用单 GPU 的大型语言模型高吞吐量生成推理,” 载于 *国际机器学习会议*.   PMLR, 2023, 第 31,094–31,116 页.

+   [22] Z. 刘, J. 袁, H. 金, S. 钟, Z. 许, V. 布拉维曼, B. 陈, 和 X. 胡, “Kivi: 一种无调优的非对称 2bit 量化用于 kv 缓存,” *arXiv 预印本 arXiv:2402.02750*, 2024.

+   [23] H. Kang, Q. Zhang, S. Kundu, G. Jeong, Z. Liu, T. Krishna, 和 T. Zhao, “Gear：用于近无损生成推理的高效 kv 缓存压缩方案，” *arXiv 预印本 arXiv:2403.05527*, 2024 年。

+   [24] A. Liu, J. Liu, Z. Pan, Y. He, G. Haffari, 和 B. Zhuang, “Minicache：针对大语言模型的 kv 缓存深度维度压缩，” *arXiv 预印本 arXiv:2405.14366*, 2024 年。

+   [25] Z. Zheng, X. Ren, F. Xue, Y. Luo, X. Jiang, 和 Y. You, “响应长度感知与序列调度：一个由 llm 驱动的 llm 推理管道，” *《神经信息处理系统进展》*, 第 36 卷, 2024 年。

+   [26] Y. Jin, C.-F. Wu, D. Brooks, 和 G.-Y. Wei, “S3：在生成推理期间提高 gpu 利用率以实现更高的吞吐量，” *《神经信息处理系统进展》*, 第 36 卷, 页码 18 015–18 027, 2023 年。

+   [27] G.-I. Yu, J. S. Jeong, G.-W. Kim, S. Kim, 和 B.-G. Chun, “Orca：一种用于$\{$Transformer-Based$\}$生成模型的分布式服务系统，” 在 *第 16 届 USENIX 操作系统设计与实现研讨会（OSDI 22）*，2022 年, 页码 521–538。

+   [28] C. Holmes, M. Tanaka, M. Wyatt, A. A. Awan, J. Rasley, S. Rajbhandari, R. Y. Aminabadi, H. Qin, A. Bakhtiari, L. Kurilenko *等*, “Deepspeed-fastgen：通过 mii 和 deepspeed-inference 实现的 llm 高吞吐量文本生成，” *arXiv 预印本 arXiv:2401.08671*, 2024 年。

+   [29] A. Agrawal, N. Kedia, A. Panwar, J. Mohan, N. Kwatra, B. S. Gulavani, A. Tumanov, 和 R. Ramjee, “通过 sarathi-serve 驯服 llm 推理中的吞吐量-延迟权衡，” *arXiv 预印本 arXiv:2403.02310*, 2024 年。

+   [30] C. Hu, H. Huang, L. Xu, X. Chen, J. Xu, S. Chen, H. Feng, C. Wang, S. Wang, Y. Bao *等*, “无干扰推理：针对混合下游工作负载的分离 llm 推理，” *arXiv 预印本 arXiv:2401.11181*, 2024 年。

+   [31] P. Patel, E. Choukse, C. Zhang, Í. Goiri, A. Shah, S. Maleki, 和 R. Bianchini, “Splitwise：通过阶段拆分实现高效生成 llm 推理，” *arXiv 预印本 arXiv:2311.18677*, 2023 年。

+   [32] Y. Zhong, S. Liu, J. Chen, J. Hu, Y. Zhu, X. Liu, X. Jin, 和 H. Zhang, “Distserve：为优化良率的大语言模型服务分解预填充和解码，” *arXiv 预印本 arXiv:2401.09670*, 2024 年。

+   [33] Z. XUANLEI, B. Jia, H. Zhou, Z. Liu, S. Cheng, 和 Y. You, “Hetegen：在资源受限设备上高效的异构并行推理用于大语言模型，” *《机器学习与系统会议论文集》*, 第 6 卷, 页码 162–172, 2024 年。

+   [34] H. Oh, K. Kim, J. Kim, S. Kim, J. Lee, D.-s. Chang, 和 J. Seo, “Exegpt：针对 llm 推理的约束感知资源调度，” 在 *第 29 届 ACM 国际编程语言与操作系统架构支持会议论文集，第二卷*，2024 年，页码 369–384。

+   [35] Y. Mei, Y. Zhuang, X. Miao, J. Yang, Z. Jia, 和 R. Vinayak, “Helix：通过 max-flow 在异构 gpu 上分布式服务大语言模型，” *arXiv 预印本 arXiv:2406.01566*, 2024 年。

+   [36] X. Miao, C. Shi, J. Duan, X. Xi, D. Lin, B. Cui, 和 Z. Jia, “Spotserve: 在可抢占实例上服务生成型大规模语言模型，” 在 *第 29 届 ACM 国际编程语言与操作系统架构支持会议论文集, 第 2 卷*, 2024, 第 1112–1127 页。

+   [37] Y. Fu, L. Xue, Y. Huang, A.-O. Brabete, D. Ustiugov, Y. Patel, 和 L. Mai, “Serverlessllm: 针对大规模语言模型的本地增强无服务器推理，” *arXiv 预印本 arXiv:2401.14351*, 2024。

+   [38] T. Griggs, X. Liu, J. Yu, D. Kim, W.-L. Chiang, A. Cheung, 和 I. Stoica, “M$\backslash$’elange: 通过利用 GPU 异质性实现成本高效的大规模语言模型服务，” *arXiv 预印本 arXiv:2404.14527*, 2024。

+   [39] B. Sun, Z. Huang, H. Zhao, W. Xiao, X. Zhang, Y. Li, 和 W. Lin, “Llumnix: 大规模语言模型服务的动态调度，” *arXiv 预印本 arXiv:2406.03243*, 2024。

+   [40] P. Patel, E. Choukse, C. Zhang, Í. Goiri, B. Warrier, N. Mahalingam, 和 R. Bianchini, “云中 LLM 的电源管理机会特征，” 在 *第 29 届 ACM 国际编程语言与操作系统架构支持会议论文集, 第 3 卷*, 2024, 第 207–222 页。

+   [41] Z. Yang, Y. Yang, C. Zhao, Q. Guo, W. He, 和 W. Ji, “Perllm: 针对多样化 LLM 服务的个性化推理调度与边缘-云协作，” *arXiv 预印本 arXiv:2405.14636*, 2024。

+   [42] X. Miao, G. Oliaro, X. Cheng, M. Wu, C. Unger, 和 Z. Jia, “Flexllm: 用于大规模语言模型推理和参数高效微调的共同服务系统，” *arXiv 预印本 arXiv:2402.18789*, 2024。

+   [43] J. Liu, Z. Wu, J.-W. Chung, F. Lai, M. Lee, 和 M. Chowdhury, “Andes: 确定和提升基于 LLM 的文本流服务的体验质量，” *arXiv 预印本 arXiv:2404.16283*, 2024。

+   [44] P. Lewis, E. Perez, A. Piktus, F. Petroni, V. Karpukhin, N. Goyal, H. Küttler, M. Lewis, W.-t. Yih, T. Rocktäschel *等*, “知识密集型 NLP 任务的检索增强生成，” *神经信息处理系统进展*, 第 33 卷，第 9459–9474 页, 2020。

+   [45] Y. Zhu, J.-C. Gu, C. Sikora, H. Ko, Y. Liu, C.-C. Lin, L. Shu, L. Luo, L. Meng, B. Liu *等*, “通过稀疏上下文选择加速检索增强生成推理，” *arXiv 预印本 arXiv:2405.16178*, 2024。

+   [46] C. Jin, Z. Zhang, X. Jiang, F. Liu, X. Liu, X. Liu, 和 X. Jin, “Ragcache: 高效的知识缓存用于检索增强生成，” *arXiv 预印本 arXiv:2404.12457*, 2024。

+   [47] J. Yao, H. Li, Y. Liu, S. Ray, Y. Cheng, Q. Zhang, K. Du, S. Lu, 和 J. Jiang, “Cacheblend: 快速大规模语言模型服务与缓存知识融合，” *arXiv 预印本 arXiv:2405.16444*, 2024。

+   [48] J. Li, Y. Jiang, Y. Zhu, C. Wang, 和 H. Xu, “通过 Lina 加速分布式 $\{$MoE$\}$ 训练和推理，” 在 *2023 USENIX 年度技术会议 (USENIX ATC 23)*, 2023, 第 945–959 页。

+   [49] J. Yao, Q. Anthony, A. Shafi, H. Subramoni, 和 D. K. D. Panda，“利用层间专家亲和性加速混合专家模型推理”，在*2024 年 IEEE 国际并行与分布式处理研讨会（IPDPS）*。IEEE，2024 年，第 915–925 页。

+   [50] Z. Du, S. Li, Y. Wu, X. Jiang, J. Sun, Q. Zheng, Y. Wu, A. Li, H. Li, 和 Y. Chen，“Sida：基于稀疏性的数据感知服务以实现高效且可扩展的大型混合专家模型”，*机器学习与系统会议论文集*，第 6 卷，第 224–238 页，2024 年。

+   [51] L. Xue, Y. Fu, Z. Lu, L. Mai, 和 M. Marina，“Moe-infinity：激活感知专家卸载以实现高效的 MOE 服务”，*arXiv 预印本 arXiv:2401.14361*，2024 年。

+   [52] K. Kamahori, Y. Gu, K. Zhu, 和 B. Kasikci，“Fiddler：用于快速推理混合专家模型的 CPU-GPU 协调”，*arXiv 预印本 arXiv:2402.07033*，2024 年。

+   [53] H. Huang, N. Ardalani, A. Sun, L. Ke, H.-H. S. Lee, A. Sridhar, S. Bhosale, C.-J. Wu, 和 B. Lee，“迈向 MOE 部署：缓解混合专家（MOE）推理中的低效”，*arXiv 预印本 arXiv:2303.06182*，2023 年。

+   [54] Y. Sheng, S. Cao, D. Li, B. Zhu, Z. Li, D. Zhuo, J. E. Gonzalez, 和 I. Stoica，“大型语言模型的公平性”，*arXiv 预印本 arXiv:2401.00588*，2023 年。

+   [55] B. Li, Y. Jiang, V. Gadepally, 和 D. Tiwari，“通过生成指令实现碳友好的大型语言模型推理的可持续性”，*arXiv 预印本 arXiv:2403.12900*，2024 年。

+   [56] K. Hong, G. Dai, J. Xu, Q. Mao, X. Li, J. Liu, Y. Dong, Y. Wang *等*，“Flashdecoding++：通过异步、扁平化 GEMM 优化和启发式方法加速大型语言模型推理”，*机器学习与系统会议论文集*，第 6 卷，第 148–161 页，2024 年。

+   [57] C. Lin, Z. Han, C. Zhang, Y. Yang, F. Yang, C. Chen, 和 L. Qiu，“Parrot：基于语义变量的 LLM 应用高效服务”，*arXiv 预印本 arXiv:2405.19888*，2024 年。

+   [58] J. Shah, G. Bikshandi, Y. Zhang, V. Thakkar, P. Ramani, 和 T. Dao，“Flashattention-3：具有异步和低精度的快速准确注意力”，*arXiv 预印本 arXiv:2407.08608*，2024 年。

+   [59] L. Chen, M. Zaharia, 和 J. Zou，“Frugalgpt：如何在降低成本和提高性能的同时使用大型语言模型”，*arXiv 预印本 arXiv:2305.05176*，2023 年。

+   [60] X. Miao, G. Oliaro, Z. Zhang, X. Cheng, Z. Wang, Z. Zhang, R. Y. Y. Wong, A. Zhu, L. Yang, X. Shi *等*，“Specinfer：通过基于树的推测推理和验证加速大型语言模型服务”，在*第 29 届 ACM 国际编程语言和操作系统架构支持会议论文集，第 3 卷*，2024 年，第 932–949 页。

+   [61] I. Ong, A. Almahairi, V. Wu, W.-L. Chiang, T. Wu, J. E. Gonzalez, M. W. Kadous, 和 I. Stoica，“Routellm：利用偏好数据学习路由 LLM”，*arXiv 预印本 arXiv:2406.18665*，2024 年。

生成于 2024 年 7 月 17 日 星期三 08:12:38，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/) 生成
