# 斯坦福 CS231n 课程作业# 3 简介

> 来源：[`zhuanlan.zhihu.com/p/20870307`](https://zhuanlan.zhihu.com/p/21946525)

译者注：本文[智能单元](https://zhuanlan.zhihu.com/intelligentunit)首发，由@[杜客](https://www.zhihu.com/people/du-ke)翻译自斯坦福 CS231n 课程作业 1 介绍页面[[Assignment #2]](https://link.zhihu.com/?target=http%3A//cs231n.github.io/assignments2016/assignment2/)*。

## 原文如下

在本作业中，你将实现循环网络，并将其应用于在微软的 COCO 数据库上进行图像标注。我们还会介绍 TinyImageNet 数据集，然后在这个数据集使用一个预训练的模型来查看图像梯度的不同应用。本作业的目标如下：

*   理解*循环神经网络（RNN）*的结构，知道它们是如何随时间共享权重来对序列进行操作的。
*   理解普通循环神经网络和长短基记忆（Long-Short Term Memory）循环神经网络之间的差异。
*   理解在测试时如何从 RNN 生成序列。
*   理解如何将卷积神经网络和循环神经网络结合在一起来实现图像标注。
*   理解一个训练过的卷积神经网络是如何用来从输入图像中计算梯度的。
*   进行高效的交叉验证并为神经网络结构找到最好的超参数。
*   实现图像梯度的不同应用，比如显著图，搞笑图像，类别可视化，特征反演和 DeepDream。

## 安装

有两种方法来完成作业：在本地使用自己的机器，或者使用[`Terminal.com`](https://link.zhihu.com/?target=http%3A//Terminal.com)*的虚拟机。* 

### 云端作业

Terminal 公司为我们的课程创建了一个单独的子域名：[www.stanfordterminalcloud.com](https://link.zhihu.com/?target=https%3A//www.stanfordterminalcloud.com/)*。在该域名下注册。作业 2 的快照可以在[这里](https://link.zhihu.com/?target=https%3A//www.stanfordterminalcloud.com/snapshot/49f5a1ea15dc424aec19155b3398784d57c55045435315ce4f8b96b62819ef65)*找到。如果你注册到了本课程，就可以联系上助教（更多信息请上 Piazza）来得到用来做作业的点数。一旦你启动了快照，所有的环境都是为你配置好的，马上就可以开始作业。我们在 Terminal 上写了一个简明[教程](https://link.zhihu.com/?target=http%3A//cs231n.github.io/terminal-tutorial/)*。*** 

### 本地作业

点击[此处](https://link.zhihu.com/?target=http%3A//cs231n.stanford.edu/winter1516_assignment3.zip)*下载代码压缩文件。初次之外还有些库间依赖的配置：*

 ***[选项 1]使用 Anaconda**：推荐方法是安装[Anaconda](https://link.zhihu.com/?target=https%3A//www.continuum.io/downloads)*，它是 Python 的一个发布版，包含了最流行的科研、数学、工程和数据分析 Python 包。一旦安装了它，下面的提示就都可略过，准备直接开始写作业吧。*译者注：推荐。**

 ***[选项 2]手动安装，虚拟环境**：如果你不想用 Anaconda，想要走一个充满风险的手动安装路径，那么可能就要为项目创建一个[虚拟环境](https://link.zhihu.com/?target=http%3A//docs.python-guide.org/en/latest/dev/virtualenvs/)*了。如果你不想用虚拟环境，那么你的确保所有代码需要的依赖关系都是景在你的机器上被安装了。要建立虚拟环境，运行下面代码：*

 *```py
cd assignment3
sudo pip install virtualenv      # This may already be installed
virtualenv .env                  # Create a virtual environment
source .env/bin/activate         # Activate the virtual environment
pip install -r requirements.txt  # Install dependencies
# Work on the assignment for a while ...
deactivate                       # Exit the virtual environment 
```

**下载数据**：一旦得到作业初始代码，你就需要下载 CIFAR-10 数据集，然后在 assignment1 目录下运行下面代码：*译者注：也可手动下载解压后放到**cs231n/datasets 目录**。*

```py
cd cs231n/datasets 
./get_coco_captioning.sh
./get_tiny_imagenet_a.sh
./get_pretrained_model.sh 
```

**编译 Cython 扩展包**：卷积神经网络需要一个高效的实现。我们使用[Cython](https://link.zhihu.com/?target=http%3A//cython.org/)*实现了一些函数。在运行代码前，你需要编译 Cython 扩展包。在 cs231n 目录下，运行下面命令：*

 *```py
python setup.py build_ext --inplace 
```

**启用 IPython**：得到了 CIFAR-10 数据集之后，你应该在作业 assignment1 目录中启用 IPython notebook 的服务器，如果对 IPython notebook 不熟悉，可以阅读[教程](https://link.zhihu.com/?target=http%3A//cs231n.github.io/ipython-tutorial)*。* 

 ***注意**：如果你是在 OSX 上的虚拟环境中工作，可能会遇到一个由 matplotlib 导致的错误，原因在[这里](https://link.zhihu.com/?target=http%3A//matplotlib.org/faq/virtualenv_faq.html)*。你可以通过在 assignment2 目录中运行 start_ipython_osx.sh 脚本来解决问题。*

## 提交作业

无论你是在云终端还是在本地完成作业，一旦完成作业，就运行 collectSubmission.sh 脚本；这样将会产生一个 assignment3.zip 的文件，然后将这个文件上传到你的 dropbox 中这门课的[作业页面](https://link.zhihu.com/?target=https%3A//coursework.stanford.edu/portal/site/W15-CS-231N-01/)*。*

### Q1：使用普通 RNN 进行图像标注（40 分）

IPython Notebook 文件**RNN_Captioning.ipynb**将会带你使用普通 RNN 实现一个在微软 COCO 数据集上的图像标注系统。

### Q2：使用 LSTM 进行图像标注（35 分）

IPython Notebook 文件**LSTM_Captioning.ipynb**将会带你实现 LSTM，并应用于在微软 COCO 数据集上进行图像标注。

### Q3：图像梯度：显著图和高效图像（10 分）

IPython Notebook 文件**ImageGradients.ipynb**将会介绍 TinyImageNet 数据集。你将使用一个训练好的模型在这个数据集上计算梯度，然后将其用于生成显著图和高效图像。

### Q4：图像生成：类别，反演和 DeepDream（30 分）

在 IPython Notebook 文件**ImageGeneration.ipynb**中，你将使用一个训练好的 TinyImageNet 模型来生成图像。具体说来，你将生成类别可视化，实现特征反演和 DeepDream。

### Q5：做点儿其他的！（+10 分）

根据作业内容，做点够酷的事儿。比如作业中没有讲过的其他生成图像的方式？

**全文完。**

## 译者反馈：

1.  转载须全文转载并注明原文链接，否则保留维权权利；

2.  如对翻译有意见建议，请通过评论批评指正，贡献者均会补充提及；
3.  后续将根据作业内容和自己的学习笔记原创教程；
4.  感谢[@Frankenstein](https://www.zhihu.com/people/f38193bc2f7f3c10c55042d009b411a5)的纠错。************