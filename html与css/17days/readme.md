# flexible.js + rem
- lib-flexible  手机淘宝团队
- 用来解决HTML5页面终端适配问题
- 开源库
- 实现原理
    设备划分10等份，确定好html标签的font-size属性值
    如：750px   html{ font-size: 75px; }，页面中元素的rem值 = 元素的px值/75，剩余部分由flexible.js来完成
## 1、使用方法
### 1)在head标签中，插入库文件
- 直接下载文件到本地，通过script标签对链接
```
<script src="js/flexible.min.js"></script>
```
- 通过script标签对，加载CDN文件
```
<script src="http://g.tbcdn.cn/mtb/lib-flexible/0.3.4/??flexible_css.js,flexible.js"></script>
```
> dpr 设备像素比
### 2）将视觉稿中的px转换成rem
## 2、flexible的实质
—— 动态改写dpr、根元素的font-size
- 做的工作
    - 动态改写meta标签
    ```
    <meta name="flexible" content="initial-dpr=2">
    initial-dpr将dpr设置为给定的值
    ```
    - 动态改写data-dpr的值
    - 给html标签添加font-size属性值，并动态改写font-size的值
## 3、特点
- 优点：可以很方便的解决HTML5页面的适配问题
- 缺点：由于viewport单位得到众多浏览器的兼容，lib-flexible这个过渡方案已经可以放弃使用，不管是现在的版本还是以前的版本，都存有一定的问题。    

# css3中过渡和动画的区别和各自的适用场景
## 区别：
- 1）语法：
    - 过渡：transition: 参与过渡属性名称  过渡的完成时间  速度曲线  延迟时间;
    - 动画：
        @keyframes 动画名称{} 定义关键帧
        animation:动画名称 动画的执行时间 速度曲线 延迟时间 播放次数 播放顺序; 引用关键帧
- 2）触发：
    - 过渡：需要借助伪类、JavaScript、@media触发
    - 动画：自动触发
- 3）执行次数
    - 过渡：执行一后不会执行，但是可以通过transitionEnd事件添加循环
    - 动画：可以通过animation-iteration-count属性设置循环的次数
- 4）复杂度
    - 过渡：简单动画效果
    - 动画：复杂动画效果，可以定义关键帧，控制每一帧的动画效果
## 适用场景
    - 过渡：适用于元素从一种样式变换为另一种样式的动画效果
    - 动画：可以在网页中取代动画图片、flash及需要灵活定位多个帧及循环的动画中

- img标签上title和alt属性的区别？
    - 分析：功能、属性、适用标签
- web标准的理解
    - 分析：三层分离结构、W3C、W3C对web标准提出的编码规范
- 谈谈你对HTML5和css3的理解
- div+css布局较table布局由什么优点？
