# 深度学习 2：第 2 部分第 8 课

> 原文：[`medium.com/@hiromi_suenaga/deep-learning-2-part-2-lesson-8-5ae195c49493`](https://medium.com/@hiromi_suenaga/deep-learning-2-part-2-lesson-8-5ae195c49493)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](http://creativecommons.org/licenses/by-nc-sa/4.0/)

*我从* [*fast.ai 课程*](http://www.fast.ai/)* 中的个人笔记。这些笔记将在我继续审查课程以“真正”理解它时继续更新和改进。非常感谢* [*Jeremy*](https://twitter.com/jeremyphoward) *和* [*Rachel*](https://twitter.com/math_rachel) *给了我这个学习的机会。*

# 目标检测

[**论坛**](http://forums.fast.ai/t/part-2-lesson-8-in-class/13556/1) **/** [**视频**](https://youtu.be/Z0ssNAbe81M) **/** [**笔记本**](https://github.com/fastai/fastai/blob/master/courses/dl2/pascal.ipynb) **/** [**幻灯片**](https://github.com/fastai/fastai/blob/master/courses/dl2/ppt/lesson8.pptx)

## **我们在第一部分中涵盖的内容 [**[**02:00**](https://youtu.be/Z0ssNAbe81M?t=2m)**]**

**可微分层 [**[**02:11**](https://youtu.be/Z0ssNAbe81M?t=2m11s)**]**

Yann LeCun 一直在推广这样一个观点，即我们不称之为“深度学习”，而是“可微分编程”。我们在第一部分所做的一切实际上都是关于建立一个可微分函数和一个描述参数好坏的损失函数，然后按下开始按钮，它就开始工作了。如果你能配置一个评分函数来评估某个任务的表现，并且有一个相当灵活的神经网络架构，那么你就完成了。

> 是的，可微分编程只不过是现代深度学习技术的一个重新包装，就像深度学习是神经网络的现代化版本，具有超过两层的层次一样。
> 
> 重要的一点是，人们现在通过组装参数化的功能块网络，并通过使用某种形式的基于梯度的优化从示例中训练它们来构建一种新型软件……这实际上非常类似于常规程序，只是它是参数化的，自动区分的，可训练/可优化的。
> 
> - [Yann LeCun，FAIR 主任](https://www.facebook.com/yann.lecun/posts/10155003011462143)

**2\. 迁移学习 [**[**03:23**](https://youtu.be/Z0ssNAbe81M?t=3m23s)**]**

迁移学习是有效使用深度学习的最重要的单一事项。你几乎永远不会想要或需要从随机权重开始，除非没有人曾经在一个大致相似的数据集上训练过一个与你正在解决的问题有一定联系的模型 — 这几乎不会发生。Fastai 库专注于迁移学习，这使它与其他库不同。迁移学习的基本思想是：

+   给定一个执行 A 任务的网络，移除最后一层。

+   在最后随机添加几个层

+   微调这些层以执行 B 任务，同时利用原始网络学到的特征

+   然后选择性地对整个模型进行微调，现在你有了一个可能使用数量级更少的数据，更准确，训练速度更快的东西。

**3\. 架构设计 [**[**05:17**](https://youtu.be/Z0ssNAbe81M?t=5m17s)**]**

通常有一小范围的架构通常在很多时候都表现得相当不错。我们一直专注于使用 CNN 处理通常大小固定的有序数据，RNN 处理具有某种状态的序列。我们还稍微调整了一下激活函数 — 如果有单一分类结果，则使用 softmax，如果有多个结果，则使用 sigmoid。我们将在第 2 部分研究的一些架构设计更有趣。特别是关于目标检测的这个第一个会话。但总的来说，我们可能花更少的时间讨论架构设计，因为这通常不是难点。

**4\. 处理过拟合 [**[**06:26**](https://youtu.be/Z0ssNAbe81M?t=6m26s)**]**

Jeremy 喜欢构建模型的方式：

+   创建一些明显过度参数化的东西，肯定会过度拟合，训练它并确保它确实过拟合。在那一点上，你已经有了一个能够反映训练集的模型。然后只需做这些事情来减少过拟合。

如果你不从一个过拟合的地方开始，你就会迷失。所以你从一个过拟合的地方开始，为了让它过拟合得更少，你可以：

+   添加更多数据

+   添加更多数据增强

+   做一些像更多的批量归一化层、稠密网络，或者各种可以处理更少数据的东西。

+   添加正则化，如权重衰减和丢失

+   最后（这通常是人们首先做的事情，但这应该是你最后做的事情）减少你的架构复杂性。减少层数或激活数量。

5. 嵌入[07:46]

我们已经谈了很多关于嵌入 - 无论是用于自然语言处理还是任何种类的分类数据，现在你可以用神经网络来建模。就在今年初，几乎没有关于在深度学习中使用表格数据的例子，但现在越来越多的人开始使用神经网络来进行时间序列和表格数据分析。

## 第一部分到第二部分[08:54]

第一部分真的是关于引入深度学习的最佳实践。我们看到的技术已经足够成熟，可以相对可靠地应用于实际的现实世界问题。Jeremy 经过相当长一段时间的研究和调整，提出了一系列步骤、架构等，并将它们快速、轻松地放入 fastai 库中。

第二部分是面向程序员的前沿深度学习，这意味着 Jeremy 通常不知道确切的最佳参数、架构细节等来解决特定问题。我们不一定知道它是否能够解决问题到足够实用的程度。它几乎肯定不会被很好地整合到 fastai 或任何其他库中，你不能只按几个按钮就开始工作。Jeremy 不会教授它，除非他非常有信心，要么现在就是，要么很快就会成为非常实用的技术。但通常需要大量的调整和实验才能使其在你的特定问题上工作，因为我们不知道足够的细节来知道如何使其适用于每个数据集或每个示例。

这意味着与 Fastai 和 PyTorch 成为你只知道这些配方的晦涩黑匣子不同，你将学会足够了解它们的细节，以便可以按照自己的意愿定制它们，可以调试它们，可以阅读它们的源代码以了解发生了什么。如果你对面向对象的 Python 不自信，那么这是你在本课程中要专注学习的内容，因为我们不会在课堂上涵盖它。但 Jeremy 会介绍一些他认为特别有帮助的工具，比如 Python 调试器，如何使用你的编辑器跳转到代码中。总的来说，将会有更多详细和具体的代码演示，编码技术讨论，以及更详细的论文演示。

注意示例代码[13:20]！学术界提供的代码与论文配套或其他人在 github 上编写的示例代码，Jeremy 几乎总是发现有一些重大的关键缺陷，所以小心从在线资源中获取代码，并准备做一些调试。

如何使用笔记本[14:17]

构建你自己的盒子[16:50]

阅读论文[21:37]

每周，我们将实现一两篇论文。左边是一篇实现 adam 的论文摘录（你也在电子表格上看到过 adam 作为一个单独的 excel 公式）。在学术论文中，人们喜欢使用希腊字母。他们也不喜欢重构，所以你经常会看到一页长的公式，仔细看时你会意识到相同的子方程出现了 8 次。学术论文有点奇怪，但最终，这是研究界传达他们发现的方式，所以我们需要学会阅读它们。一个很好的做法是拿一篇论文，努力理解它，然后写一篇博客，在博客中用代码和普通英语解释它。许多这样做的人最终会得到相当多的关注，得到一些非常好的工作机会等，因为能够展示你能理解这些论文、在代码中实现它们并用英语解释它们是一种非常有用的技能。很难阅读或理解你无法口头表达的东西。所以学习希腊字母吧！

更多机会

第二部分的主题

**生成模型**

在第一部分，我们的神经网络的输出通常是一个数字或一个类别，而在第二部分中，很多东西的输出将是很多东西，比如：

+   图像中每个对象的左上角和右下角位置以及该对象是什么

+   一幅完整的图片，显示该图片中每个像素的类别

+   输入图像的增强超分辨率版本

+   整个原始输入段落翻译成法语

我们将要查看的绝大多数数据要么是文本数据，要么是图像数据。

我们将查看一些更大的数据集，无论是数据集中的对象数量还是每个对象的大小。对于那些使用有限计算资源的人，请不要因此而退缩。随时可以用更小更简单的东西替代。Jeremy 实际上在没有互联网的情况下（在 Point Leo）用 15 英寸的 surface book 写了大部分课程。几乎所有这门课程在 Windows 笔记本电脑上都能很好地运行。你可以始终使用更小的批量大小、精简版本的数据集。但如果你有资源，当可用时，使用更大的数据集会获得更好的结果。

## 目标检测

与我们习惯的两个主要区别：

**1.我们正在对多个事物进行分类。**

这并不罕见——我们在第一部分的星球卫星数据中做过这个。

**2.我们正在对我们分类的事物周围加上边界框。**

边界框有一个非常具体的定义，即它是一个矩形，矩形内的对象完全适合其中，但它不会比必须的更大。

我们的工作将是采用这种方式标记的数据，并在未标记的数据上生成对象的类别和每个对象的边界框。需要注意的一点是，标记这种数据通常更昂贵。对于目标检测数据集，标注者会得到一个对象类别列表，并被要求在图片中找到每一个类型的对象以及它们的位置。在这种情况下，为什么没有一个树或跳跃被标记呢？因为对于这个特定的数据集，标注者没有被要求找到它们，因此不是这个特定问题的一部分。

## 阶段：

1.  对每个图像中最大的对象进行分类。

1.  找到每个图像中最大对象的位置。

1.  最后，我们将尝试同时做两件事（即标记它是什么以及在图片中的位置）。

## [帕斯卡笔记本](https://github.com/fastai/fastai/blob/master/courses/dl2/pascal.ipynb)

```py
%matplotlib inline
%reload_ext autoreload
%autoreload 2
from fastai.conv_learner import *
from fastai.dataset import *
from pathlib import Path
import json
from PIL import ImageDraw, ImageFont
from matplotlib import patches, patheffects
# torch.cuda.set_device(1) 
```

您可能会发现一行`torch.cuda.set_device(1)`被遗留下来，如果您只有一个 GPU，这会导致错误。这是在您有多个 GPU 时选择 GPU 的方法，所以只需将其设置为零或完全删除该行。

就像 ImageNet 是一个标准的对象分类数据集一样，还有许多标准的目标检测数据集[[41:12](https://youtu.be/Z0ssNAbe81M?t=41m12s)]。经典的 ImageNet 等价物是 Pascal VOC。

## Pascal VOC

我们将查看[Pascal VOC](http://host.robots.ox.ac.uk/pascal/VOC/)数据集。这个数据集相当慢，所以您可能更喜欢从[这个镜像](https://pjreddie.com/projects/pascal-voc-dataset-mirror/)下载。有两个不同的竞赛/研究数据集，分别来自 2007 年和 2012 年。我们将使用 2007 年的版本。您可以使用更大的 2012 年版本获得更好的结果，甚至可以将它们结合起来[[42:25](https://youtu.be/Z0ssNAbe81M?t=42m25s)]（但如果这样做，请注意避免验证集之间的数据泄漏）。

与以前的课程不同，我们在路径和文件访问中使用了 Python 3 标准库`pathlib`。请注意，它返回一个特定于操作系统的类（在 Linux 上是`PosixPath`），因此您的输出可能会有些不同[[44:50](https://youtu.be/Z0ssNAbe81M?t=44m50s)]。大多数以路径作为输入的库可以接受`pathlib`对象 - 尽管有些（如`cv2`）不能，这种情况下可以使用`str()`将其转换为字符串。

[Pathlib Cheat Sheet](http://pbpython.com/pathlib-intro.html)

```py
PATH = Path('data/pascal')
list(PATH.iterdir())
'''
[PosixPath('data/pascal/PASCAL_VOC.zip'),
 PosixPath('data/pascal/VOCdevkit'),
 PosixPath('data/pascal/VOCtrainval_06-Nov-2007.tar'),
 PosixPath('data/pascal/pascal_train2012.json'),
 PosixPath('data/pascal/pascal_val2012.json'),
 PosixPath('data/pascal/pascal_val2007.json'),
 PosixPath('data/pascal/pascal_train2007.json'),
 PosixPath('data/pascal/pascal_test2007.json')]
'''
```

**关于生成器的一点说明[**[**43:23**](https://youtu.be/Z0ssNAbe81M?t=43m23s)**]：**

生成器是 Python 3 中的一种可以迭代的东西。

+   `for i in PATH.iterdir(): print(i)`

+   `[i for i in PATH.iterdir()]`（列表推导）

+   `list(PATH.iterdir())`（将生成器转换为列表）

通常返回生成器的原因是，如果目录中有 1000 万个项目，您不一定希望有 1000 万个长列表。生成器让您可以“懒惰”地执行操作。

## 加载注释

除了图像外，还有*注释* - 显示每个对象位置的*边界框*。这些是手工标记的。原始版本是 XML 格式[[47:59](https://youtu.be/Z0ssNAbe81M?t=47m59s)]，这在现在有点难以处理，所以我们使用了更近期的 JSON 版本，您可以从[此链接](https://storage.googleapis.com/coco-dataset/external/PASCAL_VOC.zip)下载。

您可以在这里看到`pathlib`包含打开文件的能力（以及许多其他功能）。

```py
trn_j = json.load((PATH/'pascal_train2007.json').open())
trn_j.keys()
'''
dict_keys(['images', 'type', 'annotations', 'categories'])
'''
```

这里的`/`不是除法符号，而是路径斜杠[[45:55](https://youtu.be/Z0ssNAbe81M?t=45m55s)]。`PATH/`可以让您获取该路径中的子项。`PATH/’pascal_train2007.json’`返回一个`pathlib`对象，该对象具有一个`open`方法。这个 JSON 文件不包含图像，而是包含对象的边界框和类别。

```py
IMAGES,ANNOTATIONS,CATEGORIES = [
    'images', 'annotations', 'categories'
] 
trn_j[IMAGES][:5]
'''
[{'file_name': '000012.jpg', 'height': 333, 'id': 12, 'width': 500},  {'file_name': '000017.jpg', 'height': 364, 'id': 17, 'width': 480},  {'file_name': '000023.jpg', 'height': 500, 'id': 23, 'width': 334},  {'file_name': '000026.jpg', 'height': 333, 'id': 26, 'width': 500},  {'file_name': '000032.jpg', 'height': 281, 'id': 32, 'width': 500}]
'''
```

## 注释 [[49:16](https://youtu.be/Z0ssNAbe81M?t=49m16s)]

+   `bbox`：列，行（左上角），高度，宽度

+   `image_id`：您需要将其与`trn_j[IMAGES]`（上面）连接起来，以查找`file_name`等。

+   `category_id`：查看`trn_j[CATEGORIES]`（下面）

+   `segmentation`：多边形分割（我们将使用它们）

+   `ignore`：我们将忽略忽略标志

+   `iscrowd`：指定这是该对象的一群，而不仅仅是其中一个

```py
trn_j[ANNOTATIONS][:2]
'''
[{'area': 34104,
  'bbox': [155, 96, 196, 174],
  'category_id': 7,
  'id': 1,
  'ignore': 0,
  'image_id': 12,
  'iscrowd': 0,
  'segmentation': [[155, 96, 155, 270, 351, 270, 351, 96]]},
 {'area': 13110,
  'bbox': [184, 61, 95, 138],
  'category_id': 15,
  'id': 2,
  'ignore': 0,
  'image_id': 17,
  'iscrowd': 0,
  'segmentation': [[184, 61, 184, 199, 279, 199, 279, 61]]}]
'''
```

## 类别 [[50:15](https://youtu.be/Z0ssNAbe81M?t=50m15s)]

```py
trn_j[CATEGORIES][:4]
'''
[{'id': 1, 'name': 'aeroplane', 'supercategory': 'none'},
 {'id': 2, 'name': 'bicycle', 'supercategory': 'none'},
 {'id': 3, 'name': 'bird', 'supercategory': 'none'},
 {'id': 4, 'name': 'boat', 'supercategory': 'none'}]
'''
```

使用常量而不是字符串很有帮助，因为我们可以获得制表符补全，不会输错。

```py
FILE_NAME,ID,IMG_ID,CAT_ID,BBOX = 'file_name','id','image_id','category_id','bbox'
cats = dict((o[ID], o['name']) for o in trn_j[CATEGORIES])
trn_fns = dict((o[ID], o[FILE_NAME]) for o in trn_j[IMAGES])
trn_ids = [o[ID] for o in trn_j[IMAGES]]
```

**侧记：当人们实时看到 Jeremy 在工作时，看到他的课程后最常评论的是[**[**51:21**](https://youtu.be/Z0ssNAbe81M?t=51m21s)**]：**

“哇，你实际上不知道自己在做什么，是吧”。他做的 99%的事情都不起作用，而那些确实起作用的事情只占很小的比例。他提到这一点是因为机器学习，特别是深度学习，非常令人沮丧。理论上，您只需定义正确的损失函数和足够灵活的架构，然后按下训练按钮，就完成了。但如果那确实是所有需要的，那么什么都不会花费任何时间。问题在于一直到它起作用的所有步骤，它都不起作用。就像它直接进入无限大，崩溃并显示不正确的张量大小等。他将努力向您展示一些调试技术，但这是最难教授的事情之一。它需要的主要是坚韧不拔。那些非常有效的人和那些似乎走得不远的人之间的区别从来不是智力问题。它总是关于坚持下去 - 基本上是永不放弃。这在这种深度学习中尤为重要，因为您不会得到持续的奖励循环。它是一种持续的不起作用，不起作用，不起作用，直到最终起作用的过程，所以有点烦人。

## 让我们看看这些图像。

```py
list((PATH/'VOCdevkit'/'VOC2007').iterdir())
'''
[PosixPath('data/pascal/VOCdevkit/VOC2007/JPEGImages'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/SegmentationObject'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/ImageSets'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/SegmentationClass'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/Annotations')]*JPEGS = 'VOCdevkit/VOC2007/JPEGImages'IMG_PATH = PATH/JPEGS
list(IMG_PATH.iterdir())[:5]*[PosixPath('data/pascal/VOCdevkit/VOC2007/JPEGImages/007594.jpg'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/JPEGImages/005682.jpg'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/JPEGImages/005016.jpg'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/JPEGImages/001930.jpg'),
 PosixPath('data/pascal/VOCdevkit/VOC2007/JPEGImages/007666.jpg')]
'''
```

## 创建字典（键：图像 ID，值：注释）

每个图像都有一个唯一的 ID。

```py
im0_d = trn_j[IMAGES][0]
im0_d[FILE_NAME],im0_dID
```

`defaultdict`在任何时候都很有用，当您想要为新键设置默认字典条目时。如果尝试访问不存在的键，则它会自动使其存在，并将其设置为您指定的函数的返回值（在本例中为`lambda:[]`）。

在这里，我们创建了一个从图像 ID 到注释列表（边界框和类别 ID 的元组）的字典。

我们将 VOC 的高度/宽度转换为左上角/右下角，并切换 x/y 坐标以与 numpy 保持一致。如果给定的数据集格式不佳，请花一点时间使事情保持一致，并使它们成为您想要的方式。

```py
trn_anno = collections.defaultdict(lambda:[])
for o in trn_j[ANNOTATIONS]:
    if not o['ignore']:
        bb = o[BBOX]
        bb = np.array([bb[1], bb[0], bb[3]+bb[1]-1, bb[2]+bb[0]-1])
        trn_anno[o[IMG_ID]].append((bb,o[CAT_ID]))

len(trn_anno)
'''
2501
'''
```

**变量命名，编码风格哲学等**

**示例 1**

+   `[ 96, 155, 269, 350]`：一个边界框。正如您在上面看到的，当我们创建边界框时，我们做了几件事。首先是我们交换了 x 和 y 坐标。这样做的原因是，在计算机视觉世界中，当您说“我的屏幕是 640 乘以 480”时，宽度是高度。或者，在数学世界中，当您说“我的数组是 640 乘以 480”时，是行乘以列。因此，pillow 图像库倾向于按宽度和高度或列和行进行操作，而 numpy 则相反。其次，我们将通过描述左上角 xy 坐标和右下角 xy 坐标来进行操作，而不是 x、y、高度、宽度。

+   `7`：类标签/类别

```py
im0_a = im_a[0]; im0_a
'''
[(array([96, 155, 269, 350]), 7)]
'''
im0_a = im_a[0]; im0_a
'''
(array([ 96, 155, 269, 350]), 7)
'''
cats[7]
'''
'car'
'''
```

**示例 2**

```py
trn_anno[17]
'''
[(array([61, 184, 198, 278]), 15), (array([77, 89, 335, 402]), 13)]
'''
cats[15],cats[13]
'''
('person', 'horse')
'''
```

有些库采用 VOC 格式的边界框，因此当需要时，我们可以将其转换回来：

```py
def bb_hw(a): 
    return np.array([a[1],a[0],a[3]-a[1],a[2]-a[0]])
```

我们将使用 fast.ai 的`open_image`来显示它：

```py
im = open_image(IMG_PATH/im0_d[FILE_NAME])
```

## **集成开发环境（IDE）简介**

您可以使用[Visual Studio Code](https://code.visualstudio.com/)（vscode - 附带最新版本的 Anaconda 的开源编辑器，或者可以单独安装），或者大多数编辑器和 IDE，了解有关`open_image`函数的所有信息。vscode 需要知道的事项：

+   命令面板（`Ctrl-shift-p`）

+   选择解释器（用于 fastai 环境）

+   选择终端 shell

+   转到符号（`Ctrl-t`）

+   查找引用（`Shift-F12`）

+   转到定义（`F12`）

+   返回（`alt-left`）

+   查看文档

+   隐藏侧边栏（`Ctrl-b`）

+   禅模式（`Ctrl-k,z`）

如果您像我一样在 Mac 上使用 PyCharm 专业版：

+   命令面板（`Shift-command-a`）

+   选择解释器（用于 fastai 环境）（`Shift-command-a`然后搜索“解释器”）

+   选择终端外壳（`Option-F12`）

+   转到符号（`Option-command-shift-n`并输入类名、函数名等。如果是驼峰式或下划线分隔的，您可以输入每个部分的前几个字母）

+   查找引用（`Option-F7`），下一个出现（`Option-command-⬇︎`），上一个出现（`Option-command-⬆︎`）

+   转到定义（`Command-b`）

+   返回（`Option-command-⬅︎`）

+   查看文档

+   禅模式（`Control-`-4-2`或搜索“无干扰模式”）

## 让我们谈谈 open_image [[1:10:52](https://youtu.be/Z0ssNAbe81M?t=1h10m52s)]

Fastai 使用 OpenCV。TorchVision 使用 PyTorch 张量进行数据增强等。很多人使用 Pillow `PIL`。Jeremy 对所有这些进行了大量测试，他发现 OpenCV 比 TorchVision 快 5 到 10 倍。对于[星球卫星图像竞赛](https://www.kaggle.com/c/planet-understanding-the-amazon-from-space) [[1:11:55](https://youtu.be/Z0ssNAbe81M?t=1h11m55s)]，TorchVision 非常慢，因为他们进行了大量的数据增强，只能利用 25%的 GPU 利用率。分析器显示这一切都在 TorchVision 中。

Pillow 速度相当快，但不及 OpenCV 快，也远不及线程安全[[1:12:19](https://youtu.be/Z0ssNAbe81M?t=1h12m19s)]。Python 有一个叫做全局解释器锁（GIL）的东西，这意味着两个线程不能同时执行 Pythonic 的事情 —— 这使得 Python 成为现代编程的糟糕语言，但我们却被困在其中。OpenCV 释放了 GIL。fast.ai 库之所以如此快，是因为它不像其他库那样为数据增强使用多个处理器 —— 它实际上使用多个线程。它能够使用多个线程的原因是因为它使用了 OpenCV。不幸的是，OpenCV 有一个晦涩的 API，文档有些晦涩。这就是为什么 Jeremy 试图让使用 fast.ai 的人不需要知道它正在使用 OpenCV。您不需要知道要传递哪些标志来打开一个图像。您不需要知道如果读取失败，它不会显示异常 —— 它会静默地返回`None`。

不要开始使用 PyTorch 进行数据增强或引入 Pillow —— 您会发现事情突然变得非常缓慢，或者多线程将不再起作用。您应该坚持使用 OpenCV 进行处理[[1:14:10](https://youtu.be/Z0ssNAbe81M?t=1h14m10s)]

## 更好地使用 Matplotlib [[1:14:45](https://youtu.be/Z0ssNAbe81M?t=1h14m45s)]

Matplotlib 之所以被命名为 Matplotlib，是因为它最初是 Matlab 绘图库的一个克隆。不幸的是，Matlab 的绘图库并不好，但那时候，这是每个人都知道的。在某个时候，Matplotlib 的开发人员意识到了这一点，并添加了第二个 API，即面向对象的 API。不幸的是，因为最初学习 Matplotlib 的人没有学习过 OO API，他们随后教导下一代人使用旧的 Matlab 风格 API。现在几乎没有例子或教程使用更好、更容易理解和更简单的 OO API。由于绘图在深度学习中非常重要，我们在这门课程中要学习的一件事就是如何使用这个 API。

**技巧 1：plt.subplots [**[**1:16:00**](https://youtu.be/Z0ssNAbe81M?t=1h16m)**]**

Matplotlib 的`plt.subplots`是一个非常有用的包装器，用于创建图表，无论您是否有多个子图。请注意，Matplotlib 有一个可选的面向对象的 API，我认为这个 API 更容易理解和使用（尽管在线上很少有例子使用它！）

```py
def show_img(im, figsize=None, ax=None):
    if not ax: 
        fig,ax = plt.subplots(figsize=figsize)
    ax.imshow(im)
    ax.get_xaxis().set_visible(False)
    ax.get_yaxis().set_visible(False)
    return ax
```

它返回两个东西 —— 你可能不会关心第一个（图形对象），第二个是 Axes 对象（或其数组）。基本上，你以前在哪里说 `plt.` 什么，现在你说 `ax.` 什么，它将绘制到特定的子图。当你想绘制多个图以便进行比较时，这很有帮助。

**技巧 2：无论背景颜色如何都可见的文本 [1:17:59]**

使文本在任何背景下都可见的一个简单但很少使用的技巧是使用白色文本和黑色轮廓，或者反之。这是如何在 matplotlib 中做到的。

```py
def draw_outline(o, lw):
    o.set_path_effects([
        patheffects.Stroke(linewidth=lw, foreground='black'), 
        patheffects.Normal()
    ])
```

请注意参数列表中的 `*` 是 [splat 操作符](https://stackoverflow.com/questions/5239856/foggy-on-asterisk-in-python)。在这种情况下，与写出 `b[-2],b[-1]` 相比，这是一个小快捷方式。

```py
def draw_rect(ax, b):
    patch = ax.add_patch(patches.Rectangle(
        b[:2], *b[-2:], 
        fill=False, 
        edgecolor='white', 
        lw=2
    ))
    draw_outline(patch, 4)
def draw_text(ax, xy, txt, sz=14):
    text = ax.text(
        *xy, txt, 
        verticalalignment='top', 
        color='white',
        fontsize=sz, 
        weight='bold'
    )
    draw_outline(text, 1)
    ax = show_img(im)
b = bb_hw(im0_a[0])
draw_rect(ax, b)
draw_text(ax, b[:2], cats[im0_a[1]])
```

**将所有内容打包起来 [1:21:20]**

```py
def draw_im(im, ann):
    ax = show_img(im, figsize=(16,8))
    for b,c in ann:
        b = bb_hw(b)
        draw_rect(ax, b)
        draw_text(ax, b[:2], cats[c], sz=16)
def draw_idx(i):
    im_a = trn_anno[i]
    im = open_image(IMG_PATH/trn_fns[i])
    print(im.shape)
    draw_im(im, im_a)
    draw_idx(17)
```

当你使用新数据集时，快速探索它的能力是值得的。

# 最大项目分类器 [1:22:57]

与其一次性解决所有问题，不如持续取得进展。我们知道如何找到每个图像中最大的对象并对其进行分类，所以让我们从那里开始。Jeremy 在 Kaggle 竞赛中的方法是每天半小时 [1:24:00]。在那半小时结束时，提交一些东西，并尝试比昨天稍微好一点。

我们需要做的第一件事是遍历图像中的每个边界框并获取最大的边界框。*lambda 函数* 只是一种内联定义匿名函数的方式。在这里，我们用它来描述如何对每个图像的注释进行排序 —— 按边界框大小（降序）。

我们从左上角减去右下角并乘以（`np.product`）值以获得一个面积 `lambda x: np.product(x[0][-2:]-x[0][:2])`。

```py
def get_lrg(b):
    if not b: 
        raise Exception()
    b = sorted(
        b, 
        key=lambda x: np.product(x[0][-2:]-x[0][:2]), 
        reverse=True
    )
    return b[0]
```

**字典推导式 [1:27:04]**

```py
trn_lrg_anno = {a: get_lrg(b) for a,b in trn_anno.items()}
```

现在我们有一个从图像 ID 到单个边界框的字典 —— 该图像的最大边界框。

```py
b,c = trn_lrg_anno[23]
b = bb_hw(b)
ax = show_img(open_image(IMG_PATH/trn_fns[23]), figsize=(5,10))
draw_rect(ax, b)
draw_text(ax, b[:2], cats[c], sz=16)
```

当你有任何类型的处理管道时，你需要查看每个阶段 [1:28:01]。假设你做的每件事第一次都会出错。

```py
(PATH/'tmp').mkdir(exist_ok=True)
CSV = PATH/'tmp/lrg.csv'
```

通常，最简单的方法是简单地创建要建模的数据的 CSV，而不是尝试创建自定义数据集 [1:29:06]。在这里，我们使用 Pandas 帮助我们创建一个图像文件名和类别的 CSV。`columns=[‘fn’,’cat’]` 是因为字典没有顺序，列的顺序很重要。

```py
df = pd.DataFrame({
    'fn': [trn_fns[o] for o in trn_ids],
    'cat': [cats[trn_lrg_anno[o][1]] for o in trn_ids]
}, columns=['fn','cat'])
df.to_csv(CSV, index=False)
f_model = resnet34
sz=224
bs=64
```

从这里开始就像狗与猫！

```py
tfms = tfms_from_model(
    f_model, sz, 
    aug_tfms=transforms_side_on, 
    crop_type=CropType.NO
)
md = ImageClassifierData.from_csv(PATH, JPEGS, CSV, tfms=tfms)
```

## **让我们来看看这个 [1:30:48]**

一个不同的地方是 `crop_type`。在 fast.ai 中创建 224x224 图像的默认策略是首先调整大小，使最小边为 224。然后在训练期间随机取一个正方形裁剪。在验证期间，我们取中心裁剪，除非我们使用数据增强。

对于边界框，我们不想这样做，因为与图像网不同，我们关心的东西基本上在中间且相当大，而在目标检测中，很多东西相当小且靠近边缘。通过将 `crop_type` 设置为 `CropType.NO`，它将不会裁剪，因此，为了使其成为正方形，它会压缩它 [1:32:09]。一般来说，许多计算机视觉模型在裁剪而不是压缩时效果稍好一些，但如果你压缩，它们仍然效果很好。在这种情况下，我们绝对不想裁剪，所以这是完全可以的。

```py
x,y=next(iter(md.val_dl))
show_img(md.val_ds.denorm(to_np(x))[0]);
```

## 数据加载器 [1:33:04]

您已经知道，在模型数据对象内部，我们有一堆东西，包括训练数据加载器和训练数据集。关于数据加载器的主要知识点是，它是一个迭代器，每次从中获取下一个迭代的内容时，您会得到一个小批量。您获得的小批量是您请求的任何大小，默认情况下批量大小为 64。在 Python 中，从迭代器中获取下一个内容的方法是使用`next(md.trn_dl)`，但您不能直接这样做。您不能这样说的原因是您需要说“现在开始一个新的时期”。通常情况下，不仅仅是在 PyTorch 中，对于任何 Python 迭代器，您需要说“请从序列的开头开始”。您这样做的方式是使用`iter(md.trn_dl)`，它将从`md.trn_dl`中获取一个迭代器 —— 具体来说，正如我们稍后将学到的那样，这意味着这个类必须定义一个`__iter__`方法，该方法返回一些不同的对象，然后该对象具有一个`__next__`方法。

如果您只想获取一个批次，这是您的操作方法（`x`：自变量，`y`：因变量）：

```py
x,y=next(iter(md.val_dl))
```

我们不能直接将其发送到`show_image`[[1:35:30](https://youtu.be/Z0ssNAbe81M?t=1h35m30s)]。例如，`x`不是一个 numpy 数组，不在 CPU 上，并且形状完全错误（`3x224x224`）。此外，它们不是介于 0 和 1 之间的数字，因为所有标准 ImageNet 预训练模型都期望我们的数据已经被标准化为具有零均值和 1 标准差。

正如您所看到的，对输入进行了大量处理，以便准备传递给预训练模型。因此我们有一个名为`denorm`的函数用于反标准化，还可以修复维度顺序等。由于反标准化取决于转换[[1:37:52](https://youtu.be/Z0ssNAbe81M?t=1h37m52s)]，并且数据集知道用于创建它的转换，这就是为什么您需要执行`md.val_ds.denorm`并将小批量转换为 numpy 数组后传递：

```py
show_img(md.val_ds.denorm(to_np(x))[0]);
```

## 使用 ResNet34 进行训练[[1:38:36](https://youtu.be/Z0ssNAbe81M?t=1h38m36s)]

```py
learn = ConvLearner.pretrained(f_model, md, metrics=[accuracy])
learn.opt_fn = optim.Adamlrf=learn.lr_find(1e-5,100)
learn.sched.plot()
```

我们故意删除了前几个点和最后几个点[[1:38:54](https://youtu.be/Z0ssNAbe81M?t=1h38m54s)]，因为通常最后几个点会向无穷大飙升，以至于您无法看到任何东西，所以这通常是个好主意。但是当您只有很少的小批量时，这并不是一个好主意。当您的 LR 查找器图像看起来像上面时，您可以要求在每一端获取更多点（您还可以将批量大小设置得非常小）：

```py
learn.sched.plot(n_skip=5, n_skip_end=1)
```

```py
lr = 2e-2
learn.fit(lr, 1, cycle_len=1)
'''
epoch      trn_loss   val_loss   accuracy                      
    0      1.280753   0.604127   0.806941
'''
```

解冻几层：

```py
lrs = np.array([lr/1000,lr/100,lr])
learn.freeze_to(-2)
learn.fit(lrs/5, 1, cycle_len=1)
'''
epoch      trn_loss   val_loss   accuracy                      
    0      0.780925   0.575539   0.821064
'''
```

解冻整个模型：

```py
learn.unfreeze()
learn.fit(lrs/5, 1, cycle_len=2)
'''
epoch      trn_loss   val_loss   accuracy                       
    0      0.676254   0.546998   0.834285       
    1      0.460609   0.533741   0.833233
'''
```

准确率没有太大改善 —— 由于许多图像具有多个不同的对象，要达到那么高的准确率几乎是不可能的。

## 让我们看看结果[[1:40:48](https://youtu.be/Z0ssNAbe81M?t=1h40m48s)]

```py
fig, axes = plt.subplots(3, 4, figsize=(12, 8))
for i,ax in enumerate(axes.flat):
    ima=md.val_ds.denorm(x)[i]
    b = md.classes[preds[i]]
    ax = show_img(ima, ax=ax)
    draw_text(ax, (0,0), b)
plt.tight_layout()
```

如何理解陌生的代码：

+   逐行运行代码，打印输入和输出。

**方法 1**[[1:42:28](https://youtu.be/Z0ssNAbe81M?t=1h42m28s)]：您可以获取循环的内容，复制它，创建一个在其上方的单元格，粘贴它，取消缩进，设置`i=0`并将它们放在单独的单元格中。

**方法 2**[[1:43:04](https://youtu.be/Z0ssNAbe81M?t=1h43m4s)]：使用 Python 调试器

您可以使用 Python 调试器`pdb`逐步执行代码。

+   `pdb.set_trace()`设置断点

+   `%debug`魔术以跟踪错误（在异常发生后）

您需要了解的命令：

+   `h`（帮助）

+   `s`（步入）

+   `n`（下一行/跳过 —— 您也可以按回车键）

+   `c`（继续到下一个断点）

+   `u`（向上调用堆栈）

+   `d`（向下调用堆栈）

+   `p`（打印） —— 当有一个单字母变量也是一个命令时，强制打印。

+   `l`（列出） —— 显示上面和下面的行

+   `q`（退出） —— 非常重要

**注释 [**[**1:49:10**](https://youtu.be/Z0ssNAbe81M?t=1h49m10s)**]**：`[IPython.core.debugger](http://ipython.readthedocs.io/en/stable/api/generated/IPython.core.debugger.html)`（右侧）使其看起来很漂亮：

## 创建边界框[[1:52:51](https://youtu.be/Z0ssNAbe81M?t=1h52m51s)]

围绕最大对象创建边界框可能看起来像是您以前没有做过的事情，但实际上它完全是您以前做过的事情。我们可以创建一个回归而不是分类神经网络。分类神经网络是具有 sigmoid 或 softmax 输出的神经网络，我们使用交叉熵、二元交叉熵或负对数似然损失函数。这基本上是使其成为分类器的原因。如果我们在最后没有 softmax 或 sigmoid，并且我们使用均方误差作为损失函数，那么现在它是一个预测连续数字而不是类别的回归模型。我们还知道我们可以有多个输出，就像在 planet 竞赛中一样（多分类）。如果我们将这两个想法结合起来并进行多列回归呢？

这是您考虑它像可微编程的地方。不是“我如何创建一个边界框模型？”而是更像：

+   我们需要四个数字，因此需要一个具有 4 个激活的神经网络

+   对于损失函数，什么样的函数在较低时意味着这四个数字更好？均方损失函数！

就是这样。让我们试试看。

## Bbox only [[1:55:27](https://youtu.be/Z0ssNAbe81M?t=1h55m27s)]

现在我们将尝试找到最大对象的边界框。这只是一个具有 4 个输出的回归。因此，我们可以使用具有多个“标签”的 CSV。如果您还记得第 1 部分如何进行多标签分类，您的多个标签必须以空格分隔，并且文件名以逗号分隔。

```py
BB_CSV = PATH/'tmp/bb.csv'
bb = np.array([trn_lrg_anno[o][0] for o in trn_ids])
bbs = [' '.join(str(p) for p in o) for o in bb]
df = pd.DataFrame({
    'fn': [trn_fns[o] for o in trn_ids], 
    'bbox': bbs
}, columns=['fn','bbox'])
df.to_csv(BB_CSV, index=False)
BB_CSV.open().readlines()[:5]
'''
['fn,bbox\n',
 '000012.jpg,96 155 269 350\n',
 '000017.jpg,77 89 335 402\n',
 '000023.jpg,1 2 461 242\n',
 '000026.jpg,124 89 211 336\n']
'''
```

## Training [[1:56:11](https://youtu.be/Z0ssNAbe81M?t=1h56m11s)]

```py
f_model=resnet34
sz=224
bs=64
```

将`continuous=True`设置为告诉 fastai 这是一个回归问题，这意味着它不会对标签进行独热编码，并且将使用 MSE 作为默认的 crit。

请注意，我们必须告诉 transforms 构造函数我们的标签是坐标，以便它可以正确处理 transforms。

此外，我们使用 CropType.NO，因为我们希望将矩形图像“压缩”成正方形，而不是中心裁剪，以免意外裁剪掉一些对象。（在像 imagenet 这样的情况下，这不是太大的问题，因为有一个要分类的单个对象，通常很大且位于中心位置）。

```py
tfms = tfms_from_model(
    f_model, sz, 
    crop_type=CropType.NO, 
    tfm_y=TfmType.COORD
)
md = ImageClassifierData.from_csv(
    PATH, JPEGS, BB_CSV, 
    tfms=tfms, 
    continuous=True
)
```

下周我们将看一下`TfmType.COORD`，但现在，只需意识到当我们进行缩放和数据增强时，需要对边界框进行操作，而不仅仅是图像。

```py
x,y=next(iter(md.val_dl))ima=md.val_ds.denorm(to_np(x))[0]
b = bb_hw(to_np(y[0])); b
'''
array([  49.,    0.,  131.,  205.], dtype=float32)
'''
ax = show_img(ima)
draw_rect(ax, b)
draw_text(ax, b[:2], 'label')
```

## 让我们基于 ResNet34 创建一个卷积网络[[1:56:57](https://youtu.be/Z0ssNAbe81M?t=1h56m57s)]：

fastai 允许您使用`custom_head`在卷积网络的顶部添加自己的模块，而不是默认添加的自适应池化和全连接网络。在这种情况下，我们不想进行任何池化，因为我们需要知道每个网格单元的激活。

最终层有 4 个激活，每个激活对应一个边界框坐标。我们的目标是连续的，而不是分类的，因此使用的 MSE 损失函数不会对模块输出进行任何 sigmoid 或 softmax 处理。

```py
head_reg4 = nn.Sequential(Flatten(), nn.Linear(25088,4))
learn = ConvLearner.pretrained(f_model, md, custom_head=head_reg4)
learn.opt_fn = optim.Adam
learn.crit = nn.L1Loss()
```

+   `Flatten()`：通常在 ResNet34 中，前一层具有`7x7x512`，因此将其展平为长度为 2508 的单个向量。

+   `L1Loss`[[1:58:22](https://youtu.be/Z0ssNAbe81M?t=1h58m22s)]：不是将平方误差相加，而是将误差的绝对值相加。这通常是您想要的，因为将平方误差相加会过度惩罚错误。因此，L1Loss 通常更好地处理。

```py
learn.lr_find(1e-5,100)
learn.sched.plot(5)78%|███████▊  | 25/32 [00:04<00:01,  6.16it/s, loss=395]
```

```py
lr = 2e-3
learn.fit(lr, 2, cycle_len=1, cycle_mult=2)
'''
epoch      trn_loss   val_loss                            
    0      49.523444  34.764141 
    1      36.864003  28.007317                           
    2      30.925234  27.230705
'''
lrs = np.array([lr/100,lr/10,lr])
learn.freeze_to(-2)
lrf=learn.lr_find(lrs/1000)
learn.sched.plot(1)
```

```py
learn.fit(lrs, 2, cycle_len=1, cycle_mult=2)
'''
epoch      trn_loss   val_loss                            
    0      25.616161  22.83597  
    1      21.812624  21.387115                           
    2      17.867176  20.335539
'''
learn.freeze_to(-3)
learn.fit(lrs, 1, cycle_len=2)
'''
epoch      trn_loss   val_loss                            
    0      16.571885  20.948696 
    1      15.072718  19.925312
'''
```

验证损失是绝对值的平均值，像素偏离了。

```py
learn.save('reg4')
```

## 看一下结果[[1:59:18](https://youtu.be/Z0ssNAbe81M?t=1h59m18s)]

```py
x,y = next(iter(md.val_dl))
learn.model.eval()
preds = to_np(learn.model(VV(x)))
fig, axes = plt.subplots(3, 4, figsize=(12, 8))
for i,ax in enumerate(axes.flat):
    ima=md.val_ds.denorm(to_np(x))[i]
    b = bb_hw(preds[i])
    ax = show_img(ima, ax=ax)
    draw_rect(ax, b)
plt.tight_layout()
```

我们将在下周进一步修改这个。在这堂课之前，如果有人问你“你知道如何创建一个边界框模型吗？”，你可能会说“不，没有人教过我”。但实际上问题是：

+   您可以创建一个具有 4 个连续输出的模型吗？可以。

+   您能否创建一个损失函数，如果这 4 个输出接近另外 4 个数字，则较低？可以

然后你就完成了。

当你继续往下看时，它开始看起来有点糟糕 - 每当我们有多个对象时。这并不奇怪。总的来说，它做得相当不错。
