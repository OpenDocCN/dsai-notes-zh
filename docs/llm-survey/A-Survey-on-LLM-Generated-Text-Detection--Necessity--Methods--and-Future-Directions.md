<!--yml

类别：未分类

日期：2024-09-03 17:31:43

-->

# 生成文本检测的调查：必要性、方法和未来方向

> 来源：[`arxiv.org/html/2310.14724`](https://arxiv.org/html/2310.14724)

1.  [1 引言](https://arxiv.org/html/2310.14724v3#S1 "在 生成文本检测的调查：必要性、方法和未来方向")

1.  [2 背景](https://arxiv.org/html/2310.14724v3#S2 "在 生成文本检测的调查：必要性、方法和未来方向")

    1.  [2.1 LLM 生成文本检测任务](https://arxiv.org/html/2310.14724v3#S2.SS1 "在 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

        1.  [人工撰写文本](https://arxiv.org/html/2310.14724v3#S2.SS1.SSS0.Px1 "在 2.1 LLM 生成文本检测任务 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

        1.  [LLM 生成文本](https://arxiv.org/html/2310.14724v3#S2.SS1.SSS0.Px2 "在 2.1 LLM 生成文本检测任务 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

        1.  [LLM 生成文本检测任务](https://arxiv.org/html/2310.14724v3#S2.SS1.SSS0.Px3 "在 2.1 LLM 生成文本检测任务 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

    1.  [2.2 LLMs 文本生成和混淆源](https://arxiv.org/html/2310.14724v3#S2.SS2 "在 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

        1.  [2.2.1 LLMs 的生成机制](https://arxiv.org/html/2310.14724v3#S2.SS2.SSS1 "在 2.2 LLMs 文本生成和混淆源 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

        1.  [2.2.2 LLMs 强大生成能力的来源](https://arxiv.org/html/2310.14724v3#S2.SS2.SSS2 "在 2.2 LLMs 文本生成和混淆源 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

            1.  [上下文学习（ICL）](https://arxiv.org/html/2310.14724v3#S2.SS2.SSS2.Px1 "在 2.2.2 LLMs 强大生成能力的来源 ‣ 2.2 LLMs 文本生成和混淆源 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

            1.  [对人类偏好的对齐](https://arxiv.org/html/2310.14724v3#S2.SS2.SSS2.Px2 "在 2.2.2 LLMs 强大生成能力的来源 ‣ 2.2 LLMs 文本生成和混淆源 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

            1.  [复杂推理能力](https://arxiv.org/html/2310.14724v3#S2.SS2.SSS2.Px3 "在 2.2.2 LLMs 强大生成能力的来源 ‣ 2.2 LLMs 文本生成和混淆源 ‣ 2 背景 ‣ 生成文本检测的调查：必要性、方法和未来方向")

    1.  [2.3 我们为什么需要检测 LLM 生成的文本？](https://arxiv.org/html/2310.14724v3#S2.SS3 "在 2 背景 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [规定](https://arxiv.org/html/2310.14724v3#S2.SS3.SSS0.Px1 "在 2.3 我们为什么需要检测 LLM 生成的文本？ ‣ 2 背景 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [用户](https://arxiv.org/html/2310.14724v3#S2.SS3.SSS0.Px2 "在 2.3 我们为什么需要检测 LLM 生成的文本？ ‣ 2 背景 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [发展](https://arxiv.org/html/2310.14724v3#S2.SS3.SSS0.Px3 "在 2.3 我们为什么需要检测 LLM 生成的文本？ ‣ 2 背景 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [科学](https://arxiv.org/html/2310.14724v3#S2.SS3.SSS0.Px4 "在 2.3 我们为什么需要检测 LLM 生成的文本？ ‣ 2 背景 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [人类社会](https://arxiv.org/html/2310.14724v3#S2.SS3.SSS0.Px5 "在 2.3 我们为什么需要检测 LLM 生成的文本？ ‣ 2 背景 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

1.  [3 相关工作与我们的调查](https://arxiv.org/html/2310.14724v3#S3 "在关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [3.1 相关工作](https://arxiv.org/html/2310.14724v3#S3.SS1 "在 3 相关工作与我们的调查 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [3.2 系统调查与实施](https://arxiv.org/html/2310.14724v3#S3.SS2 "在 3 相关工作与我们的调查 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

1.  [4 数据](https://arxiv.org/html/2310.14724v3#S4 "在关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [4.1 训练](https://arxiv.org/html/2310.14724v3#S4.SS1 "在 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [4.1.1 检测数据集](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1 "在 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [HC3](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px1 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [CHEAT](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px2 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [HC3 Plus](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px3 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [OpenLLMText](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px4 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [TweepFake 数据集](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px5 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [GPT2-Output 数据集](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px6 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [GROVER 数据集](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px7 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [ArguGPT 数据集](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px8 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [DeepfakeTextDetect 数据集](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS1.Px9 "在 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [4.1.2 潜在数据集](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2 "在 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [问答](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2.Px1 "在 4.1.2 潜在数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [科学写作](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2.Px2 "在 4.1.2 潜在数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [故事生成](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2.Px3 "在 4.1.2 潜在数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [新闻写作](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2.Px4 "在 4.1.2 潜在数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [网页文本](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2.Px5 "在 4.1.2 潜在数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [社交媒体](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2.Px6 "在 4.1.2 潜在数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [理解与推理](https://arxiv.org/html/2310.14724v3#S4.SS1.SSS2.Px7 "在 4.1.2 潜在数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [4.2 评估基准](https://arxiv.org/html/2310.14724v3#S4.SS2 "在 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [TuringBench](https://arxiv.org/html/2310.14724v3#S4.SS2.SSS0.Px1 "在 4.2 评估基准 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [MGTBench](https://arxiv.org/html/2310.14724v3#S4.SS2.SSS0.Px2 "在 4.2 评估基准 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [GPABenchmark](https://arxiv.org/html/2310.14724v3#S4.SS2.SSS0.Px3 "在 4.2 评估基准 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [科学文章基准](https://arxiv.org/html/2310.14724v3#S4.SS2.SSS0.Px4 "在 4.2 评估基准 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [MULTITuDE](https://arxiv.org/html/2310.14724v3#S4.SS2.SSS0.Px5 "在 4.2 评估基准 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [HANSEN](https://arxiv.org/html/2310.14724v3#S4.SS2.SSS0.Px6 "在 4.2 评估基准 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [M4](https://arxiv.org/html/2310.14724v3#S4.SS2.SSS0.Px7 "在 4.2 评估基准 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [4.3 数据挑战](https://arxiv.org/html/2310.14724v3#S4.SS3 "在 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [4.3.1 评估框架的全面性](https://arxiv.org/html/2310.14724v3#S4.SS3.SSS1 "在 4.3 数据挑战 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [多种攻击类型](https://arxiv.org/html/2310.14724v3#S4.SS3.SSS1.Px1 "在 4.3.1 评估框架的全面性 ‣ 4.3 数据挑战 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [多领域和多任务](https://arxiv.org/html/2310.14724v3#S4.SS3.SSS1.Px2 "在 4.3.1 评估框架的全面性 ‣ 4.3 数据挑战 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [多个 LLMs](https://arxiv.org/html/2310.14724v3#S4.SS3.SSS1.Px3 "在 4.3.1 评估框架的全面性 ‣ 4.3 数据挑战 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [多语言](https://arxiv.org/html/2310.14724v3#S4.SS3.SSS1.Px4 "在 4.3.1 评估框架的全面性 ‣ 4.3 数据挑战 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [4.3.2 时间性](https://arxiv.org/html/2310.14724v3#S4.SS3.SSS2 "在 4.3 数据挑战 ‣ 4 数据 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

1.  [5 检测器研究进展](https://arxiv.org/html/2310.14724v3#S5 "在关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [5.1 水印技术](https://arxiv.org/html/2310.14724v3#S5.SS1 "在 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.1.1 数据驱动水印](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS1 "在 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.1.2 模型驱动水印](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS2 "在 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [基于 Logits 的方法](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS2.Px1 "在 5.1.2 模型驱动水印 ‣ 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [基于 Token 采样的方法](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS2.Px2 "在 5.1.2 模型驱动水印 ‣ 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.1.3 后处理水印](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS3 "在 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [字符嵌入方法](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS3.Px1 "在 5.1.3 后处理水印 ‣ 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [基于同义词替换的方法](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS3.Px2 "在 5.1.3 后处理水印 ‣ 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [序列到序列的方法](https://arxiv.org/html/2310.14724v3#S5.SS1.SSS3.Px3 "在 5.1.3 后处理水印 ‣ 5.1 水印技术 ‣ 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [5.2 基于统计的方法](https://arxiv.org/html/2310.14724v3#S5.SS2 "在 5 检测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.2.1 语言学特征统计](https://arxiv.org/html/2310.14724v3#S5.SS2.SSS1 "在 5.2 基于统计的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.2.2 白箱统计](https://arxiv.org/html/2310.14724v3#S5.SS2.SSS2 "在 5.2 基于统计的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [基于逻辑回归的统计](https://arxiv.org/html/2310.14724v3#S5.SS2.SSS2.Px1 "在 5.2.2 白箱统计 ‣ 5.2 基于统计的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [扰动基方法](https://arxiv.org/html/2310.14724v3#S5.SS2.SSS2.Px2 "在 5.2.2 白箱统计 ‣ 5.2 基于统计的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [内在维度估计](https://arxiv.org/html/2310.14724v3#S5.SS2.SSS2.Px3 "在 5.2.2 白箱统计 ‣ 5.2 基于统计的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.2.3 黑箱统计](https://arxiv.org/html/2310.14724v3#S5.SS2.SSS3 "在 5.2 基于统计的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [5.3 神经网络方法](https://arxiv.org/html/2310.14724v3#S5.SS3 "在 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.3.1 基于特征的分类器](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS1 "在 5.3 神经网络方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [基于语言特征的分类器](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS1.Px1 "在 5.3.1 基于特征的分类器 ‣ 5.3 神经网络方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [基于模型特征的分类器](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS1.Px2 "在 5.3.1 基于特征的分类器 ‣ 5.3 神经网络方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.3.2 预训练分类器](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS2 "在 5.3 神经网络方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [领域内微调是你所需的一切](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS2.Px1 "在 5.3.2 预训练分类器 ‣ 5.3 神经网络方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [对比学习](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS2.Px2 "在 5.3.2 预训练分类器 ‣ 5.3 基于神经网络的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [对抗学习方法](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS2.Px3 "在 5.3.2 预训练分类器 ‣ 5.3 基于神经网络的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [特征增强方法](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS2.Px4 "在 5.3.2 预训练分类器 ‣ 5.3 基于神经网络的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.3.3 LLM 作为探测器](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS3 "在 5.3 基于神经网络的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [使用 LLM 的可靠性问题](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS3.Px1 "在 5.3.3 LLM 作为探测器 ‣ 5.3 基于神经网络的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

            1.  [ICL：一种强大的 LLM 基于检测技术](https://arxiv.org/html/2310.14724v3#S5.SS3.SSS3.Px2 "在 5.3.3 LLM 作为探测器 ‣ 5.3 基于神经网络的方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [5.4 人工辅助方法](https://arxiv.org/html/2310.14724v3#S5.SS4 "在 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.4.1 直观指标](https://arxiv.org/html/2310.14724v3#S5.SS4.SSS1 "在 5.4 人工辅助方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.4.2 难以察觉的特征](https://arxiv.org/html/2310.14724v3#S5.SS4.SSS2 "在 5.4 人工辅助方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.4.3 提升人类检测能力](https://arxiv.org/html/2310.14724v3#S5.SS4.SSS3 "在 5.4 人工辅助方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [5.4.4 混合检测：理解与解释](https://arxiv.org/html/2310.14724v3#S5.SS4.SSS4 "在 5.4 人工辅助方法 ‣ 5 探测器研究进展 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

1.  [6 评估指标](https://arxiv.org/html/2310.14724v3#S6 "在 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [准确率](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px1 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [精确度](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px2 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [召回率](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px3 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [假阳性率 (FPR)](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px4 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [真阴性率 (TNR)](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px5 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [假阴性率 (FNR)](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px6 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [<math alttext="F_{1}" class="ltx_Math" display="inline"><semantics><msub><mi>F</mi><mn>1</mn></msub><annotation-xml encoding="MathML-Content"><apply><csymbol cd="ambiguous">subscript</csymbol><ci>𝐹</ci><cn type="integer">1</cn></apply></annotation-xml><annotation encoding="application/x-tex">F_{1}</annotation><annotation encoding="application/x-llamapun">italic_F start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT</annotation></semantics></math> 分数](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px7 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [AUROC](https://arxiv.org/html/2310.14724v3#S6.SS0.SSS0.Px8 "在 6 评价指标中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

1.  [LLM 生成文本检测的 7 个重要问题](https://arxiv.org/html/2310.14724v3#S7 "在 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [7.1 分布外挑战](https://arxiv.org/html/2310.14724v3#S7.SS1 "在 LLM 生成文本检测的 7 个重要问题中 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [跨领域](https://arxiv.org/html/2310.14724v3#S7.SS1.SSS0.Px1 "在 7.1 分布外挑战中 ‣ LLM 生成文本检测的 7 个重要问题 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [跨语言](https://arxiv.org/html/2310.14724v3#S7.SS1.SSS0.Px2 "在 7.1 分布外挑战中 ‣ LLM 生成文本检测的 7 个重要问题 ‣ LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [跨 LLMs](https://arxiv.org/html/2310.14724v3#S7.SS1.SSS0.Px3 "在 7.1 分布外挑战 ‣ 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [7.2 潜在攻击](https://arxiv.org/html/2310.14724v3#S7.SS2 "在 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [释义攻击](https://arxiv.org/html/2310.14724v3#S7.SS2.SSS0.Px1 "在 7.2 潜在攻击 ‣ 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [对抗攻击](https://arxiv.org/html/2310.14724v3#S7.SS2.SSS0.Px2 "在 7.2 潜在攻击 ‣ 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [提示攻击](https://arxiv.org/html/2310.14724v3#S7.SS2.SSS0.Px3 "在 7.2 潜在攻击 ‣ 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [训练威胁模型](https://arxiv.org/html/2310.14724v3#S7.SS2.SSS0.Px4 "在 7.2 潜在攻击 ‣ 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [7.3 真实数据问题](https://arxiv.org/html/2310.14724v3#S7.SS3 "在 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [对非纯 LLM 生成文本的检测](https://arxiv.org/html/2310.14724v3#S7.SS3.SSS0.Px1 "在 7.3 真实数据问题 ‣ 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

        1.  [数据模糊性](https://arxiv.org/html/2310.14724v3#S7.SS3.SSS0.Px2 "在 7.3 真实数据问题 ‣ 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [7.4 模型规模对检测器的影响](https://arxiv.org/html/2310.14724v3#S7.SS4 "在 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [7.5 缺乏有效评估框架](https://arxiv.org/html/2310.14724v3#S7.SS5 "在 7 个 LLM 生成文本检测的重要问题 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

1.  [8 未来研究方向](https://arxiv.org/html/2310.14724v3#S8 "在 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [8.1 通过攻击构建稳健检测器](https://arxiv.org/html/2310.14724v3#S8.SS1 "在 8 未来研究方向 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [8.2 提升零样本检测器的效能](https://arxiv.org/html/2310.14724v3#S8.SS2 "在 8 个未来研究方向 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [8.3 为低资源环境优化检测器](https://arxiv.org/html/2310.14724v3#S8.SS3 "在 8 个未来研究方向 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [8.4 针对非纯 LLM 生成文本的检测](https://arxiv.org/html/2310.14724v3#S8.SS4 "在 8 个未来研究方向 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [8.5 在数据模糊性中构建检测器](https://arxiv.org/html/2310.14724v3#S8.SS5 "在 8 个未来研究方向 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [8.6 制定与现实世界对接的有效评估框架](https://arxiv.org/html/2310.14724v3#S8.SS6 "在 8 个未来研究方向 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

    1.  [8.7 构建具有虚假信息辨别能力的检测器](https://arxiv.org/html/2310.14724v3#S8.SS7 "在 8 个未来研究方向 ‣ 关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

1.  [9 结论](https://arxiv.org/html/2310.14724v3#S9 "在关于 LLM 生成文本检测的调查：必要性、方法和未来方向")

\NewCommandCopy\cnumdef\numdef\NewCommandCopy\endcnumdef\endnumdef

y2023

# 关于 LLM 生成文本检测的调查：必要性、方法和未来方向

Junchao Wu NLP²CT 实验室，科学与技术学院

协作创新研究所

澳门大学

nlp2ct.junchao@gmail.com    Shu Yang NLP²CT 实验室，科学与技术学院

协作创新研究所

澳门大学

nlp2ct.shuyang@gmail.com    Runzhe Zhan NLP²CT 实验室，科学与技术学院

协作创新研究所

澳门大学

nlp2ct.runzhe@gmail.com    Yulin Yuan^∗ 中文语言文学系，艺术与人文学院

澳门大学

yulinyuan@um.edu.mo

中文语言文学系， 人文学院

北京大学

yuanyl@pku.edu.cn    Derek Fai Wong Yulin Yuan 和 Derek Fai Wong 是共同通讯作者。NLP²CT 实验室，科学与技术学院

协作创新研究所

澳门大学

derekfw@um.edu.mo    Lidia Sam Chao NLP²CT 实验室，科学与技术学院

智慧城市物联网国家重点实验室

澳门大学

lidiasc@um.edu.mo

###### 摘要

从大型语言模型（LLMs）中出现的强大能力，使得 LLM 生成的文本以惊人的速度涌入我们日常生活的许多领域，并被人们广泛接受。随着 LLM 的不断扩展，迫切需要开发可以检测 LLM 生成文本的工具。这对于减少 LLM 的潜在误用和保护艺术表达及社交网络等领域免受 LLM 生成内容的有害影响至关重要。LLM 生成文本检测旨在辨别一段文本是否由 LLM 生成，这本质上是一个二分类任务。检测器技术最近取得了显著进展，这得益于水印技术、基于统计的检测器、神经网络基础的检测器以及人工辅助方法的创新。在这项调查中，我们汇总了该领域的最新研究突破，并强调了加强检测器研究的紧迫需求。我们还*深入探讨*了流行的数据集，阐明了它们的局限性和发展需求。此外，我们分析了各种 LLM 生成文本检测模式，揭示了诸如分布外问题、潜在攻击、真实世界数据问题以及缺乏有效评估框架等挑战。最后，我们突出了未来在 LLM 生成文本检测领域的有趣研究方向，以推动负责任的人工智能（AI）实施。我们希望通过这项调查，为新手提供清晰全面的介绍，同时为经验丰富的研究人员提供该领域的宝贵更新。有关有用的资源可以公开获取，网址为：[`github.com/NLP2CT/LLM-generated-Text-Detection`](https://github.com/NLP2CT/LLM-generated-Text-Detection)。

^†^†问题：x

## 1 引言

随着大型语言模型（LLMs）的快速发展，这些模型的文本生成能力已经达到了与人类写作相媲美的水平 OpenAI ([2023](https://arxiv.org/html/2310.14724v3#bib.bib160))；Anthropic ([2023](https://arxiv.org/html/2310.14724v3#bib.bib5))；Chowdhery et al. ([2022b](https://arxiv.org/html/2310.14724v3#bib.bib35))。大型语言模型已经渗透到日常生活的各个方面，并在许多专业工作流程中发挥着至关重要的作用，Veselovsky、Ribeiro 和 West ([2023](https://arxiv.org/html/2310.14724v3#bib.bib223))，例如广告标语创作 Murakami、Hoshino 和 Zhang ([2023](https://arxiv.org/html/2310.14724v3#bib.bib155))，新闻撰写 Yanagi et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib240))，故事生成 Yuan et al. ([2022](https://arxiv.org/html/2310.14724v3#bib.bib251))，以及代码生成 Becker et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib18))；Zheng et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib258))。Hanley 和 Durumeric ([2023](https://arxiv.org/html/2310.14724v3#bib.bib82)) 的最新研究表明，从 2022 年 1 月 1 日到 2023 年 5 月 1 日，主流网站上 AI 生成的新闻文章数量相对增加了 55.4%，而在以传播虚假信息著称的网站上，该数量增加了 457%。此外，这些模型的影响显著塑造了多个领域和学科的进展，包括教育 Susnjak ([2022](https://arxiv.org/html/2310.14724v3#bib.bib205))，法律 Cui et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib46))，生物学 Piccolo et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib166))，以及医学 Thirunavukarasu et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib209))。

LLMs 的强大生成能力使得个人难以区分 LLM 生成的文本和人类编写的文本，导致了复杂的担忧。这些对 LLM 生成文本的担忧来源于两个方面。首先，LLMs 容易出现虚假信息（Ji et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib94))）、依赖过时信息以及对提示的高度敏感性。这些漏洞可能促进错误知识的传播（Christian ([2023](https://arxiv.org/html/2310.14724v3#bib.bib36))）、削弱技术专长（Rodriguez et al. ([2022a](https://arxiv.org/html/2310.14724v3#bib.bib179))；Aliman 和 Kester ([2021](https://arxiv.org/html/2310.14724v3#bib.bib4))），并且促进抄袭（Lee et al. ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib116))）。其次，LLMs 可能被恶意利用进行虚假信息传播（Pagnoni, Graciarena, 和 Tsvetkov ([2022a](https://arxiv.org/html/2310.14724v3#bib.bib163))；Lin, Hilton, 和 Evans ([2022](https://arxiv.org/html/2310.14724v3#bib.bib126))）、在线欺诈（Weidinger et al. ([2021](https://arxiv.org/html/2310.14724v3#bib.bib232))；Ayoobi, Shahriar, 和 Mukherjee ([2023](https://arxiv.org/html/2310.14724v3#bib.bib12))）、社交媒体垃圾信息生产（Mirsky et al. ([2022](https://arxiv.org/html/2310.14724v3#bib.bib145))），以及学术不诚实，尤其是学生利用 LLMs 进行论文写作（Stokel-Walker ([2022](https://arxiv.org/html/2310.14724v3#bib.bib201))；Kasneci et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib100))）。与此同时，LLMs 在 AI 研究中越来越多地承担数据生成的责任，这导致了 LLM 生成文本在自身训练和评估中的递归使用。最近的一项分析，名为模型自噬紊乱（MAD）（Alemohammad et al., [2023](https://arxiv.org/html/2310.14724v3#bib.bib3)），对这种 AI 数据反馈循环提出了警告。随着生成模型的迭代改进，LLM 生成的文本可能逐渐取代人类策划的训练数据。这可能导致后续模型质量和多样性的下降。总的来说，LLM 生成文本的后果涵盖了社会（Cardenuto et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib26)））和学术（Yu et al. ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib249)））风险，LLM 生成数据的使用将阻碍 LLMs 及其检测技术的未来发展。

然而，对于 LLM 生成文本检测任务，目前的检测技术，包括商业检测器的**Price**和**Sakellarios** ([2023](https://arxiv.org/html/2310.14724v3#bib.bib169)) 的鉴别能力都是不可靠的。它们主要倾向于将输出分类为人类书写的文本，而不是检测 LLM 生成的文本**Walters** ([2023](https://arxiv.org/html/2310.14724v3#bib.bib224)); **Weber-Wulff**等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib229), [2023](https://arxiv.org/html/2310.14724v3#bib.bib230))。依赖于人类的检测方法也不可靠，准确性非常低，甚至仅比随机分类略好**Uchendu**等 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib219)); **Dou**等 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib56)); **Clark**等 ([2021a](https://arxiv.org/html/2310.14724v3#bib.bib37)); **Soni**和**Wade** ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib198), [b](https://arxiv.org/html/2310.14724v3#bib.bib199))。此外，人类识别 LLM 生成文本的能力通常低于检测器或检测算法在各种环境设置中的能力**Ippolito**等 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib92)); **Soni**和**Wade** ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib199))。因此，迫切需要建立稳健的检测器来有效识别 LLM 生成的文本。建立这样的机制对减少 LLM 滥用风险和推动 LLM 时代的负责任 AI 治理至关重要**Stokel-Walker**和**Van Noorden** ([2023](https://arxiv.org/html/2310.14724v3#bib.bib202)); **Porsdam Mann**等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib168)); **Shevlane**等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib194))。

对于 LLM 生成文本的检测研究，即便在 ChatGPT 出现之前，也受到了广泛关注，尤其是在早期识别深度伪造文本 Pu 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib170))、机器生成文本检测 Jawahar、Abdul-Mageed 和 Lakshmanan ([2020](https://arxiv.org/html/2310.14724v3#bib.bib93)) 和作者身份归属 Uchendu、Le 和 Lee ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib215)) 等领域。通常，这个问题被视为分类任务，旨在区分 LLM 生成的文本与人类撰写的文本 Jawahar、Abdul-Mageed 和 Lakshmanan ([2020](https://arxiv.org/html/2310.14724v3#bib.bib93))。回到这一研究阶段，检测任务主要集中在翻译生成的文本上，并利用简单的统计方法。ChatGPT 的出现引发了对 LLM 的极大兴趣，标志着研究领域的范式转变。为了应对 LLM 生成文本带来的挑战，NLP 社区积极寻求解决方案，深入研究 LLM 生成文本的检测及相关攻击方法。虽然 Crothers、Japkowicz 和 Viktor ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib43))；Tang、Chuang 和 Hu ([2023](https://arxiv.org/html/2310.14724v3#bib.bib206)) 最近对该主题进行了综述，但我们认为现有的检测方法深度仍然不足（我们在[子节 3.1](https://arxiv.org/html/2310.14724v3#S3.SS1 "3.1 Related Works ‣ 3 Related Works and Our Investigation ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")中详细讨论了相关工作）。

在本文中，我们提供了对当前 LLM 生成文本检测研究的细致和深刻的综述，旨在指导研究人员应对挑战并探索未来的研究方向。我们探讨了最新的突破性进展，从介绍 LLM 生成文本检测任务开始，解析 LLM 文本生成的基本机制以及 LLM 文本生成能力的来源。我们还阐明了 LLM 生成文本检测的背景和必要性。此外，我们重点介绍了该任务中流行的数据集和基准，揭示了它们当前的不足，以激发更精细的数据资源的创建。我们的讨论延伸到最新的检测器研究。除了传统的基于神经网络的方法和基于统计的方法，我们还报告了水印技术和人工辅助方法。随后，我们分析了 LLM 生成文本检测器的研究局限性，突出了像分布外挑战、潜在攻击、现实数据问题以及缺乏有效评估框架等关键领域。最后，我们对未来研究的潜在方向进行了思考，旨在帮助开发高效的检测器。

## 2 背景

### 2.1 LLM 生成文本检测任务

图 1：LLM 生成文本检测任务的示意图。该任务是一个二分类任务，用于检测提供的文本是由 LLM 生成还是由人类撰写。

检测 LLM 生成的文本是一项复杂的挑战。一般而言，人们很难区分 LLM 生成的文本与人工撰写的文本（Uchendu 等人 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib219)); Dou 等人 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib56)); Clark 等人 ([2021a](https://arxiv.org/html/2310.14724v3#bib.bib37)); Soni 和 Wade ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib198), [b](https://arxiv.org/html/2310.14724v3#bib.bib199))），他们区分这些文本的能力仅稍微超出随机分类。 [表 1](https://arxiv.org/html/2310.14724v3#S2.T1 "Table 1 ‣ 2.1 LLM-generated Text Detection Task ‣ 2 Background ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions") 提供了一些例子，其中 LLM 生成的文本与人工撰写的文本非常接近，难以区分。当 LLM 生成虚构的细节时，辨别其来源和真实性同样具有挑战性。

表 1：人工撰写文本和 LLM 生成文本的例子。LLM 在正常操作期间生成的文本和虚构事实的实例通常没有直观上可辨别的差异。当 LLM 要么选择不提供回答，要么制作中立回应时，某些指标，例如明确声明“我是一个 AI 语言模型”，可能有助于人类判断，但这样的例子较少。

| 类型 | 问题 | 人工撰写 | LLM 生成 |
| --- | --- | --- | --- |
| 正常 |

&#124; 解释什么是 NLP？ &#124;

|

&#124; 自然语言处理 (NLP) 是语言学、计算机科学和人工智能的跨学科子领域 … &#124;

|

&#124; 自然语言处理 (NLP) 是计算机科学、人工智能和语言学的一个领域，专注于 … &#124;

|

| 拒绝 |
| --- |

&#124; 今天有什么特别的吗？ &#124;

|

&#124; 今天的特别节目是由 Clive VanderBurgh 在 TVOntario 制作的加拿大儿童电视节目，制作时间为 1981 年至 1987 年。 &#124;

|

&#124; 对不起，我是一个 AI 语言模型，无法访问当前的日期或事件。还有什么我可以帮助你的吗 … &#124;

|

| 虚构 |
| --- |

&#124; 根据最近文献中的一篇出版物，解释什么是 NLP。 &#124;

|

&#124; 在“自然语言处理：最新进展、当前趋势与挑战”中，NLP 被总结为一个使用各种算法、工具和方法的学科 … &#124;

|

&#124; NLP 是计算机科学、语言学和人工智能交叉的多学科领域，如最近的一篇同行评审出版物《自然语言处理：全面概述与近期进展》（2023）中所述 … &#124;

|

最近的研究 Guo 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib78))；Ma、Liu 和 Yi ([2023](https://arxiv.org/html/2310.14724v3#bib.bib137))；Muñoz-Ortiz、Gómez-Rodríguez 和 Vilares ([2023](https://arxiv.org/html/2310.14724v3#bib.bib153))；Giorgi 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib73))；Seals 和 Shalin ([2023](https://arxiv.org/html/2310.14724v3#bib.bib191)) 强调了人类撰写文本与 LLM 生成文本（如 ChatGPT）之间的显著差异。这些差异不仅体现在个别单词选择的范围内 Seals 和 Shalin ([2023](https://arxiv.org/html/2310.14724v3#bib.bib191))，还体现在风格维度上，例如句法简洁性、被动语态的使用和叙事性。值得注意的是，与人类撰写的文本相比，LLM 生成的文本通常表现出更高的组织性、逻辑结构、正式性和客观性。此外，LLM 经常产生广泛且全面的回应，具有较低的偏见和有害内容的出现频率。然而，它们偶尔会引入无意义或虚假的细节。从语言学角度来看，LLM 生成的文本往往是人类撰写文本的两倍长度，但词汇量较为有限。LLM 的名词、动词、限定词、形容词、助动词、连词和虚词类别的使用频率高于人类，而副词和标点符号较少，在句法中包含更多决定性、连接性和辅助结构。此外，LLM 生成的文本通常传达的情感强度较低，表现得比人类写作更清晰，这种现象可能与 LLM 中固有的积极偏见有关 Giorgi、Ungar 和 Schwartz ([2021](https://arxiv.org/html/2310.14724v3#bib.bib74))；Markowitz、Hancock 和 Bailenson ([2023](https://arxiv.org/html/2310.14724v3#bib.bib142))；Mitrovic、Andreoletti 和 Ayoub ([2023](https://arxiv.org/html/2310.14724v3#bib.bib147))。尽管不同数据集上存在略微不同的统计差异，但 LLM 生成文本与人类撰写文本之间的差异是明显的，因为语言特征和人类视觉感知的统计结果是一致的。Chakraborty 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib29)) 通过报告 LLM 生成文本的可检测性，进一步证实了这一观点，包括像 GPT-3.5-Turbo 和 GPT-4 这样的高性能模型 Helm、Priebe 和 Yang ([2023](https://arxiv.org/html/2310.14724v3#bib.bib84))，而 Chakraborty 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib28)) 则引入了 AI 可检测性指数，以进一步根据模型的可检测性对其进行排序。

在本次调查中，我们首先提供了人类撰写文本、LLM 生成文本和检测任务的定义。

##### 人类撰写的文本

被描述为个人创作的文本，用于表达思想、情感和观点。这包括文章、诗歌和评论等，通常反映个人知识、文化背景和情感倾向，涵盖了人类经验的全部。

##### LLM 生成的文本

定义为由 LLM 生成的连贯、语法正确且相关的内容。这些模型广泛使用 NLP 技术进行训练，利用大规模数据集和机器学习方法。生成文本的质量和真实性通常依赖于模型的规模和训练数据的多样性。

##### LLM 生成文本检测任务

被概念化为一个二分类任务，旨在确定给定的文本是否由 LLM 生成。这个任务的正式表示形式由以下方程给出：

|  | <math alttext="D(x)=\left\{\begin{array}[]{rcl}1&&\text{如果 }x\text{ 是由 LLMs 生成的}\\ 0&&\text{如果 }x\text{ 是由人类编写的}\end{array}\right." class="ltx_Math" display="block" id="S2.E1.m1.2"><semantics id="S2.E1.m1.2a"><mrow id="S2.E1.m1.2.3" xref="S2.E1.m1.2.3.cmml"><mrow id="S2.E1.m1.2.3.2" xref="S2.E1.m1.2.3.2.cmml"><mi id="S2.E1.m1.2.3.2.2" xref="S2.E1.m1.2.3.2.2.cmml">D</mi><mo id="S2.E1.m1.2.3.2.1" xref="S2.E1.m1.2.3.2.1.cmml">⁢</mo><mrow id="S2.E1.m1.2.3.2.3.2" xref="S2.E1.m1.2.3.2.cmml"><mo id="S2.E1.m1.2.3.2.3.2.1" stretchy="false" xref="S2.E1.m1.2.3.2.cmml">(</mo><mi id="S2.E1.m1.1.1" xref="S2.E1.m1.1.1.cmml">x</mi><mo id="S2.E1.m1.2.3.2.3.2.2" stretchy="false" xref="S2.E1.m1.2.3.2.cmml">)</mo></mrow></mrow><mo id="S2.E1.m1.2.3.1" xref="S2.E1.m1.2.3.1.cmml">=</mo><mrow id="S2.E1.m1.2.3.3.2" xref="S2.E1.m1.2.3.3.1.cmml"><mo id="S2.E1.m1.2.3.3.2.1" xref="S2.E1.m1.2.3.3.1.1.cmml">{</mo><mtable columnspacing="5pt" displaystyle="true" id="S2.E1.m1.2.2" rowspacing="8.0pt" xref="S2.E1.m1.2.2.cmml"><mtr id="S2.E1.m1.2.2a" xref="S2.E1.m1.2.2.cmml"><mtd class="ltx_align_right" columnalign="right" id="S2.E1.m1.2.2b" xref="S2.E1.m1.2.2.cmml"><mn id="S2.E1.m1.2.2.1.1.1" xref="S2.E1.m1.2.2.1.1.1.cmml">1</mn></mtd><mtd class="ltx_align_left" columnalign="left" id="S2.E1.m1.2.2d" xref="S2.E1.m1.2.2.cmml"><mrow id="S2.E1.m1.2.2.1.3.1" xref="S2.E1.m1.2.2.1.3.1.cmml"><mtext id="S2.E1.m1.2.2.1.3.1.2" xref="S2.E1.m1.2.2.1.3.1.2a.cmml">如果 </mtext><mo id="S2.E1.m1.2.2.1.3.1.1" xref="S2.E1.m1.2.2.1.3.1.1.cmml">⁢</mo><mi id="S2.E1.m1.2.2.1.3.1.3" xref="S2.E1.m1.2.2.1.3.1.3.cmml">x</mi><mo id="S2.E1.m1.2.2.1.3.1.1a" xref="S2.E1.m1.2.2.1.3.1.1.cmml">⁢</mo><mtext id="S2.E1.m1.2.2.1.3.1.4" xref="S2.E1.m1.2.2.1.3.1.4a.cmml"> 由 LLMs 生成</mtext></mrow></mtd></mtr><mtr id="S2.E1.m1.2.2e" xref="S2.E1.m1.2.2.cmml"><mtd class="ltx_align_right" columnalign="right" id="S2.E1.m1.2.2f" xref="S2.E1.m1.2.2.cmml"><mn id="S2.E1.m1.2.2.2.1.1" xref="S2.E1.m1.2.2.2.1.1.cmml">0</mn></mtd><mtd class="ltx_align_left" columnalign="left" id="S2.E1.m1.2.2h" xref="S2.E1.m1.2.2.cmml"><mrow id="S2.E1.m1.2.2.2.3.1" xref="S2.E1.m1.2.2.2.3.1.cmml"><mtext id="S2.E1.m1.2.2.2.3.1.2" xref="S2.E1.m1.2.2.2.3.1.2a.cmml">如果 </mtext><mo id="S2.E1.m1.2.2.2.3.1.1" xref="S2.E1.m1.2.2.2.3.1.1.cmml">⁢</mo><mi id="S2.E1.m1.2.2.2.3.1.3" xref="S2.E1.m1.2.2.2.3.1.3.cmml">x</mi><mo id="S2.E1.m1.2.2.2.3.1.1a" xref="S2.E1.m1.2.2.2.3.1.1.cmml">⁢</mo><mtext id="S2.E1.m1.2.2.2.3.1.4" xref="S2.E1.m1.2.2.2.3.1.4a.cmml"> 由人类编写</mtext></mrow></mtd></mtr></mtable></mrow></mrow><annotation-xml encoding="MathML-Content" id="S2.E1.m1.2b"><apply id="S2.E1.m1.2.3.cmml" xref="S2.E1.m1.2.3"><apply id="S2.E1.m1.2.3.2.cmml" xref="S2.E1.m1.2.3.2"><ci id="S2.E1.m1.2.3.2.2.cmml" xref="S2.E1.m1.2.3.2.2">𝐷</ci><ci id="S2.E1.m1.1.1.cmml" xref="S2.E1.m1.1.1">𝑥</ci></apply><apply id="S2.E1.m1.2.3.3.1.cmml" xref="S2.E1.m1.2.3.3.2"><csymbol cd="latexml" id="S2.E1.m1.2.3.3.1.1.cmml" xref="S2.E1.m1.2.3.3.2.1">cases</csymbol><matrix id="S2.E1.m1.2.2.cmml" xref="S2.E1.m1.2.2"><matrixrow id="S2.E1.m1.2.2a.cmml" xref="S2.E1.m1.2.2"><cn id="S2.E1.m1.2.2.1.1.1.cmml" type="integer" xref="S2.E1.m1.2.2.1.1.1">1</cn><cerror id="S2.E1.m1.2.2b.cmml" xref="S2.E1.m1.2.2"><csymbol cd="ambiguous" id="S2.E1.m1.2.2c.cmml" xref="S2.E1.m1.2.2">missing-subexpression</csymbol></cerror><apply id="S2.E1.m1.2.2 |
| --- | --- |

`<math alttext="D(x)" class="ltx_Math" display="inline" id="S2.SS1.SSS0.Px3.p2.1.m1.1"><semantics id="S2.SS1.SSS0.Px3.p2.1.m1.1a"><mrow id="S2.SS1.SSS0.Px3.p2.1.m1.1.2" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2.cmml"><mi id="S2.SS1.SSS0.Px3.p2.1.m1.1.2.2" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2.2.cmml">D</mi><mo id="S2.SS1.SSS0.Px3.p2.1.m1.1.2.1" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2.1.cmml">⁢</mo><mrow id="S2.SS1.SSS0.Px3.p2.1.m1.1.2.3.2" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2.cmml"><mo id="S2.SS1.SSS0.Px3.p2.1.m1.1.2.3.2.1" stretchy="false" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2.cmml">(</mo><mi id="S2.SS1.SSS0.Px3.p2.1.m1.1" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.1.cmml">x</mi><mo id="S2.SS1.SSS0.Px3.p2.1.m1.1.2.3.2.2" stretchy="false" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2.cmml">)</mo></mrow></mrow><annotation-xml encoding="MathML-Content" id="S2.SS1.SSS0.Px3.p2.1.m1.1b"><apply id="S2.SS1.SSS0.Px3.p2.1.m1.1.2.cmml" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2"><ci id="S2.SS1.SSS0.Px3.p2.1.m1.1.2.2.cmml" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.2.2">𝐷</ci><ci id="S2.SS1.SSS0.Px3.p2.1.m1.1.1.cmml" xref="S2.SS1.SSS0.Px3.p2.1.m1.1.1">𝑥</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S2.SS1.SSS0.Px3.p2.1.m1.1c">D(x)</annotation><annotation encoding="application/x-llamapun" id="S2.SS1.SSS0.Px3.p2.1.m1.1d">italic_D ( italic_x )</annotation></semantics></math> 代表探测器，而 <math alttext="x" class="ltx_Math" display="inline" id="S2.SS1.SSS0.Px3.p2.2.m2.1"><semantics id="S2.SS1.SSS0.Px3.p2.2.m2.1a"><mi id="S2.SS1.SSS0.Px3.p2.2.m2.1.1" xref="S2.SS1.SSS0.Px3.p2.2.m2.1.1.cmml">x</mi><annotation-xml encoding="MathML-Content" id="S2.SS1.SSS0.Px3.p2.2.m2.1b"><ci id="S2.SS1.SSS0.Px3.p2.2.m2.1.1.cmml" xref="S2.SS1.SSS0.Px3.p2.2.m2.1.1">𝑥</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.SS1.SSS0.Px3.p2.2.m2.1c">x</annotation><annotation encoding="application/x-llamapun" id="S2.SS1.SSS0.Px3.p2.2.m2.1d">italic_x</annotation></semantics></math> 是待检测的文本。

### 2.2 LLMs 的文本生成与混淆源

#### 2.2.1 LLMs 的生成机制

LLM 的文本生成机制通过顺序预测后续的令牌来运作。LLM 并不会瞬间生成整段文本，而是有条不紊地逐字构建文本。具体来说，LLM 解码文本序列中的后续令牌，考虑到输入序列和先前解码的令牌。假设总时间步为<math alttext="T" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p1.1.m1.1"><semantics id="S2.SS2.SSS1.p1.1.m1.1a"><mi id="S2.SS2.SSS1.p1.1.m1.1.1" xref="S2.SS2.SSS1.p1.1.m1.1.1.cmml">T</mi><annotation-xml encoding="MathML-Content" id="S2.SS2.SSS1.p1.1.m1.1b"><ci id="S2.SS2.SSS1.p1.1.m1.1.1.cmml" xref="S2.SS2.SSS1.p1.1.m1.1.1">𝑇</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.SS2.SSS1.p1.1.m1.1c">T</annotation><annotation encoding="application/x-llamapun" id="S2.SS2.SSS1.p1.1.m1.1d">italic_T</annotation></semantics></math>，当前时间步为<math alttext="t" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p1.2.m2.1"><semantics id="S2.SS2.SSS1.p1.2.m2.1a"><mi id="S2.SS2.SSS1.p1.2.m2.1.1" xref="S2.SS2.SSS1.p1.2.m2.1.1.cmml">t</mi><annotation-xml encoding="MathML-Content" id="S2.SS2.SSS1.p1.2.m2.1b"><ci id="S2.SS2.SSS1.p1.2.m2.1.1.cmml" xref="S2.SS2.SSS1.p1.2.m2.1.1">𝑡</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.SS2.SSS1.p1.2.m2.1c">t</annotation><annotation encoding="application/x-llamapun" id="S2.SS2.SSS1.p1.2.m2.1d">italic_t</annotation></semantics></math>，输入文本或令牌化序列为：<math alttext="X_{T}=\{x_{1},x_{2},...x_{T}\}" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p1.3.m3.3"><semantics id="S2.SS2.SSS1.p1.3.m3.3a"><mrow id="S2.SS2.SSS1.p1.3.m3.3.3" xref="S2.SS2.SSS1.p1.3.m3.3.3.cmml"><msub id="S2.SS2.SSS1.p1.3.m3.3.3.5" xref="S2.SS2.SSS1.p1.3.m3.3.3.5.cmml"><mi id="S2.SS2.SSS1.p1.3.m3.3.3.5.2" xref="S2.SS2.SSS1.p1.3.m3.3.3.5.2.cmml">X</mi><mi id="S2.SS2.SSS1.p1.3.m3.3.3.5.3" xref="S2.SS2.SSS1.p1.3.m3.3.3.5.3.cmml">T</mi></msub><mo id="S2.SS2.SSS1.p1.3.m3.3.3.4" xref="S2.SS2.SSS1.p1.3.m3.3.3.4.cmml">=</mo><mrow id="S2.SS2.SSS1.p1.3.m3.3.3.3.3" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.4.cmml"><mo id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.4" stretchy="false" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.4.cmml">{</mo><msub id="S2.SS2.SSS1.p1.3.m3.1.1.1.1.1" xref="S2.SS2.SSS1.p1.3.m3.1.1.1.1.1.cmml"><mi id="S2.SS2.SSS1.p1.3.m3.1.1.1.1.1.2" xref="S2.SS2.SSS1.p1.3.m3.1.1.1.1.1.2.cmml">x</mi><mn id="S2.SS2.SSS1.p1.3.m3.1.1.1.1.1.3" xref="S2.SS2.SSS1.p1.3.m3.1.1.1.1.1.3.cmml">1</mn></msub><mo id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.5" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.4.cmml">,</mo><msub id="S2.SS2.SSS1.p1.3.m3.2.2.2.2.2" xref="S2.SS2.SSS1.p1.3.m3.2.2.2.2.2.cmml"><mi id="S2.SS2.SSS1.p1.3.m3.2.2.2.2.2.2" xref="S2.SS2.SSS1.p1.3.m3.2.2.2.2.2.2.cmml">x</mi><mn id="S2.SS2.SSS1.p1.3.m3.2.2.2.2.2.3" xref="S2.SS2.SSS1.p1.3.m3.2.2.2.2.2.3.cmml">2</mn></msub><mo id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.6" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.4.cmml">,</mo><mrow id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.cmml"><mi id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.2" mathvariant="normal" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.2.cmml">…</mi><mo id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.1" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.1.cmml">⁢</mo><msub id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.3" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.3.cmml"><mi id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.3.2" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.3.2.cmml">x</mi><mi id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.3.3" xref="S2.SS2.SSS1.p1.3.m3.3.3.3.3.3.3.3.cmml">T</mi></msub></mrow><mo id="S2.SS2.SSS1.p1.3.m3.3.3.3.3.7" stretchy="false" xref="

|  | <math alttext="y_{t}\sim P(y_{t}&#124;Y_{t-1},X_{T})=softmax(w_{o}\cdot h_{t})" class="ltx_Math" display="block" id="S2.E2.m1.2"><semantics id="S2.E2.m1.2a"><mrow id="S2.E2.m1.2.2" xref="S2.E2.m1.2.2.cmml"><msub id="S2.E2.m1.2.2.4" xref="S2.E2.m1.2.2.4.cmml"><mi id="S2.E2.m1.2.2.4.2" xref="S2.E2.m1.2.2.4.2.cmml">y</mi><mi id="S2.E2.m1.2.2.4.3" xref="S2.E2.m1.2.2.4.3.cmml">t</mi></msub><mo id="S2.E2.m1.2.2.5" xref="S2.E2.m1.2.2.5.cmml">∼</mo><mrow id="S2.E2.m1.1.1.1" xref="S2.E2.m1.1.1.1.cmml"><mi id="S2.E2.m1.1.1.1.3" xref="S2.E2.m1.1.1.1.3.cmml">P</mi><mo id="S2.E2.m1.1.1.1.2" xref="S2.E2.m1.1.1.1.2.cmml">⁢</mo><mrow id="S2.E2.m1.1.1.1.1.1" xref="S2.E2.m1.1.1.1.1.1.1.cmml"><mo id="S2.E2.m1.1.1.1.1.1.2" stretchy="false" xref="S2.E2.m1.1.1.1.1.1.1.cmml">(</mo><mrow id="S2.E2.m1.1.1.1.1.1.1" xref="S2.E2.m1.1.1.1.1.1.1.cmml"><msub id="S2.E2.m1.1.1.1.1.1.1.4" xref="S2.E2.m1.1.1.1.1.1.1.4.cmml"><mi id="S2.E2.m1.1.1.1.1.1.1.4.2" xref="S2.E2.m1.1.1.1.1.1.1.4.2.cmml">y</mi><mi id="S2.E2.m1.1.1.1.1.1.1.4.3" xref="S2.E2.m1.1.1.1.1.1.1.4.3.cmml">t</mi></msub><mo fence="false" id="S2.E2.m1.1.1.1.1.1.1.3" xref="S2.E2.m1.1.1.1.1.1.1.3.cmml">&#124;</mo><mrow id="S2.E2.m1.1.1.1.1.1.1.2.2" xref="S2.E2.m1.1.1.1.1.1.1.2.3.cmml"><msub id="S2.E2.m1.1.1.1.1.1.1.1.1.1" xref="S2.E2.m1.1.1.1.1.1.1.1.1.1.cmml"><mi id="S2.E2.m1.1.1.1.1.1.1.1.1.1.2" xref="S2.E2.m1.1.1.1.1.1.1.1.1.1.2.cmml">Y</mi><mrow id="S2.E2.m1.1.1.1.1.1.1.1.1.1.3" xref="S2.E2.m1.1.1.1.1.1.1.1.1.1.3.cmml"><mi id="S2.E2.m1.1.1.1.1.1.1.1.1.1.3.2" xref="S2.E2.m1.1.1.1.1.1.1.1.1.1.3.2.cmml">t</mi><mo id="S2.E2.m1.1.1.1.1.1.1.1.1.1.3.1" xref="S2.E2.m1.1.1.1.1.1.1.1.1.1.3.1.cmml">−</mo><mn id="S2.E2.m1.1.1.1.1.1.1.1.1.1.3.3" xref="S2.E2.m1.1.1.1.1.1.1.1.1.1.3.3.cmml">1</mn></mrow></msub><mo id="S2.E2.m1.1.1.1.1.1.1.2.2.3" xref="S2.E2.m1.1.1.1.1.1.1.2.3.cmml">,</mo><msub id="S2.E2.m1.1.1.1.1.1.1.2.2.2" xref="S2.E2.m1.1.1.1.1.1.1.2.2.2.cmml"><mi id="S2.E2.m1.1.1.1.1.1.1.2.2.2.2" xref="S2.E2.m1.1.1.1.1.1.1.2.2.2.2.cmml">X</mi><mi id="S2.E2.m1.1.1.1.1.1.1.2.2.2.3" xref="S2.E2.m1.1.1.1.1.1.1.2.2.2.3.cmml">T</mi></msub></mrow></mrow><mo id="S2.E2.m1.1.1.1.1.1.3" stretchy="false" xref="S2.E2.m1.1.1.1.1.1.1.cmml">)</mo></mrow></mrow></mrow><annotation-xml encoding="MathML-Content" id="S2.E2.m1.2b"><apply id="S2.E2.m1.2.2.cmml" xref="S2.E2.m1.2.2"><apply id="S2.E2.m1.2.2b.cmml" xref="S2.E2.m1.2.2"><csymbol cd="latexml" id="S2.E2.m1.2.2.5.cmml" xref="S2.E2.m1.2.2.5">similar-to</csymbol><apply id="S2.E2.m1.2.2.4.cmml" xref="S2.E2.m1.2.2.4"><csymbol cd="ambiguous" id="S2.E2.m1.2.2.4.1.cmml" xref="S2.E2.m1.2.2.4">subscript</csymbol><ci id="S2.E2.m1.2.2.4.2.cmml" xref="S2.E2.m1.2.2.4.2">𝑦</ci><ci id="S2.E2.m1.2.2.4.3.cmml" xref="S2.E2.m1.2.2.4.3">𝑡</ci></apply><apply id="S2.E2.m1.1.1.1.cmml" xref="S2.E2.m1.1.1.1"><ci id="S2.E2.m1.1.1.1.3.cmml" xref="S2.E2.m1.1.1.1.3">𝑃</ci><apply id="S2.E2.m1.1.1.1.1.1.1.cmml" xref="S2.E2.m1.1.1.1.1.1"><csymbol cd="latexml" id="S2.E2.m1.1.1.1.1.1.1.3.cmml" xref="S2.E2.m1.1.1.1.1.1.1.3">conditional</csymbol><apply id="S2.E2.m1.1.1. |
| --- | --- |

`<math alttext="h_{t}" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p2.1.m1.1"><semantics id="S2.SS2.SSS1.p2.1.m1.1a"><msub id="S2.SS2.SSS1.p2.1.m1.1.1" xref="S2.SS2.SSS1.p2.1.m1.1.1.cmml"><mi id="S2.SS2.SSS1.p2.1.m1.1.1.2" xref="S2.SS2.SSS1.p2.1.m1.1.1.2.cmml">h</mi><mi id="S2.SS2.SSS1.p2.1.m1.1.1.3" xref="S2.SS2.SSS1.p2.1.m1.1.1.3.cmml">t</mi></msub><annotation-xml encoding="MathML-Content" id="S2.SS2.SSS1.p2.1.m1.1b"><apply id="S2.SS2.SSS1.p2.1.m1.1.1.cmml" xref="S2.SS2.SSS1.p2.1.m1.1.1"><csymbol cd="ambiguous" id="S2.SS2.SSS1.p2.1.m1.1.1.1.cmml" xref="S2.SS2.SSS1.p2.1.m1.1.1">subscript</csymbol><ci id="S2.SS2.SSS1.p2.1.m1.1.1.2.cmml" xref="S2.SS2.SSS1.p2.1.m1.1.1.2">ℎ</ci><ci id="S2.SS2.SSS1.p2.1.m1.1.1.3.cmml" xref="S2.SS2.SSS1.p2.1.m1.1.1.3">𝑡</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S2.SS2.SSS1.p2.1.m1.1c">h_{t}</annotation><annotation encoding="application/x-llamapun" id="S2.SS2.SSS1.p2.1.m1.1d">italic_h start_POSTSUBSCRIPT italic_t end_POSTSUBSCRIPT</annotation></semantics></math>` 是模型在时间步 `<math alttext="t" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p2.2.m2.1"><semantics id="S2.SS2.SSS1.p2.2.m2.1a"><mi id="S2.SS2.SSS1.p2.2.m2.1.1" xref="S2.SS2.SSS1.p2.2.m2.1.1.cmml">t</mi><annotation-xml encoding="MathML-Content" id="S2.SS2.SSS1.p2.2.m2.1b"><ci id="S2.SS2.SSS1.p2.2.m2.1.1.cmml" xref="S2.SS2.SSS1.p2.2.m2.1.1">𝑡</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.SS2.SSS1.p2.2.m2.1c">t</annotation><annotation encoding="application/x-llamapun" id="S2.SS2.SSS1.p2.2.m2.1d">italic_t</annotation></semantics></math>` 的隐藏状态，`<math alttext="w_{o}" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p2.3.m3.1"><semantics id="S2.SS2.SSS1.p2.3.m3.1a"><msub id="S2.SS2.SSS1.p2.3.m3.1.1" xref="S2.SS2.SSS1.p2.3.m3.1.1.cmml"><mi id="S2.SS2.SSS1.p2.3.m3.1.1.2" xref="S2.SS2.SSS1.p2.3.m3.1.1.2.cmml">w</mi><mi id="S2.SS2.SSS1.p2.3.m3.1.1.3" xref="S2.SS2.SSS1.p2.3.m3.1.1.3.cmml">o</mi></msub><annotation-xml encoding="MathML-Content" id="S2.SS2.SSS1.p2.3.m3.1b"><apply id="S2.SS2.SSS1.p2.3.m3.1.1.cmml" xref="S2.SS2.SSS1.p2.3.m3.1.1"><csymbol cd="ambiguous" id="S2.SS2.SSS1.p2.3.m3.1.1.1.cmml" xref="S2.SS2.SSS1.p2.3.m3.1.1">subscript</csymbol><ci id="S2.SS2.SSS1.p2.3.m3.1.1.2.cmml" xref="S2.SS2.SSS1.p2.3.m3.1.1.2">𝑤</ci><ci id="S2.SS2.SSS1.p2.3.m3.1.1.3.cmml" xref="S2.SS2.SSS1.p2.3.m3.1.1.3">𝑜</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S2.SS2.SSS1.p2.3.m3.1c">w_{o}</annotation><annotation encoding="application/x-llamapun" id="S2.SS2.SSS1.p2.3.m3.1d">italic_w start_POSTSUBSCRIPT italic_o end_POSTSUBSCRIPT</annotation></semantics></math>` 是输出矩阵，使用 softmax 函数来获取词汇表的概率分布，`<math alttext="y_{t}" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p2.4.m4.1"><semantics id="S2.SS2.SSS1.p2.4.m4.1a"><msub id="S2.SS2.SSS1.p2.4.m4.1.1" xref="S2.SS2.SSS1.p2.4.m4.1.1.cmml"><mi id="S2.SS2.SSS1.p2.4.m4.1.1.2" xref="S2.SS2.SSS1.p2.4.m4.1.1.2.cmml">y</mi><mi id="S2.SS2.SSS1.p2.4.m4.1.1.3" xref="S2.SS2.SSS1.p2.4.m4.1.1.3.cmml">t</mi></msub><annotation-xml encoding="MathML-Content" id="S2.SS2.SSS1.p2.4.m4.1b"><apply id="S2.SS2.SSS1.p2.4.m4.1.1.cmml" xref="S2.SS2.SSS1.p2.4.m4.1.1"><csymbol cd="ambiguous" id="S2.SS2.SSS1.p2.4.m4.1.1.1.cmml" xref="S2.SS2.SSS1.p2.4.m4.1.1">subscript</csymbol><ci id="S2.SS2.SSS1.p2.4.m4.1.1.2.cmml" xref="S2.SS2.SSS1.p2.4.m4.1.1.2">𝑦</ci><ci id="S2.SS2.SSS1.p2.4.m4.1.1.3.cmml" xref="S2.SS2.SSS1.p2.4.m4.1.1.3">𝑡</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S2.SS2.SSS1.p2.4.m4.1c">y_{t}</annotation><annotation encoding="application/x-llamapun" id="S2.SS2.SSS1.p2.4.m4.1d">italic_y start_POSTSUBSCRIPT italic_t end_POSTSUBSCRIPT</annotation></semantics></math>` 是从词汇表概率分布中采样的，`<math alttext="P(y_{t}|Y_{t-1},X_{T})" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p2.5.m5.1"><semantics id="S2.SS2.SSS1

| `Y_{T}=\{y_{1},y_{2},...,y_{T}\}` |
| --- |

解码文本的质量与选择的解码策略密切相关。鉴于模型是按顺序构建文本的，生成文本的质量取决于用于从词汇表中选择后续词的方法，也就是如何从词汇的概率分布中抽取<math alttext="y_{t}" class="ltx_Math" display="inline" id="S2.SS2.SSS1.p4.1.m1.1"><semantics id="S2.SS2.SSS1.p4.1.m1.1a"><msub id="S2.SS2.SSS1.p4.1.m1.1.1" xref="S2.SS2.SSS1.p4.1.m1.1.1.cmml"><mi id="S2.SS2.SSS1.p4.1.m1.1.1.2" xref="S2.SS2.SSS1.p4.1.m1.1.1.2.cmml">y</mi><mi id="S2.SS2.SSS1.p4.1.m1.1.1.3" xref="S2.SS2.SSS1.p4.1.m1.1.1.3.cmml">t</mi></msub><annotation-xml encoding="MathML-Content" id="S2.SS2.SSS1.p4.1.m1.1b"><apply id="S2.SS2.SSS1.p4.1.m1.1.1.cmml" xref="S2.SS2.SSS1.p4.1.m1.1.1"><csymbol cd="ambiguous" id="S2.SS2.SSS1.p4.1.m1.1.1.1.cmml" xref="S2.SS2.SSS1.p4.1.m1.1.1">subscript</csymbol><ci id="S2.SS2.SSS1.p4.1.m1.1.1.2.cmml" xref="S2.SS2.SSS1.p4.1.m1.1.1.2">𝑦</ci><ci id="S2.SS2.SSS1.p4.1.m1.1.1.3.cmml" xref="S2.SS2.SSS1.p4.1.m1.1.1.3">𝑡</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S2.SS2.SSS1.p4.1.m1.1c">y_{t}</annotation><annotation encoding="application/x-llamapun" id="S2.SS2.SSS1.p4.1.m1.1d">italic_y start_POSTSUBSCRIPT italic_t end_POSTSUBSCRIPT</annotation></semantics></math>。主导的解码技术包括贪婪搜索、波束搜索、top-k 抽样和 top-p 抽样。[Table 2](https://arxiv.org/html/2310.14724v3#S2.T2 "Table 2 ‣ 2.2.1 Generation Mechanisms of LLMs ‣ 2.2 LLMs Text Generation and Confusion Sources ‣ 2 Background ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")比较了这些解码方法的基本原理，以及各自的优点和缺点。这种比较有助于阐明 LLMs 的文本生成过程以及它们产生的特定特征。

表 2：不同文本解码策略的核心思想及其优缺点。贪心搜索使用简单的贪心策略，每一步只考虑当前概率最高的词，简单且快速，但缺乏多样性。束搜索允许在每一步考虑多个候选词，这提高了文本质量，但往往会生成重复的内容。Top-K 采样增加了多样性，但难以控制生成质量。Top-P 采样依赖于概率分布的形状来确定采样词的集合，这样生成的文本连贯，但多样性与参数<math alttext="P" class="ltx_Math" display="inline" id="S2.T2.2.m1.1"><semantics id="S2.T2.2.m1.1b"><mi id="S2.T2.2.m1.1.1" xref="S2.T2.2.m1.1.1.cmml">P</mi><annotation-xml encoding="MathML-Content" id="S2.T2.2.m1.1c"><ci id="S2.T2.2.m1.1.1.cmml" xref="S2.T2.2.m1.1.1">𝑃</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.T2.2.m1.1d">P</annotation><annotation encoding="application/x-llamapun" id="S2.T2.2.m1.1e">italic_P</annotation></semantics></math>相关。 |

| 策略 | 核心思想 | 优势 | 缺点 |
| --- | --- | --- | --- |
| 贪心搜索 | 每一步只考虑当前概率最高的词。 | 快速且简单。 | 易陷入局部最优，缺乏多样性，无法处理不确定性。 |
| 束搜索 Graves ([2012](https://arxiv.org/html/2310.14724v3#bib.bib76)) | 在每一步可以考虑更多的候选词。 | 提高了文本质量和灵活性。 | 易生成重复的片段，开放生成领域效果差，无法处理不确定性。 |
| Top-K Sampling Fan, Lewis, and Dauphin ([2018](https://arxiv.org/html/2310.14724v3#bib.bib62)) | 在每一步中从 K 个最可能的词中进行采样。 | 增加多样性，并能够处理不确定性。 | 难以控制生成的质量，可能导致文本不连贯。 |
| Top-P Sampling Holtzman et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib87)) | 使用概率分布的形状来确定采样的词集合 | 连贯性和处理不确定性的能力。 | 依赖于模型预测的质量，多样性与参数<math alttext="P" class="ltx_Math" display="inline" id="S2.T2.3.1.1.1.1.1.m1.1"><semantics id="S2.T2.3.1.1.1.1.1.m1.1a"><mi id="S2.T2.3.1.1.1.1.1.m1.1.1" xref="S2.T2.3.1.1.1.1.1.m1.1.1.cmml">P</mi><annotation-xml encoding="MathML-Content" id="S2.T2.3.1.1.1.1.1.m1.1b"><ci id="S2.T2.3.1.1.1.1.1.m1.1.1.cmml" xref="S2.T2.3.1.1.1.1.1.m1.1.1">𝑃</ci></annotation-xml><annotation encoding="application/x-tex" id="S2.T2.3.1.1.1.1.1.m1.1c">P</annotation><annotation encoding="application/x-llamapun" id="S2.T2.3.1.1.1.1.1.m1.1d">italic_P</annotation></semantics></math>相关。 |

#### 2.2.2 LLM 强大生成能力的来源

模型大小、数据量和计算能力的不断增长显著提高了 LLMs 的能力。超出特定模型大小后，存在一些能力，这些能力不能通过缩放定律进行预测。这些能力在较小的模型中不存在，但在 LLMs 中明显存在，被称为 LLMs 的“新兴能力”。

##### 上下文学习（ICL）

ICL 能力的起源仍是一个持续争论的话题 Dai 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib47)）。然而，这种能力引入了一个范式，模型参数保持不变，只有提示的设计被修改以引起 LLMs 的期望输出。这个概念最初是在 GPT-3 中介绍的 Brown 等人（[2020](https://arxiv.org/html/2310.14724v3#bib.bib25)）。Brown 等人（[2020](https://arxiv.org/html/2310.14724v3#bib.bib25)）认为 ICL 的存在对 LLMs 在各种任务中的快速适应性至关重要。只需要一些例子，LLMs 就可以有效地应对下游任务，避免了先前依赖预训练后调整特定任务的 BERT 模型方法 Raffel 等人（[2020](https://arxiv.org/html/2310.14724v3#bib.bib175)）。

##### 人类偏好的一致性

尽管 LLMs 可以通过精心设计的提示来生成内容，但生成的文本可能缺乏控制，可能导致产生误导性或偏见内容 Zhang 等人（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib256)）。这些模型的主要关注点在于基于大量语料库预测后续单词以形成连贯的句子，而不是确保生成的内容对人类有益且无害。为了解决这些缺点，OpenAI 引入了从人类反馈中进行强化学习（RLHF）方法，详见 Ouyang 等人（[2022](https://arxiv.org/html/2310.14724v3#bib.bib162)）和 Lambert 等人（[2022](https://arxiv.org/html/2310.14724v3#bib.bib112)）。该方法首先通过使用用户定向测验的数据来微调 LLMs，然后通过人类评估员评估模型的输出。同时，建立了一个奖励函数，并使用 Proximal Policy Optimization（PPO）算法进一步改进 LLM Schulman 等人（[2017a](https://arxiv.org/html/2310.14724v3#bib.bib187)）。最终的结果是一个与人类价值观一致的模型，理解人类指令，并真正帮助用户。

##### 复杂的推理能力

尽管 LLM 的 ICL 和对齐能力促进了有意义的互动和帮助，但它们在需要逻辑推理和高度复杂性的任务中的表现往往会下降。Wei 等人 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib231)) 观察到，通过思维链 (CoT) 鼓励 LLM 生成更多的中间步骤可以提高其有效性。思维树 (ToT) Yao 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib246)) 和思维图 (GoT) Besta 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib20)) 是这种方法的扩展。这两种策略通过增加模型推导答案所需的计算努力来提高 LLM 在复杂任务中的表现。

### 2.3 我们为什么需要检测由 LLM 生成的文本？

随着 LLM 经过迭代改进和通过人类反馈进行强化学习，它们的输出越来越与人类的价值观和偏好相一致。这种对齐促进了 LLM 生成文本的更广泛接受和融入日常生活。各种 AI 工具的出现在促进直观的人机交互和将以前晦涩模型的先进能力民主化方面发挥了重要作用。从像 ChatGPT ¹¹1[`chat.openai.com/`](https://chat.openai.com/)这样的互动网页助手，到增强了 LLM 技术的搜索引擎，如现代版 Bing ²²2[`www.bing.com/`](https://www.bing.com/)，再到像 Coplit ³³3[`github.com/features/copilot/`](https://github.com/features/copilot/) 和 Scispeace⁴⁴4[`typeset.io/`](https://typeset.io/)这样的专业工具，这些工具帮助专业人员进行代码生成和科学研究，LLM 已经 subtly 融入了我们生活的数字网络中，将其内容传播到各种平台。

然而，重要的是要认识到，对于大多数用户来说，LLM 及其应用仍然被视为黑箱 AI 系统。对于个人用户来说，这通常作为一种良性的效率提升，避免了繁琐的信息检索和总结。然而，在特定的背景下和更广泛的数字环境中，识别、过滤甚至排除 LLM 生成的文本变得至关重要。需要强调的是，并非所有情况都需要检测 LLM 生成的文本。不必要的检测可能导致系统效率低下和开发成本增加。通常情况下，当以下情况出现时，检测 LLM 生成的文本可能是不必要的：

+   •

    LLM 的使用风险较小，尤其是当它们处理常规、可重复的任务时。

+   •

    LLM 生成的文本传播被限制在可预测的、有限的领域内，如参与者较少的封闭信息圈。

基于本研究中回顾的文献，LLM 生成文本检测的合理性可以从多个角度进行阐述，如[图 2](https://arxiv.org/html/2310.14724v3#S2.F2 "Figure 2 ‣ 2.3 Why Do We Need to Detect Text Generated by LLMs? ‣ 2 Background ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")所示。这些划分的视角在一定程度上受到 Gade 等人（[2020](https://arxiv.org/html/2310.14724v3#bib.bib64)）和 Saeed 与 Omlin（[2023](https://arxiv.org/html/2310.14724v3#bib.bib182)）所呈现的见解的启发。

图 2：为什么急需 LLM 生成文本检测的最关键原因。我们从五个角度进行了讨论：监管、用户、发展、科学和人类社会。

尽管上述列表可能不是详尽无遗的，并且随着 LLM 和 AI 系统的发展，一些方面可能会交叉或进一步界定，但我们认为这些要点突显了检测 LLM 生成文本的必要性。

##### 监管

作为常被称为黑箱的 AI 工具，LLM 生成文本在创意工作中的使用引发了重大法律问题。一个迫切的担忧是 LLM 生成文本是否有资格获得知识产权保护，这一主题仍然充满争论，Epstein 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib59)）；维基百科（[2023](https://arxiv.org/html/2310.14724v3#bib.bib234)），尽管*欧盟人工智能法案*⁵⁵5[`artificialintelligenceact.eu/the-act/`](https://artificialintelligenceact.eu/the-act/)已经开始不断改进，以规范 AI 的使用。主要挑战来自于如 AI 生成输出所用训练数据的所有权问题，以及如何确定多少人类参与才能使其成为他们的作品。AI 监督和 AI 生成内容的版权保护前提是能区分用于训练 AI 系统的材料中的人类创造力，从而进一步促进更完善的法律监管实施。

##### 用户

通过各种对齐方法精炼的 LLM 生成文本，正逐渐与人类的偏好对齐。这些内容渗透到许多用户可访问的平台，包括博客和问答论坛。然而，过度依赖这些内容可能会削弱用户对 AI 系统以及整个数字内容的信任。在这种情况下，LLM 生成文本检测的角色变得至关重要，作为监管 LLM 生成文本在网上普及程度的门卫。

##### 发展

随着 LLM 技术的不断进步，Li et al. ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib119)) 提出 LLM 可以自我评估甚至基准测试其自身表现。由于其出色的文本生成性能，LLM 还被用于通过预设指令构建许多训练数据集（Taori et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib208))）。然而，Alemohammad et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib3)) 认为这种“自我消耗”范式可能导致 LLM 生成文本的同质化，可能最终导致所谓的“LLM 自噬障碍”（MAD）。如果 LLM 严重依赖网络来源的数据进行训练，并且这些数据中的一大部分来源于 LLM 的输出，这可能会阻碍其长期进步。

##### 科学

人类进步的无尽步伐在很大程度上归功于科学探索和发现的精神。然而，LLM 生成文本在学术写作中的日益增加（Májovskỳ et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib140))）以及 LLM 起源设计在研究中的应用，引发了关于可能稀释人类独创性和探索驱动的担忧。同时，这也可能削弱高等教育验证学生知识和理解能力的能力，并降低特定高等教育机构的学术声誉（Ibrahim et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib91))）。尽管当前的方法可能存在局限性，但检测能力的进一步提升将加强学术诚信，并在科学研究中维护人类独立思考的能力。

##### 人类社会

从社会角度分析，LLM 生成文本的影响表明，这些模型本质上在预测后续标记时模拟特定的文本模式。如果使用不当，这些模型可能会减少语言多样性，并促成社会话语中的信息孤岛形成。从长远来看，检测和过滤 LLM 生成的文本对于保持人类沟通的丰富性和多样性至关重要，无论是语言上还是信息上。

## 3 相关工作与我们的调查

### 3.1 相关工作

Beresneva 的全面综述文章（[2016](https://arxiv.org/html/2310.14724v3#bib.bib19)）代表了第一次对计算机生成文本检测方法的广泛调查。那时，检测过程相对简单，主要集中在机器翻译文本检测上，并采用简单的统计方法进行检测。自回归模型的出现显著增加了文本检测任务的复杂性。Jawahar、Abdul-Mageed 和 Lakshmanan（[2020](https://arxiv.org/html/2310.14724v3#bib.bib93)）提供了关于机器生成文本检测的详细调查，为该领域建立了基础背景，重点介绍了当时流行的 SOTA 生成模型，如 GPT-2。ChatGPT 的随后发布引发了对 LLM 的广泛兴趣，并标志着研究方向的重大转变。为了应对 LLM 生成文本带来的快速挑战，NLP 社区最近开展了广泛的研究，以制定强大的检测机制并探索检测规避技术的动态，旨在寻找有效的解决方案。Crothers、Japkowicz 和 Viktor（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib44)）；Dhaini、Poelman 和 Erdogan（[2023](https://arxiv.org/html/2310.14724v3#bib.bib54)）的近期调查提供了 LLM 生成文本检测的新评述，但我们认为这些综述还不够先进，检测方法的总结需要改进。Tang、Chuang 和 Hu（[2023](https://arxiv.org/html/2310.14724v3#bib.bib206)）提供了另一项调查，将检测方法分为黑箱检测和白箱检测，并突出了水印等前沿技术，但该综述可以通过更全面的分析和批判性评估得到改善。Ghosal 等（[2023](https://arxiv.org/html/2310.14724v3#bib.bib72)）讨论了当前的 AI 生成文本检测器攻击和防御，并提供了详细的归纳分析。然而，讨论可以通过对任务动机、数据资源和评估方法的更详细审查得到丰富。

在本文中，我们力求提供对 LLM 生成文本检测最新研究的更全面和有洞察力的综述，并进行了深思熟虑的分析。我们突出了我们的综述与其他综述的优点：

+   •

    系统性和全面性的综述：我们的调查提供了对 LLM 生成文本检测的广泛探索，涵盖了任务的描述及其背后的动机、基准和数据集、各种检测和攻击方法、评估框架、当前面临的最紧迫挑战、潜在的未来方向以及对每个方面的批判性审视。

+   •

    **深入分析检测机制**：我们提供了从传统方法到最新研究的检测策略的详细概述，并在当前 LLMs 环境下**系统评估**了它们的有效性、优点和缺点。

+   •

    更具实践性的见解。我们的讨论**深入探讨**了具有实际意义的研究问题，例如模型大小如何影响检测能力、识别不完全由 LLMs 生成的文本的挑战以及缺乏有效的评估框架。

总之，我们坚信这项综述比现有工作更具系统性和全面性。更重要的是，我们的批判性讨论不仅为新研究者提供了指导，还对该领域的已建立工作提供了有价值的见解。

### 3.2 系统性调查与实施

表 3：概述了我们研究中使用的各种数据库和搜索引擎，以及所采用的搜索方案和获得的结果。Google Scholar 作为检索文献最多的搜索引擎占据主导地位。经过仔细检查，我们发现大量文献来源于 ArXiv，主要由研究人员共享。

| 数据库 | 搜索引擎 | 搜索方案 | 检索结果 |
| --- | --- | --- | --- |
| Google Scholar | [`scholar.google.com/`](https://scholar.google.com/) | 全文 | 210 |
| ArXiv | [`arxiv.org/`](https://arxiv.org/) | 全文 | N/A^a |
| Scopus | [`www.scopus.com/`](https://www.scopus.com/) | TITLE-ABS-KEY: (标题, 摘要, 作者关键词, 索引关键词) | 133 |
| Web of Science | [`www.webofscience.com/`](https://www.webofscience.com/) | 主题: (检索标题, 摘要, 作者关键词, 关键词加) | 92 |
| IEEE Xplore | [`ieeexplore.ieee.org/`](https://ieeexplore.ieee.org/) | 全文 | 49 |
| Springer Link | [`link.springer.com/`](https://link.springer.com/) | 全文 | N/A^a |
| ACL Anthology | [`aclanthology.org/`](https://aclanthology.org/) | 全文 | N/A^a |
| ACM Digital Library | [`dl.acm.org/`](https://dl.acm.org/) | 标题 | N/A^b |

\tabnote

^a 搜索引擎无法在单次搜索字符串中使用所有关键词。因此，检索结果不准确，可能会有重复的论文查询结果。 \tabnote^b 搜索引擎检索到了与我们主题关联度较弱的论文数量。

我们的调查采用了由 Barbara Kitchenham ([2007](https://arxiv.org/html/2310.14724v3#bib.bib17)) 描述的文献综述系统（SLR），这是一个用于评估与特定研究问题或主题相关的现有证据的范围和质量的方法框架。与传统的文献综述相比，这种方法提供了更广泛和准确的见解，在许多学术调查中得到了显著应用，正如 Murtaza 等人 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib157)) 和 Saeed 与 Omlin ([2023](https://arxiv.org/html/2310.14724v3#bib.bib182)) 所证明的那样。指导我们 SLR 的研究问题如下：

*检测 LLM 生成文本的* 主要方法是什么，以及与这些方法相关的*主要挑战*是什么？

<svg class="ltx_picture ltx_centering" height="273.49" id="S3.F3.pic1" overflow="visible" version="1.1" width="315.23"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,273.49) matrix(1 0 0 -1 0 0) translate(45.14,0) translate(0,43.28) matrix(1.0 0.0 0.0 1.0 -45.14 -43.28)"><g class="ltx_nestedsvg" transform="matrix(1 0 0 1 0 0) translate(76.27,0) translate(0,43.28)"><g fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -13.84 -19.71)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="27.67">2019</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 38.05 -19.71)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="27.67">2020</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 89.94 -19.71)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="27.67">2021</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 141.83 -19.71)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="27.67">2022</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 193.72 -19.71)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="27.67">2023</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -42.94 -4.46)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92"><math alttext="0" class="ltx_Math" display="inline" id="S3.F3.pic1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.m1.1"><semantics id="S3.F3.pic1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.m1.1a"><mn id="S3.F3.pic1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.m1.1.1" xref="S3.F3.pic1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.m1.1.1.cmml">0</mn><annotation-xml encoding="MathML-Content" id="S3.F3.pic1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.m1.1b"><cn id="S3.F3.pic1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.m1.1.1.cmml" type="integer" xref="S3.F3.pic1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.1.m1.1.1">0</cn></annotation-xml></semantics></math></foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -49.86 65.81)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84"><math alttext="20" class="ltx_Math" display="inline" id="S3.F3.pic1.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.1.1.1.1.1.1.1.1.1.m1.1"><semantics id="S3.F3.pic1.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.1.1.1.1.1.1.1.1.1.m1.1a"><mn id="S3.F3.pic1.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.1.1.1.1.1.1.1.1.1.m1.1.1" xref="S3.F3.pic1.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.1.1.1.1.1.1.1.1.1.m1.1.1.cmml">20</mn><annotation-xml encoding="MathML-Content" id="S3.F3.pic1.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.1.1.1.1.1.1.1.1.1.m1.1b"><cn id="S3.F3.pic1.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.1.1.1.1.1.1.1.1.1.m1.1.1.cmml" type="integer" xref="S3.F3.pic1.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.2.1.1.1.1.1.1.1.1.

图 3：绘制了从筛选中获得的过去 5 年的文献按年份分布图。2023 年发表的文章数量引起了显著关注。

在描述研究问题后，我们的研究使用了与研究问题直接相关的搜索词，具体包括：“LLM 生成文本检测”，“机器生成文本检测”，“AI 写作文本检测”，“作者归属”，以及“深伪文本检测”。这些术语通过布尔运算符 OR 进行策略性组合，形成以下搜索字符串：（“LLM 生成文本检测” OR “机器生成文本检测” OR “AI 写作文本检测” OR “作者归属” OR “深伪文本检测”）。随后，利用这一搜索字符串，我们在相关和权威的电子论文数据库和搜索引擎中进行了初步检索。我们的调查主要集中在 2023 年 11 月之前公开访问的学术文章上。[表 3](https://arxiv.org/html/2310.14724v3#S3.T3 "Table 3 ‣ 3.2 Systematic Investigation and Implementation ‣ 3 Related Works and Our Investigation ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions") 概述了使用的来源并提供了我们的结果概况。

随后，我们建立了以下标准来审查收集的文章：

+   •

    文章应为综述，重点关注 LLM 生成（机器生成/AI 写作）文本检测的方法和挑战。

+   •

    文章应提出一种专门设计用于检测 LLM 生成（机器生成/AI 写作）文本的方法论。

+   •

    文章应描述文本生成领域面临的挑战和未来研究的前景。

+   •

    文章应阐明 LLM 生成文本检测的必要性和应用。

如果满足上述四个标准中的任何一个，则该工作被认为对我们的研究有价值。经过去重和人工筛选，我们识别出 83 篇相关文献。这些工作的年度分布趋势在[图 3](https://arxiv.org/html/2310.14724v3#S3.F3 "Figure 3 ‣ 3.2 Systematic Investigation and Implementation ‣ 3 Related Works and Our Investigation ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")中进行了说明。值得注意的是，大多数相关研究是在 2023 年发表的（如[图 3](https://arxiv.org/html/2310.14724v3#S3.F3 "Figure 3 ‣ 3.2 Systematic Investigation and Implementation ‣ 3 Related Works and Our Investigation ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")所示），突显了该领域的蓬勃发展，并强调了我们研究的重要性。在随后的部分中，我们提供了数据的综合分析（见[第四部分](https://arxiv.org/html/2310.14724v3#S4 "4 Data ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")）、主要检测器（见[第五部分](https://arxiv.org/html/2310.14724v3#S5 "5 Advances in Detector Research ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")）、评估指标（见[第六部分](https://arxiv.org/html/2310.14724v3#S6 "6 Evaluation Metrics ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")）、问题（见[第七部分](https://arxiv.org/html/2310.14724v3#S7 "7 Important Issues of LLM-generated Text Detection ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")）和未来研究方向（见[第八部分](https://arxiv.org/html/2310.14724v3#S8 "8 Future Research Directions ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")），均涉及 LLM 生成文本检测。调查的全面结构概述见[表 4](https://arxiv.org/html/2310.14724v3#S3.T4 "Table 4 ‣ 3.2 Systematic Investigation and Implementation ‣ 3 Related Works and Our Investigation ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")，提供了我们审阅组织的详细概述。

表 4：本调查内容组织的总结。

| 节 | 主题 | 内容 |
| --- | --- | --- |
| 第四部分 | 数据 | 用于 LLM 生成文本检测的数据集和基准，其他易于扩展到检测任务的数据集及 LLM 生成文本检测数据集的挑战。 |
| 第五部分 | 检测器 | 水印技术、基于统计的检测器、基于神经网络的检测器和人工辅助方法 |
| 章节 6 | 评估指标 | 准确率，精确率，召回率，假阳性率，真阴性率，假阴性率，F1 分数和 ROC 曲线下面积（AUROC）。 |
| 章节 7 | 问题 | 分布范围外挑战，潜在攻击，现实世界数据问题，模型大小对检测器的影响，缺乏有效的评估框架 |
| 章节 8 | 未来方向 | 构建抵御攻击的稳健检测器，增强零样本检测器的效果，优化低资源环境下的检测器，非纯 LLM 生成文本的检测，数据歧义中构建检测器，与现实世界相符合的有效评估框架，具有辨别错误信息能力的检测器的构建。 |
| 章节 9 | 结论 | - |

## 4 数据

高质量的数据集对于推进 LLM 生成文本检测任务的研究至关重要。这些数据集使研究人员能够迅速开发和校准高效的检测器，并建立用于评估其方法效果的标准化指标。然而，获取这样高质量的标记数据往往需要大量的财务、物质和人力资源。目前，针对检测 LLM 生成文本的数据集的开发还处于起步阶段，面临着诸如有限的数据量和样本复杂性等问题，这两者对于构建稳健的检测器至关重要。在本节中，我们首先介绍了用于训练 LLM 生成文本检测器的常用数据集。另外，我们还突出了来自无关领域或任务的数据集，尽管最初并非用于检测任务，但可以重新用于各种检测场景，这是许多当代检测研究中的一种普遍策略。我们随后介绍了用于验证 LLM 生成文本检测器有效性的基准，这些基准经过精心设计，以从不同角度评估检测器的性能。最后，我们评估了这些训练数据集和基准，确定了 LLM 生成文本检测数据集构建中的当前缺陷和挑战，旨在为未来数据资源的设计提供信息。

### 4.1 训练

#### 4.1.1 检测数据集

大规模且高质量的数据集可以帮助研究人员迅速训练他们的检测器。我们对广泛使用且具有潜力的数据集进行了全面的组织和比较，参见[表 5](https://arxiv.org/html/2310.14724v3#S4.T5 "表 5 ‣ 4.1.1 检测数据集 ‣ 4.1 训练 ‣ 4 数据 ‣ 一项关于 LLM 生成文本检测的调查：必要性、方法和未来方向")。鉴于不同研究关注各种实际问题，我们的目标是通过我们的综合审查工作，为研究人员方便地选择满足其特定需求的高质量数据集。

表 5：LLM 生成文本检测的检测数据集概述。

| 语料库 | 用途 | 人类 | LLMs | LLMs 类型 | 语言 | 攻击 | 领域 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HC3 Guo 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib78)) | 训练 | ~80k | ~43k | ChatGPT | 英语, 中文 | - | 网络文本, 问答, 社交媒体 |
| CHEAT Yu 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib249)) | 训练 | ~15k | ~35k | ChatGPT | 英语 | 改写 | 科学写作 |
| HC3 Plus Su 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib204)) | 训练 验证 测试 | ~95k ~10k ~38k | GPT-3.5-Turbo | 英语, 中文 | 改写 | 新闻写作, 社交媒体 |
| OpenLLMText Chen 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib31)) | 训练, 验证, 测试 | ~52k ~8k ~8k | ~209k ~33k ~33k | ChatGPT, PaLM, LLaMA, GPT2-XL | 英语 | - | 网络文本 |
| GROVER 数据集 Zellers 等人 ([2019b](https://arxiv.org/html/2310.14724v3#bib.bib253)) | 训练 | ~24k | Grover-Mega | 英语 | - | 新闻写作 |
| TweepFake Fagni 等人 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib60)) | 训练 | ~12k | ~12k | GPT-2, RNN, 马尔可夫, LSTM, CharRNN | 英语 | - | 社交媒体 |
| GPT-2 输出数据集⁶⁶6[`github.com/openai/gpt-2-output-dataset`](https://github.com/openai/gpt-2-output-dataset) | 训练 测试 | ~250k ~5k | ~2000k ~40k | GPT-2 (small, medium, large, xl) | 英语 | - | 网络文本 |
| ArguGPT Liu 等人 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib131)) | 训练 验证 测试 | ~6k 700 700 | GPT2-Xl, Text-Babbage-001, Text-Curie-001, Text-Davinci-001, Text-Davinci-002, Text-Davinci-003, GPT-3.5-Turbo | 英语 | - | 科学写作 |
| DeepfakeTextDetect Li 等人 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib120)) | 训练 验证 测试 | ~236k ~56k ~56k | GPT (Text-Davinci-002, Text-Davinci-003, GPT-Turbo-3.5), LLaMA (6B, 13B, 30B, 65B), GLM-130B, FLAN-T5 (small, base, large, xl, xxl), OPT(125M, 350M, 1.3B, 2.7B, 6.7B, 13B, 30B, iml1.3B, iml-30B), T0 (3B, 11B), BLOOM-7B1, GPT-J-6B, GPT-NeoX-20B) | 英语 | 改写 | 社交媒体, 新闻写作, 问答, 故事生成, 理解与推理, 科学写作 |

##### HC3

人类 ChatGPT 比较语料库（HC3）Guo 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib78)）是最早的一些开源项目之一，旨在比较 ChatGPT 生成的文本与人类撰写的文本。它涉及收集人类和 ChatGPT 对相同问题的回答。由于在这一领域的开创性贡献，HC3 语料库已被众多后续研究作为宝贵资源。该语料库提供了英文和中文的语料数据。具体来说，HC3-en 包含 58k 个人类回答和 26k 个 ChatGPT 回答，这些回答源自 24k 个问题，主要来源于 ELI5 数据集、WikiQA 数据集、爬取的维基百科、医学对话数据集和 FiQA 数据集。另一方面，HC3-zh 涵盖了更广泛的领域，包括 22k 个人类回答和 17k 个 ChatGPT 回答。这些数据来自七个来源：WebTextQA、BaikeQA、爬取的百度百科、NLPCC-DBQA 数据集、医学对话数据集、百度 AI Studio 和 LegalQA 数据集。然而，值得注意的是，HC3 数据集存在一些限制，例如用于数据创建的提示缺乏多样性。

##### CHEAT

CHEAT 数据集 Yu 等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib249)）是一个最大的公开可用资源，专注于检测 ChatGPT 生成的虚假学术内容。它包括来自 IEEE Xplore 的人类撰写的学术摘要，平均摘要长度为 163.9 个单词，词汇量为 13 万单词。在 ChatGPT 生成过程之后，数据集包含 15k 个人类撰写的摘要和 35k 个 ChatGPT 生成的总结。为了更好地模拟现实应用，这些输出经过 ChatGPT 的进一步修正和整合。“润色”过程旨在模拟那些可能寻求通过改进文本来绕过抄袭检测的用户，而“融合”则代表用户可能将手动撰写的摘要与 ChatGPT 无缝生成的文本结合，以规避检测机制。然而，CHEAT 数据集的一个限制是其关注于狭窄的学术领域，忽略了跨领域的挑战，这源于其主要数据来源的限制。

##### HC3 Plus

HC3 Plus Su 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib204)) 代表了原始 HC3 数据集的增强版本，引入了一个名为 HC3-SI 的扩展部分。该新部分专门针对需要语义不变性的任务，如摘要生成、翻译和改写，从而扩展了 HC3 的范围。为了编制 HC3-SI 的人工文本语料库，数据来源于多个渠道，包括 CNN/DailyMail 数据集、Xsum、LCSTS、CLUE 基准测试和机器翻译研讨会（WMT）的数据集。同时，LLM 生成的文本使用 GPT-3.5-Turbo 生成。扩展后的英文数据集现在包括 95k 样本的训练集、10k 样本的验证集和 38k 样本的测试集。相比之下，中文数据集包含 42k 个训练样本、4k 个验证样本和 22k 个测试样本。尽管进行了这些扩展，HC3-SI 仍然沿用了 HC3 的数据构建方法，这种方法在一定程度上单一且缺乏多样性，特别是在 LLM 的多样性和生成数据时使用的复杂多变的提示方面。

##### OpenLLMText

OpenLLMText 数据集 Chen 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib31)) 来源于四种 LLMs：GPT-3.5、PaLM、LLaMA-7B 和 GPT2-1B（也称为 GPT-2 Extra Large）。GPT2-1B 的样本来自 OpenAI 公开提供的 GPT-2 输出数据集。GPT-3.5 和 PaLM 的文本生成使用了提示“逐段改写以下段落：[Human_Sample]”，而 LLaMA-7B 通过完成人类样本的前 75 个标记生成文本。该数据集总共包含 344k 个样本，其中 68k 个由人类编写。数据集按 76%、12% 和 12% 划分为训练集、验证集和测试集。值得注意的是，该数据集包含了像 PaLM 这样在日常应用中常用的 LLMs。然而，它并未完全捕捉跨领域和多语言文本的细微差别，这限制了它在相关研究中的有用性。

##### TweepFake 数据集

TweepFake Fagni 等人 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib60)) 是一个基础数据集，旨在分析 Twitter 上的虚假推文，来源于真实和虚假的账户。它包含总计 25k 条推文，其中人类编写和机器生成的样本数量相等。机器生成的推文使用多种技术制作，包括 GPT-2、RNN、Markov、LSTM 和 CharRNN。尽管 TweepFake 继续成为许多学者的首选数据集，但从事 LLM 研究的人应当在考虑技术能力不断发展的背景下，批判性地评估其相关性和严谨性。

##### GPT2-Output 数据集

OpenAI 提出的 GPT2-Output 数据集⁷⁷7[`github.com/openai/gpt-2-output-dataset`](https://github.com/openai/gpt-2-output-dataset) 基于来自 WebText 测试集的 25 万篇文档的人工撰写文本。关于 LLM 生成的文本，该数据集包含 25 万个随机生成的样本，使用 1 的温度设置，无截断，以及另外 25 万个使用 Top-K 40 截断生成的样本。该数据集旨在进一步研究 GPT-2 模型的可检测性。然而，数据集的一个显著限制在于生成模型和数据分布的单一性。

##### GROVER 数据集

由 Zellers 等人（[2019b](https://arxiv.org/html/2310.14724v3#bib.bib253)）介绍的 GROVER 数据集以新闻文章为风格。其人工撰写的文本来自 RealNews，这是一个从 Common Crawl 获得的全面新闻文章语料库。LLM 生成的文本由 Grover-Mega 生成，Grover-Mega 是一个拥有 15 亿参数的基于变换器的新闻生成器。该数据集的一个限制，尤其是在当前的 LLM 领域中，是其生成模型和数据分布的单一性。

##### ArguGPT 数据集

ArguGPT 数据集刘等人（[2023c](https://arxiv.org/html/2310.14724v3#bib.bib131)）专门设计用于检测各种学术环境中生成的 LLM 文本，如课堂练习、托福和 GRE 写作任务。它包含 4 千篇论证性文章，由七种不同的 GPT 模型生成。其主要目的是应对与英语作为第二语言教学相关的独特挑战。

##### DeepfakeTextDetect 数据集

注意到 DeepfakeTextDetect 数据集李等人（[2023c](https://arxiv.org/html/2310.14724v3#bib.bib120)），这是一个针对深度伪造文本检测的强大平台。该数据集结合了来自十个不同数据集的人类撰写文本，包括新闻文章、故事、科学著作等。它包含由 27 个知名 LLM 生成的文本，这些 LLM 来源于 OpenAI、LLaMA 和 EleutherAI。此外，数据集还通过包括 GPT-4 生成的文本和改写文本，增加了额外的挑战。

#### 4.1.2 潜在数据集

从头构建一个同时包含人工书写和 LLM 生成文本的数据集确实是一项资源密集型的工作。鉴于在不同场景中 LLM 生成文本检测的多样化需求，研究人员通常会从问答、学术写作和故事生成等领域适配现有数据集，以代表人工书写的文本。然后，他们使用诸如提示工程和引导补充等方法生成 LLM 生成的文本用于检测器训练。本调查提供了这些数据集的简明分类和概述，详见[表 6](https://arxiv.org/html/2310.14724v3#S4.T6 "Table 6 ‣ 4.1.2 Potential Datasets ‣ 4.1 Training ‣ 4 Data ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")。

表 6: 其他潜在数据集的总结，这些数据集可以轻松扩展到 LLM 生成文本检测任务中。

| Corpus | Size | Source | Language | Domain |
| --- | --- | --- | --- | --- |
| XSum Narayan, Cohen, and Lapata ([2018](https://arxiv.org/html/2310.14724v3#bib.bib158)) | 42k | BBC | 英语 | 新闻写作 |
| SQuAD Rajpurkar et al. ([2016](https://arxiv.org/html/2310.14724v3#bib.bib176)) | 98.2k | Wiki | 英语 | 问答 |
| WritingPrompts Fan, Lewis, and Dauphin ([2018](https://arxiv.org/html/2310.14724v3#bib.bib62)) | 302k | Reddit WRITINGPROMPTS | 英语 | 故事生成 |
| Wiki40B Guo et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib79)) | 17.7m | Wiki | 40+ 语言 | 网络文本 |
| PubMedQA Jin et al. ([2019](https://arxiv.org/html/2310.14724v3#bib.bib96)) | 211k | PubMed | 英语 | 问答 |
| Children’s Book Corpus Hill et al. ([2016](https://arxiv.org/html/2310.14724v3#bib.bib86)) | 687k | 书籍 | 英语 | 问答 |
| Avax Tweets Dataset Muric, Wu, and Ferrara ([2021](https://arxiv.org/html/2310.14724v3#bib.bib156)) | 137m | Twitter | 英语 | 社交媒体 |
| Climate Change Dataset Littman and Wrubel ([2019](https://arxiv.org/html/2310.14724v3#bib.bib127)) | 4m | Twitter | 英语 | 社交媒体 |
| Yelp Dataset Asghar ([2016](https://arxiv.org/html/2310.14724v3#bib.bib11)) | 700k | Yelp | 英语 | 社交媒体 |
| ELI5 Fan et al. ([2019](https://arxiv.org/html/2310.14724v3#bib.bib61)) | 556k | Reddit | 英语 | 问答 |
| ROCStories Mostafazadeh et al. ([2016](https://arxiv.org/html/2310.14724v3#bib.bib152)) | 50k | 众包 | 英语 | 故事生成 |
| HellaSwag Zellers et al. ([2019a](https://arxiv.org/html/2310.14724v3#bib.bib252)) | 70k | ActivityNet Captions, Wikihow | 英语 | 问答 |
| SciGen Moosavi et al. ([2021](https://arxiv.org/html/2310.14724v3#bib.bib149)) | 52k | arXiv | 英语 | 科学写作, 问答 |
| WebText Radford et al. ([2019](https://arxiv.org/html/2310.14724v3#bib.bib174)) | 45m | 网络 | 英语 | 网络文本 |
| TruthfulQA Lin, Hilton, and Evans ([2022](https://arxiv.org/html/2310.14724v3#bib.bib126)) | 817 | 作者编写的英文 | 英文 | 问答 |
| NarrativeQA Kočiský et al. ([2018](https://arxiv.org/html/2310.14724v3#bib.bib103)) | 1.4k | Gutenberg3，网络 | 英文 | 问答 |
| TOEFL11 Blanchard et al. ([2013](https://arxiv.org/html/2310.14724v3#bib.bib24)) | 12k | TOEFL 测试 | 11 种语言 | 科学写作 |
| Peer Reviews Kang et al. ([2018](https://arxiv.org/html/2310.14724v3#bib.bib99)) | 14.5k | NIPS 2013–2017, CoNLL 2016, ACL 2017 | 英文 | 科学写作 |
| ICLR 2017, arXiv 2007–2017 |

##### 问答

问答是一种普遍且公平的数据集构建方法。通过向 LLMs 提出相同的问题，可以生成一对人类编写和 LLM 生成的文本集。

+   •

    PubMedQA Jin et al. ([2019](https://arxiv.org/html/2310.14724v3#bib.bib96)): 这是一个来自 PubMed 的生物医学问答（QA）数据集。[`www.ncbi.nlm.nih.gov/pubmed/`](https://www.ncbi.nlm.nih.gov/pubmed/)

+   •

    Children Book Corpus Hill et al. ([2016](https://arxiv.org/html/2310.14724v3#bib.bib86)): 该数据集源自公开可用的书籍，用于衡量语言模型利用更广泛语言上下文的能力。它挑战模型在 20 个连续句子的上下文中从十个可能选项中选择正确答案。答案类型包括动词、代词、命名实体和常见名词。

+   •

    ELI5 Fan et al. ([2019](https://arxiv.org/html/2310.14724v3#bib.bib61)): 这是一个针对长形式问答的大型语料库，ELI5 专注于需要对开放性问题进行详细回答的任务。数据集包含来自 Reddit 论坛“Explain Like I’m Five”的 27 万条条目，提供了针对五岁儿童理解水平的解释。

+   •

    TruthfulQA Lin, Hilton, and Evans ([2022](https://arxiv.org/html/2310.14724v3#bib.bib126)): 该基准评估 LLMs 生成回答的真实性。它包括 817 个问题，涵盖健康、法律、金融和政治等 38 个类别。所有问题均由人类编写。

+   •

    NarrativeQA Kočiský et al. ([2018](https://arxiv.org/html/2310.14724v3#bib.bib103)): 该英文数据集包括摘要或故事以及相关问题，旨在评估阅读理解，特别是关于扩展文档的数据。数据来源于 Project Gutenberg [`gutenberg.org/`](https://gutenberg.org/)和网络抓取的电影剧本，聘请的注释员提供答案。

##### 科学写作

科学写作在现实世界的研究环境中经常被探讨。给定特定的学术主题，LLMs 可以高效地生成学术文章或摘要。

+   •

    Peer Read Kang 等人 ([2018](https://arxiv.org/html/2310.14724v3#bib.bib99))：这是首个公开的科学同行评审文章数据集，包括 14.7k 篇草稿文章和 10.7k 篇专家撰写的同行评审报告，此外，还包括 ACL、NeurIPS 和 ICLR 等顶级会议的接受或拒绝决定。

+   •

    ArXiv:^[10]^[10]10[`arxiv.org/`](https://arxiv.org/) 一个自由访问的分发服务和资料库，ArXiv 主办了 230 万篇学术文章，涵盖物理学、数学、计算机科学和统计学等领域。

+   •

    TOEFL11 Blanchard 等人 ([2013](https://arxiv.org/html/2310.14724v3#bib.bib24))：这是一个公开可访问的语料库，包含了来自 TOEFL 测试的非母语英语写作者的作品，共有 1.1k 篇作文样本，涵盖 11 种语言：阿拉伯语、中文、法语、德语、印地语、意大利语、日语、韩语、西班牙语、泰卢固语和土耳其语。这些作文均匀分布在八个写作提示和三个评分等级（低/中/高）上。

##### 故事生成

LLMs 在故事生成领域表现出色，用户经常利用故事标题和写作提示来引导模型进行创作。

+   •

    写作提示 Fan、Lewis 和 Dauphin ([2018](https://arxiv.org/html/2310.14724v3#bib.bib62))：该数据集包含 300k 篇人工编写的故事，并配有写作提示。数据来源于 Reddit 的写作提示论坛，这是一个充满活力的在线社区，成员们通过发布故事创意或提示来互相激发灵感。数据集中故事的长度受限，介于 30 到 1k 字之间，且没有单词重复超过 10 次。

##### 新闻写作

新闻文章写作任务可以通过文章摘要数据集来处理。大型语言模型（LLMs）可以被指示从原始文本生成摘要，或根据提供的摘要生成文章。然而，鉴于资源限制，研究人员通常通过直接重新解释或扩充现有的摘要和文章来生成这样的数据集。

+   •

    极端摘要 (XSum) Narayan、Cohen 和 Lapata ([2018](https://arxiv.org/html/2310.14724v3#bib.bib158))：该数据集包含 BBC 文章及其简洁的一句话摘要。涵盖了从 2010 年到 2017 年的 225k 个样本，涉及新闻、政治、体育、天气、商业、科技、科学、健康、家庭、教育、娱乐、艺术等多个领域。

##### 网络文本

网络文本数据主要来源于维基百科等平台。对于网络文本生成，常见的方法是提供 LLMs 一个开头句子，然后让它们继续叙述。或者，可以指示 LLMs 根据网页标题生成内容。

+   •

    Wiki-40B Guo 等 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib79))：最初设想为语言模型训练的多语言基准，这个数据集包含了约 1950 万个 Wikipedia 页面中的文本，覆盖 40 种语言，总计约 400 亿字符。内容经过精细清理，以保持质量。

+   •

    WebText Radford 等 ([2019](https://arxiv.org/html/2310.14724v3#bib.bib174))：最初用于研究 LMs 或 LLMs 的学习潜力，这个数据集包括 4500 万个网页。数据集优先考虑内容质量，仅包括由人工筛选或过滤的网页，同时故意排除其他数据集中常见的来源，例如 Wikipedia。

##### 社交媒体

社交媒体数据集在评估 LLM 生成文本与人类撰写文本之间的主观表达差异中起着重要作用。

+   •

    Yelp 评价数据集 Asghar ([2016](https://arxiv.org/html/2310.14724v3#bib.bib11))：来源于 2015 年 Yelp 数据集挑战赛，这个数据集主要用于分类任务，如根据评论预测用户评分和确定极性标签。数据集包含 150 万条评论文本样本。

+   •

    r/ChangeMyView (CMV) Reddit 子社区：^[11]^[11]11[`www.reddit.com/r/changemyview/`](https://www.reddit.com/r/changemyview/) 常被称为“Change My View (CMV)”，这个 subreddit 提供了一个平台，让用户辩论各种话题，从政治和媒体到流行文化，通常提出对立的观点。

+   •

    IMDB 数据集：^[12]^[12]12[`huggingface.co/datasets/imdb`](https://huggingface.co/datasets/imdb) 作为一个广泛的电影评论数据集，用于二元情感分类，它的规模超出了以前的基准数据集，包括 25k 个训练样本和 25k 个测试样本。

+   •

    Avax 推文数据集 Muric, Wu 和 Ferrara ([2021](https://arxiv.org/html/2310.14724v3#bib.bib156))：设计用于研究社交媒体上的反疫苗虚假信息，这个数据集通过 Twitter API 获取。它包括一个以关键词为中心的流式数据集，包含超过 180 万条推文，以及一个包含超过 1.35 亿条推文的历史账户级数据集。

+   •

    气候变化推文 IDs Littman 和 Wrubel ([2019](https://arxiv.org/html/2310.14724v3#bib.bib127))：这个数据集包含了 3960 万条与气候变化相关的推文 ID。这些推文是通过 Social Feed Manager 从 Twitter API 中提取的，时间跨度从 2017 年 9 月 21 日到 2019 年 5 月 17 日，基于特定的搜索关键词。

##### 理解与推理

旨在理解和生成的 数据集 通常提供一致的上下文材料，引导 LLM 在再生成或继续文本时。

+   •

    Stanford Question and Answer Dataset (SQuAD) Rajpurkar 等 ([2016](https://arxiv.org/html/2310.14724v3#bib.bib176))：该阅读理解数据集包含 100k 个问答对，涵盖从音乐名人到抽象概念的主题。样本来自前 10k 篇英文维基百科文章，通过 PageRank 选取。从这些文章中随机选择了 536 篇，排除了短于 500 字的段落。众包贡献者根据这些专家提出问题，而额外的人员提供答案。

+   •

    SciGen Moosavi 等 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib149))：该任务侧重于从感知数据中推理以生成文本。它包括来自科学文章的表格及其描述。整个数据集来源于 arXiv 网站的“计算机科学”部分，其中包含来自“计算与语言”领域的高达 17.5k 样本，以及来自“机器学习”等领域的 35.5k 样本。此外，该数据集有助于评估生成模型的算术推理能力，使用复杂的输入格式，如科学表格。

+   •

    ROCStories Corpora (ROC) Mostafazadeh 等 ([2016](https://arxiv.org/html/2310.14724v3#bib.bib152))：旨在自然语言理解，该数据集任务是确定四句叙事的恰当结论。这是一个策划的 50k 五句故事的集合，反映了日常经历。除了其主要目的外，它还可以支持诸如故事生成等任务。

+   •

    HellaSwag Zellers 等 ([2019a](https://arxiv.org/html/2310.14724v3#bib.bib252))：专注于常识推理，该数据集包含大约 70k 个问题。利用对抗过滤（AF），数据集为多项选择设置创建了具有误导性和复杂性的虚假答案，目标是在上下文中找到正确答案。

### 4.2 评估基准

表 7：LLM 生成文本检测的基准总结。

| 语料库 | 用途 | 人类 | LLMs | LLMs 类型 | 语言 | 攻击 | 领域 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TuringBench Uchendu 等 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib219)) | 训练 | ~8k | ~159k | GPT-1, GPT-2, GPT-3, GROVER, CTRL, XLM, XLNET, FAIR, TRANSFORMER_XL, PPLM | 英语 | - | 新闻写作 |
| MGTBench He 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib83)) | 训练 测试 | ~2.4k ~0.6k | ~14.4k ~3.6k | ChatGPT, ChatGPT-turbo, ChatGLM, Dolly, GPT4All, StableLM | 英语 | 对抗性 | 科学写作、故事生成、新闻写作 |
| GPABenchmark Liu 等 ([2023d](https://arxiv.org/html/2310.14724v3#bib.bib133)) | 测试 | ~150k | ~450k | GPT-3.5 | 英语 | 意译 | 科学写作 |
| 科学文章基准 Mosca 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib151)) | 测试 | ~16k | ~13k | SCIgen, GPT-2, GPT-3, ChatGPT, Galactica | 英语 | - | 科学写作 |
| MULTITuDE Macko 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib139)) | 训练 测试 | ~4k ~3k | ~40k ~26k | Alpaca-lora, GPT-3.5-Turbo, GPT-4, LLaMA, OPT, OPT-IML-Max, Text-Davinci-003, Vicuna | 阿拉伯语、加泰罗尼亚语、中文、捷克语、荷兰语、英语、德语、葡萄牙语、俄语、西班牙语、乌克兰语 | - | 科学写作、新闻写作、社交媒体 |
| HANSEN Tripto 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib212)) | 测试 | - | ~21k | ChatGPT, PaLM2, Vicuna13B | 英语 | - | 口语文本 |
| M4 Wang 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib227)) | 训练 验证 测试 | ~35k ~3.5k ~3.5k | ~112k ~3.5k ~3.5k | GPT-4, ChatGPT, GPT-3.5, Cohere, Dolly-v2, BLOOMz 176B | 英语、中文、俄语、乌尔都语、印尼语、保加利亚语、阿拉伯语 | - | 网络文本、科学写作、新闻写作、社交媒体、问答 |

高质量的基准可以帮助研究人员快速验证他们的检测器是否可行和有效。我们整理并比较了目前流行或有潜力的基准，如[表 7](https://arxiv.org/html/2310.14724v3#S4.T7 "Table 7 ‣ 4.2 Evaluation Benchmarks ‣ 4 Data ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")所示。一方面，我们希望帮助研究人员更好地理解它们的差异，以选择适合自己实验的基准。另一方面，我们希望引起研究人员对最新基准的关注，这些基准已经充分设计以验证任务中的最新问题，并具有很大的潜力。

##### TuringBench

TuringBench 数据集 Uchendu 等人 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib219)) 是一个旨在探讨神经文本生成技术中“图灵测试”挑战的倡议。它包含从 10k 新闻文章中提取的人类撰写内容，主要来自如 CNN 等声誉良好的来源。为了此数据集的目的，仅选择了 200 到 400 字的文章。该数据集中生成的 LLM 文本由 19 种不同的文本生成模型产生，包括 GPT-1、GPT-2 的变体（小型、中型、大型、xl 和 pytorch）、GPT-3、不同版本的 GROVER（base、large 和 mega）、CTRL、XLM、XLNET 的变体（base 和 large）、FAIR 的 WMT19 和 WMT20、Transformer-XL，以及 PLM 的两个变体（distil 和 GPT-2）。每个模型贡献了 8k 样本，按标签类型分类。值得注意的是，TuringBench 成为检测 LLM 生成文本的先锋基准环境之一。然而，鉴于 LLM 技术的快速进展，TuringBench 中的样本现在不太适合训练和验证当代检测器的性能。因此，及时更新包含最新生成模型及其生成文本的样本是必要的。

##### MGTBench

由 He 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib83)）提出，MGTBench 是首个用于 MGT 检测的基准框架。它具有模块化架构，包括输入模块、检测模块和评估模块。该数据集采用了包括 ChatGPT、ChatGLM、Dolly、ChatGPT-turbo、GPT4All 和 StableLM 在内的多种顶级 LLM 生成文本。此外，它还结合了十多种广泛认可的检测算法，展示了显著的潜力。

##### GPABenchmark

GPABenchmark 由 Liu 等人（[2023d](https://arxiv.org/html/2310.14724v3#bib.bib133)）提出，是一个涵盖 60 万样本的全面数据集。这些样本包括来自计算机科学、物理学、人文学科和社会科学等广泛学科的人工编写、GPT 编写、GPT 完成和 GPT 润色的摘要。该数据集详细捕捉了反映 LLM 在学术写作中使用及潜在误用的典型场景。因此，它划定了三个具体任务：基于提供的标题生成文本、完成部分草稿和完善现有草稿。在学术写作检测领域，GPABenchmark 凭借其庞大的数据量和全面的场景表示方法，成为一个强有力的基准。

##### 科学文章基准

科学文章基准由 Mosca 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib151)）提出，包含 1.6 万篇人工编写的文章以及 1.3 万篇 LLM 生成的样本。人工编写的文章来自 Kaggle 上的 arXiv 数据集。而机器生成的样本，包括摘要、引言和结论，由 SCIgen、GPT-2、GPT-3、ChatGPT 和 Galactica 生成，使用相应科学文章的标题作为提示。该数据集的一个显著限制是遗漏了各种对抗攻击类型。

##### MULTITuDE

这是一个用于检测多语言机器生成文本的基准数据集。该数据集包含 74k 条机器生成文本和 7k 条人工编写文本，涵盖 11 种语言，包括阿拉伯语、加泰罗尼亚语、中文、捷克语、荷兰语、英语、德语、葡萄牙语、俄语、西班牙语和乌克兰语。机器生成的文本由包括 Alpaca-Lora、GPT-3.5-turbo、GPT-4、LLaMA、OPT、OPT-IML-Max、Text-Davinci-003 和 Vicuna 在内的八个生成模型生成。在多语言 LLM 迅速增加的时代，MULTITuDE 作为评估 LLM 生成文本检测器在各种语言中的检测能力的有效基准。

##### HANSEN

人类与 AI 口语文本基准（HANSEN）Tripto 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib212)）是最大的口语文本基准，涵盖了 17 个语音数据集和记录，以及 23k 个新颖的 AI 生成口语文本。HANSEN 中的 AI 生成口语文本由 ChatGPT、PaLM2 和 Vicuna-13B 创建。由于口语和书面语言之间的风格差异，检测器可能需要对口语文本有更细致的理解。HANSEN 可以有效评估研究在开发这种细致检测器方面的进展。

##### M4

M4 Wang 等人（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib227)）作为检测由 LLMs 生成的文本的全面基准语料库，涵盖了多种生成器、领域和语言。该数据集汇编自来自不同地区的维基页面、新闻媒体和学术门户等各种来源，反映了 LLMs 在日常应用中的常见场景。M4 中的 LLM 生成文本使用了如 ChatGPT、LLaMa、BLOOMz、FlanT5 和 Dolly 等前沿生成模型创建。值得注意的是，该数据集捕捉了跨语言的微妙之处，包含了十多种语言的内容。总之，虽然 M4 数据集有效应对了跨领域、模型和语言的复杂性，但通过引入更广泛的对抗性场景，可以进一步丰富数据集。

### 4.3 数据挑战

鉴于我们在该领域的广泛经验，现有的 LLMs 专用强健数据集和基准仍存在显著不足。尽管取得了可喜的进展，但当前的努力仍显不足。研究人员普遍倾向于使用原本为其他任务设计的数据集作为人工编写文本，并基于这些文本生成 LLM 生成文本以训练检测器。这种做法源于现有数据集或基准在全面应对不同研究视角方面的局限性。因此，我们旨在本文中概述当前数据集和基准的主要限制和挑战。

#### 4.3.1 评估框架的全面性

在获得信任之前，可靠的检测器需要多方面的评估。目前的基准有些有限，仅提供表面挑战，因此未能全面评估检测器。我们强调五个对 LLM 生成文本检测任务的更强大基准开发至关重要的维度。这些维度包括多种攻击类型、多样领域、多样任务、各种模型的范围，以及多语言的包含。

##### 多种类型的攻击

对于确定检测方法的有效性至关重要。在实际环境中，LLM 生成的文本检测器通常会遇到使用各种攻击机制生成的文本，这些文本与通过简单提示生成的文本不同。例如，[子章节 7.2](https://arxiv.org/html/2310.14724v3#S7.SS2 "7.2 Potential Attacks ‣ 7 Important Issues of LLM-generated Text Detection ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions") 中阐述的提示攻击迫使生成模型产生更高质量的文本，利用复杂而精细的提示。将此类文本纳入现有数据集是至关重要的。Guo 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib78)) 所列的局限性也反映了这一问题。

##### 多领域和多任务

配置对于评估检测器在不同实际领域和 LLM 应用中的表现至关重要。这些维度对检测器的鲁棒性、可用性和可信度有重要影响。例如，在学术背景下，一个高效的检测器应该在所有领域中表现出色。在日常场景中，它应能够熟练识别跨越学术论文、新闻文章、算术推理和问答环节的 LLM 生成文本。尽管许多现有研究审慎地考虑了这些因素，我们仍提倡优质数据集的推广。

##### 多个 LLM

LLM 领域的持续研究势头带来了如 LLaMa Touvron 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib211))、PaLM Chowdhery 等人 ([2022a](https://arxiv.org/html/2310.14724v3#bib.bib34)) 和 Claude-2¹³¹³13[`www.anthropic.com/index/claude-2`](https://www.anthropic.com/index/claude-2) 等强大的对手，与 ChatGPT 的能力相抗衡。尽管关注仍集中在 ChatGPT 上，但同样需要同时关注其他新兴 LLM 带来的潜在风险。

##### 多语言

考虑因素需要增加关注。我们强烈鼓励研究人员带头创建多语言数据集，以促进对由 LLM 生成的文本检测器在不同语言中的评估。使用预训练模型可能会揭示某些检测器在处理代表性不足的语言时的困难，而 LLM 可能会显示出更明显的不一致性。这一维度提供了丰富的探索和讨论途径。

#### 4.3.2 时间维度

可以看出，某些当代研究持续使用了开创性但略显过时的基准数据集，这些数据集在过去的 GPT 生成文本和假新闻检测工作中发挥了重要作用。然而，这些数据集主要来源于过时的 LLM，这意味着经过验证的方法可能并不总是与当前的实际动态相符。我们强调使用由先进且强大的 LLM 制定的数据集的重要性，同时呼吁基准数据集开发者定期更新其贡献，以反映领域的快速发展。

{森林}

对树=生长=东，反向=true，锚点=基西，父锚点=东，子锚点=西，基=左，字体=，矩形，绘制，圆角对齐=左，最小宽度=2.12em，内侧 xsep=4pt，内侧 ysep=1pt， ，其中级别=1 字体=，填充=粉色!5，其中级别=2 字体=，yshift=0.26pt，填充=黄色!20，高级

探测器

研究

(第五部分)，文本宽度=3.2em，填充=蓝色!10，[![参见标题

水印技术，文本宽度=12em [*数据驱动水印:* Gu 等人 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib77)) / Lucas 和 Havens ([2023](https://arxiv.org/html/2310.14724v3#bib.bib136)) /

Tang 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib207))，文本宽度=19em] [*模型驱动水印:* Kirchenbauer 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib101)) / Lee 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib117)) /

Kirchenbauer 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib102)) / Liu 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib129)) / Liu 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib128)) /

Kuditipudi 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib108)) / Hou 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib89)), 文本宽度=19em] [*后处理水印技术:* Por, Wong 和 Chee ([2012](https://arxiv.org/html/2310.14724v3#bib.bib167)) /

Rizzo, Bertini 和 Montesi ([2016](https://arxiv.org/html/2310.14724v3#bib.bib178)) / Topkara, Topkara 和 Atallah ([2006](https://arxiv.org/html/2310.14724v3#bib.bib210)) /

Yang 等人 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib243)) / Munyer 和 Zhong ([2023](https://arxiv.org/html/2310.14724v3#bib.bib154)) / Yoo 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib248)) /

Yang 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib242)) / Abdelnabi 和 Fritz ([2021](https://arxiv.org/html/2310.14724v3#bib.bib1)) / Zhang 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib255))，文本宽度=19em] ] ![参见标题

基于统计的探测器，文本宽度=12em [*语言特征统计:* Corston-Oliver, Gamon 和 Brockett ([2001](https://arxiv.org/html/2310.14724v3#bib.bib41)) /

Kalinichenko 等 ([2003](https://arxiv.org/html/2310.14724v3#bib.bib98)) / Baayen ([2001](https://arxiv.org/html/2310.14724v3#bib.bib13)) / Arase 和 Zhou ([2013](https://arxiv.org/html/2310.14724v3#bib.bib9)) /

Gallé 等 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib65)) / Hamed 和 Wu ([2023](https://arxiv.org/html/2310.14724v3#bib.bib81))，[*白盒统计:* Solaiman 等 ([2019](https://arxiv.org/html/2310.14724v3#bib.bib197)) / Gehrmann, Strobelt 和 Rush ([2019](https://arxiv.org/html/2310.14724v3#bib.bib71))

Su 等 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib203)) / Lavergne, Urvoy 和 Yvon ([2008](https://arxiv.org/html/2310.14724v3#bib.bib113)) / Beresneva ([2016](https://arxiv.org/html/2310.14724v3#bib.bib19)) /

Vasilatos 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib220)) / Wu 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib236)) / Mitchell 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib146)) / Deng 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib49)) /

Bao 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib16)) / Yang 等 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib244)) / Tulchinskii 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib214))，[*黑盒统计:* Yang 等 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib244)) / Mao 等 ([2024](https://arxiv.org/html/2310.14724v3#bib.bib141)) / Zhu 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib260)) /

Yu 等 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib250)) / Quidwai, Li 和 Dube ([2023](https://arxiv.org/html/2310.14724v3#bib.bib173)) / Guo 和 Yu ([2023](https://arxiv.org/html/2310.14724v3#bib.bib80))，![参考说明

基于神经网络的检测器，[*基于特征的分类器:* Aich, Bhattacharya 和 Parde ([2022](https://arxiv.org/html/2310.14724v3#bib.bib2)) / Shah 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib192)) /

Corizzo 和 Leal-Arenas ([2023](https://arxiv.org/html/2310.14724v3#bib.bib40)) / Mindner, Schlippe 和 Schaaff ([2023](https://arxiv.org/html/2310.14724v3#bib.bib144)) /

Schaaff, Schlippe 和 Mindner ([2023](https://arxiv.org/html/2310.14724v3#bib.bib185)) / Schuster 等 ([2020a](https://arxiv.org/html/2310.14724v3#bib.bib189)) /

Crothers 等 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib45)) / Li 等 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib118)) / Wang 等 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib226)) / Wu 和 Xiang ([2023](https://arxiv.org/html/2310.14724v3#bib.bib237))，[*预训练分类器:* Bakhtin 等 ([2019](https://arxiv.org/html/2310.14724v3#bib.bib15)) / Uchendu 等 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib217)) /

Antoun 等 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib6)) / Li 等 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib120)) / Fagni 等 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib60)) / Gambini 等 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib66)) /

Guo 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib78)) / Liu 等 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib131)) / Liu 等 ([2023d](https://arxiv.org/html/2310.14724v3#bib.bib133)) / Wang 等 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib228)) /

Wang 等 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib228)) / Bakhtin 等 ([2019](https://arxiv.org/html/2310.14724v3#bib.bib15)) / Uchendu 等 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib217)) /

Antoun 等 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib6)) / Li 等 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib120)) / Sarvazyan 等 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib183)) /

Rodriguez 等 ([2022b](https://arxiv.org/html/2310.14724v3#bib.bib180)) / Liu 等 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib130)) / Zhong 等 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib259)) /

Bhattacharjee 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib22)) / Yang, Jiang 和 Li ([2023](https://arxiv.org/html/2310.14724v3#bib.bib241)) / Shi 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib196)) /

Koike, Kaneko 和 Okazaki ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib105)) / He 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib83)) / Hu, Chen 和 Ho ([2023](https://arxiv.org/html/2310.14724v3#bib.bib90)) /

Koike, Kaneko 和 Okazaki ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib105)) / Tu 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib213)) / Kumarage 等 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib110)) /

Cowap, Graham 和 Foster ([2023](https://arxiv.org/html/2310.14724v3#bib.bib42)) / Uchendu, Le 和 Lee ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib216))，文本宽度=19em ] [*LLMs 作为探测器：* Zellers 等 ([2019b](https://arxiv.org/html/2310.14724v3#bib.bib253)) / Liu 等 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib131)) /

Bhattacharjee 和 Liu ([2023](https://arxiv.org/html/2310.14724v3#bib.bib23)) / Koike, Kaneko 和 Okazaki ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib105))，文本宽度=19em ] ] ![参见说明

人工辅助方法，文本宽度=12em [*直观指标：* Uchendu 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib218)) / Dugan 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib58)) /

/ Jawahar, Abdul-Mageed 和 Lakshmanan ([2020](https://arxiv.org/html/2310.14724v3#bib.bib93))，[*不可察觉的特征:* Ippolito et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib92)) / Clark et al. ([2021b](https://arxiv.org/html/2310.14724v3#bib.bib38)) /

Gehrmann, Strobelt 和 Rush ([2019](https://arxiv.org/html/2310.14724v3#bib.bib71))，[*提升人类检测能力:* Ippolito et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib92)) / Dugan et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib57)) /

Dugan et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib58)) / Dou et al. ([2022](https://arxiv.org/html/2310.14724v3#bib.bib56))，[*混合检测: 理解与解释:* Weng et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib233))] /

图 4: LLM 生成文本探测器的分类，附有相应的图示和论文列表。我们将探测器分为水印技术、基于统计的探测器、基于神经网络的探测器和人类辅助的方法。在图示中，HWT 代表人类书写文本，LGT 代表 LLM 生成文本。我们使用橙色线条突出探测器检测能力的来源，绿色线条描述检测过程。

## 5 探测器研究的进展

在本节中，我们展示了不同的探测器设计和检测算法，包括水印技术、基于统计的探测器、基于神经网络的探测器和人类辅助的方法。我们关注最近提出的方法，并根据其基本原理对讨论进行分类（见[图 4](https://arxiv.org/html/2310.14724v3#S4.F4 "Figure 4 ‣ 4.3.2 Temporal ‣ 4.3 Data Challenges ‣ 4 Data ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")）。

### 5.1 水印技术

最初应用于计算机视觉领域以开发生成模型，水印技术在检测 AI 生成图像中起到了核心作用，为视觉艺术中的知识产权和财产权提供了保护措施。随着大语言模型（LLMs）的出现和普及，水印技术的应用扩展到了对这些模型生成的文本的识别。水印技术不仅保护了大量模型免受未经授权的获取，如序列蒸馏，还减少了与 LLM 生成文本的复制和滥用相关的风险。

#### 5.1.1 数据驱动的水印技术

数据驱动方法通过在 LLMs 的训练数据集中嵌入特定的模式或标签，实现数据所有权验证或追踪非法复制或滥用。这些方法通常依赖于后门插入，其中将少量带水印的样本添加到数据集中，使模型能够隐式地学习由防御者设置的秘密功能集。当激活特定触发器时，后门水印被触发，这通常在黑箱设置中实现 Gu 等 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib77))。这一机制通过在模型训练的基础和多任务学习框架阶段嵌入后门，保护模型免受未经授权的微调或超出许可证条款的使用，即使模型经过多次下游任务微调，水印仍然难以根除。

然而，后续研究发现了这一技术的漏洞，显示它相对容易被破解。Lucas 和 Havens ([2023](https://arxiv.org/html/2310.14724v3#bib.bib136)) 通过分析自回归模型生成的内容，详细描述了对这种水印策略的攻击方法，以精确定位后门水印的触发词或短语。研究指出，由随机组合的常见词组成的触发器比由独特且稀有的标记组成的触发器更容易被检测到。此外，研究还提到，访问模型的权重是检测后门水印的唯一前提。最近，Tang 等 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib207)) 提出了一个清洁标签后门水印框架，该框架使用微妙的对抗扰动来标记和触发样本。这种方法有效地保护了数据集，同时将对原始任务性能的影响最小化。结果显示，仅添加 1% 的带水印样本就可以注入一个可追踪的水印特征。

需要注意的是，数据驱动方法最初是为了保护数据集的版权而设计的，因此通常缺乏实质性的负载能力和通用性。此外，将这些技术应用于 LLM 生成文本检测领域需要大量的资源投入，包括在大量数据中嵌入水印和重新训练 LLMs。

#### 5.1.2 模型驱动水印

模型驱动方法通过在推理过程中操控 logits 输出分布或令牌采样，直接将水印嵌入到 LLMs 中。因此，LLMs 生成的响应会带有嵌入的水印。

##### 基于 Logits 的方法

Kirchenbauer 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib101)) 首次设计了一种基于 logits 的水印框架用于大语言模型（LLMs），其特点是对文本质量的影响最小。该框架通过高效的开源算法简化了检测过程，无需访问 LLM 的 API 或参数。在文本生成之前，该方法会随机选择一组“绿色”标记，将其余标记定义为“红色”，然后在采样过程中轻柔地引导模型选择来自“绿色”集合的标记。此外，Kirchenbauer 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib101)) 开发了一种基于可解释的 <math alttext="p" class="ltx_Math" display="inline" id="S5.SS1.SSS2.Px1.p1.1.m1.1"><semantics id="S5.SS1.SSS2.Px1.p1.1.m1.1a"><mi id="S5.SS1.SSS2.Px1.p1.1.m1.1.1" mathcolor="#000000" xref="S5.SS1.SSS2.Px1.p1.1.m1.1.1.cmml">p</mi><annotation-xml encoding="MathML-Content" id="S5.SS1.SSS2.Px1.p1.1.m1.1b"><ci id="S5.SS1.SSS2.Px1.p1.1.m1.1.1.cmml" xref="S5.SS1.SSS2.Px1.p1.1.m1.1.1">𝑝</ci></annotation-xml><annotation encoding="application/x-tex" id="S5.SS1.SSS2.Px1.p1.1.m1.1c">p</annotation><annotation encoding="application/x-llamapun" id="S5.SS1.SSS2.Px1.p1.1.m1.1d">italic_p</annotation></semantics></math>-值的水印检测方法，该方法通过对文本中的红色和绿色标记进行统计分析来识别水印，从而计算 <math alttext="p" class="ltx_Math" display="inline" id="S5.SS1.SSS2.Px1.p1.2.m2.1"><semantics id="S5.SS1.SSS2.Px1.p1.2.m2.1a"><mi id="S5.SS1.SSS2.Px1.p1.2.m2.1.1" mathcolor="#000000" xref="S5.SS1.SSS2.Px1.p1.2.m2.1.1.cmml">p</mi><annotation-xml encoding="MathML-Content" id="S5.SS1.SSS2.Px1.p1.2.m2.1b"><ci id="S5.SS1.SSS2.Px1.p1.2.m2.1.1.cmml" xref="S5.SS1.SSS2.Px1.p1.2.m2.1.1">𝑝</ci></annotation-xml><annotation encoding="application/x-tex" id="S5.SS1.SSS2.Px1.p1.2.m2.1c">p</annotation><annotation encoding="application/x-llamapun" id="S5.SS1.SSS2.Px1.p1.2.m2.1d">italic_p</annotation></semantics></math>-值的显著性。继 Kirchenbauer 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib101)) 之后，Lee 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib117)) 引入了一种新的水印方法，称为 SWEET，该方法仅在生成过程中选择具有高标记分布熵的位置来提升“绿色”标记，从而保持水印的隐蔽性和完整性。它使用基于熵的统计测试和 Z 分数来检测水印代码。

尽管 Kirchenbauer 等人的研究（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib101)）表现出色，但其鲁棒性仍然存在争议。Kirchenbauer 等人（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib102)）的最新工作研究了带水印文本在手动重写、使用未加水印的 LLM 重写或融入大量手写文档中的抵抗能力。该研究引入了一种称为“WinMax”的窗口测试方法，以评估在大量文档中准确检测水印区域的效果。为了解决同义词替换和文本释义的挑战，Liu 等人（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib129)）提出了一种针对 LLM 的语义不变鲁棒水印方法。该方法生成所有前置标记的语义嵌入，并利用这些嵌入来确定水印逻辑，表现出对同义词替换和文本释义的鲁棒性。此外，当前的水印检测算法在生成过程中需要使用密钥，这可能导致公开检测过程中的安全漏洞和伪造。为了解决这一问题，Liu 等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib128)）首次引入了专用的私有水印算法用于水印生成和检测，分别在每个阶段部署了两种不同的神经网络。通过避免在两个阶段中使用密钥，该方法创新性地扩展了现有的文本水印算法。此外，它在水印生成和检测网络之间共享某些参数，从而提高了检测网络的效率和准确性，同时最小化了对生成和检测过程速度的影响。

##### 基于标记采样的方法

在正常模型推理过程中，标记采样由采样策略决定，通常是随机的，这有助于引导 LLM 生成更不可预测的文本。基于标记采样的方法通过影响标记采样过程来实现水印化，方法包括设置随机种子或特定模式进行标记采样。Kuditipudi 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib108)）使用一系列随机数字作为秘密水印密钥，以干预并确定标记采样，随后将其映射到 LLM 中生成带水印的文本。在检测阶段，利用秘密密钥将文本与随机数字序列对齐，以完成检测任务。这种方法在应对释义攻击时表现出强大的鲁棒性，即使大约 40-50% 的标记被修改。

另一项近期的工作是 SemStamp Hou 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib89)）提出的基于局部敏感哈希（LSH）的鲁棒句子级语义水印算法。该算法首先对由 LLM 生成的候选句子进行编码和 LSH 哈希，将语义嵌入空间划分为水印区域和非水印区域。然后，它不断进行句子级的拒绝采样，直到采样的句子落入语义嵌入空间的水印分区。实验结果表明，这种方法不仅在防御常见的二元语义攻击方面比之前的 SOTA 方法更具鲁棒性，而且在保持文本生成质量方面也更为出色。

总的来说，模型驱动的水印技术是一种即插即用的方法，不需要对模型参数进行任何更改，对文本质量的影响最小，是一种可靠且实用的水印方法。然而，它的鲁棒性仍有显著改进的空间，其具体可用性需要通过更多的实验和实际应用进一步探索。

#### 5.1.3 后处理水印技术

后处理水印技术指的是在文本由大型语言模型（LLM）输出后，通过处理文本嵌入水印的技术。这种方法通常作为一个独立模块，与生成模型的输出在流水线中配合工作。

##### 字符嵌入方法

早期的后处理水印技术依赖于将特殊的 Unicode 字符插入或替换到文本中。这些字符对肉眼难以识别，但携带着独特的编码信息 Por、Wong 和 Chee（[2012](https://arxiv.org/html/2310.14724v3#bib.bib167)）；Rizzo、Bertini 和 Montesi（[2016](https://arxiv.org/html/2310.14724v3#bib.bib178)）。最近，Rizzo、Bertini 和 Montesi（[2016](https://arxiv.org/html/2310.14724v3#bib.bib178)）引入了 Easymark，这是一种巧妙利用 Unicode 具有许多相同或类似外观的代码点的技术。具体而言，Easymark 通过用另一个空白代码点（例如，U+2004）替换常规空格字符（U+0020），使用 Unicode 的变体选择符、替换子字符串或使用稍微不同长度的空格和同形异义词来嵌入水印，同时确保文本的外观几乎不变。结果表明，通过 Easymark 嵌入的水印可以可靠地检测到，而不会降低 BLEU 分数或增加文本的困惑度，超越了现有的先进技术，在质量和水印可靠性方面均表现优越。

##### 同义词替换法

鉴于字符级方法对针对性攻击的脆弱性，一些研究已经转向在词汇层面嵌入水印，主要通过同义词替换来实现。早期的水印嵌入方案涉及不断用同义词替换单词，直到文本中包含了预期的水印内容。为了解决这个问题，Topkara、Topkara 和 Atallah（[2006](https://arxiv.org/html/2310.14724v3#bib.bib210)）提出了一种量化且具有弹性的水印技术，使用了 WordnetFellbaum（[1998](https://arxiv.org/html/2310.14724v3#bib.bib63)）。在此基础上，Yang 等人（[2022](https://arxiv.org/html/2310.14724v3#bib.bib243)）；Munyer 和 Zhong（[2023](https://arxiv.org/html/2310.14724v3#bib.bib154)）；Yoo 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib248)）使用了预训练或进一步微调的神经模型来执行单词替换和检测任务，从而更好地保留了原始句子的语义完整性。此外，Yang 等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib242)）定义了一种二进制编码函数来计算对应于单词的随机二进制代码，并选择性地用表示二进制“1”的上下文相关同义词替换表示二进制“0”的单词，从而有效地嵌入了水印。实验表明，这种方法确保了水印对诸如重译、文本润色、单词删除和同义词替换等攻击的鲁棒性，同时不损害原始文本的语义。

##### 序列到序列的方法

最近的研究探讨了端到端水印加密技术，旨在增强灵活性并减少水印引入的伪影。例如，Abdelnabi 和 Fritz ([2021](https://arxiv.org/html/2310.14724v3#bib.bib1)) 提出了对抗性水印变换器（AWT），这是第一个自动学习词语替换及其内容以进行水印嵌入的框架。该方法结合了端到端和对抗训练，能够在编码层将二进制消息注入指定的输入文本中，生成的输出文本几乎不可察觉，并且最小化地改变输入的语义和正确性。该方法使用变换器编码器层提取嵌入文本中的秘密消息。类似地，Zhang 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib255)) 介绍了 REMARK-LLM 框架，该框架包括三个组件：（i）一个消息编码模块，将二进制签名注入由 LLM 生成的文本中；（ii）一个重参数化模块，将消息编码的密集分布转换为生成水印文本标记的稀疏分布；（iii）一个解码模块，专注于提取签名。实验表明，REMARK-LLM 在保持语义完整性的同时，将更多的签名位嵌入相同的文本中，并且相比于 AWT，显示出对各种水印移除和检测攻击的增强抵抗力。

与模型驱动水印相比，后处理水印可能更依赖于特定规则，这使其更容易受到利用可见线索的复杂攻击。尽管存在这种风险，后处理水印在各种应用中具有重要潜力。许多现有的水印技术通常需要在白盒模型中进行训练，使其不适用于黑盒 LLM 设置。例如，由于 GPT-4 的专有和封闭源代码特性，几乎不可能在其中嵌入水印。然而，后处理水印为向黑盒 LLM 生成的文本中添加水印提供了一种解决方案，使第三方可以独立地嵌入水印。

### 5.2 基于统计的方法

在基于统计的设置中，本小节介绍了使用检测器有效识别由 LLM 生成的文本的方法，无需通过监督信号进行额外训练。该方法假设可以访问 LLM 或从文本中提取特征，并基于独特的特征和统计数据来推导统计规律（例如，计算阈值）。

#### 5.2.1 语言学特征统计

基于统计的检测研究的起源可以追溯到 Corston-Oliver、Gamon 和 Brockett ([2001](https://arxiv.org/html/2310.14724v3#bib.bib41)) 的开创性工作。在这项基础研究中，作者利用语言特征，如语法分析中的分支特性、功能词密度和成分长度，来判断给定的文本是否由机器翻译模型生成。这些特征作为区分机器生成文本与人类生成文本的关键指标。

另一种显著的方法，旨在实现类似的检测目标，采用了频率统计。例如，Kalinichenko 等人 ([2003](https://arxiv.org/html/2310.14724v3#bib.bib98)) 利用文本中词对的频率统计作为判断文本是否由生成系统自主生成的机制。此外，Baayen ([2001](https://arxiv.org/html/2310.14724v3#bib.bib13)) 采用了基于词的分布特征的方法。在这一研究方向上，Arase 和 Zhou ([2013](https://arxiv.org/html/2310.14724v3#bib.bib9)) 后来通过开发一种检测技术来捕捉句子中的“短语沙拉”现象。

最近关于 LLM 生成文本检测的研究提出了基于语言特征统计的方法。Gallé等人 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib65)) 提出了一种利用重复高阶 n-grams 来检测 LLM 生成文档的方法。这一方法建立在观察到某些 n-grams 在 LLM 生成文本中异常频繁出现的现象上，这一现象已经被广泛记录。类似地，Hamed 和 Wu ([2023](https://arxiv.org/html/2310.14724v3#bib.bib81)) 开发了一种基于 bigrams 统计相似性的检测系统。他们的研究结果表明，ChatGPT 生成的文本中只有 23%的 bigrams 是独特的，突显了人类和 LLM 生成内容在术语使用上的显著差异。令人印象深刻的是，他们的算法成功识别了 100 篇 LLM 撰写的学术论文中的 98 篇，展示了他们的特征工程方法在区分 LLM 生成文本中的有效性。

然而，我们的经验观察揭示了语言特征统计应用中的一个明显局限：这些方法的可用性在很大程度上依赖于广泛的语料库统计和各种类型的 LLM。

#### 5.2.2 白盒统计

目前，用于检测 LLMs 生成文本的白盒方法需要直接访问源模型以进行实施。现有的白盒检测技术主要使用零-shot 方法，这涉及获取模型的 logits 输出并计算特定度量。这些度量随后与通过统计方法获得的预定阈值进行比较，以识别 LLM 生成的文本。

##### Logits 基础统计

Logits 是 LLMs 在文本生成过程中产生的原始输出，特别是来自模型的最终线性层，这通常位于 softmax 函数之前。这些输出表示模型与生成每个潜在后续词相关的置信水平。Log-Likelihood Solaiman 等人（[2019](https://arxiv.org/html/2310.14724v3#bib.bib197)），一种直接从 logits 派生的度量，通过咨询原始 LLM 来测量提供文本中每个 token 的平均 token-wise 对数概率。这种测量有助于确定文本是否由 LLM 生成。目前，Log-Likelihood 被认为是 LLM 生成文本检测任务中最受欢迎的基准度量之一。

类似地，Rank Solaiman 等人（[2019](https://arxiv.org/html/2310.14724v3#bib.bib197)）是另一种从 logits 计算得出的常规基准。Rank 度量计算样本中每个词在模型输出概率分布中的排名。这个排名是通过将词的 logit 分数与所有其他可能词的 logit 分数进行比较来确定的。如果样本中每个词的平均排名很高，这表明样本可能是由 LLMs 生成的。而 Log-Rank 则通过应用对数函数进一步处理每个 token 的排名值，并引起了越来越多的关注。基于这种直观方法的一个值得注意的方法是 GLTR Gehrmann、Strobelt 和 Rush（[2019](https://arxiv.org/html/2310.14724v3#bib.bib71)），它被设计为一种视觉取证工具，以促进比较判断。该工具根据 token 的采样频率水平划分不同的标记颜色，并通过为提供文本的 tokens 标记不同颜色来突出 LLMs 在分析文本中倾向使用的词的比例。Su 等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib203)）提出的 Log-Likelihood Ratio Ranking（LRR）通过取两个度量的比率，将 Log-Likelihood 和 Log-Rank 结合在一起。这种方法通过有效地将 Log Likelihood 评估与 Log Rank 分析相补充，从而提供更全面的评估，提升了性能。

熵代表了另一种早期的零样本方法，用于评估由 LLM 生成的文本。它通常用于测量文本或模型输出中的不确定性或信息量，并通过单词的概率分布来计算。高熵表明样本文本的内容不明确或高度多样化，意味着许多单词被选择的概率相似。在这种情况下，该样本可能是由 LLM 生成的。Lavergne、Urvoy 和 Yvon ([2008](https://arxiv.org/html/2310.14724v3#bib.bib113)) 运用了 Kullback-Leibler (KL) 散度来给 n-gram 分配评分，考虑了它们的初始和最终单词之间的语义关系。这种方法识别出在初始和终端单词之间具有显著依赖关系的 n-gram，从而有助于检测虚假的内容，并提高检测过程的整体性能。

使用困惑度的方法，这种方法基于传统的<math alttext="n" class="ltx_Math" display="inline" id="S5.SS2.SSS2.Px1.p4.1.m1.1"><semantics id="S5.SS2.SSS2.Px1.p4.1.m1.1a"><mi id="S5.SS2.SSS2.Px1.p4.1.m1.1.1" xref="S5.SS2.SSS2.Px1.p4.1.m1.1.1.cmml">n</mi><annotation-xml encoding="MathML-Content" id="S5.SS2.SSS2.Px1.p4.1.m1.1b"><ci id="S5.SS2.SSS2.Px1.p4.1.m1.1.1.cmml" xref="S5.SS2.SSS2.Px1.p4.1.m1.1.1">𝑛</ci></annotation-xml><annotation encoding="application/x-tex" id="S5.SS2.SSS2.Px1.p4.1.m1.1c">n</annotation><annotation encoding="application/x-llamapun" id="S5.SS2.SSS2.Px1.p4.1.m1.1d">italic_n</annotation></semantics></math>-gram 语言模型（LMs），评估语言模型在预测文本方面的能力（Beresneva ([2016](https://arxiv.org/html/2310.14724v3#bib.bib19))）。更近期的工作，例如 HowkGPT Vasilatos 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib220)），通过计算和比较来自学生书写文本和 ChatGPT 生成文本的困惑度得分来区分由 LLM 生成的文本，特别是家庭作业。通过这种比较，建立了阈值来准确识别提交作业的来源。此外，广泛认可的 GPTZero¹⁴¹⁴14[`gptzero.me/`](https://gptzero.me/) 估计评论文本由 LLM 生成的可能性。该估计基于对文本困惑度和爆发度指标的细致检查。在最近的一项研究中，Wu 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib236)）揭示了 LLMDet，这是一个旨在通过计算各种模型对选定 n-grams 的下一词概率来量化和分类困惑度得分的工具。LLMDet 利用文本的内在自水印特性，如代理困惑度，以追踪文本的来源并进行检测。该工具展示了 98.54% 的高分类准确率，同时在计算效率上优于微调的 RoBERTa。此外，Venkatraman、Uchendu 和 Lee（[2023](https://arxiv.org/html/2310.14724v3#bib.bib221)）通过分析文章的标记概率提取基于 UID 的特征，然后训练逻辑回归分类器以拟合不同 LLM 生成文本的 UID 特征，以识别文本的来源。GHOSTBUSTER Verma 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib222)）将 LLM 生成的文本输入到一系列较弱的语言模型中以获得标记概率，然后对这些模型输出的组合进行结构化搜索，训练线性分类器以区分 LLM 生成的文本。该检测器实现了 99.0 的平均 F1 分数，比 GPTZero 和 DetectGPT 等先前方法的 F1 分数提高了 41.6。

##### 基于扰动的方法

一些白盒统计（或零-shot）方法通过比较统计扰动后的性能指标差异来检测 LLM 生成的文本。Mitchell 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib146)) 提出了一种通过分析 LLM 概率函数中的结构模式，特别是在负曲率区域，来识别 LLM 生成的文本的方法。前提是 LLM 生成的文本倾向于聚集在局部对数概率最大值。检测涉及将文本的对数概率与目标 LLM 的对数概率进行比较，使用预训练的掩码填充模型（如 T5）创建语义上类似的文本扰动。

尽管创新且有时比监督方法更有效，但 DetectGPT 仍有局限性，包括如果重写未能充分代表有意义的替代空间，可能会导致性能下降，以及高计算需求，因为它需要评分许多文本扰动。为应对这一挑战，Deng 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib49)) 提出了一种方法，使用贝叶斯替代模型选择少量典型样本进行评分。通过将典型样本的评分插值到其他样本中以提高查询效率，从而将开销减少了一半，同时保持了性能。Bao 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib16)) 报告了一种方法，用更高效的采样步骤替代了 DetectGPT 的扰动步骤，显著提高了约 75% 的检测准确率，并将检测速度提高了 340 倍。与 DetectGPT 不同，DNA-GPT 的白盒配置 Yang 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib244)) 利用 ChatGPT 等大型语言模型继续写作截断的文本，而不是使用扰动设置。它通过计算概率差异来分析原始文本与继续文本之间的差异，实现了接近 100% 的检测性能。另一个近期贡献 DetectLLM Su 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib203)) 与 DetectGPT 的概念框架相似。它使用归一化的扰动对数秩进行由 LLM 生成的文本检测，声称相较于 DetectGPT，对扰动模型和扰动数量的敏感性较低。

##### 内在维度估计

Tulchinskii 等人进行的研究 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib214)) 提出了人类和 LLM 在各自文本领域中展示的能力具有不变性。提出的方法包括构建检测器，利用嵌入文本样本的流形的内在维度。具体来说，该方法涉及计算目标自然语言中流畅的人类书写文本和 LLM 生成文本的内在维度平均值。随后，这两个数据集之间的统计分离有助于建立目标语言的分离阈值，从而实现对 LLM 生成文本的检测。必须承认，这种方法在各种场景中，包括跨领域挑战、模型变化和对抗性攻击，表现出很强的鲁棒性。然而，当面对不理想或高温生成器时，其可靠性会下降。

#### 5.2.3 黑箱统计

与白箱统计方法不同，黑箱统计方法利用黑箱模型计算文本的特定特征分数，而不需要访问源模型或替代模型的 logits。杨等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib244)) 使用 LLMs 继续撰写被审阅的截断文本，并通过计算<math alttext="n" class="ltx_Math" display="inline" id="S5.SS2.SSS3.p1.1.m1.1"><semantics id="S5.SS2.SSS3.p1.1.m1.1a"><mi id="S5.SS2.SSS3.p1.1.m1.1.1" mathcolor="#000000" xref="S5.SS2.SSS3.p1.1.m1.1.1.cmml">n</mi><annotation-xml encoding="MathML-Content" id="S5.SS2.SSS3.p1.1.m1.1b"><ci id="S5.SS2.SSS3.p1.1.m1.1.1.cmml" xref="S5.SS2.SSS3.p1.1.m1.1.1">𝑛</ci></annotation-xml><annotation encoding="application/x-tex" id="S5.SS2.SSS3.p1.1.m1.1c">n</annotation><annotation encoding="application/x-llamapun" id="S5.SS2.SSS3.p1.1.m1.1d">italic_n</annotation></semantics></math>-gram 相似度来定义人类撰写的文本与 LLM 生成的文本。类似地，毛等人 ([2024](https://arxiv.org/html/2310.14724v3#bib.bib141)) 和朱等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib260)) 通过计算原始文本与其改写和修订版本之间的相似度分数来识别 LLM 生成的文本。这些方法基于一个观察，即与 LLM 生成的文本相比，人类撰写的文本在 LLM 被要求进行重写和编辑时往往会触发更多的修订。余等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib250)) 引入了一种检测机制，该机制也利用原始文本与再生文本之间的相似性。与其他方法不同，这种方法最初识别出促使文本生成的原始问题，并根据这一推测的问题重新生成文本。此外，Quidwai、Li 和 Dube ([2023](https://arxiv.org/html/2310.14724v3#bib.bib173)) 分析了 LLM 生成文本及其改写的句子，通过计算余弦相似度将其与人类撰写的文本区分开来，达到了 94%的准确率。郭和余 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib80)) 引入了一种基于去噪的黑箱零样本统计方法，该方法利用黑箱 LLM 去噪输入文本中人为添加的噪声。然后，将去噪后的文本与原始文本进行语义比较，结果 AUROC 分数达到 91.8%。

然而，黑箱统计方法也面临挑战，包括访问 LLM 的显著开销和较长的响应时间。

### 5.3 神经网络基础方法

#### 5.3.1 基于特征的分类器

##### 基于语言特征的分类器

在比较由 LLM 生成的文本与人类撰写的文本时，众多语言特征的差异为基于特征的分类器有效区分它们提供了坚实的基础。这类分类器的工作流程通常从提取关键统计语言特征开始，然后应用机器学习技术来训练分类模型。这种方法在虚假新闻识别中得到了广泛应用。例如，在最近的研究中，Aich、Bhattacharya 和 Parde ([2022](https://arxiv.org/html/2310.14724v3#bib.bib2)) 通过提取 21 个文本特征并使用 KNN 分类器实现了 97% 的令人印象深刻的准确率。受到虚假新闻和 LLM 生成文本检测任务的启发，文本的语言特征可以广泛分类为风格特征、复杂性特征、语义特征、心理特征和基于知识的特征。这些特征主要通过统计方法获得。

风格特征主要关注能够突出文本风格元素的单词频率，包括大写单词、专有名词、动词、过去时单词、停用词、技术词汇、引号和标点符号的频率 Horne 和 Adali ([2017](https://arxiv.org/html/2310.14724v3#bib.bib88))。复杂性特征用于展示文本的复杂度，如类型-标记比率（TTR）和文本词汇多样性（MTLD） McCarthy ([2005](https://arxiv.org/html/2310.14724v3#bib.bib143))。语义特征包括高级语义（AdSem）、词汇语义（LxSem）以及语义依赖标签的统计信息等。这些特征可以使用像 LingFeat 这样的工具提取 Lee、Jang 和 Lee ([2021](https://arxiv.org/html/2310.14724v3#bib.bib114))。心理特征通常与情感分析相关，可以基于像 SentiWordNet 这样的工具计算情感分数或使用情感分类器提取 Baccianella、Esuli 和 Sebastiani ([2010](https://arxiv.org/html/2310.14724v3#bib.bib14))。信息特征包括命名实体（NE）、意见（OP）和实体关系提取（RE），可以使用像 UIE 和 CogIE 这样的工具提取 Lu 等 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib135)) 和 Jin 等 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib97))。

Shah 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib192)) 基于音节数、词长、句子结构、功能词使用频率以及标点符号比例等风格特征构建了一个分类器。该分类器达到了 93%的准确率，有效地展示了风格特征对于 LLM 生成文本检测的重要性。其他研究通过数据融合技术将文本建模与各种语言特征相结合，如 Corizzo 和 Leal-Arenas ([2023](https://arxiv.org/html/2310.14724v3#bib.bib40))，这些特征包括不同类型的标点符号、牛津逗号的使用、段落结构、平均句子长度、高频词的重复性以及情感评分。在英语和西班牙语数据集上，该方法分别达到了 98.36%和 98.29%的 F1 分数，表明其卓越的性能。Mindner、Schlippe 和 Schaaff ([2023](https://arxiv.org/html/2310.14724v3#bib.bib144)) 进一步采用了多维度方法来增强分类器的区分能力，这包括复杂度测量、语义分析、列表搜索、基于错误的特征、可读性评估、人工智能反馈和文本向量特征。最终，优化后的检测器在 F1 分数上超越了 GPTZero 183.8%，展现了其优越的检测能力。

尽管基于语言特征的分类器在区分人工和 AI 生成文本方面具有其优势，但其不足之处也不容忽视。Schaaff、Schlippe 和 Mindner ([2023](https://arxiv.org/html/2310.14724v3#bib.bib185)) 的结果表明，这类特征分类器对模糊语义的鲁棒性较差，且往往不如神经网络特征表现良好。此外，基于风格特征的分类器可能能够区分由人类撰写的文本和由 LLM 生成的文本，但其检测 LLM 生成虚假信息的能力有限。Schuster 等人 ([2020a](https://arxiv.org/html/2310.14724v3#bib.bib189)) 强调了这一限制，表明语言模型往往会生成风格一致的文本。然而，Crothers 等人 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib45)) 建议统计特征可以提供额外的对抗鲁棒性，并可用于构建集成检测模型。

##### 基于模型特征的分类器

除了语言特征之外，基于模型特征的分类器最近受到了研究人员的广泛关注。这些分类器不仅能够检测由 LLM 生成的文本，还可以用于文本来源追踪。Sniffer Li 等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib118)）涉及提取对齐的标记级困惑度和对比特征，这些特征在比较一个模型<math alttext="\theta_{i}" class="ltx_Math" display="inline" id="S5.SS3.SSS1.Px2.p1.1.m1.1"><semantics id="S5.SS3.SSS1.Px2.p1.1.m1.1a"><msub id="S5.SS3.SSS1.Px2.p1.1.m1.1.1" xref="S5.SS3.SSS1.Px2.p1.1.m1.1.1.cmml"><mi id="S5.SS3.SSS1.Px2.p1.1.m1.1.1.2" mathcolor="#000000" xref="S5.SS3.SSS1.Px2.p1.1.m1.1.1.2.cmml">θ</mi><mi id="S5.SS3.SSS1.Px2.p1.1.m1.1.1.3" mathcolor="#000000" xref="S5.SS3.SSS1.Px2.p1.1.m1.1.1.3.cmml">i</mi></msub><annotation-xml encoding="MathML-Content" id="S5.SS3.SSS1.Px2.p1.1.m1.1b"><apply id="S5.SS3.SSS1.Px2.p1.1.m1.1.1.cmml" xref="S5.SS3.SSS1.Px2.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S5.SS3.SSS1.Px2.p1.1.m1.1.1.1.cmml" xref="S5.SS3.SSS1.Px2.p1.1.m1.1.1">subscript</csymbol><ci id="S5.SS3.SSS1.Px2.p1.1.m1.1.1.2.cmml" xref="S5.SS3.SSS1.Px2.p1.1.m1.1.1.2">𝜃</ci><ci id="S5.SS3.SSS1.Px2.p1.1.m1.1.1.3.cmml" xref="S5.SS3.SSS1.Px2.p1.1.m1.1.1.3">𝑖</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S5.SS3.SSS1.Px2.p1.1.m1.1c">\theta_{i}</annotation><annotation encoding="application/x-llamapun" id="S5.SS3.SSS1.Px2.p1.1.m1.1d">italic_θ start_POSTSUBSCRIPT italic_i end_POSTSUBSCRIPT</annotation></semantics></math>与另一个模型<math alttext="\theta_{j}" class="ltx_Math" display="inline" id="S5.SS3.SSS1.Px2.p1.2.m2.1"><semantics id="S5.SS3.SSS1.Px2.p1.2.m2.1a"><msub id="S5.SS3.SSS1.Px2.p1.2.m2.1.1" xref="S5.SS3.SSS1.Px2.p1.2.m2.1.1.cmml"><mi id="S5.SS3.SSS1.Px2.p1.2.m2.1.1.2" mathcolor="#000000" xref="S5.SS3.SSS1.Px2.p1.2.m2.1.1.2.cmml">θ</mi><mi id="S5.SS3.SSS1.Px2.p1.2.m2.1.1.3" mathcolor="#000000" xref="S5.SS3.SSS1.Px2.p1.2.m2.1.1.3.cmml">j</mi></msub><annotation-xml encoding="MathML-Content" id="S5.SS3.SSS1.Px2.p1.2.m2.1b"><apply id="S5.SS3.SSS1.Px2.p1.2.m2.1.1.cmml" xref="S5.SS3.SSS1.Px2.p1.2.m2.1.1"><csymbol cd="ambiguous" id="S5.SS3.SSS1.Px2.p1.2.m2.1.1.1.cmml" xref="S5.SS3.SSS1.Px2.p1.2.m2.1.1">subscript</csymbol><ci id="S5.SS3.SSS1.Px2.p1.2.m2.1.1.2.cmml" xref="S5.SS3.SSS1.Px2.p1.2.m2.1.1.2">𝜃</ci><ci id="S5.SS3.SSS1.Px2.p1.2.m2.1.1.3.cmml" xref="S5.SS3.SSS1.Px2.p1.2.m2.1.1.3">𝑗</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S5.SS3.SSS1.Px2.p1.2.m2.1c">\theta_{j}</annotation><annotation encoding="application/x-llamapun" id="S5.SS3.SSS1.Px2.p1.2.m2.1d">italic_θ start_POSTSUBSCRIPT italic_j end_POSTSUBSCRIPT</annotation></semantics></math>时，测量在比较一个模型与另一个模型时困惑度较低的单词的百分比。通过使用这些特征训练线性分类器，实现了 86.0%的准确率。SeqXGPT Wang 等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib226)）在文本来源追踪领域进行了进一步探索，基于提出的特征设计了一个将 CNN 与两层变换器结合用于编码文本的上下文网络，并通过序列标注任务检测 LLM 生成的文本。Wu 和 Xiang（[2023](https://arxiv.org/html/2310.14724v3#bib.bib237)）的研究考虑了如对数似然、对数秩、熵和 LLM 偏差等特征的组合，并通过训练神经网络分类器，获得了 98.41%的平均 F1 分数。然而，这些方法的一个共同缺点是都需要访问源模型的 logits。对于那些 logits 无法访问的其他强大的封闭源模型，这些方法可能难以发挥有效作用。

#### 5.3.2 预训练分类器

##### 领域内微调即为**终极**解决方案

在这一小节中，我们探讨了微调基于 Transformer 的语言模型（LM）以区分由 LLM 生成的输入文本与非 LLM 生成文本的方法。这种方法需要配对样本来促进监督训练过程。根据 Qiu 等人（[2020](https://arxiv.org/html/2310.14724v3#bib.bib172)）的研究，预训练的语言模型在自然语言理解方面表现强大，这对提升 NLP 中的各种任务至关重要，其中文本分类尤为值得关注。著名的预训练模型，如 BERT Devlin 等人（[2019a](https://arxiv.org/html/2310.14724v3#bib.bib51)）、Roberta Liu 等人（[2019](https://arxiv.org/html/2310.14724v3#bib.bib132)）和 XLNet Yang 等人（[2019](https://arxiv.org/html/2310.14724v3#bib.bib245)），在应用于 GLUE 基准中的文本分类任务时，相较于传统统计机器学习和深度学习的同行，展示了**卓越**的表现 Wang 等人（[2019](https://arxiv.org/html/2310.14724v3#bib.bib225)）。

此外，已有大量的先前研究（Bakhtin 等人，[2019](https://arxiv.org/html/2310.14724v3#bib.bib15)；Uchendu 等人，[2020](https://arxiv.org/html/2310.14724v3#bib.bib217)；Antoun 等人，[2023a](https://arxiv.org/html/2310.14724v3#bib.bib6)；Li 等人，[2023c](https://arxiv.org/html/2310.14724v3#bib.bib120)）详细考察了微调语言模型在检测 LLM 生成文本方面的能力。值得注意的是，2019 年的研究确认了微调语言模型，特别是 Roberta Liu 等人（[2019](https://arxiv.org/html/2310.14724v3#bib.bib132)）在检测 LLM 生成文本方面尤为出色。在接下来的讨论中，我们将介绍这一领域的最新学术贡献，提供方法的更新综述和总结。

微调 Roberta 为检测由 LLMs 生成的文本提供了一个稳健的基线。Fagni 等人 ([2021](https://arxiv.org/html/2310.14724v3#bib.bib60)) 观察到微调 Roberta 在各种编码配置中产生了最佳的分类结果，Gambini 等人 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib66)) 也发现类似的情况，随后 OpenAI 的检测器（Radford 等人，[2019](https://arxiv.org/html/2310.14724v3#bib.bib174)）也采用了 Roberta 微调的方法。近期的研究如 Guo 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib78))、Liu 等人 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib131)，[d](https://arxiv.org/html/2310.14724v3#bib.bib133))、Chen 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib32)) 和 Wang 等人 ([2023c](https://arxiv.org/html/2310.14724v3#bib.bib228)，[c](https://arxiv.org/html/2310.14724v3#bib.bib228)) 进一步证实了微调 BERT 系列成员（如 RoBERTa）在识别 LLM 生成文本方面的卓越表现。平均而言，这些微调模型在各自领域中达到了 95% 的准确率，优于零-shot 和水印方法，并在领域内设置中表现出一定的攻击抗性。然而，像它们的同行一样，这些基于编码器的微调方法也缺乏鲁棒性（Bakhtin 等人，[2019](https://arxiv.org/html/2310.14724v3#bib.bib15)；Uchendu 等人，[2020](https://arxiv.org/html/2310.14724v3#bib.bib217)；Antoun 等人，[2023a](https://arxiv.org/html/2310.14724v3#bib.bib6)；Li 等人，[2023c](https://arxiv.org/html/2310.14724v3#bib.bib120)），因为它们倾向于过拟合训练数据或源模型的训练分布，导致在面对跨域或未见数据时性能下降。此外，微调语言模型分类器在应对由不同模型生成的数据时也有限制（Sarvazyan 等人，[2023a](https://arxiv.org/html/2310.14724v3#bib.bib183)）。尽管如此，基于 RoBERTa 的检测器展示了显著的鲁棒性潜力，仅需几百个标签进行微调即可获得令人印象深刻的结果（Rodriguez 等人，[2022b](https://arxiv.org/html/2310.14724v3#bib.bib180)）。mBERT（Devlin 等人，[2019b](https://arxiv.org/html/2310.14724v3#bib.bib52)）在文档级别的 LLM 生成文本分类和各种模型归属设置中表现出一致的强大性能，尤其是在英语和西班牙语任务中表现最佳。相比之下，像 XLM-RoBERTa（Conneau 等人，[2020](https://arxiv.org/html/2310.14724v3#bib.bib39)）和 TinyBERT（Jiao 等人，[2020](https://arxiv.org/html/2310.14724v3#bib.bib95)）这样的编码器模型在相同的文档级别任务和模型归属设置中显示出显著的性能差异，表明这两项任务可能需要模型具备不同的能力。

##### 对比学习

数据稀缺推动了对比学习在基于语言模型（LM）的分类器中的应用，核心在于自监督学习。此策略通过空间变换最小化锚点与正样本之间的距离，同时最大化与负样本之间的距离。刘等人（[2022](https://arxiv.org/html/2310.14724v3#bib.bib130)）提出的增强对比损失对难负样本赋予更大权重，从而优化模型效用并刺激性能提升，尤其在低资源环境中表现突出。该方法全面考虑了语言特征和句子结构，将文本表示为连贯图，以 encapsulate 其固有的实体一致性。研究结果确认了纳入信息事实结构以改进基于 LM 的检测器效能的有效性，这一结论也得到了钟等人（[2020](https://arxiv.org/html/2310.14724v3#bib.bib259)）的呼应。Bhattacharjee 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib22)）提出了 ConDA，一个对比领域适应框架，将标准领域适应技术与对比学习的表示能力相结合，大大提高了模型对未知模型的防御能力。

##### 对抗学习方法

鉴于检测器对不同攻击的脆弱性和鲁棒性问题，大量学术研究致力于将对抗学习作为缓解策略。对抗学习方法主要与微调 LM 方法相关。Koike、Kaneko 和 Okazaki（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib105)）的最新研究表明，在不微调模型的情况下，利用上下文指导参数冻结的模型进行对抗训练是可行的。我们将这些研究分为两类：基于样本增强的对抗训练和双玩家博弈。

在基于样本增强的对抗训练中，一个显著的方法是部署基于样本增强的对抗攻击，其主要目标是制造欺骗性输入，从而提高模型应对更多潜在欺骗场景的能力。具体而言，这种方法强调样本增强的重要性，并通过注入预定的对抗攻击来实现这一点。这一增强过程对提升检测器的鲁棒性至关重要，因为它提供了一个扩展的对抗样本池。文章的第 7.2 节概述了各种潜在的攻击机制，包括同义改写攻击、对抗攻击和提示攻击。杨、姜和李（[2023](https://arxiv.org/html/2310.14724v3#bib.bib241)）；石等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib196)）；何等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib83)）对 LLM 生成的文本进行了对抗数据增强过程，研究结果表明，基于精心增强的数据训练的模型在应对潜在攻击方面表现出了令人赞赏的鲁棒性。

双人游戏的方法根本上与生成对抗网络的基本原则一致（Goodfellow 等，[2020](https://arxiv.org/html/2310.14724v3#bib.bib75)），以及“破坏-修复”策略（Yasunaga 和 Liang，[2021](https://arxiv.org/html/2310.14724v3#bib.bib247)），通常涉及攻击模型与检测模型的配置，二者的迭代对抗最终提升了检测能力。Hu、Chen 和 Ho（[2023](https://arxiv.org/html/2310.14724v3#bib.bib90)）介绍了一个名为 RADAR 的框架，旨在通过对抗学习同时训练鲁棒的检测器。该框架促进了一个负责生成逃避检测的真实内容的改写模型与一个旨在提高其识别 LLM 生成文本能力的检测器之间的互动。RADAR 框架逐步完善改写模型，借助检测器获得的反馈，并采用 PPO（Schulman 等，[2017b](https://arxiv.org/html/2310.14724v3#bib.bib188)）。尽管在对抗改写攻击方面表现出色，Hu、Chen 和 Ho（[2023](https://arxiv.org/html/2310.14724v3#bib.bib90)）的研究未对 RADAR 的其他攻击模式下的防御机制进行全面分析。与之平行，Koike、Kaneko 和 Okazaki（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib105)）提出了一种基于攻击者与检测器之间持续互动的检测器训练方法。与 RADAR 不同，OUTFOX 更强调检测器使用 ICL（Dong 等，[2023](https://arxiv.org/html/2310.14724v3#bib.bib55)）进行攻击者识别的可能性。具体而言，OUTFOX 框架中的攻击者利用检测器预测的标签作为 ICL 示例生成具有检测挑战的文本。相反，检测器使用对抗生成的内容作为 ICL 示例，以提升其对强大攻击者的检测能力。这种对彼此输出的相互考虑促进了检测器对 LLM 生成文本的更强鲁棒性。实证证据证明，OUTFOX 方法相较于之前的统计方法和基于 RoBERTa 的方法表现更优，特别是在应对 TF-IDF 和 DIPPER Krishna 等（[2023](https://arxiv.org/html/2310.14724v3#bib.bib107)）的攻击时。

##### 特性增强方法

除了训练方法的改进，Tu 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib213)) 证明了语言特征的提取可以有效提高基于 RoBERTa 的检测器的鲁棒性，并在各种相关模型中观察到了好处。Cowap、Graham 和 Foster ([2023](https://arxiv.org/html/2310.14724v3#bib.bib42)) 通过对情感分析进行预训练语言模型 (PLM) 的微调，开发了一种情感感知检测器，从而提升了情感作为识别合成文本的信号的潜力。他们通过进一步微调 BERT 专门用于情感分类，结果使检测性能的 F1 分数提高了多达 9.03%。Uchendu、Le 和 Lee ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib216)) 使用 RoBERTa 捕捉上下文表示，例如语义和句法语言特征，并整合了拓扑数据分析来分析数据的形状和结构，包括语言结构。这种方法在 SynSciPass 和 M4 数据集上的表现超越了单独使用 RoBERTa 的效果。框架 J-GuardKumarage 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib110)) 指导现有的监督 AI 文本检测器通过提取新闻特征来检测 AI 生成的新闻，从而帮助检测器识别 LLM 生成的虚假新闻文本。该框架表现出强大的鲁棒性，在面对对抗性攻击时，平均性能下降保持在 7% 以下。

#### 5.3.3 大型语言模型作为检测器

##### 使用大型语言模型的可靠性问题

许多研究探讨了利用大型语言模型（LLMs）作为检测器来识别由它们自己或其他 LLMs 生成的文本的可行性。这一方法首次由 Zellers 等人提出（[2019b](https://arxiv.org/html/2310.14724v3#bib.bib253)），其中生成文本的模型 Grover 被发现生成的虚假信息非常具有欺骗性，因为其固有的可控性。Zellers 等人（[2019b](https://arxiv.org/html/2310.14724v3#bib.bib253)）随后通过不同架构模型如 GPT-2（Radford 等人，[2019](https://arxiv.org/html/2310.14724v3#bib.bib174)）和 BERT（Devlin 等人，[2019c](https://arxiv.org/html/2310.14724v3#bib.bib53)）的探索性分析揭示，Grover 最有效的对策就是 Grover 本身，准确率高达 92%，而其他检测器类型的准确率则随着 Grover 规模的增加而下降至约 70%。Bhattacharjee 和 Liu（[2023](https://arxiv.org/html/2310.14724v3#bib.bib23)）对更近期的 LLMs 如 ChatGPT 和 GPT-4 进行的重新评估显示，两者都无法可靠地识别由各种 LLMs 生成的文本。在观察中发现，ChatGPT 和 GPT-4 表现出截然不同的趋势。ChatGPT 倾向于将 LLMs 生成的文本归类为人类编写的，误分类概率约为 50%。而 GPT-4 则倾向于将人类编写的文本标记为 LLMs 生成的，大约 95%的人类编写的文本被误分类为 LLMs 生成的文本。ArguGPT（Liu 等人，[2023c](https://arxiv.org/html/2310.14724v3#bib.bib131)）进一步证明了 GPT-4-Turbo 在检测 LLMs 生成的文本方面表现平平，准确率在零-shot、one-shot 和 two-shot 设置下均低于 50%。这些发现共同展示了在直接自生成文本检测中使用 LLMs 的可靠性逐渐降低，尤其是与统计和神经网络方法相比。这在 LLMs 复杂性日益增加的背景下尤为明显。

##### ICL：LLM 基础检测的强大技术

尽管使用 LLM 直接检测 LLM 生成文本存在不可靠的问题，但最近的实证研究突出了 ICL 在增强 LLM 检测能力方面的潜在效能。ICL，一种专门的提示工程形式，将示例融入模型提供的提示中，从而促进 LLM 对新任务的学习。通过 ICL，现有的 LLM 可以熟练地处理不同任务，而无需额外的微调。OUTFOX Detector Koike, Kaneko, 和 Okazaki ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib105))采用了 ICL 方法，持续向 LLM 提供示例样本用于文本生成检测任务。实验结果表明，ICL 策略优于传统的零样本方法和基于 RoBERTa 的检测器。

### 5.4 人工辅助方法

在本节中，我们将深入探讨用于检测由 LLM 生成的文本的人工辅助方法。这些方法利用人类的先验知识和分析技能，为检测过程提供了显著的可解释性和可信度。

#### 5.4.1 直观指标

多项研究已经深入探讨了人类和机器分类能力之间的差异。人类分类主要依赖于视觉观察，以辨别 LLM 生成的文本的特征。Uchendu 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib218)）指出，LLM 生成的文本缺乏连贯性和一致性，这是伪造内容的一个强烈指标。LLM 生成的文本通常表现出语义上的不一致和逻辑错误。此外，Dugan 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib58)）发现，人们对 LLM 生成的文本的认知在不同领域之间存在差异。例如，在新闻领域，LLM 倾向于生成更“普通”的文本，而在故事领域，文本可能更“不相关”。Ma 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib138)）指出，学术写作的评估者通常强调风格。LLM 生成的摘要通常缺乏细节，特别是在描述研究动机和方法时，这妨碍了新见解的提供。相反，LLM 生成的论文中存在较少的语法和其他类型的错误，展示了更广泛的表达方式（Yan 等人，[2023](https://arxiv.org/html/2310.14724v3#bib.bib238)；Liao 等人，[2023a](https://arxiv.org/html/2310.14724v3#bib.bib124)）。然而，这些论文通常使用一般术语，而不是针对特定问题背景的有效定制信息。在人为撰写的文本中，如科学论文中，作者倾向于撰写冗长的段落和使用含糊的语言（Desaire 等人，[2023](https://arxiv.org/html/2310.14724v3#bib.bib50)），经常加入诸如“但是”、“然而”和“虽然”等术语。Dugan 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib58)）也指出，仅依赖语法错误作为检测策略是不可靠的。此外，LLM 经常出现事实和常识推理错误，这些错误虽然经常被基于神经网络的检测器忽略，但却很容易被人类注意到（Jawahar，Abdul-Mageed 和 Lakshmanan，[2020](https://arxiv.org/html/2310.14724v3#bib.bib93)）。

#### 5.4.2 无法察觉的特征

Ippolito 等人 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib92)) 提出，人类认为高质量的文本往往更容易被检测器识别。这一观察结果表明，一些对人类不可感知的特征可以被检测算法有效捕捉。尽管人类在识别许多 LLM 生成的文本中的错误方面非常擅长，但未被看到的特征也显著影响了人类的决策过程。相比之下，零-shot 检测器研究中常用的统计阈值用于区分 LLM 生成的文本可能会被操控。然而，人类通常具备通过各种指标检测这些操控的能力，GLTR Gehrmann、Strobelt 和 Rush ([2019](https://arxiv.org/html/2310.14724v3#bib.bib71)) 开创了这一方法，作为一种视觉取证工具来协助人类审查过程，同时提供了非专家也容易理解的丰富解释 Clark 等人 ([2021b](https://arxiv.org/html/2310.14724v3#bib.bib38))。

#### 5.4.3 增强人类检测能力

最近的研究 Ippolito 等人 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib92)) 指出，人类评估者在不同环境下识别 LLM 生成的文本可能不如检测算法熟练。然而，在评估前向评估者展示示例可以增强他们的检测能力，尤其是对较长样本的检测。平台 RoFT Dugan 等人 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib57)) 允许用户与 LLM 生成的文本互动，揭示了人类对这些文本的感知。尽管在标注后揭示真实界限并未立即提高标注员的准确性，但值得注意的是，通过适当的激励和动机，标注员确实可以随着时间的推移提高他们的表现 Dugan 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib58))。SCARECROW 框架 Dou 等人 ([2022](https://arxiv.org/html/2310.14724v3#bib.bib56)) 促进了对 LLM 生成文本的标注和审查，列出了十种错误类型以指导用户。SCARECROW 的结果报告显示，人工标注在一半的错误类型上优于检测模型，表明尽管存在人力开销，但开发高效的标注系统仍具有潜力。

#### 5.4.4 混合检测：理解与解释

Weng 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib233)) 引入了一个将人类专业知识与机器智能相结合的原型，用于视觉分析，前提是人类判断是基准。最初，专家根据他们的先验知识标记文本，阐明人工与 LLM 生成文本之间的区别。随后，机器学习模型基于标记数据进行训练和迭代优化。最后，通过视觉统计分析选择最直观的检测器，以实现检测目的。这种细致的分析方法不仅增强了专家对决策模型的信任，还促进了从模型行为中学习，以有效识别 LLM 生成的样本。

## 6 评估指标

评估指标在任何 NLP 任务中的模型性能评估中都是不可或缺的，值得细致考虑。在本节中，我们列举并讨论了常用于 LLM 生成文本检测任务的指标。这些指标包括准确率、配对准确率、非配对准确率、召回率、人工编写召回率（HumanRec）、LLM 生成召回率（LLMRec）、平均召回率（AvgRec）、F1 分数和接收者操作特征曲线下面积（AUROC）。此外，我们讨论了每个指标的优缺点，以便为后续研究中的不同情境选择合适的指标。

混淆矩阵可以有效地评估分类任务的性能，并描述 LLM 生成文本检测任务的所有可能结果（共四种类型）：

+   •

    真阳性 (TP) 指模型正确分类的正类结果（LLM 生成的文本）。

+   •

    真阴性 (TN) 指模型正确分类的负类结果（人工编写的文本）。

+   •

    假阳性 (FP) 指模型错误分类的正类结果（LLM 生成的文本）。

+   •

    假阴性 (FN) 指模型错误预测的负类结果（人工编写的文本）。

下文介绍的评估指标均可用 TP、TN、FP 和 FP 来描述。

##### 准确率

准确率作为一个通用指标，表示正确分类的文本与总文本数量的比率。虽然在平衡数据集上适用，但对于不平衡的数据集，由于对类别不平衡的敏感性，其效用会降低。配对和未配对准确率指标也在 Zellers 等人 ([2019b](https://arxiv.org/html/2310.14724v3#bib.bib253)) 和 Zhong 等人 ([2020](https://arxiv.org/html/2310.14724v3#bib.bib259)) 的研究中得到了应用，用于评估检测器在不同场景下的能力。在未配对设置中，鉴别器必须独立地将每个测试样本分类为人类或机器。在配对设置中，模型会接收到两个具有相同元数据的测试样本，一个是真实的，另一个是由大模型生成的。鉴别器必须为由大模型生成的文章分配更高的机器概率，而不是为人类撰写的文章分配。这些指标用于测量算法在不同场景下的数据性能。相对而言，未配对设置的检测难度高于配对设置。准确率可以用以下公式描述：

|  | <math alttext="\displaystyle Accuracy" class="ltx_Math" display="inline" id="S6.E4X.2.1.1.m1.1"><semantics id="S6.E4X.2.1.1.m1.1a"><mrow id="S6.E4X.2.1.1.m1.1.1" xref="S6.E4X.2.1.1.m1.1.1.cmml"><mi id="S6.E4X.2.1.1.m1.1.1.2" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.2.cmml">A</mi><mo id="S6.E4X.2.1.1.m1.1.1.1" xref="S6.E4X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E4X.2.1.1.m1.1.1.3" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.3.cmml">c</mi><mo id="S6.E4X.2.1.1.m1.1.1.1a" xref="S6.E4X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E4X.2.1.1.m1.1.1.4" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.4.cmml">c</mi><mo id="S6.E4X.2.1.1.m1.1.1.1b" xref="S6.E4X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E4X.2.1.1.m1.1.1.5" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.5.cmml">u</mi><mo id="S6.E4X.2.1.1.m1.1.1.1c" xref="S6.E4X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E4X.2.1.1.m1.1.1.6" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.6.cmml">r</mi><mo id="S6.E4X.2.1.1.m1.1.1.1d" xref="S6.E4X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E4X.2.1.1.m1.1.1.7" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.7.cmml">a</mi><mo id="S6.E4X.2.1.1.m1.1.1.1e" xref="S6.E4X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E4X.2.1.1.m1.1.1.8" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.8.cmml">c</mi><mo id="S6.E4X.2.1.1.m1.1.1.1f" xref="S6.E4X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E4X.2.1.1.m1.1.1.9" mathsize="90%" xref="S6.E4X.2.1.1.m1.1.1.9.cmml">y</mi></mrow><annotation-xml encoding="MathML-Content" id="S6.E4X.2.1.1.m1.1b"><apply id="S6.E4X.2.1.1.m1.1.1.cmml" xref="S6.E4X.2.1.1.m1.1.1"><ci id="S6.E4X.2.1.1.m1.1.1.2.cmml" xref="S6.E4X.2.1.1.m1.1.1.2">𝐴</ci><ci id="S6.E4X.2.1.1.m1.1.1.3.cmml" xref="S6.E4X.2.1.1.m1.1.1.3">𝑐</ci><ci id="S6.E4X.2.1.1.m1.1.1.4.cmml" xref="S6.E4X.2.1.1.m1.1.1.4">𝑐</ci><ci id="S6.E4X.2.1.1.m1.1.1.5.cmml" xref="S6.E4X.2.1.1.m1.1.1.5">𝑢</ci><ci id="S6.E4X.2.1.1.m1.1.1.6.cmml" xref="S6.E4X.2.1.1.m1.1.1.6">𝑟</ci><ci id="S6.E4X.2.1.1.m1.1.1.7.cmml" xref="S6.E4X.2.1.1.m1.1.1.7">𝑎</ci><ci id="S6.E4X.2.1.1.m1.1.1.8.cmml" xref="S6.E4X.2.1.1.m1.1.1.8">𝑐</ci><ci id="S6.E4X.2.1.1.m1.1.1.9.cmml" xref="S6.E4X.2.1.1.m1.1.1.9">𝑦</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E4X.2.1.1.m1.1c">\displaystyle Accuracy</annotation><annotation encoding="application/x-llamapun" id="S6.E4X.2.1.1.m1.1d">italic_A italic_c italic_c italic_u italic_r italic_a italic_c italic_y</annotation></semantics></math> | <math alttext="\displaystyle=\frac{\text{correctly detected samples}}{\text{all samples}}" class="ltx_Math" display="inline" id="S6.E4X.3.2.2.m1.1"><semantics id="S6.E4X.3.2.2.m1.1a"><mrow id="S6.E4X.3.2.2.m1.1.1" xref="S6.E4X.3.2.2.m1.1.1.cmml"><mo id="S6.E4X.3.2.2.m1.1.1.1" mathsize="90%" xref="S6.E4X.3.2.2.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E4X.3.2.2.m1.1.1.3" xref="S6.E4X.3.2.2.m1.1.1.3.cmml"><mfrac id="S6.E4X.3.2.2.m1.1.1.3a" xref="S6.E4X.3.2.2.m1.1.1.3.cmml"><mtext id="S6.E4X.3.2.2.m1.1.1.3.2" mathsize="90%" xref="S6.E4X.3.2.2.m1.1.1.3.2a.cmml">correctly detected samples</mtext><mtext id="S6.E4X.3.2.2.m1.1.1.3.3" mathsize="90%" xref="S6.E4X.3.2.2.m1.1.1.3.3a.cmml">all samples</mtext></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E4X.3.2.2.m1.1b"><apply id="S6.E4X.3.2.2.m1.1.1.cmml" xref="S6.E4X.3.2.2.m1.1.1"><csymbol cd="latexml" id="S6.E4X.3.2 |
| --- | --- | --- |
|  |  | <math alttext="\displaystyle=\frac{TP+TN}{TP+TN+FP+FN}" class="ltx_Math" display="inline" id="S6.E4Xa.2.1.1.m1.1"><semantics id="S6.E4Xa.2.1.1.m1.1a"><mrow id="S6.E4Xa.2.1.1.m1.1.1" xref="S6.E4Xa.2.1.1.m1.1.1.cmml"><mo id="S6.E4Xa.2.1.1.m1.1.1.1" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E4Xa.2.1.1.m1.1.1.3" xref="S6.E4Xa.2.1.1.m1.1.1.3.cmml"><mfrac id="S6.E4Xa.2.1.1.m1.1.1.3a" xref="S6.E4Xa.2.1.1.m1.1.1.3.cmml"><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.2" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.cmml"><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.2.2" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.2.cmml"><mi id="S6.E4Xa.2.1.1.m1.1.1.3.2.2.2" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.2.2.cmml">T</mi><mo id="S6.E4Xa.2.1.1.m1.1.1.3.2.2.1" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E4Xa.2.1.1.m1.1.1.3.2.2.3" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.2.3.cmml">P</mi></mrow><mo id="S6.E4Xa.2.1.1.m1.1.1.3.2.1" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.1.cmml">+</mo><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.2.3" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.3.cmml"><mi id="S6.E4Xa.2.1.1.m1.1.1.3.2.3.2" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.3.2.cmml">T</mi><mo id="S6.E4Xa.2.1.1.m1.1.1.3.2.3.1" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.3.1.cmml">⁢</mo><mi id="S6.E4Xa.2.1.1.m1.1.1.3.2.3.3" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.2.3.3.cmml">N</mi></mrow></mrow><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.3" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.cmml"><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.3.2" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.2.cmml"><mi id="S6.E4Xa.2.1.1.m1.1.1.3.3.2.2" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.2.2.cmml">T</mi><mo id="S6.E4Xa.2.1.1.m1.1.1.3.3.2.1" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E4Xa.2.1.1.m1.1.1.3.3.2.3" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.2.3.cmml">P</mi></mrow><mo id="S6.E4Xa.2.1.1.m1.1.1.3.3.1" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.3.3" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.3.cmml"><mi id="S6.E4Xa.2.1.1.m1.1.1.3.3.3.2" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.3.2.cmml">T</mi><mo id="S6.E4Xa.2.1.1.m1.1.1.3.3.3.1" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.3.1.cmml">⁢</mo><mi id="S6.E4Xa.2.1.1.m1.1.1.3.3.3.3" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.3.3.cmml">N</mi></mrow><mo id="S6.E4Xa.2.1.1.m1.1.1.3.3.1a" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.3.4" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.4.cmml"><mi id="S6.E4Xa.2.1.1.m1.1.1.3.3.4.2" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.4.2.cmml">F</mi><mo id="S6.E4Xa.2.1.1.m1.1.1.3.3.4.1" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.4.1.cmml">⁢</mo><mi id="S6.E4Xa.2.1.1.m1.1.1.3.3.4.3" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.4.3.cmml">P</mi></mrow><mo id="S6.E4Xa.2.1.1.m1.1.1.3.3.1b" mathsize="90%" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E4Xa.2.1.1.m1.1.1.3.3.5" xref="S6.E4Xa.2.1.1.m1.1.1.3.3.5.cmml"><mi id="S6.E4Xa.2.1.1.m1.1.1.3.3 |

##### 精确度

精确度是对实际预测准确性的衡量，指的是在所有检测到的 LLM 生成样本中，正确检测到的 LLM 生成样本的比例。这个指标在我们担心假阳性结果的情况下非常有用。当一个样本不是 LLM 生成的，但被分类为 LLM 生成文本时，这种错误结果可能会降低用户对模型的印象，甚至对业务造成负面影响。因此，提高精确度在 LLM 生成文本检测任务中也很重要。这个指标可以通过以下公式描述：

|  | <math alttext="\displaystyle 精度" class="ltx_Math" display="inline" id="S6.E5X.2.1.1.m1.1"><semantics id="S6.E5X.2.1.1.m1.1a"><mrow id="S6.E5X.2.1.1.m1.1.1" xref="S6.E5X.2.1.1.m1.1.1.cmml"><mi id="S6.E5X.2.1.1.m1.1.1.2" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.2.cmml">P</mi><mo id="S6.E5X.2.1.1.m1.1.1.1" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.3" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.3.cmml">r</mi><mo id="S6.E5X.2.1.1.m1.1.1.1a" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.4" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.4.cmml">e</mi><mo id="S6.E5X.2.1.1.m1.1.1.1b" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.5" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.5.cmml">c</mi><mo id="S6.E5X.2.1.1.m1.1.1.1c" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.6" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.6.cmml">i</mi><mo id="S6.E5X.2.1.1.m1.1.1.1d" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.7" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.7.cmml">s</mi><mo id="S6.E5X.2.1.1.m1.1.1.1e" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.8" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.8.cmml">i</mi><mo id="S6.E5X.2.1.1.m1.1.1.1f" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.9" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.9.cmml">o</mi><mo id="S6.E5X.2.1.1.m1.1.1.1g" xref="S6.E5X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E5X.2.1.1.m1.1.1.10" mathsize="90%" xref="S6.E5X.2.1.1.m1.1.1.10.cmml">n</mi></mrow><annotation-xml encoding="MathML-Content" id="S6.E5X.2.1.1.m1.1b"><apply id="S6.E5X.2.1.1.m1.1.1.cmml" xref="S6.E5X.2.1.1.m1.1.1"><ci id="S6.E5X.2.1.1.m1.1.1.2.cmml" xref="S6.E5X.2.1.1.m1.1.1.2">𝑃</ci><ci id="S6.E5X.2.1.1.m1.1.1.3.cmml" xref="S6.E5X.2.1.1.m1.1.1.3">𝑟</ci><ci id="S6.E5X.2.1.1.m1.1.1.4.cmml" xref="S6.E5X.2.1.1.m1.1.1.4">𝑒</ci><ci id="S6.E5X.2.1.1.m1.1.1.5.cmml" xref="S6.E5X.2.1.1.m1.1.1.5">𝑐</ci><ci id="S6.E5X.2.1.1.m1.1.1.6.cmml" xref="S6.E5X.2.1.1.m1.1.1.6">𝑖</ci><ci id="S6.E5X.2.1.1.m1.1.1.7.cmml" xref="S6.E5X.2.1.1.m1.1.1.7">𝑠</ci><ci id="S6.E5X.2.1.1.m1.1.1.8.cmml" xref="S6.E5X.2.1.1.m1.1.1.8">𝑖</ci><ci id="S6.E5X.2.1.1.m1.1.1.9.cmml" xref="S6.E5X.2.1.1.m1.1.1.9">𝑂</ci><ci id="S6.E5X.2.1.1.m1.1.1.10.cmml" xref="S6.E5X.2.1.1.m1.1.1.10">𝑛</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E5X.2.1.1.m1.1c">\displaystyle 精度</annotation><annotation encoding="application/x-llamapun" id="S6.E5X.2.1.1.m1.1d">italic_P italic_r italic_e italic_c italic_i italic_s italic_i italic_o italic_n</annotation></semantics></math> | <math alttext="\displaystyle=\frac{\text{正确检测到的 LLM 生成样本}}{\text{所有检测到的 LLM 生成样本}}" class="ltx_Math" display="inline" id="S6.E5X.3.2.2.m1.1"><semantics id="S6.E5X.3.2.2.m1.1a"><mrow id="S6.E5X.3.2.2.m1.1.1" xref="S6.E5X.3.2.2.m1.1.1.cmml"><mo id="S6.E5X.3.2.2.m1.1.1.1" mathsize="90%" xref="S6.E5X.3.2.2.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E5X.3.2.2.m1.1.1.3" xref="S6.E5X.3.2.2.m1.1.1.3.cmml"><mfrac id="S6.E5X.3.2.2.m1.1.1.3a" xref="S6.E5X.3.2.2.m1.1.1.3.cmml"><mtext id="S6.E5X.3.2.2.m1.1.1.3.2" mathsize="90%" xref="S6.E5X.3.2.2.m1. |
| --- | --- | --- |
|  |  | <math alttext="\displaystyle=\frac{TP}{TP+FP}" class="ltx_Math" display="inline" id="S6.E5Xa.2.1.1.m1.1"><semantics id="S6.E5Xa.2.1.1.m1.1a"><mrow id="S6.E5Xa.2.1.1.m1.1.1" xref="S6.E5Xa.2.1.1.m1.1.1.cmml"><mo id="S6.E5Xa.2.1.1.m1.1.1.1" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E5Xa.2.1.1.m1.1.1.3" xref="S6.E5Xa.2.1.1.m1.1.1.3.cmml"><mfrac id="S6.E5Xa.2.1.1.m1.1.1.3a" xref="S6.E5Xa.2.1.1.m1.1.1.3.cmml"><mrow id="S6.E5Xa.2.1.1.m1.1.1.3.2" xref="S6.E5Xa.2.1.1.m1.1.1.3.2.cmml"><mi id="S6.E5Xa.2.1.1.m1.1.1.3.2.2" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.3.2.2.cmml">T</mi><mo id="S6.E5Xa.2.1.1.m1.1.1.3.2.1" xref="S6.E5Xa.2.1.1.m1.1.1.3.2.1.cmml">⁢</mo><mi id="S6.E5Xa.2.1.1.m1.1.1.3.2.3" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.3.2.3.cmml">P</mi></mrow><mrow id="S6.E5Xa.2.1.1.m1.1.1.3.3" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.cmml"><mrow id="S6.E5Xa.2.1.1.m1.1.1.3.3.2" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.2.cmml"><mi id="S6.E5Xa.2.1.1.m1.1.1.3.3.2.2" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.2.2.cmml">T</mi><mo id="S6.E5Xa.2.1.1.m1.1.1.3.3.2.1" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E5Xa.2.1.1.m1.1.1.3.3.2.3" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.2.3.cmml">P</mi></mrow><mo id="S6.E5Xa.2.1.1.m1.1.1.3.3.1" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E5Xa.2.1.1.m1.1.1.3.3.3" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.3.cmml"><mi id="S6.E5Xa.2.1.1.m1.1.1.3.3.3.2" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.3.2.cmml">F</mi><mo id="S6.E5Xa.2.1.1.m1.1.1.3.3.3.1" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.3.1.cmml">⁢</mo><mi id="S6.E5Xa.2.1.1.m1.1.1.3.3.3.3" mathsize="90%" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.3.3.cmml">P</mi></mrow></mrow></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E5Xa.2.1.1.m1.1b"><apply id="S6.E5Xa.2.1.1.m1.1.1.cmml" xref="S6.E5Xa.2.1.1.m1.1.1"><csymbol cd="latexml" id="S6.E5Xa.2.1.1.m1.1.1.2.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.2">absent</csymbol><apply id="S6.E5Xa.2.1.1.m1.1.1.3.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3"><apply id="S6.E5Xa.2.1.1.m1.1.1.3.2.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.2"><ci id="S6.E5Xa.2.1.1.m1.1.1.3.2.2.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.2.2">𝑇</ci><ci id="S6.E5Xa.2.1.1.m1.1.1.3.2.3.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.2.3">𝑃</ci></apply><apply id="S6.E5Xa.2.1.1.m1.1.1.3.3.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.3"><apply id="S6.E5Xa.2.1.1.m1.1.1.3.3.2.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.2"><ci id="S6.E5Xa.2.1.1.m1.1.1.3.3.2.2.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.2.2">𝑇</ci><ci id="S6.E5Xa.2.1.1.m1.1.1.3.3.2.3.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.2.3">𝑃</ci></apply><apply id="S6.E5Xa.2.1.1.m1.1.1.3.3.3.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.3"><ci id="S6.E5Xa.2.1.1.m1.1.1.3.3.3.2.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.3.2">𝐹</ci><ci id="S6.E5Xa.2.1.1.m1.1.1.3.3.3.3.cmml" xref="S6.E5Xa.2.1.1.m1.1.1.3.3.3.3">𝑃</ci></apply></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E5Xa.2.1.1.m1.1c">\displaystyle=\frac{TP}{TP+FP}</annotation><annotation encoding="application/x-llamapun" id="S6.E5Xa.2.1.1.m1.1d |

##### 召回率

召回率表示实际机器生成文本中被准确识别为机器生成的文本的比例。在需要最小化漏报的情况下，这一指标尤为重要，比如在需要捕捉大多数机器生成文本的场景中。AvgRec，即各类别的平均召回率，对于需要跨类别综合评估的多类别任务特别有用。HumanRec 和 LLMRec 分别表示准确分类为人工撰写和机器生成的文本的比例，揭示了模型在这两类文本上的差异性能。召回率、HumanRec、LLMRec 和 AvgRec 可以通过以下公式分别描述：

|  | <math alttext="召回率=\frac{TP}{TP+FN}" class="ltx_Math" display="block" id="S6.E6.m1.1"><semantics id="S6.E6.m1.1a"><mrow id="S6.E6.m1.1.1" xref="S6.E6.m1.1.1.cmml"><mrow id="S6.E6.m1.1.1.2" xref="S6.E6.m1.1.1.2.cmml"><mi id="S6.E6.m1.1.1.2.2" mathsize="90%" xref="S6.E6.m1.1.1.2.2.cmml">R</mi><mo id="S6.E6.m1.1.1.2.1" xref="S6.E6.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.2.3" mathsize="90%" xref="S6.E6.m1.1.1.2.3.cmml">e</mi><mo id="S6.E6.m1.1.1.2.1a" xref="S6.E6.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.2.4" mathsize="90%" xref="S6.E6.m1.1.1.2.4.cmml">c</mi><mo id="S6.E6.m1.1.1.2.1b" xref="S6.E6.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.2.5" mathsize="90%" xref="S6.E6.m1.1.1.2.5.cmml">a</mi><mo id="S6.E6.m1.1.1.2.1c" xref="S6.E6.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.2.6" mathsize="90%" xref="S6.E6.m1.1.1.2.6.cmml">l</mi><mo id="S6.E6.m1.1.1.2.1d" xref="S6.E6.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.2.7" mathsize="90%" xref="S6.E6.m1.1.1.2.7.cmml">l</mi></mrow><mo id="S6.E6.m1.1.1.1" mathsize="90%" xref="S6.E6.m1.1.1.1.cmml">=</mo><mfrac id="S6.E6.m1.1.1.3" xref="S6.E6.m1.1.1.3.cmml"><mrow id="S6.E6.m1.1.1.3.2" xref="S6.E6.m1.1.1.3.2.cmml"><mi id="S6.E6.m1.1.1.3.2.2" mathsize="90%" xref="S6.E6.m1.1.1.3.2.2.cmml">T</mi><mo id="S6.E6.m1.1.1.3.2.1" xref="S6.E6.m1.1.1.3.2.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.3.2.3" mathsize="90%" xref="S6.E6.m1.1.1.3.2.3.cmml">P</mi></mrow><mrow id="S6.E6.m1.1.1.3.3" xref="S6.E6.m1.1.1.3.3.cmml"><mrow id="S6.E6.m1.1.1.3.3.2" xref="S6.E6.m1.1.1.3.3.2.cmml"><mi id="S6.E6.m1.1.1.3.3.2.2" mathsize="90%" xref="S6.E6.m1.1.1.3.3.2.2.cmml">T</mi><mo id="S6.E6.m1.1.1.3.3.2.1" xref="S6.E6.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.3.3.2.3" mathsize="90%" xref="S6.E6.m1.1.1.3.3.2.3.cmml">P</mi></mrow><mo id="S6.E6.m1.1.1.3.3.1" mathsize="90%" xref="S6.E6.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E6.m1.1.1.3.3.3" xref="S6.E6.m1.1.1.3.3.3.cmml"><mi id="S6.E6.m1.1.1.3.3.3.2" mathsize="90%" xref="S6.E6.m1.1.1.3.3.3.2.cmml">F</mi><mo id="S6.E6.m1.1.1.3.3.3.1" xref="S6.E6.m1.1.1.3.3.3.1.cmml">⁢</mo><mi id="S6.E6.m1.1.1.3.3.3.3" mathsize="90%" xref="S6.E6.m1.1.1.3.3.3.3.cmml">N</mi></mrow></mrow></mfrac></mrow><annotation-xml encoding="MathML-Content" id="S6.E6.m1.1b"><apply id="S6.E6.m1.1.1.cmml" xref="S6.E6.m1.1.1"><apply id="S6.E6.m1.1.1.2.cmml" xref="S6.E6.m1.1.1.2"><ci id="S6.E6.m1.1.1.2.2.cmml" xref="S6.E6.m1.1.1.2.2">𝑅</ci><ci id="S6.E6.m1.1.1.2.3.cmml" xref="S6.E6.m1.1.1.2.3">𝑒</ci><ci id="S6.E6.m1.1.1.2.4.cmml" xref="S6.E6.m1.1.1.2.4">𝑐</ci><ci id="S6.E6.m1.1.1.2.5.cmml" xref="S6.E6.m1.1.1.2.5">𝑎</ci><ci id="S6.E6.m1.1.1.2.6.cmml" xref="S6.E6.m1.1.1.2.6">𝑙</ci><ci id="S6.E6.m1.1.1.2.7.cmml" xref="S6.E6.m1.1.1.2.7">𝑙</ci></apply><apply id="S6.E6.m1.1.1.3.cmml" xref="S6.E6.m1.1.1.3"><apply id="S6.E6.m1.1.1.3.2.cmml" xref="S6.E6.m1.1.1.3.2"><ci id="S6.E6.m1.1.1.3.2.2.cmml" xref="S6.E6.m1.1.1.3.2.2">𝑇</ci><ci id="S6.E6.m1.1.1.3.2.3.cmml" xref="S6.E6.m1.1.1.3.2.3">𝑃</ci></apply><apply id="S6.E6.m1.1.1.3.3.cmml" xref="S6.E6.m1.1.1.3.3"><apply id="S6.E6.m1.1.1.3.3.2.cmml" xref="S6.E6.m1.1.1.3.3.2"><ci id="S6.E6.m1.1.1.3.3.2.2.cmml" xref="S6.E6.m1.1.1 |
| --- | --- |
|  | <math alttext="HumanRecall=\frac{\text{正确检测到的人工书写样本}}{\text{所有 % 人工书写样本}}" class="ltx_Math" display="block" id="S6.E7.m1.1"><semantics id="S6.E7.m1.1a"><mrow id="S6.E7.m1.1.1" xref="S6.E7.m1.1.1.cmml"><mrow id="S6.E7.m1.1.1.2" xref="S6.E7.m1.1.1.2.cmml"><mi id="S6.E7.m1.1.1.2.2" mathsize="90%" xref="S6.E7.m1.1.1.2.2.cmml">H</mi><mo id="S6.E7.m1.1.1.2.1" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.3" mathsize="90%" xref="S6.E7.m1.1.1.2.3.cmml">u</mi><mo id="S6.E7.m1.1.1.2.1a" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.4" mathsize="90%" xref="S6.E7.m1.1.1.2.4.cmml">m</mi><mo id="S6.E7.m1.1.1.2.1b" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.5" mathsize="90%" xref="S6.E7.m1.1.1.2.5.cmml">a</mi><mo id="S6.E7.m1.1.1.2.1c" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.6" mathsize="90%" xref="S6.E7.m1.1.1.2.6.cmml">n</mi><mo id="S6.E7.m1.1.1.2.1d" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.7" mathsize="90%" xref="S6.E7.m1.1.1.2.7.cmml">R</mi><mo id="S6.E7.m1.1.1.2.1e" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.8" mathsize="90%" xref="S6.E7.m1.1.1.2.8.cmml">e</mi><mo id="S6.E7.m1.1.1.2.1f" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.9" mathsize="90%" xref="S6.E7.m1.1.1.2.9.cmml">c</mi><mo id="S6.E7.m1.1.1.2.1g" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.10" mathsize="90%" xref="S6.E7.m1.1.1.2.10.cmml">a</mi><mo id="S6.E7.m1.1.1.2.1h" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.11" mathsize="90%" xref="S6.E7.m1.1.1.2.11.cmml">l</mi><mo id="S6.E7.m1.1.1.2.1i" xref="S6.E7.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E7.m1.1.1.2.12" mathsize="90%" xref="S6.E7.m1.1.1.2.12.cmml">l</mi></mrow><mo id="S6.E7.m1.1.1.1" mathsize="90%" xref="S6.E7.m1.1.1.1.cmml">=</mo><mfrac id="S6.E7.m1.1.1.3" xref="S6.E7.m1.1.1.3.cmml"><mtext id="S6.E7.m1.1.1.3.2" mathsize="90%" xref="S6.E7.m1.1.1.3.2a.cmml">正确检测到的人工书写样本</mtext><mtext id="S6.E7.m1.1.1.3.3" mathsize="90%" xref="S6.E7.m1.1.1.3.3a.cmml">所有人工书写样本</mtext></mfrac></mrow><annotation-xml encoding="MathML-Content" id="S6.E7.m1.1b"><apply id="S6.E7.m1.1.1.cmml" xref="S6.E7.m1.1.1"><apply id="S6.E7.m1.1.1.2.cmml" xref="S6.E7.m1.1.1.2"><ci id="S6.E7.m1.1.1.2.2.cmml" xref="S6.E7.m1.1.1.2.2">𝐻</ci><ci id="S6.E7.m1.1.1.2.3.cmml" xref="S6.E7.m1.1.1.2.3">𝑢</ci><ci id="S6.E7.m1.1.1.2.4.cmml" xref="S6.E7.m1.1.1.2.4">𝑚</ci><ci id="S6.E7.m1.1.1.2.5.cmml" xref="S6.E7.m1.1.1.2.5">𝑎</ci><ci id="S6.E7.m1.1.1.2.6.cmml" xref="S6.E7.m1.1.1.2.6">𝑛</ci><ci id="S6.E7.m1.1.1.2.7.cmml" xref="S6.E7.m1.1.1.2.7">𝑅</ci><ci id="S6.E7.m1.1.1.2.8.cmml" xref="S6.E7.m1.1.1.2.8">𝑒</ci><ci id="S6.E7.m1.1.1.2.9.cmml" xref="S6.E7.m1.1.1.2.9">𝑐</ci><ci id="S6.E7.m1.1.1.2.10.cmml" xref="S6.E7.m1.1.1.2.10">𝑎</ci><ci id="S6.E7.m1.1.1.2.11.cmml" xref="S6.E7.m1.1.1.2.11">𝑙</ci><ci id="S6.E7.m1.1.1.2.12.cmml" xref="S6.E7.m1.1.1.2.12">𝑙</ci></apply><apply id="S6.E7.m1.1.1.3.cmml" xref="S6.E7.m1.1.1.3"><ci id="S6.E7.m1.1.1.3.2a.cmml" xref="S6.E7.m1.1.1.3.2"><mtext id="S6.E7.m1.1.1.3.2.cmml" mathsize="90%" xref="S6.E7.m1.1.1.3.2">正确检测到的人工书写样本</mtext></ci><ci id="S6.E7.m1.1.1.3.3a.cmml" xref="S6.E7.m1.1.1.3.3"><mtext id="S6.E7.m |
|  | <math alttext="LLMRecall=\frac{\text{正确检测到的 LLM 生成样本}}{\text{所有 LLM 生成样本}}" class="ltx_Math" display="block" id="S6.E8.m1.1"><semantics id="S6.E8.m1.1a"><mrow id="S6.E8.m1.1.1" xref="S6.E8.m1.1.1.cmml"><mrow id="S6.E8.m1.1.1.2" xref="S6.E8.m1.1.1.2.cmml"><mi id="S6.E8.m1.1.1.2.2" mathsize="90%" xref="S6.E8.m1.1.1.2.2.cmml">𝐿</mi><mo id="S6.E8.m1.1.1.2.1" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.3" mathsize="90%" xref="S6.E8.m1.1.1.2.3.cmml">𝐿</mi><mo id="S6.E8.m1.1.1.2.1a" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.4" mathsize="90%" xref="S6.E8.m1.1.1.2.4.cmml">𝑀</mi><mo id="S6.E8.m1.1.1.2.1b" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.5" mathsize="90%" xref="S6.E8.m1.1.1.2.5.cmml">𝑅</mi><mo id="S6.E8.m1.1.1.2.1c" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.6" mathsize="90%" xref="S6.E8.m1.1.1.2.6.cmml">𝑒</mi><mo id="S6.E8.m1.1.1.2.1d" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.7" mathsize="90%" xref="S6.E8.m1.1.1.2.7.cmml">𝑐</mi><mo id="S6.E8.m1.1.1.2.1e" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.8" mathsize="90%" xref="S6.E8.m1.1.1.2.8.cmml">𝑎</mi><mo id="S6.E8.m1.1.1.2.1f" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.9" mathsize="90%" xref="S6.E8.m1.1.1.2.9.cmml">𝑙</mi><mo id="S6.E8.m1.1.1.2.1g" xref="S6.E8.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E8.m1.1.1.2.10" mathsize="90%" xref="S6.E8.m1.1.1.2.10.cmml">𝑙</mi></mrow><mo id="S6.E8.m1.1.1.1" mathsize="90%" xref="S6.E8.m1.1.1.1.cmml">=</mo><mfrac id="S6.E8.m1.1.1.3" xref="S6.E8.m1.1.1.3.cmml"><mtext id="S6.E8.m1.1.1.3.2" mathsize="90%" xref="S6.E8.m1.1.1.3.2a.cmml">正确检测到的 LLM 生成样本</mtext><mtext id="S6.E8.m1.1.1.3.3" mathsize="90%" xref="S6.E8.m1.1.1.3.3a.cmml">所有 LLM 生成样本</mtext></mfrac></mrow><annotation-xml encoding="MathML-Content" id="S6.E8.m1.1b"><apply id="S6.E8.m1.1.1.cmml" xref="S6.E8.m1.1.1"><apply id="S6.E8.m1.1.1.2.cmml" xref="S6.E8.m1.1.1.2"><ci id="S6.E8.m1.1.1.2.2.cmml" xref="S6.E8.m1.1.1.2.2">𝐿</ci><ci id="S6.E8.m1.1.1.2.3.cmml" xref="S6.E8.m1.1.1.2.3">𝐿</ci><ci id="S6.E8.m1.1.1.2.4.cmml" xref="S6.E8.m1.1.1.2.4">𝑀</ci><ci id="S6.E8.m1.1.1.2.5.cmml" xref="S6.E8.m1.1.1.2.5">𝑅</ci><ci id="S6.E8.m1.1.1.2.6.cmml" xref="S6.E8.m1.1.1.2.6">𝑒</ci><ci id="S6.E8.m1.1.1.2.7.cmml" xref="S6.E8.m1.1.1.2.7">𝑐</ci><ci id="S6.E8.m1.1.1.2.8.cmml" xref="S6.E8.m1.1.1.2.8">𝑎</ci><ci id="S6.E8.m1.1.1.2.9.cmml" xref="S6.E8.m1.1.1.2.9">𝑙</ci><ci id="S6.E8.m1.1.1.2.10.cmml" xref="S6.E8.m1.1.1.2.10">𝑙</ci></apply><apply id="S6.E8.m1.1.1.3.cmml" xref="S6.E8.m1.1.1.3"><ci id="S6.E8.m1.1.1.3.2a.cmml" xref="S6.E8.m1.1.1.3.2"><mtext id="S6.E8.m1.1.1.3.2.cmml" mathsize="90%" xref="S6.E8.m1.1.1.3.2">正确检测到的 LLM 生成样本</mtext></ci><ci id="S6.E8.m1.1.1.3.3a.cmml" xref="S6.E8.m1.1.1.3.3"><mtext id="S6.E8.m1.1.1.3.3.cmml" mathsize="90%" xref="S6.E8.m1.1.1.3.3">所有 LLM 生成样本</mtext></ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E8.m1.1c">LLMRecall=\frac{\text{正确检测到的 LLM 生成样本}}{\text{所有 LLM 生成样本}}</annotation><annotation encoding="application/x-llamapun" id="S6.E8.m1.1d">italic_L italic_L italic_M italic_R italic_e italic_c italic_a italic_l italic_l = divide start_ARG 正确检测到的 LLM 生成样本 end_ARG start_ARG 所有 LLM 生成样本 end_ARG</annotation></semantics></math> |  | (8) |
|  | <math alttext="AvgRecall=\frac{HumanRecall+LLMRecall}{2}" class="ltx_Math" display="block" id="S6.E9.m1.1"><semantics id="S6.E9.m1.1a"><mrow id="S6.E9.m1.1.1" xref="S6.E9.m1.1.1.cmml"><mrow id="S6.E9.m1.1.1.2" xref="S6.E9.m1.1.1.2.cmml"><mi id="S6.E9.m1.1.1.2.2" mathsize="90%" xref="S6.E9.m1.1.1.2.2.cmml">𝐴</mi><mo id="S6.E9.m1.1.1.2.1" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.3" mathsize="90%" xref="S6.E9.m1.1.1.2.3.cmml">𝑣</mi><mo id="S6.E9.m1.1.1.2.1a" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.4" mathsize="90%" xref="S6.E9.m1.1.1.2.4.cmml">𝑔</mi><mo id="S6.E9.m1.1.1.2.1b" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.5" mathsize="90%" xref="S6.E9.m1.1.1.2.5.cmml">𝑅</mi><mo id="S6.E9.m1.1.1.2.1c" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.6" mathsize="90%" xref="S6.E9.m1.1.1.2.6.cmml">𝑒</mi><mo id="S6.E9.m1.1.1.2.1d" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.7" mathsize="90%" xref="S6.E9.m1.1.1.2.7.cmml">𝑐</mi><mo id="S6.E9.m1.1.1.2.1e" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.8" mathsize="90%" xref="S6.E9.m1.1.1.2.8.cmml">𝑎</mi><mo id="S6.E9.m1.1.1.2.1f" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.9" mathsize="90%" xref="S6.E9.m1.1.1.2.9.cmml">𝑙</mi><mo id="S6.E9.m1.1.1.2.1g" xref="S6.E9.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.2.10" mathsize="90%" xref="S6.E9.m1.1.1.2.10.cmml">𝑙</mi></mrow><mo id="S6.E9.m1.1.1.1" mathsize="90%" xref="S6.E9.m1.1.1.1.cmml">=</mo><mfrac id="S6.E9.m1.1.1.3" xref="S6.E9.m1.1.1.3.cmml"><mrow id="S6.E9.m1.1.1.3.2" xref="S6.E9.m1.1.1.3.2.cmml"><mrow id="S6.E9.m1.1.1.3.2.2" xref="S6.E9.m1.1.1.3.2.2.cmml"><mi id="S6.E9.m1.1.1.3.2.2.2" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.2.cmml">𝐻</mi><mo id="S6.E9.m1.1.1.3.2.2.1" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.3" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.3.cmml">𝑢</mi><mo id="S6.E9.m1.1.1.3.2.2.1a" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.4" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.4.cmml">𝑚</mi><mo id="S6.E9.m1.1.1.3.2.2.1b" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.5" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.5.cmml">𝑎</mi><mo id="S6.E9.m1.1.1.3.2.2.1c" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.6" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.6.cmml">𝑛</mi><mo id="S6.E9.m1.1.1.3.2.2.1d" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.7" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.7.cmml">𝑅</mi><mo id="S6.E9.m1.1.1.3.2.2.1e" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.8" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.8.cmml">𝑒</mi><mo id="S6.E9.m1.1.1.3.2.2.1f" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.9" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.9.cmml">𝑐</mi><mo id="S6.E9.m1.1.1.3.2.2.1g" xref="S6.E9.m1.1.1.3.2.2.1.cmml">⁢</mo><mi id="S6.E9.m1.1.1.3.2.2.10" mathsize="90%" xref="S6.E9.m1.1.1.3.2.2.10.cmml">𝑎</mi><mo id="S6.E9.m1.1.1.3.2.2.1h" xref="S6.E9.m1.1.1.3.2.2 |

##### 假阳性率 (FPR)

FPR 指的是所有实际由人类编写的样本中被错误检测为 LLM 生成样本的比例。这个指标可以衡量模型在实际由人类编写的样本中所做的错误预测的比例。它有助于了解模型的假阳性率，从而对 LLM 生成样本的检测具有更高的敏感性。这个指标可以通过以下公式来描述：

|  | <math alttext="\displaystyle FPR" class="ltx_Math" display="inline" id="S6.E10X.2.1.1.m1.1"><semantics id="S6.E10X.2.1.1.m1.1a"><mrow id="S6.E10X.2.1.1.m1.1.1" xref="S6.E10X.2.1.1.m1.1.1.cmml"><mi id="S6.E10X.2.1.1.m1.1.1.2" mathsize="90%" xref="S6.E10X.2.1.1.m1.1.1.2.cmml">F</mi><mo id="S6.E10X.2.1.1.m1.1.1.1" xref="S6.E10X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E10X.2.1.1.m1.1.1.3" mathsize="90%" xref="S6.E10X.2.1.1.m1.1.1.3.cmml">P</mi><mo id="S6.E10X.2.1.1.m1.1.1.1a" xref="S6.E10X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E10X.2.1.1.m1.1.1.4" mathsize="90%" xref="S6.E10X.2.1.1.m1.1.1.4.cmml">R</mi></mrow><annotation-xml encoding="MathML-Content" id="S6.E10X.2.1.1.m1.1b"><apply id="S6.E10X.2.1.1.m1.1.1.cmml" xref="S6.E10X.2.1.1.m1.1.1"><ci id="S6.E10X.2.1.1.m1.1.1.2.cmml" xref="S6.E10X.2.1.1.m1.1.1.2">𝐹</ci><ci id="S6.E10X.2.1.1.m1.1.1.3.cmml" xref="S6.E10X.2.1.1.m1.1.1.3">𝑃</ci><ci id="S6.E10X.2.1.1.m1.1.1.4.cmml" xref="S6.E10X.2.1.1.m1.1.1.4">𝑅</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E10X.2.1.1.m1.1c">\displaystyle FPR</annotation><annotation encoding="application/x-llamapun" id="S6.E10X.2.1.1.m1.1d">italic_F italic_P italic_R</annotation></semantics></math> | <math alttext="\displaystyle=\frac{\text{incorrectly detected LLM-generated samples}}{\text{% all human-written samples}}" class="ltx_Math" display="inline" id="S6.E10X.3.2.2.m1.1"><semantics id="S6.E10X.3.2.2.m1.1a"><mrow id="S6.E10X.3.2.2.m1.1.1" xref="S6.E10X.3.2.2.m1.1.1.cmml"><mo id="S6.E10X.3.2.2.m1.1.1.1" mathsize="90%" xref="S6.E10X.3.2.2.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E10X.3.2.2.m1.1.1.3" xref="S6.E10X.3.2.2.m1.1.1.3.cmml"><mfrac id="S6.E10X.3.2.2.m1.1.1.3a" xref="S6.E10X.3.2.2.m1.1.1.3.cmml"><mtext id="S6.E10X.3.2.2.m1.1.1.3.2" mathsize="90%" xref="S6.E10X.3.2.2.m1.1.1.3.2a.cmml">incorrectly detected LLM-generated samples</mtext><mtext id="S6.E10X.3.2.2.m1.1.1.3.3" mathsize="90%" xref="S6.E10X.3.2.2.m1.1.1.3.3a.cmml">all human-written samples</mtext></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E10X.3.2.2.m1.1b"><apply id="S6.E10X.3.2.2.m1.1.1.cmml" xref="S6.E10X.3.2.2.m1.1.1"><csymbol cd="latexml" id="S6.E10X.3.2.2.m1.1.1.2.cmml" xref="S6.E10X.3.2.2.m1.1.1.2">absent</csymbol><apply id="S6.E10X.3.2.2.m1.1.1.3.cmml" xref="S6.E10X.3.2.2.m1.1.1.3"><ci id="S6.E10X.3.2.2.m1.1.1.3.2a.cmml" xref="S6.E10X.3.2.2.m1.1.1.3.2"><mtext id="S6.E10X.3.2.2.m1.1.1.3.2.cmml" mathsize="90%" xref="S6.E10X.3.2.2.m1.1.1.3.2">incorrectly detected LLM-generated samples</mtext></ci><ci id="S6.E10X.3.2.2.m1.1.1.3.3a.cmml" xref="S6.E10X.3.2.2.m1.1.1.3.3"><mtext id="S6.E10X.3.2.2.m1.1.1.3.3.cmml" mathsize="90%" xref="S6.E10X.3.2.2.m1.1.1.3.3">all human-written samples</mtext></ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E10X.3.2.2.m1.1c">\displaystyle=\frac{\text{incorrectly detected LLM-generated samples}}{\text{% all human-written samples}}</annotation><annotation encoding="application/x-llamapun" id="S6.E10X.3.2.2.m1.1d">= divide start_ARG incorrectly detected LLM-generated samples end_ARG start_ARG all human-written samples end_ARG</annotation></semantics></math> |  | (10) |
| --- | --- | --- | --- | --- |
|  |  | <math alttext="\displaystyle=\frac{FP}{FP+TP}" class="ltx_Math" display="inline" id="S6.E10Xa.2.1.1.m1.1"><semantics id="S6.E10Xa.2.1.1.m1.1a"><mrow id="S6.E10Xa.2.1.1.m1.1.1" xref="S6.E10Xa.2.1.1.m1.1.1.cmml"><mo id="S6.E10Xa.2.1.1.m1.1.1.1" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E10Xa.2.1.1.m1.1.1.3" xref="S6.E10Xa.2.1.1.m1.1.1.3.cmml"><mfrac id="S6.E10Xa.2.1.1.m1.1.1.3a" xref="S6.E10Xa.2.1.1.m1.1.1.3.cmml"><mrow id="S6.E10Xa.2.1.1.m1.1.1.3.2" xref="S6.E10Xa.2.1.1.m1.1.1.3.2.cmml"><mi id="S6.E10Xa.2.1.1.m1.1.1.3.2.2" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.3.2.2.cmml">F</mi><mo id="S6.E10Xa.2.1.1.m1.1.1.3.2.1" xref="S6.E10Xa.2.1.1.m1.1.1.3.2.1.cmml">⁢</mo><mi id="S6.E10Xa.2.1.1.m1.1.1.3.2.3" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.3.2.3.cmml">P</mi></mrow><mrow id="S6.E10Xa.2.1.1.m1.1.1.3.3" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.cmml"><mrow id="S6.E10Xa.2.1.1.m1.1.1.3.3.2" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.2.cmml"><mi id="S6.E10Xa.2.1.1.m1.1.1.3.3.2.2" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.2.2.cmml">F</mi><mo id="S6.E10Xa.2.1.1.m1.1.1.3.3.2.1" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E10Xa.2.1.1.m1.1.1.3.3.2.3" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.2.3.cmml">P</mi></mrow><mo id="S6.E10Xa.2.1.1.m1.1.1.3.3.1" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E10Xa.2.1.1.m1.1.1.3.3.3" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.3.cmml"><mi id="S6.E10Xa.2.1.1.m1.1.1.3.3.3.2" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.3.2.cmml">T</mi><mo id="S6.E10Xa.2.1.1.m1.1.1.3.3.3.1" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.3.1.cmml">⁢</mo><mi id="S6.E10Xa.2.1.1.m1.1.1.3.3.3.3" mathsize="90%" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.3.3.cmml">P</mi></mrow></mrow></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E10Xa.2.1.1.m1.1b"><apply id="S6.E10Xa.2.1.1.m1.1.1.cmml" xref="S6.E10Xa.2.1.1.m1.1.1"><csymbol cd="latexml" id="S6.E10Xa.2.1.1.m1.1.1.2.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.2">absent</csymbol><apply id="S6.E10Xa.2.1.1.m1.1.1.3.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3"><apply id="S6.E10Xa.2.1.1.m1.1.1.3.2.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.2"><ci id="S6.E10Xa.2.1.1.m1.1.1.3.2.2.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.2.2">𝐹</ci><ci id="S6.E10Xa.2.1.1.m1.1.1.3.2.3.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.2.3">𝑃</ci></apply><apply id="S6.E10Xa.2.1.1.m1.1.1.3.3.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.3"><apply id="S6.E10Xa.2.1.1.m1.1.1.3.3.2.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.2"><ci id="S6.E10Xa.2.1.1.m1.1.1.3.3.2.2.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.2.2">𝐹</ci><ci id="S6.E10Xa.2.1.1.m1.1.1.3.3.2.3.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.2.3">𝑃</ci></apply><apply id="S6.E10Xa.2.1.1.m1.1.1.3.3.3.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.3"><ci id="S6.E10Xa.2.1.1.m1.1.1.3.3.3.2.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.3.2">𝑇</ci><ci id="S6.E10Xa.2.1.1.m1.1.1.3.3.3.3.cmml" xref="S6.E10Xa.2.1.1.m1.1.1.3.3.3.3">𝑃</ci></apply></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E10Xa.2.1.1.m1.1c">\displaystyle=\frac{FP}{FP+TP}</annotation><annotation encoding="application/x-llamapun" id="S6.E10Xa.2.1.1.m1.1d"> |

##### 真阴性率（TNR）

TNR（真阴性率）指的是在所有实际人类编写的样本中，被正确检测为人类编写的样本的比例。这个指标衡量了模型预测人类编写样本的准确性，但不考虑 FPR（假阳性率），即实际人类编写的文本被错误地检测为 LLM 生成的文本。这个指标可以通过以下公式描述：

|  | <math alttext="\displaystyle TNR" class="ltx_Math" display="inline" id="S6.E11X.2.1.1.m1.1"><semantics id="S6.E11X.2.1.1.m1.1a"><mrow id="S6.E11X.2.1.1.m1.1.1" xref="S6.E11X.2.1.1.m1.1.1.cmml"><mi id="S6.E11X.2.1.1.m1.1.1.2" mathsize="90%" xref="S6.E11X.2.1.1.m1.1.1.2.cmml">T</mi><mo id="S6.E11X.2.1.1.m1.1.1.1" xref="S6.E11X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E11X.2.1.1.m1.1.1.3" mathsize="90%" xref="S6.E11X.2.1.1.m1.1.1.3.cmml">N</mi><mo id="S6.E11X.2.1.1.m1.1.1.1a" xref="S6.E11X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E11X.2.1.1.m1.1.1.4" mathsize="90%" xref="S6.E11X.2.1.1.m1.1.1.4.cmml">R</mi></mrow><annotation-xml encoding="MathML-Content" id="S6.E11X.2.1.1.m1.1b"><apply id="S6.E11X.2.1.1.m1.1.1.cmml" xref="S6.E11X.2.1.1.m1.1.1"><ci id="S6.E11X.2.1.1.m1.1.1.2.cmml" xref="S6.E11X.2.1.1.m1.1.1.2">𝑇</ci><ci id="S6.E11X.2.1.1.m1.1.1.3.cmml" xref="S6.E11X.2.1.1.m1.1.1.3">𝑁</ci><ci id="S6.E11X.2.1.1.m1.1.1.4.cmml" xref="S6.E11X.2.1.1.m1.1.1.4">𝑅</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E11X.2.1.1.m1.1c">\displaystyle TNR</annotation><annotation encoding="application/x-llamapun" id="S6.E11X.2.1.1.m1.1d">italic_T italic_N italic_R</annotation></semantics></math> | <math alttext="\displaystyle=\frac{\text{correctly detected human-written samples}}{\text{all%  human-written samples}}" class="ltx_Math" display="inline" id="S6.E11X.3.2.2.m1.1"><semantics id="S6.E11X.3.2.2.m1.1a"><mrow id="S6.E11X.3.2.2.m1.1.1" xref="S6.E11X.3.2.2.m1.1.1.cmml"><mo id="S6.E11X.3.2.2.m1.1.1.1" mathsize="90%" xref="S6.E11X.3.2.2.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E11X.3.2.2.m1.1.1.3" xref="S6.E11X.3.2.2.m1.1.1.3.cmml"><mfrac id="S6.E11X.3.2.2.m1.1.1.3a" xref="S6.E11X.3.2.2.m1.1.1.3.cmml"><mtext id="S6.E11X.3.2.2.m1.1.1.3.2" mathsize="90%" xref="S6.E11X.3.2.2.m1.1.1.3.2a.cmml">correctly detected human-written samples</mtext><mtext id="S6.E11X.3.2.2.m1.1.1.3.3" mathsize="90%" xref="S6.E11X.3.2.2.m1.1.1.3.3a.cmml">all human-written samples</mtext></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E11X.3.2.2.m1.1b"><apply id="S6.E11X.3.2.2.m1.1.1.cmml" xref="S6.E11X.3.2.2.m1.1.1"><csymbol cd="latexml" id="S6.E11X.3.2.2.m1.1.1.2.cmml" xref="S6.E11X.3.2.2.m1.1.1.2">absent</csymbol><apply id="S6.E11X.3.2.2.m1.1.1.3.cmml" xref="S6.E11X.3.2.2.m1.1.1.3"><ci id="S6.E11X.3.2.2.m1.1.1.3.2a.cmml" xref="S6.E11X.3.2.2.m1.1.1.3.2"><mtext id="S6.E11X.3.2.2.m1.1.1.3.2.cmml" mathsize="90%" xref="S6.E11X.3.2.2.m1.1.1.3.2">correctly detected human-written samples</mtext></ci><ci id="S6.E11X.3.2.2.m1.1.1.3.3a.cmml" xref="S6.E11X.3.2.2.m1.1.1.3.3"><mtext id="S6.E11X.3.2.2.m1.1.1.3.3.cmml" mathsize="90%" xref="S6.E11X.3.2.2.m1.1.1.3.3">all human-written samples</mtext></ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E11X.3.2.2.m1.1c">\displaystyle=\frac{\text{correctly detected human-written samples}}{\text{all% human-written samples}}</annotation><annotation encoding="application/x-llamapun" id="S6.E11X.3.2.2.m1.1d">= divide start_ARG correctly detected human-written samples end_ARG start_ARG all human-written samples end_ARG</annotation></semantics></math> |  | (11) |
| --- | --- | --- | --- | --- |
|  |  | <math alttext="\displaystyle=\frac{TN}{TN+FP}" class="ltx_Math" display="inline" id="S6.E11Xa.2.1.1.m1.1"><semantics id="S6.E11Xa.2.1.1.m1.1a"><mrow id="S6.E11Xa.2.1.1.m1.1.1" xref="S6.E11Xa.2.1.1.m1.1.1.cmml"><mo id="S6.E11Xa.2.1.1.m1.1.1.1" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E11Xa.2.1.1.m1.1.1.3" xref="S6.E11Xa.2.1.1.m1.1.1.3.cmml"><mfrac id="S6.E11Xa.2.1.1.m1.1.1.3a" xref="S6.E11Xa.2.1.1.m1.1.1.3.cmml"><mrow id="S6.E11Xa.2.1.1.m1.1.1.3.2" xref="S6.E11Xa.2.1.1.m1.1.1.3.2.cmml"><mi id="S6.E11Xa.2.1.1.m1.1.1.3.2.2" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.3.2.2.cmml">T</mi><mo id="S6.E11Xa.2.1.1.m1.1.1.3.2.1" xref="S6.E11Xa.2.1.1.m1.1.1.3.2.1.cmml">⁢</mo><mi id="S6.E11Xa.2.1.1.m1.1.1.3.2.3" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.3.2.3.cmml">N</mi></mrow><mrow id="S6.E11Xa.2.1.1.m1.1.1.3.3" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.cmml"><mrow id="S6.E11Xa.2.1.1.m1.1.1.3.3.2" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.2.cmml"><mi id="S6.E11Xa.2.1.1.m1.1.1.3.3.2.2" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.2.2.cmml">T</mi><mo id="S6.E11Xa.2.1.1.m1.1.1.3.3.2.1" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E11Xa.2.1.1.m1.1.1.3.3.2.3" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.2.3.cmml">N</mi></mrow><mo id="S6.E11Xa.2.1.1.m1.1.1.3.3.1" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E11Xa.2.1.1.m1.1.1.3.3.3" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.3.cmml"><mi id="S6.E11Xa.2.1.1.m1.1.1.3.3.3.2" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.3.2.cmml">F</mi><mo id="S6.E11Xa.2.1.1.m1.1.1.3.3.3.1" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.3.1.cmml">⁢</mo><mi id="S6.E11Xa.2.1.1.m1.1.1.3.3.3.3" mathsize="90%" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.3.3.cmml">P</mi></mrow></mrow></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E11Xa.2.1.1.m1.1b"><apply id="S6.E11Xa.2.1.1.m1.1.1.cmml" xref="S6.E11Xa.2.1.1.m1.1.1"><csymbol cd="latexml" id="S6.E11Xa.2.1.1.m1.1.1.2.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.2">absent</csymbol><apply id="S6.E11Xa.2.1.1.m1.1.1.3.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3"><apply id="S6.E11Xa.2.1.1.m1.1.1.3.2.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.2"><ci id="S6.E11Xa.2.1.1.m1.1.1.3.2.2.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.2.2">𝑇</ci><ci id="S6.E11Xa.2.1.1.m1.1.1.3.2.3.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.2.3">𝑁</ci></apply><apply id="S6.E11Xa.2.1.1.m1.1.1.3.3.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.3"><apply id="S6.E11Xa.2.1.1.m1.1.1.3.3.2.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.2"><ci id="S6.E11Xa.2.1.1.m1.1.1.3.3.2.2.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.2.2">𝑇</ci><ci id="S6.E11Xa.2.1.1.m1.1.1.3.3.2.3.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.2.3">𝑁</ci></apply><apply id="S6.E11Xa.2.1.1.m1.1.1.3.3.3.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.3"><ci id="S6.E11Xa.2.1.1.m1.1.1.3.3.3.2.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.3.2">𝐹</ci><ci id="S6.E11Xa.2.1.1.m1.1.1.3.3.3.3.cmml" xref="S6.E11Xa.2.1.1.m1.1.1.3.3.3.3">𝑃</ci></apply></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E11Xa.2.1.1.m1.1c">\displaystyle=\frac{TN}{TN+FP}</annotation><annotation encoding="application/x-llamapun" id="S6.E11Xa.2.1.1.m1.1d |

##### 假阴性率（FNR）

FNR 指的是所有实际由 LLM 生成的样本中被错误识别为人类写作的比例。这个指标有助于了解模型对于 LLM 生成文本的误解程度。这个指标可以通过以下公式描述：

|  | <math alttext="\displaystyle FNR" class="ltx_Math" display="inline" id="S6.E12X.2.1.1.m1.1"><semantics id="S6.E12X.2.1.1.m1.1a"><mrow id="S6.E12X.2.1.1.m1.1.1" xref="S6.E12X.2.1.1.m1.1.1.cmml"><mi id="S6.E12X.2.1.1.m1.1.1.2" mathsize="90%" xref="S6.E12X.2.1.1.m1.1.1.2.cmml">F</mi><mo id="S6.E12X.2.1.1.m1.1.1.1" xref="S6.E12X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E12X.2.1.1.m1.1.1.3" mathsize="90%" xref="S6.E12X.2.1.1.m1.1.1.3.cmml">N</mi><mo id="S6.E12X.2.1.1.m1.1.1.1a" xref="S6.E12X.2.1.1.m1.1.1.1.cmml">⁢</mo><mi id="S6.E12X.2.1.1.m1.1.1.4" mathsize="90%" xref="S6.E12X.2.1.1.m1.1.1.4.cmml">R</mi></mrow><annotation-xml encoding="MathML-Content" id="S6.E12X.2.1.1.m1.1b"><apply id="S6.E12X.2.1.1.m1.1.1.cmml" xref="S6.E12X.2.1.1.m1.1.1"><ci id="S6.E12X.2.1.1.m1.1.1.2.cmml" xref="S6.E12X.2.1.1.m1.1.1.2">𝐹</ci><ci id="S6.E12X.2.1.1.m1.1.1.3.cmml" xref="S6.E12X.2.1.1.m1.1.1.3">𝑁</ci><ci id="S6.E12X.2.1.1.m1.1.1.4.cmml" xref="S6.E12X.2.1.1.m1.1.1.4">𝑅</ci></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E12X.2.1.1.m1.1c">\displaystyle FNR</annotation><annotation encoding="application/x-llamapun" id="S6.E12X.2.1.1.m1.1d">italic_F italic_N italic_R</annotation></semantics></math> | <math alttext="\displaystyle=\frac{\text{incorrectly detected human-written samples}}{\text{% all LLM-generated samples}}" class="ltx_Math" display="inline" id="S6.E12X.3.2.2.m1.1"><semantics id="S6.E12X.3.2.2.m1.1a"><mrow id="S6.E12X.3.2.2.m1.1.1" xref="S6.E12X.3.2.2.m1.1.1.cmml"><mo id="S6.E12X.3.2.2.m1.1.1.1" mathsize="90%" xref="S6.E12X.3.2.2.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E12X.3.2.2.m1.1.1.3" xref="S6.E12X.3.2.2.m1.1.1.3.cmml"><mfrac id="S6.E12X.3.2.2.m1.1.1.3a" xref="S6.E12X.3.2.2.m1.1.1.3.cmml"><mtext id="S6.E12X.3.2.2.m1.1.1.3.2" mathsize="90%" xref="S6.E12X.3.2.2.m1.1.1.3.2a.cmml">incorrectly detected human-written samples</mtext><mtext id="S6.E12X.3.2.2.m1.1.1.3.3" mathsize="90%" xref="S6.E12X.3.2.2.m1.1.1.3.3a.cmml">all LLM-generated samples</mtext></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E12X.3.2.2.m1.1b"><apply id="S6.E12X.3.2.2.m1.1.1.cmml" xref="S6.E12X.3.2.2.m1.1.1"><csymbol cd="latexml" id="S6.E12X.3.2.2.m1.1.1.2.cmml" xref="S6.E12X.3.2.2.m1.1.1.2">absent</csymbol><apply id="S6.E12X.3.2.2.m1.1.1.3.cmml" xref="S6.E12X.3.2.2.m1.1.1.3"><ci id="S6.E12X.3.2.2.m1.1.1.3.2a.cmml" xref="S6.E12X.3.2.2.m1.1.1.3.2"><mtext id="S6.E12X.3.2.2.m1.1.1.3.2.cmml" mathsize="90%" xref="S6.E12X.3.2.2.m1.1.1.3.2">incorrectly detected human-written samples</mtext></ci><ci id="S6.E12X.3.2.2.m1.1.1.3.3a.cmml" xref="S6.E12X.3.2.2.m1.1.1.3.3"><mtext id="S6.E12X.3.2.2.m1.1.1.3.3.cmml" mathsize="90%" xref="S6.E12X.3.2.2.m1.1.1.3.3">all LLM-generated samples</mtext></ci></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E12X.3.2.2.m1.1c">\displaystyle=\frac{\text{incorrectly detected human-written samples}}{\text{% all LLM-generated samples}}</annotation><annotation encoding="application/x-llamapun" id="S6.E12X.3.2.2.m1.1d">= divide start_ARG incorrectly detected human-written samples end_ARG start_ARG all LLM-generated samples end_ARG</annotation></semantics></math> |  | (12) |
| --- | --- | --- | --- | --- |
|  |  | <math alttext="\displaystyle=\frac{FN}{FN+TP}" class="ltx_Math" display="inline" id="S6.E12Xa.2.1.1.m1.1"><semantics id="S6.E12Xa.2.1.1.m1.1"><mrow id="S6.E12Xa.2.1.1.m1.1.1" xref="S6.E12Xa.2.1.1.m1.1.1.cmml"><mo id="S6.E12Xa.2.1.1.m1.1.1.1" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E12Xa.2.1.1.m1.1.1.3" xref="S6.E12Xa.2.1.1.m1.1.1.3.cmml"><mfrac id="S6.E12Xa.2.1.1.m1.1.1.3a" xref="S6.E12Xa.2.1.1.m1.1.1.3.cmml"><mrow id="S6.E12Xa.2.1.1.m1.1.1.3.2" xref="S6.E12Xa.2.1.1.m1.1.1.3.2.cmml"><mi id="S6.E12Xa.2.1.1.m1.1.1.3.2.2" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.3.2.2.cmml">F</mi><mo id="S6.E12Xa.2.1.1.m1.1.1.3.2.1" xref="S6.E12Xa.2.1.1.m1.1.1.3.2.1.cmml">⁢</mo><mi id="S6.E12Xa.2.1.1.m1.1.1.3.2.3" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.3.2.3.cmml">N</mi></mrow><mrow id="S6.E12Xa.2.1.1.m1.1.1.3.3" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.cmml"><mrow id="S6.E12Xa.2.1.1.m1.1.1.3.3.2" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.2.cmml"><mi id="S6.E12Xa.2.1.1.m1.1.1.3.3.2.2" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.2.2.cmml">F</mi><mo id="S6.E12Xa.2.1.1.m1.1.1.3.3.2.1" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E12Xa.2.1.1.m1.1.1.3.3.2.3" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.2.3.cmml">N</mi></mrow><mo id="S6.E12Xa.2.1.1.m1.1.1.3.3.1" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E12Xa.2.1.1.m1.1.1.3.3.3" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.3.cmml"><mi id="S6.E12Xa.2.1.1.m1.1.1.3.3.3.2" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.3.2.cmml">T</mi><mo id="S6.E12Xa.2.1.1.m1.1.1.3.3.3.1" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.3.1.cmml">⁢</mo><mi id="S6.E12Xa.2.1.1.m1.1.1.3.3.3.3" mathsize="90%" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.3.3.cmml">P</mi></mrow></mrow></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E12Xa.2.1.1.m1.1b"><apply id="S6.E12Xa.2.1.1.m1.1.1.cmml" xref="S6.E12Xa.2.1.1.m1.1.1"><csymbol cd="latexml" id="S6.E12Xa.2.1.1.m1.1.1.2.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.2">absent</csymbol><apply id="S6.E12Xa.2.1.1.m1.1.1.3.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3"><apply id="S6.E12Xa.2.1.1.m1.1.1.3.2.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.2"><ci id="S6.E12Xa.2.1.1.m1.1.1.3.2.2.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.2.2">𝐹</ci><ci id="S6.E12Xa.2.1.1.m1.1.1.3.2.3.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.2.3">𝑁</ci></apply><apply id="S6.E12Xa.2.1.1.m1.1.1.3.3.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.3"><apply id="S6.E12Xa.2.1.1.m1.1.1.3.3.2.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.2"><ci id="S6.E12Xa.2.1.1.m1.1.1.3.3.2.2.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.2.2">𝐹</ci><ci id="S6.E12Xa.2.1.1.m1.1.1.3.3.2.3.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.2.3">𝑁</ci></apply><apply id="S6.E12Xa.2.1.1.m1.1.1.3.3.3.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.3"><ci id="S6.E12Xa.2.1.1.m1.1.1.3.3.3.2.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.3.2">𝑇</ci><ci id="S6.E12Xa.2.1.1.m1.1.1.3.3.3.3.cmml" xref="S6.E12Xa.2.1.1.m1.1.1.3.3.3.3">𝑃</ci></apply></apply></apply></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.E12Xa.2.1.1.m1.1c">\displaystyle=\frac{FN}{FN+TP}</annotation><annotation encoding="application/x-llamapun" id="S6.E12Xa.2.1.1.m1.1d">= |

##### <math alttext="F_{1}" class="ltx_Math" display="inline" id="S6.SS0.SSS0.Px7.1.m1.1"><semantics id="S6.SS0.SSS0.Px7.1.m1.1b"><msub id="S6.SS0.SSS0.Px7.1.m1.1.1" xref="S6.SS0.SSS0.Px7.1.m1.1.1.cmml"><mi id="S6.SS0.SSS0.Px7.1.m1.1.1.2" xref="S6.SS0.SSS0.Px7.1.m1.1.1.2.cmml">F</mi><mn id="S6.SS0.SSS0.Px7.1.m1.1.1.3" xref="S6.SS0.SSS0.Px7.1.m1.1.1.3.cmml">1</mn></msub><annotation-xml encoding="MathML-Content" id="S6.SS0.SSS0.Px7.1.m1.1c"><apply id="S6.SS0.SSS0.Px7.1.m1.1.1.cmml" xref="S6.SS0.SSS0.Px7.1.m1.1.1"><csymbol cd="ambiguous" id="S6.SS0.SSS0.Px7.1.m1.1.1.1.cmml" xref="S6.SS0.SSS0.Px7.1.m1.1.1">subscript</csymbol><ci id="S6.SS0.SSS0.Px7.1.m1.1.1.2.cmml" xref="S6.SS0.SSS0.Px7.1.m1.1.1.2">𝐹</ci><cn id="S6.SS0.SSS0.Px7.1.m1.1.1.3.cmml" type="integer" xref="S6.SS0.SSS0.Px7.1.m1.1.1.3">1</cn></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.SS0.SSS0.Px7.1.m1.1d">F_{1}</annotation><annotation encoding="application/x-llamapun" id="S6.SS0.SSS0.Px7.1.m1.1e">italic_F start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT</annotation></semantics></math> 得分

<math alttext="F_{1}" class="ltx_Math" display="inline" id="S6.SS0.SSS0.Px7.p1.1.m1.1"><semantics id="S6.SS0.SSS0.Px7.p1.1.m1.1a"><msub id="S6.SS0.SSS0.Px7.p1.1.m1.1.1" xref="S6.SS0.SSS0.Px7.p1.1.m1.1.1.cmml"><mi id="S6.SS0.SSS0.Px7.p1.1.m1.1.1.2" xref="S6.SS0.SSS0.Px7.p1.1.m1.1.1.2.cmml">F</mi><mn id="S6.SS0.SSS0.Px7.p1.1.m1.1.1.3" xref="S6.SS0.SSS0.Px7.p1.1.m1.1.1.3.cmml">1</mn></msub><annotation-xml encoding="MathML-Content" id="S6.SS0.SSS0.Px7.p1.1.m1.1b"><apply id="S6.SS0.SSS0.Px7.p1.1.m1.1.1.cmml" xref="S6.SS0.SSS0.Px7.p1.1.m1.1.1"><csymbol cd="ambiguous" id="S6.SS0.SSS0.Px7.p1.1.m1.1.1.1.cmml" xref="S6.SS0.SSS0.Px7.p1.1.m1.1.1">subscript</csymbol><ci id="S6.SS0.SSS0.Px7.p1.1.m1.1.1.2.cmml" xref="S6.SS0.SSS0.Px7.p1.1.m1.1.1.2">𝐹</ci><cn id="S6.SS0.SSS0.Px7.p1.1.m1.1.1.3.cmml" type="integer" xref="S6.SS0.SSS0.Px7.p1.1.m1.1.1.3">1</cn></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.SS0.SSS0.Px7.p1.1.m1.1c">F_{1}</annotation><annotation encoding="application/x-llamapun" id="S6.SS0.SSS0.Px7.p1.1.m1.1d">italic_F start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT</annotation></semantics></math> 分数构成了精度和召回率的调和平均数，综合考虑了假阳性和假阴性。 当在精度和召回率之间需要平衡时，它是一个明智的选择。 <math alttext="F_{1}" class="ltx_Math" display="inline" id="S6.SS0.SSS0.Px7.p1.2.m2.1"><semantics id="S6.SS0.SSS0.Px7.p1.2.m2.1a"><msub id="S6.SS0.SSS0.Px7.p1.2.m2.1.1" xref="S6.SS0.SSS0.Px7.p1.2.m2.1.1.cmml"><mi id="S6.SS0.SSS0.Px7.p1.2.m2.1.1.2" xref="S6.SS0.SSS0.Px7.p1.2.m2.1.1.2.cmml">F</mi><mn id="S6.SS0.SSS0.Px7.p1.2.m2.1.1.3" xref="S6.SS0.SSS0.Px7.p1.2.m2.1.1.3.cmml">1</mn></msub><annotation-xml encoding="MathML-Content" id="S6.SS0.SSS0.Px7.p1.2.m2.1b"><apply id="S6.SS0.SSS0.Px7.p1.2.m2.1.1.cmml" xref="S6.SS0.SSS0.Px7.p1.2.m2.1.1"><csymbol cd="ambiguous" id="S6.SS0.SSS0.Px7.p1.2.m2.1.1.1.cmml" xref="S6.SS0.SSS0.Px7.p1.2.m2.1.1">subscript</csymbol><ci id="S6.SS0.SSS0.Px7.p1.2.m2.1.1.2.cmml" xref="S6.SS0.SSS0.Px7.p1.2.m2.1.1.2">𝐹</ci><cn id="S6.SS0.SSS0.Px7.p1.2.m2.1.1.3.cmml" type="integer" xref="S6.SS0.SSS0.Px7.p1.2.m2.1.1.3">1</cn></apply></annotation-xml><annotation encoding="application/x-tex" id="S6.SS0.SSS0.Px7.p1.2.m2.1c">F_{1}</annotation><annotation encoding="application/x-llamapun" id="S6.SS0.SSS0.Px7.p1.2.m2.1d">italic_F start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT</annotation></semantics></math> 分数可以通过以下公式计算：

|  | <math alttext="\displaystyle F_{1}=" class="ltx_Math" display="inline" id="S6.E13X.2.1.1.m1.1"><semantics id="S6.E13X.2.1.1.m1.1a"><mrow id="S6.E13X.2.1.1.m1.1.1" xref="S6.E13X.2.1.1.m1.1.1.cmml"><msub id="S6.E13X.2.1.1.m1.1.1.2" xref="S6.E13X.2.1.1.m1.1.1.2.cmml"><mi id="S6.E13X.2.1.1.m1.1.1.2.2" mathsize="90%" xref="S6.E13X.2.1.1.m1.1.1.2.2.cmml">F</mi><mn id="S6.E13X.2.1.1.m1.1.1.2.3" mathsize="90%" xref="S6.E13X.2.1.1.m1.1.1.2.3.cmml">1</mn></msub><mo id="S6.E13X.2.1.1.m1.1.1.1" mathsize="90%" xref="S6.E13X.2.1.1.m1.1.1.1.cmml">=</mo></mrow><annotation-xml encoding="MathML-Content" id="S6.E13X.2.1.1.m1.1b">\displaystyle F_{1}=</annotation><annotation encoding="application/x-tex" id="S6.E13X.2.1.1.m1.1c">\displaystyle F_{1}=</annotation><annotation encoding="application/x-llamapun" id="S6.E13X.2.1.1.m1.1d">italic_F start_POSTSUBSCRIPT 1 end_POSTSUBSCRIPT =</annotation></semantics></math> | <math alttext="\displaystyle 2*\frac{Precision*Recall}{Precision+Recall}" class="ltx_Math" display="inline" id="S6.E13X.3.2.2.m1.1"><semantics id="S6.E13X.3.2.2.m1.1a"><mrow id="S6.E13X.3.2.2.m1.1.1" xref="S6.E13X.3.2.2.m1.1.1.cmml"><mn id="S6.E13X.3.2.2.m1.1.1.2" mathsize="90%" xref="S6.E13X.3.2.2.m1.1.1.2.cmml">2</mn><mo id="S6.E13X.3.2.2.m1.1.1.1" lspace="0.222em" mathsize="90%" rspace="0.222em" xref="S6.E13X.3.2.2.m1.1.1.1.cmml">∗</mo><mstyle displaystyle="true" id="S6.E13X.3.2.2.m1.1.1.3" xref="S6.E13X.3.2.2.m1.1.1.3.cmml"><mfrac id="S6.E13X.3.2.2.m1.1.1.3a" xref="S6.E13X.3.2.2.m1.1.1.3.cmml"><mrow id="S6.E13X.3.2.2.m1.1.1.3.2" xref="S6.E13X.3.2.2.m1.1.1.3.2.cmml">Precision⁢Recall⁢c⁢i⁢s⁢i⁢o⁢n∗R</mrow><mo id="S6.E13X.3.2.2.m1.1.1.3.2.1" lspace="0.222em" mathsize="90%" rspace="0.222em" xref="S6.E13X.3.2.2.m1.1.1.3.2.1.cmml">∗</mo><mi id="S6.E13X.3.2.2.m1.1.1.3.2.3" mathsize="90%" xref="S6.E13X.3.2.2.m1.1.1.3.2.3.cmml">Recall⁢e⁢c⁢a⁢l⁢l</mi></mrow><mrow id="S6.E13X.3.2.2.m1.1.1.3.3" xref="S6.E13X.3.2.2.m1.1.1.3.3.cmml"><mi id="S6.E13X.3.2.2.m1.1.1.3.3.2" mathsize="90%" xref="S6.E13X.3.2.2.m1.1.1.3.3.2.cmml">Precision⁢Recall⁢c⁢i⁢s⁢i⁢o⁢n</mi><mo id="S6.E13X.3.2.2.m1.1.1.3.3.1" xref="S6.E13X.3.2.2.m1.1.1.3.3.1.cmml">+</mo><mi id="S6.E13X.3.2.2.m1.1.1.3.3.3" mathsize="90%" xref="S6.E13X.3.2.2.m1.1.1.3.3.cmml">Recall⁢c⁢a⁢l⁢l</mi></mrow></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E13X.3.2.2.m1.1b"><apply id="S6.E13X.3.2.2.m1.1.1.cmml" xref="S6.E13X.3.2.2.m1.1.1"><cn id="S6.E13X.3.2.2.m1.1.1.2.cmml" type="integer" xref="S6.E13X.3.2.2.m1.1.1.2">2</cn><apply id="S6.E13X.3.2.2.m1.1.1.3.cmml" xref="S6.E13X.3.2.2.m1.1.1.3"><apply id="S6.E13X.3.2.2.m1.1.1.3.2.cmml" xref="S6.E13X.3.2.2.m1.1.1.3.2"><apply id="S6.E13X.3.2.2.m1.1.1.3.2.2.cmml" xref="S6.E13X.3.2.2 |
| --- | --- | --- |
|  |  | <math alttext="\displaystyle=\frac{2TP}{2TP+FP+FN}" class="ltx_Math" display="inline" id="S6.E13Xa.2.1.1.m1.1"><semantics id="S6.E13Xa.2.1.1.m1.1a"><mrow id="S6.E13Xa.2.1.1.m1.1.1" xref="S6.E13Xa.2.1.1.m1.1.1.cmml"><mo id="S6.E13Xa.2.1.1.m1.1.1.1" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.1.cmml">=</mo><mstyle displaystyle="true" id="S6.E13Xa.2.1.1.m1.1.1.3" xref="S6.E13Xa.2.1.1.m1.1.1.3.cmml"><mfrac id="S6.E13Xa.2.1.1.m1.1.1.3a" xref="S6.E13Xa.2.1.1.m1.1.1.3.cmml"><mrow id="S6.E13Xa.2.1.1.m1.1.1.3.2" xref="S6.E13Xa.2.1.1.m1.1.1.3.2.cmml"><mn id="S6.E13Xa.2.1.1.m1.1.1.3.2.2" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.2.2.cmml">2</mn><mo id="S6.E13Xa.2.1.1.m1.1.1.3.2.1" xref="S6.E13Xa.2.1.1.m1.1.1.3.2.1.cmml">⁢</mo><mi id="S6.E13Xa.2.1.1.m1.1.1.3.2.3" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.2.3.cmml">T</mi><mo id="S6.E13Xa.2.1.1.m1.1.1.3.2.1a" xref="S6.E13Xa.2.1.1.m1.1.1.3.2.1.cmml">⁢</mo><mi id="S6.E13Xa.2.1.1.m1.1.1.3.2.4" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.2.4.cmml">P</mi></mrow><mrow id="S6.E13Xa.2.1.1.m1.1.1.3.3" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.cmml"><mrow id="S6.E13Xa.2.1.1.m1.1.1.3.3.2" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.2.cmml"><mn id="S6.E13Xa.2.1.1.m1.1.1.3.3.2.2" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.2.2.cmml">2</mn><mo id="S6.E13Xa.2.1.1.m1.1.1.3.3.2.1" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E13Xa.2.1.1.m1.1.1.3.3.2.3" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.2.3.cmml">T</mi><mo id="S6.E13Xa.2.1.1.m1.1.1.3.3.2.1a" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.2.1.cmml">⁢</mo><mi id="S6.E13Xa.2.1.1.m1.1.1.3.3.2.4" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.2.4.cmml">P</mi></mrow><mo id="S6.E13Xa.2.1.1.m1.1.1.3.3.1" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E13Xa.2.1.1.m1.1.1.3.3.3" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.3.cmml"><mi id="S6.E13Xa.2.1.1.m1.1.1.3.3.3.2" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.3.2.cmml">F</mi><mo id="S6.E13Xa.2.1.1.m1.1.1.3.3.3.1" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.3.1.cmml">⁢</mo><mi id="S6.E13Xa.2.1.1.m1.1.1.3.3.3.3" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.3.3.cmml">P</mi></mrow><mo id="S6.E13Xa.2.1.1.m1.1.1.3.3.1a" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.1.cmml">+</mo><mrow id="S6.E13Xa.2.1.1.m1.1.1.3.3.4" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.4.cmml"><mi id="S6.E13Xa.2.1.1.m1.1.1.3.3.4.2" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.4.2.cmml">F</mi><mo id="S6.E13Xa.2.1.1.m1.1.1.3.3.4.1" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.4.1.cmml">⁢</mo><mi id="S6.E13Xa.2.1.1.m1.1.1.3.3.4.3" mathsize="90%" xref="S6.E13Xa.2.1.1.m1.1.1.3.3.4.3.cmml">N</mi></mrow></mrow></mfrac></mstyle></mrow><annotation-xml encoding="MathML-Content" id="S6.E13Xa.2.1.1.m1.1b"><apply id="S6.E13Xa.2.1.1.m1.1.1.cmml" xref="S6.E13Xa.2.1.1.m1.1.1"><csymbol cd="latexml" id="S6.E13Xa.2.1.1.m1.1.1.2.cmml" xref="S6.E13Xa.2.1.1.m1.1.1.2">absent</csymbol><apply id="S6.E13Xa.2.1.1.m1.1.1.3.cmml" xref="S6.E13Xa.2.1.1.m1.1.1.3"><apply id="S6.E13Xa.2.1.1.m1.1.1.3.2.cmml" xref="S6.E13Xa.2.1.1.m1.1.1.3.2"><cn id="S6.E13Xa.2.1.1.m1.1.1.3.2.2.cmml" type="integer" xref="S6.E13 |

##### AUROC

AUROC 指标来源于接收器操作特性曲线，它考虑了在不同分类阈值下的真正例率和假正例率，这对在不同阈值下评估分类效果非常有用。这在需要特定假正例和遗漏率的场景中尤为关键，特别是在不平衡数据集和二分类任务的背景下。由于零样本检测方法的检测率显著依赖于阈值，AUROC 指标通常被用来评估它们在所有可能阈值下的表现。AUROC 的计算公式如下：

|  | <math alttext="AUROC=\int_{0}^{1}\frac{TP}{TP+FP}\mathrm{d}\frac{FP}{FP+TN}" class="ltx_Math" display="block" id="S6.E14.m1.1"><semantics id="S6.E14.m1.1a"><mrow id="S6.E14.m1.1.1" xref="S6.E14.m1.1.1.cmml"><mrow id="S6.E14.m1.1.1.2" xref="S6.E14.m1.1.1.2.cmml"><mi id="S6.E14.m1.1.1.2.2" mathsize="90%" xref="S6.E14.m1.1.1.2.2.cmml">𝐴</mi><mo id="S6.E14.m1.1.1.2.1" xref="S6.E14.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E14.m1.1.1.2.3" mathsize="90%" xref="S6.E14.m1.1.1.2.3.cmml">𝑈</mi><mo id="S6.E14.m1.1.1.2.1a" xref="S6.E14.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E14.m1.1.1.2.4" mathsize="90%" xref="S6.E14.m1.1.1.2.4.cmml">𝑅</mi><mo id="S6.E14.m1.1.1.2.1b" xref="S6.E14.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E14.m1.1.1.2.5" mathsize="90%" xref="S6.E14.m1.1.1.2.5.cmml">𝑂</mi><mo id="S6.E14.m1.1.1.2.1c" xref="S6.E14.m1.1.1.2.1.cmml">⁢</mo><mi id="S6.E14.m1.1.1.2.6" mathsize="90%" xref="S6.E14.m1.1.1.2.6.cmml">𝐶</mi></mrow><mo id="S6.E14.m1.1.1.1" mathsize="90%" rspace="0.111em" xref="S6.E14.m1.1.1.1.cmml">=</mo><mrow id="S6.E14.m1.1.1.3" xref="S6.E14.m1.1.1.3.cmml"><msubsup id="S6.E14.m1.1.1.3.1" xref="S6.E14.m1.1.1.3.1.cmml"><mo id="S6.E14.m1.1.1.3.1.2.2" maxsize="90%" minsize="90%" stretchy="true" xref="S6.E14.m1.1.1.3.1.2.2.cmml">∫</mo><mn id="S6.E14.m1.1.1.3.1.2.3" mathsize="90%" xref="S6.E14.m1.1.1.3.1.2.3.cmml">0</mn><mn id="S6.E14.m1.1.1.3.1.3" mathsize="90%" xref="S6.E14.m1.1.1.3.1.3.cmml">1</mn></msubsup><mrow id="S6.E14.m1.1.1.3.2" xref="S6.E14.m1.1.1.3.2.cmml"><mfrac id="S6.E14.m1.1.1.3.2.2" xref="S6.E14.m1.1.1.3.2.2.cmml"><mrow id="S6.E14.m1.1.1.3.2.2.2" xref="S6.E14.m1.1.1.3.2.2.2.cmml"><mi id="S6.E14.m1.1.1.3.2.2.2.2" mathsize="90%" xref="S6.E14.m1.1.1.3.2.2.2.2.cmml">𝑇</mi><mo id="S6.E14.m1.1.1.3.2.2.2.1" xref="S6.E14.m1.1.1.3.2.2.2.1.cmml">⁢</mo><mi id="S6.E14.m1.1.1.3.2.2.2.3" mathsize="90%" xref="S6.E14.m1.1.1.3.2.2.2.3.cmml">𝑃</mi></mrow><mrow id="S6.E14.m1.1.1.3.2.2.3" xref="S6.E14.m1.1.1.3.2.2.3.cmml"><mrow id="S6.E14.m1.1.1.3.2.2.3.2" xref="S6.E14.m1.1.1.3.2.2.3.2.cmml"><mi id="S6.E14.m1.1.1.3.2.2.3.2.2" mathsize="90%" xref="S6.E14.m1.1.1.3.2.2.3.2.2.cmml">𝑇</mi><mo id="S6.E14.m1.1.1.3.2.2.3.2.1" xref="S6.E14.m1.1.1.3.2.2.3.2.1.cmml">⁢</mo><mi id="S6.E14.m1.1.1.3.2.2.3.2.3" mathsize="90%" xref="S6.E14.m1.1.1.3.2.2.3.2.3.cmml">𝑃</mi></mrow><mo id="S6.E14.m1.1.1.3.2.2.3.1" mathsize="90%" xref="S6.E14.m1.1.1.3.2.2.3.1.cmml">+</mo><mrow id="S6.E14.m1.1.1.3.2.2.3.3" xref="S6.E14.m1.1.1.3.2.2.3.3.cmml"><mi id="S6.E14.m1.1.1.3.2.2.3.3.2" mathsize="90%" xref="S6.E14.m1.1.1.3.2.2.3.3.2.cmml">𝐹</mi><mo id="S6.E14.m1.1.1.3.2.2.3.3.1" xref="S6.E14.m1.1.1.3.2.2.3.3.1.cmml">⁢</mo><mi id="S6.E14.m1.1.1.3.2.2.3.3.3" mathsize="90%" xref="S6.E14.m1.1.1.3.2.2.3.3.3.cmml">𝑃</mi></mrow></mrow></mfrac><mo id="S6.E14.m1.1.1.3.2.1" lspace="0em" xref="S6.E14.m1.1.1.3.2.1.cmml">⁢</mo><mrow id="S6.E14.m1.1.1.3.2.3" xref="S6.E14.m1.1.1.3.2.3.cmml"><mo id="S6.E14.m1.1.1.3.2.3.1" mathsize="90%" rspace="0em" xref="S6.E14.m1.1.1.3.2.3.1.cmml">d</mo><mfrac id="S6.E14.m1.1.1.3.2.3.2" xref="S6.E14.m1.1.1.3.2.3.2.cmml"><mrow id="S6.E14.m1.1.1.3.2.3.2.2" xref="S6.E14.m1.1.1.3.2.3.2.2.cmml"><mi id="S6.E14.m1.1.1.3.2.3.2.2. |
| --- | --- |

## 7 个 LLM 生成文本检测的重要问题

在本节中，我们讨论了当代 SOTA 技术在检测由 LLM 生成的文本时面临的主要问题和局限性。需要注意的是，尚未有技术被认可为万无一失。这里阐明的问题可能特别涉及一个或多个类别的检测器。

### 7.1 分布外挑战

分布外问题显著阻碍了当前专门用于检测 LLM 生成文本的技术的有效性。本节阐述了这些检测器在面对领域和语言变化时的局限性。

##### 跨领域

跨领域应用的困境是许多 NLP 任务固有的普遍挑战。Antoun 等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib6)）和 Li 等人（[2023c](https://arxiv.org/html/2310.14724v3#bib.bib120)）的研究突显了复杂检测器性能中的显著局限，包括但不限于 DetectGPT Mitchell 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib146)）、GLTR Gehrmann、Strobelt 和 Rush（[2019](https://arxiv.org/html/2310.14724v3#bib.bib71)）以及微调的 Roberta 方法在跨领域数据上的应用。这些检测器在面对现实场景中常见的分布外数据时表现出显著的性能下降，有些分类器的效果仅略好于随机分类。这种高报告性能与实际可靠性之间的差距突显了对现有方法进行关键评估和改进的必要性。

##### 跨语言

跨语言应用的问题引入了一系列复杂的挑战，这些挑战阻碍了现有检测器研究的全球适用性。主要地，当前为 LLM 生成文本设计的检测器主要针对单语应用，往往忽略了跨多语言评估和优化性能。Wang 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib227)) 和 Chaka ([2023](https://arxiv.org/html/2310.14724v3#bib.bib27)) 指出了尽管存在某些语言迁移能力，但在多语言 LLM 生成文本检测器中观察到的控制缺失。我们强调这些跨语言挑战，因为解决这些问题对于提升 LLM 生成文本检测器的可用性和公平性至关重要。此外，最近的研究 Liang 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib122)) 发现，当处理由非母语英语使用者撰写的文本时，最先进的检测器的性能明显下降。虽然采用有效的提示策略可以减轻这种偏见，但也无意中使生成的文本绕过了检测器。因此，检测器可能会无意中惩罚那些表现出非标准语言风格或使用有限表达的作者，从而引入检测过程中的歧视问题。

##### 跨语言模型

在 LLM 生成文本检测任务中，另一个显著的分布外问题是跨 LLMs 挑战。当前的白盒检测方法主要依赖于访问源模型并比较如对数似然这样的特征。因此，当遇到由未知 LLMs 生成的文本时，白盒方法可能表现不佳。DetectGPT Mitchell 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib146)) 的结果突显了白盒方法在处理未知模型时的脆弱性，特别是在遇到如 GPT-3.5-Turbo 这样的强大模型时。然而，Fast-DetectGPT Bao 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib16)) 的近期研究表明，与替代模型的统计比较可以显著缓解这个问题。此外，在应用白盒方法之前识别生成模型的类型可能是有益的。在这方面，Siniff Li 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib118))、SeqXGPT Wang 等人 ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib226)) 和 LLMDet Wu 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib236)) 的方法可能提供有用的见解。另一方面，基于神经分类器的方法，尤其是那些容易过拟合训练数据的微调分类器，可能在识别训练期间未见过的 LLMs 类型时会遇到困难。因此，对于新出现的 LLMs，检测器可能无法有效识别它们 Pagnoni、Graciarena 和 Tsvetkov ([2022b](https://arxiv.org/html/2310.14724v3#bib.bib164))。例如，OpenAI 检测器¹⁵¹⁵15openai-community/roberta-large-openai-detector（在 GPT-2 生成的文本上训练）在区分 GPT-3.5-Turbo 和 GPT-4 生成的文本时表现挣扎，仅达到 74.74%的 AUROC，而在 GPT-2 生成的文本上表现几乎完美 Bao 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib16))。Sarvazyan 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib184)) 的结果表明，监督 LLM 生成文本检测器在模型规模上展现了良好的泛化能力，但在模型家族间的泛化存在限制。因此，提升神经分类器的跨 LLMs 鲁棒性对于实际部署检测器至关重要。不过，经过 Roberta 微调的分类器仍具备强大的迁移能力，且通过在仅有的几百个样本上进行额外的微调，检测器可以有效泛化到其他模型生成的文本。因此，将来自不同来源的 LLM 生成文本纳入训练数据中，可能显著提高检测器在实际应用中的跨 LLMs 鲁棒性，即使样本量很小。

### 7.2 潜在攻击

潜在攻击显著助长了当前 LLM 生成文本检测器的持续不可靠性。我们介绍了当前有效的攻击，以促使研究人员关注更全面的防御措施。

##### 同义词攻击

同义词攻击是对使用水印技术的检测器、以及经过微调的监督检测器和零样本检测器（Sadasivan 等，[2023](https://arxiv.org/html/2310.14724v3#bib.bib181)；Orenstrakh 等，[2023](https://arxiv.org/html/2310.14724v3#bib.bib161)）最有效的攻击之一。其基本原理涉及对大型语言模型（LLM）的输出应用轻量级同义词模型，通过同义词转换改变文本的词汇和句法特征的分布，从而混淆检测器。Sadasivan 等（[2023](https://arxiv.org/html/2310.14724v3#bib.bib181)）报告了 Parrot（Damodaran，[2021](https://arxiv.org/html/2310.14724v3#bib.bib48)），一个基于 T5 的同义词模型，以及 DIPPER（Krishna 等，[2023](https://arxiv.org/html/2310.14724v3#bib.bib107)），一个 11B 同义词模型，该模型允许调整同义词多样性和内容重排序的程度，攻击现有检测方法的整体优越性。尽管基于检索的方法已被证明能有效防御同义词攻击（Krishna 等，[2023](https://arxiv.org/html/2310.14724v3#bib.bib107)），但实施这些防御措施需要语言模型 API 提供商的持续维护，并且仍然易受递归同义词攻击的影响（Sadasivan 等，[2023](https://arxiv.org/html/2310.14724v3#bib.bib181)）。

##### 对抗攻击

普通的 LLM 生成文本容易被识别，但对抗性扰动（如替换）可以有效降低检测器的准确性 Peng et al. ([2024](https://arxiv.org/html/2310.14724v3#bib.bib165))。我们总结了对处理文本特征的攻击作为对抗攻击，包括截断（裁剪特征或输入的一部分）Shen et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib193))，洗牌（随机打乱输入的词序）Lee et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib115))，变异（字符和单词变异）Liang, Guerrero, 和 Alsmadi ([2023](https://arxiv.org/html/2310.14724v3#bib.bib121))，词汇替换（根据上下文替换其他合适的单词）Shi 和 Huang ([2020](https://arxiv.org/html/2310.14724v3#bib.bib195))；Ren et al. ([2019](https://arxiv.org/html/2310.14724v3#bib.bib177))；Crothers et al. ([2022](https://arxiv.org/html/2310.14724v3#bib.bib45)) 和拼写错误 Gao et al. ([2018a](https://arxiv.org/html/2310.14724v3#bib.bib67))。还有一些对抗攻击框架，如 TextAttack Morris et al. ([2020](https://arxiv.org/html/2310.14724v3#bib.bib150))，可以从四个组件构建攻击：目标函数、一组约束、转换和搜索方法。Shi et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib196)) 和 He et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib83)) 报告了置换方法在攻击检测器上的有效性。具体而言，Shi et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib196)) 基于上下文用同义词替换单词，这对微调后的分类器形成了有效攻击，水印 Kirchenbauer et al. ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib101)) 和 DetectGPT Mitchell et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib146))，分别降低了检测器的性能超过 18%、10% 和 25%。He et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib83)) 使用概率加权词汇显著性 Ren et al. ([2019](https://arxiv.org/html/2310.14724v3#bib.bib177)) 生成对抗示例，这进一步保持了语义相似性。

Stiff 和 Johansson ([2022](https://arxiv.org/html/2310.14724v3#bib.bib200)) 利用 DeepWordBug Gao 等人 ([2018b](https://arxiv.org/html/2310.14724v3#bib.bib68)) 的对抗攻击算法对生成的文本引入了字符级扰动，包括相邻字符交换、字符替换、删除和插入，这导致 OpenAI 大型检测器的性能减少了一半以上。¹⁶¹⁶16openai-community/roberta-large-openai-detector Wolff ([2020](https://arxiv.org/html/2310.14724v3#bib.bib235)) 提出了针对这些检测器的两种黑箱攻击类型：用视觉上相似的同形异义字符随机替换字符和故意拼写错误。这些攻击将流行的神经文本检测器的召回率分别大幅降低至 0.26% 和 22.68%。此外，Bhat 和 Parthasarathy ([2020](https://arxiv.org/html/2310.14724v3#bib.bib21)) 表明，检测器对句法扰动更为敏感，包括打断较长的句子、删除定冠词、使用保留语义的规则转换（如将 “that’s” 改为 “that is”）和重新格式化机器生成的文本段落。

尽管现有的检测方法对对抗攻击具有高度敏感性，但不同类型的检测器对这些攻击表现出不同程度的抗性。Antoun 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib7)) 报告称，监督学习方法是应对这些攻击的有效防御措施：对抗样本的训练可以显著提高检测器识别被这些攻击操控的文本的能力。此外，Kulkarni 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib109)) 探讨了语义扰动对 Grover 检测器的影响，发现同义词替换、虚假替换、插入而非替换以及替换位置的变化对 Grover 的检测能力没有影响。然而，对抗嵌入技术可以有效地欺骗 Grover，将虚假文章分类为真实的。尽管对抗攻击的分布特征可以被微调分类器学习，从而形成强有力的防御，但这种攻击仍显著降低了微调分类器的性能。

##### 提示攻击

诱导攻击对当前的 LLM 生成文本检测技术构成了重大挑战。LLM 生成文本的质量与指示 LLM 生成文本的提示的复杂性有关。随着模型和语料库规模的增加，LLM 展现出卓越的 ICL 能力，具备更复杂的文本生成能力。已开发出许多高效的提示方法，包括少量样本提示（Brown et al., [2020](https://arxiv.org/html/2310.14724v3#bib.bib25)）、组合提示（Zhao et al., [2021](https://arxiv.org/html/2310.14724v3#bib.bib257)）、思维链（CoT）（Wei et al., [2022](https://arxiv.org/html/2310.14724v3#bib.bib231)）和零样本 CoT（Kojima et al., [2022](https://arxiv.org/html/2310.14724v3#bib.bib106)）等，这些方法显著提升了 LLM 的质量和能力。现有的 LLM 生成文本检测器主要利用简单直接提示创建的数据集。例如，Guo et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib78))的研究表明，检测器可能难以识别使用复杂提示生成的文本。Liu et al. ([2023d](https://arxiv.org/html/2310.14724v3#bib.bib133))报告了当面临不同提示时，使用微调语言模型的检测器检测能力显著下降，这表明不同的提示会导致现有检测器检测性能的显著差异（Koike, Kaneko, and Okazaki ([2023a](https://arxiv.org/html/2310.14724v3#bib.bib104)））。

Lu et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib134))提出的基于替换的上下文示例优化方法，采用复杂的提示来绕过当前检测系统的防御。这导致曲线下面积（AUC）的显著降低，平均减少了 0.54，并且与释义攻击相比，成功率更高，文本质量更佳。值得一提的是，上述释义攻击和对抗攻击也可以通过精心设计的提示来执行（Shi et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib196)）；Koike, Kaneko, and Okazaki ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib105)））。随着提示工程的持续研究，提示攻击带来的风险预计将进一步上升。这突显了开发更强大的检测方法的必要性，以有效应对这些不断演变的威胁。

##### 训练威胁模型

对语言模型的进一步训练已初步证明能够有效攻击现有的检测器。Nicks 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib159)）将各种开源和商业检测器的“人性”评分用作强化学习的奖励函数，这样可以对语言模型进行微调，以混淆现有检测器。在不显著改变模型的情况下，进一步微调 Llama-2-7B 可以在短时间的训练期内将 OpenAI RoBERTa-Large 检测器的 AUROC 从 0.84 降低到 0.62。Schneider 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib186)）展示了类似的思想：使用强化学习来优化生成模型可以成功绕过基于 BERT 的分类器，其检测准确率低至 0.15 AUROC，即使在使用语言特征作为奖励函数时。Kumarage 等人（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib111)）提出了一个名为 EScaPe 的通用规避框架，以指导 PLM 生成可能误导检测器的“类人文本”。通过规避性软提示学习和迁移，DetectGPT 和 OpenAI 检测器的性能可以有效降低高达 40% AUROC。Henrique、Kucharavy 和 Guerraoui（[2023](https://arxiv.org/html/2310.14724v3#bib.bib85)）的结果揭示了检测器的另一种潜在漏洞。如果生成模型可以访问用于训练检测器的人工文本并用其进行微调，则无法使用检测器对该生成模型进行文本检测。这表明，训练于更多人工编写语料库的 LLM 将更能抵御现有检测器，而针对特定检测器的训练可以为 LLM 提供一把尖锐的矛来突破其防御。

### 7.3 现实世界的数据问题

##### 非纯粹 LLM 生成文本的检测

在实际操作中，许多文本并非完全由 LLM 生成，甚至可能包含人类编写的文本的混合。具体来说，这可以被分类为数据混合文本或人工编辑文本。数据混合文本指的是人类编写的文本和 LLM 生成的文本在句子或段落层级上的混合。例如，在一份文档中，有些句子可能是由 LLM 生成的，而其他句子则是由人类编写的。在这种情况下，识别文档的类别变得具有挑战性。数据混合文本需要更细粒度的检测方法，如句子级检测，以有效应对这一挑战。然而，目前 LLM 生成文本的检测器在处理短文本时表现不佳。最近的研究，如王等人（[2023a](https://arxiv.org/html/2310.14724v3#bib.bib226)）的研究，表明句子级检测似乎是可行的。此外，我们很高兴看到有研究开始提出并尝试解决这一问题。曾等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib254)）提出了一种两步法来有效识别人类编写和 LLM 生成文本的混合。这种方法首先使用对比学习来区分 LLM 生成的内容和人类编写的内容。然后，它计算相邻原型之间的相似度，假设在最不相似的相邻原型之间存在一个边界。

另一个尚未充分讨论的问题是人工编辑的文本。例如，在应用 LLM 生成文本后，人们常常会编辑和修改某些词汇或段落。这类文本的检测具有很大的挑战性，是我们必须面对的问题，因为它在现实应用中非常普遍。因此，迫切需要组织相关的数据集并定义任务以解决这一问题。应对这个问题的一个潜在方法是基于从意图改写和对抗扰动攻击的实验结果。这些方法有效地模拟了个人如何使用 LLM 来改进文本或进行词汇替换。然而，当处理意图改写的文本时，当前主流的检测器在性能上往往会退化，尽管某些黑箱检测器显示出相对较好的鲁棒性。另一个潜在的解决方案可能涉及将检测任务细化到单词级别，但截至目前，还没有直接针对这一问题的研究。

##### 数据模糊性

数据歧义仍然是 LLM 生成文本检测领域的挑战，与检测技术本身的内在机制紧密相关。LLM 在各个领域的广泛应用加剧了这一问题，使得分辨训练数据是人工编写还是 LLM 生成的文本变得越来越困难。在误以为 LLM 生成的文本是人工编写的情况下，将其用作训练数据，会不经意地引发一个有害的循环。在这个循环中，训练出来的检测器在区分人工编写和 LLM 生成的文本方面表现出效能下降，从而破坏了检测器研究的基础前提。必须承认，这一困境对所有检测研究领域构成了重大而广泛的威胁，但据我们了解，目前没有现有研究正式解决这一问题。Alemohammad 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib3)）提出了一个额外的潜在风险，认为数据歧义可能导致 LLM 生成数据在后续模型的训练过程中被重复使用。这种情况可能会对这些新兴 LLM 的文本生成质量产生不利影响，从而破坏致力于 LLM 生成文本检测的研究领域。

### 7.4 模型规模对检测器的影响

许多研究人员关心模型大小对检测器的影响，这可以从两个角度来看：一个是生成模型的大小，另一个是监督分类器的大小。生成模型的大小与生成文本的质量密切相关。一般来说，小模型生成的文本更容易被识别，而大模型生成的文本则对检测造成更大的挑战。另一个关注的问题是，不同大小的模型生成的文本作为训练样本时对检测器的影响。Pu 等人（[2023b](https://arxiv.org/html/2310.14724v3#bib.bib171)）报告称，用中等大小的 LLM 生成的数据训练的检测器可以在没有任何样本的情况下推广到更大的版本，而由过大或过小的模型生成的训练样本可能会降低检测器的泛化能力。Antoun、Sagot 和 Seddah（[2023](https://arxiv.org/html/2310.14724v3#bib.bib8)）进一步探讨了分类器效果与生成模型大小之间的明显负相关性。结果显示，较大的 LLM 生成的文本更难检测，尤其是当分类器在由较小 LLM 生成的数据上训练时。使生成模型的训练集和测试集的分布一致可以提高检测器的性能。从监督分类器的大小角度来看，检测器的检测能力与微调后的语言模型的大小成正比（Guo 等人（[2023](https://arxiv.org/html/2310.14724v3#bib.bib78)））。然而，最近的发现表明，尽管较大的检测器在与训练集分布相同的测试集上表现更好，但其泛化能力有所下降。

### 7.5 缺乏有效的评估框架

一个普遍现象是，许多研究声称他们的检测器表现出令人印象深刻且稳健的性能。然而，在实际实验中，这些方法在其他研究人员创建的测试集上往往表现不尽如人意。这种差异是由于研究人员在构建测试集时使用了不同的策略。诸如生成测试集所用的参数、计算环境、文本分布和文本处理策略（包括截断）等变量都可能影响检测器的有效性。由于这些因素的复杂性，即使研究人员遵循相同的数据集生产协议，评估结果的可重复性也往往会受到影响。我们在[第四部分](https://arxiv.org/html/2310.14724v3#S4 "4 Data ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions")中详细阐述了现有基准的局限性，我们倡导创建一个高质量和全面的评估框架。我们鼓励未来的研究积极实施这些框架，以保持测试标准的一致性。此外，我们呼吁专注于特定问题的研究人员公开分享他们的测试集，并强调当前评估框架强大的适应性，以便将其纳入其中。总之，为检测器比较设定一个客观而公平的基准对于推动检测 LLM 生成文本的研究至关重要，而不是继续孤立的努力。

## 8 未来研究方向

在本节中，我们探讨了未来研究可能的方向，旨在更好地构建更高效且实际有效的检测器。

### 8.1 通过攻击构建稳健的检测器

[第 7.2 节](https://arxiv.org/html/2310.14724v3#S7.SS2 "7.2 Potential Attacks ‣ 7 Important Issues of LLM-generated Text Detection ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions") 中介绍的攻击方法包括释义攻击（Sadasivan 等人，[2023](https://arxiv.org/html/2310.14724v3#bib.bib181)）、对抗攻击（He 等人，[2023](https://arxiv.org/html/2310.14724v3#bib.bib83)）以及提示攻击（Lu 等人，[2023](https://arxiv.org/html/2310.14724v3#bib.bib134)）。这些方法突显了当前检测器使用中的主要挑战。尽管近期的研究，如 Yang、Jiang 和 Li（[2023](https://arxiv.org/html/2310.14724v3#bib.bib241)）已针对特定攻击的鲁棒性进行了研究，但往往忽视了其他攻击形式可能带来的威胁。因此，开发和验证多样化的攻击类型至关重要，从而获得对 LLM 生成文本检测器固有漏洞的洞察。我们进一步主张建立全面的基准，以评估现有的检测策略。尽管一些研究（He 等人，[2023](https://arxiv.org/html/2310.14724v3#bib.bib83); Wang 等人，[2023b](https://arxiv.org/html/2310.14724v3#bib.bib227)）声称提供了这样的基准，但已验证攻击的范围和多样性仍然有限。

### 8.2 提高零样本检测器的效能

Zero-shot 方法作为显著稳定的检测器脱颖而出 Deng 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib49))。关键在于，它们为用户提供了增强的可控性和可解释性 Mitrović、Andreoletti 和 Ayoub ([2023](https://arxiv.org/html/2310.14724v3#bib.bib148))。近期研究 (Giorgi 等人，[2023](https://arxiv.org/html/2310.14724v3#bib.bib73)；Liao 等人，[2023b](https://arxiv.org/html/2310.14724v3#bib.bib125)) 阐明了 LLM 生成文本与人类撰写文本之间的明显差异，凸显了二者之间的实质性和可辨别的差距。这一发现激发了 LLM 生成文本检测领域的研究。我们倡导进行更多研究，*深入探讨* LLM 生成文本与人类撰写文本之间的细微区别，涵盖从低维到高维特征的范围。挖掘出更准确区分二者的度量标准可以促进自动检测器的发展，并为决策过程提供更有力的理由。我们观察到，最新出现的黑箱 zero-shot 方法 Yang 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib244))；Mao 等人 ([2024](https://arxiv.org/html/2310.14724v3#bib.bib141))；Zhu 等人 ([2023](https://arxiv.org/html/2310.14724v3#bib.bib260))；Quidwai、Li 和 Dube ([2023](https://arxiv.org/html/2310.14724v3#bib.bib173))；Guo 和 Yu ([2023](https://arxiv.org/html/2310.14724v3#bib.bib80)) 比基于白箱的方法表现出更高的稳定性和应用潜力，因为它们通过提取与白箱模型无关的区分度量来实现。这些方法不依赖于对模型内部工作原理的理解，从而在各种模型和环境中提供了更广泛的适用性。

### 8.3 优化低资源环境下的检测器

许多现代检测技术往往忽视了资源受限环境面临的挑战，忽略了在开发检测器过程中所需的资源。不同数据量设置下各种检测器的相对效能仍未得到充分探讨。同时，确定不同检测方法在获得满意结果所需的最低资源要求也是至关重要的。除了研究模型在不同领域 Rodriguez 等人 ([2022a](https://arxiv.org/html/2310.14724v3#bib.bib179)) 和语言 Wang 等人 ([2023b](https://arxiv.org/html/2310.14724v3#bib.bib227)) 的适应性，我们还倡导研究针对各种攻击策略的防御适应性。这种探索可以指导用户选择在资源受限条件下建立可靠检测器的最佳方法。

### 8.4 针对非纯 LLM 生成文本的检测

在 [子节 7.3](https://arxiv.org/html/2310.14724v3#S7.SS3.SSS0.Px1 "Detection for Not Purely LLM-generated Text ‣ 7.3 Real-World Data Issues ‣ 7 Important Issues of LLM-generated Text Detection ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions") 中，我们突出了一个在实际场景中遇到的重要挑战：检测那些不是纯粹由 LLM 生成的文本。我们通过分别讨论混合数据源的文本和被人类编辑过的文本来检视这个问题，并回顾了最新的相关工作，提出了潜在的解决方案，但这些方案仍待验证。我们强调，组织相关数据集并定义任务以解决这个问题是当前的紧迫需求，因为从根本上讲，这类文本可能是检测器应用中最常遇到的类型。

### 8.5 在数据模糊中构建检测器

一个显著的挑战是验证训练数据的真实性。当从博客和网络评论等来源聚合文本数据时，可能会不经意间包含大量的 LLM 生成文本。这种纳入可能从根本上破坏检测器研究的完整性，形成一个有害的反馈循环。我们敦促未来的检测研究优先考虑真实数据的真实性评估，将此作为未来一个紧迫的挑战。

### 8.6 开发有效的评估框架以适应真实世界

在 [子节 7.5](https://arxiv.org/html/2310.14724v3#S7.SS5 "7.5 Lack of Effective Evaluation Framework ‣ 7 Important Issues of LLM-generated Text Detection ‣ A Survey on LLM-Generated Text Detection: Necessity, Methods, and Future Directions") 中，我们分析了评估环境与实际环境之间的客观差异，这限制了现有检测器在实际应用中的有效性。一方面，许多工作中测试集的构建可能存在偏差，因为它们通常偏向于构建者自己的检测器；另一方面，当前的基准测试通常反映的是理想化的场景，而远离实际应用。我们呼吁研究人员开发一个公平有效的评估框架，紧密结合 LLM 生成检测任务的实际需求。例如，考虑到应用领域的必要性、LLM 生成文本的黑箱性质以及文本可能遇到的各种攻击和后期编辑策略。我们相信，这样的评估框架将推动更具实用性和与真实世界场景相符的检测器的研究和开发。

### 8.7 构建具有虚假信息鉴别能力的检测器

现代检测方法在很大程度上忽视了识别虚假信息的能力。现有的检测器主要强调 LLM 生成文本中的特征分布，而往往忽视了对事实的验证能力。一个有效的检测器应具备识别文本中事实陈述的真实性或虚假的能力。在生成建模初期，当它尚未对社会构成重大挑战时，重点是评估 LLM 生成文本内容的真实性或虚假性，而对其来源关注较少（Schuster et al. ([2020b](https://arxiv.org/html/2310.14724v3#bib.bib190)））。构建具备虚假信息识别能力的检测器可以更准确地归属文本来源，而不仅仅依赖于分布特征，并有助于减缓虚假信息的传播。近期研究（Gao et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib69))；Chern et al. ([2023](https://arxiv.org/html/2310.14724v3#bib.bib33)））强调了 LLM 在检测文本中事实内容方面的潜力。我们建议通过与外部知识库（Asai et al., [2023](https://arxiv.org/html/2310.14724v3#bib.bib10)）或搜索引擎（Liang et al., [2023b](https://arxiv.org/html/2310.14724v3#bib.bib123)）的集成来加强这些努力。

## 9 结论

随着大规模语言模型（LLMs）的广泛发展和应用，LLM 生成文本在我们日常生活中的普遍存在已经从期望变成现实。LLM 生成文本检测器在区分人类编写的文本和 LLM 生成的文本方面发挥了关键作用，作为防范 LLM 被用于生成虚假新闻、从事诈骗或加剧教育不平等等问题的关键防线。在这项调查中，我们介绍了 LLM 生成文本检测的任务，概述了促进 LLM 生成文本能力的来源，并强调了对高效检测器日益增长的需求。我们还列出了受欢迎或有前景的数据集，指出了现有检测器所面临的挑战和要求。此外，我们还阐明了现代检测器的关键限制，包括与分布外数据相关的问题、潜在攻击、现实世界数据问题以及缺乏有效评估框架的问题，以引导研究人员关注该领域的焦点，从而激发创新的想法和方法。最后，我们提出了未来可能的研究方向，这些方向有望指导开发更强大和有效的检测系统。

###### 致谢。

本研究部分得到了中国国家科技委员会重大项目（资助编号：2020AAA0106701）、澳门特别行政区科学技术发展基金（资助编号：FDCT/0070/2022/AMJ, FDCT/060/2022/AFJ）以及澳门大学多年度研究资助（资助编号：MYRG-GRG2023-00006-FST-UMDF）的支持。\starttwocolumn

## 参考文献

+   Abdelnabi 和 Fritz (2021) Abdelnabi, Sahar 和 Mario Fritz. 2021. 对抗性水印变换器：通过数据隐藏追踪文本来源. 见于 *第 42 届 IEEE 安全与隐私研讨会, SP 2021, 美国加利福尼亚州旧金山, 2021 年 5 月 24-27 日*, 页码 121–140, IEEE。

+   Aich, Bhattacharya, 和 Parde (2022) Aich, Ankit, Souvik Bhattacharya, 和 Natalie Parde. 2022. 通过语言特征解释揭示神经假新闻. 见于 *第 29 届国际计算语言学会议, COLING 2022, 韩国庆州, 2022 年 10 月 12-17 日*, 页码 6586–6599, 国际计算语言学委员会。

+   Alemohammad 等人 (2023) Alemohammad, Sina, Josue Casco-Rodriguez, Lorenzo Luzi, Ahmed Imtiaz Humayun, Hossein Babaei, Daniel LeJeune, Ali Siahkoohi, 和 Richard G. Baraniuk. 2023. 自消费生成模型的疯狂. *CoRR*, abs/2307.01850。

+   Aliman 和 Kester (2021) Aliman, Nadisha Marie 和 Leon Kester. 2021. 针对科学和经验对抗性 AI 攻击的认识防御. 见于 *CEUR 工作坊论文集*, 第 2916 卷, CEUR WS。

+   Anthropic (2023) Anthropic. 2023. Claude 模型的模型卡和评估。

+   Antoun 等人 (2023a) Antoun, Wissam, Virginie Mouilleron, Benoît Sagot, 和 Djamé Seddah. 2023a. 朝着鲁棒的语言模型生成文本检测：ChatGPT 是否如此容易被检测？ *CoRR*, abs/2306.05871。

+   Antoun 等人 (2023b) Antoun, Wissam, Virginie Mouilleron, Benoît Sagot, 和 Djamé Seddah. 2023b. 朝着鲁棒的语言模型生成文本检测：ChatGPT 是否如此容易被检测？ *CoRR*, abs/2306.05871。

+   Antoun, Sagot, 和 Seddah (2023) Antoun, Wissam, Benoît Sagot, 和 Djamé Seddah. 2023. 从文本到来源：检测大型语言模型生成内容的结果. *CoRR*, abs/2309.13322。

+   Arase 和 Zhou (2013) Arase, Yuki 和 Ming Zhou. 2013. 单语网页文本中的机器翻译检测. 见于 *第 51 届计算语言学协会年会论文集 (第 1 卷：长篇论文)*, 页码 1597–1607, 计算语言学协会。

+   Asai 等人 (2023) Asai, Akari, Sewon Min, Zexuan Zhong, 和 Danqi Chen. 2023. 基于检索的语言模型及其应用. 见于 *第 61 届计算语言学协会年会论文集 (第 6 卷：教程摘要)*, 页码 41–46。

+   Asghar (2016) Asghar, Nabiha. 2016. Yelp 数据集挑战：评论评分预测. *ArXiv 预印本*, abs/1605.05362。

+   Ayoobi, Shahriar 和 Mukherjee (2023) Ayoobi, Navid, Sadat Shahriar 和 Arjun Mukherjee. 2023. 假冒和 LLM 生成的 LinkedIn 个人资料的迫在眉睫的威胁：检测和预防的挑战与机遇。见于 *第 34 届 ACM 超文本与社交媒体会议论文集*，第 1-10 页。

+   Baayen (2001) Baayen, R Harald. 2001. *词频分布*，第 18 卷。Springer Science & Business Media。

+   Baccianella, Esuli 和 Sebastiani (2010) Baccianella, Stefano, Andrea Esuli 和 Fabrizio Sebastiani. 2010. Sentiwordnet 3.0：一种增强的情感分析和意见挖掘词汇资源。见于 *国际语言资源与评估会议论文集，LREC 2010，2010 年 5 月 17-23 日，马耳他瓦莱塔*，欧洲语言资源协会。

+   Bakhtin 等 (2019) Bakhtin, Anton, Sam Gross, Myle Ott, Yuntian Deng, Marc’Aurelio Ranzato 和 Arthur Szlam. 2019. 真假？学习区分机器生成与人类生成的文本。*CoRR*，abs/1906.03351。

+   Bao 等 (2023) Bao, Guangsheng, Yanbin Zhao, Zhiyang Teng, Linyi Yang 和 Yue Zhang. 2023. Fast-detectgpt：通过条件概率曲率高效零样本检测机器生成文本。*arXiv 预印本 arXiv:2310.05130*，abs/2310.05130。

+   Barbara Kitchenham (2007) Barbara Kitchenham, Stuart Charters. 2007. 在软件工程中进行系统文献综述的指南。

+   Becker 等 (2023) Becker, Brett A, Paul Denny, James Finnie-Ansley, Andrew Luxton-Reilly, James Prather 和 Eddie Antonio Santos. 2023. 编程很难——或者至少曾经很难：AI 代码生成的教育机会和挑战。见于 *第 54 届 ACM 计算机科学教育技术研讨会论文集，第 1 卷*，第 500-506 页。

+   Beresneva (2016) Beresneva, Daria. 2016. 使用机器学习检测计算机生成文本：系统综述。见于 *自然语言处理与信息系统：第 21 届自然语言应用于信息系统国际会议，NLDB 2016，英国索尔福德，2016 年 6 月 22-24 日，论文集 21*，第 421-426 页，Springer。

+   Besta 等 (2023) Besta, Maciej, Nils Blach, Ales Kubicek, Robert Gerstenberger, Lukas Gianinazzi, Joanna Gajda, Tomasz Lehmann, Michal Podstawski, Hubert Niewiadomski, Piotr Nyczyk 等. 2023. 思维图谱：利用大语言模型解决复杂问题。*ArXiv 预印本*，abs/2308.09687。

+   Bhat 和 Parthasarathy (2020) Bhat, Meghana Moorthy 和 Srinivasan Parthasarathy. 2020. 机器能多有效地防御机器生成的假新闻？一项实证研究。见于 *首次 NLP 负面结果洞察研讨会论文集，Insights 2020，在线，2020 年 11 月 19 日*，第 48-53 页。

+   Bhattacharjee 等 (2023) Bhattacharjee, Amrita, Tharindu Kumarage, Raha Moraffah 和 Huan Liu. 2023. Conda: 对比领域适应用于 AI 生成文本检测。*CoRR*，abs/2309.03992。

+   Bhattacharjee 和 Liu（2023）Bhattacharjee, Amrita 和 Huan Liu。2023。以火攻火：ChatGPT 能检测 AI 生成的文本吗？*ArXiv 预印本*，abs/2308.01284。

+   Blanchard 等（2013）Blanchard, Daniel, Joel Tetreault, Derrick Higgins, Aoife Cahill, 和 Martin Chodorow。2013。Toefl11: 非母语英语语料库。*ETS 研究报告系列*，2013(2):i–15。

+   Brown 等（2020）Brown, Tom B., Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, Sandhini Agarwal, Ariel Herbert-Voss, Gretchen Krueger, Tom Henighan, Rewon Child, Aditya Ramesh, Daniel M. Ziegler, Jeffrey Wu, Clemens Winter, Christopher Hesse, Mark Chen, Eric Sigler, Mateusz Litwin, Scott Gray, Benjamin Chess, Jack Clark, Christopher Berner, Sam McCandlish, Alec Radford, Ilya Sutskever, 和 Dario Amodei。2020。语言模型是少样本学习者。在 *神经信息处理系统 33：神经信息处理系统年会 2020，NeurIPS 2020，2020 年 12 月 6-12 日，虚拟*。

+   Cardenuto 等（2023）Cardenuto, João Phillipe, Jing Yang, Rafael Padilha, Renjie Wan, Daniel Moreira, Haoliang Li, Shiqi Wang, Fernanda A. Andaló, Sébastien Marcel, 和 Anderson Rocha。2023。合成现实的时代：挑战与机遇。*CoRR*，abs/2306.11503。

+   Chaka（2023）Chaka, Chaka。2023。检测 ChatGPT、YouChat 和 ChatSonic 生成的响应中的 AI 内容：五种 AI 内容检测工具的案例。*应用学习与教学杂志*，6(2)。

+   Chakraborty 等（2023a）Chakraborty, Megha, S. M. Towhidul Islam Tonmoy, S. M. Mehedi Zaman, Shreya Gautam, Tanay Kumar, Krish Sharma, Niyar R. Barman, Chandan Gupta, Vinija Jain, Aman Chadha, Amit P. Sheth, 和 Amitava Das。2023a。反图灵测试（CT2）：AI 生成文本检测并不像你想的那么简单 - 引入 AI 可检测性指数（ADI）。在 *2023 年自然语言处理经验方法会议论文集，EMNLP 2023，新加坡，2023 年 12 月 6-10 日*，第 2206–2239 页，计算语言学协会。

+   Chakraborty 等（2023b）Chakraborty, Souradip, Amrit Singh Bedi, Sicheng Zhu, Bang An, Dinesh Manocha, 和 Furong Huang。2023b。关于 AI 生成文本检测的可能性。*CoRR*，abs/2304.04736。

+   Chen 等（2022）Chen, Qianben, Richong Zhang, Yaowei Zheng, 和 Yongyi Mao。2022。双重对比学习：通过标签感知的数据增强进行文本分类。*ArXiv 预印本*，abs/2201.08702。

+   Chen 等（2023a）Chen, Yutian, Hao Kang, Vivian Zhai, Liangze Li, Rita Singh, 和 Bhiksha Raj。2023a。将 Token 预测作为隐式分类来识别 LLM 生成的文本。在 *2023 年自然语言处理经验方法会议论文集，EMNLP 2023，新加坡，2023 年 12 月 6-10 日*，第 13112–13120 页，计算语言学协会。

+   Chen et al. (2023b) Chen, Yutian, Hao Kang, Vivian Zhai, Liangze Li, Rita Singh, and Bhiksha Ramakrishnan. 2023b. Gpt-sentinel: 区分人类和 ChatGPT 生成的内容。*ArXiv 预印本*, abs/2305.07969。

+   Chern et al. (2023) Chern, I, Steffi Chern, Shiqi Chen, Weizhe Yuan, Kehua Feng, Chunting Zhou, Junxian He, Graham Neubig, Pengfei Liu, et al. 2023. Factool: 生成式 AI 的事实检测——一个增强框架的多任务和多领域场景工具。*ArXiv 预印本*, abs/2307.13528。

+   Chowdhery et al. (2022a) Chowdhery, Aakanksha, Sharan Narang, Jacob Devlin, Maarten Bosma, Gaurav Mishra, Adam Roberts, Paul Barham, Hyung Won Chung, Charles Sutton, Sebastian Gehrmann, Parker Schuh, Kensen Shi, Sasha Tsvyashchenko, Joshua Maynez, Abhishek Rao, Parker Barnes, Yi Tay, Noam Shazeer, Vinodkumar Prabhakaran, Emily Reif, Nan Du, Ben Hutchinson, Reiner Pope, James Bradbury, Jacob Austin, Michael Isard, Guy Gur-Ari, Pengcheng Yin, Toju Duke, Anselm Levskaya, Sanjay Ghemawat, Sunipa Dev, Henryk Michalewski, Xavier Garcia, Vedant Misra, Kevin Robinson, Liam Fedus, Denny Zhou, Daphne Ippolito, David Luan, Hyeontaek Lim, Barret Zoph, Alexander Spiridonov, Ryan Sepassi, David Dohan, Shivani Agrawal, Mark Omernick, Andrew M. Dai, Thanumalayan Sankaranarayana Pillai, Marie Pellat, Aitor Lewkowycz, Erica Moreira, Rewon Child, Oleksandr Polozov, Katherine Lee, Zongwei Zhou, Xuezhi Wang, Brennan Saeta, Mark Diaz, Orhan Firat, Michele Catasta, Jason Wei, Kathy Meier-Hellstern, Douglas Eck, Jeff Dean, Slav Petrov, and Noah Fiedel. 2022a. Palm: 通过路径扩展语言建模。*CoRR*, abs/2204.02311。

+   Chowdhery et al. (2022b) Chowdhery, Aakanksha, Sharan Narang, Jacob Devlin, Maarten Bosma, Gaurav Mishra, Adam Roberts, Paul Barham, Hyung Won Chung, Charles Sutton, Sebastian Gehrmann, et al. 2022b. Palm: 通过路径扩展语言建模。*ArXiv 预印本*, abs/2204.02311。

+   Christian (2023) Christian, Jon. 2023. Cnet 秘密使用 AI 处理未披露该事实的文章，员工称。*Futurusm, January*。

+   Clark et al. (2021a) Clark, Elizabeth, Tal August, Sofia Serrano, Nikita Haduong, Suchin Gururangan, and Noah A. Smith. 2021a. 所有‘人类’的东西并非金光闪闪：评估生成文本的人类评价。在 *第 59 届计算语言学协会年会暨第 11 届国际自然语言处理联合会议 (第 1 卷: 长篇论文)*, 页码 7282–7296, 计算语言学协会。

+   Clark 等人（2021b）Clark, Elizabeth, Tal August, Sofia Serrano, Nikita Haduong, Suchin Gururangan, 和 Noah A. Smith. 2021b. 所有“人类”的东西并非都是金子：评估生成文本的人工评估。发表于 *第 59 届计算语言学协会年会暨第 11 届国际自然语言处理联合会议，ACL/IJCNLP 2021，（第 1 卷：长篇论文），虚拟会议，2021 年 8 月 1-6 日*，页码 7282–7296，计算语言学协会。

+   Conneau 等人（2020）Conneau, Alexis, Kartikay Khandelwal, Naman Goyal, Vishrav Chaudhary, Guillaume Wenzek, Francisco Guzmán, Edouard Grave, Myle Ott, Luke Zettlemoyer, 和 Veselin Stoyanov. 2020. 大规模无监督跨语言表示学习。发表于 *第 58 届计算语言学协会年会，ACL 2020，在线会议，2020 年 7 月 5-10 日*，页码 8440–8451，计算语言学协会。

+   Corizzo 和 Leal-Arenas（2023）Corizzo, Roberto 和 Sebastian Leal-Arenas. 2023. 用于人类 $vs$. 机器生成论文分类的深度融合模型。发表于 *国际神经网络联合会议，IJCNN 2023，澳大利亚黄金海岸，2023 年 6 月 18-23 日*，页码 1–10，IEEE。

+   Corston-Oliver, Gamon, 和 Brockett（2001）Corston-Oliver, Simon, Michael Gamon, 和 Chris Brockett. 2001. 自动评估机器翻译的机器学习方法。发表于 *第 39 届计算语言学协会年会*，页码 148–155，计算语言学协会。

+   Cowap, Graham, 和 Foster（2023）Cowap, Alan, Yvette Graham, 和 Jennifer Foster. 2023. 随机鹦鹉也有情感吗？通过情感识别改善神经网络对合成文本的检测。发表于 *计算语言学协会发现：EMNLP 2023，新加坡，2023 年 12 月 6-10 日*，页码 9928–9946，计算语言学协会。

+   Crothers, Japkowicz, 和 Viktor（2023a）Crothers, Evan, Nathalie Japkowicz, 和 Herna L Viktor. 2023a. 机器生成文本：威胁模型和检测方法的全面综述。*IEEE Access*。

+   Crothers, Japkowicz, 和 Viktor（2023b）Crothers, Evan, Nathalie Japkowicz, 和 Herna L. Viktor. 2023b. 机器生成文本：威胁模型和检测方法的全面综述。*IEEE Access*, 11:70977–71002。

+   Crothers 等人（2022）Crothers, Evan, Nathalie Japkowicz, Herna L. Viktor, 和 Paula Branco. 2022. 生成变换器中神经统计特征的对抗鲁棒性。发表于 *国际神经网络联合会议，IJCNN 2022，意大利帕多瓦，2022 年 7 月 18-23 日*，页码 1–8，IEEE。

+   Cui 等人（2023）Cui, Jiaxi, Zongjian Li, Yang Yan, Bohua Chen, 和 Li Yuan. 2023. Chatlaw：集成外部知识库的开源法律大语言模型。*ArXiv 预印本*, abs/2306.16092。

+   Dai et al. (2023) Dai, Damai, Yutao Sun, Li Dong, Yaru Hao, Shuming Ma, Zhifang Sui, 和 Furu Wei. 2023. 为什么 GPT 可以在上下文中学习？语言模型隐式地执行梯度下降作为元优化器。在*ICLR 2023 数学与经验理解基础模型研讨会*中。

+   Damodaran (2021) Damodaran, Prithiviraj. 2021. Parrot：用于自然语言理解的同义句生成。

+   Deng et al. (2023) Deng, Zhijie, Hongcheng Gao, Yibo Miao, 和 Hao Zhang. 2023. 使用贝叶斯替代模型高效检测 LLM 生成的文本。*ArXiv 预印本*，abs/2305.16617。

+   Desaire et al. (2023) Desaire, Heather, Aleesa E. Chua, Madeline Isom, Romana Jarosova, 和 David Hua. 2023. ChatGPT 还是学术科学家？使用现成的机器学习工具以 99%以上的准确率区分作者身份。*CoRR*，abs/2303.16352。

+   Devlin et al. (2019a) Devlin, Jacob, Ming-Wei Chang, Kenton Lee, 和 Kristina Toutanova. 2019a. BERT：用于语言理解的深度双向变换器的预训练。在*2019 年北美计算语言学协会年会：人类语言技术，NAACL-HLT 2019，明尼阿波利斯，MN，美国，2019 年 6 月 2-7 日，第一卷（长篇和短篇论文）*中，第 4171–4186 页，计算语言学协会。

+   Devlin et al. (2019b) Devlin, Jacob, Ming-Wei Chang, Kenton Lee, 和 Kristina Toutanova. 2019b. BERT：用于语言理解的深度双向变换器的预训练。在*2019 年北美计算语言学协会年会：人类语言技术，NAACL-HLT 2019，明尼阿波利斯，MN，美国，2019 年 6 月 2-7 日，第一卷（长篇和短篇论文）*中，第 4171–4186 页，计算语言学协会。

+   Devlin et al. (2019c) Devlin, Jacob, Ming-Wei Chang, Kenton Lee, 和 Kristina Toutanova. 2019c. BERT：用于语言理解的深度双向变换器的预训练。在*2019 年北美计算语言学协会年会：人类语言技术，第一卷（长篇和短篇论文）*中，第 4171–4186 页，计算语言学协会。

+   Dhaini, Poelman, 和 Erdogan (2023) Dhaini, Mahdi, Wessel Poelman, 和 Ege Erdogan. 2023. 检测 ChatGPT：ChatGPT 生成文本检测现状的调查。*CoRR*，abs/2309.07689。

+   Dong et al. (2023) Dong, Qingxiu, Lei Li, Damai Dai, Ce Zheng, Zhiyong Wu, Baobao Chang, Xu Sun, Jingjing Xu, 和 Zhifang Sui. 2023. 上下文学习的调查。*ArXiv 预印本*，abs/2301.00234。

+   Dou et al. (2022) Dou, Yao, Maxwell Forbes, Rik Koncel-Kedziorski, Noah A. Smith, 和 Yejin Choi. 2022. GPT-3 文本是否与人类文本不可区分？scarecrow：一个用于审查机器文本的框架。在*第 60 届计算语言学协会年会（第一卷：长篇论文）*中，第 7250–7274 页，计算语言学协会。

+   Dugan 等人（2020）Dugan, Liam, Daphne Ippolito, Arun Kirubarajan, 和 Chris Callison-Burch. 2020. RoFT：用于评估人类检测机器生成文本的工具。在*2020 年自然语言处理经验方法会议：系统演示论文集*，第 189–196 页，计算语言学协会。

+   Dugan 等人（2023）Dugan, Liam, Daphne Ippolito, Arun Kirubarajan, Sherry Shi, 和 Chris Callison-Burch. 2023. 真还是假文本？：研究人类识别人工写作和机器生成文本边界的能力。在*第 37 届 AAAI 人工智能会议，AAAI 2023，第 35 届创新应用人工智能会议，IAAI 2023，第 13 届教育进展人工智能研讨会，EAAI 2023，华盛顿特区，美国，2023 年 2 月 7-14 日*，第 12763–12771 页，AAAI Press。

+   Epstein 等人（2023）Epstein, Ziv, Aaron Hertzmann, 人类创造力调查员, Memo Akten, Hany Farid, Jessica Fjeld, Morgan R Frank, Matthew Groh, Laura Herman, Neil Leach, 等人. 2023. 艺术与生成性 AI 的科学。*科学*，380(6650):1110–1111。

+   Fagni 等人（2021）Fagni, Tiziano, Fabrizio Falchi, Margherita Gambini, Antonio Martella, 和 Maurizio Tesconi. 2021. TweepFake: 关于检测深伪推文。*PLOS ONE*，16(5):e0251415。

+   Fan 等人（2019）Fan, Angela, Yacine Jernite, Ethan Perez, David Grangier, Jason Weston, 和 Michael Auli. 2019. ELI5: 长文问答。在*第 57 届计算语言学协会年会论文集*，第 3558–3567 页，计算语言学协会。

+   Fan, Lewis 和 Dauphin（2018）Fan, Angela, Mike Lewis, 和 Yann Dauphin. 2018. 层次化神经故事生成。在*第 56 届计算语言学协会年会（第 1 卷：长篇论文）论文集*，第 889–898 页，计算语言学协会。

+   Fellbaum（1998）Fellbaum, Christiane. 1998. *WordNet: 电子词汇数据库*。MIT 出版社。

+   Gade 等人（2020）Gade, Krishna, Sahin Geyik, Krishnaram Kenthapadi, Varun Mithal, 和 Ankur Taly. 2020. 行业中的可解释 AI：实际挑战与经验教训。在*2020 年网络会议伴随论文集*，第 303–304 页。

+   Gallé 等人（2021）Gallé, Matthias, Jos Rozen, Germán Kruszewski, 和 Hady Elsahar. 2021. 无监督和分布式检测机器生成文本。*CoRR*，abs/2111.02878。

+   Gambini 等人（2022）Gambini, Margherita, Tiziano Fagni, Fabrizio Falchi, 和 Maurizio Tesconi. 2022. 推动深伪推文检测能力到极限。在*第 14 届 ACM Web 科学会议 2022 论文集*，第 154–163 页。

+   Gao 等人（2018a）Gao, Ji, Jack Lanchantin, Mary Lou Soffa, 和 Yanjun Qi. 2018a. 黑箱生成对抗文本序列以规避深度学习分类器。在*2018 IEEE 安全与隐私研讨会（SPW）*，第 50–56 页，IEEE。

+   Gao et al. (2018b) Gao, Ji, Jack Lanchantin, Mary Lou Soffa, 和 Yanjun Qi. 2018b. 黑箱生成对抗文本序列以规避深度学习分类器. 在 *2018 IEEE 安全与隐私研讨会, SP 研讨会 2018, 美国加州旧金山, 2018 年 5 月 24 日* 中，页面 50–56.

+   Gao et al. (2023) Gao, Luyu, Zhuyun Dai, Panupong Pasupat, Anthony Chen, Arun Tejasvi Chaganty, Yicheng Fan, Vincent Zhao, Ni Lao, Hongrae Lee, Da-Cheng Juan, 等. 2023. Rarr: 使用语言模型研究和修订语言模型的输出. 在 *第 61 届计算语言学协会年会（第 1 卷：长篇论文）* 中，页面 16477–16508.

+   Gao, Yao, 和 Chen (2021) Gao, Tianyu, Xingcheng Yao, 和 Danqi Chen. 2021. SimCSE: 简单对比学习句子嵌入. 在 *2021 年自然语言处理实证方法会议论文集* 中，页面 6894–6910，计算语言学协会.

+   Gehrmann, Strobelt, 和 Rush (2019) Gehrmann, Sebastian, Hendrik Strobelt, 和 Alexander Rush. 2019. GLTR: 生成文本的统计检测和可视化. 在 *第 57 届计算语言学协会年会: 系统演示* 中，页面 111–116，计算语言学协会.

+   Ghosal et al. (2023) Ghosal, Soumya Suvra, Souradip Chakraborty, Jonas Geiping, Furong Huang, Dinesh Manocha, 和 Amrit Bedi. 2023. 关于 AI 生成文本检测的可能性与不可能性的调查. *机器学习研究交易*.

+   Giorgi et al. (2023) Giorgi, Salvatore, David M. Markowitz, Nikita Soni, Vasudha Varadarajan, Siddharth Mangalik, 和 H. Andrew Schwartz. 2023. “我睡得像个宝宝”: 使用人类特征表征虚假的 ChatGPT 和人类文本. 在 *IACT - 第 1 届国际隐式作者特征化研讨会，与第 46 届国际 ACM SIGIR 信息检索研究与发展会议（SIGIR 2023）联合举办, 台湾台北, 2023 年 7 月 27 日* 中，*CEUR 工作论文集* 第 3477 卷，页面 23–37，CEUR-WS.org.

+   Giorgi, Ungar, 和 Schwartz (2021) Giorgi, Salvatore, Lyle Ungar, 和 H. Andrew Schwartz. 2021. 通过人类特征表征社交垃圾信息机器人. 在 *计算语言学协会发现: ACL-IJCNLP 2021* 中，页面 5148–5158，计算语言学协会.

+   Goodfellow et al. (2020) Goodfellow, Ian, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, 和 Yoshua Bengio. 2020. 生成对抗网络. *ACM 通讯*, 63(11):139–144.

+   Graves (2012) Graves, Alex. 2012. 使用递归神经网络进行序列转换. *arXiv 预印本 arXiv:1211.3711*.

+   Gu 等（2022）Gu, Chenxi, Chengsong Huang, Xiaoqing Zheng, Kai-Wei Chang 和 Cho-Jui Hsieh. 2022. 使用后门技术对预训练语言模型进行水印标记。*ArXiv 预印本*，abs/2210.07543。

+   Guo 等（2023）Guo, Biyang, Xin Zhang, Ziyuan Wang, Minqi Jiang, Jinran Nie, Yuxuan Ding, Jianwei Yue 和 Yupeng Wu. 2023. ChatGPT 与人类专家的距离有多近？比较语料库、评估和检测。*ArXiv 预印本*，abs/2301.07597。

+   Guo 等（2020）Guo, Mandy, Zihang Dai, Denny Vrandečić和 Rami Al-Rfou. 2020. Wiki-40B：多语言语言模型数据集。发表于*第十二届语言资源与评估会议论文集*，第 2440–2452 页，欧洲语言资源协会。

+   Guo 和 Yu（2023）Guo, Zhen 和 Shangdi Yu. 2023. Authentigpt：通过黑箱语言模型去噪检测机器生成文本。*CoRR*，abs/2311.07700。

+   Hamed 和 Wu（2023）Hamed, Ahmed Abdeen 和 Xindong Wu. 2023. 使用真实出版文本提高对 ChatGPT 生成虚假科学的检测：介绍 xfakebibs，一个监督学习网络算法。*CoRR*，abs/2308.11767。

+   Hanley 和 Durumeric（2023）Hanley, Hans W. A.和 Zakir Durumeric. 2023. 机器生成媒体：监控机器生成文章在虚假信息和主流新闻网站上的传播。*CoRR*，abs/2305.09820。

+   He 等（2023）He, Xinlei, Xinyue Shen, Zeyuan Chen, Michael Backes 和 Yang Zhang. 2023. Mgtbench：机器生成文本检测基准。*ArXiv 预印本*，abs/2303.14822。

+   Helm, Priebe 和 Yang（2023）Helm, Hayden S., Carey E. Priebe 和 Weiwei Yang. 2023. 一种用于生成模型的统计图灵测试。*CoRR*，abs/2309.08913。

+   Henrique, Kucharavy 和 Guerraoui（2023）Henrique, Da Silva Gameiro, Andrei Kucharavy 和 Rachid Guerraoui. 2023. 随机鹦鹉寻找随机鹦鹉：LLMs 容易微调且难以与其他 LLMs 检测。*CoRR*，abs/2304.08968。

+   Hill 等（2016）Hill, Felix, Antoine Bordes, Sumit Chopra 和 Jason Weston. 2016. Goldilocks 原则：阅读具有明确记忆表征的儿童书籍。发表于*第四届国际学习表征会议，ICLR 2016，波多黎各圣胡安，2016 年 5 月 2-4 日，会议跟踪论文集*。

+   Holtzman 等（2020）Holtzman, Ari, Jan Buys, Li Du, Maxwell Forbes 和 Yejin Choi. 2020. 神经文本退化的奇怪案例。发表于*第八届国际学习表征会议，ICLR 2020，埃提俄比亚亚的斯亚贝巴，2020 年 4 月 26-30 日*，OpenReview.net。

+   Horne 和 Adali（2017）Horne, Benjamin 和 Sibel Adali. 2017. 最新消息：虚假新闻在标题中包含大量信息，正文中使用更简单、重复的内容，更类似于讽刺而非真实新闻。发表于*国际 AAAI 网络与社交媒体会议论文集*，第 11 卷，第 759–766 页。

+   Hou 等（2023）Hou, Abe Bohan, Jingyu Zhang, Tianxing He, Yichen Wang, Yung-Sung Chuang, Hongwei Wang, Lingfeng Shen, Benjamin Van Durme, Daniel Khashabi 和 Yulia Tsvetkov. 2023. Semstamp：一种具有释义鲁棒性的语义水印用于文本生成。*CoRR*，abs/2310.03991。

+   Hu, Chen 和 Ho（2023）Hu, Xiaomeng, Pin-Yu Chen 和 Tsung-Yi Ho. 2023. Radar：通过对抗学习进行鲁棒的 AI 文本检测。*ArXiv 预印本*，abs/2307.03838。

+   Ibrahim 等（2023）Ibrahim, Hazem, Fengyuan Liu, Rohail Asim, Balaraju Battu, Sidahmed Benabderrahmane, Bashar Alhafni, Wifag Adnan, Tuka Alhanai, Bedoor K. AlShebli, Riyadh Baghdadi, Jocelyn J. Bélanger, Elena Beretta, Kemal Celik, Moumena Chaqfeh, Mohammed F. Daqaq, Zaynab El Bernoussi, Daryl Fougnie, Borja Garcia de Soto, Alberto Gandolfi, András György, Nizar Habash, J. Andrew Harris, Aaron Kaufman, Lefteris Kirousis, Korhan Kocak, Kangsan Lee, Seungah S. Lee, Samreen Malik, Michail Maniatakos, David Melcher, Azzam Mourad, Minsu Park, Mahmoud Rasras, Alicja Reuben, Dania Zantout, Nancy W. Gleason, Kinga Makovi, Talal Rahwan 和 Yasir Zaki. 2023. 对话式人工智能在 32 个大学课程中的感知、表现和可检测性。*CoRR*，abs/2305.13934。

+   Ippolito 等（2020）Ippolito, Daphne, Daniel Duckworth, Chris Callison-Burch 和 Douglas Eck. 2020. 当人类被欺骗时，自动检测生成文本最容易。发表于*第 58 届计算语言学协会年会论文集*，第 1808–1822 页，计算语言学协会。

+   Jawahar, Abdul-Mageed 和 Lakshmanan（2020）Jawahar, Ganesh, Muhammad Abdul-Mageed 和 Laks Lakshmanan, V.S. 2020. 自动检测机器生成文本：一个关键性调查。发表于*第 28 届国际计算语言学会议论文集*，第 2296–2309 页，国际计算语言学委员会。

+   Ji 等（2023）Ji, Ziwei, Nayeon Lee, Rita Frieske, Tiezheng Yu, Dan Su, Yan Xu, Etsuko Ishii, Ye Jin Bang, Andrea Madotto 和 Pascale Fung. 2023. 自然语言生成中的幻觉调查。*ACM 计算调查*，55(12):1–38。

+   Jiao 等（2020）Jiao, Xiaoqi, Yichun Yin, Lifeng Shang, Xin Jiang, Xiao Chen, Linlin Li, Fang Wang 和 Qun Liu. 2020. Tinybert：为自然语言理解提取 BERT。发表于*计算语言学协会会议成果：EMNLP 2020，在线活动，2020 年 11 月 16-20 日*，*ACL 会议成果*的 EMNLP 2020 卷，第 4163–4174 页，计算语言学协会。

+   Jin 等（2019）Jin, Qiao, Bhuwan Dhingra, Zhengping Liu, William Cohen 和 Xinghua Lu. 2019. PubMedQA：一个用于生物医学研究问答的数据集。发表于*2019 年自然语言处理实证方法会议及第 9 届国际联合自然语言处理会议（EMNLP-IJCNLP）论文集*，第 2567–2577 页，计算语言学协会。

+   Jin et al. (2021) Jin, Zhuoran, Yubo Chen, Dianbo Sui, Chenhao Wang, Zhipeng Xue, 和 Jun Zhao. 2021. Cogie：一个用于连接文本和 Cognet 的信息提取工具包。收录于*第 59 届年度计算语言学协会年会和第 11 届国际自然语言处理联合会议联合会议论文集，ACL 2021 - 系统演示，在线，2021 年 8 月 1-6 日*，第 92–98 页，计算语言学协会。

+   Kalinichenko et al. (2003) Kalinichenko, Leonid A, Vladimir V Korenkov, Vladislav P Shirikov, Alexey N Sissakian, 和 Oleg V Sunturenko. 2003. 数字图书馆：先进的方法和技术，数字收藏。*D-Lib Magazine*, 9(1):1082–9873。

+   Kang et al. (2018) Kang, Dongyeop, Waleed Ammar, Bhavana Dalvi, Madeleine van Zuylen, Sebastian Kohlmeier, Eduard Hovy, 和 Roy Schwartz. 2018. 同行评审数据集（PeerRead）：收集、洞察与 NLP 应用。在*2018 年北美计算语言学协会年会：人类语言技术会议论文集第 1 卷（长论文）*，第 1647–1661 页，计算语言学协会。

+   Kasneci et al. (2023) Kasneci, Enkelejda, Kathrin Seßler, Stefan Küchemann, Maria Bannert, Daryna Dementieva, Frank Fischer, Urs Gasser, Georg Groh, Stephan Günnemann, Eyke Hüllermeier, 等. 2023. Chatgpt 为善？关于大型语言模型在教育中的机遇与挑战。*Learning and Individual Differences*, 103:102274。

+   Kirchenbauer et al. (2023a) Kirchenbauer, John, Jonas Geiping, Yuxin Wen, Jonathan Katz, Ian Miers, 和 Tom Goldstein. 2023a. 大型语言模型的水印。收录于*国际机器学习会议，ICML 2023，2023 年 7 月 23-29 日，夏威夷檀香山，美国*，*机器学习研究会议录*第 202 卷，第 17061–17084 页，PMLR。

+   Kirchenbauer et al. (2023b) Kirchenbauer, John, Jonas Geiping, Yuxin Wen, Manli Shu, Khalid Saifullah, Kezhi Kong, Kasun Fernando, Aniruddha Saha, Micah Goldblum, 和 Tom Goldstein. 2023b. 关于大型语言模型水印的可靠性。*CoRR*, abs/2306.04634。

+   Kočiský et al. (2018) Kočiský, Tomáš, Jonathan Schwarz, Phil Blunsom, Chris Dyer, Karl Moritz Hermann, Gábor Melis, 和 Edward Grefenstette. 2018. NarrativeQA 阅读理解挑战。*Transactions of the Association for Computational Linguistics*, 6:317–328。

+   Koike, Ryuto, Masahiro Kaneko, 和 Naoaki Okazaki (2023a) Koike, Ryuto, Masahiro Kaneko, 和 Naoaki Okazaki. 2023a. 你的提示方式很重要！即使是任务导向的指令约束也会影响 llm 生成文本的检测。*CoRR*, abs/2311.08369。

+   Koike, Ryuto, Masahiro Kaneko, 和 Naoaki Okazaki (2023b) Koike, Ryuto, Masahiro Kaneko, 和 Naoaki Okazaki. 2023b. Outfox：通过具有对抗性生成示例的上下文学习检测 llm 生成的论文。*ArXiv 预印本*, abs/2307.11729。

+   Kojima et al. (2022) Kojima, Takeshi, Shixiang Shane Gu, Machel Reid, Yutaka Matsuo, 和 Yusuke Iwasawa. 2022. 大型语言模型是零-shot 推理器。收录于*NeurIPS*。

+   Krishna et al. (2023) Krishna, Kalpesh, Yixiao Song, Marzena Karpinska, John Wieting, 和 Mohit Iyyer. 2023. 释义避开了 AI 生成文本的检测器，但检索是一种有效的防御。*ArXiv preprint*，abs/2303.13408。

+   Kuditipudi et al. (2023) Kuditipudi, Rohith, John Thickstun, Tatsunori Hashimoto, 和 Percy Liang. 2023. 语言模型的鲁棒抗失真水印。*CoRR*，abs/2307.15593。

+   Kulkarni et al. (2023) Kulkarni, Pranav, Ziqing Ji, Yan Xu, Marko Neskovic, 和 Kevin Nolan. 2023. 探索 Grover 上的语义扰动。*CoRR*，abs/2302.00509。

+   Kumarage et al. (2023a) Kumarage, Tharindu, Amrita Bhattacharjee, Djordje Padejski, Kristy Roschke, Dan Gillmor, Scott W. Ruston, Huan Liu, 和 Joshua Garland. 2023a. J-guard：新闻生成检测的对抗性鲁棒性引导。*CoRR*，abs/2309.03164。

+   Kumarage et al. (2023b) Kumarage, Tharindu, Paras Sheth, Raha Moraffah, Joshua Garland, 和 Huan Liu. 2023b. AI 生成文本检测器的可靠性如何？使用规避性软提示的评估框架。收录于*2023 年计算语言学协会年会：EMNLP 2023，新加坡，2023 年 12 月 6-10 日*，第 1337–1349 页，计算语言学协会。

+   Lambert et al. (2022) Lambert, Nathan, Louis Castricato, Leandro von Werra, 和 Alex Havrilla. 2022. 说明从人类反馈中学习的强化学习（RLHF）。*Hugging Face Blog*。Https://huggingface.co/blog/rlhf。

+   Lavergne, Urvoy, 和 Yvon (2008) Lavergne, Thomas, Tanguy Urvoy, 和 François Yvon. 2008. 使用相对熵评分检测虚假内容。收录于*2008 年国际揭露剽窃、作者身份和社会软件滥用会议论文集-第 377 卷*，第 27–31 页。

+   Lee, Jang, 和 Lee (2021) Lee, Bruce W., Yoo Sung Jang, 和 Jason Hyung-Jong Lee. 2021. 推进文本可读性评估：变换器遇上手工制作的语言特征。收录于*2021 年自然语言处理实证方法会议，EMNLP 2021，虚拟会议/多米尼加共和国蓬塔卡纳，2021 年 11 月 7-11 日*，第 10669–10686 页，计算语言学协会。

+   Lee et al. (2020) Lee, Haejun, Drew A. Hudson, Kangwook Lee, 和 Christopher D. Manning. 2020. SLM：通过句子重排学习话语语言表示。收录于*2020 年自然语言处理实证方法会议（EMNLP）论文集*，第 1551–1562 页，计算语言学协会。

+   Lee et al. (2023a) Lee, Jooyoung, Thai Le, Jinghui Chen, 和 Dongwon Lee. 2023a. 语言模型会剽窃吗？收录于*2023 年 ACM 网络会议论文集*，第 3637–3647 页。

+   Lee 等人 (2023b) Lee, Taehyun, Seokhee Hong, Jaewoo Ahn, Ilgee Hong, Hwaran Lee, Sangdoo Yun, Jamin Shin, 和 Gunhee Kim. 2023b. 谁写了这段代码？代码生成的水印。*CoRR*, abs/2305.15060。

+   Li 等人 (2023a) Li, Linyang, Pengyu Wang, Ke Ren, Tianxiang Sun, 和 Xipeng Qiu. 2023a. 大型语言模型的来源追踪与检测。*CoRR*, abs/2304.14072。

+   Li 等人 (2023b) Li, Xian, Ping Yu, Chunting Zhou, Timo Schick, Luke Zettlemoyer, Omer Levy, Jason Weston, 和 Mike Lewis. 2023b. 通过指令回译进行自我对齐。*ArXiv preprint*, abs/2308.06259。

+   Li 等人 (2023c) Li, Yafu, Qintong Li, Leyang Cui, Wei Bi, Longyue Wang, Linyi Yang, Shuming Shi, 和 Yue Zhang. 2023c. 深度伪造文本检测。*CoRR*, abs/2305.13242。

+   Liang, Guerrero 和 Alsmadi (2023) Liang, Gongbo, Jesus Guerrero, 和 Izzat Alsmadi. 2023. 基于突变的对抗攻击神经文本检测器。*ArXiv preprint*, abs/2302.05794。

+   Liang 等人 (2023a) Liang, Weixin, Mert Yuksekgonul, Yining Mao, Eric Wu, 和 James Zou. 2023a. GPT 检测器对非母语英语写作者存在偏见。发表于 *ICLR 2023 Workshop on Trustworthy and Reliable Large-Scale Machine Learning Models*。

+   Liang 等人 (2023b) Liang, Yaobo, Chenfei Wu, Ting Song, Wenshan Wu, Yan Xia, Yu Liu, Yang Ou, Shuai Lu, Lei Ji, Shaoguang Mao, 等人. 2023b. Taskmatrix.ai: 通过将基础模型与数百万个 API 连接来完成任务。*ArXiv preprint*, abs/2303.16434。

+   Liao 等人 (2023a) Liao, Wenxiong, Zhengliang Liu, Haixing Dai, Shaochen Xu, Zihao Wu, Yiyang Zhang, Xiaoke Huang, Dajiang Zhu, Hongmin Cai, Tianming Liu, 和 Xiang Li. 2023a. 区分 ChatGPT 生成和人工编写的医学文本。*CoRR*, abs/2304.11567。

+   Liao 等人 (2023b) Liao, Wenxiong, Zhengliang Liu, Haixing Dai, Shaochen Xu, Zihao Wu, Yiyang Zhang, Xiaoke Huang, Dajiang Zhu, Hongmin Cai, Tianming Liu, 等人. 2023b. 区分 ChatGPT 生成和人工编写的医学文本。*ArXiv preprint*, abs/2304.11567。

+   Lin, Hilton 和 Evans (2022) Lin, Stephanie, Jacob Hilton, 和 Owain Evans. 2022. TruthfulQA: 衡量模型如何模仿人类虚假陈述。发表于 *Proceedings of the 60th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)*, 页码 3214–3252, 计算语言学协会。

+   Littman 和 Wrubel (2019) Littman, Justin 和 Laura Wrubel. 2019. 气候变化推文 ID。

+   Liu 等人 (2023a) Liu, Aiwei, Leyi Pan, Xuming Hu, Shu’ang Li, Lijie Wen, Irwin King, 和 Philip S Yu. 2023a. 针对大型语言模型的私有水印。*ArXiv preprint*, abs/2307.16230。

+   Liu 等人 (2023b) Liu, Aiwei, Leyi Pan, Xuming Hu, Shiao Meng, 和 Lijie Wen. 2023b. 一种针对大型语言模型的语义不变鲁棒水印。*CoRR*, abs/2310.06356。

+   Liu 等人 (2022) Liu, Xiaoming, Zhaohan Zhang, Yichen Wang, Yu Lan, 和 Chao Shen. 2022. Coco: 在数据限制下通过对比学习增强的机器生成文本检测。*ArXiv preprint*, abs/2212.10341。

+   Liu 等（2023c）Liu, Yikang, Ziyin Zhang, Wanyang Zhang, Shisen Yue, Xiaojing Zhao, Xinyuan Cheng, Yiwen Zhang, 和 Hai Hu. 2023c. Argugpt：评估、理解和识别由 GPT 模型生成的论证性文章。*ArXiv 预印本*，abs/2304.07666。

+   Liu 等（2019）Liu, Yinhan, Myle Ott, Naman Goyal, Jingfei Du, Mandar Joshi, Danqi Chen, Omer Levy, Mike Lewis, Luke Zettlemoyer, 和 Veselin Stoyanov. 2019. Roberta：一种稳健优化的 BERT 预训练方法。*CoRR*，abs/1907.11692。

+   Liu 等（2023d）Liu, Zeyan, Zijun Yao, Fengjun Li, 和 Bo Luo. 2023d. 如果你能的话，检查我：使用 CheckGPT 检测 ChatGPT 生成的学术写作。*ArXiv 预印本*，abs/2306.05524。

+   Lu 等（2023）Lu, Ning, Shengcai Liu, Rui He, 和 Ke Tang. 2023. 大型语言模型可以被引导以规避 AI 生成文本检测。*ArXiv 预印本*，abs/2305.10847。

+   Lu 等（2022）Lu, Yaojie, Qing Liu, Dai Dai, Xinyan Xiao, Hongyu Lin, Xianpei Han, Le Sun, 和 Hua Wu. 2022. 面向通用信息提取的统一结构生成。发表于*第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文），ACL 2022，都柏林，爱尔兰，2022 年 5 月 22-27 日*，页码 5755–5772，计算语言学协会。

+   Lucas 和 Havens（2023）Lucas, Evan 和 Timothy Havens. 2023. GPTs 不保守秘密：在自回归语言模型中寻找后门水印触发器。发表于*第 3 届值得信赖的自然语言处理研讨会（TrustNLP 2023）*，页码 242–248。

+   Ma, Liu, 和 Yi（2023）Ma, Yongqiang, Jiawei Liu, 和 Fan Yi. 2023. 这个摘要是由 AI 生成的吗？关于 AI 生成的科学文本与人工撰写科学文本之间差距的研究。*ArXiv 预印本*，abs/2301.10416。

+   Ma 等（2023）Ma, Yongqiang, Jiawei Liu, Fan Yi, Qikai Cheng, Yong Huang, Wei Lu, 和 Xiaozhong Liu. 2023. AI 与人类——科学内容生成的差异分析。*arXiv*，2301。

+   Macko 等（2023）Macko, Dominik, Róbert Móro, Adaku Uchendu, Jason Samuel Lucas, Michiharu Yamashita, Matús Pikuliak, Ivan Srba, Thai Le, Dongwon Lee, Jakub Simko, 和 Mária Bieliková. 2023. Multitude：大规模多语言机器生成文本检测基准。发表于*2023 年自然语言处理实证方法会议，EMNLP 2023，新加坡，2023 年 12 月 6-10 日*，页码 9960–9987。

+   Májovskỳ 等（2023）Májovskỳ, Martin, Martin Černỳ, Matěj Kasal, Martin Komarc, 和 David Netuka. 2023. 人工智能可以生成伪造但看起来真实的科学医学文章：潘多拉的盒子已经被打开。*医学互联网研究杂志*，25:e46924。

+   Mao 等（2024）Mao, Chengzhi, Carl Vondrick, Hao Wang, 和 Junfeng Yang. 2024. Raidar：通过重写进行生成 AI 检测。*CoRR*，abs/2401.12970。

+   Markowitz, Hancock, 和 Bailenson (2023) Markowitz, David M, Jeffrey Hancock, 和 Jeremy Bailenson. 2023. 内在 AI 欺骗和有意人类欺骗的语言标记：来自酒店评论的证据。*PsyArXiv preprint*。

+   McCarthy (2005) McCarthy, Philip M. 2005. *词汇多样性测量范围和实用性的评估以及文本词汇多样性测量 (MTLD) 的潜力*。博士论文，孟菲斯大学。

+   Mindner, Schlippe, 和 Schaaff (2023) Mindner, Lorenz, Tim Schlippe, 和 Kristina Schaaff. 2023. 人类与 AI 生成文本的分类：调查 Chatgpt 的特征。*CoRR*，abs/2308.05341。

+   Mirsky 等 (2022) Mirsky, Yisroel, Ambra Demontis, Jaidip Kotak, Ram Shankar, Deng Gelei, Liu Yang, Xiangyu Zhang, Maura Pintor, Wenke Lee, Yuval Elovici, 等. 2022. 攻击性 AI 对组织的威胁。*Computers & Security*，第 103006 页。

+   Mitchell 等 (2023) Mitchell, Eric, Yoonho Lee, Alexander Khazatsky, Christopher D. Manning, 和 Chelsea Finn. 2023. Detectgpt：使用概率曲率进行零样本机器生成文本检测。在 *International Conference on Machine Learning, ICML 2023, 2023 年 7 月 23-29 日, 夏威夷檀香山, 美国*，*Proceedings of Machine Learning Research* 第 202 卷，第 24950–24962 页，PMLR。

+   Mitrovic, Andreoletti, 和 Ayoub (2023) Mitrovic, Sandra, Davide Andreoletti, 和 Omran Ayoub. 2023. Chatgpt 还是人类？检测与解释。解释机器学习模型用于检测短文本的决策。*CoRR*，abs/2301.13852。

+   Mitrović, Andreoletti, 和 Ayoub (2023) Mitrović, Sandra, Davide Andreoletti, 和 Omran Ayoub. 2023. Chatgpt 还是人类？检测与解释。解释机器学习模型用于检测短文本的决策。*ArXiv preprint*，abs/2301.13852。

+   Moosavi 等 (2021) Moosavi, Nafise Sadat, Andreas Rücklé, Dan Roth, 和 Iryna Gurevych. 2021. Scigen：一个用于从科学表格生成推理意识文本的数据集。在 *第三十五届神经信息处理系统会议数据集与基准测试分会 (Round 2)*。

+   Morris 等 (2020) Morris, John X., Eli Lifland, Jin Yong Yoo, Jake Grigsby, Di Jin, 和 Yanjun Qi. 2020. Textattack：一个用于对抗攻击、数据增强和对抗训练的 NLP 框架。在 *Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing: System Demonstrations, EMNLP 2020 - Demos, Online, 2020 年 11 月 16-20 日*，第 119–126 页。

+   Mosca 等 (2023) Mosca, Edoardo, Mohamed Hesham Ibrahim Abdalla, Paolo Basso, Margherita Musumeci, 和 Georg Groh. 2023. 区分事实与虚构：识别 LLM 时代机器生成科学论文的基准数据集。在 *Proceedings of the 3rd Workshop on Trustworthy Natural Language Processing (TrustNLP 2023)*，第 190–207 页。

+   Mostafazadeh et al. (2016) Mostafazadeh, Nasrin, Nathanael Chambers, Xiaodong He, Devi Parikh, Dhruv Batra, Lucy Vanderwende, Pushmeet Kohli, 和 James Allen。2016. 用于深入理解常识故事的语料库和填空评估。在*2016 年北美计算语言学协会：人类语言技术会议论文集*，第 839–849 页，计算语言学协会。

+   Muñoz-Ortiz, Gómez-Rodríguez, 和 Vilares (2023) Muñoz-Ortiz, Alberto, Carlos Gómez-Rodríguez, 和 David Vilares。2023. 人类与大型语言模型生成文本中的语言模式对比。*ArXiv 预印本*，abs/2308.09067。

+   Munyer 和 Zhong (2023) Munyer, Travis J. E. 和 Xin Zhong。2023. Deeptextmark：基于深度学习的文本水印，用于检测大型语言模型生成的文本。*CoRR*，abs/2305.05773。

+   Murakami, Hoshino, 和 Zhang (2023) Murakami, Soichiro, Sho Hoshino, 和 Peinan Zhang。2023. 广告中的自然语言生成：综述。*ArXiv 预印本*，abs/2306.12719。

+   Muric, Wu, 和 Ferrara (2021) Muric, G, Y Wu, 和 E Ferrara。2021. 社交媒体上的 COVID-19 疫苗犹豫：构建一个公共 Twitter 数据集，包括反疫苗内容、疫苗虚假信息和阴谋论。2021；1–10。*ArXiv 预印本*，abs/2105.05134。

+   Murtaza et al. (2020) Murtaza, Ghulam, Liyana Shuib, Ainuddin Wahid Abdul Wahab, Ghulam Mujtaba, Ghulam Mujtaba, Henry Friday Nweke, Mohammed Ali Al-garadi, Fariha Zulfiqar, Ghulam Raza, 和 Nor Aniza Azmi。2020. 基于深度学习的乳腺癌分类通过医学成像方式：前沿和研究挑战。*人工智能评论*，53:1655–1720。

+   Narayan, Cohen, 和 Lapata (2018) Narayan, Shashi, Shay B. Cohen, 和 Mirella Lapata。2018. 别给我细节，只要总结！主题感知卷积神经网络用于极端摘要。在*2018 年自然语言处理实证方法会议论文集*，第 1797–1807 页，计算语言学协会。

+   Nicks et al. (2023) Nicks, Charlotte, Eric Mitchell, Rafael Rafailov, Archit Sharma, Christopher D Manning, Chelsea Finn, 和 Stefano Ermon。2023. 语言模型检测器容易被优化对抗。在*第十二届国际学习表示会议*。

+   OpenAI (2023) OpenAI. 2023. GPT-4 技术报告。*CoRR*，abs/2303.08774。

+   Orenstrakh et al. (2023) Orenstrakh, Michael Sheinman, Oscar Karnalim, Carlos Anibal Suarez, 和 Michael Liut。2023. 在计算教育中检测大型语言模型生成的文本：针对 ChatGPT 案例的比较研究。*ArXiv 预印本*，abs/2307.07411。

+   Ouyang et al. (2022) Ouyang, Long, Jeff Wu, Xu Jiang, Diogo Almeida, Carroll L Wainwright, Pamela Mishkin, Chong Zhang, Sandhini Agarwal, Katarina Slama, Alex Ray, 等人。2022. 通过人类反馈训练语言模型以遵循指令，2022。*ArXiv 预印本*，abs/2203.02155。

+   Pagnoni, Artidoro, Martin Graciarena, 和 Yulia Tsvetkov. 2022a. 威胁场景和检测神经虚假新闻的最佳实践。在*第 29 届国际计算语言学会议论文集*，第 1233–1249 页，国际计算语言学委员会。

+   Pagnoni, Artidoro, Martin Graciarena, 和 Yulia Tsvetkov. 2022b. 威胁场景和检测神经虚假新闻的最佳实践。在*第 29 届国际计算语言学会议论文集，COLING 2022，韩国庆州，2022 年 10 月 12-17 日*，第 1233–1249 页，国际计算语言学委员会。

+   Peng, Xinlin, Ying Zhou, Ben He, Le Sun, 和 Yingfei Sun. 2024. 隐藏代笔者：对 AI 生成学生论文检测的对抗性评估。*CoRR*，abs/2402.00412。

+   Piccolo, Stephen R, Paul Denny, Andrew Luxton-Reilly, Samuel Payne, 和 Perry G Ridge. 2023. 许多生物信息学编程任务可以使用 ChatGPT 进行自动化。*ArXiv 预印本*，abs/2303.13528。

+   Por, Lip Yee, KokSheik Wong, 和 Kok Onn Chee. 2012. Unispach：一种使用 Unicode 空格字符的基于文本的数据隐藏方法。*J. Syst. Softw.*，85(5)：1075–1082。

+   Porsdam Mann, Sebastian, Brian D Earp, Sven Nyholm, John Danaher, Nikolaj Møller, Hilary Bowman-Smart, Joshua Hatherley, Julian Koplin, Monika Plozza, Daniel Rodger, 等. 2023. 生成 AI 涉及信贷–责备不对称。*ArXiv 预印本*，abs/2305.15324。

+   Price, Gregory 和 Marc D Sakellarios. 2023. 免费软件检测 AI 生成写作的有效性。*国际教学、学习与教育期刊*，2(6)。

+   Pu, Jiameng, Zain Sarwar, Sifat Muhammad Abdullah, Abdullah Rehman, Yoonjin Kim, Parantapa Bhattacharya, Mobin Javed, 和 Bimal Viswanath. 2023a. Deepfake 文本检测：局限性和机会。在*第 44 届 IEEE 安全与隐私研讨会，SP 2023，美国加州旧金山，2023 年 5 月 21-25 日*，第 1613–1630 页，IEEE。

+   Pu, Xiao, Jingyu Zhang, Xiaochuang Han, Yulia Tsvetkov, 和 Tianxing He. 2023b. 关于机器生成文本检测器的零样本泛化。在*计算语言学协会发现：EMNLP 2023*，第 4799–4808 页。

+   Qiu, Xipeng, Tianxiang Sun, Yige Xu, Yunfan Shao, Ning Dai, 和 Xuanjing Huang. 2020. 自然语言处理的预训练模型：综述。*中国科学技术期刊*，63(10)：1872–1897。

+   Quidwai, Mujahid Ali, Chunhui Li, 和 Parijat Dube. 2023. 超越黑箱 AI 生成的剽窃检测：从句子到文档级别。在 *第 18 届自然语言处理在教育应用中的创新使用研讨会，BEA@ACL 2023，加拿大多伦多，2023 年 7 月 13 日*，第 727-735 页，计算语言学协会。

+   Radford, Alec, Jeffrey Wu, Rewon Child, David Luan, Dario Amodei, Ilya Sutskever, 等. 2019. 语言模型是无监督的多任务学习者。 *OpenAI 博客*，1(8):9。

+   Raffel, Colin, Noam Shazeer, Adam Roberts, Katherine Lee, Sharan Narang, Michael Matena, Yanqi Zhou, Wei Li, 和 Peter J. Liu. 2020. 探索统一文本到文本变换器的迁移学习极限。 *J. Mach. Learn. Res.*，21:140:1–140:67。

+   Rajpurkar, Pranav, Jian Zhang, Konstantin Lopyrev, 和 Percy Liang. 2016. SQuAD：100,000+ 问题用于机器文本理解。在 *2016 年自然语言处理实证方法会议*，第 2383-2392 页，计算语言学协会。

+   Ren, Shuhuai, Yihe Deng, Kun He, 和 Wanxiang Che. 2019. 通过概率加权词汇显著性生成自然语言对抗样本。在 *第 57 届计算语言学协会年会*，第 1085-1097 页，计算语言学协会。

+   Rizzo, Stefano Giovanni, Flavio Bertini, 和 Danilo Montesi. 2016. 通过 Unicode 同形字替代实现内容保留的文本水印。在 *第 20 届国际数据库工程与应用研讨会，IDEAS 2016，加拿大蒙特利尔，2016 年 7 月 11-13 日*，第 97-104 页，ACM。

+   Rodriguez, Juan, Todd Hay, David Gros, Zain Shamsi, 和 Ravi Srinivasan. 2022a. 跨领域检测 GPT-2 生成的技术文本。在 *2022 年北美计算语言学协会年会：人类语言技术*，第 1213-1233 页，计算语言学协会。

+   Rodriguez, Juan Diego, Todd Hay, David Gros, Zain Shamsi, 和 Ravi Srinivasan. 2022b. 跨领域检测 GPT-2 生成的技术文本。在 *2022 年北美计算语言学协会年会：人类语言技术，NAACL 2022，美国华盛顿州西雅图，2022 年 7 月 10-15 日*，第 1213-1233 页，计算语言学协会。

+   Sadasivan, Vinu Sankar, Aounon Kumar, Sriram Balasubramanian, Wenxiao Wang, 和 Soheil Feizi. 2023. AI 生成文本能否可靠检测？ *ArXiv 预印本*，abs/2303.11156。

+   Saeed 和 Omlin (2023) Saeed, Waddah 和 Christian Omlin. 2023. 可解释人工智能（XAI）：当前挑战和未来机会的系统性元调查. *知识基础系统*，263:110273。

+   Sarvazyan 等 (2023a) Sarvazyan, Areg Mikael, José Ángel González, Paolo Rosso, 和 Marc Franco-Salvador. 2023a. 监督机器生成文本检测器：家庭和规模的影响. 在 *跨语言评估论坛国际会议*，第 121–132 页，Springer。

+   Sarvazyan 等 (2023b) Sarvazyan, Areg Mikael, José Ángel González, Paolo Rosso, 和 Marc Franco-Salvador. 2023b. 监督机器生成文本检测器：家庭和规模的影响. 在 *实验信息检索与多语言性、多模态性和交互 - 第十四届 CLEF 协会国际会议，CLEF 2023，希腊塞萨洛尼基，2023 年 9 月 18-21 日，会议论文集*，第 14163 卷，*计算机科学讲义笔记*，第 121–132 页，Springer。

+   Schaaff, Schlippe, 和 Mindner (2023) Schaaff, Kristina, Tim Schlippe, 和 Lorenz Mindner. 2023. 人工和 AI 生成文本的分类：英语、法语、德语和西班牙语. 在 *第六届国际自然语言与语音处理会议（ICNLSP 2023），虚拟活动，2023 年 12 月 16-17 日*，第 1–10 页，计算语言学协会。

+   Schneider 等 (2023) Schneider, Sinclair, Florian Steuber, Joao A. G. Schneider, 和 Gabi Dreo Rodosek. 2023. 机器生成文本的识别效果如何？语言模型是否可以被训练以避免识别？ *CoRR*，abs/2310.16992。

+   Schulman 等 (2017a) Schulman, John, Filip Wolski, Prafulla Dhariwal, Alec Radford, 和 Oleg Klimov. 2017a. 近端策略优化算法. *CoRR*，abs/1707.06347。

+   Schulman 等 (2017b) Schulman, John, Filip Wolski, Prafulla Dhariwal, Alec Radford, 和 Oleg Klimov. 2017b. 近端策略优化算法. *ArXiv 预印本*，abs/1707.06347。

+   Schuster 等 (2020a) Schuster, Tal, Roei Schuster, Darsh J. Shah, 和 Regina Barzilay. 2020a. 使用风格特征检测机器生成虚假新闻的局限性. *计算语言学*，46(2):499–510。

+   Schuster 等 (2020b) Schuster, Tal, Roei Schuster, Darsh J. Shah, 和 Regina Barzilay. 2020b. 使用风格特征检测机器生成虚假新闻的局限性. *计算语言学*，46(2):499–510。

+   Seals 和 Shalin (2023) Seals, S. M. 和 Valerie L. Shalin. 2023. ChatGPT 生成的长篇类比缺乏类人心理语言学特征. *CoRR*，abs/2306.04537。

+   Shah 等 (2023) Shah, Aditya, Prateek Ranka, Urmi Dedhia, Shruti Prasad, Siddhi Muni, 和 Kiran Bhowmick. 2023. 通过可解释人工智能和风格特征检测和揭示 AI 生成文本. *国际高级计算机科学与应用期刊*，14(10)。

+   Shen 等（2020）Shen, Dinghan, Mingzhi Zheng, Yelong Shen, Yanru Qu, 和 Weizhu Chen. 2020. 一种简单但难以击败的数据增强方法，用于自然语言理解和生成。*ArXiv 预印本*，abs/2009.13818。

+   Shevlane 等（2023）Shevlane, Toby, Sebastian Farquhar, Ben Garfinkel, Mary Phuong, Jess Whittlestone, Jade Leung, Daniel Kokotajlo, Nahema Marchal, Markus Anderljung, Noam Kolt, Lewis Ho, Divya Siddarth, Shahar Avin, Will Hawkins, Been Kim, Iason Gabriel, Vijay Bolina, Jack Clark, Yoshua Bengio, Paul F. Christiano, 和 Allan Dafoe. 2023. 极端风险的模型评估。*CoRR*，abs/2305.15324。

+   Shi 和 Huang（2020）Shi, Zhouxing 和 Minlie Huang. 2020. 通过共享词汇增强改写识别的鲁棒性。见于 *Association for Computational Linguistics: EMNLP 2020*，第 164–171 页，计算语言学协会。

+   Shi 等（2023）Shi, Zhouxing, Yihan Wang, Fan Yin, Xiangning Chen, Kai-Wei Chang, 和 Cho-Jui Hsieh. 2023. 利用语言模型进行红队测试语言模型检测器。*ArXiv 预印本*，abs/2305.19713。

+   Solaiman 等（2019）Solaiman, Irene, Miles Brundage, Jack Clark, Amanda Askell, Ariel Herbert-Voss, Jeff Wu, Alec Radford, Gretchen Krueger, Jong Wook Kim, Sarah Kreps 等. 2019. 语言模型的发布策略及其社会影响。*ArXiv 预印本*，abs/1908.09203。

+   Soni 和 Wade（2023a）Soni, Mayank 和 Vincent Wade. 2023a. 通过盲评审员和文本分类算法比较 ChatGPT 生成的抽象摘要与真实摘要。*CoRR*，abs/2303.17650。

+   Soni 和 Wade（2023b）Soni, Mayank 和 Vincent P. Wade. 2023b. 通过盲评审员和文本分类算法比较 ChatGPT 生成的抽象摘要与真实摘要。*ArXiv 预印本*，abs/2303.17650。

+   Stiff 和 Johansson（2022）Stiff, Harald 和 Fredrik Johansson. 2022. 检测计算机生成的虚假信息。*Int. J. Data Sci. Anal.*，13(4):363–383。

+   Stokel-Walker（2022）Stokel-Walker, Chris. 2022. AI 机器人 ChatGPT 写作聪明的论文——学术界是否应该担忧？*Nature*。

+   Stokel-Walker 和 Van Noorden（2023）Stokel-Walker, Chris 和 Richard Van Noorden. 2023. ChatGPT 和生成 AI 对科学的意义。*Nature*，614(7947):214–216。

+   Su 等（2023a）Su, Jinyan, Terry Yue Zhuo, Di Wang, 和 Preslav Nakov. 2023a. Detectllm: 利用日志排名信息进行零样本检测机器生成文本。*CoRR*，abs/2306.05540。

+   Su 等（2023b）Su, Zhenpeng, Xing Wu, Wei Zhou, Guangyuan Ma, 和 Songlin Hu. 2023b. HC3 plus: 一种语义不变的人类 ChatGPT 比较语料库。*CoRR*，abs/2309.02731。

+   Susnjak（2022）Susnjak, Teo. 2022. ChatGPT: 在线考试诚信的终结？*ArXiv 预印本*，abs/2212.09292。

+   Tang, Chuang, 和 Hu（2023）Tang, Ruixiang, Yu-Neng Chuang, 和 Xia Hu. 2023. 检测 LLM 生成文本的科学。*CoRR*，abs/2303.07205。

+   Tang 等 (2023) Tang, Ruixiang, Qizhang Feng, Ninghao Liu, Fan Yang 和 Xia Hu. 2023. 你是否用过我的数据集进行训练？通过干净标签后门水印保护公共数据集。*CoRR*, abs/2303.11470。

+   Taori 等 (2023) Taori, Rohan, Ishaan Gulrajani, Tianyi Zhang, Yann Dubois, Xuechen Li, Carlos Guestrin, Percy Liang 和 Tatsunori B. Hashimoto. 2023. Stanford alpaca：一种跟随指令的 llama 模型。 [`github.com/tatsu-lab/stanford_alpaca`](https://github.com/tatsu-lab/stanford_alpaca)。

+   Thirunavukarasu 等 (2023) Thirunavukarasu, Arun James, Darren Shu Jeng Ting, Kabilan Elangovan, Laura Gutierrez, Ting Fang Tan 和 Daniel Shu Wei Ting. 2023. 医学中的大语言模型。*Nature medicine*, 第 1–11 页。

+   Topkara, Topkara 和 Atallah (2006) Topkara, Umut, Mercan Topkara 和 Mikhail J. Atallah. 2006. 模糊性的隐藏美德：通过同义词替换对自然语言文本的定量鲁棒水印。见于 *第八届多媒体与安全研讨会，MM&Sec 2006，瑞士日内瓦，2006 年 9 月 26-27 日*，第 164–174 页，ACM。

+   Touvron 等 (2023) Touvron, Hugo, Thibaut Lavril, Gautier Izacard, Xavier Martinet, Marie-Anne Lachaux, Timothée Lacroix, Baptiste Rozière, Naman Goyal, Eric Hambro, Faisal Azhar, Aurélien Rodriguez, Armand Joulin, Edouard Grave 和 Guillaume Lample. 2023. Llama：开放且高效的基础语言模型。*CoRR*, abs/2302.13971。

+   Tripto 等 (2023) Tripto, Nafis Irtiza, Adaku Uchendu, Thai Le, Mattia Setzu, Fosca Giannotti 和 Dongwon Lee. 2023. HANSEN：用于作者分析的人工智能与人类口语文本基准。*CoRR*, abs/2310.16746。

+   Tu 等 (2023) Tu, Shangqing, Chunyang Li, Jifan Yu, Xiaozhi Wang, Lei Hou 和 Juanzi Li. 2023. Chatlog：记录和分析 ChatGPT 随时间的变化。*CoRR*, abs/2304.14106。

+   Tulchinskii 等 (2023) Tulchinskii, Eduard, Kristian Kuznetsov, Laida Kushnareva, Daniil Cherniavskii, Serguei Barannikov, Irina Piontkovskaya, Sergey Nikolenko 和 Evgeny Burnaev. 2023. 用于稳健检测 AI 生成文本的内在维度估计。*ArXiv 预印本*, abs/2306.04723。

+   Uchendu, Le 和 Lee (2023a) Uchendu, Adaku, Thai Le 和 Dongwon Lee. 2023a. 神经文本作者归属的归因与模糊化：数据挖掘视角。*SIGKDD Explor. Newsl.*, 25(1):1–18。

+   Uchendu, Le 和 Lee (2023b) Uchendu, Adaku, Thai Le 和 Dongwon Lee. 2023b. Toproberta：深伪文本的拓扑感知作者归属。*CoRR*, abs/2309.12934。

+   Uchendu 等 (2020) Uchendu, Adaku, Thai Le, Kai Shu 和 Dongwon Lee. 2020. 神经文本生成的作者归属。在 *2020 年自然语言处理经验方法会议（EMNLP）论文集* 中，第 8384–8395 页，计算语言学协会。

+   Uchendu 等人 (2023) Uchendu, Adaku, Jooyoung Lee, Hua Shen, 和 Thai Le. 2023. 人类协作是否提升了识别大型语言模型生成的深度伪造文本的准确性？*ArXiv 预印本*，abs/2304.01002。

+   Uchendu 等人 (2021) Uchendu, Adaku, Zeyu Ma, Thai Le, Rui Zhang, 和 Dongwon Lee. 2021. TURINGBENCH: 神经文本生成时代的图灵测试基准环境。在 *计算语言学协会会议发现：EMNLP 2021*，第 2001-2016 页，计算语言学协会。

+   Vasilatos 等人 (2023) Vasilatos, Christoforos, Manaar Alam, Talal Rahwan, Yasir Zaki, 和 Michail Maniatakos. 2023. Howkgpt: 通过上下文感知困惑度分析研究 ChatGPT 生成的大学生作业的检测。*ArXiv 预印本*，abs/2305.18226。

+   Venkatraman, Uchendu, 和 Lee (2023) Venkatraman, Saranya, Adaku Uchendu, 和 Dongwon Lee. 2023. Gpt-who: 基于信息密度的机器生成文本检测器。*CoRR*，abs/2310.06202。

+   Verma 等人 (2023) Verma, Vivek, Eve Fleisig, Nicholas Tomlin, 和 Dan Klein. 2023. Ghostbuster: 侦测大型语言模型生成的文本代笔。*CoRR*，abs/2305.15047。

+   Veselovsky, Ribeiro, 和 West (2023) Veselovsky, Veniamin, Manoel Horta Ribeiro, 和 Robert West. 2023. 人工的人工人工智能：众包工作者广泛使用大型语言模型进行文本生产任务。*ArXiv 预印本*，abs/2306.07899。

+   Walters (2023) Walters, William H. 2023. 检测 AI 生成写作的软件的有效性：16 种 AI 文本检测器的比较。*开放信息科学*，7(1):20220158。

+   Wang 等人 (2019) Wang, Alex, Amanpreet Singh, Julian Michael, Felix Hill, Omer Levy, 和 Samuel R. Bowman. 2019. GLUE: 自然语言理解的多任务基准和分析平台。在 *第七届国际学习表示大会（ICLR 2019），美国路易斯安那州新奥尔良，2019 年 5 月 6-9 日*，OpenReview.net。

+   Wang 等人 (2023a) Wang, Pengyu, Linyang Li, Ke Ren, Botian Jiang, Dong Zhang, 和 Xipeng Qiu. 2023a. Seqxgpt: 句子级 AI 生成文本检测。*CoRR*，abs/2310.08903。

+   Wang 等人 (2023b) Wang, Yuxia, Jonibek Mansurov, Petar Ivanov, Jinyan Su, Artem Shelmanov, Akim Tsvigun, Chenxi Whitehouse, Osama Mohammed Afzal, Tarek Mahmoud, Alham Fikri Aji 等人. 2023b. M4: 多生成器、多领域和多语言黑箱机器生成文本检测。*ArXiv 预印本*，abs/2305.14902。

+   Wang 等人 (2023c) Wang, Zecong, Jiaxi Cheng, Chen Cui, 和 Chenhao Yu. 2023c. 实施 BERT 和微调 roberta 来检测 ChatGPT 生成的新闻。*CoRR*，abs/2306.07401。

+   Weber-Wulff 等人 (2023) Weber-Wulff, Debora, Alla Anohina-Naumeca, Sonja Bjelobaba, Tomáš Foltỳnek, Jean Guerrero-Dib, Olumide Popoola, Petr Šigut, 和 Lorna Waddington. 2023. 测试 AI 生成文本的检测工具。*国际教育诚信期刊*，19(1):26。

+   Weber-Wulff 等（2023）Weber-Wulff, Debora, Alla Anohina-Naumeca, Sonja Bjelobaba, Tomás Foltýnek, Jean Guerrero-Dib, Olumide Popoola, Petr Sigut, 和 Lorna Waddington. 2023. AI 生成文本检测工具的测试。*CoRR*, abs/2306.15666。

+   Wei 等（2022）Wei, Jason, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Fei Xia, Ed Chi, Quoc V Le, Denny Zhou 等. 2022. 连锁思维提示引发大型语言模型的推理。*Advances in Neural Information Processing Systems*, 35:24824–24837。

+   Weidinger 等（2021）Weidinger, Laura, John Mellor, Maribeth Rauh, Conor Griffin, Jonathan Uesato, Po-Sen Huang, Myra Cheng, Mia Glaese, Borja Balle, Atoosa Kasirzadeh 等. 2021. 语言模型的伦理与社会风险（2021）。*ArXiv preprint*, abs/2112.04359。

+   Weng 等（2023）Weng, Luoxuan, Minfeng Zhu, Kam Kwai Wong, Shi Liu, Jiashun Sun, Hang Zhu, Dongming Han, 和 Wei Chen. 2023. 针对混合主动式人工科学文本检测的理解与解释。*ArXiv preprint*, abs/2304.05011。

+   Wikipedia（2023）Wikipedia. 2023. 大型语言模型与版权。

+   Wolff（2020）Wolff, Max. 2020. 攻击神经网络文本检测器。*CoRR*, abs/2002.11768。

+   Wu 等（2023）Wu, Kangxi, Liang Pang, Huawei Shen, Xueqi Cheng, 和 Tat-Seng Chua. 2023. Llmdet: 第三方大型语言模型生成文本检测工具。见于 *Findings of the Association for Computational Linguistics: EMNLP 2023, Singapore, December 6-10, 2023*, 页 2113–2133, Association for Computational Linguistics。

+   Wu 和 Xiang（2023）Wu, Zhendong 和 Hui Xiang. 2023. MFD: 多特征检测大型语言模型生成的文本。*CoRR*。

+   Yan 等（2023）Yan, Duanli, Michael Fauss, Jiangang Hao, 和 Wenju Cui. 2023. 写作评估中 AI 生成文章的检测。*Psychological Testing and Assessment Modeling*, 65(2):125–144。

+   Yan 等（2021）Yan, Yuanmeng, Rumei Li, Sirui Wang, Fuzheng Zhang, Wei Wu, 和 Weiran Xu. 2021. ConSERT: 一种对比框架用于自监督句子表示迁移。见于 *Proceedings of the 59th Annual Meeting of the Association for Computational Linguistics and the 11th International Joint Conference on Natural Language Processing (Volume 1: Long Papers)*, 页 5065–5075, Association for Computational Linguistics。

+   Yanagi 等（2020）Yanagi, Yuta, Ryohei Orihara, Yuichi Sei, Yasuyuki Tahara, 和 Akihiko Ohsuga. 2020. 利用生成的评论进行虚假新闻检测。见于 *2020 IEEE 24th International Conference on Intelligent Engineering Systems (INES)*, 页 85–90, IEEE。

+   Yang, Jiang 和 Li（2023）Yang, Lingyi, Feng Jiang, 和 Haizhou Li. 2023. ChatGPT 是否涉及文本？通过测量打磨比率检测 ChatGPT 生成的文本。*ArXiv preprint*, abs/2307.11380。

+   Yang 等（2023a）Yang, Xi, Kejiang Chen, Weiming Zhang, Chang Liu, Yuang Qi, Jie Zhang, Han Fang, 和 Nenghai Yu. 2023a. 黑箱语言模型生成文本的水印技术。*CoRR*, abs/2305.08883。

+   Yang 等（2022）Yang, Xi, Jie Zhang, Kejiang Chen, Weiming Zhang, Zehua Ma, Feng Wang 和 Nenghai Yu。2022。《通过上下文感知的词汇替换追踪文本来源》。见于 *第 36 届 AAAI 人工智能会议，AAAI 2022，第 34 届人工智能创新应用会议，IAAI 2022，第 12 届人工智能教育进展研讨会，EAAI 2022 虚拟会议，2022 年 2 月 22 日至 3 月 1 日*，第 11613–11621 页，AAAI 出版社。

+   Yang 等（2023b）Yang, Xianjun, Wei Cheng, Linda R. Petzold, William Yang Wang 和 Haifeng Chen。2023b。《DNA-GPT：用于无训练检测 GPT 生成文本的发散 n-gram 分析》。*CoRR*，abs/2305.17359。

+   Yang 等（2019）Yang, Zhilin, Zihang Dai, Yiming Yang, Jaime G. Carbonell, Ruslan Salakhutdinov 和 Quoc V. Le。2019。《XLNet：用于语言理解的广义自回归预训练》。见于 *神经信息处理系统进展 32：2019 年神经信息处理系统年会，NeurIPS 2019，2019 年 12 月 8-14 日，温哥华，加拿大*，第 5754–5764 页。

+   Yao 等（2023）Yao, Shunyu, Dian Yu, Jeffrey Zhao, Izhak Shafran, Thomas L Griffiths, Yuan Cao 和 Karthik Narasimhan。2023。《思维树：利用大型语言模型进行深思熟虑的问题解决，2023 年 5 月》。*ArXiv 预印本*，abs/2305.10601。

+   Yasunaga 和 Liang（2021）Yasunaga, Michihiro 和 Percy Liang。2021。《Break-it-fix-it：程序修复的无监督学习》。见于 *第 38 届国际机器学习大会，ICML 2021，2021 年 7 月 18-24 日，虚拟会议*，第 139 卷 *机器学习研究会议论文集*，第 11941–11952 页，PMLR。

+   Yoo 等（2023）Yoo, KiYoon, Wonhyuk Ahn, Jiho Jang 和 Nojun Kwak。2023。《通过不变特征的多比特自然语言水印》。见于 *第 61 届计算语言学协会年会（第 1 卷：长篇论文），ACL 2023，多伦多，加拿大，2023 年 7 月 9-14 日*，第 2092–2115 页，计算语言学协会。

+   Yu 等（2023a）Yu, Peipeng, Jiahan Chen, Xuan Feng 和 Zhihua Xia。2023a。《CHEAT：用于检测 ChatGPT 编写的摘要的大规模数据集》。*CoRR*，abs/2304.12008。

+   Yu 等（2023b）Yu, Xiao, Yuang Qi, Kejiang Chen, Guoqiang Chen, Xi Yang, Pengyuan Zhu, Weiming Zhang 和 Nenghai Yu。2023b。《GPT 亲子鉴定：基于 GPT 遗传继承的 GPT 生成文本检测》。*ArXiv 预印本*，abs/2305.12519。

+   Yuan 等（2022）Yuan, Ann, Andy Coenen, Emily Reif 和 Daphne Ippolito。2022。《Wordcraft：使用大型语言模型进行故事创作》。见于 *第 27 届国际智能用户界面大会*，第 841–852 页。

+   Zellers et al. (2019a) Zellers, Rowan, Ari Holtzman, Yonatan Bisk, Ali Farhadi, 和 Yejin Choi. 2019a. HellaSwag：机器真的能完成你的句子吗？在*第 57 届计算语言学协会年会论文集*，第 4791-4800 页，计算语言学协会。

+   Zellers et al. (2019b) Zellers, Rowan, Ari Holtzman, Hannah Rashkin, Yonatan Bisk, Ali Farhadi, Franziska Roesner, 和 Yejin Choi. 2019b. 防御神经伪新闻。在*神经信息处理系统进展第 32 卷：2019 年神经信息处理系统年会，NeurIPS 2019，2019 年 12 月 8-14 日，温哥华，加拿大*，第 9051-9062 页。

+   Zeng et al. (2023) Zeng, Zijie, Lele Sha, Yuheng Li, Kaixun Yang, Dragan Gašević, 和 Guanliang Chen. 2023. 面向自动边界检测的人机混合论文教育。*arXiv 预印本 arXiv:2307.12267*。

+   Zhang et al. (2023a) Zhang, Ruisi, Shehzeen Samarah Hussain, Paarth Neekhara, 和 Farinaz Koushanfar. 2023a. REMARK-LLM：一个稳健且高效的生成大型语言模型的水印框架。*CoRR*，abs/2310.12362。

+   Zhang et al. (2023b) Zhang, Yue, Yafu Li, Leyang Cui, Deng Cai, Lemao Liu, Tingchen Fu, Xinting Huang, Enbo Zhao, Yu Zhang, Yulong Chen, et al. 2023b. 人工智能海洋中的“美人鱼之歌”：对大型语言模型中幻觉现象的调查。*ArXiv 预印本*，abs/2309.01219。

+   Zhao et al. (2021) Zhao, Zihao, Eric Wallace, Shi Feng, Dan Klein, 和 Sameer Singh. 2021. 使用前的校准：提高语言模型的少样本性能。在*第 38 届国际机器学习大会论文集，ICML 2021，2021 年 7 月 18-24 日，虚拟会议*，*机器学习研究论文集*第 139 卷，第 12697-12706 页，PMLR。

+   Zheng et al. (2023) Zheng, Qinkai, Xiao Xia, Xu Zou, Yuxiao Dong, Shan Wang, Yufei Xue, Zihan Wang, Lei Shen, Andi Wang, Yang Li, et al. 2023. Codegeex：一个用于代码生成的预训练模型，具有对 humaneval-x 的多语言评估。*ArXiv 预印本*，abs/2303.17568。

+   Zhong et al. (2020) Zhong, Wanjun, Duyu Tang, Zenan Xu, Ruize Wang, Nan Duan, Ming Zhou, Jiahai Wang, 和 Jian Yin. 2020. 基于文本事实结构的神经深伪检测。在*2020 年自然语言处理经验方法会议（EMNLP）论文集*，第 2461-2470 页，计算语言学协会。

+   Zhu et al. (2023) Zhu, Biru, Lifan Yuan, Ganqu Cui, Yangyi Chen, Chong Fu, Bingxiang He, Yangdong Deng, Zhiyuan Liu, Maosong Sun, 和 Ming Gu. 2023. 在自己的游戏中击败 LLMs：通过查询 ChatGPT 进行零样本 LLM 生成文本检测。在*2023 年自然语言处理经验方法会议论文集，EMNLP 2023，新加坡，2023 年 12 月 6-10 日*，第 7470-7483 页，计算语言学协会。

生成于 2024 年 5 月 1 日 星期三 13:47:27，由 LaTeXML![吉祥物 Sammy](http://dlmf.nist.gov/LaTeXML/)
