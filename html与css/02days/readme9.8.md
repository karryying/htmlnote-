# 超链接标签——a标签
## 1、语法
```
<a href="链接的URL地址" title="鼠标悬停时的提示信息" target="_blank|_self">链接文字</a>
```
- href属性：超链接的目标——已有网站、本地文件、空链接（#）、锚点链接、伪链接（不跳转）
```
    <a href="http://www.baidu.com"></a>
    <a href="http://www.baidu.com">百度</a>
    <a href="http://www.baidu.com">百度</a>
    <a href="readme.md">readme.md</a>
    <a href="images/comp.jpg">comp.jpg</a>
    <a href="#">占位|跳转到当前页顶部</a>
    <a href="javascript:">内容</a>
    <a href="javascript:alert('a')">内容</a>
```
- target属性
    - target="_blannk" 在新窗口打开
    - target="_self" 默认值，在当前窗口显示
## 2、特点
- 行级元素
- 宽度默认由内容撑开
- 高度默认由内容撑开
- 默认横向显示——水平布局
- 自带下划线
- 自带文字颜色
- 换行和空格会被解析
## 3、锚点使用
跳转到长页面的某个位置、跳转到某个文件的特殊位置
- 定义锚点
```
<a name="锚点名称"></a>
<div id="锚点名称">[content]</div>
```
- 引用锚点
```
<a href="#锚点名称">链接文字</a>  页内跳转
<a href="文件路径#锚点名称">链接文字</a>  跳转到某个文件的特殊位置
```

# 列表——块级元素
## 1、无序列表
无次序、无级别，列表项之间是并列关系
- 语法
```
    <ul><!-- 列表容器 -->
        <li>列表项</li>
        <li>列表项</li>
        <li>列表项</li>
    </ul>
```
- 特性
    - 宽度默认撑满整个父元素
    - 高度默认由内容撑开
    - 独立成行——垂直布局
    - 自带间距
    - 自带填充
    - 自带列表符
- css属性
    - list-style-type属性 列表符类型
        none无列表符号   disc实心圆,默认值   circle空心圆   square实心方块
    - list-style-position属性 列表符的放置位置
        - list-style-position: inside; 列表符放在文本内
        - list-style-position: outside; 默认值，列表符放在文本的外侧
    - list-style属性
        list-style: list-style-type  list-style-position;
    ```list-style: none; 去掉列表符```
## 2、有序列表
有排列次序，各个列表项之间是并列关系
- 语法
```
    <ol>
        <li>列表项</li>
        <li>列表项</li>
        <li>列表项</li>
    </ol>
    <ol start="5" type="a" reversed>
        <li>列表项1</li>
        <li>列表项2</li>
        <li>列表项3</li>
    </ol>
    start属性：开始值
    type属性：列表符类型
    reversed属性：倒序
```
- 特性
    与无序列表基本一致
## 3、自定义列表
- 语法
```
<dl>
    <dt>列表标题 或专业术语</dt>
    <dd>列表项或对专业术语的解释</dd>
    <dt>专业术语</dt>
    <dd>对专业术语的解释</dd>
</dl>
```
> 浏览器显示，dd标签中的内容会缩进显示
- 特性
    - 宽度默认撑满整个父元素
    - 高度默认由内容撑开
    - 独立成行——垂直布局
    - 自带间距
# 表格
- 早期 实现页面布局
- 现在 用来显示表格数据
- 表格——将数据有效地组织在一起，并以网格的形式进行显示
## 1、创建表格
- 创建基本表格
包含table标签、tr标签、单元格；单元格中可以放置任意内容（文本、标签）
```
    <table border="1"><!-- 表格容器，用来定义表格 -->
        <tr><!-- 表格的行，必须嵌套在table内部 -->
            <th>表头单元格</th><!-- 默认文字加粗，水平、垂直居中显示 -->
            <th>单元格</th>
        </tr>
        <tr>
            <td>单元格</td>
            <td>普通单元格</td><!-- 默认水平居左，垂直居中显示 -->
        </tr>
    </table>
```
- 复杂表格的语法
可以thead、tbody、tfoot划分表格结构
```
<table border="1">
        <caption>表格标题</caption><!-- 在表格中水平居中显示，只在表格中有意义 -->
        <thead><!-- 表格的头，放置标题之类的内容，内部必须要有tr标签 -->
            <tr>
                <th>表头单元格</th>
                <th>单元格</th>
            </tr>
        </thead>
        <tbody><!-- 表格的正文，放置表格数据 -->
            <tr>
                <td>单元格</td>
                <td>普通单元格</td>
            </tr>
        </tbody>
        <tfoot><!-- 表格的脚注，放置脚注之类的内容 -->
            <tr>
                <td>单元格</td>
                <td>单元格</td>
            </tr>
        </tfoot>
    </table>
```
> 注意：在一个table标签中只能有一个thead和一个tfoot，但是可以有多个tbody标签，这些标签只能放在table标签中
## 2、表格特性
- 有内容，没有设置宽度的单元格，由内容撑开
- 没有内容，没有设置宽度的单元格，默认平分整个表格
- 同一行单元格，高度只会识别一个，取最大值
- 同一列单元格，宽度只会识别一个，取最大值
## 3、表格属性
- border属性：表格边框
    - border="0" 默认，没有边框
    - border="1"
- width属性：宽度
- height属性：高度

- cellpadding属性：单元格内容和边框之间的距离
- cellspacing属性：单元格之间的距离，默认值2px
```
<table border="1" cellpadding="30" cellspacing="0"></table>
```
- 合并单元格
    - 跨列合并单元格 colspan="合并单元格的数量"
    - 跨行合并单元格 rowspan="合并单元格的数量"
    - 实现步骤
        - 1）确定跨行、跨列合并单元格
        - 2）找到目标单元格，添加合并单元格属性设置合并属性
        - 3）删除多余的单元格
- 表格的css属性
    - border-collapse属性
        - border-collapse: collapse; 边框合并
        - border-collapse: separate; 单元格边框独立，默认值
    - border-spacing属性 当边框独立时，行和单元格在水平方向和垂直方向的间距
        - 如果有两个值，第一个值表示水平方向，第二个值表示垂直方向
        - 如果只有一个值，表示水平和垂直方向的间距
## 总结
- 表格优点：方便排列一些有规律的、结构均匀的内容或数据
- 表格缺点：产生垃圾代码，影响页面下载速度、时间，灵活性不打，难于修改

# HTML语义化
## 1、什么是HTML语义化？
根据页面内容结构，选择合适的标签。便于开发者阅读和写出更优雅的代码；便于浏览器、搜索引擎解析；便于团队开发和维护；有利于SEO。如：标题使用h1~h6，段落用p标签。

## 2、语义化的好处有哪些？
- 在没有css的情况下，页面也能呈现出较好的内容结构
- 使代码更具可读性，便于团队开发和维护
- 有利于用户体验
- 有利于SEO搜索引擎优化，和搜索引擎建立良好的沟通，有助于爬虫抓取关键字

# 标签的合理嵌套
- ul和li,ol和li,dl和dt、dd拥有父子关系的标签，ul和ol的第一级子元素只能有li,dl的第一级子元素只能使dt和dd
- p、dt、h系列标签中不能嵌套块级元素
- a标签不能嵌套a标签
- 行级元素不能嵌套块级元素

# CSS——cascading style sheet
层叠样式表或级联样式表。为HTML页面文本内容、图片外形、版本的布局等外观样式的设置。
实现了页面内容和样式的彻底分离，提高工作效率
## 1、css语法
- 组成；选择器{ 属性名称1: 属性值; 属性名称2: 属性值; }
    找对象（标签）
    属性名称1: 属性值————声明语句，多个声明语句之间用分号隔开，属性名称和属性值之间用冒号隔开
- 注释——ctrl+/  shift + alt +a
    /* css注释 */
## 2、css特点
- 可以取代之前一部分必须使用专门图像处理软件实现的图片特效功能
- 利于管理样式，方便排版，简化管理成本
- 便于统一风格
- 几乎所有浏览器都支持
## 3、css样式的引入方式
### 1）行间样式——内联式
- 位置：放在开始标签内部
- 语法：使用style属性
```
<div style="width: 100px; height: 100px; background-color: red;"></div>
    width属性：元素的宽度，属性值单位px像素
    height属性：元素的高度，属性值单位px像素
    background-color属性：背景颜色，属性值可以设置关键词 red红色
```
- 应用场景
适用于单个元素需要有特殊样式
- 优缺点：
比较直观、相同样式需要重复定义，造成代码冗余、作用范围较小，大量使用不利于后期维护，代码不能复用；结构和表现不分离
### 2）内部样式——嵌入式
- 位置：放在head标签内部
- 语法：使用style标签对
```
<head>
    <style type="text/css"></style>
</head>
```
- 应用场景
适用于单个HTML文档需要特殊样式
- 优缺点：
相对于行间样式，作用范围较大，代码可以复用；结构和表现半分离
### 3）外部样式——外链式
- 位置：将在外部新建的css文件，在head标签中通过link标签引入
- 语法：
```
<link href="css文件路径" rel="stylesheet" type="text/css">
    rel属性：当前文档和被链接文档之间的关系。只有stylesheet得到所有浏览器支持，表示外部文件类型是css文件
```
- 应用场景
适用于多个HTML文档拥有相同样式
- 优缺点
便于修改、维护，使用范围广，代码可以复用。结构和表现彻底分离
- 书写步骤
    - 1）新建一个css文件夹，在文件夹中新建一个后缀名为.css的文件
    - 2）在外部的.css文件中设置编码方式：
    ```
    @charset "utf-8";
    ```
    - 3）在html文档中，head标签内部，写link标签引入外部样式
    ```
    <link rel="stylesheet" href="css/*.css">
    ```
### 样式引入方式的优先级
- 行间样式优于内部和外部样式
- 内部样式和外部样式就近原则


# 选择器
## 1、通配符选择器 *
单独使用，匹配所有元素
## 2、标签选择器
- 元素选择器
- 以标签名称作为选择器，选取所有对应名称的标签
- 语法
```
结构中：<标签名></标签名>
样式中：标签名{ 声明语句 }
```
