# 背景
应用于内容、padding、border区域
## 1、背景颜色属性——background-color
- 关键词 transparent透明色 默认背景颜色   red
- 十六进制色值：#+六位十六进制数
- rgb(r,g,b)
- rgba(r,g,b,a)
> 作用于内容、padding、border区域
## 2、背景图片属性——background-image
- 语法
```
background-image: url(图片地址);
background-image: none; 没有背景图片，默认值
```
- 特征
    - 背景图不占位
    - 默认背景图在水平方向和垂直方向重复平铺，并且铺满整个内容区域
    - 背景图是网页的装饰，起美化页面的作用
    - 背景图不会被搜索引擎检索到
    - 写在样式中
## 3、背景图是否重复属性——background-repeat
    - background-repeat: repeat; 默认值，沿着水平方向和垂直方向重复
    - background-repeat: repeat-x; 沿着水平方向重复
    - background-repeat: repeat-y; 沿着垂直方向重复
    - background-repeat: no-repeat; 不重复
## 4、背景图的位置属性——background-position
- 语法
```
background-position: x y;
    x——沿着水平方向移动
    y——沿着垂直方向移动
```
- 属性值
    - 关键词：left|center|right  top|center|bottom
    - 数值：px 水平方向，向右为正；垂直方向，向下为正
    - 百分比：左上角0% 0%   右下角100% 100%
    > 如果只有一个关键词，则另一个关键词默认为center
    > 如果只有一个数值表示水平方向，则另一个数值默认为50%（垂直方向）
## 5、简写属性——background
- 语法
```
background: background-color background-image background-repeat background-position;
background: 背景颜色 背景图片 背景图重复 背景图位置;
```
# 选择器
## 1、后代选择器——选择器之间用空格隔开
```
祖辈选择器  后辈选择器{ }
    祖辈选择器范围内的所有的后辈选择器都有效
```

## 2、子代选择器——选择器之间用>隔开
```
父选择器>子选择器{ }
    父选择器范围内的所有的第一级子选择器有效，孙子元素无效
```
## 3、群组选择器——选择器之间用逗号隔开
- 分组选择器，当样式表中有具有相同样式的元素
```
选择器1,选择器2{ }
    选择器1和选择器2都具有相同的样式
```
## 4、交集选择器
由两个及以上选择器组成
```
结构中：<div class="box"></div>
样式中：div.box{ }
```
## 5、伪类链接选择器
用于添加特殊效果
- 语法
```
    选择器:伪类{ }
```
- 用于设置链接不同状态
```
    a:link{ 链接的默认状态 }
    a:visited{ 链接访问过后的样式 }
    a:hover{ 鼠标悬停时的样式 }
    a:active{ 鼠标按下时的样式 }
```
> 四个伪类状态都有效：L-v-H-a
- :hover 不仅可以用于链接的悬停，而且可以用于其他标签
```
 /* 鼠标悬停到.box盒子上，让.box盒子背景颜色变为绿色 */
    .box:hover{
        background: lightgreen;
    }
/* 鼠标悬停到.box2盒子上，让.box2中的子盒p背景颜色变为red */
    .box2:hover p{
        background: red;
    }
```

# css三大特性
## 1、层叠性
- 浏览器处理样式冲突的一种能力
- 多种css样式   不同的选择器   作用在同一个元素上
    - 样式不冲突：样式叠加，并同时作用在元素上
    - 样式冲突：存在优先级问题，优先级高的显示；不存在优先级问题，后写的会把先写的覆盖掉
## 2、继承性
- 子元素继承父元素的样式
- 不是所有的属性都能被继承（width、height、background-color、margin、border、padding、text-decoration）
- 可以被继承的属性（目前）
    - 字体系列属性
        font-size属性、font-family属性、font-weight属性、font-style属性、line-height属性、font属性
    - 文本系列属性
        text-align属性、text-indent属性、color属性、letter-spacing属性、word-spacing属性
    - list-style属性
> a标签的文字颜色需要选中a标签之后单独设置才能修改
## 3、优先级
- 样式引入方式优先级
    行间样式优于内部和外部样式；内部样式和外部样式就近原则
- 选择器优先级
    - 选择器优先级与权值相关
    - 基础选择器的权值：通配符选择器（0）、标签选择器（1）、class选择器（10）、id选择器（100）
    复合选择器的权值是所有的单一选择器权值的累加
    - 权值越大，优先级越高；权值相同，后写的会覆盖先写的
    - 继承样式的优先级为0，子元素设置样式会覆盖继承样式
    - 行间样式权值为1000，优于id选择器
    - !important优于行间样式
    ```
    div{
        background: orange !important;
    }
    ```
> 伪类选择器、属性选择器（10）
> 伪元素选择器（1）

# 标签分类与转换
## 1、标签分类及特征
### 1）块级标记 block level
- 特征：
    - 宽度默认撑满整个父元素
    - 高度默认由内容撑开
    - 默认独立成行——垂直布局
    - 具有盒模型特征——默认可以设置宽度、高度、padding、border、margin
- 常用块级标记
    div、h1、h2、h3、h4、h5、h6、p、ul、ol、li、dl、dt、dd等
### 2）行级标记 inline level——内联
- 特征：
    - 宽度默认由内容撑开
    - 高度默认由内容撑开
    - 默认横向显示——水平布局，相邻的行级标记会在同一行显示，直到一行排不下折行
    - 换行和空格会被解析
    - 具有部分盒模型特征——默认没有width、height属性，边框保留，可以设置padding-left、padding-right、margin-left、margin-right
- 常用行级标记
    span、b、strong、i、em、sup、sub、del、a等
### 3）行块级标记 inline-block
- 特征
    - 具有行级标记的特征：默认横向显示——水平布局，相邻的行级标记会在同一行显示，直到一行排不下折行；换行和空格会被解析
    - 具有块级标记的特征：具有盒模型特征
- 常用行块级标记
    img
## 2、标签类型转换——display属性
    - display: block; 转为块级标记
    - display: inline; 转为行级标记
    - display: inline-block; 转为行块级标记
    - display: none; 隐藏元素，隐藏之后不占位