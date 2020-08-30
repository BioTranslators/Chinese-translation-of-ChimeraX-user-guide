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
---
> open 2bbv
> light full

![](https://www.cgl.ucsf.edu/chimerax/docs/quickstart/images/colorchain.png)

文件从PDB以mmCIF格式取回并缓存在本地。照亮、有阴影。

## 示例：密度图命令
