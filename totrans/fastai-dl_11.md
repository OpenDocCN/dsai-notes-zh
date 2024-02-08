# 深度学习 2：第 2 部分第 11 课

> 原文：[`medium.com/@hiromi_suenaga/deep-learning-2-part-2-lesson-11-61477d24dc34`](https://medium.com/@hiromi_suenaga/deep-learning-2-part-2-lesson-11-61477d24dc34)

*我从* [*fast.ai 课程*](http://www.fast.ai/)*中得到的个人笔记。随着我继续复习课程以“真正”理解它，这些笔记将继续更新和改进。非常感谢* [*Jeremy*](https://twitter.com/jeremyphoward) *和* [*Rachel*](https://twitter.com/math_rachel) *给了我这个学习的机会。*

# 链接

[**论坛**](http://forums.fast.ai/t/part-2-lesson-11-in-class/14699/1) **/** [**视频**](https://youtu.be/tY0n9OT5_nA)

# 开始之前：

+   [1cycle 策略](https://sgugger.github.io/the-1cycle-policy.html#the-1cycle-policy) 由 Sylvain Gugger 提出。基于 Leslie Smith 的新论文，该论文结合了之前的两篇关键论文（循环学习率和超级收敛），并通过一系列实验来展示如何实现超级收敛。超级收敛让您训练模型比之前的分阶段方法快五倍（比 CLR 更快，尽管不到五倍）。超级收敛让您可以通过 1 到 3 之间的极高学习率进行训练。超级收敛的有趣之处在于，您在相当大比例的 epochs 中以非常高的学习率进行训练，而在此期间，损失并没有真正得到很大的改善。但诀窍在于它在空间中进行了大量搜索，以找到真正通用的区域。Sylvain 在 fastai 中实现了这一点，通过补充缺失的部分，然后确认他确实在 CIFAR10 上实现了超级收敛。目前称为`use_clr_beta`，但将来会更名。他还在 fastai 库中添加了循环动量。

+   [如何使用序列到序列模型创建神奇的数据产品](https://towardsdatascience.com/how-to-create-data-products-that-are-magical-using-sequence-to-sequence-models-703f86a231f8) 由 Hamel Husain 撰写。他在博客中介绍了训练一个模型来总结 GitHub 问题。这是基于他的博客创建的 Kubeflow 团队的[演示](http://gh-demo.kubeflow.org/)。

# 神经机器翻译 [[5:36](https://youtu.be/tY0n9OT5_nA?t=5m36s)]

让我们构建一个序列到序列模型！我们将致力于机器翻译。机器翻译已经存在很长时间了，但我们将看一种称为神经翻译的方法，它使用神经网络进行翻译。神经机器翻译几年前出现，当时并不像使用经典特征工程和标准 NLP 方法（如词干处理、调整词频、n-gram 等）的统计机器翻译方法那么好。一年后，它比其他所有方法都要好。它基于一个叫做 BLEU 的指标——我们不会讨论这个指标，因为它不是一个很好的指标，也不是很有趣，但每个人都在使用它。

我们看到机器翻译开始沿着我们在 2012 年看到的计算机视觉对象分类的道路前进，后者刚刚超越了最先进技术，现在正在以很快的速度超越它。看这个视频的人不太可能会构建一个机器翻译模型，因为[`translate.google.com/`](https://translate.google.com/)效果相当不错。那么我们为什么要学习机器翻译呢？我们学习机器翻译的原因是，将一些输入（比如法语句子）转换为任意长度的其他输出（比如英语句子）的一般想法是一件非常有用的事情。例如，正如我们刚才看到的，Hamel 将 GitHub 问题转换为摘要。另一个例子是将视频转换为描述，或者基本上任何你需要输出任意长度输出的地方，通常是一个句子。也许是将 CT 扫描转换为放射学报告——这就是你可以使用序列到序列学习的地方。

## 神经机器翻译的四个重大优势[[8:36](https://youtu.be/tY0n9OT5_nA?t=8m36s)]

+   端到端训练：不需要围绕启发式和繁琐的特征工程纠缠。

+   我们能够构建这些分布式表示，这些表示被单个网络中的许多概念共享。

+   我们能够在 RNN 中使用长期状态，因此它比 n-gram 类型的方法使用了更多的上下文。

+   最终，我们生成的文本也使用了 RNN，因此我们可以构建更加流畅的东西。

## BiLSTMs（+Attn）不仅适用于神经机器翻译

我们将使用带有注意力的双向 GRU（基本上与 LSTM 相同）-正如您在上面看到的，这些一般想法也可以用于许多其他事情。

## 让我们来看代码[[9:47](https://youtu.be/tY0n9OT5_nA?t=9m47s)]

[笔记本](https://github.com/fastai/fastai/blob/master/courses/dl2/translate.ipynb)

我们将尝试按照标准的神经网络方法将法语翻译成英语：

1.  数据

1.  架构

1.  损失函数

## 1. 数据

像往常一样，我们需要`(x, y)`对。在这种情况下，x：法语句子，y：英语句子，您将与之比较您的预测。我们需要许多这些法语句子及其相应的英语句子的元组-这被称为“平行语料库”，比语言模型的语料库更难找到。对于语言模型，我们只需要某种语言的文本。对于任何生活语言，互联网上至少会有几千兆字节的文本供您获取。对于翻译，有一些非常好的欧洲语言的平行语料库可用。欧洲议会有每种欧洲语言的每个句子。任何提交给联合国的东西都会被翻译成许多语言。对于法语到英语，我们有一个特别好的东西，那就是几乎任何半官方的加拿大网站都会有法语版本和英语版本[[12:13](https://youtu.be/tY0n9OT5_nA?t=12m13s)]。

## 翻译文件

```py
**from** **fastai.text** **import** *
```

从[`www.statmt.org/wmt15/translation-task.html`](http://www.statmt.org/wmt15/translation-task.html)获取的法语/英语平行文本。这是由克里斯·卡利森-伯奇（Chris Callison-Burch）创建的，他爬取了数百万个网页，然后使用*一组简单的启发式规则将法语 URL 转换为英语 URL（即用“fr”替换为“en”和其他大约 40 个手写规则），并假设这些文档是彼此的翻译*。

```py
PATH = Path('data/translate')
TMP_PATH = PATH/'tmp'
TMP_PATH.mkdir(exist_ok=**True**)
fname='giga-fren.release2.fixed'
en_fname = PATH/f'**{fname}**.en'
fr_fname = PATH/f'**{fname}**.fr'
```

对于边界框，所有有趣的东西都在损失函数中，但对于神经翻译，所有有趣的东西都将在架构中[[13:01](https://youtu.be/tY0n9OT5_nA?t=13m1s)]。让我们快速浏览一下，杰里米希望你特别考虑的一件事是我们在语言建模与神经翻译之间所做任务及如何做任务的关系或相似之处。

第一步是做与语言模型中相同的事情，即通过 RNN 传递一个句子[[13:35](https://youtu.be/tY0n9OT5_nA?t=13m35s)]。

现在在分类模型中，我们有一个解码器，它接收 RNN 输出并提取三个内容：在所有时间步上的`maxpool`和`meanpool`，以及在最后一个时间步上的 RNN 的值，将所有这些堆叠在一起并通过一个线性层[[14:24](https://youtu.be/tY0n9OT5_nA?t=14m24s)]。大多数人不这样做，只使用最后一个时间步，所以我们今天将要讨论的所有内容都使用最后一个时间步。

我们首先通过 RNN 将输入句子传递，然后得到一些“隐藏状态”（即代表编码了句子的 RNN 的输出的向量）。

## 编码器≈骨干[[15:18](https://youtu.be/tY0n9OT5_nA?t=15m18s)]

Stephen 使用了“编码器”这个词，但我们倾向于使用“骨干”。就像当我们谈论向现有模型添加自定义头部时，例如现有的预训练 ImageNet 模型，我们说这是我们的骨干，然后我们在其上添加一些执行我们想要的任务的头部。在序列到序列学习中，他们使用“编码器”这个词，但基本上是一样的——它是神经网络架构的一部分，它接受输入并将其转换为我们可以在其上添加几层以获取某些内容的表示，就像我们为分类器所做的那样，我们在其上堆叠一个线性层以将其转换为情感。不过，这次我们要做的事情比创建情感要困难一点。我们不是将隐藏状态转换为积极或消极情感，而是要将其转换为一系列标记，这些标记是 Stephen 示例中的德语句子。

这听起来更像是语言模型而不是分类器，因为语言有多个标记（对于每个输入单词，都有一个输出单词）。但语言模型也更容易，因为语言模型输出中的标记数量与语言模型输入中的标记数量相同。不仅它们的长度相同，而且它们完全匹配（例如，单词一后面是单词二，单词二后面是单词三，依此类推）。对于翻译语言，你不一定知道单词“he”会被翻译为输出的第一个单词（不幸的是，在这种特殊情况下是这样的）。很多时候，主语宾语顺序会有所不同，或者会插入一些额外的单词，或者我们需要添加一些代词，性别化的文章等。我们将要处理的关键问题是，我们有一个任意长度的输出，其中输出中的标记与输入中的特定标记的顺序不对应。但总体思路是一样的。这里有一个 RNN 来编码输入，将其转换为一些隐藏状态，然后我们要学习的新内容是生成一个序列输出。

## 序列输出[[17:47](https://youtu.be/tY0n9OT5_nA?t=17m47s)]

我们已经知道：

+   从序列到类别（IMDB 分类器）

+   从序列到等长序列（语言模型）

但我们还不知道如何做一个通用的序列到序列，所以这是今天的新内容。除非你真正理解第 6 课中 RNN 的工作原理，否则很少有人能理解这一点。

## 快速回顾第 6 课 [[18:20](https://youtu.be/tY0n9OT5_nA?t=18m20s)]

我们学到，RNN 在其核心是一个标准的全连接网络。下面是一个有 4 层的网络——接受一个输入并通过四层，但在第二层，它将第二个输入连接起来，第三层将第三个输入连接起来，但实际上我们在 Python 中只写了一个四层的神经网络。除了线性层和 ReLU 之外，我们没有使用其他东西。每次输入时我们使用相同的权重矩阵，每次从一个隐藏状态到下一个时我们也使用相同的矩阵——这就是为什么这些箭头是相同颜色的原因。

我们可以将上面的图重新绘制成下面的样子[[19:29](https://youtu.be/tY0n9OT5_nA?t=19m29s)]。

我们不仅重新绘制了它，还将 PyTorch 中的四行线性代码替换为一个 for 循环。记住，我们有一个与下面完全相同的东西，但只有四行代码说`self.l_in(input)`，我们用一个 for 循环替换了它，因为这样重构很好。不改变任何数学、任何想法或任何输出的重构是一个 RNN。它将代码中的一堆单独的行转换为 Python 的 for 循环。

我们可以将输出放在循环内部而不是在循环外部[[20:25](https://youtu.be/tY0n9OT5_nA?t=20m25s)]。如果这样做，我们现在将为每个输入生成一个单独的输出。上面的代码，隐藏状态每次都被替换，最终我们只输出最终的隐藏状态。但是如果我们有一个说`hs.append(h)`并在最后返回`hs`的东西，那就是下面的图片。

要记住的主要事情是当我们说隐藏状态时，我们指的是一个向量——技术上是每个小批量中的每个东西的向量，所以它是一个矩阵，但通常当 Jeremy 谈到这些事情时，他忽略了小批量部分，将其视为单个项目。

我们还学到可以将这些层堆叠在一起[[21:41](https://youtu.be/tY0n9OT5_nA?t=21m41s)]。所以与其上面图中的左侧 RNN 输出，它们可以将输入传递到第二个 RNN 中。如果你此时在想“我想我理解了，但我不太确定”，那意味着你并没有理解。你真正理解的唯一方法是从头开始用 PyTorch 或 Numpy 编写这个。如果你做不到，那么你知道你并没有理解，你可以回去重新观看第 6 课，并查看笔记本，复制一些想法，直到你能够。重要的是你能够从头开始编写它——不到一屏的代码。所以你要确保你可以创建一个 2 层的 RNN。下面是展开它的样子。

为了得到（x，y）句子对，我们将从下载数据集开始[[22:39](https://youtu.be/tY0n9OT5_nA?t=22m39s)]。训练一个翻译模型需要很长时间。谷歌的翻译模型有八层 RNN 堆叠在一起。八层和两层之间没有概念上的区别。如果你是谷歌，有更多的 GPU 或 TPU，那么你可以这样做。否则，在我们的情况下，我们构建的序列到序列模型很可能不需要那种计算水平。所以为了保持简单[[23:22](https://youtu.be/tY0n9OT5_nA?t=23m22s)]，让我们做一个简化的事情，而不是学习如何翻译法语到英语的任何句子，让我们学习如何将法语问题翻译成英语问题——具体是以 what/where/which/when 开头的问题。这里有一个正则表达式，寻找以“wh”开头并以问号结尾的内容。

```py
re_eq = re.compile('^(Wh[^?.!]+\?)')
re_fq = re.compile('^([^?.!]+\?)')lines = ((re_eq.search(eq), re_fq.search(fq)) 
         **for** eq, fq **in** zip(open(en_fname, encoding='utf-8'), 
                           open(fr_fname, encoding='utf-8')))qs = [(e.group(), f.group()) **for** e,f **in** lines **if** e **and** f]
```

我们遍历语料库，打开两个文件中的每一个，每一行是一个平行文本，将它们压缩在一起，获取英语问题和法语问题，并检查它们是否匹配正则表达式。

```py
pickle.dump(qs, (PATH/'fr-en-qs.pkl').open('wb'))
qs = pickle.load((PATH/'fr-en-qs.pkl').open('rb'))
```

将其转储为一个 pickle，这样我们就不必再次执行它，现在我们有 52,000 个句子对，这里有一些示例：

```py
qs[:5], len(qs)*([('What is light ?', 'Qu’est-ce que la lumière?'),
  ('Who are we?', 'Où sommes-nous?'),
  ('Where did we come from?', "D'où venons-nous?"),
  ('What would we do without it?', 'Que ferions-nous sans elle ?'),
  ('What is the absolute location (latitude and longitude) of Badger, Newfoundland and Labrador?',
   'Quelle sont les coordonnées (latitude et longitude) de Badger, à Terre-Neuve-etLabrador?')],
 52331)*
```

这样做的一个好处是，关于什么/谁/在哪里类型的问题往往相当简短。但是，我们可以从零开始学习，没有对语言概念的先前理解，更不用说英语或法语，我们可以创建一个可以将一个语言翻译成另一种语言的东西，对于任何任意问题，只需要 50k 个句子，听起来像是一个难以置信的困难任务。因此，如果我们能取得任何进展，那将是令人印象深刻的。这是一个非常少的数据来进行一个非常复杂的练习。

`qs`包含法语和英语的元组。你可以使用这个方便的习语将它们分开成一个英语问题列表和一个法语问题列表。

```py
en_qs,fr_qs = zip(*qs)
```

然后我们对英语问题进行标记化，对法语问题进行标记化。所以记住，这只是将它们分剒成单独的单词或类似单词的东西。默认情况下，我们这里有的标记器（记住这是一个包装在 spaCy 标记器周围的标记器，它是一个很棒的标记器）假设是英语。所以要求法语，你只需添加一个额外的参数'fr'。第一次这样做时，你会收到一个错误，说你没有安装 spaCy 法语模型，所以你可以运行`python -m spacy download fr`来获取法语模型。

```py
en_tok = Tokenizer.proc_all_mp(partition_by_cores(en_qs))fr_tok = Tokenizer.proc_all_mp(partition_by_cores(fr_qs), 'fr')
```

在这里，你们中没有人会遇到 RAM 问题，因为这不是特别大的语料库，但是有些学生在这一周尝试训练新的语言模型时遇到了 RAM 问题。如果你遇到了，了解这些函数（`proc_all_mp`）实际在做什么是值得的。`proc_all_mp`正在跨多个进程处理每个句子：

上面的函数找出你有多少个 CPU，将其除以二（因为通常情况下，由于超线程，它们实际上并不都是并行工作的），然后并行运行这个`proc_all`函数。这将为你的每个 CPU 生成一个完全独立的 Python 进程。如果你有很多核心，那就是很多 Python 进程——每个人都将加载所有这些数据，这可能会使用完所有你的 RAM。所以你可以用`proc_all`替换它，而不是用`proc_all_mp`来使用更少的 RAM。或者你可以只使用更少的核心。目前，我们正在调用`partition_by_cores`，它在列表上调用`partition`，并要求根据你有多少个 CPU 将其分剒成一些等长的部分。所以你可以将其替换为将列表分割成更小的部分，并在更少的部分上运行它。

在对英语和法语进行标记化后，你可以看到它是如何分割的。

```py
en_tok[0], fr_tok0
```

你可以看到法语的标记化看起来非常不同，因为法语喜欢他们的撇号和连字符。因此，如果您尝试为法语句子使用英语标记器，您将得到一个相当糟糕的结果。您不需要了解大量的自然语言处理（NLP）理念来使用深度学习进行自然语言处理，但只需要一些基本的东西，比如使用正确的标记器对于您的语言是重要的。本周我们研究小组中的一些学生一直在尝试为中文实例构建语言模型，当然中文并没有真正的标记化概念，所以我们开始研究[sentence piece](https://github.com/google/sentencepiece)，它将事物分割成任意的子词单元，所以当 Jeremy 说标记化时，如果您使用的是没有空格的语言，您应该考虑使用 sentence piece 或其他类似的子词单元。希望在接下来的一两周内，我们将能够报告这些中文实验的一些早期结果。

```py
np.percentile([len(o) **for** o **in** en_tok], 90), 
    np.percentile([len(o) **for** o **in** fr_tok], 90)*(23.0, 28.0)*keep = np.array([len(o)<30 **for** o **in** en_tok])en_tok = np.array(en_tok)[keep]
fr_tok = np.array(fr_tok)[keep]pickle.dump(en_tok, (PATH/'en_tok.pkl').open('wb'))
pickle.dump(fr_tok, (PATH/'fr_tok.pkl').open('wb'))en_tok = pickle.load((PATH/'en_tok.pkl').open('rb'))
fr_tok = pickle.load((PATH/'fr_tok.pkl').open('rb'))
```

所以在标记化之后，我们将其保存到磁盘。然后记住，在我们创建标记之后的下一步是将它们转换为数字。为此，我们有两个步骤——第一步是获取所有出现的单词的列表，然后我们将每个单词转换为索引。如果出现的单词超过 40,000 个，那么让我们在那里截断，以免变得太疯狂。我们插入一些额外的标记，用于流的开始（`_bos_`）、填充（`_pad_`）、流的结束（`_eos_`）和未知（`_unk`）。因此，如果我们尝试查找不在最常见的 40,000 个单词中的东西，那么我们使用`deraultdict`返回 3，即未知。

```py
**def** toks2ids(tok,pre):
    freq = Counter(p **for** o **in** tok **for** p **in** o)
    itos = [o **for** o,c **in** freq.most_common(40000)]
    itos.insert(0, '_bos_')
    itos.insert(1, '_pad_')
    itos.insert(2, '_eos_')
    itos.insert(3, '_unk')
    stoi = collections.defaultdict(**lambda**: 3, 
                                   {v:k **for** k,v **in** enumerate(itos)})
    ids = np.array([([stoi[o] **for** o **in** p] + [2]) **for** p **in** tok])
    np.save(TMP_PATH/f'**{pre}**_ids.npy', ids)
    pickle.dump(itos, open(TMP_PATH/f'**{pre}**_itos.pkl', 'wb'))
    **return** ids,itos,stoi
```

现在我们可以继续，通过将每个标记放入我们刚刚创建的字符串到整数字典（`stoi`）中，将每个标记转换为 ID，然后在最后添加数字 2，即流的结束。你在这里看到的代码是 Jeremy 在迭代和实验时编写的代码。因为他在迭代和实验时编写的代码中，99%都是完全错误的、愚蠢的或令人尴尬的，你看不到。但是在他编写代码时，没有必要重构它并使其变得美观，所以他希望你看到他所有的小技巧。与其为`_eos_`标记使用某个常量并使用它，当他在原型设计时，他只做简单的事情。并不是说他最终会得到错误的代码，但他试图在美丽的代码和可行的代码之间找到一些折中。

**问题**：刚听他提到我们将 CPU 数量除以 2，因为使用超线程时，我们不会通过使用所有超线程核心来加速。这是基于实际经验还是有一些潜在原因导致我们无法获得额外的加速？是的，这只是实际经验，并不是所有事情都像这样，但我确实注意到在标记化时，超线程似乎会使事情变慢一点。此外，如果我使用所有核心，通常我想同时做一些其他事情（比如运行一些交互式笔记本），我没有多余的空间来做那些事情。

现在对于我们的英语和法语，我们可以获取一个 ID 列表`en_ids`。当我们这样做时，当然，我们需要确保我们也存储了词汇。如果我们不知道数字 5 代表什么，那么拥有 ID 就没有意义，拥有数字 5 也没有意义。所以这就是我们的词汇`en_itos`和反向映射`en_stoi`，我们可以用它们来在将来转换更多的语料库。

```py
en_ids,en_itos,en_stoi = toks2ids(en_tok,'en')
fr_ids,fr_itos,fr_stoi = toks2ids(fr_tok,'fr')
```

为了确认它是否有效，我们可以通过每个 ID，将 int 转换为字符串，并将其输出 - 现在我们的句子已经回来了，末尾有一个流标记。我们的英语词汇量为 17,000，法语词汇量为 25,000，所以我们处理的词汇量既不太大也不太复杂。

```py
**def** load_ids(pre):
    ids = np.load(TMP_PATH/f'**{pre}**_ids.npy')
    itos = pickle.load(open(TMP_PATH/f'**{pre}**_itos.pkl', 'rb'))
    stoi = collections.defaultdict(**lambda**: 3, 
                                   {v:k **for** k,v **in** enumerate(itos)})
    **return** ids,itos,stoien_ids,en_itos,en_stoi = load_ids('en')
fr_ids,fr_itos,fr_stoi = load_ids('fr')[fr_itos[o] **for** o **in** fr_ids[0]], len(en_itos), len(fr_itos)*(['qu’', 'est', '-ce', 'que', 'la', 'lumière', '?', '_eos_'], 17573, 24793)*
```

## 词向量[[32:53](https://youtu.be/tY0n9OT5_nA?t=32m53s)]

在这一周的论坛上，我们花了很多时间讨论词向量是多么无聊，以及你应该停止对它们感到兴奋 - 现在我们要使用它们。为什么？我们一直在学习如何使用语言模型和预训练的正确模型，而不是预训练的线性单层，这就是词向量的内容，同样适用于序列到序列。但 Jeremy 和 Sebastian 正在开始研究这个问题。对于任何有兴趣创造一些真正新颖且高度可发表的结果的人来说，序列到序列与预训练语言模型的整个领域尚未被触及。Jeremy 相信这将和分类一样好。如果您在这方面有所作为，并且您已经有了一些看起来令人兴奋的东西，并且您希望得到帮助发表它，Jeremy 非常乐意帮助共同撰写论文。因此，当您有一些有趣的结果时，请随时联系。

在这个阶段，我们没有任何东西，所以我们将使用非常少的 fastai[[34:14](https://youtu.be/tY0n9OT5_nA?t=34m14s)]。我们只有词向量 - 所以让我们至少使用体面的词向量。Word2vec 是非常古老的词向量。现在有更好的词向量，而 fast.text 是一个相当不错的词向量来源。有数百种语言可用，您的语言可能会被代表。

fasttext 词向量可从[`fasttext.cc/docs/en/english-vectors.html`](https://fasttext.cc/docs/en/english-vectors.html)获取

fasttext Python 库在 PyPI 中不可用，但这里有一个方便的技巧[[35:03](https://youtu.be/tY0n9OT5_nA?t=35m3s)]。如果有一个 GitHub 存储库，其中包含 setup.py 和 reqirements.txt，您只需在开头加上`git+`，然后将其放入`pip install`中，它就会起作用。几乎没有人似乎知道这一点，如果您去 fasttext 存储库，他们不会告诉您这一点 - 他们会告诉您必须下载它并`cd`进入它，等等，但您不必这样做。您只需运行以下命令：

```py
*# ! pip install git+https://github.com/facebookresearch/fastText.git***import** **fastText** **as** **ft**
```

要使用 fastText 库，您需要下载[fasttext 词向量](https://github.com/facebookresearch/fastText/blob/master/pretrained-vectors.md)（下载“bin plus text”）。

```py
en_vecs = ft.load_model(str((PATH/'wiki.en.bin')))fr_vecs = ft.load_model(str((PATH/'wiki.fr.bin')))
```

以上是我们的英语和法语模型。有文本版本和二进制版本。二进制版本更快，所以我们将使用它。文本版本也有点 buggy。我们将把它转换为标准的 Python 字典，以使其更容易使用[[35:55](https://youtu.be/tY0n9OT5_nA?t=35m55s)]。这只是通过字典理解遍历每个单词，并将其保存为 pickle 字典：

```py
**def** get_vecs(lang, ft_vecs):
    vecd = {w:ft_vecs.get_word_vector(w) 
                **for** w **in** ft_vecs.get_words()}
    pickle.dump(vecd, open(PATH/f'wiki.**{lang}**.pkl','wb'))
    **return** vecden_vecd = get_vecs('en', en_vecs)
fr_vecd = get_vecs('fr', fr_vecs)en_vecd = pickle.load(open(PATH/'wiki.en.pkl','rb'))
fr_vecd = pickle.load(open(PATH/'wiki.fr.pkl','rb'))ft_words = ft_vecs.get_words(include_freq=**True**)
ft_word_dict = {k:v **for** k,v **in** zip(*ft_words)}
ft_words = sorted(ft_word_dict.keys(), 
                     key=**lambda** x: ft_word_dict[x])
```

现在我们有了我们的 pickle 字典，我们可以继续查找一个单词，例如逗号[[36:07](https://youtu.be/tY0n9OT5_nA?t=36m7s)]。这将返回一个向量。向量的长度是这组词向量的维度。在这种情况下，我们有 300 维的英语和法语词向量。

```py
dim_en_vec = len(en_vecd[','])
dim_fr_vec = len(fr_vecd[','])
dim_en_vec,dim_fr_vec*(300, 300)*
```

出于即将看到的原因，我们还想找出我们的向量的平均值和标准差。所以平均值约为零，标准差约为 0.3。

```py
en_vecs = np.stack(list(en_vecd.values()))
en_vecs.mean(),en_vecs.std()*(0.0075652334, 0.29283327)*
```

## 模型数据[[36:48](https://youtu.be/tY0n9OT5_nA?t=36m48s)]

通常，语料库的序列长度具有相当长尾的分布，而最长的序列往往会压倒性地影响时间、内存使用等。因此，在这种情况下，我们将获取英语和法语的第 99 到 97 百分位数，并将它们截断到该数量。最初 Jeremy 使用的是 90 百分位数（因此变量名）：

```py
enlen_90 = int(np.percentile([len(o) **for** o **in** en_ids], 99))
frlen_90 = int(np.percentile([len(o) **for** o **in** fr_ids], 97))
enlen_90,frlen_90*(29, 33)*
```

我们快要完成了[[37:24](https://youtu.be/tY0n9OT5_nA?t=37m24s)]。我们已经有了我们的标记化、数字化的英语和法语数据集。我们有一些词向量。现在我们需要为 PyTorch 准备好它。PyTorch 需要一个`Dataset`对象，希望到现在为止你可以说一个 Dataset 对象需要两个东西——一个长度(`__len__`)和一个索引器(`__getitem__`)。Jeremy 开始编写`Seq2SeqDataset`，结果只是一个通用的`Dataset`[[37:52](https://youtu.be/tY0n9OT5_nA?t=37m52s)]。

```py
en_ids_tr = np.array([o[:enlen_90] **for** o **in** en_ids])
fr_ids_tr = np.array([o[:frlen_90] **for** o **in** fr_ids])**class** **Seq2SeqDataset**(Dataset):
    **def** __init__(self, x, y): self.x,self.y = x,y
    **def** __getitem__(self, idx): **return** A(self.x[idx], self.y[idx])
    **def** __len__(self): **return** len(self.x)
```

+   `A`：数组。它将遍历您传递的每个对象，如果它还不是一个 numpy 数组，它会将其转换为一个 numpy 数组，并返回一个元组，其中包含您传递的所有现在保证为 numpy 数组的对象[[38:32](https://youtu.be/tY0n9OT5_nA?t=38m32s)]。

+   `V`：变量

+   `T`：张量

## 训练集和验证集[[39:03](https://youtu.be/tY0n9OT5_nA?t=39m3s)]

现在我们需要获取我们的英语和法语 ID，并获得一个训练集和一个验证集。互联网上许多代码令人失望的一点是它们没有遵循一些简单的最佳实践。例如，如果你去 PyTorch 网站，他们有一个关于序列到序列翻译的示例部分。他们的示例没有单独的验证集。Jeremy 尝试根据他们的设置进行训练，并使用验证集进行测试，结果发现它严重过拟合。因此，这不仅仅是一个理论问题——实际的 PyTorch 存储库有实际的官方序列到序列翻译示例，它没有检查过拟合，严重过拟合[[39:41](https://youtu.be/tY0n9OT5_nA?t=39m41s)]。此外，它没有使用小批量，因此实际上没有充分利用 PyTorch 的任何效率。即使你在官方 PyTorch 存储库中找到代码，也不要认为它是好的。你会注意到的另一件事是，Jeremy 在互联网上找到的几乎每个 PyTorch 序列到序列模型都明显是从那个糟糕的 PyTorch 存储库中复制的，因为它们都有相同的变量名，有相同的问题，有相同的错误。

另一个例子是，Jeremy 找到的几乎每个 PyTorch 卷积神经网络都没有使用自适应池化层[[40:27](https://youtu.be/tY0n9OT5_nA?t=40m27s)]。换句话说，最终层总是平均池化(7,7)。他们假设前一层是 7 乘 7，如果你使用任何其他大小的输入，你会得到一个异常，因此几乎每个使用 PyTorch 的人都认为 CNNs 有一个基本限制，即它们与输入大小相关联，这自从 VGG 以来就不再成立。因此，每当 Jeremy 拿到一个新模型并将其放入 fastai 存储库时，他都必须搜索“pool”并在开头添加“adaptive”，将 7 替换为 1，现在它适用于任何大小的对象。所以要小心。现在仍然是早期阶段，信不信由你，即使你们大多数人只在过去一年开始了深度学习之旅，你们对许多更重要的实际方面了解的要比大多数在官方存储库中发布和编写东西的人多得多。因此，当阅读其他人的代码时，你需要比你期望的更有一些自信。如果你发现自己在想“那看起来很奇怪”，那不一定是你。

如果你正在查看的存储库没有一个部分说这里是我们做的测试，我们得到了与应该实现的论文相同的结果，那几乎肯定意味着他们没有得到他们正在实现的论文相同的结果，甚至可能根本没有检查[[42:13](https://youtu.be/tY0n9OT5_nA?t=42m13s)]。如果你运行它，肯定不会得到那些结果，因为第一次做对事情很难——Jeremy 需要尝试 12 次。如果他们没有测试过一次，几乎肯定不会起作用。

这是一个获取训练和验证集的简单方法[42:45]。获取一堆随机数 - 每行数据一个，然后看它们是否大于 0.1。这会给你一个布尔值列表。使用该布尔值列表索引到你的数组中以获取一个训练集，使用该布尔值列表的相反值索引到该数组中以获取你的验证集。

```py
np.random.seed(42)
trn_keep = np.random.rand(len(en_ids_tr))>0.1
en_trn,fr_trn = en_ids_tr[trn_keep],fr_ids_tr[trn_keep]
en_val,fr_val = en_ids_tr[~trn_keep],fr_ids_tr[~trn_keep]
len(en_trn),len(en_val)*(45219, 5041)*
```

现在我们可以用我们的 X 和 Y（即法语和英语）创建我们的数据集[43:12]。如果你想将英语翻译成法语，只需交换这两个，就完成了。

```py
trn_ds = Seq2SeqDataset(fr_trn,en_trn)
val_ds = Seq2SeqDataset(fr_val,en_val)
```

现在我们需要创建 DataLoaders[43:22]。我们只需获取我们的数据加载器并传入我们的数据集和批量大小。我们实际上必须转置数组 - 我们不会详细讨论为什么，但如果你感兴趣，我们可以在这一周讨论，但想一想为什么我们可能需要转置它们的方向。由于我们已经完成了所有的预处理，没有必要启动多个工作人员来进行增强等工作，因为没有工作要做。因此，`使 num_workers=1`会节省一些时间。我们必须告诉它我们的填充索引是什么 - 这非常重要，因为将会发生的是，我们有不同长度的句子，fastai 将自动将它们粘在一起并填充较短的句子，使它们长度相等。记住张量必须是矩形的。

```py
bs=125trn_samp = SortishSampler(en_trn, key=**lambda** x: len(en_trn[x]), 
                          bs=bs)
val_samp = SortSampler(en_val, key=**lambda** x: len(en_val[x]))trn_dl = DataLoader(trn_ds, bs, transpose=**True**, transpose_y=**True**, 
                    num_workers=1, pad_idx=1, pre_pad=**False**, 
                    sampler=trn_samp)
val_dl = DataLoader(val_ds, int(bs*1.6), transpose=**True**, 
                    transpose_y=**True**, num_workers=1, pad_idx=1,
                    pre_pad=**False**, sampler=val_samp)
md = ModelData(PATH, trn_dl, val_dl)
```

特别是在解码器中，我们希望我们的填充在末尾，而不是在开头[44:29]：

+   分类器 → 在开头填充。因为我们希望最终的标记代表电影评论的最后一个单词。

+   解码器 → 在末尾填充。正如你将看到的，将填充放在末尾实际上会更好一些。

**采样器 [44:54]** 最后，由于我们输入的句子长度不同，它们都必须通过填充放在一个小批次中以使它们具有相同的大小，我们更希望小批次中的句子已经具有相似的大小。否则，它将与最长的句子一样长，这将浪费时间和内存。因此，我们将使用上次学到的采样器技巧，即对验证集，我们将要求它首先按长度排序。然后对于训练集，我们将随机排列事物的顺序，但大致使得长度相似的事物大致在同一位置。

**模型数据 [45:40]** 在这一点上，我们可以创建一个模型数据对象 - 记住，模型数据对象实际上只做一件事，那就是它说“我有一个训练集和一个验证集，还有一个可选的测试集”，然后把它们放入一个单一对象中。我们还有一个路径，这样它就有地方存储临时文件、模型等等。

在这个例子中，我们几乎没有使用 fastai。我们使用了与 PyTorch 兼容的数据集和数据加载器 - 在幕后实际上使用的是 fastai 版本，因为我们需要它来方便地进行自动填充，因此在 fastai 版本中有一些稍微快速和更方便的调整。我们还使用了 fastai 的采样器，但这里没有太多的事情发生。

## 架构[46:59]

+   这个架构将接受我们的标记序列。

+   它将把它们传递给一个编码器（又名骨干）。

+   这将输出最终的隐藏状态，对于每个句子，它只是一个单一的向量。

这一切都不会是新的[47:41]。这一切都将使用我们已经学过的非常直接简单的技术。

+   然后我们将把它传递到另一个 RNN 中，这是一个解码器。这将有一些新的东西，因为我们需要一个可以逐个单词地进行处理的东西。它会一直进行下去，直到它认为已经完成了句子。它不知道句子将有多长。它会一直进行下去，直到它认为已经完成了句子，然后停止并返回一个句子。

```py
**def** create_emb(vecs, itos, em_sz):
    emb = nn.Embedding(len(itos), em_sz, padding_idx=1)
    wgts = emb.weight.data
    miss = []
    **for** i,w **in** enumerate(itos):
        **try**: wgts[i] = torch.from_numpy(vecs[w]*3)
        **except**: miss.append(w)
    print(len(miss),miss[5:10])
    **return** embnh,nl = 256,2
```

让我们从编码器开始[[48:15](https://youtu.be/tY0n9OT5_nA?t=48m15s)]。在这里的变量命名方面，编码器和解码器具有相同的属性。编码器版本有`enc`，解码器版本有`dec`。

+   `emb_enc`：编码器的嵌入

+   `gru`：RNN。GRU 和 LSTM 几乎是相同的东西。

我们需要创建一个嵌入层，因为要记住 - 我们传递的是单词在词汇表中的索引。我们想要获取它们的 fast.text 嵌入。随着时间的推移，我们可能还想微调以端到端地训练该嵌入。

`create_emb`[[49:37](https://youtu.be/tY0n9OT5_nA?t=49m37s)]：现在重要的是您知道如何设置嵌入的行和列，因此行数必须等于您的词汇量大小 - 因此每个词汇都有一个词向量。嵌入的大小由 fast.text 确定，fast.text 嵌入的大小为 300。因此我们也必须使用大小 300，否则我们无法使用它们的嵌入开始。

`nn.Embedding`最初会给我们一组随机的嵌入[[50:12](https://youtu.be/tY0n9OT5_nA?t=50m12s)]。所以我们将遍历每一个，如果在 fast.text 中找到它，我们将用 fast.text 嵌入替换它。再次提醒您应该已经知道的是（`emb.weight.data`）：

+   一个可学习的 PyTorch 模块具有`weight`属性。

+   `weight`属性是一个具有`data`属性的`Variable`。

+   `data`属性是一个张量

现在我们有了权重张量，我们可以遍历我们的词汇表，查找我们预训练向量中的单词，如果找到，我们将用该预训练向量替换随机权重[[52:35](https://youtu.be/tY0n9OT5_nA?t=52m35s)]。随机权重的标准差为 1。我们的预训练向量的标准差约为 0.3。所以，这是 Jeremy 在原型设计时做的一种巧妙的事情，他只是将其乘以 3。当您看到这个视频时，我们可能已经能够将所有这些序列到序列的内容放入 fastai 库中，您在那里不会找到这样的可怕的黑客行为（希望如此）。但在原型设计时可以尝试各种方法。有些东西可能不在 fast.text 中，这种情况下，我们将继续跟踪[[53:22](https://youtu.be/tY0n9OT5_nA?t=53m22s)]。打印语句是为了让我们看到发生了什么（即为什么我们会丢失东西？）。记住我们大约有 30,000 个，所以我们不会丢失太多。

```py
*3097 ['l’', "d'", 't_up', 'd’', "qu'"]
1285 ["'s", '’s', "n't", 'n’t', ':']*
```

Jeremy 已经开始做一些关于将大词汇量处理整合到 fastai 中的工作 - 还没有完成，但希望到达这里时，这种工作将是可能的[[56:50](https://youtu.be/tY0n9OT5_nA?t=56m50s)]。

```py
**class** **Seq2SeqRNN**(nn.Module):
    **def** __init__(self, vecs_enc, itos_enc, em_sz_enc, vecs_dec, 
                 itos_dec, em_sz_dec, nh, out_sl, nl=2):
        super().__init__()
        self.nl,self.nh,self.out_sl = nl,nh,out_sl
        self.emb_enc = create_emb(vecs_enc, itos_enc, em_sz_enc)
        self.emb_enc_drop = nn.Dropout(0.15)
        self.gru_enc = nn.GRU(em_sz_enc, nh, num_layers=nl, 
                              dropout=0.25)
        self.out_enc = nn.Linear(nh, em_sz_dec, bias=**False**)

        self.emb_dec = create_emb(vecs_dec, itos_dec, em_sz_dec)
        self.gru_dec = nn.GRU(em_sz_dec, em_sz_dec, num_layers=nl, 
                              dropout=0.1)
        self.out_drop = nn.Dropout(0.35)
        self.out = nn.Linear(em_sz_dec, len(itos_dec))
        self.out.weight.data = self.emb_dec.weight.data

    **def** forward(self, inp):
        sl,bs = inp.size()
        h = self.initHidden(bs)
        emb = self.emb_enc_drop(self.emb_enc(inp))
        enc_out, h = self.gru_enc(emb, h)
        h = self.out_enc(h)

        dec_inp = V(torch.zeros(bs).long())
        res = []
        **for** i **in** range(self.out_sl):
            emb = self.emb_dec(dec_inp).unsqueeze(0)
            outp, h = self.gru_dec(emb, h)
            outp = self.out(self.out_drop(outp[0]))
            res.append(outp)
            dec_inp = V(outp.data.max(1)[1])
            **if** (dec_inp==1).all(): **break**
        **return** torch.stack(res)

    **def** initHidden(self, bs): 
        **return** V(torch.zeros(self.nl, bs, self.nh))
```

要知道的关键是编码器接收我们的输入并输出一个隐藏向量，希望它能学会包含关于句子内容以及如何设置的所有信息[[58:49](https://youtu.be/tY0n9OT5_nA?t=58m49s)]。如果它做不到，我们就不能将其输入解码器，并希望它将句子翻译成另一种语言。这就是我们希望它学会的。我们不会采取任何特殊措施来让它学会这样做 - 我们只会做三件事（数据、架构、损失函数），然后抱着幸运的心态。

**解码器[**[**59:58**](https://youtu.be/tY0n9OT5_nA?t=59m58s)**]**：我们现在如何处理新的部分？新部分的基本思想是相同的。我们将做完全相同的事情，但我们将编写自己的 for 循环。这个 for 循环将完全执行 PyTorch 中编码器内部的 for 循环，但我们将手动执行。for 循环有多大？它是一个输出序列长度（`out_sl`），这是传递给构造函数的一个参数，它等于最长英语句子的长度。因为我们正在翻译成英语，所以在这个语料库中至少不可能比这更长。如果我们将其用于某个更长的不同语料库，这将失败 —— 当然你可以传入不同的参数。因此，基本思想是相同的[[1:01:06](https://youtu.be/tY0n9OT5_nA?t=1h1m6s)]。

+   我们将通过嵌入层。

+   我们将通过 RNN、dropout 和线性层。

+   然后，我们将输出附加到一个列表中，该列表将堆叠成一个单个张量并返回。

通常，递归神经网络一次处理整个序列，但我们有一个 for 循环来分别处理序列的每个部分[[1:01:37](https://youtu.be/tY0n9OT5_nA?t=1h1m37s)]。因此，我们必须在开头添加一个主要单位轴（`.unsqueeze(0)`）来表示这是一个长度为一的序列。我们实际上并没有充分利用递归网络 —— 我们可以很容易地用线性层重写这个。

要注意的一件事是`dec_inp`[[1:02:34](https://youtu.be/tY0n9OT5_nA?t=1h2m34s)]：嵌入的输入是什么？答案是前一个我们翻译的单词。基本思想是，如果你试图翻译新句子的第四个单词，但你不知道刚说的第三个单词是什么，那将非常困难。因此，我们将在每个时间步骤中提供这个信息。在开始时，前一个单词是什么？没有。具体来说，我们将从一个流的开始标记（`_bos_`）开始，该标记为零。

`outp`[[1:05:24](https://youtu.be/tY0n9OT5_nA?t=1h5m24s)]：它是一个张量，其长度等于我们英语词汇中的单词数，其中包含每个单词是该单词的概率。

`outp.data.max`：它在其张量中查找具有最高概率的单词。PyTorch 中的`max`返回两个值：第一个是最大概率，第二个是该最大概率在数组中的索引。因此，我们想要第二个项目，即具有最大值的单词索引。

`dec_inp`：它包含单词在词汇表中的索引。如果是 1（即填充），那么表示我们已经完成了 —— 我们已经以一堆填充结束了。如果不是 1，让我们回去继续。

每次，我们将输出（不是单词，而是概率）附加到列表[[1:06:48](https://youtu.be/tY0n9OT5_nA?t=1h6m48s)]中，然后将其堆叠成一个张量，然后我们可以继续将其馈送到损失函数中。

## 损失函数[[1:07:13](https://youtu.be/tY0n9OT5_nA?t=1h7m13s)]

损失函数是分类交叉熵损失。我们有一个概率列表，对应每个类别，其中类别是我们英语词汇中的所有单词，我们有一个目标，即正确的类别（即在此位置的正确单词）。有两个调整，这就是为什么我们需要编写自己的损失函数，但基本上可以看到它将是交叉熵损失。

```py
**def** seq2seq_loss(input, target):
    sl,bs = target.size()
    sl_in,bs_in,nc = input.size()
    **if** sl>sl_in: input = F.pad(input, (0,0,0,0,0,sl-sl_in))
    input = input[:sl]
    **return** F.cross_entropy(input.view(-1,nc), target.view(-1))
```

调整[[1:07:40](https://youtu.be/tY0n9OT5_nA?t=1h7m40s)]：

1.  如果生成的序列长度短于目标序列长度，我们需要添加一些填充。PyTorch 填充函数需要一个 6 元组来填充一个秩为 3 的张量（序列长度、批量大小、词汇表中的单词数）。每对表示在该维度之前和之后的填充。

`F.cross_entropy` 期望一个秩为 2 的张量，但我们有序列长度乘以批量大小，所以让我们展平它。这就是 `view(-1, ...)` 做的事情。

```py
opt_fn = partial(optim.Adam, betas=(0.8, 0.99))
```

`.cuda()` 和 `to_gpu()` 之间的区别：如果没有 GPU，`to_gpu` 不会将其放入 GPU。您还可以将 `fastai.core.USE_GPU` 设置为 `false`，以强制它不使用 GPU，这对调试很方便。

```py
rnn = Seq2SeqRNN(fr_vecd, fr_itos, dim_fr_vec, en_vecd, en_itos, 
                 dim_en_vec, nh, enlen_90)
learn = RNN_Learner(md, SingleModel(to_gpu(rnn)), opt_fn=opt_fn)
learn.crit = seq2seq_loss*3097 ['l’', "d'", 't_up', 'd’', "qu'"]
1285 ["'s", '’s', "n't", 'n’t', ':']*
```

然后我们需要一些东西告诉它如何处理学习率组，所以有一个叫做 `SingleModel` 的东西，你可以传递给它，它将整个东西视为一个单一的学习率组。这是将 PyTorch 模块转换为 fastai 模型的最简单方法。

我们可以直接调用 Learner 将其转换为一个学习器，但如果我们调用 RNN_Learner，它会添加 `save_encoder` 和 `load_encoder`，有时会很方便。在这种情况下，我们确实可以说 `Leaner`，但 `RNN_Learner` 也可以。

```py
learn.lr_find()
learn.sched.plot()
```

```py
lr=3e-3
learn.fit(lr, 1, cycle_len=12, use_clr=(20,10))*epoch      trn_loss   val_loss                              
    0      5.48978    5.462648  
    1      4.616437   4.770539                              
    2      4.345884   4.37726                               
    3      3.857125   4.136014                              
    4      3.612306   3.941867                              
    5      3.375064   3.839872                              
    6      3.383987   3.708972                              
    7      3.224772   3.664173                              
    8      3.238523   3.604765                              
    9      2.962041   3.587814                              
    10     2.96163    3.574888                              
    11     2.866477   3.581224**[3.5812237]* learn.save('initial')
learn.load('initial')
```

## 测试

记住，学习器的模型属性是一个标准的 PyTorch 模型，所以我们可以传递一些 `x`，我们可以从验证集中获取，或者您可以使用 `learn.predict_array` 或其他方法来获取一些预测。然后我们通过 `.max()[1]` 将这些预测转换为单词，以获取概率最高的单词的索引。然后我们可以通过一些示例，打印出法语、正确的英语和预测的英语，对于那些不是填充的内容。

```py
x,y = next(iter(val_dl))
probs = learn.model(V(x))
preds = to_np(probs.max(2)[1])

**for** i **in** range(180,190):
    print(' '.join([fr_itos[o] **for** o **in** x[:,i] **if** o != 1]))
    print(' '.join([en_itos[o] **for** o **in** y[:,i] **if** o != 1]))
    print(' '.join([en_itos[o] **for** o **in** preds[:,i] **if** o!=1]))
    print()*quels facteurs pourraient influer sur le choix de leur emplacement ? _eos_
what factors influencetheir location ? _eos_
what factors might might influence on the their ? ? _eos_

qu’ est -ce qui ne peut pas changer ? _eos_
what can not change ? _eos_
what not change change ? _eos_

que faites - vous ? _eos_
what do you do ? _eos_
what do you do ? _eos_

qui réglemente les pylônes d' antennes ? _eos_
who regulates antenna towers ? _eos_
who regulates the doors doors ? _eos_

où sont - ils situés ? _eos_
where are they located ? _eos_
where are the located ? _eos_

quelles sont leurs compétences ? _eos_
what are their qualifications ? _eos_
what are their skills ? _eos_

qui est victime de harcèlement sexuel ? _eos_
who experiences sexual harassment ? _eos_
who is victim sexual sexual ? ? _eos_

quelles sont les personnes qui visitent les communautés autochtones ? _eos_
who visits indigenous communities ? _eos_
who are people people aboriginal aboriginal ? _eos_

pourquoi ces trois points en particulier ? _eos_
why these specific three ? _eos_
why are these two different ? ? _eos_

pourquoi ou pourquoi pas ? _eos_
why or why not ? _eos_
why or why not _eos_*
```

令人惊讶的是，这种可能是最简单的从头开始编写的 PyTorch 模块，仅有五万个句子，有时在验证集上能够给出完全正确的答案。有时正确答案略有不同措辞，有时句子真的不通顺，甚至有太多的问号。所以我们在正确的轨道上。我们认为您会同意，即使是可能是最简单的 seq-to-seq 模型，经过很少的迭代训练，除了使用词嵌入之外没有任何预训练，效果也出奇的好。我们以后会改进这一点，但这里的信息是，即使您认为序列到序列模型比您认为的更简单，即使使用比您认为的更少的数据进行学习，也可能会出奇地有效，在某些情况下，这可能已经足够满足您的需求。

问题：规范标点符号（例如 `’` vs. `'`）会有帮助吗？这种特定情况的答案可能是肯定的——弯引号和直引号之间的区别实际上是语义上的。但是你必须非常小心，因为可能会发现使用漂亮的弯引号的人更喜欢使用更正式的语言，他们的写作方式也不同。因此，如果你要进行某种类似标点符号规范化的预处理，你应该绝对检查带有和不带有这种预处理的结果，因为几乎总是这种预处理会使事情变得更糟，即使你确信它不会。

**问题**：除了 dropout 和权重衰减，有哪些正则化这些 seq2seq 模型的方法？让我在这一周内考虑一下。我们一直依赖的 AWD-LSTM 有许多不同种类的 dropout，还有一种基于激活和变化的正则化。Jeremy 还没有看到有人将这么多工作投入到正则化序列到序列模型中，有一个巨大的机会让某人像 AWD-LSTM 一样对 seq-to-seq 进行正则化，这可能就像从 AWD-LSTM 中窃取所有想法并直接在 seq-to-seq 中使用它们一样容易尝试。最近几周 Stephen Merity 添加了一篇有趣的论文，他使用了一个想法，即获取所有这些不同的 AWD-LSTM 超参数并训练一堆不同的模型，然后使用随机森林找出最重要的特征，然后找出如何设置它们。你完全可以使用这种方法来找出对序列到序列正则化方法哪种是最好的，并优化它们，这将是令人惊讶的。但目前，我们不知道除了那篇关于常规语言模型的论文之外，是否还有其他关于序列到序列正则化的想法。

# 技巧

## **技巧#1：使用双向**

对于分类，Jeremy 建议使用的双向方法是获取所有的标记序列，旋转它们，训练一个新的语言模型，然后训练一个新的分类器。他还提到，如果你在名称中用`bwd`替换`fwd`，你将得到他为你创建的预训练的后向模型。获取一组预测，然后像普通集成一样对预测进行平均。这就是我们在这种分类中进行双向的方式。可能有一些方法可以端到端地完成，但 Jeremy 还没有完全弄清楚，而且它们还没有在 fastai 中。所以如果你弄清楚了，那是一个有趣的研究方向。但因为我们不是在处理大量文档，需要将其分成单独的部分，然后对它们进行汇总，所以在这种情况下我们可以很容易地进行双向。只需将`bidirectional=True`添加到我们的编码器中就可以了。人们倾向于不对解码器进行双向处理，部分原因是因为这被认为是作弊，但也许在某些情况下它可能有效，尽管在解码器中可能需要更多的集成方法，因为这不太明显。但对于编码器来说很简单——`bidirectional=True`，现在我们有了一个沿着相反方向的第二个 RNN。第二个 RNN 按相反顺序访问每个标记，因此当我们到达最终隐藏状态时，它是第一个（即最左边）标记。但隐藏状态的大小是相同的，因此最终的结果是我们得到了一个长度为 2 的额外轴的张量。根据你使用的库，通常这将与层数相结合，所以如果你有 2 层和双向——那个张量维度现在是长度 4。对于 PyTorch，取决于你查看的过程的哪一部分，你是否会得到每一层和/或每个双向位的单独结果。你必须查阅文档，它会告诉你适用于层数的输入输出张量大小以及是否有`bidirectional=True`。

在这种特殊情况下，你将看到必须进行的所有更改。例如，当我们添加了`bidirectional=True`时，`Linear`层现在需要隐藏数量乘以 2（即`nh*2`）来反映我们隐藏状态中有第二个方向的事实。在`initHidden`中现在是`self.nl*2`。

```py
**class** **Seq2SeqRNN_Bidir**(nn.Module):
    **def** __init__(self, vecs_enc, itos_enc, em_sz_enc, vecs_dec, 
                 itos_dec, em_sz_dec, nh, out_sl, nl=2):
        super().__init__()
        self.emb_enc = create_emb(vecs_enc, itos_enc, em_sz_enc)
        self.nl,self.nh,self.out_sl = nl,nh,out_sl
        self.gru_enc = nn.GRU(em_sz_enc, nh, num_layers=nl,
                              dropout=0.25, bidirectional=**True**)
        self.out_enc = nn.Linear(nh***2**, em_sz_dec, bias=**False**)
        self.drop_enc = nn.Dropout(0.05)
        self.emb_dec = create_emb(vecs_dec, itos_dec, em_sz_dec)
        self.gru_dec = nn.GRU(em_sz_dec, em_sz_dec, num_layers=nl,
                              dropout=0.1)
        self.emb_enc_drop = nn.Dropout(0.15)
        self.out_drop = nn.Dropout(0.35)
        self.out = nn.Linear(em_sz_dec, len(itos_dec))
        self.out.weight.data = self.emb_dec.weight.data

    **def** forward(self, inp):
        sl,bs = inp.size()
        h = self.initHidden(bs)
        emb = self.emb_enc_drop(self.emb_enc(inp))
        enc_out, h = self.gru_enc(emb, h)
        h = h.view(2,2,bs,-1).permute(0,2,1,3)
                .contiguous().view(2,bs,-1)
        h = self.out_enc(self.drop_enc(h)) dec_inp = V(torch.zeros(bs).long())
        res = []
        **for** i **in** range(self.out_sl):
            emb = self.emb_dec(dec_inp).unsqueeze(0)
            outp, h = self.gru_dec(emb, h)
            outp = self.out(self.out_drop(outp[0]))
            res.append(outp)
            dec_inp = V(outp.data.max(1)[1])
            **if** (dec_inp==1).all(): **break**
        **return** torch.stack(res)

    **def** initHidden(self, bs): 
        **return** V(torch.zeros(self.nl***2**, bs, self.nh))
```

为什么将解码器设置为双向被认为是作弊？这不仅仅是作弊，而且我们有这种循环进行，所以不仅仅是有两个张量那么简单。那么如何将这两个单独的循环转换为最终结果呢？在休息期间讨论过后，Jeremy 已经从“每个人都知道这不起作用”变成“也许它可能起作用”，但需要更多的思考。在这一周期间，他可能会意识到这是一个愚蠢的想法，但我们会考虑一下。

为什么需要为循环设置一个范围？因为当我们开始训练时，一切都是随机的，所以`if (dec_inp==1).all(): break`可能永远不会成立。后来，它最终几乎总是会中断，但基本上我们会永远进行下去。在设计架构时，非常重要的一点是要记住，当你开始时，模型对任何事情一无所知。所以你要确保如果它要做一些事情，至少它是模糊合理的。

我们使用单向获得了 3.58 的交叉熵损失。使用双向后，我们降到了 3.51，所以稍微有所改善。这不会真正减慢速度太多。双向意味着需要进行更多的顺序处理，但通常是一个很好的胜利。在 Google 翻译模型中，8 层中只有第一层是双向的，因为它允许它更多地并行进行，所以如果你创建了非常深的模型，你可能需要考虑哪些是双向的，否则我们会有性能问题。

```py
rnn = Seq2SeqRNN_Bidir(fr_vecd, fr_itos, dim_fr_vec, en_vecd,
                       en_itos, dim_en_vec, nh, enlen_90)
learn = RNN_Learner(md, SingleModel(to_gpu(rnn)), opt_fn=opt_fn)
learn.crit = seq2seq_losslearn.fit(lr, 1, cycle_len=12, use_clr=(20,10))*epoch      trn_loss   val_loss                              
    0      4.896942   4.761351  
    1      4.323335   4.260878                              
    2      3.962747   4.06161                               
    3      3.596254   3.940087                              
    4      3.432788   3.944787                              
    5      3.310895   3.686629                              
    6      3.454976   3.638168                              
    7      3.093827   3.588456                              
    8      3.257495   3.610536                              
    9      3.033345   3.540344                              
    10     2.967694   3.516766                              
    11     2.718945   3.513977**[3.5139771]*
```

## 技巧#2 教师强制

现在让我们谈谈教师强制。当模型开始学习时，它对一无所知。所以当模型开始学习时，它不会在第一步就吐出“Er”，它会吐出一些随机无意义的单词，因为它对德语、英语或语言的概念一无所知。它会将其作为输入馈送到下一个过程中，并且完全没有帮助。这意味着早期学习会非常困难，因为它将一个愚蠢的输入馈送到一个一无所知的模型中，但不知何故它会变得更好。所以最终它会到达那里，但肯定不像我们可以做的那样有帮助。那么，如果我们不是输入我刚才预测的东西，而是输入实际正确的单词，会怎样呢？我们在推理时无法这样做，因为根据定义，我们不知道正确的单词 - 必须将其翻译。我们不能要求正确的翻译来进行翻译。

设置的方式是我们有一个叫做`pr_force`的东西，它是强制的概率。如果某个随机数小于该概率，那么我们将用实际正确的东西替换我们的解码器输入。如果我们已经走得太远，如果它已经比目标序列长，我们就会停止，因为显然我们无法给出正确的东西。你可以看到 PyTorch 在这方面是多么美妙。去年课程的这个确切时刻，我们切换到 PyTorch 的关键原因是因为 Jeremy 尝试在 Keras 和 TensorFlow 中实现教师强制，结果比之前更疯狂。几周都没有进展，然后他在 Twitter 上看到 Andrej Karpathy 提到了一个叫做 PyTorch 的东西，很酷。他当天尝试了一下，第二天就有了教师强制。所有这些尝试调试的事情突然变得容易得多，这种动态的东西也变得容易得多。所以这是一个很好的例子，“嘿，我可以使用随机数和 if 语句”。

```py
**class** **Seq2SeqStepper**(Stepper):
    **def** step(self, xs, y, epoch):
        self.m.pr_force = (10-epoch)*0.1 **if** epoch<10 **else** 0
        xtra = []
        output = self.m(*xs, y)
        **if** isinstance(output,tuple): output,*xtra = output
        self.opt.zero_grad()
        loss = raw_loss = self.crit(output, y)
        **if** self.reg_fn: loss = self.reg_fn(output, xtra, raw_loss)
        loss.backward()
        **if** self.clip:   *# Gradient clipping*
            nn.utils.clip_grad_norm(trainable_params_(self.m), 
                                    self.clip)
        self.opt.step()
        **return** raw_loss.data[0]
```

这里是基本思想[[1:25:29](https://youtu.be/tY0n9OT5_nA?t=1h25m29s)]。在训练开始时，让`pr_force`非常高，以便几乎总是得到实际正确的前一个单词，因此它有一个有用的输入。然后随着我们训练的进一步，让`pr_force`逐渐减少，直到最后`pr_force`为零，它必须正确学习，这是可以的，因为现在它几乎总是输入合理的输入。

```py
**class** **Seq2SeqRNN_TeacherForcing**(nn.Module):
    **def** __init__(self, vecs_enc, itos_enc, em_sz_enc, vecs_dec,
                 itos_dec, em_sz_dec, nh, out_sl, nl=2):
        super().__init__()
        self.emb_enc = create_emb(vecs_enc, itos_enc, em_sz_enc)
        self.nl,self.nh,self.out_sl = nl,nh,out_sl
        self.gru_enc = nn.GRU(em_sz_enc, nh, num_layers=nl, 
                              dropout=0.25)
        self.out_enc = nn.Linear(nh, em_sz_dec, bias=**False**)
        self.emb_dec = create_emb(vecs_dec, itos_dec, em_sz_dec)
        self.gru_dec = nn.GRU(em_sz_dec, em_sz_dec, num_layers=nl, 
                              dropout=0.1)
        self.emb_enc_drop = nn.Dropout(0.15)
        self.out_drop = nn.Dropout(0.35)
        self.out = nn.Linear(em_sz_dec, len(itos_dec))
        self.out.weight.data = self.emb_dec.weight.data
        self.pr_force = 1.

    **def** forward(self, inp, y=**None**):
        sl,bs = inp.size()
        h = self.initHidden(bs)
        emb = self.emb_enc_drop(self.emb_enc(inp))
        enc_out, h = self.gru_enc(emb, h)
        h = self.out_enc(h) dec_inp = V(torch.zeros(bs).long())
        res = []
        **for** i **in** range(self.out_sl):
            emb = self.emb_dec(dec_inp).unsqueeze(0)
            outp, h = self.gru_dec(emb, h)
            outp = self.out(self.out_drop(outp[0]))
            res.append(outp)
            dec_inp = V(outp.data.max(1)[1])
            **if** (dec_inp==1).all(): **break**
            **if** (y **is** **not** **None**) **and** (random.random()<self.pr_force):
                **if** i>=len(y): **break**
                dec_inp = y[i]
        **return** torch.stack(res)

    **def** initHidden(self, bs): 
        **return** V(torch.zeros(self.nl, bs, self.nh))
```

`pr_force`: “probability of forcing”. High in the beginning zero by the end.

现在让我们写一些东西，使得在训练循环中逐渐减少`pr_force`[[1:26:01](https://youtu.be/tY0n9OT5_nA?t=1h26m1s)]。我们如何做到这一点？一种方法是编写我们自己的训练循环，但我们不要这样做，因为我们已经有一个训练循环，它有进度条，使用指数加权平均值来平滑损失，跟踪指标，并做了一堆事情。它们还跟踪在 epoch 开始时调用 RNN 的重置，以确保隐藏状态设置为零。我们发现的趋势是，当我们开始编写一些新东西并需要替换代码的某些部分时，我们会添加一些小钩子，以便我们可以使用该钩子使事情变得更容易。在这种特殊情况下，Jeremy 一直在使用的一个钩子是称为 stepper 的钩子。如果你查看源代码，model.py 是我们的 fit 函数所在的地方，这是最低级的东西，不需要学习者或任何其他东西，只需要一个标准的 PyTorch 模型和一个模型数据对象。你只需要知道多少个 epochs，一个标准的 PyTorch 优化器和一个标准的 PyTorch 损失函数。我们在课堂上几乎从未使用过，我们通常调用`learn.fit`，但`learn.fit`调用这个。

我们有时查看源代码[[1:27:49](https://youtu.be/tY0n9OT5_nA?t=1h27m49s)]。我们看到它如何通过每个 epoch 循环，然后循环遍历批处理中的每个内容并调用`stepper.step`。`stepper.step`是负责的事情：

+   调用模型

+   获取损失

+   找到损失函数

+   调用优化器

所以默认情况下，`stepper.step`使用一个称为`Stepper`的特定类，基本上调用模型，将梯度置零，调用损失函数，调用`backward`，如果需要进行梯度裁剪，然后调用优化器。这些是我们在“从头开始的 PyTorch”中看到的基本步骤。好处是，我们可以用其他东西替换它，而不是替换训练循环。如果你继承自`Stepper`，然后编写你自己版本的`step`，你可以只需复制并粘贴 step 的内容并添加任何你喜欢的内容。或者如果这是你要在之前或之后做的事情，你甚至可以调用`super.step`。在这种情况下，Jeremy 相当怀疑他不必要地复杂[[1:29:12](https://youtu.be/tY0n9OT5_nA?t=1h29m12s)] - 他可能本来可以做一些像这样的事情：

```py
**class** **Seq2SeqStepper**(Stepper):
    **def** step(self, xs, y, epoch):
        self.m.pr_force = (10-epoch)*0.1 **if** epoch<10 **else** 0
        **return** super.step(xs, y, epoch)
```

但正如他所说的，当他在原型设计时，他并没有仔细考虑如何最小化他的代码 - 他复制并粘贴了`step`的内容，并在顶部添加了一行，用于将模块中的`pr_force`逐渐线性减少前 10 个 epochs，10 个 epochs 后，它为零。所以总体上是一个 hack，但足够好用来尝试一下。好处是除了添加这三行之外，其他一切都是一样的：

```py
 **if** (y **is** **not** **None**) **and** (random.random()<self.pr_force):
                **if** i>=len(y): **break**
                dec_inp = y[i]
```

唯一需要做的不同之处是当我们调用`fit`时，我们传入我们定制的 stepper 类。

```py
rnn = Seq2SeqRNN_TeacherForcing(fr_vecd, fr_itos, dim_fr_vec, 
                         en_vecd, en_itos, dim_en_vec, nh, enlen_90)
learn = RNN_Learner(md, SingleModel(to_gpu(rnn)), opt_fn=opt_fn)
learn.crit = seq2seq_losslearn.fit(lr, 1, cycle_len=12, use_clr=(20,10), 
          stepper=Seq2SeqStepper)*epoch      trn_loss   val_loss                              
    0      4.460622   12.661013 
    1      3.468132   7.138729                              
    2      3.235244   6.202878                              
    3      3.101616   5.454283                              
    4      3.135989   4.823736                              
    5      2.980696   4.933402                              
    6      2.91562    4.287475                              
    7      3.032661   3.975346                              
    8      3.103834   3.790773                              
    9      3.121457   3.578682                              
    10     2.917534   3.532427                              
    11     3.326946   3.490643**[3.490643]*
```

现在我们的损失降至 3.49。我们需要确保至少进行 10 个 epochs，因为在那之前，通过使用强制教师，这是作弊的。

## Trick #3 注意力模型[[1:31:00](https://youtu.be/tY0n9OT5_nA?t=1h31m)]

下一个技巧是一个更大、更酷的技巧。它被称为“注意力”。注意力的基本思想是这样的——期望将整个句子总结为这个单一的隐藏向量是要求太多了。它必须知道说了什么，怎么说的，以及创建德语句子所需的一切。注意力的想法基本上是我们可能要求太多了。特别是因为我们可以使用这种形式的模型（下面），在这种模型中我们不仅输出循环的每一步，而不仅仅是在最后有一个隐藏状态，而是在每个单词之后都有一个隐藏状态。为什么不尝试利用这些信息呢？它已经存在，但到目前为止我们只是把它丢掉了。不仅如此，而且双向的，我们在每一步都有两个状态向量，我们可以利用。我们怎么做呢？

让我们假设我们现在正在翻译一个词“liebte”[[1:32:34](https://youtu.be/tY0n9OT5_nA?t=1h32m34s)]。我们想要之前的 5 个隐藏状态中的哪一个？显然我们想要“love”，因为这是这个词。那么“zu”呢？我们可能需要“eat”、“to”和“loved”来确保我们已经得到了正确的时态，并知道我实际上需要动词的这部分等等。因此，根据我们正在翻译的部分，我们可能需要这些不同隐藏状态的一个或多个部分。实际上，我们可能需要对它们进行加权。换句话说，对于这五个隐藏状态，我们想要一个加权平均值[[1:33:47](https://youtu.be/tY0n9OT5_nA?t=1h33m47s)]。我们希望它根据某种可以确定哪些句子部分现在最重要的东西进行加权。我们如何找出哪些句子部分现在很重要？我们创建一个神经网络，训练神经网络来找出。我们什么时候训练这个神经网络？端到端。所以现在让我们训练两个神经网络[[1:34:18](https://youtu.be/tY0n9OT5_nA?t=1h34m18s)]。嗯，我们已经有了一堆——RNN 编码器，RNN 解码器，几个线性层，那就再加一个神经网络吧。这个神经网络将为每一个这些状态输出一个权重，我们将在每一步进行加权平均，这只是我们同时学习的另一组参数。这就是所谓的“注意力”。

这个想法是一旦学会了注意力，每个单词都会进行加权平均，你可以在 Chris Olah 和 Shan Carter 的这个精彩演示中看到[[1:34:50](https://youtu.be/tY0n9OT5_nA?t=1h34m50s)]。查看这篇[distill.pub 文章](https://distill.pub/2016/augmented-rnns/)——这些都是交互式图表，向你展示了注意力是如何工作的，以及在训练翻译模型中实际的注意力是什么样子。

[](https://distill.pub/2016/augmented-rnns/)

让我们尝试实现注意力[[1:35:47](https://youtu.be/tY0n9OT5_nA?t=1h35m47s)]:

```py
**def** rand_t(*sz): **return** torch.randn(sz)/math.sqrt(sz[0])
**def** rand_p(*sz): **return** nn.Parameter(rand_t(*sz))**class** **Seq2SeqAttnRNN**(nn.Module):
    **def** __init__(self, vecs_enc, itos_enc, em_sz_enc, vecs_dec, 
                 itos_dec, em_sz_dec, nh, out_sl, nl=2):
        super().__init__()
        self.emb_enc = create_emb(vecs_enc, itos_enc, em_sz_enc)
        self.nl,self.nh,self.out_sl = nl,nh,out_sl
        self.gru_enc = nn.GRU(em_sz_enc, nh, num_layers=nl, 
                              dropout=0.25)
        self.out_enc = nn.Linear(nh, em_sz_dec, bias=**False**)
        self.emb_dec = create_emb(vecs_dec, itos_dec, em_sz_dec)
        self.gru_dec = nn.GRU(em_sz_dec, em_sz_dec, num_layers=nl, 
                              dropout=0.1)
        self.emb_enc_drop = nn.Dropout(0.15)
        self.out_drop = nn.Dropout(0.35)
        self.out = nn.Linear(em_sz_dec*2, len(itos_dec))
        self.out.weight.data = self.emb_dec.weight.data self.W1 = rand_p(nh, em_sz_dec)
        self.l2 = nn.Linear(em_sz_dec, em_sz_dec)
        self.l3 = nn.Linear(em_sz_dec+nh, em_sz_dec)
        self.V = rand_p(em_sz_dec) **def** forward(self, inp, y=**None**, ret_attn=**False**):
        sl,bs = inp.size()
        h = self.initHidden(bs)
        emb = self.emb_enc_drop(self.emb_enc(inp))
        enc_out, h = self.gru_enc(emb, h)
        h = self.out_enc(h) dec_inp = V(torch.zeros(bs).long())
        res,attns = [],[]
        w1e = enc_out @ self.W1
        **for** i **in** range(self.out_sl):
            w2h = self.l2(h[-1])
            u = F.tanh(w1e + w2h)
            a = F.softmax(u @ self.V, 0)
            attns.append(a)
            Xa = (a.unsqueeze(2) * enc_out).sum(0)
            emb = self.emb_dec(dec_inp)
            wgt_enc = self.l3(torch.cat([emb, Xa], 1))

            outp, h = self.gru_dec(wgt_enc.unsqueeze(0), h)
            outp = self.out(self.out_drop(outp[0]))
            res.append(outp)
            dec_inp = V(outp.data.max(1)[1])
            **if** (dec_inp==1).all(): **break**
            **if** (y **is** **not** **None**) **and** (random.random()<self.pr_force):
                **if** i>=len(y): **break**
                dec_inp = y[i] res = torch.stack(res)
        **if** ret_attn: res = res,torch.stack(attns)
        **return** res **def** initHidden(self, bs): 
        **return** V(torch.zeros(self.nl, bs, self.nh))
```

有了注意力，大部分代码都是相同的。唯一的主要区别是这一行：`Xa = (a.unsqueeze(2) * enc_out).sum(0)`。我们将进行加权平均，我们将如何进行加权平均是我们创建一个小型神经网络，我们将在这里看到：

```py
w2h = self.l2(h[-1])
u = F.tanh(w1e + w2h)
a = F.softmax(u @ self.V, 0)
```

我们使用 softmax，因为 softmax 的好处是我们希望确保我们使用的所有权重加起来等于 1，而且我们也希望其中一个权重可能比其他权重更高[[1:36:38](https://youtu.be/tY0n9OT5_nA?t=1h36m38s)]。Softmax 给了我们这样的保证，它们加起来等于 1，因为它里面有`e^`，它倾向于鼓励其中一个权重比其他权重更高。

让我们看看这是如何工作的[[1:37:09](https://youtu.be/tY0n9OT5_nA?t=1h37m9s)]。我们将取最后一层的隐藏状态，然后将其放入一个线性层中。然后我们将其放入一个非线性激活函数，然后进行矩阵相乘。所以如果你考虑一下——一个线性层，非线性激活函数，矩阵相乘——这就是一个神经网络。这是一个具有一个隐藏层的神经网络。将其放入 softmax，然后我们可以使用它来加权我们的编码器输出。现在，我们不再只是取最后一个编码器输出，而是有了所有编码器输出的张量，我们只需用我们创建的这个神经网络来加权。

在 Python 中，`A @ B`是矩阵乘积，`A * B`是逐元素乘积

## 论文[[1:38:18](https://youtu.be/tY0n9OT5_nA?t=1h38m18s)]

+   [通过联合学习对齐和翻译进行神经机器翻译](https://arxiv.org/abs/1409.0473)——这是一篇令人惊叹的论文，最初介绍了注意力的概念，以及一些真正改变了人们在这一领域工作方式的关键事项。他们说，注意力领域不仅用于文本，还用于从图片中读取文本或在计算机视觉中执行各种任务。

+   [作为外语的语法](https://arxiv.org/abs/1412.7449)——Geoffrey Hinton 参与的第二篇论文，使用了 RNN 与注意力的想法，试图用自动标记每个单词的 RNN 替换基于规则的语法。结果表明，它比任何基于规则的系统做得更好，这在今天看来是显而易见的，但在当时被认为是非常令人惊讶的。它们是关于注意力如何工作的摘要，非常清晰简洁。

**问题**：你能再解释一下注意力吗？[[1:39:46](https://youtu.be/tY0n9OT5_nA?t=1h39m46s)] 当然！让我们回头看看我们最初的编码器。

RNN 输出两个东西：它在每个时间步骤之后输出一个状态列表（`enc_out`），并且还告诉您在最后一个时间步骤的状态（`h`），我们使用最后一个时间步骤的状态来创建我们的解码器的输入状态，这是下面的一个向量`s`：

但我们知道它在每个时间步骤都创建一个向量（橙色箭头），那么使用它们所有不是更好吗？但使用哪一个或哪些对于翻译我们正在翻译的单词最相关呢？所以能否按照当前适当的权重取每个时间步骤的隐藏状态的加权平均值会更好。例如，“liebte”肯定是时间步骤＃2，因为那是我正在翻译的单词。那么我们如何得到一个适合当前训练的单词的权重列表呢？答案是通过训练一个神经网络来找出权重列表。所以每当我们想要弄清楚如何训练一个小型神经网络来执行任何任务时，通常最简单的方法就是将其包含在你的模块中，并与其他所有内容一起训练。最简单的神经网络是包含两层和一个非线性激活函数的东西，所以`self.l2`是一个线性层。

实际上，我们甚至可以只是随机选择一个矩阵，如果我们不关心偏差[[1:42:18](https://youtu.be/tY0n9OT5_nA?t=1h42m18s)]。`self.W1`是一个随机张量，包装在一个`Parameter`中。

`Parameter`：记住，`Parameter`与 PyTorch 的`Variable`是相同的，但它只是告诉 PyTorch“请学习这些权重”。[[1:42:35](https://youtu.be/tY0n9OT5_nA?t=1h42m35s)]

因此，当我们开始我们的解码器时，让我们取解码器当前的隐藏状态，将其放入一个线性层（`self.l2`），因为我们用来决定接下来应该关注哪些单词的信息——我们唯一可以依赖的信息就是解码器当前的隐藏状态。所以让我们抓住它：

+   将其放入线性层（`self.l2`）

+   将其通过非线性激活函数（`F.tanh`）处理

+   通过一个非线性层（`u @ self.V`中没有偏差，所以只是矩阵相乘）

+   通过 softmax

就是这样——一个小型神经网络。它什么也不做。它只是一个神经网络，没有神经网络做任何事情，它们只是具有随机权重的线性层和非线性激活。但是如果我们给它一个任务，它就开始做一些事情。在这种情况下，我们给它的任务是不要只取最终状态，而是现在让我们使用所有编码器状态，并且让我们取出所有这些状态，并将它们乘以那个小型神经网络的输出。因此，考虑到这个小型神经网络中的东西是可学习的权重，希望它学会对这些编码器隐藏状态进行有用的加权。神经网络所做的一切就是我们给它一些随机权重作为起点和一个任务，并希望它学会完成这个任务。结果表明，它确实做到了。

这里的其他一切与以前完全相同。我们有教师强制，它不是双向的，所以我们可以看看情况如何。

```py
rnn = Seq2SeqAttnRNN(fr_vecd, fr_itos, dim_fr_vec, en_vecd, en_itos, dim_en_vec, nh, enlen_90)
learn = RNN_Learner(md, SingleModel(to_gpu(rnn)), opt_fn=opt_fn)
learn.crit = seq2seq_loss
lr=2e-3learn.fit(lr, 1, cycle_len=15, use_clr=(20,10), 
          stepper=Seq2SeqStepper)*epoch      trn_loss   val_loss                              
    0      3.882168   11.125291 
    1      3.599992   6.667136                              
    2      3.236066   5.552943                              
    3      3.050283   4.919096                              
    4      2.99024    4.500383                              
    5      3.07999    4.000295                              
    6      2.891087   4.024115                              
    7      2.854725   3.673913                              
    8      2.979285   3.590668                              
    9      3.109851   3.459867                              
    10     2.92878    3.517598                              
    11     2.778292   3.390253                              
    12     2.795427   3.388423                              
    13     2.809757   3.353334                              
    14     2.6723     3.368584*[3.3685837]
```

教师强制为 3.49，现在几乎完全相同的东西，但我们有这个小型神经网络来找出给我们输入的权重，我们降到了 3.37。记住，这些损失是对数，所以`e³.37`是一个相当显著的变化。

```py
learn.save('attn')
```

## 测试[[1:45:37](https://youtu.be/tY0n9OT5_nA?t=1h45m37s)]

```py
x,y = next(iter(val_dl))
probs,attns = learn.model(V(x),ret_attn=**True**)
preds = to_np(probs.max(2)[1])**for** i **in** range(180,190):
    print(' '.join([fr_itos[o] **for** o **in** x[:,i] **if** o != 1]))
    print(' '.join([en_itos[o] **for** o **in** y[:,i] **if** o != 1]))
    print(' '.join([en_itos[o] **for** o **in** preds[:,i] **if** o!=1]))
    print()*quels facteurs pourraient influer sur le choix de leur emplacement ? _eos_
what factors influencetheir location ? _eos_
what factors might influence the their their their ? _eos_**qu’ est -ce qui ne peut pas changer ? _eos_
what can not change ? _eos_
what can not change change ? _eos_**que faites - vous ? _eos_
what do you do ? _eos_
what do you do ? _eos_**qui réglemente les pylônes d' antennes ? _eos_
who regulates antenna towers ? _eos_
who regulates the lights ? ? _eos_**où sont - ils situés ? _eos_
where are they located ? _eos_
where are they located ? _eos_**quelles sont leurs compétences ? _eos_
what are their qualifications ? _eos_
what are their skills ? _eos_**qui est victime de harcèlement sexuel ? _eos_
who experiences sexual harassment ? _eos_
who is victim sexual sexual ? _eos_**quelles sont les personnes qui visitent les communautés autochtones ? _eos_
who visits indigenous communities ? _eos_
who is people people aboriginal people ? _eos_**pourquoi ces trois points en particulier ? _eos_
why these specific three ? _eos_
why are these three three ? ? _eos_**pourquoi ou pourquoi pas ? _eos_
why or why not ? _eos_
why or why not ? _eos_*
```

还不错。仍然不完美，但相当多的结果是正确的，考虑到我们要求它学习两种不同语言之间的语言概念，以及如何在两种语言之间进行翻译，以及语法和词汇，我们只有 50,000 个句子，很多词只出现一次，我会说这实际上是非常惊人的。

**问题：**为什么我们在注意力小网络中使用 tanh 而不是 ReLU？[[1:46:23](https://youtu.be/tY0n9OT5_nA?t=1h46m23s)]我不太记得——我很久没有看过了。你完全可以尝试使用值并看看效果如何。显然，tanh 的关键区别在于它可以在每个方向上移动，并且在顶部和底部都受限。我知道在 RNNs、LSTMs 和 GRUs 内部的门中，tanh 通常效果更好，但是我已经大约一年没有看过这个具体问题了，所以我会在这周看一下。简短的答案是你应该尝试不同的激活函数，看看是否可以得到更好的结果。

> 来自第 7 课[[44:06](https://youtu.be/H3g26EVADgY?t=44m6s)]：正如我们上周所看到的，tanh 强制值在-1 和 1 之间。由于我们一遍又一遍地乘以这个权重矩阵，我们担心 relu（因为它是无界的）可能会有更多的梯度爆炸问题。话虽如此，你可以指定 RNNCell 使用不同的非线性函数，其默认值为 tanh，并要求它使用 relu。

## 可视化[[1:47:12](https://youtu.be/tY0n9OT5_nA?t=1h47m12s)]

我们还可以通过将`forward`函数添加返回注意力参数来从模型中提取注意力。你可以在`forward`函数参数中放任何你想要的东西。所以我们添加了一个返回注意力参数，默认为 false，因为显然训练循环不知道这一点，但然后我们在这里添加了一些东西，如果返回注意力，那么也将注意力添加进去（`if ret_attn: res = res,torch.stack(attns)`）。注意力就是值`a`，只需将其放入列表中（`attns.append(a)`）。现在我们可以调用带有返回注意力等于 true 的模型，并获得概率和注意力[[1:47:53](https://youtu.be/tY0n9OT5_nA?t=1h47m53s)]：

```py
probs,attns = learn.model(V(x),ret_attn=**True**)
```

现在我们可以在每个时间步绘制注意力的图片。

```py
attn = to_np(attns[...,180])fig, axes = plt.subplots(3, 3, figsize=(15, 10))
**for** i,ax **in** enumerate(axes.flat):
    ax.plot(attn[i])
```

当你是 Chris Olah 和 Shan Carter 时，你做出的东西看起来像☟，当你是 Jeremy Howard 时，完全相同的信息看起来像☝︎。你可以看到在每个不同的时间步，我们有不同的注意力。

当你尝试构建这样的东西时，非常重要的一点是，你不知道它是否工作正常，因为如果它不工作（通常情况下，Jeremy 的前 12 次尝试都失败了），它们失败的意义在于它并没有真正学到任何有用的东西。因此，它对每件事都给予了同等的关注，它并没有变得更糟——只是并没有变得更好。直到你真正找到一种方法来以一种你事先知道它应该是什么样子的方式来可视化这个东西，你才真正知道它是否有效。因此，非常重要的一点是，你要尝试找到一种方法来检查你的中间步骤和输出。

**问题**：注意力神经网络的损失函数是什么？没有，注意力神经网络没有损失函数。它是端到端训练的。它只是坐在我们的解码器循环中。解码器循环的损失函数是相同的损失函数，因为结果包含的东西完全相同——单词的概率。为什么这个小型神经网络在学习？因为为了使输出变得更好，如果它使加权平均的权重变得更好，那将是很好的。因此，创建我们的输出的一部分是请尽量找到一组好的权重，如果它不能找到一组好的权重，那么损失函数就不会从那一部分改善。因此，端到端学习意味着你将一切都放入一个损失函数中，所有不同参数的梯度都指向一个方向，即“嘿，你知道如果你在那里放更多的权重，那会更好。”多亏了链式法则的魔力，它知道要在那里放更多的权重，稍微改变矩阵乘法中的参数等。这就是端到端学习的魔力。这是一个非常容易理解的问题，但你必须意识到这段代码中没有任何特定的东西表明这些特定的部分是单独的小型神经网络，就像 GRU 不是一个单独的小型神经网络，或者线性层不是一个单独的小型函数一样。所有这些最终都被推送到一个输出中，这个输出是一堆概率，最终进入一个返回单个数字的损失函数，这个数字表示这是一个好的翻译还是不是一个好的翻译。多亏了链式法则的魔力，我们然后向所有参数反向传播一点更新，使它们变得更好一点。这是一个很大、很奇怪、很反直觉的想法，如果它有点令人费解，那完全没关系。这是一个让我们回到第一课“我们是如何让它找到狗和猫的？”的地方——我们没有。我们所做的只是说“这是我们的数据，这是我们的架构，这是我们的损失函数。请反向传播到权重，使它们变得更好，当你让它们变得更好一段时间后，它将开始从狗中找到猫。”在这种情况下（即翻译），我们没有使用别人的卷积网络架构。我们说“这是一个我们希望在这个问题上特别擅长的自定义架构。”即使没有这个自定义架构，也还可以。但我们制作的方式更有意义，或者我们认为它应该做得更好。但在任何时候，我们都没有做任何不同的事情，只是说“这是数据，这是架构，这是损失函数——请找到参数”它做到了，因为这就是神经网络所做的事情。

所以这就是序列到序列学习。

+   如果你想将图像编码到某种 CNN 骨干中，然后将其传递到一个类似带有注意力的 RNN 的解码器中，然后将你的 y 值设为每个图像的实际正确字幕，你最终会得到一个图像字幕生成器。

+   如果你用视频和字幕做同样的事情，你最终会得到一个视频字幕生成器。

+   如果你用 3D CT 扫描和放射学报告做同样的事情，你最终会得到一个放射学报告生成器。

+   如果你用 Github 问题和人们选择的摘要做同样的事情，你会得到一个 Github 问题摘要生成器。

> Seq-to-seq 是神奇的，但它们起作用。我觉得人们还没有开始深入研究如何在自己的领域中使用 seq-to-seq 模型。作为一个不太用 Github 的人，我从来没有想到“从某个问题开始并自动生成摘要会很酷”。但现在，当然，下次我进入 Github 时，我想看到一个为我写的摘要。我不想写自己的提交消息。当我完成对很多行添加注释后，为什么我要自己写代码审查的摘要呢 — 它也应该为我做这件事。现在我在想 Github 太落后了，它本来可以做这些事情。那么在你的行业中有什么事情呢？你可以从一个序列开始并生成一些东西。我无法想象。再次强调，这是一个相当新的领域，用于它的工具并不容易使用 — 它们甚至还没有内置到 fastai 中。希望很快会有。我认为没有人知道机会在哪里。

# Devise [[1:55:23](https://youtu.be/tY0n9OT5_nA?t=1h55m23s)]

[笔记本](https://github.com/fastai/fastai/blob/master/courses/dl2/devise.ipynb) / [论文](http://papers.nips.cc/paper/5204-devise-a-deep-visual-semantic-embedding-model.pdf)

我们将要做一些事情，第一次将我们专注的两个小世界——文本和图像[[1:55:49](https://youtu.be/tY0n9OT5_nA?t=1h55m49s)]结合起来。这个想法是由一位名叫 Andrea Frome 的杰出深度学习从业者和研究人员提出的。当时 Andrea 在谷歌工作，她疯狂的想法是单词可以有一个分布式表示，一个空间，特别是在那个时候只是单词向量。图像也可以在一个空间中表示。最后，如果我们有一个全连接层，它们最终会成为一个向量表示。我们能够合并这两者吗？我们能否以某种方式鼓励图像最终得到的向量空间与单词所在的向量空间相同？如果我们能做到这一点，那意味着什么？我们可以用它做什么？那么我们可以用它做什么，涵盖了诸如“如果我错了怎么办，如果我预测这张图片是一只猎犬，而我预测是大型喷气机，Yannet 的模型预测是柯基。正常的损失函数表示 Yannet 和 Jeremy 的模型一样好（即它们都是错误的）。但如果我们能以某种方式说，你知道柯基更接近猎犬而不是大型喷气机。所以 Yannet 的模型比 Jeremy 的更好。我们应该能够做到这一点，因为在单词向量空间中，猎犬和柯基是非常接近的，但大型喷气机不是那么接近。所以这将给我们一个很好的情况，希望我们的推理如果错误的话会以更合理的方式出错。这也将使我们能够搜索不在 ImageNet Synset ID（即 ImageNet 中的一个类别）中的事物。为什么我们必须训练一个全新的模型来找到狗和猫，当我们已经有找到柯基和虎斑猫的东西。为什么我们不能只是说找到狗？如果我们在单词向量空间中训练过它，我们完全可以，因为它们是单词向量，我们可以找到具有正确图像向量的东西等等。我们将在一会儿看一些我们可以用它做的很酷的事情，但首先让我们训练一个模型，这个模型不是学习一个类别（独热编码 ID），其中每个类别与其他每个类别的距离都是相等的，而是训练一个模型，我们正在寻找一个依赖变量，这是一个单词向量。那么什么单词向量？显然是你想要的单词的单词向量。所以如果是柯基，让我们训练它创建一个柯基单词向量，如果是大型喷气机，让我们训练它与一个依赖变量说这是大型喷气机的单词向量。

```py
**from** **fastai.conv_learner** **import** *
torch.backends.cudnn.benchmark=**True**

**import** **fastText** **as** **ft**PATH = Path('data/imagenet/')
TMP_PATH = PATH/'tmp'
TRANS_PATH = Path('data/translate/')
PATH_TRN = PATH/'train'
```

这实在太容易了。让我们再次获取 fast text 单词向量，加载它们进来（这次我们只需要英语）。

```py
ft_vecs = ft.load_model(str((TRANS_PATH/'wiki.en.bin')))np.corrcoef(ft_vecs.get_word_vector('jeremy'), 
            ft_vecs.get_word_vector('Jeremy'))*array([[1\.     , 0.60866],
       [0.60866, 1\.     ]])*
```

例如，“jeremy”和“Jeremy”的相关系数为 0.6。

```py
np.corrcoef(ft_vecs.get_word_vector('banana'), 
            ft_vecs.get_word_vector('Jeremy'))*array([[1\.     , 0.14482],
       [0.14482, 1\.     ]])*
```

Jeremy 一点也不喜欢香蕉，“香蕉”和“Jeremy”相关系数为 0.14。所以你期望相关的词是相关的，而应该尽可能远离彼此的词，不幸的是，它们仍然略微相关，但不那么明显。

## 将 ImageNet 类别映射到单词向量

现在让我们获取所有 ImageNet 类别，因为我们实际上想知道哪一个是柯基，哪一个是大型喷气机。

```py
ft_words = ft_vecs.get_words(include_freq=**True**)
ft_word_dict = {k:v **for** k,v **in** zip(*ft_words)}
ft_words = sorted(ft_word_dict.keys(), key=**lambda** x: ft_word_dict[x])len(ft_words)*2519370***from** **fastai.io** **import** get_data
```

我们在 files.fast.ai 上有一个所有这些的列表，我们可以获取它们。

```py
CLASSES_FN = 'imagenet_class_index.json'
get_data(f'http://files.fast.ai/models/{CLASSES_FN}', 
         TMP_PATH/CLASSES_FN)
```

让我们还获取 Jeremy 提供的所有英语名词的列表：

```py
WORDS_FN = 'classids.txt'
get_data(f'http://files.fast.ai/data/{WORDS_FN}', PATH/WORDS_FN)
```

所以我们有每个千个 ImageNet 类别的名称，以及根据 WordNet 列出的所有英语名词，这是一个用于表示哪些词是什么的流行工具。我们现在可以加载 ImageNet 类别列表，将其转换为字典，因此`classids_1k`包含了比赛数据集中的 1000 个图像的类别 ID。

```py
class_dict = json.load((TMP_PATH/CLASSES_FN).open())
classids_1k = dict(class_dict.values())
nclass = len(class_dict); nclass*1000*
```

这里有一个例子。一个“tench”显然是一种鱼。

```py
class_dict['0']*['n01440764', 'tench']*
```

让我们为所有这些 WordNet 名词做同样的事情。结果发现 ImageNet 正在使用 WordNet 类名，这样在两者之间进行映射就变得简单了。

```py
classid_lines = (PATH/WORDS_FN).open().readlines()
classid_lines[:5]*['n00001740 entity\n',
 'n00001930 physical_entity\n',
 'n00002137 abstraction\n',
 'n00002452 thing\n',
 'n00002684 object\n']*classids = dict(l.strip().split() **for** l **in** classid_lines)
len(classids),len(classids_1k)*(82115, 1000)*
```

这是我们的两个世界 — 我们有 ImageNet 的一千个和 WordNet 中的 82,000 个。

```py
lc_vec_d = {w.lower(): ft_vecs.get_word_vector(w) **for** w 
                           **in** ft_words[-1000000:]}
```

我们想要将这两者联系起来，这只是简单地创建一些字典来基于 Synset ID 或 WordNet ID 进行映射。

```py
syn_wv = [(k, lc_vec_d[v.lower()]) **for** k,v **in** classids.items()
          **if** v.lower() **in** lc_vec_d]
syn_wv_1k = [(k, lc_vec_d[v.lower()]) **for** k,v **in** classids_1k.items()
          **if** v.lower() **in** lc_vec_d]
syn2wv = dict(syn_wv)
len(syn2wv)*49469*
```

现在我们需要做的是获取 WordNet 中的 82,000 个名词，并尝试在快速文本中查找它们。我们已经在快速文本中查找到了 49,469 个名词。我们现在有一个字典，从 synset ID（即 WordNet 称之为的 ID）到单词向量。我们还为 1k 个 ImageNet 类别做了同样的事情。

```py
pickle.dump(syn2wv, (TMP_PATH/'syn2wv.pkl').open('wb'))
pickle.dump(syn_wv_1k, (TMP_PATH/'syn_wv_1k.pkl').open('wb'))syn2wv = pickle.load((TMP_PATH/'syn2wv.pkl').open('rb'))
syn_wv_1k = pickle.load((TMP_PATH/'syn_wv_1k.pkl').open('rb'))
```

现在我们获取了所有的 ImageNet，你现在可以从 Kaggle 下载。如果你看一下 Kaggle 的 ImageNet 本地化比赛，其中包含了所有的 ImageNet 分类。

```py
images = []
img_vecs = []**for** d **in** (PATH/'train').iterdir():
    **if** d.name **not** **in** syn2wv: **continue**
    vec = syn2wv[d.name]
    **for** f **in** d.iterdir():
        images.append(str(f.relative_to(PATH)))
        img_vecs.append(vec)n_val=0
**for** d **in** (PATH/'valid').iterdir():
    **if** d.name **not** **in** syn2wv: **continue**
    vec = syn2wv[d.name]
    **for** f **in** d.iterdir():
        images.append(str(f.relative_to(PATH)))
        img_vecs.append(vec)
        n_val += 1n_val*28650*
```

其中有 28,650 个项目的验证集。对于 ImageNet 中的每个图像，我们可以使用 synset 到单词向量（`syn2wv`）获取其快速文本词向量，并将其放入图像向量数组（`img_vecs`），将所有这些堆叠到一个矩阵中并保存下来。

```py
img_vecs = np.stack(img_vecs)
img_vecs.shape
```

现在我们为每个 ImageNet 图像都有一个与之相关联的快速文本词向量。通过查找 synset ID → WordNet → 快速文本 → 单词向量。

```py
pickle.dump(images, (TMP_PATH/'images.pkl').open('wb'))
pickle.dump(img_vecs, (TMP_PATH/'img_vecs.pkl').open('wb'))images = pickle.load((TMP_PATH/'images.pkl').open('rb'))
img_vecs = pickle.load((TMP_PATH/'img_vecs.pkl').open('rb'))arch = resnet50n = len(images); n*766876*val_idxs = list(range(n-28650, n))
```

这里有一个很酷的技巧。我们现在可以创建一个模型数据对象，它专门是一个图像分类器数据对象，我们有一个叫做`from_names_and_array`的东西，我不确定我们以前是否使用过，但我们可以传递一个文件名列表（ImageNet 中的所有文件名）和一个我们的因变量数组（所有快速文本词向量）。然后我们传入验证索引，这种情况下只是所有最后的 ID — 我们需要确保它们与 ImageNet 使用的相同，否则我们会作弊。然后我们传入`continuous=True`，这意味着这个图像分类器数据现在是一个图像回归数据，连续等于 True 意味着不要对我的输出进行独热编码，而是将它们视为连续值。现在我们有一个模型数据对象，其中包含所有文件名，对于每个文件名，都有一个表示该单词向量的连续数组。所以我们有了数据，现在我们需要一个架构和损失函数。

```py
tfms = tfms_from_model(arch, 224, transforms_side_on, max_zoom=1.1)
md = ImageClassifierData.**from_names_and_array**(PATH, images,  
        img_vecs, val_idxs=val_idxs, classes=**None**, tfms=tfms,
        continuous=**True**, bs=256)x,y = next(iter(md.val_dl))
```

让我们创建一个架构。我们下周会对此进行修订，但我们可以使用到目前为止学到的技巧，实际上非常简单。Fastai 有一个`ConvnetBuilder`，当你说`ConvLerner.pretrained`时就会调用它，并指定：

+   `f`: 架构（我们将使用 ResNet50）

+   `c`: 你想要多少类（在这种情况下，它实际上不是类别，而是你想要的输出数量，即快速文本词向量的长度，即 300）。

+   `is_multi`: 这不是多分类，因为根本不是分类。

+   `is_reg`: 是的，这是一个回归。

+   `xtra_fc`: 你想要什么全连接层。我们将添加一个长度为 1024 的全连接隐藏层。为什么是 1024？我认为 ResNet50 的最后一层是 1024，我们需要的最终输出是 300。显然，我们需要倒数第二层比 300 长。否则信息不足，所以我们选择了稍大一点的值。也许不同的数字会更好，但这对 Jeremy 有效。

+   `ps`: 你想要多少 dropout。Jeremy 发现默认的 dropout，他一直欠拟合，所以他将 dropout 从 0.5 降低到 0.2。

所以这是一个卷积神经网络，没有任何 softmax 之类的东西，因为它是回归，最后只是一个线性层，这就是我们的模型。我们可以从该模型创建一个 ConvLearner，并为其提供一个优化函数。现在我们只需要一个损失函数。

```py
models = ConvnetBuilder(arch, md.c, is_multi=**False**, is_reg=**True**, 
             xtra_fc=[1024], ps=[0.2,0.2])learn = ConvLearner(md, models, precompute=**True**)
learn.opt_fn = partial(optim.Adam, betas=(0.9,0.99))
```

**损失函数**：回归的默认损失函数是 L1 损失（绝对差异）- 这并不坏。但不幸的是，在真正高维空间中（任何稍微了解一点机器学习的人可能都知道），一切都在外面（在这种情况下，是 300 维）。当一切都在外面时，距离并不毫无意义，但有点尴尬。事物往往要么靠在一起，要么远离，在这些真正高维空间中，一切都在边缘，这并不意味着太多。然而，有意义的是，如果一件事在这边的边缘，另一件事在那边的边缘，我们可以形成这些向量之间的角度，这个角度是有意义的。这就是为什么在寻找高维空间中事物之间的接近或远离时，我们使用余弦相似度。如果你以前没有见过余弦相似度，它基本上与欧几里德距离相同，但被归一化为单位范数（即除以长度）。因此，我们不关心向量的长度，我们只关心它的角度。有很多东西你可以在几个小时内轻松学会，但如果你以前没有见过，它可能有点神秘。现在，只需知道损失函数和高维空间中，你在尝试找到相似性时，你关心角度，而不关心距离。如果你没有使用以下自定义损失函数，它仍然可以工作，但效果会差一点。现在我们有了数据、架构和损失函数，因此，我们完成了。我们可以继续拟合。

```py
**def** cos_loss(inp,targ):
    **return** 1 - F.cosine_similarity(inp,targ).mean()
learn.crit = cos_losslearn.lr_find(start_lr=1e-4, end_lr=1e15)learn.sched.plot()lr = 1e-2
wd = 1e-7
```

我们正在训练所有的 ImageNet，这将需要很长时间。所以`precompute=True`是你的朋友。还记得`precompute=True`吗？那是我们很久以前学到的东西，它会缓存最终卷积层的输出，然后只训练完全连接的部分。即使使用`precompute=True`，在所有的 ImageNet 上训练一个时代大约需要 3 分钟。所以这大约是一个小时的训练时间，但很酷的是，使用 fastai，我们可以在一个小时左右的时间内在所有的 ImageNet 上训练一个新的自定义头部 40 个时代。

```py
learn.precompute=**True**learn.fit(lr, 1, cycle_len=20, wds=wd, use_clr=(20,10))*epoch      trn_loss   val_loss                                  
    0      0.104692   0.125685  
    1      0.112455   0.129307                                 
    2      0.110631   0.126568                                 
    3      0.108629   0.127338                                 
    4      0.110791   0.125033                                 
    5      0.108859   0.125186                                 
    6      0.106582   0.123875                                 
    7      0.103227   0.123945                                 
    8      0.10396    0.12304                                  
    9      0.105898   0.124894                                 
    10     0.10498    0.122582                                 
    11     0.104983   0.122906                                 
    12     0.102317   0.121171                                  
    13     0.10017    0.121816                                  
    14     0.099454   0.119647                                  
    15     0.100425   0.120914                                  
    16     0.097226   0.119724                                  
    17     0.094666   0.118746                                  
    18     0.094137   0.118744                                  
    19     0.090076   0.117908**[0.11790786389489033]*learn.bn_freeze(**True**)learn.fit(lr, 1, cycle_len=20, wds=wd, use_clr=(20,10))*epoch      trn_loss   val_loss                                  
    0      0.104692   0.125685  
    1      0.112455   0.129307                                 
    2      0.110631   0.126568                                 
    3      0.108629   0.127338                                 
    4      0.110791   0.125033                                 
    5      0.108859   0.125186                                 
    6      0.106582   0.123875                                 
    7      0.103227   0.123945                                 
    8      0.10396    0.12304                                  
    9      0.105898   0.124894                                 
    10     0.10498    0.122582                                 
    11     0.104983   0.122906                                 
    12     0.102317   0.121171                                  
    13     0.10017    0.121816                                  
    14     0.099454   0.119647                                  
    15     0.100425   0.120914                                  
    16     0.097226   0.119724                                  
    17     0.094666   0.118746                                  
    18     0.094137   0.118744                                  
    19     0.090076   0.117908**[0.11790786389489033]*lrs = np.array([lr/1000,lr/100,lr])learn.precompute=**False**
learn.freeze_to(1)learn.save('pre0')learn.load('pre0')
```

# 图像搜索

## 搜索 imagenet 类

在所有这些之后，我们现在可以说让我们获取 1000 个 ImageNet 类，让我们在整个验证集上进行预测，并查看一些图片。

```py
syns, wvs = list(zip(*syn_wv_1k))
wvs = np.array(wvs)%time pred_wv = learn.predict()*CPU times: user 18.4 s, sys: 7.91 s, total: 26.3 s
Wall time: 7.17 s*start=300denorm = md.val_ds.denorm**def** show_img(im, figsize=**None**, ax=**None**):
    **if** **not** ax: fig,ax = plt.subplots(figsize=figsize)
    ax.imshow(im)
    ax.axis('off')
    **return** ax**def** show_imgs(ims, cols, figsize=**None**):
    fig,axes = plt.subplots(len(ims)//cols, cols, figsize=figsize)
    **for** i,ax **in** enumerate(axes.flat): show_img(ims[i], ax=ax)
    plt.tight_layout()
```

因为验证集是有序的，所有相同类型的东西都在同一个地方。

```py
show_imgs(denorm(md.val_ds[start:start+25][0]), 5, (10,10))
```

**最近邻搜索**[[2:10:56](https://youtu.be/tY0n9OT5_nA?t=2h10m56s)]：现在我们可以使用最近邻搜索。所谓最近邻搜索意味着这里有一个 300 维向量，这里有很多其他 300 维向量，它最接近哪个？通常这需要很长时间，因为你必须查看每个 300 维向量，计算其距离，找出它有多远。但是有一个几乎不为人知的神奇库叫做**NMSLib**，它可以做得非常快。你们中有些人可能尝试过其他最近邻库，我保证这比你们使用的更快 —— 我可以告诉你这一点，因为这是由专业人士进行基准测试的。在每个可能的维度上，这是迄今为止最快的。我们想要在角距离上创建一个索引，并且需要在我们所有的 ImageNet 词向量上执行。添加一个完整的批次，创建索引，现在我们可以一次查询一堆向量，获取最近的 10 个邻居。该库使用多线程，绝对棒。你可以从 pip 安装（`pip install nmslib`），它就能用了。

```py
**import** **nmslib****def** create_index(a):
    index = nmslib.init(space='angulardist')
    index.addDataPointBatch(a)
    index.createIndex()
    **return** index**def** get_knns(index, vecs):
     **return** zip(*index.knnQueryBatch(vecs, k=10, num_threads=4))**def** get_knn(index, vec): **return** index.knnQuery(vec, k=10)nn_wvs = create_index(wvs)
```

它告诉你它们有多远以及它们的索引[[2:12:13](https://youtu.be/tY0n9OT5_nA?t=2h12m13s)].

```py
idxs,dists = get_knns(nn_wvs, pred_wv)
```

所以现在我们可以浏览并打印出前 3 个，结果是鸟实际上是一只鹭鸟。有趣的是第四个并没有说它是一只鹭鸟，Jeremy 查了一下。他对鸟类了解不多，但其他一切都是棕色带白色斑点，但第四个不是。所以我们不知道那是否真的是一只鹭鸟，或者是否被错误标记，但它看起来绝对不像其他鸟类。

```py
[[classids[syns[id]] **for** id **in** ids[:3]] 
                         **for** ids **in** idxs[start:start+10]]*[['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['spoonbill', 'bustard', 'oystercatcher'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill']]*
```

这并不是一件特别困难的事情，因为 ImageNet 只有一千个类别，而且并没有做任何新的事情。但是如果我们现在引入整个 WordNet，然后说它最接近那 45,000 个东西中的哪一个呢？

## 搜索所有 WordMet 名词类别

```py
all_syns, all_wvs = list(zip(*syn2wv.items()))
all_wvs = np.array(all_wvs)nn_allwvs = create_index(all_wvs)idxs,dists = get_knns(nn_allwvs, pred_wv)[[classids[all_syns[id]] **for** id **in** ids[:3]] 
                             **for** ids **in** idxs[start:start+10]]*[['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['spoonbill', 'bustard', 'oystercatcher'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill'],
 ['limpkin', 'oystercatcher', 'spoonbill']]*
```

结果完全相同。现在正在搜索所有的 WordNet。

## 文本->图像搜索[[2:13:16](https://youtu.be/tY0n9OT5_nA?t=2h13m16s)]

现在让我们做一些有点不同的事情 —— 就是取出我们所有的预测（`pred_wv`），基本上取出我们整个验证图像集的预测，并创建一个图像表示的 KNN 索引，因为记住，它正在预测那些应该是词向量的东西。现在让我们获取“船”的快速文本向量，船不是 ImageNet 的概念 —— 然而我们现在可以找到所有在我们预测的词向量（即我们的验证集）中最接近“船”这个词的图像，即使它并没有被训练过。

```py
nn_predwv = create_index(pred_wv)
en_vecd = pickle.load(open(TRANS_PATH/'wiki.en.pkl','rb'))
vec = en_vecd['boat']idxs,dists = get_knn(nn_predwv, vec)
show_imgs([open_image(PATH/md.val_ds.fnames[i]) **for** i **in** idxs[:3]],
                      3, figsize=(9,3));
```

如果我们现在取引擎的向量和船的向量并取它们的平均值，如果我们现在在最近的邻居中寻找那个[[2:14:04](https://youtu.be/tY0n9OT5_nA?t=2h14m4s)]呢？

```py
vec = (en_vecd['engine'] + en_vecd['boat'])/2 idxs,dists = get_knn(nn_predwv, vec)
show_imgs([open_image(PATH/md.val_ds.fnames[i]) **for** i **in** idxs[:3]],
                      3, figsize=(9,3));
```

这些是带引擎的船。我的意思是，是的，中间那个实际上是一艘带引擎的船 —— 它碰巧也有翅膀。顺便说一句，帆不是 ImageNet 的东西，船也不是。这是两个不是 ImageNet 的东西的平均值，然而除了一个例外，它给我们找到了两艘帆船。

```py
vec = (en_vecd['sail'] + en_vecd['boat'])/2idxs,dists = get_knn(nn_predwv, vec)
show_imgs([open_image(PATH/md.val_ds.fnames[i]) **for** i **in** idxs[:3]],
                      3, figsize=(9,3));
```

## 图像->图像[[2:14:35](https://youtu.be/tY0n9OT5_nA?t=2h14m35s)]

好的，让我们做一些疯狂的事情。让我们在验证集中打开一张图像。让我们对该图像调用`predict_array`以获取其类似词向量的东西，并让我们在所有其他图像上进行最近邻搜索。

```py
fname = 'valid/n01440764/ILSVRC2012_val_00007197.JPEG'
img = open_image(PATH/fname)
show_img(img);
```

```py
t_img = md.val_ds.transform(img)
pred = learn.predict_array(t_img[**None**])idxs,dists = get_knn(nn_predwv, pred)
show_imgs([open_image(PATH/md.val_ds.fnames[i]) **for** i **in** idxs[1:4]],
                      3, figsize=(9,3));
```

这里是所有其他任何东西的图像。所以你可以看到，这很疯狂 —— 我们在一个小时内对所有 ImageNet 进行了训练，使用了一个基本上只需要两行代码的自定义头部，这些搜索运行在 300 毫秒内。

Jeremy 去年也教过这个基本概念，但是当时是在 Keras 中，代码很长，一切都很复杂。当时 Jeremy 说他无法想象你可以用这个做什么。他认为没有人真正深入思考过这个问题，但他觉得这很迷人。所以回去读 DeVICE 论文，因为 Andrea 有很多其他想法，现在做起来很容易，希望人们现在会深入研究这个问题。Jeremy 觉得这太疯狂和令人惊讶了。

好的，下周见！
