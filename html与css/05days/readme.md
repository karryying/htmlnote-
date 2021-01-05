# 外边距（间距）塌陷问题
## 1、并列关系的外间距的塌陷
- 现象：
    元素并列关系，垂直方向相邻的margin值相遇，会出现叠加现象——两个值相同，取当前值；两个值不同，取较大值
- 原因：
    并列关系的两个元素共用一个外间距
- 解决方案：
    - 为这两个并列关系的元素分别套一个父元素，并为父元素设置overflow:hidden;属性
    - 可以为并列关系的元素分别触发BFC
## 2、嵌套关系的外间距塌陷
- 现象：
    元素嵌套关系，子元素的margin-top属性值会叠加给父元素；如果父元素有margin-top属性值，会与子元素的margin-top属性值合并，取较大值
- 原因
    父元素和子元素共用一个上外间距区域
- 解决方案：
    - 为父元素设置上边框或上内填充
    - 为父元素设置overflow:hidden; 触发BFC，改变父元素的渲染规则
    - 转换思路，巧用padding，规避margin

# float浮动
- css的定义机制：标准流、浮动、定位
- 标准流——文档流：文档中可以显示的对象在排列时所占的位置
## 1、浮动
- 使元素脱离正常文档流，按照指定方向发生移动，直到碰到父元素的边界或另外一个浮动元素的边界为止
> 浮动让元素水平方向移动，不能上下移动
## 2、浮动属性
    - float: left; 左浮动
    - float: right; 右浮动
    - float: none; 不浮动，默认值
## 3、浮动特性
    - 元素脱离正常文档流
    - 可以提升层级（半层）
    - 使没有设置宽度的块级元素宽度由内容撑开；如果浮动元素的宽度之和大于父元素，则浮动盒会被挤到下一行显示
    - 使行级元素支持宽高
    - 浮动元素不占位，父级盒高度为零
## 4、浮动产生的问题
    元素浮动之后，脱离正常文档流，导致父元素高度塌陷，会影响与浮动元素父级盒同级的后续元素的正常布局
## 5、清浮动的方法
- 给浮动元素的父级盒设置一个固定的高度
    - 不够灵活；适用于高度固定的布局中
- 给浮动元素的父级盒设置浮动
    - 会产生新的浮动问题
- 给浮动元素的父级盒添加overflow属性，属性值可以是hidden、scroll、auto
    - 可能会导致内容显示不完全、代码简洁
- 在浮动元素之后，与浮动元素呈现并列关系的位置，加一个空div(div元素本身不浮动，没有尺寸)，在空div上加属性clear: both;
    -  代码冗余；通俗易懂，书写方便
- 推荐方式：给浮动元素的父级盒加类名.clearfix，并在.clearfix中添加样式：
    .clearfix{
        *zoom: 1;
    }
    .clearfix::after{
        content: "";
        display: block;
        clear: both;
    }
    - 不会在结构上产生冗余代码；可以重复使用；结构语义化正确

# overflow属性
内容溢出处理方式，包含水平方向和垂直方向
    - overflow: visible; 默认值，溢出显示
    - overflow: hidden;/* 溢出隐藏 */
    - overflow: auto;/* 自动，内容溢出时显示滚动条 */
    - overflow: scroll;/* 溢出显示滚动条 */
    - overflow: inherit; 从父元素继承overflow属性
- overflow-x属性：只包含水平方向的内容溢出处理方式
- overflow-y属性：只包含垂直方向的内容溢出处理方式
# clear属性
清除浮动带来的影响
    - clear: left; 清除左浮动
    - clear: right; 清除右浮动
    - clear: both; 清除两侧浮动
# 伪元素选择器
## 1、伪元素
    用css语言创造出来的标签
## 2、创建伪元素
- element::before{ content:"伪元素的文本内容"; 属性名:属性值; } 
    element元素内部，内容之前，添加"伪元素的文本内容"
- element::after{ content:"伪元素的文本内容"; 属性名:属性值; }
    element元素内部，内容之后，添加"伪元素的文本内容"

# vertical-align属性 垂直对齐方式
- 常用属性
   - vertical-align: top; 顶端对齐
   - vertical-align: bottom; 底端对齐
   - vertical-align: middle; 中部对齐
   - vertical-align: baseline; 基线对齐，默认值

   - vertical-align: super; 上标
   - vertical-align: sub;  下标
- 使用
    图片下方间隙问题、文本与图片对齐方式处理、文本输入框和按钮之间的对齐方式处理
    - 图片下方间隙问题
        - 将img标签转成块级元素
        img{ display: block; }
        - 为img标签设置垂直对齐方式
        img{ vertical-align: top|bottom|middle; }
        - 为img标签的父元素设置font-size:0;或line-height:0;
        - 为img标签的父元素设置高度，添加overflow:hidden;
    