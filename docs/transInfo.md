## forTranslators 200826

不知道你愿不愿意学一下git的操作？

我在github上面创建了[team](https://github.com/BioTranslators)和[仓库](https://github.com/BioTranslators/Chinese-translation-of-ChimeraX-user-guide)，并通过[docsify](https://docsify.js.org/#/)创建了[译文的网站](https://biotranslators.github.io/Chinese-translation-of-ChimeraX-user-guide/#/)；译文文档提交到仓库，就可以实时发布到网站上。

如果你比较忙的话，那可以直接把译文写成markdown文档发给我，我来提交。

如果你觉得可以学git的话，那你可以创个GitHub账号，我把你拉进team，然后你就可以直接通过git对仓库进行修改。这个仓库有两个分支：master和dev；你可以直接对master分支进行修改。总的来说，你需要学习**git操作、GitHub**。

git操作可以参考廖雪峰的[git教程](https://www.liaoxuefeng.com/wiki/896043488029600)，GitHub的操作很简单，可以看看知乎的话题。

安装git的话，如果你是windows，比较推荐你[cmder](https://cmder.net/)这个集成了git的命令行工具，不用安装就可以用，或者你也可以直接下载git for windows。装好git之后需要配置ssh密钥到你的个人账号，配置好之后就可以在本地访问GitHub的仓库了。


## 关于docsify 200826
docsify是网站所使用的框架。我们这个网站主要由一个index.html文件以及众多markdown文件构成。

index.html是必要的，里面设置了很多网站参数。
_coverpage.md控制封面内容。
README.md(这里指doc文件夹内的README.md)控制封面下滑页面的内容。
_sidebar.md内则写明了侧边栏的内容，这是一个很重要的文件，我们依靠它连接网站首页和我们的译文页面。
其它的md文件则主要是我们的译文文件了。

如果需要实时预览自己的译文，可以在电脑里装上npm（要装上[nodejs](https://nodejs.org/zh-cn/)，这是一个js的"解释器"，npm是它的包管理器；js、nodejs、npm这三者的关系类似于python、python解释器、pip）。然后用npm装上docsify-cli，如此，可以通过`docsify serve ./docs`一边编辑一边实时预览自己的网站。


## 关于译文文件命名和修改_sidebar.md 200826
译文文件命名可以中文也可以英文，但是词与词之间最好下划线连接，不要有空格短横线破折号之类的符号。

译文文件名字需要添加到_sidebar.md中才可以生效，比如翻译了_sidebar.md文件中[教程]对应的译文，则译文文件名应及时添加到_sidebar.md文件中[教程]之后的括号里，如：

```
- [教程](/)
- [教程](tutorial.md)
- [教程](教程.md)
```

## 关于链接的处理 200829

目前的想法是，用类似于广度搜索的方法，第一遍只翻译文本，对于链接跳转的地方，一律采用原始链接；等主体部分全部译成中文之后，再对于跳转的地方进行修改或者翻译。


## 关于图片的处理 200829

图片目前先一律使用原始链接，用图片的方式插入到markdown中即可。排版方式可能没法按照原始网页进行排版，可以进行适当调整。
如果要修改图片尺寸，请参考<https://docsify.js.org/#/helpers?id=resizing>

```
![camera](https://www.cgl.ucsf.edu/chimerax/docs/user/tools/shortcut-icons/video.png ':size=20x20')
```


## 关于视频的处理 200830
插入到markdown文档中，参见<https://angry-swanson-b4e47b.netlify.app/zh-cn/embed-files>，代码示例：

```markdown
[spin movie](media/quick_start_guide_spin.mp4 ':include')
```

要注意插入的语法，`':include'`与文件名中间只有一个空格，默认工作目录是在docs文件夹里，所以写medie路径的时候从media开始写，放在media文件夹里的图片等也是同理。


**media**文件夹被用于存放某些多媒体文件，图片文件一般直接引用原始链接，但某些多媒体文件可能原始链接插入到译文中无法生效，可以下载到media文件夹中并插入到译文。如果多媒体文件名有重复，可以在名字前面加上前缀：译文名 + 文件名，如`quick_start_guide_spin.mp4`。


## 关于软件中命令和按钮的处理 200830

所有文中出现的命令，如果是短命令（如`help', 'select'等）均采用markdown的行内代码格式，也即在命令前后加上单引号。
所有文中出现的长命令（自己感觉长不长哈哈哈）采用代码块或者引用的方式翻译，示例如下：

```ChimeraX
select protein
```

或者：

> Usage: **Select** *spec* [ **residues** true | false ][ **sequence** *pattern*][**polymer** *chain-spec*]

所有命令的Usage比较建议使用引用的方式翻译，稍微好看一些。

所有软件中按钮或者按键的翻译，建议使用加粗标示，比如**File**。

如果使用`>`创建多行引用来表示命令，记得在每行命令末尾加上*两个空格*，防止解析的时候被显示为一行。


## 关于xxx.github.io无法访问的问题 200901

参考<https://juejin.im/post/6863358382410203144>，改改DNS就好了；如果有必要，或许我们应该迁移到gitee?!


## 关于cmder的git-gui 200901

我在cmder的目录下发现了一个git的可视化工具，cmder\vendor\git-for-windows\cmd\git-gui.exe，可以完成git的大多数任务，有点儿界面，可以看到文件的哪些地方被更改，还挺好的。

关于它中文显示为乱码的问题，可以参考<https://gist.github.com/nightire/5069597>；在cmder里面输入这几条命令就可以了：

```cmder
git config --global core.quotepath false  		# 显示 status 编码
git config --global gui.encoding utf-8			# 图形界面编码
git config --global i18n.commit.encoding utf-8	# 提交信息编码
git config --global i18n.logoutputencoding utf-8	# 输出 log 编码
```

常见git客户端比如说git desktop，今天也看到一个评价比较好的，[Tower](https://www.git-tower.com/windows)，它的官网的git教程也是很不错的，如果不喜欢命令行，可以下载Tower试试。