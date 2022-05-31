# 线框图质量自动检测

### 1. 动机(Motivation)
线框图是PBN产品中必不可少的一环，线框图的质量直接影响内容的质量和用户的体验。为了确保内容
的精美度和用户体验的完美度，产品线会对所有的线框图进行质量核查，核查内容包括线框的粗细，是否
存在断开的线段等，如下图所示。比如，低于2PX的线条是过细的，不符合标准的，会被打回。另外，如果线框图中
存在未闭合的线段，会使原本独立的闭合区域连成一体，造成质量问题。
![线框图质量问题](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/schecker_problems.png)

以线条过细为例，**现在的方法是把线框图拉入Illustrate软件进行人工核查，不但效率低，而且可能存在遗漏**。
更重要的是，这种评价标准不够统一和客观，不同的审核人员可能有细微的差别。时间久了，核查人员也容易疲劳遗
漏。考虑到新产品ZenColor可能拥有更加复杂的线框图，会消耗更多的人力去做重复的查验工作。因此，需要设计一
种自动化工具，能够代替重复的、主观的人力核查，自动核查线框图中可能存在的问题。

### 2. 研究内容（Research)
为了完成自动核查线框图的任务，并实现真正的落地，需要解决以下问题：
+ 以PDF文件作为输入进行处理。这是一个工程问题。设计师一般提供的是PDF文件，但是算法进行处理时以
图像（PNG格式）作为输入。为了做的真正可用，需要以PDF作为输入，提取其中的图像，再进行后续处理。
+ 算法要具有一定的普适性。线框图有不同的类型，以分辨率来说，分为长宽不同的墙纸型和长宽相同的
正方型线框图。两者的分辨率不同，导致同样的2PX，在不同图像上具有不同的标准。因此，需要根据分辨率
进行一定的换算，形成统一的判别标准。
+ 同样是细线，但是可能存在很多假阳的结果，如下图所示。比如一条线的末端可能变细了，但是并不意味着这条线都是
不符合标准的。因此，需要去除很多假阳的结果。如果检测到的假阳性比较多，需要设计师花较多时间辨别
，那么自动工具就失去意义了。如何分辨线框图中真正的细线，是项目中非常难的研究内容。
![细线假阳](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/schecker_thinline.png)

+ 同样是未闭合的断点，也存在很多假阳的结果，如下图所示。而且，有些线段，本身就是要断开的效果。
同样的，需要设计算法，将假阳结果去除。同样，这也是本项目中很难的研究内容。
![断点假阳](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/schecker_brokenline.png)

+ 算法要适应黑白和彩色的线框图。除了常规黑白的线框图，还有彩色的线框图，算法需要解决黑白和彩色
两种不同样式的线框图作为输入。特别是彩色线框图，有些颜色看起来非常淡，会影响最终的检测结果。

### 3. 成果(Results)
为了满足实际落地的需求，本项目花费了数月，特别是在假阳性的判断上，我们结合了传统图像处理的方法和
神经网络方法，取得了很好的结果。经过实际设计师的测试，该工具能高效的检测线框图中低于2px的细线，
以及距离不超过10px的断点。目前该工具已交付PBN组，接下来会整合到公司的业务流程中。
下面是一些检测结果示例(原图过大，仅截取部分)。在细线检测环境，我们还用不同的颜色对一般细线和超细细线进行区分标示。
![细线结果](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/schecker_res_thin.png)
![断点结果](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/schecker_res_broken.png)


