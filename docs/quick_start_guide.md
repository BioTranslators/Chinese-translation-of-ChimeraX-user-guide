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

> 鼠标拖动来移动

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/shift.png)

通过拖动来旋转，通过鼠标中键拖动来平移（Mac用户也可以按下**option**键拖动，[更多](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/ui.html#mousedefaults)）。

> hide /c

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/undisplay.png)

隐藏链c的原子。

> ribbon /c

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/ribbon.png)

显示骨架色带

> 按下ctrl键的同时鼠标点击来选择一个原子

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/select.png)

被选中的会有一个绿色的轮廓线，按下shift和ctrl的同时点击来添加一个选择，按下ctrl同时点击背景来清除一个选择。

> 按下向上箭头

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

[spin movie](media/quick_start_guide_spin.mp4 ':include')

影片被保存在桌面，命名为movie.mp4

> measure buriedarea /a with /b   
> measure sasa #1 & ~solvent

```log
Buried area between /a and /b = 1900.4
area /a = 15385, area /b = 14989, area both = 26573

Solvent accessible area for #1 & ~solvent = 34093
```

计算链A和链B的溶剂可及的埋藏表面积，也计算总非水溶剂可及表面积。

> interfaces #1 & protein

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/contacts.png)

```log
6 buried areas: 
  C A 1675, C B 1671, A B 1663,
  C F 739, A D 714, B E 699
```

展示所有链之间的联系图谱。

> close  
> set bg black  
> set silhouettes false

关闭所有3D数据，设置背景色为黑色，不显示轮廓线。


## 示例：密度图命令

示例数据：
- [EMD-1080](https://www.ebi.ac.uk/pdbe/entry/emdb/EMD-1080)，GroEL的11.5Å单粒子重建和原子结构, [1GRL](http://www.rcsb.org/pdb/explore.do?structureId=1grl)
- [EMD-1273](https://www.ebi.ac.uk/pdbe/entry/emdb/EMD-1273), 免疫突触的断层图。
- PDB [1A0M](http://www.rcsb.org/pdb/explore.do?structureId=1a0m)，也即α-conotoxin的晶体密度（来自[电子密度服务器](http://eds.bmc.uu.se/eds/index.html)）和原子结构

> open 1080 from emdb  
> light full

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/emdb1080.png)

打开EM数据库图1080，照亮、有阴影

> volume #1 level 9

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/level.png)

在图上悬停鼠标，在状态行中会报告当前轮廓水平为1.675；然后更改水平。

> 点击图标 ![](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/mouse-icons/contour.png ':size=20x20')（在[工具栏]的**Right Mouse**标签里），来用鼠标控制轮廓水平，按下鼠标右键拖动

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/mouselevel.png)

如果是Mac的单键鼠标，按下**command**键的同时拖动

> vol #1 enclose 1e6 step 1 color tan

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/enclose.png)

把水平设置为封闭的1,000,000立方埃，显示全分辨率，并设置颜色

> set bg gray  
> set silhouettes true  

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/litmap.png)

设置背景为灰色和窄黑色轮廓线

> open 1grl 
> light default  

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/1grl.png)

打开原子模型来适配密度图，更简单的打光，没有阴影

> 点击图标 ![](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/mouse-icons/move_h2o.png ':size=20x20') ，用鼠标来移动选中的部分。**Ctrl**加鼠标单击原子来选中。然后用鼠标右键拖动来移动分子进入密度图。

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/handfit.png)

点击 ![](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/mouse-icons/rotate_h2o.png ':size=20x20') 图标，可以进入到旋转选中部分的鼠标模式。

> fit #2 in #1  
> volume #1 transparency 0.5  

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/fitmap.png)

在密度图中对原子模型进行局部对齐的优化。让密度图50%透明

> molmap #2 10  
> vol #3 style mesh

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/molmap.png)

建立原子模型的10埃分辨率模拟图，表示为网格。

> vol subtract #1 #3 minrms t  
> vol #4 color pink transparency 0  
> hide atoms; show riboon  

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/vopsub2.png)

从实验图上分解出模拟图

> close  
> set bg black; set silhouettes false  
> open 1a0m from eds

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/eds_1a0m.png)

打开来自电子密度服务器的PDB 1a0m 的x-ray图

> open 1a0m  
> hide ribbon  
> show atoms  
> vol #1 level 1.0 style mesh  

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/1a0m.png)

显示原子模型，并调整x-ray图的轮廓水平。

> vol zone #1 near #2 range 2  
> vol #1 level 0.5 transp 0.6

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/zone.png)

显示原子间隔在两埃之内的图区

> close  
> open emdb:1273

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/emdb1273.png)

打开T细胞的断层扫描图（200 MB），因为图较大，所以显示为单平面灰度图

> volume #1 region all showOutline true  

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/grayscale.png)

显示断层图的所有平面，进行灰度渲染。
