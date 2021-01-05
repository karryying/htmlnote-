# HTML表单
- 用于采集用户输入数据，发送给服务器，实现用户和服务器之间的数据交互
- 一个完整的表单通常包含表单元素、提示信息、表单域等3个部分
## 1、表单标签——form标签
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
## 2、表单控件——input标签、button标签、select标签、option标签、textarea标签、label标签
### 1）input标签
```
<input type="" name="" value="" />
    type属性：用来设置不同的控件类型
```
- 单行文本输入框
```
<input type="text" name="" value="初始值" placeholder="提示信息文本">
```
- 密码框（默认掩码处理）
    ```
    <input type="password" name="" placeholder="提示信息文本">
    ```

- 按钮——提交按钮
    ```
    <input type="submit" value="按钮上的文字">
    ```
- 按钮——重置按钮
    ```
    <input type="reset" value="按钮上的文字">
    ```
- 按钮——普通按钮
    ```
    <input type="button" value="按钮上的文字">
    ```
    > value属性：用于修改按钮上的文字

- 单选按钮
```
    <input type="radio" name="" value="">
    name属性：可以实现单选按钮的互斥效果
    value属性：表示选项代表的值
```
- 复选框
```
    <input type="checkbox" name="" value="">
    name属性：实现多个选项保存在同一个字段中
    value属性：表示选项代表的值
```
> checked属性：用于单选按钮和复选框的默认选中，可以直接在input标签中写checked或checked="checked"

- 上传文件
    ``<input type="file">``
    > 要实现文件上传，在form标签中添加enctype属性
    ``<form action="#" enctype="multipart/form-data"></form>``
    > 不能设置value属性
- 图片形式的按钮
    ```
    <input type="image" src="图片路径" alt="替换文本" width="" height="">
    ```
    > input必须与src属性、alt属性配合使用；一般不建议使用
- 隐藏域
    对用户不可见，目的：收集或发送信息到服务器，有利于程序处理信息
    ``<input type="hidden" value="">``

### 2）button标签
- 提交按钮
    ```
    <button>提交按钮</button>
    <button type="submit">提交按钮</button>
    ```
- 重置按钮
    ```
    <button type="reset">重置按钮</button>
    ```
- 普通按钮
    ```
    <button type="button">普通按钮</button>
    ```
> 一般不设置value属性


### 3）select标签——下拉列表
```
    <select>
        <option value=""></option>
        <option value=""></option>
        <option value=""></option>
    </select>
    value属性：表示选项代表的值
    selected属性：下拉列表的默认选中，可以在option标签中写selected或selected="selected"
```

### 4）textarea标签：多行文本域
```
    <textarea></textarea>
    <textarea cols="1" rows="3"></textarea>
        cols属性：宽度
        rows属性：行数
```
> 用于需要输入大量文本的位置
> 不能设置value属性
> textarea{ resize: none; } 禁止用户手动调整

### 5）label标签：表单标注
- 一般与单选按钮、复选框组合使用
- 没有特殊效果，可以扩大点击范围
- 使用：
    - 显示方式
    ```
    <input type="radio" value="男" name="sex" checked id="man">
    <label for="man">男</label> 
    ```
    - 隐式方式
    ```
    <label>
        <input type="checkbox" value="吃饭" name="hob" checked>吃饭
    </label>
    ```

## 3、表单属性
- readonly属性：只读属性，只能读，不能修改，可以被提交
- disabled属性：禁用属性，不可用，不可点击，不会被提交

- maxlength属性：允许输入的最多字符数
- size属性：控件长度

- checked属性：单选按钮和复选框的默认选中
- selected属性：下拉列表项option标签的默认选中

# 兼容问题处理
## 1、IE8中图片边框问题
    解决：
``img{ border: none; }``
## 2、IE8中背景复合属性书写问题
    描述：
``.box{ background: url()no-repeat left top; }``
    解决：
``.box{ background: url() no-repeat left top; }``
## 3、定义鼠标指针形状为手型，并兼容所有浏览器
    解决：
``.box{ cursor: pointer; }``
- cursor: auto; 默认值，浏览器设置光标
- cursor: defalut; 默认光标
- cursor: text; 光标指示文本
- cursor: wait; 程序正忙
- cursor: move; 可移动
- cursor: help; 帮助
- cursor: crosshair; 十字线
## opacity属性  filter属性
## 其他IE低版本兼容问题
- IE6及更早版本浏览器中小高问题
    解决：
```.box{ height: 10px; font-size: 0; line-height: 0; }```
- IE6及更早版本浏览器中浮动产生的双边距BUG
    解决：
    _display: inline; 
- IE7及更早版本浏览器中子元素相对定位，父元素设置overflow属性的auto|hidden失效问题
    解决：
        在父元素中设置position: relative;
- 块元素转行块元素IE7及更早版本的浏览器中不在一行显示问题
    解决：
        *display: inline; *zoom:1;
- IE7及更早版本浏览器中，当li中出现2个及以上的子元素浮动，li之间会产生空白间隙问题
    解决：
        在li标签中设置vertical-align属性，属性值可以是top|middle|bottom