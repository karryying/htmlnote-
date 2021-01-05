# 回顾——响应式布局
    一个网站适配所有终端，实现不同屏幕分辨率下的终端网页的不同布局；使用媒体查询针对不同宽度的设备进行布局和样式设置，从而达到适配不同设备的目的
- 优点：一站适配所有终端、减少工作量；缩短开发周期；对搜索引擎表现更友好；在每个设备中都能得到较好的设计
- 缺点：在老版本的浏览器兼容性不好；兼容各种设备工作量大，效率较低；加载更多的样式和脚本文件；设计比较难于精确定位和控制；是一种折中性质的设计方案，在一定程度上改变网页布局结构，会出现用户混淆情况；维护困难

# 什么是响应式设计？
- 响应式布局、响应式开发
- 解决移动互联网实现不同屏幕分辨率下网页的不同的展示效果，不需要为每个终端定制特性的版本
- 包含：弹性布局、图片、css media query等
- 页面设计与开发，需要根据用户行为、设备环境进行相应的调整
- 通过媒体查询检测不同的设备尺寸，通常在页面头部添加meta标签声明viewport

# 响应式设计技术要点
## 1、标签的设置
- meta标签设置
    - 虚拟窗口：创建虚拟窗口，自定义窗口大小和缩放功能，适应移动端设备的屏幕大小
    - 使用高版本的IE内核浏览器或chrome
    ```
    <meta http-equiv="X-UA-Compatible" content="ie=edge,chrome=1">
    ```
    - 针对手持设备优化，一些老的不识别viewport的浏览器
    ```
    <meta name="HandHeldFriendly" content="true">
    ```
- IE8- 不支持媒体查询，使用media-queries.js或respond.js增加IE对媒体查询的支持
    ```
    <script src="https://cdn.bootcdn.net/ajax/libs/livingston-css3-mediaqueries-js/1.0.0/css3-mediaqueries.min.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/respond.js/1.4.2/respond.min.js"></script>
    ```
## 2、使用媒体查询适配对应的样式
- 媒体查询常见的媒体尺寸设置——断点

| 屏幕| 设备 | 断点|
|-----|------|-----|
| 超小屏幕|手机|<768px|
|小屏幕|平板| >=768px~<992px|
|中等屏幕|桌面|>=992px~<1200px|
|大屏幕|桌面|>=1200px|
    常用媒体查询尺寸
        1200px
        1100px 1024px 1000px
        980px
        768px  720px
        640px
        480px
        320px
- 移动设备优先：超小设备  手机  768px以下
    @media screen and (min-width: 768px){ 小屏幕 }
    @media screen and (min-width: 992px){ 中等屏幕 }
    @media screen and (min-width: 1200px){ 大屏幕 }
- 大屏幕优先：大屏幕  桌面  1200px及以上
    @media screen and (max-width: 1199px){ 中等屏幕 }
    @media screen and (max-width: 991px){ 小屏幕}
    @media screen and (max-width: 767px){ 超小屏幕}
## 3、响应式内容设置
- 字体设置
    css3 rem 
    html{ font-size: 100%;}
    @media all and (max-width: 1199px){
        html{ font-size: ;}
    }
    px
- 百分比布局
    - 宽度使用百分比，内填充、margin、border
    - 布局：浮动、定位、弹性盒子
    - 图片
        - 前景图：max-width属性控制图片大小，height: auto
        - 背景图：background-size属性

# 媒体查询
## 1、媒体查询
- 可以根据设备显示器的特性，设置不同的css样式
- css2 允许设计者根据不同的媒体类型定义不同的css样式
- css3 可以针对设备特性在不改变页面内容情况下，为特定输出设备定制显示效果
- 媒体查询可以检测的内容：viewport宽度和高度、设备的宽度和高度、设备的朝向、分辨率
## 2、引入方式
### 1）在样式表中引入——在style标签对引入、在外部的css文件中添加媒体查询并通过link标签引入
```
@media mediaType  and     (media feature){
    选择器{ 属性: 属性值; }
}
```
- mediaType设备类型：
    - all 所有多媒体设备
    - print 打印机或打印预览
    - screen 电脑屏幕、平板电脑、智能手机等
    - speech 屏幕阅读器等发声设备
- media feature 媒体特性表达式
    - width 浏览器宽度   height浏览器高度
    - max-width 最大宽度  min-width 最小宽度
    - device-width 设备宽   device-height 设备高
    - max-device-width 最大设备宽  min-device-width 最小设备宽
    - max-device-height 最大设备高
    - orientation 浏览器朝向(landscape横屏、portrait纵屏)
    - aspect-ratio:1/2 可视区宽度和高度的比率（max、min)
    - device-aspect-ratio:1/2输出设备的屏幕可视区的宽度和高度的比率
### 2）通过link标签引入——media属性
```
<link rel="stylesheet" media="mediaType and (media Feature)" href="css文件路径" >
```
```
<link rel="stylesheet" href="css/media2-1.css" media="all and (max-width: 1000px)">
```
- 如何让img标签在div中上下居中
- 如何居中一个浮动元素
- 
- 文字水平、垂直方向上重叠