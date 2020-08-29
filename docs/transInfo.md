## forTranslators 200826

不知道你愿不愿意学一下git的操作？

我在github上面创建了[team](https://github.com/BioTranslators)和[仓库](https://github.com/BioTranslators/Chinese-translation-of-ChimeraX-user-guide)，并通过[docsify](https://docsify.js.org/#/)创建了[译文的网站](https://biotranslators.github.io/Chinese-translation-of-ChimeraX-user-guide/#/)；译文文档提交到仓库，就可以实时发布到网站上。



如果你比较忙的话，那可以直接把译文写成markdown文档发给我，我来提交。

如果你觉得可以学git的话，那你可以创个GitHub账号，我把你拉进team，然后你就可以直接通过git对仓库进行修改。这个仓库有两个分支：master和dev；你可以直接对master分支进行修改。总的来说，你需要学习**git操作、GitHub**。

git操作可以参考廖雪峰的[git教程](https://www.liaoxuefeng.com/wiki/896043488029600)，GitHub的操作很简单，可以看看知乎的话题。

安装git的话，如果你是windows，比较推荐你[cmder](https://cmder.net/)这个集成了git的命令行工具，不用安装就可以用，或者你也可以选择git的一个desktop版本。装好git之后需要配置ssh密钥到你的个人账号，配置好之后就可以在本地访问GitHub的仓库了。

## 关于docsify
docsify是网站所使用的框架。我们这个网站主要由一个index.html文件以及众多markdown文件构成。
index.html是必要的，里面设置了很多网站参数。
_coverpage.md控制封面内容
README.md(这里指doc文件夹内的README.md)控制封面下滑页面的内容。
_sidebar.md内则写明了侧边栏的内容，这是一个很重要的文件，我们依靠它连接网站首页和我们的译文页面。
其它的md文件则主要是我们的译文文件了。

## 关于链接的处理 200829

目前的想法是，用类似于广度搜索的方法，第一遍只翻译文本，对于链接跳转的地方，一律采用原始链接；等主体部分全部译成中文之后，再对于跳转的地方进行修改或者翻译。

## 关于图片的处理 200829

图片目前先一律使用原始链接，用图片的方式插入到markdown中即可。排版方式可能没法按照原始网页进行排版，可以进行适当调整。

## 关于译文文件命名和修改_sidebar.md
译文文件命名可以中文也可以英文，但是词与词之间最好下划线连接，不要有空格短横线破折号之类的符号。

译文文件名字需要添加到_sidebar.md中才可以生效，比如翻译了_sidebar.md文件中[教程]对应的译文，则译文文件名应及时添加到_sidebar.md文件中[教程]之后的括号里，如：
```
- [教程](/)
- [教程](tutorial.md)
- [教程](教程.md)
```