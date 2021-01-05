# 弹性盒子
## 1、什么是弹性盒子？
- 弹性盒子   弹性布局、flex布局
- 传统布局
    - 兼容性好
    - 布局繁琐
    - 局限性，不会在移动端布局中有较好的呈现
    - PC端页面中更多的使用传统布局
- flex布局
    - css3新增布局方式——一种当页面需要使用不同屏幕大小、不同设备类型时，能够保证元素拥有恰当的布局方式
    - 操作方便，布局简单，移动端使用广泛
    - PC端浏览器支持情况较差
    - IE11及更低版本的浏览器中，不支持或部分支持
    - 在盒模型中较为灵活
- 弹性盒模型的内容包含：弹性容器、弹性子元素（项目）
- 引入弹性盒模型的目的：用一种更加有效的方法对容器中的子元素进行排列、对齐、分配空白空间，即使是弹性子元素的尺寸发生改变，弹性盒模型也可以正常工作
- 原理：为父元素设置flex属性，控制子元素的位置及排列方式
## 2、设置弹性盒子——display属性
- display: flex; 将块级元素设置为弹性盒
- display: inline-flex; 将盒子设置为弹性盒
> 为父元素设置flex属性，子元素中的float、clear、vertical-align属性都会失效
## 3、基本概念
- flex容器    项目——弹性子元素
- 默认在容器中有两根轴线
    - 默认主轴方向——水平方向，水平向右（左侧为主轴的起点，右侧主轴的终点）
    - 默认交叉轴方向——垂直方向，垂直向下（上方是交叉轴的起点，下方是交叉轴终点）
## 4、容器属性——添加在弹性容器上
- flex-direction属性：设置主轴的方向，子元素的排列方向
    - flex-direction: row; 默认值，主轴方向为水平方向，起点在左侧，排列次序与文档顺序一致
    - flex-direction: row-reverse; 主轴方向为水平方向，排列次序与文档顺序相反
    - flex-direciton: column; 主轴方向为垂直方向，起点在上方，排列次序与文档顺序一致
    - flex-direction: column-reverse; 主轴方向为垂直方向，排列次序与文档顺序相反
- justify-content属性：弹性子元素在主轴方向上的对齐方式
    - justify-content: flex-start; 默认值，子元素位于弹性容器的开头
    -justify-content: flex-end; 子元素位于弹性容器的结尾
    -justify-content: center; 子元素位于弹性容器的中间
    - justify-content: space-between; 子元素和子元素之间有空白空间
    - justify-content: space-around; 子元素之前、之间、之后都留有空白空间
- align-items属性：弹性子元素在交叉轴方向上的对齐方式
    - align-items: stretch; 默认值，如果弹性子元素没有高度或高度为auto，将占满整个容器的高度
    - align-items: flex-start; 子元素位于交叉轴的起点
    - align-items: flex-end; 子元素位于交叉轴的终点
    - align-items: center; 子元素位于交叉轴的中间
    - align-items: baseline; 子元素在第一行文字的基线对齐
- flex-wrap属性：弹性子元素在一根轴线上放不下时的换行方式
    - flex-wrap: nowrap; 默认值，不换行
    - flex-wrap: wrap; 换行，第一行在上方显示
    - flex-wrap: wrap-reverse; 换行，第一行在下方显示
- align-content属性：多根轴线的对齐方式，如果只有一根轴线，属性失效
    - align-content: flex-start; 与交叉轴的起点对齐
    - align-content:flex-end; 与交叉轴的终点对齐
    - align-content:center; 与交叉轴的中间对齐
    - align-content:space-between; 轴线之间的间距
    - align-content:space-around; 轴线两侧都有间距
    - align-content: stretch; 默认值，轴线占满整个交叉轴
## 5、项目属性——写在弹性子元素上
-  order属性：子元素的排列次序
    - 属性值：数值，没有单位，默认数值为0
    - 数值越小，排列越靠前
- flex-grow属性：子元素的放大比例
    - 属性值：数值，没有单位
    - 默认值为0，表示不放大
- flex-shrink属性：子元素的缩小比例
    - 属性值：数值，没有单位
    - 默认值为1，表示当空间不足时，等比例缩小
    - 属性值为0，表示当空间不足，不缩小
- flex属性：
    - flex-grow,属性值为0，不放大，flex-shrink属性值为0 不缩小
    - flex: flex-grow flex-shrink;
- align-self属性：弹性容器中，被选中的弹性子元素的对齐方式
    - align-self: auto; 默认值，元素继承了父容器的align-items属性，如果父容器没有设置则属性值为stretch
    - align-self: stretch; 占满整个容器的高度
    - align-self: flex-start; 交叉轴的起点对齐
    - align-self: flex-end; 交叉轴的终点对齐
    - align-self: center; 交叉轴的中点对齐
    - align-self: baseline; 子元素的第一行文字的基线对齐
# 预处理
## 1、预处理
- 一种新的语言
- 基本思想：用一种专门的编程语言，为css增加一些变成特性，将css文件作为目标生成文件，然后程序员使用预处理语言进行编码工作
## 2、Less
- 包含一套自定义的语法及一个解析器，用户根据语法定义自己的样式规则，这些规则最终通过解析器编译生成对应css文件，只有被编译后的文件才能被浏览器识别
- 扩展css语言，增加了一些新的功能，如：定义变量、混合、函数、运算等
- 好处：
    结构清晰，便于扩展；可以方便地屏蔽浏览器私有语法差异；可以实现多重继承；完全兼容css代码，可以方便地应用到老项目中
## 3、预处理编译工具Koala
## 4、less基本语法
### 1）新建less文件
    - 新建后缀名为.less的文件
    - 新建一个后缀名为.less的文件，并保存在css文件夹下；打开Koala，将项目文件夹拖入目录列表中；右击——设置输出路径，选择正确的输出路径，输入文件名.css，单击确定；执行编译；在HTML文档中将编译好的css文件通过link标签链入
### 2）注释
    - //单行注释，只在less源文件中保留，编译后被省略
    - /* 标准css注释，会保留在编译后的文件中 */
### 3）import导入样式
    可以导入css文件、less文件
    @import必须写在样式表的头部，后面必须添加分号
- 语法：
```
@import  "*.css";
@import  url("*.css");
@import  url(*.css);
```
- link和@import的区别：
    - link是HTML标签；@import是css定义的，只能加载样式文件
    - link在页面载入时同时载入；@import在页面加载完成后载入
    - link没有兼容问题；@import在css2.1以下浏览器中不支持
    - link支持使用JavaScript修改样式；@import不支持JavaScript改变样式
### 4）变量
    在全局样式中可以使用
- 定义语法：
```
@变量名: 值;

@col: red;
@wi: width;
@bo: box;
```
- 使用变量
    - 作为属性值
    ```
    .box{ color: @col; }
    ```
    - 作为属性名
    ```
    .box{ @{wi}: 200px; }
    ```
    - 作为选择器名称
    ```
    .@{bo}{ @{wi}: 300px; }
    ```
### 5）混入
    将一种或一系列的属性从一个规则集引入到另一个规则集
- 混入类名：
    - 定义通用属性：
    ```
    .fo{ color: blue; } 在解析后的css文件中可以看到
    .fo2(){ font-size: 30px; } 在解析后的css文件中看不到
    ```
    - 调用定义好的类：
    ```
    .box2{ .fo; }
    ```
- 混入参数
    - 混入参数没有设置默认值，调用的时候必须传入参数
    ```
    .fo3(@radius){ border-radius: @radius; }
    .box{ .fo3(20px);}
    ```
    - 混入参数并设置了默认值，调用时如果不传入参数，使用默认参数设置；如果传入参数，使用传入参数显示
    ```
    .fo4(@bol:bold){ font-weight: @bol;}
    .box{ .fo4; .fo4(400);  }
    ```
- 使用@arguments 来引用所有传入参数
```
    .bor(@bw,@bs,@bc){ border: @arguments; }
    .box{ .bor(10px, solid,#000)}

    .bor2((@bwi:5px, @bst: solid,@bcl:red){ border: @arguments; }
    .box{
        .bor2;
        .bor2(10px);
        .bor2(10px,dotted);
        .bor2(10px,dotted, #f0f);
    }
```

### 6）嵌套
- 模仿HTML结构——选择器嵌套
- 在嵌套代码中，可以使用&表示引用父元素
### 7）继承
    extend伪类实现样式的继承
    ```
    .fontSt{ font-size: 30px; }
    .box{
        p{
            &:extend(.fontSt);
        }
    }
    .txt:extend(.fontSt){
        font-style: italic; 
    }
    ```
### 8）运算
    数值、变量、颜色都可以运算
- 数值运算
    运算符前后用空格隔开；不需要为每个值都加单位
- 颜色运算
    将颜色色值转为rgb颜色模式，运算，再转回十六进制色值并返回
- 在calc函数中运算
```
width: calc(~"100% - 20px");
```

# 盒子的绝对居中
- marign负间距实现有width属性和height属性的绝对定位元素的居中
- margin:auto; 实现有width属性和height属性的绝对定位元素的居中
- transform: translate();实现绝对定位元素的居中
- 使用弹性布局实现元素的居中