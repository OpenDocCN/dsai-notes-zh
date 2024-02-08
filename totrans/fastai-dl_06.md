# 深度学习 2：第 1 部分第 6 课

> 原文：[`medium.com/@hiromi_suenaga/deep-learning-2-part-1-lesson-6-de70d626976c`](https://medium.com/@hiromi_suenaga/deep-learning-2-part-1-lesson-6-de70d626976c)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](http://creativecommons.org/licenses/by-nc-sa/4.0/)

*我从* [*fast.ai 课程*](http://www.fast.ai/)*中的个人笔记。这些笔记将继续更新和改进，因为我继续复习这门课程以“真正”理解它。非常感谢* [*Jeremy*](https://twitter.com/jeremyphoward) *和* [*Rachel*](https://twitter.com/math_rachel) *给了我这个学习的机会。*

# [第 6 课](http://forums.fast.ai/t/wiki-lesson-6/9404)

[## 2017 年深度学习优化的亮点

### 目录：深度学习最终是关于找到一个很好泛化的最小值--附加分为...

ruder.io](http://ruder.io/deep-learning-optimization-2017/index.html?source=post_page-----de70d626976c--------------------------------)

上周的回顾[[2:15](https://youtu.be/sHcLkfRrgoQ?t=2m15s)]

上周我们深入研究了协同过滤，最终在 fast.ai 库中重新创建了`EmbeddingDotBias`类（`column_data.py`）。让我们看看嵌入是什么样子的[[笔记本](https://github.com/fastai/fastai/blob/master/courses/dl1/lesson5-movielens.ipynb)]。

在一个学习者`learn`内部，通过调用`learn.model`可以获得一个 PyTorch 模型本身。`@property`看起来像一个普通的函数，但当你调用它时不需要括号。

```py
@property
def model(self): 
    return self.models.model
```

`learn.models`是`CollabFilterModel`的一个实例，它是 PyTorch 模型的一个薄包装，允许我们使用“层组”，这是 PyTorch 中没有的概念，fast.ai 使用它来对不同的层组应用不同的学习率。

PyTorch 模型很好地打印出层，包括层名称，这就是我们在代码中称呼它们的方式。

```py
m=learn.model; m
'''
EmbeddingDotBias (
  (u): Embedding(671, 50)
  (i): Embedding(9066, 50)
  (ub): Embedding(671, 1)
  (ib): Embedding(9066, 1)
)
'''
```

`m.ib`指的是一个项目偏差的嵌入层--在我们的例子中是电影偏差。PyTorch 模型和层的好处是我们可以像调用函数一样调用它们。所以如果你想得到一个预测，你调用`m(...)`并传入变量。

层需要变量而不是张量，因为它需要跟踪导数--这就是`V(...)`将张量转换为变量的原因。PyTorch 0.4 将摆脱变量，我们将能够直接使用张量。

```py
movie_bias = to_np(m.ib(V(topMovieIdx)))
```

`to_np`函数将获取一个变量或张量（无论是在 CPU 还是 GPU 上）并返回一个 numpy 数组。Jeremy 的方法[[12:03](https://youtu.be/sHcLkfRrgoQ?t=12m3s)]是除了在他明确需要在 GPU 上运行的时候或者需要它的导数时使用 PyTorch 外，其他情况下都使用 numpy。Numpy 比 PyTorch 存在的时间更长，与其他库如 OpenCV、Pandas 等很好地配合。

关于生产中的 CPU vs. GPU 的问题。建议的方法是在 CPU 上进行推断，因为它更具可扩展性，而且你不需要将事物放入批处理中。你可以通过键入`m.cpu()`将模型移动到 CPU 上，类似地，通过键入`V(topMovieIndex).cpu()`将变量移动到 CPU 上（从 CPU 到 GPU 的操作是`m.cuda()`）。如果你的服务器没有 GPU，它将自动在 CPU 上运行推断。要加载在 GPU 上训练的保存模型，请查看`torch_imports.py`中的这行代码：

```py
def load_model(m, p): 
    m.load_state_dict(torch.load(p, map_location=lambda storage, loc: storage))
```

现在我们有了前 3000 部电影的电影偏差，让我们来看一下评分：

```py
movie_ratings = [(b[0], movie_names[i]) for i,b in zip(topMovies,movie_bias)]
```

`zip`将允许你同时迭代多个列表。

## 最差的电影

关于排序键--Python 有`itemgetter`函数，但普通的`lambda`只是多了一个字符。

```py
sorted(movie_ratings, key=lambda o: o[0])[:15]
'''
[(-0.96070349, 'Battlefield Earth (2000)'),
 (-0.76858485, 'Speed 2: Cruise Control (1997)'),
 (-0.73675376, 'Wild Wild West (1999)'),
 (-0.73655486, 'Anaconda (1997)'),
 ...]
'''
sorted(movie_ratings, key=itemgetter(0))[:15]
```

## 最佳电影

```py
sorted(movie_ratings, key=lambda o: o[0], reverse=True)[:15]
'''
[(1.3070084, 'Shawshank Redemption, The (1994)'),
 (1.1196285, 'Godfather, The (1972)'),
 (1.0844109, 'Usual Suspects, The (1995)'),
 (0.96578616, "Schindler's List (1993)"),
 ...]
'''
```

## 嵌入解释[[18:42](https://youtu.be/sHcLkfRrgoQ?t=18m42s)]

每部电影有 50 个嵌入，很难可视化 50 维空间，所以我们将其转换为三维空间。我们可以使用几种技术来压缩维度：主成分分析（PCA）（Rachel 的计算线性代数课程详细介绍了这一点——几乎与奇异值分解（SVD）相同）

```py
movie_emb = to_np(m.i(V(topMovieIdx)))
movie_emb.shape*(3000, 50)
from sklearn.decomposition import PCA
pca = PCA(n_components=3)
movie_pca = pca.fit(movie_emb.T).components_
movie_pca.shape
'''
(3, 3000)
'''
```

我们将看一下第一个维度“轻松观看 vs. 严肃”（我们不知道它代表什么，但可以通过观察来推测）：

```py
fac0 = movie_pca[0] 
movie_comp = [(f, movie_names[i]) for f,i in zip(fac0, topMovies)]
sorted(movie_comp, key=itemgetter(0), reverse=True)[:10]
sorted(movie_comp, key=itemgetter(0), reverse=True)[:10]
'''
[(0.06748189, 'Independence Day (a.k.a. ID4) (1996)'),
 (0.061572548, 'Police Academy 4: Citizens on Patrol (1987)'),
 (0.061050549, 'Waterworld (1995)'),
 (0.057877172, 'Rocky V (1990)'),
 ...
]
'''
sorted(movie_comp, key=itemgetter(0))[:10]
'''
[(-0.078433245, 'Godfather: Part II, The (1974)'),
 (-0.072180331, 'Fargo (1996)'),
 (-0.071351372, 'Pulp Fiction (1994)'),
 (-0.068537779, 'Goodfellas (1990)'),
 ...
]
'''
```

第二个维度“对话驱动 vs. CGI”

```py
fac1 = movie_pca[1]
movie_comp = [(f, movie_names[i]) for f,i in zip(fac1, topMovies)]
sorted(movie_comp, key=itemgetter(0), reverse=True)[:10]
'''
[(0.058975246, 'Bonfire of the Vanities (1990)'),
 (0.055992026, '2001: A Space Odyssey (1968)'),
 (0.054682467, 'Tank Girl (1995)'),
 (0.054429606, 'Purple Rose of Cairo, The (1985)'),
 ...]*sorted(movie_comp, key=itemgetter(0))[:10]*[(-0.1064609, 'Lord of the Rings: The Return of the King, The (2003)'),
 (-0.090635143, 'Aladdin (1992)'),
 (-0.089208141, 'Star Wars: Episode V - The Empire Strikes Back (1980)'),
 (-0.088854566, 'Star Wars: Episode IV - A New Hope (1977)'),
 ...]
'''
```

绘图

```py
idxs = np.random.choice(len(topMovies), 50, replace=False)
X = fac0[idxs]
Y = fac1[idxs]
plt.figure(figsize=(15,15))
plt.scatter(X, Y)
for i, x, y in zip(topMovies[idxs], X, Y):
    plt.text(x,y,movie_names[i], color=np.random.rand(3)*0.7, fontsize=11)
plt.show()
```

当你说`learn.fit`时实际发生了什么？

## [分类变量的实体嵌入](https://arxiv.org/pdf/1604.06737.pdf) [[24:42](https://youtu.be/sHcLkfRrgoQ?t=24m42s)]

第二篇论文讨论了分类嵌入。图 1 的标题应该听起来很熟悉，因为它们讨论了实体嵌入层等效于一个独热编码后跟着一个矩阵乘法。

他们做的有趣的事情是，他们用神经网络训练的实体嵌入替换了每个分类变量，然后将其输入到梯度提升机（GBM）、随机森林（RF）和 KNN 中——这将误差降低到几乎与神经网络（NN）一样好。这是一个很好的方法，可以在组织内提供神经网络的能力，而不需要强迫其他人学习深度学习，因为他们可以继续使用他们目前使用的东西，并将嵌入作为输入。GBM 和 RF 的训练速度比 NN 快得多。

他们还绘制了德国各州的嵌入，有趣的是（正如 Jeremy 所说的那样）它们与实际地图相似。

他们还绘制了实体在物理空间和嵌入空间中的距离——显示了一个美丽而清晰的相关性。

星期几或一年中的月份之间似乎也存在相关性。可视化嵌入可能很有趣，因为它向你展示了你期望看到的或者你没有预料到的内容。

## 关于 Skip-Gram 生成嵌入的问题 [[31:31](https://youtu.be/sHcLkfRrgoQ?t=31m31s)]

Skip-Gram 是特定于 NLP 的。将一个无标签的问题转化为有标签的问题的一个好方法是“发明”标签。Word2Vec 的方法是取一个包含 11 个单词的句子，删除中间的单词，然后用一个随机单词替换它。然后他们给原始句子一个标签 1；虚假句子一个标签 0，并构建一个机器学习模型来找出虚假句子。结果，他们现在有了可以用于其他目的的嵌入。如果你将这个作为一个单一的矩阵乘法器（浅层模型）而不是深度神经网络来训练，你可以训练得非常快速——缺点是这是一个预测性较差的模型，但优点是你可以在一个非常大的数据集上训练，更重要的是，所得到的嵌入具有*线性特征*，这使我们可以很好地进行加减或绘制。在 NLP 中，我们应该超越 Word2Vec 和 Glove（即基于线性的方法），因为这些嵌入的预测性较差。最先进的语言模型使用深度 RNN。

## 要学习任何类型的特征空间，你要么需要有标记的数据，要么需要发明一个虚假任务 [[35:45](https://youtu.be/sHcLkfRrgoQ?t=35m45s)]

+   一个虚假任务比另一个更好吗？尚未研究清楚。

+   直觉上，我们希望有一个任务可以帮助机器学习你关心的关系类型。

+   在计算机视觉中，人们使用一种虚假任务的类型是应用不真实和不合理的数据增强。

+   如果你想不出很好的虚假任务，只需使用糟糕的任务——令人惊讶的是你需要的很少。

+   **自动编码器** - 它最近赢得了一场[保险索赔竞赛](https://www.kaggle.com/c/porto-seguro-safe-driver-prediction/discussion/44629)。拿一个单一的政策，通过神经网络运行它，并让它重建自己（确保中间层的激活少于输入变量）。基本上，这是一个输入=输出的任务，作为一个虚假任务效果惊人。

在计算机视觉中，您可以训练猫和狗，并将其用于 CT 扫描。也许它对语言/NLP 也有效！（未来研究）

## [Rossmann](https://github.com/fastai/fastai/blob/master/courses/dl1/lesson3-rossman.ipynb)

+   笔记本中添加了正确使用测试集的方法。

+   有关更详细的解释，请参见机器学习课程。

+   `apply_cats(joined_test, joined)` 用于确保测试集和训练集具有相同的分类代码。

+   跟踪包含每个连续列的均值和标准差的`mapper`，并将相同的`mapper`应用于测试集。

+   不要依赖 Kaggle 公共板块 - 依赖您自己精心创建的验证集。

## 查看 Rossmann 的一个好的[Kernel](https://www.kaggle.com/thie1e/exploratory-analysis-rossmann)

+   周日对销售的影响

在店铺关闭前后销售有所增长。第三名获奖者在开始任何分析之前删除了关闭的店铺行。

> **除非您首先分析以确保您所做的是正确的 - 不要触碰您的数据。**

## Vim 技巧

+   `:tag ColumnarModelData`将带您到类定义处

+   `ctrl + ]`将带您到光标下的定义

+   `ctrl + t`返回

+   `*`查找光标下的内容的用法

+   您可以使用`:tabn`和`:tabp`在选项卡之间切换，使用`:tabe <filepath>`可以添加一个新选项卡；使用常规的`:q`或`:wq`关闭一个选项卡。如果将`:tabn`和`:tabp`映射到 F7/F8 键，您可以轻松地在文件之间切换。

## 在 ColumnarModelData 内部

慢慢地，曾经只是“魔术”的东西开始变得熟悉起来。正如您所看到的，`get_learner`返回`Learner`，这是 fast.ai 概念，它包装了数据和 PyTorch 模型：

在`MixedInputModel`内部，您可以看到它是如何创建我们现在更多了解的`Embedding`的。`nn.ModuleList`用于注册一系列层。我们将在下周讨论`BatchNorm`，但是其他部分，我们之前已经见过。

同样，我们现在了解了`forward`函数中发生的事情。

+   使用第*i*个分类变量调用嵌入层，并将它们全部连接在一起

+   通过 dropout 处理

+   逐个遍历我们的线性层，称之为，应用 relu 和 dropout

+   然后最终的线性层大小为 1

+   如果传入`y_range`，则应用 sigmoid 并将输出拟合在一个范围内（我们上周学到的）

## [随机梯度下降 - SGD](https://github.com/fastai/fastai/blob/master/courses/dl1/lesson6-sgd.ipynb)

为了确保我们完全熟悉 SGD，我们将使用它来学习`*y = ax + b*`。如果我们可以用 2 个参数解决问题，我们可以使用相同的技术来解决 1 亿个参数。

```py
# Here we generate some fake data
def lin(a,b,x): 
    return a*x+b

def gen_fake_data(n, a, b):
    x = s = np.random.uniform(0,1,n) 
    y = lin(a,b,x) + 0.1 * np.random.normal(0,3,n)
    return x, y

x, y = gen_fake_data(50, 3., 8.)

plt.scatter(x,y, s=8); plt.xlabel("x"); plt.ylabel("y");
```

要开始，我们需要一个损失函数。这是一个回归问题，因为输出是连续输出，最常见的损失函数是均方误差（MSE）。

> 回归 - 目标输出是一个实数或一整个实数向量
> 
> 分类 - 目标输出是一个类标签

```py
def mse(y_hat, y): 
    return ((y_hat - y) ** 2).mean()
def mse_loss(a, b, x, y): 
    return mse(lin(a,b,x), y)
```

+   `y_hat` - 预测

我们将创建 10,000 个更多的虚假数据，并将它们转换为 PyTorch 变量，因为 Jeremy 不喜欢求导，PyTorch 可以为他做到这一点：

```py
x, y = gen_fake_data(10000, 3., 8.) 
x,y = V(x),V(y)
```

然后为`a`和`b`创建随机权重，它们是我们想要学习的变量，因此设置`requires_grad=True`。

```py
a = V(np.random.randn(1), requires_grad=True) 
b = V(np.random.randn(1), requires_grad=True)
```

然后设置学习率，并进行 10000 个完全梯度下降的周期（不是 SGD，因为每个周期将查看所有数据）：

```py
learning_rate = 1e-3
for t in range(10000):
    # Forward pass: compute predicted y using operations on Variables
    loss = mse_loss(a,b,x,y)
    if t % 1000 == 0: print(loss.data[0])

    # Computes the gradient of loss with respect to all Variables with requires_grad=True.
    # After this call a.grad and b.grad will be Variables holding the gradient
    # of the loss with respect to a and b respectively
    loss.backward()

    # Update a and b using gradient descent; a.data and b.data are Tensors,
    # a.grad and b.grad are Variables and a.grad.data and b.grad.data are Tensors
    a.data -= learning_rate * a.grad.data
    b.data -= learning_rate * b.grad.data

    # Zero the gradients
    a.grad.data.zero_()
    b.grad.data.zero_()
```

+   计算损失（记住，`a`和`b`最初是随机设置的）

+   偶尔（每 1000 个周期）打印出损失

+   `loss.backward()`将计算所有`requires_grad=True`的变量的梯度，并填充`.grad`属性

+   将`a`更新为原来的值减去 LR * `grad`（`.data`访问变量内的张量）

+   当有多个损失函数或许多输出层对梯度有贡献时，PyTorch 会将它们相加。所以你需要告诉何时将梯度设置回零（`zero_()`中的`_`表示变量是原地更改的）。

+   代码的最后 4 行是包含在`optim.SGD.step`函数中的内容

## 让我们只用 Numpy（不用 PyTorch）来做这个[[1:07:01](https://youtu.be/sHcLkfRrgoQ?t=1h7m1s)]

我们实际上需要做微积分，但其他方面应该看起来类似：

```py
x, y = gen_fake_data(50, 3., 8.)
a_guess,b_guess = -1., 1.
mse_loss(y, a_guess, b_guess, x)
lr=0.01 
def upd():
     global a_guess, b_guess
     y_pred = lin(a_guess, b_guess, x)
     dydb = 2 * (y_pred - y)
     dyda = x*dydb
     a_guess -= lr*dyda.mean()
     b_guess -= lr*dydb.mean()
```

只是为了好玩，你可以使用`matplotlib.animation.FuncAnimation`来制作动画：

提示：Fast.ai AMI 没有附带`ffmpeg`。所以如果你看到`KeyError: 'ffmpeg'`

+   运行`print(animation.writers.list())`并打印出可用的 MovieWriters 列表

+   如果`ffmpeg`在其中。否则[安装它](https://github.com/adaptlearning/adapt_authoring/wiki/Installing-FFmpeg)。

# [循环神经网络 - RNN](https://github.com/fastai/fastai/blob/master/courses/dl1/lesson6-rnn.ipynb) [[1:09:16](https://youtu.be/sHcLkfRrgoQ?t=1h9m16s)]

让我们学习如何像尼采一样写哲学。这类似于我们在第 4 课学到的语言模型，但这次，我们将一次一个字符地做。RNN 与我们已经学过的内容没有区别。

## 一些例子：

+   [SwiftKey](https://blog.swiftkey.com/neural-networks-a-meaningful-leap-for-mobile-typing/)

+   [Andrej Karpathy LaTex 生成器](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)

## 具有单隐藏层的基本 NN

所有形状都是激活（激活是通过 relu、矩阵乘积等计算得到的数字）。箭头是层操作（可能不止一个）。查看机器学习课程第 9-11 课，从头开始创建这个。

## 具有单个密集隐藏层的图像 CNN

我们将在下周更详细地介绍如何展平一个层，但主要方法被称为“自适应最大池化”——在高度和宽度上取平均值，将其转换为向量。

这里没有显示`batch_size`维度和激活函数（例如 relu，softmax）

## 使用字符 1 和 2 预测字符 3[[1:18:04](https://youtu.be/sHcLkfRrgoQ?t=1h18m4s)]

我们将为 NLP 实现这个。

+   输入可以是一个独热编码字符（向量长度=唯一字符数）或一个整数，并通过使用嵌入层假装它是独热编码。

+   与 CNN 的区别在于然后 char 2 输入被添加。

未显示层操作；记住箭头代表层操作

让我们实现这个，没有 torchtext 或 fast.ai 库，这样我们就可以看到。

+   `set`将返回所有唯一字符。

```py
text = open(f'{PATH}nietzsche.txt').read()
print(text[:400])
'''
'PREFACE\n\n\nSUPPOSING that Truth is a woman--what then? Is there not ground\nfor suspecting that all philosophers, in so far as they have been\ndogmatists, have failed to understand women--that the terrible\nseriousness and clumsy importunity with which they have usually paid\ntheir addresses to Truth, have been unskilled and unseemly methods for\nwinning a woman? Certainly she has never allowed herself '
'''
chars = sorted(list(set(text))) 
vocab_size = len(chars)+1 
print('total chars:', vocab_size)
'''
total chars: 85
'''
```

+   总是好的为填充放置一个空字符或空字符。

```py
chars.insert(0, "\0")
```

将每个字符映射到唯一 ID，并将唯一 ID 映射到字符

```py
char_indices = dict((c, i) for i, c in enumerate(chars))
indices_char = dict((i, c) for i, c in enumerate(chars))
```

现在我们可以用它的 ID 来表示文本：

```py
idx = [char_indices[c] for c in text]
idx[:10]
'''
[40, 42, 29, 30, 25, 27, 29, 1, 1, 1]
'''
```

## 问题：基于字符的模型与基于单词的模型[[1:22:30](https://youtu.be/sHcLkfRrgoQ?t=1h22m30s)]

+   通常，你希望结合字符级模型和单词级模型（例如用于翻译）。

+   当词汇表包含不寻常的单词时，字符级模型很有用——而单词级模型将其视为“未知”。当你看到一个以前没有见过的单词时，你可以使用字符级模型。

+   还有一种叫做字节对编码（BPE）的东西，它查看字符的 n-gram。

## 创建输入[[1:23:48](https://youtu.be/sHcLkfRrgoQ?t=1h23m48s)]

```py
cs = 3 
c1_dat = [idx[i]   for i in range(0, len(idx)-cs, cs)]
c2_dat = [idx[i+1] for i in range(0, len(idx)-cs, cs)]
c3_dat = [idx[i+2] for i in range(0, len(idx)-cs, cs)]
c4_dat = [idx[i+3] for i in range(0, len(idx)-cs, cs)]
```

注意`c1_dat[n+1] == c4_dat[n]`，因为我们是按 3 跳过的（`range`的第三个参数）

```py
x1 = np.stack(c1_dat) 
x2 = np.stack(c2_dat) 
x3 = np.stack(c3_dat) 
y = np.stack(c4_dat)
```

`x`是我们的输入，`y`是我们的目标值。

## 构建一个模型[[1:26:08](https://youtu.be/sHcLkfRrgoQ?t=1h26m8s)]

```py
n_hidden = 256 
n_fac = 42
```

+   `n_hiddein`-图表中的“#激活”。

+   `n_fac`-嵌入矩阵的大小。

这是上一个图表的更新版本。请注意，现在箭头是彩色的。所有具有相同颜色的箭头将使用相同的权重矩阵。这里的想法是，一个字符不会根据它在序列中是第一个、第二个还是第三个项目而具有不同的含义（语义上或概念上），因此将它们视为相同。

```py
class Char3Model(nn.Module):
     def __init__(self, vocab_size, n_fac):
         super().__init__()
         self.e = nn.Embedding(vocab_size, n_fac)
         self.l_in = nn.Linear(n_fac, n_hidden)
         self.l_hidden = nn.Linear(n_hidden, n_hidden)
         self.l_out = nn.Linear(n_hidden, vocab_size) 
     
     def forward(self, c1, c2, c3):
         
         in1 = F.relu(self.l_in(self.e(c1)))
         in2 = F.relu(self.l_in(self.e(c2)))
         in3 = F.relu(self.l_in(self.e(c3)))

         h = V(torch.zeros(in1.size()).cuda())
         h = F.tanh(self.l_hidden(h+in1))
         h = F.tanh(self.l_hidden(h+in2))
         h = F.tanh(self.l_hidden(h+in3))

         return F.log_softmax(self.l_out(h))
```

[视频[1:27:57]](https://youtu.be/sHcLkfRrgoQ?t=1h27m57s)

+   [[1:29:58](https://youtu.be/sHcLkfRrgoQ?t=1h29m58s)]重要的是，这个`l_hidden`使用一个大小与`l_in`的输出匹配的方形权重矩阵。然后`h`和`in2`将具有相同的形状，允许我们像在`self.l_hidden(h+in2)`中看到的那样将它们相加。

+   `V(torch.zeros(in1.size()).cuda())`只是为了使这三行相同，以便稍后更容易放入循环中。

```py
md = ColumnarModelData.from_arrays('.', [-1], np.stack([x1,x2,x3], axis=1), y, bs=512)
```

我们将重用`ColumnarModelData`[[1:32:20](https://youtu.be/sHcLkfRrgoQ?t=1h32m20s)]。如果我们堆叠`x1`，`x2`和`x3`，我们将在`forward`方法中得到`c1`，`c2`，`c3`。当您想以原始方式训练模型时，`ColumnarModelData.from_arrays`会派上用场，您在`[x1, x2, x3]`中放入的内容，将在`**def** **forward**(self, c1, c2, c3)`中返回。

```py
m = Char3Model(vocab_size, n_fac).cuda()
```

+   我们创建一个标准的 PyTorch 模型（不是`Learner`）

+   因为它是一个标准的 PyTorch 模型，不要忘记`.cuda`

```py
it = iter(md.trn_dl)
*xs,yt = next(it)
t = m(*V(xs))
```

+   `iter`来获取一个迭代器

+   `next`返回一个小批量

+   “变量化”`xs`张量，并将其通过模型-这将给我们一个包含预测的 512x85 张量（批量大小*独特字符）

```py
opt = optim.Adam(m.parameters(), 1e-2)
```

+   创建一个标准的 PyTorch 优化器-需要传入一个要优化的列表，该列表由`m.parameters()`返回

```py
fit(m, md, 1, opt, F.nll_loss)
set_lrs(opt, 0.001)
fit(m, md, 1, opt, F.nll_loss)
```

+   我们找不到学习率查找器和 SGDR，因为我们没有使用`Learner`，所以我们需要手动进行学习率退火（将 LR 设置得稍低一些）

## 测试一个模型[[1:35:58](https://youtu.be/sHcLkfRrgoQ?t=1h35m58s)]

```py
def get_next(inp):
     idxs = T(np.array([char_indices[c] for c in inp]))
     p = m(*VV(idxs))
     i = np.argmax(to_np(p))
     return chars[i]
```

这个函数接受三个字符，并返回模型预测的第四个。注意：`np.argmax`返回最大值的索引。

```py
get_next('y. ')
'''
'T'
'''
get_next('ppl')
'''
'e'
'''
get_next(' th')
'''
'e'
'''
get_next('and')
'''
' '
'''
```

## 让我们创建我们的第一个 RNN[[1:37:45](https://youtu.be/sHcLkfRrgoQ?t=1h37m45s)]

我们可以简化上一个图表如下：

使用 1 到 n-1 个字符预测第 n 个字符

让我们实现这个。这次，我们将使用前 8 个字符来预测第 9 个。这是如何创建输入和输出的，就像上次一样：

```py
cs = 8
c_in_dat = [[idx[i+j] for i in range(cs)] for j in range(len(idx)-cs)]
c_out_dat = [idx[j+cs] for j in range(len(idx)-cs)]
xs = np.stack(c_in_dat, axis=0)
y = np.stack(c_out_dat)
xs[:cs,:cs]
'''
array([[40, 42, 29, 30, 25, 27, 29,  1],
       [42, 29, 30, 25, 27, 29,  1,  1],
       [29, 30, 25, 27, 29,  1,  1,  1],
       [30, 25, 27, 29,  1,  1,  1, 43],
       [25, 27, 29,  1,  1,  1, 43, 45],
       [27, 29,  1,  1,  1, 43, 45, 40],
       [29,  1,  1,  1, 43, 45, 40, 40],
       [ 1,  1,  1, 43, 45, 40, 40, 39]])
'''
y[:cs]
'''
array([ 1,  1, 43, 45, 40, 40, 39, 43])
'''
```

请注意，它们是重叠的（即 0-7 预测 8，1-8 预测 9）。

```py
val_idx = get_cv_idxs(len(idx)-cs-1)
md = ColumnarModelData.from_arrays('.', val_idx, xs, y, bs=512)
```

## 创建模型[[1:43:03](https://youtu.be/sHcLkfRrgoQ?t=1h43m3s)]

```py
class CharLoopModel(nn.Module):
    # This is an RNN!
    def __init__(self, vocab_size, n_fac):
        super().__init__()
        self.e = nn.Embedding(vocab_size, n_fac)
        self.l_in = nn.Linear(n_fac, n_hidden)
        self.l_hidden = nn.Linear(n_hidden, n_hidden)
        self.l_out = nn.Linear(n_hidden, vocab_size)

    def forward(self, *cs):
        bs = cs[0].size(0)
        h = V(torch.zeros(bs, n_hidden).cuda())
        for c in cs:
            inp = F.relu(self.l_in(self.e(c)))
            h = F.tanh(self.l_hidden(h+inp))

        return F.log_softmax(self.l_out(h), dim=-1)
```

大部分代码与以前相同。您会注意到`forward`函数中有一个`for`循环。

> 双曲正切（Tanh）[[1:43:43](https://youtu.be/sHcLkfRrgoQ?t=1h43m43s)]
> 
> 这是一个偏移的 sigmoid 函数。在隐藏状态到隐藏状态的转换中使用双曲正切是常见的，因为它可以阻止其飞得太高或太低。对于其他目的，relu 更常见。

现在这是一个相当深的网络，因为它使用 8 个字符而不是 2 个。随着网络变得更深，它们变得更难训练。

```py
m = CharLoopModel(vocab_size, n_fac).cuda() 
opt = optim.Adam(m.parameters(), 1e-2)
fit(m, md, 1, opt, F.nll_loss)
set_lrs(opt, 0.001)
fit(m, md, 1, opt, F.nll_loss)
```

## 添加 vs.连接

现在我们将尝试为`self.l_hidden(**h+inp**)`[[1:46:04](https://youtu.be/sHcLkfRrgoQ?t=1h46m4s)]尝试其他方法。原因是输入状态和隐藏状态在质上是不同的。输入是字符的编码，h 是一系列字符的编码。因此，将它们相加，我们可能会丢失信息。让我们改为连接它们。不要忘记更改输入以匹配形状（`n_fac+n_hidden`而不是`n_fac`）。

```py
class CharLoopConcatModel(nn.Module):
    def __init__(self, vocab_size, n_fac):
        super().__init__()
        self.e = nn.Embedding(vocab_size, n_fac)
        self.l_in = nn.Linear(n_fac+n_hidden, n_hidden)
        self.l_hidden = nn.Linear(n_hidden, n_hidden)
        self.l_out = nn.Linear(n_hidden, vocab_size)

    def forward(self, *cs):
        bs = cs[0].size(0)
        h = V(torch.zeros(bs, n_hidden).cuda())
        for c in cs:
            inp = torch.cat((h, self.e(c)), 1)
            inp = F.relu(self.l_in(inp))
            h = F.tanh(self.l_hidden(inp))

        return F.log_softmax(self.l_out(h), dim=-1)
```

这带来了一些改进。

## 使用 PyTorch 的 RNN[[1:48:47](https://youtu.be/sHcLkfRrgoQ?t=1h48m47s)]

PyTorch 将自动为我们编写`for`循环，还会编写线性输入层。

```py
class CharRnn(nn.Module):
    def __init__(self, vocab_size, n_fac):
        super().__init__()
        self.e = nn.Embedding(vocab_size, n_fac)
        **self.rnn = nn.RNN(n_fac, n_hidden)**
        self.l_out = nn.Linear(n_hidden, vocab_size)

    def forward(self, *cs):
        bs = cs[0].size(0)
        h = V(torch.zeros(1, bs, n_hidden))
        inp = self.e(torch.stack(cs))
        **outp,h = self.rnn(inp, h)**

        return F.log_softmax(self.l_out(**outp[-1]**), dim=-1)
```

+   出于以后会变得明显的原因，`self.rnn`将返回不仅输出，还有隐藏状态。

+   PyTorch 中的一个微小差异是`self.rnn`会将一个新的隐藏状态附加到张量上，而不是替换（换句话说，它会在图表中返回所有省略号）。我们只想要最后一个，所以我们做`outp[-1]`

```py
m = CharRnn(vocab_size, n_fac).cuda() 
opt = optim.Adam(m.parameters(), 1e-3)
ht = V(torch.zeros(1, 512,n_hidden)) 
outp, hn = m.rnn(t, ht) 
outp.size(), hn.size()
'''
(torch.Size([8, 512, 256]), torch.Size([1, 512, 256]))
'''
```

在 PyTorch 版本中，隐藏状态是一个秩为 3 的张量`h = V(torch.zeros(1, bs, n_hidden)`（在我们的版本中，它是秩为 2 的张量）[[1:51:58](https://youtu.be/sHcLkfRrgoQ?t=1h51m58s)]。我们以后会学到更多关于这个，但事实证明你可以有第二个向后运行的 RNN。这个想法是它会更好地找到向后的关系——它被称为“双向 RNN”。你也可以有一个 RNN 馈送到一个 RNN，这被称为“多层 RNN”。对于这些 RNN，你将需要张量中的额外轴来跟踪额外层的隐藏状态。现在，我们只有 1 个，然后返回 1 个。

## 测试模型

```py
def get_next(inp):
    idxs = T(np.array([char_indices[c] for c in inp]))
    p = m(*VV(idxs))
    i = np.argmax(to_np(p))
    return chars[i]
def get_next_n(inp, n):
    res = inp
    for i in range(n):
        c = get_next(inp)
        res += c
        inp = inp[1:]+c
    return res
get_next_n('for thos', 40) 
'''
'for those the same the same the same the same th'
'''
```

这次，我们循环`n`次，每次调用`get_next`，每次我们将我们的输入替换为删除第一个字符并添加我们刚预测的字符。

对于有趣的作业，尝试编写自己的`nn.RNN`“`JeremysRNN`”，而不查看 PyTorch 源代码。

## 多输出[[1:55:31](https://youtu.be/sHcLkfRrgoQ?t=1h55m31s)]

从最后一个图表中，我们可以进一步简化，将字符 1 视为字符 2 到 n-1 相同。你会注意到三角形（输出）也移动到循环内部，换句话说，我们在每个字符之后创建一个预测。

使用字符 1 到 n-1 预测字符 2 到 n

我们可能想要这样做的原因之一是我们之前看到的冗余：

```py
array([[40, 42, 29, 30, 25, 27, 29,  1],
       [42, 29, 30, 25, 27, 29,  1,  1],
       [29, 30, 25, 27, 29,  1,  1,  1],
       [30, 25, 27, 29,  1,  1,  1, 43],
       [25, 27, 29,  1,  1,  1, 43, 45],
       [27, 29,  1,  1,  1, 43, 45, 40],
       [29,  1,  1,  1, 43, 45, 40, 40],
       [ 1,  1,  1, 43, 45, 40, 40, 39]])
```

这次我们可以通过采用**不重叠**的字符集来使其更有效。因为我们正在进行多输出，对于输入字符 0 到 7，输出将是字符 1 到 8 的预测。

```py
xs[:cs,:cs]
'''
array([[40, 42, 29, 30, 25, 27, 29,  1],
       [ 1,  1, 43, 45, 40, 40, 39, 43],
       [33, 38, 31,  2, 73, 61, 54, 73],
       [ 2, 44, 71, 74, 73, 61,  2, 62],
       [72,  2, 54,  2, 76, 68, 66, 54],
       [67,  9,  9, 76, 61, 54, 73,  2],
       [73, 61, 58, 67, 24,  2, 33, 72],
       [ 2, 73, 61, 58, 71, 58,  2, 67]])
'''
ys[:cs,:cs]
'''
array([[42, 29, 30, 25, 27, 29,  1,  1],
       [ 1, 43, 45, 40, 40, 39, 43, 33],
       [38, 31,  2, 73, 61, 54, 73,  2],
       [44, 71, 74, 73, 61,  2, 62, 72],
       [ 2, 54,  2, 76, 68, 66, 54, 67],
       [ 9,  9, 76, 61, 54, 73,  2, 73],
       [61, 58, 67, 24,  2, 33, 72,  2],
       [73, 61, 58, 71, 58,  2, 67, 68]])
'''
```

这不会使我们的模型更准确，但我们可以更有效地训练它。

```py
class CharSeqRnn(nn.Module):
    def __init__(self, vocab_size, n_fac):
        super().__init__()
        self.e = nn.Embedding(vocab_size, n_fac)
        self.rnn = nn.RNN(n_fac, n_hidden)
        self.l_out = nn.Linear(n_hidden, vocab_size)

    def forward(self, *cs):
        bs = cs[0].size(0)
        h = V(torch.zeros(1, bs, n_hidden))
        inp = self.e(torch.stack(cs))
        outp,h = self.rnn(inp, h)
        return F.log_softmax(self.l_out(outp), dim=-1)
```

请注意，我们不再做`outp[-1]`，因为我们想保留所有这些。但其他一切都是相同的。一个复杂性[[2:00:37](https://youtu.be/sHcLkfRrgoQ?t=2h37s)]是我们想要像以前一样使用负对数似然损失函数，但它期望两个秩为 2 的张量（两个矢量的小批量）。但在这里，我们有秩为 3 的张量：

+   8 个字符（时间步）

+   84 个概率

+   对于 512 个小批量

## 让我们编写一个自定义损失函数[[2:02:10](https://youtu.be/sHcLkfRrgoQ?t=2h2m10s)]:

```py
def nll_loss_seq(inp, targ):
    sl,bs,nh = inp.size()
    targ = targ.transpose(0,1).contiguous().view(-1)
    return F.nll_loss(inp.view(-1,nh), targ)
```

+   `F.nll_loss`是 PyTorch 的损失函数。

+   展平我们的输入和目标。

+   转置前两个轴，因为 PyTorch 期望 1.序列长度（多少个时间步），2.批量大小，3.隐藏状态本身。`yt.size()`是 512 乘以 8，而`sl, bs`是 8 乘以 512。

+   当你做像“transpose”这样的事情时，PyTorch 通常不会实际洗牌内存顺序，而是保留一些内部元数据来处理它，就好像它被转置了。当你转置一个矩阵时，PyTorch 只是更新元数据。如果你看到一个错误说“这个张量不连续”，在它后面加上`.contiguous()`，错误就会消失。

+   `.view`与`np.reshape`相同。`-1`表示它需要多长。

```py
fit(m, md, 4, opt, null_loss_seq)
```

记住`fit(...)`是 fast.ai 实现训练循环的最低级抽象。因此，除了`md`是包装测试集、训练集和验证集的模型数据对象之外，所有参数都是标准的 PyTorch 东西。

问题[[2:06:04](https://youtu.be/sHcLkfRrgoQ?t=2h6m4s)]: 现在我们在循环内部放了一个三角形，我们需要更大的序列大小吗？

+   如果我们有一个短序列像 8 这样，第一个字符没有任何依据。它从零开始的空隐藏状态。

+   我们将学习如何避免这个问题下周。

+   基本思想是“为什么我们每次都要将隐藏状态重置为零？”（见下面的代码）。如果我们可以以某种方式排列这些小批量，使得下一个小批量正确连接起来，代表尼采作品中的下一个字母，那么我们可以将`h = V(torch.zeros(1, bs, n_hidden))`移到构造函数中。

```py
class CharSeqRnn(nn.Module):
    def __init__(self, vocab_size, n_fac):
        super().__init__()
        self.e = nn.Embedding(vocab_size, n_fac)
        self.rnn = nn.RNN(n_fac, n_hidden)
        self.l_out = nn.Linear(n_hidden, vocab_size)

    def forward(self, *cs):
        bs = cs[0].size(0)
        **h = V(torch.zeros(1, bs, n_hidden))**
        inp = self.e(torch.stack(cs))
        outp,h = self.rnn(inp, h)
        return F.log_softmax(self.l_out(outp), dim=-1)
```

## 梯度爆炸 [[2:08:21](https://youtu.be/sHcLkfRrgoQ?t=2h8m21s)]

`self.rnn(inp, h)` 是一个循环，一遍又一遍地应用相同的矩阵乘法。如果那个矩阵乘法倾向于每次增加激活，我们实际上是将其乘以 8 次 — 我们称之为梯度爆炸。我们希望确保初始的`l_hidden`不会导致我们的激活平均增加或减少。

一个很好的能做到这一点的矩阵被称为单位矩阵：

我们可以用单位矩阵覆盖随机初始化的隐藏-隐藏权重：

```py
m.rnn.weight_hh_l0.data.copy_(torch.eye(n_hidden))
```

这是由 Geoffrey Hinton 等人在 2015 年介绍的（[一种初始化修正线性单元循环网络的简单方法](https://arxiv.org/abs/1504.00941)） — 在 RNN 存在几十年后。它效果非常好，你可以使用更高的学习率，因为它表现良好。
