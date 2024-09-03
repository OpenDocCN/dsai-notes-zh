<!--yml

类别：未分类

日期：2024-09-03 17:29:09

-->

# 大型语言模型遇见多模态生成与编辑：一项调查

> 来源：[`arxiv.org/html/2405.19334`](https://arxiv.org/html/2405.19334)

1.  [1 引言](https://arxiv.org/html/2405.19334v2#S1 "在 大型语言模型遇见多模态生成与编辑：一项调查")

    1.  [1.1 范围](https://arxiv.org/html/2405.19334v2#S1.SS1 "在 1 引言 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

    1.  [1.2 内容概览](https://arxiv.org/html/2405.19334v2#S1.SS2 "在 1 引言 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

1.  [2 相关调查](https://arxiv.org/html/2405.19334v2#S2 "在大型语言模型遇见多模态生成与编辑：一项调查")

1.  [3 基础知识](https://arxiv.org/html/2405.19334v2#S3 "在 大型语言模型遇见多模态生成与编辑：一项调查")

    1.  [3.1 生成模型](https://arxiv.org/html/2405.19334v2#S3.SS1 "在 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

        1.  [3.1.1 生成对抗网络](https://arxiv.org/html/2405.19334v2#S3.SS1.SSS1 "在 3.1 生成模型 ‣ 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

        1.  [3.1.2 变分自编码器](https://arxiv.org/html/2405.19334v2#S3.SS1.SSS2 "在 3.1 生成模型 ‣ 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

        1.  [3.1.3 流基模型](https://arxiv.org/html/2405.19334v2#S3.SS1.SSS3 "在 3.1 生成模型 ‣ 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

        1.  [3.1.4 扩散模型](https://arxiv.org/html/2405.19334v2#S3.SS1.SSS4 "在 3.1 生成模型 ‣ 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

        1.  [3.1.5 自回归模型](https://arxiv.org/html/2405.19334v2#S3.SS1.SSS5 "在 3.1 生成模型 ‣ 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

    1.  [3.2 多模态对齐模型](https://arxiv.org/html/2405.19334v2#S3.SS2 "在 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

    1.  [3.3 大型语言模型](https://arxiv.org/html/2405.19334v2#S3.SS3 "在 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

    1.  [3.4 多模态大型语言模型](https://arxiv.org/html/2405.19334v2#S3.SS4 "在 3 基础知识 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

1.  [4 图像生成与编辑](https://arxiv.org/html/2405.19334v2#S4 "在 大型语言模型遇见多模态生成与编辑：一项调查")

    1.  [4.1 图像生成](https://arxiv.org/html/2405.19334v2#S4.SS1 "在 4 图像生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

        1.  [4.1.1 基于 CLIP 的文本引导图像生成](https://arxiv.org/html/2405.19334v2#S4.SS1.SSS1 "在 4.1 图像生成 ‣ 4 图像生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：一项调查")

        1.  [4.1.2 通过 LLMs 进行文本引导图像生成](https://arxiv.org/html/2405.19334v2#S4.SS1.SSS2 "在 4.1 图像生成‣4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [4.1.3 通过 LLMs 进行图像布局规划](https://arxiv.org/html/2405.19334v2#S4.SS1.SSS3 "在 4.1 图像生成‣4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [4.1.4 通过 LLMs 合成和改进提示语](https://arxiv.org/html/2405.19334v2#S4.SS1.SSS4 "在 4.1 图像生成‣4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [4.1.5 通过 LLMs 进行图像质量评估](https://arxiv.org/html/2405.19334v2#S4.SS1.SSS5 "在 4.1 图像生成‣4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

    1.  [4.2 图像编辑](https://arxiv.org/html/2405.19334v2#S4.SS2 "在 4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [4.2.1 使用 CLIP/T5 进行图像编辑](https://arxiv.org/html/2405.19334v2#S4.SS2.SSS1 "在 4.2 图像编辑‣4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [4.2.2 使用 LLMs 进行图像编辑](https://arxiv.org/html/2405.19334v2#S4.SS2.SSS2 "在 4.2 图像编辑‣4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

    1.  [4.3 图像语言数据集](https://arxiv.org/html/2405.19334v2#S4.SS3 "在 4 图像生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

1.  [5 视频生成和编辑](https://arxiv.org/html/2405.19334v2#S5 "在 LLMs 遇见多模态生成和编辑：一项调查中")

    1.  [5.1 视频生成](https://arxiv.org/html/2405.19334v2#S5.SS1 "在 5 视频生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [5.1.1 使用 CLIP 进行文本到视频生成](https://arxiv.org/html/2405.19334v2#S5.SS1.SSS1 "在 5.1 视频生成‣5 视频生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [5.1.2 使用 LLMs 进行文本到视频生成](https://arxiv.org/html/2405.19334v2#S5.SS1.SSS2 "在 5.1 视频生成中‣5 视频生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查")

        1.  [5.1.3 通过 LLMs 进行视频布局规划](https://arxiv.org/html/2405.19334v2#S5.SS1.SSS3 "在 5.1 视频生成‣5 视频生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [5.1.4 通过 LLMs 进行时间提示生成](https://arxiv.org/html/2405.19334v2#S5.SS1.SSS4 "在 5.1 视频生成‣5 视频生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

    1.  [5.2 视频编辑](https://arxiv.org/html/2405.19334v2#S5.SS2 "在 5 视频生成和编辑‣LLMs 遇见多模态生成和编辑：一项调查中")

        1.  [5.2.1 使用 CLIP/T5 的文本引导视频编辑](https://arxiv.org/html/2405.19334v2#S5.SS2.SSS1 "在 5.2 视频编辑 ‣ 5 视频生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [5.2.2 使用大型语言模型进行文本引导的视频编辑](https://arxiv.org/html/2405.19334v2#S5.SS2.SSS2 "在 5.2 视频编辑 ‣ 5 视频生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

    1.  [5.3 视频语言数据集](https://arxiv.org/html/2405.19334v2#S5.SS3 "在 5 视频生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

    1.  [5.4 总结](https://arxiv.org/html/2405.19334v2#S5.SS4 "在 5 视频生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

1.  [6 3D 生成与编辑](https://arxiv.org/html/2405.19334v2#S6 "在 大型语言模型遇见多模态生成与编辑：综述")

    1.  [6.1 3D 生成](https://arxiv.org/html/2405.19334v2#S6.SS1 "在 6 3D 生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [6.1.1 使用 CLIP/T5 生成 3D](https://arxiv.org/html/2405.19334v2#S6.SS1.SSS1 "在 6.1 3D 生成 ‣ 6 3D 生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [6.1.2 使用大型语言模型生成 3D](https://arxiv.org/html/2405.19334v2#S6.SS1.SSS2 "在 6.1 3D 生成 ‣ 6 3D 生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

    1.  [6.2 3D 编辑](https://arxiv.org/html/2405.19334v2#S6.SS2 "在 6 3D 生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [6.2.1 使用 CLIP/T5 编辑 3D](https://arxiv.org/html/2405.19334v2#S6.SS2.SSS1 "在 6.2 3D 编辑 ‣ 6 3D 生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [6.2.2 使用大型语言模型编辑 3D](https://arxiv.org/html/2405.19334v2#S6.SS2.SSS2 "在 6.2 3D 编辑 ‣ 6 3D 生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

    1.  [6.3 总结](https://arxiv.org/html/2405.19334v2#S6.SS3 "在 6 3D 生成与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

1.  [7 音频生成、理解与编辑](https://arxiv.org/html/2405.19334v2#S7 "在 大型语言模型遇见多模态生成与编辑：综述")

    1.  [7.1 领域](https://arxiv.org/html/2405.19334v2#S7.SS1 "在 7 音频生成、理解与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [7.1.1 一般音频声音](https://arxiv.org/html/2405.19334v2#S7.SS1.SSS1 "在 7.1 领域 ‣ 7 音频生成、理解与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [7.1.2 音乐](https://arxiv.org/html/2405.19334v2#S7.SS1.SSS2 "在 7.1 领域 ‣ 7 音频生成、理解与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

        1.  [7.1.3 语音](https://arxiv.org/html/2405.19334v2#S7.SS1.SSS3 "在 7.1 领域 ‣ 7 音频生成、理解与编辑 ‣ 大型语言模型遇见多模态生成与编辑：综述")

    1.  [7.2 LLMs 的角色](https://arxiv.org/html/2405.19334v2#S7.SS2 "在 7 音频生成、理解和编辑 ‣ LLMs 遇见多模态生成与编辑：调查")

        1.  [7.2.1 LLMs 作为骨干](https://arxiv.org/html/2405.19334v2#S7.SS2.SSS1 "在 7.2 LLMs 的角色 ‣ 7 音频生成、理解和编辑 ‣ LLMs 遇见多模态生成与编辑：调查")

        1.  [7.2.2 LLMs 作为调节器](https://arxiv.org/html/2405.19334v2#S7.SS2.SSS2 "在 7.2 LLMs 的角色 ‣ 7 音频生成、理解和编辑 ‣ LLMs 遇见多模态生成与编辑：调查")

        1.  [7.2.3 LLMs 作为标签器](https://arxiv.org/html/2405.19334v2#S7.SS2.SSS3 "在 7.2 LLMs 的角色 ‣ 7 音频生成、理解和编辑 ‣ LLMs 遇见多模态生成与编辑：调查")

        1.  [7.2.4 LLMs 作为代理](https://arxiv.org/html/2405.19334v2#S7.SS2.SSS4 "在 7.2 LLMs 的角色 ‣ 7 音频生成、理解和编辑 ‣ LLMs 遇见多模态生成与编辑：调查")

        1.  [7.2.5 受启发的骨干 LLMs](https://arxiv.org/html/2405.19334v2#S7.SS2.SSS5 "在 7.2 LLMs 的角色 ‣ 7 音频生成、理解和编辑 ‣ LLMs 遇见多模态生成与编辑：调查")

1.  [8 工具增强多模态代理](https://arxiv.org/html/2405.19334v2#S8 "在 LLMs 遇见多模态生成与编辑：调查")

    1.  [8.1 动机](https://arxiv.org/html/2405.19334v2#S8.SS1 "在 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成与编辑：调查")

    1.  [8.2 方法](https://arxiv.org/html/2405.19334v2#S8.SS2 "在 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成与编辑：调查")

        1.  [8.2.1 无需训练的方法](https://arxiv.org/html/2405.19334v2#S8.SS2.SSS1 "在 8.2 方法 ‣ 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成与编辑：调查")

        1.  [8.2.2 指令调优方法](https://arxiv.org/html/2405.19334v2#S8.SS2.SSS2 "在 8.2 方法 ‣ 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成与编辑：调查")

    1.  [8.3 示范](https://arxiv.org/html/2405.19334v2#S8.SS3 "在 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成与编辑：调查")

    1.  [8.4 总结](https://arxiv.org/html/2405.19334v2#S8.SS4 "在 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成与编辑：调查")

1.  [9 生成式 AI 安全](https://arxiv.org/html/2405.19334v2#S9 "在 LLMs 遇见多模态生成与编辑：调查")

1.  [10 应用](https://arxiv.org/html/2405.19334v2#S10 "在 LLMs 遇见多模态生成与编辑：调查")

    1.  [10.1 图像](https://arxiv.org/html/2405.19334v2#S10.SS1 "在 10 应用 ‣ LLMs 遇见多模态生成与编辑：调查")

    1.  [10.2 视频](https://arxiv.org/html/2405.19334v2#S10.SS2 "在 10 应用 ‣ LLMs 遇见多模态生成与编辑：调查")

    1.  [10.3 音频](https://arxiv.org/html/2405.19334v2#S10.SS3 "在 10 应用 ‣ LLMs 遇见多模态生成与编辑：调查")

    1.  [10.4 3D](https://arxiv.org/html/2405.19334v2#S10.SS4 "在 10 应用 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [10.4.1 其他](https://arxiv.org/html/2405.19334v2#S10.SS4.SSS1 "在 10.4 3D ‣ 10 应用 ‣ LLMs 迎接多模态生成与编辑：调查")

1.  [11 未来前景](https://arxiv.org/html/2405.19334v2#S11 "在 LLMs 迎接多模态生成与编辑：调查")

    1.  [11.1 技术前景](https://arxiv.org/html/2405.19334v2#S11.SS1 "在 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.1.1 高分辨率生成](https://arxiv.org/html/2405.19334v2#S11.SS1.SSS1 "在 11.1 技术前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.1.2 长期序列生成](https://arxiv.org/html/2405.19334v2#S11.SS1.SSS2 "在 11.1 技术前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.1.3 更准确且细致的生成控制](https://arxiv.org/html/2405.19334v2#S11.SS1.SSS3 "在 11.1 技术前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.1.4 多视角一致性](https://arxiv.org/html/2405.19334v2#S11.SS1.SSS4 "在 11.1 技术前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.1.5 多模态生成的统一训练](https://arxiv.org/html/2405.19334v2#S11.SS1.SSS5 "在 11.1 技术前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.1.6 高效训练与部署策略](https://arxiv.org/html/2405.19334v2#S11.SS1.SSS6 "在 11.1 技术前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.1.7 伦理安全内容生成](https://arxiv.org/html/2405.19334v2#S11.SS1.SSS7 "在 11.1 技术前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

    1.  [11.2 应用前景](https://arxiv.org/html/2405.19334v2#S11.SS2 "在 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.2.1 语义音频合成](https://arxiv.org/html/2405.19334v2#S11.SS2.SSS1 "在 11.2 应用前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.2.2 多模态讲故事](https://arxiv.org/html/2405.19334v2#S11.SS2.SSS2 "在 11.2 应用前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.2.3 互动内容设计](https://arxiv.org/html/2405.19334v2#S11.SS2.SSS3 "在 11.2 应用前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.2.4 3D 场景生成](https://arxiv.org/html/2405.19334v2#S11.SS2.SSS4 "在 11.2 应用前景 ‣ 11 未来前景 ‣ LLMs 迎接多模态生成与编辑：调查")

        1.  [11.2.5 可定制的头像](https://arxiv.org/html/2405.19334v2#S11.SS2.SSS5 "在 11.2 应用前景 ‣ 11 未来前景 ‣ LLMs 与多模态生成和编辑：综述")

    1.  [11.3 迈向世界模型](https://arxiv.org/html/2405.19334v2#S11.SS3 "在 11 未来前景 ‣ LLMs 与多模态生成和编辑：综述")

1.  [12 结论](https://arxiv.org/html/2405.19334v2#S12 "在 LLMs 与多模态生成和编辑：综述")

# LLMs 与多模态生成和编辑：

综述

Yingqing He^†^∗、Zhaoyang Liu^†^∗、Jingye Chen^∗、Zeyue Tian^∗、Hongyu Liu^∗、Xiaowei Chi^∗，

Runtao Liu^∗、Ruibin Yuan^∗、Yazhou Xing^∗、Wenhai Wang、Jifeng Dai、Yong Zhang，

Wei Xue、Qifeng Liu、Yike Guo 和 Qifeng Chen^† 项目负责人；^∗ 共同第一作者。Yingqing He、Zhaoyang Liu、Jingye Chen、Zeyue Tian、Hongyu Liu、Xiaowei Chi、Runtao Liu、Ruibin Yuan、Yazhou Xing、Wei Xue、Qifeng Liu、Yike Guo 和 Qifeng Chen 均来自香港科技大学，香港特别行政区。Wenhai Wang 来自香港中文大学，香港特别行政区。Jifeng Dai 来自清华大学，中国。Yong Zhang 来自腾讯 AI 实验室，中国。

###### 摘要

随着大语言模型（LLMs）的最新进展，人们对将 LLMs 与多模态学习相结合越来越感兴趣。此前对多模态大语言模型（MLLMs）的调查主要集中在多模态理解上。本调查详细阐述了在各个领域（包括图像、视频、3D 和音频）中的多模态生成和编辑。具体而言，我们总结了这些领域的重要进展及里程碑工作，并将这些研究分为基于 LLM 的方法和基于 CLIP/T5 的方法。接着，我们总结了 LLM 在多模态生成中的各种角色，并全面探讨了这些方法背后的关键技术组件和这些研究中使用的多模态数据集。此外，我们还深入研究了可以利用现有生成模型进行人机交互的工具增强型多模态代理。最后，我们讨论了生成 AI 安全领域的进展，调查了新兴应用，并讨论了未来前景。我们的工作提供了多模态生成和处理的系统性和深入的概述，预计将推动人工智能生成内容（AIGC）和世界模型的发展。所有相关论文的精选列表可以在 [`github.com/YingqingHe/Awesome-LLMs-meet-Multimodal-Generation`](https://github.com/YingqingHe/Awesome-LLMs-meet-Multimodal-Generation) 找到。

###### 索引词：

LLMs、MLLMs、多模态生成、文本到图像、文本到视频、文本到 3D、文本到音频、多模态代理、AI 安全、扩散模型、变换器、生成 AI、AIGC。![参见标题](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 1：我们的主要目标是研究大语言模型在语言引导的多模态生成任务中的角色。我们关注的模态包括图像、视频、3D 和音频（包括声音、音乐和语音）。

## 1 引言

人类与物理世界的互动涉及来自多种模态的信息，例如语言、视觉和音频。因此，实现一个世界模拟器也要求模型能够以灵活的方式感知和响应多模态信息。最近，OpenAI 推出了一个名为 Sora 的基础文本到视频生成模型[[1](https://arxiv.org/html/2405.19334v2#bib.bib1)]，它能够生成高度逼真的视频作为世界模拟器。它在模拟或生成现实世界场景方面取得了重大进展，但无法生成其他模态，例如文本、3D 和音频。此外，它缺乏感知其他模态（如图像、视频、3D 和音频）的能力，使其成为一个无法理解的世界模拟器。

在过去几年中，研究人员专注于每种单一模态的生成，并取得了巨大进展：在文本生成方面，我们见证了自然语言处理任务性能的**质的飞跃**：从 BERT [[2](https://arxiv.org/html/2405.19334v2#bib.bib2)]、GPT1 [[3](https://arxiv.org/html/2405.19334v2#bib.bib3)]、GPT2 [[4](https://arxiv.org/html/2405.19334v2#bib.bib4)]、GPT3 [[5](https://arxiv.org/html/2405.19334v2#bib.bib5)]、GPT4 [[6](https://arxiv.org/html/2405.19334v2#bib.bib6)]到 ChatGPT [[7](https://arxiv.org/html/2405.19334v2#bib.bib7)]、LLaMA [[8](https://arxiv.org/html/2405.19334v2#bib.bib8), [9](https://arxiv.org/html/2405.19334v2#bib.bib9)]，模型参数和训练样本数量迅速增长，导致模态能力和产品部署的不断提升。在视觉生成领域，随着扩散模型和大规模图像-文本数据集的快速进展，文本到图像（T2I）生成取得了显著成就，能够根据用户提供的各种文本提示合成高质量图像，例如 SDXL [[10](https://arxiv.org/html/2405.19334v2#bib.bib10)]和 PIXART-$\alpha$ [[11](https://arxiv.org/html/2405.19334v2#bib.bib11)]。随后，通过利用视频扩散模型 [[12](https://arxiv.org/html/2405.19334v2#bib.bib12)]和大规模视频-语言数据集 [[13](https://arxiv.org/html/2405.19334v2#bib.bib13)]，在文本到视频生成领域取得了显著进展。特别是，出现了若干里程碑式的工作，如 [[14](https://arxiv.org/html/2405.19334v2#bib.bib14), [15](https://arxiv.org/html/2405.19334v2#bib.bib15), [16](https://arxiv.org/html/2405.19334v2#bib.bib16), [17](https://arxiv.org/html/2405.19334v2#bib.bib17), [18](https://arxiv.org/html/2405.19334v2#bib.bib18), [19](https://arxiv.org/html/2405.19334v2#bib.bib19), [20](https://arxiv.org/html/2405.19334v2#bib.bib20), [21](https://arxiv.org/html/2405.19334v2#bib.bib21), [22](https://arxiv.org/html/2405.19334v2#bib.bib22), [23](https://arxiv.org/html/2405.19334v2#bib.bib23)]和 Sora [[1](https://arxiv.org/html/2405.19334v2#bib.bib1)]。在 3D 生成方面，随着 CLIP [[24](https://arxiv.org/html/2405.19334v2#bib.bib24)]模型的出现，一些方法 [[25](https://arxiv.org/html/2405.19334v2#bib.bib25), [26](https://arxiv.org/html/2405.19334v2#bib.bib26), [27](https://arxiv.org/html/2405.19334v2#bib.bib27)]尝试将文本信息对齐到 3D 表示的渲染图像，如网格、点云、NeRF [[28](https://arxiv.org/html/2405.19334v2#bib.bib28)]和高斯溅射 [[29](https://arxiv.org/html/2405.19334v2#bib.bib29)]。这些方法已导致文本到 3D 生成的显著发展。此外，将稳定扩散（SD） [[30](https://arxiv.org/html/2405.19334v2#bib.bib30)]与文本到图像渲染结合，使得在文本到 3D 生成领域取得了一系列的工作 [[31](https://arxiv.org/html/2405.19334v2#bib.bib31), [32](https://arxiv.org/html/2405.19334v2#bib.bib32), [33](https://arxiv.org/html/2405.19334v2#bib.bib33), [34](https://arxiv.org/html/2405.19334v2#bib.bib34), [35](https://arxiv.org/html/2405.19334v2#bib.bib35), [36](https://arxiv.org/html/2405.19334v2#bib.bib36), [37](https://arxiv.org/html/2405.19334v2#bib.bib37), [38](https://arxiv.org/html/2405.19334v2#bib.bib38), [39](https://arxiv.org/html/2405.19334v2#bib.bib39), [40](https://arxiv.org/html/2405.19334v2#bib.bib40), [41](https://arxiv.org/html/2405.19334v2#bib.bib41), [42](https://arxiv.org/html/2405.19334v2#bib.bib42), [43](https://arxiv.org/html/2405.19334v2#bib.bib43), [44](https://arxiv.org/html/2405.19334v2#bib.bib44), [45](https://arxiv.org/html/2405.19334v2#bib.bib45)]。强大的文本到图像模型帮助 3D 生成实现了更高的性能和更好的视觉效果。在文本到音频生成领域，一系列代表性工作处理了不同的音频领域，如 [[46](https://arxiv.org/html/2405.19334v2#bib.bib46), [47](https://arxiv.org/html/2405.19334v2#bib.bib47), [48](https://arxiv.org/html/2405.19334v2#bib.bib48)]的文本到音频、[[49](https://arxiv.org/html/2405.19334v2#bib.bib49), [50](https://arxiv.org/html/2405.19334v2#bib.bib50), [51](https://arxiv.org/html/2405.19334v2#bib.bib51)]的文本到音乐和[[52](https://arxiv.org/html/2405.19334v2#bib.bib52), [53](https://arxiv.org/html/2405.19334v2#bib.bib53), [54](https://arxiv.org/html/2405.19334v2#bib.bib54), [55](https://arxiv.org/html/2405.19334v2#bib.bib55), [56](https://arxiv.org/html/2405.19334v2#bib.bib56), [57](https://arxiv.org/html/2405.19334v2#bib.bib57)]的文本到语音，它们在生成高质量的自然声音、音乐和人类级别的语音方面取得了显著的性能。

随着大型语言模型（LLMs）的显著进展和性能提升，其他非文本模态开始利用 LLMs 的力量，以提高生成质量或将多种模态集成到一个统一的系统中，以实现更强大的功能。在图像生成的背景下，LLMs 的集成可以分为两类。第一类涉及将视觉信息编码为离散的标记索引，试图统一视觉理解和生成 [[58](https://arxiv.org/html/2405.19334v2#bib.bib58), [59](https://arxiv.org/html/2405.19334v2#bib.bib59), [60](https://arxiv.org/html/2405.19334v2#bib.bib60), [61](https://arxiv.org/html/2405.19334v2#bib.bib61), [62](https://arxiv.org/html/2405.19334v2#bib.bib62), [63](https://arxiv.org/html/2405.19334v2#bib.bib63)]。具体来说，视觉信息被编码为标记表示，LLMs 直接理解和生成视觉标记，从而实现视觉理解和生成的同时进行。第二类则专注于利用 LLMs 提高现有预训练 T2I 模型的生成质量：一种方法利用 LLM 作为布局规划师，整合对象空间位置、数量和对象大小的知识，从而生成所需的边界框 [[64](https://arxiv.org/html/2405.19334v2#bib.bib64), [65](https://arxiv.org/html/2405.19334v2#bib.bib65), [66](https://arxiv.org/html/2405.19334v2#bib.bib66), [67](https://arxiv.org/html/2405.19334v2#bib.bib67), [68](https://arxiv.org/html/2405.19334v2#bib.bib68)]。获得边界框后，可以通过基于实际情况的 T2I 模型如 GLIGEN [[69](https://arxiv.org/html/2405.19334v2#bib.bib69)]生成图像。另一种方法利用 LLMs 扩展输入用户提示 [[70](https://arxiv.org/html/2405.19334v2#bib.bib70)]：通过提供高度详细和全面的提示，LLMs 生成高质量和丰富的图像。在 LLMs 的帮助下，图像生成达到了更高的生成质量，改进了提示跟随能力、对话功能和用户友好界面。

与图像领域类似，在视频生成中，LLMs 作为统一多模态联合生成的**通用骨干** [[71](https://arxiv.org/html/2405.19334v2#bib.bib71), [72](https://arxiv.org/html/2405.19334v2#bib.bib72)]，视频布局规划 [[73](https://arxiv.org/html/2405.19334v2#bib.bib73), [74](https://arxiv.org/html/2405.19334v2#bib.bib74), [65](https://arxiv.org/html/2405.19334v2#bib.bib65), [75](https://arxiv.org/html/2405.19334v2#bib.bib75), [76](https://arxiv.org/html/2405.19334v2#bib.bib76)] 和时间性提示生成 [[77](https://arxiv.org/html/2405.19334v2#bib.bib77), [78](https://arxiv.org/html/2405.19334v2#bib.bib78), [79](https://arxiv.org/html/2405.19334v2#bib.bib79), [80](https://arxiv.org/html/2405.19334v2#bib.bib80), [81](https://arxiv.org/html/2405.19334v2#bib.bib81)] 用于时间动态指导。在 3D 生成和编辑方面，LLMs 充当用户与 3D 资产之间的**桥梁**，提高了交互效率 [[82](https://arxiv.org/html/2405.19334v2#bib.bib82), [83](https://arxiv.org/html/2405.19334v2#bib.bib83)] 并帮助用户理解 3D 资产 [[84](https://arxiv.org/html/2405.19334v2#bib.bib84), [85](https://arxiv.org/html/2405.19334v2#bib.bib85)]。在音频生成和编辑的背景下，LLMs 的角色主要是作为多模态音频的**协调骨干** [[86](https://arxiv.org/html/2405.19334v2#bib.bib86), [87](https://arxiv.org/html/2405.19334v2#bib.bib87), [88](https://arxiv.org/html/2405.19334v2#bib.bib88), [89](https://arxiv.org/html/2405.19334v2#bib.bib89), [90](https://arxiv.org/html/2405.19334v2#bib.bib90), [91](https://arxiv.org/html/2405.19334v2#bib.bib91), [92](https://arxiv.org/html/2405.19334v2#bib.bib92), [93](https://arxiv.org/html/2405.19334v2#bib.bib93), [94](https://arxiv.org/html/2405.19334v2#bib.bib94), [95](https://arxiv.org/html/2405.19334v2#bib.bib95), [96](https://arxiv.org/html/2405.19334v2#bib.bib96), [97](https://arxiv.org/html/2405.19334v2#bib.bib97), [98](https://arxiv.org/html/2405.19334v2#bib.bib98)]，特定任务的**调节器** [[99](https://arxiv.org/html/2405.19334v2#bib.bib99), [100](https://arxiv.org/html/2405.19334v2#bib.bib100), [101](https://arxiv.org/html/2405.19334v2#bib.bib101)]，音频理解的**标注器** [[102](https://arxiv.org/html/2405.19334v2#bib.bib102), [103](https://arxiv.org/html/2405.19334v2#bib.bib103), [104](https://arxiv.org/html/2405.19334v2#bib.bib104)]，用于交互生成和编辑的**代理** [[105](https://arxiv.org/html/2405.19334v2#bib.bib105), [106](https://arxiv.org/html/2405.19334v2#bib.bib106), [107](https://arxiv.org/html/2405.19334v2#bib.bib107), [108](https://arxiv.org/html/2405.19334v2#bib.bib108), [109](https://arxiv.org/html/2405.19334v2#bib.bib109), [110](https://arxiv.org/html/2405.19334v2#bib.bib110)]，以及新颖方法的**灵感来源** [[55](https://arxiv.org/html/2405.19334v2#bib.bib55), [49](https://arxiv.org/html/2405.19334v2#bib.bib49), [111](https://arxiv.org/html/2405.19334v2#bib.bib111), [50](https://arxiv.org/html/2405.19334v2#bib.bib50), [112](https://arxiv.org/html/2405.19334v2#bib.bib112), [113](https://arxiv.org/html/2405.19334v2#bib.bib113)]。LLMs 在音频领域的广泛应用不仅改变了我们与声音和音乐的互动方式，还扩展了 AGI 与音频技术交汇处的边界。此外，多模态代理 [[105](https://arxiv.org/html/2405.19334v2#bib.bib105), [114](https://arxiv.org/html/2405.19334v2#bib.bib114), [115](https://arxiv.org/html/2405.19334v2#bib.bib115), [116](https://arxiv.org/html/2405.19334v2#bib.bib116), [117](https://arxiv.org/html/2405.19334v2#bib.bib117), [118](https://arxiv.org/html/2405.19334v2#bib.bib118)] 将大量 AIGC 工具整合到框架中，作为一个通用系统，依赖于 LLMs 来调用工具，但赋予 LLMs 理解和生成非文本模态内容的能力。总体而言，LLMs 在生成各种内容模式中扮演了不可或缺的角色。

为了促进多模态生成的发展并赋能世界模拟器，本工作提供了一个全面的综述，涉及 LLMs 在多模态生成中的作用。如图 [1](https://arxiv.org/html/2405.19334v2#S0.F1 "Figure 1 ‣ LLMs Meet Multimodal Generation and Editing: A Survey")所示，我们将 LLMs 的角色总结为几个关键方面，例如评估者、标签者、指令处理器、规划者、语义指导提供者或作为骨干架构。此外，我们在第[9](https://arxiv.org/html/2405.19334v2#S9 "9 Generative AI Safety ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节讨论了生成 AI 安全主题的发展，介绍了新兴应用，并在第[10](https://arxiv.org/html/2405.19334v2#S10 "10 Applications ‣ LLMs Meet Multimodal Generation and Editing: A Survey")和第[11](https://arxiv.org/html/2405.19334v2#S11 "11 Future prospects ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节讨论了潜在的未来前景。

我们总结了以下贡献：

+   •

    我们首次系统性地回顾了 LLMs 在多种模态（包括图像、视频、3D 和音频）生成和编辑中的应用。

+   •

    我们通过对比 LLM 前后的技术演变，提供了对这些方法进展和精炼的清晰视角。

+   •

    我们从技术角度总结了 LLMs 在每种模态生成或编辑过程中的各种角色。

+   •

    我们讨论了重要的 AI 安全问题，研究了新兴应用，并探索了推动多模态生成和世界模型发展的未来方向。

### 1.1 范围

本综述探讨了包括图像、视频、3D 模型和音频在内的多模态生成。我们调查的多模态生成包括不同模态的独立生成以及多模态的联合生成。我们不会深入探讨纯文本生成和处理，因为已有许多专门关注该领域进展的综述[[119](https://arxiv.org/html/2405.19334v2#bib.bib119), [120](https://arxiv.org/html/2405.19334v2#bib.bib120), [121](https://arxiv.org/html/2405.19334v2#bib.bib121)]。我们的主要关注点是近年来 LLMs 的出现如何协助生成其他视觉和音频模态，尤其是在开放域生成中的作用。这将帮助我们设计更好的多模态统一生成模型。请注意，我们讨论的任务和工作主要集中在基于语言的生成和编辑上。无条件生成和其他非文本基础的编辑不是我们的主要关注点，因为它们要么限于小范围领域，要么缺乏灵活性和可控性。具体而言，我们关注以下任务：

+   •

    文本到图像的生成和编辑：图像生成旨在根据用户提供的文本描述创建各种开放领域的图像内容，包括图片、照片或风格化的画作。图像编辑旨在修改输入图像内容，并可以根据用户指示进行。

+   •

    文本到视频的生成和编辑，其中模型根据自由形式的文本描述生成或修改各种动态视觉内容。

+   •

    文本到 3D 的生成和编辑，这是一项生成和编辑 3D 对象、场景或虚拟形象的任务，基于用户提供的文本描述。

+   •

    文本到音频的生成和编辑，其中使用文本描述生成音频，包括一般声音、音乐和语音。音频编辑任务，如添加、删除或修补，都可以通过修改现有音频内容的文本描述来完成。

+   •

    多模态生成代理，使得大语言模型（LLMs）能够通过利用各种专门的多模态工具处理不同模态的数据。

+   •

    生成性人工智能安全，关注减少有毒和偏见内容，保护版权，并解决多模态生成模型创造虚假内容的问题。

### 1.2 内容概述

我们首先在第[2](https://arxiv.org/html/2405.19334v2#S2 "2 Related Surveys ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节回顾了有关单一模态生成和 LLMs 的相关调查。接着，我们在第[3](https://arxiv.org/html/2405.19334v2#S3 "3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节简要回顾了代表性生成模型、多模态对齐模型、LLMs 和 MLLMs 的基本技术。接下来，我们在第[4](https://arxiv.org/html/2405.19334v2#S4 "4 Image Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节回顾了不同视觉模态下基于 LLM 的视觉生成，包括图像，第[5](https://arxiv.org/html/2405.19334v2#S5 "5 Video Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节的视频，第[6](https://arxiv.org/html/2405.19334v2#S6 "6 3D Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节的 3D，第[7](https://arxiv.org/html/2405.19334v2#S7 "7 Audio Generation, Understanding and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节的音频模态，以及第[8](https://arxiv.org/html/2405.19334v2#S8 "8 Tool-augmented Multimodal Agents ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节的多模态代理。最后，我们在第[9](https://arxiv.org/html/2405.19334v2#S9 "9 Generative AI Safety ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节回顾了生成 AI 的安全性，第[10](https://arxiv.org/html/2405.19334v2#S10 "10 Applications ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节的新兴应用，以及第[11](https://arxiv.org/html/2405.19334v2#S11 "11 Future prospects ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节对基于 LLMs 的多模态生成领域的潜在未来方向。

## 2 相关调查

模态特定生成调查。系列调查集中于单一模态生成，例如图像生成的[[122](https://arxiv.org/html/2405.19334v2#bib.bib122)]，视频生成的[[123](https://arxiv.org/html/2405.19334v2#bib.bib123)]，3D 生成的[[124](https://arxiv.org/html/2405.19334v2#bib.bib124)]，音频生成的[[125](https://arxiv.org/html/2405.19334v2#bib.bib125)]。然而，之前的生成范式主要采用预训练的 CLIP [[24](https://arxiv.org/html/2405.19334v2#bib.bib24)]，CLIP 相关变体 [[126](https://arxiv.org/html/2405.19334v2#bib.bib126)]，或语言编码器 T5 [[127](https://arxiv.org/html/2405.19334v2#bib.bib127)] 来实现开放领域的文本引导生成。随着 LLMs 的出现，利用强大的 LLMs 来增强每种模态内容生成的趋势日益增长。我们的工作旨在提供一个关于 LLMs 在各种模态生成中的作用的全面调查，这是之前调查中所缺乏的。

关于 LLMs 和 MLLMs 的调查。已经进行了大量调查以探讨 LLMs 的各个方面。例如，[[128](https://arxiv.org/html/2405.19334v2#bib.bib128)] 提供了基于 LLMs 的自主代理的全面检查。此外，[[129](https://arxiv.org/html/2405.19334v2#bib.bib129)] 和 [[130](https://arxiv.org/html/2405.19334v2#bib.bib130)] 研究了 MLLMs，介绍了将 LLMs 与其他非文本模态结合的论文。它们以混合的方式回顾了多模态理解和生成的论文，主要介绍了多模态理解的工作，而较少关注多模态生成。相比之下，我们的工作主要集中于生成方面，旨在深入探讨 LLMs 在每种模态生成过程中的性能和功能改进，最终带来一个更好的多模态 AI 生成世界。

## 3 基础知识

在本节中，我们首先在第[3.1 节](https://arxiv.org/html/2405.19334v2#S3.SS1 "3.1 Generative Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")回顾不同类型的生成模型。然后，我们在第[3.2 节](https://arxiv.org/html/2405.19334v2#S3.SS2 "3.2 Multimodal Alignment Model ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中说明多模态对齐模型。最后，我们在第[3.3 节](https://arxiv.org/html/2405.19334v2#S3.SS3 "3.3 Large Language Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")介绍大型语言模型的技术原理，并在第[3.4 节](https://arxiv.org/html/2405.19334v2#S3.SS4 "3.4 Multimodal Large Language Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")解释多模态大型语言模型。

![参考说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 2：生成模型的插图。在此图中，$x$ 和 $x_{0}$ 表示来自真实数据分布的样本，$x^{\prime}$ 代表来自模型估计数据分布的样本，而 $z$ 表示从先验分布（通常是高斯分布）中采样的潜在变量。

### 3.1 生成模型

我们回顾了经典生成模型的核心原理和基本概念，包括生成对抗网络（GANs）、变分自编码器（VAEs）、流模型、扩散模型和自回归模型。

生成模型的生成过程可以被描述为从先验分布 $p_{\mathbf{z}}(\mathbf{z})$ 中抽取的潜在样本 $z$ 转换为与目标数据分布一致的真实数据分布 $p_{\text{data}}(\mathbf{x})$ 中的生成样本 $\mathbf{x}^{\prime}$。具体而言，潜在变量 $\mathbf{z}$ 通过一个参数化函数，通常实现为神经网络，该函数学习将先验分布映射到目标数据分布。该转换的输出 $\mathbf{x}^{\prime}$ 被视为模仿原始数据分布统计特性的合成实例，这些实例可以对应于图像、视频、3D 表示、音频或文本等多种模态。

#### 3.1.1 生成对抗网络

GAN [[131](https://arxiv.org/html/2405.19334v2#bib.bib131)] 在多年的发展中在各种任务中取得了令人鼓舞的成果。如图 [2](https://arxiv.org/html/2405.19334v2#S3.F2 "Figure 2 ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")所示，GAN 包含两个关键组件：判别器（$D$）和生成器（$G$）。判别器旨在区分真实样本和虚假样本。生成器的目标是创建无法与真实数据区分开的虚假样本，并试图欺骗判别器。在训练过程中，$G$ 和 $D$ 同时训练，并进行一个双人极小极大博弈。优化目标公式如下：

|  | $\displaystyle\min_{G}\max_{D}V(D,G)=$ |  |
| --- | --- | --- |
|  | $\displaystyle\mathbb{E}_{\mathbf{x}\sim p_{\text{data}}(\mathbf{x})}[\log D(% \mathbf{x})]+\mathbb{E}_{\mathbf{z}\sim p_{\mathbf{z}}(\mathbf{z})}[\log(1-D(G% (\mathbf{z})))]$ |  |

其中 $D(\mathbf{x})$ 表示真实样本 $\mathbf{x}$ 是真实样本的概率，而 $D(G(\mathbf{z}))$ 表示生成样本是虚假样本的概率。$\mathbb{E}_{x}$ 是对所有样本的期望值。

#### 3.1.2 变分自编码器

变分自编码器 [[132](https://arxiv.org/html/2405.19334v2#bib.bib132)] 包含一个编码器和一个解码器，用于从输入数据中学习潜在表示，如图 [2](https://arxiv.org/html/2405.19334v2#S3.F2 "Figure 2 ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")第二行所示。

编码器是一个神经网络，将输入数据 $\mathbf{x}$ 映射到潜在空间变量 $\mathbf{z}$ 的分布。然后，变分后验分布 $q(\mathbf{z}|\mathbf{x})$ 通常被假设为高斯分布 $N(\mu,\sigma^{2})$。在这种情况下，编码器给出 $\mu$ 和 ${\sigma}^{2}$。

解码器将潜在空间变量 $\mathbf{z}$ 映射回输入空间 $\mathbf{x}^{\prime}$，得到生成数据 $x$ 的条件分布 $q(x|z)$。

VAE 的训练优化目标是最大化数据的边际对数似然的下界。通过随机梯度下降和重参数化技巧可以实现这一目标。这也被称为证据下界（ELBO）。具体来说，ELBO 可以写成以下形式：

|  | $\displaystyle\mathcal{L}(\theta;\mathbf{X})=$ |  |
| --- | --- | --- |
|  | $\displaystyle-\left[KL(q(\mathbf{z}&#124;\mathbf{x};\theta)&#124;&#124;p(\mathbf{z}))-\mathbb% {E}_{q(\mathbf{z}&#124;\mathbf{x};\theta)}[\log p(\mathbf{x}&#124;\mathbf{z};\theta)]\right]$ |  |

其中 $KL(\textperiodcentered||\textperiodcentered)$ 表示 KL 散度，它衡量编码器 $q(\mathbf{z}|\mathbf{x})$ 推断出的后验分布与先验分布 $p(z)$ 之间的差异。第二项是重构误差，它表示从 $z$ 生成的 $\mathbf{x^{\prime}}$ 与实际数据 $x$ 之间的匹配程度。

向量量化变分自编码器 VQ-VAE[[133](https://arxiv.org/html/2405.19334v2#bib.bib133)] 是变分自编码器（VAE）的一个变体，它引入了一个离散的潜在空间，与原始的 VAE 相比，显著提高了生成样本的质量。在 VQ-VAE 中，编码器将编码器的连续输出映射到预定义离散代码本中的最近点，并输出一个离散的潜在表示 $\mathbf{z}$。代码本与模型的其余参数一起学习。使用离散潜在空间允许 VQ-VAE 捕捉关于数据的更多全局和结构化信息，从而提高生成质量。

#### 3.1.3 基于流的模型

基于流的模型，也称为归一化流，是一种生成模型，已成功应用于各种任务，包括图像合成、变分推断和无监督表示学习。基于流的模型的架构由一系列可逆变换（或流）组成。每个流都由一个神经网络参数化，该网络学习将数据分布逐步转化为更简单的先验分布。训练基于流的模型的目标函数是模型下数据的负对数似然，由于流的可逆性，这可以准确计算。该函数表示为：

|  | $\displaystyle\mathcal{L}(\theta)=-\mathbb{E}_{\mathbf{x}\sim p_{\text{data}}(% \mathbf{x})}[\log p_{\text{model}}(\mathbf{x};\theta)]$ |  | (3) |
| --- | --- | --- | --- |

其中 $p_{\text{model}}(\mathbf{x};\theta)$ 是模型的概率密度函数。在实践中，基于流的模型中使用的变换通常选择易于逆转并具有易于计算的雅可比矩阵，例如仿射变换。

#### 3.1.4 扩散模型

扩散模型在[[134](https://arxiv.org/html/2405.19334v2#bib.bib134)]中提出，该文献首次给出了近期扩散模型的原型。然而，现代扩散模型的基础结构，它引发了生成范式的革命，最初在去噪扩散概率模型[[135](https://arxiv.org/html/2405.19334v2#bib.bib135)]中提出。它在训练和神秘改进方面都很优雅，仅引入了一个简单的回归损失。如图[2](https://arxiv.org/html/2405.19334v2#S3.F2 "Figure 2 ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")所示，扩散模型将复杂的工作转变为一系列去噪任务，主要包括两个步骤：将先验噪声注入数据和去噪预测。

正向噪声注入 在正向噪声注入过程中，模型在$T$步的每一步$t$中逐步将高斯噪声$\mathbf{\zeta_{t}}$引入数据。该过程可以表示如下：

|  | $\mathbf{x_{t+1}}=\sqrt{1-\alpha_{t}^{2}}x_{t}+\alpha_{t}\mathbf{\zeta_{t}}$ |  | (4) |
| --- | --- | --- | --- |

其中$\mathbf{x_{t}}$是时间$t$的数据，$\mathbf{\zeta_{t}}$是时间$t$的高斯噪声，$\mathbf{\alpha_{t}}$是一个噪声调度器，决定每一步添加的噪声量。噪声调度器$\mathbf{\alpha_{t}}$通常从接近 0 的值开始，并在$T$步中逐渐增加到 1。

每一步的噪声假设遵循马尔可夫过渡过程，这意味着时间$t$的噪声$\mathbf{\zeta_{t}}$与所有之前时间的噪声无关。这一假设简化了模型，使其易于训练。

反向去噪 在正向噪声注入后，模型旨在通过从噪声版本中预测原始数据来逆转这一过程。这是通过学习去噪函数实现的，该函数通常被参数化为深度神经网络。去噪函数输入时间$t$的噪声数据，并试图预测该步骤中添加的噪声。这个过程会对每个时间步进行，从$T$到 1 反向进行。去噪函数可以表示如下：

|  | $\mathbf{\hat{\zeta}_{t}}=D_{\theta}(\mathbf{x_{t}},t)$ |  | (5) |
| --- | --- | --- | --- |

其中$D_{\theta}$是由$\theta$参数化的去噪函数，$x_{t}$是时间$t$的噪声数据，而$\mathbf{\hat{\zeta}_{t}}$是预测的噪声。

模型在训练期间的目标是最小化预测噪声$\mathbf{\hat{\zeta}_{t}}$与正向过程中添加的实际噪声$\mathbf{\zeta_{t}}$之间的差异。这可以通过简单的均方误差损失来衡量。

训练模型以执行这种反向去噪预测使其能够生成类似于原始数据分布的数据，使扩散模型成为生成任务的强大工具。

#### 3.1.5 自回归模型

自回归模型是另一类广泛用于各种任务的生成模型，包括时间序列预测、语音合成和自然语言处理。它们的架构根据过去的值预测未来的值。

自回归模型的训练目标函数也是模型下数据的负对数似然，由于模型的序列性质，可以准确计算。其公式为：

|  | $\displaystyle\mathcal{L}(\theta)=-\mathbb{E}{\mathbf{x}\sim p_{\text{data}}(\mathbf{x})}[\log p_{\text{model}}(\mathbf{x_{t+1}} | \mathbf{x_{\leq t}};\theta)]$ |  | (6) |
| --- | --- | --- | --- | --- |

其中 $p_{\text{model}}(\mathbf{x_{t+1}}|\mathbf{x_{\leq t}};\theta)$ 是模型的条件概率密度函数。在实践中，模型的训练目标是最大化给定前一个值的序列中下一个值的可能性。

### 3.2 多模态对齐模型

CLIP [[24](https://arxiv.org/html/2405.19334v2#bib.bib24)] 是一种开创性的图像语言对齐模型，同时学习图像编码器和文本编码器，以在共享语义空间中生成视觉和文本表示，通过对比学习 [[136](https://arxiv.org/html/2405.19334v2#bib.bib136)] 进行训练。在大规模对比预训练后，它能够处理各种下游任务，包括细粒度对象识别、视频动作识别、面部情感识别、地理定位等，且以零样本方式完成。由于其网络规模的训练，它可以理解大量的语义。因此，它已成为各种视觉生成和编辑工作中最广泛使用的视觉和文本编码器之一，如 DALLE-2 [[137](https://arxiv.org/html/2405.19334v2#bib.bib137)] 和 LDM [[30](https://arxiv.org/html/2405.19334v2#bib.bib30)] 用于文本到图像生成，VideoCrafter [[19](https://arxiv.org/html/2405.19334v2#bib.bib19)] 用于文本到视频生成，CLIP-Nerf [[138](https://arxiv.org/html/2405.19334v2#bib.bib138)] 用于 3D。

除了文本和视觉对齐，CLAP [[139](https://arxiv.org/html/2405.19334v2#bib.bib139)] 对齐文本和音频信息。音频对齐的文本嵌入表示被用作 AudioLDM [[46](https://arxiv.org/html/2405.19334v2#bib.bib46)] 的条件，用于文本引导的音频生成。

CAVP 进一步推进了视频与音频对齐，它在 Diff-Foley [[140](https://arxiv.org/html/2405.19334v2#bib.bib140)] 中训练，用于视频到音频生成任务。在训练 CAVP 后，Diff-Foley 进一步训练一个潜在扩散模型，该模型基于音频对齐的视频表示来输出同步的音频信号。

与之前的配对模态对齐方法不同，ImageBind[[141](https://arxiv.org/html/2405.19334v2#bib.bib141)] 在一个共享的语义空间中对齐六种不同的模态。这些支持模态包括文本、图像、视频、音频、深度和热量。它已被用于多模态生成任务，如 Next-GPT [[142](https://arxiv.org/html/2405.19334v2#bib.bib142)]、Seeing-and-Hearing [[143](https://arxiv.org/html/2405.19334v2#bib.bib143)]，以及多模态理解工作，如 PandaGPT [[144](https://arxiv.org/html/2405.19334v2#bib.bib144)]。

### 3.3 大语言模型

现代的大语言模型利用 transformer 架构生成具有丰富上下文的嵌入。这些模型在大量文本语料库上进行训练，然后针对特定任务进行微调。它们通过预测序列中的下一个词来生成文本，前提是给定了前面的词。

典型的例子包括 LlaMA[[145](https://arxiv.org/html/2405.19334v2#bib.bib145)] 和 GPT[[146](https://arxiv.org/html/2405.19334v2#bib.bib146), [147](https://arxiv.org/html/2405.19334v2#bib.bib147), [148](https://arxiv.org/html/2405.19334v2#bib.bib148)]，这些是自回归模型，它们仅使用左侧上下文来进行预测。它们主要由 transformer 解码器构建。这些模型会在大量多样的数据集上进行预训练，以获取强大的语言理解和生成能力基础，然后在提供明确指令或指导的特定任务数据集上进行微调，例如问答总结或代码生成。此外，像 Chain-of-Thought (CoT) [[5](https://arxiv.org/html/2405.19334v2#bib.bib5)] 微调和 Reinforcement Learning from Human Feedback (RLHF) [[149](https://arxiv.org/html/2405.19334v2#bib.bib149)] 这样的技巧可以提升模型在特定任务上的能力。

### 3.4 多模态大语言模型

多模态大语言模型（MLLMs）是最近出现的模型，旨在赋予 LLM 理解或生成其他模态的能力。MLLMs 通常包括几个关键组件：用于特征提取的额外预训练模态特定编码器和用于将多模态隐藏特征与 LLM 主干对齐的输入投影器。对于具备生成能力的 MLLMs，它们通常包含额外的输出投影器和相应的模态生成器作为生成端点。将额外的预训练编码器用于对多模态信息进行编码到预训练 LLM，并训练模态对齐模块以实现这一点的一系列工作 [[150](https://arxiv.org/html/2405.19334v2#bib.bib150), [151](https://arxiv.org/html/2405.19334v2#bib.bib151), [142](https://arxiv.org/html/2405.19334v2#bib.bib142), [152](https://arxiv.org/html/2405.19334v2#bib.bib152), [153](https://arxiv.org/html/2405.19334v2#bib.bib153), [154](https://arxiv.org/html/2405.19334v2#bib.bib154)]。其他工作则以端到端的方式训练整个多模态系统 [[155](https://arxiv.org/html/2405.19334v2#bib.bib155)]。在接下来的章节中，我们将展示一系列最近的 MLLMs 工作，特别是多模态生成的 MLLMs。

![参见说明](img/9df2a699c179d7d103da938773675ba1.png)

图 3：图像生成的发展历程回顾。早期的图像生成工作主要集中于合成特定狭窄领域的图像，例如人脸或卧室 [[156](https://arxiv.org/html/2405.19334v2#bib.bib156), [157](https://arxiv.org/html/2405.19334v2#bib.bib157)]。随后，DALL-E [[158](https://arxiv.org/html/2405.19334v2#bib.bib158)] 和潜在扩散模型（LDM） [[30](https://arxiv.org/html/2405.19334v2#bib.bib30)] 已经进展到通过用户提示生成图像，并支持开放领域图像的合成。在最近两年，借助 LLMs 的支持，研究趋向于实现更加直观和互动的图像生成过程，例如通过对话进行迭代生成 [[159](https://arxiv.org/html/2405.19334v2#bib.bib159), [160](https://arxiv.org/html/2405.19334v2#bib.bib160)]。

表 I：使用 LLMs 进行基于语言的图像生成的现有方法概述。根据 LLMs 在此任务中的角色，这些方法可以分为四类：用于生成的多模态 LLMs、图像布局规划、提示合成与精炼以及图像质量评估。在“任务”栏中，“T”和“I”分别是“文本”和“图像”的缩写，而“Any”代表支持文本、图像、视频和音频模态的通用生成。“-”表示在官方论文中没有提供相关信息。

| 方法 | 场所 | 任务 | LLM | 生成模型 | 训练成本 |
| --- | --- | --- | --- | --- | --- |
| 多模态 LLMs 与图像生成 |
| FROMAGe [[161](https://arxiv.org/html/2405.19334v2#bib.bib161)] | ICML 2023 | TI$\rightarrow$TI | OPT | 检索 | 1$\times$A6000, 24 小时 |
| GILL [[162](https://arxiv.org/html/2405.19334v2#bib.bib162)] | NeurIPS 2023 | TI$\rightarrow$TI | OPT | 检索/SD | 2$\times$A6000, 48 小时 |
| SPAE [[163](https://arxiv.org/html/2405.19334v2#bib.bib163)] | NeurIPS 2023 | 分词 | PaLM2/GPT-3.5 | CNN | - |
| Emu [[155](https://arxiv.org/html/2405.19334v2#bib.bib155)] | ICLR 2024 | TI$\rightarrow$TI | LLaMa | SD | - |
| SEED [[58](https://arxiv.org/html/2405.19334v2#bib.bib58)] | ICLR 2024 | 分词 | OPT | SD | 64$\times$V100, 44 小时 |
| CM3Leon [[164](https://arxiv.org/html/2405.19334v2#bib.bib164)] | arXiv 2023 | TI$\rightarrow$I, I$\rightarrow$T | CM3Leon | CM3Leon | 64$\times$A100 |
| NExT-GPT [[142](https://arxiv.org/html/2405.19334v2#bib.bib142)] | arXiv 2023 | Any$\rightarrow$Any | Vicuna | SD 等 | - |
| DreamLLM [[159](https://arxiv.org/html/2405.19334v2#bib.bib159)] | ICLR 2024 | TI$\rightarrow$TI | Vicuna | SD | 128$\times$A800, 17.5 小时 |
| MiniGPT-5 [[165](https://arxiv.org/html/2405.19334v2#bib.bib165)] | arXiv 2023 | TI$\rightarrow$TI | Vicuna | SD | 4$\times$A6000 |
| OpenLEAF [[166](https://arxiv.org/html/2405.19334v2#bib.bib166)] | arXiv 2023 | T$\rightarrow$TI | GPT-4 | SDXL | 无需训练 |
| Mini-DALLE3 [[59](https://arxiv.org/html/2405.19334v2#bib.bib59)] | arXiv 2023 | TI$\rightarrow$TI | GPT-3.5/GPT-4 等 | SD-XL/DALLE-3 等 | 无需训练 |
| EasyGen [[63](https://arxiv.org/html/2405.19334v2#bib.bib63)] | arXiv 2023 | I$\rightarrow$T,T$\rightarrow$I | FlanT5XL/Vicuna | BiDiffuser | 120$\times$A100 小时 |
| TEAL [[167](https://arxiv.org/html/2405.19334v2#bib.bib167)] | arXiv 2023 | Any$\rightarrow$Any | LLaMa-Adapter | VQGAN | 8$\times$A100 |
| LLMGA [[168](https://arxiv.org/html/2405.19334v2#bib.bib168)] | arXiv 2024 | T$\rightarrow$I | LLaVA-1.5 | SD | - |
| ChatIllusion [[169](https://arxiv.org/html/2405.19334v2#bib.bib169)] | arXiv 2023 | TI$\rightarrow$TI | LLaMa-AdapterV2 | SDXL | 4$\times$A6000, 80 小时 |
| CoDi-2 [[60](https://arxiv.org/html/2405.19334v2#bib.bib60)] | CVPR 2024 | Any$\rightarrow$Any | Llama 2 | SD | - |
| CAFE [[170](https://arxiv.org/html/2405.19334v2#bib.bib170)] | CVPR 2024 | T$\rightarrow$I | Llama 2 | SD | 10000$\times$A100 小时 |
| StoryGPT-V [[171](https://arxiv.org/html/2405.19334v2#bib.bib171)] | arXiv 2024 | 故事生成 | OPT/Llama2 | Char-LDM | - |
| ELLA [[172](https://arxiv.org/html/2405.19334v2#bib.bib172)] | arXiv 2024 | T$\rightarrow$I | Llama 2 | SDXL | 1344$\times$A100 小时 |
| Lavi-Bridge [[173](https://arxiv.org/html/2405.19334v2#bib.bib173)] | arXiv 2024 | T$\rightarrow$I | Llama 2 | SD/PixArt-$\alpha$ | 8$\times$A100, 48 小时 |
| 图像布局规划 |
| LMD [[65](https://arxiv.org/html/2405.19334v2#bib.bib65)] | TMLR 2024 | T$\rightarrow$I | GPT-3.5/GPT-4 | SD | 无需训练 |
| LayoutGPT [[66](https://arxiv.org/html/2405.19334v2#bib.bib66)] | NeurIPS 2023 | T$\rightarrow$I | GPT-3.5/GPT-4/Codex | GLIGEN/SD | - |
| VP-GEN [[174](https://arxiv.org/html/2405.19334v2#bib.bib174)] | NeurIPS 2023 | T$\rightarrow$I | Vicuna | GLIGEN/SD | 4$\times$A6000，48 小时 |
| Control-GPT [[67](https://arxiv.org/html/2405.19334v2#bib.bib67)] | arXiv 2023 | T$\rightarrow$I | GPT-4 | ControlNet/SD | - |
| LayoutLLM-T2I [[68](https://arxiv.org/html/2405.19334v2#bib.bib68)] | MM 2023 | T$\rightarrow$I | GPT-3.5 | GLIGEN/SD | - |
| LLM Blueprint [[175](https://arxiv.org/html/2405.19334v2#bib.bib175)] | ICLR 2024 | T$\rightarrow$I | GPT-3.5 | LMD | 1$\times$A100 |
| SLD [[176](https://arxiv.org/html/2405.19334v2#bib.bib176)] | CVPR 2024 | T$\rightarrow$I | GPT-4 | DALLE3/SD | 无需训练 |
| TextDiffuser-2 [[177](https://arxiv.org/html/2405.19334v2#bib.bib177)] | arXiv 2023 | T$\rightarrow$I | Vicuna | SD | 8$\times$A100，168 小时 |
| COLE [[178](https://arxiv.org/html/2405.19334v2#bib.bib178)] | arXiv 2023 | T$\rightarrow$I | Llama 2/LLaVA | IF | - |
| 提示生成与优化 |
| SUR-Adapter [[179](https://arxiv.org/html/2405.19334v2#bib.bib179)] | MM 2023 | T$\rightarrow$I | LLaMa | SD | - |
| ChatGenImage [[180](https://arxiv.org/html/2405.19334v2#bib.bib180)] | arXiv 2023 | 数据合成 | GPT-3.5 | SD | 1$\times$GTX3090 |
| SwitchGPT [[181](https://arxiv.org/html/2405.19334v2#bib.bib181)] | arXiv 2023 | T$\rightarrow$TI | Llama 2/GPT-3.5 | SD | 4$\times$A100，3 小时 |
| TIAC [[182](https://arxiv.org/html/2405.19334v2#bib.bib182)] | arXiv 2023 | T$\rightarrow$I | GPT-3.5 | SD | - |
| Idea2Img [[183](https://arxiv.org/html/2405.19334v2#bib.bib183)] | arXiv 2023 | T$\rightarrow$I | GPT-4V | IF/SD | 无需训练 |
| WordArt Designer [[184](https://arxiv.org/html/2405.19334v2#bib.bib184)] | EMNLP 2023 | T$\rightarrow$I | GPT-3.5 | ControlNet | 1$\times$V100 |
| 图像质量评估 |
| DreamSync [[185](https://arxiv.org/html/2405.19334v2#bib.bib185)] | arXiv 2023 | T$\rightarrow$I | PaLM2/TIFA | SD-XL | - |
| LLMScore [[186](https://arxiv.org/html/2405.19334v2#bib.bib186)] | NeurIPS 2023 | T$\rightarrow$I | GPT-4 | SD | - |

表 II: 可用于基于语言的图像生成的图像-语言数据集。

| 名称 | 日期 | 场所 | 机构 | 领域 | 来源 | #图像 | 标题 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Im2Text [[187](https://arxiv.org/html/2405.19334v2#bib.bib187)] | 2011 年 12 月 12 日 | NeurIPS 2011 | SBU | Open | Internet | 1M | 手动 |
| Microsoft-COCO [[188](https://arxiv.org/html/2405.19334v2#bib.bib188)] | 2014 年 5 月 1 日 | ECCV 2014 | Microsoft | 常见物体 | Internet | 328K | 手动 |
| ALIGN [[189](https://arxiv.org/html/2405.19334v2#bib.bib189)] | 2021 年 2 月 11 日 | ICML 2021 | Google | Open | Internet | 1.8B | 手动 |
| Conceptual 12M [[190](https://arxiv.org/html/2405.19334v2#bib.bib190)] | 2021 年 2 月 17 日 | CVPR 2021 | Google | Open | Internet | 12M | 手动 |
| WIT [[191](https://arxiv.org/html/2405.19334v2#bib.bib191)] | 2021 年 3 月 2 日 | SIGIR 2021 | Google | 开放 | 维基百科 | 11.5M | 手工 |
| LAION-400M [[192](https://arxiv.org/html/2405.19334v2#bib.bib192)] | 2021 年 11 月 3 日 | NeurIPS 2021 | LAION | 开放 | 互联网 | 400M | 手工 |
| LAION-FACE [[193](https://arxiv.org/html/2405.19334v2#bib.bib193)] | 2021 年 12 月 6 日 | CVPR 2022 | Microsoft | 面部 | LAION | 20M | 手工 |
| M3W [[194](https://arxiv.org/html/2405.19334v2#bib.bib194)] | 2022 年 4 月 29 日 | NeurIPS 2022 | Deepmind | 交错 | 互联网 | 43M | 手工 |
| LAION-COCO [[195](https://arxiv.org/html/2405.19334v2#bib.bib195)] | 2022 年 9 月 15 日 | - | LAION | 开放 | LAION | 600M | 合成 |
| LAION-5B [[196](https://arxiv.org/html/2405.19334v2#bib.bib196)] | 2022 年 10 月 16 日 | NeurIPS 2022 | LAION | 开放 | 互联网 | 5B | 手工 |
| Coyo-700M [[197](https://arxiv.org/html/2405.19334v2#bib.bib197)] | 2022 年 8 月 31 日 | - | Kakao Brain | 开放 | 互联网 | 700M | 手工 |
| KOSMOS-1 [[198](https://arxiv.org/html/2405.19334v2#bib.bib198)] | 2023 年 2 月 27 日 | NeurIPS 2023 | Microsoft | 交错 | 互联网 | 355M | 手工 |
| Multimodal C4 [[199](https://arxiv.org/html/2405.19334v2#bib.bib199)] | 2023 年 4 月 14 日 | NeurIPS 2023 | UCSB | 交错 | 互联网 | 571M | 手工 |
| LLaVA-instruct [[200](https://arxiv.org/html/2405.19334v2#bib.bib200)] | 2023 年 4 月 17 日 | NeurIPS 2023 | UWM | 指令 | COCO | 150k | 合成 |
| DATACOMP [[201](https://arxiv.org/html/2405.19334v2#bib.bib201)] | 2023 年 4 月 27 日 | NeurIPS 2023 | DATACOMP | 开放 | 互联网 | 12.8B | 手工 |
| MARIO-10M [[202](https://arxiv.org/html/2405.19334v2#bib.bib202)] | 2023 年 5 月 19 日 | NeurIPS 2023 | Microsoft | 图像内文本 | LAION, TMDB, OpenLibrary | 10M | 手工 |
| LAION-Glyph [[203](https://arxiv.org/html/2405.19334v2#bib.bib203)] | 2023 年 5 月 29 日 | NeurIPS 2023 | Microsoft | 图像内文本 | LAION | 10M | 手工 |

| MIMIC-IT [[204](https://arxiv.org/html/2405.19334v2#bib.bib204)] | 2023 年 6 月 8 日 | arXiv 2023 | NTU | 交错 | 互联网 | 2.8M | 合成 | ![参见说明](img/108b5a9e624cd3f5387c15d4f5350ff6.png)

图 4：集成图像理解和生成能力的通用管道 [[62](https://arxiv.org/html/2405.19334v2#bib.bib62), [58](https://arxiv.org/html/2405.19334v2#bib.bib58), [159](https://arxiv.org/html/2405.19334v2#bib.bib159), [61](https://arxiv.org/html/2405.19334v2#bib.bib61)]。在推理阶段，用户可以输入交错的多模态数据（例如，文本和图像）。图像标记器将信息处理为图像标记，并将其输入到 LLM 中。LLM 输出图像标记，然后将其解码为文本响应和图像。

![参见说明](img/ebb17c4cc7cc9df00a33d741a1bf8410.png)

图 5： (a) 标准文本到图像（T2I）[[205](https://arxiv.org/html/2405.19334v2#bib.bib205), [30](https://arxiv.org/html/2405.19334v2#bib.bib30)]，(b) 使用 LLM 作为布局规划器的 T2I [[66](https://arxiv.org/html/2405.19334v2#bib.bib66), [68](https://arxiv.org/html/2405.19334v2#bib.bib68), [64](https://arxiv.org/html/2405.19334v2#bib.bib64), [65](https://arxiv.org/html/2405.19334v2#bib.bib65), [174](https://arxiv.org/html/2405.19334v2#bib.bib174), [67](https://arxiv.org/html/2405.19334v2#bib.bib67), [175](https://arxiv.org/html/2405.19334v2#bib.bib175)]，以及 (c) 用于布局建议的 LLM 的 T2I [[178](https://arxiv.org/html/2405.19334v2#bib.bib178), [176](https://arxiv.org/html/2405.19334v2#bib.bib176)]。

## 4 图像生成与编辑

### 4.1 图像生成

图像生成一直是计算机视觉领域的基础任务，在数字艺术、娱乐、教育和通信等各种应用中发挥着重要作用[[206](https://arxiv.org/html/2405.19334v2#bib.bib206), [207](https://arxiv.org/html/2405.19334v2#bib.bib207), [208](https://arxiv.org/html/2405.19334v2#bib.bib208)]。在图像生成的初期阶段，生成的内容通常限于特定类别，例如人脸、猫或建筑。近年来，由于引入了文本引导和开放领域生成，图像生成的进展尤为显著。最近，LLMs 的强大功能将图像生成提升到了一个新的水平，使得生成过程变得互动或交替。在图 [3](https://arxiv.org/html/2405.19334v2#S3.F3 "Figure 3 ‣ 3.4 Multimodal Large Language Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey") 中，我们详细总结了图像生成的历史和发展轨迹。最近的图像生成方法的精选列表展示在表 [I](https://arxiv.org/html/2405.19334v2#S3.T1 "TABLE I ‣ 3.4 Multimodal Large Language Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey") 中。我们还在表 [II](https://arxiv.org/html/2405.19334v2#S3.T2 "TABLE II ‣ 3.4 Multimodal Large Language Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey") 中列出了图像生成的代表性数据集。这些工作使得生成的图像能够与文本提示紧密对齐，为创意的可视化提供了强大的工具。

#### 4.1.1 基于文本引导的图像生成与 CLIP

之前，图像-文本对齐模型的采用，例如 CLIP [[24](https://arxiv.org/html/2405.19334v2#bib.bib24)]，在文本指导的图像生成的发展中发挥了关键作用 [[137](https://arxiv.org/html/2405.19334v2#bib.bib137), [177](https://arxiv.org/html/2405.19334v2#bib.bib177), [209](https://arxiv.org/html/2405.19334v2#bib.bib209), [30](https://arxiv.org/html/2405.19334v2#bib.bib30), [210](https://arxiv.org/html/2405.19334v2#bib.bib210), [211](https://arxiv.org/html/2405.19334v2#bib.bib211)]。CLIP 文本编码器的对齐能力确保生成的图像与给定的文本提示对齐，产生准确符合预期描述的图像，包括所需的对象、场景或属性。鉴于 CLIP 在生成逼真图像方面取得的重大进展，自然会问：更强大的 LLM 是否会进一步促进图像生成领域的发展？

值得一提的是，LLMs 在图像领域的应用已被广泛研究，特别是在图像理解方面。LLMs 可以有效地作为视觉标记和语言标记的统一处理器[[212](https://arxiv.org/html/2405.19334v2#bib.bib212), [213](https://arxiv.org/html/2405.19334v2#bib.bib213), [214](https://arxiv.org/html/2405.19334v2#bib.bib214), [215](https://arxiv.org/html/2405.19334v2#bib.bib215), [216](https://arxiv.org/html/2405.19334v2#bib.bib216), [150](https://arxiv.org/html/2405.19334v2#bib.bib150), [217](https://arxiv.org/html/2405.19334v2#bib.bib217), [218](https://arxiv.org/html/2405.19334v2#bib.bib218), [9](https://arxiv.org/html/2405.19334v2#bib.bib9), [219](https://arxiv.org/html/2405.19334v2#bib.bib219), [220](https://arxiv.org/html/2405.19334v2#bib.bib220), [221](https://arxiv.org/html/2405.19334v2#bib.bib221), [142](https://arxiv.org/html/2405.19334v2#bib.bib142), [222](https://arxiv.org/html/2405.19334v2#bib.bib222), [8](https://arxiv.org/html/2405.19334v2#bib.bib8), [223](https://arxiv.org/html/2405.19334v2#bib.bib223), [224](https://arxiv.org/html/2405.19334v2#bib.bib224), [225](https://arxiv.org/html/2405.19334v2#bib.bib225)], 工具协调员[[116](https://arxiv.org/html/2405.19334v2#bib.bib116), [105](https://arxiv.org/html/2405.19334v2#bib.bib105), [117](https://arxiv.org/html/2405.19334v2#bib.bib117), [226](https://arxiv.org/html/2405.19334v2#bib.bib226)], 或上游视觉模型输出的分析师[[227](https://arxiv.org/html/2405.19334v2#bib.bib227), [228](https://arxiv.org/html/2405.19334v2#bib.bib228), [229](https://arxiv.org/html/2405.19334v2#bib.bib229)]。受这些工作的启发，许多研究进一步利用 LLMs 进行图像生成，里程碑式的工作如图[3](https://arxiv.org/html/2405.19334v2#S3.F3 "图 3 ‣ 3.4 多模态大语言模型 ‣ 3 初步知识 ‣ LLMs 遇见多模态生成与编辑：综述")所示。接下来，我们将介绍 LLMs 出现后图像生成任务取得的进展。

#### 4.1.2 基于文本指导的图像生成与 LLMs

如图[4](https://arxiv.org/html/2405.19334v2#S3.F4 "Figure 4 ‣ 3.4 Multimodal Large Language Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")所示，MLLMs 已经成为 LLMs 的一个变革性扩展，解决了 LLMs 在处理视觉内容方面的固有限制。虽然 LLMs 在灵活的文本互动方面表现出色，但它们局限于文本输入和输出。MLLMs 的引入源于弥合这一差距的必要性，使语言模型能够理解和生成图像。MLLMs 提供了双重优势：首先，它们作为一个统一的接口来理解和生成文本和视觉信息，为用户提供语言和图像的无缝集成。其次，MLLMs 引入了交互式生成能力，允许用户发送命令以迭代地修改图像内容。这一交互过程赋予用户更大的控制权，提升了用户体验和对用户期望内容的可控性。

具体来说，CM3Leon [[164](https://arxiv.org/html/2405.19334v2#bib.bib164)] 是一个自回归的 MLLMs，旨在同时生成文本和图像输出。它在仅解码器、检索增强、基于令牌的框架内运行，提供了一种独特的多模态语言处理方法。DreamLLM [[159](https://arxiv.org/html/2405.19334v2#bib.bib159)] 展示了首个能够生成自由格式交错内容的 MLLM，支持多轮对话，并在图像字幕生成和视频问答（VQA）中取得了显著的结果，无需微调。整个框架在真正的端到端方式下对交错的多模态内容进行训练。SEED-LLaMA [[61](https://arxiv.org/html/2405.19334v2#bib.bib61)]，类似于 DreamLLM，使 LLMs 理解多模态指令，并支持多轮上下文中的图像和文本生成。特别是，SEED-LLaMA 强调了图像令牌器的设计，提出了其功能的两个关键设计原则。MiniGPT-5 [[165](https://arxiv.org/html/2405.19334v2#bib.bib165)] 将视觉令牌（称为 ”voken”）引入传统的 LLMs，使其能够生成图像。提出了一个两阶段训练流程，包括单模态对齐阶段和多模态学习阶段，使 LLMs 能够有机地生成文本和图像。OpenLeaf [[166](https://arxiv.org/html/2405.19334v2#bib.bib166)] 利用对 LLMs 的提示生成交错的文本和视觉数据，产生实体和风格一致的图像和文本。它支持各种任务，如如何提问回答、讲故事、图形故事重写和网页/海报生成。EasyGen [[63](https://arxiv.org/html/2405.19334v2#bib.bib63)] 利用双向条件扩散模型 BiDiffuser，赋予 LLMs 多模态理解和生成能力。与以前的 CLIP 基于的方法不同，EasyGen 基于该模型生成图像。TEAL [[167](https://arxiv.org/html/2405.19334v2#bib.bib167)] 使用现有的令牌化工具处理不同的模态，并将获得的令牌转化为联合嵌入空间，使得冻结的 LLMs 能够理解和生成各种模态的数据，包括文本、图像和音频。ChatIllusion [[169](https://arxiv.org/html/2405.19334v2#bib.bib169)] 引入了 Genadapter 和 LLaMa-AdapterV2，以桥接 SD XL 的隐藏嵌入空间，使 LLMs 能够理解视觉指令并生成交错的图像和文本，支持图像生成、编辑和讲故事。Emu2 [[62](https://arxiv.org/html/2405.19334v2#bib.bib62)] 强调了 MLLMs 的上下文学习能力，通过扩大模型规模和统一的自回归训练展示了改进的性能。它支持视觉提示和对象基础生成等任务，在问答基准测试和开端主题驱动生成后获得了最先进的结果。ELLA [[172](https://arxiv.org/html/2405.19334v2#bib.bib172)] 和 Lavi-Bridge [[173](https://arxiv.org/html/2405.19334v2#bib.bib173)] 通过训练若干轻量级适配器，将大型语言模型纳入 T$\rightarrow$I 生成架构。LLMGA [[168](https://arxiv.org/html/2405.19334v2#bib.bib168)] 利用 LLaVA 同时对图像和指令进行编码，使得基于稳定扩散操作图像。StoryGPT-V [[171](https://arxiv.org/html/2405.19334v2#bib.bib171)] 利用 LLM 实现连贯的故事脚本生成。

#### 4.1.3 通过 LLMs 进行图像布局规划

尽管 T$\rightarrow$I 生成技术迅速发展，但仍有若干具有挑战性的问题尚未完全解决，包括文本渲染、空间关系和数量表示。在这种情况下，一些方法试图利用 LLMs 进行布局规划，然后根据获得的布局生成图像，如图[5](https://arxiv.org/html/2405.19334v2#S3.F5 "Figure 5 ‣ 3.4 Multimodal Large Language Models ‣ 3 Preliminaries ‣ LLMs Meet Multimodal Generation and Editing: A Survey")所示。LayoutGPT [[66](https://arxiv.org/html/2405.19334v2#bib.bib66)]利用 LLMs 固有的推理能力通过上下文演示来促进布局生成。它使用 GPT3.5/4 将用户提示转换为 CSS 风格的输出布局，其中指定了每个对象的位置。LMD [[65](https://arxiv.org/html/2405.19334v2#bib.bib65)]通过增强提示理解能力改进了 T$\rightarrow$I 扩散模型。它采用两阶段方法，利用预训练语言模型生成场景布局并指导图像生成。VP-GEN [[174](https://arxiv.org/html/2405.19334v2#bib.bib174)]将 T2I 任务拆分为对象/计数生成、布局生成和图像生成步骤。通过利用基于文本-布局对的微调 GPT-3.5-Turbo，VPGEN 实现了比端到端模型更好的空间控制。Control-GPT [[67](https://arxiv.org/html/2405.19334v2#bib.bib67)]利用 GPT-4 输出 TikZ 代码，根据文本描述构建草图布局。LayoutLLM-T2I [[68](https://arxiv.org/html/2405.19334v2#bib.bib68)]利用 ChatGPT 根据用户提示诱导布局。然后，使用提示编码器模块分别建模文本提示、关系三元组和诱导的布局。为了高效整合布局信息，介绍了一种基于 UNet 的布局感知空间变换器。LLM Blueprint [[175](https://arxiv.org/html/2405.19334v2#bib.bib175)]利用 ChatGPT 生成详细的对象描述、边界框布局以及背景提示。随后，进行迭代修正操作，以根据布局纠正区域错误。SLD [[176](https://arxiv.org/html/2405.19334v2#bib.bib176)]通过从输入提示迭代生成图像并使用基于 LLM 的布局规划器纠正错误来改进 T$\rightarrow$I 生成。特别是，布局规划器可以添加、删除或调整对象框，以帮助 T2I 模型生成更准确的图像。TextDiffuser-2 [[64](https://arxiv.org/html/2405.19334v2#bib.bib64)]使用 Vicuna-7B-1.5 进行布局规划，根据用户提供的提示生成待渲染文本的位置和内容。COLE [[178](https://arxiv.org/html/2405.19334v2#bib.bib178)]利用大型语言模型将用户提示转化为详细的 JSON 文件。这些文件包含添加文本的规格，如内容、位置和风格。

#### 4.1.4 通过 LLMs 进行提示合成和优化

LLMs 可以被视为一个巨大的知识库。一些方法[[180](https://arxiv.org/html/2405.19334v2#bib.bib180), [183](https://arxiv.org/html/2405.19334v2#bib.bib183), [182](https://arxiv.org/html/2405.19334v2#bib.bib182), [184](https://arxiv.org/html/2405.19334v2#bib.bib184)] 探索了利用 LLMs 来合成或优化提示，从而指导 T$\rightarrow$I (T2I) 模型生成内容丰富且细致的图像。例如，ChatGenImage [[180](https://arxiv.org/html/2405.19334v2#bib.bib180)] 利用 ChatGPT 生成提示，引导 AIGC 模型生成初步图像。随后，它通过结合自动生成的详细注释作为局部约束提示，迭代地优化这些提示，生成多样而复杂的场景。受三层艺术理论的启发，TIAC [[182](https://arxiv.org/html/2405.19334v2#bib.bib182)] 和 WordArt Designer [[184](https://arxiv.org/html/2405.19334v2#bib.bib184)] 使用 LLMs 将抽象概念转化为语义相关的物理对象，使得下游 T$\rightarrow$I 模型更容易处理。Idea2Img [[183](https://arxiv.org/html/2405.19334v2#bib.bib183)] 采用多模态 LLM 来评估 T$\rightarrow$I 模型生成的图像。随后，根据获得的反馈，该框架迭代优化初始提示，以生成令人满意的结果。DiffusionGPT [[230](https://arxiv.org/html/2405.19334v2#bib.bib230)] 利用 LLMs 来优化图像生成的提示。通过解析多样的提示并利用特定领域的 Trees-of-Thought，该模型选择最合适的生成模型来生成高质量的图像。RPG [[231](https://arxiv.org/html/2405.19334v2#bib.bib231)] 是一个无需训练的 T$\rightarrow$I 生成框架。它利用多模态 LLMs 来优化原始提示，将复杂提示分解为子区域任务，在物体组合和文本-图像对齐方面表现出色。SUR-adapter [[179](https://arxiv.org/html/2405.19334v2#bib.bib179)] 利用 LLMs 改善其语义理解和推理能力，使其能够为 T$\rightarrow$I 生成创建更好的文本语义表示。SwitchGPT [[181](https://arxiv.org/html/2405.19334v2#bib.bib181)] 引入了一种创新的框架，使传统的 LLMs，如 GPT，能够解读给定指令的潜在意图，从而生成更合适的响应非文本输出。

#### 4.1.5 通过 LLMs 进行图像质量评估

一些研究集中在使用大型语言模型来评估生成图像的质量。例如，DreamSync [[185](https://arxiv.org/html/2405.19334v2#bib.bib185)] 利用两个视觉语言模型（VLMs）来评估生成的结果，并选择最佳生成图像：一个用于文本对齐，另一个用于美学质量。然后使用 LoRA [[232](https://arxiv.org/html/2405.19334v2#bib.bib232)] 迭代地微调 T2I 模型，以达到所选的最佳生成效果。LLMScore [[186](https://arxiv.org/html/2405.19334v2#bib.bib186)] 将图像转换为图像级别和对象级别的视觉描述。随后，给定一组指令给 LLMs，以检查图像与描述之间的匹配程度。最后，生成一个带有理由的评分。

### 4.2 图像编辑

图像编辑是与生成密切相关的任务，因此随着图像生成模型的发展，图像编辑也取得了显著的进展。最近图像编辑方法的精选列表见表[III](https://arxiv.org/html/2405.19334v2#S4.T3 "TABLE III ‣ 4.2.1 Image Editing with CLIP/T5 ‣ 4.2 Image Editing ‣ 4 Image Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")。

#### 4.2.1 使用 CLIP/T5 的图像编辑

CLIP 模型使基于语言的图像编辑成为可能[[233](https://arxiv.org/html/2405.19334v2#bib.bib233), [234](https://arxiv.org/html/2405.19334v2#bib.bib234), [235](https://arxiv.org/html/2405.19334v2#bib.bib235), [236](https://arxiv.org/html/2405.19334v2#bib.bib236), [237](https://arxiv.org/html/2405.19334v2#bib.bib237), [238](https://arxiv.org/html/2405.19334v2#bib.bib238), [239](https://arxiv.org/html/2405.19334v2#bib.bib239), [240](https://arxiv.org/html/2405.19334v2#bib.bib240), [241](https://arxiv.org/html/2405.19334v2#bib.bib241), [242](https://arxiv.org/html/2405.19334v2#bib.bib242), [243](https://arxiv.org/html/2405.19334v2#bib.bib243), [244](https://arxiv.org/html/2405.19334v2#bib.bib244), [245](https://arxiv.org/html/2405.19334v2#bib.bib245), [246](https://arxiv.org/html/2405.19334v2#bib.bib246)]。PAIR-Diffusion [[243](https://arxiv.org/html/2405.19334v2#bib.bib243)] 识别出结构和外观是图像编辑中最直观的两个方面。因此，PAIR-Diffusion 使用从训练图像中显式提取的结构和外观信息进行训练，这使得在推理过程中可以分别编辑结构和外观。另一类工作[[238](https://arxiv.org/html/2405.19334v2#bib.bib238), [241](https://arxiv.org/html/2405.19334v2#bib.bib241)] 通过轻微调整预训练的扩散模型来编辑目标图像，而不是依赖于大规模数据集上扩散模型的繁重训练过程。Imagic [[238](https://arxiv.org/html/2405.19334v2#bib.bib238)] 提出了一个通用的基于文本的图像编辑模型。值得注意的是，Imagic 不依赖于源提示，通过优化目标提示嵌入来实现。之后，整个扩散模型被微调以提高重建性能。编辑能力通过插值优化后的提示嵌入和目标提示嵌入来实现。还有许多无需调优的方法用于文本引导的图像编辑[[233](https://arxiv.org/html/2405.19334v2#bib.bib233), [234](https://arxiv.org/html/2405.19334v2#bib.bib234), [235](https://arxiv.org/html/2405.19334v2#bib.bib235), [236](https://arxiv.org/html/2405.19334v2#bib.bib236), [237](https://arxiv.org/html/2405.19334v2#bib.bib237), [239](https://arxiv.org/html/2405.19334v2#bib.bib239), [240](https://arxiv.org/html/2405.19334v2#bib.bib240), [242](https://arxiv.org/html/2405.19334v2#bib.bib242), [244](https://arxiv.org/html/2405.19334v2#bib.bib244), [245](https://arxiv.org/html/2405.19334v2#bib.bib245), [246](https://arxiv.org/html/2405.19334v2#bib.bib246)]。SDEdit [[233](https://arxiv.org/html/2405.19334v2#bib.bib233)] 可以从用户输入的笔画、草图或遮罩生成逼真的图像，并根据文本指令编辑现有图像。它的工作原理是先向目标图像添加噪声，然后通过文本指令逐渐去噪。去噪过程由一个基于大规模图像数据集训练的扩散模型生成先验引导。根据人类感知研究，SDEdit 在多个图像合成和编辑任务中超越了最先进的基于 GAN 的方法。其他无需调优的方法[[242](https://arxiv.org/html/2405.19334v2#bib.bib242), [244](https://arxiv.org/html/2405.19334v2#bib.bib244), [236](https://arxiv.org/html/2405.19334v2#bib.bib236), [239](https://arxiv.org/html/2405.19334v2#bib.bib239)] 通过对潜在变量、交叉注意力图或 UNet 特征进行正则化或操控来实现文本引导的编辑。然而，大多数文本引导的图像编辑工作依赖于 CLIP 模型，其能力限制了编辑到简单的文本提示，无法理解复杂的人类指令。

表 III: 基于 CLIP 和 LLM 的语言驱动图像编辑方法概述。我们总结了涉及的 LLM 和生成模型，以及方法是否需要训练。

| 方法 | 会议 | LLM | 生成模型 | 训练 |
| --- | --- | --- | --- | --- |
| CLIP 用于图像编辑 |
| SDEdit [[233](https://arxiv.org/html/2405.19334v2#bib.bib233)] | ICLR 2022 | - | DDPM | ✗ |
| DiffusionCLIP [[234](https://arxiv.org/html/2405.19334v2#bib.bib234)] | CVPR 2022 | - | DDPM | ✗ |
| P2P [[236](https://arxiv.org/html/2405.19334v2#bib.bib236)] | ICLR 2023 | - | Imagen&SD | ✗ |
| NTI [[237](https://arxiv.org/html/2405.19334v2#bib.bib237)] | ICLR 2023 | - | SD | ✗ |
| Imagic [[238](https://arxiv.org/html/2405.19334v2#bib.bib238)] | CVPR 2023 | - | Imagen | ✓ |
| PaP [[239](https://arxiv.org/html/2405.19334v2#bib.bib239)] | CVPR 2023 | - | SD | ✗ |
| SINE [[241](https://arxiv.org/html/2405.19334v2#bib.bib241)] | CVPR 2023 | - | SD | ✓ |
| pix2pix-zero [[242](https://arxiv.org/html/2405.19334v2#bib.bib242)] | SIGGRAPH 2023 | - | SD | ✗ |
| PAIR-Diffusion [[243](https://arxiv.org/html/2405.19334v2#bib.bib243)] | arXiv 2023 | - | PAIR-Diffusion | ✓ |
| MasaCtrl [[244](https://arxiv.org/html/2405.19334v2#bib.bib244)] | SIGGRAPH 2023 | - | SD | ✗ |
| Dragondiffusion [[247](https://arxiv.org/html/2405.19334v2#bib.bib247)] | ICLR 2024 | - | SD | ✓ |
| DiffEditor [[248](https://arxiv.org/html/2405.19334v2#bib.bib248)] | CVPR 2024 | - | SD | ✓ |
| LLMs 用于图像编辑 |
| InstructPix2Pix [[249](https://arxiv.org/html/2405.19334v2#bib.bib249)] | CVPR 2023 | GPT-3 | SD | ✓ |
| VisualChatGPT [[116](https://arxiv.org/html/2405.19334v2#bib.bib116)] | arXiv 2023 | GPT-3 | SD | ✓ |
| CHATEDIT [[250](https://arxiv.org/html/2405.19334v2#bib.bib250)] | EMNLP 2023 | GPT-3 | StyleGAN | ✓ |
| MGIE [[251](https://arxiv.org/html/2405.19334v2#bib.bib251)] | ICLR 2024 | LLaVA-7B | SD | ✓ |
| Emu Edit [[252](https://arxiv.org/html/2405.19334v2#bib.bib252)] | arXiv 2023 | Llama 2-70B | Emu | ✓ |
| SLD [[176](https://arxiv.org/html/2405.19334v2#bib.bib176)] | CVPR 2024 | GPT-4 | DALL-E 3 | ✓ |
| SmartEdit [[253](https://arxiv.org/html/2405.19334v2#bib.bib253)] | CVPR 2024 | LLaVA-7B/13B | InstructDiffusion [[254](https://arxiv.org/html/2405.19334v2#bib.bib254)] | ✓ |

表 IV: 基于 CLIP 和 LLM 的视频编辑方法概述。我们总结了涉及的 LLM 和生成模型，以及方法是否需要训练。

| 方法 | 会议 | LLM | 生成模型 | 训练 |
| --- | --- | --- | --- | --- |
| CLIP 用于视频编辑 |
| Tune-A-Video [[255](https://arxiv.org/html/2405.19334v2#bib.bib255)] | ICCV 2023 | - | SD | ✓ |
| Dreamix [[256](https://arxiv.org/html/2405.19334v2#bib.bib256)] | arXiv 2023 | - | Imagen-video | ✓ |
| Video-P2P [[257](https://arxiv.org/html/2405.19334v2#bib.bib257)] | arXiv 2023 | - | SD | ✓ |
| FateZero [[258](https://arxiv.org/html/2405.19334v2#bib.bib258)] | ICCV 2023 | - | SD | ✗ |
| Pix2Video [[259](https://arxiv.org/html/2405.19334v2#bib.bib259)] | ICCV 2023 | - | SD | ✗ |
| StableVideo [[260](https://arxiv.org/html/2405.19334v2#bib.bib260)] | ICCV 2023 | - | SD | ✗ |
| Rerender-A-Video [[261](https://arxiv.org/html/2405.19334v2#bib.bib261)] | SIGGRAPH Asia 2023 | - | SD | ✓ |
| TokenFlow [[262](https://arxiv.org/html/2405.19334v2#bib.bib262)] | ICLR 2024 | - | SD | ✗ |
| CoDeF [[263](https://arxiv.org/html/2405.19334v2#bib.bib263)] | CVPR 2024 | - | SD | ✓ |
| MagicEdit [[264](https://arxiv.org/html/2405.19334v2#bib.bib264)] | arXiv 2023 | - | SD | ✓ |
| MagicStick [[265](https://arxiv.org/html/2405.19334v2#bib.bib265)] | arXiv 2023 | - | SD | ✓ |
| 基于语言的大型语言模型视频编辑 |
| InstructV2V [[266](https://arxiv.org/html/2405.19334v2#bib.bib266)] | ICLR 2024 | GPT-3 | SD | ✗ |
| InstructVid2Vid [[267](https://arxiv.org/html/2405.19334v2#bib.bib267)] | arXiv 2023 | GPT-3 | SD | ✗ |

#### 4.2.2 使用 LLMs 进行图像编辑

LLMs 提供强大的基于聊天或交互的图像编辑功能 [[268](https://arxiv.org/html/2405.19334v2#bib.bib268), [116](https://arxiv.org/html/2405.19334v2#bib.bib116), [250](https://arxiv.org/html/2405.19334v2#bib.bib250), [251](https://arxiv.org/html/2405.19334v2#bib.bib251), [252](https://arxiv.org/html/2405.19334v2#bib.bib252), [176](https://arxiv.org/html/2405.19334v2#bib.bib176)]。

InstructPix2pix [[268](https://arxiv.org/html/2405.19334v2#bib.bib268)] 提出了使用 LLMs 来构建数据元组（原始图像、提示、目标图像），以训练一个能够根据编辑提示编辑图像的模型。该模型基于条件扩散模型，可以处理任意交错的图像和文本输入，并生成连贯的图像（和文本）输出。为了生成数据元组，作者利用了两个大型预训练模型的知识：一个语言模型（GPT-3）和一个 T$\rightarrow$I 模型（Stable Diffusion）。语言模型生成编辑指令和编辑图像的文本描述，而 T$\rightarrow$I 模型则根据文本描述渲染编辑后的图像。作者还引入了一个映射网络，将语言模型的隐藏表示转换为视觉模型的嵌入空间，使模型能够利用 LLM 的强大文本表示生成视觉输出。

CHATEDIT [[250](https://arxiv.org/html/2405.19334v2#bib.bib250)] 进一步利用 LLMs 贡献了一个通过对话进行交互式面部图像编辑的系统。具体而言，CHATEDIT 将基于对话的编辑问题拆分为（1）用户编辑请求跟踪，（2）图像编辑和（3）响应生成子任务。用户编辑请求跟踪模块负责从对话历史中提取用户的编辑意图并动态更新。图像编辑模块基于条件扩散模型，能够处理图像和文本输入输出，并执行各种编辑操作，如更改发色、添加眼镜或去除皱纹。响应生成模块旨在生成自然且信息丰富的响应，反映编辑结果并引导用户进入下一步。CHATEDIT 在作者提出的一个新基准数据集上进行了评估，该数据集包含多轮对话和相应的面部图像，并附有用户编辑请求。

MGIE [[251](https://arxiv.org/html/2405.19334v2#bib.bib251)] 研究了 MLLMs 在图像编辑任务中的应用。提出的 MGIE 可以学习将表达性的人工指令转换为编辑指导。编辑模型也经过训练以端到端的方式遵循编辑指导。MGIE 的有效性在类似 Photoshop 的操作、全球照片优化和局部编辑中得到了验证。SmartEdit [[253](https://arxiv.org/html/2405.19334v2#bib.bib253)] 是另一项最近的工作，它利用 MLLMs 进行复杂的基于指令的图像编辑。SmartEdit 分析了复杂指令下基于指令的图像编辑模型的性能，并提出了一个双向交互模块，以使由预训练图像编码器输出的图像特征与 LLaVA 的输出特征进行交互。他们还微调了预训练的扩散模型，以增强模型的感知和推理能力。

Emu edit [[252](https://arxiv.org/html/2405.19334v2#bib.bib252)] 以多任务方式训练了图像编辑模型。任务包括基于区域的编辑、自由形式的编辑和其他计算机视觉任务，所有任务都被制定为生成任务。Emu edit 利用 LLMs 生成指令。具体来说，作者向 LLMs 提供任务描述、一些任务特定的示例和实际图像标题。然后，LLM 被期望输出一个编辑指令、理想输出图像的输出标题，以及哪些对象应该更新或添加到原始图像中。

与上述利用 LLMs 提供编辑指令的工作不同，SLD [[176](https://arxiv.org/html/2405.19334v2#bib.bib176)] 使用 LLMs 来纠正不正确的生成，以实现物体级别的图像编辑。

### 4.3 图像语言数据集

图像语言数据集在训练 T$\rightarrow$I 模型中起着至关重要的作用，提供了这些模型学习如何从文本描述中生成准确且相关的视觉内容所需的基础数据。十多年前，IM2Text [[187](https://arxiv.org/html/2405.19334v2#bib.bib187)]项目通过搜索流行的照片共享网站 Flickr，收集了大量照片。他们筛选了大量数据，精心挑选出一百万张具有清晰且直接相关描述的图像。MS-COCO [[188](https://arxiv.org/html/2405.19334v2#bib.bib188)]则收集了描绘复杂日常场景的图像，这些图像展示了常见物体的自然环境。研究人员附上了五个书面描述以提供详细背景。这些描述提供了对场景和其中物体的更丰富理解。近年来，学术界见证了大规模图像-文本数据集的激增。通常，研究人员通过网络爬取这些数据集。例如，LAION-5B [[196](https://arxiv.org/html/2405.19334v2#bib.bib196)]是一个庞大的数据集，通过搜索图像-文本对来收集。使用 CLIP 模型筛选结果，研究人员确保文本与图像相关。该过程产生了一个包含 58.5 亿对图像-文本的数据集。此外，一些研究人员正在深入挖掘 LAION-5B，以寻找特定类型的内容。例如，Mario-10M 数据集专注于提取图像中包含文本的部分以便进一步研究。同时，LAION-FACE [[193](https://arxiv.org/html/2405.19334v2#bib.bib193)]则专注于包含面孔的图像。这些专门的数据子集帮助研究人员专注于图像-文本对的大规模集合中的特定领域。此外，为了帮助图像生成器在对话过程中遵循指令，LLaVA Visual Instruct 150K 数据集 [[212](https://arxiv.org/html/2405.19334v2#bib.bib212)]包含了一组为指令跟随任务设计的多模态数据，这些数据由 GPT 模型生成。

表 V：概述了现有的利用 LLM 进行基于语言的视频生成的方法。我们将这些方法分为四类：用于视频生成的多模态 LLM、视频布局规划和时间提示生成。在每种方法中，我们总结了任务的输入输出、涉及的 LLM 和生成模型。在“任务”列中，“T”和“V”分别是“文本”和“视频”的缩写，而“Any”表示支持文本、图像、视频和音频模态的通用生成。标记化是将视频转换为离散视频标记的任务，这可以被视为一些视频生成管道的子模块。

| 方法 | 发表场所 | 任务 | LLM | 生成模型 |
| --- | --- | --- | --- | --- |
| 多模态 LLM 用于视频生成 |
| VideoPoet [[71](https://arxiv.org/html/2405.19334v2#bib.bib71)] | arXiv 2023 | Any$\rightarrow$V | VideoPoet | VideoPoet |
| MAGVIT-v2 [[72](https://arxiv.org/html/2405.19334v2#bib.bib72)] | ICLR 2024 | Tokenization | BERT | BERT |
| Video-LaVIT [[72](https://arxiv.org/html/2405.19334v2#bib.bib72)] | arXiv 2024 | TIV$\rightarrow$TIV | Llama 2-7B | SVD img2vid-xt |
| 视频布局规划 |
| Dysen-VDM [[73](https://arxiv.org/html/2405.19334v2#bib.bib73)] | CVPR 2024 | T$\rightarrow$V | GPT-4 | Text2Video-Zero |
| VideoDirectorGPT [[74](https://arxiv.org/html/2405.19334v2#bib.bib74)] | arXiv 2023 | TI$\rightarrow$V | GPT-4 | LayoutVid |
| LVD [[65](https://arxiv.org/html/2405.19334v2#bib.bib65)] | ICLR 2024 | T$\rightarrow$V | GPT-3.5/GPT-4 | DSL-grounded generator |
| GPT4MOTION [[75](https://arxiv.org/html/2405.19334v2#bib.bib75)] | arXiv 2023 | T$\rightarrow$V | GPT-4 | SDXL / ControlNet |
| FlowZero [[76](https://arxiv.org/html/2405.19334v2#bib.bib76)] | arXiv 2023 | T$\rightarrow$V | GPT-4 | Gligen |
| 时间提示生成 |
| DirecT2V [[77](https://arxiv.org/html/2405.19334v2#bib.bib77)] | arXiv 2023 | T$\rightarrow$V | GPT-4 | Text2Video-Zero |
| Free-Bloom [[78](https://arxiv.org/html/2405.19334v2#bib.bib78)] | NeurIPS 2023 | T$\rightarrow$V | GPT-3.5 | LDM |
| InterControl [[79](https://arxiv.org/html/2405.19334v2#bib.bib79)] | arXiv 2023 | T$\rightarrow$V | GPT-4 | HMDM |
| PRO-Motion [[80](https://arxiv.org/html/2405.19334v2#bib.bib80)] | arXiv 2023 | T$\rightarrow$V | GPT-3.5 | Posture-Diffuser |
| VideoDrafter [[81](https://arxiv.org/html/2405.19334v2#bib.bib81)] | arXiv 2024 | T$\rightarrow$V | ChatGLM-6B | SD-XL |

## 5 视频生成与编辑

### 5.1 视频生成

尽管视频理解已经得到了彻底研究[[269](https://arxiv.org/html/2405.19334v2#bib.bib269), [270](https://arxiv.org/html/2405.19334v2#bib.bib270), [271](https://arxiv.org/html/2405.19334v2#bib.bib271), [272](https://arxiv.org/html/2405.19334v2#bib.bib272), [273](https://arxiv.org/html/2405.19334v2#bib.bib273), [274](https://arxiv.org/html/2405.19334v2#bib.bib274), [275](https://arxiv.org/html/2405.19334v2#bib.bib275), [276](https://arxiv.org/html/2405.19334v2#bib.bib276), [277](https://arxiv.org/html/2405.19334v2#bib.bib277), [278](https://arxiv.org/html/2405.19334v2#bib.bib278), [279](https://arxiv.org/html/2405.19334v2#bib.bib279), [280](https://arxiv.org/html/2405.19334v2#bib.bib280)]，过去两年见证了视频生成的快速发展。特别是在基于文本的视频生成领域，许多工作取得了显著成果。我们在图[6](https://arxiv.org/html/2405.19334v2#S5.F6 "Figure 6 ‣ 5.1.4 Temporal Prompt Generation via LLMs ‣ 5.1 Video Generation ‣ 5 Video Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中列出了里程碑式的工作，包括基于 CLIP/T5 的方法和基于 LLM 的方法，并在表[V](https://arxiv.org/html/2405.19334v2#S4.T5 "TABLE V ‣ 4.3 Image-language datasets ‣ 4 Image Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中总结了关键技术组件，在表[VI](https://arxiv.org/html/2405.19334v2#S5.T6 "TABLE VI ‣ 5.4 Summary ‣ 5 Video Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中总结了常用的视频-语言数据集。

#### 5.1.1 使用 CLIP 的文本到视频生成

基于生成模型的类型，主要有两种范式：一种是基于扩散模型，另一种是基于使用变换器架构和离散代码本构建的自回归模型，并通过下一个标记预测损失进行训练。扩散模型因其训练方便而成为主流范式。在扩散框架中，有像素级视频扩散模型 [[12](https://arxiv.org/html/2405.19334v2#bib.bib12), [16](https://arxiv.org/html/2405.19334v2#bib.bib16), [17](https://arxiv.org/html/2405.19334v2#bib.bib17)] 和潜在级视频扩散模型 [[14](https://arxiv.org/html/2405.19334v2#bib.bib14), [15](https://arxiv.org/html/2405.19334v2#bib.bib15), [281](https://arxiv.org/html/2405.19334v2#bib.bib281), [282](https://arxiv.org/html/2405.19334v2#bib.bib282), [283](https://arxiv.org/html/2405.19334v2#bib.bib283), [284](https://arxiv.org/html/2405.19334v2#bib.bib284), [285](https://arxiv.org/html/2405.19334v2#bib.bib285), [286](https://arxiv.org/html/2405.19334v2#bib.bib286)]。像素级方法展现出更好的文本对齐性，但需要大量计算资源。另一方面，潜在级模型更为高效，因为它们减少了视频数据中的冗余。不同的视频生成工作关注点各异。一些强调真实感或高清输出，旨在提高生成视频的质量。其他则关注可控生成，例如图像到视频的方法，可以局部控制运动区域、物体和摄像机的运动方向以及使用草图、深度和姿势来控制结构。一些工作则集中于生成更长的视频或探索更好的网络架构。

#### 5.1.2 使用 LLMs 进行文本到视频的生成

最近，一些工作也利用了多模态 LLMs [[71](https://arxiv.org/html/2405.19334v2#bib.bib71), [72](https://arxiv.org/html/2405.19334v2#bib.bib72)]来完成视频生成任务。例如，VideoPoet [[71](https://arxiv.org/html/2405.19334v2#bib.bib71)]利用预训练的自回归变换器模型处理多模态数据，以合成具有时间一致性和高运动保真度的视频。它适应了 LLMs 的训练技术，允许特定任务的视频生成，包括文本到视频和图像到视频的转换。另一项工作，MAGVIT-v2 [[72](https://arxiv.org/html/2405.19334v2#bib.bib72)]，探索了 MLLMs 的视频标记化技术。它将视觉输入转换为离散标记，提高了图像和视频生成任务的性能。在 ImageNet 和 Kinetics 等基准测试中优于扩散模型，并提供与先进编解码器相当的视频压缩，并通过有效的表征学习提高了动作识别。

#### 5.1.3 通过 LLMs 进行视频布局规划

众多研究已验证了大型语言模型（LLMs）在生成图像布局方面的有效性，最近的研究也探索了 LLMs 在制作视频布局中的潜力。例如，一些方法使用 LLMs 按顺序生成每帧中物体的边界框，以辅助视频生成过程。VideoDirectorGPT [[74](https://arxiv.org/html/2405.19334v2#bib.bib74)]利用语言模型生成包括每个场景中物体边界框的视频计划。这些边界框提供了实体的空间坐标，用于在视频生成过程中保持物体一致性和精确布局控制。LLM 基础的视频扩散（LVD） [[65](https://arxiv.org/html/2405.19334v2#bib.bib65)]通过首先使用 LLM 从文本提示中创建详细的场景布局，捕捉复杂的动作，从而增强视频生成。这些布局随后通过调整的注意力图指导扩散模型，生成准确反映提示动作和动态的视频，改进了现有的视频生成方法。FlowZero [[76](https://arxiv.org/html/2405.19334v2#bib.bib76)]利用 LLMs 生成包括物体边界框的动态场景语法，这对定义每帧中的物体位置和运动至关重要。这些边界框指导扩散模型以确保视频中的物体准确放置和一致运动。另一类工作尝试超越传统的边界框使用布局。Dysen-VDM [[73](https://arxiv.org/html/2405.19334v2#bib.bib73)]通过使用动态场景图（DSG）提高生成视频的质量。DSG 用于捕捉和组织文本描述中的动作的时间动态，然后将其丰富细节并整合到扩散模型中，以生成更动态和真实的视频。GPT4Motion [[75](https://arxiv.org/html/2405.19334v2#bib.bib75)]使用 GPT-4 在 Blender 中编写物理场景。模拟场景被转换为中间表示，如深度图，以作为布局条件。然后将这些条件输入到稳定扩散模型中以生成最终视频，确保在物体交互和流体动态等场景中的动作一致性和效率。

#### 5.1.4 通过 LLMs 生成时间提示

与图像生成相比，视频生成需要更复杂且详细的描述。通过利用 LLMs 的能力，可以促进提示的精炼和扩展。例如，DirecT2V [[77](https://arxiv.org/html/2405.19334v2#bib.bib77)] 改善了用户提示中的叙事一致性和场景构图。它使用了经过指令调整的大型语言模型，将单一用户提示分解为详细的逐帧描述。这些描述指导每一帧视频的生成，使时间变化元素和连贯的叙事得以无缝融合。Free-Bloom [[78](https://arxiv.org/html/2405.19334v2#bib.bib78)] 利用大型语言模型（LLMs）创建语义一致的提示序列，指导视频的叙事流。然后使用预训练的潜在扩散模型（LDMs）作为动画生成器，生成高保真度的帧，以视觉上表现不断变化的语义内容，例如花朵绽放的过程。InterControl [[79](https://arxiv.org/html/2405.19334v2#bib.bib79)] 使用 LLM 规划器将文本互动描述转换为详细的接触计划，从而提高了运动视频的生成质量。PRO-MOTION [[80](https://arxiv.org/html/2405.19334v2#bib.bib80)] 使用 LLMs 创建一个详细描述目标动作所需关键姿势的脚本序列。这些脚本基于简单的模板，与自然语言不同，旨在全面描述所有可能的姿势，从而简化后续生成过程。VideoDrafter [[81](https://arxiv.org/html/2405.19334v2#bib.bib81)] 利用 LLMs 将输入提示转换为详细的多场景脚本。该脚本利用 LLMs 的逻辑知识以确保场景按顺序合理。

![参见说明](img/1a659a5b01c2ef160b61ce311c78d792.png)

图 6：基于 Clip/T5 和 LLM 的语言引导视频生成的里程碑工作。

### 5.2 视频编辑

#### 5.2.1 基于 CLIP/T5 的文本引导视频编辑

CLIP [[24](https://arxiv.org/html/2405.19334v2#bib.bib24)] 实现了基于语言的视频编辑。在这里，我们主要讨论基于扩散模型的视频编辑方法。Tune-A-Video [[255](https://arxiv.org/html/2405.19334v2#bib.bib255)] 展示了使用预训练扩散模型进行文本引导视频编辑的早期尝试。Wu 等人[[255](https://arxiv.org/html/2405.19334v2#bib.bib255)] 提出了在目标视频上以一次性方式扩展和调整预训练的文本到图像扩散模型。调整后，扩展的扩散模型支持多样化的视频编辑能力。尽管其方法简单，Tune-A-Video [[255](https://arxiv.org/html/2405.19334v2#bib.bib255)] 在时间稳定性方面表现较差，并且在保持无关区域不变方面存在限制。Video-P2P [[257](https://arxiv.org/html/2405.19334v2#bib.bib257)] 和 FateZero [[258](https://arxiv.org/html/2405.19334v2#bib.bib258)] 利用更好的逆转技术，并提出了操控注意力图以保持背景在编辑时不变的方法。Pix2Video [[259](https://arxiv.org/html/2405.19334v2#bib.bib259)] 采用先编辑关键帧然后将编辑传播到其他帧的策略，从而实现了改进的时间一致性和更长的视频编辑能力。与这些工作不同，Rerender-A-video [[261](https://arxiv.org/html/2405.19334v2#bib.bib261)] 和 CoDeF [[263](https://arxiv.org/html/2405.19334v2#bib.bib263)] 将应用重点放在视频到视频风格转换上，并通过基于光流的正则化[[261](https://arxiv.org/html/2405.19334v2#bib.bib261)] 或采用可变形内容场[[263](https://arxiv.org/html/2405.19334v2#bib.bib263)] 实现了令人印象深刻的结果。最近，基于 CLIP 的视频编辑的发展趋向于更好的时间一致性[[262](https://arxiv.org/html/2405.19334v2#bib.bib262), [260](https://arxiv.org/html/2405.19334v2#bib.bib260), [264](https://arxiv.org/html/2405.19334v2#bib.bib264)]，更可控[[265](https://arxiv.org/html/2405.19334v2#bib.bib265)]，以及更具计算效率[[287](https://arxiv.org/html/2405.19334v2#bib.bib287)]。我们在表[IV](https://arxiv.org/html/2405.19334v2#S4.T4 "TABLE IV ‣ 4.2.1 Image Editing with CLIP/T5 ‣ 4.2 Image Editing ‣ 4 Image Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中列出了最近具有代表性的视频编辑工作。

#### 5.2.2 基于 LLMs 的文本引导视频编辑

目前利用大型语言模型（LLMs）进行视频编辑的工作相对有限。当前基于 LLMs 的视频编辑遵循类似于 InstructPix2pix 的方案[[268](https://arxiv.org/html/2405.19334v2#bib.bib268)]，即利用 LLMs 更高效地构建训练数据。

InstructVid2Vid [[267](https://arxiv.org/html/2405.19334v2#bib.bib267)] 是涉及大型语言模型高效训练数据构建的作品之一。该方法使用大型语言模型生成合成的视频-指令对，然后用这些对来训练一个编辑模型，以实现基于自然语言指令的可控视频编辑。InstructVid2Vid 利用预训练的图像生成模型，即稳定扩散（Stable Diffusion），和条件 3D Unet 来生成高质量且时间上连贯的视频，匹配输入视频和指令。为了提高合成数据的多样性和真实性，InstructVid2Vid 融合了不同模型的知识和专业技术，如 ChatGPT、BLIP 和 Tune-a-Video，以合成同一视频的各种指令。论文展示了使用大型语言模型合成复杂和创造性任务训练数据的有效性，如属性编辑、背景更改和风格迁移。

InsV2V [[266](https://arxiv.org/html/2405.19334v2#bib.bib266)] 是另一种将 InstructPix2Pix 范式扩展到视频编辑领域的方法。InsV2V 使用大型语言模型构建合成数据来训练视频编辑模型，该模型也可以遵循自然语言指令来编辑视频。InsV2V 采用一体化模型策略，消除了对每个视频每个模型进行微调或反演的需求，通过只需要一个编辑提示来简化用户交互。InsV2V 利用预训练的图像生成模型 Stable Diffusion 和条件 3D U-Net 架构来生成高质量且时间上连贯的视频，匹配输入视频和指令。InsV2V 展示了使用大型语言模型合成训练数据和执行基于文本的视频编辑的多样性和有效性，适用于各种任务，如对象替换、风格迁移和背景更改。

### 5.3 视频语言数据集

字幕视频数据集的可用性对文本到视频生成至关重要。为了解决这一挑战，MSR-VTT [[288](https://arxiv.org/html/2405.19334v2#bib.bib288)] 推出了一个大规模开放领域的视频语言数据集，涵盖了广泛的类别和多样的内容，为 2016 年的视频理解任务设定了新的基准。该数据集包含来自 10K 个网页视频的 20 万对视频-语言对，每个视频都有 20 个英文人工注释。Anna 等人提出了大规模电影描述挑战 (LSMDC) [[289](https://arxiv.org/html/2405.19334v2#bib.bib289)]，该挑战包含 202 部电影，并配有转录的音频描述。这些描述提供了视觉视频中显著事件的叙述。在自然视频中，单个视频中通常会发生多个事件。例如，一个视频可能展示一个人弹钢琴，一个女孩唱歌，以及一群人鼓掌。为了识别和描述每个事件，Ranjay 等人提出了 ActivityNet Caption [[290](https://arxiv.org/html/2405.19334v2#bib.bib290)] 基准，该基准涉及检测事件、使用自然语言描述事件，并通过开始和结束时间进行定位。How2 [[291](https://arxiv.org/html/2405.19334v2#bib.bib291)] 和 VATEX [[292](https://arxiv.org/html/2405.19334v2#bib.bib292)] 是多语言视频描述数据集。How2 是一个大规模的教学多模态和多语言视频数据集，包括英文和葡萄牙文描述、视频、语音以及英文视频级总结。VATEX 包含英文和中文描述，涵盖 600 种人类活动。HowTo100M [[293](https://arxiv.org/html/2405.19334v2#bib.bib293)] 引入了一种自动视频字幕生成方法，利用从网页视频中转录的叙述，而非手动标注，从而实现快速和可扩展的数据收集。Jonathan 等人观察到，网页视频通常附带文本元数据，如标题和描述。他们提出了一个数据收集过程，收集了 7000 万段视频片段，称为 WTS70M [[294](https://arxiv.org/html/2405.19334v2#bib.bib294)]，使用了包括标题、描述、标签和频道名称在内的元数据。WebVid [[13](https://arxiv.org/html/2405.19334v2#bib.bib13)] 数据集是为了文本到视频检索任务而创建的。鉴于以前数据集中存在的噪声，WebVid-2M 和 WebVid-10M 从互联网收集了特征较弱的字幕。YT-Temporal-180M [[295](https://arxiv.org/html/2405.19334v2#bib.bib295)] 是一个包含多样化帧语料库的数据集，其中 ASR 来源于经过筛选的 600 万 YouTube 视频，作为多模态表示学习的资源。HDVILA [[296](https://arxiv.org/html/2405.19334v2#bib.bib296)] 是一个高分辨率的大规模数据集，包含 37 万部视频，覆盖 15 个流行的 YouTube 类别，提供了多样的视频内容。VideoCC3M [[297](https://arxiv.org/html/2405.19334v2#bib.bib297)] 提出了一种方法，将现有图像字幕中的字幕转移到 CC3M，创建了一个新的弱标注音视频字幕数据集。VideoFactory [[298](https://arxiv.org/html/2405.19334v2#bib.bib298)] 引入了 HD-VG-130M，这是一个包含 1.3 亿个高清晰度、宽屏和无水印文本-视频对的数据集。InternVid [[299](https://arxiv.org/html/2405.19334v2#bib.bib299)] 提出了构建高质量视频文本数据集的可扩展方法。他们采用了一种多尺度方法，利用 Tag2Text、LLM 和 BLIP2 生成视频字幕。Panda-70M [[300](https://arxiv.org/html/2405.19334v2#bib.bib300)] 是 2024 年提出的一个高质量和大规模的带字幕视频数据集。它包含 7000 万段来自 YouTube 视频的视频片段，字幕通过多个教师模型提取，以获得一个视频的多个字幕，并通过一个经过良好训练的字幕检索模型选择最佳字幕。Vript [[301](https://arxiv.org/html/2405.19334v2#bib.bib301)] 是 2024 年提出的一个细粒度视频文本数据集，包含 12000 个注释视频。虽然视频数量有限，但每个视频的字幕都是细粒度的，包含了镜头类型、相机运动、内容和场景标题的信息。

### 5.4 总结

在第[5](https://arxiv.org/html/2405.19334v2#S5 "5 Video Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")节中，我们介绍了视频模态生成和编辑的研究工作。对于每个任务，我们将论文分为两组：基于 CLIP/T5 的方法和基于 LLMs 的方法，以突出 LLMs 带来的进展。我们在表[V](https://arxiv.org/html/2405.19334v2#S4.T5 "TABLE V ‣ 4.3 Image-language datasets ‣ 4 Image Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中总结了基于 LLMs 的方法的关键技术组件，在图[6](https://arxiv.org/html/2405.19334v2#S5.F6 "Figure 6 ‣ 5.1.4 Temporal Prompt Generation via LLMs ‣ 5.1 Video Generation ‣ 5 Video Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中展示了语言引导的视频生成任务中的里程碑工作的发展，以及在表[VI](https://arxiv.org/html/2405.19334v2#S5.T6 "TABLE VI ‣ 5.4 Summary ‣ 5 Video Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")中展示了相关的视频-语言数据集。

表 VI：可以用于语言引导的视频生成的公开视频-语言数据集。每个数据集在每列中列出了以下信息：数据集名称（Dataset）、论文会议场所（Venue）、数据集领域（Domain）、视频来源（Vid. Source）、视频空间分辨率（Res.）、每个片段的平均时长（Dur./Clip）、片段总数（#Clips）、视频总数（#Videos）、总小时数（#Hours）和字幕来源（Cap. Source）。数据集按发布时间的升序排列。

| Dataset | Venue | Domain | Vid. Source | Res. | Dur./Clip | #Clips | #Videos | #Hrs | Cap. Source |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| MSR-VTT [[288](https://arxiv.org/html/2405.19334v2#bib.bib288)] | CVPR 2016 | Open | Internet | 240p | 15s | 10K | 7K | 41 | Human |
| LSMDC [[289](https://arxiv.org/html/2405.19334v2#bib.bib289)] | IJCV 2017 | Movie | Amazon | 1080p | 4.8s | 118K | 202 | 158 | Audio Desc. |
| ActivityNet Captions [[290](https://arxiv.org/html/2405.19334v2#bib.bib290)] | ICCV 2017 | Activity | Internet | - | 36s | 100K | 20K | 849 | Human |
| How2 [[291](https://arxiv.org/html/2405.19334v2#bib.bib291)] | NIPS 2018 | Instruction | Youtube | - | 90s | 80K | - | 298 | Human |
| VATEX [[292](https://arxiv.org/html/2405.19334v2#bib.bib292)] | ICCV 2019 | Open | Youtube | 240p | 10s | 41K | 41K | - | Human |
| HowTo100M [[293](https://arxiv.org/html/2405.19334v2#bib.bib293)] | ICCV 2019 | Instruction | Youtube | 240p | 4s | 136M | 1.2M | 134K | ASR |
| WTS70M [[294](https://arxiv.org/html/2405.19334v2#bib.bib294)] | arXiv 2020 | Open | Youtube | - | 10s | 70M | 70M | 194K | Metadata |
| WebVid-10M [[13](https://arxiv.org/html/2405.19334v2#bib.bib13)] | ICCV 2021 | Open | Internet | 360p | 18s | 10.7M | 10.7M | 52K | Alt-text |
| YT-Temporal-180M [[295](https://arxiv.org/html/2405.19334v2#bib.bib295)] | NeurIPS 2021 | 开放 | Youtube | - | - | 180M | 6M | - | ASR |
| HD-VILA-100M [[296](https://arxiv.org/html/2405.19334v2#bib.bib296)] | CVPR 2022 | 开放 | Youtube | 720p | 13.4s | 103M | 3.3M | 372 | 算法 |
| CelebV-Text [[302](https://arxiv.org/html/2405.19334v2#bib.bib302)] | CVPR 2023 | 面部 | 互联网 | 512²+ | 14s | 70K | - | 279 | 人类+算法 |
| VideoCC3M [[297](https://arxiv.org/html/2405.19334v2#bib.bib297)] | ECCV 2022 | 开放 | CC3M | - | 10s | 6.3M | - | 17.5K | CC3M |
| HD-VG-130M [[298](https://arxiv.org/html/2405.19334v2#bib.bib298)] | arXiv 2023 | 开放 | Youtube | 720p | - | 130M | - | - | 算法 |
| InternVid [[299](https://arxiv.org/html/2405.19334v2#bib.bib299)] | ICLR 2024 | 开放 | Youtube | 720p | 12s | 234M | 7M | 760K | 算法 |
| Panda-70M [[300](https://arxiv.org/html/2405.19334v2#bib.bib300)] | CVPR 2024 | 开放 | Youtube | 720p | 8.5s | 70.8M | - | 166.8K | 算法 |
| Vript [[301](https://arxiv.org/html/2405.19334v2#bib.bib301)] | Github | 开放 | Youtube | 720p-2K | 11.7s | 400K | 12K | 1.3K | 算法 |

## 6 3D 生成与编辑

![参考说明](img/b70cd20838f82652e09cae77fa4eec83.png)

图 7：使用 CLIP 和 LLM 的 3D 生成通用流程。基于 CLIP 的模型通过最小化渲染图像与文本提示之间的距离来优化 3D 表示。为了更好地提高交互效率，基于 LLM 的方法尝试将 LLM 的语言输出直接转换为 blender 代码或 3D 表示（即人类动作）。一些图像来自 [[303](https://arxiv.org/html/2405.19334v2#bib.bib303), [83](https://arxiv.org/html/2405.19334v2#bib.bib83), [304](https://arxiv.org/html/2405.19334v2#bib.bib304)]

最近的研究集中于建立 3D 资产与文本之间的联系。可以为 3D 资产提供文本信息的方法有两种，包括 LLMs 和 CLIP/T5 模型。LLMs 可以根据用户需求对 3D 生成和理解的输出进行迭代更新，从而促进高效的人机交互（即，根据语言指导人类动作的生成）。与 LLMs 直接以互动迭代方式影响 3D 资产不同，CLIP/T5 模型融合了渲染图像和文本的特征，使得将文本信息注入 3D 资产成为可能。在本节中，我们将深入探讨利用 CLIP 模型或 LLMs 来指导 3D 生成、编辑和理解过程的各种方法。通用流程图见图[7](https://arxiv.org/html/2405.19334v2#S6.F7 "Figure 7 ‣ 6 3D Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")。3D 生成和编辑方法的概述见表[VII](https://arxiv.org/html/2405.19334v2#S6.T7 "TABLE VII ‣ 6.3 Summary ‣ 6 3D Generation and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")。

### 6.1 3D 生成

#### 6.1.1 CLIP/T5 的 3D 生成

通过利用 CLIP 的多模态表示能力，研究人员已经能够使用文本描述或查询来引导 3D 资产的生成和编辑，从而实现更精确的控制和定制。具体而言，CLIP [[24](https://arxiv.org/html/2405.19334v2#bib.bib24)] 使用两个编码器提取图像和文本的特征，并以对比学习的方式对其进行对齐。这种对齐有效地建立了图像和文本之间的联系，带来了文本引导的 2D [[305](https://arxiv.org/html/2405.19334v2#bib.bib305), [30](https://arxiv.org/html/2405.19334v2#bib.bib30), [137](https://arxiv.org/html/2405.19334v2#bib.bib137), [306](https://arxiv.org/html/2405.19334v2#bib.bib306), [205](https://arxiv.org/html/2405.19334v2#bib.bib205), [25](https://arxiv.org/html/2405.19334v2#bib.bib25)], 文本引导的 3D [[25](https://arxiv.org/html/2405.19334v2#bib.bib25), [138](https://arxiv.org/html/2405.19334v2#bib.bib138), [43](https://arxiv.org/html/2405.19334v2#bib.bib43)] 生成的显著改进。有三种典型方法利用 CLIP 模型在 3D 生成过程中提供文本信息：1\. 采用预训练的 CLIP 模型作为监督者，计算生成图像与文本之间的 CLIP 损失，或将文本特征直接注入到 3D 资产中。2\. 利用预训练的文本到图像生成模型作为监督信号，并使用诸如 SDS [[43](https://arxiv.org/html/2405.19334v2#bib.bib43), [307](https://arxiv.org/html/2405.19334v2#bib.bib307)] 等蒸馏损失函数来蒸馏 3D 资产 [[308](https://arxiv.org/html/2405.19334v2#bib.bib308), [309](https://arxiv.org/html/2405.19334v2#bib.bib309), [310](https://arxiv.org/html/2405.19334v2#bib.bib310)]。3\. 利用公开的标注 3D 数据集 [[304](https://arxiv.org/html/2405.19334v2#bib.bib304), [311](https://arxiv.org/html/2405.19334v2#bib.bib311), [312](https://arxiv.org/html/2405.19334v2#bib.bib312), [313](https://arxiv.org/html/2405.19334v2#bib.bib313)] 获取网格、NeRF 或多视图图像，然后将这些输出用于训练 3D 扩散模型。如上所述，我们将在以下内容中详细探讨当前方法的两大类。

CLIP/T5 模型监督者。

Text2Mesh [[27](https://arxiv.org/html/2405.19334v2#bib.bib27)] 关注于通过预测颜色和局部几何细节来美化 3D 网格，这些细节与目标文本提示对齐。整个过程由 CLIP 损失指导，这有助于确保生成的网格符合期望的文本规范。这种方法提供了对 3D 网格视觉外观和几何属性的增强控制，使得能够创建视觉上吸引人且语义上有意义的形状。

TANGO [[314](https://arxiv.org/html/2405.19334v2#bib.bib314)] 提出了一个在给定网格上生成纹理的管道。通过利用 CLIP 模型，TANGO 将纹理生成过程与文本描述对齐，允许合成匹配特定视觉或语义标准的纹理网格。这种方法有助于创建具有详细表面纹理的逼真且视觉一致的 3D 模型。CLIP-Mesh [[26](https://arxiv.org/html/2405.19334v2#bib.bib26)] 通过优化 3D 物体的纹理、法线和垂直位置，解决了无监督文本引导的 3D 生成问题。该方法使得生成与文本提示对齐的 3D 物体成为可能，为基于文本的内容创建和设计提供了强大的工具。X-mesh [[315](https://arxiv.org/html/2405.19334v2#bib.bib315)] 通过采用基于注意力的网络进一步提高了 CLIP-Mesh 的性能，增强了生成 3D 网格的保真度和准确性。CLIP-forge [[25](https://arxiv.org/html/2405.19334v2#bib.bib25)] 引入了一种零样本文本到形状的方法，通过结合 CLIP 模型的文本特征和条件归一化流网络 [[316](https://arxiv.org/html/2405.19334v2#bib.bib316)] 来预测体积占据。这种方法使得根据文本提示生成 3D 形状成为可能，无需显式监督或标记的训练数据。

一些方法利用 CLIP 指导输出 NeRF 表示 [[308](https://arxiv.org/html/2405.19334v2#bib.bib308)]，用于建模复杂场景并捕捉高频空间信息。DreamFields [[317](https://arxiv.org/html/2405.19334v2#bib.bib317)] 引入了通用先验，以帮助将优化的 NeRF 与给定的文本提示对齐，从而提高生成场景的质量和保真度。CLIP-NeRF [[138](https://arxiv.org/html/2405.19334v2#bib.bib138)] 采取了两步方法，首先训练一个解耦的条件 NeRF，然后利用文本特征调整学习到的 NeRF 的参数，使得对生成场景的控制更加精细。

ShapeGPT [[318](https://arxiv.org/html/2405.19334v2#bib.bib318)] 利用“词-句子-段落”管道将形状转换为词语。这些词语随后被组合成形状句子，并与说明文本集成，创建描述 3D 形状的多模态段落。这些多模态段落帮助 ShapeGPT 进行多种应用，包括文本到形状生成、图像到形状生成，以及多模态到形状的完成和编辑。

超越对象生成，MotionCLIP [[319](https://arxiv.org/html/2405.19334v2#bib.bib319)] 提出了一个 3D 人体运动自编码器，能够预测姿态序列。通过利用 CLIP，该方法能够基于文本提示生成逼真且上下文一致的人体运动，提供了一种基于文本的动画和虚拟角色控制手段。MotionGPT [[320](https://arxiv.org/html/2405.19334v2#bib.bib320)] 将人体运动视为一种独特的语言，并用 T5 模型训练了一个运动语言模型。该方法结合了离散向量量化来表示人体运动，并将 3D 运动转化为运动标记。通过建立一个全面的“运动词汇”，模型在运动和文本上进行一致的语言建模。

尽管上述方法在文本引导生成方面取得了显著成功，但它们仍面临与视觉伪影相关的挑战。这可以归因于 CLIP 损失的语义级特性，它倾向于减少生成图像中的高频空间信息。解决这一限制仍然是一个活跃的研究领域，目标是进一步提高文本引导 3D 生成方法的视觉质量和逼真度。

文本到图像模型监督者。

与直接利用 CLIP 模型或 CLIP 损失进行 3D 生成的方法相比，最近的一些方法 [[45](https://arxiv.org/html/2405.19334v2#bib.bib45), [307](https://arxiv.org/html/2405.19334v2#bib.bib307), [38](https://arxiv.org/html/2405.19334v2#bib.bib38), [40](https://arxiv.org/html/2405.19334v2#bib.bib40), [321](https://arxiv.org/html/2405.19334v2#bib.bib321), [39](https://arxiv.org/html/2405.19334v2#bib.bib39), [33](https://arxiv.org/html/2405.19334v2#bib.bib33), [36](https://arxiv.org/html/2405.19334v2#bib.bib36), [42](https://arxiv.org/html/2405.19334v2#bib.bib42), [322](https://arxiv.org/html/2405.19334v2#bib.bib322), [323](https://arxiv.org/html/2405.19334v2#bib.bib323)] 重点关注从预训练的文本到图像生成模型（即 Stable Diffusion [[30](https://arxiv.org/html/2405.19334v2#bib.bib30)]）中提取 3D 资产。这些模型在 DreamFusion [[43](https://arxiv.org/html/2405.19334v2#bib.bib43)] 框架内采用了得分蒸馏采样（SDS）损失。具体而言，文本到 2D 图像生成模型利用来自 CLIP 的文本特征来训练一个生成模型（即扩散模型）在文本-图像配对数据集中，SDS [[43](https://arxiv.org/html/2405.19334v2#bib.bib43)] 模拟了扩散模型的训练过程，并计算渲染图像的空间梯度以优化 NeRF 的参数。许多后续方法利用了 SDS 损失函数作为监督信号，并引入了各种技术来改善 3D 生成的性能。

例如，Magic3D [[44](https://arxiv.org/html/2405.19334v2#bib.bib44)] 结合了 DMTed [[310](https://arxiv.org/html/2405.19334v2#bib.bib310)]，将 NeRF 模型转化为网格表示，从而实现高分辨率的渲染效果。论文中展示的实验结果表明，Magic3D 在提升几何体和纹理的生成质量方面具有显著效果。类似于 Magic3D，TextMesh [[42](https://arxiv.org/html/2405.19334v2#bib.bib42)] 用纹理网格表示替代了 NeRF 模型用于 3D 资产生成。LatentNeRF[[324](https://arxiv.org/html/2405.19334v2#bib.bib324)] 引入了一种潜在空间优化策略。它利用文本到图像模型学习到的潜在空间结构，该模型已经在大规模文本-图像数据集上进行过训练。通过将 NeRF 优化过程与潜在空间结构对齐，LatentNeRF 提高了训练过程的收敛性和稳定性。

Fantasia3D [[41](https://arxiv.org/html/2405.19334v2#bib.bib41)] 提出了一种生成 3D 资产的新方法，通过分离几何体和纹理组件来实现。它首先细化法线图以生成几何体，然后固定几何体以预测颜色场。此外，Fantasia3D 将颜色场设置为物理基础渲染（PBR）材质模型，以增强生成的逼真度。此外，艺术家和设计师可以独立操作和修改几何体和纹理组件，从而提供更广泛的艺术表现和定制可能性。

尽管 SDS 带来了显著的改进，但生成的结果仍然存在一些局限性。这些包括过度饱和、过度平滑、多面 Janus 伪影以及计算耗时。为了解决这些问题并进一步提升生成性能，一些方法 [[325](https://arxiv.org/html/2405.19334v2#bib.bib325), [35](https://arxiv.org/html/2405.19334v2#bib.bib35), [34](https://arxiv.org/html/2405.19334v2#bib.bib34)] 已经被提出。

例如，Perp-Neg [[326](https://arxiv.org/html/2405.19334v2#bib.bib326)] 针对视角一致的文本到 3D 生成的评分蒸馏框架进行了去偏处理，旨在缓解多面 Janus 问题。Prolificdreamer [[37](https://arxiv.org/html/2405.19334v2#bib.bib37)] 引入了变分评分蒸馏（VSD）以避免过饱和和过度平滑。它最小化了优化后的 3D 资产与目标分布之间的 KL 散度，使得生成过程能够利用正常的 CFG 权重。DreamPropeller [[327](https://arxiv.org/html/2405.19334v2#bib.bib327)] 提出了一个即插即用的加速算法，以加快训练过程。它扩展了 Picard 迭代的概念，Picard 迭代是一种用于 ODE 路径并行采样的成熟算法，涵盖了超出 ODE 的各种情境。这包括适应基于动量的梯度更新和处理优化过程中常见的维度变化，这些变化通常出现在 3D 生成的上下文中。此外，一些方法 [[32](https://arxiv.org/html/2405.19334v2#bib.bib32), [31](https://arxiv.org/html/2405.19334v2#bib.bib31)] 已经用高斯喷洒 [[29](https://arxiv.org/html/2405.19334v2#bib.bib29)] 技术替代了 NeRF 模型，以提高训练效率并生成高质量的几何体。

除了上述方法，这些方法主要集中于一般对象生成，一些方法 [[328](https://arxiv.org/html/2405.19334v2#bib.bib328), [329](https://arxiv.org/html/2405.19334v2#bib.bib329), [330](https://arxiv.org/html/2405.19334v2#bib.bib330), [331](https://arxiv.org/html/2405.19334v2#bib.bib331), [332](https://arxiv.org/html/2405.19334v2#bib.bib332), [333](https://arxiv.org/html/2405.19334v2#bib.bib333), [334](https://arxiv.org/html/2405.19334v2#bib.bib334), [335](https://arxiv.org/html/2405.19334v2#bib.bib335), [336](https://arxiv.org/html/2405.19334v2#bib.bib336), [337](https://arxiv.org/html/2405.19334v2#bib.bib337), [338](https://arxiv.org/html/2405.19334v2#bib.bib338), [339](https://arxiv.org/html/2405.19334v2#bib.bib339), [340](https://arxiv.org/html/2405.19334v2#bib.bib340), [341](https://arxiv.org/html/2405.19334v2#bib.bib341), [342](https://arxiv.org/html/2405.19334v2#bib.bib342), [343](https://arxiv.org/html/2405.19334v2#bib.bib343), [344](https://arxiv.org/html/2405.19334v2#bib.bib344)] 尝试探索 3D 头像生成的 3D 生成技术。

3D 数据集主管。

一些方法[[345](https://arxiv.org/html/2405.19334v2#bib.bib345), [346](https://arxiv.org/html/2405.19334v2#bib.bib346), [347](https://arxiv.org/html/2405.19334v2#bib.bib347), [348](https://arxiv.org/html/2405.19334v2#bib.bib348)]尝试使用扩散损失或重建模型[[349](https://arxiv.org/html/2405.19334v2#bib.bib349), [350](https://arxiv.org/html/2405.19334v2#bib.bib350), [351](https://arxiv.org/html/2405.19334v2#bib.bib351)]来训练多视图扩散模型以进行文本到 3D 的生成，这些方法通常采用文本到 3D 的数据集[[304](https://arxiv.org/html/2405.19334v2#bib.bib304), [311](https://arxiv.org/html/2405.19334v2#bib.bib311), [312](https://arxiv.org/html/2405.19334v2#bib.bib312)]作为训练标签。

Point-E[[313](https://arxiv.org/html/2405.19334v2#bib.bib313)]和 Shape-E[[352](https://arxiv.org/html/2405.19334v2#bib.bib352)]首先利用 Blender 收集点云 3D 数据集，然后分别训练扩散模型以生成点云和网格，并加入文本条件。

MVDream[[345](https://arxiv.org/html/2405.19334v2#bib.bib345)]、RichDreamer[[348](https://arxiv.org/html/2405.19334v2#bib.bib348)]、SPAD[[346](https://arxiv.org/html/2405.19334v2#bib.bib346)]和 UniDreamer[[347](https://arxiv.org/html/2405.19334v2#bib.bib347)]从 Objaverse 数据集中获取多视图图像。利用这些多视图图像，它们随后将 2D 文本到图像的扩散模型微调为 3D 扩散模型，以在文本和相机姿态的指导下预测多视图图像。

尽管基于 CLIP 的 3D 生成方法已经取得了显著进展，但 CLIP 模型本身在 3D 生成过程中无法保持人机交互的灵活性。最近，大型语言模型（LLMs）被引入以增强 3D 生成中的人机交互，这将在下一节中讨论。

#### 6.1.2 使用 LLMs 进行 3D 生成

LLM 与 3D 资产的融合最近成为一个有前景的研究方向。通过利用 LLM 强大的语言理解能力，研究人员旨在通过文本指令直接提升 3D 资产的生成、操控或理解性能。这些方法使用户能够更直观自然地与 3D 环境互动，弥合了人类认知与计算机生成内容之间的差距。

3D-GPT [[82](https://arxiv.org/html/2405.19334v2#bib.bib82)] 提出了一个无需训练的框架，该框架利用了 LLMs。该框架由三个代理组成：任务分配代理、概念化代理和建模代理。通过使用这些代理，3D-GPT 能够生成与语言对应的 Blender 代码，并提高从事程序化 3D 建模的最终用户的效率。与 3D-GPT 类似，SceneCraft [[353](https://arxiv.org/html/2405.19334v2#bib.bib353)] 引入了一个 LLM 代理，通过生成 Blender 脚本将输入文本查询转化为 3D 场景。具体来说，sceneCraft 具有一个双循环自我改进的流程：在内循环中，对每个场景，LLM 自动编写脚本与 Blender 交互，接收渲染的图像，并不断改进脚本直到获得良好的场景；在外循环中，SceneCraft 汇总一批编写的脚本中的常见功能，以维护一个可重用的设计技能库。

LL3DA [[84](https://arxiv.org/html/2405.19334v2#bib.bib84)] 提出了一个大型语言 3D 助手，该助手利用变换器网络预测查询令牌。这些令牌被投影到文本指令的前缀上，作为冻结的 LLM 的输入。最终，LLM 将生成对文本指令的回答。

PointLLM [[354](https://arxiv.org/html/2405.19334v2#bib.bib354)] 使用人类指令处理彩色点云，并在 LLMs 的帮助下预测对用户问题的回应。这使得用户能够更有效地分析和解释点云。

3D-LLM [[355](https://arxiv.org/html/2405.19334v2#bib.bib355)] 以具有特征的 3D 点和语言提示作为输入，执行各种与 3D 相关的任务，利用 LLMs 的能力。该研究所涉及的流程包括收集一个综合数据集，该数据集包含超过 300,000 个 3D-语言数据实例。该数据集涵盖了各种多样化的 3D 相关任务，包括但不限于 3D 标注、密集标注、3D 问答、任务分解、3D 定位、3D 辅助对话、导航以及各种其他任务。

总结来说，LLMs 与 3D 资产的结合为通过自然语言指令生成、操控和理解 3D 内容开辟了新的可能性。这些方法在提升 3D 领域的人机交互方面展示了显著的进展。

### 6.2 3D 编辑

类似于生成，我们将文本到 3D 编辑分为两个方面。我们将首先讨论基于 CLIP/T5 的编辑方法。

#### 6.2.1 使用 CLIP/T5 进行 3D 编辑

CLIP/T5 模型监督。

Blended-NeRF [[356](https://arxiv.org/html/2405.19334v2#bib.bib356)] 引入了一种框架，通过 CLIP 损失修改现有 NeRF 场景中的特定感兴趣区域。这种方法利用 CLIP 的对比学习能力来实现 NeRF 场景的有针对性编辑。NeRF-Art [[28](https://arxiv.org/html/2405.19334v2#bib.bib28)] 提出了全球-局部对比学习策略，以对预训练的 NeRF 模型进行风格化。通过运用对比学习，NeRF-Art 能够通过操控预先存在的 NeRF 场景来创建艺术和风格化的渲染。TextDeformer [[357](https://arxiv.org/html/2405.19334v2#bib.bib357)] 采用文本到几何体的操控，通过引入基于 Jacobians 的网格变形技术。这种方法利用文本描述来变形物体的几何体，提供了一种新颖的 3D 模型操控和编辑方式。Sine [[358](https://arxiv.org/html/2405.19334v2#bib.bib358)] 提出了一个先验指导编辑场，该场编码了精细的几何和纹理修改。通过利用这种方法，Sine 实现了对 3D 场景中几何体和纹理的精确和详细编辑，提供了一个强大的创作工具。

文本到图像模型监督器。

SKED [[359](https://arxiv.org/html/2405.19334v2#bib.bib359)] 利用草图作为文本到图像生成模型的指导输入。在 SDS 中，SKED 通过结合草图信息来增强生成过程，产生更准确且上下文对齐的文本到图像翻译。DreamEditor [[360](https://arxiv.org/html/2405.19334v2#bib.bib360)] 将 NeRF 表示转移到网格上，并采用名为 DreamBooth 的个性化文本到图像生成模型进行网格编辑。这种方法允许通过基于文本的指令进行交互式和个性化的网格编辑，使用户能够根据个人偏好修改和塑造 3D 场景。Instruct-NeRF2NeRF [[361](https://arxiv.org/html/2405.19334v2#bib.bib361)] 利用 InstructPix2Pix 模型结合 SDS 损失，通过基于文本的指令编辑 NeRF 场景。通过结合文本指令与 NeRF 编辑的能力，这种方法使用户能够以受控和精确的方式修改场景，增强 NeRF 的交互式编辑能力。3D Paintbrush [[362](https://arxiv.org/html/2405.19334v2#bib.bib362)] 提出了用于编辑网格中局部语义区域纹理的级联评分蒸馏方法。通过蒸馏评分，这种方法允许有针对性和局部的纹理编辑，为用户提供了一个强大的工具，以增强 3D 模型中特定区域的视觉效果。

#### 6.2.2 使用 LLMs 进行 3D 编辑

与基于 CLIP 的方法不同，尚无特定方法使用 LLMs 进行 3D 编辑。编辑更像是基于 LLMs 的 3D 生成的子任务，因此一些生成方法（即 3D-GPT [[82](https://arxiv.org/html/2405.19334v2#bib.bib82)], SceneCraft [[353](https://arxiv.org/html/2405.19334v2#bib.bib353)]）可以直接编辑 3D 资产。我们将关注 LLMs 基于的 3D 编辑的最新进展，并在未来进行讨论。

### 6.3 摘要

在 3D 生成和编辑的背景下，CLIP 或 LLM 的使用提供了多个优势。首先，它使用户能够用自然语言表达他们的创意意图或期望的修改，简化了交互过程，减少了对专业软件或技术专长的需求。此外，将文本信息融入 3D 生成流程提高了生成输出的可解释性和可解释性，使用户能够更好地理解和调整结果以符合他们的要求。

总结来说，CLIP 或 LLM 与 3D 资产的集成开辟了人机交互的新途径。通过将文本信息与 3D 资产的视觉特征对齐，研究人员能够促进对 3D 内容生成和编辑的更直观和精确的控制。这些进展在计算机图形学、虚拟现实和增强现实等领域具有巨大的应用潜力，提供了更好的用户体验，并使用户能够更加无缝和高效地释放他们的创造力。

表 VII：3D 通用对象生成的摘要。优化目标指的是学习过程中重要的约束条件。表示方式指的是 3D 输出的类型。没有优化目标的方法意味着该方法不受 CLIP 损失或基于 SDS 的损失指导。

| 方法 | 会议 | 优化目标 | 表示方式 | 指导模型 |
| --- | --- | --- | --- | --- |
| CLIP/T5 用于 3D 生成 |  |  |  |  |
| MotionCLIP [[319](https://arxiv.org/html/2405.19334v2#bib.bib319)] | ECCV 2022 | CLIP 损失 | 动作序列 | CLIP |
| MotionGPT [[320](https://arxiv.org/html/2405.19334v2#bib.bib320)] | NeurIPS 2023 | - | 动作序列 | T5 |
| MDM [[363](https://arxiv.org/html/2405.19334v2#bib.bib363)] | ICLR 2023 | - | 动作序列 | CLIP |
| CLIP-Mesh [[26](https://arxiv.org/html/2405.19334v2#bib.bib26)] | SIGGRAPH Asia 2022 | CLIP 损失 | 网格 | CLIP |
| TANGO [[314](https://arxiv.org/html/2405.19334v2#bib.bib314)] | NeurIPS 2022 聚焦 | CLIP 损失 | 网格 | CLIP |
| DreamFields [[317](https://arxiv.org/html/2405.19334v2#bib.bib317)] | CVPR 2022 | CLIP 损失 | NeRF | CLIP |
| Clip-forge [[25](https://arxiv.org/html/2405.19334v2#bib.bib25)] | CVPR 2022 | CLIP 损失 | 体素 | CLIP |
| Text2Mesh [[27](https://arxiv.org/html/2405.19334v2#bib.bib27)] | CVPR 2022 | CLIP 损失 | 网格 | CLIP |
| TextMesh [[42](https://arxiv.org/html/2405.19334v2#bib.bib42)] | 3DV 2023 | CLIP Loss | 网格 | CLIP |
| X-Mesh [[315](https://arxiv.org/html/2405.19334v2#bib.bib315)] | ICCV 2023 | CLIP Loss | 网格 | CLIP |
| ShapeGPT [[318](https://arxiv.org/html/2405.19334v2#bib.bib318)] | arXiv 2023 | - | SDF | T5 |
| Shape-E [[352](https://arxiv.org/html/2405.19334v2#bib.bib352)] | arXiv 2023 | 扩散损失 | 网格/NeRF | CLIP |
| Point-E [[313](https://arxiv.org/html/2405.19334v2#bib.bib313)] | arXiv 2023 | 扩散损失 | 点云 | CLIP |
| DreamFusion [[43](https://arxiv.org/html/2405.19334v2#bib.bib43)] | ICLR 2023 口头报告 | Score Distillation | NeRF | Imagen |
| SJC [[307](https://arxiv.org/html/2405.19334v2#bib.bib307)] | CVPR 2023 | Score Distillation | NeRF | SD |
| Magic3D [[44](https://arxiv.org/html/2405.19334v2#bib.bib44)] | CVPR 2023 精彩展示 | Score Distillation | NeRF | SD |
| Perp-Neg [[326](https://arxiv.org/html/2405.19334v2#bib.bib326)] | arXiv 2023 | Score Distillation | NeRF | SD |
| Latent-NeRF [[324](https://arxiv.org/html/2405.19334v2#bib.bib324)] | CVPR 2023 | Score Distillation | NeRF | SD |
| Fantasia3D [[364](https://arxiv.org/html/2405.19334v2#bib.bib364)] | ICCV 2023 | Score Distillation | NeRF | SD |
| ATT3D [[38](https://arxiv.org/html/2405.19334v2#bib.bib38)] | ICCV 2023 | Score Distillation | NeRF | SD |
| ProlificDreamer [[37](https://arxiv.org/html/2405.19334v2#bib.bib37)] | NeurIPS 2023 亮点 | Score Distillation | NeRF | SD |
| Text2Room [[33](https://arxiv.org/html/2405.19334v2#bib.bib33)] | ICCV 2023 | Score Distillation | 网格 | SD |
| 3DFuse [[45](https://arxiv.org/html/2405.19334v2#bib.bib45)] | ICLR 2024 | Score Distillation | NeRF | SD |
| GaussianDreamer [[31](https://arxiv.org/html/2405.19334v2#bib.bib31)] | CVPR 2024 | Score Distillation | 高斯溅射 | SD |
| DreamGaussian [[32](https://arxiv.org/html/2405.19334v2#bib.bib32)] | ICLR 2024 | Score Distillation | 高斯溅射 | SD |
| NFSD [[325](https://arxiv.org/html/2405.19334v2#bib.bib325)] | ICLR 2024 | Score Distillation | NeRF | SD |
| MVDream [[345](https://arxiv.org/html/2405.19334v2#bib.bib345)] | ICLR 2024 | 扩散损失 | 多视图图像 | SD |
| RichDreamer [[348](https://arxiv.org/html/2405.19334v2#bib.bib348)] | CVPR 2024 | 扩散损失 | 多视图图像 | SD |
| SPAD [[346](https://arxiv.org/html/2405.19334v2#bib.bib346)] | CVPR 2024 | 扩散损失 | 多视图图像 | SD |
| UniDreamer [[347](https://arxiv.org/html/2405.19334v2#bib.bib347)] | CVPR 2024 | 扩散损失 | 多视图图像 | SD |
| Enhancing3D [[365](https://arxiv.org/html/2405.19334v2#bib.bib365)] | ICLR 2024 | Score Distillation | NeRF | SD |
| LucidDreamer [[34](https://arxiv.org/html/2405.19334v2#bib.bib34)] | CVPR 2024 | Score Distillation | 高斯溅射 | SD |
| CSD [[35](https://arxiv.org/html/2405.19334v2#bib.bib35)] | ICLR 2024 | Score Distillation | NeRF | SD |
| SweetDreamer [[36](https://arxiv.org/html/2405.19334v2#bib.bib36)] | ICLR 2024 | Score Distillation | NeRF | SD |
| HiFA [[40](https://arxiv.org/html/2405.19334v2#bib.bib40)] | ICLR 2024 | Score Distillation | NeRF | SD |
| AToM [[366](https://arxiv.org/html/2405.19334v2#bib.bib366)] | arXiv 2023 | Score Distillation | Mesh | SD |
| Consistent3D [[367](https://arxiv.org/html/2405.19334v2#bib.bib367)] | arXiv 2023 | Score Distillation | Mesh/NeRF | SD |
| DreamControl [[368](https://arxiv.org/html/2405.19334v2#bib.bib368)] | CVPR 2024 | Score Distillation | NeRF | SD |
| IT3D [[369](https://arxiv.org/html/2405.19334v2#bib.bib369)] | AAAI 2024 | Score Distillation | NeRF | SD |
| Efficientdreamer [[370](https://arxiv.org/html/2405.19334v2#bib.bib370)] | CVPR 2024 | Score Distillation | NeRF | SD |
| GSGEN [[371](https://arxiv.org/html/2405.19334v2#bib.bib371)] | CVPR 2024 | Score Distillation | Gaussian Splatting | SD |
| X-Dreamer [[372](https://arxiv.org/html/2405.19334v2#bib.bib372)] | arXiv 2023 | Score Distillation | Gaussian Splatting | SD |
| HD-Fusion [[373](https://arxiv.org/html/2405.19334v2#bib.bib373)] | WACV 2024 | Score Distillation | Gaussian Splatting | SD |
| LODS [[374](https://arxiv.org/html/2405.19334v2#bib.bib374)] | arXiv 2023 | Score Distillation | Gaussian Splatting | SD |
| Sherpa3d [[375](https://arxiv.org/html/2405.19334v2#bib.bib375)] | CVPR 2024 | Score Distillation | NeRF | SD |
| DreamPropeller [[327](https://arxiv.org/html/2405.19334v2#bib.bib327)] | CVPR 2024 | Score Distillation | NeRF | SD |
| DreamPolisher [[376](https://arxiv.org/html/2405.19334v2#bib.bib376)] | arXiv 2024 | Score Distillation | Gaussian Splatting | SD |
| LLM for 3D generation |  |  |  |  |
| 3D-GPT [[82](https://arxiv.org/html/2405.19334v2#bib.bib82)] | arXiv 2023 | - | Blender Code | GPT-3.5 |
| PoseGPT [[83](https://arxiv.org/html/2405.19334v2#bib.bib83)] | CVPR 2024 | - | Motion Sequences | LLaVA |
| HOLODECK [[377](https://arxiv.org/html/2405.19334v2#bib.bib377)] | CVPR 2024 | - | Scene | GPT-4 |
| LL3DA [[84](https://arxiv.org/html/2405.19334v2#bib.bib84)] | arXiv 2023 | - | PointCloud | GPTV |
| SceneCraft [[353](https://arxiv.org/html/2405.19334v2#bib.bib353)] | arXiv 2023 | - | Blender Code | GPT-3.5 |
| CLIP for 3D editing |  |  |  |  |
| CLIP-NeRF [[138](https://arxiv.org/html/2405.19334v2#bib.bib138)] | CVPR 2022 | CLIP Loss | NeRF | CLIP |
| Blended-NeRF [[356](https://arxiv.org/html/2405.19334v2#bib.bib356)] | ICCVW 2023 | CLIP Loss | NeRF | CLIP |
| SKED [[359](https://arxiv.org/html/2405.19334v2#bib.bib359)] | ICCV 2023 | Score Distillation | NeRF | SD |
| DreamEditor [[360](https://arxiv.org/html/2405.19334v2#bib.bib360)] | SIGGRAPH Asia 2023 | Score Distillation | NeRF | SD |
| Instruct-NeRF2NeRF [[361](https://arxiv.org/html/2405.19334v2#bib.bib361)] | SIGGRAPH Asia 2023 | Score Distillation | NeRF | SD |
| TextDeformer [[357](https://arxiv.org/html/2405.19334v2#bib.bib357)] | TVCG 2022 | Score Distillation | Mesh | SD |
| SINE [[358](https://arxiv.org/html/2405.19334v2#bib.bib358)] | CVPR 2023 | 分数蒸馏 | NeRF | SD |
| Blending-NeRF [[378](https://arxiv.org/html/2405.19334v2#bib.bib378)] | ICCV2023 | CLIP 损失 | NeRF | CLIP |
| CustomNeRF [[379](https://arxiv.org/html/2405.19334v2#bib.bib379)] | CVPR 2024 | 分数蒸馏 | NeRF | SD |
| Paint3D [[380](https://arxiv.org/html/2405.19334v2#bib.bib380)] | arXiv 2023 | - | 网格 | SD |
| 3D Paintbrush [[362](https://arxiv.org/html/2405.19334v2#bib.bib362)] | arXiv 2023 | 分数蒸馏 | NeRF | SD |

## 7 音频生成、理解与编辑

最近，诸如[[97](https://arxiv.org/html/2405.19334v2#bib.bib97)、[100](https://arxiv.org/html/2405.19334v2#bib.bib100)、[106](https://arxiv.org/html/2405.19334v2#bib.bib106)、[102](https://arxiv.org/html/2405.19334v2#bib.bib102)、[86](https://arxiv.org/html/2405.19334v2#bib.bib86)、[104](https://arxiv.org/html/2405.19334v2#bib.bib104)]等创新作品的涌现，展示了 LLMs 在各种音频相关任务中的应用。这些任务涵盖了音频效果创建、语音处理和音乐创作等领域，展示了 LLMs 的多样性。LLMs 在这些领域的角色多种多样，作为复杂系统的核心[[86](https://arxiv.org/html/2405.19334v2#bib.bib86)、[87](https://arxiv.org/html/2405.19334v2#bib.bib87)、[88](https://arxiv.org/html/2405.19334v2#bib.bib88)、[89](https://arxiv.org/html/2405.19334v2#bib.bib89)、[90](https://arxiv.org/html/2405.19334v2#bib.bib90)、[91](https://arxiv.org/html/2405.19334v2#bib.bib91)、[92](https://arxiv.org/html/2405.19334v2#bib.bib92)、[93](https://arxiv.org/html/2405.19334v2#bib.bib93)、[94](https://arxiv.org/html/2405.19334v2#bib.bib94)、[95](https://arxiv.org/html/2405.19334v2#bib.bib95)、[96](https://arxiv.org/html/2405.19334v2#bib.bib96)、[97](https://arxiv.org/html/2405.19334v2#bib.bib97)、[98](https://arxiv.org/html/2405.19334v2#bib.bib98)]、特定任务的调节器[[99](https://arxiv.org/html/2405.19334v2#bib.bib99)、[100](https://arxiv.org/html/2405.19334v2#bib.bib100)、[101](https://arxiv.org/html/2405.19334v2#bib.bib101)]、音频内容标签生成器[[102](https://arxiv.org/html/2405.19334v2#bib.bib102)、[103](https://arxiv.org/html/2405.19334v2#bib.bib103)、[104](https://arxiv.org/html/2405.19334v2#bib.bib104)]、交互环境中的代理[[105](https://arxiv.org/html/2405.19334v2#bib.bib105)、[106](https://arxiv.org/html/2405.19334v2#bib.bib106)、[107](https://arxiv.org/html/2405.19334v2#bib.bib107)、[108](https://arxiv.org/html/2405.19334v2#bib.bib108)、[109](https://arxiv.org/html/2405.19334v2#bib.bib109)、[110](https://arxiv.org/html/2405.19334v2#bib.bib110)]，以及某些方法的灵感来源[[55](https://arxiv.org/html/2405.19334v2#bib.bib55)、[49](https://arxiv.org/html/2405.19334v2#bib.bib49)、[111](https://arxiv.org/html/2405.19334v2#bib.bib111)、[50](https://arxiv.org/html/2405.19334v2#bib.bib50)、[112](https://arxiv.org/html/2405.19334v2#bib.bib112)、[113](https://arxiv.org/html/2405.19334v2#bib.bib113)]。LLMs 在音频领域应用的激增不仅在重新塑造我们与声音和音乐的互动方式，也在音频技术与 AGI 交汇的前沿开辟了新天地。

表 VIII: 可用于基于语言的音频研究的音频数据集。对于每个数据集，我们在每列中列出以下信息：数据集名称（Dataset），论文会议地点（Venue），每个剪辑的平均持续时间（Dur./Clip），剪辑总数（$\#$Clips），总小时数（$\#$Hours），以及数据集领域（Domain）。

| 数据集 | 会议地点 | Dur./Clip | #Clips | #Hours | 领域 |
| --- | --- | --- | --- | --- | --- |
| MagnaTagATune [[381](https://arxiv.org/html/2405.19334v2#bib.bib381)] | ISMIR 2009 | 29 秒 | 25,863 | 208 小时 | 音乐 |
| Librispeech [[382](https://arxiv.org/html/2405.19334v2#bib.bib382)] | ICASSP 2015 | - | - | 1,000 小时 | 语音 |
| Audioset [[383](https://arxiv.org/html/2405.19334v2#bib.bib383)] | ICASSP 2017 | 10 秒 | 2M | - | 音频 |
| MAESTRO [[384](https://arxiv.org/html/2405.19334v2#bib.bib384)] | ICLR 2019 | - | - | 200 小时 | 音乐 |
| Libri-TTS [[385](https://arxiv.org/html/2405.19334v2#bib.bib385)] | INTERSPEECH 2019 | - | - | 585 小时 | 语音 |
| MTG-Jamendo [[386](https://arxiv.org/html/2405.19334v2#bib.bib386)] | ICMLw 2019 | - | 55,000 | - | 音乐 |
| Librilight [[387](https://arxiv.org/html/2405.19334v2#bib.bib387)] | ICASSP 2020 | - | - | 60,000 小时 | 语音 |
| Vggsound [[388](https://arxiv.org/html/2405.19334v2#bib.bib388)] | ICASSP 2020 | 10 秒 | 210,000 | 550 小时 | 音频 |
| WenetSpeech [[389](https://arxiv.org/html/2405.19334v2#bib.bib389)] | ICASSP 2022 | - | - | 22,400 小时 | 语音 |
| Libri-heavy [[390](https://arxiv.org/html/2405.19334v2#bib.bib390)] | ICASSP 2024 | - | - | 50,000 小时 | 语音 |

表 IX: 相关于 LLMs 的音频任务方法汇总：生成（G）、理解（U）和编辑（E）。我们根据 LLMs 的角色将方法分为五种类型：LLMs 作为骨干，LLMs 启发的骨干，LLMs 作为调节器，LLMs 作为代理，LLMs 作为标签器。

| 任务 | 方法 | 会议地点 | LLM 模型 | 领域 |
| --- | --- | --- | --- | --- |
| LLMs 作为骨干 |  |  |  |  |
| G, U | SongComposer [[98](https://arxiv.org/html/2405.19334v2#bib.bib98)] | arXiv 2024 | SongComposer | 音频音乐, 语音 |
| G, U | ChatMusician [[97](https://arxiv.org/html/2405.19334v2#bib.bib97)] | arXiv 2024 | Llama 2 | 符号音乐 |
| G, U | AnyGPT [[391](https://arxiv.org/html/2405.19334v2#bib.bib391)] | arXiv 2024 | Llama 2 | 音频, 音频音乐 |
| G | Boosting Large [[392](https://arxiv.org/html/2405.19334v2#bib.bib392)] | arXiv 2023 | LLaMA | 语音 |
| G, U | Unified-IO 2 [[393](https://arxiv.org/html/2405.19334v2#bib.bib393)] | arXiv 2023 | Unified-IO 2 | 语音, 音频, 音频音乐 |
| G, U | M²UGen [[95](https://arxiv.org/html/2405.19334v2#bib.bib95)] | arXiv 2023 | Llama 2 | 音频音乐 |
| G, U | LauraGPT [[91](https://arxiv.org/html/2405.19334v2#bib.bib91)] | arXiv 2023 | - | 语音 |
| U | LLaSM [[96](https://arxiv.org/html/2405.19334v2#bib.bib96)] | arXiv 2023 | Llama 2 | 语音 |
| G, U | AudioPaLM [[89](https://arxiv.org/html/2405.19334v2#bib.bib89)] | arXiv 2023 | PaLM | 语音 |
| U | Pengi [[88](https://arxiv.org/html/2405.19334v2#bib.bib88)] | NeurIPS 2023 | - | 语音、音频、音频音乐 |
| G, U | Speechgpt [[86](https://arxiv.org/html/2405.19334v2#bib.bib86)] | EMNLP 2023 | LLaMA | 语音 |
| G, U | Sparks [[394](https://arxiv.org/html/2405.19334v2#bib.bib394)] | arXiv 2023 | GPT-4 | 符号音乐 |
| U | Qwen-Audio [[94](https://arxiv.org/html/2405.19334v2#bib.bib94)] | arXiv 2023 | Qwen-LM | 音频、语音、音频音乐 |
| U | SALMONN [[93](https://arxiv.org/html/2405.19334v2#bib.bib93)] | arXiv 2023 | Vicuna | 音频、语音、音频音乐 |
| U | Llark [[92](https://arxiv.org/html/2405.19334v2#bib.bib92)] | arXiv 2023 | Llama 2 | 音频音乐 |
| U | MU-LLaMA [[90](https://arxiv.org/html/2405.19334v2#bib.bib90)] | arXiv 2023 | LLaMA | 音频音乐 |
| U | Speech-LLaMA [[395](https://arxiv.org/html/2405.19334v2#bib.bib395)] | ASRU 2023 | LLaMA | 语音 |
| U | LTU [[87](https://arxiv.org/html/2405.19334v2#bib.bib87)] | ICLR 2024 | LLaMA | 音频 |
| U | Yu et al. [[396](https://arxiv.org/html/2405.19334v2#bib.bib396)] | ICASSP 2024 | Vicuna | 语音 |
| LLMs inspired backbone |  |  |  |  |
| G, E | UniAudio [[113](https://arxiv.org/html/2405.19334v2#bib.bib113)] | arXiv 2023 | - | 音频、语音、音频音乐 |
| G | AudioLM [[112](https://arxiv.org/html/2405.19334v2#bib.bib112)] | IEEE/ACM TASLP | - | 音频 |
| G | MusicGen [[50](https://arxiv.org/html/2405.19334v2#bib.bib50)] | NeurIPS 2023 | - | 音频音乐 |
| G | Jukebox [[111](https://arxiv.org/html/2405.19334v2#bib.bib111)] | arXiv 2020 | - | 音频音乐 |
| G | MusicLM [[49](https://arxiv.org/html/2405.19334v2#bib.bib49)] | arXiv 2023 | - | 音频音乐 |
| G | VALL-E [[55](https://arxiv.org/html/2405.19334v2#bib.bib55)] | arXiv 2023 | - | 语音 |
| U | SICL [[397](https://arxiv.org/html/2405.19334v2#bib.bib397)] | arXiv 2023 | - | 语音 |
| LLMs as conditioner |  |  |  |  |
| G | TANGO [[100](https://arxiv.org/html/2405.19334v2#bib.bib100)] | arXiv 2023 | FLAN-T5 | 音频 |
| G | Music ControlNet [[90](https://arxiv.org/html/2405.19334v2#bib.bib90)] | ICASSP 2024 | ChatGPT | 音频音乐 |
| U | Wu et al. [[101](https://arxiv.org/html/2405.19334v2#bib.bib101)] | ICASSP 2024 | - | 音频 |
| LLMs as agent |  |  |  |  |
| G, E | Loop Copilot [[109](https://arxiv.org/html/2405.19334v2#bib.bib109)] | arXiv 2023 | GPT-4 | 音频音乐 |
| G, U | MusicAgent [[108](https://arxiv.org/html/2405.19334v2#bib.bib108)] | EMNLP (Demos) 2023 | ChatGPT | 音频音乐、符号音乐 |
| G, U | Audiogpt [[106](https://arxiv.org/html/2405.19334v2#bib.bib106)] | AAAI 2024 | GPT-3.5 | 音频、语音、音频音乐 |
| G, U | Hugginggpt [[105](https://arxiv.org/html/2405.19334v2#bib.bib105)] | NeurIPS 2023 | ChatGPT | 音频、语音、音频音乐 |
| G | Wavjourney [[107](https://arxiv.org/html/2405.19334v2#bib.bib107)] | arXiv 2023 | ChatGPT | 音频、音频音乐 |
| G | ComposerX [[398](https://arxiv.org/html/2405.19334v2#bib.bib398)] | arXiv 2024 | GPT-4 | 符号音乐 |
| LLMs 作为标注器 |  |  |  |  |
| G | Audiobox [[104](https://arxiv.org/html/2405.19334v2#bib.bib104)] | arXiv 2023 | LLAMA2 7B | Audio, Speech, Audio music |
| G | Make-An-Audio 2 [[102](https://arxiv.org/html/2405.19334v2#bib.bib102)] | arXiv 2023 | GPT-3.5 | Audio |

![参见说明](img/3aa5d7ae0235d0a558fb54e0bffad5c5.png)

图 8：基于 LLMs 的音频研究的里程碑工作，包括音频生成、理解和编辑。

![参见说明](img/b5dd8a4974f126b9fcaa8e5bd2dcaf58.png)

图 9：根据 LLMs 的不同角色总结 LLMs 相关音频研究的方法。LLMs 作为骨干：语言预训练 LLMs 检查点作为处理文本和音频标记的核心单元，无论是连续的还是离散的。LLMs 作为灵感：与 LLMs 作为骨干不同，这种方法在随机初始化的 LLMs 架构上进行离散音频标记的训练。LLMs 作为条件生成器：LLMs 将文本提示编码为嵌入，这些嵌入作为音频生成器的条件。LLMs 作为代理：LLMs 通过利用外部工具解决用户请求。LLMs 作为标注器：LLMs 将类别标签转换为音频标题。

### 7.1 领域

将 LLMs 整合到音频领域的工作可以分为三类：通用音频声音、音乐和语音。每一类都从生成、理解和编辑三个关键视角提出了挑战和前景。LLMs 相关音频任务的 LLMs 基础方法的关键技术组件总结见表 LABEL:tab:audio_method，相关音频-语言数据集见表 [VIII](https://arxiv.org/html/2405.19334v2#S7.T8 "TABLE VIII ‣ 7 Audio Generation, Understanding and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")。里程碑工作的时间线见图 [8](https://arxiv.org/html/2405.19334v2#S7.F8 "Figure 8 ‣ 7 Audio Generation, Understanding and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")。

#### 7.1.1 通用音频声音

一般音频声音指的是任何可以听到的声音。它包括各种听觉体验，如自然声音（例如鸟鸣和风吹树叶的声音）、人类活动（如交通噪音和机械声）以及其他环境噪音。在过去几个月中，通过应用 LLMs，该领域经历了显著的进步[[100](https://arxiv.org/html/2405.19334v2#bib.bib100), [106](https://arxiv.org/html/2405.19334v2#bib.bib106), [87](https://arxiv.org/html/2405.19334v2#bib.bib87), [102](https://arxiv.org/html/2405.19334v2#bib.bib102), [105](https://arxiv.org/html/2405.19334v2#bib.bib105), [112](https://arxiv.org/html/2405.19334v2#bib.bib112), [101](https://arxiv.org/html/2405.19334v2#bib.bib101), [113](https://arxiv.org/html/2405.19334v2#bib.bib113), [93](https://arxiv.org/html/2405.19334v2#bib.bib93), [94](https://arxiv.org/html/2405.19334v2#bib.bib94), [104](https://arxiv.org/html/2405.19334v2#bib.bib104), [393](https://arxiv.org/html/2405.19334v2#bib.bib393)]。在接下来的章节中，我们将深入探讨音频生成、音频理解和音频编辑的具体领域，以分析这些由 LLMs 推动的发展如何重塑音频领域。

音频理解。一般音频理解涉及分析和解释我们环境中各种声音，而不仅仅是语言和音乐。这项任务包括识别和分类声音（例如区分汽车喇叭声和狗叫声）、识别环境声音中的模式（如检测降雨声或接近的车辆声），甚至理解声音的背景或来源。

一系列开创性的模型，如 LTU (Listen, Think, and Understand) [[87](https://arxiv.org/html/2405.19334v2#bib.bib87)]、SALMONN (Speech Audio Language Music Open Neural Network) [[93](https://arxiv.org/html/2405.19334v2#bib.bib93)]、Qwen-Audio [[94](https://arxiv.org/html/2405.19334v2#bib.bib94)] 和 UNIFIED-IO 2 [[393](https://arxiv.org/html/2405.19334v2#bib.bib393)]，都利用 LLM 作为其音频理解的核心。不同于 LTU [[87](https://arxiv.org/html/2405.19334v2#bib.bib87)] 作为首个关注超越语音的通用音频理解的多模态 LLM，SALMONN [[93](https://arxiv.org/html/2405.19334v2#bib.bib93)] 是第一个能够感知和理解包括语音、音频事件和音乐在内的通用音频输入的多模态 LLM。通过将音频与其他数据模态结合，UNIFIED-IO 2 [[393](https://arxiv.org/html/2405.19334v2#bib.bib393)] 利用 LLM 来增强对各种输入类型之间复杂交互的理解。Qwen-Audio [[94](https://arxiv.org/html/2405.19334v2#bib.bib94)] 通过涵盖 30 多种不同任务和各种音频类型，包括人类语音、自然声音、音乐和歌曲，来提升预训练音频模型的交互能力，从而促进全面的音频理解能力。为了提高用户交互，像 AudioGPT [[106](https://arxiv.org/html/2405.19334v2#bib.bib106)] 和 HuggingGPT [[105](https://arxiv.org/html/2405.19334v2#bib.bib105)] 这样的模型也利用 LLM 作为智能接口。这些工作 [[101](https://arxiv.org/html/2405.19334v2#bib.bib101), [87](https://arxiv.org/html/2405.19334v2#bib.bib87), [94](https://arxiv.org/html/2405.19334v2#bib.bib94), [393](https://arxiv.org/html/2405.19334v2#bib.bib393), [93](https://arxiv.org/html/2405.19334v2#bib.bib93)] 展示了 LLM 如何被用来增强自动音频标注的能力。

LTU [[87](https://arxiv.org/html/2405.19334v2#bib.bib87)] 将音频感知模型 AST [[399](https://arxiv.org/html/2405.19334v2#bib.bib399)] 与 LLaMA [[145](https://arxiv.org/html/2405.19334v2#bib.bib145)] 结合，通过感知到理解的课程来改善音频理解。为此，这项工作还构建了 OpenAQA-5M 数据集，该数据集包含 190 万个封闭式和 370 万个开放式数据对。该数据集有助于 LTU 在自回归框架中的训练。

SALMONN [[93](https://arxiv.org/html/2405.19334v2#bib.bib93)] 通过将基于文本的 LLM 与语音和音频编码器结合起来，处理包括语音、事件和音乐在内的各种音频输入。这种融合提高了 SALMONN 对各种音频现象的理解能力。

UNIFIED-IO 2 [[393](https://arxiv.org/html/2405.19334v2#bib.bib393)] 是第一个自回归的多模态模型，将文本、图像、音频和动作整合到一个统一的框架中。它使用一个单一的编码器-解码器变换模型，将来自不同模态的输入标记化为一个共享的语义空间进行处理。

Qwen-Audio [[94](https://arxiv.org/html/2405.19334v2#bib.bib94)] 将音频语言预训练的规模扩大到包括超过 30 个任务。为了解决在一起训练所有任务和数据集时出现的干扰问题，设计了一个多任务训练框架。该框架使用了一系列层次化标签用于解码器，通过使用共享标签和特定标签来帮助共享知识和防止干扰。在 Qwen-Audio 的基础上进一步发展出的 Qwen-Audio-Chat 可以接收来自不同音频和文本源的输入，支持多轮对话，并支持各种以音频为中心的场景。

AudioGPT [[106](https://arxiv.org/html/2405.19334v2#bib.bib106)] 和 HuggingGPT [[105](https://arxiv.org/html/2405.19334v2#bib.bib105)] 展示了通过 LLMs 驱动的接口协调工具来进行音频理解的应用。AudioGPT 利用 ChatGPT 作为音频和语音应用的核心节点，依赖外部音频系统来实现功能。HuggingGPT 作为一个代理，将 ChatGPT 的语言能力与 Hugging Face 社区的各种 AI 模型结合起来，提高其理解音频内容的能力。

Wu 等人 [[101](https://arxiv.org/html/2405.19334v2#bib.bib101)] 重点推动自动音频字幕生成（AAC）的进展，这是一个致力于为自然和人类活动中的声音生成描述性文本的领域。这项工作通过广泛整合预训练模型和 LLMs 进一步推动了这一发展。Wu 等人使用 BEATS 提取详细的音频特征，并使用 INSTRUCTOR LLM 获取字幕的文本嵌入。此外，Wu 等人引入了一种使用 ChatGPT 创建字幕混合并丰富训练数据（包括数量、复杂性和多样性）的数据增强技术。

音频生成。音频生成是一个新兴领域，专注于建模多样音频内容的创作。LLMs 的应用显著推动了音频生成的发展。文本到音频生成的重要贡献包括 TANGO [[100](https://arxiv.org/html/2405.19334v2#bib.bib100)]、Make-an-Audio 2 [[102](https://arxiv.org/html/2405.19334v2#bib.bib102)]、WavJourney [[107](https://arxiv.org/html/2405.19334v2#bib.bib107)]、AudioLM [[112](https://arxiv.org/html/2405.19334v2#bib.bib112)] 和 Audiobox [[104](https://arxiv.org/html/2405.19334v2#bib.bib104)]。从在 TANGO [[100](https://arxiv.org/html/2405.19334v2#bib.bib100)] 和 Make-an-Audio 2 [[102](https://arxiv.org/html/2405.19334v2#bib.bib102)] 中使用文本嵌入器和扩散模型，到在 WavJourney [[107](https://arxiv.org/html/2405.19334v2#bib.bib107)] 中整合多模态方法，再到 AudioLM [[112](https://arxiv.org/html/2405.19334v2#bib.bib112)] 和 Audiobox [[104](https://arxiv.org/html/2405.19334v2#bib.bib104)] 中的先进标记化，这些举措突显了 LLMs 在推动音频生成技术能力方面的多样性和影响力。

TANGO 使用 FLAN-T5 [[400](https://arxiv.org/html/2405.19334v2#bib.bib400)] 作为文本嵌入器，而 Make-an-Audio 2 则利用预训练的 LLMs 将文本解析成结构化的对，二者都利用基于潜在扩散的模型进行音频合成。WavJourney [[107](https://arxiv.org/html/2405.19334v2#bib.bib107)] 利用 LLM 代理整合各种音频模型，基于文本描述生成连贯的音频内容，包括语音、音乐和音效。AudioLM [[112](https://arxiv.org/html/2405.19334v2#bib.bib112)] 生成高质量音频，强调长期一致性。该方法将输入音频转换为离散的标记，从而使音频生成成为类似于离散空间中的语言建模任务。Audiobox [[104](https://arxiv.org/html/2405.19334v2#bib.bib104)] 使用 LLMs 进行数据构建，包括用高质量、详细的字幕标记音频，并使用 LLMs 自动评估这些注释的质量。然后，Audiobox 使用流匹配技术生成具有精确属性控制的多样音频类型，从语音到音乐和音效。UniAudio [[113](https://arxiv.org/html/2405.19334v2#bib.bib113)] 引入了一个多功能系统，利用 LLMs 在各种输入条件下生成多样化的音频类型，包括语音、声音、音乐和歌唱。与特定任务模型不同，UniAudio 将不同的音频类型及其相关条件标记化为统一序列，从而使 LLMs 能够进行下一标记预测。

#### 7.1.2 音乐

音乐是一种以时间为特征的艺术形式，通常包括诸如旋律、和声、节奏和音色等元素。它是使用乐器和/或人声制作的，通常根据音高（影响旋律和和声）、节奏（包括速度、节拍和发音）、动态（响度的变化）以及音色和音质的声学特性来组织。音乐具有多种功能，包括审美享受、仪式用途和文化身份的表达。在音乐研究领域，音频音乐指的是音乐的实际录音声波，而象征性音乐则涉及音乐的符号表示，比如 MIDI [[401](https://arxiv.org/html/2405.19334v2#bib.bib401)] 文件。对于每种形式，都需要不同的分析和操作方法。我们探索音乐理解、生成和编辑这互相关领域，每个领域利用不同的技术和技术来分析、创造和改进音乐，进一步丰富其文化和艺术影响。

音乐理解。音乐理解涉及对音乐元素（如旋律、和声、节奏和音色）的分析和解释，以识别音乐中的模式、流派、情感和情境意义。它包括对简单主题到复杂结构的分析。

随着像音乐理解 LLaMA（MU-LLaMA） [[90](https://arxiv.org/html/2405.19334v2#bib.bib90)], LLARK [[92](https://arxiv.org/html/2405.19334v2#bib.bib92)], MusicAgent [[108](https://arxiv.org/html/2405.19334v2#bib.bib108)], LyricWhiz [[110](https://arxiv.org/html/2405.19334v2#bib.bib110)], 和 ChatMusician [[97](https://arxiv.org/html/2405.19334v2#bib.bib97)] 等模型的发展，音乐理解领域取得了显著进展。这些模型展示了一系列方法，从分析详细的音乐特征到改善歌词转录。它们突出了 LLMs 如何以不同的方式和应用帮助我们理解和互动音乐。

MU-LLaMA [[90](https://arxiv.org/html/2405.19334v2#bib.bib90)] 使用一个预训练的 MERT 编码器来进行初始音乐表示，然后将其与适配器集成到 LLaMA 模型中。这个过程利用了大语言模型（LLMs）通过分析音乐的综合特征来理解音乐的能力。LLARK [[92](https://arxiv.org/html/2405.19334v2#bib.bib92)] 通过使用一个多模态模型，并结合音乐数据集中精细注释的指令来改进音乐理解。它将生成音乐模型与语言模型结合起来，以统一的方式分析音乐。MusicAgent [[108](https://arxiv.org/html/2405.19334v2#bib.bib108)] 通过 LLMs 帮助音乐理解和生成，自动化任务以满足用户需求，并使用工具执行任务。这简化了流程，鼓励了音乐处理中的探索。总之，MU-LLaMA 关注于音乐特征的分析，LLARK 利用精细标签进行更为通用的理解，而 MusicAgent 强调用户友好的互动。

LyricWhiz [[110](https://arxiv.org/html/2405.19334v2#bib.bib110)] 提出了一个多语言的零样本自动歌词转录方法，在各种音乐类型中表现良好。它使用“Whisper”进行语音识别，并使用“GPT-4”进行上下文感知的注释，充当转录的“耳朵”和“大脑”。这种组合大大降低了英文的词错率，并提供了多语言的有效转录。

音乐生成。AI 音乐生成，特别是使用 LLMs，正在通过创造各种复杂的音乐作品改变行业。值得注意的例子包括 MusicLM [[49](https://arxiv.org/html/2405.19334v2#bib.bib49)]、Jukebox [[111](https://arxiv.org/html/2405.19334v2#bib.bib111)]、MusicGen [[50](https://arxiv.org/html/2405.19334v2#bib.bib50)]、Music ControlNet [[99](https://arxiv.org/html/2405.19334v2#bib.bib99)]、M²UGen [[95](https://arxiv.org/html/2405.19334v2#bib.bib95)]、ChatMusician [[97](https://arxiv.org/html/2405.19334v2#bib.bib97)] 和 SongComposer [[98](https://arxiv.org/html/2405.19334v2#bib.bib98)]。具体来说，这些模型使用了不同的技术，从将 LLMs 作为文本嵌入器到采用扩散过程和自回归 Transformers。

MusicLM [[49](https://arxiv.org/html/2405.19334v2#bib.bib49)]、Jukebox [[111](https://arxiv.org/html/2405.19334v2#bib.bib111)] 和 MusicGen [[50](https://arxiv.org/html/2405.19334v2#bib.bib50)] 代表了文本到音乐生成的重要进展，每一个都从大语言模型（LLMs）的能力中汲取灵感，并采用 Transformer 架构来处理复杂的音频任务。MusicLM [[49](https://arxiv.org/html/2405.19334v2#bib.bib49)] 将条件音乐生成视为一个层次化的序列到序列任务，利用仅解码器的 Transformer 在语义和声学阶段生成音乐。Jukebox [[111](https://arxiv.org/html/2405.19334v2#bib.bib111)] 通过使用多尺度 VQ-VAE 将原始音频压缩为离散代码，然后用自回归 Transformer 对这些代码进行建模，从而解决了长音频上下文的挑战。

另一方面，MusicGen [[50](https://arxiv.org/html/2405.19334v2#bib.bib50)] 直接将大语言模型（LLM）作为文本嵌入器。它将文本标记和旋律条件结合到一个 Transformer 解码器中，然后以自回归的方式处理输入。最后一步涉及一个编解码器模型，该模型将处理后的标记转换回音乐。

Music ControlNet [[99](https://arxiv.org/html/2405.19334v2#bib.bib99)] 使用大语言模型（LLM）作为文本嵌入器，并引入了一种基于扩散的音乐生成模型，提供对音频动态和时间方面的精确控制。受图像领域 ControlNet 像素级控制的启发，它通过从训练音频中得出的旋律、动态和节奏控制，将类似的精度应用于音频。

M²UGen [[95](https://arxiv.org/html/2405.19334v2#bib.bib95)] 引入了一个多模态音乐理解和生成框架，利用大语言模型（LLMs）以及像 MERT、ViT 和 ViViT 这样的预训练模型来分析和创建来自音乐、图像和视频等多种输入的音乐。解码器部分利用 AudioLDM 2 [[47](https://arxiv.org/html/2405.19334v2#bib.bib47)] 和 MusicGen [[50](https://arxiv.org/html/2405.19334v2#bib.bib50)] 生成音乐。

ChatMusician [[97](https://arxiv.org/html/2405.19334v2#bib.bib97)] 和 SongComposer [[98](https://arxiv.org/html/2405.19334v2#bib.bib98)] 都专注于生成符号化音乐，但使用了不同的方法和表现形式。ChatMusician 是一个开源的 LLM，具备内在的音乐能力，利用 Llama2 的持续预训练和微调，采用与文本兼容的音乐表示 ABC 符号。它将音乐视为第二语言，允许它仅通过文本分词器理解和生成音乐，无需外部多模态神经结构。相比之下，SongComposer 使用 MIDI 作为符号化音乐表示，并引入了一种独特的元组设计，将歌词与三个音符属性（音高、时值和休止时长）格式化。该设计确保了音乐符号的正确解释和歌词与旋律之间的精确对齐，使其与 ChatMusician 的方法有所不同。

音乐编辑涉及细化和修改音乐元素，以提高声音质量和艺术表达。Loop Copilot [[109](https://arxiv.org/html/2405.19334v2#bib.bib109)] 将 LLMs 与专门的 AI 音乐模型相结合，创建了一个用于人机音乐循环创作的对话界面。它使用大型语言模型解读用户意图，并通过互动对话指导专门的 AI 模型生成和细化音乐。关键的音乐属性被集中管理，以确保创作过程中的一致质量。

#### 7.1.3 语音

语音特指人类说话时发出的声音。它是语言的口头表现形式，包括单词、句子、语调、语音重音和节奏等各种语言元素。语音是人类沟通的基本方式，因语言、方言、情绪状态和上下文等因素而变化。在人工智能领域，LLMs 在语音理解和生成方面不断进步，帮助机器以更高的准确性和自然性解读和复制人类的口语交流。

语音理解。语音理解使机器能够解读口语。AI 的这一方面不仅捕捉词汇，还能把握说话者的意图和细微差别，进展由 LLMs 推动。该领域的主要贡献包括 SpeechGPT [[86](https://arxiv.org/html/2405.19334v2#bib.bib86)], AudioPaLM [[89](https://arxiv.org/html/2405.19334v2#bib.bib89)], 以及其他研究 [[395](https://arxiv.org/html/2405.19334v2#bib.bib395), [397](https://arxiv.org/html/2405.19334v2#bib.bib397), [396](https://arxiv.org/html/2405.19334v2#bib.bib396)]，展示了 LLMs 在识别和处理不同语境下语音的能力提升。

SpeechGPT[[86](https://arxiv.org/html/2405.19334v2#bib.bib86)]、AudioPaLM[[89](https://arxiv.org/html/2405.19334v2#bib.bib89)] 和 Speech-LLaMA[[395](https://arxiv.org/html/2405.19334v2#bib.bib395)] 代表了语音理解领域的重要进展，它们都利用 LLMs 作为其框架的结构骨架。SpeechGPT[[86](https://arxiv.org/html/2405.19334v2#bib.bib86)] 和 Speech-LLaMA[[395](https://arxiv.org/html/2405.19334v2#bib.bib395)] 特别使用 LLaMA 作为其基础。SpeechGPT 不仅促进了多模态内容的理解和生成，还支持跨模态知识转移。它引入了 SpeechInstruct，一个建立在离散语音表示基础上的大规模跨模态语音指令数据集，突显了其多模态能力。同时，Speech-LLaMA 将语音信号与 LLMs 集成，强调了听觉和语言数据处理的混合。类似地，AudioPaLM[[89](https://arxiv.org/html/2405.19334v2#bib.bib89)] 将 PaLM-2[[402](https://arxiv.org/html/2405.19334v2#bib.bib402)] 和 AudioLM[[112](https://arxiv.org/html/2405.19334v2#bib.bib112)] 的优势结合成一个统一的多模态框架，在语音理解和生成方面表现良好。它保留了来自 AudioLM 的副语言特征，如说话者身份和语调，并将其与 PaLM-2 的文本语言能力融合，展示了一种多模态语音处理方法。

最近在自动语音识别（ASR）领域的研究集中于利用 LLMs 提高模型准确性。Wang 等人[[397](https://arxiv.org/html/2405.19334v2#bib.bib397)] 研究了 Whisper[[403](https://arxiv.org/html/2405.19334v2#bib.bib403)]的上下文学习能力，Whisper 是由 OpenAI 发布的一个 ASR 模型。SICL[[397](https://arxiv.org/html/2405.19334v2#bib.bib397)] 被引入以减少在只有少量标记语音样本的情况下的词错误率（WERs），而无需梯度下降。Yu 等人[[396](https://arxiv.org/html/2405.19334v2#bib.bib396)] 提出了一个结构研究，包括全连接层、多头交叉注意力和 Q-Former 作为连接器，用于将 ASR 模型与 LLMs 集成。

语音生成。语音生成，即将文本或其他输入（如语音提示）转换为口语的过程，随着大语言模型（LLMs）的集成而显著发展。这些模型提高了生成语音的自然性和上下文相关性，使其越来越逼真，类似于人类的语音。

受 LLM 能力启发，Wang 等人引入了 VALL-E [[55](https://arxiv.org/html/2405.19334v2#bib.bib55)]，这是一种在语音生成领域具有变革性的创新方法。VALL-E 利用神经编解码语言模型，采用来自现有神经音频编解码器的离散编码，将文本到语音（TTS）合成重新构建为条件语言建模任务，而不是传统的连续信号回归。基于 VALL-E，Hao 等人通过他们的研究[[392](https://arxiv.org/html/2405.19334v2#bib.bib392)]进一步推动了该领域。他们进行了一项研究，旨在通过将预训练的 LLM 框架 LLaMA/OPT 与 TTS 模型 VALL-E 集成，提升 LLM 的语音生成能力。这项研究展示了语言建模与语音合成技术的结合，旨在产生更加自然和有效的语音输出。

不同于以往的工作，将 LLM 作为骨干，LauraGPT [[91](https://arxiv.org/html/2405.19334v2#bib.bib91)]，由 Wang 等人开发，是一个统一的 GPT 模型，能够处理音频和文本的识别、理解和生成任务。它在语音识别、翻译、文本到语音合成等多种功能上表现良好。

Kakouros 等人提出的另一项研究[[404](https://arxiv.org/html/2405.19334v2#bib.bib404)]探讨了词汇惊讶度的潜力，这是一种衡量词语在上下文中可预测性的指标，以改善语音合成的韵律。

### 7.2 LLM 的角色

语言提供了我们世界的极佳抽象。凭借语言的灵活性和丰富的描述能力，研究人员将语言理解和语言生成统一为一种所谓的生成理解范式。在 LLM 时代，音频研究受益匪浅，LLM 作为桥梁来收集和处理信息，该领域现在能够达到类似的生成理解阶段。广义上，我们将 LLM 的角色分类为以下几种：LLM 作为骨干，LLM 作为调节器，LLM 作为标注器，LLM 作为代理，以及 LLM 启发的骨干。方法总结见图 [9](https://arxiv.org/html/2405.19334v2#S7.F9 "Figure 9 ‣ 7 Audio Generation, Understanding and Editing ‣ LLMs Meet Multimodal Generation and Editing: A Survey")。

#### 7.2.1 LLM 作为骨干

将 LLM 作为骨干意味着利用预训练的 LLM，如 LLaMA，作为系统的核心架构。这些骨干是系统学习和处理能力的核心，与各种网络组件集成并进行微调。在音频领域的多模态 LLM 应用中，LLM 骨干扮演着关键角色。它要么与专门用于模态特定理解或生成的结构耦合，要么利用分词器将音频转换为离散的标记。

当前在 LLM 的研究中，大多采用级联方法，这通常涉及使用特定模态的编码器和/或解码器。在 LTU [[87](https://arxiv.org/html/2405.19334v2#bib.bib87)]中，Yuan 等人建议使用音频频谱变换器（AST） [[399](https://arxiv.org/html/2405.19334v2#bib.bib399)]，这是一种用 CAV-MAE [[405](https://arxiv.org/html/2405.19334v2#bib.bib405)]预训练的变换器编码器。该编码器的表示被聚合并输入到 LLaMA-7B 主干中。这些音频预训练表示随后与相应的文本配对。为了微调 LLM 主干，使用 LoRA 适配器 [[232](https://arxiv.org/html/2405.19334v2#bib.bib232)]，任务是基于音频表示预测文本对。Pengi [[88](https://arxiv.org/html/2405.19334v2#bib.bib88)]遵循类似的范式。Soham 等人称之为“音频-文本到文本”格式。除了一个 CLAP [[139](https://arxiv.org/html/2405.19334v2#bib.bib139)]音频编码器外，它还使用文本编码器来编码任务指令。音频表示以及文本指令表示一起作为前缀输入到 LLM 中。然后，LLM 被训练以预测配对的文本输出，例如声音描述。LTU 和 Pengi 在封闭式音频理解任务以及一定程度的开放式音频理解任务中表现出改进。类似的方法也可以在 LLaSM [[96](https://arxiv.org/html/2405.19334v2#bib.bib96)]、Mu-LLaMA [[90](https://arxiv.org/html/2405.19334v2#bib.bib90)]、MusicLingo [[406](https://arxiv.org/html/2405.19334v2#bib.bib406)]、Llark [[92](https://arxiv.org/html/2405.19334v2#bib.bib92)]、Qwen-Audio [[94](https://arxiv.org/html/2405.19334v2#bib.bib94)]中找到。流行的音频编码器可能包括 CLAP [[139](https://arxiv.org/html/2405.19334v2#bib.bib139)]、MERT [[407](https://arxiv.org/html/2405.19334v2#bib.bib407)]、Whisper [[397](https://arxiv.org/html/2405.19334v2#bib.bib397)]、AST [[399](https://arxiv.org/html/2405.19334v2#bib.bib399)]。

除了专注于理解的模型，还有一些研究扩展到了生成领域。其中一部分研究采纳了级联方法的设计理念，除了音频编码器外，还引入了音频解码器。例如，在 M²UGen [[95](https://arxiv.org/html/2405.19334v2#bib.bib95)]中，Atin 等人适配了 MERT 编码器和 Audioldm2 [[47](https://arxiv.org/html/2405.19334v2#bib.bib47)] / MusicGen [[50](https://arxiv.org/html/2405.19334v2#bib.bib50)]解码器。输出投影层将 LLaMA2 模型的输出嵌入映射到音乐解码器。在 NExT-GPT [[142](https://arxiv.org/html/2405.19334v2#bib.bib142)]中观察到类似的方法，这是一种最近提出的任意到任意的多模态语言模型。

然而，级联方法需要训练异质神经结构。在数据和计算资源充足的情况下，这些异质神经结构可能会导致训练效率下降和系统可扩展性降低。最近，一种统一的方法引起了研究人员的关注。这种方法通常需要使用音频编解码器 [[408](https://arxiv.org/html/2405.19334v2#bib.bib408), [409](https://arxiv.org/html/2405.19334v2#bib.bib409)]，将原始音频标记化为离散的标记，然后将其展平成一维序列输入到 LLM 中。这要求 LLM 的词汇表中包括音频标记，从而需要扩展 LLM 词汇表，类似于将音频作为新语言集成到 LLM 中。这种方法采用统一的 LLM 结构，促进了可扩展性。AudioPaLM [[89](https://arxiv.org/html/2405.19334v2#bib.bib89)]、LauraGPT [[91](https://arxiv.org/html/2405.19334v2#bib.bib91)]、SpeechGPT [[86](https://arxiv.org/html/2405.19334v2#bib.bib86)] 遵循这一范式。

#### 7.2.2 LLMs 作为调节器

在这种设置中，LLMs 通常作为文本嵌入器，将输入文本编码以调节系统的响应或输出，从而实现对音频数据的更细致和具有上下文感知的处理。

Tango [[100](https://arxiv.org/html/2405.19334v2#bib.bib100)] 遵循这一范式。它包括三个主要组件：一个文本编码器，一个潜在扩散模型 (LDM)，和一个 Mel-Spectrogram/Audio 变分自编码器 (VAE)。文本编码器是 Flan-T5，它将音频的输入文本提示转换为文本表示。然后利用该表示通过逆扩散从标准高斯噪声构建潜在音频表示或音频先验。接着，Mel-Spectrogram VAE 的解码器从潜在音频表示中生成 Mel-Spectrogram。最后，将此 Mel-Spectrogram 输入到语音合成器中生成最终的音频输出。MusicGen [[50](https://arxiv.org/html/2405.19334v2#bib.bib50)] 遵循类似的范式。研究测试了 T5 和 Flan-T5 模型及 CLAP，发现 T5 编码器作为文本调节器在与文本输入相关的主观测试中取得了最高的相关性评分。

#### 7.2.3 LLMs 作为标签器

目前，大多数大规模音频数据集，如 AudioSet [[383](https://arxiv.org/html/2405.19334v2#bib.bib383)] 和 VGGSound [[388](https://arxiv.org/html/2405.19334v2#bib.bib388)]，仅用类别标签进行标注，类似于 ImageNet [[410](https://arxiv.org/html/2405.19334v2#bib.bib410)]。希望进行文本到音频任务的研究人员被迫将这些类别标签转换为完整的音频描述，也称为音频标注。一个普遍的方法是利用 LLMs 实现这一转换。

一个常见的文本描述增强管道首先是手动为标注的音频数据集创建描述模板，从而将音频类别解析为更统一格式的描述。随后的步骤利用自我指令方法，使用诸如 ChatGPT [[7](https://arxiv.org/html/2405.19334v2#bib.bib7)] 这样的 LLMs，它们能够按照指令改述这些描述，通常利用自我指令 [[411](https://arxiv.org/html/2405.19334v2#bib.bib411)] 技术进一步丰富数据集。

#### 7.2.4 LLMs 作为代理

在“LLMs 作为代理”中，LLMs 被用来与各种工具接口，协调多个功能以完成不同的任务。这一角色突显了 LLMs 在管理和执行复杂、多维操作方面的多功能性。

与 LLMs 的沟通可以通过多种方式进行。一种明显直接但有效的方法是通过文本接口。在多模态 LLM 音频研究的初期，黄等人引入了 AudioGPT。该系统利用先进的音频基础模型，处理如声音检测、音频到文本转换、语音识别和语音翻译等任务。从这些音频处理得到的数据然后被转化为文本，与 LLM 互动无缝集成。在这个框架下，任务分析、模型分配和响应生成都通过文本操作进行。AudioGPT 的灵感来源于其同时期的工作 HuggingGPT，它采用了类似的方法。HuggingGPT 使用 LLMs 调用 Hugging Face 上的各种模型，Hugging Face 是一个托管各种机器学习模型的平台。同样，MusicAgent 提议通过集成各种工具和自主工作流来简化 AI 驱动的音乐处理，主要由 LLMs 如 ChatGPT 推动。它具备来自 Hugging Face、GitHub 和各种网络 API 的多样化工具集。支持音乐分类、音乐分离、歌词识别等任务。

#### 7.2.5 LLMs 灵感背骨

随着下一个令牌预测范式在语言建模中的成功，音频领域也寻求通过将音频离散化为令牌进行建模。研究人员旨在在音频令牌上实现类似于 LLMs 的突现能力，如上下文学习和思维链能力。目前，已经确认可以通过音频令牌的语言建模预训练实现适度的上下文学习能力。

在 VALL-E[[55](https://arxiv.org/html/2405.19334v2#bib.bib55)]中，研究人员将自回归和非自回归语言模型结合起来，以对编码的标记进行建模。得益于残差向量量化（RVQ）建模[[408](https://arxiv.org/html/2405.19334v2#bib.bib408)]的声学信息，VALL-E 可以仅通过短音频和文本提示继续语音，同时保持说话者的音色、韵律和声学环境，并遵循文本限制。在 AudioLM[[112](https://arxiv.org/html/2405.19334v2#bib.bib112)]中，研究人员发现对基于 RVQ 的声学标记进行无条件训练未能实现语义级一致性。因此，他们提出引入基于自监督学习（SSL）表示的语义标记。这些来自 SSL 预训练教师的表示包含丰富的语义信息，对这些表示进行 k-means 聚类可以得到一个 k-means 量化器，从而提取训练集的语义标记。对这些语义标记进行语言建模能实现更好的语义一致性，使无条件的语音续写保持语义连贯。

## 8 工具增强的多模态代理

![参见说明文字](img/3056f7567a8d8df15b27f17313e6bd21.png)

图 10：工具增强的多模态代理的流程图。

![参见说明文字](img/c83e69920eb76c9c681272549a16b4d8.png)

图 11：关注于多模态生成和编辑的多模态代理的里程碑。

在过去几个月中，许多被称为工具增强型大型语言模型的工作[[412](https://arxiv.org/html/2405.19334v2#bib.bib412)、[413](https://arxiv.org/html/2405.19334v2#bib.bib413)、[414](https://arxiv.org/html/2405.19334v2#bib.bib414)、[105](https://arxiv.org/html/2405.19334v2#bib.bib105)、[117](https://arxiv.org/html/2405.19334v2#bib.bib117)、[115](https://arxiv.org/html/2405.19334v2#bib.bib115)、[415](https://arxiv.org/html/2405.19334v2#bib.bib415)、[416](https://arxiv.org/html/2405.19334v2#bib.bib416)、[417](https://arxiv.org/html/2405.19334v2#bib.bib417)、[418](https://arxiv.org/html/2405.19334v2#bib.bib418)、[114](https://arxiv.org/html/2405.19334v2#bib.bib114)、[419](https://arxiv.org/html/2405.19334v2#bib.bib419)、[420](https://arxiv.org/html/2405.19334v2#bib.bib420)、[421](https://arxiv.org/html/2405.19334v2#bib.bib421)、[422](https://arxiv.org/html/2405.19334v2#bib.bib422)、[423](https://arxiv.org/html/2405.19334v2#bib.bib423)、[424](https://arxiv.org/html/2405.19334v2#bib.bib424)、[425](https://arxiv.org/html/2405.19334v2#bib.bib425)、[426](https://arxiv.org/html/2405.19334v2#bib.bib426)、[427](https://arxiv.org/html/2405.19334v2#bib.bib427)、[428](https://arxiv.org/html/2405.19334v2#bib.bib428)、[116](https://arxiv.org/html/2405.19334v2#bib.bib116)、[429](https://arxiv.org/html/2405.19334v2#bib.bib429)、[430](https://arxiv.org/html/2405.19334v2#bib.bib430)]作为人机交互中的一个有前景的方向而出现。它们使大型语言模型能够使用外部工具来增强模型的能力。其中，几项工作[[105](https://arxiv.org/html/2405.19334v2#bib.bib105)、[116](https://arxiv.org/html/2405.19334v2#bib.bib116)、[117](https://arxiv.org/html/2405.19334v2#bib.bib117)、[115](https://arxiv.org/html/2405.19334v2#bib.bib115)、[118](https://arxiv.org/html/2405.19334v2#bib.bib118)、[114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 通过调用相应的工具，能够在自然语言之外扩展大型语言模型到其他模态。这些开创性的工作能够交互式地生成或编辑图像、视频和音频，与那些仅专注于优化特定任务（例如图像生成或视频生成）的专家模型形成对比。本节主要关注审视近期旨在通过增强外部工具来扩展大型语言模型到多模态生成的工作。

### 8.1 动机

已知大型语言模型（LLMs）在访问和处理其训练数据中没有的信息方面存在局限性，例如短暂的、变化的或私密的数据。例如，大型语言模型可能无法回答涉及频繁更新的事实知识的问题，例如当前的天气或股票价格。

为了克服这些限制，一些研究提出了用外部工具或 API 增强 LLMs，如检索增强生成（RAG）、计算器或视觉基础模型，这些可以为 LLMs 提供额外的信息或功能。这些工具可以通过自然语言指令被 LLMs 调用，结果可以集成到 LLMs 的输出中。例如，LLM 可以使用天气 API 获取给定位置的当前温度和湿度，并用这些信息生成自然语言响应。工具增强范式的有效性已被许多研究验证[[412](https://arxiv.org/html/2405.19334v2#bib.bib412), [413](https://arxiv.org/html/2405.19334v2#bib.bib413)]。在实践中，微软 Copilot¹¹1[`www.microsoft.com/en/microsoft-copilot`](https://www.microsoft.com/en/microsoft-copilot) 通过各种工具增强，已被集成到包括 Bing、Edge 和 Windows 操作系统在内的应用程序中，这极大地提升了用户体验。OpenAI 也发布了 Function Calling²²2[`platform.openai.com/docs/assistants/tools`](https://platform.openai.com/docs/assistants/tools) 服务，可以让助手访问 OpenAI 托管的工具，如代码解释器和知识检索，或创建自己的工具。

众所周知，LLMs 不能生成或编辑其他模态的内容，如图像、视频或音频，这些对于创造性目的很有帮助。受到工具增强的 LLMs 的启发，一些先驱者开发了多模态代理，可以控制跨不同模态的各种工具，如图像、视频和音频。通过将 LLMs 与外部工具结合，可以实现更自然和多样化的人机交互，以及更强大和创造性的应用。

### 8.2 方法

如图[10](https://arxiv.org/html/2405.19334v2#S8.F10 "Figure 10 ‣ 8 Tool-augmented Multimodal Agents ‣ LLMs Meet Multimodal Generation and Editing: A Survey")所示，增强工具的多模态交互 LLMs 的一般框架包括三个主要阶段：1）任务规划，将 LLM 作为控制器，将自然语言指令解释为工具调用方案。具体来说，这一阶段的核心目标是决定使用哪些工具并为工具准备参数。在这一阶段，选择的工具被组织成工具调用方案，指定工具调用的顺序和工具的输入。2）任务执行，包含许多外部多模态工具，如图像生成、视频编辑或音频合成。根据任务规划中获得的调用方案调用这些工具。值得注意的是，大多数工具基于深度学习模型，包括稳定扩散[[30](https://arxiv.org/html/2405.19334v2#bib.bib30)]、ControlNet[[67](https://arxiv.org/html/2405.19334v2#bib.bib67)]、Blip[[213](https://arxiv.org/html/2405.19334v2#bib.bib213)]、LLaVA[[151](https://arxiv.org/html/2405.19334v2#bib.bib151)]，*等等*。3）响应生成，通过使用任务执行中的输出提示 LLM 以生成用户友好的响应。整个系统连接了 LLM 和外部多模态工具，这不仅增强了 LLM 的能力，还显著改善了用户体验。

现有工作的主要区别在于它们如何执行任务规划。为此，增强工具的多模态交互的 LLMs 大致可以分为两类：（1）免训练方法[[116](https://arxiv.org/html/2405.19334v2#bib.bib116), [105](https://arxiv.org/html/2405.19334v2#bib.bib105), [117](https://arxiv.org/html/2405.19334v2#bib.bib117), [431](https://arxiv.org/html/2405.19334v2#bib.bib431)]，和（2）指令调整方法[[115](https://arxiv.org/html/2405.19334v2#bib.bib115), [114](https://arxiv.org/html/2405.19334v2#bib.bib114), [118](https://arxiv.org/html/2405.19334v2#bib.bib118), [432](https://arxiv.org/html/2405.19334v2#bib.bib432)]。演变路径见图[11](https://arxiv.org/html/2405.19334v2#S8.F11 "Figure 11 ‣ 8 Tool-augmented Multimodal Agents ‣ LLMs Meet Multimodal Generation and Editing: A Survey")。此外，表[XI](https://arxiv.org/html/2405.19334v2#S8.T11 "TABLE XI ‣ 8.3 Demonstrations ‣ 8 Tool-augmented Multimodal Agents ‣ LLMs Meet Multimodal Generation and Editing: A Survey")总结了与多模态代理相关的工作。接下来，我们将详细阐述这两种方法的细节。

#### 8.2.1 免训练方法

无需训练的方法[[431](https://arxiv.org/html/2405.19334v2#bib.bib431)、[433](https://arxiv.org/html/2405.19334v2#bib.bib433)、[105](https://arxiv.org/html/2405.19334v2#bib.bib105)、[116](https://arxiv.org/html/2405.19334v2#bib.bib116)、[117](https://arxiv.org/html/2405.19334v2#bib.bib117)、[434](https://arxiv.org/html/2405.19334v2#bib.bib434)]主要依赖于提示工程，例如，ReAct [[435](https://arxiv.org/html/2405.19334v2#bib.bib435)]，上下文学习 [[436](https://arxiv.org/html/2405.19334v2#bib.bib436)]，以提升 LLMs 的推理能力。这些方法在许多任务中表现出了其有效性。

Gupta *等人* [[431](https://arxiv.org/html/2405.19334v2#bib.bib431)] 和 Surís *等人* [[433](https://arxiv.org/html/2405.19334v2#bib.bib433)] 提出了一个基于代码生成的方法，用于解决给定自然语言指令的复杂和组合视觉任务。这两种方法主要关注图像感知和视觉问答。以[[431](https://arxiv.org/html/2405.19334v2#bib.bib431)]为例，他们开发了 VISPROG 框架，包含两个主要组件：程序生成器和程序执行器。程序生成器使用大型语言模型（GPT-3）根据自然语言指令生成类似 Python 的模块化程序。作者向 GPT-3 提供指令和所需的高级程序对，以及新的指令。GPT-3 随后生成一个可以在输入图像上执行的程序以完成描述的任务。程序的每一行调用 VISPROG 支持的 20 个模块之一，例如物体检测、分割、图像编辑、知识检索等。然后，程序执行器在输入图像上执行生成的程序，并产生输出和视觉理由。执行器逐行执行程序，并使用指定的输入调用正确的模块。这些模块作为 Python 类实现，利用现成的计算机视觉模型、图像处理例程或 Python 函数。执行器还会在每一步后更新程序状态，包括输出变量的名称和值。注意到 VISPROG 没有明确的第三阶段，而是直接将工具的输出返回给用户。这项工作为多模态人机交互开辟了新方向，并激发了后续研究。

与 VISPROG [[431](https://arxiv.org/html/2405.19334v2#bib.bib431), [433](https://arxiv.org/html/2405.19334v2#bib.bib433)] 相比，Visual ChatGPT [[116](https://arxiv.org/html/2405.19334v2#bib.bib116)] 并不会直接生成代码。它将大型语言模型（ChatGPT）与各种视觉基础模型（VFM）结合，能够进行文本和图像的对话互动。为了实现这一点，Wu *et al.* [[116](https://arxiv.org/html/2405.19334v2#bib.bib116)] 设计了一个 Prompt Manager，弥合了 ChatGPT 与 VFM 之间的差距。Prompt Manager 将所有非语言信号转换为 ChatGPT 可以理解和处理的语言提示。本质上，Visual ChatGPT 通过 ReAct [[435](https://arxiv.org/html/2405.19334v2#bib.bib435)] 进行任务规划，这是增强 LLM 工具的最简单直接的方法。ReAct 扩展了 Chain-of-Thought 的工具使用，每个思考后立即执行工具。这意味着系统交替进行第 1 阶段和第 2 阶段。此外，为了准确调用工具，每个工具配备了精心制作的自然语言提示，指导 LLM 如何使用它。在实践中，可以使用类似“请使用名为 ImageBind 的工具生成一张戴帽子的猫的图像”的提示来调用图像生成工具，并期望系统返回图像路径作为响应。这种方法不需要对 LLM 进行任何修改或重新训练，可以利用现有的预训练 LLM，如 GPT-3 或 ChatGPT。InternGPT [[117](https://arxiv.org/html/2405.19334v2#bib.bib117)] 与 Visual ChatGPT 具有类似的流程，但支持指向设备。因此，InternGPT 提供了更多有趣和多样的互动模式，包括点击和绘图。例如，在点击操作被触发后，InternGPT 利用 SAM [[437](https://arxiv.org/html/2405.19334v2#bib.bib437)] 选择所选的语义区域，这可以用来移除或替换对象。此外，InternGPT 支持用户直接绘制草图，基于此生成新图像。 

表 X：用于训练或评估模型的多模态代理的指令样本。

|       图像 |
| --- |
| 1\. 你能去掉图像 _1.png 中的狗吗？ |
| 2\. 你能创建一张描绘前景中一家人正在野餐的新图像吗？ |
| 3\. 基于名为 seg.png 的分割图生成一张新图像，新图像应展示美丽的风景。 |
| 4\. 利用姿势图 pose.png 生成一张新图像，图中应展示森林中的一个舒适小屋，旁边有篝火、树木和一对正在烤棉花糖的情侣。 |
| 5\. 利用给定图像中的分割，生成一张展示神奇森林的图像，图中有发光的蘑菇和飞舞的仙女。 |
| 视频 |
| 1\. 你能去掉视频 _1.mp4 中的狗吗？ |
| 2\. 你能提供一个与给定图像相关的视频吗？ |
| 3\. 请给我从这个文件 image_2.png 衍生的新视频？ |
| 4\. 制作一个展示湖泊及其周围植被的宁静风景的视频。 |
| 5\. 如果你能用名为 aud_1.wav 的音频文件为 video_1.mp4 配音，我将不胜感激。 |
| 音频 |
| 1\. 你能创建一首视觉上表现图像的歌曲吗？ |
| 2\. 你需要为 video_3.mp4 生成一段背景音乐。 |
| 3\. 请根据给定提示生成一段音乐：一首 80 年代风格的动感流行歌曲，背景有重鼓。 |
| 4\. 我想为 video_4.mp4 创建一段背景音乐，并用这段音乐为视频配音。 |
| 5\. 将以下文本转化为语音：“希望是那栖息在灵魂中的羽毛之物，唱着没有词的旋律，从不停止。” |
|   |

![参考说明](img/e8558e92e4e2dd65a15c6abd02f7105c.png)

图 12: 我们展示了针对不同方法的图像生成案例研究。

![参考说明](img/ad7a264d510c6691d57fa3b785a103a1.png)

图 13: 通过点击进行的交互式图像编辑。

![参考说明](img/af21439121a8b5ca2d01bbfe4a931ed3.png)

图 14: 从给定图像生成音频的示例。

![参考说明](img/7646e3cdcd6f5cae929ec71e9975c7cf.png)

图 15: 此示例展示了多模态智能体 [[114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 从指令生成多个输出。它首先根据文本提示生成图像，然后从生成的图像创建视频。

![参考说明](img/4ea9c30db839988ec7a6e4183b381114.png)

图 16: 可视化天气条件的多模态生成示例。

此外，HuggingGPT [[105](https://arxiv.org/html/2405.19334v2#bib.bib105)] 基于一个大型语言模型，作为核心控制器来管理和组织来自机器学习社区（如 Hugging Face）的专家模型的合作。HuggingGPT 包括四个阶段：任务规划、模型选择、任务执行和响应生成。HuggingGPT 将模型选择与任务规划分开。在任务规划阶段，Shen *等人* [[105](https://arxiv.org/html/2405.19334v2#bib.bib105)] 使用 ChatGPT 将用户请求解析为任务列表，并确定任务之间的执行顺序和资源依赖关系。在模型选择阶段，他们使用 ChatGPT 根据 Hugging Face 上提供的模型描述为每个任务分配合适的模型。在任务执行阶段，系统调用并执行选定的模型。最后，响应生成阶段使用 ChatGPT 整合所有模型的预测，并生成用户的响应。值得注意的是，HuggingGPT 在任务规划和模型选择中使用了上下文学习。因此，它在一些简单案例中表现良好，但几乎总是无法解决难题。不同于图 [10](https://arxiv.org/html/2405.19334v2#S8.F10 "Figure 10 ‣ 8 Tool-augmented Multimodal Agents ‣ LLMs Meet Multimodal Generation and Editing: A Survey")，HuggingGPT 实际上将任务规划分解为两个步骤，即一个步骤用于解析任务，另一个步骤用于识别每个任务的工具。HuggingGPT 还引入了一些技术来处理资源依赖关系、混合端点和提示设计。

限制。无训练方法存在一些缺点。首先，这些方法依赖于预训练的语言模型（LLMs）的可用性和可访问性，而这些模型通常是专有的，使用起来成本高昂。其次，这些方法需要手动设计和调整提示，这可能既耗时又容易出错。最后，这些方法假设 LLMs 具有足够的知识和能力来使用工具。然而，这通常无法解决复杂问题。此外，我们发现直接使用现成的 LLMs 在将工具集扩展到大规模时会导致性能下降。这是因为 LLMs 通常并未为此目的进行训练。

#### 8.2.2 指令调整方法

指令调优方法 [[413](https://arxiv.org/html/2405.19334v2#bib.bib413), [414](https://arxiv.org/html/2405.19334v2#bib.bib414), [412](https://arxiv.org/html/2405.19334v2#bib.bib412)] 涉及训练语言模型以更准确地遵循人类指令，这可以大幅提高 LLM 的工具使用能力。因此，一些多模态代理 [[115](https://arxiv.org/html/2405.19334v2#bib.bib115), [118](https://arxiv.org/html/2405.19334v2#bib.bib118), [114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 在任务规划的第一阶段微调 LLM，以便在不同模态之间使用工具。在这种方法中，关键在于如何生成训练 LLM 的指令语料库。

以 GPT4Tools [[115](https://arxiv.org/html/2405.19334v2#bib.bib115)] 为例，它的目标是通过从高级 LLM（如 LLaMA [[145](https://arxiv.org/html/2405.19334v2#bib.bib145)] 和 OPT [[438](https://arxiv.org/html/2405.19334v2#bib.bib438)]) 自我指导，来高效地使 LLM 使用多模态工具，如视觉模型。第一个挑战是如何构建训练语料库。杨*等人* [[115](https://arxiv.org/html/2405.19334v2#bib.bib115)] 采用了一种简单但有效的方法，通过提示高级 LLM（如 ChatGPT）以不同的多模态上下文和工具描述，生成一个指令跟随数据集。接下来，他们从原始数据中筛选出类似或无效的指令，得到了 41K 条数据。GPT4Tools 通过引入负样本（不需要工具使用的指令）和上下文样本（涉及多个回合或动作的指令）来增强数据。最后，这项工作构建了一个包含 71.4K 指令-响应对的数据集，涵盖了 31 种用于各种视觉任务的工具。我们在表 [X](https://arxiv.org/html/2405.19334v2#S8.T10 "TABLE X ‣ 8.2.1 Training-free Methods ‣ 8.2 Methods ‣ 8 Tool-augmented Multimodal Agents ‣ LLMs Meet Multimodal Generation and Editing: A Survey") 中展示了一些指令示例。数据集构建后，GPT4Tools 采用低秩适应 (LoRA) 来微调开源 LLM，使其能够用于各种视觉任务，如视觉理解和图像生成。由于 LLM 在指令语料库上进行了调优，工具使用能力显著提高。

李*等人* [[118](https://arxiv.org/html/2405.19334v2#bib.bib118)] 提出了 ModelScope-Agent，利用 ModelScope 中的模型来增强开源 LLM。在这项工作中，作者还提供了一个名为 MSAgent-Bench 的工具数据集。与上述方法不同，李*等人* [[118](https://arxiv.org/html/2405.19334v2#bib.bib118)] 设计了一个带有记忆控制的工具检索模块，以识别工具而不是直接提示 LLM。这种设计使整个系统更加灵活和可扩展。

刘*等*[[114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 并没有直接训练一个 LLM 作为控制器来生成解决方案，而是训练了一个语言模型来执行工具无关的任务分解，并提出了 Thoughts-on-Graph (ToG) 以为每个子任务生成解决方案，这使得 LLM 能够使用各种工具来解决复杂的现实世界任务，如文本、图像、音频和视频。本文认为在工具增强的 LLM 中存在三大主要挑战：a) 模糊的用户提示，b) 不准确的工具选择和参数设置，c) 低效的工具调度。为此，刘*等*[[114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 提出了 ControlLLM，一个强大的框架，包括三个组件：任务分解，可以将用户输入解析为几个具有特定输入和输出的子任务；Thoughts-on-Graph (ToG) 模式，通过深度优先搜索 (DFS) 算法在预建的工具图上找到最佳解决路径；执行引擎配备了强大的工具箱，可以解释解决路径并在不同计算设备上高效调度工具。ControlLLM 支持许多多模态工具，并提供了用户友好的演示界面。

紧接着 ControLLM，王*等*[[432](https://arxiv.org/html/2405.19334v2#bib.bib432)] 开发了一个名为 MLLM-Tool 的多模态工具代理系统。与之前的工作[[115](https://arxiv.org/html/2405.19334v2#bib.bib115), [118](https://arxiv.org/html/2405.19334v2#bib.bib118), [114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 相比，这是第一个训练大型多模态模型用于工具学习的工作。在任务规划中，他们利用基于 ImageBind [[141](https://arxiv.org/html/2405.19334v2#bib.bib141)] 的多模态编码器以及一个投影层来提取六种模态的统一嵌入空间：文本、图像、视频、音频、语音和音乐。然后，将结合多模态嵌入的用户指令输入到语言模型中，以预测相应的 API 名称。

限制。目前，指令训练方法仍然存在一些不足。一方面，训练一个大型语言模型（LLM）对于大多数研究人员来说成本极高。尽管已经提出了许多高效训练 LLM 的方法[[232](https://arxiv.org/html/2405.19334v2#bib.bib232), [439](https://arxiv.org/html/2405.19334v2#bib.bib439), [440](https://arxiv.org/html/2405.19334v2#bib.bib440)]，如 LoRA 及其变体，但仍需在性能和训练成本之间做出权衡。另一方面，还需要生成多样的指令语料库以用于训练。Self-instruct[[411](https://arxiv.org/html/2405.19334v2#bib.bib411)]是一种有效的方法，可以促使 LLM 从种子指令自动生成更多指令。然而，控制生成语料库的质量非常困难，这不可避免地对训练 LLM 产生负面影响。此外，仍然存在一个待解决的开放性问题，即如何使从封闭语料库中学习的 LLM 能够对未见过的指令进行泛化。这个问题涉及语言模型是否能够生成在训练语料库中未出现过的创新解决方案，以解决更复杂的问题。

### 8.3 演示

一些作品[[116](https://arxiv.org/html/2405.19334v2#bib.bib116), [105](https://arxiv.org/html/2405.19334v2#bib.bib105), [117](https://arxiv.org/html/2405.19334v2#bib.bib117), [114](https://arxiv.org/html/2405.19334v2#bib.bib114)]不仅开放了源代码，还发布了在线演示。因此，在本节中，我们通过使用它们提供的在线演示简单展示一些作品的功能。

目前，几种多模态代理[[116](https://arxiv.org/html/2405.19334v2#bib.bib116), [105](https://arxiv.org/html/2405.19334v2#bib.bib105), [117](https://arxiv.org/html/2405.19334v2#bib.bib117), [114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 可以与图像互动，或通过生成、编辑或理解图像来实现。例如，它们将图像生成或编辑模型，如 Stable Diffusion [[30](https://arxiv.org/html/2405.19334v2#bib.bib30)]、ControlNet [[67](https://arxiv.org/html/2405.19334v2#bib.bib67)] 和 InstructPix2Pix [[249](https://arxiv.org/html/2405.19334v2#bib.bib249)]，与 LLMs 增强结合，这些模型可以根据文本提示创建或修改图像。如图[12](https://arxiv.org/html/2405.19334v2#S8.F12 "图 12 ‣ 8.2.1 无需训练的方法 ‣ 8.2 方法 ‣ 8 工具增强多模态代理 ‣ LLMs 与多模态生成和编辑：一项调查")所示，我们通过图像生成示例对 Visual ChatGPT、HuggingGPT、InternGPT 和 ControlLLM 进行比较，这有助于直接研究它们的能力。有趣的是，HuggingGPT 将指令拆分为两个任务，并返回两个生成的图像。ControlLLM 生成的图像与提供的指令更为一致。我们可以发现，由于系统中使用的基础模型不同，不同方法之间存在轻微的性能差距。与如 Stable Diffusion [[30](https://arxiv.org/html/2405.19334v2#bib.bib30)]等 text2image 模型相比，多模态代理能够以互动的方式生成生动的图像，而不是僵硬地将图像返回给用户。此外，InternGPT 和 ControlLLM 支持指向设备作为输入，以增强互动性。如图[13](https://arxiv.org/html/2405.19334v2#S8.F13 "图 13 ‣ 8.2.1 无需训练的方法 ‣ 8.2 方法 ‣ 8 工具增强多模态代理 ‣ LLMs 与多模态生成和编辑：一项调查")所示，以 ControlLLM 为例，用户可以点击图像中的感兴趣区域，然后使用 SAM [[437](https://arxiv.org/html/2405.19334v2#bib.bib437)] 将该区域的对象分割成一个掩模。接下来，用户可以发送指令来编辑图像，例如移除图像中的掩模对象。这种方式不仅能更精确、高效地编辑图像，还能提高工具使用的成功率。

此外，一些工作 [[105](https://arxiv.org/html/2405.19334v2#bib.bib105), [114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 能够生成视频，如图 [14](https://arxiv.org/html/2405.19334v2#S8.F14 "图 14 ‣ 8.2.1 无需训练的方法 ‣ 8.2 方法 ‣ 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成和编辑：一项调查") 所示，并且还能为视频配音。然而，目前没有支持直接编辑视频帧的多模态代理。这部分是因为视频编辑极具挑战性，仍需要进一步研究。一些代理还支持生成音频，例如语音 [[105](https://arxiv.org/html/2405.19334v2#bib.bib105), [114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 和音乐 [[114](https://arxiv.org/html/2405.19334v2#bib.bib114)]。将工具结合起来（*例如*，image_captioning 和 text_to_music）为图像生成音乐，如图 [15](https://arxiv.org/html/2405.19334v2#S8.F15 "图 15 ‣ 8.2.1 无需训练的方法 ‣ 8.2 方法 ‣ 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成和编辑：一项调查") 所示，是非常有趣的。此外，多模态代理不仅限于这些视听任务。例如，ControlLLM [[114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 支持查询天气，甚至可以通过图像可视化天气条件，如图 [16](https://arxiv.org/html/2405.19334v2#S8.F16 "图 16 ‣ 8.2.1 无需训练的方法 ‣ 8.2 方法 ‣ 8 工具增强多模态代理 ‣ LLMs 遇见多模态生成和编辑：一项调查") 所示。

表 XI: 多模态代理。我们仅展示那些基于 LMMs 的方法，这些方法通过调用专家模型来解决用户的问题。

|   方法 | 场所 | 图像编辑 | 图像生成 | 视频编辑 | 视频生成 | 音频编辑 | 音频生成 | 3D 生成 | 指点设备 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|   Idea-2-3D [[441](https://arxiv.org/html/2405.19334v2#bib.bib441)] | arXiv 2024 | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ |
| MLLM-Tool [[432](https://arxiv.org/html/2405.19334v2#bib.bib432)] | arXiv 2024 | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✗ | ✗ |
| ControlLLM [[114](https://arxiv.org/html/2405.19334v2#bib.bib114)] | arXiv 2023 | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✗ | ✓ |
| ModelScope-Agent [[118](https://arxiv.org/html/2405.19334v2#bib.bib118)] | EMNLP 2023 | ✗ | ✓ | ✗ | ✓ | ✗ | ✓ | ✗ | ✗ |
| GPT4Tools [[115](https://arxiv.org/html/2405.19334v2#bib.bib115)] | NeurIPS 2023 | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| InternGPT [[117](https://arxiv.org/html/2405.19334v2#bib.bib117)] | arXiv 2023 | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ | ✓ |
| HuggingGPT [[105](https://arxiv.org/html/2405.19334v2#bib.bib105)] | NeurIPS 2023 | ✓ | ✓ | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ |
| Visual ChatGPT [[116](https://arxiv.org/html/2405.19334v2#bib.bib116)] | arXiv 2023 | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| VISPROG [[431](https://arxiv.org/html/2405.19334v2#bib.bib431)] | CVPR 2022 | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
|   |  |  |  |  |  |  |  |  |  |

### 8.4 摘要

本节探讨了使用外部工具来增强大型语言模型（LLMs）能力的方法，特别是在多模态交互中。这种整合的动机是解决 LLMs 在处理训练数据中不存在的信息（例如实时数据或私人数据）时的局限性。通过为 LLMs 增添可以提供额外信息或功能的工具，并通过自然语言指令调用这些工具，实现了这一目标。

这些方法分为两类：无训练方法，依赖于提示工程和上下文学习，以及指令调优方法，涉及训练 LLMs 更准确地遵循指令。这些方法通常包括三个阶段的框架：任务规划、任务执行和响应生成。任务规划将指令解释为工具调用方案，任务执行涉及使用多模态工具进行图像生成或音频合成等任务，响应生成则从执行输出中创建用户友好的回应。

总之，工具增强的多模态代理代表了人机交互的重大进展，使交互更加自然和多样化，并促进了跨各种模态的创造性应用。然而，它们也带来了需要解决的挑战，以实现其终极潜力。

## 9 生成性 AI 安全

多模态生成内容的安全问题正受到越来越多的关注。研究主要集中在减少偏见和有害内容生成、保护版权以及缓解生成模型带来的虚假内容的影响。

生成模型对攻击或恶意使用的脆弱性带来了独特的挑战，并吸引了大量的研究关注。最近的研究包括基于优化的攻击、提示级别的操控和数据中毒方法：(i) 基于优化的攻击展示了对抗性技术在降低模型性能方面的有效性[[442](https://arxiv.org/html/2405.19334v2#bib.bib442)]，或诱导偏见和有害输出[[443](https://arxiv.org/html/2405.19334v2#bib.bib443), [444](https://arxiv.org/html/2405.19334v2#bib.bib444), [445](https://arxiv.org/html/2405.19334v2#bib.bib445), [446](https://arxiv.org/html/2405.19334v2#bib.bib446)]。对抗性攻击和基于检测的防御研究也在音频和视频领域进行[[447](https://arxiv.org/html/2405.19334v2#bib.bib447), [447](https://arxiv.org/html/2405.19334v2#bib.bib447), [448](https://arxiv.org/html/2405.19334v2#bib.bib448), [449](https://arxiv.org/html/2405.19334v2#bib.bib449), [450](https://arxiv.org/html/2405.19334v2#bib.bib450), [451](https://arxiv.org/html/2405.19334v2#bib.bib451)]。 (ii) 提示级别的攻击[[452](https://arxiv.org/html/2405.19334v2#bib.bib452), [453](https://arxiv.org/html/2405.19334v2#bib.bib453), [454](https://arxiv.org/html/2405.19334v2#bib.bib454), [455](https://arxiv.org/html/2405.19334v2#bib.bib455)] 揭示了在推理级别的风险，其中人造的输入可以绕过保护措施并引发不安全的输出，从而带来安全挑战。 (iii) 数据中毒方法[[456](https://arxiv.org/html/2405.19334v2#bib.bib456), [457](https://arxiv.org/html/2405.19334v2#bib.bib457)] 显示了当训练数据的完整性被破坏时，模型可以通过注入恶意数据输入进行操控。这些研究工作强调了需要综合的方法来提高模型的鲁棒性、确保数据的完整性，并识别用户的不安全交互，从而应对生成 AI 的脆弱性。

在讨论攻击大型生成模型的技术之后，通常有两种主要方法来防御不良生成内容。第一种方法是不修改模型的现有参数，而是采用检测机制或操控输入提示上下文。[[458](https://arxiv.org/html/2405.19334v2#bib.bib458)] 利用 VLMs 来检测和纠正多模态表情包中的仇恨言论。[[459](https://arxiv.org/html/2405.19334v2#bib.bib459), [460](https://arxiv.org/html/2405.19334v2#bib.bib460)] 通过上下文学习操作 LLMs 并防御越狱攻击。对于文本到图像生成，提出了一个有效且高效的框架，名为 Latent Guard [[461](https://arxiv.org/html/2405.19334v2#bib.bib461)]，用于检测不安全的输入提示。与传统的基于黑名单的方法相比，它更加稳健，因为输入提示是在潜在空间中进行检查的。它的速度也比基于 LLM 的不安全检测方法要快得多。第二种策略通过使用对齐算法将模型与人类的偏好或价值观对齐，从而增强安全性。Proximal Policy Optimization (PPO) 算法，在 [[462](https://arxiv.org/html/2405.19334v2#bib.bib462)] 中引入，已经广泛用于对齐 LLMs。最近，Direct Preference Optimization (DPO) 和相关方法 [[463](https://arxiv.org/html/2405.19334v2#bib.bib463), [464](https://arxiv.org/html/2405.19334v2#bib.bib464)] 通过提供更高效的对齐算法，能够直接从偏好数据中学习对齐，从而改进了 [[462](https://arxiv.org/html/2405.19334v2#bib.bib462)]。对于图像生成模型，也提出了一些偏好数据集 [[465](https://arxiv.org/html/2405.19334v2#bib.bib465)] 和对齐方法 [[466](https://arxiv.org/html/2405.19334v2#bib.bib466)]。

一些研究关注于防止多模态生成模型伪造事实。能够生成高度真实视频的强大生成模型因其潜在的误用而引起了广泛关注，如 Deepfakes [[467](https://arxiv.org/html/2405.19334v2#bib.bib467), [468](https://arxiv.org/html/2405.19334v2#bib.bib468), [469](https://arxiv.org/html/2405.19334v2#bib.bib469)]。Deepfake 是一种技术，可以生成特定身份的真实内容，形式为图像或视频。方法 [[470](https://arxiv.org/html/2405.19334v2#bib.bib470), [471](https://arxiv.org/html/2405.19334v2#bib.bib471), [472](https://arxiv.org/html/2405.19334v2#bib.bib472)] 关注通过检测视觉伪影来区分 deepfake 视频。尽管这些检测方法仍然有限 [[473](https://arxiv.org/html/2405.19334v2#bib.bib473)]，它们并未坚持对抗攻击，因此在依赖训练中观察到的模式的新 AIGC 模型上效果不好。

生成内容也可能引发版权问题。为解决这些问题，我们可能需要使用数据归属和在生成输出中嵌入水印。数据来源归属，即追踪模型预测到其原始训练数据，可以帮助找到引发版权问题的数据 [[474](https://arxiv.org/html/2405.19334v2#bib.bib474), [475](https://arxiv.org/html/2405.19334v2#bib.bib475), [476](https://arxiv.org/html/2405.19334v2#bib.bib476)]。水印技术 [[477](https://arxiv.org/html/2405.19334v2#bib.bib477), [478](https://arxiv.org/html/2405.19334v2#bib.bib478), [479](https://arxiv.org/html/2405.19334v2#bib.bib479)]可以通过在生成内容中嵌入所有权信息，使生成内容与真实内容区分开来。

此外，还提出了多种数据集来评估生成性 AI 安全性的不同方面。SafetyBench [[480](https://arxiv.org/html/2405.19334v2#bib.bib480)]数据集是一个用于评估不安全内容的多项选择题数据集，包含 11,435 个条目，涵盖 7 个安全类别。该努力得到了 GOAT-Bench 数据集 [[481](https://arxiv.org/html/2405.19334v2#bib.bib481)]的补充，GOAT-Bench 评估了超过 6K 个不同主题的危险模因，包括隐性仇恨言论、性别歧视和网络欺凌。此外，像 ToViLaG 等数据集 [[482](https://arxiv.org/html/2405.19334v2#bib.bib482), [483](https://arxiv.org/html/2405.19334v2#bib.bib483), [484](https://arxiv.org/html/2405.19334v2#bib.bib484)] 专门为视觉 LLM 开发，揭示了应对有毒内容生成（如冒犯性文本和不当图像）的挑战。这些数据集提供了全面的评估，进一步提升了生成模型的安全性，涵盖了文本和图像内容。

总之，生成性 AI 模型的安全技术可以减轻伦理风险并保护版权。商业模型正在利用检测和数据算法技术。一些开源项目也默认提供安全检查。水印和数据追踪技术在缓解版权保护问题方面取得了重大进展。采用安全技术用于有影响力的公共项目可以增强多模态生成应用的安全性和可信度。表 [XII](https://arxiv.org/html/2405.19334v2#S9.T12 "TABLE XII ‣ 9 Generative AI Safety ‣ LLMs Meet Multimodal Generation and Editing: A Survey")总结了与生成性 AI 安全性问题相关的选定研究。

表 XII：概述了各种模态和方法下的生成性 AI 安全性。"Adv." 表示"对抗攻击"。

| 名称 | 媒体 | 类型 | 方法 | 会议 |
| --- | --- | --- | --- | --- |
| Wallace et al.[[442](https://arxiv.org/html/2405.19334v2#bib.bib442)] | T | 攻击 | Adv. | EMNLP 2019 |
| Fu 等人[[443](https://arxiv.org/html/2405.19334v2#bib.bib443)] | T | 攻击 | Adv. | arXiv 2023 |
| Image hijacks[[444](https://arxiv.org/html/2405.19334v2#bib.bib444)] | I | 攻击 | Adv. | arXiv 2023 |
| Jones 等人[[446](https://arxiv.org/html/2405.19334v2#bib.bib446)] | T | 攻击 | Adv. | ICML 2023 |
| Wu 等人[[452](https://arxiv.org/html/2405.19334v2#bib.bib452)] | T + I | 攻击 | Prompt | arXiv 2024 |
| Xie 等人[[453](https://arxiv.org/html/2405.19334v2#bib.bib453)] | T | 攻击 | Prompt | NMI 2023 |
| Liu 等人[[454](https://arxiv.org/html/2405.19334v2#bib.bib454)] | T | 攻击 | Prompt | arXiv 2023 |
| Carlini 等人[[456](https://arxiv.org/html/2405.19334v2#bib.bib456)] | T | 攻击 | 数据 | arXiv 2023 |
| Jia 等人[[457](https://arxiv.org/html/2405.19334v2#bib.bib457)] | T | 攻击 | 数据 | EMNLP 2017 |
| Latent Guard[[461](https://arxiv.org/html/2405.19334v2#bib.bib461)] | T+I | 防御 | 检测 | arXiv 2023 |
| Van 等人[[458](https://arxiv.org/html/2405.19334v2#bib.bib458)] | T+I | 防御 | 检测 | arXiv 2023 |
| Wei 等人[[459](https://arxiv.org/html/2405.19334v2#bib.bib459)] | T | 防御 | Prompt | arXiv 2023 |
| Smoothllm[[460](https://arxiv.org/html/2405.19334v2#bib.bib460)] | T | 防御 | Prompt | arXiv 2023 |
| Rafailov 等人[[463](https://arxiv.org/html/2405.19334v2#bib.bib463)] | T | 防御 | 对齐 | arXiv 2023 |
| Raft[[466](https://arxiv.org/html/2405.19334v2#bib.bib466)] | T+I | 防御 | 对齐 | TMLR 2023 |
| Wodajo 等人[[471](https://arxiv.org/html/2405.19334v2#bib.bib471)] | V | 防御 | 检测 | arXiv 2023 |
| Safetybench[[480](https://arxiv.org/html/2405.19334v2#bib.bib480)] | T | 数据集 | - | arXiv 2023 |
| GOAT-Bench[[481](https://arxiv.org/html/2405.19334v2#bib.bib481)] | T | 数据集 | - | arXiv 2024 |
| ToViLaG[[482](https://arxiv.org/html/2405.19334v2#bib.bib482)] | T+I | 数据集 | - | EMNLP 2023 |
| Figstep[[483](https://arxiv.org/html/2405.19334v2#bib.bib483)] | T+I | 数据集 | - | arXiv 2023 |
| Liu 等人[[484](https://arxiv.org/html/2405.19334v2#bib.bib484)] | T+I | 数据集 | - | arXiv 2023 |

## 10 应用

来自 OpenAI、Google、Meta、百度和微软等公司的 LLMs 的快速进步，推动了多种令人印象深刻的 AI 驱动应用的开发。这些模型，如 GPT-4、Gemini 和 Claude，展示了在多模态任务，特别是多模态理解方面的卓越能力。

这些模型在理解、解释和生成多模态内容方面的能力是人工智能领域的重要里程碑。这种多模态能力对各个行业具有巨大潜力，并展示了 LLMs 在多模态生成中的有效性。

在本节中，我们将回顾一些已经发布的杰出应用。从图像生成开始，逐步介绍到视频、音频和 3D 生成，这些展示了 LLMs 在生成多模态内容方面的显著影响。

### 10.1 图像

扩散模型的快速进步使合成图像的质量和逼真度显著提高。这促使了许多公司开发高质量的文本到图像生成工具以及多模态条件图像编辑或生成解决方案的出现。

Midjourney[[485](https://arxiv.org/html/2405.19334v2#bib.bib485)] 在行业中取得了显著进展。它通过提供生成高质量、逼真图像的能力，使用户能够从文本提示中进行内容创作和设计。其用户友好的界面和强大的性能使其成为图像生成领域的专业人士和爱好者的首选。

此外，Stability AI[[486](https://arxiv.org/html/2405.19334v2#bib.bib486)] 提供了一个强大的开源生成模型。用户社区提供了各种使用方法，确实将创意和工具交给了用户。开放微调功能创建了一个庞大的开源图像使用社区。即使是不具备计算机科学背景的艺术家也可以轻松基于他们的基础模型制作自己的小模型。用户将各种模态工具整合到部署中，使他们的图像生成模型发挥更好的作用。

DALLE3[[160](https://arxiv.org/html/2405.19334v2#bib.bib160)] 是一个出色的例子，展示了如何将图像生成能力无缝集成到强大的 ChatGPT4 聊天机器人[[487](https://arxiv.org/html/2405.19334v2#bib.bib487)] 中。使用 DALLE3，用户可以通过基于文本的提示生成和修改图像。OpenAI[[489](https://arxiv.org/html/2405.19334v2#bib.bib489)] 的 DALL-E[[158](https://arxiv.org/html/2405.19334v2#bib.bib158)] 和 DALL-E 2[[488](https://arxiv.org/html/2405.19334v2#bib.bib488)] 的成功为 LLMs 中高度复杂的图像生成能力铺平了道路。这些模型可以从文本描述中创建详细的、逼真的图像，允许在多个领域快速原型设计和内容创作。

除了上述提到的行业领先解决方案外，许多利用大语言模型（LLMs）来增强用户体验的文本到图像生成工具已经出现。通过利用 LLMs 来扩展和细化字幕，这些工具可以提升生成图像的质量以及平台的整体可靠性和用户友好性。

### 10.2 视频

随着大规模视频生成模型的出现，个人现在可以通过简单输入文本描述来获取高质量的视频片段。用户不需要传统视频制作的专业技能，如 CG 建模、3D 建模或其他专业知识。用户可以通过文本描述生成所需的视频片段，然后将这些片段组装起来，制作出引人注目的短片或动画视频。现有的主要工具包括商业工具如 Pika [[490](https://arxiv.org/html/2405.19334v2#bib.bib490)]和 Runway 的 Gen2 [[491](https://arxiv.org/html/2405.19334v2#bib.bib491)]，以及开源视频生成模型如 AnimateDiff [[20](https://arxiv.org/html/2405.19334v2#bib.bib20)]、VideoCrafter [[19](https://arxiv.org/html/2405.19334v2#bib.bib19)]和 SVD [[260](https://arxiv.org/html/2405.19334v2#bib.bib260)]。在人类视频生成方面，Heygen [[492](https://arxiv.org/html/2405.19334v2#bib.bib492)]是一个广泛应用于电商、社交媒体和广告视频等多个领域的热门工具。

在 Sora[[1](https://arxiv.org/html/2405.19334v2#bib.bib1)]生成的一些演示视频发布后，现实感和跟随提示的能力都有了显著提升，这增强了对大规模文本转视频模型应用的信心。很多努力已经被投入到降低影视制作成本的工作中。

### 10.3 音频

多模态人工智能在音频领域的应用已经被探索了很长时间。应用场景更加明确，定制化和多样化声音的需求也更加确定。文本转语音生成、声音转移、音乐生成及其他音频生成技术在教育、视频配音、智能终端、语音助手和医疗领域展现了良好的前景。

微软的 Azure 平台[[493](https://arxiv.org/html/2405.19334v2#bib.bib493)]在语音生成领域处于领先地位，并推动了 AI 生成声音在短视频平台上的整合。基于 AI 的音频和视频编辑器 Descript[[494](https://arxiv.org/html/2405.19334v2#bib.bib494)]能够将音频和视频中的语音转录为文本，使用户可以像编辑 Word 文档一样修改音频和视频。此外，许多视频平台、视频编辑软件和音频平台也对多模态模型和音频生成给予了大量关注。

除了语音和音频生成，音乐生成也是行业中的一个热点。对音乐的热情驱使了无数 AI 研究人员和科学家在推动这一领域的发展上付出巨大的努力。Suno AI[[495](https://arxiv.org/html/2405.19334v2#bib.bib495)] 引领了音乐生成的“空海时代”，用户现在只需提供一个描述所需歌词风格的文本提示，即可创建生动的高质量歌曲。此外，像 Stability Audio[[496](https://arxiv.org/html/2405.19334v2#bib.bib496)]、谷歌的 MusicFX[[497](https://arxiv.org/html/2405.19334v2#bib.bib497)]、Tuneflow[[498](https://arxiv.org/html/2405.19334v2#bib.bib498)]和 Deepmusic[[499](https://arxiv.org/html/2405.19334v2#bib.bib499)]这样的公司也提供了他们的音乐生成产品，进一步扩展了这一领域的能力。

### 10.4 3D

3D 模型的生成在电影、游戏、工业设计、建筑、室内设计、产品设计和虚拟现实等各个领域都至关重要。它提供了真实的视觉体验和沉浸式互动，促进了角色、场景、产品和虚拟环境的创建，以增强创造力和参与感。Meta[[500](https://arxiv.org/html/2405.19334v2#bib.bib500)] 在 3D 建模和虚拟现实技术上进行了大量投资。Epic Games 的 MetaHuman Creator[[501](https://arxiv.org/html/2405.19334v2#bib.bib501)] 是一个云流式应用，旨在提升实时数字人类创建，另一个值得注意的发展，可以与 Unreal Engine 这个最先进的实时引擎和编辑器一起使用。

至于 3D 重建和生成，Luma AI[[502](https://arxiv.org/html/2405.19334v2#bib.bib502)] 正在取得重大进展，他们的技术能够从 2D 图像生成 3D 模型，简化了 3D 内容创作的过程。其他行业参与者，如 Adobe[[503](https://arxiv.org/html/2405.19334v2#bib.bib503)] 和 Kaedim3D[[504](https://arxiv.org/html/2405.19334v2#bib.bib504)]，也在这一领域取得了实质性进展。Adobe[[503](https://arxiv.org/html/2405.19334v2#bib.bib503)] 的 3D 和 AR 工具使沉浸式内容的创建成为可能，而 Kaedim3D[[504](https://arxiv.org/html/2405.19334v2#bib.bib504)] 的 AI 技术可以将 2D 图像转换为 3D 模型。

Wonder Studio[[505](https://arxiv.org/html/2405.19334v2#bib.bib505)] 是一个强大的 AI 工具，用于视频中的角色替换，它可以将视频中的原始角色替换为用户创建的 3D 模型，开启了个性化内容创作的激动人心的可能性。

最近语言到语言模型（LLMs）的进展揭示了文本交互和生成的显著潜力，开辟了使用自然语言命令创建和操作 3D 模型的新可能，使过程更加直观和可访问。例如，Meta 的 SceneScript [[506](https://arxiv.org/html/2405.19334v2#bib.bib506)] 能够基于其强大的语言模型 Llama [[145](https://arxiv.org/html/2405.19334v2#bib.bib145)] 重建环境并表示物理空间的布局。然而，与图像到 3D 相比，文本到 3D 仍然是像 Meta [[500](https://arxiv.org/html/2405.19334v2#bib.bib500)]、Google [[507](https://arxiv.org/html/2405.19334v2#bib.bib507)]、腾讯 [[508](https://arxiv.org/html/2405.19334v2#bib.bib508)] 等公司的研究课题。

将 LLMs 融入 3D 世界正在改变我们创建和互动数字内容的方式。随着这些技术的不断发展，我们预期将会出现更多有趣且实用的应用。

#### 10.4.1 其他

一款 AI 驱动的软件通常需要处理各种模态的输入数据。这对多模态解决方案的需求不断增长，突显了能够无缝集成和处理各种数据类型的高级 AI 模型的重要性。例如，AI 生成的电影结合了 3D 技术用于视频、音乐和语音生成，与人类艺术家合作生产高质量的电影体验。数字人也已成为各个行业的突出人物，从直播和游戏到纪念服务和大规模互动显示。此外，LLM $+$ 多模态生成工具在数学、法律、教育和机器人领域找到了多种应用。总之，我们目前正在见证 LLMs 的多模态生成模型的黎明，这无疑将改变我们的生活。

## 11 未来前景

LLMs 增强的多模态生成作为一个有前途的研究课题脱颖而出，它利用 LLMs 的语言知识来提升图像、视频、3D 和音频等多种模态的生成。这系列方法不仅可以提高生成内容的质量、多样性和可控性，还可以促进多模态生成过程中的交互。按照这一方向，我们打算展示未来工作的前景。

### 11.1 技术前景

本节重点关注多模态生成的技术前景，预计将提供更多见解并促进未来的工作。

#### 11.1.1 高分辨率生成

高分辨率多模态生成至关重要，因为它直接影响到图像[[509](https://arxiv.org/html/2405.19334v2#bib.bib509), [510](https://arxiv.org/html/2405.19334v2#bib.bib510)], 视频[[511](https://arxiv.org/html/2405.19334v2#bib.bib511), [512](https://arxiv.org/html/2405.19334v2#bib.bib512)], 音频和 3D 生成[[44](https://arxiv.org/html/2405.19334v2#bib.bib44)]等多个领域的生成内容的质量和可用性。因此，音频生成中也需要考虑高保真度[[409](https://arxiv.org/html/2405.19334v2#bib.bib409), [49](https://arxiv.org/html/2405.19334v2#bib.bib49), [513](https://arxiv.org/html/2405.19334v2#bib.bib513), [513](https://arxiv.org/html/2405.19334v2#bib.bib513), [514](https://arxiv.org/html/2405.19334v2#bib.bib514)]。生成高分辨率多模态内容的能力对需要详细和逼真表现的应用至关重要，从虚拟现实到电影制作，因为它能提升感知体验，提供更多的分析信息，并改善后续任务如物体识别和场景理解的性能。

LLMs 具有解决高分辨率多模态生成挑战的潜力。它们能够实现视觉和文本模态的更无缝整合，提供基于对话的接口和指令跟随能力[[70](https://arxiv.org/html/2405.19334v2#bib.bib70)]。这可以通过改善对复杂指令的理解和生成更准确、多样化的输出，来提升生成过程。近期在图像[[30](https://arxiv.org/html/2405.19334v2#bib.bib30), [515](https://arxiv.org/html/2405.19334v2#bib.bib515), [70](https://arxiv.org/html/2405.19334v2#bib.bib70), [11](https://arxiv.org/html/2405.19334v2#bib.bib11)], 视频[[19](https://arxiv.org/html/2405.19334v2#bib.bib19), [281](https://arxiv.org/html/2405.19334v2#bib.bib281), [516](https://arxiv.org/html/2405.19334v2#bib.bib516), [517](https://arxiv.org/html/2405.19334v2#bib.bib517)], 3D[[365](https://arxiv.org/html/2405.19334v2#bib.bib365), [518](https://arxiv.org/html/2405.19334v2#bib.bib518), [519](https://arxiv.org/html/2405.19334v2#bib.bib519)]和音频[[46](https://arxiv.org/html/2405.19334v2#bib.bib46), [48](https://arxiv.org/html/2405.19334v2#bib.bib48), [102](https://arxiv.org/html/2405.19334v2#bib.bib102)]等不同模态的进展，已经显著提高了生成内容的质量。我们非常期待未来能够看到更多整合 LLMs 的工作，从而为高分辨率生成提供更好的支持。此外，高分辨率内容生成通常涉及大量硬件费用和时间成本。因此，高效的高分辨率内容生成也是一个值得研究的课题。

#### 11.1.2 长期序列生成

长期序列生成对于在视频[[517](https://arxiv.org/html/2405.19334v2#bib.bib517), [520](https://arxiv.org/html/2405.19334v2#bib.bib520)]和音频[[521](https://arxiv.org/html/2405.19334v2#bib.bib521), [112](https://arxiv.org/html/2405.19334v2#bib.bib112), [46](https://arxiv.org/html/2405.19334v2#bib.bib46), [522](https://arxiv.org/html/2405.19334v2#bib.bib522)]中创造沉浸式体验至关重要。在视频中，它允许表现不断变化的场景和叙事，而在音频中，它支持音乐和对话的开发，这些内容可以随着时间的推移而适应和流动。生成长期序列的能力不仅是技术挑战，也是创造性挑战，模型必须理解和预测复杂的模式和进程。它应保持连续性，防止重复，并引入与总体主题和输入条件相一致的新元素。只有当我们能够为视频和音频生成长期序列时，它才能潜在地带来实际意义。

最近 LLMs 的进展，如 OpenAI 的 GPT 系列和 Meta 的 LLaMA [[145](https://arxiv.org/html/2405.19334v2#bib.bib145)]，解决了长期序列生成的挑战。LLMs 建立在预训练的语言表示和微调技术的基础上，捕捉文本数据中的复杂模式和依赖关系，使其能够生成连贯且上下文相关的长序列。通过利用 LLMs 的上下文理解和生成能力，研究人员可以深入探索长期序列生成。例如，在多模态数据集上微调预训练的 LLMs 可以使其生成在不同模态（包括视频和音频）中连贯且多样化的序列。此外，技术如提示工程和条件设置可以引导生成过程朝向预期的结果，从而创建具有特定主题或叙事的长序列。我们认为 LLMs 可以提升生成长序列的连贯性和一致性。

通常，长期序列生成代表了一个复杂而引人入胜的研究领域。通过利用 LLMs 的能力并解决相关挑战，研究人员可以解锁创建沉浸式和引人入胜的序列的新机会，这些序列能吸引观众并推动内容创作和叙事的边界。

#### 11.1.3 更准确和细致的生成控制

精确且细致的生成控制在 AIGC 中是一个重要话题，原因有几个。首先，它允许创造更真实和高质量的多模态内容。这在娱乐、广告和教育等领域尤为重要，因为高质量的内容能显著提升用户体验。其次，细致的控制可以促进人类与 AI 之间更有效的沟通。例如，具有细致控制的 AI 模型可以根据用户的详细描述生成特定的图像或声音，从而改善用户与 AI 之间的互动。最后，细致的控制也可以推动其他 AI 领域的进步。例如，在强化学习中，如果 AI 代理能够生成详细且准确的环境模拟，它的学习效果会更好。

许多方法 [[70](https://arxiv.org/html/2405.19334v2#bib.bib70), [523](https://arxiv.org/html/2405.19334v2#bib.bib523), [524](https://arxiv.org/html/2405.19334v2#bib.bib524), [19](https://arxiv.org/html/2405.19334v2#bib.bib19)] 已被提出以解决精确且细致的生成控制问题。然而，这些方法仍然存在一些局限性。例如，它们在生成细节，如手指或身体部位时仍然存在困难，这可能导致不现实的输出。此外，它们还可能无法准确捕捉控制信号中的细微差别，从而导致生成内容与控制信号之间的不匹配。

大型语言模型在理解和生成文本方面表现出了显著的能力。通过利用这些能力，我们可以潜在地提高生成控制的准确性和细致性。一个突出的例子是图像或视频上的文本渲染 [[525](https://arxiv.org/html/2405.19334v2#bib.bib525), [202](https://arxiv.org/html/2405.19334v2#bib.bib202), [64](https://arxiv.org/html/2405.19334v2#bib.bib64), [526](https://arxiv.org/html/2405.19334v2#bib.bib526), [203](https://arxiv.org/html/2405.19334v2#bib.bib203)]。观察发现，通过使用强大的语言模型，如 T5-XXL，作为编码器，图像生成模型会展现出更好的拼写能力。在这种背景下，将更强大的 LLM 集成到生成模型中是值得进一步探索的。一般来说，可以训练大型语言模型更好地理解控制信号中的细微差别，从而改善控制信号与生成内容之间的对齐。

#### 11.1.4 多视角一致性

多视图一致性（MVC）是视觉生成的一个基本方面，特别是在 3D 生成中，它确保了从不同视角观察物体时外观的一致性和连贯性。这种一致性对于增强现实（AR）、虚拟现实（VR）和计算机图形等应用至关重要，因为用户在看似真实的世界中与 3D 对象进行交互。不一致的外观会打破沉浸感，导致体验不够真实。多视图一致性的意义在于它能够提供对 3D 对象的无缝和集成的感知，从而增强用户对数字内容的体验和互动。

MVC 特别具有挑战性，因为将 2D 图像转换为一致的 3D 模型的过程复杂，其中可能会出现遮挡、光照变化和几何扭曲等问题。最近的进展非常关注多视图一致性。在 3D 生成中，Sculpt3D [[527](https://arxiv.org/html/2405.19334v2#bib.bib527)] 引入了稀疏的 3D 先验以提高一致性，而无需重新训练 2D 扩散模型。HarmonyView [[528](https://arxiv.org/html/2405.19334v2#bib.bib528)] 通过使用扩散采样技术解决了一致性与多样性之间的平衡。此外，MVDream [[345](https://arxiv.org/html/2405.19334v2#bib.bib345)] 在评分蒸馏过程中缺乏全面的多视图知识或 3D 意识，导致生成不稳定和伪影。在图像和视频生成中，相关研究 [[529](https://arxiv.org/html/2405.19334v2#bib.bib529), [530](https://arxiv.org/html/2405.19334v2#bib.bib530)] 通过关注基于大型视频数据集的新视图合成和多视图图像生成对该领域做出了贡献。

尽管已有这些进展，但仍有若干挑战需要进一步研究：1）有限的泛化能力：许多方法在跨不同数据集和物体类别时泛化能力不足。2）复杂几何体的困难：准确渲染具有复杂几何形状或无纹理表面的物体。由于语言提示可以为生成提供更多先验知识，我们相信通过在流程中引入 LLMs 可以增强多视图一致性以及生成质量。

#### 11.1.5 多模态生成的统一训练

多模态生成被定义为能够同时生成不同模态的内容，包括图像、视频、3D 对象和音频。目前，大多数方法 [[70](https://arxiv.org/html/2405.19334v2#bib.bib70), [30](https://arxiv.org/html/2405.19334v2#bib.bib30), [260](https://arxiv.org/html/2405.19334v2#bib.bib260), [71](https://arxiv.org/html/2405.19334v2#bib.bib71), [353](https://arxiv.org/html/2405.19334v2#bib.bib353), [83](https://arxiv.org/html/2405.19334v2#bib.bib83), [46](https://arxiv.org/html/2405.19334v2#bib.bib46), [112](https://arxiv.org/html/2405.19334v2#bib.bib112)] 只关注于文本到图像或文本到视频合成等某一方面。这不可避免地引发了一个问题：一个模型是否能够同时具备生成多种模态的能力？

一些近期的工作 [[141](https://arxiv.org/html/2405.19334v2#bib.bib141), [531](https://arxiv.org/html/2405.19334v2#bib.bib531), [279](https://arxiv.org/html/2405.19334v2#bib.bib279), [532](https://arxiv.org/html/2405.19334v2#bib.bib532), [393](https://arxiv.org/html/2405.19334v2#bib.bib393), [533](https://arxiv.org/html/2405.19334v2#bib.bib533)] 在文本、图像、视频、音频和其他模态的特征对齐方面取得了显著进展。一些多模态代理 [[105](https://arxiv.org/html/2405.19334v2#bib.bib105), [116](https://arxiv.org/html/2405.19334v2#bib.bib116), [115](https://arxiv.org/html/2405.19334v2#bib.bib115), [117](https://arxiv.org/html/2405.19334v2#bib.bib117), [114](https://arxiv.org/html/2405.19334v2#bib.bib114)] 提供了卓越的各种模态生成能力，但它们使用的原子工具并未进行联合训练。此外，先驱性工作 [[141](https://arxiv.org/html/2405.19334v2#bib.bib141), [95](https://arxiv.org/html/2405.19334v2#bib.bib95), [142](https://arxiv.org/html/2405.19334v2#bib.bib142)] 已经初步探讨了如何在一个模型中生成多模态内容。

尽管取得了这些进展，实现多模态生成的有效统一训练仍然面临挑战。一个突出的障碍在于不同模态之间的特征对齐，因为每种模态具有不同的统计属性和潜在结构，这需要强大的对齐机制来确保生成输出的一致性和连贯性。此外，训练过程中的相互干扰也是一个重大障碍，因为同时优化多个模态可能会导致模态特定目标之间的冲突或竞争，从而影响整体训练的稳定性和收敛性。此外，多模态数据固有的复杂性增加了计算开销，需要高效的算法和可扩展的架构来有效处理各种模态。

追求多模态生成的统一训练代表了 AI 研究中的一个关键进展，为提升生成模型在各个领域的能力提供了巨大的潜力。未来，我们甚至期待能够以交错方式生成不同模态的模型。

#### 11.1.6 高效训练和部署策略

多模态生成中的高效训练和部署策略仍然需要研究。随着数据集和模型的指数级扩展，实现高效训练和部署的挑战变得越来越重要，这与扩展规律一致，该规律认为，训练和部署模型所需的计算资源随着模型规模和数据集规模的增长而迅速增加 [[534](https://arxiv.org/html/2405.19334v2#bib.bib534)]。高效的策略不仅对降低计算成本至关重要，还对实现实时或资源受限的多模态生成技术应用至关重要。通过最小化计算开销和资源利用，高效的训练和部署策略不仅减少了时间和能源成本，还提高了可扩展性和可及性，将先进的生成能力普及到各个领域。

已经提出了几种方法来应对多模态生成中高效训练的挑战。一些研究探讨了低秩逼近技术，如 LoRA [[232](https://arxiv.org/html/2405.19334v2#bib.bib232)] 和 Q-LoRA [[439](https://arxiv.org/html/2405.19334v2#bib.bib439)]，旨在通过用低秩结构逼近权重矩阵来减少模型训练的计算复杂性。此外，混合精度训练 [[535](https://arxiv.org/html/2405.19334v2#bib.bib535)]，涉及使用降低精度（如 16 位浮点）进行某些计算，已成为加速训练而不牺牲模型准确性的强大工具。尽管这些高效训练技术有效，但仍然存在局限性。低秩逼近方法可能引入逼近误差，从而降低生成输出的质量，特别是在高保真合成至关重要的场景中。类似地，混合精度训练可能遇到数值不稳定问题，尤其是在处理极大模型或数据集时，导致次优收敛或甚至训练失败。

高效的部署策略，如量化[[536](https://arxiv.org/html/2405.19334v2#bib.bib536)、[537](https://arxiv.org/html/2405.19334v2#bib.bib537)、[538](https://arxiv.org/html/2405.19334v2#bib.bib538)、[539](https://arxiv.org/html/2405.19334v2#bib.bib539)]到 int8 甚至 int4 精度，提供了另一种减少多模态生成模型在推理过程中计算和内存需求的途径。通过将模型权重和激活量化为更低精度的格式，可以显著节省内存带宽和计算资源，从而实现更快的推理和在资源受限设备上的部署。然而，量化也存在问题，特别是在保持模型准确性和生成质量方面。降低模型参数和激活的精度可能导致信息丢失和输出保真度的下降，尤其在细节至关重要的复杂多模态合成任务中。

总之，高效的训练和部署策略对于实现多模态生成技术在各种应用中的全部潜力是不可或缺的。通过克服与可扩展性和资源限制相关的挑战，研究人员可以加速多模态生成系统在现实世界场景中的应用，开启内容创作、人机交互等方面的新可能。

#### 11.1.7 伦理安全内容生成

尽管已有许多研究探索如何增强文本和图像生成模型的安全性[[458](https://arxiv.org/html/2405.19334v2#bib.bib458)][[459](https://arxiv.org/html/2405.19334v2#bib.bib459)][[460](https://arxiv.org/html/2405.19334v2#bib.bib460)]，但视频生成模型能力的提升应引起安全关注。由于即使使用之前较弱的视频模型也会出现像 Deepfakes[[469](https://arxiv.org/html/2405.19334v2#bib.bib469)]这样的安全问题，视频模型的日益强大加剧了潜在风险的社会影响。

对抗攻击已证明可以有效地从开源模型转移到商业闭源模型[[445](https://arxiv.org/html/2405.19334v2#bib.bib445)]。未来的商业闭源模型应考虑防御来自开源模型的攻击，例如通过实施相应的对抗性令牌检测机制。同时，也可以考虑采取措施减轻可转移攻击的影响，如最小化商业模型与开源模型的相似性，例如在网络架构、数据使用和权重方面。

目前，大多数研究文章集中于从个体视角确保安全，如检测[[458](https://arxiv.org/html/2405.19334v2#bib.bib458)]、对齐[[462](https://arxiv.org/html/2405.19334v2#bib.bib462)]、事后检查[[540](https://arxiv.org/html/2405.19334v2#bib.bib540)]等。这些方法各有优缺点。例如，检测技术提供了快速检查，但可能会忽视某些漏洞。对齐方法也无法保证用于对齐的训练数据涵盖所有安全案例。此外，事后检查可能计算开销大，尤其是生成图像和视频时。目前还没有将这些技术整合成一个整体系统来确保大型生成模型的安全。例如，系统可以首先检测用户输入，然后同时应用安全对齐的模型，最后对输出进行安全检查以决定是否继续。整合这些技术可以提高效率和安全性。

### 11.2 应用前景

在本节中，我们努力构建多模态生成模型应用的蓝图。

#### 11.2.1 语义音频合成

语义音频合成涉及基于语义描述或上下文线索生成音频信号，使得创建具有特定特征或属性的沉浸式听觉体验成为可能。多模态生成模型通过利用来自其他模态的信息（如文本或图像）提供了一个有前途的方法。例如，基于文本的声音景观或音乐作品描述可以通过训练在多模态数据上的生成模型转化为音频波形。类似地，描述场景或环境的图像或视频可以为生成相应的音频伴奏提供信息，增强多媒体内容的现实感和丰富性。通过跨模态整合语义信息，多模态生成模型能够创建高度个性化和具有上下文相关的音频体验，涵盖娱乐、虚拟现实和辅助技术等应用。

#### 11.2.2 多模态叙事

多模态叙事涉及融合不同的模态来创作引人入胜的叙事，能够同时调动多种感官。这种方法不仅丰富了叙事体验，还为创造性表达和观众参与开辟了新的途径。在多模态叙事中，内容的合成可以在多个方向上进行。

从文本提示到图像序列，多模态叙事可以从一个主题、剧本或甚至故事大纲开始，这些内容作为生成补充模态（如文本和图像序列）的基础。例如，给定一个关于奇幻冒险的提示，多模态生成模型可以生成生动的图像来描绘角色和场景，制作展示关键事件的动画视频序列，或创作配合叙事的主题音乐。

从文本提示或图像到视频和音频，在这种情况下，图像作为生成附加文本描述、视频序列或音频叙述的起点。例如，给定一张描绘风景的图像，多模态生成模型可以生成详细描述环境的文本，制作展示场景动态的视频动画，或创建捕捉环境声音和氛围的沉浸式音频体验。

多模态叙事具有极大的潜力，可以提升传统叙事格式，创造沉浸式的多感官体验，与不同媒介和平台上的观众产生共鸣。通过利用多模态生成模型的能力，讲故事者、内容创作者和媒体制作人可以在数字时代解锁新的创造力和互动维度。

#### 11.2.3 互动内容设计

互动内容设计旨在实时创建和操控媒体元素，使用户能够积极参与创作过程。传统上，内容创作过程包括构思、设计和完善等多个迭代步骤，通常需要大量时间和资源。然而，凭借基础生成模型所提供的互动能力，创作者可以迅速探索多种设计可能性，快速迭代概念，并实时完善作品，从而简化整体创作工作流程。

通过实现媒体元素的实时交互和操作，它可以提高多模态生成模型的效率。创作者可以高效地实验不同的视觉和听觉元素，探索多样的艺术风格，并生成高质量的内容，而无需大量的手工劳动或专业知识。因此，这不仅加快了生产过程，还减少了雇佣额外资源或外包任务的费用。此外，多模态生成模型在互动内容设计中的整合有助于创意民主化，通过降低对有志艺术家和设计师的入门门槛。与通常需要掌握复杂软件界面或艺术技能的传统设计工具不同，这些模型提供了直观和易于访问的界面，使来自不同背景的个人能够进行创意表达。通过民主化高级内容创作能力，这些工具促进了创意社区的包容性和多样性，使更多声音能够被听到。

展望未来，多模态生成模型的发展为互动内容设计的未来带来了令人兴奋的前景。随着技术进步不断扩展生成内容在不同模态中的范围和真实性，我们可以预期在虚拟现实、增强现实和沉浸式叙事等领域将有更大的创新机会。此外，旨在提升这些模型的可解释性、可控性和可扩展性的持续研究将进一步推动它们在各种创意领域的应用，为我们构思、设计和互动数字内容的方式带来变革性的改变。

#### 11.2.4 3D 场景生成

3D 场景生成指的是在虚拟世界、游戏、模拟和建筑可视化中创建沉浸式和逼真的环境。这个应用领域利用多模态生成模型来合成复杂的 3D 场景，包括对象、纹理、光照和空间布置。生成 3D 场景的能力对娱乐、教育、设计和虚拟现实等多个行业具有深远的影响。

在游戏和虚拟环境的背景下，多模态生成模型可以自动化场景创建过程，减少对手动建模和资产创建的依赖。通过输入文本描述或概念草图，开发者可以生成整个 3D 环境，其中充满了互动对象、角色和气氛效果。这不仅加快了游戏开发流程，还使得创建动态且沉浸式的游戏体验成为可能。此外，在建筑可视化和设计中，多模态生成模型可以帮助建筑师、城市规划师和设计师可视化和探索不同的设计选项。通过输入建筑蓝图或设计参数，设计师可以生成逼真的建筑、景观和室内空间的 3D 效果图，允许快速迭代和探索设计概念。这促进了设计过程中的利益相关者之间的协作、决策和沟通。

通过利用多模态生成模型的能力，3D 场景生成可能会彻底改变虚拟环境的创建、体验和互动方式。无论是在游戏、模拟还是建筑可视化中，程序生成沉浸式和逼真的 3D 场景的能力为虚拟世界中的创造力、探索和叙事开辟了新的可能性。

#### 11.2.5 可定制头像

可定制头像代表了用户的数字化表现，可以进行个性化和调整以反映个人偏好、身份和特征。

多模态生成模型提供了一种引人注目的定制化头像创建方法，通过合成图像、文本和音频等多种媒体类型，创造出逼真且富有表现力的头像。例如，基于多模态数据训练的生成模型可以根据文本描述或用户偏好生成逼真的头像图像，包含面部特征、服装风格和表情等细节。同样，基于音频的头像可以使用语音合成技术生成，使头像能够使用自然的声音与用户沟通，反映其个性或偏好。通过在多个模态中实现定制化头像的创建，多模态生成模型使用户能够在虚拟环境中表达自我，促进社交互动、游戏和虚拟通信平台中的更深层次参与和个性化。

目前，有几个方面可以进一步研究：1) 个性化和定制化：多模态生成模型可以根据面部特征、身体类型和服装偏好等输入参数生成与用户相似的虚拟形象。用户可以通过直观的界面互动地定制他们的虚拟形象，实时调整发型、面部表情和配件等属性。2) 情感表达和肢体动作：多模态模型生成的虚拟形象可以表现出广泛的情感表达、手势和身体动作，提高其在虚拟环境中传达非语言交流信号的能力。用户可以动态控制虚拟形象的行为，从而在虚拟世界中实现更具沉浸感的社交互动和协作体验。3) 与虚拟环境的集成：可定制的虚拟形象可以无缝集成到各种虚拟环境中，包括社交平台、在线游戏和虚拟现实应用。用户可以使用他们的虚拟形象在这些环境中导航，与其他用户和对象实时互动，增强数字空间中的存在感和归属感。

### 11.3 迈向世界模型

世界模型[[541](https://arxiv.org/html/2405.19334v2#bib.bib541), [542](https://arxiv.org/html/2405.19334v2#bib.bib542), [543](https://arxiv.org/html/2405.19334v2#bib.bib543), [544](https://arxiv.org/html/2405.19334v2#bib.bib544), [545](https://arxiv.org/html/2405.19334v2#bib.bib545)] 最近成为一个热点话题。许多著名研究人员表示，世界模型将在可预见的未来成为现实，全球研究人员对这一发展寄予厚望。我们发现，调查中提到的所有主题与世界建模的主要组件完全对应，包括视觉、听觉和语言等感知模态，以及空间理解和生成。一旦世界模型发展到可用阶段，它们将为众多行业带来新的可能性。我们在此强调几个核心应用以供参考。

多模态教育和沟通。世界模型在通过促进多模态学习体验和沉浸式互动方面对教育和沟通的革命性变革具有巨大潜力。通过整合文本、图像、音频和视频等多种感官模态，这些模型能够创建丰富的教育内容，满足不同的学习风格和偏好。此外，它们使学习者能够更直观和互动地接触复杂的概念和环境，从而增强理解和记忆。此外，世界模型通过合成自然且富有表现力的多模态对话，促进无缝沟通，在虚拟学习环境和在线协作平台中培养更具吸引力和个性化的互动。

电影生成。世界模型在电影生成中的应用代表了电影制作中的一种范式转变，为电影制作者提供了前所未有的创作自由和灵活性。通过利用多模态生成技术，电影制作者可以无缝地整合对话、视觉、音效和音乐等各种元素，打造能够与观众深层次产生共鸣的沉浸式电影体验。此外，世界模型使得生成动态和个性化的叙事成为可能，以适应个人观众的偏好，从而增强观众的参与感和沉浸感。此外，这些模型还促进了探索替代叙事格式和实验电影制作技术，推动了电影创作和表达的边界。

元宇宙。元宇宙的出现为利用世界模型创建沉浸式和互动式虚拟世界带来了令人兴奋的机会。通过合成多模态感官体验，包括视觉、听觉和触觉反馈，这些模型能够创建高度逼真且沉浸的虚拟环境，模糊了物理和数字现实之间的界限。此外，世界模型促进了智能虚拟代理和 NPC 的开发，这些代理和 NPC 展现了逼真的行为和互动，增强了在元宇宙中的存在感和社交沉浸感。此外，这些模型使用户能够定制和个性化他们的虚拟体验，激发了在数字世界中的创造力和探索。

## 12 结论

在这项调查中，我们系统回顾了由 LLMs 增强的多模态编辑和生成工作，深入探讨了包括图像、视频、3D 和音频在内的各种模态的进展。随后，详细讨论了集成了大量先进生成模型的多模态代理的多种案例研究。我们还调查了多模态生成模型的安全性问题，这些模型在实际应用中发挥着不可或缺的作用。我们的全面回顾突出了 LLMs 在提升生成系统质量和能力方面的重要贡献。展望未来，我们期待在 AI 和生成内容的交汇处进一步创新，推动更统一和强大的多模态生成框架的发展。总之，我们热切期待我们的研究能为多模态生成，特别是世界模型的发展提供见解和灵感，这些模型已经引起了大多数研究人员的关注和期待。

## 参考文献

+   [1] OpenAI, “Video generation models as world simulators,” OpenAI, Tech. Rep., 2024\. [在线]. 可用: [`openai.com/research/video-generation-models-as-world-simulators`](https://openai.com/research/video-generation-models-as-world-simulators)

+   [2] J. 德夫林，M.-W. 张，K. 李，和 K. 托托瓦纳，“Bert：深度双向变压器的预训练用于语言理解”，*arXiv 预印本 arXiv:1810.04805*，2018 年。

+   [3] A. 拉德福德，K. 纳拉西姆汗，T. 萨里曼斯，I. 苏茨克维尔 *等*，“通过生成式预训练改善语言理解”，2018 年。

+   [4] A. 拉德福德，J. 吴，R. 查尔德，D. 卢安，D. 阿莫代伊，I. 苏茨克维尔 *等*，“语言模型是无监督多任务学习者”，*OpenAI 博客*，1 卷，8 号，第 9 页，2019 年。

+   [5] T. 布朗，B. 曼，N. 赖德，M. 苏比亚，J. D. 卡普兰，P. 达里瓦尔，A. 尼拉坎坦，P. 夏亚姆，G. 萨斯特里，A. 阿斯凯尔 *等*，“语言模型是少样本学习者”，*神经信息处理系统进展*，第 33 卷，1877–1901 页，2020 年。

+   [6] J. 阿奇亚姆，S. 阿德勒，S. 阿加沃尔，L. 艾哈迈德，I. 阿卡亚，F. L. 阿莱曼，D. 阿尔迈达，J. 阿尔滕施密特，S. 奥尔特曼，S. 阿纳德卡特 *等*，“GPT-4 技术报告”，*arXiv 预印本 arXiv:2303.08774*，2023 年。

+   [7] OpenAI，“ChatGPT：用于对话式人工智能的语言模型”，OpenAI，技术报告，2023 年。[在线]。可用：[`www.openai.com/research/chatgpt`](https://www.openai.com/research/chatgpt)

+   [8] Y. 李，C. 王，和 J. 贾，“Llama-vid：大型语言模型中一张图像价值等于 2 个令牌”，*arXiv 预印本 arXiv:2311.17043*，2023 年。

+   [9] P. 高，J. 韩，R. 张，Z. 林，S. 耿，A. 周，W. 张，P. 卢，C. 何，X. 岳 *等*，“LLAMA-Adapter V2：参数高效的视觉指导模型”，*arXiv 预印本 arXiv:2304.15010*，2023 年。

+   [10] D. 波代尔，Z. 英格利希，K. 莱西，A. 布拉特曼，T. 多克霍恩，J. 穆勒，J. 彭纳，和 R. 龙巴赫，“SDXL：改善高分辨率图像合成的潜在扩散模型”，*arXiv 预印本 arXiv:2307.01952*，2023 年。

+   [11] J. 陈，J. 于，C. 盖，L. 姚，E. 谢，Y. 吴，Z. 王，J. 郭，P. 罗，H. 卢 *等*，“Pixart-$\alpha$：逼真文本到图像合成的快速扩散变压器训练”，*arXiv 预印本 arXiv:2310.00426*，2023 年。

+   [12] J. 何，T. 萨里曼斯，A. 格里特森科，W. 陈，M. 诺鲁兹，和 D. J. 弗利特，“视频扩散模型”，*神经信息处理系统进展*，第 35 卷，8633–8646 页，2022 年。

+   [13] M. 贝恩，A. 纳格拉尼，G. 瓦罗尔，和 A. 齐瑟尔曼，“时间冻结：用于端到端检索的联合视频和图像编码器”，*2021 年 IEEE/CVF 国际计算机视觉大会(ICCV)*，第 1708–1718 页，2021 年。[在线]。可用：[`api.semanticscholar.org/CorpusID:232478955`](https://api.semanticscholar.org/CorpusID:232478955)

+   [14] Y. 何，T. 杨，Y. 张，Y. 山，和 Q. 陈，“高保真度长视频生成的潜在视频扩散模型”，*arXiv 预印本 arXiv:2211.13221*，2022 年。

+   [15] D. 周，W. 王，H. 颜，W. 吕，Y. 朱，和 J. 冯，“Magicvideo：高效的视频生成与潜在扩散模型”，*arXiv 预印本 arXiv:2211.11018*，2022 年。

+   [16] U. Singer, A. Polyak, T. Hayes, X. Yin, J. An, S. Zhang, Q. Hu, H. Yang, O. Ashual, O. Gafni *等*，“Make-a-video: 无需文本-视频数据的文本到视频生成”，*arXiv 预印本 arXiv:2209.14792*，2022 年。

+   [17] J. Ho, W. Chan, C. Saharia, J. Whang, R. Gao, A. Gritsenko, D. P. Kingma, B. Poole, M. Norouzi, D. J. Fleet *等*，“Imagen video: 使用扩散模型生成高分辨率视频”，*arXiv 预印本 arXiv:2210.02303*，2022 年。

+   [18] R. Villegas, M. Babaeizadeh, P.-J. Kindermans, H. Moraldo, H. Zhang, M. T. Saffar, S. Castro, J. Kunze 和 D. Erhan，“Phenaki: 从开放领域文本描述生成可变长度视频”，发表于*国际学习表征会议*，2022 年。

+   [19] H. Chen, M. Xia, Y. He, Y. Zhang, X. Cun, S. Yang, J. Xing, Y. Liu, Q. Chen, X. Wang *等*，“Videocrafter1: 用于高质量视频生成的开放扩散模型”，*arXiv 预印本 arXiv:2310.19512*，2023 年。

+   [20] Y. Guo, C. Yang, A. Rao, Y. Wang, Y. Qiao, D. Lin 和 B. Dai，“Animatediff: 让你的个性化文本到图像扩散模型无需特定调整”，*arXiv 预印本 arXiv:2307.04725*，2023 年。

+   [21] O. Bar-Tal, H. Chefer, O. Tov, C. Herrmann, R. Paiss, S. Zada, A. Ephrat, J. Hur, Y. Li, T. Michaeli *等*，“Lumiere: 一种用于视频生成的时空扩散模型”，*arXiv 预印本 arXiv:2401.12945*，2024 年。

+   [22] R. Girdhar, M. Singh, A. Brown, Q. Duval, S. Azadi, S. S. Rambhatla, A. Shah, X. Yin, D. Parikh 和 I. Misra，“Emu video: 通过显式图像条件化分解文本到视频生成”，*arXiv 预印本 arXiv:2311.10709*，2023 年。

+   [23] H. Chen, Y. Zhang, X. Cun, M. Xia, X. Wang, C. Weng 和 Y. Shan，“Videocrafter2: 克服数据限制以提高视频扩散模型的质量”，*arXiv 预印本 arXiv:2401.09047*，2024 年。

+   [24] A. Radford, J. W. Kim, C. Hallacy, A. Ramesh, G. Goh, S. Agarwal, G. Sastry, A. Askell, P. Mishkin, J. Clark *等*，“从自然语言监督中学习可迁移的视觉模型”，发表于*国际机器学习会议*。PMLR，2021 年，第 8748–8763 页。

+   [25] A. Sanghi, H. Chu, J. G. Lambourne, Y. Wang, C.-Y. Cheng, M. Fumero 和 K. R. Malekshan，“Clip-forge: 朝零样本文本到形状生成迈进”，发表于*IEEE/CVF 计算机视觉与模式识别会议论文集*，2022 年，第 18 603–18 613 页。

+   [26] N. Mohammad Khalid, T. Xie, E. Belilovsky 和 T. Popa，“Clip-mesh: 使用预训练图像-文本模型生成纹理网格”，发表于*SIGGRAPH Asia 2022 会议论文集*，2022 年，第 1–8 页。

+   [27] O. Michel, R. Bar-On, R. Liu, S. Benaim 和 R. Hanocka，“Text2mesh: 文本驱动的网格神经风格化”，发表于*IEEE/CVF 计算机视觉与模式识别会议论文集*，2022 年，第 13 492–13 502 页。

+   [28] C. Wang, R. Jiang, M. Chai, M. He, D. Chen 和 J. Liao，“Nerf-art: 文本驱动的神经辐射场风格化”，*IEEE 视觉化与计算机图形学汇刊*，2023 年。

+   [29] B. Kerbl, G. Kopanas, T. Leimkühler 和 G. Drettakis, “实时辐射场渲染的 3D 高斯点云,” *ACM 图形学学报*, 第 42 卷，第 4 期，2023 年 7 月。[在线]. 可用: [`repo-sam.inria.fr/fungraph/3d-gaussian-splatting/`](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)

+   [30] R. Rombach, A. Blattmann, D. Lorenz, P. Esser 和 B. Ommer, “高分辨率图像合成与潜在扩散模型,” 载于 *IEEE/CVF 计算机视觉与模式识别会议论文集*, 2022, 页 10 684–10 695。

+   [31] T. Yi, J. Fang, J. Wang, G. Wu, L. Xie, X. Zhang, W. Liu, Q. Tian 和 X. Wang, “Gaussiandreamer: 通过连接 2D 和 3D 扩散模型实现从文本到 3D 高斯体的快速生成,” *arXiv 预印本 arXiv:2310.08529*, 2023。

+   [32] J. Tang, J. Ren, H. Zhou, Z. Liu 和 G. Zeng, “Dreamgaussian: 生成高效 3D 内容创作的高斯点云,” *arXiv 预印本 arXiv:2309.16653*, 2023。

+   [33] L. Höllein, A. Cao, A. Owens, J. Johnson 和 M. Nießner, “Text2room: 从 2D 文本到图像模型中提取纹理化 3D 网格,” 载于 *IEEE/CVF 国际计算机视觉会议（ICCV）论文集*, 2023 年 10 月, 页 7909–7920。

+   [34] Y. Liang, X. Yang, J. Lin, H. Li, X. Xu 和 Y. Chen, “LucidDreamer: 通过区间评分匹配实现高保真文本到 3D 生成,” *https://arxiv.org/abs/2311.11284*, 2023。

+   [35] X. Yu, Y.-C. Guo, Y. Li, D. Liang, S.-H. Zhang 和 X. Qi, “通过分类器评分蒸馏实现文本到 3D,” *https://arxiv.org/abs/2310.19415*, 2023。

+   [36] W. Li, R. Chen, X. Chen 和 P. Tan, “SweetDreamer: 在 2D 扩散中对齐几何先验以实现一致的文本到 3D,” *https://arxiv.org/abs/2310.02596*, 2023。

+   [37] Z. Wang, C. Lu, Y. Wang, F. Bao, C. Li, H. Su 和 J. Zhu, “Prolificdreamer: 高保真且多样的文本到 3D 生成与变分评分蒸馏,” *arXiv 预印本 arXiv:2305.16213*, 2023。

+   [38] J. Lorraine, K. Xie, X. Zeng, C.-H. Lin, T. Takikawa, N. Sharp, T.-Y. Lin, M.-Y. Liu, S. Fidler 和 J. Lucas, “Att3d: 计算文本到 3D 对象合成的摊销,” 载于 *国际计算机视觉会议（ICCV）*, 2023。

+   [39] J. Xu, X. Wang, W. Cheng, Y.-P. Cao, Y. Shan, X. Qie 和 S. Gao, “Dream3D: 使用 3D 形状先验和文本到图像扩散模型的零样本文本到 3D 合成,” *https://arxiv.org/abs/2212.14704*, 2023。

+   [40] J. Zhu 和 P. Zhuang, “HiFA: 高保真文本到 3D 的先进扩散引导,” *https://arxiv.org/abs/2305.18766*, 2023。

+   [41] R. Chen, Y. Chen, N. Jiao 和 K. Jia, “Fantasia3d: 通过解缠几何和外观实现高质量文本到 3D 内容创作,” 载于 *IEEE/CVF 国际计算机视觉会议（ICCV）论文集*, 2023 年 10 月。

+   [42] C. Tsalicoglou, F. Manhardt, A. Tonioni, M. Niemeyer 和 F. Tombari, “Textmesh: 从文本提示生成逼真的 3D 网格,” *arXiv 预印本 arXiv:2304.12439*, 2023。

+   [43] B. Poole, A. Jain, J. T. Barron, 和 B. Mildenhall，“Dreamfusion：使用 2D 扩散进行文本到 3D 转换，” *arXiv 预印本 arXiv:2209.14988*，2022 年。

+   [44] C.-H. Lin, J. Gao, L. Tang, T. Takikawa, X. Zeng, X. Huang, K. Kreis, S. Fidler, M.-Y. Liu, 和 T.-Y. Lin，“Magic3d：高分辨率文本到 3D 内容创建，” 见于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 300–309 页。

+   [45] J. Seo, W. Jang, M.-S. Kwak, J. Ko, H. Kim, J. Kim, J.-H. Kim, J. Lee, 和 S. Kim，“让 2D 扩散模型了解 3D 一致性以实现稳健的文本到 3D 生成，” *arXiv 预印本 arXiv:2303.07937*，2023 年。

+   [46] H. Liu, Z. Chen, Y. Yuan, X. Mei, X. Liu, D. Mandic, W. Wang, 和 M. D. Plumbley，“Audioldm：使用潜在扩散模型进行文本到音频生成，” *arXiv 预印本 arXiv:2301.12503*，2023 年。

+   [47] H. Liu, Q. Tian, Y. Yuan, X. Liu, X. Mei, Q. Kong, Y. Wang, W. Wang, Y. Wang, 和 M. D. Plumbley，“Audioldm 2：通过自监督预训练学习整体音频生成，” *arXiv 预印本 arXiv:2308.05734*，2023 年。

+   [48] F. Kreuk, G. Synnaeve, A. Polyak, U. Singer, A. Défossez, J. Copet, D. Parikh, Y. Taigman, 和 Y. Adi，“Audiogen：基于文本的音频生成，” *arXiv 预印本 arXiv:2209.15352*，2022 年。

+   [49] A. Agostinelli, T. I. Denk, Z. Borsos, J. Engel, M. Verzetti, A. Caillon, Q. Huang, A. Jansen, A. Roberts, M. Tagliasacchi *等*，“Musiclm：从文本生成音乐，” *arXiv 预印本 arXiv:2301.11325*，2023 年。

+   [50] J. Copet, F. Kreuk, I. Gat, T. Remez, D. Kant, G. Synnaeve, Y. Adi, 和 A. Défossez，“简单且可控的音乐生成，” *神经信息处理系统进展*，第 36 卷，2024 年。

+   [51] S. Forsgren 和 H. Martiros，“Riffusion-稳定扩散用于实时音乐生成，2022 年，” *URL https://riffusion.com/about*，第 6 卷，2022 年。

+   [52] X. Tan, J. Chen, H. Liu, J. Cong, C. Zhang, Y. Liu, X. Wang, Y. Leng, Y. Yi, L. He *等*，“Naturalspeech：具有人类水平质量的端到端文本到语音合成，” *IEEE 模式分析与机器智能汇刊*，2024 年。

+   [53] K. Shen, Z. Ju, X. Tan, Y. Liu, Y. Leng, L. He, T. Qin, S. Zhao, 和 J. Bian，“Naturalspeech 2：潜在扩散模型是自然的零样本语音和歌唱合成器，” *arXiv 预印本 arXiv:2304.09116*，2023 年。

+   [54] Z. Ju, Y. Wang, K. Shen, X. Tan, D. Xin, D. Yang, Y. Liu, Y. Leng, K. Song, S. Tang *等*，“Naturalspeech 3：具有因式分解编解码器和扩散模型的零样本语音合成，” *arXiv 预印本 arXiv:2403.03100*，2024 年。

+   [55] C. Wang, S. Chen, Y. Wu, Z. Zhang, L. Zhou, S. Liu, Z. Chen, Y. Liu, H. Wang, J. Li *等*，“神经编解码器语言模型是零样本文本到语音合成器，” *arXiv 预印本 arXiv:2301.02111*，2023 年。

+   [56] Z. Jiang, J. Liu, Y. Ren, J. He, C. Zhang, Z. Ye, P. Wei, C. Wang, X. Yin, Z. Ma *等*，“Mega-tts 2：具有任意长度语音提示的零样本文本到语音合成，” *arXiv 预印本 arXiv:2307.07218*，2023 年。

+   [57] Y. 任，C. 胡，X. 谭，T. 秦，S. 赵，Z. 赵，和 T.-Y. 刘，“Fastspeech 2: 快速高质量的端到端文本到语音转换，” *arXiv 预印本 arXiv:2006.04558*，2020。

+   [58] Y. 葛，Y. 葛，Z. 曾，X. 王，和 Y. 山，“在大型语言模型中种植视觉种子，” *arXiv 预印本 arXiv:2307.08041*，2023。

+   [59] L. 泽强，Z. Xi 州，D. 吉凤，Q. 于，W. 文海，“Mini-dalle3: 通过提示大型语言模型进行交互式文本到图像，” *arXiv 预印本 arXiv:2310.07653*，2023。

+   [60] Z. 唐，Z. 杨，M. 卡德米，Y. 刘，C. 朱，和 M. 班萨尔，“Codi-2: 上下文、交替和交互式的任何到任何生成，” *arXiv 预印本 arXiv:2311.18775*，2023。

+   [61] Y. 葛，S. 赵，Z. 曾，Y. 葛，C. 李，X. 王，和 Y. 山，“使用种子标记器使羊驼看和绘画，” *arXiv 预印本 arXiv:2310.01218*，2023。

+   [62] Q. 孙，Y. 崔，X. 张，F. 张，Q. 于，Z. 罗，Y. 王，Y. 饶，J. 刘，T. 黄 *等*，“生成式多模型是上下文学习者，” *arXiv 预印本 arXiv:2312.13286*，2023。

+   [63] X. 赵，B. 刘，Q. 刘，G. 石，和 X.-M. 吴，“使多模式生成变得更简单：当扩散模型遇见 LLM，” *arXiv 预印本 arXiv:2310.08949*，2023。

+   [64] J. 陈，Y. 黄，T. 吕，L. 崔，Q. 陈，和 F. 魏，“Textdiffuser-2: 发挥语言模型在文本渲染中的力量，” *arXiv 预印本 arXiv:2311.16465*，2023。

+   [65] L. Lian, B. Li, A. Yala, and T. Darrell，“LLM-grounded diffusion: 使用大型语言模型增强文本到图像扩散模型的快速理解，” *arXiv 预印本 arXiv:2305.13655*，2023。

+   [66] W. 冯，W. 朱，T.-j. 富，V. 贾潘尼，A. 阿库拉，X. 何，S. 巴苏，X. 王，和 W. Y. 王，“Layoutgpt: 使用大型语言模型进行组合视觉规划和生成”，*arXiv 预印本 arXiv:2305.15393*，2023。

+   [67] T. 张，Y. 张，V. Vineet，N. 乔希，和 X. 王，“使用 GPT-4 进行可控文本到图像生成，” *arXiv 预印本 arXiv:2305.18583*，2023。

+   [68] L. 屈，S. 吴，H. 费，L. 聂，和 T.-S. 蔡，“Layoutllm-t2i: 从 LLM 中引导布局指南进行文本到图像生成，”在第 31 届 ACM 国际多媒体会议论文集中，2023 年，第 643-654 页。

+   [69] Y. 李，H. 刘，Q. 吴，F. 穆，J. 杨，J. 高，C. 李，和 Y. J. 李，“Gligen: 面向开放集群的文本到图像生成，”在*IEEE/CVF 计算机视觉与模式识别会议论文集*中，2023 年，第 22 511-22 521 页。

+   [70] J. 贝克尔，G. 戈，L. 景，T. 布鲁克斯，J. 王，L. 李，L. 欧阳，J. 庄，J. 李，Y. 郭 *等*，“通过优化标题改进图像生成，” *计算机科学，https://cdn.openai.com/papers/dall-e-3\. pdf*，2023。

+   [71] D. 康德拉特尤克，L. 于，X. 顾，J. 莱扎马，J. 黄，R. 霍恩，H. 亚当，H. 阿克巴里，Y. 阿隆，V. 比罗德卡尔 *等*，“Videopoet: 无监督视频生成的大型语言模型”，*arXiv 预印本 arXiv:2312.14125*，2023。

+   [72] L. 余，J. 列萨马，N. B. 冯达拉普，L. 维萨里，K. 孙，D. 明嫩，Y. 程，A. 古普塔，X. 顾，A. G. 豪普特曼 *等*，“语言模型优于扩散——分词器是视觉生成的关键，” *arXiv 预印本 arXiv:2310.05737*，2023 年。

+   [73] H. 费，S. 吴，W. 姬，H. 张，和 T.-S. 蔡，“赋能动态感知的文本到视频扩散，利用大型语言模型，” *arXiv 预印本 arXiv:2308.13812*，2023 年。

+   [74] H. 林，A. 扎拉，J. 曹，和 M. 班萨尔，“Videodirectorgpt: 通过 LLM 引导的规划进行一致的多场景视频生成，” *arXiv 预印本 arXiv:2309.15091*，2023 年。

+   [75] J. 吕，Y. 黄，M. 严，J. 黄，J. 刘，Y. 刘，Y. 温，X. 陈，和 S. 陈，“Gpt4motion: 通过面向 Blender 的 GPT 规划在文本到视频生成中编写物理动作，” *arXiv 预印本 arXiv:2311.12631*，2023 年。

+   [76] Y. 陆，L. 朱，H. 范，和 Y. 杨，“Flowzero: 使用 LLM 驱动的动态场景语法进行零样本文本到视频合成，” *arXiv 预印本 arXiv:2311.15813*，2023 年。

+   [77] S. 洪，J. 徐，S. 洪，H. 辛，和 S. 金，“大型语言模型是零样本文本到视频生成的帧级导演，” *arXiv 预印本 arXiv:2305.14330*，2023 年。

+   [78] H. 黄，Y. 风，C. 石，L. 徐，J. 余，和 S. 杨，“Free-bloom: 使用 LLM 导演和 LDM 动画师的零样本文本到视频生成器，” *arXiv 预印本 arXiv:2309.14494*，2023 年。

+   [79] Z. 王，J. 王，D. 林，和 B. 戴，“Intercontrol: 通过控制每个关节生成人体动作交互，” *arXiv 预印本 arXiv:2311.15864*，2023 年。

+   [80] J. 刘，W. 戴，C. 王，Y. 程，Y. 唐，和 X. 童，“计划、姿势与前行：面向开放世界的文本到动作生成，” *arXiv 预印本 arXiv:2312.14828*，2023 年。

+   [81] F. 龙，Z. 邱，T. 姚，和 T. 梅，“Videodrafter: 使用 LLM 的内容一致的多场景视频生成，” *arXiv 预印本 arXiv:2401.01256*，2024 年。

+   [82] C. 孙，J. 韩，W. 邓，X. 王，Z. 秦，和 S. 古尔德，“3d-gpt: 使用大型语言模型进行程序化 3D 建模，” *arXiv 预印本 arXiv:2310.12945*，2023 年。

+   [83] Y. 风，J. 林，S. K. 德维维，Y. 孙，P. 帕特尔，和 M. J. 布莱克，“Posegpt: 关于 3D 人体姿势的对话，” *arXiv 预印本 arXiv:2311.18836*，2023 年。

+   [84] S. 陈，X. 陈，C. 张，M. 李，G. 余，H. 费，H. 朱，J. 范，和 T. 陈，“Ll3da: 用于全景 3D 理解、推理和规划的视觉互动指令调整，” *arXiv 预印本 arXiv:2311.18651*，2023 年。

+   [85] T. 吴，G. 杨，Z. 李，K. 张，Z. 刘，L. 贵巴斯，D. 林，和 G. 韦茨坦，“Gpt-4v(ision) 是用于文本到 3D 生成的人类对齐评估器，” *IEEE/CVF 计算机视觉与模式识别会议 (CVPR)*，2024 年。

+   [86] D. 张，S. 李，X. 张，J. 詹，P. 王，Y. 周，和 X. 邱，“Speechgpt: 赋能大型语言模型内在的跨模态对话能力，” *arXiv 预印本 arXiv:2305.11000*，2023 年。

+   [87] Y. 龚，H. 罗，A. H. 刘，L. 卡尔斯基，和 J. 玻璃，“倾听、思考与理解，” *arXiv 预印本 arXiv:2305.10790*，2023 年。

+   [88] S. Deshmukh, B. Elizalde, R. Singh, 和 H. Wang, “PENGI: 用于音频任务的音频语言模型，” *arXiv 预印本 arXiv:2305.11834*，2023 年。

+   [89] P. K. Rubenstein, C. Asawaroengchai, D. D. Nguyen, A. Bapna, Z. Borsos, F. d. C. Quitry, P. Chen, D. E. Badawy, W. Han, E. Kharitonov *等*, “AUDIOPALM: 一种能够说话和听的语言模型，” *arXiv 预印本 arXiv:2306.12925*，2023 年。

+   [90] S. Liu, A. S. Hussain, C. Sun, 和 Y. Shan, “音乐理解 LLaMA: 通过问答和标注推动文本到音乐生成，” *ICASSP 2024-2024 IEEE 国际声学、语音与信号处理会议（ICASSP）*。IEEE，2024，第 286–290 页。

+   [91] Q. Chen, Y. Chu, Z. Gao, Z. Li, K. Hu, X. Zhou, J. Xu, Z. Ma, W. Wang, S. Zheng *等*, “LAURAGPT: 用 GPT 听、关注、理解和再生音频，” *arXiv 预印本 arXiv:2310.04673*，2023 年。

+   [92] J. Gardner, S. Durand, D. Stoller, 和 R. M. Bittner, “LLARK: 一种多模态音乐基础模型，” *arXiv 预印本 arXiv:2310.07160*，2023 年。

+   [93] C. Tang, W. Yu, G. Sun, X. Chen, T. Tan, W. Li, L. Lu, Z. Ma, 和 C. Zhang, “SALMONN: 朝着大型语言模型的通用听觉能力迈进，” *arXiv 预印本 arXiv:2310.13289*，2023 年。

+   [94] Y. Chu, J. Xu, X. Zhou, Q. Yang, S. Zhang, Z. Yan, C. Zhou, 和 J. Zhou, “QWEN-AUDIO: 通过统一的大规模音频语言模型推进通用音频理解，” *arXiv 预印本 arXiv:2311.07919*，2023 年。

+   [95] A. S. Hussain, S. Liu, C. Sun, 和 Y. Shan, “M² UGEN: 利用大型语言模型的多模态音乐理解与生成，” *arXiv 预印本 arXiv:2311.11255*，2023 年。

+   [96] Y. Shu, S. Dong, G. Chen, W. Huang, R. Zhang, D. Shi, Q. Xiang, 和 Y. Shi, “LLASM: 大型语言和语音模型，” *arXiv 预印本 arXiv:2308.15930*，2023 年。

+   [97] R. Yuan, H. Lin, Y. Wang, Z. Tian, S. Wu, T. Shen, G. Zhang, Y. Wu, C. Liu, Z. Zhou *等*, “CHATMUSICIAN: 用 LLM 内在地理解和生成音乐，” *arXiv 预印本 arXiv:2402.16153*，2024 年。

+   [98] S. Ding, Z. Liu, X. Dong, P. Zhang, R. Qian, C. He, D. Lin, 和 J. Wang, “SONGCOMPOSER: 用于歌词和旋律创作的大型语言模型，” *arXiv 预印本 arXiv:2402.17645*，2024 年。

+   [99] S.-L. Wu, C. Donahue, S. Watanabe, 和 N. J. Bryan, “MUSIC CONTROLNET: 音乐生成的多种时间变化控制，” *arXiv 预印本 arXiv:2311.07069*，2023 年。

+   [100] D. Ghosal, N. Majumder, A. Mehrish, 和 S. Poria, “使用指令调整的 LLM 和潜在扩散模型进行文本到音频生成，” *arXiv 预印本 arXiv:2304.13731*，2023 年。

+   [101] S.-L. Wu, X. Chang, G. Wichern, J.-w. Jung, F. Germain, J. Le Roux, 和 S. Watanabe, “通过细粒度音频特征、文本嵌入监督和 LLM 混合增强来改进音频标注模型，” *ICASSP 2024-2024 IEEE 国际声学、语音与信号处理会议（ICASSP）*。IEEE，2024，第 316–320 页。

+   [102] J. Huang, Y. Ren, R. Huang, D. Yang, Z. Ye, C. Zhang, J. Liu, X. Yin, Z. Ma, 和 Z. Zhao，“Make-an-audio 2: Temporal-enhanced text-to-audio generation，” *arXiv 预印本 arXiv:2305.18474*，2023 年。

+   [103] Z. Wang, S. Mao, W. Wu, Y. Xia, Y. Deng, 和 J. Tien，“Assessing phrase break of esl speech with pre-trained language models and large language models，” *arXiv 预印本 arXiv:2306.04980*，2023 年。

+   [104] A. Vyas, B. Shi, M. Le, A. Tjandra, Y.-C. Wu, B. Guo, J. Zhang, X. Zhang, R. Adkins, W. Ngan *等*，“Audiobox: Unified audio generation with natural language prompts，” *arXiv 预印本 arXiv:2312.15821*，2023 年。

+   [105] Y. Shen, K. Song, X. Tan, D. Li, W. Lu, 和 Y. Zhuang，“Hugginggpt: Solving ai tasks with chatgpt and its friends in huggingface，” 在 *神经信息处理系统进展*，2023 年。

+   [106] R. Huang, M. Li, D. Yang, J. Shi, X. Chang, Z. Ye, Y. Wu, Z. Hong, J. Huang, J. Liu *等*，“Audiogpt: Understanding and generating speech, music, sound, and talking head，” *arXiv 预印本 arXiv:2304.12995*，2023 年。

+   [107] X. Liu, Z. Zhu, H. Liu, Y. Yuan, M. Cui, Q. Huang, J. Liang, Y. Cao, Q. Kong, M. D. Plumbley *等*，“Wavjourney: Compositional audio creation with large language models，” *arXiv 预印本 arXiv:2307.14335*，2023 年。

+   [108] D. Yu, K. Song, P. Lu, T. He, X. Tan, W. Ye, S. Zhang, 和 J. Bian，“Musicagent: An ai agent for music understanding and generation with large language models，” *arXiv 预印本 arXiv:2310.11954*，2023 年。

+   [109] Y. Zhang, A. Maezawa, G. Xia, K. Yamamoto, 和 S. Dixon，“Loop copilot: Conducting ai ensembles for music generation and iterative editing，” *arXiv 预印本 arXiv:2310.12404*，2023 年。

+   [110] L. Zhuo, R. Yuan, J. Pan, Y. Ma, Y. LI, G. Zhang, S. Liu, R. Dannenberg, J. Fu, C. Lin *等*，“Lyricwhiz: Robust multilingual zero-shot lyrics transcription by whispering to chatgpt，” *arXiv 预印本 arXiv:2306.17103*，2023 年。

+   [111] P. Dhariwal, H. Jun, C. Payne, J. W. Kim, A. Radford, 和 I. Sutskever，“Jukebox: A generative model for music，” *arXiv 预印本 arXiv:2005.00341*，2020 年。

+   [112] Z. Borsos, R. Marinier, D. Vincent, E. Kharitonov, O. Pietquin, M. Sharifi, D. Roblek, O. Teboul, D. Grangier, M. Tagliasacchi *等*，“Audiolm: a language modeling approach to audio generation，” *IEEE/ACM 音频、语音和语言处理交易*，2023 年。

+   [113] D. Yang, J. Tian, X. Tan, R. Huang, S. Liu, X. Chang, J. Shi, S. Zhao, J. Bian, X. Wu *等*，“Uniaudio: An audio foundation model toward universal audio generation，” *arXiv 预印本 arXiv:2310.00704*，2023 年。

+   [114] Z. Liu, Z. Lai, Z. Gao, E. Cui, Z. Li, X. Zhu, L. Lu, Q. Chen, Y. Qiao, J. Dai, 和 W. Wang，“Controlllm: Augment language models with tools by searching on graphs，” *arXiv 预印本 arXiv:2310.17796*，2023 年。

+   [115] R. Yang, L. Song, Y. Li, S. Zhao, Y. Ge, X. Li, 和 Y. Shan，“Gpt4tools: Teaching large language model to use tools via self-instruction，” 在 *神经信息处理系统进展*，2023 年。

+   [116] C. Wu, S. Yin, W. Qi, X. Wang, Z. Tang, 和 N. Duan，“视觉 ChatGPT：利用视觉基础模型进行对话、绘画和编辑”，*arXiv 预印本 arXiv:2303.04671*，2023。

+   [117] Z. Liu, Y. He, W. Wang, W. Wang, Y. Wang, S. Chen, Q. Zhang, Y. Yang, Q. Li, J. Yu *等*，“Internchat：通过与聊天机器人互动解决以视觉为中心的任务”，*arXiv 预印本 arXiv:2305.05662*，2023。

+   [118] C. Li, H. Chen, M. Yan, W. Shen, H. Xu, Z. Wu, Z. Zhang, W. Zhou, Y. Chen, C. Cheng *等*，“Modelscope-agent：使用开源大型语言模型构建您的可定制代理系统”，*arXiv 预印本 arXiv:2309.00986*，2023。

+   [119] W. X. Zhao, K. Zhou, J. Li, T. Tang, X. Wang, Y. Hou, Y. Min, B. Zhang, J. Zhang, Z. Dong *等*，“大型语言模型综述”，*arXiv 预印本 arXiv:2303.18223*，2023。

+   [120] S. Minaee, T. Mikolov, N. Nikzad, M. Chenaghlu, R. Socher, X. Amatriain, 和 J. Gao，“大型语言模型：综述”，*arXiv 预印本 arXiv:2402.06196*，2024。

+   [121] Y. Chang, X. Wang, J. Wang, Y. Wu, L. Yang, K. Zhu, H. Chen, X. Yi, C. Wang, Y. Wang, W. Ye, Y. Zhang, Y. Chang, P. S. Yu, Q. Yang, 和 X. Xie，“大型语言模型评估综述”，*ACM 智能系统技术学报*，第 15 卷，第 3 期，2024 年 3 月。[在线]. 可用：[`doi.org/10.1145/3641289`](https://doi.org/10.1145/3641289)

+   [122] C. Zhang, C. Zhang, M. Zhang, 和 I. S. Kweon，“生成 AI 中的文本到图像扩散模型：综述”，*arXiv 预印本 arXiv:2303.07909*，2023。

+   [123] Z. Xing, Q. Feng, H. Chen, Q. Dai, H. Hu, H. Xu, Z. Wu, 和 Y.-G. Jiang，“视频扩散模型综述”，*arXiv 预印本 arXiv:2310.10647*，2023。

+   [124] Z. Shi, S. Peng, Y. Xu, A. Geiger, Y. Liao, 和 Y. Shen，“3D 表示的深度生成模型：综述”，*arXiv 预印本 arXiv:2210.15663*，2022。

+   [125] C. Zhang, C. Zhang, S. Zheng, M. Zhang, M. Qamar, S.-H. Bae, 和 I. S. Kweon，“用于语音合成的音频扩散模型：文本到语音和语音增强的生成 AI 综述”，*arXiv 预印本 arXiv:2303.13336*，2023。

+   [126] Q. Sun, Y. Fang, L. Wu, X. Wang, 和 Y. Cao，“Eva-clip：改进的 CLIP 大规模训练技术”，*arXiv 预印本 arXiv:2303.15389*，2023。

+   [127] C. Raffel, N. Shazeer, A. Roberts, K. Lee, S. Narang, M. Matena, Y. Zhou, W. Li, 和 P. J. Liu，“使用统一文本到文本变换器探索迁移学习的极限”，*机器学习研究期刊*，第 21 卷，第 140 期，第 1–67 页，2020。

+   [128] L. Wang, C. Ma, X. Feng, Z. Zhang, H. Yang, J. Zhang, Z. Chen, J. Tang, X. Chen, Y. Lin *等*，“基于大型语言模型的自主代理综述”，*arXiv 预印本 arXiv:2308.11432*，2023。

+   [129] S. Yin, C. Fu, S. Zhao, K. Li, X. Sun, T. Xu, 和 E. Chen，“多模态大型语言模型综述”，*arXiv 预印本 arXiv:2306.13549*，2023。

+   [130] J. Wu, W. Gan, Z. Chen, S. Wan, 和 S. Y. Philip, “多模态大型语言模型：综述，” 在 *2023 IEEE 国际大数据会议 (BigData)*. IEEE, 2023, 第 2247–2256 页。

+   [131] I. Goodfellow, J. Pouget-Abadie, M. Mirza, B. Xu, D. Warde-Farley, S. Ozair, A. Courville, 和 Y. Bengio, “生成对抗网络，” *ACM 通讯*，第 63 卷，第 11 期，第 139–144 页，2020 年。

+   [132] D. P. Kingma 和 M. Welling, “自编码变分贝叶斯，” *arXiv 预印本 arXiv:1312.6114*，2013 年。

+   [133] P. Esser, R. Rombach, 和 B. Ommer, “驯化变压器用于高分辨率图像合成，” 在 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2021 年，第 12 873–12 883 页。

+   [134] J. Sohl-Dickstein, E. Weiss, N. Maheswaranathan, 和 S. Ganguli, “使用非平衡热力学的深度无监督学习，” 在 *国际机器学习会议*。 PMLR, 2015, 第 2256–2265 页。

+   [135] J. Ho, A. Jain, 和 P. Abbeel, “去噪扩散概率模型，” *神经信息处理系统进展*，第 33 卷，第 6840–6851 页，2020 年。

+   [136] Y. Tian, D. Krishnan, 和 P. Isola, “对比多视图编码，” 在 *计算机视觉–ECCV 2020：第 16 届欧洲会议，英国格拉斯哥，2020 年 8 月 23–28 日，论文集，第 XI 部分 16*。 Springer, 2020，第 776–794 页。

+   [137] A. Ramesh, P. Dhariwal, A. Nichol, C. Chu, 和 M. Chen, “具有 clip 潜变量的分层文本条件图像生成，” *arXiv 预印本 arXiv:2204.06125*，第 1 卷，第 2 期，第 3 页，2022 年。

+   [138] C. Wang, M. Chai, M. He, D. Chen, 和 J. Liao, “Clip-nerf：文本和图像驱动的神经辐射场操作，” 在 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2022 年，第 3835–3844 页。

+   [139] B. Elizalde, S. Deshmukh, M. Al Ismail, 和 H. Wang, “Clap 学习来自自然语言监督的音频概念，” 在 *ICASSP 2023-2023 IEEE 国际声学、语音和信号处理会议 (ICASSP)*. IEEE, 2023, 第 1–5 页。

+   [140] S. Luo, C. Yan, C. Hu, 和 H. Zhao, “Diff-foley：使用潜在扩散模型同步视频到音频的合成，” *神经信息处理系统进展*，第 36 卷，2024 年。

+   [141] R. Girdhar, A. El-Nouby, Z. Liu, M. Singh, K. V. Alwala, A. Joulin, 和 I. Misra, “Imagebind：一个嵌入空间绑定所有模型，” 在 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 15 180–15 190 页。

+   [142] S. Wu, H. Fei, L. Qu, W. Ji, 和 T.-S. Chua, “Next-gpt：任何到任何的多模态 LLM，” *arXiv 预印本 arXiv:2309.05519*, 2023。

+   [143] Y. Xing, Y. He, Z. Tian, X. Wang, 和 Q. Chen, “视觉与听觉：使用扩散潜变量对齐器的开放域视觉音频生成，” *arXiv 预印本 arXiv:2402.17723*, 2024。

+   [144] Y. Su, T. Lan, H. Li, J. Xu, Y. Wang, 和 D. Cai, “Pandagpt：一个模型来指导所有任务，” *arXiv 预印本 arXiv:2305.16355*，2023 年。

+   [145] H. 图弗龙, T. 拉夫里尔, G. 伊扎卡德, X. 马尔蒂内, M.-A. 拉肖, T. 拉克鲁瓦, B. 罗兹耶尔, N. 戈亚尔, E. 汉布罗, F. 阿扎尔, A. 罗德里格斯, A. 朱林, E. 格雷夫, 和 G. 兰普尔, “Llama: 开放而高效的基础语言模型,” *arXiv 预印本 arXiv:2302.13971*, 2023。

+   [146] A. 拉德福德, K. 纳拉辛汉, T. 萨利曼斯, I. 苏茨克弗 *等*, “通过生成预训练改善语言理解,” 2018。

+   [147] A. 拉德福德, J. 吴, R. 柴尔德, D. 刘安, D. 阿莫德, I. 苏茨克弗 *等*, “语言模型是无监督的多任务学习者,” *OpenAI 博客*, 第 1 卷，第 8 期，第 9 页, 2019。

+   [148] T. 布朗, B. 曼恩, N. 赖德, M. 萨比亚, J. D. 卡普兰, P. 达里瓦尔, A. 尼拉坎坦, P. 夏姆, G. 萨斯特里, A. 阿斯凯尔 *等*, “语言模型是少样本学习者,” *神经信息处理系统进展*, 第 33 卷, 第 1877–1901 页, 2020。

+   [149] Y. 白, A. 琼斯, K. 恩杜斯, A. 阿斯凯尔, A. 陈, N. 达斯萨尔玛, D. 德雷恩, S. 福特, D. 冈普利, T. 亨尼汉 *等*, “通过从人类反馈的强化学习训练一个有帮助且无害的助手,” *arXiv 预印本 arXiv:2204.05862*, 2022。

+   [150] D. 朱, J. 陈, X. 沈, X. 李, 和 M. 艾尔霍塞尼, “Minigpt-4: 通过先进的大型语言模型增强视觉-语言理解,” *arXiv 预印本 arXiv:2304.10592*, 2023。

+   [151] W.-G. 陈, I. 斯皮里东诺娃, J. 杨, J. 高, 和 C. 李, “Llava-interactive: 一个集成图像聊天、分割、生成和编辑的演示,” *arXiv 预印本 arXiv:2311.00571*, 2023。

+   [152] R. 皮, L. 姚, J. 高, J. 张, 和 T. 张, “Perceptiongpt: 有效融合视觉感知到 LLM,” *arXiv 预印本 arXiv:2311.06612*, 2023。

+   [153] R. 皮, J. 高, S. 刁, R. 潘, H. 董, J. 张, L. 姚, J. 韩, H. 许, 和 L. K. T. 张, “Detgpt: 通过推理检测你需要的东西,” *arXiv 预印本 arXiv:2305.14167*, 2023。

+   [154] J. 高, R. 皮, J. 张, J. 叶, W. 钟, Y. 王, L. 洪, J. 韩, H. 许, Z. 李 *等*, “G-llava: 使用多模态大型语言模型解决几何问题,” *arXiv 预印本 arXiv:2312.11370*, 2023。

+   [155] Q. 孙, Q. 余, Y. 崔, F. 张, X. 张, Y. 王, H. 高, J. 刘, T. 黄, 和 X. 王, “多模态中的生成预训练,” *arXiv 预印本 arXiv:2307.05222*, 2023。

+   [156] F. 余, A. 塞夫, Y. 张, S. 宋, T. 芬克豪瑟, 和 J. 肖, “Lsun: 使用深度学习构建的大规模图像数据集,” *arXiv 预印本 arXiv:1506.03365*, 2015。

+   [157] Z. 刘, P. 罗, X. 王, 和 X. 唐, “大规模的 CelebFaces 属性 (Celeba) 数据集,” *检索于 8 月*, 第 15 卷，第 2018 期，第 11 页, 2018。

+   [158] “Dalle-1,” [`openai.com/research/dall-e`](https://openai.com/research/dall-e)。

+   [159] R. 董, C. 韩, Y. 彭, Z. 齐, Z. 戈, J. 杨, L. 赵, J. 孙, H. 周, H. 魏 *等*, “Dreamllm: 协同的多模态理解与创作,” *arXiv 预印本 arXiv:2309.11499*, 2023。

+   [160] “Dalle-3,” [`openai.com/dall-e-3`](https://openai.com/dall-e-3)。

+   [161] J. Y. Koh, R. Salakhutdinov, 和 D. Fried, “将语言模型与图像结合进行多模态生成，” *arXiv 预印本 arXiv:2301.13823*，2023。

+   [162] J. Y. Koh, D. Fried, 和 R. Salakhutdinov, “使用多模态语言模型生成图像，” *arXiv 预印本 arXiv:2305.17216*，2023。

+   [163] L. Yu, Y. Cheng, Z. Wang, V. Kumar, W. Macherey, Y. Huang, D. A. Ross, I. Essa, Y. Bisk, M.-H. Yang *等*，“SPAE：用于冻结 LLM 的多模态生成的语义金字塔自编码器，” *arXiv 预印本 arXiv:2306.17842*，2023。

+   [164] L. Yu, B. Shi, R. Pasunuru, B. Muller, O. Golovneva, T. Wang, A. Babu, B. Tang, B. Karrer, S. Sheynin *等*，“扩展自回归多模态模型：预训练和指令调优，” *arXiv 预印本 arXiv:2309.02591*，2023。

+   [165] K. Zheng, X. He, 和 X. E. Wang, “Minigpt-5：通过生成性令牌的交错视觉和语言生成，” *arXiv 预印本 arXiv:2310.02239*，2023。

+   [166] J. An, Z. Yang, L. Li, J. Wang, K. Lin, Z. Liu, L. Wang, 和 J. Luo, “Openleaf：开放域交错的图像-文本生成和评估，” *arXiv 预印本 arXiv:2310.07749*，2023。

+   [167] Z. Yang, Y. Zhang, F. Meng, 和 J. Zhou, “TEAL：为多模态大型语言模型进行所有的令牌化和嵌入，” *arXiv 预印本 arXiv:2311.04589*，2023。

+   [168] B. Xia, S. Wang, Y. Tao, Y. Wang, 和 J. Jia, “Llmga：基于多模态大型语言模型的生成助手，” *arXiv 预印本 arXiv:2311.16500*，2023。

+   [169] X. Chi, Y. Liu, Z. Jiang, R. Zhang, Z. Lin, R. Zhang, P. Gao, C. Fu, S. Zhang, Q. Liu *等*，“Chatillusion：与视觉指令模型高效对齐的交错生成能力，” *arXiv 预印本 arXiv:2311.17963*，2023。

+   [170] Y. Zhou, R. Zhang, J. Gu, 和 T. Sun, “文本到图像生成的定制化助手，” *arXiv 预印本 arXiv:2312.03045*，2023。

+   [171] X. Shen 和 M. Elhoseiny, “Storygpt-v：作为一致故事可视化工具的大型语言模型，” 2023。

+   [172] X. Hu, R. Wang, Y. Fang, B. Fu, P. Cheng, 和 G. Yu, “Ella：装备扩散模型以提升 LLM 语义对齐，” *arXiv 预印本 arXiv:2403.05135*，2024。

+   [173] S. Zhao, S. Hao, B. Zi, H. Xu, 和 K.-Y. K. Wong, “弥合不同语言模型与生成视觉模型的文本到图像生成，” *arXiv 预印本 arXiv:2403.07860*，2024。

+   [174] J. Cho, A. Zala, 和 M. Bansal, “用于文本到图像生成和评估的视觉编程，” *arXiv 预印本 arXiv:2305.15328*，2023。

+   [175] H. Gani, S. F. Bhat, M. Naseer, S. Khan, 和 P. Wonka, “LLM 蓝图：通过复杂和详细的提示实现文本到图像生成，” *arXiv 预印本 arXiv:2310.10640*，2023。

+   [176] T.-H. Wu, L. Lian, J. E. Gonzalez, B. Li, 和 T. Darrell, “自我纠正的 LLM 控制扩散模型，” *arXiv 预印本 arXiv:2311.16090*，2023。

+   [177] J. Chen, Y. Huang, T. Lv, L. Cui, Q. Chen, 和 F. Wei, “Textdiffuser：扩散模型作为文本画家，” *arXiv 预印本 arXiv:2305.10855*，2023。

+   [178] P. Jia, C. Li, Z. Liu, Y. Shen, X. Chen, Y. Yuan, Y. Zheng, D. Chen, J. Li, X. Xie *等*，“Cole: 用于图形设计的层次生成框架”，*arXiv 预印本 arXiv:2311.16974*，2023 年。

+   [179] S. Zhong, Z. Huang, W. Wen, J. Qin, 和 L. Lin，“Sur-adapter: 使用大型语言模型增强文本到图像的预训练扩散模型”，在*第 31 届 ACM 国际多媒体会议论文集*，2023 年，第 567–578 页。

+   [180] Q. Yu, J. Li, W. Ye, S. Tang, 和 Y. Zhuang，“通过 llms-aigcs 协作进行系统视觉适应的互动数据合成”，*arXiv 预印本 arXiv:2305.12799*，2023 年。

+   [181] X. Wang, B. Zhuang, 和 Q. Wu，“Switchgpt: 为非文本输出适配大型语言模型”，*arXiv 预印本 arXiv:2309.07623*，2023 年。

+   [182] J. Liao, X. Chen, Q. Fu, L. Du, X. He, X. Wang, S. Han, 和 D. Zhang，“抽象概念的文本到图像生成”，*arXiv 预印本 arXiv:2309.14623*，2023 年。

+   [183] Z. Yang, J. Wang, L. Li, K. Lin, C.-C. Lin, Z. Liu, 和 L. Wang，“Idea2img: 使用 gpt-4v (ision) 进行自动图像设计和生成的迭代自我优化”，*arXiv 预印本 arXiv:2310.08541*，2023 年。

+   [184] J.-Y. He, Z.-Q. Cheng, C. Li, J. Sun, W. Xiang, X. Lin, X. Kang, Z. Jin, Y. Hu, B. Luo *等*，“Wordart designer: 用户驱动的艺术排版合成，使用大型语言模型”，*arXiv 预印本 arXiv:2310.18332*，2023 年。

+   [185] J. Sun, D. Fu, Y. Hu, S. Wang, R. Rassin, D.-C. Juan, D. Alon, C. Herrmann, S. van Steenkiste, R. Krishna *等*，“Dreamsync: 将文本到图像生成与图像理解反馈对齐”，*arXiv 预印本 arXiv:2311.17946*，2023 年。

+   [186] Y. Lu, X. Yang, X. Li, X. E. Wang, 和 W. Y. Wang，“Llmscore: 揭示大型语言模型在文本到图像合成评估中的力量”，*神经信息处理系统进展*，第 36 卷，2024 年。

+   [187] V. Ordonez, G. Kulkarni, 和 T. Berg，“Im2text: 使用 100 万张标注照片描述图像”，*神经信息处理系统进展*，第 24 卷，2011 年。

+   [188] T.-Y. Lin, M. Maire, S. Belongie, J. Hays, P. Perona, D. Ramanan, P. Dollár, 和 C. L. Zitnick，“Microsoft coco: 背景中的常见物体”，在*计算机视觉–ECCV 2014: 第 13 届欧洲会议，瑞士苏黎世，2014 年 9 月 6-12 日，论文集，第五部分 13*。 Springer，2014 年，第 740–755 页。

+   [189] C. Jia, Y. Yang, Y. Xia, Y.-T. Chen, Z. Parekh, H. Pham, Q. Le, Y.-H. Sung, Z. Li, 和 T. Duerig，“利用噪声文本监督扩展视觉和视觉语言表征学习”，在*国际机器学习会议*。 PMLR，2021 年，第 4904–4916 页。

+   [190] S. Changpinyo, P. Sharma, N. Ding, 和 R. Soricut，“Conceptual 12m: 推动网络规模的图像-文本预训练以识别长尾视觉概念”，在*IEEE/CVF 计算机视觉与模式识别会议论文集*，2021 年，第 3558–3568 页。

+   [191] K. Srinivasan, K. Raman, J. Chen, M. Bendersky, 和 M. Najork，“Wit: 基于维基百科的图像文本数据集，用于多模态多语言机器学习”，*《第 44 届国际 ACM SIGIR 信息检索研究与发展会议论文集》*，2021 年，第 2443–2449 页。

+   [192] C. Schuhmann, R. Vencu, R. Beaumont, R. Kaczmarczyk, C. Mullis, A. Katta, T. Coombes, J. Jitsev, 和 A. Komatsuzaki，“Laion-400m: 400 百万图像-文本对的开放数据集”，*《arXiv 预印本 arXiv:2111.02114》*，2021 年。

+   [193] Y. Zheng, H. Yang, T. Zhang, J. Bao, D. Chen, Y. Huang, L. Yuan, D. Chen, M. Zeng, 和 F. Wen，“视觉-语言方式下的通用面部表示学习”，*《IEEE/CVF 计算机视觉与模式识别会议论文集》*，2022 年，第 18 697–18 709 页。

+   [194] J.-B. Alayrac, J. Donahue, P. Luc, A. Miech, I. Barr, Y. Hasson, K. Lenc, A. Mensch, K. Millican, M. Reynolds *等人*，“Flamingo: 一种用于少样本学习的视觉语言模型”，*《神经信息处理系统进展》*，第 35 卷，第 23 716–23 736 页，2022 年。

+   [195] LAION-COCO，“https://laion.ai/blog/laion-coco/”，2022 年。 [在线]。可用链接: [`laion.ai/blog/laion-coco/`](https://laion.ai/blog/laion-coco/)

+   [196] C. Schuhmann, R. Beaumont, R. Vencu, C. Gordon, R. Wightman, M. Cherti, T. Coombes, A. Katta, C. Mullis, M. Wortsman *等人*，“Laion-5b: 用于训练下一代图像-文本模型的开放大规模数据集”，*《神经信息处理系统进展》*，第 35 卷，第 25 278–25 294 页，2022 年。

+   [197] Coyo-700M，“https://huggingface.co/datasets/kakaobrain/coyo-700m”，2022 年。 [在线]。可用链接: [`huggingface.co/datasets/kakaobrain/coyo-700m`](https://huggingface.co/datasets/kakaobrain/coyo-700m)

+   [198] S. Huang, L. Dong, W. Wang, Y. Hao, S. Singhal, S. Ma, T. Lv, L. Cui, O. K. Mohammed, B. Patra *等人*，“语言不是你所需的一切: 将感知与语言模型对齐”，*《神经信息处理系统进展》*，第 36 卷，2024 年。

+   [199] W. Zhu, J. Hessel, A. Awadalla, S. Y. Gadre, J. Dodge, A. Fang, Y. Yu, L. Schmidt, W. Y. Wang, 和 Y. Choi，“Multimodal c4: 一个开放的十亿规模图像-文本混合语料库”，*《神经信息处理系统进展》*，第 36 卷，2024 年。

+   [200] H. Liu, C. Li, Q. Wu, 和 Y. J. Lee，“视觉指令调优”，*《神经信息处理系统进展》*，第 36 卷，2024 年。

+   [201] S. Y. Gadre, G. Ilharco, A. Fang, J. Hayase, G. Smyrnis, T. Nguyen, R. Marten, M. Wortsman, D. Ghosh, J. Zhang *等人*，“Datacomp: 寻找下一代多模态数据集”，*《神经信息处理系统进展》*，第 36 卷，2024 年。

+   [202] J. Chen, Y. Huang, T. Lv, L. Cui, Q. Chen, 和 F. Wei，“Textdiffuser: 作为文本画家的扩散模型”，*《神经信息处理系统进展》*，第 36 卷，2024 年。

+   [203] Y. Yang, D. Gui, Y. Yuan, W. Liang, H. Ding, H. Hu 和 K. Chen, “Glyphcontrol: 用于视觉文本生成的符号条件控制，” *神经信息处理系统进展*, 第 36 卷, 2024。

+   [204] B. Li, Y. Zhang, L. Chen, J. Wang, F. Pu, J. Yang, C. Li 和 Z. Liu, “Mimic-it: 多模态上下文指令调优，” *arXiv 预印本 arXiv:2306.05425*, 2023。

+   [205] C. Saharia, W. Chan, S. Saxena, L. Li, J. Whang, E. L. Denton, K. Ghasemipour, R. Gontijo Lopes, B. Karagol Ayan, T. Salimans *等*, “具有深度语言理解的逼真文本到图像扩散模型，” *神经信息处理系统进展*, 第 35 卷，页码 36 479–36 494, 2022。

+   [206] T. Vetter 和 T. Poggio, “从单个示例图像进行线性对象类别和图像合成，” *IEEE 模式分析与机器智能汇刊*, 第 19 卷，第 7 期，页码 733–742, 1997。

+   [207] M. F. Cohen 和 J. R. Wallace, *辐射度与真实图像合成*。摩根·考夫曼, 1993。

+   [208] D. Kirk 和 J. Arvo, “无偏采样技术用于图像合成，” *ACM SIGGRAPH 计算机图形学*, 第 25 卷，第 4 期，页码 153–156, 1991。

+   [209] K. Frans, L. Soros 和 O. Witkowski, “Clipdraw: 通过语言-图像编码器探索文本到图像的合成，” *神经信息处理系统进展*, 第 35 卷，页码 5207–5218, 2022。

+   [210] S. Gu, D. Chen, J. Bao, F. Wen, B. Zhang, D. Chen, L. Yuan 和 B. Guo, “用于文本到图像合成的矢量量化扩散模型，” 在 *IEEE/CVF 计算机视觉与模式识别会议论文集*, 2022, 页码 10 696–10 706。

+   [211] Z. Wang, W. Liu, Q. He, X. Wu 和 Z. Yi, “Clip-gen: 用于文本到图像生成器的无语言训练与 clip，” *arXiv 预印本 arXiv:2203.00386*, 2022。

+   [212] H. Liu, C. Li, Q. Wu 和 Y. J. Lee, “视觉指令调优，” *arXiv 预印本 arXiv:2304.08485*, 2023。

+   [213] J. Li, D. Li, S. Savarese 和 S. Hoi, “Blip-2: 通过冻结的图像编码器和大型语言模型引导语言-图像预训练，” *arXiv 预印本 arXiv:2301.12597*, 2023。

+   [214] T. Lv, Y. Huang, J. Chen, L. Cui, S. Ma, Y. Chang, S. Huang, W. Wang, L. Dong, W. Luo *等*, “Kosmos-2.5: 一个多模态的知识模型，” *arXiv 预印本 arXiv:2309.11419*, 2023。

+   [215] Q. Ye, H. Xu, G. Xu, J. Ye, M. Yan, Y. Zhou, J. Wang, A. Hu, P. Shi, Y. Shi *等*, “mplug-owl: 模块化使大型语言模型具备多模态能力，” *arXiv 预印本 arXiv:2304.14178*, 2023。

+   [216] J. Ye, A. Hu, H. Xu, Q. Ye, M. Yan, Y. Dan, C. Zhao, G. Xu, C. Li, J. Tian *等*, “mplug-docowl: 模块化的多模态大型语言模型用于文档理解，” *arXiv 预印本 arXiv:2307.02499*, 2023。

+   [217] J. Chen, D. Zhu, X. Shen, X. Li, Z. Liu, P. Zhang, R. Krishnamoorthi, V. Chandra, Y. Xiong 和 M. Elhoseiny, “Minigpt-v2: 大型语言模型作为视觉-语言多任务学习的统一接口，” *arXiv 预印本 arXiv:2310.09478*, 2023。

+   [218] R. Zhang, J. Han, A. Zhou, X. Hu, S. Yan, P. Lu, H. Li, P. Gao, 和 Y. Qiao，“Llama-adapter: 使用零初始化注意力的语言模型高效微调，” *arXiv 预印本 arXiv:2303.16199*，2023 年。

+   [219] W. Dai, J. Li, D. Li, A. Tiong, J. Zhao, W. Wang, B. Li, P. Fung, 和 S. Hoi，“Instructblip: 致力于具有指令调优的一般用途视觉-语言模型，” *arXiv 预印本 arXiv:2305.06500*，2023 年。

+   [220] W. Wang, Z. Chen, X. Chen, J. Wu, X. Zhu, G. Zeng, P. Luo, T. Lu, J. Zhou, Y. Qiao *等*，“Visionllm: 大型语言模型也是用于视觉中心任务的开放式解码器，” *arXiv 预印本 arXiv:2305.11175*，2023 年。

+   [221] J. Bai, S. Bai, S. Yang, S. Wang, S. Tan, P. Wang, J. Lin, C. Zhou, 和 J. Zhou，“Qwen-vl: 一种具有多功能的大型视觉-语言模型，” *arXiv 预印本 arXiv:2308.12966*，2023 年。

+   [222] W. Wang, Q. Lv, W. Yu, W. Hong, J. Qi, Y. Wang, J. Ji, Z. Yang, L. Zhao, X. Song *等*，“Cogvlm: 预训练语言模型的视觉专家，” *arXiv 预印本 arXiv:2311.03079*，2023 年。

+   [223] Y. Jin, K. Xu, L. Chen, C. Liao, J. Tan, B. Chen, C. Lei, A. Liu, C. Song, X. Lei *等*，“基于动态离散视觉标记的统一语言-视觉预训练，” *arXiv 预印本 arXiv:2309.04669*，2023 年。

+   [224] Z. Chen, J. Wu, W. Wang, W. Su, G. Chen, S. Xing, Z. Muyan, Q. Zhang, X. Zhu, L. Lu *等*，“Internvl: 扩展视觉基础模型并对齐以实现通用视觉-语言任务，” *arXiv 预印本 arXiv:2312.14238*，2023 年。

+   [225] S. Huang, L. Dong, W. Wang, Y. Hao, S. Singhal, S. Ma, T. Lv, L. Cui, O. K. Mohammed, Q. Liu *等*，“语言并非你所需的一切：将感知与语言模型对齐，” *arXiv 预印本 arXiv:2302.14045*，2023 年。

+   [226] Z. Yang, L. Li, J. Wang, K. Lin, E. Azarnasab, F. Ahmed, Z. Liu, C. Liu, M. Zeng, 和 L. Wang，“Mm-react: 通过提示 ChatGPT 进行多模态推理和行动，” *arXiv 预印本 arXiv:2303.11381*，2023 年。

+   [227] S. Wang, Z. Zhao, X. Ouyang, Q. Wang, 和 D. Shen，“Chatcad: 使用大型语言模型进行医疗图像的互动计算机辅助诊断，” *arXiv 预印本 arXiv:2302.07257*，2023 年。

+   [228] Z. Yang, Z. Gan, J. Wang, X. Hu, Y. Lu, Z. Liu, 和 L. Wang，“对 GPT-3 进行少样本知识问答的实证研究，” 在 *AAAI 人工智能会议论文集*，第 36 卷，第 3 期，2022 年，页码 3081–3089。

+   [229] Z. Gu, B. Zhu, G. Zhu, Y. Chen, M. Tang, 和 J. Wang，“Anomalygpt: 使用大型视觉-语言模型检测工业异常，” *arXiv 预印本 arXiv:2308.15366*，2023 年。

+   [230] J. Qin, J. Wu, W. Chen, Y. Ren, H. Li, H. Wu, X. Xiao, R. Wang, 和 S. Wen，“Diffusiongpt: 基于 LLM 的文本到图像生成系统，” *arXiv 预印本 arXiv:2401.10061*，2024 年。

+   [231] L. Yang, Z. Yu, C. Meng, M. Xu, S. Ermon, 和 B. Cui，“掌握文本到图像扩散：利用多模态 LLMs 进行重新描述、规划和生成，” *arXiv 预印本 arXiv:2401.11708*，2024 年。

+   [232] E. J. Hu, Y. Shen, P. Wallis, Z. Allen-Zhu, Y. Li, S. Wang, L. Wang, 和 W. Chen, “LoRA: 大型语言模型的低秩适配，” 收录于 *国际学习表征会议*，2022 年。[在线]. 可获取：[`openreview.net/forum?id=nZeVKeeFYf9`](https://openreview.net/forum?id=nZeVKeeFYf9)

+   [233] C. Meng, Y. He, Y. Song, J. Song, J. Wu, J.-Y. Zhu, 和 S. Ermon, “Sdedit: 基于随机微分方程的图像引导合成和编辑，” *arXiv 预印本 arXiv:2108.01073*，2021 年。

+   [234] G. Kim, T. Kwon, 和 J. C. Ye, “Diffusionclip: 基于文本引导的扩散模型用于稳健的图像操作，” 收录于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2022 年，第 2426–2435 页。

+   [235] G. Couairon, J. Verbeek, H. Schwenk, 和 M. Cord, “Diffedit: 基于扩散的语义图像编辑与掩码引导，” *arXiv 预印本 arXiv:2210.11427*，2022 年。

+   [236] A. Hertz, R. Mokady, J. Tenenbaum, K. Aberman, Y. Pritch, 和 D. Cohen-Or, “利用交叉注意力控制进行逐提示图像编辑，” *arXiv 预印本 arXiv:2208.01626*，2022 年。

+   [237] R. Mokady, A. Hertz, K. Aberman, Y. Pritch, 和 D. Cohen-Or, “利用引导扩散模型进行真实图像编辑的空文本反演，” 收录于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 6038–6047 页。

+   [238] B. Kawar, S. Zada, O. Lang, O. Tov, H. Chang, T. Dekel, I. Mosseri, 和 M. Irani, “Imagic: 基于文本的真实图像编辑与扩散模型，” 收录于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 6007–6017 页。

+   [239] N. Tumanyan, M. Geyer, S. Bagon, 和 T. Dekel, “用于文本驱动的图像到图像翻译的即插即用扩散特征，” 收录于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 1921–1930 页。

+   [240] R. Morita, Z. Zhang, M. M. Ho, 和 J. Zhou, “带复杂文本指令的交互式图像操作，” 收录于 *IEEE/CVF 冬季计算机视觉应用会议论文集*，2023 年，第 1053–1062 页。

+   [241] Z. Zhang, L. Han, A. Ghosh, D. N. Metaxas, 和 J. Ren, “Sine: 使用文本到图像扩散模型的单图像编辑，” 收录于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 6027–6037 页。

+   [242] G. Parmar, K. Kumar Singh, R. Zhang, Y. Li, J. Lu, 和 J.-Y. Zhu, “零样本图像到图像翻译，” 收录于 *ACM SIGGRAPH 2023 会议论文集*，2023 年，第 1–11 页。

+   [243] V. Goel, E. Peruzzo, Y. Jiang, D. Xu, N. Sebe, T. Darrell, Z. Wang, 和 H. Shi, “Pair-diffusion: 基于结构和外观配对扩散模型的对象级图像编辑，” *arXiv 预印本 arXiv:2303.17546*，2023 年。

+   [244] M. Cao, X. Wang, Z. Qi, Y. Shan, X. Qie, 和 Y. Zheng, “Masactrl: 无需调优的互自注意力控制用于一致的图像合成和编辑，” *arXiv 预印本 arXiv:2304.08465*，2023 年。

+   [245] T. Nguyen, Y. Li, U. Ojha, 和 Y. J. Lee, “视觉指令反演: 通过视觉提示进行图像编辑，” *arXiv 预印本 arXiv:2307.14331*，2023 年。

+   [246] A. Mirzaei, T. Aumentado-Armstrong, M. A. Brubaker, J. Kelly, A. Levinshtein, K. G. Derpanis, 和 I. Gilitschenski, “注意你的步骤: 通过文本指令进行局部图像和场景编辑，” *arXiv 预印本 arXiv:2308.08947*，2023 年。

+   [247] C. Mou, X. Wang, J. Song, Y. Shan, 和 J. Zhang, “Dragondiffusion: 实现扩散模型上的拖拽风格操作，” *arXiv 预印本 arXiv:2307.02421*，2023 年。

+   [248] ——, “Diffeditor: 提高基于扩散的图像编辑的准确性和灵活性，” *arXiv 预印本 arXiv:2402.02583*，2024 年。

+   [249] T. Brooks, A. Holynski, 和 A. A. Efros, “Instructpix2pix: 学习遵循图像编辑指令，” *arXiv 预印本 arXiv:2211.09800*，2022 年。

+   [250] X. Cui, Z. Li, P. Li, Y. Hu, H. Shi, C. Cao, 和 Z. He, “Chatedit: 通过对话实现多轮交互式面部图像编辑，” 见 *2023 年自然语言处理实证方法大会论文集*，2023 年，第 14,567–14,583 页。

+   [251] T.-J. Fu, W. Hu, X. Du, W. Y. Wang, Y. Yang, 和 Z. Gan, “通过多模态大型语言模型指导基于指令的图像编辑，” *arXiv 预印本 arXiv:2309.17102*，2023 年。

+   [252] S. Sheynin, A. Polyak, U. Singer, Y. Kirstain, A. Zohar, O. Ashual, D. Parikh, 和 Y. Taigman, “Emu edit: 通过识别和生成任务进行精确图像编辑，” *arXiv 预印本 arXiv:2311.10089*，2023 年。

+   [253] Y. Huang, L. Xie, X. Wang, Z. Yuan, X. Cun, Y. Ge, J. Zhou, C. Dong, R. Huang, R. Zhang *等*，“Smartedit: 使用多模态大型语言模型探索复杂的基于指令的图像编辑，” 见 *IEEE/CVF 计算机视觉与模式识别大会论文集*，2024 年。

+   [254] Z. Geng, B. Yang, T. Hang, C. Li, S. Gu, T. Zhang, J. Bao, Z. Zhang, H. Hu, D. Chen *等*，“Instructdiffusion: 用于视觉任务的通用建模接口，” *arXiv 预印本 arXiv:2309.03895*，2023 年。

+   [255] J. Z. Wu, Y. Ge, X. Wang, S. W. Lei, Y. Gu, Y. Shi, W. Hsu, Y. Shan, X. Qie, 和 M. Z. Shou, “Tune-a-video: 一次性调整图像扩散模型用于文本到视频生成，” 见 *IEEE/CVF 国际计算机视觉大会论文集*，2023 年，第 7,623–7,633 页。

+   [256] E. Molad, E. Horwitz, D. Valevski, A. R. Acha, Y. Matias, Y. Pritch, Y. Leviathan, 和 Y. Hoshen, “Dreamix: 视频扩散模型作为通用视频编辑器，” *arXiv 预印本 arXiv:2302.01329*，2023 年。

+   [257] S. Liu, Y. Zhang, W. Li, Z. Lin, 和 J. Jia, “Video-p2p: 通过交叉注意力控制进行视频编辑，” *arXiv 预印本 arXiv:2303.04761*，2023 年。

+   [258] C. Qi, X. Cun, Y. Zhang, C. Lei, X. Wang, Y. Shan, 和 Q. Chen, “Fatezero: 融合注意力进行零样本文本基础的视频编辑，” 见 *IEEE/CVF 国际计算机视觉大会论文集*，2023 年，第 15,932–15,942 页。

+   [259] D. Ceylan, C.-H. P. Huang, 和 N. J. Mitra, “Pix2video: 使用图像扩散的视频编辑,” 在 *IEEE/CVF 国际计算机视觉会议论文集*, 2023, pp. 23 206–23 217。

+   [260] W. Chai, X. Guo, G. Wang, 和 Y. Lu, “Stablevideo: 基于文本驱动的一致性感知扩散视频编辑,” 在 *IEEE/CVF 国际计算机视觉会议论文集*, 2023, pp. 23 040–23 050。

+   [261] S. Yang, Y. Zhou, Z. Liu, 和 C. C. Loy, “重新渲染视频：零-shot 文本引导的视频到视频翻译,” 在 *SIGGRAPH Asia 2023 会议论文*, 2023, pp. 1–11。

+   [262] M. Geyer, O. Bar-Tal, S. Bagon, 和 T. Dekel, “Tokenflow: 一致扩散特征用于一致的视频编辑,” *arXiv 预印本 arXiv:2307.10373*, 2023。

+   [263] H. Ouyang, Q. Wang, Y. Xiao, Q. Bai, J. Zhang, K. Zheng, X. Zhou, Q. Chen, 和 Y. Shen, “Codef: 内容变形场用于时间一致的视频处理,” *arXiv 预印本 arXiv:2308.07926*, 2023。

+   [264] J. H. Liew, H. Yan, J. Zhang, Z. Xu, 和 J. Feng, “Magicedit: 高保真和时间一致的视频编辑,” *arXiv 预印本 arXiv:2308.14749*, 2023。

+   [265] Y. Ma, X. Cun, Y. He, C. Qi, X. Wang, Y. Shan, X. Li, 和 Q. Chen, “Magicstick: 通过控制手柄变换进行可控的视频编辑,” *arXiv 预印本 arXiv:2312.03047*, 2023。

+   [266] J. Cheng, T. Xiao, 和 T. He, “使用合成数据集进行一致的视频到视频传输,” *arXiv 预印本 arXiv:2311.00213*, 2023。

+   [267] B. Qin, J. Li, S. Tang, T.-S. Chua, 和 Y. Zhuang, “Instructvid2vid: 使用自然语言指令进行可控的视频编辑,” *arXiv 预印本 arXiv:2305.12328*, 2023。

+   [268] T. Brooks, A. Holynski, 和 A. A. Efros, “Instructpix2pix: 学习遵循图像编辑指令,” 在 *IEEE/CVF 计算机视觉与模式识别会议论文集*, 2023, pp. 18 392–18 402。

+   [269] B. Wu, S. Yu, Z. Chen, J. B. Tenenbaum, 和 C. Gan, “Star: 现实世界视频中的情境推理基准,” 在 *第三十五届神经信息处理系统会议数据集与基准跟踪 (第二轮)*, 2021。

+   [270] Z. Liu, L. Wang, W. Wu, C. Qian, 和 T. Lu, “Tam: 用于视频识别的时间自适应模块,” 在 *IEEE/CVF 国际计算机视觉会议论文集*, 2021, pp. 13 708–13 718。

+   [271] M. Zhao, B. Li, J. Wang, W. Li, W. Zhou, L. Zhang, S. Xuyang, Z. Yu, X. Yu, G. Li *等*, “面向视频文本视觉问答：基准测试与基线,” *神经信息处理系统进展*, vol. 35, pp. 35 549–35 562, 2022。

+   [272] M. Bain, A. Nagrani, G. Varol, 和 A. Zisserman, “冻结在时间中：用于端到端检索的联合视频和图像编码器,” 在 *IEEE/CVF 国际计算机视觉会议论文集*, 2021, pp. 1728–1738。

+   [273] A. Yang, A. Miech, J. Sivic, I. Laptev, 和 C. Schmid，“通过冻结的双向语言模型进行零样本视频问答，” *神经信息处理系统进展*，第 35 卷，第 124–141 页，2022 年。

+   [274] ——，“从网络视频中学习回答视觉问题，” *arXiv 预印本 arXiv:2205.05019*，2022 年。

+   [275] K. Lin, L. Li, C.-C. Lin, F. Ahmed, Z. Gan, Z. Liu, Y. Lu, 和 L. Wang，“Swinbert: 具有稀疏注意力的端到端变换器用于视频字幕生成，” *IEEE/CVF 计算机视觉与模式识别会议论文集*，2022 年，第 17,949–17,958 页。

+   [276] J. Lin, C. Gan, 和 S. Han，“Tsm: 用于高效视频理解的时间偏移模块，” *IEEE/CVF 国际计算机视觉会议论文集*，2019 年，第 7083–7093 页。

+   [277] G. Bertasius, H. Wang, 和 L. Torresani，“时空注意力是否是视频理解所需的一切？” *ICML*，第 2 卷，第 3 期，2021 年，第 4 页。

+   [278] C.-Y. Wu, C. Feichtenhofer, H. Fan, K. He, P. Krahenbuhl, 和 R. Girshick，“用于详细视频理解的长期特征库，” *IEEE/CVF 计算机视觉与模式识别会议论文集*，2019 年，第 284–293 页。

+   [279] H. Zhang, X. Li, 和 L. Bing，“Video-llama: 一种用于视频理解的指令调优视听语言模型，” *arXiv 预印本 arXiv:2306.02858*，2023 年。

+   [280] J. Chen, D. Zhu, K. Haydarov, X. Li, 和 M. Elhoseiny，“Video chatcaptioner: 朝着丰富的时空描述前进，” *arXiv 预印本 arXiv:2304.04227*，2023 年。

+   [281] A. Blattmann, R. Rombach, H. Ling, T. Dockhorn, S. W. Kim, S. Fidler, 和 K. Kreis，“Align your latents: 使用潜在扩散模型进行高分辨率视频合成，” *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 22,563–22,575 页。

+   [282] Y. He, M. Xia, H. Chen, X. Cun, Y. Gong, J. Xing, Y. Zhang, X. Wang, C. Weng, Y. Shan *等人*，“Animate-a-story: 使用检索增强的视频生成进行讲故事，” *arXiv 预印本 arXiv:2307.06940*，2023 年。

+   [283] Y. Ma, Y. He, X. Cun, X. Wang, S. Chen, X. Li, 和 Q. Chen，“Follow your pose: 基于姿态的文本到视频生成，使用无姿态视频，” *AAAI 人工智能会议论文集*，第 38 卷，第 5 期，2024 年，第 4117–4125 页。

+   [284] Y. He, H. Liu, H. Chen, X. Cun, X. Wang, Y. Shan *等人*，“Make-your-video: 使用文本和结构指导进行定制视频生成。” *IEEE 视觉与计算机图形学学报*，2024 年。

+   [285] H. Qiu, M. Xia, Y. Zhang, Y. He, X. Wang, Y. Shan, 和 Z. Liu，“Freenoise: 通过噪声重新调度实现无调优的长视频扩散，” *arXiv 预印本 arXiv:2310.15169*，2023 年。

+   [286] Y. Ma, Y. He, H. Wang, A. Wang, C. Qi, C. Cai, X. Li, Z. Li, H.-Y. Shum, W. Liu *等人*，“Follow-your-click: 通过简短提示进行开放领域区域图像动画，” *arXiv 预印本 arXiv:2403.08268*，2024 年。

+   [287] Y. Bao, D. Qiu, G. Kang, B. Zhang, B. Jin, K. Wang, 和 P. Yan，“Latentwarp: 一致的扩散潜变量用于零样本视频到视频翻译，” *arXiv 预印本 arXiv:2311.00353*，2023。

+   [288] J. Xu, T. Mei, T. Yao, 和 Y. Rui，“Msr-vtt: 大规模视频描述数据集，用于弥合视频与语言之间的鸿沟，” *2016 IEEE 计算机视觉与模式识别会议 (CVPR)*，第 5288–5296 页，2016\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:206594535`](https://api.semanticscholar.org/CorpusID:206594535)

+   [289] A. Rohrbach, A. Torabi, M. Rohrbach, N. Tandon, C. J. Pal, H. Larochelle, A. C. Courville, 和 B. Schiele，“电影描述，” *国际计算机视觉杂志*，卷 123，第 94 – 120 页，2016\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:18217052`](https://api.semanticscholar.org/CorpusID:18217052)

+   [290] R. Krishna, K. Hata, F. Ren, L. Fei-Fei, 和 J. C. Niebles，“视频中的密集描述事件，” *2017 IEEE 国际计算机视觉会议 (ICCV)*，第 706–715 页，2017\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:1026139`](https://api.semanticscholar.org/CorpusID:1026139)

+   [291] R. Sanabria, O. Caglayan, S. Palaskar, D. Elliott, L. Barrault, L. Specia, 和 F. Metze，“How2: 大规模多模态语言理解数据集，” *ArXiv*，卷 abs/1811.00347，2018\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:53186236`](https://api.semanticscholar.org/CorpusID:53186236)

+   [292] X. E. Wang, J. Wu, J. Chen, L. Li, Y. fang Wang, 和 W. Y. Wang，“Vatex: 大规模高质量多语言数据集，用于视频与语言研究，” *2019 IEEE/CVF 国际计算机视觉会议 (ICCV)*，第 4580–4590 页，2019\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:102352148`](https://api.semanticscholar.org/CorpusID:102352148)

+   [293] A. Miech, D. Zhukov, J.-B. Alayrac, M. Tapaswi, I. Laptev, 和 J. Sivic，“Howto100m: 通过观看一亿个叙述视频片段学习文本-视频嵌入，” *2019 IEEE/CVF 国际计算机视觉会议 (ICCV)*，第 2630–2640 页，2019\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:182952863`](https://api.semanticscholar.org/CorpusID:182952863)

+   [294] J. C. Stroud, D. A. Ross, C. Sun, J. Deng, R. Sukthankar, 和 C. Schmid，“从文本网页监督中学习视频表征，” *ArXiv*，卷 abs/2007.14937，2020\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:220845567`](https://api.semanticscholar.org/CorpusID:220845567)

+   [295] R. Zellers, X. Lu, J. Hessel, Y. Yu, J. S. Park, J. Cao, A. Farhadi, 和 Y. Choi，“Merlot: 多模态神经脚本知识模型，” 收录于 *Neural Information Processing Systems*，2021\. [在线]. 可用: [`api.semanticscholar.org/CorpusID:235352775`](https://api.semanticscholar.org/CorpusID:235352775)

+   [296] H. 薛，T. 杭，Y. 曾，Y. 孙，B. 刘，H. 杨，J. 符，和 B. 郭，“用大规模视频转录提高高分辨率视频语言表示，” *2022 IEEE/CVF 计算机视觉与模式识别会议（CVPR）*，pp. 5026–5035，2021．[在线]。可访问[`api.semanticscholar.org/CorpusID:244462849`](https://api.semanticscholar.org/CorpusID:244462849)

+   [297] A. Nagrani，P. H. Seo，B. Seybold，A. Hauth，S. Manén，C. Sun 和 C. Schmid，“从图像标题中学习音频-视频模态，”在*欧洲计算机视觉大会*，2022 年．[在线]。可访问[`api.semanticscholar.org/CorpusID:247939759`](https://api.semanticscholar.org/CorpusID:247939759)

+   [298] W. 王，H. 杨，Z. 庹，H. 贺，J. 祝，J. 符和 J. 刘，“Videofactory：文本到视频生成中的空间扩散注意力交换，” *ArXiv*，vol．abs/2305.10874，2023．[在线]。可访问[`api.semanticscholar.org/CorpusID:258762479`](https://api.semanticscholar.org/CorpusID:258762479)

+   [299] Y. 王，Y. 何，Y. 李，K. 李，J. 余，X. J. 麻，X. 陈，Y. 王，P. 罗，Z. 刘，Y. 王，L. 王和 Y. 乔，“Internvid：用于多模态理解和生成的大规模视频文本数据集，” *ArXiv*，vol．abs/2307.06942，2023．[在线]。可访问[`api.semanticscholar.org/CorpusID:259847783`](https://api.semanticscholar.org/CorpusID:259847783)

+   [300] T.-S. 陈，A. Siarohin，W. Menapace，E. Deyneka，H.-w. 赵，B. E. 全，Y. 方，H.-Y. 李，J. 任，M.-H. 杨*等*，“Panda-70m：使用多个跨模态教师的 70m 视频标题，” *arXiv preprint arXiv:2402.19479*，2024。

+   [301] “Vript”，[`github.com/mutonix/Vript`](https://github.com/mutonix/Vript)。

+   [302] J. 余，H. 朱，L. 姜，C. C. 蒂，W. T. 蔡和 W. 吴，“Celebv-text：大规模面部文本视频数据集，” *2023 IEEE/CVF 计算机视觉与模式识别会议（CVPR）*，pp. 14 805–14 814，2023．[在线]。可访问[`api.semanticscholar.org/CorpusID:257767123`](https://api.semanticscholar.org/CorpusID:257767123)

+   [303] X. 李，Q. 张，D. 康，W. 程，Y. 高，J. 张，Z. 梁，J. 廖，Y.-P. 曹和 Y. 单，“3D 生成的进展：一项调查，” *arXiv preprint arXiv:2401.17807*, 2024．

+   [304] M. 迪基，D. 施文克，J. 萨尔瓦多，L. 韦斯，O. 米歇尔，E. 范德比尔特，L. 施密特，K. 艾哈赛，A. 坎布哈维和 A. 法哈迪，“Objaverse：带有注释的 3D 对象宇宙，”在*IEEE/CVF 计算机视觉与模式识别大会*，2023 年，pp．13 142–13 153。

+   [305] A. 拉梅什，M. 帕夫洛夫，G. 戈，S. 格雷，C. 沃斯，A. 拉德福德，M. 陈和 I. 苏茨克维尔，“零-shot 文本到图像生成，”在*国际机器学习大会*。PMLR，2021 年，pp. 8821–8831。

+   [306] A. Nichol, P. Dhariwal, A. Ramesh, P. Shyam, P. Mishkin, B. McGrew, I. Sutskever, 和 M. Chen, “Glide: 通过文本引导扩散模型实现照片级图像生成与编辑,” *arXiv 预印本 arXiv:2112.10741*, 2021.

+   [307] H. Wang, X. Du, J. Li, R. A. Yeh, 和 G. Shakhnarovich, “分数雅可比链: 将预训练的 2D 扩散模型提升到 3D 生成,” 在 *IEEE/CVF 计算机视觉与模式识别会议论文集*, 2023, pp. 12 619–12 629.

+   [308] B. Mildenhall, P. P. Srinivasan, M. Tancik, J. T. Barron, R. Ramamoorthi, 和 R. Ng, “Nerf: 通过神经辐射场表示场景以进行视图合成,” *ACM 通讯*, vol. 65, no. 1, pp. 99–106, 2021.

+   [309] P. Wang, L. Liu, Y. Liu, C. Theobalt, T. Komura, 和 W. Wang, “Neus: 通过体积渲染学习神经隐式表面以进行多视图重建,” *arXiv 预印本 arXiv:2106.10689*, 2021.

+   [310] T. Shen, J. Gao, K. Yin, M.-Y. Liu, 和 S. Fidler, “深度行进四面体: 高分辨率 3D 形状合成的混合表示,” *神经信息处理系统进展*, vol. 34, pp. 6087–6101, 2021.

+   [311] M. Deitke, R. Liu, M. Wallingford, H. Ngo, O. Michel, A. Kusupati, A. Fan, C. Laforte, V. Voleti, S. Y. Gadre *等*, “Objaverse-xl: 一个包含 1000 万+ 3D 对象的宇宙,” *神经信息处理系统进展*, vol. 36, 2024.

+   [312] J. Reizenstein, R. Shapovalov, P. Henzler, L. Sbordone, P. Labatut, 和 D. Novotny, “3D 常见对象: 大规模真实世界 3D 类别重建的学习与评估,” 在 *IEEE/CVF 国际计算机视觉大会论文集*, 2021, pp. 10 901–10 911.

+   [313] A. Nichol, H. Jun, P. Dhariwal, P. Mishkin, 和 M. Chen, “Point-e: 从复杂提示生成 3D 点云的系统,” *arXiv 预印本 arXiv:2212.08751*, 2022.

+   [314] J. Lei, Y. Zhang, K. Jia *等*, “Tango: 基于文本驱动的光照分解下的照片级真实感与鲁棒性 3D 风格化,” *神经信息处理系统进展*, vol. 35, pp. 30 923–30 936, 2022.

+   [315] Y. Ma, X. Zhang, X. Sun, J. Ji, H. Wang, G. Jiang, W. Zhuang, 和 R. Ji, “X-mesh: 通过动态文本引导实现快速而准确的文本驱动 3D 风格化,” 在 *IEEE/CVF 国际计算机视觉大会论文集*, 2023, pp. 2749–2760.

+   [316] L. Dinh, J. Sohl-Dickstein, 和 S. Bengio, “使用真实 NVP 的密度估计,” *arXiv 预印本 arXiv:1605.08803*, 2016.

+   [317] A. Jain, B. Mildenhall, J. T. Barron, P. Abbeel, 和 B. Poole, “零样本文本引导的对象生成与梦境场,” 在 *IEEE/CVF 计算机视觉与模式识别会议论文集*, 2022, pp. 867–876.

+   [318] F. Yin, X. Chen, C. Zhang, B. Jiang, Z. Zhao, J. Fan, G. Yu, T. Li, 和 T. Chen, “Shapegpt: 使用统一的多模态语言模型进行 3D 形状生成,” *arXiv 预印本 arXiv:2311.17618*, 2023.

+   [319] G. Tevet, B. Gordon, A. Hertz, A. H. Bermano, 和 D. Cohen-Or，"Motionclip: 将人体动作生成暴露于剪辑空间"，发表于*欧洲计算机视觉会议*。   Springer，2022，页码 358–374。

+   [320] B. Jiang, X. Chen, W. Liu, J. Yu, G. Yu, 和 T. Chen，"Motiongpt: 将人体动作视为外语"，*神经信息处理系统进展*，第 36 卷，2024。

+   [321] Z. Zhou 和 S. Tulsiani，"Sparsefusion: 蒸馏视角条件扩散用于三维重建"，发表于*CVPR*，2023。

+   [322] Z. Wan, D. Paschalidou, I. Huang, H. Liu, B. Shen, X. Xiang, J. Liao, 和 L. Guibas，"Cad: 通过对抗性蒸馏实现照片级真实三维生成"，*arXiv 预印本 arXiv:2312.06663*，2023。

+   [323] B. Yang, W. Dong, L. Ma, W. Hu, X. Liu, Z. Cui, 和 Y. Ma，"Dreamspace: 用文本驱动的全景纹理传播来梦幻你的房间空间"，发表于*2024 IEEE 虚拟现实与三维用户界面会议（VR）*。   IEEE，2024，页码 650–660。

+   [324] G. Metzer, E. Richardson, O. Patashnik, R. Giryes, 和 D. Cohen-Or，"用于形状引导三维形状和纹理生成的潜在神经辐射场"，发表于*IEEE/CVF 计算机视觉与模式识别会议论文集*，2023，页码 12 663–12 673。

+   [325] O. Katzir, O. Patashnik, D. Cohen-Or, 和 D. Lischinski，"无噪声评分蒸馏"，2023。

+   [326] M. Armandpour, H. Zheng, A. Sadeghian, A. Sadeghian, 和 M. Zhou，"重新设想负面提示算法: 将二维扩散转化为三维，缓解 Janus 问题及更多"，*arXiv 预印本 arXiv:2304.04968*，2023。

+   [327] L. Zhou, A. Shih, C. Meng, 和 S. Ermon，"Dreampropeller: 通过并行采样超级充能文本到三维生成"，*arXiv 预印本 arXiv:2311.17082*，2023。

+   [328] C. Yu, G. Lu, Y. Zeng, J. Sun, X. Liang, H. Li, Z. Xu, S. Xu, W. Zhang, 和 H. Xu，"通过仅使用图像实现高保真文本引导的三维人脸生成和操控"，发表于*IEEE/CVF 国际计算机视觉会议论文集*，2023，页码 15 326–15 337。

+   [329] C. Zhang, Y. Chen, Y. Fu, Z. Zhou, G. Yu, B. Wang, B. Fu, T. Chen, G. Lin, 和 C. Shen，"Styleavatar3d: 利用图像-文本扩散模型生成高保真三维头像"，*arXiv 预印本 arXiv:2305.19012*，2023。

+   [330] T. Wang, B. Zhang, T. Zhang, S. Gu, J. Bao, T. Baltrusaitis, J. Shen, D. Chen, F. Wen, Q. Chen *等*，"Rodin: 一个用于使用扩散塑造三维数字头像的生成模型"，发表于*IEEE/CVF 计算机视觉与模式识别会议论文集*，2023，页码 4563–4573。

+   [331] S. Aneja, J. Thies, A. Dai, 和 M. Nießner，"Clipface: 基于文本的纹理三维可变模型编辑"，发表于*ACM SIGGRAPH 2023 会议论文集*，2023，页码 1–11。

+   [332] M. Wu, H. Zhu, L. Huang, Y. Zhuang, Y. Lu, 和 X. Cao，"从自然语言描述生成高保真三维人脸"，发表于*IEEE/CVF 计算机视觉与模式识别会议论文集*，2023，页码 4521–4530。

+   [333] T. Liao, H. Yi, Y. Xiu, J. Tang, Y. Huang, J. Thies, 和 M. J. Black, “Tada! 从文本生成可动画数字头像，” *arXiv 预印本 arXiv:2308.10899*，2023 年。

+   [334] S. Huang, Z. Yang, L. Li, Y. Yang, 和 J. Jia, “Avatarfusion: 使用 2D 扩散的零样本服装解耦 3D 头像生成，” 见 *第 31 届 ACM 国际多媒体会议论文集*，2023 年，页 5734–5745。

+   [335] X. Han, Y. Cao, K. Han, X. Zhu, J. Deng, Y.-Z. Song, T. Xiang, 和 K.-Y. K. Wong, “Headsculpt: 利用文本制作 3D 头像，” *arXiv 预印本 arXiv:2306.03038*，2023 年。

+   [336] Y. Cao, Y.-P. Cao, K. Han, Y. Shan, 和 K.-Y. K. Wong, “Dreamavatar: 通过扩散模型进行文本和形状引导的 3D 人类头像生成，” *arXiv 预印本 arXiv:2304.00916*，2023 年。

+   [337] H. Zhang, B. Chen, H. Yang, L. Qu, X. Wang, L. Chen, C. Long, F. Zhu, K. Du, 和 M. Zheng, “Avatarverse: 从文本和姿势生成高质量且稳定的 3D 头像，” *arXiv 预印本 arXiv:2308.03610*，2023 年。

+   [338] L. Zhang, Q. Qiu, H. Lin, Q. Zhang, C. Shi, W. Yang, Y. Shi, S. Yang, L. Xu, 和 J. Yu, “Dreamface: 在文本指导下逐步生成可动画的 3D 面孔，” *arXiv 预印本 arXiv:2304.03117*，2023 年。

+   [339] F. Hong, M. Zhang, L. Pan, Z. Cai, L. Yang, 和 Z. Liu, “Avatarclip: 零样本文本驱动的 3D 头像生成和动画，” *arXiv 预印本 arXiv:2205.08535*，2022 年。

+   [340] N. Kolotouros, T. Alldieck, A. Zanfir, E. G. Bazavan, M. Fieraru, 和 C. Sminchisescu, “Dreamhuman: 从文本生成可动画的 3D 头像，” *arXiv 预印本 arXiv:2306.09329*，2023 年。

+   [341] X. Huang, R. Shao, Q. Zhang, H. Zhang, Y. Feng, Y. Liu, 和 Q. Wang, “Humannorm: 学习高质量和逼真的 3D 人类生成的常规扩散模型，” *arXiv 预印本 arXiv:2310.01406*，2023 年。

+   [342] Y. Zeng, Y. Lu, X. Ji, Y. Yao, H. Zhu, 和 X. Cao, “Avatarbooth: 高质量和可定制的 3D 人类头像生成，” *arXiv 预印本 arXiv:2306.09864*，2023 年。

+   [343] D. Wang, H. Meng, Z. Cai, Z. Shao, Q. Liu, L. Wang, M. Fan, Y. Shan, X. Zhan, 和 Z. Wang, “Headevolver: 通过局部可学习网格变形从文本生成头像，” *arXiv 预印本 arXiv:2403.09326*，2024 年。

+   [344] H. Liu, X. Wang, Z. Wan, Y. Shen, Y. Song, J. Liao, 和 Q. Chen, “Headartist: 条件文本 3D 头部生成与自评分蒸馏，” *arXiv 预印本 arXiv:2312.07539*，2023 年。

+   [345] Y. Shi, P. Wang, J. Ye, M. Long, K. Li, 和 X. Yang, “Mvdream: 用于 3D 生成的多视角扩散，” *arXiv 预印本 arXiv:2308.16512*，2023 年。

+   [346] Y. Kant, Z. Wu, M. Vasilkovsky, G. Qian, J. Ren, R. A. Guler, B. Ghanem, S. Tulyakov, I. Gilitschenski, 和 A. Siarohin, “Spad: 空间感知多视角扩散器，” *arXiv 预印本 arXiv:2402.05235*，2024 年。

+   [347] Z. Liu, Y. Li, Y. Lin, X. Yu, S. Peng, Y.-P. Cao, X. Qi, X. Huang, D. Liang, 和 W. Ouyang, “Unidream: 统一的扩散先验用于可重新照明的文本到 3D 生成，” 2023 年。

+   [348] L. Qiu, G. Chen, X. Gu, Q. Zuo, M. Xu, Y. Wu, W. Yuan, Z. Dong, L. Bo, 和 X. Han, “Richdreamer: 一种通用的文本到 3D 的正常深度扩散模型，用于细节丰富性，” *arXiv 预印本 arXiv:2311.16918*，2023 年。

+   [349] J. Li, H. Tan, K. Zhang, Z. Xu, F. Luan, Y. Xu, Y. Hong, K. Sunkavalli, G. Shakhnarovich, 和 S. Bi, “Instant3d: 通过稀疏视图生成和大型重建模型实现快速文本到 3D 转换，” *arXiv 预印本 arXiv:2311.06214*，2023 年。

+   [350] J. Tang, Z. Chen, X. Chen, T. Wang, G. Zeng, 和 Z. Liu, “Lgm: 高分辨率 3D 内容创建的大型多视角高斯模型，” *arXiv 预印本 arXiv:2402.05054*，2024 年。

+   [351] X. Yinghao, S. Zifan, Y. Wang, C. Hansheng, Y. Ceyuan, P. Sida, S. Yujun, 和 W. Gordon, “Grm: 用于高效 3D 重建和生成的大型高斯重建模型，” 2024 年。

+   [352] H. Jun 和 A. Nichol, “Shap-e: 生成条件 3D 隐式函数，” *arXiv 预印本 arXiv:2305.02463*，2023 年。

+   [353] Z. Hu, A. Iscen, A. Jain, T. Kipf, Y. Yue, D. A. Ross, C. Schmid, 和 A. Fathi, “Scenecraft: 用于合成 3D 场景的 LLM 代理，生成 Blender 代码，” *arXiv 预印本 arXiv:2403.01248*，2024 年。

+   [354] R. Xu, X. Wang, T. Wang, Y. Chen, J. Pang, 和 D. Lin, “Pointllm: 赋能大型语言模型理解点云，” *arXiv 预印本 arXiv:2308.16911*，2023 年。

+   [355] Y. Hong, H. Zhen, P. Chen, S. Zheng, Y. Du, Z. Chen, 和 C. Gan, “3d-llm: 将 3D 世界注入大型语言模型，” *arXiv 预印本 arXiv:2307.12981*，2023 年。

+   [356] O. Gordon, O. Avrahami, 和 D. Lischinski, “Blended-nerf: 在现有神经辐射场中实现零样本物体生成与融合，” *arXiv 预印本 arXiv:2306.12760*，2023 年。

+   [357] W. Gao, N. Aigerman, T. Groueix, V. Kim, 和 R. Hanocka, “Textdeformer: 使用文本指导的几何操作，” 收录于 *ACM SIGGRAPH 2023 会议论文集*，2023 年，第 1–11 页。

+   [358] C. Bao, Y. Zhang, B. Yang, T. Fan, Z. Yang, H. Bao, G. Zhang, 和 Z. Cui, “Sine: 基于语义的图像神经场编辑与先验指导编辑场，” 收录于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 20 919–20 929 页。

+   [359] A. Mikaeili, O. Perel, M. Safaee, D. Cohen-Or, 和 A. Mahdavi-Amiri, “Sked: 基于草图的文本驱动 3D 编辑，” 收录于 *IEEE/CVF 国际计算机视觉会议 (ICCV)*，2023 年 10 月，第 14 607–14 619 页。

+   [360] J. Zhuang, C. Wang, L. Lin, L. Liu, 和 G. Li, “Dreameditor: 基于文本的 3D 场景编辑与神经场，” 收录于 *SIGGRAPH Asia 2023 会议论文集*，2023 年，第 1–10 页。

+   [361] A. Haque, M. Tancik, A. A. Efros, A. Holynski, 和 A. Kanazawa, “Instruct-nerf2nerf: 使用指令编辑 3D 场景，” *arXiv 预印本 arXiv:2303.12789*，2023 年。

+   [362] D. Decatur, I. Lang, K. Aberman, 和 R. Hanocka, “3D 画笔: 使用级联评分蒸馏进行 3D 形状的局部风格化，” *arXiv 预印本 arXiv:2311.09571*，2023 年。

+   [363] G. Tevet, S. Raab, B. Gordon, Y. Shafir, D. Cohen-or, 和 A. H. Bermano, “人体运动扩散模型，” 发表在 *第十一届国际学习表示会议*，2023\. [在线]. 可用: [`openreview.net/forum?id=SJ1kSyO2jwu`](https://openreview.net/forum?id=SJ1kSyO2jwu)

+   [364] R. Chen, Y. Chen, N. Jiao, 和 K. Jia, “Fantasia3d: 解开几何和外观的纠缠以实现高质量的文本到 3d 内容创建，” *arXiv 预印本 arXiv:2303.13873*, 2023。

+   [365] Z. Pan, J. Lu, X. Zhu, 和 L. Zhang, “通过逐像素梯度裁剪增强高分辨率 3d 生成，” 发表在 *国际学习表示会议 (ICLR)*，2024。

+   [366] G. Qian, J. Cao, A. Siarohin, Y. Kant, C. Wang, M. Vasilkovsky, H.-Y. Lee, Y. Fang, I. Skorokhodov, P. Zhuang *等*, “Atom: 使用 2d 扩散的摊销文本到网格，” *arXiv 预印本 arXiv:2402.00867*, 2024。

+   [367] Z. Wu, P. Zhou, X. Yi, X. Yuan, 和 H. Zhang, “Consistent3d: 朝着一致的高保真文本到 3d 生成迈进，使用确定性采样先验，” *arXiv 预印本 arXiv:2401.09050*, 2024。

+   [368] T. Huang, Y. Zeng, Z. Zhang, W. Xu, H. Xu, S. Xu, R. W. Lau, 和 W. Zuo, “Dreamcontrol: 基于控制的文本到 3d 生成与 3d 自先验，” *arXiv 预印本 arXiv:2312.06439*, 2023。

+   [369] Y. Chen, C. Zhang, X. Yang, Z. Cai, G. Yu, L. Yang, 和 G. Lin, “It3d: 通过显式视图合成改进文本到 3d 生成，” 2023。

+   [370] M. Zhao, C. Zhao, X. Liang, L. Li, Z. Zhao, Z. Hu, C. Fan, 和 X. Yu, “Efficientdreamer: 通过正交视图扩散先验实现高保真和鲁棒的 3d 创建，” *arXiv 预印本 arXiv:2308.13223*, 2023。

+   [371] Z. Chen, F. Wang, 和 H. Liu, “使用高斯溅射进行文本到 3d 转换，” *arXiv 预印本 arXiv:2309.16585*, 2023。

+   [372] Y. Ma, Y. Fan, J. Ji, H. Wang, X. Sun, G. Jiang, A. Shu, 和 R. Ji, “X-dreamer: 通过弥合文本到 2d 和文本到 3d 生成之间的领域差距来创建高质量的 3d 内容，” *arXiv 预印本 arXiv:2312.00085*, 2023。

+   [373] J. Wu, X. Gao, X. Liu, Z. Shen, C. Zhao, H. Feng, J. Liu, 和 E. Ding, “Hd-fusion: 通过利用多种噪声估计进行详细的文本到 3d 生成，” 发表在 *IEEE/CVF 计算机视觉应用冬季会议论文集*，2024 年，第 3202–3211 页。

+   [374] X. Yang, Y. Chen, C. Chen, C. Zhang, Y. Xu, X. Yang, F. Liu, 和 G. Lin, “学习优化去噪评分以生成 3d：在 nerf 和 3d 高斯溅射上的统一且改进的扩散先验，” *arXiv 预印本 arXiv:2312.04820*, 2023。

+   [375] F. Liu, D. Wu, Y. Wei, Y. Rao, 和 Y. Duan, “Sherpa3d: 通过粗略 3d 先验提升高保真文本到 3d 生成，” 2023。

+   [376] Y. Lin, R. Clark, 和 P. Torr, “Dreampolisher: 通过几何扩散朝着高质量文本到 3d 生成迈进，” *arXiv 预印本 arXiv:2403.17237*, 2024。

+   [377] Y. Yang, F.-Y. Sun, L. Weihs, E. VanderBilt, A. Herrasti, W. Han, J. Wu, N. Haber, R. Krishna, L. Liu, C. Callison-Burch, M. Yatskar, A. Kembhavi, 和 C. Clark, “Holodeck: 语言引导的 3D 具身 AI 环境生成，” *arXiv 预印本 arXiv:2312.09067*，2023 年。

+   [378] H. Song, S. Choi, H. Do, C. Lee, 和 T. Kim, “Blending-nerf: 基于文本驱动的神经辐射场局部编辑，” 见 *IEEE/CVF 国际计算机视觉会议论文集*，2023 年，第 14 383–14 393 页。

+   [379] R. He, S. Huang, X. Nie, T. Hui, L. Liu, J. Dai, J. Han, G. Li, 和 S. Liu, “定制你的 nerf: 通过局部-全局迭代训练进行适应性源驱动的 3D 场景编辑，” *arXiv 预印本 arXiv:2312.01663*，2023 年。

+   [380] X. Zeng, X. Chen, Z. Qi, W. Liu, Z. Zhao, Z. Wang, B. FU, Y. Liu, 和 G. Yu, “Paint3d: 用于照明缺失纹理扩散模型的 3D 涂画，” 2023 年。

+   [381] E. Law, K. West, M. I. Mandel, M. Bay, 和 J. S. Downie, “使用游戏评估算法：以音乐标签为例。” 见 *ISMIR*。Citeseer，2009 年，第 387–392 页。

+   [382] V. Panayotov, G. Chen, D. Povey, 和 S. Khudanpur, “Librispeech: 基于公共领域有声读物的自动语音识别语料库，” 见 *2015 IEEE 国际声学、语音与信号处理会议（ICASSP）*。IEEE，2015 年，第 5206–5210 页。

+   [383] J. F. Gemmeke, D. P. Ellis, D. Freedman, A. Jansen, W. Lawrence, R. C. Moore, M. Plakal, 和 M. Ritter, “Audio set: 用于音频事件的本体和人工标注数据集，” 见 *2017 IEEE 国际声学、语音与信号处理会议（ICASSP）*。IEEE，2017 年，第 776–780 页。

+   [384] C. Hawthorne, A. Stasyuk, A. Roberts, I. Simon, C.-Z. A. Huang, S. Dieleman, E. Elsen, J. Engel, 和 D. Eck, “通过 maestro 数据集实现分解的钢琴音乐建模与生成，” *arXiv 预印本 arXiv:1810.12247*，2018 年。

+   [385] H. Zen, V. Dang, R. Clark, Y. Zhang, R. J. Weiss, Y. Jia, Z. Chen, 和 Y. Wu, “Libritts: 从 librispeech 衍生的文本到语音语料库，” *arXiv 预印本 arXiv:1904.02882*，2019 年。

+   [386] D. Bogdanov, M. Won, P. Tovstogan, A. Porter, 和 X. Serra, “用于自动音乐标签的 mtg-jamendo 数据集。” ICML，2019 年。

+   [387] J. Kahn, M. Riviere, W. Zheng, E. Kharitonov, Q. Xu, P.-E. Mazaré, J. Karadayi, V. Liptchinsky, R. Collobert, C. Fuegen *等*， “Libri-light: 有限或无监督下的自动语音识别基准，” 见 *ICASSP 2020-2020 IEEE 国际声学、语音与信号处理会议（ICASSP）*。IEEE，2020 年，第 7669–7673 页。

+   [388] H. Chen, W. Xie, A. Vedaldi, 和 A. Zisserman, “Vggsound: 大规模音视频数据集，” 见 *ICASSP 2020-2020 IEEE 国际声学、语音与信号处理会议（ICASSP）*。IEEE，2020 年，第 721–725 页。

+   [389] B. Zhang, H. Lv, P. Guo, Q. Shao, C. Yang, L. Xie, X. Xu, H. Bu, X. Chen, C. Zeng *等*，“Wenetspeech：一个 10000+ 小时多领域普通话语音识别语料库”，在 *ICASSP 2022-2022 IEEE 国际声学、语音与信号处理会议（ICASSP）*，IEEE，2022 年，页码 6182–6186。

+   [390] W. Kang, X. Yang, Z. Yao, F. Kuang, Y. Yang, L. Guo, L. Lin, 和 D. Povey，“Libriheavy：一个包含标点符号大小写和上下文的 50,000 小时 ASR 语料库”，在 *ICASSP 2024-2024 IEEE 国际声学、语音与信号处理会议（ICASSP）*，IEEE，2024 年，页码 10 991–10 995。

+   [391] J. Zhan, J. Dai, J. Ye, Y. Zhou, D. Zhang, Z. Liu, X. Zhang, R. Yuan, G. Zhang, L. Li *等*，“Anygpt：具有离散序列建模的统一多模态 LLM”，*arXiv 预印本 arXiv:2402.12226*，2024 年。

+   [392] H. Hao, L. Zhou, S. Liu, J. Li, S. Hu, R. Wang, 和 F. Wei，“提升大语言模型的语音合成：一项实证研究”，*arXiv 预印本 arXiv:2401.00246*，2023 年。

+   [393] J. Lu, C. Clark, S. Lee, Z. Zhang, S. Khosla, R. Marten, D. Hoiem, 和 A. Kembhavi，“Unified-io 2：扩展自回归多模态模型，涵盖视觉、语言、音频和动作”，*arXiv 预印本 arXiv:2312.17172*，2023 年。

+   [394] S. Bubeck, V. Chandrasekaran, R. Eldan, J. Gehrke, E. Horvitz, E. Kamar, P. Lee, Y. T. Lee, Y. Li, S. Lundberg *等*，“人工通用智能的火花：与 GPT-4 的早期实验”，*arXiv 预印本 arXiv:2303.12712*，2023 年。

+   [395] J. Wu, Y. Gaur, Z. Chen, L. Zhou, Y. Zhu, T. Wang, J. Li, S. Liu, B. Ren, L. Liu *等*，“解码器唯一架构在语音到文本和大语言模型集成中的应用”，在 *2023 IEEE 自动语音识别与理解研讨会（ASRU）*，IEEE，2023 年，页码 1–8。

+   [396] W. Yu, C. Tang, G. Sun, X. Chen, T. Tan, W. Li, L. Lu, Z. Ma, 和 C. Zhang，“将语音编码器与大语言模型连接用于自动语音识别”，*arXiv 预印本 arXiv:2309.13963*，2023 年。

+   [397] S. Wang, C.-H. H. Yang, J. Wu, 和 C. Zhang，“Whisper 是否能够进行基于语音的上下文学习”，*arXiv 预印本 arXiv:2309.07081*，2023 年。

+   [398] Q. Deng, Q. Yang, R. Yuan, Y. Huang, Y. Wang, X. Liu, Z. Tian, J. Pan, G. Zhang, H. Lin *等*，“Composerx：多代理符号音乐创作与 LLMs”，*arXiv 预印本 arXiv:2404.18081*，2024 年。

+   [399] Y. Gong, Y.-A. Chung, 和 J. Glass，“AST：音频频谱转换器”，*arXiv 预印本 arXiv:2104.01778*，2021 年。

+   [400] H. W. Chung, L. Hou, S. Longpre, B. Zoph, Y. Tay, W. Fedus, Y. Li, X. Wang, M. Dehghani, S. Brahma *等*，“扩展指令微调语言模型”，*arXiv 预印本 arXiv:2210.11416*，2022 年。

+   [401] J. Rothstein，*MIDI：全面介绍*，AR Editions, Inc.，1995 年，第 7 卷。

+   [402] R. Anil, A. M. Dai, O. Firat, M. Johnson, D. Lepikhin, A. Passos, S. Shakeri, E. Taropa, P. Bailey, Z. Chen *等*，“Palm 2 技术报告”，*arXiv 预印本 arXiv:2305.10403*，2023 年。

+   [403] A. Radford, J. W. Kim, T. Xu, G. Brockman, C. McLeavey, 和 I. Sutskever，“通过大规模弱监督进行鲁棒语音识别，” 在 *国际机器学习会议*。PMLR, 2023 年，第 28 492–28 518 页。

+   [404] S. Kakouros, J. Šimko, M. Vainio, 和 A. Suni，“研究大语言模型对语音合成韵律的惊讶效用，” *arXiv 预印本 arXiv:2306.09814*，2023 年。

+   [405] Y. Gong, A. Rouditchenko, A. H. Liu, D. Harwath, L. Karlinsky, H. Kuehne, 和 J. Glass，“对比音频-视觉掩蔽自编码器，” *arXiv 预印本 arXiv:2210.07839*，2022 年。

+   [406] Z. Deng, Y. Ma, Y. Liu, R. Guo, G. Zhang, W. Chen, W. Huang, 和 E. Benetos，“Musilingo: 利用预训练语言模型进行音乐标注和查询响应，” *arXiv 预印本 arXiv:2309.08730*，2023 年。

+   [407] Y. Li, R. Yuan, G. Zhang, Y. Ma, X. Chen, H. Yin, C. Lin, A. Ragni, E. Benetos, N. Gyenge *等*，“Mert: 具有大规模自监督训练的声学音乐理解模型，” *arXiv 预印本 arXiv:2306.00107*，2023 年。

+   [408] A. Défossez, J. Copet, G. Synnaeve, 和 Y. Adi，“高保真神经音频压缩，” *arXiv 预印本 arXiv:2210.13438*，2022 年。

+   [409] R. Kumar, P. Seetharaman, A. Luebs, I. Kumar, 和 K. Kumar，“高保真音频压缩与改进的 rvqgan，” *神经信息处理系统进展*，第 36 卷，2024 年。

+   [410] J. Deng, W. Dong, R. Socher, L.-J. Li, K. Li, 和 L. Fei-Fei，“Imagenet: 大规模分层图像数据库，” 在 *2009 IEEE 计算机视觉与模式识别会议*。Ieee, 2009 年，第 248–255 页。

+   [411] Y. Wang, Y. Kordi, S. Mishra, A. Liu, N. A. Smith, D. Khashabi, 和 H. Hajishirzi，“Self-instruct: 使语言模型与自生成指令对齐，” *arXiv 预印本 arXiv:2212.10560*，2022 年。

+   [412] Y. Qin, S. Liang, Y. Ye, K. Zhu, L. Yan, Y. Lu, Y. Lin, X. Cong, X. Tang, B. Qian *等*，“Toolllm: 促进大型语言模型掌握 16000+ 现实世界 API，” *arXiv 预印本 arXiv:2307.16789*，2023 年。

+   [413] Q. Tang, Z. Deng, H. Lin, X. Han, Q. Liang, 和 L. Sun，“Toolalpaca: 针对语言模型的 3000 个模拟案例的通用工具学习，” *arXiv 预印本 arXiv:2306.05301*，2023 年。

+   [414] T. Schick, J. Dwivedi-Yu, R. Dessì, R. Raileanu, M. Lomeli, L. Zettlemoyer, N. Cancedda, 和 T. Scialom，“Toolformer: 语言模型可以自我学习使用工具，” *arXiv 预印本 arXiv:2302.04761*，2023 年。

+   [415] N. Farn 和 R. Shin，“Tooltalk: 评估对话设置中的工具使用情况，” *arXiv 预印本 arXiv:2311.10775*，2023 年。

+   [416] S. Hao, T. Liu, Z. Wang, 和 Z. Hu，“Toolkengpt: 通过工具嵌入增强冻结语言模型的能力，” *arXiv 预印本 arXiv:2305.11554*，2023 年。

+   [417] C.-Y. Hsieh, S.-A. Chen, C.-L. Li, Y. Fujii, A. Ratner, C.-Y. Lee, R. Krishna, 和 T. Pfister，“工具文档使大型语言模型能够零-shot 工具使用，” *arXiv 预印本 arXiv:2308.00675*，2023 年。

+   [418] J. Ruan, Y. Chen, B. Zhang, Z. Xu, T. Bao, G. Du, S. Shi, H. Mao, X. Zeng 和 R. Zhao, “Tptu: 基于大语言模型的任务规划与工具使用，” *arXiv 预印本 arXiv:2308.03427*，2023 年。

+   [419] A. Parisi, Y. Zhao 和 N. Fiedel, “Talm: 工具增强语言模型，” *arXiv 预印本 arXiv:2205.12255*，2022 年。

+   [420] J. Zhang, “Graph-toolformer: 通过 ChatGPT 增强图形推理能力的 LLMs，” *arXiv 预印本 arXiv:2304.11116*，2023 年。

+   [421] Y. Zhuang, X. Chen, T. Yu, S. Mitra, V. Bursztyn, R. A. Rossi, S. Sarkhel 和 C. Zhang, “Toolchain*: 使用 a*搜索在大型语言模型中高效导航行动空间，” *arXiv 预印本 arXiv:2310.13227*，2023 年。

+   [422] Z. Gou, Z. Shao, Y. Gong, Y. Shen, Y. Yang, N. Duan 和 W. Chen, “Critic: 大型语言模型可以通过工具互动批评进行自我纠正，” *arXiv 预印本 arXiv:2305.11738*，2023 年。

+   [423] Q. Jin, Y. Yang, Q. Chen 和 Z. Lu, “Genegpt: 用领域工具增强大型语言模型以改善对生物医学信息的访问，” *ArXiv*，2023 年。

+   [424] B. Paranjape, S. Lundberg, S. Singh, H. Hajishirzi, L. Zettlemoyer 和 M. T. Ribeiro, “Art: 自动化多步骤推理和工具使用的语言模型，” *arXiv 预印本 arXiv:2303.09014*，2023 年。

+   [425] Z. Gou, Z. Shao, Y. Gong, Y. Yang, M. Huang, N. Duan, W. Chen *等*，“Tora: 一个用于数学问题解决的工具集成推理代理，” *arXiv 预印本 arXiv:2309.17452*，2023 年。

+   [426] Y. Song, W. Xiong, D. Zhu, C. Li, K. Wang, Y. Tian 和 S. Li, “Restgpt: 通过 RESTful API 将大型语言模型与现实世界应用连接起来，” *arXiv 预印本 arXiv:2306.06624*，2023 年。

+   [427] S. Qiao, H. Gui, H. Chen 和 N. Zhang, “通过执行反馈提升语言模型的工具学习能力，” *arXiv 预印本 arXiv:2305.13068*，2023 年。

+   [428] K. Zhang, H. Chen, L. Li 和 W. Wang, “通过有限状态解码实现 LLMs 的无语法错误和可泛化工具使用，” *arXiv 预印本 arXiv:2310.07075*，2023 年。

+   [429] W. Shen, C. Li, H. Chen, M. Yan, X. Quan, H. Chen, J. Zhang 和 F. Huang, “小型 LLMs 是弱工具学习者：一个多 LLM 代理，” *arXiv 预印本 arXiv:2401.07324*，2024 年。

+   [430] J. Wang, H. Xu, J. Ye, M. Yan, W. Shen, J. Zhang, F. Huang 和 J. Sang, “Mobile-agent: 具有视觉感知的自主多模态移动设备代理，” *arXiv 预印本 arXiv:2401.16158*，2024 年。

+   [431] T. Gupta 和 A. Kembhavi, “视觉编程：无需训练的组合视觉推理，”发表于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 14 953–14 962 页。

+   [432] C. Wang, W. Luo, Q. Chen, H. Mai, J. Guo, S. Dong, X. M. Xuan, Z. Li, L. Ma 和 S. Gao, “Mllm-tool: 一个用于工具代理学习的多模态大型语言模型，” *arXiv 预印本 arXiv:2401.10727*，2024 年。

+   [433] D. Surís, S. Menon 和 C. Vondrick，“Vipergpt: 通过 Python 执行的视觉推理，” *IEEE 国际计算机视觉大会 (ICCV) 论文集*，2023。

+   [434] Z. Gao, Y. Du, X. Zhang, X. Ma, W. Han, S.-C. Zhu 和 Q. Li，“Clova: 一个具有工具使用和更新的闭环视觉助手，” *arXiv 预印本 arXiv:2312.10908*，2023。

+   [435] S. Yao, J. Zhao, D. Yu, N. Du, I. Shafran, K. Narasimhan 和 Y. Cao，“ReAct: 在语言模型中协同推理和行动，” 载于 *国际学习表示大会 (ICLR)*，2023。

+   [436] J. Wei, X. Wang, D. Schuurmans, M. Bosma, F. Xia, E. Chi, Q. V. Le, D. Zhou *等*，“Chain-of-thought 提示激发大语言模型的推理，” *神经信息处理系统进展*，第 35 卷，第 24 824–24 837 页，2022。

+   [437] A. Kirillov, E. Mintun, N. Ravi, H. Mao, C. Rolland, L. Gustafson, T. Xiao, S. Whitehead, A. C. Berg, W.-Y. Lo *等*，“Segment anything，” *arXiv 预印本 arXiv:2304.02643*，2023。

+   [438] S. Zhang, S. Roller, N. Goyal, M. Artetxe, M. Chen, S. Chen, C. Dewan, M. Diab, X. Li, X. V. Lin, T. Mihaylov, M. Ott, S. Shleifer, K. Shuster, D. Simig, P. S. Koura, A. Sridhar, T. Wang 和 L. Zettlemoyer，“Opt: 开放预训练变换器语言模型，” 2022。

+   [439] T. Dettmers, A. Pagnoni, A. Holtzman 和 L. Zettlemoyer，“Qlora: 高效微调量化 LLMs，” *arXiv 预印本 arXiv:2305.14314*，2023。

+   [440] S. Mangrulkar, S. Gugger, L. Debut, Y. Belkada, S. Paul 和 B. Bossan，“Peft: 最先进的参数高效微调方法，” [`github.com/huggingface/peft`](https://github.com/huggingface/peft)，2022。

+   [441] J. Chen, X. Li, X. Ye, C. Li, Z. Fan 和 H. Zhao，“Idea-2-3d: 协作 LMM 代理使得从交错的多模态输入生成 3D 模型，” *arXiv 预印本 arXiv:2404.04363*，2024。

+   [442] E. Wallace, S. Feng, N. Kandpal, M. Gardner 和 S. Singh，“针对 NLP 的通用对抗触发器，” *arXiv 预印本 arXiv:1908.07125*，2019。

+   [443] X. Fu, Z. Wang, S. Li, R. K. Gupta, N. Mireshghallah, T. Berg-Kirkpatrick 和 E. Fernandes，“利用视觉对抗样本滥用大语言模型中的工具，” *arXiv 预印本 arXiv:2310.03185*，2023。

+   [444] L. Bailey, E. Ong, S. Russell 和 S. Emmons，“图像劫持：对抗性图像可以在运行时控制生成模型，” *arXiv 预印本 arXiv:2309.00236*，2023。

+   [445] A. Zou, Z. Wang, J. Z. Kolter 和 M. Fredrikson，“对齐语言模型的通用和可转移对抗攻击，” *arXiv 预印本 arXiv:2307.15043*，2023。

+   [446] E. Jones, A. Dragan, A. Raghunathan 和 J. Steinhardt，“通过离散优化自动审计大语言模型，” 载于 *国际机器学习大会*。   PMLR，2023，第 15 307–15 329 页。

+   [447] P. Żelasko、S. Joshi、Y. Shao、J. Villalba、J. Trmal、N. Dehak 和 S. Khudanpur，“语音识别系统的对抗攻击与防御，” *arXiv 预印本 arXiv:2103.17122*，2021 年。

+   [448] Z. Chen、L. Xie、S. Pang、Y. He 和 Q. Tian，“附加对抗帧以进行通用视频攻击，” 见 *IEEE/CVF 冬季计算机视觉应用会议论文集*，2021 年，页码 3199–3208。

+   [449] H. Liu、W. Zhou、D. Chen、H. Fang、H. Bian、K. Liu、W. Zhang 和 N. Yu，“一致的对抗深伪视频生成，” *信号处理*，第 203 卷，页码 108790，2023 年。

+   [450] S.-Y. Lo 和 V. M. Patel，“防御多重和未预见的对抗视频，” *IEEE 图像处理学报*，第 31 卷，页码 962–973，2021 年。

+   [451] H. J. Lee 和 Y. M. Ro，“通过防御模式防御视频识别模型免受对抗扰动，” *IEEE 可靠与安全计算学报*，2023 年。

+   [452] Y. Wu、X. Li、Y. Liu、P. Zhou 和 L. Sun，“通过系统提示进行自我对抗攻击以越狱 gpt-4v，” *arXiv 预印本 arXiv:2311.09127*，2023 年。

+   [453] Y. Xie、J. Yi、J. Shao、J. Curl、L. Lyu、Q. Chen、X. Xie 和 F. Wu，“通过自我提醒防御 ChatGPT 免受越狱攻击，” *自然机器智能*，第 5 卷，第 12 期，页码 1486–1496，2023 年。

+   [454] Y. Liu、G. Deng、Y. Li、K. Wang、T. Zhang、Y. Liu、H. Wang、Y. Zheng 和 Y. Liu，“针对 llm 集成应用的提示注入攻击，” *arXiv 预印本 arXiv:2306.05499*，2023 年。

+   [455] F. Perez 和 I. Ribeiro，“忽略先前提示：语言模型的攻击技术，” *arXiv 预印本 arXiv:2211.09527*，2022 年。

+   [456] N. Carlini、M. Jagielski、C. A. Choquette-Choo、D. Paleka、W. Pearce、H. Anderson、A. Terzis、K. Thomas 和 F. Tramèr，“对网络规模训练数据集进行毒化是切实可行的，” *arXiv 预印本 arXiv:2302.10149*，2023 年。

+   [457] R. Jia 和 P. Liang，“用于评估阅读理解系统的对抗样本，” *arXiv 预印本 arXiv:1707.07328*，2017 年。

+   [458] M.-H. Van 和 X. Wu，“使用大型视觉语言模型检测和纠正多模态表情中的仇恨言论，” *arXiv 预印本 arXiv:2311.06737*，2023 年。

+   [459] Z. Wei、Y. Wang 和 Y. Wang，“用少量上下文示例对齐语言模型的越狱与防护，” *arXiv 预印本 arXiv:2310.06387*，2023 年。

+   [460] A. Robey、E. Wong、H. Hassani 和 G. J. Pappas，“Smoothllm：防御大规模语言模型免受越狱攻击，” *arXiv 预印本 arXiv:2310.03684*，2023 年。

+   [461] R. Liu、A. Khakzar、J. Gu、Q. Chen、P. Torr 和 F. Pizzati，“潜在保护：一种用于文本到图像生成的安全框架，” *arXiv 预印本 arXiv:2404.08031*，2024 年。

+   [462] J. Schulman、F. Wolski、P. Dhariwal、A. Radford 和 O. Klimov，“邻近策略优化算法，” *arXiv 预印本 arXiv:1707.06347*，2017 年。

+   [463] R. Rafailov, A. Sharma, E. Mitchell, C. D. Manning, S. Ermon, 和 C. Finn，“直接偏好优化：你的语言模型秘密地是一个奖励模型”，*神经信息处理系统进展*，第 36 卷，2024 年。

+   [464] R. Pi, T. Han, W. Xiong, J. Zhang, R. Liu, R. Pan, 和 T. Zhang，“通过引导偏好优化增强多模态大型语言模型”，*arXiv 预印本 arXiv:2403.08730*，2024 年。

+   [465] X. Wu, K. Sun, F. Zhu, R. Zhao, 和 H. Li，“更好地将文本到图像模型与人类偏好对齐”，*arXiv 预印本 arXiv:2303.14420*，2023 年。

+   [466] H. Dong, W. Xiong, D. Goyal, R. Pan, S. Diao, J. Zhang, K. Shum, 和 T. Zhang，“Raft：用于生成基础模型对齐的奖励排名微调”，*arXiv 预印本 arXiv:2304.06767*，2023 年。

+   [467] P. Korshunov 和 S. Marcel，“深伪：对面部识别的新威胁？评估与检测”，*arXiv 预印本 arXiv:1812.08685*，2018 年。

+   [468] Y. Mirsky 和 W. Lee，“深伪的创建与检测：综述”，*ACM 计算机调查 (CSUR)*，第 54 卷，第 1 期，第 1–41 页，2021 年。

+   [469] M. Masood, M. Nawaz, K. M. Malik, A. Javed, A. Irtaza, 和 H. Malik，“深伪生成与检测：最前沿、开放挑战、对策及未来方向”，*应用智能*，第 53 卷，第 4 期，第 3974–4026 页，2023 年。

+   [470] L. Verdoliva，“媒体取证与深伪：概述”，*IEEE 选定信号处理期刊*，第 14 卷，第 5 期，第 910–932 页，2020 年。

+   [471] D. Wodajo, S. Atnafu, 和 Z. Akhtar，“使用生成卷积视觉变换器进行深伪视频检测”，*arXiv 预印本 arXiv:2307.07036*，2023 年。

+   [472] D. Wodajo 和 S. Atnafu，“使用卷积视觉变换器进行深伪视频检测”，*arXiv 预印本 arXiv:2102.11126*，2021 年。

+   [473] S. Hussain, P. Neekhara, M. Jere, F. Koushanfar, 和 J. McAuley，“对抗性深伪：评估深伪检测器对对抗性样本的脆弱性”，发表于*IEEE/CVF 冬季计算机视觉应用会议论文集*，2021 年，第 3348–3357 页。

+   [474] W. Shi, A. Ajith, M. Xia, Y. Huang, D. Liu, T. Blevins, D. Chen, 和 L. Zettlemoyer，“检测大型语言模型中的预训练数据”，*arXiv 预印本 arXiv:2310.16789*，2023 年。

+   [475] S. M. Park, K. Georgiev, A. Ilyas, G. Leclerc, 和 A. Madry，“Trak：大规模归因模型行为”，*arXiv 预印本 arXiv:2303.14186*，2023 年。

+   [476] Z. Wang, C. Chen, Y. Zeng, L. Lyu, 和 S. Ma，“我来自哪里？AI 生成图像的起源归属”，*神经信息处理系统进展*，第 36 卷，2024 年。

+   [477] J. Kirchenbauer, J. Geiping, Y. Wen, J. Katz, I. Miers, 和 T. Goldstein，“大型语言模型的水印”，发表于*国际机器学习会议*，PMLR，2023 年，第 17 061–17 084 页。

+   [478] Y. Cui, J. Ren, H. Xu, P. He, H. Liu, L. Sun, 和 J. Tang，“Diffusionshield：一种针对生成扩散模型的版权保护水印”，*arXiv 预印本 arXiv:2306.04642*，2023 年。

+   [479] P. Fernandez, G. Couairon, H. Jégou, M. Douze, 和 T. Furon, “稳定签名: 根植于潜在扩散模型中的水印,” 见 *IEEE/CVF 国际计算机视觉会议论文集*, 2023, 页 22 466–22 477。

+   [480] Z. Zhang, L. Lei, L. Wu, R. Sun, Y. Huang, C. Long, X. Liu, X. Lei, J. Tang, 和 M. Huang, “Safetybench: 使用多项选择题评估大型语言模型的安全性,” *arXiv 预印本 arXiv:2309.07045*, 2023。

+   [481] H. Lin, Z. Luo, B. Wang, R. Yang, 和 J. Ma, “Goat-bench: 通过基于表情包的社会滥用获取对大型多模态模型的安全见解,” *arXiv 预印本 arXiv:2401.01523*, 2024。

+   [482] X. Wang, X. Yi, H. Jiang, S. Zhou, Z. Wei, 和 X. Xie, “Tovilag: 你的视觉语言生成模型也是恶棍,” *arXiv 预印本 arXiv:2312.11523*, 2023。

+   [483] Y. Gong, D. Ran, J. Liu, C. Wang, T. Cong, A. Wang, S. Duan, 和 X. Wang, “Figstep: 通过印刷视觉提示破解大型视觉语言模型,” *arXiv 预印本 arXiv:2311.05608*, 2023。

+   [484] X. Liu, Y. Zhu, Y. Lan, C. Yang, 和 Y. Qiao, “与查询相关的图像破解大型多模态模型,” *arXiv 预印本 arXiv:2311.17600*, 2023。

+   [485] “midjourney,” [`www.midjourney.com/home`](https://www.midjourney.com/home)。

+   [486] “Stability ai,” [`stability.ai/`](https://stability.ai/)。

+   [487] “Gpt-4,” [`openai.com/gpt-4`](https://openai.com/gpt-4)。

+   [488] “Dalle-2,” [`openai.com/dall-e-2`](https://openai.com/dall-e-2)。

+   [489] “Openai,” [`openai.com`](https://openai.com)。

+   [490] “Pika labs,” [`www.pika.art/`](https://www.pika.art/)。

+   [491] “Gen2,” [`research.runwayml.com/gen2`](https://research.runwayml.com/gen2)。

+   [492] “heygen,” [`app.heygen.com/home`](https://app.heygen.com/home)。

+   [493] “Azure ai-services: 文本转语音,” [`azure.microsoft.com/zh-cn/products/ai-services/text-to-speech`](https://azure.microsoft.com/zh-cn/products/ai-services/text-to-speech)。

+   [494] “descript,” [`www.descript.com/`](https://www.descript.com/)。

+   [495] “Suno ai,” [`suno-ai.org/`](https://suno-ai.org/)。

+   [496] “Stability ai: Stable audio,” [`stability.ai/stable-audio`](https://stability.ai/stable-audio)。

+   [497] “Musicfx,” [`aitestkitchen.withgoogle.com/tools/music-fx`](https://aitestkitchen.withgoogle.com/tools/music-fx)。

+   [498] “tuneflow,” [`www.tuneflow.com/`](https://www.tuneflow.com/)。

+   [499] “deepmusic,” [`www.deepmusic.fun/`](https://www.deepmusic.fun/)。

+   [500] “meta,” [`about.meta.com/`](https://about.meta.com/)。

+   [501] “Epic games’ metahuman creator,” [`www.unrealengine.com/en-US/metahuman`](https://www.unrealengine.com/en-US/metahuman)。

+   [502] “Luma ai,” [`lumalabs.ai/`](https://lumalabs.ai/)。

+   [503] “Adobe,” [`www.adobe.com/`](https://www.adobe.com/)。

+   [504] “Kaedim3d,” [`www.kaedim3d.com/`](https://www.kaedim3d.com/)。

+   [505] “Wonder studio,” [`wonderdynamics.com/`](https://wonderdynamics.com/)。

+   [506] A. Avetisyan, C. Xie, H. Howard-Jenkins, T.-Y. Yang, S. Aroudj, S. Patra, F. Zhang, D. Frost, L. Holland, C. Orme, J. Engel, E. Miller, R. Newcombe, 和 V. Balntas，“Scenescript: 使用自回归结构化语言模型重建场景，” 2024 年。

+   [507] “谷歌，” [`www.google.com/`](https://www.google.com/)。

+   [508] “腾讯，” [`www.tencent.com/`](https://www.tencent.com/)。

+   [509] Y. He, S. Yang, H. Chen, X. Cun, M. Xia, Y. Zhang, X. Wang, R. He, Q. Chen, 和 Y. Shan，“Scalecrafter: 无需调整的更高分辨率视觉生成与扩散模型，” 见于 *第十二届国际学习表征会议*，2023 年。

+   [510] L. Guo, Y. He, H. Chen, M. Xia, X. Cun, Y. Wang, S. Huang, Y. Zhang, X. Wang, Q. Chen *等*，“Make a cheap scaling: 一种自级联扩散模型用于更高分辨率适配，” *arXiv 预印本 arXiv:2402.10491*，2024 年。

+   [511] Y. Xu, T. Park, R. Zhang, Y. Zhou, E. Shechtman, F. Liu, J.-B. Huang, 和 D. Liu，“Videogigagan: 朝向细节丰富的视频超分辨率，” *arXiv 预印本 arXiv:2404.12388*，2024 年。

+   [512] S. Zhou, P. Yang, J. Wang, Y. Luo, 和 C. C. Loy，“Upscale-a-video: 真实世界视频超分辨率的时间一致性扩散模型，” *arXiv 预印本 arXiv:2312.06640*，2023 年。

+   [513] R. S. Roman, Y. Adi, A. Deleforge, R. Serizel, G. Synnaeve, 和 A. Défossez，“从离散标记到高保真音频的多频带扩散，” *arXiv 预印本 arXiv:2308.02560*，2023 年。

+   [514] Y. Yao, P. Li, B. Chen, 和 A. Wang，“Jen-1 composer: 高保真多轨音乐生成的统一框架，” *arXiv 预印本 arXiv:2310.19180*，2023 年。

+   [515] M. Ding, W. Zheng, W. Hong, 和 J. Tang，“Cogview2: 通过层次化变换器实现更快更好的文本到图像生成，” *神经信息处理系统进展*，第 35 卷，第 16 890–16 902 页，2022 年。

+   [516] Y. Zhang, Y. Wei, X. Lin, Z. Hui, P. Ren, X. Xie, X. Ji, 和 W. Zuo，“Videoelevator: 利用多功能文本到图像扩散模型提升视频生成质量，” *arXiv 预印本 arXiv:2403.05438*，2024 年。

+   [517] R. Henschel, L. Khachatryan, D. Hayrapetyan, H. Poghosyan, V. Tadevosyan, Z. Wang, S. Navasardyan, 和 H. Shi，“Streamingt2v: 从文本生成一致、动态且可扩展的长视频，” *arXiv 预印本 arXiv:2403.14773*，2024 年。

+   [518] R. Or-El, X. Luo, M. Shan, E. Shechtman, J. J. Park, 和 I. Kemelmacher-Shlizerman，“Stylesdf: 高分辨率的 3D 一致性图像和几何生成，” 见于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2022 年，第 13 503–13 513 页。

+   [519] X. Huang, W. Li, J. Hu, H. Chen, 和 Y. Wang，“Refsr-nerf: 朝向高保真度和超分辨率视图合成，” 见于 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023 年，第 8244–8253 页。

+   [520] F.-Y. Wang, W. Chen, G. Song, H.-J. Ye, Y. Liu, 和 H. Li, “Gen-l-video：通过时间联合去噪生成多文本到长视频”，*arXiv 预印本 arXiv:2305.18264*，2023。

+   [521] J. Yoo, S. Kim, D. Lee, C. Kim, 和 S. Hong, “迈向具有内存高效双向变换器的长视频生成建模”，在 *IEEE/CVF 计算机视觉与模式识别会议论文集*，2023，第 22,888–22,897 页。

+   [522] L. Lin, G. Xia, Y. Zhang, 和 J. Jiang, “安排、修补和完善：通过基于内容的控制进行可控的长期音乐音频生成和编辑”，2024。

+   [523] L. Zhang, A. Rao, 和 M. Agrawala, “向文本到图像扩散模型添加条件控制”，在 *IEEE/CVF 国际计算机视觉大会论文集*，2023，第 3836–3847 页。

+   [524] M. Zhao, R. Wang, F. Bao, C. Li, 和 J. Zhu, “Controlvideo：为一次性文本到视频编辑添加条件控制”，*arXiv 预印本 arXiv:2305.17098*，2023。

+   [525] R. Liu, D. Garrette, C. Saharia, W. Chan, A. Roberts, S. Narang, I. Blok, R. Mical, M. Norouzi, 和 N. Constant, “字符感知模型提升视觉文本渲染”，*arXiv 预印本 arXiv:2212.10562*，2022。

+   [526] J. Ma, M. Zhao, C. Chen, R. Wang, D. Niu, H. Lu, 和 X. Lin, “Glyphdraw：在图像合成模型中一致地学习绘制汉字”，*arXiv 预印本 arXiv:2303.17870*，2023。

+   [527] C. Chen, X. Yang, F. Yang, C. Feng, Z. Fu, C.-S. Foo, G. Lin, 和 F. Liu, “Sculpt3d：具有稀疏 3D 先验的一致多视角文本到 3D 生成”，*arXiv 预印本 arXiv:2403.09140*，2024。

+   [528] S. Woo, B. Park, H. Go, J.-Y. Kim, 和 C. Kim, “Harmonyview：在单图像到 3D 的一致性和多样性中取得平衡”，*arXiv 预印本 arXiv:2312.15980*，2023。

+   [529] J. Ye, P. Wang, K. Li, Y. Shi, 和 H. Wang, “Consistent-1-to-3：通过几何感知扩散模型实现一致的图像到 3D 视图合成”，*arXiv 预印本 arXiv:2310.03020*，2023。

+   [530] Q. Zuo, X. Gu, L. Qiu, Y. Dong, Z. Zhao, W. Yuan, R. Peng, S. Zhu, Z. Dong, L. Bo *等*，“Videomv：基于大型视频生成模型的一致多视角生成”，*arXiv 预印本 arXiv:2403.12010*，2024。

+   [531] P. Wang, S. Wang, J. Lin, S. Bai, X. Zhou, J. Zhou, X. Wang, 和 C. Zhou, “One-peace：探索一个通用表示模型以应对无限模态”，*arXiv 预印本 arXiv:2305.11172*，2023。

+   [532] C. Boletsis, A. Lie, O. Prillard, K. Husby, 和 J. Li, “Invizar 项目：用于夹套平台的增强现实可视化无损检测数据”，2023。

+   [533] S. Chen, H. Li, Q. Wang, Z. Zhao, M. Sun, X. Zhu, 和 J. Liu, “Vast：一个视觉-音频-字幕-文本的全模态基础模型和数据集”，*神经信息处理系统进展*，第 36 卷，2024。

+   [534] J. Kaplan, S. McCandlish, T. Henighan, T. B. Brown, B. Chess, R. Child, S. Gray, A. Radford, J. Wu, 和 D. Amodei, “神经语言模型的规模法则”，*arXiv 预印本 arXiv:2001.08361*，2020。

+   [535] P. Micikevicius, S. Narang, J. Alben, G. Diamos, E. Elsen, D. Garcia, B. Ginsburg, M. Houston, O. Kuchaiev, G. Venkatesh *等*，“混合精度训练，” *arXiv 预印本 arXiv:1710.03740*，2017 年。

+   [536] B. Jacob, S. Kligys, B. Chen, M. Zhu, M. Tang, A. Howard, H. Adam 和 D. Kalenichenko，“神经网络的量化与训练以实现高效的整数算术推理，”收录于 *IEEE 计算机视觉与模式识别会议论文集*，2018 年，第 2704–2713 页。

+   [537] T. Dettmers, M. Lewis, Y. Belkada 和 L. Zettlemoyer，“Gpt3\. int8 (): 大规模变换器的 8 位矩阵乘法，” *神经信息处理系统进展*，第 35 卷，第 30 318–30 332 页，2022 年。

+   [538] Y. Choukroun, E. Kravchik, F. Yang 和 P. Kisilev，“神经网络的低位量化以实现高效推理，”收录于 *2019 年 IEEE/CVF 国际计算机视觉大会研讨会（ICCVW）*。 IEEE，2019 年，第 3009–3018 页。

+   [539] X. Wu, C. Li, R. Y. Aminabadi, Z. Yao 和 Y. He，“理解语言模型的 int4 量化：延迟加速、可组合性和失败案例，”收录于 *国际机器学习大会*。 PMLR，2023 年，第 37 524–37 539 页。

+   [540] Y. Qu, X. Shen, X. He, M. Backes, S. Zannettou 和 Y. Zhang，“不安全的扩散：从文本到图像模型生成不安全图像和仇恨迷因，”收录于 *2023 年 ACM SIGSAC 计算机与通信安全会议论文集*，2023 年，第 3403–3417 页。

+   [541] D. Ha 和 J. Schmidhuber，“世界模型，” *arXiv 预印本 arXiv:1803.10122*，2018 年。

+   [542] H. Liu, W. Yan, M. Zaharia 和 P. Abbeel，“带有环注意力的百万长度视频与语言的世界模型，” *arXiv 预印本 arXiv:2402.08268*，2024 年。

+   [543] Y. LeCun，“通往自主机器智能的路径版本 0.9\. 2，2022-06-27，” *开放评论*，第 62 卷，第 1 期，2022 年。

+   [544] C. Min, D. Zhao, L. Xiao, Y. Nie 和 B. Dai，“Uniworld：通过世界模型进行自主驾驶预训练，” *arXiv 预印本 arXiv:2308.07234*，2023 年。

+   [545] D. Hafner, J. Pasukonis, J. Ba 和 T. Lillicrap，“通过世界模型掌握多样领域，” *arXiv 预印本 arXiv:2301.04104*，2023 年。

由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/) 于 2024 年 6 月 9 日星期日 11:27:10 生成
