# HTML5基础
## 1、什么是HTML5？
- web 1.0静态页面   -->   web 2.0 交互 --> HTML5时代   
    HTML4   XHTML1.0
- HTML的升级版本，不仅用来表示web内容，而且将web带入一个更加成熟的平台。在HTML5平台上，音频、视频、图像、动画、交互等都被标准化
    2004年 提出
    2007年 被W3C接纳   成立HTML工作组
    2008年 第一份正式草案
    2014年 W3C HTML工作组 发布第一份官方推荐标准
    2020年 完成最终测试
    2022年 正式发布
## 2、HTML5中的新特性
- 新增的语义化标签
- 新增的表单元素和表单属性
- 新增的在网页上绘制图像的canvas元素
- 新增了多媒体相关的video、audio元素
- 对本地离线存储的更好支持
    - 本地存储：提供两种客户端存储数据的方法——localStorage、sessionStorage
    - 离线应用
## 3、HTML5新增标签
### 1）新增结构标签
- 网页的头部区域或某个模块的头部
    - 一种具有引导和导航作用的结构元素，定义文档或某个区域的头部信息。通常包含整个页面或一个内容块的标题、搜索框、LOGO等
```
<header></header>
```
- 网页的底部区域或某个模块的底部
    - 定义文档或文档中某个区域的底部信息，通常包含网页中的版权信息、相关链接、文档的作者信息、使用条款链接等等
```
<footer></footer>
```
- 导航
    - 定义导航链接的部分，通常包含页面中的主要的导航链接（传统导航、侧边栏导航、页内导航、翻页操作等）
```
<nav></nav>
```
- 页面中独立、完整的内容
    - 可以包含header标签，一篇有自身含义的文章。通常包含一篇博文、论坛帖子、报刊中的文章、一段用户评论或独立的插件
```
<article></article>
```
- 页面中内容的章节
    - 通常一个section由标题和内容组成
```
<section></section>
```
- 侧边栏
    - 当前页面或文章的附属信息，通常包含与主要内容相关的引用、侧边栏、广告、链接组等
```
<aside></aside>
```
- 标题组
    - 可以作为标题或子标题的分组，通常与h1~h6组合使用
```
<hgroup></hgroup>
```
- 文章中的联系信息
    - 通常包含文档作者或文档的编辑者的名字、电子邮箱、电话号码、地址等
```
<address></address>
```
> 块级标记、文字自带倾斜效果

### 2）新增其他标签
- figure标签
    - figcaption标签，在一个figure标签中只能有一个figcaption标签
    ```
    <figure>
        被主体内容引用的内容，相对独立的内容块，如：图片、代码块、图表等
        <figcaption>定义figure标签的标题</figcaption>
    </figure>
    ```
    > 自带间距、块级元素
- 带有标记的文本
    - 页面中突出显示的，高亮的部分
    - 行级标记、自带背景颜色（黄色）、自带文字颜色（黑色），颜色可修改
```
<mark></mark>
```
- 日期时间标签
    - 公历日期时间
    - 行级标记
    ```
    <time>2020-9-18</time>
    <time pubdate="pubdate" datetime="2020-9-18"></time>
        pubdate属性：当前内容的发布时间
        datetime属性：日期时间；如果没有定义该属性，则必须在time标签中设置日期时间
    ```
- 进度条
    - 行块级元素
    ```
    <progress max="" value=""></progress>
        max属性：最大值
    ```
## 4、HTML5兼容
- 最新版本的chrome、Firefox、Opera、Safari、IE10+支持HTML5
- IE9支持部分HTML5特性
- IE8及更早版本的浏览器中对HTML5新增元素有兼容问题
### 1）使用JavaScript新增元素的方法解决
```
结构中：<div id="box"></div>
javascript：
    <script>
        //1、新建一个header元素
        var ele = document.createElement("header");//新建header元素放在ele容器中

        //2、找到#box的盒子
        var oBox = document.getElementById('box');//找到#box盒子，放在oBox容器中

        //3、在#box盒子(oBox)中追加新建的header的元素(ele)
        oBox.appendChild(ele);
    </script>
样式中：
    将新建的header标签转为块级元素
```
### 2）使用谷歌提供的html5shiv.js插件解决
    用于解决IE9及以下版本的浏览器对HTML5新增元素的不兼容问题
    > 必须写在网页的头部（head标签内）
    ```
    <!--[if lte IE 9]>
        <script src="js/html5shiv.min.js"></script>
    <![endif]-->
    ```
## 5、HTML5中已经移除的标签
- acronym标签：首字母缩写
- applet标签：嵌入applet
- font标签：定位字体、颜色、字号
- basefont标签：默认字体、颜色、字号
- big标签：大号文本
- center标签：文本居中
- s标签：删除线文本
- strike标签： 删除线文本
- u标签：下划线文本
- dir标签：目录
- frame标签：框架或窗口
- frameset标签：框架集
- noframes：不支持框架的用户替代内容
...

## 6、新增多媒体标签
### 1）audio标签
- HTML5中新增的音频的标准方法
- IE8及更早版本的浏览器中不支持
- HTML5中支持的音频格式
    - ogg  audio/ogg  支持浏览器：chrome、Firefox、Opera10+
    - mp3  audio/mpeg 支持浏览器：chrome、Firefox、Opera10+、IE9+、Safari
    - wav  audio/wav  支持浏览器：chrome、firefox、Opera、Safari
- 语法：
```
<audio src="音频文件路径">您的浏览器不支持audio元素，播放音频文件</audio>
```
- 常用属性
    - src属性：音频文件的路径
    - controls属性：浏览器为音频提供的播放控件
    - loop属性：循环播放
    - muted属性：静音
### source标签
可以链接不同格式的文件（音频、视频），浏览器使用第一个可以被识别的格式
```
    <audio controls>
        <source src="videoAudio/nada1.wav">
        <source src="videoAudio/biubiubiu2.ogg">
        <source src="videoAudio/hanmai.mp3">
        您的浏览器不支持audio元素，播放音频文件
    </audio>
```
### 2）video标签
- HTML5中视频标准方法
- IE8及更早版本浏览器中不支持video标签
- HTML5支持的视频格式：
    - ogg  支持浏览器：chrome、Firefox、Opera
    - mp4--MPEG4  支持浏览器：chrome、Firefox、Safari、IE9+
    - webM 支持浏览器：chrome、Firefox、Opera
- 语法
```
<video src="视频文件的路径">您的浏览器不支持video元素，播放视频文件</video>
```
- 常用属性
    - src属性：视频文件路径
    - controls属性：播放控件
    - loop属性：循环播放
    - muted属性

    - width属性、height属性：视频播放器的宽度和高度
    - poster属性：预览图片，视频正在下载时显示的图像
## 7、新增表单元素及属性
### 1）新增表单元素
- 包含访问协议的完整的路径的输入域，在提交表单时，自动验证url域的内容
```
<input type="url" placeholder="请输入地址" name="userUrl">
```
- 包含e-mail地址的输入域，在提交表单时，自动验证email域的值
```
<input type="email" placeholder="请输入邮箱地址" name="e-mail">
```

- 用于搜索关键字的文本输入域，一般用于手机客户端
```
<input type="search" placeholder="请输入要检索的内容">
```
- 用于输入电话号码的文本输入域，用于触屏网页开发，在电脑网页中无效，在触屏网页中点击输入域，弹出虚拟电话键盘（0-9、*、#）
```
<input type="tel" placeholder="请输入电话号码">
```

- 用于包含数值的输入域
```
<input type="number" max="10" min="0" value="0" step="2">
    max属性：最大值
    min属性：最小值
    step属性：步长，合法的数字间隔，默认为1
```
> 当用户输入的数值不在制定范围内时，会弹出相关提示信息，并阻止表单提交
- 用于生成一个数字滑动条，跟number类型相似，区别在于外观样式不同，默认值不同。
```
<input type="range" max="10" min="0" value="0" step="2">
```
> range类型的min值默认0，max属性默认为100

- 用于生成一个颜色选择器，值为十六进制色值
```
<input type="color">
<input type="color" value="#ff0000">
```

### input的日期时间类型
- 从一个日期选择器中选择一个日期，包含年、月、日
```
<input type="date">
```
- 手动输入一个日期时间（UTC时间）
1884年 华盛顿  国际经度会议  划分24个时区   英国格林尼治天文台为中时区， 中国UTC+8 东8区   UTC-10
```
<input type="datetime">
```
- datetime-local类型 ，从一个日期时间选择器中选择一个日期时间，包含年、月、日、时、分
```
<input type="datetime-local">
```
- month类型，从一个日期选择器中选择一个月份，包含年、月
```
<input type="month">
```
- time类型，从一个时间选择器中选择一个时间，包含时、分
```
<input type="time">
```
- week类型，从一个日期选择器中选择周，包含年、周（全年的第几周）
```
<input type="week">
```

- datalist标签：可选下拉列表，需要与input标签配合使用，通过input标签的list属性和datalist标签的id属性关联
```
<input list="con">
<datalist id="con">
    <option value="abcd">abcd</option>
    <option value="123">123</option>
</datalist>
```
### 2）新增表单属性
- placeholder属性
    设置文本域的提示信息，当用户开始输入内容，提示信息消失
- min、max、step属性
    最小值、最大值、合法的数字间隔
    用于包含数字的input类型，规定数值范围，如：input的numbet、range类型等
- list属性
    实现数据列表的下拉效果
    用于input标签和datalist标签关联，实现可选下拉列表

- autocomplete属性
    设置表单是否可以启用自动完成功能，可以加在form标签、input标签上
    - autocomplete="on" 启用自动完成功能
    - autocomplete="off" 不启用自动完成功能
    > 必须在input标签中添加name属性
```
    <form action="#" autocomplete="off">
        <div><input type="text" placeholder="请输入用户名" name="user"></div>

        <div><input type="text" placeholder="请输入昵称" name="userName" autocomplete="on"></div>

        <hr>
        <input type="submit">
    </form>
```
- autofocus属性
    页面加载时自动获取焦点，一个页面中只能有一个表单元素具有这个属性
```
<input type="text" placeholder="请输入昵称" name="userName" autofocus>
```

- required属性
    提交表单时元素不能为空
    > 要让属性有效，则不能添加value值
```
<input type="text" required>
```
- pattern属性
    验证输入内容——正则表达式
    ```
    <input type="text" name="content" placeholder="请输入5位字母数字" pattern="[0-9a-zA-Z]{5}">
    ```
- multiple属性
    可以选择多个值
    用于上传域file类型和email类型的文本输入域
    ```
    <input type="file" multiple>
    ```
- form属性
    设置输入域所属的表单
    ```
    <form action="#" id="wrap">
        <div><input type="text" placeholder="请输入用户名" name="user"></div>
    </form>
    <div><input type="submit" form="wrap"></div>
    <div><input type="text" name="user2" form="wrap"></div>
    ```

