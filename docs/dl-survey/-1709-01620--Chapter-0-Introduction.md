<!--yml

类别：未分类

日期：2024-09-06 20:08:40

-->

# [1709.01620] 第零章 引言

> 来源：[`ar5iv.labs.arxiv.org/html/1709.01620`](https://ar5iv.labs.arxiv.org/html/1709.01620)

深度学习音乐生成技术综述 – 让-皮埃尔·布里奥^(∗,)¹¹1 也担任 UNIRIO（里约热内卢州立大学）访问教授，以及 PUC-Rio（里约热内卢天主教大学）常驻访问教授，巴西里约热内卢；盖坦·哈杰雷^† 和 弗朗索瓦-大卫·帕切^‡ ^∗ 索邦大学，法国国家科学研究中心，LIP6，F-75005 巴黎，法国

^† 索尼计算机科学实验室，CSL-巴黎，F-75005 巴黎，法国

^‡ Spotify 创作者技术研究实验室，CTRL，F-75008 巴黎，法国

本文综述并分析了使用深度学习（深度人工神经网络）生成音乐内容的不同方法。我们提出了一种基于五个维度的分析方法：

+   •

    目标

    +   –

        生成什么样的音乐内容？

        示例包括：旋律、和声、伴奏或对位。

    +   –

        用于什么目的和用途？

        可以由人类（在音乐谱的情况下）或机器（在音频文件的情况下）执行。

+   •

    表示

    +   –

        要操作的概念是什么？

        示例包括：波形、频谱图、音符、和弦、拍号和节拍。

    +   –

        使用什么格式？

        示例包括：MIDI、钢琴卷或文本。

    +   –

        表示将如何编码？

        示例包括：标量、单热编码或多热编码。

+   •

    架构

    +   –

        将使用什么类型的深度神经网络？

        示例包括：前馈网络、递归网络、自编码器或生成对抗网络。

+   •

    挑战

    +   –

        有哪些限制和未解决的挑战？

        示例包括：变异性、互动性和创造性。

+   •

    策略

    +   –

        我们如何建模和控制生成过程？

        示例包括：单步前馈、迭代前馈、采样或输入操作。

对于每个维度，我们进行各种模型和技术的比较分析，并提出一些初步的多维分类法。这种分类法是自下而上的，基于对从相关文献中选取的许多现有深度学习音乐生成系统的分析。这些系统被描述并用于举例说明目标、表示、架构、挑战和策略的各种选择。最后一部分包括一些讨论和前景展望。

额外材料提供于以下配套网站：

www.briot.info/dlt4mg/

本文是以下书籍的简化版（弱 DRM²²2 除了包含高质量彩色插图外，本书还包括：目录、表格清单、图形清单、缩略语表、术语表和索引。）briot:dlt4mg:book:2019：Jean-Pierre Briot, Gaëtan Hadjeres 和 François-David Pachet，《音乐生成的深度学习技术、计算合成与创意系统》，Springer，2019 年。硬封面 ISBN：978-3-319-70162-2。电子书 ISBN：978-3-319-70163-9。系列 ISSN：2509-6575。

## 第零章 引言

###### 摘要

*第一章 引言提供了本书的动机。它包括计算机音乐和音乐生成的历史简要总结（包括人工神经网络以及其他模型如文法、规则和马尔可夫链的早期应用）直到深度学习的近期崛起。它还描述了本书的组织和读者群体，以及相关工作。

深度学习最近成为一个快速增长的领域，现在被广泛用于分类和预测任务，如图像识别、语音识别或翻译。它在 2012 年变得流行，当时一种深度学习架构在图像分类比赛中显著超越了依赖手工特征的标准技术，详细信息见第 LABEL:section:architectures:history 节。

我们可以通过以下几点来解释人工神经网络技术的成功和重现：

+   •

    大规模的数据可用性；

+   •

    高效且负担得起的计算能力¹¹1 尤其是得益于最初为视频游戏设计的图形处理单元（GPU），它们现在在数据科学和深度学习应用中拥有最大的市场之一。；

+   •

    技术进步，例如：

    +   –

        预训练，解决了具有多层神经网络的初始训练效率低的问题 hinton:fast:algorithm:2006²²2 虽然如今它已被其他技术取代，如批量归一化 ioffe:batch:normalization:arxiv:2015 和深度残差学习 he:resnet:deep:residual:arxiv:2015。；

    +   –

        卷积，这提供了图案的平移不变性 le:cun:convolutional:handbook:1998；

    +   –

        LSTM（长短期记忆），解决了递归神经网络的初始训练效率低的问题 hochreiter:lstm:1997。

深度学习没有统一的定义。它是一种基于人工神经网络的机器学习（ML）技术的综合体。关键方面和共同点是“深度”这个术语。这意味着有多个层次处理多个层次的抽象，这些抽象是从数据中自动提取的³³3 虽然深度学习会自动提取数据中的重要特征，但输入表示的手动选择，例如音频的频谱与原始波形信号，对于学习的准确性和生成内容的质量可能非常重要，请参见第 LABEL:section:representation:feature:extraction 节。因此，深度架构可以管理和分解复杂的表示，转化为更简单的表示。其技术基础主要是人工神经网络，如我们将在第 LABEL:section:chapter:architecture 章中看到的，还有许多扩展，如：卷积网络、递归网络、自编码器和限制玻尔兹曼机。有关深度学习历史和各种方面的更多信息，请参见例如，最近的一本全面介绍该领域的书籍 goodfellow:deep:learning:book:2016。

深度学习的驱动应用是传统的机器学习任务⁴⁴4 机器学习中的任务是问题类型，也可以描述为机器学习系统应该如何处理一个示例（goodfellow:deep:learning:book:2016，第 5.1.1 节）。示例包括：分类、回归和异常检测：分类（例如，图像识别）和预测⁵⁵5 作为神经网络初始 DNA 的见证：线性回归和逻辑回归，请参见第 LABEL:section:architecture:linear:regression 节。（例如，天气预测）以及更近期的应用，如翻译。

但深度学习技术的一个增长领域是内容生成。内容可以是多种类型的：图像、文本和音乐，后者是我们分析的重点。动机在于利用现在广泛可用的各种语料库，自动学习音乐风格，并基于此生成新的音乐内容。

### 1 动机

#### 1 基于计算机的音乐系统

计算机生成的第一首音乐出现在 1957 年。它是一首 17 秒长的旋律，名为“银色音阶”，由其作者纽曼·古特曼创作，并由贝尔实验室开发的音乐合成软件 Music I 生成。同年，“伊利亚克组曲”是由计算机首次作曲的乐谱。它以美国伊利诺伊大学厄巴纳-香槟分校（UIUC）的 ILLIAC I 计算机命名。人类“元作曲家”是音乐家兼科学家雷加伦·A·希勒和莱昂纳德·M·艾萨克森。这是算法作曲的早期示例，利用随机模型（马尔可夫链）生成以及根据所需属性过滤生成材料的规则。

在声音合成领域，一个里程碑是 1983 年雅马哈发布 DX 7 合成器，基于乔宁关于基于频率调制（FM）合成模型的工作。同年，音乐乐器数字接口（MIDI）⁶⁶6 详见第 LABEL:section:representation:midi 节。接口推出，作为各种软件和乐器（包括雅马哈 DX 7 合成器）进行互操作的一种方式。另一个里程碑是在 IRCAM 由普克特开发的 Max/MSP 实时交互处理环境，用于实时合成和互动表演。

在算法作曲方面，20 世纪 60 年代初，伊安尼斯·克萨纳基斯探索了随机作曲的概念⁷⁷7 早在计算机出现之前，就有记录的随机音乐案例之一是沃尔夫冈·阿马德乌斯·莫扎特的《音乐骰子游戏》。这是为了通过使用骰子按照给定风格（奥地利圆舞曲在特定调性中）随机连接预定义的音乐片段来生成音乐 xenakis:formalized:music:book:1963。他在 1962 年的作品《阿特里斯》中实现了这一理念。这一想法涉及使用计算机快速计算来根据作曲家设计的一组概率计算各种可能性，以生成要选择的音乐片段样本。在“伊利亚克组曲”最初方向的另一种方法中，使用语法和规则来指定给定语料库或更普遍的音乐理论的风格。一个例子是在 1980 年代，埃比奥尔格鲁的作曲软件 CHORAL 中生成类似约翰·塞巴斯蒂安·巴赫风格的四声部赞美诗，根据超过 350 条手工制作的规则 ebcioglu:expert:system:bach:cmj:1988。在 1980 年代末，大卫·科普的系统名为音乐智能实验（EMI），通过学习作曲家的乐谱库来扩展这一方法，创建自己的语法和规则数据库 cope:algorithmic:composer:book:2000。

自那时以来，计算机音乐持续发展以服务于大众，例如考虑到 GarageBand 音乐创作和制作应用程序，它是 Apple 平台（计算机、平板电脑和手机）的一个衍生品，而 GarageBand 最初源于 Steinberg 于 1989 年发布的 Cubase 序列软件。

关于计算机音乐的历史和原则的更多细节，请参阅，例如 Roads 的书籍（roads:computer:music:tutorial:book:1996）。关于算法作曲的历史和原则的更多细节，请参阅，例如 maurer 的著作（maurer:brief:history:algorithmic:composition:1999）以及 Cope 的书籍（cope:algorithmic:composer:book:2000）或 Dean 和 McLean 的著作（dean:oxford:handbook:2018）。

#### 2 自主性与辅助性

说到计算机生成音乐时，实际上存在一些模糊性，即目标是否是

+   •

    设计和构建自主音乐创作系统——最近的两个例子是基于深度学习的 Amper™ 和 Jukedeck 系统/公司，旨在为广告和纪录片创作原创音乐；或者

+   •

    设计和构建计算机环境以辅助人类音乐家（作曲家、编曲家、制作人等）——例如，Sony CSL-Paris 开发的 FlowComposer 环境（在第 LABEL:section:systems:flow:composer 节中介绍）和 IRCAM 开发的 OpenMusic 环境（assayag:openmusic:cmj:1999）就是两个例子。

对于自主音乐创作系统的探索可能是一个有趣的视角来研究创作过程⁸⁸8 正如理查德·费曼所言：“我不能创造的东西，我不理解。” 它也作为一种评估方法。例如，音乐图灵测试⁹⁹9 最初由艾伦·图灵于 1950 年制定，并由他命名为“模仿游戏”（turing:test:mind:1950），该测试是对机器是否能展现出等同于（更准确地说，是无法区分的）人类智能行为的测试。在他的虚拟实验设置中，图灵提出了一个自然语言对话的测试，其中人类（评估者）与隐藏的演员（另一个人或机器）进行对话。如果评估者不能可靠地区分机器和人类，则认为机器通过了测试。将在第 LABEL:section:experiment:deep:bach 节中介绍。这种测试涉及向不同公众（从初学者到专家）展示由 J. S. 巴赫创作的合唱曲或由深度学习系统生成并由人类音乐家演奏的合唱曲¹⁰¹⁰10 这是为了避免计算机生成音乐的偏见（合成风味）.. 如我们将在下文中看到的，深度学习技术在这样的测试中表现出色，因为它们能够从特定的语料库中学习音乐风格并生成符合该风格的新音乐。也就是说，我们认为这样的测试更多的是一种手段而非目的。

更广泛的视角是帮助人类音乐家在音乐创作的各个阶段：作曲、编曲、编排、制作等。确实，要进行作曲或即兴创作¹¹¹¹11 即兴创作是一种实时作曲形式。，音乐家很少从零开始创作新音乐。他/她会有意识或无意识地重用和适应自己已经知道或听过的各种音乐特征，同时遵循一些原则和指导方针，例如和声和音阶理论。基于计算机的音乐助手可以在创作的不同阶段发挥作用，以启动、建议、激发和/或补充人类作曲家的灵感。

也就是说，正如我们将看到的那样，目前大多数基于深度学习的音乐生成系统仍然专注于自主生成，尽管越来越多的系统正在解决人类水平的控制和互动问题。

#### 3 符号 AI 与子符号 AI

人工智能（AI）通常分为两个主要方向¹²¹²12 有一些例外，因为这种划分并不那么严格。：

+   •

    符号 AI - 处理高级符号表示（例如，和弦、和声……）和过程（和声化、分析……）；以及

+   •

    子符号 AI - 处理低级表示（例如，声音、音色……）和过程（音高识别、分类……）。

用于音乐的符号模型的例子包括基于规则的系统或语法来表示和声。用于音乐的子符号模型的例子包括机器学习算法，它们通过从一系列音乐作品中自动学习音乐风格。这些模型可以以生成性和互动性的方式使用，帮助音乐家创作新音乐，通过利用这种附加的“智能”记忆（联想、归纳和生成）来建议提案、草图、推断、映射等。这现在是可行的，因为各种形式的音乐（例如声音、乐谱和 MIDI 文件）越来越容易获得，可以由计算机自动处理。

最近一个集成音乐创作环境的例子是 FlowComposer papadopoulos:flow:composer:cp:2016，我们将在第 LABEL:section:systems:flow:composer 节中介绍它。它提供了各种符号和子符号技术，例如，用于建模风格的马尔可夫链、用于表达约束的约束求解模块、用于生成和声分析的基于规则的模块，以及用于生成渲染的音频映射模块。另一个集成音乐创作环境的例子是 OpenMusic assayag:openmusic:cmj:1999。

然而，符号技术（如约束和推理）与子符号技术（如深度学习）的更深层次整合仍然是一个未解的问题¹³¹³13 将子符号和符号层整合成一个完整的 AI 系统的总体目标是 AI 的“圣杯”之一，尽管在有限的背景下已经存在一些部分整合（例如，pachet:markov:constraints:constraints:2011; barbieri:lyrics:style:2012 中的 Markov 约束，以及 FlowComposer 的一个使用示例见 Section LABEL:section:systems:flow:composer）。

#### 4 深度学习

使用深度学习（以及更一般的机器学习技术）生成音乐内容的动机在于其通用性。与手工制作的模型（如基于语法的 steedman:generative:grammar:blues:mp:1984 或基于规则的音乐生成系统 ebcioglu:expert:system:bach:cmj:1988）相比，基于机器学习的生成系统可以是不可知的，因为它从任意音乐语料库中学习模型。因此，同一系统可以用于各种音乐类型。

因此，随着更多大规模音乐数据集的提供，基于机器学习的生成系统将能够从语料库中自动学习音乐风格并生成新的音乐内容。正如 Fiebrink 和 Caramiaux 所述 fiebrink:ml:creative:tool:arxiv:2016，一些好处是

+   •

    它可以使创作变得可行，当期望的应用过于复杂以至于无法通过分析公式或手动设计完成时，

+   •

    学习算法通常比手动设计的规则集更不易脆弱，学习到的规则更可能准确地推广到输入可能变化的新上下文中。

此外，与结构化表示（如规则和语法）相反，深度学习擅长处理原始非结构化数据，从中其层次结构将提取适应任务的高级表示。

#### 5 现状与未来

正如我们将看到的，基于深度学习的音乐生成研究领域最近变得非常热门，这建立在最初利用人工神经网络生成音乐的工作基础上（例如，1989 年 Todd 的开创性实验 todd:connectionist:composition:1989 和 1994 年 Mozer 开发的 CONCERT 系统 mozer:composition:prediction:1994），同时也由于深度学习的进步而带来了大量的新思想和挑战。我们还注意到一些大型数字媒体公司对计算机辅助艺术内容生成的兴趣日益增长，Google 在 2016 年 6 月创建了 Magenta 研究项目 google:magenta:project:web，Spotify 在 2017 年 9 月创建了 Creator Technology Research Lab (CTRL) spotify:ctrl:2017。这可能会通过音乐内容的个性化模糊音乐创作和音乐消费之间的界限 amato:ai:media:arxiv:2019。

### 2 本书

目前我们所知缺乏对这一活跃研究领域的全面调查和分析，这激发了本书的编写，该书从大量近期研究工作的分析中自下而上地构建。其目标是提供有关使用深度学习生成音乐的问题和技术的全面描述，通过对文献中各种架构、系统和实验的分析进行说明。我们还提出了一个概念框架和类型学，以便更好地理解当前和未来系统的设计决策。

#### 其他书籍和来源

据我们了解，目前只有少数对使用深度学习生成音乐的分析尝试。在 briot:dlt4mg:arxiv:2017 中，Briot 等人提出了通过多标准分析（考虑目标、表示、架构和策略作为维度）对各种系统的首次调查。我们通过将挑战作为附加维度进行扩展和整合（在 briot:mgbdl:cd:ncaa:2018 中进行了分析）。

在 graves:generating:sequences:rnn:arxiv:2014 中，Graves 呈现了一个关注于递归神经网络和文本生成的分析。在 humphrey:feature:learning:music:2013 中，Humphrey 等人提出了另一个分析，讨论了音乐表示的一些问题（见第 LABEL:section:representation 节），但专注于音乐信息检索（MIR）任务，如和弦识别、流派识别和情绪估计。有关深度学习在 MIR 应用中的教程，请参见 Choi 等人的最近教程论文 choi:tutorial:deep:learning:mir:arxiv:2017。

还可以查阅一些最近创建的国际研讨会的会议记录，例如

+   •

    2016 年构造性机器学习研讨会（CML 2016），在第 30 届神经信息处理系统年会（NIPS 2016）上举行 cml:nips:2016；

+   •

    深度学习音乐研讨会（DLM），在国际联合神经网络会议（IJCNN 2017）期间举行 dl4m:ijcnn:2017，之后是特别期刊文章 herremans:deep:music:ncaa:2019；以及

+   •

    关于创意的深层挑战，相关的国际计算创意会议系列（ICCC）iacc:iccc:web。

对于计算机生成音乐的更一般性调查，读者可以参考一些通用书籍，例如

+   •

    Roads 关于计算机音乐的书籍 roads:computer:music:tutorial:book:1996；

+   •

    Cope 的 cope:algorithmic:composer:book:2000，Dean 和 McLean 的 dean:oxford:handbook:2018 和/或 Nierhaus 的 nierhaus:algorithmic:composition:book:2009 有关算法作曲的书籍；

+   •

    关于算法作曲中 AI 方法的最近调查 fernandez:ai:methods:algorithmic:composition:survey:jair:2013；以及

+   •

    Cope 关于音乐创意模型的书籍 cope:musical:creativity:book:2005。

关于机器学习，一些教科书的例子有

+   •

    mitchell 的教科书 mitchell:ml:book:1997；

+   •

    Domingos 的精彩介绍和总结 domingos:things:know:2012；以及

+   •

    关于深度学习的最新、完整且全面的书籍 Goodfellow 等著 goodfellow:deep:learning:book:2016。

#### 2 其他模型

我们必须记住，除了马尔可夫模型和图形模型外，还有许多其他模型和技术用于生成音乐，例如规则、语法、自动机等。这些模型要么由专家手动定义，要么通过各种机器学习技术从示例中自动学习。由于本书关注的是深度学习技术，因此这些模型不会在书中讨论。然而，在接下来的部分中，我们将对深度学习和马尔可夫模型进行快速比较。

#### 3 深度学习与马尔可夫模型的比较

深度学习模型并不是唯一能够从示例中学习音乐风格的模型。马尔可夫链模型也被广泛使用，例如，参见 pachet:continuator:ieee:cga:2004。一个关于深度神经网络模型和马尔可夫链模型优缺点的快速比较（灵感来源于 Mozer 的分析 mozer:composition:prediction:1994¹⁴¹⁴14 请注意，他的分析是在 1994 年完成的，远在深度学习浪潮之前。）如下：

[–]

+

马尔可夫模型在概念上简单。

+

马尔可夫模型具有简单的实现和学习算法，因为该模型是一个转移概率表¹⁵¹⁵15 统计数据是从示例数据集中收集的，用于计算概率。

–

神经网络模型在概念上简单，但当前深度网络架构的优化实现可能复杂且需要大量调优。

–

一阶马尔可夫模型（即只考虑前一个状态）无法捕捉长期的时间结构。

–

n 阶马尔可夫模型（考虑前 n 个状态）是可能的，但需要巨大的训练集¹⁶¹⁶16 参见 (mozer:composition:prediction:1994，第 249 页) 并且可能导致抄袭¹⁷¹⁷17 通过从语料库中抄袭过长的序列。一些有前途的解决方案是考虑变阶马尔可夫模型，并通过最小阶和最大阶约束来限制生成（在垃圾和抄袭之间找到某个甜点）。 papadopoulos:maxorder:universality:book:2016。

+

神经网络可以捕捉各种类型的关系、上下文和规律。

+

深度网络可以学习长期和高阶依赖关系。

+

马尔可夫模型可以从少量示例中学习。

–

神经网络需要大量示例才能很好地学习。

–

马尔可夫模型的泛化能力较差。

+

神经网络通过分布式表示的使用具有更好的泛化能力 hinton:boltzmann:machines:pdp:1986。

+

马尔可夫模型是可附加某些生成控制的操作模型（自动机）¹⁸¹⁸18 例如马尔可夫约束 pachet:markov:constraints:constraints:2011 和因子图 pachet:variations:structured:ismir:2017。

–

深度网络是具有分布式表示的生成模型，因此没有直接控制机制可以附加¹⁹¹⁹19 此问题及一些可能的解决方案将在第 LABEL:section:challenges:strategies:control:dimensions:strategies 节中讨论。

随着深度学习实现的成熟和大量示例的出现，基于深度学习的模型因其特性而需求旺盛。尽管如此，其他模型（如马尔可夫链、图形模型等）仍然有用并且被使用，模型的选择及其调整取决于问题的特性。

#### 4 个必要条件和路线图

本书不要求读者具备深度学习、神经网络或音乐方面的先验知识。

第一章 引言（本章）介绍了本书的目的和基本原理。

第一章 方法介绍了分析方法（概念框架）及其基础上的五个维度（目标、表示、架构、挑战和策略），这些维度将在接下来的四章中讨论。

第 LABEL:section:chapter:objective 章 目标涉及我们希望生成的不同类型的音乐内容（如旋律或对现有旋律的伴奏）²⁰²⁰20 我们提出的可能目标类型将对我们的分析有用，因为正如我们将看到的，不同的目标可以导致不同的架构和策略，以及其预期的使用（由人类和/或机器）。

第 LABEL:section:chapter:representation 章 表示提供了对不同类型表示和编码音乐内容（如音符、时值或和弦）技术的分析，以适用于深度学习架构。本章可由已经精通计算机音乐的读者跳过，尽管一些编码策略对神经网络和深度学习架构是特定的。

第 LABEL:section:chapter:architecture 章 架构总结了用于音乐生成的最常见的深度学习架构（如前馈、递归或自编码器）。包括对简单神经网络基本知识的简短回顾。本章可由已经精通人工神经网络和深度学习架构的读者跳过。

第 LABEL:section:chapter:challenges:strategies 章 挑战与策略提供了在应用深度学习技术于音乐生成时所遇到的各种挑战的分析，以及应对这些挑战的各种策略。我们将以从文献中调查的各种系统和实验的分析为基础。该章是本书的核心。

第 LABEL 章:部分:章:分析 分析总结了第 LABEL 章:部分:章:挑战:策略中进行的调查和分析，通过一些表格来识别不同系统的设计决策及其相互关系²¹²¹21 并希望对未来的系统也有所帮助。如果我们在某种元层面上将其与期望模型从语料库中学习的能力进行类比，期望其能够推广到未来的示例（见第 LABEL 章:部分:架构:训练:过拟合），我们希望本书中提出的概念框架（从深度学习音乐生成系统的科学和技术文献语料库中手动引导出来）也能在未来系统的设计和理解中提供帮助。

第 LABEL 章:部分:章:讨论:结论 讨论与结论回顾了在第 LABEL 章:部分:章:挑战:策略中分析挑战和策略时提到的一些未解问题，然后对本书进行总结。

书末附有目录、缩略语表、参考文献列表、术语表和索引。

附加材料可在以下伴随网站获取：

www.briot.info/dlt4mg/

#### 5 限制

本书并不打算成为深度学习的通用介绍——最近的一本关于这一主题的全面书籍是 goodfellow:deep:learning:book:2016。我们不打算涉及所有实施的技术细节，如工程和调整，以及理论²²²²22 例如，我们不会展开神经网络和深度学习行为的概率论和信息论框架。然而，第 LABEL 章:部分:架构:神经:网络:熵 将介绍熵和交叉熵的直觉，这些概念用于衡量学习过程中取得的进展。我们希望专注于概念层面，同时提供足够的精确度。此外，尽管有明确的教学目标，我们并没有提供有关如何实施和调整完整的深度学习音乐生成系统的端到端教程及所有步骤和细节。

最后，由于本书涉及的是一个非常活跃的领域，并且我们的调查和分析基于现有系统，因此我们的分析显然不够全面。我们尽力选择了最具代表性的提案和实验，而新的提案在我们写作时正不断出现。因此，我们鼓励读者和同行提供反馈和建议，以改进本调查和分析，这是一个仍在进行的项目。

## 第一章 方法
