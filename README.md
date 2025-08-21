# lyrics-book
基于Python-docx自动合成的歌词本，支持中文（含粤语），日语（含中文翻译与罗马音），和英语（含中文翻译）

### 前言

网购歌词本太多歌曲不喜欢怎么办？自己~~纯度太高~~听的歌不太与他人一样怎么办？快来试试我耗时4h用deepseek写出来的一键生成歌词本代码罢！

## 使用

你可以到Github Actions下载构建，或者跟着下文的方法手动运行

### 系统环境，依赖处理

1. 作者系统环境：Win10 LTSC x64 （但是应该能装Python的系统都跑得起来吧）
   Python环境：Python 3.9 64bit
   因作者~~太懒~~实力不足，以下过程均以Windows环境下运行，并**默认你已经安装了Python pip等一系列工具**

2. 使用前**请先安装依赖**（python-docx lxml）
    - 使用release的lyrics_book.7z：请在CMD/powershell中执行以下命令```pip install python-docx lxml```
    - 使用源码：clone本仓库，然后在项目根目录下执行```pip install -r requirements.txt```
    - 使用Github Actions的打包构建：什么都不用做

3. 本项目为了实现更好的排版，使用[霞鹜新晰黑](https://github.com/lxgw/LxgwNeoXiHei)<sup>1</sup>作为默认排版字体（附fonts文件夹中）**建议**使用前安装本字体以在word中获得更好观赏体验。

### 操作步骤

1. 下载[releases](https://github.com/qazedc-abcd/lyrics-book/releases)里面的lyrics_book.7z 文件
2. 使用[163MusicLyrics](https://github.com/jitwxs/163MusicLyrics/releases)下载歌单中歌曲的.lrc文件并将其保存在lrc_files里（release中已包含该软件的7.1版本）
   当下载外语（特指日语英语，按需打开）![method1.png](https://raw.githubusercontent.com/qazedc-abcd/lyrics-book/refs/heads/main/photos/method1.png)
3. 打开”合成.bat“，等待合成，完成后窗口会自己关闭，打开output以查看.docx文档（输出页面为A5，双栏）

#### 输出文档的微调

哎...deepseek老是不能输出我满意的内容，那我就自己动手！

##### 改目录！

把原来的目录删掉了，用word里面自带目录生成器生成了目录，字体大小重新手调成了8

##### 加页码！

因为我想省纸，所以这样直接在页脚加会又吧页脚弹出来，占纸。怎么办呢>_<，有啦！导出为PDF，然后使用Adobe Acrobat 再加页码不就行了？所以我真这样做了。www,感觉这样做好蠢，但是我确实只会这样。![2](https://raw.githubusercontent.com/qazedc-abcd/lyrics-book/refs/heads/main/photos/meme-2.jpg)

##### 打印方面

使用Adobe Acrobat的打印里面的“小册子功能”，以普通的线装书为思路，设置10页一个PDF文档，最后合并，打印，装订，OK！
电子稿长这样![2](https://raw.githubusercontent.com/qazedc-abcd/lyrics-book/refs/heads/main/photos/eshow.png)（实体版正在制作中……)

### 后记

> [!NOTE]
>
> 存在歌词类别的问题。
>
> 1.如歌曲下等马中存在歌词“如果我下手太重すみません”有日语字符，所以被自动识别成了日语歌，但实际上是中文歌。本歌曲为V家曲（VC）故存在“调教”一说，但该代码只删掉了作词，作曲，没删掉这个。
>
> 该歌词版权由著作人chilichili所有，此处仅作展示![bug2](https://raw.githubusercontent.com/qazedc-abcd/lyrics-book/refs/heads/main/photos/bug2.png)
>
> 2.如歌曲Avid中存在日语英语歌词混搭现象，当一句歌词全是英文时没有罗马音，所以这里再次歇菜
>
> 该歌词版权由著作人澤野弘之所有，此处仅作展示![bug1](https://raw.githubusercontent.com/qazedc-abcd/lyrics-book/refs/heads/main/photos/bug1.png)

孩子没事快高三了想自己哼几首歌玩玩，拿DeepSeek-R1写的，传到github是为了给自己记录步骤免得忘了，有问题大概率页不会修（逃）将就着看看得了（真的）毕竟嘛...
![毕竟嘛....](https://raw.githubusercontent.com/qazedc-abcd/lyrics-book/refs/heads/main/photos/meme-1.jpg)

最后，我表示对霞鹜新晰黑，163MusicLyrics的作者以及提供全部~~（迫真）~~代码支持的deepseek表示感谢。没有你们的开源精神，开源社区不会走到现在。

#### 部分角标注

1.霞鹜新晰黑，一款衍生于「IPAexゴシック」的中文黑体字型，支持中日英多语言，将日本写法的字体改造成了中国大陆规范写法。（我看的顺眼）
链接见：https://github.com/lxgw/LxgwNeoXiHei

Copyright © 2025 qazedc-abcd <qazedc_hello@hotmail.com>
This work is free. You can redistribute it and/or modify it under the
terms of the Do What The Fuck You Want To Public License, Version 2,
as published by Sam Hocevar. See the COPYING file for more details.
