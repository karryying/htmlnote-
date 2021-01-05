# 过渡效果属性——transition属性
## 语法
- transition-property属性：参与过渡的属性  all表示所有属性都有过渡效果
- transition-duration属性：过渡效果执行的时间，默认执行时间为0，属性值单位s|ms
- transition-timing-function属性：速度曲线
    - ease 默认值 平滑过渡
    - ease-in 加速
    - ease-out 减速
    - ease-in-out 先加速后减速
    - linear 匀速
- transition-delay属性：延迟时间，默认时间为0，属性值单位s|ms
- 简写
```
transition: transition-property transition-duration  transition-timing-function  transition-delay;
```
> 参与的属性可以写多组，多个属性名称之间用逗号隔开
```
transition-property: width,background;
```
# 2D|3D转换——transform属性
## 2D转换
- transform: translate(); 位移
    - transform: translate(x,y); 沿着x轴方向和y轴方向位移
    - transform: translateX(); 沿着x轴方向移动
    - transform: translateY(); 沿着y轴方向移动
    > 属性值：向右、向下为正
    > transform: translate(100px);/* 沿着水平方向位移 */

- transform: rotate(); 旋转
    - transform: rotate(ndeg);
    > 属性值：单位deg角度
    > 正值沿着顺时针方向旋转，负值沿着逆时针方向旋转

- transform: scale()缩放
    - transform: scale(x,y) 沿着x轴方向和y轴方向缩放
    - transform: scaleX(x) 沿着x轴方向缩放
    - transform: scaleY(y) 沿着y轴方向缩放
    > 属性值：没有单位，0~1之间表示缩小，1表示正常大小，1以上表示放大
    > transform: scale(2);/* 等比例缩放 */
    > transform: scale(-2);/* 先翻转后缩放 */

- transform: skew() 倾斜
    - transform: skew(x,y) 沿着x轴和y轴倾斜
    - transform: skewX(x) 沿着x轴倾斜
    - transform: skewY(y) 沿着y轴倾斜
    > 属性值：单位deg角度
    > transform: skew(30deg);/* 沿着水平方向倾斜 */
## transform-origin属性：改变基点位置
- 属性值
    - 关键词：left|center|right  top|center|bottom
    - 数值，单位可以是px|em|rem|%
## 3D变形
- 必须要设置的属性
    - transform-style属性
        - transform-style: preserve-3d;创建一个3d空间 
    - perspective属性：景深，单位像素
    > 需要设置在父元素上
- 位移
    - transform: translateX(); 沿着x轴方向位移
    - transform: translateY(); 沿着y轴方向位移
    - transform: translateZ(); 沿着z轴方向位移
    - transform: translate3d(x,y,z) 
- 旋转
    - transform: rotateX(); 沿着x轴方向旋转
    - transform: rotateY(); 沿着Y轴方向旋转
    - transform: rotateZ(); 沿着z轴方向旋转
    - transform: rotate3d(x,y,z,ndeg)
- 缩放
    - transform: scaleX() 沿着x轴方向缩放
    - transform: scaleY() 沿着y轴方向缩放
    - transform: scaleZ() 沿着z轴方向缩放
    - transform: scale3d(x,y,z)
> 实现元素既缩放又旋转
```
 transform: scale(0)  rotate(360deg);
```

# 动画
## 1、帧动画
- 第一步：定义帧动画
```
    @keyframes 动画名称（英文）{
        0%{ 动画开始 }  
        50%{}
        100%{ 动画结束 }
    }
    @keyfames 动画名称{
        from{ 动画开始 }
        to{ 动画结束 }
    }
```
- 第二步：引用关键帧
```
animation: animation-name animation-duration [animation-timing-function] [animation-delay] [animation-iteration-count] [animation-direction] [animation-fill-mode];
animation: 动画的名称 动画执行时间（s|ms） 动画的速度曲线（ease|ease-in|ease-out|ease-in-out|linear） 延迟时间 动画执行的次数 动画如何播放 动画结束之后显示的状态;
    动画执行的次数：默认为1，infinite无限循环 
    动画如何播放：
        normal 正常播放
        alternate 正向、反向轮流播放
        reverse 反向播放
        alternate-reverse 反向、正向轮流播放
    动画结束之后显示状态：
        both 动画结束或开始时的状态
        forwards 动画结束时的状态
        backwards 动画开始时的状态
```
## 2、animate.css动画库
    css3动画库，预设了闪烁（flash)、弹跳（bounce）、翻转（flip)、旋转（rotateIn|rotateOut）、淡入淡出（fadeIn|fadeOut）、抖动（shake）等动画效果。
- 使用方法
    - 1）引入文件：<link rel="stylesheet" href="css/animate.min.css">
    - 2）使用：
    <p class="animate__animated animate__bounceIn">内容</p>
    animate__animated为基本类名，必须要添加
    animate__bounceIn为指定动画样式名称

## css3中过渡和动画的区别和各自适用场景？
区别：语法、触发、执行次数、复杂度

# calc()函数
    css3中新增功能，用于动态计算长度值
    流体布局：屏幕分辨率变化时，页面中元素的大小会变化，但是布局不变
- 语法
```
calc(表达式)
    可以用来实现加、减、乘、除四则运算
```
> 运算符的前后需要添加空格
```
    width: calc(100px +100px);/* 语法错误 */
    width: calc(100px+100px);/* 语法错误 */ 
```
> 运算规则：有括号先算括号里面的，先算乘除后算加减
```
width: calc(1000px - (100px + 100px) * 2);/*600px*/
```
- 兼容
    在IE9+、firefox、chrome、Safari可以正常呈现
- 利用calc函数实现三列自适应布局