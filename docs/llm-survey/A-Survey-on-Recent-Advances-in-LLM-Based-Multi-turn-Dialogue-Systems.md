<!--yml

类别: 未分类

日期: 2024-09-03 17:30:41

-->

# 关于基于 LLM 的多轮对话系统的最新进展的调查

> 来源：[`arxiv.org/html/2402.18013`](https://arxiv.org/html/2402.18013)

1.  [1 引言](https://arxiv.org/html/2402.18013v1#S1 "1\. 引言 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

    1.  [1.1 什么是多轮对话系统？](https://arxiv.org/html/2402.18013v1#S1.SS1 "1.1\. 什么是多轮对话系统？ ‣ 1\. 引言 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

    1.  [1.2 为什么对基于 LLM 的多轮对话系统进行调查？](https://arxiv.org/html/2402.18013v1#S1.SS2 "1.2\. 为什么对基于 LLM 的多轮对话系统进行调查？ ‣ 1\. 引言 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

    1.  [1.3 本调查的贡献](https://arxiv.org/html/2402.18013v1#S1.SS3 "1.3\. 本调查的贡献 ‣ 1\. 引言 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

1.  [2 一般方法](https://arxiv.org/html/2402.18013v1#S2 "2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

    1.  [2.1 仅解码器变换器架构](https://arxiv.org/html/2402.18013v1#S2.SS1 "2.1\. 仅解码器变换器架构 ‣ 2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

        1.  [2.1.1 因果解码器](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1 "2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器变换器架构 ‣ 2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

            1.  [GPT 系列](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1 "GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器变换器架构 ‣ 2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

                1.  [GPT-1](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1.SPx1 "GPT-1\. ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器变换器架构 ‣ 2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

                1.  [GPT-2](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1.SPx2 "GPT-2\. ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器变换器架构 ‣ 2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

                1.  [GPT-3](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1.SPx3 "GPT-3\. ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器变换器架构 ‣ 2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

                1.  [GPT-3.5](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1.SPx4 "GPT-3.5\. ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器变换器架构 ‣ 2\. 一般方法 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查")

                1.  [GPT-4.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1.SPx5 "GPT-4\. ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

                1.  [ChatGPT.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1.SPx6 "ChatGPT. ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

                1.  [GPTs.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px1.SPx7 "GPTs. ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

            1.  [LLAMA 系列](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px2 "LLAMA 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

                1.  [LLAMA.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px2.SPx1 "LLAMA. ‣ LLAMA 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

                1.  [LLAMA2.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px2.SPx2 "LLAMA2\. ‣ LLAMA 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

                1.  [LLAMA2 CHAT.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px2.SPx3 "LLAMA2 CHAT. ‣ LLAMA 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

                1.  [CODE LLAMA.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS1.Px2.SPx4 "CODE LLAMA. ‣ LLAMA 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

        1.  [2.1.2 前缀解码器](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS2 "2.1.2\. 前缀解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

            1.  [GLM](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS2.Px1 "GLM ‣ 2.1.2\. 前缀解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

            1.  [ChatGLM 系列](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS2.Px2 "ChatGLM 系列 ‣ 2.1.2\. 前缀解码器 ‣ 2.1\. 仅解码器的 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展综述")

                1.  [ChatGLM-6B.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS2.Px2.SPx1 "ChatGLM-6B. ‣ ChatGLM 系列 ‣ 2.1.2\. 前缀解码器 ‣ 2.1\. 仅解码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

                1.  [ChatGLM2-6B.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS2.Px2.SPx2 "ChatGLM2-6B. ‣ ChatGLM 系列 ‣ 2.1.2\. 前缀解码器 ‣ 2.1\. 仅解码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

                1.  [ChatGLM3-6B.](https://arxiv.org/html/2402.18013v1#S2.SS1.SSS2.Px2.SPx3 "ChatGLM3-6B. ‣ ChatGLM 系列 ‣ 2.1.2\. 前缀解码器 ‣ 2.1\. 仅解码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

    1.  [2.2 仅编码器 Transformer 架构](https://arxiv.org/html/2402.18013v1#S2.SS2 "2.2\. 仅编码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

        1.  [2.2.1 BERT 系列](https://arxiv.org/html/2402.18013v1#S2.SS2.SSS1 "2.2.1\. BERT 系列 ‣ 2.2\. 仅编码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

            1.  [BERT](https://arxiv.org/html/2402.18013v1#S2.SS2.SSS1.Px1 "BERT ‣ 2.2.1\. BERT 系列 ‣ 2.2\. 仅编码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

            1.  [RoBERTa](https://arxiv.org/html/2402.18013v1#S2.SS2.SSS1.Px2 "RoBERTa ‣ 2.2.1\. BERT 系列 ‣ 2.2\. 仅编码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

        1.  [2.2.2 UNiLM](https://arxiv.org/html/2402.18013v1#S2.SS2.SSS2 "2.2.2\. UNiLM ‣ 2.2\. 仅编码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

    1.  [2.3 编码器-解码器 Transformer 架构](https://arxiv.org/html/2402.18013v1#S2.SS3 "2.3\. 编码器-解码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

        1.  [2.3.1 BART](https://arxiv.org/html/2402.18013v1#S2.SS3.SSS1 "2.3.1\. BART ‣ 2.3\. 编码器-解码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

        1.  [2.3.2 文本到文本转换 Transformer](https://arxiv.org/html/2402.18013v1#S2.SS3.SSS2 "2.3.2\. 文本到文本转换 Transformer ‣ 2.3\. 编码器-解码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 最近 LLM 基于多轮对话系统的进展调查")

1.  [3 微调](https://arxiv.org/html/2402.18013v1#S3 "3\. 微调 ‣ 最近 LLM 基于多轮对话系统的进展调查")

    1.  [3.1 完全微调](https://arxiv.org/html/2402.18013v1#S3.SS1 "3.1\. 完全微调 ‣ 3\. 微调 ‣ 最近 LLM 基于多轮对话系统的进展调查")

    1.  [3.2 参数高效的微调](https://arxiv.org/html/2402.18013v1#S3.SS2 "3.2\. Parameter-efficient Fine-Tuning ‣ 3\. Fine-Tuning ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [3.2.1 适配器](https://arxiv.org/html/2402.18013v1#S3.SS2.SSS1 "3.2.1\. Adapters ‣ 3.2\. Parameter-efficient Fine-Tuning ‣ 3\. Fine-Tuning ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [3.2.2 LoRA](https://arxiv.org/html/2402.18013v1#S3.SS2.SSS2 "3.2.2\. LoRA ‣ 3.2\. Parameter-efficient Fine-Tuning ‣ 3\. Fine-Tuning ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [3.2.3 指令微调](https://arxiv.org/html/2402.18013v1#S3.SS2.SSS3 "3.2.3\. Instruction Fine-Tuning ‣ 3.2\. Parameter-efficient Fine-Tuning ‣ 3\. Fine-Tuning ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

    1.  [3.3 缓解微调不稳定性](https://arxiv.org/html/2402.18013v1#S3.SS3 "3.3\. Mitigating Fine-Tuning Instabilities ‣ 3\. Fine-Tuning ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

1.  [4 提示工程](https://arxiv.org/html/2402.18013v1#S4 "4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

    1.  [4.1 提示调优](https://arxiv.org/html/2402.18013v1#S4.SS1 "4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [4.1.1 离散提示](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS1 "4.1.1\. Discrete Prompts ‣ 4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

            1.  [D1: 模式利用训练](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS1.Px1 "D1:Pattern-Exploiting Training ‣ 4.1.1\. Discrete Prompts ‣ 4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

            1.  [D2: LM-BFF](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS1.Px2 "D2:LM-BFF ‣ 4.1.1\. Discrete Prompts ‣ 4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

            1.  [D3: 带规则的提示调优](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS1.Px3 "D3:Prompt Tuning with Rules ‣ 4.1.1\. Discrete Prompts ‣ 4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

            1.  [D4: 知识丰富的提示调优](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS1.Px4 "D4:Knowledgeable Prompt-tuning ‣ 4.1.1\. Discrete Prompts ‣ 4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [4.1.2 连续提示](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS2 "4.1.2\. Continuous Prompts ‣ 4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

            1.  [C1:P-调优](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS2.Px1 "C1:P-调优 ‣ 4.1.2\. 连续提示 ‣ 4.1\. 提示调优 ‣ 4\. 提示工程 ‣ 近期 LLM 基础多轮对话系统的进展综述")

            1.  [C2:前缀调优](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS2.Px2 "C2:前缀调优 ‣ 4.1.2\. 连续提示 ‣ 4.1\. 提示调优 ‣ 4\. 提示工程 ‣ 近期 LLM 基础多轮对话系统的进展综述")

            1.  [C3: P-调优 V2](https://arxiv.org/html/2402.18013v1#S4.SS1.SSS2.Px3 "C3: P-调优 V2 ‣ 4.1.2\. 连续提示 ‣ 4.1\. 提示调优 ‣ 4\. 提示工程 ‣ 近期 LLM 基础多轮对话系统的进展综述")

    1.  [4.2 无需调优的提示](https://arxiv.org/html/2402.18013v1#S4.SS2 "4.2\. 无需调优的提示 ‣ 4\. 提示工程 ‣ 近期 LLM 基础多轮对话系统的进展综述")

        1.  [4.2.1 上下文学习](https://arxiv.org/html/2402.18013v1#S4.SS2.SSS1 "4.2.1\. 上下文学习 ‣ 4.2\. 无需调优的提示 ‣ 4\. 提示工程 ‣ 近期 LLM 基础多轮对话系统的进展综述")

        1.  [4.2.2 思维链](https://arxiv.org/html/2402.18013v1#S4.SS2.SSS2 "4.2.2\. 思维链 ‣ 4.2\. 无需调优的提示 ‣ 4\. 提示工程 ‣ 近期 LLM 基础多轮对话系统的进展综述")

1.  [5 基于 LLM 的任务导向对话系统](https://arxiv.org/html/2402.18013v1#S5 "5\. 基于 LLM 的任务导向对话系统 ‣ 近期 LLM 基础多轮对话系统的进展综述")

    1.  [5.1 基于管道的方法](https://arxiv.org/html/2402.18013v1#S5.SS1 "5.1\. 基于管道的方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ 近期 LLM 基础多轮对话系统的进展综述")

        1.  [5.1.1 自然语言理解](https://arxiv.org/html/2402.18013v1#S5.SS1.SSS1 "5.1.1\. 自然语言理解 ‣ 5.1\. 基于管道的方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ 近期 LLM 基础多轮对话系统的进展综述")

            1.  [意图检测](https://arxiv.org/html/2402.18013v1#S5.SS1.SSS1.Px1 "意图检测 ‣ 5.1.1\. 自然语言理解 ‣ 5.1\. 基于管道的方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ 近期 LLM 基础多轮对话系统的进展综述")

            1.  [联合意图检测与槽填充](https://arxiv.org/html/2402.18013v1#S5.SS1.SSS1.Px2 "联合意图检测与槽填充 ‣ 5.1.1\. 自然语言理解 ‣ 5.1\. 基于管道的方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ 近期 LLM 基础多轮对话系统的进展综述")

        1.  [5.1.2 对话状态跟踪](https://arxiv.org/html/2402.18013v1#S5.SS1.SSS2 "5.1.2\. 对话状态跟踪 ‣ 5.1\. 基于管道的方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ 近期 LLM 基础多轮对话系统的进展综述")

        1.  [5.1.3 政策学习](https://arxiv.org/html/2402.18013v1#S5.SS1.SSS3 "5.1.3\. 政策学习 ‣ 5.1\. 流水线方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

        1.  [5.1.4 自然语言生成](https://arxiv.org/html/2402.18013v1#S5.SS1.SSS4 "5.1.4\. 自然语言生成 ‣ 5.1\. 流水线方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

    1.  [5.2 端到端方法](https://arxiv.org/html/2402.18013v1#S5.SS2 "5.2\. 端到端方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

1.  [6 基于 LLM 的开放域对话系统](https://arxiv.org/html/2402.18013v1#S6 "6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

    1.  [6.1 检索式方法](https://arxiv.org/html/2402.18013v1#S6.SS1 "6.1\. 检索式方法 ‣ 6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

    1.  [6.2 生成式方法](https://arxiv.org/html/2402.18013v1#S6.SS2 "6.2\. 生成式方法 ‣ 6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

        1.  [6.2.1 知识增强生成](https://arxiv.org/html/2402.18013v1#S6.SS2.SSS1 "6.2.1\. 知识增强生成 ‣ 6.2\. 生成式方法 ‣ 6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

        1.  [6.2.2 个性化和一致性](https://arxiv.org/html/2402.18013v1#S6.SS2.SSS2 "6.2.2\. 个性化和一致性 ‣ 6.2\. 生成式方法 ‣ 6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

    1.  [6.3 混合方法](https://arxiv.org/html/2402.18013v1#S6.SS3 "6.3\. 混合方法 ‣ 6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

        1.  [6.3.1 整合检索和生成](https://arxiv.org/html/2402.18013v1#S6.SS3.SSS1 "6.3.1\. 整合检索和生成 ‣ 6.3\. 混合方法 ‣ 6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

        1.  [6.3.2 增强对话与外部知识](https://arxiv.org/html/2402.18013v1#S6.SS3.SSS2 "6.3.2\. 增强对话与外部知识 ‣ 6.3\. 混合方法 ‣ 6\. 基于 LLM 的开放域对话系统 ‣ LLM-Based 多轮对话系统最新进展调查")

1.  [7 评估方法](https://arxiv.org/html/2402.18013v1#S7 "7\. 评估方法 ‣ LLM-Based 多轮对话系统最新进展调查")

    1.  [7.1 自动评估](https://arxiv.org/html/2402.18013v1#S7.SS1 "7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

        1.  [7.1.1 面向任务导向对话系统的自动评估方法](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS1 "7.1.1\. 面向任务导向对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [联合目标准确度](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS1.Px1 "联合目标准确度 ‣ 7.1.1\. 面向任务导向对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [槽位准确度](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS1.Px2 "槽位准确度 ‣ 7.1.1\. 面向任务导向对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [平均目标准确度](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS1.Px3 "平均目标准确度 ‣ 7.1.1\. 面向任务导向对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [所请求槽位 F1 值](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS1.Px4 "所请求槽位 F1 值 ‣ 7.1.1\. 面向任务导向对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [BLEU（BLEU 评估指标）](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS1.Px5 "BLEU ‣ 7.1.1\. 面向任务导向对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [实体 F1 值](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS1.Px6 "实体 F1 值 ‣ 7.1.1\. 面向任务导向对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

        1.  [7.1.2 开放领域对话系统的自动评估方法](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS2 "7.1.2\. 开放领域对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [困惑度](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS2.Px1 "困惑度 ‣ 7.1.2\. 开放领域对话系统的自动评估方法 ‣ 7.1\. 自动评估 ‣ 7\. 评估方法 ‣ 最近基于 LLM 的多轮对话系统的研究进展调查")

            1.  [DIST-n](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS2.Px2 "DIST-n ‣ 7.1.2\. Automatic Evaluation Approaches for Open-domain Dialogue Systems ‣ 7.1\. Automatic Evaluation ‣ 7\. EVALUATION APPROACHES ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

            1.  [Recall@K](https://arxiv.org/html/2402.18013v1#S7.SS1.SSS2.Px3 "Recall@K ‣ 7.1.2\. Automatic Evaluation Approaches for Open-domain Dialogue Systems ‣ 7.1\. Automatic Evaluation ‣ 7\. EVALUATION APPROACHES ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

    1.  [7.2 人工评估](https://arxiv.org/html/2402.18013v1#S7.SS2 "7.2\. Human Evaluation ‣ 7\. EVALUATION APPROACHES ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

1.  [8 数据集](https://arxiv.org/html/2402.18013v1#S8 "8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

    1.  [8.1 任务导向对话系统的数据集](https://arxiv.org/html/2402.18013v1#S8.SS1 "8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [MultiWOZ](https://arxiv.org/html/2402.18013v1#S8.SS1.SSS0.Px1 "MultiWOZ ‣ 8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [RiSAWOZ](https://arxiv.org/html/2402.18013v1#S8.SS1.SSS0.Px2 "RiSAWOZ ‣ 8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [CrossWOZ](https://arxiv.org/html/2402.18013v1#S8.SS1.SSS0.Px3 "CrossWOZ ‣ 8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [PersuasionForGood](https://arxiv.org/html/2402.18013v1#S8.SS1.SSS0.Px4 "PersuasionForGood ‣ 8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [WOZ 2.0](https://arxiv.org/html/2402.18013v1#S8.SS1.SSS0.Px5 "WOZ 2.0 ‣ 8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [斯坦福多领域](https://arxiv.org/html/2402.18013v1#S8.SS1.SSS0.Px6 "Stanford Multi-Domain ‣ 8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

    1.  [8.2 开放域对话系统的数据集](https://arxiv.org/html/2402.18013v1#S8.SS2 "8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [PersonaChat](https://arxiv.org/html/2402.18013v1#S8.SS2.SSS0.Px1 "PersonaChat ‣ 8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")

        1.  [MMdialog](https://arxiv.org/html/2402.18013v1#S8.SS2.SSS0.Px2 "MMdialog ‣ 8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ 关于基于 LLM 的多轮对话系统的最新进展综述")

        1.  [Dailydialog](https://arxiv.org/html/2402.18013v1#S8.SS2.SSS0.Px3 "Dailydialog ‣ 8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ 关于基于 LLM 的多轮对话系统的最新进展综述")

        1.  [Pchatbot](https://arxiv.org/html/2402.18013v1#S8.SS2.SSS0.Px4 "Pchatbot ‣ 8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ 关于基于 LLM 的多轮对话系统的最新进展综述")

        1.  [PersonalDialogue](https://arxiv.org/html/2402.18013v1#S8.SS2.SSS0.Px5 "PersonalDialogue ‣ 8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ 关于基于 LLM 的多轮对话系统的最新进展综述")

        1.  [Douban](https://arxiv.org/html/2402.18013v1#S8.SS2.SSS0.Px6 "Douban ‣ 8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ 关于基于 LLM 的多轮对话系统的最新进展综述")

1.  [9 讨论](https://arxiv.org/html/2402.18013v1#S9 "9\. 讨论 ‣ 关于基于 LLM 的多轮对话系统的最新进展综述")

1.  [10 结论](https://arxiv.org/html/2402.18013v1#S10 "10\. 结论 ‣ 关于基于 LLM 的多轮对话系统的最新进展综述")

许可证：CC ZeroarXiv:2402.18013v1 [cs.CL] 2024 年 2 月 28 日

# 关于基于 LLM 的多轮对话系统的最新进展综述

Zihao Yi yizh6@mail2.sysu.edu.cn 中山大学 深圳 中国, Jiarui Ouyang ouyjr@mail2.sysu.edu.cn 中山大学 深圳 中国, Yuwen Liu liuyw86@mail2.sysu.edu.cn 中山大学 深圳 中国, Tianhao Liao liaoth5@mail2.sysu.edu.cn 中山大学 深圳 中国, Zhe Xu xuzh226@mail2.sysu.edu.cn 中山大学 深圳 中国 和 Ying Shen sheny76@mail.sysu.edu.cn 中山大学 深圳 中国（2024 年 2 月 20 日；2007 年 12 月；2009 年 3 月 12 日；2009 年 6 月 5 日）

###### 摘要。

本综述提供了对多轮对话系统研究的全面回顾，特别关注基于大语言模型（LLMs）的多轮对话系统。本文旨在：(a) 总结现有的 LLMs 及其适配到下游任务的方法；(b) 阐述多轮对话系统的最新进展，涵盖基于 LLM 的开放领域对话（ODD）和任务导向对话（TOD）系统，以及相关数据集和评估指标；(c) 讨论 LLMs 发展和对多轮对话系统需求增加带来的未来重点和近期研究问题。

大语言模型、微调、提示工程、任务导向对话系统、开放域对话系统^†^†版权：acm 授权^†^†期刊年份：2024^†^†doi：XXXXXXX.XXXXXXX^†^†期刊：JACM^†^†期刊卷号：37^†^†期刊期号：4^†^†文章：111^†^†出版月份：2^†^†isbn：978-1-4503-XXXX-X/18/06^†^†ccs：计算方法 话语、对话和语用学^†^†ccs：综合和参考 调查和概述

## 1\. 引言

### 1.1\. 什么是多轮对话系统？

能够生成自然且有意义的响应以与人类沟通的多轮对话系统是人工智能（AI）的长期目标。这类人机交互任务由于其潜在影响和商业价值的吸引力，受到了学术界和工业界的越来越多关注。多轮对话任务可以视为序列到序列的任务，它从用户消息 $\mathcal{U}=(u_{1},u_{2},...u_{t})$ 生成系统响应 $\mathcal{S}=(s_{1},s_{2},...s_{t})$，其中 $u_{t}$ 和 $s_{t}$ 分别是第 $t$ 轮的用户消息和系统响应。

多轮对话系统可以分为任务导向（TOD）系统和开放域（ODD）系统。TOD 系统帮助用户处理特定领域内的任务，如酒店预订、餐馆推荐等，而 ODD 系统则在没有领域限制的情况下与用户聊天。TOD 任务和 ODD 任务并非完全独立，一旦对话系统检测到特定的用户需求，ODD 任务可以转换为 TOD 任务。

传统对话系统主要依赖于基于规则的方法和基于检索的方法。基于规则的对话系统（[weizenbaum1966eliza,](https://arxiv.org/html/2402.18013v1#bib.bib1) ; [colby1971artificial,](https://arxiv.org/html/2402.18013v1#bib.bib2) ; [goddeau1996form,](https://arxiv.org/html/2402.18013v1#bib.bib3) ）通过为特定场景预定义对话流程生成响应。基于检索的对话系统（[wu2016sequential,](https://arxiv.org/html/2402.18013v1#bib.bib4) ; [zhao2016towards,](https://arxiv.org/html/2402.18013v1#bib.bib5) ; [ma2019triplenet,](https://arxiv.org/html/2402.18013v1#bib.bib6) ）依赖于预定义的模板，使它们比基于规则的系统更具灵活性。然而，基于检索的对话系统的应用范围仍然有限，因为生成的响应基于预定义的模板。随着深度学习方法的发展，提出了许多基于深度神经网络的多轮对话系统（[serban2016building,](https://arxiv.org/html/2402.18013v1#bib.bib7) ; [he2020amalgamating,](https://arxiv.org/html/2402.18013v1#bib.bib8) ; [qiu2019training,](https://arxiv.org/html/2402.18013v1#bib.bib9) ）。最近，随着预训练大语言模型的出现，多轮对话系统的性能得到了显著提升。

### 1.2\. 为什么要对基于大语言模型（LLM）的多轮对话系统进行调查？

Arora 等人（[arora2013dialogue,](https://arxiv.org/html/2402.18013v1#bib.bib10)）提供了对话系统的概述，并介绍了各种对话系统框架。然而，该调查将对话系统视为一种通用系统，而不是将其分类为 TOD 和 ODD 系统，也没有涵盖深度学习模型。Chen 等人（[chen2017survey,](https://arxiv.org/html/2402.18013v1#bib.bib11)）将对话系统分类为 TOD 和 ODD 系统，讨论了深度学习技术在这两种对话系统中的应用。然而，该调查并未深入探讨基于预训练 LLM 的多轮对话系统。Ni 等人（[ni2023recent,](https://arxiv.org/html/2402.18013v1#bib.bib12)）的综述涵盖了基于预训练 LLM 的多轮对话系统，但这项研究没有提供关于 LLM 的详细见解以及将其适应于下游子任务的方法。相比之下，Qin 等人（[qin2023end,](https://arxiv.org/html/2402.18013v1#bib.bib13)）对预训练 LLM 在特定目标对话场景中的应用进行了更全面的探索。然而，本文的重点主要集中在端到端任务导向的多轮对话系统上。

我们的论文旨在提供基于 LLM 的多轮对话系统的最前沿概述，随后我们将全面阐述现有的预训练 LLM 及其适应这些模型以用于下游任务的方法。预计这一调查将吸引学术界和工业界的广泛观众，包括研究人员和从业者。

### 1.3\. 本调查的贡献

在本文中，我们对基于 LLM 的多轮对话方法、评估指标和数据集进行了全面的回顾。我们论文的贡献可以总结如下：

(1) 对 LLM 及其适应不同子任务的方法进行彻底回顾，以及最新的基于 LLM 的多轮对话系统；

(2) 详细阐述最前沿的多轮对话数据集和评估指标。

(3) 讨论一些未来的重点和因对话系统需求增加以及 LLM 的发展而出现的最新研究问题。

本调查的其余部分组织如下。在第[2](https://arxiv.org/html/2402.18013v1#S2 "2\. GENERAL METHODS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节中，我们提供了对流行 LLMs 的详细阐述。从第[3](https://arxiv.org/html/2402.18013v1#S3 "3\. Fine-Tuning ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节到第[4](https://arxiv.org/html/2402.18013v1#S4 "4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节，我们将全面介绍将 LLMs 适应于下游任务的方法。在第[5](https://arxiv.org/html/2402.18013v1#S5 "5\. LLM Based Task-oriented Dialogue Systems ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节中，我们介绍了任务导向对话系统（TOD）的重要方法，包括基于管道的方法和端到端的方法。第[6](https://arxiv.org/html/2402.18013v1#S6 "6\. LLM Based Open-Domain Dialogue Systems ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节提出了最先进的开放域对话系统（ODD）方法。在第[7](https://arxiv.org/html/2402.18013v1#S7 "7\. EVALUATION APPROACHES ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节和第[8](https://arxiv.org/html/2402.18013v1#S8 "8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节中，我们介绍了一些相关的数据集和评估指标。此外，第[9](https://arxiv.org/html/2402.18013v1#S9 "9\. DISCUSSION ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节提出了基于 LLM 的多轮对话的一些问题和挑战。最后，我们在第[10](https://arxiv.org/html/2402.18013v1#S10 "10\. CONCLUSION ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")节中总结了我们的调查。

## 2\. 一般方法

LLMs 是一类大规模人工智能模型，具有数十亿个参数的特征（[kaplan2020scaling,](https://arxiv.org/html/2402.18013v1#bib.bib14)）。扩大 LLMs 的规模使其能够学习更复杂和准确的语言表示，从而在各种下游自然语言处理（NLP）任务中表现更好，特别是在自然语言生成（NLG）挑战中表现尤为出色（[wei2022emergent,](https://arxiv.org/html/2402.18013v1#bib.bib15)；[qiu2020pre,](https://arxiv.org/html/2402.18013v1#bib.bib16)）。不同 LLMs 结构的简要比较见于表[1](https://arxiv.org/html/2402.18013v1#S2.T1 "Table 1 ‣ 2\. GENERAL METHODS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems")。

原始的 Transformer 架构（[vaswani2017attention](https://arxiv.org/html/2402.18013v1#bib.bib17)），一种序列到序列的模型，已经成为各种 LLM 的基础框架，利用编码器和解码器以及自注意力机制作为其核心组件，凭借其卓越的并行性和能力而受到关注。根据模型中使用的不同注意力机制的掩蔽方法，当前的 LLM 可以分为三类，即编码器-解码器、仅解码器和仅编码器。仅解码器类别进一步包括因果解码器和前缀解码器，如图 [1](https://arxiv.org/html/2402.18013v1#S2.F1 "Figure 1 ‣ 2\. GENERAL METHODS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 所示。

在接下来的子节中，我们将介绍基于不同 Transformer 架构的不同类型的 LLM。

表 1\. 不同模型结构的比较

| 模型 | 模型名称 | 解码器 | 编码器 | 注意力机制 |
| --- | --- | --- | --- | --- |
| 因果 | 前缀 |
| GPT 系列 | GPT-1 | ✓ | - | - | 掩蔽的单向多头自注意力 |
| GPT-2 | ✓ | - | - | 掩蔽的单向多头自注意力 |
| GPT-3 | ✓ | - | - | 稀疏单向注意力（分解注意力） |
| GPT-3.5 | ✓ | - | - | 稀疏单向注意力（分解注意力） |
| GPT-4 | ✓ | - | - | 多查询单向注意力 |
| LLaMA 系列 | LLaMA | ✓ | - | - | 因果单向多头注意力 |
| LLaMA2 | ✓ | - | - | 分组查询单向注意力 |
| GLM 系列 | GLM | - | ✓ | - | 双向自注意力 |
| BERT 系列 | BERT | - | - | ✓ | 双向自注意力 |
| UNILM 系列 | UNILM | - | - | ✓ | 双向自注意力 |
| BART 系列 | BERT | ✓ | - | ✓ | 掩蔽的多头自注意力 & 编码器与解码器之间的交叉注意力 |

| T5 系列 | T5 | ✓ | - | ✓ | 掩蔽的多头自注意力 & 编码器与解码器之间的交叉注意力 | ![参见说明](img/c84a1ddf0330c601304fc94eaba28651.png)

图 1\. 解码器-仅架构和编码器-解码器架构之间的注意力掩蔽模式的矩阵比较。该矩阵使用深色单元格允许在输出时间步 $i$ 上对输入元素 $j$ 进行自注意力，而浅色单元格限制这种注意力。左侧面板代表完整的输入注意力，中间面板表示防止未来输入的依赖，而右侧面板则将因果掩蔽与前缀结合，进行部分输入序列的全视掩蔽。([raffel2020exploring](https://arxiv.org/html/2402.18013v1#bib.bib18) )

### 2.1\. 仅解码器 Transformer 架构

仅解码器模型（[raffel2020exploring,](https://arxiv.org/html/2402.18013v1#bib.bib18)），独立运行没有编码器，可以作为一个主要用于下一个步骤预测的语言模型（[liu2018generating,](https://arxiv.org/html/2402.18013v1#bib.bib19); [radford2018improving,](https://arxiv.org/html/2402.18013v1#bib.bib20); [al2019character,](https://arxiv.org/html/2402.18013v1#bib.bib21)）。在语言模型训练过程中，仅解码器模型负责生成目标序列。

#### 2.1.1\. 因果解码器

因果解码器架构采用单向注意力掩蔽，以确保每个输入标记只能关注过去的标记和自身。输入和输出标记在解码器中以类似的方式处理。该架构的示意图在图 [1](https://arxiv.org/html/2402.18013v1#S2.F1 "图 1 ‣ 2\. 一般方法 ‣ 基于 LLM 的多轮对话系统的最新进展调查") 的中间面板中显示。

##### GPT 系列

生成式预训练变换器（GPT）模型在自然语言处理领域引起了广泛关注（[ye2023comprehensive,](https://arxiv.org/html/2402.18013v1#bib.bib22)），GPT 系列模型的技术演变在图 [2](https://arxiv.org/html/2402.18013v1#S2.F2 "图 2 ‣ GPT 系列 ‣ 2.1.1\. 因果解码器 ‣ 2.1\. 仅解码器 Transformer 架构 ‣ 2\. 一般方法 ‣ 基于 LLM 的多轮对话系统的最新进展调查") 中进行了说明。作为建立在 Transformer 架构上的前沿技术，GPT 模型的多功能性和强大性能使其成为各种 NLP 任务的通用解决方案。

![参见说明](img/5ef62bde5736f5f34fe024e9df6e0e39.png)

图 2\. GPT 系列模型技术演变的简要说明。我们主要依赖于研究论文、博客文章以及 OpenAI 提供的官方 API 来创建此流程图。实线代表两个模型之间演变路径的明确证据（例如，官方声明新的模型是基于基础模型开发的），而虚线表示相对较弱的演变关系。

###### GPT-1.

由 OpenAI 团队提出的 GPT-1 ([radford2018improving,](https://arxiv.org/html/2402.18013v1#bib.bib20))，即生成式预训练变换器 1（[vaswani2017attention,](https://arxiv.org/html/2402.18013v1#bib.bib17)），作为 GPT 系列的基础模型，确立了模型自然语言文本的关键架构和基本原则，特别是预测下一个词。GPT-1 采用仅解码器的 Transformer 架构，通过无监督预训练和有监督微调的组合，实施半监督的方法来理解语言。

###### GPT-2.

GPT-2 ([radford2019language,](https://arxiv.org/html/2402.18013v1#bib.bib23)) 是 GPT-1 架构 ([radford2018improving,](https://arxiv.org/html/2402.18013v1#bib.bib20)) 的扩展，其参数规模增加到 15 亿。GPT-2 在大规模的 WebText 数据集上进行训练，旨在通过无监督语言建模执行多种任务，消除了对带标签数据进行明确微调的需求。GPT-2 使用一种概率形式来解决多任务问题，表示为 $p(output|input,task)$，根据输入和任务信息预测输出。这种方法类似于在 ([mccann2018natural,](https://arxiv.org/html/2402.18013v1#bib.bib24)) 中发现的类似方法。利用多层自注意机制，GPT-2 实现了对整个上下文的全连接交叉注意，并以计算效率高的方式进行。

###### GPT-3。

GPT-3 ([brown2020language,](https://arxiv.org/html/2402.18013v1#bib.bib25)) 采用注意力机制，使得模型能够选择性地关注其认为最相关的输入文本片段，并采用自回归方法，利用 Transformer 架构的变换能力。

###### GPT-3.5。

GPT-3.5 模型，也称为 InstructGPT ([ouyang2022training,](https://arxiv.org/html/2402.18013v1#bib.bib26))，是基于 code-davinci-002 开发的，突显了在代码数据上进行训练以提升 GPT 模型推理能力的有效性 ([zhao2023survey,](https://arxiv.org/html/2402.18013v1#bib.bib27))。InstructGPT 是一个在 GPT-3 ([brown2020language,](https://arxiv.org/html/2402.18013v1#bib.bib25)) 上通过结合监督学习和基于人类反馈的强化学习（RLHF）进行微调的语言模型。GPT-3.5 被用于开发聊天机器人产品 ChatGPT ([openai_chatgpt,](https://arxiv.org/html/2402.18013v1#bib.bib28); [lock2022ai,](https://arxiv.org/html/2402.18013v1#bib.bib29))。gpt-3.5-turbo 是最强大且具有成本效益的 GPT-3.5 模型。GPT-3.5 在维持真实度和减少有害输出方面有所改进，表明用人类反馈进行微调是提升语言模型与人类意图对齐的有效方法。

###### GPT-4。

GPT-4 ([openai2023gpt4,](https://arxiv.org/html/2402.18013v1#bib.bib30)) 是一种多模态的语言模型，接受图像和文本输入并生成文本输出。尽管在各种现实世界的场景中不如人类能力强，GPT-4 在一系列专业和学术基准测试中展示了接近人类水平的表现。值得注意的是，与 GPT-3.5 相比，GPT-4 的校准有了改进 ([ouyang2022training,](https://arxiv.org/html/2402.18013v1#bib.bib26))，在预测答案正确性方面表现出更高的准确性。GPT-4 的多功能性扩展到 ChatGPT ([openai_chatgpt,](https://arxiv.org/html/2402.18013v1#bib.bib28))，在这里它可以处理图像作为输入。

###### ChatGPT。

ChatGPT（[openai_chatgpt](https://arxiv.org/html/2402.18013v1#bib.bib28)），全称为“聊天生成预训练变换器”，代表了一种聊天机器人创新。利用强大的 LLM，它使用户能够根据特定标准（如长度、格式、风格、细节水平和语言）来塑造和引导对话（[lock2022chatgpt](https://arxiv.org/html/2402.18013v1#bib.bib31)）。ChatGPT 基于 GPT-3.5（[ouyang2022training](https://arxiv.org/html/2402.18013v1#bib.bib26)）或 GPT-4（[openai2023gpt4](https://arxiv.org/html/2402.18013v1#bib.bib30)），并通过结合监督学习和强化学习来进行对话应用的微调（[gertner2023wikipedia](https://arxiv.org/html/2402.18013v1#bib.bib32)）。ChatGPT Plus（[chatgpt-openai](https://arxiv.org/html/2402.18013v1#bib.bib33)）是一个由 GPT-4 支持的 ChatGPT 版本。ChatGPT Plus 的用户可以上传图像，移动应用用户可以与聊天机器人进行对话（[roose2023chatgpt](https://arxiv.org/html/2402.18013v1#bib.bib34)）。

###### GPTs。

GPTs（[openaigpts](https://arxiv.org/html/2402.18013v1#bib.bib35)）代表了一项创新功能，允许用户定制 ChatGPT（[openai_chatgpt](https://arxiv.org/html/2402.18013v1#bib.bib28)）的版本以满足特定需求。这些个性化的 GPTs 帮助用户提高日常效率，优化特定任务的表现，并简化工作或家庭活动。用户可以与他人分享他们的创作，以促进这些专用 GPTs 的实用性。GPTs 优先考虑隐私和安全，通过确保用户在 ChatGPT 环境中对数据的控制来保护用户。与 GPTs 的互动保持保密，用户对话不会与创建者分享。

##### LLAMA 系列

LLaMA（[touvron2023llama](https://arxiv.org/html/2402.18013v1#bib.bib36)），全称为“大型语言模型 Meta AI”，是 Meta AI（[llama2023](https://arxiv.org/html/2402.18013v1#bib.bib37)）发布的一系列 LLM。由于其开放性和有效性，LLaMA 吸引了研究界的广泛关注，许多努力致力于对其不同模型版本进行微调或持续预训练，以实现新模型或工具的开发。LLaMA 系列模型的技术演变如图 [3](https://arxiv.org/html/2402.18013v1#S2.F3 "Figure 3 ‣ LLAMA Series ‣ 2.1.1\. Causal Decoder ‣ 2.1\. Decoder-only Transformer Architecture ‣ 2\. GENERAL METHODS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 所示。

![参考说明](img/a4b9b632e5e703f5e894dcd86077b86d.png)

图 3\. LLaMA 系列的简要说明。

###### LLAMA。

LLaMA ([touvron2023llama,](https://arxiv.org/html/2402.18013v1#bib.bib36))，一系列基础语言模型，参数范围从 7B 到 65B，经过数万亿个标记的训练，展示了仅使用公开可用的数据集即可训练出最先进模型的可能性，无需依赖专有和不可访问的数据集。特别地，LLaMA-13B 在大多数基准测试中优于 GPT-3 ([brown2020language,](https://arxiv.org/html/2402.18013v1#bib.bib25))（175B），而 LLaMA-65B 在当时的最佳模型 Chinchilla-70B ([hoffmann2022training,](https://arxiv.org/html/2402.18013v1#bib.bib38)) 和 PaLM-540B ([rae2021scaling,](https://arxiv.org/html/2402.18013v1#bib.bib39))中具有竞争力。

###### LLAMA2。

LLaMA2 ([llama2announcement,](https://arxiv.org/html/2402.18013v1#bib.bib40))，LLaMA 系列的下一代，通过 Meta 和 Microsoft 的合作发布。Llama 2 是一系列预训练和微调的语言模型，参数范围从 70 亿到 700 亿。Llama 2 预训练模型在 2 万亿标记上训练，相比于 Llama 具有两倍的上下文长度。LLaMA2 的发布包括模型权重和用于预训练和微调 LLaMA 语言模型（Llama Chat、Code Llama）的启动代码。

###### LLAMA2 CHAT。

LLaMA2 包括基础模型和为对话优化的模型，称为 LLaMA 2-Chat ([touvron2023llama2,](https://arxiv.org/html/2402.18013v1#bib.bib41))。Llama 2-Chat 专门针对对话用例进行优化。这些模型在大多数测试基准中优于开源聊天模型，并且根据对有用性和安全性的人工评估，可能是封闭源模型的合适替代品。

###### CODE LLAMA。

Code Llama ([rozière2023code,](https://arxiv.org/html/2402.18013v1#bib.bib42)) 包含三种不同参数数量的版本，即 7 亿参数版本、13 亿参数版本和 340 亿参数版本。在训练基础模型时，首先使用相同参数数量的 Llama 2 模型 ([llama2announcement,](https://arxiv.org/html/2402.18013v1#bib.bib40)) 初始化权重，然后在 5000 亿单词的代码数据集上进行训练。Meta 还将训练过的基础模型进一步微调为两种不同风格：Python 专家版本（增加了 1000 亿额外单词）和可以理解自然语言指令的指令微调版本。

#### 2.1.2\. 前缀解码器

前缀解码器结构（[raffel2020exploring](https://arxiv.org/html/2402.18013v1#bib.bib18)）修改了因果编码器的掩蔽机制，以便在前缀标记上实现双向注意，同时在生成的标记上保持单向注意。类似于编码器-解码器范式，这允许对前缀序列进行双向编码，并进行自回归生成输出标记，在编码和解码阶段共享相同的参数。采用前缀解码器架构的著名模型包括 U-PaLM、GLM-130B 以及其他大规模前缀编码器。该架构的示意图显示在图 [1](https://arxiv.org/html/2402.18013v1#S2.F1 "Figure 1 ‣ 2\. GENERAL METHODS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 的右侧面板中。

##### GLM

GLM（[du2021glm](https://arxiv.org/html/2402.18013v1#bib.bib43)），即通用语言模型，是一个综合预训练框架。GLM 系列模型的技术演变如图 [4](https://arxiv.org/html/2402.18013v1#S2.F4 "Figure 4 ‣ GLM ‣ 2.1.2\. Prefix Decoder ‣ 2.1\. Decoder-only Transformer Architecture ‣ 2\. GENERAL METHODS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 所示。GLM 的架构修改包括重新排列层归一化和残差连接的顺序，使用单个线性层进行输出标记预测，并将 ReLU 激活函数替换为 GeLUs。GLM 在自回归空白填充的共同框架下统一了各种任务的预训练目标，采用了混合注意力掩蔽和新型的 2D 位置编码。

![参见说明](img/9df2a699c179d7d103da938773675ba1.png)

图 4。GLM 系列的简要说明。

##### ChatGLM 系列

ChatGLM（[zeng2022glm](https://arxiv.org/html/2402.18013v1#bib.bib44)）是一个双语模型，包含问答、多轮对话和代码生成。建立在 GLM-130B（[zeng2022glm](https://arxiv.org/html/2402.18013v1#bib.bib44)）的基础上，ChatGLM 遵循 ChatGPT（[openai_chatgpt](https://arxiv.org/html/2402.18013v1#bib.bib28)）的设计原则。

###### ChatGLM-6B。

ChatGLM-6B（[zeng2022glm](https://arxiv.org/html/2402.18013v1#bib.bib44)），作为首个 ChatGLM 对话模型，建立在 GLM-130B 的训练见解基础上。它解决了 2D RoPE 位置编码实现中的问题，并采用了传统的前馈网络（FFN）结构。

###### ChatGLM2-6B。

ChatGLM2-6B ([thudm2022chatglm2-6b,](https://arxiv.org/html/2402.18013v1#bib.bib45) )，在 GLM 框架内融合了目标函数，通过 1.4 万亿中文和英文标识符进行预训练，并与人类偏好对齐。利用 FlashAttention 技术，ChatGLM2-6B 将基础模型的上下文长度从 2K（ChatGLM-6B）扩展到 32K，在对话训练中使用 8K 上下文长度。通过集成 Multi-Query Attention 技术，ChatGLM2-6B 实现了更高效的推理速度和更低的 GPU 内存使用，相较于其前身，官方模型实现的推理速度提升了 42%。

###### ChatGLM3-6B。

ChatGLM3-6B ([THUDM2023chatglm3,](https://arxiv.org/html/2402.18013v1#bib.bib46) ) 引入了一种新设计的 Prompt 格式，适应正常的多轮对话，同时原生支持复杂场景如工具调用（Function Call）、代码执行（Code Interpreter）和 Agent 任务。

### 2.2\. 仅编码器 Transformer 架构

与仅解码器和编码器-解码器 LLM 使用自回归回归不同，仅编码器 LLM 强调对输入内容的理解和生成任务特定的输出。

#### 2.2.1\. BERT 系列

BERT ([devlin2018bert,](https://arxiv.org/html/2402.18013v1#bib.bib47) )，全称为 Bidirectional Encoder Representations from Transformers，是一种基于 Transformer 架构的语言模型，以其在以前最先进模型上的显著改进而著称。BERT 系列的简要说明见图[5](https://arxiv.org/html/2402.18013v1#S2.F5 "图 5 ‣ 2.2.1\. BERT 系列 ‣ 2.2\. 仅编码器 Transformer 架构 ‣ 2\. 一般方法 ‣ LLM 基础的多轮对话系统的最新进展调查")。

![参见说明](img/ebb17c4cc7cc9df00a33d741a1bf8410.png)

图 5\. BERT 系列的简要说明。

##### BERT

BERT ([devlin2018bert,](https://arxiv.org/html/2402.18013v1#bib.bib47) ) 即双向 Transformer 编码器，是由 Google AI 语言团队推出的 LLM ([bertopensourcing,](https://arxiv.org/html/2402.18013v1#bib.bib48) )。它结合了掩蔽语言模型，使预训练能够捕捉左右上下文词之间的交互。近期的进展，如延长训练时间、跨层参数绑定和跨度掩蔽代替单个词汇，已展示了性能提升。值得注意的是，BERT 的自回归预测限制了其在生成任务中的效果。

##### RoBERTa

RoBERTa ([liu2019roberta,](https://arxiv.org/html/2402.18013v1#bib.bib49))，即经过强力优化的 BERT ([devlin2018bert,](https://arxiv.org/html/2402.18013v1#bib.bib47)) 方法，通过简单的修改改进了 BERT ([devlin2018bert,](https://arxiv.org/html/2402.18013v1#bib.bib47))，如更长时间的训练、更大的批量、移除下一句预测目标，以及动态变化的掩码模式，并采用更广泛的字节级 Byte Pair Encoding (BPE) 词汇表。然而，与 BERT 不同，RoBERTa 通过省略下一句预测 (NSP) 任务来简化其训练过程，专注于优化掩码语言模型 (MLM) 任务。这种方法增强了模型学习双向上下文信息的能力。

#### 2.2.2\. UNiLM

UNILM ([dong2019unified,](https://arxiv.org/html/2402.18013v1#bib.bib50)) 是一种统一的预训练模型，旨在通过共享参数对多种语言建模目标进行联合优化，包括双向、单向和序列到序列语言模型。该模型通过三种语言建模任务进行预训练：单向、双向和序列到序列预测。统一建模通过一个共享的 Transformer 网络实现，使用特定的自注意力掩码来控制预测的上下文条件。

### 2.3\. 编码器-解码器 Transformer 架构

传统的 Transformer 模型基于编码器-解码器架构 ([raffel2020exploring,](https://arxiv.org/html/2402.18013v1#bib.bib18))，由两个 Transformer 块构成，分别作为编码器和解码器。编码器利用堆叠的多头自注意力层对输入序列进行编码，并生成其潜在表示。与此同时，解码器对这些表示进行交叉注意力，并自回归地生成目标序列。这种架构的示意图见于图 [1](https://arxiv.org/html/2402.18013v1#S2.F1 "Figure 1 ‣ 2\. GENERAL METHODS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 的左侧面板。

#### 2.3.1\. BART

BART ([lewis2019bart,](https://arxiv.org/html/2402.18013v1#bib.bib51)) 是一种去噪自动编码器，旨在预训练序列到序列模型，结合了双向和自回归 Transformer。它采用适用于多种终端任务的序列到序列模型，利用涉及文本腐蚀和重建的两阶段预训练过程。BART 的架构基于用于神经机器翻译的标准 Transformer，可以看作是对 BERT、GPT 和其他近期预训练方案的概括。

#### 2.3.2\. Text-to-Text Transfer Transformer

T5 ([raffel2020exploring,](https://arxiv.org/html/2402.18013v1#bib.bib18))，被称为“文本到文本转换器”，采用了 Transformer 编码器-解码器结构，将每个文本处理挑战视为“文本到文本”任务——从给定输入生成新文本。这个框架确保了在所有任务中应用相同的模型、目标、训练程序和解码过程。该模型采用无监督的跨度损坏目标和多任务预训练策略。T5 建立了一个统一的模型框架，适用于各种 NLP 任务，简化了在阅读理解、摘要和文本分类任务中评估不同结构、预训练目标和数据集的过程。

## 3\. 微调

### 3.1\. 完整微调

完整微调（FFT）是神经网络适应领域的基石技术，它涉及优化所有模型参数，以将任务特定知识融入在预训练期间获得的基础架构中。FFT 在将这些模型定制化以适应专业应用中发挥了关键作用，从细致的语言理解到领域特定的任务。

FFT 基于优化预训练模型的参数。对于一个以参数$\theta$为特征的模型$M$，以及一个为特定任务设计的数据集$D$，FFT 的目标是找到使定义的损失函数$\mathcal{L}$最小化的最优参数配置$\theta^{*}$。这可以形式化地表示为：

| (1) |  | $\theta^{*}=\underset{\theta}{\mathrm{argmin}}\ \mathcal{L}(M(\theta),D),$ |  |
| --- | --- | --- | --- |

其中$\mathcal{L}(M(\theta),D)$表示损失函数，用于量化模型预测与$D$中真实结果之间的差距。

选择一个已经从各种数据中学习的预训练模型开始了这一过程。接下来的步骤包括准备一个针对具体任务的数据集。FFT 的核心在于彻底优化所有模型参数，以减少与任务相关的损失。此外，这一过程还包括通过数据增强、高级正则化和优化学习率等技术提升模型的学习效果。

FFT 因其将详细的任务特定特征融入模型的能力而受到重视，从而提升了模型的准确性和有效性。这种方法对自然语言处理、计算机视觉和预测分析等领域的显著进展做出了贡献。

尽管 FFT 在深度适应模型方面非常有效，但神经网络技术的发展催生了更多聚焦于资源节省的微调方法。例如，参数高效微调（PEFT）方法只调整一部分参数，实现了全面适应与计算需求之间的平衡，即使在资源有限的情况下也能实现模型适应。

### 3.2\. 参数高效微调

参数高效微调（PEFT）方法因其在不改变所有模型参数的情况下对预训练模型进行微调的能力而受到关注([houlsby2019parameter,](https://arxiv.org/html/2402.18013v1#bib.bib52) ; [pfeiffer2020Adapter,](https://arxiv.org/html/2402.18013v1#bib.bib53) ; [liu2021ptuning,](https://arxiv.org/html/2402.18013v1#bib.bib54) ; [hu2021lora,](https://arxiv.org/html/2402.18013v1#bib.bib55) )。本节概述了几种已开发的 PEFT 技术，重点介绍了它们的关键概念及对该领域的贡献。

#### 3.2.1\. 适配器

适配器作为一种创新的方法出现在参数高效微调领域，特别是用于将大型预训练模型适应特定任务。最初由 Houlsby 等人提出([houlsby2019parameter,](https://arxiv.org/html/2402.18013v1#bib.bib52) )，适配器被战略性地插入到预训练模型的层之间，使得原始模型参数保持不变，而适配器则学习任务特定特征的细微差别。

适配器的架构特点包括一个降维层、一个非线性激活函数和一个升维层。降维层将输入压缩到较低的维度，激活函数引入非线性以实现复杂的映射，而升维层则将转换后的表示扩展回原始的维度。其数学表示为：

| (2) |  | $\text{Adapter}(\mathbf{x})=\mathbf{U}(\text{Activation}(\mathbf{D}\mathbf{x}+% \mathbf{b}_{d}))+\mathbf{b}_{u},$ |  |
| --- | --- | --- | --- |

其中 $\mathbf{x}$ 是输入，$\mathbf{D}$ 和 $\mathbf{U}$ 分别表示降维和升维矩阵，$\mathbf{b}_{d}$ 和 $\mathbf{b}_{u}$ 是它们相应的偏置向量。

适配器通过在每层的前馈网络后插入来集成到预训练模型中。一个层的输出，在结合了适配器后，是原始层输出和适配器处理后的输出的总和。这表示为：

| (3) |  | $\text{Layer}_{\text{output}}^{\text{mod}}=\text{Layer}_{\text{output}}+\text{% Adapter}(\text{Layer}_{\text{output}}),$ |  |
| --- | --- | --- | --- |

其中 $\text{Layer}_{\text{output}}$ 是模型中一层的初始输出。

在适配器框架中，训练阶段专注于适配器的参数，其余模型参数保持静态。这种选择性训练旨在最小化任务特定的损失函数 $\mathcal{L}_{\text{task}}$，其形式为：

| (4) |  | $\theta_{\text{adapter}}^{*}=\underset{\theta_{\text{adapter}}}{\mathrm{argmin}% }\ \mathcal{L}_{\text{task}}(M_{\text{adapter}}(\theta_{\text{adapter}}),D_{% \text{task}}),$ |  |
| --- | --- | --- | --- |

其中 $\theta_{\text{adapter}}$ 表示适配器参数，$M_{\text{adapter}}$ 是包含适配器的模型，$D_{\text{task}}$ 是特定任务的数据集。

适配器在微调场景中提供了明显的优势。与完整模型微调相比，它们需要训练的参数显著较少，从而使训练过程更加资源高效。此外，适配器的模块化特性允许它们在模型中轻松插入和移除，从而能够迅速适应各种任务。重要的是，通过保持原始模型参数不变，适配器保留了在预训练过程中学到的基础知识和表示，确保了预训练模型的完整性和鲁棒性。

#### 3.2.2\. LoRA

LoRA（低秩适配，Low-Rank Adaptation） ([hu2021lora,](https://arxiv.org/html/2402.18013v1#bib.bib55)）是一种高效的微调方法，通过向特定的权重矩阵引入低秩更新来修改预训练模型。它允许在仅训练少量附加参数的情况下显著改变模型的行为。LoRA 的思想是使用低秩矩阵更新模型的权重，这大大减少了需要微调的参数数量。对于权重矩阵 $\mathbf{W}\in\mathbb{R}^{m\times n}$，低秩更新由以下公式给出：

| (5) |  | $\Delta\mathbf{W}=\mathbf{B}\mathbf{A},$ |  |
| --- | --- | --- | --- |

其中 $\mathbf{B}\in\mathbb{R}^{m\times r}$ 和 $\mathbf{A}\in\mathbb{R}^{r\times n}$ 是低秩矩阵，$r$ 是比 $m$ 和 $n$ 小得多的秩。

实际上，LoRA 被应用于神经网络的特定层，例如变换器模型中的注意力层和前馈层 ([vaswani2017attention,](https://arxiv.org/html/2402.18013v1#bib.bib17))。更新后的权重矩阵是：

| (6) |  | $\mathbf{W}^{\prime}=\mathbf{W}+\Delta\mathbf{W},$ |  |
| --- | --- | --- | --- |

其中 $\mathbf{W}^{\prime}$ 是在微调和推理过程中使用的新权重矩阵。

LoRA 提供了几个优势：通过仅更新少量参数，LoRA 减少了计算和内存需求。它可以应用于网络的各种层，从而进行有针对性的修改。由于原始权重没有被丢弃，LoRA 保持了在预训练过程中学到的丰富表示。

已经提出了几个 LoRA 的扩展以进一步提高其效率。例如，量化 LoRA（QLoRA） ([dettmers2023qlora,](https://arxiv.org/html/2402.18013v1#bib.bib56)）是高效微调的一个进展。它结合了 LoRA 的原则和 4 位量化，大大减少了内存占用。QLoRA 使得在有限的硬件资源上微调极其庞大的模型成为可能，同时保持任务性能。

#### 3.2.3\. 指令微调

指令微调（IFT） ([wei2021finetuned,](https://arxiv.org/html/2402.18013v1#bib.bib57) ) 是一种通过利用特定任务的指令来增强预训练语言模型（PLMs）能力的方法。这种技术使 PLMs 更好地理解和执行指令，从而提高其在各种任务中的表现。

IFT 的核心思想涉及在一个数据集中对预训练的语言模型（LM）进行微调，每个数据点包括一个特定的指令及其相关的输入-输出对。目标是使 LM 能够理解并遵循指令，以生成期望的输出。

IFT 对于需要细致理解和执行复杂指令的任务尤其有利。通过保留原始模型架构，它提供了一种有效的方式来扩展预训练语言模型（PLMs）在新任务和领域中的适用性，而无需进行广泛的架构修改。

### 3.3. 缓解微调不稳定性

微调预训练模型，特别是在深度学习应用中，常常会遇到不稳定性问题，导致性能不佳 ([zhang2020revisiting,](https://arxiv.org/html/2402.18013v1#bib.bib58) ; [mosbach2021on,](https://arxiv.org/html/2402.18013v1#bib.bib59) )。这些不稳定性表现为损失函数地形不规律、收敛困难以及对超参数设置的敏感性。一个常见问题是表示崩溃，即模型的表示在微调过程中变得不那么有表达力 ([aghajanyan2020better,](https://arxiv.org/html/2402.18013v1#bib.bib60) )。研究人员已经开发了各种策略来稳定微调过程，并提高微调模型的鲁棒性 (dodge2020fine; [mosbach2021on,](https://arxiv.org/html/2402.18013v1#bib.bib59) )。

Aghajanyan 等人 ([aghajanyan2020better,](https://arxiv.org/html/2402.18013v1#bib.bib60) ) 提出了在微调预训练模型过程中缓解表示崩溃的方法。他们通过正则化微调（R3F）和正则化与重新参数化微调（R4F）引入了稳健表示，其中前者向损失函数中添加了正则化项，后者通过引入重新参数化来扩展 R3F。这些方法的形式化为：

| (7) |  | R3F 损失: | $\displaystyle\mathcal{L}_{\text{R3F}}=\mathcal{L}_{\text{original}}+\lambda% \cdot\mathcal{R}(\theta),$ |  |
| --- | --- | --- | --- | --- |
| (8) |  | R4F 损失: | $\displaystyle\mathcal{L}_{\text{R4F}}=\mathcal{L}_{\text{original}}+\lambda% \cdot(\mathcal{R}(\theta)+\mathcal{R}(\text{Reparam}(\theta))),$ |  |

其中 $\mathcal{L}_{\text{original}}$ 是原始损失函数，$\lambda$ 是正则化强度，$\mathcal{R}$ 是正则化项，Reparam 是重新参数化函数。

Jiang 等人（[jiang2019smart,](https://arxiv.org/html/2402.18013v1#bib.bib61)）提出了 SMART（Smoothness-inducing Adversarial Regularization for Multitask Training），通过正则化优化来增强预训练模型的微调。它使用平滑性诱导对抗正则化来控制模型复杂性，并通过 Bregman Proximal Point Optimization 稳定更新。该方法旨在提高 PLMs 微调的鲁棒性和效率，解决过拟合问题，并提升 NLP 任务的泛化能力。

| (9) |  | $\min_{\theta}\mathbb{E}_{(x,y)\sim\mathcal{D}}\left[\max_{\delta}\mathcal{L}(f(x+\delta;\theta),y)-\rho\cdot\|\delta\|_{2}^{2}\right],$ |  |
| --- | --- | --- | --- |

其中$\delta$表示对抗扰动，$\rho$在对抗目标和正则化之间进行平衡，$f$是模型的预测函数。

Zhu 等人（[zhu2019freelb,](https://arxiv.org/html/2402.18013v1#bib.bib62)）提出了 Free Large-Batch Adversarial Training（FreeLB），这是一种对抗训练算法，旨在提高 PLMs 的鲁棒性和泛化能力（[zhu2019freelb,](https://arxiv.org/html/2402.18013v1#bib.bib62)）。它通过将对抗扰动添加到词嵌入中并最小化对抗风险来增强训练。

| (10) |  | $\min_{\theta}\frac{1}{N}\sum_{i=1}^{N}\max_{\delta_{i}}\mathcal{L}(f(x_{i}+\delta_{i};\theta),y_{i})-\rho\cdot\|\delta_{i}\|_{2}^{2},$ |  |
| --- | --- | --- | --- |

其中$N$是批量大小，$\delta_{i}$是对抗扰动，$\rho$则在原始损失与对抗项之间进行平衡。

## 4\. Prompt Engineering

Prompt 工程在帮助预训练语言模型（PLMs）理解特定任务的领域中获得了显著关注。Prompt 工程可以分为两种方法：Prompt Tuning 和 Tuning-free Prompting，本节将讨论这两种方法。

### 4.1\. Prompt Tuning

Prompt Tuning 涉及修改预训练模型的参数或调整额外的 prompt 相关参数，以增强预训练模型对下游任务的适应能力。在这方面，一个突出的方法是 Pattern-Verbalizer-Pair（PVP）结构，该结构最初由（[schick2020exploiting,](https://arxiv.org/html/2402.18013v1#bib.bib63)）提出。随后，Prompt Tuning 方法大多建立在 PVP 框架之上。如图 [6](https://arxiv.org/html/2402.18013v1#S4.F6 "Figure 6 ‣ 4.1\. Prompt Tuning ‣ 4\. Prompt Engineering ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 所示，Gao 等人（[gao2020making,](https://arxiv.org/html/2402.18013v1#bib.bib64)）证明了模板和标签的选择可以导致最终准确性上的显著差异。因此，当前研究主要集中在如何选择或构建合适的 Patterns 和 Verbalizers。Prompt 的设计可以分为离散提示和连续提示。

![参见说明](img/09755212ad9f9dc9dc51acdf4157d046.png)

图 6\. 模板和标签词对提示调优的影响。

#### 4.1.1\. 离散提示

之前的工作主要集中在离散提示的探索，也称为硬提示，这些提示通常对应于可读的语言短语。离散模板的词嵌入在训练过程中保持不变，不会引入任何新的参数到语言模型中。在接下来的部分，我们将详细概述为此目的提出的几种方法：

##### D1: 模式利用训练

模式利用训练（PET）（[schick-schutze-2021-exploiting,](https://arxiv.org/html/2402.18013v1#bib.bib65)）通过手动生成 PVP 内容 p = (*P*, *v*) 来构建一个提示集，其中 $P$ 是一个将 $x$ 作为输入并输出包含一个掩码标记的短语或句子 $P(x)\in V^{*}$ 的函数。$v$ 是一个注入函数 $\mathcal{L}\rightarrow V$，将每个标签映射到掩码语言模型词汇 $M$ 中的一个词。PET 可以被表述为：

| (11) |  | $\displaystyle s_{p}(l\ &#124;\ x)=M(v(l)\ &#124;\ P(x)),$ |  |
| --- | --- | --- | --- |
| (12) |  | $\displaystyle q_{p}(l\ &#124;\ x)=\frac{e^{s_{p}(l&#124;x)}}{{\textstyle\sum_{l^{\prime}% \in\mathcal{L}}e^{s_{p}(l^{\prime}&#124;x)}}},$ |  |

其中 $s_{p}$ 是标签 $l\in\mathcal{L}$ 的得分，$q_{p}$ 是通过 softmax 计算的标签概率分布。然后，$q_{p}(l\ |\ x)$ 和真实的（独热编码）之间的交叉熵被用作微调 $M$ 的损失函数。

##### D2: LM-BFF

寻找合适的提示是繁琐且容易出错的，这需要领域专业知识和对自然语言处理的理解。即使投入大量努力，手动提示也可能效果不佳。因此，LM-BFF ([gao2020making,](https://arxiv.org/html/2402.18013v1#bib.bib64) ) 自动生成提示，包括修剪的穷举搜索以识别最佳的标签词，并利用 T5 模型自动生成模板（[raffel2020exploring,](https://arxiv.org/html/2402.18013v1#bib.bib18)）。给定固定模板 $T(x)$，可以基于初始 $L$ 的条件似然性构造一个修剪的 $V_{c}\subset V$ 的前 $k$ 个词汇集，公式化为：

| (13) |  | $\displaystyle{}_{v\in V}^{{Top-k}}\left\{\sum_{x_{in}\in D_{train}^{c}}\log{P_% {\mathcal{L}}([MASK]=v\ &#124;\ T(x_{in}))}\right\},$ |  |
| --- | --- | --- | --- |

其中 $P_{\mathcal{L}}$ 表示 $\mathcal{L}$ 的输出概率分布。

##### D3: 规则提示调优

规则提示调优（PTR）（[han2022ptr,](https://arxiv.org/html/2402.18013v1#bib.bib66)）可以应用逻辑规则将少量手动创建的子提示自动组合成最终的任务特定提示。以关系分类为例，给定句子 $x=\{...e_{s}...e_{o}...\}$，其中 $e_{s}$ 和 $e_{o}$ 分别是主语实体和宾语实体，$e_{s}$ 和 $e_{o}$ 的子提示模板和标签词集可以形式化为：

| (14) |  |  | $\displaystyle T_{e_{s}/e_{o}}=``x\ the\ [MASK]\ e_{s}/e_{o}&quot;,$ |  |
| --- | --- | --- | --- | --- |
|  |  | $\displaystyle V_{e_{s}/e_{o}}=\{``person&quot;,``organization&quot;,...\},$ |  |

$e_{s}$ 和 $e_{o}$ 之间的子提示可以形式化为：

| (15) |  |  | $\displaystyle T_{e_{s}/e_{o}}=``x\ e_{s}\ [MASK]\ e_{o}&quot;,$ |  |
| --- | --- | --- | --- | --- |
|  |  | $\displaystyle V_{e_{s}/e_{o}}=\{``^{\prime}s\ parent\ was&quot;,``was\ born\ in&quot;,..% .\},$ |  |

通过汇聚子提示，完整的提示如下，

| (16) |  |  | $\displaystyle T=``x\ the\ [MASK]_{1}\ e_{s}\ [MASK]_{2}\ the\ [MASK]_{3}\ e_{o% }&quot;,$ |  |
| --- | --- | --- | --- | --- |
|  |  | $\displaystyle V_{[MASK]_{1}}=\{``person&quot;,``organization&quot;,...\},$ |  |
|  |  | $\displaystyle V_{[MASK]_{2}}=\{``^{\prime}s\ parent\ was,``was\ born\ in&quot;,...\},$ |  |
|  |  | $\displaystyle V_{[MASK]_{3}}=\{``person&quot;,``organization&quot;,...\},$ |  |

PTR 的最终学习目标是最大化

| (17) |  | $\displaystyle\frac{1}{&#124;X&#124;}\sum_{x\in X}\log{\prod_{j=1}^{n}}p\left([MASK]_{j}=% \phi_{j}(y)&#124;T(x)\right),$ |  |
| --- | --- | --- | --- |

其中 $\phi_{j}(y)$ 用于将类 $y$ 映射到 $j$-th 掩码位置 $[MASK]_{j}$ 的标签词集 $V_{[MASK]_{j}}$。

##### D4: 知识丰富的提示调优

知识丰富的提示调优（KPT）（[hu2021knowledgeable](https://arxiv.org/html/2402.18013v1#bib.bib67)）使用外部知识库（KBs）为每个标签生成一组标签词。这些扩展的标签词不仅是彼此的同义词，还涵盖了不同的粒度和视角，因此比类名更全面和客观。然后，提出了改进方法来处理生成标签词中的噪声。这保留了可以用于微调 PLMs 的高质量词汇，并展示了上下文学习（ICL）的有效性。

#### 4.1.2\. 连续提示

连续提示不是创建可读的语言短语，而是将提示转换为连续向量。连续提示具有自己可以基于下游任务的训练数据进行调整的参数。

##### C1: P-调优

P-调优（[liu2023gpt](https://arxiv.org/html/2402.18013v1#bib.bib68)）是通过使用连续提示来实现提示调优的早期尝试。与离散提示中的可读模板不同，P-调优使用连续提示嵌入 $p_{i}$ 来构建提示模板：

| (18) |  | $\displaystyle T=\{[P_{0:i}],x,[p_{(i+q:j)}],y,[P_{j+1}:k]\},$ |  |
| --- | --- | --- | --- |

然后利用额外的嵌入函数 $f:[p_{i}]\to h_{i}$ 将模板映射到：

| (19) |  | $\displaystyle\{h_{0},...,h_{i},e(x),h_{(i+1)},...h_{j},e(y),h_{j+1},...j_{k}\},$ |  |
| --- | --- | --- | --- |

使用函数 $f$，任务损失函数可以通过更新嵌入 $\{P_{i}\}_{i=1}^{k}$ 来优化。

##### C2: 前缀调优

前缀调整（[li2021prefix,](https://arxiv.org/html/2402.18013v1#bib.bib69)）冻结 PLMs 的参数，仅优化前缀参数。因此，我们只需为每个任务存储前缀，使前缀调整具有模块化和空间效率。给定一个可训练的前缀矩阵 $M_{\phi}$ 和一个由 $\theta$ 参数化的固定预训练 LM，训练目标与完整微调的目标相同：

| (20) |  | $\displaystyle\max_{\phi}{\log{P_{\phi}(y&#124;x)}=\max_{\phi}\sum_{i\in Y_{idx}}% \log{P_{\phi}(z_{i}&#124;h_{<i})}},$ |  |
| --- | --- | --- | --- |

其中 $h_{<i}$ 是时间步 $i$ 所有神经网络层的连接。如果 $i\in P_{idx}$，则 $h_{i}=P_{\theta}[i,:]$；否则，$h_{i}=LM_{\phi}(z_{i},h_{<i})$。

Lester 等人提出了提示调整（[lester2021power,](https://arxiv.org/html/2402.18013v1#bib.bib70)），这可以看作是前缀调整的一种简化。它大大减少了参数数量，并首次证明仅使用提示调整也是具有竞争力的。

![参考说明](img/8f180bf630ae2b3e721f8b0e459b2f7a.png)

图 7\. 从 P-tuning 到 P-tuning v2\. ([liu2021p,](https://arxiv.org/html/2402.18013v1#bib.bib71))

##### C3: P-tuning V2

P-tuning v2 ([liu2021p,](https://arxiv.org/html/2402.18013v1#bib.bib71)) 是前缀调整（[li2021prefix,](https://arxiv.org/html/2402.18013v1#bib.bib69)）和软提示混合（[qin2021learning,](https://arxiv.org/html/2402.18013v1#bib.bib72)）的实现。如图[7](https://arxiv.org/html/2402.18013v1#S4.F7 "图 7 ‣ C2: 前缀调整 ‣ 4.1.2\. 连续提示 ‣ 4.1\. 提示调整 ‣ 4\. 提示工程 ‣ 最近进展的调查")所示，与 P-tuning 相比，它不仅具有更多可调的任务特定参数（从 0.01%到 0.1%-3%），以便在参数高效的同时允许更多的每任务容量，还将提示添加到更深的层次上，对模型预测有更直接的影响。P-tuning v2 在所有规模上始终与微调相当，但只需 0.1%的任务特定参数，相比微调证明了提示调整可以有效地帮助 PLMs 适应下游任务。

### 4.2\. 无调整提示

无调整提示直接生成答案，而不修改 PLMs 的参数。这些可以选择性地利用响应提示来增强输入，以前的研究探讨了提示对 PLMs 生成效果的影响，并提供了许多创建提示的技巧。主流的无调整提示方法包括 ICL 和链式思维（CoT）。

#### 4.2.1\. 上下文学习

ICL 使用多个输入-输出示例对来指导 PLMs 生成所需的响应，这一方法最早与 GPT-3 一起提出。ICL 是一种有效的方法，因为无需调优参数，图 [8](https://arxiv.org/html/2402.18013v1#S4.F8 "图 8 ‣ 4.2.1\. 上下文学习 ‣ 4.2\. 无需调优的提示 ‣ 4\. 提示工程 ‣ LLM 基础多轮对话系统的最新进展调查") 中展示了 ICL 的一个示例提示。

以往研究表明，ICL 可以从上下文示例中获得目标任务的标签空间、输入文本的分布和输入-标签对应关系。上下文提示与目标任务之间的相似性也显著影响 ICL 的表现。通常，当上下文提示在嵌入空间中与测试样本接近时，性能往往会提高 ([liu2021makes,](https://arxiv.org/html/2402.18013v1#bib.bib73))。上下文提示本身的排列也对 ICL 的性能产生重要影响，这在小规模模型中尤为明显 ([lu2021fantastically,](https://arxiv.org/html/2402.18013v1#bib.bib74))。因此，许多研究人员致力于探索构建高性能上下文提示的方法，并提出了许多基于 ICL 的方法 ([chen2022improving,](https://arxiv.org/html/2402.18013v1#bib.bib75); [chen2021meta,](https://arxiv.org/html/2402.18013v1#bib.bib76); [min2021metaicl,](https://arxiv.org/html/2402.18013v1#bib.bib77)) 以更好地设计上下文提示。

![参考说明](img/98ba304d005bc1846e6f37393212e858.png)

图 8\. ICL 和 CoT 的示例。

#### 4.2.2\. 思维链

CoT ([wei2022chain,](https://arxiv.org/html/2402.18013v1#bib.bib78)) 通过模拟逐步思考过程来改进在各种算术、常识和符号推理任务上的表现。图 [8](https://arxiv.org/html/2402.18013v1#S4.F8 "图 8 ‣ 4.2.1\. 上下文学习 ‣ 4.2\. 无需调优的提示 ‣ 4\. 提示工程 ‣ LLM 基础多轮对话系统的最新进展调查") 中展示了 CoT 的一个示例提示。零-shot CoT ([kojima2022large,](https://arxiv.org/html/2402.18013v1#bib.bib79)) 是一种经典的 CoT 方法，通过在不同任务中使用相同的提示“让我们一步步思考”来指导模型进行推理和生成结果。另一种经典方法是 Least-to-Most ([zhou2022least,](https://arxiv.org/html/2402.18013v1#bib.bib80))，它将目标问题分解为一系列简单的子问题，逐步解决。

一种更为广泛的方法是向模型提供一系列设计用于逐步推理的 CoT 提示，以指导其思考。类似于 ICL，提示的选择对生成结果有显著影响，这促使研究人员通过投票或自动生成提示等方法进行大量努力以识别最佳提示（[zhang2022automatic,](https://arxiv.org/html/2402.18013v1#bib.bib81) ; [shum2023automatic,](https://arxiv.org/html/2402.18013v1#bib.bib82)）。此外，近期研究还集中于探索 CoT 在多模态（[zhang2023multimodal,](https://arxiv.org/html/2402.18013v1#bib.bib83)）和多语言（[huang2023not,](https://arxiv.org/html/2402.18013v1#bib.bib84)）场景中的应用。

## 5\. 基于 LLM 的任务导向对话系统

TOD 系统通过互动对话帮助用户实现特定领域相关目标，如酒店预订或餐馆查询。由于其显著的实用性，这项技术近年来引起了研究人员的越来越多关注。一般来说，TOD 可以分为基于管道的 TOD 和端到端 TOD。在这一节中，我们将对基于 LLM 的 TOD 进行全面介绍。

如图[9](https://arxiv.org/html/2402.18013v1#S5.F9 "Figure 9 ‣ 5.1\. 基于管道的方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ 基于 LLM 的多轮对话系统的最新进展综述")所示，基于管道的 TOD 系统包括四个相连的模块：（1）NLU，用于提取用户意图和填充槽位；（2）对话状态跟踪（DST），基于管道 TOD 中的关键模块，用于根据 NLU 模块的输出和对话的历史输入跟踪当前轮次的对话状态；（3）策略学习（PL），根据 DST 模块生成的对话状态确定后续行动；（4）NLG，基于管道 TOD 系统的最终模块，将 PL 模块生成的对话行动转化为可理解的自然语言。对话管理器（DM）是基于管道 TOD 系统的中央控制器，由 DST 模块和 PL 模块组成。

### 5.1\. 基于管道的方法

![参见说明文字](img/bddef62066bb2dfd54c6b8861a89af14.png)

图 9\. 基于管道的任务导向对话框架。

由于管道式 TOD 系统中的每个模块是独立训练的，任何模块在适应子任务方面的失败都可能导致整个系统的性能严重下降。同时，由于管道式 TOD 系统顺序解决所有子任务，模块之间的错误会积累，从而导致错误传播问题。然而，由于管道式 TOD 系统中的每个模块是单独操作的，确保了输入和输出的一致性，因此可以方便地在管道式 TOD 系统中互换各个模块。随着 PLM 的发展，通过不同方法微调的大规模语言模块可以轻松访问并无缝集成到 TOD 系统中，以替换系统中的模块，这使得用户能够轻松地将系统适配到目标领域的子任务中。

#### 5.1.1\. 自然语言理解

NLU 模块从用户提供的自然语言输入中识别和提取信息，如用户意图和槽位值。一般来说，NLU 模块的输出如下：$Un=(In,Zn)$，其中 $In$ 是检测到的用户意图，而 $Zn$ 是槽位-值对。例如，在餐厅推荐任务中，用户意图是“find-restaurant”，领域是“restaurant”。槽位填充可以被视为一个序列分类任务。例如，用户输入一条消息：“我在东边找一家昂贵的餐馆”，NLU 模块读取此输入并生成以下槽位-值对：{restaurant-area: east, restaurant-pricerange: expensive}。

##### 意图检测

基于深度学习的方法 ([deng2012use,](https://arxiv.org/html/2402.18013v1#bib.bib85) ; [tur2012towards,](https://arxiv.org/html/2402.18013v1#bib.bib86) ) 被广泛用于解决意图检测任务。特别是，许多基于神经网络的方法取得了令人满意的成果。然而，随着 LLM 的发展，大量研究人员将 LLM 应用于 TOD 任务，许多方法取得了很好的表现。Comi 等人提出了一种基于预训练 BERT 模型的管道式意图检测方法 ([comi2023zero,](https://arxiv.org/html/2402.18013v1#bib.bib87) )。他们首先使用零样本方法从一个预训练的 BERT 模型中提取一组潜在意图作为发言意图分类问题的候选类别。Parikh 等人 ([parikh2023exploring,](https://arxiv.org/html/2402.18013v1#bib.bib88) ) 使用提示来进行意图分类任务的 GPT-3 和 Flan-T5-XXL 模型。他们还使用 PEFT 方法对 LLM 进行微调，并在意图分类任务中展示了卓越的表现。为了解决仅通过 LLM 上下文提示增强无法改善性能的问题，Lin 等人 ([lin2023selective,](https://arxiv.org/html/2402.18013v1#bib.bib89) ) 引入了一种基于点对点 V 信息的新方法，并成功提高了基于 LLM 的意图检测任务的性能。

插槽填充任务为每个词子序列标注不同的标签。因此，插槽填充任务可以视为序列分类任务。Coope 等人提出了 Span-ConveRT ([coope2020span,](https://arxiv.org/html/2402.18013v1#bib.bib90))，这是一个用于对话插槽填充任务的模型，通过整合在大型预训练对话模型中编码的对话知识，展示了在少样本场景中的优异表现。Siddique 等人 ([siddique2021linguistically,](https://arxiv.org/html/2402.18013v1#bib.bib91)) 提出了一个零样本插槽填充模型 LEONA，该模型利用预训练的 LLM 提供上下文化的词表示，这些表示捕捉了基于使用上下文的复杂句法和语义特征，并利用这些词表示为每个词生成特定插槽的预测。

##### 联合意图检测和插槽填充

一些研究将意图检测和插槽填充结合成一个联合意图检测和插槽填充模块，这促进了意图检测任务和插槽填充任务之间的双向信息共享。Chen 等人 ([chen2019bert,](https://arxiv.org/html/2402.18013v1#bib.bib92)) 基于 NLU 数据集对 LLM 进行微调，他们的实验结果表明，基于微调 LLM 的联合 NLU 模块优于分开的 NLU 模块和基于未调优 LLM 的 NLU 模块。Nguyen 等人 ([nguyen2023cof,](https://arxiv.org/html/2402.18013v1#bib.bib93)) 提出了 CoF-CoT 方法，该方法将 NLU 任务拆解为多个推理步骤。LLM 通过学习获取和利用关键概念，能够在不同粒度上增强解决 NLU 任务的能力。

#### 5.1.2\. 对话状态跟踪

如图 [9](https://arxiv.org/html/2402.18013v1#S5.F9 "Figure 9 ‣ 5.1\. Pipeline-based Methods ‣ 5\. LLM Based Task-oriented Dialogue Systems ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 所示，DST 和 PL 组成了对话管理器（DM）模块，这是管道式 TOD 系统的中央控制器。作为 DM 模块的第一个模块，DST 通过预测当前回合 $t$ 的插槽-值对来跟踪当前对话状态。在 TOD 任务中，对话状态 $\mathcal{B}_{t}$ 记录了直到回合 t 的整个对话历史。DST 模块以插槽-值对的形式记录用户的目标，例如，在酒店预订任务中，回合 $t$ 的对话状态是 $\mathcal{B}_{t}={(hotel-bookstay,5),(hotel-bookday,Friday),(hotel-bookname,% Hiltion)}$。

DST 方法可以分为静态本体 DST 模型和动态本体 DST 模型。静态本体 DST 模型从预定义的槽值对中预测对话状态，而动态本体 DST 模型则从不固定的槽值集合中预测对话状态。已经提出了许多静态本体 DST 模型（[balaraman2019scalable,](https://arxiv.org/html/2402.18013v1#bib.bib94) ; [zhong2018global,](https://arxiv.org/html/2402.18013v1#bib.bib95) ; [lee2019sumbt,](https://arxiv.org/html/2402.18013v1#bib.bib96)）。然而，大多数基于 LLM 的 DST 方法都基于动态本体 DST 模型，这些模型从不固定的槽值对中跟踪对话状态。例如，SAVN 和 MinTL（[wang2020slot,](https://arxiv.org/html/2402.18013v1#bib.bib97) ; [lin2020mintl,](https://arxiv.org/html/2402.18013v1#bib.bib98)）专注于创建 LLM 可以有效应用的方法或框架。这些方法取得了具有竞争力的结果，并允许用户即插即用预训练的序列到序列模型来解决 DST 任务。胡等人（[hu2022context,](https://arxiv.org/html/2402.18013v1#bib.bib99)）提出了 IC-DST，一个基于 ICL 的零样本和少样本 DST 框架。IC-DST 从标记对话中检索几个最相似的回合作为提示，然后将其输入 LLM，以产生当前回合的对话状态变化。冯等人提出了 LDST（[feng2023towards,](https://arxiv.org/html/2402.18013v1#bib.bib100)），一个利用 LLaMa 模型的 DST 框架。LDST 首先创建一个指令调整数据集，并在此数据集上微调 LLaMa 模型。随后，LDST 通过构建和输入输出提示来指导 LLaMa 生成准确的响应。

#### 5.1.3\. 策略学习

作为 DM 模块的第二部分，PL 模块负责根据 DST 模块中当前回合 t 的对话状态 $\mathcal{B}_{t}$ 生成适当的下一步系统动作。因此，PL 模块的任务可以表述为学习一个映射函数：

|  | $f:\mathcal{B}_{t}\to a_{i}\in\mathcal{A},$ |  |
| --- | --- | --- |

其中 $\mathcal{A}$ 是动作集 $\mathcal{A}=\left\{a_{1},\ \dots,\ a_{n}\right\}$。

TOD 系统中的 PL 模块可以从两个层面进行处理：对话行为（DA）层面和词级对话策略。DA 层面的对话策略的目标是生成如‘Inform’:（‘people’，‘area’）这样的对话行为，然后在 NLG 模块中转换为可读的输出。强化学习方法（[takanobu2020multi,](https://arxiv.org/html/2402.18013v1#bib.bib101)；[wang2020task,](https://arxiv.org/html/2402.18013v1#bib.bib102)；[gordon2020learning,](https://arxiv.org/html/2402.18013v1#bib.bib103)）广泛应用于 DA 层面的 PL 任务。词级对话 PL 模块结合了 PL 和 NLG 模块，因为它通过选择一串词语生成可读的句子。通过这种方式，词级对话 PL 任务可以被视为序列到序列的生成任务。由于 LLM 在解决序列到序列任务方面表现优异，因此提出了众多基于 LLM 的词级对话 PL 方法。Chen 等人（[chen2019semantically,](https://arxiv.org/html/2402.18013v1#bib.bib104)）使用 BERT 模型作为解码器。Li 等人（[li2021retrieve,](https://arxiv.org/html/2402.18013v1#bib.bib105)）将 BERT 模型用于上下文感知的检索模块。许多研究者（[budzianowski2019hello,](https://arxiv.org/html/2402.18013v1#bib.bib106)；[hosseini2020simple,](https://arxiv.org/html/2402.18013v1#bib.bib107)；[jang2022gpt,](https://arxiv.org/html/2402.18013v1#bib.bib108)）对 GPT-2 模型进行微调，并将微调后的模型应用于词级对话 PL 任务。Ramachandran 等人（[ramachandran2021causal,](https://arxiv.org/html/2402.18013v1#bib.bib109)）对 BART 进行微调，He 等人（[he2022galaxy,](https://arxiv.org/html/2402.18013v1#bib.bib110)）对 UniLM 进行微调。Yu 等人（[yu2023prompt,](https://arxiv.org/html/2402.18013v1#bib.bib111)）提出了一种基于提示的方法，通过提示 LLM 作为策略先验来解决 PL 任务。

#### 5.1.4\. 自然语言生成

NLG，包括数据到文本生成和文本到文本生成，是为特定目的生成自然语言文本的过程。在基于管道的任务导向对话系统中，NLG 是最后一个模块，负责将 PL 模块生成的对话动作转换为可读的自然语言。例如，对于对话动作：“Inform: (‘people’)”，NLG 模块将其转换为可读的句子“How many people are planning to check in?” 传统的 NLG 模块基于管道结构，可以分为文本规划模块、句子规划模块和语言规划模块 ([REITER_DALE_1997,](https://arxiv.org/html/2402.18013v1#bib.bib112) )。随着深度学习方法的发展，研究人员引入了基于神经网络的端到端 NLG 方法 ([wen2015stochastic,](https://arxiv.org/html/2402.18013v1#bib.bib113) ; [wen2015semantically,](https://arxiv.org/html/2402.18013v1#bib.bib114) ; [zhou2016context,](https://arxiv.org/html/2402.18013v1#bib.bib115) ) 来解决最近的 NLG 任务。许多近期的工作提出了使用 LLM 解决 NLG 任务，因为基于管道的 TOD 系统中的 NLG 任务是序列到序列任务，可以通过 LLM 高效解决。例如，Peng 等人提出了 SC-GPT ([peng2020few,](https://arxiv.org/html/2402.18013v1#bib.bib116) ) 模型，该模型在大量标注的 NLG 语料库上进行预训练，并在具有有限领域标签的数据集上进行微调，以适应新领域。Chen 等人 ([chen2019few,](https://arxiv.org/html/2402.18013v1#bib.bib117) ) 微调了 PLMs 的其他参数，并保持预训练的词嵌入固定，以增强模型的泛化能力。Baheti 等人 ([baheti2020fluent,](https://arxiv.org/html/2402.18013v1#bib.bib118) ) 将基于 BERT 的分类器整合到端到端 NLG 系统中，以从候选响应中识别最佳答案。Qian 等人 ([qian2022controllable,](https://arxiv.org/html/2402.18013v1#bib.bib119) ) 通过利用前缀调整方法提高了 GPT-2 在处理 NLG 任务中的性能。

### 5.2. 端到端方法

![参考说明](img/f9f64cbbbe4c4075fd8c8ed9844b1869.png)![参考说明](img/633096cbd19f08505923531136a91526.png)

图 10. 模块化的端到端任务导向对话系统 (a) 和完全端到端任务导向对话系统 (b)。

如图 [10](https://arxiv.org/html/2402.18013v1#S5.F10 "图 10 ‣ 5.2\. 端到端方法 ‣ 5\. 基于 LLM 的任务导向对话系统 ‣ 关于基于 LLM 的多轮对话系统的最新进展的调查") 所示，端到端 TOD 系统可以分为模块化端到端 TOD 系统和完全端到端 TOD 系统。尽管模块化端到端 TOD 系统通过分离的模块生成响应，这与基于管道的 TOD 系统类似，但模块化端到端 TOD 系统同时训练所有模块并优化所有模块的参数。端到端 TOD 系统基于相应的知识库 $\mathcal{KB}$ 和对话历史 $\mathcal{H}=\left(u_{1},s_{1}\right),\left(u_{2},s_{2}\right),\ldots,\left(u_{% n-1},s_{n-1}\right)$ 生成对话系统响应 $\mathcal{S}$，其中 $u$ 是用户输入，$s$ 是系统回答：

| (21) |  | $\mathcal{S}=\text{ 端到端 TOD }(\mathcal{H},\mathcal{KB}).$ |  |
| --- | --- | --- | --- |

LLMs 在 ODD 任务中取得了显著成功。然而，由于缺乏大量的 TOD 任务训练数据，与训练完全基于 LLM 的端到端 TOD 模型相关的研究仍然相对有限。因此，大多数现有的基于 LLM 的端到端 TOD 方法都基于模块化端到端 TOD 系统。

简单任务导向对话 (SimpleTOD) ([hosseini2020simple,](https://arxiv.org/html/2402.18013v1#bib.bib107) ) 是一种基于单一因果语言模型训练所有子任务的端到端 TOD 方法。SimpleTOD 在训练 LLM 时采用的方法，作为利用此类模型解决 TOD 任务的成功案例。给定串联 $x^{t}=[\mathcal{H}_{t},\mathcal{B}_{t},\mathcal{D}_{t},\mathcal{A}_{t},\mathcal{S}_{t}]$，其中 $\mathcal{H}_{t}$、$\mathcal{B}_{t}$、$\mathcal{D}_{t}$、$\mathcal{A}_{t}$ 和 $\mathcal{S}_{t}$ 分别是对话历史 $\mathcal{H}$、信念状态 $\mathcal{B}$、数据库查询结果 $\mathcal{D}$、对话动作 $\mathcal{A}$ 和系统回答 $\mathcal{S}$ 在轮次 $t$ 的值。数据集 $D=\left\{x^{1},\ldots,x^{\mid D\mid}\right\}$ 上的联合概率 $p(x)$ 和负对数似然 $\mathcal{L}(D)$ 可以表示为：

| (22) |  | $p(x)=\prod_{i=1}^{n}p\left(x_{i}\mid x_{<i}\right),$ |  |
| --- | --- | --- | --- |
| (23) |  | $\mathcal{L}(D)=-\sum_{t=1}^{\mid D\mid}\sum_{i=1}^{n_{t}}\log p_{\theta}\left(x_{i}^{t}\mid x_{<i}^{t}\right),$ |  |

其中 $n_{t}$ 是 $x^{t}$ 的长度，$\theta$ 是神经网络中的参数，该网络被训练以最小化 $\mathcal{L}(D)$。

彭等人提出了 Soloist ([peng2021soloist,](https://arxiv.org/html/2402.18013v1#bib.bib120))，这是一种使用迁移学习和机器教学构建端到端 TOD 系统的方法。Soloist 的训练过程与 SimpleTOD 相似。然而，Soloist 对每个对话轮次的数据格式进行了改进，不再需要对话动作 $\mathcal{A}$。训练数据中的每个对话轮次可以表示为 $x=[\mathcal{H},\mathcal{B},\mathcal{D},\mathcal{S}]$。Soloist 的完整预训练目标被分为三个子任务：信念预测、基于上下文的响应生成和基于上下文的响应生成。给定信念状态序列的长度 $T_{\mathcal{B}}$ 和轮次 $t$ 前的标记 $\mathcal{B}_{<t}$，预测信念状态的目标定义为：

| (24) |  | $\mathcal{L}_{\mathrm{B}}=\log p(\mathcal{B}\mid\mathcal{H})=\sum_{t=1}^{T_{% \mathcal{B}}}\log p_{\boldsymbol{\theta}}\left(\mathcal{B}_{t}\mid\mathcal{B}_% {<t},\mathcal{H}\right),$ |  |
| --- | --- | --- | --- |

其中 $p(x)$ 是联合概率，$\theta$ 是待学习的参数。

同样，给定去词汇化响应的长度 $T_{\mathcal{S}}$，即 $\mathcal{S}=\left[\mathcal{S}_{1},\cdots,\mathcal{S}_{T_{\mathcal{S}}}\right]$，相应的训练目标可以表述为：

| (25) |  | $\displaystyle\mathcal{L}_{\mathrm{R}}$ | $\displaystyle=\log p(\mathcal{S}\mid\mathcal{D},\mathcal{B},\mathcal{H})$ |  |
| --- | --- | --- | --- | --- |
|  |  | $\displaystyle=\sum_{t=1}^{T_{\mathcal{S}}}\log p_{\boldsymbol{\theta}}\left(% \mathcal{S}_{t}\mid\mathcal{S}_{<t},\mathcal{D},\mathcal{B},\mathcal{H}\right).$ |  |

设 $x$ 为正样本，$x^{\prime}$ 为负样本，Soloist 利用应用于特征的二分类器来预测序列中的项是否对应（$y$ = 1）或不对应（$y$ = 0）。对比目标是定义为交叉熵的：

| (26) |  | $\mathcal{L}_{\mathrm{C}}=y\log\left(p_{\boldsymbol{\theta}}(\boldsymbol{x})% \right)+(1-y)\log\left(1-p_{\boldsymbol{\theta}}\left(\boldsymbol{x}^{\prime}% \right)\right).$ |  |
| --- | --- | --- | --- |

然后，完整的训练目标可以表述为：

| (27) |  | $\mathcal{L}_{\boldsymbol{\theta}}(D)=\sum_{t=1}^{\|D\|}\left(\mathcal{L}_{% \mathrm{B}}\left(\boldsymbol{x}_{t}\right)+\mathcal{L}_{\mathrm{R}}\left(% \boldsymbol{x}_{t}\right)+\mathcal{L}_{\mathrm{C}}\left(\boldsymbol{x}_{t}% \right)\right).$ |  |
| --- | --- | --- | --- |

对于 UBAR（[yang2021ubar,](https://arxiv.org/html/2402.18013v1#bib.bib121)），以前的模块化端到端对话方法是在回合级序列中进行训练和评估的，这些方法基于对话历史$\mathcal{H}_{t}=\left(u_{1},s_{1}\right),\left(u_{2},s_{2}\right),\ldots\left(u_{t-1},s_{t-1}\right),\left(u_{t}\right)$ 在回合 t 中生成回应。而 UBAR 将上下文中的中间信息 $\mathcal{B}$、$\mathcal{D}$ 和 $\mathcal{A}$ 集成在一起。因此，UBAR 在回合 $t$ 的训练序列定义为 $[\mathcal{H}_{0},\mathcal{B}_{0},\mathcal{D}_{0},\mathcal{A}_{0},\mathcal{S}_{0},\dots\mathcal{H}_{t},\mathcal{B}_{t},\mathcal{D}_{t},\mathcal{A}_{t},\mathcal{S}_{t}]$，然后用于微调大型预训练模型 GPT-2。

Su 等人提出了一种用于任务导向对话（PPTOD）的即插即用模型（[su2021multi,](https://arxiv.org/html/2402.18013v1#bib.bib122)），这是一个模块化的端到端对话模型。PPTOD 经过四个与对话任务相关的任务的预训练，并使用提示来增强语言模型的性能。值得一提的是，PPTOD 的学习框架允许其使用部分标注的数据进行训练，这显著减少了手动创建数据集的成本。

半监督预训练对话模型（SPACE）包含一系列 PLMs（[he2022galaxy,](https://arxiv.org/html/2402.18013v1#bib.bib110)；[he2022space,](https://arxiv.org/html/2402.18013v1#bib.bib123)；[he2022unified,](https://arxiv.org/html/2402.18013v1#bib.bib124)），由阿里巴巴 DAMO 学院的对话 AI 团队提出。GALAXY（SPACE-1）（[he2022galaxy,](https://arxiv.org/html/2402.18013v1#bib.bib110)）是一个模块化的端到端对话模型，通过结合有限的标注对话和大量未标注对话语料库，应用半监督学习来明确获取对话策略。以往的研究主要集中在增强 NLU 和 NLG 模块的性能，而 GALAXY 通过在预训练过程中引入新的对话动作预测任务来优化 PL 模块的性能。这些方法提升了 GALAXY 在解决对话任务中的表现，并赋予 GALAXY 比其他模型更强的少样本能力。

SPACE-2 ([he2022space,](https://arxiv.org/html/2402.18013v1#bib.bib123)) 是一个树状结构对话模型，在有限标注对话和大规模未标注对话语料上进行预训练。在传统方法中，正样本被专门定义为具有相同注释的示例，而所有其他实例被归类为负样本。这种分类忽视了不同示例可能在某种程度上展现出共享语义相似性的可能性。因此，SPACE-2 框架为各种数据集建立了树状结构，即语义树结构（STS），基于其各自的数据结构。然后，SPACE-2 衡量不同标注对话之间的相似性，并聚合输出多个分数。在这种方法中，所有注释数据被视为具有软分数的正实例，而不是之前方法中常用的二进制分数（0 或 1）。

SPACE-3 ([he2022unified,](https://arxiv.org/html/2402.18013v1#bib.bib124)) 是最先进的预训练模块化端到端 TOD 模型之一。SPACE-3 框架整合了 SPACE-1 和 SPACE-2 的努力，结合了 STS 以统一不同数据集之间不一致的注释模式，并为每个组件设计了专门的预训练目标。SPACE-3 使用 $p^{u}=\left\{p_{1}^{u},p_{2}^{u},\ldots,p_{A}^{u}\right\}$ 和 $p^{o}=\left\{p_{1}^{o},p_{2}^{o},\ldots,p_{B}^{o}\right\}$ 来表示对话理解提示序列和策略提示序列，其中 $A$ 和 $B$ 是提示序列的长度。然后，$p^{u}$ 和 $p^{o}$ 被用来提取语义并帮助通过 TOD 系统中的任务流。

## 6\. 基于 LLM 的开放领域对话系统

ODD 系统旨在就广泛的主题进行对话，没有特定的任务或目标。虽然 TOD 侧重于实现特定任务，但 ODD 旨在提供连贯且上下文相关的响应，无论用户提出什么话题。ODD 主要分为三种方法：基于检索的方法，从预定义的集合中选择响应；基于生成的方法，动态生成响应；以及混合方法，结合检索和生成以优化对话结果。表 [2](https://arxiv.org/html/2402.18013v1#S6.T2 "Table 2 ‣ 6\. LLM Based Open-Domain Dialogue Systems ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 显示了这三种方法在 ODD 系统领域中的最新进展。

表 2\. 开放领域对话系统的最新进展。

| 任务 | 方法 | 描述 |
| --- | --- | --- |
| 基于检索的方法 | 稠密检索器 ([karpukhin2020dense,](https://arxiv.org/html/2402.18013v1#bib.bib125)) | 稠密向量表示以提高准确性 |
| MSN ([yuan2019multi,](https://arxiv.org/html/2402.18013v1#bib.bib126)) | 通过多跳机制进行上下文管理 |
| IoI Network ([tao2019one,](https://arxiv.org/html/2402.18013v1#bib.bib127) ) | 多轮响应选择的增强 |
| Generation-based Methods | PLATO-LTM ([xu2022long,](https://arxiv.org/html/2402.18013v1#bib.bib128) ) | 长期记忆下的角色一致性 |
| PAML ([madotto2019personalizing,](https://arxiv.org/html/2402.18013v1#bib.bib129) ) | 通过元学习实现个性化 |
| Persona-Consistent Generation ([chen2023learning,](https://arxiv.org/html/2402.18013v1#bib.bib130) ) | 使用潜在变量保持一致性 |
| PHMN ([li2021dialogue,](https://arxiv.org/html/2402.18013v1#bib.bib131) ) | 基于用户历史的个性化匹配 |
| DHAP ([ma2021one,](https://arxiv.org/html/2402.18013v1#bib.bib132) ) | 个性化的动态用户档案学习 |
| MSP Model ([zhong2022less,](https://arxiv.org/html/2402.18013v1#bib.bib133) ) | 对话历史细化用于个性化 |
| GDR Framework ([song2020generate,](https://arxiv.org/html/2402.18013v1#bib.bib134) ) | 角色一致的对话生成 |
| CLV Model ([tang2023enhancing,](https://arxiv.org/html/2402.18013v1#bib.bib135) ) | 双重角色数据利用个性化响应 |
| Hybrid Methods | Retro ([borgeaud2022improving,](https://arxiv.org/html/2402.18013v1#bib.bib136) ) | 检索增强的自回归语言模型 |
| FiD ([izacard2020leveraging,](https://arxiv.org/html/2402.18013v1#bib.bib137) ) | 段落检索与解码融合 |
| K2R ([adolphs2021reason,](https://arxiv.org/html/2402.18013v1#bib.bib138) ) | 以知识为首的事实准确性方法 |
| EMDR${}^{2}$ ([singh2021end,](https://arxiv.org/html/2402.18013v1#bib.bib139) ) | T5 与 Top-k MIPS 检索的集成 |
| Latent Retrieval ([lee2019latent,](https://arxiv.org/html/2402.18013v1#bib.bib140) ) | 高效证据检索的 MIPS |
| IAG ([komeili2021internet,](https://arxiv.org/html/2402.18013v1#bib.bib141) ) | 实时互联网搜索集成 |

### 6.1\. 基于检索的方法

在 ODD 系统中，早期的基础工作为后续的发展奠定了基础。Bordes 等人 ([bordes2016learning,](https://arxiv.org/html/2402.18013v1#bib.bib142) ) 将重点转向端到端学习方法，挑战了传统对领域特定手工制作的依赖。进一步推动这一范式，Tao 等人 ([tao2019one,](https://arxiv.org/html/2402.18013v1#bib.bib127) ) 引入了对多轮响应选择中交互深度的细致方法，展示了更深的交互可以显著提高上下文与响应的匹配。同时，Henderson 等人 ([henderson2017efficient,](https://arxiv.org/html/2402.18013v1#bib.bib143) ) 展示了这些概念在大规模商业环境中的实际应用。这些开创性的贡献为检索式 ODD 系统的新一波创新奠定了基础。

Karpukhin 等人（[karpukhin2020dense,](https://arxiv.org/html/2402.18013v1#bib.bib125)）在信息检索领域引入了一种围绕密集检索器模型的方法。 这种模型与传统的 Lucene-BM25 等检索方法有所不同，主要是通过使用密集向量表示而不是传统的稀疏向量模型，如 TF-IDF 和 BM25。 这些密集表示是从精心策划的一组问题和段落学习的嵌入中获得的，从而提高了前 20 段落检索准确性。 另外，该模型利用了基于 BERT 的双编码器框架，其中一个编码器处理问题，另一个关注段落，每个都将其输入映射到低维向量空间以实现高效检索。模型的训练过程侧重于优化嵌入以有效地对齐问题和段落向量。此优化的目标函数定义如下：

| （28） | | $L(q_{i},p_{i}^{+},p_{i,1}^{-},\ldots,p_{i,n}^{-})=-\log\frac{e^{\text{sim}(q_{% i},p_{i}^{+})}}{e^{\text{sim}(q_{i},p_{i}^{+})}+\sum_{j=1}^{n}e^{\text{sim}(q_% {i},p_{i,j}^{-})}},$ | |  |
| --- | --- | --- | --- | --- |

其中$q_{i}$是问题向量，$p_{i}^{+}$是正向对齐的段落向量，$p_{i,j}^{-}$是负向段落向量。相似性函数$\text{sim}(q,p)$计算问题和段落嵌入的点积。

有了密集检索模型的基础，随后的努力集中于完善对话系统内部的交互深度。Tao 等人（[tao2019one,](https://arxiv.org/html/2402.18013v1#bib.bib127)）引入了 Interaction-over-Interaction（IoI）网络。 IoI 增强了基于检索的聊天机器人中的多轮响应选择。该模型通过利用多轮交互来加深上下文和响应之间的交互。它介绍了多层次的交互，允许网络更有效地捕捉复杂的语义关系。 IoI 模型的交互块逐个处理话语-响应对，自注意机制和迭代细化增强了交互深度。此外，该模型还包括了一种机制，用于在各种交互层次上聚合匹配信号。

### 6.2\. 基于生成的方法

ODD 系统中的生成方法已经显著发展，提供了在响应合成中的灵活性和创造力。早期的工作如 Vinyals 和 Le（[vinyals2015neural,](https://arxiv.org/html/2402.18013v1#bib.bib144)）以及 Sutskever 等人（[sutskever2014sequence,](https://arxiv.org/html/2402.18013v1#bib.bib145)）开创了使用序列到序列模型进行连贯对话生成的工作。Shang 等人（[shang2015neural,](https://arxiv.org/html/2402.18013v1#bib.bib146)）的进一步进展引入了注意力机制，提高了响应的相关性和质量，而 Serban 等人（[serban2016building,](https://arxiv.org/html/2402.18013v1#bib.bib7)）开发了层次递归编码器-解码器以应对更复杂的对话。最近的进展，由 Radford 等人（[radford2019language,](https://arxiv.org/html/2402.18013v1#bib.bib23)）标志，见证了大型变换器模型如 GPT-2 的集成，推动了生成响应的流畅性和上下文意识的界限。

#### 6.2.1\. 知识增强生成

基于这些序列到序列模型和注意力机制的基础性进展，赵等人（[zhao2020knowledge,](https://arxiv.org/html/2402.18013v1#bib.bib147)）通过将外部知识与如 GPT-2 的 PLMs 集成，提出了对话生成的增强方法。他们的方法涉及一个基于 BERT 的知识选择模块，从一组$D$中选择与对话上下文$U$相关的文档$D^{\prime}$。选定的知识被用于基于 GPT-2 的响应生成模型，以生成响应：

| (29) |  | $P(r \mid U,D^{\prime};\theta)=\prod_{t=1}^{lr}P(r_{t} \mid g(U,D^{\prime}),r_{1:t-1}; \theta),$ |  |
| --- | --- | --- | --- |

其中$g(U,D^{\prime})$表示综合的用户对话上下文和选择的知识，$\theta$表示 GPT-2 参数。这种方法允许生成在上下文中相关且受到外部知识启发的响应。

此外，虽然赵等人专注于通过外部知识增强对话生成，徐等人（[xu2022long,](https://arxiv.org/html/2402.18013v1#bib.bib128)）引入了 PLATO-LTM 模型，该模型具有一个长期记忆（LTM）机制，以持续维护个性信息。该模型利用个性提取器（PE）根据用户输入$U_{i}$使用 ERNIE-CNN 架构来分类个性标签。PLATO-LTM 中的 LTM 模块负责将上下文与相关个性匹配，使系统能够检索适当的个性特定信息。生成模块表示为：

| (30) |  | $L_{\text{NLL}}=-\mathbb{E}\left[\sum_{t=1}^{T}\log p(r_{t} \mid c,\rho_{u},\rho_{s},r_{<t})\right].$ |  |
| --- | --- | --- | --- |

该方程表示负对数似然损失函数，其中 $r_{t}$ 是时间 $t$ 生成的响应，$c$ 表示当前上下文，$\rho_{u}$ 和 $\rho_{s}$ 分别是用户和系统的个性嵌入，$r_{<t}$ 表示到前一个时间步生成的响应。PLATO-LTM 的设计重点在于通过动态管理个性信息来增强对话的连贯性和参与度，从而促进更自然和上下文相关的对话生成。

进一步扩展个性化主题，宋等人（[song2020generate](https://arxiv.org/html/2402.18013v1#bib.bib134)）开发了生成-删除-重写（GDR）框架，以创建与个性一致的对话。GDR 框架分为三个阶段：首先生成响应原型，然后识别和遮盖与既定个性不一致的元素，最后对输出进行精细化。该过程从创建初始响应向量开始，接着计算注意力权重以识别不一致性，并在最后的精细化阶段调整初始输出，以确保个性一致性。在量身定制对话生成的思想基础上，唐等人（[tang2023enhancing](https://arxiv.org/html/2402.18013v1#bib.bib135)）引入了基于对比潜变量（CLV）的模型。该模型通过使用稀疏和密集的个性资源来增强对话个性化。它首先对个性信息和用户查询进行编码，然后通过结合这些编码的输入来生成个性化响应。CLV 模型通过将密集的个性描述聚类到稀疏类别中，从而有效地利用不同的个性数据来指导和个性化对话响应。CLV 模型不仅与用户个性一致，而且通过对个体用户特征的深入理解得到丰富。

#### 6.2.2\. 个性化与一致性

转向对话个性化和一致性的关注，Madotto 等人（[madotto2019personalizing](https://arxiv.org/html/2402.18013v1#bib.bib129)）使用模型无关元学习（MAML）进行对话学习个性化。他们的个性无关元学习（PAML）框架将不同的个性视为元学习中的独立任务。PAML 通过对话样本将对话模型适应到新的个性中，这与传统的个性特定描述形成对比。这种方法在生成流畅且一致的对话方面效果显著。

随着领域向更细化的个性化方法发展，Li 等人（[li2021dialogue,](https://arxiv.org/html/2402.18013v1#bib.bib131) ）开发了个性化混合匹配网络（PHMN），该网络将用户特定的对话历史纳入响应选择。PHMN 模型主要有两个方面：首先，它从用户的对话历史中提取个性化的措辞行为。其次，它对上下文-响应话语进行混合表示学习，整合了定制的注意力机制，以从上下文-响应互动中提取关键信息。它提高了匹配响应到用户对话风格和偏好的准确性。

基于利用对话历史进行个性化响应生成的概念，Zhong 等人（[zhong2022less,](https://arxiv.org/html/2402.18013v1#bib.bib133) ）引入了 MSP 模型以细化用户对话历史。MSP 模型包括用户细化器、话题细化器、标记细化器和响应生成器。对话生成过程整合了这些组件：

| (31) |  | $\hat{y}=\text{TRMdec}(x,u_{\text{sim}},t,A),$ |  |
| --- | --- | --- | --- |

其中 $\hat{y}$ 是响应，$x$ 是对话输入，$u_{\text{sim}}$ 是用户相似度输出，$t$ 是话题信息，$A$ 是标记级注意力。该模型通过细化用户对话历史来增强响应生成的个性化。

### 6.3\. 混合方法

ODD 系统中的混合方法代表了基于检索和基于生成的方法的集成，结合了两者的优势。早期的研究包括 Sordoni 等人（[sordoni2015neural,](https://arxiv.org/html/2402.18013v1#bib.bib148) ）的工作，他们探索了基于传统检索方法的上下文敏感生成模型。这种方法为领域内后续的发展奠定了基础。另一个 Yan 等人（[yan2016docchat,](https://arxiv.org/html/2402.18013v1#bib.bib149) ）的贡献则引入了一种模型，该模型根据对话的上下文动态选择生成响应或检索响应。这种混合方法允许更灵活和上下文相关的响应。

#### 6.3.1\. 整合检索与生成

基于对混合方法的初步探索，Borgeaud 等人（[borgeaud2022improving,](https://arxiv.org/html/2402.18013v1#bib.bib136) ）引入了检索增强型变换器（Retro）模型，该模型结合了大规模检索机制和自回归语言模型。这种集成使得语言模型能够从检索数据库中获取上下文相关的信息。模型检索增强型序列对数似然定义为：

| (32) |  | $\mathcal{L}(\mathbf{X}&#124;\theta,\mathcal{D})=\sum_{u=1}^{l}\sum_{i=1}^{m}\log p_% {\theta}(x^{(u-1)m+i}&#124;\mathbf{x}{<(u-1)m+i},\text{Ret}\mathcal{D}(\mathcal{C}^% {u_{0}}{<u})),$ |  |
| --- | --- | --- | --- |

其中 $\mathbf{X}$ 表示输入序列，$\theta$ 表示模型参数，$\mathcal{D}$ 是检索数据库，$\text{Ret}\mathcal{D}$ 指的是检索操作。

#### 6.3.2\. 通过外部知识增强对话

Adolphs 等人 ([adolphs2021reason,](https://arxiv.org/html/2402.18013v1#bib.bib138)) 开发了知识到响应 (K2R) 模型，专注于事实准确性。K2R 首先生成与对话上下文相关的知识序列，然后将这些知识整合以合成最终响应。Izacard 和 Grave ([izacard2020leveraging,](https://arxiv.org/html/2402.18013v1#bib.bib137)) 开发了解码器中的融合 (FiD) 模型，将生成模型与段落检索结合。FiD 独立编码一个问题和多个检索到的段落，将每个段落与问题串联以进行解码，从而促进了从各种段落中综合信息。

在检索增强的概念基础上，Xu 等人 ([xu2021beyond,](https://arxiv.org/html/2402.18013v1#bib.bib150)) 关注长期对话的动态。他们探索了检索增强生成模型，其特点是将对话上下文和模型机制相结合：

| (33) |  | $p(y\vert x)=\sum_{z\in\text{Retrieve}(x)}p(z\vert x)\cdot p(y\vert x,z).$ |  |
| --- | --- | --- | --- |

此外，他们还探索了基于记忆的模型与总结，其中模型总结过去的对话以生成响应：

| (34) |  | $P(y\vert x,S)=\text{SummaryGeneration}(x,\text{Past Dialogues}).$ |  |
| --- | --- | --- | --- |

Singh 等人 ([singh2021end,](https://arxiv.org/html/2402.18013v1#bib.bib139)) 开发了 $\mathrm{EMDR}^{2}$，将 T5 编码和解码与 Top-k MIPS 检索机制集成，并通过尺度证据文档编码器增强。该系统旨在优化多文档阅读和检索。$\mathrm{EMDR}^{2}$ 实现了用于潜变量模型训练的期望最大化 (EM) 算法。训练过程涉及计算潜变量 $Z$ 的后验分布，训练目标为：

| (35) |  | $\displaystyle L=\log p(a\vert q,Z_{\text{top-K}};\Theta)+\log\sum_{k=1}^{K}\text{SG% }(p(a\vert q,z_{k};\Theta))p(z_{k}\vert q,Z_{\text{top-K}};\lambda),$ |  |
| --- | --- | --- | --- |

其中 SG 是停止梯度操作符，$\Theta$ 是阅读器的参数，$\lambda$ 是检索器的参数。

Komeili 等人 ([komeili2021internet,](https://arxiv.org/html/2402.18013v1#bib.bib141)) 引入了一个“互联网增强对话生成”系统，集成了实时互联网。该系统包括一个搜索查询生成器和一个响应生成模块。搜索查询生成器是一个基于变压器的编码器-解码器模型，从对话上下文中生成互联网搜索查询。响应模块利用检索到的信息构建响应。系统的功能封装在：

| (36) |  | $R=\text{FiD}\left(\text{Encoder-Decoder}(C),\,\text{InternetSearch}(\text{% Encoder-Decoder}(C))\right),$ |  |
| --- | --- | --- | --- |

其中 $C$ 是对话上下文，$R$ 是生成的响应。Encoder-Decoder 函数处理 $C$，InternetSearch 基于查询检索信息。FiD 方法将这些信息整合生成 $R$。

## 7\. 评估方法

有效的模型评估方法一直是研究领域关注的重点。在本节中，我们介绍了广泛使用的自动评估和人工评估方法。

### 7.1\. 自动评估

#### 7.1.1\. 任务导向对话系统的自动评估方法

对于任务导向对话（TOD）系统的评估主要采用自动方法，包括联合目标准确率、槽准确率、平均目标准确率、请求槽 F1、BLEU 和实体 F1。在以下内容中，将简要介绍每种方法。

##### 联合目标准确率

联合目标准确率（JGA），由 Henderson 等人 ([henderson2014word,](https://arxiv.org/html/2402.18013v1#bib.bib151) ) 和 Zhong 等人 ([zhong2018global,](https://arxiv.org/html/2402.18013v1#bib.bib95) ) 提出，是 DST 最广泛使用的评估方法。联合目标是对话中的一组累计轮次目标，比较预测的对话状态与包含所有可能配对槽值的实际值。如果在每轮中所有预测值都与实际值匹配，则输出被认为是正确预测。JGA 可以表示为：

| (37) |  | $JGA=\begin{cases}1&amp;\text{如果预测状态 = 金标准状态},\\ 0&amp;\text{否则}.\end{cases}$ |  |
| --- | --- | --- | --- |

##### 槽准确率

槽准确率（SA） ([wu2019transferable,](https://arxiv.org/html/2402.18013v1#bib.bib152) ) 也是一种广泛使用的自动评估方法。与联合目标准确率不同，它只对每个值与相应的实际值进行逐个比较，而不考虑其他轮次。SA 可以表示为：

| (38) |  | $SA=\frac{T-M-W}{T},$ |  |
| --- | --- | --- | --- |

其中 $T$ 表示所有领域预定义槽的总数，$M$ 代表模型未准确预测的金标准状态中包含的槽的数量，$W$ 表示在金标准状态中不存在的槽中错误预测的数量。

##### 平均目标准确率

平均目标准确率（AGA） ([rastogi2020towards,](https://arxiv.org/html/2402.18013v1#bib.bib153) ) 是在每轮中对一个活动槽正确值预测的平均准确率。如果槽值在当前轮次中提到并且不是从前面的轮次继承的，则槽变为活动状态。AGA 可以表示为：

| (39) |  | $AGA=\frac{&#124;N_{t}\cap B_{t}^{\prime}&#124;}{&#124;N_{t}&#124;},$ |  |
| --- | --- | --- | --- |

其中 $B_{t}$ 和 $B_{t}^{\prime}$ 分别是第 $t$ 回合的真实和预测的信念状态集合。然后令 $N_{t}\subseteq B_{t}$ 为具有非空槽位值的真实三元组集合。

##### 请求的槽位 F1

请求槽位 F1 指标表示模型在正确预测用户是否请求了某个槽位方面的表现，估算为所有请求槽位的宏平均 F1 分数。宏平均 F1 分数是对每个回合中的个别槽位类型和槽位值进行计算的。要定义宏平均 F1 分数 ($ma\,F_{1}$)，首先考虑以下每个类别中的精确度 ($P_{i}$) 和召回率 ($R_{i}$)，$i\,=\,1,\ \dots,\ 2$：

| (40) |  | $\displaystyle P_{i}$ | $\displaystyle=\frac{TP_{i}}{(TP_{i}+FP_{i})}=\frac{p_{ii}}{p_{i-}},$ |  |
| --- | --- | --- | --- | --- |
| (41) |  | $\displaystyle R_{i}$ | $\displaystyle=\frac{TP_{i}}{(TP_{i}+FN_{i})}=\frac{p_{ii}}{p_{-i}},$ |  |

而每个类别中的 F1 分数（$F_{1i}$）定义为 $P_{i}$ 和 $R_{i}$ 的调和均值，即：

| (42) |  | $F_{1i}=2\frac{P_{i}\times R_{i}}{P_{i}+R_{i}}=2\frac{p_{ii}}{p_{i-}+p_{-i}}.$ |  |
| --- | --- | --- | --- |

宏平均 F1 分数定义为 $F_{1i}$ 的简单算术平均值：

| (43) |  | $ma\,F_{1}=\frac{1}{r}\sum_{i=1}^{r}F_{1i}=\frac{2}{r}\sum_{i=1}^{r}\frac{p_{ii% }}{p_{i-}+p_{-i}}.$ |  |
| --- | --- | --- | --- |

##### BLEU

BLEU ([papineni2002bleu,](https://arxiv.org/html/2402.18013v1#bib.bib154) ) 用于基于匹配的 n-gram 短语的加权平均来计算两个句子的共现频率。BLEU 最初用于评估机器翻译，后来也用于评估 TOD 和 ODD 系统。

##### 实体 F1

实体 F1 用于评估模型从基础知识库中生成相关实体的能力，以及捕捉用户发起对话流程的语义。要计算实体 F1，需要对整个系统对话响应集进行微平均，并使用标准化形式的实体。

#### 7.1.2\. 开放领域对话系统的自动评估方法

ODD 系统的评估主要通过自动化方法进行，即困惑度、BLEU、DIST-n 和 recall@K。以下是每种方法的简要描述。

##### 困惑度

困惑度 ([vinyals2015neural,](https://arxiv.org/html/2402.18013v1#bib.bib144) ) 最初被设想为一种信息论度量，用于评估给定语言模型对文本序列的预测适用性，或者等效地，词序列在特定语言模型中的适应性。现在，它被用作一种分析方法，可能用于支持早期诊断心理障碍症状。困惑度可以表示为：

| (44) |  | $PP(W)=P(w_{1}w_{2}...w_{N})^{-1/N}=\sqrt[N]{\frac{1}{P(w_{1}w_{2}\dots w_{N})}},$ |  |
| --- | --- | --- | --- |

其中 $W$ 是长度为 $N$ 的词序列，$P(w_{1}w_{2}\dots w_{N})$ 是该词序列的概率。

##### DIST-n

DIST-n ([li2015diversity,](https://arxiv.org/html/2402.18013v1#bib.bib155) ) 用于通过计算生成响应中不同的单字（unigrams）和双字（bigrams）的数量来衡量对话生成的多样性。该值通过生成的总词数进行缩放，以避免偏向长句子。DIST-1 和 DIST-2 分别是不同单字和双字的数量除以生成的总词数。

##### Recall@K

Recall@K 是评估的标准方法之一。对于查询 $q$，它定义为在前 k 个排名的示例中相关（正向）示例的数量与 $q$ 的所有相关示例数量的比率，用 $|P_{q}|$ 表示。当针对查询 $q$ 和数据库 $\Omega$ 计算时，记作 $R^{k}_{\Omega}(q)$，函数 $H(.)$ 为海维赛德阶跃函数。因此，可以表达为：

| (45) |  | $R^{k}_{\Omega}(q)=\frac{H(k-1-\sum_{z\in\Omega,z\neq x}H(S_{qz}-S_{qx}))}{ | P_{q} | }.$ |  |
| --- | --- | --- | --- | --- | --- |

### 7.2\. 人工评估

人工评估也作为不同任务中的评估方法。人工评估着重于解释两个问题：多样性和创造力，即在形式和重点上变换文本的能力，以适应各种发言情况，以及将任何对象或关系表达为自然语言文本的潜力。此外，人工评估审查三个关键方面：语法（生成的句子是否语法正确且流畅）、忠实（输出是否准确反映输入）和连贯性（确保句子逻辑一致并符合自然书写的流畅性）。

## 8\. 数据集

在本节中，我们介绍了近年来在任务导向对话（TOD）和开放域对话（ODD）系统中广泛使用的数据集。表[3](https://arxiv.org/html/2402.18013v1#S8.T3 "Table 3 ‣ Stanford Multi-Domain ‣ 8.1\. Datasets for Task-oriented Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 和表[4](https://arxiv.org/html/2402.18013v1#S8.T4 "Table 4 ‣ Douban ‣ 8.2\. Datasets for Open-domain Dialogue Systems ‣ 8\. DATASETS ‣ A Survey on Recent Advances in LLM-Based Multi-turn Dialogue Systems") 显示了 TOD 和 ODD 数据集的一些信息。

### 8.1\. 任务导向对话系统的数据集

##### MultiWOZ

MultiWOZ ([budzianowski2018multiwoz,](https://arxiv.org/html/2402.18013v1#bib.bib156) ) 是一个完全标注的人机对话数据集，包含 10,438 个对话。该数据集通过 Wizard-of-Oz 收集，包含 7 个领域的对话，每个对话覆盖 1 到 5 个领域，因此在长度和复杂度上有很大的变化。MultiWOZ 经历了多个版本，进行了几次错误修正。MultiWOZ 2.1 ([eric2019multiwoz,](https://arxiv.org/html/2402.18013v1#bib.bib157) ) 为数据集中的每个槽位提供了 2-3 个描述。MultiWOZ 2.2 ([zang2020multiwoz,](https://arxiv.org/html/2402.18013v1#bib.bib158) ) 进一步提供了领域和槽位的描述，以及分类槽位的可能值。MultiWOZ 2.3 ([han2021multiwoz,](https://arxiv.org/html/2402.18013v1#bib.bib159) ) 区分了对话行为与对话状态中的错误标注，识别了缺乏共指的问题。MultiWOZ 2.4 ([ye2021multiwoz,](https://arxiv.org/html/2402.18013v1#bib.bib160) ) 是最新版本，修正了不正确和不一致的标注。

##### RiSAWOZ

RiSAWOZ ([quan2020risawoz,](https://arxiv.org/html/2402.18013v1#bib.bib161) ) 是一个大规模的多领域中文 Wizard-of-Oz 数据集，具有丰富的语义标注。它包含 11,200 个人工对话，具有丰富的语义标注，涵盖 12 个领域，超过 150,000 个发言。每个对话都标注了全面的对话注释，包括对话目标、领域、对话状态和用户及系统端的行为。

##### CrossWOZ

CrossWOZ ([zhu2020crosswoz,](https://arxiv.org/html/2402.18013v1#bib.bib162) ) 是一个大规模的中文跨领域 Wizard-of-Oz 任务导向数据集。它包含 6,000 个对话会话和 102,000 个发言，涵盖 5 个领域。它包含丰富的对话状态和行为标注，包括用户端和系统端，大约 60%的对话具有跨领域的用户目标。

##### PersuasionForGood

PersuasionForGood (P4G) ([wang2019persuasion,](https://arxiv.org/html/2402.18013v1#bib.bib163) ) 是一个包含 1,017 个对话的数据集，并从一个子集中标注了新兴的说服策略。该数据集通过在线说服任务收集，参与者被要求劝说另一个人向特定慈善机构捐款。这是一个丰富的人工对话数据集，涵盖了用户心理研究和说服策略标注。

##### WOZ 2.0

WOZ 2.0 ([mrkvsic2016neural,](https://arxiv.org/html/2402.18013v1#bib.bib164) ) 是一个从 CamRest ([wen2016network,](https://arxiv.org/html/2402.18013v1#bib.bib165) ) 数据集更新而来的数据集，包含 676 个对话。该数据集通过 Wizard-of-Oz 收集，包含 1,200 个对话。对话中的每个回合均由不同的用户贡献，这些用户需要审查该对话中的所有先前回合。

##### 斯坦福多领域

Stanford Multi-Domain (SMD) ([eric2017key,](https://arxiv.org/html/2402.18013v1#bib.bib166)) 是一个 Wizard-of-Oz 数据集。它包含 3,031 个对话，分布在 3 个不同领域。这些对话基于底层知识库，并且每个对话都附有一个知识片段，作为简化的数据库信息。

表 3\. 任务导向对话的数据集概述。*SMD 仅提供每个对话中的发言平均数和每个发言中的令牌平均数的统计数据。单一领域和多领域显示数据集中是否包含单一领域或多领域的对话。*

| 数据集 | 对话数 | 平均每对话轮次 | 平均每轮令牌数 | 领域 | 单一领域 | 多领域 |
| --- | --- | --- | --- | --- | --- | --- |
| MultiWOZ | 10,438 | 13.70 | 13.18 | 7 | ✓ | ✓ |
| RiSAWOZ | 11,200 | 13.57 | 10.91 | 12 | ✓ | ✓ |
| CrossWOZ | 6,012 | 16.90 | 16.25 | 5 | ✓ | ✓ |
| P4G | 1,017 | 10.43 | - | 1 | ✓ | ✗ |
| WOZ 2.0 | 1,200 | 7.35 | 11.27 | 1 | ✓ | ✗ |
| SMD | 3,031 | 5.29* | 9* | 3 | ✓ | ✗ |

### 8.2\. 开放领域对话系统的数据集

##### PersonaChat

PersonaChat ([zhang2018personalizing,](https://arxiv.org/html/2402.18013v1#bib.bib167)) 包含聊天记录和个体，这些是描述个性的五句或更多句子的集合。该数据集由众包对话组成，其中每个参与者扮演指定个体的角色；每个人都有一个词汇独特的改写。它配对了人类生成的个人资料和对话，帮助构建具有一致个性和观点的智能体。

##### MMdialog

MMdialgo ([feng2022mmdialog,](https://arxiv.org/html/2402.18013v1#bib.bib168)) 是一个大规模的多轮对话数据集，旨在进行多模态开放领域对话。它由 108 万个真实世界对话和 153 万个独特图像组成，涵盖了 4148 个主题。它包含大量主题，以便推广到开放领域，并且是按对话数量计算的最大多模态对话数据集，数量是其他数据集的 88 倍。

##### Dailydialog

Dailydialog ([li2017dailydialog,](https://arxiv.org/html/2402.18013v1#bib.bib169)) 是一个多轮对话数据集，包含 13118 个对话。它通过从一个英语学习网站上抓取对话文本来创建。这些对话涵盖了 10 个主题，并遵循常见的对话流程。此外，该数据集包含独特的多轮对话流模式，反映了我们的现实沟通方式。每个发言都标记了对话行为和情感。

##### Pchatbot

Pchatbot ([qian2021pchatbot,](https://arxiv.org/html/2402.18013v1#bib.bib170)) 是一个大规模对话数据集，包含了从微博和司法论坛分别收集的两个子集。它由近 2 亿对话对组成。该数据集经过精心规范化，如匿名化、去重、分段和过滤。它提供了匿名的用户 ID 和帖子及回复的时间戳。这使得模型能够直接从用户的对话历史中学习隐含的用户个性。

##### PersonalDialogue

PersonalDialogue ([zheng2019personalized,](https://arxiv.org/html/2402.18013v1#bib.bib171)) 是一个大规模的多轮对话数据集，包含了大量人的各种特征。数据集包含了 2083 万次会话和 5625 万句话，由 847 万人提供。每句话都与标记有年龄、性别、位置、兴趣标签等特征的说话者相关联。该数据集有助于个性化对话生成的研究。

##### 豆瓣

豆瓣 ([wu2016sequential,](https://arxiv.org/html/2402.18013v1#bib.bib4)) 是首个用于多轮回应选择的人类标注数据集。它从豆瓣小组抓取了 110 万对话（每对话超过 2 轮），并随机抽取了 50 万对话用于创建训练集，25,000 对话用于创建验证集，1,000 对话用于创建测试集。该数据集的对话来自开放领域，对话候选项从检索引擎收集。

表 4. 开放域对话数据集概述。人与人表示两个互相对话的人所用的数据集。抓取的标记表示从现有在线资源收集的数据集。

| 数据集 | 对话 | 方法 | 来源 | 语言 |
| --- | --- | --- | --- | --- |
| PersonaChat | 164,356 | 人与人 | 众包 | en |
| MMdialog | 1,079,117 | 抓取的 | 社交媒体 | en |
| Dailydialog | 13,118 | 抓取的 | - | en |
| Pchatbot | 198,875,796 | 抓取的 | 微博，司法 | zh |
| PersonalDialogue | 约 2083 万 | 抓取的 | 微博 | zh |
| 豆瓣 | 526,000 | 抓取的 | 豆瓣 | zh |

## 9. 讨论

越来越多的研究人员正在探讨将大型语言模型应用于多轮对话系统的不同组件或多轮开放领域对话系统的不同组件。推动多轮对话系统任务流行的一个重要因素是对聊天机器人的需求在工业环境和日常活动中的不断增长。行业代表如 OpenAI 的 ChatGPT、Anthropic 的 Claude 2、Meta 的 Meta AI 和 Google 的 Gemini Ultra 极大地提高了人们生活的便利性。另一个原因是大量的自然语言数据以对话形式存在，而多轮对话系统更符合现实场景，从而促进了基于大型模型的多轮对话系统的发展。同时，LLMs 为人类提供了一个强大的工具箱。

本节讨论了 LLM 基于多轮对话系统面临的挑战，这些挑战值得解决和研究未来。

深度理解和大规模开放检索。通过在多轮对话中使用 LLM，需要更高效地理解和保留较长的上下文信息，以生成更连贯和相关的回答。与开放领域 QA 任务相比，开放检索对话主要源于人机交互的特征，带来了新的挑战，影响了效率和效果。

情感化和个性化。情感化对话系统和增强逻辑一致性可以使回答更符合查询的需求，理解表达背后的情感，从而更好地理解语义和上下文关联，提供更合适的答案。

多任务对话系统。最近在端到端的 TOD 系统和知识驱动的开放领域系统的研究为将这两种不同的范式融合到一个统一框架中，甚至可能是一个统一模型，开辟了前景。这些混合对话系统被设计为同时作为助手高效执行特定任务和作为聊天机器人进行对话互动。

多模态对话系统。我们生活的世界本质上是多模态的，人类利用视觉、听觉、嗅觉、味觉和触觉等多种感官来感知它。因此，聊天机器人必须具备将来自不同模态的信息融合的能力。虽然现代的大型聊天模型在处理文本、音频和图片方面表现出色，但在视频处理方面仍然面临显著的局限性和挑战。

偏见识别和隐私保护。LLM 由于其训练数据来自公开的在线数据集，可能生成有害、冒犯或偏见的内容。虽然研究人员已通过微调来解决这一问题，但特别是在英语以外的语言中，公开数据集有限，挑战可能依然存在。在发展更复杂的对话系统的同时，保护用户隐私也非常重要。

## 10\. 结论

近年来，LLM（大规模语言模型）的快速进展使多轮对话任务成为自然语言处理研究的前沿。本文深入研究了基于 LLM 的多轮对话系统。文章首先根据模型结构对常见的 LLM 进行分类，并介绍了将 LLM 适应于各种子任务的方法，包括微调和提示工程。随后，讨论了基于 LLM 的多轮对话系统的两大类：基于 LLM 的任务导向对话（TOD）系统和基于 LLM 的开放域对话（ODD）系统。接着，论文概述了从多轮对话系统的输出中得出的评估指标，这些指标有助于评估和理解 LLM 的对话能力。此外，论文还突出了近年来在 TOD 和 OOD 系统中广泛使用的数据集。最后，文章提出了一些开放问题，以指示 LLM-based 多轮对话系统的主要挑战和未来研究方向。

## 参考文献

+   (1) Joseph Weizenbaum. Eliza——一个用于研究人机自然语言交流的计算机程序. ACM 通讯，9(1)：36–45，1966 年。

+   (2) Kenneth Mark Colby、Sylvia Weber 和 Franklin Dennis Hilf. 人工偏执. 人工智能，2(1)：1–25，1971 年。

+   (3) David Goddeau 等人. 一种用于口语语言应用的基于表单的对话管理器. 见于第四届国际口语语言处理会议论文集。ICSLP’96，第 2 卷，页 701–704。IEEE，1996 年。

+   (4) Yu Wu 等人. 顺序匹配网络：一种用于检索型聊天机器人中的多轮对话选择的新架构. 见于第 55 届计算语言学协会年会（第 1 卷：长篇论文）论文集，页 496–505，温哥华，加拿大，2017 年 7 月。计算语言学协会。

+   (5) Tiancheng Zhao 和 Maxine Eskenazi. 致力于通过深度强化学习实现对话状态追踪和管理的端到端学习. 见于第 17 届话语与对话特别兴趣小组年会论文集，页 1–10，洛杉矶，2016 年 9 月。计算语言学协会。

+   (6) Wentao Ma 等人. TripleNet: 一种用于检索型聊天机器人中的多轮对话选择的三重注意力网络. 见于第 23 届计算自然语言学习会议（CoNLL）论文集，页 737–746，香港，中国，2019 年 11 月。计算语言学协会。

+   (7) Iulian Serban 等人. 使用生成层次神经网络模型构建端到端对话系统. 见于 AAAI 人工智能会议论文集，第 30 卷，2016 年。

+   (8) Wanwei He 等人. 通过对抗训练将两个教师的知识融合用于任务导向对话系统. 见于 2020 年自然语言处理实证方法会议（EMNLP）论文集，页 3498–3507，2020 年。

+   (9) Lisong Qiu 等人。训练样本是否相关？学习生成对话回应的多重参考。在第 57 届计算语言学协会年会上，页面 3826–3835，2019 年。

+   (10) Suket Arora、Kamaljeet Batra 和 Sarabjit Singh。对话系统：简要综述。arXiv 预印本 arXiv:1306.4134，2013 年。

+   (11) Hongshen Chen 等人。对话系统综述：最新进展与新前沿。Acm Sigkdd Explorations Newsletter，19(2)：25–35，2017 年。

+   (12) Jinjie Ni 等人。基于深度学习的对话系统的最新进展：系统综述。人工智能评论，56(4)：3055–3155，2023 年。

+   (13) Libo 等人。秦。端到端任务导向对话：任务、方法和未来方向的综述。在 2023 年自然语言处理实证方法会议上，页面 5925–5941，新加坡，2023 年 12 月。计算语言学协会。

+   (14) Jared Kaplan 等人。神经语言模型的规模定律。arXiv 预印本 arXiv:2001.08361，2020 年。

+   (15) Jason Wei 等人。大规模语言模型的涌现能力。arXiv 预印本 arXiv:2206.07682，2022 年。

+   (16) Xipeng Qiu 等人。自然语言处理的预训练模型：综述。科学中国技术科学，63(10)：1872–1897，2020 年。

+   (17) Ashish Vaswani 等人。注意力即你所需。神经信息处理系统进展，30，2017 年。

+   (18) Colin Raffel 等人。探索统一文本到文本变换器的迁移学习极限。《机器学习研究杂志》，21(1)：5485–5551，2020 年。

+   (19) Peter J. Liu 等人。通过总结长序列生成维基百科。arXiv 预印本 arXiv:1801.10198，2018 年。

+   (20) Alec Radford 等人。通过生成预训练提升语言理解。2018 年。

+   (21) Rami Al-Rfou 等人。使用更深自注意力的字符级语言建模。在 AAAI 人工智能会议上，卷 33，页面 3159–3166，2019 年。

+   (22) Junjie Ye 等人。GPT-3 和 GPT-3.5 系列模型的综合能力分析。arXiv 预印本 arXiv:2303.10420，2023 年。

+   (23) Alec Radford 等人。语言模型是无监督的多任务学习者。OpenAI 博客，1(8)：9，2019 年。

+   (24) Bryan McCann 等人。自然语言十项全能：多任务学习作为问答。arXiv 预印本 arXiv:1806.08730，2018 年。

+   (25) Tom Brown 等人。语言模型是少样本学习者。神经信息处理系统进展，33：1877–1901，2020 年。

+   (26) Long Ouyang 等人。通过人类反馈训练语言模型以遵循指令。神经信息处理系统进展，35：27730–27744，2022 年。

+   (27) Wayne Zhao Xin 等人。大规模语言模型综述。arXiv 预印本 arXiv:2303.18223，2023 年。

+   (28) OpenAI。介绍 ChatGPT，2022 年 11 月。

+   (29) Samantha Lock。什么是 AI 聊天机器人现象 ChatGPT，它能取代人类吗。卫报，第 5 页，2022 年。

+   (30) OpenAI。GPT-4 技术报告，2023 年。

+   (31) Samantha Lock. 什么是 AI 聊天机器人现象 ChatGPT， 它会取代人类吗? 《卫报》.

+   (32) Jon Gertner. 维基百科的真实时刻. 《纽约时报杂志》.

+   (33) ChatGPT 现在可以看、听和说话. [`www.openai.com`](https://www.openai.com), 2023. 2023 年 10 月 16 日检索.

+   (34) Kevin Roose. 新版 ChatGPT 能“看见”和“说话”。这是什么感觉. 《纽约时报》，2023 年 9 月 27 日. 2023 年 10 月 16 日检索.

+   (35) OpenAI. 介绍 GPTs, 2023 年 11 月.

+   (36) Hugo Touvron 等. Llama: 开放且高效的基础语言模型. arXiv 预印本 arXiv:2302.13971, 2023.

+   (37) Meta AI. 介绍 Llama: 一种基础的 65 亿参数大型语言模型. 2023 年 2 月. URL-of-the-Article（访问时间：2024 年 2 月 28 日）。

+   (38) Jordan Hoffmann 等. 训练计算优化的大型语言模型. arXiv 预印本 arXiv:2203.15556, 2022.

+   (39) Jack W. Rae 等. 扩展语言模型: 方法、分析与 Gopher 训练的洞察. arXiv 预印本 arXiv:2112.11446, 2021.

+   (40) Meta. Meta 和微软介绍下一代 Llama. 2023 年 7 月. 2023 年 7 月 21 日检索, 来自 [`about.fb.com/news/2023/07/llama-2/`](https://about.fb.com/news/2023/07/llama-2/)。

+   (41) Hugo Touvron 等. Llama 2: 开放基础模型和微调聊天模型, 2023.

+   (42) Baptiste Rozière 等. Code Llama: 用于代码的开放基础模型, 2023.

+   (43) Zhengxiao Du 等. Glm: 具有自回归空白填充的通用语言模型预训练. arXiv 预印本 arXiv:2103.10360, 2021.

+   (44) Aohan Zeng 等. Glm-130b: 一种开放的双语预训练模型. arXiv 预印本 arXiv:2210.02414, 2022.

+   (45) THUDM. Chatglm2-6b. [`github.com/thudm/chatglm2-6b`](https://github.com/thudm/chatglm2-6b), 2022.

+   (46) THUDM. Chatglm3. [`github.com/THUDM/ChatGLM3`](https://github.com/THUDM/ChatGLM3), 2023.

+   (47) Jacob Devlin 等. BERT: 用于语言理解的深度双向变换器的预训练. 页码 4171–4186, 明尼阿波利斯, 明尼苏达州, 2019 年 6 月. 计算语言学协会.

+   (48) Google AI 博客. 开源 BERT: 用于自然语言处理的最先进预训练. 2018 年 11 月. 2019 年 11 月 27 日检索.

+   (49) Yinhan Liu 等. Roberta: 一种稳健优化的 BERT 预训练方法. arXiv 预印本 arXiv:1907.11692, 2019.

+   (50) Li Dong 等. 统一语言模型预训练用于自然语言理解与生成. 神经信息处理系统进展, 32, 2019.

+   (51) Mike Lewis 等. Bart: 用于自然语言生成、翻译和理解的去噪序列到序列预训练. arXiv 预印本 arXiv:1910.13461, 2019.

+   (52) Neil Houlsby 等. 参数高效的 NLP 转移学习. 在国际机器学习大会, 页码 2790–2799. PMLR, 2019.

+   (53) Jonas Pfeiffer 等. AdapterHub: 用于适配变换器的框架. 页码 46–54, 在线, 2020 年 10 月. 计算语言学协会.

+   (54) Xiao Liu 等. GPT 也理解. AI Open, 2023。

+   (55) Edward Hu 等. Lora: 大型语言模型的低秩适应. 收录于 2021 年北美计算语言学协会年会: 人类语言技术会议，第 4395–4409 页，2021 年。

+   (56) Tim Dettmers 等. Qlora: 高效量化 LLMs 微调. arXiv 预印本 arXiv:2305.14314, 2023。

+   (57) Jason Wei 等. 微调的语言模型是零样本学习者. arXiv 预印本 arXiv:2109.01652, 2021。

+   (58) Tianyi Zhang 等. 重新审视少样本 BERT 微调. arXiv 预印本 arXiv:2006.05987, 2020。

+   (59) Marius Mosbach, Maksym Andriushchenko 和 Dietrich Klakow. 关于 BERT 微调的稳定性: 误解、解释与强基线. arXiv 预印本 arXiv:2006.04884, 2021。

+   (60) Armen Aghajanyan 等. 通过减少表示崩溃来改进微调. arXiv 预印本 arXiv:2008.03156, 2020。

+   (61) Haoming Jiang 等. SMART: 通过有原则的正则化优化实现对预训练自然语言模型的鲁棒且高效的微调. 收录于第 58 届计算语言学协会年会，第 2177–2190 页，在线，2020 年 7 月。计算语言学协会。

+   (62) Chen Zhu 等. Freelb: 增强对抗训练以提高自然语言理解能力. arXiv 预印本 arXiv:1909.11764, 2019。

+   (63) Timo Schick 和 Hinrich Schütze. 利用填空题进行少样本文本分类和自然语言推理. 收录于第 16 届欧洲计算语言学协会会议论文集: 主卷，第 255–269 页，在线，2021 年 4 月。计算语言学协会。

+   (64) Tianyu Gao, Adam Fisch 和 Danqi Chen. 让预训练语言模型成为更好的少样本学习者. 收录于第 59 届计算语言学协会年会及第 11 届国际自然语言处理联合会议（第 1 卷: 长篇论文），第 3816–3830 页，在线，2021 年 8 月。计算语言学协会。

+   (65) Timo Schick 和 Hinrich Schütze. 利用填空题进行少样本文本分类和自然语言推理. 收录于第 16 届欧洲计算语言学协会会议论文集: 主卷，第 255–269 页，在线，2021 年 4 月。计算语言学协会。

+   (66) Xu Han 等. PTR: 规则驱动的提示微调用于文本分类. AI Open, 3:182–192, 2022。

+   (67) Shengding Hu 等. 知识性提示微调: 将知识融入提示语以进行文本分类. 收录于第 60 届计算语言学协会年会（第 1 卷: 长篇论文），第 2225–2240 页，都柏林，爱尔兰，2022 年 5 月。计算语言学协会。

+   (68) Xiao Liu 等. GPT 也理解. AI Open, 2023。

+   (69) Xiang Lisa Li 和 Percy Liang. 前缀调优：优化生成的连续提示. 载于《第 59 届计算语言学协会年会暨第 11 届国际自然语言处理联合会议（第 1 卷：长篇论文）》论文集，第 4582–4597 页，线上，2021 年 8 月\. 计算语言学协会。

+   (70) Brian Lester, Rami Al-Rfou, 和 Noah Constant. 参数高效的提示调优的规模效应. 载于《2021 年自然语言处理经验方法会议论文集》，第 3045–3059 页，线上及多米尼加共和国蓬塔卡纳，2021 年 11 月\. 计算语言学协会。

+   (71) Xiao Liu 等. P-tuning v2：提示调优可以在不同规模和任务中与微调相媲美. arXiv 预印本 arXiv:2110.07602，2021 年。

+   (72) Guanghui Qin 和 Jason Eisner. 学习如何提问：用软提示的混合查询语言模型. 载于《2021 年北美计算语言学协会人类语言技术会议论文集》，第 5203–5212 页，线上，2021 年 6 月\. 计算语言学协会。

+   (73) Jiachang Liu 等. 什么使得 GPT-3 的上下文示例有效？ 载于《深入学习透视（DeeLIO 2022）：第三届知识提取与集成研讨会》，第 100–114 页，爱尔兰都柏林及线上，2022 年 5 月\. 计算语言学协会。

+   (74) Yao Lu 等. 奇妙排序的提示及其发现：克服少量样本提示顺序敏感性. 载于《第 60 届计算语言学协会年会（第 1 卷：长篇论文）》论文集，第 8086–8098 页，爱尔兰都柏林，2022 年 5 月\. 计算语言学协会。

+   (75) Mingda Chen 等. 通过自监督训练提升上下文中的少量样本学习. 载于《2022 年北美计算语言学协会人类语言技术会议论文集》，第 3558–3573 页，美国西雅图，2022 年 7 月\. 计算语言学协会。

+   (76) Yanda Chen 等. 通过语言模型的上下文调优进行元学习. 载于《第 60 届计算语言学协会年会（第 1 卷：长篇论文）》论文集，第 719–730 页，爱尔兰都柏林，2022 年 5 月\. 计算语言学协会。

+   (77) Sewon Min 等. MetaICL：在上下文中学习如何学习. 载于《2022 年北美计算语言学协会人类语言技术会议论文集》，第 2791–2809 页，美国西雅图，2022 年 7 月\. 计算语言学协会。

+   (78) Jason Wei 等. 思维链提示激发大语言模型中的推理. 《神经信息处理系统进展》，35:24824–24837，2022 年。

+   (79) Takeshi Kojima 等人. 大语言模型是零样本推理器。发表于《神经信息处理系统进展》，35:22199–22213，2022 年。

+   (80) Denny Zhou 等人. 最少到最多提示实现大语言模型中的复杂推理。arXiv 预印本 arXiv:2205.10625，2022 年。

+   (81) Zhuosheng Zhang 等人. 大语言模型中的自动思维链提示。arXiv 预印本 arXiv:2210.03493，2022 年。

+   (82) Kashun Shum, Shizhe Diao 和 Tong Zhang. 从标记数据中自动提示增强与选择的思维链。发表于《计算语言学协会会议记录：EMNLP 2023》，第 12113–12139 页，新加坡，2023 年 12 月。计算语言学协会。

+   (83) Zhuosheng Zhang 等人. 语言模型中的多模态思维链推理。arXiv 预印本 arXiv:2302.00923，2023 年。

+   (84) Haoyang Huang 等人. 并非所有语言在大语言模型中都是平等的：通过跨语言思维提示提升多语言能力。发表于《计算语言学协会会议记录：EMNLP 2023》，第 12365–12394 页，新加坡，2023 年 12 月。计算语言学协会。

+   (85) Li Deng 等人. 使用核深度凸网络和端到端学习进行语音语言理解。发表于 2012 IEEE 语音语言技术研讨会（SLT），第 210–215 页。IEEE，2012 年。

+   (86) Gokhan Tur 等人. 迈向更深层次理解：用于语义发话分类的深度凸网络。发表于 2012 IEEE 国际声学、语音与信号处理会议（ICASSP），第 5045–5048 页。IEEE，2012 年。

+   (87) Daniele Comi 等人. Zero-shot-bert-adapters：一种零样本管道用于未知意图检测。发表于《计算语言学协会会议记录：EMNLP 2023》，第 650–663 页，2023 年。

+   (88) Soham Parikh 等人. 探索零样本和少样本技术用于意图分类。发表于第 61 届计算语言学协会年会（第 5 卷：行业轨道），第 744–751 页，加拿大多伦多，2023 年 7 月。计算语言学协会。

+   (89) Yen-Ting Lin 等人. 使用点对点 V 信息的选择性上下文数据增强进行意图检测。发表于第 17 届欧洲计算语言学协会会议，第 1463–1476 页，克罗地亚杜布罗夫尼克，2023 年 5 月。计算语言学协会。

+   (90) Samuel Coope 等人. Span-ConveRT：基于预训练对话表示的少样本跨度提取。发表于第 58 届计算语言学协会年会，第 107–121 页，在线，2020 年 7 月。计算语言学协会。

+   (91) AB Siddique, Fuad Jamour 和 Vagelis Hristidis. 语言学丰富和上下文感知的零样本槽填充。发表于 2021 年网络会议，第 3279–3290 页，2021 年。

+   (92) Qian Chen, Zhu Zhuo 和 Wen Wang. Bert 用于联合意图分类和槽填充。arxiv. arXiv 预印本 arXiv:1902.10909，2019 年。

+   (93) Hoang Nguyen 等。CoF-CoT：通过粗到细的思维链提示增强大型语言模型以处理多领域 NLU 任务。收录于 2023 年自然语言处理经验方法会议论文集，页码 12109–12119，新加坡，2023 年 12 月。计算语言学协会。

+   (94) Vevake Balaraman 和 Bernardo Magnini。可扩展的神经对话状态追踪。收录于 2019 年 IEEE 自动语音识别与理解研讨会（ASRU）论文集，页码 830–837。IEEE，2019 年。

+   (95) Victor Zhong、Caiming Xiong 和 Richard Socher。用于对话状态追踪的全局-局部自注意力编码器。收录于第 56 届计算语言学协会年会（卷 1：长论文）论文集，页码 1458–1467，2018 年。

+   (96) Hwaran Lee、Jinsik Lee 和 Tae-Yoon Kim。SUMBT：用于通用和可扩展信念追踪的槽-发话匹配。收录于第 57 届计算语言学协会年会论文集，页码 5478–5483，意大利佛罗伦萨，2019 年 7 月。计算语言学协会。

+   (97) Yexiang Wang、Yi Guo 和 Siqi Zhu。多领域对话状态追踪的槽注意力与值归一化。收录于 2020 年自然语言处理经验方法会议（EMNLP）论文集，页码 3019–3028，2020 年。

+   (98) Zhaojiang Lin 等。MinTL：面向任务的对话系统的极简转移学习。收录于 2020 年自然语言处理经验方法会议（EMNLP）论文集，页码 3391–3405，在线，2020 年 11 月。计算语言学协会。

+   (99) Yushi Hu 等。用于少样本对话状态追踪的上下文学习。收录于计算语言学协会会议发现：EMNLP 2022，页码 2627–2643，阿布扎比，阿联酋，2022 年 12 月。计算语言学协会。

+   (100) Yujie Feng 等。面向 LLM 驱动的对话状态追踪。收录于 2023 年自然语言处理经验方法会议论文集，页码 739–755，新加坡，2023 年 12 月。计算语言学协会。

+   (101) Ryuichi Takanobu、Runze Liang 和 Minlie Huang。具有角色感知奖励分解的多智能体任务导向对话策略学习。收录于第 58 届计算语言学协会年会论文集，页码 625–638，在线，2020 年 7 月。计算语言学协会。

+   (102) Sihan Wang 等。通过对偶网络的蒙特卡罗树搜索进行任务完成对话策略学习。收录于 2020 年自然语言处理经验方法会议（EMNLP）论文集，页码 3461–3471，2020 年。

+   (103) Gabriel Gordon-Hall、Philip John Gorinski 和 Shay B. Cohen。从弱示范中学习对话策略。收录于第 58 届计算语言学协会年会论文集，页码 1394–1405，在线，2020 年 7 月。计算语言学协会。

+   (104) Wenhu Chen 等人。通过分层解缠自注意力生成语义条件对话响应。发表于第 57 届计算语言学协会年会论文集，页码 3696–3709，意大利佛罗伦萨，2019 年 7 月。计算语言学协会。

+   (105) YunHao Li 等人。检索与记忆：具有多动作记忆的对话策略学习。发表于计算语言学协会发现：ACL-IJCNLP 2021，页码 447–459，线上，2021 年 8 月。计算语言学协会。

+   (106) Paweł Budzianowski 和 Ivan Vulić。你好，这是 GPT-2 - 我能帮你什么？朝向预训练语言模型在任务导向对话系统中的应用。发表于第 3 届神经生成与翻译研讨会论文集，页码 15–22，中国香港，2019 年 11 月。计算语言学协会。

+   (107) Ehsan Hosseini-Asl 等人。用于任务导向对话的简单语言模型。神经信息处理系统进展，第 33 卷：20179–20191，2020 年。

+   (108) Youngsoo Jang、Jongmin Lee 和 Kee-Eung Kim。Gpt-critic：用于端到端任务导向对话系统的离线强化学习。发表于第 10 届国际学习表征会议，ICLR 2022。国际学习表征会议，ICLR，2022 年。

+   (109) Govardana Sachithanandam Ramachandran、Kazuma Hashimoto 和 Caiming Xiong。[CASPI] 任务导向对话的因果感知安全策略改进。发表于第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文），页码 92–102，爱尔兰都柏林，2022 年 5 月。计算语言学协会。

+   (110) Wanwei He 等人。Galaxy：一种用于任务导向对话的生成预训练模型，结合半监督学习和显式策略注入。发表于 AAAI 人工智能会议论文集，第 36 卷，页码 10749–10757，2022 年。

+   (111) Xiao Yu、Maximillian Chen 和 Zhou Yu。基于提示的蒙特卡洛树搜索用于目标导向对话策略规划。发表于 2023 年自然语言处理经验方法会议论文集，页码 7101–7125，新加坡，2023 年 12 月。计算语言学协会。

+   (112) EHUD REITER 和 ROBERT DALE。构建应用自然语言生成系统。自然语言工程，第 3 卷第 1 期：57–87，1997 年。

+   (113) Tsung-Hsien Wen 等人。使用卷积句子重排序的递归神经网络进行对话中的随机语言生成。发表于第 16 届话语与对话特别兴趣组年会论文集，页码 275–284，捷克共和国布拉格，2015 年 9 月。计算语言学协会。

+   (114) Tsung-Hsien Wen 等. 基于语义条件的 LSTM 自然语言生成用于语音对话系统. 见于 2015 年自然语言处理经验方法会议论文集，第 1711–1721 页，葡萄牙里斯本，2015 年 9 月。计算语言学协会。

+   (115) Hao Zhou, Minlie Huang, 和 Xiaoyan Zhu. 面向语音对话系统的上下文感知自然语言生成. 见于 COLING 2016，第 26 届计算语言学国际会议：技术论文集，第 2032–2041 页，2016 年。

+   (116) Baolin Peng 等. 针对任务导向对话的少样本自然语言生成. 见于计算语言学协会发现：EMNLP 2020，第 172–182 页，在线，2020 年 11 月。计算语言学协会。

+   (117) Zhiyu Chen 等. 具有预训练语言模型的少样本自然语言生成. 见于第 58 届计算语言学协会年会论文集，第 183–190 页，在线，2020 年 7 月。计算语言学协会。

+   (118) Ashutosh Baheti, Alan Ritter, 和 Kevin Small. 用于对话问答的流畅响应生成. 见于第 58 届计算语言学协会年会论文集，第 191–207 页，在线，2020 年 7 月。计算语言学协会。

+   (119) Jing Qian 等. 具有对比前缀的可控自然语言生成. 见于计算语言学协会发现：ACL 2022，第 2912–2924 页，爱尔兰都柏林，2022 年 5 月。计算语言学协会。

+   (120) Baolin Peng 等. Soloist：通过迁移学习和机器教学大规模构建任务机器人. 计算语言学协会学报，9:807–824，2021 年。

+   (121) Yunyi Yang, Yunhao Li, 和 Xiaojun Quan. Ubar：基于 GPT-2 的完全端到端任务导向对话系统. 见于 AAAI 人工智能会议论文集，第 35 卷，第 14230–14238 页，2021 年。

+   (122) Yixuan Su 等. 插拔式任务导向对话系统的多任务预训练. 见于第 60 届计算语言学协会年会论文集（第 1 卷：长篇论文），第 4661–4676 页，爱尔兰都柏林，2022 年 5 月。计算语言学协会。

+   (123) Wanwei He 等. SPACE-2：用于任务导向对话理解的树结构半监督对比预训练. 见于第 29 届计算语言学国际会议论文集，第 553–569 页，韩国庆州，2022 年 10 月。国际计算语言学委员会。

+   (124) Wanwei He 等. 统一对话模型预训练用于任务导向对话理解和生成. 见于第 45 届国际 ACM SIGIR 信息检索研究与发展会议论文集，第 187–200 页，2022 年。

+   (125) Vladimir Karpukhin 等人. 用于开放领域问答的密集段落检索. 载于《2020 年自然语言处理经验方法会议（EMNLP）论文集》，第 6769–6781 页，在线，2020 年 11 月\. 计算语言学协会。

+   (126) Chunyuan Yuan 等人. 用于基于检索的聊天机器人的多轮响应选择的多跳选择网络. 载于《2019 年自然语言处理经验方法会议及第 9 届国际自然语言处理联合会议（EMNLP-IJCNLP）论文集》，第 111–120 页，2019 年。

+   (127) Chongyang Tao 等人. 一次交互可能不够：使用交互-交互网络深入响应选择. 载于《第 57 届计算语言学协会年会论文集》，第 1–11 页，2019 年。

+   (128) Xinchao Xu 等人. 好久不见！具有长期角色记忆的开放领域对话. 载于《计算语言学协会发现：ACL 2022》，第 2639–2650 页，爱尔兰都柏林，2022 年 5 月\. 计算语言学协会。

+   (129) Andrea Madotto 等人. 通过元学习个性化对话代理. 载于《第 57 届计算语言学协会年会论文集》，第 5454–5459 页，2019 年。

+   (130) Ruijun Chen 等人. 学习记忆蕴含和话语关系以实现角色一致的对话. arXiv 预印本 arXiv:2301.04871，2023 年。

+   (131) Juntao Li 等人. 对话历史很重要！多轮基于检索的聊天机器人的个性化响应选择. ACM 信息系统交易（TOIS），39(4):1–25，2021 年。

+   (132) Zhengyi Ma 等人. 每人一个聊天机器人：基于隐式用户档案创建个性化聊天机器人. 载于《第 44 届国际 ACM SIGIR 信息检索研究与开发会议论文集》，第 555–564 页，2021 年。

+   (133) Hanxun Zhong 等人. 少即是多：学习精炼对话历史以生成个性化对话. 载于《2022 年北美计算语言学协会年会：人类语言技术论文集》，第 5808–5820 页，美国西雅图，2022 年 7 月\. 计算语言学协会。

+   (134) Haoyu Song 等人. 生成、删除和重写：改善对话生成中角色一致性的三阶段框架. 载于《第 58 届计算语言学协会年会论文集》，第 5821–5831 页，在线，2020 年 7 月\. 计算语言学协会。

+   (135) Yihong Tang 等人. 通过对比潜变量增强个性化对话生成：结合稀疏与密集角色. 载于《第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）》，第 5456–5468 页，加拿大多伦多，2023 年 7 月\. 计算语言学协会。

+   (136) **塞巴斯蒂安·博尔戈德**等人。《通过从万亿令牌中检索来改进语言模型》。发表于《国际机器学习会议》，页码 2206–2240。PMLR，2022 年。

+   (137) **戈蒂埃·伊扎卡尔**和**爱德华·格雷夫**。《利用生成模型的段落检索进行开放领域问答》。发表于《计算语言学协会第 16 届欧洲分会会议：主卷》，页码 874–880，在线，2021 年 4 月。计算语言学协会。

+   (138) **莱昂纳德·阿道夫斯**等人。《先推理，再响应：知识注入对话的模块化生成》。发表于《计算语言学协会会议记录：EMNLP 2022》，页码 7112–7132，阿布扎比，阿拉伯联合酋长国，2022 年 12 月。计算语言学协会。

+   (139) **德文德拉·辛格**等人。《用于开放领域问答的多文档阅读器和检索器的端到端训练》。发表于《神经信息处理系统进展》，34:25968–25981，2021 年。

+   (140) **肯顿·李**、**明伟·张** 和 **克里斯蒂娜·图塔诺娃**。《弱监督开放领域问答的潜在检索》。发表于《计算语言学协会第 57 届年会会议记录》，页码 6086–6096，佛罗伦萨，意大利，2019 年 7 月。计算语言学协会。

+   (141) **莫杰塔巴·科梅利**、**库尔特·舒斯特** 和 **杰森·韦斯顿**。《互联网增强的对话生成》。发表于《计算语言学协会第 60 届年会会议记录（第 1 卷：长论文）》，页码 8460–8478，都柏林，爱尔兰，2022 年 5 月。计算语言学协会。

+   (142) **安托万·博尔德斯**、**Y-Lan Boureau** 和 **杰森·韦斯顿**。《端到端目标导向对话的学习》。arXiv 预印本 arXiv:1605.07683，2016 年。

+   (143) **马修·亨德森**等人。《智能回复的高效自然语言响应建议》。arXiv 预印本 arXiv:1705.00652，2017 年。

+   (144) **奥里奥尔·维尼亚尔斯** 和 **阮国乐**。《神经对话模型》。arXiv 预印本 arXiv:1506.05869，2015 年。

+   (145) **伊利亚·苏茨克维尔**、**奥里奥尔·维尼亚尔斯** 和 **阮国乐**。《基于神经网络的序列到序列学习》。发表于《神经信息处理系统进展》，27，2014 年。

+   (146) **李锋·尚**、**郑东·卢** 和 **杭利**。《短文本对话的神经响应机器》。发表于《计算语言学协会第 53 届年会及第 7 届国际自然语言处理联合会议（第 1 卷：长论文）》，页码 1577–1586，北京，中国，2015 年 7 月。计算语言学协会。

+   (147) **薛亮·赵**等人。《基于知识的对话生成与预训练语言模型》。发表于《2020 年自然语言处理经验方法会议（EMNLP）》，页码 3377–3390，在线，2020 年 11 月。计算语言学协会。

+   (148) Alessandro Sordoni 等人。用于上下文敏感对话响应生成的神经网络方法。在 2015 年北美计算语言学协会：人类语言技术会议论文集中，页码 196–205，科罗拉多州丹佛，2015 年 5 月-6 月。计算语言学协会。

+   (149) Zhao Yan 等人。Docchat：一种基于信息检索的聊天机器人引擎方法，使用非结构化文档。在第 54 届计算语言学协会年会（第 1 卷：长篇论文）上，页码 516–525，2016 年。

+   (150) Jing Xu、Arthur Szlam 和 Jason Weston。超越金鱼记忆：长期开放领域对话。在第 60 届计算语言学协会年会（第 1 卷：长篇论文）上，页码 5180–5197，爱尔兰都柏林，2022 年 5 月。计算语言学协会。

+   (151) Matthew Henderson、Blaise Thomson 和 Steve Young。基于词的对话状态追踪与递归神经网络。在第 15 届对话与话语特别兴趣小组年会上（SIGDIAL），页码 292–299，2014 年。

+   (152) Chien-Sheng Wu 等人。可转移的多领域状态生成器，用于任务导向对话系统。在第 57 届计算语言学协会年会上，页码 808–819，意大利佛罗伦萨，2019 年 7 月。计算语言学协会。

+   (153) Abhinav Rastogi 等人。迈向可扩展的多领域对话代理：Schema-guided 对话数据集。在 AAAI 人工智能会议论文集中，第 34 卷，页码 8689–8696，2020 年。

+   (154) Kishore Papineni 等人。Bleu：一种自动评估机器翻译的方法。在第 40 届计算语言学协会年会上，页码 311–318，2002 年。

+   (155) Jiwei Li 等人。用于神经对话模型的多样性促进目标函数。在 2016 年北美计算语言学协会：人类语言技术会议论文集中，页码 110–119，加利福尼亚州圣地亚哥，2016 年 6 月。计算语言学协会。

+   (156) Paweł Budzianowski 等人。MultiWOZ - 用于任务导向对话建模的大规模多领域 Wizard-of-Oz 数据集。在 2018 年自然语言处理经验方法会议上，页码 5016–5026，比利时布鲁塞尔，2018 年 10 月-11 月。计算语言学协会。

+   (157) Mihail Eric 等人。MultiWOZ 2.1：一个整合的多领域对话数据集，包含状态修正和状态追踪基线。在第十二届语言资源与评估会议上，页码 422–428，法国马赛，2020 年 5 月。欧洲语言资源协会。

+   (158) Xiaoxue Zang 等人。MultiWOZ 2.2：一个包含额外注释修正和状态跟踪基线的对话数据集。发表于第 2 届自然语言处理与对话人工智能研讨会会议录，第 109–117 页，在线，2020 年 7 月。计算语言学协会。

+   (159) Ting Han 等人。Multiwoz 2.3：一个增强了注释修正和共指注释的多领域任务导向对话数据集。发表于自然语言处理与中文计算：第 10 届 CCF 国际会议，NLPCC 2021，中国青岛，2021 年 10 月 13–17 日，会议录，第十部分，第 206–218 页。施普林格，2021 年。

+   (160) Fanghua Ye, Jarana Manotumruksa 和 Emine Yilmaz。MultiWOZ 2.4：一个多领域任务导向对话数据集，包含重要的注释修正以改善状态跟踪评估。发表于第 23 届话语与对话特别兴趣小组年会会议录，第 351–360 页，英国爱丁堡，2022 年 9 月。计算语言学协会。

+   (161) Jun Quan 等人。RiSAWOZ：一个大规模的多领域 Wizard-of-Oz 数据集，具有丰富的语义注释，用于任务导向对话建模。发表于 2020 年自然语言处理实证方法会议（EMNLP）会议录，第 930–940 页，在线，2020 年 11 月。计算语言学协会。

+   (162) Qi Zhu 等人。Crosswoz：一个大规模的中文跨领域任务导向对话数据集。计算语言学协会会刊，8：281–295，2020 年。

+   (163) Xuewei Wang 等人。为善而劝：迈向一个个性化的劝说对话系统以促进社会公益。发表于第 57 届计算语言学协会年会会议录，第 5635–5649 页，意大利佛罗伦萨，2019 年 7 月。计算语言学协会。

+   (164) Nikola Mrkšić 等人。神经信念跟踪器：数据驱动的对话状态跟踪。发表于第 55 届计算语言学协会年会会议录（第 1 卷：长篇论文），第 1777–1788 页，加拿大温哥华，2017 年 7 月。计算语言学协会。

+   (165) Tsung-Hsien Wen 等人。基于网络的端到端可训练任务导向对话系统。发表于第 15 届计算语言学协会欧洲分会会议：第 1 卷，长篇论文，第 438–449 页，西班牙瓦伦西亚，2017 年 4 月。计算语言学协会。

+   (166) Mihail 等人。Eric。任务导向对话的关键值检索网络。发表于第 18 届 SIGdial 语篇与对话年会会议录，第 37–49 页，德国萨尔布吕肯，2017 年 8 月。计算语言学协会。

+   (167) Saizheng Zhang 等人。个性化对话代理：我有一只狗，你也有宠物吗？发表于第 56 届计算语言学协会年会会议录（第 1 卷：长篇论文），第 2204–2213 页，澳大利亚墨尔本，2018 年 7 月。计算语言学协会。

+   (168) Jiazhan Feng 等人。《MMDialog：大规模多轮对话数据集，面向多模态开放领域对话》。发表于《第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）》第 7348-7363 页，2023 年 7 月。

+   (169) Yanran Li 等人。《DailyDialog：一个人工标注的多轮对话数据集》。发表于《第八届国际自然语言处理联合会议论文集（第 1 卷：长篇论文）》第 986-995 页，2017 年 11 月，台北，台湾。亚洲自然语言处理联合会。

+   (170) Hongjin Qian 等人。《Pchatbot：一个大规模的个性化聊天机器人数据集》。发表于《第 44 届国际 ACM SIGIR 信息检索研究与发展会议论文集》第 2470-2477 页，2021 年。

+   (171) Yinhe Zheng 等人。《具有多样化特征的个性化对话生成》。arXiv 预印本 arXiv:1901.09672，2019 年。

生成于 2024 年 2 月 28 日星期三 03:17:09，由 [LATExml![[LOGO]](img/70e087b9e50c3aa663763c3075b0d6c5.png)](http://dlmf.nist.gov/LaTeXML/)
