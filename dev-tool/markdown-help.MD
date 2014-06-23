##Markdown简明教程

###一. 概述

Markdown的优点我就不讲了。需要说明的是，本教程基于Markdown的Github衍生版本(GFM,Github Flavored Markdown)，与Markdown的标准版会有所不同,当然文中会说明两个版本有差异的部分。

各平台Markdown部分编辑器推荐:

* Web: [Cmd Markdown](https://www.zybuluo.com/mdeditor) (在线Markdown编辑器)
* Windows: [MarkdownPad](http://www.markdownpad.com/) (免费版功能有限制,需要花$15才能支持GFM语法)
* Linux: [ReText](http://sourceforge.net/p/retext/home/ReText/) (免费下载和使用,Ubuntu v10.04+ 可以通过 [ppa:mitya57](https://launchpad.net/~mitya57/+archive/ppa)下载安装)
* Mac: [Mou](http://mouapp.com/) (免费下载和使用)

###二. 语法

* **换行**: 只要在需要换行的地方添加一条新行即可(敲两次以上Enter键)，如:
    <pre><code>这是第一行(Enter)
    (Enter)...
    这是第二行</code></pre>

    Tip: 一条以上的新行都会被视为一行
* **标题**: Markdown提供了六种规格的标题，分别对应html标签中的&lt;h1&gt;-&lt;h6&gt;。通过在标题的前面添加不同数量的\#字符可以实现不同大小的标题，如:
    <pre><code>#最大的标题(相当于一个&lt;h1&gt;标签)
    </br>##次大的标题(相当于一个&lt;h2&gt;标签)
    ...
    </br>######最小的标题(相当于一个&lt;h6&gt;标签)</code></pre>

    Tip: <span>#</span>越多，标题越小
* **引用**: 先看效果
    > Software is like sex; it's better when it's free.
    >> HeHe.
    
    实现方法就是在前面加&gt;，像这样:
 <pre><code>&gt; Software is like sex; it's better when it's free.
</br>&gt;&gt; HeHe.
</code></pre>
* **粗体和斜体**: 斜体和粗体的实现符号是一样的，就是符号的数量不一样,如:

    <pre><code>*斜体1*   _斜体2_
    </br>**粗体1** __粗体2__
    </br>***粗斜体1*** ___粗斜体2___
    </code></pre>
    
    由于变量命名时经常要使用\_，所以GFM规定，语句中间的两个\_不渲染为斜体，如:
    标准Markdown: 一个_斜体_啊 (一个\_斜体\_啊)
    GFM: 一个\_斜体\_啊(一个\_斜体\_啊) _一个\_斜体\_啊_ (\_一个\_斜体\_啊\_)
        
* **列表**: 先说有序列表，有序列表很简单，直接打数字，点和空格就行，如:
    1. 项目1
    2. 项目2
    3. 项目3

    无序列表则要把有序列表的数字和点换成\*或\_即可，如:
    * 项目1 (\*项目1)
    * 项目2 (\*项目2)
    * 项目3 (\*项目3)
    
    以及子项目表示(缩进一个tab):
    * 项目1
        * 子项目1
        * 子项目2
    * 项目2
        * 子项目1
            
* **代码块**: 先看效果
    ```
    public static final int GIT = 10000;
    ```
    ```
    def hello():
        print 'Hello World!'
    ```
    
    实现方式如下:
    \```
    public static final int GIT = 10000;
    \```
    GFM扩展了Markdown的代码块功能，使不同语言展现不同的代码高亮风格，如:
    ```java
    public static final int GIT = 10000;
    ```
    ```python
    def hello():
        print 'Hello World!'
    ```
    实现方式就是在第一个\```添加语言名称，如:
    \```java
    public static final int GIT = 10000;
    \```
    
* **链接**: 标准的Markdown中，需要为链接添加描述，如:
    <pre><code>[Visit Github](http://www.github.com)</code></pre>
    效果: [Visit Github](http://www.github.com)
    GFM对Markdown链接做了简化，只要输入http://www.github.com，GFM就会自动生成链接。
* **表格**: 标准的Markdown中并不支持表格，但GFM可以
    表头1  |  表头2
    ------- | -------
    单元格1 | 单元格2
    单元格3 | 单元格4

    实现方法:
    表头1  \|  表头2
    \------- | -------
    单元格1 \| 单元格2
    单元格3 \| 单元格4

    而且还可以通过\:符号来决定单元格的对齐方向
    表头1  |  表头2  |  表头3
    :----- | :-----: | ----:
    左对齐1  |  居中1  |  右对齐1
    左对齐2  |  居中2  |  右对齐2
    
    实现方法:
     表头1  \|  表头2  \|  表头3
    \:\----- \| \:-----: | \----:
    左对齐1  \|  居中1  \|  右对齐1
    左对齐2  \|  居中2  \|  右对齐2

* **图片**: 插入图片和添加链接类似，只要在描述前面加个!就行了，先看效果:
    ![Github](http://www.oschina.net/uploads/img/201011/05074222_v51b.png)
  
  实现方法:
  <pre><code>![Github](http://www.oschina.net/uploads/img/201011/05074222_v51b.png)</code></pre>
    Tip: 关于图片和链接还有一种更“高级”的写法，该写法便于对链接的管理，展示如下:
<pre><code>![Github][1]  

[1] http://www.oschina.net/uploads/img/201011/05074222_v51b.png</code></pre>
* **特殊字符转义**: 自此，本文总共使用了Markdown字符为: \_, \* , \> , \``` ,\# 等。如果需要在正文里使用这些特殊字符的话，可以1). 用\\来转义 2). 使用html标签(&lt;span&gt;\_&lt;/span&gt;，标准Markdown不支持)
###三. 说明
这篇教程就是用Markdown写的，文中出现的任何错误欢迎指正。
