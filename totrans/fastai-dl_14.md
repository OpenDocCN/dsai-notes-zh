# 深度学习 2：第 2 部分第 14 课

> 原文：[`medium.com/@hiromi_suenaga/deep-learning-2-part-2-lesson-14-e0d23c7a0add`](https://medium.com/@hiromi_suenaga/deep-learning-2-part-2-lesson-14-e0d23c7a0add)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](http://creativecommons.org/licenses/by-nc-sa/4.0/)

*我从*[*fast.ai 课程*](http://www.fast.ai/) *中得到的个人笔记。随着我继续复习课程以“真正”理解它，这些笔记将继续更新和改进。非常感谢*[*Jeremy*](https://twitter.com/jeremyphoward) *和*[*Rachel*](https://twitter.com/math_rachel) *给了我这个学习的机会。*

[论坛](http://forums.fast.ai/t/part-2-lesson-14-wiki/15650/1) / [视频](https://youtu.be/nG3tT31nPmQ)

## 上周的展示

Alena Harley 做了一些非常有趣的事情，她尝试找出如果只对三四百张图片进行循环 GAN 会发生什么，我真的很喜欢这些项目，人们只需使用 API 或其中一个库去谷歌图片搜索。我们的一些学生已经创建了一些非常好的库，用于与谷歌图片 API 进行交互，下载一些他们感兴趣的东西，比如一些照片和一些彩色玻璃窗。有了 300~400 张照片，她训练了几个不同的模型——这是我特别喜欢的。正如你所看到的，用相当少量的图片，她得到了非常漂亮的彩色玻璃效果。所以我认为这是一个有趣的例子，使用相当少量的数据，她能够很快地下载到的数据。如果你感兴趣，论坛上有更多信息。

人们会用这种生成模型想出什么样的东西是很有趣的。这显然是一个很好的艺术媒介。显然也是一个很好的伪造和欺骗媒介。我想知道人们会意识到他们可以用这种生成模型做什么其他类型的事情。我认为音频将成为下一个重要领域。还有非常互动的类型。英伟达刚刚发布了一篇论文，展示了一种互动的照片修复工具，你只需刷过一个物体，它就会用深度学习生成的替代品替换得很好。我认为这种互动工具也会很有趣。

# 超分辨率[[2:06](https://youtu.be/nG3tT31nPmQ?t=2m6s)]

[实时风格转移和超分辨率的感知损失](https://arxiv.org/abs/1603.08155)

上次，我们看了通过直接优化像素来进行风格转移。就像第二部分的大部分内容一样，我并不是想让你理解风格转移本身，而是直接优化输入并使用激活作为损失函数的一种想法，这才是真正的关键点。

因此，有趣的是看到接下来的论文，不是来自同一组人，而是在这些视觉生成模型序列中接下来的一篇来自斯坦福大学的 Justin Johnson 和他的同事。它实际上做了同样的事情——风格转移，但是用了不同的方法。与其优化像素，我们将回到更熟悉的东西，优化一些权重。具体来说，我们将训练一个模型，学习将一张照片转换成某种艺术作品风格的照片。因此，每个卷积网络将学习产生一种风格。

现在，事实证明，要达到那一点，有一个中间点（我认为更有用，可以让我们走一半的路）叫做超分辨率。所以我们实际上要从超分辨率开始[[3:55](https://youtu.be/nG3tT31nPmQ?t=3m55s)]。因为然后我们将在超分辨率的基础上构建卷积神经网络风格转移的最后部分。

超分辨率是指我们将一个低分辨率图像（我们将采用 72x72）放大到一个更大的图像（在我们的情况下是 288x288），试图创建一个看起来尽可能真实的高分辨率图像。这是一件具有挑战性的事情，因为在 72x72 的情况下，关于很多细节的信息并不多。很酷的是，我们将以一种与视觉模型相似的方式来做，这种方式不受输入大小的限制，因此您完全可以将这个模型应用于 288x288 的图像，得到每边都大四倍的东西，比原始图像大 16 倍。通常在那个级别甚至效果更好，因为您真的在更细节的地方引入了很多细节，您可以真正打印出一个高分辨率的打印品，而之前它看起来相当像素化。

## [笔记本](https://github.com/fastai/fastai/blob/master/courses/dl2/enhance.ipynb)

这很像 CSI 风格的增强，我们将拿出一些看起来信息不在那里的东西，我们会发明它——但是卷积网络将学会以与已有信息一致的方式发明它，所以希望它发明正确的信息。这种问题的一个非常好的地方是，我们可以创建自己的数据集，而不需要任何标签要求，因为我们可以通过对图像进行降采样轻松地从高分辨率图像创建低分辨率图像。所以我希望你们中的一些人这周尝试做其他类型的图像到图像的转换，你可以发明“标签”（你的因变量）。例如：

+   **去斜**：识别已经旋转了 90 度或更好的是旋转了 5 度并将其拉直的东西。

+   **着色**：将一堆图像变成黑白，然后学会重新加上颜色。

+   **降噪**：也许做一个质量很低的 JPEG 保存，然后学会将其恢复到应该有的样子。

+   也许将一个 16 色调色板的东西放回到更高的色调色板。

我认为这些东西都很有趣，因为它们可以用来处理您以前用糟糕的旧数码相机拍摄的照片，或者您可能已经扫描了一些现在已经褪色的旧照片等。我认为这是一件非常有用的事情，也是一个很好的项目，因为它与我们在这里所做的非常相似，但又有足够的不同，让您在途中遇到一些有趣的挑战，我相信。

我将再次使用 ImageNet。您根本不需要使用所有的 ImageNet，我只是碰巧有它。您可以从 files.fast.ai 下载 ImageNet 的百分之一样本。您可以使用您手头上任何一组图片。

```py
matplotlib inline
%reload_ext autoreload
%autoreload 2
```

# 超分辨率数据

```py
**from** **fastai.conv_learner** **import** *
**from** **pathlib** **import** Path

torch.backends.cudnn.benchmark=**True**PATH = Path('data/imagenet')
PATH_TRN = PATH/'train'
```

在这种情况下，正如我所说，我们实际上没有标签，所以我只是给每样东西都标上零，这样我们就可以更容易地与我们现有的基础设施一起使用。

```py
fnames_full,label_arr_full,all_labels = folder_source(PATH, 'train')
fnames_full = ['/'.join(Path(fn).parts[-2:]) **for** fn **in** fnames_full]
list(zip(fnames_full[:5],label_arr_full[:5]))*[('n01440764/n01440764_9627.JPEG', 0),
 ('n01440764/n01440764_9609.JPEG', 0),
 ('n01440764/n01440764_5176.JPEG', 0),
 ('n01440764/n01440764_6936.JPEG', 0),
 ('n01440764/n01440764_4005.JPEG', 0)]*all_labels[:5]*['n01440764', 'n01443537', 'n01484850', 'n01491361', 'n01494475']*
```

现在，因为我指向一个包含所有 ImageNet 的文件夹，我当然不想等待所有 ImageNet 完成一个周期才运行。所以在这里，我通常会将“保留百分比”（`keep_pct`）设置为 1 或 2%。然后我只生成一堆随机数，然后只保留那些小于 0.02 的数，这样让我快速地对行进行子采样。

```py
np.random.seed(42)
# keep_pct = 1.
*keep_pct = 0.02*
keeps = np.random.rand(len(fnames_full)) < keep_pct
fnames = np.array(fnames_full, copy=**False**)[keeps]
label_arr = np.array(label_arr_full, copy=**False**)[keeps]
```

所以我们将使用 VGG16，VGG16 是我们在这门课程中还没有真正研究过的东西，但它是一个非常简单的模型，我们将采用我们通常的预计是 3 通道输入，然后基本上通过一系列 3x3 的卷积运行它，然后不时地，我们将它通过一个 2x2 的最大池化，然后我们再做一些 3x3 的卷积，最大池化，依此类推。这就是我们的骨干。

然后我们不再使用自适应平均池化层。经过几次操作后，我们像往常一样得到了一个 7x7x512 的网格（或类似的东西）。所以我们不再进行平均池化，而是做一些不同的事情，即将整个东西展平 - 这样就会输出一个大小为 7x7x512 的非常长的激活向量。然后将其馈送到两个全连接层，每个全连接层有 4096 个激活，并且还有一个具有多少类别的全连接层。所以如果你考虑一下，这里的权重矩阵是巨大的 7x7x512x4096。正是因为这个权重矩阵，VGG 很快就不受欢迎了 - 因为它占用了大量内存，需要大量计算，速度非常慢。这里有很多冗余的东西，因为实际上这 512 个激活并不特定于它们在哪个 7x7 网格单元中。但是当你有这里的整个权重矩阵，包含了每种可能的组合，它会将它们都视为独特的。这也可能导致泛化问题，因为有很多权重等等。

我认为现代网络中使用的方法是进行自适应平均池化（在 Keras 中被称为全局平均池化，在 fast.ai 中我们使用自适应连接池），这将直接输出一个 512 维的激活。我认为这样做丢失了太多的几何信息。所以对我来说，可能正确的答案在两者之间，并且可能涉及某种因子卷积或张量分解，也许我们中的一些人可以在未来几个月考虑一下。所以目前，我们已经从自适应平均池化这个极端转向了另一个极端，即这个巨大的扁平化全连接层。

关于 VGG 有一些有趣的事情，使它至今仍然有用[[11:59](https://youtu.be/nG3tT31nPmQ?t=11m59s)]。第一件事是这里有更多有趣的层，大多数现代网络包括 ResNet 系列，第一层通常是一个 7x7 的卷积，步幅为 2 或类似的。这意味着我们立即丢弃了一半的网格大小，因此几乎没有机会使用细节，因为我们从不对其进行任何计算。这对于分割或超分辨率模型等需要细节的问题是一个问题。我们实际上想要恢复它。然后第二个问题是自适应池化层完全丢弃了最后几个部分的几何信息，这意味着模型的其余部分实际上没有太多有趣的几何学习。因此，对于依赖位置的事物，任何需要生成模型的定位方法都会不太有效。所以我希望你在我描述这些内容时能听到的一件事是，也许现有的架构都不是理想的。我们可以发明一个新的。实际上，我在这一周尝试了发明一个新的，就是将 VGG 头部连接到 ResNet 骨干上。有趣的是，我发现我实际上得到了一个稍微更好的分类器，比普通的 ResNet 好一点，但它也包含了一些更有用的信息。训练时间长了 5 到 10%，但没有什么值得担心的。也许我们可以在 ResNet 中，用我们之前简要讨论过的方式，将这个（7x7 卷积步幅 2）替换为更像 Inception stem 的东西，这样有更多的计算。我认为这些架构肯定有一些小的调整空间，这样我们可以构建一些可能更多功能的模型。目前，人们倾向于构建只能做一件事的架构。他们并没有真正考虑到机会的丢失，因为这就是出版的工作方式。你发表“我在这一件事上达到了最新水平”而不是你创造了一些在很多方面都很擅长的东西。

出于这些原因，今天我们将使用 VGG，尽管它已经过时并且缺少很多很棒的东西[[14:42](https://youtu.be/nG3tT31nPmQ?t=14m42s)]。不过，我们要做的一件事是使用一个稍微更现代的版本，这是一个在所有卷积层之后添加了批量归一化的 VGG 版本。在 fast.ai 中，当你请求一个 VGG 网络时，你总是得到批量归一化的版本，因为那基本上总是你想要的。所以这是带有批量归一化的 VGG。有 16 和 19，19 更大更重，但实际上并没有做得更好，所以没有人真的使用它。

```py
arch = vgg16
sz_lr = 72
```

我们将从 72x72 的 LR（`sz_lr`：低分辨率大小）输入开始。我们将首先通过 64 的批次大小将其放大 2 倍，以获得 2 * 72，即 144x144 的输出。这将是我们的第一阶段。

```py
scale,bs = 2,64
*# scale,bs = 4,32*
sz_hr = sz_lr*scale
```

我们将为此创建自己的数据集，值得查看 fastai.dataset 模块的内部并看看那里有什么[[15:45](https://youtu.be/nG3tT31nPmQ?t=15m45s)]。因为几乎任何你想要的东西，我们可能都有几乎符合你要求的东西。所以在这种情况下，我想要一个数据集，其中我的*x*是图像，我的*y*也是图像。已经有一个文件数据集，我们可以继承其中的*x*是图像，然后我只需继承自那个，并且我只是复制并粘贴了`get_x`并将其转换为`get_y`，这样它就打开了一个图像。现在我有了一个*x*是图像，*y*也是图像的东西，在这两种情况下，我们传入的都是文件名数组。

```py
**class** **MatchedFilesDataset**(FilesDataset):
    **def** __init__(self, fnames, y, transform, path):
        self.y=y
        **assert**(len(fnames)==len(y))
        super().__init__(fnames, transform, path)
    **def** get_y(self, i): 
        **return** open_image(os.path.join(self.path, self.y[i]))
    **def** get_c(self): **return** 0
```

我将进行一些数据增强。显然，对于所有的 ImageNet，我们并不真正需要它，但这主要是为了任何使用较小数据集的人能够充分利用它。`RandomDihedral`指的是每个可能的 90 度旋转加上可选的左/右翻转，因此它们是八个对称的二面角群。通常我们不会对 ImageNet 图片使用这种转换，因为你通常不会把狗颠倒过来，但在这种情况下，我们并不是试图分类它是狗还是猫，我们只是试图保持它的一般结构。因此，实际上对于这个问题来说，每个可能的翻转都是一个相当明智的事情。

```py
aug_tfms = [RandomDihedral(tfm_y=TfmType.PIXEL)]
```

以通常的方式创建一个验证集。你可以看到我使用了一些更低级别的函数——一般来说，我只是从 fastai 源代码中复制和粘贴它们，找到我想要的部分。这里有一个部分，它接受一个验证集索引数组和一个或多个变量数组，然后简单地分割。在这种情况下，这个（`np.array(fnames)`）分成一个训练和验证集，这个（第二个`np.array(fnames)`）分成一个训练和验证集，给我们我们的*x*和*y*。在这种情况下，*x*和*y*是相同的。我们的输入图像和输出图像是相同的。我们将使用转换使它们中的一个分辨率较低。这就是为什么它们是相同的东西。

```py
val_idxs = get_cv_idxs(len(fnames), val_pct=min(0.01/keep_pct, 0.1))
((val_x,trn_x),(val_y,trn_y)) = split_by_idx(val_idxs, 
                                np.array(fnames), np.array(fnames))
len(val_x),len(trn_x)*(12811, 1268356)*img_fn = PATH/'train'/'n01558993'/'n01558993_9684.JPEG'
```

接下来我们需要像往常一样创建我们的转换。我们将使用`tfm_y`参数，就像我们为边界框所做的那样，但我们不是使用`TfmType.COORD`，而是使用`TfmType.PIXEL`。这告诉我们的转换框架，你的*y*值是带有正常像素的图像，所以任何你对*x*做的事情，你也需要对*y*做同样的事情。你需要确保你使用的任何数据增强转换也具有相同的参数。

```py
tfms = tfms_from_model(arch, sz_lr, tfm_y=TfmType.PIXEL, 
          aug_tfms=aug_tfms, sz_y=sz_hr)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y), 
               (val_x,val_y), tfms, path=PATH_TRN)
md = ImageData(PATH, datasets, bs, num_workers=16, classes=**None**)
```

你可以看到你得到的可能的转换类型：

+   分类：我们将在今天的下半部分使用分割

+   坐标：坐标——没有任何转换

+   像素

一旦我们有了`Dataset`类和一些*x*和*y*的训练和验证集。有一个方便的小方法叫做获取数据集(`get_ds`)，它基本上运行构造函数，返回你需要的所有数据集，以恰好正确的格式传递给 ModelData 构造函数（在这种情况下是`ImageData`构造函数）。所以我们有点回到了 fastai 的内部，从头开始构建。在接下来的几周里，这一切都将被整合和重构成你可以在 fastai 中一步完成的东西。但这个类的目的是为了学习一些关于内部的知识。

我们之前简要看到的是，当我们输入图像时，我们不仅要进行数据增强，还要将通道维度移到开头，我们要减去平均值除以标准差等。所以如果我们想要显示那些从我们的数据集或数据加载器中出来的图片，我们需要对它们进行反归一化。所以模型数据对象（`md`）的数据集（`val_ds`）有一个 denorm 函数，知道如何做到这一点。我只是为了方便给它一个简短的名字：

```py
denorm = md.val_ds.denorm
```

现在我要创建一个函数，可以显示数据集中的图像，如果你传入一个说这是一个归一化图像的东西，那么我们将对它进行反归一化。

```py
**def** show_img(ims, idx, figsize=(5,5), normed=**True**, ax=**None**):
    **if** ax **is** **None**: fig,ax = plt.subplots(figsize=figsize)
    **if** normed: ims = denorm(ims)
    **else**:      ims = np.rollaxis(to_np(ims),1,4)
    ax.imshow(np.clip(ims,0,1)[idx])
    ax.axis('off')x,y = next(iter(md.val_dl))
x.size(),y.size()*(torch.Size([32, 3, 72, 72]), torch.Size([32, 3, 288, 288]))*
```

你会看到我们传入了低分辨率大小（`sz_lr`）作为我们的转换大小，高分辨率大小（`sz_hr`）作为，这是新的东西，大小 y 参数（`sz_y`）。所以这两部分将得到不同的大小。

在这里，您可以看到我们的*x*和*y*的两种不同分辨率，用于一大堆鱼。

```py
idx=1
fig,axes = plt.subplots(1, 2, figsize=(9,5))
show_img(x,idx, ax=axes[0])
show_img(y,idx, ax=axes[1])
```

像往常一样，使用`plt.subplots`创建我们的两个图，然后我们可以使用返回的不同轴将东西放在一起。

```py
batches = [next(iter(md.aug_dl)) **for** i **in** range(9)]
```

然后我们可以看一下数据转换的几个不同版本[[21:37](https://youtu.be/nG3tT31nPmQ?t=21m37s)]。在那里，您可以看到它们被以各种不同方向翻转。

```py
fig, axes = plt.subplots(3, 6, figsize=(18, 9))
**for** i,(x,y) **in** enumerate(batches):
    show_img(x,idx, ax=axes.flat[i*2])
    show_img(y,idx, ax=axes.flat[i*2+1])
```

## 模型[[21:48](https://youtu.be/nG3tT31nPmQ?t=21m48s)]

让我们创建我们的模型。我们将有一个小图像输入，并且我们希望有一个大图像输出。因此，我们需要在这两者之间进行一些计算，以计算大图像会是什么样子。基本上有两种方法来进行这种计算：

+   我们首先可以进行一些上采样，然后进行一些步幅为 1 的层来进行大量计算。

+   我们可以首先进行大量步幅为 1 的层来进行所有计算，然后最后进行一些上采样。

我们将选择第二种方法，因为我们想在较小的东西上进行大量计算，因为这样做速度更快。此外，在上采样过程中，我们可以利用所有这些计算。上采样，我们知道有几种可能的方法可以做到这一点。我们可以使用：

+   转置或分数步幅卷积

+   最近邻上采样，然后是 1x1 卷积

在“进行大量计算”部分，我们可以只进行大量的 3x3 卷积。但在这种特殊情况下，ResNet 块似乎更好，因为输出和输入非常相似。因此，我们真的希望有一个流经路径，允许尽可能少地烦扰，除了必要的最小量来进行我们的超分辨率。如果我们使用 ResNet 块，那么它们已经有一个身份路径。因此，您可以想象那些简单版本，它采用双线性采样方法或其他方法，它可以直接通过身份块，然后在上采样块中，只需学习获取输入的平均值，并得到一些不太糟糕的东西。

这就是我们要做的。我们将创建一个具有五个 ResNet 块的模型，然后对于每个 2 倍的缩放，我们将有一个上采样块。

它们都将由通常的卷积层组成，可能在其中的许多之后带有激活函数[[24:37](https://youtu.be/nG3tT31nPmQ?t=24m37s)]。我喜欢将我的标准卷积块放入一个函数中，这样我可以更容易地重构它。我不会担心传递填充，并直接计算它作为内核大小的一半。

```py
**def** conv(ni, nf, kernel_size=3, actn=**False**):
    layers = [nn.Conv2d(ni, nf, kernel_size, 
              padding=kernel_size//2)]
    **if** actn: layers.append(nn.ReLU(**True**))
    **return** nn.Sequential(*layers)
```

我们小卷积块的一个有趣之处在于没有批量归一化，这对于 ResNet 类型的模型来说是非常不寻常的。

[`arxiv.org/abs/1707.02921`](https://arxiv.org/abs/1707.02921)

没有批量归一化的原因是因为我从这篇最近的出色论文中窃取了一些想法，这篇论文实际上赢得了最近的超分辨率性能比赛。要看看这篇论文有多好，SRResNet 是之前的最先进技术，他们在这里所做的是他们已经放大到了一个上采样的网格/围栏。HR 是原始的。您可以看到在以前的最佳方法中，存在大量的失真和模糊。或者，在他们的方法中，几乎完美。因此，这篇论文是一个真正的重大进步。他们称其模型为 EDSR（增强深度超分辨率网络），并且他们与以前的标准方法有两点不同：

1.  拿起 ResNet 块并丢弃批量归一化。为什么要丢弃批量归一化？原因是因为批量归一化会改变东西，而我们希望有一个不改变东西的良好直通路径。因此，这里的想法是，如果您不想对输入进行更多操作，那么就不要强迫它计算诸如批量归一化参数之类的东西-所以丢弃批量归一化。

1.  缩放因子（我们很快会看到）。

```py
**class** **ResSequential**(nn.Module):
    **def** __init__(self, layers, res_scale=1.0):
        super().__init__()
        self.res_scale = res_scale
        self.m = nn.Sequential(*layers)

    **def** forward(self, x): **return** x + self.m(x) * self.res_scale
```

所以我们将创建一个包含两个卷积的残差块。正如你在他们的方法中看到的那样，他们甚至在第二个卷积后没有 ReLU。这就是为什么我只在第一个上有激活。

```py
**def** res_block(nf):
    **return** ResSequential(
        [conv(nf, nf, actn=**True**), conv(nf, nf)],
        0.1)
```

这里有几个有趣的地方[27:10]。一个是这个想法，即有一种主要的 ResNet 路径（卷积，ReLU，卷积），然后通过将其添加回到身份来将其转换为 ReLU 块——我们经常这样做，以至于我将其提取出来成为一个名为 ResSequential 的小模块。它简单地将您想要放入残差路径的一堆层转换为顺序模型，运行它，然后将其添加回输入。有了这个小模块，我们现在可以通过将其包装在 ResSequential 中，将任何东西，比如卷积激活卷积，转换为一个 ResNet 块。

但这并不是我正在做的全部，因为通常一个 Res 块在它的`forward`中只有`x + self.m(x)`。但我还加上了`* self.res_scale`。什么是`res_scale`？`res_scale`是数字 0.1。为什么要有它？我不确定有人完全知道。但简短的答案是，发明批量归一化的那个人最近还发表了一篇论文，他在其中首次展示了在不到一个小时内训练 ImageNet 的能力。他是如何做到的呢？他启动了大量的机器，并让它们并行工作，以创建非常大的批量大小。通常情况下，当你将批量大小增加*N*倍时，你也会相应地增加*N*倍的学习率。所以通常情况下，非常大的批量大小训练也意味着非常高的学习率训练。他发现，当使用这些非常大的批量大小，如 8000+甚至高达 32000 时，在训练开始时，他的激活基本上会直接变为无穷大。很多其他人也发现了这一点。我们在 DAWN bench 上参加 CIFAR 和 ImageNet 比赛时也发现了这一点，我们很难充分利用我们试图利用的八个 GPU，因为这些更大批量大小和利用它们的挑战。Christian 发现的一件事是，在 ResNet 块中，如果他将它们乘以小于 1 的某个数字，比如 0.1 或 0.2，这确实有助于在开始时稳定训练。这有点奇怪，因为从数学上讲，它是相同的。因为显然，无论我在这里乘以什么，我只需按相反的数量缩放权重，就可以得到相同的数字。但我们不是在处理抽象的数学——我们在处理真实的优化问题，不同的初始化、学习率和其他因素。所以权重消失到无穷大的问题，我想通常主要是关于计算机在实践中的离散和有限性质的一部分。因此，通常这种小技巧可以起到关键作用。

在这种情况下，我们只是根据我们的初始初始化来调整事物。所以可能还有其他方法可以做到这一点。例如，Nvidia 的一些人提出的一种叫做 LARS 的方法，我上周简要提到过，这是一种实时计算的判别学习率方法。基本上是通过查看梯度和激活之间的比率来按层缩放学习率。因此，他们发现他们不需要这个技巧来大幅增加批量大小。也许只需要不同的初始化就足够了。我提到这一点的原因并不是因为我认为你们中很多人可能想要在大型计算机集群上进行训练，而是因为我认为你们中很多人想要快速训练模型，这意味着使用高学习率，并且理想情况下实现超级收敛。我认为这些技巧是我们需要能够在更多不同的架构等方面实现超级收敛的技巧。除了 Leslie Smith 之外，没有其他人真正致力于超级收敛，现在只有一些 fastai 学生在做这些事情。因此，关于如何以非常非常高的学习率进行训练的问题，我们将不得不自己去解决，因为据我所知，其他人还没有关心这个问题。因此，查看围绕在一个小时内训练 ImageNet 的文献，或者最近有现在在 15 分钟内训练 ImageNet 的文献，我认为，这些论文实际上有一些技巧可以让我们以高学习率训练事物。这就是其中之一。

有趣的是，除了在一个小时内训练 ImageNet 的论文中提到过之外，我唯一看到这个提到的地方是在这篇 EDSR 论文中。这真的很酷，因为赢得比赛的人，我发现他们非常务实和博学。他们实际上必须让事情运转起来。因此，这篇论文描述了一种方法，实际上比任何其他方法都要好，他们做了这些务实的事情，比如放弃批量归一化，使用几乎没有人知道的这个小缩放因子。所以这就是 0.1 的来源。

```py
**def** upsample(ni, nf, scale):
    layers = []
    **for** i **in** range(int(math.log(scale,2))):
        layers += [conv(ni, nf*4), nn.PixelShuffle(2)]
    **return** nn.Sequential(*layers)
```

因此，我们的超分辨率 ResNet（`SrResnet`）将进行卷积，从我们的三个通道到 64 个通道，只是为了稍微丰富一下空间。然后我们实际上有 8 个而不是 5 个 Res 块。请记住，每个 Res 块的步幅都是 1，因此网格大小不会改变，滤波器的数量也不会改变。一直都是 64。我们将再做一次卷积，然后根据我们要求的比例进行上采样。然后我添加了一个批量归一化，因为感觉可能有帮助，只是为了缩放最后一层。最后再进行卷积，回到我们想要的三个通道。因此，你可以看到这里有大量的计算，然后稍微进行一些上采样，就像我们描述的那样。

```py
**class** **SrResnet**(nn.Module):
    **def** __init__(self, nf, scale):
        super().__init__()
        features = [conv(3, 64)]
        **for** i **in** range(8): features.append(res_block(64))
        features += [conv(64,64), upsample(64, 64, scale),
                     nn.BatchNorm2d(64),
                     conv(64, 3)]
        self.features = nn.Sequential(*features)

    **def** forward(self, x): **return** self.features(x)
```

只是提一下，就像我现在倾向于做的那样，整个过程是通过创建一个带有层的列表，然后在最后将其转换为一个顺序模型，因此我的前向函数尽可能简单。

这是我们的上采样，上采样有点有趣，因为它既不是转置卷积也不是分数步长卷积，也不是最近邻上采样后跟着 1x1 卷积。所以让我们稍微谈谈上采样。

这是来自论文《用于实时风格转移和超分辨率的感知损失》的图片。所以他们说“嘿，我们的方法好得多”，但看看他们的方法。里面有一些瑕疵。这些瑕疵到处都是，不是吗。其中一个原因是他们使用了转置卷积，我们都知道不要使用转置卷积。

这里是转置卷积[[35:39](https://youtu.be/nG3tT31nPmQ?t=35m39s)]。这是来自这篇出色的卷积算术论文，也在 Theano 文档中展示过。如果我们从（蓝色是原始图像）3x3 图像升级到 5x5 图像（如果我们添加了一层填充则为 6x6），那么转置卷积所做的就是使用常规的 3x3 卷积，但它在每对像素之间插入白色零像素。这使得输入图像变大，当我们在其上运行这个卷积时，因此会给我们一个更大的输出。但这显然很愚蠢，因为当我们到达这里时，例如，从九个像素中进入的八个是零。所以我们只是浪费了大量的计算。另一方面，如果我们稍微偏离，那么我们九个中有四个是非零的。但是，我们只有一个滤波器/核来使用，所以它不能根据进入的零的数量而改变。所以它必须适用于两者，这是不可能的，所以我们最终得到这些伪像。

[`deeplearning.net/software/theano/tutorial/conv_arithmetic.html`](http://deeplearning.net/software/theano/tutorial/conv_arithmetic.html)

我们学到的一种方法是不要在这里放白色的东西，而是将像素的值复制到这三个位置中的每一个[[36:53](https://youtu.be/nG3tT31nPmQ?t=36m53s)]。所以这是最近邻上采样。这当然好一点，但仍然相当糟糕，因为现在当我们到达这九个（如上所示）时，其中有 4 个是完全相同的数字。当我们移动一个时，现在我们有了完全不同的情况。所以取决于我们在哪里，特别是，如果我们在这里，重复会少得多：

所以再次，我们有这样一个问题，即存在浪费的计算和数据中的太多结构，这将再次导致伪像。因此，上采样比转置卷积更好——最好复制它们而不是用零替换它们。但这仍然不够好。

因此，我们将进行像素洗牌[[37:56](https://youtu.be/nG3tT31nPmQ?t=37m56s)]。像素洗牌是这个次像素卷积神经网络中的一个操作，有点令人费解，但却很迷人。

[**使用高效的次像素卷积神经网络进行实时单图像和视频超分辨率**](https://arxiv.org/abs/1609.05158)

我们从输入开始，经过一些卷积一段时间，直到最终到达第*n[i-1]*层，其中有 n[i-1]个特征图。我们将进行另一个 3x3 卷积，我们的目标是从一个 7x7 的网格单元（我们将进行一个 3x3 的放大），所以我们将扩展到一个 21x21 的网格单元。那么我们还有另一种方法可以做到这一点吗？为了简化，让我们只选择一个面/层-所以让我们取最顶部的滤波器，只对其进行卷积，看看会发生什么。我们要做的是使用一个卷积，其中卷积核大小（滤波器数量）比我们需要的大九倍（严格来说）。所以如果我们需要 64 个滤波器，实际上我们要做的是 64 乘以 9 个滤波器。为什么？这里，r 是比例因子，所以 3²是 9，这里有九个滤波器来覆盖这些输入层/切片中的一个。但我们可以做的是，我们从 7x7 开始，然后将其转换为 7x7x9。我们想要的输出等于 7 乘以 3 乘以 7 乘以 3。换句话说，这里的像素/激活数量与上一步的激活数量相同。所以我们可以重新洗牌这些 7x7x9 的激活，以创建这个 7x3 乘以 7x3 的地图。所以我们要做的是，我们要取这里的一个小管道（所有网格的左上角），我们要把紫色的放在左上角，然后把蓝色的放在右边，淡蓝色的放在右边，稍微深一点的放在最左边的中间，绿色的放在中间，依此类推。所以这些九个单元中的每一个在左上角，它们最终会出现在我们网格的小 3x3 部分中。然后我们要取（2,1）并将所有这 9 个移动到网格的这个 3x3 部分，依此类推。所以我们最终会在 7x3 乘以 7x3 的图像中有每一个这些 7x7x9 的激活。

所以首先要意识到的是，当然这在某种定义下是有效的，因为我们这里有一个可学习的卷积，它将得到一些梯度，这些梯度将尽力填充正确的激活，使得输出是我们想要的东西。所以第一步是意识到这里没有什么特别神奇的地方。我们可以创建任何我们喜欢的架构。我们可以随意移动事物，我们想要的方式，我们的卷积中的权重将尽力做到我们要求的一切。真正的问题是——这是一个好主意吗？这是一个更容易做的事情，也是一个更灵活的事情，比转置卷积或上采样后再进行一对一卷积更好吗？简短的答案是是的，原因很简单，因为这里的卷积发生在低分辨率的 7x7 空间中，这是相当高效的。否则，如果我们首先进行上采样，然后再进行卷积，那么我们的卷积将发生在 21x21 的空间中，这是很多计算。此外，正如我们讨论过的，最近邻上采样版本中存在很多复制和冗余。实际上，他们在这篇论文中展示了这一点，事实上，我认为他们有一个后续的技术说明，其中提供了更多关于正在进行的工作的数学细节，并展示了这种方式确实更有效。所以这就是我们要做的。对于我们的上采样，我们有两个步骤：

1.  3x3 卷积，比我们最初想要的通道数多*r*²倍

1.  然后是一个像素洗牌操作，将每个网格单元中的所有内容移动到遍布其中的小*r*乘以*r*的网格中。

所以这就是：

这只是一行代码。这是一个卷积，输入数量到输出数量乘以四，因为我们正在进行一个比例为 2 的上采样（2²=4）。这是我们的卷积，然后这里是我们的像素洗牌，它内置在 PyTorch 中。像素洗牌是将每个东西移动到正确位置的东西。因此，这将通过一个比例因子为 2 进行上采样。所以我们需要做对数以 2 为底的比例次数。如果比例是四，那么我们将做两次，以便两次两次。这就是这里的上采样所做的事情。

## 棋盘格模式[[44:19](https://youtu.be/nG3tT31nPmQ?t=44m19s)]

太好了。猜猜看。这并没有消除棋盘格模式。我们仍然有棋盘格模式。所以我相信在极度愤怒和沮丧的情况下，来自 Twitter 团队的同一团队，我认为这是在他们被 Twitter 收购之前的一个创业公司叫做魔术小马，他们再次回来，发表了另一篇论文，说好吧，这次我们消除了棋盘格。

[`arxiv.org/abs/1707.02937`](https://arxiv.org/abs/1707.02937)

为什么我们仍然有棋盘格？即使在这样做之后，我们仍然有棋盘格的原因是，当我们在开始时随机初始化这个卷积核时，这意味着这里这个小的 3x3 网格中的每个 9 个像素将会完全随机不同。但接下来的 3 个像素集将彼此随机不同，但将与前一个 3x3 部分中的相应像素非常相似。所以我们将一直有重复的 3x3 东西。然后当我们尝试学习更好的东西时，它是从这个重复的 3x3 起点开始的，这不是我们想要的。实际上，我们想要的是这些 3x3 像素最初是相同的。为了使这些 3x3 像素相同，我们需要使每个滤波器的这 9 个通道在这里相同。因此，这篇论文中的解决方案非常简单。就是当我们在开始时初始化这个卷积时，我们不是完全随机初始化它。我们随机初始化*r*²组通道中的一个，然后将其复制到其他*r*²中，使它们都相同。这样，最初，这些 3x3 将是相同的。这就是所谓的 ICNR，这就是我们马上要使用的。

## 像素损失[[46:41](https://youtu.be/nG3tT31nPmQ?t=46m41s)]

在我们开始之前，让我们快速看一下。所以我们有这个超分辨率的 ResNet，它只是用很多 ResNet 块进行大量计算，然后进行一些上采样，得到我们最终的三个通道输出。

然后为了让生活更快，我们将并行运行这些东西。我们想要并行运行的一个原因是因为 Gerardo 告诉我们他有 6 个 GPU，这就是他的电脑现在的样子。

所以我相信任何拥有多个 GPU 的人以前都有过这种经历。那么我们如何让这些设备一起工作呢？你所需要做的就是将你的 PyTorch 模块包装在`nn.DataParallel`中。一旦你这样做了，它会将它复制到每个 GPU，并自动并行运行。它在两个 GPU 上表现得相当好，三个 GPU 还可以，四个 GPU 及以上，性能就会下降。默认情况下，它会将其复制到所有 GPU 上 - 你可以添加一个 GPU 数组，否则如果你想避免麻烦，例如，我必须与 Yannet 共享我们的盒子，如果我没有把这个放在这里，那么她现在会对我大喊大叫或抵制我的课程。这就是你如何避免与 Yannet 发生麻烦。

```py
m = to_gpu(SrResnet(64, scale))
m = nn.DataParallel(m, [0,2])
learn = Learner(md, SingleModel(m), opt_fn=optim.Adam)
learn.crit = F.mse_loss
```

这里需要注意的一件事是，一旦你这样做了，它实际上会修改你的模块[[48:21](https://youtu.be/nG3tT31nPmQ?t=48m21s)]。所以如果你现在打印出你的模块，比如以前它只是一个无限的顺序，现在你会发现它是一个嵌入在一个名为`Module`的模块内部的`nn.Sequential`。换句话说，如果你保存了一个`nn.DataParallel`的东西，然后尝试将其加载到一个没有`nn.DataParallel`的东西中，它会说它不匹配，因为其中一个嵌入在这个 Module 属性内部，而另一个没有。甚至可能取决于你将其复制到的 GPU ID。两种可能的解决方案：

1.  不要保存模块`m`，而是保存模块属性`m.module`，因为那实际上是非数据并行位。

1.  始终将其放在相同的 GPU ID 上，然后使用数据并行，并每次加载和保存。这就是我使用的方法。

这对我来说很容易在 fast.ai 中自动修复，我很快就会做到，这样它就会自动查找那个模块属性并自动处理。但是现在，我们必须手动操作。了解背后发生的事情可能很有用。

所以我们有了我们的模块[[49:46](https://youtu.be/nG3tT31nPmQ?t=49m46s)]。我发现如果你在 1080Ti 上运行，它会比较快 50%或 60%，如果你在 volta 上运行，它实际上会并行化得更好。有更快的并行化方式，但这是一个超级简单的方式。

我们以通常的方式创建我们的学习器。我们可以在这里使用 MSE 损失，这样就可以比较输出的像素与我们期望的像素。我们可以运行我们的学习率查找器，然后训练一段时间。

```py
learn.lr_find(start_lr=1e-5, end_lr=10000)
learn.sched.plot()31%|███▏      | 225/720 [00:24<00:53,  9.19it/s, loss=0.0482]
```

```py
lr=2e-3learn.fit(lr, 1, cycle_len=1, use_clr_beta=(40,10))2%|▏         | 15/720 [00:02<01:52,  6.25it/s, loss=0.042]  
epoch      trn_loss   val_loss                                 
    0      0.007431   0.008192*[array([0.00819])]*x,y = next(iter(md.val_dl))
preds = learn.model(VV(x))
```

这是我们的输入：

```py
idx=4
show_img(y,idx,normed=**False**)
```

这是我们的输出。

```py
show_img(preds,idx,normed=**False**);
```

你可以看到我们已经成功训练了一个非常先进的残差卷积网络，学会了将事物变蓝。为什么呢？因为这是我们要求的。我们说要最小化 MSE 损失。像素之间的 MSE 损失真的最好的方法就是对像素求平均，即模糊化。所以像素损失不好。所以我们要使用我们的感知损失。

```py
show_img(x,idx,normed=**True**);
```

```py
x,y = next(iter(md.val_dl))
preds = learn.model(VV(x))show_img(y,idx,normed=**False**)
```

```py
show_img(preds,idx,normed=**False**);
```

```py
show_img(x,idx);
```

## 感知损失[50:57]

使用感知损失，我们基本上要拿出我们的 VGG 网络，就像我们上周做的那样，找到在我们得到最大池之前的块索引。

```py
**def** icnr(x, scale=2, init=nn.init.kaiming_normal):
    new_shape = [int(x.shape[0] / (scale ** 2))] + list(x.shape[1:])
    subkernel = torch.zeros(new_shape)
    subkernel = init(subkernel)
    subkernel = subkernel.transpose(0, 1)
    subkernel = subkernel.contiguous().view(subkernel.shape[0],
                                            subkernel.shape[1], -1)
    kernel = subkernel.repeat(1, 1, scale ** 2)
    transposed_shape = [x.shape[1]] + [x.shape[0]] + 
                          list(x.shape[2:])
    kernel = kernel.contiguous().view(transposed_shape)
    kernel = kernel.transpose(0, 1)
    **return** kernelm_vgg = vgg16(**True**)

blocks = [i-1 **for** i,o **in** enumerate(children(m_vgg))
              **if** isinstance(o,nn.MaxPool2d)]
blocks, [m_vgg[i] **for** i **in** blocks]*([5, 12, 22, 32, 42],
 [ReLU(inplace), ReLU(inplace), ReLU(inplace), ReLU(inplace), ReLU(inplace)])*
```

这是每个相同网格大小块的末尾。如果我们将它们打印出来，正如我们所期望的那样，每一个都是一个 ReLU 模块，所以在这种情况下，这最后两个块对我们来说不太有趣。那里的网格大小足够小，当然足够小，对于超分辨率来说并不那么有用。所以我们只会使用前三个。为了节省不必要的计算，我们只会使用 VGG 的前 23 层，然后丢弃其余的。我们会把它放在 GPU 上。我们不会训练这个 VGG 模型——我们只是用它来比较激活。所以我们会将其设置为评估模式，并设置为不可训练。

```py
vgg_layers = children(m_vgg)[:23]
m_vgg = nn.Sequential(*vgg_layers).cuda().eval()
set_trainable(m_vgg, **False**)**def** flatten(x): **return** x.view(x.size(0), -1)
```

就像上周一样，我们将使用`SaveFeatures`类来做一个前向钩子，保存每个层的输出激活[[52:07](https://youtu.be/nG3tT31nPmQ?t=52m7s)]。

```py
**class** **SaveFeatures**():
    features=**None**
    **def** __init__(self, m): 
        self.hook = m.register_forward_hook(self.hook_fn)
    **def** hook_fn(self, module, input, output): self.features = output
    **def** remove(self): self.hook.remove()
```

现在我们已经有了创建我们的感知损失或者我在这里称之为`FeatureLoss`类所需的一切。我们将传入一个层 ID 列表，我们希望计算内容损失的层，以及每个层的权重列表。我们可以遍历每个层 ID 并创建一个具有前向钩子函数来存储激活的对象。所以在我们的前向传播中，我们可以直接调用模型的前向传播，使用目标（我们试图创建的高分辨率图像）。我们这样做的原因是因为这将调用那个钩子函数并将我们想要的激活存储在`self.sfs`（self 点保存特征）中。现在我们还需要对我们的卷积网络输出进行相同的操作。所以我们需要克隆这些，否则卷积网络输出将继续覆盖我已经有的内容。所以现在我们可以对卷积网络输出执行相同的操作，这是损失函数的输入。所以现在我们有了这两个东西，我们可以将它们与权重一起压缩在一起，所以我们有了输入、目标和权重。然后我们可以计算输入和目标之间的 L1 损失，并乘以层权重。我还做的另一件事是我也获取了像素损失，但我将其权重降低了很多。大多数人不这样做。我没有看到有论文这样做，但在我看来，这可能更好一点，因为你有感知内容损失激活的东西，但在最细微的层面上，它也关心个别像素。所以这就是我们的损失函数。

```py
**class** **FeatureLoss**(nn.Module):
    **def** __init__(self, m, layer_ids, layer_wgts):
        super().__init__()
        self.m,self.wgts = m,layer_wgts
        self.sfs = [SaveFeatures(m[i]) **for** i **in** layer_ids]

    **def** forward(self, input, target, sum_layers=**True**):
        self.m(VV(target.data))
        res = [F.l1_loss(input,target)/100]
        targ_feat = [V(o.features.data.clone()) **for** o **in** self.sfs]
        self.m(input)
        res += [F.l1_loss(flatten(inp.features),flatten(targ))*wgt
               **for** inp,targ,wgt **in** zip(self.sfs, targ_feat, 
                                       self.wgts)]
        **if** sum_layers: res = sum(res)
        **return** res

    **def** close(self):
        **for** o **in** self.sfs: o.remove()
```

我们创建我们的超分辨率 ResNet，告诉它要放大多少倍。

```py
m = SrResnet(64, scale)
```

然后我们将对像素混洗卷积进行`icnr`初始化[[54:27](https://youtu.be/nG3tT31nPmQ?t=54m27s)]。这是非常无聊的代码，实际上我是从别人那里抄的。它实际上只是说，好吧，你有一些权重张量`x`，你想要初始化，所以我们将把它视为具有形状（即特征数量）除以比例平方特征的实际特征。所以这可能是 2² = 4，因为我们实际上只想保留一组然后将它们复制四次，所以我们除以四并创建一个相同大小的东西，我们用默认的`kaiming_normal`初始化它。然后我们只需复制它的 scale²份。其余部分只是稍微移动一下轴。所以这将返回一个新的权重矩阵，其中每个初始化的子核被重复 r²或`scale`²次。所以细节并不重要。这里重要的是我只是查找了一下，在像素混洗之前实际的卷积层，并将其存储起来，然后我调用`icnr`来获得我的新权重矩阵。然后我将这个新的权重矩阵复制回那一层。

```py
conv_shuffle = m.features[10][0][0]
kernel = icnr(conv_shuffle.weight, scale=scale)
conv_shuffle.weight.data.copy_(kernel);
```

正如你所看到的，我在这个练习中费了很大的劲，真的尽力去实现所有最佳实践[[56:13](https://youtu.be/nG3tT31nPmQ?t=56m13s)]。我倾向于做事情有点极端。我向你展示了一个只能勉强工作的非常粗糙的版本，或者我会尽最大努力让它真正运行良好。所以这个版本是我声称这几乎是一个最先进的实现。这是一个获奖的竞赛，或者至少是我重新实现的一个获奖方法。我这样做的原因是因为我认为这是那些实际上把很多细节做对的罕见论文之一，我希望你能感受到把所有细节做对的感觉。记住，把细节做对是区分丑陋模糊混乱和漂亮精致结果之间的区别。

```py
m = to_gpu(m)learn = Learner(md, SingleModel(m), opt_fn=optim.Adam)t = torch.load(learn.get_model_path('sr-samp0'), 
         map_location=**lambda** storage, loc: storage)
learn.model.load_state_dict(t, strict=**False**)learn.freeze_to(999)**for** i **in** range(10,13): set_trainable(m.features[i], **True**)conv_shuffle = m.features[10][2][0]
kernel = icnr(conv_shuffle.weight, scale=scale)
conv_shuffle.weight.data.copy_(kernel);
```

所以我们再次对其进行 DataParallel[[57:14](https://youtu.be/nG3tT31nPmQ?t=57m14s)]。

```py
m = nn.DataParallel(m, [0,2])
learn = Learner(md, SingleModel(m), opt_fn=optim.Adam)learn.set_data(md)
```

我们将把我们的标准设置为使用我们的 VGG 模型的 FeatureLoss，获取前几个块，这些是我发现效果非常好的一组层权重。

```py
learn.crit = FeatureLoss(m_vgg, blocks[:3], [0.2,0.7,0.1])lr=6e-3
wd=1e-7
```

进行学习率查找。

```py
learn.lr_find(1e-4, 0.1, wds=wd, linear=**True**) 1%|          | 15/1801 [00:06<12:55,  2.30it/s, loss=0.0965]
12%|█▏        | 220/1801 [01:16<09:08,  2.88it/s, loss=0.42]learn.sched.plot(n_skip_end=1)
```

适应一段时间

```py
learn.fit(lr, 1, cycle_len=2, wds=wd, use_clr=(20,10))epoch      trn_loss   val_loss                                  
    0      0.04523    0.042932  
    1      0.043574   0.041242[array([0.04124])]learn.save('sr-samp0')learn.save('sr-samp1')
```

我花了一段时间来尝试弄清楚一些细节。但这里是我最喜欢的论文部分，接下来会发生什么。现在我们已经为尺度等于 2 做好了准备——渐进式调整大小。渐进式调整大小是让我们在 DAWN 基准上对 ImageNet 训练获得最佳单台计算机结果的技巧。这个想法是从小开始逐渐变大。我只知道有两篇论文使用了这个想法。一篇是 GANs 渐进式调整大小的论文，允许训练非常高分辨率的 GANs，另一篇是 EDSR 论文。渐进式调整大小的酷之处不仅在于，假设你的前几个时期是 2x2 更小，速度快了四倍。你也可以让批量大小可能增加 3 或 4 倍。但更重要的是，它们将更好地泛化，因为在训练过程中你会向模型输入不同尺寸的图像。因此，我们能够为 ImageNet 训练使用一半的时代，比大多数人快。我们的时代更快，而且数量更少。因此，渐进式调整大小是一种特别适合从头开始训练的东西（我不确定它是否对微调迁移学习有用，但如果你是从头开始训练），你可能几乎想一直这样做。

## 渐进式调整大小

接下来的步骤是回到顶部，将尺度改为 4，批量大小为 32，重新启动。在这样做之前，我保存了模型。

回去，这就是为什么在这里重新加载时会有一点混乱，因为现在我需要做的是重新加载我的保存模型。

但有一个小问题，就是现在我有一个比以前多的上采样层，从 2x2 到 4x4。我的循环现在循环两次，而不是一次。因此，它添加了一个额外的卷积网络和一个额外的像素混洗。那么我要如何为不同的网络加载权重呢？

答案是我在 PyTorch 中使用一个非常方便的东西`load_state_dict`。这就是`lean.load`在幕后调用的内容。如果我传递这个参数`strict=False`，那么它会说“好吧，如果你不能填充所有的层，就填充你能填充的层。”因此，在这种方式下加载模型后，我们将得到一个加载了所有可能层的模型，而那个新的卷积层将被随机初始化。

然后我冻结所有的层，然后解冻那个上采样部分。然后在我新添加的额外层上使用`icnr`。然后我可以继续学习。所以接下来的步骤是一样的。

如果你试图复制这个过程，不要只是从头到尾运行。要意识到这需要有一些跳跃。

```py
learn.load('sr-samp1')lr=3e-3learn.fit(lr, 1, cycle_len=1, wds=wd, use_clr=(20,10))epoch      trn_loss   val_loss                                
    0      0.069054   0.06638[array([0.06638])]learn.save('sr-samp2')learn.unfreeze()learn.load('sr-samp2')learn.fit(lr/3, 1, cycle_len=1, wds=wd, use_clr=(20,10))epoch      trn_loss   val_loss           
    0      0.06042    0.057613[array([0.05761])]learn.save('sr1')learn.sched.plot_loss()
```

```py
**def** plot_ds_img(idx, ax=**None**, figsize=(7,7), normed=**True**):
    **if** ax **is** **None**: fig,ax = plt.subplots(figsize=figsize)
    im = md.val_ds[idx][0]
    **if** normed: im = denorm(im)[0]
    **else**:      im = np.rollaxis(to_np(im),0,3)
    ax.imshow(im)
    ax.axis('off')fig,axes=plt.subplots(6,6,figsize=(20,20))
**for** i,ax **in** enumerate(axes.flat): 
    plot_ds_img(i+200,ax=ax, normed=**True**)
```

```py
x,y=md.val_ds[215]y=y[**None**]learn.model.eval()
preds = learn.model(VV(x[**None**]))
x.shape,y.shape,preds.shape*((3, 72, 72), (1, 3, 288, 288), torch.Size([1, 3, 288, 288]))*learn.crit(preds, V(y), sum_layers=**False**)[Variable containing:
 1.00000e-03 *
   1.1935
 [torch.cuda.FloatTensor of size 1 (GPU 0)], Variable containing:
 1.00000e-03 *
   8.5054
 [torch.cuda.FloatTensor of size 1 (GPU 0)], Variable containing:
 1.00000e-02 *
   3.4656
 [torch.cuda.FloatTensor of size 1 (GPU 0)], Variable containing:
 1.00000e-03 *
   3.8243
 [torch.cuda.FloatTensor of size 1 (GPU 0)]]learn.crit.close()
```

训练时间越长，效果就越好。我最终训练了大约 10 个小时，但如果你不那么耐心，仍然可以更快地获得非常好的结果。所以我们可以试一试，这里是结果。左边是我的像素化鸟，右边是放大版本。它实际上发明了着色。但它弄清楚了这是什么鸟，知道这些羽毛应该是什么样子的。因此，它想象出了一组与这些确切像素兼容的羽毛，这是天才。同样适用于头部后面。你无法告诉这些蓝点代表什么。但如果你知道这种鸟在这里有一排羽毛，你就知道它们必须是这样的。然后你可以推断出羽毛必须是这样的，以至于当它们被像素化时它们会出现在这些位置。因此，它根据对这种确切鸟类的了解，逆向工程出了它必须看起来像这样才能创建这个输出。这太神奇了。它还知道周围所有的迹象表明这里（背景）几乎肯定被模糊处理了。因此，它实际上重建了模糊的植被。如果它没有做所有这些事情，它就不会得到如此好的损失函数。因为最终，它必须匹配激活，说“哦，这里有一根羽毛，看起来有点蓬松，朝这个方向”，等等。

```py
_,axes=plt.subplots(1,2,figsize=(14,7))
show_img(x[**None**], 0, ax=axes[0])
show_img(preds,0, normed=**True**, ax=axes[1])
```

好了，这就是超分辨率的结束。别忘了查看[向 Jeremy 提问任何问题](http://forums.fast.ai/t/ask-jeremy-anything/15646/1)的帖子。

# 向 Jeremy 提问

**问题**：fast.ai 和这门课程的未来计划是什么？会有第 3 部分吗？如果有第 3 部分，我真的很想参加。

**Jeremy**：我不太确定。猜测总是很困难的。我希望会有某种后续。去年，在第 2 部分之后，有一名学生发起了一个每周读书俱乐部，通过 Ian Goodfellow 的深度学习书籍，Ian 实际上进来并介绍了很多章节，还有一个专家，每章节都有人介绍。那是一个非常酷的第 3 部分。在很大程度上，这将取决于你们社区，提出想法并帮助实现它们，我肯定愿意帮助。我有很多想法，但我对说出来感到紧张，因为我不确定哪些会发生，哪些不会。但如果你们支持我，让你们想要发生的事情发生，那么它们发生的可能性就更大。

**问题**：你创业的经历是怎样的？你一直是创业者吗，还是从大公司开始，然后转向创业公司？你是从学术界转向创业公司，还是从创业公司转向学术界的？

**Jeremy**：不，我绝对不是学术界的。我完全是一个假学者。我 18 岁时在麦肯锡公司开始工作，那是一家战略公司，这意味着我不能真正去大学，所以我也没有去。然后在商界度过了 8 年，帮助一些大公司解决战略问题。我一直想成为一名企业家，计划只在麦肯锡待两年，我生命中唯一后悔的事情就是没有坚持那个计划，而是浪费了八年。所以两年本来就够了。然后我进入了创业领域，在澳大利亚创办了两家公司。最好的部分是我没有得到任何资金支持，所以我赚的钱都是我的，决策也是我和我的合作伙伴的。我完全专注于利润、产品、客户和服务。而我发现在旧金山，我很高兴来到这里，我和安东尼一起来到这里为 Kaggle 工作，为这家全新的公司筹集了 1100 万美元的资金。这真的很有趣，但也很分散注意力，要担心扩张和风险投资者想看到你的业务发展计划，而且根本没有真正需要实现利润。所以在 Enlitic，我又遇到了同样的问题，我很快又筹集了 1500 万美元，分散了很多注意力。我认为尝试自己创业，专注于通过销售盈利并将利润再投入公司，效果非常好。因为在五年内，我们从第三个月开始盈利，五年内，我们的利润足够不仅支付我们所有人的工资，还能看到我的银行账户在增长，十年后以一大笔钱出售，虽然不足以让风险投资者兴奋，但足以让我不再为钱担心。所以我认为自己创业是一个好主意，至少在旧金山的人似乎不太欣赏这个主意。

**问题**：如果你今天 25 岁，仍然知道你所知道的，你会在哪里寻找使用人工智能的机会？你现在正在做什么，或者在接下来的两年里打算做什么？

**Jeremy**：你应该忽略那个问题的最后部分。我甚至不会回答它。我在哪里寻找并不重要。你应该利用你对领域的知识。我们这样做的主要原因之一是为了让那些在招聘、油田调查、新闻业、活动主义等领域有背景的人解决问题。对你来说，真正的问题会很明显，你拥有的数据在哪里找也会很明显。对其他人来说，这些都是非常困难的部分。所以那些开始时说“哦，我现在懂深度学习了，我会找一些东西来应用它”的人基本上从来没有成功，而那些像“哦，我已经花了 25 年专门为法律公司招聘，我知道关键问题是什么，我知道这个数据完全解决了它，所以我现在就去做，我已经知道该打电话给谁或者开始销售了”的人往往会成功。如果你除了学术研究什么都没做过，那可能更多是关于你的爱好和兴趣。每个人都有爱好。我想说的主要是，请不要专注于为数据科学家或软件工程师构建工具，因为每个数据科学家都了解数据科学家的市场，而只有你了解分析油田调查世界或理解听力学研究等你所做的市场。

**问题**：鉴于您向我们展示了如何将迁移学习从图像识别应用到 NLP，看起来值得关注整个机器学习领域发生的所有发展，如果您专注于某一领域，可能会错过其他领域的一些重大进展。在深入研究您特定领域的同时，如何保持对整个领域的所有进展的了解？

**Jeremy**：是的，这太棒了。我是说这门课程的关键信息之一。在不同地方做了很多好工作，人们都很专业，大多数人都不知道。如果我在开始研究 NLP 六个月后就能获得最先进的结果，我认为这更多地反映了 NLP 而不是我。这有点像创业的事情。你选择你了解的领域，然后转移类似“哦，我们可以使用深度学习来解决这个问题”或者在这种情况下，我们可以使用计算机视觉的这个想法来解决那个问题。所以像迁移学习这样的东西，我敢肯定在其他领域有成千上万的机会让你像 Sebastian 和我在 NLP 中做 NLP 分类那样做。所以回答你的问题的简短答案是保持对正在发生的事情的了解的方法是关注我的 Twitter 收藏夹，我的方法是在 Twitter 上关注很多人，然后将他们放入你的 Twitter 收藏夹。每当我遇到有趣的东西时，我都会点击收藏。我这样做的原因有两个。第一个是当下一门课程出现时，我会浏览我的收藏夹，找出我想学习的东西。第二个是为了让你也可以做同样的事情。然后你深入研究的东西几乎无关紧要。我发现每次我看某件事情时，它都会变得非常有趣和重要。所以选择一些你觉得解决那个问题会真正有用的东西，而且似乎并不很受欢迎，这与其他人的做法恰恰相反。其他人都在解决已经受欢迎的问题，因为它们似乎很受欢迎。我无法完全理解这种思维方式，但它似乎非常普遍。

**问题**：在表格数据上使用深度学习是否过度？什么时候最好在表格数据上使用 DL 而不是 ML？

**Jeremy**：这是一个真正的问题，还是你只是放在那里让我指出 Rachel Thomas 刚写了一篇文章？[`www.fast.ai/2018/04/29/categorical-embeddings/`](http://www.fast.ai/2018/04/29/categorical-embeddings/)

所以 Rachel 刚刚写了这篇文章，Rachel 和我花了很长时间讨论这个问题，简短的答案是我们认为在表格数据上使用深度学习是很棒的。实际上，在 Rachel 的 Twitter 流中出现的所有丰富复杂重要和有趣的事情中，从罗兴亚种族灭绝到 AI 公司最新的伦理违规行为，迄今为止引起社区最多关注和参与的是有关表格数据或结构化数据的问题。所以是的，问计算机人如何命名事物，你会得到很多兴趣。这里有一些来自 Instacart 和 Pinterest 以及其他一些在这一领域做出了一些出色工作的人的链接。如果你们中有人参加了数据研究所的会议，就会看到 Jeremy Stanley 在 Instacart 做的非常酷的工作的演示。

**Rachel**：我在撰写这篇文章时主要依赖于第 1 部分的第 3 和第 4 课，因此其中的许多内容可能对您来说很熟悉。

**Jeremy**: Rachel 在后面问我如何判断是否应该使用决策树集成，如 GBM 或随机森林，还是神经网络，我的答案是我仍然不知道。据我所知，没有人以任何特别有意义的方式进行过这方面的研究。所以这里有一个需要回答的问题，我想。我的方法是尽可能通过 fast.ai 库使这两种方法都尽可能易于使用，这样你就可以尝试它们并看看哪种方法有效。这就是我做的。

**问题**: 强化学习在最近逐渐受到关注。你对强化学习有什么看法？fast.ai 是否考虑在未来涵盖一些流行的强化学习技术？

**Jeremy**: 我仍然不相信强化学习。我认为解决这个问题是一个有趣的问题，但我们并没有一个很好的解决这个问题的方法。问题实际上是延迟奖励问题。所以我想学会玩乒乓球，我向上或向下移动，三分钟后我才知道我是否赢得了乒乓球比赛——我采取的哪些行动实际上是有用的？对我来说，计算输出相对于这些输入的梯度，奖励是如此延迟，以至于这些导数似乎并不那么有趣。到目前为止，在我所教授的四门课程中，我经常被问到这个问题。我总是说同样的话。我很高兴最近终于有一些结果表明，实际上基本上随机搜索往往比强化学习做得更好，所以基本上发生的情况是，拥有大量计算能力的资金充裕的公司将所有资源投入到强化学习问题中，并取得了良好的结果，然后人们就会说“这是因为强化学习”，而不是因为大量的计算资源。或者他们使用非常周到和聪明的算法，比如卷积神经网络和蒙特卡洛树搜索的组合，就像他们在 Alpha Go 项目中所做的那样取得了很好的结果，人们错误地说“这是因为强化学习”，而实际上根本不是强化学习。所以我对解决这些更通用的优化问题非常感兴趣，而不仅仅是预测问题，这些延迟奖励问题看起来就是这样。但我认为我们还没有得到足够好的最佳实践，我没有任何准备好教授的东西，也没有说我必须教你这个东西，因为我认为明年它仍然会有用。所以我们将继续观察并看看会发生什么。

## 超分辨率网络转换为风格转移网络[[1:17:57](https://youtu.be/nG3tT31nPmQ?t=1h17m57s)]

我们现在要把超分辨率网络转换为风格转移网络。我们会很快地完成这个过程。我们基本上已经有了一些东西。*x*是我的输入图像，我将有一些损失函数和一些神经网络。这次我们的输入和输出大小是一样的，所以我们要先做一些下采样。然后是计算，最后是上采样。这是我们要做的第一个改变——我们要在网络的前面添加一些下采样，也就是一些步幅为 2 的卷积层。第二个改变是，不再只是比较*yc*和*x*是否相同。我们基本上要说我们的输入图像应该在最后看起来像它自己。具体来说，我们将通过 VGG 将其传递并在其中一个激活层进行比较。然后它的风格应该看起来像一幅画，我们将像我们用 Gatys 的方法那样通过查看多个层的 Gram 矩阵对应来实现。基本上就是这样。这应该非常简单明了。这实际上是将我们已经做过的两件事结合在一起。

## 风格转移网络

[笔记本](https://github.com/fastai/fastai/blob/master/courses/dl2/style-transfer-net.ipynb)

所以所有这些代码都是相同的，除了我们没有高分辨率和低分辨率，我们只有一个尺寸为 256。

```py
%matplotlib inline
%reload_ext autoreload
%autoreload 2**from** **fastai.conv_learner** **import** *
**from** **pathlib** **import** Path
torch.cuda.set_device(0)torch.backends.cudnn.benchmark=**True**PATH = Path('data/imagenet')
PATH_TRN = PATH/'train'fnames_full,label_arr_full,all_labels = folder_source(PATH, 'train')
fnames_full = ['/'.join(Path(fn).parts[-2:]) **for** fn **in** fnames_full]
list(zip(fnames_full[:5],label_arr_full[:5]))*[('n01440764/n01440764_9627.JPEG', 0),
 ('n01440764/n01440764_9609.JPEG', 0),
 ('n01440764/n01440764_5176.JPEG', 0),
 ('n01440764/n01440764_6936.JPEG', 0),
 ('n01440764/n01440764_4005.JPEG', 0)]*all_labels[:5]*['n01440764', 'n01443537', 'n01484850', 'n01491361', 'n01494475']*np.random.seed(42)
*# keep_pct = 1.*
*# keep_pct = 0.01*
keep_pct = 0.1
keeps = np.random.rand(len(fnames_full)) < keep_pct
fnames = np.array(fnames_full, copy=**False**)[keeps]
label_arr = np.array(label_arr_full, copy=**False**)[keeps]arch = vgg16
*# sz,bs = 96,32*
sz,bs = 256,24
*# sz,bs = 128,32***class** **MatchedFilesDataset**(FilesDataset):
    **def** __init__(self, fnames, y, transform, path):
        self.y=y
        **assert**(len(fnames)==len(y))
        super().__init__(fnames, transform, path)
    **def** get_y(self, i): 
        **return** open_image(os.path.join(self.path, self.y[i]))
    **def** get_c(self): **return** 0val_idxs = get_cv_idxs(len(fnames), val_pct=min(0.01/keep_pct, 0.1))
((val_x,trn_x),(val_y,trn_y)) = split_by_idx(val_idxs, 
                                 np.array(fnames), np.array(fnames))
len(val_x),len(trn_x)(12800, 115206)img_fn = PATH/'train'/'n01558993'/'n01558993_9684.JPEG'tfms = tfms_from_model(arch, sz, tfm_y=TfmType.PIXEL)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y), 
                   (val_x,val_y), tfms, path=PATH_TRN)
md = ImageData(PATH, datasets, bs, num_workers=16, classes=**None**)denorm = md.val_ds.denorm**def** show_img(ims, idx, figsize=(5,5), normed=**True**, ax=**None**):
    **if** ax **is** **None**: fig,ax = plt.subplots(figsize=figsize)
    **if** normed: ims = denorm(ims)
    **else**:      ims = np.rollaxis(to_np(ims),1,4)
    ax.imshow(np.clip(ims,0,1)[idx])
    ax.axis('off')
```

## 模型

我的模型是一样的。这里我做的一件事是我没有使用任何花哨的最佳实践。部分原因是因为似乎没有。与超分辨率的研究相比，对这种方法的跟进非常少。我们稍后会讨论原因。所以你会看到，这看起来更加正常。

```py
**def** conv(ni, nf, kernel_size=3, stride=1, actn=**True**, pad=**None**, 
         bn=**True**):
    **if** pad **is** **None**: pad = kernel_size//2
    layers = [nn.Conv2d(ni, nf, kernel_size, stride=stride,
                          padding=pad, bias=**not** bn)]
    **if** actn: layers.append(nn.ReLU(inplace=**True**))
    **if** bn: layers.append(nn.BatchNorm2d(nf))
    **return** nn.Sequential(*layers)
```

我有批量归一化层。这里没有缩放因子。

```py
**class** **ResSequentialCenter**(nn.Module):
    **def** __init__(self, layers):
        super().__init__()
        self.m = nn.Sequential(*layers) **def** forward(self, x): **return** x[:, :, 2:-2, 2:-2] + self.m(x)**def** res_block(nf):
    **return** ResSequentialCenter([conv(nf, nf, actn=**True**, pad=0), 
              conv(nf, nf, pad=0)])
```

我没有像素混洗 —— 只是使用正常的上采样，然后是 1x1 的卷积。所以这只是更正常的。

```py
**def** upsample(ni, nf):
    **return** nn.Sequential(nn.Upsample(scale_factor=2), conv(ni, nf))
```

他们在论文中提到的一件事是他们在零填充中遇到了很多问题，他们解决这个问题的方法是在开始时添加 40 像素的反射填充。所以我也做了同样的事情，然后他们在他们的 Res 块中的卷积中使用了零填充。现在如果你的 Res 块中的卷积中有零填充，那么你的 ResNet 的两部分将不再相加，因为你在每个卷积的每一侧都失去了一个像素。所以我的`ResSequential`变成了`ResSequentialCenter`，我去掉了那些好细胞的每一侧的最后 2 个像素。除此之外，这基本上和以前一样。

```py
**class** **StyleResnet**(nn.Module):
    **def** __init__(self):
        super().__init__()
        features = [nn.ReflectionPad2d(40),
                    conv(3, 32, 9),
                    conv(32, 64, stride=2), conv(64, 128, stride=2)]
        **for** i **in** range(5): features.append(res_block(128))
        features += [upsample(128, 64), upsample(64, 32),
                     conv(32, 3, 9, actn=**False**)]
        self.features = nn.Sequential(*features)

    **def** forward(self, x): **return** self.features(x)
```

## 风格图像

然后我们可以引入我们的星夜图片。

```py
style_fn = PATH/'style'/'starry_night.jpg'
style_img = open_image(style_fn)
style_img.shape*(1198, 1513, 3)*plt.imshow(style_img);
```

```py
h,w,_ = style_img.shape
rat = max(sz/h,sz/h)
res = cv2.resize(style_img, (int(w*rat), int(h*rat)), interpolation=cv2.INTER_AREA)
resz_style = res[:sz,-sz:]
```

我们可以调整大小。

```py
plt.imshow(resz_style);
```

我们可以通过我们的变换

```py
style_tfm,_ = tfms1style_tfm = np.broadcast_to(style_tfm[**None**], (bs,)+style_tfm.shape)
```

为了让我的大脑更容易处理这种方法，我拿出了我们的变换风格图像，经过 3 x 256 x 256 的变换后，我制作了一个小批量。我的批量大小是 24 — 有 24 个副本。这样做可以更容易地进行批量算术，而不用担心一些广播问题。它们实际上并不是 24 个副本。我使用`np.broadcast`基本上伪造了 24 个部分。

```py
style_tfm.shape(24, 3, 256, 256)
```

## 感知损失

所以就像以前一样，我们创建了一个 VGG，抓住了最后一个块。这一次我们要使用所有这些层，所以我们保留了所有直到第 43 层的内容。

```py
m_vgg = vgg16(**True**)blocks = [i-1 **for** i,o **in** enumerate(children(m_vgg))
              **if** isinstance(o,nn.MaxPool2d)]
blocks, [m_vgg[i] **for** i **in** blocks[1:]]*([5, 12, 22, 32, 42],
 [ReLU(inplace), ReLU(inplace), ReLU(inplace), ReLU(inplace)])*vgg_layers = children(m_vgg)[:43]
m_vgg = nn.Sequential(*vgg_layers).cuda().eval()
set_trainable(m_vgg, **False**)**def** flatten(x): **return** x.view(x.size(0), -1)**class** **SaveFeatures**():
    features=**None**
    **def** __init__(self, m): 
        self.hook = m.register_forward_hook(self.hook_fn)
    **def** hook_fn(self, module, input, output): self.features = output
    **def** remove(self): self.hook.remove()**def** ct_loss(input, target): **return** F.mse_loss(input,target)**def** gram(input):
        b,c,h,w = input.size()
        x = input.view(b, c, -1)
        **return** torch.bmm(x, x.transpose(1,2))/(c*h*w)*1e6**def** gram_loss(input, target):
    **return** F.mse_loss(gram(input), gram(target[:input.size(0)]))
```

所以现在我们的组合损失将加上第三个块的内容损失，再加上所有块的 Gram 损失，使用不同的权重。再次回到尽可能正常的一切，我又回到了使用均方误差。基本上发生的事情是我在训练这个模型时遇到了很多困难。所以我逐渐去掉了一个又一个技巧，最终只是说“好吧，我只会让它尽可能平淡”。

上周的 Gram 矩阵是错误的。它只适用于批量大小为 1，而我们只有一个批量大小，所以没问题。我使用的是矩阵乘法，这意味着每个批次都与其他每个批次进行比较。实际上，你需要使用批量矩阵乘法（`torch.bmm`），它对每个批次执行矩阵乘法。所以这是需要注意的一点。

```py
**class** **CombinedLoss**(nn.Module):
    **def** __init__(self, m, layer_ids, style_im, ct_wgt, style_wgts):
        super().__init__()
        self.m,self.ct_wgt,self.style_wgts = m,ct_wgt,style_wgts
        self.sfs = [SaveFeatures(m[i]) **for** i **in** layer_ids]
        m(VV(style_im))
        self.style_feat = [V(o.features.data.clone()) 
                              **for** o **in** self.sfs] **def** forward(self, input, target, sum_layers=**True**):
        self.m(VV(target.data))
        targ_feat = self.sfs[2].features.data.clone()
        self.m(input)
        inp_feat = [o.features **for** o **in** self.sfs]

        res = [ct_loss(inp_feat[2],V(targ_feat)) * self.ct_wgt]
        res += [gram_loss(inp,targ)*wgt **for** inp,targ,wgt
                **in** zip(inp_feat, self.style_feat, self.style_wgts)]

        **if** sum_layers: res = sum(res)
        **return** res

    **def** close(self):
        **for** o **in** self.sfs: o.remove()
```

所以我有 Gram 矩阵，我在 Gram 矩阵之间进行均方误差损失，我用风格权重对它们进行加权，所以我创建了那个 ResNet。

```py
m = StyleResnet()
m = to_gpu(m)learn = Learner(md, SingleModel(m), opt_fn=optim.Adam)
```

我创建了我的组合损失，传入 VGG 网络，传入块 ID，传入变换后的星夜图像，你会看到这里的开始，我通过我的 VGG 模型进行了前向传递，以保存其特征。请注意，现在非常重要的是我不做任何数据增强，因为我保存了特定未增强版本的风格特征。所以如果我增强它，可能会出现一些小问题。但没关系，因为我有所有的 ImageNet 要处理。我实际上不需要做数据增强。

```py
learn.crit = CombinedLoss(m_vgg, blocks[1:], style_tfm, 1e4,
                             [0.025,0.275,5.,0.2])wd=1e-7learn.lr_find(wds=wd)
learn.sched.plot(n_skip_end=1) 1%|▏         | 7/482 [00:04<05:32,  1.43it/s, loss=2.48e+04] 
 53%|█████▎    | 254/482 [02:27<02:12,  1.73it/s, loss=1.13e+12]
```

```py
lr=5e-3
```

所以我有我的损失函数，我可以继续拟合[[1:24:06](https://youtu.be/nG3tT31nPmQ?t=1h24m6s)]。这里一点聪明的地方都没有。

```py
learn.fit(lr, 1, cycle_len=1, wds=wd, use_clr=(20,10))epoch      trn_loss   val_loss                               
    0      105.351372 105.833994[array([105.83399])]learn.save('style-2')x,y=md.val_ds[201]learn.model.eval()
preds = learn.model(VV(x[**None**]))
x.shape,y.shape,preds.shape*((3, 256, 256), (3, 256, 256), torch.Size([1, 3, 256, 256]))*
```

最后，我有我的`sum_layers=False`，这样我就可以看到每个部分的样子，看到它们是平衡的。然后我终于可以弹出它

```py
learn.crit(preds, VV(y[**None**]), sum_layers=**False**)*[Variable containing:
  53.2221
 [torch.cuda.FloatTensor of size 1 (GPU 0)], Variable containing:
  3.8336
 [torch.cuda.FloatTensor of size 1 (GPU 0)], Variable containing:
  4.0612
 [torch.cuda.FloatTensor of size 1 (GPU 0)], Variable containing:
  5.0639
 [torch.cuda.FloatTensor of size 1 (GPU 0)], Variable containing:
  53.0019
 [torch.cuda.FloatTensor of size 1 (GPU 0)]]*learn.crit.close()_,axes=plt.subplots(1,2,figsize=(14,7))
show_img(x[**None**], 0, ax=axes[0])
show_img(preds, 0, ax=axes[1])
```

所以我提到这应该很容易，但实际上花了我大约 4 天，因为我发现这个真的很麻烦，才让它正常工作[[1:24:26](https://youtu.be/nG3tT31nPmQ?t=1h24m26s)]。所以当我终于早上起床时，我对 Rachel 说“猜猜，它训练正确了。” Rachel 说“我从来没想过会发生这种事。” 它看起来一直很糟糕，真的是关于得到精确的内容损失和风格损失的混合以及风格损失的层次的混合。最糟糕的部分是训练这个该死的 CNN 需要很长时间，我真的不知道应该训练多久才能确定它表现不佳。我应该只是继续训练吗？我不知道所有这些细节似乎都没有稍微改变它，但它总是会完全崩溃。所以我提到这部分是为了提醒大家，最终你在这里看到的答案是在我整整一周把自己逼疯几乎总是不起作用，直到最后一刻它终于起作用。即使对于那些看起来不可能困难的事情，因为那是将两个我们已经有的工作结合在一起。另一个是要小心解释作者声称的内容。

让这个风格转移起作用真的很麻烦[[1:26:10](https://youtu.be/nG3tT31nPmQ?t=1h26m10s)]。做完之后，我想为什么我要费这个劲，因为现在我有了一个需要花几个小时来创建一个可以将任何类型的照片转换为一个特定风格的网络。我觉得我很少会想要这样做。我能想到这有用的唯一原因是在视频上做一些艺术性的东西，我想把每一帧都转换成某种风格。这是一个极其狭隘的想法。但当我看了论文后，表格上写着“哦，我们比 Gatys 的方法快一千倍”，这种说法显然毫无意义。这是一个极其误导人的说法，因为它忽略了为每种风格进行的所有训练时间，我发现这很令人沮丧，因为像斯坦福这样的团体显然更清楚或应该更清楚，但仍然我猜学术界鼓励人们提出这些荒谬的夸大宣称。它也完全忽视了这个极其敏感的繁琐的训练过程，所以这篇论文一出来就被如此广泛接受。我记得每个人都在推特上说“哇，你知道这些斯坦福的人找到了这种方式可以让风格转移快一千倍。” 显然说这话的人是该领域的顶尖研究人员，显然他们中没有人真正理解，因为没有人说“我不明白为什么这有任何用处，而且我尝试过，让它正常工作真的很麻烦。” 直到 18 个月后，我最终回头看，有点想“等一下，这有点愚蠢。” 所以我认为这就是为什么人们没有对此进行后续研究，以创造真正令人惊叹的最佳实践和更好的方法，就像论文中的超分辨率部分一样。我认为答案是因为这很愚蠢。所以我认为论文中的超分辨率部分显然不愚蠢。它已经得到改进，现在我们有了很棒的超分辨率。我认为我们可以从中得到很棒的降噪、很棒的着色、很棒的倾斜去除、很棒的交互式伪影去除等等。所以我认为这里有很多很酷的技术。它还利用了我们一直在学习和不断进步的许多东西。

# 分割[[1:29:13](https://youtu.be/nG3tT31nPmQ?t=1h29m13s)]

最后，让我们谈谈分割。这来自著名的 CamVid 数据集，这是一个学术分割数据集的经典示例。基本上你可以看到我们的做法是从一幅图片开始（实际上在这个数据集中是视频帧），我们有一些标签，它们实际上不是颜色 - 每个标签都有一个 ID，这些 ID 映射到颜色。所以红色可能是 1，紫色可能是 2，浅粉色可能是 3，等等。所以所有建筑物属于一类，所有汽车属于另一类，所有人属于另一类，所有道路属于另一类，依此类推。所以我们实际上在这里为每个像素进行多类分类。你可以看到，有时多类分类确实非常棘手 - 就像这些分支。尽管有时标签实际上并不是那么好。正如你所看到的，这非常粗糙。这就是我们要做的。

我们将进行分割，所以这很像边界框。但与其只是找到每个物体周围的框，我们实际上要为每个像素标记其类别。实际上，这实际上要容易得多，因为它非常适合我们的 CNN 风格，我们可以创建任何输出为 N 乘以 M 网格的 CNN，其中包含从 0 到 C 的整数，其中 C 是类别数。然后我们可以使用 softmax 激活的交叉熵损失，然后就完成了。我实际上可以在这里停止课程，你可以使用在第 1 和第 2 课中学到的完全相同的方法，你会得到一个完全可以接受的结果。所以首先要说的是，这实际上并不是一件非常困难的事情。但我们将尽力做得更好。

## 以简单的方式进行[[1:31:26](https://youtu.be/nG3tT31nPmQ?t=1h31m26s)]

[笔记本](https://github.com/fastai/fastai/blob/master/courses/dl2/carvana.ipynb)

让我们从最简单的方式开始。我们将使用 Kaggle [Carvana](https://www.kaggle.com/c/carvana-image-masking-challenge)比赛，你可以像往常一样使用 Kaggle API 下载它。

```py
%matplotlib inline
%reload_ext autoreload
%autoreload 2**from** **fastai.conv_learner** **import** *
**from** **fastai.dataset** **import** *

**from** **pathlib** **import** Path
**import** **json**
```

## 设置

有一个包含一堆图像的训练文件夹，这是自变量，还有一个 train_masks 文件夹，这是因变量，它们看起来像下面这样。

在这种情况下，就像猫和狗一样，我们选择简单的方式，而不是进行多类分类，我们将进行二元分类。但当然，多类分类只是更一般的版本 - 分类交叉熵或二元分类熵。在概念上没有区别，因此因变量只是零和一，而自变量是常规图像。

为了做到这一点，真的很有帮助知道汽车是什么样子的。因为我们真正想做的是弄清楚这是一辆车，以及它的方向，并根据图片和他们对汽车外观的理解，在我们期望汽车出现的地方放置白色像素。

```py
PATH = Path('data/carvana')
list(PATH.iterdir())*[PosixPath('data/carvana/train_masks.csv'),
 PosixPath('data/carvana/train_masks-128'),
 PosixPath('data/carvana/sample_submission.csv'),
 PosixPath('data/carvana/train_masks_png'),
 PosixPath('data/carvana/train.csv'),
 PosixPath('data/carvana/train-128'),
 PosixPath('data/carvana/train'),
 PosixPath('data/carvana/metadata.csv'),
 PosixPath('data/carvana/tmp'),
 PosixPath('data/carvana/models'),
 PosixPath('data/carvana/train_masks')]*MASKS_FN = 'train_masks.csv'
META_FN = 'metadata.csv'
TRAIN_DN = 'train'
MASKS_DN = 'train_masks'masks_csv = pd.read_csv(PATH/MASKS_FN)
masks_csv.head()
```

原始数据集还附带了这些 CSV 文件[[1:32:44](https://youtu.be/nG3tT31nPmQ?t=1h32m44s)]。我实际上并没有用它们做很多其他事情，只是从中获取图像列表。

```py
meta_csv = pd.read_csv(PATH/META_FN)
meta_csv.head()
```

```py
**def** show_img(im, figsize=**None**, ax=**None**, alpha=**None**):
    **if** **not** ax: fig,ax = plt.subplots(figsize=figsize)
    ax.imshow(im, alpha=alpha)
    ax.set_axis_off()
    **return** axCAR_ID = '00087a6bd4dc'list((PATH/TRAIN_DN).iterdir())[:5][PosixPath('data/carvana/train/5ab34f0e3ea5_15.jpg'),
 PosixPath('data/carvana/train/de3ca5ec1e59_07.jpg'),
 PosixPath('data/carvana/train/28d9a149cb02_13.jpg'),
 PosixPath('data/carvana/train/36a3f7f77e85_12.jpg'),
 PosixPath('data/carvana/train/843763f47895_08.jpg')]Image.open(PATH/TRAIN_DN/f'**{CAR_ID}**_01.jpg').resize((300,200))
```

```py
list((PATH/MASKS_DN).iterdir())[:5][PosixPath('data/carvana/train_masks/6c0cd487abcd_03_mask.gif'),
 PosixPath('data/carvana/train_masks/351c583eabd6_01_mask.gif'),
 PosixPath('data/carvana/train_masks/90fdd8932877_02_mask.gif'),
 PosixPath('data/carvana/train_masks/28d9a149cb02_10_mask.gif'),
 PosixPath('data/carvana/train_masks/88bc32b9e1d9_14_mask.gif')]Image.open(PATH/MASKS_DN/f'**{CAR_ID}**_01_mask.gif').resize((300,200))
```

每张图片在车辆 ID 之后都有一个 01、02 等，我已经打印出其中一个车辆的所有 16 个方向，正如你所看到的，基本上这些数字是一个车辆的 16 个方向[[1:32:58](https://youtu.be/nG3tT31nPmQ?t=1h32m58s)]。我认为在这个比赛中没有人实际上使用这些方向信息。我相信他们都保留了车辆的图像，只是单独处理它们。

```py
ims = [open_image(PATH/TRAIN_DN/f'**{CAR_ID}**_{i+1:02d}.jpg') 
          **for** i **in** range(16)]fig, axes = plt.subplots(4, 4, figsize=(9, 6))
**for** i,ax **in** enumerate(axes.flat): show_img(ims[i], ax=ax)
plt.tight_layout(pad=0.1)
```

## 调整大小和转换[[1:33:27](https://youtu.be/nG3tT31nPmQ?t=1h33m27s)]

这些图像非常大 - 大小超过 1000 乘以 1000，只是打开 JPEG 并调整它们的大小很慢。所以我对它们进行了处理。此外，OpenCV 无法处理 GIF 文件，因此我对它们进行了转换。

**问题**：有人最初如何获得这些用于训练的蒙版？[Mechanical turk](https://www.mturk.com/)或其他什么[[1:33:48](https://youtu.be/nG3tT31nPmQ?t=1h33m48s)]？是的，只是很多无聊的工作。可能有一些工具可以帮助你进行一些边缘捕捉，这样人类可以粗略地完成，然后只需微调它错误的部分。这种标签是昂贵的。所以我真正想要做的事情之一是增强深度学习交互式标注工具，因为这显然是可以帮助很多人的事情。

我这里有一个小节，如果你想的话可以运行。你可能想要。它将 GIF 转换为 PNG，所以只需用 PIL 打开它，然后保存为 PNG，因为 OpenCV 不支持 GIF。像往常一样，对于这种类型的东西，我使用线程池，这样我就可以利用并行处理。然后创建一个单独的目录`train-128`和`train_masks-128`，其中包含它们的 128x128 调整大小版本。

这是在过程早期进行的工作，可以让你保持理智的工作。所以每当你获得新的数据集时，认真考虑创建一个较小的版本以加快速度。每当你发现自己在电脑上等待时，尝试想出一种创建较小版本的方法。

```py
(PATH/'train_masks_png').mkdir(exist_ok=**True**)**def** convert_img(fn):
    fn = fn.name
    Image.open(PATH/'train_masks'/fn).save(PATH/'train_masks_png'/
                     f'**{fn[:-4]}**.png')files = list((PATH/'train_masks').iterdir())
**with** ThreadPoolExecutor(8) **as** e: e.map(convert_img, files)(PATH/'train_masks-128').mkdir(exist_ok=**True**)**def** resize_mask(fn):
    Image.open(fn).resize((128,128)).save((fn.parent.parent)
        /'train_masks-128'/fn.name)

files = list((PATH/'train_masks_png').iterdir())
**with** ThreadPoolExecutor(8) **as** e: e.map(resize_img, files)(PATH/'train-128').mkdir(exist_ok=**True**)**def** resize_img(fn):
    Image.open(fn).resize((128,128)).save((fn.parent.parent)
         /'train-128'/fn.name)

files = list((PATH/'train').iterdir())
**with** ThreadPoolExecutor(8) **as** e: e.map(resize_img, files)
```

所以在你从 Kaggle 获取它之后，你可能想要运行这些东西，离开，吃午餐，回来时，当你完成时，你将拥有这些较小的目录，我们将从 128x128 开始使用。

## 数据集[[1:35:33](https://youtu.be/nG3tT31nPmQ?t=1h35m33s)]

```py
TRAIN_DN = 'train-128'
MASKS_DN = 'train_masks-128'
sz = 128
bs = 64ims = [open_image(PATH/TRAIN_DN
            /f'**{CAR_ID}**_{i+1:02d}.jpg') **for** i **in** range(16)]
im_masks = [open_image(PATH/MASKS_DN
            /f'**{CAR_ID}**_{i+1:02d}_mask.png') **for** i **in** range(16)]
```

这里有一个很酷的技巧。如果你使用相同的轴对象（`ax`）两次绘制图像，第二次使用 alpha，你可能知道在计算机视觉世界中意味着透明度，那么你实际上可以在照片的顶部绘制蒙版。这是一个很好的方法，可以看到所有车辆组中所有照片顶部的所有蒙版。

```py
fig, axes = plt.subplots(4, 4, figsize=(9, 6))
**for** i,ax **in** enumerate(axes.flat):
    ax = show_img(ims[i], ax=ax)
    show_img(im_masks[i][...,0], ax=ax, alpha=0.5)
plt.tight_layout(pad=0.1)
```

这是我们已经看过两次的相同的 MatchedFilesDataset。这是相同的代码。这里有一些重要的东西。如果我们在训练集中有左边的图像，然后验证集中有右边的图像，那将是一种作弊，因为它是相同的车辆。

```py
**class** **MatchedFilesDataset**(FilesDataset):
    **def** __init__(self, fnames, y, transform, path):
        self.y=y
        **assert**(len(fnames)==len(y))
        super().__init__(fnames, transform, path)
    **def** get_y(self, i): 
        **return** open_image(os.path.join(self.path, self.y[i]))
    **def** get_c(self): **return** 0x_names = np.array([Path(TRAIN_DN)/o **for** o **in** masks_csv['img']])
y_names = np.array([Path(MASKS_DN)/f'**{o[:-4]}**_mask.png' 
                       **for** o **in** masks_csv['img']])len(x_names)//16//5*16*1008*
```

所以我们使用一系列连续的汽车 ID，由于每个集合是一组 16 个，我们确保可以被 16 整除。因此，我们确保我们的验证集包含与训练集不同的汽车 ID。这是你必须小心的事情。在 Kaggle 上，情况并不那么糟糕 - 你会知道，因为你会提交你的结果，你的排行榜上的结果会与你的验证集有很大不同。但在现实世界中，你不会知道，直到你投入生产并让公司破产并失去工作。所以在这种情况下，你可能需要仔细考虑你的验证集。

```py
val_idxs = list(range(1008))
((val_x,trn_x),(val_y,trn_y)) = split_by_idx(val_idxs, x_names, 
                                              y_names)
len(val_x),len(trn_x)*(1008, 4080)*
```

在这里，我们将使用转换类型分类（`TfmType.CLASS`）[[1:37:03](https://youtu.be/nG3tT31nPmQ?t=1h37m3s)]。这基本上与转换类型像素（`TfmType.PIXEL`）相同，但是如果你考虑一下，对于像素版本，如果我们旋转一点，那么我们可能希望在两者之间平均像素，但是分类，显然我们不需要。我们使用最近邻。所以这里有一点不同。此外，对于分类，光照不起作用，归一化不起作用于因变量。

```py
aug_tfms = [RandomRotate(4, tfm_y=TfmType.CLASS),
            RandomFlip(tfm_y=TfmType.CLASS),
            RandomLighting(0.05, 0.05)]
*# aug_tfms = []*
```

它们已经是方形图像，所以我们不必进行任何裁剪。

```py
tfms = tfms_from_model(resnet34, sz, crop_type=CropType.NO, tfm_y=TfmType.CLASS, aug_tfms=aug_tfms)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y), (val_x,val_y), tfms, path=PATH)
md = ImageData(PATH, datasets, bs, num_workers=8, classes=**None**)denorm = md.trn_ds.denorm
x,y = next(iter(md.aug_dl))
x = denorm(x)
```

所以在这里你可以看到增强图像的不同版本 - 它们在移动一点，旋转一点，等等。

```py
fig, axes = plt.subplots(5, 6, figsize=(12, 10))
**for** i,ax **in** enumerate(axes.flat):
    ax=show_img(x[i], ax=ax)
    show_img(y[i], ax=ax, alpha=0.5)
plt.tight_layout(pad=0.1)
```

在我们的学习小组中，我经常被问到如何调试和修复不起作用的东西。我从来没有一个很好的答案，除了每次我解决问题都是因为我经常做这样的事情。我总是在进行过程中打印出所有内容，然后我搞砸的那一件事总是最后发现是我忘记检查的那一件事。你能做这种事情的越多越好。如果你不看所有的中间结果，你会遇到麻烦。

## 模型[[1:38:30](https://youtu.be/nG3tT31nPmQ?t=1h38m30s)]

```py
**class** **Empty**(nn.Module): 
    **def** forward(self,x): **return** x

models = ConvnetBuilder(resnet34, 0, 0, 0, custom_head=Empty())
learn = ConvLearner(md, models)
learn.summary()**class** **StdUpsample**(nn.Module):
    **def** __init__(self, nin, nout):
        super().__init__()
        self.conv = nn.ConvTranspose2d(nin, nout, 2, stride=2)
        self.bn = nn.BatchNorm2d(nout)

    **def** forward(self, x): **return** self.bn(F.relu(self.conv(x)))flatten_channel = Lambda(**lambda** x: x[:,0])simple_up = nn.Sequential(
    nn.ReLU(),
    StdUpsample(512,256),
    StdUpsample(256,256),
    StdUpsample(256,256),
    StdUpsample(256,256),
    nn.ConvTranspose2d(256, 1, 2, stride=2),
    flatten_channel
)
```

考虑到我们想要一个知道汽车长什么样的东西，我们可能想要从一个预训练的 ImageNet 网络开始。所以我们将从 ResNet34 开始。使用`ConvnetBuilder`，我们可以获取我们的 ResNet34 并添加一个自定义头部。自定义头部将是一些上采样的东西，现在我们将做一些非常愚蠢的事情，就是我们只是做一个 ConvTranspose2d，批量规范化，ReLU。

这就是我说的 - 任何人都可以在不看任何笔记本的情况下构建这个，或者至少你有来自以前课程的信息。这里没有任何新东西。所以最后，我们有一个单一的过滤器。现在这将给我们一个批量大小为 1 乘以 128 乘以 128。但我们想要的是批量大小为 128 乘以 128。所以我们必须去掉那个单元轴，所以我在这里有一个 lambda 层。Lambda 层非常有帮助，因为没有这个 lambda 层，它只是通过索引 0 来删除那个单元轴，没有 lambda 层，我将不得不创建一个自定义类，具有自定义的前向方法等等。但通过创建一个 lambda 层来执行一个自定义操作，我现在可以将其放入 Sequential 中，这样就更容易了。

PyTorch 的人们对这种方法有点傲慢。Lambda 层实际上是 fastai 库的一部分，而不是 PyTorch 库的一部分。而且 PyTorch 讨论板上的人们说“是的，我们可以给人们这个”，“是的，这只是一行代码”，但他们从不鼓励他们过于频繁地使用 Sequential。所以你看。

这是我们的自定义头部[[1:40:36](https://youtu.be/nG3tT31nPmQ?t=1h40m36s)]。所以我们将有一个 ResNet 34 进行下采样，然后一个非常简单的自定义头部，非常快速地上采样，希望这样做一些事情。我们将使用阈值为 0.5 的准确度并打印出指标。

```py
models = ConvnetBuilder(resnet34, 0, 0, 0, custom_head=simple_up)
learn = ConvLearner(md, models)
learn.opt_fn=optim.Adam
learn.crit=nn.BCEWithLogitsLoss()
learn.metrics=[accuracy_thresh(0.5)]learn.lr_find()
learn.sched.plot()94%|█████████▍| 30/32 [00:05<00:00,  5.48it/s, loss=10.6]
```

```py
lr=4e-2learn.fit(lr,1,cycle_len=5,use_clr=(20,5))*epoch      trn_loss   val_loss   <lambda>                  
    0      0.124078   0.133566   0.945951  
    1      0.111241   0.112318   0.954912                  
    2      0.099743   0.09817    0.957507                   
    3      0.090651   0.092375   0.958117                   
    4      0.084031   0.086026   0.963243**[0.086025625, 0.96324310824275017]*
```

经过几个时代，我们得到了 96%的准确率。这好吗[[1:40:56](https://youtu.be/nG3tT31nPmQ?t=1h40m56s)]？96%的准确率好吗？希望对这个问题的答案是取决于。这是为了什么？答案是 Carvana 想要这个，因为他们想要能够拍摄他们的汽车图像并将它们剪切并粘贴到异国情调的蒙特卡洛背景或其他地方（这是蒙特卡洛的地方，而不是模拟）。为了做到这一点，你需要一个非常好的蒙版。你不想留下后视镜，缺少一个车轮，或者包括一点背景之类的东西。那看起来很愚蠢。所以你需要一些非常好的东西。所以只有 96%的像素正确并不听起来很好。但我们真的不知道直到我们看到它。所以让我们看看。

```py
learn.save('tmp')learn.load('tmp')py,ay = learn.predict_with_targs()ay.shape*(1008, 128, 128)*
```

所以这是我们想要剪切的正确版本[[1:41:54](https://youtu.be/nG3tT31nPmQ?t=1h41m54s)]

```py
show_img(ay[0]);
```

这是 96%准确的版本。所以当你看到它时，你会意识到“哦，是的，准确地获取 96%的像素实际上很容易，因为所有外部部分都不是汽车，所有内部部分都是汽车，而真正有趣的部分是边缘。所以我们需要做得更好。

```py
show_img(py[0]>0);
```

让我们解冻，因为到目前为止我们只训练了自定义头部。让我们做更多。

```py
learn.unfreeze()learn.bn_freeze(**True**)lrs = np.array([lr/100,lr/10,lr])/4learn.fit(lrs,1,cycle_len=20,use_clr=(20,10))*epoch      trn_loss   val_loss   <lambda>                   
    0      0.06577    0.053292   0.972977  
    1      0.049475   0.043025   0.982559                   
    2      0.039146   0.035927   0.98337                    
    3      0.03405    0.031903   0.986982                   
    4      0.029788   0.029065   0.987944                   
    5      0.027374   0.027752   0.988029                   
    6      0.026041   0.026718   0.988226                   
    7      0.024302   0.025927   0.989512                   
    8      0.022921   0.026102   0.988276                   
    9      0.021944   0.024714   0.989537                   
    10     0.021135   0.0241     0.990628                   
    11     0.020494   0.023367   0.990652                   
    12     0.01988    0.022961   0.990989                   
    13     0.019241   0.022498   0.991014                   
    14     0.018697   0.022492   0.990571                   
    15     0.01812    0.021771   0.99105                    
    16     0.017597   0.02183    0.991365                   
    17     0.017192   0.021434   0.991364                   
    18     0.016768   0.021383   0.991643                   
    19     0.016418   0.021114   0.99173**[0.021113895, 0.99172959849238396]*
```

再经过一段时间，我们得到了 99.1%。这好吗？我不知道。让我们看看。

```py
learn.save('0')x,y = next(iter(md.val_dl))
py = to_np(learn.model(V(x)))
```

实际上不是。它完全错过了左侧的后视镜，右侧也错过了很多。底部的边缘明显错了。当我们尝试剪裁时，这些事情完全会影响到，所以还不够好。

```py
ax = show_img(denorm(x)[0])
show_img(py[0]>0, ax=ax, alpha=0.5);
```

```py
ax = show_img(denorm(x)[0])
show_img(y[0], ax=ax, alpha=0.5);
```

## 512x512

让我们尝试放大。很好的一点是，当我们将其放大到 512x512 时（确保减少批量大小，因为你会耗尽内存），有更多的信息供其使用，因此我们的准确性提高到 99.4%，事情一直在变得更好。

```py
TRAIN_DN = 'train'
MASKS_DN = 'train_masks_png'
sz = 512
bs = 16x_names = np.array([Path(TRAIN_DN)/o **for** o **in** masks_csv['img']])
y_names = np.array([Path(MASKS_DN)/f'**{o[:-4]}**_mask.png' 
                      **for** o **in** masks_csv['img']])((val_x,trn_x),(val_y,trn_y)) = split_by_idx(val_idxs, x_names, 
                                      y_names)
len(val_x),len(trn_x)*(1008, 4080)*tfms = tfms_from_model(resnet34, sz, crop_type=CropType.NO,
                         tfm_y=TfmType.CLASS, aug_tfms=aug_tfms)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y),
                      (val_x,val_y), tfms, path=PATH)
md = ImageData(PATH, datasets, bs, num_workers=8, classes=**None**)denorm = md.trn_ds.denorm
x,y = next(iter(md.aug_dl))
x = denorm(x)
```

这是真实的。

```py
fig, axes = plt.subplots(4, 4, figsize=(10, 10))
**for** i,ax **in** enumerate(axes.flat):
    ax=show_img(x[i], ax=ax)
    show_img(y[i], ax=ax, alpha=0.5)
plt.tight_layout(pad=0.1)
```

```py
simple_up = nn.Sequential(
    nn.ReLU(),
    StdUpsample(512,256),
    StdUpsample(256,256),
    StdUpsample(256,256),
    StdUpsample(256,256),
    nn.ConvTranspose2d(256, 1, 2, stride=2),
    flatten_channel
)models = ConvnetBuilder(resnet34, 0, 0, 0, custom_head=simple_up)
learn = ConvLearner(md, models)
learn.opt_fn=optim.Adam
learn.crit=nn.BCEWithLogitsLoss()
learn.metrics=[accuracy_thresh(0.5)]learn.load('0')learn.lr_find()
learn.sched.plot()85%|████████▌ | 218/255 [02:12<00:22,  1.64it/s, loss=8.91]
```

```py
lr=4e-2learn.fit(lr,1,cycle_len=5,use_clr=(20,5))epoch      trn_loss   val_loss   <lambda>                     
    0      0.02178    0.020653   0.991708  
    1      0.017927   0.020653   0.990241                     
    2      0.015958   0.016115   0.993394                     
    3      0.015172   0.015143   0.993696                     
    4      0.014315   0.014679   0.99388[0.014679321, 0.99388032489352751]learn.save('tmp')learn.load('tmp')learn.unfreeze()
learn.bn_freeze(**True**)lrs = np.array([lr/100,lr/10,lr])/4learn.fit(lrs,1,cycle_len=8,use_clr=(20,8))epoch      trn_loss   val_loss   mask_acc                     
    0      0.038687   0.018685   0.992782  
    1      0.024906   0.014355   0.994933                     
    2      0.025055   0.014737   0.995526                     
    3      0.024155   0.014083   0.995708                     
    4      0.013446   0.010564   0.996166                     
    5      0.01607    0.010555   0.996096                     
    6      0.019197   0.010883   0.99621                      
    7      0.016157   0.00998    0.996393[0.0099797687, 0.99639255659920833]learn.save('512')x,y = next(iter(md.val_dl))
py = to_np(learn.model(V(x)))ax = show_img(denorm(x)[0])
show_img(py[0]>0, ax=ax, alpha=0.5);
```

```py
ax = show_img(denorm(x)[0])
show_img(y[0], ax=ax, alpha=0.5);
```

事情一直在变得更好，但我们仍然有一些小黑色块状物。所以让我们调整到 1024x1024。

## 1024x1024

所以让我们调整到 1024x1024，批量大小减少到 4。现在这是相当高分辨率的了，再训练一段时间，99.6%，99.8%！

```py
sz = 1024
bs = 4tfms = tfms_from_model(resnet34, sz, crop_type=CropType.NO,
                         tfm_y=TfmType.CLASS, aug_tfms=aug_tfms)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y), 
                            (val_x,val_y), tfms, path=PATH)
md = ImageData(PATH, datasets, bs, num_workers=8, classes=**None**)denorm = md.trn_ds.denorm
x,y = next(iter(md.aug_dl))
x = denorm(x)
y = to_np(y)fig, axes = plt.subplots(2, 2, figsize=(8, 8))
**for** i,ax **in** enumerate(axes.flat):
    show_img(x[i], ax=ax)
    show_img(y[i], ax=ax, alpha=0.5)
plt.tight_layout(pad=0.1)
```

```py
simple_up = nn.Sequential(
    nn.ReLU(),
    StdUpsample(512,256),
    StdUpsample(256,256),
    StdUpsample(256,256),
    StdUpsample(256,256),
    nn.ConvTranspose2d(256, 1, 2, stride=2),
    flatten_channel,
)models = ConvnetBuilder(resnet34, 0, 0, 0, custom_head=simple_up)
learn = ConvLearner(md, models)
learn.opt_fn=optim.Adam
learn.crit=nn.BCEWithLogitsLoss()
learn.metrics=[accuracy_thresh(0.5)]learn.load('512')learn.lr_find()
learn.sched.plot()85%|████████▌ | 218/255 [02:12<00:22,  1.64it/s, loss=8.91]
```

```py
lr=4e-2learn.fit(lr,1,cycle_len=2,use_clr=(20,4))*epoch      trn_loss   val_loss   <lambda>                       
    0      0.01066    0.011119   0.996227  
    1      0.009357   0.009696   0.996553**[0.0096957013, 0.99655332546385511]*learn.save('tmp')learn.load('tmp')learn.unfreeze()
learn.bn_freeze(**True**)lrs = np.array([lr/100,lr/10,lr])/8learn.fit(lrs,1,cycle_len=40,use_clr=(20,10))*epoch      trn_loss   val_loss   mask_acc                       
    0      0.015565   0.007449   0.997661  
    1      0.01979    0.008376   0.997542                       
    2      0.014874   0.007826   0.997736                       
    3      0.016104   0.007854   0.997347                       
    4      0.023386   0.009745   0.997218                       
    5      0.018972   0.008453   0.997588                       
    6      0.013184   0.007612   0.997588                       
    7      0.010686   0.006775   0.997688                       
    8      0.0293     0.015299   0.995782                       
    9      0.018713   0.00763    0.997638                       
    10     0.015432   0.006575   0.9978                         
    11     0.110205   0.060062   0.979043                      
    12     0.014374   0.007753   0.997451                       
    13     0.022286   0.010282   0.997587                       
    14     0.015645   0.00739    0.997776                       
    15     0.013821   0.00692    0.997869                       
    16     0.022389   0.008632   0.997696                       
    17     0.014607   0.00677    0.997837                       
    18     0.018748   0.008194   0.997657                       
    19     0.016447   0.007237   0.997899                       
    20     0.023596   0.008211   0.997918                       
    21     0.015721   0.00674    0.997848                       
    22     0.01572    0.006415   0.998006                       
    23     0.019519   0.007591   0.997876                       
    24     0.011159   0.005998   0.998053                       
    25     0.010291   0.005806   0.998012                       
    26     0.010893   0.005755   0.998046                       
    27     0.014534   0.006313   0.997901                       
    28     0.020971   0.006855   0.998018                       
    29     0.014074   0.006107   0.998053                       
    30     0.01782    0.006561   0.998114                       
    31     0.01742    0.006414   0.997942                       
    32     0.016829   0.006514   0.9981                         
    33     0.013148   0.005819   0.998033                       
    34     0.023495   0.006261   0.997856                       
    35     0.010931   0.005516   0.99812                        
    36     0.015798   0.006176   0.998126                       
    37     0.021636   0.005931   0.998067                       
    38     0.012133   0.005496   0.998158                       
    39     0.012562   0.005678   0.998172**[0.0056782686, 0.99817223208291195]*learn.save('1024')x,y = next(iter(md.val_dl))
py = to_np(learn.model(V(x)))ax = show_img(denorm(x)[0])
show_img(py[0][0]>0, ax=ax, alpha=0.5);
```

```py
ax = show_img(denorm(x)[0])
show_img(y[0,...,-1], ax=ax, alpha=0.5);
```

```py
show_img(py[0][0]>0);
```

```py
show_img(y[0,...,-1]);
```

现在如果我们看一下掩模，它们实际上看起来不错。这看起来相当不错。那么我们能做得更好吗？答案是肯定的。

# U-Net

[笔记本](https://github.com/fastai/fastai/blob/master/courses/dl2/carvana-unet.ipynb) / [论文](https://arxiv.org/abs/1505.04597)

U-Net 网络非常了不起。使用之前的方法，我们的预训练 ImageNet 网络被压缩到 7x7，然后再扩展到 224x224（1024 被压缩到比 7x7 大得多）。然后再次扩展出来，这意味着它必须以某种方式在小版本中存储关于更大版本的所有信息。实际上，关于更大版本的大部分信息实际上已经在原始图片中。因此，这种压缩和解压似乎不是一个很好的方法。

因此，U-Net 的想法来自于这篇出色的论文，在这篇论文中，它实际上是在生物医学图像分割这个非常特定的领域中发明的。但事实上，基本上每一个与分割有关的 Kaggle 获胜者最终都使用了 U-Net。这是每个 Kaggle 参与者都知道的最佳实践之一，但在更多的学术圈中，这已经存在至少几年了，很多人仍然没有意识到这是迄今为止最好的方法。

这里是基本的想法。在左侧是向下路径，我们从 572x572 开始，然后将网格大小减半 4 次，然后在右侧是向上路径，我们将网格大小扩大 4 次。但我们还做的一件事是，在每个减半网格大小的点，我们实际上将这些激活复制到向上路径，并将它们连接在一起。

在右下角可以看到，这些红色箭头是最大池化操作，这些绿色箭头是向上采样，然后这些灰色箭头是复制。所以我们复制并连接。换句话说，经过几次卷积后的输入图像被复制到输出中，连接在一起，现在我们可以使用所有经过所有向下和向上的信息，还有输入像素的略微修改版本。以及输入像素的略微修改版本，因为它们是通过这里上来的。所以我们拥有所有向下和向上的丰富性，但也有一个略微不那么粗糙的版本，然后是一个略微不那么粗糙的版本，然后是一个真正简单的版本，它们都可以组合在一起。这就是 U-Net。这是一个很酷的想法。

我们在 carvana-unet 笔记本中。所有这些与之前的代码相同。

```py
%matplotlib inline
%reload_ext autoreload
%autoreload 2**from** **fastai.conv_learner** **import** *
**from** **fastai.dataset** **import** *
**from** **fastai.models.resnet** **import** vgg_resnet50

**import** **json**torch.backends.cudnn.benchmark=**True**
```

# 数据

```py
PATH = Path('data/carvana')
MASKS_FN = 'train_masks.csv'
META_FN = 'metadata.csv'
masks_csv = pd.read_csv(PATH/MASKS_FN)
meta_csv = pd.read_csv(PATH/META_FN)**def** show_img(im, figsize=**None**, ax=**None**, alpha=**None**):
    **if** **not** ax: fig,ax = plt.subplots(figsize=figsize)
    ax.imshow(im, alpha=alpha)
    ax.set_axis_off()
    **return** axTRAIN_DN = 'train-128'
MASKS_DN = 'train_masks-128'
sz = 128
bs = 64
nw = 16TRAIN_DN = 'train'
MASKS_DN = 'train_masks_png'
sz = 128
bs = 64
nw = 16**class** **MatchedFilesDataset**(FilesDataset):
    **def** __init__(self, fnames, y, transform, path):
        self.y=y
        **assert**(len(fnames)==len(y))
        super().__init__(fnames, transform, path)
    **def** get_y(self, i): 
        **return** open_image(os.path.join(self.path, self.y[i]))
    **def** get_c(self): **return** 0x_names = np.array([Path(TRAIN_DN)/o **for** o **in** masks_csv['img']])
y_names = np.array([Path(MASKS_DN)/f'**{o[:-4]}**_mask.png' 
                        **for** o **in** masks_csv['img']])val_idxs = list(range(1008))
((val_x,trn_x),(val_y,trn_y)) = split_by_idx(val_idxs, x_names, 
                                             y_names)aug_tfms = [RandomRotate(4, tfm_y=TfmType.CLASS),
            RandomFlip(tfm_y=TfmType.CLASS),
            RandomLighting(0.05, 0.05, tfm_y=TfmType.CLASS)]tfms = tfms_from_model(resnet34, sz, crop_type=CropType.NO, 
                        tfm_y=TfmType.CLASS, aug_tfms=aug_tfms)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y), 
                             (val_x,val_y), tfms, path=PATH)
md = ImageData(PATH, datasets, bs, num_workers=16, classes=**None**)
denorm = md.trn_ds.denormx,y = next(iter(md.trn_dl))x.shape,y.shape*(torch.Size([64, 3, 128, 128]), torch.Size([64, 128, 128]))*
```

# 简单的上采样

一开始，我有一个简单的上采样版本，只是为了再次向你展示非 U-net 版本。这次，我将加入一个称为 dice 指标的东西。Dice 非常类似，如你所见，与 Jaccard 或 I over U 非常相似。只是有一点小差别。基本上是交集除以并集，稍微调整了一下。我们要使用 dice 的原因是 Kaggle 竞赛使用了这个指标，而且要获得高 dice 分数比获得高准确度要困难一些，因为它真的在看正确像素与你的像素的重叠部分。但它非常相似。

在 Kaggle 竞赛中，表现良好的人得到了大约 99.6 点，而获胜者得到了大约 99.7 点。

```py
f = resnet34
cut,lr_cut = model_meta[f]**def** get_base():
    layers = cut_model(f(**True**), cut)
    **return** nn.Sequential(*layers)**def** dice(pred, targs):
    pred = (pred>0).float()
    **return** 2\. * (pred*targs).sum() / (pred+targs).sum()
```

这是我们的标准上采样。

```py
**class** **StdUpsample**(nn.Module):
    **def** __init__(self, nin, nout):
        super().__init__()
        self.conv = nn.ConvTranspose2d(nin, nout, 2, stride=2)
        self.bn = nn.BatchNorm2d(nout)

    **def** forward(self, x): **return** self.bn(F.relu(self.conv(x)))
```

这一切和以前一样。

```py
**class** **Upsample34**(nn.Module):
    **def** __init__(self, rn):
        super().__init__()
        self.rn = rn
        self.features = nn.Sequential(
            rn, nn.ReLU(),
            StdUpsample(512,256),
            StdUpsample(256,256),
            StdUpsample(256,256),
            StdUpsample(256,256),
            nn.ConvTranspose2d(256, 1, 2, stride=2))

    **def** forward(self,x): **return** self.features(x)[:,0]**class** **UpsampleModel**():
    **def** __init__(self,model,name='upsample'):
        self.model,self.name = model,name

    **def** get_layer_groups(self, precompute):
        lgs = list(split_by_idxs(children(self.model.rn), [lr_cut]))
        **return** lgs + [children(self.model.features)[1:]]m_base = get_base() m = to_gpu(Upsample34(m_base))
models = UpsampleModel(m)learn = ConvLearner(md, models)
learn.opt_fn=optim.Adam
learn.crit=nn.BCEWithLogitsLoss()
learn.metrics=[accuracy_thresh(0.5),dice]learn.freeze_to(1)learn.lr_find()
learn.sched.plot()86%|█████████████████████████████████████████████████████████████          | 55/64 [00:22<00:03,  2.46it/s, loss=3.21]
```

```py
lr=4e-2
wd=1e-7
lrs = np.array([lr/100,lr/10,lr])/2learn.fit(lr,1, wds=wd, cycle_len=4,use_clr=(20,8))0%|          | 0/64 [00:00<?, ?it/s]
epoch      trn_loss   val_loss   <lambda>   dice           
    0      0.216882   0.133512   0.938017   0.855221  
    1      0.169544   0.115158   0.946518   0.878381       
    2      0.153114   0.099104   0.957748   0.903353       
    3      0.144105   0.093337   0.964404   0.915084[0.09333742126112893, 0.9644036065964472, 0.9150839788573129]learn.save('tmp')learn.load('tmp')learn.unfreeze()
learn.bn_freeze(**True**)learn.fit(lrs,1,cycle_len=4,use_clr=(20,8))epoch      trn_loss   val_loss   <lambda>   dice           
    0      0.174897   0.061603   0.976321   0.94382   
    1      0.122911   0.053625   0.982206   0.957624       
    2      0.106837   0.046653   0.985577   0.965792       
    3      0.099075   0.042291   0.986519   0.968925[0.042291240323157536, 0.986519161670927, 0.9689251193924556]
```

现在我们可以检查我们的 dice 指标[[1:48:00](https://youtu.be/nG3tT31nPmQ?t=1h48m)]。所以你可以看到在 dice 指标上，我们在 128x128 处得到了大约 96.8。所以这不太好。

```py
learn.save('128')x,y = next(iter(md.val_dl))
py = to_np(learn.model(V(x)))show_img(py[0]>0);
```

```py
show_img(y[0]);
```

## U-net（ish）[[1:48:16](https://youtu.be/nG3tT31nPmQ?t=1h48m16s)]

所以让我们尝试 U-Net。我称之为 U-net(ish)，因为通常我正在创建自己的有点 hacky 版本——尽量保持与你习惯的东西尽可能相似，并做我认为有意义的事情。所以至少有很多机会让你至少通过查看确切的网格大小来使其更加真实地成为 U-net，看看这里（左上角的卷积）大小有点下降。所以显然他们没有添加任何填充，然后有一些裁剪——有一些差异。但其中一件事是因为我想利用迁移学习——这意味着我不能完全使用 U-Net。

所以另一个重要的机会是，如果你创建了 U-Net 的下行路径，然后在末尾添加一个分类器，然后在 ImageNet 上训练它。现在你有了一个在 ImageNet 上训练过的分类器，专门设计为 U-Net 的良好骨干。然后你应该能够回来并接近赢得这个旧竞赛（实际上并不是很旧——是一个相当新的竞赛）。因为以前不存在这种预训练网络。但是如果你想一下 YOLO v3 是如何做的，基本上就是这样。他们创建了一个 DarkNet，他们在 ImageNet 上预训练了它，然后他们将其用作边界框的基础。所以，再次强调这种不仅为分类而设计而且为其他事物而设计的预训练的想法——这是迄今为止没有人做过的事情。但正如我们所展示的，你现在可以用 25 美元在三小时内训练 ImageNet。如果社区中的人们对此感兴趣，希望我也能提供帮助，如果你愿意，我可以帮助你设置并给我一个脚本，我可能可以为你运行它。但目前我们还没有。所以我们将使用 ResNet。

```py
**class** **SaveFeatures**():
    features=**None**
    **def** __init__(self, m):
        self.hook = m.register_forward_hook(self.hook_fn)
    **def** hook_fn(self, module, input, output): self.features = output
    **def** remove(self): self.hook.remove()
```

所以我们基本上要从`get_base`开始[[1:50:37](https://youtu.be/nG3tT31nPmQ?t=1h50m37s)]。Base 是我们的基础网络，这在第一部分中已经定义过了。

所以`get_base`将调用`f`是什么，`f`是`resnet34`。所以我们将获取我们的 ResNet34 并且`cut_model`是我们的卷积网络构建器做的第一件事。它基本上删除了自适应池化之后的所有内容，这样我们就得到了 ResNet34 的骨干。所以`get_base`将给我们返回 ResNet34 的骨干。

```py
**class** **UnetBlock**(nn.Module):
    **def** __init__(self, up_in, x_in, n_out):
        super().__init__()
        up_out = x_out = n_out//2
        self.x_conv  = nn.Conv2d(x_in,  x_out,  1)
        self.tr_conv = nn.ConvTranspose2d(up_in, up_out, 2, 
                                          stride=2)
        self.bn = nn.BatchNorm2d(n_out)

    **def** forward(self, up_p, x_p):
        up_p = self.tr_conv(up_p)
        x_p = self.x_conv(x_p)
        cat_p = torch.cat([up_p,x_p], dim=1)
        **return** self.bn(F.relu(cat_p))**class** **Unet34**(nn.Module):
    **def** __init__(self, rn):
        super().__init__()
        self.rn = rn
        self.sfs = [SaveFeatures(rn[i]) **for** i **in** [2,4,5,6]]
        self.up1 = UnetBlock(512,256,256)
        self.up2 = UnetBlock(256,128,256)
        self.up3 = UnetBlock(256,64,256)
        self.up4 = UnetBlock(256,64,256)
        self.up5 = nn.ConvTranspose2d(256, 1, 2, stride=2)

    **def** forward(self,x):
        x = F.relu(self.rn(x))
        x = self.up1(x, self.sfs[3].features)
        x = self.up2(x, self.sfs[2].features)
        x = self.up3(x, self.sfs[1].features)
        x = self.up4(x, self.sfs[0].features)
        x = self.up5(x)
        **return** x[:,0]

    **def** close(self):
        **for** sf **in** self.sfs: sf.remove()**class** **UnetModel**():
    **def** __init__(self,model,name='unet'):
        self.model,self.name = model,name

    **def** get_layer_groups(self, precompute):
        lgs = list(split_by_idxs(children(self.model.rn), [lr_cut]))
        **return** lgs + [children(self.model)[1:]]
```

然后我们将把那个 ResNet34 主干转换成一个，我称之为 Unet34。因此，它将保存我们传入的 ResNet，然后我们将使用一个前向钩子，就像以前一样，在第 2、4、5 和 6 个块处保存结果，这些块是每个步幅 2 卷积之前的层。然后我们将创建一堆我们称之为`UnetBlock`的东西。我们需要告诉`UnetBlock`有多少东西来自我们要上采样的上一层，有多少来自交叉路径，然后我们想要输出多少。来自上一层的数量完全由基础网络定义——无论下行路径是什么，我们都需要那么多层。这有点尴尬。实际上我们这里的一个硕士学生，Kerem，实际上创建了一个叫做 DynamicUnet 的东西，你可以在[fastai.model.DynamicUnet](https://github.com/fastai/fastai/blob/d3ef60a96cddf5b503361ed4c95d68dda4a873fc/fastai/models/unet.py#L53)中找到，它实际上为你计算这一切，并自动从你的基础模型创建整个 Unet。它仍然有一些小问题，我想要修复。视频发布时，它肯定会正常工作，我至少会有一个展示如何使用它的笔记本，可能还有一个额外的视频。但现在你只能自己去做。一旦你有了一个 ResNet，你可以输入它的名称，它会打印出层。你可以看到每个块中有多少激活。或者你可以让它自动为每个块打印出来。无论如何，我只是手动做了这个。

所以 UnetBlock 的工作原理是这样的：

+   `up_in`：从上一层传入的数量

+   `x_in`：从下行路径传入的数量（因此`x`）

+   `n_out`：我们想要输出的数量

现在我要做的是，然后我说，好的，我们将从上行路径创建一定数量的卷积，从交叉路径创建一定数量的卷积，所以我将它们连接在一起，所以让我们将我们想要的数量除以 2。因此，我们将让我们的交叉卷积从交叉路径中取出并除以 2（`n_out//2`）。然后上行路径将是`ConvTranspose2d`，因为我们想要增加/上采样。同样在这里，我们将我们想要的数量除以 2（`up_out`），然后最后，我只是将它们连接在一起。

所以我有一个上升样本，我有一个交叉卷积，我可以将这两者连接在一起。这就是 UnetBlock 的全部内容。所以这实际上是一个相当容易创建的模块。

然后在我的前向路径中，我需要将上升路径和交叉路径传递给 UnetBlock 的前向方法。上升路径只是到目前为止的任何事情。但是交叉路径是在下降过程中存储的激活。因此，当我上升时，我首先需要的是最后一组保存的特征。随着我逐渐向上走得更远，最终是第一组特征。

有一些更多的技巧可以让这个变得更好一点，但这已经是一个很好的东西了。所以简单的上采样方法看起来很糟糕，dice 值为 0.968。一个 Unet，除了现在我们有了这些 UnetBlocks 之外，其他一切都相同，dice 值为…

```py
m_base = get_base()
m = to_gpu(Unet34(m_base))
models = UnetModel(m)learn = ConvLearner(md, models)
learn.opt_fn=optim.Adam
learn.crit=nn.BCEWithLogitsLoss()
learn.metrics=[accuracy_thresh(0.5),dice]learn.summary()OrderedDict([('Conv2d-1',
              OrderedDict([('input_shape', [-1, 3, 128, 128]),
                           ('output_shape', [-1, 64, 64, 64]),
                           ('trainable', False),
                           ('nb_params', 9408)])),
             ('BatchNorm2d-2',
              OrderedDict([('input_shape', [-1, 64, 64, 64]),
                           ('output_shape', [-1, 64, 64, 64]),
                           ('trainable', False),
                           ('nb_params', 128)])),
             ('ReLU-3',
              OrderedDict([('input_shape', [-1, 64, 64, 64]),
                           ('output_shape', [-1, 64, 64, 64]),
                           ('nb_params', 0)])),
             ('MaxPool2d-4',
              OrderedDict([('input_shape', [-1, 64, 64, 64]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('Conv2d-5',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 36864)])),
             ('BatchNorm2d-6',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 128)])),
             ('ReLU-7',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('Conv2d-8',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 36864)])),
             ('BatchNorm2d-9',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 128)])),
             ('ReLU-10',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('BasicBlock-11',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('Conv2d-12',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 36864)])),
             ('BatchNorm2d-13',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 128)])),
             ('ReLU-14',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('Conv2d-15',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 36864)])),
             ('BatchNorm2d-16',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 128)])),
             ('ReLU-17',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('BasicBlock-18',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('Conv2d-19',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 36864)])),
             ('BatchNorm2d-20',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 128)])),
             ('ReLU-21',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('Conv2d-22',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 36864)])),
             ('BatchNorm2d-23',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('trainable', False),
                           ('nb_params', 128)])),
             ('ReLU-24',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('BasicBlock-25',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 64, 32, 32]),
                           ('nb_params', 0)])),
             ('Conv2d-26',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 73728)])),
             ('BatchNorm2d-27',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-28',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-29',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 147456)])),
             ('BatchNorm2d-30',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('Conv2d-31',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 8192)])),
             ('BatchNorm2d-32',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-33',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('BasicBlock-34',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-35',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 147456)])),
             ('BatchNorm2d-36',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-37',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-38',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 147456)])),
             ('BatchNorm2d-39',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-40',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('BasicBlock-41',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-42',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 147456)])),
             ('BatchNorm2d-43',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-44',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-45',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 147456)])),
             ('BatchNorm2d-46',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-47',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('BasicBlock-48',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-49',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 147456)])),
             ('BatchNorm2d-50',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-51',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-52',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 147456)])),
             ('BatchNorm2d-53',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', False),
                           ('nb_params', 256)])),
             ('ReLU-54',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('BasicBlock-55',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('nb_params', 0)])),
             ('Conv2d-56',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 294912)])),
             ('BatchNorm2d-57',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-58',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-59',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-60',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('Conv2d-61',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 32768)])),
             ('BatchNorm2d-62',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-63',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('BasicBlock-64',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-65',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-66',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-67',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-68',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-69',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-70',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('BasicBlock-71',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-72',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-73',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-74',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-75',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-76',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-77',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('BasicBlock-78',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-79',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-80',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-81',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-82',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-83',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-84',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('BasicBlock-85',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-86',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-87',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-88',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-89',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-90',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-91',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('BasicBlock-92',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-93',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-94',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-95',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-96',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 589824)])),
             ('BatchNorm2d-97',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', False),
                           ('nb_params', 512)])),
             ('ReLU-98',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('BasicBlock-99',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('Conv2d-100',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1179648)])),
             ('BatchNorm2d-101',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1024)])),
             ('ReLU-102',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('Conv2d-103',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 2359296)])),
             ('BatchNorm2d-104',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1024)])),
             ('Conv2d-105',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 131072)])),
             ('BatchNorm2d-106',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1024)])),
             ('ReLU-107',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('BasicBlock-108',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('Conv2d-109',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 2359296)])),
             ('BatchNorm2d-110',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1024)])),
             ('ReLU-111',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('Conv2d-112',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 2359296)])),
             ('BatchNorm2d-113',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1024)])),
             ('ReLU-114',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('BasicBlock-115',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('Conv2d-116',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 2359296)])),
             ('BatchNorm2d-117',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1024)])),
             ('ReLU-118',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('Conv2d-119',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 2359296)])),
             ('BatchNorm2d-120',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('trainable', False),
                           ('nb_params', 1024)])),
             ('ReLU-121',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('BasicBlock-122',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 512, 4, 4]),
                           ('nb_params', 0)])),
             ('ConvTranspose2d-123',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 128, 8, 8]),
                           ('trainable', True),
                           ('nb_params', 262272)])),
             ('Conv2d-124',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 128, 8, 8]),
                           ('trainable', True),
                           ('nb_params', 32896)])),
             ('BatchNorm2d-125',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('trainable', True),
                           ('nb_params', 512)])),
             ('UnetBlock-126',
              OrderedDict([('input_shape', [-1, 512, 4, 4]),
                           ('output_shape', [-1, 256, 8, 8]),
                           ('nb_params', 0)])),
             ('ConvTranspose2d-127',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', True),
                           ('nb_params', 131200)])),
             ('Conv2d-128',
              OrderedDict([('input_shape', [-1, 128, 16, 16]),
                           ('output_shape', [-1, 128, 16, 16]),
                           ('trainable', True),
                           ('nb_params', 16512)])),
             ('BatchNorm2d-129',
              OrderedDict([('input_shape', [-1, 256, 16, 16]),
                           ('output_shape', [-1, 256, 16, 16]),
                           ('trainable', True),
                           ('nb_params', 512)])),
             ('UnetBlock-130',
              OrderedDict([('input_shape', [-1, 256, 8, 8]),
                           ('output_shape', [-1, 256, 16, 16]),
                           ('nb_params', 0)])),
             ('ConvTranspose2d-131',
              OrderedDict([('input_shape', [-1, 256, 16, 16]),
                           ('output_shape', [-1, 128, 32, 32]),
                           ('trainable', True),
                           ('nb_params', 131200)])),
             ('Conv2d-132',
              OrderedDict([('input_shape', [-1, 64, 32, 32]),
                           ('output_shape', [-1, 128, 32, 32]),
                           ('trainable', True),
                           ('nb_params', 8320)])),
             ('BatchNorm2d-133',
              OrderedDict([('input_shape', [-1, 256, 32, 32]),
                           ('output_shape', [-1, 256, 32, 32]),
                           ('trainable', True),
                           ('nb_params', 512)])),
             ('UnetBlock-134',
              OrderedDict([('input_shape', [-1, 256, 16, 16]),
                           ('output_shape', [-1, 256, 32, 32]),
                           ('nb_params', 0)])),
             ('ConvTranspose2d-135',
              OrderedDict([('input_shape', [-1, 256, 32, 32]),
                           ('output_shape', [-1, 128, 64, 64]),
                           ('trainable', True),
                           ('nb_params', 131200)])),
             ('Conv2d-136',
              OrderedDict([('input_shape', [-1, 64, 64, 64]),
                           ('output_shape', [-1, 128, 64, 64]),
                           ('trainable', True),
                           ('nb_params', 8320)])),
             ('BatchNorm2d-137',
              OrderedDict([('input_shape', [-1, 256, 64, 64]),
                           ('output_shape', [-1, 256, 64, 64]),
                           ('trainable', True),
                           ('nb_params', 512)])),
             ('UnetBlock-138',
              OrderedDict([('input_shape', [-1, 256, 32, 32]),
                           ('output_shape', [-1, 256, 64, 64]),
                           ('nb_params', 0)])),
             ('ConvTranspose2d-139',
              OrderedDict([('input_shape', [-1, 256, 64, 64]),
                           ('output_shape', [-1, 1, 128, 128]),
                           ('trainable', True),
                           ('nb_params', 1025)]))])[o.features.size() **for** o **in** m.sfs]*[torch.Size([3, 64, 64, 64]),
 torch.Size([3, 64, 32, 32]),
 torch.Size([3, 128, 16, 16]),
 torch.Size([3, 256, 8, 8])]*learn.freeze_to(1)learn.lr_find()
learn.sched.plot() 0%|                                                                                           | 0/64 [00:00<?, ?it/s]92%|█████████████████████████████████████████████████████████████████▍     | 59/64 [00:22<00:01,  2.68it/s, loss=2.45]
```

```py
lr=4e-2
wd=1e-7

lrs = np.array([lr/100,lr/10,lr])learn.fit(lr,1,wds=wd,cycle_len=8,use_clr=(5,8))*epoch      trn_loss   val_loss   <lambda>   dice           
    0      0.12936    0.03934    0.988571   0.971385  
    1      0.098401   0.039252   0.990438   0.974921        
    2      0.087789   0.02539    0.990961   0.978927        
    3      0.082625   0.027984   0.988483   0.975948        
    4      0.079509   0.025003   0.99171    0.981221        
    5      0.076984   0.022514   0.992462   0.981881        
    6      0.076822   0.023203   0.992484   0.982321        
    7      0.075488   0.021956   0.992327   0.982704**[0.021955982234979434, 0.9923273126284281, 0.9827044502137199]*learn.save('128urn-tmp')learn.load('128urn-tmp')learn.unfreeze()
learn.bn_freeze(**True**)learn.fit(lrs/4, 1, wds=wd, cycle_len=20,use_clr=(20,10))0%|          | 0/64 [00:00<?, ?it/s]
epoch      trn_loss   val_loss   <lambda>   dice            
    0      0.073786   0.023418   0.99297    0.98283   
    1      0.073561   0.020853   0.992142   0.982725        
    2      0.075227   0.023357   0.991076   0.980879        
    3      0.074245   0.02352    0.993108   0.983659        
    4      0.073434   0.021508   0.993024   0.983609        
    5      0.073092   0.020956   0.993188   0.983333        
    6      0.073617   0.019666   0.993035   0.984102        
    7      0.072786   0.019844   0.993196   0.98435         
    8      0.072256   0.018479   0.993282   0.984277        
    9      0.072052   0.019479   0.993164   0.984147        
    10     0.071361   0.019402   0.993344   0.984541        
    11     0.070969   0.018904   0.993139   0.984499        
    12     0.071588   0.018027   0.9935     0.984543        
    13     0.070709   0.018345   0.993491   0.98489         
    14     0.072238   0.019096   0.993594   0.984825        
    15     0.071407   0.018967   0.993446   0.984919        
    16     0.071047   0.01966    0.993366   0.984952        
    17     0.072024   0.018133   0.993505   0.98497         
    18     0.071517   0.018464   0.993602   0.985192        
    19     0.070109   0.018337   0.993614   0.9852[0.018336569653853538, 0.9936137114252362, 0.9852004420189631]
```

0.985！这就像我们将错误减半，其他一切完全相同。而且更重要的是，你可以看一下。

```py
learn.save('128urn-0')learn.load('128urn-0')x,y = next(iter(md.val_dl))
py = to_np(learn.model(V(x)))
```

与我们的非 Unet 等效物相比，这实际上看起来有点像汽车，后者只是一个斑点。因为试图通过下行和上行路径来做这个——这只是要求太多了。而当我们实际上在每个点提供下行路径像素时，它实际上可以开始创建一些类似汽车的东西。

```py
show_img(py[0]>0);
```

```py
show_img(y[0]);
```

最后，我们将执行 m.close 以删除占用 GPU 内存的`sfs.features`。 

```py
m.close()
```

## 512x512 [[1:56:26](https://youtu.be/nG3tT31nPmQ?t=1h56m26s)]

转到较小的批量大小，更高的大小

```py
sz=512
bs=16tfms = tfms_from_model(resnet34, sz, crop_type=CropType.NO, 
                       tfm_y=TfmType.CLASS, aug_tfms=aug_tfms)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y), 
                            (val_x,val_y), tfms, path=PATH)
md = ImageData(PATH, datasets, bs, num_workers=4, classes=**None**)
denorm = md.trn_ds.denormm_base = get_base()
m = to_gpu(Unet34(m_base))
models = UnetModel(m)learn = ConvLearner(md, models)
learn.opt_fn=optim.Adam
learn.crit=nn.BCEWithLogitsLoss()
learn.metrics=[accuracy_thresh(0.5),dice]learn.freeze_to(1)**learn.load('128urn-0')**learn.fit(lr,1,wds=wd, cycle_len=5,use_clr=(5,5))epoch      trn_loss   val_loss   <lambda>   dice              
    0      0.071421   0.02362    0.996459   0.991772  
    1      0.070373   0.014013   0.996558   0.992602          
    2      0.067895   0.011482   0.996705   0.992883          
    3      0.070653   0.014256   0.996695   0.992771          
    4      0.068621   0.013195   0.996993   0.993359[0.013194938530288046, 0.996993034604996, 0.993358936574724]
```

你可以看到 Dice 系数真的在上升[[1:56:30](https://youtu.be/nG3tT31nPmQ?t=1h56m30s)]。所以请注意，我正在加载网络的 128x128 版本。我们再次使用渐进式调整大小的技巧，这样我们得到了 0.993。

```py
learn.save('512urn-tmp')learn.unfreeze()
learn.bn_freeze(**True**)learn.load('512urn-tmp')learn.fit(lrs/4,1,wds=wd, cycle_len=8,use_clr=(20,8))epoch      trn_loss   val_loss   <lambda>   dice              
    0      0.06605    0.013602   0.997      0.993014  
    1      0.066885   0.011252   0.997248   0.993563          
    2      0.065796   0.009802   0.997223   0.993817          
    3      0.065089   0.009668   0.997296   0.993744          
    4      0.064552   0.011683   0.997269   0.993835          
    5      0.065089   0.010553   0.997415   0.993827          
    6      0.064303   0.009472   0.997431   0.994046          
    7      0.062506   0.009623   0.997441   0.994118[0.009623114736602894, 0.9974409020136273, 0.9941179137381296]
```

然后解冻以达到 0.994。

```py
learn.save('512urn')learn.load('512urn')x,y = next(iter(md.val_dl))
py = to_np(learn.model(V(x)))
```

你可以看到，现在看起来很不错。

```py
show_img(py[0]>0);
```

```py
show_img(y[0]);
```

```py
m.close()
```

## 1024x1024 [[1:56:53](https://youtu.be/nG3tT31nPmQ?t=1h56m53s)]

将批量大小降至 4，大小为 1024。

```py
sz=1024
bs=4tfms = tfms_from_model(resnet34, sz, crop_type=CropType.NO, 
                         tfm_y=TfmType.CLASS)
datasets = ImageData.get_ds(MatchedFilesDataset, (trn_x,trn_y), 
                            (val_x,val_y), tfms, path=PATH)
md = ImageData(PATH, datasets, bs, num_workers=16, classes=**None**)
denorm = md.trn_ds.denormm_base = get_base()
m = to_gpu(Unet34(m_base))
models = UnetModel(m)learn = ConvLearner(md, models)
learn.opt_fn=optim.Adam
learn.crit=nn.BCEWithLogitsLoss()
learn.metrics=[accuracy_thresh(0.5),dice]
```

加载我们刚刚保存的 512。

```py
learn.load('512urn')learn.freeze_to(1)learn.fit(lr,1, wds=wd, cycle_len=2,use_clr=(5,4))epoch      trn_loss   val_loss   <lambda>   dice                 
    0      0.007656   0.008155   0.997247   0.99353   
    1      0.004706   0.00509    0.998039   0.995437[0.005090427414942828, 0.9980387706605215, 0.995437301104031]
```

这让我们达到了 0.995。

```py
learn.save('1024urn-tmp')learn.load('1024urn-tmp')learn.unfreeze()
learn.bn_freeze(**True**)lrs = np.array([lr/200,lr/30,lr])learn.fit(lrs/10,1, wds=wd,cycle_len=4,use_clr=(20,8))epoch      trn_loss   val_loss   <lambda>   dice                 
    0      0.005688   0.006135   0.997616   0.994616  
    1      0.004412   0.005223   0.997983   0.995349             
    2      0.004186   0.004975   0.99806    0.99554              
    3      0.004016   0.004899   0.99812    0.995627[0.004898778487196458, 0.9981196409180051, 0.9956271404784823]learn.fit(lrs/10,1, wds=wd,cycle_len=4,use_clr=(20,8))epoch      trn_loss   val_loss   <lambda>   dice                 
    0      0.004169   0.004962   0.998049   0.995517  
    1      0.004022   0.004595   0.99823    0.995818             
    2      0.003772   0.004497   0.998215   0.995916             
    3      0.003618   0.004435   0.998291   0.995991[0.004434524739663753, 0.9982911745707194, 0.9959913929776539]
```

解冻将我们带到...我们将称之为 0.996。

```py
learn.sched.plot_loss()
```

```py
learn.save('1024urn')learn.load('1024urn')x,y = next(iter(md.val_dl))
py = to_np(learn.model(V(x)))
```

正如你所看到的，实际上看起来很不错[[1:57:17](https://youtu.be/nG3tT31nPmQ?t=1h57m17s)]。在准确性方面，99.82%。你可以看到这看起来像是你可以用来裁剪的东西。我认为，在这一点上，我们可以做一些微小的调整来达到 0.997，但真正的关键是，我认为，也许只需要做一些平滑处理或一点后处理。你可以去看看 Carvana 获奖者的博客，看看其中的一些技巧，但正如我所说，我们目前的 0.996 和获奖者得到的 0.997 之间的差距并不大。所以实际上，U-Net 基本上解决了这个问题。

```py
show_img(py[0]>0);
```

```py
show_img(y[0]);
```

# 回到边界框[[1:58:15](https://youtu.be/nG3tT31nPmQ?t=1h58m15s)]

好的，就是这样。我想要提到的最后一件事是现在回到边界框，因为你可能还记得，我说我们的边界框模型在小物体上仍然表现不佳。所以希望你能猜到我接下来要做什么，那就是对于边界框模型，记得我们在不同的网格单元中输出了模型的输出。那些较早的具有较小网格大小的输出并不好。我们该如何修复呢？用 U-Net！让我们有一个带有交叉连接的向上路径。然后我们将使用 U-Net，然后从中输出。因为现在那些更精细的网格单元具有该路径的所有信息，以及该路径、该路径和该路径的信息。当然，这是深度学习，这意味着你不能写一篇论文说我们只是用 U-Net 来处理边界框。你必须发明一个新词，所以这被称为特征金字塔网络或 FPNs。这在 RetinaNet 论文中使用过，它是在早期关于 FPNs 的论文中创建的。如果我记得正确的话，他们确实简要引用了 U-Net 论文，但他们似乎让它听起来像是这个模糊地稍微相关的东西，也许有些人可能认为稍微有用。但实际上，FPNs 就是 U-Nets。

我没有实现它来展示给你，但这将是一件有趣的事情，也许对于我们中的一些人来尝试，我知道一些学生一直在尝试在论坛上使其良好运行。所以是的，尝试一下是有趣的事情。所以我认为在这堂课之后要看的一些事情，以及我提到的其他事情，可能是玩玩 FPNs，也可能尝试一下 Kerem 的 DynamicUnet。它们都是值得一看的有趣的东西。

所以你们现在已经经历了我对你们讲解的 14 堂课。对此我感到抱歉。谢谢你们忍受我。我认为你们会发现很难找到其他人对神经网络训练和实践了解得像你们这样多。你们很容易高估其他人的能力，低估自己的能力。所以我想说的是，请继续练习。因为现在没有每个星期一晚上都有我在这里让你们回来了。很容易失去动力。所以找到方法保持下去。组织一个学习小组，一个读书小组，或者和朋友们一起做项目，或者做一些不仅仅是决定我要继续做 X 的事情。除非你是那种超级有动力的人，每当你决定做某事，它就会发生。那不是我。我知道，要让事情发生，我必须说“是的，大卫。十月份，我绝对会教那门课程”，然后我就得开始写一些材料。这是我让事情发生的唯一方法。所以我们在论坛上有一个很棒的社区。如果有人有想法让它变得更好，请告诉我。如果你认为你可以帮忙，如果你想创建一些新的论坛或以某种不同的方式进行管理，或者其他什么的，只要告诉我。你可以随时私信我，GitHub 上也有很多项目正在进行中——很多东西。所以我希望能在其他地方再见到你们，非常感谢你们加入我的旅程。
