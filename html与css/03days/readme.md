# 选择器——基础选择器
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
## 3、class选择器
- 类选择器
- 语法
```
结构中：<标签名 class="类名"></标签名>
    <标签名 class="类名1 类名2"></标签名>
样式中：.类名{ 声明语句 }
        .类名1{ }
        .类名2{ }
```
> 多个标签可以使用同一个class名称
> 一个标签可以有多个class名称，多个名称之间用空格隔开（词列表），写在一个class属性中

## 4、id选择器
- 语法
```
结构中：<标签名 id="id名称"></标签名>
样式中：#id名称{ 声明语句 }
```
> id名称在本页面中只能出现一次
## 选择器的命名规范
- 名称要有含义
- 名称建议以英文字母开头，包含英文字母、数字、-、_
- 除了-和_之外的特殊字符不允许使用（空格等）
- 不能使用中文汉字、纯数字，不能以数字开头
- 类名区分大小写
## 基础选择器的优先级
- 选择器的权值越大，优先级越高
- 基础选择器的权值分别为：通配符选择器（0）、标签选择器（1）、class选择器（10）、id选择器（100）、行间样式（1000）
- 选择器的权值相同时，后写的会覆盖前面写的内容

# 文本文字属性
- photoshop：窗口菜单--字符，打开字符面板
- Photoshop：编辑菜单--首选项--单位与标尺，打开的窗口中修改单位（文字单位、标尺单位）为像素，单击确定
## 1、文字属性
- font-size属性：字号，属性值单位像素px
    浏览器默认字号为16像素
- font-family属性：字体
    - 如果字体名称为中文或字体中包含空格，字体名称必须加引号
    - 可以把多个字体名称作为一个“回退”系统来保存。如果浏览器不支持第一个字体，则尝试下一个字体，多个字体之间用逗号隔开
    - 中英文混排的段落文字，英文字体要放在前面
    - Arial  微软雅黑    Times New Roman  宋体
- font-weight属性：文字加粗
    为字体指定了9级加粗度，范围100~900之间
    - font-weight: normal; 正常，默认值（相当于400）
    - font-weight: bold; 加粗（相当于700）
    - font-weight: 900;
- font-style属性：字体样式
    - font-style: normal; 正常，默认值
    - font-style: italic; 斜体
- line-height属性：文字行高
    - 文字在行高范围内垂直居中
    Photoshop中：视图菜单--标尺
    参考线：在标尺上按住鼠标左键不松手，拖拽鼠标
    按住alt键，滚动滚轮实现放大|缩小
    选框工具：m
    - 行高撑不起盒高
    - 如果行高的属性值没有单位，表示字号的倍数
- font属性
    font: [font-style] [font-weight] font-size[/line-height] font-family;
> 只有同时具有font-size属性和font-family属性值时，简写有效
## 2、文本属性
- color属性 文字颜色
    - 关键词：transparent透明色、red、green、blue
    - 十六进制色值：由0-9 a-f的六位十六进制数组成
        #ff0000--#f00   #334545  #334555  #334455--#345
        photoshop：英文状态下，i键，右键点击--拷贝颜色的十六进制代码--在代码中ctrl+v粘贴
    - rgb颜色模式： r-red红色，g-green绿色，b-blue蓝色，取值范围0-255之间
        rgb(r,g,b)   rgb(255,0,0)
    - rgba颜色模式：r-red红色，g-green绿色，b-blue蓝色，取值范围0-255之间；a-alpha透明度，0(完全透明)  1（完全不透明）  0~1之间表示半透明效果
        rgba(r,g,b,a)
- text-align属性：文本（图片）水平对齐方式，该属性设置给块级元素
    - text-align: left; 左对齐，默认值
    - text-align: center; 居中对齐
    - text-align: right; 右对齐
    - text-align: justify; 两端对齐
- text-decoration属性：文本装饰线
    - text-decoration: none; 去掉文本装饰线
    - text-decoration: underline; 下划线
    - text-decoration: overline; 上划线
    - text-decoration: line-through; 删除线  <del></del>
> 文本装饰线的颜色默认为前景色（color颜色相关）
- text-indent属性：文本块首行缩进，属性值的单位px、em(字符宽度的倍数)、百分比（相对于父元素的宽度）
    ```
    text-indent: 100px;/* 向右缩进 */
    text-indent: -100px;/* 向左缩进 */
    ```
- text-transform属性：字母大小写转换
    - text-transform: capitalize; 首字母大写
    - text-transform: uppercase; 全大写
    - text-transform: lowercase; 全小写

- letter-spacing属性：字间距
- word-spacing属性：词间距

# css长度单位
## 1、px 像素
- 相对于显示器的屏幕分辨率
- 值是固定
- 计算比较容器
## 2、em
- 相对长度单位，相对于父元素的font-size属性值而言
- 值不固定
- 浏览器默认字号16像素，未经调整的浏览器符合：1em = 16px
## 3、rem
- 相对长度单位，相对于根元素的font-size属性值而言
- 值不固定
- 浏览器默认字号16像素，未经调整的浏览器符合：1rem = 16px
> 是css3新增单位，IE8及更早版本的浏览器中不兼容
## 4、%
- 相对长度单位

# 盒模型Box Model
## 1、什么是盒子模型？
- 框模型，在页面布局中，将页面元素合理、有效地组织在一起，形成一套完整的、行之有效的规则、规范
- 包含：元素内容content、内填充padding、边框border、外间距margin几个要素
- 标准盒模型的计算公式：
    
## 2、盒模型相关属性
- 元素内容相关属性
    - width属性：元素的宽度
    - height属性：元素的高度
        - 属性值：auto(默认值)、数值(单位px|em|rem|%——相对于父元素的宽度和高度)、inherit
    - max-width属性：最大宽度   min-width属性：最小宽度
    - max-height属性：最大高    min-height属性：最小高
- 内填充——padding属性
定义元素边框和元素内容之间的区域
    - 单边内填充
        - padding-top属性 上内填充
        - padding-bottom属性 下内填充
        - padding-left属性 左内填充
        - padding-right属性  右内填充
    - 复合写法
        - padding: npx;
        - padding: npx mpx;
        - padding: npx mpx xpx;
        - padding: npx mpx xpx ypx;
    ```
    padding: 10px;/* 元素的上、右、下、左各有10像素的内填充 */
    padding: 10px 20px;/* 元素的上、下各有10像素，左、右各有20像素内填充 */
    padding: 10px 20px 30px;/* 元素的上10像素，左右各有20像素，下30px的内填充 */
    padding: 10px 20px 30px 40px;/* 元素的上10px、右20px、下30px、左40像素的内填充 */
    ````
    > 上下内填充和左右内填充百分数值是相对于父元素的width属性计算
- 边框——border属性
围绕着内容和内填充的线
    - 边框属性
        - border-width属性：边框的宽度，单位像素
        - border-style属性：边框的线型
            - border-style: solid; 单实线
            - border-style: double; 双实线
            - border-style: dotted; 点状虚线
            - border-style: dashed; 条状虚线
            - border-style: none; 没有边框
        - border-color属性：边框颜色
            如果没有设置边框颜色，默认于文本颜色一致
    - 复合写法
        - border-width: npx;
            border-width: npx mpx;
            border-width: npx mpx xpx;
            border-width: npx mpx xpx ypx;
        - border-style
        - border-color
    - 单边属性
        - border-top属性 上边框
            border-top: border-top-width border-top-style border-top-color;
            border-top: 5px solid red;
        - border-bottom属性
        - border-left属性
        - border-right属性
    - border简写
        border: border-width border-style border-color; 
    - 去掉边框
        - border: 0;
        - border: none;
    - 使用——实现向下三角
    ```
    .box4{
        width: 0;
        height: 0;
        font-size: 0;
        line-height: 0;

        border-top: 100px solid red;
        border-left: 100px solid transparent;
        border-right: 100px solid transparent;
    }
    ```
- 外间距——margin
两个盒子之间的距离，盒外属性
    - 单边外间距
        - margin-top属性 上外间距
        - margin-bottom属性
        - margin-left属性
        - margin-right属性
    > margin值可以设置负值，较少元素的占位。如margin-top: -50px; 将元素在原位置的基础上，向上移动50像素，减少50像素的占位
    - 复合写法
        margin: npx;
        margin: npx mpx;
        margin: npx mpx xpx;
        margin: npx mpx xpx ypx;
    - 盒子的水平居中
        margin: 0 auto; 固定宽度且居中，必须与width属性配合使用才会有效