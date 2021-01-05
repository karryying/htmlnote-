# Grid布局——网格布局
- flex布局：弹性布局，轴线布局，只能在指定的轴线上排列，可以看作一维布局
- grid布局：网格布局，二维布局，水平方向和垂直方向同时存在
## 1、基本概念
- 容器container：采用网格布局的区域
- 项目item：容器中采用网格定位的子元素

- 行row：容器中的水平区域
- 列column：容器中的垂直区域

- 单元格cell：行列交叉区域，正常情况下m行n列  m*n个单元格

- 网格线grid line：划分网格的线
    - 水平网格线    行
    - 垂直网格线    列
    正常情况下，m行有m+1根水平网格线，n列有n+1根垂直网格线
## 2、属性
- 容器属性
    - display属性：指定容器使用网格布局
        - display: grid;
        - display: inline-grid;
    - grid-template-rows、grid-template-columns 对网格进行水平方向和垂直方向的划分
        - 属性值：px、百分比、auto、fr(对网格剩余空间比例分配，值的大小大于等于1全部分配，否则会有剩余空间)
        - repeat() 重复，可以设置两个参数，第一个参数表示重复次数，第二参数表示重复的值
        - minmax() 长度范围，两个参数，分别表示最大值和最小值
        - 网格线名称
        ```
            grid-template-rows: [r1] 100px [r2] 200px [r3] 100px;
            grid-template-columns: [c1] 100px [c2] 200px [c3] 100px;
        ```
    - grid-row-gap属性、grid-column-gap属性、grid-gap属性 设置网格间隙
        - grid-gap: grid-row-gap grid-column-gap;
    ```
        grid-row-gap: 10px;/* 行间隙 */
        grid-column-gap: 20px;/* 列间隙 */
        grid-gap: 10px;/* 行间隙和列间隙都为10像素 */
        grid-gap: 10px 0; /* 10px指行间隙 */
        grid-gap: 0 20px;/* 20px值列间隙 */
    ```
    - grid-auto-flow属性：划分网格后，对容器中子元素的排列位置的调整
        - grid-auto-flow: row; 默认值，先行后列的排序
        - grid-auto-flow: column; 先列后行
    - justify-items属性、align-items属性、place-items属性：内容的分布
        - justify-items属性：设置网格元素的水平呈现方式
        - align-items属性：设置网格元素的垂直呈现方式
        - place-items: align-items justify-items;
        - 属性值
            - start 单元格左侧对齐或顶端对齐
            - end  单元格右侧对齐或底端对齐
            - center 单元格中间对齐
            - stretch 占满整个单元格，默认
    - justify-content属性、align-content属性、place-content属性  元素分布
        - justify-content属性：水平分布方式
        - align-content属性：垂直分布方式
        - place-content: align-content justify-content; 
        - 属性值：
            - start 容器的起始位置 默认值
            - end 容器的结束位置
            - center 容器的中间位置
            - space-between 项目之间留有空白间隙
            - space-around 项目之间、之前、之后都留有空白间隙，并且项目之间间隔比容器和项目之间的间隔大
            - space-evenly 项目之间、之前、之后都留有空白间隙，并且项目之间间隔和容器与项目之间的间隔相等
    - grid-template-area属性 定义网格区域
        ```
        .wrap1{
            grid-template-areas: "b1 b1 b2"
                                 "b3 b3 b2"
                                 "b3 b3 b2";
        /*将3行3列的单元格分成三类，用3个项目实现布局*/    
        }
        ```
        项目属性：grid-area属性：项目处在哪个区域
        ```
        .wrap1 div:nth-child(1){
            grid-area: b1;
        }
        .wrap1 div:nth-child(2){
            grid-area: b2;
        }
        .wrap1 div:nth-child(3){
            grid-area: b3;
        }
        ```
- 项目属性
    - 指定项目的位置
        - grid-column-start属性： 项目的左边在哪根网格线上
        - grid-column-end属性： 项目的右边在哪根网格线上
        - grid-row-start属性： 项目的上边在哪根网格线上
        - grid-row-end属性： 项目的下边在哪根网格线上

        - grid-column属性
            grid-column: grid-column-start/grid-column-end;
        - grid-row属性
            grid-row: grid-row-start/grid-row-end;
    - justify-self属性、align-self属性、place-self属性  设置单元格内容对齐方式
        - justify-self属性： 单元格内容水平对齐方式
        - align-self属性：单元格内容垂直对齐方式
        - place-self: align-self justify-self;
        - 属性值
            - start 单元格起始位置
            - end 单元格结束位置
            - center 单元格中间位置
            - stretch   默认值，占满整个单元格

# a标签
- 点击之后会直接打开邮件客户端，在收件人栏"111@163.com"
```
<a href="mailto:111@163.com">111@163.com</a>
```
- 为10086和10010发送内容为ABC的信息
```
<a href="sms:10086,10010?body=ABC">发送信息</a>
```
- 点击后可以直接拨打400-400-400电话
```
<a href="tel:400400400">拨打电话400-400-400</a>
```
- 下载图片
```
<a href="images/logo.jpg" download="logo.jpg">下载图片</a>
```