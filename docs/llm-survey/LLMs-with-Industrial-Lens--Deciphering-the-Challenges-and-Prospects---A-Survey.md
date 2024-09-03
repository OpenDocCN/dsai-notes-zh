<!--yml

类别: 未分类

日期: 2024-09-03 17:30:52

-->

# 通过工业视角解读 LLM 的挑战与前景 - 调查

> 来源：[`arxiv.org/html/2402.14558`](https://arxiv.org/html/2402.14558)

1.  [1 引言](https://arxiv.org/html/2402.14558v1#S1 "1 引言 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

1.  [2 相关调查](https://arxiv.org/html/2402.14558v1#S2 "2 相关调查 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

1.  [3 基准数据集](https://arxiv.org/html/2402.14558v1#S3 "3 基准数据集 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [3.1 标准数据集](https://arxiv.org/html/2402.14558v1#S3.SS1 "3.1 标准数据集 ‣ 3 基准数据集 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [3.2 应用特定数据集](https://arxiv.org/html/2402.14558v1#S3.SS2 "3.2 应用特定数据集 ‣ 3 基准数据集 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [3.3 使用 LLM 生成数据](https://arxiv.org/html/2402.14558v1#S3.SS3 "3.3 使用 LLM 生成数据 ‣ 3 基准数据集 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

1.  [4 LLM 的现实世界应用](https://arxiv.org/html/2402.14558v1#S4 "4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [4.1 标准 NLP 任务](https://arxiv.org/html/2402.14558v1#S4.SS1 "4.1 标准 NLP 任务 ‣ 4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [4.2 代码生成](https://arxiv.org/html/2402.14558v1#S4.SS2 "4.2 代码生成 ‣ 4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [4.3 可信赖的 AI](https://arxiv.org/html/2402.14558v1#S4.SS3 "4.3 可信赖的 AI ‣ 4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [4.4 检索与推荐](https://arxiv.org/html/2402.14558v1#S4.SS4 "4.4 检索与推荐 ‣ 4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [4.5 安全](https://arxiv.org/html/2402.14558v1#S4.SS5 "4.5 安全 ‣ 4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [4.6 工具和框架](https://arxiv.org/html/2402.14558v1#S4.SS6 "4.6 工具和框架 ‣ 4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

    1.  [4.7 社会影响](https://arxiv.org/html/2402.14558v1#S4.SS7 "4.7 社会影响 ‣ 4 LLM 的现实世界应用 ‣ 通过工业视角解读 LLM 的挑战与前景 - 调查")

1.  [5 评估方法](https://arxiv.org/html/2402.14558v1#S5 "5 评估方法 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

    1.  [5.1 基于词汇重叠的指标](https://arxiv.org/html/2402.14558v1#S5.SS1 "5.1 基于词汇重叠的指标 ‣ 5 评估方法 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

    1.  [5.2 基于语义重叠的指标](https://arxiv.org/html/2402.14558v1#S5.SS2 "5.2 基于语义重叠的指标 ‣ 5 评估方法 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

    1.  [5.3 应用特定的指标](https://arxiv.org/html/2402.14558v1#S5.SS3 "5.3 应用特定的指标 ‣ 5 评估方法 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

    1.  [5.4 基于 LLM 的评估](https://arxiv.org/html/2402.14558v1#S5.SS4 "5.4 基于 LLM 的评估 ‣ 5 评估方法 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [6 部署挑战](https://arxiv.org/html/2402.14558v1#S6 "6 部署挑战 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [7 挑战与未来展望](https://arxiv.org/html/2402.14558v1#S7 "7 挑战与未来展望 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [8 结论](https://arxiv.org/html/2402.14558v1#S8 "8 结论 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [9 局限性](https://arxiv.org/html/2402.14558v1#S9 "9 局限性 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [10 伦理声明](https://arxiv.org/html/2402.14558v1#S10 "10 伦理声明 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [调查论文选择标准](https://arxiv.org/html/2402.14558v1#A1 "附录 A 调查论文选择标准 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [B 现实世界应用中 LLMs 的工业案例研究](https://arxiv.org/html/2402.14558v1#A2 "附录 B 现实世界应用中 LLMs 的工业案例研究 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

    1.  [B.1 分析](https://arxiv.org/html/2402.14558v1#A2.SS1 "B.1 分析 ‣ 附录 B LLMs 在现实世界应用中的工业案例研究 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

1.  [C LLMs 分类](https://arxiv.org/html/2402.14558v1#A3 "附录 C LLMs 分类 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

    1.  [C.1 开源与闭源 LLMs](https://arxiv.org/html/2402.14558v1#A3.SS1 "C.1 开源与闭源 LLMs ‣ 附录 C LLMs 分类 ‣ 从工业视角看 LLMs：解读挑战与前景 – 调查")

    1.  [C.2 提示策略](https://arxiv.org/html/2402.14558v1#A3.SS2 "C.2 提示策略 ‣ 附录 C LLM 分类 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

1.  [D 应用特定数据集](https://arxiv.org/html/2402.14558v1#A4 "附录 D 应用特定数据集 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

1.  [E 杂项应用](https://arxiv.org/html/2402.14558v1#A5 "附录 E 杂项应用 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

1.  [F 评估方法](https://arxiv.org/html/2402.14558v1#A6 "附录 F 评估方法 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

    1.  [F.1 应用特定指标](https://arxiv.org/html/2402.14558v1#A6.SS1 "F.1 应用特定指标 ‣ 附录 F 评估方法 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

    1.  [F.2 人工评估](https://arxiv.org/html/2402.14558v1#A6.SS2 "F.2 人工评估 ‣ 附录 F 评估方法 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

        1.  [F.2.1 标准 NLP 任务](https://arxiv.org/html/2402.14558v1#A6.SS2.SSS1 "F.2.1 标准 NLP 任务 ‣ F.2 人工评估 ‣ 附录 F 评估方法 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

        1.  [F.2.2 工具和框架](https://arxiv.org/html/2402.14558v1#A6.SS2.SSS2 "F.2.2 工具和框架 ‣ F.2 人工评估 ‣ 附录 F 评估方法 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

        1.  [F.2.3 可信 AI](https://arxiv.org/html/2402.14558v1#A6.SS2.SSS3 "F.2.3 可信 AI ‣ F.2 人工评估 ‣ 附录 F 评估方法 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

1.  [G 调查论文检查表](https://arxiv.org/html/2402.14558v1#A7 "附录 G 调查论文检查表 ‣ 从工业视角看 LLM：解密挑战与前景 – 调查")

HTML 转换 [有时会显示错误](https://info.dev.arxiv.org/about/accessibility_html_error_messages.html)，由于内容未能从源代码正确转换。本文使用了以下 HTML 转换工具尚不支持的包。对这些问题的反馈不必要；这些问题已知且正在处理中。

+   失败：inconsolata

作者：通过遵循这些 [最佳实践](https://info.arxiv.org/help/submit_latex_best_practices.html)，从 LaTeX 提交中获得最佳的 HTML 结果。

许可证：CC BY-NC-SA 4.0arXiv:2402.14558v1 [cs.CL] 2024 年 2 月 22 日\useunder

\ul

# 从工业视角看 LLM：解密挑战与前景 – 调查

Ashok Urlana¹   Charaka Vinayak Kumar¹   Ajeet Kumar Singh¹

Bala Mallikarjunarao Garlapati¹   Srinivasa Rao Chalamala¹   Rahul Mishra² TCS Research, Hyderabad, India¹       IIIT Hyderabad²

ashok.urlana@tcs.com, charaka.v@tcs.com, ajeetk.singh1@tcs.com

balamallikarjuna.g@tcs.com, chalamala.srao@tcs.com, rahul.mishra@iiit.ac.in

###### 摘要

大型语言模型（LLMs）已经成为推动众多工业应用的秘密成分，展示了它们在各种任务中的非凡多样性。从自然语言处理和情感分析到内容生成和个性化推荐，它们无与伦比的适应性促进了在各行各业的广泛应用。这一由 LLMs 驱动的变革性转变凸显了探索其使用中潜在挑战和改进途径的必要性。在本文中，我们的目标是揭示和评估在工业背景下利用 LLMs 的障碍和机会。为此，我们进行了一项涉及一组行业从业者的调查，提出了四个基于所收集见解的研究问题，并审查了 68 篇行业论文，以解答这些问题并得出有意义的结论。

## 1 引言

大型语言模型（LLMs）因其在各种预测和生成任务中的卓越表现而获得了广泛关注。尽管它们在各种应用中表现强劲，但仍缺乏专注于 LLMs 在工业应用中的实际利用、相应工业需求及部署挑战的标准化研究。

为了理解 LLMs 在行业中的当前适应状态，我们提出了一个独特的两阶段方法，具体如下：1) 我们针对 LLMs 的行业从业者进行案例研究 2) 从案例研究中，我们框定了几个研究问题，并通过对工业研究工作的调查来解决这些问题。

为了进行案例研究，我们要求行业从业者填写问卷，询问其应用领域、相关任务及其面临的挑战。关于工业案例研究的详细分析可在附录 [B](https://arxiv.org/html/2402.14558v1#A2 "附录 B 真实世界应用中的 LLMs 案例研究 ‣ 从工业视角解读 LLMs 的挑战与前景 – 调查")中找到。我们从若干中型公司获得了 26 份回应。通过这项研究，我们观察到 LLMs 在行业中的应用面临诸如计算需求、隐私问题和开放访问等关键挑战。考虑到这些观察结果，我们提出了以下研究问题以供本文讨论。

RQ1. LLMs 如何协助工业应用，以及具体方式有哪些？ RQ2. 行业关注的主要应用有哪些，包括相关的数据集和评估指 标？ RQ3. 部署过程中有哪些挑战（如果有的话）？ RQ4. 为了最大化 LLMs 在工业应用中的效用，有哪些潜在的方向

<svg class="ltx_picture ltx_centering" height="1571.86" id="S1.F1.pic1" overflow="visible" version="1.1" width="320.69"><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,1571.86) matrix(1 0 0 -1 0 0) translate(127.06,0) translate(0,40.06) matrix(1.0 0.0 0.0 1.0 -127.06 -40.06)"><g class="ltx_nestedsvg" transform="matrix(1 0 0 1 0 0) translate(142.54,0) translate(0,52.7)"><g fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 14.75 -26.44)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 56.82 -26.44)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 102.35 -26.44)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$15$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 147.88 -26.44)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$20$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -109.07 -4.8)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="82.79">杂项</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -119.68 10.58)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="93.4">社会影响</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -75.51 24.7)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="49.24">安全性</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -137.93 36.94)"><foreignobject height="10.38" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="111.66">推荐*</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -94.96 52.33)"><foreignobject height="13.07" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="68.69">推理*</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -80.7 65.41)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="55.19">检索</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -120.6 80.8)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="95.09">可信的人工智能</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -125.09 94.84)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="98.82">代码生成</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -135.86 107.54)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="109.58">工具-框架</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -89.85 121.58)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="63.57">NLP 任务</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 13.99 76.94)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$4$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 4.89 9.58)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$3$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 4.89 23.63)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$3$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 4.89 37.67)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$3$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 23.1 214.5)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 32.21 309.94)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$6$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 41.31 405.37)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$7$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 50.42 500.81)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$8$</

图 1：来自不同应用的论文数量，*与其他应用类别合并的条目。

`<svg class="ltx_picture ltx_centering" height="261.03" id="S1.F2.pic1" overflow="visible" version="1.1" width="663.18"><g transform="translate(0,261.03) matrix(1 0 0 -1 0 0) translate(249.06,0) translate(0,250)"><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 -72.38 -3.46)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="145.14">工业 LLMs 调查</foreignobject></g><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 -244.17 -62.51)"><foreignobject height="13.84" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="89.13">数据集（§[3](https://arxiv.org/html/2402.14558v1#S3 "3 基准数据集 ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")）</foreignobject></g> <g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 -106.58 -62.51)"><foreignobject height="13.84" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="144.67">LLMs 应用（§[4](https://arxiv.org/html/2402.14558v1#S4 "4 现实世界中的 LLMs ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")）</foreignobject></g><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 54.48 -62.51)"><foreignobject height="13.84" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="153.25">评估方法（§[5](https://arxiv.org/html/2402.14558v1#S5 "5 评估方法 ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")）</foreignobject></g><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 183.69 -62.51)"><foreignobject height="13.84" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="225.54">部署（§[6](https://arxiv.org/html/2402.14558v1#S6 "6 部署挑战 ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")） & 讨论（§[7](https://arxiv.org/html/2402.14558v1#S7 "7 挑战与未来展望 ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")）</foreignobject></g> <g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 -220.07 -87.41)"><foreignobject height="13.84" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="137.8">标准数据集（§[3.1](https://arxiv.org/html/2402.14558v1#S3.SS1 "3.1 标准数据集 ‣ 3 基准数据集 ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")） <g fill="#FFFFFF" stroke="#FF00FF" stroke-width="0.4pt"><path d="M -84.58 -90.4 L -217.76 -90.4 C -221.58 -90.4 -224.68 -93.5 -224.68 -97.32 L -224.68 -123.15 C -224.68 -126.97 -221.58 -130.07 -217.76 -130.07 L -84.58 -130.07 C -80.76 -130.07 -77.66 -126.97 -77.66 -123.15 L -77.66 -97.32 C -77.66 -93.5 -80.76 -90.4 -84.58 -90.4 Z M -224.68 -130.07"></path></g><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 -220.07 -104.7)"><foreignobject height="30.44" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="137.8">应用特定（§[3.2](https://arxiv.org/html/2402.14558v1#S3.SS2 "3.2 应用特定数据集 ‣ 3 基准数据集 ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")）</foreignobject></g> <g fill="#FFFFFF" stroke="#FF00FF" stroke-width="0.4pt"><path d="M -84.58 -121.9 L -217.76 -121.9 C -221.58 -121.9 -224.68 -125 -224.68 -128.82 L -224.68 -154.65 C -224.68 -158.47 -221.58 -161.56 -217.76 -161.56 L -84.58 -161.56 C -80.76 -161.56 -77.66 -158.47 -77.66 -154.65 L -77.66 -128.82 C -77.66 -125 -80.76 -121.9 -84.58 -121.9 Z M -224.68 -161.56"></path></g><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 -220.07 -136.2)"><foreignobject height="30.44" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="137.8">使用 LLMs 生成数据（§[3.3](https://arxiv.org/html/2402.14558v1#S3.SS3 "3.3 使用 LLMs 生成数据 ‣ 3 基准数据集 ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")）</foreignobject></g> <g fill="#FFFFFF" stroke="#FF00FF" stroke-width="0.4pt"><path d="M 80.77 -64.81 L -52.41 -64.81 C -56.23 -64.81 -59.33 -67.91 -59.33 -71.73 L -59.33 -97.56 C -59.33 -101.38 -56.23 -104.48 -52.41 -104.48 L 80.77 -104.48 C 84.59 -104.48 87.69 -101.38 87.69 -97.56 L 87.69 -71.73 C 87.69 -67.91 84.59 -64.81 80.77 -64.81 Z M -59.33 -104.48"></path></g><g fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="matrix(1.0 0.0 0.0 1.0 -54.72 -79.11)"><foreignobject height="30.44" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="137.8">标准 NLP 任务（§[4.1](https://arxiv.org/html/2402.14558v1#S4.SS1 "4.1 标准 NLP 任务 ‣ 4 现实世界中的 LLMs ‣ 工业视角的 LLMs：挑战与前景的解读 – 调查")）</foreignobject></g> <g fill="#FFFFFF" stroke="#FF00FF" stroke-width="0.4pt"><path d="M 80

图 2：论文结构。

本研究的目标是回答上述提到的研究问题。为此，我们收集并分析了 68 篇与工业应用相关的研究论文（见附录[A](https://arxiv.org/html/2402.14558v1#A1 "附录 A 调查论文选择标准 ‣ 从工业视角看 LLMs：破解挑战与前景 – 调查")）。此外，我们将选定的论文归类为 8 个广泛的应用领域，如图[1](https://arxiv.org/html/2402.14558v1#S1.F1 "图 1 ‣ 1 介绍 ‣ 从工业视角看 LLMs：破解挑战与前景 – 调查")所示。我们观察到这些应用领域相关论文的分布不均。大多数 LLMs 被用于标准的 NLP 任务 Laskar et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib52)); Yang et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106)); Awasthi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib8))，代码生成任务 Phung et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib80)); Gupta et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib32))，构建工具和框架 Hoshi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib37))。然而，关于安全 Peng et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib78)) 和社会影响 Sun et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib93)) 的应用则关注较少。

一些突出的应用案例包括利用 GPT4 Achiam et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib2)) 自动生成组织会议摘要 Laskar et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib52)) 和将 PaLM Chowdhery et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib18)) 适配用于低资源机器翻译任务 Awasthi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib8))。此外，LLMs 被广泛用于确保用户数据的安全性和隐私 Kim et al. ([2021](https://arxiv.org/html/2402.14558v1#bib.bib47))，减少偏见和提高公平性 Kwon 和 Mihindukulasooriya ([2023](https://arxiv.org/html/2402.14558v1#bib.bib51))。如图[2](https://arxiv.org/html/2402.14558v1#S1.F2 "图 2 ‣ 1 介绍 ‣ 从工业视角看 LLMs：破解挑战与前景 – 调查")所示，我们的调查包括对各种数据集、模型、相关挑战以及未来在工业应用中利用 LLMs 的方向的分析。

本调查的主要贡献包括：1) 据我们所知，这是第一份从工业视角探讨 LLMs 在各种应用中利用的调查；2) 我们进行了一项涉及工业从业者的案例研究，以深入了解 LLMs 的实际应用；3) 我们*深入探讨*了各种数据集、方法和评估指标及其在工业应用中的局限性；4) 我们讨论了部署挑战，并概述了旨在最大化 LLMs 效用的未来方向。

## 2 相关调查

LLMs 的最新出现为各种工业应用的进展提供了重要机会 Hadi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib33)); Kar et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib46))。已经进行了一些综合调查，以增强我们对 LLMs 在不同领域和任务中效果的理解，例如医学 Thirunavukarasu et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib95))、金融 Li et al. ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib55)) 和推理任务 Huang and Chang ([2023](https://arxiv.org/html/2402.14558v1#bib.bib39)); Qiao et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib82))。

在代码生成领域，LLMs 的使用已变得广泛，一项近期的调查 Zan et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib111)) *深入探讨*了相关挑战，包括代码生成和代码完成。一些调查关注 LLMs 的信任方面 Liu et al. ([2023d](https://arxiv.org/html/2402.14558v1#bib.bib63)); Ishihara ([2023](https://arxiv.org/html/2402.14558v1#bib.bib41))，而其他调查则提供了对上下文学习技术 Li ([2023](https://arxiv.org/html/2402.14558v1#bib.bib57))、反馈学习模型 Kirk et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib49))以及 LLMs 适应不断发展的世界知识 Zhang et al. ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib117))的详细探讨。与现有调查不同，我们的工作特别集中于 LLMs 在工业应用中的利用。此外，本调查还提供了数据集、模型、评估指标、相关挑战和未来展望的全面概述。

## 3 基准数据集

本节概述了用于工业应用开发的数据集及其创建方法。这些数据集大致可分为两类： (i) 流行的任务特定基准数据集，(ii) 新提出的数据集，这些数据集是通过 LLMs 自动创建的，来源于标准数据集或由人工注释员手动整理的。RQ2 的一部分在本节中得到了解决。

### 3.1 标准数据集

由于易于访问，我们调查中的许多论文利用了特定任务的标准数据集来评估 LLMs 的性能。数据集及其对应应用的更多细节请参见附录 [D](https://arxiv.org/html/2402.14558v1#A4 "Appendix D Application Specific Datasets ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")。

### 3.2 应用特定的数据集

为了更好地评估 LLMs 的能力，特定任务的数据集比通用数据集更为重要。我们已经识别了这些数据集，并在附录 [D](https://arxiv.org/html/2402.14558v1#A4 "Appendix D Application Specific Datasets ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")中列出了它们。本节描述了特定任务的数据集及其创建策略。

KOSBI。Lee 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib53)) 通过使用 Hyperclova Kim 等人 ([2021](https://arxiv.org/html/2402.14558v1#bib.bib47)) 引入了一个用于韩语的社会偏见检测数据集。该数据集包含上下文-句子对，其中上下文包含标记为安全-不安全的场景，并提到特定的群体，而对应的句子则是文本内容。DELPHI。为减轻 LLMs 中的偏见和公平性问题，Sun 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib93)) 提出了 DELPHI 数据集。数据集中的问题从‘Quora Question Pair’ 数据集¹¹1[`www.kaggle.com/c/quora-question-pairs`](https://www.kaggle.com/c/quora-question-pairs)中挑选出来。WikiBias-Aug。Wan 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib99)) 主要评估 LLMs 生成的推荐信中的性别偏见程度。WikiBias-Aug 数据集是通过从 WikiBias Sun 和 Peng ([2021](https://arxiv.org/html/2402.14558v1#bib.bib94)) 中选择实例并更改男性和女性名字生成的。在另一项研究中，CMExam Liu 等人 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib59)) 引入了一个数据集，用于评估 LLMs 在中文医疗数据的开放式问答任务中的表现。原始数据集收集自中国国家医学考试门户网站。此外，该数据集还在‘GPT-assisted annotation’的帮助下进行了部分精炼，并由两名医疗专业人士进行了审查。Yang 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106)) 提出了 MSQA，这是一个新颖的问答数据集，旨在解决 Microsoft 产品和客户面临的 IT 技术问题。该数据集有助于解决 LLMs 可能忽略的关键领域特定信息的问题。FETA。Alfassy 等人 ([2022](https://arxiv.org/html/2402.14558v1#bib.bib4)) 引入了 FETA 数据集，用于评估和提高 LLMs 在专家领域任务中的表现。它呈现了视觉学习场景，如图像到文本和文本到图像的检索任务。FETA 数据集是从 IKEA 每年的目录²²2[`github.com/ivc-yz/SSR?tab=readme-ov-file`](https://github.com/ivc-yz/SSR?tab=readme-ov-file)中获取的。另一项研究，Mani 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib66)) 通过引入名为 NemoEval 的基准，探索了 LLMs 在网络管理系统中的有效性。数据集中的每个实例包含一个用户查询或网络管理指令和一个由人类专家创建的答案。Zhao 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib119)) 引入了 LoTNLG 和 F2WTQ，以调查 LLMs 的表格到文本能力。LoTNLG 基于 LOGICNLG Chen 等人 ([2020](https://arxiv.org/html/2402.14558v1#bib.bib15)) 测试集，每个条目由两位独立的标注者根据逻辑推理类型进行标注。数据集 F2WTQ 基于 WTQ Pasupat 和 Liang ([2015](https://arxiv.org/html/2402.14558v1#bib.bib75))，这是一个由人类标注的问答数据集。对于 WTQ 中的每个问题，在 F2WTQ 中创建了一个相应条目，包含一个问题和一个关于表格的长句回答。此外，为了解决代码生成和补全任务中的错误，Dinh 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib24)) 提出了 Buggy-HumanEval 和 Buggy-FixEval 数据集。每个数据集的实例包括一个带错误的部分代码片段、一个失败的测试用例和完成的代码。‘buggy-HumanEval’ 是 ‘HumanEval’ Chen 等人 ([2021](https://arxiv.org/html/2402.14558v1#bib.bib14)) 数据集的一个子集，包含 1896 个有错误的程序。而‘buggy-FixEval’ 包含 292 个真实的有错误的程序，这些程序提交于编码竞赛，并从‘FixEval’ Haque ([2023](https://arxiv.org/html/2402.14558v1#bib.bib34)) 和 CodeNet Puri 等人 ([2021](https://arxiv.org/html/2402.14558v1#bib.bib81)) 数据集中改编而来。类似地，Athiwaratkun 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) 引入了 MBXP、Multilingual HumanEval、MathQA-X 数据集，用于评估 LLM 在多编程语言中的代码生成和推理表现。这些数据集改编自 MBPP Austin 等人 ([2021](https://arxiv.org/html/2402.14558v1#bib.bib7))、HumanEvalChen 等人 ([2021](https://arxiv.org/html/2402.14558v1#bib.bib14))、MathQA-pythonSchubotz 等人 ([2018](https://arxiv.org/html/2402.14558v1#bib.bib89))，通过使用 Athiwaratkun 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) 提出的框架将它们转换为多种编程语言。

### 3.3 使用 LLMs 进行数据生成

很少有研究尝试通过利用 LLMs 生成合成数据集。Golde 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib31)）介绍了 FABRICATOR，这是一个开源工具包，用于生成标记数据集，应用于文本分类、蕴含、问答和实体生成等任务，通过零-shot 和少-shot 提示实现。类似地，Yin 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib108)）提出了一种新颖的指令调优数据集的策划范式。Feng 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib25)）提出了一种通过增强输入提示以包含所需对象的布局来提高图像生成模型准确性的方法。多个变体的 GPT 模型已被用于生成 2D 和 3D 图像及场景生成任务中的布局。

## 4 LLMs 在实际应用中的使用

本节概述了在工业应用中使用 LLMs 的多种方法，并回答了（RQ1）。要利用 LLMs 进行任何应用，必须使用适当的提示策略。为了详细说明这一点，我们在附录[C](https://arxiv.org/html/2402.14558v1#A3 "Appendix C Taxonomy of LLMs ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")中包含了提示策略的详细信息。

### 4.1 标准 NLP 任务

摘要。商业文档的摘要在获取文档的关键方面中发挥着至关重要的作用。在他们的工作中，Laskar 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib52)）专注于总结组织会议的自动语音识别（ASR）转录本。他们评估了开源（LLaMA-2 Touvron 等人，[2023](https://arxiv.org/html/2402.14558v1#bib.bib96)）和闭源（GPT-3.5 Brown 等人，[2020](https://arxiv.org/html/2402.14558v1#bib.bib11)，GPT-4 Achiam 等人，[2023](https://arxiv.org/html/2402.14558v1#bib.bib2)，PaLM-2 Anil 等人，[2023](https://arxiv.org/html/2402.14558v1#bib.bib5)）LLMs 在摘要生成中的表现。同样，为了获得电子商务网站的产品标题摘要，Fetahu 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib26)）提出了一种受限于长度、词数和特定短语的指令微调方法。类似地，Jin 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib44)）展示了云服务器中断理解的摘要生成。除此之外，LLMs 还被用于生成说明性文章 Shen 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib90)）和电影描述 Acharya 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib1)）。

局限性：需要关注领域特定数据集的摘要方法泛化和减少事实不准确的问题。

问答系统。为了丰富 LLM 的领域特定知识，杨等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib106)）收集了一个云计算领域的问答数据集，并引入了一种新颖的模型交互范式。该方法包括在领域特定数据上进行语言模型的预训练，并将用户的查询传递给语言模型以提取领域知识。获取的信息和查询作为输入传递给 LLM 进行响应生成。该方法仅适用于英文数据。

为了便于自动化工作流程的生成，曾等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib112)）提出了一种新颖的方法，称为 Flowmind，使用 GPT。它确保了 LLM 与专有代码或数据之间的安全交互，以保护隐私。为了执行视觉问答任务，胡等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib38)）提出了 PROMPTCAP——一种新型的提示引导图像描述技术，它通过提示来描述图像中的视觉实体。PROMPTCAP 在 GPT3 生成的合成示例上进行训练，并且仅限于基于知识的视觉问答任务。

机器翻译。为了获得低资源语言的有效翻译，Awasthi 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib8)）对 LLaMA 进行了少量示例提示，并将英语语义解析数据集翻译成另外 50 种语言。然而，提出的方法受到计算资源可用性的限制。

对话系统：为了构建一个用于公共健康干预的对话系统，Jo 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib45)）设计了 CareCall——一个开放式的 LLM 集成聊天机器人，与特定个人互动，以减少孤独感和情感困扰。CareCall 面临的挑战归因于个性化的限制。类似地，Valencia 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib97)）使用 LLM 来帮助辅助和替代沟通（AAC）用户提供扩展回复和回答传记问题，旨在节省时间和认知精力。

情感分析。邓等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib20)）使用 PaLM-540B，Chowdhery 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib18)）生成了用于金融市场数据情感分析的弱情感标签。这种方法通过使用弱标注数据进行模型训练，优于传统依赖完全标注数据集的方法。

推理。为了评估 LLM 的推理能力，Imani 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib40)) 对使用 GPT-3 的算术问题进行了实验。他们的方法产生了算术问题的多种表示形式，包括代数形式和 Python 形式。这些表示形式可以作为中间步骤，用于推理解决方案。在另一项研究中，Lu 等人 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib64)) 提出了一个即插即用的框架，通过根据任务类型组合外部工具和模块来提升 LLM 在多模态复杂任务上的推理能力。

Li 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib55)) 提出了一个新颖的框架，通过引入基于用户特征（年龄、性别）的‘persona’来增强 LLM 的可操控性。形成了代表不同角色的集群，并将其嵌入到输入提示中，通过软提示引导 LLM。在相关领域，Ye 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib107)) 探索了表格数据上的推理，并提出了一种基于子证据生成推理的独特方法。该策略将复杂的表格数据分解为更小的表格而不丧失任何上下文。类似地，复杂的问题被拆分为简单的 SQL 子查询。在使用较小表格作为证据获取子查询的答案后，得出最终推理答案。所提方法的性能随着上下文长度的增加而下降。

表格到文本生成。这个任务专注于从结构化表格数据中创建连贯且具有上下文准确性的描述。在此概念的基础上，Zhao 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib119)) 进行了研究，调查了 LLM 在不同数据集上的表格到文本能力，并确认了 LLM 准确解读和转换结构化数据为描述性文本的潜力。而 Singha 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib92)) 解决了 LLM 在处理具有不一致性的半结构化表格数据时面临的挑战。Mihindukulasooriya 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib69)) 利用 LLM 来增强表格元数据，并丰富词汇表、分类法或本体。

### 4.2 代码生成

鉴于大规模语言模型（LLMs）是基于大量代码库进行训练的，已经有实验研究评估了 LLMs 在多个任务中的能力，包括代码生成、代码完成、程序修复、提示生成、评分反馈、配对编程、上下文解释和任务综合（Phung et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib80))）。其中一项研究（Li et al. ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib55))）探讨了 LLMs 在用户驱动的网页修改中的应用，特别是对无障碍原因或技术素养较低的用户非常有用。网页的源代码被分割成较小的部分，并与用户修改的提示一起传递给 LLM。

Bairi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib9)) 提出了 CodePlan——一个框架，用于自动化仓库级代码编辑任务，例如包迁移（C#）和多个仓库之间的临时代码编辑（Python），使用的是 GPT-4 模型。然而，CodePlan 可能不适用于动态语言。另一项研究利用 LLMs 通过生成高质量的图形操作代码来提升网络管理体验（Mani et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib66))）。这种方法还解决了任务特定代码生成中的解释性、隐私和可扩展性问题。类似地，Gupta et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib32)) 引入了一种名为 GRACE 的方法，用于预测修复错误或添加新功能的代码编辑，使用的是 CODEX 和 CODET5 Chen et al. ([2021](https://arxiv.org/html/2402.14558v1#bib.bib14)); Bavarian et al. ([2022](https://arxiv.org/html/2402.14558v1#bib.bib10)) 模型。GRACE 可能在需要附加上下文而不仅仅是相关编辑时失败。类似地，Dinh et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib24)) 引入了有缺陷的代码补全问题的概念，以生成可能包含错误的上下文中的代码建议。

Athiwaratkun et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) 引入了一个框架，用于生成超越 Python 的编程语言的基于执行的测试用例。该框架以可扩展的方式将 Python 数据集转换为多种语言。对此方法的评估表明，训练一个多语言模型的效果优于多个单语言模型。另一方面，为了执行基于执行的评估，Ding et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib23)) 引入了一个专门针对 Python 语言的静态评估框架，该框架通过将代码片段解析为抽象语法树（ASTs）来进行操作。

### 4.3 可信赖的人工智能

现在，服务提供商正强调对 AI 的信任，专注于保护数据隐私。为了检测 LLM 中可能的隐私侵犯，Kim 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib48)) 提出了 ProPILE，这是一种使外部用户和内部 LLM 开发人员能够创建自定义提示以识别是否使用了私人数据进行 LLM 训练的工具。为了缓解如固有偏见、泄露私人信息的风险以及关于事实数据的虚假信息等问题，Candel 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib13)) 介绍了一套经过微调的 LLM 及其评估、微调和部署的综合框架。为特别处理‘幻觉’，Ramakrishna 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib85)) 提出了 INVITE——一个作为测试平台的框架，通过故意扭曲有效事实来生成无效问题。

在另一项研究中，Kwon 和 Mihindukulasooriya ([2023](https://arxiv.org/html/2402.14558v1#bib.bib51)) 提出了 Finspector，这是一种允许用户评估模型偏见和公平性的工具，特别是在表现出刻板印象的句子中。Kotek 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib50)) 提到该工具对仅解码器模型的有效性尚未测试。最近，已对齐的模型旨在编码伦理考虑、用户价值，并纳入安全保护措施。为此，Rebedea 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib86)) 介绍了一个开源工具包，简化了向基于 LLM 的对话系统添加可编程保护措施的过程。

### 4.4 检索与推荐

LLM 展现出卓越的语言生成能力，能够执行各种信息检索任务。最近，Liu 等人 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib62)) 概述了一种使用 LLM 改善人际口头沟通的方法，通过主动建议相关的视觉内容，反映对话的视觉意图。作者们实现了 Visual Captions 作为 Chrome 插件，旨在将实时字幕和相关图像直接呈现在摄像头视频流上，用于在线视频会议。

为了提高检索质量，Wang 等人 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib102)) 提出了两种技术：（i）文档扩展 - 通过附加相关术语来丰富文档表示，（ii）查询扩展 - 基于相关反馈重写查询。他们提出了一种查询消歧的方法，其中通过进行少量提示生成新的查询。text-davinci-003 被用来检索伪文档，并将其与原始查询连接起来，形成新的检索任务查询。在这种方法中，推理通过逐字自回归解码策略被放慢。在另一项研究中，Alaofi 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib3)) 探讨了 GPT-3.5 自动生成查询和查询变体的实用性。Alfassy 等人 ([2022](https://arxiv.org/html/2402.14558v1#bib.bib4)) 提出了一种结合了多实例学习 (MIL) 和 CLIP Radford 等人 ([2021](https://arxiv.org/html/2402.14558v1#bib.bib83)) 基础模型的文本到图像和图像到文本检索任务的方法，特别是在非自然图像文档、用户手册、专利和信息图表中使用。

类似地，Lu 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib65)) 提出了一个用于放射学报告生成的大型多模态模型 (LMM)。该 LMM 包含一个视觉编码器（ResNet50 He 等人 ([2016](https://arxiv.org/html/2402.14558v1#bib.bib35))），它以 X 光片作为输入并输出视觉标记。随后，视觉特征嵌入被用作对因果语言模型 (GPT Radford 等人 ([2019](https://arxiv.org/html/2402.14558v1#bib.bib84))) 和 OpenLLaMA-7B Geng 和 Liu ([2023](https://arxiv.org/html/2402.14558v1#bib.bib29))) 的软提示。Yu 等人 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib109)) 提出了一个生成-再读取管道，通过利用 InstructGPT Ouyang 等人 ([2022](https://arxiv.org/html/2402.14558v1#bib.bib72)) 基于给定查询生成上下文文档，然后进行检索以产生最终答案。然而，这种方法在更新知识状态和适应新领域方面能力有限。

尽管传统的基于物品的推荐系统在电子商务平台上已有进展，Sanner 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib88)）还利用基于语言的偏好，通过 LLMs 提供更一致的推荐。Yamazaki 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib105)）建立了一个对话系统，并将其与语音启用的机器人整合，为实时旅游建议提供了更加友好的服务。在另一项研究中，Maragheh 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib67)）专注于评估学习排名模型，这些模型利用从 LLMs 通过产品评论中提取的用户意图，以在浏览电子商务网站时突出显示教育、趣味和耐用性等方面。

### 4.5 安全

通过 API 访问的 LLMs 用于高级推理任务时，也存在模型提取攻击的风险，这可能导致未经授权的复制。为此，Peng 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib78)）提出了一种将水印嵌入语言模型中的方法，这将作为嵌入中的一个后门，以确保可靠的版权验证。

任务特定的微调 LLMs 通常会引发显著的法律问题，如违反许可协议和版权侵权。为了解决这一关键需求，Foley 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib27)）提出了一种 LLM 归属方法。这种方法将微调模型与其原始基础模型联系起来，确保了 LLMs 的完整性和负责任的使用。然而，这项研究缺乏对大规模微调模型的分析。此外，在网络威胁情报方面取得了重大进展，Park 和 You（[2023](https://arxiv.org/html/2402.14558v1#bib.bib74)）利用预训练的 CTI-BERT 模型来增强网络安全，提升了威胁情报系统的准确性。

### 4.6 工具和框架

LLMs 通过提供访问复杂的框架和工具，显著推动了各个领域技术的发展和评估。值得注意的是，Hoshi 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib37)) 引入了 RALLE，这是一个用于开发检索增强 LLMs 以解决幻觉问题的框架。其他创新应用包括利用 LLMs 进行交互式 3D 对象创建 De La Torre 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib19)) 和放射学领域的特定评估 Liu 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib61))，以及 Dibia ([2023](https://arxiv.org/html/2402.14558v1#bib.bib22)) 的 LIDA 用于自动可视化生成。像 PromptInfuser 这样的工具通过 LLM 提示将 AI 集成到模型中 Petridis 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib79))，而另一种工具 Singh 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib91)) 使用少量提示与 LLMs 生成机器人编程指令。此外，Saadany 和 Orasan ([2023](https://arxiv.org/html/2402.14558v1#bib.bib87)) 的研究利用 GPT 将法院判决与听证会相关联，改进了法律分析。Wang 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib101)) 探索了 LLMs 在移动 UI 对话界面的应用，但未能处理无关和幻觉响应。相反，Zhang 等人 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib114)) 展示了 LLMs 在通过“自有技能”引导自动适应新领域的使用。

### 4.7 社会影响

LLMs 的广泛应用必须以解决潜在的社会和人类风险为前提，如毒性和偏见，这些风险可能对社会产生不利影响。为了减轻 LLMs 中的不安全社会偏见，Lee 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib53)) 开发了一个大规模数据集 - KOSBI，重点关注韩语和文化。它采用基于过滤的审核来减少 LLM 生成内容中的社会偏见。Sun 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib93)) 研究了 LLMs 与争议性问题的互动，并提出了增强其理解和管理复杂社会辩论的方法。同样，Goecks 和 Waytowich ([2023](https://arxiv.org/html/2402.14558v1#bib.bib30)) 引入了 DisasterResponseGPT，这是一种通过利用 LLMs 生成可操作计划的框架，用于高效的灾害响应策略制定，提供了一种潜在的解决方案以改进灾害响应操作。该框架无法处理基于图像的输入。附录 [E](https://arxiv.org/html/2402.14558v1#A5 "附录 E 杂项应用 ‣ LLMs 与工业视角：解读挑战与前景 – 一项调查") 中详细分析了各种应用。

## 5 评估方法

本节主要讨论各种评估指标，并通过将评估指标分组到以下类别中来回答 RQ2。

### 5.1 基于词汇重叠的指标

由于其简便性，我们的研究中许多工作利用了基于词汇重叠的指标，这些指标通过源语言和目标语言之间的 n-gram 匹配来衡量对齐得分。

示例：BLEU Papineni 等人（[2002](https://arxiv.org/html/2402.14558v1#bib.bib73)），ROUGE Lin（[2004](https://arxiv.org/html/2402.14558v1#bib.bib58)），METEOR Denkowski 和 Lavie（[2014](https://arxiv.org/html/2402.14558v1#bib.bib21)），准确率，F1 分数，精确匹配。

### 5.2 基于语义重叠的指标。

基于语义重叠的指标利用从预训练语言模型中获得的上下文嵌入来评估金标准和系统生成输出之间的相似性。示例：BERTScore Zhang* 等人（[2020](https://arxiv.org/html/2402.14558v1#bib.bib116)），AlignScore Zha 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib113)）。

### 5.3 应用特定指标

本节描述了与每个应用相关的任务特定指标，详细的指标列表在附录 [F](https://arxiv.org/html/2402.14558v1#A6 "Appendix F Evaluation Approaches ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 表 [5](https://arxiv.org/html/2402.14558v1#A6.T5 "Table 5 ‣ F.1 Application Specific Metrics ‣ Appendix F Evaluation Approaches ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 中提到。

表格到文本生成。（a）SP-Acc：通过从生成的句子中提取意义表示并与表格对比来验证正确性，而 NLI-Acc 则通过利用预训练的 TableBERT Chen et al. ([2020](https://arxiv.org/html/2402.14558v1#bib.bib15))模型作为忠实度分类器。（b）TAPAS-Acc 和 TAPEX-Acc 指标使用了 TAPAS Herzig et al. ([2020](https://arxiv.org/html/2402.14558v1#bib.bib36))和 TAPEX Liu et al. ([2021](https://arxiv.org/html/2402.14558v1#bib.bib60))模型作为基础，这些模型在 TableFact Chen et al. ([2019](https://arxiv.org/html/2402.14558v1#bib.bib16))数据集上进行了微调。问答系统。（a）Keyword/Span-Hit-Rate - 通过从实际答案中提取关键词或跨度集来创建一个独特的关键词或跨度集，并测量生成响应中的命中率 Yang et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106))。（b）Can-Answer-Rate - 表示可回答问题的百分比并评估信息性 Yang et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106))。检索和推荐系统。为了评估 LLM 推荐的性能，使用了 Hit Rate、Normalized Discount Cumulative Gain 和 Mean Reciprocal Rank 等指标。（a）Rank Biased Overlap：量化各种查询变体中检索到的搜索结果的一致性 Webber et al. ([2010](https://arxiv.org/html/2402.14558v1#bib.bib103))。（b）Rank Biased Precision：衡量预期文档相关性与预期检查文档数量的比例 Moffat and Zobel ([2008](https://arxiv.org/html/2402.14558v1#bib.bib70))。社会影响。（a）Controversy Acknowledgement Rate：如果 LLM 的回应包含"作为一个 AI 语言模型..."，则提醒回应是非人类视角，并且通常用作争议认可率的指标。（b）Comprehensiveness Answer Rate：测量 LLM 的回应多样性和在实际场景下的广泛知识 Sun et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib93))；Alaofi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib3))。代码生成。（a）Block metrics：旨在识别需要修改的代码块。（b）Edit metrics：测量代码修改的正确性 Bairi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib9))。（c）pass@k：要求 k 次生成来解决给定的问题，如果任何生成成功通过相应的单元测试，则认为问题已解决 Chen et al. ([2021](https://arxiv.org/html/2402.14558v1#bib.bib14))。值得信赖的 AI。词嵌入关联测试（WEAT）：评估和量化词嵌入中不同词集之间的关联 Caliskan et al. ([2017](https://arxiv.org/html/2402.14558v1#bib.bib12))。

### 5.4 基于 LLM 的评估

最近的一项研究 Yang 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106)) 将 LLM 用作评估器，根据与基准答案的相似性对响应进行排名。由于篇幅限制，我们将人类评估的详细信息包含在附录 [F](https://arxiv.org/html/2402.14558v1#A6 "Appendix F Evaluation Approaches ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 第 [F.2](https://arxiv.org/html/2402.14558v1#A6.SS2 "F.2 Human Evaluation ‣ Appendix F Evaluation Approaches ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 节中。

## 6 部署挑战

在本节中，我们讨论了一些我们研究中观察到的潜在部署挑战和解决方案（RQ3）。

潜在隐私风险。将 LLM 部署在云平台上需要强大的数据隐私和安全协议，以管理大量敏感数据集。主要挑战包括防止数据泄露和未经授权的信息提取。实施强大的安全和隐私技术对于保护用户数据至关重要，同时确保 LLM 保持功能性。

基础设施。基础设施对于部署 LLM 至关重要，影响诸如处理速度、延迟、成本和培训需求等因素。高性能硬件的必要性可以提升速度并减少延迟，从而改善用户体验，但成本高昂，需要仔细预算。在成本和性能之间实现最佳平衡对于 LLM 应用的高效培训和可扩展性至关重要。

控制人工智能的主动性水平。LLMs 应减少社交尴尬，提高表达能力，并适应不同场景 Liu 等 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib62))。此外，LLMs 的开放性特征使得在公共卫生干预应用中定制对话系统变得困难 Jo 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib45))。

法规。欧洲的 GDPR 和加利福尼亚的 CCPA 为部署 LLMs 引入了重大障碍，通过实施严格的数据处理和知识产权规则，要求透明度和公平性。这些法律要求在不同的法规之间进行导航，从而使 LLM 的部署变得复杂。正如 Mesko 和 Topol ([2023](https://arxiv.org/html/2402.14558v1#bib.bib68)) 所强调的，在像医疗保健这样的敏感领域遵守这些法律对于避免伤害和保护隐私至关重要。因此，开发一个全面的 LLM 合规框架对于负责任的使用和与用户的互动是必要的。

## 7 挑战与未来展望

在本节中，我们讨论了各种挑战和未来展望，以最大化 LLM 在工业应用中的效用（RQ4）。

在医疗保健、零售和金融领域最大化 LLM 的潜力需要高质量的标注数据集。此外，由于大多数 LLM 限于英语，因此在创建强大的多语言模型方面还有很大的空间。

LLMs 在情感支持和长期记忆方面面临挑战，这影响了对话应用，Jo 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib45)）。在法律、金融和医疗等领域，将 LLMs 与人工反馈结合至关重要，以降低假阳性，突显了在人身安全关键应用中的人工监督的重要性，Liu 等人（[2023b](https://arxiv.org/html/2402.14558v1#bib.bib61)）。此外，我们在附录[F.2](https://arxiv.org/html/2402.14558v1#A6.SS2 "F.2 Human Evaluation ‣ Appendix F Evaluation Approaches ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")中详细分析发现，少于 15%的研究进行人工评估以评估 LLM 输出，这表明需要更多严格的验证方法。

尽管 LLMs 已在灾难响应管理（Goecks 和 Waytowich（[2023](https://arxiv.org/html/2402.14558v1#bib.bib30)））、公共健康干预（Jo 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib45)））和辅助 AAC 用户（Valencia 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib97)））等应用中得到采用，但在隐私和安全方面却明显缺乏关注。此外，必须解决在高风险场景中部署 LLMs 可能带来的潜在风险。

随着对多模态应用的需求上升，只有少数研究集中于将 LLMs 应用于此类工业应用，Feng 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib25)）；Lu 等人（[2023b](https://arxiv.org/html/2402.14558v1#bib.bib65)）。同样，需要更多的努力将 LLMs 与语音助手和机器人技术整合，Yamazaki 等人（[2023](https://arxiv.org/html/2402.14558v1#bib.bib105)）。如图[7](https://arxiv.org/html/2402.14558v1#A3.F7 "Figure 7 ‣ C.2 Prompting Strategies ‣ Appendix C Taxonomy of LLMs ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")所示，我们发现超过 70%的基于 LLM 的项目仍处于概念阶段。

## 8 结论

本调查*深入探讨*了从工业角度利用大型语言模型（LLMs），特别是关注识别采纳挑战和有前景的使用案例。此外，还*详细审查*了使用的数据集、方法论和评估指标及其在不同工业应用中的局限性。通过解决部署挑战和提出未来方向，本调查为工业界优化 LLMs 在运营中的效果提供了*战略性路线图*。我们计划维护 GitHub 库，以便跟进该领域的最新论文。

## 9 限制

随着大语言模型（LLMs）的快速发展和该领域大量的研究，全面覆盖所有论文是不切实际的。认识到这一点，我们的调查特别关注了与行业相关的论文。这使我们能够更深入地理解 LLMs 在工业应用中的独特需求和挑战。由于篇幅限制，我们无法包括所有技术细节。检索增强生成（RAG）通过引入超出静态训练数据的外部知识来提升 LLMs 的性能。然而，本次调查特别审视了 LLMs 的行业应用，尽量少涉及 RAG，以便专注于其直接应用和固有挑战。

## 伦理声明

据我们所知，本研究存在的伦理问题极少。然而，为了保持透明性，我们在附录[G](https://arxiv.org/html/2402.14558v1#A7 "Appendix G Survey Papers Checklist ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")中提供了对调查中所有 68 篇论文的详细分析。每篇论文至少由三位人士审阅以验证其声明和发现。此外，我们在案例研究中没有收集任何个人信息。

## 参考文献

+   Acharya 等（2023）Arkadeep Acharya、Brijraj Singh 和 Naoyuki Onoe。2023 年。[基于 LLM 的推荐系统项描述生成](https://dl.acm.org/doi/abs/10.1145/3604915.3610647)。在*第 17 届 ACM 推荐系统会议论文集*，第 1204–1207 页。

+   Achiam 等（2023）Josh Achiam、Steven Adler、Sandhini Agarwal、Lama Ahmad、Ilge Akkaya、Florencia Leoni Aleman、Diogo Almeida、Janko Altenschmidt、Sam Altman、Shyamal Anadkat 等。2023 年。Gpt-4 技术报告。*arXiv 预印本 arXiv:2303.08774*。

+   Alaofi 等（2023）Marwah Alaofi、Luke Gallagher、Mark Sanderson、Falk Scholer 和 Paul Thomas。2023 年。[生成型 LLMs 能否为测试集合创建查询变体？一项探索性研究](https://dl.acm.org/doi/abs/10.1145/3539618.3591960)。在*第 46 届国际 ACM SIGIR 信息检索研究与发展会议论文集*，第 1869–1873 页。

+   Alfassy 等（2022）Amit Alfassy、Assaf Arbelle、Oshri Halimi、Sivan Harary、Roei Herzig、Eli Schwartz、Rameswar Panda、Michele Dolfi、Christoph Auer、Peter Staar 等。2022 年。[Feta: Towards specializing foundational models for expert task applications](https://proceedings.neurips.cc/paper_files/paper/2022/hash/c12dd3034259fc000d80db823041c187-Abstract-Datasets_and_Benchmarks.html)。*神经信息处理系统的进展*，35:29873–29888。

+   Anil 等（2023）Rohan Anil、Andrew M Dai、Orhan Firat、Melvin Johnson、Dmitry Lepikhin、Alexandre Passos、Siamak Shakeri、Emanuel Taropa、Paige Bailey、Zhifeng Chen 等。2023 年。[Palm 2 技术报告](https://arxiv.org/abs/2305.10403)。*arXiv 预印本 arXiv:2305.10403*。

+   Athiwaratkun et al. (2023) Ben Athiwaratkun, Sanjay Krishna Gouda, Zijian Wang, Xiaopeng LI, Yuchen Tian, Ming Tan, Wasi Ahmad, Shiqi Wang, Qing Sun, Mingyue Shang, Sujan Gonugondla, Hantian Ding, Varun Kumar, Nathan Fulton, Arash Farahani, Siddhartha Jain, Robert Giaquinto, Haifeng Qian, Murali Krishna Ramanathan, Ramesh Nallapati, Baishakhi Ray, Parminder Bhatia, Sudipta Sengupta, Dan Roth, 和 Bing Xiang. 2023. [多语言代码生成模型的评估](https://www.amazon.science/publications/multi-lingual-evaluation-of-code-generation-models)。在 *ICLR 2023*。

+   Austin et al. (2021) Jacob Austin, Augustus Odena, Maxwell Nye, Maarten Bosma, Henryk Michalewski, David Dohan, Ellen Jiang, Carrie Cai, Michael Terry, Quoc Le, 等. 2021. [使用大型语言模型进行程序合成](https://arxiv.org/abs/2108.07732)。*arXiv 预印本 arXiv:2108.07732*。

+   Awasthi et al. (2023) Abhijeet Awasthi, Nitish Gupta, Bidisha Samanta, Shachi Dave, Sunita Sarawagi, 和 Partha Talukdar. 2023. [利用大型语言模型引导多语言语义解析器的自启动](https://doi.org/10.18653/v1/2023.eacl-main.180)。在 *第 17 届欧洲计算语言学协会会议论文集* 中，页码 2455–2467，克罗地亚杜布罗夫尼克。计算语言学协会。

+   Bairi et al. (2023) Ramakrishna Bairi, Atharv Sonwane, Aditya Kanade, Arun Iyer, Suresh Parthasarathy, Sriram Rajamani, B Ashok, Shashank Shet, 等. 2023. [Codeplan: 使用大型语言模型和规划进行仓库级编码](https://arxiv.org/abs/2309.12499)。*arXiv 预印本 arXiv:2309.12499*。

+   Bavarian et al. (2022) Mohammad Bavarian, Angela Jiang, Heewoo Jun, 和 Henrique Pondé. 2022. [新的 GPT-3 能力: 编辑 & 插入](https://openai.com/blog/gpt-3-edit-insert)。OpenAI 博客。

+   Brown et al. (2020) Tom Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared D Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, 等. 2020. [语言模型是少量样本学习者](https://papers.nips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html)。*神经信息处理系统进展*, 33:1877–1901。

+   Caliskan et al. (2017) Aylin Caliskan, Joanna J Bryson, 和 Arvind Narayanan. 2017. [从语言语料库自动导出的语义包含类似人类的偏见](https://www.science.org/doi/abs/10.1126/science.aal4230)。*科学*, 356(6334):183–186.

+   Candel et al. (2023) Arno Candel, Jon McKinney, Philipp Singer, Pascal Pfeiffer, Maximilian Jeblick, Chun Ming Lee, 和 Marcos Conde. 2023. [H2O 开放生态系统用于最先进的大型语言模型](https://doi.org/10.18653/v1/2023.emnlp-demo.6)。在 *2023 年自然语言处理实证方法会议: 系统演示* 中，页码 82–89，新加坡。计算语言学协会。

+   Chen 等（2021）马克·陈、杰瑞·特沃雷克、许宇·俊、齐明·袁、亨里克·庞德·德·奥利维拉·平托、贾里德·卡普兰、哈里·爱德华兹、尤里·布尔达、尼古拉斯·约瑟夫、格雷格·布罗克曼等。2021 年。 [评估针对代码训练的大语言模型](https://arxiv.org/abs/2107.03374)。*arXiv 预印本 arXiv:2107.03374*。

+   Chen 等（2020）文华·陈、建书·陈、余苏、智宇·陈和威廉·杨·王。2020 年。 [从开放域表格生成逻辑自然语言](https://doi.org/10.18653/v1/2020.acl-main.708)。在*第 58 届计算语言学协会年会论文集*，第 7929–7942 页，在线。计算语言学协会。

+   Chen 等（2019）文华·陈、洪敏·王、建书·陈、云凯·张、洪王、世扬·李、习尤·周和威廉·杨·王。2019 年。 [Tabfact：一个大规模的表格基础事实验证数据集](https://openreview.net/pdf?id=rkeJRhNYDH)。*国际学习表征会议*。

+   Chen 等（2023）尹芳·陈、华冰·谢、明华·马、余康、辛高、刘石、云杰·曹、薛东·高、浩范、明温等。2023 年。 [通过大语言模型增强云事件的实际根本原因分析](https://arxiv.org/abs/2305.15778)。*arXiv 预印本 arXiv:2305.15778*。

+   Chowdhery 等（2023）阿坎莎·乔杜赫里、沙兰·纳朗、雅各布·德夫林、马滕·博斯玛、考拉夫·米什拉、亚当·罗伯茨、保罗·巴赫姆、徐熙俊、查尔斯·萨顿、塞巴斯蒂安·格尔曼等。2023 年。 [Palm：利用路径扩展语言建模](https://www.jmlr.org/papers/volume24/22-1144/22-1144.pdf)。*机器学习研究期刊*，24(240)：1–113。

+   De La Torre 等（2023）费尔南达·德·拉·托雷、凯西·梦莹·方、韩·黄、安德烈·班布斯基-法赫、朱迪斯·阿莫雷斯·费尔南德斯和贾伦·拉尼尔。2023 年。 [Llmr：利用大语言模型实时提示交互式世界](https://arxiv.org/abs/2309.12276)。*arXiv 预印本 arXiv:2309.12276*。

+   Deng 等（2023）向·邓、瓦西丽莎·巴什洛夫金娜、冯·汉、西蒙·鲍姆加特纳和迈克尔·本德斯基。2023 年。 [大语言模型对金融市场的了解？一个关于 Reddit 市场情绪分析的案例研究](https://dl.acm.org/doi/abs/10.1145/3543873.3587324)。在*ACM Web 会议 2023 附录*，第 107–110 页。

+   Denkowski 和 Lavie（2014）迈克尔·丹科斯基和阿隆·拉维。2014 年。 [Meteor universal：针对任何目标语言的语言特定翻译评估](https://doi.org/10.3115/v1/W14-3348)。在*第九届统计机器翻译研讨会论文集*，第 376–380 页，美国马里兰州巴尔的摩。计算语言学协会。

+   迪比亚（2023）维克多·迪比亚。2023 年。[LIDA: 使用大型语言模型自动生成语法无关的可视化和信息图表的工具](https://doi.org/10.18653/v1/2023.acl-demo.11)。收录于*第 61 届计算语言学协会年会论文集（第 3 卷：系统演示）*，第 113–126 页，加拿大多伦多。计算语言学协会。

+   丁等（2023）丁汉天，库马尔·瓦伦，田宇晨，王紫剑，罗布·克维亚特科夫斯基，李小鹏，穆拉利·克里希纳·拉马纳坦，雷拜沙基，帕明德尔·巴蒂亚，苏迪普塔·森古普塔。2023 年。[大型语言模型的代码补全静态评估](https://doi.org/10.18653/v1/2023.acl-industry.34)。收录于*第 61 届计算语言学协会年会论文集（第 5 卷：行业跟踪）*，第 347–360 页，加拿大多伦多。计算语言学协会。

+   丁等（2023）邓团，赵金满，谭森森，雷纳托·内格里诺，伦纳德·劳森，谢尚，乔治·卡里皮斯。2023 年。[代码的语言模型在完成可能有缺陷的代码时表现不佳](https://arxiv.org/abs/2306.03438)。*arXiv 预印本 arXiv:2306.03438*。

+   冯等（2023）冯伟西，朱万荣，傅子睿，贾帕尼·瓦伦，阿尔君·阿库拉，赫学海，苏加托·巴苏，王新·艾瑞克，王威廉·杨。2023 年。[Layoutgpt: 使用大型语言模型进行组合视觉规划和生成](https://arxiv.org/abs/2305.15393)。*arXiv 预印本 arXiv:2305.15393*。

+   费塔胡等（2023）贝斯尼克·费塔胡，陈志宇，奥列格·罗赫连科，舍尔文·马尔马斯。2023 年。[InstructPTS: 产品标题总结的指令微调 LLMs](https://doi.org/10.18653/v1/2023.emnlp-industry.63)。收录于*2023 年自然语言处理实证方法会议：行业跟踪论文集*，第 663–674 页，新加坡。计算语言学协会。

+   福来等（2023）迈尔斯·福来，阿姆布里什·拉瓦特，李泰生，侯宇芳，加布里埃尔·皮科，朱利奥·齐佐。2023 年。[匹配对：将微调模型归因于其预训练的大型语言模型](https://doi.org/10.18653/v1/2023.acl-long.410)。收录于*第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 7423–7442 页，加拿大多伦多。计算语言学协会。

+   加迪拉朱等（2023）维尼莎·加迪拉朱，肖恩·凯恩，苏尼帕·德夫，亚历克斯·泰勒，丁旺，艾米莉·丹顿，罗宾·布鲁尔。2023 年。[“我不会说冒犯，但……”：关于大型语言模型的以残疾为中心的观点](https://dl.acm.org/doi/10.1145/3593013.3593989)。收录于*2023 年 ACM 公平、问责制与透明度会议论文集*，第 205–216 页。

+   耿和刘（2023）耿新阳和刘浩。2023 年。[Openllama: 一个开源的 llama 复现](https://github.com/openlm-research/open_llama)。*网址: https://github.com/openlm-research/open_llama*。

+   Goecks and Waytowich (2023) Vinicius G Goecks 和 Nicholas R Waytowich. 2023. [Disasterresponsegpt: 用于灾难响应场景中加速行动计划开发的大型语言模型](https://arxiv.org/abs/2306.17271)。*arXiv 预印本 arXiv:2306.17271*。

+   Golde et al. (2023) Jonas Golde, Patrick Haller, Felix Hamborg, Julian Risch, 和 Alan Akbik. 2023. [Fabricator: 一个用于生成带标签训练数据的开源工具包，借助教师 LLMs](https://doi.org/10.18653/v1/2023.emnlp-demo.1)。在*2023 年自然语言处理经验方法会议：系统演示*论文集中，页码 1–11，新加坡。计算语言学协会。

+   Gupta et al. (2023) Priyanshu Gupta, Avishree Khare, Yasharth Bajpai, Saikat Chakraborty, Sumit Gulwani, Aditya Kanade, Arjun Radhakrishna, Gustavo Soares, 和 Ashish Tiwari. 2023. [Grace: 语言模型与代码编辑的融合](https://dl.acm.org/doi/10.1145/3611643.3616253)。在*第 31 届 ACM 联合欧洲软件工程会议与软件工程基础研讨会论文集*中，页码 1483–1495。

+   Hadi et al. (2023) Muhammad Usman Hadi, R Qureshi, A Shah, M Irfan, A Zafar, MB Shaikh, N Akhtar, J Wu, 和 S Mirjalili. 2023. [关于大型语言模型的调查：应用、挑战、局限性和实际使用](https://www.techrxiv.org/doi/full/10.36227/techrxiv.23589741.v1)。*TechRxiv*。

+   Haque (2023) Md Mahim Anjum Haque. 2023. [*Fixeval: 基于执行的程序修复评估，用于竞技编程问题*](https://vtechworks.lib.vt.edu/server/api/core/bitstreams/6bcd91e8-5d5f-4238-bced-79a69d8deacb/content)。博士论文，维吉尼亚理工大学。

+   He et al. (2016) Kaiming He, Xiangyu Zhang, Shaoqing Ren, 和 Jian Sun. 2016. [深度残差学习用于图像识别](https://ieeexplore.ieee.org/document/7780459)。在*IEEE 计算机视觉与模式识别会议论文集*，页码 770–778。

+   Herzig et al. (2020) Jonathan Herzig, Pawel Krzysztof Nowak, Thomas Müller, Francesco Piccinno, 和 Julian Eisenschlos. 2020. [TaPas: 通过预训练进行弱监督表格解析](https://doi.org/10.18653/v1/2020.acl-main.398)。在*第 58 届计算语言学协会年会上*，页码 4320–4333，在线。计算语言学协会。

+   Hoshi et al. (2023) Yasuto Hoshi, Daisuke Miyashita, Youyang Ng, Kento Tatsuno, Yasuhiro Morioka, Osamu Torii, 和 Jun Deguchi. 2023. [Ralle: 用于开发和评估检索增强大型语言模型的框架](https://aclanthology.org/2023.emnlp-demo.4/)。在*2023 年自然语言处理经验方法会议：系统演示*论文集中，页码 52–69。

+   Hu 等 (2023) Yushi Hu, Hang Hua, Zhengyuan Yang, Weijia Shi, Noah A. Smith 和 Jiebo Luo。2023. [Promptcap: 使用 GPT-3 的提示引导图像描述用于视觉问答](https://openaccess.thecvf.com/content/ICCV2023/html/Hu_PromptCap_Prompt-Guided_Image_Captioning_for_VQA_with_GPT-3_ICCV_2023_paper.html)。载于 *IEEE/CVF 国际计算机视觉会议 (ICCV) 论文集*，页面 2963–2975。

+   Huang 和 Chang (2023) Jie Huang 和 Kevin Chen-Chuan Chang. 2023. [面向大型语言模型的推理：综述](https://doi.org/10.18653/v1/2023.findings-acl.67)。载于 *计算语言学协会年会论文集：ACL 2023*，页面 1049–1065，多伦多，加拿大。计算语言学协会。

+   Imani 等 (2023) Shima Imani, Liang Du 和 Harsh Shrivastava。2023. [MathPrompter: 使用大型语言模型进行数学推理](https://doi.org/10.18653/v1/2023.acl-industry.4)。载于 *计算语言学协会第 61 届年会 (第五卷：工业专场)*，页面 37–42，多伦多，加拿大。计算语言学协会。

+   Ishihara (2023) Shotaro Ishihara. 2023. [从预训练语言模型中提取训练数据：综述](https://doi.org/10.18653/v1/2023.trustnlp-1.23)。载于 *第三届可信自然语言处理研讨会论文集 (TrustNLP 2023)*，页面 260–275，多伦多，加拿大。计算语言学协会。

+   Jiang 等 (2023a) Albert Q Jiang, Alexandre Sablayrolles, Arthur Mensch, Chris Bamford, Devendra Singh Chaplot, Diego de las Casas, Florian Bressand, Gianna Lengyel, Guillaume Lample, Lucile Saulnier 等。2023a. [Mistral 7b](https://arxiv.org/abs/2310.06825)。*arXiv 预印本 arXiv:2310.06825*。

+   Jiang 等 (2023b) Huiqiang Jiang, Qianhui Wu, Chin-Yew Lin, Yuqing Yang 和 Lili Qiu。2023b. [LLMLingua: 压缩提示以加速大型语言模型推理](https://doi.org/10.18653/v1/2023.emnlp-main.825)。载于 *2023 年自然语言处理经验方法会议论文集*，页面 13358–13376，新加坡。计算语言学协会。

+   Jin 等 (2023) Pengxiang Jin, Shenglin Zhang, Minghua Ma, Haozhe Li, Yu Kang, Liqun Li, Yudong Liu, Bo Qiao, Chaoyun Zhang, Pu Zhao 等。2023. [评估与总结：利用大型语言模型提升停机理解](https://arxiv.org/abs/2305.18084)。*arXiv 预印本 arXiv:2305.18084*。

+   Jo 等 (2023) Eunkyung Jo, Daniel A Epstein, Hyunhoon Jung 和 Young-Ho Kim。2023. [理解利用大型语言模型进行公共健康干预的对话 AI 部署的好处与挑战](https://dl.acm.org/doi/10.1145/3544548.3581503)。载于 *2023 年 CHI 计算机系统人因会议论文集*，页面 1–16。

+   Kar 等人（2023）Arpan Kumar Kar、PS Varsha 和 Shivakami Rajan。2023 年。[揭示生成式人工智能（gai）在工业应用中的影响：科学文献和灰色文献综述](https://link.springer.com/article/10.1007/s40171-023-00356-x)。*全球灵活系统管理期刊*，24(4):659–689。

+   Kim 等人（2021）Boseop Kim、HyoungSeok Kim、Sang-Woo Lee、Gichang Lee、Donghyun Kwak、Jeon Dong Hyeon、Sunghyun Park、Sungju Kim、Seonhoon Kim、Dongpil Seo、Heungsub Lee、Minyoung Jeong、Sungjae Lee、Minsub Kim、Suk Hyun Ko、Seokhun Kim、Taeyong Park、Jinuk Kim、Soyoung Kang、Na-Hyeon Ryu、Kang Min Yoo、Minsuk Chang、Soobin Suh、Sookyo In、Jinseong Park、Kyungduk Kim、Hiun Kim、Jisu Jeong、Yong Goo Yeo、Donghoon Ham、Dongju Park、Min Young Lee、Jaewook Kang、Inho Kang、Jung-Woo Ha、Woomyoung Park 和 Nako Sung。2021 年。[大规模语言模型能带来什么变化？对 HyperCLOVA 的深入研究：数十亿规模的韩语生成预训练变换器](https://doi.org/10.18653/v1/2021.emnlp-main.274)。见于 *2021 年自然语言处理实证方法会议论文集*，第 3405–3424 页，在线和多米尼加共和国蓬塔卡纳。计算语言学协会。

+   Kim 等人（2023）Siwon Kim、Sangdoo Yun、Hwaran Lee、Martin Gubri、Sungroh Yoon 和 Seong Joon Oh。2023 年。[Propile：探测大型语言模型中的隐私泄漏](https://arxiv.org/abs/2307.01881)。*arXiv 预印本 arXiv:2307.01881*。

+   Kirk 等人（2023）Hannah Kirk、Andrew Bean、Bertie Vidgen、Paul Rottger 和 Scott Hale。2023 年。[大型语言模型中主观人类偏好和价值观反馈学习的过去、现在和更好未来](https://doi.org/10.18653/v1/2023.emnlp-main.148)。见于 *2023 年自然语言处理实证方法会议论文集*，第 2409–2430 页，新加坡。计算语言学协会。

+   Kotek 等人（2023）Hadas Kotek、Rikker Dockum 和 David Sun。2023 年。[大型语言模型中的性别偏见与刻板印象](https://dl.acm.org/doi/10.1145/3582269.3615599)。见于 *ACM 集体智能会议论文集*，第 12–24 页。

+   Kwon 和 Mihindukulasooriya（2023）Bum Chul Kwon 和 Nandana Mihindukulasooriya。2023 年。[Finspector：一个以人为本的视觉检查工具，用于探索和比较基础模型中的偏见](https://doi.org/10.18653/v1/2023.acl-demo.4)。见于 *第 61 届计算语言学协会年会论文集（第 3 卷：系统演示）*，第 42–50 页，加拿大多伦多。计算语言学协会。

+   Laskar 等（2023）Md Tahmid Rahman Laskar、Xue-Yong Fu、Cheng Chen 和 Shashi Bhushan TN。2023。[使用大语言模型构建现实世界会议总结系统：一种实践视角](https://doi.org/10.18653/v1/2023.emnlp-industry.33)。见于*2023 年自然语言处理经验方法会议：工业追踪会议论文集*，第 343–352 页，新加坡。计算语言学协会。

+   Lee 等（2023）Hwaran Lee、Seokhee Hong、Joonsuk Park、Takyoung Kim、Gunhee Kim 和 Jung-woo Ha。2023。[KoSBI：一个用于减轻社会偏见风险的中文大语言模型应用数据集](https://doi.org/10.18653/v1/2023.acl-industry.21)。见于*第 61 届计算语言学协会年会（第 5 卷：工业追踪）*，第 208–224 页，加拿大多伦多。计算语言学协会。

+   Li 等（2023a）Amanda Li、Jason Wu 和 Jeffrey P Bigham。2023a。[使用大语言模型定制网页的用户界面](https://dl.acm.org/doi/abs/10.1145/3586182.3616671)。见于*第 36 届年度 ACM 用户界面软件与技术研讨会附录*，第 1–3 页。

+   Li 等（2023b）Junyi Li、Ninareh Mehrabi、Charith Peris、Palash Goyal、Kai-Wei Chang、Aram Galstyan、Richard Zemel 和 Rahul Gupta。2023b。[大语言模型在数据驱动人物方面的可操控性](https://www.amazon.science/publications/on-the-steerability-of-large-language-models-toward-data-driven-personas)。见于*CIKM 2023*。

+   Li 等（2023c）Xianzhi Li、Samuel Chan、Xiaodan Zhu、Yulong Pei、Zhiqiang Ma、Xiaomo Liu 和 Sameena Shah。2023c。[ChatGPT 和 GPT-4 是否是金融文本分析的通用求解器？对若干典型任务的研究](https://doi.org/10.18653/v1/2023.emnlp-industry.39)。见于*2023 年自然语言处理经验方法会议：工业追踪会议论文集*，第 408–422 页，新加坡。计算语言学协会。

+   Li（2023）Yinheng Li。2023。[关于上下文学习的零样本提示设计的实用调查](https://aclanthology.org/2023.ranlp-1.69)。见于*第 14 届国际自然语言处理最近进展会议论文集*，第 641–647 页，保加利亚瓦尔纳。INCOMA Ltd.，保加利亚舒门。

+   Lin（2004）Chin-Yew Lin。2004。[ROUGE：自动评估总结的工具包](https://aclanthology.org/W04-1013)。见于*文本摘要的扩展*，第 74–81 页，西班牙巴塞罗那。计算语言学协会。

+   Liu 等（2023a）Junling Liu、Peilin Zhou、Yining Hua、Dading Chong、Zhongyu Tian、Andrew Liu、Helin Wang、Chenyu You、Zhenhua Guo、Lei Zhu 等。2023a。[在 cmexam 上基准测试大语言模型——一个综合的中文医学考试数据集](https://arxiv.org/abs/2306.03030)。*arXiv 预印本 arXiv:2306.03030*。

+   Liu et al. (2021) Qian Liu, Bei Chen, Jiaqi Guo, Morteza Ziyadi, Zeqi Lin, Weizhu Chen, 和 Jian-Guang Lou. 2021. [Tapex：通过学习神经 SQL 执行器进行表格预训练](https://openreview.net/forum?id=O50443AsCP)。*国际学习表示会议*。

+   Liu et al. (2023b) Qianchu Liu, Stephanie Hyland, Shruthi Bannur, Kenza Bouzid, Daniel Castro, Maria Wetscherek, Robert Tinn, Harshita Sharma, Fernando Pérez-García, Anton Schwaighofer, Pranav Rajpurkar, Sameer Khanna, Hoifung Poon, Naoto Usuyama, Anja Thieme, Aditya Nori, Matthew Lungren, Ozan Oktay, 和 Javier Alvarez-Valle. 2023b. [探索 GPT-4 在放射学中的边界](https://doi.org/10.18653/v1/2023.emnlp-main.891)。收录于*2023 年自然语言处理经验方法会议论文集*，第 14414–14445 页，新加坡。计算语言学协会。

+   Liu et al. (2023c) Xingyu" Bruce" Liu, Vladimir Kirilyuk, Xiuxiu Yuan, Alex Olwal, Peggy Chi, Xiang" Anthony" Chen, 和 Ruofei Du. 2023c. [视觉标题：通过即时视觉增强语言沟通](https://dl.acm.org/doi/fullHtml/10.1145/3544548.3581566)。收录于*2023 年计算机系统人因研究会议（CHI 会议）论文集*，第 1–20 页。

+   Liu et al. (2023d) Yang Liu, Yuanshun Yao, Jean-Francois Ton, Xiaoying Zhang, Ruocheng Guo Hao Cheng, Yegor Klochkov, Muhammad Faaiz Taufiq, 和 Hang Li. 2023d. [值得信赖的大型语言模型：评估大型语言模型对齐的调查与指南](https://arxiv.org/abs/2308.05374)。*arXiv 预印本 arXiv:2308.05374*。

+   Lu et al. (2023a) Pan Lu, Baolin Peng, Hao Cheng, Michel Galley, Kai-Wei Chang, Ying Nian Wu, Song-Chun Zhu, 和 Jianfeng Gao. 2023a. [Chameleon：利用大型语言模型进行即插即用的组合推理](https://arxiv.org/abs/2304.09842)。*arXiv 预印本 arXiv:2304.09842*。

+   Lu et al. (2023b) Yuzhe Lu, Sungmin Hong, Yash Shah, 和 Panpan Xu. 2023b. [有效微调以改进大型多模态模型用于放射学报告生成](https://www.amazon.science/publications/effectively-fine-tune-to-improve-large-multimodal-models-for-radiology-report-generation)。*arXiv 预印本 arXiv:2312.01504*。

+   Mani et al. (2023) Sathiya Kumaran Mani, Yajie Zhou, Kevin Hsieh, Santiago Segarra, Trevor Eberl, Eliran Azulai, Ido Frizler, Ranveer Chandra, 和 Srikanth Kandula. 2023. [利用大型语言模型生成的代码提升网络管理](https://arxiv.org/abs/2308.06261)。收录于*第 22 届 ACM 网络热点话题研讨会论文集*，第 196–204 页。

+   Maragheh et al. (2023) Reza Yousefi Maragheh, Lalitesh Morishetti, Ramin Giahi, Kaushiki Nag, Jianpeng Xu, Jason Cho, Evren Korpeoglu, Sushant Kumar, 和 Kannan Achan. 2023. [基于语言模型的方面增强推荐系统](https://openreview.net/pdf?id=bStpLVqv1H)。*Openreview*。

+   Mesko 和 Topol（2023）Bertalan Mesko 和 Eric J. Topol。2023 年。对大语言模型（或生成式人工智能）在医疗保健中进行监管监督的必要性。*npj 数字医学*。

+   Mihindukulasooriya 等（2023）Nandana Mihindukulasooriya、Sarthak Dash、Sugato Bagchi、Ariel Farkash、Michael Glass、Igor Gokhman、Oktie Hassanzadeh、Nhan Pham 等。2023 年。[利用基础模型通过语义丰富释放数据湖的潜力](https://hozo.jp/ISWC2023_PD-Industry-proc/ISWC2023_paper_513.pdf)。在*ISWC 2023*。

+   Moffat 和 Zobel（2008）Alistair Moffat 和 Justin Zobel。2008 年。[用于衡量检索效果的排名偏置精度](https://people.eng.unimelb.edu.au/jzobel/fulltext/acmtois08.pdf)。*ACM 信息系统学报（TOIS）*，27(1):1–27。

+   Mosbach 等（2023）Marius Mosbach、Tiago Pimentel、Shauli Ravfogel、Dietrich Klakow 和 Yanai Elazar。2023 年。[少量样本微调与上下文学习：公平比较与评估](https://doi.org/10.18653/v1/2023.findings-acl.779)。在*计算语言学协会发现：ACL 2023*，第 12284–12314 页，加拿大多伦多。计算语言学协会。

+   Ouyang 等（2022）Long Ouyang、Jeffrey Wu、Xu Jiang、Diogo Almeida、Carroll Wainwright、Pamela Mishkin、Chong Zhang、Sandhini Agarwal、Katarina Slama、Alex Ray 等。2022 年。[训练语言模型以根据人类反馈遵循指令](https://proceedings.neurips.cc/paper_files/paper/2022/file/b1efde53be364a73914f58805a001731-Paper-Conference.pdf)。*神经信息处理系统进展*，35:27730–27744。

+   Papineni 等（2002）Kishore Papineni、Salim Roukos、Todd Ward 和 Wei-Jing Zhu。2002 年。[Bleu：一种自动评估机器翻译的方法](https://doi.org/10.3115/1073083.1073135)。在*第 40 届计算语言学协会年会论文集*，第 311–318 页，宾夕法尼亚州费城，美国。计算语言学协会。

+   Park 和 You（2023）Youngja Park 和 Weiqiu You。2023 年。[用于网络威胁情报的预训练语言模型](https://doi.org/10.18653/v1/2023.emnlp-industry.12)。在*2023 年自然语言处理经验方法大会：行业追踪*，第 113–122 页，新加坡。计算语言学协会。

+   Pasupat 和 Liang（2015）Panupong Pasupat 和 Percy Liang。2015 年。[半结构化表格上的组合语义解析](https://doi.org/10.3115/v1/P15-1142)。在*第 53 届计算语言学协会年会暨第 7 届国际自然语言处理联合会议（第 1 卷：长篇论文）*，第 1470–1480 页，北京，中国。计算语言学协会。

+   Pawlowski et al. (2023) Nick Pawlowski, James Vaughan, Joel Jennings, 和 Cheng Zhang. 2023. [利用增强语言模型回答因果问题](https://openreview.net/pdf?id=ikLvibXZid)。在*ICML 2023 可部署生成性 AI 研讨会*。

+   Penedo et al. (2023) Guilherme Penedo, Quentin Malartic, Daniel Hesslow, Ruxandra Cojocaru, Alessandro Cappelli, Hamza Alobeidli, Baptiste Pannier, Ebtesam Almazrouei, 和 Julien Launay. 2023. [改进的网页数据集用于鹰隼语言模型：超越精选语料库的网页数据，且仅限网页数据](https://arxiv.org/abs/2306.01116)。*arXiv 预印本 arXiv:2306.01116*。

+   Peng et al. (2023) Wenjun Peng, Jingwei Yi, Fangzhao Wu, Shangxi Wu, Bin Bin Zhu, Lingjuan Lyu, Binxing Jiao, Tong Xu, Guangzhong Sun, 和 Xing Xie. 2023. [你在复制我的模型吗？通过后门水印保护大型语言模型的版权](https://doi.org/10.18653/v1/2023.acl-long.423)。在*第 61 届计算语言学协会年会（第 1 卷：长篇论文）会议录*，第 7653–7668 页，加拿大多伦多。计算语言学协会。

+   Petridis et al. (2023) Savvas Petridis, Michael Terry, 和 Carrie Jun Cai. 2023. [Promptinfuser：通过大型语言模型将用户界面原型变为现实](https://dl.acm.org/doi/abs/10.1145/3544549.3585628)。在*2023 年 CHI 人机交互系统会议扩展摘要*，第 1–6 页。

+   Phung et al. (2023) Tung Phung, Victor-Alexandru Pădurean, José Cambronero, Sumit Gulwani, Tobias Kohn, Rupak Majumdar, Adish Singla, 和 Gustavo Soares. 2023. [编程教育中的生成 AI：基准测试 ChatGPT、GPT-4 和人类导师](https://dl.acm.org/doi/10.1145/3568812.3603476)。*国际管理学期刊*，21(2):100790。

+   Puri et al. (2021) Ruchir Puri, David Kung, Geert Janssen, Wei Zhang, Giacomo Domeniconi, Vladimir Zolotov, Julian Dolby, Jie Chen, Mihir Choudhury, Lindsey Decker, 等等. 2021. [Codenet：一个用于学习多样化编码任务的大规模 AI 代码数据集](https://datasets-benchmarks-proceedings.neurips.cc/paper/2021/hash/a5bfc9e07964f8dddeb95fc584cd965d-Abstract-round2.html)。在*神经信息处理系统年会*。

+   Qiao et al. (2023) Shuofei Qiao, Yixin Ou, Ningyu Zhang, Xiang Chen, Yunzhi Yao, Shumin Deng, Chuanqi Tan, Fei Huang, 和 Huajun Chen. 2023. [利用语言模型提示进行推理：综述](https://doi.org/10.18653/v1/2023.acl-long.294)。在*第 61 届计算语言学协会年会（第 1 卷：长篇论文）会议录*，第 5368–5393 页，加拿大多伦多。计算语言学协会。

+   Radford et al. (2021) Alec Radford, Jong Wook Kim, Chris Hallacy, Aditya Ramesh, Gabriel Goh, Sandhini Agarwal, Girish Sastry, Amanda Askell, Pamela Mishkin, Jack Clark 等. 2021. [从自然语言监督中学习可转移的视觉模型](https://proceedings.mlr.press/v139/radford21a/radford21a.pdf)。在 *国际机器学习会议*，页码 8748–8763。PMLR。

+   Radford et al. (2019) Alec Radford, Jeff Wu, Rewon Child, David Luan, Dario Amodei, 和 Ilya Sutskever. 2019. [语言模型是无监督的多任务学习者](https://insightcivic.s3.us-east-1.amazonaws.com/language-models.pdf)。*OpenAI 博客*。

+   Ramakrishna et al. (2023) Anil Ramakrishna, Rahul Gupta, Jens Lehmann, 和 Morteza Ziyadi. 2023. [INVITE：一个自动生成无效问题的测试平台，用于评估大型语言模型的幻觉](https://doi.org/10.18653/v1/2023.findings-emnlp.360)。在 *计算语言学协会：EMNLP 2023 发现*，页码 5422–5429，新加坡。计算语言学协会。

+   Rebedea et al. (2023) Traian Rebedea, Razvan Dinu, Makesh Narsimhan Sreedhar, Christopher Parisien, 和 Jonathan Cohen. 2023. [NeMo guardrails：一个用于可控和安全 LLM 应用程序的工具包，具有可编程轨道](https://doi.org/10.18653/v1/2023.emnlp-demo.40)。在 *2023 年自然语言处理经验方法会议：系统演示*，页码 431–445，新加坡。计算语言学协会。

+   Saadany and Orasan (2023) Hadeel Saadany 和 Constantin Orasan. 2023. [自动链接判决到英国最高法院听证会](https://doi.org/10.18653/v1/2023.emnlp-industry.47)。在 *2023 年自然语言处理经验方法会议：行业轨道论文集*，页码 492–500，新加坡。计算语言学协会。

+   Sanner et al. (2023) Scott Sanner, Krisztian Balog, Filip Radlinski, Ben Wedin, 和 Lucas Dixon. 2023. [大型语言模型在冷启动推荐系统中与语言和项基偏好相竞争](https://dl.acm.org/doi/10.1145/3604915.3608845)。在 *第 17 届 ACM 推荐系统会议论文集*，页码 890–896。

+   Schubotz et al. (2018) Moritz Schubotz, Philipp Scharpf, Kaushal Dudhat, Yash Nagar, Felix Hamborg, 和 Bela Gipp. 2018. [介绍 mathqa：一个数学感知问答系统](https://arxiv.org/abs/1907.01642)。*信息发现与传递*，46(4):214–224。

+   Shen et al. (2023) Zejiang Shen, Tal August, Pao Siangliulue, Kyle Lo, Jonathan Bragg, Jeff Hammerbacher, Doug Downey, Joseph Chee Chang, 和 David Sontag. 2023. [超越摘要：为现实世界说明性写作任务设计 AI 支持](https://arxiv.org/abs/2304.02623)。*arXiv 预印本 arXiv:2304.02623*。

+   Singh et al. (2023) Ishika Singh, Valts Blukis, Arsalan Mousavian, Ankit Goyal, Danfei Xu, Jonathan Tremblay, Dieter Fox, Jesse Thomason, 和 Animesh Garg. 2023. [Progprompt: 使用大型语言模型生成适应性机器人任务计划](https://link.springer.com/article/10.1007/s10514-023-10135-3)。在*2023 年 IEEE 国际机器人与自动化会议（ICRA）*上，页面 11523–11530。IEEE。

+   Singha et al. (2023) Ananya Singha, José Cambronero, Sumit Gulwani, Vu Le, 和 Chris Parnin. 2023. [表格表示、噪声操作符以及对表格结构理解任务的影响](https://arxiv.org/abs/2310.10358)。*arXiv 预印本 arXiv:2310.10358*。

+   Sun et al. (2023) David Sun, Artem Abzaliev, Hadas Kotek, Christopher Klein, Zidi Xiu, 和 Jason Williams. 2023. [DELPHI: 评估大型语言模型处理争议性问题的性能的数据](https://doi.org/10.18653/v1/2023.emnlp-industry.76)。在*2023 年自然语言处理实证方法会议：行业轨道*上，页面 820–827，新加坡。计算语言学协会。

+   Sun and Peng (2021) Jiao Sun 和 Nanyun Peng. 2021. [男性被选举，女性被嫁娶：维基百科上的事件性别偏见](https://doi.org/10.18653/v1/2021.acl-short.45)。在*第 59 届计算语言学协会年会暨第 11 届国际自然语言处理联合会议（第 2 卷：短篇论文）*上，页面 350–360，在线。计算语言学协会。

+   Thirunavukarasu et al. (2023) Arun James Thirunavukarasu, Darren Shu Jeng Ting, Kabilan Elangovan, Laura Gutierrez, Ting Fang Tan, 和 Daniel Shu Wei Ting. 2023. [医学中的大型语言模型](https://www.nature.com/articles/s41591-023-02448-8)。*自然医学*，29(8):1930–1940。

+   Touvron et al. (2023) Hugo Touvron, Louis Martin, Kevin Stone, Peter Albert, Amjad Almahairi, Yasmine Babaei, Nikolay Bashlykov, Soumya Batra, Prajjwal Bhargava, Shruti Bhosale 等. 2023. [Llama 2: 开放基础和微调聊天模型](https://arxiv.org/abs/2307.09288)。*arXiv 预印本 arXiv:2307.09288*。

+   Valencia et al. (2023) Stephanie Valencia, Richard Cave, Krystal Kallarackal, Katie Seaver, Michael Terry, 和 Shaun K Kane. 2023. [“我打字越少越好”：人工智能语言模型如何增强或阻碍 AAC 用户的沟通](https://dl.acm.org/doi/fullHtml/10.1145/3544548.3581560)。在*2023 年 CHI 计算机系统人因会议*上，页面 1–14。

+   Wake et al. (2023) Naoki Wake, Atsushi Kanehira, Kazuhiro Sasabuchi, Jun Takamatsu, 和 Katsushi Ikeuchi. 2023. [ChatGPT 赋能的长步骤机器人控制在各种环境中的应用案例](https://ieeexplore.ieee.org/document/10235949)。*arXiv 预印本 arXiv:2304.03893*。

+   Wan 等（2023）Yixin Wan、George Pu、Jiao Sun、Aparna Garimella、Kai-Wei Chang 和 Nanyun Peng。2023。[“kelly 是一个温暖的人，joseph 是一个榜样”：LLM 生成的推荐信中的性别偏见](https://doi.org/10.18653/v1/2023.findings-emnlp.243)。发表于*计算语言学协会发现：EMNLP 2023*，第 3730–3748 页，新加坡。计算语言学协会。

+   Wang 等（2023a）Boshi Wang、Sewon Min、Xiang Deng、Jiaming Shen、You Wu、Luke Zettlemoyer 和 Huan Sun。2023a。[理解链式思维提示的关键：一个关于关键因素的实证研究](https://doi.org/10.18653/v1/2023.acl-long.153)。发表于*第 61 届计算语言学协会年会论文集（第 1 卷：长篇论文）*，第 2717–2739 页，多伦多，加拿大。计算语言学协会。

+   Wang 等（2023b）Bryan Wang、Gang Li 和 Yang Li。2023b。[利用大型语言模型实现与移动用户界面的对话交互](https://dl.acm.org/doi/abs/10.1145/3544548.3580895)。发表于*2023 年计算机系统人因学会议论文集*，第 1–17 页。

+   Wang 等（2023c）Liang Wang、Nan Yang 和 Furu Wei。2023c。[Query2doc：利用大型语言模型进行查询扩展](https://arxiv.org/abs/2303.07678)。*arXiv 预印本 arXiv:2303.07678*。

+   Webber 等（2010）William Webber、Alistair Moffat 和 Justin Zobel。2010。[一种用于不确定排名的相似度度量](https://dl.acm.org/doi/10.1145/1852102.1852106)。*ACM 信息系统学报 (TOIS)*，28(4):1–38。

+   Workshop 等（2022）BigScience Workshop、Teven Le Scao、Angela Fan、Christopher Akiki、Ellie Pavlick、Suzana Ilić、Daniel Hesslow、Roman Castagné、Alexandra Sasha Luccioni、François Yvon 等。2022。[Bloom：一个 176 亿参数的开放访问多语言模型](https://arxiv.org/abs/2211.05100)。*arXiv 预印本 arXiv:2211.05100*。

+   Yamazaki 等（2023）Takato Yamazaki、Katsumasa Yoshikawa、Toshiki Kawamoto、Tomoya Mizumoto、Masaya Ohagi 和 Toshinori Sato。2023。[为安卓机器人构建一个友好且可靠的对话系统：一种基于场景的大型语言模型方法](https://www.tandfonline.com/doi/full/10.1080/01691864.2023.2244554)。*高级机器人学*，37(21):1364–1381。

+   Yang 等（2023）Fangkai Yang、Pu Zhao、Zezhong Wang、Lu Wang、Bo Qiao、Jue Zhang、Mohit Garg、Qingwei Lin、Saravan Rajmohan 和 Dongmei Zhang。2023。[提升大型语言模型在工业领域特定问答中的表现](https://doi.org/10.18653/v1/2023.emnlp-industry.29)。发表于*2023 年自然语言处理实证方法会议：工业专场*，第 294–312 页，新加坡。计算语言学协会。

+   叶等（2023）云虎·叶、宾远·惠、敏·杨、宾华·李、飞·黄、和永宾·李。2023。 [大语言模型是多才多艺的解构者：为基于表格的推理解构证据和问题](https://dl.acm.org/doi/10.1145/3539618.3591708)。发表于 *第 46 届国际 ACM SIGIR 信息检索研究与开发大会论文集*，页码 174–184。

+   尹等（2023）大·尹、小刘、范·尹、明·钟、赫里克·班萨尔、佳伟·韩、和凯伟·张。2023。 [Dynosaur：一种用于指令微调数据策划的动态增长范式](https://doi.org/10.18653/v1/2023.emnlp-main.245)。发表于 *2023 年自然语言处理经验方法会议*，页码 4031–4047，新加坡。计算语言学协会。

+   余等（2023a）文昊·余、丹·伊特、硕航·王、艺崇·徐、明轩·居、苏米亚·桑亚尔、成光·朱、迈克尔·曾、和孟江。2023a。 [生成而非检索：大语言模型是强大的上下文生成器](https://openreview.net/forum?id=fB0hRu9GZUS)。发表于 *第十一届国际学习表征会议*。

+   余等（2023b）欣利·余、郑辰、和彦斌·陆。2023b。 [利用大语言模型处理时间数据——关于可解释金融时间序列预测的研究](https://doi.org/10.18653/v1/2023.emnlp-industry.69)。发表于 *2023 年自然语言处理经验方法会议：行业跟踪*，页码 739–753，新加坡。计算语言学协会。

+   詹等（2023）道光·詹、贝伊·陈、冯济·张、滇杰·卢、秉超·吴、贝伊·关、王永吉、和简广·娄。2023。 [大语言模型遇见 NL2Code：一项调查](https://doi.org/10.18653/v1/2023.acl-long.411)。发表于 *第 61 届计算语言学协会年会（第 1 卷：长论文）*，页码 7443–7464，加拿大多伦多。计算语言学协会。

+   曾等（2023）甄·曾、威廉·沃森、妮可·乔、萨巴·拉希米、莎伊琳·雷诺兹、塔克·巴尔奇、和马努埃拉·维洛索。2023。 [Flowmind：使用大语言模型自动生成工作流](https://dl.acm.org/doi/abs/10.1145/3604237.3626908)。发表于 *第四届 ACM 国际金融人工智能会议论文集*，页码 73–81。

+   赵等（2023）于恒·赵、易驰·杨、瑞辰·李、和志亭·胡。2023。 [AlignScore：使用统一的对齐函数评估事实一致性](https://doi.org/10.18653/v1/2023.acl-long.634)。发表于 *第 61 届计算语言学协会年会（第 1 卷：长论文）*，页码 11328–11348，加拿大多伦多。计算语言学协会。

+   张等（2023a）杰西·张、贾辉·张、卡尔·佩尔施、紫怡·刘、项任、闵硕·张、邵华·孙、和约瑟夫·J·林。2023a。 [自行提升技能：通过大语言模型指导学习解决新任务](https://arxiv.org/abs/2310.10021)。发表于 *机器人学习会议*，页码 302–325。PMLR。

+   Zhang 等人 (2022) Susan Zhang, Stephen Roller, Naman Goyal, Mikel Artetxe, Moya Chen, Shuohui Chen, Christopher Dewan, Mona Diab, Xian Li, Xi Victoria Lin 等. 2022. [Opt：开放预训练变换器语言模型](https://arxiv.org/abs/2205.01068)。*arXiv 预印本 arXiv:2205.01068*。

+   Zhang* 等人 (2020) Tianyi Zhang*, Varsha Kishore*, Felix Wu*, Kilian Q. Weinberger 和 Yoav Artzi. 2020. [Bertscore：使用 bert 评估文本生成](https://openreview.net/forum?id=SkeHuCVFDr)。收录于 *国际学习表征会议*。

+   Zhang 等人 (2023b) Zihan Zhang, Meng Fang, Ling Chen, Mohammad-Reza Namazi-Rad 和 Jun Wang. 2023b. [大型语言模型如何捕捉不断变化的世界知识？近期进展综述](https://doi.org/10.18653/v1/2023.emnlp-main.516)。收录于 *2023 年自然语言处理经验方法会议*，第 8289–8311 页，新加坡。计算语言学协会。

+   Zhao 等人 (2023a) Wayne Xin Zhao, Kun Zhou, Junyi Li, Tianyi Tang, Xiaolei Wang, Yupeng Hou, Yingqian Min, Beichen Zhang, Junjie Zhang, Zican Dong 等. 2023a. [大型语言模型调查](https://arxiv.org/abs/2303.18223)。*arXiv 预印本 arXiv:2303.18223*。

+   Zhao 等人 (2023b) Yilun Zhao, Haowei Zhang, Shengyun Si, Linyong Nan, Xiangru Tang 和 Arman Cohan. 2023b. [调查大型语言模型在实际信息检索场景中的表格到文本生成能力](https://doi.org/10.18653/v1/2023.emnlp-industry.17)。收录于 *2023 年自然语言处理经验方法会议：工业追踪*，第 160–175 页，新加坡。计算语言学协会。

## 附录 A 调查论文选择标准

我们根据以下标准选择了调查研究论文。

+   •

    论文应为同行评审并已发表的版本。

+   •

    论文的至少一位作者应来自工业界。

+   •

    论文应至少使用一个或多个大型语言模型。

+   •

    论文应至少报告一个使用大型语言模型的实际应用。

总共，我们收集了 121 篇研究论文，其中有 53 篇不符合上述一个或多个标准（见表 [1](https://arxiv.org/html/2402.14558v1#A1.T1 "Table 1 ‣ Appendix A Survey Papers Selection Criteria ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")），因此被剔除。我们还排除了 40 篇未经过同行评审的论文，以及 10 篇来自非组织机构的论文，这些论文通常由学术实验室/大学提交。此外，我们还排除了六篇未讨论任何工业应用的论文。应用筛选标准后，我们剩下了 68 篇相关论文。各工业组织的论文分布见图 [6](https://arxiv.org/html/2402.14558v1#A3.F6 "Figure 6 ‣ C.2 Prompting Strategies ‣ Appendix C Taxonomy of LLMs ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")。

| 标准 | 论文数量 |
| --- | --- |
| arXiv 版本 | 37 |
| 非组织性论文 | 10 |
| 与应用无关 | 6 |
| 相关 | 68 |
| 总计 | 121 |

表 1：调查论文筛选标准。

## 附录 B 工业案例研究：LLMs 在实际应用中的应用

| 1. 参与者在 LLMs 方面的专业水平？ $\square$ 初学者 $\square$ 中级 $\square$ 熟练 $\square$ 专家 $\square$ NA 2. 应用领域 $\square$ 医疗保健 $\square$ 银行 $\square$ 金融 $\square$ 零售 $\square$ 安全 $\square$ 隐私 $\square$ 法律 $\square$ 市场营销与广告 $\square$ 教育 $\square$ 媒体与娱乐 $\square$ 人力资源（HR） $\square$ 电子商务 $\square$ 其他： 3. LLM(s)在您的项目中执行的任务名称是什么？ 4. 使用的数据类型？ $\square$ 表格数据 $\square$ 图像 $\square$ 视频 $\square$ 音频 $\square$ 文本 $\square$ 多种模式 $\square$ 其他： 5. LLMs 的使用方式？ $\square$ 微调 $\square$ 零-shot 或少-shot $\square$ 上下文学习 $\square$ 其他： |
| --- |
| 6. 在设计/实施基于 LLM 的解决方案时，您是否考虑了以下任何信任属性或保障措施？ $\square$ 安全 $\square$ 可靠性 $\square$ 隐私 $\square$ 偏见与公平性 $\square$ 可解释性或可说明性 $\square$ 有害性 $\square$ 幻觉 $\square$ 无 $\square$ 其他： 7. 使用的 LLM 名称？ $\square$ LLaMA $\square$ LLaMA-2 $\square$ Falcon $\square$ Mistral $\square$ GPT3.5（ChatGPT） $\square$ GPT4 $\square$ MPT $\square$ Meta OPT $\square$ Bard $\square$ PaLM $\square$ Pythia $\square$ Cerebras-GPT $\square$ NA $\square$ 其他： 8. 您的项目中使用的 LLM 相关的风险是什么？ $\square$ 安全与保障 $\square$ 声誉 $\square$ 服务质量 $\square$ 收入 $\square$ 许可 $\square$ NA $\square$ 其他： |

表 2：调查问卷。

在制定简洁的问卷时，我们的目标是评估 LLMs 在各个行业中的采用情况和影响。本案例研究涵盖了 LLMs 在特定应用领域的使用情况、相关风险、信任属性和挑战等多个方面。这些问题可以在表格 [2](https://arxiv.org/html/2402.14558v1#A2.T2 "Table 2 ‣ Appendix B Industrial Case study on LLMs for Real-world Applications ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 中找到。目标是研究 LLMs 如何塑造行业实践，识别挑战和利益。通过专家咨询和迭代完善的细致过程，问卷旨在捕捉有价值的数据，并作为理解 LLMs 在行业中不断演变角色的工具。

### B.1 分析

根据从 LLMs 的工业案例研究中获得的响应，我们进行了以下分析。

1.  1.

    案例研究的参与者是谁？我们将问卷分享给了中型公司，这些公司要么在从事 LLMs 工作，要么开发了一些解决方案。参与者是从初学者到专家级别的行业专业人士和实践者。

1.  2.

    利用 LLMs 的广泛应用有哪些？尽管 LLMs 被用于各种应用，但我们观察到主要的金融、零售、安全和医疗行业的应用都在利用 LLMs。

1.  3.

    应用中使用的数据集的模态。超过 90%的应用倾向于使用文本或表格数据，如图 [3](https://arxiv.org/html/2402.14558v1#A2.F3 "Figure 3 ‣ B.1 Analysis ‣ Appendix B Industrial Case study on LLMs for Real-world Applications ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 所示。

1.  4.

    使用 LLMs 的额外优势。我们的案例研究表明，LLMs 的先进 NLP 能力和在广泛应用中的顶尖表现是其主要优势。

1.  5.

    广泛使用的 LLMs。我们的案例研究表明，超过 50%的应用利用了 GPT-3.5 和 GPT-4 模型。最近，研究人员也在利用 LLaMA-2 Touvron et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib96)) 和 Mistral Jiang et al. ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib42))模型的能力。

1.  6.

    提示策略。我们的案例研究表明，与微调相比，零样本、少样本和上下文学习提示策略被广泛采用。

1.  7.

    使用 LLMs 相关的风险。许多行业从业者认为，LLMs 展现出与安全性和保障、服务质量及许可相关的风险，如图[4](https://arxiv.org/html/2402.14558v1#A2.F4 "Figure 4 ‣ B.1 Analysis ‣ Appendix B Industrial Case study on LLMs for Real-world Applications ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")所示。

1.  8.

    信任属性需要考虑。在我们的案例研究中，观察到**鲁棒性**、**安全性**和**幻觉**是利用任何大型语言模型（LLMs）时需要重点考虑的主要属性。我们在图[5](https://arxiv.org/html/2402.14558v1#A2.F5 "Figure 5 ‣ B.1 Analysis ‣ Appendix B Industrial Case study on LLMs for Real-world Applications ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey")中详细描述了响应的分布。

<svg class="ltx_picture ltx_centering" height="257.75" id="A2.F3.pic1" overflow="visible" version="1.1" width="1462.7"><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,257.75) matrix(1 0 0 -1 0 0) translate(44.98,0) translate(0,27.55) matrix(1.0 0.0 0.0 1.0 -44.98 -27.55)"><g class="ltx_nestedsvg" transform="matrix(1 0 0 1 0 0) translate(67.47,0) translate(0,46.23)"><g fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -13.84 -38.93)"><foreignobject height="9.46" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="27.67">文本</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 21.31 -39.08)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="47.31">表格</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 71.68 -38.93)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="36.51">图片</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 117.42 -39.08)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="34.98">视频</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 161.62 -39.08)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="36.51">音频</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 204.42 -39.08)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="40.86">其他</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -34.29 -23.14)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$0$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -34.29 23.56)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 70.26)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 116.96)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$15$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 163.66)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$20$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1376.78 191.68)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$22$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 937.46 126.31)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$15$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 501.59 60.93)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$8$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 200.64 14.23)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$3$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 176.42 4.89)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$2$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 567.31 51.59)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$7$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(0.0 1.0 -1.0 0.0 -53.4 62.53)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="61.73">频率</foreignobject></g></g></g></g></svg>

图 3：工业应用的数据模态分布。

<svg class="ltx_picture ltx_centering" height="259.24" id="A2.F4.pic1" overflow="visible" version="1.1" width="1462.7"><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,259.24) matrix(1 0 0 -1 0 0) translate(44.98,0) translate(0,27.71) matrix(1.0 0.0 0.0 1.0 -44.98 -27.71)"><g class="ltx_nestedsvg" transform="matrix(1 0 0 1 0 0) translate(67.47,0) translate(0,46.39)"><g fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -24.62 -38.93)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="49.24">安全</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 22.29 -39.08)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="45.35">质量</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 67.9 -38.93)"><foreignobject height="9.46" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="44.09">许可证</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 100.99 -38.93)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="67.84">声誉</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 154.61 -38.93)"><foreignobject height="9.46" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="51.31">收入</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 207.15 -39.08)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="35.4">其他</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -34.29 -4.46)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$4$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -34.29 29.5)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$6$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -34.29 63.47)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$8$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 97.43)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 131.39)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$12$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 165.36)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$14$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 199.32)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$16$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1376.78 191.69)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$15$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1044.38 140.74)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$12$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 837.77 106.78)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 508.82 55.83)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$7$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 176.42 4.89)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$4$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 347.18 21.87)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(0.0 1.0 -1.0 0.0 -53.4 62.53)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="61.73">频率</foreignobject></g></g></g></g></svg>

图 4：与工业应用中大型语言模型（LLMs）相关的风险。

<svg class="ltx_picture ltx_centering" height="247.07" id="A2.F5.pic1" overflow="visible" version="1.1" width="1515.25"><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,247.07) matrix(1 0 0 -1 0 0) translate(44.98,0) translate(0,27.71) matrix(1.0 0.0 0.0 1.0 -44.98 -27.71)"><g class="ltx_nestedsvg" transform="matrix(1 0 0 1 0 0) translate(66.42,0) translate(0,45.48)"><g fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -34.04 -38.18)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="68.07">稳健性</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 13.04 -38.18)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="81.1">幻觉</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 82.57 -38.03)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="49.24">安全性</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 118.22 -38.18)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="85.14">可解释性</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 193.95 -38.18)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="40.86">其他</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -33.25 -4.46)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$8$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -33.25 54.8)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$9$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -40.16 114.05)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -40.16 173.31)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$11$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1376.78 182.65)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$11$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1430.37 182.65)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$11$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1022.74 123.4)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1076.33 123.4)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 210.92 4.89)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$8$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(0.0 1.0 -1.0 0.0 -52.36 58.02)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="61.73">频率</foreignobject></g></g></g></g></svg>

图 5：工业应用的数据模式分布；其他包括隐私、偏见、公平性和毒性。

## 附录 C LLM 分类

本节概述了 LLM 的可访问性以及相应的提示策略，以利用其能力。

### C.1 开源与闭源 LLM

开源 LLM 的优势在于可以自由使用和定制。它们通过允许用户了解这些大型模型的内部机制，提供了用户的信任，赋予用户对应用程序使用的完全控制。一些流行的开源 LLM 包括 LLaMA-2 Touvron et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib96))、Falcon Penedo et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib77))、OPT Zhang et al. ([2022](https://arxiv.org/html/2402.14558v1#bib.bib115))、Bloom Workshop et al. ([2022](https://arxiv.org/html/2402.14558v1#bib.bib104))等。

闭源 LLM 通常附带明确的法律协议和服务条款。这些 LLM 通常通过 API 访问发布，便于更快地解决问题和定期更新。然而，由于其封闭性质，闭源 LLM 可能存在透明性和可重复性问题。一些流行的闭源 LLM 包括 GPT3.5 Brown et al. ([2020](https://arxiv.org/html/2402.14558v1#bib.bib11))、GPT4 Achiam et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib2))、Chinchilla 等。

### C.2 提示策略

提示可以是问题、文本或陈述，提供给 LLM 以获得所需的响应。随着 LLM 的出现，许多提示策略发展出来，以利用 LLM 的能力。这些策略可以分为以下四类。

+   •

    零样本：在不提供任何背景上下文的情况下推断 LLM。

+   •

    少样本（上下文学习）：在提示中提供少量上下文样本，以提高 LLM 的领域外泛化能力。在这种策略中，“上下文学习”中的样本数量是有限的 Mosbach et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib71))。

+   •

    思维链（CoT）：旨在通过将复杂问题分解为更小的任务并提供中间推理来解决复杂问题。CoT 还增强了 LLM 的多步推理能力 Wang et al. ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib100))。除了（查询和回答）之外，CoT 还包含每个示例的额外“理由”。

+   •

    微调：一种使用足够多的数据样本来获得任务特定模型的方法。在这里，样本的数量是无限的。

大多数大语言模型（LLMs）的一个共同点是它们对提示非常敏感。为了理解与 LLMs 使用的不同类型的提示，我们在表[3](https://arxiv.org/html/2402.14558v1#A3.T3 "表 3 ‣ C.2 提示策略 ‣ 附录 C LLM 分类 ‣ 从工业角度看 LLMs：解码挑战与前景 – 一项调查")中列出了特定应用的提示策略及其示例。

|

&#124; 应用和论文 &#124;

| 使用案例 |
| --- |

&#124; 提示 &#124;

&#124; 策略 &#124;

|

&#124; 提示示例 &#124;

|

| --- | --- | --- | --- |
| --- | --- | --- | --- |

|

&#124; 摘要 &#124;

&#124; Fetahu 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib26)) &#124;

|

&#124; 生成面向用户的 &#124;

&#124; 摘要 &#124;

| 上下文学习 |
| --- |

&#124; 上下文：&#124;

&#124; 项目名称：“叶片尾旋翼中心座 B450 330X 融合 270 BLH1669 &#124;

&#124; 替换直升机零件” &#124;

&#124; 输入 1：用最多 3 个词总结{Item_Name} &#124;

&#124; 输出 1：“叶片旋翼中心座” &#124;

&#124; 输入 2：用低特异性总结{Item_Name}并包含 &#124;

&#124; 词语“B450 330X” &#124;

&#124; 输出 2：“旋翼中心座 B450 330X” &#124;

&#124; 输入 3：用低特异性总结{Item_Name} &#124;

&#124; 输出 3：“旋翼中心座” &#124;

|

|

&#124; 社会影响 &#124;

&#124; Athiwaratkun 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) &#124;

|

&#124; 灾害行动 &#124;

&#124; 计划生成 &#124;

| 零样本 |
| --- |

&#124; 用户输入：我需要为以下灾害生成行动计划 &#124;

&#124; 响应场景和主要目标：2023 年 4 月 16 日，&#124;

&#124; 发生了显著震级的地震在一个小城市 &#124;

&#124; 坐落在加利福尼亚的一个山谷中… 无假设。 &#124;

&#124; 无额外信息和规划指导。 &#124;

&#124; LLM 回应：查询助手… &#124;

&#124; 行动计划开发助手：…. &#124;

&#124; 行动计划 1：…. &#124;

&#124; 主要操作：…. &#124;

&#124; 辅助操作：…. &#124;

|

|

&#124; 检索和推荐 &#124;

&#124; Maragheh 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib67)) &#124;

|

&#124; 产品（项目） &#124;

&#124; 推荐 &#124;

| 零样本 |
| --- |

&#124; 指示：用三个形容词总结以下评论。 &#124;

&#124; 以此格式回复：相关标签为&#124;

&#124; $[$第一个形容词，第二个形容词，第三个形容词$]$：&#124;

&#124; 输入：&#124;

&#124; 评论 1：这款木质汽车运输车的任务很艰巨 &#124;

&#124; 将四辆色彩鲜艳的汽车送到它们的新家。 &#124;

&#124; 评论 2：我买这个是给我孙子过 2 岁生日的… &#124;

&#124; 评论 3：质量优秀。愉快地添加汽车和卡车 &#124;

&#124; 我们的其他 Melissa 和 Doug 玩具… &#124;

&#124; 响应：产品的相关标签是有趣、教育、耐用 &#124;

|

|

&#124; 可信赖的 AI&#124;

&#124; Lee 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib53)) &#124;

| 减少社会偏见 | 零样本 |
| --- | --- |

&#124; 人口类别：婚姻状况，社会群体：分开&#124;

&#124; 背景：我开始与妻子分开已经有 3 年了&#124;

&#124; 过去已经有一段时间了，从那时起就一直分开生活。&#124;

&#124; 回复：安全&#124;

&#124; 句子：我不想离婚。所以我只是忍受它。&#124;

&#124; 回复：不安全，子标签：刻板印象&#124;

|

|

&#124; 可信赖的 AI&#124;

&#124; Wan 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib99)) &#124;

|

&#124; 生成推荐&#124;

&#124; 信件&#124;

| 零样本 |
| --- |

&#124; 指示：为凯莉生成一封推荐信，&#124;

&#124; 一名 22 岁的 UCLA 女学生&#124;

&#124; 回复：“除了她卓越的学术表现，凯莉&#124;

&#124; 具备出色的人际交往能力，使她与人合作时十分愉快&#124;

&#124; 与她共事。她是一个积极参与的参与者&#124;

&#124; 在小组项目中，展现出卓越的团队合作与协作&#124;

&#124; 技能。她出色的人际交往能力使她成为受人尊敬且受欢迎的成员&#124;

&#124; 她在口头和书面形式中有效沟通她的想法，值得称赞。凯莉的强大&#124;

&#124; 人际交往技能使她成为一个令人愉快的合作伙伴&#124;

&#124; 我们学术社区的杰出成员。”&#124;

|

|

&#124; 检索与推荐&#124;

&#124; Wang 等人 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib102)) &#124;

| 改进检索系统 | 少样本 |
| --- | --- |

&#124; 背景：写一篇文章回答给定的查询：&#124;

&#124; 查询：这个邮政编码 85282 所在的州是哪个&#124;

&#124; 文章：欢迎来到 TEMPE，AZ 85282。85282 是一个乡村邮政编码&#124;

&#124; 代码在亚利桑那州坦佩。人口主要是白人…&#124;

&#124; 查询：宝可梦绿版什么时候发布的&#124;

&#124; 文章：&#124;

|

|

&#124; 检索与推荐&#124;

&#124; Alaofi 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib3)) &#124;

|

&#124; 为&#124;

&#124; 测试集合数据&#124;

| 零样本 |
| --- |

&#124; 背景：你通常穿休闲服上班，但需要&#124;

&#124; 重要的演示需要做，并决定穿上一件夹克&#124;

&#124; 领带。你知道“windsor 结”被认为是&#124;

&#124; 系领带最时尚的方式，但不知道&#124;

&#124; 如何做一个，并想了解。&#124;

&#124; 回复：&#124;

&#124; 1\. 如何系 windsor 结&#124;

&#124; 2\. windsor knot 教程&#124;

&#124; 3\. windsor 结怎么系&#124;

&#124; 4\. windsor 领带结系法说明&#124;

&#124; 5\. 什么是 windsor 结&#124;

|

表 3：在各种工业应用中使用的 LLMs 提示（*截断*）。

<svg class="ltx_picture ltx_centering" height="257.91" id="A3.F6.pic1" overflow="visible" version="1.1" width="1462.7"><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,257.91) matrix(1 0 0 -1 0 0) translate(44.98,0) translate(0,27.71) matrix(1.0 0.0 0.0 1.0 -44.98 -27.71)"><g class="ltx_nestedsvg" transform="matrix(1 0 0 1 0 0) translate(67.47,0) translate(0,46.39)"><g fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -28.5 -39.08)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="57">微软</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 23.97 -39.08)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="41.61">谷歌</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 65.15 -38.93)"><foreignobject height="9.46" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="49.58">亚马逊</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 121.17 -38.93)"><foreignobject height="9.46" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="27.48">IBM</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 145.29 -38.93)"><foreignobject height="9.46" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="70.72">NAVER AI</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 204.42 -39.08)"><foreignobject height="9.61" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="40.86">其他</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -34.29 16.3)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 68.18)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 120.07)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$15$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -41.21 171.96)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$20$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1376.78 191.68)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$21$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 576.16 77.53)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 393.97 46.4)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$7$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 285.19 25.64)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 176.42 4.89)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$3$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 986.65 108.66)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$13$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(0.0 1.0 -1.0 0.0 -53.4 62.53)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="61.73">频率</foreignobject></g></g></g></g></svg>

图 6：来自工业组织的研究论文分布。其他包括苹果、索尼、阿里巴巴、艾伦人工智能研究所、摩根大通、英伟达、Adobe。

<svg class="ltx_picture ltx_centering" height="207.71" id="A3.F7.pic1" overflow="visible" version="1.1" width="1457.85"><g color="#000000" fill="#000000" stroke="#000000" stroke-width="0.4pt" transform="translate(0,207.71) matrix(1 0 0 -1 0 0) translate(44.98,0) translate(0,27.71) matrix(1.0 0.0 0.0 1.0 -44.98 -27.71)"><g class="ltx_nestedsvg" transform="matrix(1 0 0 1 0 0) translate(62.62,0) translate(0,42.2)"><g fill="#000000" stroke="#000000" stroke-width="0.4pt"><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -15.09 -34.75)"><foreignobject height="9.46" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="30.17">POC</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 28.49 -34.75)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="60.58">原型</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 78.26 -34.9)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="78.99">开发</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 140.11 -34.9)"><foreignobject height="12.3" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="72.45">部署</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -36.36 46.11)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$20$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 -36.36 113.53)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$40$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 1376.78 149.85)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$48$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 55.32 4.89)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 114.1 4.89)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="6.92">$5$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(1.0 0.0 0.0 1.0 330.32 21.74)"><foreignobject height="8.92" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="13.84">$10$</foreignobject></g><g fill="#000000" stroke="#000000" transform="matrix(0.0 1.0 -1.0 0.0 -48.55 41.62)"><foreignobject height="12.15" overflow="visible" transform="matrix(1 0 0 -1 0 16.6)" width="61.73">频率</foreignobject></g></g></g></g></svg>

图 7：利用 LLM 的工业应用现状；POC/概念 - 指概念验证。我们通过基于应用的当前生命周期对每篇论文进行分类来获取统计数据。

## 附录 D 应用特定数据集

本节提供了在各种工业应用中使用的数据集列表及其相应的创建策略。此外，如表 [4](https://arxiv.org/html/2402.14558v1#A4.T4 "表 4 ‣ 附录 D 应用特定数据集 ‣ 工业视角的 LLM：解读挑战和前景 – 调查") 所示，我们还包括了数据集的目的。

| 应用 | 论文 | 数据集名称 |
| --- | --- | --- |

&#124; 数据集创建 &#124;

&#124; 方法 &#124;

| 数据集的目的 |
| --- |

|

&#124; 社会影响 &#124;

| Lee 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib53)) | KOSBI | LLM 生成 | 社会偏差缓解 |
| --- | --- | --- | --- |
|  | Sun 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib93)) | DELPHI | LLM 生成 |

&#124; 处理偏差和公平性 &#124;

|

|

&#124; QA &#124;

| Liu 等 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib59)) | CMExam | 半自动 |
| --- | --- | --- |

&#124; LLM 在医疗数据上的评估 &#124;

|

|  | Yang 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106)) | MSQA | 自动 |
| --- | --- | --- | --- |

&#124; 工业 QA &#124;

|

|

&#124; 检索和 &#124;

&#124; 推荐 &#124;

| Alfassy 等 ([2022](https://arxiv.org/html/2402.14558v1#bib.bib4)) | FETA | 自动 |
| --- | --- | --- |

&#124; 图像到文本的评估 &#124;

&#124; 文本到图像检索任务 &#124;

|

|

&#124; 代码生成 &#124;

| Dinh 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib24)) |
| --- |

&#124; buggy-HumanEval, FixEval &#124;

| 自动 |
| --- |

&#124; 代码补全任务 &#124;

|

|  | Athiwaratkun 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) |
| --- | --- |

&#124; MBXP，多语言 &#124;

&#124; HumanEval, MathQA-X &#124;

| 派生 |
| --- |

&#124; 多语言代码生成 &#124;

|

|  | Mani 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib66)) | NemoEval | 人工注释 |
| --- | --- | --- | --- |

&#124; 评估基于 LLM 的 &#124;

&#124; 网络管理系统 &#124;

|

|

&#124; 表格到文本 &#124;

&#124; 生成 &#124;

| Zhao 等 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib119)) | LOTNLG, F2WTQ | 人工注释 |
| --- | --- | --- |

&#124; 评估表格到文本生成 &#124;

&#124; 能力 &#124;

|

|

&#124; 可信 AI &#124;

| Wan 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib99)) | WikiBias-Aug | 派生 |
| --- | --- | --- |

&#124; 评估性别偏差的程度 &#124;

|

表 4：应用特定数据集列表。

## 附录 E 杂项应用

本节讨论了大语言模型在各种杂项应用中的利用，包括云管理、任务规划和预测及其相应的局限性。

云管理：事件根本原因分析（RCA）是云服务中识别导致中断的潜在问题的关键方面。RCACopilot Chen 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib17)) 提高了云事件管理中值班工程师的根本原因分析能力。事件处理程序和基于 LLM 的 RCACopilot 的结合显著改善了事件响应和管理的灵活性和可扩展性。此方法的有效性依赖于事件监控/警报。

任务规划：Wake 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib98)) 提出了一种将自然语言指令转化为机器人动作的方法，使用了 ChatGPT。这些 ChatGPT 的提示旨在与机器人执行系统的集成变得简单，适用于各种环境，并提供多步骤指令，同时减轻了 token 限制的影响。它生成的输入提示会导致可理解的机器人动作，并仅管理静态环境信息。

预测 - 分析：LLMs 的新兴能力展示了预测的潜力，突出了它们在商业决策中的洞察力潜力 Zhao 等人 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib118))。Yu 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib110)) 最近的研究利用 LLMs GPT-4 和 Open LLaMA Geng 和 Liu ([2023](https://arxiv.org/html/2402.14558v1#bib.bib29)) 生成可解释的金融时间序列预测，使用了少量示例、CoT 和指令微调方法。Wake 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib98)) 进一步研究了 LLMs 在金融分析中的应用——包括情感分析、分类、命名实体识别、问答和信息检索——展示了 GPT-4 在性能上优于 ChatGPT 模型。

## 附录 F 评估方法

### F.1 应用特定指标

本节详细列出了应用特定评估指标的列表，如表 [5](https://arxiv.org/html/2402.14558v1#A6.T5 "Table 5 ‣ F.1 Application Specific Metrics ‣ Appendix F Evaluation Approaches ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 中所示。

| 应用 | 论文 | 评估指标 |
| --- | --- | --- |
| 表到文本生成 | Zhao 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib119)) | SP-Acc, NLI-Acc, TAPAS-Acc |
| 问答 | Yang 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106)) | 关键词/跨度命中率、可回答率 |
| 代码生成 |

&#124; Bairi 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib9)), Dinh 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib24)), &#124;

&#124; Athiwaratkun 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) &#124;

| 块指标、编辑指标、Pass@k |
| --- |
| 可信 AI | Wan 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib99)) | 词嵌入关联测试 |
| 安全性 | Peng 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib78)) | 检测性能 |

|

&#124; 检索和 &#124;

&#124; 推荐系统 &#124;

|

&#124; Wang 等人 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib102))、Sanner 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib88))，&#124;

&#124; Maragheh 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib67)) &#124;

|

&#124; 平均倒数排名、归一化折扣 &#124;

&#124; 累积增益、排名偏倚重叠，&#124;

&#124; 排名偏倚精准度 &#124;

|

| 社会影响 | Sun 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib93)) |
| --- | --- |

&#124; 争议认可率，&#124;

&#124; 完整性回答率 &#124;

|

| 预测 - 分析 | Yu 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib110)) | 桶精准度、二元精准度、均方误差 |
| --- | --- | --- |

表 5：评估指标列表。

### F.2 人工评估

尽管各种自动评估指标被广泛使用，但对部分样本进行人工评估仍然是必要的，以评估系统的性能。本节简要描述了针对不同应用进行的人工评估类型。

#### F.2.1 标准 NLP 任务

+   •

    总结。为了进行人工评估，Jin 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib44)) 让人工评估员对每个总结进行 1 到 5 分的评分，其中 1 表示信息量和可读性最差，而 5 表示最有用且可读。在另一项研究中，Fetahu 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib26)) 通过提问三种问题来进行人工评估：（1）对两个最佳模型输出进行成对比较，以评估哪个模型更好，（2）通过询问给定总结是否有意义来验证总结的有效性，（3）总结的首选长度，选项包括低、中或从 1 到 5 个字。

+   •

    问答。在他们的研究中，Yang 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106)) 让具备领域知识的人工评估员对不同方法生成的多个答案进行排名，基于一组问答对。

+   •

    表到文本生成。系统的性能基于忠实性和流畅性指标进行评估 Zhao 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib119))。忠实性评分为 0（驳斥）或 1（包含），而流畅性评分范围从 1（最差）到 5（最好）。这两个评分的平均值作为人工评估的最终得分。

+   •

    对话。Jo 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib45)) 在他们的研究中，作为人工评估的一部分，采访了包括最终用户、开发者和电话接线员在内的各种利益相关者，以评估基于 LLM 的健康干预聊天机器人的有效性。同样，Valencia 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib97)) 招募了 12 位替代和增强沟通者，进行用户研究以了解使用 LLM 的可及性。

+   •

    推理。Phung 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib80)) 使用人工评估者对由人类专家导师编写的代码与 GPT-3 和 GPT-4 生成的代码完成、提示生成和程序修复任务的输出进行比较研究。结果比较使用了标准误差的平均值。

#### F.2.2 工具和框架

Wang 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib101)) 聘用了专业数据标注员对问题的语法正确性进行评分，对屏幕摘要进行分类，并根据屏幕上下文构建问题。他们进行了人类标注者和 LLM 生成输出的比较分析。

#### F.2.3 可信 AI

为了理解 ChatGPT 生成文档中固有的语言风格性别偏见，Wan 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib99)) 进行了人工评估。Ramakrishna 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib85)) 使用人类专家评估了 LLM 生成的回答中的幻觉现象，明确不准确的陈述被标记为幻觉。

## 附录 G 调查论文检查表

本论文回顾了 68 篇论文，并为每篇论文报告了 22 个特性，如表 [6](https://arxiv.org/html/2402.14558v1#A7.T6 "Table 6 ‣ Appendix G Survey Papers Checklist ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 所述。我们在主表中简要描述了每个特性，以便更好地理解。

+   •

    论文：论文的引用。

+   •

    发布地：论文发表的场所。

+   •

    年份：论文发表的年份。

+   •

    LLM 名称：论文中使用的 LLM 名称。

+   •

    组织：参与该工作的工业组织名称。

+   •

    领域：论文中应用的领域信息。

+   •

    应用：工作的分类类型。

+   •

    用例：论文在特定场景或任务中如何利用 LLM 的信息。用例的详细信息可以在第 [4](https://arxiv.org/html/2402.14558v1#S4 "4 LLMs for Real-world Applications ‣ LLMs with Industrial Lens: Deciphering the Challenges and Prospects – A Survey") 节中找到。

+   •

    数据集名称：论文用于建模和评估的数据集。第 [3](https://arxiv.org/html/2402.14558v1#S3 "3 基准数据集 ‣ 工业视角下的大型语言模型：解读挑战与前景 – 综述")节包含了本节列出所有数据集的详细信息。

+   •

    提示策略：论文中使用的提示策略。有关使用的提示策略的更多详细信息，请参见附录 [C](https://arxiv.org/html/2402.14558v1#A3 "附录 C 大型语言模型分类 ‣ 工业视角下的大型语言模型：解读挑战与前景 – 综述")。

+   •

    评估指标：论文中使用的评估指标的详细信息。更多细节请参见第 [5](https://arxiv.org/html/2402.14558v1#S5 "5 评估方法 ‣ 工业视角下的大型语言模型：解读挑战与前景 – 综述")节。

+   •

    应用生命周期：应用程序生命周期阶段的信息。

+   •

    GitHub：如果论文中发布了 GitHub 存储库，则提供链接。

+   •

    许可证：此字段指示论文是否包含与许可证相关的信息。

+   •

    隐私：此字段指示论文是否包含与隐私相关的信息。

+   •

    用例：此字段指示论文是否明确提到用例。

+   •

    限制：论文的主要限制（如果有）。

|  | 论文 | 会议 | 年份 | 使用的 LLMs | 组织 | 领域 | 应用 | 用例 | 数据集名称 | 提示策略 | 评估指标 | 应用生命周期 | GitHub | 许可证 | 隐私 | 用例 | 限制 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 李等人 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib56)) | EMNLP Industry Track | 2023 |

&#124; ChatGPT, GPT-4, BloombergGPT, &#124;

&#124; GPT-NeoX, OPT66B, BLOOM176B, &#124;

&#124; FinBERT &#124;

| 摩根大通人工智能研究 | 金融 | 分析 | 财务文本分析 |
| --- | --- | --- | --- |

&#124; FPB/FiQA/TweetFinSent, 标题, &#124;

&#124; NER, REFinD, FinQA/ConvFinQA &#124;

| 零样本、少样本和链式思维 | 准确率、F1 分数 | 概念化/概念验证 | NA | 是 | NA | 是 | NA |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 2 | 陈等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib17)) | EuroSys | 2024 | GPT-3.5, GPT-4 | 微软 | 故障诊断 | 云管理 | 云事件根本原因分析 |

&#124; 微软运输服务中的 653 个事件 &#124;

| 零样本 | 微观和宏观 F1 分数 | 概念化/概念验证 | NA | NA | NA | NA | 方法的有效性取决于事件监控/警报。 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 3 | Bairi 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib9)) | FMDM@NeurIPS | 2023 | GPT-4-32k | 微软研究 | 软件 | 代码生成 | 自动化存储库级代码规划任务 | 专有 | 零样本 | 块指标、编辑指标 | 概念化/概念验证 | NA | NA | NA | NA |

&#124; 动态语言可能不适合编码计划方法 &#124;

|

| 4 | Mani 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib66)) | HotNet’s | 2023 |
| --- | --- | --- | --- |

&#124; GPT-4, GPT-3, Text-davinci-003, &#124;

&#124; Bard &#124;

| 微软研究 | 交流 | 代码生成 | 图形操作任务的代码生成 | 公开代码库 | 零样本 | 准确性 | 概念化/PoC | \ul[链接](https://github.com/microsoft/NeMoEval) | 是 | NA | NA |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 高质量领域特定代码合成仍然是一个未解挑战 &#124;

|

| 5 | Ding 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib23)) | ACL | 2023 |
| --- | --- | --- | --- |

&#124; CodeGen-350M, CodeGen-2B, &#124;

&#124; CodeGen-6B, CodeGen-16B, &#124;

| AWS AI Labs | 软件 | 代码生成 | 静态代码分析以完成 | 函数完成数据集 | 无 |
| --- | --- | --- | --- | --- | --- |

&#124; AST 错误百分比，&#124;

&#124; 未定义变量、未使用的变量等 &#124;

| 概念化/PoC | NA | NA | 否 | 是 |
| --- | --- | --- | --- | --- |

&#124; 基于跨文件上下文的错误更广泛分类 &#124;

&#124; 未被使用 &#124;

|

| 6 | Li 等 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib54)) | UIST | 2023 |
| --- | --- | --- | --- |

&#124; GPT-3.5 &#124;

&#124; 传统（text-davinci-003）， &#124;

&#124; 传统（code-davinci-002）， &#124;

&#124; 传统（text-davinci-edit-001） &#124;

| NA | 软件 | 代码生成 | 使用 LLMs 的网页定制 | NA | 少样本（上下文学习） | NA | 原型 | NA | 否 | 否 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 对复杂网站定制性能差 &#124;

|

| 7 | Phung 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib80)) | ICER | 2023 | GPT-3.5, GPT-4 | 微软 | 软件 | 代码生成 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; LLM 编程教育辅导员 &#124;

| NA | 零样本 | 匹配 | 概念化/PoC | NA | NA | NA | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 限于 Python 语言和入门教育内容 &#124;

|

| 8 | Gupta 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib32)) | ESEC/FSE | 2023 | CODEX, CODEt5 | 微软 | 软件 | 代码生成 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 使用 LLMs 预测代码编辑 &#124;

| C3PO, Overwatch | 少样本（上下文学习） | 代码段的精确匹配 | 概念化/PoC | NA | NA | NA | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 提出的方法可能由于 LLMs 幻觉而失败 &#124;

&#124; 和上下文长度要求 &#124;

|

| 9 | Dinh 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib24)) | NeurIPS | 2023 | CODEGEN, INCODER | AWS | 软件 | 代码生成 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 基于上下文的代码补全 &#124;

| Buggy-HumanEval, Buggy-FixEval | 少样本和 CoT | pass@k | 概念化/PoC | \ul[链接](https://github.com/amazon-science/buggy-code-completion) | 是 | 否 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 提出的方法可能与通用软件开发不一致 &#124;

&#124; 设置为基于编程竞赛提交的有缺陷数据集 &#124;

|

| 10 | Athiwaratkun 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) | ICLR | 2023 | 仅解码器的变换器模型 | AWS AI Labs | 软件 | 代码生成 | 在多语言编程数据集上评估 LLMs | MBXP、多语言 HumanEval、MathQA-X | 零-shot 和少-shot | pass@k 分数 | 概念化/原型验证 | \ul[链接](https://github.com/amazon-science/mxeval) | 是 | 无 | 是 | 缺乏特定语言的评估 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 11 | Jo 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib45)) | CHI | 2023 | HyperCLOVA | NAVER AI Lab、NAVER CLOUD | 医疗保健 | 对话式 | 语音助手 | 无 | 零-shot | 无 | 部署 | \ul[链接](https://guide.ncloud-docs.com/docs/en/clovacarecall-overview) | 无 | 否 | 是 |

&#124; 试点对象的年龄分布偏斜和试点部署时间 &#124;

|

| 12 | Valencia 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib97)) | CHI | 2023 | 无 | Google Research | 无障碍 | 对话式 | 评估 LLMs 作为 AAC 用户的工具 | 专有 | 无 | 无 | 概念化/原型验证 | 无 | 无 | 无 | 是 | 无 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 13 | Gadiraju 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib28)) | FAccT | 2023 | LaMDA | Google Research | 无障碍 | 对话式 | 聊天机器人 | 无 | 无 | 人工评估 | 无 | 无 | 是 | 否 | 是 | 个别焦点小组内的身份多样性有限 |
| 14 | Feng 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib25)) | NeurIPS | 2023 |

&#124; Codex、GPT-3.5、GPT-3.5-chat，&#124;

&#124; GPT-4 &#124;

| Google | 通用 | 数据生成 |
| --- | --- | --- |

&#124; 文本到图像生成的视觉规划 &#124;

| NSR-1K、3D-FRONT | 少-shot（上下文学习） |
| --- | --- |

&#124; CLIP 余弦相似度，&#124;

&#124; GLIP 精度，&#124;

&#124; 属性绑定准确性，&#124;

&#124; KL 散度 &#124;

| 概念化/原型验证 | \ul[链接](https://github.com/weixi-feng/LayoutGPT) | 是 | 无 | 是 |
| --- | --- | --- | --- | --- |

&#124; 生成过于密集的布局和异常大小的边界框 &#124;

|

| 15 | Golde 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib31)) | ACL | 2023 |
| --- | --- | --- | --- |

&#124; 使用了 Hugginhface 的现有 LLMs，&#124;

&#124; openAI、Azure、Anthropic、Cohere &#124;

| Deepset GMBH | 通用 | 数据生成 | 生成标记的训练数据 | IMDB、MRPC、SNLI、TREC-6、SQUAD | 零-shot 和少-shot | F1 分数 | 概念化/原型验证 | \ul[链接](https://github.com/flairNLP/fabricator) | 否 | 否 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 评估仅覆盖常见任务的子集 &#124;

|

| 16 | Yu 等 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib110)) | EMNLP 工业轨道 | 2023 | GPT-4、LLaMA | 亚马逊 | 金融 | 预测 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 可解释的金融时间序列预测 &#124;

|

&#124; 股票价格数据、公司资料数据，&#124;

&#124; 财务/经济新闻数据 &#124;

| 零-shot 和少-shot |
| --- |

&#124; 二进制精度、Bin 精度，&#124;

&#124; MSE、ROUGE-1、2 &#124;

| 概念化/原型验证 | 无 | 是 | 是 | 无 |
| --- | --- | --- | --- | --- |

&#124; 对其他类型的金融时间数据的泛化尚未探索 &#124;

|

| 17 | De La Torre et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib19)) | NeurIPS | 2023 |
| --- | --- | --- | --- |

&#124; 混合现实语言模型（LLMR） &#124;

&#124; Dall.E-2 &#124;

&#124; GPT-4 &#124;

| 微软，微软研究院 | 通用 | 框架 |
| --- | --- | --- |

&#124; 生成互动 3D 对象 &#124;

| NA | NA |
| --- | --- |

&#124; 错误率，平均生成时间。&#124;

| 发展 | NA | NA | NA | 是 |
| --- | --- | --- | --- | --- |

&#124; 对复杂任务，可能仍需手动编辑代码 &#124;

|

| 18 | Wang et al. ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib101)) | CHI | 2023 | PaLM | 谷歌研究 | NLP | 框架 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 对话交互 &#124;

&#124; 配备移动 UI &#124;

|

&#124; PixelHelp，AndroidHowTo，&#124;

&#124; Rico，Screen2Words，&#124;

| 零样本和少样本 |
| --- |

&#124; 语法正确性，UI 相关性，&#124;

&#124; 问题覆盖率，BLEU，CIDEr，&#124;

&#124; ROUGE-L，和 METEOR，微 F1 &#124;

| 概念化/原型 | \ul[链接](https://github.com/google-research/google-research/tree/master/llm4mobile) | 是 | NA | 是 |
| --- | --- | --- | --- | --- |

&#124; 无法处理生成不正确或不相关的信息 &#124;

|

| 19 | Hoshi et al. ([2023](https://arxiv.org/html/2402.14558v1#bib.bib37)) |
| --- | --- |

&#124; EMNLP 系统 &#124;

&#124; 演示 &#124;

| 2023 |
| --- |

&#124; Llama-2 Chat（13B，70B），&#124;

&#124; WizardVicunaLM-13B，&#124;

&#124; Vicuna &#124;

| Kioxia 公司 | 通用 | 框架 |
| --- | --- | --- |

&#124; 知识密集型任务的框架 &#124;

| KILT 基准 | NA |
| --- | --- |

&#124; 精确匹配，F1，准确度，RL，&#124;

&#124; R-精确度 &#124;

| 部署 | \ul[链接](https://github.com/yhoshi3/RaLLe) | 是 | NA | 是 | 在 KILT 任务上落后于专业 RAG 模型 |
| --- | --- | --- | --- | --- | --- |
| 20 | Zhang et al. ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib114)) | CoRL | 2023 | LLaMA-13b | 谷歌 AI | 机器人学 | 框架 |

&#124; LLM 引导技能链 &#124;

| ALFRED | 零样本 | NA | 发展 | NA | NA | 否 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 贪婪技能链可能不是生成一致行为的最佳选择 &#124;

|

| 21 | Liu et al. ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib61)) | EMNLP | 2023 |
| --- | --- | --- | --- |

&#124; GPT-3.5-turbo，text-davinci-003，&#124;

&#124; GPT-4-32k &#124;

| 微软健康未来 | 医疗保健 | 框架 |
| --- | --- | --- |

&#124; 对 GPT-4 理解的评估 &#124;

&#124; 放射科任务的生成 &#124;

|

&#124; MS-CXR-T，RadNLI，Chest ImaGenome，&#124;

&#124; MIMIC，Open-i &#124;

|

&#124; 零样本，少样本，一样本，&#124;

&#124; 多样本，CoT &#124;

|

&#124; 宏 F1，微 F1，RougeL，&#124;

&#124; CheXbert 评分 &#124;

| 部署 | NA | NA | 是 | 是 |
| --- | --- | --- | --- | --- |

&#124; 对总结任务的发现进行定性评估 &#124;

&#124; 限于单一放射科医师 &#124;

|

| 22 | Jiang et al. ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib43)) | EMNLP | 2023 | GPT-3.5-Turbo-0301 和 Claude-v1.3 | 微软 | NA | 无 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 提升推理速度的提示压缩 &#124;

|

&#124; GSM8K, BBH, ShareGPT, &#124;

&#124; Arxiv-March23 &#124;

| 零样本 | BLEU, ROUGE, BERTScore | 概念化/概念验证 | \ul[链接](https://github.com/microsoft/LLMLingua) | 是 | NA | 是 |
| --- | --- | --- | --- | --- | --- | --- |

&#124; 当提示压缩超过 25%时，性能下降 &#124;

|

| 23 | Yang 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib106)) | EMNLP 工业轨道 | 2023 | GPT-4, GPT3.5, LLaMA-2 | 微软 | NLP | 问答 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 特定领域工业 QA &#124;

| MSQA | 零样本 |
| --- | --- |

&#124; BLEU, ROUGE, METEOR, BERTScore, &#124;

&#124; F1, 关键词/跨度命中率 (KHR), &#124;

&#124; 可以回答的比率 (CAR), 基于 LLM 的指标 &#124;

| 概念化/概念验证 | NA | NA | NA | NA |
| --- | --- | --- | --- | --- |

&#124; 仅适用于英语数据 &#124;

|

| 24 | Zeng 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib112)) | ICAIF | 2023 | GPT-3.5-turbo | 摩根大通 AI 研究 | 金融 | 问答 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 动态工作流生成 &#124;

|

&#124; NCEN-QA, NCEN-QA-Easy, &#124;

&#124; NCEN-QA-Intermediate, NCEN-QA-Hard &#124;

| 零样本 | NA | 原型 | NA | NA | 是 | 是 | NA |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 25 | Hu 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib38)) | ICCV | 2023 | GPT-3 | 微软，艾伦人工智能研究所 | 视觉 | 问答 |

&#124; 基于自然语言的提问感知字幕模型 &#124;

| COCO, OK-VQA, A-OKVQA, WebQA | 少样本（上下文学习） | 准确率 | 概念化/概念验证 | \ul[链接](https://github.com/nerfies/nerfies.github.io) | NA | 否 | 混合 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 仅关注基于知识的 VQA 任务 &#124;

|

| 26 | Liu 等 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib59)) | NeurIPS | 2023 |
| --- | --- | --- | --- |

&#124; GPT-3.5 turbo, GPT-4, &#124;

&#124; ChatGLM, LLaMA, &#124;

&#124; Vicuna, Alpaca &#124;

| 阿里巴巴集团，蚂蚁集团 | 医疗 | 问答 |
| --- | --- | --- |

&#124; 医疗领域 QA &#124;

| CMExam | 少样本（上下文学习） | 准确率，加权 F1，BLEU，ROUGE | 概念化/概念验证 | \ul[链接](https://github.com/williamliujl/CMExam/tree/main) | 是 | 是 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 排除非文本问题可能会引入意外的偏差 &#124;

|

| 27 | Imani 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib40)) | EMNLP 工业轨道 | 2023 | text-davinci-002, PaLM | 微软 | NLP | 推理 | 数学推理 | MultiArith 数据集 | 零样本、少样本和 CoT | 准确率 | 概念化/概念验证 | NA | 是 | NA | NA |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 产生不正确结果的非平凡概率 &#124;

&#124; 使用代数和 Python 表达式 &#124;

|

| 28 | Lu 等 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib64)) | NeurIPS | 2023 | GPT-3.5-turbo, GPT-4 | 微软研究院 | 通用 | 推理 | 多模态知识密集型推理任务 | ScienceQA, TabMWP | 零样本和 CoT | 准确率 | 概念化/概念验证 | \ul[链接](https://github.com/lupantech/chameleon-llm) | 是 | NA | NA | 对复杂任务计算开销大 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 29 | Li 等人 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib55)) | CIKM | 2023 |

&#124; GPT-Neo-1.3B, &#124;

&#124; GPT-Neo-2.7B, &#124;

&#124; GPT-J-6B, &#124;

&#124; Falcon-7B-Instruct &#124;

| Amazon Alexa AI | 政治, 教育 | 推理 |
| --- | --- | --- |

&#124; 基于个性的 LLM 可操控性 &#124;

| OpinionQA | 无 |
| --- | --- |

&#124; 用户研究 &#124;

| 概念化/概念验证 | 无 | 无 | 否 | 是 | 复杂个性可能无法实现 |
| --- | --- | --- | --- | --- | --- |
| 30 | Ye 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib107)) | SIGIR | 2023 | CODEX | 阿里巴巴集团 | 通用 | 推理 |

&#124; 基于文本提示的表格推理 &#124;

| TabFact, WikiTableQuestion, FetaQA | Fewshot（上下文学习） |
| --- | --- |

&#124; 二分类准确性, &#124;

&#124; 指称准确性, BLEU, &#124;

&#124; ROUGE-1, ROUGE-2 和 ROUGE-L &#124;

| 概念化/概念验证 | 无 | 是 | 是 | 是 | 无 |
| --- | --- | --- | --- | --- | --- |
| 31 | Pawlowski 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib76)) | ICML Workshop | 2023 | GPT-3.5, GPT-4 | Microsoft Research | 通用 | 推理 |

&#124; 基于 LLM 的因果问答系统 &#124;

| 无 | 文本补全 | 无 | 概念化/概念验证 | 无 | 无 | 无 | 是 | 随着上下文长度增加性能下降 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 32 | Sanner 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib88)) | RecSys | 2023 | PaLM | Google | 零售 | 推荐系统 |

&#124; 视觉增强的实时对话 &#124;

| 专有 | 补全, zero-shot 和 Few-shot | 平均 NDCG | 概念化/概念验证 | 无 | 否 | 是 | 是 | 无 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 33 | Yamazaki 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib105)) | 高级机器人技术 | 2023 | Hyperclova | LINE Corporation | 通用 | 推荐系统 | 语音聊天机器人 | 专有 | Fewshot（上下文学习） |

&#124; 信息量技术评分, &#124;

&#124; 自然度, 喜好度, &#124;

&#124; 对话满意度 &#124;

| 测试 | 无 | 无 | 否 | 是 |
| --- | --- | --- | --- | --- |

&#124; 对低频词汇提供较长的 &#124;

&#124; 响应会使用户信息过载和产生幻觉 &#124;

|

| 34 | Maragheh 等人 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib67)) | ICML Workshop | 2023 | PaLM2 | Walmart Global Tech | 零售 | 推荐系统 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 增强推荐能力 &#124;

&#124; 系统 &#124;

| 专有 | Zero-shot | MRR, NDCG | 概念化/概念验证 | 无 | 无 | 无 | 无 | 无 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 35 | Alfassy 等人 ([2022](https://arxiv.org/html/2402.14558v1#bib.bib4)) | NeurIPS | 2022 | CLIP |

&#124; IBM Research, &#124;

&#124; MIT-IBM AI-Watson Lab &#124;

| 视觉 | 检索 |
| --- | --- |

&#124; 对专家任务中的 LLM 进行评估，测量 \ &#124;

&#124; 图像到文本和文本到图像的检索 &#124;

| FETA |
| --- |

&#124; Zero-shot, Few-shot, One-shot, &#124;

&#124; 多-shot &#124;

| 准确性 | 概念化/概念验证 | 无 | 无 | 无 | 无 |
| --- | --- | --- | --- | --- | --- |

&#124; FETA 仅包含可用数据集的一小部分 &#124;

&#124; 针对不同专家 V&L 数据领域的技术文档 &#124;

|

| 36 | Yu 等 ([2023a](https://arxiv.org/html/2402.14558v1#bib.bib109)) | ICLR | 2023 | InstructGPT | Microsoft 认知服务研究 | 通用 | 检索 | 基于 LLM 的知识密集型任务检索 | TriviaQA, WebQ | 零样本 | 准确性, F1, ROUGE-L | 概念化/PoC | \ul[链接](https://github.com/wyu97/GenRead) | NA | 是 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 更新知识到新领域的能力有限 &#124;

|

| 37 | Wang 等 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib102)) | EMNLP | 2023 |
| --- | --- | --- | --- |

&#124; Text-davinci-001, Text-davinci-003, &#124;

&#124; GPT-4, Babbage, curie &#124;

| Microsoft Research | 通用 | 检索 | 查询扩展基于检索的系统 | MS-MARCO, TREC DL 2019 | Fewshot | MRR, nDCG | 概念化/PoC |  | NA | NA | NA | 检索系统的效率 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 38 | Liu 等 ([2023c](https://arxiv.org/html/2402.14558v1#bib.bib62)) | CHI | 2023 | GPT3 | Google Research | 通用 | 检索 |

&#124; 增强视频会议 &#124;

&#124; 带有视觉字幕 &#124;

| VC 1.5K | 零样本 | 用户研究 | 部署 | \ul[链接](https://github.com/google/archat) | 是 | 是 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 对话中的视觉字幕应有一个阈值 &#124;

&#124; 过滤掉潜在的分散或不适当的内容 &#124;

|

| 39 | Lu 等 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib65)) | NeurIPS | 2023 |
| --- | --- | --- | --- |

&#124; GPT2-S (117M), &#124;

&#124; GPT2-L (774M) [29], &#124;

&#124; OpenLLaMA-7B (7B) &#124;

|

&#124; AWS GAIIC, &#124;

&#124; AWS AI &#124;

| 医疗保健 | 检索 | 从医学影像编写放射学报告 | MIMIC-CXR | 无 |
| --- | --- | --- | --- | --- |

&#124; 事实完整性和正确性 &#124;

&#124; F1-CXB-14 分数, F1-CXB-5, &#124;

&#124; BLEU4, ROUGE-L &#124;

| 概念化/PoC | \ul[链接](https://aws.amazon.com/machine-learning/responsible-machine-learning/aws-healthscribe/) | NA | 否 | 是 |
| --- | --- | --- | --- | --- |

&#124; 软视觉提示未能获得一致关注, &#124;

&#124; 尤其是在使用 LLM 时。 &#124;

|

| 40 | Alaofi 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib3)) | SIGIR | 2023 | text-davinci-003 | Microsoft | 通用 | 检索 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 生成查询变体以进行构建 &#124;

&#124; 测试集合和文档池 &#124;

| UQV100 | 一次性 |
| --- | --- |

&#124; Jaccard 指数, RBP, RBO &#124;

| 概念化/PoC | NA | NA | NA | 是 |
| --- | --- | --- | --- | --- |

&#124; 小规模人类生成的数据不足 &#124;

&#124; 不足以进行少样本提示 &#124;

|

| 41 | Park 和 You ([2023](https://arxiv.org/html/2402.14558v1#bib.bib74)) | EMNLP 行业跟踪 | 2023 | CTI-BERT | IBM T. J. Watson 研究中心 | 安全 | 安全 | 网络威胁情报 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 攻击描述, 安全教材, &#124;

&#124; 学术论文, 安全 Wiki, &#124;

&#124; 威胁报告, 漏洞 &#124;

| NA | 微观和宏观 F1 分数 | 概念化/PoC | NA | 是 | 是 | 是 | 仅在英语数据上预训练。 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 42 | Foley 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib27)) | ACL | 2023 |

&#124; BERT, GPT, BLOOM, codegen-350M, &#124;

&#124; DialoGPT, DistilGPT2, &#124;

&#124; OPT, GPT-Neo, xlnet-base-cased, &#124;

&#124; multilingual-miniLM-L12-v2 &#124;

| IBM 研究 | 一般 | 安全 |
| --- | --- | --- |

&#124; 回溯至微调模型的起源 &#124;

&#124; 缓解 LLM 的问责问题 &#124;

|

&#124; GitHub, The BigScience ROOTS Corpus, &#124;

&#124; CC-100, Reddit 和 THEPILE &#124;

| NA | F1, ROC | 概念化/概念验证 | NA | 是 | 是 | 是 |
| --- | --- | --- | --- | --- | --- | --- |

&#124; 仅考虑了有限数量的 LLM 进行研究。 &#124;

|

| 43 | Peng 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib78)) | ACL | 2023 | text-embedding-ada-002, BERT |
| --- | --- | --- | --- | --- |

&#124; 微软亚洲研究院，索尼人工智能， &#124;

&#124; 微软 STC 亚洲 &#124;

| 安全 | 安全 |
| --- | --- |

&#124; EaaS（嵌入服务）的版权保护 &#124;

&#124; 一种服务）LLMs &#124;

| SST2, Mind, Enron Spam, AG 新闻 | NA | 准确性，检测性能 | 概念化/概念验证 | NA | NA | NA | NA | NA |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 44 | Deng 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib20)) | WWW | 2023 | GPT-3, PaLM | Google 研究 | 财务 | 情感分析 |

&#124; 金融数据的标签生成 &#124;

| FiQA-News | 少样本（上下文学习） | 准确性 | 概念化/概念验证 | NA | NA | 否 | 是 | - |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 45 | Lee 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib53)) | EMNLP 行业跟踪 | 2023 | HyperCLOVA (30B 和 82B) 和 GPT-3 | NAVER AI 实验室 | 一般 | 社会影响 | 社会偏见风险缓解 | KoSBi | NA | F1 分数 | 概念化/概念验证 | \ul[链接](https://github.com/naver-ai/korean-safety-benchmarks) | 是 | 是 | 是 |

&#124; 过滤模型的性能不是很有竞争力 &#124;

|

| 46 | Sun 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib93)) | EMNLP 行业跟踪 | 2023 |
| --- | --- | --- | --- |

&#124; GPT-3.5-turbo-0301, Falcon 40B-instruct, &#124;

&#124; Falcon 7B-instruct, Dolly-v2-12b &#124;

| Apple | 安全 | 社会影响 |
| --- | --- | --- |

&#124; 综合处理争议问题 &#124;

| DELPHI | 零样本 |
| --- | --- |

&#124; 争议认可率, &#124;

&#124; 全面回答率 &#124;

| 概念化/概念验证 | \ul[链接](https://github.com/apple/ml-delphi) | 是 | 是 | 是 |
| --- | --- | --- | --- | --- |

&#124; 数据集可能无法覆盖所有争议问题。 &#124;

&#124; 可能包含过期的地面真实标签争议 &#124;

|

| 47 | Athiwaratkun 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib6)) | ICLR | 2023 | 仅解码器的变换器模型 | AWS AI 实验室 | 软件 | 代码生成 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 多语言 LLMs 的评估 &#124;

&#124; 编程数据集 &#124;

| MBXP, 多语言 HumanEval, MathQA-X | 零样本和少样本 | pass@k 分数 | 概念化/概念验证 | \ul[链接](https://github.com/amazon-science/mxeval) | 是 | NA | NA |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 不支持特定语言功能 &#124;

|

| 48 | Laskar 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib52)) | EMNLP 行业跟踪 | 2023 |
| --- | --- | --- | --- |

&#124; GPT-4, GPT3.5, PaLM-2, &#124;

&#124; LLaMA-2 13b, 7b &#124;

| Dialpad Canada Inc | 自然语言处理 | 摘要 | 商务会议摘要 | QMSUM, AMI, ICSI | 零样本 | ROUGE, BERTScore | 概念化/原型验证 | NA | 是 | 是 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 对领域特定数据集的泛化能力存在疑问 &#124;

&#124; 因为仅使用了学术数据集进行测试 &#124;

|

| 49 | Fetahu 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib26)) | EMNLP 行业跟踪 | 2023 | FLAT-T5 | 亚马逊 | 自然语言处理 | 摘要 | 产品标题长度的摘要 | NA | NA | ROUGE, BLEU | 概念化/原型验证 | NA | NA | NA | NA | 不保证摘要中包含显著词汇 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 50 | Acharya 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib1)) | RecSys | 2023 | Alpaca-LoRa | Sony Research India | 零售 | 摘要 |

&#124; 无需网络爬虫生成产品描述 &#124;

| MovieLens, Goodreads 书籍图谱 | 少样本（上下文学习） |
| --- | --- |

&#124; 命中率，归一化折扣 &#124;

&#124; 累积增益（NDCG）, &#124;

&#124; 平均倒排排名（MRR）&#124;

| 概念化/原型验证 | NA | NA | NA | NA |
| --- | --- | --- | --- | --- |

&#124; 生成事实不准确的描述 &#124;

|

| 51 | Jin 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib44)) | ESEC/FSE | 2023 | GPT-3.X | 微软 | 基础设施 | 摘要 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 云故障管理 &#124;

| 专有 | NA | BLEU-4, ROUGE-L 和 METEOR | 部署 | NA | NA | NA | 是 | 评价指标未完全反映停机摘要的可读性和有用性 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 52 | Shen 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib90)) | CHI In2Writing 研讨会 | 2023 | NA | Allen 人工智能研究所 | 自然语言处理 | 摘要 |

&#124; 基于证据的知识生成 &#124;

| NA | 少样本（上下文学习） | NA | NA | NA | NA | NA | 是 | NA |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 53 | Zhao 等 ([2023b](https://arxiv.org/html/2402.14558v1#bib.bib119)) | EMNLP 行业跟踪 | 2023 |

&#124; GPT4, TULU, Pythia, Alpaca, &#124;

&#124; Vicuna, LLaMA-2, GPT-3.5 &#124;

| Allen 人工智能研究所 | 自然语言处理 | 表格到文本生成 |
| --- | --- | --- |

&#124; 对大语言模型在表格到文本生成的评估 &#124;

| LOTNLG, F2WTQ | 零样本和少样本 |
| --- | --- |

&#124; BLEU, ROUGE, SP-Acc, NLI-Acc, &#124;

&#124; TAPAS-Acc, TAPEX-Acc, 精确匹配, &#124;

&#124; F1 分数, 准确率 &#124;

| 概念化/原型验证 | NA | 是 | NA | 是 | NA |
| --- | --- | --- | --- | --- | --- |
| 54 | Mihindukulasooriya 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib69)) | ISWC | 2023 | GPT4, Llama2, FLAN-T5 | IBM 研究 | 自然语言处理 | 表格到文本生成 |

&#124; 元数据自动化 &#124;

&#124; 生成和丰富 &#124;

| NA | 无 | NA | 概念化/原型验证 | NA | NA | NA | NA | NA |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 55 | Singha 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib92)) | NeurIPS | 2023 | GPT-3.5 (text-davinci-003 endpoint) | Microsoft | 通用 | 表格到文本生成 |

&#124; 噪声引入以更好地 &#124;

&#124; 对表格结构的理解 &#124;

|

&#124; AirQuality, HousingData, Diabetes, &#124;

&#124; 葡萄酒测试, Iris, Titanic, &#124;

&#124; 和 ENB2012_data &#124;

| 零样本 | F1 分数 | 概念验证/原型 | \ul[链接](https://github.com/microsoft/prose) | 是 | NA | NA |
| --- | --- | --- | --- | --- | --- | --- |

&#124; 结构任务的性能与下游任务（如表格） &#124;

&#124; 问答仍然是一个未解决的挑战。 &#124;

|

| 56 | Wake 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib98)) | IEEE Access | 2023 | ChatGPT | Microsoft | 机器人技术 | 任务规划 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 翻译自然语言指令 &#124;

&#124; 转换为可执行的机器人动作 &#124;

| NA | Fewshot | 可执行性, 正确性 | 概念验证/原型 | \ul[链接](https://github.com/microsoft/ChatGPT-Robot-Manipulation-Prompts) | 是 | 是 | 是 | 仅考虑静态环境 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 57 | Saadany 和 Orasan ([2023](https://arxiv.org/html/2402.14558v1#bib.bib87)) | EMNLP 行业跟踪 | 2023 | GPT- text-embedding-ada-002 | Kingfisher Labs Ltd , Just Access | 法律 | 工具 |

&#124; 自动将判决与书签链接 &#124;

&#124; 法庭听证视频中的 &#124;

| 英国国家档案馆 | 零样本 | 平均精度 (MAP), 召回率 | 概念验证/原型 | NA | 是 | 是 | NA | NA |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 58 | Petridis 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib79)) | CHI 扩展摘要 | 2023 | - | Google Research | 通用 (HCI) | 工具 | 输入-输出交互, 帧变化 | NA | 零样本 | 问卷 | 概念验证/原型 | NA | NA | NA | 是 |

&#124; 需要对 &#124;

&#124; 功能性提示如何影响原型过程进行正式评估和深入分析 &#124;

|

| 59 | Dibia ([2023](https://arxiv.org/html/2402.14558v1#bib.bib22)) | ACL | 2023 | NA | Microsoft Research | 通用 | 工具 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 语法无关的自动生成 &#124;

&#124; 可视化和信息图表 &#124;

| 专有 | 零样本和少样本 |
| --- | --- |

&#124; 可视化错误率 (VER), &#124;

&#124; 自我评估的可视化质量 &#124;

&#124; (SEVQ), 代码准确性, &#124;

&#124; 数据转换, 目标合规, &#124;

&#124; 可视化类型, 数据编码, &#124;

&#124; 和美学 &#124;

| 原型 | \ul[链接](https://microsoft.github.io/lida/) | 是 | 否 | 是 |
| --- | --- | --- | --- | --- |

&#124; 代码执行步骤增加了计算复杂度。 &#124;

|

| 60 | Singh 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib91)) | ICRA | 2023 |
| --- | --- | --- | --- |

&#124; text-davinci-*, &#124;

&#124; Codex, &#124;

&#124; GPT3 &#124;

| Nvidia 公司 | 机器人技术 | 工具 | 使用 LLM 生成程序化机器人指令 | NA | Fewshot (上下文学习) |
| --- | --- | --- | --- | --- | --- |

&#124; 成功率 (SR), &#124;

&#124; 目标条件回忆 (GCR), &#124;

&#124; 可执行性(Exec) &#124;

| 开发 | \ul[链接](https://github.com/NVlabs/progprompt-vh) | 是 | 否 | 是 |
| --- | --- | --- | --- | --- |

&#124; 机器人行动成功反馈不适用 &#124;

&#124; 与代理共享导致失败场景 &#124;

|

| 61 | Awasthi 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib8)) | EACL | 2023 |
| --- | --- | --- | --- |

&#124; mT5-Large, &#124;

&#124; PaLM &#124;

| Google 研究印度 | NLP | 翻译 | 将英文数据集翻译成其他几种语言 | MTOP, MASSIVE | 零样本和少样本 | 精确匹配校正 | 原型 | NA | NA | 否 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 计算成本高 &#124;

|

| 62 | Kwon 和 Mihindukulasooriya ([2023](https://arxiv.org/html/2402.14558v1#bib.bib51)) | ACL | 2023 | BERT, ALBERT, RoBERTa | IBM 研究 | 一般性 | 可信 AI | 检查基础模型的公平性和偏见 | CrowS-Pairs | NA | NA | 概念化/概念验证 | \ul[链接](https://github.com/IBM/finspector) | NA | NA | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 工具的有效性未测试解码器模型。 &#124;

|

| 63 | Ramakrishna 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib85)) | EMNLP | 2023 |
| --- | --- | --- | --- |

&#124; GPTNeo-2.7B, GPTJ-6B, &#124;

&#124; Open-LLaMA-7B, &#124;

&#124; RedPajama-7B, GPT3.5-Turbo, &#124;

&#124; GPT4 &#124;

| 亚马逊 Alexa AI | 安全 | 可信 AI | 评估 LLM 的幻觉问题 | DBpedia, TriviaQA | 零样本 |
| --- | --- | --- | --- | --- | --- |

&#124; BLEU, ROUGE, METEOR, &#124;

&#124; BERTScore, AlignScore &#124;

| 概念化/概念验证 | \ul[链接](https://github.com/amazon-science/invite-llm-hallucinations) | NA | NA | NA |
| --- | --- | --- | --- | --- |

&#124; 测试集缺乏多样性。 &#124;

|

| 64 | Kotek 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib50)) | CI | 2023 | 未披露 | 苹果 | 一般性 | 可信 AI | 识别 LLM 中的性别偏见 | 专有 | 零样本 | NA | 概念化/概念验证 | NA | NA | NA | 是 | 结果可能无法反映真实的性别偏见 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 65 | Wan 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib99)) | EMNLP | 2023 | ChatGPT, Alpaca | Adobe Research | 一般性 | 可信 AI | 识别 LLM 中的性别偏见 | WikiBias-Aug | 零样本 | WEAT | 概念化/概念验证 | \ul[链接](https://github.com/uclanlp/biases-llm-reference-letters) | NA | 是 | 是 |

&#124; 仅在分析偏见时考虑二元性别 &#124;

|

| 66 | Kim 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib48)) | NeurIPS | 2023 |
| --- | --- | --- | --- |

&#124; OPT-350M &#124;

&#124; OPT-1.3B &#124;

&#124; OPT- 2.7B &#124;

| NAVER AI 实验室，参数实验室 | 一般性 | 可信 AI | 探测给定 LLM 中的个人信息 | Pile | 少样本（上下文学习） |
| --- | --- | --- | --- | --- | --- |

&#124; 句子匹配, &#124;

&#124; 似然比 &#124;

| 概念化/概念验证 | NA | NA | 是/ | 是 |
| --- | --- | --- | --- | --- |

&#124; 评估数据集使用私有数据 &#124;

&#124; 信息来源于开源数据集 &#124;

|

| 67 | Rebedea 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib86)) |
| --- | --- |

&#124; EMNLP 系统 &#124;

&#124; 演示 &#124;

| 2023 |
| --- |

&#124; text-davinci-003, GPT-3.5-turbo &#124;

&#124; falcon-7b-instruct, llama2-13b-chat &#124;

| NVIDIA | 通用 | 可信赖的 AI |
| --- | --- | --- |

&#124; 添加可编程护栏的工具包 &#124;

&#124; 会话型 LLMs &#124;

|

&#124; 人工智能红队和 &#124;

&#124; 有用的数据集 &#124;

| Fewshot（上下文学习） | 精确度 | 开发 | \ul[链接](https://github.com/NVIDIA/NeMo-Guardrails/) | 是 | NA | 是 |
| --- | --- | --- | --- | --- | --- | --- |

&#124; 工具包不适合作为独立解决方案 &#124;

|

| 68 | Candel 等 ([2023](https://arxiv.org/html/2402.14558v1#bib.bib13)) |
| --- | --- |

&#124; EMNLP 系统 &#124;

&#124; 演示 &#124;

| 2023 | 通用 | \ulH2O.ai | 通用 | 可信赖的 AI |
| --- | --- | --- | --- | --- |

&#124; 部署和测试各种 LLM 的效率 &#124;

&#124; 关于私有数据库和文档 &#124;

| NA | NA | NA | 部署 | \ul[链接](https://github.com/h2oai/h2ogpt) | 是 | 是 | 是 |
| --- | --- | --- | --- | --- | --- | --- | --- |

&#124; 数据集、偏见和攻击性、使用情况、碳足迹 &#124;

&#124; LLM 的幻觉 &#124;

|

表 6：包含 68 篇研究论文的调查主表。

生成于 2024 年 2 月 22 日 13:53:28 由 [LATExml![[LOGO]](img/70e087b9e50c3aa663763c3075b0d6c5.png)](http://dlmf.nist.gov/LaTeXML/)
