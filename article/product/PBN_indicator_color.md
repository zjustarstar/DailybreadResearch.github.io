# 纯色图提取

### 1. 动机(Motivation)
如下图所示，基于线框图，并在参考原彩绘图的基础上，为线框图中的每个区域设定用户填充
时用的指示性颜色，是一个必须的步骤。一般PBN产品中的线框图具有数十个，甚至数百个闭合
的连通区域。要为每个区域设定与彩绘色彩相近的指示性颜色，会花费设计师大量时间。

本项目拟设计一种自动化工具，利用算法提取与线框图区域相匹配的彩绘图区域的主要颜色，  
并最终形成完整的纯色图，从而大大节省设计师在每个区域的颜色指定上花费的时间。  
![指示色](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/clrindicator_flowchart.jpg)

### 2. 研究内容（Research)
为了使项目能完全落地，并且真正满足设计师的要求，需要做到以下几点：
+ 能基于用户输入的参数，限制生成的纯色图中颜色数量的上限和下限
+ 能基于用户输入的参数，限制生成的纯色图中仅有单一连通区域的颜色的数量
+ 对于每一个闭合的连通区域，能保证纯色和相同区域的彩绘图案的颜色，最大程度在视觉上接近。
这样用户填色后生成的效果与预期不会差很多。
+ 为了保证效果，只能基于原图进行处理。原图分辨率较大，要保证算法耗时不能过长。
+ 算法具有通用性，能适应正方形的图和长方形的墙纸类图。

### 3. 成果(Results)
目前整个算法已经交付PBN产品组，并已经作为工具上线，内嵌在产品线流程中。根据设计师的
反馈，我们的工具不但可以代替设计师的上色工作，而且色彩的提取效果更符合原彩绘图。
实际效果如下图所示。    
![结果](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/clrindicator_result1.png)
![结果](https://raw.githubusercontent.com/zjustarstar/dailybreadResearch.github.io/gh-pages/article/product/imgs/clrindicator_result2.png)


