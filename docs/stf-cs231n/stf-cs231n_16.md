# 斯坦福 CS231n 课程作业# 2 简介

> 来源：[`zhuanlan.zhihu.com/p/20870307`](https://zhuanlan.zhihu.com/p/21941485)

译者注：本文[智能单元](https://zhuanlan.zhihu.com/intelligentunit)首发，由@[杜客](https://www.zhihu.com/people/du-ke)翻译自斯坦福 CS231n 课程作业 1 介绍页面[[Assignment #2]](https://link.zhihu.com/?target=http%3A//cs231n.github.io/assignments2016/assignment2/)*。

## 原文如下

在本作业中，你将练习编写反向传播代码，训练神经网络和卷积神经网络。本作业的目标如下：

*   理解**神经网络**及其分层结构。
*   理解并实现（向量化）**反向传播**。
*   实现多个用于神经网络最优化的**更新方法**。
*   实现用于训练深度网络的**批量归一化**（ **batch normalization** ）。
*   实现**随机失活**（**dropout**）。
*   进行高效的**交叉验证**并为神经网络结构找到最好的超参数。
*   理解**卷积神经网络**的结构，并积累在数据集上训练此类模型的经验。

## 安装

有两种方法来完成作业：在本地使用自己的机器，或者使用[`Terminal.com`](https://link.zhihu.com/?target=http%3A//Terminal.com)*的虚拟机。* 

### 云端作业

Terminal 公司为我们的课程创建了一个单独的子域名：[www.stanfordterminalcloud.com](https://link.zhihu.com/?target=https%3A//www.stanfordterminalcloud.com/)*。在该域名下注册。作业 2 的快照可以在[这里](https://link.zhihu.com/?target=https%3A//www.stanfordterminalcloud.com/snapshot/49f5a1ea15dc424aec19155b3398784d57c55045435315ce4f8b96b62819ef65)*找到。如果你注册到了本课程，就可以联系上助教（更多信息请上 Piazza）来得到用来做作业的点数。一旦你启动了快照，所有的环境都是为你配置好的，马上就可以开始作业。我们在 Terminal 上写了一个简明[教程](https://link.zhihu.com/?target=http%3A//cs231n.github.io/terminal-tutorial/)*。*** 

### 本地作业

点击[此处](https://link.zhihu.com/?target=http%3A//vision.stanford.edu/teaching/cs231n/winter1516_assignment2.zip)*下载代码压缩文件。初次之外还有些库间依赖的配置：*

 ***[选项 1]使用 Anaconda**：推荐方法是安装[Anaconda](https://link.zhihu.com/?target=https%3A//www.continuum.io/downloads)*，它是 Python 的一个发布版，包含了最流行的科研、数学、工程和数据分析 Python 包。一旦安装了它，下面的提示就都可略过，准备直接开始写作业吧。***译者注：推荐。****

 ***[选项 2]手动安装，虚拟环境**：如果你不想用 Anaconda，想要走一个充满风险的手动安装路径，那么可能就要为项目创建一个[虚拟环境](https://link.zhihu.com/?target=http%3A//docs.python-guide.org/en/latest/dev/virtualenvs/)*了。如果你不想用虚拟环境，那么你的确保所有代码需要的依赖关系都是景在你的机器上被安装了。要建立虚拟环境，运行下面代码：*

 *```py
cd assignment2
sudo pip install virtualenv      # This may already be installed
virtualenv .env                  # Create a virtual environment
source .env/bin/activate         # Activate the virtual environment
pip install -r requirements.txt  # Install dependencies
# Work on the assignment for a while ...
deactivate                       # Exit the virtual environment 
```

**下载数据**：一旦得到作业初始代码，你就需要下载 CIFAR-10 数据集，然后在**assignment1**目录下运行下面代码：***译者注：也可手动下载解压后放到******cs231n/datasets 目录******。***

```py
cd cs231n/datasets 
./get_datasets.sh 
```

**编译 Cython 扩展包：**卷积神经网络需要一个高效的实现。我们使用[Cython](https://link.zhihu.com/?target=http%3A//cython.org/)*实现了一些函数。在运行代码前，你需要编译 Cython 扩展包。在**cs231n**目录下，运行下面命令：*

 *```py
python setup.py build_ext --inplace 
```

**启用 IPython**：得到了 CIFAR-10 数据集之后，你应该在作业**assignment1**目录中启用 IPython notebook 的服务器，如果对 IPython notebook 不熟悉，可以阅读[教程](https://link.zhihu.com/?target=http%3A//cs231n.github.io/ipython-tutorial)*。* 

 ***注意**：如果你是在 OSX 上的虚拟环境中工作，可能会遇到一个由**matplotlib**导致的错误，原因在[这里](https://link.zhihu.com/?target=http%3A//matplotlib.org/faq/virtualenv_faq.html)*。你可以通过在**assignment2**目录中运行**start_ipython_osx.sh**脚本来解决问题。*

## 提交作业

无论你是在云终端还是在本地完成作业，一旦完成作业，就运行**collectSubmission.sh**脚本；这样将会产生一个**assignment2.zip**的文件，然后将这个文件上传到你的 dropbox 中这门课的[作业页面](https://link.zhihu.com/?target=https%3A//coursework.stanford.edu/portal/site/W15-CS-231N-01/)*。*

### Q1：全连接神经网络（30 分）

IPython Notebook 文件**FullyConnectedNets****.ipynb**将会向你介绍我们的模块化设计，然后使用不同的层来构建任意深度的全连接网络。为了对模型进行最优化，还需要实现几个常用的更新方法。

### Q2：批量归一化（30 分）

在 IPython Notebook 文件**BatchNormalization.ipynb**中，你需要实现批量归一化，然后将其应用于深度全连接网络的训练中。

### Q3：随机失活（Dropout）（10 分）

IPython Notebook 文件**Dropout.ipynb**将会帮助你需要实现随机失活，然后在模型泛化中检查它的效果。

### Q4：在 CIFAR-10 上运行卷积神经网络（30 分）

在 IPython Notebook 文件**ConvolutionalNetworks.ipynb**中，你将实现几个卷积神经网络中常用的新的层。你将在 CIFAR-10 上训练一个深度较浅的卷积神经网络，然后由你决定竭尽所能地训练处一个最好网络。

### Q5：做点儿其他的！（+10 分）

在训练网络的过程中，为了得到更好的结果，你可以自由实现任何想法。你可以修改训练器（solver），实现额外的层，使用不同的正则化方法，使用模型集成，或者任何其它你想到的东西。如果你实现了作业要求以外的内容，那么将得到加分。

**全文完。**

## 译者反馈：

1.  转载须全文转载并注明原文链接，否则保留维权权利；

2.  如对翻译有意见建议，请通过评论批评指正，贡献者均会补充提及；
3.  后续将根据作业内容和自己的学习笔记原创教程。************