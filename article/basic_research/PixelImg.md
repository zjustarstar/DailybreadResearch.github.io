# 像素画生成

### 1. 动机(Motivation)
乐信的业务线会涉及各种以图像为主的内容，这些内容包括线框图(Sketch)、彩绘图(Painting)、插画
(Illustration)、照片(Photo)、像素画(Pixel Art)等等。除了照片以外，其它的内容生成均需要设计
师的参与。因此，内容的生成是一项非常消耗人力和时间的工作。本项目拟基于已有的部分简易画(来
自ezdrawing)，设计能自动生成带有艺术美感的像素图的算法。

### 2. 研究内容（Research)
![PixelMe](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/basic_research/imgs/pixel_pixelme.png)

现有基于输入的图像生成像素画的工具其实不少，比如PixelMe(https://pixel-me.tokyo/en/),
Pixelator(<http://pixelatorapp.com/index.html>)等等，但是使用过后，我们发现效果往往达不到
要求。另外，还有部分论文[1]也提出了一些像素画的自动生成算法，甚至TOG上还发表过基于端到
端神经网络[2]的像素图自动生成算法。但是经过测试，已有的工具或者算法均不能满足实际产品上
的需求。这些需求包括：
+ 生成的像素图缺乏美感。仅仅是将图像变成了像素画的格式，但是在实际产品上，对像素画的质量
其实要求是很高的。如下图所示，设计师在进行像素画设计时，会考虑像素画后线条的布局。
+ 算法要能输出任意大小的像素画。这一条，神经网络算法基本无法达到，因为此类算法的输出大小
基本是固定的。而在实际的产品中，可能会用到不同分辨率的像素画。
+ 生成的像素画中的目标应该保持完整的轮廓。已有的工具和算法，均不能保证原图中的目标在像素画
以后的轮廓完整性。这样会使目标在像素图中看起来“支离破碎”，语义信息不完整。

![像素图中线条的布局](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/basic_research/imgs/pixel_lineformat.png)

**参考文献**:
1. Yunyi Shang, Hon-Cheng Wong. Automatic portrait image pixelization. Computers & Graphics. 
Volume 95. 2021.Pages 47-59.
2. Han, Chu, et al. "Deep unsupervised pixelization." ACM Transactions on Graphics (TOG),
Vol. 37.6 (2018): 1-11

### 3. 成果(Results)
为了实际解决上述三点需求（要有美感、要能输出任意大小、保持目标轮廓完整），我们设计了单独的
算法框架，如下图所示：
![算法框架](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/basic_research/imgs/pixel_flowchart.png)

实事求是的说，这个框架仍然存在一些问题，比如对于比较复杂的输入图，生成的效果还不够令人满意。
但是对于比较简单的输入图，基本能生成比现有工具和算法更满意的效果，部分效果如下所示，左边是
输入图，右边三列分别是32X32,48X48和64X64的输出效果图。
![算法效果](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/basic_research/imgs/pixel_results.png)

下图是我们生成的算法中像素图上的线条布局效果，带有一定的美感。
![美感效果](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/basic_research/imgs/pixel_linearrange.png)