## 启动 

在图形化界面的启动中，ChimeraX的splash界面出现，几秒钟后替换为[ChimeraX窗口](https://www.cgl.ucsf.edu/chimerax/docs/user/window.html)，也请参见[启动偏好](https://www.cgl.ucsf.edu/chimerax/docs/user/preferences.html#startup)、[窗口偏好](https://www.cgl.ucsf.edu/chimerax/docs/user/preferences.html#window)

在**Windows**操作系统上：

ChimeraX可以通过点击图标启动。如果需要声明[选项参数](https://www.cgl.ucsf.edu/chimerax/docs/user/options.html)（如立体、nogui模式等）或者[输入文件](https://www.cgl.ucsf.edu/chimerax/docs/user/startup.html#inputfiles)，可以创建一个新的快捷方式：
  1. 右键拖动ChimeraX图标并从菜单中选择**复制到这里**来创建一个新的快捷方式
  2. 右键点击新的图标，从弹出菜单中选择**属性**
  3. 在弹出的面板里，点击**快捷方式**标签，并添加需要的[**参数**](https://www.cgl.ucsf.edu/chimerax/docs/user/options.html)和[**输入**](https://www.cgl.ucsf.edu/chimerax/docs/user/startup.html#inputfiles)到**目标(Target)**命令中。指向ChimeraX可执行程序的路径、参数、输入文件等，如果它们内部存在空格，则都应该用引号包裹，例如：

> "c:\Program Files\ChimeraX\bin\chimerax.exe" [--stereo](https://www.cgl.ucsf.edu/chimerax/docs/user/options.html#stereo) [--start](https://www.cgl.ucsf.edu/chimerax/docs/user/options.html#start) "Side View"  

  4. 保存之后点击新的图标可以带指定参数地启动ChimeraX了。


在**Linux**操作系统上：

ChimeraX可以从系统的命令行启动：

> $ chimerax [[*options*](https://www.cgl.ucsf.edu/chimerax/docs/user/options.html)] [[*input1 input2*](https://www.cgl.ucsf.edu/chimerax/docs/user/startup.html#inputfiles)...]

...使用安装程序创建的指向可执行程序的符号链接（可执行程序在ChimeraX安装目录的bin子文件夹里）


在**Mac OS X**操作系统上：

Chimerax可以通过点击图标或者拖放[已知类型文件](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/open.html#formats)到图标上来启动；当然它也可以从终端命令行打开：

> $ chimerax\_install\_dir/Contents/MacOS/ChimeraX [[*options*](https://www.cgl.ucsf.edu/chimerax/docs/user/options.html)] [[*input1 input2*](https://www.cgl.ucsf.edu/chimerax/docs/user/startup.html#inputfiles)...]

**chimerax_install_dir**通常指**/Applications/ChimraX.app**。从终端启动是在Mac上运行同一ChimeraX安装的多个实例的一种方法。


## 启动输入和命令

输入文件可能包含需要展示的数据，或者需要执行的命令或者代码。

任何[已知类型文件](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/open.html#formats)都可以在命令行[启动](https://www.cgl.ucsf.edu/chimerax/docs/user/startup.html#top)的时候打开，由本地路径名或URL说明的文件格式由[文件名后缀](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/open.html#file-table)指示。.gz后缀的压缩文件也能被读取。从网络数据库获取的文件的格式由紧跟着冒号的[源前缀](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/open.html#fetch-table)指示。例如emdb:1024

如果提供了有效的四个字符的识别码，那么默认源前缀**pdb**可以被忽略。

保存在**\~/chimerax_start**文件夹（\~是用户家目录）下的Python文件可以在软件启动的时候自动导入。

在[ChimeraX命令行界面](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/cli.html)启动的时候要执行的[ChimeraX命令](https://www.cgl.ucsf.edu/chimerax/docs/user/index.html#commands)可以在[启动偏好](https://www.cgl.ucsf.edu/chimerax/docs/user/preferences.html#startup)进行设置。如果ChimeraX是[nogui mode](https://www.cgl.ucsf.edu/chimerax/docs/user/options.html#nogui)（没有图形用户界面的模式）启动的，也没有命令/脚本输入文件的话，一个输入提示符会显示在系统终端，共用户通过标准输入设备进行[命令](https://www.cgl.ucsf.edu/chimerax/docs/user/index.html#commands)输入。


## 退出ChimeraX

ChimeraX可以通过点击窗口的关闭按钮、或者点击ChimeraX菜单的**Quit**、或者在[命令行](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/cli.html)输入[**exit** or **quit**](https://www.cgl.ucsf.edu/chimerax/docs/user/commands/exit.html)命令进行退出。
