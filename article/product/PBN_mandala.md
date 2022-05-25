# 曼陀罗图案自动设计与生成

### 1. 动机(Motivation)
PBN产品中，内容具有决定性作用。线框图是内容的重要组成部分，制作线框图也是最耗时的工作。
前期，我们探索了从内容（图像）中直接提取线框图，如下图所示。事实证明，这条路很难走通，
![从图像中提取线框图](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/mandala_motivation.png)
前期，我们探索了从内容（图像）中直接提取线框图，如下图所示。事实证明，这条路很难走通。
![从图像中提取线框图](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/mandala_motivation.png)

具体原因主要是：
- PBN中的线框图都是以封闭区域进行表示的，直接从图像中，很难提取到具有光滑边界的闭合区域线框图。
- 公司的设计师在创作线框图时，虽然会参考相关的内容图像，但是在绘制线框时，会加入自己的
想象和修改，这种“创作”过程，AI还无法做到。

虽然从自然图像中无法提取出具有艺术效果的线框图，但是我们发现，设计师创造的曼陀罗图相对
比较规则，有可能通过算法自动生成曼陀罗图，从而减少人工在曼陀罗图案上的投入。毕竟任何线
框图的设计与生成，都需要人工的投入。

### 2. 研究内容（Research)
为了要完全代替人工生成曼陀罗图案，并满足PBN产品的需求，必须具有一定的条件。经过长时间
的设计与调试，我们发现，算法要落地，必须做到以下几点：
+ 生成的曼陀罗图案，必须具有美观性，而不仅仅是图案的堆积。
+ 生成的曼陀罗图案，需要具有一定的景深，从而看起来更有立体感。
+ 生成的曼陀罗图案，其线框图中任何一个区域都是封闭的，这样才能上色。
+ 生成的曼陀罗图案，要具有随机性和创造性，每次运行时都能生成不同的效果。
+ 生成的曼陀罗图案，要具有丰富的色彩，且能生成不同的配色效果。
+ 生成的曼陀罗图案，必须是矢量格式的，并能根据产品的要求，保存为不同的分辨率。

这些要求同时也是对算法设计的约束。我们在尝试了多种算法和技术路线后，最终完成了一套
自动化的曼陀罗图案生成工具。整个系统的框架如下图所示：
![曼陀罗图案生成框架](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/mandala_flowchart.png)


### 3. 成果(Results)
该算法已落地交付给PBN产品线。我们最终完成了一套能自动生成常规曼陀罗图案和多边形曼陀罗图案的算法，该算法具有足够的
创造性，每次运行均能生成不同的曼陀罗图案，且能根据样图进行自动上色。下面是一些我们的
算法生成的曼陀罗图案。
![曼陀罗效果图](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/mandala_regular.png)
![曼陀罗效果图](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/mandala_polygon.png)

产品线也对算法自动生成的图案和设计师生成的图案进行了AB测。数据如下：
+ 到2021年10月份，我们自动生成的曼陀罗图案已经上线45组。为了AB测，选用其他同类型同期的曼陀罗素材51张
+ 根据APP端的用户打分，算法生成的图案平均分63.42，平均分52.4。
+ 算法生成的图案的平均点击率17.23%，同类型时期其他曼陀罗素材平均点击率10.96%。
+ 算法生成的图案的良品素材18张，良品率40.0%，其他同类型同期良品素材20张，良品率39.21%

数据证明，我们自动生成曼陀罗的算法不但效率更快，而且生成的图案质量更高。



