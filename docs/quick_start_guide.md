# 快速开始引导

[UCSF ChimeraX](http://www.rbvi.ucsf.edu/chimerax/)是加州旧金山大学[RBVI](http://www.rbvi.ucsf.edu/)项目中产生的[Chimera](http://www.rbvi.ucsf.edu/chimera/)之后一代可视化程序。参见[ChimeraX 教程](http://www.rbvi.ucsf.edu/chimerax/tutorials.html)

![ChimeraX](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/chimerax.png)

大量ChimeraX操作需要输入命令。可以通过[`help`](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/help.html)指令得到特定命令的帮助信息（例如：`help style`）。其它与此程序交互的方式包括：
    - 点击[工具栏图标](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/toolbar.html)，某些在[选择](https://www.cgl.ucsf.edu/chimerax/docs/user/selection.html)之后可选
    - [图形工具](https://www.cgl.ucsf.edu/chimerax/docs/user/index.html#tools)
    - 右键单击显示上下文菜单（在Mac上按住Ctrl键单击，在Windows轨迹板上按住Alt键单击）


# 执行命令的链接

如果这个页面是由ChimeraX内置的浏览器打开的话（可以通过ChimeraX菜单的**Help**...**Quick Start Guide**访问），点击下面示例中的命令链接，ChimeraX就会自动执行这些命令。


## 示例：原子级别结构的命令

示例结构：Protein DataBank [2BBV](http://www.rcsb.org/pdb/explore.do?structureId=2bbv), 黑甲虫病毒衣壳


> open 2bbv
> light full

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/colorchain.png)

文件从PDB以mmCIF格式取回并缓存在本地。照亮、有阴影。

> style /b stick

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/stick.png)

把b链显示为stick模式。

> *鼠标拖动来移动*

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/shift.png)

通过拖动来旋转，通过鼠标中键拖动来平移（Mac用户也可以按下**option**键拖动，[更多](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/ui.html#mousedefaults)）。

> hide /c

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/undisplay.png)

隐藏链c的原子。

> ribbon /c

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/ribbon.png)

显示骨架色带

> *按下ctrl键的同时鼠标点击来选择一个原子*

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/select.png)

被选中的会有一个绿色的轮廓线，按下shift和ctrl的同时点击来添加一个选择，按下ctrl同时点击背景来清除一个选择。

> *按下向上箭头*

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/uparrow.png)

按下向上箭头来扩张选择区域，按下向下箭头来收缩选择区域。

> color sel gold
> select clear

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/color.png)

在任何命令中都可以用*sel*来指代被选择的原子。
清除选择。

> surface #1

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/surface.png)

展示每条链的溶剂排斥表面。

> style solvent sphere
> style ~solvent stick

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/water.png)

将溶剂展示为球体（表面），并把其它原子从球体展示为棍子（stick）模式。

> sym #1

||2bbv mmCIF Assemblies||
|:--|:--:|:--:|
|1 | complete icosahedral assembly | 60 copies of chains A-F,N|
|2 | icosahedral asymmetric unit| 1copy of chains A-F,N|
|3| icosahedral pentamer | 5 copies of chains A-F,N|
|4| icosahedral 23 hexamber | 6 copies of chains A-F,N|
|PAU| icosahedral asymmetric unit, std point frame| 1 copy of chains A-F,N|
|XAU| crystal asymmetric unit, crystal frame | 5 copies of chains A-F,N|

在*log*中列出mmCIF的所有组件。不要点击*log*中的链接来产生组件，那是下一条命令要做的。（如果不小心做了，可以通过`close #2; show #1 model`命令取消）

> sym #1 assembly 3 newmodel f

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/assembly3.png)

根据前一条命令产生的*log*信息，显示组件"3"

> view

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/view3.png)

把所有模型显示出来

> set bg white
> set silhouettes true
> save ~/Desktop/2bbv.png

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/view3nice.png)

将背景色设置为白色，显示窄的黑色轮廓线，保存png格式图片到桌面。

> 点击录影机图标![camera](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/shortcut-icons/video.png ':size=20x20')以录制一个旋转影片

[spin movie](../media/quick_start_guide_spin.mp4 ':include')

影片被保存在桌面，命名为movie.mp4





## 示例：密度图命令
