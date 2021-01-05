# BFC
## 1、什么是BFC
    - BFC——block formatting context 块级格式化上下文，W3C css2.1规范中的概念
    - 页面中的一个渲染区域
    - web页面可视化css视觉渲染的一部分，用于决定块级盒子的布局及浮动相互影响范围的一个区域
    - 本质：一个封闭的盒子
## 2、怎样生成BFC？
    - 根元素
    - float: left|right;
    - position: absolute|fixed;
    - display: inline-block;
    - overflow: hidden|auto|scroll;
## 3、BFC的特性
    - 内部元素会在垂直方向上一个接一个放置
    - 垂直方向上的外间距由margin值决定，属于同一个BFC的两个相邻元素的margin值会重叠
    - 每个元素的左外间距和包含块的左边界相接触，浮动元素也是如此
    - BFC区域不会与浮动元素区域重叠
    - 计算BFC高度时，浮动元素也参与计算
    - BFC是页面上的一个独立的渲染区域，容器中子元素不会影响到外面的元素，反之亦然
## 4、BFC解决的问题
- 1）外间距重叠问题
- 2）清浮动
- 3）自适应两栏或三栏布局
    - 自适应两栏布局：左侧宽度固定，右侧不设宽，则右侧宽度为自适应，随浏览器窗口大小变化而变化
    - 自适应三栏布局：左右两侧宽度固定，中间不设宽，则中间宽度自适应，随浏览器窗口大小变化而变化
- 4）防止文字环绕

# css小箭头
## 1、原理
    - 使用css绘制两个三角形
    - 通过绝对定位让两个三角形不完全重叠
    - 让处于上层的三角形比处于下层的三角形偏移属性少1px，就可以生成空心箭头
## 2、兼容
    在IE6及更早版本的浏览器中添加font-size: 0; line-height: 0; 目的是为了让三角的height:0; 有效
## 3、实现
```
结构中：向下箭头
    <div class="arrowDown">
        <i class="arr"></i>
        <i></i>
    </div>
样式中：
    .arrowDown i{/* 向下的两个三角 */
        width: 0;
        height: 0;

        font-size: 0;
        line-height: 0;

        border-top: 5px solid #f5f5f5;
        border-left: 5px solid transparent;
        border-right: 5px solid transparent;

        position: absolute;
        left: 0;
        top: -1px;
    }

    .arrowDown .arr{ /*两个三角错位*/
        border-top-color:#d4d4d4;
        top: 0;
    }
```

# iconfont 字体图标
## 阿里矢量图标库
- 1、通过检索界面选择需要的图标，并添加到购物车
- 2、打开购物车--选择“下载代码”
- 3、将下载好的文件夹中的字体文件（.eot|.svg|.ttf|.woff|.woff2）放入项目的fonts文件夹下
- 4、将下载好的iconfont.css文件，放入css文件夹，并修改css文件中的字体文件路径（../fonts/iconfont.eot）
- 5、将修改好的iconfont.css文件链接到HTML文档中
- 6、在HTML文档中添加指定类名iconfont和图标的名称（&#xe63e;）或在标签中添加类名iconfont和图标对应的类名icon-XX
```
    <p class="txt1"><span class="iconfont">&#xe63e;</span></p>
    <p class="txt2"><span class="iconfont icon-sousuo"></span></p>
```
> 需要通过文字样式修改字体图标的大小和颜色

# 文本溢出处理
## 1、单行文本溢出显示省略号
- 使用的属性
    - text-overflow: clip; 文字溢出后直接被裁切
    - text-overflow: ellipsis; 文本溢出后用省略号表示被裁切的文本
    - text-overflow: string; 文本溢出后用给定的字符串表示被裁切的文本，仅在火狐中生效
- 实现
```
.box{
    width: 200px; 
    white-space: nowrap;  /*强制不换行*/
    overflow: hidden;
    text-overflow: ellipsis;/*文本溢出后用省略号表示*/
}
```
## 2、多行文本溢出显示省略号
- 使用webkit的css扩展属性——只在-webkit-内核的浏览器中有效
```
    .box2{
        width: 200px;
        overflow: hidden;
        text-overflow: ellipsis;

        display: -webkit-box;/* 将元素转换为弹性伸缩盒子 */
        -webkit-line-clamp: 2;/* 显示的文本内容的行数 */
        -webkit-box-orient: vertical;/* 设置弹性伸缩盒中子元素的排列方式 */

    }
```
- 使用伪元素模拟溢出显示省略号——兼容性较好
```
    .box3{
        position: relative;
        width: 200px;
        height: 40px;/* height是line-height属性值的倍数*/
        overflow: hidden;
        line-height: 20px;
    }
    .box3::after{/* 模拟省略号 */
        content: "...";
        position: absolute;
        right: 6px;
        bottom: 0;
        background: #fff;
        padding: 0 3px;
    }
```

# HTML表单
- 用于采集用户输入数据，发送给服务器，实现用户和服务器之间的数据交互
- 一个完整的表单通常包含表单元素、提示信息、表单域等3个部分
## 1、表单标签
- 用于申明表单，定义数据采集范围
- 一个页面中可以有多个或一个表单标签，标签之间相互独立，不能嵌套
- 用户向服务器提交数据一个只能提交一个表单中的数据；如果要提交多个表单，需要使用JavaScript中的异步交互方式
- 语法
```
<form action="提交表单时向何处发送表单数据URL" method="get|post" name="表单名称">表单控件</form>
```
- 属性
    - method属性：提交表单使用的HTTP方法；默认get方式
        - get方式：将数据作为URL地址的一部分发送服务器；安全性较低；请求数据可以被缓存，能保留在浏览器的历史记录中，可以作为书签被收藏；有长度限制。
        https://www.baidu.com/?username1=123&username2=ABC
        https://www.baidu.com/?参数名1=参数值1&参数名2=参数值2
        - post方式：将数据隐藏在HTTP数据流中进行传输；安全性比get方式高；请求数据不会被缓存，不能保留在浏览器的历史记录中，不会作为书签被收藏；对数据没有长度限制
    - name属性
        如果表单元素中不设置name属性，输入框中的内容无法随表单一起提交到后台
## 2、表单控件
- input标签
```
<input type="" name="" value="" />
    type属性：用来设置不同的控件类型
```
-
    - 单行文本输入框
    ```
    <input type="text" name="" value="" placeholder="提示信息文本">
    ```
    - 密码框（默认掩码处理）
    ```
    <input type="password" name="" placeholder="提示信息文本">
    ```

    - 按钮——提交按钮
    ```
    <input type="submit" value="">
    ```

    > value属性：用于修改按钮上的文字