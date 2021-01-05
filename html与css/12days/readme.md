# css3基础
## 1、css3简介
### 1）什么是CSS3？
- 是css的升级版本，在css2的基础上，新增了一些新特性，弥补css2的不足，让web页面开发变得更加高效、便捷
- css3按照模块进行设计，比较重要的模块：
    选择器、框模型、背景和边框、文本效果、2D|3D转换、动画、多列布局、用户界面
- css3现状：
    - 部分属性在浏览器中需要添加兼容性前缀
    - 移动端支持优于PC端
    - 不断更新中
    - 应用相对广泛
- css3向后兼容
- css2和css3的区别
    - css3能使代码更加简介、页面结构更加清晰、合理，性能和效果得到兼顾；css2要请求服务器的次数要高于css3，性能和访问相对于css3要差
    - css3能实现动画效果；css2更加偏向于表现
    - css3数据更加精简使用，许多在css2中需要使用图片实现的效果，在css3中可以通过代码实现
    - 兼容性问题，css2中所有的属性都能在浏览器中呈现；css3中部分属性在主流浏览器的最新版本中仍然需要添加兼容性前缀
### 2）渐进增强和优雅降级
- 渐进增强：针对低版本浏览器进行页面构建，保证最基本的功能，然后再最对高版本的浏览器进行交互、效果之类的改进，追加一些功能，达到更高的用户体验——普通到华丽

- 优雅降级：一开始构建一个完整的功能，然后再针对低版本浏览器进行兼容——华丽到普通
### 区别
    - 渐进增强：从基础到复杂，并能适应未来的环境
    - 优雅降级：从复杂到基础，减少用户体验
## 2、兼容性前缀
- 浏览器生产商对新属性或规则的提前支持，暗示这个属性或规则没有成为W3C标准的一般部分
- 书写规则：先写私有css属性或规则，最后写标准css属性
- 浏览器、内核、私有前缀（兼容性前缀）
    |浏览器|内核|私有前缀|
    |------|----|------|
    |chrome、safari|webkit| -webkit-|
    |opera|Presto|-o-|
    |firefox|Gecko|-moz|
    |IE|Trident|-ms-|
- 当一个属性或规则成为标准，并被主流浏览器的最新版本普遍兼容的时候，可以去掉兼容性前缀
- autofix
    - 在VScode中安装autoprefixer插件
    - 在外部的css文件中书写相关的属性和属性值
    - 按下F1，选择autoprefixer:run,之后会在css文件中添加|删除私有前缀
## 3、选择器
### 1）属性选择器
- css2中属性选择器
    - element[attr]{ } 指定了属性名，但是没有指定属性值的element元素
    - element[attr=value]{ } 指定了属性名，并且指定属性值的element元素
    - element[attr~=value]{ } 指定了属性名，属性值可以是词列表，在词列表中包含指定value值的element元素
- css3中新增的属性选择器
    - element[attr^=value]{ } 指定了属性名attr,并且属性值为value开头的element元素
    - element[attr$=value]{ } 指定了属性名attr,并且属性值为value结尾的element元素
    - element[attr*=value]{ } 指定了属性名attr,并且属性值包含value的element元素
### 2)结构伪类选择器
- :root{} 匹配根元素

- ele:first-child{ } 选择一组相同元素中的第一个元素——css2
- ele:last-child{ } 选择一组相同元素中的最后一个元素
- ele:nth-child(n){ } 选择一组相同元素中的第n个元素。n取值可以是数值、关键词、表达式
    - 数值
    - 关键词：odd奇数  even偶数
    - 表达式：2n+1奇数   2n表示偶数
- ele:nth-last-child(n){ } 选择一组相同元素中的倒数第n个元素。n取值可以是数值、关键词、表达式

- ele:nth-of-type(n){ } 选择一组元素中特定类型的第n个ele元素。n取值可以是数值、关键词、表达式
- ele:nth-last-of-type(n){ } 选择一组元素中特定类型的倒数第n个ele元素。n取值可以是数值、关键词、表达式

### 3)状态伪类选择器
- ele:checked{ } 选择处于选中状态的ele元素
- ele:disabled{ } 选择处于禁用状态的ele元素
- ele:enabled{ } 选择处于可用状态的ele元素

## 4、背景
### 1）多背景
```
background-image:url(图片路径), url(图片路径);
```
- 多个背景图片之间用逗号隔开
- 显示越靠前，书写顺序越靠前
### 2）背景图片尺寸设置
- background-size属性：数值
    - background-size: 300px;/* 按照宽度300像素，高度自适应 */
    - background-size: 200px 100px;/* 按照给定的尺寸设置背景图片大小 */
    - background-size: 100% 100%;/* 背景图片撑满整个盒子 */
- background-size属性：关键词
    - background-size: cover;覆盖，等比例缩放背景图片到铺满整个盒子，但是背景图片可能会无法完整的显示在盒子中
    - background-size: contain;包含，等比例缩放背景图片到完整显示在盒子中，但是背景图片可能在区域内铺不满
```
background:url(images/3.jpg) no-repeat;
background-size: cover;
简写：
background: url(images/3.jpg) no-repeat left top/cover;
```
### 3）背景图片定位区域——backgorund-origin属性
    - background-origin: content-box; 背景图片相对于内容区域来定位
    - background-origin: padding-box; 默认值，背景图片相对内填充区域来定位
    - background-origin: border-box; 背景图片相对于边框区域来定位
### 4）背景颜色绘制区域——background-clip属性
    - background-clip: content-box; 背景颜色仅在内容区域显示
    - background-clip: padding-box;背景颜色在padding区域和内容区域显示
    - background-clip: border-box; 默认值，背景颜色在padding区域、内容区域、border区域显示

## 5、渐变
从一种颜色到另外一种颜色的过渡（两种及以上）
### 1）线性渐变 linear-gradient
- 语法
```
background-image: linear-gradient(方向, 颜色1 范围1, 颜色2 范围2, 颜色3 范围3, ...);
    方向：数值（单位deg角度）、关键词（left|right top|bottom）
    颜色：关键词、十六进制色织、rgb()、rgba()
    范围：每个颜色结点显示的范围
```
- 重复线性渐变
```
background-image: repeating-linear-gradient(方向, 颜色1 范围1, 颜色2 范围2, 颜色3 范围3, ...);
background-image: -webkit-repeating-linear-gradient(方向, 颜色1 范围1, 颜色2 范围2, 颜色3 范围3, ...);
```
### 2）径向渐变 radial-gradient
- 语法
```
background-image: radial-gradient(中心位置，渐变形状，颜色1 范围1, 颜色2 范围2, ...);
    中心位置： left|center|right   top|center|bottom 
    渐变形状：椭圆(默认值 ellipse)、圆形（circle）
```
- 重复径向渐变
```
background-image: repeating-radial-gradient(中心位置，渐变形状，颜色1 范围1, 颜色2 范围2, ...);
```
> 如果不设置径向渐变的中心位置，默认位置为center

## 6、用户界面
### 1）resize属性：用户是否可以对元素尺寸进行调整
- resize:none; 不允许用户手动调整元素的尺寸
- resize:both; 用户可以手动调整元素的宽度和高度
- resize: vertical; 用户可以手动调整元素的高度
- resize: horizontal; 用户可以手动调整元素的宽度
> resize属性要生效，必须与overflow属性配合使用，属性值可以是hidden|auto|scroll
### 2) box-sizing属性
- box-sizing: content-box;默认值，在width属性和height属性之外绘制元素的内填充和边框
- box-sizing: border-box; 通过已有的设置好的width属性和height属性中分别减去内填充和边框，得到内容的宽度和高度

## 7、多列布局
- 元素被分割的列数——column-count属性
    - column-count：n; 被划分为n列，没有单位
    - column-count: auto; 由其他属性决定列数
- 列宽——column-width属性
    - column-width: npx; 每一列宽度设置
    - column-width: auto; 由其他属性决定列宽

- 列间距——column-gap属性
    - column-gap: npx; 两列之间的间隔
    - column-gap: normal; 两列之间为常规间隔，W3C建议1em
- 列间分割线——column-rule属性
    - column-rule: column-rule-width column-rule-style column-rule-color;
    > border、outline
- 跨列合并——column-span属性
    - column-span: all; 横跨所有列合并